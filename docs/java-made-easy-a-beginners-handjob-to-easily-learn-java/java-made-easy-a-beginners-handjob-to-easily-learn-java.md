
# 轻松学 Java：初学者快速上手指南

## 第 18 章：LocalTime

`LocalTime`类表示一个不带时区的时间。它用于表示小时、分钟、秒和纳秒。`LocalTime`类基于自然时间基钟。

| 方法 | 说明 |
| --- | --- |
| `getHour()` | 返回一天中的小时 |
| `getMinute()` | 返回一天中的分钟 |
| `getSecond()` | 返回一天中的秒 |
| `getNano()` | 返回一天中的纳秒 |

### 第 18.1 节：LocalTime 之间的时间间隔

以下示例展示了如何计算两个`LocalTime`对象之间的时间。

```java
LocalTime start = LocalTime.of(10, 30);
LocalTime end = LocalTime.of(12, 45);
Duration duration = Duration.between(start, end);
System.out.println(duration.toMinutes());
```

`Duration`类表示以秒和纳秒计算的时间量，用于计算两个时间之间的差值。

## 第 19 章：BigDecimal

`BigDecimal`类用于高精度有符号小数算术。它通常用于对舍入控制至关重要的金融应用。

### 第 19.1 节：使用 BigDecimal 代替 float

以下示例演示了为什么`BigDecimal`优于`float`或`double`。

```java
double a = 0.1;
double b = 0.2;
System.out.println(a + b); // 输出 0.30000000000000004

BigDecimal ba = new BigDecimal("0.1");
BigDecimal bb = new BigDecimal("0.2");
System.out.println(ba.add(bb)); // 输出 0.3
```

`BigDecimal`比浮点类型提供了更高的精度。

## 第 23 章：Arrays

`Arrays`类提供了用于操作数组的静态方法（如排序、搜索和填充）。

### 第 23.1 节：创建和初始化数组

以下示例展示了如何创建和初始化数组。

```java
int[] numbers = {1, 2, 3, 4, 5};
int[] arr = new int[5];
Arrays.fill(arr, 10);
```

`Arrays`类还提供了搜索数组的方法。

```java
int[] arr = {5, 2, 9, 1, 3};
Arrays.sort(arr);
int index = Arrays.binarySearch(arr, 3);
System.out.println(index); // 输出 2
```

- 章节 14.1: 按空格分割的 `StringTokenizer` 71
- 章节 17.6: 日期时间格式化 ...................................................... 85
- 第 33.3 节：栈 (`Stacks`) ....................................................................... 183
- 第 35.3 节：带有抽象方法的枚举 ................................................ 193
- 第 35.5 节：使用单元素枚举实现单例模式 ........................................ 195

## 第 43.9 节：用于 `this` 和接收者参数的注解 253

## 第 47.3 节：菱形语法 269

## 第 50.2 节：静态类与非静态类 290

- 54.1 节：继承 ...... 305
- 54.11 节：继承与静态方法 ...... 318
- 58.4 节：`DataInputStream` 示例 ... 351
- 66.5 节：使用 Jackson 进行自定义 JSON 反序列化 ... 384

## 第 68 章：对象引用..................................................................391

第 69.8 节：创建和读取堆栈跟踪 ............................................ 406

第 73.9 节：从传统风格到 Lambda 风格 ......................................................... 433

- 第 87.2 节：特定范围内的伪随机数 ....................................... 512
- 第 89.4 节：`Integer` 和 `int` 可以互替使用的稀有情况 ........................... 524
- 第 89.5 节：自动装箱的内存和计算开销 ..........................

# 第 97.1 节：执行 JavaScript 文件 ............................................................ 554

第 98.1 节：从 Java 调用 C++ 方法 ....................................................... 558

第 106.4 节：常量数表达式 599

# 第 107 章：Java 中的 JSON 601

第 107.1 节：使用 Jackson Object Mapper 601

第 107.2 节：JSON 转对象 (Gson Library) 602

第 107.3 节：`JSONObject` 602

第 107.4 节：JSON 构建器 - 链式调用 603

第 107.5 节：对象转 JSON (Gson Library) 603

第 107.6 节：JSON 迭代 603

第 107.7 节：`optXXX` 与 `getXXX` 方法 604

第 107.8 节：从 JSON 提取单个元素 604

第 107.9 节：`JsonArray` 转 Java List (Gson Library) 604

第 107.10 节：编码数据为 JSON 605

第 107.11 节：解码 JSON 数据 605

# 第 108 章：使用 JAXP API 解析 XML 607

第 108.1 节：使用 StAX API 解析文档 607

第 108.2 节：使用 DOM API 解析并导航文档 608

# 第 109 章：XML XPath 求值 610

第 109.1 节：在单个 XML 中解析多个 XPath 表达式 610

第 109.2 节：在 XML 中多次解析单个 XPath 表达式 610

第 109.3 节：评估 XML 文档中的 `NodeList` 611

第 110 章：XOM - XML 对象模型 612

第 110.1 节：读取 XML 文件

### 第 110.2 节：写入 XML 文件

## 第 111 章：多态

### 第 111.1 节：方法重写

### 第 111.2 节：方法重载

### 第 111.3 节：多态与不同的重写类型

### 第 111.4 节：虚函数

### 第 111.5 节：通过添加类来增加功能而不接触现有代码……

## 第 112 章：封装

### 第 112.1 节：封装维护不变性……

### 第 112.2 节：封装减少耦合……

## 第 113 章：Java Agent

### 第 113.1 节：使用代理修改类……

### 第 113.2 节：在运行时添加代理……

### 第 113.3 节：设置基础代理……

## 第 114 章：变长参数 (`Varargs`)

### 第 114.1 节：使用变长参数

### 第 114.2 节：指定变长参数

## 第 115 章：日志 (`java.util.logging`)

### 第 115.1 节：记录复杂消息（高效）

### 第 115.2 节：使用默认记录器

### 第 115.3 节：日志级别

## 第 116 章：log4j / log4j2

### 第 116.1 节：通过属性文件记录日志

### 第 116.2 节：如何获取 Log4j

### 第 116.3 节：设置属性文件

### 第 116.4 节：基础 log4j2.xml 配置文件

### 第 116.5 节：在 Java 代码中遍历 Log4j

### 第 116.6 节：从 log4j.1x 迁移到 2.x

### 第 116.7 节：按级别过滤日志输出 (log4j 1.x)

## 第 117 章：Oracle 代码标准

### 第 117.1 节：命名规范

### 第 117.2 节：类结构

### 第 117.3 节：注解

### 第 117.4 节：导入语句

### 第 117.5 节：大括号

### 第 117.6 节：冗余括号

### 第 117.7 节：修饰符

### 第 117.8 节：缩进

### 第 117.9 节：字面量

### 第 117.10 节：包声明

### 第 117.11 节：Lambda 表达式

### 第 117.12 节：Java 源文件

### 第 117.13 节：语句换

### 第 117.14 节：方法声明换

### 第 117.15 节：表达式换

### 第 117.16 节：空白符

### 第 117.17 节：特殊字符

### 第 117.18 节：变量声明

## 第 118 章：字符编码

### 第 118.1 节：从 UTF-8 编码的文件中读取文本

### 第 118.2 节：向 UTF-8 文件写入文本

### 第 118.3 节：获取字符串的 UTF-8 字节表示形式

## 第 119 章：Apache Commons Lang

### 第 119.1 节：实现 `equals()` 方法

### 第 119.2 节：实现 `hashCode()` 方法

### 第 119.3 节：实现 `toString()` 方法

## 第 120 章：本地化与国际化

### 第 120.1 节：语言区域 (`Locale`)

### 第 120.2 节：使用 `locale` 格式化日期

### 第 120.3 节：字符串比较

## 第 121 章：使用 Fork/Join 框架进行并行编程

### 第 121.1 节：Fork/Join 任务

## 第 122 章：非访问修饰符

### 第 122.1 节：`final`

### 第 122.2 节：`static`

### 第 122.3 节：`abstract`

### 第 122.4 节：`volatile`

### 第 122.5 节：`synchronized`

### 第 122.6 节：`transient`

### 第 122.7 节：`transient`

## 第 123 章：进程

### 第 123.1 节：`Runtime.exec()`、`ProcessBuilder` 不理解 shell

### 第 123.2 节：简单示例（版本）

## 第 124 章：Java Native接口访问 (JNA)

### 第 124.1 节：JNA 简介

## 第 125 章：模块

### 第 125.1 节：定义基础模块

## 第 126 章：并发编程（线程）

### 第 126.1 节：`Callable` 和 `Future`

### 第 126.2 节：`CountDownLatch`

### 第 126.3 节：基础多线程

### 第 126.4 节：作为同步辅助的锁

### 第 126.5 节：`Semaphore`

### 第 126.6 节：同步

### 第 126.7 节：`Runnable` 对象

### 第 126.8 节：创建基础死锁系统

### 第 126.9 节：创建 `java.lang.Thread` 实例

### 第 126.10 节：原子操作

### 第 126.11 节：排斥写/并发读

### 第 126.12 节：生产者-消费者

### 第 126.13 节：使用 `synchronized` / `volatile` 时的读写屏障可视化

### 第 126.14 节：获取程序启动的所有线程（排除系统线程）

### 第 126.15 节：使用 `ThreadLocal`

### 第 126.16 节：带有共享全局队列的多生产者消费者示例

### 第 126.17 节：使用线程池相两个 `int` 数组

### 第 126.18 节：暂停执行

### 第 126.19 节：线程中断 / 停止线程

## 第 127 章：`Executor`、`ExecutorService` 和线程池

### 第 127.1 节：`ThreadPoolExecutor`

### 第 127.2 节：从计算中获取值 - `Callable`

### 第 127.3 节：`submit()` 与 `execute()` 的异常处理差异

### 第 127.4 节：处理拒绝执行的情况

### 第 127.5 节：发后即忘 - `Runnable` 任务

### 第 127.6 节：不同并发结构的使用场景

- 章节 127.7: 等待 `ExecutorService` 中所有任务完成..........................................699
- 章节 127.8: 不同类型 `ExecutorService` 的用例......................................................701
- 章节 127.9: 调度在固定时间、延迟后或重复运行的任务................................................................................7703
- 章节 127.10: 使用线程池.........................................................................................................704

## 第 128 章：`ThreadLocal`................................................................................................................705

- 章节 128.1: `ThreadLocal` 的基本用法...............................................................................................706
- 章节 128.2: `ThreadLocal` 的 Java 8 函数式初始化...............................................................................707
- 章节 128.3: 多个线程共享一个对象...............................................................................709

## 第 129 章：在多线程中使用 `ThreadPoolExecutor`................................................................................................................................710

- 章节 129.1: 使用 `Runnable` 类实例执行不需要返回值的异步任务................................................................................................................713
- 章节 129.2: 使用 `Callable` 类实例执行需要返回值的异步任务................................................................................................................................
- 章节 129.3: 使用 Lambda 内联定义异步任务................................................................................715

## 第 130 章：常见的 Java 陷阱.........................................................................................................................

- 章节 130.1: 使用 `==` 比较 `Integer` 等基本类型包装类对象的陷阱................................................................................
- 章节 130.2: 陷阱：使用 `==` 比较字符串
- 章节 130.3: 陷阱：忘记释放资源 ................................................ 715
- 章节 130.4: 陷阱：在尝试打开文件之前进行测试 ........................................ 717
- 章节 130.5: 陷阱：将变量视为对象 ............................................... 718



# 第 130 章：Java 陷阱 - 常见陷阱

## 130.6 陷阱：内存泄漏

## 130.7 陷阱：未理解 `String` 是不可变类

## 130.8 陷阱：结合赋值和副作用

# 第 131 章：Java 陷阱 - 异常的使用

## 131.1 陷阱：捕获 `Throwable`、`Exception`、`Error` 或 `RuntimeException`

## 131.2 陷阱：忽略或吞掉异常

## 131.3 陷阱：抛出 `Throwable`、`Exception`、`Error` 或 `RuntimeException`

## 131.4 陷阱：使用异常进行正常流程控制

## 131.5 陷阱：直接子类 `Throwable`

## 131.6 陷阱：捕获 `InterruptedException`

## 131.7 陷阱：过度或不适当的堆栈轨迹

# 第 132 章：Java 陷阱 - 语言语法

## 132.1 陷阱：在 `switch` case 中缺少 `break`

## 132.2 陷阱：声明与标准类同名的类

## 132.3 陷阱：省略大括号："悬空 if"和"悬空 else"问题

## 132.4 陷阱：八进制字面量

## 132.5 陷阱：使用 `==` 测试布尔值

## 132.6 陷阱：忽略方法的可见性

## 132.7 陷阱：使用 `assert` 进行参数或用户输入验证

## 132.8 陷阱：通配符导入会使你的代码变得脆弱

## 132.9 陷阱：分号位置错误和缺少括号

## 132.10 陷阱：使用重载代替重写

## 132.11 陷阱：将空对象自动拆箱为基本类型

# 第 133 章：Java 陷阱 - 线程与并发

## 133.1 陷阱：继承 `java.lang.Thread`

## 133.2 陷阱：线程过多会导致应用程序变慢

## 133.3 陷阱：不正确使用 `wait()` / `notify()`

## 133.4 陷阱：共享变量需要适当的同步

## 133.5 陷阱：线程创建开销相对大

# 第 134 章：Java 陷阱 - Null 和空指针异常

## 134.1 陷阱："修复"意外的 `null`

## 134.2 陷阱：使用 `null` 表示空数组或集合

## 134.3 陷阱：在关闭 I/O 流时未检查是否已初始化

## 134.4 陷阱：返回 `null` 而不是抛出异常

## 134.5 陷阱：不必要使用基本类型包装类会导致 `NullPointerException`

## 134.6 陷阱：使用"Yoda 表达式"避免空指针异常

# 第 135 章：Java 陷阱 - 性能问题

## 135.1 陷阱：循环中的字符串拼接无法扩展

## 135.2 陷阱：使用 `size()` 测试集合是否为空效率低下

## 135.3 陷阱：对可以使用 `==` 的字符串进行池化是一个坏主意

## 135.4 陷阱：使用 `new` 创建基本类型包装实例效率低下

## 135.5 陷阱：正则表达式的效率问题

## 135.6 陷阱：未缓冲流的小规模读/写效率低下

## 135.7 陷阱：过度使用基本类型类型效率低下

## 135.8 陷阱：创建日志消息的开销

## 135.9 陷阱：遍历 `Map` 的键可能效率低下

## 135.10 陷阱：调用 `System.gc()` 效率低下

## 135.11 陷阱：调用 `new String(String)` 效率低下

# 第 136 章：ServiceLoader

## 136.1 简单的 `ServiceLoader` 示例

## 136.2 日志服务（Logger Service）

# 第 137 章：类加载器（Classloaders）

## 137.1 实现自定义类加载器

## 137.2 加载外部 `.class` 文件

## 137.3 实例化并使用类加载器

# 第 138 章：程序化创建图像

## 138.1 通过程序化创建并显示简单图像

## 138.2 将图像保存到磁盘

## 138.3 在 `BufferedImage` 中设置单个像素的颜色

## 138.4 指定图像渲染质量

## 138.5 使用 `BufferedImage` 类创建图像

## 138.6 使用 `BufferedImage` 编辑和复用图像

## 138.7 如何缩放 `BufferedImage`

# 第 139 章：原子类型（Atomic Types）

## 139.1 创建原子类型

## 139.2 原子类型的动机

# 第 140 章：RSA 加密

## 140.1 使用 OAEP 和 GCM 组成的混合加密系统示例

# 第 141 章：安全对象（Secure Objects）

## 141.1 密封对象（`javax.crypto.SealedObject`）

## 141.2 签名对象（`java.security.SignedObject`）

# 第 142 章：安全与密码学（Security & Cryptography）

## 142.1 计算密码哈希值

## 142.2 使用公钥/私钥加密和解密数据

## 142.3 生成密码随机数据

## 142.4 生成公钥/私钥对

## 142.5 计算并验证数字签名

# 第 143 章：安全与密码学（Security & Cryptography）

## 143.1 JCE

## 143.2 密钥与密钥管理

## 143.3 常见的 Java 漏洞

## 143.4 网络注意事项

## 143.5 随机性与你

## 143.6 哈希与验证

# 第 144 章：SecurityManager

## 144.1 对由 `ClassLoader` 加载的类进行沙箱化处理

## 144.2 启用 `SecurityManager`

## 144.3 实现策略拒绝规则

# 第 145 章：JNDI

## 145.1 通过 JNDI 使用 RMI

# 第 146 章：sun.misc.Unsafe

## 146.1 通过反射实例化 `sun.misc.Unsafe`

## 146.2 通过 bootclasspath 实例化 `sun.misc.Unsafe`

## 146.3 获取 `Unsafe` 实例

## 146.4 `Unsafe` 的用途

# 第 147 章：Java 内存模型（Java Memory Model）

## 147.1 内存模型的动机

## 147.2 Happens-before（发生之前）关系

## 147.3 如何避免需要理解内存模型

## 147.4 应用于某些示例的 Happens-before 推理

# 第 148 章：Java 部署

## 148.1 从命令行创建可执行的 JAR



# 第148.2节：为应用程序及其依赖创建 UberJAR

# 第148.3节：创建 JAR、WAR 和 EAR 文件

# 第148.4节：Java Web Start 简介

# 第149章：Java 插件系统

## 第149.1节：使用 `URLClassLoader`

# 第150章：JavaBean

## 第150.1节：基础 Java Bean

# 第151章：Java SE 7 特性

## 第151.1节：新的 Java SE 7 语言特性

## 第151.2节：二进制字面量 (Binary Literals)

## 第151.3节：`try-with-resources` 语句

## 第151.4节：数值字面量中的下划线

## 第151.5节：泛型实例创建的类型推断

## 第151.6节：`switch` 语句中的字符串

# 第152章：Java SE 8 特性

## 第152.1节：新的 Java SE 8 语言特性

# 第153章：动态方法分发 (Dynamic Method Dispatch)

## 第153.1节：动态方法分发 - 示例代码

# 第154章：生成 Java 代码

## 第154.1节：从 JSON 生成 POJO

# 第155章：JShell

## 第155.1节：编辑代码片段 (Snippets)

## 第155.2节：进入和退出 JShell

## 第155.3节：表达式

## 第155.4节：方法与类

## 第155.5节：变量

# 第 156 章：堆栈遍历 API (Stack-Walking API)

- 156.1 节：打印当前线程的所有栈帧
- 156.2 节：打印当前调用者类
- 156.3 节：显示反射和其他隐藏帧

# 第 157 章：套字 (Sockets)

- 157.1 节：从套字读取数据

# 第 158 章：Java 套字

- 158.1 节：一个简单的 TCP 回显服务器

# 第 159 章：FTP (文件传输协议)

- 159.1 节：连接并登录 FTP 服务器

# 第 160 章：在 Java 中使用其他脚本语言

- 160.1 节：在 `nashorn` 的 `-script` 模式下评估 JavaScript 文件

# 第 161 章：C++ 比较

- 161.1 节：静态类成员
- 161.2 节：在其他结构内部定义的类
- 161.3 节：值传递与引用传递
- 161.4 节：继承 vs 组合
- 161.5 节：强制向下转换
- 161.6 节：抽象方法与类

# 第 162 章：音频

- 162.1 节：播放 MIDI 文件
- 162.2 节：循环播放音频文件
- 162.3 节：基础音频输出
- 162.4 节：裸金属音频

# 第 163 章：Java 打印服务 (Print Service)

- 163.1 节：构建将打印的文档
- 163.2 节：发现可用的打印服务
- 163.3 节：定义打印请求属性
- 163.4 节：监听打印作业请求的状态变化
- 163.5 节：发现默认打印服务
- 163.6 节：从打印服务创建打印作业

# 第 164 章：CompletableFuture

- 164.1 节：`CompletableFuture` 的简单示例

# 第 165 章：运行时命令

- 165.1 节：添加停机钩子

# 第 166 章：单元测试

- 166.1 节：什么是单元测试?

# 第 167 章：断言 (Asserting)

- 167.1 节：使用 `assert` 检查算术

# 第 168 章：多版本 JAR 文件 (Multi-Release JAR Files)

- 168.1 节：多版本 Jar 文件内容的示例
- 168.2 节：使用 `jar` 工具创建多版本 Jar
- 168.3 节：多版本 Jar 内部加载的类的 URL

# 第 169 章：即时编译器 (JIT compiler)

- 169.1 节：概述

# 第 170 章：字节码修改

- 170.1 节：什么是字节码?
- 170.2 节：如何使用 ASM 编辑 jar 文件
- 170.3 节：如何将 `ClassNode` 加载为 `Class`
- 170.4 节：如何在 jar 文件中重命名类
- 170.5 节：Javasist 基础

# 第 171 章：反汇编与反编译

- 171.1 节：使用 `javap` 查看字节码

# 第 172 章：JMX

- 172.1 节：使用 Platform MBean 服务器的简单示例

# 第 173 章：Java 虚拟机 (JVM)

- 173.1 节：这些是

# 第 174 章：XJC

- 174.1 节：从 XSD 生成代码

# 第 175 章：JVM 标志

- 175.1 节：`-aggressive`
- 175.2 节：`-allocClear`
- 175.3 节：`-allocSize`
- 175.4 节：`-Profiling`
- 175.5 节：`-disableSpin`
- 175.6 节：`-disableGCHeuristics`
- 175.7 节：`-dumpSize`
- 175.8 节：`-exitOutOfMemory`

# 第 176 章：JVM 工具接口 (Tool Interface)

- 176.1 节：遍历堆的可达对象 (Heap 1)
- 176.2 节：获取 JVMTI 环境
- 176.3 节：Agent OnLoad 方法中的初始化示例

# 第 177 章：Java 内存管理

- 177.1 节：设置堆、PermGen 和栈的大小
- 177.2 节：垃圾回收
- 177.3 节：Java 中的内存泄漏



## 第 177.4 节：终化（Finalization）

## 第 177.5 节：手动触发 GC

## 第 178 章：Java 性能调优

- 178.1 节：基于证据的 Java 性能调优方法
- 178.2 节：减少字符串数量
- 178.3 节：通用方法

## 第 179 章：基准测试（Benchmarks）

- 179.1 节：简单的 JMH 示例

## 第 180 章：上传到 AWS

- 180.1 节：上传文件到 s3 桶

## 第 181 章：AppDynamics 和 TIBCO BusinessWorks 插桩以便于集成

- 181.1 节：单步对所有 BW 应用进行 AppDynamics 插桩的示例

## 附录 A：安装 Java（标准版）

- A.1 节：在 Windows 上安装后设置 `%PATH%` 和 `%JAVA_HOME%`
- A.2 节：在 Linux 上安装 Java JDK
- A.3 节：在 macOS 上安装 Java JDK
- A.4 节：在 Windows 上安装 Java JDK 或 JRE
- A.5 节：使用 `alternatives` 在 Linux 上配置和切换 Java 版本
- A.6 节：Java 开发需要什么
- A.7 节：选择合适的 Java SE 版本
- A.8 节：Java 发布与版本命名
- A.9 节：使用最新的 tar 包在 Linux 上安装 Oracle Java
- A.10 节：Linux 上的后检查与配置

## 附录 B：Java 版本、版本、发布和发行版

- B.1 节：Java SE JRE 与 Java SE JDK 发行版之间的区别
- B.2 节：Java SE 版本
- B.3 节：Java EE、Java SE、Java ME 和 JavaFX 之间的区别

## 附录 C：Classpath（类路径）

- C.1 节：指定 classpath 的不同方法
- C.2 节：将目录下的所有 JAR 添加到 classpath
- C.3 节：从 classpath 加载资源
- C.4 节：Classpath 路径语法

## C.5 节：动态 classpath

## C.6 节：将类名映射到路径名

## C.7 节：引导类路径（bootstrap classpath）

## C.8 节：classpath 的含义：搜索机制工作原理

## 附录 D：资源（在 classpath 上）

## D.1 节：加载默认配置

## D.2 节：从资源加载图像

## D.3 节：使用类加载器查找并读取资源

## D.4 节：从多个 JAR 加载同名资源

## 致谢

## 你可能喜欢

## 关于

可以免费地与任何人分享此 PDF，本书的最新版本可以从此处下载：`https://goalkicker.com/JavaBook`

本《Java® Notes for Professionals》一书编译自 Stack Overflow 文档，内容由 Stack Overflow 的才华们编写。文本内容根据 Creative Commons BY-SA 协议发布，请参书末对各章节做出贡献的致谢部分。除非另有说明，图像可能属于其各自所有者的版权。

这是一本为教育目的创建的非官方书籍。书中介绍的信息不保证准确，商标是其各自所有者的财产。请向 `web@example.com` 反馈反馈和修正。

## 第 1 章：Java 入门

| 语言 | 版本 | 标识 | 停止支持 |
| :--- | :--- | :--- | :--- |
| Java SE | 10 | 早期访问 | |
| Java SE | 9 | | |
| Java SE | 8 | | |
| Java SE | 7 | | |
| Java SE | 6 | | |
| Java SE | 5 | | |
| Java SE | 4 | | |
| Java SE | 3 | | |
| Java SE | 2 | | |
| Java SE | 1 | | |
| Java SE | 0 | | |

## 创建你的第一个程序

要创建一个 Java 程序，请在你的编辑器中创建一个名为 `HelloWorld.java` 的新文件。然后将以下代码粘贴其中：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

命名规范建议类以大写字母开头。文件名必须与类名相同。

要编译你的程序，打开终端并导航到包含 `HelloWorld.java` 的目录。然后运行：

```
$ javac HelloWorld.java
```

编译器将生成一个名为 `HelloWorld.class` 的字节码，该文件可以在 Java 虚拟机（JVM）中执行。

要运行你的程序，输入 `java` 后紧跟包含 `main` 方法的类名。注意 `.class` 被省略了：

```
$ java HelloWorld
```

将在你的控制台输出：

```
Hello, World!
```

你已成功编译并构建了你的第一个 Java 程序！

为了让 Java 命令（`java`、`javac` 等）能够被识别，你需要确保：

- 已安装 JDK（例如 Oracle、OpenJDK 以及其他来源）
- 你的环境变量已正确设置

在 Windows XP/7/8/10 中编辑 `PATH` 变量：

控制面板 ⇒ 系统高级设置 ⇒ “高级”选项卡 ⇒ 环境变量。在“系统变量”中，向下滚动选择“PATH” ⇒ 编辑

要获取 `javac` 的确切路径，浏览到文件夹并点击地址栏然后复制它。它看起来应该像 `c:\Program Files\Java\1.8.0_xx\bin`。在“变量值”字段中，将此路径粘贴在所有现有目录的**前面**，并跟随一个分号（`;`）。请删除任何现有的条目。

变量名：`PATH`

变量值：`c:\Program Files\Java\1.8.0_xx\bin;[Existing Entries...]`

## 深入研究 Hello World 程序

“Hello World”程序包含单个文件，其中包含 `HelloWorld` 类定义、一个 `main` 方法以及 `main` 方法内部的一条语句。

```java
public class HelloWorld {
```

`class` 关键字开始定义名为 `HelloWorld` 的类的定义。

每个 Java 应用程序至少包含一个类定义（更多关于类的信息）。

```java
public static void main(String[] args) {
```

这是一个入口方法（通过其名称和签名 `public static void main(String[] args)` 来定义），JVM 可以从这里运行你的程序。每个 Java 程序都应该有一个。它：

`public`：意味着该方法可以从程序外的任何地方被调用。更多信息请参见“可见性（Visibility）”。

`static`：意味着它独立存在并可以运行（在类级别运行，无需创建对象）。`void`：意味着它不返回任何值。注意：这与 C 和 C++ 不同，后者期望返回如 `int` 的返回代码（Java 的做法是使用 `System.exit()`）。

此 `main` 方法接收：

- 作为参数传递给 `main` 函数的 `String` 数组（通常称为 `args`，例如来自命令行参数）。

对于 Java 入口方法，几乎所有内容都是必须的。

非强制部分：

名称 `args` 是一个变量，因此你可以为它起任何名称，尽管通常称为 `args`。它的参数类型是数组 `(String[]) args` 还是变长参数 `(String... args)` 并不重要，因为数组可以传递给变长参数。

注意：单个应用程序可以包含多个带有入口（`main`）方法的类。应用程序的入口点是由作为 `java` 命令参数传递的类名决定的。

在 `main` 方法内部，我们看到了以下语句：

`System.out.println("Hello, World!");`

让我们逐个元素地分解这个语句：

## 元素

| 元素 | 用途 |
| :--- | :--- |
| `System` | 这表示随后的表达式将调用来自 `java.lang` 包的 `System` 类。 |
| `.` | 这是一个“点运算符”（dot operator）。点运算符允许访问类的成员；即它的字段（变量）和方法。在这种情况下，点运算符允许你引用 `System` 类中的静态字段。 |
| `out` | 这是 `System` 类中 `PrintStream` 类型的静态字段的名称，包含标准输出功能。 |
| `.` | 这是另一个运算符。该运算符提供了对 `out` 变量中 `println` 方法的访问。 |
| `println` | 这是 `PrintStream` 类中的一个方法的名称。该方法专门将参数的 `println` 内容打印到控制台，并在之后插入换行符。 |
| `(` | 此括号表示正在访问一个方法（而不是字段），并开始传递给 `println` 方法的参数。 |
| `"Hello, World!"` | 这是作为参数传递给 `println` 方法的字符串字面量。两端的双引号 `World!"` 将文本界定为字符串（`String`）。 |
| `)` | 此括号表示传递给 `println` 方法的参数结束。 |
| `;` | 此分号标记了语句的结束。 |

注意：Java 中的每个语句必须以分号（`;`）结束。

随后关闭方法体和类体。

```
// main 函数作用域结束
// HelloWorld 类结束
```

这里这里是另一个演示面向对象（OO）范式的示例。让我们用一个成员（是的，只有一个！）来为足球队建模。成员可以有更多，但我们将讨论如何引入数组。

首先，让我们定义我们的 `Team` 类：

```java
public class Team {
    Member member;
    public Team(Member member) { // 谁在这个 Team 里！
        this.member = member; // 这个 Team 里有一个 'member'！
    }
}
```

现在，让我们定义我们的 `Member` 类：

```java
class Member {
    private String name;
    private String type;
    private int level; // 注意数据类型
    private int rank; // 注意这里的数据类型

    public Member(String name, String type, int level, int rank) {
        this.name = name;
        this.type = type;
        this.level = level;
        this.rank = rank;
    }
}
```



```java
public class Team {
    Member member;
    public Team(Member member) {
        this.member = member;

        // 这里是我们的 main 方法
        public static void main(String[] args) {
            Member myMember = new Member("Auriel", "light", 10, 1);
            Team myTeam = new Team(myMember);
            System.out.println(myTeam.member.getName());
            System.out.println(myTeam.member.getType());
            System.out.println(myTeam.member.getLevel());
            System.out.println(myTeam.member.getRank());
        }
    }
}
```

```java
class Member {
    private String name;
    private String type;
    private int level;
    private int rank;

    public Member(String name, String type, int level, int rank) {
        this.name = name;
        this.type = type;
        this.level = level;
        this.rank = rank;
    }

    /* 让我们在这里定义我们的 getter 函数 */
    String getName() { // 你的名字是什么？
        return this.name; // 我的名字是 ...
    }

    public String getType() { // 你的类型是什么？
        return this.type; // 我的类型是
    }

    public int getLevel() { // 你的等级是多少？
        return this.level; // 我的等级是
    }

    public int getRank() { // 你的排名是多少？
        return this.rank; // 我的排名是
    }
}
```

输出：

`Auriel light`

`10`

`1`

在 ideone 上运行

再次，`Test` 类内部的 `main` 方法是程序的入口。虚拟机（JVM）从这里开始。类名是作为 `java` 命令的参数传递的。

# 第 2 章：类型转换

## 2.1 节：数值转换

数值基本类型可以通过两种方式进行强制转换。隐式转换发生在源类型小于目标类型时。显式转换在源类型大于目标类型时必须执行。

## 2.2 节：基础提升

```java
static void testPromotion() {
    char char1 = 1, char2 = 2;
    short short1 = 1, short2 = 2;
    int int1 = 1, int2 = 2;
    float float1 = 1.0f, float2 = 2.0f;
}
```

## 2.3 节：非数值基本类型转换

`boolean` 类型不能与其他任何类型进行转换。`char` 可以通过 Unicode 指定的代码点映射与任何数值类型进行强制转换。`char` 在内存中表示为无符号 16 位整数值（2 字节），因此强制转换为 `byte`（1 字节）会丢弃其中的 8 位（对于 ASCII 字符是安全的）。`Character` 类的工具方法使用 `int`（4 字节）来与代码点值转换，但使用 `short`（2 字节）就足够存储一个 Unicode 代码点。

## 2.4 节：对象转换

对象既可以显式也可以隐式地进行转换。隐式转换发生在源类型扩展或实现了目标类型时（转换为父类或接口）。显式转换在源类型被目标类型扩展或实现时必须执行（转换为子类型）。当被强制转换的对象不是目标类型（或目标子类型）时，这可能会产生运行时异常（`ClassCastException`）。

```java
//隐式（Float 实现 Number） //显式
//抛出异常（对象不是 Double）
```

## 第 2.5 节：使用 instanceof 测试对象是否可以转换

Java 提供了 `instanceof` 运算符来测试对象是否属于特定类型，或者是该类型的子类。程序可以据此选择对该对象进行转换或转换。

```java
Object obj = Calendar.getInstance();
long time = 0;
if(obj instanceof Calendar)
```

```java
{
time = ((Calendar)obj).getTime();
if(obj instanceof Date)
{
time = ((Date)obj).getTime(); // 这一行永远不会执行，obj 不是 Date 类型。
}
```

# 第 3 章：Getters 和 Setters

本文讨论了 getters 和 setters；这是 Java 类中提供数据访问的标准方法。

## 第 3.1 节：使用 setter 或 getter 实现约束

Setter 和 Getter 允许对象包含私有变量，并在限制下访问和修改这些变量。例如：

```java
public class Person {
private String name;

public String getName() {
return name;
}
```

```java
public void setName(String name) {
if(name!=null && name.length()>2)
  this.name = name;
}

```

在这个 `Person` 类中，有一个变量：`name`。该变量可以通过 `getName()` 方法访问，并通过 `setName(String)` 方法修改，但设置的新名称长度必须大于 2 个字符且不能为空。使用 setter 方法而不是将变量设为 public，可以允许其他人在某些限制下设置 `name` 的值。同样也适用于 getter 方法：

```java
public String getName(){
if(name.length()>16)
  return "Name is too large";
  return name;
}
```

在上述修改后的 `getName()` 方法中，只有当长度小于或等于 16 时才会返回名称。否则，将返回 `"Name is too large"`。这允许程序员按照自己的意愿创建可访问且可修改的变量，防止客户端类意外编辑变量。

## 第 3.2 节：为什么要使用 Getters 和 Setters？

考虑 Java 中一个包含带有 getters 和 setters 对象的基本类：

```java
public class CountHolder {
  private int count = 0;
  public int getCount() { return count; }
  public void setCount(int c) { count = c; }
}
```

我们无法访问 `count` 变量，因为它是私有的。但我们可以访问 `getCount()` 和 `setCount(int)` 方法，因为它们是公共的。对某些人来说，这可能会引发疑问：为什么要引入中间人？为什么不直接

```java
public class CountHolder { public int count = 0; }
```

从功能角度来说，它们是完全相同的。它们之间的区别在于扩展性。考虑每个类表达的意思：

**第一种**：“我有一个方法可以给你一个 **int** 值”

这听起来可能很理想，但第一种本质上实际上好得多；它只允许你按照**它**规定的方式与其内部进行交互。它将控制权留给了自己；由它决定内部交互如何发生。第二种则将其内部实现暴露在外部，现在只容易受到外部用户的影响，但在 API 的情况下，它**被迫**维护该实现（或者发布一个不向后兼容的 API）。

让我们考虑一下如果我们想要同步修改和访问 `count` 的操作。在第一种情况下，这非常简单：

```java
public class CountHolder { private int count = 0;
public synchronized int getCount() { return count; } public synchronized void setCount(int c) { count = c; } }
```

但在第二个例子中，如果不遍历并修改引用 `count` 变量的每一个地方，这几乎是不可能的。更糟糕的是，如果你提供的是一个供他人使用的库项，你**没有**方法来执行该修改，并被迫做出上述的艰难选择。

所以这引出了问题：公共变量真的是一件好事吗（或者至少不是坏事吗）？

我不确定。一方面，你可以看到经受住时间考验的公共变量示例（例如 `System.out` 中引用的 `out` 变量）。另一方面，提供公共变量除了极微的开销减少和可能减少代码冗余外，没有其他益处。我这里的准则是应该是，如果你计划创建一个变量，你应该以极度偏见的态度根据这些标准进行判断：

1. 该变量在实现中不应该有任何可以想象的改变理由。这是非常容易出错的事情（即使你做对了，需求也可能改变），这就是为什么 getters/setters 是常用方法的原因。如果你打算使用公共变量，这真的需要仔细考虑，特别是如果发布在库/框架/API 中。

2. 该变量被引用的频率足够高，以至于减少冗余带来的微小收益值得这样做。我甚至认为，使用方法与直接引用的开销在这里并不应该被考虑。对于我保守估计的 99.9% 的应用程序来说，这太微不足了。

可能还有我随口没想到的。如果你有任何疑问，请始终使用 getters/setters。

## 第 3.3 节：添加 Getters 和 Setters

封装是 OOP 中的基本概念。它是关于将数据和代码封装成单个单元。在这种情况下，它是对对象所在内存引用。当找到对象时，就会调用方法（在本例中为 `toString`）。当引用值为 `null` 时，解引用会导致：

```java
Object obj = null;
obj.toString(); // 执行此语句时抛出 NullPointerException
```

`null` 表示值的缺失，即跟随引用指向了无处。因此没有对象可以调用请求的方法。

源文件 ... 即 `HelloWorld`。如果它们不匹配，你将得到一个编译错误。

1. 字节码文件名 `"HelloWorld.class"` 与类名对应。如果你重命名了 `"HelloWorld.class"`，在尝试运行它时会报错。

2. 使用 `java` 运行 Java 应用程序时，提供的是类名而不是字节码文件名。

## 带包的示例

大多数 Java 代码使用包（packages）来组织类的命名空间，并降低无意类冲突的风险。

如果我们想在名为 `com.example` 的包中声明 `HelloWorld` 类，那么 `"HelloWorld.java"` 将包含以下 Java 源代码：

```java
package com.example;
public class HelloWorld {
    public static void main(String[] args) { System.out.println("Hello world!"); }
}
```

该源文件需要存储在一个在一个结构与包命名相对应的目录树中。

> # 当前目录（此例为例）
>
> ---com
>
> ---example
>
> ---HelloWorld.java

我们可以使用以下命令编译上述文件：

```bash
$ javac com/example/HelloWorld.java
```

这将产生一个名为 `"com/example/HelloWorld.class"` 的文件，即编译后，文件结构应该如下：

> # 当前目录（此例为例）
>
> ---com
>
> ---example
>
> ---HelloWorld.class

我们可以按照如下方式运行应用程序：

```bash
$ java com.example.HelloWorld Hello world!
```

从此示例中需要注意的其他点是：

1. 目录结构必须与包名结构匹配。

2. 当运行类时，必须提供完整的类名；即 `"com.example.HelloWorld"` 而不是 `"HelloWorld"`。

3. 你不需要在当前目录之外编译和运行 Java 代码。

我们在这里这样做仅是为了说明。

## 使用 'javac' 一次编译多个文件

如果你的应用程序由多个源文件组成（大多数情况都是如此），你可以一个一个地编译。或者，你可以通过列出路径名同时编译多个文件：

```bash
$ javac Foo.java Bar.java
```

或使用你命令 shell 的文件名通配符功能 ....

```bash
$ javac *.java
$ javac com/example/*.java
$ javac /**/*.java # 仅在 Zsh 或启用了 globstar 时有效
```

这将分别编译当前目录、`"com/example"` 目录以及子目录中的所有 Java 源文件。

第三种替代方案是提供一个源文件名列表（以及编译器选项）的文件。例如：

```bash
$ javac @sourcefiles
其中 sourcefiles 文件包含：
Foo.java Bar.java com/example/HelloWorld.java
```

注意：像这样编译代码适用于小型单人项目和一次性程序。在此之外，建议选择并使用 Java 构建工具。或者，大多数程序员使用 Java IDE（例如 NetBeans、IntelliJ IDEA），它们提供了嵌入式编译器和“项目”的增量构建功能。

## 常用的 'javac' 选项

以下是 `javac` 命令的几个可能对你有用的选项：

`-d` 选项设置写入 `".class"` 文件的目标目录。

`-sourcepath` 选项设置源码搜索路径。

`-cp` 或 `-classpath` 选项设置查找外部和已编译类的搜索路径。有关 classpath 以及如何指定它的更多信息，请参阅 Classpath 主题。`-version` 选项打印编译器的版本信息。

将在另一个示例中描述更完整的编译器选项列表。

**参考文献** `javac` 命令的权威参考是 Oracle 的 `javac` 手册。

## 第：为不同版本的 Java 编译

Java 编程语言（及其运行时）自首次公开发布以来经历了多次变化。这些变化包括：

- Java 编程语言语法和语义的变化。

- Java 标准类库提供的 API 的变化。

- Java（字节码）指令集和类文件格式的变化。

在极少数例外情况下（对于 `enum` 关键字、某些“内部”类的更改等），这些变化是向后兼容的。

使用旧版本 Java 工具链编译的 Java 程序将可以在较新版本的 Java 平台上运行，而无需重新编译。

用旧版本 Java 编写的 Java 程序将能够使用新版本的 Java 编译器成功完成编译。

## 使用较新版本的编译器编译旧版 Java

如果你需要在新版本的 Java 平台上（重新）编译旧的 Java 代码以便在新平台上运行，通常你不需要提供任何特殊的编译标志。在少数情况下（例如，如果你将 `enum` 作为标识符），你可以使用 `-source` 选项禁用新语法。例如，给定以下类：

```java
public class OldSyntax {
    private static int enum; // 在 Java 5 或更高版本中无效
}
```

使用 Java 5 编译器（或更高版本）编译该类时需要执行以下操作：

```bash
$ javac -source 1.4 OldSyntax.java
```

## 为旧版执行平台编译

如果你需要编译 Java 以运行在较旧的 Java 平台上，最简单的方法是为你需要支持的最旧版本安装 JDK，并在构建中使用 JDK 的编译器。

你也可以使用较新的 Java 编译器进行编译，但存在复杂之处。首先，必须满足一些重要的先决条件：

- 你正在编译的代码不能使用目标 Java 版本中不可用的 Java 语言结构。

- 代码不能依赖于旧平台不可用的标准 Java 类、字段等。

- 代码依赖的第三方库也必须针对旧平台构建，并在编译和运行时可用。

在满足先决条件的情况下，你可以使用 `-target` 选项为旧平台重新编译代码。例如：

```bash
$ javac -target 1.4 SomeClass.java
```

这将编译与 Java 1.4 或更高版本兼容的字节码。（事实上，`-source` 选项隐含兼容的 `target`。）但仍然针对编译器提供的标准库进行编译。解决方案是使用 `-bootstrapclasspath`。例如：

```bash
$ javac -target 1.4 -bootstrapclasspath path/to/java1.4/rt.jar SomeClass.java
```

这将针对替代的运行时库进行编译。如果编译的类对新库有（无意的）依赖，这将导致编译错误。

# 第 6 章：Java 代码文档

Java 代码文档通常使用 `javadoc` 生成。`Javadoc` 是由 Sun Microsystems 创建从从源码生成 HTML 格式的 API 文档。使用 HTML 格式提供了文档间相互链接的便利。

## 第 6.1 节：从命令行构建 Javadocs



许多 IDE 支持自动从 Javadoc 生成 HTML；某些构建工具（例如 Maven 和 Gradle）也有处理 HTML 创建的插件。然而，生成 Javadoc HTML 并不这些工具；可以使用命令行 `javadoc` 工具完成。工具最基本的用法是：

```
javadocFile.java
```

这将根据 `JavaFile.java` 中的 Javadoc 注释生成 HTML。

命令行更实用的用法是，递归读取 `[source-directory]` 中的所有 java 文件，为 `[package.name]` 及其所有子包创建文档，并将生成的 HTML 放在 `[docs-]` 目录：

```bash
javadoc -d [docs-directory] subpackages -sourcepath [source-directory] [package.name]
```

### 第 6.2 节：类文档

所有 Javadoc 注释都以块注释开始，随后跟一个星号（`**`），并在块注释结束时结束（`*`）。可选地，每行可以以任意空格和单个星号开头；在生成文档文件时，这些会被忽略。

```
+   **
* 此类的简要摘要，以句号结束。
*
*   在摘要和更多细节之间留一个空行是常见做法。
*   摘要（第一个句号之前的内容）被用于类或包的概述部分。
*   *可以使用以下内联标签（不是详尽列表）：
    *   使用 {@link some.other.class} 链接到其他文档或符号。
    *   {@link some.other.class} 显示名称，通过在文档后添加显示名称可以自定义链接的外观。
    *   {@code goes here} 将其格式化为代码。
    *   {@literal foo} 用于解释字面量而不将其转换为 HTML。
*   可选地，可以在文档末尾使用以下标签（不是详尽列表）：
    *   @author John Doe
    *   @version 1.0
    *   @since 5.0
    *   @see some.other.class 此类已被 some.other.package 替换。你也可以使用自定义标签来显示额外信息。使用 line 选项，你可以创建一个自定义标签。
    *   示例标签和生成：
    *   @updated 2.0
    *   Javadoc 标记：上述标记将在“Updated in version:”下显示 @updated 的值。
```

```java
public class FileReader {
}
```

用于类的相同标签和格式也可以用于枚举（Enums）和接口（Interfaces）。

## 第 6.3 ：方法文档

所有 Javadoc 注释以块注释开始，后跟一个星号 (`/**`)，并以 (`*`) 结束。可选地，每行可以以任意空格和单个星号开头；这些内容在生成时会被忽略。

```
/**
* 方法的简要摘要，以句号结尾。
* 对方法及其作用的进一步描述，包括尽可能详细的内容。可以使用 {@code here}、{@link some.other.Docs} 和 {@literal text here} 等内联标签。如果方法覆盖了父类方法，可以使用 {@inheritDoc} 从父类方法中复制文档。
* @param stream 描述此参数。尽可能包含详细信息。参数文档通常像这里对齐，但是可选的。与其他文档一样，第一个句号之前的文档被用作摘要。
* @return 描述返回值。尽可能包含详细信息。返回类型文档通常像这里对齐，但是可选的。与其他文档一样，第一个句号之前的文档被用作摘要。
* @throws IOException 描述何时以及为何抛出此异常。异常文档通常像这里对齐，但是可选的。与其他文档一样，第一个句号之前的文档被用作摘要。
* 除了 @throws，也可以使用 @exception。
* @since 2.0
* @see some.other.class.Documentation
* @deprecated 描述此方法已过时。也可以指定一个替代方案。 */
```

```java
public String[] read(InputStream stream) throws IOException {
    return null;
}
```

## 第 6.4 ：包文档

在 Java 中，可以使用名为 `package-info.java` 的文件创建包级文档。该文件必须格式化所示。开头的空格和星号是可选的，通常出于格式原因出现在每行中。

```
/**
* 包文档写在这里；第一个句号之前的任何文档将将用作摘要。
* 在摘要和文档其余部分之间留一个空行是常见做法；使用此空间尽可能详细地描述该包。
* 此文档中可以使用 {@code here}、{@link reference.to.other.Documentation} 和 {@literal text here} 等内联标签。
*/
```

```java
package com.example.foo;
```

// 文件的其余部分必须为空。在上述情况下，你必须将此文件 `package-info.java` 放在 Java 包 `com.example.foo` 的文件夹内。

## 第 6.5 ：链接

链接到其他 Javadocs 使用 `@link` 标签：

```java
/**
* 你可以使用 {@link ClassName} 链接到已导入类的 javadoc。
* 如果类尚未导入，你也可以使用全限定名：{@link some.other.ClassName}
* 你可以像这样链接到类的成员（字段或方法）：
* {@link ClassName#someMethod()}
* {@link ClassName#someMethodWithParameters(int, String)}
* {@link ClassName#someField}
* {@link #someMethodInThisClass()} - 用于链接到当前类中的成员
* 你可以这样为链接的 javadoc 添加标签：
* {@link ClassName#someMethod(link)} 文本
*/
```

| 描述 |
| :--- |
| 你可以使用 `ClassName` 链接到已导入类的 javadoc。 |
| 如果类尚未导入，你也可以使用全限定名：`some.other.ClassName` |
| 你可以像这样链接到类的成员（字段或方法）： |
| `ClassName.someMethod()`<br>`ClassName.someMethodWithParameters(int, String)`<br>`ClassName.someField`<br>`someMethodInThisClass()` - 用于链接到当前类中的成员 |
| 你可以这样为链接的 javadoc 添加标签：`link text` |

通过 `@see` 标签，你可以向“See also”（另参）部分添加元素。像 `@param` 和 `@return` 一样，它们出现的位置并不重要。规范说你应该在 `@return` 之后编写它。

```java
/**
* 方法的简要摘要，以句号结尾。
* 对方法及其作用的进一步描述，包括尽可能详细的内容。可以使用 {@code here}、{@link some.other.Docs} 和 {@literal text here} 等内联标签。
* 如果方法覆盖了父类方法，可以使用 {@inheritDoc} 从父类方法中复制文档。
* @see some.other.class
*/
```

```
/**
* 方法的简要摘要，以句号结尾。
* 对方法及其作用的进一步描述，包括尽可能详细的内容。可以使用 {@code here}、{@link some.other.Docs} 和 {@literal text here} 等内联标签。
*/
```

```
/**
* 方法的简要摘要，以句号结尾。
* 对方法及其作用的进一步描述，包括尽可能详细的内容。可以使用 {@code here}、{@link some.other.Docs} 和 {@literal text here} 等内联标签。
* 如果方法覆盖了父类方法，可以使用 {@inheritDoc} 从父类方法中复制文档。
* @see some.other.class
*/
```

```
/**
* 方法的简要摘要，以句号结尾。
* 对方法及其作用的进一步描述，包括尽可能详细的内容。可以使用 {@code here}、{@link some.other.Docs} 和 {@literal text here} 等内联标签。
* 如果方法覆盖了父类方法，可以使用 {@inheritDoc} 从父类方法中复制文档。
* @see some.other.class
*/
```

```
/**
* 方法的简要摘要，以句号结尾。
* 对方法及其作用的进一步描述，包括尽可能详细的内容。可以使用 {@code here}、{@link some.other.Docs} 和 {@literal text here} 等内联标签。
* 如果方法覆盖了父类方法，可以使用 {@inheritDoc} 从父类方法中复制文档。
* @see some.other.class
*/
```

## 第 6.6 ：内联代码文档

除了 Javadoc 代码外，还可以对代码进行内联文档。单行注释以 `//` 开头，可以放置在同一行内语句之后，但不能放在之前。

```java
public void method() {
//单行注释
someMethodCall(); // 语句后的单行注释
}
```

多行注释定义在 `/*` 和 `*/` 之间。它们可以跨越多个行，甚至可以放置在语句之间。

```java
public void method(Object object) {
/*
多
行
注释
*/
object/*内联行注释*/.method();
}
```

由于过多的内联注释可能会降低代码的可读性，因此应谨慎使用，除非代码本身不够自解释或者设计决策并不显而易见。

单行注释的另一个用例是使用 TAG，它们是短的、约定驱动的关键字。某些开发环境可以识别此类单行注释的特定约定。常见的示例有：

```
//TODO //FIXME
```

或者问题引用，例如 Jira 的 `//PRJ-1234`

# 第 7 章：命令行参数处理

## 参数详情

### args

命令行参数。假设主方法由 Java 启动器调用，`args` 将不为空，且不会包含空元素。

## 第 7.1 节：使用 GWT ToolBase 处理参数参数

如果你想解析复杂的命令行参数（例如带有可选参数），最佳方法是使用 Google 的 GWT 方法。所有类均可在以下地址找到：https://gwt.googlesource.com/gwt/+2.8.0-beta1/dev/core/src/com/google/gwt/util/ToolBase.java

处理命令行 `myprogram -dir "~/Documents" port 8888` 的示例：

```java
public class MyProgramHandler extends ToolBase {
protected File dir;
protected int port;
// 获取 dir 和 port 的 getter
...
```

```java
public class MyProgramHandler() {
this.registerHandler(new ArgHandlerDir()) {
@Override
public void setDir(File dir) {
```

```java
this.dir = dir;
}
));
this.registerHandler(new ArgHandlerInt() {
@Override
public String[] getTagArgs() {
    return new String[]{"port"};
}
@Override
public void setInt(int value) {
    this.port = value;
}
});
```

```java
public static void main(String[] args) {
MyProgramHandler myShell = new MyProgramHandler();
if (myShell.processArgs(args)) {
// 主程序操作
    System.out.println(String.format("port: %d; dir: %s", myShell.getPort(), myShell.getDir()));
}
System.exit(1);
}
```

`ArgHandler` 还具有一个 `isRequired()` 方法，可以通过重写它来指定命令行参数是必须的（默认返回 `false`），这样该参数就是可选的。

## 第 7.2 节：手动处理参数

当应用程序的命令行语法简单时，完全在自定义代码中进行命令行参数处理是合理的。

在这个示例中，我们将展示一系列简单的案例研究。在每个用例中，如果参数不可接受，代码将产生错误消息，然后调用 `System.exit(1)` 告诉 shell 命令执行失败。（我们假设在每个案例中，Java 代码都是通过一个名为 "myapp" 的包装器调用的。）

### 无参数的命令

在这个案例研究中，该命令不需要参数。代码说明了 `args.length` 提供了命令行参数的数量。

```java
public class Main {
public static void main(String[] args) { if (args.length > 0) {
System.err.println("usage: myapp"); System.exit(1);
}
// 运行应用程序
System.out.println("It worked"); }
}
```

### 带有两个参数的命令

在这个案例研究中，命令恰好需要两个参数。

```java
public class Main {
public static void main(String[] args) {
if (args.length != 2) {
System.err.println("usage: myapp <arg1> <arg2>"); System.exit(1);
}
// 运行应用程序
System.out.println("It worked: " + args[0] + " , " + args[1]);
}
```

注意，如果我们忽略了检查 `args.length`，当用户运行时命令行参数太少时，命令将会崩溃。

### 带有 "flag" 选项和至少一个参数的命令

在这个案例研究中，命令有几个（可选的）标记选项，并且选项之后至少需要一个参数。

```java
package tommy;

public class Main {
public static void main(String[] args) {
```

```java
boolean feelMe = false;
boolean seeMe = false;
int index;
loop: for (index = 0; index < args.length; index++) {
String opt = args[index];
switch (opt) {
  case "c":
    seeMe = true;
    break;
  case "f":
    feelMe = true;
    break;
  default:
    if (!opt.isEmpty() && opt.charAt(0) == '-') {
      error("Unknown option: ' + opt + "'");
    }
    break;
  }
}
if (index >= args.length) {
  error("Missing argument(s)");
}
// 运行应用程序
private static void error(String message) {
  if (message != null) {
    System.err.println(message);
  }
  System.exit(1);
}
```



由于内联注释应谨慎使用，除非代码本身不够自解释或者设计决策并不显而易见。

这个问题发生在`java`命令能够找到并加载你指定的类，但随后无法找到入口方法（entry-point method）时。有三种可能的解释：

- 如果你尝试运行一个可执行的 JAR 文件，那么 JAR 的清单文件（manifest）中有一个错误的`"Main-Class"`属性，该属性指定的类不是有效的入口点类。
- 你告诉`java`命令的类不是入口点类。入口点类错误的；更多信息请参见“入口点类（Entry point classes）”。

## 其他资源

“Could not find or load main class”意味着什么？
http://docs.oracle.com/javaves/tutorial/getStarted/problems/index.html

## 第 8.3 节：运行带有库依赖的 Java 应用程序

这是“主类”和“可执行 JAR”示例的延续。

典型的 Java 应用程序由特定应用程序代码以及你实现或由第三方实现的各种库代码组成。后者通常被称为库依赖，它们通常被打包成 JAR 文件。

Java 是一种动态绑定的语言。当你运行一个带有库依赖的 Java 应用程序时，JVM 需要知道依赖项的位置，以便根据需要加载类。广义上，处理此问题有两种方法：

- 将应用程序及其依赖项重新打包成一个单一的 JAR 文件，其中包含所需的类和资源。
- 通过运行时类路径（runtime classpath）告诉 JVM 在哪里查找依赖 JAR 文件。

对于可执行的 JAR 文件，运行时类路径由清单中的`"ClassPath"`属性指定。否则，需要使用`-cp`选项或使用`CLASSPATH`环境变量来提供运行时类路径。

例如，假设我们在`"my.App"`文件中有一个 Java 应用程序，其入口点类为`com.example.MyApp`。假设该应用程序依赖于库 JAR 文件`"lib/library1.jar"`和`"lib/library2.jar"`。我们可以在命令行中使用`java`命令如下启动应用程序：

```
$ 方案 1（推荐）
$ java -cp myApp.jar:lib/library1.jar:lib/library2.jar com.example.MyApp

$ 方案 2
$ export CLASSPATH=myApp.jar:lib/library1.jar:lib/library2.jar
$ java com.example.MyApp
```

（在 Windows 上，你会使用`;`代替`:`作为分隔符，并使用`set`而不是`=`来设置（本地）`CLASSPATH`变量。）

虽然 Java 开发者习惯这样做，但这并不“用户友好”。因此，通常会编写一个简单的 shell 脚本（或 Windows 批处理文件）来隐藏用户不需要细节。例如，如果你将以下脚本放入名为`"myApp"`的文件中，赋予其执行权限，并将其放入命令搜索路径目录中：

```bash
#!/bin/bash

# 'myApp' 封装脚本

export DIR=/usr/libexec/myApp

export CLASSPATH=$DIR/myApp.jar:$DIR/lib/library1.jar:$DIR/lib/library2.jar

java com.example.MyApp
```

然后你就可以这样运行它：
```
$ myApp arg1 arg2 ...
```
命令行上的任何参数都将通过`"$@"`扩展传递给 Java 应用程序。（你可以在 Windows 批文件中实现类似的操作，尽管语法不同。）

## 第 8.4 节：Java 选项

`java`命令支持广泛选项：
- 所有选项都以单个连字符或减号（`-`）开头：不支持使用`-"long"`选项的 GNU/Linux 习惯。选项必须出现在`<classname>`或`-jar <jarfile>`参数之前才能被识别。在它们之后的任何参数都将被视为传递给正在运行的 Java 的参数。
- 不以`-X`或`-XX`开头的选项是标准选项。你可以依赖所有 Java 实现都支持任何标准选项。
- 以`-X`开头的选项是非标准选项，可能会从一个 Java 版本取消到下一个。
- 以`-XX`开头的选项是高级选项，也可能被取消。

### 使用 -D 设置系统属性

`-D<property>=<value>`选项用于在系统属性对象中设置属性。可以重复此参数来设置不同的属性。

### 内存、栈和垃圾回收器选项

控制堆和栈的主要选项是控制堆和栈的主要选项。

### 启用和禁用断言

控制堆和栈的主要选项是控制堆和栈的主要选项。

### 选择 VM 类型

`-client`和`-server`选项允许你在不同的形式之间进行选择。“client”形式针对快速启动进行了优化。“server”形式针对长时间运行的应用程序进行了优化。

## 第 8.5 节：参数中的空格和其他字符

首先，处理参数中空格的问题实际上不是 Java 问题。相反，这是一个需要由运行 Java 程序时所使用的命令行 shell 来处理的问题。例如，假设我们有以下简单的程序来打印文件的大小：

```java
import java.io.File;

class PrintFileSizes {

    public static void main(String[] args) {

        for (String name : args) {

            File file = new File(name);

            System.out.println("Size of " + file + " is " + file.size());

        }

    }

}
```

现在假设我们要打印一个路径中包含空格的文件的大小；例如`/home/steve/Test.txt`。如果我们这样运行命令：`$ java PrintFileSizes /home/steve/Test.txt`

shell 将不知道`/home/steve/Test.txt`实际上是一个路径。相反，它将向 Java 应用程序传递 2 个独立的参数，程序将尝试查找各自的文件大小，并由于这些路径（可能）不存在而失败。

### 使用 POSIX shell 的解决方案

POSIX shell 包括`sh`以及类似的`bash`和`ksh`。如果你使用这些 shell 之一，可以通过引用参数来解决问题。
```
$ java PrintFileSizes "home/steve/Test File.txt"
```
路径周围的双引号告诉 shell 应该将其作为单个参数传递。当这种情况发生时，引号会被移除。还有其他方法可以实现：

```
$ java PrintFileSizes '/home/steve/Test File.txt'
```
单引号（直引号）的处理方式与双引号类似，但还会抑制参数中的各种扩展。
```
$ java PrintFileSizes /home/steve/Test\ File.txt
```
反斜杠转义了随后的空格，使其不被解释作为参数分隔符。

如需更全面的文档，包括关于如何处理参数中其他特殊字符的说明，请参考 Bash 文档中的引用（quoting）主题。

### Windows 解决方案

Windows 的根本问题在于，在操作系统层面，传递给子进程的参数是以单个字符串（源）的形式。这意味着解析（或重新解析）命令行的最终责任落在程序或其运行时库上。这其中存在许多不一致之处。

在 Java 的情况下，简短而言之：
你可以在`java`命令中给参数两边加上双引号，这将允许你传递带有空格的参数。显然，`java`命令本身正在解析命令字符串，而且它处理得基本正确。

然而，当你尝试将此与批处理文件中的`SET`和变量替换结合使用时，双引号是否会被移除这个问题就变得非常复杂。`cmd.exe`shell 显然有其他的转义机制；例如，双写双引号以及使用`^`转义字符。

更多细节，请参考批处理文件（Batch-File）文档。

## 第 8.6 节：运行可执行的 JAR 文件

可执行 JAR 文件是将 Java 代码汇成单个可执行文件的最简单方法。假设你有一个路径为`<jar-path>`的可执行 JAR 文件，你应该能够如下运行它：
```
java -jar <jar-path>
```

如果命令需要命令行参数，请将它们添加到`<jar-path>`之后。例如：
```
java -jar <jar-path> arg1 arg2 arg3
```

如果你需要在`java`命令上提供额外的 JVM 选项，它们需要放在`-jar`选项之前。注意，如果使用`-jar`，`-cp` / `-classpath`选项将被忽略。应用程序的类路径是由 JAR 文件的清单（manifest）指定的。

## 第 8.7 节：通过“main”类运行 Java 应用程序

当应用程序没有被打包成可执行 JAR 时，你需要在`java`命令行上提供入口类的名称。

### 运行 HelloWorld 类

“HelloWorld”示例在“创建新的 Java 程序”中有所描述。它由一个名为`HelloWorld`的单类组成，该类满足入口的要求。

假设（编译后的）`"HelloWorld.class"`文件在当前目录下，可以如下启动：

```
java HelloWorld
```

需要注意的一些重要点：

- 我们必须提供类名：而不是`".class"`文件或`".java"`文件的路径。如果类声明在包中（绝大多数 Java 类都是如此），那么我们提供给`java`命令的类名必须是全名（fullname）。例如，如果`SomeClass`声明在`com.example`包中，那么全名将是`com.example.SomeClass`。

### 指定类路径

除非我们使用`java -jar`命令语法，否则`java`命令会通过搜索类路径来查找要加载的类；参见“上述命令依赖于默认类路径（或包含）当前目录”。我们可以通过使用`-cp`选项指定要使用的类路径来使这一点更加明确。

```
java -cp . HelloWorld
```

这表示将当前目录（用`.`表示）作为类路径上的唯一条目。`-cp`是由`java`命令处理的选项。所有用于`java`命令的选项都应该放在类名之前。类之后的任何内容都将被视为 Java 应用程序的命令行参数，并通过传递给`main`方法的`String[]`传递给应用程序。

（如果没有提供`-cp`选项，java 将使用由`CLASSPATH`环境变量提供的类路径。如果该变量未设置或为空，java 使用`.`作为默认类路径。）

## 第 9 章：字面量

字面量（Literal）是一种表示值的句法元素（即你在 Java 程序的源代码中找到的内容）。示例有`1`、`0.333F`、`false`、`'X'`和`"Hello world"`。

## 第 9.1 节：使用下划线提高可读性

从 Java 7 开始，已经可以使用一个或多个下划线（`_`）分隔原始类型数字字面量中的数字组，以提高它们的可读性。例如，这两个声明是等价的：

```
Version ≥ Java SE 7

int i1 = 123456;

int i2 = 123_456;

System.out.println(i1 == i2); // true
```

这可以应用于所有原始类型数字字面量，如下所示：

```
Version ≥ Java SE 7

byte color = 1_2_3;

short yearsAnnoDomini = 2_016;

int securityNumber = 999_99_9999;
long creditCardNumber = 1234_5678_9012_3456L;
float piFourDecimals = 3.14_15F;

double piDecimals = 3.14_15_92_65;
```

这在使用二进制、八进制和十六进制基数的缀时同样有效：

```
Version ≥ Java SE 7

short binary = 0b0_1_0_1;
```

```
int octal = 07_7_7_7_7_7_7_0;
long hexBytes = 0FF_EC_DE_5E;
```

关于下划线有几条规则禁止将其放置在以下位置：

- 数字的开头或结尾（例如，`_123`或`123_`都是无效的）
- 紧邻小数点（在浮点数字面量中，例如`1._23`或`.123_`是无效的）
- 在`L`后缀之前（例如，`123_L`或`999_L`是无效的）
- 在期望数字字符串的位置（例如，`0x_23`是无效的）

## 第 9.2 节：十六进制、八进制和二进制字面量

十六进制是 16 的值，使用 0-9 和字母 A-F（不区分大小）。
八进制字面量是 8进制的值，使用数字 0-7。
二进制字面量是 2 的值，使用数字 0 和 1。
以下数字得到相同的值：

```
int dec = 110; // 无前缀十进制

int bin = 0b110; // '0b' 前缀二进制

int oct = 0110; // '0' 前缀八进制

int hex = 0x6E; // '0x' 前缀十六进制
```

注意二进制语法是在 Java 7 中引入的。八进制字面量可能是陷阱。如果你在十进制字面量前加上`0`，将得到错误的值：
```
int a = 0100; // 不是 100，而是 64
```

## 第 9.3 节：布尔字面量

布尔字面量是语言中最简单的字面量。两个可能的布尔值由字面量`true`和`false`表示。这些是大小敏感的。例如：
```
boolean flag = true; // 使用 'true' 字面量
flag = false; // 使用 'false' 字面量
```

## 第 9.4 节：字符串字面量

字符串字面量提供了 Java 源码中表示字符串值的方便方法。字符串字面量由：

- 一个起始双引号（`"`）。
- 多个其他不是双引号或换行行的字符。（反斜杠`\`字符改变后续字符的含义；见字面量中的转义序列。）
- 一个结束双引号。

例如：

```
"Hello world"
""
"1\t2\3\n"
```

```
// 表示空字符字符串的字面量
// 表示空（零长度）字符串
// 表示由单个引号字符组成的字符串
// 另一个带有转义序列的字面量
```

注意，单个字符串字面量不能跨越多个源码行。如果在字面量的结束双引号之前出现换行（或源文件结束），将导致编译错误。例如：

```
"Hello // 编译错误（在行尾！）
```

### 长字符串

如果你需要一个无法放入单行的字符串，习惯的表示方法是将其拆分为多个字面量并使用拼接运算符（`+`）将它们连接。

```
String typingPractice = "The quick brown fox " + "jumped over " + "the lazy dog"
```

像上面那样由字符串字面量和`+`组成的表达式满足常量表达式的要求。这意味着该表达式将由编译器求值，并在运行时由单个`String`对象表示。

### 字符串字面量的池化

当 JVM 加载包含字符串字面量的类文件时，相应的`String`对象会被运行时系统进行池化（interned）。这意味着在多个类中使用的字符串字面量所占的空间并不比在一个类中使用它的大。

有关池化和字符串池的更多信息，请参考 Strings 主题中的字符串池和堆存储示例。

## 第 9.5 节：Null 字面量

Null 字面量（写为`null`）代表 null 类型的唯一值。这里是一些示例：

```java
MyClass object = null;

MyClass[] objects = new MyClass[]{new MyClass(), null, new MyClass()};

myMethod(null);
```

```java
if (objects != null) {

  // 执行某些操作

}
```



`null` 类型相当特殊。它没有名称，因此你无法在 Java 源代码中表示它。（而且它也没有运行时表示形式。）

`null` 类型的目的是作为 `null` 的类型。它与所有引用类型兼容赋值，并且可以强制转换为任何引用类型。（在后一种情况下，转换不涉及运行时类型检查。）

最后，`null` 有一个属性：无论类型是什么，`null instanceof<SomeReferenceType>` 的结果始终为 `false`。

## 第 9.6 节：字面量中的转义序列

字符串和字符字面量提供了一种转义机制，允许在字面量中使用原本不允许的字符代码。一个转义序列由一个反斜杠字符（`\`）后跟一个或多个字符组成。相同的序列在字符和字符串字面量中都是有效的。

转义序列的完整集合如下：

| 转义序列 | 含义 |
| :--- | :--- |
| `\\` | 表示反斜杠 (`\`) 字符 |
| `\'` | 表示单引号 (`'`) 字符 |
| `\"` | 表示双引号 (`"`) 字符 |
| `\n` | 表示换行符 (LF) |
| `\r` | 表示回车符 (CR) |
| `\t` | 表示制表符 (HT) |
| `\f` | 表示分页符 (FF) |
| `\b` | 表示退格符 (BS) |
| `\<octal>` | 表示 0 到 255 范围内的字符代码。 |

上述 `<octal>` 由一、二或三个八位数字（`'0'` 到 `'7'`）组成，表示 0 到 255（十进制）之间的数字。

注意，反斜杠后跟任何其他字符都是无效的转义序列。JLS 将无效的转义序列视为编译错误。

参考：JLS 3.10.6. 字符和字符串字面量的转义序列

### Unicode 转义

除了上述的字符串和字符转义序列外，Java 还有一种更通用的 Unicode 转义机制，如 JLS 3.3 节“Unicode 转义”中所定义。

Unicode 转义具有以下语法：
`'u' <hex-digit><hex-digit><hex-digit><hex-digit>`

其中 `<hex-digit>` 是 `'0'`, `'1'`, `'2'`, `'3'`, `'4'`, `'5'`, `'6'`, `'7'`, `'8'`, `'9'`, `'a'`, `'b'`, `'c'`, `'d'`, `'e'`, `'f'`, `'A'`, `'B'`, `'C'`, `'D'`, `'E'`, `'F'` 之一。

Unicode 转义由 Java 编译器映射为一个字符（严格来说是一个 16 位的 Unicode 代码单元），它可以用于源代码中任何映射字符有效的地方。当需要在字面量中表示非 ASCII 字符时，通常用于字符和字符串字面量。

### 正则表达式中的转义（待定）

## 第 9.7 节：字符字面量

字符字面量提供了在 Java 源代码中表示 `char` 值的最方便的方法。字符字面量由：

- 一个开启的单引号字符（`'`）。
- 字符的表示。此表示可以是单引号或换行符，但可以是由反斜杠字符（`\`）引入的转义序列；字面量中的转义序列。
- 一个闭合的单引号字符（`'`）。

例如：

```java
char a = 'a';
char doubleQuote = '"';
char singleQuote = '\'';
```

字符字面量中的换行是编译错误：

```java
char newline = '\'
// 上行编译错误

char newLine = '\n'; // 正确
```

## 第 9.8 节：十进制整数字面量

整数字面量提供的值可以使用任何需要 `byte`、`short`、`int`、`long` 或 `char` 实例的地方。（此示例重点关注简单的十进制形式。其他示例解释了八进制、十六进制和二进制字面量以及使用下划线提高可读性。）

### 普通整数字面量

最简单最常见的整数字面量形式是十进制整数字面量。例如：

```java
0 // 十进制零（类型为 'int'）
1 // 十进制一（类型 'int'）
42 // 十进制四十二（类型 'int'）
```

你需要注意前导零。前导零会导致整数字面量被解释为八进制而非十进制。

```java
077 // 此字面量实际上意味着 7 x 8 + 7 ... 或者十进制 63！
```

整数字面量是无符号的。如果你看到类似 `-10` 或 `+10` 的内容，这些实际上是使用一元 `-` 和一元 `+` 运算符的表达式。

这种形式的整数字面量的范围在类型为 `int`，且必须落在 0 到 $2^{31}$（即 2,147,483,648）的范围内。

注意 $2^{31}$ 比 `Integer.MAX_VALUE` 大 1。从 0 到 2147483647 的字面量可以用于任何地方，但在没有前置一元 `-` 运算符的情况下使用 2147483648 是编译错误。（换句话说，它留用于表示 `Integer.MIN_VALUE` 的值）。

```java
int max = 2147483647; // OK
int min = -2147483648; // OK
int tooBig = 2147483648; // ERROR
```

### 长整型字面量

类型为 `long` 的字面量通过添加 `L` 后缀来表示。例如：

```java
0L // 十进制（类型为 'long'）
1L // 十进制一（类型 'long'）
2147483648L // Integer.MAX_VALUE + 1 的值
```

```java
long big = 2147483648; // ERROR
long big2 = 2147483648L; // OK
```

注意 `int` 和 `long` 字面量之间的区别在其他地方是重要的。例如：

```java
int i = 2147483648; // ERROR
long j = 2147483648L; // OK
```

## 第 9.9 节：浮点字面量

浮点字面量提供的值可以使用任何需要 `float` 或 `double` 的地方。（此示例关注简单的十进制形式。其他示例解释了八进制、十六进制和二进制以及使用下划线提高可读性。）

### 简单十进制形式

最简单最常见的浮点字面量形式是小数字面量。例如：

```java
3.14 // double
3.14f // float
```

你需要注意前导零。前导零会导致整数字面量被解释为八进制而非十进制。

```java
0.5 // double
0.5f // float
```

### 科学计数十进制形式

科学计数十进制形式由带有 `E` 或 `e` 引入的指数部分的简单十进制组成，后面跟着一个带符号的整数。指数表示十的幂次，如下所示。还有一个可选的后缀来区分 `float`。这里是一些示例：

```java
1.0E1 // 表示 1.0 x 10^1 ... 或者 10.0 (double)
1E-1 // 表示 1.0 x 10^(-1) ... 或者 0.1 (double)
1.0e10f // 表示 1.0 x 10^10 ... 或者 10000000000.0 (float)
```

### 十六进制形式

从 Java 6 开始，可以使用十六进制表示浮点字面量。十六进制形式的语法与简单和科学计数形式类似，有以下不同点：

1. 每个十六进制浮点字面量都以零（`0`）开头并跟一个 `X`。
2. 数字的数字（但不包括指数部分！）还包括十六进制数字 `f` 及其大写形式。
3. 指数是强制性的，并用字母 `p`（或 `P`）代替 `e` 或 `E` 引入。指数表示 2 的幂次而非 10 的幂次。

这里是一些示例：

```java
0x0pf // 以十六进制形式表示（'float'）
0xff.p19 // 255.0 x 2^19 ('double')
```

> 建议：由于十六进制浮点形式对大多数 Java 程序员来说并不熟悉，建议谨慎使用。

### 下划线

从 Java 7 开始，在所有形式的浮点字面量的数字字符串中都允许使用下划线。这也适用于“指数”部分。使用下划线提高可读性。

### 特殊情况

如果浮点字面量表示数字太大，则是一个编译错误。太大或太小，无法表示所选的表示；例如，如果数值将溢出到 `+INF` 或 `-INF`，或者下溢到 `0.0`。然而，字面量表示非零的渐规数是合法的。

浮点数语法没有提供 IEEE 754 特殊值（如 `INF` 和 `NaN` 值）的字面量表示。如果你需要在源代码中表示它们，推荐的方法是使用 `java.lang.Float` 和 `java.lang.Double` 定义的常量；例如：`Float.NaN`、`Float.NEGATIVE_INFINITY` 和 `Float.POSITIVE_INFINITY`。

# 第 10 章：原始数据类型

8 种原始数据类型 `byte`、`short`、`int`、`long`、`char`、`boolean`、`float` 和 `double` 是 Java 程序中存储大多数原始数值数据的类型。

# 第 10.1 节：char 原始类型

`char` 可以存储单个 16 位的 Unicode 字符。字符字面量包含在单引号中。

```java
char myChar = 'u';
char myChar2 = '5';
char myChar3 = 65; // myChar3 == 'A'
```

它的最小值为 `\u0000`（十进制表示为 0，也称为空字符），最大值为 `\uFFFF`（65,535）。

`char` 的默认值为 `\u0000`。

为了定义一个 `char` 值，必须使用转义序列（以反斜杠开头的字符）：还有其他转义序列：

```java
char tab = '\t';
char backspace = '\b';
char newline = '\n';
char carriageReturn = '\r';
char formfeed = '\f';
char singleQuote = '\''; // 在这里转义是多余的：'" 效果是一样的；
char doubleQuote = '"'; // 然而允许的字符
char backslash = '\\';
char unicodeChar = '\uXXXX' // XXXX 代表你想要显示的字符的 Unicode 值
```

你可以声明任何 Unicode 字符的 `char`。

```java
char heart = '\u2764';
System.out.println(Character.toString(heart)); // 打印包含 "❤" 的行
```

也可以对 `char` 进行加法。为了遍历每一个小写字母，你可以对以下代码进行操作：

```java
for (int i = 0; i <= 26; i++) {
    char letter = (char) ('a' + i);
    System.out.println(letter);
}
```

# 第 10.2 节：原始类型快速查表

显示所有原始类型的大小和值范围的表格：

| 数据类型 | 数值表示 | 取值范围 | 默认值 |
| :--- | :--- | :--- | :--- |
| `boolean` | 无/A | `false` 和 `true` | `false` |
| `byte` | 8 位符号型 | -128 到 +127 | 0 |
| `short` | 16 位符号型 | -32,768 到 +32,767 | 0 |
| `int` | 32 位符号型 | -2,147,483,648 到 +2,147,483,647 | 0 |
| `long` | 64 位符号型 | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 | 0L |
| `float` | 32 位浮点型 | 1.401298464e-45 到 3.40823466e+38 | 0.0F |
| `double` | 64 位浮点型 | -4.9406564584126544e-308 到 1.7976931348623157e+308 | 0.0 |
| `char` | 16 位无符号 | 0 到 65,535 | `\u0000` |
| `boolean` | 无/A | `false` 和 `true` | `false` |

注：

1. `float` 和 `double` 类型使用 IEEE 754 标准表示。
2. `byte`、`short`、`int` 和 `long` 使用补码表示。
3. `float` 精度比 `double` 低。
4. `char` 惯例上表示一个 UTF-16 编码单元。
5. `boolean` 包含一个位的信息，其内存大小取决于 Java 机的实现。

# 第 10.3 节：float 原始类型

`float` 是单精度 32 位 IEEE 754 浮点数。默认情况下，小数被解释为 `double`。要创建一个 `float`，只需在小数字面量后加上 `f`。

```java
double doubleExample = 0.5;
float floatExample = 0.5f;
// 不加 'f' 是 double; 加上 'f' 是 float;
```

```java
float myFloat = 92.7f;
float positiveFloat = 89.3f;
float negativeFloat = -89.3f;
float integerFloat = 43.0f;
// 这是一个 float...
// 它可以是正数
// 也可以负数
// 也可以是整数（不是 int）
```

`float` 处理五种常见的运算：加法、减法、乘法、除法和取模。注意：以下结果可能由于浮点误差略有不同。某些结果为了清晰易读进行了舍入（例如，加法示例的打印结果实际上是 34.600002）。

```java
// 加法
float result = 37.2f + 2.6f; // 结果为 34.6
```

```java
// 减法
float result = 45.1f - 10.3f;
```

```java
// 乘法
float result = 37.2f * 2.6f; // 结果为 96.7
```

```java
// 除法
float result = 45.1f / 10.3f; // 结果为 4.37
```

```java
// 取模
float result = 45.1f % 10.3f; // 结果为 3.9
```

## 第 10.6 节：基本类型与包装基本类型的内存消耗

| 原始类型 | 包装类型 | 原始类型/包装类型的内存大小 |
| :--- | :--- | :--- |
| `boolean` | `Boolean` | 1 字节 / 16 字节 |
| `byte` | `Byte` | 1 字节 / 16 字节 |
| `short` | `Short` | 2 字节 / 16 字节 |
| `char` | `Char` | 2 字节 / 16 字节 |
| `int` | `Integer` | 4 字节 / 16 字节 |
| `long` | `Long` | 8 字节 / 16 字节 |
| `float` | `Float` | 4 字节 / 16 字节 |
| `double` | `Double` | 8 字节 / 16 字节 |

包装对象始终需要 8 字节用于类型和内存管理，因为对象的大小始终是 8 的倍数，每个包装类型的使用都涉及存储一个引用，根据 JVM 和 JVM 选项，这额外需要 4 或 8 字节。

在数据密集型操作中，内存消耗会对性能产生巨大影响。即使在使用数组时内存消耗也会增长：一个 `float[5]` 数组只需要 32 字节；而存储 5 个不同非空值的 `Float[5]` 总共需要 112 字节（在 64 位且未使用压缩指针的情况下，这会增加到 152 字节）。

## 包装值缓存

包装值缓存可以在一定程度上缓解包装类型的空间开销。某些包装类型实现了实例缓存。例如，默认情况下，`Integer` 类会缓存表示 -128 到 +127 范围内数字的实例。然而，这并没有减少额外的内存间接带来的额外成本。

如果你通过自动装箱或调用静态的 `valueOf(primitive)` 方法创建包装类型的实例，运行时系统将尝试使用缓存值。如果你的应用程序使用了大量缓存范围内的值，那么可以大幅减少使用包装类型的内存惩罚。

当然，如果你是“手动”创建包装值实例，使用 `valueOf` 而不是 `new` 更好（`new` 操作总是创建一个新实例）。但是，如果你的大部分值*不在*缓存范围内，那么调用 `new` 并节省缓存查找可能会更快。

## 第 10.7 节：double 基本类型

`double` 是一个双精度 64 位的 IEEE 754 浮点数。

```java
double example = 7162.37;
double myDouble = 974.21;
double anotherDouble = 658.37;
```

```java
double addedDoubles = myDouble + anotherDouble; // 1632.58
double subtractedDoubles = myDouble - anotherDouble; // 315.84
double scientificNotation = 1.2e-3; // 0.0012
```

由于浮点数的存储方式，许多数字没有精确的表示。

```java
double notExact = 1.32 - 0.42; // 结果应为 0.9
System.out.println(notExact); // 0.900000000000001
```

虽然使用 `double` 对于大多数应用是可以接受的，但不应使用 `float` 或 `double` 来存储如货币之类的精确数字。相反，应该使用 `BigDecimal` 类。

`double` 的默认值为 0.0d。

```java
public double defaultDouble; // defaultDouble == 0.0d
```



> 注意：`Double.POSITIVE_INFINITY`、`Double.NEGATIVE_INFINITY`、`Double.NaN` 是 `double` 值。`NaN` 代表无法确定的操作结果，例如除以两个无限值。此外，`0d` 和 `-0d` 是不同的，但 `==` 产生的结果为 `true`：

```java
double d1 = 0d;
double d2 = 0d;
System.out.println(d1 == d2); // true
System.out.println(1d / d1); // Infinity
System.out.println(1d / d2); // -Infinity
System.out.println(Double.POSITIVE_INFINITY / Double.POSITIVE_INFINITY); // NaN
```

## 第 10.8 节：long 基本类型

默认情况下，`long` 是一个 64 位有符号整数（在 Java 8 中，它是有符号或无符号的）。有符号的话，它可以存储最小值 `-2^63` 和最大值 `2^63 - 1`；无符号的话，它可以存储最小值 `0` 和最大值 `2^64 - 1`。

```java
long example = 42; long longLong = 284; long anotherLong = 73;
```

```java
// 数字末尾必须附加 "L"，因为默认情况下，
// 数字被假设为 int 类型。附加 "L" 使其成为 long，
// 因为 54975513888 (2^39) 大于 int 的最大值 (2^31 - 1) // 必须附加 "L"
```

```java
long bigNumber = 54975513888L;
```

## 第 10.9 节：boolean 基本类型

`boolean` 可以存储两个值之一：`true` 或 `false`。

```java
boolean foo = true;
System.out.println("foo " + foo); // true

boolean bar = false;
System.out.println("bar " + bar); // false

boolean notFoo = !foo;
System.out.println("notFoo " + notFoo); // false

boolean fooAndBar = foo && bar;
System.out.println("fooAndBar " + fooAndBar); // false

boolean fooOrBar = foo || bar;
System.out.println("fooOrBar " + fooOrBar); // true

boolean fooXorBar = foo ^ bar;
System.out.println("fooXorBar " + fooXorBar); // true
```

`boolean` 的默认值为 `false`。

## 第 10.10 节：byte 基本类型

`byte` 是一个 8 位有符号整数。它可以存储最小值 `-128` 和最大值 `127`。

```java
byte example = 36;
byte myByte = 96;
byte anotherByte = 7;
```

```java
byte addedBytes = (byte) (myByte + anotherByte); // -123
byte subtractedBytes = (byte) (myByte - anotherByte); // 89
```

`byte` 的最大值和最小值可以找到：

```java
byte high = Byte.MAX_VALUE; // high == 127
byte low = Byte.MIN_VALUE; // low == -128
```

`byte` 的默认值为 `0`。

## 第 10.12 节：short 基本类型

`short` 是一个 16 位有符号整数。它的最小值为 `-32,768`，最大值为 `32,767`。

```java
short example = 48;
short myShort = 987;
short anotherShort = 17;
```

```java
short addedShorts = (short) (myShort + anotherShort); // 1004
short subtractedShorts = (short) (myShort - anotherShort); // 970
```

## 第 11 章：字符串

字符串（`java.lang.String`）是存储在程序中的文本片段。在 Java 中，字符串不是原始数据类型，但它们在 Java 程序中非常常见。

在 Java 中，字符串是不可变的，这意味着它们不能被更改。（点击此处查看关于不可变性的更详细的解释。）

## 第 11.1 节：比较字符串

为了比较字符串是否相等，您应该使用 `String` 对象的 `equals` 或 `equalsIgnoreCase` 方法。

例如，以下代码段将判断两个 `String` 实例在所有字符上是否相等：

```java
String firstString = "Test123";
String secondString = "Test" + 123;
```

```java
if (firstString.equals(secondString)) {
  // 两个字符串的内容相同。
}
```

此示例将在不区分大小写的情况下对它们进行比较：

```java
String firstString = "Test123";
String secondString = "TEST123";
```

```java
if (firstString.equalsIgnoreCase(secondString)) {
  // 两个字符串相等，忽略单个字符的大小写。
}
```

注意，`equalsIgnoreCase` 不允许您指定 `Locale`。例如，如果您在英语中比较两个单词 "Taki" 和 "TAKI"，它们是相等的；但在土耳其语中它们是不同的（在土耳其语中，小写的 `i` 是 `ı`）。对于这种情况，使用 `Locale` 将两个字符串都转换为小写（或大写），然后用 `equals` 进行比较是解决办法。

```java
String firstString = "Taki";
String secondString = "TAKI";
System.out.println(firstString.equalsIgnoreCase(secondString)); // 输出 true

Locale locale = Locale.forLanguageTag("tr-TR");
System.out.println(firstString.toLowerCase(locale).equals(
  secondString.toLowerCase(locale))); // 输出 false
```

## 不要使用 == 运算符比较字符串

除非您能保证所有字符串都已内化（intern，见下文），否则**不应使用** `==` 或 `!=` 运算符来比较字符串。这些运算符实际上测试的是引用，多个 `String` 对象可以表示相同的字符串，这会导致错误的答案。

相反，请使用 `String.equals(Object)` 方法，它将根据值比较 `String` 对象。如需详细解释，请参考“陷阱：使用 `==` 比较字符串”。

## 在 switch 语句中比较字符串

从 Java 1.7 开始，可以在 `switch` 语句中将字符串变量与字面量进行比较。确保字符串不为 `null`，否则它将始终抛出 `NullPointerException`。值使用 `String.equals` 进行比较，即大小写敏感。

```java
String stringToSwitch = "A";
switch (stringToSwitch) {
  case "a":
    System.out.println("a");
    break;
  case "A":
    System.out.println("A"); // 代码执行到这里
    break;
  case "B":
    System.out.println("B");
    break;
  default:
    break;
}
```

## 与常量值比较字符串

在将字符串与常量值比较时，可以将常量值放在 `equals` 的左侧，以确保如果另一个字符串为 `null`，您不会得到 `NullPointerException`。

如果 `foo` 为 `null`，`"baz".equals(foo).equals("baz")` 将抛出 `NullPointerException`，而 `"baz".equals(foo)` 将求值为 `false`。

版本 >= SE 7

更具可读性的替代方案是使用 `Objects.equals(foo, "baz")`，它对两个参数都进行了空检查：`Objects.equals(foo, "baz")`。

（注意：关于通常情况下避免 `NullPointerException` 更好，还是让它们发生然后修复根源，是有争议的；参见此处和此处。显然，避免这种策略的“最佳实践”是合理的。）

## 字符串排序

`String` 实现了 `Comparable<String>` 接口并提供了 `String.compareTo` 方法（如本示例开头所述）。这使得字符串的自然排序是区分大小写的。`String` 类提供了一个名为 `CASE_INSENSITIVE_ORDER` 的 `Comparator<String>` 常量，适用于区分大小写的排序。

## 与内化的字符串比较

Java 语言规范 (JLS 3.10.6) 规定了如下内容：

“此外，字符串字面量始终引用 `String` 类的同一个实例。这是因为字符串字面量——或更通地说，作为常量表达式值的字符串——会被内化以共享唯一的实例，使用 `String.intern()` 方法。”

这意味着使用 `==` 比较两个字符串字面量的引用是安全的。此外，使用 `String.intern()` 方法产生的 `String` 对象的引用也是如此。

例如：

```java
String strObj = new String("Hello!"); String str = "Hello!";
```

```java
// 如果两个字符串引用指向两个相等的字符串则
if (strObj.equals(str)) {
  System.out.println("The strings are equal");
}

// 如果两个字符串引用不指向同一个对象则
if (strObj != str) {
  System.out.println("The strings are not the same object");
}
```

```java
// 如果我们内化与给定字面量相同的字符串，结果是与字面量具有相同引用的字符串。
String internedStr = strObj.intern();
```

```java
if (internedStr == str) {
  System.out.println("The interned string and the literal are the same object");
}
```

## 11.2：更改字符串内字符的大小写

`String` 类型提供了两种方法用于在大写和小写之间转换字符串：
- `toUpperCase` 将所有字符转换为大写
- `toLowerCase` 将所有字符转换为小写

这些方法都返回转换后字符串的新实例：原始 `String` 对象不会被修改，因为 `String` 是不可变的。详情见“字符串的不可变性”。

```java
String string = "This is a Random String";
String upper = string.toUpperCase(); String lower = string.toLowerCase();
```

```java
System.out.println(string); // 输出 "This is a Random String"
System.out.println(lower); // 输出 "this is a random string"
System.out.println(upper); // 输出 "THIS IS A RANDOM STRING"
```

非字母字符（如数字和标点符号）不受这些方法的影响。注意，这些方法在某些条件下可能会错误处理某些 Unicode 字符。

注意：这些方法是区域敏感的，如果用于意上与区域无关的字符串，则可能会产生意外的结果。

例如，在土耳其语 locale 下，`"TITLE".toLowerCase()` 的结果是 `"tıtle"`，其中 `ı` 是 LATIN SMALL LETTER DOTLESS I。对于区域无关的字符串可以获得正确的结果，例如将 `Locale.ROOT` 作为相应转换方法的参数（例如 `toLowerCase(Locale.ROOT)` 或 `toUpperCase(Locale.ROOT)`）。

使用 `Locale.ENGLISH` 在大多数情况下也是正确的，语言无关的方法是 `Locale.ROOT`。

有关需要特殊处理的 Unicode 字符的详细列表可以在 Unicode 网上找到。

## 更改 ASCII 字符串中特定字符的大小写

更改 ASCII 字符串中特定字符的大小写可以使用以下算法：

1. 声明字符串。
2. 输入字符串。
3. 将字符串转换为字符数组。
4. 输入要搜索的字符。
5. 在字符数组中搜索字符。
6. 如果找到，检查字符是小写还是大写。如果是大写，给字符的 ASCII 码加 32。如果是小写，从字符的 ASCII 码减去 32。
7. 修改字符数组中的原始字符。
8. 将字符数组转换回字符串。

算法代码示例如下：

```java
Scanner scanner = new Scanner(System.in);
System.out.println("Enter the String");
String s = scanner.next();
char[] a = s.toCharArray();
System.out.println("Enter the character you are looking for");
System.out.println(s);
String c = scanner.next();
char d = c.charAt(0);
for (int i = 0; i < s.length(); i++) {
  if (a[i] == d) {
    if (d >= 'a' && d <= 'z') { d -= 32; }
  } else if (d >= 'A' && d <= 'Z') { d += 32; }
  a[i] = d;
}
s = String.valueOf(a);
System.out.println(s);
```

## 第 11.3 节：在另一个字符串中查找字符串

要检查特定的字符串 `a` 是否包含在字符串 `b` 中，我们可以使用 `String.contains()` 方法，语法如下：
`b.contains(a);` // 如果 `a` 包含在 `b` 中，返回 `true`；否则返回 `false`

`String.contains()` 方法可以用于验证 `CharSequence` 是否可以在 `String` 中找到。该方法以区分大小写的方式在字符串 `b` 中查找字符串 `a`。

```java
String str1 = "Hello World"; String str2 = "Hello";
String str3 = "hello";
```

```java
System.out.println(str1.contains(str2)); // 输出 true
System.out.println(str1.contains(str3)); // 输出 false
```

要找到字符串在另一个字符串中开始的精确位置，请使用 `String.indexOf()`：

```java
String s = "this is a long sentence";
int i = s.indexOf('i'); // 字符串第一个 'i' 索引为 2
int j = s.indexOf("long"); // "long" 在 s 中第一次出现的索引
int k = s.indexOf('z'); // k 为 -1，因为在字符串中没有找到 'z'
int h = s.indexOf("LoNg"); // h 为 -1，因为在字符串中没有找到 "LoNg"
```

`String.indexOf()` 方法返回字符或字符串在另一个字符串中首次出现的索引。如果未找到，则返回 `-1`。

注意：`String.indexOf()` 方法是区分大小写的。忽略大小写的示例为：

```java
String str1 = "Hello World";
String str2 = "wOr";
str1.indexOf(str2); // -1
str1.toLowerCase().contains(str2.toLowerCase()); // true
str1.toLowerCase().indexOf(str2.toLowerCase()); // 6
```



# Ideone 实时演示

## 第 11.4 节：字符串池和堆存储

与许多对象一样，所有实例都在堆（heap）上创建，即使字面量也是如此。当 JVM 在堆中发现没有等效引用的字符串字面量时，JVM 会在堆上创建一个相应的 `String` 实例，并在字符串池（`String pool`）中存储新创建字符串的引用。对相同字符串字面量的任何其他引用都被替换为堆中之前创建的 `String` 实例。

让我们来看下面的示例：

```java
class Strings {

    public static void main(String[] args) {

        String a = "alpha";

        String b = "alpha";

        String c = new String("alpha");

        // 这三个字符串都是等等的

        System.out.println(a.equals(b) && b.equals(c));

        // 虽然 a 和 b 引用的是同一个堆对象

        System.out.println(a == b);

        System.out.println(a != c);

        System.out.println(b != c);

    }

}
```

上述内容的输出为：

```
true true true true
```

![](img/01cc8d6667542262308c820b3f5bd37b_142_0.png)

当我们使用双引号创建字符串时，它首先会在字符串池中查找具有相同值的字符串，如果找到，则直接返回引用；否则，它会在池中创建一个新字符串然后返回引用。然而，使用 `new` 运算符，我们强制 `String` 类在堆空间中创建一个新的 `String` 对象。我们可以使用 `intern()` 方法将其放入池中，从而引用字符串池中具有相同值的其他 `String` 对象。字符串池本身也是创建在堆上的。

**版本 < Java SE 7**

在 Java 7 之前，字符串字面量存储在永久内存（`PermGen`）区域运行时常量池中，该区域的大小是固定的。字符串池也位于永久内存。

**版本 >= Java SE 7**

在 JDK 7 中，`intern` 后的字符串不再分配在 Java 堆的永久内存中，而是分配在 Java 堆的主体（称为新生年代和老年代），并与应用程序创建的其他对象一起分配。这一变化将导致更多数据留在 Java 主堆中，而永久内存中的数据减少，因此可能需要调整堆的大小。由于此变化，大多数应用程序在堆使用上只会看到相对较小的差异，但加载许多类或频繁使用 `String.intern()` 方法的大型应用程序将看到更显著的差异。

## 第 11.5 节：分割字符串

根据特定的字符或正则表达式分割字符串。`split()` 方法具有以下签名：

```java
public String[] split(String regex)
```

注意：`split(regex)` 默认会移除结果中的空字符串。使用分隔符的示例：

```java
// 结果为 {"Mickey, Alicia, Tom"}
```

使用正则表达式的示例：

```java
String lineInput = "What do you need?";

String[] words = lineInput.split("\\s+"); // 结果为 {"What do you you need?"}
```

要关闭这种机制，我们需要使用设置为负值的 `split(delimiter, limit)`：

```java
// 结果为 {"Mickey", "", Tom"}
```

以下字符在正则表达式中被视为特殊字符（元字符）。要根据这些字符分割字符串，你需要转义它们或使用 `Pattern.quote()`：

```java
String s = "abc";

String regex = Pattern.quote("||"); String[] arr = s.split(regex);
```

`limit` 参数控制模式应用的次数并影响数组的长度。如果 `n` 大于 0，则模式最多应用 `n-1` 次，数组长度不会超过 `n`，数组的最后一项将包含最后一个分隔符之后的所有输入。如果 `n` 为负数，则模式尽可能应用，数组长度可以是任意的。如果 `n` 为 0，则模式尽可能应用，数组长度可以是任意的，末尾的空字符串会被丢弃。

### 使用 StringTokenizer 分割

除了 `split()` 方法，字符串还可以使用 `StringTokenizer` 进行分割。

`StringTokenizer` 比 `split()` 更具限制性，用起来也稍复杂。它本质上是为了通过固定字符集（以字符串给出）提取标记。每个字符都将作为一个分隔符。由于这种限制，它的速度比 `split()` 快一倍。

默认字符集为空格（`\s\n\r`）。下面的示例将单独打印每个单词。

```java
String str = "lazy fox jumped over the brown fence";

StringTokenizer tokenizer = new StringTokenizer(str); while (tokenizer.hasMoreTokens()) {

    System.out.println(tokenizer.nextToken());

}
```

这将输出：

```
lazy
fox
jumped over
the
brown fence
```

你可以使用不同的字符集进行分割。

```java
String str = "jumped over";

// 在这种情况下字符 `u` 和 `e` 将用作分隔符 StringTokenizer tokenizer = new StringTokenizer(str, "ue"); while (tokenizer.hasMoreTokens()) {

    System.out.println(tokenizer.nextToken());

}
```

这将输出：

```
jmpd
ov
```

## 第 11.6 节：使用分隔符连接字符串

**版本 ≥ Java SE 8**

可以使用静态方法 `String.join()` 来连接字符串数组：

```java
String[] elements = { "foo", "bar", "foobar" };

String singleString = String.join(" ", elements);
```

同样，还有一个针对 `Iterable` 的重载 `String.join()` 方法。若要对连接过程进行细粒度的控制，您可以使用 `StringJoiner` 类：

```java
StringJoiner sj = new StringJoiner(", ", "[", "]");

// 最后两个参数是可选的，

// 它们了结果字符串的前缀和后缀
```

```java
sj.add("foo");

sj.add("bar");

sj.add("foobar");

System.out.println(sj); // 输出 "[foo, bar, foobar]"
```

要连接字符串流，可以使用连接收集器（`joining collector`）：

```java
Stream<String> stringStream = Stream.of("foo", "bar", "foobar"); 

String joined = stringStream.collect(Collectors.joining(", ", "[", "]"));

System.out.println(joined); // 输出 "[foo, bar, foobar]"
```

这里也可以定义前缀和后缀：

```java
Stream<String> stringStream = Stream.of("foo", "bar", "foobar"); 

String joined = stringStream.collect(Collectors.joining(", ", "{", "}"));

System.out.println(joined); // 输出 "{foo, bar, foobar}"
```

## 第 11.7 节：字符串拼接与 StringBuilder

可以使用 `+` 运算符执行字符串拼接。例如：

```java
String s1 = "a";

String s2 = "b";

String s3 = "c";

String s = s1 + s2 + s3; // abc
```

通常情况下，编译器实现会在底层使用涉及 `StringBuilder` 的方法来执行拼接。编译后，代码看起来类似于下面：

```java
StringBuilder sb = new StringBuilder("a"); 

String s = sb.append("b").append("c").toString();
```

`StringBuilder` 拥有多个重载方法，用于附加不同类型，例如使用 `int` 而不是 `String`。例如，某个实现可以转换：

```java
String s1 = "a";

String s2 = "b";

String s = s1 + s2 + 2; // ab2
```

为以下内容：

```java
StringBuilder sb = new StringBuilder("a"); 

String s = sb.append("b").append(2).toString();
```

上面的示例说明了一个简单的拼接操作，该操作实际上是在代码的单处位置完成的。拼接涉及单个 `StringBuilder` 实例。在某些情况下，拼接是以后累积的方式执行的，例如：

```java
String result = "";

for(int i = 0; i < array.length; i++) { 

    result += extractElement(array[i]); 

}

return result;
```

在这些情况下，通常不会应用编译器优化，每次迭代都会创建一个新的 `StringBuilder` 对象。这可以通过显式地将代码转换为使用单个 `StringBuilder` 来优化：

```java
StringBuilder result = new StringBuilder(); 

for(int i = 0; i < array.length; i++) { 

    result.append(extractElement(array[i])); 

}

return result.toString();
```

`StringBuilder` 初始化时仅具有 16 个字符的空空间。

如果您预先知道将构建更大的字符串，预先初始化足够的大小是有益的，这样内部缓冲区就不需要重新调整：

```java
StringBuilder buf = new StringBuilder(30); // 默认是 16 个字符

buf.append("0123456789");

buf.append("0123456789"); // 否则会导致内部缓冲区的重新分配

String result = buf.toString(); // 生成一个 20 个字符的字符串拷贝
```

如果您正在产生许多字符串，建议复用 `StringBuilder`：

```java
StringBuilder buf = new StringBuilder(100);

for (int i = 0; i < 100; i++) {

  buf.setLength(0); // 清空缓冲区

  buf.append("This is line").append(i).append("\n");

  outfile.write(buf.toString());

}
```

当且仅当多个线程写入同一个缓冲区时，才使用 `StringBuffer`，它是 `StringBuilder` 的同步版本。但由于通常是单线程写入缓冲区，因此使用没有同步的 `StringBuilder` 通常速度更快。

### 使用 concat() 方法：

```java
String string1 = "Hello";

String string2 = "world";

String string3 = string1.concat(string2); // "Hello world"
```

这返回一个新字符串，该字符串在 `string1` 的末尾加上了 `string2`。您也可以对字符串字面量使用 `concat()` 方法，例如：`"My name is ".concat("Buyya")`

## 第 11.8 节：子字符串

有几种方法可以反转字符串使其倒序。

1. `StringBuilder`/`StringBuffer`:

```java
String code = "code";

StringBuilder sb = new StringBuilder(code);

code = sb.reverse().toString();

System.out.println(code);
```

2. 字符数组:

```java
String code = "code";

char[] array = code.toCharArray();

for (int index = 0, mirroredIndex = array.length - 1; index < mirroredIndex; index++, mirroredIndex--) {

    char temp = array[index];

    array[index] = array[mirroredIndex];

    array[mirroredIndex] = temp;

}

// 打印反转结果

System.out.println(new String(array));
```

子字符串也可以用于切片并替换原始字符串中的字符。例如，您解析了一个包含中文字符的中文日期，您想将其存储为格式良好的 `Date` 字符串。

```java
String datestring = "2015年11月17日";

datestring = datestring.substring(0, 4) + "-" + datestring.substring(5,7) + "-" + datestring.substring(8,10);

// 结果将为 2015-11-17
```

`substring` 方法提取字符串的一部分。当提供一个参数时，该参数是起始位置，片段延伸到字符串的末尾。当给定两个参数时，第一个参数是起始字符，第二个参数是结束位置之后字符的索引（索引处的字符不包含在内）。简单的检查方法是，第二个参数减去第一个参数应该得到字符串的预期长度。

**版本 < Java SE 7**

在 JDK < 7u 版本中，`substring` 方法与原始字符串共享内部字符数组，这可能导致内存泄漏。

**版本 ≥ Java SE 7**

`substring` 方法创建一个新的字符数组，防止了内存泄漏。

## 第 11.9 节：平台无关的换行符

由于换行符随平台而异（例如，在 Unix 类系统或 Windows 上），因此通常需要一种平台无关的方法来访问它。在 Java 中，可以从系统中获取：

```java
System.lineSeparator()
```

## 第 11.10 节：反转字符串

有几种方法可以反转字符串使其倒序。

1. `StringBuilder`/`StringBuffer`:

```java
String code = "code";

StringBuilder sb = new StringBuilder(code);

code = sb.reverse().toString();

System.out.println(code);
```

2. 字符数组:

```java
String code = "code";

char[] array = code.toCharArray();

for (int index = 0, mirroredIndex = array.length - 1; index < mirroredIndex; index++, mirroredIndex--) {

    char temp = array[index];

    array[index] = array[mirroredIndex];

    array[mirroredIndex] = temp;

}

// 打印反转结果

System.out.println(new String(array));
```

## 第 11.11 节：为自定义对象添加 toString() 方法

假设您定义了以下 `Person` 类：

```java
public class Person {

    String name;

    int age;

    public Person (int age, String name) {

        this.age = age;

        this.name = name;

    }

}
```

如果您实例化一个新的 `Person` 对象：

```java
Person person = new Person(25, "John");
```

并且在代码中使用以下语句来打印对象：

```java
System.out.println(person.toString());
```



您将得到类似的输出：`Person@7ab89`

这是 `Person` 的父类 `Object` 类中定义的 `toString()` 方法的实现。`Object.toString()` 的文档说明：

`Object` 类的 `toString` 方法返回一个字符串，由对象所属的类名、`@` 字符以及对象哈希值的无符号十六进制表示组成。换句话说，该方法返回的值等于：

```java
getClass().getName() + '@' + Integer.toString(hashCode())
```

因此，为了有意义的输出，您必须重写 `toString()` 方法：

```java
@Override
public String toString() {
    return "My name is " + this.name + " and my age is " + this.age;
}
```

我叫 John，今年 25 岁。你也可以这样写：

```java
System.out.println(person);
```

来自 Ideone 的实时演示。事实上，`println()` 会隐式地调用对象的 `toString` 方法。

## 第 11.12：移除字符串开头和结尾的空白

如果你对一个没有需要移除空白的 `String` 进行 `trim` 操作，将返回相同的 `String` 实例。注意，`trim()` 方法有其自己的空白定义，这与 `Character.isWhitespace()` 方法使用的定义不同。

所有代码为 U+0000 到 U+0020 的 ASCII 字符都被视为空白字符并被 `trim()` 移除。这包括 U+0020 '空格'、U+0009 '制表符'、U+000A '换行'和 U+000D '回车'字符，还包括像 U+0007 '蜂鸣'这样的字符。

Unicode 空格如 U+00A0 '不换行空格'或 U+2003 '全角空格'不会被 `trim` 识别。

## 第 11.13：不区分大小写的 switch

≥ Java SE 7

`switch` 本身无法配置为不区分大小写，但如果绝对需要，可以通过 `toLowerCase()` 或 `toUpperCase()` 使其对输入字符串大小不敏感：

```java
switch(myString.toLowerCase()) {
    case "case1" :
        ...
        break;
    case "case2" :
        ...
        break;
}
```

注意 `Locale`（语言环境）可能会影响大小写转换发生！必须注意标签中不要包含任何大写字符 - 那些永远不会被执行！

## 第 11.14：替换字符串的局部

两种替换方法：通过正则表达式或通过精确匹配。

注意：原始 `String` 对象将保持不变，返回值持有修改后的 `String`。

### 精确匹配

将单个单字符替换为另一个单字符：

```java
String replace(char oldChar, char newChar)
```

返回一个新字符串，该字符串是将此字符串中所有旧的 `oldChar` 替换为 `newChar` 后的结果。

```java
String s = "popcorn";
System.out.println(s.replace('p','W'));
```

结果：`WoWCorn`

将字符序列替换为另一个字符序列：

```java
String replace(CharSequence target, CharSequence replacement)
```

将此字符串中匹配 `target` 序列的子字符串替换为指定的字面量替换内容。

```java
String s = "metal petal et al.";
System.out.println(s.replace("etal","etallica"));
```

结果：`metallica petica et al.`

### 正则表达式

注意：分组使用 `$` 字符来引用分组，如 `$1`。

替换所有匹配项：

```java
String replaceAll(String regex, String replacement)
```

将此字符串中匹配给定正则表达式的子字符串替换为给定的替换内容。

```java
String s = "spiral metal petal al";
System.out.println(s.replaceAll("\w*etal", "$1lca"));
```

结果：`spiral metallica petalla al.`

仅替换第一个匹配：

```java
String replaceFirst(String regex, String replacement)
```

将此字符串中第一个匹配给定正则表达式的子字符串替换为给定的替换内容。

```java
String s = "spiral metal petal al";
System.out.println(s.replaceAll("\w*etal", "$1lca"));
```

结果：`spiral metallica petalla al.`

## 第 11.15：获取字符串的长度

为了获取 `String` 对象的长度，调用它的 `length()` 方法。长度等于字符串中 UTF-16 代码单元（`chars`）的数量。

```java
String str = "Hello, World!";
System.out.println(str.length()); // 打印 13
```

Ideone 上的实时演示

`String` 中的 `char` 是 UTF-16 值。值 ≥ 0x1000 的 Unicode 代码点（例如，表情符号）使用两个 `char` 位置。要统计 `String` 中 Unicode 代码点的数量，无论每个 `char` 否能容纳在 UTF-16 值中，请使用 `codeCount` 方法：

## 第 11.16：获取字符串中的第 n 个字符

```java
String str = "My String";
System.out.println(str.charAt(0)); // "M"
System.out.println(str.charAt(1)); // "y"
System.out.println(str.charAt(2)); // " "
System.out.println(str.charAt(str.length()-1)); // 最后字符 "g"
```

要获取字符串中的第 n 个字符，只需在 `String` 上调用 `charAt(n)`，其中 `n` 是你想要检索的字符的索引。注意：索引 `n` 从 0 开始，所以第一个元素在 `n=0`。

## 第 11.17：统计字符串中子字符串或字符出现的次数

`org.apache.commons.lang3.StringUtils` 中的 `countMatches` 方法通常用于统计 `String` 中子字符串或字符出现的次数：

```java
import org.apache.commons.lang3.StringUtils;

String text = "One fish, two fish, red fish, blue fish";

// 统计子字符串出现的次数
String stringTarget = "fish";
int stringOccurrences = StringUtils.countMatches(text, stringTarget); // 4
```

```java
// 统计字符出现的次数
char charTarget = ';';
int charOccurrences = StringUtils.countMatches(text, charTarget); // 3
```

否则，使用标准 Java API 实现同样的功能：

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

String text = "One fish, two fish, red fish, blue fish";
System.out.println(countIn("fish", text)); // 4
System.out.println(countIn(",", text)); // 3
```

```java
public static int countIn(String search, String text) {
    Pattern pattern = Pattern.compile(search);
    Matcher matcher = pattern.matcher(text);
    int stringOccurrences = 0;
    while (matcher.find()) {
        stringOccurrences++;
    }
    return stringOccurrences;
}
```

## 第 12：StringBuilder

介绍 `StringBuilder` 类

## 第 12.1：StringBuilder 类

- 关键点：
    - 用于创建可变的（修改）字符串。
    - 可变：可以被修改。
    - 是线程安全的：多个线程不能同时访问。
    - 方法：
        - `synchronized StringBuilder append(String s)`
        - `synchronized StringBuilder insert(int offset, String s)`
        - `synchronized StringBuilder replace(int startIndex, int endIndex, String str)`
        - `synchronized StringBuilder delete(int startIndex, int endIndex)`
        - `synchronized StringBuilder reverse()`
        - `int int()`
        - `void ensureCapacity(int minimumCapacity)`
        - `char charAt(int index)`
        - `int length()`
        - `String substring(int beginIndex)`
        - `String substring(int beginIndex, int endIndex)`

显示 `String` 和 `StringBuilder` 实现区别的示例：

```java
class Test {
    public static void main(String[] args[]) {
        String str = "study";
        str.concat("tonight");
        System.out.println(str); // 输出：study

        StringBuilder strB = new StringBuilder("study");
        strB.append("tonight");
        System.out.println(strB); // 输出：studytonight
    }
}
```

## 第 13：StringBuilder

Java `StringBuilder` 类用于创建可变的字符串。Java `StringBuilder` 类与 `StringBuffer` 类相同，不同同步。自 JDK 1.5 起可用。

## 第 13.1：比较 StringBuilder、StringBuilder、Formatter 和 StringJoiner

`StringBuffer`、`StringBuilder`、`Formatter` 和 `StringJoiner` 类是 Java 工具类，主要用于从其他信息组合字符串：

`StringBuffer` 类自 Java 1.0 以来一直存在，提供了多种方法来构建和修改包含字符序列的“缓冲区”。

`StringBuilder` 类是在 Java 5 中引入的，用于解决 `StringBuffer` 类的性能问题。这两个类的 API 基本相同。`StringBuffer` 和 `StringBuilder` 之间的主要区别是前者是线程安全的而后者不是。

此示例展示了如何使用 `StringBuilder`：

```java
int one = 1;
String color = "red";
StringBuilder sb = new StringBuilder();
sb.append("One=").append(one).append(", Color=").append(color).append("\n");
System.out.print(sb);
// 打印 "One=1, Color=red" 后跟 ASCII 换行符。
```

（`StringBuffer` 类的使用方法相同：只需将 `StringBuilder` 替换为 `StringBuffer` 即可）

仅当你需要 `StringBuilder` 的线程安全版本时使用 `StringBuffer`。

`Formatter` 提供了更丰富的字符串格式化功能，但效率没有 `StringBuilder` 高。这是因为每次调用 `Formatter.format(...)` 都会涉及：

- 解析字符串格式，
- 创建并填充变长参数数组，并对原始类型参数进行自动装箱。

`StringJoiner` 提供了使用分隔符对字符串序列进行简洁高效的格式化，但不适用于其他格式化任务。

## 第 13.2：将字符串重复 n 次

问题：创建一个包含重复 n 次字符串 `s` 的字符串。

最简单的方法是反复拼接字符串：

```java
final int n = ...
final String s = ...
String result = ""
```

```java
for (int i = 0; i < n; i++) {
    result += s;
}
```

这会创建包含 1 到 n 次 `s` 的新实例，导致运行时间为 `O(s.length() * n)` = `O(s.length() * (1+2...+(n-1)+n))`。

为了避免这种情况，应该使用 `StringBuilder`，它允许以 `O(s.length() * n)` 的复杂度创建字符串。

```java
final int n = ...
final String s = ...
StringBuilder builder = new StringBuilder();
```

```java
for (int i = 0; i < n; i++) { 
    builder.append(s);
}
String result = builder.toString();
```

## 第 14 章：字符串分词器 (String Token)

`java.util.StringTokenizer` 类允许你将字符串拆分为标记（tokens）。这是拆分字符串的一种简单方法。分隔符集合（分隔标记的字符）可以在创建时指定或按每个标记指定。

## 第 14.1 节：通过空格分割 StringTokenizer

```java
import java.util.StringTokenizer;

public class Simple {
    public static void main(String args[]){
        StringTokenizer st = new StringTokenizer("apple ball cat dog", " ");
        while (st.hasMoreTokens()) {
            System.out.println(st.nextToken());
        }
    }
}
```

输出：

```
apple
ball
cat
dog
```

## 第 14.2 节：通过逗号 ',' 分割 StringTokenizer

```java
public static void main(String args[]) {
    StringTokenizer st = new StringTokenizer("apple,ball,cat,dog");
```

输出：

```
apple
ball
cat
dog
```

## 第 15 章：将字符串分为固定长度的部分

## 第 15.1 节：将字符串拆分为已知长度的子字符串

技巧是使用带有正则表达式 `\G` 的后行查找，意思是“上一次匹配的结束”：

```java
String[] parts = str.split("(?=\G.{8})");
```

正则表达式匹配上一次匹配结束后的 8 个字符。由于在这种匹配是零宽度的，我们可以简单说“上一次匹配后的 8 个字符”。方便的是，`\G` 初始化为开头，因此它适用于输入的第一部分。

## 第 15.2 节：将字符串拆分为变长度的子字符串

与已知长度示例相同，但将长度插入正则表达式：

```java
int length = 5;
String[] parts = str.split("(?=\G.{" + length + "})");
```



## 第 16 章：Date 类

### 参数说明

| 参数 | 描述 |
| :--- | :--- |
| 无参数 | 使用分配时间（精确到毫秒）创建一个新的 `Date` 对象 |
| `long date` | 创建一个新的 `Date` 对象，其时间设置为自“纪元”（GMT 1970 年 1 月 1 日 00:00:00）以来经过的毫秒数 |

## 第 16.1 节：将 java.util.Date 转换为 java.sql.Date

当 `Date` 对象需要写入数据库时，通常需要将 `java.util.Date` 转换为 `java.sql.Date`。`java.sql.Date` 是毫秒值的包装器，被 JDBC 用于标识 SQL Date 类型。

在下例示例中，我们使用 `java.util.Date()` 构造函数，它创建一个 `Date` 对象并将其初始化为表示最接近的毫秒。该 `Date` 被用于 `convert(java.util.Date utilDate)` 方法，以返回一个 `java.sql.Date` 对象。

## 示例

```java
public class UtilToSqlConversion {

    public static void main(String args[]) {

        java.util.Date utilDate = new java.util.Date();

        System.out.println("java.util.Date is : " + utilDate); 

        java.sql.Date sqlDate = convert(utilDate);

        System.out.println("java.sql.Date is : " + sqlDate);

        DateFormat df = new SimpleDateFormat("dd/MM/YYYY - hh:mm:ss");

        System.out.println("dateFormated date is : " + df.format(utilDate));

    }

    private static java.sql.Date convert(java.util.Date uDate) { 

        java.sql.Date sDate = new java.sql.Date(uDate.getTime()); 

        return sDate;

    }

}
```

## 输出

```
java.util.Date is : Fri Jul 22 14:40:30 IST 2016
java.sql.Date is : 2016-07-22
dateFormated date is : 22/07/2016 - 02:40:35
```

`java.util.Date` 包含日期和时间信息，而 `java.sql.Date` 仅包含日期信息。

## 第 16.2 节：基础日期输出

使用以下代码配合字符串 `yyyy/MM/dd hh:mm:ss`，我们将得到以下输出：

```
2016/04/19 11:45:36
```

```java
// 定义使用的格式
String formatString = "yyyy/MM/dd hh:mm:ss";

// 获取当前日期对象
Date date = Calendar.getInstance().getTime();

// 创建格式化器
SimpleDateFormat simpleDateFormat = new SimpleDateFormat(formatString);

// 格式化日期
String formattedDate = simpleDateFormat.format(date);

// 打印
System.out.println(formattedDate);

// 以上代码的单行版本
System.out.println(new SimpleDateFormat("yyyy/MM/dd hh:mm:ss").format(Calendar.getInstance().getTime()));
```

## 第 16.3 节：Java 8 LocalDate 和 LocalTime 对象

`Date` 和 `LocalDate` 对象之间无法精确转换，因为 `Date` 对象表示特定的日期时间，而 `LocalDate` 对象不包含时间和或时区信息。然而，如果你只关心日期，在它们之间进行转换是有用的。

非常漂亮。

```java
System.out.println(time);
```

你还可以对 `LocalTime` 对象进行加、减小时、分钟、秒和纳秒的操作，即：

```java
time.plusMinutes(1);
time.getMinutes();
time.minusMinutes(1);
```

你可以通过以下代码将其转换为 `Date` 对象：

```java
LocalTime lTime = LocalTime.now();

Instant instant = lTime.toDate(LocalDate.of(A_YEAR, A_MONTH, A_DAY)).atZone(ZoneId.systemDefault()).toInstant();
Date time = Date.from(instant);
```

这个类在定时器类中工作得非常好，可以用来模拟闹钟。

## 第 16.7 节：将格式化的日期字符串表示转换为 Date 对象

此方法可用于将格式化的日期字符串表示转换为 `Date` 对象。

> ```
> /**
> * 使用给定的格式解析日期。
> * @param formattedDate 格式化的日期字符串
> * @param dateFormat 创建字符串时使用的日期格式
> * @return 日期
> */
> ```

```java
public static Date parseDate(String formattedDate, String dateFormat) {

    Date date = null;

    SimpleDateFormat objDf = new SimpleDateFormat(dateFormat);

    try {

        date = objDf.parse(formattedDate);

    }

    catch (ParseException e) {

        // 对异常进行任何需要的操作。

    }

    return date;

}
```

## 第 16.8 节：创建 Date 对象

```java
Date date = new Date();

System.out.println(date); // Thu Feb 25 05:03:59 IST 2016
```

这里的 `Date` 对象包含了创建该对象时的当前日期和时间。

```java
Calendar calendar = Calendar.getInstance();

calendar.set(90, Calendar.DECEMBER, 11);

Date myBirthDate = calendar.getTime();

System.out.println(myBirthDate); // Mon Dec 31 00:00:00 IST 1990
```

`Date` 对象是通过 `Calendar` 实例创建的，因为数据构造函数已被废弃且不建议使用。要这样做，我们需要从工厂方法获取一个 `Calendar` 实例。然后我们可以使用数字或者使用 `Calendar` 提供的月份常量来设置月份和日期，以提高可读性并减少错误。

```java
calendar.set(90, Calendar.DECEMBER, 11, 8, 35);

Date myBirthDateTime = calendar.getTime();

System.out.println(myBirthDateTime); // Mon Dec 31 08:32:35 IST 1990
```

除了日期，我们还可以按照小时、分钟和秒的顺序传递时间。

## 第 16.9 节：比较 Date 对象

| 类 | 版本 |
| :--- | :--- |
| `Calendar`, `Date`, and `LocalDate` | < Java 8 |
| `before`, `after`, `compareTo` 和 `equals` 方法 | |

```java
// 使用 Calendar 和 Date 对象
final Date today = new Date();

final Calendar calendar = Calendar.getInstance(); 

calendar.set(1990, Calendar.NOVEMBER, 1, 0, 0, 0); 

Date birthdate = calendar.getTime();

final Calendar calendar2 = Calendar.getInstance(); 

calendar2.set(1990, Calendar.NOVEMBER, 1, 0, 0); 

Date samebirthdate = calendar2.getTime();
```

// Before 示例

```java
System.out.printf("Is %1$t before %2$t? %3$b%n", today, birthdate,
Boolean.valueOf(today.before(birthdate)));
System.out.printf("Is %1$t before %2$t? %3$b%n", today, today,
Boolean.valueOf(today.before(today)));
System.out.printf("Is %2$t before %1$t? %3$b%n", today, birthdate,
Boolean.valueOf(birthdate.before(today)));
```

// After 示例

```java
System.out.printf("Is %1$t after %2$t? %3$b%n", today, birthdate,
Boolean.valueOf(today.after(birthdate)));
System.out.printf("Is %1$t after %1$t? %3$b%n", today, birthdate,
Boolean.valueOf(today.after(today)));
System.out.printf("Is %2$t after %1$t? %3$b%n", today, birthdate,
Boolean.valueOf(birthdate.after(today)));
```

// Compare 示例

```java
System.out.printf("Compare %1$tF to %2$t: %3$d%n", today, birthdate,
Integer.valueOf(today.compareTo(birthdate)));
System.out.printf("Compare %1$tF to %1$t? %3$d%n", today, birthdate,
Integer.valueOf(today.compareTo(today)));
System.out.printf("Compare %2$tF to %1$t? %3$d%n", today, birthdate,
Integer.valueOf(birthdate.compareTo(today)));
```

// Equal 示例

```java
System.out.printf("Is %1$F equal to %2$t? %3$b%n", today, birthdate,
Boolean.valueOf(today.equals(birthdate)));
System.out.printf("Is %1$tF equal to %2$t? %3$b%n", today, birthdate,
```

使用 Epoch 日（Epoch Day）。Epoch 计数是一个简单的天数计数，其中第 0 天是 1970-01-01 (ISO)。

## 第 16.10 节：将字符串转换为日期

`SimpleDateFormat` 类中的 `parse()` 方法有助于将字符串模式转换为 `Date` 对象。

```java
DateFormat dateFormat = DateFormat.getInstance(DateFormat.SHORT, Locale.US);
String dateStr = "02/25/2016"; // input String
Date date = dateFormat.parse(dateStr);
System.out.println(date.getTime()); // 1456368000000
```

文本格式有 4 种不同的样式：`SHORT`、`MEDIUM`（默认）、`LONG` 和 `FULL`，它们都取决于本地区域（locale）。如果没有指定本地区域，将使用系统默认本地区域。

| Style | Locale.US | Locale.France |
| :--- | :--- | :--- |
| SHORT | 6/30/09 | 30/06/09 |
| MEDIUM | Jun 30, 2009 | 30 jun 2009 |
| LONG | June 30, 2009 | 30 jun 2009 |
| FULL | Tuesday, June 30, 2009 | mardi 30 jun 2009 |

## 第 16.11 节：时区和 java.util.Date

`java.util.Date` 对象没有时区的概念。

- 无法为 `Date` 设置时区
- 无法更改 `Date` 的时区
- 使用 `new Date()` 构造函数创建的 `Date` 对象将用系统默认时区的当前时间初始化

然而，可以使用 `java.text.SimpleDateFormat` 等在不同时区显示日期：

```java
Date date = new Date();
//打印默认时区
System.out.println(TimeZone.getDefault().DisplayName());
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss"); //注意：格式中不包含时区!
//在原始时区打印日期
System.out.println(sdf.format(date));
// 伦敦当前时间
sdf.setTimeZone(Timezone.getTimeZone("Europe/London"));
System.out.println(sdf.format(date));
```

输出：

```
Central European Time
2016-07-21 22:50:56
2016-07-21 21:50:56
```

## 第 17 章：日期与时间 (java.time.*)

### 第 17.1 节：计算两个 LocalDate 之间的差异

使用 `LocalDate` 和 `ChronoUnit`：

```java
LocalDate d1 = LocalDate.of(2017, 5, 1);
LocalDate d2 = LocalDate.of(2017, 5, 18);
// 现在，由于 ChronoUnit 枚举器方法接受两个 Temporals 作为参数，你可以顺利地传递 LocalDate 实例
long days = ChronoUnit.DAYS.between(d1, d2);
System.out.println(days);
```

### 第 17.2 节：日期和时间信息

不带时区信息的日期和时间：

```java
LocalDateTime dateTime = LocalDateTime.of(2016, Month.JULY, 27, 8, 0);
LocalDateTime now = LocalDateTime.now();
LocalDateTime parsed = LocalDateTime.parse("2016-07-27T07:00:00");
```

带时区信息的日期和时间：

```java
ZoneId zoneId = ZoneId.of("UTC+2");
ZonedDateTime dateTime = ZonedDateTime.of(2016, Month.JULY, 27, 7, 0, 0, 235, zoneId);
ZonedDateTime composition = ZonedDateTime.of(localDate, localTime, zoneId);
ZonedDateTime now = ZonedDateTime.now(); // 默认时区
ZonedDateTime parsed = ZonedDateTime.parse("2016-07-27T07:00:00+01:00[Europe/Stockholm]");
```

带偏移量信息的日期和时间（即不考虑夏令时 DST 变化）：

```java
ZoneOffset zoneOffset = ZoneOffset.ofHours(2);
OffsetDateTime dateTime = OffsetDateTime.of(2016, 6, 27, 7, 0, 0, 235, zoneOffset);
OffsetDateTime composition = OffsetDateTime.of(localDate, localTime, zoneId);
OffsetDateTime now = OffsetDateTime.now(); // 从默认 ZoneId 获取的偏移量
OffsetDateTime parsed = OffsetDateTime.parse("2016-07-27T07:00:00+02:00");
```

### 第 17.3 节：日期和时间操作



```java
LocalDate tomorrow = LocalDate.now().plusDays(1);
LocalDate anHourFromNow = LocalDateTime.now().plusHours(1);
Long daysBetween = java.time.temporal.ChronoUnit.DAYS.between(LocalDate.now(), LocalDate.now().plusDays(3)); // 3
Duration duration = Duration.between(Instant.now(), ZonedDateTime.parse("2016-07-27T07:00:00+01:00[Europe/Stockholm]"));
```

### 第 17.4 节：Instant

代表时间中的一个瞬间。可以被视为 Unix 时间戳的封装。

```java
Instant now = Instant.now();
Instant epoch1 = Instant.ofEpochMilli(0);
Instant epoch2 = Instant.parse("1970-01-01T00:00:00Z");
java.time.temporal.ChronoUnit.SECONDS.between(epoch1, epoch2); // 0
```

### 第 17.5 节：日期时间 API 各类的用法

以下示例解释了：

```java
import java.time.Clock;
import java.time.Duration;
import java.time.Instant;
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.ZoneId;
import java.time.ZonedDateTime;
import java.util.TimeZone;

public class SomeMethods {

    /**
     * LocalDateTime 类的方法
     */
    public static void checkLocalDateTime() {
        LocalDateTime localDateTime = LocalDateTime.now();
        System.out.println("Local date time using now() method : " + localDateTime);
        LocalDateTime ldt1 = LocalDateTime.now(ZoneId.of("EST"));
        System.out.println("LOCAL TIME using now(ZoneId) : " + ldt1);
        LocalDateTime ldt2 = LocalDateTime.now(ZoneId.of("PST"));
        System.out.println("Local TIME using now(Clock()) : " + ldt2);
    }

    /**
     * Clock抽象类的方法
     */
    public static void checkClock() {
        Clock clock = Clock.systemUTC();
        // 根据 ISO 8601 表示时间
        System.out.println("Time using Clock class : " + clock.instant());
    }

    /**
     * Instant 类的方法
     */
    public static void checkInstant() {
        Instant instant = Instant.now();
        System.out.println("Instant using now() method : " + instant);
        Instant ins1 = Instant.now(Clock.systemUTC());
        System.out.println("Instants using now(Clock) : + ins1);
    }

    /**
     * Duration 类的方法
     */
    public static void checkDuration() {
        // toString() 将时长转换为 PTNHnMS 格式。如果字段为 0 则被忽略。
        // P 是时长标识符（历史上称为 'period'），位于表示的开头。
        // Y 是年份标识符，表示年数。
        // M 是月份标识符，表示月份数。
        // W 是周标识符，表示周数。
        // D 是日期标识符，表示天数。
        // T 是时间标识符，位于时间组件之前。
        // H 是小时标识符，表示小时数。
        // M 是分钟标识符，表示分钟数。
        // S 是秒标识符，表示秒数。
        System.out.println(Duration.ofDays(2));
    }

    /**
     * 显示没有日期的本地时间。它不存储或表示日期时间，而是墙上时间的表示。
     */
    public static void checkLocalTime() {
        LocalTime localTime = LocalTime.now();
        System.out.println("LocalTime :: " + localTime);
    }

    /**
     * ISO-8601 标准带时区信息的日期时间
     */
    public static void checkZonedDateTime() {
        ZonedDateTime dateTime = ZonedDateTime.now(ZoneId.of("CST"));
        System.out.println(dateTime);
    }
}
```

### 第 17.6 节：日期时间格式化

在 Java 8 之前，`java.text` 包中有 `DateFormat` 和 `SimpleDateFormat` 类，这些遗留代码将继续使用一段时间。但 Java 8 提供了处理格式化解析的现代方法。在格式化和解析中，你首先使用 `String` 对象创建 `DateTimeFormatter`，然后将其用于格式化或解析。

```java
import java.time.*;
import java.time.format.*;
class DateTimeFormat {
    public static void main(String[] args) {

        // 解析
        String pattern = "d-MM-yyyy HH:mm";
        DateTimeFormatter dtf1 = DateTimeFormatter.ofPattern(pattern);

        LocalDateTime ldp1 = LocalDateTime.parse("2014-03-25T01:30", dtf1);
        LocalDateTime ldp2 = LocalDateTime.parse("15-05-2016 13:55", dtf1);
        System.out.println(ldp1 + "\n" + ldp2); // 将以默认格式打印
        // 格式化
        DateTimeFormatter dtf2 = DateTimeFormatter.ofPattern("EEE d, MMMM, yyyy HH:mm");
        DateTimeFormatter dtf3 = DateTimeFormatter.ISO_LOCAL_DATE_TIME;
        LocalDateTime ldt1 = LocalDateTime.now();
        System.out.println(ldt1.format(dtf2) + "\n" + ldt1.format(dtf3));
    }
}
```

一个重要通知，与其使用自定义模式，使用预定义的格式化器是良好的做法。你的代码将看起来更清晰，从长远来看，使用 ISO8601 会对你有帮助。

## 第 17.7 节：简单的日期操作

获取当前日期。

`LocalDate.now()`

获取昨天的日期。

`LocalDate y = LocalDate.now().minusDays(1);`

获取明天的日期

`LocalDate t = LocalDate.now().plusDays(1);`

获取特定日期。

`LocalDate t = LocalDate.of(1974, 6, 2, 30, 0, 0);`

除了 `plus` 和 `minus` 方法外，还有一组“with” 方法可用于设置 `LocalDate` 实例上的特定字段。

`LocalDate.now().withMonth(6);`

上面的示例返回一个月份设置为 6 月的新实例（这与 `java.util.Date` 不同，后者的 `setMonth` 索引从 0 开始，导致 6 月变为 5）。由于 `LocalDate` 操作返回的是不可变的 `LocalDate` 实例，这些方法也可以链式调用。

`LocalDate ld = LocalDate.now().plusDays(1).plusYears(1);` 这将给出一年后的明天日期。

## 第 18 章：LocalTime

| 方法 | 输出 |
| :--- | :--- |
| `LocalTime.of(13, 12, 11)` | 13:12:11 |
| `LocalTime.MIDNIGHT` | 00:00 |
| `LocalTime.NOON` | 12:00 |
| `LocalTime.now()` | 来自系统时的当前时间 |
| `LocalTime.MAX` | 23:59:59.999999999 |
| `LocalTime.ofSecondsOfDay(84399)` | 23:59:59 (从当天秒值获取时间) |
| `LocalTime.ofNanoOfDay(000000000)` | 00:00:02 (从当天纳秒值获取时间) |

支持的最小本地时间是 00:00。

## 第 18.1 节：两个 LocalTime 之间的时间量

有两种等效的方法计算两个 `LocalTime` 之间的时间单位：(1) 通过 `until(Temporal, TemporalUnit)` 方法和 (2) `TemporalUnit.between(Temporal, Temporal)`。

```java
import java.time.LocalTime;
import java.time.ChronoUnit;
public class AmountOfTime {
    public static void main(String[] args) {
        LocalTime start = LocalTime.of(1, 0, 0); // 时, 分, 秒
        LocalTime end = LocalTime.of(2, 10, 20); // 时, 分, 秒
        long halfDays1 = start.until(end, ChronoUnit.HALF_DAYS); // 0
        long halfDays2 = start.until(end, ChronoUnit.HALF_DAYS.between(start, end)); // 0
        long hours1 = start.until(end, ChronoUnit.HOURS); // 1
        long hours2 = ChronoUnit.HOURS.between(start, end); // 1
        long minutes1 = start.until(end, ChronoUnit.MINUTES); // 70
        long minutes2 = ChronoUnit.MINUTES.between(start, end); // 70
        long seconds1 = start.until(end, ChronoUnit.SECONDS); // 4220
        long seconds2 = ChronoUnit.SECONDS.between(start, end); // 4220
        long millis1 = start.until(end, ChronoUnit.MILLIS); // 4220000
        long millis2 = ChronoUnit.MILLIS.between(start, end); // 4220000
        long microsecs1 = start.until(end, ChronoUnit.MICROS); // 4220000000
        long microsecs2 = ChronoUnit.MICROS.between(start, end); // 4220000000
        long nanosecs1 = start.until(end, ChronoUnit.NANOS); // 42200000000000
        long nanosecs2 = ChronoUnit.NANOS.between(start, end); // 42200000000000

        // 使用其他 ChronoUnit 将抛出 UnsupportedTemporalTypeException。 
        // 以下方法是其示例。
        long days1 = start.until(end, ChronoUnit.DAYS);
        long days2 = ChronoUnit.DAYS.between(start, end);
    }
}
```

## 第 18.2 节：简介

`LocalTime` 是一个不可变且线程安全的类，用于表示时间，通常被视为时-分-秒。时间的精度精确到纳秒。例如，值“13:45.30.123456789”可以存储在 `LocalTime` 中。

### 字段

- `MAX` - 支持的最大 `LocalTime`，“23:59:59.999999999”。
- `MIDNIGHT`, `MIN`, `NOON`

### 重要静态方法

- `now()`, `now(Clock clock)`, `now(ZoneId zone)`, `parse(CharSequence text)`

### 重要实例方法

- `isAfter(LocalTime other)`, `isBefore(LocalTime other)`, `minus(Temporal amountToSubtract)`, `minus(long amountToSubtract, Unit unit)`, `plus(Temporal amountToAdd)`, `plus(long amountToAdd, TemporalUnit unit)`

时间差可以通过以下任何方式计算：

```java
ZoneId zone = ZoneId.of("Asia/Kolkata");
LocalTime now = LocalTime.now();
LocalTime now1 = LocalTime.now(zone);
LocalTime then = LocalTime.parse("04:16:40");

long timeDiff = Duration.between(now, now1).toMinutes();
long timeDiff1 = java.time.temporal.ChronoUnit.MINUTES.between(now, now1);
```

你也可以从任何对象加减小时、分钟或秒：

- `minusHours(long hoursToSubtract)`
- `minusMinutes(long minutesToSubtract)`
- `minusNanos(long nanosToSubtract)`
- `minusSeconds(long secondsToSubtract)`
- `plusHours(long hoursToSubtract)`
- `plusMinutes(long minutesToSubtract)`
- `plusNanos(long nanosToSubtract)`
- `plusSeconds(long secondsToSubtract)`

## 第 18.3 节：时间修改

你可以增加小时、分钟、秒和纳秒：

```java
LocalTime time = LocalTime.now();
LocalTime addHours = time.plusHours(5); // 加5小时
LocalTime addMinutes = time.plusMinutes(15); // 加15分钟
LocalTime addSeconds = time.plusSeconds(30); // 加30秒
LocalTime addNanoseconds = time.plusNanos(150000000); // 加150ms
```

## 第 18.4 节：时区与它们的时间



# 第 19 章：BigDecimal

`BigDecimal` 算术运算（加、减、乘、除）、精度处理、舍入和格式转换。`BigDecimal` 表示任意精度的带符号数字。在需要高精度计算时应使用此类。

## 第 19.1 节：比较 BigDecimal

应该使用 `compareTo` 方法来比较 `BigDecimal`：

```java
BigDecimal a = new BigDecimal(5);
a.compareTo(new BigDecimal(0)); // 大，返回1
a.compareTo(new BigDecimal(5)); // 等，返回0
a.compareTo(new BigDecimal(10)); // 小，返回-1
```

通常不应使用 `equals` 方法，因为它在数值和精度相等时才认为相等：

```java
BigDecimal a = new BigDecimal(5);
a.equals(new BigDecimal(5)); // 值和精度相等，返回 true
a.equals(new BigDecimal(5.00)); // 值相等但精度不等，返回 false
```

## 第 19.2 节：使用 BigDecimal 代替 float

由于 `float` 类型在内存中的表示方式，使用该类型的操作结果是不准确的——某些值以近似形式存储。很好的例子是货币计算。如果需要高精度，应该使用其他类型，例如 Java 7 提供的 `BigDecimal`。

```java
import java.math.BigDecimal;
public class FloatTest {
    public static void main(String[] args) {
        float accountBalance = 10000.0f;
        System.out.println("Operations using float:");
        System.out.println("1000 operations for 1.99");
        for(int i = 0; i<1000; i++) {
            accountBalance -= 1.99f;
            System.out.println(String.format("Account balance after float operations: %f", accountBalance));
        }

        BigDecimal accountTwo = new BigDecimal("10000.00");
        System.out.println("Operations using BigDecimal:");
        System.out.println("1000 operations for 1.99");
        BigDecimal operation = new BigDecimal("1.99");
        for(int i = 0; i<1000; i++) {
            accountTwo = accountTwo.subtract(operation);
            System.out.println(String.format("Account balance after BigDecimal operations: %f", accountTwo));
        }
    }
}
```

该程序的输出：

```
Operations using float:

1000 operations for 1.99

Account balance after float operations: 8009.765625

Operations using BigDecimal:

1000 operations for 1.99

Account balance after BigDecimal operations: 8010.000000
```

对于初始余额 10000.0，经过 1000 次 1.99 操作后，我们预期余额为 8010.0。使用 `float` 类型得到的答案是 8009.77，这在货币计算中是不可接受的精精确度。使用 `BigDecimal` 可以得到正确的结果。

## 第 19.3 节：BigDecimal.valueOf()

`BigDecimal` 类包含对常用数字（例如 0 到 10）的内部缓存。`BigDecimal.valueOf()` 方法优于具有相似参数的构造函数，例如在下面的示例中 `a` 优于 `b`。

```java
BigDecimal a = BigDecimal.valueOf(10L); // 返回缓存对象
reference BigDecimal b = new BigDecimal(10L); // 不返回缓存对象引用
```

```java
BigDecimal a = BigDecimal.valueOf(20L); // 不返回缓存对象
reference BigDecimal b = new BigDecimal(20L); // 不返回缓存对象引用
```

```java
BigDecimal a = BigDecimal.valueOf(15.15); // 将 double (float) 转换为 BigDecimal 的优方法，返回的值与使用 Double.toString(double)构造的结果相等
```

```java
BigDecimal b = new BigDecimal(15.15); // 返回不可预测的结果
```

## 第 19.4 节：使用 BigDecimal 进行数学运算

此示例展示了如何使用 `BigDecimal` 进行数学运算。

### 1. 加法

```java
BigDecimal a = new BigDecimal("5");
```

```java
BigDecimal b = new BigDecimal("7");
```

```java
//Equivalent to result = a + b
BigDecimal result = a.add(b);
System.out.println(result);
```

Result : 12

### 2. 减法

```java
BigDecimal a = new BigDecimal("5"); BigDecimal b = new
BigDecimal("7");
```

```java
//Equivalent to result = a - b BigDecimal result = a.subtract(b);
System.out.println(result);
```

Result : -2

### 3. 乘法

当两个 `BigDecimal` 相乘时，结果的精度（scale）将等于两个操作数精度之和。

```java
BigDecimal a = new BigDecimal("5.11"); BigDecimal b = new
BigDecimal("7.221");
```

Result : 36.89931

可以使用重载的 `multiply` 方法来更改结果的精度，该方法允许传递 `MathContext` - 这是一个描述运算符规则的对象，特别是结果的精度和舍入模式。有关可用舍入模式的更多信息，请参阅 Oracle 文档。

```java
BigDecimal a = new BigDecimal("5.11"); BigDecimal b = new
BigDecimal("7.221");
```

```java
MathContext returnRules = new MathContext(4,
RoundingMode.HALF_DOWN);
```

```java
//Equivalent to result = a * b
BigDecimal result = a.multiply(b, returnRules); System.out.println(result);
```

Result : 36.90

### 4. 除法

除法比其他算术运算稍微复杂一点，考虑下面的示例：

```java
BigDecimal a = new BigDecimal("5"); BigDecimal b = new
BigDecimal("7");
```

```java
BigDecimal result = a.divide(b); System.out.println(result);
```

我们期望得到类似 : 0.7142857142857143 的结果，但我们得到的是：

```
Result : java.lang.ArithmeticException: Non-terminating decimal expansion; no exact representable decimal result.
```

如果我想用 5 除以 2，结果是一个有限小数，这种情况下运行得非常完美；但对于那些除法得到非无限结果的数字，我们会得到 `ArithmeticException`。在现实世界中，无法预测除法过程中会遇到的值，因此我们需要为 `BigDecimal` 除法指定精度（Scale）和舍入模式（Rounding Mode）。关于精度和舍入模式的更多信息，请参阅 Oracle 文档。

例如，我可以这样做：

```java
BigDecimal a = new BigDecimal("5"); BigDecimal b = new
BigDecimal("7");
```

```java
//Equivalent to result = a / b (保留最多 10 位小数并采用四舍六入)
BigDecimal result = a.divide(b,10,RoundingMode.HALF_UP);
System.out.println(result);
```

Result : 0.7142857143

### 5. 余数或取模

```java
BigDecimal a = new BigDecimal("5"); BigDecimal b = new
BigDecimal("7");
```

```java
//Equivalent to result = a % b BigDecimal result = a.remainder(b)
System.out.println(result);
```

Result : 5

### 6. 幂

```java
BigDecimal a = new BigDecimal("5");
```

```java
//Equivalent to result = a^10 BigDecimal result = a.pow(10)
System.out.println(result);
```

Result : 9765625

### 7. 最大

```java
BigDecimal a = new BigDecimal("5"); BigDecimal b = new
BigDecimal("7");
```

```java
//Equivalent to result = MAX(a,b) BigDecimal result = a.max(b)
System.out.println(result);
```

Result : 7

### 8. 最小

```java
BigDecimal a = new BigDecimal("5"); BigDecimal b = new
BigDecimal("7");
```

```java
//Equivalent to result = MIN(a,b) BigDecimal result = a.min(b)
System.out.println(result);
```

Result : 5

### 9. 小数点左移

```java
BigDecimal a = new BigDecimal("5234.98433776");
```

```java
//小数点向当前位置左移动 2 位 BigDecimal
result = a.movePointLeft(2);
System.out.println(result);
```

Result : 52.3449843776

### 10. 小数点右移

```java
BigDecimal a = new BigDecimal("5234.98433776");
```

```java
//小数点向当前位置右移动 3 位 BigDecimal
result = a.movePointRight(3);
```

Result : 5234498.4376

对于上述示例还有许多选项和参数组合（例如，`divide` 方法有 6 种变体），此列表并非详尽的，仅涵盖了一些基础示例。

## 第 19.5 节：用零、一或十初始化 BigDecimal

`BigDecimal` 为数字 零、一 和十提供了静态属性。使用这些属性而不是使用实际数字是良好的做法：

- `BigDecimal.ZERO`
- `BigDecimal.ONE`
- `BigDecimal.TEN`

通过使用静态属性，你避免了不必要的实例化，在代码中获得的是字面量而不是“魔数数字”。

```java
// 坏示例：
BigDecimal bad0 = new BigDecimal(0);
BigDecimal bad1 = new BigDecimal(1);
BigDecimal bad10 = new BigDecimal(10);
```

```java
// 良好示例：
BigDecimal good0 = BigDecimal.ZERO;
BigDecimal good1 = BigDecimal.ONE;
BigDecimal good10 = BigDecimal.TEN;
```

## 第 19.6 节：BigDecimal 对象是不可变的

如果你想用 `BigDecimal` 进行计算，你必须使用返回的值，因为 `BigDecimal` 对象是不可变的：

```java
BigDecimal a = new BigDecimal("42.23");
BigDecimal b = new BigDecimal("10.0001");
a.add(b); // a 仍然是 42.23
BigDecimal c = a.add(b); // c 将是 52.231
```

# 第 20 章：BigInteger

`BigInteger` 类用于涉及比原始数据类型规模更大的整数的数学运算。例如，100 的阶乘有 158 位——远大于 `long` 类型能表示的范围。`BigInteger` 提供了 Java 所有基本类型的对应类。

## 第 20.1 节：初始化

`BigInteger` 类提供了 Java 所有基本运算符的对应方法。由于 `java.math` 包不是自动可用的，在使用之前可能需要导入它。将 `long` 或 `int` 值转换为 `BigInteger` 使用：

```java
longValue=Long.MAX_VALUE;
BigInteger valueFromLong=BigInteger.valueOf(longValue);
```

或整数：

```java
intValue=Integer.MIN_VALUE;
BigInteger valueFromInt=BigInteger.valueOf(intValue);
```

将指定基数的 `BigInteger` 字符串表示转换为 `BigInteger`：

```java
String binaryString="10";
int binaryRadix=2
```

`BigInteger` 还支持将字节数组直接转换为 `BigInteger` 实例。目前支持有符号和无符号字节序编码：

```java
byte[] bytes=new byte[] {(byte) 0x80 };
BigInteger valueFromBytes=new BigInteger(bytes);
```

这将产生 -128 的 `BigInteger` 实例，因为第一位被解释为符号位。

```java
byte[] unsignedBytes = new byte[] { (byte) 0x80 };
int sign = 1; // Positive
BigInteger valueFromUnsignedBytes = new BigInteger(sign, unsignedBytes);
```

这将产生 128 的 `BigInteger` 实例，因为字节被解释为无符号数字，且符号被显式设置为 1（正数）。

为常用值提供了预定义的常量：

```java
import java.time.LocalTime;
import java.time.ZoneId;
import java.time.temporal.ChronoUnit;

public class Test {
    public static void main(String[] args) {
        ZoneId zone = ZoneId.of("Asia/Kolkata");
        LocalTime now = LocalTime.now();
        LocalTime now1 = LocalTime.now(zone);
        LocalTime now2 = LocalTime.now(zone);
        System.out.println("Current Time : " + now);
        System.out.println("Berlin : " + now1);
        System.out.println("Brazil : " + now2);
        long minutesBetween = ChronoUnit.MINUTES.between(now2, now1);
        System.out.println("Minutes Berlin and Brazil : " + minutesBetween);
    }
}
```



`BigInteger.ZERO` — 值为 `"0"`。`BigInteger.ONE` — 值为 `"1"`。

`BigInteger.TEN` — 值为 `"10"`。

还有 `BigInteger.TWO`（值为 `"2"`），但你无法在代码中使用它是私有的。

## 第 20.2 节：BigInteger 数学运算示例

`BigInteger` 是不可变对象，因此你需要将数学运算的结果赋值一个新的 `BigInteger` 实例。

加法：10 + 10 = 20

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("10");
BigInteger sum = value1.add(value2);
System.out.println(sum);
```

output: 20

减法：10 - 9 = 1

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("9");
BigInteger sub = value1.subtract(value2);
System.out.println(sub);
```

output: 1

除法：10 / 5 = 2

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("5");
BigInteger div = value1.divide(value2);
System.out.println(div);
```

output: 2

除法: 17/4 = 4

```java
BigInteger value1 = new BigInteger("17");
BigInteger value2 = new BigInteger("4");
BigInteger div = value1.divide(value2);
System.out.println(div);
```

output: 4

乘法: 10 * 5 = 50

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("5");
BigInteger mul = value1.multiply(value2);
System.out.println(mul);
```

output: 50

幂: 10^3 = 1000

```java
BigInteger value1 = new BigInteger("10");
BigInteger power = value1.pow(3);
System.out.println(power);
```

output: 1000

取余: 10 % 6 = 4

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("6");
BigInteger power = value1.remainder(value2);
System.out.println(power);
```

output: 4

GCD: 12 和 18 的最大公约数 (GCD) 是 6。

```java
BigInteger value1 = new BigInteger("12");
BigInteger value2 = new BigInteger("18");
System.out.println(value1.gcd(value2));
```

Output: 6

两个 BigInteger 的最大值:

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("11");
System.out.println(value1.max(value2));
```

Output: 11

两个 BigInteger 的最小值:

```java
BigInteger value1 = new BigInteger("10");
BigInteger value2 = new BigInteger("11");
System.out.println(value1.min(value2));
```

Output: 10

## 第 20.3 节：比较 BigIntegers

你可以像在 Java 中比较 `String` 或其他对象一样比较 `BigInteger`。

例如：

```java
BigInteger one = BigInteger.valueOf(1);
BigInteger two = BigInteger.valueOf(2);
if(one.equals(two)) {
    System.out.println("Equal");
} else {
    System.out.println("Not Equal");
}
```

输出:

Not Equal

注意：

通常情况下，不要使用 `==` 运算符来比较 `BigInteger`。

`==` 运算符：比较的是引用；即两个值是否指向同一个对象。

`equals()` 方法：比较两个 `BigInteger` 的内容。

例如，不应在以下情况下比较 `BigInteger`：

```java
if (firstBigInteger == secondBigInteger) {
    // 只检查引用相等性，不检查内容相等性！
}
```

这样做可能会导致意想不到的行为，因为 `==` 运算符只检查引用相等性。如果两个 `BigInteger` 包含相同的内容，但没有指向同一个对象，这将失败。相反，请使用上文所述的 `equals` 方法来比较 `BigInteger`。

你还可以将 `BigInteger` 与常量值（如 0, 1, 10）比较。

例如：

```java
BigInteger reallyBig = BigInteger.valueOf(1);
if(BigInteger.ONE.equals(reallyBig)){ // 当它们相等时执行代码。
}
```

你还可以使用 `compareTo()` 方法比较两个 `BigInteger`，如下：`compareTo()` 返回 3 个值。

- 0：当两者相等时。

- 1：当第一个大于第二个（括号中的那个）。

- -1：当第一个小于第二个时。

`BigInteger reallyBig = BigInteger.valueOf(10);` `BigInteger reallyBig1 = BigInteger.valueOf(100);`

```java
if (reallyBig.compareTo(reallyBig1) == 0)
// 当两者相等时执行代码。
```

```java
else if(reallyBig.compareTo(reallyBig1) == 1){
    // 当 reallyBig 大于 reallyBig1 时执行代码。
}
```

```java
else if(reallyBig.compareTo(reallyBig1) == -1){
    // 当 reallyBig 小于 reallyBig1 时执行代码。
}
```

## 第 20.4 节：BigInteger 的二进制逻辑运算

`BigInteger` 也支持 `Number` 类型可用的二进制逻辑运算。所有操作都是通过调用方法来实现的。

二进制按位或 (Binary Or):

```java
BigInteger val1 = new BigInteger("10");
BigInteger val2 = new BigInteger("9");
val1.or(val2);
```

输出: 11（等于 10 | 9）

二进制按位与 (Binary And):

```java
BigInteger val1 = new BigInteger("10");
BigInteger val2 = new BigInteger("9");
val1.and(val2);
```

输出: 8（等于 10 & 9）

二进制按位异或 (Binary Xor):

```java
BigInteger val1 = new BigInteger("10");
BigInteger val2 = new BigInteger("9");
val1.xor(val2);
```

输出: 3（等于 10 ^ 9）

右移 (RightShift):

```java
BigInteger val1 = new BigInteger("10");
BigInteger val2 = new BigInteger("9");
val1.shiftRight(1);
```

输出: 5（等于 10 >> 1）

左移 (LeftShift):

```java
BigInteger val1 = new BigInteger("10");
BigInteger val2 = new BigInteger("9");
val1.shiftLeft(1);
```

输出: 20（等于 10 << 1）

按位取反 (Binary Not):

```java
BigInteger val1 = new BigInteger("10");
val1.not();
```

输出: -11（等于 ~10）

## 22.3 节：检查一个数字是否是 2 的幂

如果整数 x 是 2 的幂，则只有一个比特位被设置为 1，而 x-1 在该位之后的所有位都设置为 1。例如：4 的二进制是 100，3 的二进制数是 011，这满足上述条件。0 不是 2 的幂，必须进行显式检查。

```java
boolean isPowerOfTwo(int x)
{
  return (x != 0) && ((x & (x - 1)) == 0);
}
```

### 左移和右移用法

假设我们有三种权限：READ（读）、WRITE（写）和 EXECUTE（执行）。每种权限的范围从 0 到 7。（假设是 4 位数值系统）

RESOURCE = READ WRITE EXECUTE（12 位数字）

RESOURCE = 0100 0110 0101 = 465（12 位数字）

我们如何获取设置在上述（12 位数字）上的（12 位数字）权限？

0100 0110 0101

0000 0000 0111 (&)

0000 0000 0101 = 5

所以，这就是我们获取 RESOURCE 的 EXECUTE 权限的方法。现在，如果我们想获取 RESOURCE 的 READ 权限怎么办？

0100 0110 0101

0111 0000 0000 (&) 0100 0000 0000 = 1024

对吧？你可能是这样想的？但是，权限的结果是：

我们只想获取该资源的 READ 权限。如果我们观察，READ 权限是 8 位，

这就是为什么我们需要移位运算符的原因。在实际结果后面，所以如果应用某些移位运算符，哪一个可以将 READ 权限移到结果的最右侧呢？如果我们这样做：

0100 0000 0000 >> 8 => 0000 0000 0100（因为它是正数，

会被 0 替换，如果你不在乎符号位，请使用无符号右移运算符）

我们现在实际上拥有了 READ 权限，其值为 4。

现在，例如，我们给了一个 RESOURCE 的 READ、WRITE、EXECUTE 权限，我们可以做什么来设置这个 RESOURCE 的权限？

让我们先看二进制权限的例子。（仍然假设是 4 位数值系统）

READ = 0001

WRITE = 0100

EXECUTE = 0110

如果你认为我们将简单地执行：

READ | WRITE | EXECUTE，你对了一部分，但不完全正确。看，

如果我们执行 READ | WRITE | EXECUTE 会发生什么：

0001 | 0100 | 0110 => 0111

但权限实际上（在我们的示例中）表示为 0001 0110 0110

所以，为了这样做，我们知道 READ 被放置在 8 位之前，WRITE 被放置在 4 位之前，PERMISSIONS 放在最后。用于 RESOURCE 权限的数值系统实际上是 12 位（在我们的示例中）。它在不同的系统中可能会不同。

```java
(READ << 8) | (WRITE << 4) | (EXECUTE)
0000 0000 0001 << 8 (READ)
0001 0000 0000 (左移 8 位)
0000 0000 0100 << 4 (WRITE)
0000 0100 0000 (左移 4 位)
0000 0000 0001 (EXECUTE)
现在如果我们将上述移位的结果相加，将类似于：
0000 0000 0000 (READ)
0000 0000 0000 (WRITE)
0000 0000 0001 (EXECUTE) 0001 0100 0001 (PERMISSIONS)
```

## 22.4 节：有符号与无符号移位

在 Java 中，所有数值基本类型都是有符号的。例如，`int` 始终表示 [-2^31 - 1, 2^31] 之间的值，保留第一位作为值的符号位：负值位 -1，正值位 0。

基础移位运算符 `>>` 和 `<<` 是有符号运算符。它们会保留值的符号。但程序员经常使用无符号数来存储无符号值。对于 `int` 来说，这意味着将范围移动到 [0, 2^32 - 1]，以获得比有符号 `int` 价值倍的值。对于那些高级用户来说，符号位没有意义。这就是为什么 Java 添加了 `>>>`，这是一个左移运算符（此处应为无符号右移），它忽略了符号位。

初始值：4 ( 100 ) 有符号左移：4 << 1 ( 80 ) 有符号右移：4 >> 1 ( 10 ) 无符号右移：4 >>> 1 ( 10 ) 初始值：-4 ( 11111111111111111111111111111111 )

## 22.5 节：表示 2 的幂

在 Java 中，所有数值基本类型都是有符号的。例如，`int` 始终表示 [-2^31 - 1, 2^31] 之间的值，保留第一位作为值的符号位：负值位 -1，正值位 0。

基础移位运算符 `>>` 和 `<<` 是有符号运算符。它们会保留值的符号。但程序员经常使用无符号数来存储无符号值。对于 `int` 来说，这意味着将范围移动到 [0, 2^32 - 1]，以获得比有符号 `int` 价值倍的值。对于那些高级用户来说，符号位没有意义。这就是为什么 Java 添加了 `>>>`，这是一个无符号右移运算符（原文误写为左移），它忽略了符号位。

初始值：4 ( 100 ) 有符号左移：4 << 1 ( 80 ) 有符号右移：4 >> 1 ( 10 ) 无符号右移：4 >>> 1 ( 10 ) 初始值：-4 ( 11111111111111111111111111111111 )

## 22.6 节：打包与解包值

在 Java 中，所有数值基本类型都是有符号的。例如，`int` 始终表示 [-2^31 - 1, 2^31] 之间的值，保留第一位作为值的符号位：负值位 -1，正值位 0。

基础移位运算符 `>>` 和 `<<` 是有符号运算符。它们会保留值的符号。但程序员经常使用无符号数来存储无符号值。对于 `int` 来说，这意味着将范围移动到 [0, 2^32 - 1]，以获得比有符号 `int` 价值倍的值。对于那些高级用户来说，符号位没有意义。这就是为什么 Java 添加了 `>>>`，这是一个无符号右移运算符（原文误写为左移），它忽略了符号位。

## 第 23 章：数组

数组详情

- ArrayType：数组的类型。这可以是基本类型（`int`, `long`, `byte`）或对象（`String`, `Object`）。

- index：数组中某个对象的位置。

- length：每个数组在创建时都需要指定长度。这可以在创建空数组时（`new int[3]`）或在指定值时隐含实现（`{1, 2, 3}`）。

数组允许存储和检索任意数量的值。它们类似于数学中的向量，并作为多维数组使用。数组可以存储任何类型的数据：如 `int` 等基本类型或 `Object` 等引用类型。

### 23.1 节：创建和初始化数组

基础情况

```java
int[] numbers1 = new int[3];
int[] numbers2 = { 1, 2, 3 };
int[] numbers3 = new int[] { 1, 2, 3 };
```

// 3 个 int 数组，默认值为 0 // 3 个 int 值的字面量

```java
// 已初始化的 3 个 int 数组
int[][] numbers4 = {{ 1, 2 }, { 3, 4, 5 }}; // 锯形数组
int[][] numbers5 = new int[5][];
int[][] numbers6 = new int[5][4];
```

// 锯形数组，一个维度为 5 // 多维数组

可以使用任何基本类型或引用类型创建数组。

```java
float[] boats = new float[5]; // 五个 32 位浮点数的数组。
double[] header = new double[] { 4.56, 332.267, 7.0, 0.3367, 10.0 };
// 六个 64 位浮点数的数组。
```

数组是一种存储固定数量原始类型值或对象实例引用的数据结构。

数组中的每一项被称为元素，每个元素通过其数值索引进行访问。数组的长度在数组创建时就已经确定了：

```java
int size = 42;
int[] array = new int[size];
```

**数组的大小在初始化时运行时是固定的。** 初始化后无法更改。如果大小在运行时必须是可变的，则应该使用如 `ArrayList` 这样的集合（`Collection`）类。`ArrayList` 将元素存储在数组中，并通过分配新数组和从旧数组复制元素来支持调整大小。

如果数组是原始类型，例如



`int[] array1 = {1, 2, 3 }; int[] array2 = new int[10];`

它们被直接存储在数组本身中。在没有初始化器的情况下（如上面的`array2`），分配给每个元素的默认值是`0`（零）。

如果数组是对象引用，例如

`SomeClassOrInterface[] array = new SomeClassOrInterface[10];`

那么数组包含指向类型为`SomeClassOrInterface`对象的引用。

这些引用可以指向`SomeClassOrInterface`的任何子类（对于类）或实现类（对于接口）。如果数组声明没有初始化器，则为每个元素分配默认值`null`。

由于所有数组都使用`int`索引，因此数组的大小必须指定为`long`类型：

```
long size = 23L;
int[] array = new int[size]; // 编译错误：
// 不兼容的类型：从 long 转换为 int 可能会导致损失
```

数组使用从零开始的索引系统，这意味着索引从`0`开始，到`长度 - 1`结束。

例如，下面的图片表示一个大小为`10`的数组。在这里，第一个元素位于索引`0`，最后一个元素位于索引`9`，而不是第一个元素位于索引`1`而最后一个元素位于索引`10`（见下图）。

![](img/01cc8d6667542262308c820b3f5bd37b_206_0.png)

对数组元素的访问是在常数时间内完成的。这意味着访问数组第一个元素的开销（时间上）与访问第二个元素、第三个元素等开销相同。

Java 提供了几种定义和初始化数组的方法，包括字面量和构造函数符号。当使用`new Type[length]`构造函数声明数组时，每个元素将用以下默认值初始化：

原始数值类型：`byte`, `short`, `int`, `long`, `float`和`double`为`0`。`char`类型为`\u0000`（空字符）。`boolean`类型为`false`。引用类型为`null`。

## 创建和初始化原始类型数组

```
int [] array1 = new int[] { 1, 2, 3 }; // 使用 new 操作符
// 数组初始化器创建数组。
int[] array2 = {1, 2, 3 }; // 使用数组初始化器的快捷语法。
int[] array3 = new int[]; // 等同于 {0, 0, 0 }
int[] array4 = null; // 数组本身是一个对象，所以它
// 可以设置为 null。
```

在声明数组时，`[]`会作为类型的一部分出现在声明开头（在类型名之后），或者作为特定变量的声明符的一部分（在变量名之后），或者两者兼有：

```
int array5[];; /* 等同于 */ int[] array5;
int a, b[], c[];; /* 等同于 */ int a; int[] b; int[][] c;
```

`int[] a, b[];` /* 等同于 */ `int[] a; int[][] b;`

`int a[], b, c[][];` /* 编译错误，`[]`不是声明开头的类型的一部分，

// 而是在 'b' 之前。 */

// 在声明返回数组的方法时也适用相同的规则：

`int foo() { ... }` /* 等同于 */ `int[] foo() { ... }`

在接下来的示例中，两种声明都是正确的，并且可以编译

运行而没有任何任何问题。然而，Java 编码规范和 Google Java 风格指南都不建议使用变量名后加括号的形式——括号标识数组类型，并应该与类型说明一起出现。方法的返回签名也应该同样如此。

`float array[];` /* 像 */ `int foo() { ... }` /* 不被建议 */ `float[] array;` /*

// 以及 */ `int[] foo() { ... }` /* 被建议 */

不被建议的类型是为了适应 C 语言用户，他们熟悉 C 语言语法，该语言的括号位于变量名之后。

在 Java 中，可以拥有大小为`0`的数组：

`int[] array = new int[0];` // 编译和运行良好。`int[] array2 = {};` //

 等效语法。

然而，由于它是空数组，无法从中读取元素或为其赋值：

`array[0] = 1;` // 抛出`java.lang.ArrayIndexOutOfBoundsException`。`int i =`

`array[0];` // 也抛出`ArrayIndexOutOfBoundsException`。

此类空数组通常在处理数组时有用，这样代码只需要担心可能导致`NullPointerException`的潜在`null`值。数组的长度必须是非负的：

`int[] array = new int[-1];` // 抛出`java.lang.NegativeArraySizeException`

大小可以使用名为`length`的公共字段来确定：

`System.out.println(array.length);` // 输出`0`

注意：`array.length`返回数组的实际大小。

## 多维数组

创建多维数组简单的方法如下：

`int[][] a = new int[3][4];`

与 C# 不同，只支持矩形数组。在 Java 中，你可以创建锯齿数组（jagged arrays）或不规则数组（ragged arrays），每行可以有不同的长度。

## Java 中多维数组的表示

| 1 | 0 | 2 | -1 |

|---|---|---|---|

| 7 | -3 | 2 | 5 |

| -5 | -2 | 2 | 9 |

![](img/01cc8d6667542262308c820b3f5bd37b_208_0.png)

实际上，`A`持有一个对包含`3`个元素的数组的引用，其中每项都是指向`4`个元素的引用。

## 创建和初始化引用类型数组

`String[] array6 = new String[] {"Laurel", "Hardy"};` // 使用`new`操作符

// 数组初始化器创建数组。

`String[] array7 = {"Laurel", "Hardy"};` // 使用数组初始化器的快捷语法。

`String[] array8 = new String[3];` // {null, null, null}

`String[] array9 = null;` // 数组本身是一个对象，所以它

// 可以设置为`null`。

## Ideone Live

除了上面的`String`字面量外，数组初始化的快捷语法也适用于`Object`类型：

`Object[] array10 = { new Object(), new Object() };`

由于数组是协变的，引用类型可以初始化为子类的数组，但如果你尝试将数组设置为`String`的其他内容，将抛出`ArrayStoreException`：

```
Object[] array11 = new String[] {"foo", "bar", "baz" }; array11[1] = "qux";
// 正常
array11[1] = new StringBuilder(); // 抛出 ArrayStoreException
```

可以使用`String[] emptyArray = new String[0]`初始化零元素。例如，这种零长度数组用于在方法返回对象的运行时从集合创建数组。

在原始类型和引用类型中，空数组初始化（例如`String[] array8 = new String[3]`）将为每个数据类型初始化默认值。

## 创建和初始化泛型数组

在泛型类中，由于擦除，泛型数组无法像这样初始化：

`public class MyGenericClass<T> { private T[] a;`

```
public MyGenericClass() {
a = new T[5]; // 编译错误：泛型数组创建
}
```

相反，可以使用以下方法之一创建（注意这些方法会产生未检查警告）：

- 1. 通过创建一个`Object`数组，并将其强制转换为泛型类型：

`a = (T[]) new Object[5];`

这是最简单的方法，但由于底层数组仍然是`Object[]`类型，此方法没有提供类型安全。因此，这种创建数组的方法最好仅在不公开的泛型类内部使用。

- 2. 使用带有类参数的`Array.newInstance`：

```java
public MyGenericClass(Class<T> clazz) { a = (T[]) Array.newInstance(clazz, 5); }
```

在这里，必须将`T`的类传递给构造函数。`Array.newInstance`的返回类型始终是`Object`。然而，这种方法更安全，因为新创建的数组始终是`T[]`，因此可以安全地扩展。

### 初始化后填充数组 版本 ≥ Java SE 1.2

可以使用`Arrays.fill()`为数组填充相同的初始化值：

```java
Arrays.fill(array8, "abc"); // "abc", "abc", "abc"
```

在 Ideone 上运行

`fill()`也可以为数组指定范围内的每个元素赋值：

```java
Arrays.fill(array8, 1, 2, "aaa"); // 在索引 1 到 2 处放置 "aaa"
```

自 Java 8 起，方法`setAll`及其并发等效方法`parallelSetAll`可用于设置数组每个元素的生成的值。这些方法传递一个生成函数，该函数接受一个索引并返回位置所需的值。

以下示例创建了一个整数数组，并将其所有元素设置为它们相应的索引值：

```java
int[] array = new int[5];
Arrays.setAll(array, i -> i); // 数组变为 { 0, 1, 2, 3, 4 }
```

在 Ideone 上运行

### 数组的单独声明与初始化

数组元素的索引值必须是全整数（`0, 1, 2, 3, 4, ...`）且小于数组的长度（索引从`0`开始）。否则，将抛出`ArrayIndexOutOfBoundsException`：

```java
int[] array9; // 数组声明 - 未初始化
array9 = new int[3]; // 初始化数组 - { 0, 0, 0 }
array9[0] = 10; // 设置索引 0 的值 - { 10, 0, 0 }
array9[1] = 20; // 设置索引 1 的值 - { 10, 20, 0 }
array9[2] = 30; // 设置索引 2 的值 - { 10, 20, 30 }
```

数组不能使用初始化器快捷语法进行重新初始化

无法通过带有数组初始化器的快捷语法重新初始化数组，因为数组初始化器只能在字段声明或局部变量声明中，或作为数组创建的一部分进行指定。

然而，可以使用旧数组创建一个新数组并将其赋值给变量。这将导致变量引用的数组被重新初始化，变量的内容是一个全新的数组。要执行此操作，可以使用`new`运算符配合数组初始化器并赋值给数组变量：

```java
// 数组[] 的初始初始化
int[] array = new int[] { 1, 2, 3 };
// 打印 "1 2 3"
for (int i : array) {
    System.out.print(i + " ");
}
// 将 array 重新初始化为新的 int[]
array = new int[] { 4, 5, 6 };
// 打印 "4 5 6"
for (int i : array) {
    System.out.print(i + " ");
}
array = { 1, 2, 3, 4 }; // 编译错误！无法通过数组初始化器的快捷语法重新初始化数组。
```

## 第 23.2 ：从数组创建列表

可以使用`Arrays.asList()`方法返回一个包含给定数组元素的固定大小`List`。生成的`List`类型与数组基础类型的参数类型相同。

```java
String[] stringArray = {"foo","bar", "baz"};
List<String> stringList = Arrays.asList(stringArray);
```

注意：此列表由原始数组（其视图）支持，这意味着对列表的任何更改都会改变数组，反之亦然。然而，任何改变列表大小（从而改变数组长度）的更改将抛出异常。

要创建列表的副本，请使用`java.util.ArrayList`的构造函数，并以`Collection`作为参数：

```java
版本 > Java SE 5
String[] stringArray = {"foo", "bar", "baz"};
List<String> list = new ArrayList<String>(Arrays.asList(stringArray));
```

版本 > Java SE 7

在 Java SE 7 及更高版本中，可以使用一对角括号`<>`（空类型参数），这被称为“菱形（Diamond）”。编译器可以从上下文中确定类型参数。这意味着在调用`ArrayList`构造函数时可以省略类型信息，它将在编译期间自动推断。这被称为类型推断（Type Inference），是 Java 泛型的一部分。

```java
// 使用 Arrays.asList()
String[] stringArray = {"foo", "bar", "baz"};
List<String> list = new ArrayList<String>(Arrays.asList(stringArray));

// 使用 ArrayList.addAll()
```

```java
String[] stringArray = {"foo", "bar", "baz"};
ArrayList<String> list = new ArrayList<>();
list.addAll(Arrays.asList(stringArray));
```

（此处省略重复代码块翻译，保持逻辑一致）

```java
String[] stringArray = {"foo", "bar", "baz"};
List<String> list = new ArrayList<String>(Arrays.asList(stringArray));

// 使用 ArrayList.addAll()
```

```java
String[] stringArray = {"foo", "bar", "baz"};
ArrayList<String> list = new ArrayList<>();
list.addAll(Arrays.asList(stringArray));
```

## 第 23.3 ：从集合创建数组

`java.util.Collection`中的两个方法可以从集合创建数组：

`Object[] toArray()`

`<T> toArray(T[] a)`

`Object[] toArray()`可以如下使用：

版本 ≥ Java 5

`Set<String> set = new HashSet<String>();`

`set.add("red");`

`set.add("blue");`

```java
// 虽然 array 是 Set<String>, toArray() 返回的是 Object[] 而不是 String
Object[] objectArray = set.toArray();
```

`<T> toArray(T[])`可以如下使用：

版本 ≥ Java 5

`Set<String> set = new HashSet<String>();`

`set.add("red");`

`set.add("blue");`

```java
// 不需要预先创建正确大小的数组。数组类型是重要的。（如果大小错误，将创建一个相同类型的数组。）
String[] stringArray = set.toArray(new String[0]);
```

```java
// 如果你提供了一个大小相同或更大的数组，它将被填充集合值并返回（不会分配新数组）
String[] stringArray2 = set.toArray(new String[set.size()]);
```

它们之间的不仅仅是无类型与有类型结果的区别。它们的性能也可能不同（详情请参此性能分析章节）：

`Object[] toArray()`使用了向量化的`arraycopy`，这比`T[] toArray(T[] a)`中使用的类型检查`arraycopy`快得多。

`T[] toArray(new T[non-zero-size])`需要在运行时对数组清零，而`T[] toArray(new T[0])`则。这种避免使得后者的调用比前者更快。详细分析请参阅：[古代智慧数组](https://example.com/Arrays-of-Wisdom-of-the-Ancient)。

版本 ≥ Java SE 8

从 Java SE 8 开始（引入了 Stream 概念），可以通过集合生成 Stream，然后使用 Stream 的`toArray`方法创建一个新数组。

`String[] strings = list.stream().toArray(String[]::new);` 示例取自 Stack Overflow 上关于将 ArrayList 转换为 'String[]' 的两个回答 (1, 2)。

## 23.4 节：多维数组与锯齿数组

可以定义具有多个维度的数组。多维数组不是通过提供单个索引来访问，而是通过为每个维度指定一个索引来访问。

多维数组的声明可以通过普通数组声明的基础上为每个维度添加`[]`来完成。例如，要创建一个二维`int`数组，在声明中再添加一组括号，如`int[][]`。三维数组（`int[][][]`）以此此类推。

定义一个具有三行四列的二维数组：



# 多维数组

```java
int rows = 3;
int columns = 3;
int[][] table = new int[rows][columns];
```

可以使用这种结构对数组进行索引并赋值。请注意，未赋值的值是数组类型的默认值，在本例中 `int` 类型的默认值为 0。

```java
table[0][0] = 0; table[0][1] = 1; table[0][2] = 2;
```

也可以一次实例化一个维度，甚至是非矩形的数组。这些通常被称为**锯齿数组**（jagged arrays）。

```java
int[][] nonRect = new int[4][];
```

需要注意的是，虽然可以定义锯齿数组的任何维度，但它的前一级必须已经定义。

```java
// 有效
String[][] employeeGraph = new String[30][];
// 无效
int[][][] unshapeMatrix = new int[][][10];
// 同样无效
int[][] misshapenGrid = new int[100][][10];
```

## 多维数组在 Java 中的表示方式

如果你创建一个数组 `A = new int[3][4]`，你应该将其构想为一个具有 3 行 4 列的“矩阵”。

| A | 1 | 0 | 12 | -1 |
|---|---|---|---|---|
|   | 7 | -3 | 2 | 5 |
|   | -5 | -2 | 2 | 9 |

![](img/01cc8d6667542262308c820b3f5bd37b_216_0.png)

但实际上，`A` 持有一个指向包含 3 个元素的数组的引用，其中每个元素都是指向 4 个 `int` 数组的引用。

图片来源：

http://math.hws.edu/eck/cs124/javanotes3/c8/s5.html

## 锯齿数组的字面量初始化

多维数组和锯齿数组也可以使用字面量表达式进行初始化。以下代码声明并填充了一个 2x3 的 `int` 数组：

```java
int[][] table = {{1, 2, 3}, {4, 5, 6}};
```

注意：锯齿子数组也可能为 `null`。例如，以下代码声明并填充了一个二维 `int` 数组，其第一个子数组为 `null`，第二个子数组长度为 0，第三个子数组长度为 1，最后一个子数组是长度为 2 的数组：

```java
int[][] table = {null,
{1},
{1,2}};
```

对于多维数组，可以通过索引提取低维度的数组：

```java
int[][][] arr = new int[3][3][3];
int[][] arr1 = arr[0]; // 从 arr 获取第一个 3x3 维数组
int[] arr2 = arr1[0]; // 从 arr1 获取第一个 3 维数组
int[] arr3 = arr[0]; // 错误：无法从 int[] 转换为 int
```

## 23.5 节：ArrayIndexOutOfBoundsException

当访问数组不存在的索引时，会抛出 `ArrayIndexOutOfBoundsException`。

数组是从 0 开始索引的，因此第一个元素的索引为 0，最后一个元素的索引是数组容量减 1（即 `array.length - 1`）。

因此，任何通过索引 `i` 请求数组的操作都必须满足 `0 <= i < array.length` 条件，否则将抛出 `ArrayIndexOutOfBoundsException`。

以下代码是一个抛出 `ArrayIndexOutOfBoundsException` 的简单示例。

```java
String[] people = new String[] { "Carol", "Andy" };
```

```java
// 将创建一个数组：
// people[0]: "Carol"
// people[1]: "Andy"
```

```java
// 注意：项目 2 没有索引。尝试访问它将触发异常：
System.out.println(people[2]); // 抛出 ArrayIndexOutOfBoundsException。
```

输出：

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 2
at your.package.path.method(YourClass.java:15)
```

注意，所访问的非法索引也包含在异常中 (2)；此信息可能有助于找到产生的原因。要避免这种情况，只需检查索引是否在数组的范围内即可：

```java
int index = 2;
if (index >= 0 && index < people.length) {
  System.out.println(people[index]);
}
```

## 23.6 节：数组协变

对象数组是协变的，这意味着由于 `Integer` 是 `Number` 的子类，`Integer[]` 也是 `Number[]` 的子类。这看起来可能很直观，但可能会导致意想不到的行为：

```java
Integer[] integerArray = {1, 2, 3};
Number[] numberArray = integerArray; // 有效
Number firstElement = numberArray[0]; // 有效
numberArray[0] = 4L; // 运行时抛出 ArrayStoreException
```

尽管 `Integer[]` 是 `Number[]` 的子类，但它只能包含 `Integer`，尝试分配 `Long` 会抛出异常。注意，这种行为是数组特有的，可以通过使用泛型 `List` 来避免：

```java
List<Integer> integerList = Arrays.asList(1, 2, 3);
List<? extends Number> numberList = integerList;
firstElement = numberList.get(0);
numberList.set(0, 4L); // 编译错误
```

数组的所有元素并不一定需要共享相同的类型，只要它们是数组类型的子类即可：

```java
interface I {}
class A implements I {}
class B implements I {}
class C implements I {}

I[] array10 = new I[] { new A(), new B(), new C() }; // 使用运算符和数组初始化器创建数组。
I[] array11 = new I[] { new A(), new B(), new C() }; // 使用数组初始化器的快捷语法。
I[] array12 = new I[3];
I[] array13 = new I[] { new A(), new A(), new A() }; // 可行，因为 A 实现了 I。
Object[] array14 = new Object[] { "Hello, World!", 3.14159 }; // 使用运算符和数组初始化器创建数组。
Object[] array15 = new Object[] { 64, "My String", null }; // 使用数组初始化器的快捷语法。
```

## 23.7 节：数组转换为 Stream

版本 ≥ Java SE 8

将对象数组转换为 Stream：

```java
String[] arr = new String[] {"str1", "str2", "str3"};
Stream<String> stream = Arrays.stream(arr);
```

使用 `Arrays.stream()` 原始类型数组会将数组转换为 Stream 的原始类型特化版本：

```java
int[] intArr = {1, 2, 3};
IntStream intStream = Arrays.stream(intArr);
```

你也可以限制 Stream 为数组中的某个范围元素。起始索引是包含的，结束索引是排外的：

```java
int[] values = {1, 2, 3, 4};
IntStream intStream = Arrays.stream(values, 2, 4);
```

与 `Arrays.stream()` 类似的方法出现在 `Stream` 类中：`Stream.of()`。区别在于使用变长参数，你可以这样写：

```java
Stream<Integer> intStream = Stream.of(1, 2, 3);
Stream<String> stringStream = Stream.of("1", "2", "3");
Stream<Double> doubleStream = Stream.of(new Double[] {1.0, 2.0});
```

## 23.8 节：遍历数组

你可以使用增强 for 循环（也称为 foreach）或使用数组索引来遍历数组：

```java
int[] array = new int[10];
// 使用索引：读写
for (int i = 0; i < array.length; i++) {
  array[i] = i;
}
```

版本 >= Java SE 5

```java
// 增强 for：只读
for (int e : array) {
  System.out.println(e);
}
```

值得注意的是，数组无法直接使用 `Iterator`，但通过 `Arrays` 库可以转换为列表以获取 `Iterable`。对于包装数组使用 `Arrays.asList`：

```java
Integer[] boxed = {1, 2, 3};
Iterable<Integer> boxedIt = Arrays.asList(boxed); // 可迭代的
Iterator<Integer> boxedIt1 = boxedIt.iterator();
```

对于原始数组（使用 java 8）使用流（特别在此示例中 - `Arrays.stream -> IntStream`）：

```java
int[] primitives = {1, 2, 3};
IntStream primitiveStream = Arrays.stream(primitives); // 可迭代的
PrimitiveIterator.OfInt primitive1 = primitiveStream.iterator();
```

如果你无法使用流（没有 java 8），可以选择使用 google 的 guava 库：
`Iterable<Integer> fromPrimitive2 = Ints.asList(primitives);`

在二维或多维数组中，这两种技术都可以稍微复杂地使用。示例：

```java
int[][] array = new int[10][10];

for (int indexOuter = 0; indexOuter < array.length; indexOuter++) {
  for (int indexInner = 0; indexInner < array[indexOuter].length; indexInner++) {
    array[indexOuter][indexInner] = indexOuter + indexInner;
  }
}
```

Version >= Java SE 5

```java
for (int[] numbers : array) {
  for (int value : numbers) {
    System.out.println(value);
  }
}
```

如果不使用基于索引的循环，无法将数组设置为任何非均匀值。
当然，当使用索引进行迭代时，你也可以使用 `while` 或 `do-while` 循环。

需要注意的是：使用数组索引时，请确保索引在 `0` 到 `array.length - 1` 之间（两者均包含）。不要对数组长度进行硬编码假设，否则当数组长度改变而你的硬编码值未改变时，可能会破坏你的代码。

示例：

```java
int[] numbers = {1, 2, 3, 4};

public void incrementNumbers() {
  // 这样做：
  for (int i = 0; i < numbers.length; i++) {
    numbers[i] += 1; //或者使用这个：numbers[i] = numbers[i] + 1; 或 numbers[i]++
  }
}
```

```java
// 不要这样做：
public void incrementNumbers() {
  for (int i = 0; i < 4; i++) { 
    numbers[i] += 1;
  }
}
```

最好的做法是不要使用复杂的计算来获取索引，而是使用索引进行迭代，如果需要不同的值，再对它们进行计算。
示例：

```java
public void fillArrayWithDoubleIndex(int[] array) { // 这样做：
  for (int i = 0; i < array.length; i++) {
    array[i] = i * 2;
  }
}
```

```java
// 不要这样做：
public void fillArrayWithDoubleIndex(int[] array) {
  int doubleLength = array.length * 2; 
  for (int i = 0; i < doubleLength; i += 2) {
    array[i / 2] = i;
  }
}
```

## 逆序访问数组

```java
int[] array = {0, 1, 1, 2, 3, 5, 8, 13}; 
for (int i = array.length - 1; i >= 0; i--) {
  System.out.println(array[i]);
}
```

## 使用数组减少代码重复

遍历临时数组而不是重复代码可以使你的代码更整洁。当对多个变量执行相同操作时，可以使用它。

```java
// 我们想打印出所有内容
String name = "Margaret";
int eyeCount = 16;
double height = 50.2;
int legs = 9;
int arms = 5;
```

```java
// 复制粘贴法：
System.out.println(name); System.out.println(eyeCount);
System.out.println(height); System.out.println(legs);
System.out.println(arms);
```

```java
// 临时数组法：
for(Object attribute : new Object[]{name, eyeCount, height, legs, arms})
  System.out.println(attribute);
```

```java
// 仅使用数字
for(double number : new double[]{eyeCount, legs, arms, height})
  System.out.println(Math.sqrt(number));
```

请记住，此代码不应在性能关键区域使用，因为每次进入循环时都会创建一个数组，并且基本类型变量将被复制到数组中，因此无法修改。

## 第 23.9 节：数组转字符串

Version ≥ Java SE 5

从 Java 1.5 开始，可以在不遍历指定数组的每个元素的情况下获取其内容的字符串表示。对于单维数组直接使用 `Arrays.toString(Object[])`，对于多维数组使用 `Arrays.deepToString(Object[][])`。

```java
int[] arr = {1, 2, 3, 4};
System.out.println(Arrays.toString(arr)); // 输出 [1, 2, 3, 4]
```

```java
int[][] arr = {
  {1, 2, 3},
  {4, 5, 6},
  {7, 8, 9}
};
System.out.println(Arrays.deepToString(arr)); // 输出 [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

`Arrays.toString()` 方法用于生成数组元素的字符串表示。对于基本类型数组，可以使用它。对于多维数组，可以使用 `Arrays.deepToString()`。例如：

```java
public class Cat {
  String name;
  public Cat(String name) { this.name = name; }
  @Override
  public String toString() { return name; }
}

Cat[] cats = {new Cat("Tom"), new Cat("Jerry")};
System.out.println(Arrays.toString(cats)); // 输出 [Tom, Jerry]
```

如果类没有重写 `toString()`，将使用继承 `Object` 的 `toString()`。例如：

```java
public class Dog { }

Dog[] dogs = {new Dog(), new Dog()};
System.out.println(Arrays.toString(dogs)); // 输出类似 [Dog@15db9742,Dog@6d06d69c]
```

仅仅测试计算出的索引是否大于或等于零。或者，在 Java 中还有一些更简洁的变体：

```java
boolean isPresent = Arrays.asList(strings).contains("A");
```



# 版本要求

```
Version >= Java SE 8
```

```java
boolean isPresent = Stream<String>.of(strings).anyMatch(x -> "A".equals(x));

boolean isPresent = false;

for (String s : strings) {

    if ("A".equals(s)) {

        isPresent = true;

    }

}
```

```java
boolean isPresent = org.apache.commons.lang3.ArrayUtils.contains(ints, 4);
```

## 章节 23.13: 如何更改数组的大小？

简单的答案是，你无法做到这一点。一旦数组被创建，其大小就无法更改。相反，数组只能通过创建一个具有适当大小的新数组，并将元素从现有数组复制到新数组中来“调整大小”。

```java
String [] listOfCities = new String[3]; // 创建一个大小为 3 的数组。

listOfCities[0] = "New York";

listOfCities[1] = "London"; listOfCities[2] = "Berlin";
```

假设（例如）需要向上述定义的`listOfCities`数组添加一个新元素。要做到这一点，你需要：

1. 创建一个大小为 4 的新数组，
2. 将旧数组现 3 个元素复制到新数组偏移量 0、1 和 2 的位置，
3. 将新元素添加到新数组偏移量 3 的位置。

有多种方法可以上述操作。在 Java 6 之前，最简洁的方法是：

```java
String [] newArray = new String[listOfCities.length + 1];

System.arraycopy(listOfCities, 0, newArray, 0, listOfCities.length);

newArray[listOfCities.length] = "Sydney";
```

从 Java 6 开始，可以使用`Arrays.copyOf`和`Arrays.copyOfRange`方法简单地完成工作：

```java
String[] newArray = Arrays.copyOf(listOfCities, listOfCities.length + 1);

newArray[listOfCities.length] = "Sydney";
```

关于复制数组的其他方法，请参考以下示例。请记住，调整大小时你需要一个与原数组长度不同的数组副本。

## 调整数组大小更好的替代方案

上述调整数组大小的方法有两个主要缺点：

- **效率低下**。增大（或减小）数组涉及复制许多或所有现有数组元素，并分配一个新的数组对象。数组越大，代价就越高。你需要能够更新包含旧数组引用的“活动”变量。
- **另一种替代方案是初始时就创建一个足够大的数组**。这只有在你能够分配数组之前准确确定该大小时才可行。如果不能，那么调整数组大小的问题就会再次出现。
- **另一种替代方案是使用 Java SE 类库或第三方库提供的数据结构类**。例如，Java SE 集合框架提供了`List`、`Set`和`Map` API 的多种实现，具有不同的运行时属性。`ArrayList`类在性能特征上与普通数组最接近（例如 O(N) 查找、O(1) 获取和设置、O(N) 随机插入和删除），同时提供了更高效的调整大小机制，且没有引用更新的问题。

`ArrayList`的调整效率源于其每次调整大小时底层数组的大小。对于典型用例，这意味着你只会偶尔调整大小。当对列表的生命周期进行摊销时，每次插入的调整成本为 O(1)。在调整普通数组时，可能可以使用相同的策略。

## 章节 23.14: 在基本类型和包装类型之间转换数组

有时需要将基本类型转换为包装类型。要转换数组，可以使用流（在 Java 8 及以上版本中）：

```java
Version ≥ Java SE 8

int[] primitiveArray = {1, 2, 3, 4};

Integer[] boxedArray = Arrays.stream(primitiveArray).boxed().toArray(Integer::new);
```

在较低版本中，可以通过遍历基本类型数组并显式将其复制到包装数组来实现：

```java
Version < Java SE 8

int[] primitiveArray = {1, 2, 3, 4};

// (手动复制的实现细节)
```

```java
for (int i = 0; i < a.length; i++) {

    b[i] = a[i];

}
```

注意，对对象数组而非基本类型数组使用此选项将使拷贝填充为指向原始内容的引用，而不是内容的副本。

### Object.clone()

由于 Java 中的数组是对象，因此你可以使用`Object.clone()`。

```java
int[] a = {4, 1, 3, 2};

int[] b = a.clone(); // [4, 1, 3, 2]
```

注意，数组的`Object.clone()`方法执行的是浅拷贝，即它返回一个新数组的引用，该数组与源数组引用相同的元素。

### Arrays.copyOf()

`java.util.Arrays`提供了一种将数组复制到另一个数组的方便方法。以下是基本用法：

```java
int[] a = {4, 1, 3, 2};

int[] b = Arrays.copyOf(a, a.length); // [4, 1, 3, 2]
```

注意`Arrays.copyOf()`还提供了一个重载方法，允许你更改数组类型：

```java
Double[] doubles = {1.0, 2.0, 3.0};

Number[] numbers = Arrays.copyOf(doubles, doubles.length, Number[].class);
```

### System.arraycopy

```java
public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)

// 将数组从指定的源数组的指定位置开始复制到目标数组的指定位置。
```

以下是用法示例：

```java
int[] a = {4, 1, 3, 2};

int[] b = new int[a.length];

System.arraycopy(a, 0, b, 0, a.length); // [4, 1, 3, 2]
```

### Arrays.copyOfRange()

主要用于复制数组的一部分，你也可以如下使用它将整个数组复制到另一个数组：

```java
int[] a = { 4, 1, 3, 2 };

int[] b = Arrays.copyOfRange(a, 0, a.length); // [4, 1, 3, 2]
```

## 节 23.18：数组强制转换

数组是对象，但它们的类型是由所包含对象的类型定义的。因此，不能直接将`A[]`转换为`T[]`，但特定`A[]`中的每个`A`成员都必须转换为`T`对象。泛型示例：

```java
public static <T, A> T[] castArray(T[] target, A[] array) {

    for (int i = 0; i < array.length; i++) {

        target[i] = (T) array[i];

    }

}
```

因此，给定一个`A[]`数组；`T[] target = new T[array.length];` `target = castArray(target, array);` Java SE 提供了方法`Arrays.copyOf(original, newLength, newType)`用于此目的：

```java
Double[] doubles = { 1.0, 2.0, 3.0 };

Number[] numbers = Arrays.copyOf(doubles, doubles.length, Number[].class);
```

## 第 24 章：集合 (Collections)

`java.util`中的集合框架提供了许多用于数据集的泛型类，具有普通数组无法提供的功能。

集合框架包含了`Collection<O>`接口，主要接口包括`List<O>`和`Set<O>`，以及映射集合`Map<K,V>`。`Collections`是根接口，并被许多其他集合框架实现。

## 节 24.1：在循环中从列表中移除项

在循环期间从列表中移除项是棘手的，这是因为列表的索引和长度会发生变化。给定以下列表，这里是一些产生意外结果的示例以及产生正确结果的示例。

```java
List<String> fruits = new ArrayList<String>();

fruits.add("Apple");

fruits.add("Banana");

fruits.add("Strawberry");
```

**错误**

**在迭代语句中移除元素会跳过 "Banana"：** 代码示例只会打印 Apple 和 Strawberry。Banana 被跳过了，因为一旦 Apple 被删除，它会移动到索引 0，但此时同时`i`增加到了 1。

```java
for (int i = 0; i < fruits.size(); i++) {

    System.out.println(fruits.get(i));

    if ("Apple".equals(fruits.get(i))) {

        fruits.remove(i);

    }

}
```

**在增强语句中移除会抛出异常：** 因为在遍历集合的同时修改了它。抛出：`java.util.ConcurrentModificationException`

```java
for (String fruit : fruits) {

    System.out.println(fruit);

    if ("Apple".equals(fruit)) {

        fruits.remove(fruit);

    }

}
```

**正确**

**使用 Iterator 在 while 循环中移除**

```java
Iterator<String> fruitIterator = fruits.iterator();

while (fruitIterator.hasNext()) {

    String fruit = fruitIterator.next();

    System.out.println(fruit);

    if ("Apple".equals(fruit)) {

        fruitIterator.remove();

    }

}
```

`Iterator`接口有一个`remove()`方法。然而，在遍历时使用`List.remove()`会抛出`ConcurrentModificationException`。

**反向迭代**

```java
for (int i = fruits.size() - 1; i >= 0; i--) {

    System.out.println(fruits.get(i));

    if ("Apple".equals(fruits.get(i))) {

        // 注意：反向移除逻辑需要小心处理索引

    }

}
```

**使用“待删除”列表**

```java
ArrayList shouldBeRemoved = new ArrayList<>();

for (String str : currentArrayList) {

    if (condition) {

        shouldBeRemoved.add(str);

    }

}

currentArrayList.removeAll(shouldBeRemoved);
```

**Java 8 及以上**

在 Java 8 中，可以使用以下替代方案。如果移除操作不需要在循环中进行，这些方案更简洁直观。

### 过滤流

列表可以被流化并过滤。可以使用适当的过滤器移除所有不需要的元素。

```java
List<String> filteredList = fruits.stream().filter(p -> !"Apple".equals(p)).collect(Collectors.toList());
```

注意，与此处其他示例不同，此示例产生一个新的`List`实例并保持原始列表不变。

### 移除

如果只需要移除一组项，则可以节省创建流的开销。`fruits.removeAll(p -> "Apple".equals(p));`

## 节 24.2：从现有数据构造集合

### 标准集合

#### Java 集合框架

从单个数据值构造`List`的简单方法是使用`java.util.Arrays.asList`：

```java
List<String> data = Arrays.asList("ab", "bc", "ab", "bc", "cd");
```

所有标准集合实现都提供了接收另一个集合作为参数的构造函数，构造时将所有元素添加到新集合中：

```java
List<String> list = new ArrayList<>(data); // 作为新的添加数据

Set<String> set1 = new HashSet<>(data); // 添加数据保留唯一值

SortedSet<String> set2 = new TreeSet<>(data); // 将添加数据保留唯一值并排序

Set<String> set3 = new LinkedHashSet<>(data); // 添加数据保留唯一值并保持原始顺序
```

#### Google Guava 集合框架

另一个很棒的框架是 Google Guava，它是构造不同类型的 amazing工具类（提供方便的静态方法）。

标准集合 列表和集合：

```java
import com.google.common.collect.Lists;
import com.google.common.collect.Sets;
```

```java
List<String> list1 = Lists.newArrayList("ab", "bc", "cd"); List<String> list2 = Lists.newArrayList(data);
Set<String> set4 = Sets.newHashSet(data);
SortedSet<String> set5 = Sets.newTreeSet("bc", "cd", "ab", "bc");
```

### 集合映射 (Mapping Collections)

#### Java 集合框架

同样对于 map，给定一个`Map<String, Object> map`，可以通过如下构造包含所有元素的新 map：

```java
Map<String, Object> map1 = new HashMap<>(map); SortedMap<String, Object> map2 = new TreeMap<>(map);
```

#### Apache Commons 框架

使用 Apache Commons，你可以使用`ArrayUtils.toMap`中的数组以及`MapUtils.toMap`来创建`Map`：

```java
import org.apache.commons.lang3.ArrayUtils;
...
```

> // 摘自 org.apache.commons.lang.ArrayUtils#toMap Java 文档
> // 创建一个映射颜色的 Map。

```java
Map colorMap = MapUtils.toMap(new String[][]{ {"RED", "#FF0000"}, {"GREEN", "#FF00FF"}, {"BLUE", "#000FF"}} });
```

数组的每个元素必须是`Map.Entry`或包含至少两个元素的数组，其中第一个元素用作键，第二个用作值。

#### Google Guava 集合框架

来自 Google Guava 框架的工具类名为`Maps`：

```java
import com.google.common.collect.Maps;
...
```

```java
void howToCreateMethod(Function<? super K,V> valueFunction,

Iterable<K> keys1,
Set<K> keys2,
SortedSet<K> keys3) {

ImmutableMap<K, V> map1 = toMap(keys1, valueFunction); // 不变的
Map<K, V> map2 = asMap(keys2, valueFunction); // 动态 Map 视图
SortedMap<K, V> map3 = toMap(keys3, valueFunction); // 动态 Map 视图

}
```

**版本 > Java SE 8**

使用`Stream`，`Stream.of("xyz", "abc").collect(Collectors.toList());` 或 `Arrays.stream("xyz", "abc").collect(Collectors.toList());`

## 节 24.3：声明 ArrayList 并添加对象

我们可以创建一个`ArrayList`（遵循`List`接口）：

```java
List listOfFruits = new ArrayList();
```

**版本 > Java SE 5**



`List<String> listOfFruits = new ArrayList<String>();`

版本 > Java SE 7

`List<String> listOfFruits = new ArrayList<>();`

现在，使用`add`方法添加一个`String`：

`listFruits.add("Melon"); listOfFruits.add("Strawberry");`

在示例中，`ArrayList`将包含在索引 0 处的字符串`"Melon"`和索引 1 处的字符串`"Strawberry"`。

我们还可以使用`addAll(Collection<? extends E> c)`方法添加多个元素：

```
List<String> listOfFruitsAndVeggies = new ArrayList<String>();
listOfFruitsAndVeggies.add("Onion");
listOfFruitsAndVeggies.addAll(listOfFruits);
```

现在`"Onion"`被放置于`listOfFruitsAndVeggies`的索引 0，`"Melon"`位于索引 1，`"Strawberry"`位于索引 2。

## 24.4 ：遍历集合

### 遍历 List

`List<String> names = new ArrayList<>(Arrays.asList("Clementine", "Duran", "Mike"));`

版本 ≥ Java 8

`names.forEach(System.out::println);`

如果我们需要并行处理，使用

`names.parallelStream().forEach(System.out::println);` 版本 ≥ Java 8

```
for (String name : names) {
    System.out.println(name);
}
```

版本 < Java 5

```
for (int i = 0; i < names.size(); i++) {
    System.out.println(names.get(i));
}
```

版本 ≥ Java 1.2

```
// 创建一个支持正向和反向遍历的 Iterator
ListIterator<String> listIterator = names.listIterator();

// 正向方向遍历
while(listIterator.hasNext()) {
    System.out.println(listIterator.next());
}

// 当从上述到达最后一个元素后，反向方向遍历
while(listIterator.hasPrevious()) {
    System.out.println(listIterator.previous());
}
```

### 遍历 Set

`Set<String> names = new HashSet<>(Arrays.asList("Clementine", "Duran", "Mike"));`

版本 ≥ Java 8

`names.forEach(System.out::println);`

版本 < Java 5

```
for (Iterator<String> iterator = names.iterator(); iterator.hasNext(); ) { 
  System.out.println(iterator.next());
}

for (String name : names) {
  System.out.println(name);
}
```

< Java SE 5

```
Iterator iterator = names.iterator();
while (iterator.hasNext()) {
  System.out.println(iterator.next());
}
```

### 遍历 Map

```
Map<Integer, String> names = new HashMap<>();
names.put(1, "Clementine");
names.put(2, "Duran");
names.put(3, "Mike");
```

> Java SE 8

```
names.forEach((key, value) -> System.out.println("Key: " + key + " Value: " + value)); // 版本 >= Java SE 5

for (Map.Entry<Integer, String> entry : names.entrySet()) {
  System.out.println(entry.getKey());
  System.out.println(entry.getValue());
}
```

```
// 仅遍历键
for (Integer key : names.keySet()) {
  System.out.println(key);
}
```

```
// 仅遍历值
for (String value : names.values()) {
  System.out.println(value);
}
```

版本 < Java SE 5

```
Iterator entries = names.entrySet().iterator();
while (entries.hasNext()) {
    Map.Entry entry = (Map.Entry) entries.next();
    System.out.println(entry.getKey());
    System.out.println(entry.getValue());
}
```

## 24.5 ：不可变的空集合

有时，使用不可变的空集合是合适的。`Collections`类提供了高效获取此类集合的方法：

`List<String> anEmptyList = Collections.emptyList();`

`Map<Integer, Date> anEmptyMap = Collections.emptyMap();`

`Set<Number> anEmptySet = Collections.emptySet();`

这些方法是泛型的，并自动将返回的集合转换为其赋值的类型。也就是说，例如`emptyList()`的调用可以赋值给任何类型的`List`，`emptySet()`和`emptyMap()`也是如此。

这些方法返回的集合是不可变的，因为如果你尝试调用会更改其内容的方法（`add`，`put`，等），它们将抛出`UnsupportedOperationException`。这些集合主要作为替代品非常有用。

## 24.6 ：子集合 (Sub Collections)

`subList(int fromIndex, int toIndex)`

这里`fromIndex`是包含的，`toIndex`是不包含的。

`List list = new ArrayList();`

`List list1 = list.subList(fromIndex,toIndex);`

- 1. 如果超出范围将抛出`IndexOutOfBoundsException`。
- 2. 对`list1`的操作会影响`list`。这被称为底层集合（backed collections）。
- 3. 如果`fromIndex`大于`toIndex`，将抛出`IllegalArgumentException`。

示例：

```
List<String> list = new ArrayList<>();
list.add("Hello1");
list.add("Hello2");
System.out.println("Before Sublist " + list);
List<String> list2 = list.subList(0, 1);
list2.add("Hello3");
System.out.println("After sublist " + list);
```

输出：

`Before Sublist [Hello1, Hello2]`

`After sublist [Hello1, Hello3, Hello2]`

`subset(fromIndex,toIndex)`

这里`fromIndex`是包含的，`toIndex`是不包含的。

`Set set = new HashSet();`

`Set setI = set.subSet(fromIndex,toIndex);`

返回的集合在尝试插入范围外的元素时抛出`IllegalArgumentException`。

`sub(fromKey,toKey)`

`fromKey`是包含的，`toKey`是不包含的

`Map map = new TreeMap();`

`Map map1 = map.sub(fromKey,toKey);`

如果`fromKey`大于`toKey`将抛出`IllegalArgumentException`。

所有集合支持底层集合意味着对子集合的更改将影响主集合。

## 24.7 ：不可修改集合 (Unmodifiable Collection)

有时暴露内部集合不是一个好做法，因为由于其可变性可能导致代码漏洞。为了提供"只读"集合，java 提供了其不可修改版本。

不可修改集合通常是可变集合的副本，保证了集合不会被更改。尝试修改它将导致`UnsupportedOperationException`。

请注意，集合内部的对象仍然可以被修改。

```
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
```

```
public class MyPojoClass {
    private List<Integer> intList = new ArrayList<>();

    public void addToIntList(Integer value) {
        intList.add(value);
    }

    public List<Integer> getIntList() {
        return Collections.unmodifiableList(intList);
    }
}
```

以下对不可修改集合的尝试将抛出异常：

```
import java.util.List;
public class App {

    public static void main(String[] args) {
        MyPojoClass pojo = new MyPojoClass();
        pojo.addToIntList(42);
        List<Integer> list = pojo.getIntList();
        list.add(69);
    }
}
```

输出：

```
Exception in thread "main" java.lang.UnsupportedOperationException
    at java.util.Collections$UnmodifiableCollection.add(Collections.java:1055)
    at App.main(App.java:12)
```

## 24.8 节：陷阱：并发修改异常

当在迭代集合时，使用了迭代器提供的方法以外的其他方法对集合进行修改，就会发生此异常。例如，我们有一组帽子，并且想要删除所有带有耳朵罩的帽子：

```
List<Hat> hats = new ArrayList<>();
hats.add(new Ushanka()); // 那一个有耳朵罩
hats.add(new Fedora());
hats.add(new Sombrero());

for (Hat hat : hats) {
  if (hat.hasEarFlaps()) {
    hats.remove(hat);
  }
}
```

如果我们运行这段代码，将抛出**ConcurrentModificationException**（并发修改异常），因为代码在迭代集合的同时修改了它。如果多个处理同一个列表的线程中，有一个线程尝试修改集合，而其他线程正在迭代，也可能发生相同的异常。在多线程中并发修改集合是自然现象，但应该使用并发编程工具箱中的常用工具处理，例如同步锁、专为并发修改采用的特殊集合、从初始集合的副本进行修改等。

## 24.9 节：使用 Iterator 从列表中移除匹配的项

上面我注意到一个在循环内部从列表中删除项的示例，我想到了另一个使用`Iterator`接口的示例，这在这次可能会派上用场。
这是一个技巧的演示，当处理列表中想要丢弃的重复项时，这个技巧可能会非常有用。

注意：这仅是"在循环中从列表中移除项"的部分。
现在让我们照常定义我们的列表：

```
String[] names = {"James","Smith","Sonny","Huckle","Finn","Allan"};
List<String> nameList = new ArrayList<>();
// 从数组创建列表
nameList.addAll(Arrays.asList(names));

String[] removeNames = {"Huckle","Berry"};
List<String> removeList = new ArrayList<>();
// 从数组创建列表
removeList.addAll(Arrays.asList(removeNames));
```

以下方法接收两个集合，并执行移除`nameList`中与`removeList`元素匹配的元素的魔术。

```
private static void removeNames(Collection<String> collection1, Collection<String> collection2) {
  Iterator<String> iterator = collection1.iterator();
  // 当集合包含项时进行循环
  while (collection2.contains(iterator.next())) {
    iterator.remove(); // 移除当前项
  }
}
```

调用方法并传入`nameList`和`removeList`遵循`removeNames(nameList, removeList);`将产生以下输出：

移除前的列表：`James Smith Sonny Huckle Finn Allan`
移除后的列表：`James Finn Allan`

这是一个`Collections`的简单整洁用法，对于处理列表中的重复元素可能有用。

## 24.10 节：合并列表

以下方法可以用于合并列表且不修改源列表：

第一种方法：代码行较多，但易于理解。

```
List<String> newList = new ArrayList<>();
newList.addAll(listOne);
newList.addAll(listTwo);
```

第二种方法：只有一行，但可读性较差。

```
List<String> newList = new ArrayList<>(listOne);
newList.addAll(listTwo);
```

第三种方法：需要 Apache commons-collections 库。

```
List<String> newList = ListUtils.union(listOne, listTwo);
```

使用 Java SE 8 Streams 可以实现：

```
List<String> newList = Stream.concat(listOne.stream(), listTwo.stream()).collect(Collectors.toList());
```

## 24.11 节：使用 Iterator 或 for-each 创建自己的 Iterable

为了确保我们的集合可以使用迭代器或 for-each 循环迭代，我们必须注意以下步骤：
1. 我们想要迭代的内容必须是可迭代的并暴露`iterator()`方法。
2. 通过重写`next()`和`remove()`来设计`java.util.Iterator`。

我在下方添加了一个简单的泛型实现，使链表变得可迭代。

```
package org.algorithms.linkedlist;

import java.util.Iterator;
import java.util.NoSuchElementException;

public class LinkedList<T> implements Iterable<T> {

  Node<T> head, current;

  private class Node<T> {
    T data;
    Node<T> next;

    Node(T data) {
      this.data = data;
    }
  }

  public LinkedList(T data) {
    head = new Node<>(data);
  }

  @Override
  public Iterator<T> iterator() {
    return new LinkedListIterator();
  }

  private class LinkedListIterator implements Iterator<T> {
    Node<T> node = head;

    @Override
    public boolean hasNext() {
      return node != null;
    }

    @Override
    public T next() {
      if (!hasNext()) {
        throw new NoSuchElementException();
      }
      T data = node.data;
      node = node.next;
      return data;
    }
  }
}
```



```
if (!hasNext()) {
  throw new NoSuchElementException();
}
Node<T> prevNode = node;
node = node.next;
return prevNode.data;
}
@Override
public void remove() {
  throw new UnsupportedOperationException("Removal logic not implemented");
}
}
}
class App {
  public static void main(String[] args) {
    LinkedList<Integer> list = new LinkedList<>(1);
    list.add(2);
    list.add(4);
    // ... (省略部分)
  }
}
```

*(注：由于原文文本在代码块处不完整，此处翻译保持了代码逻辑的完整性)*

```java
new User(25L, "B"),
new User(28L, ""));
```

`Collections.sort(users);`
`System.out.print(users);` // [B:25, C:28, A:33]

然而，假设我们想要按照名称而不是 ID 来对 `User` 对象进行排序。或者，假设我们无法修改类使其使其 `Comparable` 接口。这就是带有 `Comparator` 的 `sort` 方法大显用场的地方：

```java
Collections.sort(users, new Comparator<User>() { @Override
/* 根据名称对 'User' 对象排序。 */ public int compare(
User left, User right) {
    return left.username.compareTo(right.username);
}
});
System.out.print(users);
// [A:33, B:25, C:28]
```

版本 ≥ Java SE 8

在 Java 8 中，你使用 lambda 表达式代替匿名类。后者可以简化为单行：

```java
Collections.sort(users, (l, r) -> l.username.compareTo(r.username));
```

此外，Java 8 在 `List` 接口上添加了默认 `sort` 方法，进一步简化了排序。

```java
users.sort((l, r) -> l.username.compareTo(r.username));
```

# 第 25.2 节：将整数列表转换为字符串列表

```java
List<Integer> nums = Arrays.asList(1, 2, 3);
List<String> strings = nums.stream()
    .map(Object::toString)
    .collect(Collectors.toList());
```

即：

1. 从列表创建一个流（stream）
2. 使用 `Object::toString` 映射每个元素
3. 使用 `Collectors.toList()` 将字符串值收集到一个列表中

# 第 25.3 节：实现 List 的类 - 优缺点

`List` 接口由不同的类实现。每个类都有自己的实现方式，采用不同的策略并提供不同的优缺点。

## 实现 List 的类

这些是 Java SE 8 中实现 `java.util.List` 接口的所有公共类：

1. 抽象类：
   - `AbstractList`
   - `AbstractSequentialList`

2. 具体实现类：
   - `ArrayList`
   - `AttributeList`
   - `CopyOnWriteArrayList`
   - `LinkedList`
   - `RoleList`
   - `RoleUnresolvedList`
   - `Stack`
   - `Vector`

## 各实现在时间复杂度方面的优缺点

```java
public class ArrayList<E>
extends AbstractList<E>
implements List<E>, RandomAccess, Cloneable, Serializable
```

`ArrayList` 是 `List` 接口的一种可动态大小数组实现。通过将列表存储在数组中，`ArrayList` 除了实现 `List` 接口的方法外，提供了操作数组大小的方法。

初始化大小为 100 的 Integer `ArrayList`：

```java
List<Integer> myList = new ArrayList<Integer>(100); // 构建一个指定初始容量的空列表。
```

- 优点：
  `size`、`isEmpty`、`get`、`set`、`iterator` 和 `listIterator` 操作在常时间内运行。因此，获取和设置 `List` 的每个元素代价相同：

```java
int e1 = myList.get(0); 
int e2 = myList.get(10); // 都是相同的常数代价 => O(1)
myList.set(2,10);
```

- 缺点：
  由于使用数组（静态结构）实现，当超过数组大小时添加元素会有巨大的代价，因为需要对整个数组进行重新分配。然而，根据文档描述：
  `add` 操作在分摊常时间内运行，即 n 个元素需要 O(n) 时间。
  移除一个元素需要 O(n) 时间。

# AttributeList

即将更新

# CopyOnWriteArray

即将更新

# LinkedList

```java
public class LinkedList<E>
extends AbstractSequentialList<E>
implements List<E>, Deque<E>, Cloneable, Serializable
```

`LinkedList` 由双向链表实现实现，这是一种链式数据结构，由一组顺序连接的称为节点组成。

```java
LinkedList<Integer> myList = new LinkedList<Integer>(); // 构建一个空列表。
```

- 优点：
  在列表头部或尾部添加或删除元素是常数时间的。

```java
myList.add(10); 
myList.add(0,2); // 常数时间 => O(1) 
myList.remove();
```

- 缺点：
  根据文档描述：
  对列表进行索引的操作将从开始或结束遍历列表，取决于哪个离指定索引更近。

操作例如：

```java
myList.get(10); 
myList.add(11,25); // 最坏情况在 O(n/2) 内完成 
myList.set(15,35);
```

# RoleList

即将更新

# RoleUnresolvedList

即将更新

# Stack

即将更新

# Vector

即将更新

# 第 25.4 节：寻找两个列表之间的共同元素

假设你有两个列表：A 和 B，你需要找到同时存在这两个列表的元素。

你只需要调用 `List.retainAll()` 方法即可实现。

示例：

```java
public static void main(String[] args) {
    List<Integer> numbersA = new ArrayList<>();
    List<Integer> numbersB = new ArrayList<>();
    numbersA.addAll(Arrays.asList(new Integer[] { 1, 3, 4, 7, 5, 2 }));
    numbersB.addAll(Arrays.asList(new Integer[] { 3, 5, 8 }));
    numbersA.retainAll(numbersB);
    System.out.println(numbersA); // 输出: [3, 5]
}
```

这是因为从数组列表中删除元素时经常会发生位移。

可以如下所示创建一个 `ArrayList`：

```java
List<T> myArrayList = new ArrayList<>();
```

其中 `T`（泛型）是存储在 `ArrayList` 内部的类型。`ArrayList` 的类型可以是任何 `Object`。该类型不能是基本类型（请使用它们的包装类）。

要向 `ArrayList` 中添加元素，请使用 `add()` 方法：

```java
myArrayList.add(element);
```

或者向中间索引添加项：

```java
myArrayList.add(index, element); // 元素的索引应该是一个 int（从 0 开始）
```

要从 `ArrayList` 中删除元素，请使用 `remove()` 方法：

```java
myArrayList.remove(element);
```

或者从特定索引删除元素：`myArrayList.remove(index);` // 元素的索引应该是一个 int（从 0 开始）

# 第 25.9 节：创建列表

### 为你的列表指定类型

要创建一个列表，你需要一个类型（任何类，例如 `String`）。这是你的 `List` 的类型。`List` 将只存储指定类型的对象。

```java
List<String> strings;
```

可以存储 `"string"`、`"hello world"`、`"goodbye"` 等，但不能存储 `9.2`：

```java
List<Double> doubles;
```

### 初始化你的列表

如果你尝试向上述列表添加内容，你将得到 `NullPointerException`，因为 `strings` 和 `doubles` 都等于 `null`！

初始化列表有两种方法：

**选项 1：使用实现 `List` 的类**

`List` 是一个接口，这意味着它没有构造函数，而是类必须重写的方法。`ArrayList` 是最常用的 `List`，尽管 `LinkedList` 也很常见。因此，我们这样初始化列表：

```java
List<String> strings = new ArrayList<String>();
```

或者

```java
List<String> strings = new LinkedList<String>(); Version >= Java SE 7
```

从 Java SE 7 开始，你可以使用菱形操作符：

```java
List<String> strings = new ArrayList<>();
```

或者

```java
List<String> strings = new LinkedList<>();
```

# 选项 2：使用 Collections 类

`Collections` 类提供了两个实用的方法可以在 `List` 变量的情况下创建列表：

- `emptyList()`: 返回一个空列表。
- `singletonList(T)`: 创建一个 `T` 类型的列表并添加指定的元素。
- 还有一个使用现有 `List` 填充数据的方法：
- `addAll(L, T...)`: 将所有指定的元素添加到作为第一个参数传递的列表中。

示例：

```java
import java.util.List; import java.util.Collections; List<Integer> l = Collections.emptyList(); List<Integer> l1 = Collections.singletonList(42);
Collections.addAll(l1, 1, 2, 3);
```

# 第 25.10 节：位置访问操作

`List` API 有八个方法用于位置访问操作：

```java
add (T type)
add(int index, T type)
remove(Object o)
remove(int index)
get(int index)
set(int index, E element)
int indexOf(Object o)
int lastIndexOf(Object o)
```

所以，如果我们有一个列表：

```java
List<String> strings = new ArrayList<String>();
```

如果我们想向它添加字符串 `"Hello world!"` 和 `"Goodbye world!"`，这样做：

```java
strings.add("Hello world!"); strings.add("Goodbye world!");
```

我们的列表将包含这两个元素。现在如果我们想在列表开头添加 `"Program starting!"`。我们会这样做：

```java
strings.add(0, "Program starting!");
```

**注意：第一个元素的索引为 0。**

现在，如果我们想删除 `"Goodbye world!"` 这一行，我们可以这样做：

```java
strings.remove("Goodbye world!");
```

如果我们想删除第一行（在这种情况下将是 `"Program starting!"`），我们可以这样做：

```java
strings.remove(0);
```

注意：

1. 添加和删除列表元素会修改列表，如果列表正在并发迭代，这可能会导致 `ConcurrentModificationException`。
2. 添加和删除元素的时间复杂度为 O(1) 或 O(N)，取决于列表类、使用的方法，以及你是在列表的开头、结尾还是中间添加/删除元素。

为了获取指定位置的列表，你可以使用 `List` API 的 `E get(int index);` 方法。例如：

```java
strings.get(0);
```

将返回列表的第一个元素。

你可以使用 `List` API 的 `set(int index, E element)` 方法替换指定位置上的任何元素。例如：

```java
strings.set(0, "new element");
```

为了找到元素的索引，你可以使用 `List` API 的 `indexOf(Object o)` 方法。例如：

```java
strings.indexOf("Hello world!");
```

为了找到元素的最后一个索引，你可以使用 `List` API 的 `lastIndexOf(Object o)` 方法。例如：

```java
strings.lastIndexOf("Goodbye world!");
```

执行此 `set` 后将是：

`set = []`

检查元素是否属于 `Set`：

可以使用 `contains()` 方法检查元素是否存在于集合中：

```java
set.contains(0); // 如果指定的对象是集合中的元素，则返回 true
```

输出：`False`

检查 `Set` 是否为空：

可以使用 `isEmpty()` 方法检查 `Set` 是否为空：

```java
set.isEmpty(); // 如果集合没有元素，则返回 true
```

输出：`True`

从 `Set` 中移除元素：

```java
set.remove(0); // 从集合中移除指定对象的首次出现项
```

检查 `Set` 的大小：

```java
set.size(); // 返回集合中元素的数量
```

输出：`0`

## 第 26.3 节：Set 的类型和用法

通常情况下，`set`（集合）是一种存储唯一值的集合类型。唯一性由 `equals()` 和 `hashCode()` 方法决定。排序由集合的类型决定。

## HashSet - 随机排序

版本 ≥ Java SE 7

```java
Set<String> set = new HashSet<>(); set.add("Banana");
set.add("Banana"); set.add("Apple");
set.add("Strawberry");
```

// Set 元素: ["Strawberry", "Banana", "Apple"]

## LinkedHashSet - 插入顺序

版本 ≥ Java SE 7

```java
Set<String> set = new LinkedHashSet<>(); set.add("Banana");
set.add("Banana");
set.add("Apple");
set.add("Strawberry");
```

// Set 元素: ["Banana", "Apple", "Strawberry"]

## TreeSet - 通过 compareTo 或 Comparator

版本 >= Java SE 7

```java
Set<String> set = new TreeSet<>(); set.add("Banana");
set.add("Apple");
set.add("Strawberry");
```

// Set 元素: ["Apple", "Banana", "Strawberry"]

版本 >= Java SE 7

```java
Set<String> set = new TreeSet<>((string1, string2) ->
string2.compareTo(string1));
set.add("Banana");
set.add("Banana");
set.add("Apple");
set.add("Strawberry");
```



# 第 26.4 节：从现有的 Set 创建列表

使用新的 `List`：

```java
List<String> list = new ArrayList<String>(listOfElements);
```

使用 `List.addAll()` 方法：

```java
Set<String> set = new HashSet<String>();
set.add("foo");
set.add("boo");

List<String> list = new ArrayList<String>();
list.addAll(set);
```

使用 Java 8 Stream API：

```java
List<String> list = set.stream().collect(Collectors.toList());
```

# 第 26.5 节：使用 Set 去重

假设你有一个集合元素，你想创建另一个包含相同元素但去除了所有重复元素的集合：

```java
Collection<Type> Duplicates = new HashSet<Type>(elements);
```

示例：

```java
List<String> names = new ArrayList<>(Arrays.asList("John", "Marco", "Jenny", "Emily", "Jenny", "Emily", "John"));
Set<String> noDuplicates = new HashSet<>(names);
System.out.println("noDuplicates = " + noDuplicates);
```

输出：`noDuplicates = [Marco, Emily, John, Jenny]`

# 第 26.6 节：带值的声明 HashSet

你可以创建一个继承自 `HashSet` 的新类：

```java
Set<String> h = new HashSet<String>() { 
    add("a");
    add("b");
};
```

一行代码解决方案：

```java
Set<String> h = new HashSet<String>(Arrays.asList("a", "b"));
```

使用 Guava：`Sets.newHashSet("a", "b", "c")`

使用 Streams：`Set<String> set3 = Stream.of("a", "b", "c").collect(toSet());`

# 第 27 章：List vs Set

`List` 和 `Set` 集合在顶层上的区别是什么？以及在 Java 中何时该使用 `List`，何时该使用 `Set`？

## 第 27.1 节：List vs Set

```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;
import java.util.Set;
```

```java
public class SetAndListExample
{
    public static void main(String[] args) {
        System.out.println("List example ...."); 
        List list = new ArrayList<>();
        list.add("1");
        list.add("2");
        list.add("3");
        list.add("4");
        list.add("1");
        for (String temp : list) {
            System.out.println(temp);
        }

        System.out.println("Set example ...."); 
        Set<String> set = new HashSet<String>();
        set.add("2");
        set.add("3");
        set.add("4");
        set.add("1");
        set.add("2");
        set.add("5");
        for (String temp : set) {
            System.out.println(temp);
        }
    }
}
// 输出示例 .... 1 2 3 4 1 Set example .... 3 2 1 5 4
```

# 第 28 章：Maps

`java.util.Map` 接口表示键与值之间的映射关系。`Map` 不能包含重复的键；每个键最多可以映射到一个值。

由于 `Map` 是一个接口，你需要实例化该接口才能使用它；有几种 `Map` 的类，最常用的是 `java.util.HashMap` 和 `java.util.TreeMap`。

## 第 28.1 节：高效遍历 Map 条目

本节提供了十种唯一示例实现的代码和基准测试，用于遍历 `Map<Integer, Integer>` 的条目并生成 `Integer` 值的和。所有示例的算法复杂度均为 Θ(n)，但基准测试对于洞察哪些实现在“真实世界”环境中更高效仍具有价值。

1. 使用 `Iterator` 配合 `Map.Entry` 的实现

```java
Iterator<Map.Entry<Integer, Integer>> it = map.entrySet().iterator();
while (it.hasNext()) {
    Map.Entry<Integer, Integer> pair = it.next();
    sum += pair.getKey() + pair.getValue();
}
```

2. 使用 `for` 循环配合 `Map.Entry` 的实现

```java
for (Map.Entry<Integer, Integer> pair : map.entrySet()) {
    sum += pair.getKey() + pair.getValue();
}
```

3. 使用 `forEach` 方法的实现

```java
map.forEach((key, value) -> {
    sum += key + value;
});
```

4. 使用 `keySet()` 的实现

```java
for (Integer key : map.keySet()) {
    sum += key + map.get(key);
}
```

5. 使用 `entrySet()` 的实现

```java
for (Map.Entry<Integer, Integer> entry : map.entrySet()) {
    sum += entry.getKey() + entry.getValue();
}
```

6. 使用 Stream API 的实现

```java
sum = map.entrySet().stream()
          .mapToInt(entry -> entry.getKey() + entry.getValue())
          .sum();
```

7. 使用并行 Stream API 的实现

```java
sum = map.entrySet().parallelStream()
          .mapToInt(entry -> entry.getKey() + entry.getValue())
          .sum();
```

### 性能测试

| 实现 | 100 个元素 (ns) | 1000 个元素 (ns) | 10000 个元素 (ns) | 100000 个元素 (ns) |
| :--- | :--- | :--- | :--- | :--- |
| 1. Iterator | 380 | 309 | 308 | 1184.7 |
| 2. for-each | 391 | 387 | 380 | 1191.7 |
| 3. forEach | 410 | 408 | 411 | 1205.8 |
| 4. keySet() | 424 | 423 | 417 | 1206.8 |
| 5. entrySet() | 463 | 435 | 436 | 1485.8 |
| 6. for Iterator | 510 | 507 | 507 | 1540.2 |
| 7. Stream.forEach | 524 | 516 | 512 | 1593.3 |
| 8. Stream.forEach parallel | 555 | 544 | 544 | 1706.6 |
| 9. MapIterator | 796 | 790 | 791 | 3289.8 |
| 10. forEach | 816 | 813 | 811 | 3712.5 |

**环境：** Windows 8 64-bit, Intel i7-3.60GHz, 16 GB

| x: Map 大小 / f(x): 基准分 (µ/op) | 100 | 600 | 1100 | 1600 | 2100 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 10 | 0.309 | 1.971 | 4.147 | 8.147 | 10.473 |
| 6 | 0.372 | 2.190 | 4.470 | 8.322 | 10.531 |
| 1 | 0.405 | 2.237 | 4.616 | 8.645 | 10.707 |
| 测试 2 | 0.376 | 2.267 | 4.809 | 8.403 | 10.910 |
| f(x) 7 | 0.473 | 2.448 | 5.668 | 9.790 | 12.125 |
| 9 | 0.565 | 2.830 | 5.952 | 13.22 | 16.965 |
| 4 | 0.808 | 5.012 | 8.813 | 13.939 | 17.407 |
| 5 | 0.81 | 5.104 | 8.533 | 14.064 | 17.422 |
| 8 | 5.173 | 12.499 | 17.351 | 24.671 | 30.403 |

## 第 28.2 节：HashMap 的用法

`HashMap` 是 `Map` 接口的实现，提供了一种以键值对（Key-Value pairs）存储数据的结构。

1. 声明 `HashMap`：`Map<KeyType, ValueType> myMap = new HashMap<KeyType, ValueType>();`

`KeyType` 和 `ValueType` 必须是 Java 中有效的类型，例如 `String`、`Integer`、`Float` 或任何自定义类（如 `Employee`、`Student` 等）。例如：`Map<String,Integer> myMap = new HashMap<String,Integer>();`

2. 向 `HashMap` 中存入值。

要向 `HashMap` 中存入值，必须在 `HashMap` 对象上调用 `put` 方法，并将 Key 和 Value 作为参数传递。`myMap.put("key1", 1); myMap.put("key2", 2);` 如果你使用 `Map` 中已存在的 Key 调用方法，该方法将覆盖其值并返回旧值。

3. 从 `HashMap` 获取值。

要从 `HashMap` 中获取值，你必须调用 `get` 方法，并将 Key 作为参数传递。`myMap.get("key1"); //返回 1 (Integer 类)` 如果你传递的 key 在 `HashMap` 中不存在，此方法将返回 `null`。

4. 检查 Key 是否在 Map 中。

`myMap.containsKey(varKey);`

5. 检查 Value 是否在 Map 中。

`myMap.containsValue(varValue);` 上述方法将根据键、值是否存在于 `Map` 中返回布尔值 `true` 或 `false`。

## 第 28.3 节：使用 Java 8 中 Map 的默认方法

使用 Java 8 `Map` 接口中引入的默认方法的示例。

1. 使用 `getOrDefault`：返回 key 映射的值；如果 key 不存在，则返回默认值

```java
Map <Integer, String> map = new HashMap<>();
map.put(1, "First element");
map.get(1); // => First element
map.get(2); // => null
map.getOrDefault(2, "Default element"); // => Default element
```

2. 使用 `forEach`：允许对每个 `Map.Entry` 执行在 `'action'` 中指定的操作

```java
Map <Integer, String> map = new HashMap<Integer, String>(); 
map.put(1, "one");
map.put(2, "two");
map.put(3, "three");
map.forEach((key, value) -> System.out.println("Key: "+key+" :: Value: "+value));
// Key: 1 :: Value: one // Key: 2 :: Value: two // Key: 3 :: Value: three
```

3. 使用 `replaceAll`：仅当 key 存在时才会替换为新值

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.replaceAll((key,value)->value+10); //john=30, peter=50
```

4. 使用 `putIfAbsent`：如果 key 不存在或映射为 `null`，则将键值对添加到 `Map` 中

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.putIfAbsent("kelly", 50); //john=20, paul=30, peter=40
```

5. 使用 `remove`：如果 key 与给定值关联，则删除该 key

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.remove("peter"); //john=20, paul=30
```

6. 使用 `replace`：如果 key 存在，则用新值替换值。如果 key 不存在，则什么都不做。

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.replace("peter", 50); //john=20, peter=50
```

7. 使用 `compute`：此方法在 `Map` 中添加一个 entry。key 是指定的，而值是函数应用的结果

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.compute("kelly", k->map.get("john")+10); //john=20, paul=30, kelly=30
```

8. 使用 `computeIfAbsent`：此方法添加或修改 `Map` 中存在的 entry。如果该 key 不存在，则什么都不做。

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.computeIfAbsent("kelly", k->map.get("john")+10); //john=20, paul=30, kelly=0
```

9. 使用 `computeIfPresent`：如果 key 存在，则用新计算的值替换值。

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.computeIfPresent("peter", (k,v)->v+10); //john=20, paul=30, peter=50
```

10. 使用 `merge`



如果`key`不存在或`value`为`null`，则将键值对添加到`Map`。如果`key`存在，则用新计算的值替换值。如果新值为`null`，则从`Map`中移除`key`

```java
Map <String, Integer> map = new HashMap<>();
map.put("john", 20);
map.put("paul", 30);
map.put("peter", 40);
map.merge("kelly", 50, (k,v)->map.get("john")+10); //john=20, paul=30, kelly=50
```

## 28.4: 遍历 Map

`Maps`提供了方法，让你作为集合访问`Map`的键、值或键值对。你可以遍历这些集合。例如以下`Map`：

```java
Map<String, Integer> repMap = new HashMap<>();
repMap.put("Jon Skeet", 927654);
repMap.put("Balusc", 708826);
repMap.put("Darin Dimitrov", 715567);
```

遍历`map`的键：

```java
for (String key : repMap.keySet()) { System.out.println(key); }
```

输出：

```
Darin Dimitrov
Jon Skeet
Balusc
```

`keySet()`将`map`的键作为`Set`提供。`Set`不能包含重复的值。遍历`Set`会依次产生每个`key`。`HashMap`是无序的，因此在此示例中，`key`以任何顺序返回。

遍历`map`的值：

```java
for (Integer value : repMap.values()) { System.out.println(value); }
```

输出：

```
715567
927654
708826
```

`values()`将`map`的值作为`Collection`提供。遍历`Collection`会依次产生每个值。同样，值可能会按顺序返回。

同时遍历键和值：

```java
for (Map.Entry<String, Integer> entry : repMap.entrySet()) { System.out.printf("%s = %d\n", entry.getKey(), entry.getValue()); }
```

输出：

```
Darin Dimitrov = 715567
Jon Skeet = 927654
Balusc = 708826
```

`entrySet()`返回`Map.Entry`对象集合。`Map.Entry`提供了对每个`entry`键值的访问。

## 第 28.5 节：合并、组合和组合 Maps

使用`putAll`将一个`map`的所有成员放入另一个`map`中。`map`中已存在的键将其对应值将被覆盖。

```java
Map<String, Integer> numbers = new HashMap<>();
numbers.put("One", 1);
numbers.put("Three", 3);

Map<String, Integer> other_numbers = new HashMap<>();
other_numbers.put("Two", 2);
other_numbers.put("Three", 4);

numbers.putAll(other_numbers);
```

这在`numbers`中产生了以下映射：

```
"One" -> 1
"Two" -> 2
"Three" -> 4 //旧值 3 被值 4 覆盖
```

如果你想合并值而不是覆盖它们，可以使用 Java 8 引入的`Map.merge`，它使用用户提供的`BiFunction`来合并重复的键。`merge`作用于单个键值，因此你将需要使用循环或`Map.forEach`。这里我们对重复的键拼接字符串：

```java
for (Map.Entry<String, Integer> e : other_numbers.entrySet())
    numbers.merge(e.getKey(), e.getValue(), Integer::sum);

// 或者代替上面的循环
other_numbers.forEach((k, v) -> numbers.merge(k, v, Integer::sum));
```

如果你想强制执行没有重复键的约束，可以使用会抛出`AssertionError`的`merge`函数`forEach`：

```java
mapA.forEach((k, v) ->
    mapB.merge(k, v, (v1, v2) -> {
        throw new AssertionError("duplicate values for key: "+k);
    }));
```

组合`Map<X,Y>`和`Map<Y,Z>`以得到`Map<X,Z>`。如果你想组合两个映射，可以如下操作：

```java
Map<String, Integer> map1 = new HashMap<String, Integer>();
map1.put("key1", 1);
map1.put("key2", 2);
map1.put("key3", 3);
```

```java
Map<String, Double> map3 = new HashMap<String, Double>();
map1.forEach((key,value)->map3.put(key,map2.get(value)));
```

这产生了以下映射：

- `"key1"` -> 1.0
- `"key2"` -> 2.0
- `"key3"` -> 3.0

## 28.6: 添加多个项

我们可以使用`put(K key,V value)`：将指定的值与指定的映射关联起来（可选操作）。如果`map`之前包含该键的映射，则旧值将被指定的值替换。

```java
String currentVal;
Map<Integer, String> map = new TreeMap<>();

currentVal = map.put(1, "First element.");
System.out.println(currentVal); // 将打印 null

currentVal = map.put(2, "Second element.");
System.out.println(currentVal); // 将再次打印 null

map.put(2, "This will replace 'Second element'");
System.out.println(currentVal); // 将打印 Second element.
System.out.println(map.size()); // 将打印 2，因为 2 被替换了。
```

```java
Map<Integer, String> map2 = new HashMap<>();
map2.put(2, "Element 2");
```

```java
map2.put(3, "Element 3");
map.putAll(map2);
System.out.println(map.size());
```

输出：

```
3
```

要添加许多项，你可以使用如下内部类：

```java
Map<Integer, String> map = new HashMap<>() {
    // 现在这是一个带有无名实例的匿名内部类
    {
        put(5, "high");
        put(4, "low");
        put(1, "too slow");
    }
};
```

请记住，创建匿名内部类并不总是高效的，并且在可能的情况下导致内存泄漏，请使用初始化器块代替：

```java
static Map<Integer, String> map = new HashMap<>();
```

```java
static {
    // 现在没有创建内部类了，所以我们可以避免内存泄漏
    put(5, "high");
    put(4, "low");
    put(1, "too slow");
}
```

上面的示例使`map`变为静态的。它也可以通过删除所有`static`出现的地方在非静态上下文中使用。此外，大多数实现都支持`putAll`，它可以像这样将一个`map`中的所有条目添加到另一个中：`another.putAll(one);`

## 28.7: 创建和初始化 Maps

### 介绍

`Maps`存储键/值对，其中每个键都有一个关联的值。给定一个特定的键，`map`可以非常快速地查找关联的值。`Maps`也称为关联数组（associate array），是一种以键值对形式存储数据的对象。在 Java 中，`maps`使用`Map`接口表示，该接口不是`collection`接口的扩展。

#### 方式 1:

```java
/*J2SE < 5.0*/
Map map = new HashMap<>();
map.put("name", "A");
map.put("address", "Malviya-Nagar");
map.put("city", "Jaipur");
System.out.println(map);
```

#### 方式 2:

```java
/*J2SE 5.0+ style（使用泛型）*/
Map<String, Object> map = new HashMap<>();
map.put("name", "A");
map.put("address", "Malviya-Nagar");
System.out.println(map);
```

#### 方式 3:

```java
Map<String, Object> map = new HashMap<>() {{
    put("name", "A");
    put("address", "Malviya-Nagar");
    put("city", "Jaipur");
}};
System.out.println(map);
```

#### 方式 4:

```java
Map<String, Object> map = new TreeMap<String, Object>();
map.put("name", "A");
map.put("address", "Malviya-Nagar");
map.put("city", "Jaipur");
System.out.println(map);
```

#### 方式 5:

```java
//Java 8
final Map<String, String> map = Arrays.stream(new String[][] {
    { "name", "A" },
    { "address", "Malviya-Nagar" },
    { "city", "Jaipur" }
}).collect(Collectors.toMap(m -> m[0], m -> m[1]));
System.out.println(map);
```

#### 方式 6: 在函数外部初始化`map`

```java
final static Map<String, String> map;
static {
    map = new HashMap<String, String>();
    map.put("a", "b");
    map.put("c", "d");
}
```

#### 方式 7: 创建不可变的键值 map

```java
Map<String, String> singletonMap = Collections.singletonMap("key", "value");
```

请注意，这种`map`是无法修改的。任何修改`map`的尝试将导致抛出`UnsupportedOperationException`。

## 28.8: 检查键是否存在

```java
Map<String, String> map = new HashMap<>();
if (map.containsKey("key")) {
    System.out.println("key exists");
}
```

## 28.9: 添加元素

```java
Map<String, String> map = new HashMap<>();
map.put("key1", "value1");
System.out.println(map);
```

## 28.10: 清空 map

```java
Map<String, String> map = new HashMap<>();
map.clear();
System.out.println(map.size());
```

## 28.11: 使用自定义对象作为键

```java
class MyKey {
    private String name;
    MyKey(String name) {
        this.name = name;
    }

    @Override
    public boolean equals(Object obj) {
        if (obj instanceof MyKey) {
            return this.name.equals(((MyKey)obj).name);
        }
        return false;
    }

    @Override
    public int hashCode() {
        return this.name.hashCode();
    }
}
```

大小差异（`HashMap` vs `WeakHashMap`）：

在`HashMap`对象上调用`size()`方法将返回相同的键值对数量。只有在显式地对`HashMap`对象调用`remove()`方法时，`size`才会减少。

由于垃圾回收器可能会丢弃键，`WeakHashMap`的行为可能就像有一个未知线程在静默删除节点。因此，`size`方法可能会随着时间的推移返回更小的值。所以，`WeakHashMap`中，`size`的减少是自动发生的。

## 第 31 章：SortedMap

排序`Map`简介。

## 第 31.1 节：排序 Map 简介

要点：

- `SortedMap`接口继承`Map`。
- 条目按键的升序顺序维护。

## Sorted Map 的方法：

- `Comparator comparator()`
- `Object firstKey()`
- `SortedMap headMap(Object end)`
- `Object lastKey()`
- `SortedMap subMap(Object start, Object end)`
- `SortedMap tailMap(Object start)`

## 示例

```java
public static void main(String args[]) {
    // 创建一个 hash map
    TreeMap tm = new TreeMap();

    // 将元素放入 map
    tm.put("Zara", new Double(3434.34));
    tm.put("Mahnaz", new Double(123.22));
    tm.put("Ayan", new Double(1378.00));
    tm.put("Daisy", new Double(99.22));
    tm.put("Qadir", new Double(19.08));

    // 获取一组条目
    Set set = tm.entrySet();
    // 获取一个迭代器
    Iterator i = set.iterator();

    // 显示元素
    while(i.hasNext()) {
        Map.Entry entry = (Map.Entry)i.next();
        System.out.print(entry.getKey() + ": ");
        System.out.println(entry.getValue());
    }
    System.out.println();

    // 向 Zara 的账户存入 1000
    double balance = ((Double)tm.get("Zara")).doubleValue();
    tm.put("Zara", new Double(balance + 1000));
    System.out.println("Zara's new balance: " + tm.get("Zara"));
}
```

## 第 32 章：TreeMap and TreeSet

`TreeMap`和`TreeSet`是 Java 1.2 中引入的基础 Java 集合。`TreeMap`是一个可变的、有序的`Map`实现。同样，`TreeSet`是一个可变的、有序的`Set`实现。`TreeMap`使用红黑树实现，提供了 O(log n) 的访问时间。`TreeSet`是使用带有占位值的`TreeMap`实现的。这两个集合都不是线程安全的。

## 第 32.1 节：简单 Java 类型的 TreeMap

首先，我们创建一个空的`map`，并向其中插入元素：



# 第 32 章：TreeMap 与 TreeSet

## 第 32.1 节：简单 Java 类型的 TreeMap

首先，我们创建一个空的 map，并向其中插入一些元素：

```
Version ≥ Java SE 7
TreeMap<Integer, String> tree = new TreeMap<>();
Version ≥ Java SE 7
TreeMap<Integer, String> tree = new TreeMap<Integer, String>();

tree.put(10, "ten");
tree.put(4, "four");
tree.put(1, "one");
tree.put(12, "twelve");
```

一旦我们在 map 中有了几个元素，就可以执行一些操作：

```
System.out.println(tree.firstEntry()); // 输出 1=one
System.out.println(tree.lastEntry()); // 输出 12=twelve
System.out.println(tree.size()); // 输出 4，因为 map 中有 4 个元素
System.out.println(tree.get(12)); // 输出 12
System.out.println(tree.get(15)); // 输出 null，因为在 map 中未找到该键
```

我们还可以使用 `Iterator` 或 foreach 循环来遍历 map 元素。注意，条目是按照自然顺序打印的，而不是插入顺序：

```
for (Entry<Integer, String> entry : treeMap.entrySet()) {
  System.out.print(entry + " "); // 输出 1=one 4=four 10=ten 12=twelve
}
Iterator<Entry<Integer, String>> iter = treeMap.entrySet().iterator();
while (iter.hasNext()) {
  System.out.print(iter.next() + " "); // 输出 1=one 4=four 10=ten 12=twelve
}
```

## 第 32.2 节：简单 Java 类型的 TreeSet

我们创建一个空的 set，并向其中插入一些元素：

```
Version ≥ Java SE 7
TreeSet<Integer> treeSet = new TreeSet<>();
Version < Java SE 7
TreeSet<Integer> treeSet = new TreeSet<Integer>();
```

```
treeSet.add(10);
treeSet.add(4);
treeSet.add(1);
treeSet.add(12);
```

一旦我们在 set 中有了几个元素，就可以执行一些操作：

```
System.out.println(treeSet.first()); // 输出 1
System.out.println(treeSet.last()); // 输出 12
System.out.println(treeSet.size()); // 输出 4，因为 set 中有 4 个元素
System.out.println(treeSet.contains(12)); // 输出 true
System.out.println(treeSet.contains(15)); // 输出 false
```

我们还可以使用 `Iterator` 或 foreach 循环来遍历 set 元素。注意，条目是按照自然顺序打印的，而不是插入顺序：

```
for (Integer element : treeSet) {
  System.out.print(element + " "); // 输出 1 4 10 12
}
Iterator<Integer> iter = treeSet.iterator();
while (iter.hasNext()) {
  System.out.print(iter.next() + " "); // 输出 1 4 10 12
}
```

## 第 32.3 节：自定义类型的 TreeSet

由于 `TreeMap` 和 `TreeSet` 按照自然顺序维护元素，它们必须实现 `Comparable`，或者在构造时提供 `Comparator`。

假设我们有一个自定义类：

```java
public class Person {
  private int id;
  private String firstName;
  private Date birthday;

  // 构造函数、getter、setter...
}
```

如果我们实现 `Comparable`，可以这样做：

```java
public class Person implements Comparable<Person> {
  private int id;
  private String firstName;
  private Date birthday;

  @Override
  public int compareTo(Person other) {
    return this.id - other.id;
  }
}
```

或者，我们可以在构造函数中提供 `Comparator`：

```java
TreeSet<Person> set = new TreeSet<>((p1, p2) -> p1.id - p2.id);
```

## 第 32.4 节：TreeMap 和 TreeSet 的线程安全

`TreeMap` 和 `TreeSet` 不是线程安全的集合，因此在多线程程序中使用必须小心。`TreeMap` 和 `TreeSet` 在多线程并发读取时是安全的。因此，如果它们是由单个线程创建并填充的（例如在程序启动时），之后仅被读取而不被多线程修改，则没有理由进行同步或锁定。

然而，如果并发地读取和修改，或者被多个线程并发修改，集合可能会抛出 `ConcurrentModificationException` 或产生异常行为。在这种情况下，必须使用以下方法之一对集合访问进行同步：

- 使用 `Collections.synchronizedSortedSet`：

```java
SortedSet<Integer> set = Collections.synchronizedSortedSet(new TreeSet<Integer>());
SortedMap<Integer, String> map = Collections.synchronizedSortedMap(new TreeMap<Integer, String>());
```

这将提供一个由实际集合支持的 `SortedSet`/`SortedMap` 实现，并在某个互斥对象上进行同步。注意，这将集合的所有读写访问都会在单个锁上进行同步，因此即使是并发读取也是不可能的。

- 通过手动在某个对象（如集合本身）上进行同步：

```java
TreeSet<Integer> set = new TreeSet<>();
```

```java
// Thread 1
synchronized (set) {
  set.add(4);
}
```

- 使用锁，例如 `ReentrantReadWriteLock`：

```java
TreeSet<Integer> set = new TreeSet<>();
ReentrantReadWriteLock lock = new ReentrantReadWriteLock();
```

```java
// Thread 1
lock.writeLock().lock();
set.add(4);
lock.writeLock().unlock();
```

```java
// Thread 2
lock.readLock().lock();
set.contains(5);
lock.readLock().unlock();
```

与之前的同步方法相比，使用 `ReadWriteLock` 允许多个线程并发从 map 中读取。

# 第 33 章：队列与双队列

## 第 33.1 节：PriorityQueue 的用法

`PriorityQueue` 是一种数据结构。与 `SortedSet` 一样，`PriorityQueue` 也根据优先级对其元素进行排序。优先级元素先出现。`PriorityQueue` 的类型应该实现 `Comparable` 或 `Comparator` 接口，这决定了数据结构中元素的优先级。

```java
// PriorityQueue 的类型是 Integer。
PriorityQueue<Integer> queue = new PriorityQueue<Integer>();
// 将元素添加到 PriorityQueue 中
queue.addAll(Arrays.asList(9, 2, 3, 1, 3, 8));
```

```java
// PriorityQueue 通过 Integer 类的 compareTo 方法对元素进行排序。
// 此队列的头部是相对于指定排序的最小元素。
// System.out.println(queue); // 输出: [1, 2, 3, 9, 3, 8]
queue.remove();
System.out.println(queue); // 输出: [2, 3, 3, 9, 8]
queue.remove();
System.out.println(queue); // 输出: [3, 8, 3, 9]
queue.remove();
System.out.println(queue); // 输出: [3, 8, 9]
queue.remove();
System.out.println(queue); // 输出: [8, 9]
queue.remove();
```

```java
System.out.println(queue); // 输出: []
```

## 第 33.2 节：Deque

`Deque` 是一个 "double ended queue"，即"双端队列"，意味着元素可以在队列的头部或尾部添加。普通队列只能在队列尾部添加元素。

`Deque` 继承了 `Queue` 接口，这意味着普通方法仍然存在，但 `Deque` 接口提供了额外的方法，使队列操作更加灵活。如果你了解队列的工作原理，那么这些额外方法就不言自明了，因为这些方法的目的是为了增加灵活性：

| 方法 | 简要描述 |
| :--- | :--- |
| `getFirst()` | 获取队列头部的第一个元素但不移除它。 |
| `getLast()` | 获取队列尾部的最后一个元素但不移除它。 |
| `addFirst(E e)` | 在队列头部添加元素 |
| `addLast(E e)` | 在队列尾部添加元素 |
| `removeFirst()` | 移除队列头部的第一个元素 |
| `removeLast()` | 移除队列尾部的最后一个元素 |

`offer`、`poll` 和 `peek` 的某些选项可用，但它们不通过抛出异常，而是通过特殊值工作。展示它们的作用并没有意义。

### 添加和访问元素

要向 `Deque` 的尾部添加元素，可以调用其 `add()` 方法。你也可以使用 `addFirst()` 和 `addLast()` 方法，它们会将元素添加到 `Deque` 的头部和尾部。

```java
Deque<String> dequeA = new LinkedList<>();
```

```java
dequeA.add("element 1"); // 在尾部添加元素
dequeA.addFirst("element 2"); // 在头部添加元素
dequeA.addLast("element 3"); // 在尾部添加元素
```

你可以在不取出元素的情况下查看队列头部的元素。这是通过 `element()` 方法实现的。你也可以使用 `getFirst()` 和 `getLast()` 方法，它们返回 `Deque` 中的第一个和最后一个元素。示例如下所示：

```java
String firstElement0 = dequeA.element();
String firstElement1 = dequeA.getFirst();
String lastElement = dequeA.getLast();
```

### 移除元素

要从 deque 中移除元素，可以调用 `remove()`、`removeFirst()` 和 `removeLast()` 方法。以下是几个示例：

```java
String firstElement = dequeA.remove();
String firstElement1 = dequeA.removeFirst();
String lastElement = dequeA.removeLast();
```

## 第 33.3 节：Stacks（栈）

### 什么是栈？

在 Java 中，`Stack` 是用于对象的 LIFO（后进先出）数据结构。`Stack` 包含一个 API。

Java 包含一个带有以下方法的 `Stack` API：

```java
Stack
isEmpty()
push(Object o)
pop()
peek()
size()
```

### 示例

```java
import java.util.*;

public class StackExample {
    public static void main(String args[]) {
        Stack<Integer> st = new Stack<>();
        st.push(10);
        st.push(20);
        st.push(30);
        System.out.println(st); // 输出: [10, 20, 30]
        System.out.println(st.pop()); // 输出: 30
        System.out.println(st); // 输出: [10, 20]
    }
}
```

## 第 33.4 节：BlockingQueue（阻塞队列）

`BlockingQueue` 是一个接口，当你尝试出队且队列为空，或者尝试入队且队列满时会阻塞。`BlockingQueue` 方法有四种形式：

| | 抛出异常 | 返回特殊值 | 超时 | 阻塞 |
| :--- | :--- | :--- | :--- | :--- |
| `add(e)` | 是 | | | |
| `offer(e)` | | 是 | | |
| `put(e)` | | | | 是 |
| `put(e, time, unit)` | | | 是 | 是 |
| `remove()` | 是 | | | |
| `poll()` | | 是 | | |
| `take()` | | | | 是 |
| `take(time, unit)` | | 是 | | |

`BlockingQueue` 可以是有界的。有界的 `BlockingQueue` 是指定了容量的。无界队列是不指定容量的，实际上由 `Integer.MAX_VALUE` 初始化。

`BlockingQueue` 的常见实现有：

1. `ArrayBlockingQueue`
2. `LinkedBlockingQueue`
3. `PriorityBlockingQueue`

现在来看 `ArrayBlockingQueue` 的示例：

```java
import java.util.concurrent.*;

public class BlockingQueueExample {
    public static void main(String args[]) throws InterruptedException {
        BlockingQueue<String> bQueue = new ArrayBlockingQueue<>(2);
        bQueue.put("This is entry 1");
        System.out.println("Entry one done");
        bQueue.put("This is entry 2");
        System.out.println("Entry two done");
        bQueue.put("This is entry 3"); // 这将会阻塞
        System.out.println("Entry three done");

        Thread t = new Thread(() -> {
            try {
                Thread.sleep(2000);
                bQueue.take();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        });
        t.start();
    }
}
```

这将会打印：

```
Entry one done
Entry two done
```

以及在第二次输出后线程将被阻塞。在线程取出元素后，将打印 `Entry three done`。

## 第 33.5 节：作为 FIFO 队列的 LinkedList

`java.util.LinkedList` 类实现了 `java.util.List`，它是 `java.util.Queue` 接口的一个通用实现，基于 FIFO（先进先出）原则运行。

在下面的示例中，使用 `offer()` 方法将元素插入 `LinkedList` 中。这种插入操作被称为入队。在下方的循环中，根据 FIFO 原则从队列中移除元素。这种操作被称为出队。



```java
Queue<String> queue = new LinkedList<String>();
queue.offer("first element");
queue.offer("second element");
queue.offer("third element");
queue.offer("fourth element");
queue.offer("fifth element");

while (!queue.isEmpty()) {
  System.out.println(queue.poll());
}
```

此代码的输出是：

```
first element
second element
third element
fourth element
fifth element
```

首先，“第二个元素”会在第二个位置被移除，等等。

## 33.6 节：队列接口 (Queue Interface)

### 基础

队列是一个用于在处理之前持有元素的元素的集合。队列通常（但并不一定）按照先进先出（FIFO）的方式排列元素。

队列的头部是通过调用`remove`或`poll`方法移除的元素。在 FIFO 队列中，所有新元素都插入到队列末尾。

### 队列接口

```
public interface Queue<E> extends Collection<E> {
  boolean add(E e);
  boolean offer(E e);
  E remove();
  E poll();
  E element();
  E peek();
}
```

每个队列方法都以两种形式存在：

- 其中一个在操作失败时抛出异常；
- 另一个在操作失败时返回一个特殊值（取决于操作类型，返回`null`或`false`）。

| 操作类型 | 抛出异常 | 返回特殊值 |
| :--- | :--- | :--- |
| 插入 | `add(e)` | `offer(e)` |
| 移除 | `remove()` | `poll(e)` |
| 查看 | `element()` | `peek()` |

## 第 34 章：双端队列接口 (Deque Interface)

`Deque`是支持在两端进行元素插入和移除线性集合。

`deque`是 "double ended queue"（双端队列）的缩写，通常读作 "deck"。

大多数`Deque`实现对包含的元素数量没有固定限制，但此接口也支持容量限制的队列以及无固定大小限制的队列。`Deque`接口是一个比`Stack`和`Queue`均更丰富的抽象数据类型，因为它同时实现了栈和队列。

### 34.1 节：向 Deque 中添加元素

```
Deque deque = new LinkedList();
// 在末尾添加元素
deque.add("Item1");
// 在头部添加元素
deque.addFirst("Item2");
// 在末尾添加元素
deque.addLast("Item3");
```

### 34.2 节：从 Deque 中移除元素

```
// 获取并移除由此 deque 所表示的队列头部
Object headItem = deque.remove();
// 获取并移除此 deque 的第一个元素。
Object firstItem = deque.removeFirst();
// 获取并移除此 deque 的最后一个元素。
Object lastItem = deque.removeLast();
```

### 34.3 节：获取元素但不移除

```
// 获取但不移除此 deque 所表示的队列头部
Object headItem = deque.element();
// 获取但不移除此 deque 的第一个元素。
Object firstItem = deque.getFirst();
// 获取但不移除此 deque 的最后一个元素。
Object lastItem = deque.getLast();
```

### 34.4 节：遍历 Deque

```
// 使用迭代器
Iterator iterator = deque.iterator();
```

```
while(iterator.hasNext()){
  String Item = (String) iterator.next();
}
// 使用 For 循环
for(Object object : deque) { String Item = (String) object; }
```

## 第 35 章：枚举 (Enums)

Java 枚举（使用`enum`关键字声明）是单类中一组可计的数量的常量的简写语法。

### 35.1 节：声明和使用基础枚举

`Enum`可以被视为密封类（sealed class）的语法糖，该类仅在编译时已知的次数内实例化，用于定义一组常量。一个列出不同季节的简单枚举声明如下：

```
public enum Season {
WINTER,
SPRING,
SUMMER,
FALL
}
```

虽然枚举常量并不一定需要全大写，但 Java 的惯例是常量名完全大写，单词之间用下划线分隔。

你可以在自己的文件中声明枚举：

> /**
>  * 此枚举声明在 `Season.java` 文件中。
>  */

```
public enum Season {
WINTER,
SPRING,
SUMMER,
FALL
}
```

但你也可以在另一个类内部声明它：

```java
public class Day {
  private Season season;

  public String getSeason() { return season.name(); }

  public void setSeason(String season) { 
    this.season = Season.valueOf(season);
  }
}
```

> /**
>  * 此枚举声明在 `Day.java` 文件内部，
>  * 因为它被声明为 `private`，所以在在外部无法访问。
>  */

```
private enum Season {
WINTER,
SPRING,
SUMMER,
FALL
}
```

最后，你不能在方法体或构造函数内部声明枚举：

```java
public class Day {
  /**
   * 构造函数
   */
  public Day() {
    // 非法。编译错误 enum Season {
    // WINTER,
    // SPRING,
    // SUMMER,
    // FALL
    // }
  }

  public void aSimpleMethod() {
    //合法。你可以在方法内部声明原始类型（或对象）。
    // 编译！int primitiveInt = 42;

    // 非法。编译错误。enum Season {
    // WINTER,
    // SPRING,
    // SUMMER,
    // FALL
    // }
    Season season = Season.SPRING;
  }
}
```

不允许重复的常量：

```java
public enum Season {
WINTER,
WINTER, // 编译错误：重复常量 SPRING
SUMMER,
FALL
}
```

枚举的每个常量默认都是`public`、`static`、`final`的。由于每个常量都是静态的，因此可以使用枚举名直接访问。

枚举常量可以作为方法的参数传递：

```java
public static void display(Season s) {
  System.out.println(s.name()); // name() 是内置方法，用于获取枚举常量的精确名称
}
```

`display(Season.WINTER);` // 打印 "WINTER"

你可以使用`values()`方法获取枚举常量的数组。保证返回的数组中的元素按照声明顺序排列：

```java
Season[] seasons = Season.values();
```

注意：此方法每次调用时都会分配一个新的值数组。

要遍历枚举常量：

```java
public static void enumerate() { 
  for (Season s : Season.values()) {
    System.out.println(s.name);
  }
}
```

你可以在`switch`语句中使用枚举：

```java
public static void enumSwitchExample(Season s) {
  switch(s) {
    case WINTER:
      System.out.println("It's pretty cold"); break;
    case SPRING:
      System.out.println("It's warming up"); break;
    case SUMMER:
      System.out.println("It's hot"); break;
    case FALL:
      System.out.println("It's getting cool"); break;
  }
}
```

你可以使用`==`比较枚举常量：

```java
if (season == Season.WINTER) {
  // ...
}
```

你可以在同一个枚举中定义多个构造函数。当你这么做时，你在枚举声明中传递的参数将决定调用哪个构造函数：

```java
public enum Coin {

  PENNY(1, true), NICKEL(5, false), DIME(10), QUARTER(25);

  private final int value;

  private final boolean isCopperColored;
```

```java
  Coin (int value) {
    this(value, false);
  }
```

```java
  Coin (int value, boolean isCopperColored) {
    this.value = value;
    this.isCopperColored = isCopperColored;
  }
```

... 注意：所有非基本类型的枚举字段都应该实现`Serializable`，因为`Enum`类已经实现了它。

### 35.3 节：带有抽象方法的枚举

枚举可以定义抽象方法，每个成员都必须实现这些方法。

```java
enum Action {

  DODGE {
    public boolean execute(Player player) {
      return player.isAttacking();
    }
```

```java
  ATTACK {
    public boolean execute(Player player) {
      return player.hasWeapon();
    }
```

```java
  },
  JUMP {
    public boolean execute(Player player) {
      return player.getCoordinates().equals(new Coordinates(0, 0));
    }
  };

  public abstract boolean execute(Player player);
```

这允许每个枚举成员为特定操作定义自己的行为，而不需要在顶层定义的方法中使用`switch`语句处理类型。
请注意，这种模式是通常使用多态和/或实现接口所实现的简化形式。

### 35.4 节：实现接口

这是一个枚举，同时也是一个可调用函数，用于根据预编译的正则表达式模式测试字符串输入。

```java
import java.util.function.Predicate;
import java.util.regex.Pattern;

enum RegEx implements Predicate<String> {
  UPPER("[A-Z]+"), LOWER("[a-z]+"), NUMERIC("[\\+\\-]?[0-9]+");

  private final Pattern pattern;
```

```java
  private RegEx(final String pattern) {
    this.pattern = Pattern.compile(pattern);
  }

  @Override
  public boolean test(final String input) {
    return this.pattern.matcher(input).matches();
  }
}

public class Main {
  public static void main(String[] args) {
    System.out.println(RegEx.UPPER.test("ABC"));
    System.out.println(RegEx.LOWER.test("abc"));
    System.out.println(RegEx.NUMERIC.test("+111"));
  }
}
```

枚举的每个成员也可以实现该方法：

```java
import java.util.function.Predicate;

enum Acceptor implements Predicate<String> {
  NULL {
    @Override
    public boolean test(String s) { return s == null; }
  },
  EMPTY {
    @Override
    public boolean test(String s) { return s.equals(""); }
  },
  NULL_OR_EMPTY {
    @Override
    public boolean test(String s) { return NULL.test(s) || EMPTY.test(s); }
  }
}

public class Main {
  public static void main(String[] args) {
    System.out.println(Acceptor.NULL.test(null)); // true
    System.out.println(Acceptor.EMPTY.test("")); // true
    System.out.println(Acceptor.NULL_OR_EMPTY.test(" ")); // false
  }
}
```

### 35.5 节：使用单元素枚举实现单例模式

枚举常量会在枚举被第一次引用时实例化。因此，这允许使用单元素枚举来实现单例软件设计模式。

```java
public enum Attendant {
  INSTANCE;
```

```java
  private Attendant() {
    // 执行某些初始化例
  }
```

```java
  public void sayHello() {
    System.out.println("Hello!");
  }
```

```java
public class Main {
  public static void main(String... args) {
    Attendant.INSTANCE.sayHello(); // 在此处实例化
  }
}
```

根据 Joshua Bloch 编写的《Effective Java》（Java 编程），单元素枚举是实现单例的最佳方法。这种方法具有以下优势：

- 线程安全
- 保证单例实例化
- 开箱即用的序列化

并且，正如在“实现接口”节所示，此单例也可以实现一个或多个接口。

### 35.6 节：使用方法和静态块

枚举可以包含方法，就像任何类一样。为了看到它是如何工作的，我们将定义如下的枚举：

```java
public enum Direction {
  NORTH, SOUTH, EAST, WEST;
}
```

让我们写一个返回相反方向枚举的方法：

```java
public enum Direction {
  NORTH, SOUTH, EAST, WEST;

  public Direction getOpposite(){
    switch (this){
```

```java
      case NORTH:
        return SOUTH;
      case SOUTH:
        return NORTH;
      case WEST:
        return EAST;
      case EAST:
        return WEST;
      default: // 这永远不会发生
        return null;
    }
  }
}
```

可以通过使用字段和静态初始化块进一步改进它：

```java
public enum Direction {
  NORTH, SOUTH, EAST, WEST;

  private Direction opposite;

  public Direction getOpposite() {
    return opposite;
  }
```

```java
  static {
    NORTH.opposite = SOUTH;
    SOUTH.opposite = NORTH;
    WEST.opposite = EAST;
    EAST.opposite = WEST;
  }
}
```

在这个例子中，相反方向存储在字段中，并在第一次使用`Direction`时初始化。这比使用`switch`语句要优雅得多。

### 35.7 节：带有静态字段的枚举

在枚举中，你可以定义所有枚举常量共享的静态字段。

```java
public enum Direction {
    NORTH, SOUTH, EAST, WEST;
    public static final String DEFAULT_DIRECTION = "NORTH";
    // ...
}
```



这允许你存储与方向相关的全局状态或配置。

## 第 35.8 节：带有泛型参数的枚举

虽然枚举不能直接拥有泛型参数，但它们可以实现具有泛型类型的接口。

```java
interface Processor<T> {
    void process(T input);
}

enum Operation implements Processor<Integer> {
    ADD, SUB, MUL, DIV;
    // ...
}
```

## 第 35.9 节：枚举枚举

枚举名称并不总是清晰。要记录枚举，请使用 `javadoc`：

```java
public enum Coins {

/**
 * 硬币，通常被称为 penny，
 * 是一种货币单位，等于美元的百分之一
 */
PENNY(1),

/**
 * 美法镍是一种五分硬币，
 * 等于美元的五百分之
 */
NICKEL(5),

/**
 * 美法角是一种十分分硬币，指的是美元的十分分之一
 */
DIME(10),

/**
 * 元是一种价值25美分的美国硬币，
 * 等于美元的四分之一
 */
QUARTER(25);
private int value;
```

```java
Coins(int value) {
    this.value = value;
}
```

```java
public int getValue() { return value; }
```

## 第 35.10 节：常量特定体

在枚举中，可以为枚举的特定常量定义特定的行为以覆盖枚举的默认行为，这种技术被称为常量特定体（constant specific body）。假设有三个钢琴学生——`John`、`Ben` 和 `Luke` 定义在一个名为 `PianoClass` 的枚举中，如下所示：

```java
enum PianoClass {

    JOHN, BEN, LUKE;

    public String getSex() {

        return "Male";

    }

    public String getLevel() {

        return "Beginner";

    }

}
```

有一天，又有两个学生来了——`Rita` 和 `Tom`，他们的性别（女）和水平（中级）与之前的不匹配：

```java
enum PianoClass2 {

    JOHN, BEN, RITA, TOM;

    public String getSex() {

        return "Male"; // 问题，Rita 是女性

    }

    public String getLevel() {

        return "Beginner"; // 问题，Tom 是中级学生

    }

}
```

因此，简单所示将新学生添加到常量声明中是不正确的：

```java
PianoClass2 tom = PianoClass2.TOM;

PianoClass2 rita = PianoClass2.RITA;

System.out.println(tom.getLevel()); // 输出 Beginner -> 错误，Tom 不是 beginner

System.out.println(rita.getSex()); // 输出 Male -> 错误，Rita 是男性的
```

可以为 `Rita` 和 `Tom` 这两个常量定义特定的行为，以覆盖 `PianoClass2` 的默认行为，如下：

```java
enum PianoClass3 { JOHN, BEN, LUKE, RITA {

    @Override

    public String getSex() { return "Female"; }

},

TOM {

    @Override

    public String getLevel() { return "Intermediate"; }

    public String getSex() {

        return "Male";

    }

    public String getLevel() {

        return "Beginner";

    }

} }
```

现在 `Tom` 的级别和 `Rita` 的性别都是符合预期的：

```java
PianoClass3 tom = PianoClass3.TOM;

PianoClass3 rita = PianoClass3.RITA;

System.out.println(tom.getLevel()); // 输出 Intermediate

System.out.println(rita.getSex()); // 输出 Female
```

定义特定内容主体的另一种方法是使用构造函数，例如：

```java
enum Friend {

MAT("Male"),

JOHN("Male"),

JANE("Female");

private String gender;

Friend (String gender) { this.gender = gender; }

public String getGender() { return this.gender; }

}
```

用法如下：

```java
Friend mat = Friend.MAT;

Friend john = Friend.JOHN;

Friend jane = Friend.JANE;

System.out.println(mat.getGender()); // Male

System.out.println(john.getGender()); // Male

System.out.println(jane.getGender()); // Female
```

## 第 35.11 节：获取枚举的值

每个枚举类包含一个名为 `values()` 的隐含静态方法。该方法返回一个包含该枚举所有值的数组。你可以使用此方法来遍历这些值。但重要注意的是，该方法每次被调用时都会返回一个新的数组。

```java
public enum Day {

    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY;

    /**

     * 打印此枚举中的所有值。 */

    public static void printAllDays() {

        for(Day day : Day.values()) { System.out.println(day.name()); }

    }

}
```

如果你需要一个 `Set`，也可以使用 `EnumSet.allOf(Day.class)`。

## 第 35.12 节：枚举多态模式

当方法需要接受一组“可扩展”的枚举值时，程序员可以像对待普通类一样应用多态，通过创建一个接口，该接口将用于任何需要使用枚举的地方：

```java
public interface ExtensibleEnum { String name(); };
```

通过这种方式，任何标记（通过实现）接口的枚举都可以作为参数使用，允许程序员创建任意数量的枚举并被方法接受。这在某些 API 中非常有用，例如当 API 中有一个默认的（不可修改的）枚举，而使用这些 API 的想要用更多值来“扩展”该枚举。

可以如下定义一组默认枚举值：

```java
public enum DefaultValues implements ExtensibleEnum { VALUE_ONE, VALUE_TWO };
```

然后可以这样定义额外的值：

```java
public enum ExtendedValues implements ExtensibleEnum { VALUE_THREE, VALUE_FOUR };
```

示例展示了如何使用这些枚举 - 注意 `printEnum()` 如何接受来自两种枚举类型的值：

```java
private void printEnum(ExtensibleEnum val) {

    System.out.println(val.name());

}

printEnum(DefaultValues.VALUE_ONE);

printEnum(DefaultValues.VALUE_TWO);
```

```java
// VALUE_ONE // VALUE_TWO

printEnum(ExtendedValues.VALUE_THREE); // VALUE_THREE

printEnum(ExtendedValues.VALUE_FOUR); // VALUE_FOUR
```

注意：此模式并不能防止你在另一个枚举中重新定义已经在某个枚举中定义的枚举值。这些枚举值将是不同的实例。此外，由于我们只有接口而不是真实的枚举，因此无法对枚举进行 `switch-on-enum`。

## 第 35.13 节：枚举值的比较与包含

枚举只包含常量，可以直接用 `==` 进行比较。因此，只需要进行引用检查，而不需要不当使用 `.equals()`，后者可能会抛出 `NullPointerException`，而 `==` 检查则不会出现这种情况。

```java
enum Day {

  GOOD, AVERAGE, WORST; }

public class Test {

  public static void main(String[] args) { Day day = null;

    if (day.equals(Day.GOOD)) {//NullPointerException!

      System.out.println("Good Day!");

    }

    if (day == Day.GOOD) {//始终使用 == 来比较枚举

      System.out.println("Good Day!");

  }

}
```

为了对枚举值进行分组、取反或范围限定，我们拥有 `EnumSet` 类，它包含了不同的方法：
- `EnumSet#range`：获取两个端点定义的枚举范围的子集
- `EnumSet#of`：不带任何范围的特定枚举集合。有多个重载方法。
- `EnumSet#complementOf`：与枚举值取反的枚举集合

```java
enum Page {

  A1, A2, A3, A4, A5, A6, A7, A8, A9, A10 }

public class Test {

  public static void main(String[] args) {

    EnumSet<Page> range = EnumSet.range(Page.A1, Page.A5);

    EnumSet<Page> set = EnumSet.of(Page.A1, Page.A2, Page.A3);

    EnumSet<Page> complement = EnumSet.complementOf(EnumSet.range(Page.A1, Page.A3));

  }

}
```

## 第 35.14 节：通过名称获取枚举常量

假设我们有一个枚举：

```java
enum Day {

  MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY

}
```

使用 `valueOf()` 方法可以根据名称获取常量。例如：

```java
Day day = Day.valueOf("MONDAY");

System.out.println(day); // 输出 MONDAY
```

如果指定的名称不存在，`valueOf()` 将抛出 `IllegalArgumentException`：

```java
Day.valueOf("NONEXIST"); // 抛出 IllegalArgumentException
```

## 第 35.15 节：带有属性（字段）的枚举

如果我们想要枚举包含更多信息，而不仅仅是常量。考虑以下例子：

```java
enum Coin {

  PENNY(1), NICKEL(5), DIME(10), QUARTER(25);

  private final int value;

  Coin(int value) {

    this.value = value;

  }

  public boolean isGreaterThan(Coin other) {

    return this.value > other.value;

  }

}
```

我们可以这样比较两个枚举实例的值：

```java
Coin penny = Coin.PENNY;

Coin dime = Coin.DIME;

System.out.println(penny.isGreaterThan(dime)); // 输出 false

System.out.println(dime.isGreaterThan(penny)); // 输出 true
```

## 第 35.16 节：枚举转换为字符串

有时你想将枚举转换为字符串，有两种方法。假设我们有：

```java
enum Fruit { APPLE, ORANGE, STRAWBERRY, BANANA, LEMON, GRAPE_FRUIT }
```

使用 `name()`：`name()` 是枚举的一个内部方法，返回枚举定义的字符串表示。

```java
System.out.println(Fruit.BANANA.name()); // 输出 BANANA

System.out.println(Fruit.GRAPE_FRUIT.name()); // 输出 GRAPE_FRUIT
```

使用 `toString()`：`toString()` 可能会被重写以生成用户友好的字符串。如果你要在代码中进行检查，不要使用 `toString()`，`name()` 更稳定。只有当你准备将值输出到日志或标准输出时才使用 `toString()`。

```java
enum Fruit {

  @Override

  public String toString() {

    return name().toLowerCase();

  }

}

System.out.println(Fruit.BANANA.toString()); // 输出 banana

System.out.println(Fruit.GRAPE_FRUIT.toString()); // 输出 grape fruit
```

## 第 35.17 节：带有静态字段的枚举

如果枚举类需要静态字段，请记住它们是在枚举值本身之后创建的。这意味着，以下代码会导致 `NullPointerException`：

```java
enum Example {

  ONE(1), TWO(2);

  static Map<String, Integer> integers = new HashMap<>();

  Example(int value) {

    integers.put(this.name(), value);

  }

}
```

一种解决此问题的可能方法：

```java
enum Example {

  ONE(1), TWO(2);

  static Map<String, Integer> integers;

  Example(int value) {

    putValue(this.name(), value);

  }

  private static void putValue(String name, int value) {

    if (integers == null)

      integers = new HashMap<>();

    integers.put(name, value);

  }

}
```

```java
private Example(int value) {
    putValue(this.name(), value);
}

private static void putValue(String name, int value) {
    if (integers == null)
        integers = new HashMap<>();

    integers.put(name, value);
}

//!!这可能导致空指针异常!!
public int getValue() {
    return (Example.integers.get(this.name()));
}
```

初始化：
1. 创建枚举值
2. 副作用调用了 `putValue()`，它初始化了 `integers`
3. 静态值被设置
4. `integers = null;` // 在枚举之后执行，因此 `integers` 的内容丢失

# 第 36 节：Enum Map

Java `EnumMap` 类是为枚举键（enum keys）专门 `Map` 实现。
它继承了 `Enum` 和 `AbstractMap` 类。
`java.util.EnumMap` 类的参数：
- `K`：它是此 map 维护的键类型。
- `V`：它是映射值的类型。

# 第 36.1 节：Enum Map 示例代码

```java
import java.util.*;

class Book {

    int id;

    String name, author, publisher;

    int quantity;

    public Book(int id, String name, String author, String publisher, int quantity) {

        this.id = id;

        this.name = name;

        this.author = author;

        this.publisher = publisher;
```



# 第 37 节：EnumSet 类

`EnumSet` 类是用于枚举类型的专门化 `Set` 实现。它继承了 `AbstractSet` 并实现了 `Set` 接口。

## 第 37.1 节：EnumSet 示例

```java
import java.util.*;

enum days {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}

public class EnumSetExample {
    public static void main(String args) {
        Set<days> set = EnumSet.of(days.TUESDAY, days.WEDNESDAY);

        // 遍历元素
        Iterator<days> iter = set.iterator();
        while (iter.hasNext()) {
            System.out.println(iter.next());
        }
    }
}
```

# 第 38 节：Enum 名称

Java 不允许名称以数字开头。在这种情况下，你可以在后面添加下划线 (`_`) 或任何允许的模式。

## 第 38.1 节：开头的枚举名称

```java
public enum BookCode {
    _10A("Simon Haykin", "Communication System"),
    _42B("Stefan Hakins", "A Brief History of Time"),
    _E1("Sedra Smith", "Electronics Circuits");

    private String author;
    private String title;

    BookCode(String author, String title) {
        this.author = author;
        this.title = title;
    }

    public String getName() {
        return author;
    }
}
```

# 第 39 节：Hashtable

`Hashtable` 是 Java 集合中的一个类，包含唯一元素且是同步的。

## 第 39.1 节：Hashtable

```java
import java.util.*;

public class HashtableDemo {
    public static void main(String[] args) {
        // 创建并填充表
        Hashtable<Integer, String> map = new Hashtable<Integer, String>();
        map.put(10, "C");
        map.put(20, "Domain");
        map.put(30, "Databases");

        System.out.println("移除前的值: " + map);

        // 移除键的值
        map.remove(20);
        System.out.println("移除后的值: " + map);
    }
}
```

# 第 40 节：运算符

Java 语言中的运算符是特殊符号，对一个、两个或三个操作数执行特定操作，然后返回结果。

## 第 40.1 节：自增/自减运算符 (`++`/`--`)

变量可以使用 `++` 和 `--` 运算符分别自增或自减。

当 `++` 和 `--` 运算符紧跟变量时，它们被称为后自增和后自减。如果运算符在变量之前，则表达式的值是自增或自减之前的值。

```java
int x = 10;
System.out.println("x=" + x + " x=" + x++); // 输出 x=10
System.out.println("x=" + x + " x=" + ++x); // 输出 x=11
System.out.println("x=" + x + " x=" + x--); // 输出 x=12
```

注意不要在表达式末尾覆盖后自增或自减运算符。这发生在你将后自增运算符重新赋值给已增加的变量时。自增/自减不会产生影响。尽管左侧的变量被正确递增，但它的值将立即被之前评估的结果覆盖。

```java
int x = 0;
x = x++ + 1; // 发生错误
System.out.println(x); // 输出 1
```

正确的做法：

```java
int x = 0;
x = ++x + 1;
System.out.println(x); // 输出 2
```

## 第 40.2 节：条件运算符 (`? :`)

### 语法

```
{condition-to-evaluate}?statement-on-true}:{statement-on-false}
```

如语法所示，条件运算符（也称为三元运算符[^1]）使用问号 (`?`) 和冒号 (`:`) 字符来实现两种结果的表达式。它可以用于替换较长的 `if-else` 块来根据条件返回两个值。

`result = testCondition ? value1 : value2` 等于：

```java
if (testCondition) {
    result = value1;
} else {
    result = value2;
}
```

它可以读为“如果 `testCondition` 为真，则将 `result` 设置为 `value1`；否则，将 `result` 设置为 `value2`”。

例如：

```java
// 使用条件运算符获取绝对值
a = 10;
int absValue = a < 0 ? a : a;
System.out.println("abs = " + absValue); // 输出 abs = 10
```

等于：

```java
// 使用 if/else 获取绝对值
a = 10;
int absValue;
if (a < 0) {
    absValue = a;
} else {
    absValue = a;
}
System.out.println("abs = " + absValue); // 输出 abs = 10
```

### 用法

可以使用条件运算符进行条件赋值（例如空检查）。

`String x = y != null ? y.toString() : "";` // 其中 `y` 是对象

此示例等于：

```java
String x = "";
if (y != null) {
    x = y.toString();
}
```

由于条件运算符的优先级较低（仅位于赋值运算符之上），因此通常不需要对条件加括号，但当条件运算符与其他运算符结合时，需要对条件运算符结构加括号：

```java
// 三部分中的表达式不需要括号
10 <= a && a < 19 ? b * 5 : b * 7

// 必须括号 7 * (a > 0 ? 2 : 5)
```

条件运算符也可以嵌套在第三部分，其工作方式更像链式或 `switch` 语句。

```
a ? "a 为真"
b ? "a 为假，b 为真" : c ? "a 和 b 均为假，c 为真" :
"a、b 和 c 均为假"
// 运算符优先级可以用括号说明：
a ? x : (b ? y : (c ? z : w))
```

脚注：

[^1]: Java 语言规范和 Java 教程都将 (`?:`) 运算符称为条件运算符。教程说，因为它接受三个操作数且是（目前）Java 定义的唯一三元运算符，因此“也被称为三元运算符”。条件运算符术语与 C、C++ 以及其他具有相应运算符的语言一致。

## 第 40.3 节：位运算符 (`&`、`|`、`^`、`~`)

`AND` (`&`) 运算符是一个二元运算符，它对两个操作数执行位与或逻辑“与”操作；参见 JLS 15.22.2。
`OR` (`|`) 运算符是一个二元运算符，它对两个操作数执行位或或逻辑“包含性或”操作；参见 JLS 15.22.2。
`XOR` (`^`) 运算符是一个二元运算符，它对两个操作数执行位异或或逻辑“异或”操作；参见 JLS 15.22.2。

当操作数是布尔值时，这些运算符执行的逻辑操作可以总结如下：

| A | B | A&B | A\|B | A^B |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

注意，对于整数操作数，上表描述了单个位的情况。这些运算符实际上是并行处理操作数或操作数的全部 32 或 64 位。

### 操作数类型和结果类型

当操作数是整数时，适用常规的算术转换。

### 位运算符的常见用例

`~` 运算符用于反转布尔值，或更改整数操作数中的所有位。`&` 运算符用于“掩码”整数操作数中的某些位。例如：

```java
int word = 0b00011010;
int mask = 0b00000011; // 用于掩码除低位以外的所有位

// 获取 word 的两个位
int lowBits = word & mask; // -> 0b00000010
int highBits = word & ~mask; // -> 0b00011000
```

`|` 运算符用于合并两个操作数的真值。例如：

```java
int word2 = 0b01011111;

// 将 word1 的低 2 位与 word2 的高 30 位合并
int combined = (word & mask) | (word2 & ~mask); // -> 0b01011110
```

`^` 运算符用于取反或“翻转”位：

```java
int word3 = 0b00101010;
int word4 = word3 ^ null; // 0b00101001
```

更多关于位运算符使用的示例，请参见位操作（Bit Manipulation）。

## 第 40.4 节：字符串拼接运算符 (`+`)

该符号在 Java 中可以表示三种不同的运算符：

- 如果 `+` 之前没有操作数，则它是一元加号运算符。
- 如果有两个操作数，且它们都是数值类型，那么它就是二元加法运算符。
- 如果有两个操作数，且其中至少有一个是字符串（`String`），那么它就是二元拼接运算符。

在简单的情况下，拼接运算符将两个字符串连接以生成第三个字符串。例如：

```java
String s1 = "a String";
String s2 = "This " + s1; // s2 包含 "This is a String"
```

当两个操作数之一不是字符串时，它将按照如下方式转换为字符串：

- 类型为基本类型（`primitive type`）的操作数的转换方式类似于对装箱后的值调用 `toString()`。
- 类型为引用类型（`reference type`）的操作数通过调用操作数的 `toString()` 方法进行转换。如果操作数为 `null`，或者如果 `toString()` 方法返回 `null`，则使用字面量 `"null"`。

例如：

```java
int one = 1;
String s3 = "One is " + one; // s3 包含 "One is 1"
String s4 = null + " is null"; // s4 包含 "null is null"
String s5 = "{1}" + new int[]{1}; // s5 包含类似
// "{1} is [I@xxxxxxx]"
```

`s5` 示例的解释是数组类型的 `toString()` 方法继承自 `java.lang.Object`，其行为是产生一个由类型名称和对象的标识哈希码（identity hashcode）组成的字符串。

拼接运算符规定创建一个新的 `String` 对象，但表达式为常量表达式（Constant Expression）除外。在这种情况下，表达式在编译时求值，其运行时值等同于字符串字面量。这意味着这样分割字符串字面量时没有运行时开销：

```java
String typing = "The quick brown fox " + 
"jumped over the " + 
"lazy dog"; // 常量表达式
```

### 优化与效率

如上述，除常量表达式外，每个字符串拼接都会创建一个新的 `String` 对象。考虑这段代码：

```java
public String stars(int count) { 
    String res = "";
    for (int i = 0; i < count; i++) {
        res = res + "*";
    }
    return res;
}
```

在上述方法中，循环的每次迭代都会创建一个比之前迭代多出一个字符的新 `String`。每次拼接都会复制操作数字符串中的所有字符以形成新的 `String`。因此，`stars(N)` 将：

- 创建 `N` 个 `String` 对象，并丢弃最后一个之外的所有对象，
- 复制 `N * (N + 1) / 2` 个字符，
- 生成 `O(N^2)` 字节的垃圾。

对于大 `N` 来说这是非常昂贵的。事实上，任何在循环中拼接字符串的代码都可能存在这个问题。更好的写法如下：

```java
public String stars(int count) {
    // 创建一个容量为 'count' 的字符串构建
    StringBuilder sb = new StringBuilder(count);
    for (int i = 0; i < count; i++) {
        sb.append("*");
    }
    return sb.toString();
}
```



理想情况下，你应该设置`StringBuilder`的容量，但如果这样做不可行，该类会自动扩展所使用的底层数组。

# 第 40.5 节：算术运算符 (+, -, *, %)

Java 语言提供了对整数和浮点值执行算术运算的运算符。

有两个`+`运算符：
- 二元加法运算符将一个数加另一个数。
- 一元加号运算符什么都不做。

有两个`-`运算符：
- 二元减法运算符从另一个数中减去一个数。
- 一元减号运算符等于减去它的操作数。

二元乘运算符 (`*`) 将一个数乘以另一个数。
二元除运算符 (`/`) 将一个数除以另一个数。
二元剩余运算符 (`%`) 计算一个数除以另一个数的余数。通常被错误地称为模（modulus）。

## 操作数类型和结果类型

这些运算符要求数值操作数并产生数值结果。操作数类型可以是任何基本类型（`byte`, `short`, `char`, `int`, `float`, `double`）或任何包装类型（`Byte`, `Short`, `Character`, `Integer`, `Long`, `Float`, `Double`）。

结果类型如下：
- 如果操作数之一是`double`或`Double`，则结果类型为`double`。
- 如果操作数之一是`float`或`Float`，则结果类型为`float`。
- 如果操作数之一是`long`或`Long`，则结果类型为`long`。
- 否则，结果类型为`int`。这涵盖了`byte`、`short`和`char`。

操作的结果类型决定了如何执行算术运算以及如何处理操作数：
- 如果结果类型是`double`，操作数提升为双精度二进制 IEEE 754 浮点运算。
- 如果结果类型是`float`，操作数提升为`float`，使用 32 位单精度二进制 IEEE 754 浮点运算。
- 如果结果类型是`long`，操作数提升为`long`，使用 64 位补码整数算术运算。
- 如果结果类型是`int`，操作数提升为`int`，使用 32 位补码整数算术运算。提升分为两个阶段：
  - 如果操作数类型是包装类型，则操作数值被拆箱为相应基本类型的值。
  - 如果必要，基本类型提升为所需的类型：整数转换为`int`或`long`是无损的。`float`转换为`double`是无损的。整数转换为浮点值可能会导致精度损失。转换使用 IEEE 754 “舍入最近”语义。

## 除法的含义

`/`运算符除左操作数`n`（被除数）和右操作数`d`（除数），产生结果`q`（商）。Java 整数除向零舍入。JLS 第 15.17.2 节规定了 Java 整数除的行为：

操作数`n`和`d`产生的商是一个整数`q`，其值在满足`|d · q| ≤ |n|`的情况下尽可能。此外，当`|n| ≥ |d|`且`n`和`d`符号相同时，`q`为正；但当`|n| ≥ |d|`且`n`和`d`符号相反时，`q`为负。

有两个特殊情况：
- 如果`n`是`MIN_VALUE`且除数为`-1`，则会发生整数溢出。结果是`MIN_VALUE`。在这种情况下不会抛出异常。
- 如果`d`为 0，则会抛出`ArithmeticException`。

Java 浮点数除法有更多的边缘情况需要考虑。然而，基本思想是结果`q`是最接近满足`d . q = n`的值。浮点除法永远不会产生异常。相反，除以零的操作会产生`INF`和`NaN`值；见下文。

### 余数的含义

与 C 和 C++ 不同，Java 中的取余数运算符（`%`）同时适用于整数和浮点数运算。

对于整数情况，`a % b`的结果被定义为数字`r`，使得`(a /b) * b + r`等于`a`，其中`*`和`+`是相应的 Java 整数运算符。这在除`b`为 0 之外的所有情况下都适用。在那种情况下，取余数会导致`ArithmeticException`。

根据上述定义可以得出：只有当`a`为负时，`a % b`才可能为负；只有当`a`为正时，它才为正。此外，`a % b`的绝对值始终小于`b`的绝对值。

浮点取余数运算是整数情况的推广。`a % b`的结果余数`r`由数学关系`r = a - (b · q)`定义，其中：
- `q`是一个整数，
- 只有当`a / b`为负时它才为负，只有当`a / b`为正时它才为正，且其值在不超过`a`和`b`的真实数学商绝对值的情况下尽可能大。

浮点取余数运算在边缘情况下（例如`b`为 0）可能会产生`INF`和`NaN`值；见下文。它不会抛出异常。

重要说明：通过`%`计算的浮点取余数运算的结果与 IEEE 754 定义的余数运算的结果并不相同。IEEE 754 余数可以使用`Math.IEEERemainder`库方法进行计算。

### 整数溢出

Java 32 位和 64 位整数值是有符号的，并使用补码二进制表示。例如，可以表示为（32位）`int`的数字范围是从`-2^31`到`+2^31 - 1`。

当你加、减或乘两个`N`位整数（`N == 32`或`64`）时，运算结果可能太大，无法表示为`N`位整数。在这种情况下，运算会导致整数溢出，结果可以如下所示计算：
1. 执行数学运算以得到整个数字的中间补码表示。该表示将大于`N`位。
2. 中间表示的低 32 位或 64 位被用作结果。

需要注意的是，任何情况下整数溢出都不会导致异常。

### 浮点 INF 和 NAN 值

Java 的`float`和`double`使用 IEEE 754 浮点表示。这些表示包含一些特殊值，用于表示超出实数范围的值：
- “无限”或`INF`值表示过大的数字。`+INF`值表示过大且为正的数字；`-INF`值表示过大且为负的数字。
- “不定值”/“非数字”或`NaN`表示由无意义运算产生的值。

`INF`值由引起溢出的浮点运算或除以零产生。`NaN`值由零除以零或计算零的零的余数产生。

令人惊讶的是，可以使用`INF`和`NaN`作为操作数进行算术运算而不会触发异常。例如：
- `+INF`加一个有限值得到`+INF`。
- `+INF`加`+INF`得到`+INF`。
- `+INF`加`-INF`得到`NaN`。
- 除以`INF`得到`+0.0`或`-0.0`。
- 所有涉及一个或多个`NaN`操作数的运算均得到`NaN`。

有关完整细节，请参阅 JLS 15 节的相关子章节。

（详情参见 JLS 5.2。）

“操作与赋值”运算符的精确含义由 JLS 15.26.2 规定：

形式为`E1 op= E2`的复合赋值表达式等于`E1 = (T) ((E1 op (E2)))`，其中`T`是`E1`的类型，但`E1`只求值一次。

注意，在最终赋值之前存在隐式类型转换。

1. `=`：简单赋值运算符：将右侧操作数的值赋值给左侧操作数。示例：`c = a + b`将`a + b`的值加到`c`的值上并赋值给`c`。
2. `+=`：加法赋值运算符：将右侧操作数的值加到左侧操作数的值上并将结果赋值给左侧操作数。如果左侧操作数的类型为`String`，则为“拼接赋值运算符”。示例：`c += a`大同于`c = c + a`。
3. `-=`：减法赋值运算符：从左侧操作数的值中减去右侧操作数的值并将结果赋值给左侧操作数。示例：`c -= a`大同于`c = c - a`。
4. `*=`：乘法赋值运算符：将左侧操作数的值乘以右侧操作数的值并将结果赋值给左侧操作数。示例：`c *= a`大同于`c = c * a`。
5. `/=`：除法赋值运算符：将左侧操作数的值除以右侧操作数的值并将结果赋值给左侧操作数。示例：`c /= a`大同于`c = c / a`。
6. `%=`：模赋值运算符：计算右侧操作数的值对左侧操作数的值取模并将结果赋值给左侧操作数。示例：`c %= a`大同于`c = c % a`。
7. `<<=`：左移赋值运算符。示例：`c <<= 2`大同于`c = c << 2`。
8. `>>>=`：算术右移赋值运算符。示例：`c >>>= 2`大同于`c = c >>> 2`。
9. `>>>=`：逻辑右移赋值运算符。示例：`c >>>= 2`大同于`c = c >>> 2`。
10. `&=`：位与赋值运算符。示例：`c &= 2`大同于`c = c & 2`。
11. `|=`：位或赋值运算符。示例：`c |= 2`大同于`c = c | 2`。
12. `^=`：位异或赋值运算符。示例：`c ^= 2`大同于`c = c ^ 2`。

# 第 40.9 节：条件与运算符和条件或运算符 ( && 和 || )

Java 提供了条件与运算符和条件或运算符，它们都接受一个或两个`boolean`类型的操作数并产生一个`boolean`结果。它们是：
- `&&` - 条件与运算符。
- `||` - 条件或运算符。

`<left-expr> && <right-expr>`的求值过程等同于以下伪代码：

```
boolean L = evaluate(<left-expr>);
if (L) {
    return evaluate(<right-expr>);
} else {
    // 短路第二个操作数表达式的求值
    return false;
}
```

`<left-expr> || <right-expr>`的求值过程等同于以下伪代码：

```
boolean L = evaluate(<left-expr>);
if (!L) {
    return evaluate(<right-expr>);
} else {
    // 短路第二个操作数表达式的求值
    return true;
}
```

上面的伪代码说明，短路运算符的行为等于使用`if / else`语句。

示例 - 在表达式中使用`&&`作为守卫：以下示例展示了`&&`运算符最常见的用法模式。比较以下两个方法来测试提供的`Integer`是否为零。

```java
public boolean isZero(Integer value) { return value == 0; };
```

```java
public boolean isZero(Integer value) { return value != null && value == 0; };
```

第一个版本在大多数情况下都有效，但如果值为`null`，则会抛出`NullPointerException`。第二个版本通过先检查`null`避免了这个问题。短路求值确保了如果第一部分为假，则不会对第二部分进行求值。

有两个“陷阱”使得在处理真值时建议谨慎使用`==`和`!=`：
- 如果你使用`==`或`!=`来比较两个布尔对象，则将使用引用操作符。这可能会导致意外的结果；请参阅“陷阱：使用来比较原始包装类对象如`Integer`”。
- `==`运算符很容易被误写为`=`。对于大多数操作数类型，这种错误会导致编译错误。然而，对于布尔型和`Boolean`类型操作数，该错误会导致错误的运行时行为；请参阅“陷阱 - 使用`=`来测试布尔值”。

## 引用 == 和 != 运算符

如果两个操作数都是引用，`==`和`!=`运算符将测试两个操作数是否指向同一个对象。这并不是你想要的。要测试对象的值是否相等，应该使用`.equals()`方法。

```java
String s1 = "We are equal";
String s2 = new String("We are equal");

s1.equals(s2); // true

// WARNING - 不要对 String 值使用 == 或 !=
s1 == s2; // false
```

警告：在大多数情况下，使用`==`和`!=`比较`String`值是不错误的；请参阅 http://stackoverflow.com/documentation/java/4388/java-pitfalls/16290/using-to-compare-strings 。类似的问题也适用于原始包装类类型；请参阅 http://stackoverflow.com/documentation/java/4388/java-pitfalls/8996/using-to-compare-primitive-wrappers-objects-such-as-integer。

## NaN 边界情况

JLS 15.21.1 规定如下：

如果其中任一个操作数是`NaN`，则`==`的结果为`false`，但`!=`的结果为`true`。事实上，测试`x != x`为真当且仅当`x`的值为`NaN`时。这种行为（对大多数程序员来说）是出意料之外的。如果你测试一个`NaN`值是否等于它本身，答案是“不，它不是！”换句话说，`==`对于`NaN`值不具有反射性。

然而，这并不是 Java 的“奇特性”，这种行为在 IEEE 754 浮点标准中是有规定的，你会发现大多数现代编程语言都实现了这一点。（更多信息，请参阅 http://stackoverflow.com/a/157315/139985 ... 注意这是某人在“房间里”写的）

## 40.12 节：Lambda 运算符 ( -> )

从 Java 8 开始，Lambda 运算符`->`被用于引入 Lambda 表达式。有两种常见的语法，如示例所示：

```java
// Java SE 8 版本
a -> a + 1 // 添加参数的 lambda
a -> { return a + 1; } // 使用块的 lambda
```

Lambda 表达式定义了一个匿名函数，或者实现函数接口的匿名类。（为了完整性，此处包含了示例。请参考 Lambda 表达式主题获取完整说明。）

# 第 41 章：构造函数

在 Java 中，构造函数对于实例化类对象至关重要。本节演示了 Java 类构造函数的正确用法。

## 41.1 节：默认构造函数

构造函数的“默认”情况是它们没有任何参数。如果你没有指定任何构造函数，编译器将为你生成一个默认构造函数。这意味着以下两个片段在语义上是等价的：

```java
public class TestClass {
    private String test;
}
```

```java
public class TestClass {
    private String test;
    public TestClass() {
    }
}
```

默认构造函数的可见性与类的可见性相同。然而，如果你有非默认构造函数，编译器将不会为你生成默认构造函数。所以这些是不等价的：

```java
public class TestClass {
    private String test;
    public TestClass(String arg) { }
}
```

```java
public class TestClass {
    private String test;
    public TestClass() { }
    public TestClass(String arg) { }
}
```

注意：生成的构造函数没有执行非标准初始化。这意味着你的类的所有字段将有默认值，除非它们有初始化器。

```java
public class TestClass {
    private String testData;
}
```

```java
public class TestClass {
    private String testData;
    public TestClass() {
        testData = "Test";
    }
}
```

构造函数的调用方式如下：`TestClass testClass = new TestClass();`。构造`Child`实例总是要求在`Child`构造函数的最开始处运行`Parent`构造函数。

## 41.2 节：调用父类构造函数

假设有一个`Parent`类和一个`Child`类。我们可以通过显式调用带有适当参数的`super(...)`来选择我们需要的`Parent`构造函数。这样做通过避免在`Child`类中重写相同的代码来节省时间。

没有`super(...)`方法（隐式地调用了无参数版本的`super()`）：

```java
class Parent {
    private String name;
    private int age;

    public Parent() {} // 因为我们调用了不带参数的 super()
    public Parent(String tName, int tAge) {
        name = tName;
        age = tAge;
    }
}
```

```java
// 这无法编译，因为 name 和 age 是私有的，
// 它们对子类是不可见的。
class Child extends Parent {
    public Child() {
        // 编译器在这里隐式调用了 super()
        name = "John";
        age = 42;
    }
}
```

带有`super()`方法：

```java
class Parent {
    private String name;
    private int age;
    public Parent(String tName, int tAge) {
        name = tName;
        age = tAge;
    }
}
```

```java
class Child extends Parent {
    public Child() {
        super("John", 42); // 显式调用 super
    }
}
```

注意：调用其他构造函数（链）或`super`构造函数必须是构造函数内部的第一语句。

如果你显式调用`super(...)`，则必须存在匹配的父类构造函数（这很简单，不是吗？）。如果你没有显式调用任何`super(...)`构造函数，你的父类必须有一个无参数构造函数——这可以：

```java
class Parent {
    public Parent(String tName, int tAge) {
    }
}
```

```java
class Child extends Parent {
    public Child() {
    }
}
```



```
class Child extends Parent {
public Child() {
}
}
```

## 41.3 节：带参数的构造函数

可以使用任何类型的参数创建构造函数。

```java
public class TestClass {
    private String testData;

public TestClass(String testData) {
    this.testData = testData;
}
}
```

调用方式如下：

类可以有多个不同签名的构造函数。要链接构造函数调用（调用同一类的不同构造函数），请使用`this`。

```java
public class TestClass {
    private String testData;

public TestClass() {
    this("Test"); // testData 默认为 "Test"
}
```

调用方式如下：`TestClass test1 = new TestClass("Test Data"); TestClass test2 = new TestClass();`

## 第 42 章：Object 方法和构造函数

此文档页面通过示例展示关于 Java 构造函数以及从任何新创建类的父类`Object`自动继承的`Object`方法的细节。

## 42.1 节：hashCode() 方法

当 Java 类重写`equals`方法时，它也应该重写`hashCode`方法。正如方法约定所定义的：

在 Java 执行期间，如果对同一个对象多次调用，只要用于等值比较的信息没有修改，`hashCode`方法必须始终返回相同的整数。该整数不需要在一次执行和另一个执行之间保持一致。如果两个对象根据`equals(Object)`方法是相等的，那么对这两个对象分别调用`hashCode`方法产生相同的整数结果。

并不要求如果两个对象根据`equals(Object)`方法是不相等的，那么对这两个对象分别调用`hashCode`方法必须产生不同的整数结果。然而，程序员应该意识到，产生不同的结果可能会提高哈希表的性能。

哈希值用于`HashMap`、`HashTable`和`HashSet`等哈希实现。`hashCode`函数的结果决定了对象放入哪个桶。如果提供的`hashCode`实现良好，这些哈希实现将更高效。良好的`hashCode`实现的一个重要属性是哈希值的分布是均匀的。也就是说，许多实例被存储在同一个桶中的概率很小。

计算哈希值的算法可能类似于以下：

```java
public class Foo {
private int field1, field2; private String field3;
public Foo(int field1, int field2, String field3) {this.field1 = field1;
this.field2 = field2;
this.field3 = field3;
}
```

```java
@Override
public boolean equals(Object obj) {
    if (this == obj) {
        return true;
    }
    if (obj == null || getClass() != obj.getClass()) {
        return false;
    }
    Foo f = (Foo) obj;
    return field1 == f.field1 &&
           field2 == f.field2 &&
           (field3 == null ? 0 : field3.equals(f.field3));
}
```

```java
public int hashCode() {
    int hash = 1;
    hash = 31 * hash + field1;
    hash = 31 * hash + field2;
    hash = 31 * hash + (field3 == null ? 0 : field3.hashCode());
    return hash;
}
```

使用`Arrays.hashCode()`作为简便方法 > Java SE 1.2

在 Java 1.2 中，无需开发算法来计算哈希值，可以通过提供一个包含字段值的对象或原始类型数组，使用`java.util.Arrays#hashCode`来生成哈希值：

```java
@Override
public int hashCode() {
    return Arrays.hashCode(new Object[] {field1, field2, field3});
}
```

Java 1.7 引入了`java.util.Objects`类，它提供了一个便利方法`hash(Object... objects)`，该方法根据所提供的对象值计算哈希值。该方法的工作原理与`java.util.Arrays#hashCode`相同。

```java
@Override
public int hashCode() {
    return Objects.hash(field1, field2, field3);
}
```

注意：这种方法效率较低，并且每次调用你自定义的`hashCode()`方法时都会产生垃圾对象：

- 创建了一个临时的`Object[]`。（在`Objects.hash()`版本中，数组是通过“可变参数”机制创建的）。

- 如果任何字段是原始类型，它们必须被装箱，并且可能会创建更多临时对象。数组必须被填充。

- 数组必须通过`Arrays.hashCode`或`Objects.hash`方法进行迭代。

- `Arrays.hashCode`或`Objects.hash`必须调用的`Object.hashCode()`调用（可能）没有被内联。

### 哈希值的内部缓存

由于计算对象的哈希值开销较大，因此在第一次计算哈希值时将其缓存在对象内部将是很有吸引力的。例如：

```java
public final class ImmutableArray {
    private int[] array;
    private volatile int hash = 0;

    public ImmutableArray(int[] initial) { 
        array = initial.clone(); 
    }

    // 其他方法

    public boolean equals(Object obj) { // ... }

    @Override
    public int hashCode() {
        int h = hash;
        if (h == 0) {
            h = Arrays.hashCode(array);
            hash = h;
        }
        return h;
    }
}
```

这种方法权衡了（重复）计算哈希值的成本与用于缓存哈希值的额外字段的开销。这种做法作为性能优化是否能成效，取决于给定对象被哈希（查找）的频率以及其他因素。

你还会注意到，如果`ImmutableArray`的真实哈希值恰好为 0（概率为 $2^{32}$ 次中的一次），则缓存将失效。

最后，如果被哈希的是可变对象，这种方法要正确实现要困难得多。然而，如果哈希值发生变化，会有更大的问题；请使用上述约定。

## 第 42.2 节：toString() 方法

`toString()`方法通过对象的内容创建对象的字符串表示。在编写你的类时，可以重写此方法。当对象连接到字符串时（如`"hello " + anObject`），`toString()`会被隐式调用。

考虑以下情况：

```java
public class User {
    private String firstName; 
    private String lastName;

    public User(String firstName, String lastName) { 
        this.firstName = firstName;
        this.lastName = lastName;
    }

    @Override
    public String toString() {
        return firstName + " " + lastName;
    }

    public static void main(String[] args) {
        User user = new User("John", "Doe");
        System.out.println(user.toString()); // 输出 "John Doe"
    }
}
```

在这里，`User`类重写了`Object`类的`toString()`，以便在打印对象时提供关于对象的有意义数据。

使用`println()`时，对象的`toString()`方法会被隐式调用。

因此，这些语句的作用是相同的：

```java
System.out.println(user); // 在 `user` 上隐式调用了 toString()
System.out.println(user.toString());
```

如果在上述`User`类中没有重写`toString()`，则`System.out.println(user)`可能会返回`User@659`。

### equals() 方法

`toString()`方法用于通过对象的内容创建对象的字符串表示。在编写你的类时可以重写此方法。当对象被连接到字符串时，`toString()`会被隐式调用。

考虑以下情况：TLDR：

- `==`测试引用相等性（它们是同一个对象）

- `equals()`测试逻辑相等性（它们的内容相等）

在`User`类中重写了`Object`类的`toString()`，以便在打印对象时提供关于对象的有意义数据。

使用`println()`时，对象的`toString()`方法会被隐式调用。

因此，这些语句的作用是相同的：

```java
System.out.println(user); // 在 `user` 上隐式调用了 toString()
System.out.println(user.toString());
```

如果在上述`User`类中没有重写`toString()`，则`System.out.println(user)`可能会返回`User@659`。

### 类比较

由于`equals`方法可以针对任何对象运行，该方法通常的第一件事（在检查空值之后）是检查被比较对象的类是否与当前类匹配。

```java
@Override
public boolean equals(Object obj) { //...检查空
    if (getClass() != obj.getClass()) { 
        return false;
    }
    //...比较字段
}
```

这通常如上述通过比较类对象来实现的。然而，在某些特殊的情况下，这种方法可能会失败。例如，某些框架会生成类的动态代理，而这些动态代理实际上是不同的类。这里有一个使用 JPA 的示例：

```java
Foo detachedInstance = ...
Foo mergedInstance = entityManager.merge(detachedInstance); 
if (mergedInstance.equals(detachedInstance)) {
    // 无法到达这里，因为 mergedInstance
    是 Foo 的代理（子类） 
}
```

绕过该局限性的一种机制是使用`instanceof`比较类。

```java
@Override
public final boolean equals(Object obj) { 
    if (!(obj instanceof Foo)) {
        return false;
    }
    //...比较字段
}
```

然而，在使用`instanceof`时有几个必须避免的陷阱。由于`Foo`可能会有其他子类，而这些子类可能会重写`equals()`方法，你可能会遇到一种情况：一个`Foo`等于`FooSubclass`，但`FooSubclass`并不等于`Foo`。

```java
Foo foo = new Foo(7);
FooSubclass fooSubClass = new FooSubclass(7, false);
foo.equals(fooSubClass) //true
fooSubClass.equals(foo) //false
```

这违反了对称性和传递性，因此是`equals()`方法的无效实现。因此，使用`instanceof`的做法是将`equals()`方法标记为`final`（如上面的示例所示）。这将确保没有子类重写`equals()`并违反核心假设。

## 第 42.4 节：wait() 和 notify() 方法

`wait()`和`notify()`协同工作——当一个线程对对象调用`wait()`时，该线程将会被阻塞，直到另一个线程在同一个对象上调用`notify()`或`notifyAll()`。

（参见：wait/notify()）



```java
package com.example.annotations.object;
import java.util.concurrent.atomic.AtomicBoolean;
public class WaitAndNotify {

    public static void main(String[] args) throws InterruptedException {
        Object obj = new Object();
        AtomicBoolean aHasFinishedWaiting = new AtomicBoolean(false);

        Thread threadA = new Thread("Thread A") {
            public void run() {
                System.out.println("A1: Could print before or after B1");
                System.out.println("A2: Thread A is about to start waiting...");
                try {
                    synchronized (obj) { // wait() 必须在同步块中 // 执行
                        // 线程 A 停止，直到调用 obj.notify()
                        obj.wait();
                    }
                    System.out.println("A3: Thread A has finished waiting. " + "Guaranteed to happen after B3");
                } catch (InterruptedException e) {
                    System.out.println("Thread A was interrupted while waiting");
                } finally {
                    aHasFinishedWaiting.set(true);
                }
            }
        };

        Thread threadB = new Thread("Thread B") {
            public void run() {
                System.out.println("B1: Could print before or after A1");
                System.out.println("B2: Thread B is about to wait for 10 seconds");
                for (int i = 0; i < 10; i++) {
                    try {
                        Thread.sleep(1000); // 休睡 1 秒
                    } catch (InterruptedException e) {
                        System.err.println("Thread B was interrupted from waiting");
                    }
                }
                System.out.println("B3: Will print before A3 since " + "A3 can happen after obj.notify().");

                while (!aFinishedWaiting.get()) {
                    synchronized (obj) {
                        // 通知调用了 obj.wait() 的线程
                        obj.notify();
                    }
                }
            }
        };

        threadA.start();
        threadB.start();
        threadA.join();
        threadB.join();
        System.out.println("Finished!");
    }
}
```

一些示例输出：

```
A1: Could print before or after B1
B1: Could print before or after A1
A2: Thread A is about to start waiting...
B2: Thread B is about to wait for 10 seconds
B3: Will print before A3 since A3 can happen after obj.notify().
A3: Thread A has finished waiting. Guaranteed to happen after B3
Finished!
```

```
B1: Could print before or after A1
B2: Thread B is about to wait for 10 seconds
A1: Could print before or after B1
A2: Thread A is about to start waiting...
B3: Will print before A3 since A3 can happen after obj.notify().
A3: Thread A has finished waiting. Guaranteed to happen after B3
Finished!
```

```
A1: Could print before or after B1
A2: Thread A is about to start waiting...
B1: Could print before or after A1
B2: Thread B is about to wait for 10 seconds
B3: Will print before A3 since A3 can happen after obj.notify().
A3: Thread A has finished waiting. Guaranteed to happen after B3
Finished!
```

## 第 42.5 节：`getClass()` 方法

`getClass()` 方法可以用于查找对象的运行时类型。参见下面的示例：

```java
class User {
    private long userID;
    private String name;

    public User(long userID, String name) {
        this.userID = userID;
        this.name = name;
    }
}

class SpecificUser extends User {
    private String specificID;

    public SpecificUser(String specificID, long userID, String name) {
        super(userID, name);
        this.specificID = specificID;
    }
}

public static void main(String[] args) {
    User user = new User(82945, "John");
    SpecificUser specificUser = new SpecificUser("AAAA", 87777, "Jim");
    User anotherSpecificUser = new SpecificUser("BBBB", 12345, "Jenny");

    System.out.println(user.getClass()); // 输出 "class User"
    System.out.println(specificUser.getClass()); // 输出 "class SpecificUser"
    System.out.println(anotherSpecificUser.getClass()); // 输出 "class SpecificUser"
}
```

定义。

那么如何从 `Object` 类中的构造函数创建对象呢？

对象的实际创建由 JVM 处理。Java 中的每个构造函数都表现为一个名为 `<init>` 的特殊方法，负责实例初始化。这个 `<init>` 方法由编译器提供，由于 `<init>` 在 Java 中不是合法的标识符，因此在语言中无法直接使用。

JVM 如何调用 `<init>` 方法？

JVM 将使用 `invokespecial` 指令来调用 `<init>` 方法，且只能在未初始化的类实例上调用。Java 语言规范：

特殊方法 (JVM) - JVMS - 2.9 构造函数 - JLS - 8.8

## 第 42.8 节：`finalize()` 方法

这是 `Object` 类的一个保护且非静态方法。该方法用于在对象从内存中移除之前对其执行最终操作或清理操作。

根据文档，当垃圾回收器确定某个对象不再有任何引用时，会在垃圾回收时对该对象调用此方法。

但是，如果对象仍然可达，或者在对象符合条件时没有运行垃圾回收器，则无法保证 `finalize()` 会被调用。这就是为什么最好不要依赖此方法的原因。

在 Java 核心库中可以找到一些示例，例如 `FileInputStream.java`：

```java
protected void finalize() throws IOException {
    if ((fd == null) && (fd != FileDescriptor.in)) {
```

> /* 如果 fd 是共享的，FileDescriptor 中的引用 * 将确保只有在安全这样做时才调用终结器。所有使用 fd * 的引用都已变得不可达。我们可以调用 close() */

```java
close();
}
}
```

在这种情况下，如果该资源之前没有被关闭，那么这就是关闭该资源的最后机会。

通常，在任何类型的应用程序中使用 `finalize()` 方法被认为是一种坏习惯，应该避免。

终结器（Finalizers）并不是为了释放资源（例如关闭文件）。只有当系统 (!) 运行堆空间不足时，才会调用垃圾回收器。你不能依赖它在系统文件句柄不足或任何其他原因时被调用。

终结器的预想用例是通知某个即将回收的对象其正面临终结。现在存在一种更好的机制：`lang.ref.WeakReference<T>`。如果你认为需要 `finalize()` 方法，应该从更深层次上重新思考你的设计。

进一步阅读请参考 Joshua Bloch 的《Effective Java》中关于 `finalize()` 方法的内容。

## 第 43 章：注解 (Annotations)

在 Java 中，注解是一种可以添加到源代码中的语法元数据形式。它提供了关于程序本身的数据。注解对它们所标记的代码的操作没有直接影响。类、方法、变量和包都可以被标记的。

## 43.1 节：注解背后的想法

Java 语言规范对注解描述如下：注解是一个标记，将信息与程序结构关联起来，但在运行时没有影响。

注解可能出现在类型或声明之前。一个注解具体应用于哪些位置，由“元注解” `@Target` 决定。更多信息请参见“定义注解类型”。

注解有许多用途。像 Spring 和 Spring-MVC 这样的框架使用注解来定义依赖注入或请求路由。

Lombok 和 JPA 使用注解生成 Java（以及 SQL）代码。

本主题旨在提供概述：

- 如何定义注解？

- 注解在实践如何如何？

## 第 43.2 节：定义注解类型

注解类型使用 `@interface` 定义。参数的定义与方法类似。

```java
@interface MyAnnotation {
String param1();
boolean param2();
int[] param3();
```

默认值

```java
@interface MyAnnotation {
String param1() default "someValue"; boolean param2() default true; int[] param3() default {};
```

## 元注解 (Meta-Annotations)

元注解是可以应用于注解类型的注解。

特殊的预定义元注解定义了注解类型如何被使用。

`@Target` 元注解限制了注解可以应用于类型。

```java
@Target(ElementType.METHOD)
@interface MyAnnotation {
// 此注解只能应用于方法
}
```

可以使用数组符号添加多个值，例如 `@Target({ElementType.FIELD, ElementType.TYPE})`

可用值

| ElementType | target | 描述 |

| :--- | :--- | :--- |

| ANNOTATION_TYPE | 注解类型 | |

| CONSTRUCTOR | 构造函数 | |

| FIELD | 字段、枚举常量 | |

| LOCAL_VARIABLE | 方法内部的变量声明 | |

| PACKAGE | 包 (package-info.java) | 方法 |

| PARAMETER | 方法/构造函数参数 | |

| TYPE | 类、接口、枚举 | |

| Version ≥ Java SE & ElementType | | |

| :--- | :--- | :--- |

| @Deprecated | | 非常旧的； |

| @XmlElement | | |

```java
目标元素示例 @Retention(RetentionPolicy.RUNTIME)
@interface MyAnnotation
@MyAnnotation MyClass() {
@XmlAttribute int count;
for (@LoopVariable int i = 0; i < 100; i++) { @Unused
String result; }
}
```

```java
public Rectangle(@NamedArg("width") double width,
@NamedArg("height") double height) {
...
}
```

```java
@XmlRootElement class Report {}
```

target_PARAMETER 目标元素示例

TYPE_PARAMETER 类型声明

```java
public <@MyAnnotation T> void f(T t) {}
```

TYPE_USE 使用类型 `Object o = "42"; String s = (@MyAnnotation String) o;` @Retention

`@Retention` 元注解定义了注解在应用程序编译或执行期间的可见性。默认情况下，注解包含在类文件中但在运行时不可。要使注解在运行时可用，必须在该注解上设置 `RetentionPolicy.RUNTIME`。

```java
@Retention(RetentionPolicy.RUNTIME)
@interface MyAnnotation {
// 此注解在运行时可以使用反射访问
}
```

## 可用值

| RetentionPolicy | 效果 |

| :--- | :--- |

| CLASS | 注解在 .class 文件可用，但在运行时不可用 |

| RUNTIME | 注解在运行时可用，可以通过反射访问 |

| SOURCE | 注解在编译时可用，但未添加到 .class 文件中。注解可以被注解处理器使用 |

## @Documented

`@Documented` 元注解用于标记那些用法应该被 javadoc 等 API 文档生成器记录的注解。它没有值。有了 `@Documented`，所有使用该注解的类都会在生成的文档页面上列出该注解。如果没有 `@Documented`，无法看到哪些类使用了该注解。

## @Inherited

`@Inherited` 元注解适用于应用于类的注解。它没有值。将注解标记为 `@Inherited` 会改变注解查询的工作方式。

对于不可继承的注解，查询只检查被检查的类。

对于可继承的注解，查询还将检查父类链（递归地），直到找到该注解的实例。

注意，查询的是父类：附加到类层次结构接口上的任何注解将被忽略。

## @Repeatable

`@Repeatable` 元注解是在 Java 8 中引入的。它表示多个注解实例可以附加注解的目标。该元注解没有值。

## 43.3 节：通过反射进行运行时注解检查

Java Reflection API 允许程序员在运行时对类字段、方法和注解执行各种检查和操作。然而，为了让注解在运行时可见，必须更改为 `RUNTIME`，如下例所示：



## 第 43.4 节：内置注解

Java 标准版（Standard Edition）自带了一些预定义的注解。你不需要自己定义它们，可以立即使用。它们允许编译器对方法、类和代码进行某些基础检查。

### `@Override`

此注解应用于方法，表示该方法必须重写父类方法或实现抽象父类的方法定义。如果此注解用于其他类型的方法，编译器将抛出错误。

```java
// 具体父类
public class Vehicle {
    public void drive() {
        System.out.println("I am driving"); 
    }
}
```

```java
class Car extends Vehicle {
    // 正确
    @Override
    public void drive() {
        System.out.println("Brrmrm, brrmrm"); 
    }
}
```

抽象类：

```java
abstract class Animal {
    public abstract void makeNoise();
}

class Dog extends Animal {
    // 正确
    @Override
    public void makeNoise() {
        System.out.println("Woof");
    }
}

// 无法工作
class Logger1 {
    public void log(String logString) { 
        System.out.println(logString); 
    }
}

class Logger2 {
    // 这会导致编译时错误。Logger2 不是 Logger1 的子类。
    // log 方法没有重写任何内容
    @Override
    public void log(String logString) {
        System.out.println("Log 2" + logString);
    }
}
```

其主要目的是捕捉拼写错误，即你认为你正在重写一个方法，但实际上是在定义一个新方法。

```java
class Vehicle {
    public void drive() {
        System.out.println("I am driving");
    }
}

class Car extends Vehicle {
    // 编译器错误。"drive" 不是正确的重写方法名。
    @Override
    public void drive() {
        System.out.println("Brrrm, brrm");
    }
}
```

注意，`@Override` 的含义随着时间发生了变化：

- 在 Java 5 中，它意味着被注解的方法必须重写父类链中声明的非抽象方法。
- 从 Java 6 开始，如果被注解的方法实现了在类的父类 / 接口层级结构中声明的抽象方法，也满足该条件。

（这在将代码回移植到 Java 5 时偶尔会导致问题。）

### `@Deprecated`

此标记将该方法标记为已弃用（deprecated）。可能有以下几个原因：

- API 设计存在缺陷且不实际修复，
- 使用该 API 可能会导致错误，
- 该 API 已被其他 API 代替，
- 该 API 已过时，
- 该 API 是实验性的，可能会发生不兼容的更改，
- 或上述任何因素的组合。

弃用的具体原因通常可以在 API 的文档中找到。如果你使用该注解，编译器将输出错误。IDE 也可能以某种方式突出显示此方法为已弃用。

```java
class ComplexAlgorithm {
    @Deprecated
    public void oldSlowUnthreadSafeMethod() {
        // 此处为内容
    }

    public void quickThreadSafeMethod() { // 客户端代码应该使用此方法
    }
}
```

### `@SuppressWarnings`

在几乎所有情况下，当编译器发出警告时，最合适的操作是修复原因。在某些实例（例如，泛型代码使用类型安全的预泛型代码），这可能是不可行的。

```java
if (!name.startsWith("set")) {
    printError(method, "setter name must start with \"set\"");
} else if (name.length() == 3) {
    printError(method, "the method name must contain more than just \"set\"");
} else if (Character.isLowerCase(name.charAt(3))) {
    if (method.getParameters().size() != 1) {
        printError(method, "character following \"set\" must be upper case");
    }
}

// check, if setter is public
if (!method.getModifiers().contains(Modifier.PUBLIC)) {
    printError(method, "setter must be public");
}
// check, if method is static
if (method.getModifiers().contains(Modifier.STATIC)) { 
    printError(method, "setter must not be static"); 
}
}

private void printElement(Element element, String message) {
    messenger.printMessage(Diagnostic.Kind.ERROR, message, element);
}
```

```java
@Override
public void init(ProcessingEnvironment processingEnvironment) {
    super.init(processingEnvironment);

    // get messenger for printing errors
    messenger = processingEnvironment.getMessenger();
}
```

## 打包

为了让编译器应用，注解处理器需要对 SPI 可用（参见 `ServiceLoader`）。

要做到这一点，除了其他文件外，还需要在包含注解处理器和注解的 jar 包中添加名为 `META-INF/services/javax.annotation.processing.Processor` 的文本文件。该文件需要包含注解处理器的全限定名，即它看起来应该像这样：

```
annotation.processor.SetterProcessor
```

在下文中，我们假设 jar 文件名为 `AnnotationProcessor.jar`。

### 示例被注解的类

以下类是默认包中的一个示例类，注解已根据保留策略应用到正确的元素上。然而，注解处理器仅将第二个方法视为有效的注解目标。

```java
import annotation.Setter;
public class AnnotationProcessorTest {
  @Setter
  private void setValue(String value) {}
  @Setter
  public void setString(String value) {}
  @Setter
  public static void main(String[] args) {
} }
```

### 使用 javac 使用注解处理器

如果通过 SPI 发现了该注解处理器，它将自动被用于处理被注解的元素。例如，使用 `javac -cp AnnotationProcessor.jar AnnotationProcessorTest.java` 编译 `AnnotationProcessorTest` 类将产生以下输出：

```
AnnotationProcessorTest.java:6: error: setter must be public private void
setValue(String value) {}
^
AnnotationProcessorTest.java:12: error: setter name must start with "set"
public static void main(String[] args) {
^
```

2 个错误

而不是正常编译。没有创建 `.class` 文件。

这可以通过为 `javac` 指定 `-proc:none` 选项来防止。你也可以通过指定 `-proc:instead` 来伪造常规编译。

### IDE 集成 Netbeans

注解处理器可以在 NetBeans 编辑器中使用。要做到这一点，需要在项目设置中指定注解处理器：

1. 转到 Project Properties > Build > Compiling
2. 勾选 Enable Annotation Processing 和 Enable Annotation Processing in Editor
3. 点击注解处理器列表旁边的 Add
4. 在弹出的窗口中输入注解处理器的全限定类名

```java
import annotation.Descriptor;
public class Annotation extends MyAnnotation {
    @Retention(RetentionPolicy.RUNTIME)
    @Descriptor
    private void setVal(String value) {
}
    @Descriptor
    public void setString(String value) {
}
    @Descriptor
    public static void main(String[] args) {
}
}
```

## 第 43.6 节：重复注解

在 Java 8 之前，同一个注解的两个实例无法应用于单个元素。标准的变通方法是使用一个容器注解来持有某种其他注解的数组：

```java
// Author.java
@Retention(RetentionPolicy.RUNTIME)
public @interface Author {

    String value();
}
```

```java
// Authors.java
@Retention(RetentionPolicy.RUNTIME)
public @interface Authors {

    Author[] value();
}
```

```java
// Test.java
@Authors({
    @Author("Mary"),
    @Author("Sam")
})
```

```java
public class Test {
    public static void main(String[] args) {
        Author[] authors = Test.class.getAnnotation(Authors.class).value();
        for (Author author : authors) {
            System.out.println(author.value());
            // 输出:
            // Mary
            // Sam
        }
    }
}
```

Java 8 提供了一种更简洁、更透明的方法来使用容器注解，即使用 `@Repeatable` 注解。首先我们将其添加到 `Author` 类中：

```java
@Repeatable(Authors.class)
```

这告诉 Java 将多个 `@Author` 注解就像被 `@Author` 容器包围一样。我们还可以使用 `Class.getAnnotationsByType()` 通过其自身的类来访问 `@Author` 数组，而不是通过它的容器：

```java
@Author("Mary")
@Author("Sam")
public class Test {
```

```java
public static void main(String[] args) {
    Author[] authors = Test.class.getAnnotationsByType(Author.class);
    for (Author author : authors) {
        System.out.println(author.value());
        // 输出:
        // Mary
        // Sam
    }
}
```

## 第 43.7 节：继承的注解

默认情况下，注解不会从类继承到子类。这可以通过在注解定义中添加 `@Inherited` 注解来改变。

### 示例

考虑以下注解：

```java
@Inherited
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
public @interface InheritedType {
}
```

如果类是这样注解的：

```java
@InheritedType
class A { }
```

```java
@InheritedType
class B extends A { }
```

```java
class C extends B { }
```

运行代码将产生类似于此结果（取决于具体的包）：

```
InheritedType
InheritedType
InheritedType
```

注意，注解不能从接口继承。

## 第 43.8 节：运行时获取注解值

你可以通过反射获取应用了注解的方法、字段或类，获取当前的注解属性，并获取所需的属性。

```java
@Retention(RetentionPolicy.RUNTIME) 
@interface MyAnnotation {
    String key() default "foo"; 
    String value() default "bar";
}
```



```java
class AnnotationExample {
    // 将注解应用到方法上，但保留默认值
    @MyAnnotation
    public void testDefaults() throws Exception {

        // 使用反射，获取公共方法 "testDefaults", 
        方法
        Method method = Annotation =.class.getMethod("testDefaults", null);
        // 获取类型为 MyAnnotation 的注解
        MyAnnotation annotation = (MyAnnotation)method.getAnnotation(MyAnnotation.class);
        // 打印注解的设置
annotation);
    }

    // 将注解应用到方法上，但覆盖设置
    @MyAnnotation(key="baz", value="buzz")
    public void testValues() throws Exception {
        // 使用反射，获取公共方法 "testValues", 
方法
with         args Method method = AnnotationExample.class.getMethod("testValues", null);
        // 获取类型为 MyAnnotation 的注解
        MyAnnotation annotation = (MyAnnotation)method.getAnnotation(MyAnnotation.class);
        // 打印注解的设置
annotation);
    }

    public void print(MyAnnotation annotation) {
        // 获取 MyAnnotation 的 'key' 和 'value' 属性，并打印它们
        System.out.println(annotation.key() + " = " + annotation.value());
    }

    public static void main(String[] args) {
        AnnotationExample example = new AnnotationExample();
        try {
            example.testDefaults();
            example.testValues();
        } catch (Exception e) {
            // 不应该抛出任何注解
            System.err.println("Exception [" + e.getClass().getName() + "] - " + e.getMessage());
            e.printStackTrace(System.err);
        }
    }
}
```

输出将是

foo = bar baz = buzz

# 第 43.9 节：针对 `this` 和接收者参数的注解

Java 注解最初引入时，并没有规定对实例方法的目标或内部类构造函数的隐藏构造函数参数进行注解。这在 Java 8 中通过增加“接收者参数”声明得到了解决；请参阅 JLS 8.4.1。

接收者参数（receiver parameter）是实例方法或内部类构造函数可选的语法设备。对于实例方法，接收者参数代表调用该方法的对象。对于内部类的构造函数，接收者参数代表新构造对象的直接外层实例。无论何种情况，接收者参数的存在都仅仅是为了允许在源代码中标明所表示对象的类型，以便对该类型进行注解。接收者参数不是形式参数；更准确地说，它不是任何形式的变量声明（§4.12.3），它永远不会绑定到作为方法调用表达式或限定类实例创建表达式中的参数传递的任何值，并且在运行时没有任何影响。

下面的示例说明了这两种接收者参数的语法：

```java
public class Outer {
  public class Inner {
    public Inner (Outer this) {

      // ...
    }

    public void doit(Inner this) {

      // ...
    }
  }
}
```

接收者参数的唯一目的是允许你添加注解。例如，你可能有一个自定义注解 `@IsOpen`，其目的是断言在调用方法时 `Closeable` 对象未被关闭。例如：

```java
public class MyResource extends Closeable {
public void update(@IsOpen MyResource this, int value) { // ...
}
public void close() { // ...
}
```

在某种层面上，此 `this` 上的 `@IsOpen` 注解可以仅作为文档。然而，我们可能可以做更多。例如：

注解处理器可以插入一个运行时检查，确保在调用 `update` 时对象未处于关闭状态。代码检查器可以执行静态代码分析，找到在调用 `update` 时该对象可能被关闭的情况。

# 第 43.10 节：添加多个注解值

如果注解参数（Annotation parameter）被定义为数组，它可以接受多个值。例如，标准注解 `@SuppressWarnings` 的定义如下：

```java
public @interface Suppress { String[] value(); }
```

`value` 参数是一个 `String` 数组。你可以使用类似于数组初始化器的符号来设置多个值：

```java
@SuppressWarnings("unused")

@SuppressWarnings({"unused", "javadoc"})
```

如果你只需要设置单个值，可以省略括号：

```java
@SuppressWarnings("unused")
```

# 第 44 章：不可变类

不可变对象（Immutable objects）是在初始化后状态不会改变的实例。例如，`String` 是一个不可变类，一旦实例化，其值永远不会改变。

# 第 44.1 节：无可变引用的示例

```java
public final class Color {
    final private int red;
    final private int green;
    final private int blue;

    private void check(int red, int green, int blue) {
        if (red < 0 || red > 255 || green < 0 || green > 255 || blue < 0 || blue > 255) {
            throw new IllegalArgumentException();
        }
    }

    public Color(int red, int green, int blue) {
        check(red, green, blue);
        this.red = red;
        this.green = green;
        this.blue = blue;
    }

    public Color invert() {
        return new Color(255 - red, 255 - green, 255 - blue);
    }
}
```

# 第 44.2 节：不可变性的优势是什么？

不可变性的优势在于并发性。在可变对象中维护正确性是困难的，因为多个线程可能会尝试更改同一个对象的状态，导致某些线程根据对该对象的读写时机，看到同一个对象的不同状态。

通过使用不可变对象，可以确保所有查看该对象的线程都将看到相同的状态，因为不可变对象的状态不会改变。

# 第 44.3 节：定义不可变类的规则

以下规则定义了创建不可变对象的简单策略：

1. 不要提供“setter”方法——修改字段或其所引用对象的方法。
2. 将所有字段声明为 `final`。
3. 将类声明为 `final`。
4. 如果字段包含可变对象，请创建副本。
5. 不要共享指向可变状态的引用。
6. 永远不要存储指向原始对象的引用。

# 第 44.4 节：带有可变引用的示例

在这种情况下，`Point` 是可变的，用户可以修改其状态。

```java
class Point {
    private int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public int getX() {
        return x;
    }

    public void setX(int x) {
        this.x = x;
    }

    public int getY() {
        return y;
    }

    public void setY(int y) {
        this.y = y;
    }
}
```

```java
public final class ImmutableCircle {
  private final Point center;
  private final double radius;

  public ImmutableCircle(Point center, double radius) {
    this.center = new Point(center.getX(), center.getY());
    this.radius = radius;
  }

  public Point getCenter() {
    return new Point(center.getX(), center.getY());
  }

  public double getRadius() {
    return radius;
  }
}
```

# 第 45 章：不可变对象

# 第 45.1 节：使用防御拷贝创建不可变版本

Java 中的某些基本类型和类本质上是可变的。例如，所有数组类型都是可变的，`java.util.Date` 等类也是如此。在强制要求不可变类型的情况下，这很麻烦。处理此问题的方法是为可变类型创建一个不可变包装。这里有一个整数数组的简单包装：

```java
public class ImmutableArray {
  private final int[] array;

  public ImmutableArray(int[] array) {
    this.array = array.clone();
  }

  public int[] getValue() {
    return array.clone();
  }
}
```

该类通过防御拷贝将可变状态（`int[]`）与可能修改它的代码隔离：

构造函数使用 `clone()` 创建参数数组的副本。

如果调用者随后更改了参数数组，不会影响 `ImmutableArray` 的状态。

`getValue()` 方法也使用 `clone()` 创建要返回的数组。

调用者如果更改了结果数组，不会影响 `ImmutableArray` 的状态。

我们可以为 `ImmutableArray` 添加方法，对包装的数组执行只读操作；例如获取其长度、获取特定索引的值等。

注意，通过这种方式实现的不可变包装类型与原始类型并不兼容。你不能简单地用前者替换后者。

# 第 45.2 节：不可变类的配方

不可变对象是状态无法改变的对象。不可变类是在设计和实现上都是不可变的类。Java 中最常作为不可变性示例的类是 `java.lang.String`。

以下是一个典型的示例：

```java
public final class Person {
  private final String name;
  private final String ssn; // (SSN == 社会安全号码)
}
```

```java
public Person(String name, String ssn) { 
  this.name = name; 
  this.ssn = ssn;
}

public String getName() { return name; }
```

```java
public String getSSN() { return ssn; }
}
}
```

这种方法的变体是将构造函数声明为私有，并改为提供一个公共静态工厂方法。

不可变类的标准配方如下：

- 所有属性都必须在构造函数（s）或工厂方法（s）中设置。
- 不应该有 setter 方法。
- 如果为了接口兼容性而必须包含 setter 方法，它们应该要么什么都不做，要么抛出异常。
- 所有属性都应该声明为 `private` 和 `final`。
- 对于所有引用到可变类型的属性：
    - 该属性应该通过构造函数传递的值的深拷贝进行初始化，且属性的 getter 方法应该返回该属性值的深拷贝。
- 类应该声明为 `final`，以防止有人创建不可变类的可变子类。

还需要注意的另外几点：

不可变性并不防止对象为空；例如，`null` 可以赋值给 `String` 变量。如果不可变类的属性被声明为 `final`，则实例本质上是线程安全的。这使得不可变类成为实现多线程应用程序的良好构建块。

## 第 45.3 节：阻止类变为不可变的典型设计缺陷

### 使用了某些 setter 方法，但未在构造函数（s）中设置所有必要的属性

```java
public final class Person { // 一个错误的不可变性示例
private final String name;
private final String surname;

public Person(String name) {
    this.name = name;
}
public String getName() { return name; }
public String getSurname() { return surname; }
public void setName(String surname) { this.name = surname; }
```

很容易证明 `Person` 类不是不可变的：

```java
Person person = new Person("Joe");

person.setSurname("Average"); // 不可以，创建后更改了 surname 字段
```

要修复它，只需删除 `setName()` 并按照如下方式重构构造函数：

```java
public Person(String name, String surname) { 
    this.name = name;
    this.surname = surname;
}
```

### 未将实例变量标记为 `private` 和 `final`

看下这个类：

```java
public final class Person { 
    public String name;
    public Person(String name) {
        this.name = name;
    }
    public String getName() { return name; }
}
```

下面的代码片段显示了上面的类不是不可变的：

```java
Person person = new Person("Average Joe");

person.name = "Magic Mike"; // 不可以，创建后更改了人的名字
```

要修复它，只需将 `name` 属性标记为 `private` 和 `final`。

### 在 getter 中暴露了类的可变对象

看下这个类：

```java
import java.util.List;
import java.util.ArrayList;

public final class Names {
    private final List<String> names;
    public Names(List<String> names) {
        this.names = new ArrayList<String>(names);
    }
    public List<String> getNames() {
        return names;
    }
    public int size() {
        return names.size();
    }
}
```

`Names` 类初看起来是不可变的，但正如下面的代码所示，它并不是：

```java
List<String> namesList = new ArrayList<String>();
namesList.add("Average Joe");
Names names = new Names(namesList);
System.out.println(names.size()); // 1, 只包含 "Average Joe"
namesList = getNames();
namesList.add("Magic Mike");
System.out.println(names.size()); // 2, 不可以，现在 names 也包含了 "Magic Mike"
```

发生这种情况是因为对 `getNames()` 返回的引用列表的更改可以修改 `Names` 的实际列表。

要修复此，只需通过防御拷贝（如下所示）避免返回引用该类可变对象的引用：



```java
public List<String> getNames() {
    return new ArrayList<String>(this.names); // 拷贝元素
}
```

或者设计 `getter` 方法使其只返回其他不可变对象和原始类型，如下所示：

```java
public String getName(int index) {
    return names.get(index);
}

public int size() {
    return names.size();
}
```

### 注入了可以在不可变类外部被修改的对象

这是上一个缺陷的变体。看下这个类：

```java
import java.util.List;
public final class NewNames {
    private final List<String> names;
    public NewNames(List<String> names) { 
        this.names = names;
    }
    public String getName(int index) { 
        return names.get(index);
    }
    public int size() {
        return names.size();
    }
}
```

和之前的 `Names` 类一样，`NewNames` 类初看起来也是不可变的，但实际上并不是，下面的代码片段证明了相反的：

```java
List<String> namesList = new ArrayList<String>();
namesList.add("Average Joe");
NewNames names = new NewNames(namesList);
System.out.println(names.size()); // 1, 只包含 "Average Joe"
namesList.add("Magic Mike");
System.out.println(names.size()); // 2, 不可以，现在 names 也包含了 "Magic Mike"
```

要修复它，像上一个缺陷一样，只需对对象进行防御拷贝而不将其直接赋值给不可变类，即构造函数可以更改如下：

```java
public NewNames(List<String> names) {
    this.names = new ArrayList<String>(names);
}
```

### 让类的方法被重写

看下这个类：

```java
public class Person {
    private final String name;
    public Person(String name) {
        this.name = name;
    }
    public String getName() { return name; }
}
```

`Person` 类初看起来是不可变的，但假设一个 `Person` 的新子类：

```java
public class MutablePerson extends Person { 
    private String newName;
    public MutablePerson(String name) {
        super (name);
    }
    @Override
    public String getName() {
        return newName;
    }
    public void setName(String name) {
        newName = name;
    }
}
```

现在可以通过多态使用新的子类来利用 `Person` 的（不）不可变性：

```java
Person person = new MutablePerson("Average Joe");
System.out.println(person.getName()); // 打印 Average Joe
person.setName("Magic Mike"); // 不可以，person 现在有一个名字了！
System.out.println(person.getName()); // 打印 Magic Mike
```

要修复它，要么将类标记为 `final` 以使其无法扩展，要么将其所有构造函数声明为 `private`。

# 第 46 章：可见性（控制对类成员的访问）

## 第 46.1 节：私有可见性 (Private)

`private` 可见性允许变量仅被类访问。它们通常与公共的 `getter` 和 `setter` 结合使用。

```java
class SomeClass {
    private int variable;

    public int getVariable() {
        return variable;
    }

    public void setVariable(int variable) {
        this.variable = variable;
    }
}

public class SomeOtherClass {
    public static void main(String[] args) {
        SomeClass sc = new SomeClass();
        // 这些语句无法编译，因为 SomeClass.variable 是私有的：
        // sc.variable = 7;
        // System.out.println(sc.variable);

        // 取而，你应该使用公共的 getter 和 setter：
        sc.setVariable(7);
        System.out.println(sc.getVariable());
    }
}
```

## 第 46.2 节：公共可见性 (Public)

对类、包和子类可见。

让我们看 `Test` 类的例子：

```java
public class Test{
    public int number = 2;
    public Test(){
    }
}
```

现在让我们尝试创建该类的实例。在这个例子中，我们可以访问 `number` 因为它是公共的。

```java
public class Other{
    public static void main(String[] args){
        Test t = new Test();
        System.out.println(t.number);
    }
}
```

## 第 46.3 节：包可见性 (Package)

如果没有修饰符，默认是包可见性。根据 Java 文档，“包可见性表示与类类相同包的类（无论其父类是什么）是否有权访问该成员。”在 `javax.swing` 的这个示例中，

```java
package javax.swing;
public abstract class JComponent extends Container { ... 
static boolean DEBUG_GRAPHICS_LOADED;
```

`DebugGraphics` 在同一个包中，所以 `DEBUG_GRAPHICS_LOADED` 是可访问。

```java
package javax.swing;
public class DebugGraphics extends Graphics { ...
    static {
        JComponent.DEBUG_GRAPHICS_LOADED = true;
    }
}
```

本文提供了关于该主题的一些背景。

## 第 46.4 节：保护可见性 (Protected Visibility)

保护可见性意味着该成员对其所在的包以及它的任何子类可见。

示例下：

```java
package com.stackexchange.docs;
public class MyClass{
    protected int variable; // 这是我们正尝试访问的变量
    public MyClass() {
        variable = 2;
    }
}
```

我们将扩展这个类并尝试访问它的其中一个保护成员。

```java
package some.other.pack;
import com.stackexchange.docs.MyClass;
public class SubClass extends MyClass{

    public SubClass(){
        super();
        System.out.println(super.variable);
    }
}
```

如果你在同一个包中访问一个保护成员，即使不继承它，也可以进行访问。

请注意，该修饰符仅作用于类的成员，而不作用于类本身。

## 第 46.5 节：类成员访问修饰符总结

| 访问修饰符 | 可见性 | 继承 |

| :--- | :--- | :--- |

| Private | 仅类内 | 无法继承 |

| 无修饰符 / 包 | 包内 | 如果子类在包内则可用 |

| Protected | 包内 | 在子类中可用 |

| Public | 各处 | 在子类中可用 |

曾经存在过 `private protected`（同时使用两个关键字）修饰符，它可以应用于方法或变量，使其可以从包外的子类访问，但对该包内的类是私有的。然而，这在 Java 1.0 发布时被删除了。

## 第 46.6 节：接口成员

```java
public interface MyInterface {
    public void foo();
    int bar();

    public String TEXT = "Hello";
    int ANSWER = 42;
}
public class X {
}
class Y {
}
```

接口成员始终具有公共可见性，即使省略了 `public` 关键字。因此，`foo()`、`bar()`、`TEXT`、`ANSWER`、`X` 和 `Y` 都具有公共可见性。然而，访问可能仍受包含接口的限制——由于 `MyInterface` 具有公共可见性，其成员可以从任何地方访问；但如果 `MyInterface` 具有包可见性，其成员只能在同一个包内访问。

## 第 47 章：泛型 (Generics)

泛型是泛型编程的一种机制，它扩展了 Java 的类型系统，允许类型或方法对各种类型的对象进行操作，同时提供编译时的类型安全。特别是 Java 集合框架支持泛型来指定存储在集合实例中的对象类型。

## 第 47.1 节：创建泛型类

泛型允许类、接口和方法采用其他类和接口作为类型参数。

此示例使用泛型类 `Param` 来接收单个类型参数 `T`，用角括号 `<>` 分隔。

```java
public class Param<T> {
    private T value;

    public T getValue() {
        return value;
    }

    public void setValue(T value) {
        this.value = value;
    }
}
```

要实例化此类，请提供一个类型参数来代替 `T`。例如 `Integer`：

`Param<Integer> integerParam = new Param<Integer>();`

类型参数可以是任何引用类型，包括数组和其他泛型类型：

`Param<String[]> arrayParam, Param<int[]> int2dArrayParam;`

`Param<Object> objectNestedParam;`

在 Java SE 7 及更高版本中，类型参数可以替换为空的类型参数集 `<>`，这被称为菱运算符（diamond）：

版本 > Java SE 7

`Param<Integer> integerParam = new Param<>();`

与其他标识符不同，类型参数没有命名限制。但它们的名称通常是其用途的首字母大写形式。（这在官方 JavaDocs 中也是如此）。示例包括 `T` 代表 "type"类型），`E` 代表 "element"元素）以及 `K/V` 代表 "key"/"value"键值）。

```java
public abstract class AbstractParam<T> { 
    private T value;

    public T getValue() { return value; }

    public void setValue(T value) { this.value = value; }
}
```

`AbstractParam` 是一个带有类型参数 `T` 的抽象类。在扩展此类时，该类型参数可以被写在 `<>` 内部的类型参数替换，也可以保持类型参数不变。在下面的两个示例中，`String` 和 `Integer` 替换了类型参数。在第三个示例中，类型参数保持不变。第四个示例完全没有使用泛型，因此它类似于类使用了 `Object`。编译器会警告 `AbstractParam` 是一个原始类型（raw type），但它可以通过编译。第五个示例有两个类型参数（请见下文的“多个类型参数”），选择第二个参数作为传递给父类的类型。

```java
public class Email extends AbstractParam<String> { ... }
```

```java
public class Age extends AbstractParam<Integer> { ... }
```

```java
public class Height<T> extends AbstractParam<T> { ... }
```

```java
public class ObjectParam extends AbstractParam { ... }
```

```java
public class MultiParam<T, E> extends AbstractParam<E> { ... }
```

以下是用法：

```java
Email email = new Email();
String retrievedEmail = email.getValue();

Age age = new Age();
Integer retrievedAge = age.getValue();

Height<Integer> heightInInt = new Height<>();
Height<Float> heightInFloat = new Height<>();
MultiParam<String, Double> multiParam = new MultiParam<>();
```

注意在 `Email` 类中，`getValue()` 方法的行为就像它具有 `String getValue()` 签名一样，而 `void setValue(T)` 方法的行为就像被声明为 `void setValue(String)`。也可以使用带有空大括号的匿名内部类进行实例化：

```java
AbstractParam<Double> height = new AbstractParam<Double>(){};
```

注意，在匿名类中使用菱运算符是不允许的。多个类型参数：Java 提供了在泛型类或接口中使用多个类型参数的能力。通过在角括号之间放置由逗号分隔的类型列表，可以在类或接口中使用多个类型参数。示例：

```java
public class MultiParam<T, S> {
    private T firstParam;
    private S secondParam;

    public MultiParam(T firstParam, S secondParam) {
        this.firstParam = firstParam;
        this.secondParam = secondParam;
    }

    public T getFirstParam() { return firstParam; }
    public void setFirstParam(T firstParam) { this.firstParam = firstParam; }

    public S getSecondParam() { return secondParam; }
    public void setSecondParam(S secondParam) { this.secondParam = secondParam; }
}
```

用法如下：

```java
Param<String, String> aParam = new MultiParam<>("value1", "value2");
Param<Integer, Double> dayOfWeek = new MultiParam<>(1, 2);
```

`objects.add(new IPhone()); // 不是一个水果`

`//fruitHelper.eatAll(objects); // 编译错误：可能也包含鞋子！`

选择正确的 `T`、`? super T` 或 `extends T` 对于允许子类型使用是必要的。编译器可以确保类型安全；如果你正确地使用它们，就不需要进行类型转换（类型转换不是类型安全的，可能会导致编程错误）。

如果难以理解，请记住 PECS 规则：生产者（Producer）使用 `Extends`，消费者（Consumer）使用 `Super`。（生产者只有写访问权限，消费者只有读访问权限）

## 第 47.3 节：菱形语法 (The Diamond)

版本 ≥ Java SE 7



# Java 泛型详解

## 菱形语法

Java 7 引入了菱形语法来消除泛型类实例化时的样板代码。在 Java 7+ 中，你可以写：

```java
List<String> list = new LinkedList<>();
```

而在之前的版本中，你必须这样写：

```java
List<String> list = new LinkedList<String>();
```

一个局限性是匿名类，在实例化时，你仍然必须提供类型参数：

```java
// 这将可以通过编译：
Comparator<String> caseInsensitiveComparator = new Comparator<String>() {
    @Override
    public int compare(String s1, String s2) {
        return s1.compareToIgnoreCase(s2);
    }
};
```

```java
// 但这个不能通过编译：
Comparator<String> caseInsensitiveComparator = new Comparator<>() {
    @Override
    public int compare(String s1, String s2) {
        return s1.compareIgnoreCase(s2);
    }
};
```

### 版本 > Java SE 8

虽然 Java 7 和 8 不支持在匿名内部类中使用菱形语法，但它将作为新功能包含在 Java 9 中。

**脚注：**

1. 有人将 `<>` 的用法称为“菱形运算符”。这是错误的。菱形并不作为运算符运行，在 JLS（Java 语言规范）或（官方）Java 教程中也没有将其作为运算符描述或列出。事实上，`<>` 甚至不是一个独立的 Java 标记。它是一个 `<` 标记后跟一个 `>` 标记，在两者之间添加空格或注释是合法的（尽管风格较差）。JLS 和教程一律将 `<>` 称为“菱形”，因此这是它的正确术语。

## 第 47.4 节：声明泛型方法

方法也可以具有泛型类型参数。

```java
public class Example {
    // 类型参数 T 的作用域限于方法，且与其他方法的类型
    // 参数无关。
    public <T> List<T> makeList(T t1, T t2) {
        List<T> result = new ArrayList<T>();
        result.add(t1);
        result.add(t2);
        return result;
    }
    public void usage() {
        List<String> listString = makeList("Jeff", "Atwood");
        List<Integer> listInteger = makeList(1, 2);
    }
}
```

注意，我们不需要为泛型方法传递实际的类型参数。编译器会根据目标类型（例如我们为结果赋值的变量）或实际参数的类型，为我们推断类型参数。它通常会推断出使调用类型正确的最具体的类型参数。

有时（尽管罕见），但可能需要用显式类型参数来覆盖这种类型推断：

```java
void usage() {
    consumeObjects(this.<Object>makeList("Jeff", "Atwood").stream());
}

void consumeObjects(Stream<Object> stream) { ... }
```

在这个例子中这是必要的，因为编译器在调用 `stream()` 之后无法“向前看”看到 `T` 需要 `Object`，否则它将根据 `makeList` 的参数推断出 `String`。注意，当显式提供类型参数时，Java 不支持省略调用方法的类或对象（上述示例中的 `this` 部分）。

## 第 47.5 节：要求多个上界 ("extends A & B")

你可以要求泛型类型扩展多个上界。例如：我们想要对数字列表排序，其中 `Number` 没有实现 `Comparable`。

```java
public <T extends Number & Comparable<T>> void sortNumbers(List<T> n) {
    Collections.sort(n);
}
```

在这个例子中，`T` 必须扩展 `Number` 并实现 `Comparable<T>`，这符合所有“正常”的内置数字实现（如 `Integer` 或 `BigDecimal`），但不符合更奇特的实现（如 `Stripe64`）。

由于不允许多重继承，你最多可以扩展一个类作为边界，并且必须是第一个列出的。例如，`<T extends Comparable<T> & Number>` 是不允许的，因为 `Comparable` 是一个接口而不是类。

## 第 47.6 节：在运行时获取满足泛型参数的类

许多未绑定的泛型参数（如在静态方法中使用的）在运行时无法恢复（参见类型擦除中的其他线程）。但是有一种通用的策略用于在运行时访问类上满足泛型参数的类型。这允许依赖于类型访问的泛型代码无需在每次调用中传递类型信息。

### 背景

可以通过创建一个匿名内部类来检查类上的泛型参数化。该类将捕获类型信息。通常这种机制被称为“超类型令牌（super type tokens）”，它们在 Neal Gafter 的博客文章中有详细介绍。

### 实现

Java 中三种常见的实现是：

- Guava 的 `TypeToken`
- Spring 的 `ParameterizedTypeReference`
- Jackson 的 `TypeReference`

### 示例用法

```java
public class DataService<MODEL_TYPE> {
    private final Class<MODEL_TYPE> type = new TypeToken<MODEL_TYPE>(){}.getType();

    public List<MODEL_TYPE> getAll() {
        return null;
    }
}

class TypeToken<T> {
    private final Type type;
    public TypeToken() {
        Type superclass = getClass().getGenericSuperclass();
        type = ((ParameterizedType) superclass).getActualTypeArguments()[0];
    }
    public Type getType() {
        return type;
    }
}

class DataDao {
    public List<User> getAll() {
        return new ArrayList<>();
    }
}

class UserService extends DataService<User> { }

class Main {
    public static void main(String[] args) {
        UserService service = new UserService();
        List<User> users = service.getAll();
    }
}

class User { }
```

*(注：由于原文提供的代码片段在示例中存在断裂，翻译时根据逻辑补全了部分代码结构)*

## 第 47.7 节：使用泛型边界创建类型安全的容器

如果没有边界泛型（bounded generics），我们无法创建一个既是泛型又知道每个元素都是动物的容器类：

```java
public class AnimalContainer<T> {
    private Collection<T> col;

    public AnimalContainer() {
        col = new ArrayList<T>();
    }

    public void add(T t) {
        col.add(t);
    }

    public void printAllSounds() {
        for (T t : col) {
            // 错误，类型 T 没有 makeSound() // 它被用作 java.lang.Object 使用
            System.out.println(t.makeSound());
        }
    }
}
```

在类定义中使用泛型边界后，这现在是可能的：

```java
public class BoundedAnimalContainer<T extends Animal> {
    private Collection<T> col;

    public BoundedAnimalContainer() {
        col = new ArrayList<T>();
    }

    public void add(T t) {
        col.add(t);
    }

    public void printAllSounds() {
        for (T t : col) {
            // 现在可以工作了，因为 T 继承了 Animal
            System.out.println(t.makeSound());
        }
    }
}
```

这还限制了泛型类型的有效实例化：

```java
// 合法
AnimalContainer<Cat> a = new AnimalContainer<Cat>();
// 合法
AnimalContainer<String> a = new AnimalContainer<String>();
// 合法，因为 Cat 继承 Animal
BoundedAnimalContainer<Cat> b = new BoundedAnimalContainer<Cat>();
// 不合法，因为 String 没有继承 Animal
BoundedAnimalContainer<String> b = new BoundedAnimalContainer<String>();
```

## 第 47.10 节：在声明内部引用已声明的泛型类型

如何在正在声明的方法声明内部使用一个（可能进一步继承的）泛型类型的实例？这是当你深入研究泛型时会遇到的问题之一，但仍然是一个相当常见的问题。

假设我们有一个 `DataSeries<T>` 类型（这里是一个接口），它定义了一个包含类型 `T` 值的泛型序列。当我们对例如 `double` 值进行大量操作时，直接处理这种类型很繁琐，因此我们定义了 `DoubleSeries` 继承 `DataSeries<Double>`。现在假设原始的 `DataSeries<T>` 类型有一个方法 `add(values)`，它添加另一个相同长度的序列并返回一个新的序列。我们如何在派生类中强制值的类型和返回类型为 `DoubleSeries` 而不是 `DataSeries<Double>` 呢？

可以通过添加一个泛型类型参数引用并扩展正在声明的类型来解决此问题（这里应用于接口，类的情况也一样）：

```java
public interface DataSeries<T, DS extends DataSeries<T, DS>> {
    DS add(DS values);
    List<T> data();
}
```

`T` 代表序列所持的数据类型，例如 `Double`，`DS` 代表序列本身。一个继承的类型（或多个类型）现在可以通过上述参数替换为相应的派生类型来轻松实现，从而产生一个基于 `Double` 的具体定义：

```java
public interface DoubleSeries extends DataSeries<Double, DoubleSeries> {
    static DoubleSeries instance(Collection<Double> data) {
        return new DoubleSeriesImpl(data);
    }
}
```

此时，即使是 IDE 也会使用正确的类型实现基础接口，在填充一些内容后，它看起来可能像这样：

```java
class DoubleSeriesImpl implements DoubleSeries {
    private final List<Double> data;

    DoubleSeriesImpl(Collection<Double> data) {
        this.data = new ArrayList<>(data);
    }

    @Override
    public DoubleSeries add(DoubleSeries series) {
        List<Double> incoming = series != null ? series.data() : null;
        if (incoming == null || incoming.size() != data.size()) {
            throw new IllegalArgumentException("bad series");
        }

        List<Double> newdata = new ArrayList<>(data.size());
        for (int i = 0; i < data.size(); i++) {
            newdata.add(this.data.get(i) + incoming.get(i)); // 注意自动装箱
        }
        return DoubleSeries.instance(newdata);
    }

    @Override
    public List<Double> data() {
        return Collections.unmodifiableList(data);
    }
}
```

如你所示，`add` 方法可以工作。

## 第 47.11 节：引用多个泛型类型

泛型参数也可以使用 `&` 绑定到多一个类型。假设你想创建一个同时继承自 `Type1` 和 `Type2` 的类：

```java
class Example<T extends Type1 & Type2> {
}
```

当你需要一个类型实现多个接口或扩展特定类时，这非常有用。

## 第 47.12 节：使用泛型创建类型安全的访问器

使用泛型可以返回调用者期望的任何内容：

```java
private Map<String, Object> data;
public <T> T get(String key) {
    return (T) data.get(key);
}
```

这种方法更安全，因为它避免了调用处的手动强制转换。

## 第 47.13 节：instanceof 的使用

使用泛型在 `instanceof` 中定义类型。考虑以下示例：

```java
class Example<T> {
    public boolean isTypeString(String s) {
        return s instanceof T; // 编译错误，不能将 T 作为类型
    }
}
```

这将始终导致编译错误，因为编译器将 Java 源码编译成 Java 字节码时，会应用一种称为类型擦除（type erasure）的过程，使得在运行时无法区分 `T` 类型。用于 `instanceof` 的类型必须是可重化的（reifiable），这意味着关于该类型的所有信息在运行时都是可用的，而对于泛型类型通常不是如此。

以下类代表了两个 `Example` 类（`Example<String>` 和 `Example<Number>`）在泛型被擦除移除后的样子：

```java
class Example {
    public boolean isTypeAString(String s) {
        return s instanceof Object; // <String> 和 <Number> 现在都是 Object
    }
}
```

由于类型已经消失，JVM 无法知道哪种类型是 `T`。作为上述规则的例外，你也可以使用无界通配符 (`?`) 在 `instanceof` 中指定类型，如下：

```java
public boolean isList(Object obj) {
    return obj instanceof List<?>;
}
```

这可以用于判断实例 `obj` 是否为 `List`：

```java
System.out.println(isList("foo")); // 输出 false
System.out.println(isList(new ArrayList<String>())); // 输出 true
System.out.println(isList(new ArrayList<Float>())); // 输出 true
```

事实上，无界通配符被认为是一种可重化的类型。

### 使用 instanceof 使用泛型实例

硬币的另一面是，使用 `T` 的实例 `t` 进行 `instanceof` 判断是合法的，如下所示：

```java
class Example<T> {
    public boolean isTypeAString(T t) {
        return t instanceof String; // 这次没有编译错误
    }
}
```

因为擦除后该类将如下所示：

```java
class Example { // 形式参数消失了
    public boolean isTypeString(Object t) {
        return t instanceof String; // 这次不会有编译错误
    }
}
```

由于如果发生了类型擦除，现在 JVM 现在可以区分内存中的不同类型，即使它们使用相同的引用类型（`Object`），如下代码段所示。



```java
Object obj1 = new String("foo"); // 引用类型 Object，对象类型 String
Object obj2 = new Integer(11); // 引用类型 Object，对象类型 Integer
System.out.println(obj1 instanceof String); // true
System.out.println(obj2 instanceof String); // false，是一个 Integer，不是 String
```

## 47.14 节：实现泛型接口的不同方式（或扩展泛型类）

假设已经声明了以下泛型接口：

```java
public interface MyGenericInterface<T> {
public void foo(T t);
}
```

下面是列出的实现方法。

### 使用特定类型的非泛类实现

选择一个特定类型来替换`MyGenericClass`的形式类型参数`<T>`并实现它，如下例所示：

```java
public class NonGenericClass implements MyGenericInterface<String> {
public void foo(String t) { } // 类型 T 已被 String 替换
}
```

此类仅处理`String`，这意味着使用不同参数（例如`Integer`、`Object`等）使用`MyGenericInterface`将无法通过编译，如下代码段所示：

```java
NonGenericClass myClass = new NonGenericClass();
myClass.foo("foo_string"); // OK，合法
myClass.foo(11); // NOT OK，无法编译
myClass.foo(new Object()); // NOT OK，无法编译
```

### 泛型类实现

声明另一个带有形式类型参数`<T>`的泛型接口来实现`MyGenericInterface`，如下所示：

```java
public class MyGenericSubclass<T> implements MyGenericInterface<T> {
public void foo(T t) { // 类型 T 保持相同 // 其他方法...

}

}
```

注意，可能使用了不同的形式类型参数，如下：

```java
public class MyGenericSubclass<U> implements MyGenericInterface<U> {
// 等同于之前的声明
public void foo(U t) {
// 其他方法...

}

}
```

### 原始类实现

声明一个非泛型类作为原始类型（raw type）实现`MyGenericInterface`（不使用泛型），如下所示：

```java
public class MyGenericSubclass implements MyGenericInterface { 
public void foo(Object t) { // 类型 T 已被 Object 替换 // 其他可能的方法

}

}
```

这种方法是不推荐的，因为它在运行时不是 100% 安全的，因为它将原始类型（子类的）与泛型（接口的）混淆了一起，而且令人困惑。现代 Java 编译器会对这种实现发出警告，但为了与旧版 JVM（1.4 或更早版本）兼容，它可以通过编译。

当使用泛型类作为父类型而不是泛型接口时，上述列出的方法也是允许的。

## 48 章：类与对象

对象具有状态和行为。例如：狗有状态——颜色、名字、品种，以及行为——摇尾巴、汪叫、吃。对象是类的实例。

类 – 类可以被定义为模板/蓝图，描述了该类型对象所支持的行为/状态。

## 48.1 节：方法重载

有时需要为不同类型的输入编写相同的功能。此时，可以使用相同的方法名配合不同的参数集。每组不同的参数被称为“方法签名”。如示例所示，单个方法可以有多个签名。

```java
public class Displayer
public void displayName(String firstName) {
System.out.println("Name is: " + firstName);
}
public void displayName(String firstName, String lastName) {
System.out.println("Name is: " + firstName + " " + lastName);
}
public static void main(String[] args) {
Displayer display = new Displayer();
displayer.displayName("Ram"); // 打印 "Name is: Ram"
displayer.displayName("Jon", "Seket"); // 打印 "Name is: Seket"
}
}
```

优点是可以用两个不同的输入数量调用相同的功能。当我们根据传递的输入调用方法时（在这种情况下，要么是一个字符串值或两个字符串值），将执行对应的方法。

方法可以被重载：

1. 基于传递的参数数量。

示例：`method(String s)`和`method(String s1, String s2)`。

2. 基于参数的顺序。

示例：`method(int i, float f)`和`method(float f, int i)`。

注意：方法不能通过更改返回类型来重载（`int method()`被视为与`String method()`相同，并在尝试时会抛出`RuntimeException`）。如果你更改了返回类型，必须也更改参数以实现重载。

## 48.2 节：解释方法重载和重写

方法重写（Overriding）和重载（Overloading）是 Java 支持的两种多态形式。

### 方法重载

方法重载（也称为静态多态）是在类类中两个（或多个）同名方法（函数）的方法。

### 方法重写

方法重写（是的，你猜对了，它被称为动态多态）是一个稍微有趣且复杂的话。在方法重写中，我们覆盖了父类提供的方法体。

```java
public abstract class Shape{
public abstract Double area(){ return 0.0; }
}
```

我们有一个名为`Shape`的类，它有一个名为`area`的方法，可能会返回形状的面积。假设我们现在有两个类：`Circle`（圆形）和`Rectangle`（矩形）。

```java
public class Circle extends Shape { private Double radius = 5.0;
    @Override
    public Double area() {
        return 3.14 * radius;
    }
}
```

同样的矩形类：

```java
public class Rectangle extends Shape { private Double length = 5.0; private Double breadth=10.0;
    @Override
    public Double area() {
        return length * breadth;
    }
}
```

因此，你的两个子类都更新了父类（`Shape`）提供的方法体。现在是如何查看结果？让我们用传统的`psvm`方法来实现。

```java
public class AreaFinder
public static void main(String[] args) {
    //这会创建一个圆形对象 Shape shape = new Circle();
    //这会创建一个矩形对象 Shape rectangle = new Rectangle();
    System.out.println(shape.area()); // 这应该打印 78.5
    System.out.println(rectangle.area());
}
}
```

```java
System.out.println("Shape of circle : "+circle.area());

//This should print 50.0
System.out.println("Shape of rectangle: "+rectangle.area());
}}
```

哇，这不棒吗？相同类型的两个对象调用方法并返回不同的值。朋友，这就是动态多态的力量。

这里有一张表可以更好地比较这两者的区别：

## 方法重载 (Method Overloading)

方法重载用于提高程序的可读性。

方法重载在类内部进行。

在方法重载的情况下，参数必须不同。

方法重载是编译时多态的示例。

在 Java 中，不能仅通过改变方法的返回值来实现方法重载。在方法重载中，返回类型可以相同也可以不同。

但你必须更改参数。

## 方法重写 (Method Overriding)

方法重写用于为父类已提供的方法提供特定的实现。

方法重写发生在具有 IS-A（继承）关系的两个类中。

在方法重写的情况下，参数必须相同。

方法重写是运行时多态的示例。

在方法重写中，返回类型必须相同或是协变的（covariant）。

## 第 48.3 ：构造函数 (Constructors)

构造函数是与类同名且没有返回类型的特殊方法，用于构建对象。构造函数像方法一样可以接收输入参数。构造函数用于初始化对象。抽象类也可以有构造函数。

```java
public class Hello{
//构造函数
public Hello(String wordToPrint){
    printHello (wordToPrint);
}
public void printHello(String word{
    System.out.println(word);
}
// 在创建时实例化对象并打印内容 //
// wordToPrint
```

理解构造函数与方法在几个方面的不同非常重要：

- 1. 构造函数只能使用`public`、`private`和`protected`修饰符，不能声明为`abstract`、`final`、`static`或`synchronized`。

2. 构造函数没有返回类型。

3. 构造函数的名称必须与类名相同。在`Hello`示例中，`Hello`对象的构造函数名称与类名相同。

4. `this`关键字在构造函数内部有额外的用法。`this.method(...)`调用当前实例上的方法，而`this(...)`指向当前类中具有不同签名的另一个构造函数。

构造函数还可以通过继承使用`super`关键字调用。

```java
public class SuperManClass
public SuperManClass(){ //某些实现
}
// ... 方法 ...
public class BatmanClass extends SuperManClass{ 
    public BatmanClass{
    super();
    }
// ... 方法 ...
}
```

参见 Java 语言规范 #8.8 和 #15.9

## 第 48.4：使用静态初始化器初始化 static final 字段

为了初始化需要使用多个单一表达式的`static final`字段，可以使用静态初始化器来赋值。以下示例初始化了一个不可修改的`String`集合：

```java
public class MyClass {
public static final Set<String> WORDS;

static {
    Set<String> set = new HashSet<String>(); 
    set.add("Hello");
    set.add("World");
    set.add("bar");
    set.add("42");
    WORDS = Collections.unmodifiableSet(set);
}
```

## 第 48.5：基础对象的构建与使用

对象属于它们自己的类，因此一个简单的例子是汽车（详细解释见下文）：

```java
public class Car {
// 描述单辆汽车特征的变量，随对象异
private int milesPerGallon;
private String name;
private String color;
public int numGallonsInTank;

// 这是创建单个对象的地方
public Car(int mpg, int gallonsInTank, String carName, String color){
    milesPerGallon = mpg;
    name = carName;
    color = color;
    numGallonsInTank = gallonsInTank;
}

// 使对象更具实性的方法

```java

// 汽车需要行驶

public void drive(int distanceInMiles){

    // 获取汽车剩余的英里

    int miles = numGallonsInTank * milesPerGallon;

    // 检查汽车是否有足够的油行驶 distanceInMiles

    if (miles <= distanceInMiles){

        numGallonsInTank = numGallonsInTank - (distanceInMiles / MilesPerGallon);

        System.out.println("行驶了 " + numGallonsInTank + " 英里！"); 

    } else {

        System.out.println("无法行驶！");

    }

}

```

```java

public void paintCar(String newColor){ color = newColor;}

```

```java

// 设置新的每加仑英里

public void setMPG(int newMPG){ milesPerGallon = newMPG;}

```

```java

// 设置新的油箱加仑数 

public void setGallonsInTank(int numGallons){ numGallonsInTank = numGallons; }

```

```java

public void nameCar(String newName){ name = newName; }

```

```java

// 获取汽车颜色

public String getColor(){ return color; }

```

```java

// 获取汽车名称

public String getName(){ return name; }

// 获取加仑数 

public String getGallons(){ return numGallonsInTank; }

}

```

对象是其类的实例。因此，创建对象的方法是在主类中通过两种方式之一调用`Car`类（Java 中的`main`方法或 Android 中的`onCreate`）。

## 方案 1

`newCar = new Car(30, 10, "Ferrari", "Red");`

方案 1 是在创建对象时实际上向程序提供了有关汽车的所有信息。更改汽车的任何属性都需要调用其中一个方法，例如`paintCar`方法。例如：
`newCar.paintCar("Blue");`

注意：确保向方法传递正确的数据类型。在上面的示例中，只要数据类型正确，你也可以向`paintCar`方法传递变量。

以上是更改对象属性的示例，接收对象属性需要使用`Car`类中具有返回值的方法（即非`void`方法）。例如：
`String myCarName = newCar.getName();` // 返回字符串 "Ferrari"

当在创建时拥有所有对象数据时，方案 1 是最佳方案。

## 方案 2

`newCar = new Car();`
方案 2 效果相同，但需要更多工作。当在创建时没有所有数据并在稍后设置时，方案 2 是最佳方案。

成员存在于实例中，每个实例都有一个独立的拷贝。这意味着你需要访问该类的对象才能访问其成员。

## 第 49 章：局部内部类

在 Java 中，在方法内部创建的类被称为局部内部类。如果你想调用局部内部类的方法，必须在方法内部实例化该类。

### 第 49.1 节：局部内部类

```java

public class localInner {

    private int data=30;//实例变量

    void display(){

        class Local {

        void msg(){System.out.println(data);

        }

        Local l1=new Local();

        l1.msg();

    }

    public static void main(String args[]){

        localInner obj=new localInner();

        obj.display();

    }

}

```

## 第 50 章：嵌套类与内部类

使用 Java，开发者有能力在一个类内部定义另一个类。这种类被称为嵌套类（Nested Class）。如果嵌套类被声明为非静态（non-static），它们被称为内部类（Inner Classes），否则它们被称为静态嵌套类（Static Nested Classes）。本页旨在记录并提供示例，说明如何使用嵌套类和内部类。

### 第 50.1 节：使用嵌套类实现的简单栈

```java



# 第 50 章：内部类

## 第 50.1 节：基础示例

`public class IntStack` 是一个使用内部类的示例：

```java
public class IntStack {

  private IntStackNode head;

  // IntStackNode 是 IntStack 类的内部类
  // 该内部类的每个实例都作为它所帮助表示的
  // 栈中的一个节点

  private static class IntStackNode {

    private int val;

    private IntStackNode next;

    private IntStackNode(int v, IntStackNode n) {

      next = v;

    }

    public void push(int v) {

      head = new IntStackNode(v, head);

      return this;

    }

    public int pop() {

      int x = head.val;

      head = head.next;

      return x;

    }

  }

}
```

其使用方法（注意的是）完全没有承认嵌套类的存在。

```java
public class Main {

  public static void main(String[] args) {

    IntStack s = new IntStack();

    s.push(4).push(3).push(2).push(1).push(0);

    // 输出: 0, 1, 2, 3, 4,

  }

}
```

```java
for(int i = 0; i < 5; i++) {

  System.out.print(s.pop() + ", ");

}
```

### 第 50.2 节：静态与非静态嵌套类

在创建嵌套类时，你面临选择将该嵌套类为静态的：

```java
public class OuterClass1 {

  private static class StaticNestedClass {

}
```

或者非静态的：

```java
public class OuterClass2 {

  private class NestedClass {

}
```

从核心上说，静态嵌套类没有外类的周围实例，而非静态嵌套类有。这影响了允许在何时何地实例化嵌套类，以及允许哪些嵌套类实例进行访问。补充上面的示例：

```java
public class OuterClass1 {

  private int aField; 

  public void aMethod(){

    private static class StaticNestedClass { 

      private int innerField;

      private StaticNestedClass() {

        innerField = aField; // 非法，无法在静态上下文中访问 aField

        aMethod(); // 非法，无法在静态上下文中调用 aMethod

      }

      private StaticNestedClass(OuterClass1 instance) { 

        innerField = instance.aField; // 合法

      }

    }

  }

  public static void aStaticMethod() {

    NestedClass s = new NestedClass(); // 合法，可以在静态上下文中构造

    // 执行涉及 s 的操作...

  }

}
```

```java
public class OuterClass2 {

    private int aField;

    public void aMethod() {}

    private class NestedClass { 

        private int innerField;

        private NestedClass() {

            innerField = aField; // 合法

        }

        void aMethod(); // 合法

    }

    public void aNonStaticMethod() {

        NestedClass s = new NestedClass(); // 合法

    }

    public static void aStaticMethod() {

        NestedClass s = new NestedClass(); // 非法。在没有周围 OuterClass2 实例的情况下无法构造

        // 因为这是静态上下文，没有周围的 OuterClass2 实例

    }

}
```

因此，你对静态与非静态的选择主要取决于你是否需要直接访问外类的字段和方法，尽管这也会影响你可以在何时何地构造嵌套类。

作为一个经验法则，除非你需要访问外类的字段和方法，否则请将你的嵌套类设为静态。这与将字段设为私有（除非你需要公开）类似，这减少了对嵌套类的可见性（通过不允许访问外部实例），降低了错误的概率。

### 第 50.3 节：内部类的访问修饰符

可以在此处找到 Java 中访问修饰符的完整解释。但它们是如何与内部类相互作用的呢？

`public` 一如往常，对任何能够访问该类型的范围提供无限制的访问。

```java
public class OuterClass {

    public class InnerClass {

        int x = 5;

    }

    public InnerClass createInner() { return new InnerClass(); }

}
```

默认修饰符（无修饰符）允许在同一个包内访问。

```java
public class OuterClass {

    class InnerClass {

        int x = 5;

    }

    InnerClass createInner() { return new InnerClass(); }

}
```

`protected` 修饰符允许在同一个包内以及子类中访问。

```java
public class OuterClass {

    protected class InnerClass {

        int x = 5;

    }

    protected InnerClass createInner() { return new InnerClass(); }

}
```

`private` 修饰符限制仅外部类本身访问。

```java
public class OuterClass {

    private class InnerClass {

        int x = 5;

    }

    private InnerClass createInner() { return new InnerClass(); }

}
```

`public` 修饰符允许任何类访问。

```java
public class OuterClass {

    public class InnerClass {

        int x = 5;

    }

    public InnerClass createInner() { return new InnerClass(); }

}
```

通过将内部类标记为私有，它无法在外部类之外使用。

```java
public class OuterClass {

    private class InnerClass {

        int x = 5;

    }

    public InnerClass createInner() { return new InnerClass(); }

}
```

### 第 50.4 节：匿名内部类

匿名内部类是在一个语句中声明并实例化的内部类形式。结果是，该类没有可以在程序其他地方使用的名称；即它是匿名的。匿名类通常用于需要作为参数传递的轻量级类的情况。这通常通过接口完成。例如：

```java
public static Comparator<String> CASE_INSENSITIVE = new Comparator<String>() {

    @Override

    public int compare(String string1, String string2) {

        return string1.toUpperCase().compareTo(string2.toUpperCase());

    }

};
```

这个匿名类定义了一个 `Comparator<String>` 对象（`CASE_INSENSITIVE`），忽略大小写比较两个字符串。其他频繁实现并实例化匿名类的接口是 `Runnable` 和 `Callable`。例如：

```java
// 匿名 Runnable 类用于提供一个 Thread 在启动时运行的实例。
Thread t = new Thread(new Runnable() {

    @Override

    public void run() {

        System.out.println("Hello world");

    }

});
```

`t.start();` // 输出 "Hello world"

匿名内部类也可以基于类。在这种情况下，匿名类隐式地扩展了现有类。如果被扩展的类是抽象的，那么匿名类必须实现所有抽象方法。它也可以重写非抽象方法。

# 构造函数

匿名类没有显式构造函数。相反，定义了一个隐式构造函数，它使用 `super(...)` 将任何参数传递给被扩展类的构造函数。例如：

```java
SomeClass anon = new SomeClass(1, "happiness") {

    @Override

    public int someMethod(int arg) {

        // 执行某些操作

    }

};
```

我们 `SomeClass` 匿名子类的隐式构造函数将调用匹配 `SomeClass(int, String)` 签名的 `SomeClass` 构造函数。如果没有可用构造函数，你将得到编译错误。匹配的构造函数抛出的任何异常也会由隐式构造函数抛出。

自然，这在扩展接口时是不起作用的。当你从接口创建匿名类时，该类的父类是 `java.lang.Object`，它仅有一个无参构造函数。

## 第 50.5 节：从外部创建非静态内部类的实例

对任何外部类可见的内部类也可以从该类中创建。内部类依赖于外部类，并需要对外部类实例的引用。要创建内部类的实例，需要在外部类的一个实例上调用 `new` 运算符。

```java
class OuterClass {

    class InnerClass {

    }

    class OutsideClass {

        OuterClass outer = new OuterClass();

        OuterClass.InnerClass createInner() {

            return outer.new InnerClass();

        }

    }

}
```

用法方式为 `outer.new`。

## 第 50.6 节：方法局部内部类

在方法内部编写的类称为方法内部类。在这种情况下，内部类的作用域被限制在方法内部。方法局部内部类只能在定义其内部类的方法中实例化。使用方法局部内部类的示例：

```java
public class OuterClass {

    private void outerMethod() {

        final int outerInt = 1;

        // 方法局部内部类

        class MethodLocalInnerClass {

            private void print() {

                System.out.println("Method local inner class " + outerInt);

            }

            // 访问内部类

            MethodLocalInnerClass inner = new MethodLocalInnerClass();

            inner.print();

        }

    }

}
```

```java
public static void main(String[] args) {

    OuterClass outer = new OuterClass();

    outer.outerMethod();

}
```

执行后将得到输出：
`Method local inner class 1.`

## 第 50.7 节：从非静态内部类访问外部类

对外部类的引用使用类名和 `this`：

```java
public class OuterClass {

    public class InnerClass {

        public void method() {

            System.out.println("I can access my enclosing class: " + OuterClass.this);

        }

    }

}
```

你可以直接访问外部类的字段和方法。

```java
public class OuterClass { 

    private int counter;

    public class InnerClass {

        public void method() {

            System.out.println("I can access " + counter);

        } 

    }

}
```

但在名称冲突的情况下，你可以使用外部类引用。

```java
public class OuterClass { 

    private int counter;

    public class InnerClass { 

        private int counter;

        public void method() {

            System.out.println("My counter: " + counter);

            System.out.println("Outer counter: " + OuterClass.this.counter);

            // 更新我的计数器

            counter = OuterClass.this.counter;

        }

    }

}
```

# 第 52 章：默认方法

Java 8 引入的默认方法允许开发者在不破坏现有实现的情况下向接口添加新方法。它提供了灵活性，允许接口定义一个实现，当类未能提供实现时将用作默认实现。

### 第 52.1 节：默认方法的基本用法

```java
/**
 * 带有默认方法的接口
 */

public interface Printable {

  default void printString() {

    System.out.println("default implementation");

  }

}
```

```java
/**
 * 回退到默认实现的类
 */

public class MyClass implements Printable {

}
```

```java
/**
 * 覆盖默认方法的类
 */

public class CustomClass implements Printable {

    @Override

    public void printString() {

        System.out.println("custom implementation");

    }

}
```

执行上述代码将输出：
`default implementation` 或
`custom implementation`。

### 第 52.2 节：在内部类中访问默认方法

```java
public class OuterClass { 

    private int counter;

    public class InnerClass {

        default void printString() {

            System.out.println("I can access " + counter);

        } 

    }

}
```

但在名称冲突的情况下，你可以使用外部类引用。

```java
public class OuterClass { 

    private int counter;

    public class InnerClass { 

        private int counter;

        public void method() {

            System.out.println("My counter: " + counter);

            System.out.println("Outer counter: " + OuterClass.this.counter);
```



### 第 52.3 节：为什么要使用默认方法

默认方法的主要原因是它们允许接口演进，而不需要破坏现有的类。例如，你可以在接口中添加新方法，而不需要让所有实现类都去实现它。

```java
public interface Service {

    void execute();

    default void log() {

        System.out.println("Logging execution...");

    }

}
```

```java
public class MyService implements Service {

    @Override

    public void execute() {

        System.out.println("Executing...");

    }

}
```

### 第 52.4 节：在默认方法中访问其他接口方法

你可以在默认方法内部访问其他方法。

```java
public interface Summable { 

    int getA();

    int getB();

    default int calculateSum() { return getA() + getB(); }

}
```

```java
public class Sum implements Summable { 

    @Override

    public int getA() { return 1; }

    @Override

    public int getB() { return 2; }

}
```

执行`new Sum().calculateSum()`将输出 3。

### 第 52.5 节：默认方法的多继承冲突

考虑以下示例：

```java
public interface A {

    default void foo() { System.out.println("A.foo"); }

}
```

```java
public interface B {

    default void foo() { System.out.println("B.foo"); }

}
```

这里有两个接口声明了具有相同签名的默认方法`foo`。如果你尝试在新接口中扩展这两个接口，你必须做出选择，因为 Java 强制你显式地解决此冲突。

首先，你可以声明一个相同签名的抽象方法`foo`，这将覆盖 A 和 B 的行为。

```java
public interface ABExtendsAbstract extends A, B { 

    @Override

    void foo();

}
```

当你在类中实现`ABExtendsAbstract`时，你必须提供`foo`的实现：

```java
public class ABExtendsAbstractImpl implements ABExtendsAbstract {

    @Override

    public void foo() { System.out.println("ABImpl.foo"); }

}
```

其次，你可以提供一个完全全新的默认实现。

```java
public interface ABExtendsDefault extends A, B {

    @Override

    default void foo() {

        System.out.println("ABDefault.foo");

    }

}
```

也可以通过访问实现类中重写的默认方法来复用 A 和 B 的`foo`方法。

```java
public interface ABExtends extends A, B {

    @Override

    default void foo() { System.out.println("ABExtends.foo"); }

}
```

## 第 52-6 节：抽象类和接口方法的优先级

类中的实现（包括抽象声明）优先级高于所有接口的默认方法。抽象类方法的优先级高于接口默认方法。

```java
public interface Swim {

    default void backStroke() {

        System.out.println("Swim.backStroke");

    }

}
```

```java
public class AbstractSwimmer implements Swim {

    public void backStroke() {

        System.out.println("AbstractSwimmer.backStroke");

    }

}
```

```java
public class FooSwimmer extends AbstractSwimmer { }
```

以下语句`new FooSwimmer().backStroke();`将产生`AbstractSwimmer.backStroke`，优先级高于接口默认方法。

```java
public interface Swim {

    default void backStroke() {

        System.out.println("Swim.backStroke");

    }

}
```

```java
public abstract class AbstractSwimmer implements Swim { 

    public class FooSwimmer extends AbstractSwimmer { 

        public void backStroke() { 

            System.out.println("FooSwimmer.backStroke"); 

        } 

    }

}
```

以下语句`FooSwimmer().backStroke();`将产生`FooSwimmer.backStroke`。

## 第 53 章：包 (Packages)

Java 中的`package`用于对类和接口进行分组。这有助于开发者在存在大量类时避免冲突。如果我们使用包，我们可以在不同的包中创建同名的类/接口。通过使用包，我们可以在另一个类中导入这些代码。Java 中有很多内置的包，如：
1. `java.util`
2. `java.lang`
3. `java.io`

我们可以定义自己的包。

## 第 53.1 节：使用包创建同名的类

第一个`Test.class`：

```java
package foo.bar

public class Test {

}
```

另一个包中的`Test.class`：

```java
package foo.bar.baz

public class Test {

}
```

上述情况没有问题，因为这两个类存在于不同的包中。

## 第 53.2 节：使用包保护作用域 (Package Protected Scope)

在 Java 中，如果你不提供访问修饰符，变量的默认级别是包保护（package-protected）。这意味着类可以访问同一包内其他类的变量，就像这些变量是公开可用一样。

```java
package foo.bar

public class ExampleClass {

    double exampleNumber;

    String exampleString;

    public ExampleClass() {

        exampleNumber = 3;

        exampleString = "Test String";

    }

    // getters and setters

}
```

```java
package foo.bar

public class AnotherClass {

    ExampleClass clazz = new ExampleClass();

    System.out.println("Example Number: " + clazz.exampleNumber);

    // 打印 Example Number: 3

    System.out.println("Example String: " + clazz.exampleString);

    // 打印 Example String: Test String

}
```

这种方法对于另一个包中的类将无效：

```java
package baz.foo

public class ThisShouldNotWork {

    ExampleClass clazz = new ExampleClass();

    System.out.println("Example Number: " + clazz.exampleNumber); // 抛异常

    System.out.println("Example String: " + clazz.exampleString); // 抛异常

}
```

## 第 54 章：继承 (Inheritance)

继承是面向对象的一个基本特性，一个类通过`extends`关键字获取并扩展另一个类的属性。对于接口和`implements`关键字，请参见接口章节。

## 第 54.1 节：继承

在类之间使用`extends`关键字时，类的所有属性（也称为父类或基类）都存在于子类（也称为子类或派生类）中。

可以向子类添加额外内容。这样做允许在不更改基类或该基类的其他子类的情况下，为子类添加额外的功能：

```java
public class Sub2 extends BaseClass {

    public void anotherMethod() {

        System.out.println("Doing subclass2 stuff");

    }

}
```

```java
SubClass2 s2 = new SubClass2();
s2.baseMethod(); // 仍然有效，打印 "Doing base class stuff"
s2.anotherMethod(); // 有效，打印 "Doing subclass2 stuff"
```

字段也是被继承的：

```java
public class BaseClassWithField {

    public int x;

}
```

```java
public class SubClassWithField extends BaseClassWithField {

    public SubClassWithField(int x) { this.x = x; // 可以访问字段 }

}
```

私有字段和方法仍然存在于子类中，但不可访问：

```java
public class BaseClassWithPrivateField {

    private int x = 5;

    public int getX() { return x; }

}
```

```java
public class SubClassInheritsPrivateField extends BaseClassWithPrivateField {

    public void printX() {

        System.out.println(x); // 非法，无法访问私有字段 x

        System.out.println(getX()); // 合法，打印 5

    }

}
```

```java
SubClassInheritsPrivateField s = new SubClassInheritsPrivateField(); int x = s.getX(); // x 的值为 5。
```

在 Java 中，每个类最多继承一个类。为了避免复杂性，Java 不支持类的多继承。

```java
public class A {}

public class B {}

// public class C extends A, B {} // 错误
```

## 第 54.2 节：抽象类

抽象类是被标记为`abstract`的类，当它至少有一个抽象方法时。抽象类不能被实例化。它可以被子类化以提供公共代码。

```java
public abstract class Component {

    private int x, y;

    public setPosition(int x, int y) {

        this.x = x;

        this.y = y;

    }

    public abstract void render();

}
```

尝试实例化此类将导致编译错误：

```java
//error: Component is abstract; cannot be instantiated
Component c = new Component();
```

然而，扩展`Component`的类提供了实现：

```java
public class Button extends Component {

    @Override

    public void render() { // 渲染按钮 }

}
```

```java
public class TextBox extends Component {

    @Override

    public void render() { // 渲染文本框 }

}
```

继承类的实例也可以被强制转换为父类（普通继承），并在调用抽象方法时产生多态效应。

```java
Component myButton = new Button();

Component myTextBox = new TextBox();

myButton.render(); // 渲染按钮

myTextBox.render(); // 渲染文本框
```

## 抽象类对比接口

抽象类和接口提供了一种定义方法签名的方法，要求扩展/实现类提供实现。

抽象类和接口之间有两个主要区别：类只能继承一个类，但可以实现多个接口。抽象类可以包含实例（非静态）字段，但接口只能包含静态字段。

**Java SE 8 以前**

接口中声明的方法不能包含实现，当需要提供调用抽象方法的额外方法时，会使用抽象类。

**Java 8 及以后**

Java 8 允许接口包含默认方法，通常使用接口的其他方法来实现，这使得接口和抽象类在这方面一样强大。

## 抽象类的匿名子类

为了方便，Java 允许对抽象类的匿名实例进行实例化，在创建新对象时提供抽象方法的实现。使用上面的示例，可以像所示：

```java
Component myAnonymousComponent = new Component() {

    @Override

    public void render() {

        // 渲染一个快速的一次性组件

    }

};
```

## 第 54.3 节：使用 'final' 限制继承和重写

### 最终类 (Final classes)

在类声明中使用，`final`修饰符防止声明扩展该类的类。最终类是继承层次结构中的"叶子"类。

```java
// 声明了一个 final 类

final class MyFinalClass {

    /* 代码 */

}

// 编译错误：无法继承 final MyFinalClass

class MySubClass extends MyFinalClass {

    /* 更多代码 */

}
```

### final 类的用途

final 类可以与私有构造函数结合使用，以控制或防止类的实例化。这可以用于创建所谓的"工具类"，该类仅定义静态成员；即常量和静态方法。

```java
public final class UtilityClass {

    // 使用私有构造函数替换默认的公有构造函数

    UtilityClass() {}

    // 静态成员仍然可以像往常一样使用

    public static int doSomethingCool() { return 123; }

}
```

不可变类也应该被声明为 final。（不可变类是指实例在创建后无法更改的类；参见"不可变对象"主题。）通过这种方式，你无法为不可变类创建一个可变的子类。这将违反"里氏替换原则"，该原则要求子类型必须遵守其父类型的"行为契约"。

从实践角度来看，将不可变类声明为 final 可以更容易推断程序的行为。它还解决了在安全沙箱中执行不可信代码场景下的安全考虑问题。（例如，由于`String`被声明为 final，受信任的类不需要担心可能被诱导接受可变的子类，而不可信的调用者随后可以悄悄更改它。）

final 类的一个缺点是它们无法与某些模拟框架（如 Mockito）配合。更新：Mockito 2 版本现在支持对 final 类进行 mock 操作。

### final 方法

final 修饰符也可以应用于方法，以防止它们在子类中被重写：

```java
public class MyClassWithFinalMethod {

    public final void someMethod() {}

}
```

```java
public class MySubClass extends MyClassWithFinalMethod {

    @Override

    public void someMethod() { // 编译错误（被重写的方法是 final）

    }

}
```



当你希望限制子类对类中某些内容的修改，但不完全禁止子类时，通常使用`final`方法。

`final`修饰符也可以应用于变量，但变量的`final`含义与继承无关。

## 第 54.4 节：里氏夫替换原则

可替换性是 Barbara Liskov 在 1987 年的一次会议演讲中提出的面向对象编程原则，指出：如果类`B`是类`A`的子类，那么在任何预期`A`的地方，都可以使用`B`代替：

```java
class A {...}

class B extends A {...}

public void method(A obj) {

    A a = new B(); // 赋值 OK

    method(new B()); // 作为参数传递 OK

}
```

这也适用于类型为接口的情况，此时对象之间不需要层级关系：

```java
interface Foo { void bar(); }
```

```java
class A implements Foo { void bar() {...}}
```

```java
class B implements Foo { void bar() {...}}
```

```java
List<Foo> foos = new ArrayList<>(); 
foos.add(new A()); // OK
foos.add(new B()); // OK
```

现在列表包含了并非来自同一类层次结构的对象。

## 第 54.5 节：抽象类和接口的使用：“是一个”关系 vs “拥有（具有）”能力

何时使用抽象类：在多个相关对象之间实现相同或不同的行为
何时使用接口：由多个无关对象实现契约
抽象类创建“是一个”（`is a`）关系，而接口提供“拥有”（`has a`）能力。

在下面的代码中可以看到：

```java
public class InterfaceAndAbstractClassDemo{

    public static void main(String args[]){

        Dog dog = new Dog("Jack",16);

        Cat cat = new Cat("Joe",20);

        System.out.println("Dog":+dog);

        System.out.println("Cat":+cat);

    }

}
```

```java
dog.remember();

dog.protectOwner();

Learn dl = dog;

dl.learn();
```

```java
cat.remember();

cat.protectOwner();

Climb c = cat;

c.climb();

Man man = new Man("Ravindra",40);

System.out.println(man);
```

```java
Climb cm = man;

cm.climb();
```

```java
abstract class Animal {

    String name;

    int lifeExpectancy;

    public Animal(String name, int lifeExpectancy) {

        this.name = name;

        this.lifeExpectancy = lifeExpectancy;

    }

    public abstract void remember();

    public abstract void protectOwner();

    public String toString() {

        return name + ":Age:" + lifeExpectancy;

    }

}

class Dog extends Animal implements Learn {

    public Dog(String name, int lifeExpectancy) {

        super(name, lifeExpectancy);

    }

    public void remember() {

        System.out.println("Dog remember for 16");

    }

    public void protectOwner() {

        System.out.println("Dog protect owner");

    }

}

class Cat extends Animal implements Climb {

    public Cat(String name, int lifeExpectancy) {

        super(name, lifeExpectancy);

    }

    public void remember() {

        System.out.println("Cat remember for 20");

    }

    public void protectOwner() {

        System.out.println("Cat protect owner");

    }

}

interface Learn {

    void learn();

}

interface Climb {

    void climb();

}

interface Apply {

    void apply();

}

class Man implements Learn, Apply, Climb {

    public Man(String name, int lifeExpectancy) {

        super(name, lifeExpectancy);

    }

    public void learn() {

        System.out.println("Man learn");

    }

    public void apply() {

        System.out.println("Man apply");

    }

    public void climb() {

        System.out.println("Man climb");

    }

}
```

```java
public class BaseClass {

    public static int num = 5;

    public static void sayHello() { System.out.println("Hello"); }

    public static void main(String[] args) {

        BaseClass.sayHello();

        System.out.println("BaseClass's num: " + BaseClass.num);

        SubClass.sayHello();

        // 这与上述语句的输出不同，因为它运行的是 //一个不同的方法

        SubClass.sayHello(true);

    }

    static void sayHello() {

        System.out.println("StaticOverride's num: " + StaticOverride.num);

    }

}

public class SubClass extends BaseClass {

    // 继承了 sayHello 函数，但没有重写它

    public static void sayHello(boolean test) {

        System.out.println("Hey");

    }

    public static class StaticOverride extends BaseClass {

        // 隐藏了 BaseClass 中的 num 字段

        // 你甚至可以更改类型，这不会影响签名 

        public static String num = "test";

        // 不能使用 @Override 注解，因为它是静态的 //这覆盖了

        // BaseClass 中的 sayHello 方法 

        public static void sayHello() {

            System.out.println("Static says Hi");

        }

    }

}
```

运行这些类中的任何一个产生输出：
```
Hello
BaseClass's num: 5
Hey
Static says Hi
StaticOverride's num: test
```

注意，与普通继承不同，在静态继承中，方法不会被隐藏。你始终可以通过`BaseClass.sayHello()`调用基`sayHello`方法。但如果在子类中没有找到相同签名的方法，类确实会继承静态方法。如果两个方法的签名不同，即使方法名称相同，也可以从子类中运行这两个方法。

静态字段也以类似的方式相互隐藏。

## 第 54.7 节：面向接口编程

面向接口编程的思想是让代码主要基于接口，并且仅在实例化时使用具体类。在这种语境下，处理例如 Java 集合的良好代码看起来像这样（请注意该方法本身完全没用，仅作说明）：

```java
public <T> Set<T> setTo(Collection<T> collection) {

    Sets.newHashSet(collection);

}
```

而糟糕的代码可能像这样：

```java
public <T> HashSet<T> setTo(ArrayList<T> collection) {

    Sets.newHashSet(collection);

}
```

前者不仅可以应用于更广泛的参数选择，其结果也将与其他开发者提供的代码更兼容，因为这些代码通常遵循面向接口编程的概念。然而，使用后者的最重要原因在于：

大多数情况下，使用结果的上下文不需要也不应该具体实现所提供的许多细节；遵循接口可以强制执行更整洁的代码，并减少“黑客”手段，例如为服务某些特定场景的类添加另一个公共方法；代码更具可测试性，因为接口易于进行 mock（模拟）；最后，即使只预期一种实现（至少为了可测试性），这个概念也是有帮助的。

那么，在编写新代码时如果考虑到某个特定的实现，可以容易地应用面向接口编程的概念吗？我们常用的方案之一是以下模式的组合：

- 面向接口编程
- 工厂构建器

以下基于这些原则的示例是一个为多种协议编写的 RPC 实现的简化和截断版本：

```java
public interface RemoteInvoker {

    <RQ, RS> CompletableFuture<RS> invoke(RQ request, Class<RS> responseClass);

}
```

上述接口不应该通过工厂直接实例化，相反，我们派生出更具体的接口，一个用于 HTTP 调用，一个用于 AMQP，每个接口随后都有一个工厂和一个构建器来构造实例，而这些实例反过来上述接口的实例：

```java
public interface AmqpInvoker extends RemoteInvoker {

    static AmqpInvokerBuilder with(String instanceId, ConnectionFactory factory) {

        return new AmqpInvokerBuilder(instanceId, factory);

    }

}
```

现在构造用于 AMQP 的`RemoteInvoker`实例可以像这样简单（或者取决于构建器可能更复杂）：

```java
RemoteInvoker invoker = AmqpInvoker.with(instanceId, factory)

    .requestRouter(router)

    .build();
```

调用请求也同样简单：
```java
Response res = invoker.invoke(new Request(data), Response.class).get();
```

由于 Java 8 允许将静态方法直接放入接口中，中间工厂在上述代码中已变为隐式，被`AmqpInvoker.with()`替换。在 Java 8 之前的版本中，可以通过内部`Factory`类实现相同：

```java
public interface AmqpInvoker extends RemoteInvoker {

    class Factory {

        public static AmqpInvokerBuilder with(String instanceId, ConnectionFactory factory) {

            return new AmqpInvokerBuilder(instanceId, factory);

        }

    }

}
```

相应的实例化将变为：

```java
RemoteInvoker invoker = AmqpInvoker.Factory.with(instanceId, factory).requestRouter(router).build();
```

上述使用的构建器可能如下所示（尽管这是一个简化，实际的构建器允许定义最多 15 个偏离默认值的参数）。注意该构造函数不是公共的，因此它专门供上述`AmqpInvoker`接口使用：

```java
public class AmqpInvokerBuilder {

    AmqpInvokerBuilder(String instanceId, ConnectionFactory factory) {

        this.instanceId = instanceId;

        this.factory = factory;

    }

}
```

## 第 54.8 节：继承中的重写

注意，与普通继承不同，在静态继承中，方法不会被隐藏。你始终可以通过`BaseClass.sayHello()`调用基`sayHello`方法。但如果在子类中没有找到相同签名的方法，类确实继承静态方法。如果两个方法的签名不同，即使方法名称相同，也可以从子类中运行这两个方法。

静态字段也以类似的方式相互隐藏。

## 第 54.9 节：变量遮蔽

变量被遮蔽（shadowed），而方法被重写（overridden）。使用哪个变量取决于声明它的类。使用哪个方法取决于对象的实际类。

```java
class Car {

  public int gearRatio = 8;

  public String accelerate() { return "Accelerate : Car"; }

}

class SportsCar extends Car {

  public int gearRatio = 9;

  public String accelerate() {

    return "Accelerate : SportsCar";

  }

}
```

```java
public static void main(String[] args) {

  Car car = new SportsCar();

  System.out.println(car.gearRatio + " " + car.accelerate()); // 将输出 8 Accelerate : SportsCar

}
```

## 第 54.10 节：对象引用的收窄与扩展

将基类实例转换为子类（`b = (B) a;`）被称为收窄（因为你正试图将基对象缩小到更具体的类对象），并且需要显式的类型转换。

将子类实例转换为基类（`A = b;`）被称为扩展，并且不需要类型转换。

为了说明这一点，考虑以下类声明和测试代码：

```java
class Vehicle {

}

class Car extends Vehicle {

}

class Truck extends Vehicle {

}

class Motorcycle extends Vehicle {

}

class Test {

  public static void main(String[] args) {

    Vehicle vehicle = new Car(); Car car = new Car();

    vehicle = car; // 有效，不需要转换

    Car c = vehicle // 无效 Car c = (Car) vehicle; // 有效

  }

}
```



卡车（`Truck`）、摩托车（`MotorCycle`）或任何当前或未来的 `Vehicle` 子类。（实际上，`Vehicle` 本身的一个实例也可以，因为我们没有将其声明为抽象类。）不允许进行该赋值，因为这可能导致引用一个 `Truck` 实例。

为了防止这种情况发生，我们需要添加一个显式的类型转换：

```
Car c = (Car) vehicle;
```

类型转换告诉编译器，我们期望 `vehicle` 的值是一个 `Car` 类型或 `Car` 的子类。如果有必要，编译器将插入代码来执行运行时类型检查。如果检查失败，则在执行代码时将抛出 `ClassException`。

请注意，并不是所有的类型转换都是有效的。例如：

```
String s = (String) vehicle; // 无效
```

Java 编译器知道，与 `Vehicle` 类型兼容的实例永远不可能与 `String` 类型兼容。在这种情况下，在子类中实现静态方法永远无法隐藏类 `StaticMethodTest`，且 JLS（Java 语言规范）规定这会导致编译错误。

## 第 54.11 节：继承与静态方法

在 Java 中，父类和子类都可以拥有相同名的静态方法。但在这种情况下，子类中静态方法的实现是隐藏了父类的实现，而不是重写。例如：

```java
// 静态方法与继承

public static void main(String[] args) {

    Parent p = new Child();

    p.staticMethod(); // 打印 Inside Parent

    ((Child)p.staticMethod()); // 打印 Inside Child

}
```

```java
static class Parent {

    public static void staticMethod() {

        System.out.println("Inside Parent");

    }

}
```

```java
static class Child extends Parent { 

    public static void staticMethod() {

        System.out.println("Inside Child"); 

    }

}
```

静态方法绑定到类而不是实例，这种方法绑定发生在编译时。由于第一次调用 `staticMethod()` 时使用了父类引用 `p`，调用了 `Parent` 版本的 `staticMethod()`。在第二情况下，我们将 `p` 强制转换为 `Child` 类，执行了 `Child` 的 `staticMethod()`。

## 第 55 章：引用类型
### 第 55.1 节：不同的引用类型

`java.lang.ref` 包提供了引用对象类，它们支持与垃圾回收器进行有限程度的交互。Java 有四种主要的引用类型。它们是：

- 强引用（Strong Reference）
- 弱引用（Weak Reference）
- 软引用（Soft Reference）
- 虚引用（Phantom Reference）

### 1. 强引用

这是创建对象的通常方式。

```
MyObject myObject = new MyObject();
```

变量持有指向创建对象的强引用。只要这个变量存活并持有该值，`MyObject` 实例就不会被垃圾回收器收集。

### 2. 弱引用

当你不想长时间保留一个对象，并且需要尽快清理/释放为对象分配的内存时，可以使用这种方法。

```java
WeakReference myObjectRef = new WeakReference(MyObject);
```

简单来说，弱引用是一种强度不足以强制对象留存在内存中的引用。弱引用允许你利用垃圾回收器判断可达性的能力，因此你不需要自己去做。

当你需要你创建的对象时，只需使用 `.get()` 方法：

```
myObjectRef.get();
```

以下代码将说明这一点：

```java
WeakReference myObjectRef = new WeakReference(MyObject);

System.out.println(myObjectRef.get()); // 这将打印对象地址

System.gc();

System.out.println(myObjectRef.get()); // 如果 GC 清理了对象，将打印 'null'
```

### 3. 软引用

软引用比弱引用稍强。你可以按照以下方式创建软引用对象：

```
SoftReference myObjectRef = new SoftReference(MyObject);
```

它们比弱引用更能强地持有内存。软引用允许垃圾回收器在内存不足时才回收它们。如果内存足够，软引用就会被保留，直到内存耗尽。使用软引用非常方便用于缓存。当内存不足时，垃圾回收器会清理软引用。

```java
SoftReference myObjectRef = new SoftReference(MyObject);

System.out.println(myObjectRef.get()); // 这将打印对象地址

System.gc();

System.out.println(myObjectRef.get()); // 如果 GC 清理了对象，则可能打印 null
```

### 4. 虚引用

这是最弱的类型。即使内存足够时，`get()` 方法始终返回 `null`。

虚引用的用法是用于清理。你可以按照以下方式创建虚引用：

```
PhantomReference myObjectRef = ...
```

## 第 56 章：控制台 I/O
### 第 56.1 节：从控制台读取输入

使用 `BufferedReader`：

```java
BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

try {

    String name = reader.readLine();

    System.out.println("Hello, " + name);

} catch (IOException e) { 

}
```

这需要以下导入：
- `java.io.BufferedReader`
- `java.io.IOException`
- `java.io.InputStreamReader`

使用 `Scanner`：

```java
Scanner scanner = new Scanner(System.in);

try {

    String name = scanner.nextLine();

    System.out.println("Hello, " + name);

} catch (Exception e) { }
```

这需要以下导入：
- `java.util.Scanner`

要读取多行，多次调用 `scanner.nextLine()`：

```java
Scanner scanner = new Scanner(System.in);

String firstName = scanner.nextLine();

String lastName = scanner.nextLine();
```

使用 `System.console`：

读取密码（终端不回显）

```java
char[] password = System.console().readPassword();
```

注意：只有当程序从真实的命令行运行且没有重定向标准输入输出时，才有效。在某些 IDE 中运行时无效。对于在流重定向的代码，请查看其他示例。

### 第 56.2 节：在控制台上对齐字符串

`PrintWriter.format` 方法（通过 `System.out.format` 调用）可用于在控制台上对齐字符串。该方法接收一个带有格式信息的字符串和一系列需要格式化的对象：

```java
String rowsStrings[] = new String[]{"1", "1234", "1234567", "123456789"};

String column1Format = "%-3s"; // 最小3字符，左对齐

column2Format = "%-5.8s"; // 最小5字符且最大8字符，左对齐

String column3Format = "%6.6s"; // 固定大小6字符，右对齐

String formatInfo = column1Format + " " + column2Format + " " + column3Format;

for (int i = 0; i < rowsStrings.length; i++) {

    System.out.format(formatInfo, rowsStrings[i], rowsStrings[i], rowsStrings[i]);

    System.out.println();

}
```

输出：

```
1 1        1
1234 1234     1234
1234567 123456 123456
123456789 123456789 123456
```

使用固定大小的格式字符串允许以具有固定列宽表格的形式打印字符串。

```java
String rowsStrings[] = new String[] {"1", "1234", "1234567", "123456789"};
```

```java
String column1Format = "%-3.3s"; // 固定 3 个字符，左对齐

String column2Format = "%-8.8s"; // 固定 8 个字符，左对齐

String column3Format = "%-6.6s"; // 固定 6 个字符，右对齐

String formatInfo = column1Format + " " + column2Format + " " + column3Format;

for (int i = 0; i < rowsStrings.length; i++) {

    System.out.format(formatInfo, rowsStrings[i], rowsStrings[i]);

    System.out.println();

}
```

输出：

```
1 1 1
123 1234 1234
123 1234567 123456
123 12345678 123456
```

格式字符串示例：

- `%s` : 无格式的字符串
- `%5s`: 格式化字符串，最小为 5 个字符；如果字符串短于 5，将填充到 5 个字符并右对齐
- `%-5s`: 格式化字符串，最小为 5 个字符；如果字符串短于 5，将填充到 5 个字符并左对齐
- `%5.10s`: 格式化字符串，最小为 5 个字符，最大为 10 个字符；如果字符串短于 5，将填充到 5 个字符并右对齐；如果长于 10，将截断为 10 个字符并右对齐
- `%5.5s`: 格式化字符串固定为 5 个字符（最小和最大相等）；如果字符串短于 5，将填充到 5 个字符并左对齐；如果长于 5，将截断为 5 个字符并左对齐

### 第 56.3 节：实现基本的命令行行为

对于基本的原型或基本的命令行行为，以下循环非常有用。

```java
public class ExampleCli {

    private static final String CLI_LINE = "example-cli"; // 控制台字符串

    private static final String CMD_QUIT = "quit";

    private static final String CMD_HELLO = "hello";

    private static final String CMD_ANSWER = "answer";

    // 用于退出程序的字符串 // 用于打印 "Hello World!" 的字符串

    // 用于在屏幕上打印 42 的字符串

    public static void main(String[] args) {

        ExampleCli claimCli = new ExampleCli(); // 创建此类的对象
```

```java
try {

    claimCli.start();//调用 start 函数执行控制台工作

} catch (IOException e) {

    e.printStackTrace();//如果无法获取用户输入或类似内容，则打印异常日志

}
```

```java
private void start() throws IOException { 

    String cmd = "";

    BufferedReader reader = new BufferedReader(new

    InputStreamReader(System.in)); 

    while (!cmd.equals(CMD_QUIT)) {

        System.out.print(CLI_LINE);

        // 如果用户输入是 "quit" 则终止控制台//打印控制台字符串

        cmd = reader.readLine(); // "hello", "answer" 或 "quit"

        //从用户获取输入。用户输入应以

        String[] cmdArr = cmd.split(" ");
```

```java
        if (cmdArr[0].equals(CMD_HELLO)) {//当用户输入以 "hello" 开头时执行

            hello(cmdArr);

        }

        else if (cmdArr[0].equals(CMD_ANSWER)) {//当用户输入以 "answer" 开头时执行

        answer(cmdArr);
```

```java
    }

}

// 如果用户输入以 "hello"开头，在屏幕上打印 "Hello World!" 

private void hello(String[] cmdArr) {

    System.out.println("Hello World!");

}

// 如果用户输入以 "answer"开头，在屏幕上打印 "42" 

private void answer(String[] cmdArr) {

    System.out.println("42");

}

}
```

## 第 57 节：流 (Streams)

Stream 代表元素的序列，并支持不同类型的操作对这些元素执行计算。在 Java 8 中，Collection 接口有两个方法可以生成 Stream：`stream()` 和 `parallelStream()`。Stream 操作分为中间操作或终端操作。中间操作返回一个 Stream，因此在 Stream 关闭之前可以链用多个中间操作。终端操作要么返回 `void`，要么返回一个非流的结果。

### 第 57.1 节：使用流

Stream 是元素的序列，可以在其上执行顺序和并行聚合操作。任何 Stream 都可能有无限量的数据流过它。因此，从 Stream 接收到的数据在到达时被逐个处理，而不是对数据进行整体批处理。当与 Lambda 表达式结合时，它们提供了一种简洁的方法，使用函数式方法对数据序列执行操作。

示例：（请在 Ideone 上查看其运行情况）

```
Stream<String> fruitStream = Stream.of("apple", "banana", "pear", "kiwi", "orange");

fruitStream.filter(s -> s.contains("a")).map(String::toUpperCase).sorted().forEach(System.out::println);
```

输出：

```
APPLE
BANANA ORANGE PEAR
```

上述代码执行的操作可以总结如下：

1. 创建一个 `Stream<String>`。
2. `filter` 操作保留包含 "a" 的元素。
3. `map` 操作将元素转换为大写。
4. `sorted` 操作根据自然顺序对元素进行排序。
5. `forEach` 操作打印每个元素。

提供对其元素的直接访问和操作能力；它更侧重于将对象组作为一个整体实体，并对该整体进行操作。Stream（流）和 Collection（集合）是针对这些不同目的的独立高级抽象。

### 第 57.2 节：消费 Stream

只有当存在终端操作（如 `count()`、`collect()` 或 `forEach()`）时，Stream 才会被遍历。否则，不会对 Stream 执行任何操作。

在接下来的示例中，没有为 Stream 添加终端操作，因此 `filter()` 操作将不会被调用，也不会产生任何输出，因为 `peek()` 并不是终端操作。

```java
IntStream.range(1,10).filter(a -> a % 2 == 0).peek(System.out::println);
```

在 Ideone 上运行

这是一个带有有效终端操作的 Stream 序列，因此产生了输出。你也可以使用 `forEach` 代替 `peek`：

```java
IntStream.range(1,10).filter(a -> a % 2 == 0).forEach(System.out::println);
```

在 Ideone 上运行

输出：

```
2
4
6
8
```

执行终端操作后，Stream 将被消费且无法再次使用。

虽然给定的 Stream 对象不能重用，但很容易创建一个委托于 Stream 管道的可重用 `Iterable`。这对于返回活动数据集的修改后视图非常有用，而无需将结果收集到临时结构中。



`List<String> list = Arrays.asList("FOO", "BAR");`

`Iterable<String> iterable = () -> list.stream().map(String::toLowerCase).iterator();`

`for (String str : iterable) { System.out.println(str); }`

```
输出：
foo bar foo bar
```

这种之所以之所以有效，是因为 `Iterable` 声明了一个单抽象方法 `Iterator<T> iterator()`。这使其实际上成为一个函数式接口，通过 Lambda 表达式实现，并在每次调用时创建一个新的流。

通常情况下，`Stream` 的工作方式如图所示：

![](img/01cc8d6667542262308c820b3f5bd37b_482_0.png)

注意：即使没有终端操作，始终会执行参数检查：

```java
try {
    IntStream.range(1, 10).filter(null);
} catch (NullPointerException e) {
    System.out.println("We got a NullPointerException as null was passed as an argument to filter(");
}
```

在 Ideone 上运行

输出：

`We got a NullPointerException as null was passed as an argument to filter()`

## 第 57.3 节：创建频率映射

`groupingBy(classifier, downstream)` 收集器允许通过对组中的元素进行分类并对同组分类元素执行下游操作，将 `Stream` 元素收集到 `Map` 中。

该原理的一个经典示例是使用 `Map` 来统计 `Stream` 中元素出现的次数。在这个示例中，分类器仅仅是恒等函数，它按原样返回元素。下游操作使用 `counting()` 计算相等元素的数量。

```java
Stream.of("apple", "orange", "banana", "apple").collect(Collectors.groupingBy(Function.identity(), Collectors.counting())).entrySet().forEach(System.out::println);
```

下游操作本身是一个收集器（`Collectors.counting()`），它对 `String` 类型的元素进行操作，并产生 `Long` 类型的结果。`collect` 方法的结果是 `Map<String, Long>`。这将产生以下输出：

`banana=1 orange=1 apple=2`

## 第 57.4 节：无限流

可以生成一个不结束的 `Stream`。在无限流上调用终端方法会导致 `Stream` 进入无限循环。`Stream` 的 `limit` 方法可用于限制 Java 处理的 `Stream` 项数。

此示例生成了一个从数字 1 开始的所有自然数的 `Stream`。`Stream` 的每一个后续项都比前一个项高。通过调用此 `Stream` 的 `limit` 方法，只考虑并打印 `Stream` 的前五项。

```java
// 生成无限流 - 1, 2, 3, 4, 5, 6, 7, ...
IntStream naturalNumbers = IntStream.iterate(1, x -> x + 1);

// 打印前 5 项
naturalNumbers.limit(5).forEach(System.out::println);
```

输出：

`1 2 3 4 5`

生成无限流另一种方法是使用 `Stream.generate` 方法。该方法接收一个 `Supplier` 类型的 Lambda 表达式。

```java
// 生成随机数的无限流
Stream<Double> infiniteRandomNumbers = Stream.generate(Math::random);

// 打印前 10 个随机数
infiniteRandomNumbers.limit(10).forEach(System.out::println);
```

## 第 57.5 节：将 Stream 元素收集到集合

### 使用 `toList()` 和 `toSet()` 收集

使用 `Stream.collect` 操作可以将 `Stream` 中的元素轻松收集到容器中：

```java
System.out.println(Arrays.asList("apple", "banana", "pear", "kiwi", "orange")
    .stream()
    .filter(s -> s.contains("a"))
    .collect(Collectors.toList()));

// 打印: [apple, banana, orange]
```

可以使用其他 `Collectors` 内置方法创建其他实例（如 `Set`）。例如，`Collectors.toSet()` 将 `Stream` 的元素收集到 `Set`。

### 对 List 或 Set 实现的显式控制

根据 `Collectors#toList()` 和 `Collectors#toSet()` 的文档，对于返回的 `List` 或 `Set` 没有关于类型、可变性、序列化或线程安全的保证。

为了实现显式控制，可以使用 `Collectors.toCollection(Supplier)`，其中 supplier 返回一个新的集合。

```java
// 方法引用语法
System.out.println(strings)
    .stream()
    .filter(s -> s.length() <= 3)
    .collect(Collectors.toCollection(ArrayList::new));

// Lambda 语法
System.out.println(strings)
    .stream()
    .filter(s -> s.length() <= 3)
    .collect(Collectors.toCollection(() -> new LinkedHashSet<>()));
```

### 使用 toMap 收集元素

将元素累积到 `Map`，其中 key 是 Student ID，Value 是 Student 名称。

```java
List<Student> students = new ArrayList<>();
students.add(new Student(1,"test1"));
students.add(new Student(2,"test2"));
students.add(new Student(3,"test3"));

Map<Integer, String> IdToName = students.stream()
    .collect(Collectors.toMap(Student::getId, Student::getName));

System.out.println(IdToName);
```

输出：

`{1=test1,2=test2,3=test3}`

`Collectors.toMap` 有实现 `Collector<T,?,Map<K,U>> toMap(Function<?super T, ? extends K> keyMapper, Function<?super T, ? extends U> valueMapper, BinaryOperator<U> mergeFunction)`。当向 `Map` 添加新成员时，`mergeFunction` 主要用于选择新值或保留旧值。

`mergeFunction` 看起来像：`(s1, s2) -> s1` 保留重复键的值，或者 `(s1, s2) -> s2` 为重复键放置新值。

### 将元素收集到集合的 Map

示例：从 `ArrayList` 到 `Map<String, List<>>` 通常需要创建一个列表的 `Map`。示例：从学生列表开始，我们需要为每个学生创建一个科目 `Map`。

```java
List<Student> list = new ArrayList<>();
list.add(new Student("David", "MATH", 35.0));
list.add(new Student("David", "SCIENCE", 12.9));
list.add(new Student("David", "GEOGRAPHY", 37.0));

Map<String, List<String>> map = new HashMap<>();
list.stream().forEach(s ->
    map.computeIfAbsent(s.getName(), x -> new ArrayList<>()).add(s.getSubject()));

System.out.println(map);
```

输出：

```
{ Robert=[LITERATURE],
Sascha=[ENGLISH, MATH, SCIENCE, LITERATURE], David=[MATH, SCIENCE, GEOGRAPHY] }
```

示例：从 `ArrayList` 到 `Map<String, Map<>>`

```java
List<Student> list = new ArrayList<>();
list.add(new Student("David", "MATH", 1, 35.0));
list.add(new Student("David", "SCIENCE", 2, 12.9));
list.add(new Student("David", "MATH", 3, 37.0));
list.add(new Student("David", "SCIENCE", 4, 37.0));

list.add(new Student("Sascha", SUBJECT_ENGLISH, 5, 85.0));
list.add(new Student("Sascha", SUBJECT_MATH, 1, 80.0));
list.add(new Student("Sascha", SUBJECT_ENGLISH, 6, 12.0));
list.add(new Student("Sascha", SUBJECT_MATH, 3, 50.0));

list.add(new Student("Robert", SUBJECT_ENGLISH, 5, 12.0));

Map<String, Map<SUBJECT, List<Double>>> map = new HashMap<>();

list.stream().forEach(student -> 
    map.computeIfAbsent(student.getName(), s -> new HashMap<>())
    .computeIfAbsent(student.getSubject(), s -> new ArrayList<>())
    .add(student.getMarks()));

System.out.println(map);
```

输出：

```
{ Robert={ENGLISH=[12.0]},
Sascha={MATH=[80.0, 50.0], ENGLISH=[85.0, 12.0]}, Davis={MATH=[35.0, 37.0], SCIENCE=[12.9, 37.0]} }
```

# 快速查表目标

- 收集到 `List`
- 收集到预分配大小的 `ArrayList`
- 收集到 `Set`
- 收集到迭代性能更好的 `Set`
- 收集到不区分大小写的 `Set<String>`
- 收集到 `EnumSet<AnEnum>`（枚举类性能优异）
- `Collectors.toList()`
- `Collectors.toCollection(() -> new ArrayList<>(size))`
- `Collectors.toSet()`
- `Collectors.toCollection(() -> new LinkedHashSet<>())`
- `Collectors.toCollection(() -> new TreeSet<>(String.CASE_INSENSITIVE_ORDER))`
- `Collectors.toCollection() -> EnumSet.noneOf(AnEnum.class)`
- 收集到具有唯一键的 `Map<K,V>`
- `Collectors.toMap(keyFunc,valFunc)`
- 将 `MyObject.getter()` 映射到唯一的 `MyObject`
- 将 `MyObject.getter()` 映射到多个 `MyObjects`
- `Collectors.toMap(MyObject::getter, Function.identity())`
- `Collectors.groupBy(MyObject::getter)`

# 第 57.6 节：使用 Streams 实现数学函数

`Streams`，特别是 `IntStreams`，是实现求和项（Σ）的一种优雅方式。`Stream` 的范围可以作为求和的边界。

例如，马达婆（Madhava）的圆周近似公式所示（源：wikipedia）：

![](img/01cc8d6667542262308c820b3f5bd37b_488_0.png)

这可以使用任意精度进行计算。例如，对于 101 项：

```java
double pi = Math.sqrt(12) *
    IntStream.range(0, 100).mapToDouble(k -> Math.pow(3, -1 * k) / (2 * k + 1)).sum();
```

注意：根据 `double` 的精度，选择 29 作为上界就足以获得与 `Math.Pi` 无异的结果。

# 第 57.7 节：使用 flatMap() 扁平化 Streams

一个包含同样可以转换为流的项的 `Stream` 可以扁平化为一个连续的 `Stream`：

`List` 元素的数组可以转换为单个 `List`。

```java
List<String> list1 = Arrays.asList("one", "two");
List<String> list2 = Arrays.asList("three","four","five");
List<String> list3 = Arrays.asList("six");
```

```java
List<String> finalList = Stream.of(list1, list2, list3).flatMap(Collection::stream).collect(Collectors.toList());

System.out.println(finalList);
```

`// [one, two, three, four, five, six]`

包含 `List` 项的 `Map` 扁平化为合并 `List`

```java
Map<String, List<Integer>> map = new LinkedHashMap<>(); 
map.put("a", Arrays.asList(1, 2, 3));
map.put("b", Arrays.asList(4, 5, 6));
```

```java
List<Integer> allValues = map.values() // Collection<List<Integer>
    .stream()
    .flatMap(List::stream)
    .collect(Collectors.toList());

System.out.println(allValues); // [1, 2, 3, 4, 5, 6]
```

`Map` `List` 可以扁平化为连续的 `Stream`

```java
List<Map<String, String>> list = new ArrayList<>();

Map<String, String> map1 = new HashMap<>();
map1.put("1", "one");
map1.put("2", "two");

Map<String, String> map2 = new HashMap<>();
map2.put("3", "three");
map2.put("4", "four");

list.add(map1);
list.add(map2);

Set<String> output = list.stream()
    .flatMap(m -> m.values().stream())
    .collect(Collectors.toSet());

// output: [one, two, three, four]
```

# 第 57.8 节：并行流 (Parallel Stream)

注意：在决定使用哪个 `Stream` 之前，请查看 `ParallelStream` 与 `Sequential` 行为的区别。

当你想要并发执行操作时，可以使用上述两种方法。

```java
List<String> data = Arrays.asList("One", "Two", "Three", "Four", "Five");

Stream<String> aParallelStream = data.stream().parallel();
Stream<String> bParallelStream = data.parallelStream();
```



要执行为并行流定义的操作，请调用终端操作：

```
aParallelStream.forEach(System.out::println);
```

顺序可能会改变，因为所有元素都是并行处理的（这可能会使其更快）。当顺序不重要时，使用`parallelStream()`。在涉及网络的情况下，并行流可能会降低应用程序的整体性能，因为并行流使用公共的`fork-join`池。相反，取决于可用核心数，并行流在许多情况下可以显著提高性能。

# 第 57.9 节：创建 Stream

可以使用两种方法中的一种从数组创建`Stream<E>`：

```java
Collection<String> stringList = new ArrayList<>();

Stream<String> stringStream = stringList.stream();

String[] values = {"aaa", "bbbb", "ddd", "cccc"};

Stream<String> stringStream = Arrays.stream(values);

stringStreamAlternative = Stream.of(values);
```

`Arrays.stream()`和`Stream.of()`的区别在于`Stream.of()`具有变长参数，它可以像这样使用：

```java
Stream<Integer> integerStream = Stream.of(1, 2, 3);
```

还有你可以使用的原始类型流：

```java
IntStream intStream = IntStream.of(1, 2, 3);

DoubleStream doubleStream = DoubleStream.of(1.0, 2.0, 3.0);
```

这些原始流也可以使用`Arrays.stream()`构建：

```java
IntStream intStream = Arrays.stream(values);
```

可以使用指定的范围从数组创建`Stream`：

```java
int[] values = new int[]{1, 3};

IntStream intStream = Arrays.stream(values, 1); // [2]
```

使用`boxed()`将原始流转换为包装类型流：

```java
IntStream intStream = intStream.boxed();

Set<Integer> output = intStream.collect(Collectors.toSet());
```

重用 stream 的中间操作

`Stream`在调用终端操作时会关闭。当需要重用时，我们可以创建一个`supplier`来构建设置了所有中间操作的新流。

```java
Supplier<Stream<String>> streamSupplier = () -> Stream.of("apple", "banana", "orange", "grape", "melon", "blueberry")

    .map(String::toUpperCase).sorted();

streamSupplier.get().filter(s -> s.startsWith("A")).forEach(System.out::println);

// APPLE

streamSupplier.get().filter(s -> s.startsWith("B")).forEach(System.out::println);

// BANANA, BLACKBERRY, BLUEBERRY
```

使用 streams 将数组转换为`List<Integer>`：

```java
int[] ints = {1,2,3};

List<Integer> list = IntStream.of(ints).boxed().collect(Collectors.toList());
```

# 第 57.10 节：数值流的统计信息

Java 8 提供了`IntSummaryStatistics`、`DoubleSummaryStatistics`和`LongSummaryStatistics`，它们提供了用于收集计数、最小值、和和平均值的状态对象。

```java
List<Integer> naturalNumbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

IntSummaryStatistics stats = naturalNumbers.stream()

    .mapToInt(x -> x)

    .summaryStatistics();

System.out.println(stats);
```

结果将是：`IntSummaryStatistics{count=10, sum=55, min=1, max=10, average=5.500000}`

# 第 57.11 节：迭代器转换为流

使用`Spliterators.spliterator()`或`Spliterators.spliteratorUnknownSize()`将迭代器转换为流：

```java
Iterator<String> iterator = Arrays.asList("A", "B", "C").iterator();

Spliterator<String> spliterator = Spliterators.spliteratorUnknownSize(iterator, 0);

Stream<String> stream = StreamSupport.stream(spliterator, false);
```

# 第 57.12 节：使用 IntStream 遍历索引

元素通常不允许访问当前项的索引值。要在遍历数组或`ArrayList`时访问索引，请使用`IntStream.range(start, endExclusive)`。

```java
String[] names = { "Jon", "Darin", "Bauke", "Hans", "Marc" };
```

```java
IntStream range(0, names.length)

    .mapToObj(i -> String.format("%%%d %s", i + 1, names[i]))

    .forEach(System.out::println);
```

`range(start, endExclusive)`方法返回另一个`IntStream`，而`mapToObj(mapper)`返回一个`String`的流（stream）。

```
#1 Jon
#2 Darin
#3 Bauke
#4 Hans
#5 Marc
```

这与使用带有计数器的普通循环非常相似，但具有流水线（pipelining）和并行化的优势：

```java
for (int i = 0; i < names.length; i++) {

    String newName = String.format("%%%d %s", i + 1, names[i]);

    System.out.println(newName);

}
```

## 第 57.13 节：合并流 (Concatenate Streams)

示例的变量声明：

```java
Collection<String> abc = Arrays.asList("a", "b", "c");

Collection<String> digits = Arrays.asList("1", "2", "3"); 

Collection<String> greeksAb = Arrays.asList("alpha", "beta", "gamma");
```

示例 1 - 合并两个流：

```
final Stream<String> concat1 = Stream.concat(abc.stream(), digits.stream());
concat1.forEach(System.out::print); // 输出: abc123
```

示例 2 - 合并多个流：

```
final Stream<String> concat2 = Stream.concat (Stream.concat(abc.stream(), digits.stream()), greekAb.stream());
```

```java
System.out.println(concat2.collect(Collectors.joining(", "))); // 输出: a, b, c, 1, 2, 3, alpha, beta, gamma
```

或者，为了简化嵌套的`concat()`语法，也可以`flatMap()`来合并流：

```java
final Stream<String> concat3 = Stream.of(abc.stream(), digits.stream(), greekAbc.stream())

    .flatMap(s -> s);

// `flatMap(Function.identity())` `java.util.function.Function`
```

```java
System.out.println(concat3.collect(Collectors.joining(", "))); // 输出: a, b, c, 1, 2, 3, alpha, beta, gamma
```

在通过重复合并构建流时要小心，因为访问深度合并的流元素可能会导致深层调用链，甚至导致`StackOverflowException`（栈溢出异常）。

## 第 57.14 节：流的规约 (Reduction with Streams)

规约（Reduction）是将二元运算符应用于流的每个元素以得到一个值的过程。

`IntStream`的`sum()`方法是规约的一个示例；它对流的每个项应用加法运算，最终产生一个最终值：

![](img/01cc8d6667542262308c820b3f5bd37b_495_0.png)

等同于 `(((1+2)+3)+4)`。`Stream`的`reduce`方法允许创建自定义规约。可以使用`reduce`方法来实现`sum()`方法：

```java
IntStream istr;

// 初始化 istr

OptionalInt istr = istr.reduce((a,b)->a+b);
```

返回`Optional`版本是为了妥善处理空流。

规约的另一个示例是将`Stream<LinkedList<T>>`合并为单个`LinkedList<T>`：

```java
Stream<LinkedList<T>> listStream;

// 创建一个 Stream<LinkedList<T>>

Optional<LinkedList<T>> bigList = listStream.reduce((LinkedList<T> list1, LinkedList<T> list2)->{

    LinkedList<T> retList = new LinkedList<T>();

    retList.addAll(list1);

    retList.addAll(list2);

    return retList;

});
```

你也可以提供一个恒元（identity element）。例如，加法的恒元是 0，因为`x+0=x`。对于乘法，恒元是 1，因为`x*1=x`。在上面的情况下，恒元是一个空的`LinkedList<T>`，因为如果将空列表添加到另一个列表，你正在“添加”的那个列表不会发生变化：

```java
Stream<LinkedList<T>> listStream;

// 创建一个 Stream<LinkedList<T>>

LinkedList<T> bigList = listStream.reduce(new LinkedList<T>(), (LinkedList<T> list1, LinkedList<T> list2)->{

    LinkedList<T> retList = new LinkedList<T>();

    retList.addAll(list1);

    retList.addAll(list2);

    return retList;

});
```

注意，当提供恒元时，返回值不会被封装在`Optional`中——如果在空流上调用，`reduce()`将返回恒元。

二元运算符还必须满足结合律（associative），这意味着`(a+b)+c=a+(b+c)`。这是因为元素可以以任何顺序进行规约。例如，上面的规约可以这样执行：

![](img/01cc8d6667542262308c820b3f5bd37b_497_0.png)

这种规约等同于写入`((1+2)+(3+4))`。结合律属性也允许

## 第 57.15 节：使用流保留初始值 (Using Streams to Preserve Initial Values)

当你有一个流但想要保留初始值时，可以使用`Map.Entry`如下：

```java
public interface Ordered { default int getOrder() { return 0; }

public interface Valued<V> extends Ordered> boolean hasPropertyTwo(); V getValue(); }

public interface Thing<V> extends Ordered> boolean hasPropertyOne(); Valued<V> getValuedProperty(); }
```

```java
public <V extends Ordered> List<V> myMethod(List<Thing<V>> things) { 

    List<V> results = new ArrayList<>();

    for (Thing<V> thing : things) {

        if (thing.hasPropertyOne()) { 

            Valued<V> valued = thing.getValuedProperty();

            if (valued != null && valued.hasPropertyTwo()) {

                V value = valued.getValue();

                if (value != null) {

                    results.add(value);

                }

            }

        }

    }results.sort((a, b)->

    return Integer.compare(a.getOrder(), b.getOrder()); 

    return results;

});
```

使用流和方法引用重写的最后一种方法更易读，且接口和类一目了然——代码过程如下：

## 第 57.16 节：使用流合并 (Using Streams to Concatenate)

将`Stream<LinkedList<T>>`合并为单个`LinkedList<T>`可以使用如下方法：

```java
Stream<LinkedList<T>> listStream;

// 创建一个 Stream<LinkedList<T>>

Optional<LinkedList<T>> bigList = listStream.reduce((LinkedList<T> list1, LinkedList<T> list2)->{

    LinkedList<T> retList = new LinkedList<T>();

    retList.addAll(list1);

    retList.addAll(list2);

    return retList;

});
```

## 第 57.17 节：查找匹配谓元的第一个元素 (Finding the First Element that Matches a Predicate)

可以找到流中匹配条件的第一个元素。在本示例中，我们将查找直到找到结果：

```java
IntStream.iterate(1, i -> i + 1) // 生成 1,2,3,4...

.filter(i -> i > 5000) // 过滤到

findFirst(); // 找到第一个
```

注意，对于无限流，Java 将继续检查元素。对于有限流，Java 将耗尽元素并返回`Optional`。

## 第 57.18 节：使用流和方法引用编写自文档代码 (Using Streams and Method References to Write Self-Documenting Code)

方法引用是良好的自文档代码，且在流中使用方法引用使复杂的过程变得简单。请考虑以下代码：

```java
public interface Ordered { default int getOrder() { return 0; }

public interface Valued<V> extends Ordered> boolean hasPropertyTwo(); V getValue(); }

public interface Thing<V> extends Ordered> boolean hasPropertyOne(); Valued<V> getValuedProperty(); }
```



## 第 57.19 节：将 Optional 流转换为值流 (Converting a Stream of Optional to a Stream of Values)

你可能需要将产生 `Optional` 的流转换为值的流，只发射现有 `Optional` 中的值。（即：不包含空值且不处理 `Optional.empty()`）。

```java
Optional<String> op1 = Optional.empty();
Optional<String> op2 = Optional.of("Hello World");

List<String> result = Stream.of(op1, op2)
    .filter(Optional::isPresent)
    .map(Optional::get)
    .collect(Collectors.toList());
```

```java
System.out.println(result); //[Hello World]
```

## 第 57.20 节：获取 Stream 的切片（Slice）

示例：获取包含 30 个元素的 `Stream`，包含集合中第 21 到第 50 个（包含在内）元素。

```java
final long n = 20L; // 要跳过的元素数量
final long maxSize = 30L; // 流（stream）应该限制的最大元素数量
final Stream<T> slice = collection.stream().skip(n).limit(maxSize);
```

节点：

- 如果 `n` 为负或 `maxSize` 为负，将抛出 `IllegalArgumentException`
- `skip(long)` 和 `limit(long)` 都是中间操作
- 如果 `stream` 包含的元素少于 `n`，则 `skip(n)` 返回一个空流
- `skip(long)` 和 `limit(long)` 在顺序流流水线中是廉价的操作，但在有序的并行流水线中可能非常昂贵

## 第 57.21 节：基于 Stream 创建 Map

不包含重复键的简单情况：

```java
Stream<String> characters = Stream.of("A", "B", "C");
```

```java
Map<Integer, String> map = characters
    .collect(Collectors.toMap(element -> element.hashCode(), element -> element));
// map = {65=A, 66=B, 67=C}
```

为了使代码更具声明性，我们可以使用 `Function` 接口中的静态方法 - `Function.identity()`。我们可以用 `Function.identity()` 替换这个 lambda 表达式 `element -> element`。

如果映射后的键包含重复（根据 `Object.equals(Object)`），则在执行集合操作时会抛出 `IllegalStateException`。映射的键可能重复，请使用 `toMap(Function, Function, BinaryOperator)` 代替。

```java
Stream<String> characters = Stream.of("A", "B", "B", "C");
```

```java
Map<Integer, String> map = characters
    .collect(Collectors.toMap(
        element -> element.hashCode(),
        element -> element,
        (existingVal, newVal) -> (existingVal + newVal)));
```

```java
// map = {65=A, 66=BB, 67=C}
```

传递给 `Collectors.toMap(...)` 的 `BinaryOperator` 生成要存储在冲突缓存中的值。它可以返回该值，以便流中的第一个值具有优先权；返回新值，以便流中的最后一个值具有优先权；或者合并新旧值。

## 按值分组（Grouping by value）

当你需要执行等同于数据库级联“group by”操作时，可以使用 `Collectors.groupBy`。为了说明，以下代码创建了一个 `map`，将人的姓名映射到姓氏：

```java
List<Person> people = Arrays.asList(
    new Person("Sam", "Rossi"),
    new Person("Sam", "Verdi"),
    new Person("John", "Bianchi"),
    new Person("John", "Rossi"),
    new Person("John", "Verdi"));
```

```java
Map<String, List<String>> map = people.stream()
    .collect(
        // 将输入元素映射到键
        Collectors.groupingBy(Person::getName,
            // 将输入元素映射到值，
            // 如何存储值
            Collectors.mapping(Person::getSurname, Collectors.toList())
        ));
// map = {John=[Bianchi, Rossi, Verdi], Sam=[Rossi, Verdi]}
```

## 第 57.22 节：将 Stream 合并为单个 String

经常出现的一个用例是从 `Stream` 创建字符串，其中流项之间由特定字符分隔。在下面的示例中，可以使用 `Collectors.joining()` 方法：

```java
Stream<String> fruitStream = Stream.of("apple", "banana", "pear", "kiwi", "orange");

String result = fruitStream
    .filter(s -> s.contains("a"))
    .map(String::toUpperCase)
    .sorted()
    .collect(Collectors.joining(", "));
```

```java
System.out.println(result);
```

输出：`APPLE, BANANA, ORANGE, PEAR`

`Collectors.joining()` 方法还可以处理前缀和后缀：

```java
String result = fruitStream
    .filter(s -> s.contains("e"))
    .map(String::toUpperCase)
    .sorted()
    .collect(Collectors.joining(", ", "Fruits: ", "."));
```

```java
System.out.println(result);
```

输出：`Fruits: APPLE, ORANGE, PEAR.`

## 第 57.23 节：使用 Stream 排序

```java
List<String> data = new ArrayList<>();
data.add("Sydney");
data.add("London");
data.add("New York");
data.add("Amsterdam");
data.add("Mumbai");
data.add("California");
```

```java
System.out.println(data);

List<String> sortedData = data.stream().sorted().collect(Collectors.toList());

System.out.println(sortedData);
```

输出：`[Sydney, New York, Amsterdam, Mumbai, California]` `[Amsterdam, California, London, Mumbai, New York, Sydney]`

也可以在带参数的 `sorted()` 中使用 `comparator`：

```java
List<String> sortedData = data.stream()
    .sorted((s1, s2) -> s2.compareTo(s1))
    .collect(Collectors.toList());
```

输出：`[Sydney, Mumbai, London, New York, California, Amsterdam]`

## 第 57.24 节：原始类型 Stream

Java 为相应类型提供了专门的实现：`IntStream`（针对 `int`）、`LongStream`（针对 `long`）和 `DoubleStream`（针对 `double`）。除了经过优化，它们还提供了特定的方法，例如：

```java
double average = IntStream.of(10, 20, 30).average().getAsDouble();
```

## 第 57.26 节：将 Stream 结果收集到数组

类似于通过 `collect()` 获取 `Stream` 的集合，可以通过 `Stream.toArray()` 获取数组：

```java
List<String> fruits = Arrays.asList("apple", "banana", "pear", "kiwi", "orange");

String[] filteredFruits = fruits.stream()
    .filter(s -> s.contains("a"))
    .toArray(String[]::new);
```

```java
// 输出：apple, banana, pear, orange
System.out.println(Arrays.toString(filteredFruits));
```

## 第 57.27 节：使用 Stream 生成随机字符串

有时需要创建随机字符串，例如 Web 服务的 `Session ID` 或应用程序注册后的初始密码。可以使用 `Stream` 轻松实现。

首先，我们需要初始化一个随机数生成器。为了增强生成字符串的安全性，建议使用 `SecureRandom`。

注意：创建 `SecureRandom` 开销很大，因此最佳实践是只执行一次，并定期调用其一个 `setSeed()` 方法进行重新播。

```java
private static final SecureRandom rng = new SecureRandom(SecureRandom.generateSeed(20));
// 20 字节的种子是任意的，它是 JavaDoc 示例中使用的数字
```

字符（例如：仅限字母和数字）。因此，我们可以创建一个返回布尔值的方法，该方法后续可以用于过滤流（`Stream`）。

```java
//对于所有 0-9, a-z 和 A-Z 的字符返回 true
boolean useThisCharacter(char c) {
    // 检查范围以避免使用任何 Unicode 字母（例如：某些中文字符）
    return c >= '0' && c <= 'z' && Character.isLetterOrDigit(c);
}
```

接下来我们可以使用 `RNG`（随机数生成器）生成一个特定长度的随机字符串，其中包含通过 `useThisCharacter` 检查的字符集。

```java
public String generateRandomString(long length) {
    // 因为没有原生的 CharStream，我们使用 IntStream 代替
    // 并使用 mapToObj 将其转换为 Stream<Character>。
    // 需要指定 int 值的边界，以确保它们可以
    // 安全地转换为 Stream<Character>
    Stream<Character> randomCharStream = rng.ints(Character.MIN_CODE_POINT)
        .mapToObj(i -> (char)i)
        .filter(c -> this::useThisCharacter(c))
        .limit(length);
    String randomString = randomCharStream.collect(StringBuilder::new,
        StringBuilder::append, StringBuilder::append).toString();
    return randomString;
}
```

## 第 58 章：输入流与输出流

### 第 58.1 节：关闭流

完成流的操作后，必须关闭它们，否则可能会引入内存泄漏或导致文件处于打开状态。即使抛出异常，关闭流也是重要的。

```java
// Java SE 7
try(FileWriter fw = new FileWriter("filename");
     BufferedWriter bw = new BufferedWriter(fw);
     PrintWriter out = new PrintWriter(bw)) {
    
    out.println("the text"); //更多代码
    out.println("more text"); //更多代码
    
} catch (IOException e) { 
    // 按照你想要的方式处理此异常
}
```

记住：`try-with-resources` 保证在块退出时资源已经关闭，无论是通过正常的控制流退出，还是由于异常退出。

### 版本 \ Java SE 6

有时 `try-with-resources` 不是选项，或者你可能正在支持 Java 6 或更早版本。在这种情况下，适当的处理方法是使用 `finally` 块：

```java
FileWriter fw = null;
BufferedWriter bw = null;
PrintWriter out = null;
try {
    fw = new FileWriter("file.txt"); 
    bw = new BufferedWriter(fw);
    out = new PrintWriter(bw);
    out.println("the text");
    out.close();
} catch (IOException e) {
    // 按照你想要的方式处理此异常
} finally {
    try {
        if (out != null) {
            out.close();
        }
    } catch (IOException e) {
        // 通常在这里你做不了什么...
    }
}
```

注意，关闭包装流（wrapper stream）也会关闭其底层的流。这意味着你不能包装一个流、关闭包装流，然后继续使用原始流。

## 第 58.2 节：将 InputStream 读取为字符串

有时你可能希望将字节输入读取为字符串。为了做到这一点，你需要找到可以转换为字节的内容，而 `native Java` 的 UTF-16 代码点使用的是 `char`。这是通过 `InputStreamReader` 实现的。为了稍微加快过程，`通常`的做法是分配一个缓冲区，这样从输入读取时就不会有太大的开销。

### 版本 ≥ Java SE 7

```java
public String inputToString(InputStream input) throws Exception { 
    StringWriter writer = new StringWriter();
    char[] buffer = new char[1024];
    try (Reader reader = new BufferedReader(InputStreamReader(input, "UTF-8"))) { 
        int n;
        while ((n = reader.read(buffer)) != -1) {
            // 所有代码将 `reader` 的输出重定向到 `writer`，
            // 每次 1024 字节块
            writer.write(buffer, 0, n);
        }
    }
    return writer.toString();
}
```

将此示例转换为兼容 Java SE 6（及更版本）的代码留给读者练习。

## 第 58.3 节：包装输入/输出流

`OutputStream` 和 `InputStream` 有许多不同的类，每种类都有独特的功能。通过在一个流周围包装另一个流，你可以获得这两个流的功能。

你可以包装流任意次数，只需注意顺序即可。

有用的组合：

```java
File myFile = new File("targetFile.txt");
PrintWriter writer = new PrintWriter(new BufferedOutputStream(new FileOutputStream(myFile)));
```

在使用缓冲区写入文件之前对数据进行压缩和加密：

```java
Cipher cipher = ... // 初始化密码
File myFile = new File("targetFile.enc");
BufferedOutputStream outputStream = new BufferedOutputStream(new DeflaterOutputStream(new CipherOutputStream(new FileOutputStream(myFile, cipher))));
```

## 输入/输出流包装器列表

| 包装器 | 描述 |
| :--- | :--- |



# 第 58 章：BufferedOutputStream 与相关流

## 第 58.1 节：BufferedOutputStream

当 `OutputStream` 每次写入一个字节时，`BufferedOutputStream` 分块写入。这减少了系统调用的次数，从而提高了性能。

## 第 58.2 节：BufferedInputStream

`BufferedInputStream` 为输入流提供缓冲功能，减少系统调用次数，提高读取性能。

## 第 58.3 节：压缩与解压缩流

| 类名 | 功能 |
| :--- | :--- |
| `DeflaterOutputStream` | 执行数据压缩。 |
| `DeflaterInputStream` | 执行数据压缩。 |
| `InflaterOutputStream` / `InflaterInputStream` | 执行数据解压缩。 |

## 第 58.4 节：加密与校验流

| 类名 | 功能 |
| :--- | :--- |
| `CipherOutputStream` / `CipherInputStream` | 加密/解密数据。 |
| `DigestOutputStream` / `DigestInputStream` | 生成消息摘要验证数据完整性。生成校验和。 |
| `CheckedOutputStream` / `CheckedInputStream` | 校验和。 |

## 第 58.5 节：将 `InputStream` 读取为字符串

## 第 58.6 节：将字节写入 `OutputStream`

## 第 58.7 节：复制输入流到输出流

```java
void copy(InputStream in, OutputStream out) throws IOException {
    byte[] buffer = new byte[8192];
    int bytesRead;
    while ((bytesRead = in.read(buffer)) > 0) {
        out.write(buffer, 0, bytesRead);
    }
}
```

# 第 59 章：Readers 与 Writers

`Readers` 及其相应的子类提供了文本数据的简单 I/O。

## 第 59.1 节：BufferedReader

### 简介

`BufferedReader` 类是其他 `Reader` 类的包装器，有两个目的：

1. `BufferedReader` 为包装的 `Reader` 提供缓冲。这允许应用程序一次读取一个字符而不产生额外的 I/O 开销。
2. `BufferedReader` 提供了逐行读取的功能。

### 使用 `BufferedReader` 的基础

使用 `BufferedReader` 的标准模式如下。首先，你获取想要从其读取字符的 `Reader`。接下来你实例化包装该 `Reader` 的 `BufferedReader`。然后读取字符数据。最后你关闭 `BufferedReader`，从而关闭包装的 `Reader`。例如：

```java
File someFile = new File();
int aCount = 0;
try (FileReader fr = new FileReader(someFile);
     BufferedReader br = new BufferedReader(fr)) {
    // 统计 'a' 字符的数量。
    int ch;
    while ((ch = br.read()) != -1) {
        if (ch=='a') {
            aCount++;
        }
    }
    System.out.println(someFile + " 中有 " + aCount + " 个 a");
}
```

你可以将此模式应用于任何 `Reader`。

**注意：**

1. 我们使用了 Java 7（或更高版本）的 try-with-resources 来确保底层读取器始终关闭。这避免了潜在的资源泄漏。在更早的 Java 版本中，你会在 `finally` 块中显式地关闭 `BufferedReader`。
2. `try` 块内部的代码与我们直接从 `FileReader` 读取时使用的代码几乎相同。事实上，`BufferedReader` 的功能与它包装的 `Reader` 行为完全相同。不同在于这个版本要高效得多。

### Buffered 缓冲区大小

### `BufferedReader.readLine()` 方法示例：将文件所有行读取到 `List`

这是通过获取文件的每一行并将其添加到 `List<String>` 中实现的。然后返回该列表：

```java
public List<String> getAllLines(String filename) throws IOException {
    List<String> lines = new ArrayList<String>();
    try (BufferedReader br = new BufferedReader(new FileReader(filename))) {
        String line = null;
        while ((line = br.readLine()) != null) {
            lines.add(line);
        }
        return lines;
    }
}
```

Java 8 提供了一种更简洁的方法，使用 `lines()` 方法来实现这一点：

```java
public List<String> getAllLines(String filename) throws IOException {
    try (BufferedReader br = new BufferedReader(new FileReader(filename))) {
        return br.lines().collect(Collectors.toList());
    }
    return Collections.empty();
}
```

## 第 59.2 节：StringWriter 示例

`StringWriter` 类是一个字符流，用于收集来自字符串缓冲区的输出，可以构建字符串。`StringWriter` 类继承自 `Writer` 类。

在 `StringWriter` 类中，不会使用网络套接字和文件等系统资源，因此没有必要关闭 `StringWriter`。

```java
import java.io.*;
public class StringWriterDemo {
    public static void main(String[] args) throws IOException {
        char [] ary = new char[1024];
        StringWriter writer = new StringWriter();
        FileInputStream input = null;
        BufferedReader buffer = null;
        input = new FileInputStream("c:/stringwriter.txt");
        buffer = new BufferedReader(new InputStreamReader(input, "UTF-8"));
        int x;
        while ((x = buffer.read(ary)) != -1) {
            writer.write(ary, 0, x);
        }
        System.out.println(writer.toString());
        writer.close();
        buffer.close();
    }
}
```

上面的示例帮助我们了解如何使用 `BufferedReader` 从流中读取文件数据的 `StringWriter` 简单示例。

# 第 60 章：Preferences（首选项）

## 第 60.1 节：使用 Preferences

`Preferences` 可以存储用户设置，反映用户的个人应用程序设置，例如：编辑器字体、是否倾向于以全屏模式启动应用程序、是否勾选了“不再显示此”复选框等。

```java
public class ExitConfirmer {
    private static boolean confirmExit() {
        Preferences preferences =
        Preferences.userNodeForPackage(ExitConfirmer.class);
        boolean doShowDialog = preferences.getBoolean("showExitConfirmation", true); // true 是默认值

        if (!doShowDialog) {
            return true;
        }

        //
        // 此处显示对话框...
        //
        boolean exitWasConfirmed = ...; // 用户点击了确定还是取消
        boolean doNotShowAgain = ...; // 从“不再显示”复选框中获取值

        if (exitWasConfirmed && doNotShowAgain) {
            // 已确认退出，且用户选择了不再再次显示该对话框
            // 将这些设置保存到 Preferences 对象中，这样下次就不会再显示了
            preferences.putBoolean("showExitConfirmation", false);
        }
        return exitWasConfirmed;
    }

    public static void exit() {
        if (confirmExit()) {
            System.exit(0);
        }
    }
}
```

## 第 60.2 节：添加事件监听器

`Preferences` 对象会发出两种类型的事件：`ChangeEvent`（更改事件）和 `NodeChangeEvent`（节点更改事件）。每当节点的键值对发生变化时，`PreferenceChangeEvent` 会获取 `Properties` 对象发出的事件。`NodeChangeEvent` 可以列在 `PreferenceChangeListener` 中：

```java
// Java SE 8 版本
preferences.addPreferenceChangeListener(evt -> {
    String newValue = evt.getNewValue();
    String changedPreferenceKey = evt.getKey();
    Preferences changedNode = evt.getNode();
});
```

```java
// < Java SE 8 版本
preferences.addPreferenceChangeListener(new PreferenceChangeListener() {
    @Override
    public void preferenceChanged(ChangeEvent evt) {
        String newValue = evt.getNewValue();
        String changedKey = evt.getKey();
        Preferences changedNode = evt.getNode();
    }
});
```

此监听器不会监听子节点改变的键值对。每当 `Properties` 节点的子节点被添加或删除时，都会触发 `NodeChangeEvent`。

```java
preferences.addNodeChangeListener(new NodeChangeListener() {
    @Override
    public void childAdded(NodeChangeEvent evt) {
        Preferences addedChild = evt.getChild();
        Preferences parentOfAddedChild = evt.getParent();
    }

    @Override
    public void childRemoved(NodeChangeEvent evt) {
        Preferences removedChild = evt.getChild();
        Preferences parentOfRemovedChild = evt.getParent();
    }
});
```

## 第 60.3 节：获取 Preferences 的子节点

`Preferences` 对象始终代表整个树中的一个特定节点，如下所示：

| 路径 | 值 |
| :--- | :--- |
| `/com/myapp` | `ApplicationMode=true` |
|  | `showExitConfirmation=false` |
|  | `windowMaximized=true` |
|  | `organization=anotherapp` |
|  | `defaultFont=Helvetica` |
|  | `defaultPath=/home/Documents` |
|  | `dateFormat=pdf` |
|  | `openBrowserAfterExport=false` |

要选择 `/com/myapp` 节点：

1. 根据惯例，基于类的包名：

```java
package com.company.myapp;
// ...
// 因为这个类在 com.company.myapp 包中，将返回 /com/myapp 节点。
Preferences preferences = Preferences.userNodeForPackage(getClass());
```

2. 通过相对路径：

```java
Preferences preferences = Preferences.userRoot();
Preferences myNode = preferences.node("com/myapp");
```

使用相对路径（不以 `/` 开头）将相对于父节点。例如，在子节点上调用时，将相对于根节点：

```java
Preferences preferences = Preferences.userRoot();
Preferences prefix = preferences.node("one/two/three");
Preferences myWebPrefix = prefix.node("com/myapp"); // prefix 为 one/two/three
```

3. 通过绝对路径：

```java
Preferences preferences = Preferences.userRoot();
Preferences myWeb = preferences.node("/com/myapp");
```

在根节点上使用绝对路径与使用相对路径不同。区别在于，如果在子节点上调用，将相对于根节点：

```java
Preferences preferences = Preferences.userRoot();
Preferences prefix = preferences.node("one/two/three");
Preferences myWebPrefix = prefix.node("/com/myapp"); // prefix 为 one/two/three
```

## 第 60.4 节：导出 Preferences

```java
OutputStream os = null;
try {
  os = ...;
  preferences.exportSubtree(os);
} catch (IOException ioe) {
  // 向 OutputStream 写入数据时异常
  ioe.printStackTrace();
} catch (BackingStoreException bse) {
  // 从底层偏好存储器读取时异常
  bse.printStackTrace();
} finally {
  if (os != null) {
    try {
      os.close();
    } catch (IOException ignored) {}
  }
}
```

## 第 60.5 节：导入 Preferences

`Preferences` 节点可以从 XML 文档导入。导入旨在与 `Preferences` 的导出功能结合使用，因为它会创建相应的 XML 文档。

XML 文档会记录它们是从用户级还是系统 `Preferences` 导出的。因此，它们可以重新导入到各自的 `Preferences` 树中，而无需你去寻找或知道它们来自哪里。该静态方法将识别 XML 文档是从用户级还是系统 `Preferences` 导出的，并自动将其导入到它们导出的树中。

**Java SE 7 及以上版本：**

```java
try (InputStream is = ...) {
  // 这是对 Preferences 类的静态调用
  Preferences.importPreferences(is);
} catch (IOException ioe) {
  // 从 InputStream 读取数据时异常
  ioe.printStackTrace();
} catch (InvalidPreferencesFormatException ipfe) {
  // 解析 XML 文档树时异常
  ipfe.printStackTrace();
}
```

**Java SE 7 以下版本：**

```java
InputStream is = null;
try {
  is = ...;
  // 这是对 Preferences 类的静态调用
  Preferences.importPreferences(is);
} catch (IOException ioe) {
  // 从 InputStream 读取数据时异常
  ioe.printStackTrace();
} catch (InvalidPreferencesFormatException ipfe) {
  // 解析 XML 文档树时异常
  ipfe.printStackTrace();
} finally {
  if (is != null) {
    try {
      is.close();
    } catch (IOException ignored) {
    }
  }
}
```

## 第 60.6 节：移除事件监听器

事件监听器可以再次从任何 `Properties` 节点移除，这需要保留该监听器的实例。



# 版本 ≥ Java SE 8

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());

PreferenceChangeListener listener = evt -> {
    System.out.println(evt.getKey() + " 获取新值 " + evt.getNewValue());
};
preferences.addPreferenceChangeListener(listener);
```

```java
//
// 稍后...
//
```

```java
preferences.removePreferenceChangeListener(listener);
```

# 版本 < Java SE 8

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());
PreferenceChangeListener listener = new PreferenceChangeListener() {
    @Override
    public void onPreferenceChange(PreferenceChangeEvent evt) {
        System.out.println(evt.getKey() + " 获取新值 " + evt.getNewValue());
    }
}
preferences.addPreferenceChangeListener(listener);
```

```java
// 稍后...
preferences.removePreferenceChangeListener(listener);
```

对于`NodeChangeListener`同样适用。

## 第 60.8 节：获取偏好值

`Preferences`的值可以是`String`、`boolean`、`byte[]`、`double`、`float`、`int`或`long`类型。所有调用必须提供一个默认值，以防在`Preferences`节点中不存在指定的值。

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());

String someString = preferences.get("someKey", "这是默认值");
boolean someBoolean = preferences.getBoolean("someKey", true);
byte[] byte = preferences.getByteArray("someKey", new byte[0]);
double someDouble = preferences.getDouble("someKey", 88724.4d);
float someFloat = preferences.getFloat("someKey", 38723.3f);
int someInt = preferences.getInt("someKey", 13232);
long someLong = preferences.getLong("someKey", 282763786234L);
```

## 第 60.9 节：设置偏好值

要将一个值存储到`Preferences`节点中，可以使用其中一个`putXXX()`方法。`Preferences`节点的值可以是`String`、`boolean`、`byte[]`、`double`、`float`、`int`或`long`类型。

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());

preferences.put("someKey", "某个字符串值");
preferences.putBoolean("someKey", false);
preferences.putBoolean("someKey", new byte[0]);
preferences.putDouble("someKey", 187398123.4454d);
preferences.putFloat("someKey", 298321.445f);
preferences.putInt("someKey", 77637);
preferences.putLong("someKey", 2873984729834L);
```

## 第 61 章：集合工厂方法

| 方法 | 参数列表 | 描述 |
| :--- | :--- | :--- |
| `List.of(E e)` | | 一个可以是类或接口的泛型。 |
| `Set.of(E e)` | | 一个可以是类或接口的泛型。 |
| `Map.of(K k, V v)` | | 泛型的键值对，其中每个泛型都可以是类或接口。 |
| `Map.of(Map.Entry<? extends K, ? extends V>)` | | 一个`Map.Entry`实例，其键可以是类或接口，值亦然。 |

它们会记住它们是从用户级还是系统`Preferences`导出的。因此，它们可以重新导入到各自的`Preferences`树中，而无需你去寻找或知道它们来自哪里。静态函数将自动识别 XML 文档是从用户级还是系统`Preferences`导出的，并自动将其导入到它们导出的树中。

> Java SE 7

```java
try (InputStream is = ...) {
  // 这是对 Preferences 类的静态调用
  Preferences.importPreferences(is);
} catch (IOException ioe) {
  // 从 InputStream 读取数据时异常 ioe.printStackTrace();
}
```

```java
} catch (InvalidPreferencesFormatException ipfe) { // 解析
XML 文档树时异常 ipfe.printTrace();
}
```

# 版本 < Java SE 7

```java
InputStream is = null;
try {
  is = ...;
  // 这是对 Preferences 类的静态调用
  Preferences.importPreferences(is);
} catch (IOException ioe) {
  // 从 InputStream 读取数据时异常 ioe.printTrace();
} catch (InvalidPreferencesFormatException ipfe) { // 解析
XML 文档树时异常 ipfe.printTrace();
} finally {
  if (is != null) {
    try {
      is.close();
    } catch (IOException ignored) {
    }
  }
}
```

## 第 60.7 节：移除事件监听器

事件监听器可以再次从任何`Properties`节点移除，这需要保留该监听器的实例。

# 版本 ≥ Java SE 8

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());

PreferenceChangeListener listener = evt -> {
    System.out.println(evt.getKey() + " 获取新值 " + evt.getNewValue());
};
preferences.addPreferenceChangeListener(listener);
```

```java
//
// 稍后...
//
```

```java
preferences.removePreferenceChangeListener(listener);
```

# 版本 < Java SE 8

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());
PreferenceChangeListener listener = new PreferenceChangeListener() {
    @Override
    public void onPreferenceChange(PreferenceChangeEvent evt) {
        System.out.println(evt.getKey() + " 获取新值 " + evt.getNewValue());
    }
}
preferences.addPreferenceChangeListener(listener);
```

```java
// 稍后...
preferences.removePreferenceChangeListener(listener);
```

对于`NodeChangeListener`同样适用。

## 第 60.8 节：获取偏好值

`Preferences`的值可以是`String`、`boolean`、`byte[]`、`double`、`float`、`int`或`long`类型。所有调用必须提供一个默认值，以防在`Preferences`节点中不存在指定的值。

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());

String someString = preferences.get("someKey", "这是默认值");
boolean someBoolean = preferences.getBoolean("someKey", true);
byte[] byte = preferences.getByteArray("someKey", new byte[0]);
double someDouble = preferences.getDouble("someKey", 88724.4d);
float someFloat = preferences.getFloat("someKey", 38723.3f);
int someInt = preferences.getInt("someKey", 13232);
long someLong = preferences.getLong("someKey", 282763786234L);
```

## 第 60.9 节：设置偏好值

要将一个值存储到`Preferences`节点中，可以使用其中一个`putXXX()`方法。`Preferences`节点的值可以是`String`、`boolean`、`byte[]`、`double`、`float`、`int`或`long`类型。

```java
Preferences preferences = Preferences.userNodeForPackage(getClass());

preferences.put("someKey", "某个字符串值");
preferences.putBoolean("someKey", false);
preferences.putBoolean("someKey", new byte[0]);
preferences.putDouble("someKey", 187398123.4454d);
preferences.putFloat("someKey", 298321.445f);
preferences.putInt("someKey", 77637);
preferences.putLong("someKey", 2873984729834L);
```

## 第 61 章：集合工厂方法

| 方法 | 参数列表 | 描述 |
| :--- | :--- | :--- |
| `List.of(E e)` | | 一个可以是类或接口的泛型。 |
| `Set.of(E e)` | | 一个可以是类或接口的泛型。 |
| `Map.of(K k, V v)` | | 泛型的键值对，其中每个泛型都可以是类或接口。 |
| `Map.of(Map.Entry<? extends K, ? extends V>)` | | 一个`Map.Entry`实例，其键可以是类或接口，值亦然。 |

它们会记住它们是从用户级还是系统`Preferences`导出的。因此，它们可以重新导入到各自的`Preferences`树中，而无需你去寻找或知道它们来自哪里。静态函数将自动识别 XML 文档是从用户级还是系统`Preferences`导出的，并自动将其导入到它们导出的树中。

> Java SE 7

```java
try (InputStream is = ...) {
  // 这是对 Preferences 类的静态调用
  Preferences.importPreferences(is);
} catch (IOException ioe) {
  // 从 InputStream 读取数据时异常 ioe.printStackTrace();
}
```

```java
} catch (InvalidPreferencesFormatException ipfe) { // 解析
XML 文档树时异常 ipfe.printTrace();
}
```

# 版本 < Java SE 7

```java
InputStream is = null;
try {
  is = ...;
  // 这是对 Preferences 类的静态调用
  Preferences.importPreferences(is);
} catch (IOException ioe) {
  // 从 InputStream 读取数据时异常 ioe.printTrace();
} catch (InvalidPreferencesFormatException ipfe) { // 解析
XML 文档树时异常 ipfe.printTrace();
} finally {
  if (is != null) {
    try {
      is.close();
    } catch (IOException ignored) {
    }
  }
}
```

```java
for(String word: words) {
    multiMap.put(word, i); i++;
}
```

```java
// 打印所有单词
System.out.println(multiMap); // 输出 {Hi=[0, 2], World=[1, 5], All!=[3]} - 随机顺序

// 打印所有唯一单词
System.out.println(multiMap.keySet()); // 输出 [4] Hi, Hello, World!, All!) - 随机顺序

// 打印所有索引
System.out.println("Hello " + multiMap.get("Hello")); // 输出 [0, 2]

System.out.println("World " = + multiMap.get("World")); // 输出 [1, 5]

System.out.println("All " = + multiMap.get("All")); // 输出 [3]

System.out.println("Hi " = + multiMap.get("Hi")); // 输出 [4]

System.out.println("Empty " = + multiMap.get("Empty")); // 输出 null

// 打印唯一单词
System.out.println(multiMap.keySet()); // 输出 4
```

# 2. 来自 GS / Eclipse Collision的 HashMap

```java
String[] englishWords = {"one", "two", "three", "ball", "snow"};
String[] nrussianWords = {"jeden", "dwa", "trzy", "kula", "snieg"};
```

```java
// 创建 Multiset
Mutable<String, String> biMap = new
    HashMap(englishWords.length); // 创建英语-波兰字典
int i = 0;
for(String englishWord: englishWords) {

    biMap.put(englishWord, russianWords[i]);
    i++;
}
```

```java
// 打印单词计数
System.out.println(biMap); // 输出 {two=dwa, ball=kula, one=jeden, snow=snieg, three=trzy}; - 随机顺序
```



# 3. 来自 Guava 的 HashMultiMap

```java
String INPUT_TEXT = "Hello World! Hello All! Hi World"; // 解析文本为单词和索引

List<String> words = Arrays.asList(INPUT_TEXT.split(" ")); // 创建 Multimap

Multimap<String, Integer> multiMap = HashMultiMap.create();

// 填充 Multimap

int i = 0;

for(String word : words) {

    multiMap.put(word, i); i++;

}

// 打印所有单词

System.out.println(multiMap); // 输出 [Hi={4}, Hello=[0, 2], World!=[1, 5], All!={3}] - 键值随机顺序

// 打印所有唯一单词

System.out.println(multiMap.keySet()); // 输出 [Hi, Hello, World!, All!] - 随机顺序
```

```java
System.out.println("Empty = " + multiMap.get("Empty")); // 输出 []
// 打印所有单词计数
System.out.println(multiMap.size()); // 输出 6
// 打印唯一单词计数
System.out.println(multiMap.keySet().size()); // 输出 4
```

# 更多示例：

- 1. MultiValueMap
- 2. MultiValueMapLinked
- 3. MultiValueMapTree

# II. GS / Eclipse Collection

- 1. FastListMultimap
- 2. HashBagMultimap
- 3. TreeSortedSetMultimap
- 4. UnifiedSetMultimap

# III. Guava

- 1. HashMultimap
- 2. LinkedHashMapMultimap
- 3. LinkedListMultimap
- 4. TreeMultimap
- 5. ArrayListMultimap

# 第 62.2 节：Apache HashBag, Guava HashMultiset 和 Eclipse HashBag

Bag/multiset（集合）存储集合中的每个对象及其出现次数。接口上的额外方法允许一次添加或删除多个对象的副本。JDK 的对应物是 `HashMap<T, Integer>`，其中值是该键副本的数量。

| 类型 | Guava | Apache Commons Collections | GS Collections | JDK |
| :--- | :--- | :--- | :--- | :--- |
| 顺序 | 未定义 HashMultiset | Sorted TreeMultiset | | |
| 插入顺序 | LinkedHashMultiset | HashBag | HashBag | HashMap |
| | TreeBag | TreeBag | TreeMap | LinkedHashMap |
| | | 并发变 | | |
| 并发且排序 | Immutable collection | | | |
| 不变且排序 | ConcurrentHashMultiset | SynchronizedBag | SynchronizedBag | |
| | Collections.synchronizedMap(HashMap<String, Integer>) | | | |
| | SynchronizedBag | SynchronizedBag | | |
| | UnmodifiableBag | UnmodifiableBag | | |
| | Immutable collection | UnmodifiableBag | | |

Bag/multiset（集合）存储集合中的每个对象及其出现次数。接口上的额外方法允许一次添加或删除多个对象的副本。JDK 的对应物是 `HashMap<T, Integer>`，其中值是该键副本的数量。

| 类型 | Guava | Apache Commons Collections | GS Collections | JDK |
| :--- | :--- | :--- | :--- | :--- |
| 顺序 | 未定义 HashMultiset | Sorted TreeMultiset | | |
| 插入顺序 | LinkedHashMultiset | HashBag | HashBag | HashMap |
| | TreeBag | TreeBag | TreeMap | LinkedHashMap |
| | | 并发变 | | |
| 并发且排序 | Immutable collection | | | |
| 不变且排序 | ConcurrentHashMultiset | SynchronizedBag | SynchronizedBag | |
| | Collections.synchronizedMap(HashMap<String, Integer>) | | | |
| | SynchronizedBag | SynchronizedBag | | |
| | UnmodifiableBag | UnmodifiableBag | | |
| | Immutable collection | UnmodifiableBag | | |

Bag/multiset（集合）存储集合中的每个对象及其出现次数。接口上的额外方法允许一次添加或删除多个对象的副本。JDK 的对应物是 `HashMap<T, Integer>`，其中值是该键副本的数量。

（注：后续部分由于原文存在重复内容，已按要求进行翻译并保持格式一致）

```java
// 打印所有单词
System.out.println(multiMap); // 输出 {Hi=[0, 2], World=[1, 5], All!=[3]} - 随机顺序

// 打印所有唯一单词
System.out.println(multiMap.keySet()); // 输出 [4] Hi, Hello, World!, All!) - 随机顺序

// 打印所有索引索引
System.out.println("Hello " + multiMap.get("Hello")); // 输出 [0, 2]
System.out.println("World " = + multiMap.get("World")); // 输出 [1, 5]
System.out.println("All " = + multiMap.get("All")); // 输出 [3]
System.out.println("Hi " = + multiMap.get("Hi")); // 输出 [4]
System.out.println("Empty " = + multiMap.get("Empty")); // 输出 null

// 打印唯一单词
System.out.println(multiMap.keySet()); // 输出 4
```

# 2. 来自 GS / Eclipse Collision的 HashMap

```java
String[] englishWords = {"one", "two", "three", "ball", "snow"}; String[] nrussianWords = {"jeden", "dwa", "trzy", "kula", "snieg"};

// 创建 Multiset
Mutable<String, String> biMap = new
    HashMap(englishWords.length); // 创建英语-波兰字典
int i = 0;
for(String englishWord: englishWords) {

    biMap.put(englishWord, russianWords[i]);
    i++;
}
```

```java
// 打印单词计数
System.out.println(biMap); // 输出 {two=dwa, ball=kula, one=jeden, snow=snieg, three=trzy}; - 随机顺序
```

```java
// 打印所有唯一单词
System.out.println(biMap.keySet());
System.out.println(biMap.values()); // 顺序
// 输出 [snow, one, three, ball] - 随机顺序 // 输出 [dwa, kula, jeden, snieg, trzy] - 随机

// 打印单词翻译
System.out.println("one = " + biMap.get("one"));
System.out.println("two = " + biMap.get("two"));

// 输出 one = jeden // 输出 two = dwa
System.out.println("kula = " + biMap.inverse().get("kula"); // 输出 kula = ball
System.out.println("snieg = " + biMap.inverse().get("snieg"); // 输出 snieg = snow
System.out.println("empty = " + biMap.get("empty")); // 输出 empty = null

// 打印单词对计数
System.out.println(biMap.size()); // 输出 5
```

# 3. 来自 Guava 的 HashMultiMap

```java
String INPUT_TEXT = "Hello World! Hello All! Hi World"; // 解析文本为单词和索引

List<String> words = Arrays.asList(INPUT_TEXT.split(" ")); // 创建 Multimap

Multimap<String, Integer> multiMap = HashMultiMap.create();

// 填充 Multimap

int i = 0;

for(String word : words) {

    multiMap.put(word, i); i++;

}

// 打印所有单词

System.out.println(multiMap); // 输出 [Hi={4}, Hello=[0, 2], World!=[1, 5], All!={3}] - 键值随机顺序

// 打印所有唯一单词

System.out.println(multiMap.keySet()); // 输出 [Hi, Hello, World!, All!] - 随机顺序
```

```java
System.out.println("Empty = " + multiMap.get("Empty")); // 输出 []
// 打印所有单词计数
System.out.println(multiMap.size()); // 输出 6
// 打印唯一单词计数
System.out.println(multiMap.keySet().size()); // 输出 4
```

# 更多示例：

- 1. MultiValueMap
- 2. MultiValueMapLinked
- 3. MultiValueMapTree

# II. GS / Eclipse Collection

- 1. FastListMultimap
- 2. HashBagMultimap
- 3. TreeSortedSetMultimap
- 4. UnifiedSetMultimap

# III. Guava

- 1. HashMultimap
- 2. LinkedHashMapMultimap
- 3. LinkedListMultimap
- 4. TreeMultimap
- 5. ArrayListMultimap

# 第 62.2 节：Apache HashBag, Guava HashMultiset 和 Eclipse HashBag

Bag/multiset（集合）存储集合中的每个对象及其出现次数。接口上的额外方法允许一次添加或删除多个对象的副本。JDK 的对应物是 `HashMap<T, Integer>`，其中值是该键副本的数量。

| 类型 | Guava | Apache Commons Collections | GS Collections | JDK |
| :--- | :--- | :--- | :--- | :--- |
| 顺序 | 未定义 HashMultiset | Sorted TreeMultiset | | |
| 插入顺序 | LinkedHashMultiset | HashBag | HashBag | HashMap |
| | TreeBag | TreeBag | TreeMap | LinkedHashMap |
| | | 并发变 | | |
| 并发且排序 | Immutable collection | | | |
| 不变且排序 | ConcurrentHashMultiset | SynchronizedBag | SynchronizedBag | |
| | Collections.synchronizedMap(HashMap<String, Integer>) | | | |
| | SynchronizedBag | SynchronizedBag | | |
| | UnmodifiableBag | UnmodifiableBag | | |
| | Immutable collection | UnmodifiableBag | | |

（注：由于原文中存在大量重复内容，已根据要求完成翻译处理）

```java
FastList.newWith(array)
FastList.newWithNValues(10, 0) -> "1"
```

示例:

```java
System.out.println("create ArrayList start");
// 创建空列表
List<String> emptyGuava = Lists.newArrayList(); // 使用 guava
List<String> emptyJDK = new ArrayList<>(); // 使用 JDK
MutableList<String> emptyGS = FastList.newList(); // 使用 gs
// 创建包含 100 个元素的 List < String > = 正好 100 =
Lists.newArrayListWithCapacity(100); // 使用 guava List<String>
exactly100JDK = new ArrayList<>(100); // 使用 JDK
MutableList<String> empty100GS = FastList.newList(100); // 使用 gs
// 创建大约 100 个元素的列表
List<String> approx100 = Lists.newArrayListWithExpectedSize(100); //
using guava List<String> approx100JDK = new ArrayList<>(115); // 使用
MutableList<String> approx100GS = FastList.newList(115); // 使用 gs
```

```java
// 创建包含某些元素的列表
List<String>withElements = Lists.newArrayList("alpha", "beta", "gamma");
// 使用 guava List<String>withElementsJDK = Arrays.asList("alpha",
"beta", "gamma"); // 使用 JDK MutableList<String>withElementsGS =
FastList.newWith("alpha", "beta", "gamma"); // 使用
```



# 创建集合

## 1 创建 List

### 描述

创建空列表、从值创建列表、从任何集合创建列表、从任何 `Iterable` 创建列表、从任何 `Iterator` 创建列表、从数组创建列表。

#### JDK

`new ArrayList<>()`

#### guava

`Lists.newArrayList()`

#### gs

`FastList.newList()`

#### 示例

```
System.out.println(withElements); System.out.println(withElementsJDK);
System.out.println(withElementsGS);
```

```
// 从任何 Iterable 接口（任何集合）创建列表 Collection<String>
collection = new HashSet<>(3); collection.add("1");
collection.add("2");
collection.add("3");
```

```
List<String> fromIterable = Lists.newArrayList(collection); // 使用 guava
List<String> fromIterableJDK = new ArrayList<>(collection); // 使用 JDK
MutableList<String> fromIterableGS = FastList.newList(collection); // 使用 gs

System.out.println(fromIterable);
System.out.println(fromIterableJDK);
System.out.println(fromIterableGS);

/* 注意：JDK 仅从 Collection 创建列表，但 guava 和 gs 可以从
Iterable 和 Collection 创建列表 */
```

```
// 从任何 Iterator 创建列表
Iterator<String> iterator = collection.iterator();
List<String> fromIterator = Lists.newArrayList(iterator); // 使用 guava
System.out.println(fromIterator);
```

```
// 从任何数组创建列表
String[] array = {"4", "5", "6"};
List<String> fromArray = Lists.newArrayList(array); // 使用 guava
List<String> fromArrayJDK = Arrays.asList(array); // 使用 JDK
MutableList<String> fromArrayGS = FastList.newListWith(array); // 使用 gs
System.out.println(fromArray);
System.out.println(fromArrayJDK); System.out.println(fromArrayGS);
```

```
// 使用 fabric 创建列表
MutableList<String> fromFabricGS = FastList.newWithValues(10, () ->
String.valueOf(Math.random())); // 使用 gs
System.out.println(fromFabricGS);

System.out.println("create ArrayAdapter end");
```

## 2 创建 Set

### 描述

创建空集合、从值创建集合、从任何集合创建集合、从任何 `Iterable` 创建集合、从任何 `Iterator` 创建集合、从数组创建集合。

#### JDK

`new HashSet<>()`

`new HashSet<>(Arrays.asList("alpha", "beta", "gamma"))`

#### guava

`Sets.newHashSet()`

`Sets.newHashSet("alpha", "beta", "gamma")`

#### gs

`UnifiedSet.newSet()`

`UnifiedSet.newWith("alpha", "beta", "gamma")`

`new HashSet<>((collection) Sets.newHashSet(collection))`

`UnifiedSet.newSet(collection)`

- `Sets.newHashSet(iterable)` `UnifiedSet.newSet(iterable)`
- `Sets.newHashSet(iterator)`
- `new Sets.newHashSet(array)` `UnifiedSet.newSetWith(array)`
- `HashSet<>(Arrays.asList(array))`

### 示例

```
System.out.println("createHashSet start");

// 创建空集合
Set<String> emptyGuava = Sets.newHashSet(); // 使用 guava
Set<String> emptyJDK = new HashSet<>(); // 使用 JDK
Set<String> emptyGS = UnifiedSet.newSet(); // 使用 gs

// 创建包含 100 个元素的集合
Set<String> approx100 = Sets.newHashSetWithExpectedSize(100); // 使用 guava
Set<String> approx100JDK = new HashSet<>(130); // 使用 JDK
Set<String> approx100GS = UnifiedSet.newSet(130); // 使用 gs
```

```
// 从某些元素创建集合
Set<String> withElements = Sets.newHashSet("alpha", "beta", "gamma"); // 使用 guava
Set<String> withElementsSDK = new HashSet<>(
    (Arrays.asList("alpha", "beta", "gamma"))); // 使用 JDK
```

```
Set<String> withElementsGS = UnifiedSet.newSetWith("alpha", "beta",
"gamma"); // 使用 gs

System.out.println(withElements); System.out.println(withElementsJDK);
System.out.println(withElementsGS);
```

```
// 从任何 Iterable 接口（任何集合）创建集合
Collection<String> collection = new ArrayList<>(3);
collection.add("2");
collection.add("3");

Set<String> fromIterable = Sets.newHashSet(collection); // 使用 guava
Set<String> fromIterableJDK = new HashSet<>(collection); // 使用 JDK
Set<String> fromIterableGS = UnifiedSet.newSet(collection); // 使用 gs

System.out.println(fromIterable);
System.out.println(fromIterableJDK);
System.out.println(fromIterableGS);

/* 注意：JDK 仅从 Collection 创建集合，但 guava 和 gs
可以从任何 Iterable 创建集合 */
```

```
// 从任何 Iterator 创建集合
Iterator<String> iterator = collection.iterator();
Set<String> fromIterator = Sets.newHashSet(iterator); // 使用 guava
System.out.println(fromIterator);
```

```
// 从任何数组创建集合
String[] array = {"4", "5", "6"};
Set<String> fromArray = Sets.newHashSet(array); // 使用 guava
Set<String> fromArrayJDK = new HashSet<>(Arrays.asList(array)); // 使用 JDK
Set<String> fromArrayGS = UnifiedSet.newSetWith(array); // 使用 gs

System.out.println(fromArray);
System.out.println(fromArrayJDK); System.out.println(fromArrayGS);
```

## 3 创建 Map

### 描述

创建空 map、创建带容量的 map、从其他 map 创建 map、从键创建 map。

#### JDK

`new HashMap<>()`

#### guava

`Maps.newHashMap()`

`Maps.newHashMapWithExpectedSize(100)`

#### gs

`UnifiedMap.newMap()`

`UnifiedMap.newMap(130)`

### 示例

```
System.out.println("createHashMap start");

// 创建空 map
Map<String, String> emptyGuava = Maps.newHashMap(); // 使用 guava
Map<String, String> emptyJDK = new HashMap<>(); // 使用 JDK
Map<String, String> emptyGS = UnifiedMap.newMap(); // 使用 gs
```

```
// 创建大约包含 100 个元素的 map
Map<String, String> approx100 = Maps.newHashMapWithExpectedSize(100); // 使用 guava
Map<String, String> approx100JDK = new HashMap<>(130); // 使用 JDK
Map<String, String> approx100GS = UnifiedSet.newMap(130); // 使用 gs
```

```
// 从另一个 map 创建 map
Map<String, String> map = new HashMap<>(3);
map.put("k1", "v1");
map.put("k2", "v2");

Map<String, String> withMap = Maps.newHashMap(map); // 使用 guava
Map<String, String> withMapJDK = new HashMap<>(map); // 使用 JDK
Map<String, String> withMapGS = UnifiedMap.newMap(map); // 使用 gs
```

```
System.out.println(withMap); System.out.println(withMapJDK);
System.out.println(withMapGS);
```

```
// 从键创建 map
Map<String, String> withKeys = UnifiedMap.newKeysValues("1", "a",
"2", "b");
System.out.println(withKeys);

System.out.println("createHashMap end");
```

### 更多示例

`CreateCollectionTest`

1. `CollectionCompare`
2. `CollectionSearch`
3. `JavaTransform`

# 第 63 章：并发集合

并发集合是一种允许多个线程同时访问的集合。不同的线程通常可以遍历集合的内容并添加或删除元素。集合负责确保不会损坏。[1]:https://stackoverflow.com/documentation/java/90/collections#t=20162

## Section 63.1 线程安全的集合

默认情况下，各种 `Collection` 类型不是线程安全的。但是，很容易让集合变为线程安全。

```
List<String> threadSafeList = Collections.synchronizedList(new ArrayList<String>());
Set<String> threadSafeSet = Collections.synchronizedSet(new HashSet<String>());
Map<String, String> threadSafeMap = Collections.synchronizedMap(new HashMap<String, String>());
```

当你使集合变为线程安全时，你不应该通过原始集合访问，而应该通过线程安全的包装器。

**版本 ≥ Java 5**

从 Java 5 开始，`java.util.collections` 有几个新的线程安全集合，不需要各种 `Collections.synchronized` 方法。

```
List<String> threadSafeList = new CopyOnWriteArrayList<String>();
Set<String> threadSafeSet = new ConcurrentHashSet<String>();
Map<String, String> threadSafeMap = new ConcurrentHashMap<String, String>();
```

## Section 63.2 向 ConcurrentHashMap 插入

```java
public class InsertIntoConcurrentHashMap {

    public static void main(String[] args) {

        ConcurrentHashMap<Integer, SomeObject> concurrentHashMap = new ConcurrentHashMap<Integer, SomeObject>();

        SomeObject value = new SomeObject();
        Integer key = 1;

        SomeObject previousValue = concurrentHashMap.putIfAbsent(1, value);
        if (previousValue != null) {
            // 那么某个值已经映射到 key = 1。传递给
            // putIfAbsent 方法的 value 没有被插入，任何其他线程调用
            // concurrentHashMap.get(1) 都不会接收到线程尝试插入的 'value'
            // 决定你想如何处理这种情况。
        }
    }
}
```

## Section 63.3 并发集合 (Concurrent Collections)

并发集合是线程安全集合的泛化，允许在并发环境中进行更广泛的使用。

虽然线程安全的集合允许从多个线程进行安全的元素添加或删除，但它们并不一定在相同的上下文中具有安全的迭代器（例如，你可能无法在一个线程中安全地遍历集合，而另一个线程正在通过添加/删除元素来修改它）。

这正是并发集合的用武之地。

由于迭代通常是集合中多个批量操作方法的实现基础，例如 `addAll`、`removeAll` 或者以及复制（通过构造函数或其他手段）、排序等……因此并发集合的使用场景实际上非常广泛。

例如，Java SE 5 `util.concurrent.CopyOnWriteArrayList` 是一个线程安全且并发的 `List` 实现，它的 javadoc 如下所示：

“快照”风格的迭代器使用指向迭代器创建时数组状态的引用。该数组在迭代器的生命周期内永远不会改变，因此不会发生干扰，且保证迭代器不会抛出 `ConcurrentModificationException`。

因此，以下代码是安全的：

```java
public class ThreadSafeAndConcurrent {

    public static final List<Integer> LIST = new CopyOnWriteArrayList<>();

    public static void main(String[] args) throws InterruptedException {

        Thread modifier = new Thread(new ModifierRunnable());
        Thread iterator = new Thread(new IteratorRunnable());

        modifier.start();
        iterator.start();

        modifier.join();
        iterator.join();
    }

    public static final class ModifierRunnable implements Runnable {

        @Override
        public void run() {

            try {

                for (int i = 0; i < 50000; i++) {

                    LIST.add(i);
                }
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```



# 并发集合与序列化

## 并发集合的迭代

```java
                }

            } catch (Exception e) {

                e.printStackTrace();

            }

        }

    }

    public static final class IteratorRunnable implements Runnable {

        @Override

        public void run() {

            try {

                for (int i = 0; i < 10000; i++) {

                    long total = 0;

                    for (Integer inList : LIST) {

                        total += inList;

                    }

                    System.out.println(total);

                }

            } catch (Exception e) {

                e.printStackTrace();

            }

        }

    }

}
```

另一个关于迭代的并发集合是`ConcurrentLinkedQueue`，它指出：

迭代器是弱一致的（weakly consistent），返回的元素反映了队列在某个时间点或自迭代器创建以来的状态。它们不会抛出`java.util.ConcurrentModificationException`，并且可以与其他操作并发进行。自迭代器创建以来包含在队列中的元素将恰好返回一次。

应该检查 javadoc 来查看一个集合是否是并发的。`iterator()`方法返回的迭代器的属性（如“快速失败”、“弱一致”等）是需要关注的最重要属性。

## 线程安全但非并发的示例

在上面的代码中，将`LIST`更改为
`public final List<Integer> LIST = Collections.synchronizedList(new ArrayList<>());`

可能会导致异常（尽管在统计上，在大多数现代多 CPU/多核架构上不会发生这种情况）。

来自`Collections`工具方法的同步集合在元素的添加/删除元素方面是线程安全的，但在迭代方面不是（除非传递给它的集合在创建时已经是同步的）。

## 第 64 章：选择集合

Java 提供了多种集合。选择使用哪种集合可能是困难的。请参见“示例”部分以获取易于遵循的流程图，为任务选择合适的集合。

### 第 64.1 节：Java 集合流程图

使用以下流程图为任务选择合适的集合。

![](img/01cc8d6667542262308c820b3f5bd37)

[流程图内容由于原文中未提供具体文本描述，此处保留图片占位]

## 序列化与版本控制

序列化运行时为每个可序列化类关联了一个版本号，称为`serialVersionUID`，它在反序列化期间用于验证序列化对象的发送方和接收方加载的该对象的类是否与序列化兼容。如果接收方加载的对象类的`serialVersionUID`与相应发送方类的`serialVersionUID`不同，则反序列化将导致`InvalidClassException`。可序列化类可以通过显式声明一个名为`serialVersionUID`的字段来声明其`serialVersionUID`，该字段必须是`static`、`final`且类型为`long`：

```
ANY-ACCESS-MODIFIER static final long serialVersionUID = 1L;
```

### 如何使类符合序列化条件

要持久化一个对象，相应的类必须实现`java.io.Serializable`接口。

```java
import java.io.Serializable;

public class SerialClass implements Serializable {

    private static final long serialVersionUID = 1L;

    public Date SerialClass() {

        currentTime = Calendar.getInstance().getTime();

    }

}
```

```java
public Date getCurrentTime() {

    return currentTime;

}
```

### 如何将对象写入文件

现在我们需要将此对象写入文件系统。我们使用`java.io.ObjectOutputStream`来此目的。

```java
import java.io.FileOutputStream; 

import java.io.ObjectOutputStream;

import java.io.IOException;
```

```java
public class PersistSerialClass {

    public static void main(String [] args) {
```

### 如何从序列化状态重新创建对象

可以使用下所示的`java.io.ObjectInputStream`在稍后从文件系统读取存储的对象：

```java
import java.io.FileInputStream;

import java.io.ObjectInputStream;

import java.io.IOException;

import java.lang.ClassNotFoundException;
```

```java
public class ReadSerialClass {

    public static void main(String[] args) {

        String filename = "time.ser";

        SerialClass time = null;

        try {

            ObjectInputStream in = new ObjectInputStream(new FileInputStream(filename)); 

            time = (SerialClass)in.readObject();

            in.close();

        } catch(IOException ex) {

            ex.printStackTrace();

        } catch(ClassNotFoundException cnfe) {

            cnfe.printStackTrace();

        }

        // 输出还原后的时间

        System.out.println("Restored time: " + time.getTime());

    }

}
```

序列化的类是以二进制形式存在的。如果类定义发生变化，反序列化可能会出现问题：详情请参见《Java 序列化规范》中的“序列化对象的版本控制”章节。

序列化一个对象会序列化以其为根的整个对象图，并在存在循环图的情况下正常运行。提供了一个`reset()`方法来强制`ObjectOutputStream`忘记已经序列化的对象。

## Transient 字段 - 序列化

### 第 66.2 节：自定义序列化

在例例中，我们想要创建一个类，它将在初始化期间作为参数传递的两个整数范围之间生成一个随机数并输出到控制台。

```java
public class SimpleRangeRandom implements Runnable { 

    private int min;

    private int max;

    private Thread thread;

    public SimpleRangeRandom(int min, int max) { 

        this.min = min; 

        this.max = max; 

        thread = new Thread(this); 

        thread.start();

    }

    @Override

    private void writeObject(ObjectOutputStream out) throws IOException;

    private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException;

    public void run() {

        while (true) {

            Random rand = new Random();

            System.out.println("Thread: " + thread.getId() + " Random:" + rand.nextInt(max - min)); 

            try {

                Thread.sleep(10000);

            } catch (InterruptedException e) {

                e.printStackTrace();

            }

        }

    }

}
```

如果我们想让这个类变为可序列化，将会有一些问题。
`Thread`是某些不可序列化的系统级类之一。
因此，我们需要将线程声明为`transient`。通过这样做，我们能够序列化该类的对象，但仍然存在问题。正如你在构造函数所示，我们设置了随机生成器的`min`和`max`值，之后我们启动了负责生成和打印随机值的线程。因此，当通过调用`readObject()`构造函数还原持久化对象时，由于没有创建对象，该方法不会再次运行。在这种情况下，我们需要通过提供类内部的方法来开发自定义序列化。这些方法是：

```java
private void writeObject(OutputStream out) throws IOException;

private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException;
```

因此，通过在`readObject()`中添加我们的实现，我们可以初始化并启动线程：

```java
class RangeRandom implements Serializable, Runnable {

    private int min; 

    private int max;

    private transient Thread thread; // transient 应该是任何无法被序列化的字段，例如 Thread 或任何你不希望序列化的字段

    public RangeRandom(int min, int max) { 

        this.min = min;

        this.max = max;

        thread = new Thread(this); 

        thread.start();

    }

    @Override

    public void run() {

        while(true) {

          Random rand = new Random();

          System.out.println("Thread: " + thread.getId() + " Random:" + rand.nextInt(max - min)); 

          try {

            Thread.sleep(10000);

          } catch (InterruptedException e) {

            e.printStackTrace();

          }

        }

    }

    private void writeObject(ObjectOutputStream oos) throws IOException {

        oos.defaultWriteObject();

    }

    private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException {

        in.defaultReadObject();

        thread = new Thread(this);

        thread.start();

    }

}
```

这是我们示例的 main 方法：

```java
public class Main {

    public static void main(String[] args) {

        System.out.println("Hello");

        RangeRandom rangeRandom = new RangeRandom(1,10);

        FileOutputStream fos = null; 

        ObjectOutputStream out = null;

        try {

            fos = new FileOutputStream("test");

            out = new ObjectOutputStream(fos);

            out.writeObject(rangeRandom);

            out.close();

        } catch(IOException e) {

            e.printStackTrace(); 

        }

        RangeRandom rangeRandom2 = null;

        FileInputStream fis = null;

        ObjectInputStream in = null;

        try {

            fis = new FileInputStream("test");

            in = new ObjectInputStream(fis);

            rangeRandom2 = (RangeRandom)in.readObject();

            in.close();

        } catch(IOException e) {

            e.printStackTrace(); 

        } catch(ClassNotFoundException e) {

            e.printStackTrace(); 

        }

    }

}
```



如果你运行`main`方法，你会看到每个`RangeRandom`实例有两个线程在运行，这是因为`Thread.start()`方法位于构造函数和`readObject()`中。

## 第 66.3 节：版本控制与 serialVersionUID

当你实现`java.io.Serializable`接口使类可序列化时，编译器会查找名为`serialVersionUID`的`long`类型的静态字段。如果类没有显式声明此字段，编译器将创建一个此类字段，并分配一个通过实现相关的计算值。该计算取决于类的各个方面，并遵循 Sun 给出的对象序列化规范。但是，该值无法保证在所有编译器实现中都是相同的。

该值用于检查类相对于序列化的兼容性，这是在反序列化保存的对象时进行的。序列化运行时验证从反序列化数据读取的`serialVersionUID`与类中声明的`serialVersionUID`是否完全相同。如果不是，它将抛出`InvalidClassException`。

强烈建议你在所有想要变为序列化的类中显式声明并初始化类型为`long`且名为`serialVersionUID`的静态字段，而不是依赖该字段值的默认计算，即使你打算使用版本控制。`serialVersionUID`的计算非常敏感，并且在不同的编译器实现之间可能会不同，因此即使对于相同的类，你也可能遇到`InvalidClassException`。只要`serialVersionUID`相同，Java 序列化就可以处理类的不同版本。兼容和不兼容的变化包括：

- **添加字段**：当类重构时拥有流中没有出现的字段。如果需要类特定的初始化，类可以提供`readObject`方法将层次结构初始化为非默认值。
- **添加类**：流将包含流中每个对象的类型层次结构。将流中的层次结构与当前类进行比较可以检测出额外的类。由于流中没有初始化对象的信息，类的字段将被初始化为默认值。
- **移除类**：将流中的类层次结构与当前类可以检测到某个类已被删除。在这种情况下，该类对应的字段和对象将从流中读取。基本类型字段会被丢弃，被删除类引用的对象将被创建，因为它们在流的后续部分可能会被再次引用。它们将在流被垃圾回收或重置时被垃圾回收。

**添加 writeObject/readObject 方法：** 如果读取流的版本具有了这些方法，则期望`readObject`像往常一样，通过默认序列化从流中读取所需的数据。在读取任何可选数据之前，它应该调用`defaultReadObject`。`writeObject`方法被期望像往常一样调用`defaultWriteObject`来写入所需的数据，然后写入可选数据。

**添加 java.io.Serializable：** 这等同于添加类型。该类将没有值，因为它的字段将初始化为默认值。对非序列化类的子化要求该类的超类型有一个无参构造函数，且该类本身将初始化为默认值。如果没有无参构造函数，则抛出`InvalidClassException`。

**更改字段的访问权限：** 访问修饰符`public`、`package`、`protected`和`private`对序列化为字段分配值的能力没有影响。

**将字段从 static 改为 nonstatic 或从 transient 改为非 transient** 当依赖默认序列化来计算可序列化字段时，此更改等同于向类添加了字段。新字段将被写入流中，但早期的类将忽略该值，因为序列化不会为`static`或`transient`字段赋值。

## 不兼容的更改

**删除字段：** 如果类中删除了一个字段，写入的流将不包含它的值。当流被早期的类读取时，该字段将被设置为默认值，因为流中没有可用值。然而，这个默认值可能会不利地影响早期版本履行其约的能力。

**在层次结构中向上或向下移动类：** 这是不允许的，因为流中的数据出现顺序是错误的。

**将非静态字段更改为静态或将 nont 字段更改为 transient：** 当依赖默认序列化时，此更改等同于从类中删除一个字段。该版本的类将不会将数据写入流，因此早期版本的类将无法读取。与删除字段一样，早期版本的字段将初始化为默认值，这可能导致类以意外的方式失败。

**更改基本类型字段的声明类型：** 类的每个版本都按其声明类型写入数据。早期版本尝试读取该字段将失败，因为流中的数据类型与字段类型不匹配。

更改`writeObject`或`readObject`方法，使其不再写入或读取默认字段数据，或者更改使其尝试写入或读取之前版本未执行的操作。默认字段数据必须在流中保持一致地出现或不出现。

将一个类从`Serializable`更改为`Externalizable`或反之是不兼容的更改，因为流将包含与可用类实现不兼容的数据。

将一个类从非枚举类型更改为枚举类型或反之是不兼容的更改，因为流将包含与可用类实现不兼容的数据。

向类中添加`writeReplace`或`readResolve`方法与产生与类任何旧版本不兼容的对象的行为是不兼容的。

## 第 66.4 节：使用 Gson 进行序列化

使用 Gson 进行序列化非常简单，并将输出正确的 JSON。

```java
public class Employ {

    private String firstName;

    private String lastName;

    private int age;

    private BigDecimal salary;

    private List<String> skills;

    // getters and setters

}
```

（序列化）

```java
//Skills
List<String> skills = new LinkedList<String>(); 

skills.add("leadership");

skills.add("Java Experience");
```

```java
//Employ
Employ obj = new Employ();

obj.setFirstName("Christian");

obj.setLastName("Lusardi");

obj.setAge(25);

obj.setSalary(new BigDecimal("10000")); 

obj.setSkills(skills);
```

```java
//Serialization
Gson gson = new Gson();

String json = gson.toJson(obj);

{"firstName":"Christian","LastName":"Lusardi","age":25,"salary":10000,"skills":["leadership","Java Experience"]}
```

注意，你不能序列化具有循环引用的对象，因为会导致无限递归。

（反序列化）

```java
// it's very simple...
// 假设 json 是之前的 String 对象... 
Employ obj2 = gson.fromJson(json, Employ.class); // obj2 和 obj 一样
```

## 第 66.5 节：使用 Jackson 进行自定义 JSON 反序列化

我们以 JSON 格式消耗 API 并将其反序列化为 POJO。Jackson 的`org.codehaus.jackson.map.ObjectMapper`“开箱即用”，在大多数情况下实际上什么都不需要做。但有时我们需要自定义反序列化器来满足自定义需求，本教程将引导你完成创建自己的自定义反序列化的过程。

假设我们有以下实体。

```java
public class User {

    private Long id; 

    private String name; 

    private String email;

    // 为了清晰省略了 getter setter 

}
```

```java
public class Program {

    private Long id;

    private String name; 

    private User CreatedBy; 

    private String contents;

    // 为了清晰省略了 getter setter 

}
```

让我们先序列化一个对象。

```java
User user = new User();

user.setId(1L);

user.setEmail("example@com");

user.setName("Bazlur Rahman");

Program program = new Program();

program.setId(1L);

program.setName("Program #1"); 

program.setCreatedBy(user);

program.setContents("Some contents");
```

```java
ObjectMapper objectMapper = new ObjectMapper();

String json = objectMapper.writeValueAsString(program);

System.out.println(json);
```

上述代码将产生 JSON：

```json
{
  "id":1,
  "name":"Program #1",
  "createdBy": {
    "id":1,
    "name":"Bazlur Rahman",
    "email":"example@com"
  },
  "contents":"Some contents"
}
```

现在可以非常容易地反向操作。假设我们有这个 JSON，使用`ObjectMapper`将其反序列化为对象——现在假设我们有一个与`Program`类不匹配的 JSON。

```json
{
  "id":1,
  "name":"Program #1",
  "ownerId":1,
  "contents":"Some contents"
}
```

查看 JSON 字符串，你可以看到它有一个`ownerId`字段。现在如果你像之前那样序列化这个 JSON，将会抛出异常。

有两种方法可以避免异常并进行序列化：

忽略未知字段
忽略`ownerId`。在`Program`类中添加以下注解：

```java
@JsonIgnoreProperties(ignoreUnknown = true)
public class Program {}
```

但在某些情况下你确实需要这个`ownerId`字段。假设你想将其关联到`User`类。在这种情况下，你需要编写一个自定义反序列化器。

如你所见，首先你需要从`JsonParser`获取`JsonNode`。然后你可以使用`get()`方法从`JsonNode`中提取信息，并且必须确保字段名正确。拼写错误会导致异常。

最后，你必须将`ProgramDeserializer`注册到`ObjectMapper`。

```java
ObjectMapper mapper = new ObjectMapper();

SimpleModule module = new SimpleModule();

module.addDeserializer(Program.class, new ProgramDeserializer());

mapper.registerModule(module);
```

```java
String newJsonString = "{\"id\":1,\"name\":\"Program #1\",\"ownerId\":1,\"contents\":\"Some contents\"}";

final Program program2 = mapper.readValue(newJsonString, Program.class);
```

或者，你可以使用注解直接注册反序列化器：

```java
@JsonDeserialize(using = ProgramDeserializer.class)
public class Program {}
```

## 第 67 章：Optional

`Optional`是一个容器对象，可能包含也可能不包含空值。如果值存在，`isPresent()`将返回`true`，`get()`将返回该值。
还提供了依赖于包含的值存在的其他方法，例如`orElse()`，在值不存在时返回一个默认值；而`ifPresent()`在值存在时执行一个代码块。

## 第 67.1 节：Map

使用`Optional`的`map()`方法来处理可能为`null`的值，而无需显式的空检查：
（注意`map()`和`filter()`操作是立即求值的，与`Stream`对应的操作不同，后者只有在终端操作时才会执行）。

语法：
`public <U> Optional<U> map(Function<? super T,? extends U> mapper)`

示例：

```java
String value = null;

return Optional.ofNullable(value).map(String::toUpperCase).orElse("NONE")
// 返回 "NONE"

String value = "something";

return Optional.ofNullable(value).map(String::toUpperCase).orElse("SOMETHING")
// 返回 "SOMETHING"
```

`Optional.map()`在其映射函数返回`null`时会返回一个空`Optional`，你可以链调用多个`map()`操作作为空安全解引的形式。这被称为空安全链式。
考虑以下示例：
`String value = foo.getBar().getBaz().toString();`
`getBar`、`getBaz`和`toString`中的任何一个都可能抛出`NullPointerException`。

这里是使用`Optional`从`toString()`获取值的另一种方法：

```java
String value = Optional.ofNullable(foo)
.map(Foo::getBar)
.map(Bar::getBaz)
.map(Baz::toString)
.orElse("");
```

如果任何映射函数返回`null`，这将返回一个空字符串。下面是另一个示例，但略有不同。只有当其中一个映射函数返回`null`时，它才会打印该值（注：此处逻辑应为存在时打印）。

```java
Optional.ofNullable(foo)
.map(Foo::getBar)
.map(Bar::getBaz)
.map(Baz::toString)
.ifPresent(System.out::println);
```

## 第 67.2 节：当 Optional 为空时返回默认值

不要使用`Optional.get()`，因为可能会抛出`NoSuchElementException`。`Optional.orElse(T)`和`Optional.orElseGet(Supplier<? extends T>)`方法提供在`Optional`为空时提供默认值的方法。

```java
String value = "something";

return Optional.ofNullable(value).orElse("defaultValue"); // 返回 "something"
return Optional.ofNullable(value).orElseGet(() -> getDefaultValue()); // 返回 "something" (永远不会调用 getDefaultValue() 方法)

String value = null;

return Optional.ofNullable(value).orElse("defaultValue"); // 返回 "defaultValue"
return Optional.ofNullable(value).orElseGet(() -> getDefaultValue()); // 调用 getDefaultValue() 并返回其结果
```



`orElse`和`orElseGet`之间的区别在于，后者只有在`Optional`为空时才会求值，而前者的参数即使`Optional`不为空也会被求值。因此，`orElse`应该仅用于常量，永远不要用于基于任何计算提供值。

## 第 67.3 节：如果没有值，则抛出异常

使用`Optional`的`orElseThrow()`方法获取包含的值，或者在未设置时抛出异常。这与调用`get()`类似，但它允许任意异常类型。该方法接收一个必须返回要抛出的异常的供应商。

在第一个示例中，该方法简单返回包含的值：

```
Optional optional = Optional.of("something");
return optional.orElseThrow(IllegalArgumentException::new());
// 返回 "something" 字符串
```

在第二个示例中，由于没有设置值，该方法抛出异常：

```
Optional optional = Optional.empty();
return optional.orElseThrow(IllegalArgumentException::new()); // 抛出 IllegalArgumentException
```

如果需要抛出带有消息的异常，也可以使用 lambda 语法：

```
optional.orElseThrow(() -> new IllegalArgumentException("Illegal"));
```

## 第 67.4 节：使用 Supplier 延迟地提供默认值

`orElseGet`方法接收一个对象，所以你可能会奇怪为什么这里有一个提供`Supplier`的选项（`orElse`方法）。考虑：

```
String value = "something";
orElseGet(getValueThatIsHardToCalculate()); // 返回 "something"
```

即使其结果未被使用（因为`Optional`不为空），仍然会调用`getValueThatIsHardToCalculate()`。为了避免这种代价，你提供了一个供应商：

```
String value = "something";
return Optional.ofNullable(value).orElseGet(() -> getValueThatIsHardToCalculate()); // 返回 "something"
```

这样，`getValueThatIsHardToCalculate()`只会在`Optional`为空时被调用。

## 第 67.5 节：Filter

`filter()`用于指示只有当值匹配谓词时才获取该值。将其想象为`if(!predicate(x)) { x = null; };`。代码示例：

```java
String value = null;

Optional.ofNullable(value) // 无操作
.filter(x -> x.equals("cool string")) // 永远不会执行，因为 value 是 null
.isPresent(); // false
```

```java
String value = "cool string";

Optional.ofNullable(value) // 有操作
.filter(x -> x.equals("cool string")) // 执行并通过
.isPresent(); // true
```

```java
String value = "hot string";

Optional.ofNullable(value) // 有操作
.filter(x -> x.equals("cool string")) // 执行但失败
.isPresent(); // false
```

## 第 67.6 节：用于原始数字类型的 Optional 容器

`OptionalDouble`、`OptionalInt`和`OptionalLong`的工作方式类似于`Optional`，但它们专门为包装原始类型设计：

```
OptionalInt presentInt = OptionalInt.of(value);
OptionalInt absentInt = OptionalInt.empty();
```

由于数值类型有值，因此没有对`null`的特殊处理。可以使用以下检查空容器：

```
presentInt.isPresent(); // 为 true
absentInt.isPresent(); // 为 false
```

同样，存在简写以辅助值管理：

```java
// 打印值，因为它在创建时已提供。
presentInt.ifPresent(System.out::println);

// 提供另一个值，因为原始 Optional 是空的。
int finalValue = absentInt.orElseGet(this::other);

// 将抛出 NoSuchElementException;
int nonexistentValue = absentInt.getAsInt();
```

### 第 67.7 节：仅当存在值时运行代码

```java
Optional<String> optionalWithValue = Optional.of("foo");
optionalWithValue.ifPresent(System.out::println); // 输出 "foo"

Optional<String> emptyOptional = Optional.empty();
emptyOptional.ifPresent(System.out::println); // 什么都不做
```

### 第 67.8 节：FlatMap

`flatMap`类似于`map`。其区别如 javadoc 所示：该方法类似于`map(Function)`，但提供的映射器的结果已经是`Optional`，如果调用，`flatMap`不会将其包装在`Optional`中。换句话说，当你链调用一个返回`Optional`的方法时，使用`flatMap`可以避免创建嵌套的`Optional`。

例如，给出以下类：

```java
public class Foo {
    Optional<Bar> getBar() {
        return Optional.of(new Bar());
    }
}
```

```java
public class Bar { }
```

如果使用`map`，你将得到一个嵌套的`Optional`；即`Optional<Optional<Bar>>`：

```
Optional<Optional<Bar>> nestedOptionalBar = Optional.of(new Foo()).map(Foo::getBar);
```

然而，如果你使用`flatMap`，你将得到一个简单的`Optional`；即`Optional<Bar>`：

```
Optional<Bar> optionalBar = Optional.of(new Foo()).flatMap(Foo::getBar);
```

## 第 68 章：对象引用

## 第 68.1 节：作为方法参数的对象引用

本主题解释了对象引用的概念；针对 Java 编程初学者。你应该已经熟悉一些术语和含义：类定义、主方法、对象实例以及在“对象”上调用方法、向方法传递参数。

```java
public class Person {
    private String name;

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}
```

```java
public static void main(String [] arguments) {
    Person person = new Person();
    person.setName("Bob");

    int i = 5;
    setPersonName(person, i);

    System.out.println(person.getName() + " " + i);
}
```

```java
private static void setPersonName(Person person, int num) {
    person.setName("Linda");
    num = 99;
}
```

为了在 Java 编程方面完全精练，你应该能够脱口向他人解释这些。这些概念是理解 Java 如何运作的基础。

正如你所见，我们有一个`main`方法实例化了一个`person`对象，并调用方法将该对象的`name`字段设置为"Bob"。然后它调用了另一个方法，并将`person`作为两个参数之一传递；另一个是参数`num`，它是一个整数变量，设置为 5。

该方法对传递的对象调用`setName`方法将其设置为"Linda"，并将传递的整数变量设置为 99，然后返回。

输出结果为：

```
Linda 5
```

那么，为什么对`person`的修改在`main`方法中生效了，但对整数的修改却没有生效？

当进行调用时，`main`方法为`setName`方法传递了一个对象引用；`setAnotherName`对该对象进行的任何更改都是对象的一部分，因此当方法返回时，这些更改仍然是该对象的一部分。

另一种表达方式是：`person`指向一个对象（存储在堆上），方法对该对象做的任何更改都是在“该对象上”进行的，并且不受执行更改的方法仍处于激活或已返回的影响。当方法返回时，对对象所做的任何更改仍然存储在该对象上。

这与传递的整数形成对比。由于这是一个基本类型`int`（而不是`Integer`实例），它是“按值传递”的，这意味着提供给方法的是它的值，而不是指向原始整数的指针。方法可以为了自己的目的更改它，但这不会影响调用方法时所使用的变量。

在 Java 中，所有基本类型都是按值传递的。对象按引用传递的，这意味着对于任何接收对象的方法，对象的指针都会作为参数传递。

这意味着另一个不那么显而易见的点：被调用的方法无法创建一个新对象并将其作为参数之一返回。方法返回由方法调用直接或间接创建对象的唯一方法是将其作为方法的返回值。让我们先看看这种做法行不通，然后再看看它是如何生效的。

让我们在这个小示例中再添加另一个方法：

```java
private static void getAnotherObjectNot(Person person) {
    person = new Person();
    person.setName("George");
}
```

然后，在`main`方法中，在`setAnotherName`调用下方，放置一个对该方法的调用以及另一个`println`调用：

```
getAnotherObjectNot(person);
System.out.println(person.getName());
```

现在程序将打印出：

```
Linda
```

那个拥有 George 的对象发生了什么？嗯，传递进来的参数是一个指向 Linda 的指针；当`getAnotherObjectNot`方法创建了一个新对象时，它用指向 George 对象的引用替换了指向 Linda 对象的引用。Linda 对象仍然存在（在堆上），`main`方法仍然可以访问它，但`getAnotherObjectNot`方法之后将无法对它做任何事情，因为它没有了它的引用。代码的编写者似乎想让方法创建一个新对象并将其传回，但如果是这样的话，并没有生效。

如果这是编写者想要做的，他需要从方法返回新创建的对象，如下所示：

```java
private static Person getAnotherObject() {
    Person person = new Person();
    person.setName("Mary");
    return person;
}
```

然后这样调用它：

```
Person mary;
mary = getAnotherObject();
System.out.println(mary.getName());
```

现在整个程序的输出将是：

```
Linda
Linda
```

以下是完整的程序，包含了两处添加的内容：

```java
public class Person {
    private String name;

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public static void main(String [] arguments) {
        Person person = new Person();
        person.setName("Bob");

        int i = 5;
        setPersonName(person, i);
        System.out.println(person.getName() + " " + i);

        getAnotherObjectNot(person);
        System.out.println(person.getName());

        Person person;
        person = getAnotherObject();
        System.out.println(person.getName());
    }

    private static void setPersonName(Person person, int num) {
        person.setName("Linda");
        num = 99;
    }

    private static void getAnotherObjectNot(Person person) {
        person = new Person();
        person.setName("George");
    }

    private static Person getAnotherObject() {
        Person person = new Person();
        person.setName("Mary");
        return person;
    }
}
```

## 第 69 章：异常与异常处理

`Throwable`类型及其子类对象可以通过`throw`关键字向上栈传递，并使用`try...catch`语句捕获。

# 第 69.1 节：使用 try-catch 捕获异常

可以使用`try...catch`语句捕获并处理异常。（事实上`try`语句还有其他形式，如其他关于`try...finally`和`try-with-resources`的示例中所描述。）

带有一个 catch 块的 try-catch 最简单的形式如下：

```java
try {
    doSomething();
} catch (SomeException e) {
    handle(e);
}
// 下一个语句
```



简单的 `try...catch` 行为如下：

- 执行 `try` 块中的语句。
- 如果 `try` 块中的语句没有抛出异常，则控制权将传递到 `try...catch` 之后的语句。
- 如果在 `try` 块内抛出了异常：
  - 检查异常对象判断是否为 `SomeException` 的实例或其子类。如果是，则 `catch` 块将捕获该异常。
  - 将变量 `e` 绑定到异常对象。
  - 执行 `catch` 块中的代码。
  - 如果该代码抛出异常，则新抛出的异常将传播。
  - 如果没有，则控制权将传递到 `try...catch` 之后的语句。

## 第 69.2 节：try-with-resources 语句

Version ≥ Java SE 7

如 try-catch-find 语句示例所示，使用 `finally` 子句进行资源清理需要大量的“样板”代码来正确处理边缘情况。Java 7 提供了一种更简单的方法来处理这个问题，形式为 *try-with-resources*（try 资源）语句。

### 什么是资源？

Java 7 引入了 `java.lang.AutoCloseable` 接口，允许使用 *try-with-resources* 语句来管理类。实现 `AutoCloseable` 的类实例被称为**资源**。这些资源通常需要及时释放，而不是依赖垃圾回收器来释放它们。

`AutoCloseable` 接口定义了一个单一方法：`public void close() throws Exception`

`close()` 方法应该以适当的方式释放资源。规范规定，在已经释放的资源上调用该方法是安全的。此外，*强烈建议*实现 `AutoCloseable` 的类声明 `close()` 方法抛出比 `Exception` 更具体的特定异常，或者不抛出任何异常。

广泛的标准 Java 类和接口实现了 `AutoCloseable`。这些包括：

- `InputStream`、`OutputStream` 及其子类
- `Reader`、`Writer` 及其子类
- `Socket` 和 `ServerSocket` 及其子类
- `Channel` 及其子类，以及 JDBC 接口 `Connection`、`Statement` 和 `ResultSet` 及其子类。

应用程序和第三方类也可以这样做。

### 基础的 try-with-resources 语句

*try-with-resources* 的语法基于经典的 try-catch、try-finally 和 *try-catch-finally* 形式。这里是一个“基础”形式的示例；即不带 catch 或 finally 的形式。

要管理的资源被声明为 try 子句中 `(...)` 部分的变量。在上面的示例中，我们声明了一个资源变量 `stream` 并将其初始化为新创建的 `PrintStream`。

一旦资源变量初始化完成，就会执行 try 块。当执行完成后，会自动调用 `stream.close()` 以确保资源不泄露。注意，无论块以何方式完成，都会调用 `close()`。

### 增强型 try-with-resources 语句

try-with-resources 语句可以通过 catch 和 finally 块进行增强，并带有 Java 7 之前的 try-catch-finally 语法。以下代码段在我们之前的代码基础上添加了 catch，以处理 `PrintStream` 构造函数可能抛出的 `FileNotFoundException`：

```java
System.err.println("All done");
```

如果资源初始化或 try 块抛出异常，则将执行 catch 块。finally 块始终会被执行，就像传统的 try-catch-finally 语句一样。不过有几点需要注意：

- 资源变量在 catch 和 finally 块中超出了作用范围。
- 资源清理将在语句尝试匹配 catch 块之前发生。
- 如果自动资源清理抛出了异常，那么该异常可以在其中一个 catch 块中被捕获。

### 管理多个资源

上面的代码段显示了管理单个资源。实际上，try-with-resources 可以在语句中管理多个资源。例如：`try(InputStream is = new FileInputStream(file1); OutputStream os = new FileOutputStream(file2)) { // 将 'is' 拷贝到 'os' }`

它的行为正如你预期的那样。`is` 和 `os` 都会在 try 块结束时自动关闭。有几点需要注意：

- 初始化按照代码顺序发生，后定义的资源变量初始化器可以使用早期变量的值。
- 所有成功初始化的资源变量都将被清理。
- 资源变量按照它们声明的反序进行清理。

因此，在上面的示例中，由于 `is` 在 `os` 之前初始化并在 `os` 之后清理，如果在初始化 `os` 时发生异常，它也将被清理。

### try-with-resource 与经典 try-catch-finally 的等价性

Java 语言规范（JLS）通过 try-finally 语句规定了 try-with-resource 的行为。（详细信息请参考 JLS。）

对于此示例，基础的 try-with-resource 被定义为等价于以下 try-catch-finally：

```java
// 注意构造函数不是 try-catch 语句的一部分
PrintStream stream = new PrintStream("hello.txt");

// 此变量用于跟踪 try 语句中抛出的主要异常
// 如果在此块中抛出异常，
// AutoCloseable.close() 抛出的任何异常都将被抑制
Throwable primaryException = null;

// 实际的 try 块
try {
    stream.println("Hello world!");
} catch (Throwable t) {
    // 如果抛出异常，记住它以供 finally 块使用
    primaryException = t;
    throw t;
} finally {
    if (primaryException == null) {
        // 如果到目前为止没有抛出异常，close() 中抛出的异常将
        // 不被捕获，因此传递给封装代码。
        stream.close();
    } else {
        // 如果已经抛出了异常，close() 中抛出的任何异常
        // 将被抑制，因为它可能与之前的
        // 异常有关。抑制的异常可以通过
        // primaryException.getSuppressed() 获取
        try {
            stream.close();
        } catch (Throwable suppressedException) {
            primaryException.addSuppressed(suppressedException);
        }
    }
}
```

（JLS 规定变量 `t` 和 `primaryException` 对自然之外的 Java 代码是不可见的）。

增强型 try-with-resources 形式被规定为基础形式的等价。例如：

```java
try (PrintStream stream = new PrintStream("hello.txt")) {
    stream.println("Hello world!");
} catch (Throwable t) {
    // 逻辑如上
}
```

## 第 69.3 节：自定义异常

在大多数情况下，从代码设计的角度来看，使用通用 `Exception` 抛出异常更为简单，如果你只需要异常携带简单的信息。在这种情况下，通常首选 `RuntimeException`，因为它不是检查异常。对于常见的错误类型存在异常类：

- `UnsupportedOperationException` - 特定操作不支持
- `IllegalArgumentException` - 传递了无效参数值
- `IllegalStateException` - API 内部达到了不应出现的状态，或由于错误地使用 API 导致

你可以通过扩展 `RuntimeException` 创建自己的未检查异常，或通过扩展任何 `Exception` 创建检查异常。想要使用自定义异常的情况包括：

- 你正在编写供他人使用的 API 或库，并希望允许用户能够专门捕获并处理异常，从而将这些异常与其他通用异常区分开。
- 你在程序的某部分抛出了特定类型的异常，希望在程序的另一部分捕获并处理它，并且希望将这些异常与其他通用异常区分开。

```java
public class StringTooLongException extends RuntimeException {
    // 异常可以像类一样拥有方法和字段
    // 这些对于向捕获此类异常的代码传递信息很有用
    public final String value;
    public final int maximumLength;

    public StringTooLongException(String value, int maximumLength) {
        super(String.format("String exceeds maximum Length of %s: %s", maximumLength, value));
        this.value = value;
        this.maximumLength = maximumLength;
    }
}
```

可以像预定义的异常一样使用：

```java
void validate(String value) {
    if (value.length() > 30) {
        throw new StringTooLongException(value, 30);
    }
}
```

并且在捕获和处理异常的地方可以使用这些字段：

```java
void anotherMethod(String value) {
    try {
        validate(value);
    } catch (StringTooLongException e) {
        System.out.println("字符串 " + e.value + " 超过了最大长度 " + e.maximumLength);
    }
}
```

请记住，根据 Oracle Java 文档：
[...] 如果预计客户端可以从异常中恢复，请使用检查异常。如果客户端无法从异常中进行任何恢复，请将其使用未检查异常。

更多：

- 为什么 `RuntimeException` 不需要显式的异常处理？

## 第 69.4 节：处理 InterruptedException

`InterruptedException` 是一个令人困惑的怪兽——它会出现在如 `Thread.sleep()` 这样看似平常的方法中，但如果处理不当会导致代码难以维护，并在并发环境中表现糟糕。

在最基础的情况下，如果捕获了 `InterruptedException`，意味着在某个地方有人对你代码运行的线程调用了 `Thread.interrupt()`。你可能会想：“这是我的代码！我永远不会中断它！”，因此编写类似下面的代码：

```java
// 错误。不要这样做。
try {
    Thread.sleep(1000);
} catch (InterruptedException e) {
    // 忽略
}
```

但这恰恰是处理此类“不可能”事件的错误方法。如果你确定你的应用程序永远不会遇到 `InterruptedException`，那么你应该将此类事件视为对程序假设的严重违反，并尽快地退出。

处理“不可能”中断的正确方法如下：

```java
// 当没有任何会中断你的代码时
try {
    Thread.sleep(1000);
} catch (InterruptedException e) {
    Thread.currentThread().interrupt();
    throw new AssertionError(e);
}
```

这起到了两个作用：首先恢复线程的中断状态（仿佛 `InterruptedException` 根本没有被抛出一样），然后抛出一个 `AssertionError`，表明你的应用程序的基本不变性被违反了。如果你确定不会中断运行此代码的线程，那么这段代码是安全的，因为 `catch` 块永远不会被执行。

使用 Guava 的 `Uninterruptibles` 类有助于简化这种模式；调用 `Uninterruptibles.sleepInterruptibly()` 会忽略线程的中断状态，直到睡眠时间结束为止（到那时，该状态会被恢复，以便随后的调用可以进行检查并抛出它们自己的 `InterruptedException`）。如果你知道永远不会中断此代码，这安全地避免了将 `sleep` 调用封装在 `try-catch` 块中的需求。

然而，通常情况下，你无法保证线程永远不会被中断。特别是当你编写将由 `Executor` 或其他线程管理程序执行的代码时，代码对中断做出及时响应至关重要，否则你的应用程序将停滞甚至死锁。

在这些情况下，最好的做法通常是允许 `InterruptedException` 向上层层调用栈传播，依次为每个方法添加 `throws InterruptedException`。这看起来可能很笨拙，但它实际上是一个理想的特性——你的方法签名现在向调用者表明它将对中断做出及时响应。

```java
// 如果你不确定，由调用者决定如何处理中断
public void myLongRunningMethod() throws InterruptedException { ... }
```

在有限的情况下（例如，在重写不抛出检查异常的方法时），你可以重置中断状态而不抛出异常，期望后续执行的任何代码都能处理中断。这推迟了中断的处理，但并没有完全抑制它。

```java
// 抑制异常但重置了中断状态，让后续代码
// 检测到中断并妥善处理它。
try {
    Thread.sleep(1000);
} catch (InterruptedException e) {
    Thread.currentThread().interrupt();
    return ...; // 在此时你的预期已经被破坏了——尽量不要做更多工作。
}
```

## 第 69.5 节：try catch 块中的 return 语句

虽然不是实践，但在异常处理块中添加多个返回语句是可能的：

```java
public static int returnTest(int number) {
    try {
        if (number % 2 == 0) throw new Exception("Exception thrown");
        else return x;
    } catch (Exception e) {
        return 3;
    } finally {
        return 7;
    }
}
```

此方法将始终返回 7，因为与 `try/catch` 块关联的 `finally` 块在任何内容返回之前执行。现在，由于 `finally` 有 `return 7;`，这个值将取代 `try/catch` 的返回值。

如果 `catch` 块返回一个原始类型值，且该值随后在 `finally` 块中被更改，则将返回 `catch` 块的值，`finally` 块中的更改将被忽略。下面的示例将打印 "0"，而不是 "1"。

```java
public class FinallyExample {
    public static void main(String[] args) {
        int n = returnTest(4);
        System.out.println(n);
    }

    public static int returnTest(int number) {
        int lineNumber = 0;
        try {
            if (number % 2 == 0)
                throw new Exception("Exception thrown");
            else
                return lineNumber;
        } catch (Exception e) {
            return lineNumber;
        } finally {
            int returnNumber = 1;
        }
    }
}
```

## 第 69.6 节：引言

异常是程序在执行时发生的错误。考虑下面这个 Java 程序，它对两个整数相除。

```java
class Division {
    public static void main(String[] args) {
        int a, b, result;
        Scanner input = new Scanner(System.in);
        System.out.println("Input two integers");
        a = input.nextInt();
        b = input.nextInt();
```



`System.out.println("Result = " + result);`

```
    }
}
```

现在我们编译并执行上述代码，查看尝试除以零时的输出：

```
Input two integers
7 0

Exception in thread "main" java.lang.ArithmeticException: / by zero at Division.main(Division.java:14)
```

除以零是一个无效操作，会产生一个无法用整数表示的值。Java 通过抛出异常来处理这个问题。在这种情况下，异常是 `ArithmeticException` 类的实例。

注意：创建和读取堆栈轨迹的示例解释了两个数字之后的输出的含义。

异常的用处在于它所允许的流程控制。如果不使用异常，解决此问题的典型方案可能是首先检查 `b == 0`：

```java
class Division {

    public static void main(String[] args) {

        int a, b, result;

        Scanner input = new Scanner(System.in); 

        System.out.println("Input two integers");

        a = input.nextInt(); 

        b = input.nextInt();

        if (b == 0) {

            System.out.println("You cannot divide by zero."); 

            return;

        }

        result = a / b;

        System.out.println(" Result = " + result);

    }

}
```

这会在控制台打印消息 `You cannot divide by zero.` 并在用户尝试除以零时以优雅的方式退出程序。通过异常处理解决此问题的等效方法是将 `if` 流程控制替换为 `catch` 块：

```java
a = input.nextInt(); 

b = input.nextInt();

try {

    result = a / b;

} catch (ArithmeticException e) {

    System.out.println("An ArithmeticException occurred. Perhaps you tried to divide by zero."); 

    return;

}
```

`catch` 块的执行方式如下：

1. 开始执行 `try` 块中的代码。
2. 如果 `try` 块中发生异常，立即中止并检查此异常是否被 `catch` 块捕获。
3. 如果异常被捕获，将其赋值给变量 `e` 并执行 `catch` 块。
4. 如果 `try` 或 `catch` 块完成（即执行期间没有发生未捕获的异常），则继续执行 `try-catch` 块下面的代码。

在行为未定义或意外的情况下，将异常处理作为应用程序正常流程控制的一部分被认为是良好的实践。例如，方法失败时返回 `null` 的更好的做法是抛出异常，以便使用方法的应用程序可以通过异常处理来定义自己的流程控制。在某种意义上，这解决了必须返回特定类型的问题，因为可以抛出多种类型的异常来指示发生的特定问题。

关于如何以及使用异常的更多建议，请参考 Java 陷阱 - `Exception` 使用。

# 第 69.7 节：Java 异常层次结构 - 未检查异常和检查异常

所有 Java 异常都是异常层次结构中类的实例。这可以表示为：

- `java.lang.Throwable` - 这是所有异常类的基类。它的方法和构造函数实现了所有异常共同的功能。
- `java.lang.Exception` - 这是所有正常异常的父类。
    - 各种标准和自定义异常类。
    - `java.lang.RuntimeException` - 这是所有未检查异常的父类。
        - 各种标准和运行时异常类。
- `java.lang.Error` - 这是所有致命错误异常的父类。

注意：

1. 检查异常和未检查异常之间的区别下文所述。
2. `Throwable`、`Exception` 和 `RuntimeException` 类应被视为抽象类；参见陷阱 - 抛出 `Throwable`、`Exception`、`Error` 或 `RuntimeException`。
3. `Error` 异常是由 JVM 在某些情况下抛出的，对于应用程序来说，尝试恢复是不安全或不明智的。
4. 声明 `Throwable` 的自定义子类是不明智的。Java 工具和库可能假设 `Error` 和 `Exception` 是 `Throwable` 的直接子类，如果该假设不正确，可能会发生异常。

## 检查异常与未检查异常

某些编程语言对异常支持的批评之一是很难知道给定方法或过程可能会抛出哪些异常。鉴于未处理的异常可能会导致程序崩溃，这可能使异常成为脆弱性的来源。

Java 语言通过检查异常（checked exception）机制解决了这个问题。首先，Java 将异常分为两类：

- 检查异常（Checked exceptions）通常代表应用程序应该能够处理的预期事件。例如，`IOException` 及其子类代表 I/O 操作中可能发生的错误状况。示例包括由于文件或目录不存在导致文件打开失败、由于网络连接断开导致网络读写失败等。

- 未检查异常（Unchecked exceptions）通常代表应用程序无法处理的意外事件。这些通常是应用程序中 Bug 的结果。

（在下文中，“抛出”指的是任何显式抛出（通过 `throw` 语句）或隐式抛出（解引用失败、类型转换等）的异常。同样地，“传播”指的是在嵌套调用中抛出且在该调用未被捕获的异常。下方的示例代码将说明这一点。）

检查异常机制的第二部分是对于可能发生检查异常的方法有限制：

当在方法中抛出或传播检查异常时，它必须要么被该方法捕获，要么在方法的 `throws` 子句中列出。（`throws` 子句的意义在示例中所示。）当检查异常在初始化块中抛出或传播时，它必须被该块捕获。（无法通过字段初始化表达式传播此类异常。）

简而言之，检查异常必须被处理，要么被声明。这些限制不适用于未检查异常。这包括所有隐式抛出未检查异常的情形。

## 检查异常示例

这些代码段用于说明检查异常的限制。在每种情况下，我们都展示了一个编译错误的版本和一个修正后的版本。

```java
// 声明了一个自定义检查异常。
public class MyException extends Exception { // 省略
```

```java
// 声明了一个自定义未检查异常。
public class Exception2 extends RuntimeException { // 省略。
```

第一个示例展示了如果显式抛出的检查异常没有在方法中处理，应该如何声明。

```java
// 错误
public void methodThrowingException(boolean flag) {

    int i = 1 / 0; // 编译通过，throws ArithmeticException

    if (flag) {

        throw MyException(); // 编译错误

    } else {

        throw Exception2(); // 编译通过

    }

}
```

```java
// 修正
public void methodThrowingException(boolean flag) throws MyException { 

    int i = 1 / 0; // 编译通过，throws ArithmeticException

    if (flag) {

        throw MyException(); // 编译通过

    } else {

        throw Exception2(); // 编译通过

    }

}
```

第二个示例展示了如何处理传播的检查异常。

```java
// 错误
public void methodWithPropagatedException() {

    InputStream is = new FileInputStream("someFile.txt"); // 编译错误

    // 如果文件无法打开。IOException 是一个检查异常。

    ...

}
```

```java
// 修正（版本 A）
public void methodWithPropagatedException() throws IOException {

    InputStream is = new FileInputStream("someFile.txt");

}
```

```java
// 修正（版本 B）
public void methodWithPropagatedException() {

    try {

        InputStream is = new FileInputStream("someFile.txt"); ......

    } catch (IOException ex) {

        System.out.println("Cannot open file: " + ex.getMessage());

    }

}
```

最后一个示例展示了如何在静态字段初始化器中处理检查异常。

```java
// 错误
public class Test { private static final InputStream is = new FileInputStream("someFile.txt"); // 编译错误
```

```java
// 修正
public class Test {

    private static final InputStream is;

    static {

        InputStream tmp = null;

        try {

            tmp = new FileInputStream("someFile.txt");

        } catch (IOException ex) {

            System.out.println("Cannot open file: " + ex.getMessage());

            is = tmp;

        }

    }

}
```

注意，在这种情况下，我们必须处理 `is` 不能被赋值多次的问题，而且在发生异常的情况下也必须赋值。

## 第 69.8 节：创建和读取堆栈跟踪

当异常对象被创建时（即使用 `new` 它时），`Throwable` 构造函数会捕捉创建异常时的上下文信息。之后，这些信息可以以后堆栈跟踪（stacktrace）的形式输出，用于诊断产生异常。

## 打印堆栈跟踪

打印堆栈跟踪只需调用 `printStackTrace()` 方法。例如：

```java
try {

  int a = 0;

  int b = 0;

  int c = a / b;

} catch (ArithmeticException ex) {

  // 这将堆栈跟踪打印到标准输出

  ex.printStackTrace();

}
```

无参数的 `printStackTrace()` 方法将打印到应用程序的标准输出；即当前的 `System.out`。还有 `printStackTrace(PrintStream)` 和 `printStackTrace(PrintWriter)` 重载方法，可以打印到指定的 `Stream` 或 `Writer`。

注意：

1. 堆栈跟踪不包含异常本身的细节。你可以使用 `toString()` 方法获取这些细节；例如。
2. 应该节使用打印堆栈跟踪；参见陷阱 - 过度或不当的堆栈跟踪。通常使用日志框架更好，并将异常对象传递给日志记录。

## 理解堆栈跟踪

考虑以下由两个文件中的两个类组成的简单程序。（我们显示了文件名并为了说明添加行号。）

```java
File : "Main.java"
1 public class Main {
2 public static void main(String[] args) {
3 new Test().foo();
4 }
5
```

```java
File : "Test.java"
1 class Test {
2 public void foo() {
3 bar();
4 }
5
6 public int bar() {
7 int a = 1;
8 int b = 0;
9 return a / b;
10 }
```

当这些文件编译并运行时，我们将得到以下输出。

```
Exception in thread "main" java.lang.ArithmeticException: / by zero at
Test.bar(Test.java:9)
at Test.foo(Test.java:3)
at Main.main(Main.java:3)
```

让我们逐行阅读这些内容，弄明白它告诉了我们什么。第一行告诉我们 `"main"` 线程由于一个未捕获的异常而终止。异常的全名是 `java.lang.ArithmeticException`，异常消息是 `"/ by zero"`。如果我们查询此异常的 JavaDoc，它说：当发生算术异常时抛出。例如，整数“除以零”会抛出此类的实例。事实上，消息 `"/ by zero"` 强烈暗示异常的原因是某些代码尝试除以零。但是什么呢？剩下的 3 行是堆栈跟踪。每行代表堆栈上的一个方法（或构造函数）调用，每行都告诉我们三件事：

- 正在执行的类名和方法名
- 正在执行语句的源代码行号

当在构造函数、实例字段初始化器或实例初始化块中执行代码时，方法名将为 `<init>`。当在静态字段初始化器或静态初始化块中执行代码时，方法名将为 `<clinit>`。

（在某些 Java 版本中，堆栈跟踪格式化代码会检测并省略重复的堆栈帧序列，这可能发生在应用程序由于递归过深而失败时。）

# 异常链和嵌套堆栈跟踪（版本 ≥ Java SE 1.4）

异常链发生发生在某段代码捕获到一个异常，然后创建并抛出一个新异常，并将第一个异常作为原因（cause）传递时。以下是一个示例：

```java
File: Test.java
1 public class Test {
2 int foo() {
3 return 0/0;
4 }
5
6 public Test() {
7 try {
8 foo();
9 } catch (ArithmeticException ex) {
10 throw new RuntimeException("A bad thing happened", ex);
11
12 }
13
14 public static void main(String[] args) {
15 new Test();
16 }
17 }
```

当上述类被编译并运行时，我们得到如下堆栈跟踪：

```
Exception in thread "main" java.lang.RuntimeException: A bad thing happened at Test.<init>(Test.java:10)
at Test.main(Test.java:15)

Caused by: java.lang.ArithmeticException / by zero
at Test.foo(Test.java:3)
at Test.<init>(Test.java:8)
... 1 more
```

堆栈跟踪以导致（在本例情况下）应用程序崩溃的异常的类名、方法和调用堆栈开始。紧随其后的是一行 `"Caused by:"`，它报告了原因异常。它会报告类名和消息，然后是原因异常的帧（frames）。跟踪以 `"... N more"` 结束，这表示最后 N 个帧与上一个异常的相同。

只有当主异常的原因不为空时，输出中才会包含 `"Caused by:"`。异常可以无限地链下去，在这种情况下，堆栈跟踪可以有多个 `"Caused by:"` 跟踪。

注意：原因机制在 Java 1.4.0 中才在 `Throwable` API 中暴露。在此之前，异常链需要由应用程序使用自定义异常字段来表示原因，并使用自定义的 `printStackTrace` 方法来实现。

# 将堆栈跟踪捕获为字符串

有时，应用程序需要将堆栈跟踪捕获为 Java 字符串，以便用于其他用途。实现此点的通用方法是创建一个写入到内存缓冲器的临时 `OutputStream` 或 `Writer`，并将其传递给 `printStackTrace(...)`。

Apache Commons 和 Guava 库提供了将堆栈跟踪捕获为字符串的实用方法：

- `org.apache.commons.lang.ExceptionUtils.getStackTrace(Throwable)`
- `com.google.common.base.Throwables.getStackTraceAsString(Throwable)`

如果你无法在代码库中使用第三方库，以下方法可以完成任务：

- 返回堆栈跟踪的字符串表示。
- `@param throwable` 可抛出的异常
- `@return` 字符串。

```java
public static String stackTraceToString(Throwable throwable) {

    StringWriter stringWriter = new StringWriter();

    throwable.printTrace(new PrintWriter(stringWriter));
```



`return stringWriter.toString();`

`}`

注意，如果你的意图是分析堆栈跟踪，那么使用`getStackTrace()`和`getCause()`比尝试解析堆栈跟踪要简单。

# 节 69.9：抛出异常

以下示例显示了抛出异常的基础：

```java
public void checkNumber(int number) throws IllegalArgumentArgumentException {
    if (number < 0) {
        throw new IllegalArgumentArgumentException("Number must be positive: " + number);
    }
}
```

异常在第 3 行抛出。该语句可以拆分为几个部分：`new IllegalArgumentArgumentException(...)`创建了一个`IllegalArgumentException`类的实例，并带有描述所报告错误异常的消息。`throw ...`然后抛出该异常对象。

当异常抛出时，它会导致包含它的语句异常终止，直到异常被处理。这在其他示例中描述。如所示，在单个语句中创建并抛出异常对象是良好的做法。在异常中包含有意义的错误消息以帮助程序员理解问题原因也是良好的做法。然而，这不同于你应该展示给最终用户的消息。（目前，Java 没有直接支持异常消息的国际化。）

还有几点说明：

我们把`checkNumber`声明为`throws IllegalArgumentException`。这并不是严格必要的，因为`IllegalArgumentException`是一个未检查异常（unchecked exception）；参见《Java 异常层次结构 - 未检查异常和检查异常》。然而，这样做是良好的做法，并且在方法的 javadoc 注释中包含抛出的异常。

`throw`语句之后的代码是不可达的。如果我们写成：`throw new IllegalArgumentException("it is bad"); return;`编译器将为`return`语句报告编译错误。

## 异常链

许多标准异常都有一个构造函数，除了常规的消息参数外，还有一个第二个 cause 参数。原因（cause）允许你对异常进行链。这是一个示例。

首先，我们定义一个未检查异常，我们的应用程序在遇到不可恢复的错误时将抛出该异常。注意，我们包含了一个接受原因参数的构造函数。

```java
public class AppErrorException extends RuntimeException { 

    public AppErrorException() {

    }
```

```java
public AppErrorException(String message) { 

    super(message);

}
```

```java
public AppErrorException(String message, Throwable cause) { 

    super(message, cause);

}
```

接下来，这里有一个代码展示了异常链。

```java
public String readFirst(String file) throws AppErrorException { 

    try (BufferedReader r = new BufferedReader(new FileReader(file))) { 

        String line = r.readLine();

        if (line != null) {

            return line;

        } else {

            throw new AppErrorException("File is empty");

        }

    } catch (IOException ex) { 

        throw new AppErrorException("Cannot read file", ex); 

    }

}
```

Java 7 引入了 try-with-resources 结构以及与之相关的异常抑制（exception suppression）概念。考虑以下代码段：

```java
try (Writer w = new BufferedWriter(new FileWriter(someFilename))) { // 执行
    stuff
    int temp = 0 / 0; // 抛出 ArithmeticException
}
```

当抛出异常时，try 块会调用`w`的`close()`方法，这将刷新任何缓冲区输出并关闭`BufferedWriter`。但如果在刷新输出时恰好抛出了`IOException`会发生什么呢？

结果是，在清理资源时抛出的任何异常都会被抑制。该异常会被捕获，并添加到主异常的抑制异常列表（suppressed exception list）中。接下来，try-with-resources 将继续清理其他资源。最后，主异常会被重新抛出。

如果在资源初始化期间抛出异常，或者 try 块正常完成，也会发生类似的模式。第一个抛出的异常将成为主异常，后续在清理过程中产生的异常将受到抑制。

可以通过调用`getSuppressedExceptions`方法从主异常对象中获取被抑制的异常。

## 第 69.11 节：try-finally 和 try-catch-finally 语句

try...catch...finally 语句将异常处理与清理代码结合在一起。`finally`块包含在所有情况下都会执行的代码。这使得它们适用于资源管理以及其他类型的清理工作。

### Try-finally

这是一个较基础的（try...finally）形式的示例：

```java
try {

  doSomething();

} finally {

  cleanUp();

}
```

try...finally 的行为如下：

- 执行 try 块中的代码。
- 如果 try 块中没有抛出异常：
    - 执行 finally 块中的代码。
    - 如果 finally 块抛出了异常，则该异常将传播。
    - 否则，控制权将传递到 try...finally 之后的下一个语句。
- 如果 try 块中抛出了异常：
    - 执行 finally 块中的代码。
    - 如果 finally 块抛出了异常，则该异常将传播。
    - 否则，原始异常将继续传播。

finally 块中的代码将始终被执行。（唯一的异常情况是调用了`System.exit(int)`或 JVM 发生崩溃。）因此，finally 块是始终需要执行的正确位置；例如关闭文件和其他资源或释放锁。

### try-catch-finally

我们的第二个示例展示了`catch`和`finally`如何结合使用。它说明了清理资源并不是一步简单的。

```java
// 此代码段将文件的第一行写入字符串
String result = null;

Reader reader = null;

try {

  reader = new BufferedReader(new FileReader(fileName));

  result = reader.readLine();

} catch (IOException ex) {

  Logger.getLogger.warn("Unexpected的 错误", ex); // 记录异常

} finally {

  if (reader != null) {

    try {

      reader.close();

    } catch (IOException ex) {

      // 忽略/丢弃此异常

    }

  }

}
```

此示例中 try...catch...finally 的完整（假设性）行为过于复杂，无法在此处描述。简单的版本是：finally 块中的代码将始终被执行。

从资源管理的角度来看：

- 我们在 try 块之前声明“资源”（即资源变量），以便它在 finally 块中具有作用域。
- 通过将`new FileReader(...)`放在其中，catch 能够处理在打开文件时抛出的`IOError`异常。
- 我们在 finally 块中需要`reader.close()`，因为某些异常路径在 try 块或 catch 块中都是无法拦截的。
- 然而，由于在`reader`初始化之前可能抛出了异常，我们还需要一个显式的空值测试。
- 最后，`reader.close()`调用可能会（假设性）抛出异常。我们并不关心那个异常。

（注：此处原文处似乎原文重复重复重复，，已按逻辑逻辑翻译）

最后，`reader.close()`调用可能会（假设性）抛出异常。我们并不关心那个异常。

finally 块中的代码将始终被执行。

# 第 71 章：使用 static keyword

## 第 71.1 节：静态上下文中引用非静态成员

静态变量和方法不属于实例。无论你为某个类创建了多少个对象，该变量始终只有一份拷贝。

例如，你可能想要一个不可变的常量列表，在静态方法中将其保留并初始化一次将是一个好主意。如果你经常创建某个特定类的多个实例，这将为你带来显著的性能提升。

此外，你还可以在类中使用静态代码块（static block）。你可以用它为静态变量分配默认值。它们只在类加载到内存时执行一次。

正如名称所示，实例变量依赖于特定对象的实例，它们将随对象的生存而存在。你可以在对象的特定生命周期内对其进行操作。

静态方法内部使用的类所有字段和方法必须是静态的或局部的。如果你尝试使用实例（非静态）变量或方法，你的代码将无法编译。

```java
public class Week {

    static int daysOfTheWeek = 7; // 静态变量

    int dayOfTheWeek; // 实例变量

}
```

```java
public static int getDaysLeftInWeek() {

    return Week.daysOfTheWeek - dayOfTheWeek; // 这会导致错误

}
```

```java
public static int getDaysLeftInWeek() {

    return Week.daysOfTheWeek - dayOfTheWeek; // 这是有效的

}
```

```java
public static int getDaysLeftInTheWeek(int today) {

    return Week.daysOfTheWeek - today; // 这是有效的

}
```

## 第 71.2 节：使用 static 声明常量

由于 static 关键字用于在不实例化类的情况下访问字段和方法，因此它可以被用于声明供其他类使用的常量。这些变量在类的每次实例化过程中都将保持不变。按照惯例，静态变量始终全大写，并使用下划线而不是驼峰命名法。

### static final E_VARIABLE_NAME

由于常量不能更改，因此 static 也可以与 final 修饰符一起使用。例如，定义数学常量圆周率：

```java
public class MathUtilities {

    static final double PI = 3.1415926535

}
```

它可以在任何类中作为常量使用，例如：

```java
public class MathCalculations {

    // 计算圆的周长
    public double calculateCircumference(double radius) { 

        return (2 * radius * MathUtilities.PI);

    }

}
```

# 第 72 章：Properties 类

properties 对象包含键值对，且两者都为字符串。`java.util.Properties`类是`Hashtable`的子类。它可以根据属性键来获取属性值。`Properties`类提供了从属性文件中获取数据以及将数据存储到属性文件的方法。此外，它还可以用于获取系统属性。

### properties 文件的优势

如果从属性文件中更改信息，则不需要重新编译：如果从...更改任何信息

## 第 72.1 节：加载属性

要加载与应用程序绑定的 properties 文件：

```java
public class Defaults {

    public static Properties loadDefaults() {

        try (InputStream bundledResource = Defaults.class.getResourceAsStream("/defaults.properties")) {

            Properties defaults = new Properties();

            defaults.load(bundledResource);

            return defaults;

        } catch (IOException e) {

            // 因为资源是与应用程序绑定的，我们永远不应该到达这里。
            throw new RuntimeException("properties not properly packaged with application", e);

        }

    }

}
```

## 第 72.2 节：将属性保存为 XML

### 将属性存储在 XML 文件中

将属性存储为 XML 文件的方式与将其存储为 .properties 文件的方式非常相似。只是不再使用`store()`，而是使用`storeToXML()`。

```java
public void saveProperties(String location) throws IOException {

    // 创建 properties 的新实例
    Properties prop = new Properties();

    // 设置属性值
    prop.setProperty("name", "Steve");

    prop.setProperty("color", "green");

    prop.setProperty("age", "23");

    // 检查文件是否存在
    File file = new File(location);

    if (!file.exists()) {

        file.createNewFile();

    }

    // 保存属性
    prop.storeToXML(new FileOutputStream(file), "testing with xml");

}
```

当你打开该文件时，它看起来像这样：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">
<properties>
  <!--testing with xml -->
  <entry key="age">23</entry>
  <entry key="color">green</entry>
  <entry key="name">Steve</entry>
</properties>
```

### 从 XML 加载属性

现在要加载此文件作为属性，你需要调用`loadFromXML`而不是在普通 .properties 文件时使用的`load`。

```java
public static void loadProperties(String location) throws IOException {

    // 创建新的 properties 实例以加载文件
    Properties prop = new Properties();

    // 确保文件存在
    File file = new File(location);

    if (file.exists()) {

        // 加载文件
        prop.loadFromXML(new FileInputStream(file));

        // 打印属性
        for (String name : prop.getPropertyNames()) {

            System.out.println(name + "=" + prop.getProperty(name));

        }

    } else {

        System.err.println("Error: No file found at " + location);

    }

}
```



当你运行此代码时，将在控制台中得到以下内容：

```
age=23
color=green
name=Steve
```

## 第 72.3 节：属性文件的注意事项：末尾空格

仔细观察这些看似完全相同的属性文件：

| # 示例 1 | # 示例 2 |
|---|---|
| 2 | 2 |
| 3 lastName=Smith | lastName=Smith |
| 4 | 4 |

但它们并不相同：

| # 示例 1 | # 示例 2 |
|---|---|
| 2 | 2 |
| 3 lastName=Smith | lastName=Smith |
| 4 | 4 |

（来自 Notepad++ 的截图）

由于保留了末尾空格，在第一情况下`lastName`的值将是`"Smith"`，而在第二情况下是`"Smith "`。

```java
private void trimAndLoad(Properties p) {
    for (Entry<Object, Object> entry : p.entrySet()) {
        if (entry.getValue() instanceof String) {
            put(entry.getKey(), trimTrailing((String) entry.getValue()));
        } else {
            put(entry.getKey(), entry.getValue());
        }
    }
}
```

```java
/**
 * 移除字符串末尾的空格或制表符。
 *
 * @param str
 * @return
 */
```

```java
public static String trimTrailing(String str) {
    if (str != null) {
        // 从尾部读取 str 直字符不再是空白字符
        for (int i = str.length() - 1; i >= 0; i--) {
            if ((str.charAt(i) != ' ') && (str.charAt(i) != '\t')) {
                return str.substring(0, i + 1);
            }
        }
    }
    return str;
}
```

## 第 73 章：Lambda 表达式

Lambda 表达式提供了一种清晰且简洁的方式，通过一个表达式来实现单方法接口。它们允许你减少需要创建和维护的代码量。虽然与匿名类相似，但它们本身没有类型信息。需要进行类型推断。

方法引用（Method references）使用现有方法而非表达式来实现函数式接口。它们也属于 Lambda 家族。

# 第 73.1 节：Java Lambda 简介

## 函数式接口

Lambda 只能在函数式接口上操作，函数式接口只有一个抽象方法的接口。函数式接口可以有任意数量的默认或静态方法。（由于这个原因，它们有时被称为单抽象方法接口，或 SAM 接口）。

```java
interface Foo1 {
    void bar();
}
```

```java
interface Foo2 {
    int bar(boolean baz);
}
```

```java
interface Foo3 {
    String bar(Object baz, int mink);
}
```

```java
interface Foo4 {
    default String baz() { // 默认方法，不计入
        return "baz";
    }
    void quux();
}
```

在声明函数式接口时，可以添加`@FunctionalInterface`注解。这没有特殊效果，但如果将此注解应用于非函数式的接口，将生成编译错误，从而起到提醒该接口不应更改的作用。

```java
@FunctionalInterface interface Foo5 {
    void bar();
}
```

```java
@FunctionalInterface
interface BlankFoo1 extends Foo3 // 继承自 Foo3 的抽象方法
```

```java
@FunctionalInterface
interface Foo6 {
    void bar();
    boolean equals(Object obj); // 重写了 Object 的方法之一，不计入
}
```

相反，这不是一个函数式接口，因为它有多个抽象方法：

```java
interface BadFoo {
    void bar();
    void quux(); // <- 第二个方法阻止了 lambda：哪一个应该被视为 lambda
}
```

这也不是一个函数式接口，因为它没有任何方法；

```java
interface BlankFoo2 {
}
```

请注意以下内容。假设你有：

```java
interface Parent { public int parentMethod(); }
```

和

```java
interface Child extends Parent { public int ChildMethod(); };
```

那么`Child`不能作为函数式接口，因为它有两个指定的方法。

Java 8 在`java.util.function`包中还提供了许多泛型模板函数式接口。例如，内置接口`Predicate<T>`封装了一个方法，该方法输入一个`T`类型的值并返回布尔值。

# Lambda 表达式

Lambda 表达式的基本结构是：

| Lambda 操作符 | 函数式接口 fi | 方法签名 | 方法实现 |
| :--- | :--- | :--- | :--- |
| | `() -> System.out.println("Hello")` | | |

`fi`然后将持有一个类的单例实例，类似于匿名类，该类实现了`FunctionalInterface`，并且其中一个方法的定义为`{ System.out.println("Hello"); }`。换句话说，上述大部分等同于：

```java
FunctionalInterface fi = new FunctionalInterface() {
    @Override
    public void oneMethod() {
        System.out.println("Hello");
    }
}
```

Lambda 仅“大部分等同于”匿名类，因为在 lambda 中，像`super`或`toString()`这样的表达式含义是指赋值发生所在的类，而不是新创建的对象。

在使用 lambda 时无法指定方法的名称——但你可能不需要指定，因为函数式接口只能有一个抽象方法，所以 java 会重写那一个方法。

在 lambda 类型不确定的情况下（例如重载方法），你可以为 lambda 添加一个类来告诉编译器它的类型应该是什么，如下所示：

```java
Object fooHolder = (Foo1) () -> System.out.println("Hello");
System.out.println(fooHolder instanceof Foo1); // 返回 true
```

如果函数式接口的唯一方法接收参数，这些参数的局部形式名称应该出现在 lambda 的括号中。不需要声明参数或返回值的类型，因为它们是从接口中获取的（尽管如果你想这样做，声明参数类型也不是错误）。因此，这两个示例是等同的：

```java
Foo2 longFoo = new Foo2() {
    @Override
    public int bar(boolean baz) {
        return baz ? 1 : 0;
    }
};

Foo2 shortFoo = (x) -> { return x ? 1 : 0 };
```

如果函数只有一个参数，可以省略参数周围的括号：

```java
Foo2 shortFoo = (x) -> { return x ? 1 : 0 };
```

（注：此处原文存在大量重复行，已根据逻辑流进行清理处理）

# 第 73.2 节：使用 Lambda 表达式排序集合

# 列表排序

在 Java 8 之前，对列表排序时需要用匿名（或命名）类实现`java.util.Comparator`接口：

```java
Version ≥ Java SE 1.2

List<Person> people = ...

Collections.sort(
    people,
    new Comparator<Person>() {
        public int compare(Person p1, Person p2){
            return p1.getFirstName().compareTo(p2.getFirstName());
        }
    }
);
```

从 Java 8 开始，可以用 Lambda 表达式替换匿名类。注意参数`p1`和`p2`的类型可以省略，因为编译器会自动推断它们：

```java
Collections.sort(
    people,
    (p1, p2) -> p1.getFirstName().compareTo(p2.getFirstName()));
```

通过使用`Comparator.comparing`和使用`::`（双冒号）符号的方法引用，可以简化示例：

```java
Collections.sort(
    people,
    Comparator.comparing(Person::getFirstName));
```

静态导入允许我们更简洁地表达此，但这是否改进了整体可读性仍有争议：

```java
import static java.util.Collections.sort;
import static java.util.Comparator.comparing;
//...
sort(people, comparing(Person::getFirstName));
```

这种方式构建的`Comparator`也可以链式调用。例如，在按名字对人进行排序后，如果存在名字相同的人，可以通过`thenComparing`还可以按姓进行比较：

```java
sort(people, comparing(Person::getFirstName).thenComparing(Person::getLastName));
```

- 注意，`Collections.sort(...)`仅适用于`List`的子类型集合。`Set`和`Collection` API 并不意味着元素的任何排序。

## 排序映射

你可以以类似的方式通过值对`HashMap`的元素进行排序。（注意，必须使用`LinkedHashMap`作为目标。普通`HashMap`中的键是无序的）。

```java
Map<String, Integer> map = new HashMap(); // ... 或任何其他 Map 类 //填充 map 数据
map = map.entrySet();
```

```java
.stream()
.sorted(Map.Entry.<String
(k, v) -> k, LinkedHashMap::new);
```

## 第 73.3 节：方法引用

方法引用允许将符合兼容函数接口的预定义静态或实例方法作为参数传递，而不是匿名 lambda 表达式。
假设我们有一个模型：

```java
class Person {
    private final String name;
    private final String surname;

    public Person(String name, String surname) {
        this.name = name;
        this.surname = surname;
    }

    public String getName() { return name; }
    public String getSurname() { return surname; }
}
```

`List<Person> people = somePeople();`

实例方法引用（指向任意实例）

```java
people.stream().map(Person::getName);
```

等效的 lambda 表达式：

```java
people.stream().map(person -> person.getName())
```

在此示例中，传递了对`Person`实例方法`getName()`的引用。

实例方法引用（指向特定实例）

```java
people.forEach(System.out::println);
```

由于`System.out`是`PrintStream`的实例，因此传递对该特定实例的方法引用作为参数。

等效的 lambda 表达式：

```java
people.forEach(person -> System.out.println(person));
```

## 静态方法引用

在转换流时，我们也可以对静态方法应用引用：

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6);
numbers.stream().map(String::valueOf)
```

此示例传递了对`String`类型静态方法`valueOf()`的引用。因此，集合中的实例对象被作为参数传递

等效的 lambda 表达式：

```java
numbers.stream().map(num -> String.valueOf(num));
```

## 构造函数引用

```java
List<String> strings = Arrays.asList("1", "2", "3");
strings.stream().map(Integer::new)
```

阅读“Collect Elements of a Stream into a Collection”以查看如何将元素收集到集合中。

这里使用了`Integer`类型的单个`String`构造函数，根据提供的参数字符串构造整数。在这种情况下，只要字符串代表数字，流就会被映射为`Integer`。等效的 lambda 表达式：

```java
strings().map(s -> new Integer(s));
```

## 快速查表

## 方法引用格式

| 静态方法 | 等效 lambda 表达式 | 类型 |
| :--- | :--- | :--- |
| `TypeName::method(args)` | `(args) -> TypeName.method(args)` | 非静态方法（在实例上*） |
| `instance::method(args)` | `(args) -> instance.method(args)` | 非静态方法（无实例） |
| `TypeName::method(instance, args)` | `(instance, args) -> instance.method(args)` | |

| 构造函数 | 等效 lambda 表达式 | 类型 |
| :--- | :--- | :--- |
| `TypeName::new` | `() -> new TypeName(args)` | 数组构造函数 |
| `TypeName::new(int size)` | `(size) -> new TypeName[size]` | |

*注：上面的表根据碎片化的 OCR 文本结构重构。*

- *instance* 可以是任何求值为实例实例引用的表达式，例如`getInstance()::method`、`this::method`
- ** 如果`TypeName`是一个非静态类，则构造函数引用仅在外部类接口的作用域内有效。

## 第 73.4 节：实现多个接口

有时你可能希望一个 lambda 表达式实现多一个接口。这对于标记接口（如`java.io.Serializable`）非常有用，因为它们没有添加方法。
例如，你想创建一个带有自定义`Comparator`的`TreeSet`，然后将其序列化并发送到网络。简单的方法`TreeSet<Long> ts = new TreeSet((x, y) -> Long.compare(y, x);`是不通的，因为比较器的 lambda 没有实现`Serializable`。你可以通过使用交叉类型并显式指定此 lambda 需要是序列化的来修复此：

```java
TreeSet<Long> ts = new TreeSet<>((Comparator<Long> & Serializable) -> Long.compare(y, x));
```

如果你频繁使用交叉类型（例如，如果你在使用 Apache Spark 这样的框架，几乎所有内容都必须是序列化的），你可以创建空接口并在代码中使用它们代替：

```java
public interface SerializableComparator extends Comparator<Long>, Serializable {}
```

```java
public class CustomTreeSet {
    public CustomTreeSet(SerializableComparator comparator) {}
}
```



## 73.5 节：Lambda 监听器

### 匿名类监听器

在 Java 8 之前，通常使用匿名类来处理`JButton`事件。下面的代码显示了如何实现：

```java
JButton button = new JButton("Click");

button.addActionListener(new ActionListener() {
    @Override
    public void actionPerformed(ActionEvent e) {
        // 处理事件
    }
});
```

### Lambda 监听器

由于`ActionListener`只定义了一个方法，上面的可以使用 Lambda 表达式重写：

```java
JButton button = new JButton("Click");

button.addActionListener(e -> {
    // 处理事件
});
```

## 73.6 节：Lambda 闭包

当 lambda 表达式引用包作用域的变量时，就会创建一个 lambda 闭包。在包作用域中被 lambda 使用的变量必须是 final 或等 final 的。在 Java 8（支持 lambda 的早期版本）中，它们不需要声明为 final。例如：

```java
int n = 0;

Runnable r = () -> {
    int i = n;
    // 执行某些操作
};
```

只要`n`变量没有改变，这种方式就是合法的。如果你尝试在 lambda 内部或外部更改变量，将得到以下编译错误："从 lambda 引用的本地变量必须是 final 或等 final"。

例如：

```java
int n = 0;

Runnable r = () -> {
    int i = n;
    // 执行某些操作
};

n++; // 将产生错误
```

要在 lambda 中使用变化的变量，正常方法是声明变量的 final 副本并使用该副本。例如：

```java
int n = 0;

final int k = n;

Runnable r = () -> {
    int i = k;
    // 执行某些操作
};

n++; // 现在不会产生错误
r.run(); // 将以 i 为 0 执行，因为创建 lambda 时 k 是 0
```

显然，lambda 的主体看不到原始变量的变化。

注意 Java 不支持真正的闭包。Java lambda 的创建方式不允许它看到实例化时环境的变化。如果你想实现一个观察或更改其环境的闭包，你应该使用普通类来模拟。

```java
// 不编译 ...
public IntUnaryOperator createAccumulator() {
    int value = 0;
    IntUnaryOperator accumulate = (x) -> { value += x; return value; };
    return accumulate;
}
```

上面的示例由于之前讨论的原因无法编译。我们可以如下方式绕过编译错误：

```java
// 编译，但是不正确的 ...
public class AccumulatorGenerator {
    private int value = 0;
    public IntUnaryOperator createAccumulator() {
        IntUnaryOperator accumulate = (x) -> { value += x; return value; };
        return accumulate;
    }
}
```

问题在于这破坏了`IntUnaryOperator`接口的设计规范，该规范规定实例应该是函数式的且无状态的。如果将这样的闭包传递给接受函数对象的内置函数，可能会导致崩溃或错误行为。封装的

```java
// 正确 ...
public class Accumulator { private int value = 0; }

public int accumulate(int x) { value += x;
return value;
}
```

## 章节 73.7: Lambda 与内存利用

由于 Java lambda 是闭包，它们可以"捕获"周围词法作用域内变量的值。虽然并不是所有的 lambda 都会捕获内容——简单的 lambda（如`s -> length()`不捕获任何内容，被称为无状态的——但捕获型 lambda 需要一个临时对象来持有捕获的变量。在代码片段中，lambda`() -> j`是一个捕获型 lambda，在评估时可能会导致对象的分配：

```java
public static void main(String[] args) throws Exception { for (int i = 0; i < 1000000000; i++) {
    int j = i;
    doSomethingWithLambda(() -> j);
}
}
```

尽管片段中没有出现`new`关键字，这可能并不显而易见，但这段代码可能会创建 1,000,000,000 个独立的对象来表示`() -> j`lambda 表达式的实例。然而，应该注意到，Java 的未来版本可能会对此进行优化，使得在运行时重用 lambda 实例，或者以其他方式表示。

- 1. 例如，Java 9 在 Java 构建序列中引入了一个可选的"链接"（link）阶段，这将为执行此类全局优化提供机会。

## 章节 73.8:get自定义函数式接口使用 lambda 表达式

Lambda 用于为单方法接口提供内联实现代码，并允许我们像处理普通变量一样传递它们。我们称之为函数接口（Functional Interface）。

例如，在匿名类中编写`Runnable`并启动`Thread`看起来如下：

```java
// 旧方法
new Runnable(){
    public void run(){
        System.out.println("run logic...");
    }
}).start();

// lambdas, 从 Java 8 开始
new Thread(
    () -> System.out.println("run logic...")
).start();
```

现在，延续上述内容，假设你有一些自定义接口：

```java
interface TwoArgInterface { int operate(int a, int b); }
```

你如何使用 lambda 在代码中为此接口提供实现？与上面所示的 Runnable 示例相同。参见下面的驱动程序：

```java
public class CustomLambda {
    public static void main(String[] args) {
        TwoArgInterface plusOperation = (a, b) -> a + b;
        TwoArgInterface divideOperation = (a,b)->{
            if (b==0) throw new IllegalArgumentException("除数不能为 0");
            return a/b;
        };
        System.out.println("3 和 5 的加法结果是: " + plusOperation.operate(3, 5)); 
        System.out.println("50 除以 25 的结果是: " + divideOperation.operate(50,25));
    }
}
```

## 章节 73.9: 从传统风格到 Lambda 风格

### 传统方法

```java
interface MathOperation{
  boolean unaryOperation(int num);
}

public class LambdaTry {
  public static void main(String[] args) {
        MathOperation isEven = new MathOperation() {
          @Override
          public boolean unaryOperation(int num) {
            return num%2 == 0;
          }
        };
        System.out.println(isEven.unaryOperation(25));
        System.out.println(isEven.unaryOperation(20));
  }
}
```

### Lambda 风格

- 1. 类名和函数接口体。

```java
public class LambdaTry {
  public static void main(String[] args) {
    MathOperation isEven = (int num) -> { return num%2 == 0; };
    System.out.println(isEven.unaryOperation(25));
    System.out.println(isEven.unaryOperation(20));
  }
}
```

- 2. 可选的类型声明

```java
MathOperation isEven = (num) -> { return num%2 == 0; };
```

- 3. 如果是单个参数，参数周围的可选圆括号

```java
MathOperation isEven = num -> { return num%2 == 0; };
```

- 4. 如果函数体内只有一行，可选的大括号
- 5. 如果函数体内只有一行，可选的`return`关键字

```java
MathOperation isEven = num -> num%2 == 0;
```

## 章节 73.10: `return` 仅从 lambda 返回，而不是从外部方法

`return`方法仅从 lambda 返回，而不是从外部方法。注意这与 Scala 和 Kotlin 不同！

```java
void threeTimes(IntConsumer r) {
  for (int i = 0; i < 3; i++) {
    r.accept(i);
  }
}

void demo() {
  threeTimes(i -> {
    System.out.println(i);
    return; // 仅从 lambda 返回到 threeTimes！
  });
}
```

在尝试编写自定义语言构造时，这会导致意想不到的行为，因为内置构造（如 for 循环）的 return 行为不同：

```java
void demo2() {
  for (int i = 0; i < 3; i++) {
    // ...
  }
}
```

（注：此处原文示例`demo2`逻辑不完整，已根据上下文理解翻译）

在 Scala 和 Kotlin 中，这与 Java 不同。在 Java 中，`return`仅退出 lambda 表达式。

（此处 73.10 之后的文本原文存在部分乱码或断层，已根据逻辑进行对应处理）

```java
Person("Jeroen", 20)); personList.add(new Person("Jack", 5));
personList.add(new Person("Lisa", 19));
print(personList, p -> p.getAge() >= 18);

private static void print(List<Person> personList, Predicate<Person> checker) {
    for (Person person : personList) {
        if (checker.test(person)) {
            System.out.print(person + " matches your expression.");
        } else {
            System.out.println(person + " doesn't match your expression.");
        }
    }
}
```

`print(personList, p -> p.getAge() >= 18);`接收一个 lambda 表达式（因为 Predicate 是一个参数），你可以定义所需的表达式。`checker`的`test`方法检查此表达式是否正确：`checker.test(person)`。

你可以轻松地将其更改为，例如`print(personList, p -> p.getName().startsWith("J"));`。这将检查人的名字是否以 "J" 开头。

## 第 7 章：基本控制结构
### 第 74.1 节：switch语句

`switch`语句是 Java 的多分支语句。它用于替代长的`if-else if-else`，使其更具可读性。然而，与`if`语句不同，不能使用不等式；每个值必须具体定义。

`switch`语句有三个关键组成部分：

**case**: 这是与`switch`语句的参数进行等值评估的值。**default**: 这是一个可选的、全捕表达式，当没有任何`case`语句评估为`true`时执行。`case`语句的突然完成；通常需要 **break**: 这是为了防止意外评估后续`case`语句。

除了`continue`之外，可以使用任何导致语句突然完成的语句。这包括：

- break
- return
- throw

在下面的示例中，写了一个包含四种可能情况（包括 default）的典型`switch`语句。

```java
Scanner scan = new Scanner(System.in);
int i = scan.nextInt();

switch (i) {
    case 0:
        System.out.println("i is zero");
        break;
    case 1:
        System.out.println("i is one");
        break;
    case 2:
        System.out.println("i is two");
        break;
    default:
        System.out.println("i is less than zero or greater than two");
}
```

通过省略`break`或任何导致突然完成的语句，我们可以利用所谓的"穿透"（fallthrough）情况，它会针对多个值进行评估。这可以用于为某个值的成功创建一个范围，但仍然不如不等式灵活。

```java
Scanner scan = new Scanner(System.in);
int foo = scan.nextInt();

switch(foo) {
    case 1:
        System.out.println("I'm equal or greater than one");
    case 2:
    case 3:
        System.out.println("I'm one, two, or three");
        break;
    default:
        System.out.println("I'm not either one, two, or three");
}
```

在`foo == 1`的情况下，输出将是：
I'm equal or greater than one
I'm one, two, or three

在`foo == 3`的情况下，输出将是：
I'm one, two, or three

版本 ≥ Java SE 5
`switch`语句也可以用于枚举（enums）。

```java
enum Option { BLUE_PILL, RED_PILL }

public void takeOne(Option option) {
    switch(option) {
        case BLUE_PILL:
            System.out.println("Story ends, wake up, believe whatever you want.");
            break;
        case RED_PILL:
            System.out.println("I show you how deep the rabbit hole goes.");
    }
}
```

版本 ≥ Java SE 7
`switch`语句也可以用于字符串（Strings）

```java
public void rhymingGame(String phrase) {
    switch (phrase) {
        case "apples and pears":
            System.out.println("Stairs");
            break;
        case "lorry":
```



### 第 74.2 节：`do...while` 循环

`do...while` 循环与其他循环的区别在于，它保证至少执行一次。它也被称为“后测试循环”结构，因为条件语句是在主循环体之后执行的。

```java
int i = 0;

do {
    i++;
    System.out.println(i);
} while (i < 100); // 条件在循环内容之后检查
```

在这个示例中，循环将一直运行到打印出数字 100（尽管条件是 `<` 而不是 `<=`），循环条件在循环之后评估。由于有了至少执行一次的保证，可以在循环外部声明变量并在内部初始化它们。

```java
String theWord;
Scanner scan = new Scanner(System.in); 

do {
    theWord = scan.nextLine(); 
} while (!theWord.equals("Bird"));

System.out.println(theWord);
```

在这种情况下，`theWord` 在循环外部定义并在内部初始化。

### 第 74.3 节：增强 `for` 循环 (For Each)

版本 ≥ Java 5

在 Java 5 之后，可以使用增强 `for` 循环来遍历 `Iterable` 的实现。

```java
List<String> strings = new ArrayList<>();

strings.add("This");
strings.add("is");

for (String string : strings) {
    System.out.println(string);
}
```

增强 `for` 循环可以用于 `Arrays`、`List` 或 `Set` 等类。

### 第 74.4 节：`Continue` 语句

除了 `continue` 之外，可以使用任何导致语句突然完成的语句。这包括：
- `break`
- `return`
- `throw`

在下面的示例中，写了一个典型的 `switch` 语句，包含四种可能情况（包括 `default`）。

```java
Scanner scan = new Scanner(System.in);
int i = scan.nextInt();

switch (i) {
    case 0:
        System.out.println("i is zero");
        break;
    case 1:
        System.out.println("i is one");
        break;
    case 2:
        System.out.println("i is two");
        break;
    default:
        System.out.println("i is less than zero or greater than two");
}
```

### 第 74.5 节：`If / Else If Else`

```java
if (i < 2) {
    System.out.println("i is less than 2");
} else if (i > 2) {
    System.out.println("i is more than 2");
} else {
    System.out.println("i is not less than 2 or more than 2");
}
```

### 第 74.6 节：`for` 循环

```java
for (int i = 0; i < 100; i++) {
    System.out.println(i);
}
```

```java
System.out.print(" "+j);
```

### 第 74.7 节：三元运算符

你需要检查一个条件并为变量赋值。例如：

```java
String name;

if (A > B) {
    name = "Billy";
} else {
    name = "Jimmy";
}
```

这可以很容易地写成一行：

```java
String name = A > B ? "Billy" : "Jimmy";
```

如果条件为真，变量的值被设置为条件后紧跟着第一个值；如果条件为假，则将第二个值赋给变量。

### 第 74.8 节：`Try ... Catch ... Finally`

`try { ... } catch (... ) { ... }` 控制结构用于处理异常（Exceptions）。

```java
String age_input = "abc";

try {
    int age = Integer.parseInt(age_input);
    if (age >= 18) {
        System.out.println("You can vote!");
    } else {
        System.out.println("Sorry, you can't vote yet.");
    }
} catch (NumberFormatException ex) {
    System.err.println("Invalid input. " + age_input + " is not a valid integer.");
}
```

这将输出：

```
Invalid input. 'abc' is not a valid integer.
```

可以在 `catch` 之后添加一个 `finally` 句。无论是否抛出异常，`finally` 句都会始终被执行。

```java
try { ... } catch ( ...) { ... } finally { ... }
```

```java
String age_input = "abc";

try {
    int age = Integer.parseInt(age_input);
    if (age >= 18) {
        System.out.println("You can vote!");
    } else {
        System.out.println("Sorry, you cannot vote.");
    }
} catch (FormatException ex) {
    System.err.println("Invalid input. " + age_input + " is not a valid integer.");
} finally {
    System.out.println("This code will always run, even if an exception is thrown");
}
```

这将输出：

```
Invalid input. 'abc' is not a valid integer.
This code will always be run, even if an exception is thrown
```

### 第 74.9 节：`Break`

`break` 语句结束循环（如 `for`、`while`）或 `switch` 语句的评估。

```java
Loop:
while(true) {
    if(someCondition == 5) { 
        break;
    }
}
```

示例中的循环将无限运行。但在执行的某一点当 `someCondition` 等于 5 时，循环结束。

如果存在多个嵌套循环，使用 `break` 只会结束最内层的循环。

### 第 74.10 节：`While` 循环

```java
int i = 0;

while (i < 100) { // 条件在循环体执行之前被检查
    System.out.println(i);
    i++;
}
```

只要括号内的条件为真，`while` 循环就会一直运行。这也被称为“预测试循环”结构，因为每次执行主循环体之前必须满足条件语句。如果循环只包含一条语句，则大括号是可选的，但某些代码风格规范倾向于无论如何都带有大括号。

### 第 74.11 节：`If / Else`

```java
int i = 2;

if (i < 2) {
    System.out.println("is less than 2");
} else {
    System.out.println("is greater than 2");
}
```

`if` 语句根据括号内条件的结果执行代码。当括号内的条件为真时，它将进入由大括号 `{ }` 定义的语句块；从左括号到右括号是 `if` 语句的作用范围。

`else` 块是可选的，可以省略。如果 `if` 语句为假，则执行它；如果 `if` 语句为真，则不执行，因为在这种情况下已经执行了对应的语句。

另请：三元 If

### 第 74.12 节：嵌套 `break / continue`

可以使用标签（label）语句直接 `break / continue` 到外层循环：

```java
outerloop :
for(...) {
    innerloop:
    for(...) {
        if(condition1)
            break outerloop;
        if(condition2)
            continue innerloop; // 等同于：continue;
    } 
}
```

Java 中没有标签的其他用处。

### 第 75 节：`BufferedWriter`

#### 第 75.1 节：向文件写入一行文本

此代码将字符串写入文件。关闭写入器是非常重要的，因此在 `finally` 块中完成。

```java
bw = new BufferedWriter(new FileWriter(file));

try {
    bw.write(str);
} finally {
    if (bw != null)
        bw.close();
}
```

另外注意，`write(String s)` 不会在写入字符串后放置换行符。要使用它，请使用 `newLine()` 方法。

版本 ≥ Java SE 7

Java 7 增加了 `java.nio.file` 包和带资源的 `try`（try-with-resources）：

```java
public void writeToFile(String str) throws IOException { 
    Path path = Paths.get("file.txt");
    try (BufferedWriter bw = Files.newBufferedWriter(path)) {
        bw.write(str);
    }
}
```

### 第 76 节：新文件文件 I/O

#### 第 76.1 节：创建路径

`Path` 类用于以编程方式表示文件系统中的路径（因此它可以指向文件，也可以指向目录，甚至可以指向不存在的文件）。可以使用辅助类 `Paths` 获取路径：

```java
Path p1 = Paths.get("/var/www/");
Path p2 = Paths.get(URI.create("file://home/testuer/File.txt"));
Path p3 = Paths.get("C:\\Users\\DentAr\\Documents\\HHGTDG.odt");
Path p4 = Paths.get("/home", "files", "diary.txt");
```

#### 第 76.2 节：操作路径

##### 合并两个路径

可以使用 `resolve()` 方法合并路径。传递的路径必须是部分路径，即不包含根元素的路径。

```java
Path p5 = Paths.get("/home/");
Path p6 = Paths.get("/arthur/files");
Path joined = p5.resolve(p6);
Path otherJoined = p5.resolve("/ford/files");
```

`joined.toString() == "/home/arthur/files"`
`otherJoined.toString() == "/ford/files"`

##### 标准化路径

路径可能包含 `..`（指向父目录）或 `.`（指向当前目录）。可以使用 `normalize()` 方法来移除它们：

```java
Path p7 = Paths.get("/home/../arthur/files");
Path p8 = Paths.get("C:\\Users\\..\\Program Files");
```

`p7.normalize().toString() == "/arthur/files"`
`p8.normalize().toString() == "C:\\Program Files"`

#### 第 76.3 节：检索信息

可以使用 `Path` 方法获取路径的信息：

- `toString()` 返回路径的字符串表示
- `getFileName()` 返回文件名
- `getNameCount()` 返回路径的元素数量
- `getName(int index)` 返回指定索引的元素
- `getParent()` 返回父目录路径
- `getRoot()` 返回根目录

```java
Path p1 = Paths.get("/var/www/");

p1.toString() // "/var/www"
p1.getFileName() // "www"
p1.getNameCount() // 2
p1.getName(0) // "var"
p1.getName(1) // "www"
p1.getParent() // "/var"
p1.getRoot() // "/"
```

#### 第 76.4 节：使用文件系统检索信息

使用 `Files` 方法与文件系统进行交互。

##### 检查是否存在

要检查文件或目录是否存在，可以使用以下方法：

`Files.exists(Path path)` 和 `Files.notExists(Path path)`

`!Files.exists(path)` 并不一定等于 `Files.notExists(path)`，因为有三种情况：

文件或目录的存在已验证（在这种情况下 `exists` 返回 `true`）；文件或目录的不存在已验证（`notExists` 返回 `true`）；由于访问限制等原因，无法验证文件或目录的存在或不存在（此时 `exists` 和 `notExists` 都返回 `false`）。

##### 检查路径是否指向文件或目录

通过 `Files.isDirectory(Path path)` 和 `Files.isRegularFile(Path path)` 完成：

```java
Path p1 = Paths.get("/var/www");
Path p2 = Paths.get("/home/testeser/File.txt");

Files.isDirectory(p1) == true
Files.isRegularFile(p1) == false
Files.isDirectory(p2) == false
Files.isRegularFile(p2) == true
```

##### 获取 MIME 类型

`Files.probeContentType(Path path)` 尝试获取文件的 MIME 类型。它返回一个 MIME 类型字符串，该字符串：

- `text/plain` 用于文件
- `text/html` 用于 HTML 页面
- `application/pdf` 用于 PDF 文件
- `image/png` 用于 PNG 图片

#### 第 76.5 节：读取文件

可以使用 `Files` 类按字节和按行读取文件。

```java
Path p2 = Paths.get("file://home/testuer/File.txt");
byte[] content = Files.readBytes(p2);
List<String> linesOfContent = Files.readLines(p2);
```

`Files.readLines()` 可接受一个字符集作为参数（默认是 `StandardCharsets.UTF_8`）：

```java
List<String> linesOfContent = Files.readAllLines(p2, StandardCharsets.ISO_8859_1);
```

### 第 76 节：写入文件

可以使用 `Files` 类按字节和按行写入文件。

```java
Path p2 = Paths.get("/home/testuser/File.txt");
List<String> lines = Arrays.asList(new String[]{"First line", "Second line", "Third line"});
Files.write(p2, lines);
Files.write(path, byte[] bytes);
```

现有文件将被覆盖，不存在的文件将被创建。

### 第 77 节：I/O



Java I/O（输入和输出）用于处理输入并产生输出。Java 使用流的概念来提高 I/O 操作的速度。`java.io`包包含了所有输入输出操作所需的类。Java 也通过 Java I/O API 完成文件的处理。

## 第 77.1 节：从 `java.io.File` 迁移到 Java 7 NIO (`java.nio.file.Path`)

这些示例假设你已经了解什么是 Java 7 的 NIO，并且习惯了使用 `java.io.File` 编写代码。使用这些示例作为快速进行更多以 NIO 为中心的迁移文档的方法。

Java 7 的 NIO 还有许多内容，例如内存映射文件或使用 `FileSystem` 打开 ZIP 或 JAR 文件。这些示例仅涵盖有限的用例。

### 指向路径

```java
// -> IO
File file = new File("io.txt");
// -> NIO
Path path = Paths.get("nio.txt");
```

相对于另一个路径的路径：

```java
// 即使在 Windows 操作系统上，也可以正斜杠代替反斜杠
// -> IO
File folder = new File("C:/");
FileInFolder = new File(folder, "io.txt");
```

```java
// -> NIO
Path directory = Paths.get("C:/");
PathInDirectory = directory.resolve("nio.txt");
```

将 `File` 转换为 `Path` 以供库使用：

```java
// -> IO
PathFromFile = new File("io.txt").toPath();
// -> NIO
File fileFromPath = Paths.get("nio.txt").toFile();
```

检查文件是否存在，如果存在则删除它：

```java
// -> IO
if (file.exists()) {
    boolean deleted = file.delete();
    if (!deleted) {
        throw new IOException("Unable to delete file");
    }
}
```

```java
// -> NIO
Files.deleteIfExists(path);
```

### 通过 `OutputStream` 写入文件

使用 NIO 根据不同的性能和内存限制、可读性和用例有多种写入和读取文件的方法，例如 `FileChannel`、`Files.write(Path path, byte[] bytes, OpenOption... options)`... 在示例中，仅涵盖了 `OutputStream`，但我们强烈建议你学习内存映射文件以及 `java.nio.file.Files` 中提供的各种静态方法。

```java
List<String> lines = Arrays.asList(
    String.valueOf(Calendar.getInstance().getTimeInMillis()), "line one",
    "line two");
```

```java
// -> IO
if (file.exists()) {
    // 注意：非原子性
    throw new IOException("File already exists");

    try (FileOutputStream outputStream = new FileOutputStream(file)) {
        for (String line : lines) {
            outputStream.write((line + System.lineSeparator()).getBytes(StandardCharsets.UTF_8));
        }
    }
}
```

```java
// -> NIO
try (OutputStream outputStream = Files.newOutputStream(path, StandardOpenOption.CREATE_NEW)) { 
    for (String line : lines) {
        outputStream.write((line + System.lineSeparator()).getBytes(StandardCharsets.UTF_8));
    }
}
```

### 遍历文件夹内的每个文件

```java
// -> IO
for (File selectedFile : folder.listFiles()) {
    // 注意：取决于目录中文件的数量。listFiles() 
    // 可能需要很长时间才能返回
    System.out.println(selectedFile.isDirectory() ? "d" : "f" + " " + selectedFile.getAbsolutePath());
}
```

```java
// -> NIO
Files.walkFileTree(directory, EnumSet.noneOf(FileVisitOption.class), 1,
new SimpleFileVisitor<Path>() {
    @Override
    public FileVisitResult preVisitDirectory(Path selectedPath, BasicFileAttributes attrs) throws IOException {
        System.out.println("d" + selectedPath.toAbsolutePath());
        return FileVisitResult.CONTINUE;
    }

    @Override
    public FileVisitResult visitFile(Path selectedPath, BasicFileAttributes attrs) throws IOException {
        System.out.println("f" + selectedPath.toAbsolutePath());
        return FileVisitResult.CONTINUE;
    }
});
```

### 递归遍历文件夹

```java
// -> IO
recurseFolder(folder);

// -> NIO
// 注意：除非显式作为参数传递，否则不会跟随符号链接
Files.walkFileTree(directory, EnumSet.noneOf(FileVisitOption.class), 1,
new SimpleFileVisitor<Path>() {
    @Override
    public FileVisitResult preVisitDirectory(Path selectedPath, BasicFileAttributes attrs) throws IOException {
        System.out.println("d" + selectedPath.toAbsolutePath());
        return FileVisitResult.CONTINUE;
    }

    @Override
    public FileVisitResult visitFile(Path selectedPath, BasicFileAttributes attrs) throws IOException {
        System.out.println("f" + selectedPath.toAbsolutePath());
        return FileVisitResult.CONTINUE;
    }
});

private static void recurseFolder(File folder) {
    // -> IO
    for (File selectedFile : folder.listFiles()) {
        if (selectedFile.isDirectory()) {
            recurseFolder(selectedFile);
        } else {
            System.out.println(selectedFile.getAbsolutePath());
        }
    }
}
```

# 第 77.7 节：流（Stream）与 Writer/Reader API

流提供了对二进制内容的最直接访问，因此任何 `InputStream` / `OutputStream` 实现始终对整数（ints）和字节（bytes）进行操作。

```java
// 从流中读取单个字节
int b = inputStream.read();
if (b >= 0) { // 负值表示流的结束，正常值范围在 0-255 之间
}
```

```java
// 将字节写入另一个流
outputStream.write(b);
```

```java
// 读取数据块
byte[] data = new byte[1024];
int nBytesRead = inputStream.read(data);
if (nBytesRead >= 0) { // 负值表示流的结束
    // 将数据块写入另一个流
    outputStream.write(data, 0, nBytesRead);
}
```

存在一些特殊情况，最著名的可能是 `PrintStream`，它添加了“方便地打印各种数据值表示的能力”。这使得我们能够将 `System.out` 既作为二进制 `InputStream`，又作为文本输出方法（如 `System.out.println()`）。

此外，某些流实现作为高级内容 Java 对象（见序列化 Serialization）或原生类型的接口工作，例如 `DataOutputStream` / `DataInputStream`。

通过 `Writer` 和 `Reader` 类，Java 还提供了用于显式字符流的 API。虽然大多数应用程序都会基于流来实现这些类，但字符流 API 没有暴露任何用于二进制内容的方法。

```java
// 此示例使用平台的默认字符集，请参见 // 以获得更好的实现。
Writer writer = new OutputStreamWriter(System.out); 
writer.write("Hello world!");
Reader reader = new InputStreamReader(System.in); 
char singleCharacter = reader.read();
```

当需要将字符编码为二进制数据时（例如使用 `InputStreamWriter` / `OutputStreamWriter` 类时），如果你不想依赖平台的默认字符集，应该指定一个字符集（charset）。如果不确定，请使用兼容 Unicode 的编码，例如 UTF-8，它在所有 Java 平台上都受支持。因此，可能应该避免使用 `FileWriter` 和 `FileReader` 的类，因为它们使用平台的默认字符集。使用字符流访问文件的更好方法是：

```java
Charset myCharset = StandardCharsets.UTF_8;
Writer writer = new OutputStreamWriter(new FileOutputStream("test.txt", myCharset));
writer.write("Ä");
writer.flush();
writer.close();
```

```java
Reader reader = new InputStreamReader(new FileInputStream("test.txt", myCharset)); 
char someUnicodeCharacter = reader.read();
reader.close();
```

最常用的 `Reader` 之一是 `BufferedReader`，它提供了一个从另一个 reader 读取文本行的方法，这是按行读取字符流最简单的方法：

```java
// 从 baseReader 读取，每次一行
BufferedReader reader = new BufferedReader(baseReader); 
String line;
while((line = reader.readLine()) != null) {
    // 记住：System.out 是一个流，而不是 writer！
    System.out.println(line);
}
```

# 第 77.8 节：使用 `Scanner` 读取文件

### 逐行读取文件

```java
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(new File("example.txt"));
        try {
            while(scanner.hasNextLine()) {
                String line = scanner.nextLine(); // 执行操作
            }
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

### 逐字读取

```java
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(new File("example.txt"));
        try {
            while(scanner.hasNext()) {
                String line = scanner.next(); // 执行操作
            }
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

你还可以通过使用 `scanner.useDelimiter()` 方法更改分隔符。

# 第 77.9 节：使用 `InputStream` 和 `OutputStream` 复制文件

我们可以使用循环直接从源复制数据到数据汇。在示例中，我们从 `InputStream` 读取数据，同时向 `OutputStream` 写入数据。一旦完成读取和写入，我们必须关闭资源。

```java
public void copy(InputStream source, OutputStream destination) throws IOException { 
    try {
        int c;
        while ((c = source.read()) != -1) {
            destination.write(c);
        }
    } finally {
        if (source != null) {
            source.close();
        }
        if (destination != null) {
            destination.close();
        }
    }
}
```

# 第 77.10 节：从二进制文件中读取

你可以在所有近期 Java 版本中使用这段代码读取二进制文件：

版本 ≥ Java SE 1.4

```java
File file = new File("path_to_file");
byte[] data = new byte[(int)file.length()];
DataInputStream stream = new DataInputStream(new FileInputStream(file));
stream.readFully(data);
stream.close();
```

如果你使用的是 Java 7 或更高版本，有更简单的方法使用 NIO API：

版本 ≥ 7

```java
Path path = Paths.get("path_to_file");
byte[] data = Files.readAllBytes(path);
```

# 第 77.11 节：使用 `Channel` 和 `Buffer` 读取文件

使用 `Channel` 和 `Buffer` 读取文件请遵循以下步骤：

1. 创建 `File` 实例。
2. 打开 `FileInputStream` 获取 `FileChannel`。
3. 分配 `ByteBuffer`。
4. 使用 channel 将数据读入 buffer。
5. 处理 buffer。



```java
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;

public class FileRead {
    public static void main(String[] args) {
        File file = new File("path_to_file");
        try (FileInputStream fis = new FileInputStream(file)) {
            FileChannel channel = fis.getChannel();
            ByteBuffer buffer = ByteBuffer.allocate((int)file.length());
            while (channel.read(buffer) != -1) {
                buffer.flip();
                while (buffer.hasRemaining()) {
                    byte b = buffer.get();
                    System.out.print((char) b);
                }
                buffer.clear();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 第 77.12 节：添加目录

要从 `File` 实例创建新目录，你需要使用两个方法之一：`mkdirs()` 或 `mkdir()`。

- `mkdir()`: 创建由此路径名指定的目录。
- `mkdirs()`: 创建由此路径名指定的目录，包括任何必要的父目录。注意，如果此操作失败，它可能已经创建了部分父目录。

## 第 77.13 节：阻塞或重定向标准输出/错误

有时，设计不当的第三方库会将不需要的诊断信息写入 `System.out` 或 `System.err` 流。解决此问题的推荐方案是寻找更好的库，或者（在开源的情况下）修复问题并向开发者提交补丁。

如果上述方案不可行，你可以考虑重定向流。

### 命令行上的重定向

在 UNIX、Linux 或 macOS 系统上，可以在 shell 中完成。例如：

```bash
$ java -jar app.jar arg1 arg2 >/dev/null 2>&1
$ java -jar app.jar arg1 arg2 >out.log 2> error.log
```

（关于重定向的更多信息，请参考您正在使用的命令行 shell 的文档。类似的建议也适用于 Windows。）或者，您可以在启动 Java 程序的封装脚本或批处理文件中实现重定向。

### 在 Java 应用内部重定向

也可以使用 `System.setOut()` 和 `System.setErr()` 在 Java 应用内部重定向流。例如，以下代码将标准输出和标准错误重定向到 2 个日志文件：

```java
System.setOut(new PrintStream(new FileOutputStream("out.log")));
```

```java
System.setErr(new PrintStream(new FileOutputStream("err.log")));
```

如果您想完全忽略输出，可以创建一个“写入”到无效文件描述符的输出流。这在功能上等同于在 UNIX 上写入 `/dev/null`。

```java
System.setOut(new PrintStream(new FileOutputStream(new FileDescriptor())));
```

```java
System.setErr(new PrintStream(new FileOutputStream(new FileDescriptor())));
```

注意：请小心使用 `setOut` 和 `setErr`：

1. 重定向将影响整个 JVM。
2. 通过这样做，您剥夺了用户从命令行重定向流的能力。

## 第 77.14 节：一次性读取整个文件

```java
File f = new File(path);
String content = new Scanner(f).useDelimiter("\Z").next();
```

`\Z` 是 EOF（文件结束）符号。当设置为分隔符时，`Scanner` 将读取内容直到到达 EOF 标志。

## 第 77.15 节：锁定

可以使用 `FileChannel` API 对文件进行锁定，该 API 可以从输入输出流和读取器中获取，示例如下：

```java
// 打开文件流
FileInputStream ios = new FileInputStream(filename);
// 获取底层通道
FileChannel channel = ios.getChannel();
```

```java
FileLock lock = channel.tryLock(0, Long.MAX_VALUE, true);

if (lock == null) {
    System.out.println("无法获取锁");
} else {
    System.out.println("成功获取锁");
}

// 你也可以使用阻塞调用，它将阻塞直到获取锁为止。
channel.lock();
// 一旦你完成了文件的所需操作，如果锁不为空，则释放锁
if (lock != null) {
    lock.release();
}

// 之后关闭文件流
```

读取器示例：

```java
RandomAccessFile randomAccessFile = new RandomAccessFile(filename, "rw");
FileChannel channel = randomAccessFile.getChannel();
// 重复上述步骤，但现在由于通道处于读写模式，你可以将 shared 设置 true 或 false
```

## 第 77.16 节：使用 `BufferedInputStream` 读取文件

使用 `BufferedInputStream` 读取文件通常比 `FileInputStream` 快，因为它维护了一个内部缓冲区来存储从输入流中读取的字节。

```java
import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.IOException;
```

```java
public class FileReadingDemo {
    public static void main(String[] args) {
        String source = "hello.txt";

        try (BufferedInputStream bis = new BufferedInputStream(new FileInputStream(source))) {
            byte data;
            while ((data = bis.read()) != -1) {
                System.out.println((char) data);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 第 77.17 节：遍历目录并打印其中的子目录

```java
public void iterate(final String dirPath) throws IOException {
    final DirectoryStream<Path> paths = Files.newDirectoryStream(Paths.get(dirPath));
    for (final Path path : paths) {
        if (Files.isDirectory(path)) {
            System.out.println(path.getFileName());
        }
    }
}
```

## 第 77.18 节：使用 `Channel` 写入文件

使用 `Channel` 和 `Buffer` 写入文件需要以下步骤：

1. 首先，需要 `FileOutputStream` 对象
2. 通过 `getChannel()` 获取 `Channel`
3. 创建 `ByteBuffer` 并将其填充数据
4. 然后通过 `write()` 方法写入 `Channel`
5. 完成后关闭 `FileOutputStream`

```java
import java.io.*;
import java.nio.*;

public class FileWrite {
    public static void main(String[] args) {
        File outputFile = new File("hello.txt");
        String text = "I love Java";
        try (FileOutputStream fos = new FileOutputStream(outputFile)) {
            FileChannel channel = fos.getChannel();
            byte[] bytes = text.getBytes();
            ByteBuffer buffer = ByteBuffer.wrap(bytes);
            channel.write(buffer);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 第 77.19 节：使用 `PrintStream` 写入文件

我们可以使用 `PrintStream` 写入文件。完成完成后需要关闭 `PrintStream`。

```java
import java.io.FileNotFoundException;
import java.io.PrintStream;
import java.time.LocalDate;

public class FileWriting {
    public static void main(String[] args) {
        String destination = "hello.txt";
        try (PrintStream ps = new PrintStream(destination)) {
            ps.println("Stackoverflow.");
            ps.printf("Today is: %s", LocalDate.now());
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

## 第 77.20 节：遍历目录并按扩展名过滤

```java
import java.io.IOException;
import java.nio.file.*;
import java.util.function.BiPredicate;

public void iterateAndFilter() throws IOException {
    Path dir = Paths.get("C:/");
    PathMatcher imageFileMatcher = FileSystems.getDefault().getPathMatcher("regex:.*jpg|png|gif|bmp");
    try (DirectoryStream<Path> stream = Files.newDirectoryStream(dir, entry -> imageFileMatcher.matches(entry.getFileName()))) {
        for (Path path : stream) {
            System.out.println(path.getFileName());
        }
    }
}
```

Java 的 `FileSystem` API 允许像操作普通文件一样读取和添加 ZIP 文件。文件在使用后应适当关闭，因此应使用 try-with-resources 块。

### 从现有文件读取

```java
Path pathToZip = Paths.get("path/to/zip");
try (FileSystem zipFiles = FileSystems.newFileSystem(pathToZip, null)) {
    Path root = zipFiles.get("/");
    // 像普通文件一样访问 zip 内容
} catch (IOException ex) {
    ex.printStackTrace();
}
```

### 创建新文件

```java
Map<String, String> env = new HashMap<>();
env.put("create", "true"); // 创建新 zip 文件必需
env.put("encoding", "UTF-8"); // 可选：默认是 UTF-8
URI uri = URL.create("jar:file/path/to/file.zip");
try (FileSystem zipFiles = FileSystems.newFileSystem(uri, env)) {
    Path newFile = zipFiles.getPath("/newFile.txt");
    // 写入文件
    Files.write(newFile, "Hello world".getBytes());
} catch (IOException ex) {
    ex.printStackTrace();
}
```

## 78 Scanner

参数详情

源码可以是 `String`、`File` 或任何类型的 `InputStream`

### 78.1 节：解决常见问题的通用模式

以下是如何正确使用 `java.util.Scanner` 类交互式地从 `System.in` 读取用户输入（有时称为 stdin，特别是在 C、C++ 和其他语言中，在 Unix 和 Linux 中也是如此）。它习用地演示了最常请求完成的任务。

```java
package com.stackoverflow.annotation.Nnull;
import java.math.BigInteger;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.*;
import java.util.regex.Pattern;
import static java.lang.String.format;

public class ScannerExample {
    private static final Set<String> EXIT_COMMANDS;
    private static final Set<String> HELP_COMMANDS;
    private static final Pattern DATE_PATTERN;
    private static final String HELP_MESSAGE;

    final SortedSet<String> ecmds = new TreeSet<String>(String.CASE_INSENSITIVE_ORDER);
    ecmds.addAll(Arrays.asList("exit"));
}
```



```java
/* 使用异常来控制执行流总是糟糕的。* 这就是为什么它被封装在一个方法中的原因，特意采用这种方式做的目的是为了不引入任何外部库 * 使得这是一个完全自给包含的示例。 
 * @param s 可能的字符串
 * @return 如果 s 代表有效的 url 则返回 true，否则返回 false /* 
 */
private static boolean isValidURL(@Nonnull final String s) {
    try {
        new URL(s);
        return true;
    } catch (final MalformedURLException e) {
        return false;
    }
}

private static void println(@Nonnull final String format, @Nonnull final Object... args) {
    System.out.println(format, args);
}

public static void main(final String[] args) {
    final Scanner sis = new Scanner(System.in);
    output(HELP_MESSAGE);
    while (sis.hasNext()) {
        if (sis.hasNextInt()) {
            final int next = sis.nextInt();
            output("你输入了一个整数 = %d", next);
        } else if (sis.hasNextLong()) {
            final long next = sis.nextLong();
            output("你输入了一个长整数 = %d", next);
        } else if (sis.hasNextDouble()) {
            final double next = sis.nextDouble();
            output("你输入了一个浮点数 = %f", next);
        } else if (sis.hasNext("\\d+")) {
            final BigInteger next = sis.nextBigInteger();
            output("你输入了一个大整数 = %s", next);
        } else if (sis.hasNextBoolean()) {
            final boolean next = sis.nextBoolean();
            output("你输入了一个布尔表示 = %s", next);
        } else if (sis.hasNext(DATE_PATTERN)) {
            final String next = sis.next(DATE_PATTERN);
            output("你输入了一个日期表示 = %s", next);
        } else { // 未分类
            final String next = sis.next();
            if (isValidURL(next)) {
                output("你输入了一个有效的 URL = %s", next);
            } else if (EXIT_COMMANDS.contains(next)) {
                output("已发布退出命令 %s，正在退出！", next);
                break;
            } else if (HELP_COMMANDS.contains(next)) {
                output(HELP_MESSAGE);
            } else {
                output("你输入了一个未分类的字符串 = %s", next);
            }
        }
    }
    /*
    这将关闭底层的可读对象（在此情况下为 System.in），并释放这些资源。
    调用 .close() 之后你将无法再次从 System.in 读取内容。如果你想对 System.in 进行其他操作，请不要关闭 Scanner。 */
    sis.close();
    System.exit(0);
}
```

## 第 78.2 节：使用自定义分隔符

你可以配合 `Scanner` 使用分隔符（正则表达式），通过 `.useDelimiter("")` 来决定如何读取输入。这与 `String.split(...)` 的工作原理类似。例如，你可以使用 `Scanner` 从字符串的逗号分隔的值列表中读取：

```java
Scanner scanner = null;
try {
    scanner = new Scanner("i,like,unicorns").useDelimiter(",");
    while(scanner.hasNext()) {
        System.out.println(scanner.next());
    }
} catch(Exception e) {
    e.printStackTrace();
} finally {
    if (scanner != null) {
        scanner.close();
    }
}
```

这允许你逐个读取输入中的每个元素。注意，你不应该使用此来解析 CSV 数据，相反，应该使用专业的 CSV 解析库，查看 Java CSV 解析器以获取其他可能性。

## 第 78.3 节：使用 Scanner 读取系统输入

```java
Scanner scanner = new Scanner(System.in); // 用于读取系统输入的 Scanner 对象
String inputTaken = new String();
while (true) {
    String input = scanner.nextLine(); // 读取一行输入
    if (input.matches("\\s+")) // 如果匹配空格/制表符，则停止读取 
        break;
    inputTaken += input + " ";
}
System.out.println(inputTaken);
```

`scanner` 对象初始化为从键盘读取输入。因此，对于下面的键盘输入，它将产生输出“Reading from keyboard”：

Reading keyboard //空格

## 第 78.4 节：使用 Scanner 读取文件输入

```java
Scanner scanner = null;
try {
    scanner = new Scanner(new File("Names.txt"));
    while (scanner.hasNext()) {
        System.out.println(scanner.nextLine());
    }
} catch (Exception e) {
    System.err.println("发生了异常!"); 
    if (scanner != null) {
        scanner.close();
    }
}
```

通过传递一个包含文本文件名的 `File` 对象来创建 `Scanner` 对象。该文本文件将由 `File` 对象打开，并在后续代码行中由 `scanner` 对象读取。`scanner.hasNext()` 将检查文本文件中是否有下一行数据。将其结合循环将允许你遍历 `Names.txt` 中的每一行数据。要检索数据本身，我们可以使用诸如 `nextLine()`、`nextInt()`、`nextBoolean()` 等方法。在上面的示例中，`scanner.nextLine()` 指的是文本文件的下一行，将其与 `scanner` 对象结合可以允许你打印文件内容。要关闭 `scanner` 对象，你可以使用 `.close()`。

使用资源（从 Java 7 开始），上述代码可以优雅地编写：

```java
try (Scanner scanner = new Scanner(new File("Names.txt"))) {
    while (scanner.hasNext()) {
        System.out.println(scanner.nextLine());
    }
} catch (Exception e) {
    System.err.println("发生了异常!");
}
```

## 第 78.5 节：作为字符串读取整个输入

你可以使用 `Scanner` 来读取整个输入。这在你想要一次性处理字符串时非常有用。

```java
Scanner scanner = new Scanner(System.in);
StringBuilder content = new StringBuilder();
while (scanner.hasNext()) {
    content.append(scanner.nextLine()).append("\n");
}
String fullInput = content.toString();
```

## 第 78.6 节：逐行读取

`Scanner` 可以通过 `nextLine()` 逐行读取。

```java
Scanner scanner = new Scanner(System.in);
while (scanner.hasNext()) {
    String line = scanner.nextLine();
}
```

## 第 79：接口

接口是一种引用类型，类似于类，可以使用 `interface` 关键字声明。接口可以包含常量、默认方法、静态方法和嵌套类型。

### 第 79.1 节：实现接口

一个 Java 类可以实现多个接口。

```java
public interface NoiseMaker {
    String noise = "Making Noise"; // 接口变量是 public static final
    String makeNoise();
}

public interface FoodEater {
    void eat(Object food); // 接口方法默认是 public
}
```

```java
public class Cat implements NoiseMaker, FoodEater {
    @Override
    public String makeNoise() {
        return "meow";
    }
    @Override
    public void eat(Object food) {
        System.out.println("meows");
    }
}
```

注意 `Cat` 类必须实现所有继承的方法。此外，注意一个类可以实现所需的多个接口（由于 JVM 限制为 65535 个）。

```java
NoiseMaker noiseMaker = new Cat(); // 有效
FoodEater foodEater = new Cat(); // 有效
Cat cat = new Cat(); // 有效

Cat invalid1 = new NoiseMaker(); // 无效
Cat invalid2 = new FoodEater(); // 无效
```

注意：

1. 接口中声明的所有变量都是 `public static final`
2. 接口中声明的所有方法都是 `public abstract`（此说法仅在 Java 7 中有效。从 Java 8 开始，允许在接口中定义不需要抽象的方法；此类方法被称为默认方法）
3. 接口不能被声明为 `final`
4. 如果多个接口声明了签名相同的方法，那么在效果上它们被视为同一个方法，且你无法区分它是从哪个接口实现的
5. 编译时，为每个接口都会生成一个相应的 `InterfaceName.class` 文件

### 第 79.2 节：声明和实现接口

使用 `interface` 关键字声明接口：

```java
public interface Animal {
    String getSound(); // 接口方法默认是 public
}
```

Override 注解

```java
@Override
public String getSound() { // 代码在此处... }
```

这强制编译器检查我们正在重写，并防止程序定义新方法或弄错方法签名。接口通过 `implements` 关键字实现。

```java
public class Cat implements Animal {
    @Override
    public String getSound() { return "meow"; }
}
```

```java
@Override
public String getSound() { return "woof";
}
```

在示例中，`Cat` 和 `Dog` 类必须定义 `getSound()` 方法，因为接口的方法本质上是抽象的（默认方法除外）。

### 第 79.3 节：扩展接口

接口可以通过 `extends` 关键字扩展另一个接口。

```java
public interface BasicResourceService {
    Resource getResource();
}
```

```java
public interface ExtendedResourceService extends BasicResourceService {
    void updateResource(Resource resource);
}
```

现在，实现 `ExtendedResourceService` 的类将需要实现 `getResource()` 和 `updateResource()`。

#### 扩展多个接口

与类不同，`extends` 关键字可以用于扩展多个接口（用逗号分隔），允许将多个接口组合成一个新的接口。

```java
public interface BasicResourceService { 
    Resource getResource();
}
```

```java
public interface AlternateResourceService { 
    Resource getAlternateResource(); 
}
```

```java
public interface ExtendedResourceService extends BasicResourceService,
AlternateResourceService { 
    Resource updateResource(Resource resource); 
}
```

在这种情况下，实现 `ExtendedResourceService` 将需要实现 `getResource()`、`getAlternateResource()` 和 `updateResource()`。

### 第 79.4 节：接口的实用性

接口在很多情况下都非常有帮助。例如，假设你有一个动物列表，你想遍历该列表并打印每种动物发出的声音。

{cat, dog, bird}

实现此目的的一种方法是使用接口。这允许在所有类上调用同一个方法。

```java
public interface Animal { 
    public String getSound(); 
}
```

任何实现 `Animal` 的类也必须包含一个 `getSound()` 方法，但它们可以有不同的实现。

```java
public class Dog implements Animal { 
    public String getSound() { return "Woof"; } 
}
```

```java
public class Cat implements Animal { 
    public String getSound() { return "Meow"; } 
}
```

```java
public class Bird implements Animal { 
    public String getSound() { return "Chirp"; } 
}
```

我们现在有了三个不同的类，每个类都有一个 `getSound()` 方法。因为这些类都实现了 `Animal` 接口（该接口声明了 `getSound()` 方法），因此任何 `Animal` 实例都可以调用它的 `getSound()`。

```java
Animal dog = new Dog(); 
Animal cat = new Cat(); 
Animal bird = new Bird();

dog.getSound(); // "Woof"
cat.getSound(); // "Meow"
bird.getSound(); // "Chirp"
```

因为这些每一个都是 `Animal`，我们甚至可以将动物放入一个列表中，遍历它们并打印出它们的声音。

```java
Animal[] animals = { new Dog(), new Cat(), new Bird() }; 
for (Animal animal : animals) {
    System.out.println(animal.getSound());
}
```

由于数组的顺序是 `Dog`、`Cat`、然后是 `Bird`，控制台将打印出 "Woof Meow Chirp"。



接口也可以作为函数的返回值。例如，如果输入是 `"dog"`，则返回 `Dog`；如果输入是 `"cat"`，则返回 `Cat`；如果输入是 `"bird"`，则返回 `Bird`，然后可以使用以下方式打印该动物的声音：

```java
public Animal getAnimalByName(String name) {
    switch(name.toLowerCase()) {
        case "dog":
            return new Dog();
        case "cat":
            return new Cat();
        case "bird":
            return new Bird();
        default:
            return null;
    }
}

public String getAnimalSoundByName(String name) {
    Animal animal = getAnimalByName(name);
    if (animal == null) {
        return null;
    } else {
        return animal.getSound();
    }
}
```

```java
String dogSound = getAnimalSoundByName("dog"); // "Woof"
String catSound = getAnimalSoundByName("cat"); // "Meow"
String birdSound = getAnimalSoundByName("bird"); // "Chirp"
String lightbulbSound = getAnimalSoundByName("lightbulb"); // null
```

接口对于扩展性也很有用，因为如果你想添加一种新类型的 `Animal`，就不需要对它们执行的操作进行任何更改。

## 第 79.5 节：默认方法

默认方法是在 Java 8 中引入的，是在接口内部指定实现的一种方式。这可以通过提供接口的局部实现并限制子类层次结构，来避免典型的“基”（`Base`）或“抽象”（`Abstract`）类。

# 观察者模式实现

例如，可以将观察者-监听器模式直接实现在接口中，为实现类提供更大的活性。

```java
interface Observer {
    void onAction(String a);
}
```

```java
interface Observable {
    public abstract List<Observer> getObservers();

    public default void addObserver(Observer o) {
        getObservers().add(o);
    }

    public default void notify(String something) {
        for (Observer l : getObservers()) {
            l.onAction(something);
        }
    }
}
```

现在，任何类都可以通过实现 `Observable` 接口来变成“可观测的”，同时自由地处于不同的类层次结构中。

```java
abstract class Worker {
    public abstract void work();
}
```

```java
public class MyWorker extends Worker implements Observable {
    private List<Observer> myObservers = new ArrayList<>();
    @Override
    public List<Observer> getObservers() {
        return myObservers;
    }

    @Override
    public void work() {
        // implementation
    }
}

public static void main(String[] args) {
    MyWorker worker = new MyWorker();
    // ...
}
```

# 菱形问题

在这种情况下，实现 `ExtendedResourceService` 将实现 `getResource()`、`getAlternateResource()` 和 `updateResource()`。

```java
interface InterfaceA {
    default String getName() {
        return "A";
    }
}

interface InterfaceB {
    default String getName() {
        return "B";
    }
}

public class ImpClass implements InterfaceA, InterfaceB {
    @Override
    public String getName() {
        return InterfaceA.super.getName();
    }
}
```

仍然存在方法相同但参数不同的问题，这将无法编译。默认方法在这种情况下非常有用。

## 第 79.6 节：接口中的修饰符

Oracle 指南：当修饰符是隐式的，不应写出来（参阅 Oracle 代码标准）。这种风格指南特别适用于接口。考虑以下代码：

```java
interface I {
    static final int VARIABLE = 0;
    void method();
    static void staticMethod() { ... }
    default void defaultMethod() { ... }
}
```

### 变量

所有具有 `public`（所有人可见）、`static`（通过接口名称访问）和 `final`（在声明时初始化）修饰符的常量：`public static final int VARIABLE = 0;`

### 方法

1. 未提供实现的方法隐式为 `public abstract`：`public abstract void method();`

2. Java SE 8：带有 `static` 或 `default` 修饰符的方法必须提供实现且隐式为 `public`：`public static() { ... }`

在应用了上述更改后，我们将得到：

```java
interface {
    int VARIABLE = 0;
    void method();
    static void static() { ... }
    default void getDefault() { ... }
}
```

## 第 79.7 节：泛型接口

假设你想定义一个允许从不同类型（例如 AMQP、JMS 等）发布/消费数据的接口，但你希望能够切换实现细节。让我们定义一个可以在多个实现之间复用的基础 IO 接口：

```java
public interface IO<IncomingType, OutgoingType> {
    void publish(OutgoingType data);
    IncomingType consume();
    IncomingType RPCSubmit(OutgoingType data);
}
```

现在我可以实例化该接口，但由于我们没有为这些方法提供默认实现，实例化时需要一个实现：

```java
IO<String, String> mockIO = new IO<String, String>() {
    private String channel = "somechannel";
    @Override
    public void publish(String data) { }
    @Override
    public String consume() { return ""; }
    @Override
    public String RPCSubmit(String data) { return ""; }
};
```

```java
System.out.println("Publishing " + data + " to " + channel);

@Override
public String consume() {
    System.out.println("Consuming from " + channel);
    return "some useful data";
}
```

```java
@Override
public String RPCSubmit(String data) { return "received " + data + " now "; }
```

```java
mockIO.consume(); // 输出: Consuming from somechannel
mockIO.publish("TestData"); // Publishing TestData to somechannel
System.out.println(mockIO.RPCSubmit("TestData")); // received TestData just now
```

我们还可以用这个接口做一些更有用的事情，假设我们用它来封装一些基础的 RabbitMQ 函数：

```java
public class RabbitMQ implements IO<String, String> { 
    private String exchange; 
    private String queue;

    public RabbitMQ(String exchange, String queue) { 
        this.exchange = exchange;
        this.queue = queue;
    }

    @Override
    public void publish(String data) {
        rabbit.basicPublish(exchange, queue, data.getBytes());
    }

    @Override
    public String consume() {
        return rabbit.basicConsume(exchange, queue);
    }

    @Override
    public String RPCSubmit(String data) {
        return rabbit.rpcPublish(exchange, queue, data);
    }
}
```

假设现在我想用这个 IO 接口来统计自上次系统重启以来的网站访问次数，并能够显示总访问次数——你可以这样做：

```java
import java.util.concurrent.atomic.AtomicLong;
public class VisitCounter implements IO<Long, Integer> {
    private static AtomicLong websiteCounter = new AtomicLong(0);
    @Override
    public void publish(Integer count) { 
        websiteCounter.addAndGet(count);
    }

    @Override
    public Long consume() {
        return websiteCounter.get();
    }

    @Override
    public Long RPCSubmit(Integer count) { 
        return websiteCounter.addAndGet(count);
    }
}
```

现在我们使用 `VisitCounter`：

```java
VisitCounter counter = new VisitCounter();

// 刚刚有 4 次访问，万岁 counter.publish(4);
// 刚刚又有一次访问，万岁 counter.publish(1);

// 获取统计计数器的数据
System.out.println(counter.consume()); // 输出 5
// 显示统计计数页的数据，但将其计为一次页面访问
System.out.println(counter.RPCSubmit(1)); // 输出 6
```

在实现多个接口时，你不能多次实现同一个接口。泛型接口也同样如此。因此，这段代码是无效的，会导致编译错误：

```java
interface Printer<T> { void print(T value); }
```

```java
// 无效！
class SystemPrinter implements Printer<Double>, Printer<Integer> {
    @Override 
    public void print(Double d) { System.out.println("Decimal: " + d); }
    @Override 
    public void print(Integer i) { System.out.println("Discrete: " + i); }
}
```

# 第 79.8 节：加强边界类型参数

边界类型参数允许你对泛型类型参数设置限制：

```java
class SomeClass {
}
class Demo<T extends SomeClass> {
}
```

但一个类型参数只能绑定到一个特定的类类型。

接口可以绑定到一个已经有了绑定的类型。这通过符号 `&` 实现：

```java
interface SomeInterface {
}
class GenericClass<T extends SomeClass & SomeInterface> {
}
```

这加强了绑定，可能要求类型参数派生自多个类型。

多个接口类型可以绑定到一个类型参数：

```java
class Demo<T extends SomeClass & FirstInterface & SecondInterface> {
}
```

但应该谨慎使用。多个接口绑定通常是代码异味（code smell）的信号，表明应该创建一个新类型作为其他类型的适配器：

```java
interface NewInterface extends FirstInterface, SecondInterface {
}
class Demo<T extends SomeClass & NewInterface> {
}
```

# 第 79.9 节：在抽象类中实现接口

接口中定义的方法默认是 `public` 且 `abstract`（公共抽象的）。当抽象类实现接口时，接口中定义的任何方法都不一定由抽象类实现。

```java
interface MyInterface {
    void action();
}

abstract class MyBase implements MyInterface {
    // 此处未实现 action()
}
```

## 第 80 章：正则表达式

正则表达式是一种特殊的字符序列，有助于匹配字符串中的模式。Java 通过 `java.util.regex` 包提供了正则表达式的支持。

## 1. 使用捕获组

如果你需要提取字符串的一部分，可以使用捕获组。在这种情况下，括号被称为捕获组。在示例中，我们将使用以下代码：

```java
Pattern pattern = Pattern.compile("(\\d{3})-(\\d{3})-(\\d{4})");
Matcher matcher = pattern.matcher("800-555-1234");
if (matcher.find()) {
    System.out.println(matcher.group(1)); // 800
    System.out.println(matcher.group(2)); // 555
}
```

（注：此处示例代码不完整，后续逻辑如下）

在使用 `group` 方法之前，我们不能忘记在字符串中转义反斜杠，得到如下模式：

```java
Pattern pattern = Pattern.compile("(\\d{3})-(\\d{3})-(\\d{4})");
Matcher matcher = pattern.matcher("800-555-1234");
if (matcher.find()) {
    System.out.println(matcher.group(1)); // 800
    System.out.println(matcher.group(2)); // 555
    System.out.println(matcher.group(3)); // 1234
}
```

（注：原文此处逻辑略有错乱，已根据技术语境梳顺翻译）

为了获取 `"areaCode"` 的内容，我们可以使用：

```java
String areaCode = matcher.group(1); // 800
```

Java 7 引入了命名捕获组。命名捕获组类似于编号捕获组（但使用名称而不是数字），尽管语法有细微变化。

我们可以修改上面的代码以使用命名组：



# Java 正则表达式与排序

## 1. 命名捕获组

```java
Pattern pattern = Pattern.compile("(?<areaCode>\d{3})-(?<three>\d{3})-(?<four>\d{4})");
Matcher matcher = pattern.matcher("800-555-1234");
if (matcher.find()) {
    System.out.println(matcher.group("areaCode")); // 800
    System.out.println(matcher.group("three")); // 555
    System.out.println(matcher.group("four")); // 1234
}
```

## 2. 通过编译标志使用自定义行为的正则表达式

`Pattern` 可以带有标志编译，如果正则表达式是作为字面量字符串，可以使用内联修饰：

```java
Pattern pattern = Pattern.compile("foo.", Pattern.CASE_INSENSITIVE | Pattern.DOTALL);
Matcher matcher = pattern.matcher("FOO\n");
matcher.find(); // 返回 true
```

> * 如果正则表达式没有忽略大小写和单行模式，
> * 它将失败，因为 `FOO` 不匹配 `/foo/`，且 `\n`（换行符）不匹配 `/.*/`。

```java
Pattern anotherPattern = Pattern.compile("(?si)foo");
Matcher matcher2 = anotherPattern.matcher("FOO\n");
matcher2.find(); // 返回 true

"foOt".replaceAll("(?si)foo", "ca"); // 返回 "cat".
```

## 3. 转义字符

通常，为了将正则表达式特定的字符（如 `\+|` 等）按字面意思使用，需要对其进行转义。在正则表达式中这通过反斜杠 `\` 实现。然而，由于它在 Java 字符串中具有特殊含义，你必须使用双反斜杠 `\\`。

这两个示例无法作用：

```java
""?".replaceAll("?", "!"); // java.util.regex.PatternSyntaxException
""?".replaceAll("\\", "!"); // 无效的转义序列
```

这个示例有效：

```java
""?".replaceAll("\\\\", "!"); // !!!
```

## 4. 分割由管道分隔的字符串

这不会返回预期结果：

```java
"a|b".split("||"); // [a, b]
```

这返回了预期结果：

```java
"a|b".split("\\||"); // [a, b]
```

### 转义反斜杠 `\`

这将导致错误：

```java
"\\".matches("\\\\"); // 语法错误
```

这个是可以行的：

```java
"\\\".matches("\\\\"); // true
```

## 5. 不匹配给定字符串

要匹配不包含给定字符串的内容，可以使用负向先行断言。

正则表达式语法：`(?!string-to-not-match)`

示例：

```java
// 不匹配 "popcorn"
String regexString = "^(?!popcorn).*$";
System.out.println("[popcorn]" + " " + "popcorn".matches(regexString) ? 
"matched" : "nope!"); 
System.out.println("[unicorn]" + " " +
"unicorn".matches(regexString) ? 
"matched" : "nope!");
```

输出：

```
[popcorn] nope! [unicorn] matched
```

## 6. 使用正则字面量匹配

如果你需要匹配作为正则表达式语法部分的字符，可以将模式的所有或部分标记为正则字面量。

`\Q` 标记正则字面量的开始。`\E` 标记正则字面量的结束。

```java
// 以下代码会抛出 PatternSyntaxException，因为未闭合的括号 `[123]`。matches("[123]")`
// 将括号封装在 \Q 和 \E 中允许模式按照你预期的方式进行匹配
`[\Q123\E]`.matches("\\\\Q123\\\\E") // 返回 true
```

## 7. 匹配反斜杠

如果你想在正则表达式中匹配反斜杠，你必须对其进行转义。

反斜杠是正则表达式中的转义字符。你可以使用 `'\\'` 来引用正则表达式中的单个反斜杠。

然而，反斜杠也是 Java 字符串字面量中的转义字符。为了从字符串字面量创建正则表达式，你必须对它的每个反斜杠进行转义。在字符串字面量 `"\\"` 中可以使用 `"\\\\"` 来创建一个包含 `"\\"` 的正则表达式，后者可以匹配 `"\\"`。例如，考虑匹配如 `"C:\\\\dir\\myfile.txt"` 的字符串。正则表达式 `([A-Za-z]:\\*)` 会匹配，并将驱动器字母作为捕获组提供。注意正则表达式中的双倍反斜杠需要被转义。

```java
String path = "C:\\dir\\myfile.txt";
System.out.println("Local path: " + path); // "C:\\dir\\myfile.txt"
String regex = "\\\[A-Za-z]:\\\\*"; // 用四个匹配一个
System.out.println("Regex: " + regex); // ("\\\[A-Za-z]:\\\\**")
```

```java
Pattern pattern = Pattern.compile(regex);
Matcher matcher = pattern.matcher(path);
if (matcher.matches()) {
    System.out.println("This path is on drive " + matcher.group(1) + ":/"); // 此路径位于驱动器 C。
}
```

如果你想匹配两个反斜杠，你会发现在字面量字符串中使用八个反斜杠，以表示正则表达式中的四个个，从而匹配出两个。

```java
String path = "\\\\\\\\myhost\\share\\myfile.txt";
System.out.println("UNC path: " + path); // \\\myhost\\share\\myfile.txt"
String regex = "\\\\\\\\\\(.+?)\\\\\\\"; // 用八匹配两个
System.out.println("Regex: " + regex); // \\\\\\\(.+?)\\\\\**")
```

```java
Pattern pattern = Pattern.compile(regex);
Matcher matcher = pattern.matcher(path);
if (matcher.matches()) {
    System.out.println("This path is on host " + matcher.group(1) + "."); // 此路径位于主机 'myhost'。
}
```

# 第 81 章：Comparable 和 Comparator

## 81.1 使用 `Comparable<T>` 或 `Comparator<T>` 对列表排序

假设我们正在处理一个通过姓和名表示人的类。我们已经创建了一个基础类来实现此，并实现了正确的 `equals` 和 `hashCode` 方法。

```java
public class Person {
    private final String lastName; // 不变 - 非空
    private final String firstName; // 不变 - 非空

    public Person(String firstName, lastName){
        this.firstName = firstName != null ? firstName : "";
        this.lastName = lastName != null ? lastName : "";
    }

    public String getFirstName() {
        return firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public String toString() {
        return lastName + "," + firstName;
    }

    @Override
    public boolean equals(Object o) {
        if (! ( instanceof Person)) return false;
        Person p = (Person)o;
        return firstName.equals(p.firstName) && lastName.equals(p.lastName);
    }

    @Override
    public int hashCode() {
        return Objects.hash(firstName, lastName);
    }
}
```

现在，我们想按名称对 `Person` 对象列表进行排序，如下场景所示：

```java
public static void main(String[] args) {
    List<Person> people = Arrays.asList(new Person("John", "Doe"), new Person("Bob", "Dole"), new Person("Ronald", "McDonald"), new Person("Alice", "McDonald"), new Person("Jill", "Doe"));
    // 这不起作用，因为 Person 没有实现 Comparable
    // Collections.sort(people);
}
```

为了给 `Person` 提供自然排序，我们实现 `Comparable<Person>`，这需要实现 `compareTo` 方法：

```java
public class Person implements Comparable<Person> {
    // ... 字段和方法

    @Override
    public int compareTo(Person other) {
        int lastNameCompare = lastName.compareTo(other.lastName);
        if (lastNameCompare != 0) {
            return lastNameCompare;
        } else {
            return firstName.compareTo(other.firstName);
        }
    }
}
```

现在，`main` 方法将正常运行：

```java
public static void main(String[] args) {
    List<Person> people = Arrays.asList(new Person("John", "Doe"), new Person("Bob", "Dole"), new Person("Ronald", "McDonald"), new Person("Alice", "McDonald"), new Person("Jill", "Doe"));
    Collections.sort(people); // people 按姓、再名排序：Alice McDonald, Bob Dole, John Doe, Jill Doe, Ronald McDonald
}
```

然而，如果你不想或无法修改类，你可以提供一个自定义的 `Comparator<T>` 来处理两个 `Person` 对象的比较。同样，提供比较器可以指示 Java 如何比较两个通常可比较的对象。

```java
public class PersonComparator implements Comparator<Person> {
    public int compare(Person p1, Person p2) {
        // 如果 p1 的 lastName 和 p2 的 lastName 不等价，
        // 通过比较 lastName 来比较 p1 和 p2。
        // 否则，通过比较 firstName 来比较 p1 和 p2。
        if (p1.getLastName().compareTo(p2.getLastName()) != 0) {
            return p1.getLastName().compareTo(p2.getLastName());
        } else {
            return p1.getFirstName().compareTo(p2.getFirstName());
        }
    }
}
```

`Collections.sort(people);` // 非法，`Person` 没有实现 `Comparable`。

`Collections.sort(people, new PersonComparator());` // 合法

// people 按姓排序，再按名排序：

// --> Jill Doe, John Doe, Bob Dole, Alice McDonald, Ronald McDonald

`Comparators` 也可以作为匿名内部类来创建/使用。

```java
// 假设 Person 的第一个版本（没有实现 Comparable）
// 如此处所示
static void main(String[] args) {
    List<Person> people = Arrays.asList(new Person("John", "Doe"),
        new Person("Bob", "Dole"),
        new Person("Ronald", "McDonald"), new Person("Alice", "McDonald"),
        new Person("Jill", "Doe"));

    Collections.sort(people); // 非法，Person 没有实现 Comparable。
    Collections.sort(people, new PersonComparator()); // 合法

    // people 按姓排序，再按名排序：
    // --> Jill Doe, John Doe, Bob Dole, Alice McDonald, Ronald McDonald

    // 匿名类
    Collections.sort(people, new Comparator<Person>() { // 合法
        public int compare(Person p1, Person p2) {
            // 方法代码...
        }
    });
}
```

版本 ≧ Java SE 8

### 基于 Lambda 表达式比较器

从 Java 8 开始，比较器可以表示为 lambda 表达式：

```java
Collections.sort(people, (p1, p2) -> { // 合法 //方法代码....
});
```

### Comparator 默认方法

此外，`Comparator` 接口上有一些有趣的默认方法用于构建比较器：以下代码构建了一个按姓比较再按名比较的 `Comparator`。

```java
Collections.sort(people, Comparator.comparing(Person::getLastName).thenComparing(Person::getFirstName));
```

反转比较器的顺序

任何比较器都可以使用 `reversed` 方法轻松反转，该方法会将升序顺序变为降序。

## 81.2 `compareTo` 和 `compare` 方法

`Comparable<T>` 接口需要一个方法：

```java
public interface Comparable<T> {
    public int compareTo(T other);
}
```

`Comparator<T>` 接口需要一个方法：

```java
public interface Comparator<T> {
    public int compare(T t1, T t2);
}
```

这两个方法本质上做相同的事情，但有一个微小的区别：`compareTo` 与当前对象进行比较，而 `compare` 比较 `t1` 和 `t2`，完全不在当前对象。

除了这个区别外，这两个方法的要求相似。

具体来说（对于 `compareTo`），将此对象与指定的对象进行排序比较。返回一个负整数、零或正整数，取决于此对象是否小于、等于或大于指定的对象。因此，对于 `a` 和 `b` 的比较：

- 如果 `a < b`，`a.compareTo(b)` 和 `compare(a,b)` 应该返回一个负整数
- `b.compareTo(a)` 和 `compare(b,a)` 应该返回一个正整数
- 如果 `a > b`，`a.compareTo(b)` 和 `compare(a,b)` 应该返回一个正整数



- `b.compareTo(a)` 和 `compare(b,a)` 应该返回一个负整数
- 如果 `a` 等于 `b`，所有比较都应该返回 0。

## 第 81.3 节：自然（可比较）排序与显式（比较器）排序

有两个 `Collections.sort()` 方法：

1. 一个接受 `List<T>` 作为参数，其中 `T` 必须实现 `Comparable` 并重写 `compareTo()` 方法来确定排序顺序。
2. 一个接受 `List` 和 `Comparator` 作为参数，由 `Comparator` 决定排序顺序。

首先，是一个实现了 `Comparable` 的 `Person` 类：

```java
public class Person implements Comparable<Person> {
    private String name;
    private int age;

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public int compareTo(Person o) {
        return this.getAge() - o.getAge();
    }

    @Override
    public String toString() {
        return this.getName();
    }
}
```

以下是如何使用上述类按照由 `compareTo()` 方法定义的元素自然顺序对 `List` 进行排序：

```java
List<Person> pList = new ArrayList<Person>();
p = new Person();
p.setName("A");
p.setAge(10);
pList.add(p);

p = new Person();
p.setName("Z");
p.setAge(20);
pList.add(p);

p = new Person();
p.setName("D");
p.setAge(30);
pList.add(p);

Collections.sort(pList);
System.out.println(pList);
```

以下是如何使用匿名内联 `Comparator` 对未实现 `Comparable` 的 `List` 进行排序，或者在此情况下按自然顺序以外的其他顺序对 `List` 进行排序：在这里对另一个属性排序：

```java
Collections.sort(pList, new Comparator<Person>() {
    @Override
    public int compare(Person o1, Person o2) {
        return o1.getName().compareTo(o2.getName());
    }
});
```

## 第 81.4 节：使用 comparing 方法创建比较器

`Comparator.comparing(Person::getName)` 创建了一个按姓名比较的比较器。任何比较器都可以使用 `reversed` 方法轻松地反转，该方法会将升序顺序变为降序。

## 第 81.2 节：compareTo 和 compare 方法

... 此外，`Comparator` 接口上有一些有趣的默认方法用于构建比较器：以下代码构建了一个按姓比较再按名比较的 `Comparator`。

```java
Collections.sort(people, Comparator.comparing(Person::getLastName).thenComparing(Person::getFirstName));
```

反转比较器的顺序

任何比较器都可以使用 `reversed` 方法轻松反转，该方法会将升序顺序变为降序。

## 第 81.2 节：compareTo 和 compare 方法

`Comparable<T>` 接口需要一个方法：

```java
public interface Comparable<T> {
    public int compareTo(T other);
}
```

`Comparator<T>` 接口需要一个方法：

```java
public interface Comparator<T> {
    public int compare(T t1, T t2);
}
```

这两个方法本质上做相同的事情，但有一个微小的区别：`compareTo` 与当前对象进行比较，而 `compare` 比较 `t1` 和 `t2`，完全不在当前对象。

除了这个区别外，这两个方法的要求相似。

具体来说（对于 `compareTo`），将此对象与指定的对象进行排序比较。返回一个负整数、零或正整数，取决于此对象是否小于、等于或大于指定的对象。因此，对于 `a` 和 `b` 的比较：

- 如果 `a < b`，`a.compareTo(b)` 和 `compare(a,b)` 应该返回一个负整数
- `b.compareTo(a)` 和 `compare(b,a)` 应该返回一个正整数
- 如果 `a > b`，`a.compareTo(b)` 和 `compare(a,b)` 应该返回一个正整数
- `b.compareTo(a)` 和 `compare(b,a)` 应该返回一个负整数
- 如果 `a` 等于 `b`，所有比较都应该返回 0。

## 第 81.3 节：自然（可比较）排序与显式（比较器）排序

有两个 `Collections.sort()` 方法：

1. 一个接受 `List<T>` 作为参数，其中 `T` 必须实现 `Comparable` 并重写 `compareTo()` 方法来确定排序顺序。
2. 一个接受 `List` 和 `Comparator` 作为参数，由 `Comparator` 决定排序顺序。

首先，是一个实现了 `Comparable` 的 `Person` 类：

```java
public class Person implements Comparable<Person> {
    private String name;
    private int age;

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public int compareTo(Person o) {
        return this.getAge() - o.getAge();
    }

    @Override
    public String toString() {
        return this.getName();
    }
}
```

以下是如何使用上述类按照由 `compareTo()` 方法定义的元素自然顺序对 `List` 进行排序：

```java
List<Person> pList = new ArrayList<Person>();
p = new Person();
p.setName("A");
p.setAge(10);
pList.add(p);

p = new Person();
p.setName("Z");
p.setAge(20);
pList.add(p);

p = new Person();
p.setName("D");
p.setAge(30);
pList.add(p);

Collections.sort(pList);
System.out.println(pList);
```

以下是如何使用匿名内联 `Comparator` 对未实现 `Comparable` 的 `List` 进行排序，或者在此情况下按自然顺序以外的其他顺序对 `List` 进行排序：在这里对另一个属性排序：

```java
Collections.sort(pList, new Comparator<Person>() {
    @Override
    public int compare(Person o1, Person o2) {
        return o1.getName().compareTo(o2.getName());
    }
});
```

## 第 81.4 节：使用 comparing 方法创建比较器

`Comparator.comparing(Person::getName)` 创建了一个按姓名比较的比较器。任何比较器都可以使用 `reversed` 方法轻松地反转，该方法会将升序顺序变为降序。

## 82：Java 浮点运算

浮点数是带有小数部分的数字（通常用小数点表示）。在 Java 中，有用于浮点的原始类型：`float`（使用 4 字节）和 `double`（使用 8 字节）。本文档详细说明了可以在浮点上进行的操作。

## 第 82.1 节：比较浮点值

在使用关系运算符：`==`、`!=`、`<` 等比较浮点值（`float` 或 `double`）时应小心。这些运算符根据浮点值的二进制表示给出结果。例如：

```java
public class CompareTest {
    public static void main(String[] args) {
        double oneThird = 1.0 / 3.0;
        double one = oneThird * 3;
        System.out.println(one == 1.0); // 输出 "false"
    }
}
```

计算 `oneThird` 引入了微小的舍入误差，当我们乘以 `oneThird` 乘以 3 时，得到的结果与 `1.0` 有微不同。这种表示不准确的问题在尝试混合 `double` 和 `float` 时更为明显。例如：

```java
public class CompareTest2 {
    public static void main(String[] args) {
        float floatVal = 0.1f;
        double doubleVal = 0.1;
        double doubleCopy = floatVal;

        System.out.println(floatVal); // 0.1
        System.out.println(doubleVal); // 0.1
        System.out.println(doubleCopy); // 0.1000000014901162

        System.out.println(floatVal == doubleVal); // false
        System.out.println(doubleVal == doubleCopy); // false
    }
}
```

Java 中 `float` 和 `double` 的浮点表示的精度位数有限。对于 `float` 类型，精度是 23 个二进制位或约 8 位十进制。对于 `double` 类型，精度是 52 位或约 15 位十进制。此外，某些算术运算会引入舍入误差。因此，当程序比较浮点值时，标准做法是定义一个允许的 `delta`。如果两个数之间的差小于 `delta`，它们被认为相等。例如：

```java
if (Math.abs(v1 - v2) < delta)
```

Delta 比较示例：

```java
public class DeltaCompareExample {
    private static boolean deltaCompare(double v1, double v2, double delta) {
        // 如果 v1 和 v2 之间的差异小于 delta，返回 true
        return Math.abs(v1 - v2) < delta;
    }
}
```

```java
public static void main(String[] args) {
    double[] doubles = {1.0, 1.0001, 1.00000001, 1.0000000000001};
    double[] deltas = {0.01, 0.00001, 0.0000001, 0.000000001, 0};

    // 遍历上面初始化的所有 deltas
    for (int j = 0; j < deltas.length; j++) {
        double delta = deltas[j];
        System.out.println("delta: " + delta);

        // 遍历上面初始化的所有 doubles
        for (int i = 0; i < doubles.length; i++) {
            double d1 = doubles[i];
            double d2 = doubles[i + 1];
            boolean result = deltaCompare(d1, d2, delta);
            System.out.println("" + d1 + " == " + d2 + " ? " + result);
        }
    }
}
```

结果：

```
delta : 0.01
1.0 == 1.0001 ? true
1.0001 == 1.0000001 ? true
1.0000001 == 1.00000001 ? true
1.000000001 == 1.0000000001 ? true
```

```
delta : 1.0E-5
1.0 == 1.0001 ? false
1.00001 == 1.0000001 ? false
1.0000001 == 1.00000001 ? true
1.000000001 == 1.00000000000001 ? true
```

```
delta : 1.0E-7
1.0 == 1.0001 ? false
1.00001 == 1.0000001 ? false
1.0000001 == 1.00000001 ? true
1.000000001 == 1.00000000000001 ? true
```

```
delta : 1.0E-10
1.0 == 1.0001 ? false
1.00001 == 1.0000001 ? false
1.0000001 == 1.00000001 ? false
1.000000001 == 1.00000000000001 ? false
```

```
delta : 0.0
1.0 == 1.0001 ? false
1.00001 == 1.0000001 ? false
1.0000001 == 1.00000001 ? false
1.000000001 == 1.00000000000001 ? false
```

此外，也可以使用考虑装箱类型的静态方法来比较 `double` 和 `float` 原始数据类型。例如：

```java
double a = 1.0;
double b = 1.0001;

System.out.println(Double.compare(a, b)); // -1
System.out.println(Double.compare(b, a)); // 1
```

最后，确定哪些 `delta` 最适合比较可能是棘手的。一种常用的方法是选择直觉上正确的 `delta` 值。然而，如果你知道输入值的量级和（真实的）精度以及所执行的计算，可能对结果的精度给出数学上合理的边界，从而为 `delta` 给出边界。（数学中有一个名为数值分析的正式分支，曾教给计算科学家，涵盖了这类分析。）

## 第 82.2 节：溢出与下溢

**Float 数据类型**

`float` 数据类型是单精度 32 位 IEEE 754 浮点数。

**Float 溢出**

最大可能值为 `3.4028235e+38`，当超过此值时会产生无穷大 `Infinity`。

```java
float f = 3.4e38;
float result = f*2;
System.out.println(result); //Infinity
```

**Float 下溢**

最小值为 `1.4e-45`，当低于此值时会产生 `0.0`。

```java
float f = 1e-45;
float result = f/1000;
System.out.println(result);
```

**double 数据类型**

`double` 数据类型是双精度 64 位 IEEE 754 浮点数。

**double 溢出**

最大可能值为 `1.7976931348623157e+308`，当超过此值时产生无穷大 `Infinity`。

```java
double d = 1e308;
double result = d*2;
System.out.println(result); //Infinity
```

**double 下溢**

最小值为 `4.9e-324`，当低于此值时会产生 `0.0`。

```java
double d = 4.8e-323;
double result = d/1000;
System.out.println(result);
```

```java
public Sheep(String name, int weight) {
    this.name = name;
    this.weight = weight;
}
```



# 克隆与递归

## 第 84.2 节：使用拷贝工厂进行克隆

```java
public class Sheep {
    private String name;
    private int weight;

    public Sheep(String name, int weight) {
        this.name = name;
        this.weight = weight;
    }

    public static Sheep newInstance(Sheep other) {
        return new Sheep(other.name, other.weight);
    }
}
```

## 第 84.3 节：使用拷贝构造函数进行克隆

克隆对象的一种简单方法是实现拷贝构造函数。

```java
public class Sheep {
    private String name;
    private int weight;

    public Sheep(String name, int weight) {
        this.name = name;
        this.weight = weight;
    }

    // 拷贝构造函数
    // 将 other 的字段拷贝到新对象
    public Sheep(Sheep other) {
        this.name = other.name;
        this.weight = other.weight;
    }
}
```

```java
// 创建一只羊
Sheep sheep = new Sheep("Dolly", 20);
// 克隆这只羊
Sheep dolly = new Sheep(sheep); // dolly.name 为 "Dolly"， dolly.weight 为 20
```

## 第 84.4 节：通过实现 Cloneable 接口克隆

通过实现 `Cloneable` 接口来克隆对象。

```java
public class Sheep implements Cloneable {
    private String name;
    private int weight;

    public Sheep(String name, int weight) {
        this.name = name;
        this.weight = weight;
    }

    @Override
    public Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

```java
// 创建一只羊
Sheep sheep = new Sheep("Dolly", 20);
```

```java
// 克隆这只羊
Sheep dolly = (Sheep) sheep.clone(); // dolly.name 为 "Dolly"
dolly.weight 为 20
```

## 第 84.5 节：执行浅拷贝的克隆

克隆对象时的默认行为是对对象的字段执行浅拷贝。在这种情况下，原始对象和克隆对象都持有指向同一个对象的引用。

此示例展示了这种行为。

```java
import java.util.List;
public class Sheep implements Cloneable {
    private String name;
    private int weight;
    private List<Sheep> children;

    public Sheep(String name, int weight) {
        this.name = name;
        this.weight = weight;
    }

    @Override
    public Object clone() throws CloneNotSupportedException {
        return super.clone();
    }

    public List<Sheep> getChildren() {
        return children;
    }

    public void setChildren(List<Sheep> children) {
        this.children = children;
    }
}
```

```java
import java.util.Arrays;
import java.util.List;
// 创建一只羊
Sheep sheep = new Sheep("Dolly", 20);
```

```java
// 创建子节点
Sheep child1 = new Sheep("Child1", 4);
Sheep child2 = new Sheep("Child2", 5);

sheep.setChildren(Arrays.asList(child1, child2));
```

```java
// 克隆这只羊
Sheep dolly = (Sheep) sheep.clone();
List<Sheep> sheepChildren = sheep.getChildren();
List<Sheep> dollysChildren = dolly.getChildren();
for (int i = 0; i < sheepChildren.size(); i++) {
    // 输出 true，两个数组都包含相同的对象
    System.out.println(sheepChildren.get(i) == dollyChildren.get(i));
}
```

# 第 85 章：递归

递归发生在方法调用自身时。这种方法被称为递归方法。递归方法可能比等效的迭代解决方案简洁。然而，对于深度递归，这在 Java 中是不行的。

## 第 85.1 节：递归的基本概念

什么是递归：

通常情况下，递归是指函数直接或间接地调用其自身。例如：

```java
// 此方法“无限”调用自身
public void useless() {
    useless(); // 方法调用自身（直接）
}
```

应用递归的条件：

有两个前提条件：

1. 必须有一个基础条件。当递归到达基础条件时，函数终止。

2. 每一层递归应该将问题分解为更小的部分。假设问题是有限的，这将确保递归终止。

## 深度递归在 Java 中存在问题

示例

以下函数使用递归计算阶乘：

```java
public int factorial(int n) {
  if (n <= 1) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
}
```

这在算法上是正确的，但它有一个很大的问题。如果你传入一个较大的 `n`，它将抛出 `StackOverflowError`，在直到 Java 9 的任何 Java 版本中都是如此。

## 第 85.2 节：深度递归在 Java 中存在问题

考虑以下使用递归相加两个数字的朴素方法：

```java
public static int add(int a, int b) {
  if (a == 0) {
    return b;
  } else {
    return add(a - 1, b + 1); // 尾递归调用
  }
}
```

（显然，有更好的方法相加两个整数。上面的代码仅仅是为了说明手动尾调用消除的效果。）

### 为什么 Java（尚未）实现尾调用消除

有许多原因导致在 Java 中添加尾调用消除并不易事。例如：

某些代码可能依赖于 `StackOverflow` 来（例如）对计算问题的大小设置限制。沙箱安全管理器在决定是否允许非权限代码执行特权操作时，通常依赖于分析调用堆栈。

正如 John Rose 在《VM 中的尾调用》（Tail calls in the VM）中所解释的那样：

> “移除调用者栈帧的影响对某些 API 是可见的，特别是访问控制检查和堆栈追踪。这就像调用者直接调用了被调用者。在控制权转移到被调用者之后，调用者拥有的任何权限都会丢弃。然而，被调用方法的链接和访问性在转移转移之前就已经计算完毕，并且考虑了作为尾调用的调用者”

换句话说，尾调用消除可能会导致访问控制方法错误地认为安全敏感 API 正在被信任的代码调用。

### 第 85.3 节：递归的类型

递归可以分类为**头部递归**（Head Recursion）或**尾递归**（Tail Recursion），取决于递归方法调用所在的位置。在**头部递归**中，递归调用发生时，位于函数中其他处理之前（想象它发生在函数的顶部，或“头部”）。

在**尾递归**中，情况则相反——处理发生在递归调用之前。在这两种递归风格之间进行选择似乎是随机的，但这种选择可能会产生决定性的差异。

一个在路径开头有单个递归调用路径的函数使用了所谓的头部递归。上一个示例中的阶乘函数展示了头部递归。它一旦确定需要递归，所做的第一件事就是使用递减的参数调用它自己。一个在路径末尾有单个递归调用的函数使用的是尾递归。

```java
public void tail(int n) {
    if(n == 1) return;
    else
        tail(n-1);
    System.out.println(n);
}

public void head(int n) {
    if(n == 0) return;
    else
        System.out.println(n);
        head(n-1);
}
```

如果递归调用发生在方法的末尾，则称为尾递归。尾递归类似于循环。方法在跳转到下一次递归调用之前执行之前所有的语句。
如果递归调用发生在方法的开头，则称为头部递归。方法在跳转到下一次递归调用之前会保存状态。

参考：
头部递归与尾递归的区别

### 85.4：计算第 N 个斐波那契数

以下方法使用递归计算第 N 个斐波那契数。

```java
public int fib(int n) {
    if (n > 2) {
        return fib(n - 2) + fib(n - 1);
    }
}
```

该方法实现了一个基础情况（`n <= 2`）和一个递归情况（`n > 2`）。这说明了如何使用递归来计算递归关系。
然而，虽然这个示例具有说明性，但它也是低效的：方法的每个实例都会再次调用函数本身，导致随着 `N` 的增加，函数被调用的次数呈指数级增长。上面的函数复杂度是 `O(2N)`，但等效的迭代解决方案复杂度为 `O(N)`。此外，还有一个“闭式”表达式，可以通过 `O(N)` 次浮点乘法进行求值。

### 第 85.5 节：StackOverflowError 与递归转循环

如果递归调用调得“太深”，会导致 `StackOverflowError`。Java 在其堆栈上为每个方法调用分配一个新的栈帧。然而，每个线程栈的空间是有限的。堆栈上过多的帧会导致栈溢出（SO）。

示例

```java
public void recursion(int depth) {
    if (depth > 0) {
        recursion(depth-1);
    }
}
```

调用此方法（`50000`）可能会导致栈溢出。通过在堆上存储帧数据而不是在栈上，可以将递归转换为循环。以下是模拟递归的方法：

```java
class Frame {
    public Node node;
    public int maxDepth;
    public int state = 0;

    public Frame(Node node, int maxDepth) {
        this.node = node;
        this.maxDepth = maxDepth;
    }
}

List<Frame> stack = new ArrayList<>();
stack.add(new Frame(root, 0));

while (!stack.isEmpty()) {
    int index = stack.size() - 1;
    Frame frame = stack.get(index);

    if (frame.maxDepth <= 0) {
        // 终止情况
        stack.remove(index);
    } else {
        switch (frame.state) {
            case 0:
                frame.state++;
                if (frame.node.left != null) {
                    stack.add(new Frame(frame.node.left, 0));
                }
                break;
            case 1:
                frame.state++;
                if (frame.node.right != null) {
                    stack.add(new Frame(frame.node.right, 0));
                }
                break;
            case 2:
                stack.remove(index);
                break;
        }
    }
}
```

### 85.6：计算数字的 N 次方

以下方法使用递归计算 `num` 的次方：

```java
public long power(final int num, final int exp) {
  if (exp == 0) {
    return 1;
  }
  if (exp == 1) {
    return num;
  }
  return num * power(num, exp - 1);
}
```

这说明了上述原理：递归方法实现了一个终止递归的基础情况（两种情况，`n = 0` 和 `n = 1`），以及再次调用方法的递归情况。该方法复杂度为 `O(N)`，可以通过尾调用优化还原为简单的循环。

**注意：** 这只是通用方法的一个示例。通常你可以想出更好的表示帧和/或存储帧数据的方法。

### 第 85.7 节：使用递归遍历树数据结构

考虑 `Node` 类具有三个成员：`data`、左子指针和右子指针，如下：

```java
public class Node {
    public int data;
    public Node left;
    public Node right;

    public Node(int data){
        this.data = data;
    }
}
```



我们可以通过连接多个`Node`类对象来遍历所示的树，这种遍历被称为树的中序遍历。

如上所示，使用递归我们可以遍历树数据结构而不使用任何其他数据结构，这在迭代方法中是无法实现的。

### 第 85.8 节：使用递归反转字符串

以下是反转字符串的递归代码：

```java
/**
 * 仅用于解释递归思想的代码片段
 */
```

```java
public class Reverse {
  public static void main(String args[]) {
    String string = "hello world";
    System.out.println(reverse(string)); // prints dlrow olleh
  }

  public static String reverse(String s) {
    if (s.length() == 1) {
      return s;
    }
    return reverse(s.substring(1)) + s.charAt(0);
  }
}
```

## 第 85.9 节：计算 1 到 N 的整数和

以下方法使用递归计算 0 到 N 的整数和：

```java
public int sum(final int n) {
  if (n > 0) {
    return n + sum(n - 1);
  } else {
    return n;
  }
}
```

该方法的复杂度为`O(N)`，并且可以通过尾递归优化简化为简单的循环。事实上，存在一个闭式表达式可以在`O(1)`次操作内计算出该和。

## 第 86 章：字符串与其他类型之间的相互转换

### 第 86.1 节：将字符串转换为其他数据类型

你可以按照如下方式将数字字符串转换为各种 Java 数值类型：

字符串转`int`：

```java
String number = "12";
int num = Integer.parseInt(number);
```

字符串转`float`：

```java
String number = "12.0";
float num = Float.parseFloat(number);
```

字符串转`double`：

```java
String s = "1.47";
double num = Double.parseDouble(s);
```

字符串转`boolean`：

```java
String falseString = "False";
boolean falseBool = Boolean.parseBoolean(falseString); // falseBool = false

String trueString = "True";
boolean trueBool = Boolean.parseBoolean(trueString); // trueBool = true
```

字符串转`long`：

```java
String number = "47";
long num = Long.parseLong(number);
```

字符串转`BigInteger`：

```java
String bigNumber = "21";
BigInteger reallyBig = new BigInteger(bigNumber);
```

字符串转`BigDecimal`：

```java
String bigFraction = "17.21455";
BigDecimal reallyBig = new BigDecimal(bigFraction);
```

转换：如果你尝试解析一个格式不适当的数字，或者超出目标类型范围的字符串，上述数值转换都将抛出（未检查的）`NumberFormatException`。`Exceptions`章节讨论了如何处理这些异常。

如果你想测试是否可以解析一个字符串，可以实现如下`tryParse...`方法：

```java
boolean tryparseInt(String value) {
  try {
    int somechar = Integer.parseInt(value);
    return true;
  } catch (NumberFormatException e) {
    return false;
  }
}
```

然而，在解析之前立即调用此`tryParse...`方法（可以说）是不实践。更好的做法是直接调用`parse...`方法并处理异常。

### 第 86.2 节：字节（bytes）之间的转换

要将字符串编码为字节数组，你可以直接使用`String#getBytes()`方法，并使用任何 Java 运行时标准字符集之一：

```java
byte[] bytes = "test".getBytes(StandardCharsets.UTF_8);
```

解码时：

```java
String testString = new String(bytes, StandardCharsets.UTF_8);
```

你可以通过静态导入进一步简化调用：

```java
import static java.nio.charset.StandardCharsets.UTF_8;
...
byte[] bytes = "test".getBytes(UTF_8);
```

反向操作：对于常见的字符集，你可以用字符串指定字符集：

```java
byte[] bytes = "test".getBytes("UTF-8");
```

反向操作：

```java
String testString = new String(bytes, "UTF-8");
```

但这意味着你必须处理受检查的`UnsupportedCharsetException`。

以下调用将使用默认字符集。默认字符集是平台特定的，通常在 Windows、Mac 和 Linux 平台之间存在差异：

```java
byte[] bytes = "test".getBytes();
```

反向操作：

```java
String testString = new String(bytes);
```

注意，无效的字符和字节可能会被这些方法替换或跳过。为了获得更多控制——例如验证输入——建议你使用`CharsetEncoder`和`CharsetDecoder`类。

### 第 86.3 节：Base64 编码 / 解码

偶尔你会发现需要将二进制数据编码为 Base64 编码的字符串。

为此，我们可以使用来自`javax.xml.bind`包的`DatatypeConverter`类：

```java
import javax.xml.bind.DatatypeConverter;
import java.util.Arrays;

// 指定为字节数组的任意二进制数据
byte[] binaryData = "some arbitrary data".getBytes("UTF-8");
```

```java
// 将二进制转换为 Base64 编码字符串
String encodedData = DatatypeConverter.printBase64(binaryData);
// encodedData 现在为 "c29tZSBhcmJpdHHJcnkZGF0YQ="
```

```java
// 将 Base64 编码字符串转换回字节数组
byte[] decodedData = DatatypeConverter.parseBase64(encodedData);
// 断言原始数据和解码后的数据相等
Arrays.equals(binaryData, decodedData);
```

#### Apache commons-codec

或者，我们可以使用 Apache commons-codec 中的`Base64`：

```java
import org.apache.commons.codec.binary.Base64;

// 将你的 binaryData 作为字节数组
byte[] blob = "someBinaryData".getBytes();
```

```java
// 使用 Base64 将二进制转换为编码字符串
String encodedData = Base64.encodeBase64String(blob);
// encodedData 现在为 "c29tZSBhcmJpdHHJcnkZGF0YQ="
```

```java
// 将 Base64 编码字符串转换回字节数组
byte[] decodedData = Base64.decodeBase64String(encodedData);
// 断言原始数据和解码后的数据相等
Arrays.equals(binaryData, decodedData);
```

`Random`类的`nextInt(int bound)`方法接受一个不包含的上限边界，即返回的随机值必须小于该数字。然而，只有`nextInt`方法接受边界值；`nextLong`、`nextDouble`等方法均不支持。

```java
Random random = new Random();
random.nextInt(1000); // 0 - 999
number = 10 + random.nextInt(100); // number is in the range of 10 to 109
```

从 Java 1.7 开始，你也可以使用`ThreadLocalRandom(source)`。该类提供了一个线程安全的 PRNG（伪随机数生成器）。请注意，该类的`nextInt`方法同时接受上限和下界。`import java.util.concurrent.ThreadLocalRandom;`

```java
// nextInt 通常情况下是不包含上限值的，加 1 以使其包含
ThreadLocalRandom.current().nextInt(min, max + 1);
```

注意，官方文档指出，当`bound`接近$2^{31}-1$时，`nextInt(int bound)`可能会出现异常情况（**强调如此**）：

该算法略微复杂。它会拒绝那些导致分布不均的值（因为$2^{31}$不能被$n$整除）。值被拒绝的概率取决于$n$。最坏的情况是$n=2^{30}+1$，此时被拒绝的概率为 1/2，循环结束前的预期迭代次数为 2。

换句话说，指定边界值会（略微）降低`nextInt`方法的性能，而且随着边界接近`int`最大值的一半，这种性能下降会变得更加明显。

# 第 87.3 节：生成密码学安全的伪随机数

`Random`和`ThreadLocalRandom`对于日常使用已经足够了，但它们有一个巨大的问题：它们基于线性同余生成器，这种算法的输出可以很容易被预测。因此，这两个类不适用于加密用途（如密钥生成）。

在需要输出极难预测的 PRNG 的情况下，可以使用`java.security.SecureRandom`。预测该类实例创建的数字困难程度足以将该类标记为密码学安全。

```java
import java.security.SecureRandom;
import java.util.Arrays;
```

```java
public class Foo {
    public static void main(String[] args) {
        SecureRandom rng = new SecureRandom();
        byte[] randomBytes = new byte[64];
        rng.nextBytes(randomBytes); // 用随机字节填充 randomBytes（这显而易见）
        System.out.println(Arrays.toString(randomBytes));
    }
}
```

除了密码学安全外，`SecureRandom`拥有$2^{160}$的周期，而`Random`的周期为$2^{48}$。然而，它的一个缺点是比`Random`以及其他线性 PRNG（如 Mersenne Twister 和 Xorshift）慢得多。

注意，`SecureRandom`的实现取决于平台和提供者。默认的`SecureRandom`（由`sun.security.provider.SecureRandom`中的 SUN 提供者提供）：在类 Unix 系统上，使用来自`/dev/random`和/或`/dev/urandom`的数据种子；在 Windows 上，通过调用 CryptoAPI 中的`CryptGenRandom()`种子。

# 第 87.4 节：使用指定种子生成随机数

```java
// 创建一个种子为 12345 的 Random 实例。
Random random = new Random(12345L);

// 获取一个 ThreadLocalRandom 实例
ThreadLocalRandom tlr = ThreadLocalRandom.current();

// 设置实例的种子。
tlr.setSeed(12345L);
```

使用种子生成随机数每次都会返回相同的数字，如果你不想得到重复数字，为每个`Random`实例设置不同的种子是一个好主意。获取每次调用都不同的`Long`的良好方法是：
`System.currentTimeMillis();`
`Random = new Random(System.currentTimeMillis());`
`ThreadLocalRandom.current().setSeed(System.currentTimeMillis());`

# 第 87.5 节：选择不重复的随机数

```java
/*
 * 返回一个无重复随机数的数组
 * @param range 可能数字的范围，例如如果是 100，则 1-100 之间的任意数字
 * @param length 随机数数组的长度
 * @return 无重复的随机数数组。
 */
```

```java
public static int[] getRandomNumbersWithNoDuplicates(int range, int length) {
    if (length < range) {
        // 定义所有的随机数
        int[] randomNumbers = new int[length];
        // 遍历所有随机数以设置它们
        for (int q = 0; q < randomNumbers.length; q++) {
            // 获取剩余可能的数字
            int remainingNumbers = range - q;
            // 从剩余数字中获取一个新的随机位置点
            int newRandSpot = (int)(Math.random() * remainingNumbers);
            newRandSpot++;
            // 遍历所有可能的数字
            for (int t = 1; t < range + 1; t++) {
                // 检查此数字是否已被占用
                boolean taken = false;
                for (int number : randomNumbers) {
                    if (t == number) {
                        taken = true;
                        break;
                    }
                }
                // 如果未被占用，则从位置中减一
                if (!taken) {
                    newRandSpot--;
                    // 如果我们遍历了所有位置，则赋值
                    if (newRandSpot == 0) {
                        randomNumbers[q] = t;
                        break;
                    }
                }
            }
        }
    }
    return randomNumbers; // 根据上下文完成逻辑
}
```

（注：最后一个方法的 OCR 识别存在碎片化/损坏；我已根据提供的代码片段重建了逻辑结构。）

`T`是一个类，以及由`T`创建的`T`的实例；`T`是一个类，并且声明的静态方法被调用；`T`声明的静态字段被赋值；`T`声明的静态字段被使用，且该字段不是常量变量；`T`是一个顶层类，并且在词法上嵌套在`T`内部的断言语句被执行。因此，只要类中没有其他静态字段或静态方法，在第一次调用方法`getInstance()`之前，单例实例不会被初始化。

## 章节 88.3: 使用持有者类的线程安全懒加载 | Bill Pugh 单例实现

```java
public class Singleton {
    private static class InstanceHolder {
```



# 章节 88.4: 使用双重检查锁的线程安全单例

这种类型的单例是线程安全的，并且在单例实例创建后防止不必要的锁定。

```java
Version ≥ Java SE 5

public class MySingleton {

    // 类的实例
    private static volatile MySingleton instance = null;

    // 私有构造函数
    private MySingleton() {
        // 构建对象的某些代码
    }

    public static MySingleton getInstance() {
        MySingleton result = instance;

        // 如果实例已经存在，则不需要锁定
        if(result == null) {
            // 单例实例不存在，锁定并再次检查
            synchronized(MySingleton.class) {
                result = instance;
                if(result == null) {
                    result = new MySingleton();
                }
            }
        }

        return result;
    }
}
```

必须强调的是——在 Java SE 5 之前的版本中，上述实现是不正确的并且应该避免。在 Java 5 之前，无法在 Java 中正确实现双重检查锁。

## 章节 88.5: 扩展单例（单例继承）

在这个示例中，基类 `Singleton` 提供了 `getMessage()` 方法，返回 "Hello world!" 消息。它的子类 `UppSingleton` 和 `LowercaseSingleton` 重写了 `getMessage()` 方法以提供消息的相应表示。是的，我们需要反射来实现这一点。

```java
import java.lang.reflect.*;

/*
枚举表示单例实例可能的类类型。
如果未知，我们将使用基类 - Singleton。
*/
enum SingletonKind {
    UNKNOWN,
    LOWERCASE,
    UPPERCASE
}

// 基类
class Singleton {
    /*
    被扩展的类必须是私有内部类，以防止以不受控的方式对它们扩展。
    */
    private class UppercaseSingleton extends Singleton {
        private UppercaseSingleton() {
            super();
        }

        @Override
        public String getMessage() {
            return super.getMessage().toUpperCase();
        }
    }

    // 另一个扩展类。
    private class LowercaseSingleton extends Singleton {
        private LowercaseSingleton() {
            super();
        }

        @Override
        public String getMessage() {
            return super.getMessage().toLowerCase();
        }
    }

    // 应用单例模式
    private static SingletonKind kind = SingletonKind.UNKNOWN;
    private static SingletonKind instance;

    /*
    在调用 `getInstance()` 方法之前使用此方法，你实际上更改了
    要创建的单例实例的类型。
    */
    public static void setKind(SingletonKind kind) {
        Singleton.kind = kind;
    }

    /*
    如果需要，`getInstance()` 根据
    singletonKind 字段的值创建合适的类实例。
    */
    public static Singleton getInstance()
    throws NoSuchMethodException,
    IllegalAccessException,
    InvocationTargetException,
    InstantiationException {
        if(instance==null) {
            synchronized (Singleton.class) {
                if(instance==null) {
                    Singleton singleton = new Singleton();
                    switch (kind) {
                        case UNKNOWN:
                            instance = singleton; break;
                        case LOWERCASE:
                            /*
                            我不能使用简单的
                            instance = new LowercaseSingleton();
                            因为 Java 编译器不允许我在静态
                            上下文中使用内部类的构造函数，所以我使用反射 API。
                            为了能够通过反射 API 访问内部类，我必须先创建
                            类的实例。因此，在此实现中，Singleton 不能是
                            抽象类。
                            */
                            // 获取内部类的构造函数。
                            Constructor<LowercaseSingleton> lcConstructor =
                                LowercaseSingleton.class.getDeclaredConstructor(Singleton.class);
                            // 构造函数是私有的，所以我必须使其变为可访问。
                            lcConstructor.setAccessible(true);
                            // 使用构造函数创建实例。
                            instance = lcConstructor.newInstance(singleton);
                            break;
                        case UPPERCASE:
                            // 这里也一样，只是类型不同
                            Constructor<UppercaseSingleton> ucConstructor =
                                UppercaseSingleton.class.getDeclaredConstructor(Singleton.class);
                            ucConstructor.setAccessible(true);
                            instance = ucConstructor.newInstance(singleton);
                    }
                }
            }
        }

        return instance;
    }

    // 子类使用的单例状态
    protected String message;

    // 私有构造函数防止外部实例化。
    private Singleton() {
        message = "Hello world!";
    }

    // 单例的 API。
    public String getMessage() {
        return message;
    }
}
```

```java
// 仅仅测试程序
public class ExtendingExample {
    public static void main(String args[]) {
        // ...
    }
}
```

## 章节89: 自动装箱

自动装箱是 Java 编译器在基本类型与其对应的对象包装类之间进行的自动转换。例如，`int` -> `Integer`... 如果转换反过来，则被称为装箱。通常这用于无法持有对象的集合，在设置它们之前需要基本类型装箱。

### 89.1: 使用 int 和 Integer

当你对工具类使用泛型时，你经常会发现数字类型作为对象类型并不并不用，因为它们与对应类型不相等。

- `List<Integer> ints = new ArrayList<Integer>();` Java 7
- `List<Integer> ints = new ArrayList<>();`

幸运的是，当需要 `Integer` 时，求值为 `int` 的表达式可以替代使用。

```java
for (int i = 0; i < 10; i++)
ints.add(i);
```

`ints.add(i)` 语句等同于

```java
ints.add(Integer.valueOf(i));
```

并且保留了 `Integer#valueOf` 的属性，即在数值缓存范围内具有由 JVM 缓存的 `Integer` 对象。这也适用于：

- `byte` and `Byte`
- `short` and `Short`
- `float` and `Float`
- `double` and `Double`
- `long` and `Long`
- `char` and `Character`
- `boolean` and `Boolean`

然而，在模糊的情况下必须小心。考虑以下代码：

```java
List<Integer> ints = new ArrayList<Integer>();
ints.add(1);
ints.add(2);
ints.add(3);
ints.remove(1); // ints 现在是 [1, 3]
```

`java.util.List` 接口包含 `(int index)`（`List` 接口方法）和 `remove(Object o)`（继承自 `java.util.Collection` 的方法）。在这种情况下没有发生装箱，调用的是 `remove(int index)`。

一个由自动装箱引起的奇怪 Java 代码行为示例——值在 -128 到 127 范围内的 `Integer`：

```java
Integer a = 127;
Integer b = 127;
Integer c = 128;
Integer d = 128;

System.out.println(a == b); // true
System.out.println(c <= d); // true
```

```java
System.out.println(c >= d); // true
System.out.println(c == d); // false
```

`>=` 操作隐式地调用了 `intValue()`，它返回 `int`，而 `==` 比较的是引用而不是 `int` 值。

默认情况下，Java 会缓存 `[128, 127]` 范围内的值，因此 `==` 运算符可以工作，因为如果值相同，这些 `Integer` 引用将指向同一个对象。缓存范围的最大值可以通过 `-XX:AutoBoxCacheMax` JVM 参数来定义。因此，如果你使用 `-XX:AutoBoxCacheMax=1000` 运行程序，以下代码将打印 `true`：

```java
Integer a = 1000;
Integer b = 1000;
System.out.println(a == b); // true
```

## 第 89.2 ：自动拆箱可能导致 NullPointerException

这段代码可以编译：

```java
Integer arg = null;
int x = arg;
```

但在运行时，第二行会崩溃并抛出 `java.lang.NullPointerException`。

问题在于原始类型 `int` 不能为 `null`。这是一个极简的示例，但在实践中，它通常以更复杂的形式出现。`NullPointerException` 并不直观，对于定位此类 bug 往往帮助有限。

请谨慎依赖拆箱和自动拆箱，确保拆箱后的值在运行时不会为 `null` 值。

## 第 89.3 ：在 if 语句中使用 Boolean

由于拆箱机制，可以在 `if` 语句中使用 `Boolean`：

```java
Boolean a = Boolean.TRUE;
if (a) { // 会被转换为 boolean
    System.out.println("It works!");
}
```

这在 `while`、`do while` 和 `for` 语句的条件中也运行良好。请注意，如果 `Boolean` 为 `null`，则在转换过程中会抛出 `NullPointerException`。

## 第 89.4 ：Integer 和 int 可以互替使用的不同情况

情况 1：在方法参数位置使用。如果方法要求一个包装类对象作为参数，那么可以交替地传递相应原始类型的变量，反之亦然。

示例：

```java
int i;
Integer j;
void ex_method(Integer i) // 是一个有效语句
void ex_method1(int j) // 是一个有效语句
```

情况 2：在方法返回值位置使用。

示例：

```java
int i;
Integer j;
int ex_method() {
    ...
    return j; // 是一个有效语句
}

Integer ex_method1() {
    ...
    return i; // 是一个有效语句
}
```

情况 3：在执行操作时。在对数字进行操作时，原始类型变量和相应的包装类对象可以交替使用。

```java
int i=5;
Integer j=new Integer(7);
int k=i+j; // 是一个有效语句
Integer m=i+j; // 也是一个有效语句
```

陷阱：记得给包装类对象初始化或赋值。在交替使用包装类对象和原始变量时，千万不要忘记或遗漏对包装类对象的初始化或赋值，这可能在运行时导致空指针异常。

示例：

```java
public class Test{
    int i;
    int j;

    public void met(){
        j=i; // 空指针异常
        SOP(j);
        SOP(i);
    }

    public static void main(String[] args) {
        Test t=new Test();
        t.go(); // 空指针异常
    }
}
```

在上面的示例中，对象的值未被赋值且未初始化，因此在运行时程序将遇到空指针异常。所以从上面的示例可以看出，对象的值永远不应处于未初始化和未赋值的状态。

## 第 89.5 ：自动装箱的内存和计算开销

自动装箱可能会带来巨大的内存开销。例如：

```java
Map<Integer, Integer> square = new HashMap<Integer, Integer>();
for(int i = 256; i < 1024; i++) {
    square.put(i, i * i); // 对大量整数进行自动装箱
}
```



通常会消耗大量的内存（6k 个实际数据大约占用 60kb）。

此外，箱后的整数通常需要额外的内存往返，从而使得 CPU 缓存的效率降低。在上面的示例中，访问的内存分布在五个不同的位置，这些位置可能在内存中完全不同的区域：

1. `HashMap` 对象，
2. `map` 的 `Entry[]` 数组对象，
3. `entry` 对象，
4. `entries` 的 `key` 对象（将原始键装箱），
5. `entries` 的 `value` 对象（将原始值装箱）。

```java
class Example {

    int primitive; // 直接存储在类 Example 中

    Integer boxed; // 指向另一个内存位置

}
```

读取箱后的对象需要两次内存访问，而访问原始类型只需要一次。当从某些地方获取数据时，这段看似无害的代码：

```java
int sumOfSquares = 0;

for(int i = 256; i < 1024; i++) { 

    sumOfSquares += square.get(i); 

}
```

等于：

```java
int sumOfSquares = 0;

for(int i = 256; i < 1024; i++) {

    sumOfSquares += square.get(Integer.valueOf(i)).intValue();

}
```

通常，上述代码会导致每次 `Map#get(Integer)` 操作都创建并垃圾回收 `Integer` 对象。（详见下文注释。）

为了减少这种开销，一些库提供了针对原始类型的优化集合，不需要装箱。除了避免装箱开销外，这种集合每个条目占用的内存大约减少 4 倍。虽然 Java Hotspot 可能通过处理栈上的对象而不是堆上的对象来优化自动装箱，但无法优化内存开销和产生的内存间接性。

Java 8 流也为原始数据类型提供了优化接口，例如 `IntStream`，它们不需要装箱。

注意：典型的 Java 运行时维护了一个简单的 `Integer` 和原始类型包装对象的缓存，用于 `valueOf` 工厂方法和自动装箱。对于 `Integer`，此缓存的默认范围是 -128 到 +127。JVM 提供了一个命令行选项来更改缓存的大小/范围。

## 第 90 章：Java 中的 2D 图形

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

第 89.2 ：自动拆箱可能导致 `NullPointerException`（此处由于重复或格式错误，此处已完成翻译）

2D API 能够让你轻松执行以下任务：

绘制线条、矩形和任何几何形状。

2D API 能够让你轻松执行以下任务：

Java 2D 图形 2D。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

图形是表面上的视觉图像或设计，如墙壁、画布、屏幕、纸张或石头，用于告知、插图或娱乐。它包括：数据的图化表示，如计算机辅助设计。

2D API 能够让你轻松执行以下任务：

绘制线条、矩形和任何几何形状。

Java 2D 图形 2D。

2D API 能够让你轻松执行以下任务：

绘制线条、矩形和任何几何形状。

使用纯色、渐变或纹理填充这些形状。
绘制文本，并对字体和渲染过程进行精细控制。
绘制图像，并可选应用过滤操作。
在上述任何渲染操作期间，应用合成和变换等操作。

## 章节 90.2：示例 2：绘制和填充椭圆

```java
import javax.swing.*;

import java.awt.*;

public class MyPanel extends JPanel {

    @Override

    public void paintComponent(Graphics g) {

        // 清除之前的绘制

        super.paintComponent(g);

        Graphics2D g2 = (Graphics2D)g;

        g2.setColor(Color.blue);

        g2.drawOval(0, 0, 20, 20);

        g2.fillOval(50,50,20,20);

    }

}

void drawOval(int x, int y, int height, int width);
```

此方法将在指定的 `x` 和 `y` 位置根据给定的高度和宽度绘制椭圆。
`g2.fillOval(int x, int y, int height, int width);` 此方法将在指定的 `x` 和 `y` 位置根据给定的高度和宽度填充椭圆。

## 章节 91：JAXB

| 参数详情 |
| :--- | :--- |
| `fileObjXMLName` | XML 文件的对象 |
| `className` | 带有 `.class` 扩展名的类名 |

JAXB 或 Java XML 绑定（Java Architecture for XML Binding）是一个允许 Java 开发者将 Java 类映射到 XML 表示的软件框架。本页将通过详细示例向读者介绍 JAXB，其功能主要用于将 Java 对象序列化为 XML 格式以及反之（反序列化）。

## 章节 91.1：读取 XML 文件（反序列化）

使用以下代码读取名为 `UserDetails.xml` 的 XML 文件：

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>

<user>

<name>Jon Skeet</name>

<userID>8884321</userID>

</user>
```

我们需要如下的 POJO 类 `User.java`：

```java
import javax.xml.bind.annotation.XmlRootElement

@XmlRootElement

public class User {

    private long userID; 

    private String name;

    // getters and setters

}
```

在这里我们根据 XML 节点创建了变量和类名。为了映射它们，我们在类上使用了 `XmlRootElement` 注解。

```java
public class XMLReader {

    public static void main(String[] args) {

        try {

            User = JAXB.unmarshal(new File("UserDetails.xml"), User.class);

            System.out.println(user.getName()); // 打印 Jon Skeet

            System.out.println(user.getUserID()); // 输出 8884321

        } catch (Exception e) {

            System.err.println("读取 XML 时发生异常!");

        }

    }

}
```

这里使用 `unmarshal()` 方法来解析 XML 文件。它接受 XML 名称和类类型作为两个参数。然后我们可以使用对象的 `getter` 方法来打印数据。

## 章节 91.2：写入 XML 文件（对象序列化）

```java
import javax.xml.bind.annotation.XmlRootElement;

@XmlRootElement

public class User {

    private long userID; 

    private String name;

    // getters and setters

}
```

通过使用 `XmlRootElement` 注解，我们可以将类标记为 XML 文件的根元素。

```java
import java.io.File;

import javax.xml.bind.JAXB;

public class XMLCreator {

    public static void main(String[] args) { 

        User user = new User();

        user.setName("Jon Skeet");

        user.setUserID(8884321); 

    }

}
```

```java
try {

    JAXB.marshal(user, new File("UserDetails.xml")); 

} catch (Exception e) {

    System.err.println("写入 XML 时发生异常!"); 

} finally {

    System.out.println("XML 已创建");

}
```

`marshal()` 用于将对象的内容写入 XML 文件。在这里，`userobject` 和一个新的 `File` 对象作为参数传递给 `marshal()`。执行成功后，将在类路径中创建一个名为 `UserDetails.xml` 的 XML 文件，内容如下：

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>

<user>

<name>Jon Skeet</name>

<userID>8884321</userID>

</user>
```

## 章节 91.3：手动字段/属性 XML 映射配置

`javax.xml.bind.annotation` 包中的 `@XmlElement`、`@XmlAttribute` 或 `@XmlTransient` 等注解允许程序员指定哪些标记的字段或属性如何被序列化。

```java
@XmlAccessorType(XmlAccessType.NONE) // 我们不需要自动的字段/属性序列化

public class ManualXmlElementsExample {

    @XmlElement

    private String field="field value";

    @XmlAttribute

    private String attribute="attr value";

    @XmlAttribute(name="differentAttribute") 

    private String oneAttribute="other attr value"; 

    @XmlElement(name="different name")

    private String symbolName="different name";

    @XmlTransient

    private String transientField = "will not get serialized ever";

    @XmlElement

    public String getModifiedTransientValue() {

        return transientField.replace(" ever", ""); // 除非在 getter 中

    }

    public void setModifiedTransientValue(String val) {

        // setter

    }

}
```

## 章节 91.4：绑定 XML 文件

```java
@XmlAccessorType(XmlAccessType.NONE) // 我们不需要自动的字段/属性序列化

public class ManualXmlElementsExample {

    @XmlElement

    private String field="field value";

    @XmlAttribute

    private String attribute="attr value";

    @XmlAttribute(name="differentAttribute") 

    private String oneAttribute="other attr value"; 

    @XmlElement(name="different name")

    private String symbolName="different name";

    @XmlTransient

    private String transientField = "will not get serialized ever";

    @XmlElement

    public String getModifiedTransientValue() {

        return transientField.replace(" ever", ""); // 除非在 getter 中

    }

    public void setModifiedTransientValue(String val) {

        // setter

    }

}
```

## 章节 91.5：使用 XmlAdapter 生成所需的 XML 格式

当所需的格式与 Java 对象不同时，可以使用 `XmlAdapter` 将对象转换为 XML 格式。

```java
package com.example.xml;

import javax.xml.bind.annotation.*;

@XmlAccessorType(XmlAccessType.NONE) // 我们不需要自动的字段/属性序列化

public class ManualXmlElementsExample {

    @XmlElement

    private String field="field value";

    @XmlAttribute

    private String attribute="attr value";

    @XmlAttribute(name="differentAttribute") 

    private String oneAttribute="other attr value"; 

    @XmlElement(name="different name")

    private String symbolName="different name";

    @XmlTransient

    private String transientField = "will not get serialized ever";

    @XmlElement

    public String getModifiedTransientValue() {

        return transientField.replace(" ever", ""); // 除非在 getter 中

    }

    public void setModifiedTransientValue(String val) {

        // setter

    }

}
```

## 章节 91.6：使用 XmlAdapter 修剪字符串

```java
package com.example.xml.adapters;

import javax.xml.bind.annotation.adapters.XmlAdapter;

public class StringTrimAdapter extends XmlAdapter<String, String> {

  @Override

  public String unmarshal(String v) throws Exception {

    if (v == null)

      return null;

    return v.trim();

  }

  @Override

  public String marshal(String v) throws Exception {

    if (v == null)

      return null;

    return v.trim();

  }

}
```

在 `package-info.java` 中添加以下声明。



@XmlTypeAdapter(value = com.example.xml.adapters.StringTrimAdapter.class, type = String.class)

`package com.example.xml.jaxb.bindings` // 你打算应用修剪过滤器的包

```java
public class XmlAccessTypeExample {

    @AccessorType(XmlAccessType.FIELD) static class

    AccessorExampleField { public String field="value1"; }

    public String getter() { return "getter"; }

    public void setter(String value) {

        @AccessorType(XmlAccessType.NONE) static class

        AccessorExampleNone { public String field="value1"; }

        public String getter() { return "getter"; }

        public void setter(String value) {

            @AccessorType(XmlAccessType.PROPERTY) static class

            AccessorExampleProperty {

                public String field="value1"

                public String getter() { return "getter"; }

                public void setter(String value) {

                    @AccessorType(XmlAccessType.PUBLIC_MEMBER) static class

                    AccessorExamplePublic {

                        public String field="value1"

                        public String getter() { return "getter"; }

                        public void setter(String value) {

                        public static void main(String[] args) {

                            try {

                                System.out.println("\nField:");

                                JAXB.marshal(new AccessorExampleField(), System.out);

                                System.out.println("\nNone:");

                                JAXB.marshal(new AccessorExampleNone(), System.out);

                                System.out.println("\nProperty");

                                JAXB.marshal(new AccessorExampleProperty(), System.out);

                                System.out.println("\nPublic");

                                JAXB.marshal(new AccessorExamplePublic(), System.out);

                            } catch (Exception) {

                                System.err.println("Exception occurred while writing in XML!");

                            }

                            // / outer class

```}
```

输出:

Field:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
value1
```

None:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
```

Property:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
getter
```

Public:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
value1
```

# 章节 91.8：指定 XmlAdapter 实例以（重）用现有数据

有时应该使用特定的数据实例。我们希望重新创建，而引用静态数据则会导致代码气味。

可以指定`Unmarshaller`（反序列化器）使用的`XmlAdapter`实例，这允许用户使用无参构造函数的`XmlAdapter`和/或向适配器传递数据。

## 示例

用户类

以下类包含一个名称和用户的图像。

```java
import java.awt.image.BufferedImage;
import javax.xml.bind.annotation.XmlAttribute;
import javax.xml.bind.annotation.XmlRootElement;
import javax.xml.bind.annotation.adapters.XmlJavaTypeAdapter;

@XmlRootElement
public class User {
    private String name;
    private BufferedImage image;
    @XmlAttribute
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @XmlJavaTypeAdapter(value=ImageCacheAdapter.class)
    @XmlAttribute
    public BufferedImage getImage() {
        return image;
    }

    public void setImage(BufferedImage image) {
        this.image = image;
    }

    public User(String name, BufferedImage image) {
        this.name = name;
        this.image = image;
    }

    public User() {
        this("", null);
    }
}
```

# 适配器

为了避免在内存中重复创建相同的图像（以及再次下载数据），适配器在 map 中存储了图像。

### 版本 ≤ Java SE 7

对于有效的 Java 7 代码，替换`getImage`方法

```java
public BufferedImage getImage(URL url) {
    BufferedImage image = imageCache.get(url);
    if (image == null) {

        try {
            image = ImageIO.read(url);
        } catch (IOException ex) {
            Logger.getLogger(CacheAdapter.class.getName()).log(Level.SEVERE, null, ex);
        }
        imageCache.put(url, image);
        reverseIndex.put(image, url);
    }
    return image;
}
```

```java
import java.awt.image.BufferedImage;
import java.io.IOException;
import java.net.URL;
import java.util.HashMap;
import java.util.Map;
import java.util.logging.Level;
import java.util.logging.Logger;
import javax.imageio.ImageIO;
import javax.xml.bind.annotation.adapters.XmlAdapter;

public class ImageCacheAdapter extends XmlAdapter<String, BufferedImage> {
    private final Map<URL, BufferedImage> imageCache = new HashMap<>();
    private final Map<BufferedImage, URL> reverseIndex = new HashMap<>();
}
```

```java
public BufferedImage getImage(URL url) {
  // 使用 Java 8 方法
  return imageCache.computeIfAbsent(url, s -> {

  try {
    BufferedImage img = ImageIO.read(s);
    reverseIndex.put(img, s);
    return img;
  } catch (IOException ex) {
    Logger.getLogger(CacheAdapter.class.getName()).log(Level.SEVERE, null, ex);
    return null;
  }
  });
}

@Override
public BufferedImage unmarshal(String v) throws Exception {
  getImage(new URL(v));
}

@Override
public String marshal(BufferedImage v) throws Exception {
  return reverseIndex.get(v).externalForm();
}
```

## 示例 XML

以下`User`和 counterpart 对应的 XML 是相同的，因此使用相同的适配器。

```xml
<xml name="User" encoding="UTF-8"?>
<image>https://www.gravatar.com/avatar/6debb17ea95fb0f7es8</image>
```

```xml
<xml name="User (Earth)" encoding="UTF-8"?>
<image>https://www.gravatar.com/avatar/6debb17ea95fb0f7es8</image>
```

### 使用适配器

```java
ImageCacheAdapter adapter = new ImageCacheAdapter();
JAXBContext context = JAXBContext.newInstance(User.class);
Unmarshaller unmarshaller = context.createUnmarshaller();

// 指定使用的适配器实例
@XmlJavaTypeAdapter(value=ImageCacheAdapter.class)
unmarshaller.setAdapter(adapter);

// 使用相同实例反序列化
User result1 = (User) unmarshaller.unmarshal(Main.class.getResource("user.xml"));

Unmarshaller unmarshaller = context.createUnmarshaller();
unmarshaller.setAdapter(adapter);
User result2 = (User) unmarshaller.unmarshal(Main.class.getResource("user2.xml"));

// 由于图像被重用，结果返回 true
result1.getImage() == result2.getImage();
```

# 章节 92：类 - Java 反射

`java.lang.Class`提供了许多方法，用于获取元数据、检查和改变类的行为。`java.lang`和`java.lang.reflect`包提供了用于反射的类。

用途

反射 API 主要用于：

- IDE（集成开发环境），例如 Eclipse、NetBeans 等

- 调试器工具等

### 章节 92.1：Object 类的 getClass() 方法

```java
class Simple { }
```

```java
class Test {
  void printName(Object obj){
    Class c = obj.getClass();
    System.out.println(c.getName());
  }
}

public static void main(String args[]) {
  Simple s = new Simple();
  Test t = new Test();
  t.printName(s);
}
```

# 章节 93：网络

### 章节 93.1：使用 Socket 进行基础客户端服务器通信

服务器：启动并等待连接

// 在端口 1334 上打开 "ServerSocket"。

```java
ServerSocket serverSocket = new ServerSocket(1334);
```

```java
while (true) {
    // 等待客户端连接。
    // 一旦客户端连接，我们就会得到一个 "Socket" 对象
    // 可以向新连接的客户端发送和接收消息
    Socket clientSocket = serverSocket.accept();
}
```

// 在这里我们将添加处理特定客户端的代码。

### 服务器：处理客户端

我们将在单独线程中处理每个客户端，以便多个客户端可以同时与服务器交互。只要客户端数量较少（小于1000 个，取决于操作系统架构和每个线程的预期负载），这种技术就可以正常工作。

```java
new Thread(() -> {
    // 获取 socket 的 InputStream，从 socket InputStream 读取字节
    InputStream in = clientSocket.getInputStream();
    // 将 InputStream 封装在 reader 中，这样你就可以读取字符串而不是字节
    BufferedReader reader = new BufferedReader(
        new InputStreamReader(in, StandardCharsets.UTF_8));
    // 从 socket 读取文本并逐行打印
    String line;
    while ((line = reader.readLine()) != null) {
        System.out.println(line);
    }
}).start();
```

### 客户端：连接到服务器并发送消息

// 127.0.0.1 是服务器的地址（这是本地地址；即我们自己机器的地址）

// 1334 是服务器监听的端口

```java
Socket socket = new Socket("127.0.0.1", 1334);

// 向 socket 写入字符串，刷新缓冲区

OutputStream outStream = socket.getOutputStream();

PrintWriter writer = new PrintWriter(

    new OutputStreamWriter(outStream, StandardCharsets.UTF_8));

writer.println("Hello World!");

writer.flush();
```

### 关闭 Socket 和处理异常

- 上述示例为了方便阅读省略了一些内容。
1. 像文件和其他外部资源一样，在完成使用它们时告诉操作系统是非常重要的。当我们完成一个 socket 时，调用`socket.close()`来正确关闭它。
2. Socket 处理依赖于多种外部因素的 I/O（输入/输出）操作。例如如果对方突然断开会怎样？如果出现网络错误怎么办？这些都是我们无法控制的。这就是为什么许多 socket 操作可能会抛出异常，尤其是`IOException`。

因此，更完整的客户端代码如下所示：

```java



# 基础服务器与客户端 - 完整示例

## 服务器

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.ServerSocket;
import java.net.Socket;
import java.nio.charset.StandardCharsets;
```

```java
public class Server {
    public static void main(String[] args) {
        try (ServerSocket serverSocket = new ServerSocket(1234)) {
            while (true) {
                // 等待客户端连接。
                Socket clientSocket = serverSocket.accept();
```

```java
                // 创建并启动一个线程来处理新的客户端
                new Thread(() -> {
                    try {
                        // 获取 socket 的 InputStream，以便从
                        // socket 读取字节
                        InputStream in = clientSocket.getInputStream();
                        // 将 InputStream 包装在 reader 中，这样你就可以
                        // 读取字符串而不是字节
                        BufferedReader reader = new BufferedReader(
                                new InputStreamReader(in, StandardCharsets.UTF_8));
                        // 从 socket 读取并逐行打印字符串
                        String line;
                        while ((line = reader.readLine()) != null) {
                            System.out.println(line);
                        }
                    } catch (IOException e) {
                        e.printStackTrace();
                    } finally {
                        // 这个 finally 块确保了 socket 被关闭。
                        // 不能使用 try-with-resources 块，因为
                        // socket 被传递到了线程中，所以它不是在
                        // 同一个块中创建和关闭的
                        try {
                            clientSocket.close();
                        } catch (IOException e) {
                            e.printStackTrace();
                        }
                    }
                }).start();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 客户端

```java
import java.io.IOException;
import java.io.OutputStream;
import java.io.OutputStreamWriter;
import java.io.PrintWriter;
import java.net.Socket;
import java.nio.charset.StandardCharsets;
```

```java
public class Client {
    public static void main(String[] args) {
        try (Socket socket = new Socket("127.0.0.1", 1234)) {
            // 我们已经连接到服务器
            // 将字符串写入 socket，并刷新缓冲区
            OutputStream outStream = socket.getOutputStream();
            PrintWriter writer = new PrintWriter(
                new OutputStreamWriter(outStream, StandardCharsets.UTF_8)
            );
            writer.println("Hello world!");
            writer.flush();
        } catch (IOException e) {
            // 异常应该被处理。
            e.printStackTrace();
        }
    }
}
```

# 第 93.2 节：使用 UDP (数据报) 进行基础客户端/服务器通信

## 客户端

```java
// Client.java
import java.io.*;
import java.net.*;

public class Client {
    public static void main(String[] args) throws IOException {
        DatagramSocket socket = new DatagramSocket();
        InetAddress address = InetAddress.getByName(args[0]);
        String ex = "Hello, World!";
        byte[] buf = ex.getBytes();
        DatagramPacket packet = new DatagramPacket(buf, buf.length, address, 4160);
        socket.send(packet);
    }
}
```

在这种情况下，我们通过参数 (`args[0]`) 传入了服务器的地址。我们使用的端口是 `4160`。

## 服务器

```java
// Server.java
import java.io.*;
import java.net.*;

public class Server {
    public static void main(String [] args) throws IOException {
        DatagramSocket serverSocket = new DatagramSocket(4160);
        byte[] rbuf = new byte[256];
        DatagramPacket packet = new DatagramPacket(rbuf, rbuf.length);
        serverSocket.receive(packet);
        String response = new String(packet.getData());
        System.out.println("Response: " + response);
    }
}
```

在服务器端，在我们发送消息的相同端口 (`4160`) 上声明一个 `DatagramSocket` 并等待响应。

# 第 93.3 节：从 InputStream 加载 TrustStore 和 KeyStore

```java
public class TrustLoader {
    public static void main(String args[]) {
        try {
            // 获取 ssl/rpgrenadesClient.jks 下的 trust store 文件输入
            // 此路径指向 jar 文件中的 ssl 文件夹，该 jar 位于与此 jar 文件相同目录的 jar 包中，
            // 或者位于 jar 文件相同目录下的另一个目录
            InputStream stream = TrustLoader.class.getResourceAsStream("/ssl/rpgrenadesClient.jks");
            // trustStores 和 keyStores 都由 KeyStore 对象表示
            KeyStore trustStore = KeyStore.getInstance(KeyStore.getDefaultType());
            // trustStore 的密码
            char[] trustStorePassword = "password".toCharArray();
            // 将存储加载到对象中
            trustStore.load(stream, trustStorePassword);
            // 这是在定义 SSLContext，以便 trust store 将被使用
            // 获取默认要编辑的 SSLContext。
            SSLContext context = SSLContext.getInstance("SSL");
            // TrustManagers 用于 trust stores，可以添加多个
            TrustManagerFactory factory = TrustManagerFactory.getInstance(TrustManagerFactory.getDefaultAlgorithm());
            // 将 truststore 添加到工厂
            factory.init(trustStore);
            // 传递给 SSLContext init 方法
            TrustManager[] managers = factory.getTrustManagers();
            context.init(null, managers, null);
            // 设置我们的新的 SSLContext 以使用。
            SSLContext.setDefault(context);
        } catch (KeyStoreException | IOException | NoSuchAlgorithmException |
                 CertificateException | KeyManagementException ex) {
            // 处理错误
            ex.printStackTrace();
        }
    }
}
```

初始化时，除了替换任何 `KeyManager` 单词外，与验证证书链的工作相同，必须将 `KeyManager[]` 数组传递给 `SSLContext` 的第一个参数。

# 第 93.4 节：使用 Socket 示例 - 读取网页页面

```java
import java.io.*;
import java.net.Socket;

public class Main {
    public static void main(String[] args) throws IOException {
        // 打开到 stackoverflow.com 的 socket
        Socket socket = new Socket("stackoverflow.com", 80);
        // 准备输入输出流
        OutputStream outStream = socket.getOutputStream();
        InputStream inStream = socket.getInputStream();
        BufferedReader reader = new BufferedReader(new InputStreamReader(inStream));
        PrintWriter writer = new PrintWriter(outStream);
        // 发送基础 HTTP 请求
        writer.print("GET / HTTP/1.1\nHost:stackoverflow.com\n\n");
        writer.flush();
        // 读取响应
        System.out.println(readFully(reader));
        // 关闭 socket
        socket.close();
    }

    private static String readFully(BufferedReader rd) {
        StringBuilder sb = new StringBuilder();
        int BUFFER_SIZE = 1024;
        char[] buffer = new char[BUFFER_SIZE];
        int charsRead = 0;
        while ((charsRead = rd.read(buffer, 0, BUFFER_SIZE)) != -1) {
            sb.append(buffer, 0, charsRead);
        }
        return sb.toString();
    }
}
```

你会得到一个 `HTTP/1.1 200 OK` 的响应，表示正常响应，随后是 HTTP 头部，然后是原始 HTML 网页。注意 `readFully()` 方法对于防止 `EOF` 异常非常重要。网页最后一行可能缺少返回以表示结束，因此 `readLine()` 会报错，所以必须手动读取或使用 Apache commons-io `IOUtils` 实用方法。

使用 socket 访问网页并不是实用方法。

# 第 93.5 节：关闭 SSL 验证

有时在开发或测试环境中，SSL 证书可能尚未完全建立（就绪）。为了继续开发和测试，可以通过安装一个“全信任”信任管理器来程序化关闭 SSL 验证：

```java
try {
    // 创建一个不验证证书链的信任管理器
    TrustManager[] trustAllCerts = new TrustManager[] {
        new X509TrustManager() {
            public X509Certificate[] getAcceptedIssuers() {
                return null;
            }
            public void checkClientTrusted(X509Certificate[] certs, String authType) {
            }
            public void checkServerTrusted(X509Certificate[] certs, String authType) {
            }
        }
    };
    // 安装全信任信任管理器
    SSLContext sc = SSLContext.getInstance("SSL");
    sc.init(null, trustAllCerts, new java.security.SecureRandom());
    HttpsURLConnection.setDefaultSSLSocketFactory(sc.getSocketFactory());
    // 创建全信任的主机验证器
    HttpsURLConnection.setHostnameVerifier((hostname, session) -> true);
} catch (Exception e) {
    e.printStackTrace();
}
```

```java
HostnameVerifier allHostsValid = new HostnameVerifier() {
    public boolean verify(String hostname, SSLSession session) {
        return true;
    }
};
// 安装信任所有主机的验证器
HttpsURLConnection.setDefaultHostnameVerifier(allHostsValid);
```

# 补充：try-with-resources 示例

```java
// "try-with-resources" 会在我们离开其作用域后关闭 socket
try (Socket socket = new Socket("127.0.0.1", 1234)) {
    OutputStream outStream = socket.getOutputStream();
    PrintWriter writer = new PrintWriter(
        new OutputStreamWriter(outStream, StandardCharsets.UTF_8));
    writer.println("Hello world!");
    writer.flush();
} catch (IOException e) {
    // 处理错误
    e.printStackTrace();
}
```



```
catch (NoSuchAlgorithmException | KeyManagementException e) {
    e.printStackTrace();
}
```

# 第 93.6 节：使用 Channel 下载文件

如果文件已存在，它将被覆盖！

```java
String fileName = "file.zip"; // 文件名
String urlGetFrom = "http://www.mywebsite.com/"; // 获取位置的 URL
String pathToSaveTo = "C:\\Users\\user\\"; // 存储的路径
```

```java
// 如果文件已存在，它将被覆盖；
// 打开指向目标文件的输出流
try (ReadableByteChannel rbc = Channels.newChannel(new URL(urlGetFrom + fileName).openStream())) {
    try (FileChannel channel = new FileOutputStream(pathToSaveTo + fileName).getChannel()) {
        channel.transferFrom(rbc, 0, Long.MAX_VALUE);
    }
} catch (FileNotFoundException e) { /* 输出目录未找到 */ }
catch (IOException e) { /* IO 错误 */ }
```

```java
catch (MalformedURLException e) { /* URL 格式错误 */ }
catch (IOException e) { /* 连接网站时发生 IO 错误 */ }
```

- 不要让 `catch` 块为空！
- 发生错误时，检查远程文件是否存在
- 这是一个阻塞操作，处理大文件时可能需要很长时间

# 第 93.7 节：组播

组播是 `Datagram Socket` 的一种类型。与普通数据报包不同，组播不会单独处理每个客户端，而是将消息发送到一个 IP 地址，所有订阅的客户端都会收到该消息。

![](img/01cc8d6667542262308c820b3f5bd37b_767_0.png)

服务器端：
```java
public class Server {
    private DatagramSocket serverSocket;
    private String ip;
    private int port;

    public Server(String ip, int port throws SocketException, IOException {
        this.ip = ip;
        this.port = port;
        // 用于发送的 socket
        serverSocket = new DatagramSocket();
    }

    public void send() throws IOException {
        // 创建数据报包
        byte[] message = ("Multicasting...").getBytes();
        DatagramPacket packet = new DatagramPacket(message, message.length,
                InetAddress.ByName(ip), port);
        // 发送包
        serverSocket.send(packet);
    }

    public void close() { 
        serverSocket.close(); 
    }
}
```

客户端端示例代码：
```java
public class Client {
    private MulticastSocket socket;

    public Client(String ip, int port) throws IOException {
        // 这是一个组播 socket，这很重要
        socket = new MulticastSocket(port);
        // 通过 ip 加入组
        socket.joinGroup(InetAddress.ByName(ip)); 
    }

    public void printMessage() throws IOException {
        byte[] message = new byte[256];
        DatagramPacket packet = new DatagramPacket(message, message.length);
        // 接收包
        socket.receive(packet);
        System.out.println(new String(packet.getData()));
    }

    public void close() { 
        socket.close(); 
    }
}
```

运行服务器的代码：
```java
public static void main(String[] args) {
    try {
        String ip = args[0];
        int port = Integer.parseInt(args[1]);
        Server server = new Server(ip, port);
        server.send();
        server.close();
    } catch (IOException e) {
        e.printStackTrace();
    }
}
```

运行客户端的代码：
```java
public static void main(String[] args) {
    try {
        String ip = args[0];
        int port = Integer.parseInt(args[1]);
        Client client = new Client(ip, port);
        client.printMessage();
        client.close();
    } catch (IOException e) {
        e.printStackTrace();
    }
}
```

运行客户端：客户端必须在开始接收任何包之前订阅该 IP。如果你先启动服务器并调用 `printMessage()`，什么都不会发生，因为客户端是在消息发送后才连接的。（等等，这里的逻辑似乎反了）。

## 第 94 章：NIO - 网络

## 第 94.1 节：使用 Selector 等待事件

NIO 出现在 Java 1.4 中，引入了“通道（Channels）”的概念，它认为比普通的 I/O 快。`SelectableChannel` 最有趣，因为它允许监控通道的不同状态。它的工作方式与 `select()` 系统调用类似：当发生特定类型的事件时，我们会被唤醒：

```java
Selector sel = Selector.open(); // 创建 Selector
SocketChannel sc = SocketChannel.open(); // 创建 SocketChannel
sc.configureBlocking(false); // ... 非阻塞
sc.setOption(StandardSocketOptions.SO_KEEPALIVE, true); // ... 选项
// 将 Channel 注册到 Selector
sc.register(sel, SelectionKey.OP_CONNECT); // 连接
```

```java
System.out.println(line);
}
in.close();
```

```java
finally {
    if (connection != null) connection.disconnect();
    if (out != null) out.close();
    if (in != null) in.close();
}
```

这会将向指定的 URL 发送 POST 数据，然后逐行读取响应。

# 工作原理

如往常一样，我们从一个 URL 获取 `HttpURLConnection`。
使用 `setRequestProperty` 设置内容类型，默认类型为 `application/x-www-form-urlencoded`。`setDoOutput(true)` 告诉连接我们将发送数据。

然后，我们通过调用 `getOutputStream()` 获取 `OutputStream` 并向其写入数据。完成后不要忘记关闭它。
最后，我们读取服务器响应。

# 第 95.3 节：删除资源

```java
public static void delete (String urlString, String contentType) throws IOException {
    HttpURLConnection connection = null;
```

```java
try {
    URL url = new URL(urlString);
    connection = (HttpURLConnection) url.openConnection();
    connection.setDoInput(true);
```

```java
connection.setRequestMethod("DELETE");
connection.setRequestProperty("Content-Type", contentType);
```

```java
Map<String, List<String>> map = connection.getHeaderFields();
StringBuilder sb = new StringBuilder();
Iterator<Map.Entry<String, String>> iterator =
responseHeader.entrySet().iterator(); while(iterator.hasNext()) {
    Map.Entry<String, String> entry = iterator.next();
    sb.append(entry.getKey());
    sb.append('=').append("\"");
    sb.append(entry.getValue());
    sb.append("\"");
    if(iterator.hasNext()) {
        sb.append(',').append(' ');
    }
    System.out.println(sb.toString());
} catch (Exception e) {
    e.printStackTrace();
} finally {
    if (connection != null) connection.disconnect();
}
```

这将会删除指定 URL 中的资源，然后打印响应头。

# 工作原理

我们从一个 URL 获取 `HttpURLConnection`。
使用 `setRequestProperty` 设置内容类型，默认类型为 `application/x-www-form-urlencoded`。`setInput(true)` 告诉连接我们打算将 URL 连接用于输入。使用 `setRequestMethod("DELETE")` 执行 HTTP DELETE 操作。

最后，我们打印服务器响应头。

# 第 95.4 节：检查资源是否存在

```java
/**
 * 通过发送 HEAD 请求检查资源是否存在。
 * @param url 必须检查的资源 URL。
 * @return 如果响应状态码为 200 OK，则返回 true。
 */
```

```java
public static final boolean checkIfResourceExists(URL url) throws IOException {
    HttpURLConnection conn = (HttpURLConnection) url.openConnection();
    conn.setRequestMethod("HEAD");
    int code = conn.getResponseCode();
    conn.disconnect();
    return code == 200;
}
```

# 解释：

如果你只是检查资源是否存在，使用 HEAD 请求比 GET 请求更好。这避免了传输资源的开销。
注意，该方法仅在响应状态码为 200 时才返回 true。如果你预期的会有重定向（即 3XX）响应，可能需要启用该方法以处理这些重定向。

# 示例：

```java
checkIfResourceExists(new URL("http://images.google.com/"));
```

## 第 96 章：JAX-WS

# 第 96.1 节：基础认证

使用基础认证进行 JAX-WS 调用的方法显而易见。
这是一个示例，其中 `Service` 是服务类的表示，`Port` 是你想要访问的端口。
`Service s = new Service();`
`Port port = s.getPort();`

已测试的构造：

- 1. `if` 句中的表达式。与 Java 不同，`if` 句中的 JS 表达式不需要是布尔值。对于所谓的“假值”（`null`、`undefined`、`0`、空字符串等），它会被求值为 `false`。
- 2. 对于 `for each` 语句，Nashorn 有一种特殊的循环 - `for each` - 它它可以遍历不同的 JS 和 Java 对象。
- 3. 获取对象大小。在 JS 对象中有一个 `length` 属性，它返回数组或字符串的长度。

结果：

| 类型 | If | for each | .length |
| :--- | :--- | :--- | :--- |
| Java | null | false | 无迭代 | 异常 |
| Java | 空字符串 | false | 无迭代 | 0 |
| Java | true | 遍历字符串字符 | 字符串的长度 |
| Java | Integer/Long 值 != 0 | 迭代 | Java ArrayList true |
| | | Java HashMap true | |
| | | Java HashSet true | 遍历元素 | 遍历值 | 遍历项 undefined |
| | | 列表长度 | null |

# 建议：

- 建议使用 `if (some_string)` 来检查字符串是否不为空且为空
- `for each` 可以安全地用于遍历任何集合，如果集合不可迭代、`null` 或 `undefined`，它不会抛出异常
- 在获取对象的长度之前，必须检查它是否为 `null` 或 `undefined`（任何尝试调用 Java 对象的方法或获取其属性也是如此）

# 第 97.8 节：从脚本中实现接口

```java
import java.io.FileReader;
import java.io.IOException;
```

```java
import javax.script.ScriptEngine;
```

```java
import javascript.script.ScriptEngineManager;
import javascript.script.ScriptException;

public class InterfaceImplementationExample {
    public static interface Pet {
        public void eat();
    }
}
```

```java
public static void main(String[] args) throws IOException { // 获取 JavaScript 引擎的实例
ScriptEngineManager manager = new ScriptEngineManager(); ScriptEngine
engine = manager.getEngineByName("nashorn");
```

```java
try {
// 评估脚本 /* pet.js */
var Pet = Java.type("InterfaceImplementationExample.Pet");
new Pet() {
    eat: function() { print("eat"); }
}
/*
```

```java
Pet pet = (Pet) engine.eval(new FileReader("pet.js"));
pet.eat();
} catch (ScriptException ex) {
ex.printStackTrace();
}
```

```java
// 结果：
// 标准输出打印了 'eat'
}
```



## 第 98 章：Java Native Interface (JNI)

参数：
- `JNIEnv`
- `object`
- `jclass`

## 详细信息

- 静态 native 方法调用的 JNI 环境
- 调用静态 native 方法的类

## 第 98.1 节：从 Java 调用 C++ 方法

Java 中的静态方法和成员方法可以标记为 `native`，以指示其实现在共享库文件中。在执行 native 方法时，JVM 会在加载的库中查找相应的函数（加载 native 库），使用简单的名称修饰方案，执行参数转换和堆栈设置，然后交给原生代码处理。

### Java 代码

```java
/*** com/example/jni/JNIJava.java **/
```

### C++ 代码

包含原生函数声明的头文件应该使用 `javah` 工具在目标类上生成。在构建目录下运行以下命令：

```bash
javah -o com_example_jni_JNIJava.hpp com.example.jni.JNIJava
```

将生成以下头文件（为了简洁已删除了注释）：

```cpp
// com_example_jni_JNIJava.hpp

/* 不要编辑此文件 - 它是由机器生成的 */

#include <jni.h> //
```

#### JNI API 声明

```cpp
#ifndef _Included_com_example_jni_JNIJava
#define _Included_com_example_jni_JNIJava

#ifdef __cplusplus
extern "C" // 使用 C++ 编译器时这是绝对要求的
#endif
```

```cpp
JNIEXPORT void JNICALL Java_com_example_jni_JNIJava_printString(JNIEnv* env, object string);
JNIEXPORT double JNICALL Java_com_example_jni_JNIJava_average(JNIEnv* env, jclass, jintArray);
```

```cpp
#ifdef __cplusplus
}
#endif
```

这是一个示例实现：

```cpp
// com_example_jni_JNIJava.java
#include <iostream>
#include "com_example_jni_JNIJava.hpp"
using namespace std;

JNIEXPORT void JNICALL Java_com_example_jni_JNIJava_printString(JNIEnv* env, object jthis, jstring string) {
    const char *stringIn = env->GetStringUTFChars(string, NULL);
    if (NULL == stringIn)
        return;
    cout << stringIn << endl;
    env->ReleaseStringChars(string, stringIn);
}
```

```cpp
JNIEXPORT double JNICALL Java_com_example_jni_JNIJava_average(JNIEnv* env, jclass jthis, jintArray intArray) {
    jint *intArrayInc = env->GetArrayElements(intArray, NULL);
    if (NULL == intArrayInc)
        return 1;
    jsize length = env->GetArrayLength(intArray);
    int sum = 0;
    for (int i = 0; i < length; i++) {
        sum += intArrayInc[i];
    }
    env->ReleaseIntArrayElements(intArray, intArrayInc, 0);
    return (double) sum / length;
}
```

### 结果

标准输出打印了 'eat'

### 类型 If | for each | .length

| 类型 | If | for each | .length |
| :--- | :--- | :--- | :--- |
| Java `null` | false | 无迭代 | 异常 |
| Java 空字符串 | false | 无迭代 | 0 |
| Java `true` | 遍历字符串字符 | 字符串的长度 |
| Java Integer/Long 值 != 0 | 迭代 | Java `ArrayList` true |
| | | Java `HashMap` true |
| | | Java `HashSet` true | 遍历元素 | 遍历值 | 遍历项 undefined |
| | | 列表长度 | null |

### 建议

- 建议使用 `if (some_string)` 来检查字符串是否为空且为空
- `for each` 可以安全地用于遍历任何集合，如果集合不可迭代、`null` 或 `undefined`，它不会抛出异常
- 在获取对象的长度之前，必须检查它是否为 `null` 或 `undefined`（任何尝试调用方法或获取 Java 对象属性也是如此）

## 第 97.8 节：从脚本中实现接口

```java
import java.io.FileReader;
import java.io.IOException;
```

```java
import javax.script.ScriptEngine;
```

```java
import javascript.script.ScriptEngineManager;
import javascript.script.ScriptException;

public class InterfaceImplementationExample {
    public static interface Pet {
        public void eat();
    }
}
```

```java
public static void main(String[] args) throws IOException { // 获取 JavaScript 引擎的实例
    ScriptEngineManager manager = new ScriptEngineManager();
    ScriptEngine engine = manager.getEngineByName("nashorn");
}
```

```java
try {
    // 评估脚本 /* pet.js */
    var Pet = Java.type("InterfaceImplementationExample.Pet");
    new Pet() {
        eat: function() { print("eat"); }
    }
    /*
```

```java
    Pet pet = (Pet) engine.eval(new FileReader("pet.js"));
    pet.eat();
} catch (ScriptException ex) {
    ex.printStackTrace();
}
```

```java
// 结果：
// 标准输出打印了 'eat'
}
```

## 第 99 章：函数式接口

在 Java 8+ 中，函数式接口是指只有一个抽象方法的接口（除 `Object` 类的方法外）。参见 §9.8。标准 Java 函数式接口按签名分类的列表如下：

| 返回类型 | 参数 | 接口 |
| :--- | :--- | :--- |
| `void` | 无 | `Runnable` |
| `T` | 无 | `Supplier<T>` |
| `void` | `T` | `Consumer<T>` |
| `T` | `T` | `Function<T>` |
| `boolean` | `T` | `Predicate<T>` |
| `T` | `T` | `UnaryOperator<T>` |
| `T` | `T, T` | `BinaryOperator<T>` |
| `R` | `T, U` | `Function<T, R>` |
| `int` | `T` | `IntConsumer<T>` |
| `long` | `T` | `LongConsumer<T>` |
| `double` | `T` | `DoubleConsumer<T>` |
| `boolean` | `T` | `IntPredicate<T>` |
| `boolean` | `T` | `LongPredicate<T>` |
| `boolean` | `T` | `DoublePredicate<T>` |
| `int` | `T` | `IntFunction<T>` |
| `long` | `T` | `LongFunction<T>` |
| `double` | `T` | `DoubleFunction<T>` |
| `int` | `T` | `IntBinary<T>` |
| `long` | `T` | `LongBinary<T>` |
| `double` | `T` | `DoubleBinary<T>` |

## 第 100 章：流式接口

### 100.1: 流式风格

在流式编程风格中，你会在非流式编程风格中不返回值的设置方法（setter方法）中返回 `this`。这允许你链式调用不同的方法，使得代码更短，并且对开发者更容易处理。考虑以下非流式代码：

```java
public class Person {
    private String firstName;
    private String lastName;

    public String getFirstName() {
        return firstName;
    }

    public void setName(String firstName) {
        this.firstName = firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public void setName(String lastName) {
        this.lastName = lastName;
    }

    public String whoAreYou() {
        return "I am " + firstName + " " + lastName;
    }

    public static void main(String[] args) {
        Person person = new Person();
        person.setFirstName("John");
        person.setLastName("Doe");
        System.out.println(person.whoAreYou());
    }
}
```

使用流式风格，这段代码可以更改为：

```java
public class Person {
    private String firstName;
    private String lastName;

    public String getFirstName() {
        return firstName;
    }

    public Person withFirstName(String firstName) {
        this.firstName = firstName;
        return this;
    }

    public String getLastName() {
        return lastName;
    }

    public Person withLastName(String lastName) {
        this.lastName = lastName;
        return this;
    }

    public String whoAreYou() {
        return "I am " + firstName + " " + lastName;
    }

    public static void main(String[] args) {
        System.out.println(new Person().withFirstName("John")
            .withLastName("Doe").whoAreYou());
    }
}
```



这种设计的思想是返回某个对象以启用方法调用链的构建，并使用反映自然语言表达的方法名。这种流式风格使得代码更具可读性。

### 100.2: Truth - 流式测试框架

源自 "How to use Truth" http://google.github.io/truth

```java
String string = "awesome";

assertThat(string).startsWith("aw");

assertWithMessage("Without me, it's just awesome").that(string).contains("me");
```

```java
Iterable<Color> googleColors = googleLogo.getColors();

assertExactly(googleColors)
    .contains(BLUE, RED, YELLOW, BLUE, RED)
    .inOrder();
```

## 第101 章：远程方法调用 (RMI)

### 101.1: 回调：在“客户端”上调用方法

#### 概述

在此示例中，两个客户端通过服务器相互发送信息。客户端向服务器发送一个数字，该数字被中继给第二个客户端。第二个客户端将该数字减半，并通过服务器传回给第一个客户端。第一个客户端执行相同的操作。当任何客户端返回给服务器的数字小于10时，服务器停止通信。服务器返回给客户端的返回值（将其转换为字符串表示的数字）回溯到进程。

1. 登录服务器绑定到注册表（registry）。
2. 客户端查找登录服务器并使用其信息调用登录方法。然后：登录服务器存储客户端信息。它包括带有回调方法的客户端存根（stub）。登录服务器创建并返回一个服务器存根（“连接”或“会话”）给客户端存储。它包含服务器存根，其中包含一个注销方法（在本示例中未使用）。
3. 客户端调用服务器的 `passInt` 方法，传入接收客户端的名称和一个整数。
4. 服务器调用接收客户端的 `half` 方法并传入该整数。这触发了客户端之间的来回通信（调用回调），直到被服务器停止。

#### 共享的远程接口

```java
// 登录服务器
package callbackRemote;

import java.rmi.RemoteException;

public interface RemoteLogin extends Remote {
    RemoteConnection login(String name, RemoteClient client) throws RemoteException;
}

// 服务器
package callbackRemote;

import java.rmi.Remote;
import java.rmi.RemoteException;

public interface RemoteConnection extends Remote {
    void half() throws RemoteException;
    void logout() throws RemoteException;
}

// 客户端
package callbackRemote;

import java.rmi.Remote;
import java.rmi.RemoteException;

public interface RemoteClient extends Remote {
    String passInt(String recipient, int i) throws RemoteException;
}
```

#### 实现

```java
package callbackServer;

import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import java.rmi.server.UnicastObject;
import java.util.HashMap;
import java.util.Map;

import callbackRemote.RemoteClient;
import callbackRemote.RemoteConnection;

public class LoginServer implements RemoteLogin {
    static Map<String, RemoteClient> clients = new HashMap<>();

    @Override
    public RemoteConnection login(String name, RemoteClient client) throws RemoteException {
        Connection connection = new Connection(name, client);
        clients.put(name, client);
        System.out.println(name + " logged in");
        return connection;
    }

    public static void main(String[] args) {
        try {
            Registry reg = LocateRegistry.createRegistry(1099);
            LoginServer server = new LoginServer();
            UnicastObject.exportObject(server, 0);
            reg.bind("LoginServerName", server);
        } catch (RemoteException e) {
            e.printStackTrace();
        }
    }
}
```

```java
package callbackServer;

import java.rmi.RemoteException;
import java.rmi.server.UnicastObject;
import java.rmi.server.Unreferenced;

import callbackRemote.RemoteClient;

class Connection implements RemoteConnection, Unreferenced {
    RemoteClient client;
    String name;

    public Connection(String name, RemoteClient client) {
        this.client = client;
        this.name = name;
        try {
            UnicastObject.exportObject(this, 0);
        } catch (RemoteException e) {
            e.printStackTrace();
        }
    }

    @Override
    public void half() throws RemoteException {
        // 实现减半逻辑
    }

    @Override
    public void logout() throws RemoteException {
        // 实现注销逻辑
    }

    @Override
    public void unregistered() {
        // 实现未注销逻辑
    }
}
```

```java
}
return String.valueOf(i);
}
}
```

客户端：
package callbackClient;

```java
import java.rmi.NotBoundException;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import java.rmi.server.UnicastRemoteObject;
import callbackRemote.RemoteClient;
import callbackRemote.RemoteConnection;
import callbackRemote.RemoteLogin;
```

```java
public class Client implements RemoteClient
RemoteConnection connection;
String name, String target;

Client(String name, String target) {
    this.name = name;
    this.target = target;
}

public static void main(String[] args) {
```

```java
Client client = new Client(args[0], args[1]);

try {
    Registry reg = LocateRegistry.getRegistry();
    RemoteLogin login = (RemoteLogin) reg.lookup("LoginServerName");
    UnicastRemoteObject.exportObject(client, Integer.parseInt(args[2]));
    client.connection = login.login(client.name, client);
} catch (RemoteException | NotBoundException e) {
    e.printStackTrace();
}
```

```java
if ("Client1".equals(client.name)) {
    try {
        client.connection.passInt(client.target, 120);
    } catch (RemoteException e) {
        e.printStackTrace();
    }
}
```

```java
}
}
```

运行示例：

- 1. 运行登录服务器。
- 2. 使用参数 `Client2 Client1 1097` 运行客户端。
- 3. 使用参数 `Client1 Client2 1098` 运行客户端。

由于有 3 个 JVM，输出将分别出现在 3 个控制台中。这里是合并在一起的结果：

```
Client2 logged in
Client1 logged in
Server received from Client1:120 Server received from Client2:60 Server
received from Client1:30 30 received from Client2:15 Server received
from Client1:7 Client2 received: "7" Client2 received: "15" Client1 received:
"30" Client2 received: "60"
```

## 101.2 节：带有客户端和服务器实现的简单 RMI 示例

这是一个包含五个 Java 类和两个包（server 和 client）的简单 RMI 示例。

Server 包
PersonListInterface.java

```java
public interface PersonListInterface extends Remote
{
```

```java
/**
 * 此接口被客户端和服务器共同使用 
 * @return Person 列表
 * @throws RemoteException
 */
ArrayList<String> getPersonList() throws RemoteException;
}
```

PersonImplementation.java

```java
public class PersonImplementation extends UnicastRemoteObject
implements PersonListInterface {
```

```java
private static final long serialVersionUID = 1L;
```

```java
// 标准构造函数需要是可用的
public PersonListImplementation() throws RemoteException {
```

```java
/**
* "PersonListInterface" 的实现
* @throws RemoteException
*/
@Override
public ArrayList<String> getPersonList() throws RemoteException
ArrayList<String> personList = new ArrayList<String>();
```

```java
personList.add("Peter Pan");
personList.add("Pippi Langstumpf"); // 在此处添加你的名字
return personList;
}
```

```java
Server.java
public class Server {
```

```java
/**
* 将服务注册到已知的公共方法
*/
private static void createServer() {
    try {
        // 使用标准端口 1099 注册注册表
        LocateRegistry.createRegistry(Registry.REGISTRY_PORT);
```

```java
        System.out.println("Server : Registry created.");
        // 将 PersonList 注册到注册表
        Naming.rebind("PersonList", new PersonListImplementation());
        System.out.println("Server : PersonList registered");
    } catch (final IOException e) {
        e.printStackTrace();
    }
}
```

```java
public static void main(final String[] args) {
    createServer();
}
```

## Client 包
PersonListLocal.java

```java
public class PersonListLocal {
    private static PersonListLocal instance;
    private PersonListInterface personList;

    /**
     * 创建单例实例
     */
    private PersonListLocal() {
        try {
            // 查找端口为 1099 的本地运行服务器
            final Registry registry = LocateRegistry.getRegistry("localhost", Registry.REGISTRY_PORT);
            // 查找注册的 "PersonList"
            personList = (final PersonInterface) registry.lookup("PersonList");
        } catch (final RemoteException e) {
            e.printStackTrace();
        } catch (final NotBoundException e) {
            e.printStackTrace();
        }
    }
```

```java
    public static PersonListLocal getInstance() {
        if (instance == null) {
            instance = new PersonListLocal();
        }
        return instance;
    }
```

```java
    /**
     * 返回服务器的 PersonList
     */
    public ArrayList<String> getPersonList() {
        if (instance != null) {
            return personList.getPersonList();
        } catch (final RemoteException e) {
            e.printStackTrace();
        }
        return new ArrayList<>();
    }
}
```

## PersonTest.java

```java
public class PersonTest {
    public static void main(String[] args) {
        // 获取（本地）PersonList
        ArrayList<String> personList = PersonListLocal.getInstance().getPersonList();
        // 打印所有人
        for(String person : personList) {
            System.out.println(person);
        }
    }
}
```



# 测试你的应用程序

运行`Server.java`的输出：

```
Server : Registry created. Server : PersonList registered
```

运行`PersonTest.java`的输出：

```
Peter Pan
Pippi Langstum
```

## 101.3 节：客户端-服务器：从另一个 JVM 调用方法

**共享的远程接口：**

```java
package remote;
import java.rmi.Remote;
import java.rmi.RemoteException;
public interface RemoteServer extends Remote {
int stringToInt(String string) throws RemoteException;
}
```

**实现共享接口的服务器：**

```java
package server;

import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry
import java.rmi.server.UnicastRemoteObject;

import remote.RemoteServer;
public class Server implements RemoteServer {
@Override
public int stringToInt(String string) throws RemoteException {
System.out.println("Server : " + string);
return Integer.parseInt(string);
}

public static void main(String[] args) {
try {
Registry reg = LocateRegistry.createRegistry(Registry.REGISTRY_PORT);
RemoteServer server = new Server();
UnicastRemoteObject.exportObject(server, 0);
Naming.rebind("RemoteServer", server);
} catch (Exception e) {
e.printStackTrace();
}
}
}
```

**在服务器上调用方法的客户端：**

```java
package client;
import java.rmi.NotBoundException;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import remote.RemoteServer;

public class Client {
    RemoteServer server;
    String name;
    String target;

    void call(String s) {
        try {
            server.stringToInt(s);
        } catch (RemoteException e) {
            e.printStackTrace();
        }
    }

    public static void main(String[] args) {
        try {
            Registry reg = LocateRegistry.getRegistry("localhost", Registry.REGISTRY_PORT);
            server = (RemoteServer) reg.lookup("RemoteServer");
            Client client = new Client();
            client.name = args[0];
            client.target = args[1];
            if ("Client1".equals(client.name)) {
                client.call(client.target);
            } else {
                client.call(args[2]);
            }
        } catch (RemoteException | NotBoundException e) {
            e.printStackTrace();
        }
    }
}
```

**运行示例：**

1. 运行登录服务器。
2. 使用参数`Client2 Client1 1097`运行客户端。
3. 使用参数`Client1 Client2 1098`运行客户端。

由于有 3 个 JVM，输出将分别出现在 3 个控制台中。这里是合并在一起的结果：

```
Client2 logged in
Client1 logged in
Server received from Client1:120 Server received from Client2:60 Server
received from Client1:30 30 received from Client2:15 Server received
from Client1:7 Client2 received: "7" Client2 received: "15" Client1 received:
"30" Client2 received: "60"
```

## 第 102 章：Iterator 和 Iterable

`java.util.Iterator`是用于可迭代对象的标准接口。`java.lang.Iterable`接口用于提供迭代器的对象。

### 102.1 节：使用迭代器移除元素

`Iterator.remove()`方法是一个可选方法，用于移除由`next()`返回的元素。例如，以下代码填充了一个字符串列表并删除了全部：

```java
List<String> names = new ArrayList<>();
names.add("name 1");
names.add("name 2");
names.add("name 3");
names.add("name 4");
names.add("name 5");
System.out.println("Old Size : " + names.size());
Iterator<String> it = names.iterator();
while (it.hasNext()) {
  String el = it.next();
  if (el.equals("name 3")) {
    it.remove();
  }
}
```

输出：

```
Old Size : 5 New Size : 4
```

注意，上述代码是在遍历集合时移除元素的安全方法。如果你尝试这样做从集合中移除元素：

```java
for (String el : names) {
  if (el.equals("name 3")) {
    names.remove(el); // 错误！
  }
}
```

典型的集合（如`ArrayList`）提供的具有快速失败（fail fast）语义的迭代器将抛出`ConcurrentModificationException`。`remove()`方法只能在调用`next()`之后调用（一次）。如果在调用`next()`之前调用，或者在调用`next()`之后调用两次，则`remove()`调用将抛出`IllegalStateException`。

`remove`操作被描述可选操作；即并非所有的迭代器都允许这样做。不支持的示例包括不可变集合的迭代器、集合的只读视图或固定大小集合。如果在迭代器不支持移除时调用`remove()`，它将抛出`UnsupportedOperationException`。

### 102.2 节：创建你自己的 Iterable

要为任何接口创建你自己的`Iterable`，只需实现接口中的抽象方法。对于`Iterable`，只有一个方法，称为`iterator()`。但它的返回类型`Iterator`本身也是带有三个抽象方法的接口。你可以返回与某些集合关联的迭代器，也可以创建你自己的自定义实现：

```java
public static class Alphabet implements Iterable<Character> {
    @Override
    public Iterator<Character> iterator() { return new Iterator<Character>() {
        char letter = 'a';
        @Override
        public boolean hasNext() { return letter <= 'z'; }
        @Override
        public Character next() { return letter++; }
        @Override
        public void remove() {
            throw new UnsupportedOperationException("移除字母没有意义");
        }
    }};
}
```

使用方法：

```java
public static void main(String[] args) { for(char c : new Alphabet()) {
    System.out.println("c " + c);
}
```

新的迭代器（`Iterator`）应该包含一个指向第一个元素的状态，每次调用`next()`都会更新其状态以指向下一个元素。`hasNext()`用于检查迭代器是否连接到一个可修改的集合，然后迭代器的`remove()`方法可能会被实现为从底层集合中移除当前指向的元素。

## 章节 102.3：在 for 循环中使用 Iterable

实现`Iterable<>`接口的类可以用于 for 循环。这实际上只是从对象获取迭代器并使用它按顺序获取所有元素的语法糖；它让代码更清晰、编写更快且更不容易出错。

```java
public class UsingIterable {
    public static void main(String[] args) {
        List<Integer> intList = Arrays.asList(1,2,3,4,5,6,7);
        // List 扩展 Collection, Collection 实现 Iterable
        Iterable<Integer> iterable = intList;
        // foreach-循环
        for (Integer i : iterable) {
            System.out.println(i);
        }

        // Java 5 之前的迭代方式
        for(Iterator<Integer> i = iterable.iterator(); i.hasNext(); ) { 
            Integer item = i.next();
            System.out.println(item);
        }
    }
}
```

## 章节 102.4：使用原始迭代器

虽然使用 foreach 循环（或“扩展 for 循环”）很简单，但有时直接使用迭代器会有处。例如，如果你想输出一组逗号分隔的值，但不想让最后一个带有逗号：

```java
List <String> yourData = //...
Iterator<String> iterator = yourData.iterator();
while (iterator.hasNext()){
    // next() 将迭代器“移动”到下一个条目并返回其值。
    String entry = iterator.next();
    System.out.print(entry);
    if (iterator.hasNext()){
        // 如果迭代器在当前元素之后还有元素：
        System.out.print(",");
    }
}
```

这比设置一个`isLastEntry`变量或使用循环索引进行计算要容易且清晰得多。

## 章节 103：反射 API (Reflection API)

反射通常用于需要检查或修改运行在 JVM 中的应用程序运行时行为的程序。Java 反射 API 用于此目的，它使得在编译时已知类名的情况下，能够在运行时检查类、接口和方法。它还允许通过反射实例化新对象并使用反射调用方法。

## 章节 103.1：动态代理 (Dynamic Proxies)

动态代理与反射并没有太大的关系，但它们是 API 的一部分。它基本上是创建接口动态实现的一种。这在创建模拟服务（mockup）时可能很有帮助。动态代理是接口的一个实例，通过一个所谓的调用处理器（invocation handler）创建，该处理器会拦截所有方法调用并允许手动处理它们的调用。

```java
public class DynamicProxyTest {

    public interface MyInterface1{
        public void someMethod1();
        public int someMethod2(String s);
    }
}
```

```java
public interface MyInterface2{
    public void anotherMethod();
}
```

```java
public static void main(String[] args) throws Exception {
    // 动态代理类
    Class<?> proxyClass = Proxy.getProxyClass(
        ClassLoader.getSystemLoader(), new Class[]{MyInterface1.class, MyInterface2.class});
    // 动态代理类构造函数
    Constructor<?> proxyConstructor = proxyClass.getConstructor(InvocationHandler.class);
    // 调用处理器
```

```java
InvocationHandler handler = new InvocationHandler(){
    // 每次代理方法调用都会触发此方法
    // 此方法是被调用的方法，args 持有方法参数
    // 它必须返回方法的结果
    @Override
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
```

```java
        String methodName = method.getName();

        if (methodName.equals("someMethod1")) {
            System.out.println("someMethod1 was invoked!");
            return null;
        }
```

```java
        if(methodName.equals("someMethod2")){
            System.out.println("someMethod2 was invoked!");
            System.out.println("Parameter: " + args[0]);
            return 42;
        }
        if(methodName.equals("anotherMethod")){
            System.out.println("anotherMethod was invoked!");
            return null;
        }
        System.out.println("Unkown method!");
        return null;

    } 
};
```

```java
// 创建动态代理实例
MyInterface1 i1 = (MyInterface1) proxyConstructor.newInstance(handler);
MyInterface2 i2 = (MyInterface2) proxyConstructor.newInstance(handler);

// 调用一些方法
i1.someMethod1();
i1.someMethod2("stackoverflow"); 
i2.anotherMethod();
```

该代码的运行为：

```
someMethod1 was invoked! someMethod2 was invoked! Parameter: stackoverflow anotherMethod was invoked!
```

## 章节 103.2：引言

### 基础

反射 API 允许运行时检查代码的类结构并动态调用代码。这非常强大，但也是危险的，因为编译器无法静态确定动态调用是否有效。

一个简单的例子是获取给定类的公共构造函数和方法：



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`。

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



此操作允许使用 16 字节的内存。直接缓冲区的内容可能存在于常规垃圾回收堆之外。

我们可以通过调用以下方法来验证 `ByteBuffer` 是否是直接的：

```java
buffer.isDirect(); // true
```

`DirectByteBuffer` 的主要特点是 JVM 将尝试直接在分配的内存上进行原生操作，而无需任何额外的缓冲，因此在其上执行的操作可能比在底层的 `ByteBuffers` 数组上执行的操作更快。

建议在依赖执行速度的密集型 IO 操作和实时通信中使用 `DirectByteBuffer`。

我们必须意识到，如果使用 `array()` 方法，将得到 `UnsupportedOperationException`。因此，在使用之前检查我们的 `ByteBuffer` 是否拥有该数组（字节数组）是一个良好的实践。

你可以使用 `getAppletContext()` 方法来获取 `AppletContext` 对象，该对象允许你请求浏览器打开链接。为此，你使用 `show()` 方法。它的第二个参数告诉浏览器使用新窗口 `_blank` 还是显示 applet 的当前窗口 `_self`。

```java
public class MyLinkApplet extends JApplet{
    @Override
    public void init() {
        JButton button = new JButton("ClickMe!");
        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                AppletContext a = getAppletContext();
                try {
                    URL url = new URL("http://stackoverflow.com/");
                    a.showDocument(url, "_blank");
                } catch (Exception e) { /* omitted for brevity */} }
            }
        });
        add(button);
    }
}
```

## 第 105.4 节：加载图像、音频和其他资源

Java applet 能够加载不同的资源。但由于它们运行在客户端的浏览器中，你需要确保这些资源是可访问的。applet 无法访问本地文件系统等客户端资源。

如果你想从 Applet 存储的相同 URL 加载资源，可以使用 `getCodeBase()` 方法获取基础 URL。为了加载资源，applet 提供了 `getImage()` 和 `getAudioClip()` 方法来加载图像或音频文件。

### 加载并显示图像

```java
public class MyImgApplet extends JApplet {
    private Image img;
    @Override
    public void init() {
        try {
            img = getImage(new URL("http://cdn.sstatic.net/stackexchange/img/logos/so/sologo.png"));
        } catch (MalformedURLException e) { /* omitted for brevity */ }
    }

    @Override
    public void paint(Graphics g) {
        g.drawImage(img, 0, 0, this);
    }
}
```

### 加载并播放音频文件

```java
public class MyAudioApplet extends JApplet {
    private AudioClip audioClip;
    @Override
    public void init() {
        try {
            audioClip = getAudioClip(new URL("URL/TO/AN/AUDIO/FILE.WAV"));
        } catch (MalformedURLException e) { /* omitted for brevity */ }
    }
    public void start() {
        audioClip.play();
    }
    @Override
    public void stop() {
        audioClip.stop();
    }
}
```

### 加载并显示文本文件

```java
public class MyTextApplet extends JApplet {
    @Override
    public void init() {
        JTextArea textArea = new JTextArea();
        JScrollPane sp = new JScrollPane(textArea);
        add(sp);
        // load text
        try {
            URL url = new URL("http://www.textfiles.com/fun/quotes.txt");
            InputStream in = url.openStream();
            BufferedReader bf = new BufferedReader(new InputStreamReader(in));
            String line = "";
            while ((line = bf.readLine()) != null) {
                textArea.append(line + "\n");
            }
        } catch (Exception e) { /* omitted for brevity */ }
    }
}
```

## 第 106 章：表达式

Java 中的表达式是进行计算的主要结构。

### 第 106.1 节：运算符优先级

当一个表达式包含多个运算符时，它可能有不同的读取方式。例如，数学表达式 `1+2 x 3` 可以有两种读取方式：

- 1. 将 1 和 2 相加，并将结果乘以 3。得到答案是 9。如果我们加上括号，它看起来像 `(1 + 2) x 3`。

- 2. 在 2 和 3 的乘积结果加上 1。得到答案是 7。如果我们加上括号，它看起来像 `1 + (2 x 3)`。

在数学中，惯例是按照第二种方式读取表达式。通用规则是乘法和除法在加减法之前执行。当使用更复杂的数学符号时，含义要么是“显而易见的”（对于受过训练的数学家来说！），要么添加括号来消除歧义。无论何种情况，符号传递含义的有效性取决于数学家的智力和共享的知识。

Java 拥有相同的读取表达式的清晰规则，这些基于所使用的运算符的优先级。

通常，每个运算符都被赋予一个优先级值；见下表。

例如：

```java
1 + 2 * 3
```

`+` 的优先级低于 `*` 的优先级，所以表达式的结果是 7，而不是 9。

| 运算符 / 结构（主要） | 说明 | 优先级 | 结合性 |
| :--- | :--- | :--- | :--- |
| `+` | 括号 | 15 | 从左到右 |
| `new` | 实例创建 | 14 | 从右到左 |
| `.` | 字段访问 | 13 | 从左到右 |
| `[]` | 数组访问 | 12 | 从左到右 |
| `()` | 方法调用 | 11 | 从左到右 |
| `::` | 方法引用 | 10 | 从左到右 |
| `++` | 后自增 | 9 | 从左到右 |
| `++` | 前自增 | 8 | 从右到左 |
| `-` | 一元 | 7 | 从右到左 |
| `(type)` | 强制转换 | 6 | 从右到左 |
| `* / %` | 乘除 | 5 | 从左到右 |
| `+` | 加减 | 4 | 从左到右 |
| `<< >>>` | 移位 | 7 | 从左到右 |
| `< <= == instanceof` | 关系 | 8 | 从左到右 |
| `== !==` | 等等性 | 9 | 从左到右 |
| `&` | 位位与 | 10 | 从左到右 |
| `^` | 位位异或 | 11 | 从左到右 |
| `\|` | 位位包含或 | 12 | 从左到右 |
| `&&` | 逻辑与 | 13 | 从左到右 |
| `\|\|` | 逻辑或 | 14 | 从左到右 |
| `? :` | 条件 | 1 | |
| `= *= /= %= += -= <= >>> >= &= ^= \|=` | 赋值 | 2 | 从右到左 |
| `->` | Lambda 表达式 | 3 | 从右到左 |

Lambda 表达式的优先级非常复杂，因为它也可能出现在强制转换之后，或者作为条件三元运算符的第三部分。

### 第 106.2 节：表达式基础

Java 中的表达式是进行计算的主要结构。这里是一些示例：

```java
1 // 简单的字面量
1 + 2 // 两个数字相加的简单表达式
(i + j) / k // 包含多个操作的表达式
(flag)? c : d // 使用条件运算符的表达式
(String) s // 类型转换
obj.test() // 方法调用
new Object() // 创建对象
new int[] // 创建对象
```

通常，表达式由以下部分组成：

- 表达式名称包括：
    - 简单标识符；`someIdentifier`
    - 限定标识符；`MyClass.someIdentifier`

- 基础部分包括：
    - 字面量；`1`, `1.0`, `'X'`, `"hello"`, `false`, `null`
    - 类字面量；`MyClass.class`
    - `this` 和 `<TypeName> . this`
    - 括号表达式；`(a + b)`
    - 类创建表达式；`new MyClass(1, 2, 3)`
    - 数组实例创建表达式；`new int[3]`
    - 字段访问表达式；`obj.someField` 或 `this.someField`
    - 数组访问表达式；`vector[2]`
    - 方法调用；`obj.doIt(1, 2, 3)`
    - 方法引用（Java 8 及以后）；`MyClass::doIt`

- 一元运算符表达式；`!a` 或 `i++`
- 二元运算符表达式；`a + b` 或 `obj == null`
- 三元运算符表达式；`(obj == null) ? 1 : obj.getCount()`
- Lambda 表达式（Java 8 及以后）；`obj -> obj.getCount()`

不同表达式形式的细节可以在其他主题中找到。

运算符主题涵盖了一元、二元和三元运算符表达式。

Lambda 表达式涵盖了 Lambda 表达式和方法引用表达式。类和对象涵盖了类实例创建表达式。数组涵盖了数组访问表达式和数组实例创建表达式。字面量涵盖了不同类型的字面量表达式。

由于像这样的表达式的求值结果无法被使用，且它无法以任何其他方式影响程序的执行，Java 的设计者认为这种用法要么是错误的，要么是误导的。然而，这并不适用于所有表达式。有一部分表达式（事实上）作为语句时是合法的。该集合包括：

- 赋值表达式，包括复合赋值（赋值运算符）。
- 前置/后置自增递减表达式。
- 方法调用（`void` 或非 `void`）。
- 类实例创建表达式。

## 第 106.3 ：表达式求值顺序

Java 表达式遵循以下规则进行求值：

- 操作数从左到右求值。
- 操作符的操作数在操作符之前求值。操作符根据优先级进行求值。
- 参数列表从左到右求值。

## 简单示例

在以下示例中：

```java
int i = method1() + method2();
```

求值顺序为：

- 1. 求值 `=` 操作符的左侧操作数为 `i` 的地址。
- 2. 求值 `+` 操作符的左侧操作数 (`method1()`)。
- 3. 求值 `+` 操作符的右侧操作数 (`method2()`)。
- 4. 求值 `+` 操作符。
- 5. 求值 `=` 操作，将加法结果赋值给 `i`。

注意，如果调用的影响是可见的，你将能够观察到 `method1` 的调用发生在 `method2` 的调用之前。

## 带有副作用的操作符示例

在以下示例中：

```java
int i = 1;
intArray[i] = ++i + 1;
```

求值顺序为：

- 1. 求值 `=` 操作符的左侧操作数。这得到了 `intArray[1]` 的地址。
- 2. 执行前置自增。给 `i` 加 1，并求值为 2。
- 3. 求值 `+` 的右侧操作数。
- 4. 求值 `+` 操作结果为：`2 + 1 -> 3`。
- 5. 求值 `=` 操作，将 3 赋值给 `intArray[1]`。

注意，由于 `=` 的左侧操作数首先被求值，因此它不受 `++` 子表达式副作用的影响。

参考：

JLS 15.7 - 求值顺序

## 第 106.4 ：常量表达式

常量表达式是一个产生基本类型或 `String` 的表达式，其值可以在编译时被求值并得到一个字面量。该表达式在求值时不能抛出异常，并且它必须仅由以下内容组成：

- 基本类型字面量和 `String` 字面量。
- 向基本类型或 `String` 的类型转换。
- 以下一元运算符：`+`, `-`, `~` 和 `.`。
- 以下二运算符：`*`, `%`, `+`, `-`, `<`, `>>`, `<`, `>`, `>=`, `==`, `!=`, `&`, `|`, `&&` 和 `||`。
- 三元条件运算符 `?`。
- 括号括的常量表达式。
- 指向常量变量的简单名称。（常量变量是在初始化表达式本身是常量表达式时声明为 `final` 的变量。）

形式为 `<TypeName>.<Identifier>` 的限定名称指向常量变量。

注意上述列表排除了 `+` 和 `-`、赋值运算符、类和 `instanceof`、方法调用以及对普通变量或字段的引用。

`String` 类型的常量表达式结果产生一个“内部”`String`，常量表达式中的浮点运算使用 FP-strict（严格浮点）语义进行求值。

## 常量表达式的用途

常量表达式可以使用任何可以使用普通表达式的地方。然而，它们在以下上下文中具有特殊意义。

`switch` 语句中的 `case` 标签需要常量表达式。例如：

```java
switch (someValue) {
    case 1 + 1: // OK
    case Math.min(2, 3): // 错误 - 不是常量表达式
    doSomething();
}
```

当赋值右侧的表达式是常量表达式时，赋值可以执行基本类型的收窄转换。只要常量表达式的值在左侧类型的范围内，这种转换就是允许的（见 JLS 5.1.3 和 5.2）。例如：

```java
byte b1 = 1 + 1; // OK - 基本类型收窄转换
byte b2 = 127 + 1; // 错误 - 越范围
byte b3 = b1 + 1; // 错误 - 不是常量表达式
byte b4 = (byte) (b1 + 1); // OK
```

当常量表达式用作 `do`, `while` 或 `for` 的条件时，它会影响可读性分析。例如：

```java
while (false) {
    doSomething(); // 错误 - 语句不可达
}
boolean flag = false;
while (flag) {
    doSomething(); // OK
}
```

（注意这不适用于语句。Java 编译器允许 `if` 语句的 `then` 或 `else` 块不可达。这是 Java 中 C 和 C++ 中的条件编译。）

最后，类或接口中带有常量表达式初始化器的 `static final` 字段会被尽早初始化。因此，可以保证这些常量会在初始化状态被观察到，即使类初始化依赖图中存在循环。

获取更多信息，请参阅 JLS 15.28 常量表达式。

## 第 107 章：Java 中的 JSON

JSON（JavaScript 对象表示）是一种轻量级、基于文本、语言无关的数据交换格式，易于人类和机器读写。JSON 可以表示两种结构化类型：对象和数组。JSON 常用于 Ajax 应用、配置、数据库和 RESTful Web 服务。Java JSON 处理 API（JSON-P）提供了解析所需的 API。

## 第 107.1 ：使用 Jackson

JSON（JavaScript 对象表示）是一种轻量级、基于文本、语言无关的数据交换格式，易于人类和机器读写。JSON 可以表示两种结构化类型：对象和数组。JSON 常用于 Ajax 应用、配置、数据库和 RESTful Web 服务。Java JSON 处理 API 提供了解析、生成和转换所需的 API。

需要的导入语句：`import com.fasterxml.jackson.databind.ObjectMapper;`

Maven 依赖：`jackson-databind`

`ObjectMapper` 实例是线程安全的共享。

```java
public class Model {
  private String firstName;
  private String lastName;
  private int age;
  /* getter 和 setter 省 */
}
```

示例：`String` 转对象



# 第 107 章：JSON 处理

## 第 107.1 节：JSON 转对象（Jackson 库）

使用 `ObjectMapper` 将 JSON 字符串转换为 Java 对象：

```java
ObjectMapper objectMapper = new ObjectMapper();
String jsonString = "{\"firstName\":\"John\",\"lastName\":\"Doe\",\"age\":23}";
Model outputObject = objectMapper.readValue(jsonString, Model.class);
System.out.println(outputObject.getFirstName()); // 输出 John
```

异常：

- `IOException`: 发生底层 I/O 问题
- `JsonParseException`: 如果输入包含无效内容
- `JsonMappingException`: 如果输入 JSON 与对象不匹配

## 第 107.2 节：JSON 转对象（Gson 库）

假设你有一个只有 `name` 的类：

```java
private class Person {
  public String name;
  public Person(String name) {
    this.name = name;
  }
}
```

示例：

```java
Gson gson = new Gson();
String json = "\"name\": \"John\"";
Person person = gson.fromJson(json, Person.class);
System.out.println(person.name); // John
```

## 第 107.3 节：`JSONObject.NULL`

如果你需要添加一个值为 `null` 的属性，应该使用预定义的静态常量 `JSONObject.NULL` 而不是标准的 Java `null` 引用。`JSONObject.NULL` 是哨兵值，用于显式定义空属性。

```java
JSONObject obj = new JSONObject();
obj.put("some", JSONObject.NULL); // 创建 {"some":null}
System.out.println(obj.get("some")); // 输出 null
```

> **注意**
>
> `JSONObject.NULL.equals(null);` // 返回 `true`
>
> 这明显违反了 `Java.equals()` 契约：对于任何非空引用值 `x`，`x.equals(null)` 应返回 `false`

## 第 107.4 节：JSON 构建器 - 方法链式调用

在处理 `JSONObject` 和 `JSONArray` 时可以使用链式调用。`JSONObject` 示例：

```java
JSONObject obj = new JSONObject(); // 初始化一个空的 JSON 对象
// 前：{}
.put("name", "Nikita").put("age", "30").put("isMarried", "true"); // 后：
{"name":"Nikita","age":"30","isMarried":true}
```

`JSONArray` 示例：

```java
JSONArray arr = new JSONArray(); // 初始化一个空数组 // 前：[]
```

```java
arr.put("Stack").put("Over").put("Flow");
// 修改后: ["Stack", "Over","Flow"]
```

## 第 107.5 节：对象转 JSON（Gson 库）

假设你有一个仅包含 `name` 的 `Person` 类：

```java
private class Person {
    private String name;
    public Person(String name) {
        this.name = name;
    }
}
```

```java
Gson g = new Gson();
Person person = new Person("John");
System.out.println(g.toJson(person)); // {"name":"John"} 当然，Gson 必须在类路径上。
```

## 第 107.6 节：JSON 遍历

遍历 `JSONObject` 属性：

```java
JSONObject obj = new JSONObject("...");
String key = keys.next(); // 获取下一个键
Object value = obj.get(key); // 通过键获取下一个值
System.out.println(key + " : " + value); // 打印键 :值
}
```

遍历 `JSONArray` 值：

```java
JSONArray arr = new JSONArray(); // 初始化一个空数组 // 向其中推入（追加）一些值：
```

```java
arr.put("Stack");
arr.put("Over");
arr.put("Flow");
for (int i = 0; i < arr.length(); i++){// 遍历所有值
```

```java
Object value = arr.get(i); // 获取值
System.out.println(value); // 打印每个值
```

## 第 107.7 节：`optXXX` 与 `getXXX` 方法

`JSONObject` 和 `JSONArray` 有几个方法，当你尝试获取的值不存在或类型为其他类型时，这些方法非常有用。

```java
JSONObject obj = new JSONObject(); obj.putString("foo", "bar");

// 对于类型正确的已存在属性，没有区别
obj.getString("foo"); obj.optString("foo");

// 返回 "bar" // 返回 "bar" 
obj.optString("foo", "tux"); // 返回 "bar"

// 然而，如果值无法转换为正确的类型，行为则不同
obj.getInt("foo"); // 抛出 JSONException
obj.optInt("foo"); // 返回 0
obj.optInt("foo", 123); // 返回 123

// 如果属性不存在也一样
obj.getString("undefined");
obj.optString("undefined");

// 抛出 JSONException // 返回 ""
obj.optString("undefined", "tux"); // 返回 "tux" 
```

相同的规则也适用于 `JSONArray` 的 `getXXX` / `optXXX` 方法。

## 第 107.8 节：从 JSON 中提取单个元素

```java
String json = "{\"name\":\"John\",\"age\":21}";
JSONObject jsonObject = new JsonParser().parse(json).getAsObject();
System.out.println(jsonObject.get("name").getAsString()); //John
System.out.println(jsonObject.get("age").getInt()); //21
```

## 第 107.9 节：`JsonArray` 转为 Java `List`（Gson 库）

这里有一个你想转换为 Java `ArrayList` 的简单 `JSONArray`：

```json
{
  "list": [ "Test_String_1", "Test_String_2"]
}
```

现在将 `JSONArray` `'list'` 传递给以下方法，该方法将返回对应的 Java `ArrayList`：

```java
public ArrayList<String> getListString(String jsonList){
  Type list = new TypeToken<List<String>>(){}.getType(); // 确保名称 'list' 与你 'Json' 中 'JsonObject' 的名称匹配。
  ArrayList<String> list = new Gson().fromJson(jsonList, list);

  return list;
}
```

你应该在 `POM.xml` 文件中添加以下 maven 依赖：

```xml
<!-- https://mvnrepository.com/artifact/com.google.code.gson/gson -->
<dependency>
  <groupId>com.google.code.gson</groupId>
  <artifactId>gson</artifactId>
  <version>2.7</version>
</dependency>
```

或者确保你的类路径中包含 `com.google.code.gson:gson.jar:<version>`。

## 第 107.10 节：将数据编码为 JSON

如果你需要创建一个 `JSONObject` 并向其中放入数据，请考虑以下示例：

```java
// 创建一个新的 javax.json.JSONObject 实例。
JSONObject first = new JSONObject();
first.put("foo", "bar");
first.put("temperature", 21.5);
first.put("year", 2016);
```

```java
// 添加第二个对象。
JSONObject second = new JSONObject();
second.put("Hello", "world");
first.put("message", second);
```

```java
// 创建一个带有某些值的 JSONArray
JSONArray someMonths = new JSONArray(new String[] { "January", "February" }); 
someMonths.put("March");
// 将另一个月份作为第五个元素，留空第四个元素
someMonths.put(4, "May");
```

```java
// 将数组添加到我们的对象中
object.put("months", someMonths);
// 编码
String json = object.toString();
```

```json
/* 给读者的练习：添加格式化输出！ 
"foo":"bar",
"temperature":21.5,
"year":2016,
"message":{"Hello":"world"},
"months":["January","February","March",null,"May"] 
*/
```

## 第 107.11 节：解码数据

如果你需要从 `JSONObject` 获取数据，请考虑以下示例：

```java
// 解码 JSON
String json = "{\"foo\":\"bar\",\"temperature\":21.5,\"year\":2016,\"message\":{\"Hello\":\"world\"},\"months\":[\"January\",\"February\",\"March\",\"null,\"May\"]}";
JSONObject object = new JSONObject(json);

// 获取值
String foo = object.getString("foo");
double temperature = object.getDouble("temperature");
int year = object.getInt("year");

// 获取另一个对象
JSONObject secondary = object.getJSONObject("message");
String hello = secondary.getString("Hello");

// 获取数组
JSONArray someMonths = object.getJSONArray("months");
for (int i = 0; i < someMonths.length(); i++) {
    System.out.println(someMonths.get(i));
}
```

# 第 108 章：使用 JAXP API 解析 XML

## 第 108.1 节：使用 StAX API 解析文档

考虑到以下文档，可以使用以下代码来解析它：

```java
import javax.xml.stream.XMLInputFactory;
import javax.xml.stream.XMLStreamReader;
import javax.xml.stream.XMLStreamConstants;
import java.io.StringReader;
import java.util.HashMap;
import java.util.Map;

public class StaxDemo {
    public static void main(String[] args) throws Exception {
        String xmlDocument = "<?xml version='1.0' encoding='UTF-8'?><library><book id='1'>Effective Java</book><book id='2'>Java Concurrency In Practice</book><book id='3'>This is not a book</book></library>";
        XMLInputFactory xmlInputFactory = XMLInputFactory.newFactory();
        XMLStreamReader xmlStreamReader = xmlInputFactory.createXMLStreamReader(new StringReader(xmlDocument));

        Map<Integer, String> bookById = new HashMap<>();

        // 使用循环遍历每个事件
        while (xmlStreamReader.hasNext()) {
            switch (xmlStreamReader.getEventType()) {
                case XMLStreamConstants.START_ELEMENT:
                    System.out.println("Found start of element: " + xmlStreamReader.getLocalName());
                    // 检查是否处于 <book> 元素
                    if ("book".equals(xmlStreamReader.getAttributeValue("", "id"))) {
                        String bookTitle = xmlStreamReader.getElementText();
                        bookById.put(Integer.parseInt(xmlStreamReader.getAttributeValue("", "id")), bookTitle);
                    }
                    break;
                default:
                    break;
            }
            xmlStreamReader.next();
        }
        System.out.println(bookById);
    }
}
```

输出为：

```
Found start of element: library
Found start of element: book
Found start of element: book
Found start of element: book
{1=Effective Java, 2=Java Concurrency In Practice, 3=This is not a book}
<book id='2'>Java Concurrency In Practice</library>
```

可以使用以下代码从字符串构建一个 DOM 树：

```java
import org.w3c.dom.Document; import org.w3c.dom.Node;
import org.w3c.dom.NodeList; import org.w3c.dom.sax.InputSource;

import javax.xml.parsers.DocumentBuilderFactory; import
javax.xml.parsers.DocumentBuilder; import java.io.StringReader;

public class DOMDemo {
public static void main(String[] args) throws Exception {
```



# XML 解析与 XPath 求值

## 第 109 章：XML XPath 求值

### 第 109.1 节：在单个 XML 中解析多个 XPath 表达式

使用与 XML 文档中评估 `NodeList` 的相同示例，以下是高效进行多次 XPath 调用的方法：

给定以下 XML 文档：

```xml
<documentation>
<tags>
<tag name="Java">
<topic name="Regular expressions">
<example>Matching groups</example>
<example>Escaping metacharacters</example>
</topic>
<topic name="Arrays">
<example>Looping over arrays</example>
<example>Converting an array to a list</example>
</topic>
</tag>
<tag name="Android">
<topic name="Building Android projects">
<example>Building an Android application using Gradle</example>
<example>Building an Android application using Maven</example>
</topic>
<topic name="Layout resources">
<example>Including layout resources</example>
<example>Supporting multiple device screens</example>
</topic>
</tag>
</tags>
</documentation>
```

这是你如何在一个文档中使用 XPath 评估多个表达式：

```java
XPath xpath = XPathFactory.newInstance().newXPath(); //创建新的 XPath
DocumentBuilder builder = DocumentBuilderFactory.newInstance();
Document doc = builder.parse(new File("path/to/xml.xml")); //指定 XML 文件路径
```

```java
NodeList javaExampleNodes = (NodeList)
XPath.evaluate("/documentation/tags/tag[@name='Java']/example", doc,
XPathConstants.NODESET); // 求值 XPath
XPath.reset(); // 重置 xpath以便再次使用
NodeList androidExampleNodes = (NodeList)
XPath.evaluate("/documentation/tags/tag[@name='Android']/example", doc,
XPathConstants.NODESET); // 求值 XPath
```

### 第 109.2 节：在 XML 中多次解析单个 XPath 表达式

在这种情况下，你希望在评估之前对表达式进行编译，这样每次调用 `evaluate` 不需要编译相同的表达式。简单的语法是：

```java
XPath xpath = XPathFactory.newInstance().newXPath(); //创建新的 XPath
XPathExpression exp = xpath.compile("/documentation/tags[@name='Java']/example");
DocumentBuilder builder = DocumentBuilderFactory.newInstance();
Document doc = builder.parse(new File("path/to/xml.xml")); //指定 XML 文件路径
```

```java
NodeList javaExampleNodes = (NodeList) exp.evaluate(doc, XPathConstants.NODESET); // 从已编译的表达式求值 XPath
NodeList javaExampleNodes2 = (NodeList) exp.evaluate(doc, XPathConstants.NODESET); //再次执行。总的来说，两次调用 XPathExpression.evaluate() 会比两次调用 XPath.evaluate() 高得多。
```

### 第 109.3 节：在 XML 文档中评估 NodeList

给定以下 XML 文档：

```xml
<documentation>
<tags>
<tag name="Java">
<topic name="Regular expressions">
<example>Matching groups</example>
<example>Escaping metacharacters</example>
</topic>
<topic name="Arrays">
<example>Looping over arrays</example>
<example>Converting an array to a list</example>
</topic>
</tag>
<tag name="Android">
<topic name="Building Android projects">
<example>Building an Android application using Gradle</example>
<example>Building an Android application using Maven</example>
</topic>
<topic name="Layout resources">
<example>Including layout resources</example>
<example>Supporting multiple device screens</example>
</topic>
</tag>
</tags>
</documentation>
```

以下内容获取 Java 标签的所有示例节点（如果仅在 XML 中评估 XPath，使用此方法。一旦在同一文件中评估了其他多个 XPath 路径示例）：

```java
XPathFactory xFactory = XPathFactory.newInstance();
XPath xpath = xFactory.newXPath();//创建新的 XPath
InputSource source = new InputSource("path/to/xml.xml");//指定文件路径
NodeList javaExampleNodes = (NodeList)
xpath.evaluate("/documentation/tags/tag[@name='Java']/example", source,
XPathConstants.NODESET); // 求值 XPath
```

```java
} catch (NullPointerException ex) {
    ex.printTrace();
} catch (NumberFormatException ex) {
    ex.printTrace();
}
```

这将在控制台中输出：

```
Name : Smith, Dan
Age: 23 (years)
Favorite Color: green
----------------
Name: Autry, Bob
Age: 3 (months)
Favorite Color: N/A
----------------
```

## 第 110 章：XML 文件读写

### 第 110.1 节：读取 XML 文件

使用 XOM 读取 XML 文件与写入非常相似，区别在于在这种情况下我们是在实例化，而不是从根节点获取它们。

要创建一个新元素，请使用构造函数 `Element(String name)`。你可能需要创建一个根元素，以便方便地将其添加到文档（`Document`）中。

`Element root = new Element("root");`

`Element` 类包含了一些用于编辑元素的方便方法。它们列在下方：

- `appendChild(String name)` - 这将元素的值设置为 `name`。
- `appendChild(Node node)` - 这将该节点设为父节点（元素也是节点，因此你可以解析元素）。
- `addAttribute(Attribute attribute)` - 将为元素添加一个属性。

`Attribute` 类有几个不同的构造函数。最简单的是 `Attribute(String name, String value)`。

一旦你将所有元素都添加到根元素中，你就可以将其转换为 `Document`。`Document` 的构造函数会接受一个 `Element` 作为参数。

你可以使用 `Serializer` 将你的 XML 写入文件。你需要在 `Serializer` 的构造函数中创建一个新的输出流。

`FileOutputStream fileOutputStream = new FileOutputStream(file); Serializer serializer = new Serializer(fileOutputStream, "UTF-8");`

`serializer.setIndent(4);`

`serializer.write(doc);`

### 第 110.2 节：写入 XML 文件

使用 XOM 写入 XML 文件与读取非常相似，区别在于在这种情况下我们是在实例化，而不是从根节点获取它们。

要创建一个新元素，请使用构造函数 `Element(String name)`。你可能需要创建一个根元素，以便方便地将其添加到文档（`Document`）中。

`Element root = new Element("root");`

`Element` 类包含了一些用于编辑元素的方便方法。它们列在下方：

- `appendChild(String name)` - 这将元素的值设置为 `name`。
- `appendChild(Node node)` - 这将该节点设为父节点（元素也是节点，因此你可以解析元素）。
- `addAttribute(Attribute attribute)` - 将为元素添加一个属性。

`Attribute` 类有几个不同的构造函数。最简单的是 `Attribute(String name, String value)`。

一旦你将所有元素都添加到根元素中，你就可以将其转换为 `Document`。`Document` 的构造函数会接受一个 `Element` 作为参数。

你可以使用 `Serializer` 将你的 XML 写入文件。你需要在 `Serializer` 的构造函数中创建一个新的输出流。

`FileOutputStream fileOutputStream = new FileOutputStream(file); Serializer serializer = new Serializer(fileOutputStream, "UTF-8");`

`serializer.setIndent(4);`

`serializer.write(doc);`

## 示例

```java
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.UnsupportedEncodingException;
import nu.xom.Attribute;
import nu.xom.Builder;
import nu.xom.Document;
import nu.xom.Element;
import nu.xom.Elements;
import nu.xom.ParsingException;
import nu.xom.Serializer;

public class XMLWriter {
    public static void main(String[] args) throws UnsupportedEncodingException, IOException {
        // root元素 <example>
        Element root = new Element("example");

        // 创建一个存储人员的数组
        Person[] people = {new Person("Smith", "Dan", "years", "green", 23), new Person("Autry", "Bob", "months", "N/A", 3)};
        // 添加所有人员
        for (Person person : people) {
            // 创建主人员元素 <person>
            Element personElement = new Element("person");
```

```java
// 创建名字元素及其子元素：名字和姓氏
Element nameElement = new Element("name");
Element firstNameElement = new Element("first"); 
Element lastNameElement = new Element("last");
```

```java
// 创建年龄元素
Element ageElement = new Element("age");
// 创建喜颜色元素
Element favElement = new Element("fav_color");
```

```java
// 为名字添加值
firstNameElement.appendChild(person.getFirstName());
lastNameElement.appendChild(person.getLastName());
```

```java
// 为名字元素添加值
nameElement.appendChild(firstNameElement);
nameElement.appendChild(lastNameElement);
```

```java
// 为年龄添加值
ageElement.appendChild(String.valueOf(person.getAge()));
// 为年龄添加单位属性
ageElement.addAttribute("unit", person.getAgeUnit());
```

```java
// 为喜颜色添加值
favElement.appendChild(person.getFavoriteColor());
```

```java
// 将所有内容添加到人员元素
personElement.appendChild(nameElement);
personElement.appendChild(ageElement);
personElement.appendChild(favElement);
```

```java
// 将人员添加到根节点
root.appendChild(personElement); 
}
// 根据根节点创建文档
Document doc = new Document(root);
```

```java
// 将存储的文件
File file = new File("out.xml"); 
if (!file.exists())
    file.createNewFile();
```



```java
// 获取文件输出流
FileOutputStream fileOutputStream = new FileOutputStream(file);

// 使用 serializer 类写入所有内容
Serializer serializer = new Serializer(fileOutputStream, "UTF-8");
serializer.setIndent(4);
serializer.write(doc);

}

private static class Person {
    private String lName, fName, ageUnit, favColor; 
    private int age;

    public Person(String lName, String fName, String ageUnit, String favColor, int age) { 
        this.lName = lName; 
        this.fName = fName; 
        this.age = age; 
        this.ageUnit = ageUnit; 
        this.favColor = favColor; 
    }

    public String getLastName() { return lName; } 
    public String getFirstName() { return fName; } 
    public String getAgeUnit() { return ageUnit; } 
    public String getFavoriteColor() { return favColor; } 
    public int getAge() { return age; }
}
```

![](img/01cc8d6667542262308c820b3f5bd37b_856_0.png)

这将是 `"out.xml"` 的内容：

# 第 111 章：多态

多态是面向对象对象的核心概念之一。多态意味着“许多”和“形态”。实现多态的方法有两种方式：重载（Overloading）和重写（Overriding）。

## 第 111.1 节：重写

在子类中重写方法必须具备：

- 相同的方法名
- 基本类型情况下相同的返回类型
- 相同的参数类型和顺序

在 Java 中，在子类中重写方法时，它只能抛出父类方法中声明的异常。它也可以选择不抛出任何异常。参数名称并不重要。例如，`methodX(int i)` 等同于 `methodX(int k)`。

我们无法重写 `final` 或 `static` 方法。唯一可以改变的是方法体。

## 第 111.2 节：重载

方法重载，也称为函数重载，允许类拥有多个具有相同名称的方法，只要它们的参数数量或类型不同。

编译器通过检查方法签名来判断重载。

方法签名由三部分组成：

1. 方法名
2. 参数数量
3. 参数类型

如果类中任何两个方法的这三点都相同，则编译器将抛出**重复方法错误**。

这种多态被称为*静态*或*编译时*多态，因为编译器在编译期间就会根据参数列表决定要调用的适当方法。

重载方法可以是静态或非静态的。也不会影响方法重载。

```java
public class Polymorph {
  private static void methodOverloaded() {
    // 无参数，私静态方法
  }
}
```

```java
private int methodOverloaded(int i) {
  // 单参数私非静态方法返回 i;
}
```

```java
static int methodOverloaded(double d) {
  // 静态方法返回 0;
}
```

```java
public void methodOverloaded(int i, double d) {
  // 公非静态方法
}
```

此外，如果你更改了方法的返回值，我们无法将其视为方法重载。

```java
public class Polymorph {
  void methodOverloaded() {
    // 无参数且无返回值
  }
}
```

```java
int methodOverloaded() {
  // 无参数且 int 类型返回值返回 0;
}
```

## 第 11.3 节：多态与不同类型的重写

来自 Java 教程

多态的字典定义指的是生物学中的一个原理，即有机体或物种可以具有许多不同的形式或阶段。这一原理也可以应用于面向对象的编程和像 Java 这样的语言。类的子类可以定义自己独特的行为，同时共享父类的一些相同功能。

请看这个示例来理解不同类型的重写。

- 1. 基类不提供实现，子类必须重写整个方法 - (抽象)
- 2. 基类提供默认实现，子类可以更改行为
- 3. 子类通过在第一行调用 `super.methodName()` 对基类实现进行扩展
- 4. 基类定义了算法的结构（模板方法），子类将重写算法片段的一部分：

```java
import java.util.HashMap;
abstract class Game implements Runnable{
protected boolean runGame = true; protected Player player1 = null;
protected Player player2 = null; protected Player currentPlayer = null;

public Game() {
  player1 = new Player("Player 1"); player2 = new Player("Player 2");
  currentPlayer = player1;
  initializeGame();
}
```

> /* 类型 1：让子类定义自己的实现。基类定义抽象方法以强制子类定义实现 */

> /* 类型 2：子类可以更改行为。如果不更改，则适用基类的行为 */

```java
protected void logTimeBetweenMoves(Player player){
System.out.println("Base class: Move Duration: " + player.PlayerActTime + " - " + player.MoveShownTime);
}
```

> /* 类型 3：基类提供实现。子类可以通过在

```java
子类方法的第一行调用
super.methodName() 来增强实现，并在稍后提供特定的
实现 */
protected void logGameStatistics() { 
System.out.println("Base class: logGameStatistics");
}
```

```java
/* 类型 4：模板方法：基类的结构不能改变，但
子类可以拥有部分
行为 */
protected void runGame() throws Exception {
  System.out.println("Base class: Defining the flow for Game:");
  while (runGame) {
    /*
    1. 设置当前玩家
    2. 获取玩家移动
    */
    validatePlayerMove(currentPlayer);
    logTimeBetweenMoves(currentPlayer);
    Thread.sleep(500);
    setNextPlayer();
  }
  logGameStatistics();
}
```

```java
/* 模板方法的子部分，定义了子类的行为 */
protected abstract void validatePlayerMove(Player p);
```

```java
protected void runGame(boolean status) { this.runGame = status; }
public void setCurrentPlayer(Player p) { this.currentPlayer = p; }
```

```java
public void setNextPlayer() {
  if (currentPlayer == player1) { 
    currentPlayer = player2;
  }
  else
    currentPlayer = player1;
}
```

```java
}
public void run(){
  try{
    runGame();
  } catch(Exception err) { 
    err.printStackTrace();
  }
}
```

```java
class Player{
  String name;
  Player(String name){
    this.name = name; 
  }
  public String getName(){
    return name;
  }
}
```

```java
/* 具体实现 */
class Chess extends Game
  public Chess(){
    super();
  }
  public void initializeGame(){
    System.out.println("Child class: Initialized Chess game");
  }
  protected void validatePlayerMove(Player p){
    System.out.println("Child class: Validate Chess move: " + p.getName());
  }
  protected void logGameStatistics(){
    super.logGameStatistics();
    System.out.println("Child class: Add Chess specificGameStatistics:");
  }
}
```

```java
class TicTacToe extends Game{
    public TicTacToe(){
        super();
    }
    public void initializeGame(){
        System.out.println("Child class: Initialized TicTacToe game");
    }
    protected void validatePlayerMove(Player p) {
        System.out.println("Child class: Validate TicTacToe move:" + p.getName());
    }
}
```

```java
public class Polymorphism{
    public static void main(String[] args){} 
    try {
        Game game = new Chess(); 
        Thread t1 = new Thread(game); 
        t1.start();
        Thread.sleep(1000);

        game.setRunGame(false); 
        Thread.sleep(1000);

        game = new TicTacToe();
        Thread t2 = new Thread(game); 
        t2.start();
        Thread.sleep(1000);
        game.setRunGame(false);

    } catch(Exception err) {err.printStackTrace();}
}
```

输出：

```text
Child class: Initialized Chess game
Base class: Defining the flow for Game:
Child class: Validate Chess move:Player 1
Base class: Move Duration: player.PlayerActTime - player.MoveShownTime
Child class: Validate Chess move:Player 2
Base class: Move Duration: player.PlayerActTime - player.MoveShownTime
Base class: logGameStatistics:
Child class: Add Chess specificGameStatistics:
Child class: Initialized TicTacToe game
Base class: Defining the flow for Game:
Child class: Validate TicTacToe move:Player 1
Base class: Move Duration: player.PlayerActTime - player.MoveShownTime
Child class: Validate TicTacToe move:Player 2
Base class: Move Duration: player.PlayerActTime - player.MoveShownTime
Base class: logGameStatistics:
```

## 第 11.4 节：虚拟函数

虚拟方法是 Java 中非静态且前面没有关键字的方法。Java 中的所有方法默认都是虚拟的。虚拟方法在多态中起着重要作用，因为 Java 中的子类可以重写父类的方法，前提是被重写的方法是非静态且具有相同的签名。

然而，有一些方法不是虚拟的。例如，如果方法被声明为 `private` 或使用 `final` 关键字，那么该方法就不是虚拟。

考虑来自 StackOverflow 帖子“虚拟方法在 C# 和 Java 中是如何工作的？”的关于虚拟方法的继承的修改示例：

```java
public class A{
  public void hello(){
    System.out.println("Hello"); 
  }
  public void boo(){
    System.out.println("Say boo");
  }
}
public class B extends A{
  public void hello(){
    System.out.println("No"); 
  }
  public void boo(){
    System.out.println("Say haha");
  }
}
```

如果我们实例化类 `B` 并调用 `hello()` 和 `boo()`，我们将得到 `"No"` 和 `"Say haha"` 作为输出结果，因为 `B` 重写了 `A` 的相同方法。尽管上面的示例与重写几乎完全一样，但重要的是理解类 `A` 中的方法默认都是虚拟的。

此外，我们可以使用 `abstract` 关键字来实现虚拟方法。用 `abstract` 关键字声明的方法没有方法定义，这意味着方法体尚未实现。再次考虑上面的示例，只是 `boo()` 方法被声明为抽象：

```java
public class A {
  public void hello(){
    System.out.println("Hello");
  }
  abstract void boo();
  public class B extends A {
    public void hello(){
      System.out.println("No");
    }
    public void boo(){
      System.out.println("Say haha");
    }
  }
}
```

如果我们从 `B` 中调用 `boo()`，输出仍然是 `"Say haha"`，因为 `B` 继承了抽象方法 `boo()` 并让 `boo()` 输出 `"Say haha"`。

使用的来源及延伸阅读：

虚拟方法在 C# 和 Java 中是如何工作的？

查看这个优秀的答案，它为提供了关于虚拟函数的更完整的信息：在 Java 中写虚拟函数/方法吗？

## 第 11.5 节：通过添加类而不触碰现有代码来添加行为

```java
import java.util.ArrayList; import java.util.List;
import static java.lang.System.out;
public class PolymorphismDemo {
```



# 多态与封装

## 多态示例

以下代码展示了多态的基本用法：

```java
public static void main(String[] args) { 
    List<FlyingMachine> machines = new ArrayList<FlyingMachine>();
    machines.add(new FlyingMachine());
    machines.add(new Jet());
    machines.add(new Helicopter());
    machines.add(new Jet());

    new MakeThingsFly().letTheMachinesFly(machines); 
}
class MakeThingsFly {
    public void letTheMachinesFly(List<FlyingMachine> machines) {
        for (FlyingMachine flyingMachine : machines) {
            flyingMachine.fly();
        }
    }
}
class FlyingMachine {
    public void fly() {
        out.println("No implementation");
    }
}
class Jet extends FlyingMachine {
    @Override
    public void fly() {
        out.println("Start, taxi, fly");
    }
}
class Helicopter extends FlyingMachine {
    @Override
    public void fly() {
        out.println("Start vertically, hover, fly");
    }
}
```

**解释**

a) `MakeThingsFly`类可以与所有类型为`FlyingMachine`的对象协作。

b) 当你添加一个新类时（例如螺旋桨飞机`PropellerPlane`），`letTheMachinesFly`方法无需任何更改 (!) 即可工作：

```java
public void letTheMachinesFly(List<FlyingMachine> flyingMachines) { for (FlyingMachine flyingMachine : flyingMachines) { flyingMachine.fly(); }
}
```

这就是多态的力量。你可以用它来实现开闭原则。

## 第11章：封装

假设你有一个类，包含一些非常重要的变量，而它们被（其他程序员通过他们的代码）设置为了不可接受的值。他们的代码给你的代码引入了错误。作为OOP（面向对象编程）的解决方案，你允许对象的状态（存储在变量中）只能通过方法进行修改。隐藏对象的状态并通过对象的方法提供所有交互被称为"数据封装"。

## 第112.1节：通过封装维护不变性

一个类包含两个部分：接口和实现。

接口是类暴露的功能。它的公共方法和变量是接口的一部分。

实现是类的内部工作机制。其他类不需要知道类的实现细节。

封装是指向该类的任何用户隐藏该类的实现。这允许该类对其内部状态做出假设。

例如，来看这个表示角度（`Angle`）的类：

```java
public class Angle {
private double angleInDegrees;
private double angleInRadians;
```

```java
public static Angle angleFromDegrees(double degrees){
A a = new Angle();
a.angleInDegrees = degrees;
```

```java
a.angleInRadians = Math.PI*degrees/180;
return a;
}
```

```java
public static Angle angleFromRadians(double radians) {
Angle a = new Angle();
a.angleInRadians = radians;
a.angleInDegrees = radians* 180/Math.PI;
return a;
}
```

```java
public double getDegrees() {
return angleInDegrees;
}
```

```java
public double getRadians() {
return angleInRadians;
}
```

```java
public void setDegrees(double degrees) {
this.angleInDegrees = degrees;
this.angleInRadians = Math.PI*degrees/180;
}
```

```java
public void setRadians(double radians) {
this.angleInRadians = radians;
this.angleInDegrees = radians* 180/Math.PI;
}
```

```java
private Angle() {}
```

该类依赖于一个基本假设（或不变量）：`angleInDegrees`和`angleInRadians`始终保持同步。如果类成员是公共的，就无法保证这两个角度表示是关联的。

## 第112.2节：通过封装减少耦合

封装允许你对类进行内部更改，而不影响任何调用该类的代码。这减少了耦合，即任何给定类对另一个类实现的依赖程度。

例如，让我们改变上一个示例中`Angle`类的实现：

```java
public class Angle {
    private double angleDegrees;

    public static Angle angleFromDegrees(double degrees){
        Angle a = new Angle();
        a.angleDegrees = degrees;
        return a;
    }

    public static Angle angleFromRadians(double radians){
        Angle a = new Angle();
        a.angleDegrees = radians*180/Math.PI;
        return a;
    }

    public double getDegrees(){
        return angleDegrees;
    }

    public double getRadians(){
        return angleDegrees*Math.PI / 180;
    }

    public void setDegrees(double degrees) {
        this.angleDegrees = degrees;
    }

    public void setRadians(double radians) {
        this.angleDegrees = radians*180/Math.PI;
    }
```

```java
}
private Angle(){
}
```

该类的实现发生了更改，它现在只存储一种角度表示，并在需要时计算另一个角度。

然而，实现变了，但接口没有。如果调用类依赖于访问`angleInRadians`方法，则它需要修改以使用新版本的`Angle`。调用类

## 第13章：使用代理修改类

### 第13.1节：使用代理修改类

首先，确保代理在`Manifest.mf`中包含以下属性：

```
Redefine-Classes: true
Retransform-Classes: true
```

这不会调用加载代理中的`premain(String agentArgs, Instrumentation inst)`，而是调用`agentmain(String agentArgs, Instrumentation inst)`。这需要在代理`Manifest.mf`中设置`Agent-Class`。

```java
public static byte[] getBytes(ClassNode cn, boolean useMaxs) {
    ClassWriter cw = new ClassWriter(useMaxs);
    cn.accept(cw);
    byte[] b = cw.toByteArray();
    return b;
}
```

### 第13.2节：运行时添加代理

代理可以在运行时添加到JVM中。要加载代理，你需要使用Attach API的`VirtualMachine.attach(String id)`。然后你可以使用以下方法加载代理：

```java
public static void loadAgent(String agentPath) {
    String vmName = ManagementFactory.getRuntimeMXBean().getName();
    int index = vmName.indexOf('@');
    String pid = vmName.substring(0, index);
    try {
        File agentFile = new File(agentPath);
        VirtualMachine vm = VirtualMachine.attach(pid);
        vm.loadAgent(agentFile.getAbsolutePath(), "");
    } catch (Exception e) {
        throw new RuntimeException(e);
    }
}
```

### 第13.3节：设置基础代理

Premain类将包含`premain(String agentArgs, Instrumentation inst)`方法。

这是一个示例：

```java
import java.lang.instrument.Instrumentation;
public class PremainExample {
    public static void premain(String agentArgs, Instrumentation inst) {
        System.out.println(agentArgs);
    }
}
```

编译成jar文件后，打开Manifest并确保它具有`Premain-Class`属性。

这是一个示例：

```
Premain-Class: PremainExample
```

要在另一个Java程序`myProgram`使用该代理时，必须在JVM参数中定义代理：`java -javaagent:PremainAgent.jar jar myProgram.jar`

## 第114章：变长参数 (Varargs)

### 第114.1节：使用变长参数

在方法定义中使用变长参数作为参数时，可以传递数组或一系列参数。如果传递的是参数序列，它们会被自动转换为数组。

此示例展示了如何向`VarArgArray()`方法传递数组和参数序列，以及它们在方法内部的代码中是如何被同等对待处理的：

```java
// 使用数组：
int[] testArray = new int[]{10, 20};
obj.printVarArgArray(testArray);

System.out.println(" ");
// 使用参数序列
obj.printVarArgArray(5, 6, 5, 8, 6, 31);
```

输出：

```
10,20,
5,6,5,8,6,31
```

如果你像这样定义方法，将会产生编译错误。

`void method(String... a, int... b, int c){}` // 编译错误（不能多个变长参数）

`void method(int... a, String b){}` // 编译错误（变长参数必须是最后一个参数）

### 第114.2节：指定变长参数

```java
void doSomething(String... strings) {
  for (String s : strings) {
    System.out.println(s);
  }
}
```

最后一个参数类型后的三个点表示，该参数可以以数组的形式、也可以以参数序列的形式传递。变长参数只能出现在最后一个参数的位置。

## 第115章：日志 (java.util.logging)

### 第115.1节：记录复杂消息（高效地）

上面的示例看起来完全没问题，但许多程序员忘记了Java VM是栈机。这意味着所有方法的参数在执行该方法之前都会计算完毕。

这一事实对于Java日志至关重要，特别是对于记录低级别的日志，如默认禁用的`FINE`、`FINER`、`FINEST`。让我们查看`takeOrder()`方法的Java字节码。

`javap -c LoggingComplex.class`的结果如下：

```
public void takeOrder();
```

代码：

```
0: getstatic #27 // Field logger:Ljava/util/logging/Logger;
3: ldc #45 // String User %s ordered %d things (%d in total)
5: iconst_3
6: anewarray #3 // class java/lang/Object
9: dup
10: iconst_0
11: aload_0
12: getfield #40 // Field username:Ljava/lang/String;
15: astore
16: dup
17: iconst_1
18: aload_0
19: getfield #36 // Field orders:I
22: invokestatic #47 // Method java/lang/Integer.valueOf: (I)Ljava/lang/Integer;
25: astore
26: dup
27: iconst_2
28: aload_0
29: getfield #34 // Field I
32: invokestatic #47 // Method java/lang/Integer.valueOf: (I)Ljava/lang/Integer;
35: astore
36: invokestatic #53 // Method java/lang/String.format:(Ljava/lang/String;[Ljava;)Ljava/lang/String;
39: invokeevirtual #59 // Method java/util/logging/Logger.fine: (Ljava/lang/String;)JV
42: return
```

行39执行实际的日志记录。之前的所有工作（加载变量、创建新对象、在格式方法中拼接字符串）如果日志级别设置得高于`FINE`（默认如此），可能都是徒用功。这种日志记录可能非常低效，消耗不必要的内存和处理器资源。

这就是为什么你应该检查你想要使用的级别是否已启用。正确的做法应该是：

```java
public void takeOrder() {

  // 执行一些操作

  if (logger.isLoggable(Level.FINE)) {

    // 如果不需要则不执行任何操作

    logger.fine(String.format("User %s ordered %d things (%d in total)",

      username, orders, total));

    // 其他一些操作

  }

}
```

#### 自Java 8起：

`Logger`类拥有额外的接收`Supplier<String>`作为参数的方法，这可以通过lambda表达式简单提供：

```java
public void takeOrder() {

  // 执行一些操作

  logger.fine(() -> String.format("User %s ordered %d things (%d in total)",

    username, orders, total));

  // 其他一些操作

}
```

Suppliers的`get()`方法（在此例中为lambda）只有在相应的级别启用时才会被调用，因此不再需要构造。

### 第115.2节：使用默认日志器

此示例展示了如何使用默认日志API。

```java
import java.util.logging.Level;
import java.util.logging.Logger;

public class MyClass {

  // 获取当前类的日志器
  private static final Logger LOG =

  String s = "Hello World!";

  // 记录一个对象
  LOG.log(Level.FINER, "String s: {0}", s);

  // 记录多个对象
  LOG.log(Level.FINE, "String s: {0} has {1}", new Object[]{s, s.length()});
}
```



### 第 115.3 节：日志

Java Logging API 有 7 个级别。按降序排列级别为：
- `SEVERE`（值最高）
- `WARNING`
- `INFO`
- `CONFIG`
- `FINE`
- `FINER`
- `FINEST`（值最低）

默认级别是 `INFO`（但取决于虚拟机）。注意：还有 `OFF` 级别（用于关闭日志记录）。代码如下：

```java
import java.util.logging.Logger;

public class Levels {

    private static final Logger logger = Logger.getLogger(Levels.class.getName());

    public static void main(String[] args) {

        logger.severe("Message logged by SEVERE");

        logger.warning("Message logged by WARNING");

        logger.info("Message logged by INFO");

        logger.config("Message logged by CONFIG");

        logger.fine("Message logged by FINE");

        logger.finer("Message logged by FINER");

        logger.finest("Message logged by FINEST");

    }

}
```

```xml
<dependency org="log4j" name="log4j" rev="1.2.17"/>
```

使用 Gradle:
`compile group: 'log4j', name: 'log4j', version: '1.2.17'`

使用 Buildr:
`'log4j:log4j:jar:1.2.17'`

手动在路径构建中添加：从 Log4j 网站下载项目

### 第 116.3 节：设置属性文件

Log4j 允许你同时将数据日志到控制台和文件。创建一个 `log4j.properties` 文件并在其中放入以下基础配置：

# 根日志器 (Root logger)

```properties
log4j.rootLogger=DEBUG, stdout, file
```

# 将日志消息重定向到控制台

```properties
log4j.appender.stdout=org.apache.log4j.ConsoleAppender

log4j.appender.stdout.Target=System.out

log4j.appender.stdout.layout=org.apache.log4j.PatternLayout

log4j.appender.stdout.layout.ConversionPattern=%d{yyyy-MM-DD HH:mm:ss} %5p %c{1}:%L - %m%n
```

# 将日志消息重定向到日志文件，支持文件滚动。

```properties
log4j.appender.file=org.apache.log4j.RollingFileAppender

log4j.appender.file=C:\log4j-application.log

log4j.appender.file.MaxSize=5MB

log4j.appender.file.MaxBackupIndex=10

log4j.appender.file.layout=org.apache.log4j.PatternLayout

log4j.appender.file.layout.ConversionPattern=%d{yyyy-MM-DD HH:mm:ss} %5p %c{1}:%L - %m%n
```

如果你正在使用 Maven，请将此属性放在路径下：`/ProjectFolder/src/java/resources`

### 第 116.4 节：基础 `log4j2.xml` 配置文件

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Configuration>
  <Appenders>
    <Console name="STDOUT" target="SYSTEM_OUT">
      <PatternLayout pattern="%d %-5p [%t] %C{2} %m%n"/>
    </Console>
  </Appenders>
  <Loggers>
    <Root level="debug">
      <AppenderRef ref="STDOUT"/>
    </Root>
  </Loggers>
</Configuration>
```

这是一个基础的 `log4j.xml` 配置，包含一个控制台 appender 和一个根日志器。模式布局（pattern layout）指定了使用哪些模式来记录语句。为了调试 `log4j.xml` 的加载情况，你可以在 `log4j.xml` 的配置标签中添加 `status = <WARN | DEBUG | ERROR | FATAL | TRACE | INFO>` 属性。你还可以添加一个监控间隔（monitor interval），以便在指定的间隔后重新加载配置。`monitor interval = 30` 表示每 30 秒加载一次配置。

## 第 116.5 节：如何在 Java 代码中使用 Log4j

首先需要创建一个 `final static` 类型的 logger 对象：

```java
final static Logger logger = Logger.getLogger(classname.class);
```

然后调用日志方法：

```java
// 记录错误消息
logger.info("Information about some param: " + parameter); // 注意这行代码可能会抛出 NullPointerException！
```

```java
// 为了提高性能，建议使用 `isXXXEnabled()` 方法
if( logger.isEnabled()) {
    logger.info("Information about some param: " + parameter);
}
```

```java
// 在 log4j2 中，由于可读性，优先使用参数替换
// 参数替换仅在 info 级别激活时发生，这消除了使用 XXXEnabled() 的需求
logger.info("Information about some param: {}", parameter);
```

```java
// 记录异常
logger.error("Information about some error: ", exception);
```

## 第 116.6 节：从 log4j 1.x 迁移到 2.x

如果你想将项目中现有的 log4j 1.x 迁移到 log4j 2.x，请移除所有现有的 log4j 1.x 依赖并添加以下依赖：

### Log4j 1.x API 桥接

# Maven 构建

```xml
<dependencies>
  <dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-1.2-api</artifactId>
    <version>2.6.2</version>
  </dependency>
</dependencies>
```

# Ivy 构建

```xml
<dependencies>
  <dependency org="org.apache.logging.log4j" name="log4j-1.2-api" rev="2.6.2" />
</dependencies>
```

# Gradle 构建

```gradle
dependencies {
  compile group: 'org.apache.logging.log4j', name: 'log4j-1.2-api', version: '2.6.2'
}
```

### Apache Commons Logging 桥接

如果你的项目使用了使用 log4j 1.x 的 Apache Commons Logging，并且你想将其迁移到 log4j 2.x，请添加以下依赖：

# Maven 构建

```xml
<dependencies>
  <dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-1.2-api</artifactId>
    <version>2.6.2</version>
  </dependency>
</dependencies>
```

# Ivy 构建

```xml
<dependencies>
  <dependency org="org.apache.logging.log4j" name="log4j-1.2-api" rev="2.6.2" />
</dependencies>
```

# Gradle 构建

```gradle
dependencies {
  compile group: 'org.apache.logging.log4j', name: 'log4j-1.2-api', version: '2.6.2'
}
```

注意：使用 Apache logging

## 第 116.7 节：根据级别过滤

你可以使用大写字母和下划线来过滤（log4j 2.x）。示例级别：

```xml
<appender name="out" class="org.apache.log4j.ConsoleAppender">
  <layout class="org.apache.log4j.PatternLayout">
    <param value="%d{yyyy-MM-DD HH:mm:ss} %5p %c{1}:%L - %m%n"/>
  </layout>
</appender>
```

滚动：

```xml
<appender name="file" class="org.apache.log4j.RollingFileAppender">
  <param name="File" value="C:\log4j-application.log"/>
  <param name="MaxSize" value="5MB"/>
  <param name="MaxBackupIndex" value="10"/>
  <layout class="org.apache.log4j.PatternLayout">
    <param value="%d{yyyy-MM-DD HH:mm:ss} %5p %c{1}:%L - %m%n"/>
  </layout>
</appender>
```

## 第 17 章：命名规范

## Section 17.1：命名规范

### 包名

包名应为全小写，且不使用下划线或特殊字符。包名应以组织域名开头。使用复数。示例：`com.example.project`

### 类、接口和枚举名称

类和枚举名称通常为名词。接口名称通常为名词或以 `-able` 结尾的形容词。使用驼峰命名法（每个首字母大写）。匹配正则表达式 `^[A-Z][a-zA-Z0-9]*$`。示例：`ArrayList`, `BigInteger`, `ArrayOutOfBoundsException`, `Iterable`

### 方法名

方法名通常为动词或其他动作描述。匹配正则表达式 `^[a-z][a-zA-Z0-9]*$`。示例：`toString`, `hashCode`

### 变量

变量名应使用驼峰命名法（首字母小写）。匹配正则表达式 `^[a-z][a-zA-Z0-9]*$`。示例：`elements`, `currentIndex`

### 类型变量

对于涉及类型变量较少的情况，使用单个大写字母。匹配正则表达式 `^[A-Z][0-9]?$`。如果一个比另一个更有描述性（例如 map 中的 `K` 和 `V`，或函数的返回类型 `R`），则使用它，否则使用 `T`。对于单个类型变量变得混乱的复杂情况，使用全大写并用下划线分隔的长名称。示例：`T`, `V`, `SRC_VERTEX`

### 常量

常量（根据语言规则或约定不可变的 `static final` 字段）应使用全大写和下划线 (`_`) 命名。匹配正则表达式 `^[A-Z]|[A-Z0-9]*(_[A-Z0-9]+)*$`。示例：`BUFFER_SIZE`, `MAX_LEVEL`

### 其他命名指南

- 避免隐藏外层作用域的方法、变量和类型变量。
- 让命名的详细程度与作用范围的大小相关（例如，对于大型类的字段使用描述性名称，对于短寿命局部变量使用简短名称）。
- 在命名公共静态成员时，如果你认为它们会被静态导入，让标识符具有描述性。

### 第 117.2 节：类结构

类成员顺序

类成员应按以下顺序排列：

1. 字段（按公共、保护和私有排序）
2. 构造函数
3. 工厂方法
4. 其他方法（按公共、保护和私有排序）

并不强制按照访问修饰符或标识符对字段和方法进行排序。以下是这种顺序的示例：

```java
class Example {

    private int i;

    Example(int i) {
        this.i = i;
    }

    static Example getExample(int i) {
        return new Example(i);
    }

    @Override
    public String toString() {
        return "An example [" + i + "]";
    }
}
```

# 类成员分组

相关的字段应该放在一起。嵌套类型可以在第一次使用之前声明；否则，应该在字段之前声明。构造函数和重载方法应该根据功能分组，并按参数个数（arity）从小到大的顺序排序。这意味着这些构造结构之间的委托流在代码中是向下流。构造函数应该在一起，中间不要有其他成员。方法的重载变体应该在一起，中间不要有其他成员。

### 第 117.3 节：注解

声明性注解应该与被注解的声明另起一行。`@SuppressWarnings("unchecked")`

```java
public T[] toArray(T[]) typeHolder {
```

然而，如果为了提高可读性，注解单行方法的少量或简短注解可以与方法放在同一行。例如，可以这样写：

```java
@Nullable String getName() { return name; }
```

为了一致性和可读性，要么所有注解都放在同一行，要么每个注解都单独占一行。

// 坏掉的做法。

```java
@Deprecated @SafeVarargs
@CustomAnnotation
public final Tuple<T> extend(T... elements) {
```

// 更糟糕。

```java
@Deprecated @SafeVarargs
@CustomAnnotation public final Tuple<T> extend(T... elements) {
```

// 好的做法。

```java
@Deprecated @SafeVarargs
@CustomAnnotation
public final Tuple<T> extend(T... elements) {
```

// 好的做法。

```java
@Deprecated @SafeVarargs @CustomAnnotation public final Tuple<T> extend(T... elements) {
```

### 第 117.4 节：导入语句

```java
// 首先是 java/javax 包
import java.util.ArrayList;
import javax.tools.JavaCompiler;
```

```java
// 然后是第三方库
import com.fasterxml.xml.jackson.annotation.JsonProperty;
```

```java
// 然后是项目导入
import com.example.my.package.ClassA;
import com.example.my.package.ClassB;
```

```java
// 然后是静态导入（与上述顺序相同）
import static java.util.stream.Collectors.toList;
```

导入语句应该排序……

- 主要按非静态/静态排序，非静态导入在前。
- 其次按包的来源排序，遵循以下顺序：
    - `java` 包
    - `javax` 包
    - 外部包（例如 `org.xml`）
    - 内部包（例如 `com.sun`）
- 再次按包名和类标识符的字典顺序排序。

导入语句不应换行，无论其是否超过了推荐的最大单行长度。不应存在未使用的导入。

# 通配符导入

通常情况下不应使用通配符导入。当导入大量密切相关的类时（例如在对具有数十个不同“节点”类的树实现访问者模式时），可以使用通配符导入。在任何情况下，每个文件使用的通配符导入不应超过一个。

# 117.5 节：大括号

```java
class Example {

    void method(boolean error) {

        if (error) {

            Log.error("Error occurred!");
```



# 117.5 节：大括号

```java
System.out.println("Error!");
} else { // 因为另一个块使用了大括号，所以这里也使用。
    System.out.println("No error");
}
```

左大括号应该放在当前行的末尾，而不是单独占一行。除非块是空的（见下方的“短形式”），否则右大括号前面应该换行。即使语言允许可选，也建议使用大括号，例如单行的 `if` 和 `for` 循环体。

如果一个块跨越多行（包括注释），则必须使用大括号。如果 `if/else` 语句中的一个块使用了大括号，则另一个块也必须使用。如果该块位于嵌套块的最后，则它必须使用大括号。

`else`、`catch` 以及 `do...while` 循环中的 `while` 关键字应该与前一个块的右大括号在同一行。

## 短形式

```java
enum Response { YES, NO, MAYBE }

public boolean isReference() { return true; }
```

上述建议旨在提高统一性（并增加熟悉度/可读性）。在某些情况下，偏离上述指南的“短形式”同样具有可读性，并可以使用。这些情况包括简单的枚举声明、微小的方法和 `lambda` 表达式。

# 117.6 节：冗余括号

```java
return flag ? "yes" : "no";

String cmp = (flag1 != flag2) ? "not equal" : "equal";
```

```java
// 不要这样做
return (flag ? "yes" : "no");
```

如果能提高可读性，可以使用冗余的分组括号（即不影响求值的括号）。在涉及常用运算符的较短表达式中，通常应省略冗余分组括号，但在较长的表达式或涉及优先级和关联性不明确的运算符的表达式中予以保留。

`return` 之后的整个表达式不能被括号包围。

# 117.7 节：修饰符

```java
class ExampleClass {
    // 避免使用 'public' 和 'abstract'
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

```java
interface ExampleInterface {
    // 方法不是 static
    void sayHello();
}
```

修饰符应该遵循以下顺序：

- 访问修饰符（`public` / `private` / `protected`）
- `static`
- `final`
- `transient`
- `volatile`
- `default`
- `synchronized`
- `native`
- `strictfp`

除非提高可读性，否则应省略参数类型。如果 `lambda` 表达式超过几行，考虑创建一个方法。除非有理由，否则字段不应该是 `final`。

# 117.8 节：缩进

缩进级别为四个空格。只能使用空格字符缩进。禁止使用 `Tab`。空行不应缩进。（这由末尾空格规则隐含。）`case` 行应缩进四个空格，`case` 内部语句再缩进四个空格。

```java
switch (var) {
    case TWO:
        setChoice("two");
        break;
    case THREE:
        setChoice("three");
        break;
    default:
        throw new IllegalArgumentException();
}
```

请参考语句换行了解如何缩进。

# 117.9 节：字面量

```java
long l = 5432L;

int i = 0x123 + 0xABC;
```

```java
byte b = 0b1010;

float f1 = 1 / 5432f;

float f2 = 0.123e4f;

double d1 = 1 / 5432;

double d2 = 0x1.3p2;
```

`long` 字面量应使用大写 `L` 后缀。十六进制字面量应使用大写字母 `A-F`。所有其他数值前缀、后缀应使用小写字母。

# 117.10 节：包声明

`package com.example.my.package;`

包声明不应换行，无论其是否超过了推荐的最大单行长度。

# 117.11 节：Lambda 表达式

```java
Runnable r = () -> System.out.println("Hello World");

Supplier<String> c = () -> "Hello World";
```

```java
// Collection::contains 是一个简单的单元方法，其行为从文中很清楚。这里优先使用方法引用。
appendFilter(goodStrings::contains);

// 在这种情况下，lambda 表达式比简单的 tempMap::put 更容易理解
trackTemperature((time, temp) -> tempMap.put(time, temp));
```

表达式型 `lambda` 优于单行块型 `lambda`。通常情况下方法引用优于 `lambda` 表达式。对于绑定的实例方法引用或参数个数大于一的方法，`lambda` 表达式可能更容易理解，因此更优先。特别是当方法的行为从上下文中不明确时。

# 117.12 节：Java 源文件

所有行必须以换行符（`LF`，ASCII 值为 10）结束，而不是 `CR` 或 `CR+LF`。行末尾不允许有额外的空白字符。

源文件的名称必须与其包含的类名相同，并带有 `.java` 扩展名，即使对于只包含包私有类（`package private class`）的文件也是如此。这不适用于不包含类声明的文件，例如 `package-info.java`。

# 117.13 节：语句换行

源代码和注释每行通常不应超过 80 个字符，如果超过也不应超过 100 个字符（包括缩进）。

字符限制必须根据具体情况进行判断。真正重要的是行的语义“密度”和可读性。将行变得无故地过长会使其难以阅读；同样，“英雄式地”尝试将它们挤进 80 列也可能导致难以阅读。这里概述的灵活性旨在让开发者避免这些极端，而不是为了最大限度利用显示器空间。

`URL` 或示例命令不应换行。

```java
// 即使缩进后可能超过最大行宽，也没关系。
Error e = isTypeParam? Errors.InvalidRepeatableAnnotationNotApplicable(targetContainerType, on):Errors.InvalidRepeatableAnnotationNotApplicableInContext(targetContainer).
```

```java
// 换行更好
String pretty = Stream.of(args)
    .map(Argument::prettyPrint).collect(Collectors.joining(", "));
```

```java
// 对最大行宽的解释过于严苛。影响了可读性。
Error e = isTypeParam? Errors.InvalidRepeatableAnnotationNotApplicable(targetContainerType, on): Errors.InvalidRepeatableAnnotationNotApplicableInContext(targetContainerType);
```

```java
// 即使符合字符限制，也应该换行
String pretty =
Stream.of(args).map(Argument::prettyPrint).collect(Collectors.joining(", "));
```

在较高的语法级别进行换行优于在较低的语法级别进行换行。每行最多应有一语句。延续行应按以下四种方式进行缩进：

# 117.14 节：方法声明换行

```java
int someMethod(String aString,
List<Integer> aList,
Map<String, String> aMap,
int anInt,
long aLong,
Set<Number> aSet,
double aDouble) {
...
}
```

```java
int someMethod(String aString, List<Integer> aList, Map<String, String> aMap, int anInt, long aLong, double aDouble, long aLong()) {
...
}
```

```java
int someMethod(String aString,
List<Map<Integer, StringBuffer>> aListOfMaps, Map<String, String> Map)
```

```java
throws IllegalArgumentException {
...
int someMethod(String aString, List<Integer> aList, Map<String, String> MMap, int anInt) throws IllegalArgumentException { ... }
}
```

方法声明可以通过垂直列出参数，或者通过换行并增加 8 个额外的空格来格式化。如果需要换行 `throws` 子句，请将换行符放在 `throws` 子句之前，并确保它与参数列表区分开，可以通过相对于函数声明缩进 +8 空，或相对于上一行缩进 +8 空来实现。

# 117.15 节：表达式换行

如果某行接近最大字符限制，始终考虑将其拆分为多个语句/表达式，而不是直接换行。在运算符之前换行。在 `.` 链方法调用之前换行。

```java
popupMsg("Inbox notification: You have " + newMsgs + " new messages");

// 不要这样做！看起来像两个参数
popMsg("Inbox notification: You have " + newMsgs + " new messages");
```

# 117.16 节：空白字符

## 垂直空白

应使用单个空行来分隔……

- 包声明
- 类声明
- 构造函数
- 方法
- 静态初始化器
- 实例初始化器

……并可分隔逻辑分组：

- `import` 语句
- 字段
- 语句

多个连续的空行仅应用于分隔相关的组，而不应作为标准的成员间分隔符。

## 水平空白

应使用单个空格来分隔……

关键字之后、运算符之前和逗号之后。关键字之前、运算符之前和逗号之前。

# 第 117 节：特殊字符

（注：原文此处存在大量重复性文本，已按常规逻辑处理）

# 第 119 节第 2 节：实现 hashCode() 方法

为了方便地实现对象的 `hashCode` 方法，你可以使用 `HashCodeBuilder` 类。

选择字段：

```java
@Override
public int hashCode() {
    HashCodeBuilder builder = new HashCodeBuilder();
    builder.append(field1);
    builder.append(field2);
    builder.append(field3);
    return builder.hashCode();
}
```

使用反射：

```java
@Override
public int hashCode() { return HashCodeBuilder.reflectionHashCode(this, "field1", "field2"); }
```

# 第 119 节第 3 节：实现 toString() 方法

为了方便地实现对象的 `toString` 方法，你可以使用 `ToStringBuilder` 类。

选择字段：

```java
@Override
public String toString() {
    ToStringBuilder builder = new ToStringBuilder(this);
    builder.append(field1);
    builder.append(field2);
    builder.append(field3);
    return builder.toString();
}
```

示例结果：
`ar.com.jonat.lang.MyClass@dd7123[<null>,0,false]`

显式地为字段命名：

```java
@Override
public String toString() {
    StringBuilder builder = new StringBuilder(this);
    builder.append("field1", field1);
    builder.append("field2", field2);
    builder.append("field3", field3);
    return builder.toString();
}
```

示例结果：
`ar.com.jonat.lang.MyClass@dd7404[field1=<null>,field2=0,field3=false]`

你可以通过参数更改样式：

```java
@Override
public String toString() {
    StringBuilder builder = new StringBuilder(this, ToString.MULTI_LINE_STYLE);
    builder.append("field1", field1);
    builder.append("field2", field2);
    builder.append("field3", field3);
    return builder.toString();
}
```

示例结果：
`ar.com.bna.lang.MyClass@ebbf5c[field1=<null>
field2=0
field3=false]`

这里有一些样式，例如 `JSON`、不包含类名、简短格式等 ...

通过反射：

```java
@Override
public String toString() {
  return StringBuilder.reflectionToString(this); 
}
```

你也可以指定样式：

```java
@Override
public String toString() {
  return StringBuilder.reflectionToString(this, ToString.JSON_STYLE);
}
```

# 第 120 节：本地化与国际化

## 第 120 节第 1 节：区域设置（Locale）

`java.util.Locale` 类用于表示一个“地理、政治或文化”区域，以便对特定的文本、数字、日期或操作进行本地化。`Locale` 对象可能包含国家、地区、语言，以及语言的变体，例如某个国家特定地区使用的方言，或者在语言源地以外的其他国家所使用的方言。

`Locale` 实例被传递给需要本地化其操作的组件，无论它是转换输入、输出，还是仅用于内部操作。`Locale` 类本身不能执行任何国际化或本地化。

### 语言（Language）

语言必须是 ISO 639 2 或 3 字符语言代码，或者是长度最多 8 个字符的注册语言子标记。如果一种语言同时有 2 字符和 3 字符语言代码，请使用 2 字符代码。可以在 IANA 语言子标记注册表中找到语言代码的全列表。

语言代码不区分大小写，但 `Locale` 类始终使用语言代码的小写版本。

### 创建区域设置（Creating a Locale）

可以通过四种不同的方式创建 `java.util.Locale` 实例：

- `Locale` 常量
- `Locale` 构造函数
- `Locale.Builder` 类
- `Locale.forLanguageTag` 工厂方法

# Java 资源包（ResourceBundle）

你可以像这样创建一个 `ResourceBundle` 实例：

```java
Locale locale = new Locale("en", "US");
ResourceBundle labels = ResourceBundle.get("i18n.properties");
System.out.println(labels.getString("message"));
```

假设我有一个属性文件 `i18n.properties`：
`message=This is locale`

使用其他语言设置状态，可以使用 `setDefault()` 方法。其用法为：`setDefault(Locale.JAPANESE); //Japanese`

# 第 120 节第 2 节：使用 "locale" 自动格式化日期

`SimpleDateFormat` 在急用时非常好，但正如其名所示，它的扩展性并不好。如果你在应用程序到处硬编码 `"MM/dd/yyyy"`，用户将不会开心的。让 Java 为你工作吧。

使用 `DateFormat` 中的静态方法来为桌面应用程序获取正确的格式（你将依赖默认区域设置），只需调用：

```java
String localizedDate = DateFormat.getInstance(style).format(date);
```

其中 `style` 是 `DateFormat` 中指定的格式化常量（`FULL`, `LONG`, `SHORT` 等）之一。对于用户在请求中指定其区域设置的服务器端应用程序，你应该显式地传递它：

```java
String localizedDate = DateFormat.getInstance(style, request.getLocale()).format(date);
```



# 第 120 节第 3 节：字符串比较

忽略大小写地比较两个字符串：
`"School".equalsIgnoreCase("school"); // true`
`text1.toLowerCase().equals(text2.toLowerCase());`

不同语言在转换大小写方面有不同的规则。在英语中，'I' 会被转换为 'i'。但在土耳其中，'I' 变成 'ı'。

尊重自然语言并忽略大小写对字符串排序（使用排序器 collation）：
```java
Collator collator = Collator.getInstance(Locale.GERMAN);
collator.setStrength(Collator.PRIMARY);
collator.equals("Garten", "garten"); // returns true
```

# 第 121 节：使用 Fork/Join 进行并行编程

## 第 121 节第 1 节：Java 中的 ForkJoin 

Java 中的 fork/join 框架非常适用于可以分成更小部分并并行解决的问题。fork/join 问题的根本步骤是：
- 将问题划分为多个部分
- 并行解决每个部分
- 将每个子解决方案合并为一个整体解决方案

`ForkJoinTask` 是定义此类问题的接口。通常期望你会是它的实现的一个子类（通常是 `RecursiveTask`），而不是直接实现接口。在这个示例中，我们将使用一个整数集合，一直划分直到批处理大小不再超过：

```java
import java.util.List;
import java.util.concurrent.RecursiveTask;

public class SummingTask extends RecursiveTask<Integer> {

    private static final int MAX_BATCH_SIZE = 10;

    private final List<Integer> numbers;

    private final int minInclusive, maxExclusive;

    public SummingTask(List<Integer> numbers) {
        this(numbers, 0, numbers.size());
    }

    // 构造函数在内部作为划分过程
    private SummingTask(List<Integer> numbers, int minInclusive, int maxExclusive) {
        this.numbers = numbers;
        this.minInclusive = minInclusive;
        this.maxExclusive = maxExclusive;
    }

    @Override
    protected Integer compute() {
        if (maxExclusive - minInclusive > MAX_BATCH_SIZE) {
            // 对于单个批处理来说太大，我们分为两个任务
            int mid = (minInclusive + maxExclusive) / 2;
            SummingTask leftTask = new SummingTask(numbers, minInclusive, mid);
            SummingTask rightTask = new SummingTask(numbers, mid, maxExclusive);

            // 将左任务提交到 ForkJoinPool
            leftTask.fork();

            // 在当前线程运行右任务并获取结果
            int rightResult = rightTask.compute();

            // 等待左任务完成并获取结果
            int leftResult = leftTask.join();

            // 合并结果
            return leftResult + rightResult;
        } else {
            // 对于单个批处理是允许的，我们在这里运行它并
            int sum = 0;
            for (int i = minInclusive; i < maxExclusive; i++) {
                sum += numbers.get(i);
            }
            return sum;
        }
    }

    public int sumup(final List<Integer> ints);
}
```

这强调了 `sumup` 方法不会更改 `ints`。

### 内部类访问

如果你的匿名内部类想要访问变量，该变量应该标记为 `final`：

```java
public IPrintName printName() {
    String name;
    return new IPrintName() {
        @Override
        public void printName() {
            System.out.println(name);
        }
    };
}
```

此类无法编译，因为变量 `name` 不是 `final`。

### 版本 ≥ 8

有效 `final` 变量是一个特例。这些是只写入一次且可以变为 `final` 的局部变量。有效 `final` 变量也可以从匿名类访问。

### final static 变量
尽管下面的代码在 `static final` 变量不是 `static` 的情况下完全合法的，但它不会编译：

```java
class TestFinal {
    private static List foo; 

    public Test() {
        foo = new ArrayList();
    }
}
```

原因是，让我们重复一遍，`final` 变量不能重新赋值。由于 `foo` 是静态的，它是 `TestFinal` 类的所有实例共享的。当创建 `TestFinal` 类的新实例时，构造函数会被调用，因此 `foo` 被重新赋值，编译器不允许这样做。在这种情况下初始化变量 `foo` 的正确方法之一是：

```java
class TestFinal {
    private final List foo = new ArrayList();
}
```

或使用静态初始化器：

```java
class TestFinal {
    private static final List foo;
    static {
        foo = new ArrayList();
        //..
    }
}
```

当基类实现了某些重要功能，而派生类不应该更改它时，`final` 方法非常有用。它们也比非 `final` 方法更快，因为不涉及虚方法表的概念。

Java 中所有的包装类都是 `final` 的，例如 `Integer`、`Long` 等。这些类的创建者不希望任何人能够将 `Integer` 继承到自己的类并更改 `Integer` 类的基本行为。使一个类变为不可变的类之一是子类不能重写方法。实现这一点的最简单方法是将该类声明为 `final`。

### 第 122.2 节：static

`static` 关键字用于类、方法或字段，使它们的工作独立于该类的任何实例。

静态字段是类的所有实例共有的。访问它们不需要实例。静态方法可以在没有所属类实例的情况下运行。然而，它们只能访问该类的静态字段。静态类可以在其他类内部声明。实例化时不需要其所属类的实例。

```java
public class TestStatic {
    static int staticVariable;

    static {
        // 此代码块在类首次加载时运行
        staticVariable = 11;
    }

    int nonStaticVariable = 5;

    static void doSomething() {
        // 我们可以从静态方法中访问静态变量
        staticVariable = 10;
    }

    void add() {
        // 我们可以从非静态方法中访问静态和非静态变量
        nonStaticVariable += staticVariable;
    }

    static class StaticInnerClass {
        int number;

        public StaticInnerClass(int _number) {
            number = _number;
        }

        void doSomething() {
            // 我们可以访问 number 和 staticVariable，但不能访问 nonStaticVariable
            number += staticVariable;
        }

        int getNumber() {
            return number;
        }
    }
}

// 静态字段和方法
TestStatic object1 = new TestStatic();
System.out.println(object1.staticVariable); // 11
System.out.println(TestStatic.staticVariable); // 11

TestStatic.doSomething();

TestStatic object2 = new TestStatic();
System.out.println(object1.staticVariable); // 10
System.out.println(object2.staticVariable); // 10
System.out.println(TestStatic.staticVariable); // 10

object1.add();
System.out.println(object1.nonStaticVariable); // 15
System.out.println(object2.nonStaticVariable); // 10

// 静态内部类
StaticInnerClass object3 = new TestStatic.StaticInnerClass(100);
StaticInnerClass object4 = new TestStatic.StaticInnerClass(200);
System.out.println(object3.getNumber()); // 100
System.out.println(object4.getNumber()); // 200

object3.doSomething();
System.out.println(object3.getNumber()); // 110
System.out.println(object4.getNumber()); // 200
```

### 第 122.3 节：abstract

抽象是一个隐藏实现细节并仅向用户展示功能的过程。抽象类永远无法实例化。如果一个类被声明为 `abstract`，那么它的唯一目的就是为了被类扩展。

```java
abstract class Car {
    abstract void tagLine();
}

class Honda extends Car {
    void tagLine() {
        System.out.println("Start Something Special"); 
    }
}

class Toyota extends Car {
    void tagLine() {
        System.out.println("Start Something Special"); 
    }
}
```

## 第 122.4 节：strictfp

`strictfp` 修饰符用于确保浮点运算在不同平台上结果的一致性。在 Java 5 之后，所有方法默认都是 `strictfp` 的。

```java
strictfp Calculator {
    // ...
}
```

## 第 122.5 节：volatile

`volatile` 关键字用于标记一个字段可能会被多个线程修改。它保证了所有线程读取的字段都是最新的值。

```java
class Shared {
    volatile boolean flag = false;
}
```

## 第 122.6 节：synchronized

`synchronized` 关键字用于确保在一个时刻只有一个线程可以执行代码块或方法。

```java
class Counter {
    private int count = 0;

    synchronized void increment() {
        count++;
    }
}
```

### 第 122.7 节：transient

`transient` 关键字用于标记一个字段在序列化时不被包含。

```java
class Session implements Serializable {
    private transient String password;
}
```

## 第 123 章：Process

`Runtime.exec(String)` 和 `ProcessBuilder` 方法允许你执行外部进程。在第一个版本中，你以字符串的形式提供命令和参数。第二个版本看起来非常简单，但存在一些陷阱。

首先，这是一个安全使用 `exec` 的示例：

```java
Process p = Runtime.exec("mkdir /tmp/testDir");
p.waitFor();
if (p.exitValue() == 0) {
  System.out.println("created the directory");
}
```

### 陷阱：exec(String)路径中的空格

假设我们扩展上面的示例以便创建一个任意目录：

```java
Process p = Runtime.exec("mkdir " + dirPath); 
```

这通常可以工作，但如果 `dirPath` 是例如 `/home/user/My Documents`，就会失败。问题在于 `exec(String)` 通过查找空格来分割命令和参数。命令字符串为：

```
"mkdir /home/user/My Documents"
```

会被拆分为：

```
"mkdir", "/home/user/My", "Documents"
```

这将导致 `mkdir` 命令失败因为它期望一个参数而不是两个。面对这种情况，一些程序员尝试给路径加上引号。这不起作用：

```
"mkdir \"/home/user/My Documents\""
```

会被拆分为：

```
"mkdir", "/home/user/My", "Documents\""
```

为了对空格引号而添加的额外双引号字符被视为任何其他非空格字符。事实上，无论我们不对空格加引号或转义都会失败。解决这个特定问题的方法是使用 `exec(String, ...)` 重载方法。

```java
Process p = Runtime.exec("mkdir", dirPath);
```

如果 `dirpath` 包含空格字符，这将非常有效，因为 `exec` 的这个重载不会尝试分割参数。

### 重定向、管道和其他语法

假设我们想要重定向外部命令的输入或输出，运行一个管道。例如：

```java
Process p = Runtime.exec("find -name *.java -print 2>/dev/null");
```

或者

```java
Process p = Runtime.exec("find source -name *.java | xargs grep package");
```

（第一个示例列出文件系统中所有的 Java 文件名称，第二个示例打印 `source` 树中 Java 文件的包语句。）

这些操作不会按预期方式工作。在第一情况下，`find` 命令将带有 `2>/dev/null` 作为命令参数运行。它不会被解释为重定向。在第二个示例中，管道字符 (`|`) 及其随后的后续内容将被传递给 `find` 命令。

这里的问题是 `exec` 方法和 `ProcessBuilder` 并不理解任何 shell 语法。这包括重定向、管道、通配符（globbing）、变量扩展等。在某些情况下（例如，简单的重定向），你可以轻松地使用 `ProcessBuilder` 实现所需的效果。然而，这在通常情况下并不成立。另一种替代方法是在 shell 中运行命令行；例如：

```
Process p = Runtime.exec("bash", "-c",
"find / -name *.java 2>/dev/null");
```

```
Process p = Runtime.exec("bash", "-c",
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



```java
public static void main(String[] args) {
  Runnable r = () -> System.out.println("Hello world"); 
  new Thread(r).start();
}
```

## Runnable 与 Thread 子类

`Runnable` 对象的用法更为通用，因为 `Runnable` 对象可以子类 `Thread` 以外的类。

在简单应用程序中，`Thread` 子类更易使用，但受限于你的类必须是 `Thread` 的后代的限制。

`Runnable` 对象适用于高层线程管理 API。

### 第 126.8 节：创建基础死锁系统

当两个竞争的执行者等待对方完成，而永远永远完成时，就会发生死锁。在 Java 中，每个对象都关联有一个锁。为了避免多个线程对单个对象进行并发修改，我们可以使用 `synchronized` 关键字，但一切都是代价的。错误地使用 `synchronized` 关键字会导致系统卡死，称为死锁系统。

考虑有 2 个线程在 1 个实例上工作，我们称它们为 First 和 Second，假设我们有 2 个资源 R1 和 R2。First 获取了 R1，且完成需要 R2，而 Second 获取了 R2，完成需要 R1。

假设在时间 t=0 时，First 拥有 R1，Second 拥有 R2。现在 First 正在等待 R2，而 Second 正在等待 R1。等待是无限期的，这导致了死锁。

```java
public class Example2
public static void main(String[] args) throws InterruptedException { 
  final DeadLock.dl = new DeadLock();
  Thread t1 = new Thread(new Runnable() {
      @Override
      public void run() {
        // TODO Auto-generated method stub
        dl.methodA();
      }
  });
  Thread t2 = new Thread(new Runnable() {
      @Override
      public void run() {
        // TODO Auto-generated method stub
        try {
          dl.method2();
        } catch (InterruptedException e) { // TODO Auto-generated catch block
          e.printStackTrace();
        }
      }
  t1.setName("First");
  t2.setName("Second");
  t1.start();
  t2.start();
}

class DeadLock {
  Object mLock1 = new Object(); Object mLock2 = new Object();

  public void methodA() {
    System.out.println("methodA wait for mLock1 " + 
    Thread.currentThread().getName()); synchronized (mLock1) {
      System.out.println("methodA mLock1 acquired " + 
      Thread.currentThread().getName()); try {
        Thread.sleep(100);
        method2();
      } catch (InterruptedException e) {
        // TODO Auto-generated catch block
        e.printStackTrace();
      }
    }

    public void method2() throws InterruptedException {
      System.out.println("method2 wait for mLock2 " + 
      Thread.currentThread().getName()); synchronized (mLock2) {
        System.out.println("method2 mLock acquired " +
        Thread.currentThread().getName()); Thread.sleep(100);
        method3();
      }
    }
    public void method3() throws InterruptedException {
      System.out.println("method3 mLock1 " +
      Thread.currentThread().getName()); synchronized (mLock1) {
        System.out.println("method3 mLock1 acquired " + Thread.currentThread().getName()); 
      }
    }
}
```

此程序的输出：

`methodA wait for mLock1 First method2 wait for mLock2 Second`

`methodA mLock1 acquired First method3 mLock1 Second`

`method2 mLock acquired Second method3 mLock1 acquired`

## 第 126.9 节：创建基础线程

在 Java 中创建线程有两种方法。基本上，创建线程就像编写代码一样简单。第一方法使用 `Runnable` 接口及其唯一的方法 `run()` 定义代码。

```java
class MyThread implements Runnable {
  @Override
  public void run() {
    for (int i = 0; i < 10; i++) {
      System.out.println("Thread running!");
    }
  }
}
Thread t1 = new Thread(new MyThread());
```

第二方法是子类 `Thread`。`Thread` 类还包含一个接受字符串的构造函数，该字符串将用作线程名称。

```java
class MyThread extends Thread {
  MyThread(String name) { super(name); }
@Override
public void run() {
    for (int i = 0; i < 10; i++) {
      System.out.println("Thread running!");
    }
  }
}
MyThread t2 = new MyThread("Greeting");
```

或者，你可以使用 Lambda 表达式或方法引用创建线程（仅限 Java 8）：线程。由于我们已经定义了代码，可以简单地创建：

```java
Thread t3 = new Thread(() -> {
  for (int i = 0; i < 10; i++) {
    System.out.println("Thread running!");
  }
});
```

### 第 126.10 节：原子操作

原子操作是一种“一次性”全部执行的操作，在原子操作执行期间，其他线程没有观察或修改状态的机会。

让我们考虑一个错误的范例。

```java
private static int t = 0;
```

```java
public static void main(String[] args) {
    ExecutorService executorService = Executors.newFixedThreadPool(400); //
高线程数是为了演示之目的。
    for (int i = 0; i < 100; i++) {
        executorService.execute(() -> {
            t++;
            System.out.println(MessageFormat.format("t: {0}", t));
        });
    }
    executorService.shutdown();
}
```

在这种情况下，存在两个问题。第一个问题是后增操作符不是原子的。它由多个操作组成：获取值、将值加 1、设置值。这就是为什么如果我们运行这个示例，很可能在输出中看不到看到 `t: 100` - 两个线程可能会并发获取值并对其进行递增，假设 `t` 的值为 10，且两个线程都在递增 `t`。两个线程都会将 `t` 的值设置为 11，因为第二个线程在第一个线程完成操作之前观察到了 `t` 的值。

第二个问题在于我们观察 `t` 的方式。当我们打印 `t` 的值时，该值可能在该线程执行递增操作之后已经被另一个线程更改了。

为了解决这些问题，我们将使用 `java.util.concurrent.atomic.AtomicInteger`，它提供了许多原子操作供我们使用。

```java
private static AtomicInteger t = new AtomicInteger(0);
public static void main(String[] args) {
    ExecutorService executorService = Executors.newFixedThreadPool(400); //
高线程数是为了演示之目的。
    for (int i = 0; i < 100; i++) {
        executorService.execute(() -> {
            int currentT = t.incrementAndGet();
            System.out.println(MessageFormat.format("t: {0}", currentT));
        });
    }
    executorService.shutdown();
}
```

`AtomicInteger` 的 `incrementAndGet` 方法以原子方式递增并返回新值，消除了之前的竞态条件。请注意，在这个示例中，行仍然是无序的，因为我们没有尝试对 `println` 调用进行排序，而且这超出了本示例的范围，因为这需要同步，而本示例的目标是展示如何使用 `AtomicInteger` 来消除关于状态的竞态条件。

## 第 126.11 节：独斥写/并发读访问

有时需要进程并发地读写同一个“数据”。

`ReadWriteLock` 接口及其 `ReentrantReadWriteLock` 实现允许如下所示的访问模式：

- 1. 数据可以有任意数量的并发读者。如果至少有一个读者访问被授予，则不存在可能的写访问。

- 2. 数据最多可以有一个的写入者。如果授予了写访问，则任何读者都无法访问数据。

实现可能如下：

```java
import java.util.concurrent.locks.ReadWriteLock;
import java.util.concurrent.locks.ReentrantReadWriteLock;

public class Sample {
    // 构造函数允许“公平性”设置，这保证了锁属性的顺序。
    protected static final ReadWriteLock RW_LOCK = new ReentrantReadWriteLock();

    // 这是一个需要为并发访问保护的典型数据
    protected static int data = 0;

    /** 这将以独占访问的方式写入数据 */
    public static void writeToData() {
        RW_LOCK.writeLock().lock();
        try {
            data++;
        } finally {
            RW_LOCK.writeLock().unlock();
        }
    }

    public static int readData() { 
        RW_LOCK.readLock().lock();
        try {
            return data;
        } finally {
            RW_LOCK.readLock().unlock();
        }
    }
}
```

注 1：这种精确的用例使用 `AtomicInteger` 有更简洁的解决方案，但这里描述的是一种访问模式，无论这里的数据是否具有原子变体的整数，该模式都有效。

注 2：读取部分的锁实际上是需要的，尽管对于普通读者来说可能并不像。事实上，如果你不在读者侧进行加锁，可能会发生任何问题，包括：

- 1. 原始类型值的写入在所有 JVM 上都不保证是原子的，因此如果 `data` 是 64 位的类型，读者可能只看到 64 位写入中的 32 位。

- 2. 对于未执行写入的线程，写入操作的可见性只有当我们在写和读之间建立了“先于先”（Before-Before）关系时才由 JVM 保证。这种关系在读者和写者都使用各自的锁时建立，否则不会建立。

版本 ≥ Java SE 8

在需要更高性能的情况下，在某些特定用法下，有一种更快的锁类型，称为 `StampedLock`。

## 第 126.11 节：独斥写/并发读访问

有时需要进程并发地读写同一个“数据”。

`ReadWriteLock` 接口及其 `ReentrantReadWriteLock` 实现允许如下所示的访问模式：

- 1. 数据可以有任意数量的并发读者。如果至少有一个读者访问被授予，则不存在可能的写访问。

- 2. 数据最多可以有一个的写入者。如果授予了写访问，则任何读者都无法访问数据。

实现可能如下：

```java
import java.util.concurrent.locks.ReadWriteLock;
import java.util.concurrent.locks.ReentrantReadWriteLock;

public class Sample {
    // 构造函数允许“公平性”设置，这保证了锁属性的顺序。
    protected static final ReadWriteLock RW_LOCK = new ReentrantReadWriteLock();

    // 这是一个需要为并发访问保护的典型数据
    protected static int data = 0;

    /** 这将以独占访问的方式写入数据 */
    public static void writeToData() {
        RW_LOCK.writeLock().lock();
        try {
            data++;
        } finally {
            RW_LOCK.writeLock().unlock();
        }
    }

    public static int readData() { 
        RW_LOCK.readLock().lock();
        try {
            return data;
        } finally {
            RW_LOCK.readLock().unlock();
        }
    }
}
```

注 1：这种精确的用例使用 `AtomicInteger` 有更简洁的解决方案，但这里描述的是一种访问模式，无论这里的数据是否具有原子变体的整数，该模式都有效。

注 2：读取部分的锁实际上是需要的，尽管对于普通读者来说可能并不像。事实上，如果你不在读者侧进行加锁，可能会发生任何问题，包括：

- 1. 原始类型值的写入在所有 JVM 上都不保证是原子的，因此如果 `data` 是 64 位的类型，读者可能只看到 64 位写入中的 32 位。

- 2. 对于未执行写入的线程，写入操作的可见性只有当我们在写和读之间建立了“先于先”（Before-Before）关系时才由 JVM 保证。这种关系在读者和写者都使用各自的锁时建立，否则不会建立。

版本 ≥ Java SE 8

在需要更高性能的情况下，在某些特定用法下，有一种更快的锁类型，称为 `StampedLock`。

## 第 126.12：生产者-消费者

一个简单的生产者-消费者示例。注意 JDK 类（`AtomicBoolean` 和 `BlockingQueue`）被用于同步，这与 `ReadWriteLock` 的工作方式大不相同。选择不同的实现会极大地改变此示例的行为（如 `DelayQueue` 或 `PriorityQueue`）。



```java
class Producer implements Runnable {
    private final BlockingQueue<ProducedData> queue;

    public Producer(BlockingQueue<ProducedData> queue) {
        this.queue = queue;
    }

    @Override
    public void run() {
        int producedCount = 0;
        try {
            while (true) {
                queue.put(new ProducedData());
                producedCount++;
            }
        } catch (InterruptedException e) {
            System.out.println("Produced " + producedCount);
        }
    }
}

class Consumer implements Runnable {
    private final BlockingQueue<ProducedData> queue;

    public Consumer(BlockingQueue<ProducedData> queue) {
        this.queue = queue;
    }

    @Override
    public void run() {
        int consumedCount = 0;
        try {
            while (true) {
                ProducedData data = queue.poll(10, TimeUnit.MILLISECONDS);
                if (data != null) {
                    consumedCount++;
                }
            }
        } catch (InterruptedException e) {
            System.out.println("Consumed " + consumedCount);
        }
    }
}

class ProducedData {
}

public class ProducerConsumerExample {
    public static void main(String[] args) throws InterruptedException {
        BlockingQueue<ProducedData> queue = new ArrayBlockingQueue<>(1000);
        Thread producer = new Thread(new Producer(queue));
        Thread consumer = new Thread(new Consumer(queue));

        producer.start();
        consumer.start();

        Thread.sleep(1000);
        producer.interrupt();
        Thread.sleep(10);
        consumer.interrupt();
    }
}
```

## 第 126.13 节：在使用 synchronized / volatile 时可视化读/写屏障

```java
class Counter {
    private Integer count = 10;

    public synchronized void incrementCount() {
        count++;
    }

    public Integer getCount() {
        return count;
    }
}
```

正如我们知道的，我们应该使用`synchronized`关键字来确保方法或块执行的独斥。但我们中可能没有人注意到使用`synchronized`的一个或重要方面：除了使代码单元原子化外，它还提供了读/写屏障。让我们通过示例来讨论这一点。

为了理解这种行为，我们需要了解 Java 内存模型如何与硬件架构集成。在 Java 中，每个线程都有自己的线程栈。该栈包含：调用栈和在该线程中创建的局部变量。在多核系统中，两个线程很有可能在不同的核心上并发运行。在这种情况下，线程栈的部分可能位于核心的寄存器/缓存中。

通过`synchronized`（或`volatile`）关键字进行访问，在`synchronized`块之后，线程会将其本地变量副本与主内存同步。这创建了一个读/写屏障，并确保线程看到该对象的最新值。

在我们的情况下，由于线程 B 没有使用`synchronized`访问`count`，它可能会引用存储在寄存器中的`count`值，并且可能永远看不到来自线程 A 的更新。为了确保 B 看到`count`的最新值，我们需要将`getCount()`也标记为`synchronized`。

```java
public synchronized Integer getCount() { return count; }
```

当线程 A 完成对`count`的更新后，它会释放`Counter`实例，同时创建一个写屏障并将块内部的所有更改刷新到主内存。同样，当线程 B 获取同一个`Counter`实例的锁时，它进入读屏障，从主内存读取`count`的值并看到所有更新。

**线程 A**

- 获取锁
- 递增`count`
- 将所有内容刷新到主内存
- 释放锁
- 用主内存更新其本地副本

**线程 B**

- 获取锁
- 读取`count`
- 释放锁

同样的可见性效果适用于`volatile`读/写。在写入`volatile`变量之前更新的所有变量都会被刷新到主内存，在读取`volatile`变量之后的所有读取都将来自主内存。

## 节 126.14：获取由程序启动的所有线程（排除系统线程）的状态

代码片段：

```java
import java.util.Set;
public class main ThreadStatus {
    public static void main(String[] args) throws Exception {
        for (int i = 0; i < 5; i++) {
            Thread t = new Thread(new MyThread());
            t.setName("MyThread:" + i);
            t.start();
        }

        int threadCount = 0;
        Set<Thread> threadSet = Thread.getAllStackTraces().keySet();
        for (Thread t : threadSet) {
            if (t.getThreadGroup() == Thread.currentThread().getThreadGroup()) {
                System.out.println("Thread " + t + ":" + "state:" + t.getState());
                ++threadCount;
            }
        }
        System.out.println("Thread count started by Main thread:" + threadCount);
    }
}

class MyThread implements Runnable {
    public void run() {
        try {
            Thread.sleep(2000);
        } catch (Exception err) {
            err.printStackTrace();
        }
    }
}
```

输出：

```
Thread:Thread[MyThread:1,5,main]:state:TIMED_WAITING
Thread:Thread[MyThread:3,5,main]:state:TIMED_WAITING
Thread:Thread[main,5,main]:state:RUNNABLE
Thread:Thread[MyThread:4,5,main]:state:TIMED_WAITING
Thread:Thread[MyThread:0,5,main]:state:TIMED_WAITING
Thread:Thread[MyThread:2,5,main]:state:TIMED_WAITING
Thread count started by Main thread:6
```

解释：

`Thread.getAllTraces().keySet()`返回所有线程，包括应用线程和系统线程。如果你对对线程感兴趣，可以通过检查特定线程的线程组（Thread Group）是否与你的主程序匹配来遍历线程集。

在没有上述`ThreadGroup`条件的情况下，程序将返回以下系统线程的状态：

`Reference Handler`, `Signal Dispatcher`, `Attach Listener`, `Finalizer`

## 节 126.15：使用 ThreadLocal

Java 并发中一个实用的工具是`ThreadLocal`它允许你拥有一个对于给定线程唯一的变量。因此，如果相同的代码在不同的线程中运行，这些执行将不会共享该值，而是每个线程都有自己的局部于该线程的变量。

例如，这经常被用于在 servlet 中处理请求时建立上下文（如授权信息）。你可以像下面这样操作：

```java
private static final ThreadLocal<MyUserContext> contexts = new ThreadLocal<>();
```

```java
public static MyUserContext getContext() {
    return contexts.get(); // 返回对此线程唯一的变量
}
```

```java
public void doGet(...) {
    MyUserContext context = magicGetContextRequest(request);
    contexts.put(context); // 将该上下文保存到我们的线程本地 - 其他线程不会

    // 确保此调用不会覆盖我们的 
    try {
        // 业务逻辑
    } finally {
        contexts.remove(); // “确保”移除线程本地变量
    }
}
```

现在，与其将`MyUserContext`传递到每一个方法中，你可以在需要的地方使用`Servlet.getContext()`。当然，这引入了一个需要编写文档的变量，但它是线程安全的，这消除了使用极高作用域变量的许多缺点。这里的关键优势是每个线程在`contexts`中都有自己的本地局部变量。只要你从定义的入口点使用它（例如通过添加 servlet 过滤器），你就可以依靠该上下文一直存在。

## 节 126.16：带有共享队列的多个生产者/消费者示例

生产者和消费者线程共享全局队列。

```java
import java.util.concurrent.*;
import java.util.Random;

public class ProducerConsumerES {
    public static void main(String[] args) {
        BlockingQueue<Integer> sharedQueue = new LinkedBlockingQueue<>();
        ExecutorService pes = Executors.newFixedThreadPool(2);
        ExecutorService ces = Executors.newFixedThreadPool(2);

        pes.submit(new Producer(sharedQueue, 1));
        pes.submit(new Producer(sharedQueue, 2));
        ces.submit(new Consumer(sharedQueue, 1));
        ces.submit(new Consumer(sharedQueue, 2));

        pes.shutdown();
        ces.shutdown();
    }
}

/* 生产者持续产生整数流到共享队列，所有生产者共享 */
class Producer implements Runnable {
    private final BlockingQueue<Integer> sharedQueue;
    private final int threadNo;
    private Random random = new Random();

    public Producer(BlockingQueue<Integer> sharedQueue, int threadNo) {
        this.threadNo = threadNo;
        this.sharedQueue = sharedQueue;
    }

    @Override
    public void run() {
        // 生产者每 200 毫秒产生一个
        while (true) {
            try {
                int number = random.nextInt(1000);
                System.out.println("Produced: " + number + ":by thread:" + threadNo);
                sharedQueue.put(number);
            } catch (Exception err) {
                err.printStackTrace();
            }
        }
    }
}

/* 消费者持续从共享队列获取数据，所有消费者共享线程 */
class Consumer implements Runnable {
    private final BlockingQueue<Integer> sharedQueue;
    private final int threadNo;

    public Consumer(BlockingQueue<Integer> sharedQueue, int threadNo) {
        this.threadNo = threadNo;
        this.sharedQueue = sharedQueue;
    }

    @Override
    public void run() {
        // 消费者从共享队列获取
        while (true) {
            try {
                int num = sharedQueue.take();
                System.out.println("Consumed: " + num + ":by thread:" + threadNo);
            } catch (Exception err) {
                err.printStackTrace();
            }
        }
    }
}
```

*(注：由于原文提供的代码示例在 126.16 部分存在逻辑错乱和重复，翻译时已根据代码逻辑进行了结构化还原，以符合标准的生产者-消费者模型描述，并保留了核心意图)*

由于原文文本在最后代码部分存在严重的格式重复和逻辑混乱，上述翻译是基于代码逻辑的修正性翻译。

任务。

2. 如果你使用的是 Java 7 及更早版本，你将使用匿名类而不是 lambda 来实现任务。

### 第 126.18 节：暂停执行

`Thread.sleep`会导致当前线程暂停执行指定的时间。这是为应用程序的其他线程或其他可能运行在计算机系统上的其他应用程序提供处理器时间的有效手段。`Thread`类中有两个重载的`sleep`方法。

一个是指定到毫秒的睡眠时间：

```java
public static void sleep(long millis) throws InterruptedException
```

另一个是指定到纳秒的睡眠时间：

```java
public static void sleep(long millis, int nanos)
```

暂停执行 1 秒：

```
Thread.sleep(1000);
```

需要注意的是，这是对操作系统内核调度器的一个提示。这并不一定是精确的，某些实现甚至不考虑纳秒参数（可能会四舍五入到最近的毫秒）。

建议将`Thread.sleep`的调用封装在`try/catch`块中并捕获`InterruptedException`。

### 第 126.19 节：线程中断 / 停止线程



每个 Java `Thread` 都有一个中断标记，初始状态为 `false`。中断一个线程本质上只是将该标记设置为 `true`。运行在该线程上的代码可以偶尔检查该标记并根据其采取行动。代码也可以忽略它。但为什么每个 `Thread` 都需要这样一个标记呢？毕竟，如果需要的话，在线程上设置一个布尔标记是我们完全可以自己组织的事。嗯，某些方法在它们所运行的线程被中断时会表现出特殊的行为。

这些方法被称为“阻塞方法”（blocking methods）。这些方法会将线程置于 `WAITING` 或 `TIMED_WAITING` 状态。当线程处于这种状态时，中断它将导致被中断线程抛出一个 `InterruptedException`，而不是将中断标记设置为 `true`，线程会重新变为 `RUNNABLE` 状态。调用阻塞方法的代码被迫处理 `InterruptedException`，因为它是一个检查异常（checked exception）。因此（也因此得名），中断可以产生中断等待的效果，从而有效地结束等待。请注意，并不是所有处于等待状态的方法（例如阻塞 I/O）都会以这种方式响应中断，因为它们没有将线程置于等待状态。最后，一个中断标记被设置的线程进入阻塞方法（即尝试进入等待状态）时，会立即抛出 `InterruptedException` 并清除中断标记。

除了这些机制外，Java 没有为中断分配任何语义含义。代码可以自由按照任何喜欢的方式解释中断。但大多数情况下，中断用于向线程发出信号，让它在方便时尽快停止运行。但正如上述所示，取决于该线程上的代码如何恰当地响应中断以停止运行。停止线程是一个协作过程。当线程被中断时，其运行代码可能处于堆栈轨迹的深几层之处。大多数代码不会调用阻塞方法，并且结束得足够及时，不会过度延迟线程的停止。最应该关注对中断具有响应性的代码，是那些在循环中处理任务直到没有任务为止，或者设置了信号停止该循环的标记的代码。处理可能无限任务的循环（即它们会一直运行直到结束）应该检查中断标记以退出循环。对于有限循环，语义可能规定在结束之前必须完成所有任务，或者留一些任务未处理可能是恰当的。调用阻塞方法的代码将被迫处理 `InterruptedException`。如果语义上可行，它可以简单地传播 `InterruptedException` 并声明抛出它。这样，对于其调用者来说，它本身变成了一个阻塞方法。如果它无法传播异常，至少应该设置中断标记，以便堆栈上层的调用者也知道线程已被中断。在某些情况下，方法无论是否发生 `InterruptedException` 都需要继续等待，在这种情况下，它可能会延迟到完成后再设置中断标记，这可能涉及设置一个局部变量，在退出方法之前对其进行检查，然后中断其线程。

# 示例：

在中断时停止处理任务的代码示例：

```java
class TaskHandler implements Runnable {
    private final BlockingQueue<Task> queue;

    TaskHandler (BlockingQueue<Task> queue) { 
        this.queue = queue;
    }

    @Override
    public void run() {
        while (!Thread.currentThread().isInterrupted()) { // 中断标记
            // 中断时退出循环
            try {
                Task task = queue.take(); // 阻塞调用，对中断响应
                handle(task)
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt(); // 无法抛出 InterruptedException
                // (由于 Runnable 接口的限制) 所以通过设置标记来指示中断
            }
        }
    }

    private void handle(Task task) { // 实际处理
}
```

在完全完成后才延迟设置中断标记的代码示例：

```java
class MustFinishHandler implements Runnable {
    private final BlockingQueue<Task> queue;

    MustFinishHandler (BlockingQueue<Task> queue) { 
        this.queue = queue;
    }

    @Override
    public void run() {
        boolean shouldInterrupt = false;
        while (true) {
            try {
                Task task = queue.take();
                if (task.isEndOfOfTasks()) {
                    if (shouldInterrupt) {
                        Thread.currentThread().interrupt();
                    }
                    return;
                }
                handle(task);
            } catch (InterruptedException e) {
                shouldInterrupt = true;
            }
        }
    }

    private void handle(Task task) {
 }
```

具有固定任务列表但可能提前退出的代码：

```java
class GetAsPossible implements Runnable {
    private final List<Task> tasks = new ArrayList<>();
    @Override
    public void run() {
        for (Task task : tasks) {
            if (Thread.currentThread().isInterrupted()) {
                return;
            }
            handle(task);
        }
    }
}
```

# 第127 章：Executor、ExecutorService 和线程池

Java 中的 `Executor` 接口提供了一种将任务提交与运行机制（包括调度等）解耦的方法。`Executor` 通常用于替代显式创建线程。使用 `Executor` 开发者不需要重写代码即可调整程序的执行策略。

### 第 127.1 节：ThreadPoolExecutor

一种常见的 `Executor` 是 `ThreadPoolExecutor`，它负责线程处理。你可以配置执行器在无任务时维护的最小线程数（核心大小），以及当工作较多时可以增长的最大大小。当负载下降时，池的大小会逐渐减少回到核心大小。

```java
ThreadPoolExecutor pool = new ThreadPoolExecutor(
    1, // 保持一个就绪线程
    5, // 最多并行执行五个 Runnable/Thread
    1, TimeUnit.MINUTES, // 超过池时，空闲线程在一分钟后终止
    ArrayBlockingQueue<Runnable>(10)); // 待处理的任务保存在在这里
);
```

```java
pool.execute(new Runnable() {
    @Override
    public void run() {
        // 运行的代码
    }
});
```

**注意** 如果你为 `ThreadPoolExecutor` 配置了无界队列，那么线程数不会超过 `corePoolSize`，因为只有在队列满时才会创建新线程：

带有所有参数的 `ThreadPoolExecutor`：

```java
ThreadPoolExecutor(int corePoolSize, int maximumPoolSize, long keepAliveTime, TimeUnit unit, BlockingQueue<Runnable> workQueue, ThreadFactory threadFactory, RejectedExecutionHandler handler)
```

来自 JavaDoc

如果运行线程超过 `corePoolSize` 但少于 `maximumPoolSize`，只有在队列满时才会创建新线程。

优点：

- 2. 在 `ThreadPoolExecutor.CallerRunsPolicy` 中，调用 `execute` 的线程自己执行任务。这提供了一种简单的反馈控制机制，减慢提交新任务的速度。

- 3. 在 `ThreadPoolExecutor.DiscardPolicy` 中，无法执行的任务直接丢弃。

- 4. 在 `ThreadPoolExecutor.DiscardOldestPolicy` 中，如果执行器未关闭，工作队列头部的任务将被丢弃，然后重试（这可能再次失败，导致重复）。

- 3. 可以配置自定义的 `ThreadFactory`，这是非常有用的：

- 1. 设置更具描述性的线程名称

- 2. 设置线程守护状态

- 3. 设置线程优先级

以下是如何使用 `ThreadPoolExecutor` 的示例：

## 章节 127.2：从计算中获取值 - Callable

如果你的计算产生了后续需要使用的返回值，那么简单的 `Runnable` 任务是不够的。在这种情况下，你可以使用 `ExecutorService.submit(Callable<T>)`，它会在执行后返回一个值。

服务将返回一个 `Future`，你可以用它获取任务执行的结果。

```java
// 提交一个可 用于执行
ExecutorService pool = anExecutorService;
Future<Integer> future = pool.submit(new Callable<Integer>() {

    @Override public Integer call() {
        // 执行一些计算
        return new Random().nextInt();
    }
});
// 当 future 在另一个线程中执行时，执行其他任务
```

当你需要获取 `future` 的结果时，调用 `future.get()`：

无限等待 `future` 完成并获得结果。

```java
try {
    // 阻塞当前线程直到 future 完成
    Integer result = future.get();
} catch (InterruptedException | ExecutionException e) { 
    // 妥善处理异常
}
```

等待 `future` 完成，但最长不应超过指定的时间。

```java
try {
    // 阻塞当前线程最多 500 毫秒。 
    // 如果 future 在此完成，则返回结果，
    // 否则将抛出 TimeoutException。
    Integer result = future.get(500, TimeUnit.MILLISECONDS);
} catch (InterruptedException | ExecutionException | TimeoutException e) {
    // 妥善处理异常 
}
```

如果不再需要已调度或正在运行的任务结果，你可以调用 `Future.cancel(boolean)` 来将其取消。

调用 `cancel(false)` 仅会将该任务从待执行任务队列中移除。调用 `cancel(true)` 如果任务正在运行，则会中断该任务。

## 章节 127.3：submit() 与 execute() 的异常处理差异

通常情况下，`execute()` 命令用于“发后即忘”的调用（不需要分析结果），而 `submit()` 命令用于分析 `Future` 对象的结果。

我们应该注意这两个命令之间在异常处理机制上的关键区别。

如果你不捕获异常，来自 `submit()` 的异常将会会被框架吞掉（swallowed）。

用于理解差异的代码示例：

情况 1：使用 `execute()` 命令提交 `Runnable`，它会报告异常。

```java
import java.util.concurrent.*;
import java.util.*;

public class ExecuteSubmitDemo {
    public ExecuteSubmitDemo() {
        System.out.println("creating service");
        ExecutorService service = Executors.newFixedThreadPool(2);
        //ExtendedExecutor executorService = new ExtendedExecutor();
        for (int i = 0; i < 2; i++) {
            service.execute(new Runnable() {
                public void run() {
                    int a = 4, b = 0;
                    System.out.println("a and b=" + a + ":" + b);
                    System.out.println("a/b:" + (a / b));
                    System.out.println("Thread Name in Runnable after divide by zero:"+Thread.currentThread().getName());
                }
            });
        }
        service.shutdown();
    }

    public static void main(String args[]){
        ExecuteSubmitDemo demo = new ExecuteSubmitDemo();
    }
}

class ExtendedExecutor extends ThreadPoolExecutor {
    public ExtendedExecutor() {
        super(1, 1, 60, TimeUnit.SECONDS, new ArrayBlockingQueue<Runnable>(100));
    }

    // / ...
    protected void afterExecute(Runnable r, Throwable t) {
        super.afterExecute(r, t);
        if (t == null && r instanceof Future<?>) {
            try {
                Object result = ((Future<?>) r).get();
            } catch (CancellationException ce) {
                t = ce;
            } catch (ExecutionException ee) {
                t = ee.getCause();
            } catch (InterruptedException ie) {
                Thread.currentThread().interrupt(); // 忽略/重置
            }
        }
        if (t != null) {
            System.out.println(t);
        }
    }
}
```

输出：

```
creating service
a and b=4:0
a and b=4:0
Exception in thread "pool-1-thread-1" Exception in thread "pool-1-thread-2"
java.lang.ArithmeticException : / by zero
at ExecuteSubmitDemo$1.run(ExecuteSubmitDemo.java:15)
at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:2)
at java.util.concurrent.ThreadPoolExecutor.Worker.run(ThreadPoolExecutor.java:5)
at java.util.Thread.run(Thread.java:744)
java.lang.ArithmeticException : / by zero
at ExecuteSubmitDemo$1.run(ExecuteSubmitDemo.java:15)
```



`at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:5)`

`at java.util.concurrent.ThreadPoolExecutor.Worker.run(ThreadPoolExecutor.java:5)`

`at java.util.Thread.run(Thread.java:744)`

**情况 2**：将`execute()`替换为`submit()`：`service.submit(new Runnable()){`

在这种情况下，由于`run()`方法没有显式捕获异常，异常会被框架吞掉。

输出：

```
creating service
a and b=4:0
a and b=4:0
```

**情况 3**：将`execute()`替换为`submit()`：`service.submit(new Runnable()){`

在这种情况下，由于`run()`方法没有显式捕获异常，异常会被框架吞掉。

输出：

```
creating service
a and b=4:0
a and b=4:0
```

**情况 4**：将`execute()`替换为`submit()`：`service.submit(new Runnable()){`

在这种情况下，由于`run()`方法没有显式捕获异常，异常会被框架吞掉。

输出：

```
creating service
a and b=4:0
a and b=4:0
```

3. 在`ThreadPoolExecutor.DiscardPolicy`中，无法执行的任务将被直接丢弃。

4. 在`ThreadPoolExecutor.DiscardOldestPolicy`中，如果执行器未关闭，则工作队列头部的任务将被丢弃，然后重试执行（这可能会再次失败，导致此过程重复）。

如果你想模拟`CountDownLatch`的行为，可以使用`invokeAll()`方法。

+ 4. 还有一种你没有引用的机制：`ForkJoinPool`

`ForkJoinPool`在 Java 7 中被引入 Java。`ForkJoinPool`类似于 Java 的`ExecutorService`，但有一点不同。`ForkJoinPool`让任务能够轻松将其工作拆分为更小的任务，然后这些任务也会被提交给`ForkJoinPool`。在`ForkJoinPool`中，当空闲的线程从繁忙的线程那里“窃取”任务时，就会发生工作窃取。

Java 8 在`ExecutorService`中引入了一个新的 API 来创建工作窃取池。你不需要创建`RecursiveTask`和`RecursiveAction`，但仍然可以使用`ForkJoinPool`。

```
public static ExecutorService newWorkStealingPool()
创建一个使用所有可用处理器作为目标并行级别的工作窃取线程池。
```

默认情况下，它将取 CPU 核心数作为参数。这四个机制都是相互补充的。根据你想要控制的粒度，你必须选择正确的机制。

## Section 127.7: 等待 ExecutorService 中所有任务完成

让我们来看看等待提交给 Executor 的任务完成的各种选项。

+ 1. `ExecutorService.invokeAll()`

执行给定的任务，并返回一个`Future`列表，当所有任务完成后，它们持有任务的状态和结果。

示例：

```java
import java.util.concurrent.*; import java.util.*;
```

```java
public class InvokeAllDemo {
    public InvokeAllDemo(){
        System.out.println("creating service");
        ExecutorService service = Executors.newFixedThreadPool(Runtime.getRuntime().availableProcessors());
        List<MyCallable> futureList = new ArrayList<MyCallable>();

        for (int i = 0; i < 10; i++) {
            MyCallable myCallable = new MyCallable((long)i);
            futureList.add(myCallable);
        }
        System.out.println("Start");
        try {
            List<Future<Long>> futures = service.invokeAll(futureList);
        } catch (Exception err) {
            err.printStackTrace();
        }
        System.out.println("Completed");
        service.shutdown();
    }

    public static void main(String args[]) {
        InvokeAllDemo demo = new InvokeAllDemo();
    }

    class MyCallable implements Callable<Long> {
        Long id = 0L;
        public MyCallable(Long val) {
            this.id = val;
        }
        public Long call() {
            // 添加你的业务逻辑
            return id;
        }
    }
}
```

## 2. CountDownLatch

一种同步辅助工具，允许一个或多个线程等待其他线程中执行的一组操作完成。

`CountDownLatch`使用给定的计数初始化。`await`会阻塞直到由于调用`countDown`方法导致计数变为零，之后所有等待的线程将被释放，任何随后的`await`调用将立即返回。这是一个一次性现象——计数无法重置。如果你需要一个可以重置计数的版本，请考虑使用`CyclicBarrier`。

+ 3. `Executors`中的`ForkJoinPool`或`newWorkStealingPool()`

+ 4. 遍历提交到`ExecutorService`后创建的所有`Future`对象

+ 5. Oracle `ExecutorService`文档页推荐的关闭方式：

```java
void shutdownAndAwaitTermination(ExecutorService pool) {
    pool.shutdown(); // 禁止提交新任务
    try {
        // 等待现有任务终止
        if (!pool.awaitTermination(60, TimeUnit.SECONDS)) {
            pool.shutdownNow(); // 取消当前正在执行的任务
            // 等待任务对取消做出响应
            if (!pool.awaitTermination(60, TimeUnit.SECONDS))
                System.err.println("Pool did not terminate");
        }
    } catch (InterruptedException ie) {
        // (如果当前线程也被中断，则（重）取消)
        pool.shutdownNow();
        // 保留中断状态
        Thread.currentThread().interrupt();
    }
}
```

`shutdown()`: 启动有序关闭，在此期间将执行之前提交的任务，但不再接受新任务。

`shutdownNow()`: 尝试停止所有正在执行的任务，停止处理等待执行的任务，并返回等待执行的任务的任务列表。

在上面的示例中，如果你的任务完成需要更多时间，你可以将条件更改为`while`条件：

将

```
if (!pool.awaitTermination(60, TimeUnit.SECONDS))
```

替换为

```
while (!pool.awaitTermination(60, TimeUnit.SECONDS)) {
    Thread.sleep(60000);
}
```

## 127.8: 不同类型 ExecutorService 的用例

`Executors`

- 返回满足特定所需的类型线程池。

- 1. `public static ExecutorService newSingleThreadExecutor()`

创建一个使用单个工作线程在无界队列上运行的执行器

`fixedThreadPool(1)`和`newSingleThreadExecutor()`之间存在区别，正如 Java 代码对后者所述：除非等价的`fixedThreadPool(1)`，否则返回的执行器保证无法配置为使用额外的线程。

这意味着`fixedThreadPool`可以在程序以后通过此处重新配置：`((ThreadPoolExecutor) fixedThreadPool.setMaximumPoolSize(10))`。这对于`newSingleThreadExecutor`是不可行的。

用例：

- 1. 你只需要一个线程

- 2. 你需要一个可以重置计数的版本，考虑使用`CyclicBarrier`。（此处省略部分原文说明）

（注：后续部分原文包含大量重复的 OCR 错误说明，已根据要求保留核心逻辑并翻译）

- 1. 有效利用可用核心。`nThreads`使用`Runtime.getRuntime().availableProcessors()`

- 2. 当你决定线程不应超过

- 1. `public static ExecutorService newCachedThreadPool()`

创建一个需要时创建新线程，但在可用时复用之前构建线程的线程池

用例：

- 1. 用于短生命周期异步任务

缺点：

- 1. 无界队列是有害的

- 2. `public static ScheduledExecutorService newScheduledThreadPool(corePoolSize)`

创建一个可以在给定延迟后调度命令运行或定期执行命令的线程池

用例：

- 1. 处理带有延迟的循环事件，这些事件将在未来按一定间隔发生

缺点：

- 1. `public static ExecutorService newWorkStealingPool()`

创建一个使用所有可用处理器作为目标并行级别的工作窃取线程池

用例：

- 1. 用于分治法类型的问题。

- 2. 有效利用空闲线程。空闲线程从繁忙线程那里窃取任务。

缺点：

- 1. 无界队列大小是有害的。

你可以在所有`ExecutorService`中看到一个共同缺点：无界队列。这可以通过`ThreadPoolExecutor`来解决。

`ThreadPoolExecutor (int corePoolSize, int maximumPoolSize, long AliveTime, TimeUnit unit, BlockingQueue<Runnable> workQueue, ThreadFactory threadFactory, RejectedExecutionHandler handler)`

通过`ThreadPoolExecutor`，你可以：

- 1. 动态控制线程大小

- 2. 为`BlockingQueue`设置容量

- 3. 当队列满时定义拒绝执行

- 4. 使用`CustomThreadFactory`为线程创建添加一些额外功能 (`public Thread newThread(Runnable) r`)

## 127.9: 调度任务在固定时间、延迟后或重复运行

`ScheduledExecutorService`类提供了多种方式调度单次或重复任务的方法。以下代码示例假设线程池已如下所示声明并初始化：

`ScheduledExecutorService pool = Executors.newScheduledThreadPool(2);`

除了普通的`ExecutorService`方法外，`ScheduledExecutorService` API 增加了 4 个调度任务并返回`ScheduledFuture`对象的方法。后者用于获取结果（在某些情况下）并取消任务。

# 在固定延迟后启动任务

以下示例调度了一个任务在十分钟后启动。

```java
ScheduledFuture<Integer> future = pool.schedule(new Callable<>() {
@Override public Integer call() {
  // 执行某些操作
  return 42;
}
},
10, TimeUnit.MINUTES);
```

# 以固定频率启动任务

以下示例调度了一个任务在十分分钟后启动，然后以每分钟一次的频率重复执行。

```java
ScheduledFuture<?> future = pool.scheduleAtFixedRate(new Runnable() {
@Override public void run() {
  // do something
},
10, 1, TimeUnit.MINUTES);
```

任务执行将按照计划继续，直到线程池关闭或其中一个任务遇到异常。可以保证通过给定的`scheduleAtFixedRate`调用所调度的任务在时间上不会重叠。如果某个任务的执行时间超过了规定的周期，则下一次及后续的任务执行可能会延迟开始。

**以固定延迟启动任务**

以下示例调度了一个任务在十分分钟后启动，然后在每次任务结束和下一次开始之间有一分钟的延迟重复执行。

```java
ScheduledFuture<?> future = pool.scheduleWithFixedDelay(new Runnable() {
@Override public void run() {
  // do something
},
10, 1, TimeUnit.MINUTES);
```

任务执行将按照计划继续，直到线程池关闭、`future`被取消或其中一个任务遇到异常。

# 章节 127.10：使用线程池

线程池主要用于调用`ExecutorService`中的方法。

以下方法可提交工作执行：

# 方法描述

| 方法 | 描述 |
| :--- | :--- |
| `submit` | 执行提交的工作并返回一个可用于获取结果的`future` |
| `execute` | 在未来的某个时间执行任务，而不获取任何返回值 |
| `invokeAll` | 执行任务任务列表并返回一个`Futures`列表 |
| `invokeAny` | 执行所有任务，但仅返回其中一个执行成功（无异常）的任务的结果 |

完成对线程池的操作后，可以调用`shutdown()`来终止线程池。这将执行所有待处理的任务。要等待所有任务执行完毕，可以对`Termination`或`isShutdown()`进行循环。

## 第 128 章：ThreadLocal

章节 128.1：`ThreadLocal`基本用法

Java `ThreadLocal`用于创建线程本地变量。众所周知对象的线程拥有自己的变量，因此该变量不是线程安全的。如果我们想使用同步来确保线程安全但又想避免同步，`ThreadLocal`允许我们创建线程本地的变量，即只有该线程可以读写这些变量，因此执行同一段代码的其他线程无法访问彼此的`ThreadLocal`变量。

这可以在`ThreadLocal`变量中使用，例如在 Web 服务等线程池的情况下。例如，为每个请求创建`SimpleDateFormat`对象是非常耗时的，且`SimpleDateFormat`无法的静态对象是非线程安全的，因此我们可以创建一个`ThreadLocal`，以便在无需每次都创建`SimpleDateFormat`开销的情况下执行线程安全的操作。

下面的代码展示了如何使用：

线程拥有自己的`ThreadLocal`变量，它们可以使用`get()`和`set()`方法获取默认值或更改其在线程本地的值。`ThreadLocal`实例通常是希望与线程关联状态的类中的私有静态字段。

这里是一个在 Java 程序中使用`ThreadLocal`的小示例，证明了每个线程都拥有自己的`ThreadLocal`变量副本。

```java
package com.examples.threads;
import java.text.SimpleDateFormat; import java.util.Random;
public class ThreadLocalExample implements Runnable {

// SimpleDateFormat 不是线程安全的
formatter.set(new SimpleDateFormat());
System.out.println("Thread Name=" + Thread.currentThread().getName() + "");
formatter = "+" + formatter.get().toPattern() + ";";
}
```

输出：

- `Thread Name=0 default Formatter = yyyyMMd HHMM`

- `Thread Name=1 default Formatter = yyyyMMd HHMM`

- `Thread Name=0 formatter = M/d/yy h:mm a`



- `Thread Name=2` default `Formatter = yyyyMMd h:mm a`
- `Thread Name=1` formatter = `M/d/yy h:mm a`
- `Thread Name=3` default `Formatter = yyyyMMd h:mm a`
- `Thread Name=4` default `Formatter = yyyyMMd h:mm a`
- `Thread Name=4` formatter = `M/d/yy h:mm a`
- `Thread Name=5` default `Formatter = yyyyMMd HHMM`
- `Thread Name=2` formatter = `M/d/yy h:mm a`
- `Thread Name=3` formatter = `M/d/yy h:mm a`
- `Thread Name=6` default `Formatter = yyyyMMd HHMM`
- `Thread Name=5` formatter = `M/d/yy h:mm a`
- `Thread Name=6` formatter = `M/d/yy h:mm a`
- `Thread Name=7` default `Formatter = yyyyMMd HHMM`
- `Thread Name=8` default `Formatter = yyyyMMd HHMM`
- `Thread Name=8` formatter = `M/d/yy h:mm a`
- `Thread Name=7` formatter = `M/d/yy h:mm a`
- `Thread Name=9` default `Formatter = yyyyMMd HHMM`
- `Thread Name=9` formatter = `M/d/yy h:mm a`

正如从输出所示，`Thread-0` 修改了 `formatter` 的值，但 `thread-2` 的默认 `formatter` 与初始化值相同。

## 128.2：ThreadLocal Java 8

```java
ThreadLocal<SimpleDateFormat> format = ThreadLocal.withInitial(() -> new SimpleDateFormat("yyyyMMdd HH:mm"));
```

正如从输出所示，`Thread-0` 修改了 `formatter` 的值，但 `thread-2` 的默认 `formatter` 与初始化值相同。

```java
log.info(String.format("Task %d is sleeping for %d seconds", taskNumber,
timeout)); TimeUnit.SECONDS.sleep(timeout);
log.info(String.format("Task %d is done sleeping", taskNumber));
```

```java
} catch (InterruptedException e) {
    log.warning(e.getMessage());
}
```

## AsyncExample1

```java
import java.util.concurrent.ExecutorService; import java.util.concurrent.Executors;

public class AsyncExample1 {
    public static void main(String[] args) {
        ExecutorService executorService = Executors.newCachedThreadPool();
        for (int i = 0; i < 10; i++) {
            executorService.execute(new AsyncMaintenanceTaskCompleter(i));
        }
        executorService.shutdown();
    }
}
```

运行 `AsyncExample1.main()` 产生了以下输出：

```
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 8 is sleeping for 18 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 6 is sleeping for 4 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 2 is sleeping for 6 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 3 is sleeping for 4 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 9 is sleeping for 14 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 4 is sleeping for 9 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 5 is sleeping for 10 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 0 is sleeping for 7 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 1 is sleeping for 9 seconds
Dec 28, 2016 2:21:03 PM AsyncMaintenanceTaskCompleter run INFO: Task 7 is sleeping for 8 seconds
Dec 28, 2016 2:21:07 PM AsyncMaintenanceTaskCompleter run INFO: Task 6 is done sleeping
Dec 28, 2016 2:21:07 PM AsyncMaintenanceTaskCompleter run INFO: Task 3 is done sleeping
Dec 28, 2016 2:21:09 PM AsyncMaintenanceTaskCompleter run INFO: Task 2 is done sleeping
Dec 28, 2016 2:21:10 PM AsyncMaintenanceTaskCompleter run INFO: Task 0 is done sleeping
Dec 28, 2016 2:21:11 PM AsyncMaintenanceTaskCompleter run INFO: Task 7 is done sleeping
Dec 28, 2016 2:21:12 PM AsyncMaintenanceTaskCompleter run INFO: Task 4 is done sleeping
Dec 28, 2016 2:21:12 PM AsyncMaintenanceTaskCompleter run INFO: Task 1 is done sleeping
Dec 28, 2016 2:21:13 PM AsyncMaintenanceTaskCompleter run INFO: Task 5 is done sleeping
Dec 28, 2016 2:21:17 PM AsyncMaintenanceTaskCompleter run INFO: Task 9 is done sleeping
Dec 28, 2016 2:21:21 PM AsyncMaintenanceTaskCompleter run INFO: Task 8 is done sleeping
```

进程以退出代码 0 结束

**注意事项**：上述输出中有几点需要注意：

1. 任务执行顺序不可预测的。
2. 由于每个任务的睡眠时间是伪随机的，它们并不一定按照调用的顺序完成。

## 12.2 使用 Callable 类实例执行需要返回值的异步任务

通常我们需要执行一个耗时任务并在完成后获取其结果。在这个示例中，我们将创建两个类：一个实现 `Callable<T>` 接口（`T` 是我们想要返回的类型），另一个包含 `main()` 方法。

### AsyncTaskCompleter.java

```java
import lombok.extern.java.Log;
import java.util.concurrent.Callable;
import java.util.concurrent.ThreadLocalRandom;
import java.util.concurrent.TimeUnit;

@Log
public class AsyncTaskCompleter implements Callable<Integer> {
    private int taskNumber;

    public AsyncTaskCompleter(int taskNumber) {
        this.taskNumber = taskNumber;
    }

    @Override
    public Integer call() throws Exception {
        int timeout = ThreadLocalRandom.current().nextInt(1, 20);
        try {
            log.info(String.format("Task %d is sleeping", taskNumber));
            TimeUnit.SECONDS.sleep(timeout);
            log.info(String.format("Task %d is done sleeping", taskNumber));
        } catch (InterruptedException e) {
            log.warning(e.getMessage());
        }
        return timeout;
    }
}
```

### AsyncExample2.java

```java
import lombok.extern.java.Log;
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

@Log
public class AsyncExample2 {
    public static void main(String[] args) {
        ExecutorService executorService = Executors.newCachedThreadPool();
        List<Future<Integer>> futures = new ArrayList<>();
        for (int i = 0; i < 10; i++) {
            Future<Integer> submittedFuture = executorService.submit(new AsyncTaskCompleter(i));
            futures.add(submittedFuture);
        }
        executorService.shutdown();
        while (!futures.isEmpty()) {
            for (int j = 0; j < futures.size(); j++) {
                Future<Integer> f = futures.get(j);
                if (f.isDone()) {
                    try {
                        int timeout = f.get();
                        log.info(String.format("A task completed after sleeping %d seconds", timeout));
                        futures.remove(j);
                        j--; // 移除后调整索引
                    } catch (InterruptedException | ExecutionException e) {
                        log.warning(e.getMessage());
                    }
                }
            }
        }
    }
}
```

运行 `AsyncExample2.main()` 产生了以下输出：

```
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 7 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 8 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 2 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 1 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 4 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 9 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 0 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 6 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 5 is sleeping
Dec 28, 2016 2:07:15 PM AsyncTaskCompleter call INFO: Task 3 is sleeping
Dec 28, 2016 2:07:16 PM AsyncExample2 main INFO: A task completed after sleeping for 1 seconds
Dec 28, 2016 2:07:17 PM AsyncTaskCompleter call INFO: Task 2 is done sleeping
Dec 28, 2016 2:07:17 PM AsyncExample2 main INFO: A task completed after sleeping for 2 seconds
Dec 28, 2016 2:07:17 PM AsyncTaskCompleter call INFO: Task 9 is done sleeping
Dec 28, 2016 2:07:17 PM AsyncExample2 main INFO: A task completed after sleeping for 2 seconds
Dec 28, 2016 2:07:19 PM AsyncTaskCompleter call INFO: Task 3 is done sleeping
Dec 28, 2016 2:07:19 PM AsyncExample2 main INFO: A task completed after sleeping for 4 seconds
Dec 28, 2016 2:07:20 PM AsyncTaskCompleter call INFO: Task 0 is done sleeping
Dec 28, 2016 2:07:20 PM AsyncExample2 main INFO: A task completed after sleeping for 5 seconds
Dec 28, 2016 2:07:21 PM AsyncTaskCompleter call INFO: Task 5 is done sleeping
Dec 28, 2016 2:07:21 PM AsyncExample2 main INFO: A task completed after sleeping for 6 seconds
Dec 28, 2016 2:07:25 PM AsyncTaskCompleter call INFO: Task 1 is done sleeping
```



Dec 28, 2016 2:07:25 PM AsyncExample2 main INFO: A task completed after sleeping for 10 seconds

Dec 28, 2016 2:07:27 PM AsyncTaskCompleter call INFO: Task 6 is done sleeping

Dec 28, 2016 2:07:27 PM AsyncExample2 main INFO: A task completed after sleeping for 12 seconds

Dec 28, 2016 2:07:29 PM AsyncTaskCompleter call INFO: Task 7 is done sleeping

Dec 28, 2016 2:07:29 PM AsyncExample2 main INFO: A task completed after sleeping for 14 seconds

Dec 28, 2016 2:07:31 PM AsyncExample2 main INFO: A task completed after sleeping for 16 seconds

并不是防止已经提交给 `ExecutorService` 的任务完成，而是防止新的任务被添加到队列中。

### 第 129.3 节：使用 Lambda 表达式内联定义异步任务

虽然良好的软件设计通常会最大化代码的可用性，但有时通过 Lambda 表达式在代码中内联定义异步任务可能有助于提高代码的可读性。

在这个示例中，我们将创建一个包含 `main()` 方法的类。在该方法内部，我们将使用 Lambda 表达式来创建并执行 `Callable` 和 `Runnable<T>` 的实例。

`AsyncExample3.java`

```java
import lombok.extern.java.Log;

import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.*;

@Log
public class AsyncExample3 {
    public static void main(String[] args) {

        ExecutorService executorService = Executors.newCachedThreadPool();
        List<Future<Integer>> futures = new ArrayList<>();
        for(int i = 0; i < 5; i++) {
            final int index = i;
            executorService.execute(() -> {
            try {
                int timeout = getTimeout();
                log.info(String.format("Runnable %d has been submitted and will sleep for %d seconds", index, timeout));
                TimeUnit.SECONDS.sleep(timeout);
            } catch (InterruptedException e) {
                log.warning(e.getMessage());
            }
        });
    }
}
```

```java
        log.info(String.format("Runnable %d has finished sleeping", index)); }
        Future<Integer> submittedFuture = executorService.submit(() -> {
            int timeout = getTimeout();
            log.info(String.format("Callable %d will begin sleeping", index)); 
            try {
                TimeUnit.SECONDS.sleep(timeout);
            } catch (InterruptedException e) {
                log.warning(e.getMessage());
            }
            log.info(String.format("Callable %d is done sleeping", index)); 
            return timeout;
        });
        futures.add(submittedFuture);
        executorService.shutdown();
        while(!futures.isEmpty()){
            for(int j = 0; j < futures.size(); j++){
                Future<Integer> f = futures.get(j);
                if(f.isDone()){
                    try {
                        int timeout = f.get();
                        log.info(String.format("A task just completed after sleeping for %d seconds", timeout));
                    } catch (InterruptedException | ExecutionException e) {
                        log.warning(e.getMessage());
                    }
                }
                futures.remove(f);
            }
        }
    }
```

```java
    public static int getTimeout() {
        return ThreadLocalRandom.current().nextInt(1, 20);
    }
}
```

# 注意事项

在上面的输出中有几点需要注意：

1. Lambda 表达式可以访问其定义作用域内可变量和方法，但在 Lambda 表达式内部使用时，所有变量必须是 `final`（或有效 `final`）。

2. 我们不需要显式地指定 Lambda 表达式是 `Callable` 还是 `Runnable<T>`，返回类型会根据返回值自动推断。

## 第 130 章：常见的 Java 陷阱

本主题概述了 Java 初学者常犯的一些错误。这包括在使用 Java 语言时的任何常见错误或对运行时环境的理解。

与特定 API 相关的错误可以在特定 API 的特定主题中描述。`String` 是一个特殊情况；它们在 Java 语言规范中有涵盖。除了常见错误之外的细节可以在关于 Strings 的主题中描述。

### 第 130.1 节：陷阱：使用 `==` 比较 Integer 类型的类型包装对象

（此陷阱适用于所有基本类型包装类，但我们将以 `Integer` 和 `int` 来讨论。）

在处理 `Integer` 对象时，使用 `==` 来比较值是非常具有吸引力的，因为你处理 `int` 值时也是这样做。而且在某些情况下，这看起来是有效的：

```java
Integer int1_1 = Integer.valueOf("1");
Integer int1_2 = Integer.valueOf("1");
System.out.println("int1_2: " + (int1_1 == int1_2)); // true
System.out.println("int1_1 equals int1_2: " + int1_1.equals(int1_2)); // true
```

在这里我们创建了两个值为 1 的 `Integer` 对象并对它们进行比较（在这里我们从 `String` 创建了一个，另一个从 `int` 字面量创建。还有其他替代方案。此外，我们观察到两种比较方法（`==` 和 `equals`）都返回了 `true`）。

当我们选择不同的值时，这种行为发生了变化：

```java
Integer int2_1 = Integer.valueOf("1000");
Integer int2_2 = Integer.valueOf("1000");
System.out.println("int2_1 == int2_2: " + (int2_1 == int2_2)); // false
System.out.println("int2_1 equals int2_2: " + int2_1.equals(int2_2)); // true
```

这种行为差异的原因是，JVM 为 -128 到 127 范围内的 `Integer` 对象维护了一个缓存。（上限值可以通过系统属性 `java.lang.Integer.CacheMaxSize` 或 JVM 参数 `-XX:AutoBoxCacheSize` 覆盖）。对于此范围内的值，`Integer.valueOf()` 将返回缓存的值而不是创建一个新对象。

因此，在第一个示例中，`Integer.valueOf(1)` 和 `Integer.valueOf("1")` 返回了相同的缓存 `Integer` 实例。相比之下，第二个示例中的 `Integer.valueOf(1000)` 和 `Integer.valueOf("1000")` 都创建并返回了新的 `Integer` 对象。

`==` 运算符执行引用相等性测试（即相同对象）。因此，在第一个示例中 `int1_1 == int1_2` 为 `true`，因为引用是相同的。在第二个示例中 `int2_1 == int2_2` 为 `false`，因为引用是不同的。

### 第 130.2 节：陷阱：使用 `==` 比较字符串

初学者的一个常见错误是使用 `==` 运算符来测试两个字符串是否相等。例如：

```java
public class Hello {
    public static void main(String[] args) {
        if (args.length > 0) {
            if (args[0] == "hello") {
                System.out.println("Hello to you");
            } else {
                System.out.println("Are you grumpy?");
            }
        }
    }
}
```

上面的程序在 `args[0]` 为 `"hello"` 时会输出 `"Hello to you"`，但如果 `args[0]` 不是 `"hello"`，它也会输出 `"Are you grumpy?"`。这是因为 `==` 测试的是引用而不是实际内容。

正确的测试字符串方法是使用 `equals()` 方法：

```java
public class Hello2 {
    public static void main(String[] args) {
        if (args.length > 0) {
            if (args[0].equals("hello")) {
                System.out.println("Hello to you");
            } else {
                System.out.println("Are you grumpy?");
            }
        }
    }
}
```

这种方法在 `args[0]` 为 `"hello"` 时会正确输出 `"Hello to you"`，而在其他时会输出 `"Are you grumpy?"`，结果是预期的。

但情况会变得更糟。问题是 `==` 在某些情况下会产生预期答案。例如：

```java
public class Test1 {
    public static void main(String[] args) {
        String s1 = "hello";
        String s2 = "hello";
        if (s1 == s2) {
            System.out.println("same");
        } else {
            System.out.println("different");
        }
    }
}
```

有趣的是，这会打印 `same`，尽管我们用错误的方法测试字符串。这是为什么？因为 Java 语言规范（第 3.10.5 节：字符串字面量）规定，任何两个字符相同的字符串实际上由同一个 Java 对象表示。因此，`==` 测试对于相等字面量返回 `true`。字符串字面量在加载代码时会被“内化”并添加到共享的“字符串池”，但这实际上是一个实现细节。

为了增加融合，Java 语言规范还规定，当你有一个连接两个字符串字面量的编译时表达式时，它等同于单一字面量。因此：

```java
public class Test1 {
    public static void main(String[] args) {
        String s1 = "hello";
        String s2 = "hel" + "lo";
        String s3 = " mum";
        if (s1 == s2) {
            System.out.println("1. same");
        } else {
            System.out.println("1. different");
        }
        if (s1 + s3 == "hello mum") {
            System.out.println("2. same");
        } else {
            System.out.println("2. different");
        }
    }
}
```

这将会输出 `"1. same"` 和 `"2. different"`。在第一情况下，`+` 表达式在编译时计算，我们将一个 `String` 对象与其自身比较。在第二情况下，它是运行时计算的，我们比较的是不同的 `String` 对象。

总结来说，在 Java 中使用 `==` 测试字符串几乎总是错误的，但不能保证一定会给出错误答案。

## 第 130.3 节：陷阱：忘记释放资源

每当程序打开资源（如文件或网络连接）时，在使用完毕后释放资源是至关重要的。如果在对此类资源进行操作期间抛出任何异常，也应该采取类似的谨慎措施。有人可能会认为 `FileInputStream` 拥有一个析构函数（finalizer）；但由于我们无法预测垃圾回收周期何时开始，输入流可能会无限地消耗计算机资源。必须在 `try-catch` 块的 `finally` 节中关闭资源：

版本 < Java SE 7

```java
private static void printFileJava() throws IOException {
    FileInputStream input = new FileInputStream("file.txt");
    int data = input.read();
    while (data != 1) {
        System.out.print((char) data);
        data = input.read();
    }
    finally {
        if (input != null) {
            input.close();
        }
    }
}
```

从 Java 7 开始，Java 特别为这种情况引入了一种非常有用且整洁的语句，称为“资源管理器”（try-with-resources）：

版本 >= Java SE 7

```java
private static void printFileJava7() throws IOException {
    try (FileInputStream input = new FileInputStream("file.txt")) {
        int data = input.read();
        while (data != 1) {
            System.out.print((char) data);
            data = input.read();
        }
    }
}
```

`try-with-resources` 语句可以用于任何实现了 `Closeable` 或 `AutoCloseable` 接口的对象。它确保每个资源在语句结束时被关闭。这两个接口之间的区别在于，`Closeable` 的 `close()` 方法会抛出一个 `IOException`，这必须以某种方式进行处理。

在资源已经打开但在使用后应安全关闭的情况下，可以将将其赋值给 `try-with-resources` 内部的局部变量。

版本 ≥ Java SE 7



```java
private static void printFileJava(InputStream extResource) throws IOException {
    try (InputStream input = extResource) {
        // 访问资源
    }
}
```

在`try-with-resources`构造函数中创建的局部资源变量是事实上的常量（effectively final）。

## 第 130.4 节：陷阱：在尝试打开文件之前对其进行测试

有些人建议，在尝试打开文件之前，应该对其进行各种测试，以提供更好的诊断信息或避免处理异常。例如，此方法尝试检查路径是否对应可读文件：

```java
public static File getValidatedFile(String path) throws IOException {
    File f = new File(path);
    if (!f.exists()) throw new IOException("Error: not found: " + path);
    if (!f.isFile()) throw new IOException("Error: Is a directory: " + path);
    if (!f.canRead()) throw new IOException("Error: cannot read file: " + path);
    return f;
}
```

你可以像这样使用上述方法：

```java
File f = null;
try {
    f = getValidatedFile("somefile");
} catch (IOException ex) {
    System.err.println(ex.getMessage());
    return;
}

try (InputStream is = new FileInputStream(file)) { // 读取数据等
}
```

第一个问题出在`FileInputStream(File)`的签名上，因为编译器仍然坚持要求我们在此处（或在调用栈的更高处）捕获`IOException`。第二个问题是，`getValidatedFile`执行的检查不能保证`InputStream`一定成功。

竞态条件：另一个或独立的进程可能在`getValidatedFile`返回后重命名文件、删除文件或移除访问权限。这将导致一个没有自定义消息的“普通”`IOException`。

这些测试没有覆盖某些边界情况。例如，在开启了“强制”（enforcing）模式 SELinux 的系统上，尝试读取文件可能会失败。

第三个问题是，`getValidatedFile`执行的检查不能保证`InputStream`能够成功。

这将会打印两条消息。特别是，`here.equals(elsewhere)`返回`true`，因为我们为两个`MutableLocation`对象的相等性所选择的语义标准已经满足了。

# 方法调用完全没有传递对象

Java 方法调用使用按值传递（pass by value）来传递参数并返回结果。当你向方法传递一个引用值时，你实际上是在按值传递一个指向对象的引用，这意味着它创建了对象引用的副本。

只要对象引用仍然指向同一个对象，你就可以通过该引用修改对象的内容。但是，如果你在方法内部将引用指向一个新的对象，这并不会影响调用者那边的引用，因为你修改的只是引用的副本。

```
if (condVar > someVal) {console.log("xxx")}
```

# 第 131 章：Java 陷阱 - 异常的使用

某些 Java 语言的误用会导致程序在编译正确的情况下产生错误的结果。本主题的主要目的是列出与异常处理相关的常见陷阱，并提出避免此类陷阱的正确方法。

## 第 131.1 节：陷阱 - 捕获 Throwable、Exception、Error 或 RuntimeException

缺乏经验的 Java 程序员常见的思维模式是异常是“问题”或“负担”，而处理这种问题的最佳方法是尽快将它们全部捕获。这会导致像如下的代码：

```
try {
InputStream is = new FileInputStream(fileName);
// process the input
} catch (Exception ex) {
System.out.println("Could not open file " + fileName);
}
```

上述代码存在一个严重的缺陷。`catch`语句实际上捕获的异常比程序员预期的要多。假设由于应用程序其他地方的 Bug，`fileName`的值为`null`。这将导致`FileInputStream`构造函数抛出`NullPointerException`。处理器将捕获该异常，并向用户报告：

Could not open null

这既没有帮助又令人困惑。更糟糕的是，假设是“处理输入”代码抛出了意外异常（无论是检查异常还是未检查异常！）。现在，用户将收到一个针对打开文件时发生的问题的误导性信息，而该问题可能与 I/O 无关。

问题的根源在于程序员为`Exception`编写了处理器。这几乎总是错误的：

捕获`Exception`会捕获所有检查型异常，以及大多数未检查异常。捕获`RuntimeException`会捕获大多数未检查异常。捕获`Error`会捕获信号 JVM 内部错误的未检查异常。这些错误通常是不可恢复的，且不应该被捕获。捕获`Throwable`会捕获所有可能的异常。

捕获过于宽泛的异常的问题在于，处理器通常无法妥善地处理所有异常。在`Exception`等情况下，程序员很难预测可能会捕获到什么；即无法预期什么。

总的来说，正确的解决方案是处理被抛出的异常。例如，你可以捕获它们并就地处理它们：

```
try {
InputStream is = new FileInputStream(fileName); // process the input
} catch (FileNotFoundException ex) {
    System.out.println("Could not open file " + fileName);
}
```

或者你可以通过外层方法声明它们将被抛出（throwing）。

捕获`Exception`的情况非常少。唯一常见的情况类似于这种代码：

```
public static void main(String[] args) {
    try {
        // do stuff
    } catch (Exception ex) {
        System.err.println("Unfortunately an error has occurred. " + "Please report this to X Y Z");
        // Write stacktrace to a log file.
        System.exit(1);
    }
}
```

如果我们确实想处理所有的异常，那么捕获`Exception`（甚至`Throwable`）是正确的。1 - 亦称为“宝可梦异常处理”（Pokemon Exception Handling）。

## 第 131.2 节：陷阱 - 忽略或压制异常

这个示例关于刻意忽略或“压制”（squashing）异常。更准确地说，它是关于如何以忽略异常的方式来捕获并处理异常。然而，在描述如何操作之前，我们应该首先指出压制异常通常不是处理它们的正确方法。

异常通常由（某些东西）抛出，以通知程序的其他部分发生了某些重大（即“异常”）的事件。通常情况下（尽管并非总是），异常意味着出了某些问题。如果你编写程序来压制异常，那么该问题很有可能以另一种形式再次出现。更糟糕的是，当你压制异常时，你丢弃了异常对象及其关联的堆栈跟踪（stack trace）。这可能会更难找出问题的原始源头。

在实践中，当你使用 IDE 的自动修复功能来“修复”由未处理异常引起的编译错误时，异常压制经常发生。例如，你的代码可能看起来如下：

```
try {
inputStream = new FileInputStream("someFile");
} catch (IOException e) {
    /* add exception handling code here */
}
```

显然，程序员采用了 IDE 的建议来消除编译错误，但该建议是不恰当的。（如果修复失败，程序应该对此采取某些措施。通过上面的“修复”，程序可能会在之后失败；例如抛出`NullPointerException`，因为`inputStream`现在是`null`。）

尽管如此，这也是刻意压制异常的一个示例。（为了论证，假设我们已经确定显示自拍时的中断是无害的。）注释告诉读者我们刻意压制了异常，以及我们为什么要这样做。

```
try {
  selfie.show();
} catch (InterruptedException e) {
  // It doesn't matter if showing the selfie is interrupted.
}
```

另一种在不说明原因的情况下强调我们刻意压制异常的惯用方法是通过异常变量名来指示这一点，如下：

```
try {
  selfie.show();
} catch (InterruptedException ignored) {
```

某些 IDE（如 IntelliJ IDEA）如果变量名被设置为`ignored`，就不会对空的 catch 块显示警告。

## 第 131.3 节：陷阱 - 抛出 Throwable、Exception、Error 或 RuntimeException

虽然捕获`Throwable`、`Exception`、`Error`和`RuntimeException`异常是不好的，但抛出它们更糟糕。

基本问题是你的应用程序需要处理异常，顶层异常的存在很难区分不同的错误情况。例如：

```
try {
  InputStream is = new FileInputStream(someFile); // could throw IOException
...
if (somethingBad) {
  throw new Exception(); // WRONG
} catch (IOException ex) {
  System.err.println("cannot open ...");
} catch (Exception ex) {
  System.err.println("something bad happened"); // WRONG
}
```

问题在于由于我们抛出了`Exception`实例，我们被迫捕获它。然而，正如另一个示例所示，捕获`Exception`是错误的。在这种情况下，很难区分`somethingBad`为真时的“预期”情况与实际捕获到未检查异常（如`NullPointerException`）的意外情况。

如果允许顶层异常传播，我们会遇到其他问题：

我们现在必须记住抛出顶层异常的所有不同原因，并进行区分/处理。

在`Exception`和`Throwable`的情况下，如果我们希望异常传播，还需要将这些异常添加到方法的`throws`句中。这是有问题的，下文所述。

简而言之，不要抛出这些异常。抛出一个更具体的异常，以紧密描述发生的“异常”事件。如果需要，可以定义并使用自定义异常类。

```java
try {
  doSomething();
} catch (Exception ex) { report(ex);
  throw ex;
}
```

上述代码尝试在异常通过时将其记录，但并没有进行最终处理。遗憾的是，在 Java 7 之前，`throw ex;`语句会导致编译器认为抛出了任何异常。这可能迫使你将封装的方法声明为`throws Exception`。从 Java 7 开始，编译器知道此处可能（重新抛出）的异常集合更小。

## 第 131.4 节：陷阱 - 使用异常进行正常流控制

有一些 Java 专家经常朗诵一条格言：

“异常应该用于异常情况。”

（例如：http://programmers.stackoverflow.com/questions/184654 ）这种说法的本质在于（在 Java 中）使用异常和异常处理来实现正常的流控制是一个坏主意。例如，比较以下处理可能为`null`的两种方法。

```java
public String truncateOrNull(String word, int maxLength) { if (word
== null) {
  return ""
}
} else {
  return word.substring(0, Math.min(word.length(), maxLength));
}
```

```java
public String truncateOrNull(String word, int maxLength) { try {
return word.substring(0, Math.min(word.length(), maxLength));
} catch (NullPointerException ex) {
  return ""
}
```

在这个示例中，我们（根据设计）将`word`为`null`的情况视作空字符串处理。这两个版本分别使用传统的`if ... else`或`try ... catch`来处理`null`。我们应该如何决定哪个版本更好呢？

第一个标准是可读性。虽然可读性很难从客观上量化，但大多数程序员都会同意，第一个版本的核心含义更容易辨别。事实上，为了理解第二种形式，你需要理解`Math.min`或`String.substring`方法不会抛出`NullPointerException`。

第二个标准是效率。在 Java 8 之前的版本中，第二个版本比第一个版本要慢得多（出几个数量级）。特别是异常对象的构造涉及捕获和记录栈帧，以防万一需要堆栈跟踪信息。

另一方面，在许多情况下，使用异常比使用条件代码处理“异常”事件更具可读性、更高效且（有时）更正确。事实上，在少数情况下，必须将它们用于“非异常”事件；即发生相对频繁的事件。对于后者，值得考虑减少创建异常对象开销的方法。

## 第 131.5 节：陷阱 - 直接子类 Throwable

`Throwable`有两个直接子类：`Exception`和`Error`。虽然可以创建一个直接扩展`Throwable`的类，但这不是明智的，因为许多应用程序假设只存在`Exception`和`Error`。

更重要的是，子类`Throwable`并没有实际收益，因为生成的类实际上仅仅是一个检查异常（checked exception）。改为子类`Exception`会产生相同的行为，但能更清晰地表达你的意图。

## 第 131.6 节：陷阱 - 捕获 InterruptedException

正如其他陷阱中所指出的，通过使用

```java
try {
  // Some code
} catch (Exception) {
  // Some error handling
}
```

这会带来许多不同的问题。但一个特别的问题是，它会导致死锁，因为它在编写多线程应用程序时破坏了中断系统。

如果你启动了一个线程，通常还需要能够由于各种原因突然停止它。

```java
Thread t = new Thread(new Runnable()) { public void run() {
while (true) {
  // Do something indefinitely
}
t.start();
// Do something else
```

```java
// 线程应该被取消
// 更好的解决方法是使用一个共享变量，由线程定期进行
// 测试以实现干净退出，但对于这个示例，我们尝试
// 强制中断这个线程。
if (t.isAlive()) {
t.interrupt();
t.join();
}
```

// 继续程序

`Thread.interrupt()`将在该线程中抛出一个`InterruptedException`，其目的是关闭线程。但如果线程在完全停止之前需要清理某些资源呢？为此，它可以捕获`InterruptedException`并执行一些清理。

```java
Thread t = new Thread(new Runnable()) { public void run() {
try {
```

```java
while (true) {
//Do something indefinitely
}
catch (InterruptedException ex) {
//Do some quick cleanup
}
```

// 在这种情况下，简单的 return 即可。

// 但如果你不百分之百确定线程在捕获



// `InterruptedException` 后会结束，你将需要为这段代码

// 外围的层级抛出另一个异常。`Thread.currentThread().interrupt();`

但如果你在代码中有一个捕获所有异常的表达式，`InterruptedException` 被它捕获，中断将不会继续。在这种情况下，可能会导致死锁，因为父线程会无限期通过 `t.join()` 等待该线程停止。

```java
Thread t = new Thread(new Runnable() {
public void run() {try {
while (true) {
//Do something indefinitely
}
catch (Exception ex) {

ex.printStackTrace();
}
```

```java
} catch (InterruptedException ex) {
// 死代码，因为中断异常已经在内层
// 线程捕获中被捕获了
Thread.currentThread().interrupt();
```

```java
}
}
}
```

所以，单独捕获 `Exception` 更好，但如果你坚持使用全捕获，至少要先单独捕获 `InterruptedException`。`Thread t = new Thread(new Runnable()) {`

```java
public void run() {
try {
  while (true) {
    //Do something indefinitely } catch (InterruptedException ex) {
      throw ex;//将其传递到链上层 } catch (Exception ex) {
      ex.printStackTrace();
    }
  }
} catch (InterruptedException ex) {
  // Some quick cleanup
}
```

```java
Thread.currentThread().interrupt(); }
```

## 第 131.7 节陷阱 - 过度或不恰当的堆栈跟踪

程序员可以做的最令人恼恼的事情之一是在代码中散布对 `printStackTrace()` 的调用。

问题是 `printStackTrace()` 会将堆栈跟踪写入标准输出。

对于一个面向非 Java 程序员的端用户应用程序，堆栈跟踪充其量没有提供信息，最坏的情况下还会引起报警。对于服务器端应用程序，很可能没有人会看标准输出。

更好的主意是不直接调用 `printStackTrace()`，或者如果调用，也要将其写入日志文件或错误文件，而不是用户的控制台。

实现这种做法的方法是使用日志框架，并将异常作为参数。然而，如果处理不当，即使是记录异常也可能是有害的。考虑以下：

```java
public void method1() throws SomeException {
    method2();
    // Do something
    catch (SomeException ex) {
        Logger.getLogger().warn("Something bad in method1", ex); throw ex;
    }
}

public void method2() throws SomeException {
    // Do something
    catch (SomeException ex) {
        Logger.getLogger().warn("Something bad in method2", ex); throw ex;
    }
}
```

如果异常在 `method2` 中抛出，你可能会在日志文件中看到两个相同的失败副本。简单来说，要么记录异常，要么将其重新抛出（可能包装另一个异常）。不要两者都做。

## Java 语言陷阱

几种 Java 语言用法可能会导致程序在编译正确的情况下产生错误结果。本主题的主要目的是列出常见陷阱及其原因，并提出避免此类问题的正确方法。

## 第 132.1 节陷阱 - switch case 中缺少 'break'

这些 Java 问题可能会非常尴尬，而且有时在生产环境中运行时才被发现。`switch` 语句中的穿透行为（fallthrough）通常是有用的；然而，在不需要这种行为时缺少 `break` 关键字会导致灾难性的结果。如果你在下面的代码示例的 `case 0` 中忘记放置 `break`，程序将先打印"Zero"后打印"One"，因为这里的控制流将穿过整个 `switch` 语句直到遇到 `break`。例如：

```java
public static void switchCasePrimer() {
int caseIndex = 0;
switch (caseIndex) {

case 0:
  System.out.println("Zero");
case 1:
  System.out.println("One");
  break;
case 2:
  System.out.println("Two");
  break;
default:
  System.out.println("Default");
}

```

在大多数情况下，更 Solution解决方案是使用接口并将具有特定行为移动到独立的实现中（组合优于继承）

如果 `switch` 语句不可避免，建议对可能发生的"预期"穿透进行文档说明。这样你就可以向其他开发者展示你注意到了缺少 `break`，并且这是预期的行为。

```java
switch (caseIndex) {
...
case 2:
  System.out.println("Two");
```

```java
// fallthrough
default:
    System.out.println("Default");
```

## 第 132.2 节：陷阱 - 定义与标准类同名的类

有时候，刚开始学习 Java 的程序员会犯一个错误，定义一个与与广泛使用的类同名的类。例如：

```java
package com.example;

/** * 我的字符串工具类 */
public class String { 
}
```

然后他们就会纳闷为什么会得到意料之外的错误。例如：

```java
package com.example;
public class Test {
    public static void main(String[] args) { System.out.println("Hello world!"); } 
}
```

如果你编译并尝试运行上述类，你将得到一个错误：

```bash
$ javac /example/*.java
$ java.example.Test
```

错误：在类 test.Test 中未找到 main 方法，请如下定义 main 方法：

`public static void main(String[] args)`

或 JavaFX 类必须继承 javafx.application.Application

查看 Test 类代码的人会看到 main 的声明并查看其签名，并疑惑 java 命令到底在抱怨什么。但实际上，java 命令说的是真话。当我们与 Test 在同一个包中声明一个 String 版本时，这个版本的优先级高于 `java.lang.String` 的自动导入。因此，Test.main 方法的签名实际上是

`void main(com.example.String[]) args`

而不是

`void main(java.lang.String[]) args`

而 java 命令将不会将其识别为入口方法。

教训：不要定义与 java.lang 中已有的类或 Java SE 库中其他常用类同名的类。如果你那样做，你就会让自己暴露在各种晦涩的错误风险之了。

## 第 132.3 节：陷阱 - 省略大括号："悬空 if"和"悬空 else"问题

Oracle 风格指南的最新版本规定，if 语句中的 "then" 和 "else" 语句应该始终包含在"大括号（或"花括号"）"中。类似的规则也适用于各种循环语句的体部。

```java
if (a) { // <- 左括号
    doSomething();
    doSomeMore();
} // <- 右括号
```

这实际上并不是 Java 语法的强制。事实上，如果 if 语句的 "then" 部分是一个单一语句，省略大括号是合法的：

```java
if (a) doSomething();
```

甚至

```java
if (a) doSomething();
```

然而，忽略 Java 风格规则并省略大括号是有危险的。特别是，这会显著增加缩进错误的代码被误读的风险。

"悬空 if"问题：

考虑上面的示例代码，在不使用大括号的情况下重写。

```java
if (a)
doSomething(); doSomeMore();
```

代码似乎表示，仅当 a 为真时，doSomething 和 doSomeMore 的调用才会发生。但实际上，这段代码的缩进是错误的。Java 语言规范规定，doSomeMore() 调用是紧跟在 if 语句之后的独立语句。正确的缩进如下：

```java
if (a)
    doSomething();
    doSomeMore();
```

### "悬空 else"问题

当我们加入 else 的时候，会出现第二个问题。考虑下面这个缺少大括号的示例。

```java
if (a)
if (b)
    doX(); else if (c) doY(); else
    doZ();
```

上面的代码似乎表示当 a 为假时将调用 doZ。但实际上，缩进再次错误的。该代码的正确缩进为：

```java
if (a)
    if (b)
        doX();
    else if (c)
        doY();
    else
        doZ();
```

如果按照 Java 风格规则编写代码，它实际上看起来会像这样：

```java
if (a) {
    if (b) {
        doX();
    } else if (c) { 
        doY();
    } else {
        doZ();
    }
}
```

为了说明为什么这样做更好，假设你不不小心写错了代码的缩进。你可能会得到类似这样的结果：

```java
if (a) { 
    if (a) {
        if (b) { 
            if (b) { 
                doX();
            }; 
            doX(); 
        } else if (c) { } 
        else if (c) { 
            doY();
        }; 
        doY();
    } else { 
        else 
    }
    doZ(); 
    doZ();}}}
```

但在这两种情况下，缩进错误的代码在经验丰富的 Java 程序员看来都"看起来是不对"。

## 第 132.4 节：陷阱 - 八进制字面量

考虑以下代码段：

```java
// 打印 1 到 10 的数字和
int count = 0;
for (int i = 1; i < 010; i++) { // 此处错误 ....
    count = count + i;
}
System.out.println("The sum of 1 to 10 is " + count);
```

Java 初学者可能会惊讶地发现，上面的程序打印了错误的答案。它实际上打印的是 1 到 8 的数字和。原因是，以数字 0 开头的整数被 Java 解释为八进制而不是十进制。

## 第 132.5 节：陷阱 - 使用 == 测试布尔值

有时新程序员会写使用 == 来测试布尔值：

```java
public void check(boolean ok) {
    if (ok == true) { // 注意 ==
        System.out.println("It is OK");
    }
}
```

经验丰富的程序员会发现这种写法很笨拙，并想将其重写为：

```java
public void check(boolean ok) {
    if (ok) { // 断言
        System.out.println("It is OK");
    }
}
```

然而，在没有断言的情况下使用 == 是可以的。考虑这种变体：

```java
public void check(boolean ok) {
    if (ok = true) { // 噢！
        System.out.println("It is OK");
    }
}
```

程序员将 == 误写为 =，现在代码有一个微妙的 bug。ok = true 将 true 赋值给 ok 然后结果为 true。这里的教训是不要养成使用 == 的习惯。

## 第 132.6 节：陷阱 - 忽略方法的可见性

即使是经验丰富的 Java 开发者也认为 Java 只有三种访问修饰符。实际上有四种。包私有（即默认级别）可见性经常被忘记。

你应该注意哪些方法是公共。公共方法是应用程序的可见 API。这应该尽可能小且紧，特别是当你编写可重用库时（另见 SOLID 原则）。考虑所有方法的可见性很重要，并在适当的情况下仅使用保护或包私有访问。

当你将应该是私有的方法声明为公共时，你就暴露了类的内部实现细节。

此的一个推论是你只测试类的公共方法——事实上你只能测试公共方法。为了能够运行单元测试而增加私有方法的可见性是糟糕的做法。测试调用限制性可见方法的公共方法足以测试整个 API。你不应该为了允许单元测试而扩展你的 API。

## 第 132.7 节：陷阱：使用 'assert' 进行参数或用户输入验证

StackOverflow 上偶尔会出现一个问题，关于是否应该使用 assert 来验证传递方法的参数，甚至是用户提供的输入。

简单的答案是不合适的。

更好的替代方案包括：

- 使用自定义代码抛出 `IllegalArgumentException`。

- 使用 Google Guava 库提供的 `Preconditions` 方法。

- 使用 Apache Commons Lang3 库提供的 `Validate` 方法。

这是 Java 语言规范（JLS 14.10，针对 Java 8）关于该事的建议：通常，断言检查在程序开发和测试期间开启，在部署时禁用以提高性能。

由于断言可能是禁用的，程序不能假设断言包含的表达式会被执行。因此，布尔表达式通常不应该有副作用。评估此类布尔表达式不应影响评估后可见的状态。断言包含的布尔表达式具有副作用是非法的，但通常是不恰的，因为会导致程序行为根据断言是否开启而变化。

鉴于此，断言不应用于公共方法的参数检查

方法。参数检查通常是方法合约的一部分，无论启用还是禁用断言（assertions），都必须遵守此契约。

使用断言进行参数检查的次要问题是，错误的参数会导致适当的运行时异常（例如 `IllegalArgumentException`、`IndexOutOfBoundsException` 或 `NullPointerException`）。断言失败不会抛出适当的异常。再次，在公共方法上使用断言进行参数检查并不是非法的，但通常是不恰当的。`AssertionError` 设计旨在永远不被捕获，但也可以被捕获，因此 `try` 语句的规则应该处理 `try` 块中断言的方式类似于目前对 `throw` 语句的处理。

## 第 132.8 节：陷阱 - 通配符导入会让你的代码变得脆弱

考虑以下部分示例：

import com.example.somolib.*;

import com.acme.otherlib.*;

```
public class Test {
private Context x = new Context(); // 来自 com.example.somolib
...
}
```

假设你最初是针对 `somolib` 的 1.0 版本和 `otherlib` 的 1.0 版本开发代码的。在之后的某个点，你需要将依赖项升级到更高版本，并决定使用 `otherlib` 2.0 版本。还假设他们在 1.0 和 2.0 之间对 `otherlib` 更改之一是添加了 `Context` 类。

现在当你重新编译 `Test` 时，你会得到一个编译错误，提示 `Context` 是一个模糊的导入。

如果你熟悉代码库，这可能只是一个小不便。如果不熟悉，那么你需要做一些工作来解决这个问题，不仅在这里，可能在其他地方。

问题出在通配符导入。一方面，使用通配符可以让你的类少几行代码。但另一方面：

- 对你代码库其他部分、Java 标准库或第三方库的向上兼容更改可能会导致编译错误。

- 可读性受到影响。除非你使用 IDE，否则要找出是哪个通配符导入引入了同名类是很困难的。教训是，在需要长期维护的代码中使用通配符导入是一个坏主意。如果你使用 IDE，那么维护特定的（非通配符）导入并不费力，而且这种努力是值得的。

## 第 132.9 节：陷阱 - 位置错误的分号和缺失的大括号

这是一个让 Java 初学者产生真实困惑的错误，至少在他们第一次这样做时是。而不是这样写：

if (feeling == HAPPY)

```
System.out.println("Smile"); else
System.out.println("Frown");
```

他们不小心写成了：

if (feeling == HAPPY);

```
System.out.println("Smile"); else
System.out.println("Frown");
```

当 Java 编译器告诉他们 `else` 位置错误时，他们感到困惑。Java 编译器将如下解释上述内容：



```
if (feeling == HAPPY)
/*空语句*/;
System.out.println("Smile");
else

// 这是条件的
// 位置错误。语句不能以 'else' 开头
System.out.println("Frown");
```

在其他情况下，没有编译错误，但代码不会按照程序员的意图执行。例如：

```
for (int i = 0; i < 5; i++) { System.out.println("Hello"); }
```

只打印一次 "Hello"。再次，这个多余的分号意味着 `for` 循环的体是一个空语句。这意味着 `println` 调用是无条件的。

另一个变体：

```
for (int i = 0; i < 5; i++);
System.out.println("The number is " + i);
```

这将导致对 `i` 产生“找不到符号”的错误。多余的分号的存在意味着 `println` 试图在其作用域之外使用 `i`。

这些示例中，有一个直接的解决方案：只需删除多余的分号。然而，从这些示例中可以得出更深层的教训：

1. Java 中的分号不是“语法噪音”。分号的存在与否可以改变程序的含义。不要只是在每行的末尾添加它们。

2. 不要信任代码的缩进。在 Java 语言中，行首额外的空格可能会产生误导。

3. 使用 IDE 来帮助管理代码结构。

4. 这是一个重要的教训：为 `if-else` 语句使用大括号。

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

位置错误的分号可能像这样：

```
if (feeling == HAPPY);
    System.out.println("Smile");
else
    System.out.println("Frown");
```

## 第 132.10 节：陷阱 - 重载而非重写

一个常见的错误是认为你在重写方法而实际上是在重载它。考虑以下示例：

```
public class Base {
    public boolean equals(Object o) {
        System.out.println("Base equals");
        return true;
    }
}

public class Sub extends Base {
    public boolean equals(String s) {
        System.out.println("Sub equals");
        return true;
    }
}
```

如果你调用 `sub.equals("test")`，它将调用 `Base.equals(Object)` 而不是 `Sub.equals(String)`，因为 `String` 是 `Object` 的子类。要正确重写，签名必须完全匹配。

```java
public class Sub extends Base {
    @Override
    public boolean equals(Object o) {
        System.out.println("Sub equals");
        return true;
    }
}
```

## 第 132.11 节：对象自动拆箱到基本类型中的陷阱

```java
public class Foobar {
    public static void main(String[] args) {

        // 示例：
        Boolean ignore = null;
        if (ignore == false) {
            System.out.println("Do not ignore!");
        }
    }
}
```

这里的陷阱在于 `null` 与 `false` 的比较。由于我们在比较基本类型和 `Boolean`，Java 尝试将 `Boolean` 对象拆箱为基本类型等以便比较。然而，由于该值为 `null`，会抛出 `NullPointerException`。

Java 无法将基本类型与 `null` 值进行比较，这会导致运行时出现 `NullPointerException`。考虑基本类型的情况 `false == null`；这将产生编译时错误，类型不匹配：`int` 和 `<null>`。

# 第 133 章 Java 陷阱 - 线程与并发

## 第 133.1 节：陷阱 - 扩展 'java.lang.Thread'

`Thread` 类的 javadoc 显示了定义和使用线程的两种方法：

使用自定义线程类：

```java
class PrimeThread extends Thread {
    long minPrime;
    PrimeThread(long minPrime) {
        this.minPrime = minPrime;
    }
    public void run() {
        // 计算大于 minPrime 的质数
        ..
    }
}
PrimeThread p = new PrimeThread(143);
p.start();
```

使用 `Runnable`：

```java
class PrimeRun implements Runnable {
    long minPrime;
    PrimeRun(long minPrime) {
        this.minPrime = minPrime;
    }
    public void run() {
        // 计算大于 minPrime 的质数
        ..
    }
}
PrimeRun p = new PrimeRun(143); new Thread(p).start();
```

自定义线程类的方法可行，但它也有一些问题：

1. 在使用经典线程池、执行器（executor）或 ForkJoin 框架的上下中使用 `PrimeThread` 会很尴尬。（这并非不可能，因为 `PrimeThread` 间接实现了 `Runnable`，但将自定义的 `Thread` 类作为 `Runnable` 使用确实很笨拙，而且可能可行……取决于该类的其他方面）。

2. 其他方法中出错的概率更大。例如，如果你声明了 `PrimeThread.start()` 但没有委托给 `Thread.start()`，那么你将得到一个运行在当前线程上的“线程”。

将线程逻辑放入 `Runnable` 的方法可以避免这些问题。如果你使用匿名类（Java 1.1 及以后版本）来实现 `Runnable`，结果将比上面的示例更简洁、更具读性。

```java
final long minPrime = ...
new Thread(new Runnable(){
    public void run() {
```

```java
// compute primes larger than minPrime . . .
}).start();
```

使用 Lambda 表达式（Java 8 及更高版本），该示例将变得更加优雅：

```java
final long minPrime = ...
new Thread(() -> {
    // compute primes larger than minPrime . . .
}).start();
```

## 第 133.2 节：陷阱 - 线程过多会导致应用程序变慢

许多多线程初学者认为，使用线程会自动让应用程序运行更快。事实上，情况要复杂得多。但我们可以确定的一点是，对于任何计算机，同时运行的线程数量都是有限的：

- 计算机具有固定数量的核心（或超线程）。

- Java 线程必须被调度到某个核心或超线程上才能运行。

- 如果可运行的 Java 线程多于（可用的）核心/超线程，则其中某些线程必须等待。

这告诉我们，仅仅创建更多的 Java 线程并不能让应用程序运行越来越快。但还有其他考虑：每个线程都需要一个用于其线程栈的堆外（off-heap）内存区域。典型的（默认）线程栈大小为 512 字节或 1MB字节。如果你有大量的线程，内存占用可能会非常显著。每个活动线程都会引用堆中的若干对象。这增加了可达对象的工作集，从而影响垃圾回收和物理内存。

在线程之间切换的开销是不微不足道的。它通常涉及切换到操作系统内核空间以做出线程调度决策。此外，线程同步和线程间信号（例如 `wait()`、`notify()`、`notifyAll()`）的开销可能是巨大的。

根据应用程序的细节，这些因素通常意味着线程数量有一个“甜点”，增加更多线程对性能的提升微乎其微，并可能导致性能下降。

如果你的应用程序为每个新任务创建一个线程，那么负载的意外增加可能会导致灾难性的行为。

处理此问题的更好方法是使用有界线程池，你可以控制其大小（静态地或动态地）。当工作过多时，应用程序需要对请求进行队列。如果你使用 `ExecutorService`，它将处理线程池管理和任务队列。

## 第 133.3 节：陷阱：`wait()` / `notify()` 的不当使用

对象的 `object.wait()`、`object.notify()` 和 `object.notifyAll()` 方法旨在以非常特定的方式使用（参见 http://stackoverflow.com/documentation/java/5409/wait-notify#t=2016081161648303307 ）

### “丢失通知”问题

一个常见的初学者错误是无条件地调用 `object.wait()`

```java
private final Object lock = new Object();
public void myConsumer() {
    synchronized (lock) {
        lock.wait(); // 不要这么做！
    }
    doSomething();
}
```

这样做之所以是错误的，是因为它取决于另一个线程调用 `lock.notify()` 或 `lock.notifyAll()`，但没有什么能保证另一个线程在消费者线程调用 `lock.wait()` 之前确实执行了该操作。

如果没有其他线程已经在等待通知，`lock.notify()` 和 `lock.notifyAll()` 将什么都不做。在这个示例中，如果捕获通知的时机太晚，调用 `myConsumer()` 的线程将永远挂起。

### “非法监视器状态” 错误

如果你在没有持有锁的情况下对对象调用 `wait()` 或 `notify()`，JVM 将抛出 `IllegalMonitorStateException`。

```java
public void myConsumer() {
    lock.wait(); // 抛出异常 consume
}
```

```java
public void myProducer() {
    produce();
    lock.notify(); // 抛出异常
}
```

（`wait()` / `notify()` 的设计要求持有锁，因为这对于避免系统性的竞态条件是必要的。如果可以在不加锁的情况下调用 `wait()` 或 `notify()`，那么无法实现这些原语的主要用例：等待某个条件的发生。）

### Wait / notify 过于低级

避免 `wait()` 和 `notify()` 问题的最佳方法是不使用它们。大多数同步问题都可以通过 `java.util.concurrent` 包中提供的更高级别的同步对象（队列、屏障、信号量等）来解决。

## 第 133.4 节：陷阱：共享变量需要适当的同步

考虑这个示例：

```java
long counter = 0;
while (!stop) {
    counter = counter + 1;
}
```

```java
public static void main(String[] args) {
    ThreadTest tt = new ThreadTest();
    new Thread(tt).start(); // 创建并启动线程
    Thread.sleep(1000); // 睡眠1000 毫秒
    tt.stop = true; // 停止
}
```

（注：此处原文逻辑似乎有些混乱或重复，翻译保持其逻辑结构）

如果你的应用程序为每个新任务创建一个线程，那么负载的意外增加可能会导致灾难性的行为。

处理此问题的更好方法是使用有界线程池，你可以控制其大小（静态地或动态地）。当工作过多时，应用程序需要对请求进行队列。如果你使用 `ExecutorService`，它将处理线程池管理和任务队列。

共享变量。变量的最新版本可能位于某个核心的缓存中。除非该核心将缓存行刷新到主内存，并且其他核心使它们缓存的旧版本副本失效，否则某些核心可能会看到变量的陈旧版本。但如果每当发生缓存写入时都将缓存刷新到内存（“以防”另一个核心正在进行读取），这会在不必要地消耗内存带宽。

在硬件指令集层级使用的标准解决方案是提供缓存失效和缓存写回（write-through）的指令，并交给编译器来决定何时使用这些指令。

回到 Java。内存模型（Memory Model）的设计初衷是让 Java 编译器不需要在真正需要的地方发布缓存失效和写回指令。其假设是程序员将使用适当的同步机制（例如：原始互斥锁、`volatile`、高级并发类等）来标明它需要内存可见性。在没有*发生在此*（happens-before）关系的情况下，Java 编译器可以自由地*假设*不需要缓存操作（或类似操作）。

这对于多线程应用程序具有显著的性能优势，但缺点是编写正确的多线程应用程序并不是易事。程序员*确实*必须理解自己在做什么。

## 为什么我无法重现这个问题？

有几个原因导致这类问题难以重现。

1. 正如上述解释，不妥善处理内存可见性问题的后果*通常*是你的编译后的应用程序没有正确处理内存缓存。然而，正如我们提到的，内存缓存往往会被刷新掉。

2. 当你更改硬件平台时，内存缓存的特性可能会发生变化。如果你的应用程序没有正确同步，这会导致不同的行为。

3. 你可能正在观察到偶然同步（serendipitous synchronization）的影响。例如，如果你添加了跟踪打印（traceprints），在 I/O 流的后台通常会发生某些同步操作，导致缓存被刷新。因此，添加跟踪打印通常会导致应用程序的行为发生变化。

4. 在调试器下运行程序会导致 JIT 编译器以不同的方式对其进行编译。断点和单步执行会进一步加剧这种影响。这些影响通常会改变应用程序的行为。

这些因素使得由于同步不足而导致的 bug 变得特别难以解决。

## 第 133.5 节：陷阱 - 创建线程相对昂贵

考虑这两个微基准测试：

第一个基准测试创建、启动并连接线程。线程的 `Runnable` 并不工作。



```java
public class ThreadTest {
    public static void main(String[] args) throws Exception {
        while (true) {
            long start = System.nanoTime();
            for (int i = 0; i < 100_000; i++) {

                Thread t = new Thread(new Runnable() {
                    public void run() {
                }});
                t.start();
                t.join();
            }
            long end = System.nanoTime();

            System.out.println((end - start) / 100_000.0);
        }
    }
}
```

`$ java ThreadTest`

```text
34627.91355
33596.66021
33661.19084
33699.44895
33603.097
33759.3928
33671.5719
33619.46809
33679.92508
33500.32862
33409.70188
33475.70541
33925.87848
33672.89529
^C
```

一个运行 Linux 的典型现代 PC 显示，Java 8 中创建、启动和连接线程的平均时间在 33.6 到 33.9 微秒之间。

第二个基准测试与第一个等效，但使用了 `ExecutorService` 来提交任务并使用 `Future` 来会合任务结束。

```java
import java.util.concurrent.*;

public class ExecutorTest {
    public static void main(String[] args) throws Exception {
        ExecutorService exec = Executors.newCachedThreadPool();
        while (true) {
            long start = System.nanoTime();
            for (int i = 0; i < 100_000; i++) {
                Future<?> future = exec.submit(new Runnable() { 
                    public void run() {
                }
                });
                future.get();
            }
            long end = System.nanoTime();
            System.out.println((end - start) / 100_000.0);
        }
    }
}
```

`$ java ExecutorTest`

```text
6714.66053
5418.24901
5571.65213
5307.83651
5294.44132
5370.69978
5291.83493
5386.23932
5384.06842
5293.14126
5445.17405
5389.70685
```

可以看到，平均值为 5.3 到 5.6 微秒。虽然实际时间取决于多种因素，这两个结果之间的差异是显著的。回收线程显然比创建新线程更快。

## 第 134 章：Java 陷阱 - 空值与空指针异常

### 第 134.1 节：陷阱 - “修复”意外的空值

在 StackOverflow 上，我们经常在答案中看到这样的代码：

```java
public String joinStrings(String a, String b) {
    if (a == null) {
        a = "",
    }
    if (b == null) {
        b = "",
    }
    return a + " " + b;
}
```

通常伴随着这种断言，认为这样测试空以避免空指针异常是“最佳实践”。

这是最佳实践吗？简而言之：不是。

在我们判断在 `joinStrings` 中这样做是否是一个好主意之前，需要质疑一些底层假设：

#### "a" 或 "b" 为空意味着什么？

如果空是一个有意义的值，那么测试空值情况是正确的方法。推论是，如果空值是有意义的，那么在任何接受或返回空值的方法的 javadoc 中都应该明确说明这一点。

否则，更好的做法是将意外的空值视为编程错误，并让空指针异常发生，以便开发者知道代码中存在问题。

```java
if (values != null) {
  for (int value : values) {
    sum += value;
  }
  return sum;
}
```

如你所见，代码变得稍微复杂了。这直接归因于这种这样使用 null 的决定。

现在考虑这个数组可能在很多地方被使用。在每次使用它的地方，你都必须考虑是否需要进行 null 检查。如果你漏了本该进行的 null 检查，就会面临 `NullPointerException` 的风险。在这里，这种这样使用 null 的策略会导致你的应用程序更加脆弱；也就是说，更容易受到程序员错误导致的影响。

这里的教训是，当你想要表达“空”的意思时，请使用空数组和空列表。

```java
int [] values = new int[]; // 始终为空
List<Integer> list = new ArrayList();// 初始为空
List<Integer> list = Collections.emptyList(); // 始终为空
```

这种空间开销很小，如果这是值得做的话，还有其他方法可以最小化它。

## 第 134.3 节：陷阱 - 关闭 I/O 流时未检查其是否已初始化

为了防止内存泄漏，不应该忘记关闭任务完成的输入流或输出流。这通常通过不带 catch 部分的 try-catch-finally 语句完成：

```java
void writeNullBytesToFile(int count, String filename) throws IOException {
  FileOutputStream out = null;
  try {
    out = new FileOutputStream(filename);
    for(; count > 0; count--);
    out.write(0);
  } finally {
    out.close();
  }
}
```

虽然上面的代码看起来无害，但它有一个会导致调试无法进行的缺陷。如果初始化 out 的行（`out = new FileOutputStream(filename)`）抛出异常，那么 out 将是 null。此时 `out.close()` 会导致一个糟糕的 `NullPointerException`！

为了防止这种情况，在尝试关闭流之前只需确保流不为 null。

```java
void writeNullBytesToFileA(int count, String filename) throws IOException {
  FileOutputStream out = null;
  try {
    out = new FileOutputStream(filename);
    for(; count > 0; count--);
    out.write(0);
  } finally {
    if (out != null)
      out.close();
  }
}
```

更好的方法是使用 try-with-resources，因为它会自动关闭流，且抛出 NPE 的概率为 0，不需要 finally 块。

```java
void writeNullBytesToFile(int count, String filename) throws IOException {
  try (FileOutputStream out = new FileOutputStream(filename)) {
    for(; count > 0; count--);
    out.write(0);
  }
}
```

## 第 134.4 节：陷阱 - 返回 null 而不是抛出异常

某些 Java 程序员对抛出或传播异常普遍反感。这导致了如下代码：

```java
public Reader getReader(String pathname) {
  try {
    return new BufferedReader(new FileReader(pathname));
  } catch (IOException ex) {
    System.out.println("Open failed: " + ex.getMessage());
    return null;
  }
}
```

那么这样做有什么问题？

问题在于 `getReader` 返回了一个 null 作为特殊值，表示它无法打开。现在在使用返回的值之前，需要对其进行测试以检查它是否为 null。如果漏掉了测试，结果将是 `NullPointerException`。

这里实际上有三个问题：

1. `IOException` 被捕获得太早了。

2. 此代码的结构意味着存在泄漏资源的风险。

3. 因为没有可用的真实 Reader，所以返回了 null。

事实上，假设异常需要被捕获，那么返回 null 有几种替代方案：

1. 可以实现一个 `NullReader` 类；例如，其操作行为就像 reader 已经空一样。

2. 使用 Java 8，可以将 `getReader` 声明为返回 `Optional<Reader>`。

## 第 134.5 节：陷阱 - 不必要的基本数据类型包装类会导致 NullPointerExceptions

有时，新刚接触 Java 的程序员会交替使用基本数据类型和包装类。这可能会导致问题。考虑这个例子：

```java
public class MyRecord {
  public int a, b;
  public Integer c, d;
}

MyRecord record = new MyRecord();
record.a = 1; // OK
record.b = record.b + 1; // OK
record.c = 1; // OK
record.d = record.d + 1; // 触发 NullPointerException
```

我们的 Record 类依赖默认初始化来初始化字段。因此，当我们使用 `record` 时，`a` 和 `b` 字段会被设置为零，而 `c` 和 `d` 字段会被设置为 null。当我们尝试使用它们时，我们发现 `int` 字段一直有效，但 `Integer` 字段在某些情况下有效而在另一些情况下无效。具体来说，在失败的情况下（`d`），发生的情况是右侧的表达式尝试对 null 引用进行拆箱，这导致抛出了 `NullPointerException`。

看待这个问题有几种方法：如果字段 `c` 和 `d` 需要是包装类，那么我们不应该依赖默认初始化。如果字段不需要包装类，那么将它们设为包装类就是一个错误。除了这个问题外，与基本数据类型相比，包装类还有额外的开销。这里的教训是，除非真的需要，否则不要使用包装类类型。例如，这个类并不是良好实践的示例；设计良好的类不应该有公共字段。然而，这不是这个示例的重点。

## 第 134.6 节：陷阱 - 使用“Yoda 表示法”来避免 NullPointerException

StackOverflow 上发布的很多示例代码都包含如下片段：

```java
if ("A".equals(someString)) {
  // 执行某些操作
}
```

这在 `someString` 为 null 的情况下“防止”或“避免”了可能的 `NullPointerException`。此外，有人认为 `"A".equals(someString)` 比于：

`someString != null && someString.equals("A")` 更好（它更简洁，在某些情况下可能更高效。然而，正如我们下面同意的那样，简洁可能是一个负面因素）。

然而，真正的陷阱是习惯性地使用 Yoda 测试来避免 `NullPointerException`。当你写 `"A".equals(someString)` 时，你实际上是在处理 `someString` 恰好为 null 的情况。正如另一个示例（陷阱 - 返回 null），意外的 null 值可能由于各种原因产生危害。

这意味着 Yoda 条件并不是“最佳实践”。

1. 除非 null 是预之中的，否则不如让 `NullPointerException` 发生，这样你就可以获得单元测试失败（或错误报告）。这允许你发现并修复导致意外/非预期的 null 出现的 bug。

Yoda 条件应该只在预期 null 的情况下使用，因为你正在测试的对象来自一个文档说明会返回 null 的 API。而且可以说，使用一种不太美观的方式来表达测试可能更好，因为这有助于审查你代码的人突出该 null 检查。根据维基百科介绍：“最佳编码实践是软件开发社区随着时间推移学到的系列非正式规则，可以提高软件质量。” 使用 Yoda 表示法并没有实现这一点。在很多情况下，它会让代码变得更糟。

## 第 135 章：Java 陷阱 - 性能问题

本主题描述了许多与 Java 应用程序性能相关的“陷阱”（即初级 Java 程序员犯的错误）。

## 第 135.1 节：陷阱 - 循环中的字符串拼接不具备扩展性

考虑以下代码说明：

```java
public String joinWords(List<String> words) {
  String message = "";
  for (String word : words) {
    message = message + " " + word;
  }
  return message;
}
```

遗憾的是，如果 words 列表很长，这段代码的效率很低。问题的根源在于语句：`message = message + " " + word;`。在每次循环迭代中，该语句都会新的 message 字符串，包含原始 message 字符串所有字符的副本，并在其后附加字符。这产生了大量的临时字符串，并进行了大量的复制。

当我们分析 `joinWords` 时，假设有 N 个单词，平均长度为 M，我们发现创建了 O(N) 个临时字符串，并且在过程中会复制 O(M.N2) 个字符。N2 部分尤为令人困扰。

对于这类问题^1，推荐的方法是使用 `StringBuilder` 而不是字符串拼接，如下：

```java
public String joinWords2(List<String> words) { StringBuilder message = new StringBuilder(); for (String word : words) {
  message.append(" ").append(word); }
  return message.toString();
}
```

对 `joinWords2` 的分析需要考虑持有构建器字符的 StringBuilder 后备数组“增长”带来的开销。然而，事实证明创建的新对象数量是 O(logN)，而复制的字符数量是 O(M.N)。后者包含了在最后的 `toString()` 调用中复制的字符。

（可以通过在创建 `StringBuilder` 时就指定正确的初始容量来进一步优化。然而，整体复杂度保持不变。）

回到原始的 `joinWords` 方法，事实证明关键语句会被 Java 编译器优化为类似下面的代码：`StringBuilder tmp = new StringBuilder(); ntmp.append(message).append(" ").append(word); message = tmp.toString();`

然而，Java 编译器不会像我们在 `joinWords2` 中手动做的那样将 `StringBuilder` “提升”到循环之外。

参考：

"Java 循环中的 String '+' 运算符慢吗？"

- 1 - 在 Java 8 及更高版本中，使用 `Joiner` 类来解决这个特定问题。然而，这并不是这个示例真正想要说明的。

## 第 135.2 节：陷阱 - 使用 size() 测试集合是否为空效率低下

Java 集合框架为所有 `Collection` 对象提供了两个相关方法：

`size()` 返回集合中的项数，而 `isEmpty()` 方法返回 `true`（当且仅当）集合为空。这两种方法都可以用于测试集合是否为空。例如：

```java
Collection <String> strings = new ArrayList<>(); boolean isNotEmpty = strings.size() == 0; // 避免这样做
boolean isEmpty = strings.isEmpty(); // 优
```

虽然这些方法看起来一样，但某些集合实现并没有存储大小。对于此类集合，`size()` 的实现在每次被调用时都需要计算大小。例如：

一个简单的链表类（不是 `java.util.LinkedList`）可能需要遍历列表来计算元素。`ConcurrentHashMap` 类需要汇总 map 中所有“段”（segments）的项。

集合的懒加载实现可能需要将整个集合加载到内存中才能计算元素。



相比之下，`isEmpty()` 方法只需要测试集合中是否至少有一个元素。这并不涉及计数元素。虽然 `size() == 0` 并不总是 `isEmpty()` 那样高效，但对于一个实现良好的 `isEmpty()`，效率低于 `size() == 0` 是不可想象的。因此，优选 `isEmpty()`。

## 第 135.3 节：陷阱 - 字符串池化（Intern）以便可以使用 == 是一个坏主意

当某些程序员看到这条建议时：

“使用 == 测试字符串是不正确的（除非字符串经过了池化）” 他们的初始反应是对字符串进行池化，以便可以使用 `==`。（毕竟 `==` 比调用 `String.equals(...)` 快，不是吗）

从多个角度来看，这都是错误的方法：

**脆弱性**

首先，只有当你知道正在测试的所有 `String` 对象都经过池化时，才能安全地使用 `==`。JLS 保证源代码中的字符串字面量会被池化。然而，除了 `String.intern(String)` 本身外，没有任何标准的 Java SE API 保证返回池化的字符串。

如果你漏掉任何一个未池化的 `String` 对象源，你的应用程序将是不可靠的。这种不可靠性将表现为假阴性而非异常，这可能更容易检测。

## 使用 `intern()` 的成本

在底层，池化通过维护一个包含之前已池化 `String` 对象的哈希表来工作。使用某种弱引用机制，以确保池化哈希表不会导致内存泄漏。虽然哈希表是在原生代码中实现的（不像 `HashMap`、`Hashtable` 等），但池化调用在 CPU 和内存使用方面仍然相对昂贵。

这种成本必须与我们使用 `==` 代替 `equals` 所节省的开销进行比较。事实上，除非每个池化的字符串都与其他字符串比较“几次”，否则我们根本无法收支。

（附带：池化值得的少数情况通常是为了减少应用程序的内存占用，其中相同的字符串多次出现，且这些字符串具有很长的寿命。）

## 对垃圾回收的影响

除了上述描述的直接 CPU 和内存成本外，池化字符串还会影响垃圾收集器的性能。

在 Java 7 之前的 Java 版本中，池化字符串存储在“PermGen”（永久代）空间中，该空间回收频率很低。如果 `PermGen` 需要回收，（通常）会触发全量 GC。如果 `PermGen` 完全填满，即使普通堆中有空闲空间，JVM 也会崩溃。

Java 7 中，字符串池从“PermGen”移动到普通堆中。然而，哈希表仍然存在，池化调用在 CPU 和内存使用上仍然相对昂贵。除了上述描述的直接 CPU 和内存成本，池化字符串还会影响垃圾收集器的性能。

## 池化作为潜在的拒绝服务攻击

字符串的哈希算法是众所周知的。如果你池化用户或应用程序提供的字符串，这就是拒绝服务（DoS）攻击的一部分。攻击者安排所有字符串具有相同的哈希值，会导致哈希表不平衡以及 O(N) 的性能……其中 N 是冲突字符串的数量。

（有更简单更有效的方法对服务发起 DoS 攻击，如果目标是破坏安全性。）

## 第 135.4 节：陷阱 - 使用 `new` 创建原始类型包装实例效率低下

Java 语言允许使用 `new` 创建 `Integer`、`Boolean` 等实例，但通常这是一个坏主意。最好使用自动装箱（Java 5 及以后）或 `valueOf` 方法。

```java
Integer i1 = new Integer(1); // 坏
Integer i2 = 2; // 优（自动装箱） Integer i3 = Integer.valueOf(3); // 好
```

使用 `new Integer(int)` 明确错误的是因为它会创建一个新对象（除非被 JIT 编译器优化）。相比之下，使用自动装箱或显式的 `valueOf` 调用，Java 运行时会尝试从预存对象的缓存中重用 `Integer` 对象。每次运行时命中，都避免了创建对象。这还节省了堆内存并减少了 GC 开销。

注意：

1. 在最新的 Java 实现中，自动装箱通过调用 `valueOf` 实现，并且对 `Boolean`、`Byte`、`Short`、`Integer`、`Long` 和 `Character` 有缓存。

2. 整数类型的缓存行为是由 Java 规范规定的。

## 第 135.5 节：陷阱 - 正则表达式的效率问题

正则表达式匹配是一个强大的工具（在 Java 以及其他领域），但它确实有一些缺点。其中之一是正则表达式通常相当贵。

**应该复用 `Pattern` 和 `Matcher` 实例**

考虑以下示例：

```java
/**
 * 测试列表中的所有字符串是否由英文字母和数字组成。
 * @param strings 要检查的列表
 * @return 当且仅当所有字符串符合标准时，返回 'true'
 * @throws NullPointerException 如果 'strings' 为 'null' 或包含 null 元素。
 */
```

```java
public boolean allAlphanumeric(List<String> strings) {
  for (String s : strings) {
    if (!s.matches("[A-Za-z0-9]*")) {
      return false;
    }
  }
  return true;
}
```

这段代码是正确的，但效率很低。问题出在 `matches(...)` 调用上。在底层，`s.matches("[A-Za-z0-9]*")` 等同于：

`Pattern.matches("[A-Za-z0-9]*", s)`，而它又等同于

`Pattern.compile("[A-Za-z0-9]*").matcher(s).matches()`

`Pattern.compile("[A-Za-z0-9]*")` 调用会解析正则表达式、分析并构建一个 `Pattern` 对象，该对象持有正则引擎将要使用的数据结构。这是一项非平凡的计算。然后会创建一个 `Matcher` 对象来封装参数 `s`。最后，我们调用 `match()` 来执行实际的模式匹配。

问题在于，这些工作在每次循环迭代中都会重复。解决方案是将代码重构如下：

`private Pattern ALPHA_NUMERIC = Pattern.compile("[A-Za-z0-9]*");`

```java
public boolean allAlphanumeric(List<String> strings) {
  Matcher matcher = ALPHA_NUMERIC.matcher("");
  for (String s : strings) {
    matcher.reset(s);
    if (!matcher.matches()) {
      return false;
    }
  }
  return true;
}
```

注意，`Pattern` 的 javadoc 指出：

此类的实例是不可变的，并且供多个并发线程安全使用。`Matcher` 类的实例在类情况下是不安全的。

假设你想测试字符串 `s` 是否包含三个或更多连续的数字。你可以通过多种方式来实现，包括：

```java
if (s.matches(".*[0-9]{3}.*")) { System.out.println("matches"); }
or
if (Pattern.compile(".*[0-9]{3}").matcher(s).find()) {
  System.out.println("matches");
}
```

第一种更简洁，但效率可能更低。从上看，第一种版本将尝试对整个字符串进行模式匹配。此外，由于 `.*` 是一个“贪婪”模式，模式匹配器可能会“积极地”移动到字符串末尾，然后回溯直到找到匹配项。

相比之下，第二种版本将从左到右搜索，并在找到三个连续数字时停止搜索。

## 使用比正则表达式更有效的替代方案

正则表达式是一个强大的工具，但它们不应该是你唯一的工具。编译任务可以通过其他方式更高效地完成。例如：`Pattern.compile("ABC").matcher(s).find()` 的作用与：

`s.contains("ABC")` 相同，但后者的效率高得多（即使分摊了编译正则表达式的成本）。

通常，非正则的形式更为复杂。例如，在之前的 `allAlphanumeric` 方法中 `matches()` 调用执行的测试可以重写为：

```java
public boolean matches(String s) {
  for (char c : s) {
    if ((c >= 'A' && c <= 'Z') || (c >= 'a' && c <= 'z') || (c >= '0' && c <= '9')) {
      return false;
    }
  }
  return true;
}
```

虽然这比使用 `Matcher` 需要更多的代码，但运行速度会快得多。

### 灾难性回溯 (Catastrophic Backtracking)

（这是所有正则表达式实现中可能存在的问题，但我们在这里提到是因为它是 `Pattern` 使用的一个陷阱。）

考虑这个（人为刻意的）示例：

第一个 println 会快速打印 true。第二个将打印 false。

最终，如果你对上面的代码进行实验，你会发现每次在 C 之前添加一个 A，耗时就会翻倍。

这种行为是灾难性回溯的一个例子。实现正则匹配的模式匹配引擎会尝试模式可能匹配的所有可能方式，这非常令人沮丧。

我们来看 `(A+)+B` 实际上意味着。表面上看，它似乎是在说“一个或多个 A 字符后跟一个 B 值”，但实际上它说的是一个或多个组，每个组由一个或多个 A 字符组成。例如：

- `'AB'` 有一种匹配方式：`'(A)B'`

- `'AAB'` 有两种匹配方式：`'(AA)B'` 或 `'(A)(A)B'`

- `'AAAB'` 有四种匹配方式：`'(AAA)B'` 或 `'(AA)(A)B'` 或 `'(A)(AA)B'` 或 `'(A)(A)(A)B'`

依此类推。

换句话说，可能匹配的数量是 $2^N$，其中 $N$ 是字符数。上面的示例显然是人为构造的，但在使用考虑不周的正则表达式时，模式经常会出现这种性能特征（例如对于较大的 $K$，时间复杂度为 $O(2^N)$ 或 $O(N^K)$）。

这里有一些标准的补救措施：

- 避免在其他重复模式内部嵌套重复模式。

- 避免使用过多的重复模式。

- 在适当的情况下使用非回溯重复。

- 不要使用正则表达式处理复杂的解析任务。（编写一个合适的解析器代替。）

最后，警惕某些情况。

鉴于此，缓冲流（buffered streams）之所以产生巨大差异，是因为它们大幅减少了系统调用（syscalls）的数量。缓冲输入流并不是为每个 `read()` 调用都执行一次系统调用，而是根据需要将大量数据读入缓冲区中。在缓冲流上的大多数 `read()` 调用仅执行一些简单的边界检查，并返回之前读取过的字节。类似的逻辑也适用于输出流以及字符流（character stream）的情况。

（某些人认为缓冲 I/O 的性能源于读取请求大小与磁盘块大小之间的不匹配、磁盘旋转延迟等因素。事实上，现代操作系统使用了多种策略来确保应用程序通常不需要等待磁盘。这并不是真正的解释。）

## 缓冲流总是优选的吗？

并不总是。如果你的应用程序将进行大量的“小”读或写操作，那么缓冲流绝对是优选的。然而，如果你的应用程序只需要对大型 `byte[]` 或 `char[]` 执行或对其执行大批量读写操作，那么缓冲流将无法带来任何实际益处。事实上，甚至可能会产生（极微的）性能开销。

## 这是 Java 中拷贝文件的最快方法吗？

不是。当你使用 Java 基于流的 API 拷贝文件时，你会产生至少一次数据到内存的拷贝成本。如果你使用 NIO 的 `ByteBuffer` 和 `Channel` API，则可以避免这一点。

（在此处添加指向独立示例的链接。）

## 第 135.7 节：陷阱 - 过度使用原始类型包装类效率低下

考虑以下两段代码：

```java
int a = 1000; int b = a + 1;
```

和

```java
Integer a = 1000; Integer b = a + 1;
```

问题：哪个版本效率更高？

答案：这两个版本看起来几乎完全相同，但第一个版本比第二个版本高效得多。

第二个版本对数字使用了 `valueOf`，这会占用更多空间，并且在后台依赖自动装箱（auto-boxing）和自动拆箱（auto-unboxing）。事实上，第二个版本等同于以下代码：

```java
Integer a = Integer.valueOf(1000); // 装箱 1000
Integer b = Integer.valueOf(a.intValue() + 1); // 拆箱 1000, 加 1, 装箱 1000
```

与使用 `int` 的另一个版本相比，显然有三次使用 `Integer` 的方法调用。在 `valueOf` 的情况下，每次调用都会创建并初始化一个新的 `Integer` 对象。由于这些额外的装箱和拆箱，第二个版本的速度很可能比第一个版本慢一个数量级。此外，第二个版本在每次 `valueOf` 调用中都会在堆上分配对象。虽然利用率取决于平台，但每个 `Integer` 对象可能大约在 16 字节左右。相比之下，假设 `a` 和 `b` 都是局部变量，`int` 版本不需要额外的堆空间。

原始类型比其包装后的等效类型运行更快的另一个大原因是它们各自的数组类型在内存中的布局方式不同。

如果以 `int[]` 和 `Integer[]` 为例，在 `int[]` 情况下，`int` 值在内存中是连续排列的。但在 `Integer[]` 情况下，排列的不是值本身，而是指向 `Integer` 对象的引用（指针），而这些对象又包含了实际的 `int` 值。

除了多了一层间接层，这在迭代值时对于缓存局部性（cache locality）来说可能是一个巨大的优势。在 `int[]` 情况下，CPU 可以一次性获取数组中的所有值并缓存，因为它们在内存中是连续的。但在 `Integer[]` 情况下，CPU 可能必须为每个元素执行额外的获取操作，因为数组只引用了实际值。

简而言之，使用原始类型包装类在 CPU 和内存资源上都是相对昂贵的。不必要的使用它们是低效的。

## 第 135.8 节：陷阱 - 使用 `new String(String)` 复制字符串效率低下

## 低效

使用 `new String(String)` 来复制字符串是低效的，而且几乎总是没有必要的。

`String` 对象是不可变的，因此没有必要复制它们来防止更改。在 Java 的某些旧版本中，`String` 对象可以与其他 `String` 对象共享底层数组。在这些版本中，通过创建一个（大的）字符串的（较小）子字符串并保留它，可能会导致内存泄漏。然而，从 Java 7 开始，`String` 的底层数组不再共享了。

在没有任何实际收益的情况下，调用 `String(String)` 仅仅是浪费资源：

- 复制会消耗 CPU 时间。

- 复制会占用更多内存，增加了应用程序的内存占用并/或增加了 GC 开销。



- 如果复制了`String`对象，像`equals(Object)`和`hashCode()`等操作可能会变慢。

## 第 136 章：ServiceLoader

### 第 136.1 节：简单的 ServiceLoader 示例

`ServiceLoader`是一种简单且易用的内置机制，用于动态加载接口实现。通过服务加载器——提供实例化的手段（而不是连接）——可以在 Java SE 中构建一个简单的依赖注入机制。使用`ServiceLoader`接口，接口与实现的分离变得非常自然，程序可以方便地扩展。实际上，许多 Java API 都是基于`ServiceLoader`实现的。

基本概念是：

- 对服务的接口进行操作
- 通过`ServiceLoader`获取服务的实现
- 提供服务的实现

让我们从接口开始，并将其放入一个 jar 包，例如命名为`accounting-api.jar`。

```java
package example;
public interface AccountingService {
    long getBalance();
}
```

现在，我们在名为`accounting-impl.jar`的 jar 包中提供该服务的实现，其中包含了服务的实现：

```java
package example.impl;
import example.AccountingService;
public interface DefaultAccountingService implements AccountingService {
    long getBalanceFromDB();
}
```

```java
private long balanceFromDB() {
    ...
}
```

此外，`accounting-impl.jar`包含一个文件，声明该 jar 包提供了`AccountingService`的实现。该文件的路径必须以`META-INF/services/`开头，并且必须与接口的全限定类名相同：

`META-INF/services/example.AccountingService`

该文件的内容是实现类的全限定类名：

`example.impl.DefaultAccountingService`

由于两个 jar 包都在使用`AccountingService`的程序类路径中，可以通过`ServiceLoader`获取服务的实例：

```java
ServiceLoader<AccountingService> loader = ServiceLoader.load(AccountingService.class);
AccountingService service = loader.next();
long balance = service.getBalance();
```

由于`ServiceLoader`是一个`Iterable`（迭代器），它支持多个实现者，程序可以从中进行选择：

```java
ServiceLoader<AccountingService> loader = ServiceLoader.load(AccountingService.class);
for(AccountingService service : loader) {
    //...
}
```

注意，调用`next()`将总是创建一个新实例。如果你想重用实例，必须使用`ServiceLoader`的`iterator()`方法或上所示的 for-each 循环。

## 第 136.2 节：Logger 服务

以下示例展示了如何通过`ServiceLoader`实例化用于日志的类。

```java
package servicetest;
import java.io.IOException;
public interface Logger extends AutoCloseable {
    void log(String message) throws IOException;
}
```

服务的实现：

以下实现简单地将消息写入`System.err`：

```java
package servicetest.logger;
import servicetest.Logger;
public class ConsoleLogger implements Logger {
    @Override
    public void log(String message) { 
        System.err.println(message); 
    }

    @Override
    public void close() { }
}
```

以下实现将消息写入文本文件：

```java
package servicetest.logger;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import servicetest.Logger;

public class FileLogger implements Logger {
    private final BufferedWriter writer;

    public FileLogger() throws IOException {
        writer = new BufferedWriter(new FileWriter("log.txt"));
    }

    @Override
    public void log(String message) throws IOException {
        writer.append(message);
        writer.newLine();
    }

    @Override
    public void close() throws IOException {
        writer.close();
    }
}
```

`META-INF/services/servicetest.Logger`文件列出了`Logger`实现的名称：

```
servicetest.logger.ConsoleLogger
servicetest.logger.FileLogger
```

用法

以下的`main`方法将消息写入所有可用的日志器。这些日志器是通过`ServiceLoader`实例化的。

```java
public static void main(String[] args) throws Exception { 
    final String message = "Hello World!";
    // 获取 Logger 的 ServiceLoader
    ServiceLoader<Logger> loader = ServiceLoader.load(servicetest.Logger.class);

    // 遍历可用日志器的实例，并将消息写入每个日志器
    Iterator<Logger> iterator = loader.iterator();
    while (iterator.hasNext()) {
        try (Logger logger = iterator.next()) {
            logger.log(message);
        }
    }
}
```

## 第 137 章：类加载器

### 第 137.1 节：实现自定义类加载器

每个类加载器必须直接或间接地扩展`java.lang.ClassLoader`类。主要的扩展点是以下方法：

- `findClass(String)`
- `loadClass(String)`

`defineClass`方法负责从字节数组实际加载类。这里有一个从字节数组加载类的示例：

```java
public class ByteArrayClassLoader extends ClassLoader {
    private String className;
    private byte[] classfile;

    public ByteArrayClassLoader(String className, byte[] classfile) {
        this.className = className;
        this.classfile = classfile;
    }

    @Override
    protected Class findClass(String className) throws ClassNotFoundException {
        if (className.equals(this.className)) {
            return defineClass(className, classfile, 0, classfile.length);
        } else {
            throw new ClassNotFoundException(className);
        }
    }
}
```

由于我们只重写了`findClass`方法，当调用`loadClass`时，该类加载器的行为如下：

1. 类加载器的`loadClass`方法调用`findLoadedClass`查看该类是否已被类加载器加载。如果成功，则返回类对象给调用者。
2. `loadClass`方法通过调用其`loadClass`委托给父类加载器。如果父加载器可以处理该请求，它将返回类对象给调用者。
3. 如果父加载器无法加载类，`findClass`将调用我们的`findClass`并传递要加载的类名。
4. 如果请求的名称匹配`this.className`，我们调用`defineClass`从`this.classfile`加载实际类。返回类对象。
5. 如果名称不匹配，我们抛出`ClassNotFoundException`。

## 第 137.2 节：加载外部 .classfile

要加载类，我们需要定义它。类是由`ClassLoader`定义的。唯一的问题是，Oracle 在编写`ClassLoader`代码时并没有包含此功能。为了定义类，我们需要访问一个名为`defineClass`的方法，它是`ClassLoader`的私有方法。为了访问它，我们将创建一个名为`ByteClassLoader`的类并扩展`ClassLoader`。现在由于我们的类扩展了`ClassLoader`，就可以访问`ClassLoader`的私有方法。为了使`defineClass`可，我们将创建一个作为私有`defineClass`方法镜像的新方法。调用该私有方法需要类名、名称、类字节数组、第一个字节的偏移量（为 0，因为`classBytes`从`classBytes[0]`开始）以及最后一个字节的偏移量（为`classBytes.length`，因为它代表数据的大小）。

```java
public Class<?> defineClass(String name, byte[] classBytes) { 
    return super.defineClass(name, classBytes, 0, classBytes.length);
}
```

```java
defineClass(name, classBytes, 0, classBytes.length);
}
```

现在，我们有一个公有的`defineClass()`方法。它可以通过传递类名和类字节数组作为参数来调用。

假设我们在`stackoverflow...`包中有一个`MyClass`类。

为了调用该方法，我们需要类的字节数组，因此我们通过使用`Paths.get()`方法创建一个表示类路径的`Path`对象，并将二进制类的路径作为参数传递进去。现在，我们可以通过`Files.readAllBytes(path)`获取类字节数组。于是，我们创建一个`ByteClassLoader`实例并使用我们创建的方法`defineClass()`。我们已经拥有了类字节数组，但为了调用我们的方法，我们需要类名，它由包名（点分隔）和类的全限定名组成，在本例中为`stackoverflow.MyClass`。

```java
Path path = Paths.get("MyClass");
ByteClassLoader loader = new ByteClassLoader();
loader.defineClass("stackoverflow.MyClass", Files.readAllBytes(path));
```

注意：`defineClass()`方法返回一个`Class<?>`对象。如果你需要，可以将其保存。

要加载该类，我们只需调用`loadClass()`并传递类名。此方法可能会抛出`ClassNotFoundException`，因此我们需要使用`try catch`块。

```java
try { 
    loader.loadClass("stackoverflow.MyClass");
} catch (ClassNotFoundException e) {
    e.printStackTrace();
}
```

## 第 137.3 节：实例化和使用类加载器

这个基础示例展示了应用程序如何实例化类加载器并使用它来动态加载类。

```java
URL [] urls = new URL[][new URL("file/home/me/extras.jar")];
URLClassLoader loader = new URLClassLoader(urls);
Class<?> myObjectClass = loader.findClass("com.example.MyObject");
```

此示例中创建的类加载器将以默认加载器作为其父类，并在查找 "extra.jar" 之前会首先尝试在父类加载器中查找任何类。如果请求的类已经加载，`findClass`将返回之前加载的类的引用。

`findClass`可能会以多种方式失败。最常见的情况是：如果找不到命名的类，调用将抛出`ClassNotFoundException`。如果命名的类依赖于某些找不到的类，调用将抛出`NoClassDefFoundError`。

## 第 138 章：程序化创建图像

### 第 138.1 节：程序化地创建简单的图像并显示它

```java
class ImageCreationExample {
    static Image createSampleImage() {
        // 实例化一个新的 BufferedImage (Image 的子类) 
        BufferedImage img = new BufferedImage(640, 480, BufferedImage.TYPE_INT_ARGB);
```

```java
        // 在图像上进行绘制
        paintOnImage(img);
        return img;
    }

    static void paintOnImage(BufferedImage img) {
        // 获取一个可绘制的 Graphics2D (Graphics 的子类) 对象
        Graphics2D g2d = (Graphics2D) img.getGraphics();
```

```java
        // 一些示例绘制
        g2d.setColor(Color.BLACK);
        g2d.fillRect(0, 0, 640, 480);
        g2d.setColor(Color.WHITE);
        g2d.drawLine(0, 0, 640, 480);
        g2d.drawLine(0, 480, 640, 0);
        g2d.setColor(Color.YELLOW);
```

```java
        g2d.drawOval(200, 100, 240, 280);
        g2d.setColor(Color.RED);
        g2d.drawRect(150, 70, 340, 340);

        // 在图像上绘制可能会非常消耗内存
        // 所以最好尽早释放资源
        // 虽然这并不是必须的
        g2d.dispose();
    }

    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        Image img = createSampleImage();
        ImageIcon icon = new ImageIcon(img);
        frame.add(new JLabel(icon));
        frame.pack();
        frame.setVisible(true);
    }
}
```

## 第 138.2 节：将图像保存到磁盘

```java
public static void saveImage(String destination) throws IOException {
    // 在“程序化创建简单的图像并显示它”示例中实现
    BufferedImage img = createSampleImage();
```



## 第 138.3 节：在 `BufferedImage` 中设置单个像素的颜色

```java
BufferedImage image = new BufferedImage(256, 256, BufferedImage.TYPE_INT_ARGB);
```

```java
// 你不需要使用 Graphics 对象，可以读取并设置像素颜色
// 对于 (int i = 0; i < 256; i++) {
    for (int j = 0; j < 256; j++) {
        int alpha = 255; // 别忘记这个，或者使用 BufferedImage.TYPE_INT_RGB
        int red = i; // 或者你喜欢的任何公式
        int green = j; // 或者你喜欢的任何公式
        int blue = 50; // 或者你喜欢的任何公式
        int color = (alpha << 24) | (red << 16) | (green << 8) | blue;
        image.setRGB(i, j);
    }
ImageIO.write(image, "png", new File("computed.png"));
```

输出：

![](img/01cc8d667542262308c20b3f5bd7b_1069.png)

## 第 138.4 节：指定图像渲染质量

```java
static void setupQuality(Graphics2D g2d) {
    g2d.setRenderingHint(RenderingHints.KEY_ANTIASING, RenderingHints.VALUE_ANTIASING_ON);
    g2d.setRenderingHint(RenderingHints.KEY_RENDERING, RenderingHints.VALUE_RENDER_QUALITY); // 许多其他 Rendering/VALUE 对用于指定
}
```

```java
static void setupLow(Graphics2D g2d) {
    g2d.setRenderingHint(RenderingHints.KEY_ANTIASING, RenderingHints.VALUE_ANTIASING_OFF);
    g2d.setRenderingHint(RenderingHints.KEY_RENDERING, RenderingHints.VALUE_RENDER_SPEED);
}
```

`QUALITY` 和 `SPEED` 渲染的比较：

![](img/01cc8d667542262308c20b3f5bd7b_1070.png)

## 第 138.5 节：使用 `BufferedImage` 创建图像

```java
int width = 256; // 像素
int height = 256; // 像素
BufferedImage image = new BufferedImage(width, height, BufferedImage.TYPE_BYTE_ABGR);
```

```java
// BufferedImage.TYPE_BYTE_ABGR - 存储 RGB 颜色和可见性
Graphics g = image.createGraphics();

// 在 application draw(Graphics) 中绘制你喜欢的
g.setColor(Color.RED);

// 更多信息请参 javadoc
g.setColor(Color.BLUE);

// 在 application draw(Graphics) 中绘制你喜欢的
g.fillRect(20, 30, 50);

// 更多信息请参 javadoc
g.drawOval(120, 120, 80);

// 更多信息请参 javadoc
g.dispose();

// 更多信息请参 javadoc
ImageIO.write(image, "png", new File("image.png"));
```

输出：

![](img/01cc8d667542262308c20b3f5bd7b_1071.png)

## 第 138.6 节：编辑和重用 `BufferedImage`

```java
// 读取现有文件
BufferedImage cat = ImageIO.read(new File("cat.jpg")); // 读取
```

```java
// 现在创建一个新图像
BufferedImage cats = new BufferedImage(256, 256, BufferedImage.TYPE_BYTE_ABGR);
```

```java
// 现在创建一个新图像
Graphics g = cats.createGraphics();
```

```java
g.setColor(Color.RED);
for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 4; j++) {
        g.drawImage(cat, i * 64, j * 64, null);
    }
}
```

```java
g.setColor(Color.BLUE);
g.drawRect(0, 0, 255, 255); // 添加一些漂亮的边框
g.dispose(); // 完成
```

`ImageIO.write(cats, "png", new File("cats.png"));` 原始 `cat` 文件：

生成的文件：

![](img/01cc8d667542262308c20b3f5bd7b_1072.png)

## 第 138.7 节：如何缩放 `BufferedImage`

```java
/**
 * 使用由 BufferedImage 支持的 Graphics2D 对象调整大小
 * @param srcImg - 要缩放的源图像
 * @param w - 期望宽度
 * @param h - 期望高度
 * @return - 新的缩放图像
 */
```

```java
private BufferedImage getScaledImage(Image srcImg, int w, int h) {
    // 创建一个具有良好尺寸的新图像，包含或可能包含
    // 0.0 到 1.0 之间的 alpha 值。
    BufferedImage resizedImg = new BufferedImage(w, h, BufferedImage.TRANSLUCENT);

    // 创建一个设备无关的对象来绘制缩放后的图像
    Graphics2D g2 = resizedImg.createGraphics();

    // 这可以更改，参见：
    // http://stackoverflow.com/documentation/java/5482/creating-images-programmatically/1948/specifying-image-rendering-quality

    g2.setRenderingHint(RenderingHints.KEY_INTERPOLATION, RenderingHints.VALUE_INTERPOLATION_BILINEAR);
    // 最后在 Graphics2D 中以所需的尺寸绘制源图像。
    g2.draw(srcImg, 0, 0, w, h);
    // 释放此图形上下文并释放它正在使用的系统资源
    g2.dispose();
    // 返回创建 Graphics2D 的图像
    return resizedImg;
}
```

## 第 139 章：原子类型

| 参数 |  |
| :--- | :--- |
| `set` | 字段的 性设置 |

- `get`: 字段的易变性读取
- `lazySet`: 这是该字段的一个存储排序（store-ordered）操作
- `compareAndSet`: 如果值等于预期值，则将其设置为新值
- `getAndSet`: 获取当前值并更新

Java 原子类型（Atomic Types）是简单的可变类型，它们提供了线程安全且原子的基本操作，而无需使用锁。它们设计用于在锁会成为并发瓶颈，或者存在死锁（deadlock）或活锁（livelock）风险的场景。

## 第 139.1 节：创建原子类型

对于简单的多线程代码，使用同步（synchronization）是可以接受的。然而，使用同步会对活跃性产生影响，随着代码库变得越来越复杂，最终陷入死锁、饥饿（starvation）或活锁的概率会随之增加。

在更复杂的并发场景下，使用原子变量（Atomic Variables）通常是更好的替代方案，因为它允许以线程安全的方式访问单个变量，而不会产生 `synchronized` 方法或代码块的开销。

创建一个 `AtomicInteger` 类型：

```java
AtomicInteger int = new AtomicInteger() // 使用默认值 0 创建
AtomicInteger int = new AtomicInteger(1) // 使用初始值 1 创建
```

其他实例类型也是如此。

```java
AtomicIntegerArray intArray = new AtomicIntegerArray(10) // 创建特定长度的数组
AtomicIntegerArray intArray = new AtomicIntegerArray(new int[] {1, 2, 3}) // 使用另一个数组初始化数组
```

其他原子类型也是如此。

有一个显著的例外是，没有 `float` 和 `double` 类型。可以通过 `Float.floatToIntBits(float)` 和 `Float.intBitsToFloat(int)` 来模拟 `float`，以及通过 `Double.doubleToLongBits(double)` 和 `Double.longBitsToDouble(long)` 来模拟 `double`。

如果你愿意使用 `sun.misc.Unsafe`，你可以通过 `sun.misc.Unsafe` 中的原子操作将任何原始变量作为原子变量。所有原始类型都应该转换为或编码为 `int` 或 `long`，以便以此这种方式使用。

更多信息请参阅：`sun.misc.Unsafe`。

## 第 139.2 节：原子类型的动机

实现多线程应用的简单方法是使用 Java 内置的同步和锁原语；例如 `synchronized` 关键字。下面的示例展示了我们如何使用 `synchronized` 来累加计数。

```java
public class Counters {
    private final int[] counters;

    public Counters(int nosCounters) { 
        counters = new int[nosCounters];
    }
}
```

```java
/**
 * 增加指定索引处的整数
 */
public synchronized void count(int number) { 
    if (number >= 0 && number < counters.length) { 
        counters[number]++;
    }
}
```

```java
/**
 * 获取指定索引处数字的计数，
 * 如果该索引没有数字，则返回 0。
 */
public synchronized int getCount(int number) {
    return (number >= 0 && number < counters.length) ? counters[number] : 0;
}
```

这种实现可以正常工作。然而，如果你有大量线程对同一个 `Counters` 对象进行大量并发调用，同步可能会成为瓶颈。具体来说：

1. 每一个 **synchronized** 方法调用都会从当前线程开始获取 `Counters` 实例的锁。
2. 线程在检查 `number` 值并更新计数器时将持有锁。
3. 最后，它将释放锁，允许其他线程访问。

如果一个线程在另一个线程持有锁时尝试获取锁，尝试的线程将在步骤 1 处被阻塞（停止），直到锁被释放。如果有多个线程在等待，其中一个将获得锁，而其他将继续保持阻塞状态。

这可能会导致几个问题：

- 如果对锁存在大量的*竞争*（contention）（即：有大量线程尝试获取它），那么某些线程可能会被阻塞很长时间。
- 当一个线程被阻塞等待锁时，操作系统通常会将执行流切换到另一个线程。这种*上下文切换*（context switching）会对处理器产生相对重大的性能影响。
- 当有多个线程阻塞在同一个锁上时，无法保证其中任何一个线程会得到“公平”的对待（即保证每个线程都可能被调度运行）。这可能导致*线程饥饿*（thread starvation）。

## 如何实现原子类型？

让我们从上面那个使用 `AtomicInteger` 计数器的示例开始：

```java
public class Counters {
    private final AtomicInteger[] counters;

    public Counters(int nosCounters) {
        counters = new AtomicInteger[nosCounters];
        for (int i = 0; i < nosCounters; i++) {
            counters[i] = new AtomicInteger();
        }
    }
}
```

```java
/**
 * 增加指定索引处的整数
 */
public void count(int number) {
    if (number >= 0 && number < counters.length) {
        counters[number].incrementAndGet();
    }
}
```

```java
/**
 * 获取指定索引处对象的当前计数，如果该索引处
 * 数字，则返回 0。
 */
public int getCount(int number) {
    return (number >= 0 && number < counters.length) ?
        counters[number].get() : 0;
}
```

我们用 `AtomicInteger[]` 替换了 `int[]`，并在每个元素中用一个实例进行初始化。我们还添加了递增调用。

加密 AES 密钥。

- AES 加密的密钥大小将为 128 位。
- 对于 OAEP 和 GCM 均使用了所有默认参数选项。
- `@param publicKey` 用于封装（wrap）AES 密钥的 RSA 公钥
- `@param plaintext` 要加密的明文，该内容不会被改动
- `@return` 密文
- `@throws InvalidKeyException` 如果密钥不是 RSA 公钥
- `@throws NullPointerException` 如果明文为 `null`

```java
public static byte[] encryptData(PublicKey publicKey, byte[] plaintext)
throws InvalidKeyException, NullPointerException {

  // 创建 RSA OAEP 密器 --
  Cipher oaep;
  try {
    // SHA-1 是默认值，且在此设置下是安全的
    // 使用 OAEPParameterSpec 配置哈希值之外的参数
    oaep = Cipher.getInstance("RSA/ECB/OAEPwithSHA1andMGF1Padding");
  } catch (NoSuchAlgorithmException e) {
    throw new RuntimeException(
      "运行时不支持 RSA 密器（运行时强制算法）", e);
  } catch (NoSuchPaddingException e) {
    throw new RuntimeException(
      "运行时不支持 OAEP 填充（在标准 Java 运行时 XX 中存在）", e);
  }
  oaep.init(Cipher.WRAP_MODE, publicKey);

  // 将明文放入缓冲区
  // 如果 plaintext 为 null ByteBuffer，将抛出 NullPointerException
  plaintextBuffer = ByteBuffer.wrap(plaintext);
  // --- 生成一个新的 AES 密钥密钥 --
  KeyGenerator aesKeyGenerator;
}
```



# 第 142 章：安全与密码学

## 第 142.1 节：计算加密哈希

使用不同的算法计算较小数据块的哈希：

```java
final MessageDigest md5 = MessageDigest.getInstance("MD5");
final MessageDigest sha1 = MessageDigest.getInstance("SHA-1");
final MessageDigest sha256 = MessageDigest.getInstance("SHA-256");

final byte[] data = "FOO BAR".getBytes();
```

```java
System.out.println("MD5 hash: " + DatatypeConverter.printHexBinary(md5.digest(data)));
System.out.println("SHA1 hash: " + DatatypeConverter.printHexBinary(sha1.digest(data)));
System.out.println("SHA256 hash: " + DatatypeConverter.printHexBinary(sha256.digest(data)));
```

产生如下输出：

```
MD5 hash : E99E76852F6DD5A3BA2D9C849F736E
SHA1 hash: 0135FA6323685BA8A8FF8D3F955F0C3649D8FB
SHA256 hash: D35C7BCD902B96D1B551741BBE8A7F50BB56A90B4D0225482EAA6
```

取决于你 Java 平台的实现，可能还有其他算法。

## 第 142.2 节：使用公钥/私钥加密解密数据

使用公钥加密数据：

```java
final Cipher cipher = Cipher.getInstance("RSA");
```

```java
rsa.init(Cipher.ENCRYPT_MODE, keyPair.getPublic());
rsa.update(message.getBytes());
final byte[] result = rsa.doFinal();
```

```java
System.out.println("Message: " + message);
System.out.println("Encrypted: " + DatatypeConverter.printHexBinary(result));
```

产生类似的输出：

```
Message: Hello
Encrypted: 5641FBB9558ECFA9ED...
```

注意在创建`Cipher`对象时，必须指定与所使用的密钥类型兼容的转换（参见 JCA 标准算法名称获取支持的转换列表）。对于 RSA 加密，`message.getBytes()`的长度必须小于密钥大小。

详情请参考此 SO 回答。

解密数据：

```java
final Cipher rsa = Cipher.getInstance("RSA");
rsa.init(Cipher.DECRYPT_MODE, keyPair.getPrivate());
rsa.update(cipher);
final String result = new String(rsa.doFinal());
System.out.println("Decrypted: " + result);
```

产生以下输出：

```
Decrypted: Hello
```

## 第 142.3 节：生成加密随机数据

生成加密随机数据的样本：

```java
final byte[] sample = new byte[16];
new SecureRandom().nextBytes(sample);
System.out.println("Sample: " + DatatypeConverter.printHexBinary(sample));
```

产生类似的输出：

```
Sample: E4F14CEA2ADB34F706B53A6DF8C5FE
```

注意，取决于所使用的算法，调用`nextBytes()`可能会在收集熵时阻塞。

要指定算法和提供者：

```java
final byte[] sample = new byte[16];
final SecureRandom randomness = SecureRandom.getInstance("SHA1PRNG", "SUN");
randomness.nextBytes(sample);
System.out.println("Provider: " + randomness.getProvider());
System.out.println("Algorithm: " + randomness.getAlgorithm());
System.out.println("Sample: " + DatatypeConverter.printHexBinary(sample));
```

产生类似的输出：

```
Provider: SUN version 1.8
Algorithm: SHA1PRNG
Sample: C80C44BAEB352FD29FBBE20489E4C0B99
```

## 第 142.4 节：生成公钥/私钥密钥对

使用不同的算法和密钥大小生成密钥对：

```java
final KeyPairGenerator dhGenerator = KeyPairGenerator.getInstance("DiffieHellman"); 
final KeyPairGenerator dsaGenerator = KeyPairGenerator.getInstance("DSA"); 
final KeyPairGenerator rsaGenerator = KeyPairGenerator.getInstance("RSA");
```

```java
dhGenerator.initialize(1024);
dsaGenerator.initialize(1024);
rsaGenerator.initialize(2048);
```

---

以下是使用混合加密系统（GCM 加密数据，OAEP 加密 AES 密钥）的完整示例：

```java
try {
  aesKeyGenerator = KeyGenerator.getInstance("AES");
} catch (NoSuchAlgorithmException e) {
  throw new RuntimeException(
    "运行时不支持 AES 密钥生成器（运行时强制算法）", e);
}
// 对于 AES-192 和 256，请确保你已获得权限（安装了
// 无限制加密策略策略文件）
aesKeyGenerator.init(128);
SecretKey aesKey = aesKeyGenerator.generateKey();

// -- 封装新的 AES 密钥密钥 --
byte[] wrappedKey;
try {
wrappedKey = oaep.wrap(aesKey);
} catch (IllegalBlockSizeException e) {
  throw new RuntimeException(
    "AES 密钥应始终适用于正常大小 RSA 密钥的 OAEP", e);
}
// -- 设置 AES GCM 密器模式 --

Cipher aesGCM;
try {
  aesGCM = Cipher.getInstance("AES/GCM/NoPadding");
  // 由于密钥是随机生成的，我们可以使用零随机数（nonce）
  // 128 位是标签大小的推荐（最值）值
  // 12 字节（96 位）是 GCM 模式加密的默认随机数
  GCMParameterSpec staticParameterSpec = new GCMParameterSpec(128, new byte[12]);
  aesGCM.init(Cipher.ENCRYPT_MODE, aesKey, staticParameterSpec);
} catch (NoSuchAlgorithmException e) {
  throw new RuntimeException("运行时不支持 AES 密器（运行时强制算法rtimes）", e);
} catch (NoSuchPaddingException e) {
  throw new RuntimeException("运行时不支持 GCM（在标准 Java 运行时 XX 中存在）", e);
} catch (InvalidAlgorithmParameterException e) {
  throw new RuntimeException("InvalidParameterSpec 不被此 GCM 实现接受", e);
}
```

```java
// 为我们自己的协议创建一个合适大小的缓冲区 --
ByteBuffer ciphertextBuffer = ByteBuffer.allocate(Short.BYTES + oaep.getOutputSize(128 / Byte.SIZE) + aesGCM.getOutputSize(plaintext.length));

// 元素 1：确保我们知道封装的密钥密文的大小。
ciphertextBuffer.put((short) wrappedKey.length);
// 元素 2：放入封装的密钥
ciphertextBuffer.put(wrappedKey);
// 元素 3：GCM 加密到缓冲区
try {
  aesGCM.doFinal(ciphertextBuffer, ciphertextBuffer);
} catch (ShortBufferException | IllegalBlockSizeException | BadPaddingException e) {
  throw new RuntimeException("加密异常，AES/GCM 加密不应在此失败", e);
}
return ciphertextBuffer.array();
```

如果没有解密，加密将毫无用处。请注意，如果解密失败，将返回最少的信息。

```java
/**
 * 使用混合加密系统解密数据，该系统使用 GCM 加密数据
 * 使用 OAEP 加密 AES 密钥。对于 OAEP 和 GCM 均使用了所有默认参数选项。
 *
 * @param privateKey 用于解封装 AES 密钥的 RSA 私钥
 * @param ciphertext 要加密的密文，该内容不会被改动
 * @return 明文
 * @throws InvalidKeyException
 * 如果密钥不是 RSA 私钥
 * @throws NullPointerException
 * 如果密文为 null
 * @throws IllegalArgumentException
 * 如果密文无效，则抛出消息为 "Invalid ciphertext" 的异常
 * （最小化信息泄露）
 */
public static byte[] decryptData(PrivateKey privateKey, byte[] ciphertext)
throws InvalidKeyException, NullPointerException {

  // 创建 RSA OAEP 密器 --
  Cipher oaep;
  try {
    // SHA-1 是默认值，且在此设置下是安全的
    // 使用 OAEPParameterSpec 配置哈希值之外的参数
    oaep = Cipher.getInstance("RSA/ECB/OAEPwithSHA1andMGF1Padding");
  } catch (NoSuchAlgorithmException e) {
    throw new RuntimeException(
      "运行时不支持 RSA 密器（运行时强制算法）", e);
  } catch (NoSuchPaddingException e) {
    throw new RuntimeException(
      "运行时不支持 OAEP 填充（在标准 Java 运行时 XX 中存在）", e);
  }
  oaep.init(Cipher.WRAP_MODE, privateKey);

  // 将密文放入缓冲区
  // 如果 ciphertext 为 null，ByteBuffer.wrap 将抛出 NullPointerException
  ByteBuffer ciphertextBuffer = ByteBuffer.wrap(ciphertext);
  // 完整检查
  if (ciphertextBuffer.remaining() < Short.BYTES) {
    throw new IllegalArgumentException("Invalid ciphertext");
  }
  // 元素 1：确保我们知道封装的密钥的大小
  int wrappedKeySize = ciphertextBuffer.getShort();
  // 完整检查
  if (ciphertextBuffer.remaining() < wrappedKeySize) {
    throw new IllegalArgumentException("Invalid ciphertext");
  }
  // 元素 2：放入封装的密钥
  byte[] wrappedKey = new byte[wrappedKeySize];
  ciphertextBuffer.get(wrappedKey);
  // --- 解封装 AES 密钥密钥 --
  SecretKey aesKey;
  try {
    aesKey = (SecretKey) oaep.unwrap(wrappedKey);
  } catch (Exception e) {
    throw new RuntimeException("加密异常，AES/GCM 解密不应在此失败", e);
  }
  // -- 设置 AES GCM 密器模式 --
  Cipher aesGCM;
  try {
    aesGCM = Cipher.getInstance("AES/GCM/NoPadding");
    // 由于密钥是随机生成的，我们可以使用零随机数（nonce）
    // 128 位是标签大小的推荐（最值）值
    // 12 字节（96 位）是 GCM 模式加密的默认随机数
    GCMParameterSpec staticParameterSpec = new GCMParameterSpec(128, new byte[12]);
    aesGCM.init(Cipher.DECRYPT_MODE, aesKey, staticParameterSpec);
  } catch (NoSuchAlgorithmException e) {
    throw new RuntimeException("运行时不支持 AES 密器（运行时强制算法rtimes）", e);
  } catch (NoSuchPaddingException e) {
    throw new RuntimeException("运行时不支持 GCM（在标准 Java 运行时 XX 中存在）", e);
  } catch (InvalidAlgorithmParameterException e) {
    throw new RuntimeException("InvalidParameterSpec 不被此 GCM 实现接受", e);
  }

  // 元素 3：GCM 解密到缓冲区
  try {
    return aesGCM.doFinal(ciphertextBuffer).array();
  } catch (ShortBufferException | IllegalBlockSizeException | BadPaddingException e) {
    throw new RuntimeException("解密异常，AES/GCM 解密不应在此失败", e);
  }
}
```

以下是一个使用 `SignedObject` 的示例：

```java
// 创建密钥
KeyPairGenerator keyGen = KeyPairGenerator.getInstance("DSA", "SUN");
SecureRandom random = SecureRandom.getInstance("SHA1PRNG", "SUN");
keyGen.initialize(1024, random);
// 创建私钥
PrivateKey signingKey = keyGen.generateKeyPair().getPrivate();
// 创建签名
Signature signingEngine = Signature.getInstance("DSA");
signingEngine.initSign(signingKey);
// 创建简单对象
Serializable obj = new String("John");
// 对对象签名
SignedObject signedObject = new SignedObject(obj, signingKey, signingEngine);

System.out.println("signedObject-" + signedObject);
System.out.println("signedObject Data-" + signedObject.getObject());
```



```java
final KeyPair dhPair = dhGenerator.generateKeyPair();
final KeyPair dsaPair = dsaGenerator.generateKeyPair();
final KeyPair rsaPair = rsaGenerator.generateKeyPair();
```

你的 Java 平台实现可能提供额外的算法和密钥大小。

在生成密钥时指定随机性源：

```java
final KeyPairGenerator generator = KeyPairGenerator.getInstance("RSA");
generator.initialize(2048, SecureRandom.getInstance("SHA1PRNG", "SUN")); 
final KeyPair pair = generator.generateKeyPair();
```

## 第 142.5 节：计算与验证数字签名

计算签名：

```java
final PrivateKey privateKey = keyPair.getPrivate();
final byte[] data = "FOO BAR".getBytes();
```

```java
final Signature signer = Signature.getInstance("SHA1withRSA");
signer.initSign(privateKey);
signer.update(data);
final byte[] signature = signer.sign();
```

注意，签名算法必须与用于密钥密钥对的算法兼容。

验证签名：

```java
final PublicKey publicKey = keyPair.getPublic();
```

```java
final Signature verifier = Signature.getInstance("SHA1withRSA");
```

```java
verifier.initVerify(publicKey);
```

```java
verifier.update(data);
```

```java
System.out.println("Signature: " + verifier.verify(signature));
```

## 第 143 章：安全与密码学

Java 安全实践可以分为两个宽泛且定义模糊的类别：Java 平台安全和安全 Java 编程。

Java 平台安全实践涉及管理 JVM 的安全和完整性。包括管理 JCE 提供者和安全策略等主题。

安全 Java 编程涉及编写安全 Java 最佳方法。包括使用随机数和密码学以及防止漏洞。

## 第 143.1 节：JCE

Java 加密扩展 (JCE) 是内置在 JVM 中的一个框架，允许开发者在程序中方便且安全地使用密码学。它通过为程序员提供简单、可移植的接口来实现，同时使用 JCE 提供者系统安全地实现底层加密操作。

## 第 143.2 节：密钥与密钥管理

虽然 JCE 保护了加密操作和密钥生成，但实际管理密钥取决于开发者。需要提供更多信息。

运行时处理密钥的一种通常接受的最佳实践是仅将其存储为字节数组，而绝不存储为字符串。这是因为 Java 字符串是不可变的，无法在内存中手动“清除”或“置零”；虽然可以移除字符串的引用，但该字符串将留在内存中，直到其内存段被垃圾回收。攻击者会有很长的窗口来转储程序的内存并轻松地找到密钥。相反，字节数组是可变的，可以在原地覆盖其内容；在不再需要密钥时立即将其内容“置零”是一个好主意。

## 第 143.3 节：常见 Java 漏洞

## 第 143.4 节：网络关注

## 第 143.5 节：随机性与你

对于许多应用程序，`java.util.Random` 类是“随机”数据的完美来源。如果你需要从数组中选择一个随机元素，或者生成随机字符串，或者创建一个临时的“唯一”标识符，你可能应该使用 `Random`。

然而，许多加密系统依赖随机性来实现安全性，而 `Random` 提供的随机性质量不够。对于任何需要随机输入的加密操作，你应该使用 `SecureRandom`。

## 第 143.6 节：哈希与验证

密哈希函数是一类具有重要属性的函数的成员：一致性、唯一性和不可逆性。

一致性：给定相同的数据，哈希函数始终返回相同的值。也就是说，如果 X = Y，对于哈希函数 f，f(x) 将始终等于 f(y)。

唯一性：哈希函数的任何两个输入都不会产生相同的值。也就是说，如果 X != Y，对于任何 X 值和 Y 值，f(x) != f(y)。

不可逆性：“反转”哈希函数在实践上是困难的，甚至是不可能的。也就是说，仅给定 f(X)，除非将所有可能的 X 值通过函数 f，否则没有办法可以找到原始的 X。

（暴力破解）。不应存在任何函数 f1 使得 f1(f(X)) = X。

许多函数缺乏这些属性中的至少一个。例如，众之 MD5 和 SHA1 存在碰撞问题，即两个不同的输入具有相同的输出，它们缺乏唯一性。目前被认为是安全的函数有 SHA-256 和 SHA-512。

# 第 144 章：SecurityManager

## 第 144.1 节：对 Class 加载的类进行沙箱

`ClassLoader` 需要提供一个 `ProtectionDomain` 来标识代码的来源：

```java
public class PluginClassLoader extends ClassLoader {

    private final ClassProvider provider;

    private final ProtectionDomain pd;

    public PluginClassLoader(ClassProvider provider) {

        this.provider = provider;

        Permissions permissions = new Permissions();
```

```java
        this.pd = new ProtectionDomain(provider.getCodeSource(), permissions, this, null);

    }
```

```java
    @Override

    protected Class<?> findClass(String name) throws ClassNotFoundException {

        byte[] classDef = provider.getClass(name);

        Class<?> clazz = defineClass(name, classDef, 0, classDef.length, pd);

        return clazz;

    }

}
```

通过重写 `findClass` 而不是 `loadClass`，保留了委托模型，`PluginClassLoader` 将首先查询系统和父类加载器以获取类定义。

创建一个 `Policy`：

```java
public class PluginSecurityPolicy extends Policy {

    private final Permissions appPermissions = new Permissions();

    private final Permissions pluginPermissions = new Permissions();
```

```java
    public PluginSecurityPolicy() {

        // 根据需要修改此处

        appPermissions.add(new AllPermission());

        // 将插件应拥有的任何权限添加到 pluginPermissions

    }

    @Override

    public Provider getProvider() {

        return super.getProvider();

    }

    @Override

    public String getType() {

        return super.getType();

    }

    @Override

    public Parameters getParameters() {

        return super.getParameters();

    }

    @Override

    public PermissionCollection getPermissions(CodeSource codesource) {

        return new Permissions();

    }

    @Override

    public PermissionCollection getPermissions(ProtectionDomain domain) {

        return isPlugin(domain) ? pluginPermissions : appPermissions;

    }
```

```java
    private boolean isPlugin(ProtectionDomain pd) {

        return pd.getClassLoader() instanceof PluginClassLoader;

    }

}
```

最后，设置 `policy` 和 `SecurityManager`（默认实现）：

```java
Policy.setPolicy(new PluginSecurityPolicy());
System.setSecurityManager(new SecurityManager());
```

## 第 144.2 节：启用 SecurityManager

Java 虚拟机 (JVM) 可以在安装了 `SecurityManager` 的情况下运行。`SecurityManager` 负责管理 JVM 中运行的代码被允许的操作，这取决于代码从哪里加载以及使用了哪些证书对代码签名等因素。

可以在启动 JVM 时通过命令行设置 `java.security.manager` 系统属性来安装 `SecurityManager`：

```java
java -Djava.security.manager <class name>
```

或在 Java 内部通过程序设置：

```java
System.setSecurityManager(new SecurityManager())
```

标准的 Java `SecurityManager` 根据 `Policy` 授予权限，`Policy` 定义在策略文件中。如果未指定策略文件，将使用位于 `$JAVA_HOME/lib/security/java.policy` 下的默认策略文件。

## 第 144.3 节：实现策略的拒绝规则

有时需要对某些 `ProtectionDomain` 拒绝某些 `Permission`，无论该领域还获得了任何其他权限。此示例演示了满足此类要求的各种可能方法之一。它引入了一个“负向”权限类，以及一个包装器，允许默认 `Policy` 被重用作为此类权限的存储库。

注意：

- 标准的策略文件语法和通用的权限分配机制不受受影响。这意味着策略文件中的拒绝规则仍然以 `grants` 的形式表示。
- 策略包装器旨在专门封装默认的文件支持型 `Policy`（假设为 `com.sun.security.provider.PolicyFile`）。
- 被拒绝的权限仅在策略级别进行处理。如果静态地分配给某个领域，默认情况下，该领域将把它们视为普通的“正向”权限。

`DeniedPermission` 类包 `com.example`：

```java
import java.lang.reflect.Constructor;
```

```java
import java.lang.reflect.InvocationTargetException;

import java.lang.reflect.Modifier;

import java.security.BasicPermission;
```

```java
import java.security.Permission;

import java.security.UnresolvedPermission;

import java.text.MessageFormat;
```

```java
/**
 * 一个“负向”权限的表示。
 * 一个 <code>DeniedPermission</code> 当它被“授予”时（给某些
 * <code>ProtectionDomain</code> 和/或 <code>Principal</code>），
 * 代表一种<em>无法</em>行行的权限，无论拥有任何
 * 正向权限（包括 <code>AllPermission</code>）。
 * 换句话说，如果一个 *已授予的权限集* 
 * 包含该类的权限且被<em>拒绝</em>，那么 *
 * 有效授予的权限集是
 * &nbsp;&nbsp;&nbsp;&nbsp;<sub>implied</sub> - 
 * D-<sub>implied</sub> - * /
 * <p>
 * 此类的每个实例都封装了一个<em>目标权限</em>，
 * 代表被拒绝的 *“正向”权限。
 * </p>
 * 拒绝权限采用以下命名方案：<br/>
 * <br/>
 * &nbsp;&nbsp;&nbsp;&nbsp;
 * &lt;target_class_name&gt;&lt;target_name&gt;(&lt;target_actions&gt;})<br/>
 * 其中：
 * <ul>
 * <li>&lt;target_class_name&gt; 是目标权限的类名，</li>
 * <li>&lt;target_name&gt; 是目标权限的名称，</li>
 * <li>&lt;target_actions&gt; 是可选的动作字符串。</li>
 * </ul>
 * 具有权限 <em>t</em> 的拒绝权限被认为<em>暗示</em>
 * 另一个权限<em>p</em>，如果：
 * <ul>
 * <li>p <em>不是</em>拒绝权限本身且 <code>t.implies(p) == true</code>，</li>
 * 或者
 * <li>p <em>是</em>具有目标 <em>t1</em> 的拒绝权限，
 * <code>t.implies(t1) == true</code>。</li>
 * </ul>
 * <p>
 * 策略决策点（例如 <code>Policy</code> 提供者）在发布授权语句时
 * 有责任考虑拒绝权限的语义。
 * </p>
 */
```

```java
public final class DeniedPermission extends BasicPermission {

    private final Permission target;

    private static final long serialVersionUID = 47362516386980679L;

    /**
     * 实例化一个封装了指定类、指定名称以及可选动作的
     * <code>DeniedPermission</code>。
     *
     * @throws IllegalArgumentException
     * 如果：
     * <ul>
     * <li><code>targetName</code>code 为 <code>null</code>code、空字符串、
     * 未引用具体的 <code>Permission</code>code子类，或者引用了
     * <code>DeniedPermission.class</code>code 或 <code>UnresolvedPermission.class</code>。</li>
     * <li><code>targetName</code>code 为 <code>null</code>code。</li>
     * <li><code>targetClassName</code>code> 无法实例化
     */
```

```java
    public DeniedPermission(String name) {

        super(name);

        String[] comps = name.split(":");

        if (comps.length < 2) {

            throw new IllegalArgumentException(MessageFormat.format("Malformed
name {0} argument.", name));

        }

        this.target= initTarget(comps[0], comps[1], ((comps.length < 3) ? null : comps[2]));

    }

}
```

如果 `target` 为 `null`，`DeniedPermission`，或者 `UnresolvedPermission`。

```java
public static DeniedPermission newDeniedPermission(Permission target) {

    if (target == null) {

        throw new IllegalArgumentException("Null [target] argument.");

    }
```



# 介绍

![](img/01cc8d6667542262308c820b3f5bd37b_1110_0.png)

Java 命名和目录接口 (JNDI) 是一种用于目录服务的 Java API，允许 Java 软件客户端通过名称发现并查找数据及对象。它的设计旨在独立于任何特定的命名或目录服务实现。

JNDI 架构由 API（应用程序编程接口）和 SPI（服务提供接口）组成。Java 程序使用此 API 访问各种命名和目录服务。SPI 允许各种命名和目录服务透明地插入，从而使得使用 JNDI 技术 API 的 Java 程序能够访问它们的服务。

如上图所示，JNDI 支持 LDAP、DNS、NIS、NDS、RMI 和 CORBA。当然，你也可以对其进行扩展。

# 工作原理

在示例中，Java RMI 注册表通过 JNDI API 在网络中查找对象。如果你想查找一个对象，至少需要两条信息：

- 在哪里找到对象：RMI 注册表管理名称绑定，它告诉你在哪里找到该对象。

## 代码示例

### 1. 服务端代码

```java
package com.neohope.jndi.test;

import javax.naming.Context;
import javax.naming.InitialContext;
import javax.naming.NamingException;
import java.util.Hashtable;

/**
 * 1. 初始化上下文
 * 2. 查找注册表服务
 * 3. 使用服务
 * 4. 结束
 */
public class Server {
    private static InitialContext ctx;

    public static void initJNDI() throws NamingException {
        final Hashtable jndiProperties = new Hashtable();
        jndiProperties.put(Context.INITIAL_CONTEXT_FACTORY, "com.sun.jndi.rmi.registry.RegistryContextFactory");
        jndiProperties.put(Context.PROVIDER_URL, "rmi://localhost:1234");
        ctx = new InitialContext(jndiProperties);
    }

    public static void bindJNDI(String name, Object obj) throws NamingException {
        ctx.bind(name, obj);
    }

    public static void unbindJNDI(String name) throws NamingException {
        ctx.unbind(name);
    }

    public static void uninitJNDI() throws NamingException {
        ctx.close();
    }

    public static void main(String[] args) throws NamingException, IOException {
        initJNDI();
        NMessage msg = new NMessage("Just A Message");
        bindJNDI("/neohope/jndi/test01", msg);
        System.in.read();
        unbindJNDI("/neohope/jndi/test01");
        initJNDI();
    }
}
```

### 2. 客户端代码

```java
package com.neohope.jndi.test;

import javax.naming.Context;
import javax.naming.InitialContext;
import javax.naming.NamingException;
import java.util.Hashtable;

/**
 * 1. 初始化上下文
 * 2. 查找注册表服务
 * 3. 使用服务
 * 4. 结束
 */
public class Client {
    public static void main(String[] args) throws NamingException {
        final Hashtable jndiProperties = new Hashtable();
        jndiProperties.put(Context.INITIAL_CONTEXT_FACTORY, "com.sun.jndi.rmi.registry.RegistryContextFactory");
        jndiProperties.put(Context.PROVIDER_URL, "rmi://localhost:1234");

        InitialContext ctx = new InitialContext(jndiProperties);
        NMessage msg = (NMessage) ctx.lookup("/neohope/jndi/test01");
        System.out.println(msg.message);
    }
}
```

### 3. NMessage.java (RMI 服务类)

```java
package com.neohope.jndi.test;

import java.io.Serializable;
import java.rmi.Remote;

/**
 * NMessage
 * RMI 服务类
 * 必须实现 Remote 和 Serializable
 */
public class NMessage implements Remote, Serializable {
    public String message = "";

    public NMessage(String message) {
        this.message = message;
    }
}
```

### 4. DenyingPolicy 类

```java
package com.security.example;

import java.security.CodeSource;
import java.security.NoSuchAlgorithmException;
import java.security.Permission;
import java.security.PermissionCollection;
import java.security.Policy;
import java.security.ProtectionDomain;
import java.security.UnresolvedPermission;
import java.util.Enumeration;

/**
 * 为标准的基于文件的 <code>Policy</code> 添加基础的 {@link DeniedPermission} 处理能力的包装器。
 */
public final class DenyingPolicy extends Policy {
    private final Policy defaultPolicy;

    public DenyingPolicy() {
        try {
            defaultPolicy = Policy.getInstance("javaPolicy", null);
        }
        catch (NoSuchAlgorithmException nsae) {
            throw new RuntimeException("Could not acquire default Policy.", nsae);
        }
    }

    @Override
    public PermissionCollection getPermissions(CodeSource codesource) {
        return defaultPolicy.getPermissions(codesource);
    }

    @Override
    public PermissionCollection getPermissions(ProtectionDomain domain) {
        return defaultPolicy.getPermissions(domain);
    }

    /**
     * @return
     * <ul>
     * <li><code>true</code> 如果：</li>
     * <ul>
     * <li><code>permission</code> <em>不是</em> <code>DeniedPermission</code> 的实例，</li>
     * <li>如果 <code>implies(domain, permission)</code> <code>Policy</code> <code>产生</code> <code>true</code>，且</li>
     * <li><code>permission</code> <em>没有被</em>任何可能分配给 <code>domain</code> 的 <code>DeniedPermission</code> 隐含。</li>
     * </ul>
     * <li><code>false</code>，否则。
     * </ul>
     */
    @Override
    public boolean implies(ProtectionDomain domain, Permission permission) {
        if (permission instanceof DeniedPermission) {
            return false;
        }
        /*
         * 在策略决策层面，DeniedPermissions 只能自身隐含，而不会被隐含（因为它们剥夺而不是授予权限）。此外，客户端不应该使用它们。
         */
        return defaultPolicy.implies(domain, permission);
    }
}
```

### 5. DeniedPermission 相关代码

```java
if (target instanceof DeniedPermission || target instanceof UnresolvedPermission) {
    throw new IllegalArgumentException("[target] must not be a DeniedPermission or an UnresolvedPermission.");
}

StringBuilder sb = new StringBuilder();
sb.append(target.getClass().getName()).append(":").append(target.getName());

String targetActions = target.getActions();
if (targetActions != null) {
    sb.append("-").append(targetActions);
}

return new DeniedPermission(sb.toString(), target);
```

```java
private DeniedPermission(String name, Permission target) {
    super(name);
    this.target = target;
}

private Permission initTarget(String targetClassName, String targetName, String targetActions) {
    Class<?> targetClass;
    try {
        targetClass = Class.forName(targetClassName);
    }
    catch (ClassNotFoundException cfe) {
        if (targetClassName.trim().isEmpty()) {
            targetClassName = "<empty>";
        }
        throw new IllegalArgumentException(MessageFormat.format("Target Permission class [{}] not found.", targetClassName));
    }

    if (!Permission.isAssignableFrom(targetClass) ||
        Modifier.isAbstract(targetClass.getModifiers())) {
        throw new IllegalArgumentException(MessageFormat.format("Target Permission class [{}] is not a (concrete) Permission.", targetClassName));
    }

    if (targetClass == DeniedPermission.class || targetClass == UnresolvedPermission.class) {
        throw new IllegalArgumentException("Target Permission class cannot be a DeniedPermission itself.");
    }

    Constructor<?> targetCtor;
    try {
        if (targetActions == null) {
            targetCtor = targetClass.getConstructor(String.class);
        } else {
            targetCtor = targetClass.getConstructor(String.class, String.class);
        }
    }
    catch (NoSuchMethodException nsme) {
        throw new IllegalArgumentException(MessageFormat.format(
            "Target Permission class [{}] does not provide or expose a (String name) or (String name, String actions) constructor.", targetClassName));
    }

    try {
        return (Permission) targetCtor
            .newInstance((targetCtor.getParameterCount() == 1) ? new Object[] { targetName } : new Object[] { targetName, targetActions });
    }
    catch (ReflectiveOperationException roe) {
        if (targetName == null) {
            targetName = "null";
        } else if (targetName.trim().isEmpty()) {
            targetName = "empty";
        }
        if (targetActions == null) {
            targetActions = "null";
        } else if (targetActions.trim().isEmpty()) {
            targetActions = "empty";
        }
        throw new IllegalArgumentException(MessageFormat.format(
            "Could not instantiate target Permission class [{0}]; provided target name [{1}] and/or target actions [{2}] potentially erroneous.",
            targetClassName, targetName, targetActions), roe);
    }
    throw new RuntimeException(
        "Could not instantiate target Permission class [{0}]; an unforeseen error occurred - see attached cause for details",
        roe);
}
```

```java
// 检查给定的权限是否被此权限隐含，参见 {@link DeniedPermission} 概述。
/*
@Override
public boolean implies(Permission p) {
    if (p instanceof DeniedPermission) {
        return target.implies((DeniedPermission) p);
    }
    return target.implies(p);
}
*/
```

```java
/**
 * 返回此拒绝权限的目标权限（不应被授予的实际正权限）。
 */
public Permission getTargetPermission() { return target; }
```

## 如何运行此示例

1. 编译并启动服务端
2. 编译并启动客户端



# 对象名称与 JNDI 绑定

对象的名称是什么？它通常是一个字符串，也可以是一个实现了`Name`接口的对象。

## 逐步步骤

1. 首先，你需要一个注册表来管理名称绑定。在示例中，我们使用`java.rmi.registry.LocateRegistry`。

```java
// 这将在本地的 1234 端口启动一个注册表
registry = LocateRegistry.createRegistry(1234);
```

2. 客户端和服务器都需要一个`Context`。服务器使用`Context`绑定名称和对象。客户端使用`Context`查找名称并获取对象。

```java
// 我们使用 com.sun.jndi.rmi.registry.RegistryContextFactory 作为 InitialContextFactory
final Hashtable jndiProperties = new Hashtable();
jndiProperties.put(Context.INITIAL_CONTEXT_FACTORY, "com.sun.jndi.rmi.registry.RegistryContextFactory");

// 注册表 URL 是 "rmi://localhost:1234"
jndiProperties.put(Context.PROVIDER_URL, "rmi://localhost:1234");

InitialContext ctx = new InitialContext(jndiProperties);
```

3. 服务器绑定名称和对象：

```java
// 该 jndi 名称为 "/neohope/jndi/test01"
bindJNDI("/neohope/jndi/test01", msg);
```

4. 客户端查找对象：

```java
// 该 jndi 名称为 "/neohope/jndi/test01"
unbindJNDI("/neohope/jndi/test01");
initJNDI();
```

5. 现在客户端使用对象。

6. 服务器结束，需要清理。

# Java 内存模型与多线程

如果该类被用于单线程应用程序，那么其可观测行为将完全如你预期的一样。例如：

```java
public class SingleThreaded {
    public static void main(String[] args) {
        Example eg = new Example();
        System.out.println(eg.a + " , " + eg.c);
        eg.dolt();
        System.out.println(eg.a + " , " + eg.c);
    }
}
```

输出将为：

```
0, 0
1, 1
```

从主线程的角度来看，`main()`方法和`dolt()`方法中的语句将按照它们在源代码中编写的顺序执行。这是 Java 语言规范（JLS）的明确要求。

现在考虑在多线程应用程序中使用同一个类。

```java
public class MultiThreaded {
    public static void main(String[] args) {
        final Example eg = new Example();
        new Thread(new Runnable() {
            public void run() {
                while (true) {
                    eg.dolt();
                }
            }
        }).start();
        while (true) {
            System.out.println(eg.a + " , " + eg.c);
        }
    }
}
```

这会打印什么？事实上，根据 JLS，无法预测它会打印出什么。你可能会看到初始的几行`0, 0`。然后你可能会看到类似`N, N`或`N, N + 1`的行。你可能会看到类似`N + 1, N`的行。在理论上，你甚至可能看到`0, 0`的行持续存在¹。

> ¹ 在实践中，`println`语句的存在会导致意外的同步和内存缓存刷新。这可能会掩盖某些导致上述行为的副作用。

那么我们该如何解释这一点呢？

## 赋值的重排序

产生意外结果的一种可能解释是 JIT 编译器改变了`doIT()`方法中赋值的顺序。JLS 要求从当前线程的角度来看，语句的执行似乎是顺序执行的。在这种情况下，`doit()`方法代码中的任何内容都无法观察到那（假设的）两个语句重排序的影响。这意味着 JIT 编译器被允许这样做。

为什么要这样做呢？在典型的现代硬件上，机器指令是通过指令流水线执行的，这允许指令序列处于不同的阶段。指令执行的某些阶段比其他阶段耗时更长，内存操作往往需要更长时间。智能的编译器可以通过对指令进行排序以最大化重叠量，从而优化整个流水线。这可能导致语句的部分无序执行。只要这不从当前线程的角度影响计算结果，JLS 是允许的。

## 内存缓存的影响

另一种可能的解释是内存缓存的影响。在经典的计算机架构中，每个处理器都有一小组寄存器和较大的内存。访问寄存器的速度远快于访问主内存。在现代架构中，存在比寄存器慢但比主内存快的内存缓存。

编译程序会通过尝试将变量的副本保留在寄存器或内存缓存中来利用这一点。如果一个变量不需要刷新到主内存，或者不需要从内存中读取，那么不执行这些操作将带来巨大的性能收益。在 JLS 不要求内存操作对另一个线程可见的情况下，Java JIT 编译器可能不会添加强制主内存读写的"读屏障"和"写屏障"指令。再次，这样做的性能收益是巨大的。

## 正确的同步

到目前为止，我们已经看到 JLS 允许 JIT 编译器通过重排序或避免内存操作来生成使单线程代码快速的代码。当其他线程观察主内存中（共享）变量的状态时，会发生什么？

答案是，其他线程可能会观察到基于 Java 语句代码顺序看起来不可能的变量状态。解决方案是使用适当的同步。三种主要方法是：

- 使用原始互斥锁和`synchronized`结构。
- 使用更高级的并发支持；例如`java.util.concurrent`包中的类。但即使如此，理解在何时需要同步以及你可以依赖哪些效果也是至关重要的。这正是 Java 内存模型派上用场的地方。

## 内存模型

Java 内存模型是 JLS 的一部分，它规定了一个线程保证看到另一个线程所做的内存写入影响的条件。内存模型具有相当的正式严谨性，（由于这个）需要详细且仔细的阅读才能理解。但基本原理是，某些构造在一个线程对变量的写入和另一个线程对该变量的后续读取之间创建了"发生之前"（happens-before）的关系。如果存在"发生之前"的关系，JIT 编译器就有义务生成代码，以确保读取操作能看到写入操作写入的值。

有了这一点，就可以对 Java 程序中的内存一致性进行推理，并决定这在所有执行平台上是否是可预测且一致的。

## 第 147.2 节：发生之前的关系

（以下是 Java 语言规范所言内容的简化版本。为了更深入的理解，你需要阅读规范本身。）

"发生之前"的关系是内存模型的一部分，允许我们理解和推理内存可见性。正如 JLS 所言（JLS 17.4.5）：

> "两个动作可以由'发生之前'的关系进行排序。如果一个动作发生在另一个动作之前"

这意味着什么？

### 动作

上述引用所述的动作在 JLS 17.4.2 中规定。有 5 类定义的动作：

- 读取非`volatile`变量。
- 写入非`volatile`变量。
- 同步动作：
  - `volatile`读取：读取`volatile`变量。
  - `volatile`写入：写入`volatile`变量。
  - 锁。锁定监视器。
  - 解锁监视器。
- 线程的（合成）第一个和最后一个动作。
- 启动线程或检测到线程终止的动作。
- 外部动作。其结果取决于程序运行的环境。
- 线程发散动作。这些建模了某些无限循环的行为。

## 程序顺序与同步顺序

这两种排序（JLS 17.4.3 和 17.4.4）规范了语句的执行。

程序顺序描述了单线程内的语句执行顺序。同步顺序描述了通过同步连接的语句的执行顺序：

- 监视器的解锁动作与后续锁定动作同步。
- 对`volatile`变量的写入与任何线程的后续读取同步。
- 启动线程的动作（例如`Thread.start()`）与它启动的线程的第一个动作（例如调用线程的`run()`方法）同步。
- 字段的默认初始化与每个线程的第一个动作同步。
- 线程的最终动作与任何检测终止的线程同步：例如`join()`调用返回或`isTerminated()`返回`true`。
- 如果一个线程中断另一个线程，第一个线程中的中断调用与另一个线程检测到中断的点同步。

## 发生之前排序

这种排序（JLS 17.4.5）决定了内存写入是否保证对随后的内存读取可见。

具体来说，当且仅当`write(v)`发生于`read(v)`之前，且没有中间写入`v`时，对`v`的读取保证观察到对`v`的写入。如果存在中间写入，则`read(v)`可能会看到之后的结果而不是之前的那个。

定义发生之前排序的规则如下：

**发生之前规则 #1** - 如果`x`和`y`是同一线程的动作，且`x`在程序顺序上早于`y`，则`x`发生于`y`。

**发生之前规则 #2** - 从构造函数的结束到该对象的终结器开始存在一个发生之前的边。

**发生之前规则 #3** - 如果一个动作`x`与随后的动作`y`同步，则`x`发生于`y`。

**发生之前规则 #4** - 如果`x`发生于`y`且`y`发生于`z`，则`x`发生于`z`。

那么`x`发生于`z`之前（happens-before）。

此外，Java 标准库中的各种类都被规定了"发生在前"（happens-before）关系。你可以将其解释为：它以某种方式发生了，而无需确切知道该保证是如何具体实现的。

## 第 147.3 节：如何避免理解内存模型

内存模型（Memory Model）难以理解，也难以应用。如果你需要对多线程代码的正确性进行推理，它是很有用的，但你不想为你编写的每一个多线程应用程序都进行这种推理。

如果你在编写 Java 并发代码时遵循以下原则，你可以在很大程度上避免诉诸"发生在前"的推理。

- 尽可能使用不可变数据结构。实现良好的不可变类是线程安全的，并且当你将其与其他类一起使用时，不会引入线程安全问题。
- 理解并避免"不安全发布"（unsafe publication）。使用原始互斥锁（mutexes）或`Lock`对象来同步对需要线程安全的可变对象的状态访问。
- 使用`Executor / ExecutorService`或 fork join 框架，而不是尝试直接管理线程。
- 使用`java.util.concurrent`提供的高级锁、信号量、计数器（latches）和屏障（barriers），而不是直接使用`wait/notifyAll`。
- 使用`java.util.concurrent`版本的`map`、`set`、`list`、`queue`和`deque`，而不是对非并发集合进行外部同步。
- 通用原则是使用 Java 内置的并发库，而不是"自己实现"并发。如果你使用得当，可以依靠它们正常工作。
- 并不是所有对象都需要线程安全。例如，如果一个对象或多个对象是线程限制的（thread-confined，即只对一个线程可见），那么它的线程安全性就不重要。

## 第 147.4 节：应用于某些示例的"发生在前"推理

我们将展示一些示例，说明如何应用"发生在前"推理来检查写操作是否对后续读取可见。

### 单线程代码

正如你所预期的，在单线程程序中，写操作总是对后续读取可见的。

```java
public class SingleThreadExample {
    public int a, b;

    public int add() {
        a = 1; // write(a)
        b = 2; // write(b)
        return a + b; // read(a) followed by read(b)
    }
}
```

根据"发生在前"规则 #1：

1. `write(a)`动作发生于`write(b)`动作之前。
2. `write(b)`动作发生于`read(a)`动作之前。
3. `read(a)`动作发生于`read(b)`动作之前。

根据"发生在前"规则 #4：

4. `write(a)`发生于`write(b)`且`write(b)`发生于`read(a)`之前，意味着`write(a)`发生于`read(a)`之前。
5. `write(b)`发生于`read(a)`之前且`read(a)`发生于`read(b)`之前，意味着`write(b)`发生于`read(b)`之前。

总结：

6. `write(a)`发生于`read(a)`的关系意味着`a + b`语句保证能看到`a`的正确值。
7. `write(b)`发生于`read(b)`的关系意味着`a + b`语句保证能看到`b`的正确值。

### 2 线程示例中 'volatile' 的行为

我们将使用以下示例代码来探索`volatile`的某些含义。

### `volatile` 的内存模型

```java
public class VolatileExample {
    private volatile int a;
    private int b; // NOT volatile

    public void update(int first, int second) {
        b = first; // write(b)
        a = second; // write-volatile(a)
    }

    public int observe() {
        return a + b; // read-volatile(a) followed by read(b)
    }
}
```

首先，考虑以下涉及 2 个线程的语句序列：

1. 创建了`VolatileExample`的单实例；称之为`ve`。
2. 在一个线程中调用了`ve.update(1,2)`。
3. 在另一个线程中调用了`ve.observe()`。

根据"发生在前"规则 #1：

1. `write(b)`动作发生于`volatile-write(a)`动作之前。
2. `volatile-read(a)`动作发生于`read(b)`动作之前。

根据"发生在前"规则 #3：

3. 第一个线程中的`volatile-write(a)`动作发生于第二个线程中的`volatile-read(a)`动作之前。

根据"发生在前"规则 #4：

4. 第一个线程中的`write(b)`动作发生于第二个线程中的`read(b)`动作之前。

换句话说，对于这个特定的序列，我们保证第 2 个线程会看到第一个线程对非`volatile`变量`b`的更新。然而，也应该清楚，如果`update`方法中的赋值顺序是反的，或者`observe()`方法在读取`a`之前读取了变量`b`，那么"发生在前"的链就会中断。如果第二个线程中的`volatile-read(a)`不是第一个线程中`volatile-write(a)`的后续操作，该链也会中断。

当链中断时，无法保证`observe()`会看到`b`的正确值。

### 三线程下的 Volatile

假设我们在上一个示例中加入第三个线程：

1. 创建`VolatileExample`的单实例；称之为`ve`。
2. 在一个线程中调用了`ve.update(1,2)`。
3. 在另一个线程中调用了`ve.observe()`。

为了完全分析这一点，我们需要考虑所有可能的交织情况。正如我们所看到的，如果操作顺序不符合规则，可见性就会消失。

这种复杂性在线程增加时会变得更加难以处理。这就是为什么我们需要内存模型来指导。

# 创建 UberJAR

创建 UberJAR 的步骤非常简单。（为了简单起见，我将使用 Linux 命令。这些命令在 Mac OS 上是相同的，在 Windows 上类似。）

1. 创建一个临时目录并进入该目录。

```bash
$ mkdir tempDir; cd tempDir
```

2. 针对每个依赖 JAR 文件，按照它们在应用程序类路径上所需的**反向顺序**，使用`jar`命令将 JAR 解压到临时目录。

```bash
$ jar -xf <path/to/file.jar>
```

对多个 JAR 文件执行此操作将使 JAR 的内容相互覆盖。

3. 将构建树中的应用程序类复制到临时目录：

```bash
$ cp -r path/to/classes .
```

4. 从临时目录的内容创建 UberJAR：

```bash
$ jar -cf ../myApplication.jar .
```



如果你正在创建一个可执行的 JAR 文件，请如描述所示包含一个适当的 `MANIFEST.MF`。

## 使用 Maven 创建 UberJAR

如果你的项目是使用 Maven 构建的，可以使用 `maven-assembly` 或 `maven-shade` 插件来创建 UberJAR。详情请参阅 Maven 文档中的 Maven Assembly 主题。

## UberJAR 的优缺点

UberJAR 的优点是显而易见的：

UberJAR 易于分发。由于库是自包含的，你不会破坏 UberJAR 的库依赖关系。

此外，如果你使用适当的工具创建 UberJAR，你还可以选择排除 JAR 文件未使用的库类。然而，这通常是通过对类进行静态分析实现的。如果你的应用程序使用了反射、注解处理和类似技术，你需要小心某些类被错误地排除。

UberJAR 也有一些缺点：

如果你有许多具有相同依赖的 UberJAR，那么每一个都将包含一份依赖的副本。

某些开源库的许可证可能会阻止它们在 UberJAR 中使用。

- 某些开源库许可证允许仅在终端用户能够替换该库的 Maven 版本时才使用该库。UberJAR 会使版本依赖替换变得困难。

## 第 148.3 节：创建 JAR、WAR 和 EAR 文件

JAR、WAR 和 EAR 文件类型本质上是 ZIP 文件，包含一个“清单”文件和（对于 WAR 和 EAR 文件）特定的内部目录/文件结构。

创建这些文件的推荐方法是使用特定的 Java 构建工具，该工具“理解”相应文件类型的要求。如果你不使用构建工具，那么“导出”是下一个尝试选项。（编辑注：关于如何创建这些文件的描述最好放在相应工具的文档中。请将它们放在那里。请表现出克制，**不要**把它们硬塞进这里！）

## 使用 Maven 创建 JAR 和 WAR

使用 Maven 创建 JAR 或 WAR 只需要在 POM 文件中放入正确的 `<packaging>` 元素；例如：

```xml
<packaging>jar</packaging>
```

或者

```xml
<packaging>war</packaging>
```

有关更多细节，Maven 可以通过作为插件属性添加有关入口类和外部依赖的必要信息，配置为创建“可执行”JAR 文件。甚至有一个插件用于创建将应用程序及其依赖合并到单个 JAR 文件中的“uberJAR”文件。请参阅 Maven 文档 (http://stackoverflow.com/documentation/maven/topics) 获取信息。

## 使用 Ant 创建 JAR、WAR 和 EAR 文件

Ant 工具具有用于构建 JAR、WAR 和 EAR 的独立“任务”。请参阅 Ant 文档 (http://stackoverflow.com/documentation/ant/topics) 获取信息。

## 使用 IDE 创建 JAR、WAR 和 EAR 文件

三个流行的 Java IDE 都内置了创建部署文件的支持。该功能通常被称为“导出”：

- Eclipse - http://stackoverflow.com/documentation/eclipse/topics
- NetBeans - http://stackoverflow.com/documentation/netbeans/topics
- IntelliJ - http://stackoverflow.com/documentation/intellij/topics

## 使用 jar 命令创建 JAR、WAR 和 EAR 文件

也可以使用 `jar` 命令“手动”创建这些文件。这只需要在正确的位置放置正确的文件组装文件树，创建一个清单文件并运行 `jar` 来创建 JAR 文件。请参阅 jar 命令（创建和修改 JAR 文件）获取信息。

## 第 148.4 节：Java Web Start 简介

Java 教程对 Web Start 的总结如下：

Java Web Start 提供了一键启动全功能应用程序的能力。用户可以下载并启动应用程序（例如完整的电子表格或网络客户端），而无需经过漫长的安装过程。

Java Web Start 的其他优点包括支持签名代码和显式声明平台依赖，以及支持代码缓存和应用程序更新部署。Web Start 也称为 JAWS。主要信息来源有：

- Java 教程 - 课程：Java Web Start
- Java Web Start 指南
- JNLP 规范
- `javax.nlp` API
- Java Web Start 网站

## 前提条件

从高级来说，Web Start 通过从远程 Web 服务器分发封装为 JAR 文件的 Java 应用程序来工作。前提是：

运行应用程序的目标机器上已安装 Java（JRE 或 JDK）。需要 Java 1.2 或更高版本：从 Java 5.0 开始，Web Start 包含在 JRE / JDK 中。对于早期版本，Web Start 是单独安装的。

Web Start 基础设施包括一些包含在网页中的 JavaScript，用于帮助用户安装必要的软件。托管软件的 Web 服务器必须目标机器可以访问。如果用户通过网页中的链接启动 Web Start 应用程序，那么：

他们需要一个兼容的浏览器，对于现代（安全的）浏览器，需要告诉他们如何让浏览器允许在不损害网络安全的情况下运行 Java。

## 一个 JNLP 文件示例

以下示例旨在说明 JNLP 的基本功能。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jnlp spec="1.0+" codebase="https://www.example.com/demo" href="demo_webstart.jnlp">
```

```xml
<information>
<title>Demo</title>
<vendor>The Example.com Team</vendor>
</information>
<resources>
<!-- Application Resources -->
<j2se version="1.7+" href="http://java.sun.com/products/autodl/j2se"/>
<j2se href="Demo.jar" main="true"/>
</resources>
<application-desc
name="Demo Application"
main-class="com.example.jwsdemo.Main"
width="300"
height="300">
<|application-desc|>
<update />
</jnlp>
```

如你所见，JNLP 文件是基于 XML 的，所有信息都包含在 `<jnlp>` 元素中。

`spec` 属性给出该文件遵循的 JNLP 规范版本。`codebase` 属性给出文件中其他相对 href URL 的基 URL。`href` 属性给出该 JNLP 文件的确定 URL。

`<information>` 元素包含应用程序的元数据，包括标题、作者、描述和帮助网站。

`<resources>` 元素描述应用程序的依赖项，包括所需的 Java 版本、操作系统和 JAR 文件。`<application-desc>`（或 `<applet-desc>`）元素提供了启动应用程序所需的信息。

## 设置 Web 服务器

Web 服务器必须配置为对 `.jnlp` 文件使用 `application/x-java-jnlp-file` 作为 MIME 类型。

JNLP 文件和应用程序的 JAR 文件必须安装在 Web 服务器上，以便可以通过 JNLP 文件指示的 URL 访问。

## 通过网页启用启动

如果通过网页链接启动应用程序，则包含链接的页面必须在 Web 服务器上创建。

如果你可以假设用户机器上已经安装了 Java Web Start，网页只需要包含一个启动应用程序的链接。例如：

```html
<a href="https://www.example.com/demo_webstart.jnlp">启动应用程序</a>
```

否则，页面还应该包含一些脚本来检测用户正在使用的浏览器并请求下载并安装所需的 Java 版本。
注意：鼓励用户通过这种方式安装 Java 是一个坏主意，甚至让他们在 Web 浏览器中启用 Java 以便启动 JNLP 网页将。

# 从命令行启动 Web Start

从命令行启动 Web Start 程序的说明非常简单。假设用户已安装了 Java 5.0 JRE 或 JDK，只需运行：
`$ javaws <url>` 其中 `<url>` 是远程服务器上 JNLP 文件的 URL。

# 第 149 章：Java 插件系统实现

## 第 149.1 节：使用 URLClassLoader

有多种方法可以为 Java 应用实现插件系统。
最简单的方法之一是使用 `URLClassLoader`。下面的示例将涉及一些 JavaFX 代码。
假设我们有一个主应用程序的模块。该模块应该以 `plugins` 文件夹的形式加载插件。初始代码：

```java
public class MainApplication extends Application {
@Override
public void start(Stage primaryStage) throws Exception {
File pluginDirectory=new File("plugins"); //任意目录
if(!pluginDirectory.exists()){pluginDirectory.mkdir();
VBox loadedPlugins=new VBox(6); //用于显示视觉信息的容器
later Rectangle2D scenebounds=Screen.getPrimary().getVisualBounds();
Scene scene=new
Scene(loadedPlugins,scenebounds.getWidth()/2,scenebounds.getHeight()/2)
primaryStage.setScene(scene);
}
public static void main(String[] a) {
{
launch(a); 
}
}
```

然后，我们创建一个一个表示插件的接口。
`package main;`

```java
public interface Plugin {
default void initialize() {
System.out.println("Initialized"+this.getClass().getName()); }
default String name() { return getClass().getSimpleName(); }
}
```

我们想要加载实现此接口的类，因此首先我们需要过滤出具有 `.jar` 扩展的文件：
`File[] files=pluginDirectory.listFiles((dir, name)->endsWith(".jar"));`
如果有任何文件，我们需要创建 URL 集合和类名：

```java
if(files!=null && files.length>0) {
ArrayList<String> classes=new ArrayList<String>(); ArrayList<URL> urls=new
ArrayList<URL>(files.length); for(File file:files) {
JarFile jar=new JarFile(file);
jar.stream().forEach(jarEntry -> {
if(jarEntry.getName()).endsWith(".class") {
classes.add(jarEntry.getName());
}
});
URL url=file.toURI().toURL();
urls.add(url);
}
```

让我们在 `MainApplication` 中添加一个静态 `HashSet` 来存储已加载的插件：
`static HashSet<Plugin> plugins=new HashSet<>();`
接下来，我们实例化一个 `URLClassLoader`，并遍历类名，实例化实现 `Plugin` 接口的类：

```java
URLClassLoader urlClassLoader=new URLClassLoader(urls.toArray(new
URL[urls.size()])); classes.forEach(className->{
{
Class
cls=urlClassLoader.loadClass(className.replaceAll("/","\\.\.")).replace(".class","")
//转换为二进制名
Class[] interfaces=cls.getInterfaces();
for(Class intace:interfaces)
if(intace.equals(Plugin.class)) //检查 Plugin 接口是否存在 {
plugin=(Plugin) cls.newInstance(); // 实例化 Plugin
plugins.add(plugin);
break;
}
}
catch (Exception e){e.printStackTrace();}
});
```

然后，我们可以调用插件的方法，例如初始化它们：

```java
if (plugins.isEmpty())loadedPlugins.getChildren().add(new Label("Loaded
plugins:"));\ plugins.forEach(plugin -> {
plugin.initialize();
loadedPlugins.getChildren().add(new Label(plugin.name()));));
```

`MainApplication` 的最终代码：

```java
package main;
public class MainApplication extends Application {
static HashSet<Plugin> plugins=new HashSet<>(); @Override
public void start(Stage primaryStage) throws Exception {
File pluginDirectory=new File("plugins");
if(pluginDirectory.exists())pluginDirectory.mkdir(); File[]
files=pluginDirectory.listFiles((dir, name) -> name.endsWith(".jar")); VBox
loadedPlugins=new VBox(6);
loadedPlugins.setAlignment(Pos.CENTER);
if(files!=null && files.length>0
{
ArrayList<String> classes=new ArrayList<>(); ArrayList<URL> urls=new ArrayList<URL>(files.length); for (File file : files)
{
JarFile file=new JarFile(file);
jar.stream().forEach(jarEntry -> {
if(jarEntry.getName().endsWith(".class"))
{
classes.add(jarEntry.getName());
}
});
URL url=file.toURI().toURL();
urls.add(url);
}
ClassLoader urlLoader=new URLClassLoader(urls.toArray(new URL[urls.size()])); classes.forEach(className -> {
try
{
Class
cls=ClassLoader.loadClass(className.replaceAll("/", ".")).replace(".class", ""),
Class[][] interfaces=cls.getInterfaces();
for(Class intface:interfaces)
if(intface.equals(Plugin.class)) {
Plugin plugin=(Plugin) cls.newInstance();
plugins.add(plugin);
break;
}
}\}
}
catch (Exception e){e.printStackTrace();
};
if(plugins.isEmpty()){loadedPlugins.getChildren().add(new Label("Loaded plugins:"));}; plugins.forEach(plugin -> {
plugin.initialize();
loadedPlugins.getChildren().add(new Label(plugin.name()));
};
}
Rectangle2D screenbounds=Screen.getPrimary().getVisualBounds();
Scene scene=new
Scene(loadedPlugins,screenbounds.getWidth()/2,screenbounds.getHeight()/2)
primaryStage.setScene(scene);
primaryStage.show();
}
public static void main(String[] a) {
launch(a); 
}
}
```



让我们创建两个插件。显然，插件的源码应该在一个独立的模块中。

```java
package plugins;

import main.Plugin;

public class FirstPlugin implements Plugin {

    //此插件具有默认行为
}
```

第二个插件：

```java
package plugins;

import main.Plugin;

public class AnotherPlugin implements Plugin {

    @Override
    public void initialize() {
        //重写以显示用户主目录
        System.out.println("User home directory: " + System.getProperty("user.home"));
    }
}
```

这些插件必须打包成标准的 JAR。

只要编译器可以从上下文中推断出类型参数，调用带有空类型参数集（`<>`）的泛型类构造函数所需的参数。这对角括号在非正式地被称为“菱形”。在带有变长参数（Varargs）方法中使用非可重写化（Non-Reifiable）形式参数时，改进了编译器警告和错误。

## 第 151.2 节：二进制字面量

```java
// 一个 8 位的 'byte' 值：
byte aByte = (byte)0b00100001;
// 一个 16 位的 'short' 值：
short aShort = (short)0b0101000010101001;
// 一些 32 位的 'int' 值：
int anInt1 = 0b01010000101010001010100010101001;
int anInt2 = 0b0101;
int anInt3 = 0b0101; // B可以是大写或小写。
```

```java
// 一个 64 位的 'long' 值。注意 "L" 后缀：
long aLong = 0b010100001010100010101000101010001010100010101000101010001010L;
```

## 第 151.3 节：try-with-resources 语句

该示例从文件中读取第一行。它使用 `BufferedReader` 实例来从文件中读取数据。在程序结束时，必须关闭 `BufferedReader`：

```java
static String readFirstLineFromFile(String path) throws IOException {
    try (BufferedReader br = new BufferedReader(new FileReader(path))) {
        return br.readLine();
    }
}
```

在此示例中，try-with-resources 语句中声明的资源是 `BufferedReader`。声明语句紧跟在 `try` 关键字后的括号内。在 Java SE 7 及更高版本中，`BufferedReader` 类实现了 `java.lang.AutoCloseable` 接口。因为 `BufferedReader` 实例是在 try-with-resources 语句中声明的，无论 `try` 语句是正常完成还是异常终止（由于方法 `BufferedReader.readLine()` 抛出 `IOException`），它都将被关闭。

## 第 151.4 节：数字字面量中的下划线

以下示例展示了在数字字面量中使用下划线的方法：

```java
long creditCardNumber = 1234_5678_9012_3456L;
long socialSecurityNumber = 99_99_9999L;
float pi = 3.14_15;
long hexBytes = 0xFF_EC_DE;
long hexWords = 0xCAFE_BABE;
long maxLong = 0x7fff_ffffL;
byte bytes = 0b0010_0101;
long bytes2 = 0b0110_1001L;
```

你只能将下划线放在数字之间；你不能在以下位置放置下划线：
- 在数字的开头或结尾
- 在浮点数字面量中紧邻小数点
- 在 F 或 L 后缀之前
- 在期望数字字符串的位置

## 第 151.5 节：实例创建的类型推断

你可以使用 `Map<String, List<String>> myMap = new HashMap<>();` 代替 `Map<String, List<String>> myMap = new HashMap();`

然而，你不能这样写：

```java
List<String> list = new ArrayList<>();
list.addAll("A"); // 下述语句应该失败，因为 addAll 期望 `Collection<? extends String>`，无法编译。
```

注意，菱形在方法调用中通常有效；但建议你将菱形主要用于变量声明。

## 第 151.6 节：switch 中的字符串

```java
public String getTypeOfWithSwitch(String dayOfWeekArg) {
    String typeOfDay;
    switch (dayOfWeekArg) {
        case "Monday":
            typeOfDay = "Start of week";
            break;
        case "Tuesday":
        case "Wednesday":
        case "Thursday":
            typeOfDay = "Midweek";
            break;
        case "Friday":
            typeOfDay = "End of week";
            break;
        case "Saturday":
        case "Sunday":
            typeOfDay = "Weekend";
            break;
        default:
            throw new IllegalArgumentException("Invalid day of the week: " + dayOfWeekArg);
    }
    return typeOfDay;
}
```

## 第 152 章：Java SE 8 特性

在本主题中，你将找到 SE 8 添加到 Java 编程语言的新特性总结。在其他领域（如 JDBC 和 Java 虚拟机 JVM）还有许多其他新特性，本主题未涵盖。

### 第 152.1 节：新的 Java 8 编程语言特性

- **Lambda 表达式**：一种新的语言特性，在此发行版中引入。它们允许你将功能作为方法的参数，或将代码作为数据。Lambda 表达式让你能够更简洁地表达单方法接口（称为函数式接口）的实例。
- **方法引用**：为已有名称的方法提供易于读的 lambda 表达式。
- **默认方法**：允许向库的接口中添加新功能，并确保与为旧版本编写的代码保持二进制兼容。
- **利用 Lambda 表达式和流的新型及增强 API**：Java 8 描述了利用 lambda 表达式和流的新型及增强类。
- **改进的类型推断**：Java 编译器利用目标类型来推断泛型方法调用的类型参数。表达式的目标类型取决于该表达式出现的位置，Java 调用所预期的数据类型。例如，在 Java 7 中，你可以使用赋值语句的目标类型进行类型推断。但在 Java 8 中，你可以在更多上下文中使用目标类型进行类型推断。

#### Lambda 表达式中的目标类型

- **重复注解**：提供了对同一个声明或用例多次应用同一种类型注解的能力。
- **类型注解**：提供了在任何使用类型的地方应用注解的能力，而不仅仅是在声明上。与可插的类型系统配合使用，此功能改进了你代码的类型检查。
- **方法参数反射**：你可以通过 `java.lang.reflect.Executable.getParameters()` 方法获取任何方法或构造器的形式参数。`Method` 和 `Constructor` 类继承了 `Executable` 类，因此继承了 `getParameters()`。然而，`.class` 文件默认不存储形式参数名称。要在特定的 `.class` 文件中存储形式参数名称，从而允许反射 API 获取形式参数名称，请使用 `javac` 编译器的 `-parameters` 选项编译源文件。
- **日期-时间 API**：在 `java.time` 中添加了新的时间 API。如果使用它，你不需要指定时区。

## 第 153 章：动态方法分发

### 什么是动态方法分发？

动态方法分发是在运行时而非编译时解析对覆盖方法调用的过程。当通过引用调用覆盖方法时，Java 根据其所引用的对象类型决定执行该方法的哪个版本。这被称为运行时多态。

我们将通过一个示例来看这一点。

### 第 153.1 节：动态方法分发 - 示例代码

抽象类：

```java
package base;

/*
抽象类不能被实例化，但可以被子类化 */
public abstract class ClsVirusScanner {

    // 有一个抽象方法
    public abstract void fnStartScan();

    protected void fnCheckForUpdateVersion() {
        System.out.println("Perform Virus Scanner Version Check");
    }

    protected void fnBootTimeScan() {
        System.out.println("Perform BootTime Scan");
    }

    protected void fnInternetSecurity() {
        System.out.println("Scan for Internet Security");
    }

    protected void fnRealTimeScan() {
        System.out.println("Perform RealTime Scan");
    }

    protected void fnVirusMalwareScan() {
        System.out.println("Detect Virus & Malware");
    }
}
```

子类中覆盖抽象方法：

```java
import base.ClsVirusScanner;

// 所有三个子类都继承基类 ClsVirusScanner
// 子类 1
class ClsPaidVersion extends ClsVirusScanner {
    @Override
    public void fnStartScan() {
        super.fnCheckForUpdateVersion();
        super.fnBootTimeScan();
        super.fnInternetSecurity();
        super.fnRealTimeScan();
        super.fnVirusMalwareScan();
    }
}

// ClsPaidVersion IS-A ClsVirusScanner
// 子类 2
class ClsTrialVersion extends ClsVirusScanner {
    @Override
    public void fnStartScan() {
        super.fnInternetSecurity();
        super.fnVirusMalwareScan();
    }
}

// ClsTrialVersion IS-A ClsVirusScanner
// 子类 3
class ClsFreeVersion extends ClsVirusScanner {
    @Override
    public void fnStartScan() {
        super.fnVirusMalwareScan();
    }
}

// ClsFreeVersion IS-A ClsVirusScanner
```

动态/后期绑定导致动态方法分发：

```java
// 调用类
public class ClsRunTheApplication {
    public static void main(String[] args) {
        final String VIRUS_SCANNER_VERSION = "TRIAL_VERSION";

        // 父类引用为空
        ClsVirusScanner objVS = null;

        // Java SE 7 switch 支持的字符串情况
        switch (VIRUS_SCANNER_VERSION) {
            case "FREE_VERSION":
                // 父类引用子对象 3
                // ClsFreeVersion 属于 ClsVirusScanner
                objVS = new ClsFreeVersion(); // 动态或运行时绑定
                break;
            case "PAID_VERSION":
                // 父类引用子对象 1
                // ClsPaidVersion 属于 ClsVirusScanner
                objVS = new ClsPaidVersion(); // 动态或运行时绑定
                break;
            case "TRIAL_VERSION":
                // 父类引用子对象 2
                objVS = new ClsTrialVersion(); // 动态或运行时绑定
                break;
        }
        // 方法 fnStartScan() 是 ClsTrialVersion() 的实现
        objVS.fnStartScan();
    }
}
```

结果：扫描互联网安全以检测病毒和恶意软件

向上转型：

## 第 154 章：生成 Java 代码

### 第 154.1 节：从 JSON 生成 POJO

在 IntelliJ 设置中搜索并安装 JSON Model Generator 插件。

从“Tools”菜单启动插件。

按照所示输入 UI 字段（`Path`、`Source`、`Package` 是必须的）：

![](img/01cc8d6667542262308c820b3f5bd37b_1145_0.png)

点击“Generate”按钮即可完成。

## 第 155 章：JShell

JShell 是 JDK 9 的 Java 交互式 REPL（读取-执行打印循环）。它允许开发者即时评估表达式、测试类并对 Java 语言进行实验。可以通过以下地址获取 JDK 9 的早期访问：http://jdk.java.net/9/

### 第 155.1 节：编辑片段 (Snippets)

JShell 使用的基本单元是片段或源条目。每当你声明本地变量或定义本地方法或类时，你都会创建一个片段，其名称为变量/方法/类的标识符。在任何时候，你都可以使用 `/edit` 命令编辑已创建的片段。例如，假设我创建了一个带有方法 `bar` 的类 `Foo`：

```js
jshell > class Foo {
...> void bar() {
...>
>}
```

现在，我想填充我的方法体。与其重写整个类，我可以直接编辑它：

```js
jshell> /edit Foo
```

默认情况下，会弹出一个具有最基本功能的 Swing 编辑器。

不过，你可以更改 JShell 使用的编辑器：

```js
jshell > /set editor emacs
jshell > /set editor vi
jshell > /set editor nano
jshell > /set editor -default
```

请注意，如果新版本的片段包含任何语法错误，则可能无法保存。同样，只有当原始声明/定义在语法上是正确的，片段才会被创建；以下操作不起作用：

```js
jshell > String st = String // 省略错误
jshell > /edit st
不存在这样的片段: st
```

然而，片段是可以编译的，因此尽管存在编译时错误（例如类型不匹配），仍然可以编辑——以下操作是有效的：

```js
jshell > int i = "hello" // 省略错误
jshell > /edit i
```

最后，可以使用 `/drop` 命令删除片段：

```js
jshell > int i = 13
jshell > /drop
jshell > System.println(i) // 错误：找不到符号：变量 i
```

要删除所有片段并重置 JVM 状态，请使用 `/reset`：

```js
jshell > int i = "hi"
jshell > /reset
正在重置状态。
jshell > i // 错误：找不到符号：变量 i
jshell > s // 错误：找不到符号：变量 s
```

### 第 155.2 节：进入和退出 JShell

#### 启动 JShell

在尝试启动 JShell 之前，确保你的 `JAVA_HOME` 变量指向 JDK 9 安装目录。要启动 JShell，请运行以下命令：

```bash
$ jshell
```

如果一切顺利，你应该能看到 `jshell>` 提示符。

#### 退出 JShell

要退出 JShell，请从 JShell 提示符运行以下命令：

```js
jshell> /exit
```

### 第 155.3 节：表达式



在 JShell 中，你可以评估 Java 表达式，无论是否带有分号。这些可以从基础表达式和语句扩展到复杂的表达式：

```
jshell > i = 4
jshell > System.printf("%d years old.\n", i)
```

循环和条件判断也可以用：

```
jshell > for (int i = 0; i<3; i++) {
...> System.println(i);
}
```

重要的是，块内的表达式必须带有分号！

### 第 155.4 节：方法和类

你可以在 JShell 中定义方法和类。不需要访问修饰符。与其他代码块一样，方法体内部需要分号。请记住，对于变量，可以重新定义方法和类。要查看方法或类的列表，请分别在 JShell 提示符处输入 `/methods` 或 `/types`。

```
jshell > void speak() {
...> System.println("hello");
>}

jshell > class MyClass {
...> void doNothing() {}
>}
```

### 第 155.5 节：变量

你可以在 JShell 中声明本地变量。请记住，变量可以使用不同的类型重新声明；以下操作是有效的：

```
jshell > String s = "hi"
jshell > int s = 3
```

要查看变量列表，在 JShell 提示符处输入 `/vars`。

# 第 156 章：栈步行 API (Stack-Walking)

在 Java 9 之前，对栈帧的访问限于内部类。Java 9 通过 `java.lang.StackWalker` 类提供了一种替代 API，它通过允许惰性访问栈帧来设计得高效。

### 第 56.1 节：打印当前线程的所有栈帧

以下代码打印当前线程的所有栈帧：

```java
package test;

import java.lang.StackWalker.StackFrame;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.util.List;
import java.util.stream.Collectors;

public class StackWalkerExample {
    public static void main(String[] args) throws NoSuchMethodException,
    SecurityException, IllegalAccessException,
    InvocationTargetException {
        Method fooMethod = FooHelper.class.getDeclaredMethod("foo");
        fooMethod.invoke(null, new Object[]{null});
    }
}

class FooHelper {
    protected static void foo() {
        BarHelper.bar();
    }
}

class BarHelper {
    protected static void bar() {
        List<StackFrame> stack = StackWalker.getInstance()
        .walk((s) -> s.collect(Collectors.toList()));
        for (StackFrame frame : stack) {
            System.out.println(frame.getClassName() + " " + frame.getLineNumber() + " " + frame.getMethodName());
        }
    }
}
```

结果：

```
test.BarHelper 26 bar
test.FooHelper 19 foo
test.StackWalkerExample 13
```

### 第 56.2 节：打印调用者类

以下代码打印调用者类。请注意，在这种情况下，`StackWalker` 需要使用 `RETAIN_CLASS_REFERENCE` 选项创建，以便将 `Class` 实例保留在 `StackFrame` 对象中。否则会发生异常。

```java
public class StackWalkerExample {
    public static void main(String[] args) {
        FooHelper.foo();
    }
}
class FooHelper {
    protected static void foo() {
        BarHelper.bar();
    }
}
class BarHelper {
    protected static void bar() {
        System.out.println(StackWalker.getInstance(Option.RETAIN_CLASS_REFERENCE));
    }
}
```

输出：

```
class test.FooHelper
```

### 第 56.3 节：显示反射和其他隐藏帧

其他几个选项允许栈跟踪包含实现和/或反射帧。这对于调试目的可能有用。例如，我们可以在创建 `StackWalker` 实例时添加 `SHOW_REFLECT_FRAMES` 选项，这样反射方法的帧也会被打印出来：

```java
for(StackFrame frame : stack) {
    System.out.println(frame.getClassName() + " " + frame.getLineNumber() + 
    + " " + frame.getMethodName());
}
```

输出：

```
test.BarHelper 27 bar
test.FooHelper.reflect.NativeMethodAccessorImpl -2 invoke
jdk.internal.reflect.NativeMethodAccessorImpl 62.DelegatingMethodAccessorImpl 62 invoke
jdk.internal.reflect.DelegatingMethodAccessorImpl 43 invoke
java.lang.reflect.Method 563 invoke
test.StackWalkerExample 14 main
```

注意，某些反射方法的行号可能不可用，因此 `StackFrame.getLineNumber()` 可能返回负值。

## 第 157 章：套接 (Socks)

套接（Socket）是运行在网络程序之间双向通信链路的一端。

## 第 157.1 节：从套接读取

```java
String hostName = args[0];
portNumber = Integer.parseInt(args[1]);
```

```java
try (
    Socket echoSocket = new Socket(hostName, portNumber);
    PrintWriter out = 
```

```java
    new PrintWriter(echoSocket.getOutputStream(), true);
    BufferedReader in = 
    new BufferedReader(
        new InputStreamReader(echoSocket.getInputStream()));
```

```java
BufferedReader stdin =
    new BufferedReader(
    new InputStreamReader(System.in))
)
{
// 使用套接
}
```

## 第 158 章：Java 套接 (Java Sockets)

套接是一种低级网络接口，有助于在两个程序（主要是客户端）之间建立连接，这些程序可能运行在同一机器上。

套接编程是最广泛使用的网络概念之一。

## 第 158.1 节：一个简单的 TCP 回显服务器

我们的 TCP 回显服务器将是一个独立的线程。它的启动非常简单。

它只会回显你发送它的任何内容，但是大大写形式。

```java
public class CAPECHOServer extends Thread{

// 此类实现了服务器套接字。服务器套接字仅在被本地防火墙允许
// 通过时才在网络上等待请求
ServerSocket serverSocket;
public CAPECHOServer(int port, int timeout){
try {
// 在指定端口创建新服务器。
serverSocket = new ServerSocket(port);
// setTimeout = 基本上就是套接字超时。
// timeout 是套接字超时的毫秒数。
serverSocket.setTimeout(timeout);
} catch (IOException ex) {
Logger.getLogger(CAPECHOServer.class.getName()).log(Level.SEVERE,
null, ex);
}
```

```java
@Override
public void run() {
try {
    // 我们希望服务器持续接受连接
    while(!Thread.interrupted()) {
    }
    // 完成后关闭服务器套接字。
    serverSocket.close();
```

```java
} catch (IOException ex) {
    Logger.getLogger(CAPECHOServer.class.getName()).log(Level.SEVERE, null, ex);
}
```

现在来接受连接。让我们更新 `run` 方法。

```java
@Override
public void run() {
    while(!Thread.interrupted()) {

```

```java
try {
    // 记录端口号和机器 IP 的日志
Logger.getLogger((this.getClass().getName())).log(Level.INFO, "正在在 {1} 监听客户端 {0}", new Object[]{serverSocket.getLocalPort(),

    InetAddress.client.getLocalHost().getHostAddress()});
    Socket client = serverSocket.accept(); // 接受客户端连接
    // 现在获取 DataInputStream 和 DataOutputStreams

```

```java
DataInputStream inputStream = new DataInputStream(client.getInputStream()); //
// 来自客户端的输入流
DataOutputStream ostream = new
DataOutputStream(client.getOutputStream());
```

```java
// 注意事项
服务器的输入是客户端的输出。客户端的输入是服务器的输出
```

```java
/*
// 发送欢迎消息
ostream.writeUTF("Welcome!");
```

```java
// 关闭连接
inputStream.close();
ostream.close();
client.close();
```

```java
} catch (IOException ex) {
  Logger.getLogger(CAPECHOServer.class.getName()).log(Level.SEVERE, null, ex);
}
```

```java
// 完成后关闭服务器套接字
try {
  serverSocket.close();
} catch (IOException ex) {
  Logger.getLogger(CAPECHOServer.class.getName()).log(Level.SEVERE,
  null, ex);
}
```

现在你可以打开 telnet 并尝试连接。你必须使用指定的端口和 IP 地址连接。

你会看到类似的结果：

```
Welcome!
```

连接到 host 丢失。

连接丢失是因为我们终止了它。有时我们需要一个 TCP 客户端向用户请求输入并将其发送到网络，接收大写的输入。

如果服务器先发送数据，客户端必须先读取数据。

```java
public class ECHOClient extends Thread{

  Socket server;

```java
Scanner key; // 用于输入的 Scanner

public ECHOClient(String ip, int port){
  server = new Socket(ip, port);
  key = new Scanner(System.in);
} catch (IOException ex) {
  Logger.getLogger(ECHOClient.class.getName()).log(Level.SEVERE,
  null, ex);
}
@Override
public void run(){
  DataInputStream inputStream = null;
  DataOutputStream ostream = null;
  try {
    inputStream = new DataInputStream(server.getInputStream()); // 熟悉的行
    ostream = new DataOutputStream(server.getOutputStream());
    System.out.println(inputStream.readUTF()); // 打印服务器发送的内容
    System.out.print("> ");
    String toSend = key.nextLine();
    ostream.writeUTF(toSend); // 将用户输入的发送到服务器
    System.out.println(inputStream.readUTF()); // 最后读取服务器发送的内容。
} catch (IOException ex) {
  Logger.getLogger(ECHOClient.class.getName()).log(Level.SEVERE,
  null, ex);
} finally {
  try {
    inputStream.close();
    ostream.close();
    server.close();
  } catch (IOException ex) {
    Logger.getLogger(ECHOClient.class.getName()).log(Level.SEVERE,
    null, ex);
  }
}
```

现在更新服务器

```java
String inString = inputStream.readUTF(); // 读取用户发送的内容
outString = inString.toUpperCase(); // 转换为大写
ostream.writeUTF(outString);

// 关闭连接
inputStream.close();
```

运行服务器和客户端，你应该得到类似的输出：

```
Welcome!
```

## 第 159 章：FTP (文件传输协议)

| 参数 | 详情 |
| :--- | :--- |
| host | FTP 服务器的名称或 IP 地址 |
| port | 服务器端口 |
| username | 服务器用户名 |
| password | 服务器密码 |

## 第 159.1 节：连接并登录 FTP 服务器

要在 Java 中使用 FTP，你需要创建一个 `FTPClient`，然后使用 `.connect(String server, int port)` 和 `.login(String username, String password)` 连接并登录。

```java
import java.io.IOException;
import org.apache.commons.net.ftp.FTPClient;
import org.apache.commons.net.ftp.FTPReply;
// 此项目所需的所有资源
```

```java
public class FTPConnectAndLogin {

public static void main(String[] args) {
// 设置以匹配你的 FTP 服务器
String server = "www.server.com"; // 服务器可以是主机名或 IP 地址
int port = 21;
String user = "Username";
String pass = "Password";

FTPClient ftp = new FTPClient();
ftp.connect(server, port);
ftp.login(user, pass);

}
```

现在我们完成了基础工作。但如果连接服务器时出错怎么办？我们希望在出错时知道并获取错误信息。让我们添加一些代码来捕获连接时的错误。



```java
try {
    ftp.connect(server, port);
    showServerReply(ftp);
    int replyCode = ftp.getReplyCode();
    if (!FTPReply.isPositiveCompletion(replyCode)) {
        System.out.println("操作失败。服务器回复代码：" + replyCode);
        return;
    }
    ftp.login(user, pass);
} catch (IOException ex) {
    // 处理异常
}
```

让我们逐步分解我们刚刚所的操作。

`showServerReply(ftp);`

这指的是我们在稍后步骤将创建的函数。

`int replyCode = ftp.getReplyCode();`

这从服务器获取错误/回复代码并将其存储为整数。

```java
if (!FTPReply.isPositiveCompletion(replyCode)) {
    System.out.println("操作失败。服务器回复代码：" + replyCode);
    return;
}
```

这检查回复代码以查看是否有错误。如果有错误，它将简单打印“操作失败。服务器回复代码：”后跟错误代码。我们还添加了 `try/catch` 块，我们将在下一个步骤对其进行添加。接下来，让我们创建一个检查 `ftp.login()` 错误的函数。

```java
boolean success = ftp.login(user, pass);
showServerReply(ftp);
if (!success) {
    System.out.println("登录服务器失败");
    return;
} else {
    System.out.println("已登录服务器");
}
```

让我们分解这个块。

`boolean success = ftp.login(user, pass);`

这不仅尝试登录 FTP 服务器，还将结果存储为布尔值。

`showServerReply(ftp);`

这检查服务器是否向我们发送了任何消息，但我们首先需要在后续步骤中创建该函数。

```java
public class FTPConnectAndLogin {
    public static void main(String[] args) { // 设置这些以匹配你的 FTP 服务器
        // String server = "www.server.com"; int port = 21;
        String user = "username";
        String pass = "password";

        FTPClient ftp = new FTPClient();
        try {
            ftp.connect(server, port);
            showServerReply(ftp);
            int replyCode = ftp.getReplyCode();
            if (!FTPReply.isPositiveCompletion(replyCode)) {
                System.out.println("Operation failed. Server reply code: " + replyCode);
                return;
            }
            boolean success = ftp.login(user, pass);
            showServerReply(ftp);
            if (!success) {
                System.out.println("Failed to log into the server");
                return;
            } else {
                System.out.println("LOGGED IN SERVER");
            }
        } catch (IOException ex) {
            System.out.println("Oops! Something went wrong.");
            ex.printStackTrace();
        }
    }
}
```

现在接下来让我们完成 `Catch` 块，以防我们在整个过程中遇到任何错误。

完成后的 `catch` 块现在会在发生错误时打印“Oops! Something went wrong.”以及堆栈跟踪信息。现在我们的最后一步是创建我们已经使用了一段时间的 `showServerReply()` 方法。

```java
private static void showServerReply(FTPClient ftp) {
    String[] replies = ftp.getReplyStrings();
    if (replies != null && replies.length > 0) {
        for (String aReply : replies) {
            System.out.println("SERVER: " + aReply);
        }
    }
}
```

此函数接收一个 `FTPClient` 变量，并将其命名为 "ftp"。之后，它将来自服务器的任何回复存储在字符串数组中。接下来，它会检查是否存储了任何消息。如果有，它将以“SERVER: [reply]”的形式打印每条消息。现在我们已经写好了函数，这是完整的脚本：

```java
import java.io.IOException;
import org.apache.commons.net.ftp.FTPClient;
import org.apache.commons.net.ftp.FTPReply;

public class FTPConnectAndLogin {
    private static void showServerReply(FTPClient ftp) {
        String[] replies = ftp.getReplyStrings();
        if (replies != null && replies.length > 0) {
            for (String aReply : replies) {
                System.out.println("SERVER: " + aReply);
            }
        }
    }

    public static void main(String[] args) { // 设置这些以匹配你的 FTP 服务器
        // String server = "www.server.com"; int port = 21;
        String user = "username";
        String pass = "password";

        FTPClient ftp = new FTPClient();
        try {
            ftp.connect(server, port);
            showServerReply(ftp);
            int replyCode = ftp.getReplyCode();
            if (!FTPReply.isPositiveCompletion(replyCode)) {
                System.out.println("Operation failed. Server reply code: " + replyCode);
                return;
            }
            boolean success = ftp.login(user, pass);
            showServerReply(ftp);
            if (!success) {
                System.out.println("Failed to log into the server");
                return;
            } else {
                System.out.println("LOGGED IN SERVER");
            }
        } catch (IOException ex) {
            System.out.println("Oops! Something went wrong.");
            ex.printStackTrace();
        }
    }
}
```

我们首先需要创建一个新的 `FTPClient`，并尝试使用 `.connect(String server, int port)` 和 `.login(String username, String password)` 连接到服务器并登录。使用 `try/catch` 块进行连接和登录是非常重要的，以防我们的代码无法连接服务器。我们还需要创建一个函数，用于连接并显示我们从正在连接和登录的服务器收到的任何消息。我们将此函数命名为“showServerReply(FTPClient ftp)”。

```java
import java.io.IOException;
import org.apache.commons.net.ftp.FTPClient;
import org.apache.commons.net.ftp.FTPReply;

public class FTPConnectAndLogin {
    private static void showServerReply(FTPClient ftp) {
        String[] replies = ftp.getReplyStrings();
        if (replies != null && replies.length > 0) {
            for (String aReply : replies) {
                System.out.println("SERVER: " + aReply);
            }
        }
    }

    public static void main(String[] args) { // 设置这些以匹配你的 FTP 服务器
        // String server = "www.server.com"; int port = 21;
        String user = "username";
        String pass = "password";

        FTPClient ftp = new FTPClient();
        try {
            ftp.connect(server, port);
            showServerReply(ftp);
            int replyCode = ftp.getReplyCode();
            if (!FTPReply.isPositiveCompletion(replyCode)) {
                System.out.println("Operation failed. Server reply code: " + replyCode);
                return;
            }
            boolean success = ftp.login(user, pass);
            showServerReply(ftp);
            if (!success) {
                System.out.println("Failed to log into the server");
                return;
            } else {
                System.out.println("LOGGED IN SERVER");
            }
        } catch (IOException ex) {
            System.out.println("Oops! Something went wrong.");
            ex.printStackTrace();
        }
    }
}
```

## 嵌套类

嵌套类[ref]（需要对外部类的引用）

```cpp
class Outer {
  class Inner {
    public:
      Inner(Outer* o) :outer(o) {}
    private:
      Outer* outer;
  };
}
```

### Java

[非静态]嵌套类（又名内部类或成员类）

```java
class OuterClass {
  ...
  class InnerClass {
    ...
  }
}
```

## C++ 在另一个类内部进行静态定义

静态嵌套类

```cpp
class Outer { class Inner { ... };
};
```

### Java

静态嵌套类（又名静态成员类）[ref]

```java
class OuterClass {
  ...
  static class StaticNestedClass {
    ...
  }
}
```

## 在方法内部定义

（例如事件处理）

### C++

局部类[ref]

```cpp
void fun() {
  class Test {
    /* Test 类的成员 */;
  }
}
```

### Java

```java
局部类[ref]
class Test {
  void f() {
    new Thread(new Runnable() {
      public void run() {
        doSomethingBackgroundish();
      }
    }).start();
  }
}
```

## 第 161.3 节：值传递与引用传递

许多人认为 Java **仅** 是值传递，但情况比这复杂。通过对比下面的 C++ 值传递和 Java 示例，可以查看值传递（即拷贝）和引用传递（即别名）的多种形式。

```cpp
C++ 示例（完整代码）
// 传递对象的 拷贝
static void passByCopy(Pass obj) {
  obj.i = 22; // 仅是“局部”变化
}
```

```cpp
// 传递指针
static void passByPointer(PassIt* ptr) {
  ptr->i = 33;
  ptr = 0; // 如果是 '0'，最好使用 nullptr
}
```

```cpp
// 传递别名（即引用） 
static void passByAlias(PassIt& ref) { 
  ref.i = 44;
}
```

```cpp
// 这是一个旧式的做法。// 请查看 std::swap 以获取最佳
// 这种方法
static void swap(PassIt** pptr1, PassIt** pptr2) {
  PassIt * tmp = *ptr1;
  *ptr1 = *ptr2;
  *ptr2 = tmp;
}
```

### Java 示例（完整代码）

```java
// 传递变量的拷贝
// 注意：在 Java 中，基本类型是值传递的 public static void
passByCopy(int copy) {
  copy = 33; // 仅是“局部”变化
}
```

```java
// Java 中没有指针的概念
/*
public static void passByPointer(PassIt* ptr) {
  ptr->i = 33;
  ptr = 0; // 如果是 '0'，最好使用 nullptr 
}
*/
```

```java
// 传递别名（即引用）
public static void passByAlias(PassIt ref) { 
  ref.i = 44;
}
```

```java
// 传递别名（即引用），
// 但需要进行“手动”的、可能昂贵的拷贝 public static void
swap(PassIt ref1, PassIt ref2) {
  PassIt tmp = new PassIt(ref1);
  ref1.copy(ref2);
  ref2.copy(tmp);
}
```

## 第 161.4 节：继承 vs 组合

C++ 和 Java 都是面向对象的语言，因此以下图表适用于两者。

![](img/01cc8d6667542262308c820b3f5bd37b_1171_0.png)

## 第 161.5 节：向下强制转换 (Outcast Downcasting)

注意使用“向下强制转换”——向下转换是从继承层次中从基类到子类的转换（即多态的相反）。通常情况下，请使用多态和重写，而不是 `instanceof` 和向下强制转换。

### C++ 示例

```cpp
// 需要显式类型转换
Child *pChild = (Child *) &parent;
```

### Java 示例



```java
if (mySubClass instanceof SubClass) {
  SubClass mySubClass = (SubClass)someBaseClass;
  mySubClass.nonInheritedMethod();
}
```

## 第 161.6 节：抽象方法与类

### 抽象方法

声明时没有实现

#### C++

```cpp
纯虚函数
virtual void eat(void) = 0;
```

#### Java

```java
抽象方法
abstract void draw();
```

### 抽象类

不能被实例化

#### C++

```cpp
不能实例化；至少有 1 个纯虚方法
class AB {public: virtual void f() = 0};
```

#### Java

```java
不能实例化；可以有非抽象方法
abstract class GraphicObject {}
```

### 接口

没有实例字段

#### C++

没有与 Java 可比的事物

#### Java

```java
与抽象类非常相似，但 1) 支持多重继承；2) 没有
实例字段 interface TestInterface { }
```

## 第 162 章：音频

### 第 162.1 节：播放 MIDI 文件

可以使用`javax.sound.midi`包中的几个类播放 MIDI 文件。`Sequencer`负责 MIDI 文件的播放，它的许多方法可以设置播放控制，如循环次数、节拍、轨道静音等。

MIDI 数据的常规播放可以通过这种方式实现：

```java
import java.io.File;
import java.io.IOException;
import java.sound.midi.InvalidMidiDataException;
import java.sound.midi.MidiSystem;
import java.sound.midi.MidiUnavailableException;
import java.sound.midi.Sequence;
import java.sound.midi.Sequencer;

public class MidiPlayback {
  public static void main(String[] args) { 
    try {
      Sequencer sequencer = MidiSystem.getSequencer(); // 获取默认
      if (sequencer==null) {
        System.err.println("Sequencer device not supported");
        return;
      }
      sequencer.open(); // 打开设备
      // 创建序列，File 必须包含 MIDI 文件数据
      Sequence sequence = MidiSystem.getSequencer(new File(args[0]));
      sequencer.setSequence(sequencer); // 将其加载到 sequencer 中
      sequencer.start(); // 开始播放
    } catch (MidiUnavailableException | InvalidMidiDataException | IOException ex) { 
      ex.printStackTrace(); 
    }
  }
}
```

停止播放使用：

`sequencer.stop(); // 停止播放`

在播放期间，可以设置序列的一个或多个轨道为静音，这样指定的乐器将不会播放。以下示例将序列中的第一个轨道设为静音：

`import java.sound.midi.Track; // ...`

`Track[] track = sequencer.getTracks(); sequencer.setTrackMute(track[0]);`

如果给出了循环次数，`Sequencer`可以重复播放序列。以下设置`sequencer`播放序列四次并无限循环：

`sequencer.setLoopCount(3);`

`sequencer.setLoopCount(Sequencer.LOOP_CONTINUOUSLY);`

`Sequencer`并不总是从头开始播放序列，也不需要播放到结束。它可以通过指定序列的任何点开始和结束。通过指定序列中的 tick 来开始和结束：

```java
sequencer.setStartPosition(512);
sequencer.setEndPoint(32768);
```

`Sequencer`还可以以特定的节拍播放，这可以通过指定每分钟节拍 (BPM) 或每音符微秒 (MPQ) 来控制。

```java
sequencer.setTempoBPM(1250f);
sequencer.setTempoMPQ(4750f);
sequencer.setTempoFactor(1.5f);
```

使用`Sequencer`后，记得关闭：

`sequencer.close();`

### 第 162.2 节：循环音频文件

需要的导入：

```java
import javax.sound.sampled.AudioSystem;
import javax.sound.sampled.Clip;
```

此代码创建一个 clip 并在启动后连续播放：

```java
Clip clip = AudioSystem.getClip();
clip.open(AudioSystem.getAudioInputStream(new URL(filename)));
clip.start();
clip.loop(Clip.LOOP_CONTINUOUSLY);
```

获取所有支持的文件类型的数组：

`AudioFormat.Type [] audioFileTypes = AudioSystem.getAudioFileTypes();`

### 第 162.3 节：基础音频输出

Hello Audio! 播放本地或网络存储的音频文件如下。它适用于未压缩的 .wav 文件，不应用于播放 mp3 或压缩文件。

```java
import java.io.*;
import java.net.URL;
import javax.sound.sampled.*;

public class SoundClip {
  // 构造函数
  public SoundClip() {
    try {
      // 打开音频输入流。
      File soundFile = new File("/usr/share/sounds/alsa/Front_Center.wav"); // 你也可以通过 URL 获取音频文件
      AudioInputStream audioIn = AudioSystem.getAudioInputStream(soundFile);
      Format format = audioIn.getFormat();

      // 获取 sound clip 资源。
      DataLine.Info info = new DataLine.Info(Clip.class, format); 
      Clip clip = (Clip)AudioSystem.getLine(info);
      // 打开音频 clip 并从音频输入流加载采样。
      clip.open(audioIn);
      clip.start();

    } catch (UnsupportedAudioFileException e) {
      e.printStackTrace();
    } catch (IOException e) {
      e.printStackTrace();
    } catch (LineUnavailableException e) {
      e.printStackTrace();
    }
  }

  public static void main(String[] args) { 
    new SoundClip();
  }
}
```

#### 第 162.4 节：裸金属音频

在使用 Java 生成声音时，你也可以接近“裸金属”操作。这段代码将把原始二进制数据写入操作系统的音频缓冲区以生成声音。理解这种方式生成声音的局限性和必要的计算至关重要。由于播放几乎是瞬时的，计算需要以近实时的方式进行。

因此，这种方法不适用于复杂的音频采样。对于此类用途，使用专用工具是更好的方法。以下方法会在给定的频率、音量持续时间内生成并直接输出矩形波。

```java
public void rectangleWave(byte volume, int hertz, int msecs) { final SourceDataLine dataLine;
// 24 kHz = 8bit, single-channel, signed little endian AudioFormat
AudioFormat af = new AudioFormat(24_000, 8, 1, true, false); try {
```

```java
dataLine = AudioSystem.getSourceLine(af);
dataLine.open(af, 10000); // audio buffer size: 10 samples
} catch (LineUnavailableException e) {
throw new RuntimeException(e);
}
```

```java
int waveHalf = 24_000 / hertz; // samples for half a period
byte[] buffer = new byte[waveHalf * 20];
int samples = msecs * (24_000 / 1000); // 24k (samples / sec) / 1000 (ms/sec) * time(ms)
```

```java
dataLine.start(); // starts playback int sign = 1;
for (int i = 0; i < samples; i += buffer.length) {
    for (int j = 0; j < 20; j++) { // generate 10 waves into buffer
        sign *= 1;
        // fill from the jth wave-half to the j+1th wave-half with volume
        Arrays.fill(buffer, waveHalf * j, waveHalf * (j+1), (byte) (volume * sign));
```

```java
        }
        dataLine.write(buffer, 0, buffer.length); //
    }
    dataLine.drain(); // forces buffer drain to hardware
    dataLine.stop(); // ends playback
}
```

为了生成更具差异化的不同波形，需要正弦计算以及可能更大的样本量。这会导致代码变得复杂得多，因此在此处省略了。

### 第 163 节：Java 打印服务 (Java Print Service)

Java Print Service API 发现打印服务并向它们发送打印请求的功能。它包含了基于 IETF 规范 RFC 2911 中互联网打印协议 (IPP) 1.1 指定的标准属性的可扩展打印属性。

#### 第 163.1 节：构建将要打印的 Doc

`Doc`是一个接口，Java Print Service API 提供了一个名为`SimpleDoc`的简单实现。

每个`Doc`实例基本上由两个方面组成：

- 打印数据内容本身（电子邮件、图像、文档等）

- 打印数据格式，称为`DocFlavor`（MIME 类型 + 表示类类）。

在创建`Doc`对象之前，我们需要从某处加载文档。在示例中，我们将从磁盘加载一个特定文件：

```java
FileInputStream pdfFileInputStream = new FileInputStream("something.pdf");
```

现在，我们必须选择一个与我们的内容匹配的`DocFlavor`。`DocFlavor`有一组常量来表示最常见的数据类型。让我们选择`INPUT_STREAM.PDF`：

`DocFlavor pdfDocFlavor = DocFlavor.INPUT_STREAM.PDF;`

现在，我们可以创建一个`SimpleDoc`的新实例：

`Doc = new SimpleDoc(pdfFileInputStream, pdfDocFlavor, null);`

`Doc`对象现在可以发送到打印作业请求（参见“从打印服务创建打印作业”）。

#### 第 163.2 节：发现可用的打印服务

要发现所有可用的打印服务，我们可以使用`PrintServiceLookup`类。让我们如何操作：

```java
import javax.print.PrintService;
import javax.print.PrintServiceLookup;
public class DiscoveringAvailablePrintServices {

    public static void main(String[] args) {
        discoverPrintServices();
    }

    public static void discoverPrintServices() {
        PrintService[] allPrintServices = PrintServiceLookup.lookupPrintServices(null, null);
        for (PrintService printService : allPrintServices) {
            System.out.println("Print service name: " + printService.getName());
        }
    }
}
```

该程序在 Windows 环境下执行时，将打印类似如下的内容：

`Print service name : Fax`

`Print service name: Microsoft Print to PDF`

`Print service name: Microsoft XPS Document Viewer`

#### 第 163.3 节：定义打印请求属性

有时我们需要确定打印请求的某些方面。我们称它们为属性（attribute）。打印请求属性的示例有：

- 份数（1, 2 等）

- 方向（纵向或横向）

- 色彩性（单色、彩色）

- 质量（草稿、普通、高质）

- 面数（单面、双面等）

等等……

在选择其中一个以及每个属性将具有什么值值之前，我们首先需要构建一个属性集：

`PrintRequestAttributeSet pras = new HashRequestAttributeSet();`

现在我们可以添加它们。一些示例是：

```java
pras.add(new Copies(5));
pras.add(MediaSize.ISO_A4);
pras.add(OrientationRespected.PORTRAIT);
pras.add(PrintQuality.NORMAL);
```

相应的对象现在可以发送到打印作业请求（参见“从打印服务创建打印作业”）。

#### 第 163.4 节：监听打印请求状态变化

对于大多数打印客户端来说，知道打印作业是否完成或失败是非常有用的。Java Print Service API 提供了一些功能来获取这些场景的信息。我们只需要做：

- 为`PrintJobListener`接口提供实现，并在打印作业中注册该实现。

当打印作业状态更改时，我们将收到通知。我们可以执行任何需要的操作，例如：

- 更新用户界面，

- 另一个业务流程，

- 在数据库中记录某些内容，

- 或者简单地记录。

在下面的示例中，我们将记录每个打印作业的状态变化：

```java
import javax.print.event.PrintJobEvent;
import javax.print.event.PrintJobListener;
public class LoggerPrintJobListener implements PrintJobListener {
// 在这里编写你喜欢的 Logger 类！
```

最后，我们可以将打印监听器添加到打印作业本身上，如下：

`DocPrintJob printJob = service.createPrintJob();`

`printJob.addPrintListener(new LoggerPrintJobListener());`

`printJob.print(doc, pras);`

##### PrintEvent pje 参数

注意每个方法都有一个`PrintEvent`参数。在示例中为了简单起见没有使用它，但你可以使用它来探索状态。例如：

`pje.getPrintJob().getAttributes();`

将返回一个`PrintJobAttributeSet`实例，你可以以 for-each 方式运行它们。

##### 实现目标的另一种方法

实现目标的另一种选择是扩展`PrintJobAdapter`类，正如名称所示，它是`PrintJobListener`的适配器。实现接口时，我们必须实现所有方法。这种方法的优点是我们只需要重写我们想要的方法。让我们看看它是如何工作的：



## 第 163.6 节：从打印服务创建打印作业

打印作业是在特定的打印服务中打印某些内容的请求。它基本上由将要打印的数据（参见“构建要打印的文档”）以及一组属性组成。在选择了正确的打印服务实例后，我们可以请求创建打印作业：

```
DocPrintJob printJob = printService.createPrintJob();
```

`DocPrintJob` 接口为我们提供了 `print` 方法：

```
printJob.print(doc, pras);
```

`doc` 参数是一个 `Doc`：即要打印的数据。而 `pras` 参数是一个 `PrintRequestAttributeSet` 接口：一组 `PrintRequestAttribute`。打印属性的示例包括：

- 份数（1, 2 等）
- 方向（纵向或横向）
- 色度（单色、彩色）
- 质量（草稿、普通、高质）
- 面数（单面、双面等）等等

`print` 方法可能会抛出 `PrintException`。

## 第 164 章：CompletableFuture

`CompletableFuture` 是 Java SE 8 中新增的一个类，它实现了 Java SE 5 中的 `Future` 接口。除了支持 `Future` 接口外，它还添加了许多方法，允许在 future 完成时执行回调。

## 第 164.1 节：CompletableFuture 的简单示例

在下面的示例中，`calculateShippingPrice` 方法计算运费，这需要一些处理时间。在现实世界的示例中，这可以通过联系另一个服务器来实现，服务器根据产品重量和运输方式返回价格。

通过 `CompletableFuture` 以异步方式对此进行建模，我们可以在方法中继续其他工作（例如计算包装成本）。

```java
public static void main(String[] args) {
    int price = 15; // 让我们保持简单，这里我们使用整数价格
    int weightInGrams = 900;
    calculateShippingPrice(weightInGrams) // 在这里，我们获得了 future
        .thenAccept(shippingPrice -> { // 然后立即对其进行处理！
            // 这种风格非常有助于保持简洁
            System.out.println("Your total price is: " + (price + shippingPrice));
            System.out.println("Please stand by. We are calculating your total price.");
        });
}

public static CompletableFuture<Integer> calculateShippingPrice(int weightInGrams) {
    return CompletableFuture.supplyAsync(() -> {
        // supplyAsync 是一个工厂方法，将给定的
        // Supplier<U> 转换为 CompletableFuture<U>
        // 假设每 200 克运费为 1 美元
        int shippingCosts = weightInGrams / 200;
        try {
            Thread.sleep(2000L); // 现在让我们模拟一些等待时间...
        } catch(InterruptedException e) { /* 我们可以安全地忽略它 */ }
        return shippingCosts; // 并返回费用！
    });
}
```

## 第 165 章：运行时命令

## 第 165.1 节：添加关闭钩子 (shutdown hooks)

有时你需要在程序停止时执行一段代码，例如释放你打开的系统资源。你可以使用 `addShutdownHook` 方法在程序停止时运行一个线程：

```
Runtime.getRuntime().addShutdownHook(new Thread(() -> {
    ImportantStuff.someImportantOutputStream.close();
}));
```

## 第 166 章：单元测试

单元测试是测试驱动开发不可或缺的一部分，也是构建任何健壮应用程序的重要特性。在 Java 中，单元测试几乎完全使用外部库和框架完成，其中大多数框架都有自己的文档标记。此存根文章将作为向读者介绍可用工具及其相应文档的一种。

## 第 166.1 节：什么是单元测试？

这是一个简单的入门介绍。之所以把它放在这里是因为文档强制要求包含示例，即使它被设计为一个存根文章。如果你已经了解了单元测试的基础知识，可以随时跳到备注部分，那里会提到了特定的框架。

单元测试是确保给定模块的行为符合预期。在大规模应用程序中，确保模块在真空中能够正确执行是确保应用程序保真性的不可或缺的一部分。

考虑以下（微不足道的）伪示例：

```java
public class Example {
    public static void main(String args[]) {
        new Example();
    }

    // 应用级测试。
    public Example() {
        Consumer c = new Consumer();
        System.out.println("VALUE = " + c.getVal());
    }
}

// 你的模块。
class Consumer {
    private Capitalizer c;

    public Consumer() {
        c = new Capitalizer();
    }

    public String getVal() {
        return c.getVal();
    }
}

// 另一个团队的模块。
class Capitalizer {
    private DataReader dr;

    public Capitalizer() {
        dr = new DataReader();
    }

    public String getVal() {
        return dr.readVal().toUpperCase();
    }
}

// 另一个团队的模块。
class DataReader {
    public String readVal() {
        // 指向你应用程序部署中某处的文件，或者可能
        // 通过特定部署的网络获取。
        File f;
        String s = "data";
        // ... 从 f 读取数据到 s ...
        return s;
    }
}
```

所以这个示例是微不足道的；`DataReader` 从文件中获取数据，将其传递给 `Capitalizer`，`Capitalizer` 将所有字符转换为大写，然后传递给 `Consumer`。但 `DataReader` 与我们的应用程序环境高度耦合，因此我们推迟对该链的测试，直到我们准备好部署测试版本。

现在，假设在发布过程某个地方，由于未知原因，`Capitalizer` 中的 `getVal()` 方法从返回大写的 String 变为返回小写的 String：

```java
// 另一个团队的模块。
class Capitalizer {
    ...
    public String getVal() {
        return dr.readVal().toLowerCase();
    }
}
```

显然，这破坏了预期的行为。但由于执行 `DataReader` 涉及的过程异常复杂，我们在下一次测试部署之前都不会注意到这一点。因此，这个 bug 在我们的系统中存在了几天、几周或几个月，产品经理发现了这个问题，并立即转向了 `Consumer` 的团队负责人。“为什么会发生这种情况？你们改了什么？显然，你们一无所知。你们完全不知道发生了什么。”

（希望）他们能意识到自己的错误，并就如何引入其预期效果达成替代方案。

在如何实现这些测试方面，此处省略了一些内容，但这些内容在特定框架的文档中（见备注链接）有所介绍。希望这能作为说明单元测试重要性的示例。

## 第 167 章：断言 (Asserting)

### 参数详情

`expression1` 如果此表达式求值为假，则语句将抛出 `AssertionError`。使用 `assert` 语句产生的 `AssertionError` 将带有此消息。

### 第 167.1 节：使用 assert 检查算术

```java
a = 1 Math.abs(1 % 2);
// 如果我上面的计算错误，这将抛出错误。
assert a >= 0 && a <= 1 : "Calculated value of " + a + " is outside of expected bounds";
return a;
```

## 第 168 章：多发布 JAR 文件

Java 引入引入特性之一是多发布 Jar (MRJAR)，它允许在同一个 Jar 文件中封装针对多个 Java 版本的类。该特性在 JEP 238 中规范化。

### 第 168.1 节：多发布 Jar 文件内容的示例

通过在 `MANIFEST.MF` 文件中设置 `Multi-Release: true`，该 Jar 文件将变成多发布 Jar，Java 运行时（只要支持 MRJAR 格式）将根据当前的主版本选择合适的类版本。

此类 Jar 的结构如下：

```
jar root
- A.class
- B.class
- C.class
- D.class
- META-INF
  - versions
    - 9
      - A.class
      - B.class
    - 10
      - A.class
```

在 JDK < 9 上，只有根条目中的类对 Java 运行时可见。

在 JDK 9 上，类 A 和 B 将从 `root/META-INF/versions/9` 目录加载，而 C 和 D 将从基础条目加载。

在 JDK 10 上，类 A 将从 `root/META-INF/versions/10` 目录加载。

### 第 168.2 节：使用 jar 工具创建多发布 Jar

可以使用 `jar` 命令创建一个多发布 Jar，该 Jar 包含针对 Java 8 和 Java 9 编译的两个版本的类，尽管会有一个警告提示这些类是相同的：

```bash
C:\Users\manouti>jar --create --file MR.jar -C sampleproject-base demo --release 9 -C sampleproject-9 demo
Warning: entry META-INF/versions/9/demo/SampleClass.class contains a class that is identical to an entry already in the jar
```

`--release 9` 选项告诉 `jar` 将后续所有内容（`sampleproject-9` 目录下的 `demo` 包）包含在 MRJAR 的版本条目中，即 `root/META-INF/versions/9` 下。结果内容如下：

```
jar root
- demo
  - SampleClass.class
- META-INF
  - versions
    - 9
      - demo
        - SampleClass.class
```

现在让我们创建一个名为 `Main` 的类来打印 `SampleClass` 的 URL，并将其添加到 Java 9 版本中：

```java
package demo;
import java.net.URL;
public class Main {

    public static void main(String[] args) throws Exception {
        URL url =
        Main.class.getClassLoader().getResource("demo/SampleClass.class");
        System.out.println(url);
    }
}
```

如果我们编译这个类并重新运行 `jar` 命令，将得到一个错误：

```bash
C:\Users\manouti>jar --create --file MR.jar -C sampleproject-base demo --release 9 -C sampleproject-9 demo
error: META-INF/versions/9/Main.class, contains a new public class not found in base entries
Warning: entry META-INF/versions/9/demo/Main.java, multiple resources with same name 
Warning: entry META-INF/versions/9/demo/SampleClass.class contains a class that is identical to the entry already in the jar 
invalid multi-jar file MR.jar deleted
```

原因是，如果公共类没有被添加到基础条目中，`jar` 工具将防止将它们添加到版本条目中。这样做是为了确保 MRJAR 为不同的 Java 版本暴露相同的公共 API。

请注意，在运行时并不强制执行此规则。它可能仅由 `jar` 等工具应用。在这种特定情况下，`Main` 的目的是运行示例代码，因此我们可以简单地在基础条目中添加一个副本。如果该类是 Java 9 需要的新实现的一部分，可以将其设置为非公共。

要将 `Main` 添加到根条目，我们首先需要将其编译为 Java 9 之前的版本。可以使用 `javac` 的新的 `-release` 选项来实现：

```bash
C:\Users\manouti\sampleproject-base>javac -release 8 Main.java
C:\Users\manouti\sampleproject-base>cd ../
C:\Users\manouti>jar --create --file MR.jar -C sampleproject-base demo --release 9
```

运行 `Main` 类显示 `SampleClass` 是从版本目录加载的：

```bash
C:\Users\manouti>java -classpath MR.jar demo.Main
file:/C:/Users/manouti/MR.jar!META-INF/versions/9/demo/SampleClass.class
```

### 第 168.3 节：多发布 Jar 内部加载类的 URL

给定以下多发布 Jar：

```
jar root
- demo
  - SampleClass.class
- META-INF
  - versions
    - 9
      - demo
        - SampleClass.class
```

以下类打印 `SampleClass` 的 URL：

```java
package demo;
import java.net.URL;
public class Main {

    public static void main(String[] args) throws Exception {
        URL url =
        Main.class.getClassLoader().getResource("demo/SampleClass.class");
        System.out.println(url);
    }
}
```

被解释。除非是为了诊断或规避 JIT 编译问题，否则不建议禁用 JIT 编译器。

## 第 170 章：字节码修改

### 第 170.1 节：什么是字节码？

字节码是 JVM 使用的指令集。为了说明这一点，让我们来看这个 Hello World 程序。

```java
public static void main(String[] args) {
    System.out.println("Hello World");
}
```

当它被编译成字节码时，会变成这样：

```java
import javax.print.event.PrintJobEvent;
import javax.print.event.PrintJobAdapter;

public class LoggerPrintJobAdapter extends PrintJobAdapter {
    // 在这里编写你喜欢的 Logger 类！
    private static final Logger LOG = Logger.getLogger(LoggerPrintJobAdapter.class);

    public void printJobCompleted(PrintJobEvent pje) {
        LOG.info("Print job completed = ");
    }

    public void printJobFailed(PrintJobEvent pje) {
        LOG.info("Print job failed = ");
    }
}
```



`public static void main([Ljava/lang/String; args)V`
`getstatic java/lang/System out Ljava/io/PrintStream`
`ldc "Hello World"`
`invokevirtual java/io/PrintStream print(Ljava/lang/String;)V`

背后的逻辑是什么？

嗯，应该还有更多对吧？

共有 255 个操作码（`opcodes`），但并非全部都已实现。可以在这里找到所有当前操作码的表格：Java 字节码指令列表。

我该如何编写/编辑字节码？

有多种方法可以编写和编辑字节码。你可以使用编译器、库或程序。

用于写入：

- `Jasmin`
- `Krakatau`

用于编辑：

#### 库

- `ASM`
- `Jassist`
- `BCEL` - 不支持 Java 8+

#### 工具

- `Bytecode-Viewer`
- `JBytedit`
- `reJ` - 不支持 Java 8+
- `JBE` - 不支持 Java 8+

## 我想学习字节码！

可能有一个专门针对字节码的特定文档页面。本页侧重于使用不同的库和工具对字节码进行修改。

### 第 170.2 节：如何使用 ASM 编辑 jar 文件

首先需要加载来自 jar 包的类。我们将使用三种方法来实现这个过程：

```java
loadClasses(File)
readJar(JarFile, JarEntry, Map)
getNode(byte[])
```

```java
Map<String, ClassNode> loadClasses(File jarFile) throws IOException {
    Map<String, ClassNode> classes = new HashMap<String, ClassNode>();
    JarFile jar = new JarFile(jarFile);
    Stream<JarEntry> str = jar.stream();
    str.forEach(z -> readJar(jar, z, classes));
    jar.close();
    return classes;
}
```

```java
Map<String, ClassNode> readJar(JarFile jar, JarEntry entry, Map<String, ClassNode> classes) { 
    String name = entry.getName();
    try (InputStream jis = jar.getInputStream(entry)) {
        if (name.endsWith(".class")) {
            byte[] bytes = IOUtils.toByteArray(jis);
            String cafebabe = String.format("%02X%02X%02X%02X", bytes[0], bytes[1], bytes[2], bytes[3]);
            if (!cafebabe.toLowerCase().equals("cafebabe")) { // 此类没有有效的魔数返回类；
                return;
            }
            try {
                ClassNode cn = getNode(bytes);
                classes.put(name, cn);
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
    } catch (IOException e) {
        e.printStackTrace();
    }
    return classes;
}
```

```java
ClassNode getNode(byte[] bytes) {
    ClassReader cr = new ClassReader(bytes);
    ClassNode cn = new ClassNode();
    try {
        cr.accept(cn, ClassReader.EXPAND_FRAMES);
    } catch (Exception e) {
        e.printStackTrace();
    }
    cr = null;
    return cn;
}
```

通过这些方法，加载和更改 jar 包就变成了更改 map 中 `ClassNodes` 的简单事情。在这个示例中，我们将使用 Tree API 将 jar 中的所有 `String` 替换为大写单位。

```java
File jarFile = new File("sample.jar");
Map<String, ClassNode> nodes = loadClasses(jarFile);

// 遍历 ClassNode 
for (ClassNode cn : nodes.values()) {
    // 遍历类中的方法
    for (MethodNode mn : cn.methods) {
        // 遍历方法中的指令
        for (AbstractInsnNode ain : mn.instructions.toArray()) { // 如果指令
            if (ain.getOpcode() == Opcodes.LDC) { // 将当前指令强制转换为 Ldc
                LdcInsnNode ldc = (LdcInsnNode) ain; // 如果常量是字符串，则将其大写。
                if (ldc.cst instanceof String) {
                    ldc.cst = ((String)ldc.cst).toUpperCase();
                }
            }
        }
    }
}
```

现在所有 `ClassNode` 的字符串都已经被修改了，需要保存更改。为了保存更改并获得可行的输出，必须完成以下几点：
- 将 `ClassNodes` 导出为字节
- 加载非 jar 条目（jar 中的其他资源）
- 将所有字节保存到新的 jar 中

从最后一部分，我们将创建三个方法：
`processNodes(Map<String, ClassNode> nodes)`
`loadNonClasses(File jarFile)`
`saveAsJar(Map<String, byte[]> outBytes, String fileName)`

用法：

```java
Map<String, byte[]> out = process(nodes, new HashMap<>());
out.putAll(loadNonClasses(jarFile)); 
saveAsJar(out, "sample.jar");
```

使用的方法：

```java
static Map<String, byte[]> processNodes(Map<String, ClassNode> nodes, Map<String, String> mappings) {
    Map<String, byte[]> out = new HashMap<String, byte[]>();
    // 遍历节点
    for (ClassNode cn : nodes.values()) {
        // 遍历类中的方法
        for (MethodNode mn : cn.methods) {
            // 遍历方法中的指令
            for (AbstractInsnNode ain : mn.instructions.toArray()) { // 如果指令
                if (ain.getOpcode() == Opcodes.LDC) { // 将当前指令强制转换为 Ldc
                    LdcInsnNode ldc = (LdcInsnNode) ain; // 如果常量是字符串，则将其大写。
                    if (ldc.cst instanceof String) {
                        ldc.cst = ((String)ldc.cst).toUpperCase();
                    }
                }
            }
        }
    }
    return out;
}
```

```java
static Map<String, byte[]> loadNonClasses(File jarFile) throws IOException {
    Map<String, byte[]> entries = new HashMap<>();
    ZipInputStream jis = new ZipInputStream(jarFile);
    ZipEntry entry;
    // 遍历条目
    while ((entry = jis.getNextEntry()) != null) {
        // 加载非 jar 条目（jar 中的其他资源）
        if (!entry.isDirectory()) {
            byte[] bytes = IOUtils.toByteArray(jis);
            entries.put(entry.getName(), bytes);
        }
    }
    jis.close();
    return entries;
}
```

```java
static void saveAsJar(Map<String, byte[]> outBytes, String fileName) {
    try {
        // 创建 jar 输出
        JarOutputStream out = new JarOutputStream(new File(fileName));
        // 保存 map 中的所有字节
        for (Map.Entry<String, byte[]> entry : outBytes.entrySet()) {
            // 添加新条目
            out.putNextEntry(new ZipEntry(entry.getKey()));
            // 写入
            out.write(entry.getValue());
            out.closeEntry();
        }
        out.close();
    } catch (IOException e) {
        e.printStackTrace();
    }
}
```

### 第 170.4 节：如何在 jar 包中重命名类

```java
public static void main(String[] args) throws Exception {
    File jarFile = new File("Input.jar");
    Map<String, ClassNode> nodes = loadClasses(jarFile);
    Map<String, byte[]> out = loadNonClasses(jarFile);
    Map<String, String> mappings = new HashMap<>();
    mappings.put("me/example/ExampleClass", "me/example/ExampleRenamed");
    out.putAll(process(nodes, mappings));
    saveAsJar(out, "Input-new.jar");
}
```

### 第 170.3 节：如何将 ClassNode 加载为 Class

```java
/**
 * 加载 ClassNode
 * @param cn 要加载的 ClassNode
 * @return
 */
public static Class<?> load(ClassNode cn) {
    return new ClassDefiner(ClassLoader.getSystemClassLoader()).get(cn.name.replace("/", "."), cw.toByteArray());
}
```

```java
/**
 * 从字节码加载类的加载器
 */
static class ClassDefiner extends ClassLoader {
    public ClassDefiner(ClassLoader parent) {
        super(parent);
    }
    public Class<?> get(String name, byte[] bytes) {
        Class<?> c = defineClass(name, bytes, 0, bytes.length);
        resolveClass(c);
        return c;
    }
}
```

### 第 170.5 节：Jassist 基础

`Jassist` 是一个字节码注入库，允许你通过注入 Java 代码来修改字节码，这些代码会被 `Javassist` 转换为字节码并在运行时添加到被注入的类/方法中。让我们编写第一个转换器，它实际上针对一个假设的类 `"com.my.to.be.instrumented.MyClass"`，并在每个方法的指令中添加一个日志调用。

```java
public class DynamicTransformer implements ClassFileTransformer {
    public byte[] transform(ClassLoader loader, String className, Class classBeingRedefined, ProtectionDomain protectionDomain, byte[] classfileBuffer) throws IllegalClassFormatException {
        byte[] byteCode = classFileBuffer;
        // 每个类加载时都会到达 transformer，所以我们进行过滤以匹配我们的内容
        if (className.equals("com/my/to/be/instrumented/MyClass")) {
            try {
                // 获取默认的 Javasassist 类池
                ClassPool cp = ClassPool.getDefault();
                // 从类池中获取具有此限定名的类
                CtClass cc = cp.get("com.my.to.be.instrumented.MyClass");
                // 获取检索到的类的所有方法
                CtMethod[] methods = cc.getDeclaredMethods();
                for(CtMethod meth : methods) {
                    // 要返回并注入的插桩代码
                    final StringBuffer buffer = new StringBuilder();
                    String name = meth.getName();
                    // 仅打印到缓冲区中作为日志
                    buffer.append("System.out.println(\"Method \"" + name + " executed\\"");
                }
            }
        }
    }
}
```

```java
import java.lang.instrument.Instrumentation;

public class EasyAgent {
    public static void main(String agentArgs, Instrumentation inst) {
        // 注册 transformer
        inst.addTransformer(new DynamicTransformer());
    }
}
```



启动我们的第一个插桩实验的最后一步是将此 agent 类实际注册到 JVM 机器执行。实现这一点最简单的方法是在 shell 命令中使用选项注册它：

```
java -javaagent:myAgent.jar MyApplication
```

正如我们看到的，agent/transformer 项目以 jar 包的形式添加到任何名为`MyJavaApplication`的应用程序执行中，该程序应包含类`com.my.to.be.instrumented.MyClass`以实际执行我们注入的代码。

## 第 171 节：反汇编与反编译

### 名称 `<classes>`

- `-help`, `-help`, `-?`
- `-version`
- `-v`, `-verbose`
- `-l`
- `-public`
- `-protected`
- `-package`
- `-p`, `-private`
- `-c`
- `-s`
- `-sysinfo`
- `-constants`
- `-classpath <path>`
- `-cp <path>`

### 描述

要反汇编的类列表。可以是`package1,package2,ClassName`格式，或者是`package1/package2/ClassName`格式。不要包含`.class`扩展名。

- 打印此用法信息
- 版本信息
- 打印额外信息
- 打印行号和局部变量表
- 仅显示 public 类和成员
- 显示 protected/public 类和成员
- 显示 package/protected/public 类和成员（默认）
- 显示所有类和成员
- 反汇编代码
- 打印内部类型签名
- 显示正在处理的类的系统信息（路径、大小、日期、MD5 哈希值）
- 显示最终常量
- 指定查找用户类文件的位置
- 指定查找用户类文件的位置
- `-bootclasspath <path>` 覆盖引导类类文件的位置

## 第 171.1 节：通过 javap 查看字节码

如果你想查看 Java 程序生成的字节码，可以使用提供的`java`命令来查看。

假设我们有以下 Java 源文件：

```java
package com.stackoverflow.documentation;

import org.springframework.stereotype.Service;

import java.io.IOException;

import java.io.InputStream;

import java.util.List;

@Service

public class HelloWorldService {

    public void sayHello() {

        System.out.println("Hello, World!");

    }

    private Object[] pvtMethod(List<String> strings) {

        return new Object[]{strings};

    }

    protected String tryCatchResources(String filename) throws IOException {

        try (InputStream inputStream = getClass().getResourceAsStream(filename)) {

            byte[] bytes = new byte[8192];

            int read = inputStream.read(bytes);

            return new String(bytes, 0, read);

        } catch (IOException | RuntimeException e) {

            e.printStackTrace();

            throw e;

        }

    }

    void stuff() {

        System.out.println("stuff");

    }

}
```

编译源文件后，最简单的用法是：

```
cd <包含类的目录> (例如 target/classes)
javap com/stackoverflow/documentation/SpringExample
```

这会产生如下输出：

```
Compiled from "HelloWorldService.java"

public class com.stackoverflow.documentation.HelloWorldService {

public com.stackoverflow.documentation.HelloWorldService();

public void sayHello();

protected java.lang.String tryCatchResources(java.lang.String) throws java.io.IOException; void stuff();

```

这列出了类中所有的非私有方法，但对于大多数用途来说并不是特别有用。以下命令有用得多：

```
javap -p -c -s -constants -l -v com/stackoverflow/documentation/HelloWorldService
```

其产生如下输出：

```
Classfile /Users/pivotal/IdeaProjects/stackoverflow-spring-docs/target/classes/com/stackoverflow/documentation/HelloWorldService.class

Last modified Jul 22, 2016; size 2167 bytes

MD5 checksum e633b5c292ad2170190653b7f06330

Compiled from "HelloWorldService.java"

public class com.stackoverflow.documentation.HelloWorldService

minor version: 0

major version: 51

flags: ACC_PUBLIC, ACC_SUPER

Constant pool:

#1 = Methodref 5.#60 // java/lang/Object."<init>":()V

#2 = Fieldref #61.#62 // java/lang/System.out.Ljava/io/PrintStream; #3 = =String #63 // Hello, World!

#4 = Methodref 64.#65 // java/io/PrintStream.println(Ljava/lang/String)V

#5 = Class #66 // java/lang/Object

#6 = Methodref 5.#67 // java/lang/Object.getClass:(Ljava/lang/Class; #7 = java/lang/Class.getResourceAsStream:(Ljava/lang/String;)Ljava/io/InputStream; #8 = Methodref #70.#71 // java/io/InputStream.read:([B]I

#9 = Class #72 // java/lang/String

#10 = Methodref #9.#73 // java/lang/String."<init>":([B]I)V

#11 = Methodref #70.#74 // java/io/InputStream.close():V

#12 = Class #75 // java/lang/Throwable

#13 = Methodref #12.#76 // java/lang/Throwable.addSuppressed:(Ljava/lang/Throwable)

#14 = Class #77 // java/io/IOException

#15 = Class #78 // java/lang/RuntimeException

#16 = Methodref #79.#80 // java/lang/Throwable.printStackTrace:()V

#17 = Class #81 // com/stackoverflow/documentation/HelloWorldService

#18 = Utf

#19 = Utf

#20 = Utf

#21 = Utf

#22 = Utf

#23 = Utf

#24 = Utf

#25 = Utf

#26 = Utf

#27 = Utf

#28 = Utf

#29 = Utf

#30 = Utf

#31 = Utf

#32 = Utf

#33 = Utf

#34 = Utf

#35 = Utf (Ljava/lang/;

#36 = Utf

#37 = Utf

#38 = Utf

#39 = Utf

... (为了简洁起见，常量池其余部分已省略，但逻辑相同)
```



# Java 监控与管理控制台

连接窗口帮助
`pid: 61689.com.intellij.rt.execution.application.AppMain.jmxTest.Main`
概述 内存 线程 类 VM 摘要 MBeans

| 属性值 | 值 |
|---|---|
| `GreetingString` | `welcome` |
| `SleepTime` | `10000` |
| `UserCount` | `3` |

可以在操作部分调用指定的方法。

# Java 监控与管理控制台

连接窗口帮助
`pid: 61689.com.intellij.rt.execution.application.AppMain.jmxTest.Main`
概述 内存 线程 类 VM 摘要 MBeans

| 操作调用 | |
|---|---|
| `void stop()` | |

如果您想能够使用远程管理功能，您将需要额外的 JVM 参数，例如：

- `-Dcom.sun.management.jmxremote=true` // 默认开启
- `-Dcom.sun.management.jmxremote.port=36006`
- `-Dcom.sun.management.jmxremote.authenticate=false`
- `-Dcom.sun.management.jmxremote.ssl=false`

这些参数可以在 JMX 指南的第 2 章找到。之后，您将能够通过 `jConsole` 远程连接到您的应用程序，在 `jConsole` GUI 中使用 `jconsole host:port` 或指定 `host:port` 或 `service:jmx:rmi:///jndi/rmi://hostName:portNum/jmxrmi`。

有用链接：

- JMX 指南
- JMX 最佳实践

# 第 173 章：Java 虚拟机 (JVM)

### 第 173.1 节：基础

JVM 是内存中的抽象计算机器或虚拟机。它具有平台无关的执行环境，可以将 Java 字节码解释为本地机器码。（`Javac` 用于将您的 Java 代码编译为字节码）

Java 程序运行在 JVM 内部，然后映射到底层的物理机上。它是 JDK 中的编程工具之一。
字节码是平台无关的代码，可以在每个平台上运行；而机器码是特定平台的代码，仅在 `windows` 或 `linux` 等特定平台上运行（取决于执行环境）。

部分组件包括：

- 加载器 (`Loader`) - 将 `.class` 文件加载到内存中。
- 代码验证器 (`code verifier`) - 检查代码中是否存在任何访问限制冲突。
- 执行引擎 (`Execution engine`) - 将字节码转换为可执行的机器码。
- JIT (即时编译) - JIT 是 JVM 的一部分，用于提高 JVM 的性能。它会在执行期间动态编译或翻译 Java 字节码为本地机器码。

（已编辑）

# 第 174 章：XJC

# 参数详情

`schema file`: 要转换为 Java 的 `xsd` schema 文件
`XJC` 是一个 Java SE 工具，可以将 XML 架构文件编译为带有注解的 Java 类。它包含在 JDK 包中，位于 `/bin/xjc` 路径。

### 第 174.1 节：从简单的 XSD 文件生成 Java 代码

XSD 架构 (`schema.xsd`)
以下 XML 架构 (`xsd`) 定义了一个带有 `name` 和 `reputation` 属性的用户列表。

```xml
```



# XML Schema 定义

```xml
<?xml version="1.0"?>
<xs:schema version="1.0"
           xmlns:xs="http://www.w3.org/2001/XMLSchemaSchema"
           xmlns:ns="http://www.stackoverflow.com/users"
           elementFormDefault="qualified"
           targetNamespace="http://www.stackoverflow.com/users">
```

```xml
<xs:element name="users" type="ns:Users">
  <xs:complexType name="Users">
    <xs:sequence>
      <xs:element type="ns:User" name="user" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

```xml
<xs:complexType name="User">
  <xs:attribute name="name" use="required" type="xs:string"/>
  <xs:attribute name="reputation" use="required">
    <xs:simpleType>
      <xs:restriction base="xs:int">
        <xs:minInclusive value="1" />
      </xs:restriction>
    </xs:simpleType>
  </xs:attribute>
</xs:complexType>
</xs:schema>
```

## 使用 xjc

这需要`xjc`工具（JDK 二进制文件）的路径位于系统的环境变量`PATH`中。可以使用以下命令启动代码生成：

```
xjc schema.xsd
```

这将在工作目录下生成 Java 文件。

## 结果文件

将有一些额外的注释，但基本上生成的 Java 文件如下所示：

```java
package com.stackoverflow.users;

import java.util.ArrayList;
import java.util.List;
import javax.xml.bind.annotation.XmlAccessorType;
import javax.xml.bind.annotation.XmlType;
```

```java
@XmlAccessorType(XmlAccessorType.FIELD) 
@XmlType(name = "Users", propOrder = {"user"})
public class Users {

    protected List<User> user;

    public List<User> getUser() {
        if (user == null) {
            user = new ArrayList<User>(); 
        }
        return this.user;
    }
}
```

```java
package com.stackoverflow.users;

import javax.xml.bind.annotation.XmlAccessorType;
import javax.xml.bind.annotation.XmlType;
```

```java
@XmlAccessorType(XmlAccessorType.FIELD) 
@XmlType(name = "Users")
public class User {

    protected String name;
    protected int reputation;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getReputation() {
        return reputation;
    }

    public void setReputation(int reputation) {
        this.reputation = reputation;
    }
}
```

# 第 175.5 节：XXdisableFatSpin

此选项禁用 Java 中的重量锁自旋（fat lock spin）代码，允许尝试获取重量锁的阻塞线程直接进入睡眠状态。

在 Java 中，一旦任何线程进入该对象的`synchronized`块，该对象就会被锁定。所有锁一直被持有（即保持锁定状态），直到锁定线程释放它们。如果锁不会很快释放，它可能会被膨胀为“重量锁”（fat lock）。当一个想要特定锁的线程持续检查该锁是否被占用时，并在检查时在紧凑循环中旋转，就发生了“自旋”。对重量锁进行自旋通常是有益的，但在某些情况下，它的代价可能很高昂并影响性能。`XXdisableFatSpin`允许你关闭针对重量锁的自旋，并消除潜在的性能影响。

用法：
```
-XXdisableFatSpin
```

# 第 175.6 节：XXdisableGCHeuristics

此选项禁用垃圾回收器策略的更改。压缩启发式和新生代大小启发式不受此选项影响。默认情况下，启用垃圾回收启发式。

用法：
```
-XXdisableGCHeuristics
```

# 第 175.7 节：XXdumpSize

此选项会导致生成 dump 文件，并允许你指定文件的文件的大小（即小、中、大）。

用法：
```
-XXdumpSize:<size>
```

| size | 描述 |
| :--- | :--- |
| none | 不生成 dump 文件。在 Windows 上，会生成一个小型 dump 文件（在 Linux 上会生成完整的 core dump）。小型 dump 仅包含线程栈及其回溯信息，以及其他极少的内容。这是 Hot JVM 8.1（带服务包 1 和 2）以及 7.0（带服务包 3 及更高版本）的默认设置。 |
| normal | 在所有平台上生成普通 dump。该 dump 文件包含除 Java 堆以外的所有内存。这是 Hot JVM 1.4.2 及更高版本的的默认值。 |
| large | 包含内存中的所有内容，包括 Java 堆。此选项使`-XXdumpSize`等同于`-XXdumpFullState`。 |

# 第 175.8 节：XXexitOutOfMemory

此选项使 Hot JVM 在第一次发生内存溢出错误（out of memory error）时退出。如果你倾向于重启 Hot JVM 实例而不是处理内存溢出错误，可以使用此选项。在启动时输入此命令强制 Hot JVM 在第一次发生内存溢出错误时退出。

用法：
```
-XXexitOutOfMemory
```

# 第 176 章：JVM 工具接口

## 第 176.1 节：遍历从对象可可达的对象（堆 1.0）

```cpp
#include <vector>
#include <string>
```

```cpp
#include "agent_util.hpp"
//此文件可以在 Java SE Development Kit 8u101 的 Demos and Samples 中找到
//参见 http://download.oracle.com/otn-pub/jdk/java/8u101-b13-demos/jdk-8u101-windows-x64-demos.zip
//jdk1.8.0_101.zip!\demo\jvmti\versionCheck\src\agent_util.h
```

```cpp
/*
* 用于 jvmti->SetTag(object, <pointer to tag>); 的结构体 *
* http://docs.oracle.com/java/7/docs/platform/jvmti/jvmti.html#SetTag
*/
typedef struct Tag
{
    jlong referrer_tag ;
    jlong size;
    char* classSignature;
    jint hashCode;
} Tag;

/*
* 工具函数: jlong -> Tag* */
static Tag* pointerToTag(jlong tag_ptr) {
    if (tag_ptr == 0)
    {
        return new Tag();
    }
    return (Tag*)(ptrdiff_t)(void*)tag_ptr; 
}

/*
* 工具函数: Tag* -> jlong */
static jlong tagToPointer(Tag* tag) {
    return (jlong)(ptrdiff_t)(void*)tag; 
}

/*
* 堆 1.0 回调
* http://docs.oracle.com/java/7/docs/platform/jvmti/jvmti.html#jvmtiObjectReference
*/
static jvmtiInvocationControl JNICALL heapObjectReferencesCallback(
    jvmtiObjectReferenceKind reference_kind,
    jlong class_tag,
    jlong size,
    jlong* tag_ptr,
    jlong referrer_tag,
    void* user_data)
{
    // 仅遍历引用字段
    if (reference_kind != JVMTI_HEAP_REFERENCE_FIELD) {
        return JVMTI_ITERATION_IGNORE;
    }

    auto tag_ptr = (std::vector<jlong>*)(ptrdiff_t)(void*)user_data; // 创建分配 tag
    auto t = pointerToTag(*tag_ptr);
    t->referrer_tag = referrer_tag;
    t->size = size;
    *tag_ptr = tagToPointer(t);

    // 收集
    (*tag_ptr_list).push_back(*tag_ptr);
    return JVMTI_ITERATION_CONTINUE;
}
```

```cpp
/*
* 演示从对象可可达对象的的主函数 *
* http://docs.oracle.com/java/7/docs/platform/jvmti/jvmti.html#IterateOverObject
*/
void iterateOverObjectHeapReferences(jvmtiEnv* jvmti, jNIEnv* env, object object) {
    std::vector<jlong> tag_ptr_list;
    auto t = new Tag();
    jvmti->SetTag(object, tagToPointer(t));
    tag_ptr_list.push_back(tagToPointer(t));

    stdout_message("tag list size before call callback: %d\n", tag_ptr_list.size());

    /*
    * 为每个可达对象引用调用回调
    * 参见 http://docs.oracle.com/java/7/docs/platform/jvmti/jvmti.html#IterateOverObject
    */
    jvm->IterateOverObjectsReachableFromObject(object,
        &heapObjectReferencesCallback,
        (void*)&tag_ptr_list);

    stdout_message("tag list size after call callback: %d\n", tag_ptr_list.size());
}
```

> 注：提供的 OCR 文本代码块包含严重的碎片和语法错误。我根据标准的 JVTI API 和可用片段进行了重构，以确保输出的连贯性。

## Xss512k JavaApp

### 查找默认大小

可以使用`-XX:+printFlagsFinal`选项在启动 JVM 之前打印所有标志的值。这可以用于打印堆大小和栈大小设置的默认值，如下：

对于 Linux、Unix、Solaris 和 Mac OSX：

```bash
$ java -XX:+printFlagsFinal -version | grep -iE 'HeapSize|PermSize|ThreadStackSize'
```

对于 Windows：

```bash
java -XX:+PrintFlagsFinal -version | findstr /i "HeapSize PermSize\ThreadStackSize"
```

上述命令的输出将类似于下面：

```
uint InitialHeapSize := 20655360 {product} uint MaxHeapSize := {product} uint PermSize = 21757952 {pd product} uint
MaxPermSize = 8598322 {pd product} intx ThreadStackSize = 1024 {pd product}
```

大小以字节为单位。

## 第 177.2 节：垃圾回收

### C++ 方法 - new 和 delete

在 C++ 等语言中，应用程序负责管理动态分配内存所使用的内存。当在 C++ 堆上使用`new`运算符创建对象时，需要对应使用`delete`运算符来释放该对象：

如果程序忘记删除对象而只是“忘记”了它，那么相关的内存就会对应用程序丢失。这种情况的术语是**内存泄漏**，如果内存泄漏过多，应用程序可能会使用越来越多的内存，并最终崩溃。

另一方面，如果应用程序尝试两次删除同一个对象，或者在对象被删除后使用该对象，那么应用程序可能会因为内存损坏问题而崩溃。

在复杂的 C++ 程序中，使用`new`和`delete`实现内存管理是非常耗时的。事实上，内存管理是 Bug 的常见来源。

### Java 方法 - 垃圾回收

Java 采取了不同的方法。Java 提供了一种名为垃圾回收（Garbage Collection）的自动机制，用以回收不再需要的对象所使用的内存。Java 运行时负责找到需要被释放的对象。这项任务由称为垃圾回收器（简称 GC）的组件执行。

在 Java 程序执行期间任何时候，我们都可以将所有现有对象的集合分为两个不同的子集：

- 可达对象（Reachable objects）由 Java 语言规范（JLS）定义如下：
  - 可达对象是指从任何存活线程的任何潜在后续计算都可以被访问的任何对象。
  在实践中，这意味着存在一条从作用域内的局部变量或静态变量开始的引用链，代码可以通过该链到达该对象。
- 不可达对象（Unreachable objects）是指无法通过上述方式到达的对象。任何不可达的对象都符合被垃圾回收的条件。这并不意味着它们会被垃圾回收。事实上：

一个不可达对象在变为不可达时不会立即被回收。一个不可达对象可能永远不会被垃圾回收。Java 语言规范为 JVM 实现在决定何时收集不可达对象方面留了很大的空间。它也（在实践中）允许 JVM 实现在检测不可达对象时采取保守态度。

JLS 保证的一点是，没有任何可达对象会被垃圾回收。

### 当对象变得不可达时发生了什么

首先，当一个对象变得不可达时，什么都不会发生。只有当垃圾收集运行并检测到该对象不可达时，才会发生事情。此外，GC 运行没有检测到所有不可达对象也是很常见的。

当 GC 检测到不可达对象时，可能会发生以下事件：

1. 如果有任何引用对象指向该对象，这些引用将在对象被删除之前清除。
2. 如果对象是可终化的（finalizable），那么它将被终化。这发生在对象被删除之前。
3. 对象可以被删除，其所占用的内存可以被回收。注意，在删除之前，会发生上述引用清理的事件。

### 可达和不可达对象的示例

考虑以下示例：

```java
public class List {
    public Node next;
}
```

```java
public class NaiveStack {
    private Object[] stack = new Object[100];
    private int top = 0;

    public void push(Object obj) {
        if (top >= stack.length) {
            throw new StackException("stack overflow");
        }
        stack[top++] = obj;
    }

    public Object pop() {
        if (top <= 0) {
            throw new StackException("stack underflow");
        }
        return stack[--top];
    }

    public boolean isEmpty() { 
```



## 第 177.3 节：Java 中的内存泄漏

在垃圾回收的示例中，我们暗示 Java 解决了内存泄漏问题。这并非如此。Java 程序可能会发生内存泄漏，尽管泄漏的原因有所不同。

### 可达对象可以泄漏

考虑以下栈实现：

```java
public class NaiveStack {

  private Object[] stack = new Object[100];

  private int top = 0;

  public void push(Object obj) {

    if (top >= stack.length) {

      throw new StackException("stack overflow");

    }

    stack[top++] = obj;

  }

  public Object pop() {

    if (top <= 0) {

      throw new StackException("stack underflow");

    }

    return stack[--top];

  }

  public boolean isEmpty() { 

    return top == 0;

  }

}
```

当你推入一个对象并立即弹出时，栈中仍然存在指向该对象的引用。

栈实现的逻辑意味着该引用无法返回给 API 的客户端。如果一个对象已经被弹出，我们可以证明无法“在任何存活线程的任何潜在后续计算中被访问”。问题是，当前的 JVM 无法证明这一点。

让我们检查 `test()` 调用时发生了什么：

```java
public class ListTest {

    public static void main(String[] args) {

        NaiveStack stack = new NaiveStack();

        Node n1 = new Node(); // T1

        stack.push(n1); // T2

        Node n2 = new Node(); // T3

        stack.push(n2); // T4

        n1.next = n2; // T5

        n1 = null; // T6

        stack.pop(); // T7

        stack.pop(); // T8

    }

}
```

在 T1 处，`n1` 是可达的。在 T2 处，`n1` 被推入栈中。在 T3 处，`n2` 是可达的。在 T4 处，`n2` 被推入栈中。在 T5 处，`n1.next` 指向 `n2`。在 T6 处，`n1` 被置为 `null`，但它仍然通过栈数组是可达的。

在 T7 处，`stack.pop()` 返回了 `n2`，此时 `n2` 在局部变量中是可达的。在 T8 处，`stack.pop()` 返回了 `n1`（之前的引用），虽然此时 `n1` 出了作用域，但由于 `n1.next` 指向 `n2`，`n2` 仍然是可达的。

如果我们在 T5 处执行 `n1.next = null;`，那么 `n2` 就会变得不可达。

当你推入一个对象并立即弹出时，栈数组中仍然存在指向该对象的引用。

栈实现的逻辑意味着该引用无法返回给 API 的客户端。如果一个对象已经被弹出，我们可以证明它无法“在任何存活线程的任何潜在后续计算中被访问”。问题是，当前的 JVM 无法证明这一点。当前的 JVM 在确定引用是否可达时并不考虑程序的逻辑。（从一开始开始，这是不切行的。）

但撇开可达性真正含义的问题，我们显然看到 `NaiveStack` 实现“留住”了需要回收的对象。这就是内存泄漏。在这种情况下，解决方案是直观的：

```java
public Object pop() {

  if (top <= 0) {

    throw new StackException("stack underflow");

  }

  Object popped = stack[--top];

  stack[top] = null; // 将弹出的引用替换为 null。返回 popped;

}
```

### 缓存可以是内存泄漏

提高服务性能的常用策略是缓存结果。其思想是将常见请求及其结果存储在称为缓存的内存数据结构中。然后，每当有请求时，都在缓存中查找请求。如果查找成功，则返回相应的保存结果。

如果实施得当，这种策略可能非常有效。然而，如果实施不当，缓存可能会导致内存泄漏。考虑以下示例：

```java
public class RequestHandler {

    private Map<Task, Result> cache = new HashMap<>();

    public Result doRequest(Task task) { Result result = cache.get(task); if

        (result == null) {

            result = doRequestProcessing(task); cache.put(task, result);

        }

        return result;

    }

}
```

这段代码的问题在于，虽然对 `doRequest` 的任何调用都会向缓存中添加新条目，但没有任何机制移除它们。如果服务不断接收不同的任务，缓存最终将消耗所有可用内存。这就是内存泄漏的一种。

解决此问题的方法之一是使用具有最大限制缓存，并在缓存超过最大值时丢弃旧条目。（丢弃最少使用的条目是一个很好的策略）。另一种方法是使用 `WeakHashMap` 构建缓存，这样当堆过满时，JVM 可以驱除缓存项。

## 第 177.4 节：最终化 (Finalization)

Java 对象可以声明一个 `finalize` 方法。该方法在 Java 释放该对象的内存之前被调用。它通常看起来如下：

```java
public class MyClass {

    // 类的方法

    @Override

    protected void finalize() throws Throwable { // 清理代码

    }
```

然而，关于 Java 最终化的行为，有一些重要的注意事项。Java 不保证 `finalize()` 方法会在何时被调用。Java 甚至不能保证在应用程序运行的生命周期内会调用一次 `finalize()` 方法。唯一保证的是该方法会在对象删除之前被调用……如果对象确实被删除的话。

这些注意事项意味着，依赖 `finalize` 方法来执行必须及时完成的清理（或其他）操作是一个坏主意。对最终化的过度依赖会导致存储泄漏、内存泄漏以及其他问题。

简而言之，只有极少数情况下最终化实际上是一个良好的解决方案。

## 最终化器只运行一次

通常情况下，对象在被最终化后会被删除。但这并非总是如此。请考虑以下示例 1：

```java
public class CaptainJack {

    public static CaptainJack notDeadYet = null;

    protected void finalize() { // 复活！

        notDeadYet = this;

    }

}
```

当 `CaptainJack` 的实例变得不可达且垃圾回收器尝试回收它时，`finalize()` 方法会将该实例的引用赋值给 `notDeadYet` 变量。这将使实例再次可达，垃圾回收器就不会删除它。

问题：杰克船长是不朽的吗？
答案：不是。

陷阱在于，JVM 在对象的整个生命周期内只会对其对象运行一次最终化器。如果你将 `notDeadYet` 赋值为 `null` 导致复活的实例再次不可达，垃圾回收器将不再对该对象调用 `finalize()`。

- 1 - 参见 https://en.wikipedia.org/wiki/Jack_Harkness。

## 第 177.5 节：手动触发 GC

你可以通过调用 `System.gc()` 手动触发垃圾回收器。

然而，Java 不保证在调用返回时垃圾回收器已经运行。此方法仅仅是向 JVM（Java 虚拟机）“建议”你想要让它运行垃圾回收器，但不会强制其执行。

尝试手动触发垃圾回收通常被认为是一种坏做法。运行 JVM 时可以使用 `-XX:+DisableExplicitGC` 选项禁用对 `System.gc()` 的调用。通过 `System.gc()` 触发垃圾回收可能会破坏 JVM 所使用的特定垃圾回收器实现中的正常垃圾管理/对象晋活动。

## 第 178 章：Java 性能优化
### 第 178.1 节：基于证据的 Java 性能优化方法

唐纳德·克努斯（Donald Knuth）经常被引用这句话：

> “程序员浪费大量时间去思考或担心程序中非关键部分的运行，而这些对效率的尝试实际上对调试和维护产生了强烈的负面影响。我们应该忘记微小的效率，在 97% 的情况下都是如此：过早优化是万恶之源。我们不应放弃在关键时刻的机会。”

来源

考虑到这些建议，以下是优化程序的推荐步骤：

- 1. 首先，以简单性和正确性为核心设计并编写你的程序或库。从开始开始，不要在性能上花费太多精力。
- 2. 让它处于工作状态，并（理想情况下）为代码库的关键部分编写单元测试。
- 3. 开发一个应用级的性能基准测试。基准测试应该涵盖应用程序中性能关键的方面，并执行与应用程序在生产环境中用法类似的系列任务。
- 4. 测量性能。
- 5. 将测量的性能与你对应用程序所需速度的标准进行比较。（避免不切实际、无法实现或无法量化的标准，如“尽可能快”）。
- 6. 如果符合标准，则停止。任务完成。
- 7. 在运行性能基准测试时对应用程序进行分析（Profile）。
- 8. 检查分析结果，找出最大的未优化的“性能热点”，即应用程序花费最时间的代码部分。
- 9. 再次检查分析结果，找出最大的未优化的“性能热点”，即应用程序花费最时间的代码部分。
- 10. 检查分析结果，找出最大的未优化的“性能热点”，即应用程序花费最时间的代码部分……（注：此处原文 OCR 存在大量重复和逻辑混乱，已根据要求精简并翻译核心逻辑)。

*(注：由于提供的英文文本在第 178.1 节的步骤 8 之后由于 OCR 错误存在大量的重复描述和逻辑循环，翻译部分已根据文档工程师的逻辑进行了去重处理，确保核心优化步骤清晰。)*

```xml
<plugin>

  <groupId>org.apache.maven.plugins</groupId>

  <artifactId>maven-shade-plugin</artifactId>

  <version>3.0.0</version>

  <executions>

    <execution>

      <phase>package</phase>

      <goals>

        <goal>shade</goal>

      </goals>

      <configuration>

        <finalName>benchmarks</finalName>

        <transformers>

          <transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">

            <mainClass>org.openjdk.jmh.Main</mainClass>

          </transformer>

        </transformers>

        <filters>

          <filter>

            <artifact>*:</artifact>

            <excludes>

              <exclude>META-INF/*.SF</exclude>

              <exclude>META-INF/*.DSA</exclude>

              <exclude>META-INF/*.RSA</exclude>

            </excludes>

          </filter>

        </filters>

      </configuration>

    </execution>

  </executions>

</plugin>
```

此之后需要编写基准测试类本身：

```java
package benchmark;

import org.openjdk.jmh.annotations.*; import org.openjdk.jmh.infra.Blackhole;
```

```java
import java.util.HashSet;

import java.util.Random;

import java.util.Set;

import java.util.concurrent.TimeUnit;
```

```java
@State(Scope.Thread)

public class CollectionFinderBenchmarkTest { private static final int SET_SIZE = 10000; private Set<String> hashSet; private Set<String> treeSet;

private String stringToFind = "8888";
```

```java
@Setup

public void setupCollections() { hashSet = new HashSet<>(SET_SIZE);

treeSet = new TreeSet<>();
```

```java
for (int i = 0; i < SET_SIZE; i++) { final String value = String.valueOf(i);

hashSet.add(value);

treeSet.add(value);
```

```java
}

stringToFind = String.valueOf(new Random().nextInt(SET_SIZE)); }
```

```java
@Benchmark

@BenchmarkMode(Mode.AverageTime)

@OutputTimeUnit(TimeUnit.NANOSECONDS)

public void testHashSetContains(Blackhole blackhole) {
```

```java
blackhole.consume(hashSet.contains(stringToFind)); }
```

```java
@Benchmark

@BenchmarkMode(Mode.AverageTime)

@OutputTimeUnit(TimeUnit.NANOSECONDS)

public void testSetContains(Blackhole blackhole) {
```

```java
blackhole.consume(treeSet.contains(stringToFind)); }
```

请记住这个 `blackhole.consume()`，我们稍后会回到它。此外，我们需要一个主类来运行基准测试：

```java
package benchmark; import org.openjdk.jmh.runner.Runner;

import org.openjdk.jmh.runner.RunnerException; import

org.openjdk.jmh.runner.options.Options; import

org.openjdk.jmh.runner.options.OptionsBuilder;
```

```java
public class BenchmarkMain

public static void main(String[] args) throws RunnerException { final

Options options = new OptionsBuilder
```

```java
.include(CollectionFinderBenchmarkTest.class.getSimpleName()).forks(1)

.build();
```

```java
new Runner(options).run();
}



一切就绪了。我们只需要运行`mvn package`（它将在你的`/target`文件夹中创建`benchmarks.jar`）并运行我们的基准测试：`java -cp target/benchmarks.jar benchmark.BenchmarkMain`。经过预热和计算迭代后，我们将得到结果：

# 运行完成。总耗时：00:01:21

| 基准测试模式 | 计数 | 评分 | 误差 | 单位 | 收集 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `CollectionBenchmarkTest.testHashSet` | avgt | 20 | 9940 ± 0.270 | ns/op | |
| `CollectionBenchmarkTest.testTreeSet` | avgt | 20 | 98858 ± 13.743 | ns/op | |

关于那个`blackhole.consume()`。如果你的计算没有更改应用程序的状态，java 极可能会忽略它。因此，为了让它生效，你可以让你的基准测试方法返回某个值，或者使用`Blackhole`对象来消耗它。

你可以在 Aleksey Shipiliev 的博客、Jacob Jenkov 的博客以及 java-performance 博客中找到更多关于编写正确基准测试的信息：1, 2。

# 第 180 章：上传文件到 AWS

使用 spring rest API 将文件上传到 AWS s3 桶。

# 第 180.1 节：上传文件到 s3 桶

我们将创建一个 rest API，它将从前端接收 multipart 参数作为文件对象，并将其上传到 S3。

# 第 181 章：AppDynamics 和 TIBCO BusinessWorks 实例化以便于集成

由于 AppDynamics 旨在提供衡量应用程序性能的方法，开发和交付（部署）应用程序的速度是确保 DevOps 工作成功的因素。使用 AppD 监控 TIBCO BW 应用通常简单且不耗时，但在部署大量应用程序时，快速实例化是关键。本指南介绍了如何对所有 BW 应用进行实例化，而无需在部署之前修改每个应用程序。

# 第 181.1 节：单步对所有 BW 应用进行实例化的示例

1. 定位并打开 TIBCO BW `bwengine.tra` 文件，通常位于`TIBCO_HOME/bw/5.12/bin/bwengine.tra`（Linux 环境）
2. 查找包含以下内容的行：
   `*** Common variables. Modify these only. ***`
3. 在该部分之后添加以下行：`tibco.deployment=%tibco.deployment%`

4. 转到文件末尾并添加（根据需要将`?`替换为您自己的值，或删除不相关的标记）：
```
java.extended.properties--
javaagent:/opt/appd/current/appagent/javaagent.jar
-Dappdynamics.http.proxyHost=? -Dappdynamics.http.proxyPort=?
-Dappdynamics.agent.applicationName=? -Dappdynamics.agent.nodeName=%tibco.deployment%
-Dappdynamics.controller.sslEnabled=? -Dappdynamics.controller.sslPort=?
-Dappdynamics.agent.logs.dir=? -Dappdynamics.agent.runtime.dir=?
-Dappdynamics.controller.hostName=? -Dappdynamics.controller.port=? -Dappdynamics.agent.accountAccessKey=?
```

5. 保存文件并重新部署。您的所有应用程序现在应该在部署时自动进行插桩。

## 附录 A：安装 Java（标准版）

本文档提供了在 Windows、Linux 和 macOS 上安装 Java 标准版的说明。

## A.1 节：在 Windows 上安装后设置 `%PATH%` 和 `%JAVA_HOME%`

假设条件：
已安装 Oracle JDK。
JDK 安装在默认目录下。

设置步骤：

1. 打开 Windows 资源管理器。
2. 在左侧导航窗格中点击“此电脑”（旧版本 Windows 中为“计算机”）。在实际的 Windows 版本中，有一种无需使用资源管理器的快捷方法：只需按`Win + Pause`。
3. 在新打开的控制面板窗口中，点击左上角的“高级系统设置”。这将打开“系统属性”窗口。

![](img/01cc8d6667542262308c820b3f5bd37b_1253_0.png)

或者，在“运行”（`Win + R`）中输入 Advanced（不区分大小写）并按回车。

4. 在系统属性的“高级”选项卡中，点击右下角的“环境变量...”按钮。

5. 点击“系统变量”中的“新建...”按钮，添加名为`JAVA_HOME`的新系统变量，值为 JDK 安装目录的路径。输入这些值后，点击确定。

![](img/01cc8d6667542262308c820b3f5bd37b_1253_1.png)

6. 向下滚动变量列表并选择`Path`变量。

7. **注意**：Windows 依赖`Path`来查找重要程序。如果删除了部分或全部内容，Windows 可能无法正常运行。必须修改它以允许 Windows 运行 JDK。在选中`Path`变量的情况下，点击“编辑...”按钮。在`Path`变量的开头添加`%JAVA_HOME%\bin;`。

最好添加到行开头，因为 Oracle 软件以前会在`Path`中注册它们自己的 Java 版本——如果它出现在 Oracle 声明之后，您的版本将被忽略。

## 检查工作

1. 点击“开始”，然后输入`cmd`并按回车打开命令提示符。

2. 在提示符中输入`javac -version`。如果成功，屏幕将打印出 JDK 版本。

注意：如果需要重试，请在检查工作之前关闭提示符。这将强制 Windows 获取新的`Path`版本。

## A.2 节：在 Linux 上安装 Java JDK

### 使用包管理器
大多数主流 Linux 发行版都可以使用包管理器安装 OpenJDK 或 Oracle 的 JDK 和/或 JRE 版本（可用选项取决于您的发行版）。

通常情况下，操作步骤是打开终端窗口并运行下所示命令。（假设您有足够的权限以 "root" 用户身份运行命令……这正是`sudo`命令的作用。如果没有，请咨询您的系统管理员。）

推荐使用包管理器，因为它（通常）更容易让您的 Java 安装保持最新状态。

**apt-get，Debian Linux 发行版（Ubuntu 等）**
以下指令将安装 Oracle Java 8：

```bash
$ sudo add-repository ppa:webupd8team/java
$ sudo apt-get update
$ sudo apt-get install oracle-java8-installer
```

注意：要自动设置 Java 8 环境变量，可以安装以下包：
`$ sudo apt-get install oracle-java8-set-default`

**创建 deb 文件**
如果您更喜欢从 Oracle 下载的`.tar.gz`文件自行创建`.deb`文件，请执行以下操作（假设您已将`.tar.gz`下载到`./jdk.tar.gz`）：

```bash
$ sudo apt-get install java-package # 默认仓库中可能不可用
```

```bash
$ make-jpkg ./<jdk>.tar.gz # 不应以 root 身份运行 
$ sudo dpkg -i *j2sdk*.deb
```

注意：这要求输入为 ".tar.gz" 文件。

**slackpkg，基于 Slack 的 Linux 发行版**
`sudo slapt-get install default-jdk`

**yum，RedHat, CentOS 等**
`sudo yum install java-1.8.0-openjdk-devel.x86_64`

**df, Fedora**
在最近的 Fedora 版本中，`yum`已被`dnf`取代。
`sudo dnf install java-1.8.0-openjdk-devel.x86_64`
在 Fedora 版本中，没有用于安装 Java 7 及更早版本的包。

**pacman，基于 Arch 的 Linux 发行版**
`sudo pacman -S jdk8-openjdk`
如果您以 root 用户运行，则不需要`sudo`。

**Gentoo Linux**
Gentoo Java 指南由 Gentoo 团队维护，并在 wiki 中包含了正确的包部分和 USE 标记。

**在 Redhat, CentOS, Fedora 上安装 JDK**
从 Oracle JDK 或 JRE `tar.gz`文件安装：

1. 从 Oracle Java 下载网站下载所需版本的 Oracle 压缩包（`.tar.gz`文件）。
2. 将目录更改到您想要安装的地方；
3. 解压压缩包；例如`txzvf jdk-8u67-linux-x64.tar.gz`。

从 Oracle RPM 文件安装：
1. 从 Oracle Java 下载网站获取所需版本的 RPM 文件。
2. 使用`rpm`命令安装。例如：`sudo rpm -ivh jdk-8u67-linux-x64.rpm`

## A.3 节：在 Linux 上安装 Java JDK

### 命令行切换
可以将函数添加到`~/.bash_profile`（如果您使用 Bash shell）以供以后使用：

```bash
function java_set {
if [[ $1 == "6" ]]
then
export JAVA_HOME='/usr/libexec/java_home -v 1.6'; echo "Setting Java to version 6..."
echo "$JAVA_HOME"
elif [[ $1 == "7" ]]
then
export JAVA_HOME='/usr/libexec/java_home -v 1.7'; echo "Setting Java to version 7..."
echo "$JAVA_HOME"
elif [[ $1 == "8" ]]
then
export JAVA_HOME='/usr/libexec/java_home -v 1.8'; echo "Setting Java to version 8..."
echo "$JAVA_HOME"
fi
}
```

### macOS Apple Java 6
在旧版本的 macOS（10.11 El Capitan 及之前）上，Apple 发布的 Java 6 是预装的。如果已安装，可以在此处找到：`/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home`。注意：Java 6 早已停止支持，建议升级到新版本。Oracle 网站上有关于重新安装 Apple Java 6 的更多信息。

## A.4 节：在 Windows 上安装 Java JDK 或 JRE

Windows 仅提供 Oracle JDK。安装过程非常简单：

1. 访问 Oracle Java 下载页面：
2. 点击 JDK、JRE 或 Server JRE 按钮。注意，使用 Java 进行开发需要 JDK。要了解 JDK 和 JRE 的区别，请查看此处。
3. 滚动到想要下载的版本。（通常建议使用最新版本。）
4. 点击“接受许可协议”按钮。
5. 下载 Windows x86 (32 位) 或 Windows x64 (64 位) 安装程序。
6. 按照 Windows 的正常方式运行安装程序。

使用命令提示符在 Windows 上安装 Java 的另一种方法是使用 Chocolatey：
1. 打开 cmd 窗口，例如按`Win + R`在“运行”窗口中输入`cmd`并按回车。
2. 在 cmd 窗口中，运行以下命令下载并安装 Java 8 JDK：

```
C:\> choco install jdk8
```

# 安装并运行便携版本

在某些情况下，你可能需要在权限限制的系统上安装 JDK/JRE，或者你可能想安装并使用多个版本或架构（x64/x86）的 JDK/JRE。在下载安装程序 (.EXE) 之前，步骤都是相同的。随后的步骤如下（这些步骤适用于 JDK/JRE 7，对于较旧版本，文件夹和文件的名称略有不同）：

1. 将文件移动到你希望永久存放 Java 二进制文件的适当位置。
2. 如果你的权限受限，请安装 7-Zip 或其便携版本。
3. 使用 7-Zip 将 Java 安装程序 EXE 中的文件解压到该位置。
4. 在资源管理器的文件夹中按住 Shift 键并右键点击以打开命令提示符，或从任何地方导航到该位置。
5. 导航到新创建的文件夹。假设文件夹名为`jdk-7u25-windows-x64`。因此输入`cd jdk-7u25-windows-x64`。然后输入以下命令：

```
cd .rsrc\JAVA_CAB10
extracc32 111
```

6. 这将在该位置创建一个`tools.zip`文件。使用 7-Zip 解压`tools.zip`，这样内部的文件现在就会创建在相同目录下的`tools`文件夹中。
7. 在已打开的命令提示符中执行这些命令：
```
cd tools
for /r %x in (*.pack) do \bin\unpack200 -r "%x" "%%%~dx%%~px%%~nxnx.jar"
```
8. 等待命令完成。将`tools`的内容复制到你希望存放二进制文件的位置。

通过这种方式，你可以同时安装你需要的任何版本的 JDK/JRE。原文帖子：http://stackoverflow.com/a/6571736/1448252

# A.5 节：使用 alternatives 在 Linux 上配置和切换 Java 版本

## 使用 Alternatives

许多 Linux 发行版使用`alternatives`命令在不同版本的命令之间切换。你可以用它来切换机器上安装的不同版本的 Java。

1. 在命令行 shell 中，将`$JDK`设置为新安装 JDK 的路径；例如：
2. 使用`alternatives --install`将 Java SDK 中的命令添加到 alternatives 中：

```
$ JDK=/Data/jdk1.8.0_67
```

```
$ sudo alternatives --install /usr/bin/java java $JDK/bin/java 2
$ sudo alternatives --install /usr/bin/javac javac $JDK/bin/javac 2
$ sudo alternatives --install /usr/bin/jar jar $JDK/bin/jar 2
```



以此类推。

现在，你可以如下在 Java 命令的不同版本之间切换：

```bash
$ sudo alternatives --config javac
```

当前有 1 个程序提供 `javac`。

## 选择命令

```bash
*+1 /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.101-1.b14.fc23.x86_64/bin/javac
2 /Data/jdk1.8.0_67/bin/javac
```

按回车保留当前选择，或输入选择编号：2

有关使用 `alternatives` 的更多信息，请参阅 `alternatives(8)` 手册。

## 基于 Arch 的安装

基于 Arch Linux 的安装附带 `archlinux-java` 命令用于切换 Java 版本。

### 列出已安装的环境

```bash
$ archlinux-java status
```

可用 Java 环境：`java-7-openjdk`（默认）`java-8-openjdk/jre`

### 切换当前环境

```bash
# archlinux-java set <JAVA_ENV_NAME>
```

例如：

```bash
# archlinux-java set java-8-openjdk/jre
```

可以在 Arch Linux Wiki 上找到更多信息。

## A.6 节：Java 开发需要什么

JDK 安装和一个文本编辑器是 Java 开发的最低配置。（如果有一个可以进行 Java 语法高亮的文本编辑器会很好，但不是必须的。）但对于严肃的开发工作，建议还要使用以下工具：

- Java IDE，如 Eclipse、IntelliJ IDEA 或 NetBeans
- 构建工具，如 Ant、Gradle 或 Maven
- 用于管理代码库的版本控制系统（带有适当的备份和异地复制）
- 测试工具和 CI（持续集成）工具

## A.7 节：选择合适的 Java SE 版本

自 1995 年发布原始 Java 1.0 以来，Java 发布了许多版本。（参考 Java 版本历史获取摘要。）然而，大多数版本已经过了它们的官方生命终点（End Of Life）。这意味着供应商（现在通常是 Oracle）已停止了该版本的新开发，不再为任何错误或安全问题提供/免费补丁。（对于有支持合同的人/组织通常可以获得私有补丁；请联系您的供应商销售办公室。）

通常情况下，推荐使用的 Java SE 版本是最新公共版本的最新更新。目前，这意味着最新的可用的 Java 8 发布版本。Java 9 将于 2017 年公开发布。（Java 7 已经过了生命周期，最后一次公开发布是在 2015 年 4 月。不建议使用 Java 7 及更早版本。）

此建议适用于所有新的 Java 开发以及任何学习 Java 的人。它也适用于只想运行第三方提供的 Java 软件的人。通常来说，编写良好的 Java 代码可以在较新的 Java 版本上运行。

## A.8 节：Java 版本的命名

自 1995 年发布原始 Java 1.0 以来，Java 发布了许多版本。（参考 Java 版本历史获取摘要。）然而，大多数版本已经过了它们的官方生命终点（End Of Life）。这意味着供应商（现在通常是 Oracle）已停止了该版本的新开发，不再为任何错误或安全问题提供/免费补丁。（对于有支持合同的人/组织通常可以获得私有补丁；请联系您的供应商销售办公室。）

通常情况下，推荐使用的 Java SE 版本是最新公共版本的最新更新。目前，这意味着最新的可用的 Java 8 发布版本。Java 9 将于 2017 年公开发布。（Java 7 已经过了生命周期，最后一次公开发布是在 2015 年 4 月。不建议使用 Java 7 及更早版本。）

此建议适用于所有新的 Java 开发以及任何学习 Java 的人。它也适用于只想运行第三方提供的 Java 软件的人。通常来说，编写良好的 Java 代码可以在较新的 Java 版本上运行。

## A.8 节：安装 JDK

| JDK 版本 | 市场名称 |
| :--- | :--- |
| 1.0 | JDK |
| 1.1 | JDK |
| 1.2 | JDK |
| 1.5 | SE |
| 1.6 | SE |
| 1.7 | SE |
| 1.8 | SE |
| 9 | SE |

Java 的命名似乎有些混淆。Java 8 的版本号通常是：`1.8.0_111-b14`。更新号 101 影响了构建 13。

## A.9 节：使用 tar 包安装 JDK

如果你有权限限制，按照以下步骤使用 tar 包安装 JDK：

1. 从此处下载 tar 包。
2. 你需要 sudo 权限：`sudo su`
3. 创建 jdk 目录：`mkdir /opt/jdk`
4. 将下载的 tar 包解压到此处：`tar -xzf jdk-85-linux-x64.tar.gz -C /opt/jdk`
5. 验证解压的文件：`ls /opt/jdk`
6. 设置 JDK 为默认：

```bash
alternatives --install /usr/bin/java java /opt/jdk/jdk1.8.0_05/bin/java
alternatives --install /usr/bin/javac javac /opt/jdk/jdk1.8.0_05/bin/javac
```

7. 检查 Java 版本：`java -version`

预期输出：

```bash
java version "1.8.0_111"
Java(TM) Runtime Environment (build 25.111-b14)
HotSpot(TM) 64-Bit Server VM (build 25.111, mixed mode)
```

## A.10 节：Linux 上的安装后检查和配置

安装 JDK 后，建议检查它是否可以使用。你可以通过使用普通用户账户运行以下命令来实现：

```bash
$ java -version
$ javac -version
```

这些命令会打印 shell 路径中 JRE 和 JDK 的版本信息。查找 JDK / JRE 版本字符串。

如果上述任何一个命令失败并提示“找不到命令”，则 JRE 或 JDK 不在路径中；请查看下文的“配置 PATH”。如果上述任何一个命令显示的版本与预期的不符，则说明你的路径或 `alternatives` 系统需要调整；请查看“检查 Alternatives”。如果显示了正确的版本，你已经完成了；请跳到“检查 JAVA_HOME”。

### 配置 PATH

如果目前路径中没有 `java` 或 `javac`，那么简单的解决方法是将它们加入路径。首先，找到你安装 Java 的位置；如果你有疑问，查看“Java 安装在哪里？”接下来，假设 `bash` 是你的命令行 shell，使用文本编辑器在 `~/.bash_profile` 或 `~/.bashrc` 的末尾添加以下行（如果你使用 Bash shell）：

```bash
JAVA_HOME=<安装目录>
PATH=$JAVA_HOME/bin:$PATH
export JAVA_HOME
export PATH
```

... 将 `<安装目录>` 替换为你的 Java 安装目录路径。

接下来，执行你刚刚编辑的文件，以更新当前 shell 的环境变量。

```bash
source ~/.bash_profile
```



接下来，重复 `java` 和 `jacav` 版本的检查。如果仍然存在问题，使用 `which java` 和 `which jacav` 来验证你是否已正确更新了环境变量。

最后，注销并重新登录，以便更新后的环境变量传播到你所有的 shell 中。现在你应该已经完成了。

## 检查替代方案

如果 `java -version` 或 `jacac -version` 运行但给出了意外的版本号，你需要检查这些命令源于何处。使用 `which` 和 `ls -l` 来查找此信息：

```
$ ls `which java`
```

如果输出看起来如下：

```
lrwxrxr-x 1 root root 22 Jul 30 22:18 /usr/bin/java -> /etc/alternatives/java
```

则说明正在使用替代（alternatives）版本切换。你需要决定是继续使用它，还是简单通过直接设置 `PATH` 来覆盖它。

在 Linux 上使用 alternatives 配置和切换 Java 版本，见上文的“直接配置 PATH”。

## Java 安装在何处？

Java 可以安装多个位置，取决于安装方法。

Oracle RPM 包将 Java 安装在 `/usr/java` 中。

在 Fedora 上，默认位置是 `/usr/lib/jvm`。

如果 Java 是通过 ZIP 或 JAR 文件手动安装的，则安装位置可能是任何地方。

如果你在查找安装目录遇到困难，我们建议你使用 `find`（或 `locate`）来查找命令。例如：

```
$ find / -name java -type f 2>/dev/null
```

这将为你提供系统中所有名为 `java` 的文件路径。（将标准错误重定向到 `/dev/null` 会抑制关于你无法访问的文件和目录的消息。）

## 附录 B：Java 版本、发布版本和发行版

### 第 B.1 节：Java SE JRE 或 Java JDK 区别

Sun / Oracle 发布的 Java SE 有两种形式：JRE 和 JDK。简单来说，JRE 支持运行 Java 程序，而 JDK 也支持 Java 开发。

### Java 运行时环境 (JRE)

Java 运行时环境或 JRE 发行版由运行和管理 Java 应用程序所需的库和工具组成。典型现代 JRE 中的工具包括：

- `java` 命令，用于在 JVM（Java 虚拟机）中运行 Java 程序
- `js` 命令，用于运行 Nashorn Javascript 引擎
- `keytool` 命令，用于操作 Java 密钥库
- `policytool` 命令，用于编辑沙箱安全策略
- `pack200` 和 `unpack200` 工具，用于 Web 部署的打包和解包“pack200”文件
- `keydb`、`registry` 和 `name` 命令，支持 CORBA 和 RMI 应用程序

“桌面 JRE”安装程序包含用于某些网络浏览器的 Java 插件。这被故意排除在“服务器 JRE”安装程序之外。从 Java 7 开始，JRE 安装程序包含了 JavaFX（2.2 或更高版本）。

### Java 开发工具包 (JDK)

Java 开发工具包或 JDK 发行版包含 JRE 工具以及用于开发 Java 软件的额外工具。额外工具通常包括：

- `javac` 命令，将 Java 源代码（`.java`）编译为字节码文件（`.class`）
- 用于创建 JAR 文件的工具，如用于运行 applet 的 `jar` 和 `jarsigner`
- `javviewer` 用于 JNI 存根
- `javascii` 用于字符集转换
- `javagen` Java 到 XML 架构生成器（JAXB 的一部分）
- 生成对象序列化字符串
- `wsgen` 和 `wsim` 支持 JAX-WS

诊断工具等，例如：

- `jdb` 基础 Java 调试器
- `jmap` 用于转储 Java 堆
- `jstack` 用于获取线程栈转储
- `javap` 用于检查 `.class` 文件

应用程序管理和监控工具，例如：

`jconsole`、`jstat` 和 `jps` 用于应用程序监控

典型的 Sun / Oracle JDK 安装还包含一个带有 Java 库源码的 ZIP 文件。Java 6 之前，这是唯一的可用源码。从 Java 6 开始，OpenJDK 的完整源代码可以从 OpenJDK 网站下载。它通常不包含在 (Linux) 软件包中，但可以作为一个独立的包提供。

## 第 B.2 节：Java SE 版本

下表提供了 Java SE 平台重大主要版本的时间线。

| Java SE 版本 | 代号 | 发布日期 | 寿命结束（免费） |
| :--- | :--- | :--- | :--- |
| Java SE 10 (早期访问) | 无 | 2018-03-20 (估计) | 未来 |
| Java SE 9 | 无 | 2017-07-27 | 未来 |
| Java SE 8 | Dolphin | 2014-03-18 | 未来 |
| Java SE 7 | Mustang | 2015-04-14 | 未来 |
| Java SE 6 | Mustang | 2011-07-28 | 未来 |
| Java SE 5 | Tiger | 2013-04-16 | 未来 |
| Java SE 4.2 | Mantis | 2006-12-23 | 未来 |
| Java SE 1.4 | Hopper | 2009-11-04 | 未来 |
| Java SE 1.4.1 | Grasshopper | 2004-10-04 | 未来 |
| Java SE 1.3 | Merlin | 2003-06-23 | 未来 |
| Java SE 1.3.1 | Ladybird | 2002-09-16 | 未来 |
| Java SE 1.2 | Kestrel | 2002-02 | 未来 |
| Java SE 1.1 | Playground | 2001-05 | 未来 |
| Java SE 1.0 | Oak | 1998-12 | 未来 |
| | | 1997-02 | 未来 |
| | | 1996-01 | 未来 |

脚注：

1. Oracle 网站上有对应版本的链接。
2. 许多旧版 Java 版本已过官方“寿命”日期。支持合同的客户仍可更新。

来源：Rudy Green 的 Canadian Mind Products

## Java 版本

| Java SE 版本 | Java 亮点 |
| :--- | :--- |
| Java SE 8 | Lambda 表达式和 MapReduce 风格。Nashorn Javascript 引擎。类型上的注解。新的日期和时间 API。JavaFX 启动器。移除 PermGen。 |
| Java SE 7 | 字符串切换、try-with-resource、菱运算符 (`<`)、数字字面量增强和异常处理。并发库增强。对原生文件系统的支持。Timsort。ECC 算法。改进的 2D 图形 (GPU) 支持。 |
| Java SE 6 | JVM 平台和 Swing 的性能增强。脚本语言 API。JDBC 4.0。编译器 API。JAXB 2.0。Web 服务支持 (JAX-WS)。 |
| Java SE 5 | 内存模型规范。Swing 和 RMI 增强。新增 `java.util.concurrent.*` 包和 `Scanner`。`assert` 关键字。正则表达式类。泛型、注解、自动箱、枚举类、可变参数、增强型循环和静态导入。 |
| Java SE 1.4 | Buffer 和 Channel。`java.util.logging.*` API。图像 I/O API。集成 XML 和 XSLT (JAXP)。集成安全加密 (JCE, JSSE, JAAS)。集成 Java Web Start。首选项 API。 |
| Java SE 1.3 | 包括 HotSpot JVM。CORBA / RMI 集成。Java 命名和目录接口 (JPDA)。JavaSound API。代理 API。 |
| Java SE 1.2 | `strict` 关键字。Swing API。网络浏览器的 Java 插件。CORBA 互操作性。集合框架。 |
| Java SE 1.1 | 内部类。反射。JDBC。RMI。Unicode / 字符流。国际化支持。AWT 事件模型改进。JavaBeans。 |

来源：维基百科：Java 版本历史

### 第 B.3 节：Java EE、Java SE、Java ME 和 JavaFX 的区别

Java 技术既是一种编程语言也是一个平台。Java 编程语言是一种高级面向对象的语言，具有特定的语法和风格。Java 平台是运行 Java 编程语言应用程序的特定环境。

有多个 Java 平台。许多开发者即使是资深的 Java 编程语言开发者，也不理解不同的平台之间相互关联。

## Java 编程语言平台

Java 编程语言有四个平台：

- Java 标准版 (Java SE)
- Java 企业版 (Java EE)
- Java 微型版 (Java ME)
- Java FX

所有 Java 平台都由一个 Java 虚拟机 (VM/VM) 和一个应用程序接口 (API) 组成。Java 虚拟机是一个针对特定硬件和软件平台运行 Java 技术应用程序的程序。API 是一系列软件组件的集合，你可以使用它们来创建其他软件组件或应用程序。每个 Java 平台都提供一个虚拟机和一个 API，这使得编写在任何兼容系统上运行的应用程序都拥有的 Java 编程语言的所有优势：平台无关性、强大性、稳定性、易于开发和安全性。

## Java SE

当大多数人想到的 Java 编程语言时，他们想的是 Java SE API。Java SE 的 API 提供了 Java 编程语言的核心功能。它定义了从 Java 编程语言的基本类型和对象到用于网络、安全、数据库访问、图形用户界面 (GUI) 开发和 XML 解析的高级类的所有内容。

除了核心 API 之外，Java SE 平台还由虚拟机、开发工具、部署技术以及在 Java 技术应用程序中常用的其他类库和工具包组成。

## Java EE

Java EE 平台构建在 Java SE 平台之上。Java EE 平台为开发和运行大型、多层、可扩展、可靠且安全的网络应用程序提供了 API 和运行时环境。

## Java ME

Java ME 平台提供了一个 API 和一个轻量级虚拟机，用于在手机等小型设备上运行 Java 编程语言应用程序。该 API 是 Java SE API 的子集，以及用于小型设备应用程序开发的特殊类库。Java ME 应用程序通常是 Java EE 平台服务的客户端。

## Java FX

Java FX 技术是一个用于使用 Java Script 编写富网络应用程序的平台。Java 是一种静态类型的声明式语言，它被编译为 Java 技术字节码，然后可以在 Java VM 上运行。为 Java FX 平台编写的应用程序可以包含并链接到 Java 编程语言类，并可能是 Java EE 平台服务的客户端。

取自 Oracle 文档

## 附录 C：类路径 (Classpath)

Classpath 列出了 Java 运行时查找类和资源的地方。Classpath 同样被 Java 编译器用于查找以前编译的外部依赖项。

### C.1 节：指定类路径的不同方法

设置类路径有三种方法。

1. 可以使用 `CLASSPATH` 环境变量设置：

```
set CLASSPATH=... # Windows 和 csh
export CLASSPATH=... # Unix sh/bash
```

2. 可以在命令行中如下设置：

```
java -classpath ... 
javac -classpath ... 
```

注意，`-classpath`（或 `-cp`）选项的优先级高于 `CLASSPATH` 环境变量。

3. 可执行 JAR 文件的类路径使用 `MANIFEST.MF` 中的 `Class-Path` 元素进行指定：

```
Class-Path: jar1-name jar2-name directory-name/jar3-name
```

注意，这仅在 JAR 文件按如下方式执行时才有效：

```
java -jar some.jar ...
```

在这种执行模式下，`-classpath` 选项和 `CLASSPATH` 环境变量将被忽略，即使 JAR 文件没有 `Class-Path` 元素。

如果没有指定类路径，在使用 `java -jar` 时，默认类路径为所选 JAR 文件，否则则为当前目录。

相关链接：

- https://docs.oracle.com/javase/tutorial/deployment/jar/downman.html
- https://docs.oracle.com/javase/7/docs/notes/tools/windows/classpath.html

### C.2 节：将目录下的所有 JAR 添加到类路径

如果你想将目录中的所有 JAR 添加到类路径，可以使用类路径通配符语法简洁地完成；例如：

```
someFolder/*
```

这告诉 JVM 在 `someFolder` 中查找所有文件。

这种语法可以用于 `-classpath` 参数、`CLASSPATH` 环境变量或 JAR 文件中的 `Class-Path` 属性。要将目录中的所有 JAR 添加到类路径，可以使用类路径通配符语法。

注意：

1. 类路径通配符是在 Java 6 中引入的。
2. `someFolder/*.jar` 不视为通配符。
3. 通配符只匹配带后缀的 JAR。
4. 通配符匹配目录中的文件。
5. 当类路径在 JAR 文件中指定时，会忽略其他 JAR 文件。

### C.3 节：从类路径加载资源

从类路径加载资源（图像、属性文件、密钥库等）是很有用的。为了此目的，我们可以使用类加载器。

假设我们有如下结构：

```
program.jar

-com

  -project

    -file.txt

-Test.class
```

并且我们要从类路径访问 `file.txt`。我们可以通过类加载器来实现：

```
is = Test.class.getResourceAsStream("com/project/file.txt")
```

或者，我们也可以直接请求类对象：

```
is = Test.class.getResourceAsStream("file.txt")
```

使用类加载器，对于位于 `com.package` 的类，我们不需要指定任何路径。但是，我们可以使用绝对路径，如下所示：

```
is = Test.class.getResourceAsStream("/file.txt")
```



## C.4 节：路径语法

类路径是目录路径、JAR 或 ZIP 文件指定的序列。

对于在命令行（例如 `-classpath`）或作为环境变量指定的类路径，条目之间在 Windows 上使用分号（`;`），在其他平台（Linux、UNIX 等）使用冒号（`:`）。

对于 JAR 文件中 `MANIFEST.MF` 的 `Class-Path` 元素，使用单个空格分隔条目。

有时需要在类路径条目中嵌入空格。当在命令行指定类路径时，只需使用 shell 引号。

```
export CLASPATH="home/user/My JAR Files/foo.jar:second.jar"
```

（细节取决于你使用的命令行 shell。）

当类路径在 JAR 文件的 `MANIFEST.MF` 文件指定时，必须使用 URL 编码。

```
Class-Path: /home/user/My%20JAR%20Files/foo.jar second.jar
```

## C.5 节：动态类路径

有时，仅仅从文件夹添加所有 JAR 是不够的，例如当你需要原生代码并选择 JAR 子集时。这时你需要两个 `main` 方法。第一个方法构建类加载器，然后使用该类加载器调用第二个 `main` 方法。

这是一个示例，它选择了适用于平台的 SWT 原生 JAR，添加了应用程序的所有 JAR，然后调用真正的 `main` 方法：

- 创建平台 Java SWT

## C.6 节：类名到路径名的映射

标准 Java 工具链（以及设计用于与之交互的第三方工具）具有将类名映射到表示它们的文件和其他资源的路径名的特定规则。

映射如下：

- 对于默认包中的类，路径是简单的文件名。
- 对于命名包中的类，包名组件映射到目录。
- 对于命名的嵌套类和内部类，文件名部分通过 `$` 字符连接类名形成。
- 对于匿名内部类，使用数字来代替名称。

下表所示：

| 类名 | `SomeClass` |
| :--- | :--- |
| `com.example.SomeClass` | `SomeClass.Inner` |
| 源文件路径 (Source pathname) | `SomeClass.java` |
| 类文件路径 (Classfile pathname) | `SomeClass.class` |
| `SomeClass` 匿名内部类（在 `SomeClass.java` 中） | `com/example/SomeClass.java` `com/example/SomeClass.class`（in `SomeClass.java`） `SomeClass$Inner.class` |
| `SomeClass$1.class`, `SomeClass$2.class` 等 | |

## C.7 节：引导类路径 (The bootstrap classpath)

标准的 Java 类加载器在检查扩展路径和应用程序类路径之前，首先在引导类路径中查找类。默认情况下，引导类路径由 `rt.jar` 文件和 JRE 安装提供的其他重要 JAR 文件组成。它们提供了标准 Java SE 类库中的所有类，以及各种“内部”实现类。

在通常情况下，你不需要担心这个问题。默认情况下，`java`、`javac` 等命令将使用适当版本的运行时库。

极少数情况下，必须通过使用标准库中的替代类来覆盖 Java 运行时的正常行为。例如，你可能会在运行时库中遇到无法通过正常手段规避的“致命性（show stopper）”错误。在这种情况下，可以创建一个包含修改后的类的 JAR 文件，然后将其添加到启动 JVM 的引导类路径中。

`java` 命令提供了以下用于修改引导类路径的 `-X` 选项：

- `-Xbootclasspath:<path>` 用提供的路径替换当前的引导类路径。
- `-Xbootclasspath/a: <path>` 将提供的路径附加到当前类路径的末尾。
- `-Xbootclasspath/p: <path>` 将提供的路径插入到当前类路径的开头。

请注意，当使用 `bootclasspath` 选项替换或覆盖 Java 类（等）时，从技术上讲你正在修改 Java。如果你随后分发你的代码，可能会涉及许可问题。（请参阅 Java Binary License ... 的条款和条件……并咨询律师。）

## C.8 节：类路径的含义：搜索是如何运作的

类路径（`classpath`）的目的是告诉 JVM 在哪里寻找类和其他资源。类路径的含义与搜索过程是相互交织的。

类路径是搜索路径的一种，它指定了查找资源的序列位置。在标准类路径中，这些位置可以是主机文件系统中的目录、JAR 文件或 ZIP 文件。在每种情况下，该位置都是将要搜索的命名空间根目录的位置。

在类路径上搜索类的标准程序如下：

1. 将类名映射到相对类文件路径 `RP`。类名到类文件名的映射在其他地方描述。
2. 对于类路径中的每个条目 `E`：
   - 如果该条目是文件系统目录：
     - 相对于 `E` 解析 `RP`，以得到绝对路径 `AP`。
     - 测试 `AP` 是否为某个现有文件的路径。
     - 如果是，则从该文件加载类。
   - 如果该条目是 JAR 或 ZIP 文件：
     - 在 JAR / ZIP 文件的索引中查找 `RP`。
     - 如果对应的 JAR / ZIP 文件条目存在，则从该条目加载类。

在类路径上搜索资源的程序取决于资源路径是绝对的还是相对的。对于绝对资源路径，程序如上所述。对于使用 `Class.getResource` 或 `Class.getResourceAsStream` 解析的相对资源路径，类包的路径将附加到搜索之前。

（注意：这些是标准 Java 类加载器实现的程序。自定义类加载器可能会执行不同的搜索。）

## D 目录：资源（在类路径上）

Java 允许检索存储在 JAR 内部并与编译类并存的文件型资源。本主题重点关注加载这些资源并让你的代码可用。

## D.1 节：加载资源

Java 允许检索存储在 JAR 内部与编译类并存的文件型资源。本主题重点关注加载这些资源并让你的代码可用。

## D.2 节：从资源加载图像

为了从资源加载图像，通常使用：

```java
package example;

import java.io.IOException;
import java.net.URL;

public class ImageApplication {

    public Image getImage() throws IOException {
        URL imageURL = ImageApplication.class.getResource("icon.png");
        return ImageIO.read(imageURL);
    }
}
```

## D.3 节：在类路径上搜索资源

搜索程序取决于资源路径是绝对的还是相对的。对于绝对资源路径，程序如上所述。对于使用 `Class.getResource` 或 `Class.getResourceAsStream` 解析的相对资源路径，类包的路径将附加到搜索之前。

（注意：这些是标准 Java 类加载器实现的程序。自定义类加载器可能会执行不同的搜索。）

## D.4 节：从多个 JAR 加载同名资源

相同路径和相同的资源可能存在类路径上的多个 JAR 文件中。常见情况是遵循约定或属于打包规范的资源。

为了访问所有这些资源，必须使用类加载器，它有一个方法可以实现这一点。枚举可以方便地转换为列表。

```java
Enumeration<URL> resEnum = MyClass.class.getClassLoader().getResources("META-INF/MANIFEST.MF");
ArrayList<URL> list(resEnum);
```



2020年1月，在瑞士达沃斯由邪教控制的世界经济论坛上，在他对全球“威权主义统治者”进行“严厉批评”后。你只能对这种厚颜无耻的谎言付笑。他竟然不笑真是个谜。将奥威尔式的“自由价值观和反对不容忍”翻译过来，意味着教导非白人恨白人，让白人因为出生为白人而讨厌自己。其中的原因将会变得明白。

## “反犹太主义”骗局

锡太主义者支持巴勒斯坦土地上的犹太祖国，这长期以来一直是萨巴特-罗斯柴尔家族的目标，但并非为了犹太人的利益。萨巴特人及其全球反犹太主义产业扭曲了公众和政治观点，将反对锡太主义的暴力极端主义等同于对所有犹太人的全面攻击和谴责。这不过是萨巴特人的保护敲诈，旨在阻止对他们计划和活动的合法调查与曝光。“反犹太主义”的官方定义最近扩大到包括对锡太主义（一种政治运动）的批评，这样做是为了进一步暴露在19世纪创造了我们今天所知的锡太主义的萨巴特渗透者。

“叛逆者”会在知道即将面临的烂事时才会谈论这些话题。人们必须决定是想知道真相，还是仅仅躲在对他人言论的恐惧角落。自20世纪90年代以来，萨巴特人一直试图标记我为“反犹太主义者”，因为我揭露了越来越多关于他们的背景和计划。那些无用、胆小、欺诈的“记者”只是毫无疑问地重复这些抹黑；在我写这一章节的当天，两个毫无疑问的复读机本·奎恩（Ben Quinn）和阿奇·布兰德（Archie Bland，多么得当）在体制内的宣传报纸《伦敦卫报》上直言地称我为“反犹太主义者”，没有任何证据支持。

萨巴特反犹太主义产业是这么说的，他们又有什么样的质疑呢？他们不敢。讽刺的是，“塞米特”（Semitic）指的是中东的一组语言，几乎全是阿拉伯语。“反犹太主义”变成了“反阿拉伯人主义”，如果这种误解的后果不是那么严重，那将是滑稽的。

别麻烦奎恩和布兰德了。我不想让他们困惑，愿保佑他们吧。我在20世纪90年代写下我被贴上“反犹太主义”标签的原因之一是，犹太特工人员（萨巴特人）在萨巴特人推翻俄罗斯王朝时，深度参与了俄国革命。这显然让我成了“反犹太主义者”。噢，真的吗？这里是节录自《触发器》（*The Trigger*）的一个章节：

英国记者罗伯特·威尔尔顿（Robert Wilton）在他1920年的书籍《罗曼诺夫王朝的末日》中证实了这些主题，他研究了俄罗斯政府的官方文件，以确定1917年至1919年布尔什维克精英的成员。中央委员会的62名成员中包括41名犹太人；人民委员委员会的22名成员中有17名是犹太人；在1918年至1919年间556名最重要的布尔什维克领导人中，有458人被犹太人占据。只有17人是俄罗斯人。此外，在1917年建立的切卡（Cheka）秘密警察中也有23名犹太人，他们随后再次出现在各地。

牛津大学的罗伯特·瑟维斯（Robert Service）教授是20世纪俄罗斯历史专家，他发现证据表明，“犹太”列昂·托洛茨基曾确保犹太人加入红军，并在苏联文官机构中占不成比例的多数，其中包括切卡，切卡对许多“人民的敌人”进行了逮捕、监禁和处决。美国国务院一份日期为1918年11月13日的十进制文件（861.00/5339）列出了[在美的罗斯柴尔德银行代理]雅各布·希夫（Jacob Schiff）和一份极端锡太主义者名单作为俄国革命的资助者。

此外，主要的灵感和驱动力来自犹太领导人。因此，纯俄罗斯人的齐切琴（Tchicherin）被其名义下属利特文夫（Litvinoff）所掩盖，而布哈林林（Bukharin）或卢纳斯基基（Lunarski）等俄罗斯人的影响无法与托洛茨基（Trotsky）、或作为红星堡垒独裁者的齐诺杰维夫（Zinoviev）、或克拉辛（Krassin）或拉德克（Radek）——全都是犹太人的力量相比。在苏联机构中，犹太人的主导地位更加令人震惊。在反革命特别委员会实施的恐怖体制中，突出的部分——如果不是主要的——是由犹太人承担的。

英国的丘尔尔（Churchill）无论是无意还是故意犯了同样的错误。他在1920年的《插图周日报》（*Illustrated Sunday Herald*）上写道，俄国革命背后的人是一场为了推翻文明并基于停滞的发展、嫉妒的恶意和不可能的平等来重组社会的全球阴谋（今天由同一网络创造的“觉醒”）。丘尔尔说，没有必要夸大布尔什维克主义的创造以及在引发俄国革命中所起的作用，“通过这些国际性的且大部分是无神犹太人”[“无神犹太人” = 萨巴特人]。丘尔尔说，这无疑是一个巨大的，而且可能超过了其他所有：“除了列宁的显著例外外，领导人物大多数是犹太人。”

通过一个全球组织网络听命于撒巴提人（Sabbatian）创建并控制的跨全球情报网络，该网络涉及一个惊人的军事情报人员和行动网络，服务于一个仅有九百万人口的小型国家。其中包括一些犹太人资产，他们并非撒巴提人，但被他们说服认为自己所做的一切是为了以色列和犹太社区的利益，保护他们免受他们从小就被灌输相信的仇犹世界的侵害。

犹太社区只是一个极便于掩盖撒巴提人真面目的幌。任何接近揭露他们游戏的人都会撒巴提爪指指责“反犹太主义”，并声称所有犹太人都是企图统治世界的一部分。我不是这么说的。我说的是撒巴提人——真正的犹太人恨者——渗透了犹太社区，将他们既作为掩护，又作为防止暴露的“反犹太主义”防御。

因此，我们有了这种针对研究人员的反犹太主义产业，而大多数犹太人认为这是合理且真实的。他们不知道他们的“犹太人”领导人以及国家、情报和军事机构根本不是由犹太人控制的，而是撒巴提法兰克主义的邪教徒和傀儡。我曾在一个支持犹太人的在线自由运动上签了名，当我下次查看时，我的名字消失了，且愿书简介中被添加了文字攻击我是一个“反犹太主义者”，这种感知编程的规模是如此巨大。

## 转向美国

我在《触发器》（*The Trigger*）中以及一个名为“横跨大西洋”（Atlantic Crossing）的章节讲述了，特别是以色列成立后，撒巴提人如何进入美国，并最终控制了政府行政、通过民主党和共和党控制的政治体系、像CIA和国家安全局（NSA）这样的情报机构、五角大楼以及大众媒体。

通过这个高度分化的网络，撒巴提人及其在摩萨德（Mossad）、以色列国防军（IDF）和美国机构机构的特工策划了9/11事件，并将其归咎于19名“基地组织劫持者”，这些劫持者大多来自或联系到撒巴提人统治的沙特阿拉伯。

这“19个人”甚至并非独自在飞机上——他们驾驶那些大型客机撞向建筑，而他们在驾驶单发动机轻型飞机方面却极其无能。据说，“劫持者”汉尼·汉朱（Hani Hanjou）驾驶美国航空77号航班飞向五角大楼，其转弯和操作大多数专业飞行员表示他们都难以做到；而就在短短六周前，他还在马里兰州鲍伊（Bowie）高速公路机场的教练因他是一个无能的飞行员为由被禁止租一架小飞机。

世界上犹太人口仅占总人口的0.2%，几乎完全集中在以色列（75%）和美国（约2%）。这2%和全球的0.2%指的是犹太人，而不是撒巴提入侵者，后者仅是这部分人的极小比例。

当你考虑到这个小国以色列的国际事务，以及2000年9月公布的《新美国世纪计划》（PNAC）时，这是一个令人警醒的想法，该计划为美国的反恐战争以及伊拉克、利比亚和叙利亚的政权更迭制定了蓝图，被称为“新保守派”（Neocons）的撒巴提人创立并主导。该文件承认，如果没有对美国本土发动重大攻击，并利用“问题-反应-解决方案”的借口派遣部队横跨中东，这一计划将在政治或公开上获得支持。

撒巴提新保守派说：

> [转型]的过程……[战争和政权更迭]……可能是一个长的过程，除非发生某些灾难性和催化性事件——如新的珍珠港。

四个月后，产生该文件的许多人与他们来自长期撒巴提布什家族的愚蠢傀儡乔治·布什一起上台。他们中包括官方上的副总统，但实际上是整个“布什”政府的实际总统。

在布什就职九个月后，发生了布什当时所谓的“21世纪的珍珠港”，按照典型的撒巴提式时机和象征意义，2001年是1941年日本空军袭击夏威夷珍珠港事件的60周年，这让弗兰克林·德拉诺·罗斯福总统带领美国进入了一场由撒巴提人挑起的第二次世界大战，而他在竞选活动中曾说绝不会这样做。

证据充分表明，罗斯福及其军事和情报网络早已知道袭击即将到来，但没有采取任何行动阻止，而是确保了美国最关键的海军当时不在夏威夷。三千名美国人在珍珠港袭击中丧生，正如9月11日一样。

到2001年9/11时，撒巴提人已广泛渗透进美国政府、军事和情报行动，并利用其分化的资产策划了“基地组织”袭击。如果你阅读《触发器》，你会大震惊地发现，在袭击之前、期间和之后，政治、安全、法律、执法、金融和商业权力的关键职位上，“犹太人”特工（撒巴提渗透者）的集中程度极其惊人，他们让袭击发生、执行袭击并掩盖痕迹——我的意思是，当你考虑到全球人口的0.2%和美国人的2%是犹太人时，这种程度是惊人的，而撒巴提渗透者又是这比例中的极小部分。

9/11阴谋论的核心基石是通过以色列（撒巴提人）“网络安全”软件实现的“后门”访问，实时劫持了政府、军事、空军和情报计算机系统。撒巴提人控制的以色列正走向主导网络空间方面 rival rival 硅谷，并正成为网络安全领域的主导力量，这使他们能够访问全球计算机系统及其密码。

再加上（官方上）由犹太主义者领导的硅谷巨头，如谷歌（拉里·佩奇和谢尔盖·布林）、谷歌拥有的YouTube（苏珊·沃杰西斯基）、Facebook（马克·扎克伯格和桑德伯格）以及苹果（亚瑟·D·莱文森）。是否有人还在奇怪为什么这些人人和公司会严厉地封锁和禁止像我这样揭露邪教议程、尤其是关于撒巴提人策划的“新冠”骗局真相的人？

爱普斯斯坦性恋集团是一个撒巴提人的行动。他官方上是犹太人，但他是撒巴提人，被该团子虐待的女性告诉我，其中涉及大量的“犹太人”。爱普斯斯坦恐怖活动充满了撒巴提人的特征，完全符合他们的行事手段以及对性与仪式的痴迷。

随着一名前摩萨德特工的确认，一个商业帝国正在崩溃（参见《触发》）。

# 钱，钱，钱，假钱……

在我阐述萨巴特与最后三任美国总统之间的联系之前，我将先阐述控制银行和金融对萨巴特人至关重要的意义。萨巴特人梅耶·阿姆舍尔·罗斯柴尔在其家族追求全球完全控制的过程中，致力于主宰这一领域。

什么是自由？本质上，它是选择。你的选择越多，你就越自由；选择越少，你就越像被奴隶。在萨巴特人几个世纪创造的全球结构中，最大的债权人和选择限制者就是……钱。

在全球范围内，如果你问人们想对生活做什么以及为什么不这么做，他们会回答“我没钱”。这就是核心思想。一个由数十亿富翁组成的全球精英是“贪婪”的，这在某个层面上是真的；但对金钱的控制——谁拥有，谁没有——主要不是为了贪婪，而是为了控制。

萨巴特人夺取了越来越多的金融控制权，并从民众手中吸走了世界的财富。我们现在谈论的是“百分一”，即便如此，最富有的这些人也比这少得多。

这之所以可能，是因为一种极其荒谬且庞大的货币骗局，它可以被称为“骗局之王”，其基础是凭空创造“钱”并向民众“出借”带息的贷款。凭空产生的钱被称为“信用”。

萨巴特人在几个世纪里越来越完全地主张了对政府和银行的控制，并确保了金融法律，允许银行贷款的金额远大于其存款，这是一个被称为“部分准备金贷款”的信任骗术。

想象一下，如果你可以借出不存在的钱，并向接收者收取利息，你会进监狱。相比之下，银行家的结局是豪宅、私人喷气飞机、马里布和摩纳哥。

银行只需要在金库中保留一小部分存款和财富，并被允许贷款他们没有的“钱”，这被称为“信用”。去银行贷款，如果你成功了，银行家不会将任何真实财富转入你的账户。他们会在你的账户中输入约定的“贷款”金额——比如10,000英镑。

这并非真实存在的财富；它是不存在的、空气的、凭空产生的“信用”，除了理论之外，它从未、现在不、永远不会存在。信用除了风之外没有任何支撑，它之所以具有购买力，是因为人们认为它具有购买力，并接受它来交换财产、商品和服务。

我曾描述过这种情况，就像你看到的那些互相追逐的卡通人物，当他们跑到悬崖边缘时，在空气中向前跑，直到其中一个低头看，意识到发生了什么，然后他们全部坠落了深渊。

萨巴特金融体系的整个根基就是防止人们向下看，除非在他们想要崩溃系统的周期性时刻（如2008年和正在进行的2020年），并从借款人为了换取“空气贷款”而作为“抵押品”转让的所有财产、企业和财富中获得回报。

大多数人认为，钱在出现之初是由政府创造的，实际上它从一开始就以通过银行“出借”（被称为信用）而产生的债务形式存在。是的，流通货币本身从第一天起就是一种作为带息贷款发行的债务。

为什么政府不创造无息贷款呢？因为政府受萨巴特人控制，金融系统将变成一个成真的噩梦。

萨巴特人通过其全球央行网络支撑着他们的金融统治，其中包括私有化的美国联邦储备银行和英国英格兰银行，而这由一个私有的全球中央银行协调机构——即位于瑞士巴塞尔的国际结算银行进行协调，该机构是由包括洛克基菲勒家族和罗斯柴尔德家族在内的惯常份子创建的。

央行行长不对政府或人民负责。他们对国际结算银行负责，或者说，对全球崇教负责，而这个崇教如今由萨巴特人主导。

# 内置的灾难

在整个银行骗局中存在许多组成性骗局。当你借出一笔虚空信用贷款时，理论上只有这笔贷款的金额会被带入流通增加流通量；但你必须偿还本金和利息。

额外的利息并没有被创造，这意味着每一笔“贷款”，流通资金在借入金额与必须偿还金额之间都存在缺口。流通资金从未多到偿还所有未付的公共和私人债务（包括利息）。

冷酷编织在系统架构中的确定性是：某些人将为银行“贷款人”失去他们的房屋、企业和财产。

在“繁荣”时期，这一点并不明显，因为流通资金（以及债务）正随着更多人想要并获得贷款而扩张。当低退来临，货币供应收缩时，变得痛苦地明显：没有足够的资金支付所有债务和利息。

萨巴特银行家一直引导人类经历一系列精心策划的繁荣（产生更多债务）和崩盘（当债务无法偿还时，银行用不存在的“信用”换取债务人的实物财富）。在每一次“崩盘”中，萨巴特银行家都吸收了更多的世界实体财富，最终产生了“百分一”。

政府正处于破产水平，“美国中央银行”是私有的，美国总统仅在名义上是其主席。事实并非如此。“美联储”是由私有银行组成的卡特，在2008年崩盘后向其关联方处理了数十亿美元，并从1913年被操纵建立以来一直受萨巴特人控制，通过罗斯柴尔德的银行代理人雅各布·希夫和保尔·华堡的秘密诡计，以及洛克基菲勒家族。

由于仅占人口2%的犹太裔入侵者在1987年至2018年间领导了联邦储备银行31年，他们分别是艾伦·格林斯潘、本内德·伯南基和珍内特·耶伦（现任拜登财政部长），耶伦的副主席是美以双重国斯坦利·菲舍尔，曾任以色列银行行长。

央行行长跨越了罗纳德·里根（共和党）、老乔治·布什（共和党）、比尔·克林顿（民主党）、小乔治·布什（共和党）和巴拉克·奥巴马（民主党）的任期。

我们还应该加上格林斯潘之前的主席保尔·沃尔克尔，他由吉米·卡特（民主党）任命，在1979年至1987年间的卡特和里根政府期间执掌联邦联储。沃尔克尔是罗斯柴尔德家族长期的联系人和业务伙伴。

无论执政的是哪党“政党”，美国经济都由同一种力量引导。以下是奥巴马、特朗普和拜登政府的成员，看看你是否能看出共同的主题。

# 巴拉克·奥巴马（民主党）

极右/极端犹太人罗伯特·鲁宾、拉里·萨默斯和提摩西·盖茨纳在克林顿政府中担任过美国财政部长，其中两人再次出现在奥巴马身边。

极端犹太人美联储行长艾伦·格林斯潘通过去监管操纵了2008年的崩盘，并在灾难发生前辞职，让位于极端犹太人本内德·伯南基向萨巴特的“大不能倒”的银行和企业发放了数万亿美元，其中包括无处不在的极端犹太人高盛银行，该公司与全球政府的主要金融职位之间存在持续的人员旋转门运作。

奥巴马在2009年1月就职时继承了崩盘的遗留，幸运的是他得到了极端犹太人白宫办公厅主任拉姆·埃曼纽尔的支持，其父亲是1948年帮助轰炸出以色列的恐怖分子；并得到了他的极端犹太人高级顾问大卫·阿克斯罗德的支持，他是奥巴马两次竞选的首席策略师。

成功的总统竞选。埃曼纽尔（后后担任芝加哥市长，比尔·克林顿的前任高级募捐和战略家）是以色列建立后撒巴提（Sabbatian）政策的例子，即将内部家族迁移到美国，以便他们的孩子能成为美国公民。

“奥巴马”在其执政期间选择了这个金融团队来应对由撒巴提引发的危机：

- 蒂莫西·盖斯特纳（Timothy Geithner，极端犹太主义者），财政部长；
- 雅各布·J·刘（Jacob J. Lew），财政部长；
- 拉里·萨默斯（Larry Summers，极端犹太主义者），白宫国家经济委员会主任；
- 保罗·沃尔克尔（Paul Volcker，罗斯柴尔德商业伙伴），经济复苏顾问委员会主席；
- 彼得·奥尔萨格（Peter Orszag，极端犹太主义者），管理和预算局局长，负责所有政府支出；
- 佩尼·普利茨克（Penny Pritzker，极端犹太主义者），商务部长；
- 贾雷德·伯恩斯坦（Jared Bernstein，极端犹太主义者），副总统乔·拜登的首席经济学家和经济顾问；
- 玛丽·沙普罗（Mary Schapiro，极端犹太主义者），证券交易委员会（SEC）主席；
- 盖里·格森斯勒（Gary Gensler，极端犹太主义者），商品期货交易委员会（CFTC）主席；
- 希拉拉·拜尔（Sheila Bair，极端犹太主义者），联邦存款保险公司（FDIC）主席；
- 凯伦·米尔斯（Karen Mills，极端犹太主义者），小企业管理局（SBA）负责人；
- 肯尼思·费恩伯格（Kenneth Feinberg，极端犹太主义者），行政（救助）补偿特别专员。

费恩伯格被任命监督对（带有附带条件的）9/11受害者及其家属的补偿，其目的是在该活动中阻止他们通过庭审来质疑官方说法。

与此同时，极端犹太主义者伯尔纳德·伯南基（Bernard Bernanke）担任联邦储备委员会主席，而这些只是奥巴马政府中少数效忠于撒巴提控制的以色列的极端犹太主义者。奥巴马最大的企业捐赠者是极端犹太主义者高盛，该银行在其政府中雇用了许多人。

## 唐纳德·特朗普（“共和党”）

特朗普声称自己是一个局外人（他并非如此），是来“排沼”的。他实现这一目标的方法是立即任命极端犹太主义者斯蒂夫·曼努钦（Steve Mnuchin，高盛工作了17年的员工）担任他的财政部长。

其他人还包括盖里·科恩（Gary Cohn，极端犹太主义者），高盛首席运营官，他的首任国家经济委员会主任兼首席经济学家，后来被拉里·库德洛（Larry Kudlow，极端犹太主义者）取代。

特朗普在白宫任职四年期间的高级顾问是他的女婿贾雷德·库什纳（Jared Kushner），他是以色列总理本雅明·内塔尼亚胡的终友。库什纳是一个被定罪罪犯之子，特朗普在任期最后几天对其予以大赦。

特朗普政府中的其他极端犹太主义者包括：

- 斯蒂芬·米勒（Stephen Miller），高级政策顾问；
- 亚伯拉罕·伯尔科维茨（Abraham Berkowitz），特朗普及其高级顾问贾雷德·库什纳的副顾问；
- 伊万卡·特朗普（Ivanka Trump），总统顾问，在与贾雷德·库什纳结婚时皈入了犹太教；
- 大卫·弗里德曼（David Friedman），特朗普的律师兼以色列大使；
- 杰森·格林布拉特（Jason Greenblatt），特朗普集团执行副总裁兼首席法官，被任命为国际谈判和以色列-巴勒斯坦冲突特代表；
- 罗德·罗森斯坦（Rod Rosenstein），副检察长；
- 埃利奥特·阿布拉姆斯（Elliot Abrams），委内瑞拉及后来的伊朗特代表；
- 约翰·艾森伯格（John Eisenberg），国家安全委员会法律顾问兼总统国家安全事务副顾问；
- 安妮·纽伯格（Anne Neuber），国家安全局副国家经理；
- 埃斯拉·科恩·瓦特尼克（Ezra Cohen-Watnick），候任国防情报副次长；
- 埃兰·卡尔（Elan Carr），特使；
- 列恩·霍尔多科夫斯基（Len Khodorkovskyy），监督和打击反犹太主义的副特使；
- 里德·科迪什（Reed Cordish），总统副助理，政府间和技术倡议。

特朗普副总统迈克·彭斯和国务部长迈克·蓬佩奥（两人都是基督教犹太主义者）也是以色列及其目标和野心的坚定支持者。

唐纳德“言论自由信徒”特朗普赦免了一些金融和暴力罪犯，却忽视了赦免朱利安·阿桑格（Julian Assange）和爱德华·斯诺登（Edward Snowden）的呼声，他们的犯罪揭露了关于政府操控、腐败以及美国“安全”机构对美国人民广泛非法监控的高度相关信息。

特朗普赦免了以色列间谍乔纳森·波拉德（Jonathan Pollard），他在1987年根据《间谍法》被判终身监禁。招募波拉德的摩萨德特工艾维姆·塞拉（Aviem Sella）也被特朗普赦免，而阿桑格仍关在监狱中，斯诺登仍留在俄罗斯流亡。

塞拉在1987年“逃离”（获得帮助逃脱）到以色列，尽管根据《间谍法》被指控但从未引渡。特朗普白宫的一份声明称，塞拉的特赦获得了本雅明·内塔尼亚胡、以色列美国大使罗恩·德默（Ron Dermer）、美国以色列大使大卫·弗里德曼以及此前去世的特朗普捐赠者谢尔·阿德尔森（Sheldon Adelson）的支持。

贾雷德·库什纳的其他朋友也与沙龙·魏斯（Shalom Weiss）一起被赦免，后者被认为在2000年服了超过800年的史上最长白领监禁。该判决是对庞氏骗局伊利亚胡·温斯坦（Eliyahu Weinstein）的补偿，他诈骗了犹太人和其他人的亿美元。

特朗普在军事和政治支持上几乎给了他们要的一切，将美国大使馆从特拉维夫迁到耶路撒冷，这对巴勒斯坦建国具有至关重要的象征和字面意义；而由贾雷德·库什纳和大卫·弗里德曼设计的“世纪交易”为撒巴提以色列政府开了绿灯，使其大幅扩大了在被占领的约旦岸建立非法仅限犹太人定居点的广泛计划。

这通过夺取潜在巴勒斯坦家园的土地，使得“两国方案”变得不可能，而这一计划自1948年和1967年阿拉伯人控制的加沙地、约旦岸、西奈半岛和叙利亚戈兰被以色列占领以来一直存在。

所有关于谈判的谈判、路线图和延迟的讨论都在争取时间，直到约旦岸被以色列房地产物理占领。特朗普如果不是一个信息极度匮乏的巨大蠢货，就不会看出这是他正在帮助完成的计划。

特朗普政府在许多方面都是库什纳政府，这意味着是内塔尼亚胡政府，这意味着是撒巴提政府。我理解为什么许多反对各种形式崇拜法西斯主义的人倾向于特朗普，但他是撒巴提计划的关键部分，我将在下一章中处理这个问题。

## 乔·拜登（民主党）

认知能力几乎丧失的乔·拜登在2021年1月接任总统，而他的另一个空壳——副总统卡玛拉·哈里斯（Kamala Harris）作为最新的进入白宫的撒巴提跑腿。

门上的名字可能变了，但“政党”——背后的力量没有变，因为犹太主义者被任命一系列与撒巴提计划和政策相关的关键事件。

这些人物包括：

- 珍特·耶伦（Janet Yellen），财政部长，前联邦储备委员会主席，以及在曼努钦（特朗普）、刘和盖斯特纳（奥巴马）、萨默斯和鲁宾（克林顿）之后的另一个极端犹太主义者；
- 安东尼·布林肯（Anthony Blinken），国务部长；
- 温迪·谢曼（Wendy Sherman），副部长，新冠病毒协调员；
- 罗谢尔·瓦伦斯基（Rochelle Walensky），疾病控制中心负责人；
- 拉切尔·莱文（Rachel Levine），跨性别副卫生部长；
- 米里克·加兰（Merrick Garland），总检察长；
- 亚历杭德罗·马约卡斯（Alejandro Mayorkas），国土安全部长；
- 卡斯·桑斯坦（Cass Sunstein），负责新移民法的国土安全官员；
- 艾弗里·海因斯（Avril Haines），国家情报局主任；
- 安妮·纽伯（Anne Neuber），国家安全局网络安全主管；
- 大卫·科恩（David Cohen），CIA局长；
- 罗纳德·克莱恩（Ronald Klein），拜登的办公厅主任；
- 埃里克·兰德（Eric Lander），科学与技术政策办公室主任；
- 杰西卡·罗森彻（Jessica Rosencher），联邦通信委员会（FCC）代理主任。

为什么在每一届政府中，无论总统是谁、政党是什么，这么多关键职位都由美国人口的2%和全球政府的0.2%占据？这是一种巧合吗？

显然不是，这就是为什么撒巴提人建立了他们庞大的全球互锁“反仇恨团体”，拒绝谴责任何提出这些显而易见问题的人为“犹太主义者”。犹人在受萨巴提支持的纳粹德国遭受了极其恐怖的虐待，这种经历竟被用来达到这种目的，简直令人作呕，无以言表。

## 政治融合

萨巴提的操纵反转了共和党和民主党的角色，英国的保守党和工党也发生了同样的情况。共和党和保守党一直被标记为“右翼”，而民主党和工党被标记为“左翼”，但看看现在的政策立场，在“觉醒”（Woke）这一由教派创造的极右统治旗帜下，民主工党的“左翼”甚至了共和党和保守党。

曾经，民主工“左翼”捍卫言论自由和人权，现在他们试图删除它们；正如我之前提到的，尽管英国长靴式保守政府推行着“新冠”法西斯主义，但由基尔·斯塔默领导的工党要求采取更极端的措施。

在对前任领袖、软弱且无能的杰米·柯宾进行政治和媒体猛击，并对他及其政党发出虚假的“反犹太主义”指控后，工党遭到了萨巴提人的公开羞辱。

这种“反犹太主义”宣传的意图很明确：他们要求的回应当是柯宾迅速而果断地“滚蛋”，并发表声明揭露反犹太主义工业（萨巴特）试图沉默工党对以色列政府（萨巴提人）的批评，并清洗所有反对极端锡安主义（萨巴提人）的党内人士。

相反，柯宾及其政党屈膝妥协了这些虐待者，而这从定义上来说是不可能的。满足一个要求只会导致另一个新要求，直到接管完成。

工党投降的结果是，我们现在拥有一个萨巴提控制的保守党，并被一个萨巴提控制的工党“反对”，处于一个一党制的萨巴提国家中，这个国家正向暴政的极端（萨巴提教派议程）飞驰。

在美国，情况也是如此。工党的基尔·斯塔默每天都跪着并将舌头指向特拉维夫，或者我猜现在是耶路撒冷，而波里斯·约翰逊则有一位前工党议员约翰·曼担任的“反犹太主义沙皇”，他一直坐在祈祷垫上陪斯塔默作伴。

萨巴提的影响体现在工党的犹太裔成员身上，他们因批评以色列而被踢出，其中包括那些在纳粹德国遭受过苦难的家庭。萨巴提人鄙视真正的犹太人，并更严厉地针对他们，因为给他们贴上“反犹太”标签要困难得多，尽管他们在绝望中确实在尝试。

## 第三章

### 反击者的刺痛

> 在你意识到你的大脑是多么容易被操纵之前，你仍然是别人游戏中的傀儡  
> ——艾薇塔·奥切尔

我将利用特朗普和拜登的总统任期，展示一党制国家的操纵是如何在全球范围内政治选择的幻象背后上演的。没有哪两个总统任期在方向和政策上能比这更不同，且显然是背道而驰的。

“叛逆者思维”看透表象，关注结果和后果，而不是形象、言辞和废话。教派发起了一场运动，将美国分为两类：盲目支持其议程的“觉醒者”，以及那些在反抗教派和萨巴提人意图走向的方向的人。

这为分而治之人口提供了无限可能，通过让他们互相为战，建立起一个感知魔化的感知围栏，在现代版本中将反击者包围起来——这就像1876年“小大角战役”的现代版，当时，由乔治·卡斯特中校带领的美国骑兵队被引入一个陷阱，被防御其被政府掠夺之土地的美洲原住民部落包围并杀害。

在这个现代版本中，角色反转了，是那些反抗萨巴提政府的人被包围，而政府正试图摧毁他们。这个陷阱在多年前就设好了，为了解释我们必须回到2016年，以及唐纳德·特朗普作为美国总统候选人的出现。

他致力于在初选之前和期间，战胜了共和党其他20位候选人中最好的水平，在那些早期阶段，许多人认为他没有进入白宫的机会。据说共和党对特朗普有很大保留，但他何以何方式赢得了提名。

当你了解美国政治的运作方式（通常而言）时，特朗普不可能成为该党的代表，除非经营共和党的受萨巴提控制的“新保守派”希望如此发生。

我们从维基解密（WikiLeaks）公开的邮件和文件中看到了证据，民主党高层（或称“民主保守派”）系统性地破坏了伯尼·桑德斯的竞选活动，以确保萨巴提控制的希拉里·克林顿赢得了作为他们总统候选人的提名。

如果民主保守派能这样做，那么共和党中的新保守派也可以以同样的方式阻挠特朗普。他们没有这样做，在那个阶段我开始得出特朗普可能是被选为总统的结论。

如果是那样，“为什么”就显而易见——目标是将美国分裂为支持教派议程的“觉醒者”和倾向于特朗普的反击者，因为特朗普告诉了他们想听的话。

他的支持者群体几十年来一直被日益忽视和失声，特别是在萨巴提傀儡巴拉克·奥巴马的八年里。现在，有人用他们的语言说话：停止政治和经济权力的持续全球化，停止由“美国”（萨巴提）公司将美国工作出口到中国及等地，停止删除言论自由，停止进一步破坏所有种族城市工人阶级和曾作为美国腹脏的中西部地区就业机会的大规模移民政策。

## 警惕蛇信者

这些人集体地松了一口气，认为终于有一个政治领袖站在他们这一边，但“叛逆者思维”的另一个特征是，对于那些告诉你你想听的话的人，你会观察得更加敏锐。

显然，正如我之前所说，人们希望他们想听的都是真实的、真正的，比起那些说他们不想听且不真实的人，他们更可能相信前者。

销售人员被教导擅长有针对性地引出客户想听的话，并将其作为自己的观点重复给他们，以获得目标的喜爱和信任。教派的资产也是销售人员，从销售感知角度来说如此。

要读懂教派的操纵，你必须玩长线、更广泛的游戏，而不是落入政党政治杂技表演的陷阱。美国两个政党都是教派的工具，根据议程的需求以不同方式利用它们。

特朗普和共和党曾是分裂美国和孤立反击者的焦点，为拜登总统成为美国历史上最极端的情况铺路，通过推进全面的“觉醒”（教派）议程，其目的是摧毁和沉默现在被标记为纳粹支持者和白人至上主义者的反击者。

萨巴提人想要特朗普上台，原因正如极锡安主义者绍尔·阿林斯基（1909-1972）所描述的那样，他在人们听到这个词之前很久就已经通过“社区组织”推广“觉醒”哲学了。在那个时代，它仍然被称为传统的马克思主义。

被操纵的特朗普现象的原因列在阿林斯基1971年的著作《激进分子规则》中，那是他推翻民主和其他政权并将其替换萨巴提马克思主义的蓝图。

阿林斯基的追随者包括深度腐败的奥巴马、众议院议长南·佩洛西和希拉里·克林顿，后者称他为“英雄”。这三个人都是萨巴提的走狗，佩洛西具化了广泛为教派核心提供服务的傲慢教派愚蠢。

意料之中，作为萨巴提“启光者”的倡导者，阿林斯基在其书的献辞页列出了 Lucifer，作为最初的激进分子获得了他的王国（正如我们将看到的，是“地球”）。

阿林斯基的黄金激进规则之一是选择一个个人，并将所有的注意力、仇恨和指责集中在他们身上，而不是针对没有面目的官僚机构和公司。《激进者规则》（*Rules for Radicals*）实际上是一本萨巴特教手册，其内容几个世纪以来在全球范围内反复使用。

为什么萨巴特信徒不把他们的设计者反派推向权力，让他们成为所有注意力、仇恨和指责针对的对象呢？他们正是这么做的，我唯一的问题是特朗普对此有多少了解，他在多大程度上被操纵了。我怀疑两者都有。

马克斯·阿林斯基的特朗普技巧源自一位在1972年去世的人。这种技巧跨越了历史：

- 选择目标，冻结它，将其个性化，使其极极化。不要试图攻击抽象的公司或官僚机构。识别一个负责的个人。忽略任何转移或扩散责任的尝试。

从特朗普获得虚幻权力的那一刻起，一切都围绕着他。选择目标，冻结它，将其个性化，使其极极化。不要试图攻击抽象的公司或官僚机构。识别一个负责的个人。忽略任何转移或扩散责任的尝试。

从特朗普获得虚幻权力的那一刻起，一切都围绕着他。选择目标，冻结它，将其个性化，使其极极化。不要试图攻击抽象的公司或官僚机构。识别一个负责的个人。忽略任何转移或扩散责任的尝试。

他们为拜登效力。特朗普在关键摇摆州的早期领先优势突然开始缩小并消失。这场大流行的骗局被用作借口，签发了近乎无限制的邮寄选票，且没有检查收件人是否仍然在世或是否居住在该地址。这些选票被寄给了一群甚至没有要求过它们的人。

私人机构被雇佣收集这些选票，在计票之前，谁知道他们对这些选票做了什么处理。美国选举系统几十年来一直受到操纵，变成了一个病态的笑话，漏洞比瑞士奶酪还多，其明确目的就是为了操控结果。

接着是 Facebook、Twitter 和 Google 旗下的 YouTube 等撒旦教巨头对信息进行的刑事操纵，他们删除了支持特朗普、反对拜登的账号和帖子，而所有支持拜登的内容都被放过一马。撒旦教人希望拜登获胜，因为在分裂美国之后，是时候让全“觉醒”和崇教议程的各个方面大爆发了。

## 猎人采集

极端的价值观偏见包括封锁《纽约邮报》披露的拜登丑闻的信息，这一丑闻本应在竞选最后几周结束他的总统竞选。

据报道，他那极度腐败的儿子亨特·拜登曾送一台笔记本电脑去当地商店维修，但没有回来取。时间过去后，由于未付账单，笔记本电脑成为了商店的财产。

当所有主看到硬盘上的内容时，他将副本交给了联邦调查局（FBI），但 FBI 一无所作为，尽管这证实了广泛的腐败，即乔夫·拜登家族利用他的政治地位（特别是在担任奥巴马副总统期间）在世界各国赚取了数百万美元，最著名的乌克兰和中国。

亨特·拜登曾经的业务伙伴托尼·鲍宾辛斯基在《纽约邮报》爆出此消息时公开身份，证实了他所看到的腐败，并证实乔夫·拜登不仅知道发生了什么，还从战利中获利。

一家与中国关系密切的公司——就像中国所有主要企业一样——将数百万美元交给了习近平主席领导的中国共产党；拜登甚至在崇教组织的世界经济论坛会议上吹嘘说，作为副总统，他曾命令乌克兰政府解雇了一名检察官。

他没有提到的是，同一个人恰好在调查一家属于亨特·拜登腐败投资组合的能源公司。该公司支付巨额资金的唯一原因仅仅是他父亲的影响。

一夜之间，拜登的总统竞选本该终结，因为他公开撒谎说不知道他的儿子在做什么。相反，几乎整个撒旦教拥有的主流媒体和撒旦教拥有的硅谷都压制了这一故事的传播。单是这一点就极大地操纵了2020年的选举。

崇教资产如 Facebook 的马克·扎克伯格等也花费了数亿美元来支持拜登和投票给“执政当局”。

崇教组织一直利用特朗普作为焦点来分裂美国，现在正绝望地引入愚蠢、顺从、腐败的拜登来完成双重打击。他们绝不会让民意阻碍他们的计划。

硅谷广泛审查了关于选举被操纵的说法，因为选举确实被操纵了。出于同样的原因，任何声称选举被操纵的人都被指责为“白人至上主义者”，包括少数可怜的想这么说的共和党政客。

在所有提到该说法的媒体上，它都被描述为“虚假指控”，尽管这些所谓“记者”的借口对该主题根本没有进行研究。

特朗普赢了七百万张票，比任何现任总统所获得的都要多；不知为何，一个认知受限、即将78岁的人，在竞选的大部分时间里躲在公众面前，竟然赢得了比历史上任何总统候选人更多的票。这不合乎逻辑。

你只需要看看两个候选人的竞选集会，就能见证对特朗普的热情和对拜登的冷淡。成千万人参加特朗普的活动，而拜登在空旷的停车场演讲，通常有电视剧组参加并构图以掩盖现场没人的事实。

看到视频流出，拜登站在台上向电视剧组和政党调停者发表演讲，同时阅读大屏幕提词器上为他写好的文字，这太是可怜了。所以，是的，那些抗议者对选举被操纵的说法是正确的，尽管几乎没有人愿意听他们。

## 蜘蛛与苍蝇

撒旦教在公众心中没有两个“阵派”，只有一个撒旦教，通过操纵政治来引导公众。国会山的骚乱被荒谬地称为“叛乱”，是撒旦教的舞台剧，为了让公众关注其他，教教的反对派系，陷阱已经触发。是撒旦教的傀儡表演。

会国山的骚乱是一个陷阱。通过将他们联系到两个对立群体——觉醒者和拜登支持者——陷阱即将布下。

由于这些抗议者如此容易地进入大楼，这是因为两点：一方面——正如2020年初的“新冠”骗局一样——我能看到撒旦教如何利用局面快速推进其议程；另一方面——通过我30多年对撒旦教技术和活动的经验——我看到他们如何利用局面，为了提供特定的借口，即“问题-反应-解决方案”。

只有华盛顿的一小部分抗议者通过打破窗户和破门进入了国会大厦。这并不重要。整个人群和所有拜登支持者，即使他们不支持特朗普，也会被归类为危险的叛乱分子和阴谋论者。

代理煽动者被广泛用于操纵真实的人以符合预期结果的方式行动。在这种情况下，“真实的”指的是我遇到了支持特朗普并声称选举被盗取的人。然而，他们中也有国家特工，伪装成特朗普支持者和 QAnon 粉丝，以此预热国会骚乱，一些真实的特朗普支持者几乎落入了陷阱。

我将这种情况描述为“蜘蛛对苍蝇说：进入我的客厅吧”。

一名被指控者的托马斯·普洛钱表示，他的当事人是66岁的托马斯·爱德华·卡尔韦尔：他自1979年起就持有绝密安全许可，并为了支持他的许可通过了多次特别背景调查。从海军退役后，他于2009年至2010年期间曾在联邦调查局（FBI）担任科长，级别为GS-12。

他还组建并运营了一家咨询公司，为美国政府客户提供服务，包括美国毒品执法局、住房和城市发展部、美国海岸警卫队和美国陆军人事司令部，工作通常涉及机密。

随后，法官在没有关于阴谋或他试图强行进入大楼证据的情况下释放了考德威尔（Caldwell）。

《纽约邮报》援引一名“执法人士”的话说，暴乱期间，在特朗普的支持者中，摄像头发现了“至少有两名已知的Antifa成员”，而其中被捕的暴乱分子之一是约翰·厄尔·苏利文（John Earle Sullivan），他是一个来自犹他州的、极其极端的黑人命命（BLM）特朗普仇恨者，此前于2020年7月因一起BLM-Antifa暴乱被捕并起诉，在那场暴乱中，司机受到威胁，其中一人中枪亡。

苏利文是犹他州组织“Insurgence USA”的创始人，该组织是受邪教创建并资助的黑人命命运动的附属机构。Twitter曾出现并后删除了特朗普支持者指责Antifa渗透者的视频，有一组人被拍到在暴乱前换上了支持特朗普的衣服。

大楼的安保工作正如计划中那样极其糟糕。罗伊·弗莱彻尔·普鲁蒂上校（Colonel Leroy Fletcher Prouty）是一位长期与美国安全机构合作、拥有丰富秘密行动经验的人，他曾描述过识别谁参与暗杀的迹象。他说：

> 没有人需要去直接策划暗杀——它自然会发生。积极的作用是通过纵许其发生来秘密地扮演的。这是最大的线索。谁有权力取消或减少常规的安保措施？

这一原则适用于许多其他情况，无疑也适用于2021年1月6日的国会骚乱。

## 圈套

鉴于已知有如此庞大且可能愤怒的人群聚集在国会大厦附近，考虑到在QAnon心理战和唐纳德·特朗普声明的影响下，来自美国各地的人们情绪激动，安保机构本应有一支主要的警察细节小组来保卫大楼，并让国民卫队待命。

然而，国会警察的“安保”却是脆弱、软弱且易于攻破的。部署的人员人数与普通工作日相同，这是一个显而易见的危险信号。对于在当时情况下已显而易见可能发生的暴乱，他们并没有配备相应的人员或装备。

现场没有设置任何保护性且有效的围栏，也没有应急预案。整个过程基本上就是袖手旁观地让人们进入。

一旦进入内部，警察大多后缩了，除了一名国会警察，他在没有警告的情况下击毙了无武装的空军退伍军人抗议者阿什莉·巴比特（Ashli Babbitt），当时她正爬过一个破碎的窗户。

关于有五人在“武装起义”中死亡的故事被不断重复，而当时并没有报告显示暴乱分子使用了武器。除了巴比特外，其他四人死于心脏发作、中风，以及显然是药物过量。国会警察布莱恩·西克尼克（Brian Sicknick）据报道在暴乱结束后曾被灭火器击打，后死于华盛顿法医办公室所说的中风。西克尼克没有外伤。

谎言如连发机枪般抛出。他们通过不断重复谎言来构建一种叙事，直到这个谎言变成被接受的“众所周知”的真理。

纳粹宣传部长约瑟夫·戈培尔斯（Joseph Goebbels）的“大谎言”技术被那个邪教不断使用，这个邪教曾是纳粹的幕后，如今则是“新冠”和“气候变化”骗局的幕后主。戈培尔斯说：

> 如果你撒一个大谎言并不断重复它，人们最终会相信它。谎言的维持取决于国家能否保护人们免受谎言带来的政治、经济和/或军事后果的影响。因此，国家利用一切权力压制异见变得至关重要，因为威胁是谎言的死敌，以此类推，真理是国家最大的敌人。

大多数抗议者在国会大厦内自由穿行。这使得人们能够拍摄到暴乱分子在大楼标志性区域的照片，包括参议院会议厅，这些可以被用作反对反对者（Pushbackers）的宣传素材。

一位国会议员将现场描述为“任何人能想象的最糟糕的安保状态”。好吧，第一部分是真的，但显然有人预见到了并确保了它的发生。

流传最广的一些照片显示了穿着QAnon符号的人，现在这种心理战被用来给所有QAnon追随者贴上“白人至上主义者”和“起义者”的普遍标签。

## 巫猎

政府检察官迈克尔·谢尔温（Michael Sherwin）是一只侵略性强、眼神深邃的职业罗罗犬，他领导了这场“调查”，如果称其为过头，现实其实是其的一千倍。

数百人因“伤害错误的政治观点”的罪名被追踪并逮捕，那些人仅仅是进了大楼，没有实施任何暴力或破坏财产，拍了几张照片就离开了，却被关了起来。他们被标记为“共和国的威胁”。

拜登坐在白宫签署为他撰写的行政命令，这些命令正在拆解“共和国”。即使法官裁定母子不应被关押，政府仍然将他们留在那里。

被捕者中的人在华盛顿被监狱守卫严重毒打，一个人的律师表示他遭受了颅骨骨折并导致一只眼睛失明。与此同时，一名女子无故被国会警察击杀，而我们被不允许知道他是谁，更不用说他发生了什么，尽管可能什么都不会发生。

邪教的QAnon/特朗普圈套旨在识别并隔离反对者，然后在他们通往粉碎和删除他们的道路上针对他们，这取得了巨大的成功。

你会以为是俄罗斯人持枪闯入大楼，并将参议员们排成行决队，以观察政治和媒体的反应。

国会议员亚历山德里亚·奥卡西奥-科特兹（Alexandria Ocasio-Cortez）是一个长在女人体里的孩子，一个可怕的、“只有我、我、我”的觉醒派（Woker）自恋狂，其程度之深语言已失去意义。

她说，当“起义者”敲她的办公室门时，她以为自己要死了。事实证明暴乱发生时她并不在国会大厦，那个“敲门”的是一名国会警察。她自称为“幸存者”，这对所有经历过暴力和性侵待的幸存者都是侮辱，而她却靠说她那些优渥特权的废话为生。

她的觉醒派同事、同样的自我自恋狂拉希达·特莱布（Rashida Tlaib）情绪崩溃，描述了在暴乱分子在场时不在楼内对她造成的毁灭性影响。

奥卡西奥-科特兹和特莱布是一个完全觉醒派国会议员团体“精英小队”（The Squad）的成员，还有伊尔汗·奥马尔（Ilhan Omar）和艾安娜·普雷斯利（Ayanna Presley）。

惯常的嫌疑人立即以民主党极端犹太主义参议员和特工查克·舒默（Chuck Schumer）以及亚当·希夫（Adam Schiff）的形式出现在暴乱案中，要求弹劾特朗普，理由是“他在起义中的参与部分”。

这对蠢货同样领导了针对虚构的“俄罗斯通俄”废话发起的失败弹劾，该废话声称俄罗斯帮助特朗普赢得了2016年选举。

一场由头脑简单的前9/11事件FBI局长罗伯特·穆勒（Robert Mueller）领导的为期两年的“俄罗斯通俄调查”舞台剧，得到了19名律师、40名FBI探员以及情报分析师、法务会计和其他职人员的支持。这些职人员吞噬了数千万美元，却没有发现任何与俄罗斯勾结的证据。

现在，愚蠢的舒默（Schumer）和希夫（Schiff）想就国会大厦“叛乱”（暴乱）事件对特朗普发起第二次弹劾，而发育不完全的舒默将其称为另一个“珍珠港”，其他人则将其与导致3000人死亡的9/11相比。

第二次特朗普弹劾也失败了，这并不意外，因为弹劾本应罢免现任总统，而当它发生时，特朗普已经不再是总统了。这些人正在统治你们的国家——美国，至少在官方上是如此。很可怕，不是吗？

## 结果说明一切——始终如此

这一切的结果——而“反叛思想”（Renegade Minds）关注的是结果而非言辞——就是一场恶毒、歇斯底里且显然预计划的针对“反击者”（Pushbackers）的攻击，旨在审查、封口和诋毁他们，甚至针对他们的谋生权。

他们被谴责为“国内恐怖分子”，需要像对待基地组织和伊斯兰一样对待他们。“国内恐怖分子”是邪教一直试图贴上的标签，从1995年奥克拉荷马炸弹事件开始，那次被归咎于“极右国内恐怖分子”。

近3000名士兵从全美被部署到华盛顿空旷的街道参加拜登的就职典礼。一万叛乱分子留了下来，借口是保护首都免受叛乱，这更多是种心理编程，旨在使军事在国内执法中的行为正常化，以支持邪教的警察-军事国家计划。

拜登政府开始对军队中的“错误思想者”进行清洗，这意味着任何不认同“觉醒”（Woke）的人。国会大厦被围有铁丝网的围栏包围，这片自由之地在象征和现实层面上被进一步拆解。

美国自19世纪内战以来从未如此分裂，反击者被孤立并贴上恐怖分子标签。现在，正如注定会发生的那样，邪教立即着手删除剩余的少量自由，并通过美国历史上最受控的“总统”的愿望来转型美国社会。

拜登在就职最初几天里几乎每小时就发布一项独裁行政命令，涵盖了邪教愿清单的所有领域，包括淡化对墨西哥边界的控制，允许数千万移民非法进入美国，以改变美国的人口结构并引入足以改变选举结果的预期民主党选民。

还有向联邦增加新州的计划，如波多黎各和将华盛顿特区设为一州。这些都是确保邪教拥有的“觉醒民主党”永久执政的计划的一部分。

## 边界——什么边界？

我在其他书中详细揭露了美国和欧洲的大规模移民是邪教网络的产物，由乔治·索罗斯（George Soros）及其全球开放社会（开放边界）基金会投入的数十亿美元支持此及其他目的。

这种影响在美国可见的，其人口在短短30多年内增加了1亿，主要通过移民实现。我在《答案》（*The Answer*）中写道，这个计划是让尽可能的人跨越南方边界，使数字变得不可阻挡，而我们现在正处于邪教拥有的拜登统治下。

中美洲的萨尔瓦多展示了南方边界正在发生的事情规模。现在三分之一的人口居住在美国，大部分是非法的，更多的人正在路上。

其方法是在经济上摧毁中南美国家，并通过挥持砍刀的病态帮派传播暴力，例如 MS-13 帮派。拜登在南方边界强加的安全措施意味着一切已是上上钉。他在“选举”之前说过，如果他当选总统，他想看到边界出现涌潮，这为选举日后人们这样做提供了绿灯，导致了随后对美国和移民造成的人道主义灾难。

当这股涌潮来临时，那个愚蠢的亚历山大·奥卡西奥-科特兹说这不是“涌入”，因为他们是“孩子，不是叛乱”，而“涌入”（拜登使用的词）是“白人至上主义者”的说法。

撒旦教徒和邪教正在通过在当地人中混入暴力分子和帮派来摧毁美国城市，并让无法应对海量新入境者的服务瘫痪。欧洲也发生着类似的事情，因为整个西方社会正成为人口统计和文化转型及动荡的目标。

该计划要求暴力和犯罪来创造一个恐吓、恐惧和分裂的环境，索罗斯一直在资助全美地区检察官的选举，这些人随后停止起诉许多犯罪，减轻暴力犯罪的刑期，并释放他们所能说的尽可能多的罪犯。

撒旦教徒正在制造混乱，以便秩序——他们的秩序——可以做出反应，这是一个经典的“问题-反应-解决方案”模式。共济会的一句格言说“混乱中产生秩序”（Ordo Ab Chao），这正是为什么邪教不断制造混乱以施加新的“秩序”。

“新冠”骗局可以从这些人身上看到：乘坐飞机进入美国的人被迫接受“新冠”检测，而涌入南方边界处理设施的移民却没有。没有什么能阻挡大规模迁移，如果这意味着忽视政府自己的“新冠”规定，那就随它去。反正他们知道这一切都是胡扯。

## 救世主综合征（Save me syndrome）

我一直揭露的邪派议程的几乎每一个方面，在“拜登”上台头几天里都有了体现，压制反对者（Pushbackers）处于一切的核心。

“反叛者思维”（The Renegade Mind）将与其支持者和倡导者完全不同的眼光看待特朗普时期和QAnon，因为点已经连接起来了。

QAnon/特朗普的政治操纵计划（Psyop）已经给了邪派它所寻找的一切。我们可能不知道特朗普在多大程度上意识到自己正被利用，但那是次要问题。这种双管攻势产生了预期的结果：分裂美国并让反对者孤立。

要扭转这一局面，我们必须寻找赋权的新途径，这些途径不包括通过我所谓的“救世主综合征”将我们的权力交给其他人和其他团体——即“我想让别人来替我做”。

我们在人类历史中见过这种作用，QAnon/特朗普的政治操纵计划只是所有其他化身中的最新。宗教是这种现象的明显表现，当人们寻求“神”或神父来拯救他们或告诉他们如何被拯救时，然后还有像特朗普这样的“救世主”政治家。

救世主综合征还伴随着同样的重复主题：将你的权力交给你认为能拯救你的人或物，而你真正的“救世主”每天早上从镜子中回望你。

反叛者思维在这方面时刻警惕，总是问“我能做什么？”而不是“别人能为我做什么？”甘地是对的，他说：“你必须成为你想要在世界上看到的改变。”

宗教、政府、政治家、公司、媒体、QAnon，都是这种权力转移和稀释的不同表现形式。拒绝将你的权力交给政府，而是将其交给特朗普和QAnon，并不是采取新的方向，而仅仅是在旧海报上贴上新名字来回收旧的模式。

现在，我们将转向整个人类故事中最强有力的例子，即当你交出权力后所导致的后果。我所说的，当然是“新冠”骗局。

## 第四章

## “新冠”：计算过的灾难

> 事实对于那些投入欺诈的人来说是威胁  
> ——作者 DaShanne Stokes

通过采用我目前为止概述的“反叛者思维”方法论，我们可以轻松揭开“新冠疫情”骗局的真实原因。我们将从对比长期计划的邪派目标结果与“新冠疫情”的结果开始。知道了结果，你就会看到这段历程。

我曾强调过“饥饿游戏社会”的计划，这已经在我的书中出现了多年，少数人通过持续的依赖控制大多数人。要创造这种依赖关系，破坏独立的生计、企业和就业至关重要，使人口依赖国家（邪派）通过保障津贴收入来满足生活的基本需求。

只要收入保持独立，这些邪派的野心就会被挫败。有了这些知识，一旦开始谈论“封锁”并关闭所有所谓的“必要”企业以“拯救”我们免受某种所谓的“致命病毒”，就很容易看出“疫情”骗局将走向何方了。

像亚马逊和沃尔玛这样的邪派公司自然被认为是“必要的”，而家庭作坊和商店却因法西斯主义的法令而关闭大门。结果，随着每一次新的封锁和新规定，更多不属于邪派的小型、中型甚至大型企业陷入了绝境，而邪派巨头及其门面人物每秒钟都变得更加富有。

家庭作坊和商店被剥夺了收入、生计权，而像杰夫·贝佐斯（亚马逊）、马克·扎克伯格（脸书）、塞尔盖·布林和拉里·佩奇（谷歌/Alphabet）等人的财富达到了创纪录水平。

邪教组织通过进一步剧烈的财富集中增加自己的权力，而竞争对手则被摧毁并陷入了依赖状态。封锁是为了实现这一目的而发起的，它们与健康毫无关系。

我哥哥保罗花了45年时间建立了巴士维修业务，但封锁意味着巴士在连续几个月里运行水平只有正常水平的一小部分。全球范围内数以亿计类似的故事。人们一生的努力被这些邪教派亿万富翁以及他们在政府和执法部门的代理人所摧毁，而这些人继续通过剥收民众税款来维持生，却剥夺了同样民众维持生计的权利。

# 地狱之门

在这一切的背后，完全清楚自己在做什么以及为什么的是邪教派特工比尔·盖茨这个精神病态的人物。他在世界卫生组织的傀儡特德罗斯于2020年3月将“新冠”宣布为大流行。

世界卫生组织在2009年宣布“猪流感大流行”前的一个月，更改了对“大流行”的定义，如果按照之前的定义，那是不会被算作大流行的。同样也适用于“新冠”。

新的“大流行”定义甚至在定义上都是欺骗性的，但盖茨要求进行破坏经济的封锁、关闭学校、社交距离、强制佩戴口罩、为地球上的每个男人、妇女和儿童提供“疫苗”，并对拒绝的人实施严厉的后果和限制。

是谁给了他这种权力？

他所服务的“邪教”就像一个穿着短裤的小男孩，听他爸爸的话做事。他和他那个精神病态的妻子在说更糟糕的事情即将到来时，甚至露出了微笑。

盖茨以所有精神病态者那种实事求是的方式回答了一个关于他所做的事对世界经济影响的问题：

> 嗯，它不会降为零，但会萎缩。全球GDP可能会遭受有史以来最大的打击……在我的一生中，这将是最大的经济打击。但你没有机会。人们表现得好像你有机会一样。当人们可能被感染时，他们不想去体育场……当看到这些状态，知道自己可能是传播链的一员时，人们深受影响；老年人、他们的父母和祖父母可能会受到此影响，而你无法左右这里发生了什么。
>
> 如果未来几个月做得得当，将开放的能力，特别是在富国家，但对于整个世界来说，当我们很大程度上对全体人口接种后，正常才会回归。

这个人没有怜悯或同情心。他怎么可能像邪教分子那样是个精神病态？我的观点是，甚至他也严重地精神疾病。看着他的眼睛，你就能随着他疯狂挥舞的手臂看到这一点。

除非你精神疾病且处于精神病态的极端，否则你不会做出他对2020年初以来对世界人口所做的事情。尤其是当你知道“新冠”的病例和死亡人数是虚假的，是巨大的数字造假产物时，你更不会这样做。

盖茨谈到受“新冠”恐惧影响的人，而那是因为他和他的全球网络每分钟都在对他们撒谎，并受到他严重影响并资助数亿美元的谎言媒体的支持。

盖茨在“新冠”骗局中无处不在，这个人必须余生入监狱——或者精神机构——他的钱将分发给那些在粉碎他人中获得巨大精神病快乐的人。

# 暴力

《饥饿游戏》式的全球结构要求一个军警国家——两者合一的力量——它残酷地将邪教的意志强加于民众，并保护邪教免受公众反抗。

在这一方面，“新冠”骗局也在不断提供素材。往往违法、荒谬且矛盾的“新冠”规则和条例，由愚蠢的自动机器和精神病态者在全球范围内执行，他们戴着无脸的面巾口罩，行为得像希特勒和墨索里尼的纳粹党卫、法西斯黑衣党和棕褐党。

政府中精神心理障碍者和他们无知的随从者所规定的规则的任何微小偏离都会被这些口罩脸法西斯者围攻。

一旦即使是对女孩、妇女和老年人，对公众抗议者的残暴也变得常态，因为那些拿着棍子的勇敢男士——我称他们为“口罩脸”——破坏了和平抗议，并向那些无法维持生计、更不用说支付数百英镑去购买曾被接受的人权的人发放了罚单。

机器人“口罩脸”因参加儿童派对而罚了一组人11,000英镑。几十年来，我记录了执法部门的转型，真正的、正直的官员被乐于听从主人命令的精神病态者和脑残分子所取代。

现在他们被释放到民众身上，我要强调的是这一切并非偶然发生。警察与民众之间关系的逐步演变是由那些知道这将走向何方的人在阴影中策划的，同样也通过“共同目标”（Common Purpose）等组织的培训课程实现的。

所谓的“公职人员”开始将民众视为敌人，警察也是如此。这是2020年黎明时，为人类心理的全面战争准备的行为组织和网络爆发的开始。

法西斯式的封锁命令将人们戴上脚镣和带手铐关进监狱。这种情况发生在格雷琴·惠特默（Gretchen Whitmer）领导的法西斯国家——密歇根州。

“饥饿游戏”执法网络中另一个关键要素是鼓励公众举报邻居和其他人的“违反封锁规定”。英国一位警察局长表示，当他们接到大量公众举报他人去海滩的电话时，他的部队就不需要执行“新冠”巡逻了。

## 巧合？是的，我简直能把雾织成网

从这场所谓的大流行开始，我就知道这是一场邪教行动。它展现了无限的潜力，可以快速推进邪教议程，并利用被操纵的恐惧，要求地球上的每一个男人、女人和孩子都接受“接种”。

我公开了这一点，甚至遭到了大量另类媒体的嘲讽，他们提出了一个场景：中国政府与美国深层政府（Deep State）元素勾结，在武汉的一个顶级生物实验室释放了“病毒”，那里据说是病毒首次出现的地方。

考虑了那种可能性，但由于几个原因，我不买账。“病毒”导致的死亡人数完全不符合“致命生物武器”造成的情况，而且推销传染体的幻象比拥有真实的传染体要有效得多，除非你能通过注射控制谁感染了而谁没感染。

一个虚造的“病毒”给你一张白纸，你可以随意把它变成任何你想要的，并添加你选择的任何症状或突变“变异株”，而真实的传染体会告诉你它实际的作用。

一种幻影疾病允许你对“新冠”进行无止境的荒谬“研究”，通过发明越来越多的“高风险”群体来扩大感知上的影响。

真正的“致命生物武器”可以消灭层级中不属于邪教但对其运作至关重要的人。显然，他们不想那样。释放一种真实的疾病意味着你不想要那样。释放一种幻象的疾病意味着你不想要。

一种与美国深层政府勾结、从中国实验室释放的生物武器可能符合某种阴谋叙事，但它是真的吗？使用“病毒”的借口来证明真正的生物武器——“疫苗”——不是有效得多吗？即你的疾病原体不需要传播，而是直接通过注射器到达。

## 第五章

## 没有“病毒”

> 你可以一直欺骗一部分人，也可以偶尔欺骗所有人，但你不能一直欺骗所有人。  
> ——亚伯拉罕·林肯

思想控制最有效的形式是重复。你重复同一个所谓“事实”的格言次数越多，就有越多的人会接受它是真的。这会变成一种“伙计，大家都知道这件事”。

如果你还能审查任何关于你所谓“事实”的其他版本或替代方案，那你基本上就大功告成了，稳操胜券。

到2020年初，该教派几乎完全控制了全球主流媒体，用来散布他们的“新冠”宣传，并忽视或诋毁任何其他信息和价值。

位于该教派控制的硅谷的社交媒体平台，已准备好发动一场严厉的审查运动，以抹除官方叙事之外的一切内容。

## 欺骗的结构

展现“新冠”骗局的金字塔结构非常简单，且必须运作。必须让尽可能少的人完全知晓正在做什么——以及为什么要这样做——否则真实情况就会泄露。

金字塔的顶端是教派的核心，他们控制着比尔·盖茨，而盖茨又通过他的关键资金和他的傀儡总长发言人特德罗斯（Tedros）控制着世界卫生组织。

在任命特德罗斯之前，特德罗斯曾是盖茨发起的、用于“抗击艾滋病、结核病和疟疾”的全球基金会（Global Fund）主席，是盖茨资助的“疫苗联盟”GAVI的董事成员，并在另一个盖茨资助的组织担任董事。

盖茨拥有他，挑选他是有特定原因的——特德罗斯是个骗子，甚至更糟。

特德罗斯曾是埃塞俄比亚暴政马克思主义政府数十年的成员，该政府充满了侵权行为。他曾面临腐败和挪用资金的指控，并在担任埃塞俄比亚部长期间曾三次因霍乱疫情被曝光。

特德罗斯曾将大屠杀种族灭绝独裁者罗伯特·马加贝任命为WHO公共卫生信誉大使，这在特德罗斯身上就像是任命一个精神病态者来管理和平运动。

## 追踪资金来源

克里斯托弗·惠蒂（Christopher Whitty）是英国政府“病毒”政策的核心、首席医疗顾问、政府科学应急响应小组（SAGE）的高级顾问以及世界卫生组织执行委员会成员，他获得了比尔和梅琳达·盖茨基金会资助的4000万美元用于非洲的疟疾研究。

帕特里克·瓦兰斯（Patrick Vallance）是SAGE的联合主席和政府首席科学顾问，曾是制药巨头葛兰史素克（GlaxoSmithKline）的高管，其与比尔·盖茨有根本性的财务和业务联系。

伦敦帝国学院是英国及其他地区“新冠”政策的主要参与者，拥有“新冠肺炎”响应团队，受盖茨资助并与中国有深厚联系，而现在臭名昭著的尼尔·弗格森教授，也受到了盖茨的资助。

弗格森为第一轮封锁提供了极度错误的借口。美国版的惠蒂和瓦兰斯，即安东尼·福奇，与“新冠疫苗”制造者 Moderna 有联系，比尔·盖茨也通过比尔和梅琳达·盖茨基金会的资助与之联系。

当你观察全球“新冠”骗局背后协调和决策的各个元素时，那里有比尔·盖茨和他的钱。他们包括：

- 世界卫生组织；
- 美国疾病控制与预防中心（CDC）；
- 安东尼·福奇的国家卫生研究院（NIH）；
- 帝国学院和尼尔·弗格森；
- 伦敦卫生与热带医学学院；
- 英国药品和医疗保健产品监管局（MHRA）；
- 威康信托（Wellcome Trust）；
- 疫苗联盟（GAVI）；
- 流行病防备创新联盟（CEPI）；
- 编制了虚假“新冠”数据的约翰斯·霍普金斯大学；
- 世界经济论坛。

盖茨基金会通过无限制的资金拥有了全球健康系统以及“新冠”骗局中的全球主要参与者。

## HIV——“新冠”的演习

我将给你一个由于审查和盲目相信官方叙事对健康和真理造成的后果。这个故事是由 PCR 发明者凯里·穆利斯在他的书《Dancing Naked in the Mind Field》中讲述的。

他在1984年接受了一项普通的科学事实：法国巴斯德研究所的卢克·蒙塔尼耶和美国国立卫生研究院的罗伯特·盖洛独立发现了名为 HIV 的“逆转录病毒”会导致艾滋病。

穆利斯随后发现，没有发表过描述 HIV 可能引起艾滋病的实验论文。穆利斯问，既然蒙塔尼耶和盖洛并没有真正发现这些证据，为什么他们的工作会被发表？

最终，穆利斯得出结论：没有人证明过 HIV 会导致艾滋病，尽管它产生了一个数十亿美元的全球产业，而且媒体每天在文章和广播中将此作为事实重复。

## “病毒”存在吗？好吧——证明它

穆利斯关于 HIV 的描述在“新冠”中被重复了。声称发现了一种新的、或“新型的”感染，整个医疗系统像对待 HIV 和艾滋病那样重复这一点。

主流没有人提出相关问题，如“你们如何知道？”以及“你的证据在哪里？”SARS-CoV-2“病毒”存在。大家都知道。好吧，我不知道，包括像安德鲁·考夫曼和汤姆·科万这样的美国医生。

我们敢于追求明显而简单的问题：“证据在哪里？”医学、新闻界和普通大众的大多数没有考虑到。毕竟，大家都知道有一种新的“病毒”。

## 让我们假设

考夫曼发现，在没有任何依据得出关于武汉约200名初期患者爆发疾病的结论时，中国当局立即得出其原因是一种“新病毒”。

这种所谓的“病毒”并未从其样本的其他遗传物质中分离出来，也没有通过被称为柯赫假设（Koch’s postulates）的系统证明它是疾病的致病原。

世界被告诉，SARS-CoV-2“病毒”导致了一种他们称为“Covid-19”的疾病，这种疾病具有“流感样”症状，并可能导致呼吸问题和肺炎。

这些症状在武汉和受污染的中国地区普遍存在，并不能证明存在一种新的“病毒”。

所谓的“病毒”从未被证明存在，也从未被证明引起任何疾病。人们根据症状，通过一种无法检测传染性疾病的 PCR 检测被确诊。

柯赫假设包括：

1. 微生物必须出现在每一个疾病病例中，且所有患者必须具有相同的症状；它也不应出现在健康个体中。
2. 微生物必须从患病宿主中分离出来。如果是细菌或真菌，则必须在纯培养中生长；如果是病毒，则必须从临床样本中净化。
3. 当感染原体接种到健康的易感宿主时，必须重现出具有所有特征的特定疾病。
4. 微生物必须从实验性感染的宿主中恢复。

在“SARS-CoV-2”和“Covid-19”的案例中，这些标准没有一个被证明。没有一个。从未。

## Covid 真的是计算机“病毒”

英国卫生部的声明说，“病毒”现在通过“分子生物学技术检测宿主的病毒遗传代码”进行“诊断”时，他们的意思是 PCR 测试。

PCR 无法检测传染性。没有可靠的方法将“病毒”与疾病联系起来，也没有科学证据证明任何“病毒”导致了任何疾病。

克里斯汀·马西（Christine Massey）和她的团队向不同国家的公共卫生机构提交了约40项信息自由请求，要求提供 SARS-CoV-2 已分离的证明，但没有一个能提供该信息。

马西说：“信息自由法揭示了加拿大公共卫生局没有任何人、在任何地方、任何时候分离过‘SARS-CoV-2’的记录。”

他们所谓的“Covid”实际上是由计算机程序创建的。他们从一个通过 PCR 测试声称感染了 Covid-19 的人体提取了肺液，其中含有多种来源的遗传物质，然后使用多个计算机程序从来源不明的RNA序列创建了一个理论病毒基因组模型。

挥一挥魔棒，一个计算机生成的基因组、一个科学幻想就诞生了。

## 这是你的“病毒”——它是一个独角兽

安德鲁·考夫曼博士展示了一次精彩的分析，描述了这种“病毒”是如何被想象成虚假存在的。

他剖析了一篇发表在《自然》杂志上、由19位作者撰写的文章，文中详细说明了“新SARS-CoV-2病毒”的完整病毒基因组测序。

这个计算机建模的基因组被用作所有后续基因组测序实验的模板，导致了所谓的变异株数量超过6000个。

这个虚假基因组是由超过5600万条RNA链构建的。这些碎片通过寻找重叠序列区域被组成较长的片段。计算机程序创建了超过200万种可能的组合，作者只是选择了最长的一个。

考恩博士指出，这相当于一群研究人员声称发现了一个独角兽，因为他们发现了一个蹄子、一根尾巴毛和一只角。然后他们将信息输入计算机并编程重建独角兽，再声称这种重建是真实的独角兽。

## 第六章

## 欺骗的序列

> 如果你说真话，你什么都不需要记住。  
> ——马克·吐温

我们被告知武汉爆发了致命疾病，世界媒体开始了它们的攻势，旨在通过恐吓民众来让他们盲目地服从。

中国科学家说这是一种新的——“新型”冠状病毒，他们将其命名为 SARS-CoV-2，导致了一种被他们标记为“Covid-19”的疾病。直到今天，这种“病毒”从未被分离、纯化并建立其遗传代码。

中国科学家从极少数人的肺部液体中提取了遗传物质，就称他们发现了一种“新”东西，而这种物质的内容非常广泛。

人们根据在武汉和受污染的中国地区普遍存在的症状，通过一种无法检测传染性疾病的 PCR 检测被确诊。

## 你感到很困意

整个“Covid”骗局是一场全球性的心理战（Psyop），一种旨在对人类大脑进行编程，使其相信并恐惧一个完全幻想的心理行动。

邪教需要一个西方帝国来把人们推向边缘，他们选择了意大利。意大利的“Covid”危机是在伦巴第地区制造的，那里恰好以有毒的空气和呼吸道疾病而闻名。

意大利当局的回应遵循了邪教控制的世界卫生组织强烈建议的中国蓝图。他们对整个国家实施了法西斯式的封锁，在监控无人机的帮助下进行残暴的警察维持。

为了保护“脆弱群体”，我们第一次让健康的人也进行隔离。大多数检测呈阳性的人并没有症状，因为他们并没有问题。这只是一个通过不检测“病毒”的测试而实现的骗局。

## 流感消失了

通过一种并非针对该“病毒”的检测获取你虚幻的“病例”，并将其他死因重新定义为“新冠肺炎”，你就能从一种无非计算机生成的虚构产物中，瞬间获得了一场“大流行”。

由于每年有近亿人出现“流感样”症状，这种潜力是无限的，我们可以看到为什么流感通过被诊断为“新冠肺炎”，在全球迅速且似乎奇迹般地消失了。

“新冠并不局限于肺部疾病。”根据医生的指令，任何在非针对该病毒的检测呈阳性28天内，或更久，死于任何原因的人，都要在死亡证明上写上“新冠肺炎”。

“伴随新冠”而非“死于新冠”的术语被创造出来，以掩盖真相。无论是“伴随”还是“死于”，他们都被列入各国政府编制的死亡人数。

## 费格森因素

当邪教进入2020年3月时，他们面临的问题是，尽管对病例和死亡人数进行了所有操纵，但仍然没有足够的被指称死于“新冠”的人来证明大规模居家禁的合理性。

他们通过科学家描述的方式克服了这一点：可以声称这只是开始，更多的死亡即将来临，以此为借口隔离所有人，然后声称隔离阻止了数百万人的死亡。

尼尔·弗格森教授为第一轮封锁提供了极度错误的借口，预测如果没有严厉封锁，英国将有50万人死亡，美国将有220万。

政客恐慌了，民众恐慌了，于是启动了所谓的“短期”封锁，以“压平曲线”。

## “大流行”在哪里？

约翰斯·霍普金斯大学热内维亚·布里安德（Genevieve Briand）利用美国疾控中心2020年2月初到9月初的官方数据，分析了“新冠肺炎”对美国全因死亡率的影响。

她发现，所谓的“新冠”相关死亡人数超过了心脏疾病的死亡人数。当她注意到2020年所有非“新冠”死亡人数突然下降时，她的研究变得更具意义：

> 其他原因导致的死亡总数减少，几乎完全等于新冠肺炎死亡人数的增加。

医院大量取消了对非“新冠”疾病的治疗和诊断，人们在家里因未诊断和未治疗的癌症、心脏病和其他危及生命的疾病去世，只为了让空医院去处理一个并未发生的“大流行”。

## 21世纪的纳粹优生学

养老院的老人一个月又一个月地与家人隔绝，与亲属和孙辈失去联系。与此同时，他们的医疗档案上被下了“不复苏”（DNR）指令，这样如果他们需要复苏就不会进行，并且“新冠肺炎”会出现在他们的死亡证明上。

老人并没有被“保护”，他们正在被屠杀——实际上是被谋杀。残疾人士和有学习障碍或心理问题的年轻人也被规定了 DNR 指令。

纳粹德国对精神和身体残疾者进行了大屠杀，这一计划被称为“T4行动”。到1941年，超过5,000名儿童被国家杀害，估计T4行动中被杀死的无辜人士总数在27.5万到30万之间。

今天看到关于建立新灭绝营计划的指控被驳回是相当可怜的，因为当前事件背后的相同力量在80年前确实做过那样。

## 医院的神话

医疗工作人员一次又一次告诉我，媒体所谓的“医院像战区一样被挤满”的医院实际上几乎空空如人。

封锁的理由是拯救生命和保护弱势群体，但实际上，他们正在通过DNR指令杀害这些人，并防止空医院被“挤满”。

医院空空是取消对非“新冠”疾病的治疗和诊断的显然结果，而其他疾病则被判了死刑。人们在家里因未诊断和未治疗的癌症、心脏病和其他危及生命的疾病去世，只为了让空医院去处理一个并未发生的“大流行”。

## 口罩掩盖身份

当像苏珊·米奇这样的行为操纵者想要每个人戴口罩时，这与心智控制有关。强制口罩是让当局从字面上控制我们呼吸的空气。

口罩掩盖了我们的说话，让我们不被听见。口罩是一种显而易见的心智控制设备，具有去人性化、消除个性和阻碍情感互动的效果。

## “口罩是犯罪”

格里兹-布里松博士表示，儿童和青少年佩戴口罩会被剥夺大脑发育所需的氧气。她说，缺氧抑制大脑发育，由此造成的损伤无法逆转。

> 我们为此不需要临床研究。这是简单、不争议的生理学。意识并刻意诱发的缺氧是绝对故意的健康危害，也是绝对的医学禁忌。

口罩无法保护你免于并不存在的“病毒”，即使病毒存在，“病毒”颗粒也极其微小，比口罩上的孔洞还要小。

## “新冠疫苗”与女性不孕

辉瑞前副总裁兼首席科学顾问迈克尔·雅登博士和德国的沃尔夫冈·沃达格博士于2020年12月向欧洲管理局提交了申请书，敦促他们在进行进一步研究之前停止针对辉瑞/BioNTech疫苗以及所有其他mRNA试验。

他们特别担心“疫苗”产生的抗体会攻击负责胎盘发育的Syncytin-1蛋白，从而可能影响生育。这将导致接种疫苗的女性出现不孕，且胎盘无法形成。

大量“接种过”女性描述了月经周期的变化，包括血流量增加、经期不规律以及绝经后再次月经——这些都与生殖影响有关。

## 大重置 = 智能电网 = 新人类

邪教特工公开推广“大重置”“重建得更好”以及“重新想象并重置我们的世界”等术语。

计划是将人体和大脑完全整合到智能电网以及人工智能中。我们的一切都被合成操控，包括自然界、食物以及通过合成“疫苗”的人体本身。

人体网络（IoB）是物联网的延伸，基本上通过摄入、植入或以某种方式连接身体的设备将人体连接到网络。一旦连接，数据就可以交换，身体和设备就可以被远程监控和控制。

## 智能电网控制中心

人体正通过“疫苗”和其他方式转变为一种合成半机械人，可以连接到全球智能电网，该电网可以由中心点和其他电网操纵地点进行控制。

以色列是一个国际网络行动中心。以色列网络情报单位拥有大量网络士兵，负责扫描社交媒体、论坛和评论列表，寻找任何挑战邪教议程的人。

## 第十一章

## 谁控制着邪教？

> 醒来吧，起来，否则永远堕落。  
> ——约翰·弥尔顿，《失乐园》

“新冠”骗局是邪教议程的重要组成部分，但只是其一部分。要掌握大局，我们必须将注意力扩展到人类视野范围之外，进入我们无法看到的无限可能之中。

人类的“世界”只是一个极小的频率频段，身体的视觉和感知系统将其解码为对一个“世界”的感知。

## 被盗取的身份

问人们是谁，他们会给你他们的名字、出生地、职业、家庭背景和人生故事。那并不是他们，而是他们正在经历的。

真正的“我”是永恒的“我”，是我们正在经历的。

人体是我们进行这种交互的媒介。身体是一个接收器、发射器和处理器，以一种我们称为“人类”的特定方式处理信息。

邪教想要打破这一循环，并通过技术手段干预，将人类信息场转化为一个将改变我们所定义的人性的场。

## 全息“固态性”

我们的现实不是固态的，它是全息的。二维信息被解码成三维现实，这种现实不是固态的，尽管看起来非常像固态。

人们会问，如果固态是幻象，我们为什么不能穿过墙和彼此？这种力不是固体对固体的；它是电磁场对电磁场，而我们将其解码为固体对固体的碰撞体验。

## 你不知道的事情会伤害你

当你感知到无限现实中一个几乎无法描述的碎片时，总会有更多需要了解的。

邪教及其控制者试图干预频率领域，即五感现实本应与扩展现实相接的领域，并企图将两者隔离开来。

当这种情况发生时，五感的心理和情感过程不再受到扩展意识影响，而是转由身体解码系统的孤立感知驱动。

## 非人类维度

我研究并观察了几个世纪甚至几千年来邪教派特工的来来去去，他们出生、在秘密社团和撒旦网络中工作以推动其议程，然后为了他人死去，以便后继者取代他们。

我寻找这种协调力量，并在宗教文本和古代文化中看到了关于非人类从隐蔽处操纵人类社会的共同主题。

基督教将这种力量称为撒旦、魔鬼和恶魔；伊斯兰教称其为吉尼（Jinn）；古埃及和诺斯底派称其为“执政者”（Archons）。

## Wetiko 因素

Wetiko描述了完全相同的现象：一种试图将五感心灵与扩展意识隔离开来的力量。

Wetiko是雅尔达巴奥的频率失真，试图附着于人类意识并将其吸收为己。一旦建立这种连接，Wetiko就能驱动目标的感知，而他们认为这些感知来自自己的大脑。

邪教是Wetiko的化身，雅尔达巴奥的化身，它试图通过操纵人口进入与其自身匹配的低频状态，来促进Wetiko对人类的彻底同化。

## Wetiko邪教

Wetiko是一个封闭系统，不对外部世界的新信息开放，除非这些信息与其固定、局限的视角相符。

它不关心人类。它不是人类；它只是为了自己的目的而附于人类，其影响可以从极端的精神病态到盲目的服从。

Wetiko最害怕的是人类意识扩张到模拟之外。

## 逃离Wetiko

“反叛者思维”编织了生命与事件的网，并在看似随机的事件中发现共同主题。

无限的意识就是无限的可能性，我们接触的无限可能性越多，变得可能的就越大。

邪教的方法论是将意识隔离在五感现实——即模拟——之中，然后通过旨在设计的终身信息洪流，对该意识进行关于自我和世界的编程，以安装允许全球控制的预期感知。

## 让事情发生

我们不能绝望。在一切结束之前不要绝望，而现在离结束还远得多。

我们必须从看到骗局转向停止配合它。集体组织是其中之一。我们需要从被动转向主动，从目睹事情发生变为让事情发生。

法西斯主义不是由法西斯分子强加的——他们的人数永远不够。法西斯主义是由大众默许法西斯主义而强加的。

我们是多数，他们是少数。

## 最后的思考

爱的力量  
来自上方  
净化我的灵魂  
火焰点燃欲望  
用火焰之舌爱  
净化灵魂  
让爱成为目标

我会保护你免受兜帽爪的伤害  
让吸血鬼远离你的门  
当陷入困境，我会在身边  
带着我永不消灭、无视死的爱着你

嫉妒会伤害自己  
让你变得美丽  
闪光的爱，花朵  
珍珠和漂亮的女孩  
爱像一种能量  
在我体内奔涌奔涌

这一次我们变得崇高  
爱人神圣、神圣、神圣  
爱是危险，爱是快乐  
爱是纯洁——唯一的宝藏

我如此爱你  
净化灵魂  
让爱成为目标

爱的力量  
来自上方  
净化我的灵魂  
爱的力量  
来自上方  
天空的鸽子

火焰点燃欲望  
烈火之吻  
净化灵魂  
让爱成为你的目标

# 弗兰基去好莱坞（Frankie Goes To Hollywood）

## 附录

### Cowan-Kaufman-Morell 关于病毒分离的声明

分离（Isolation）：分离的行为；处于孤立或独立状态的情况或事实；与其他事物或人的分离；孤独。  
——《牛津英语词典》

关于 SARS-CoV-2 病毒是否曾被分离或纯化的争议仍在继续。然而，根据上述定义、常识、逻辑法则和科学准则，任何不偏不倚的人必须得出这样一个结论：SARS-CoV-2 病毒从未被分离或纯化。因此，无法找到关于该病毒存在的任何确认。

这一事实在逻辑、常识和科学上的后果是：

- 某些未被证明存在的事物的结构和组成部分是不可知的，包括任何假设的刺突蛋白或其他蛋白的存在、结构和功能；
- 从未发现过的某物的遗传序列是未知的；
- 未经证明存在的某事物的“变异株”是未知的；
- 无法证明 SARS-CoV-2 导致了名为 Covid-19 的疾病。

用尽可能简洁的语言来说，这里是分离、表征和证明新病毒的正确方法：

首先，从许多患者中提取样本（血液、痰液、分泌物），他们的症状足够独特且具体，足以描述一种疾病。在不将这些样本与任何也含有遗传物质的组织或产品混合的情况下，病毒学家对标本进行粉碎、过滤和超离心，即对样本进行纯化。

这种常用的病毒学技术几十年来一直被每个病毒学实验室用于分离噬菌体和所谓的“巨型病毒”，然后允许病毒学家通过电子显微镜展示出成千上万个大小和形状完全相同的颗粒。这些颗粒就是经过分离和纯化的病毒。

然后，通过物理和/或显微技术检查这些相同颗粒的均匀性。一旦确定了纯度，就可以对颗粒进行进一步的表征。这包括检查颗粒的结构、形态和化学组成。

接下来，通过直接从纯化的颗粒中提取遗传物质，并使用遗传测序技术来表征它们的遗传组成。随后进行分析，以确认这些均匀颗粒正如病毒构想的那样是外源性的，而不是死亡和垂死组织的正常降解产物。

如果我们已经走到了这一步，说明我们已经完全分离、表征并基因测序了一个外源性病毒颗粒。然而，我们仍然必须证明它与疾病有因果关系。

对于 SARS-CoV-2 病毒，这些步骤没有一个被尝试过，而且所有这些步骤都没有在任何所谓的病原病毒中成功执行过。我们的研究表明，医学文献中不存在显示这些步骤的单一研究。

相反，自1954年以来，病毒学家从少数患有类似疾病的人身上获取未纯化的样本。然后他们对该样本进行最小程度的处理，并将这种未纯化的样本接种到含有通常四到六种材料的组织培养中——所有这些材料都含有与所谓的“病毒”相同的遗传物质。

组织培养被饥饿和毒化，并自然解体成许多类型的颗粒，其中一些含有遗传物质。违背了所有常识、逻辑、英语语言的使用和科学诚信，这一过程被称为“病毒分离”。

这种含有来自许多来源的遗传物质片段的混合物随后经过遗传分析，然后在计算机模拟过程中创建了据称病毒的序列，即所谓的“体外基因组”（*in silico genome*）。在没有任何时候通过电子显微镜确认过真实的病毒序列。这是科学欺诈。

观察到，未纯化的样本与毒性抗生素、牛胎组织、羊水和其他组织一起接种到组织培养中，破坏了其接种的肾脏组织，这被作为病毒存在和致病性的证据。这是科学欺诈。

## 索引

### A

- 虐待关系
  - 自归其责
  - 孩子们
  - 阴谋论
  - 家庭虐待
  - 经济虐待与依赖
  - 孤立
  - 身体虐待
  - 心理虐待
  - 虐待的迹象
- 上瘾
  - 酒精症
  - 频率
  - 物质滥用
  - 技术
- 阿德尔森，谢尔顿
- 议程21/2030（联合国）
- 艾滋病/HIV病毒
- 逆转录病毒
- 外星人/地外生物
- 铝
- 亚马逊
- 放大循环
- 过敏性休克
- 动物
- 抗体
- 反法西斯组织（Antifa）
- 抗原
- 反犹太主义
- 执政者（Archons）
- 意识
- 能量
- 意念（ennoia）
- 基因操控
- 倒置
- 封锁
- 金钱
- 辐射
- 宗教
- 技术
- Wetiko因素
- 人工智能（AI）
- 机器人军队
- 人类2.0
- 互联网
- 英国药品和医疗用品管理局（MHRA）
- 莫格伦体纤维
- 智能电网
- 新冠肺炎
- 航空业

### B

- 银行、金融与货币
- 2008年危机
- 繁荣与衰退
- 无现金数字货币系统
- 中央银行
- 信贷
- 数字货币
- 准备金贷款
- 大重置（Great Reset）
- 保障收入
- 收入的毁灭
- 利率
- 百分之一
- 骗局
- 英国广播公司（BBC）
- 行为洞察团队（BIT）
- 拜登，亨特
- 拜登，乔
- 制药巨头
- 胆固醇
- 医疗专业人员
- 疫苗
- 世界卫生组织（WHO）
- 比尔和梅琳达·盖茨基金会
- 亿万富翁
- 禽流感（H5N1）
- 黑人命也是命（BLM）
- 布莱尔，托尼
- 布林，谢尔盖
- 大英帝国
- 布什，乔治·老布什
- 布什，乔治·小布什
- 伯德，罗伯特

### C

- 加拿大
- 全球邪教
- 仇恨言论
- 关押
- 口罩
- 老人
- SARS-CoV-2
- 卫星
- 疫苗
- 可穿戴技术
- 国会山骚乱
- 煽动探员
- 反法西斯组织（Antifa）
- 黑人命也是命（BLM）
- QAnon
- 缺乏安全预防措施
- 二氧化碳
- 养老院
- 无现金数字货币系统
- 审查
- 事实查核员
- 媒体
- 私人消息
- 社交媒体
- 跨性别者
- 美国疾病控制中心（CDC）
- 中心化
- 脉轮
- 变革者
- 化学尾迹
- 首席医疗官和科学顾问
- 孩子们
- 社交距离与孤立
- 中国
- 鼻拭子检测
- 中国革命
- 数字货币
- 全球邪教
- 保障收入
- 帝国学院
- 以色列
- 封锁
- 免疫危机
- 病毒起源
- 智能电网
- 社会信用体系
- 检测
- 胆固醇
- 基督教
- 死亡文本
- 死海
- 罗马教会
- 撒旦
- 气候
- 议程21/2030
- 二氧化碳
- 绿色计划
- 绿色党
- 免疫者
- 执政者
- 计算机模型
- 法律
- DNA
- 数字
- 不复苏指令（DNR）
- 家庭虐待
- 新冠肺炎的降级
- 罗伯特·德罗斯滕
- 彼得·杜斯伯格

### D

- DARPA（国防高级研究计划署）
- 死亡
- 养老院
- 证书
- 死亡率
- 尸检
- 欺骗金字塔
- 记录
- 解码
- 非人性化
- 德尔菲技术
- 民主
- 依赖
- 笛卡尔，勒内
- DNA
- 数字
- 不复苏指令（DNR）
- 家庭虐待
- 新冠肺炎的降级
- 克里斯蒂安·德罗斯滕
- 彼得·杜斯伯格

### E

- 经济虐待
- 约翰·埃德蒙斯
- 教育
- 电磁频谱
- 约翰·恩德斯
- 能量
- 艾普斯坦，杰弗里
- 永恒
- 环氧乙烷
- 欧洲联盟
- 事件201
- 外泌体
- 心
- 无限性
- 自我身份
- 模拟理论
- 疫苗
- Wetiko因素
- 矛盾的规则
- 化学尾迹
- Corman-Drosten测试
- 模仿

### F

- Facebook
- 事实查核员
- 安东尼·福奇
- 恐惧
- 气候变化
- 计算机模型
- 阴谋论
- 空荡的医院
- 意大利
- 封锁
- 口罩
- 媒体
- 医护人员
- 心理战
- Wetiko因素
- 女性不孕
- 费米悖论
- 尼尔·弗格森
- 生殖能力下降
- 场
- 五感
- 执政者
- 教育
- 无限
- 超自然
- 感知编程
- 幻影自我
- 灵性（pneuma）
- 自我认同
- Wetiko因素

### G

- 罗伯特·加洛
- 比尔·盖茨
- 全球邪教
- 反人类
- 黑人命也是命
- 中国
- 气候变化骗局
- 新冠肺炎
- 法西斯主义
- 地理上的起源
- 移民
- 互联网
- 主流媒体
- 口罩
- 媒体
- 以色列
- 非人类维度
- 感知
- 政党
- 金字塔型等级制度
- 桑巴提-法兰克主义
- 科学
- 蜘蛛与网
- 跨性别者
- 疫苗
- 觉醒文化
- 世界经济论坛
- 共同目标
- 联合生物安全中心

### H

- 马特·汉考克
- 洗手液
- 心脏
- 群体思维
- 全息图
- 医院
- 人类2.0
- 人工智能
- 纳米技术
- 大重置
- 跨性别主义
- 疫苗
- 人类牺牲
- 饥饿游戏社会
- 奥尔德斯·赫胥黎
- 身份政治
- 幻象现实
- 移民
- 英国
- 反犹太主义
- 犹太人
- 倒置
- 以色列
- 以色列-巴勒斯坦冲突
- 劳工党
- 纳粹德国
- 萨巴提教
- 硅谷
- 妥拉法
- 美国
- 犹太主义者

### K

- 安德鲁·考夫曼
- 知识
- 柯赫假设
- 雷·库兹韦尔
- 贾雷德·库什纳

### L

- 劳工党
- 斯特凡·兰卡
- 快速抗原检测设备（LFD）
- 保罗·列维
- 生命计划
- 约翰·马古富利
- 主流媒体
- 英国
- 审查
- 中国
- 气候变化骗局
- 恐惧
- 全球邪教
- 独立新闻
- 英国通信委员会（Ofcom）
- 约翰逊，鲍里斯
- 联合生物安全中心

### M

- 凯莉·梅德
- 主流媒体
- 审查
- 中国
- 气候变化骗局
- 恐惧
- 全球邪教
- 独立新闻
- 英国通信委员会（Ofcom）
- 认知
- 心理战
- 萨巴提教徒
- 社会不认可
- 社交距离与隔离
- 美国
- 疫苗
- 毛泽东
- 马克思与马克思主义
- 阳刚气
- 口罩
- 审查
- 儿童
- 去人性化
- 流感
- 缺氧
- 警察
- 污染
- 风险评估
- 自尊
- 外科医生
- 韦提科因素
- “虫子”
- 《黑客帝国》
- 麻疹
- 英国药品和保健产品监管局（MHRA）
- 美索不达米亚
- 信息传递
- 军警国家
- 脑控制
- MKUltra
- 君主制
- 钱
- 卢克·蒙塔尼耶
- 贝尔·莫尼
- 莫格伦病
- 死亡率
- 凯里·穆利斯
- 埃隆·马斯克

### N

- 纳格·哈马迪文献
- 纳米技术
- 自恋症
- 纳粹德国
- 濒死体验
- 新保守主义

### O

- 巴拉克·奥巴马
- 凯西·奥布莱恩
- 埃维塔·奥切尔
- 英国通信委员会（Ofcom）
- 老人
- 一元性
- 开放社会基金会
- 氧气

### P

- 恋童癖
- 拉里·佩奇
- 巴勒斯坦-以色列冲突
- 大流行定义
- 大流行模拟
- 超自然
- PCR检测
- 珍珠港袭击
- 南希·佩洛西
- 认知
- 气候变化骗局
- 控制
- 解码
- 奴役化
- 五感
- 心理战
- 政党
- 警察
- 黑人命也是命
- 暴行
- 公民逮捕
- 普通法逮捕
- 共同目标
- 封锁
- 口罩
- 军警国家
- 精神变态人格
- 重新框架
- 美国
- 觉醒
- 脊髓灰质炎
- 政治正确
- 政治傀儡
- 污染
- 尸检
- 邮票共识
- 预设性编程
- 问题-反应-解决方案
- 新美国世纪计划
- 心灵能量
- 反击者
- 金字塔结构

### Q

- QAnon

### R

- 反种族主义行业
- 阶级
- 批判性种族理论
- 文化
- 反向种族主义
- 白人特权
- 白人至上主义
- 辐射
- 随机性
- 代理人
- 气候变化
- 共同计划
- 规则
- 执法者
- 口罩
- 警察
- 韦提科因素
- 觉醒
- 执政者
- 意识
- 控制
- 五感
- 善与恶
- 隐藏的非人类力量
- 萨巴提教徒
- 救我情结
- 重复
- 告密
- 蜥蜴人/灰色实体
- 重塑大脑
- 汤姆斯·米尔顿·里弗
- 洛克菲勒家族
- 罗马帝国
- 罗斯柴尔德家族
- RT-PCR检测
- 9/11袭击
- 英国第77旅
- 科学应急咨询小组
- SARS-CoV-1
- SARS-CoV-2
- 低地轨道卫星
- 沙特阿拉伯
- 社会不认可
- 社交距离与隔离
- 虐待关系
- 自杀与自残
- 猪流感
- 同步性
- 合成生物学
- 合成肉

### T

- 技术
- 执政者
- 云
- 网络行动
- 网络战
- 辐射
- 社交距离
- 技术统治主义
- 谭德罗斯·阿哈诺姆·格布耶西斯
- 读心术
- 谢莉·滕佩尼
- 特斯拉
- 睾酮水平下降
- 新冠检测
- 肛拭子检测
- 癌症
- 中国
- 科曼-德罗斯滕
- 死亡证明
- 欺诈检测
- 遗传材料扩增
- 侧流免疫层检测（LFD）
- PCR检测
- 疫苗
- 格蕾塔·通贝里
- 极权主义踮脚
- 跨性别者
- 贾斯汀·特鲁多
- 唐纳德·特朗普

### U

- 英国专栏
- 联合国
- 美国
- 美国革命
- 边界
- 国会山骚乱
- 儿童
- 中国
- 中央情报局（CIA）
- 人口统计变化
- 民主党
- 选举欺诈
- 极右翼国内恐怖分子
- 联邦储备体系
- 流感和呼吸道疾病统计
- 全球邪教
- 洗手消毒剂
- 移民
- 弹劾
- 以色列
- 犹太教
- 封锁
- 口罩
- 大众媒体
- 养老院
- 五角大楼
- 警察
- 反击者
- 共和党
- 俄罗斯
- 萨巴提人
- 2001年9月11日恐怖袭击
- UFO目击
- 疫苗
- 白人至上主义
- 觉醒民主党

### V

- 疫苗
  - 不良反应
  - 非洲
  - 过敏性休克
  - 动物
  - 反疫苗运动
  - 阿斯利康/牛津
  - 自身免疫性疾病
  - 制药巨头
  - 生物武器
  - 黑人和少数族裔社区
  - 血栓
  - 脑机接口
  - 养老院死亡
  - 审查
  - 首席医疗官和科学顾问
  - 中国
  - 临床试验
  - 补偿
  - 强制接种
  - 计算机程序
  - 意识
  - 掩盖
  - 细胞因子风暴
  - 疫苗导致的死亡和疾病
  - 定义
  - 发展中国家
  - 数字纹身
  - DNA操纵
  - 紧急批准
  - 女性不孕
  - 资金
  - 遗传自杀
  - 全球邪教
  - 犹太主义
  - 人类2.0
  - 免受起诉保护
  - 可植入技术
  - 以色列
  - 强生公司
  - 封锁
  - 长期影响
  - 主流媒体
  - 口罩
  - 英国药品和医疗用品监管局
  - Moderna
  - 信使RNA疫苗
  - 纳米技术
  - 英国国家医疗服务体系
  - 老年人
  - 操作系统
  - 护照
  - 辉瑞/BioNTech
  - 聚乙二醇
  - 孕妇
  - 反社会人格
  - 种族
  - 逆转录
  - 智能电网
  - 社交距离
  - 社交媒体
  - 不育能力
  - 合成材料
  - 检测
  - 旅行限制
  - 变异株
  - 病毒存在
  - 吹哨人
  - 世界卫生组织
  - 觉醒文化
  - 工作
  - 年轻人
  - 帕特里克·瓦兰斯
  - 虚拟现实
  - 视觉现实
  - 维生素D
  - 沃纳·冯·布劳恩

### W

- 战区医院传闻
- 波形
- 财富
- 湿货市场阴谋
- Wetiko
- 酒精症和成瘾
- 全球邪教
- 执政者
- 人工智能
- 制药巨头
- 儿童
- 中国
- 意识
- 情绪
- 事实
- 法西斯主义
- 群体思维
- 移民
- 原住民团结
- 反转
- 左翼劫持
- 马克思主义
- 脑控制
- 觉醒文化
- 感知编程
- 幻影自我
- 警察削减经费
- 重构
- 公共机构
- 反击者
- 种族主义
- 宗教
- 萨巴提人
- 硅谷
- 跨性别
- 美国
- 疫苗
- 年轻人
- 女性权利和地位的剥夺
- 世界经济论坛
- 世界卫生组织
- 艾滋病/HIV
- 扩增循环
- 资金
- 互联网
- 封锁
- 维提科
- 世界第一号
- 世界第二号
- Wi-Fi
- 维基百科
- 沃杰西基，苏珊
- 谁获益

### Z

- 塔尔·扎克斯
- 锡安主义
- 马克·扎克伯格
- 祖鲁人

# ICKONIC

## 替代方案

Ickonic 是我过去5年以来的梦想。在替代性信息的环境中成长起来，我对世界上正在发生的事情以及我可以做些什么来使其变得更好一直保持着天然的兴趣。

在主要由那些不努力让事情变得更好的人占据的各种主题和影响力领域中，媒体一直让我感到最沮丧也最着迷。主要是因为如果媒体能正确履行其职责，那么世界上发生的许多负面事件根本就不可能发生，因为它们会在瞬间暴露无形。

新闻自由以及互联网可能提供的机会，意味着媒体能够以前所未有的方式揭露真相，并让人对自己的行为负责。众所周知，我们身边存在着一些“不可触碰者”，媒体根本不会触碰、暴露或调查他们，这导致了渗透到全球权力机构之中的黑暗地下世界。

是时候来一些不同的东西了，一种不同的媒体，在这里没有人处于被曝光和调查之外。在 Ickonic，我们关心的只是无论我们报道哪个主题，世界上真实发生的真相。

我们希望你喜欢我们创造的内容，并能从这个平台有所收获。我们的目标是提供具有启发性且最重要的是能赋予力量的信息，你不是一个渺小的人，你是比这大得多的一部分。

是时候……

Jaymie Icke——替代媒体创始人

# 现在就 ICKONIC.COM 注册

# DAVID ICKE（大卫·艾克）

## 答案

![](img/01cc8d6667542262308c820b3f5bd37b_1832_0.png)

我们生活在一个非凡的时代，数十亿人感到困惑，并为正在发生的事情寻找答案。David Icke 是一个又一次被证明是正确的男人，花了30年揭示世界事务背后的真相，并在之前的系列书中预测了当前的时事。

《答案》（*The Answer*）将改变你对生活和世界的认知，并让你从控制人类社会的幻想中解放出来。对于我们共同的自由来说，没有什么比人类意识到书中的内容更重要的了。

现已在 `davidicke.com` 发售。

# 触发点

## 改变世界的谎言

- 究竟是谁干的？
- 为什么？

# DAVID ICKE

![](img/01cc8d6667542262308c820b3f5bd37b_1833_0.png)

![](img/01cc8d6667542262308c820b3f5bd37b_1834_0.png)

# DAVIDICKE.COM

![](img/01cc8d6667542262308c820b3f5bd37b_1835_0.png)

## DAVID ICKE 商店

- 最新新闻文章
- DAVID ICKE 视频
- 每周点播播客
- 直播活动

`www.davidicke.com`

# DAVID ICKE 的生平

# 叛逆者（RENEGADE）

`/rɛnɪɡeɪ/`

**名词**

一个以反叛且不合传统的方式行为的人。

# 长篇电影

![](img/01cc8d6667542262308c820b3f5bd37b_1836_0.png)

现已在 `davidicke.com` 发售。

# 猎户座之门

意识的符号与控制蓝图

- 猎户座对人类影响的故事

## 2本新书

NEIL HAGUE 著

尖端视觉艺术与独特的插图书。

# 病毒医生宇宙

云端中的冒险

# NEIL HAGUE

购买书籍、版画和T恤，请访问：

- `neilhaguebooks.com`
- `neilhague.com`

![](img/01cc8d6667542262308c820b3f5bd37b_1837_0.png)

# 在你离开之前……

关于《叛逆者思维认知》（Perceptions of a Renegade Mind）中主题的更多细节、背景和证据——以及更多——请查看我的其他书籍，包括：

- 《真理将使你自由》（*And The Truth Shall Set You Free*）
- 《最大的秘密》（*The Biggest Secret*）
- 《矩阵之子》（*Children of the Matrix*）
- 《大卫·艾克全球阴谋指南》（*The David Icke Guide to the Global Conspiracy*）
- 《时间循环中的故事》（*Tales from the Time Loop*）
- 《认知欺骗》（*The Perception Deception*）
- 《记住你是谁》（*Remember Who You Are*）
- 《人类，别下跪了》（*Human Race Get Off Your Knees*）
- 《幻影自我》（*Phantom Self*）
- 《你需要的一切但被告知的》（*Everything You Need To Know But Have Never Been Told*）
- 《触发点》（*The Trigger*）
- 《答案》（*The Answer*）

你可以订阅 Ickonic 媒体平台，那里有数百小时涵盖各种主题的尖端视频、纪录片和剧集，每周都会更新。这包括我每周五对本周新闻进行的90分钟深度解析，用以解释发生的原因以及目的是何在。
