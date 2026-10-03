
# Java® 语言规范

- 8.8.2 构造函数签名 281
- 11.2.3 异常检查 374
- 11.3 异常的运行时处理 376

# 12 执行 381

- 12.1 Java 虚拟机启动 381
- 12.1.1 加载类 Test 382
- 12.1.2 链接 Test：验证、准备、（可选的）解析 382
- 12.1.3 初始化 Test：执行初始化器 383
- 12.1.4 运行 Test.main 384
- 12.2 类和接口的加载 384
- 12.2.1 加载过程 385
- 12.3 类和接口的链接 386
- 12.3.1 二进制表示形式的验证 386
- 12.3.2 类或接口类型的准备 387
- 12.3.3 符号引用的解析 387
- 12.4 类和接口的初始化 389
- 12.4.1 何时发生初始化 389
- 12.4.2 详细的初始化过程 392
- 12.5 新实例的创建 394
- 12.6 类实例的终结 397
- 12.6.1 实现 final 399
- 12.6.2 与内存模型的交互 400
- 12.7 类和接口的卸载 402
- 12.8 程序退出 403

# 13 二进制兼容性 405

- 13.1 二进制的格式 406
- 13.2 什么是二进制兼容性不是什么 413
- 13.3 包和模块的演进 413
- 13.4 类的演进 414
- 13.4.1 abstract 类 414
- 13.4.2 final 类 415
- 13.4.3 public 类 415
- 13.4.4 超类和超接口 415
- 13.4.5 类型参数 417
- 13.4.6 类体和成员声明 417
- 13.4.7 成员和构造函数的访问 419
- 13.4.8 字段定义 420
- 13.4.9 final 字段和静态常量变量 422
- 13.4.10 static 字段 423
- 13.4.11 transient 字段 423
- 13.4.12 方法和构造函数的声明 424
- 13.4.13 方法和构造函数的类型参数 424
- 13.4.14 方法和构造函数的形式参数 425
- 13.4.15 方法结果类型 426
- 13.4.16 abstract 方法 426
- 13.4.17 final 方法 427
- 13.4.18 native 方法 427
- 13.4.19 static 方法 428
- 13.4.20 synchronized 方法 428
- 13.4.21 方法和构造函数的 Throws 428
- 13.4.22 方法和构造方法体 428
- 13.4.23 方法和构造函数的重载 429
- 13.4.24 方法重写 430
- 13.4.25 静态初始化器 430
- 13.4.26 枚举的演进 430
- 13.5 接口的演进 430
- 13.5.1 public 接口 430
- 13.5.2 超接口 431
- 13.5.3 接口成员 431
- 13.5.4 接口类型参数 431
- 13.5.5 字段声明 432
- 13.5.6 接口方法声明 432
- 13.5.7 注解类型的演进 433

# 14 块和语句 435

- 14.1 语句的正常和异常完成 435
- 14.2 块 437
- 14.3 局部类声明 437
- 14.4 局部变量声明语句 439
- 14.4.1 局部变量定义和类型 440
- 14.4.2 变量声明的执行 442
- 14.5 语句 442
- 14.6 空语句 444
- 14.7 标记语句 444
- 14.8 表达式语句 445
- 14.9 if 语句 446
- 14.9.1 if-then 语句 447
- 14.9.2 if-else 语句 447
- 14.10 assert 语句 448
- 14.11 switch 语句 451
- 14.11.1 switch 块 451
- 14.11.2 一个 switch 块 454
- 14.11.3 一个 switch 语句的执行 454
- 14.12 while 语句 457
- 14.12.1 while 语句的异常完成 458
- 14.13 do 语句 458
- 14.13.1 do 语句的异常完成 459
- 14.14 for 语句 460
- 14.14.1 基础 for 语句 461
- 14.14.1.1 for 语句的初始化 461
- 14.14.1.2 for 语句的迭代 462
- 14.14.1.3 for 语句的异常完成 463
- 14.14.2 增强型 for 语句 464
- 14.15 break 语句 467
- 14.16 continue 语句 469
- 14.17 return 语句 471
- 14.18 throw 语句 472
- 14.19 synchronized 语句 474
- 14.20 try-catch 的执行 479
- 14.20.1 try-finally 和 try-catch-finally 480
- 14.20.2 try-with-resources 482
- 14.20.3 基础 try-with-resources 484
- 14.20.3.2 扩展 try-with-resources 487
- 14.21 yield 语句 488
- 14.22 不可达语句 489

# 15 表达式 497

- 15.1 求值、标记和结果 497
- 15.2 表达式的形式 498
- 15.3 表达式的类型 499
- 15.4 FP 表达式 500
- 15.5 表达式和运行时检查 501
- 15.6 求值的正常和异常完成 502
- 15.7 求值顺序 504
- 15.7.1 求值左操作数 504
- 15.7.2 括号之前的操作数 507
- 15.7.3 优先级的求值 507
- 15.7.4 从右求值的参数列表 508
- 15.7.5 其他表达式的求值顺序 509
- 15.8 原始表达式 509
- 15.8.1 词法字面量 510
- 15.8.2 类字面量 511
- 15.8.3 this 512
- 15.8.4 限定的 this 513
- 15.8.5 括号化表达式 513
- 15.9 类实例表达式 514
- 15.9.1 确定实例化的类 516
- 15.9.2 确定封闭实例 517
- 15.9.3 选择构造函数及其参数 519
- 15.9.4 类实例化的运行时求值 524
- 15.9.5 匿名类声明 525
- 15.9.5.1 匿名构造函数 526
- 15.10 数组创建和访问 527
- 15.10.1 数组创建表达式 527
- 15.10.2 数组创建表达式的运行时求值 532
- 15.10.3 数组访问表达式 532
- 15.10.4 数组访问表达式的运行时求值 532
- 15.11 字段访问表达式 535
- 15.11.1 使用原始操作数的字段访问 535
- 15.11.2 使用 super 访问超类成员 538
- 15.12 方法调用表达式 540
- 15.12.1 编译阶段步骤1：确定要搜索的类或接口 541
- 15.12.2 编译阶段步骤2：确定方法签名 543
- 15.12.2.1 第一阶段：识别潜在可选的方法 549
- 15.12.2.2 第二阶段：通过严格调用识别的参数个数匹配的方法的方法 552
- 15.12.2.3 第三阶段：通过松散调用识别的参数个数匹配的方法 553
- 15.12.2.4 第四阶段：通过可变参数个数调用识别方法 554
- 15.12.2.5 选择最具体的方法 554
- 15.12.2.6 方法调用类型 559
- 15.12.3 编译阶段步骤3：所选方法合适吗？ 560
- 15.12.4 方法调用的运行时求值 563
- 15.12.4.1 计算目标（如果） 563
- 15.12.4.2 求值参数 565
- 15.12.4.3 检查类型和方法的可访问性 566
- 15.12.4.4 定位要调用的方法 567
- 15.12.4.5 创建栈帧，传递控制 571
- 15.13 表达式 573
- 15.13.1 编译时确定 576
- 15.13.2 方法的类型 582
- 15.13.3 运行时求值 584
- 15.14 后缀表达式 587
- 15.14.1 后缀 ++ 587
- 15.14.2 后缀 -- 588
- 15.14.3 前缀 + 589
- 15.14.4 前缀 - 590
- 15.14.5 按位取反 ~ 592
- 15.14.6 逻辑取反 ! 593
- 15.15 表达式 593
- 15.15.1 乘法运算符 * 595
- 15.15.2 除法运算符 / 597
- 15.15.3 取模运算符 % 598
- 15.16 加法运算符 600
- 15.16.1 字符串拼接 + 601
- 15.16.2 算术运算符 - 606
- 15.17 移位运算符 606
- 15.18 比较运算符 607
- 15.18.1 关系运算符 <, >= 607
- 15.18.2 类型运算符 instanceof 609
- 15.18.3 等于运算符 == 610
- 15.18.4 不等于运算符 != 611
- 15.19 按位运算符 612
- 15.19.1 按位与运算符 & 612
- 15.19.2 按位或运算符 | 613
- 15.20 逻辑与运算符 && 614
- 15.21 逻辑或运算符 || 615
- 15.22 三元运算符 ? : 616
- 15.22.1 布尔值条件表达式 623
- 15.22.2 算术条件表达式 623
- 15.22.3 引用条件表达式 624
- 15.23 赋值运算符 625
- 15.23.1 简单赋值运算符 = 626
- 15.23.2 复合赋值运算符 632
- 15.24 Lambda 表达式 638
- 15.24.1 Lambda 参数 640
- 15.24.2 Lambda 主体 644
- 15.24.3 Lambda 表达式的类型 647
- 15.24.4 Lambda 表达式的运行时求值 649
- 15.25 switch 表达式 650
- 15.25.1 一个 switch 块 651
- 15.25.2 switch 表达式的运行时求值 652
- 15.26 常量赋值 654

# 16 确定赋值 657

- 16.1 确定赋值和表达式 663
- 16.1.1 布尔值确定表达式 663
- 16.1.2 逻辑与运算符 && 663
- 16.1.3 逻辑或运算符 || 664
- 16.1.4 逻辑取反运算符 ! 664
- 16.1.5 三元运算符 ? : 664
- 16.1.6 switch 表达式 665
- 16.1.7 其他布尔类型的确定表达式 668
- 16.1.8 赋值表达式 668
- 16.1.9 运算符 ++ 和 -- 668
- 16.1.10 其他表达式 669
- 16.2 确定赋值和语句 670
- 16.2.1 空语句 670
- 16.2.2 块 670
- 16.2.3 局部类声明语句 672
- 16.2.4 局部变量声明语句 672
- 16.2.5 标记语句 672
- 16.2.6 表达式语句 673
- 16.2.7 if 语句 673
- 16.2.8 assert 断言语句 673
- 16.2.9 switch 语句 674
- 16.2.10 while 语句 674
- 16.2.11 do 语句 675
- 16.2.12 for 语句 675
- 16.2.12.1 for 语句的初始化部分 676
- 16.2.12.2 for 语句的增量部分 677
- 16.2.13 break, continue, return 和 throw 语句 677
- 16.2.14 synchronized 语句 677
- 16.2.15 try 语句 677
- 16.3 确定赋值与参数 679
- 16.4 确定赋值与数组初始化器 679
- 16.5 确定赋值与枚举常量 680
- 16.6 确定赋值与匿名类 680
- 16.7 确定赋值与成员类型 681
- 16.8 确定赋值与静态初始化器 681
- 16.9 确定赋值、构造方法与初始化器 682

# 17 线程 685

- 17.1 同步化 686
- 17.2 等待与通知 686
- 17.2.1 等待 687
- 17.2.2 通知 689
- 17.2.3 中断 689
- 17.2.4 等待、通知与中断 690
- 17.3 休眠 690
- 17.4 内存模型 691
- 17.4.1 共享变量 694
- 17.4.2 动作 694
- 17.4.3 程序顺序 695
- 17.4.4 同步顺序 696
- 17.4.5 发生之前的顺序 697
- 17.4.6 执行 700
- 17.4.7 格式良好的执行 701
- 17.4.8 可观测执行 701
- 17.4.9 非终止的执行 704
- 17.5 语义 706
- 17.5.1 执行的语义 708
- 17.5.2 构造的语义 709
- 17.5.3 修改的语义 709
- 17.5.4 类的语义 710
- 17.6 释放 711
- 17.7 双精度 712

# 18 类型推理 713

- 18.1 概念与符号 714
- 18.1.1 变量 714
- 18.1.2 表达式 715
- 18.1.3 边界 715
- 18.2 归纳 717
- 18.2.1 兼容性 717
- 18.2.2 类型兼容性 722
- 18.2.3 子类型化 723
- 18.2.4 等价性 725
- 18.2.5 异常 726
- 18.3 组合 728
- 18.3.1 边界对 729
- 18.3.2 涉及边界的转换 730
- 18.4 分类 733
- 18.5 使用 733
- 18.5.1 调用适用性 733
- 18.5.2 类型调用 735
- 18.5.2.1 方法调用兼容性 735
- 18.5.2.2 参数兼容性 737
- 18.5.3 泛接口参数化 742
- 18.5.4 更具体的方法推理 743

# 19 语法 747

# 限制许可授予 775

# 第1章 引言

Java® 语言是一种通用的、并发的、基于类的、面向对象的语言。它的设计非常简单，使得许多程序员都能精通。Java 语言与 C 和 C++ 有关，但组织方式不同，省略了 C 和 C++ 的某些方面，并包含了一些其他语言的想法。它旨在成为一种生产语言，而不是研究语言，正如 C. A. Hoare 在关于语言设计的经典论文中所建议的那样，该设计避免了引入未经测试的特性。

Java 语言是强静态类型的。本规范明确区分了编译时可以且必须检测的错误，以及运行时发生的错误。编译通常包括将程序翻译成机器无关的字节码表示。运行时活动包括执行程序所需的类的加载和链接、可选机器码生成和动态优化，以及程序的实际执行。

Java 语言是一种相对高级的语言，无法通过语言获取机器表示的细节。它包含了自动存储管理（通常使用垃圾回收器），以避免显式释放内存（如 C 中的 `free` 或 C++ 中的 `delete`）带来的安全问题。

可以声明一个 `finalize` 方法，该方法将在对象被垃圾回收器回收之前调用，允许对象清理其状态。

为了简单起见，该语言既没有独立于类实现的声明“头文件”，也没有独立的类型和类层次层级结构。

类的一种特殊形式——枚举（enums），支持对小范围值集合的定义并以类型安全的方式对其进行操作。与其他语言中的枚举不同，枚举是对象，并且可以拥有自己的方法。

第 9 章描述了接口（interfaces）。接口的成员包括类、接口、常量字段和方法。互不相关的类可以实现同一个接口。接口类型的变量可以包含任何实现该接口对象的引用。

类和接口支持对接口的多重继承。实现一个或多个接口的类可以从其父类和多个父接口中同时继承实例方法。

注解类型（Annotation types）是用于标记声明的特化接口。这些注解不允许以任何方式影响 Java 编程语言的语义。然而，它们为各种工具提供了输入。

第 10 章描述了数组（arrays）。数组访问包括边界检查。数组是动态创建的对象，可以赋值给 `Object` 类型的变量。该语言支持数组数组，而不是多维数组。

第 11 章描述了异常（exceptions），异常是非恢复的，并与语言语义及并发机制完全集成。异常有三种：受检查异常（checked exceptions）、运行时异常（run-time exceptions）和错误（errors）。编译器通过确保受检查异常被正确处理，要求方法或构造函数只有在声明的情况下才能产生受检查异常。这提供了编译时检查以确保异常处理程序存在，有助于大型编程。大多数用户定义的异常应该是受检查异常。Java 虚拟机检测到程序中的无效操作会导致运行时异常，例如 `NullPointerException`。Java 虚拟机检测到的失败会导致错误，例如 `OutOfMemoryError`。大多数简单的程序并不尝试处理错误。

## 第2章 词与符号

## 第3章 语法

## 第4章 类型

## 第5章 转换与提升

## 第6章 声明与命名

## 第7章 程序结构

## 第8章 类

# 规范结构



# 第 12 章

第 12 章描述了程序执行期间发生的活动。程序通常存储为表示编译后的类和接口的二进制文件。这些二进制文件可以被加载到 Java 虚拟机中，与其他类和接口链接并进行初始化。

初始化之后，可以使用类方法和类变量。某些类可以实例化以创建该类类型的新对象。作为类实例的对象还包含该类每个父类的实例，且对象的创建涉及这些父类实例的递归创建。

当对象不再被引用时，它会被垃圾回收器回收。如果一个对象声明了终结器（finalizer），则该终结器会在对象回收其最后清理否则不会释放的资源的机会之前执行。当一个类不再被需要时，它可能会被卸载。

# 第 13 章

第 13 章描述了二进制兼容性（binary compatibility），规定了类型更改对未重新编译的其它类型的影响。这些考虑对于那些准备通过互联网以连续系列版本广泛分发的类型开发者来说具有意义。良好的程序开发环境每当类型发生变化时会自动重新编译依赖代码，因此大多数程序员不需要担心这些细节。

# 第 14 章

第 14 章描述了代码块（blocks）和语句（statements），它们基于 C 和 C++。该语言没有 `goto` 语句，但包含了带标签的 `break` 和 `continue` 语句。与 C 不同，Java 编程语言要求在控制流语句中使用布尔（或 `Boolean`）表达式，并且不会隐式地将类型转换为布尔类型（通过自动拆箱除外）。`synchronized` 语句提供了基本的对象层级监视器锁。`try` 语句可以包含 `catch` 和 `finally` 子句，以防止非局部控制传递。

# 第 15 章

第 15 章描述了表达式（expressions）。本文完整规范了表达式求值的（表面的）顺序，以增加确定性和可移植性。重载的方法和构造函数在编译时通过从所有可用的方法或构造函数中选择最具体的一个来解析。

# 第 16 章

第 16 章描述了语言如何确保局部变量在使用前已明确设置。虽然所有其他变量都会自动初始化为默认值，Java 编程语言不会自动初始化局部变量以避免掩盖编程错误。

# 第 17 章

第 17 章描述了线程（threads）和锁（locks）的语义，它们基于最初随 Mesa 编程语言引入的基于监视器的并发机制。Java 编程语言使用用于共享内存多处理器的内存模型，支持高性能实现。

# 第 18 章

第 18 章描述了各种类型推断算法，用于测试泛型方法的适用性，并在泛型方法调用中推断类型。

# 第 19 章

第 19 章给出了该语言的语法。

## 1.2 示例程序

文中给出的大多数示例程序都可以执行，且其形式类似于：

```
class Test {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            System.out.print(i == 0 ? "" : " " + args[i]);
        }
        System.out.println();
    }
}
```

在安装了 Oracle JDK 的机器上，存储在 `Test.java` 文件中的程序可以通过命令进行编译和执行：

```
javac Test.java
java Test Hello, world.
```

产生输出：

Hello, world.

## 1.3

在整个规范中，我们引用 Java 平台 API 的类和接口。

预览特性可能与 Java SE Platform API 的元素相关。具体而言，如果一个 API 元素存在于 `java.lang` 或 `java.lang.annotation` 包中，则该元素是必要的（essential），且在不直接或间接引用该 API 元素的情况下，程序无法使用该预览特性。

如果禁用了预览特性，当在程序元素的声明（无论是显式还是隐式声明）中使用必要的 API 元素（重写、调用或通过名称引用）时，将发生编译错误。

如果启用了预览特性，当在程序元素的声明（无论是显式还是隐式声明）中使用必要的 API 元素（重写、调用或通过名称引用）时，Java 编译器必须产生预览警告，除非：

- 该使用位于一个本身就是必要的 API 元素的声明中；或
- 该使用所在的声明与该必要 API 元素的声明都位于同一个最外层类中；或
- 该使用位于导入了该必要 API 元素的导入声明中。

Java SE 14 包含以下必要的 API 元素：

- 针对预览特性 Records：`Record` 类；以及在枚举 `java.lang.annotation.ElementType` 中的枚举常量 `RECORD_COMPONENT`。
- 针对预览特性 Text Blocks：在类 `String` 中的方法 `stripIndent` 和 `translateEscapes`。

## 1.6 反馈

欢迎读者将《Java® 语言规范》中的技术错误和歧义报告至 `jls-jvms-spec-comments@openjdk.java.net`。

有关 `javac`（Java 编程语言的参考编译器）行为的问题，特别是其对本规范的遵循情况，可以发送至 `compiler-dev@openjdk.java.net`。

## 1.7 参考文献

Apple Computer. Dylan Reference Manual. Apple Computer Inc., Cupertino, California. September 29, 1995.

Bobrow, Daniel G., Linda G. DeMichiel, Richard P. Gabriel, Sonya E. Keene, Gregor Kiczales, and David A. Moon. Common Lisp Object System Specification, X3J13 Document 80-002R, June 1988; appears as Chapter 28 of Steele, Guy. Lisp: The Language, 2nd ed. Digital Press, 1990, ISBN 1-55558-A41-6, 770-864.

Ellis, Margaret A., and Bjarne Stroustrup. The Annotated C++ Reference Manual. Addison-Wesley, Reading, Massachusetts, with corrections October 1992, ISBN 0-201-51459-1.

Goldberg, Adele and Robson,. Smalltalk-80: The Language. Addison-Wesley, Reading, Massachusetts, 1989, ISBN 0-201-13688-0.

Harbison, Samuel. Modula-3. Prentice Hall, Englewood Cliffs, New Jersey, 1992, ISBN 0-13-596396.

Hoare, C. A. R. Hints on Programming Language Design. Stanford University Computer Science Technical Report No. CS-73-403, December 1973. Reprinted in SIGACTST/SIGPLAN Symposium on Principles of Programming Languages. Association for Computing Machinery, New York, October 1973.

IEEE Standard for Binary Floating-Point Arithmetic. ANSI/IEEE Std. 754-1985. Available from Global Engineering Documents, 15 Invernwy Way East, Englewood Cliffs, Colorado 80112-5704 USA; 800-854-7179.

Kernighan, Brian W., and Dennis M. Ritchie. The C Programming Language, 2nd ed. Prentice Hall, Englewood Cliffs, New Jersey, 1988, ISBN 0-13-110362-8.

Madsen, Ole Lehmann, Birger Moller-Pedersen, and Kristen Nygaard. Object-Oriented Programming in the Beta Programming Language. Addison-Wesley, Reading, Massachusetts, 1993, ISBN 0-201-62430-3.

Mitchell, James G., William Maybury, and Robert Sweet. The Mesa Programming Language, Version 5.0. Xerox PARC, Palo Alto, California, CSL 79-3, April 1979.

Stroustrup, Bjarne. The C++ Programming Language, 2nd ed. Addison-Wesley, Reading, Massachusetts, 1991, reprinted with corrections January 1994, ISBN 0-201-53992-6.

Unicode Consortium, The Unicode Standard, Version 12.1.0. Mountain View, California, 2019. ISBN 978-1-93623-25-2.

# 第 2 章

## 语法

本章描述了本规范中使用的上下文无关文法，用于定义程序的词法和句法结构。

## 2.1 上下文无关文法

上下文无关文法由若干个*产生式*（productions）组成。每个产生式都有一个称为*非终端*（nonterminal）的抽象符号作为其*左侧*，以及一个或多个非终端符号和终结符号的序列作为其*右侧*。对于每个语法，终结符号源自指定的*字母表*（alphabet）。

从由一个特殊的非终端符号（称为*目标符号* goal symbol）组成的句子开始，给定的上下文无关文法规定了，即通过反复替换任何非终端符号可以得到的终结符号序列集合。

## 2.2 词法语法

Java 语言的*词法语法*见于 §3。该语法的终结符号是*标记*（tokens）。它定义了一组从目标符号开始的产生式，描述了如何将 Unicode 字符转换为标记。这些标记由 §3 定义。

## 2.3 句法语法

Java 语言的句法语法位于第 4、6-10 章和第 15 章。该语法的终结符号是标记。它定义了一组产生式，描述了标记序列如何构成语法正确的程序。

## 2.4 语法表示

终结符号在词法和句法的产生式中使用等宽字体显示，并在本规范直接引用此类终结符号时同样如此。它们在程序中按原样出现。

非终端符号用斜体显示。符号的定义由定义的非终端符号名称引入，后跟一个冒号。该非终端符号的一个或多个备选定义后续后续。

例如，句法产生式：

```
IfThenStatement:
if ( Expression ) Statement
```

表示非终端符号 `IfStatement` 代表标记 `if`、接着是左括号标记、接着是 `Expression`、接着是右括号标记、最后是 `Statement`。

产生式右侧的 `[x]` 语法表示 `x` 零或多次。

例如，句法产生式：

```
ArgumentList:
Argument [ , Argument]
```

表示 `ArgumentList` 由一个 `Argument` 以及零或多次逗号和 `Argument` 组成。结果是 `ArgumentList` 可以包含任何正数量的参数。

产生式右侧的 `[x]` 语法表示 `x` 零或一次。也就是说，`x` 是可选符号。包含可选符号的备选方案实际上定义了两个备选方案：一个是省略可选符号，另一个是包含它。

这意味着：

```
BreakStatement:
  break [Identifier];
```

是以下内容的简写：

```
BreakStatement:
  break;
  break Identifier;
```

另一个例子，这意味着：

```
BasicStatement:
  for ([ForInit]; [Expression] ; [ForUpdate]) Statement
```

是以下内容的简写：

```
BasicStatement:
  for (; [Expression] ; [ForUpdate]) Statement
  for (ForInit ; [Expression] ; [ForUpdate]) Statement
```

这反过来又是以下内容的简写：

```
BasicStatement:
  for (; ; [ForUpdate]) Statement
  for (; Expression ; [ForUpdate]) Statement
  for (ForInit ; ; [ForUpdate]) Statement
  for (ForInit ; Expression ; [ForUpdate]) Statement
```

BasicForStatement:

for ( ; ; ) Statement

for ( ; ForUpdate ) Statement

for ( ; Expression ; ) Statement

for ( ; Expression ; ForUpdate ) Statement

for ( Fornit ; ; ) Statement

for ( Fornit ; ForUpdate ) Statement

for ( Fornit ; Expression ; ) Statement

for ( Fornit ; Expression ; ForUpdate ) Statement

因此非终结 BasicForStatement 实际上有可选的右侧。

一个非常长的右侧可以通过清晰地缩进第二行来在第二行继续。

例如，语法规则包含此产生式：

```
NormalClassDeclaration:
[ClassModifier] class TypeIdentifier [TypeParameters]
[Superclass][SuperInterfaces] ClassBody
```

它为非终符 NormalClassDeclaration 定义了一个右侧。

产生式右侧的短语（其之一）表示后续行行或某几行中的每个符号都是一种可选的定义。

例如，词法规则包含此产生式：

```
ZeroToThree:
(one of)
0 1 2 3
```

这仅仅是以下内容的方便缩写：

```
ZeroToThree:
0
1
2
3
```

当产生式中的可选定义看起来像是一个标记时，它代表了构成该标记的字符序列。

因此，产生式：

```
BooleanLiteral:
(one of)
true false
```

是以下内容的简写：

```
BooleanLiteral:
true
false
```

产生式的右侧可以通过使用 "but not" 短语然后指示要排除的扩展来指定某些扩展是不允许的。

例如：

```
Identifier:
IdentifierChars but not a Keyword or BooleanLiteral or NullLiteral
```

最后，一些非终符通过正体的叙述性短语定义，在这种情况下列出所有可选定义是不现实的。

例如：

```
RawInputCharacter:
any Unicode character
```

# 第 3 章

## 词法结构

本章规定了 Java 编程语言的词法结构。

程序使用 Unicode (§3.1) 编写，但提供了词法翻译（§3.2），以便可以使用 Unicode 转义（§3.3）仅使用 ASCII 字符包含任何 Unicode 字符。定义了行终止符（§3.4）以支持现有主机系统的不同约定，同时保持行号的一致性。

词法翻译产生的 Unicode 字符被还原为输入元素序列（§3.5），这些包括空白（§3.6）、注释（§3.7）和标记。标记是语法规则中的标识符（§3.8）、关键字（§3.9）、字面量（§3.10）、分隔符（§3.11）和运算符（§3.12）。

## 3.1 Unicode

Java SE平台随 Unicode 标准的演进而跟进。特定发布版本使用的 Unicode 精确版本在 `Character` 类的文档中规定。

JDK 1.1 之前的 Java 编程语言版本使用 Unicode 1.1.5。向更高版本的 Unicode 标准升级发生在 JDK 1.1（到 Unicode 2.0）、JDK 1.1.7（到 Unicode 2.1）、Java SE 1.4（到 Unicode 3.0）、Java SE 5.0（到 Unicode 4.0）、Java SE 7（到 Unicode 6.0）、Java SE 8（到 Unicode 6.2）、Java SE 9（到 Unicode 8.0）、Java SE 11（到 Unicode 10.0）、Java SE 12（到 Unicode 11.0）以及 Java SE 13（到 Unicode 12.1）。



# Unicode 标准与 Java 编码

Unicode 标准最初被设计为固定宽 16 位字符编码。它已被更改以允许表示需要超过 16 位的字符。合法代码点的范围现在是 `U+0000` 到 `U+10FFFF`，使用 `U+FFFF` `U+n` 表示法。代码点大于 `U+FFFF` 的字符被称为补充字符。为了仅使用 16 位单位表示完整的字符范围，Unicode 标准定义了一种名为 UTF-16 的编码。在 UTF-16 编码中，补充字符被表示为一对 16 位代码单元，第一个来自高代理项范围（`U+D800` 到 `U+DBFF`），第二个来自低代理项范围（`U+DC00` 到 `U+DFFF`）。`U+0000` 到 `U+FFFF` 范围内的字符，其代码点值和 UTF-16 代码单元是相同的。

Java 编程语言使用 UTF-16 编码通过 16 位代码单元序列表示文本。

Java SE 平台的一些 API（主要在 `Character` 类中）使用 32 位整数将代码点作为独立实体表示。Java SE 平台提供了在 16 位和 32 位表示之间转换的方法。

本规范在表示相关时使用代码点和 UTF-16 代码单元术语，在表示与讨论无关时使用通用术语字符。

除了字符（§3.7）、标识符以及字符和字符串字面量的内容（§3.10.4、§3.10.5），程序中的所有输入元素（§3.5）仅由 ASCII 字符（或产生 ASCII 字符的 Unicode 转义 §3.3）组成。

## 源程序到输入元素序列的词法翻译

源程序到输入元素序列的词法翻译分两个方向进行：

1. 源程序到 Unicode 字符序列的翻译。
2. Unicode 字符到输入元素序列的翻译。

### Unicode 字符序列翻译规则

Unicode 字符序列通过逐个读取源程序获得。每个字符到 Unicode 等效值的翻译遵循以下规则：

- 如果字符是 ASCII 字符，其 Unicode 等效值为该字符。
- 如果字符是 Unicode 转义，其 Unicode 等效值为转义符指定的字符。
- 如果字符是其他字符，其 Unicode 等效值为该字符。

### 输入元素序列翻译规则

输入元素序列通过逐个读取 Unicode 字符获得。每个 Unicode 字符到输入元素的翻译遵循以下规则：

（此处根据提供的 OCR 文本省略了规则）

## Unicode 转义

Java 编程语言规定了一种将以 Unicode 编写的程序转换为 ASCII 的标准，该标准将程序转换为可以被基于 ASCII 的工具处理的形式。转换涉及将源文本中的任何 Unicode 转义通过添加额外的 `u` 转换为 ASCII —— 例如，`\uxxxx` 变为 `\uuxxxx`，同时将源文本中的非 ASCII 字符转换为包含单个 `u` 的 Unicode 转义。

这种转换后的版本 Java 编译器同样接受，并表示相同的程序。可以从这种 ASCII 格式恢复精确的 Unicode 源码，方法是将每个包含多个 `u` 的转义序列转换为更少 `u` 的 Unicode 序列，同时将每个单个 `u` 的转义序列转换为对应的单个 Unicode 字符。

> 当没有合适的格式可用时，Java 编译器应该使用 `\uxxxx` 记法作为输出格式来显示 Unicode 字符。

## 3.4 行终止符

Java 编译器接下来将通过识别行终止符，将 Unicode 输入字符序列分为若干行。

**LineTerminator:**

- ASCII LF 字符，也称为“newline”（换行）
- ASCII CR 字符，也称为“return”（返回）
- ASCII CR 字符后跟 ASCII LF 字符

**InputCharacter:**

- UnicodeInputCharacter 但不是 CR 或 LF

行由 ASCII 字符 CR、LF 或 CR LF 终止。紧挨在 LF 之前的两个字符 CR 和 LF 被计作一个行终止符，而不是两个。

行终止符规定了 `//` 形式注释（§3.3）的结束。

> 由行终止符定义的行可能会决定 Java 编译器产生的行号。

结果是一个行终止符和输入字符的序列，它们是标记（tokenization）过程中第三步的终止符号。

## 3.5 输入元素和标记

经过转义处理（§3.3）和输入行识别（§3.4）产生的输入字符和行终止符被归约为输入元素序列。

**Input:**
`[InputElement] [Sub]`

**InputElement:**

- WhiteSpace（空白）
- Comment（注释）
- Token（标记）

**Token:**

- Identifier（标识符）
- Keyword（关键字）
- Literal（字面量）
- Separator（分隔符）
- Operator（操作符）

**Sub:**

- ASCII Sub 字符，也称为“control-Z”

那些不是空白或注释的输入元素是标记。标记是语法（§2.3）的终止符号。

空白（§3.6）和注释（§3.7）可以用于分隔标记，如果标记相邻，可能会以另一种方式进行标记。例如，输入中的 ASCII 字符 `-` 和 `=` 只有在中间没有空白字符的情况下，才能形成操作符标记 `-=`（§3.12）。

作为对某些操作系统的特殊妥协，如果 ASCII Sub 字符（即 control-Z）是转义输入流中的最后一个字符，则会被忽略。

考虑结果输入流中的两个标记 `x` 和 `y`。如果 `x` 于 `y` 之前，则我们称 `x` 在 `y` 的左侧，`y` 在 `x` 的右侧。

例如，在这段简单的代码中：

```
class Empty {
}
```

我们说 `}` 标记在 `{` 标记的右侧，尽管在这一二维表示中，它出现在 `{` 标记的下方且左侧。这种关于使用“左”和“右”词的习惯让我们能够讨论，例如二元操作符的右侧操作数或赋值的左侧。

## 3.6 空白

空白被定义为 ASCII 空格字符、水平制表符字符、分页字符和行终止符字符（§3.4）。

**WhiteSpace:**

- ASCII SP 字符，也称为“space”（空格）
- ASCII HT 字符，也称为“horizontal tab”（水平制表符）
- ASCII FF 字符，也称为“form feed”（分页符）
- LineTerminator（行终止符）

## 3.7 注释

注释有两种：

- `/* text */`：传统注释：从 ASCII 字符 `/*` 到 ASCII 字符 `*/` 之间的所有文本都被忽略（如在 C 和 C++ 中）。
- `// text`：行尾注释：从 ASCII 字符 `//` 到行尾的所有文本都被忽略（如在 C++ 中）。

**Comment:**

- TraditionalComment（传统注释）
- EndOfLineComment（行尾注释）

**TraditionalComment:**
`/* CommentTail:`

**CommentTailStar:**
`* CommentTailStar`

**NotStarCommentTail**

**CommentTailStar:**
`/`
`* CommentTailStar`
`StarNotSlash CommentTail`

**NotStar:**
`InputCharacter` 但不是 `*`
`LineTerminator`

**NotStarNotSlash:**
`InputCharacter` 但不是 `*` 或 `/`
`LineTerminator`

**EndOfLineComment:**
`// [InputCharacter]`

这些产生式暗示了以下所有属性：

- 注释不会嵌套。
- `/*` 和 `*/` 在以 `//` 开头的注释中没有特殊含义。
- `//` 在以 `/*` 开头的注释中没有特殊含义。

作为结果，词法语法意味着注释不会出现在字符字面量（§3.10.4）或字符串字面量（§3.10.5）内部。

## 3.8 标识符

标识符是 Java 字母和 Java 数字的无限长度的序列，其中第一个字符必须是 Java 字母。

**Identifier:**
`IdentifierChars` 但不是 Keyword（关键字）、BooleanLiteral（布尔字面量）或 NullLiteral（空字面量）

**IdentifierChars:**
`JavaLetter [JavaLetterOrDigit]`

**JavaLetter:**
任何“Java 字母”Unicode 字符

**JavaLetterOrDigit:**
任何“Java 字母或数字”Unicode 字符

“Java 字母”是指方法 `Character.isJavaIdentifierStart(int)` 返回 `true` 的字符。

“Java 字母-数字”是指方法 `Character.isJavaIdentifierPart(int)` 返回 `true` 的字符。

“Java 字母”包括大写和小写 ASCII 字母 A-Z（`\u0041-\u005a`）和 a-z（`\u0061-\u007a`），由于历史原因，还包括 ASCII 美元符号（`$` 或 `\u0024`）和下划线（`_` 或 `\u005f`）。美元符号应仅用于机械生成的代码或为了访问遗留系统上的预存名称。下划线可以在由两个或多个下划线组成的标识符中使用。

“Java 数字”包括 ASCII 数字 0-9（`\u0030-\u0039`）。

字母和数字可以来自整个 Unicode 集合，该集合支持大多数文字，包括中文、日语和韩语。

标识符的拼写（Unicode 字符）不能与关键字（§3.9）、布尔字面量（§3.10）、空字面量（§3.17）相同，否则会导致编译错误。

如果两个标识符在忽略忽略字符或数字后具有相同的 Unicode 字符，则它们是相同的。忽略字符是指方法 `Character.isIdentifierIgnorable(int)` 返回 `true` 的字符。例如，由单个字母 LATIN CAPITAL LETTER A (A, `\u0041`)、LATIN SMALL LETTER A (a, `\u0061`)、GREEK CAPITAL LETTER ALPHA (Α, `\u0391`)、CYRILLIC SMALL LETTER A (а, `\u0430`) 和 MATHEMATICAL BOLD ITALIC SMALL A (𝐴, `\uD83582`) 组成的标记都是不同的。

Unicode 字符与其规范等效字符不同。LATIN CAPITAL LETTER A ACUTE (Á, `\u00C1`) 与紧跟一个 NON-SPACING ACUTE (', `\u0301`) 的 LATIN CAPITAL LETTER A (A, `\u0041`) 在标识符中是不同的。见 Unicode 标准第 3.11 节“规范化”。

**标识符的示例：**

- `String`
- `i3`
- `αρετη`
- `MAX_VALUE`
- `isLetterDigit`

## 3.9 关键字

关键字 `const` 和 `goto` 是保留的，尽管它们目前尚未被使用。这可能允许 Java 编译器在 C++ 关键字错误地出现在程序中时，能够产生更好的错误信息。关键字 `_`（下划线）在许多声明中被保留以供未来使用。

某些字符序列有时会被错误地认为是关键字：

- `true` 和 `false` 不是关键字，而是布尔字面量（§3.10.3）。
- `null` 不是关键字，而是空值字面量（§3.10.7）。
- `var` 和 `yield` 不是关键字，而是受限的标识符（§3.8）。`var` 作为局部变量声明的类型具有特殊意义（§14.4, §14.4.1, §14.4.2, §14.20.3），并且作为 lambda 形式参数的类型（§15.27.1）。`yield` 在 `yield` 语句中具有特殊意义（§14.21）。所有对名为 `yield` 的方法的调用必须经过限定，以便与 `yield` 语句区分开。

另外十个字符序列是**受限关键字**：`open`、`module`、`requires`、`transitive`、`exports`、`opens`、`to`、`uses`、`provides` 和 `with`。这些字符序列仅在作为 `ModuleDeclaration`、`ModuleDirective` 和 `RequiresModifier` 产生式的终端时才被标记为关键字。在其他所有地方，为了兼容引入受限关键字之前编写的程序，它们被标记为标识符。有一个例外：在 `ModuleDirective` 产生式中，字符序列 `requires` 紧右侧的字符序列 `transitive` 如果其后面没有跟着分隔符，则被标记为关键字；否则，被标记为标识符。

## 3.10 字面量

*字面量*是原始类型（§4.2）、`String` 类型（§4.3.3）或空类型（§4.1）值的源码表示。

**字面量：**

- 整数字面量 (IntegerLiteral)
- 浮点数字面量 (FloatingPointLiteral)
- 布尔字面量 (BooleanLiteral)
- 字符字面量 (CharacterLiteral)
- 字符串字面量 (StringLiteral)
- 空值字面量 (NullLiteral)

## 3.10.1 整数字面量

整数字面量可以用十进制（基 10）、十六进制（基 16）、八进制（基 8）或二进制（基 2）表示。

```
IntegerLiteral:
    DecimalIntegerLiteral
    HexIntegerLiteral
    OctalIntegerLiteral
    BinaryIntegerLiteral
```

```
DecimalIntegerLiteral:
    DecimalNumeral [IntegerTypeSuffix]
```

```
HexIntegerLiteral:
    HexNumeral [IntegerTypeSuffix]
```

```
OctalIntegerLiteral:
    OctalNumeral [IntegerTypeSuffix]
```

```
BinaryIntegerLiteral:
    BinaryNumeral [IntegerTypeSuffix]
```

```
IntegerTypeSuffix:
    (其中之一)
    L
```

如果整数字面量以 ASCII 字母 `L` 或 `l` (ell) 为后缀，则它的类型为 `long`；否则它是 `int` 类型（§4.2.1）。

> 优选使用后缀 `L`，因为 `l` (ell) 很难与数字 `1` (one) 区分。

下划线允许作为表示整数的数字之间的分隔符。

在十六进制或二进制字面量中，整数仅由 `0x` 或 `0b` 字符之后、任何类型后缀之前的数字表示。因此，下划线不能紧跟在 `0x` 或 `0b` 之后，也不能出现在数字最后一位之后。

在十进制或八进制字面量中，整数由字面量中任何类型后缀之前的所有数字表示。因此，下划线不能出现在数字的第一位之前，或最后一位之后。下划线可以出现在八进制数字中 `0` 之后（因为 `0` 是表示整数部分的一个数字），也可以出现在非零十进制字面量中初始非零数字之后。



# 3.10 字面量

## 3.10.1 整数字面量

十进制数字可以是单个 ASCII 数字 `0`（代表整数 0），或者由一个 1 到 9 的 ASCII 数字组成，可选地跟随一个或多个间隔有下划线的 0 到 9 的 ASCII 数字，表示一个正整数。

```
DecimalNumeral:
0
NonZeroDigit [Digits]
NonZeroDigit Underscores Digits
```

```
NonZeroDigit:
(其中之一)
1 2 3 4 5 6 7 8 9
```

```
Digits:
Digit
Digit [DigitsAndUnderscores] Digit
```

```
Digit:
0
NonZeroDigit
```

```
DigitsAndUnderscores:
DigitOrUnderscore {DigitOrUnderscore}
```

```
DigitOrUnderscore:
Digit
-
```

```
Underscores:
- {_}
```

十六进制数字由领先的 ASCII 字符 `0x` 或 `0X` 后跟一个或多个间隔有下划线的 ASCII 数字组成，可以表示正整数、零或负整数。

值为 10 到 15 的十六进制数字分别用 ASCII 字母 a 到 f 或 A 到 F 表示；每个用作十六进制数字的字母可以是大写或小写。

```
HexNumeral:
0x HexDigits
0X HexDigits
```

```
HexDigits:
HexDigit
HexDigit[HexDigitsAndUnderscores] HexDigit
```

```
HexDigit:
(其中之一)
0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F
```

```
HexDigitsAndUnderscore:
HexDigitOrUnderscore {HexDigitOrUnderscore}
```

```
HexDigitOrUnderscore:
HexDigit
```

`HexDigit` 产生式源自 §3.3。八进制数字由 ASCII 数字 `0` 后跟一个或多个间隔有下划线的 ASCII 数字组成，可以表示正整数、零或负整数。

```
OctalNumeral:
  0 OctalDigits
  0 Underscores OctalDigits
```

```
OctalDigits:
  OctalDigit
  OctalDigit [OctalDigitsAndUnderscores]
```

```
OctalDigit:
(其中之一)
0 1 2 3 4 5 6 7
```

```
OctalDigitsAndUnderscore:
  OctalDigitOrUnderscore {OctalDigitOrUnderscore}
```

```
OctalDigitOrUnderscore:
  OctalDigit
```

注意八进制数字始终至少两个数字，单独的 `0` 始终被视为十进制数字——这在实践中并不重要，所有的 `0` 都表示相同的值。二进制字面量由领先的 ASCII 字符 `0b` 或 `0B` 后跟一个或多个间隔有下划线的 ASCII 数字 `0` 或 `1` ，可以表示正整数、零或负整数。

```
BinaryNumeral:
  0b BinaryDigits
  0B BinaryDigits
```

```
BinaryDigits:
  BinaryDigit
  BinaryDigit [BinaryDigitsAndUnderscores]
```

```
BinaryDigit:
(其中之一)
  0 1
```

```
BinaryDigitsAndUnderscore:
  BinaryDigitOrUnderscore {BinaryDigitOrUnderscore}
```

```
BinaryDigitOrUnderscore:
  BinaryDigit
```

`int` 类型最大的十进制字面量是 `2147483647` ($2^{31}-1$)。从 0 到 `2147483647` 的所有十进制字面量都可以出现在 `int` 字面量的地方。十进制字面量 `2147483648` 只能作为一元操作符的操作数 (§15.15.4)。如果十进制字面量 `2147483648` 出现在一元操作符的操作数以外的地方，或者 `int` 类型的字面量大于 `2147483648` ($2^{31}$)，则会导致编译错误。`int` 类型最大的正十六进制、八进制和二进制字面量分别表示十进制值 `2147483647` ($2^{31}-1$)：

- `0xffff_ffff`
- `0o7777_7777`
- `0b0111_1111_1111_1111_1111_1111`

`int` 类型最小的十六进制、八进制和二进制字面量分别表示十进制值 `-2147483648` ($-2^{31}$)：

- `0x8000_0000_0000_0000`
- `0o200000_0000`
- `0b1000_0000_0000_0000_0000_0000_0000`

以下十六进制、八进制和二进制字面量表示十进制值 `-1`：

- `0xffff_ffff`
- `0o3777_7777`
- `0b0111_1111_1111_1111`

如果十六进制、八进制或二进制字面量不符合 32 位，则会导致编译错误。

`long` 类型最大的十进制字面量是 `9223372036854775807` ($2^{63}-1$)。从 `0L` 到 `9223372036854775807L` 的所有十进制字面量都可以出现在 `long` 字面量的地方。十进制字面量 `9223372036854775808L` 只能作为一元操作符的操作数 (§15.15.4)。如果十进制字面量 `9223372036854775808L` 出现在一元操作符的操作数以外的地方，或者 `long` 类型的字面量大于 `9223372036854775808L` ($2^{63}$)，则会导致编译错误。

`long` 类型最大的正十六进制、八进制和二进制字面量分别表示十进制值 `9223372036854775807L` ($2^{63}-1$)：

- `0xffff_ffff_ffff`
- `0x7777_7777_7777_7777_7777L`
- `0b0111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111`

`long` 类型最小的十六进制、八进制和二进制字面量分别表示十进制值 `-9223372036854775808L` ($-2^{63}$)：

- `0x8000_0000_0000_0000L`
- `0x0100_0000_0000_0000L`
- `0b1000_0000_0000_0000_0000_0000_0000_0000`

以下十六进制、八进制和二进制字面量表示十进制值 `-1L`：

- `0xffff_ffff_ffff`
- `0x1777_7777_7777_7777_7777L`
- `0b0111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111`

如果十六进制、八进制或二进制字面量不符合 64 位，则会导致编译错误。

## 3.10.2 浮点数字面量

浮点数字面量具有以下部分：整数部分、十进制或十六进制部分（由 ASCII 点字符表示）、分数部分、指数和类型后缀。

浮点数字面量可以用十进制（基 10）或十六进制（基 16）表示。

对于十进制浮点数字面量，至少需要一个数字（整数部分或小数部分），并且需要一个小数点、一个指数或浮点类型后缀。所有其他部分均为可选的。指数如果存在，则由 ASCII 字母 `e` 或 `E` 表示，后跟一个可选带符号的整数。

对于十六进制浮点数字面量，至少需要一个数字（整数部分或小数部分），指数是强制性的，而浮点类型后缀是可选的。指数由 ASCII 字母 `p` 或 `P` 表示，后跟一个可选带符号的整数。

下划线允许作为表示整数部分的数字之间、表示小数部分的数字之间以及表示指数部分的数字之间的分隔符。

```
FloatingPointLiteral:
DecimalFloatingPointLiteral
HexadecimalFloatingPointLiteral
```

```
DecimalFloatingPointLiteral:
Digits . [Digits] [ExponentPart][FloatTypeSuffix]
. Digits [ExponentPart][FloatTypeSuffix]
Digits ExponentPart [FloatTypeSuffix]
Digits [ExponentPart] FloatType
```

```
ExponentPart:
ExponentIndicator SignedInteger
```

```
ExponentIndicator:
(one of)
e E
```

```
SignedInteger:
[Sign] Digits
```

```
Sign:
(one of)
+-
```

```
FloatTypeSuffix:
(one of)
f F d D
```

```
HexadecimalFloatingPointLiteral:
HexSignificand BinaryExponent [FloatTypeSuffix]
```

```
HexSignificand:
HexNumeral [.]
0x[HexDigits] .HexDigits
0x[HexDigits] .HexDigits
```

```
BinaryExponent:
BinaryExponentIndicator SignedInteger
```

```
BinaryExponentIndicator:
(one of)
p P
```

如果浮点数字面量以 ASCII 字母 `F` 或 `f` 结尾，则其类型为 `float`；否则其类型为 `double`，并且可以可选以 ASCII 字母 `D` 或 `d` 结尾 (§4.2.3)。

`float` 和 `double` 类型的元素是那些可以使用 IEEE 754 32 位单精度和 64 位双精度二进制浮点格式表示的值。

> 关于将浮点数正确输入转换转换为 Unicode 字符串表示，再转换为内部 IEEE 754 二进制浮点表示的详细说明，参见包 `java.lang` 中 `Float` 类和 `Double` 类的 `valueOf` 方法。

`float` 类型最大的有限字面量是 `3.4028235e38`。

`double` 类型最小的非零有限字面量是 `1.40e-45`。

`double` 类型最大的正有限字面量是 `1.7976931234862315e308`。

`double` 类型最小的正非零字面量是 `4.9e-324`。

如果一个非零浮点数字面量太大，则会导致编译错误，因此在舍入转换为其内部表示时，它会变成 IEEE 754 的无穷大。

程序通过使用常量表达式 `1f/0f` 或 `-1d/0d`，或者使用 `Float` 和 `Double` 类的定义常量 `POSITIVE_INFINITY` 和 `NEGATIVE_INFINITY` 来表示无穷大，而不产生编译错误。

如果一个非零浮点数字面量太小，以至于在舍入转换为其内部表示时会变为零，则会导致编译错误。

如果一个非零浮点数字面量的值很小，在舍入转换为其内部表示时变成一个非零的规数，则不会发生编译错误。

表示“非数字”（NaN）值的定义常量在 `Float` 和 `Double` 类中定义为 `Float.NaN` 和 `Double.NaN`。

`float` 字面量的示例：

```
1elf    2.f    .3f    0f    3.14f    6.022137e+23f
```

`double` 字面量的示例：

```
1e1    .3    0.0    3.14    1e-9d    1e37
```

## 3.10.3 布尔字面量

布尔字面量有两个值，由 ASCII 字母组成的布尔字面量 `true` 和 `false` 表示。

```
BooleanLiteral:
(one of)
true false
```

布尔字面量的类型始终为 `boolean` (§4.2.5)。

## 3.10.4 字符字面量

字符字面量表示为一个字符或转义序列 (§3.10.6)，并包含在 ASCII 单引号内。（单引号字符和撇符号字符是 `\u0027`。）

```
CharacterLiteral:
' SingleCharacter '
' EscapeSequence '
```

```
SingleCharacter:
InputCharacter but not ' \
```

有关 `EscapeSequence` 的定义请参见 §3.10.6。

字符字面量只能表示 UTF-16 代码单元 (§3.1)，即它们被限制为从 `\u0000` 到 `\ffff` 的值。补充字符必须在 `char` 序列中作为代理对表示，或者作为整数表示，这取决于它们所使用的 API。

字符字面量的类型始终为 `char` (§4.2.1)。

如果 `SingleCharacter` 转义序列后的字符不是一个 `.`，则会导致编译错误。

如果在起始单引号 `'` 之后、结束单引号 `'` 之前出现行终止符 (§3.4)，则会导致编译错误。

如 §3.4 所示，`CR` 和 `LF` 永远不是 `InputCharacter`；每个字符都被识别为行终止符。

以下是字符字面量的示例：

- `'a'`
- `'s'`
- `'\t'`
- `'\\'`
- `'\u003a'`
- `'\uFFFF'`
- `'\u177'`

由于 Unicode 转义处理得非常早，因此对于包含换行符（LF）的字符字面量，使用 `"\u000a"` 是错误的；Unicode 转义 `\u000a` 在翻译步骤 1 (§3.4) 中转换为实际字面量，并在步骤 2 变成行终止符，因此该字面量在步骤 3 是无效的。相反，应该使用 `"\n"` (§3.10.6)。同样，对于包含回车（CR）的字符字面量，使用 `"\u000d"` 是错误的。相反，应使用 `"\r"`。最后，对于包含双引号（`"`）的字符字面量，无法使用 `"\u0022"`。在 C 和 C++ 中，字符字面量可以多个字符，但这种字符字面量的值取决于实现。在 Java 语言中，字符字面量始终表示一个字符。

## 3.10.5 字符串字面量

字符串字面量由双引号包含零或多个字符。字符可以使用转义序列 (§3.10.6) 表示——对于范围 U0000 到 UFFFF 的字符使用一个转义序列，对于范围 U1000 到 UFFFF 的字符使用两个转义序列。

```
StringLiteral:
" {StringCharacter}"
```

```
StringCharacter:
InputCharacter but not "
EscapeSequence
```

有关 `EscapeSequence` 的定义请参见 §3.10.6。

字符串字面量的类型始终为 `String` (§4.3.3)。

如果在起始 `"` 之后、匹配 `"` 之前出现行终止符，则会导致编译错误。

如 §3.4 所示，`CR` 和 `LF` 永远不是 `InputCharacter`；每个字符都被识别为行终止符。

字符串字面量总是可以分成更短的部分并使用连接运算符 `+` (§15.18.1) 写为可能带括号的表达式。

以下是字符串字面量的示例：

```
"" // 空字符串
"\"" //  " 的字符串
"This is a string" // 包含16 个字符的字符串
"This is a "" // 实际上是一个字符串常量表达式
"two-line string"
```

由于 Unicode 转义处理非常早，对于包含单行（LF）的字符串字面量，使用 `"\u000a"` 是错误的；Unicode 转义 `\u000a` 在翻译步骤 1 (§3.4) 中转换为实际字面量，并在步骤 2 变成行终止符，因此该字面量在步骤 3 是无效的。相反，应该使用 `"\n"` (§3.10.6)。同样，对于包含回车（CR）的字符串字面量，使用 `"\u000d"` 是错误的。相反，应使用 `"\r"`。最后，对于包含双引号（`"`）的字符串字面量，无法使用 `"\u0022"`。

字符串字面量是 `String` 类实例的引用 (§4.3.1, §4.3.3)。

此外，字符串字面量始终引用同一个 `String` 类实例。这是因为字符串字面量——或者更泛地说，常量表达式字符串 (§15.29)——经过了“池化”以共享唯一实例，使用了 `String.intern()` 方法 (§12.5)。

### 示例 3.10-5-1. 字符串字面量

由编译单元 (§7.3) 组成的程序：

```java
package testPackage;
class Test {
    public static void main(String[] args) {
        String hello = "Hello", lo = "lo";
        System.out.println(hello == "Hello");
        System.out.println(Other.hello == hello);
        System.out.println(other.Other.hello == hello);
        System.out.println(hello == ("Hello" + lo));
        System.out.println(hello == ("Hello" + lo));
        System.out.println(hello == ("Hello" + lo).intern());
    }
}
class Other { public static String hello = "Hello"; }
```

以及编译单元：

```java
package other;
public class Other { public static String hello = "Hello"; }
```

产生输出：

```
true
true
true
true
false
true
```

这说明了六点：

- 同一个类和包包中的字符串字面量表示对同一个 `String` 对象的引用 (§4.3.1)。
- 同一个包中不同类中的字符串字面量表示对同一个 `String` 对象的引用。
- 不同包中不同类中的字符串字面量同样表示对同一个 `String` 对象的引用。
- 由常量表达式 (§15.29) 拼接的字符串在编译时计算，然后被视为字面量进行处理。



- 在运行时通过拼接计算的字符串是新创建的，因此是不同的。

- 对计算出的字符串进行显式内化（interning）的结果，与任何内容相同的预存字符串字面量是同一个 `String` 对象。

## 3.10.6 字符和字符串字面量的转义序列

字符和字符串转义序列允许在不使用 Unicode 转义符的情况下表示某些非图形字符，还可以表示单引号、双引号和反斜杠字符，分别用于字符字面量 (§3.10.4) 和字符串字面量 (§3.10.5)。

转义序列 (`EscapeSequence`):

- `\b` (退格 BS, Unicode `\u0008`)
- `\t` (水平制表符 HT, Unicode `\u0009`)
- `\n` (换行 LF, Unicode `\u000a`)
- `\f` (换页 FF, Unicode `\u000c`)
- `\r` (回车 CR, Unicode `\u000d`)
- `\"` (双引号 ", Unicode `\u0022`)
- `\'` (单引号 ', Unicode `\u0027`)
- `\\` (反斜杠, Unicode `\u005c`)
- `\OctalEscape` (八进制值, Unicode `\u0000` 到 `\u00ff`)

八进制转义序列 (`OctalEscape`):

- `\OctalDigit`
- `\OctalDigit OctalDigit`
- `\ZeroToThree OctalDigit OctalDigit`

八进制数字 (`OctalDigit`):

(以下之一)
0 1 2 3 4 5 6 7

零到三 (`ZeroToThree`):

(以下之一)
0 1 2 3

上面的 `OctalDigit` 产生式源自 §3.10.1。

如果转义序列中反斜杠后面的字符不是 ASCII `b`, `t`, `n`, `f`, `r`, `'`, `"`, `,`, `0`, `1`, `2`, `3`, `4`, `5`, `6`, 或 `7`，则为编译错误。Unicode 转义符 `\u` 在之前被处理 (§3.3)。

提供八进制转义是为了兼容 C 语言，但它们只能表示 Unicode 值 `\u0000` 到 `\u00FF`，因此通常优选八进制转义。

## 3.10.7 null 字面量

`null` 类型（`null type`）有一个值，即 `null` 引用，由 `null` 字面量 `null` 表示，它由 ASCII 字符组成。

```
NullLiteral:
null
```

`null` 字面量始终是 `null` 类型 (§4.1)。

## 3.11 分隔符

由 ASCII 字符组成的 12 个标记是分隔符（标点符号）。

```
Separator (分隔符):
(以下之一)
( ) { } [ ] ; , . ... @ ::
```

## 3.12 运算符

由 ASCII 字符组成的 38 个标记是运算符。

```
Operator (运算符):
(以下之一)
= < ! ~ ? : ->
== >= != && || ++
+ - * / & ^ << >> >>>
+= -= * = /= &= |= ^ = = << <= >= >>>
```

# 第 4 章

### 类型、值和变量

Java 编程语言是一门静态类型语言，这意味着每个变量和每个表达式都有一个在编译时已知的类型。

Java 编程语言也是一门强类型语言，因为类型限制了变量 (§4.12) 可以持有的值或表达式可以产生的值，限制了支持这些值的操作，并决定了操作的含义。强静态类型有助于在编译时检测错误。

Java 编程语言的类型分为两类：基本类型和引用类型。基本类型 (§4.2) 包括布尔和数值类型。数值类型包括整数类型 `byte`, `short`, `int`, `long` 和 `char`，以及浮点类型 `float` 和 `double`。引用类型 (§4.3) 包括类类型、接口类型和数组。还有一种特殊的 `null` 类型。对象 (§4.3.1) 是类类型的动态创建的实例或动态创建的数组。引用类型的值是对对象的引用。所有对象（包括数组）都支持类 `Object` 类 (§4.2) 的方法。字符串字面量由 `String` 对象表示 (§4.3)。

## 4.1 类型和变量种类

Java 编程语言中有两种类型：基本类型 (§4.2) 和引用类型 (§4.3)。相应地，有两种数据值可以存储在变量中、作为参数传递、由方法返回并对其进行操作：基本值 (§4.2) 和引用值 (§4.3)。

类型 (`Type`):

- `PrimitiveType` (基本类型)
- `ReferenceType` (引用类型)

还有一种特殊的 `null` 类型，即表达式的类型 (§3.10.7, §15.8)，它没有名称。因为 `null` 类型没有名称，所以无法声明 `null` 类型的变量或强制转换为 `null` 类型。`null` 引用是 `null` 类型表达式唯一可能的值。`null` 引用始终可以被赋值或强制转换为任何引用类型 (§5.2, §5.3, §5.5)。在实践中，程序员可以忽略 `null` 类型并假 `null` 仅仅是一个可以作为任何引用类型的特殊字面量。

## 4.2 基本类型和值

基本类型由 Java 语言定义并由其关键字命名 (§3.9)：

`PrimitiveType` (基本类型):

- `NumericType` (数值类型)
- `boolean` (布尔)

`NumericType` (数值类型):

- `IntegralType` (整数类型)
- `FloatingPointType` (浮点类型)

`IntegralType` (整数类型):

(以下之一)
`byte` `short` `int` `char`

`FloatingPointType` (浮点类型):

(以下之一)
`float` `double`

基本类型包括数值类型和布尔类型。数值类型包括整数类型和浮点类型。整数类型包括 `byte`, `short`, `int`, `long` 和 `char`，它们是 8 位、16 位、32 位和 64 位整数。浮点类型包括 `float` 和 `double`，它们是 32 位和 64 位浮点数。引用类型包括类类型、接口类型和数组。引用类型的值是对对象的引用。所有对象（包括数组）都支持类 `Object` 类 (§4.2) 的方法。字符串字面量由 `String` 对象表示 (§4.3)。

#### 4.2.1 整数类型和值

整数类型的值。整数类型的取值范围如下：

- `byte` 从 -128 到 127
- `short` 从 -32768 到 32767
- `int` 从 -2147483648 到 2147483647
- `long` 从 -9223372036854775808 到 9223372036854775807
- `char` 从 0 到 65535

#### 4.2.2 整数运算

整数运算符。整数运算符的结果类型为：

- 比较运算符 `<`, `<=`, `>=`：布尔类型
- 相等运算符 `==` 和 `!=`：布尔类型
- `int` 或 `long` 类型：
  - 乘法运算符 `*`, `/`, `%`
  - 加法运算符 `+` 和 `-`
  - 赋值运算符 `+=`, `-=`
  - 递增运算符 `++`（前置和后缀）
  - 递减运算符 `--`（前置和后缀）
- 有符号和无符号移位运算符 `<<`, `>>`, `>>>`
- 按位取反运算符 `~`
- 整数按位运算符 `&`, `^`, `|`
- 条件运算符 `? :`
- 强制转换运算符 (§15.16)，可以将整数值转换为任何指定的类型
- 字符串拼接运算符 `+` (§15.18)，当给定 `String` 操作数和一个整数操作数时，会将整数转换为 `String`（`byte`, `short`, `int` 或 `long` 的十进制形式，或 `char` 的字符形式），然后产生一个这两个字符串拼接的新创建字符串。



# 类型、值与变量

## 4.2 基本类型与值

基本类型包括数值类型和布尔类型。数值类型包括整数类型和浮点类型。整数类型是 `byte`、`short`、`int`、`long` 和 `char`。浮点类型是 `float` 和 `double`。引用类型包括类类型、接口类型和数组。引用类型的值是对对象的引用。所有对象（包括数组）都支持类 `Object` 的方法（§4.2）。字符串字面量由 `String` 对象表示（§4.3）。

### 4.2.1 整数类型和值

整数类型的取值范围如下：

- `byte`：从 -128 到 127
- `short`：从 -32768 到 32767
- `int`：从 -2147483648 到 2147483647
- `long`：从 -9223372036854775808 到 9223372036854775807
- `char`：从 0 到 65535

### 4.2.2 整数运算

整数运算符的结果类型为：

- 比较运算符 `<`、`<=`、`>=`：`boolean` 类型
- 相等运算符 `==` 和 `!=`：`boolean` 类型
- `int` 或 `long` 类型：
  - 乘法运算符 `*`、`/`、`%`
  - 加法运算符 `+` 和 `-`
  - 赋值运算符 `+=`、`-=`
  - 递增运算符 `++`（前置和后缀）
  - 递减运算符 `--`（前置和后缀）
- 有符号和无符号移位运算符 `<<`、`>>`、`>>>`
- 按位取反运算符 `~`
- 整数按位运算符 `&`、`^`、`|`
- 条件运算符 `? :`
- 强制转换运算符（§15.16），可以将整数值转换为任何指定的类型
- 字符串拼接运算符 `+`（§15.18），当给定 `String` 操作数和一个整数操作数时，会将整数转换为 `String`（`byte`、`short`、`int` 或 `long` 的十进制形式，或 `char` 的字符形式），然后产生一个这两个字符串拼接的新创建字符串。

```java
long l = i;
System.out.println(1 * l);
System.out.println(20296 / (1 - i));
```

该程序产生以下输出：

```
-727379968
1000000000
```

然后在执行除以 `l - i` 时遇到 `ArithmeticException` 算术异常，因为 `i` 为零。第一次乘法在 32 位精度下执行，而第二次乘法是长整型乘法。值 `-727379968` 是数学结果 `1000000000` 的 32 位对应的十进制值，该值对于 `int` 来说太大了。

### 4.2.3 浮点类型、格式与值

浮点类型有 `float` 和 `double`，它们在概念上与《二进制浮点数标准》（IEEE Standard for Binary Floating-Point Arithmetic, ANSI/IEEE Standard 754-1985 (IEEE, New York)）规定的单精度 32 位和双精度 64 位格式值及操作相关。

IEEE 754 标准不仅包含由符号和数值组成的正负数，还包含正零和负零、正无穷和负无穷，以及特殊的非数字（Not-A-Number，以下简称 NaN）。NaN 值用于表示某些无效操作的结果，例如零除以零。`float` 和 `double` 类型的 NaN 常量被预定义为 `Float.NaN` 和 `Double.NaN`。

Java 编程语言的每个实现都要求支持两个标准的浮点值集，称为 `float` 值集和 `double` 值集。此外，Java 编程语言的实现可能支持两个扩展指数值集中的一个或两个，称为扩展指数值集。在某些情况下，这些扩展指数值集可以用来代替标准值集来表示 `float` 或 `double` 类型表达式的值（§5.1.13, §15.4）。

任何浮点值的任何有限非零值都可以表示为形式 $s \cdot m \cdot 2^{(e-N+1)}$，其中 $s$ 为 $+1$ 或 $-1$，$m$ 是小于 $2^N$ 的正整数，$e$ 是介于 $E_{min} = -(2^{K-1}-2)$ 和 $E_{max} = 2^{K-1}-1$（包含）之间的整数，其中 $N$ 和 $K$ 是取决于值集的参数。某些值可以用多种方式以此形式表示；例如，假设集合中的一个值 $v$ 可以使用某些 $s, m, e$ 值以此形式表示，如果恰好 $m$ 是偶数且 $e < 2^K$，则可以将 $m$ 减半并使 $e$ 加 1，从而为同一值 $v$ 产生第二种表示。如果 $m \geq 2^{N-1}$，则这种形式的表示被称为*规格化*（normalized）；否则，如果集合中的一个值无法以 $m \geq 2^{N-1}$ 的方式表示，则该值被称为*非归一化*（denormalized）值，因为它没有归一化的表示。

强制和可选浮点值集对参数 $N$ 和 $K$（以及派生参数 $E_{min}$ 和 $E_{max}$）的约束汇总在表 4.2.3-A 中。

#### 表 4.2.3-A. 浮点值集

| 参数 | float | float 扩展指数 | double | double 扩展指数 |
| :--- | :--- | :--- | :--- | :--- |
| N | 24 | 24 | 53 | 53 |
| K | 8 | $\geq 11$ | 11 | $\geq 15$ |
| $E_{max}$ | +127 | $\geq 1023$ | +1023 | +16383 |
| $E_{min}$ | -126 | $\leq -1022$ | -1022 | $\leq -16382$ |

### 4.2.4 浮点运算

Java 编程语言提供了许多作用于浮点值的运算符：

- 比较运算符，结果为 `boolean` 类型：
  - 数值比较运算符 `<`、`<=`、`>`、`>=`（§15.20）
  - 数值相等运算符 `==` 和 `!=`（§15.21.1）
- 数值运算符，作用于 `float` 和 `double` 类型：
  - 一元加减运算符 `+` 和 `-`（§15.15.3, §15.15.4）
  - 乘法运算符 `*`、`/`、`%`（§15.17）
  - 加法运算符 `+` 和 `-`（§15.18.2）
  - 递增运算符 `++`，包括前置（§15.15.1）和后置（§15.14.2）
  - 递减运算符 `--`，包括前置（§15.15.2）和后置（§15.14.3）
- 条件运算符 `? :`（§15.25）
- 强制类型运算符（§15.16），可以将浮点值转换为任何数值类型的值
- 字符串拼接运算符 `+`（§15.18.1），当给一个字符串操作数和一个浮点操作数时，它会将浮点操作数转换为十进制形式的字符串（不丢失信息），然后拼接创建一个新的字符串。

其他构造函数、方法和常量定义在 `Float`、`Double` 和 `Math` 类中。

如果二元运算符的操作数之一是浮点类型，则该运算是浮点运算，即使另一个是整型。

如果数值运算符的操作数之一是 `double`，则运算将使用 64 位浮点算术执行，数值运算符的结果是 `double` 类型的值。如果另一个操作数不是 `double`，则首先通过数值提升位宽（§5.1.5）提升为 `double` 类型（§5.6）。

否则，操作使用 32 位浮点数算术执行，数值操作符的结果为 `float` 类型的值。（如果另一个操作数不是 `float`，则通过数值类型提升进一步扩展为 `float`。）

浮点类型的任何值都可以转换为任何数值类型，或从任何数值类型转换过来。浮点类型与 `boolean` 类型之间不存在转换。

请参阅 §4.2.5 以了解将浮点表达式转换为布尔值的惯用方法。

浮点数的操作符的行为遵循 IEEE 754 规范（除余数运算符 §15.17.3 除外）。特别是，Java 编程语言要求支持 IEEE 754 非规格化浮点数和渐进式下溢，这使得更容易证明特定数值算法的理想属性。如果计算结果是归一化的，则浮点操作不会“强制置零”（flush to zero）。

Java 编程语言要求浮点算术的行为就如同每个浮点操作都将其结果舍入到精度。不精确的结果必须舍入到距离无限精确值最近的可表示值；如果两个最近的可表示值同样近，则选择最低位为 0 的那一个。这是 IEEE 754 标准的默认舍入模式，称为“舍入最近”（round to near）。

Java 编程语言在将浮点值转换为整数时（§5.1.3）使用向零舍入（round toward zero），在这种情况下相当于数字被截断，丢弃尾数位。向零舍入选择格式值中最接近无限精确结果且绝对值不超过该结果的值。

溢出的浮点操作产生符号无穷大。

发生下溢的浮点操作产生非规格化值或符号零。

没有数学上确定结果的浮点操作产生 NaN。所有以 NaN 为操作数的数值操作都会产生 NaN 结果。

浮点操作符可能由于以下原因抛出异常（§11）：

- 当需要对空引用进行拆箱转换（§5.1.8）时，任何浮点操作符都可能抛出 `NullPointerException`。
- 自增和自减运算符 `++`（§15.14.2, §15.15.1）和 `--`（§15.14.3, §15.15.2）如果需要装箱转换（§5.1.7）且没有足够的内存来执行转换，则可能会抛出 `OutOfMemoryError`。

#### 示例 4.2.4-1. 浮点操作

此程序产生输出：

| 描述 | 结果 |
| :--- | :--- |
| 溢出产生无穷大 | 1.0E308*10==Infinity |
| 渐进式下溢 | 3.14152653589793E-305 3.141526535898258E-310 3.141526535892653E-315 3.142E-320 0.0 |
| 0.0/0.0 不是数字 | NaN |
| float 的不精确结果 | 0 41 47 55 61 82 83 94 97 |
| double 的不精确结果 | 0 49 98 |
| 向 int 舍入转换 | 0 12345 -12345 |

此示例展示了（除其他此外）渐进式下溢会导致精度丢失。

当涉及除以零时，结果 `z` 变为正无穷大，而 `z=0` 是 NaN，这不等于 1.0。

### 4.2.5 boolean 类型和 boolean 值

`boolean` 类型表示一个具有两个可能值的逻辑量，由字面量 `true` 和 `false` 表示（§3.10.3）。

布尔操作符有：

- 关系操作符 `==` 和 `!=`（§15.21.2）
- 逻辑取反运算符 `!`（§15.15.6）
- 逻辑运算符 `&`、`^` 和 `|`（§15.22.2）
- 条件与运算符 `&&`（§15.23）和 条件或运算符 `||`（§15.24）
- 条件运算符（三元运算符） `? :`（§15.25）
- 字符串拼接运算符 `+`（§15.18.1），当给定一个 `String` 操作数和一个布尔操作数时，它将把布尔操作数转换为 `String`（"true" 或 "false"），然后产生一个新创建的字符串，它是两个字符串的拼接。

布尔表达式决定了几类语句中的控制流：

- `if` 语句（§14.9）
- `while` 语句（§14.12）
- `do` 语句（§14.13）
- `for` 语句（§14.14）

布尔表达式还决定了条件运算符 `? :`（§15.25）中评估哪个子表达式。

只有 `boolean` 和 `Boolean` 表达式可以用于控制流语句，并作为条件运算符 `? :` 的第一个操作数。

整数或浮点表达式 `x` 可以遵循 C 语言约定（任何非零值均为 true），通过表达式 `x!=0` 转换为布尔值。

对象引用 `obj` 可以遵循 C 语言约定（除 `null` 以外的任何引用均为 true），通过表达式 `obj!=null` 转换为布尔值。

布尔值可以转换为 `String`（§5.4）。布尔值可以转换为 `Boolean`（§5.5）。

## 4.3 引用类型和值

引用类型有四种：

- 类类型（§8.1）
- 接口类型（§9.1）
- 数组类型（§10.1）
- 注解类型（§9.6）

整数或浮点表达式 `x` 可以遵循 C 语言约定（任何非零值为 true），通过表达式 `x!=0` 转换为布尔值。

对象引用 `obj` 可以遵循 C 语言约定（除 `null` 以外的任何引用均为 true），通过表达式 `obj!=null` 转换为布尔值。

布尔值可以转换为 `String`（§5.4）。布尔值可以转换为 `Boolean`（§5.5）。

### 4.3.1 对象创建

```java
class Point {
    int x, y;

    Point() { System.out.println("default"); }

    Point(int x, int y) { this.x = x; this.y = y; }

    public String toString() { return "(" + x + "," + y + ")"; }
}

class Test {
    public static void main(String[] args) {
        /* 使用 instance 显式创建 Point */
        Point p = null;
        try {
            p = (Point)Class.forName("Point").newInstance();
        } catch (Exception e) {
            System.out.println(e);
        }

        /* 通过初始化器隐式创建数组 */
        Point[] a = { new Point(0,0), new Point(1,1) };

        /* 通过 + 运算符隐式创建字符串 */
        System.out.println("P: " + p);
        System.out.println("a: " + a[0] + "," + a[1] + ")");

        /* 通过数组创建表达式显式创建数组 */
        String[] sa = new String[2];
        sa[0] = "he"; sa[1] = "llo";
        System.out.println(sa[0] + " " + sa[1]);
    }
}
```

此程序产生输出：

```
default
p: (0,0)
a: { (0,0), (1,1) }
hello
```

引用上的操作是对象：

- 字段访问，使用限定名（§6.6）或字段访问表达式（§15.11）
- 方法调用（§15.12）
- 字符串拼接运算符 `+`（§15.18.1），当给定一个 `String` 操作数和一个引用时，它将通过调用所引对象的 `toString` 方法将引用转换为 `String`（如果引用为 `null`，则使用 "null"，或者 `toString` 的结果为空引用），然后将产生一个新的创建的字符串，该字符串是两个字符串的拼接
- `instanceof` 运算符（§15.20.2）
- 引用相等性运算符 `==` 和 `!=`（§15.21.3）
- 条件运算符 `? :`（§15.25）。

可能存在指向同一个对象的引用。对象具有状态，存储在类的实例字段中，或者存储在数组对象的组件变量中。如果两个变量包含指向同一个对象的引用，则可以使用一个变量的引用来修改对象的状态，然后通过另一个变量的引用观察到修改后的状态。

### 示例 4.3.1-2. 原始类型与引用标识性

```java
class Value { int val; }

class Test {
    public static void main(String[] args) {
        int i1 = 3;
        int i2 = i1;
        i2 = 4;
        System.out.print("i1==" + i1);
        System.out.println(" i2==" + i2);

        Value v1 = new Value();
        v1.val = 5;
        Value v2 = v1;
        v2.val = 6;
        System.out.print("v1.val==" + v1.val);
        System.out.println(" v2.val==" + v2.val);
    }
}
```



该程序输出：

```
i1==3 but i2==4
v1.val==6 and v2.val==6
```

因为 `v1.val` 和 `v2.val` 引用由唯一的 `new` 表达式创建的 `Value` 对象中的同一个实例变量（§4.12.3），而 `i1` 和 `i2` 是不同的变量。

每个对象都关联有一个监视器（§17.1），该监视器被 `synchronized` 方法（§8.4.3）和 `synchronized` 语句（§14.19）用于提供对多线程并发访问状态的控制（§17 线程与锁）。

## 4.3.2 类对象

`Object` 类是所有其他类的超类（§8.1.4）。

所有类和数组类型都继承（§8.4.8）自 `Object` 类的方法，这些方法总结如下：

- `clone` 方法用于创建对象的副本。
- `equals` 方法定义了对象相等性的概念，这种相等性基于值的比较，而不是引用比较。
- `finalize` 方法在对象销毁之前运行（§12.6）。
- `getClass` 方法返回表示对象所属类的 `Class` 对象。

每个引用类型都存在一个 `Class` 对象。它可以被用于，例如，发现类的完全限定名、其成员、其直接超类以及它所实现的所有接口。

`getClass` 方法调用表达式的类型是 `Class<? extends T>`，其中 `T` 是为 `getClass` 查找的类或接口（§15.12.1），且 `T` 表示 `T` 的擦除（§4.6）。

声明为 `synchronized`（§8.4.6）的类方法会在该类的 `Class` 对象关联的监视器上同步。

- `hashCode` 方法非常有用，配合 `equals` 方法常用于 `java.util.HashMap` 等哈希表。
- `wait`、`notify` 和 `notifyAll` 方法用于使用线程的并发编程（§17.2）。
- `toString` 方法返回对象的字符串表示。

## 4.3.3 类字符串

`String` 类的实例表示 Unicode 代码点的序列。

`String` 对象具有一个常量（不变的）值。

`String` 字面量（§31.0.5）是指向 `String` 类实例的引用。

字符串拼接运算符 `+`（§15.18.1）在结果不是常量表达式（§15.29）时隐式地创建一个新的 `String` 对象。

# 类型、值与变量

## 4.3.4 当引用类型相同时

如果两个引用类型在与同一个模块（§7.3）相关的编译单元中声明，它们是相同的编译时类型，并且具有相同的二进制名称（§13.1），且它们的类型参数（如果有）也是相同的（递归应用此定义），它们就是相同的。

当两个引用类型相同时，有时被称为同一个类或同一个接口。

在运行时，多个具有相同二进制名的引用类型可能被不同的类加载器同时加载。这些类型可能代表也可能不代表相同的类型声明。即使这样的两个类型代表相同的类型，它们也被认为是不同的。

两个引用类型是运行时类型，如果满足：

- 它们都是类类型或接口类型，由同一个类加载器定义，并具有相同的二进制名称（§13.1），在这种情况下，它们有时被称为相同的运行时类或相同的运行时接口。
- 它们是数组类型，且它们的组件类型是相同的运行时类型（§10 数组）。

## 4.4 类型变量

类型变量是一个未限定的标识符，在类、接口、方法和构造函数体内用作类型。

类型变量通过泛型类、接口、方法或构造函数的类型参数声明而引入（§8.1.2, §9.1.2, §8.4.4, §8.8.4）。

```
TypeParameter:
    [TypeParameterModifier] TypeIdentifier [TypeBound]

TypeParameterModifier:
    Annotation

TypeBound:
    extends TypeVariable
    extends ClassOrInterfaceType [AdditionalBound]
```

# 类型变量

```
AdditionalBound:
    extends TypeVariable
    extends InterfaceType
```

声明为类型参数的类型变量范围位于 §6.3。每个声明为类型参数的类型变量 `T` 有一个边界。如果没有声明边界，则假设 `Object`。如果声明了边界，它由：

- 单个类型变量 `T`，
- 类或接口类型 `I_1 ... I_n`。

如果 `I_1 ... I_n` 中的任何一个类型不是类类型，则发生编译错误。

边界的擦除（§4.6）的所有类型必须是互不相同的，否则发生编译错误。

类型变量 `T` 必须同时是所有不同类型的子类型，否则发生编译错误。

边界中类型的顺序对于类型变量擦除没有意义，类型变量只出现在第一个位置。

类型变量 `T & I_1 ..._n` 的成员是交集类型（§4.9）在类型变量声明处出现。

## 示例 4.4-1. 类型变量的成员

```java
package TypeVar;

class C {
    public void mPublic() {}
    protected void mProtected() {}
    private void mCPage() {}
    private void mPrivate() {}
}

interface I {
    void MI();
}

class CI extends C implements I {
    public void MI() {}
}

class Test {
    <T extends C & I> void test(T t) {
        t.MI();      // OK
        t.mPublic();  // OK
        t.mProtected(); // OK
        t.mPackage(); // OK
        t.mPrivate(); // 编译错误
    }
}
```

类型变量 `T` 具有与交集类型 `C & I` 相同的成员，该交集类型在作用域内定义。接口的成员都是公共的，除非被覆盖。`MI` 是 `CT` 和 `T` 的成员。在 `C` 的成员中，所有的 `mPrivate` 都被 `CT` 继承并是 `CT` 和 `T` 的成员。

如果 `C` 在与 `T` 不同的包中声明，那么对 `mPackage` 的调用会导致编译错误，因为在声明 `T` 的点不可访问。

# 参数化类型

在本规范中，每当我们谈论类或接口类型时，我们都包含其泛型版本，除非显式排除。

如果满足以下任意条件，则两个参数化类型在证明上是不同的：

- 它们是不同泛型声明的参数化形式。
- 它们的任何一个类型参数在证明上是不同的。

根据 §8.1.2 示例中的泛型类型，以下是一些格式正确的参数化类型：

- `Seq<String>`
- `Seq<Seq<String>>`
- `Seq<String>.Zipper<Integer>`
- `Pair<String, Integer>`

以下是这些泛型类型的一些错误参数化：

- `Seq<int>` 是非法的，因为基本数据类型不能作为类型参数。
- `Pair<String>` 是非法的，因为类型参数不足。
- `Pair<String, String, String>` 是非法的，因为类型参数过多。

参数化类型可以是嵌套的泛型类 `C` 或接口的参数化形式。例如，如果一个非泛型类 `C` 有一个泛型成员类 `D<T>`，那么 `C.D<Object>` 就是一个参数化类型。如果一个泛型类 `C<T>` 有一个非泛型成员类 `D`，那么成员类型 `C<String>.D` 是一个参数化类型，即使类 `D` 本不是泛型的。

## 4.5.1 参数化类型的类型参数

类型参数可以是引用类型，也可以是通配符（wildcards）。通配符在只需要关于类型参数的部分信息的情况下非常有用。

```
TypeArgumentList:
    TypeArgument (, TypeArgument)

TypeArgument:
    ReferenceType
    Wildcard
```

# 类型、值与变量

```
Wildcard:
    [Annotation] ? [WildcardBounds]

WildcardBounds:
    extends ReferenceType
    super ReferenceType
```

通配符可以赋予显式边界，就像普通的类型变量声明一样。上界由以下语法表示，其中 `B` 是边界：

```
? extends B
```

与在方法签名中声明的普通类型变量不同，使用通配符时不需要类型推断。因此，可以使用以下语法在通配符上声明下界，其中 `B` 是下界：

```
? super B
```

通配符 `? extends Object` 等于无界通配符 `?`。

两个参数在满足以下任意条件时在证明上是不同的：

- 两个参数都不是类型变量或通配符，且两个参数不是相同类型。
- 其中一个参数是类型变量或通配符，具有上界（必要时通过捕获转换 §5.1.10）`S`，而另一个参数 `T` 不是类型变量或通配符；且非 `|S| <: |T|` 也非 `|T| <: |S|`（§4.8, §4.10）。
- 每个参数都是类型变量或通配符，具有上界（必要时通过捕获转换）`S` 和 `T`，且非 `|S| <: |T|` 也非 `|T| <: |S|`。

如果类型 `T1` 包含另一个类型参数 `T2`，记为 `T2 <= T1`，如果在以下规则的自反和传递闭下（其中 `<:` 表示子类型 §4.10），由 `T2` 表示的类型集合是由 `T1` 表示的类型集合的子集：

- `? extends T <= extends S` 如果 `T <: S`
- `? extends T <= extends Object`
- `? super T <= super S` 如果 `S <: T`
- `? super T <= extends Object`
- `T <= T`
- `T <= extends T`
- `T <= super T`

通配符与既有类型理论的关系是一个有趣的课题，我们将简要遵循这一点。通配符是存在性泛型声明 `G<T extends B>` 的受限形式，`G<?>` 大致类似于 `Some X <: B. G<X>`。

从历史上看，通配符是 Atsushi Igarashi 和 Mirko Viroli 工作的直接结果。更深入讨论的读者可以参考 Atsushi Igarashi 和 Mirko Viroli 写的《On Variance-Based Subtyping for Generic Types》，发表于第 16 届欧洲对象编程会议（ECOOP 2002）。这项工作本身建立在 Kresten Thorup 和 Mads Torgersen 的工作（Unifying Genericity, ECOOP 99）以及溯到 Pierre America 关于变性的工作（OOPSLA 89）之上。

通配符与上述论文中的构造在某些细节上有所不同，特别是 Igarashi 和 Viroli 描述的捕获版本（§5.1.10）。对于通配符的正式说明，可以参考 Torgersen、Ernst 和 Christian Plesner Hansen 在第 12 届对象编程基础会议（Foundations of Object Oriented Programming, FOOL 2005）的论文。

## 示例 4.5.1-1. 无界通配符

```java
import java.util.Collection;
import java.util.ArrayList;

class Test {
    static void printCollection(Collection<?> c) { // 通配符
        for (Object o : c) {
            System.out.println(o);
        }
    }

    public static void main(String[] args) {
        Collection<String> cs = new ArrayList<>();
        cs.add("Hello");
        cs.add("world");
        printCollection(cs);
    }
}
```

注意，将 `Collection<Object>` 作为参数 `c` 的类型并不实用，该方法只能配合 `Collection<String>` 使用。相比之下，无界通配符允许传递任何集合。这是一个由通配符参数化的示例：

```java
public Method get(Class<?>[] parameterTypes) { ... }
```

## 示例 4.5.1-2. 有界通配符

```java
boolean addAll(Collection<? extends E> c)
```

这里，方法声明在 `Collection<E>` 内部，设计用于调用时将其参数的所有元素添加到集合中。自然的倾向是使用 `Collection<E>` 作为 `c` 的类型，但是不必要的限制。另一种替代方案是将方法声明为泛型：

```java
<T> boolean addAll(Collection<T> c)
```



这个版本足够灵活，但注意类型参数仅在签名中使用一次。这反映了类型参数没有用于表示参数、返回类型和 throws 之间的任何依赖关系。在缺乏这种依赖关系的情况下，泛型方法被认为是不良风格，推荐使用通配符：

`Reference(T referent, Reference<? super T> queue)`

在这里，`referent` 可以插入任何元素类型为 `referent` 的 `T` 上类型的集合中；`T` 是通配符的下界。

## 4.5.2 参数化类型的成员与构造

假设 `c` 是带有参数 `A₁,...,ₙ` 的泛型类或接口，`c<T1,...,ₙ>` 是 `c` 的参数化，其中对于 1 ≤ i ≤ n，`Tᵢ` 是一个类型（而非通配符）。那么：

- `m` 是 `c` 中的成员或构造声明，其类型声明为 `T` (§8.2, §8.8.6)。
- `c<T1,...,ₙ>` 中 `m` 的类型是 `T[A₁=T₁, ...,Aₙ=ₙ]`。
- `m` 是 `D` 中的成员或构造声明，其中 `D` 是 `C` 扩展的类或 `C` 实现的接口。`D<U1,...,ₙ>` 是对应 `c<T1,...,ₙ>` 的上类型。

`c<T1,...,ₙ>` 中 `m` 的类型是 `D<U1,...,ₙ>` 中 `m` 的类型。

如果 `c<U1,...,ₙ>` 参数化中的任何参数都是通配符，那么：

- `c<T1,...,ₙ>` 中的字段、方法和构造器的类型是 `c<T1,...,ₙ>` 捕获转换中的字段、方法和构造器的类型 (§5.1.10)。

## 4.6 类型擦除

- 假设 `D` 是 `c` 中的（可能是泛型的）类或接口声明。那么 `c<T1,...,Tn>` 中 `D` 的类型是 `D`，如果 `D` 是泛型的，则所有类型参数都是无界通配符。

这没有影响，因为在不执行捕获转换的情况下无法访问参数化类型的成员，在类实例创建表达式的 `new` 关键字之后无法使用通配符 (§15.9)。

上一段的例外是嵌套参数化类型被用作 `instanceof` 操作符的表达式时 (§15.20.2)，此时未应用捕获转换。

泛型类型声明中声明的静态成员必须使用对应泛型类型的非泛型类型进行引用 (§6.1, §6.5.5.2, §6.5.6.2)，否则将发生编译错误。

换句话说，通过参数化类型引用泛型类型中声明的静态成员是非法的。

类型擦除是从类型（包括参数化类型或类型变量）到类型（永远不是参数化类型或类型变量）的映射。我们用 `|T|` 表示类型 `T` 的擦除。该映射定义如下：

- 参数化类型 (§4.5) `G<T1,...,Tn>` 的擦除是 `|G|`。
- 嵌套类型 `T.C` 的擦除是 `|T|.C`。
- 数组类型 `T[]` 的擦除是 `|T|[]`。
- 类型变量 (§4.4) 的擦除是其左侧边界的擦除。
- 其他所有类型的擦除都是类型本身。

类型擦除还将构造函数或方法的签名 (§8.4.2) 映射到没有参数化类型或类型变量的签名。

方法的返回类型 (§8.4.5) 和泛型方法或构造函数的类型参数 (§8.4.4, §8.8.4) 如果方法或构造函数的签名被擦除时也会擦除。

泛型方法签名的擦除没有类型参数。

# 类型、值与变量

## 4.7 可具体化类型 (Reifiable Types)

由于某些类型信息在编译期间会被擦除，因此并非所有类型在运行时都是可用的。运行时完全可用的类型被称为可具体化类型（reifiable types）。

当且仅当满足以下条件之一时，类型是可具体化的：

- 它引用的是一个非泛型的类或接口类型声明。
- 它是一个参数化类型，其中所有的类型参数都是无界通配符（§4.5.1）。
- 它是一个原始类型（raw type）（§4.8）。
- 它是一个基本类型（§4.2）。
- 它是一个数组类型（§10.1），其元素类型 `τ` 用 `[]` 分隔，且 `τ` 本身是可具体化的。
- 它是一个嵌套类型，其中对于每个用 `[]` 分隔的类型 `τ`，`τ` 本身是可具体化的。

> 例如，如果一个泛型类 `X<T>` 拥有一个泛型成员类 `Y<U>`，那么类型 `X<?>.Y<?>` 是可具体化的，因为 `X<?>` 是可具体化的且 `Y<?>` 也是可具体化的。类型 `X<?>.Y<Object>` 则不可具体化，因为 `Y<Object>` 不是可具体化的。

交叉类型（intersection type）不可具体化。

> 不将所有泛型变为可具体化的决策，是影响 Java 编程语言类型系统最关键且最具争议的设计决策之一。

归根结底，这一决策最重要的动机是为了与现有代码的兼容性。从新的意义上说，添加新结构对预先代码没有影响。只要 Java 编程语言在之前的版本中编写的每个程序在新版本中保留其含义，它就与早期版本兼容。然而，这种可以被称为“语言兼容性”的概念仅仅具有理论上的意义。真实的程序（即使是 "Hello World"）是由多个编译单元组成的，这些单元由 Java SE 平台提供（例如 `java.lang` 和 `java.util` 中的元素）。在实践中，最低要求是平台兼容性——即为旧版本的 Java SE 编写的程序在新版本中继续运行且不变。

提供平台兼容性的一种方法是保持平台功能不变，仅添加新功能。例如，与其修改 `java.util` 中现有的 Collections 层次结构，不如引入一个利用泛型的新库。

这种方案的缺点是，Collection 库的现有客户端极难迁移到新库。Collections 用于在独立开发的模块之间交换数据；如果供应商决定切换到新的泛型库，该供应商还必须分发两个版本的代码以兼容其客户。依赖其他供应商代码的库在供应商的库更新之前，无法修改为使用泛型。如果两个模块相互依赖，则必须同时进行更改。

显然，上述概述的平台兼容性并没有为随心所欲宽松的新功能提供一条现实的路径。因此，泛型类型系统的设计寻求支持**迁移兼容性**（migration compatibility）。迁移兼容性允许现有代码在演进过程中利用泛型的优势，而不会在独立开发的软件模块之间施加依赖关系。

迁移兼容性的代价是，无法对泛型类型系统进行完全且健全的具体化，至少在迁移进行期间是这样。

## 4.8 原始类型 (Raw Types)

为了便于与非泛型的遗留代码交互，可以使用参数化类型（§4.5）的擦除（§4.6）或元素类型为参数化类型的数组类型（§10.1）的擦除作为类型。此类类型被称为*原始类型*（raw type）。

更准确地说，原始类型由以下任一定义：
- 通过获取泛型类型声明的名称但不带随附的类型参数列表形成的引用类型。
- 元素类型为原始类型的数组类型。
- 原始类型 `R` 的非静态成员类型，且该类型未继承自 `R` 的父类或接口。

非泛型类或接口类型不是原始类型。

```java
class Outer<T> {
    T t;

    class Inner {
        void set(T t1) { t = t1; }
    }
}
```

```java
class Outer<T> {
    class Inner<S> {
        S s;
    }
}
```

```java
Outer<Double> x = null; // illegal
Double d = x;
```

```java
Outer<Integer> x = null; // illegal
```

```java
class Outer<T> {
    T t;

    class Inner {
        void set(T t1) { t = t1; }
    }
}
```

```java
Outer<String> x = null; // illegal
Double d = x;
```

```java
Outer<String> x = null; // illegal
```

```java
class Inner {
    void set(T t1) { t = t1; }
}
```

```java
class Outer<T> {
    T t;

    class Inner {
        void set(T t1) { t = t1; }
    }
}
```

```java
class Outer<T> {
    T t;

    class Inner {
        void set(T t1) { t = t1; }
    }
}
```

```java
class Inner {
    S s;
}
```

```java
class RawType {
    S s;
}
```

原始类型的使用仅是出于遗留代码的妥协。强烈建议在引入泛型后编写的代码中**不**使用原始类型。为了确保类型规则的违背总是被标记，对原始类型的某些访问将产生未检查警告（unchecked warnings）。在访问成员或构造函数时的未检查警告的规则如下：

- 在字段赋值时：如果字段表达式（§15.11）是原始类型，则如果擦除更改了字段类型，将产生未检查警告。
- 在调用方法或构造函数时：如果类或接口的类型（§15.12.1）是原始类型，则如果擦除更改了方法或构造函数的任何形式参数类型，将产生未检查警告。
- 对于形式参数类型未更改的方法调用（如果返回类型和或 throws 子句发生变化）、读取字段或或原始类型的类实例，不会产生未检查警告。

注意，未检查警告与缩小引用转换（§15.6）、未检查转换（§15.9）、方法声明（§8.1, §48.4.3）以及某些表达式（§15.12.4, §15.13.2, §15.27.3）不同。这里的警告来自遗留消费者使用泛型库的情况。例如，库声明了一个继承自 `String` 的泛型类 `Foo<I>`，它有一个具有 `Vector<>` 类型的字段 `f`，但消费者将一个整数向量赋值给 `f`，其中 `e` 是原始类型。该遗留消费者收到一个警告，因为这可能为泛型库的泛型消费者造成类型污染（§41.2.2）。

（注意，遗留消费者可以将库中的 `Vector<String>` 赋值给其 `Vector` 变量而不会产生警告。也就是说，子类型规则（§41.10.2）使得原始类型的变量可以被赋值任何类型的值。）

未检查转换的警告涵盖了对立的情况，即泛型消费者使用遗留库。例如，库的一个方法具有原始类型并将方法调用的结果传递给 `Vector<String>` 变量。这将是不安全的，因为原始向量的元素类型可能与 `String` 不同，但为了启用，仍允许未检查转换。

# 类型、值与变量

## 原始类型 (Raw Types)

与旧代码进行交互。未检查转换（unchecked conversion）的警告表明，泛型化的消费者可能会在程序的其他地方遇到堆污染（heap pollution）问题。

### 示例 4.8-1 原始类型

```java
class Cell<E> {
    E value;

    Cell(E v) { value = v; }

    E get() { return value; }

    void set(E v) { value = v; }

    public static void main(String[] args) {
        Cell x = new Cell<String>("abc");

        System.out.println(x.value); // OK, 类型为 Object

        System.out.println(x.get()); // OK, 类型为 Object

        x.set("def"); // 未检查警告
    }
}
```

### 示例 4.8-2 原始类型与继承

```java
import java.util.*;

class NonGeneric {
    Collection<Number> myNumbers() { return null; }
}

abstract class RawMembers<T> extends NonGeneric
    implements Collection<String> {

    static Collection<NonGeneric> cng =
        new ArrayList<NonGeneric>();

    public static void main(String[] args) {
        RawMembers<Number> rw = null;

        Collection<Number> cn = rw.myNumbers(); // OK

        Iterator<String> is = rw.iterator(); // 未检查警告

        Collection<NonGeneric> cnn = rw.cng; // OK, 静态成员
    }
}
```



# 类型、值与变量

## 原始类型

与旧代码进行交互。未检查转换的警告表明，泛型化的消费者可能会在程序的其他地方遇到堆污染问题。

### 示例 4.8-1 原始类型

```java
class Cell<E> {
    E value;
    Cell(E v) { value = v; }
    E get() { return value; }
    void set(E v) { value = v; }
    public static void main(String[] args) {
        Cell x = new Cell<String>("abc");
        System.out.println(x.value); // OK, 类型为 Object
        System.out.println(x.get()); // OK, 类型为 Object
        x.set("def"); // 未检查警告
    }
}
```

### 示例 4.8-2 原始类型与继承

```java
import java.util.*;

class NonGeneric {
    Collection<Number> myNumbers() { return null; }
}

abstract class RawMembers<T> extends NonGeneric
    implements Collection<String> {
    static Collection<NonGeneric> cng =
        new ArrayList<NonGeneric>();
    public static void main(String[] args) {
        RawMembers<Number> rw = null;
        Collection<Number> cn = rw.myNumbers(); // OK
        Iterator<String> is = rw.iterator(); // 未检查警告
        Collection<NonGeneric> cnn = rw.cng; // OK, 静态成员
    }
}
```



在该程序（并非为了运行）中，`RawMembers<T>` 继承了方法：

```
Iterator<String> iterator()
```

源自父接口 `Collection<String>`。原始类型 `RawMembers` 从 `Collection`（`Collection<String>` 的擦除）继承了 `iterator()`，这意味着 `RawMembers` 中 `iterator()` 的返回类型是 `Iterator`。因此，尝试将 `rw.iterator()` 赋值给 `Iterator<String>` 需要未检查转换，从而会发出编译时的未检查继承。

相反，`RawMembers` 从 `NonGeneric` 类继承了 `myNumbers()`，该类的擦除类型为 `NonGeneric`。因此，`RawMembers` 中 `myNumbers()` 的返回类型没有被擦除，尝试将 `rw.myNumbers()` 赋值给 `Collection<Number>` 不需要未检查转换，因此不会发出编译时的未检查继承。

类似地，静态成员 `c` 即使通过类型的实例访问，也会返回其参数化类型。请注意，通过实例访问静态成员被认为是不良风格，是不推荐的。

此示例揭示了原始类型的某些成员没有被擦除，即类型被参数化的 `static` 成员以及从非泛型父类型继承的成员。

原始类型与通配符密切相关。两者都基于存在类型。原始类型可以被看作是有故意不安全的通配符，以适应与旧代码的交互。在历史上，原始类型早于通配符；它们首次在 GJ 中引入，并在 Gil Bracha、Martin Odersky、David Stoutamper 和 Philip Wadler 发表的论文《Making the future safe for the past: Genericity to the Java Programming Language》中描述，该论文发表于 1998 年 10 月的 ACM 面向对象编程、系统、语言和应用会议（OOPSLA 98）。

## 4.9 交集类型

交集类型的类型为 $T_1 \& \dots \& T_n$ ($n > 0$)，其中 $T_i$ ($1 \le i \le n$) 是类型。

交集类型可以从类型参数边界（4.4）和强制转换表达式（5.16）推导出；它们也出现在捕获转换（5.1.10）和最小上界计算（4.10.4）的过程中。

每个交集类型都是其值是所有类型 $T_i$ ($1 \le i \le n$) 之值的对象。

每个交集类型 $T_1 \& \dots \& T_n$ 为了识别交集类型的成员，会诱导出名义类或接口，如下所示：

- 对于每个 $T_i$ ($1 \le i \le n$)，令 $C_i$ 为满足 $T_i <: C_i$ 的最具体的类或数组类型。必须存在某个 $C_k$，使得对于任何 $i$ ($1 \le i \le n$) 都有 $C_k <: C_i$，否则将发生编译时错误。
- 对于 $1 \le j \le n$，如果 $T_j$ 是类型变量，则令 $T'_j$ 为一个其成员与 $T_j$ 公有成员相同的接口；否则，如果 $T_j$ 是接口，则令 $T'_j$ 为 $T_j$。

如果 $C_k$ 是 `Object`，则诱导出一个概念接口；否则，则诱导出一个直接父类为 $C_k$ 的概念类 $C_k$。该类或接口具有直接父接口 $T_1, \dots, T_n$，并声明在交集类型所在的包中。

交集类型的成员是其所诱出的类或接口的成员。

值得仔细推敲交集类型与类型变量边界之间的区别。每个类型变量边界都会诱导出一个交集类型。这种交集类型通常是平凡的，由单个类型组成。边界的形式是限制的（只有第一个元素可以是类或类型变量，且边界中只能出现一个类型变量），以防止某些尴尬情况的发生。然而，捕获转换可能会导致创建边界更通用的类型变量，例如数组类型。

## 4.10 子类型

子类型和父类型关系是类型上的二元关系。一个类型的子类型是通过对直接父类型关系（记为 $S > T$）进行反射闭包和传递闭包得到的。我们写 $S <: T$ 来表示在 $T$ 和 $S$ 之间存在父类型关系。如果 $S \neq T$，则 $S$ 是 $T$ 的真父类型，记为 $S > T$。$T$ 是 $S$ 的直接父类型，记为 $T < S$。子类型不扩展到参数化类型：$T <: S$ 并不意味着 $C<T> <: C<S>$。

### 4.10.1 基本类型之间的子类型

以下规则定义了基本类型之间的直接父类型关系：

- $double > float$
- $float > long$
- $long > int$
- $int > short$
- $short > byte$

### 4.10.2 类和接口类型之间的子类型

给定一个非泛型类型 $c$，类型 $c$ 的直接父类型是以下所有类型：

- $c$ 的直接父类（8.4）。
- $c$ 的直接父接口（8.5）。
- 类型 `Object`，如果 $c$ 是泛型类型。

### 4.10.3 参数化类型的子类型

对于参数化类型，子类型关系定义为：$C<T_1, \dots, T_n> <: C<S_1, \dots, S_n>$ 当且仅当对于所有 $i$ ($1 \le i \le n$)，$T_i <: S_i$。

### 4.10.4 最小上界

最小上界（least upper bound，lub）的计算涉及擦除超类型集合、擦除候选集（EC）、最小擦除候选集（MEC）、相关参数化、候选参数化、最小包含参数化（lcp）和最小包含类型参数（lcta）等概念。

- 对于每个 $U_i$ ($1 \le i \le k$)：
  - 设 $ST(U_i)$ 为 $U_i$ 的超类型集合。
  - $EST(U_i)$ 为 $U_i$ 的擦除超类型集合，定义为：$EST(U_i) = \{ |W| \mid W \in ST(U_i) \}$，其中 $|W|$ 是 $W$ 的擦除结果。

计算擦除超类型集合是为了处理类型集合包含泛型类型不同参数化的情况。

例如，给定 `List<String>` 和 `List<Object>`，简单地取交集 $ST(List<String>) = \{ List<String>, Collection<String>, Object \}$ 和 $ST(List<Object>) = \{ List<Object>, Collection<Object> \}$ 会得到一个集合 $\{ Object \}$，我们将丢失“上界可以安全地假设为 List”这一事实。

相比之下，$EST(List<String>) = \{ List, Collection, Object \}$ 和 $EST(List<Object>) = \{ List, Collection, Object \}$ 得到 $\{ List, Collection, Object \}$，这最终允许我们生成 `List<?>`。

- $EC$ 是 $U_2 \dots U_k$ 的擦除候选集，是所有集合 $EST(U_i)$ ($1 \le i \le k$) 的交集。

- $MEC$ 是 $U_2 \dots U_k$ 的最小擦除候选集，定义为：
  $MEC = \{ v \mid v \in EC，且对于所有 $W \neq v$，不存在 $W \to v$ 的情况 \}$

由于我们正在寻找更精确的方法，我们想要过滤掉所有作为其他候选类型超类型的候选类型。这就是 $MEC$ 所完成的工作。在我们的示例运行中，$EC = \{ List, Collection, Object \}$，因此 $MEC = \{ List \}$。下一步是恢复 $MEC$ 中擦除类型的类型参数。

- 对于泛型类型的任意元素 $G$：
  设 $G$ 的“相关”参数化 $Relevant(G)$ 定义为：
  $Relevant(G) = \{ v \mid 1 \le i \le k; v \in ST(U_i) \text{ 且 } v = G<\dots> \}$

在我们的示例中，$MEC$ 中唯一的泛型元素是 `List`，且 $Relevant(List) = \{ List<String>, List<Object> \}$。我们现在寻求为 `List` 寻找一个类型参数以连接（4.5.1）中的 `String` 和 `Object`。

这是通过下面定义的最小包含参数化（least containing parameterization, lcp）操作实现的。第一行定义了在集合（如 $Relevant(List)$）上的 $lcp()$，其是对包含该集合元素的列表的操作。第二行定义了在该列表上的操作是对集合中的元素进行两两递归。第三行定义了在参数化类型对上的 $lcp()$，它反过来依赖于最小包含类型参数（least containing type argument, lcta）的概念。$lcta$ 对所有可能的情况都有定义。

设 $G$ 的“候选”参数化 $Candidate(G)$ 是包含 $G$ 的所有相关参数化的最特定泛型参数化。

$Candidate(G) = lcp(Relevant(G))$

其中 $lcp(U)$ 最小包含参数化定义为：

- $lcp(S) = lcp(e_1, ..., e_n)$ 其中 $e_i$ ($1 \le i \le n$) 在 $S$ 中
- $lcp(e_i, ..., e_n) = lcp(Y_i, ..., e_j, ..., e_n)$
- $lcp(G<X_1, ..., X_n, ..., Y>) = G<lcta(X_1, Y), ..., lcta(X_n, Y)>$
- $lcp(G<X_1, ..., X_n>) = G<lcta(X_1), ..., lcta(X_n)>$

其中 $lcta(U)$ 最小包含类型参数定义为：（假设 $U$ 和 $V$ 是类型）

- $lcta(U, V) = U$，如果 $U = V$，否则扩展为 $lub(U, V)$
- $lcta(U, ? extends V) = ? extends lub(U, V)$
- $lcta(U, ? super V) = ? super glb(U, V)$
- $lcta(? extends U, ? extends V) = ? extends lub(U, V)$
- $lcta(? extends U, ? super V) = ?$
- $lcta(? super U, ? super V) = ? super glb(U, V)$
- $lcta(U) = ?$ 如果 $U$ 的上界是 `Object`，否则扩展为 $lub(U, Object)$

其中 $glb$ 定义在 §5.1.10 中。

- 令 $lub(U_1 \dots U_k) = Best(W_1) \& \dots \& Best(W_k)$

其中 $W_i$ ($1 \le i \le r$) 是 $MEC$ 的元素，即 $U_1 \dots U_k$ 的最小擦除候选集；且如果这些元素中的任何一个是泛型的，我们使用该候选参数化（以便恢复类型参数）：

$Best(x) = Candidate(x)$ 如果 $x$ 是泛型的；否则为 $x$。

严格来说，这个 $lub(U)$ 函数仅近似于最小上界。形式上，可能存在其他类型 $\tau$，使得所有 $U_1 \dots U_k$ 都是 $\tau$ 的子类型且 $\tau$ 是 $lub(U_1, \dots, U_k)$ 的子类型。然而对于 Java 语言来说，$lub(U_1, \dots, U_k)$ 就足够了。$lub()$ 函数产生一个无限类型是允许的，Java 编译器必须识别此类类型。

### 投影

在 $lub()$ 期间引入了合成类型。有时需要找到某个类型的接近超类型，而向下投影并不总是存在。类型 $\tau$ 关于限制变量集合的向下投影定义如下：

- 如果 $\tau$ 没有提到任何限制变量，则结果为 $\tau$。
- 如果 $\tau$ 是一个限制变量，则结果为 $\tau$ 的向上投影。

类型 $\tau$ 关于限制变量集合的向上投影是一个偏函数，其定义如下：

- 如果 $\tau$ 没有提到任何限制变量，则结果为 $\tau$。
- 如果 $\tau$ 是一个限制变量，则结果为 $\tau$ 的向上投影。
- 如果 $\tau$ 是参数化类类型或参数化接口类型，$G<A_1, \dots, A_n>$，则结果为 $G<A_1', \dots, A_n'>$，其中对于 $1 \le i \le n$，$A_i'$ 由如下方式从 $A_i$ 推导出：
  - 如果 $A_i$ 没有提到任何限制变量，则 $A_i' = A_i$。
  - 如果 $A_i$ 提到了限制变量，令 $U$ 为 $A_i$ 的向上投影。$A_i'$ 是一个通配符，由三种情况定义：
    - $U$ 不是 `Object`，且 $G$ 的第 $i$ 个参数的声明边界 $B_i$ 提到了 $G$ 的类型参数，或 $B_i$ 不是 $U$ 的子类型，则 $A_i'$ 是上界通配符，`? extends U`。
    - 否则，如果 $A_i$ 的向下投影是 $L$，则 $A_i'$ 是下界通配符，`? super L`。
    - 否则，$A_i'$ 是提到限制变量的上界通配符，令 $U$ 为通配符边界的向上投影。$A_i'$ 是上界通配符，`? extends U`。
  - 如果 $A_i$ 是提到限制变量的下界通配符，如果通配符边界的向下投影是 $L$，则 $A_i'$ 是下界通配符，`? super L`；如果通配符边界的向下投影未定义，则 $A_i'$ 是无界通配符，`?`。
- 如果 $\tau$ 是数组类型，$S[]$，则结果是数组类型，其组件类型为 $S$ 的向上投影。
- 如果 $\tau$ 是交集类型，则结果是交集类型。对于 $\tau$ 的每个元素 $S$，结果具有一个 $S$ 的向上投影元素。

类似于 $lub$ (§4.10.4)，由于对类型变量边界的递归，向上投影和向下投影可能会产生无限类型。

## 4.11 类型使用的位置

类型用于大多数类型的声明以及某些类型的表达式中。具体而言，有 16 处使用类型的类型上下文：

### 在声明中：

1. 类声明中 `extends` 或 `implements` 子句中的类型（§8.1.4, §8.1.5, §8.5, §9.5）
2. 接口声明中 `extends` 子句中的类型（§9.1.3, §8.5, §9.5）
3. 方法的返回类型（包括注解类型元素的类型）（§8.4.5, §9.4, §9.6.1）
4. 方法或构造函数 `throws` 子句中的类型（§8.4.6, §8.8.5, §9.4）
5. 泛型类、接口、方法或构造函数的类型参数声明中 `extends` 子句的类型（§8.1.2, §9.1.2, §8.4.4, §8.8.4）
6. 类或接口的字段声明中的类型（包括枚举常量）（§8.3, §9.3, §8.9.1）
7. 方法、构造函数或 lambda 表达式的形式参数声明中的类型（§8.4.1, §8.8.1, §9.4, §15.27.1）
8. 方法接收者的类型（§8.4）
9. 局部变量声明中的类型（§14.4, §14.14.1, §14.14.2, §14.20.3）
10. 异常参数声明中的类型（§14.20）

### 在表达式中：

11. 显式构造函数调用语句、类实例创建表达式或方法调用表达式中显式类型参数列表中的类型（§8.8.7.1, §15.9, §15.12）
12. 在未限定的类实例创建表达式中，作为要实例化的类型（§15.9），或作为要实例化的匿名内部的直接父类或直接父接口（§15.9.5）
13. 数组创建表达式中的元素类型（§15.10.1）
14. 转换表达式中转换操作符中的类型（§15.16）
15. `instanceof` 关系运算符后的类型（§15.20.2）
16. 在方法引用表达式（§15.13）中，作为查找成员方法的引用类型，或作为要构造的类类型或数组类型。

此外，类型还用于：

- 上述任何语境中，数组类型的元素类型；以及
- 上述任何语境中，参数化类型的非通配符类型参数，或通配符类型参数的边界。

最后，Java 编程语言中有三个特殊术语表示对类型的使用：

- 无上界通配符（§4.5.1）
- 变长参数类型中的省略 `...`（§8.4.1），用于表示数组类型
- 构造函数声明中类型的简单名称（§8.8），用于表示所构造对象的类

类型上下文中的类型含义见于：

- §4.2，用于基本数据类型
- §4.4，用于类型参数
- §4.5，用于参数化的类和接口类型，或作为参数化类型中的类型参数出现，或作为参数化类型中通配符参数的边界出现
- §4.8，用于原始（raw）的类和接口类型
- §4.9，用于类型参数边界中的交集类型
- §6.5，用于泛型不重要的上下文中的类和接口类型（§6.1）
- §10.1，用于数组类型

某些类型上下文限制了引用类型可以参数化的方式：

- 以下类型上下文要求如果类型是参数化引用类型，则它必须具有通配符参数：
  - 在类声明的 `extends` 或 `implements` 子句中（§8.1.4, §8.1.5）
  - 在接口的 `extends` 子句中（§9.1.3）
  - 在类实例创建表达式中，作为要实例化的类型（§15.9），或作为要实例化的匿名类的直接父类或直接父接口（§15.9.5）
  - 在方法引用表达式（§15.13）中，作为查找成员方法的引用类型，或作为要构造的类类型或数组类型。

此外，在显式构造函数调用语句、类实例创建表达式或方法调用表达式的显式类型参数列表中不允许使用通配符参数。

- 以下类型上下文要求如果类型是参数化引用类型，则它具有通配符参数：
  - 数组创建表达式中的元素类型（§15.10.1）
  - `instanceof` 关系运算符后的类型（§15.20.2）

## 4.12 变量

变量是一个存储位置，并关联有一个类型（有时称为其编译类型），该类型可以是基本类型（§4.2）或引用类型（§4.3）。

变量的值通过赋值（§15.26）或前置/后置 `++`（递增）或 `--`（递减）运算符（§15.14.2, §14.14.3, §15.15.1, §15.15.2）来改变。

变量与其类型的兼容性由 Java 语言的设计保证，只要程序没有产生编译时的未检查警告。默认值（§4.12.5）是兼容的，且对变量的所有赋值都会经过赋值兼容性检查（§5.2），通常在编译时进行；但在一个涉及数组的单例情况下，会进行运行时检查（§10.5）。

### 4.12.1 基本类型变量

基本类型的变量始终持有该确切基本类型的原始值。

### 4.12.2 引用类型变量

类类型 $\tau$ 的变量可以持有 `null` 引用，或者指向类 $\tau$ 的实例或任何 $\tau$ 的子类的实例引用。

> 注意，变量不能保证始终指向其声明类型的子类型，而只指向声明类型的子类或子接口。这是由于下文提到的堆污染可能性导致的。

如果 $T$ 是一个引用类型，那么类型为“$T$ 的数组”的变量可以持有 `null` 引用，或者指向任何类型为“$S$ 的数组”的数组，其中类型 $S$ 是类型 $T$ 的子类或子接口。

类型为 `Object[]` 的变量可以持有任何引用类型数组的引用。

类型为 `Object` 的变量可以持有 `null` 引用或指向任何对象的引用，无论它是类的实例还是数组。

泛化类型的变量可能会引用一个不属于该泛化类型的对象。这种现象被称为*堆污染*（heap pollution）。

只有当程序执行了某些涉及原始类型（raw type）的操作且该操作会产生编译时的未检查警告（§4.8, §5.1.6, §5.1.9, §8.4.1, §8.4.3, §8.4.4, §9.4.1.2, §15.12.4.2），或者程序通过超类型的数组变量别名化不可重化的类型数组变量时，才会发生堆污染。

例如，代码：
```



# 类型、值与变量

## 4.12 变量

### 4.12.3 变量的种类

有以下种类：

1. **类变量**：在类声明（§8.3.1）中使用 `static` 关键字声明的字段，或者在接口声明（§9.3）中使用或不使用 `static` 关键字。类变量在类或接口准备（§12.3.2）时创建并初始化为默认值（§14.2.5）。类变量在卸载（§12.7）失效。
2. **实例变量**：在类声明中不使用 `static` 关键字声明的字段（§8.3.1）。如果类 $\tau$ 有一个实例变量字段，那么在创建每个类 $\tau$ 或其任何子类（§8.1.4）的实例时，都会创建并初始化默认值（§14.5）。当所属的对象不再被引用时，在完成必要的最终化（§12.6）后，实例变量失效。
3. **数组组件**：无名变量，每当创建新的数组对象时（§10 (Arrays), §15.10.2），就会创建并初始化默认值（§14.5）。当数组不再被引用时，数组组件失效。
4. **方法参数**（§8.4.1）：命名传递给方法的参数。对于方法声明中的每个参数，每次调用该方法时都会创建一个新参数（§15.12）。新变量由方法调用中的相应参数值进行初始化。当方法体执行完毕后，方法参数实际上不再存在了。
5. **构造方法参数**（§8.8.1）：传递给构造方法的参数值名称。对于构造方法声明中声明的每一个参数，每当类实例表达式（§15.9）或显式构造方法调用（§8.8.7）调用该构造方法时，都会创建一个新的参数变量。该新变量由创建表达式或构造方法调用中的相应参数值进行初始化。当构造方法体执行完毕后，构造方法参数实际上不再存在了。
6. **Lambda 参数**（§15.27.1）：传递给 lambda 表达式体（§15.27.2）的参数值名称。对于 lambda 表达式中声明的每一个参数，每当由该 lambda 实现的方法被调用时（§15.12），都会创建一个新的参数变量。该新变量由方法调用中的相应参数值进行初始化。当 lambda 表达式体执行完毕后，lambda 参数实际上不再存在了。
7. **异常参数**：每当 try 语句的 catch 句（§14.20）捕获到异常时，就会创建一个异常参数。该新变量由与异常相关的实际对象（§11.3, §14.18）进行初始化。当与 catch 句相关的块执行完毕后，异常参数实际上不再存在了。
8. **局部变量**：通过局部变量声明语句（§14.44）声明。每当控制流进入块（§14.2）或 for 语句（§14.14）时，对于立即包含在所述块或 for 语句中的局部变量声明语句中声明的每一个局部变量，都会创建一个新变量。局部变量声明语句可以包含一个初始化该变量的表达式。然而，带有初始化表达式的局部变量在声明它的局部变量声明语句执行之前，是不会被初始化的。（确定赋值规则（§16 (Definite Assignment)）阻止了局部变量的值在被初始化或被赋值其他值之前被使用。）当块或 for 语句执行完毕后，该局部变量实际上不再存在了。如果不是由于一种特殊情况，局部变量可以一直被视为是在其局部变量声明语句执行时被创建的。这种特殊情况涉及 switch 语句（§14.11），在该语句中，控制可能通过跳过局部变量声明语句的执行进入块。然而，由于确定赋值规则（§16 (Definite Assignment)）的限制，由这种被跳过的声明语句所声明的局部变量在被赋值表达式（§15.26）赋值之前不能被使用。

#### 示例 4.12.3. 不同类型的变量

```java
class Point {
    static int numPoints; // numPoints 是类变量
    int x, y; // x 和 y 是实例变量
    int[] w = new int[10]; // w 是数组组件
    int setX(int x) // x 是方法参数
        int oldx = this.x; // oldx 是局部变量
        this.x = x;
        return oldx;
    }
}
```

### 4.12.4 final 变量

变量可以被声明为 `final`。一个 `final` 变量只能被赋值一次。如果对 `final` 变量进行赋值，除非在赋值之前已经确定了该赋值（§16 (Definite Assignment)），否则会导致编译错误。

一旦 `final` 变量被赋值，它将始终包含相同的值。如果 `final` 变量持有对对象的引用，那么对象的状态可以通过对对象的操作来改变，但该变量将始终引用同一个对象。这也适用于数组；因为数组是对象，如果一个 `final` 持有一个数组的引用，那么数组的组件可以通过对数组的操作来改变，但该变量将始终引用同一个数组。

空白 final（blank final）是一个声明中缺少初始化器的 `final` 变量。

常量变量（constant variable）是基本类型的 `final` 变量或 `final String`，并用常量表达式（§15.29）初始化。一个变量是否为常量变量可能对类初始化（§12.4.1）、二进制兼容性（§13.1）、可达性（§14.22）以及确定赋值（§16.1.1）产生影响。

三种类型的变量被隐式声明为 `final`：接口的字段（§9.3）、作为 try-with-resources 语句资源声明的局部变量（§14.20.3），以及多异常 catch 句的异常参数（§14.20）。单异常 catch 句的异常参数永远不会被隐式声明为 `final`，但可以是有效 final（effectively final）。

#### 示例 4.12-4-1. final 变量

将变量声明为 `final` 可以作为有用的文档，说明其值不会改变，并可以帮助避免编程错误。在此程序中：

```java
class Point {
    int x, y;
    int useCount;
    Point(int x, int y) { this.x = x; this.y = y; }
    static final Point origin = new Point(0, 0);
}
```

类声明了一个 `final` 变量 `origin`。`origin` 变量持有坐标为 (0,0) 的 `Point` 对象引用。`origin` 的值不能改变，因为它始终引用同一个对象。

某些未声明为 `final` 的变量反而是有效 final：

- 每个类变量、实例变量或数组组件在创建时都会用默认值初始化（§15.9, §15.10.2）。
- 如果满足所有条件，缺少初始化器的局部变量是有效 final：
  - 它未声明为 `final`。
  - 它从不出现在赋值表达式的左侧（§15.26）。
  - 它从不作为前置递减运算符的操作数。
- 方法、构造方法、lambda 或异常参数（§8.4.1, §8.8.1, §9.4, §15.27.1, §14.20）在判断其是否为有效 final 时，被视为带有初始化器的局部变量。

如果一个变量是有效 final，在其声明中添加 `final` 修饰符不会引入编译错误。相反，声明为 `final` 的局部变量或参数在移除 `final` 修饰符后变为有效 final。

### 4.12.5 变量的初始值

程序中的每个变量在使用之前必须有一个值：

- 每个类变量、实例变量或数组组件在创建时都会用默认值初始化（§15.9）：
  - 对于 `byte` 类型，默认值是零，即 `(byte) 0` 的值。
  - 对于 `short` 类型，默认值是零，即 `(short) 0` 的值。
  - 对于 `int` 类型，默认值是零，即 `0`。
  - 对于 `long` 类型，默认值是零，即 `0L`。
  - 对于 `float` 类型，默认值是正零，即 `0.0f`。
  - 对于 `double` 类型，默认值是正零，即 `0.0d`。
  - 对于 `char` 类型，默认值是空字符，即 `'\u0000'`。
  - 对于 `boolean` 类型，默认值是 `false`。
  - 对于所有引用类型，默认值是 `null`。
- 每个方法参数（§8.4.1）由方法的调用者提供的相应参数值进行初始化。
- 每个构造方法参数（§8.8.1）由类实例创建表达式提供的相应参数值进行初始化。
- 异常参数（§14.20）由代表异常的抛出的对象进行初始化。
- 局部变量（§14.4, §14.14）在使用之前必须通过初始化（§14.4）或赋值（§15.26）显式地赋予值，且这种赋值方式可以使用确定赋值规则（§16 (Definite Assignment)）进行验证。

#### 示例 4.12.5-1. 变量的初始值

```java
class Point {
    static int npoints;
    int x, y;
    Point root;
}

class Test {
    public static void main(String[] args) {
        System.out.println("npoints=" + Point.npoints);
        Point p = new Point();
        System.out.println("p.x=" + p.x + ", p.y=" + p.y);
        System.out.println("p.root=" + p.root);
    }
}
```

该程序输出：

```
npoints=0
p.x=0, p.y=0
p.root=null
```

这说明了 `npoints` 的默认初始化（发生在准备 `Point` 类时（§12.3.2））以及 `x`、`y` 和 `root` 的默认初始化（发生在实例化新的 `Point` 时）。关于类和接口加载、链接和初始化的所有方面的描述，请参见 §12 (Execution)，以及实例化以创建新实例的描述。

### 4.12.6 类型、类与接口

在 Java 编程语言中，每个变量和每个表达式都有一个可以在编译时确定的类型。该类型可以是原始类型或引用类型。引用类型包括类和接口。引用类型通过类型声明引入，包括类声明（§8.1）和接口声明（§9.1）。我们经常使用“类型”一词来指代类或接口。

在 Java 虚拟机中，每个对象都属于某个特定的类：即产生该对象的创建表达式中提到的类（§15.9），或者是用于调用反射方法产生该对象的 `Class` 对象，亦或是通过字符串拼接运算符 `+` 隐式创建的对象的 `String` 类（§15.18.1）。这个类被称为对象的类。一个对象被认为是其类及其所有超类的实例。

每个数组也有一个类。当对数组对象调用 `getClass` 方法时，它将返回一个代表数组类的类对象（类型为 `Class`）（§10.8）。

变量的编译时类型总是被声明的，而表达式的编译时类型可以在编译时推断。编译时类型限制了变量在运行时可能持有的值或表达式在当时可能产生的值。如果运行时值是非空引用，它指向一个具有某个类的对象或数组，并且必然与编译时类型兼容。

尽管变量或表达式的编译时类型可以是接口类型，但接口没有实例。类型为接口类型的变量可以引用任何其类实现了（§8.1.5）该接口的对象。

有时，一个变量或表达式被认为具有“运行时类型”。这指的是运行时变量或表达式的值所指向的对象的类（假设该值不为空）。

编译时类型与运行时类型之间的对应关系是不完全的，原因有二：

1. 在运行时，类和接口是由 Java 虚拟机使用类加载器加载的。每个类加载器都定义了它们自己的一组类和接口。因此，两个加载器可能会加载相同的类或接口定义，但在运行时产生不同的类或接口。结果，如果加载代码的类加载器不一致，编译正确的代码可能会链接失败。
   > 更多细节请参见 Sheng Liang 和 Gilad Bracha 写的《Dynamic Class Loading in the Java Virtual Machine》，收于 OOPSLA 98（ACM SIGPLAN Notices, Volume 33, Number 10, October 1998, pages 36-44），以及《The Java Virtual Machine Specification, Java SE 14》。
2. 类型变量（§4.4）和参数在运行时不会被具体化（reified）。因此，运行时的同一个类或接口代表多个类型。

#### 4.12.6.1 变量的类型对比与对象的类

```java
interface Colorable {
    void setColor(int r, int g);
}

class Colored extends Point implements Colorable {
    int r, g;
    public void setColor(int r, int g) {
        r = r;
        g = g;
    }
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        Colored cp = new Colored();
        p = cp;
        Colorable c = cp;
    }
}
```



在此示例中：

- 局部变量 `p` 的类型为 `Point`，初始被赋值一个 `Point` 的新实例。
- 局部变量 `cp` 同样类型为 `Colored`，初始被赋值一个新实例。
- 将 `cp` 赋值给 `p` 是允许的，因为 `Colored` 是 `Point` 的子类，所以 `Colored` 与 `Point` 赋值兼容。
- 局部变量 `c` 的类型为 `Colorable`，因此它可以持有任何类实现了 `Colorable` 的对象的引用；具体来说，它可以持有 `Colored`。

注意，像 `new Colorable()` 这样的表达式是无效的，因为无法创建接口的实例，只能创建类的。然而，表达式 `new Colorable() { public void setColor... }` 是有效的，因为它声明了一个实现了 `Colorable` 的匿名类 (\$15.9)。

# 第5 章 转换与上下文

Java 编程语言中的每个表达式要么产生结果 (\$15.1)，要么有一个可以在编译时推断的类型 (\$15.3)。当一个表达式出现在大多数上下文中，它必须与环境中期望的类型兼容；该类型被称为目标类型。为了方便，表达式与其周围上下文的兼容性通过两种方式实现：

- 第一，对于某些表达式（称为多态表达式 \$15.2），推断出的类型可以受到目标类型的影响。
- 第二，在表达式类型被推断后，有时可以执行从表达式类型到目标类型的隐式转换。

如果两种策略都无法产生相应的类型，就会发生编译错误。

确定表达式是否为多态表达式以及其在特定上下文中的类型和兼容性的规则取决于上下文的种类和表达式的形式。除了影响表达式的类型，目标类型在某些情况下还会影响表达式的运行时行为，以产生相应的值。

同样，确定目标类型是否允许隐式转换的规则取决于上下文种类、表达式的类型，在一种特殊情况下取决于常量表达式的值 (\$15.29)。从类型 $S$ 到类型 $T$ 的转换允许类型 $S$ 的表达式在编译时被视为类型 $T$。在某些情况下，这需要在运行时执行相应的操作以检查转换的有效性，或将表达式的运行时值转换为适用于新类型 $T$ 的形式。

## 示例 5.0-1. 编译时和运行时转换

- 从 `Object` 类型到 `Thread` 类型的转换需要运行时检查，以确保运行时值确实是 `Thread` 类或其子类的实例；如果不是，则抛出异常。
- 从 `Thread` 类型到 `Object` 类型的转换不需要运行时操作；`Thread` 是 `Object` 的子类，因此 `Thread` 类型表达式产生的引用都是有效的 `Object` 类型引用。
- 从 `int` 类型到 `long` 类型的转换需要将 32 位整数值在运行时符号扩展为 64 位 `long` 表示。没有信息丢失。
- 从 `double` 类型到 `long` 类型的转换需要从 64 位浮点值到 64 位整数表示的非平凡翻译。根据实际运行值，可能会丢失信息。

Java 编程语言中可能的转换分为以下几大类：

- 恒等转换 (Identity conversions)
- 宽化基本类型转换 (Widening primitive conversions)
- 窄化基本类型转换 (Narrowing primitive conversions)
- 宽化引用转换 (Widening reference conversions)
- 窄化引用转换 (Narrowing reference conversions)
- 装箱转换 (Boxing conversions)
- 解箱转换 (Unboxing conversions)
- 未经检查转换 (Unchecked conversions)
- 捕获转换 (Capture conversions)
- 字符串转换 (String conversions)
- 值集转换 (Value set conversions)

存在六种转换上下文，多表达式可能会受到上下文的影响或发生隐式转换。每种上下文对多表达式类型有不同的规则，并允许上述类别中的某些转换，而不允许其他转换。这些上下文是：

- 赋值上下文 (§5.2, §15.26)，其中表达式的值绑定到一个命名变量。基本类型和引用类型会发生宽化，值可能会被装箱或解箱，某些基本常量表达式可能会被窄化。还可能发生未经检查转换。
- 严格调用上下文 (§5.3, §15.9, §15.12)，其中参数绑定到构造函数或方法的形式化参数上。可能会发生宽化基本类型、宽化引用和未经检查转换。
- 松散调用上下文 (§5.3, §15.9, §15.12)，与严格调用上下文一样，参数绑定到形式化参数上。如果仅使用严格调用上下文无法找到适用的声明，方法或构造函数调用可以提供此上下文。除了宽化和未检查版本外，此上下文还允许装箱和解箱转换发生。
- 字符串上下文 (§5.4, §15.18.1)，其中任何类型的值都被转换为 `String` 类型。
- 强制转换上下文 (§5.5)，其中表达式的值转换为强制转换操作符 (§15.16)指定的类型。强制转换上下文比赋值或松散调用上下文更具包含性，允许除字符串转换之外的任何特定转换，但某些引用类型会在运行时检查正确性。
- 数字上下文 (§5.6)，其中数字运算符的操作数或其他处理数字的表达式的操作数可能会被宽化为公共类型。

“转换”一词也用于描述特定上下文中允许的类型，但不具体指明。例如，我们看到局部变量的初始化表达式受限于“赋值转换”，这意味着根据赋值上下文的规则，将为该表达式隐式地选择一种特定的转换。

## 示例 5.0-2. 各种上下文中的转换

```java
class Test {

    public static void main(String[] args) {

        // 浮点字面量到 int 的强制转换转换 (5.4)。

        // 没有强制转换操作符，这将是一个

        // 编译错误，因为这是一个窄化转换 (5.1.3):

        int i = (int)12.5f;

        // i 的 int 值的字符串转换 (5.4):

        System.out.println("*int)12.5f=" + i);

        // i 的值到 float 类型的赋值转换 (5.2):

        // 这是一个宽化转换 (5.1.2):

        float f = i;

        // f 的 float 值的字符串转换:

        System.out.println("after float widening: " + f);

        // f 的 float 值的数字提升 (5.6):

    }

}
```

## 5.1 转换的类型

1. 在第一步中，浮点数被转换为 `long`（如果 $\tau$ 是 `long`）或转换为 `int`（如果 $\tau$ 是 `byte`、`short`、`char` 或 `int`），如下文所示：

   - 如果浮点数是 NaN (§4.2.3)，则转换的第一步的结果为 `int` 或 `long` 类型的 0。
   - 否则，如果浮点数不是无穷大，则将浮点值四舍入为整数值 $v$，使用 IEEE 754 舍入零模式 (§4.2.3)。这有两种情况：
     a. 如果 $\tau$ 是 `long`，且该整数值可以被表示为 `long`，那么第一步的结果为值 $v$。
     b. 否则，如果该整数值可以被表示为 `int`，那么第一步的结果为 `int` 类型的值 $v$。
   - 否则，以下两种情况中必须有一个为真：
     a. 该值可能太小（大值的负值或负无穷大），且第一步的结果为 `int` 或 `long` 类型最小的可表示值。
     b. 该值可能太大（大值的正值或正无穷大），且第一步的结果为 `int` 或 `long` 类型最大的可表示值。

2. 在第二步中：

   - 如果 $\tau$ 是 `int` 或 `long`，转换的结果为第一步的结果。
   - 如果 $\tau$ 是 `byte`、`char` 或 `short`，转换的结果为向类型 $\tau$ 窄化转换 (§5.1.3) 的结果或第一步的结果。

尽管可能会发生溢出、下溢或其他信息丢失，但窄化转换不会导致运行时异常 (§11.1.1)。

> 示例 5.1.3-1. 窄化原始类型转换

```java
class Test {

  public static void main(String[] args) {

    float fmin = Float.NEGATIVE_INFINITY;

    float fmax = Float.POSITIVE_INFINITY;

    System.out.println("long: " + (long) fmin + "..." + (long) fmax);

    System.out.println("int: " + (int) fmin + "..." + (int) fmax);

    System.out.println("short: " + (short) fmin + "..." + (short) fmax);

    System.out.println("char: " + (int) (char) fmin + "..." + (int) (char) fmax);

  }

}
```

```java
System.out.println("byte: " + (byte) fmin + "..." + (byte) fmax);
```

该程序产生输出：

```
long: -922337203685477808..922337203685477807
int: -2147483648..2147483647
short: 0..1
char: 0..65535
byte: 0..1
```

`char`、`int` 和 `long` 的结果令人惊讶，它们产生了类型的最小和最大表示值。

`byte` 和 `short` 的结果丢失了关于数值大小和范围的信息，并且丢失了精度。可以通过检查 `int` 最小和最大值的低位来理解这些结果。最小 `int` 的十六进制是 `0x80000000`，最大 `int` 是 `0x7fffffff`。这解释了 `short` 的结果（这些值的 16 位），也解释了 `char` 的结果（也是这些值的 16 位，即 `'\u0000'` 和 `'\ffff'`）；它解释了 `byte` 的结果（这些值的 8 位，即 `0x00` 和 `0xff`）。

## 示例 5.1.3-2. 丢失信息的窄化原始类型转换

```java
class Test {

    public static void main(String[] args) {

        // int 到 short 的窄化丢失了高位：

        System.out.println("short:0x12345678=" + Integer.toHexString((short)0x12345678));

        // 对于 byte 来说太大的 int 值改变了符号和数值：

        System.out.println("byte:255=" + (byte)255);

        // 对于 int 来说太大的 float 值无法放入，产生最大的 int：

        System.out.println("int:20f=" + (int)20f);

        // NaN 转换为 int 产生零：

        System.out.println("int:NaN=" + (int)Float.NaN);

        // 对于 float 来说太大的 double 值产生无穷大：

        System.out.println("float:100=" + (float)100);

        // 对于 float 来说太小的 double 值下溢为零：

        System.out.println("float:-50=" + (float)-50);

    }

}
```

该程序产生输出：

```
short:0x12345678=5678
byte:255=-1
int:20f=2147483647
int:NaN=0
float:100=Infinity
float:-50=0.0
```



## 5.1.4 宽化和窄化原始类型转换

以下转换结合了宽化和窄化原始类型转换：

- `byte` 到 `char`

首先，通过宽化转换 (§5.1.2) 将 `byte` 转换为 `int`，然后将得到的 `int` 通过窄化转换 (§5.1.3) 转换为 `char`。

## 5.1.5 宽化引用转换

从任何引用类型 $s$ 到任何引用类型 $t$ 都存在宽化引用转换，只要 $s$ 是 $t$ 的子类型 (§4.10)。宽引用在运行时永远不需要特殊操作，因此永远不会抛出异常。

> **注意**：`null` 类型不是引用类型 (§4.1)，因此不存在从 `null` 类型到引用类型的宽化转换。然而，许多转换允许将 `null` 类型转换为引用类型。

## 5.1.6 窄化引用转换

窄化引用转换将引用类型 $s$ 的表达式视为不同类型 $t$ 的表达式，其中 $s$ 不是 $t$ 的子类型。

## 5.1.6.1 受检与未受检窄化引用转换

如果不是未受检的，则它是受检的；Java 虚拟机能够完全验证其正确性，因此在编译时不会给出警告。

未受检的引用转换如下：

- 从类型 $s$ 到参数化类类型或接口类型 $\tau$ 的收缩引用转换是未受检的，除非至少满足以下条件之一：
    - $\tau$ 的所有类型参数、$S$ 和 $s$ 除 $\tau$ 之外没有其他子类型，其中类型参数 $x$ 的类型参数未包含在 $T$ 的类型参数中。
    - $T <$；$s$ 除 $T$ 之外没有其他子类型 $x$，其中类型参数。
- 从类型 $s$ 到类型变量 $\tau$ 的收缩引用转换是未受检的。
- 从类型 $s$ 到交集类型 $T_1 \& ... \& T_n$ 的收缩引用转换是未受检的，如果存在 $(1 \le i \le n)$ 使得 $s$ 不是 $T_i$ 的子类型，且从 $s$ 到 $T_i$ 的收缩引用转换是未受检的。

### 5.1.6.2 运行时窄化引用转换

所有受检的收缩引用转换都需要运行时进行有效性检查。

某些未受检的收缩引用转换需要在运行时进行有效性检查。这取决于该未受检的收缩引用转换是完全未受检还是部分未受检。部分未受检的收缩引用转换需要在运行时进行有效性检查，而完全未受检的收缩引用转换则不需要。

> 这些术语指的是将类型视为原始类型时的兼容性。如果转换在概念上是“向上转型”，则该转换是完全未受检的；不需要运行时测试，因为该转换在 Java 虚拟机的非泛型类型中是合法的。相反，如果转换在概念上是“向下转型”，则该转换是部分未受检的；即使在 Java 虚拟机的非泛型类型中，也需要运行时测试来测试转换涉及的（原始）类型的兼容性。

以 `java.util` 包的类型为例，从 `ArrayList<String>` 到 `Collection<?>` 的转换是完全未受检的，因为在 Java 虚拟机中，原始类型 `ArrayList` 是原始类型 `Collection` 的子类型。相反，从 `Collection<?>` 到 `ArrayList<String>` 的转换是部分未受检的，因为在 Java 虚拟机中，原始类型 `Collection` 不是原始类型 `ArrayList` 的子类型。

未受检收缩引用转换的分类如下：

- 从 $s$ 到非交集类型 $T$ 的未受检收缩引用转换，如果 $|s| < |T|$，则它是完全未受检的。否则，它是部分未受检的。
- 从 $s$ 到交集类型 $T_1 \& ... \& T_n$ 的未受检收缩引用转换，对于所有 $i$ ($1 \le i \le n$)，要么 $s <: T_i$ 或者从 $s$ 到 $T_i$ 的收缩引用转换是完全未受检的，则它是完全未受检的。否则，它是部分未受检的。

已检查或部分未受检的收缩引用转换的运行时有效性检查如下：

- 如果运行时值为 `null`，则允许该转换。
- 否则，令 $R$ 为该值所引对象的类，令 $T$ 为转换后类型的擦除类型（§4.6）：那么：
    - 如果 $R$ 是普通类（不是数组类）：
        - 如果 $T$ 是类类型，则 $R$ 必须是与 $T$ 相同的类（§4.3.4）或 $T$ 的子类，否则抛出 `ClassCastException`。
        - 如果 $T$ 是接口类型，则 $R$ 必须实现接口 $T$ (§8.1.5)，否则抛出 `ClassCastException`。

## 5.1.7 装箱转换

在运行时，装箱转换如下：

- `boolean` 类型的 $p$ 转换为 `Boolean` 引用，`booleanValue() = p`。
- `byte` 类型的 $p$ 转换为 `Byte` 引用，`byteValue() = p`。
- `char` 类型的 $p$ 转换为 `Character` 引用，`charValue() = p`。
- `short` 类型的 $p$ 转换为 `Short` 引用，`shortValue() = p`。
- `int` 类型的 $p$ 转换为 `Integer` 引用，`intValue() = p`。
- `long` 类型的 $p$ 转换为 `Long` 引用，`longValue() = p`。
- `float` 类型的 $p$ 转换为 `Float` 引用，`floatValue() = p`。
- `double` 类型的 $p$ 转换为 `Double` 引用，`doubleValue() = p`。

如果被装箱的值 $p$ 是常量表达式（§15.29）类型的 `boolean`、`char`、`short`、`int`、`long` 且结果为 `true`、`false`、范围在 `\u0000` 到 `\u007f` 之间的字符或范围在 -128 到 127 之间的整数，则 $a$ 和 $b$ 为 $p$ 的任意两个装箱转换的结果，总是 $a == b$。

理想情况下，装箱会产生相同的引用。在实践中，使用现有的实现技术可能不可行。上述规则是一种务实的折中，要求常见值也被装箱为不可区分的对象。实现可以延迟地或激进地缓存这些引用。对于其他值，该规则允许（但不要求）共享这些引用。

这确保了在大多数情况下，行为将是预期的，而不会产生不必要的性能损失，特别是在小型设备上。内存受限的实现可能会缓存 `char` 和 `short` 值，以及范围在 -32K 到 +32K 之间的 `int` 和 `long` 值。

如果需要分配一个包装类（`Boolean`、`Byte`、`Character`、`Short`、`Integer`、`Long`、`Float` 或 `Double`）的新实例且可用存储不足，装箱转换可能会导致 `OutOfMemoryError`。

## 5.1.8 解箱转换

解箱转换将引用类型的表达式视为相应原始类型的表达式。具体而言，以下八种转换被称为解箱转换：

- 从 `Boolean` 类型到 `boolean` 类型
- 从 `Byte` 类型到 `byte` 类型
- 从 `Short` 类型到 `short` 类型
- 从 `Character` 类型到 `char` 类型
- 从 `Integer` 类型到 `int` 类型
- 从 `Long` 类型到 `long` 类型
- 从 `Float` 类型到 `float` 类型
- 从 `Double` 类型到 `double` 类型

在运行时，拆箱转换按以下方式进行：

- 如果 $r$ 是 `Boolean` 类型的引用，拆箱转换将 $r$ 转换为 `r.booleanValue()`
- 如果 $r$ 是 `Byte` 类型的引用，拆箱转换将 $r$ 转换为 `r.byteValue()`
- 如果 $r$ 是 `Character` 类型的引用，拆箱转换将 $r$ 转换为 `r.charValue()`
- 如果 $r$ 是 `Short` 类型的引用，拆箱转换将 $r$ 转换为 `r.shortValue()`
- 如果 $r$ 是 `Integer` 类型的引用，拆箱转换将 $r$ 转换为 `r.intValue()`
- 如果 $r$ 是 `Long` 类型的引用，则拆箱转换将 $r$ 转换为 `r.longValue()`
- 如果 $r$ 是 `Float` 类型的引用，拆箱转换将 $r$ 转换为 `r.floatValue()`
- 如果 $r$ 是 `Double` 类型的引用，拆箱转换将 $r$ 转换为 `r.doubleValue()`
- 如果 $r$ 为 `null`，拆箱转换将抛出 `NullPointerException`

如果一个类型是数值类型 (§4.2)，或者它是可以通过拆箱转换转换为数值类型的引用类型，则认为该类型是可转换为数值类型的。

如果一个类型是整型类型，或者它是可以通过拆箱转换转换为整型类型的引用类型，则认为该类型是可转换为整型类型的。

## 5.1.9 未受检转换

假设 $G$ 是一个具有 $n$ 个类型参数的泛型类型声明。

从原始类或接口类型 (§4.8) $G$ 到任何形式为 $G<T_1...T_n>$ 的参数化类型之间存在未受检的转换。

从原始数组类型 $G[]^k$ 到任何形式为 $G<T_1,...,T_n>[]^k$ 的数组类型之间存在未受检的转换。（符号 `[]^k` 表示 $k$ 维的数组类型。）

除非所有类型参数 $T_i$ ($1 \leq i \leq n$) 都是无界通配符 (§4.5.1) 或者警告被 `@SuppressWarnings` (§9.6.4) 抑制，否则使用未受检的转换会导致编译未受检警告。

未受检的转换用于使泛型引入之前编写的旧代码能够更平畅地运行，以具有通用性（我们称这一过程为泛型化）。在这种情况下（最典型的 `java.util` 中 Collections Framework 的客户端），代码使用了原始类型（例如，用 `Collection` 代替 `Collection<String>`）。原始类型的表达式被传递给库方法，这些方法使用相同类型的参数化版本作为其对应形式参数的类型。

在使用泛型的系统中，无法证明此类调用在静态上是安全的。拒绝此类调用将导致大量现有代码失效，并阻止它们使用较新版本的库。反过来，这会抑制库供应商利用通用性。为了防止这种不受欢迎的事态发生，原始类型可以转换为其所指代的泛型类型声明的任意调用。虽然这种转换是不安全的，但出于实用考虑的妥协，它是被容忍的。

## 5.1.10 捕获转换

假设 $G$ 是一个具有 $n$ 个类型参数 $A_1,...,A_n$ 及其对应边界 $U_1,...,U_n$ 的泛型类型声明 (§8.1.2, §9.1.2)。

从参数化类型 $G<T_1,...,T_n>$ (§4.5) 到参数化类型 $G<S_1,...,S_n>$ 存在捕获转换，其中对于 $1 \leq i \leq n$：

- 如果 $T_i$ 是形式为 `?` 的通配符类型参数 (§4.5.1)，则 $S_i$ 是一个新变量，其上界为 $U_i$。
- 如果 $T_i$ 是形式为 `? extends B_i` 的通配符类型参数，则 $S_i$ 是一个新变量，其上界为 $U_i$。
- 如果 $T_i$ 是形式为 `? super B_i` 的通配符类型参数，则 $S_i$ 是一个新变量，其下界为 $U_i$。
- 否则，$S_i = T_i$。

捕获转换是为了使通配符变得有用。为了理解这种动机，让我们先看 `java.util` 中的方法：

```java
public static void reverse(List<?>);
```

从 `reverse()` 到 `rev()` 的调用实际上是安全的，因为输入参数是某种类型（尽管是未知的）。如果我们能将这种未知类型捕获到一个类型变量 $x$，就可以推断出 $T$ 为 $x$。这就是捕获转换的本质。

数学上程度深的读者需要将捕获转换与类型理论联系起来。不熟悉类型理论的读者可以跳过此讨论——或者学习合适的书籍，如 Benjamin Pierce 写的《类型与编程语言》，然后返回本节。

这里是捕获转换与现有概念关系的简要总结。通配符类型是存在类型的限制形式。捕获转换大致地作用于存在类型的开启。对表达式 $e$ 的捕获转换可以看作是在包含 $e$ 的作用域对 $e$ 进行开启。经典的开启操作要求捕获的类型变量不能逃逸表达式。对应捕获转换的开启总是在足够大的作用域内，使得捕获的类型变量在该作用域外可见。这种方案的优势是不需要关闭操作（在论文《Variance-Based Subtyping for Parametric Types》中定义）。

捕获转换不是递归的。捕获转换对于参数化类型以外的任何类型 (§4.5) 在运行时都不会抛出异常。关于通配符的正式说明，见 Mads Torgersen, Erik Ernst 和 Christian Plesner Hansen 的《Wild Fj》，发表于第12届对象基础工作坊 (POOL 2005)。

```java
List<String> ls = new ArrayList<>();

List<?> l = ls;

Collections.fill(l, new Object()); // 非法——假设它是合法的
```



# 转换与上下文

## 5.1.11 字符串转换

任何类型都可以通过字符串转换为 `String` 类型。

```java
String s = ls.get(0); // ClassCastException - ls 包含了 Objects.
```

这种做法是不可取的，因为它向调用者暴露了实现信息。API 设计者可能会意识到使用通配符的签名是调用者所要求的，并且之后发现类型安全的实现是不可能的。如果是这种情况，`reverse()` 的作者将被迫写出其签名：

```java
public static <T> void reverse(List<T>)
```

## 转换种类

### 5.1

基本类型 `T` 的值 `x` 首先被转换为引用值，其如同将其作为适当的类实例创建表达式 (§15.9) 的参数：

- 如果 `T` 是 `boolean`，则使用 `new Boolean(x)`。
- 如果 `T` 是 `char`，则使用 `new Character(x)`。
- 如果 `T` 是 `byte`、`short` 或 `int`，则使用 `new Integer(x)`。
- 如果 `T` 是 `long`，则使用 `new Long(x)`。
- 如果 `T` 是 `float`，则使用 `new Float(x)`。
- 如果 `T` 是 `double`，则使用 `new Double(x)`。

随后，该引用值通过字符串转换转换为 `String` 类型。
现在只需要考虑引用值了：

- 如果该引用为 `null`，则将其转换为字符串 `"null"`（由四个 ASCII 字符 n, u, l, l 组成）。
- 否则，转换的执行方式如同调用了被引用对象的无参 `toString` 方法；但如果 `toString` 方法的结果为 `null`，则改用字符串 `"null"`。

> `toString` 方法由原始类 `Object` 定义 (§4.3.2)。许多类重写了它，特别是 `Boolean`、`Character`、`Integer`、`Long`、`Float`、`Double` 和 `String`。

### 5.1.12 禁止转换

任何未明确允许的转换都是禁止的。

### 5.1.13 值集转换

*值集转换*（value set conversion）是将浮点值从一个值映射到另一个值而不改变其类型的过程。
在非 FP-strict (§15.4) 表达式内部，值集转换为 Java 语言的实现提供了选择：

- 如果该值是 float 扩展指数（float-extended-exponent）值集中的元素，则实现可以根据自己的选择将该值映射到 float 值集中最近的元素。这种转换可能导致溢出（在这种情况下，该值被相同符号的无穷大替换）或下溢（在这种情况下，该值被相同符号的规格数或零替换）。
- 如果该值是 double 扩展指数（double-extended-exponent）值集中的元素，则实现可以根据自己的选择将该值映射到 double 值集中最近的元素。这种转换可能导致溢出（在这种情况下，该值被相同符号的无穷大替换）或下溢（在这种情况下，由于被相同符号的规格数或零替换，可能会丢失精度）。

在 FP-strict (§15.4) 表达式内部，值集转换不提供任何选择；每个实现必须以相同的方式运行：

- 如果该值是 `float` 类型且不是 float 值集中的元素，则实现必须将该值映射到 float 值集中最近的元素。这种转换可能导致溢出或下溢。
- 如果该值是 `double` 类型且不是 double 值集中的元素，则实现必须将该值映射到 double 值集中最近的元素。这种转换可能导致溢出或下溢。

在 FP-strict 表达式内部，从 float 扩展指数值集或 double 扩展指数值集映射值，只有当调用的方法声明不是 FP-strict 且实现选择将方法调用的结果表示为扩展指数值集中的元素时，才是必要的。

无论是在 FP-strict 代码中还是非 FP-strict 代码中，值集转换都不会改变任何既不是 `float` 也不是 `double` 类型的值。

## 5.2 赋值上下文

赋值上下文允许将表达式的值赋值给变量 (§15.26)；表达式的类型必须转换为变量的类型。

赋值上下文允许使用以下之一：

- 恒等转换（identity conversion）§5.1.1
- 宽化基本类型转换（widening primitive conversion）§5.1.2
- 宽化引用转换（widening reference conversion）§5.1.5
- 宽化引用转换后跟接解箱转换（unboxing conversion）
- 宽化引用转换后跟接解箱转换，再跟接宽化基本类型转换
- 装箱转换（boxing conversion）§5.1.7
- 装箱转换后跟接宽化引用转换
- 解箱转换（unboxing conversion）§5.1.8
- 解箱转换后跟接宽化基本类型转换

如果在应用了上述转换后，结果类型是原始类型（raw type）§4.8，则可以应用未检查转换（unchecked conversion）§5.1.9。

此外，如果表达式是 `byte`、`short`、`char` 或 `int` 类型的常量表达式 (§15.29)：

- 如果变量类型为 `byte`、`short` 或 `char`，且常量表达式的值在变量类型中可表示的，则可以使用窄化基本类型转换。
- 如果变量类型为 `Byte`、`Short` 或 `Character`，且常量表达式的值分别在 `byte`、`short` 或 `char` 类型中是可以表示的，则可以使用窄化基本类型转换后跟接装箱转换。

常量表达式的编译时收缩意味着如下代码：

```java
byteAnswer = 42;
```

是被允许的。如果没有收缩，整数字面量 42 类型为 `int` 的事实将意味着需要强制转换为 `byte`：

```java
byteAnswer = (byte)42; // 允许强制转换但不是必须
```

最后，`null` 类型的值（`null` 引用是唯一的此类值）可以赋值给任何引用类型，导致该类型的 `null` 引用。

如果转换链包含两个没有子类型关系 (§4.10) 的泛型类型，则为编译时错误。

此类非法链的示例为：

`Integer, Comparable<Integer>, Comparable, Comparable<String>`

链的前三个元素通过宽化引用转换关联，而最后一项是通过未检查转换从其前驱项派出的。然而，这不是一个有效的赋值转换，因为链中包含了泛型类型 `Comparable<Integer>` 和 `Comparable<String>`，它们并不是子类型。

如果一个表达式的类型可以通过赋值转换转换为变量的类型，我们称该表达式（或其值）是可以赋值给该变量的，或者等价地，表达式的类型与变量的类型赋值兼容。

如果变量类型是 `float` 或 `double`，则对转换结果的值 `v` 应用值集转换 (§5.1.13)：

- 如果 `v` 是 `float` 类型且是 float 扩展指数值集中的元素，则实现必须将 `v` 映射到 float 值集中最近的元素。这种转换可能导致溢出或下溢。
- 如果 `v` 是 `double` 类型且是 double 扩展指数值集中的元素，则实现必须将 `v` 映射到 double 值集中最近的元素。这种转换可能导致溢出或下溢。

在赋值上下文中转换可能产生的唯一异常是：

- `ClassCastException`，如果应用了上述转换后，结果值是一个不是变量类型擦除 (§4.6) 的子类或子接口的实例。

> 这种情况只能由于堆污染（heap pollution）§4.12.2 而产生。在实践中，只有在访问泛型类型对象的字段或方法时，当字段的擦除类型或方法的擦除返回类型与其擦除类型不同时，实现才需要执行强制转换。

- 装箱转换导致的内存溢出异常（`OutOfMemoryError`）。
- 解箱 `null` 引用导致的空指针异常（`NullPointerException`）。
- 涉及数组元素和字段访问的特殊情况下的数组存储异常（`ArrayStoreException`）§10.5, §15.26。

### 示例 5.2-1. 基本类型的赋值

```java
f = 12.0;
l1 = 0x123;
d = 1.2300000190734863;
```

然而，以下程序会产生编译错误：

```java
class Test {
    public static void main(String[] args) {
        short s = 123;
        char c = s;      // 错误：需要强制转换
        s = c;           // 错误：需要强制转换
    }
}
```

因为并不是所有的 `short` 值都是 `char` 值，`char` 值同样不是 `short` 值。

### 示例 5.2-2. 引用类型的赋值

```java
class Point { int x, y; }
class Point3D extends Point { int z; }
interface Colorable { void setColor(int color); }
```

```java
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}
```

```java
class Test {
    public static void main(String[] args) {
        // 对类类型变量赋值：
        Point p = new Point();
        p = new Point3D(); // OK，因为 Point3D 是 Point 的子类
        Point3D p3d = p; // 错误：需要强制转换，因为 Point 可能不是 Point3D（尽管在这个例子中，动态它是）。

        // 对 Object 类型变量赋值：
        Object o = p; // OK：任何对象都可以赋值给 Object
        int[] a = new int[3];
        Object o2 = a; // OK：数组赋值给 Object

        // 对接口类型变量赋值：
        ColoredPoint cp = new ColoredPoint();
        Colorable c = cp; // OK：ColoredPoint 实现了 Colorable

        // 对数组类型变量赋值：
        byte[] b = new byte[4];
        a = b; // 错误：这些不是相同基本类型的类型的数组
    }
}
```

```java
Point3D[] p3da = new Point3D[3];
Point[] pa = p3da; // OK：因为我们可以将 Point3D 赋值给 Point
p3da = pa; // 错误：（需要强制转换），因为 Point 不能赋值给 Point3D
```

接下来的测试程序说明了引用值的赋值转换，但由于其注释中的错误，它无法通过编译。此示例应与之前的代码对比：

```java
class Point { int x, y; }
interface Colorable { void setColor(int color); }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        ColoredPoint cp = new ColoredPoint();
        // 因为 ColoredPoint 是 Point 的子类：
        p = cp;
        // 因为 ColoredPoint 实现了 Colorable：
        Colorable c = cp;
        // 以下操作会导致编译错误，因为
        // 我们无法确定它们是否成功，取决于
        // p 的运行时类型；对于所需的收缩转换，
        // 必须进行运行时检查，并且必须
        // 通过包含强制转换来指示：
        cp = p; // p 可能既不是 ColoredPoint 也不是 ColoredPoint 的子类
        c = p;  // p 可能没有实现 Colorable
    }
}
```

### 示例 5.2-3. 数组类型的赋值

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }
```

```java
class Test {
    public static void main(String[] args) {
        long[] vecl = new long[100];
        Object o = vecl; // OK
        long l1 = vecl[0]; // OK
        short[] vshort = vecl; // 编译错误
        Point[] pvec = new Point[100];
        ColoredPoint[] cpvec = new ColoredPoint[100];
        pvec = cpvec; // OK
        pvec[0] = new Point(); // 编译时通过，但运行时可能抛出异常
        cpvec = pvec; // 编译时错误
    }
}
```

在此示例中：

- `vecl` 的值可以赋值给 `Object` 变量，因为数组可以赋值给兼容的数组类型，或者 `Object`、`Cloneable` 或 `Serializable` 类型的变量。但不能赋值给 `Long` 变量，因为 `Long` 是类类型。
- `vecl[0]` 的值（`long` 类型）无法赋值给 `vshort`，因为它们是基本类型数组，且 `short` 和 `long` 不是相同类型。
- `cpvec` 的值可以赋值给 `pvec`，因为任何类型为 `ColoredPoint` 的表达式值都可以作为 `Point` 类型变量的值。随后对 `pvec` 组件的 `new Point` 赋值将抛出 `ArrayStoreException`（如果程序经过其他修正可以编译的话），因为 `ColoredPoint` 数组不能拥有 `Point` 实例作为组件值。
- `Point` 类型的值无法赋值给 `cpvec`，因为并不是所有作为 `Point` 类型变量值的引用都能正确地作为 `ColoredPoint` 类型变量的值。如果运行时值是 `Point[]` 实例的引用，对 `cpvec[0]` 的赋值可能会返回 `Point`，而 `Point` 并不是 `ColoredPoint`。因此，允许此类赋值将违反类型系统。可以使用强制转换（§5.5, §5.16）来确保 `pvec` 引用的是 `ColoredPoint[]`：

```java
cpvec = (ColoredPoint[])pvec; // OK，但运行时可能抛出异常
```

## 5.3 调用上下文

调用上下文允许将表达式的值作为参数传递给方法或构造函数。表达式的类型必须转换为参数的类型。调用上下文允许的转换与赋值上下文相同，但不允许使用窄化基本类型转换（无论是否为常量表达式）。



# 5.3 调用上下文

调用上下文允许方法或构造函数调用（§8.8.7.1, §15.9, §15.12）中的参数值赋值给相应的形式参数。

严格调用上下文允许使用：

- 恒等转换（§5.1.1）
- 宽基本类型转换（§5.1.2）
- 引用转换（§5.3）

宽松调用上下文允许更宽泛的转换：

- 恒等转换（§5.1.1）
- 宽基本类型转换（§5.1.2）
- 引用转换（§5.3）
- 引用转换（§5.5）
- 引用转换（§5.6）
- 装箱转换（§5.7）
- 装箱转换（§5.8）
- 装箱转换（§5.11）

## 5.4 字符串上下文

- 装箱转换导致 `OutOfMemoryError`。
- 在空引用上进行拆箱转换导致 `NullPointerException`。

## 5.5 强制转换上下文

- 恒等转换 (§5.1.1)
- 拓宽原始类型转换 (§5.1.2)
- 收窄原始类型转换 (§5.1.3)
- 拓宽和收窄原始类型转换 (§5.1.4)
- 装箱转换 (§5.1.7)
- 装箱转换后接拓宽引用转换 (§5.1.5)

如果表达式是引用类型，则强制转换上下文允许使用以下一种：

- 恒等转换 (§5.1.1)
- 拓宽引用转换 (§5.1.5)
- 拓宽引用转换后接拆箱转换
- 拓宽引用转换后接拆箱转换，再接拓宽原始类型转换
- 收窄引用转换 (§5.1.6)
- 收窄引用转换后接拆箱转换
- 拆箱转换 (§5.1.8)
- 拆箱转换后接拓宽原始类型转换

如果表达式具有空类型（null type），则该表达式可以被转换为任何引用类型。

如果强制转换上下文使用了经过检查或部分未检查的收窄引用转换 (§5.1.6, §5.1.3)，则会对表达式值的类进行运行时检查，可能会导致 `ClassCastException`。否则，不进行运行时检查。

值集 (§5.1.13) 在类型转换后应用。

下表列出了在某些强制转换上下文使用的转换。每种转换都由一个符号表示：

- `-` 表示不允许转换
- `≈` 表示恒等转换 (§5.1.1)
- `ω` 表示拓宽原始类型转换 (§5.1.2)
- `η` 表示收窄原始类型转换 (§5.1.3)
- `¤` 表示拓宽和收窄原始类型转换 (§5.1.4)
- `⇑` 表示拓宽引用转换 (§5.1.5)
- `⇓` 表示收窄引用转换 (§5.1.6)
- `⊕` 表示装箱转换 (§5.1.7)
- `⊗` 表示拆箱转换 (§5.1.8)

在表格中，符号之间的逗号表示强制转换上下文使用一种转换后接另一种转换。类型 `Object` 指除其他八个包装类（`Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double`）之外的任何引用类型。

## 表 5.5-A. 转换为原始类型

| 到 → | byte | short | char | int | long | float | double | boolean |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 从 ↓ | | | | | | | | |
| byte | = | ω | ωη | ω | ω | ω | ω | - |
| short | η | = | η | ω | ω | ω | ω | - |
| char | η | η | = | ω | ω | ω | ω | - |
| int | η | η | η | = | ω | ω | ω | - |
| long | η | η | η | η | = | ω | ω | - |
| float | η | η | η | η | η | = | ω | - |
| double | η | η | η | η | η | η | = | - |
| boolean | - | - | - | - | - | - | - | = |
| Byte | ⊗ | ⊗,ω | - | ⊗,ω | ⊗,ω | ⊗,ω | ⊗,ω | - |
| Short | - | ⊗ | - | ⊗,ω | ⊗,ω | ⊗,ω | ⊗,ω | - |
| Character | - | - | ⊗ | ⊗,ω | ⊗,ω | ⊗,ω | ⊗,ω | - |
| Integer | - | - | - | ⊗ | ⊗,ω | ⊗,ω | ⊗,ω | - |
| Long | - | - | - | - | ⊗ | ⊗,ω | ⊗,ω | - |
| Float | - | - | - | - | - | ⊗ | ⊗,ω | - |
| Double | - | - | - | - | - | - | ⊗ | - |
| Boolean | - | - | - | - | - | - | - | ⊗ |
| Object | ↓,ω | ↓,ω | ↓,ω | ↓,ω | ↓,ω | ↓,ω | ↓,ω | ↓,ω |

## 表 5.5-B. 转换为引用类型

| 到 → | Byte | Short | Character | Long | Float | Double | Boolean | Object |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 从 ↓ | | | | | | | | |
| byte | ⊕ | - | - | - | - | - | - | ↑ |
| short | - | ⊕ | - | - | - | - | - | ↑ |
| char | - | - | ⊕ | - | - | - | - | ↑ |
| int | - | - | - | ⊕ | - | - | - | ↑ |
| long | - | - | - | - | ⊕ | - | - | ↑ |
| float | - | - | - | - | - | ⊕ | - | ↑ |
| double | - | - | - | - | - | - | ⊕ | ↑ |
| boolean | - | - | - | - | - | - | - | ⊕ |
| Byte | = | - | - | - | - | - | - | ↑ |
| Short | - | = | - | - | - | - | - | ↑ |
| Character | - | - | = | - | - | - | - | ↑ |
| Integer | - | - | - | = | - | - | - | ↑ |
| Long | - | - | - | - | = | - | - | ↑ |

### 示例 5.5-1. 引用类型的强制转换

```java
class Point { int x, y; }

interface Colorable { void setColor(int color); }

class ColoredPoint extends Point implements Colorable {
    int color;

    public void setColor(int color) { this.color = color; }
}

final class EndPoint extends Point {}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        ColoredPoint cp = new ColoredPoint();
        Colorable c;

        // 以下内容可能在运行时引起错误，
        // 因为我们无法确定它们是否成功；这种可能性通过转换暗示：
        cp = (ColoredPoint)p; // p 可能不是 Point 的子类
        c = (Colorable)p; // p 可能不是 Colorable

        // 以下内容在编译时是错误的，
        // 正如文所示，它们永远不会成功：转换
        Long l = (Long)p; // 编译错误1
        EndPoint e = new EndPoint();
        c = (Colorable)e; // 编译错误2
    }
}
```

在这里，第一个编译错误是因为 `Long` 和 `Point` 类无关（即它们不相同，也不是对方的子类），因此它们之间的转换总是失败。

第二个编译错误是因为实现了 `Colorable` 的 `EndPoint` 类型变量。这是因为 `EndPoint` 是一个 final 类型，而 final 类型变量的运行时类型总是与其编译类型相同。因此，变量 `e` 的运行时类型必须是 `EndPoint`，而 `EndPoint` 没有实现 `Colorable`。

### 示例 5.5-2. 数组类型的强制转换

```java
class Point { int x; }
```

该程序无错误通过编译并产生输出：

```
cpa: { (2,2)@12, (4,5)@24, null, null }
```

### 示例 5.5-3. 运行时不兼容类型的强制转换

```java
class Point { int x, y; }

interface Colorable { void setColor(int color); }

class ColoredPoint extends Point implements Colorable {
    int color;

    public void setColor(int color) { this.color = color; }
}

class Test {
    public static void main(String[] args) {
        Point[] pa = new Point[100];

        // 以下行将抛出 ClassCastException:
        ColoredPoint[] cpa = (ColoredPoint[])pa;
        System.out.println(cpa[0]);

        int[] shortvec = new int[2];
        Object o = shortvec;

        // 以下行将抛出 ClassCastException:
        Colorable c = (Colorable)o;
        c.setColor(0);
    }
}
```

该程序使用强制转换通过编译，但在运行时会抛出异常，因为类型是不兼容的。

## 5.6 数值上下文

数值上下文应用于算术运算符的操作数、数组的创建和访问表达式、条件表达式以及 switch 表达式的结果表达式。

如果表达式是以下之一，则表达式出现在数值算术上下文中：

- 一元加运算符 `+`、一元减运算符 `-` 或按位取反运算符 `~` 操作数 (§15.15.3, §15.15.4, 或 §15.15.5)
- 乘法运算符 `*`、`/` 或 `%` 操作数 (§15.17)
- 数值类型的加法运算符 `+` 或减法运算符 `-` (§15.18.2)
- 移位运算符 `<<`、`>>`、`>>>` 操作数 (§15.19)。这些移位运算符的操作数被单独处理，而不是作为一个组。长位移距离（右操作数）不会将被位移的值（左操作数）提升为 long。
- 数值比较运算符 `<`、`<=`、`>` 或 `>=` 操作数 (§15.20.1)
- 数值相等运算符 `==` 或 `!=` 操作数 (§15.21.1)
- 整数按位运算符 `&`、`^` 或 `|` 操作数 (§15.22.1)

如果表达式是以下之一，则表达式出现在数值数组上下文中：

- 数组创建表达式中的维度表达式 (§15.10.1)
- 数组访问表达式中的索引表达式 (§15.10.3)

如果表达式是以下之一，则表达式出现在数值选择上下文中：

- 数值条件表达式第二个或第三操作数 (§15.25.2)
- 独立 switch 表达式的结果表达式 (§15.28.1)，其中所有结果表达式转换为数值类型

数值提升了数值上下文中所有表达式的提升类型。所选的提升类型使得每个表达式都能转换为该提升类型，并且在算术运算的情况下，该操作对于提升类型的值是定义的。数值上下文表达式的顺序对于数值提升并不重要。规则如下：

任何表达式如果是引用类型，它将受到拆箱转换 (§5.1.8)。

接下来，根据以下规则将宽化原始类型转换（§5.1.2）和窄化原始类型转换（§5.1.3）应用于某些表达式：

- 如果任何表达式的类型为 `double`，则提升后的类型为 `double`，其他不是 `double` 类型的表达式将通过宽化原始类型转换为 `double`。
- 否则，如果任何表达式的类型为 `float`，则提升后的类型为 `float`，其他不是 `float` 类型的表达式将通过宽化原始类型转换为 `float`。
- 否则，如果任何表达式的类型为 `long`，则提升后的类型为 `long`，其他不是 `long` 类型的表达式将通过宽化原始类型转换为 `long`。
- 否则，所有表达式都不是 `double`、`float` 或 `long` 类型。在这种情况下，上下文的类型决定了如何选择提升后的类型。

在数值算术上下文或数值数组上下文中，提升后的类型为 `int`，任何不是 `int` 类型的表达式都将通过宽化原始类型转换为 `int`。

在数值选择上下文中，适用以下规则：

- 如果任何表达式的类型为 `int` 且不是常量表达式（§15.29），则提升后的类型为 `int`，其他不是 `int` 类型的表达式将通过宽化原始类型转换为 `int`。
- 否则，如果任何表达式的类型为 `short`，且其他所有表达式都是 `short` 类型、`byte` 类型，或者值为可以在 `short` 类型表示的 `int` 类型常量表达式，则提升后的类型为 `short`，`byte` 表达式将通过宽化原始类型转换为 `short`，`int` 表达式将通过窄化原始类型转换为 `short`。
- 否则，如果任何表达式的类型为 `byte`，且其他所有表达式都是 `byte` 类型，或者值为可以在 `byte` 类型表示的 `int` 类型常量表达式，则提升后的类型为 `byte`，`int` 表达式将通过窄化原始类型转换为 `byte`。
- 否则，如果任何表达式的类型为 `char`，且其他所有表达式都是 `char` 类型，或者值为可以在 `char` 类型表示的 `int` 类型常量表达式，则提升后的类型为 `char`，`int` 表达式将通过窄化原始类型转换为 `char`。
- 否则，提升后的类型为 `int`，不是 `int` 类型的表达式将通过宽化原始类型转换为 `int`。

在转换后，如果存在任何值，则对每个表达式应用赋值值转换（§5.1.13）。

一元数值提升是指对出现在数值算术上下文或数值数组上下文中的单个表达式应用数值提升。

二元数值提升是指对出现在数值算术上下文中的一对表达式应用数值提升。

通用数值提升是指对出现在数值选择上下文中的所有表达式应用数值提升。

### 示例 5.6-1. 一元数值提升

```java
class Test {
    public static void main(String[] args) {
        byte b = 2;
        int a[] = new int[b]; // 维度表达式提升
        char c = '\u0001'; // 索引表达式提升
        a[c] = 1; // 一元负号 提升
        a[0] = -c;
        System.out.println("a=" + a[0] + "*" + a[i]);
        b = -1;
        int i = -b; // 按位取反提升
        System.out.println("0x" + Integer.toHexString(i) + "==0x" + Integer.toHexString(i));
        i = b << 4L; // 移位提升（左操作数）
        System.out.println("0x" + Integer.toHexString(b) + "<<4L=0x" + Integer.toHexString(i));
    }
}
```

该程序产生输出：

```
a:-1,1
-0xffffff=0x0
0xffffff4L=0xffffff0
```

### 示例 5.6-2. 二元数值提升

```java
class Test {
    public static void main(String[] args) {
        int i = 0;
        float f = 1.0f;
        double d = 2.0;

        // 首先 int*float 提升为 float*float，然后
        // float==double 提升为 double==double:
        if (i * f == d) System.out.println("coops");

        // charbyte 提升为 int&int:
        byte b = 0bf;
        char c = 'G';
        int control = c & b;
        System.out.println(Integer.toHexString(control));

        // 这里 int:float 提升为 float:float
        f = (b==0) ? i : 4.0f;
        System.out.println(i/f);
    }
}
```



该程序产生输出：

```
7
0.25
```

示例将 ASCII 字符 `G` 转换为 ASCII 控制字符 `BEL`，通过屏蔽该字符以外的低 5 位。`7` 是该控制字符的数值。

# 第 6 章 名称

名称用于引用程序中声明的实体。

声明的实体（§6.1）是包、类类型（普通或枚举）、接口类型（普通或注解类型）、引用类型的成员（类、接口、字段或方法）、类型参数（类或接口的）。

## 声明

- 如果泛型化不重要（如下文所示的非泛型上下文），标识符 `c` 表示非泛型类型 `c`。
- 如果泛型化很重要（如 §6.5 中除非泛型上下文以外的所有上下文），标识符 `c` 表示以下者之一：
    - 原始类型 `c`，它是泛型类型 `C<T>` 的擦除 (§4.6)；或
    - 参数化类型，它是泛型类型 `C<T>` 的特定参数化 (§4.5)。

这 14 种非泛型上下文如下：

1. 在模块声明简体 (§7.7.1) 的 `uses` 或 `provides` 指令中
2. 在单类型导入声明简体 (§7.5.1) 中
3. 在单静态导入声明简体 (§7.5.3) 中 `in` 的左侧
4. 在按需静态导入声明简体 (§7.5.4) 中 `.` 的左侧
5. 在构造函数声明简体 (§8.8) 中 `(` 的左侧
6. 在注解简体 (§9.7) 中 `@` 符号之后
7. 在类字面量简体 (§15.8.2) 中 `.class` 的左侧
8. 在限定表达式简体 (§15.8.4) 中 `.this` 的左侧
9. 在限定的超类字段访问表达式简体 (§15.11.2) 中 `.super` 的左侧
10. 在限定方法调用表达式简体 (§15.12) 中 `.Identifier` 或 `.super.Identifier` 的左侧
11. 在方法引用表达式简体 (§15.13) 中 `.super::` 的左侧
12. 在后置表达式或 `try-with-resources` 语句中的限定异常名中简体 (§15.14.1, §14.20.3)
13. 在方法或构造函数的 `throws` 子句中简体 (§8.4.6, §8.8.5, §9.4)
14. 在异常参数声明简体 (§14.20) 中

前 11 种非泛型上下文对应于 §6.5.1 中 `TypeName` 的前 11 种语法上下文。第 12 种非泛型上下文是限定的 `ExpressionName`，如 `c.x` 可能包含 `TypeName c` 以表示静态成员访问。在这十二个上下文中常用 `TypeName` 具有重要意义；它表明这些上下文对类型的使用是非一类的。相比之下，第 13 种和第 14 种非泛型上下文使用了 `ClassType`，表明 `throws` 和 `catch` 子句以一类的方式使用类型，类似于字段声明。由于异常类型无法被参数化，因此这两个上下文被描述为非泛型。

注意，`ClassType` 产生式允许注解，因此可以在 `throws` 或 `catch` 子句中使用类型上添加注解；而 `TypeName` 产生式不允许注解，因此例如在单类型导入声明中，无法对类型的名称添加注解。

## 命名规范

Java SE 平台的类库尽可能尝试根据下文介绍的规范选择名称。这些规范有助于提高代码的可读性并避免某些类型的名称冲突。

我们建议所有 Java 编程语言程序都遵循这些规范。然而，如果长久以来的习惯另有规定，则不应盲目遵循这些规范。例如，`java.lang.Math` 类的 `sin` 和 `cos` 方法具有数学上的习惯名称，尽管这些方法遵循建议的规范，是因为它们很短且不是动词。

## 包名和模块名

开发者应该通过为广泛分发的包选择唯一的包名，以避免两个已发布的包具有相同名的可能。这使得包能够容易且自动地进行分类。本节规定了用于生成唯一包名的建议规范。鼓励 Java SE 平台的实现提供自动支持，以将一组包从本地和随意的包名转换为此处描述的唯一名称。

如果不使用唯一的包名，则可能在其中一个冲突包创建时就产生包名冲突。这可能导致用户或程序员难以解决或无法解决的情况。在包之间具有受限交互的情况下，可以使用 `ClassLoader` 和 `ModuleLayer` 将同名的包相互隔离开，但这种方式对原生程序不是透明的。

你形成包名的方法是：首先拥有（或属于一个拥有）互联网域名，例如 `oracle.com`。然后你逐组件地反转该名称，在本例中得到 `com.oracle`，并将其作为你的包名的名前缀，使用在组织内部开发的规范来进一步管理包名。此类规范可能会指定某些包名组件为部门、小组、项目、机器或登录名称。

### 示例 6.1-1. 唯一的包名

```
com.nighthacks.scrabble.dictionary
org.openjdk.compiler.source.tree
net.jcip.annotations
edu.cmu.cs.bovik.cheese
gov.whitehouse.socks.mousefinder
```

唯一包名的第一个组件始终用全小写字母写入，应该是顶级名称之一，如 `com`、`edu`、`gov`、`mil`、`net` 或 `org`，或者是 ISO 标准 3166 指定的国家双字母代码之一。

在某些情况下，互联网域名可能不是有效的包名。以下是处理这些情况的建议：

- 如果名称包含连字符 `-`，则使用下划线。
- 如果有多个类型，使用数字下标。
- 如果名称是关键字，则使用下划线。

## 类和接口名

类名应使用描述性名词。接口名应简短且具有描述性，不要过长，并首字母大写。

### 示例 6.1-2. 模块名

```
com.nighthacks.scrabble
org.openjdk.compiler
net.jcip
```

### 示例 6.1-3. 描述性的类名

```
ClassLoader
SecurityManager
Thread
BufferedInputStream
```

等待，示例显示：

```
public class HashSet<E> extends AbstractSet<E> { ... }
public class HashMap<K,V> extends AbstractMap<K,V> { ... }
public class ThreadLocal<T> { ... }
public interface Functor<T,X> extends Throwable {
    T eval() throws X;
}
```

## 类型变量名

类型变量名应该简洁（尽可能单字符）且具有启发性，并且不包含小写字母。这有助于将类型参数与普通的类和接口区分开。

- 容器类型使用 `E` 表示元素类型。
- Map 使用 `K` 表示键的类型，`V` 表示值的类型。
- 使用 `X` 表示任意异常类型。
- 当类型没有更具体的特征时，使用 `T` 表示类型。

如果有多个表示任意类型的类型参数，应该使用字母表中与 `T` 相邻的字母，例如 `S`。或者，也可以使用数字下标（例如 `T1`、`T2`）来区分不同的类型变量。在这种情况下，具有相同前缀的变量应该下标。

如果泛型方法出现在泛型类内部，最好避免为方法和类的类型参数使用相同的名称，以避免混淆。嵌套泛型类也是如此。

## 方法名称

方法名称应当是动词或动词短语，采用驼峰命名法（mixed case），即首字母小写，后续每个单词的首字母大写。这里是关于方法名称的一些额外特定约定：

- 用于获取和设置可能被视为变量 `V` 的属性的方法应命名为 `getV` 和 `setV`。例如 `Thread` 类的 `getPriority` 和 `setPriority` 方法。
- 返回某物长度的方法应命名为 `length`，如 `String` 类中的方法。
- 对对象的某个布尔值 `V` 进行测试的方法应命名为 `isV`。例如 `Thread` 类的 `isInterrupted` 方法。
- 将其对象转换为特定格式 `F` 的方法应命名为 `toF`。例如 `Object` 类的 `toString` 以及 `java.util.Date` 类的 `toLocaleString` 和 `getGMTString` 方法。

在可能的情况下，将新类的方法命名基于与其相似的现有类（特别是来自 Java SE Platform API 的类），将使使用变得更加容易。

## 字段名称

非 `final` 字段名称应采用驼峰命名法，首字母小写，后续单词的首字母大写。请注意，设计良好的类极少有 `public` 或 `protected` 字段，常量字段（`static final fields`）除外。

字段名称应该是名词、名词短语或名词的缩写。

示例包括 `java.io.ByteArrayInputStream` 类的 `byte[] buf`、`pos` 和 `count`，以及 `java.io.InterruptedIOException` 类的字段 `bytesTransferred`。

## 常量名称

接口类型中的常量应该是（且类类型的 `final` 变量按照习惯也可以是）一个或多个单词、缩写或简称的序列，全部大写，并用下划线 `_` 分隔。常量名称应当具有描述性，而不一定需要缩写。按照习惯，它们可以是任何适当的词性。

常量示例包括 `Character` 类的 `MIN_VALUE`、`MAX_VALUE`、`MIN_RADIX` 和 `MAX_RADIX`。

代表备选值的常量组，或者不频繁使用的整数值掩码，有时使用通用缩写作为名称缀来完全指定。

### 6.1 声明

例如：

```
interface ProcessStates {
  int PS_RUNNING = 0;
  int PS_SUSPENDED = 1;
}
```

## 局部变量和参数名称

局部变量和参数名称应当短且有意义。它们通常是非单词的写写字母序列，例如：

- 缩写，如 `ColoredPoint` 的第一个字母 `cp`。
- 缩略词，如持有缓冲器引用的 `buf`。
- 助记词，为了帮助记忆而组织，通常模仿广泛使用的类的参数命名。例如：
    - 每当涉及输入和输出时，`in` 和 `out` 模仿 `System` 的字段。
    - 每当涉及偏移和长度时，`off` 和 `len` 模仿 `DataInput` 和 `DataOutput` 的方法。

应避免单字符局部变量或参数名称，除非是临时变量或持有某种类型的变量。常见的单字符名称有：

- `b` 代表 `byte`
- `c` 代表 `char`
- `d` 代表 `double`
- `e` 代表 `Exception`
- `f` 代表 `float`
- `i, j, k` 代表 `int`
- `l` 代表 `long`
- `o` 代表 `Object`
- `s` 代表 `String`
- `v` 代表任意类型

由两个或三个小写字母组成的局部变量或参数名称不应与包名的组成部分冲突。

## 6.2 名称和标识符

名称用于引用程序中声明的实体。名称有两种形式：简单名称和限定名称。简单名称是一个标识符。限定名称由一个名称、一个 `.` 标记和一个标识符组成。在确定名称的含义时（§6.5），考虑到名称出现的上下文。§6.5 的规则区分了表示（引用）包（§6.3）、类型（§6.5）、表达式中的变量或值（§6.6），或方法（§6.7）。包和引用类型可以通过限定名称访问成员。作为限定名称讨论和含义确定的背景，参见 §4.4、§4.5.2、§4.8、§4.9、§7.1、§8.2、§9.2 以及 §10.7 中的成员描述。程序中并非所有的标识符都是名称的一部分。标识符还用于以下情况：

- 在声明中（§6.1），标识符出现以指定已声明实体的名称。
- 作为标签语句（§14.7）以及 `break` 和 `continue` 语句（§14.15、§14.16）中的标签。标签语句及其相关的 `break` 和 `continue` 语句中标识符与声明中的标识符是完全独立的。
- 字段表达式（§15.1），每当标识符出现在 `.` 标记之后表示对象的成员。
- 方法调用表达式（§15.2），每当标识符出现在 `.` 标记之后表示要调用的方法。
- 方法引用表达式（§15.3），每当标识符出现在 `.` 标记之后表示要引用的方法。
- 限定类创建表达式（§15.9），标识符出现在 `new` 标记右侧，表示是编译时类型的成员。
- 注解的元素-值对（§9.7.1），表示对应注解类型的元素。

在程序中：

```java
class Test {
    public static void main(String[] args) {
        Class c = System.out.getClass();
        System.out.println(c.toString().length() + args[0].length + args.length);
    }
}
```



标识符 `Test` 以及 `args` 和 `c` 的首次出现并不是名称。相反，示例中出现了 `String`、`Class`、`System.out.getClass`、`System.out.println`、`c.toString`、`args` 和 `args.length`。

`args.length` 中的 `length` 是名称，因为 `args.length` 是限定名称（§6.5.2）而不是字段表达式（§15.1.1）。字段表达式以及方法调用表达式、方法引用表达式和限定类表达式使用标识符来表示感兴趣的成员。因此，`args[0].length()` 中的 `length` 不是名称，而是方法调用表达式中的标识符。

人们可能会奇怪为什么这些表达式使用标识符而不是简单名称（毕竟只是标识符）。原因是简单表达式名称定义在词法环境中；也就是说，简单表达式名称必须在变量声明的作用范围内（§6.5.6.1）。另一方面，字段访问、限定方法调用、方法引用和限定类创建引用的是名称不在词法环境中的成员。根据定义，此类名称仅在字段访问表达式、方法调用表达式、方法引用表达式或类实例创建的 `Primary` 提供的上下文中，或字段访问表达式、方法调用表达式等的 `super` 中。

更复杂的是，字段表达式不是表示对象字段的唯一方法。出于解析原因，限定名称用于表示作用域变量的字段。（变量本身由名称表示，此处提及）。让访问控制（§6.6）应用于所有字段的指示是必要的。

## 6.3 声明的作用范围

声明的*作用范围*（scope）是程序中的一个区域，在该区域内可以使用简单名称引用该声明定义的实体，前提是它没有被遮蔽（§6.4.1）。

当且仅当声明的作用范围包含了程序中的某个点时，则认为该声明在该点是*在作用范围内的*（in scope）。

可观测顶层包（§7.4.3）的声明的作用范围是与该包唯一可见的模块相关的所有可观测编译单元（§7.4.3）。

不可观测的包的声明永远不在作用范围内。

子包的声明永远不在作用范围内。

*java* 包始终在作用范围内。

由单类型导入声明（§7.5.1）或按需类型导入声明（§7.5.2）导入的类型的作用范围是：模块声明（§7.7）以及该 `import` 声明所在编译单元中所有的类声明和接口类型声明（§7.6），以及该编译单元的模块声明或包声明上的任何注解。

由单静态导入声明（§7.5.3）或按需静态导入声明（§7.5.4）导入的成员的作用范围是：模块声明以及该 `import` 声明所在编译单元中所有的类声明和接口类型声明，以及该编译单元的模块声明或包声明上的任何注解。

顶层类型（§7.6）的作用范围是声明该顶层类型的包中所有的类型声明。

在类 `c` 中声明或由 `c` 继承的成员 `m`（§8.1.6）的声明的作用范围是 `c` 的整个体，包括任何嵌套类型声明。

在接口 `t` 中声明或由 `t` 继承的成员 `m`（§9.1.4）的声明的作用范围是 `t` 的整个体，包括任何嵌套类型声明。

枚举类型 `t` 中声明的枚举常量 `c` 的作用范围是 `t` 的体，并且 `switch` 语句的任何 `case` 标签都属于枚举类型 `t`（§14.11）。

方法（§8.4.1）、构造方法（§8.8.1）或 lambda 表达式（§15.27）的形式形式参数的作用范围是该方法、构造方法或 lambda 表达式的整个体。

类类型参数（§8.1.2）的作用范围是类声明的类型参数部分、该类声明的任何超类或超接口的类型参数部分，以及类体。

接口类型参数（§9.1.2）的作用范围是接口声明的类型参数部分、该接口声明的任何超接口的类型参数部分，以及接口体。

方法类型参数（§8.4.4）的作用范围是方法的整个声明，包括类型参数部分，但不包括方法修饰符。

构造方法类型参数（§8.8.4）的作用范围是构造方法的整个声明，包括类型参数部分，但不包括构造方法修饰符。

由块（§14.2）直接闭合的局部类声明的作用范围是紧邻包含它的块的剩余部分，包括它自己的类声明。

由 switch 块语句组（§14.11）直接闭合的局部类声明的作用范围是紧邻包含它的 switch 块组的剩余部分，包括它自己的类声明。

块（§14.4）中局部变量声明的作用范围是该声明所在块的剩余部分，从它自己的初始化器开始，并包括局部变量声明语句右侧的任何后续声明符。

在基础 `for` 语句的 `ForInit` 部分（§14.4.1）中声明的局部变量的作用范围包含以下所有内容：

- 变量自身的初始化器
- `for` 语句 `ForInit` 部分右侧的任何后续声明符
- `for` 语句的 `Expression` 和 `ForUpdate` 部分
- 包含的 `Statement`

在增强型 `for` 语句的 `FormalParameter` 部分（§14.1.2）中声明的局部变量的作用范围是所包含的 `Statement`。

在 `try` 语句的 `catch` 子句（§14.20）中声明的异常处理器参数的作用范围是与 `catch` 相关的整个块。

在 `try-with` 资源语句（§14.20.3）的 `ResourceSpecification` 中声明的变量的作用范围是从声明处向右，直到 `ResourceSpecification` 的剩余部分，以及与 `try-with` 资源语句相关的整个 `try` 块。

`try-with-resources` 语句的翻译意味着上述规则。

### 示例 6.3-1 类型声明的作用范围

这些规则意味着类和接口类型的声明不需要在类型使用之前出现。在以下程序中，在类 `Point` 中 `PointList` 是有效的，因为类声明 `PointList` 的作用范围包含了类 `Point` 和类 `PointList`，以及包 `points` 中其他编译单元的任何其他类型声明。

```java
package points;

class Point {

    int x, y;

    PointList list;

    Point next;

}

class PointList {

    Point first;

}
```

### 示例 6.3-2 局部变量声明的作用范围

以下程序会导致编译错误，因为 x 的初始化在局部变量 x 声明的作用范围内，但局部变量 x 还没有值且无法使用。

```java
class Test1 {

    static int x;

    public static void main(String[] args) {

        int x = x;

    }

}
```

以下程序可以编译，因为局部变量 x 在使用之前已经被赋予了值。

```java
class Test2 {

    static int x;

    public static void main(String[] args) {

        int x = (x=2)*2;

        System.out.println(x);

    }

}
```

在以下程序中，three 的初始化可以正确引用之前声明的变量，而下一行的方法调用也可以正确引用该变量。

```java
class Test3 {

    public static void main(String[] args) {

        System.out.print("2+1=");

        int two = 2, three = two + 1;

        System.out.println(three);

    }

}
```

该程序的输出为：2+1=3

## 6.4 遮蔽与覆盖

局部变量（§14.4）、形式参数（§8.4.1，§15.27.1）、异常参数（§14.20）和局部类（§14.3）只能使用简单名称引用，不能使用限定名称（§6.2）。

某些声明不允许在局部变量、形式参数、异常参数或局部类声明的作用范围内存在，因为无法仅通过简单名称区分这些声明的实体。

例如，如果方法的形式参数名称可以重声明为方法体内的局部变量名称，那么局部变量将遮蔽形式参数，导致无法引用到该形式参数——这是一个不希望的结果。

如果在方法、构造方法或 lambda 表达式体内部使用形式参数名称声明新变量，则会导致编译错误，除非该新变量是声明在方法、构造方法或 lambda 表达式内部的类声明中。

如果在局部变量 v 的作用范围内使用其名称声明新变量，则会导致编译错误，除非该新变量是声明在 v 的作用范围内的某个类声明中。

如果在 `catch` 子句的块内部使用异常参数名称声明新变量，则会导致编译错误，除非该新变量是声明在 `catch` 块内部的类声明中。

### 遮蔽与掩盖

如果在局部类 `c` 的作用域内使用该名称声明一个新的局部类，则将导致编译时错误，除非该新局部类声明在另一个类内部，而该类的声明位于 `c` 的作用域内。

这些规则允许在变量或局部类的作用域内发生的嵌套声明中重新声明变量或局部类；此类嵌套声明可以是局部类（§14.3）或匿名类（§15.9）。因此，形式参数、局部变量或局部类的声明可能在嵌套在方法、构造函数或 lambda 表达式内部的类声明中被遮蔽；而异常参数的声明则可能在嵌套在 catch 句块（Block）内部的类声明中被遮蔽。

对于处理 lambda 表达式创建的类以及在 lambda 表达式中声明的其他变量有两种设计方案：一种是类似于局部类，lambda 表达式引入了一个新的“层级”，表达式外部的所有名称都可以被重新声明。另一种是“局部”策略：类似于 catch 句、for 循环和块，表达式的操作层级与包含它的上下文处于同一层级，且表达式外部的局部变量不能被遮蔽。上述规则使用了后者策略；并没有特殊规定允许在 lambda 表达式中声明的变量遮蔽在包含的方法中声明的变量。

请注意，局部类的规则并没有对类内部声明的同名类留出例外。然而，这种情况被另一条规则禁止：一个类不能与它包含的类具有相同的名称（§8）。

### 示例 6.4-1. 尝试遮蔽局部变量

将标识符声明为方法、构造函数或初始化块的局部变量时，其不能出现在同名参数或局部变量的作用域内，以下程序将发生编译时错误：

```java
class Test1 {

    public static void main(String[] args) {

        int i;

        for (int i = 0; i < 10; i++) {

            System.out.println(i);

        }

    }

}
```

这种限制有助于检测某些非常隐晦的 bug。对局部变量遮蔽成员的行为进行简单限制被认为是不现实的，因为在子类中添加成员可能会允许子类重命名局部变量。相关的考虑也使得嵌套类对局部变量的遮蔽，或嵌套类内部声明的局部变量对局部变量的遮蔽这些限制变得缺乏吸引力。

因此，以下程序可以编译无错误：

```java
class Test2 {

    public static void main(String[] args) {

        int i;

        class Local {

            for (int i = 0; i < 10; i++) {

                System.out.println(i);

            }

        }

        new Local();

    }

}
```

另一方面，同名的局部变量可以在两个独立的块或语句中声明，且其中一个都不包含另一个：

```java
class Test3 {

    public static void main(String[] args) {

        for (int i = 0; i < 10; i++) {

            System.out.print(i + " ");

        }

        for (int i = 10; i > 0; i--) {

            System.out.print(i + " ");

        }

    }

}
```

该程序编译无错误，并在执行时产生输出：

0 1 2 3 4 5 6 7 8 9 0 9 8 7 6 5 4 3 2 1

## 6.4.1 遮蔽

某些声明可能在其作用域的部分范围内被另一个同名的声明所遮蔽，在这种情况下，无法使用简单名称来引用所声明的实体。

遮蔽（Shadowing）不同于隐藏（hiding §8.3, §8.4.2, §8.5, §9.3, §9.5），后者仅适用于本会被继承但并非因为子类中的声明而隐藏的成员。遮蔽也不同于掩盖（obscuring §6.4.2）。

类型 `n` 的声明 `a` 在 `d` 的整个作用域内，遮蔽在 `a` 出现处作用域内任何其他名为 `n` 的类型的声明。

字段或形式参数 `n` 的声明 `a` 在 `a` 的整个作用域内，遮蔽在 `a` 出现处作用域内任何其他名为 `n` 的变量的声明。

局部变量或形式参数 `n` 的声明 `a` 在 `a` 的整个作用域内，遮蔽在 `a` 出现处作用域内任何其他名为 `n` 的变量的声明。

局部变量或形式参数 `n` 的声明 `a` 在 `a` 的整个作用域内，(a) 遮蔽在 `a` 出现处作用域内任何其他名为 `n` 的字段的声明，以及 (b) 遮蔽在出现处作用域内任何其他名为 `n` 的变量的声明。

### 示例 6.4.1-1. 局部变量对字段的遮蔽

```java
class Test {

    int x = 1;

    public static void main(String[] args) {

        int x = 0;

        System.out.print("x=" + x);

        System.out.println("Test.x=" + Test.x);

    }

}
```

该程序产生输出：

x=0, Test.x=1

该程序声明了：

- 类 `Test`
- 类 `Test` 的成员变量 `x`
- 类 `Test` 的方法 `main`
- 方法的参数 `args`
- 方法的局部变量 `x`

由于类变量的作用域包含了类的整个体（§8.2），类变量 `x` 通常在 `main` 方法的整个体范围内都是可用的。然而在这个示例中，类变量 `x` 在 `main` 方法体内部被局部变量 `x` 的声明所遮蔽。

局部变量的作用域是其声明所在块的剩余部分（§6.3）；在这种情况下，它是 `main` 方法体内的剩余部分，即其初始化器 "0" 以及对 `System.out.print` 和 `System.out.println` 的调用。

这意味着：

- print 调用中的表达式 `x` 指向（表示）局部变量 `x` 的值。
- println 调用使用了限定名称 `Test.x`（§6.6），通过类类型名称 `Test` 访问类变量 `x`，因为 `Test.x` 的声明在此处被遮蔽，无法通过其简单名称引用。

关键字 `this` 也可以用于访问被遮蔽的字段 `x`，使用形式 `this.x`。事实上，这种用法通常出现在构造函数中（§8.8）。

```java
class Pair {

  Object first, second;

  public Pair(Object first, Object second) {

    this.first = first;

    this.second = second;

  }

}
```

在这种风格化的语境中可能会引起混义。通常情况下，让局部变量与字段具有相同的名称被认为是不良的风格。

## 示例 6.4.1-2. 另一个类型声明对类型声明的遮蔽

```java
import java.util.*;

class Vector {
```



## 示例代码

```java
int val[] = { 1, 2 };

class Test {
    public static void main(String[] args) {
        Vector v = new Vector();
        System.out.println(v.val[0]);
    }
}
```

该程序可以编译并打印出：

- 1

使用了此处声明的 `Vector` 类，而不是可能按需导入的泛类 `java.util.Vector` (§8.1.2)。

## 6.4.2 遮蔽 (Obscuring)

简单名可能出现在可能被解释为变量名、类型名或包名的语境中。在这些情况下，§6.5.2 中的规则规定，变量的选择将优于类型，类型的选择将优于包。因此，有时无法通过其简单名来引用类型或包，即使其声明在作用范围内且未被掩蔽。我们称这种声明为“遮蔽”。

遮蔽与掩蔽（§6.4.1）以及隐藏（§8.3, §8.4.2, §8.5, §9.3, §9.5）是不同的。

模块名与变量名、类型名或包名之间不存在遮蔽；因此，模块可以与变量、类型和包共享名称，尽管并不建议以其所包含的包来为模块命名。

> §6.1 中的命名规范有助于减少遮蔽，但如果确实发生了，这里是一些关于你可以采取什么操作来避免它的说明。

当包名出现在表达式中时：

- 如果包名被字段声明遮蔽，则通常可以使用导入语句 (§7.5) 来使该包中声明的类型名可用。

## 名称 (NAMES)

## 确定名称的含义

- 如果包名被参数或局部变量的声明遮蔽，则可以更改参数或局部变量的名称而不影响其他代码。

包名的第一个分量通常不会被误认为是类型名，因为类型名通常以单个大写字母开头。（Java 编程语言实际上并不依赖大小写区分来确定一个名称是包名还是类型名。）

涉及类和接口类型名的遮蔽很少见。字段、参数和局部变量的名称不会遮蔽类型名，因为它们惯例上小写字母开头，而类型名惯例上以大写字母开头。

方法名不能遮蔽其他名称，也不会被其他名称遮蔽 (§6.5.7)。

涉及字段名的遮蔽很少见；但不过：

- 如果字段名遮蔽了包名，则通常可以使用导入语句 (§7.5) 来使该包中声明的类型名可用。
- 如果字段名遮蔽了类型名，则可以使用类型的完全限定名，除非该类型表示一个局部类 (§14.3)。
- 字段名不能遮蔽方法名。
- 如果字段名被参数或局部变量的声明掩蔽，则可以更改参数或局部变量的名称而不影响其他代码。

涉及常量名称的遮蔽很少见：

- 常量名不包含小写字母，因此它们通常不会遮蔽包名或类型的名称，通常也不会掩蔽字段（因为字段名称通常包含至少一个小写字母）。
- 常量名不能遮蔽方法名，因为它们在语法上是可以被区分的。

## 6.5 确定名称的含义

名称的含义取决于它所使用的语境。确定名称的含义需要三个步骤：

1. 首先，语境导致名称在语法上落入以下类之一：模块名、包名、类型名、表达式名、方法名或歧义名。类型名和方法名比其他五类更具复杂性，因为它们分别被分类为 `TypeName` 和 `UnqualifiedTypeName`（后者见 §3.8）。
2. 其次，在语境中首先被分类为 `AmbiguousName` 或 `TypeName` 的名称。
3. 第三，分类结果决定了名称的最终含义：

```text
ModuleName:
    Identifier

PackageName:
    Identifier

TypeName:
    Identifier

PackageTypeName:
    Identifier

ExpressionName:
    AmbiguousName

MethodName:
    UnqualifiedIdentifier
```

这种遮蔽涉及实体。语境的使用有助于减少不同实体之间的名称冲突。如果遵循 §6.1 中的规范，这种冲突是罕见的。

## 6.5.1 名称的语法分类

名称在以下语境下在语法上分类为 `ModuleName`：

- 导入语句中（§7.7）
- 导出语句中（§7.7）

名称在以下语境下在语法上分类为 `PackageName`：

- 导入语句中（§7.7）
- 导出语句中（§7.7）

名称在以下语境下在语法上分类为 `TypeName`：

- 导入语句中（§7.7）
- 静态导入语句（§7.5）
- 显式构造函数调用或类创建或方法调用语句中（§8.7.1, §15.9, §15.12）
- 实例化（§15.9）
- 数组表达式（§15.10）
- `instanceof` 运算符（§15.2）
- 方法的返回类型（§8.4）
- 注释类型（§9.6）
- 方法的抛出子句（§8.4.6, §8.5）
- 泛型类、接口或方法的类型参数
- 泛型类型参数
- 泛型类型通配符
- 泛型类型中的 `<`
- 数组类型中的 `[]`
- 限定表达式中的 `.`（§8.8）
- 注释类型中的 `&`（§9.7）
- 类表达式中的 `.class`（§15.8）
- 限定表达式中的 `this`（§15.8）
- 方法调用中的 `::`（§15.12）
- 字段中的 `super`（§15.11）
- 限定方法调用中的 `.super`（§15.12）

名称在以下语境下在语法上分类为 `ExpressionName`：

- 字段声明（§14.4, §14.14.1, §14.14.2, §14.20.3）
- 方法的参数声明（§8.4）
- 局部变量声明（§14.4, §14.14.1, §14.14.2, §14.20.3）
- 显式构造函数调用或类创建或方法调用语句中的异常参数列表（§8.7.1, §15.9, §15.12）

名称在以下语境下在语法上分类为 `MethodName`：

- 方法声明（§8.4）

名称在以下语境下在语法上分类为 `AmbiguousName`：

- Lambda 表达式（§14.1）

# 名称

## 确定名称的含义

在数组类型中括号左侧的名称，被归类为 `TypeName`（类型名）。后续步骤将确定 p、q 和 `Foo` 是类型名还是包名。

- 在方法调用表达式（§15.12）中的 `.` 之前
- 在限定的 `TypeName`（类型名）的 `.` 左侧
- 在限定的 `ExpressionName`（表达式名）的 `.` 左侧

## 确定名称的含义

- 字段、参数或局部变量的名称可以用作表达式（§15.14.1）。
- 方法名称只能作为方法调用表达式的一部分（§15.12）出现在表达式中。
- 类或接口类型的名称只能作为类字面量（§15.8.2）、限定表达式（§15.8.4）、类实例创建表达式（§15.9）、数组创建表达式（§15.10.1）、强制类型转换表达式（§15.6）、`instanceof` 表达式（§15.20.2）、枚举常量（§8.9）或作为字段或方法的限定名称的一部分出现在表达式中。
- 包的名称只能作为类或接口类型的限定名称的一部分出现在表达式中。

### 6.5.2 上下文模糊名称的重分类

`AmbiguousName`（模糊名称）随后被重分类为单个 `Identifier`（标识符）：

- 如果该 `Identifier` 出现在局部变量声明 (§14.4)、参数声明 (§8.4.1, §8.8.1, §14.20) 或具有名称的字段声明 (§8.3) 的范围（§6.3）内，则该 `AmbiguousName` 被重分类为 `ExpressionName`（表达式名）。
- 否则，如果包含该 `Identifier` 的编译单元 (§7.3) 通过单静态导入声明 (§7.5.3) 或按需静态导入声明 (§7.5.4) 声明了具有该名称的字段，则该 `AmbiguousName` 被重分类为 `ExpressionName`。
- 否则，如果该 `Identifier` 是一个有效的 `TypeIdentifier`（类型标识符），并且出现在顶级类（§Classes）或接口类型声明（§Interfaces）、局部类声明 (§14.3) 或成员类型声明 (§8.5, §9.5) 具有名称的范围（§6.3）内，则该 `AmbiguousName` 被重分类为 `TypeName`（类型名）。
- 否则，如果该 `Identifier` 是一个有效的 `TypeIdentifier`，并且包含该 `Identifier` 的编译单元 (§7.3) 通过单类型导入声明 (§7.5.1)、按需类型导入声明 (§7.5.2)、单静态导入声明 (§7.5.3) 或按需静态导入声明 (§7.5.4) 声明了该名称的类型，则该 `AmbiguousName` 被重分类为 `TypeName`。
- 否则，`AmbiguousName` 被重分类为 `PackageName`（包名）。后续步骤将确定该名称的包实际上是否存在。

如果 `AmbiguousName` 是一个由一个名称、一个 `.` 和一个 `Identifier` 组成的限定名称，则 `.` 左侧的名称首先被重分类（前提是它本身也是一个 `AmbiguousName`）。然后将有一个选择：

## 确定名称的含义 6.5

- 如果 `.` 左侧的名称被重分类为 `PackageName`
- 如果 `.` 左侧的名称被重分类为 `ExpressionName`，则此 `AmbiguousName` 被重分类为 `ExpressionName`。后续步骤将确定带有标识符的名称实际上是否存在。

潜在类型名必须是“有效的 `Identifier`”的要求防止将 `var` 和 `yield` 视为类型名。这通常是多余的，因为声明规则已经防止了引入名为 `var` 和 `yield` 的类型。然而，在某些情况下，编译器可能会发现一个名为 `var` 或 `yield` 的二进制类，我们希望明确此类类永远不能这样命名。简单的解决方案是始终检查是否为有效的 `Identifier`。

### 示例 6.5.2-1. 上下文模糊名称的重分类

考虑以下“库代码”：

```java
package org.rpgpoet;

import java.util.Random;

public interface Music { Random[] wizards = new Random[4]; }
```

然后考虑另一个包中的这个示例：

```java
package bazola;

class Gabriel {
    static int n = org.rpgpoet.Music.wizards.length;
}
```

首先，名称 `org.rpgpoet.Music.wizards.length` 被归类为 `ExpressionName`，因为它充当了后缀表达式（PostfixExpression）。因此，以下每个名称：

```text
org.rpgpoet.Music.wizards
org.rpgpoet.Music
org.rpgpoet
org
```

最初都被归类为 `AmbiguousName`。这些名称的重分类如下：

- `org` 被重分类为 `PackageName`（因为没有 `org` 的类或接口）。
- `org.rpgpoet` 被重分类为 `PackageName`（因为 `org.rpgpoet` 包中没有 `Music` 的类或接口）。
- 由于 `org.rpgpoet.Music` 是接口，它被重分类为 `TypeName`。
- 最后，由于 `org.rpgpoet.Music.wizards` 是可访问类型，`org.rpgpoet.Music.wizards` 被重分类为 `ExpressionName`。

### 6.5.3 模块名称的含义

模块 M，无论是简单的还是限定的，都表示该名称的模块（如果存在）。本节在没有该名称模块时不强制要求编译错误。相反，`exports` 和 `opens` 指令对不存在的模块具有容忍性。

归分类为包名的含义确定方式如下：

#### 6.5.3.1 简单包名

如果包名由单个 `Identifier` 组成，则该标识符必须出现在该包声明的范围（§6.3）内，且该包必须对当前模块可见（§7.3）。

#### 6.5.3.2 限定包名

如果包名的格式为 `Q.Id`，则 `Q` 必须是一个包名。如果 `Q.Id` 未指向一个对当前模块可见的（§7.3），则发生编译错误。

### 6.5.4 PackageOrTypeName 的含义

#### 6.5.4.1 简单 PackageOrTypeName

如果 `PackageOrTypeName` $\varrho$ 是一个有效的 `TypeIdentifier` 并且出现在名为 $\varrho$ 的类型的范围内，则该 `PackageOrTypeName` 被重分类为 `TypeName`。

否则，`PackageOrTypeName` 被重分类为 `PackageName`。该 `PackageOrTypeName` 的含义是重分类后的名称。

#### 6.5.4.2 限定 PackageOrTypeName

对于格式为 `Q.Id` 的限定 `PackageOrTypeName`，如果 `Id` 是一个有效的 `TypeIdentifier` 且由 `Q` 限定的包具有成员类型 `Id`，则该限定 `PackageOrTypeName` 被重分类为 `TypeName`。

否则，它被重分类为 `PackageName`。该限定 `PackageOrTypeName` 的含义是重分类后的名称。

### 6.5.5 类型名的含义

归分类为 `TypeName` 的名称的含义确定方式如下：

#### 6.5.5.1 简单类型名

如果类型名由单个 `Identifier` 组成，则该标识符必须出现在该类型类型声明的范围（§6.3）内，否则发生编译错误。该类型名的含义是该类型。

#### 6.5.5.2 限定类型名

如果名称的格式为 `Q.Id`，则 `Q` 必须是当前模块可见的包中某个类型的名称，或者是当前模块可见的包名（§7.4.3）。

如果 `Id` 恰好命名了一个可访问类型（§6.6）是由 `Q` 限定的类型或包的成员，则该限定类型名表示该类型。

如果 `Id` 未命名 `Q` 内部的成员类型（§8.5, §9.5），或者 `Id` 在 `Q` 内部命名了多个成员类型，则发生编译错误。

#### 示例 6.5.5.2-1. 限定类型名

```java
class Test {
    public static void main(String[] args) {
        java.util.Date date = new java.util.Date(System.currentTimeMillis());
        System.out.println(date.toString());
    }
}
```

该程序在首次运行时产生了以下输出：

```text
Sun Jan 21 22:56:29 1996
```

在此示例中，`java.util.Date` 必须表示一个类型，因此我们首先使用递归过程确定 `java.util` 是可访问的类型还是包（它确实是一个包），然后查看在该包中类型 `Date` 是否可访问。

### 6.5.6 表达式名称的含义

被分类为 `ExpressionName` 的名称的含义确定如下。

#### 6.5.6.1 简单表达式名称

如果表达式名称由单个标识符（`Identifier`）组成，则在标识符出现的地方，必须恰好有一个声明，其可以是局部变量、形式参数或字段。否则，将发生编译错误。

如果该声明表示一个实例变量（§8.3.1.1），则表达式名称必须出现在实例方法（§8.4.3.2）、实例变量初始化器（§8.3.2）、实例初始化器（§8.6）或构造函数（§8.8）中。如果表达式名称出现在类方法、类变量初始化器或静态初始化器（§8.7）中，则发生编译错误。

如果该声明声明了一个 `final` 变量，且其在简单表达式之前已明确赋值，则该名称的含义为该变量的值。否则，表达式名称的含义为该声明所定义的变量。

如果表达式名称出现在赋值上下文、调用上下文或类型转换上下文中，则表达式名称的类型为经过捕获转换后的字段、局部变量或参数的声明类型（§5.1.10）。

否则，表达式名称的类型为字段、局部变量或参数的声明类型。

也就是说，如果表达式名称出现在“右侧”，则其类型取决于捕获转换。如果表达式名称是出现在“左侧”的变量，则其类型不受捕获转换的影响。

### 示例 6.5.6-1 简单表达式名称

```java
class Test {
    static int v;
    static final int f = 3;

    public static void main(String[] args) {
        int i;
        i = 2;
        v = 33;
        f = 33; // 编译错误
        System.out.println(i + " " + v + " " + f);
    }
}
```



在此程序中，作为 `i`、`v` 和 `f` 赋值左侧所使用的名称分别表示局部变量 `i`、字段 `v` 以及 `f` 的值（而不是变量 `f`，因为 `f` 是 `final` 的）。该示例在编译时产生错误，因为最后一次赋值的左侧没有变量。如果删除了错误的赋值，修改后的代码可以编译并产生输出：

- 1 2 3

## 6.5.6.2 限定表达式名称

如果一个表达式的形式为 `Q.Id`，则 `Q` 已经被分类为包名、类型名称或表达式名称。

如果 `Q` 是包名，则发生编译错误。

如果 `Q` 是一个命名为类类型的类型名称（§8 类），那么：

- 如果该类类型中没有恰好存在一个可访问的（§6.6）名为 `Id` 的字段成员，则发生编译错误。
- 否则，如果该唯一的可访问成员字段不是类变量（即它没有声明为 `static`），则发生编译错误。
- 否则，如果该类变量被声明为 `final`，则 `Q.Id` 表示类变量的值。

表达式 `Q.Id` 的类型为经过捕获转换后类变量的声明类型（§5.1.10）。

如果 `Q.Id` 出现在需要变量而非值的上下文中，则发生编译错误。

否则，`Q.Id` 表示类变量。

表达式 `Q.Id` 的类型为经过捕获转换后类变量的声明类型（§5.1.10）。

注意，此条款涵盖了 `enum` 常量的使用（§8.9），因为这些常量始终有一个对应的 `final` 类变量。

如果 `Q` 是一个命名为接口类型的类型名称（§9 接口），那么：

- 如果该接口类型中没有恰好存在一个可访问的（§6.6）名为 `Id` 的字段成员，则发生编译错误。
- 否则，`Q.Id` 表示字段的值。

表达式 `Q.Id` 的类型为经过捕获转换后字段的声明类型（§5.1.10）。

如果 `Q.Id` 出现在需要变量而非值的上下文中，则发生编译错误。

如果 `Q` 是一个表达式名称，令 $\tau$ 为表达式 `Q` 的类型：

- 如果 $\tau$ 不是引用类型，则发生编译错误。
- 如果类型 $\tau$ 中没有恰好存在一个可访问的（§6.6）名为 `Id` 的字段成员，则发生编译错误。
- 否则，如果该字段是以下任意一种：
    - 接口类型的字段
    - 类类型的 `final` 字段（可以是静态变量，也可以是实例变量）

§15.12.1 选择在类 `Super` 中搜索，因为它包含一个名为 `f2` 的成员。然而，`Super.f2(String)` 不适用于 `f2(0)`，因此发生了编译时错误。注意，类 `Test` 未被搜索。

对于调用 `f3(0)`，作用域内有三个名为 `f3` 的方法。第一和第二个，即方法 `Super.f3(String)` 和 `Super.f3(int, int)` 的声明在整个匿名类声明的范围内都是可见的。第三个，方法 `Test.f3(int)` 的声明在 `Test` 的主体内（包括匿名类声明）中都是可见的。§15.12.1 选择在类 `Super` 中搜索，因为它包含一个名为 `f3` 的成员。然而，`Super.f3(String)` 和 `Super.f3(int, int)` 不适用于 `f3(0)`，因此发生了编译时错误。注意，类 `Test` 未被搜索。

在调用词法包围作用域之前搜索嵌套类的层级结构被称为“组合规则”（§15.12.1）。

## 6.6 Java 访问控制

Java 编程语言提供了访问控制机制，以防止包或类的用户依赖于该包或类实现中不必要的细节。如果允许访问，则被访问的实体应该是可访问的。

注意，访问性是一个静态属性，可以在编译时确定，它仅取决于类型和声明修饰符。

限定名称是访问包和引用类型成员的手段。当成员名称在上下文中（§6.5.1）未被归类为限定类型名（表示包或引用类型的成员，§6.5.5.2）或限定表达式名（表示引用类型的成员，§6.5.6.2）时，则将应用访问控制。

例如，单类型导入声明使用了限定类型名（§7.5.1），因此该名称必须从包含导入声明的编译单元中来说是可访问的。另一个例子是，类声明可以使用限定类型名作为父类（§8.1.5），因此该名称类型也必须是可访问的。

某些表达式在 §6.5.1 的类分类中是“缺失”的：通过 `Primary`（§15.11.1）进行的字段访问、在 `Primary` 上的调用（§15.12）、通过 `Primary` 建立方法引用（§15.13）以及类实例创建中的实例化类（§15.9）。由于 §6.2 中给出的原因，这些表达式都使用了标识符而非名称。因此，对成员（无论是字段、方法还是类型）的访问控制是通过字段访问表达式、方法调用表达式、方法引用表达式和限定类实例创建表达式显式实施的。（注意，对字段的访问也可以通过作为后置表达式出现的限定名称来表示。）

此外，许多语句和表达式允许使用类型而非名称。例如，类声明可以使用参数化类型（§4.5）来表示父类。参数化类型不是限定名称，类声明需要显式地对所指的父类执行访问控制。因此，大多数语句和表达式在 §6.5.1 提供的上下文中，在对类型名进行分类的同时，也执行了它们自身的访问控制检查。

除了包或引用类型的成员外，还存在对引用类型构造函数的访问问题。当隐式或显式调用构造函数时，必须检查访问控制。因此，访问控制通过显式构造函数调用语句（§8.8.1）和类实例创建表达式（§15.9.3）进行检查。这些检查是必要的，因为 §6.5.1 未提到构造函数调用语句（因为它们间接引用构造函数），并且涉及到未限定实例创建表达式所指示的类类型与该类的构造函数之间的区别。此外，我们无法依赖在限定类型分类过程中进行访问控制检查。

访问性影响类成员的继承（§8.2），包括隐藏和方法重写（§8.2）。

## 6.6.1 确定访问性

- 如果顶层类或接口类型声明为 `public`，它是包的成员，那么在包中之外是可访问的。
- 访问性是一个静态属性。如果允许访问，则被访问的实体是可访问的。
- 如果顶层类或接口类型声明为 `public`，它是包的成员，那么在包含导入声明的编译单元中是可访问的。
- 类可以使用限定类型名作为父类，因此该名称类型必须是可访问的。

## 6.6.2 访问控制

- 这种检查是必要的，并且涉及到未限定实例创建表达式所指示的类类型与该类的构造函数之间的区别。此外，我们无法依赖在限定类型分类过程中进行访问控制检查。

访问性影响类成员的继承（§8.2），包括隐藏和方法重写（§8.2）。

- 如果顶层类或接口类型声明为 `public`，它是包的成员，那么在包中之外是可访问的。
- 访问性是一个静态属性。如果允许访问，则被访问的实体是可访问的。
- 如果顶层类或接口类型声明为 `public`，它是包的成员，那么在包含导入声明的编译单元中是可访问的。
- 如果顶层类或接口类型声明为 `public`，它是包的成员，那么在包中之外是可访问的。

## 6.6.3 访问 public 字段、方法和构造函数

一个 `public` 类成员或构造函数在它定义的包内是可访问的，并且从任何其他包也是可访问的，只要它定义的包是可见的（§7.4.3）。例如，在编译单元中：

```java
package points;

public class Point {

    int x, y;

    public void move(int dx, int dy) {

        x += dx; y += dy;

        moves++;

    }

    public static int moves = 0;

}
```

`public` 类 `Point` 有公共方法 `move` 和静态字段 `moves`。这些公共成员对于任何可以访问包 `points` 的包都是可访问的。字段 `x` 和 `y` 不是 `public`，因此仅在 `points` 包内部是可访问的。

## 6.6.4 访问 public 和非 public 类

如果一个类缺少 `public` 修饰符，则对类声明的访问被限制在它所在的包内（§6.6）。在示例中：

```java
package points;

public class Point {

    int x, y;

    public void move(int dx, int dy) { x += dx; y += dy; }

}

class PointList {

    Point next, prev;

}
```

编译单元中声明了两个类。`Point` 类在包 `points` 之外是可见，而 `PointList` 类仅在包内是可访问的。

`package`。因此，另一个包中的编译单元可以通过以下方式使用其全限定名访问 `points.Point`：

```java
package pointsUser;

class Test1 {

    public static void main(String[] args) {

        points.Point p = new points.Point();

        System.out.println(p.x + " " + p.y);

    }

}
```

或者通过使用提及全限定名的单类型导入声明（§7.5.1），这样此后就可以使用简单名：

```java
package pointsUser;

import points.Point;

class Test2 {

    public static void main(String[] args) {

        points.Point p = new Point();

        System.out.println(p.x + " " + p.y);

    }

}
```

然而，该编译单元无法使用或导入 `points.PointList`，因为它没有被声明为 `public`，因此在 `points` 包之外是不可见的。

# 示例 6.6-4. 对包级访问权限字段、方法和构造函数的访问

如果没有指定 `public`、`protected` 或 `private` 访问修饰符，则类成员或构造函数具有包访问权限：它在包含该类成员的类的包内是可访问的，但该类成员或构造函数在任何其他包中都是不可见的。

如果一个 `public` 类具有具有包访问权限的方法或构造函数，则该方法或构造函数无法被该包之外的子类访问或继承。

例如，如果我们有：

```java
package points;

public class Class {

    public int x, y;

    void move(int dx, int dy) { x += dx; y += dy; }

    public void moveAlso(int dx, int dy) { move(dx, dy); }

}
```

那么另一个包中的子类可以声明一个具有相同签名（§8.4.2）和返回类型的无关 `move` 方法。原始的 `move` 方法在 `morepoints` 包中是不可见的，无法使用 `super`：

```java
package morepoints;

public class PlusPoint extends points.Point {

    public void move(int dx, int dy) {

        super.move(dx, dy); // 编译错误

        moveAlso(dx, dy);

    }

}
```

由于 `Point` 的 `move` 没有被 `PlusPoint` 的 `move` 覆盖，因此 `Point` 中的 `moveAlso` 方法永远不会调用 `PlusPoint` 中的 `move` 方法。因此，如果你从 `PlusPoint` 中删除 `super.move` 调用并执行测试程序：

```java
import points.Point;

import morepoints.PlusPoint;

class Test {

    public static void main(String[] args) {

        PlusPoint pp = new PlusPoint();

        pp.move(1, 1);

    }

}
```

它将终止。如果 `Point` 的 `move` 被 `PlusPoint` 的 `move` 覆盖，那么该程序将无限递归，直到发生 `StackOverflowError`。

# 示例 6.6-5. 对私有字段、方法和构造函数的访问

`private` 类成员或构造函数仅在封装该成员或构造定义的顶层类（§7.6）体内可访问。它不会被子类继承。在示例中：

```java
class Point {

    Point() { setMasterID(); }

    int x, y;

    private int ID;

    private static int masterID = 0;

    private void setMasterID() { ID = masterID++; }

}
```

私有成员 `ID`、`masterID` 和 `setMasterID` 只能在 `Point` 的体内使用。它们不能在 `Point` 声明体之外通过限定名、字段访问表达式或方法调用表达式进行访问。

参见 §8.8.10 以获得使用私有构造函数的示例。

## 6.6.2 关于保护级访问的细节

对象的 `protected` 成员或构造函数仅可以通过负责实现该对象的代码从其声明所在的包之外访问。

### 6.6.2.1 对保护级成员的访问

设 $c$ 为声明 `protected` 成员的类。只有在 $c$ 的子类 $s$ 体内允许访问。子类 $s$ 被视为负责类 $c$ 对象的实现。根据访问权限，$s$ 可能声明在与 $c$ 相同的包中，或与 $c$ 相同的模块的不同包中，或在不同的包中。

此外，根据限定名（§15.11）、方法调用表达式（§15.12）或方法引用表达式（§15.13），对实例字段或实例方法的访问允许：

- 如果是通过形式为 `ExpressionName.Id` 或 `TypeName.Id` 的限定名，则只有当限定类型为 $s$ 或其子类时，才访问实例字段 `Id`。限定类型为 `ExpressionName` 或 `Primary`，或由 `TypeName` 所表示。
- 如果是通过形式为 `ExpressionName.Id(...)` 或 `TypeName.Id(...)` 或 `Primary.Id(...)` 的方法调用表达式，或形式为 `ExpressionName::Id` 或 `Primary::Id` 或 `ReferenceType` 的方法引用表达式，则只有当限定类型为 $s$ 或其子类时，才访问实例方法 `Id`。限定类型为 `ExpressionName` 或 `Primary`，或由 `TypeName` 所表示。

关于访问保护级成员的更多信息，可以参考 Alessandro Goto 在《Journal of Object Technology》（2005年10月）发表的 *Access to Protected Members in the Java Virtual Machine*。

### 6.6.2.2 对构造访问

设 $c$ 为声明 `protected` 构造函数的类，$s$ 为使用该 `protected` 构造函数的内部类。那么：

- 如果是通过父类构造调用 `super(...)` 或限定父类构造调用 `E.super(...)`，$E$ 是一个 `Primary` 表达式，则允许访问。
- 如果是通过匿名类实例化 `new C(...)`，$E$ 是一个 `Primary` 表达式，则允许访问。
- 如果是通过类实例化 `new C(...)` 或限定类实例化 `E.new C(...)`，$E$ 是一个 `Primary` 表达式，或方法引用表达式 `C::new`，$C$ 是一个 `ClassType`，则不允许访问。`protected` 构造函数可以是定义包内的类实例化表达式（不声明任何类）或方法引用表达式。

### 6.6.2-1. 对保护级字段、方法和构造函数的访问

考虑此示例，`points` 包声明如下：

```java
package points;

public class Point {

    protected int x, y;

    void warp(threePoint.Point3d a) {

        if (a.z > 0) // 编译错误：无法访问 a.z

        a.delta(this);

    }

}
```

而 `threePoint` 包声明如下：

```java
package threePoint;

import points.Point;

public class Point3d extends Point {

    protected int z;

    public void delta(Point p) {

        p.x += this.x; // 编译错误：无法访问 p.x

        p.y += this.y; // 编译错误：无法访问 p.y

    }

    public void delta3d(Point3d q) {

        q.x += this.x;

        q.y += this.y;

        q.z += this.z;

    }

}
```



在此处的 `delta` 方法发生了编译错误：它无法访问参数 $p$ 的保护成员 $x$ 和 $y$，因为 `Point3d`（声明 $x$ 和 $y$ 的类）没有参与 `Point`（参数的类型）的实现。方法 `delta3d` 可以访问其参数 $q$ 的保护成员，因为类 `Point3d` 是 `Point` 的子类并参与了 `Point` 的实现。

`delta` 方法可以尝试将其参数 $(5.5, 15.16)$ 转换为 `Point3d`，但如果 $p$ 在运行时不是 `Point3d`，可能会失败并导致异常。

## 全限定名和规范名

在 `warp` 方法中也发生了编译错误：它无法访问参数 $a$ 的保护成员 $z$，虽然类 `Point`（出现字段 $z$ 引用的类）参与了 `Point3d`（参数 $a$ 的类型）的实现，但它不是 `Point3d`（声明 $z$ 的类）的子类。

每个基本类型、命名包、顶层类和顶层接口都有全限定名：

- 基本类型的全限定名是该基本类型的关键字，即 `byte`、`short`、`char`、`int`、`long`、`float`、`double` 或 `boolean`。
- 不是其他包类的命名包的全限定名是其简单名。
- 另一个命名包的子包命名包的全限定名由包含包的全限定名、后跟一个 `.`、然后是子包的简单（成员）名组成。
- 在未命名包中声明的顶层类或顶层接口的全限定名是类或接口的简单名。

每个成员类、成员接口和数组类型都可能有全限定名：

- 另一个类或接口 $C$ 的成员类或成员接口 $M$ 仅当 $C$ 有全限定名时具有全限定名。在这种情况下，$M$ 的全限定名由 $C$ 的全限定名后跟一个 `.` 以及 $M$ 的简单名组成。
- 数组类型仅当其元素类型有全限定名时具有全限定名。在这种情况下，数组的全限定名由组件类型的全限定名后跟 `[]` 组成。

本地类或匿名类没有全限定名。

## 全限定名与规范名

- 对于每一个基本类型、具名包、顶层类和顶层接口，其规范名与全限定名相同。每个成员类、成员接口和数组类型可能具有规范名：

- 在另一个类或接口 `c` 中声明的成员类或成员接口 `m` 具有规范名，当且仅当 `c` 具有规范名。

在这种情况下，`m` 的规范名由 `c` 的规范名后跟一个 `.`，再跟 `m` 的简单名组成。

- 数组类型具有规范名，当且仅当其组件类型具有规范名。

在这种情况下，数组类型的规范名由组件类型的规范名后跟 `[]` 组成。

局部类或匿名内部类没有规范名。

## 示例 6.7-1. 全限定名

- 类型 `long` 的全限定名是 "long"。
- 包 `java.lang` 的全限定名是 "java.lang"，因为它是包 `java` 的子包 `lang`。
- 定义在包 `java.lang` 中的类 `Object` 的全限定名是 "java.lang.Object"。
- 定义在包 `java.util` 中的接口 `Enumeration` 的全限定名是 "java.util.Enumeration"。
- 类型 "array of double" 的全限定名是 "double[]"。
- 类型 "array of array of array of array of String" 的全限定名是 `java.lang.String[][][][][]`。

在代码中：

```java
package points;

class Point { int x, y; }

class PointVec { Point[] vec; }
```

类型 `Point` 的全限定名是 "points.Point"；类型 `PointVec` 的全限定名是 "points.PointVec"；字段 `vec` 的类型 `Point[]` 的全限定名是 "points.Point[]"。

## 示例 6.7-2. 全限定名 vs 规范名

全限定名与规范名之间的区别可以通过此类看出：

`p.01.I` 和 `p.02.I` 都是表示成员 `I` 的全限定名，但只有 `p.01.I` 是它的规范名。

# 第 7 章

## 包与模块

程序被组织为包的集合。包的成员（§7.1）是类类型和接口类型（它们声明在包的编译单元中），以及子包（子包可能又包含它们自己的编译单元和子包）。

每个包都有自己的一套类型名称，这有助于防止命名冲突。包的命名结构是层次化的。

如果一组包具有足够的内聚性，那么这些包可以被组成一个模块。模块将其部分或全部包分类为导出的，这意味着从模块外部的代码可以访问它们的类型。如果一个包没有被模块导出，则只有模块内部的代码可以访问其类型。此外，如果模块中的代码想要访问另一个模块导出的包，则第一个模块必须显式地依赖第二个模块。因此，模块控制了它的包如何使用其他模块（通过指定依赖关系），以及其他模块如何使用它的包（通过指定哪些包是导出的）。

模块和包可能存储在文件系统或数据库中（§7.2）。存储在文件系统中的模块和包可能在编译单元的组织上存在某些限制，以便简单的实现能够容易地找到模块和类型声明。

编译单元中的代码自动访问其所在包中声明的所有类型，并自动导入预定义包 `java.lang` 中声明的所有 `public` 类型。

只有当顶层类型被声明为 `public` 时，它才能在声明它的包外部被访问（§6.6）。只有当顶层类型被声明为 `public` 且是导出包的成员时，它才能在声明它的模块外部被访问。被声明为 `public` 但不是导出包成员的类型仅对模块内部的代码可见。

## 7.1 包的成员

对于小型程序和临时性开发，包可以是未命名的（§7.4）或具有简单的名称，但如果代码要广泛分发，则应该使用全限定名选择唯一的包名。这可以防止当两个开发小组恰好选择了相同的包名，且这些包后来在同一个程序中使用时，原本可能发生冲突。

包的成员是它的子包，以及在包的所有编译单元（§7.3）中声明的所有顶层类类型（§7.6，类）和顶层接口类型（§9，接口）。

例如，在 Java SE Platform API 中：

- 包 `java` 有子包 `awt`、`applet`、`io`、`lang`、`net` 和 `util`，但没有编译单元。
- 包 `java.awt` 有一个名为 `image` 的子包，以及许多包含类和接口类型声明的编译单元。

如果一个包的全限定名（§6.7）是 $P$，而 $Q$ 是 $P$ 的一个子包，那么 $P.Q$ 就是该子包的全限定名，并且表示一个包。

一个包不能包含两个同名的成员，否则会导致编译时错误。

这里是一些示例：

- 包 `java.awt` 有一个子包 `image`，它不能（且没有包含）任何类类型或接口类型的声明。
- 如果存在一个名为 `mouse` 的包和一个名为 `Button` 的成员，那么就不可能存在任何名为 `mouse.Button` 的包。
- 如果 `nighthacks.java.jag` 是某个类型的全限定名，那么不能存在任何名为 `nighthacks.jag` 的包。

然而，不同包的成员可能具有相同的名称。例如，名为 `oliver` 的包与名为 `oliver.twist` 的包之间没有特殊关系。在这种情况下，名为 `oliver.twist` 的包的代码无法访问 `oliver` 中声明的类型。

```java
package vector;

public class Vector { Object[] vec; }
```

## 7.2 主机对模块和包的支持

每个系统决定模块、包和编译单元的创建和存储方式。

每个系统决定哪些编译单元是可见的（§7.3）。每个系统还决定哪些可见的编译单元与模块关联。编译单元的可见性决定了哪些模块是可见的（§7.7.3），以及模块内部哪些包是可见（§7.4.3）。

主机可以决定包含模块声明的编译单元实际上不是可见的，因此不与其声明的模块关联。这允许编译器选择模块源路径上的哪个目录“真正”是某个模块的体现。然而，如果主机确定一个包含模块声明的编译单元是可见的，那么 §7.4.3 强制该编译单元必须与其声明的模块关联，而不是与任何其他模块关联。

主机可以决定包含类型声明的编译单元（第一）是可见的且（第二）与一个未命名模块或自动模块关联——尽管在任何编译单元（无论是否可见）中都不存在未命名或自动模块的声明。

Java SE Platform 的简单实现中，包和编译单元可能存储在本地文件系统中。其他实现可能使用分布式文件系统或某些形式的数据库存储它们。

## 宿主机对模块和包的支持

如果宿主机系统使用数据库存储包和编译单元，则该数据库不能对基于文件的实现中允许的编译单元施加可选限制（§7.6）。

例如，使用数据库存储包的系统可能强制规定每个编译单元最多有一个公共类或接口。

然而，使用数据库的系统提供了一种选项，可以将程序转换为遵守这些限制的程序，以便导出到基于文件的实现中。

作为一个在文件系统中存储包的极其简单的示例，项目中的所有包以及源代码和二进制代码可能被存储在单一目录及其子目录中。该目录的每个直接子目录都代表一个顶层包，即其完全限定名由单个名称组成的包。每一层更深层次的子目录都代表其所包含目录所代表的包的子包，依此类推。

该目录可能包含以下直接子目录：

```
com
gls
jag
java
wnj
```

其中，`java` 目录包含 Java SE Platform 包；`jag`、`gls` 和 `wnj` 目录可能包含由本规范的三位作者为个人使用创建并在该小组内共享的包；而 `com` 目录包含在使用 §6.1 中描述的约定为包生成唯一名称而从他人获取的包。

继续该示例，`java` 目录包含以下子目录：

```
applet
awt
io
lang
net
util
```

对应于 Java SE Platform API 中定义的 `java.applet`、`java.awt`、`java.io`、`java.lang`、`java.net` 和 `java.util` 包。

继续该示例，如果我们查看 `util` 目录内部，可能会看到以下文件：

## 包与模块

```
BitSet.java Observable.java
BitSet.class Observable.class
Date.java Observer.java
Date.class Observer.class
..
```

其中每个 `.java` 文件包含编译单元（§7.3）的源码，该编译单元包含一个类或接口的定义，其二进制编译形式包含在相应的 `.class` 文件中。

在这种简单的包组织结构下，Java SE Platform 的实现将通过连接包名的各个组件，将包名转换为路径名，在相邻组件之间放置文件名分隔符（目录指示符）。

例如，如果这种简单的组织被用于文件名分隔符为 `/` 的操作系统，则包名：

```
jag.scrabble.board
```

将转换为目录名：

```
jag/scrabble/board
```

包名组件或类名可能包含一个无法正确出现在宿主机文件系统普通目录名中的字符，例如在仅允许文件名使用 ASCII 字符的系统上的 Unicode 字符。作为一种约定，可以使用转义字符进行转义，例如使用 `#` 字符后跟四个十六进制数字来给出该字符的数值，如 `\uxxxx` 转义（§3.3）所示。

在该约定下，包名：

```
children.activities.crafts.papier,h\u00e9
```

它也可以使用完整的 Unicode 写法为：

```
children.activities.crafts.papierMé
```

可能会映射到目录名：

```
children/activities/crafts/papierM#00e9
```

如果对于给定的宿主机文件系统，`#` 字符不是有效的有效字符，则可以使用另一个在标识符中无效的字符来代替。

## 7.3 编译单元

`CompilationUnit` 是 Java 程序语法规则（§2.3）的目标符号（§2.1）。它由以下产生式定义：

```
CompilationUnit:
    OrdinaryCompilationUnit
    ModularCompilationUnit

OrdinaryCompilationUnit:
    [PackageDeclaration] [ImportDeclaration] [TypeDeclaration]

ModularCompilationUnit:
    [ImportDeclaration] ModuleDeclaration
```

一个普通编译单元由三部分组成，每部分都是可选的：

- 包声明（§7.4），给出该编译单元所属包的完全限定名（§6.7）。
- 没有包声明的编译单元属于一个未命名的包（§7.4.2）。
- 导入声明（§7.5），允许使用简单名称引用其他包中的类型以及类型的静态成员。
- 类类型和接口类型的顶层类型声明（§7.6）。

一个模块编译单元由一个模块声明（§7.7）组成，前面可选地带有导入声明。导入声明允许在模块声明中使用简单名称引用该模块及其他模块中包的类型，以及类型的静态成员。

每个编译单元都会导入预定义包 `java.lang` 中声明的所有公共类型名称，仿佛在编译单元的开头、任何包声明之后立即出现了 `import java.lang.*;`。结果是，所有这些类型的名称在每个编译单元中都可以作为简单名称可用。

宿主机决定哪些编译单元是可见的，但预定义包 `java` 及其子包 `lang` 和 `io` 中的编译单元除外，它们总是可见的。

每个可见的编译单元可以与一个模块关联，如下：

宿主机可以确定一个可见的普通编译单元与宿主机选择的模块关联，但 (i) 预定义包 `java` 及其子包 `lang` 和 `io` 中的普通编译单元（它们都与 `java.base` 模块关联）以及 (ii) 任意普通编译单元除外。

## 7.4 包声明

包声明出现在普通编译单元中，用于指示编译单元所属的包。

### 7.4.1 命名包

普通编译单元中的包声明指定所属包的名称（§6.2）。

```
PackageDeclaration:
    {PackageModifier} package Identifier { . Identifier } ;

PackageModifier:
    Annotation
```

包声明中提到的包名必须是包的完全限定名（§6.7）。

包声明的作用范围和遮蔽在 §6.3 和 §6.4 中规定。

包声明上注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

对于给定的包，允许注解包声明。

强制此限制的方法必然取决于具体的实现方式。对于基于文件的实现，强烈建议采用以下方案：注解包声明如果存在，则位于包含包源文件的目录中的名为 `package-info.java` 的文件中。该文件不包含名为 `package-info` 的类的源码；这样做是违法的，因为 `package-info` 不是合法的标识符。`package-info.java` 只包含一个包声明，其紧跟在包的注解之后。虽然该文件技术上可以包含一个或多个具有包访问权限的类的源码，但是非常糟糕的做法。

建议 `package-info.java` 如果存在，则作为 javadoc 和其他文档生成系统中 `package-info.html` 的位置。如果该文件存在，文档生成工具应该查找 `package-info.java` 中（可能带有注解的）包声明。通过这种方式，`package-info.java` 成为包级注解和文档的唯一存储库。如果未来需要添加任何其他包级信息，该文件应为这些信息提供方便的存放处。

### 7.4.2 未命名包

一个没有包声明但至少包含另一种类型声明的普通编译单元，属于一个未命名包的一部分。

Java SE 平台提供未命名包，主要为了在开发小型或临时应用程序，或者在刚开始开发时提供便利。

未命名包不能有子包，因为包声明的语法始终包含对一个命名顶层包的引用。

Java SE 平台的实现必须至少支持一个未命名包。实现可以支持多个未命名包，但并非强制要求。每个未命名包包含哪些普通编译单元由宿主系统决定。

宿主系统必须将未命名包中的普通编译单元与一个未命名模块（§7.7.5）关联，而不是命名模块。

## 示例 7.4.2-1. 未命名包

该编译单元：

```java
class FirstCall {

    public static void main(String[] args) {

        System.out.println("Mr. Watson, come here." 
                                            + "I want you.");

    }

}
```



定义了一个非常简单的编译单元，作为未命名包的一部分。

在使用层次级文件系统存储包的 Java SE 平台实现中，每个目录一次只能观测到一个未命名包，即与“当前工作目录”关联的那个包。“当前工作目录”的精确含义取决于宿主系统。

## 7.4.3 包的可观测性与可见性

当且仅当以下条件至少一个成立时，包是可观测的：

- 包含该包声明的普通编译单元是观测的（§7.3）。
- 该包的子包始终是观测的。

包 `java`、`java.lang` 和 `java.io` 始终是观测的。

## 导入声明

根据上述规则以及其他关于可观测编译单元的规则，可以得出结论。预定义包 `java.lang` 声明了 `Object`，因此 `Object` 的编译单元始终是可观测的（§7.3）。因此，`java.lang` 包是观测的，`java` 包也是观测的。此外，由于 `Object` 是观测的，数组类型 `Object[]` 隐式存在。它的超接口 `java.io.Serializable` (§10.1) 也存在，因此 `java.io` 包是观测的。

当且仅当任何包含该包声明的普通编译单元对模块 M 可见时，该包对模块 M 是可见的。

可见性意味着一个包以一种对模块有用的方式是可观测的。如果仅仅因为子包 Q 是观测的就认为包 P 是可观测的，通常是没用的。例如，假设 Q（在模块 M1 中）是观测的，且 P.R（在模块 M2 中）是观测的；那么 P 是可观测的，但在哪里呢？在 M1、M2 还是两者中？这是冗余的；在编译模块 N 时，只需要 M1，Q 是否可观测很重要，但 P 是否可观测并不重要。

当且仅当满足以下条件之一时，一个包对模块 M 是唯一可见的：

- 与 M 关联的普通编译单元包含该包的声明，且 M 没有读取任何向 M 导出该包的其它模块。
- 与 M 关联的普通编译单元不包含该包的声明，且 M 恰好读取了向 M 导出该包的另一个模块。

## 7.5 导入声明

导入声明允许通过由单个标识符组成的简单名称（§6.2）来引用命名类型或静态成员。

在不使用适当的导入声明的情况下，引用另一个包中声明的类型或另一个类型的静态成员的唯一方法是使用完全限定名（§6.7）。

```
ImportDeclaration:
    SingleTypeImportDeclaration
    TypeImportOnDemandDeclaration
    StaticImportDeclaration
    StaticImportOnDemandDeclaration
```

- 单类型导入声明（§7.5.1）通过提及其规范名（§6.7）导入单个命名类型。
- 按需类型导入声明通过提及其规范名导入该包下的所有类型。
- 单静态导入声明通过提及其规范名导入所有可访问的静态成员。
- 按需静态导入声明通过提及其规范名导入所有可访问的静态成员。

导入声明允许通过简单名称引用命名类型或静态成员，该简单名称由单个标识符组成。在不使用适当的导入声明的情况下，引用另一个包中声明的类型或另一个类型的静态成员的唯一方法是使用完全限定名（§6.7）。

## 7.5.1 单类型导入声明

单类型导入声明（§7.5.1）通过提及其规范名（§6.7）导入单个命名类型。

```java
SingleTypeImportDeclaration:
    import Name;
```

`Name` 必须是类类型、接口类型、枚举类型或注解类型（§6.7）。

一个与 M 关联的普通编译单元包含该包的声明，且 M 没有读取任何向 M 导出该包的其它模块。

与 M 关联的普通编译单元不包含该包的声明，且 M 恰好读取了向 M 导出该包的另一个模块。

（注：由于提供的原始文本中关于 7.5 导入声明部分的描述存在逻辑重复和错乱，翻译时已根据 Markdown 结构进行了对齐和去处理。）

## 包与模块

```java
import java.util;

class Test { util.Random generator; }

// 错误：编译时错误
```

## 7.5.1-4. 导入与包名相同的类型名称

在 §6.1 节描述的命名约定下，包名和类型名通常是不同的。尽管如此，在一个构造的示例中，其中有一个命名不符合常规的包 `Vector`，它声明了一个名为 `Mosquito` 的公类：

```java
package Vector;

public class Mosquito { int capacity; }
```

然后是该编译单元：

```java
package strange;

import java.util.Vector;
import Vector.Mosquito;

class Test {
    public static void main(String[] args) {
        System.out.println(new Vector().getClass());
        System.out.println(new Mosquito().getClass());
    }
}
```

这种从 `java.util` 包导入类 `Vector` 的单个导入声明，并阻止包名 `Vector` 在随后的导入声明中出现并被正确识别。该示例可以编译并产生以下输出：

```
class java.util.Vector
class Vector.Mosquito
```

## 7.5.2 按需导入类型的声明

按需导入类型声明允许根据需要导入命名包或类型中所有可访问的类型。

```
TypeImportOnDemandDeclaration:
    import PackageOrTypeName *;
```

`PackageOrTypeName` 必须是包、类类型、接口类型、枚举类型或注解类型的规范名称 (§6.7)。

如果 `PackageOrTypeName` 指向一个类型 (§6.5.4)，则该类型必须是命名包的成员，或者是某个类型的成员且该类型最外层词法包含的类型声明 (§8.1.3) 是某个命名包的成员，否则将发生编译时错误。

## 导入声明

如果命名包对当前模块 (§7.4.3) 不是唯一可见的，或者命名类型不可访问 (§6.6)，则会发生编译时错误。

在按需导入类型的声明中命名 `java.lang` 或当前编译单元的命名包并不是编译时错误。在这种情况下，按需导入类型的声明将被忽略。

同一个编译单元中的两个或多个按需导入类型声明可以命名相同的类型或包。但这些声明中的任何一个都被认为是冗余的；其效果相当于该类型仅被导入了一次。

如果一个编译单元同时包含命名相同类型的按需导入类型声明和静态按需导入类型声明 (§7.5.4)，其效果相当于该类型的静态成员 (§8.5, §9.5) 仅被导入了一次。

## 7.5.2-1. 按需导入类型

```java
import java.util.*;
```

这会导致在 `java.util` 包中声明的所有公有类型名称在编译单元的类和接口声明中变为可用。因此，在编译单元中所有类型声明未被遮蔽 (§6.4.1) 或模糊化 (§6.4.2) 的地方，简单名 `Vector` 都指向包 `java.util` 中的类型 `Vector` 类型。

该声明可能被一个简单名为 `Vector` 的单类型导入声明所遮蔽；被一个在当前编译单元所属包中声明且名为 `Vector` 的类型所遮蔽；或者被任何嵌套类或接口所遮蔽。

该声明可能被名为 `Vector` 的字段、参数或局部变量的声明所模糊化。

（这些条件中的任何一种发生是不常的。）

## 7.5.3 单静态导入声明

单静态导入声明从一个类型中导入具有给定简单名的所有可访问静态成员。这使得在该单静态导入声明出现的编译单元的模块、类和接口声明中，这些静态成员以其简单名的形式可用。

```
SingleStaticImportDeclaration:
    import static TypeName . Identifier
```

`TypeName` 必须是类类型、接口类型、枚举类型或注解类型的规范名称 (§6.7)。

类型必须是命名包的成员，或者是某个类型的成员且该类型最外层词法包含的类型声明 (§8.1.3) 是某个命名包的成员，否则会发生编译时错误。类型不可访问 (§6.6)，则发生编译时错误。

`Identifier` 必须是该类型的至少一个静态成员。如果所有静态成员不可访问，则会发生编译时错误。

允许一个单静态导入声明导入多个具有相同名称的字段或类型。这发生在命名类型从父类继承了具有相同名称的字段、成员类型或方法时。

同一个编译单元中的两个单静态导入声明尝试导入相同名称的类型，会发生编译时错误，除非它们是相同的类型，在这种情况下重复声明将被忽略。

如果单静态导入导入了名为 `n` 的类型，且编译单元也声明了名为 `n` 的顶层类型（§7.6），则会发生编译时错误。

如果一个编译单元同时包含导入相同类型的单静态导入声明和按需导入类型声明（§7.5.2），其效果相当于该类型的静态成员仅被导入了一次。

## 7.5.4 静态按需导入声明

静态按需导入声明允许根据需要导入命名类型中所有可访问的静态成员。

```
StaticImportOnDemandDeclaration:
    import static TypeName . *
```

`TypeName` 是类类型、接口类型、枚举类型或注解类型的规范名称 (§6.7)。

类型必须是命名包的成员，或者是某个类型的成员且该类型最外层词法包含的类型声明 (§8.1.3) 是某个命名包的成员，否则会发生编译时错误。

如果命名类型不可访问（§6.6），则发生编译时错误。

## 7.6 顶层类型声明

同一个编译单元中的两个或多个静态按需导入声明可以命名相同的类型；其效果相当于存在这样一个声明。

同一个编译单元中的两个或多个静态按需导入声明可以命名相同的成员；其效果相当于该成员仅被导入了一次。

允许一个静态按需导入声明导入多个具有相同名称的字段或类型，或具有相同名称签名的方法。这发生在命名类型从父类继承了具有相同名称的字段、成员类型或方法时。

顶层类型声明声明一个顶层类型（§8 (类)）或顶层接口类型（§9 (接口)）。

```
TypeDeclaration:
    ClassDeclaration;
    InterfaceDeclaration;
```

在编译单元的类型声明层级出现的多余 `;` 令牌对编译单元的含义没有影响。Java 编程语言允许出现散乱的分号纯粹是为了让 C++ 程序员，他们习惯在类声明后放置 `;`。在 Java 代码中不应使用它们。

在没有访问修饰符的情况下，顶层类型具有包访问权限：它仅在声明所在的包的普通编译单元（§6.6.1）中是可访问的。类型可以声明为 `public`，以允许同一模块内其他包的代码访问该类型。

如果顶层类型声明包含以下任何一个访问修饰符：`protected`、`private` 或 `static`，则会发生编译时错误。

如果顶层类型的名称出现在同一包内声明的另一个顶层类或接口类型的名称中，则会发生编译时错误。

# 软件包与模块

# 顶层类型声明

顶层类型的作用范围和遮蔽在 §6.3 和 §6.4 中规定。

顶层类型的完全限定名在 §6.7 中规定。

## 示例 7.6-1. 冲突的顶层声明

```java
package test;

import java.util.Vector;

class Point {
    int x,
    y;
}

interface Point { // 编译错误 #1
    int getR();
    int getTheta();
}

class Vector { Point[] pts; } // 编译错误 #2
```

在这里，第一个编译错误是由在同一个包中将名称 `Point` 同时声明为类和接口的重复声明引起的。第二个编译错误是尝试将名称 `Vector` 同时声明为类声明和单类型导入。

然而，请注意，如果一个类在包含该类声明的编译单元中，名称与另一个可能通过按需类型声明（§7.5.2）导入的类型相同，这并不是一个错误。因此，在程序中：

```java
package test;

import java.util.*;

class Vector { // 不是编译时错误
```

尽管存在类 `java.util.Vector`，但对类 `Vector` 的声明是被允许的。在该编译单元内，简单名 `Vector` 指向类 `test.Vector`，而不是 `java.util.Vector`（仍然可以通过编译单元内的代码引用，但必须通过其完全限定名引用）。

## 示例 7.6-2. 顶层类型的作用范围

```java
package points;

class Point {
    int x, y; // 坐标
    PointColor color; // 此点的颜色
    Point next; // 该颜色的下一个点
    static int nPoints;
}

class PointColor {
    Point first; // 该颜色的第一个点
    PointColor(int color) { this.color = color; }
    private int color; // 颜色分量
}
```

该程序定义了两个在类成员声明互相使用的类。由于类类型 `Point` 和 `PointColor` 将包 `points` 中的所有类型声明（包括当前编译单元中的所有声明）作为其作用范围，因此该程序可以正确编译。也就是说，前向引用不是问题。

## 示例 7.6-3. 完全限定名

```java
class Point { int x, y; }
```

在这段代码中，类 `Point` 声明在一个没有包声明的编译单元中，因此 `Point` 是它的完全限定名。而在下面的代码中：

```java
package vista;

class Point { int x, y; }
```

类 `Point` 的完全限定名是 `vista.Point`。（包名 `vista` 适用于本地或个人使用：如果该包旨在广泛分发，最好给它起一个唯一的包名（§6.1））

Java SE 平台的实现必须通过其封装模块名称和二进制名称的组合（§13.1）来跟踪包中的类型。命名类型的多种方式必须被扩展为二进制名称，以确保这些名称被理解为指向同一种类型。

例如，如果一个编译单元包含单类型导入声明（§7.5）：

```java
import java.util.Vector;
```

那么在编译单元内，简单名 `Vector` 和完全限定名 `java.util.Vector` 指向同一种类型。

当且仅当包存储在文件系统中（§7.2）时，主机系统可能选择强制执行限制：如果满足以下任一情况，如果类型不在一个名为类型名加扩展名（如 `.java` 或 `.jav`）的文件中，则为编译错误：

- 该类型被声明该类型的包中的其他普通编译单元的代码引用。
- 该类型被声明为 `public`（因此可能从其他包的代码中访问）。

此限制意味着每个编译单元中最多有一个这样的类型。此限制使得 Java 编译器能够轻松地找到包内的命名类。在实践中，许多程序员选择将每个类或接口类型放在它们单独的编译单元中，无论它们是否为 `public` 或是否被其他编译单元的代码引用。

例如，公共类型 `wet.srocket.Toad` 的源代码可以在 `wet/srocket` 目录下的 `Toad.java` 文件中找到，相应的对象代码可以在同一目录下的 `Toad.class` 文件找到。

# 7.7 模块声明

模块声明指定了一个新模块。命名模块指定了对其他模块的依赖，以定义自身代码可用的类和接口宇宙；并指定它的哪些包被导出或打开，以填充指定依赖它的其他模块可用的类和接口宇宙。

> “依赖”是 `requires` 指令所表达的内容，与是否存在名为指令指定的模块无关。“依赖项”是 `requires` 指令通过解析（如 `java.lang.module` 包规范中所述）列出的可观测模块。通常，Java 编程语言的规则更关注依赖关系而非依赖项。

```
ModuleDeclaration:
    [Annotation] [open] module Identifier { .Identifier }
    { {ModuleDirective} }
```



模块声明引入了一个模块名称，该名称可以在其他模块声明中使用，以表示模块之间的关系。模块名称由一个或多个由 `.` 标记隔开的 Java 标识符（§3.8）组成。

模块有两种类型：普通模块和开放模块。模块的类型决定了对模块导出包的访问性质。带有 `open` 修饰符的普通模块在编译时仅限授予对那些显式导出的包的访问权限。带有 `open` 修饰符的开放模块在编译时仅授予对那些显式导出或打开（或两者兼有）的包的访问权限。

与编译时访问和运行时访问不同，Java SE 平台通过核心反射 API（§1.4）提供反射访问。普通模块仅对其导出的包授予反射访问。如果所有包都已打开，则开放模块对其所有包授予反射访问。

对于普通模块外部的代码，授予其模块导出（但未打开）的包中类型的反射访问权限特地针对这些包中的 `public` 和 `protected` 类型。对于开放模块外部的代码，授予其模块打开的包（无论是否导出）中类型的反射访问权限特地针对这些包中的所有类型，以及这些类型的所有成员。模块内部的代码享有对模块内所有包中所有类型和所有成员的反射访问权限。

## 包与模块

## 模块声明

### 7.7

为了便于理解，按照惯例（并非强制），模块声明会将其指令分组，这样与模块相关的 `requires` 指令在视觉上就会与包相关的 `exports` 和 `opens` 指令，以及与服务相关的 `uses` 和 `provides` 指令区分开来。例如：

```java
module com.example.foo {

    requires com.example.foo.http;

    requires java.logging;

    requires transitive com.example.foo.network;

    exports com.example.foo.bar;

    exports com.example.foo.internal to com.example.foo.probe;

    opens com.example.foo.qux;

    opens com.example.foo.internal to com.example.foo.network,
        com.example.foo.probe;

    uses com.example.foo.spi.Intf;

    provides com.example.foo.spi.Intf with com.example.foo.Impl;

}
```

模块中可以修改 `opens` 依赖：

```java
open module com.example.foo {

    requires com.example.foo.http;

    requires java.logging;

    requires transitive com.example.foo.network;

    exports com.example.foo.bar;

    exports com.example.foo.internal to com.example.foo.probe;

    uses com.example.foo.spi.Intf;

    provides com.example.foo.spi.Intf with com.example.foo.Impl;

}
```

Java 语言开发工具鼓励高亮 `transitive` 指令和未限定的 `exports` 指令，因为它们构成了模块的主要 API。

### 7.7.1 依赖

`requires` 指令指定当前模块所依赖的模块名称。

`java.base` 模块的声明中不允许出现 `requires` 指令，否则会导致编译错误，因为它是原始模块且没有依赖 (§8.1)。

如果模块声明没有表示对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，则对 `java.base` 有隐式依赖。

`requires` 关键字后面可以跟随 `transitive` 修饰符。这表示该依赖在编译时是强制的，但在运行时是可选的。

`requires` 关键字后面可以跟随 `static` 修饰符。这表示该依赖在编译时是可选的，但在运行时是强制的。

如果模块声明表示对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，那么在 `requires` 之后出现指令会导致编译错误。

如果模块声明中有多个指令指定同一个模块名称，则会导致编译错误。

如果 `requires` 指令指定的模块不可观测，或者当前模块直接或间接地表示对自身的依赖，则根据 `java.lang.module` 包规范描述，解析将失败。

如果解析成功，其结果指定了当前模块所读取的模块。当前模块读取的模块决定了哪些编译单元对当前模块是可见的 (§7.3)。这些编译单元中的类型（仅限这些编译单元）当前模块可以访问 (§6.6)。

实际上，一个模块可以通过多层依赖读取另一个模块，以支持任意数量的重构。一个模块发布供他人重用（通过 `requires`），模块作者已对其名称和 API 做出承诺，并可以自由将其内容重构成其他模块（通过 `requires transitive`），以供消费者受益。在上面的示例中，包 `p` 可能由 `m.b` 导出（因此 `m.a` `requires m.b`），但重构导致 `m.b` 的部分内容移动到了 `m.c` 和 `m.d`。通过使用 `transitive` 指令链，`m.b`、`m.c` 和 `m.d` 的第一个可以在不更改 `m.a` 的 `requires` 指令的情况下，保留 `m.a` 代码对包 `p` 的访问。注意，`m.d` 中的包 `p` 并不是由 `m.c` 和 `m.b` “重新导出”的；而是让 `m.a` 直接读取 `m.d`。

### 导出与打开包

`exports` 指令指定当前模块要导出的包名。对于其他模块的代码，这允许在编译时间和运行时访问该包中的公共和受保护类型，以及类的公共和受保护成员。它还允许其他模块对这些类型和成员进行反射访问。

`opens` 指令指定当前模块要打开的包名。对于其他模块的代码，这允许在运行时（而非编译时）访问该包中的公共和受保护类型，以及公共和受保护成员。它还允许其他模块对包中的所有类型和成员进行反射访问。

如果 `exports` 指定的包未在当前模块编译单元中声明，则会导致编译错误（§7.3）。

允许 `opens` 指定未在当前模块编译单元中声明的包。（如果该包恰好在另一个可观测编译单元中声明，则 `opens` 指令对该模块没有影响）。

### 示例 7.1.1-1. requires transitive 的解析

假设有以下四个模块声明：

```java
module m.a {

    requires m.b;

}
```

```java
module m.b {

    requires transitive m.c;

}
```

```java
module m.c {

    requires transitive m.d;

}
```

```java
module m.d {

    exports p;

}
```

其中 `m.d` 导出的包 `p` 声明如下，且 `m.a` 模块中的 `client` 包引用了导出包 `p` 中的 `Point` 类型：

```java
package client;

import p.Point;

public class Test {

    public static void main(String[] args) {

        System.out.println(new Point());

    }

}
```

假设当前目录为每个模块有一个同名的子目录，可以如下编译编译模块：

```bash
javac --module-source-path -d --module.d

javac --module-source-path -d --module.c

javac --module-source-path -d --module.b

javac --module-source-path -d --module.a
```

如下所示运行程序 `client.Test`：

```bash
java --module-path --module m.a/client.Test
```



`m.a` 代码到 `m.d` 中导出公共类型 `Point` 的引用是合法的，因为 `m.a` 读取了 `m.d`，且 `m.d` 导出包 `Point`。解析 `m.a` 读取 `m.d` 的过程如下：

- `m.a` `requires m.b`，因此读取 `m.b`。
- 由于 `m.a` 读取 `m.b`，且 `m.b` `requires transitive m.c`，解析确定 `m.a` 读取了 `m.c`。
- 随后，由于 `m.a` 读取 `m.c`，且 `m.c` `requires transitive m.d`，解析确定 `m.a` 读取了 `m.d`。

实际上，一个模块可以通过多层依赖读取另一个模块，并支持任意数量的重构。一个模块发布供他人重用（通过 `requires`），模块作者已对其名称和 API 做出承诺，并可以自由将其内容重构成其他模块，原始模块通过 `requires transitive` 重用这些模块以造消费者。在上面的示例中，包 `p` 可能由 `m.b` 导出（因此 `m.a` `requires m.b`），但重构导致 `m.b` 的部分内容移动到了 `m.c` 和 `m.d`。通过使用 `transitive` 指令链，`m.b`、`m.c` 和 `m.d` 的第一个可以在不更改 `m.a` 的 `requires` 指令的情况下，保留 `m.a` 代码对包 `p` 的访问。注意，`m.d` 中的包 `p` 并不是由 `m.c` 和 `m.b` “重新导出”的；而是让 `m.a` 直接读取 `m.d`。

### 7.7.2 导出包与打开包

如果 `exports` 或 `opens` 指令带有 `to` 子句，则该指令是限定的；否则，它是未限定的。对于限定的指令，包中的 `public` 和 `protected` 类型以及它们的 `public` 和 `protected` 成员仅可供 `to` 子句中指定的模块的代码访问。`to` 子句中指定的模块被称为当前模块的友元。对于未限定的指令，这些类型及其成员可被任何模块的代码访问。

`exports` 或 `opens` 指令的 `to` 子句允许指定一个不可见的模块（§7.7.6）。

如果给定的 `exports` 指令的 `to` 子句多次指定同一个模块名，则为编译错误。

如果给定的 `opens` 指令的 `to` 子句多次指定同一个模块名，则为编译错误。

### 7.7.3 服务消费

`uses` 指令指定一个服务，当前模块可以通过 `java.util.ServiceLoader` 发现该服务的提供者。

该服务必须是类类型、接口类型或注解类型。如果 `uses` 指令指定枚举类型（§8.9）作为服务，则为编译错误。

该服务可以在当前模块中声明，也可以在另一个模块中声明。如果服务未在当前模块中声明，则该服务对当前模块的代码可见（§6.6），否则将发生编译错误。

如果模块声明中存在多个 `uses` 指令指定了同一个服务，则为编译错误。

### 7.7.4 服务提供

`provides` 指令指定一个服务，其 `with` 子句为 `java.util.ServiceLoader` 指定一个或多个服务提供者。

该服务必须是类类型、接口类型或注解类型。如果 `provides` 指令指定枚举类型（§8.9）作为服务，则为编译错误。

该服务可以在当前模块中声明，也可以在另一个模块中声明。如果服务未在当前模块中声明，则该服务对当前模块的代码可见（§6.6），否则将发生编译错误。

每个服务提供者必须是类类型或接口类型，且是 `public` 的，并是顶层或嵌套静态的，否则将发生编译错误。

每个服务提供者必须在当前模块中声明，否则将发生编译错误。

如果服务提供者显式声明了一个没有形式参数的 `public` 构造方法，或隐式声明了 `public` 默认构造方法（§8.8.9），则该构造方法被称为提供者构造方法。

如果服务提供者显式声明了一个没有形式参数的名为 `provider` 的 `public static` 方法，则该方法被称为提供者方法。

如果服务提供者拥有提供者方法，则其返回类型 (i) 要么在当前模块声明，要么在另一个模块声明且对当前模块的代码可见；且 (ii) 是 `provides` 指令中指定的服务的子类型；否则将发生编译错误。

> 虽然由 `provides` 指令指定的服务必须在当前模块中声明，但其提供者方法的返回类型可以在另一个模块中声明。此外，并非当服务提供者声明提供者方法时，服务提供者才必须是该服务的子类型。

如果服务提供者没有提供者方法，则服务提供者必须有一个提供者构造方法，并且必须是 `provides` 指令中指定的服务的子类型，否则将发生编译错误。

如果模块声明中存在多个 `provides` 指令指定了同一个服务，则为编译错误。

如果给定的 `provides` 指令的 `with` 子句多次指定同一个服务提供者，则为编译错误。

### 7.7.5 无命名模块

宿主系统未与命名模块关联（§7.3）的可观察编译单元将与一个无命名模块关联。

Java SE 平台提供无命名模块，是为了承认 Java 9 之前开发的程序无法声明命名模块的事实。此外，Java SE 平台提供无命名包（§7.4.2）的原因很大程度上也适用于无命名模块。

Java SE 平台的实现必须支持至少一个无命名模块。实现可以支持多个无命名模块，但不是必须。哪些普通编译单元与每个无命名模块关联由宿主系统决定。

宿主系统可以将命名包中的普通编译单元与无命名模块关联。

无命名模块的规则旨在最大化地提高它们与命名模块的互操作性，如下：

- 无命名模块读取每个可观察模块（§7.7.6）。

### 7.7.6 模块的可见性

编译单元如果满足以下条件是可见的：

- 它是命名模块中的普通编译单元。
- 它是无命名模块中的普通编译单元。
- 它是命名模块中的 `public` 或 `protected` 类型（或成员）。
- 它被 `opens` 指令指定。

## 8.1 类声明

类声明指定了一个新的命名引用类型。

类声明有两种：*普通类声明*和*枚举声明*。

```
ClassDeclaration:
    NormalClassDeclaration
    EnumDeclaration
```

```
NormalClassDeclaration:
    [ClassModifier] class TypeIdentifier [TypeParameters]
    [Superclass] [SuperInterfaces] ClassBody
```

本节中的规则适用于所有类声明，包括枚举声明。然而，对于枚举声明，在类修饰符、内部类和超类方面有特殊的规则适用；这些规则在 §8.9 中进行了规定。

类声明中的 *TypeIdentifier*（类型标识符）指定类的名称。

如果一个类与它的任何嵌套类或接口同名，则会产生编译时错误。

类声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

### 8.1.1 类修饰符

类声明可以包含*类修饰符*。

```
ClassModifier:
    (其之一一)
    Annotation
    public
    protected
    private
    abstract
    static
    final
    strictfp
```

类声明上的注解修饰符规则规定在 §9.7.4 和 §9.7.5。

访问修饰符 `public`（§6.6）仅适用于顶层类（§7.6）和成员类（§8.5），不适用于局部类（§14.3）或匿名类（§15.9）。

访问修饰符 `protected` 和 `private` 仅适用于直接嵌套在类声明（§8.5）内的成员类。

修饰符 `static` 仅适用于成员类（§8.5），不适用于顶层类、局部类或匿名类。

如果同一个关键字作为类声明的修饰符出现多次，或者一个类声明具有多个一个 `public`、`protected` 和 `private` 访问修饰符之一（§6.6），则会产生编译时错误。如果一个类声明中出现两个或多个（不同的）类修饰符，按照习惯（也是要求的），它们必须按照与上述 `ClassModifier` 产生式中所示一致的顺序出现。

#### 8.1.1.1 abstract 抽象类

抽象类是一个不完整的或被认为是不完整的类。如果尝试使用类表达式（§15.9）创建抽象类的实例，则会产生编译时错误。抽象类的非抽象子类可以被实例化，这将导致抽象类构造函数的执行，从而执行该类实例变量的字段初始化器。

普通类可以拥有已声明但未实现的抽象方法（§8.4），但前提是它本身是一个抽象类。如果以下任一条件为真，则类 `c` 具有抽象方法：

- `c` 的任何成员方法——无论是声明的还是继承的——都是抽象的。
- `c` 的任何超类都有一个以包访问权限声明的抽象方法，且没有方法可以覆盖来自 `c` 的超类中的该抽象方法。

如果无法创建一个实现其所有抽象方法的子类，则声明抽象类将产生编译时错误。这种情况可能发生在该类具有具有相同签名（§8.2）但返回类型不可替换的（§8.5）的抽象方法时。

##### 示例 8.1.1.1. 抽象类声明

```java
class Point {
    int x = 1, y = 1;
    void move(int dx, int dy) {
        x += dx;
        y += dy;
    }
}
```

```java
class Point {
    abstract void alert();
}

abstract class ColoredPoint extends Point {
    int color;
}

class SimplePoint extends Point {
    void alert() { }
}
```

在这里，声明的类 `Point` 必须声明为抽象的，因为它包含一个名为 `alert` 的抽象方法的声明。`Point` 的子类 `ColoredPoint` 继承了抽象方法 `alert`，因此它也必须声明为抽象的。相反，`Point` 的子类 `SimplePoint` 提供了 `alert` 的实现，因此不需要声明为抽象的。语句：

```java
Point p = new Point();
```

将导致编译错误；类 `Point` 不能实例化，因为它是抽象的。`Point` 变量可以被指向 `Point` 的任何子类的引用正确地初始化，且类 `SimplePoint` 不是抽象的，因此语句：

```java
Point p = new SimplePoint();
```

是正确的。`SimplePoint` 的实例化会导致 `Point` 的默认构造函数以及 `x` 和 `y` 的初始化器被执行。

##### 示例 8.1.1.2. 抽象类声明禁止子类

```java
interface Colorable {
    void setColor(int color);
}

abstract class Colored implements Colorable {
    public abstract int setColor(int color);
}
```

这些声明将导致编译错误；任何 `Colored` 的子类都不可能提供名为 `setColor` 的方法的实现，该方法需要接受任何能够满足两个抽象方法规范的类型的参数，因为 `Colorable` 中的要求方法不返回值，而 `Colored` 中的要求方法返回一个 `int` 类型的值（§8.4）。

类类型应仅在意图允许子类声明以完成实现时，才声明为抽象的。如果意图是防止类的实例化，正确的表达方法是声明一个无参数的构造函数（§8.10），将其设为私有，永远不调用它，并且不声明其他构造函数。这种形式的类通常包含类方法和变量。

`Math` 类是一个无法实例化的类示例；它的声明看起来如下：

```java
public final class Math {
    private Math() { // 永远不要实例化此类
    }
    // 类变量的声明
}
```

#### 8.1.1.2 final 类

如果类的定义是完整的且不需要子类，则可以将其声明为 `final`。

如果 `final` 类名出现在另一个类的 `extends` 子句（§8.1）中，则会产生编译时错误；这意味着 `final` 类没有任何子类。

由于 `final` 类没有任何子类，其方法从不重写（§8.4）。

#### 8.1.1.3 strictfp 类

`strictfp` 修饰符的作用是使类内部所有的浮点或双精度表达式（包括变量初始化器、实例化初始化器、静态初始化器和构造函数）以及类中声明的所有方法和嵌套类型都是隐式的 `strictfp`。

### 8.1.2 泛型类和类型参数

如果一个类声明了一个或多个类型变量（§4.4），则该类是泛型的。

这些类型变量被称为类的类型参数。类型参数位于类名之后，并用角括号分隔。

```
TypeParameters:
    <TypeParameterList>
```

```
TypeParameterList:
    TypeParameter (, TypeParameter)*
```

为了方便起见，这里显示了来自 §4.4 的产生式：

```
TypeParameter:
    [TypeParameterModifier] TypeIdentifier [TypeBound]
TypeParameterModifier:
    Annotation
TypeBound:
    extends ClassOrInterfaceType [AdditionalBound]
AdditionalBound:
    & InterfaceType
```



## AdditionalBound

& InterfaceType

类型参数声明上的注解修饰符规则规定在 §9.7.4 和 §9.7.5。

在类的类型参数部分中，如果 `s` 是 `τ` 的边界，则 `τ` 直接依赖于 `s`，而如果 `τ` 直接依赖于 `s` 或 `τ` 依赖于一个依赖于 `s` 的 `U`（递归地使用此定义）。如果类的类型参数部分中的变量依赖于自身，则会产生编译时错误。

类类型参数的作用域和遮蔽在 §6.3 和 §6.4 中规定。

泛型类声明定义了一组参数化类型 (§4.5)，对于类型参数部分的每种可能的参数化方式都有。所有这些参数化类型在运行时共享同一个类。

例如，执行代码：

```java
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致变量 `b` 持有真值。

如果泛型类是 `Throwable` 的直接或间接子类 (§11.1.1)，则会产生编译时错误。这种限制是必要的，因为 Java 虚拟机的捕获机制仅适用于非泛型类。

在以下位置引用泛型类 `C` 的类型参数将产生编译错误：

- `C` 的静态成员声明 (§8.3.1.1, §8.4.3.2, §8.5.1)。
- `C` 内部任何嵌套类型声明的静态成员声明。

## 类声明

- `c` (§8.7) 的静态初始化器，
- 嵌套在 `c` 的任何类类的静态初始化器。

### 示例 8.1.2-1. 相互递归类型变量边界

```java
interface ConvertibleTo<T> {
  T convert();
}

class Reprange<T extends ConvertibleTo<S>,
  S extends ConvertibleTo<T>> {
  T t;
  void set(S s) { t = s.convert(); }
  S get() { return t.convert(); }
}
```

### 示例 8.1.2-2. 嵌套泛型类

```java
class Seq<T> {
  T head;
  Seq<T> tail;
  Seq() {
    this.head = null;
    this.tail = null;
  }
  Seq(T head, Seq<T> tail) {
    this.head = head;
    this.tail = tail;
  }
  boolean isEmpty() { return tail == null; }
}

class Zipper<S> {
  Seq<Pair<T,S>> zip(Seq<S> tail) {
    if (isEmpty()) {
      return new Seq<Pair<T,S>>();
    } else {
      Seq<T.Zipper<S>> tailZipper =
        tail.new Zipper<S>();
      return new Seq<Pair<T,S>>(new Pair<T,S>(head, that.head),
        tailZipper.zip(that.tail));
    }
  }
}

class Pair<T,S> {
  T fst; S snd;
  Pair(T f, S s) { fst = f; snd = s; }
}

class Test {
  public static void main(String[] args) {
    Seq<String> strs =
    new Seq<String>(
      "a",
      new Seq<String>("b",
      new Seq<String>())
    );
    Seq<Number> nums = (
      new Seq<Number>(
        new Integer(1),
        new Seq<Number>(new Double(1.5),
        new Seq<Number>())
      )
    );
    Seq<String>.Zipper<Number> zipper =
    strs.new Zipper<Number>;
    Seq<Pair<String,Number>> combined =
    zipper.zip(nums);
  }
}
```

## 8.1.3 内部类与编码实例

内部类是一个没有被显式或隐式声明为静态的嵌套类。

内部类可以是非静态成员类 (§8.5)、局部类 (§14.3) 或匿名类 (§15.9)。接口的成员类是隐式静态的 (§9.5)，并且永远不被视为内部类。

如果内部类声明了静态初始化器 (§8.7)，则会产生编译时错误。

如果内部类声明了显式或隐式静态的成员，则会产生编译时错误，除非该成员是常量变量 (§4.12.4)。

内部类可以继承不是常量变量的静态成员，尽管它不能声明这些成员。

不是内部类的嵌套类可以根据 Java 语言通常规则自由地声明静态成员。

### 示例 8.1.3-1. 类声明与静态成员

```java
class HasStatic {
  static int j = 100;
}

class Outer {
  class Inner extends Outer {
    static final int x = 3; // OK: 常量变量
    static int y = 4; // 编译错误：内部类
  }
  static class NestedButNotInner {
    static int z = 5; // OK: 不是内部类
  }
  interface NeverInner {} // 接口永远不是内部类
}
```

## 8.1 类声明 类

一个语句或表达式出现在静态上下文中，当且仅当封装该语句或表达式的最内层方法、构造方法、实例初始化器、静态初始化器、字段初始化器或显式构造方法调用语句是静态方法、静态初始化器、静态变量的初始化器或显式构造方法调用语句 (§8.8.7.1)。

如果 `o` 是类 `c` 的直接包围的类型声明，且 `c` 的声明没有发生在静态上下文中，则类 `c` 是类或接口 `o` 的直接内部类。

如果类 `c` 是 `o` 的直接内部类，或者是 `o` 的内部类的内部类，则类 `c` 是类或接口 `o` 的内部类。

> 内部类的直接包围的类型声明是接口是不寻常但可能的。这只发生在类被声明在默认方法的体中时 (§9.4)。具体来说，如果匿名类或局部类被声明在默认方法的体中，或者成员类被声明在位于默认方法体中的匿名类的体中，就会发生这种情况。

类或接口 `o` 是它自身的零阶词法包围类型声明。

如果 `o` 是 `c` 的第 `n` 词法包围类型声明，则 `c` 是 `o` 的第 `n` 词法包围类型声明。

## 4.1.4 父类与子类

普通类声明中可选的 `extends` 子句指定了当前类的直接父类。

父类：
extends ClassType

`extends` 子句不能出现在 `Object` 类的定义中，否则会产生编译时错误，因为它是原始类且没有直接父类。

`ClassType` 必须命名一个可访问的类类型 (§6.6)，否则会产生编译时错误。

如果 `ClassType` 命名的类是 `final`，则会导致编译时错误，因为 `final` 类不允许有子类 (§8.1.1.2)。

如果 `ClassType` 命名为 `Enum` 类或对 `Enum` 的任何调用，则会导致编译时错误 (§8.9)。

如果 `ClassType` 有类型参数，它必须表示一个良好的参数化类型 (§4.5)，且这些类型参数都不是通配符类型参数，否则会产生编译时错误。

给定一个（可能是泛型的）类声明 `C<F1,...,Fn>` (n ≥ 0, C ≠ Object)，类类型 `C<F1,...,Fn>` 的直接父类是 `C` 声明中 `extends` 子句提供的类型，否则为 `Object`。

给定一个泛型类声明 `C<F1,...,Fn>` (n > 0)，参数化类类型 `C<T1,...,Tn>` 的直接父类是 `Ti` (1 ≤ i ≤ n) 是一个类型，`D<U1,...,Uk>`。

## 类 类声明 8.1

`θ`，其中 `D<U1,...,Uk>` 是 `C<F1,...,Fn>` 的直接超类，且 `θ` 是替换关系 `[F1:=T1,...,Fn:=Tn]`。

一个类被认为是直接超类的直接子类。直接超类是当前类的实现所派生出的类。

子类关系是直接子类关系的传递闭包。如果以下任一成立，则类 `A` 是类 `C` 的子类：

- `A` 是 `C` 的直接子类
- 存在类 `B` 使得 `A` 是 `B` 的子类，且 `B` 是 `C` 的子类，递归应用此定义。

当 `A` 是 `C` 的子类时，类 `C` 被称为类 `A` 的超类。

## 示例 8.1.4-1. 直接超类与子类

```java
class Point { int x, y; }
final class ColoredPoint extends Point { int color; }
class Colored3DPoint extends ColoredPoint { int z; } // error
```

在这里，关系如下：

- 类 `Point` 是 `Object` 的直接子类。
- 类 `Object` 是类 `Point` 的直接超类。
- 类 `ColoredPoint` 是类 `Point` 的直接子类。
- 类 `Point` 是类 `ColoredPoint` 的直接超类。

类 `Colored3DPoint` 的声明会导致编译时错误，因为它尝试扩展 `final` 类 `ColoredPoint`。

## 示例 8.1.4-2. 超类与子类

```java
class Point { int x, y; }
final class ColoredPoint extends Point { int color; }
final class Colored3DPoint extends ColoredPoint { int z; }
```

在这里，关系如下：

- 类 `Point` 是类 `ColoredPoint` 的超类。
- 类 `Point` 是类 `Colored3DPoint` 的超类。
- 类 `ColoredPoint` 是类 `Point` 的子类。
- 类 `ColoredPoint` 是类 `Colored3DPoint` 的超类。
- 类 `Colored3DPoint` 是类 `ColoredPoint` 的子类。
- 类 `Colored3DPoint` 是类 `Point` 的子类。

## 类声明

如果类型 `T` 在类 `c` 的 `extends` 子句中作为超类或超接口出现，或者作为超类或超接口的全限定形式中的修饰符出现，则称类 `c` 直接依赖于类型 `T`。

如果以下任一成立，则类 `c` 依赖于引用类型 `T`：

- `c` 直接依赖于 `T`。
- `c` 直接依赖于接口 `T`，而该接口依赖于 `T` (§9.1.3)。
- `c` 直接依赖于类 `D`，而类 `D` 依赖于 `T`（递归使用此定义）。

如果类依赖于自身，则会导致编译时错误。

如果在运行时加载类时检测到循环声明的类，则会抛出 `ClassCircularityError` (§12.2.1)。

### 示例 8.1.4-3. 类依赖自身

```java
class Point extends ColoredPoint { int x, y; }
class ColoredPoint extends Point { int color; }
```

此程序会导致编译时错误，因为类 `Point` 依赖于自身。

## 8.1.5 超接口

类声明中的可选 `implements` 子句列出了作为被声明类直接超接口的接口名称。

超接口：
implements InterfaceTypeList

类型列表：
implements InterfaceType { , InterfaceType };

每个 `InterfaceType` 必须命名一个可访问的接口类型 (§6.6)，否则将发生编译时错误。

如果 `InterfaceType` 具有类型参数，它必须表示一个良好的参数化类型 (§4.5)，且任何类型参数都不能是通配符类型参数，否则将发生编译时错误。

如果在同一个 `implements` 子句中同一个接口被多次作为直接超接口提到，则会导致编译错误。即使接口以不同的方式命名，情况也是如此。

### 示例 8.1.5-1. 非法超接口

```java
class Redundant implements java.lang.Cloneable, Cloneable {
  int x;
}
```

此程序会导致编译时错误，因为名称 `java.lang.Cloneable` 和 `Cloneable` 指向同一个接口。

给定一个（可能是泛型的）类声明 `C<F1,...,Fn>` (n ≥ 0, C ≠ Object)，如果存在 `implements` 子句，则类 `C<F1,...,Fn>` 的直接超接口是声明中 `implements` 子句给出的类型。

给定泛型类声明 `C<F1,...,Fn>` (n > 0)，参数化类 `C<T1,...,Tn>` 的直接超接口是所有类型 `I<U1,...,Un>`，其中 `Ti` (1 ≤ i ≤ n) 是类型，`I<U1,...,Un>` 是 `C<F1,...,Fn>` 的直接超接口，且 `θ` 是替换 `[F1:=T1,...,Fn:=Tn]`。

如果以下任一成立，则接口 `I` 是 `c` 的超接口：

- `I` 是 `c` 的直接超接口。
- `J` 是 `c` 的超类，且 `I` 是 `J` 的超接口。
- `J` 是 `c` 的超接口，且 `I` 是 `J` 的超接口。

当 `I` 是 `c` 的超接口时，类 `c` 被称为接口 `I` 的子类型。

子类关系是直接子类关系的传递闭包。如果以下任一成立，则类 `A` 是类 `C` 的子类：

- `A` 是 `C` 的直接子类
- 存在类 `B` 使得 `A` 是 `B` 的子类，且 `B` 是 `C` 的子类，递归应用此定义。

## 8.1.6 类体与成员声明

类体可以包含该类成员的声明，即字段 (§8.3)、方法 (§8.4)、类 (§8.5) 和接口 (§8.5)。

类体还可以包含该类的实例初始化器 (§8.6)、静态初始化器 (§8.7) 以及该类构造函数的声明 (§8.8)。

```java
ClassBody:
  {ClassBodyDeclaration}

ClassBodyDeclaration:
  ClassMemberDeclaration
  InstanceInitializer
  StaticInitializer
  ConstructorDeclaration

ClassMemberDeclaration:
  FieldDeclaration
  MethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
;
```

在类类型 `c` 中声明或由其继承的成员 `m` 声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

> 如果 `c` 是嵌套类，则在外层作用域中可能存在与 `m` 相同类型（变量、方法或类型）和名的定义。这些作用域可以是块、类或包。在所有此类情况下，由 `c` 声明或其继承的成员都会遮蔽 (§6.4.1) 其他相同类型和名的定义。

## 8.2 类成员

类类型的成员包括以下所有项：

- 继承自其直接父类的成员 (§8.1.4)，但 `Object` 类除外，因为它没有直接父类
- 继承自任何直接父级接口的成员 (§8.1.5)
- 在类体中声明的成员 (§8.1.6)

### 类成员 8.2 类

在类中被声明为 `private` 的成员不会被该类的子类继承。

只有声明为 `protected` 或 `public` 的类成员才会被声明在类类所在包之外的包中的子类继承。

构造函数、静态初始化器和实例初始化器不是成员，因此不被继承。

我们使用短语“成员的类型”来表示：

- 对于字段，指其类型。
- 对于方法，指一个由以下部分组成的有序 4 元组：
  - 类型参数：该方法成员任何类型参数的声明。
  - 参数类型：该方法成员参数类型的列表。
  - 返回类型：该方法成员的返回类型。
  - throws 类：在方法成员的 `throws` 子句中声明的异常。

类类型的字段、方法和成员类型可能有相同的名称，因为它们被用于不同的上下文中，并通过不同的查找程序 (§6.5) 消除歧义。然而，从风格上来说，是不建议这样做。

### 示例 8.2-1. 类成员的使用

```java
class Point {
  int x, y;
  private Point() { reset(); }
  Point(int x, int y) { this.x = x; this.y = y; }
  private void reset() { this.x = 0; this.y = 0; }
}

class ColoredPoint extends Point {
  int color;
}
```



```java
void clear() { reset(); } // 错误
}

class Test {

  public static void main(String[] args) {

    ColoredPoint c = new ColoredPoint(0, 0); // 错误

    c.reset(); // 错误

  }

}
```

该程序会导致四个编译时错误。

## 类成员

发生一个错误是因为 `ColoredPoint` 没有按照 `main` 方法中的使用要求声明带有两个 `int` 参数的构造函数。这说明了 `ColoredPoint` 并没有继承其父类 `Point` 的构造函数。

另一个错误是因为 `ColoredPoint` 没有声明任何构造函数，因此为其隐式地声明了一个默认构造函数（§8.8.9），该默认构造函数等同于：

```java
ColoredPoint() { super(); }
```

它调用了 `ColoredPoint` 类直接父类的无参数构造函数。错误在于 `Point` 类的无参数构造函数是 `private` 的，因此在 `Point` 类外部无法访问，即使通过父类构造函数调用如此（§8.8.7）。

还有两个错误是因为 `Point` 类的 `reset` 方法是 `private` 的，因此没有被类继承。因此，在 `ColoredPoint` 类 `clear` 方法和 `Test` 类 `main` 方法中的调用都是错误的。

## 示例 8.2-2. 具有包访问权限的类成员继承

考虑 `points` 包声明了两个编译单元的示例：

```java
package points;

public class Point {

    int x, y;

    public void move(int dx, int dy) { x += dx; y += dy; }

}
```

以及：

```java
package points;

public class Point3d extends Point {

    int z;

    public void move(int dx, int dy, int dz) { x += dx; y += dy; z += dz; }

}
```

第三个编译单元在另一个包中：

```java
import points.Point3d;

class Point4d extends Point3d {

    int w;

    public void move(int dx, int dy, int dz, int dw) { x += dx; y += dy; z += dz; w += dw; } // 编译错误

}
```

在这里，`points` 包中的两个类都通过编译。`Point3d` 类继承了 `Point` 类的字段 `x` 和 `y`，因为它与 `Point` 位于同一个包。`Point4d` 类位于不同的包，它没有继承 `Point` 的字段 `x` 和 `y` 或 `Point3d` 的字段 `z`，导致编译失败。

编写第三个编译单元的更好方法是：

```java
import points.Point3d;

class Point4d extends Point3d {

    int w;

    public void move(int dx, int dy, int dz, int dw) {

        super.move(dx, dy, dz); w += dw;

    }

}
```

使用父类 `Point3d` 的 `move` 方法来处理 `dx`、`dy` 和 `dz`。如果 `Point4d` 这样写，它将无错误编译。

## 示例 8.2-3. public 和 protected 成员的继承

给定类 `Point`：

```java
package points;

public class Point {

    public int x, y;

    protected int useCount = 0;

    protected static int totalCount = 0;

    public void move(int dx, int dy) {

        x += dx; y += dy; useCount++;

    }

}
```

`public` 和 `protected` 字段 `x`、`y` 和 `totalCount` 被 `Point` 的所有子类继承。因此，这个在另一个包中的程序可以编译：

```java
class Test extends points.Point {

    public void move(int dx, int dy) {

        x += dx; y += dy; totalCount++;

    }

}
```

## 示例 8.2-4. private 成员的继承

给定类 `Point`：

```java
package points;

public class Point {

    public int x, y;

    protected int useCount = 0;

    protected static int totalCount = 0;

    public void move(int dx, int dy) {

        x += dx; y += dy; useCount++;

    }

}
```

`public` 和 `protected` 字段 `x`、`y` 和 `totalCount` 被 `Point` 的所有子类继承。因此，这个在另一个包中的程序可以编译：

```java
class Test extends points.Point {

    public void move(int dx, int dy) {

        x += dx; y += dy; totalCount++;

    }

}
```

## 8.3 字段声明

类类型的变量通过字段声明引入。

- FieldDeclaration:
  {FieldModifier} UnannType VariableDeclarList;

- VariableDeclarList:
  VariableDeclarator (, VariableDeclarator)

- VariableDeclarator:
  VariableDeclaratorId [= VariableInitializer]

- VariableDeclaratorId:
  Identifier [Dims]

- VariableInitializer:
  Expression
  ArrayInitializer

- UnannType:
  UnannPrimitiveType
  UnannReferenceType

- UnannPrimitiveType:
  NumericType
  boolean

- UnannReferenceType:
  UnannClassOrInterfaceType
  UnannTypeVariable
  UnannArrayType

- UnannClassOrInterfaceType:
  UnannClassType
  UnannInterfaceType

- UnannClassType:
  TypeIdentifier [TypeArguments]
  PackageName . [Annotation] TypeIdentifier [TypeArguments]
  UnannClassOrInterfaceType . [Annotation] TypeIdentifier [TypeArguments]

- UnannInterfaceType:
  UnannClassType

- UnannTypeVariable:
  TypeIdentifier

- UnannArrayType:
  UnannPrimitiveType Dims
  UnannClassOrInterfaceType Dims
  UnannTypeVariable Dims

为了方便起见，这里显示了 §4.3 中的产生式：

- Dims:
  [Annotation] [ ] [Annotation] [ ]

### 字段声明

`FieldDeclaration` 中的每个声明符（declarator）都声明一个字段。声明符中的标识符（`Identifier`）可用于名称以引用该字段。

通过使用多个声明符，可以在单个 `FieldDeclaration` 中声明多个字段；`FieldModifiers`（字段修饰符）和 `UnannType`（非注解类型）适用于声明中的所有声明符。

`FieldModifier` 子句在 §8.3.1 中描述。

如果 `UnannType` 和 `VariableDeclaratorId` 中均未出现括号，则字段的声明类型由 `UnannType` 表示，否则由 §10.2 规定。

字段声明的作用域和遮蔽（shadowing）在 §6.3 和 §6.4 中规定。

在类体中声明两个同名的字段是编译时错误。

如果类声明了一个具有特定名称的字段，则该字段的声明被认为隐藏了（hide）该类的超类和超接口中所有同名且可访问的字段声明。

在这方面，字段的隐藏与隐藏的隐藏（§8.4.8.3）不同，因为在字段隐藏中，静态和非静态字段之间没有区分，而在方法隐藏中，静态和非静态方法之间是有区分的。

如果被隐藏的字段是静态的，则可以使用限定名称（§6.5.6.2）访问，或者通过包含关键字 `super`（§15.11.2）的字段访问表达式或向超类类型的类型转换来访问。

在这方面，字段的隐藏与方法的隐藏相似。

如果一个字段声明隐藏了另一个字段的声明，这两个字段不需要具有相同的类型。

类从其直接超类和直接超接口继承所有非私有的字段，前提是这些字段对于类代码可访问（§6.6）且未被类中的声明所隐藏。

超类的私有字段可能对子类可访问——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能继承多个同名的字段，既可以来自其超类和超接口，也可以仅来自其超接口。这种情况本身并不会引起编译时错误。然而，在类体内部任何通过简单名称引用此类字段的尝试都将导致编译时错误，因为该引用是歧义的。

可能存在通过接口继承相同字段声明的路径。在这种情况下，字段被认为仅被继承一次，可以通过简单名称无歧义地引用。

存储在 `float` 类型字段中的值始终是 `float` 值集的一个元素（§4.2.3）；同样，存储在 `double` 类型字段中的值是 `double` 值集的一个元素。`float` 类型字段不允许包含 `float-extended-exponent` 值集中的不在 `float` 值集中的元素，`double` 类型字段也不允许 `double-extended-exponent` 值集中的不在 `double` 值集中的元素。

## 示例 8.3-1. 多重继承的字段

一个类可能从其超类和一个超接口，或从两个接口继承两个或多个同名的字段，在任何尝试通过简单名称引用任何被继承且具有歧义的字段时，都会发生这种情况。可以使用使用关键字 `super`（§15.11.2）的限定名称或字段访问来无歧义地访问此类字段。在程序中：

```java
interface Frob { float v = 2.0f; }

class SuperTest { int v = 3; }

class Test extends SuperTest implements Frob {

    public static void main(String[] args) {

        new Test().printV();

    }

    void printV() { System.out.println(v); }

}
```

类 `Test` 继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这是允许的，但由于方法 `printV()` 中使用了简单名称 `v`，会导致编译时错误：无法确定意图是指哪一个 `v`。

以下变体使用字段访问表达式 `super.v` 来引用 `SuperTest` 类中声明的字段 `v`，并使用限定名称 `Frob.v` 来引用 `Frob` 类中声明的字段 `v`：

```java
interface Frob { float v = 2.0f; }

class SuperTest { int v = 3; }

class Test extends SuperTest implements Frob {

    public static void main(String[] args) {

        new Test().printV();

    }

    void printV() {

        System.out.println(super.v);

        System.out.println(Frob.v);

    }

}
```



如果一个字段声明隐藏了另一个字段的声明，这两个字段不需要具有相同的类型。

类从其直接超类和直接超接口继承所有非私有的字段，前提是这些字段对于类代码可访问（§6.6）且未被类中的声明所隐藏。

超类的私有字段可能对子类可访问——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能继承多个同名的字段，既可以来自其超类和超接口，也可以仅来自其超接口。这种情况本身并不会引起编译时错误。然而，在类体内部任何通过简单名称引用此类字段的尝试都将导致编译时错误，因为该引用是歧义的。

（注：此处后续存在大量重复文本，已根据指令要求去重，仅保留核心逻辑翻译）

```java
System.out.println(q.origin.useCount);
}
```

此程序打印：

```
(2,2)
0
true
1
```

这表明更改 `p` 的字段 `x`、`y` 和 `useCount` 不影响 `q` 的字段，因为这些字段是不同对象中的实例变量。在这个示例中，`Point` 类的类变量 `origin` 使用相同的类名作为限定符进行引用（即 `Point.origin`），并且在字段访问表达式中使用该类类型的变量（§15.11），如 `p.origin` 和 `q.origin`。这两种访问 `origin` 类变量的方式访问的是同一个对象，这一点可以由引用等价表达式（§15.23）的值得到证明：

```
q.origin==Point.origin
```

其结果为 `true`。进一步的证据是递增操作：

```
p.origin.useCount++;
```

导致 `q.origin.useCount` 的值变为 `1`；这是因为 `p.origin` 和 `q.origin` 指向同一个变量。

## 8.3.1.1-2. 类变量的隐藏

```java
class Point {
    static int x = 2;
}

class Test extends Point {
    static double x = 4.7;

    public static void main(String[] args) {
        new Test().printX();
    }

    void printX() {
        System.out.println(x + " " + super.x);
    }
}
```

此程序产生输出：

```
4.7 2
```

这是因为 `Test` 类中 `x` 的声明隐藏了 `Point` 类中 `x` 的定义，所以 `Test` 类没有继承自其父类 `Point` 的字段 `x`。在 `Test` 类的声明内部，简单名称 `x` 指向在 `Test` 类内部声明的字段。`Test` 类中的代码可以通过 `super.x` 引用 `Point` 的字段 `x`（或者因为 `x` 是静态的，可以使用 `Point.x`）。

如果删除了 `Test.x` 的声明：

```java
class Point {
    static int x = 2;
}

class Test extends Point {
    public static void main(String[] args) {
        new Test().printX();
    }

    void printX() {
        System.out.println(x + " " + super.x);
    }
}
```

那么 `Point` 类的字段 `x` 就不再隐藏在 `Test` 类中；相反，简单名称 `x` 指向字段 `Point.x`。`Test` 类中的代码仍然 `super.x` 引用该字段。因此，该变体程序的输出为：

```
2 2
```

## 8.3.1.1-3. 实例变量的隐藏

```java
class Point {
    int x = 2;
}

class Test extends Point {
    double x = 4.7;

    void printBoth() {
        System.out.println(x + " " + super.x);
    }

    public static void main(String[] args) {
        Test sample = new Test();
        sample.printBoth();
        System.out.println(sample.x + " " + ((Point)sample).x);
    }
}
```

此程序产生输出：

```
4.7 2
2
```

这是因为 `Test` 类中 `x` 的声明隐藏了 `Point` 类中 `x` 的定义，所以 `Test` 类没有继承其父类 `Point` 的字段。必须注意的是，虽然 `Point` 类的字段没有被 `Test` 类继承，但它仍然由 `Test` 类的实例实现。换句话说，`Test` 类的每个实例包含两个字段，一个 `int` 类型，一个 `double` 类型。这两个字段都名为 `x`；但在 `Test` 类的声明内部，简单名称 `x` 始终指向在 `Test` 类内部声明的字段。`Test` 类实例方法中的代码可以通过 `super.x` 引用 `Point` 的实例变量 `x`。

## 字段声明

使用字段访问表达式访问 `x` 将访问由引用表达式类型所指示的类中名为 `x` 的字段。因此，表达式 `sample.x` 访问一个 `double` 值（即在 `Test` 类中声明的实例变量），因为变量 `sample` 的类型是 `Test`；但表达式 `((Point)sample).x` 访问一个 `int` 值（即在 `Point` 类中声明的实例变量），因为强制转换为了类型 `Point`。

如果从 `Test` 类中删除 `x` 的声明，如程序所示：

```java
class Point {
    static int x = 2;
}

class Test extends Point {
    void Point() {
        System.out.println(x + " " + super.x);
    }

    public static void main(String[] args) {
        Test sample = new Test();
        sample.printBoth();
        System.out.println(sample.x + " " + ((Point)sample).x);
    }
}
```

那么 `Point` 类的 `x` 不再隐藏在 `Test` 类中。在 `Test` 声明的实例方法中，简单名称 `x` 指向在 `Point` 中声明的字段。`Test` 中的代码仍然可以通过 `super.x` 引用该字段。表达式 `sample.x` 仍然指向 `Test` 内部的字段 `x`，但该字段现在是一个继承的字段，因此指向在 `Point` 中声明的字段 `x`。该变体的输出为：

```
2 2
```

## 8.3.1.2 final 字段

字段可以声明为 `final` (§4.1)。类变量和实例变量（静态是非静态字段）都可以声明为 `final`。一个空的 `final` 变量必须由其声明所在类的静态初始化器进行确定赋值，否则会发生编译错误 (§8.7, §16)。

一个空的 `final` 实例变量必须在类声明所在类的每个构造函数结束时都已确定赋值，并且没有未被赋值，否则会发生编译错误 (§8.8, §16)。

## 8.3.1.3 transient 字段

变量可以标记为 `transient`，以表示它们不是对象持久化状态的一部分。

## 示例 8.3.1-3. transient 字段的持久化

如果类

```java
class Point {
    transient x, y;
}
```

的实例被系统服务保存到持久化存储器，那么只有字段 `x` 和 `y` 会被保存。此规范未指定此类服务的细节；请参见 `java.io.Serializable` 实例对于此类服务的规范。

## 8.3.1.4 volatile 字段

Java 允许线程访问共享变量 (§17.1)。为了确保共享变量一致且可靠地更新，线程应该通过锁来确保互斥。Java 语言提供了第二种机制：`volatile` 字段，这在某些情况下比锁更方便。内存模型确保线程看到一致的值简体17.4)。如果字段被声明为 `final`，则会导致编译错误。

## 示例 8.3.1-4. volatile 字段

如果在下面的示例中，一个线程重复调用 `one`（多于 `Integer.MAX_VALUE` 次），另一个线程重复调用 `two`：

```java
class Test {
    static int i = 0, j = 0;

    static void one() { i++; j++; }

    static void two() {
        System.out.println("i=" + i + " " + j);
    }
}
```

`two` 方法偶尔可能会打印比 `i` 更大的 `j` 值，因为示例中没有同步，`i` 和 `j` 可能会无序更新。防止这种无序行为的一种方法是将 `one` 和 `two` 声明为 `synchronized` (§8.4.3)。

```java
class Test {
    static int i = 0, j = 0;

    static synchronized void one() { i++; j++; }

    static synchronized void two() {
        System.out.println("i=" + i + " " + j);
    }
}
```

这防止了 `one` 和 `two` 同时执行，并保证 `i` 和 `j` 的共享值在方法返回之前已更新。因此，`two` 永远观察不到比 `i` 更大的 `j`；事实上，它总是观察到相同的 `i` 和 `j`。

另一种方法是将 `i` 和 `j` 声明为 `volatile`：

```java
class Test {
    static volatile int i = 0, j = 0;

    static void one() { i++; j++; }

    static void two() {
        System.out.println("i=" + i + " " + j);
    }
}
```

这允许 `one` 和 `two` 同时执行，并保证对 `i` 和 `j` 共享值的访问与每个线程执行程序文本时出现的次数相同、顺序也相同。因此，共享值 `j` 永远大于 `i`，因为每次对 `i` 的更新必须在 `j` 发生之前反映。然而，任何对 `two` 的调用可能会观察到的 `j` 值远大于观察到的 `i` 值，因为在 `two` 获取 `i` 值的时刻与获取 `j` 值的时刻之间，`one` 可能会被执行多次。

参见 17.4 获取更多讨论和示例。

## 8.3.2 字段初始化

如果字段声明中的声明符有一个变量初始化器，则该声明符的语义等同于对声明变量进行赋值 (§15.26)。

如果该声明符是用于类变量（即静态字段），则其初始化器适用以下规则：

- 如果初始化器中通过简单名称引用了任何实例变量，则为编译错误。
- 如果初始化器中出现了关键字 `this` (§15.8.3) 或关键字 `super` (§15.11.2, §15.12)，则为编译错误。
- 在运行时，初始化器被求值并执行一次赋值，即在类初始化时简体12.4.2)。

## 8.3 字段声明

注意，作为常量变量（§4.12.4）的静态字段会在其他静态字段（§12.4.2）之前初始化。这同样适用于接口（§9.3.1）。当通过简单名引用此类字段时，它们永远不会被观察到具有其默认初始值（§14.2.5）。

如果声明符是一个实例变量（即非静态字段），则以下规则适用于其初始化器：

- 初始化器可以通过简单名引用由该类声明或继承的任何类变量，即使该变量的声明位于初始化器的右侧（§3.5）。
- 初始化器可以使用关键字 `this`（（§15.8.3）或关键字 `super`（§15.11.2, §15.12）引用当前对象。
- 在运行时，每当创建类的实例时，都会对初始化器进行求值并执行赋值（§12.5）。

从变量初始化器到可能未初始化的字段引用受额外限制，具体见 §8.3.3 和 §16（确定赋值）。

字段声明中变量初始化器的异常检查规定在 §11.2.3 中。

变量初始化器也用于局部变量声明语句（§14.4），每当执行局部变量声明语句时，都会对初始化器进行求值并执行赋值。

### 示例 8.3.2-1. 字段初始化

```java
class Point {
    int x = 1, y = 5;
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        System.out.println(p.x + ", " + p.y);
    }
}
```

该程序产生输出：

```
1, 5
```

因为每当创建新的 `Point` 时，都会发生 x 和 y 的赋值。

### 示例 8.3.2-2. 对类变量的前向引用

```java
class Test {
    float f = j;
    static int j = 1;
}
```

该程序编译无错误；它在初始化类 `Test` 时将 `j` 初始化为 `i` 的值，并在每当创建类 `Test` 的实例时，将 `f` 初始化为 `j` 的当前值。

## 8.3.3 初始化器中字段引用的限制

即使字段在作用域内，对字段的引用有时也会受到限制。以下规则限制了对字段的前向引用（使用处在文本上先于字段声明）以及自引用（即字段在其自身的初始化器中使用）。

对于在类 `c` 或接口 `c` 中声明的类变量 `f` 的简单名引用，如果满足以下条件，则为编译错误：

- 该引用出现在 `c` 的类变量初始化器中，或 `c` 的静态初始化器中（§8.7）；且
- 该引用出现在 `f` 自身声明符的初始化器中，或 `f` 声明符左侧的位置；且
- 该引用不是赋值表达式的左侧（§15.26）；且
- 封装该引用的最内层类或接口是 `c`。

对在类 `c` 中声明的实例变量 `f` 的简单名引用，如果满足以下条件，则为编译错误：

- 该引用出现在 `c` 的实例变量初始化器中，或 `c` 的实例初始化器中（§8.6）；且
- 该引用出现在 `f` 自身声明符的初始化器中，或 `f` 声明符左侧的位置；且
- 该引用不是赋值表达式的左侧（§15.26）；且
- 封装该引用的最内层类是 `c`。

### 示例 8.3.3-1. 字段引用的限制

此程序会发生编译错误：

```java
class Test1 {
    int i = j; // 编译错误：
    // 错误的前向引用
    int j = i;
}
```

而以下程序编译无错误：

```java
class Test2 {
    Test2() { k = 2; }
    int j = 1;
    int i = j;
    int k;
}
```

即使 `Test2` 的构造函数（§8.8）引用了三行后声明的字段 `k`。

上述限制旨在编译时捕获循环或其他格式错误的初始化。因此，以下两种情况都会导致编译错误：

```java
class Z {
    static int i = j + 2;
    static int j = 4;
}
```

以及：

```java
class Z {
    static { i = j + 2; }
    static int i, j;
    static { j = 4; }
}
```

通过方法的访问不进行此类检查，因此：

```java
class Z {
    static int peek() { return j; }
    static int i = peek();
    static int j = 1;
}

class Test {
    public static void main(String[] args) {
        System.out.println(Z.i);
    }
}
```

产生输出：

```
0
```

因为变量 `i` 使用类方法 `peek` 在 `j` 被其变量初始化器初始化之前访问了变量 `j` 的值，此时它仍然具有默认值。一个更复杂的示例是：

```java
class UseDeclaration {
  static { x = 100; }
  static int y = x + 1;
  static int z = 2;
  static { j = 3; }
  static int n = j + 1;
  static int p = j;
  static int u = 3;
  static int h = j;
  static int v = x + 1;
  static int l = j;
  static int w = x;
  static int q = j;
}
```

以及一个标识符（可选地跟随括号），用于指定参数的名称。

如果一个方法或构造函数没有形式参数，也没有接收器参数，则在方法或构造函数的声明中会出现一对空括号。

```
FormalParameterList:
```



## 形式参数

```
FormalParameter (, FormalParameter)

FormalParameter:
    [VariableModifier] UnannType VariableDeclaratorId
    VariableArity

VariableArityParameter:
    [VariableModifier] UnannType [Annotation] ... Identifier

VariableModifier:
    Annotation
    final
```

为了方便起见，这里显示了 §8.3 和 §4.3 中的以下产生式：

```
VariableDeclaratorId:
    Identifier [Dims]

Dims:
    [Annotation] [] {[Annotation] []}
```

方法或构造函数的形式参数可以是变长参数，通过类型后的省略号（`...`）来指示。一个方法或构造函数最多允许一个变长参数。如果变长参数出现在参数规格列表的最后一个位置以外的任何位置，则将是一个编译时错误。

在 `VariableArityParameter` 的语法中，注意省略号（`...`）是一个独立的标记（§3.11）。可以在它和类型之间插入空格，但从风格上来说这样做是不建议的。

如果最后一个形式参数是变长参数，则该方法是变长方法。否则，它是固定长度方法。

形式参数声明上和接收器参数上的注解修饰符规则在 §9.7.4 和 §9.7.5 中规定。

## 类方法声明 8.4

如果 `final` 作为形式参数声明的修饰符出现多次，则将是一个编译时错误。

形式参数的作用域和隐藏规则在 §6.3 和 §6.4 中规定。

方法或构造函数声明两个同名的形式参数将是一个编译时错误。（也就是说，它们的声明提到了同一个标识符 `Identifier`。）

如果一个声明为 `final` 的形式参数被赋值给方法或构造函数的体，则将是一个编译时错误。

形式参数的声明类型取决于它是否为变长参数：

- 如果形式参数不是变长参数，则如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号对，则声明类型由 `UnannType` 表示，否则由 §10.2 规定。
- 如果形式参数是变长参数，则其声明类型由 §10.2 规定的数组类型。

如果变长数组的声明类型具有不可重化的元素类型（§4.7），则该变长方法的声明将发生编译时未检查警告，除非它被注记了 `@SafeVarargs`（§9.6.4.7）或该警告被 `@SuppressWarnings`（§9.6.4.5）抑制。

当调用方法或构造函数时（§15.12），实际参数表达式的值会在方法或构造函数体执行之前初始化新创建的参数变量，每个变量都具有声明的类型。`FormalParameter` 中出现的标识符 `Identifier` 可以在方法或构造函数体中作为简单名称来引用该形式参数。

变长方法的调用包含的实际表达式可能比形式参数多。所有对应于变长参数之前的形式参数的实际参数表达式将被求值，结果将存储在一个数组中并传递给方法调用（§15.12.4.2）。

方法或构造函数类型为 `float` 的形式参数始终包含 `float` 值集中的一个元素（§4.2.3）；同样，方法或构造函数类型为 `double` 的形式参数始终包含 `double` 值集中的一个元素。方法或构造函数类型为 `float` 的形式参数不允许包含不属于 `float` 值集的 `float-扩展指数` 值集中的元素，方法或构造函数类型为 `double` 的形式参数也不允许包含不属于 `double` 值集的 `double-扩展指数` 值集中的元素。

当参数变量对应的参数表达式不是 FP-strict（15.4）时，允许该实际参数表达式的求值使用从适当的扩展指数值集中提取中间值。在存储到参数变量之前，此类表达式的结果将通过调用转换（§5.3）映射到相应标准值集中最接近的值。

以下是实例方法和内部类构造函数中接收器参数的一些示例：

```java
class Test {

    Test(/* // 在顶层类的构造函数中允许接收器参数

    // 因为没有可以想象的类型或名称。

    void m(Test this) {

        // OK：实例方法中的接收器参数

    }

    static void n(Test this) {

        // 非法：静态方法中的接收器参数

    }

    class A {

        A(Test.this) {

            // OK：接收器参数代表

            // 紧接其外部的正在构造的

            // A 实例。

        }

        void m(A this) {

            // OK：接收器参数代表

            // 调用 A.m() 的 A 实例。

        }

        class B {

            B(Test.A A.this) {

                // OK：接收器参数代表

                // 紧接其外部的正在构造的 B 实例的 A 实例。

            }

            void m(Test.A B this) {

                // OK：接收器参数代表

                // 调用 B.m() 的 B 实例。

            }

        }

    }

}
```

当参数变量对应的参数表达式不是 FP-strict（15.4）时，允许该实际参数表达式的求值使用从适当的扩展指数值集中提取的中间值。

接收器参数的参数类型。

## 8.4.2 签名

两个方法或构造函数 $M$ 和 $N$ 具有相同的签名，如果它们具有相同的名称、相同的参数类型（泛型），并且在泛型擦除后相同（§8.4）。

$m_1$ 的签名是 $m_2$ 的子签名，如果：

- $m_2$ 的签名与 $m_1$ 相同，或者
- $m_1$ 的签名是 $m_2$ 的子签名。

两个签名 $m_1$ 和 $m_2$ 是等价的，如果 $m_1$ 是 $m_2$ 的子签名，且 $m_2$ 是 $m_1$ 的子签名。

### 8.4.2.1 等价签名

在类中声明两个等价签名的方法是一个编译时错误。

```java
class Point {

    int x, y;

    abstract void move(int dx, int dy);

    void move(int dx, int dy) { x += dx; y += dy; }

}
```

此程序会导致编译错误，因为它声明了两个相同的（抽象）签名。子签名的概念用于表示两个签名不相同的方法之间的关系，其中一个可以覆盖另一个。具体来说，它允许一个不使用泛型的方法覆盖其泛型版本。考虑以下示例：

```java
class CollectionConverter {

    List toList(Collection c) { ... }

}
```

现在，假设此代码是在引入泛型之前编写的，现在 `CollectionConverter` 的作者决定将其泛型化：

```java
class CollectionConverter {

  <T> List<T> toList(Collection<T> c) { ... }

}
```

如果没有特殊许可，`Overrider.toList` 将不再覆盖 `CollectionConverter.toList`，这将极大抑制泛型的使用，因为库编写者会犹豫迁移现有代码。

## 8.4.3 方法修饰符

```
MethodModifier:
（以下之一）
Annotation public protected private
abstract static final synchronized strictfp
```

方法声明上的注解修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果同一个关键字作为方法声明的修饰符出现多次，或者方法声明具有多个 `public`、`protected` 或 `private` 修饰符（§6.6），则将是一个编译时错误。

如果方法声明包含 `abstract` 同时同时包含 `private`、`static`、`final`、`native`、`strictfp` 或 `synchronized` 关键字，则将是一个编译时错误。

如果方法声明包含 `native` 同时包含 `strictfp`，则将是一个编译时错误。

> 如果方法声明中出现了两个或多个（不同的）方法修饰符，习惯上（但不是要求）它们按照上述 `MethodModifier` 产生式所示的顺序出现。

### 8.4.3.1 抽象方法

抽象方法引入此成员，提供了其签名（§8.4.2）、结果简体（8.4.5）以及任何有的抛出子句简体（8.4.6），但没有提供实现简体（8.4.7）。

抽象方法的声明必须直接出现在抽象类（称为 A）内部，除非它出现在枚举声明简体（8.9）中，否则将发生编译时错误。

A 的每一个非抽象子类（§8.1.1.1）都必须为 `m` 提供一个实现，否则将发生编译时错误。

抽象类可以通过提供另一个抽象方法声明来重写抽象方法。

这可以提供一个放置文档注释的地方，用于精炼返回类型，或者声明该方法在被子类实现时，其可能抛出的受检异常集合将更具局限性。

非抽象的实例方法可以被抽象方法重写。

#### 示例 8.4.3.1-1. 抽象/抽象方法的重写

```java
class BufferEmpty extends Exception {

    BufferEmpty() { super(); }

    BufferEmpty(String s) { super(s); }

}

class BufferError extends Exception {

    BufferError() { super(); }

    BufferError(String s) { super(s); }

}

interface Buffer {

    char get() throws BufferEmpty, BufferError;

}

abstract class InfiniteBuffer implements Buffer {

    public abstract char get() throws BufferError;

}
```

类 `InfiniteBuffer` 中方法 `get` 的重写声明表示，`InfiniteBuffer` 的任何子类中的 `get` 方法永远不会抛出 `BufferEmpty` 异常，据推是因为它在缓冲区中生成数据，因此永远不会耗尽数据。

#### 示例 8.4.3.1-2. 抽象/非抽象方法的重写

我们声明了一个抽象类 `Point`，它要求子类如果要成为完整的可实例化的类，就实现 `toString`：

```java
abstract class Point {

    int x, y;

    public abstract String toString();

}
```

此对 `toString` 的抽象声明重写了 `Object` 类的非抽象 `toString` 方法。（`Object` 类是 `Point` 类的隐式直接超类）。加上：

```java
class ColoredPoint extends Point {

    int color;

}
```

```java
public String toString() {

    return super.toString() + ": " + color; // 错误

}
```

会导致编译时错误，因为 `super.toString()` 指向 `Point` 类中的 `toString` 方法，而该方法是抽象的，无法被调用。只有当 `Point` 类通过某些其他方法显式地让 `Object` 类的 `toString` 方法对 `ColoredPoint` 可时，例如：

```java
abstract class Point {

    int x, y;

    public abstract String toString();

    protected String objToString() { return super.toString(); }

}

class ColoredPoint extends Point {

    int color;

    public String toString() {

        return objToString() + ": " + color; // 正确

    }

}
```

### 8.4.3.2 static 方法

声明为 `static` 的方法称为类方法。

在类方法的头部或体中使用任何周围声明的类型参数名称是编译时错误。

类方法始终在不引用特定对象的情况下被调用。尝试使用 `this` 关键字（§15.8.3）或 `super` 关键字（§15.11.2）引用当前对象是编译时错误。

未声明为 `static` 的方法是实例方法，有时称为非静态方法。

实例方法总是相对于某个对象被调用，该对象在方法体执行期间成为当前对象，关键字 `this` 和 `super` 正指向该对象。

### 8.4.3.3 final 方法

方法可以被声明为 `final` 以防止子类重写或隐藏它。

尝试重写或隐藏 `final` 方法是编译时错误。

私有方法以及所有直接声明在 `final` 类（§8.1.1.2）内部的方法的行为都等同于 `final` 方法，因为重写它们是不可能的。

在运行时，机器码生成器或优化器可以“内联” `final` 方法的体，用该方法的调用替换为其代码。内联过程必须保留方法调用的语义。特别是，如果实例方法的目标为 `null`，即使方法被内联，也必须抛出 `NullPointerException`。Java 编译器必须确保异常在正确的位置抛出，以便方法的实际参数在方法调用之前能以正确的顺序被看到。

考虑以下示例：

```java
final class Point {

    int x, y;

    void move(int dx, int dy) { x += dx; y += dy; }

}

class Test {

    public static void main(String[] args) {

        Point[] p = new Point[100];

        for (int i = 0; i < p.length; i++) {

            p[i] = new Point();

            p[i].move(i, p.length-1-i);

        }

    }

}
```

在 `main` 方法中内联 `Point` 类的 `move` 方法将把 `for` 循环转换为如下：

```java
for (int i = 0; i < p.length; i++) {

    p[i] = new Point();

    Point pi = p[i];

    int j = p.length-1-i;

    pi.x += i;

    pi.y += j;

}
```



该循环随后可能会进一步优化。

这种内联无法在编译时完成，除非能保证 `Test` 和 `Point` 将一起重新编译，这样每当 `Point`（特别是它的方法）发生变化时，`Test.main` 的代码也会更新。

### 8.4.3.4 native 方法

声明为 `native` 的方法实现在依赖平台的代码中，通常用 C 等另一种编程语言编写。`native` 方法的体是省略的。

### 8.4.4 泛型方法

如果一个方法声明了一个或多个类型变量（§4.4），则该方法是泛型的。

这些类型变量被称为方法的类型参数。泛型方法类型参数部分的形式与泛型类的类型参数部分（§8.1.2）相同。

泛型方法声明定义了一组方法，类型参数部分的每种可能调用对应一个方法。类型参数可以是当调用泛型方法时，不需要显式提供，因为它们通常可以推断出来（§18 (类型推断)）。

方法的类型参数的作用范围和遮蔽在 §6.3 中规定。

两个方法或构造方法 $M$ 和 $N$ 具有相同的类型参数，当且仅当以下两个条件时：

- $M$ 和 $N$ 具有相同类型的参数（可能为零）。
- 设 $A_1, \dots, A_n$ 是 $M$ 的类型参数，$B_1, \dots, B_n$ 是 $N$ 的类型参数，令 $\theta=[B_1:A_1, \dots, B_n:A_n]$。那么，对于所有的 $i$ ($1 \le i \le n$)，$A_i$ 的边界与将 $\theta$ 应用于 $B_i$ 的边界的类型相同。

当方法或构造方法 $M$ 和 $N$ 具有相同的类型参数时，$N$ 中提到的类型可以通过将上述定义的 $\theta$ 应用于该类型，适配为 $M$ 的类型参数。

### 8.4.5 方法结果

方法声明的结果要么声明该方法返回的值的类型（返回类型），要么使用关键字 `void` 表明该方法不返回任何值。

> 结果：
> UnannType
> void

如果结果是 `void`，且在形式参数列表后没有出现括号对，则方法的返回类型表示为 $UnannType$；否则由 §10.2 规定。

如果返回类型是引用类型，则在相互覆盖的方法之间，返回类型可能会不同。返回类型可替换性的概念支持*协变返回*，即返回类型向其子类型的特化。

一个返回类型为 $R_1$ 的方法声明 $d_1$ 对于另一个返回类型为 $R_2$ 的方法 $d_2$ 是*返回类型可替换的*，当且仅当以下任一条件成立：

- 如果 $R_1$ 是 void，则 $R_2$ 也是 void。
- 如果 $R_1$ 是基本类型，则 $R_2$ 与 $R_1$ 相同。
- 如果 $R_1$ 是引用类型，则以下任一成立：
  - $R_1$ 适配到 $d_2$ 的类型参数 (§8.4.4) 后是 $R_2$ 的子类型。
  - $R_1$ 可以通过 unchecked转换 (§5.1.9) 转换为 $R_2$ 的子类型。
  - $d_1$ 与 $d_2$ 没有相同的签名 (§8.4.2)，且 $R_1 = |R_2|$。

默认情况下允许进行 unchecked转换（尽管是不安全的），作为从非泛型代码向泛型代码平滑迁移的特殊允许。如果使用 unchecked转换来确定 $R_1$ 对于 $R_2$ 是返回类型可替换的，那么 $R_1$ 必然不是 $R_2$ 的子类型，覆盖规则 (§8.4.3, §9.4.1) 将要求产生编译时的 unchecked 。

## 8.4.6 方法 throws

`throws` 子句用于表示方法或构造体体语句可以抛出的任何检查异常类 (§11.1.1) (§11.2.2)。

```
Throws:
  throws ExceptionTypeList

ExceptionTypeList:
  ExceptionType {, ExceptionType}

ExceptionType:
  ClassType
  TypeVariable
```

如果 `throws` 子句中提到的 `ExceptionType` 不是 `Throwable` 的子类型 (§4.10)，则为编译错误。

尽管类型变量在 `catch` 子句中是不允许的 (§14.20)，但在 `throws` 子句中是允许的。

在 `throws` 子句中提到 unchecked异常类 (§11.1.1) 是允许的并非要求的。

`throws` 子句与方法或构造体异常检查之间的关系规定在 §11.2.3。本质上，对于方法或构造体执行产生的每个检查异常，除非其异常类型或其父类型在 `throws` 子句中提到，否则将发生编译错误。未能处理在体中抛出的检查异常的方法或构造方法会导致编译错误。Java 语言因此鼓励这种方式来记录罕见且真实的异常情况。

方法的 `throws` 子句与被覆盖或遮蔽方法的 `throws` 子句之间的关系规定在 §8.4.3。

### 8.4.6-1. 作为抛出异常的类型变量

```java
import java.io.FileNotFoundException;

interface PrivilegedAction<E extends Exception> {
    void run() throws E;
}

class AccessController {
    public static <E extends Exception> Object doPrivileged(PrivilegedAction<E> action) throws E {
        return "success";
    }
}

class Test {
    public static void main(String[] args) {
        try {
            AccessController.doPrivileged(new PrivilegedAction<FileNotFoundException>() {
                public void run() throws FileNotFoundException {
                    // ...
                }
            });
        } catch (FileNotFoundException f) { /* Do something */ }
    }
}
```

### 8.4.7 方法体

方法体要么是实现方法的块，要么是一个分号，表示缺失实现。

MethodBody:
Block

如果方法是抽象或 native 的 (§8.4.3, §8.4)，方法体必须是一个分号：

- 如果方法声明是抽象或 native 但使用了块，则为编译错误。
- 如果方法声明既不是抽象也不是 native 但使用了分号，则为编译错误。

方法体中返回语句的规则规定在 §14.17。如果方法声明具有返回类型 (§8.4.5)，且方法体可以正常完成 (§14.1)，则发生编译错误。换句话说，具有返回类型的方法必须通过返回语句返回值；方法不允许直接“结束体”。

方法可以具有返回类型且没有返回语句。有一个例子：

```java
class DizzyBean {
    int() { throw new RuntimeException(""); }
}
```

## 8.4.8 继承、覆盖和遮蔽

类 $c$ 继承其直接父类的所有具体方法 $m$（静态和实例），当且仅满足以下所有条件：

- $m$ 是 $C$ 直接父类的成员。
- $m$ 是 public、protected 或在 $C$ 相同的包中声明。
- $c$ 中声明的方法没有签名是 $m$ 签名的子签名 (§8.4.2)。

类 $c$ 继承其直接父类和直接父接口的所有抽象和默认 (§9.4) 方法 $m$，当且仅满足以下所有条件：

- $m$ 是 $C$ 直接父类或直接父接口 $D$ 的成员。
- $m$ 是 public、protected 或在 $C$ 相同的包中声明。
- $c$ 中声明的方法没有签名是 $m$ 签名的子签名 (§8.4.2)。
- $c$ 从其直接父类继承的具体方法没有签名是 $m$ 的子签名。
- 不存在方法 $m'$，它是 $c$ 的直接父类或直接接口 $D'$（不同于 $D'$，$不同于 $D$）的成员，使得 $m'$ 覆盖 (§8.4.1, §9.4.1) 方法 $m$ 的声明。

类不从接口继承私有或静态方法。方法基于签名进行覆盖或遮蔽。例如，如果一个类声明了同名的 public 方法 (§8.4.9)，而子类覆盖了其中一个，子类仍然继承另一个方法。

### 示例 8.4.8-1. 继承

```java
interface I1 {
  int foo();
}

interface I2 {
  int foo();
}

abstract class Test implements I1, I2 {
```

在这里，抽象类 `Test` 从接口 `I1` 继承了抽象方法 `foo`，也从接口 `I2` 继承了抽象方法 `foo`。确定从 `I1` 继承 `foo` 的关键问题是：`I2` 中的 `foo` 方法是覆盖了“I2”还是 `I1` 中的 `foo` 方法？不，因为 `I1` 和 `I2` 不是互相的子接口。因此，从类 `Test` 的观点来看，从 `I1` 继承 `foo` 与从 `I2` 继承 `foo` 是独立的。根据 §8.4.4，类 `Test` 可以继承两个 `foo` 方法；显然必须被声明为抽象，或者用具体方法覆盖两个抽象 `foo` 方法。

注意，被继承的方法可能会阻止抽象或默认方法的继承。（具体方法将覆盖“c”的抽象或默认方法，§8.4.1 和 §9.4.1。）如果一个父类型方法“已经”覆盖了另一个父类型方法，也可能阻止另一个父类型方法的继承——这与接口的规则相同 (§9.4.1)，并在继承了多个默认方法且其中一个实现显然旨在取代另一个时防止冲突。

### 8.4.8.1 覆盖（通过实例方法）

类 $c$ 中声明或其继承的实例方法 $m_c$ 覆盖来自 $c$ 的类 $A$ 中声明的另一个方法 $m_A$，当仅当以下任一条件成立：

- $c$ 是 $A$ 的子类。
- $c$ 不继承 $m_A$。
- $m_C$ 的签名是 $m_A$ 签名 (§8.4.2) 的子签名。
- 满足以下条件之一为真：
    - $m_A$ 是公共的（public）。
    - $m_A$ 是保护的（protected）。
    - $m_A$ 在与 $C$ 相同的包中以包级访问权限（package access）声明，且 $C$ 声明了 $m_C$，或 $m_A$ 是 $C$ 直接父类的成员。
    - $m_A$ 以包级访问权限声明，且 $m_C$ 重写了来自 $C$ 的某个父类的方法的 $m_A$。
    - $m_C$ 以包级访问权限声明，且 $m_C$ 重写了来自 $C$ 的方法 $m'$（不同于 $m_C$ 和 $m_A$），使得 $m'$ 重写了来自 $C$ 的某个父类的方法。

如果 $m_C$ 是非抽象的且重写了来自 $C$ 的抽象方法 $m_A$，则称 $m_C$ 实现了来自 $C$ 的 $m_A$。

如果被重写的方法 $m_A$ 是静态方法，则是编译错误。

> 在这方面，方法的重写与字段的隐藏 (§8.3) 不同，因为实例变量隐藏静态变量是允许的。

在类 $C$ 中声明或其继承的实例方法 $m_C$，如果满足以下所有条件，则它重写了接口 $I$ 中声明的另一个方法 $m_I$：

- $I$ 是 $C$ 的父接口。
- $m_I$ 不是静态的。
- $C$ 不继承 $m_T$。
- $m_C$ 的签名是 $m_I$ 签名 (§8.4.2) 的子签名。
- $m_I$ 是公共的。

如果其中一个方法的形式化参数具有原始类型（raw type），而另一个方法的对应参数具有泛型类型（parameterized type），则重写方法的签名可能与被重写的方法不同。这是为了方便现有代码迁移以利用泛型。

重写的概念包含了重写了其声明类之某个子类中方法的方法。这可以通过两种方式发生：

- 泛型父类中的具体方法在某些参数化情况下，可能与该类中的抽象方法具有相同的签名。在这种情况下，具体方法被继承，而抽象方法未被继承（如上所述）。此时继承的方法应被视为重写了来自 $c$ 的抽象同类方法。（这种场景由于包级访问而变得复杂：如果 $c$ 在不同的包中，$m$ 本身就不会被继承，也不应被视为已重写。）
- 从类继承的方法可以重写父接口方法。（幸运的是，这里不考虑包级访问。）

可以使用包含关键字 `super` 的方法调用表达式 (§15.12) 来访问被重写的方法。使用限定名或强制转换为父类类型对于访问被重写的方法是无效的。

在这方面，方法的重写与字段的隐藏不同。

`strictfp` 修饰符的存在与否对重写方法和实现抽象方法的规则完全没有影响。例如，允许非严格浮点（FP-strict）方法重写严格浮点方法，也允许严格浮点方法重写非严格浮点方法。

### 示例 8.4.8.1-1. 重写

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
}

class SlowPoint extends Point {
    int xLimit, yLimit;
    void move(int dx, int dy) {
        super.move(dx, dy);
        limit(dy, yLimit);
    }
    static int limit(int d, int limit) {
        return d > limit ? limit : d < -limit ? -limit : d;
    }
}
```

`SlowPoint` 类用自己的方法重写了 `Point` 类方法的声明，限制了点在每次调用方法时可以移动的距离。当为 `SlowPoint` 实例调用 `move` 方法时，`SlowPoint` 类中的重写定义始终会被调用，即使对 `SlowPoint` 对象的引用是从类型为 `Point` 的变量获取的。

### 8.4.8.1-2. 重写

重写使得子类能够扩展现有类的行为，例如例所示：

```java
import java.io.OutputStream;
import java.io.IOException;

class BufferOutput {
    private OutputStream o;
    BufferOutput(OutputStream o) { this.o = o; }
    protected byte[] buf = new byte[512];
    protected int pos = 0;
    public void putchar(char c) throws IOException {
        if (pos == buf.length) flush();
        buf[pos++] = (byte)c;
    }
    public void putstr(String s) throws IOException {
        for (int i = 0; i < s.length(); i++)
            putchar(s.charAt(i));
    }
    public synchronized void flush() throws IOException { 
        // implementation omitted
    }
}

class LineOutput extends BufferOutput {
    LineOutput(OutputStream o) { super(o); }
    @Override
    public void putchar(char c) throws IOException {
        if (pos == buf.length) flush();
        buf[pos++] = (byte)c;
    }
}
```

*(注：提供的原文片段存在严重的 OCR 错误和碎片，我根据 Java 逻辑和提供的代码片段进行了重构，使其成为完整的示例。)*

`BufferOutput` 类实现了一个带缓冲的 `OutputStream`，当缓冲区满时执行 `flush`。在 `LineOutput` 的 `putchar` 方法中，字符参数是换行符。该示例重写的关键点是 `putstr` 定义在 `BufferOutput` 中。

因此，`putstr` 是通过 `LineOutput` 引用被调用的。

该程序输出：
```
abc
```

### 8.4.8.2 隐藏（通过类方法）

如果一个类声明或继承了一个静态方法 $m$，则称 $m$ 隐藏了类 $c$ 的父类和接口中原本可访问的（6.6）方法 $m'$。

如果静态方法隐藏了实例方法，则是编译错误。

隐藏方法可以使用限定名或强制转换为父类类型或包含 `super` 的方法调用表达式来访问。

```java
class Super {
    static String greeting() { return "Goodnight"; }
    String name() { return "Richard"; }
}

class Sub extends Super {
    static String greeting() { return "Hello"; }
    String name() { return "Dick"; }
}

class Test {
    public static void main(String[] args) {
        Sub s = new Sub();
        System.out.println(s.name());
```



```java
System.out.println(s.greeting());

System.out.println(Super.greeting());

}
}
```

隐藏的类（静态）方法可以使用实际上包含该方法声明的引用来调用。在这方面，静态方法的隐藏与实例方法的重写不同。

## 类

## 方法声明

## 8.4

```java
Super s = new Sub();

System.out.println(s.greeting() + " " + s.name());
```

产生输出：

Goodnight, Dick

这是因为 `greeting()` 的调用使用了 `s` 的类型（即 `Super`）在编译时确定调用哪种方法，而 `name()` 的调用使用了 `s` 的类（即 `Sub`）在运行时确定调用哪种实例方法。

### 8.4.8.3 重写与隐藏的限制

如果返回类型为 `R1` 的方法声明 `d1` 重写或隐藏了返回类型为 `R2` 的另一个方法 `d2`，则 `d1` 必须是返回类型可替换的 (§8.4.5)，否则发生编译错误。

此规则允许协变返回类型 - 在重写方法时完善方法的返回类型。

如果 `R1` 不是 `R2` 的子类型，则会发生编译未检查警告，除非被 `@SuppressWarnings` (§9.6.4.5) 抑制。

重写或隐藏另一个方法的方法、实现接口中定义的抽象的方法，其抛出的异常不能多于被重写或隐藏方法的异常。

在这方面，方法的重写与字段的隐藏 (§8.3) 不同，因为允许一个字段隐藏另一个不同类型的字段。

更准确地说，假设 `B` 是一个类或接口，`A` 是 `B` 的超类或超接口，且 `B` 中的方法声明 `m2` 重写或隐藏了 `A` 中的方法声明 `m1`。那么：

- 如果 `m2` 具有包含任何抛出异常的 `throws` 子句，则 `m1` 必须也具有 `throws` 子句，否则发生编译错误。
- 对于 `m2` `throws` 子句中列出的每一个检查异常类型，该异常类本身或其父类型之一必须出现在 `m1` `throws` 子句的擦除 (§4.6.6) 中；否则发生编译错误。
- 如果 `m1` 未擦除的 `throws` 子句不包含 `m2` `throws` 子句中每个异常类型的父类型（在必要时根据 `m1` 的类型参数进行调整），则会发生编译未检查警告，除非被 `@SuppressWarnings` (§9.6.4.5) 抑制。

如果一个类型声明 $\tau$ 拥有成员方法 $m_1$，且在 $\tau$ 或其超类型中声明了方法 $m_2$，使得满足以下所有条件，则发生编译错误：

- $m_1$ 和 $m_2$ 具有相同的名称。
- $m_2$ 从 $\tau$ 可访问 (§6.6)。
- $m_1$ 的签名不是 $m_2$ 签名的子签名 (§8.4.2)。
- $m_1$ 的签名或某些方法 $m_1$（直接或间接）重写的方法的签名，与 $m_2$ 的签名或某些方法 $m_2$（直接或间接）重写的方法的签名具有相同的擦除。

这些限制是必要的，因为泛型是通过擦除实现的。上述意味着在同一个类中声明的相同名称的方法必须具有不同的擦除。它还意味着类型声明不能实现或扩展同一个泛型接口的两个不同调用。

重写或隐藏方法的访问修饰符提供的访问权限必须至少与被重写或隐藏的方法相同，如下：

- 如果被重写或隐藏的方法是 `public`，则重写或隐藏方法必须是 `public`；否则发生编译错误。
- 如果被重写或隐藏的方法是 `protected`，则重写或隐藏方法必须是 `protected` 或 `public`；否则发生编译错误。
- 如果被重写或隐藏的方法具有包级访问权限（package access），则重写或隐藏方法不能是 `private`；否则发生编译错误。

> 注意，在技术意义上，`private` 方法不能被重写或隐藏。这意味着子类可以声明一个与其中一个父类中的 `private` 方法签名相同的方法，且并不要求该方法的返回类型或 `throws` 子句与父类中 `private` 方法有任何关系。

### 示例 8.4.8.3-1 协变返回类型

以下声明在从 Java SE 5.0 开始的 Java 编程语言中是合法的：

```java
class C implements Cloneable {

    C copy() throws CloneNotSupportedException {

        return (C) clone();

    }

}

class D extends C implements Cloneable {

    D copy() throws CloneNotSupportedException {

        return (D) clone();

    }

}
```

重写的宽松规则还允许放宽实现接口的抽象类的条件。

### 示例 4.8.4.3-2. 返回类型导致的未检查警告

考虑：

```java
class StringSorter {

  // 将字符串集合转换为排序列表

  List toList(Collection c) {...}

}
```

并假设某些子类 `StringSorter`：

```java
class Overrider extends StringSorter {

  List toList(Collection c) {...}

}
```

现在，`StringSorter` 的作者决定生成代码：

```java
class StringSorter {

  // 将字符串集合转换为排序列表

  List<String> toList(Collection<String> c) {...}

}
```

`Overrider` 将收到一个未检查警告，因为返回类型 `List` 不是 `List<String>` 的子类型。

### 示例 8.4.8.3-3 因为 throws 导致的错误重写

此程序使用通常的形式声明 `BadException`：

```java
class BadException extends Exception {}

class Point {

    void move() throws BadException {}

}

class Superclass extends Point {

    void move() throws Exception {}

}

class Subclass extends Superclass {

    void move() throws Exception {}

}
```

这会导致编译错误，因为 `Subclass` 中的方法抛出的异常比 `Superclass` 中被重写的方法异常多。

## 8.4 方法声明

可能通过多种路径从接口继承相同的方法声明。这一事实不会引起任何困难，且其本身永远不会导致编译错误。

## 8.4.9 重载

如果类中的两个方法（无论是在同一个类中声明的，还是都被类继承的，或者是一个声明、一个继承）具有相同的名称且不具重写等效（override-equivalent）的签名，则该方法名被称为重载。

这一事实不会引起任何困难，且其本身永远不会导致编译错误。两个同名方法的返回类型或 `throws` 子句之间没有强制的关系，除非它们的签名是重写等效的。

当调用方法 (§15.12) 时，在编译时将使用参数的实际数量（以及任何显式类型参数）和参数的编译时类型来确定将调用的方法签名 (§15.12)。如果要调用的方法是实例方法，则将使用动态方法查找 (§15.24) 在运行时确定要调用的实际方法。

### Example 8.4.9-1. 重载

```java
class Point {

    float x, y;

    void move(int dx, int dy) { x += dx; y += dy; }

    void move(float dx, float dy) { x += dx; y += dy; }

    public String toString() { return "("+x+","+y+")"; }

}
```

在这里，类 `Point` 具有相同名称 `move` 的方法。对于任何特定调用，选定的 `Point` 类重载方法是在编译时通过 §15.12 中的重载解析程序确定的。

总的来说，`Point` 类的成员包括在 `Point` 中声明的 `float` 实例变量 `x` 和 `y`、两个声明的方法、`toString` 方法，以及 `Point` 从其隐式直接父类 `Object` (§4.3.2) 继承的成员，例如方法 `hashCode()`。注意，`Point` 没有继承 `Object` 类的 `toString` 方法，因为该方法被 `Point` 类中 `toString` 方法的声明重写了。

### Example 8.4.2. 重载、重写与隐藏

```java
class Point {

    int x = 0, y = 0;

    void move(int dx, int dy) { x += dx; y += dy; }

    int color;

}

class RealPoint extends Point {

    float x = 0.0f, y = 0.0f;

    void move(int dx, int dy) { move((float)dx, (float)dy); }

    void move(float dx, float dy) { x += dx; y += dy; }

}
```

在这里，`RealPoint` 类用自己的 `float` 实例变量 `x` 和 `y` 隐藏了 `Point` 类实例变量 `x` 和 `y` 的声明，并用自己的 `move` 方法重写了 `move` 方法。它还通过另一个不同签名的方法重写了名称 `move` (8.4.2)。

在这个示例中，`RealPoint` 类成员包括从 `Point` 类继承的实例变量 `color`、在 `RealPoint` 中声明的 `float` 变量 `x` 和 `y` 以及在 `RealPoint` 中声明的两个 `move` 方法。

对于此特定调用，选择 `RealPoint` 哪个重载 `move` 方法将在编译时通过 15.12 中描述的重载解析程序确定。

以下是前面程序的扩展版本：

```java
class Point {

  int x = 0, y = 0, color;

  void move(int dx, int dy) { x += dx; y += dy; }

  int getX() { return x; }

  int getY() { return y; }

}

class RealPoint extends Point {

  float x = 0.0f, y = 0.0f;

  void move(int dx, int dy) { move((float)dx, (float)dy); }

  void move(float dx, float dy) { x += dx; y += dy; }

  float getX() { return x; }

  float getY() { return y; }

}
```

在这里，`RealPoint` 类提供了 `getX` 和 `getY` 来返回其字段 `x` 和 `y` 的值；`RealPoint` 类通过声明具有相同签名的方法重写了这些方法。结果是在编译时产生两个错误，每个各一个，因为返回类型不匹配；`Point` 类中的方法返回 `int` 类型的值，但 `RealPoint` 类中尝试重写的方法返回 `float` 类型的值。

此程序纠正了前面程序的错误：

```java
class Point {

  int x = 0, y = 0;

  void move(int dx, int dy) { x += dx; y += dy; }

  int getX() { return x; }

  int getY() { return y; }

  int color;

}

class RealPoint extends Point {

    float x = 0.0f, y = 0.0f;

    void move(int dx, int dy) { move((float)dx, (float)dy); }

    void move(float dx, float dy) { x += dx; y += dy; }

    int getX() { return (int)Math.floor(x); }

    int getY() { return (int)Math.floor(y); }

}
```

`RealPoint` 类中的重写方法 `getX` 和 `getY` 与 `Point` 类的返回类型相同... [注：提供的 OCR 文本在后几页包含大量重复和乱码部分，我已根据上下文清理了逻辑流]。

## 8.5 静态成员声明

`static` 关键字可以修饰非内部类或接口 `T` 体内成员类型 `c` 的声明。其作用是声明 `c` 不是内部类。正如 `T` 的静态方法在其体中没有 `T` 的当前实例一样，`c` 也没有 `T` 的当前实例，也没有任何词法封闭实例。

如果静态类包含对外部类非静态成员的使用，则为编译错误。

成员接口是隐式静态的 (§9.1.1)。成员接口的声明允许冗余指定 `static` 修饰符。

## 8.6 实例初始化器

类中定义的实例初始化器在类实例化时执行 (§12.5, §15.9, §8.7.1)。

```
InstanceInitializer: Block
```

如果实例初始化器无法正常完成，则为编译错误 (§14.22)。

如果在实例初始化器的任何地方出现返回语句 (§14.17)，则为编译错误。

实例初始化器允许使用 `this` 关键字 (§15.8.3) 或 `super` 关键字 (§15.11.2, §15.12) 来引用当前对象，并使用作用域内的任何类型变量。

实例初始化器引用实例变量的方式限制（即使是在初始化器中引用实例变量）在 §8.3.3 中规定。

实例初始化器的异常检查在 §11.2.3 中规定。

## 8.7 静态初始化器

在类中声明的静态初始化器在类初始化时执行 (§12.4.2)。与类变量的任何字段初始化器 (§8.3.2) 一起使用，静态初始化器可用于初始化类的类变量。

```
StaticInitializer:
static Block
```

如果静态初始化器无法正常完成 (§14.22)，则为编译错误。

如果在静态初始化器内部的任何地方出现返回语句 (§14.17)，则为编译错误。

如果在静态初始化器内部的任何地方出现 `this` 关键字 (§15.8.3) 或 `super` 关键字 (§15.11, §15.12) 或任何在静态初始化器之外声明的类型变量，则为编译错误。

关于静态初始化器如何引用类变量的限制（即使类变量在作用域内）规定在 §8.3.3 中。

静态初始化器的异常检查规定在 §11.2.3 中。

## 8.8 构造方法声明

构造方法用于创建类的实例对象 (§12.5, §15.9)。

```
ConstructorDeclaration:
{ConstructorModifier} ConstructorDeclarator [Throws] ConstructorBody

ConstructorDeclarator:
[TypeParameters] SimpleTypeName
([ReceiverParameter , ] [FormalParameterList])

SimpleTypeName:
TypeIdentifier
```

本节中的规则适用于所有类声明中的构造方法，包括枚举声明。然而，枚举声明对于构造方法修饰符、构造方法体和默认构造方法有特殊规则；这些规则规定在 §8.9.2 中。

### 构造方法声明

`ConstructorDeclarator` 中的 `SimpleTypeName` 必须是包含构造方法声明的类的简单名称，否则将发生编译错误。

在其他所有方面，构造方法声明看起来就像一个没有结果的方法声明 (§8.4.5)。

构造方法声明不是成员。它们永远不会被继承，因此不受隐藏或重写（overriding）的影响。

构造方法通过类实例创建表达式 (§15.9)、由字符串拼接运算符 `+` 声明的字符串及其拼接 (§15.18.1)，以及来自其他构造方法的显式构造方法调用 (§8.8.7) 来触发。对构造方法的访问受访问修饰符 (§6.6) 支配，因此可以通过声明不可访问的构造方法 (§8.8.10) 来防止类的实例化。

构造方法永远不会通过方法调用表达式 (§15.12) 触发。

### 示例 8.8-1. 构造方法声明

```java
class Point {

    int x, y;

    Point(int x, int y) { this.x = x; this.y = y; }

}
```



# 8.8 构造器声明

## 8.8.1 形式参数

构造方法的形式参数在语法和语义上与方法的参数相同（§8.4.1）。

非私有内部成员类的构造方法隐式地声明第一个参数为代表该类的直接闭包实例的变量（§15.9.2, §15.9.3）。

> 为什么只有这类类具有隐式声明的构造方法的原理是微妙的。以下解释可能有所帮助：

1. 在非私有内部成员类的实例创建中，§15.9.2 规定了成员类的直接闭包实例。该成员类可能由一个与类实例创建编译器不同的编译器生成。因此，创建表达式的编译器必须有一个标准，将引用（代表直接闭包实例）传递给成员类的构造方法。因此，Java 语言认为非私有内部类的构造方法隐式地声明了直接闭包实例的初始参数：§15.9.3 规定该实例被传递给构造方法。

2. 在局部类（不在静态上下文中）或匿名类的实例创建中，§15.9.2 规定了局部/匿名类的直接闭包实例。局部/匿名类必然是由与类实例表达式相同的编译器生成的。该编译器可以以其希望的任何方式表示直接闭包实例。Java 编程语言不需要在局部/匿名类的构造方法中隐式地声明参数。

3. 在匿名类的实例表达式中，且当匿名类的父类是内部类或局部类（不在静态上下文中）时，§15.9.2 规定了匿名类相对于其父类的匿名类直接闭包实例。该实例必须从匿名类传输到其父类，在父类中它将作为直接闭包实例。由于父类可能由与类实例创建表达式不同的编译器生成，因此有必要以标准方式传输实例，将其作为第一个参数传递给父类构造方法。注意，匿名类本身必然由类实例表达式生成，因此必须由编译器以其希望的任何方式将相对于父类的直接闭包实例传递给匿名类，然后由匿名类将实例传递给父类的构造方法。然而，为了保持一致性，Java 语言在 §15.9.5.1 中认为，在某些情况下，匿名类的构造方法声明了相对于父类的直接闭包实例的初始参数。

非私有内部成员类可能被与其不同的编译器访问，而局部类或匿名类始终由编译它的编译器访问，这解释了为什么非私有内部类的二进制名被定义为可预测的，而局部或匿名类的二进制名不可预测（§13）。

## 8.8.2 构造方法签名

在类中声明两个重写等签名（§8.4.2）的构造方法是编译错误。

在类中声明两个签名相同（§4.6）的构造方法是编译错误。

## 8.8.3 构造方法修饰符

```
ConstructorModifier:
(one of)
public protected private
```

构造方法上注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。

如果同一个关键字作为修饰符出现多次，或者构造方法具有多个访问修饰符（`public`、`protected`、`private`），则为编译错误。

在普通类声明中，没有访问修饰符的构造方法具有包访问权限。

与方法不同，习惯上（尽管不是强制）它们的顺序与上述 `MethodModifier` 的产生式一致。与方法不同，构造方法不能是 `abstract`、`static`、`final`、`native`、`strictfp` 或 `synchronized`：

- 构造方法不被继承，因此不需要声明。
- 抽象构造方法无法实现。
- 构造方法总是相对于对象调用的，因此构造方法为静态的没有意义。
- 构造方法通常不需要同步，因为它会锁定正在构建的对象，而该对象在所有构造方法完成工作之前通常不可用。
- 没有原生构造方法是一种任意的语言设计选择，使得 Java 虚拟机实现能够验证父类构造方法的调用。
- 不能将构造方法声明为 `strictfp`（与方法 §8.4.3 相比）是一种刻意的语言设计选择；它实际上确保了构造方法是严格严格的当且仅当其类是严格严格的（§15.4）。

## 8.8.4 泛型构造方法

如果构造方法声明了一个或多个类型变量（§§4.4），则它是泛型的。

这些类型变量被称为构造方法的类型参数。泛型构造方法的类型参数部分的形式与泛型类的类型参数部分相同（§8.1.2）。

即使类本身不是泛型的，构造方法也可以是泛型的。

泛型构造方法声明定义了一组构造方法，对应类型参数部分的每可能的调用。调用泛型构造方法时，可能不需要显式提供类型参数，因为它们通常可以被推断（§18）。

## 8.8.5 构造方法抛出异常

构造方法的 `throws` 子句在结构和行为上与方法的 `throws` 子句（§8.4.6）完全相同。

## 8.8.6 构造方法的类型

构造方法的类型由其签名和其 `throws` 子句提供的异常类型组成。

## 8.8.7 构造方法体

构造方法体的第一条语句可以是对同类或其直接父类的另一个构造方法的显式调用（§8.8.7.1）。

```
ConstructorBody: {ExplicitConstructorInvocation][BlockStatements}
```

构造方法通过一系列一个或多个涉及 `this` 的显式构造方法调用来直接或间接调用自己，这会导致编译时错误。

如果构造方法体不是以显式构造方法调用开头，且所声明的构造方法不是原始类 `Object` 的一部分，则该构造方法隐式地从父类构造方法调用 `super();` 开始，即对其直接父类的无参数构造方法的调用。

除了显式构造方法调用的可能性以及显式返回一个值（§14.17）外，构造方法体与方法的体（§8.4.7）相似。

构造方法体可以使用 `return` 语句（§14.17），前提是它不包含表达式。

### 8.8.7.1 显式构造方法调用

```
ExplicitConstructorInvocation:
    [TypeArguments] this ([ArgumentList])
    | [TypeArguments] super ([ArgumentList])
    | ExpressionName [TypeArguments] super ([ArgumentList])
    | Primary [TypeArguments] super ([ArgumentList])
```

为了方便起见，这里展示了 §4.5.1 和 §8.12 中的产生式：

```
TypeArguments: <TypeArgument>
ArgumentList: Expression , Expression
```

显式构造方法调用语句分为两种：

- 备用构造方法调用以关键字 `this` 开头（前面可能带有类型参数）。它们用于调用同类的备用构造方法。
- 父类构造方法调用以关键字 `super`（前面可能带有类型参数）或一个 `Primary` 表达式开头。它们用于调用直接父类的构造方法。它们进一步分为：
    - 未限定的父类构造方法调用以关键字 `super` 开头（前面可能带有类型参数）。
    - 限定的父类构造方法调用以 `Primary` 表达式或 `ExpressionName` 开头。它们允许子类构造方法显式指定相对于父类的新创建对象的直接封装实例（§8.1.3）。

构造方法体中的显式构造方法调用语句不能引用在该类或父类中声明的任何实例变量、方法或内部类，也不能在任何表达式中使用 `this` 或 `super`；否则，将发生编译时错误。如果 `this` 或 `super` 左侧存在 `TypeArguments`，则如果任何参数为通配符，则会导致编译时错误（§4.5.1）。

令 `s` 为父类。如果父类构造方法调用是未限定的，那么：

- 如果 `s` 是内部类，或者 `s` 在该类或父类的上下文中，则会导致编译时错误。

如果父类构造方法调用是限定的，那么：

- 如果 `s` 是内部类，或者 `s` 在静态上下文中，则会导致编译时错误。
- 否则，令 `p` 为 `Primary` 表达式或 `ExpressionName`，令 `o` 为 `s` 的直接封装实例（§6.6）。

构造方法调用可能抛出的异常类型在 §11.2 中规定。备用构造方法调用的评估过程如下：

1. 如果 `p` 评估为 `null`，则抛出 `NullPointerException`，且构造方法调用完成。
2. 否则，评估结果是相对于 `s` 的直接封装实例。对于 `o`，父类构造方法调用的评估通过对参数进行评估（与普通方法调用相同），然后调用构造方法。
3. 最后，如果父类构造方法调用正常完成，则 `c` 的所有实例变量初始化和实例初始化将被执行。如果实例变量初始化 `i` 在实例初始化 `j` 之前，则 `i` 在 `j` 之前执行。

无论父类构造方法调用是作为显式构造方法调用语句还是隐式提供的，实例变量初始化和实例初始化化的都会执行。

### 示例 8.8.7.1-1. 构造方法调用限制

如果将 §8.8.7 中 `ColoredPoint` 的第一个构造方法更改如下：

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}

class ColoredPoint extends Point {
    static final int WHITE = 0, BLACK = 1;
    int color;
    ColoredPoint(int x, int y, color) {
        this(x, y); // 将 WHITE 改为 color
    }
    ColoredPoint(int x, int y, int color) {
        super(x, y);
        this.color = color;
    }
}
```

将发生编译时错误，因为实例变量 `color` 不能被显式构造方法调用使用。

### 示例 8.8.7.1-2. 限定的父类构造方法调用

在代码中，`ChildOfInner` 没有词法封装类型声明，因此 `ChildInner` 的实例没有封装实例。然而，`ChildInner` 的父类（`Inner`）有一个词法封装类型声明（`Outer`），且 `Inner` 的实例有一个 `Outer` 的封装实例。`Outer` 的封装实例在创建 `Inner` 实例时被设置。因此，当我们创建 `ChildInner` 实例（它隐式是 `Inner` 的实例）时，必须通过 `ChildOfInner` 构造方法中的限定父类构造方法调用来提供 `Outer` 实例。

```java
class Outer {
    class Inner {}
}

class ChildOfInner extends Outer.Inner {
    ChildOfInner() { new Outer().super(); }
}
```

可能令人惊讶的是，同一个 `Outer` 实例可以作为多个 `ChildOfInner` 实例相对于 `Inner` 的直接封装实例。

下面的程序通过将 `Outer` 的实例传递给 `ChildOfInner` 构造器来实现这一点。显式构造器调用的规则不允许使用构造器的形式参数。

```java
class Outer {
    int secret = 5;
    class Inner {
        int getSecret() { return secret; }
        void setSecret(int s) { secret = s; }
    }
}

class ChildOfInner extends Outer.Inner {
    ChildOfInner(Outer x) { super(); }
}

public class Test {
    public static void main(String[] args) {
        Outer x = new Outer();
        ChildOfInner a = new ChildOfInner(x);
        System.out.println(a.getSecret());
        a.setSecret(6);
        System.out.println(a.getSecret());
    }
}
```

该程序输出：

```
5
6
```

结果是，可以通过对 `ChildOfInner` 的引用操作 `Outer` 的实例变量，尽管这些引用在传统意义上并不是别名。

## 8.8.8 构造器重载

构造器的重载行为与方法的重载相同（§8.4.9）。重载在编译时通过每个类实例进行解析（§15.9）。

## 8.8.9 默认构造器

如果一个类没有构造器声明，则会隐式声明一个默认构造器。顶级类、成员类或局部类的默认构造器形式如下：

- 默认构造器具有与类相同的访问修饰符，除非类缺少访问修饰符，此时默认构造器具有包访问权限（§6.6）。
- 默认构造器没有形式参数，除非是非私有内部成员类，此时默认构造器隐式声明了一个表示该类的形式参数（8.8.1、15.9.2、15.9.3）。
- 默认构造器没有 `throws` 子句。
- 如果声明的类是 `Object`，则默认构造器的体为空。否则，默认构造器简单地调用无参数的父类构造器。

匿名类的默认构造器形式在 §15.9.5 中指定。

如果隐式声明了默认构造器但父类没有无参数且没有 `throws` 子句的构造器，则会导致编译错误。

### 示例 8.8.9-1. 默认构造器

声明：

```java
public class Point {
    int x, y;
}
```

等同于声明：

```java
public class Point {
    int x, y;
    public Point() { super(); }
}
```

其中默认构造器是 `public` 的，因为类 `Point` 是 `public`。

### 示例 8.8.9-2. 构造器与类的访问性

类的默认构造器的访问权限与类本身相同的规则是简单且直观的。然而，这并不意味着只要类是可见的，构造器就是可访问的。考虑：

```java
package p1;
public class Outer {
    protected class Inner { }
}

package p2;

class SonOfOuter extends p1.Outer {
    void foo() {
        new Inner(); // 编译访问错误
    }
}
```

`Inner` 的默认构造器是 `protected` 的。然而，该构造器相对于 `Inner` 是保护的，而 `Inner` 相对于 `Outer` 是保护的。因此，`Inner` 在 `SonOfOuter` 中是可见的，因为它是 `Outer` 的子类。`Inner` 的构造器在 `SonOfOuter` 中是不可访问的，因为 `SonOfOuter` 类并不是 `Inner` 的子类！因此，尽管 `Inner` 是可见的，它的默认构造器也是不可访问的。

## 8.8.10 防止类的实例化

可以设计一个类来防止类声明之外的代码创建类的实例：通过声明至少一个构造器防止创建默认构造器，并将所有构造器声明为私有（§6.6.1）。

`public` 类同样可以通过声明至少一个构造器来防止包外创建实例，防止创建具有包访问权限的默认构造器，并且不声明任何 `public` 或 `protected` 的构造器（§6.6.2）。

> 示例 8.8.10-1. 通过构造器访问性防止实例化

```java
class ClassOnly {
    private ClassOnly() { }
    static String just = "only the lonely";
}
```

在这里，以下代码中 `ClassOnly` 类无法被实例化：

```java
package just;
public class PackageOnly {
    PackageOnly() { }
    String[] justDesserts = {"cheesecake", "ice cream"};
}
```

`public` 类 `PackageOnly` 只能在其声明的包 `just` 中被实例化。如果 `PackageOnly` 的构造器是 `protected` 的，该限制也适用，尽管在这种情况下，其他包的代码可能实例化 `PackageOnly` 的子类。

# 8.9 枚举类型

枚举声明指定了一个新的枚举类型，一种特殊的类类型。

### EnumDeclaration:

```
[ConstantModifier] enum Type[interfaces] EnumBody
```

## 8.9.1 枚举常量

枚举的体可以包含枚举常量。一个枚举常量定义了枚举的一个实例。

### EnumBody:

```
{ [ConstantList] [EnumDeclarations] }
```

### ConstantList:

```
EnumConstant {, EnumConstant}
```

### EnumConstant:



# 枚举类型

## 语法定义

```
[ConstantModifier] Identifier ([ArgumentList]) [ClassBody]
```

### 枚举常量修饰符

```
EnumConstantModifier:
Annotation
```

### 参数列表

```
ArgumentList:
Expression [ , Expression]
```

枚举常量上的注解修饰符规则在 §9.7.4 和 §9.7.5 中。

`EnumConstant` 中的 `Identifier` 可以作为名称引用该枚举常量。

枚举常量的作用域和隐藏在 §6.3 和 §6.4 中。

枚举常量后面可以跟随参数，在类初始化期间这些参数传递给枚举的构造器。如果省略参数，则假设一个空列表。所调用的构造器使用标准的重载解析规则（§15.12.2）。

枚举常量的可选类体隐式定义了一个扩展直接枚举类型的匿名类声明（§15.9.5）。类体受匿名类的通常规则限制；特别是它不能包含任何构造器。在这些类体中定义的实例方法只有在覆盖了封装枚举类的可访问方法时，才能在外部调用（§8.4.8）。

枚举类体声明抽象方法会导致编译错误。

由于每个枚举常量只有一个实例，在 `equals` 方法中比较两个对象引用时，如果已知至少一个引用指向枚举常量，则允许使用 `==` 运算符。

> `Enum` 中的 `equals` 方法是一个 `final` 方法，它仅仅对其参数调用 `super.equals` 并返回结果，执行这种恒等比较。

除了编译错误外，三种进一步机制确保不存在定义之外的实例：

- `Enum` 中的 `clone` 方法确保枚举常量永远无法被克隆。
- 禁止反射实例化枚举类型。
- 序列化机制的特殊处理确保不会反序列化产生重复实例。

## 8.9.2 枚举体声明

除了枚举常量，枚举声明的体还可以包含构造器和成员声明以及实例和静态初始化器。

```
EnumBodyDeclarations:
; [ClassBodyDeclaration]
```

为了方便起见，此处展示了 §8.1.6 中的后续内容：

```
ClassBodyDeclaration:
ClassMemberDeclaration
InstanceInitializer
StaticInitializer
ConstructorDeclaration

ClassMemberDeclaration:
FieldDeclaration
MethodDeclaration
ClassDeclaration
InterfaceDeclaration
```

除非另有说明，枚举声明体中的任何构造方法声明或成员声明对枚举类型的作用，与它们在普通类声明体中存在时的作用完全相同。

如果枚举声明中的构造方法声明为 `public` 或 `protected`（§6.6），则会导致编译时错误。

如果枚举声明中的构造方法声明包含对父类构造方法的调用（§8.8.7），则会导致编译时错误。

如果从枚举类型的构造方法、实例初始化器或实例变量初始化器引用该枚举类型的静态字段，除非该字段是一个常量变量（§4.12.4），否则会导致编译时错误。

在枚举声明中，没有访问修饰符的构造方法声明是 `private` 的。

> 在实践中，编译器可能会通过在枚举类型的默认构造方法中声明 `String` 和 `int` 参数来镜像 `Enum` 类型。然而，这些参数并没有被指定为“隐式声明”，因为不同的编译器不需要对默认构造的形式达成一致。只有枚举类型的编译器知道如何实例化枚举常量；其他编译器可能简单地依赖枚举类型隐式声明的 `public static` 字段（§8.9.3），而不忽略这些字段是如何初始化的。

如果枚举声明 E 有抽象方法作为成员，则会导致编译时错误，除非 E 至少有一个枚举常量，且 E 的所有枚举常量都具有提供 m 具体实现的方法体。

枚举声明声明一个终结器方法（finalizer）（§12.6）会导致编译时错误。枚举类型的实例永远无法被终结化。

### 示例 8.9.2-1. 枚举体成员声明

```java
enum Coin {
  PENNY(1), NICKEL(5), DIME(10), QUARTER(25);

  Coin(int value) { this.value = value; }

  private final int value;

  public int value() { return value; }
}
```

每个枚举常量通过构造方法传递在 `value` 字段中对应不同的值。该字段代表美国硬币以分值为单位的值。注意，对于枚举类型可以声明的参数没有任何限制。

### 示例 8.9.2-2. 枚举常量自引用的限制

如果没有关于静态访问的规则，看似合理的代码将因为枚举类型中的初始化循环性而在运行时失败。（任何具有“自类型”静态字段的类中都存在循环性。）以下是此类会失败的代码示例：

```java
import java.util.Map;
import java.util.HashMap;

enum Color {
  RED, GREEN, BLUE;

  Color() { colorMap.put(toString(), this); }

  static final Map<String, Color> colorMap =
    new HashMap<String, Color>();
}
```

此枚举 `colorMap` 的静态初始化将抛出 `NullPointerException`，因为在枚举常量构造方法运行时，静态变量尚未初始化。该限制确保了此类代码无法编译。然而，代码可以很容易地重构以正常工作。

```java
import java.util.Map;
import java.util.HashMap;

enum Color {
  RED, GREEN, BLUE;

  static final Map<String, Color> colorMap =
    new HashMap<String, Color>();

  static {
    for (Color c : Color.values()) {
      colorMap.put(c.toString(), c);
    }
  }
}
```

重构后的版本显然是正确的，因为静态初始化是从上到下发生的。

## 8.9.3 枚举成员

枚举类型 E 的成员包含所有以下内容：

- 在 E 的声明体体中声明的成员。
- 继承自 `Enum<E>` 的成员。
- 对于 E 声明体中声明的每个枚举常量 `c`，E 都有一个类型为 E 的隐式声明 `public static final` 字段，其名称与 `c` 相同。该字段有一个变量初始化器，该初始化器实例化 E 并将 `c` 的任何参数传递给为 E 选择的构造方法。该字段具有与 `c` 相同的注解（如果有的话）。

这些字段的隐式声明顺序与相应的枚举常量顺序相同，并且位于 E 声明体中显式声明的任何静态字段之前。

当相应的隐式声明字段被初始化时，认为该枚举已创建。

- 一个隐式声明的方法 `public static E[] values()`，它返回一个包含 E 的枚举常量的数组，顺序与它们在 E 的声明体中出现的顺序相同。
- 一个隐式声明的方法 `public static E valueOf(String name)`，它返回具有指定名称的 E 枚举常量。

因此，枚举类型 E 的声明不能包含与 E 的枚举常量对应的隐式声明字段冲突的字段，也不能包含与隐式声明方法冲突的或覆盖 `Enum<E>` 类中 `final` 方法的方法。

### 示例 8.9.3-1. 遍历枚举常量

```java
class Test {
    enum Season { WINTER, SPRING, FALL }

    public static void main(String args) {
        for (Season s : Season.values()) {
            System.out.println(s);
        }
    }
}
```

该程序输出：
```
WINTER
SPRING
FALL
```

### 示例 8.9.3-2. 枚举常量切换

使用 `switch` 语句处理枚举常量是安全的，它为枚举类型添加了 `switch` 打印了以分值为单位的美国硬币的 `value()` 方法。

```java
class Test {
    enum Coin { PENNY, NICKEL, DIME, QUARTER }

    static String color(Coin c) {
        switch (c) {
            case PENNY:
                return "COPPER";
            case NICKEL:
                return "NICKEL";
            case DIME:
                return "DIME";
            case QUARTER:
                return "SILVER";
            default:
                throw new AssertionError("Unknown coin: " + c);
        }
    }

    public static void main(String[] args) {
        for (Coin c : Coin.values()) {
            System.out.println(c + "\t" + color(c));
        }
    }
}
```

该程序输出：
```
PENNY	COPPER
NICKEL	NICKEL
DIME	DIME
QUARTER	SILVER
```

### 示例 8.9.3-3. 带有方法的常量

```java
enum Operation {
    // 每个常量支持算术运算
    abstract double eval(double x, double y);

    PLUS {
        double eval(double x, double y) { return x + y; }
    },
    MINUS {
        double eval(double x, double y) { return x - y; }
    },
    TIMES {
        double eval(double x, double y) { return x * y; }
    },
    DIVIDED_BY {
        double eval(double x, double y) { return x / y; }
    }

    public static void main(String args[]) {
        double x = Double.parseDouble(args[0]);
        double y = Double.parseDouble(args[1]);
        for (Operation op : Operation.values()) {
            System.out.println(x + " " + op + " " + y + " = " + op.eval(x, y));
        }
    }
}
```

运行程序 `Operation 2.0 4.0` 输出：

```
2.0 PLUS 4.0 = 6.0
2.0 MINUS 4.0 = -2.0
2.0 TIMES 4.0 = 8.0
2.0 DIVIDED_BY 4.0 = 0.5
```

这种在基类型（`Operation`）中使用 `switch` 语句的模式要安全得多，因为它消除了忘记为新常量添加行为的可能性（因为枚举声明会导致编译时错误）。

### 示例 8.9.3-4. 多重枚举类型

在以下程序中，纸牌类构建在两个简单枚举之上。

```java
import java.util.List;
import java.util.ArrayList;

class Card implements Comparable<Card> {
    java.io.Serializable

    public enum Rank { DEUCE, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, JACK, QUEEN, KING, ACE }
    public enum Suit { CLUBS, DIAMONDS, HEARTS, SPADES }

    private final Rank rank;
    private final Suit suit;

    public Rank rank() { return rank; }
    public Suit suit() { return suit; }

    private Card(Rank rank, Suit suit) {
        if (rank == null || suit == null)
            throw new NullPointerException(rank + ", " + suit);
        this.rank = rank;
        this.suit = suit;
    }

    public String toString() { return rank + " of " + suit; }

    // 先按花色排序，再按点数排序
    public int compareTo(Card c) {
        int suitCompare = suit.compareTo(c.suit);
        return (suitCompare != 0) ? 
            suitCompare :
            rank.compareTo(c.rank);
    }

    private static final List<Card> prototypeDeck = 
        new ArrayList<Card>(52);

    static {
        for (Suit suit : Suit.values()) {
            for (Rank rank : Rank.values()) {
                prototypeDeck.add(new Card(rank, suit));
            }
        }
    }

    // 返回一个新的牌组
    public static List<Card> newDeck() {
        return new ArrayList<Card>(prototypeDeck);
    }
}
```

下面的程序演示了 `Card` 类。它在命令行上接收两个整数参数，分别代表要发的牌数和每手牌的牌数。

```java
import java.util.List;
import java.util.ArrayList;
import java.util.Collections;

class Deal {
    public static void main(String[] args) {
        int numHands = Integer.parseInt(args[0]);
        int cardsPerHand = Integer.parseInt(args[1]);

        List<Card> deck = Card.newDeck();
        Collections.shuffle(deck);

        for (int i = 0; i < numHands; i++) {
            System.out.println(dealHand(deck, cardsPerHand));
        }
    }

    /**
     * 返回包含最后 n 个元素的新 ArrayList，这些元素已从原列表中移除。
     * 返回的结果使用自然排序。
     */
    public static <E extends Comparable<E>> List<E> dealHand(List<E> deck, int n) {
        int deckSize = deck.size();
        List<E> handView = deck.subList(deckSize - n, deckSize);
        ArrayList<E> hand = new ArrayList<E>(handView);
        handView.clear();
        Collections.sort(hand);
        return hand;
    }
}
```

程序产生输出：

```
java Deal 4 3
[DEUCE OF CLUBS, SEVEN OF CLUBS, QUEEN OF DIAMONDS]
[NINE OF HEARTS, FIVE OF SPADES, ACE OF SPADES]
[THREE OF HEARTS, SIX OF HEARTS, TEN OF SPADES]
[TEN OF CLUBS, NINE OF DIAMONDS, THREE OF SPADES]
```



## 第 9 章 接口

接口声明引入了一种新的引用类型，其成员可以是类、接口、常量和方法。该类型没有实例变量，并且通常会声明一个或多个 `abstract` 方法；否则，不相关的类可以通过提供对其 `abstract` 方法的实现来实现接口。接口不能被直接实例化。

**嵌套接口**（nested interface）是指任何位于另一个类体内的接口。

**顶层接口**（top level interface）不是嵌套接口的接口。

我们区分两种接口——普通接口和注解类型。

本章讨论了所有接口的共同语义——普通接口（包括顶层 $7.6$ 和嵌套 $8.5$）以及注解类型 ($9.6$）。针对特定类型接口的细节将在专门讨论这些构造的节中进行讨论。

程序可以使用接口，使得相关类无需共享共同的 `abstract` 超类，或无需向 `Object` 添加方法。

接口可以被声明为一个或多个接口的*直接扩展*（direct extension），这意味着它继承了所扩展接口的所有成员类型、实例方法和常量，但被覆盖或隐藏的成员除外。

类可以被声明为*直接实现*（directly implement）一个或多个接口，这意味着该类的任何实例都实现了该接口或多个接口指定的所有 `abstract` 方法。类必然实现其直接父类和直接父接口所实现的所有接口。这种（多重）接口继承允许对象在不共享超类的情况下支持（多重）共同行为。

声明类型为接口类型的变量，其值可以是实现指定接口的类的任何实例的引用。仅仅该类恰好实现了该接口的所有抽象方法是不够的；该类或其某个父类必须实际上被声明为实现了该接口，否则该类不被认为实现了该接口。

## 9.1 接口声明

接口声明指定了一个新的命名引用类型。接口声明有两种类型——普通接口声明和注解类型声明 (§9.6)。

```
InterfaceDeclaration:
    NormalInterfaceDeclaration
    AnnotationTypeDeclaration
```

```
NormalInterfaceDeclaration:
    [InterfaceModifier] interface TypeIdentifier [TypeParameters]
    [ExtendsInterfaces] InterfaceBody
```

接口声明中的 `TypeIdentifier` 指定了接口的名称。
如果接口与它的任何一个内部类或接口具有相同的简单名，则为编译错误。
接口声明的作用范围在 §6.3 和 §6.4 中规定。

### 9.1.1 接口修饰符

接口声明可以包含接口修饰符。

```
InterfaceModifier:
    (其一)
    Annotation public protected private
    abstract static strictfp
```

接口声明中注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

访问修饰符 `public` (§6.6) 适用于各种接口声明。

访问修饰符 `protected` 和 `private` 仅适用于声明被直接包含在类声明内部的成员接口 (§8.5.1)。

修饰符 `static` 仅适用于成员接口 (§8.5.1, 9.5)，而不适用于顶层接口 (§7.6)。

如果同一个关键字作为接口声明的修饰符出现多次，或者一个声明具有多个 `public`、`protected` 和 `private` 访问修饰符 (§6.6)，则为编译错误。

如果接口声明中出现了两个或多个（不同的）接口修饰符，按照惯例（并非强制），它们出现的顺序应与上述 `InterfaceModifier` 产生式所示顺序一致。

#### 9.1.1.1 abstract 接口

每个接口都是隐式抽象的。

此修饰符已过时，不应在新程序中使用。

#### 9.1.1.2 strictfp 接口

`strictfp` 修饰符的作用是使接口内所有的浮点或双精度精度表达式都是显式严格的 (§15.4)。

这意味着在接口中声明的所有方法以及接口中声明的所有嵌套类型都是隐式的 `strictfp`。

### 9.1.2 泛型接口和类型参数

如果接口声明了一个或多个类型变量 (§4.4)，则该接口是泛型的。

这些变量被称为接口的类型参数。类型参数部分位于接口名称之后，并用尖括号分隔。

为了方便起见，这里展示了 §8.1.2 和 §4.4 的产生式：

```
TypeParameters:
    <ParameterList>

ParameterList:
    TypeParameter , TypeParameter

TypeParameter:
    [TypeModifier] TypeIdentifier [TypeBound]

TypeModifier:
    Annotation
```

类型参数声明中注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

在接口的类型参数部分中，如果 $s$ 是 $t$ 的边界，则 $t$ 直接依赖于 $s$，而 $t$ 依赖于 $s$ 或直接依赖于依赖 $s$ 的类型变量 $u$（递归使用此定义）。如果接口类型参数中的类型变量依赖于其自身，则为编译错误。

接口类型参数的作用范围和隐藏在 §6.3 中规定。

在泛型接口 `I` 的静态成员声明的任何位置引用其类型参数都是编译错误 (§9.3, §9.4, §9.5)。

泛型接口定义了一组参数化类型 (§4.5)，对于类型参数部分的每种可能的参数化都对应一种。所有这些参数化类型在运行时共享同一个接口。

### 9.1.3 父接口和子接口

如果提供了 `extends` 子句，被声明的接口将扩展每个其他命名的接口，并继承了每个其他命名的接口的成员类型、实例方法和常量。

这些其他命名的接口是被声明接口的直接父接口。

任何实现被声明接口的类也被认为实现了该接口所扩展的所有接口。

```
ExtendsInterfaces:
    extends InterfaceTypeList
```

为了方便起见，这里展示了 §8.1.5 的产生式：

```
InterfaceTypeList:
    InterfaceType (, InterfaceType)
```

接口声明中 `extends` 子句的每个 `InterfaceType` 必须命名一个可访问的接口类型 (§6.6)，否则发生编译错误。

如果 `InterfaceType` 具有类型参数，则它必须表示一个良好的参数化类型 (§4.5)，且其中任何参数都不能通配符类型参数，否则将发生编译时错误。

给定一个（可能是泛型的）接口声明 $I<F1,...,Fn>$ $(n \ge 0)$，接口类型 $I<F1,...,Fn>$ 的直接超接口是 $I$ 声明中 `extends` 子句中的类型（如果存在 `extends` 子句）。

给定一个泛型接口声明 $I<T1,...,Tn>$ $(n > 0)$，参数化类型 $I<Ti,...,Tp>$ 的直接超接口包括：当 $T_i$ $(1 \le i \le n)$ 是一个类型时，所有类型 $J<U1,...,Un>$，其中 $U_i$ 是 $I<F1,...,Fn>$ 的直接超接口，且 $\theta$ 是替换方案 $[F1:=T1, ..., Fn:=Tn]$。

超接口关系是直接超接口关系的传递闭包。如果满足以下任一条件，则接口 $K$ 是接口 $I$ 的超接口：

- $K$ 是 $I$ 的直接超接口。
- 存在接口 $J$，使得 $K$ 是 $J$ 的超接口，且 $J$ 是 $I$ 的超接口（递归应用此定义）。

当 $K$ 是 $I$ 的超接口时，称接口 $I$ 是接口 $K$ 的子接口。

虽然每个类都是类 `Object` 的扩展，但并没有一个单一接口是所有接口的扩展。

如果类型 $T$ 出现在 $I$ 的 `extends` 子句中（作为超接口或作为接口名称全限定形式中的限定符），则称接口 $I$ 依赖于类型 $T$。

如果满足以下任一条件，则接口 $I$ 依赖于引用类型 $T$：

- $I$ 直接依赖于 $T$。
- $I$ 直接依赖于依赖 $T$ 的类 $C$ (§8.1.5)。
- $I$ 直接依赖于依赖 $T$ 的接口 $J$（递归应用此定义）。

如果接口依赖于自身，则会导致编译时错误。

如果在运行时加载接口时检测到循环声明的接口，则抛出 `ClassCircularityError` (§12.2.1)。

### 9.1.4 接口体与成员声明

接口体可以声明接口的成员，即字段 (§9.3)、方法 (§9.4)、类 (§9.5) 和接口 (§9.5)。

```
InterfaceBody:
    { InterfaceMemberDeclaration }

InterfaceMemberDeclaration:
    ConstantDeclaration
    InterfaceMethodDeclaration
    ClassDeclaration
    InterfaceDeclaration
    ;
```

在接口类型 $t$ 中声明或由其继承的成员 $m$ 的声明作用域在 §6.3 中有所规定。

## 9.2 接口成员

接口类型的成员包括：

- 在接口体中声明的成员 (§9.1.4)。
- 从任何直接超接口继承的成员 (§9.1.3)。
- 如果一个接口没有直接超接口，则对于 `Object` 中声明的每个签名为 $s$、返回类型为 $r$ 且 `throws` 子句为 $\tau$ 的 `public` 实例方法 $m$，该接口隐式地声明一个具有相同签名 $s$、返回类型 $r$ 和 `throws` 子句 $\tau$ 的 `public abstract` 成员方法 $m$，除非该接口显式声明了具有相同签名、返回类型和兼容 `throws` 子句的 `abstract` 方法。

如果接口显式声明了这样的成员 $m$，而 $m$ 在 `Object` 中被声明为 `final`，则会导致编译时错误。

如果接口声明的方法签名与 `Object` 的 `public` 方法具有重写等效性 (§8.4.2)，但具有不同的返回类型、或不兼容的 `throws` 子句、或不是 `abstract`，则会导致编译时错误。

接口从其扩展的接口中继承这些接口的所有成员，但排除：(i) 它隐藏的字段、类和接口；(ii) 它覆盖的 `abstract` 方法和默认方法 (§9.4.1)，(iii) 私有方法以及 (iv) 静态方法。

接口类型的字段、方法和成员类型可以具有相同的名称，因为它们被用于不同的上下文中，并通过不同的查找程序消除歧义 (§6.5)。然而，从风格上来说，不建议这样做。

## 9.3 字段（常量）声明

```
ConstantDeclaration:
    (ConstantModifier UnannType VariableDeclaratorList;

ConstantModifier:
    (one of)
    Annotation public
    static final
```

关于 `UnannType` 参见 §8.3。为了方便起见，这里列出了 §4.3 和 §8.3 中的产生式：

- VariableDeclaratorList: VariableDeclarator ( , VariableDeclarator]
- VariableDeclarator: VariableDeclaratorId [= VariableInitializer]
- VariableDeclaratorId: Identifier [Dims]
- Dims: [Annotation] { }]
- VariableInitializer: Expression | ArrayInitializer

接口字段声明上的注解修饰符规则在 §9.7.4 和 §9.7.5。

接口体中的每个字段声明都是隐式的 `public`、`static` 和 `final`。允许对此类字段冗余地指定这些任何或所有修饰符。

如果同一个关键字作为字段声明的修饰符出现多次，则会导致编译时错误。

## 9.4 方法声明

```
InterfaceMethodDeclaration:
    {InterfaceMethodModifier} MethodHeader MethodBody

InterfaceMethodModifier:
    (以下之一)
    Annotation public private
    abstract default static strictfp
```

为了方便起见，此处展示了来自 §8.4、§8.5 和 §8.7 的以下产生式：

```
MethodHeader:
    ResultMethodDeclarator [Throws]
    TypeParameters [Annotation] ResultMethodDeclarator [Throws]
```

```
Result:
    UnannType
    void
```

```
MethodDeclarator:
    Identifier ([ReceiverParameter, ] [FormalParamList]) Dims
```

```
MethodBody:
    Block
    ;
```

接口方法声明中注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

接口体中的方法可以声明为 `public` 或 `private`（§6.6）。如果没有提供访问修饰符，则该方法默认为 `public`。在接口方法声明中，冗余地指定 `public` 修饰符是允许的，但从风格角度上不建议这样做。

默认方法（default method）是接口中带有 `default` 修饰符声明的实例方法。其体始终由代码块（block）表示，为任何实现接口且未覆盖该方法的类提供默认实现。默认方法区别于具体方法（§8.4.3.1，后者在类中声明），也区别于私有接口方法（后者不被继承也不被重写）。

接口可以声明静态方法（static methods），这种方法无需引用特定对象即可调用。静态接口方法与默认方法不同，后者是实例方法。

在接口静态方法的头部或正体中使用任何周围声明的参数名称将导致编译时错误。

`strictfp` 修饰符的作用是使默认或静态方法体内的所有浮点数（float 或 double）表达式显式地遵循 FP 严格标准（§15.4）。

缺少 `private`、`default` 或 `static` 修饰符的接口方法默认为抽象的（abstract）。其体由分号表示，而不是代码块。对于此类方法声明，冗余地指定 `abstract` 修饰符是允许的，但从风格角度上不建议这样做。

> 注意，接口方法不能声明为 `protected` 或包访问权限（package access），也不能使用 `final`、`synchronized` 或 `native` 修饰符。

如果同一个关键字多次出现在接口方法声明的修饰符中，或者接口方法声明包含 `public` 和 `private` 多个访问修饰符（§6.6），则将导致编译时错误。

如果接口方法声明包含 `abstract`、`default` 或 `static` 关键字中的多个，将导致编译时错误。

如果包含 `private` 关键字的接口方法声明也包含 `abstract` 或 `default` 关键字，将导致编译时错误。接口方法声明同时包含 `private` 和 `static` 是允许的。

如果包含 `abstract` 关键字的接口方法声明也包含 `strictfp` 关键字，将导致编译时错误。

接口体显式或隐式地声明两个具有重写等效签名（override-equivalent signatures，§8.4.2）的方法会导致编译时错误。然而，接口可以继承多个具有此类签名的抽象方法（§9.4.1）。

接口中声明的方法可以是泛型的（generic）。接口中泛型方法的类型参数规则与类中泛型方法的规则相同（§8.4.4）。

### 9.4.1 继承与重写

接口 `I` 从其直接超接口继承所有的抽象方法和默认方法 `m`，前提是满足以下所有条件：

- `m` 是 `I` 的直接超接口 `J` 的成员。
- `I` 中声明的方法没有具有 `m` 签名的子签名（§8.4.2）。
- 不存在方法 `m'`，它是 `I` 的直接超接口 `S` 的成员（`m'` 不同于 `m`，`S` 不同于 `J`），使得 `m'` 重写了方法 `m` 的声明。

注意，方法的重写是基于签名的（signature-basis）的。例如，如果一个接口声明了两个同名的 `public` 方法（§9.4.2），且子接口重写了其中一个，则子接口仍然继承另一个方法。

第三条子句防止了子接口重复继承已经被其另一个超接口重写方法。例如，在以下程序中：

```
interface Top {
    default String name() { return "unnamed"; }
}

interface Left extends Top {
    default String name() { return getClass().getName(); }
}

interface Right extends Top, Left { }
```



`Right` 从 `Top` 继承 `name()`，但 `Bottom` 从 `Left`、`Right` 继承 `name()`。这是因为 `Left` 中的 `name()` 重写了 `Top` 中 `name()` 的声明。

接口不从其超接口继承私有或静态方法。

如果接口 `I` 声明了一个私有或静态方法 `m`，且 `m` 的签名是 `I` 的超接口中 `public` 实例方法 `m'` 的子签名，且 `m'` 原本可以被 `I` 中的代码访问，则会发生编译时错误。

> 本质上，接口中的静态方法不能隐藏超接口中的实例方法。这与 §8.4.8.2 中的规则相似，在该规则中，类中的静态方法不能隐藏超类或超接口中的实例方法。§8.4.8.2 关于类的规则是指“声明或继承了静态方法”，而上述规则仅指代“声明了静态方法”的接口，因为接口无法继承静态方法。此外注意，§8.4.8.2 中的规则允许在子类/超接口中隐藏实例方法和静态方法，而上述规则仅考虑接口中的 `public` 实例方法可以被重写。同样的，私有或静态方法无法重写超接口中的实例方法。这与 §8.4.8.1 和 §8.4.8.3 的规则相似，§8.4.8.1 要求重写方法必须是非私有的，而 §8.4.8.3 要求重写方法的访问权限至少与被重写方法相同。总之，只有接口中的 `public` 方法可以被重写，且只能被子接口或实现类重写。

## 9.4.1.1 重写（通过实例方法）

接口 `I` 中声明或继承自接口的实例方法 `m_I` 重写了声明在 `J` 中的另一个实例方法 `m_J`，当且仅当以下所有条件均成立（`J` 是一个接口）：

- `I` 是 `J` 的子接口。
- `I` 没有继承 `m_J`。
- `m_I` 的签名是 `m_J` 签名的签名（§8.4.2）。
- `m_J` 是 `public`。

`strictfp` 修饰符的存在与否对重写规则完全没有影响。例如，允许非 FP 严格方法重写 FP 严格方法，也允许 FP 严格方法重写非 FP 严格方法。

> 被重写的默认方法可以通过包含由超接口限定的 `super` 关键字的方法表达式（§15.12）来访问。

## 9.4.1.2 继承中的重写

接口方法的返回类型与被重写的接口方法的返回类型之间的关系规定在 §8.4.3 中。

接口方法的 `throws` 子句与被重写的接口方法的 `throws` 子句之间的关系规定在 §8.4.3 中。

接口方法的签名与被重写的接口方法的签名之间的关系规定在 §8.4.3 中。

接口方法的访问权限与被重写的接口方法的访问权限之间的关系规定在 §8.4.3 中。

如果默认方法与类 `Object` 的非私有方法具有重写等效性，会导致编译时错误，因为任何实现该接口的类将继承该方法自身的实现。

禁止将 `Object` 类的方法之一声明为默认方法可能令人惊讶。毕竟，存在诸如 `java.util.List` 这样的情况，其中 `toString` 和 `equals` 的行为是有精确定义的。然而，当考虑到更广泛的设计决策时，理由变得更加清晰：

- 继承自超类的方法允许覆盖继承自超接口的方法（§8.4.8.1）。因此，每个实现类都会自动覆盖接口的 `toString` 默认方法。这是 Java 语言中的长期行为。我们不希望通过默认方法的设计来改变这一点，因为这将与允许接口的目标冲突。

无声地演进，仅当类没有通过类层级已经拥有该方法时，才提供默认行为。

- 第二，接口不继承自 `Object`，而是隐式地将许多方法声明为 `Object` 的方法 ($9.2)。因此，在 `Object` 中声明的 `toString` 和在接口中声明的 `toString` 并没有共同的祖先。最好的情况下，如果这两个继承候选者都存在，它们可以工作。解决这个问题需要对类继承树和接口继承树进行尴尬的合并。

- 第三，在接口中声明 `Object` 方法的用例通常假设了一个线性接口层次结构；该特性无法很好推广到多重继承场景。

- 第四，`Object` 方法是如此基础，以至于允许任意开发者简单地添加一个改变其行为的默认方法似乎是危险的。

然而，接口的目的是定义另一个方法，为覆盖 `Object` 方法的类提供行为。例如，`java.util.List` 接口可以声明 `elementString` 来产生由 `toString` 契约声明的字符串，那么类中 `toString` 的实现者随后可以委托给该方法。

## 9.4.1.3 继承具有重写等签名的方法

接口可以继承多个具有重写等签名的方法 (§8.4.2)。

如果接口继承 `fact` 一个默认方法，其签名与它所继承的另一个方法是重写等签名，则会发生编译错误。（无论另一个方法是抽象方法还是默认方法情况均如此。）

否则，所有继承的方法都是抽象的，且该接口被认为继承了所有方法。

所有继承的方法中，必须有一个方法对于其他所有继承的方法都是返回类型可替换的，否则会发生编译错误。（在这种情况下，`throws` 子句不会引起错误。）

可能通过多条路径从接口继承同一个方法声明。这一事实导致了困难，但其本身永远不会导致编译错误。

通常，当一个子接口继承两个签名匹配的不同的默认方法时，会发生行为冲突。我们会主动检测这种冲突并通过错误通知程序员，而不是等到在编译具体类时出现问题。可以通过声明一个新方法来覆盖（并阻止继承）所有冲突的方法来避免该错误。

同样，当一个子接口继承一个签名匹配的抽象方法和一个默认方法时，我们会产生一个错误。在这种情况下，本可以给其中一个赋予优先级——也许我们会假设默认方法为抽象方法提供了一个合理的实现。但这是危险的，因为除了巧合的名称和签名外，我们没有理由相信默认方法的行为与抽象方法的契约保持一致——在子接口最初开发时，该默认方法可能根本不存在。在这种情况下，要求用户主动断言默认实现是合适的（通过重写声明）是更安全的。

相比之下，类中继承的具体方法的长期以来的行为是它们覆盖接口中声明的抽象方法（见§8.4.2）。关于潜在违反契约的论点也适用于这里，但在此情况下，类和接口之间存在内在的不平衡。为了保持类层级的独立性，我们倾向于通过简单地赋予具体方法优先级来尽可能减少类与接口之间的冲突。

## 9.4.2 重载

如果接口的两个方法（无论是在同一个接口中声明的，还是由接口继承的，或者一个声明一个继承）具有相同的名称但具有不同的非重写等（§8.4.2）签名，则该方法名称被认为重载。

这一事实没有导致任何困难，其本身永远不会导致编译错误。对于两个具有相同名称但非重写等签名的方法，其返回类型或 `throws` 子句之间不存在强制关系。

示例 9.4.2-1. 重载一个抽象方法声明

```java
interface PointInterface {

    void move(int dx, int dy);

}

interface RealPointInterface extends PointInterface {

    void move(float dx, float dy);

    void move(double dx, double dy);

}
```

在接口 `RealPointInterface` 中，名为 `move` 的方法有三个重签名，其中两个是声明的，一个是继承的。任何实现 `RealPointInterface` 的非抽象类都必须提供这三个签名的实现。

## 9.4.3 接口方法体

默认方法具有块体。当类实现了接口但没有提供方法的自己的实现时，该代码块提供了方法的实现。

私有或静态方法也有块体，它提供了方法的实现。

如果接口方法声明是抽象的（显式或隐式）且具有方法体块，则为编译错误。

如果接口方法声明是 `default`、`private` 或 `static`，且以分号作为方法体，则为编译错误。

静态方法的方法体尝试使用关键字 `this` 或 `super` 引用当前对象将是编译错误。

方法体中 `return` 语句的规则在 §14.17 中规定。

如果声明方法有返回类型所示8.4.5)，则当方法体可以正常完成时§14.1) 会发生编译错误。

## 9.5 成员类型声明

接口可以包含成员类型声明 (§8.5)。

接口体中的每个成员类型声明都是隐式 `public` 且 `static` 的。允许冗余地指定这些修饰符之一。

如果接口中的成员类型声明具有 `protected` 或 `private` 修饰符，则为编译错误。

如果同一个关键字多次作为成员类型声明的修饰符，则为编译错误。

如果接口声明了一个具有特定名称的成员类型，则该类型的声明被认为隐藏了父类接口中所有可用的成员类型声明。

接口从其直接父接口继承所有未被隐藏的非私有成员类型。

接口可以继承多个具有相同名称的成员类型。这种情况本身不会导致编译错误。然而，在接口体内部任何通过简单名称引用此类此类成员类型的尝试都将导致编译错误，因为引用是歧义的。

可能通过多条路径从接口继承同一个方法声明。在这种情况下，该方法被认为只继承了一次。

## 9.6 注解类型

注解类型声明指定了一种新的注解类型，一种特殊的接口。为了区分注解类型与普通接口声明，`interface` 关键字前面有一个 `@` 符号（at）。

```
AnnotationTypeDeclaration:
{InterfaceModifier} @ interface Identifier AnnotationTypeBody own
```

注意 `@` 符号（at）和 `interface` 关键字是不同的标记标记。可以使用空白符分隔它们，但从风格的角度来看这是不被鼓励的。

注解类型声明上注解修饰符的规则在 $9.7.4 和 $9.7.5 中规定。

注解类型声明中的 `Identifier` 指定了注解类型的名称。

如果注解类型与其任何包含的类或接口具有相同的简单名称（simple name），则为编译错误。

每个注解类型的直接父接口都是 `java.lang.annotation.Annotation`。

> 根据 `AnnotationTypeDeclaration` 语法，注解类型不能是泛型的，且不允许使用 `extends` 子句。

由于注解类型不能显式声明父类，且不能是注解类型的子类或接口，结果是其本身永远不是注解类型。`java.lang.annotation.Annotation` 本身并不是注解类型。

注解类型从 `java.lang.annotation.Annotation` 继承了几个成员，包括与 `Object` 实例方法对应的隐式声明方法，但这些方法并没有定义注解类型的元素 (§9.6.1)。

由于这些方法没有定义注解类型的元素，因此在该类型的注解中使用它们是违合法的 (§9.7)。如果没有这一点，我们无法确保元素是可以在注解中表示的类型，或者无法获得这些元素的访问器方法。

除非在此处显式修改，否则适用于普通接口声明的所有规则都适用于注解类型声明。

例如，注解类型与普通类类型和接口类型共享相同的命名空间；在接口声明合法的地方，注解类型声明也是合法的，并且具有相同的作用域和可访问性。

## 9.6.1 注解类型元素

注解类型声明的体可以包含方法声明，每个方法定义了该注解类型的一个元素。注解类型除了其显式声明的方法定义的元素外，不包含其他元素。

```
AnnotationTypeBody:
{ {AnnotationTypeMemberDeclaration} }

AnnotationTypeMemberDeclaration:
 AnnotationTypeElementDeclaration
 ConstantDeclaration
 ClassDeclaration
 InterfaceDeclaration
;
```

```
AnnotationTypeElementDeclaration:
[AnnotationTypeElementModifier] Type Identifier () [Dims]
[DefaultValue];
```

```
AnnotationTypeElementModifier:
(one of)
 Annotation public
abstract
```

根据 `AnnotationTypeElementDeclaration` 产生式，注解类型声明中的方法声明不能有形式参数列表、类型参数或 `throws` 子句。为了方便起见，这里展示了来自 $4.3 的后续产生式：

```
Dims:
{[Annotation] { {} }
```

根据 `AnnotationTypeElementModifier` 产生式，注解类型声明中的方法声明不能是 `default` 或 `static` 的。因此，注解类型不能像普通接口类型那样声明多种方法。请注意，注解类型仍然可以从其隐式超接口 `java.lang.annotation.Annotation` 继承默认方法，尽管截至 Java SE 14 并不存在这样的默认方法。

按照惯例，注解类型元素上应该存在的 `AnnotationTypeElementModifiers` 只有注解（annotations）。

## 9.6 接口

### 注解类型

在注解类型中声明的方法返回类型必须是以下类型之一，否则将发生编译错误：

- 原始类型
- `String`
- `Class` 或 `Class` 的调用（§§4.5）
- 枚举类型（enum type）
- 注解类型

此规则排除了具有嵌套数组类型的元素，例如：

```java
@interface Verboten {

  String[] value();

}
```

返回数组的方法声明允许在空的形式参数列表之后放置表示数组的括号对。对这种语法的支持是为了兼容 Java 编程语言的早期版本。非常建议在新代码中不要这种语法。

如果注解类型中声明的任何方法的签名与类 `Object` 或接口 `java.lang.annotation.Annotation` 中声明的任何公共或保护方法的签名重写等效，则为编译错误。

如果注解类型声明 `T` 直接或间接地包含一个类型为 `T` 的元素，则为编译错误。

例如，这是不合法的：

```java
@interface SelfRef { SelfRef value(); }
```

这种也是不合法的：

```java
@interface Ping { Pong value(); }

@interface Pong { Ping value(); }
```

没有元素的注解类型被称为标记注解类型（marker annotation type）。

只有一个元素的注解类型被称为单元素注解类型（single-element annotation type）。

按照惯例，单元素注解中唯一元素的名称为 `value`。这种惯例的语言支持由单元素注解（§9.7.3）提供。

## 示例 9.6.1-1. 注解声明

以下注解类型声明定义了一个具有多个元素的注解类型：

```java
/**

 * 描述“增强请求”（RFE），

 * 导致被注解的 API 元素存在。

 */

@interface RequestForEnhancement {

    int id(); // 与 RFE 关联的唯一 ID 号

    String synopsis(); // RFE 的摘要

    String engineer(); // 实现 RFE 的工程师姓名

    String date(); // RFE 实现的日期

}
```

## 示例 9.6.1-2. 标记注解类型声明

以下注解类型声明定义了一个标记注解类型：

```java
/**

 * 此类型的注解表示

 * 被注解的 API 元素的规范

 * 是初步的，并且可能会更改。

 */

@interface Preliminary {

}
```

## 示例 9.6.1-3. 单元素注解类型声明

单元素注解类型名为 `value` 的惯例在以下注解类型声明中所示：

```java
/**

 * 与注解的元素关联版权声明。

 */

@interface Copyright {

    String value();

}
```

以下注解类型定义了一个元素为数组类型的单元素注解类型：

```java
/**

 * 与注解的类关联支持者列表。

 */

@interface Endorsers {

    String[] value();

}
```

以下注解类型声明显示了一个受通配符约束的 `Class` 类型元素：

```java
interface Formatter {

// 用于美化被注解类的 formatter

@interface PrettyPrinter {

    Class<? extends Formatter> value();

}
```

以下注解类型声明包含一个类型也是另一个注解类型的元素：

```java
/**

 * 被注解程序的元素的作者。此注解类型

* 不是直接用于程序元素，而是为了定义其他注解类型。

 */

@interface Author {

    String first();

    String last();

}
```

注解类型的语法允许除方法声明以外的其他声明。例如，可能会为注解类型声明一个嵌套枚举：

```java
@interface Quality {

    enum Level { BAD, INDIFFERENT, GOOD }

    Level value();

}
```

## 9.6.2 注解类型元素的默认值

注解类型元素可以有默认值，通过在元素的（空）参数列表后跟随 `default` 关键字和 `ElementValue`（$9.7）来指定。

```
DefaultValue:
    default ElementValue
```

如果元素的类型与默认值不匹配（$9.7），则为编译错误。

默认值不会编译进注解，而是在读取注解时动态应用的。因此，更改默认值会影响即使在更改之前就已经编译过的类（假设这些注解缺少该元素的显式值）。

## 示例 9.6.2-1. 带有默认值的注解类型

这里引用 9.6.1 中的 `RequestForEnhancement` 注解：

```java
@interface RequestForEnhancementDefault {

    int id(); // 没有默认值——必须在

               // 注中指定
}
```



## 9.6.3 可重复注解类型

如果注解类型 `T` 的声明被元注解标记了 `@Repeatable` 注解（§9.6.4.8），且该元素的包含包含 `T` 的包含注解类型，则它是重复的。

如果满足以下条件，类型 `TC` 就是 `T` 的包含注解类型：

- `TC` 声明了一个返回类型为 `T[]` 的 `value()` 方法
- 除了 `value` 方法外，`TC` 的所有方法都有默认值
- `TC` 的保留时间与 `T` 相同，其中保留时间通过 `@Retention` 注解（§9.6.4.2）显式或隐式表示。具体而言：
  - 如果 `TC` 的保留策略为 `java.lang.annotation.RetentionPolicy.SOURCE`，则 `T` 的保留策略为 `java.lang.annotation.RetentionPolicy.SOURCE`。
  - 如果 `TC` 的保留策略为 `java.lang.annotation.RetentionPolicy.CLASS`，则 `T` 的保留策略为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.SOURCE`。
  - 如果 `TC` 的保留策略为 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 `T` 的保留策略为 `java.lang.annotation.RetentionPolicy.SOURCE` 或 `java.lang.annotation.RetentionPolicy.RUNTIME`。

4. $au$ 的适用范围至少包含与 `TC` 相同的程序元素类型（§9.6.4.1）。
   具体而言，$au$ 适用的程序元素类型由集合 $m_1$ 表示，而 `TC` 适用的程序元素类型由集合 $m_2$ 表示，那么 $m_2$ 中的每种类型必须出现在 $m_1$ 中，但例外是：
   - 如果 $m_2$ 中的类型为 `java.lang.annotation.ElementType.ANNOTATION_TYPE`，那么 `java.lang.annotation.ElementType.ANNOTATION_TYPE`、`java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 $m_2$ 中。
   - 如果 $m_2$ 中的类型为 `java.lang.annotation.ElementType.TYPE`，那么 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 $m_2$ 中。
   - 如果 $m_2$ 中的类型为 `java.lang.annotation.ElementType.TYPE_PARAMETER`，那么 `java.lang.annotation.ElementType.TYPE_PARAMETER` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 $m_2$ 中。

此条款实现了以下策略：注解类型可能仅在其*适用*的某些程序元素类型上是可重复的。

5. 如果 $au$ 的声明具有对应于 `java.lang.annotation.Documented` 的（元）注解，那么 `TC` 的声明必须具有对应于 `java.lang.annotation.Documented` 的（元）注解。

> 注意，`TC` 使用 `@Documented` 而 $au$ 不 `@Documented` 是允许的。

6. 如果 $au$ 的声明具有对应于 `java.lang.annotation.Inherited` 的（元）注解，那么 `TC` 的声明必须具有对应于 `java.lang.annotation.Inherited` 的（元）注解。

> 注意，`TC` 使用 `@Inherited` 而 $au$ 不 `@Inherited` 是允许的。

如果一个注解类型使用了 `@Repeatable` 注解，其值元素指示的类型不是 $au$ 的容器注解类型，则将导致编译错误。

### 示例 9.6.3-1. 错误的容器注解类型

考虑以下声明：

```java
import java.lang.annotation.Repeatable;

@Repeatable(FooContainer.class)
@interface Foo { }
```

# 注解类型

```java
@interface FooContainer { Object[] value(); }
```

编译 `Foo` 声明会产生编译错误：`Foo` 使用 `@Repeatable` 尝试将 `FooContainer` 指定为其注解类型，但实际上 `FooContainer` 并不是 `Foo` 的注解类型。（`FooContainer.value()` 的返回类型不是 `Foo[]`）。

`@Repeatable` 注解本身是不可重复的，因此一个可重复注解类型只能指定一个容器注解类型。

允许指定多个注解类型会导致编译时产生不可预期的影响，因为此时多个同类型可重复注解类型的注解在逻辑上会被放置于一个容器注解中（§9.7.5）。

一个注解类型最多可以作为另一个注解类型的注解类型。

这隐含于如下要求：如果注解类型 `T` 的声明指定了一个容器注解类型 `TC`，那么 `TC` 的 `value()` 方法的返回类型应涉及 `T`，具体而言为 `T[]`。

注解类型不能将自身指定为自身的注解类型。

这隐含于对容器注解类型 `value()` 方法的要求。具体而言，如果注解 `A`（通过 `@Repeatable`）将自身指定为其容器注解类型，那么 `A` 的 `value()` 方法的返回类型将是 `A[]`；但这会导致编译错误，因为注解类型在其元素中不能引用自身（§9.6）。更广泛地说，两个注解除了容器注解类型外不能互相指定，循环的注解类型声明是非法的。

注解类型 `TC` 可以是某些注解类型 `T` 的容器注解类型，同时具有它自己的容器注解类型 `TC'`。也就是说，容器注解类型本身可以是一个可重复注解类型。

### 示例 9.6.3.2. 限制可以重复的注解

类型声明指示目标为 `java.lang.annotation.ElementType.TYPE` 的注解，其出现次数至少不少于类型声明指示目标为 `java.lang.annotation.ElementType.ANNOTATION_TYPE` 的注解。例如，给定以下可重复注解类型和容器注解类型的声明：

```java
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;
import java.lang.annotation.Repeatable;

@Target(ElementType.TYPE)
@Repeatable(FooContainer.class)
```

# 接口

```java
@interface Foo {
    @Target(ElementType.ANNOTATION_TYPE)
    @interface FooContainer {
        Foo[] value();
    }
}
```

`@Foo` 可以出现在任何类型声明上，而 `@FooContainer` 只能出现在注解声明上。因此，以下注解类型声明是合法的：

```java
@Foo @Foo
@interface Anno
```

但以下接口声明是非法的：

```java
@Foo @Foo
interface Int
```

更宽泛地说，如果 `Foo` 是一个可重复注解类型且 `FooContainer` 是它的容器注解类型，那么：

- 如果 `Foo` 没有 `@Target` 元注解且 `FooContainer` 也没有 `@Target` 元注解，则 `@Foo` 可以在任何支持注解的程序元素上重复。
- 如果 `Foo` 没有 `@Target` 元注解但 `FooContainer` 有 `@Target` 元注解，则 `@Foo` 可以在 `FooContainer` 可能出现的程序元素上重复。
- 如果 `Foo` 有 `@Target` 元注解但 `FooContainer` 没有 `@Target` 元注解，则 `@Foo` 可以在 `FooContainer` 可能出现的程序元素上重复。
- 如果 `Foo` 有 `@Target` 元注解且 `FooContainer` 有 `@Target` 元注解，则 `@Foo` 可以在 `FooContainer` 可能出现的程序元素上重复。

具体而言，如果 `Foo` 适用于字段和方法声明，那么当 `FooContainer` 适用于字段声明时，`FooContainer` 无法正当地作为 `Foo` 的注解类型（这防止了 `@Foo` 的重复）。但如果 `FooContainer` 仅适用于参数声明，那么 `Foo` 选择 `FooContainer` 作为注解类型就是一个糟糕的选择，因为 `Foo` 依赖它是很危险的。

注解类型可能适用于声明上下文（即注解应用于声明的上下文），也可能适用于类型上下文（即注解应用于声明和表达式中使用的类型的上下文）。

共有 9 种声明上下文，每种上下文对应 `java.lang.annotation.ElementType` 中的一个枚举常量：

1. 模块声明 (§7.7)
   对应 `java.lang.annotation.ElementType.MODULE`
2. 包声明 (§7.4.1)
   对应 `java.lang.annotation.ElementType.PACKAGE`
3. 类型声明（类、接口、枚举和注解类型声明）（§8.1.1, §9.1.1, §8.5, §9.5, §9.6）
   对应 `java.lang.annotation.ElementType.TYPE`
   此外，注解类型声明对应 `java.lang.annotation.ElementType.ANNOTATION_TYPE`
4. 方法声明（包括注解类型的元素）（§8.4.3, §9.4, §9.6.1）
   对应 `java.lang.annotation.ElementType.METHOD`
5. 构造方法声明 (§8.8.3)
   对应 `java.lang.annotation.ElementType.CONSTRUCTOR`
6. 型类、接口、方法和构造方法的类型参数声明（§8.1.2, §9.1.2, §8.4.4, §8.8.4）
   对应 `java.lang.annotation.ElementType.TYPE_PARAMETER`
7. 字段声明（包括枚举常量）（§8.3.1, §9.3, §8.9.1）
   对应 `java.lang.annotation.ElementType.FIELD`
8. 形式参数和异常参数声明 (§8.4.1, §9.4, §14.20)
   对应 `java.lang.annotation.ElementType.PARAMETER`
9. 局部变量声明（包括 for 语句中的循环变量和 try-with-resources 语句中的资源变量）（§14.4, §14.14.1, §14.14.2, §14.20.3）
   对应 `java.lang.annotation.ElementType.LOCAL_VARIABLE`

共有 16 种类型上下文 (§4.11)，全部由 `java.lang.annotation.ElementType` 的枚举常量 `TYPE_USE` 表示。

如果同一个枚举常量在注解类型 `java.lang.annotation.Target` 的值元素中出现多次，则构成一个编译时错误。

如果注解类型 `T` 的声明上不存在类型为 `java.lang.annotation.Target` 的注解，则 `T` 在所有 9 种声明上下文和 16 种类型上下文都是有效的。

## 9.6.4.2 @Retention

注解可能仅存在于源代码中，也可能存在类或接口的二进制形式中。存在于二进制形式的注解在运行时可以通过 Java SE Platform 的反射库可用，也可以不可用。注解类型 `java.lang.annotation.Retention` 用于在这些可能性之间进行选择。

如果注解 `a` 对应于类型 `T` 且 `T` 有一个对应于 `java.lang.annotation.Retention` 的（元）注解 `m`，那么：

- 如果 `m` 有一个取值为 `java.lang.annotation.RetentionPolicy.SOURCE` 的元素，则 Java 编译器必须确保 `a` 不出现在 `a` 所在的类或接口的二进制表示中。
- 如果 `m` 有一个取值为 `java.lang.annotation.RetentionPolicy.CLASS` 的元素，则 Java 编译器必须确保 `a` 出现在 `a` 所在的类或接口的二进制表示中；如果取值为 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 Java 编译器必须确保 `a` 出现在类或接口的二进制表示中，除非 `a` 注解了局部变量声明或 Lambda 表达式的形式参数声明。

在局部变量声明上的注解，或 Lambda 表达式的形式参数声明上的注解，永远不会保留在二进制表示中。相比之下，局部变量类型上或 Lambda 表达式形式参数类型上的注解，如果该注解类型指定了合适的保留策略，则会被保留在二进制表示中。

注意，注解类型带有 `@Target(java.lang.annotation.ElementType.LOCAL_VARIABLE)` 元注解是合法的，接口也是注解类型。

```java
@Retention(java.lang.annotation.RetentionPolicy.CLASS)
@Retention(java.lang.annotation.RetentionPolicy.RUNTIME)
```

或者

如果 `m` 有一个取值为 `java.lang.annotation.RetentionPolicy.RUNTIME` 的元素，Java SE Platform 的反射库会在运行时使 `a` 可用。

如果 `T` 没有对应于 `java.lang.annotation.Retention` 的（元注解）`m`，则 Java 编译器必须将 `T` 视为它拥有这样一个元素取值为 `java.lang.annotation.RetentionPolicy.CLASS` 的元注解 `m`。

## 9.6.4.3 @Inherited

注解类型 `java.lang.annotation.Inherited` 用于表示类 `C` 上对应于给定注解类型的注解会被 `C` 的子类继承。

## 9.6.4.4 @Override

程序员在想要重写方法声明时偶尔会重载方法声明，从而导致细微的问题。`Override` 注解类型支持对此类问题进行早期检测。

经典的例子涉及 `equals` 方法。程序员在以下类 `Foo` 中写了代码：

```java
public boolean equals(Foo that) { ... }
```

而他们本意写：

```java
public boolean equals(Object that) { ... }
```

这是完全合法的，但 `Foo` 继承了来自 `Object` 的 `equals` 实现，这可能会导致细微的错误。

如果类型 `T` 中的方法声明被带有 `@Override` 注解，但该方法没有重写来自 `T` 的父类型中声明的方法（§8.4.1.1, §9.4.1.1），或者与 `Object` 的公共方法不是重写等价（§4.3.2, §8.4.2），则会发生编译时错误。

这种行为与 Java 5.0 不同，在 Java 5.0 中，只有当 `@Override` 应用于实现来自父接口且该方法在父类中不存在的方法时，才会导致编译时错误。

关于重写公共方法的子句是由于在接口中使用 `@Override` 而考虑的。考虑以下类型声明：

```java
class Foo {
    @Override public int hashCode() {..}
}

interface Bar {
    @Override int hashCode();
}
```



## 9.6.4.3 @Inherited

注解类型 `java.lang.annotation.Inherited` 用于表示类 $C$ 上对应于给定注解类型的注解会被 $C$ 的子类继承。

## 9.6.4.4 @Override

程序员在想要重写方法时偶尔会重载方法声明，导致细微的问题。`@Override` 注解类型支持对此类问题进行早期检测。

经典的例子涉及 `equals` 方法。程序员在以下类 `Foo` 中写了代码：

```java
public boolean equals(Foo that) { ... }
```

而他们本意写：

```java
public boolean equals(Object that) { ... }
```

这是完全合法的，但 `Foo` 继承了来自 `Object` 的 `equals` 实现，这可能会导致细微的错误。

如果类型 $T$ 中的方法声明被带有 `@Override` 注解，但该方法没有重写来自 $T$ 的父类型中声明的方法（§8.4.1.1, §9.4.1.1），或者与 `Object` 的公共方法不是重写等价（§4.3.2, §8.4.2），则会发生编译时错误。

这种行为与 Java 5.0 不同，在 Java 5.0 中，只有当 `@Override` 应用于实现来自父接口且该方法在父类中不存在的方法时，才会导致编译时错误。

关于重写公共方法的子句是由于在接口中使用 `@Override` 而考虑的。考虑以下类型声明：

```java
class Foo {
    @Override public int hashCode() {..}
}

interface Bar {
    @Override int hashCode();
}
```

根据第一句，在声明中使用 `@Override` 是合法的，因为 `Foo.hashCode` 重写了 `Object.hashCode`。

对于接口声明，假设该接口没有对应于 `java.lang.annotation.Retention` 的（元注解）$m$，则 Java 编译器必须将 $T$ 视为它拥有这样一个元素取值为 `java.lang.annotation.RetentionPolicy.CLASS` 的元注解 $m$。

如果 $m$ 有一个取值为 `java.lang.annotation.RetentionPolicy.RUNTIME` 的元素，Java SE Platform 的反射库会在运行时使其可用。

如果 $T$ 没有对应于 `java.lang.annotation.Retention` 的（元注解）$m$，则 Java 编译器必须将 $T$ 视为它拥有这样一个元素取值为 `java.lang.annotation.RetentionPolicy.CLASS` 的元注解 $m$。

局部变量声明上的注解，或 Lambda 表达式形式参数声明上的注解，永远不会保留在二进制表示中。相比之下，局部变量类型上或 Lambda 表达式形式参数类型上的注解，如果注解类型指定了合适的保留策略，则会被保留在二进制表示中。

注意，注解类型带有 `@Target(java.lang.annotation.ElementType.LOCAL_VARIABLE)` 元注解是合法的，接口也是注解类型。

```java
@Retention(java.lang.annotation.RetentionPolicy.CLASS)
@Retention(java.lang.annotation.RetentionPolicy.RUNTIME)
```

或者

如果 $m$ 有一个取值为 `java.lang.annotation.RetentionPolicy.RUNTIME` 的元素，Java SE Platform 的反射库会在运行时使其可用。

如果 $T$ 没有对应于 `java.lang.annotation.Retention` 的（元注解）$m$，则 Java 编译器必须将 $T$ 视为它拥有这样一个元素取值为 `java.lang.annotation.RetentionPolicy.CLASS` 的元注解 $m$。

## 9.6.4.6 @Deprecated

程序员有时被不要使用某些程序元素（模块、类型、字段、方法和构造方法），因为它们是危险的或者有更好的替代方案。`@Deprecated` 注解类型允许对这些用法产生警告。

弃用的程序元素是带有 `@Deprecated` 注解的模块、类型、字段、方法或构造方法。程序元素的弃用方式取决于保留元素的值：

- 如果 `forRemoval=false`（默认值），则该程序元素是普通弃用的。
- 普通弃用的程序元素不打算在未来的版本中删除，但程序员仍然应该尽量避免使用它。
- 如果 `forRemoval=true`，则该程序元素是严重弃用的。

严重弃用的程序元素打算在未来的版本中删除。程序员应该停止使用它，否则在升级到新版本时面临源和二进制不兼容问题（§13.2）。

当普通弃用的程序元素在程序元素的声明（显式或隐式声明）中使用（重写、调用或按名称引用）时，Java 编译器必须产生弃用警告，除非：

- 该使用位于一个带有注解以抑制弃用警告的声明中（§9.6.4.5）；或
- 出现该使用的声明与通常被弃用的程序元素的声明都位于同一个最层类中；或
- 该使用位于导入了该通常被弃用的类型或成员的 `import` 声明中；或
- 该使用位于 `exports` 或 `opens` 指令中（§7.7.2）。

当在程序元素的声明（无论显式还是隐式声明的）中使用一个终极弃用的程序元素（重写、调用或通过名称引用）时，Java 编译器必须产生一个移除警告，除非：

- 该使用位于一个带有注解以抑制移除警告的声明中（§9.6.4.5）；或
- 出现该使用的声明与终极弃用程序元素的声明都位于同一个最层类中；或
- 该使用位于导入了终极弃用类型或成员的 `import` 声明中；或
- 该使用位于 `exports` 或 `opens` 指令中。

> 终极弃用具有足够的紧迫性，使用终极弃用元素会导致即使该元素本身已被弃用，也会产生移除警告，因为无法保证两个元素会同时被移除。为了消除此警告，程序员必须通过 `@SuppressWarnings` 注解手动确认该风险。

在以下情况下，不会产生弃用警告或移除警告：

- 使用了局部变量或形式参数（通过名称引用），即使该局部变量或形式参数的声明标记了 `@Deprecated` 注解。
- 使用了包名（通过限定类型名、`import` 声明或 `exports` 或 `opens` 指令），即使该包的声明标记了 `@Deprecated` 注解。
- 通过限定的 `exports` 或 `opens` 指令使用了模块名，即使该友元模块的声明标记了 `@Deprecated` 注解。

导出或打开一个包的模块声明通常由控制该包声明的同位程序员或团队控制。因此，当包被模块声明导出或打开时，警告该包声明标记了 `@Deprecated` 注解并没有多大益处。相比之下，向友元模块导出或打开一个包的模块声明通常由控制该友元模块的同一程序员或团队控制。仅仅导出或打开包并不会使模块声明依赖于友元模块，因此如果友元模块被弃用，发出警告的意义不大；模块声明的程序员几乎总是希望抑制此类警告。

唯一可能导致声明移除或移除警告的隐式声明是容器注解（§9.7.5）。具体来说，如果 $T$ 是一个可重复注解类型且 $TC$ 是其注解类型，且 $TC$ 被弃用，则重复使用 `@T` 注解将导致警告。该警告源于隐式的 `@TC` 容器注解。强烈不建议在不弃用相应注解类型的情况下弃用容器注解类型。

## 9.6.4.7 @SafeVarargs

具有不可靠的元素类型（§4.4）的变长参数可能会导致堆污染（§14.2.2）并产生编译时的未检查警告（§5.1.9）。如果变长参数方法的体在处理变长参数的操作上是良好的，则此类警告将是不提供任何有用信息的。

`@SafeVarargs` 注解类型在用于标记方法或构造函数声明时，是程序员做出的一项断言，防止 Java 编译器对变长参数方法或构造函数的声明或调用报告未检查警告，而在其他情况下，编译器会因为变长参数具有不可靠的元素类型而报告此类警告。

`@SafeVarargs` 注解具有非局部影响，因为它在抑制方法调用表达式中的未检查警告之外，还抑制与变长参数方法本身声明相关的未检查警告（§8.4.1）。相比之下，`@SuppressWarnings("unchecked")` 注解具有局部影响，因为它只抑制与方法声明相关的未检查警告。

`@SafeVarargs` 的标准目标是诸如 `java.util.Collections.addAll` 这样的方法，其声明如下：

```java
public static boolean addAll(Collection<? super T> c, T... elements)
```

变长参数的声明类型为 `T[]`，它是不可靠的。然而，该方法从根本上只是从输入数组读取元素并添加到集合中，对于数组而言，这些操作是安全的。因此，`java.util.Collections.addAll` 方法调用表达式中的任何编译时未检查警告认为都是多余且不提供有用信息的。在方法声明上应用 `@SafeVarargs` 可以防止在方法调用表达式中生成这些未检查警告。

如果固定参数个数的方法或构造函数声明标记了 `@SafeVarargs` 注解，则为编译错误。

如果一个既不是 `static` 也不是 `final` 也不是 `private` 的变长方法声明标记了 `@SafeVarargs` 注解，则为编译错误。

> 由于 `@SafeVarargs` 仅适用于静态、`final` 和/或 `private` 实例方法以及构造函数，因此该注解在发生方法重写的地方不可用。注解继承仅适用于类上的注解（而不适用于方法、接口或构造函数上的注解）；因此，`@SafeVarargs` 风格的注解无法通过类中的实例方法或接口传递。

## 9.6.4.8 @Repeatable

注解类型 `java.lang.annotation.Repeatable` 用于可重复注解类型以指示其容器注解类型（§9.6）。注意，在 $T$ 上的 `@Repeatable` 不足以使 $TC$ 成为容器注解类型。存在大量的规则来使 $TC$ 被视为容器注解类型。

## 9.6.4.9 @FunctionalInterface

`@FunctionalInterface` 注解类型用于指示接口是功能接口（§9.8）。

如果接口声明标记了 `@FunctionalInterface` 但实际上不是功能接口，则为编译错误。

因为某些接口本身就是功能性的，所以没有必要对所有功能接口声明都标记 `@FunctionalInterface`。

## 9.7 注解

注解是与程序结构关联信息的标记，但在运行时没有作用。注解表示类型的特定调用（§9.6），并通常为该类型的元素提供值。

有三种注解。第一种是最通用的，而其他种类仅仅是第一种的简写。

### INTERFACES 注解 9.7

```
Annotation:
    NormalAnnotation
    MarkerAnnotation
    SingleElementAnnotation
```

普通注解描述见 §9.7.1，标记注解见 §9.7.2，单元素注解描述见 §9.7.3。注解可以出现在程序中的各种语法位置，见 §9.7.4。同一处相同注解的数量由其类型决定，见 §9.7.5。

## 9.7.1 普通注解

*普通注解*指定注解类型的名称，以及可选的逗号分隔的*元素-值*对。每个对包含一个与注解元素关联的值（§9.6.1）。

```
NormalAnnotation:
    @ TypeName ( [ ElementValuePairList ] )

ElementValuePairList:
    ElementValuePair { , ElementValuePair }

ElementValuePair:
    Identifier = ElementValue

ElementValue:
    ConditionalExpression
    ElementValueArrayInitializer
    Annotation

ElementValueArrayInitializer:
    { [ ElementValueList ] [ , ] }

ElementValueList:
    ElementValue { , ElementValue }
```

注意 `@` 符号（`@`）是一个单独的标记（§3.11）。可以在它和 `TypeName` 之间放置空格，但从风格上考虑不建议这样做。

`TypeName` 指定与注解对应的注解类型。该注解被认为“属于”该类型。

### 注释

`TypeName` 必须命名一个可访问的注解类型（§6.6），否则将发生编译错误。

- $\tau$ 是数组类型 $E[]$，且满足：
    - $v$ 是一个条件表达式（`ConditionalExpression`）或一个注解（`Annotation`），则 $v$ 与 $E$ 兼容；
    - $v$ 是一个元素值数组初始化器（`ElementValueArrayInitializer`），则每个元素值 $v$ 都与 $E$ 兼容。

> `ElementValueArrayInitializer` 类似于普通的数组初始化器（§10.6），不同之处在于 `ElementValueArrayInitializer` 在语法上也可以包含注解以及表达式和嵌套初始化器。然而，嵌套初始化器在 `ElementValueArrayInitializer` 中语义上是不合法的，因为它们永远与注解类型声明中的数组类型元素不兼容（注解类型声明中不允许嵌套数组类型）。

- $\tau$ 不是数组类型，且 $v$ 的类型与 $\tau$ 是赋值兼容的（§5.2），
    - 如果 $\tau$ 是基本数据类型或 `String`，则 $v$ 是一个常量表达式（§15.29）。
    - 如果 $\tau$ 是 `Class` 或 `Class` 的调用（§4.5），则 $v$ 是一个类字面量（§15.8.2）。
    - 如果 $\tau$ 是枚举类型（§8.9），则 $v$ 是一个枚举常量（§8.9.1）。
- $v$ 不是 `null`。

注意，如果 $\tau$ 不是数组类型或注解类型，则元素值必须是一个条件表达式（§15.25）。使用条件表达式而不是更通用的表达式（`Expression`）产生是一种语法技巧，用于防止将赋值表达式作为元素值。由于赋值表达式不是常量表达式，因此不能作为基本数据类型或 `String` 类型元素的兼容元素值。

### 接口

### 注释

### 9.7

从形式上讲，说元素值（`ElementValue`）是 FP 严格的（§15.4）是无效的，因为它可能是一个注解或类字面量。尽管如此，当 `ElementValue` 是一个常量表达式、常量表达式数组，或者其元素（递归地）被发现是常量表达式的注解时，我们可以非正式地认为 `ElementValue` 是 FP 严格的；毕竟，每个常量表达式都是 FP 严格的。

一个普通注解必须为相应注解类型的每个元素包含元素-值对，但那些具有默认值的元素除外，否则将发生编译时类型错误。

普通注解可以（但不是要求）为具有默认值的元素包含元素-值对。

按照习惯（尽管不是要求），注解中的元素-值对的呈现顺序与注解类型声明中对应元素的顺序相同。

位于注解类型上的注解被称为元注解（meta-annotation）。

类型 $\tau$ 的注解可以作为元注解出现在类型 $\tau$ 自身的声明上。更一般地说，允许“注解”关系的传递闭包中存在循环引用。

> 示例，使用类型 $\tau$ 的元注解对注解类型 $s$ 的声明进行注解是合法的，并且使用类型 $s$ 的元注解对 $\tau$ 自身的声明进行注解也是合法的。预定义的注解类型中就包含此类循环引用。

### 示例 9.7.1-1. 普通注解

这里是一个使用来自 §9.6 中注解类型的普通注解示例：



@RequestForEnhancement(
  id = 2868724,
  synopsis = "Provide time-travel functionality",
  engineer = "Mr. Peabody",
  date = "4/1/2004"
)
public static void travelThroughTime(Date destination) { ... }

这是一个利用默认值的普通注解示例，使用了来自 §9.6.2 的注解类型：

@RequestForEnhancement(
  id = 4561414,
  synopsis = "Balance the federal budget"
)
public static void balanceFederalBudget() {
  throw new UnsupportedOperationException("Not implemented")
}

### 9.7.2 标记注解

标记注解（marker annotation）是一种为用于标记注解类型（§9.6.1）设计的简写形式。

```
MarkerAnnotation:
@ TypeName
```

它是普通注解的简写：

```
@TypeName()
```

只要所有元素都具有默认值（§9.6.2），对带有元素的注解类型使用标记注解是合法的。

#### 示例 9.7.2-1. 标记注解

这里是一个使用 §9.6.1 中初步标记注解类型的示例：

```
@Preliminary public class TimeTravel { ... }
```

### 9.7.3 单元素注解

单元素注解（single-element annotation）是一种为用于单元素注解类型（§9.6.1）设计的简写形式。

```
SingleElementAnnotation:
@ TypeName ( ElementValue )
```

它是普通注解的简写：

```
@TypeName(value = ElementValue)
```

只要其中一个元素名为 `value` 且所有其他元素都具有默认值（§9.6.2），对多元素注解类型使用单元素注解是合法的。

#### 示例 9.7.3-1. 单元素注解

以下注解使用了 §9.6.1 中的单元素注解类型。

这里是一个单元素注解的示例：

```
@Copyright("2002 Yoyodyne Propulsion Systems, Inc.")
public class OscillationOverthruster { ... }
```

这里是一个数组值型单元素注解的示例：

```
@Endorsers("Children", "Unscrupulous dentists")
public class Lollipop { ... }
```

这里是一个单元素数组值型单元素注解的示例：（注意省略了大括号）。

```
@Endorsers("Epicurus")
public class Pleasure { ... }
```

这里是一个带有受边界通配配符约束的 `Class` 类型元素的单元素注解示例。

```java
class GorgeousFormatter implements Formatter { ... }

@PrettyPrinter(GorgeousFormatter.class)
public class Petunia { ... }

// 非法；String 不是 Formatter 的子类型
@PrettyPrinter(String.class)
public class Begonia { ... }
```

这里是一个包含枚举类型注解的单元素注解示例：

```
@Author(@Name(first = "Joe", last = "Hacker"))
public class BitTwiddle { ... }
```

这里是一个使用在注解类型内部定义的枚举类型的单元素注解示例：

```
@Quality(Quality.Level.GOOD)
public class Karma { ... }
```

### 9.7.4 注解可能出现的地方

声明注解（declaration annotation）是一种应用于声明的注解，且其类型在由该声明表示的上下文（§9.6.4）中适用；或者是一种应用于类、接口、枚举、类型或参数声明的注解，且其类型在类型上下文中适用（§4.11）。

类型注解（type annotation）是一种应用于类型或其部分的注解。

示例，给定的字段声明：

```
@Foo int f;
```

`@Foo` 是针对 `f` 的声明注解，其带有 `@Target(ElementType.FIELD)`，也是针对 `int` 的类型注解，其带有 `@Target(ElementType.TYPE_USE)`。`@Foo` 可能既是声明注解也是类型注解。

类型注解可以应用于任何类型或类型的类型（§10.1）。例如，假设 `A`、`B` 和 `C` 是带有 `@Target(ElementType.TYPE_USE)` 的注解类型，那么给定的字段声明：

```
@C int @A [] @B [] f;
```

`@A` 应用 `int[]`，`@B` 应用其组件类型 `int[]`，而 `@C` 应用类型 `int`。

这种语法的重要属性是，两个声明仅在数组层级上不同，类型左侧的注解指向相同的类型。例如，`@C` 在所有声明中都应用于 `int`：

```
@C int f;
@C int[] f;
@C int[][] f;
```

习惯（尽管不是要求）是将声明注解写在所有修饰符之前，并将类型注解紧接在它们适用的类型之前。

注解可能出现在程序中的语法位置，在该位置可以合理地应用于声明、类型或两者。这可以发生在任何五个修饰符直接位于被声明实体类型之前的声明上下文中：

* 方法声明（包括注解类型的元素）
* 构造方法声明
* 字段声明（包括枚举常量）
* 参数和异常参数声明
* 局部变量声明（包括 `for` 语句的循环变量和 `try-with-resources` 语句的资源变量）

Java 编程语言语法明确将这些位置的注解视为声明的修饰符（§8.3），但这纯粹是语法问题。注解应用于声明还是应用于被声明实体的类型——因此，注解是声明注解还是类型注解——取决于注解类型的适用性：

* 如果注解的类型在与声明对应的声明上下文中适用，但在类型上下文中不适用，则该注解被认为仅适用于该声明。
* 如果注解的类型在类型上下文中适用，但在与声明对应的声明上下文中不适用，则该注解被认为仅适用于距离注解最近的类型。
* 如果注解的类型既在与声明对应的声明上下文中适用，在类型上下文中适用，则该注解被认为同时适用于该声明和距离注解最近的类型。

在上述第二和第三种情况下，距离注解最近的类型确定方式如下：

* 如果注解出现在 `void` 方法声明或使用（§14.4、§14.14.2、§14.20.3）的局部变量声明之前，则没有最近的类型。如果注解的类型被认为仅适用于距离其最近的类型，则会发生编译错误。
* 如果注解出现在构造方法声明之前，则最近的类型是新构造对象的类型。新构造对象的类型是紧邻封装构造方法声明的类型的完全限定名。在该完全限定名中，注解适用于构造方法声明所指的简单类型。
* 在所有其他情况下，最近的类型是源代码中书写的声明实体的类型；如果该类型是数组类型，则元素类型被认为距离注解最近。

> 例如，在字段声明 `@Foo static String f` 中，距离 `@Foo` 最近的类型是 `String`。如果字段声明的类型被写为 `java.lang.String`，那么 `java.lang.String` 将是距离 `@Foo` 最近的类型，且随后的规则将禁止类型注解应用于包名 `java`。
> 在泛型方法声明 `@Foo <T> int[] m() {...}` 中，为声明实体书写的类型是 `int[]`，因此 `@Foo` 适用于元素类型 `int`。

不使用 `var` 的局部变量声明与 `lambda` 表达式的形式参数声明相似，因为在其中在源代码中，声明注解和类型注解都存在，但只有类型注解可以存储在类文件中。

如果类型为 `T` 的注解在语法上是以下内容的修饰符，则会发生编译错误：

* 模块声明，或 `T` 不适用于模块声明。
* 包声明，或 `T` 不适用于包声明。
* 类、接口或枚举声明，但 `T` 不适用于类型声明或类型上下文；或注解类型声明，但 `T` 不适用于注解类型声明或类型上下文。
* 方法声明（包括注解类型的元素），但 `T` 不适用于方法声明或类型上下文。
* 构造方法声明，但 `T` 不适用于构造方法声明或类型上下文。
* 泛型类、接口、方法或构造方法的类型参数声明，但 `T` 不适用于类型参数声明或类型上下文。
* 字段声明（包括枚举常量），但 `T` 不适用于字段声明或类型上下文。
* 形式参数或异常参数声明，但 `T` 不适用于形式参数或异常参数声明或类型上下文。
* 接收参数，但 `T` 不适用于类型上下文。
* 局部变量声明（包括 `for` 语句的循环变量或 `try-with-resources` 语句的资源变量），但 `T` 不适用于局部变量声明或类型上下文。

这九类中有五类提到了“……类型上下文”，是因为它们描述了注解可能合理应用于声明或声明实体类型的五种语法位置。此外，其中两类——类、接口、枚举和注解声明的类，以及参数声明类——提到了“……或类型上下文”，因为将一个类型被标记了 `@Target(ElementType.TYPE_USE)` 元注解（因此在类型上下文中适用）的注解应用于类型声明可能是方便的。

如果满足任一条件，则类型注解是允许的：

* 距离注解最近的简单名被分类为类型（Type），而不是包名（PackageName）。
* 如果距离注解最近的简单名后面跟着 ".另一个类型——即注解以 `@Foo T.U` 的形式出现——那么 `U` 表示 `T` 的一个内部类。

第二句背后的直觉是，如果 `Outer` 在由 `Outer` 封装的嵌套类中是合法的，`Outer` 可以被注解，因为它代表了运行时某个对象的类型。另一方面，如果 `Outer` 不是合法的，是因为它在运行时出现 `Outer` 的类是不合法的——那么 `Outer` 可能无法被注解，因为它在逻辑上只是一个名称，类似于完全限定类型名中包名的组件。

例如，在以下程序中，无法在 `B` 的体中编写 `A.this`，因为 `B` 没有词法封装的实例（§8.5.1）。因此，无法在类型 `A.B` 中对 `A` 应用 `@Foo`，因为 `A` 在逻辑上只是一个名称，而不是一个类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}
```

```java
class Test {
    class A {
        static class B {}
    }

    @Foo A.B x; // 非法
}
```

另一方面，在以下程序中，可以在 `D` 的体中编写 `C.this`。因此，可以在类型 `C.D` 中对 `C` 应用 `@Foo`，因为 `C` 代表了运行时某个对象的类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}
```

```java
class Test {
    class C {
        class D {}
    }

    @Foo C.D x; // 合法
}
```

最后，注意第二句只向深看了一层。这是因为该注解仅适用于类型使用。

### 9.7.5 同类型的多个注解

如果相同类型的注解 `au` 出现在声明上下文或类型上下文中，则会发生编译错误，除非 `au` 是可重复的（§9.6.3），且 `au` 和包含 `au` 的注解类型 `t` 都适用于声明上下文或类型上下文（§9.6.4.1）。

习惯上（并非要求）相同类型的多个注解是连续出现的。

如果声明上下文或类型上下文有多个重复注解类型 `au` 的注解，只要它有一个显式声明的类型为 `au` 的注解和一个隐式声明的 `au` 的容器注解类型的注解，则是允许的。

这种隐式声明的注解被称为容器注解，而在上下文中出现的多个类型 `au` 的注解被称为基础注解（base annotation）。容器注解的（数组类型的）值元素（value element）的元素是它们在上下文从左到右出现的所有基础注解。

在声明上下文中或类型上下文中，如果存在多个可重复注解类型 `T` 的注解，以及任何作为 `T` 的包含性注解类型的注解，则是一个编译时错误。

换句话说，当与与其容器类型相同的注解也出现时，是不允许重复注解的：

```
@Foo(0) @Foo(1) @FooContainer((@Foo(2)))
class A { }
```

如果这段代码是合法的，就需要多层包含：首先，类型 `Foo` 的注解将被一个隐式声明的类型 `FooContainer` 的容器注解包含，然后该注解和显式声明的类型 `FooContainer` 的注解将被包含在另一个隐式声明的注解中。Java 编程语言设计者认为，这种复杂度是不理想的。另一种方法，即将类型 `Foo` 的注解视为与 `@FooContainer` 注解并列，也是不可取的，因为这可能会改变反射程序解释 `@FooContainer` 注解的方式。

在声明上下文中或类型上下文中，如果存在一个可重复注解类型 `T` 的注解，以及多个作为 `T` 的包含性注解类型的注解，则是一个编译时错误。

此规则的设计是为了允许以下代码：

```
@Foo(1) @FooContainer((@Foo(2)))
class A { }
```

如果可重复注解类型 `Foo` 只有一个注解，且 `FooContainer` 是 `Foo` 的包含性注解类型，则不会隐式声明容器注解。然而，重复类型 `FooContainer` 的注解，例如：

```
@Foo(1) @FooContainer((@Foo(2))(@Foo(3)))
class A { }
```



即使 `FooContainer` 也是可重复的且拥有自己的包含性注解类型，这也是被禁止的。在存在底层可重复类型的注解的情况下，重复那些其本身就是容器的注解是晦涩的。

## 9.8 函数式接口

函数式接口是一个只有一个抽象方法（`Object` 方法之外）的接口，因此代表了一个单一的函数契约。这个“单一”方法可能表现为多个继承自父接口的具有重写等效签名的抽象方法；在这种情况下，继承的方法在逻辑上代表了一个单一方法。

对于接口 $I$，设 $M$ 为 $I$ 的成员中不与 `Object` 类的任何公共实例方法签名（§4.3.2）相同的抽象方法集合。那么，如果 $M$ 中存在一个方法 $m$，使得以下两个条件均真，则 $I$ 是一个函数式接口：

- $m$ 的签名是 $M$ 中每个方法签名的签名（§8.4.2）。
- $m$ 对于 $M$ 中的每个方法都是返回类型可替换的（§8.4.5）。

除了声明和实例化类来创建接口实例（§15.9）的常规过程外，还可以方法引用和 lambda 表达式（§15.13, §15.27）创建函数式接口实例。

> 函数式接口的定义除了接口中也是 `Object` 公共方法的方法。这样做允许对如 `java.util.Comparator<T>` 的接口进行函数式处理，该接口声明了多个方法，其中只有一个真正是“新”的：`int compare(T,T)`。另一个——`boolean equals(Object)`——是对抽象方法的显式声明，否则该方法将在接口中隐式声明（§9.2）并由实现接口的每个类自动实现。

注意，`Object` 的非公共方法（如 `clone()`）不会由实现接口的每个类自动实现。从 `Object` 继承的实现在接口公共时是保护的，因此实现接口的唯一方法是让类用公共方法重写非公共的 `Object` 方法。

### 示例 9.8-1. 函数式接口

函数式接口的一个简单示例是：

```java
interface Runnable {
    void run();
}
```

以下接口不是函数式接口，因为它声明的任何内容都不是 `Object` 已有的成员：

```java
interface NonFunc {
    boolean equals(Object obj);
}
```

然而，它的子类可以通过声明一个不是 `Object` 成员的抽象方法来成为函数式的：

```java
interface Func extends NonFunc {
    int compare(String o1, String o2);
}
```

同样，著名的接口 `java.util.Comparator<T>` 是函数式接口，因为它有一个抽象的非 `Object` 方法：

```java
interface Comparator<T> {
    boolean equals(Object obj);
    int compare(T o1, T o2);
}
```

以下接口不是函数式接口，因为它声明了一个不是 `Object` 成员的抽象方法，并声明了两个不是 `Object` 公共成员的抽象方法：

```java
interface Foo {
    int m();
    Object clone();
}
```

### 示例 9.8-2. 函数式接口与擦除

在以下接口层次结构中，`Z` 是函数式接口，因为它继承了两个不是 `Object` 成员的抽象方法，它们具有相同的签名，因此继承的方法在逻辑上代表了一个单一方法：

```java
interface X { int m(Iterable<String> arg); }
interface Y { int m(Iterable<String> arg); }
interface Z extends X, Y { }
```

同样，`Z` 在接口层次结构中也是函数式接口，因为 `Y.m` 是 `X.m` 的签名，并且对于 `X.m` 是返回类型可替换的：

```java
interface X { int m(Iterable<String> arg); }
interface Y { int m(Iterable<String> arg); }
interface Z extends X, Y { }
```

“函数式接口”的定义限制了接口只能具有重写等效签名的方法，前提是其中一个方法对于所有其他方法都是返回类型可替换。因此，在以下接口层次结构中 `Z` 导致了编译时错误，`Z` 不是函数式接口：因为它的没有任何抽象成员对于所有其他成员都是返回可替换的。

```java
interface X { long m(); }
interface Y { int m(); }
interface Z extends X, Y { }
```

### 示例 9.8-3. 泛型函数接口

函数接口可以是泛型的，例如 `java.util.function.Predicate<T>`。此类函数接口可以以产生抽象方法的方式进行参数化——也就是说，无法通过单个声明来合法地重写多个方法。例如：

```java
interface I { void m(Class c); }
interface J<S> { void m(Class<? extends S> c); }
interface K<T> { void m(Class<? extends T> c); }
interface Functional<S,T> extends I, J<S>, K<T> { }
```

`Functional<S,T>` 是一个函数接口——`I.m` 在返回类型上可以替换 `J.m` 和 `K.m`，但函数接口类型 `Functional<String,Integer>` 显然无法通过单个方法实现。然而，`Functional<S,T>` 的其他参数化是四种可能的函数类型。

函数接口的声明允许在程序中使用*函数接口类型*。函数接口类型有四种：

- 非泛型（§6.1）函数接口的类型
- 泛型函数接口的参数化（§4.5）参数化类型
- 泛型函数接口的原始类型（§4.8）
- 导出概念函数接口的交集类型（§4.9）

在特殊情况下，将函数接口类型与一个或多个标记接口类型的交集是有用的，这看起来像是函数接口类型与诸如 `Runnable` & `java.io.Serializable` 的交集。这种交集可以用于强制转换（§15.16），强制 lambda 表达式符合特定类型。如果交集中的接口类型之一是 `java.io.Serializable`，则触发针对序列化的特殊运行时支持（§15.27.4）。

## 9.9 函数类型

函数接口 *I* 的*函数类型*是一个方法类型（§8.2），可用于重写（§8.4.8）*I* 的抽象方法。

设 *M* 为 *I* 定义的抽象方法集。*I* 的函数类型由以下部分组成：

### 类型参数、形式参数类型和返回类型

设 $m$ 为 $M$ 中的一个方法，其：
1. 签名是 $M$ 中每个方法签名的签名，且
2. 返回类型为 $R$（可能为 `void`），其中 $R$ 与 $M$ 中每个方法的返回类型相同，或者 $R$ 是一个引用类型且是 $M$ 中每个方法返回类型的子类型（在适配任何类型参数（§8.4.4）后），如果两个方法具有相同的签名则如此。

如果不存在这样的方法，则设 $m$ 为 $M$ 中的一个方法，其：
1. 签名是 $M$ 中每个方法签名的签名，且
2. 返回类型使得 $m$ 对于 $M$ 中的每个方法在返回类型上是可替换的（§8.4.5）。

函数类型参数、形式参数类型和返回类型由 $m$ 给出。

### `throws` 子句

函数类型的 `throws` 子句从 $M$ 中方法的 `throws` 子句派生，如下所示：

1. 如果函数类型是泛型的，则首先将 `throws` 子句适配函数类型的类型参数（§8.4.4）。如果函数类型不是泛型的但 $M$ 中至少有一个方法是泛型的，则首先擦除 `throws` 子句。
2. 然后，函数类型的 `throws` 子句包含满足以下约束的每个类型 $E$：
   - $E$ 属于某个 `throws` 子句。
   - 对于每个 `throws` 子句，$E$ 是该子句中类型的子类型。

当 $M$ 中的返回类型是原始类型时，函数的定义尝试选择最具体的类型。例如，如果是 `LinkedList` 和 `LinkedList<String>`，则后者被选为函数类型的返回类型。如果没有最具体的类型，例如存在第三种返回类型 `List<?>`，则并非其中一个返回类型是另一个的子类型（因为原始 `LinkedList` 不是 `List<?>` 的子类型）；相反，由于 `LinkedList<String>` 在返回类型上对两者都是可替换的。

驱动函数类型抛出异常定义的定义是确保生成的 `throws` 子句可以重写函数接口的每个抽象方法。根据 §8.4.6，这意味着函数类型抛出的异常不能多于 $M$ 中的任何单一方法，因此我们尽可能寻找被每个方法的 `throws` 子句“覆盖”的异常类型。

函数接口的函数类型规定如下：

- 非泛型函数接口 $I$ 的类型的函数类型简单为接口 $I$ 的函数类型，如上。
- 参数化函数接口 $I<A1...An>$（其中 $A1...An$ 是类型且 $I$ 对应的类型参数为 $P1...Pn$）的函数类型确定如下：设 $M$ 为 $I$ 的抽象方法集，$I<A1...An>$ 的函数类型是用 $A1...An$ 替换 $P1...Pn$ 后 $I$ 的函数类型。
- 交集类型 $I_1 \cap I_2 \cap ... \cap I_n$ 的函数类型是 $I_1, I_2, ..., I_n$ 函数类型的交集。
- 原始类型 $I$ 的函数类型是相应泛型接口 $I$ 的函数类型。
- 通配符类型 $I<? extends T>$ 的函数类型是 $I<T>$ 的函数类型，其中 $T$ 是边界。
- 通配符类型 $I<? super T>$ 的函数类型是 $I<T>$ 的函数类型，其中 $T$ 是边界。
- 无界通配符类型 $I<?$ 的函数类型是原始类型 $I$ 的函数类型。
- 函数接口 $I<T>$ 的函数类型是用 $T$ 替换类型参数后 $I$ 的函数类型。

## 10 数组

在 Java 编程语言中，数组是对象（§4.3.1），是动态创建的，并且可以赋值给 `Object` 类型的变量（§4.3.2）。`Object` 类的所有方法都可以在数组上被调用。

一个数组对象包含多个变量。变量的数量可以为零，在这种情况下，数组被认为为空。数组中包含的变量没有名称；相反，它们通过使用非负整数值的数组访问表达式来引用。这些变量被称为数组的组件。如果一个数组有 $n$ 个变量，我们说 $n$ 是数组的长度；数组的组件使用从 0 到 $n-1$（包含）的整数索引进行引用。

数组的所有组件都具有相同的类型，称为数组的组件类型。如果数组的组件类型为 $t$，则数组本身的类型为 $t[]$。

`float` 类型的数组组件的值始终是 `float` 值集（§4.2.3）中的一个元素；同样，`double` 类型的数组组件的值始终是 `double` 值集中的一个元素。`float` 类型数组组件的值不允许是 `float` 扩展指数值集中的元素（且该元素也不是 `float` 值集中的元素），`double` 类型数组组件的值不允许是 `double` 扩展指数值中的元素（且该元素也不是 `double` 值集中的元素）。

数组的组件类型本身也可以是数组类型。此类数组的组件可能包含对子数组的引用。从数组类型开始，考虑它的组件类型，以及（如果该类型也是数组类型）该类型的组件类型，依此类推，最终必须到达一个不是数组类型的组件类型；这被称为原始数组的元素类型，而该数据结构在该层级的组件被称为原始数组的元素。

### 数组类型

在某些情况下，数组的元素可以是数组：如果元素类型是 `Object` 或 `Cloneable` 或 `java.io.Serializable`，那么部分或所有元素都可能是数组，因为任何数组对象都可以赋值给这些类型的任何变量。

## 10.1 数组类型

数组类型用于声明和强制转换表达式（§15.16）。

数组类型写为元素类型的名称，后面跟随着若干个空括号对 `[]`。括号对的数量表示数组嵌套的深度。

数组类型中的每个括号对都可以由类型注解（§9.7.4）进行标记。注解适用于跟随其后的括号对（或可变性参数声明中的省略号）。

数组的元素类型可以是任何类型，无论是原始类型还是引用类型。特别：

- 允许以接口类型作为元素类型的数组。
- 此类数组的元素的值可以是 `null` 引用或实现该接口的任何类型的实例。
- 允许以抽象类类型作为元素类型的数组。
- 此类数组的元素的值可以是 `null` 引用或该抽象类的任何子类的实例（且该子类本身不是抽象类）。

数组的长度不是其类型的一部分。

数组类型的超类型规定在 §4.10.3 中。

> 数组的超类型关系与子类关系并不相同。根据 §4.10.3，`Integer[]` 的直接超类型是 `Number[]`，但根据 `Integer[]` 的 `Class` 对象，其直接父类是 `Object`（§10.8）。这在实践中并不重要，因为 `Object` 是所有数组类型的超类型。

## 10.2 数组变量

数组类型的变量持有指向对象的引用。声明数组类型的变量不会创建数组对象，也不会为数组组件分配任何空间。它只创建变量本身，该变量可以包含指向数组的引用。然而，声明器中的初始化器 `var`（§8.3, §9.3）可以包含指向数组的引用。

## 10.5 数组存储异常 (Array Store Exception)

此程序产生输出：

```
5050
```

程序声明了一个类型为 `int[]` 的变量 `ia`。变量 `ia` 初始化为一个新创建的数组对象的引用，该对象由数组创建表达式（§15.10.1）创建。数组创建表达式指定数组应有 101 个组件。可以使用字段 `length` 获取数组的长度，如所示。程序用从 0 到 100 的整数填充数组，对这些整数求和，并打印结果。

数组必须使用 `int` 值进行索引；`short`、`byte` 或 `char` 值也可以用作索引值，因为它们会经过一元数值提升（§5.6）并变为 `int` 值。

尝试使用 `long` 类型的索引值访问数组组件会导致编译时错误。

所有的数组访问都在运行时进行检查；尝试使用小于或大于数组长度的索引会导致抛出 `ArrayIndexOutOfBoundsException`（§15.10.4）。

## 10.5 数组存储异常 (Array Store Exception)

对于类型为 `A[]` 的数组（其中 `A` 是引用类型），对数组组件的赋值会在运行时进行检查，以确保赋值的值可以赋值给该组件。

如果所赋值值的类型与组件类型不兼容赋值兼容（§5.2），则会抛出 `ArrayStoreException`。

> 如果数组的组件类型不是可重构（reifiable）（§4.7），Java 虚拟机将无法执行前述段的存储检查。这就是为什么禁止使用非可重构元素类型的数组创建表达式（§15.10.1）。可以声明一个元素类型为不可重构的数组类型变量，但将数组创建表达式的结果赋值给该变量将必然导致未检查警告（§5.1.9）。

### 示例 10.5-1. ArrayStoreException

```java
class Point { int x, y; }

class ColoredPoint extends Point { int color; }

class Test {
    public static void main(String[] args) {
        ColoredPoint[] cpa = new ColoredPoint[10];
        Point[] pa = cpa;
        System.out.println(pa[1] == null);
        try {
            pa[0] = new Point();
        } catch (ArrayStoreException e) {
            System.out.println(e);
        }
    }
}
```

此程序输出：

```
true
java.lang.ArrayStoreException: Point
```

变量 `pa` 的类型为 `Point[]`，变量 `cpa` 的值是对类型为 `ColoredPoint[]` 对象的引用。`ColoredPoint` 可以赋值给 `Point`；因此，`cpa` 的值可以赋值给 `pa`。

对此数组 `pa` 的引用（例如测试 `pa[1]` 是否为 `null`）不会导致运行时错误。这是因为类型为 `ColoredPoint[]` 的数组元素是 `ColoredPoint`，而每个 `ColoredPoint` 都可以代表 `Point`，因为 `Point` 是 `ColoredPoint` 的子类。

另一方面，对数组 `pa` 的赋值可能会导致运行时错误。在编译时，对 `pa` 元素的赋值会进行检查，以确保所赋值的值是一个 `Point`。由于 `pa` 持有一个指向 `ColoredPoint` 数组的引用，只有当运行时赋值值的类型是、更具体来说是 `ColoredPoint` 时，该赋值才是有效的。

Java 虚拟机会在运行时检查此类情况以确保赋值是有效的；如果不是，将抛出 `ArrayStoreException`。

## 10.6 数组初始化器 (Array Initializers)

数组初始化器可以在字段声明（§8.3, §9.3）或局部变量声明（§14.4）中指定，或者作为数组创建表达式的一部分（§15.10.1），用于创建一个数组并提供一些初始值。

```
ArrayInitializer:
    { [VariableInitializerList] [,] }

VariableInitializerList:
    VariableInitializer (, VariableInitializer)*

VariableInitializer:
    Expression
```



# ArrayInitializer

数组初始化器被写为逗号分隔的表达式列表，并用大括号 `{` 和 `}` 包围。

数组初始化器中最后一个表达式后可以出现尾逗号，且会被忽略。

每个变量初始化器必须与数组的组件类型赋值兼容（§5.2），否则将发生编译时错误。

如果被初始化数组的组件类型不是可重构（§4.7），则为编译时错误。

要构造的数组长度等于紧邻数组初始化器括号包围的变量初始化器的数量。将为该长度的数组分配空间。如果没有足够的空间分配数组，数组初始化器的求值将通过抛出 `OutOfMemoryError` 异常终止。否则，将创建一个指定长度的一维数组，并将数组的每个组件都初始化为其默认值（§4.12.5）。

数组初始化器括号内紧邻的变量初始化器按照它们在源代码中出现的文本顺序从左到右执行。第 $n$ 个变量初始化器指定第 $(n-1)$ 个数组组件的值。如果某个变量初始化器的执行由于相同原因异常终止，则后续执行也将终止。

## 10.7 数组成员 (Array Members)

此程序产生输出：

```
1
2
```

数组的成员包括所有内容：
- 公有字段 `length`，包含数组的组件数量。
- 方法 `clone`，继承自 `Object` 并被重写。参见 9.6 另一种返回类型为 `T[]` 的情况。

```java
class A<T> implements Cloneable, java.io.Serializable {

    public final int length;

    public T[] clone() {

        try {

            return (T[])super.clone();

        } catch (CloneSupportedException e) {

            throw new InternalError(e.getMessage());

        }

    }

}
```

注意，上述代码中的强制转换为 `T[]` 将产生未检查警告（§5.1.9）。

### 示例 10.7-1. Arrays Cloneable

```java
class Test1 {

    public static void main(String[] args) {

        int[] ia1 = { 1, 2 };

        int[] ia2 = ia1.clone();

        System.out.print((ia1 == ia2) + " ");

        ia1[1]++;

        System.out.println(ia2[1]);

    }

}
```

此程序输出：

```
false 2
```

说明 `ia1` 和 `ia2` 引用的数组组件是不同的变量。

### 示例 10.7-2. 复制后共享子数组 (Shared Subarrays After Clone)

数组被复制时子数组共享的实通过此程序所示：

```java
class Test2 {

    public static void main(String[] args) throws Throwable {

        int[][] ia1 = { {1,2}, null };

        int[][] ia2 = ia1.clone();

        System.out.print((ia1 == ia2) + " ");

        System.out.println(ia1[0] == ia2[0] && ia1[1] == ia2[1]);

    }

}
```

此程序输出：

```
false true
```

说明 `int[]` 数组是 `ia1[0]` 且 `ia2[0]` 是同一个数组。

## 10.8 数组的类对象 (Class Objects for Arrays)

每个数组都有关联的类对象，与所有具有相同组件类型的数组共享。

尽管数组类型不是类，但每个数组的类对象表现就像：

- 每一个数组类型的直接超父类都是 `Object`。
- 每一个数组类型都实现了 `Cloneable` 和 `java.io.Serializable` 接口。

### 示例 10.8-1. 数组的 Class 对象

```java
class Test1 {

    public static void main(String[] args) {

        int[] ia = new int[3];

        System.out.println(ia.getClass().getSuperclass());

        System.out.println(ia.getClass().getInterfaces());

        for (Class<?> c : ia.getClass().getInterfaces()) {

            System.out.println("Superinterface: " + c);

        }

    }

}
```

该程序产生输出：

```
class java.lang.Object
Superinterface: interface java.lang.Cloneable
Superinterface: interface java.io.Serializable
```

其中字符串 `[I` 是组件类型为 `int` 的数组 `array` Class 对象的运行时类型签名。

### 示例 10.8-2. 共享的数组 Class 对象

```java
class Test2 {

    public static void main(String[] args) {

        int[] ia = new int[3];

        int[] ib = new int[6];

        System.out.println(ia.getClass() == ib.getClass());

    }

}
```



该程序产生输出：`true`

虽然 `ia` 和 `ib` 指向不同的数组，但 `Class` 对象的比较结果表明，所有组件类型为 `int` 的数组都是同一种数组类型的实例（即 `int[]`）。

## 10.9 字符数组不是字符串

在 Java 编程语言中，与 C 语言不同，`char` 数组不是 `String`，且 `String` 或 `char` 数组都不是以 `\0`（NUL 字符）终止的。

`String` 对象是不可变的，也就是说它的内容永远不会改变，而 `char` 数组具有可变的元素。

`String` 类中的 `toCharArray` 方法返回一个字符数组，其中包含与 `String` 相同的字符序列。`StringBuffer` 类在可变字符数组上实现了实用的方法。

## 11 异常

当程序违反 Java 编程语言的语义约束时，Java 虚拟机会将此错误作为异常信号给程序。

此类违反的示例是尝试访问数组边界之外的索引。某些编程语言及其实现通过预先终止程序来对此类错误做出反应；其他编程语言则允许实现以任意或不可预测的方式做出反应。这两种方法都不符合 Java SE 平台的设计目标：提供可移植性和健壮性。

相反，Java 编程语言规定，当违反语义约束时将抛出异常，并导致控制权从异常发生点向程序员可以指定的点发生非局部转移。

异常从其发生点被认为被*抛出*（thrown），并在控制权转移到的点被认为被*捕获*（caught）。

程序还可以使用 `throw` 语句（§14.18）来显式地抛出异常。

显式使用 `throw` 语句为旧式的通过返回“奇怪值”来处理错误状况的方法（例如在通常不期望出现负值的地方返回整数 -1）提供了一种替代方案。经验表明，这些奇怪值往往被调用者忽略或未进行检查，导致程序不健壮、表现出非预期行为或两者兼有。

每一个异常都由 `Throwable` 类的一个实例或其子类之一表示（§11.1）。此类对象可以用于从异常发生点携带信息到捕获它的处理程序。处理器通过 `try` 语句的 `catch` 子句建立（§14.20）。

## 11.1 异常的种类和产生

在抛出异常的过程中，Java 虚拟机会突然完成当前线程中已开始但尚未执行的任何表达式、语句、方法和构造函数调用、初始化器以及字段初始化异常。这一过程一直持续，直到找到一个通过指定异常的类或该异常类的父类来处理此特定异常的处理器（§11.2）。如果没有找到这样的处理器，则异常可能由未捕获异常处理器层次结构中的一个（§11.3）处理——因此，已尽一切避免让异常未被处理。

Java SE 平台的异常机制与其同步模型集成（§17.1），使得监视器在同步语句（§14.19）处解锁，并且同步方法的调用（§8.4.3.6, §15.12）意外结束。

### 11.1.1 异常的种类

异常由 `Throwable` 类（`Object` 的直接子类）的一个实例或其子类之一表示。

`Throwable` 及其所有子类共同构成异常类。

`Exception` 和 `Error` 类是 `Throwable` 的直接子类。

- `Exception` 是所有异常的父类，普通程序可能希望从这些异常中恢复。

`RuntimeException` 类是 `Exception` 的直接子类。`RuntimeException` 是在表达式求值过程中由于各种原因可能抛出的异常的父类，仍然可以恢复。

`RuntimeException` 及其所有子类共同构成运行时异常类。

- `Error` 是所有异常的父类，普通程序不期望从这些异常中恢复。

`Error` 及其所有子类共同构成错误类。

### 11.1.2 异常产生

异常由 `Throwable` 类（`Object` 的直接子类）的一个实例或其子类之一表示。

`Throwable` 及其所有子类共同构成异常类。

`Exception` 和 `Error` 类是 `Throwable` 的直接子类。

- `Exception` 是所有异常的父类，普通程序可能希望从这些异常中恢复。

`RuntimeException` 类是 `Exception` 的直接子类。`RuntimeException` 是在表达式求值过程中由于各种原因可能抛出的异常的父类，仍然可以恢复。

`RuntimeException` 及其所有子类共同构成运行时异常类。

- `Error` 是所有异常的父类，普通程序不期望从这些异常中恢复。

`Error` 及其所有子类共同构成错误类。

### 11.1.3 异步异常

大多数异常是由于发生异常的线程的动作而同步发生的，并且发生在程序指定的点。相比之下，异步异常是可能在执行过程的任何点发生的异常。

异步异常仅由于以下结果产生：
- 调用 `Thread` 或 `ThreadGroup` 的已弃用的 `stop` 方法。

这些已弃用的 `stop` 方法由一个线程调用以影响另一个线程或指定组中的所有线程。它们是异步的，因为它们可能发生在其他线程执行的任何点。

Java 虚拟机的内部错误或资源限制导致其无法实现 Java 编程语言的语义。在这种情况下，抛出的异步异常是 `VirtualMachineError` 子类的实例。

## 11.2 异常的编译时检查

Java 语言要求程序必须包含对方法或构造函数执行时产生的检查异常的处理器（§8.4.6, §8.8.5）。这种对异常处理器是否存在的编译时检查旨在减少未被妥善处理的异常数量。对于每个可能的结果的检查异常，方法或构造函数的 `throws` 子句必须提到该异常类或该异常类的一个父类类（§11.2.3）。

`throws` 子句中命名的检查异常类（§11.1.1）是方法或构造函数实现者与用户之间约定的一部分。重写方法的 `throws` 子句不能指定该方法将抛出被重写方法通过 `throws` 子句不允许抛出的任何检查异常（§8.4.8.3）。涉及接口时，一个重写声明可能会重写多个方法。在这种情况下，重写声明必须具有与所有被重写声明兼容的 `throws` 子句（§9.4.1）。

未检查异常类（§11.1.1）免于编译时检查。

> 错误类是豁免的，因为它们可能发生在程序的许多点，且从它们中恢复是困难或不可能的。复杂的程序可能仍希望捕获并尝试从这些某些情况中恢复。

例如，代码可能实现一种循环数据结构，该结构根据构造永远不会涉及空引用；程序员借此确定 `NullPointerException` 不会发生，但 Java 编译器很难证明这一点。建立此类数据结构之全局属性属性所需的证明技术超出了本规范的范围。

我们说根据 §11.2.1 和 §11.2.2 中的规则，一个语句或表达式可以抛出异常类 E，即该语句或表达式的执行可能导致抛出类 E 的异常。

我们说一个 `catch` 子句可以捕获其可捕获的异常类：

- 单捕获子句的可捕获异常类是其异常参数的声明类型（§14.20）。
- 多捕获子句的可捕获异常类是表示其异常参数类型的联合类型中的候选项。

### 11.2.1 表达式的异常分析

类实例创建表达式（§15.9）可以抛出异常类 E，当且仅当：

- 该表达式是限定的类实例创建表达式，且限定表达式可以抛出 E；或者
- 参数列表中的某些表达式可以抛出 E；或者
- E 是所选构造函数调用类型的异常类型之一（§15.12.2:6）；或者
- 类实例创建表达式包含一个类体（`ClassBody`），且 `ClassBody` 中的某些实例初始化器或实例变量初始化器可以抛出 E。

方法调用表达式（§15.12）可以抛出异常类 E，当且仅当：

- 方法调用表达式符合 `Primary . [TypeArguments] Identifier` 形式，且 `Primary` 表达式可以抛出 E；或者
- 参数列表中的某些表达式可以抛出 E；或者
- E 是所选方法调用类型的异常类型之一（§15.12.2:6）。

Lambda 表达式（§15.27）不能抛出任何异常类。

`switch` 表达式（§15.28）可以抛出异常类 E，当且仅当：

- 选择器表达式可以抛出 E；或者
- `switch` 块中的某些 `switch` 规则表达式、`switch` 块、`switch` throw 语句或 `switch` 标签语句可以抛出 E。

对于其他所有类型的表达式，表达式可以抛出异常类 E，当且仅当其任一子表达式可以抛出 E。

> 形式为 `Primary : [TypeArguments] Identifier` 的方法引用表达式（§15.13）如果 `Primary` 子表达式可以抛出异常类，则该表达式可以抛出异常类。相比之下，Lambda 表达式不会抛出任何内容，且没有可以进行异常分析的直接子表达式。是 Lambda 表达式的主体（包含表达式和语句）可以抛出异常类。

### 11.2.2 语句的异常分析

`throw` 语句（§14.18）的抛出表达式静态类型为 E 且不是 `final` 或有效 final 的异常参数，可以抛出 E 或该抛出表达式可以抛出的任何异常类。

例如，语句 `throw new java.io.FileNotFoundException();` 只能抛出 `java.io.FileNotFoundException`。

形式上，它并不是“可以抛出” `java.io.FileNotFoundException` 的子类或父类。

`throw` 语句的抛出表达式是 `catch` 子句 C 的 `final` 或有效 final 参数，则在满足以下条件时，可以抛出异常 E：

- E 是声明 C 的 `try` 语句的 `try` 块可以抛出的异常类；且
- E 与 C 的任何可捕获异常类赋值兼容；
- E 与在同一 `try` 语句中声明在 C 左侧的任何 `catch` 子句的可捕获异常类都不赋值兼容。

`try` 语句（§14.20）可以抛出异常类 E，当且仅当：

- `try` 块可以抛出 E，或者初始化资源的表达式（在 `try-with-resources` 语句中）可以抛出 E，或者资源 `close()` 方法的自动调用（`try-with-resources` 语句）可以抛出 E，且 E 与该 `try` 中任何 `catch` 子句的任何可捕获异常类都不赋值兼容，且不存在 `finally` 块或 `finally` 块可以正常完成；或者
- `try` 语句的某些 `catch` 块可以抛出 E，且不存在 `finally` 块或 `finally` 块可以正常完成；或者
- 存在 `finally` 块且它可以抛出 E。

显式构造函数调用语句（§8.8.7.1）可以抛出异常类 E，当且仅当：

- 构造函数调用参数列表中的某些异常可以抛出 E；或者
- E 被确定为调用的构造函数的 `throws` 子句的异常类（§15.12.2.6）。

`switch` 语句（§14.11）可以抛出异常类 E，当且仅当：

- 选择器表达式可以抛出 E；或者
- `switch` 块中的某些 `switch` 表达式、`switch` 规则块、`switch` throw 语句或 `switch` 标签语句组可以抛出 E。

如果直接在语句 S 中的表达式或语句可以抛出 E，则语句 S 都可以抛出异常 E。

### 11.2.3 异常检查

当 E 是检查异常类且 E 不是 `throws` 子句中声明的类的子类时，如果方法或构造函数体可以抛出某些异常类，则为编译错误。

当 E 是检查异常类且 E 不是 Lambda 表达式的目标函数类型 `throws` 子句中声明的类的子类时，如果 Lambda 体可以抛出某些异常类，则为编译错误。

如果命名类或接口 E 的类变量初始化器（§8.3.2）或静态初始化器（§8.7）可以抛出检查异常，则为编译错误。

如果命名类的实例变量初始化器（§8.3.2）或实例初始化器（§8.6）可以抛出检查异常，则为编译错误，除非该命名类至少有一个显式声明的构造函数，且该异常类或其父类之一在每个构造函数中被显式声明。

> 注意，如果匿名类（§15.9.5）的实例变量初始化器或实例初始化器可以抛出异常，则没有编译错误。在命名类中，程序员传播关于可以抛出的异常信息的责任是在任何显式构造函数声明上声明 `throws` 子句。类构造函数所抛出的检查异常类之间的关系在匿名类声明中是有保证的，因为不存在可能的显式构造函数声明，且 Java 编译器总是根据其初始化器可以抛出的检查异常类为匿名类声明生成带有合适子句的构造函数。

如果一个 `catch` 子句可以捕获检查异常类 E1，且阻塞捕获的 `try` 块无法抛出 E1 的子类或父类的检查异常类（除非 E1 是 `Exception` 或 `Exception` 的父类），则为编译错误。

如果一个 `catch` 子句可以捕获异常类 E1，且紧邻相邻的 `try` 语句中之前的 `catch` 子句可以捕获 E1 或其父类，则为编译错误。

当 `catch` 子句可以捕获检查异常类 $E_j$，而与该 `catch` 子句对应的 `try` 块可以抛出异常类 $E_i$（其中 $E_j < E_i$），且紧邻的 `try` 语句之前的 `catch` 子句可以捕获检查异常类 $E_k$（其中 $E_k < E_j$）时，鼓励 Java 编译器发出警告。

### 示例 11.2.3. 捕获检查异常

```java
import java.io.*;

class StaticallyThrownExceptions {

    public static void main(String[] args) {

        try {

            throw new FileNotFoundException();

        } catch (IOException ioe) {

            // "catch IOException" 捕获 IOException 
            // 以及任何子类型。

        }

        try {

            throw new FileNotFoundException();

            // 语句 "can throw" 抛出 FileNotFoundException。
            // 并不是 "can throw" 抛出
            // FileNotFoundException 的子类或父类。

        } catch (FileNotFoundException fnfe) {

            // 处理异常

        } catch (IOException ioe) {

            // 合法，但从 Java 7 开始鼓励
            // 给出警告，因为所有 
            // "can throw" 的 IOException 子类型
            // 已经被之前的 catch 子句捕获了。

        }

        try {

            m();

            // m 的声明说 "throws IOException"，所以
            // m "can throw" IOException。并不是
            // m "can throw" 抛出 IOException 的
            // 子类或父类（例如 Exception）。

        } catch (FileNotFoundException fnfe) {

            // 合法，异常的动态类型
            // 可能是 FileNotFoundException。

        } catch (IOException ioe) {

            // 合法，异常的动态类型
            // 可能是 IOException 的另一个子类型。

        } catch (Throwable t) {

            // 始终捕获 Throwable。

        }

    }

    static void m() throws IOException {

        throw new FileNotFoundException();

    }

}
```

根据上述规则，多 `catch` 子句（§14.20）中的每个备选方案必须能够捕获 `try` 块抛出且未被之前的 `catch` 子句捕获的异常。例如，下方的第二个 `catch` 块会导致编译错误，因为异常分析确定 `SubclassFoo` 已经被第一个 `catch` 子句捕获了。

```java
try ( ... )
catch (Foo foo) { ... }
catch (Bar bar) { ... }
```



## 11.3 异常的运行时处理

当抛出异常时（§14.18），控制将从导致异常的代码转移到能够处理该异常的 `try` 语句（§14.20）中最近的 `catch` 子句（如果有的话）。

如果一个语句或表达式出现在 `catch` 子句所属的 `try` 语句的 `try` 块中，或者该语句或表达式的调用者动态地被 `catch` 子句包围，则该语句或表达式被 `catch` 子句动态包围。

语句或表达式的调用者取决于它出现的位置：

- 如果在方法内部，则调用者是执行以进行调用的方法调用表达式（§15.12）。
- 如果是构造函数、实例初始化器或实例变量的初始化器，则调用者是执行以创建对象的实例创建表达式（§15.9）或 `new` 的方法调用。
- 如果是静态初始化器或静态变量的初始化器，则调用者是使用类或接口作为原因使其初始化的表达式（§12.4）。

一个特定的 `catch` 子句是否能处理异常，通过比较抛出的对象的类与 `catch` 子句中可捕获的异常类来确定。如果可捕获的异常类之一是异常的类或该异常类的父类，则该 `catch` 子句可以处理该异常。

等价地，`catch` 子句将捕获任何 `instanceof`（§15.20.2）其任一可捕获异常类的异常对象。

### 异常的运行时处理

抛出异常时发生的控制转移会导致表达式（§15.6）和语句（§14.1）异常终止，直到遇到能够处理该异常的 `catch` 子句；执行继续，且导致异常的那个 `catch` 子句永远不会恢复。

所有异常（同步和异步）都是精确的：当控制转移发生时，在抛出异常的点之前执行的语句和评估的表达式的所有影响似乎都已发生。在抛出异常点之后发生的任何异常、语句或其部分都不可能似乎已经执行过。

> 优化后的代码可能推测地执行了异常发生点之后的某些表达式或语句；代码必须准备好从程序可见的状态中隐藏这种推测性的执行。

如果找不到可以处理异常的 `catch` 子句，当前线程（遇到异常的线程）将终止。通过终止，所有 `finally` 子句都将执行，并根据以下规则处理未捕获的异常：

- 如果当前线程有未捕获异常的处理器，则执行该处理器。
- 否则，为当前线程的父 `ThreadGroup` 调用方法 `uncaughtException`。如果 `ThreadGroup` 及其父级 `ThreadGroup` 没有重写 `uncaughtException`，则调用默认处理器的 `uncaughtException` 方法。

在希望确保某块代码在另一块代码之后始终执行的情况下（如果另一块代码异常终止），可以使用带有 `finally` 子句的 `try` 语句（§14.20.2）。

如果 `try-finally` 或 `try-catch-finally` 语句中的 `try` 块或 `catch` 块异常终止，则在异常传播期间执行 `finally` 子句，即使最终没有找到匹配的 `catch`。

如果因为 `try` 块的异常终止而执行了 `finally` 子句，且该 `finally` 子句本身也异常终止，则 `try` 块异常终止的原因被丢弃，新的异常终止原因从那里开始传播。异常终止和捕获异常的规则在 §14（块和语句）中每个语句的规范以及 §15（表达式）中（特别是 §15.6）的表达式规范中进行了详细说明。

### 示例 11.3-1. 抛出和捕获异常

以下程序声明了一个异常类 `TestException`。类的 `main` 方法调用 `thrower` 四次，导致三次抛出异常。`main` 方法中的 `try` 语句捕获了 `thrower` 抛出的每个异常。无论 `thrower` 调用是正常完成还是异常终止，都会有一个描述发生情况的消息。

```java
class TestException extends Exception {

    TestException() { super(); }

    TestException(String s) { super(s); }

}

class Test {

    public static void main(String[] args) {

        for (String arg : args) {

            try {

                thrower(arg);

                System.out.println("Test " + arg + " didn't throw an exception");

            } catch (Exception e) {

                System.out.println("Test " + arg + " throw a " + e.getClass() + "\n with message: " + e.getMessage());

            }

        }

        static int thrower(String s) throws TestException {

            try {

                if (s.equals("divide")) {

                    int i = 0;

                    return i / i;

                }

                if (s.equals("null")) {

                    s = null;

                    return s.length();

                }

                if (s.equals("test")) {

                    throw new TestException("Test message");

                }

                return 0;

            } finally {

                System.out.println("{thrower \"" + s + "\" done!}");

            }

        }

    }

}
```

如果我们执行该程序并传递参数：

```
divide null test
```

它产生输出：

```
[thrower("divide") done]
Test "divide" threw a class java.lang.ArithmeticException
with message: / by zero
[thrower("null") done]
Test "null" throw a class java.lang.NullPointerException
with message: null
[thrower("not") done]
Test "not" didn't throw an exception
[thrower("test") done]
Test "test" threw a class TestException
with message: Test message
```

方法 `thrower` 的声明必须包含 `throws` 子句，因为它可能会抛出 `TestException` 实例，这是一个检查异常类（§11.1.1）。如果省略 `throws` 子句，将会发生编译错误。

注意，`finally` 子句在每次调用 `thrower` 时都会执行，无论是否发生异常，这从每次调用时都会出现的 `[thrower(...)] done` 输出所示。

# 第 12 章 执行

本章规定了程序运行期间发生的各项活动。它围绕 Java 虚拟机的生命周期、接口以及构成程序的对象展开。

Java 虚拟机通过加载指定的类或接口启动，然后调用该指定类或接口中的 `main` 方法。第 12.2 节概述了执行 `main` 所涉及的加载、链接和初始化步骤，作为对本章概念的介绍。后续章节详细规定了加载（§12.2）、链接（§12.3）和初始化（§12.4）的细节。

本章继续介绍了创建新类实例的程序（§12.5）以及类实例的终结处理（§12.6）。最后，通过描述类的卸载（§12.7）以及程序退出时遵循的程序（§12.8）作为结束。

## 12.1 Java 虚拟机的启动

Java 虚拟机通过调用某个指定类或接口的 `main` 方法启动，传递一个参数，该参数是一个字符串数组。在本规范的示例中，第一个类通常被称为 `Test`。

Java 虚拟机启动的精确语义在《Java 虚拟机规范，Java SE 14 版》的第 5 章给出。在这里我们从 Java 编程语言的角度给出该过程的概述。

向 Java 虚拟机指定初始类或接口的方法超出了本规范的范围，但在使用命令行的主机环境中，典型的做法是将类或接口的全限定名作为命令行参数指定，并将随后的 Java 虚拟机启动行参数作为字符串，提供给 `main` 方法的参数使用。

例如，在 UNIX 实现中，命令行：

```
java Test reboot Bob Dot Enzo
```

通常会通过调用类 `Test`（一个未命名包中的类）的 `main` 方法来启动 Java 虚拟机，并向其传递包含 "reboot"、"Bob"、"Dot" 和 "Enzo" 四个字符串的数组。

我们现在概述 Java 虚拟机可能执行 `Test` 的步骤，作为后续章节中进一步描述的加载、链接和初始化过程的示例。

### 12.1.1 加载类 Test

首次尝试执行类 `Test` 的 `main` 方法会发现 `Test` 类未加载——即 Java 虚拟机当前不包含该类的二进制表示。随后，Java 虚拟机将使用类加载器尝试寻找此种二进制表示。如果此过程失败，则会抛出错误。此加载过程在 §12.2 中有进一步描述。

### 12.1.2 链接 Test：验证、准备、（可选的）解析

`Test` 加载后，必须在调用 `main` 之前进行初始化。而且 `Test` 与所有（类或接口）类型一样，在初始化之前必须经过链接。链接涉及验证、准备和（可选的）解析。链接在 §12.3 中有进一步描述。

验证检查加载的 `Test` 表示是否格式正确，并具有正确的符号表。验证还检查实现 `Test` 的代码是否遵守 Java 编程语言和 Java 虚拟机的语义要求。如果在验证期间检测到问题，则会抛出错误。验证在 §12.3.1 中有进一步描述。

准备涉及静态存储以及 Java 虚拟机实现内部使用的任何数据结构（例如方法表）的分配。准备工作在 §12.3.2 中有进一步描述。

解析是检查从 `Test` 到其他类和接口的符号引用的过程，通过加载提到的其他类和接口，并检查这些引用是否正确。

解析步骤在初始链接时是可选的。实现可以在非常早期就解析正在链接的类或接口的符号引用，甚至可以递归地解析从进一步引用的类和接口中所有的符号引用。（这种解析可能会导致这些后续加载和链接步骤产生错误。）此实现选择了一种极端情况，类似于多年以来 C 语言简单实现中一直采用的“静态”链接。（在这些实现中，编译后的程序通常被表示为 "a.out" 文件，该文件包含一个完全链接的程序版本。这些库程序包含在 "a.out" 文件中。）

实现也可以选择仅在符号引用被积极使用时才解析；对所有符号引用采用这种策略代表了最“懒”的解析形式。在这种情况下，如果 `Test` 有指向另一个类的符号引用，则解析过程在 §12.3.3 中进一步描述。

### 12.1.3 初始化 Test：执行初始化器

在我们持续的示例中，Java 虚拟机仍在尝试执行类 `Test` 的 `main` 方法。初始化包括按照文本顺序执行任何类变量初始化器和静态初始化器。在初始化 `Test` 之前，必须初始化其直接父类，以及其父类的直接父类，依此类推。在最简单的情况下，`Test` 以 `Object` 为其隐式父类；如果类 `Object` 尚未初始化，则必须在初始化 `Test` 之前对其初始化。`Object` 没有父类，因此递归终止。

如果类 `Test` 有另一个类 `Super` 作为其父类，则必须在初始化 `Test` 之前初始化 `Super`。这需要在尚未完成的情况下加载、验证并准备 `Super`，并且取决于实现，可能还涉及解析 `Super`。

初始化可能会导致加载、链接和初始化错误，包括涉及其他类型的错误。

初始化过程在 §12.4 中有进一步描述。

### 12.1.4 调用 Test.main

最后，在完成类 `Test` 的初始化（在此期间可能发生了后续加载、链接和初始化），调用 `Test` 的 `main` 方法。

`main` 方法必须声明为 `public`、`static` 和 `void`。它必须指定一个形式参数（§8.4.1），其声明类型为 `String` 数组。因此，以下两种声明都是可以的：

```java
public static void main(String[] args)

public static void main(String... args)
```



## 12.2 类和接口的加载

加载是指寻找特定名称的类或接口类型的二进制格式的过程，可能是动态计算的，但更常见的方法是检索由 Java 编译器从源码编译的二进制表示，并从该二进制构建一个表示该类或接口的 `Class` 对象。加载的精确语义在《Java 虚拟机规范，Java SE 14 版》的第 5 章给出。在这里我们从 Java 编程语言的角度给出该过程的概述。

类或接口的二进制格式通常是类文件格式……但只要符合 §13.1 规定的要求，其他格式也是可能的。

### 执行

`ClassLoader` 类的 `defineClass` 方法可用于从 `class` 文件格式的二进制表示中构建 `Class` 对象。

良好的类加载器维护着这些属性：

- 在名称相同的情况下，一个良好的类加载器应该始终返回相同的类对象。
- 如果类 `L1` 将类 `c` 的加载委托给另一个加载器 `L2`，那么对于任何作为 `c` 的直接超类或直接接口的类型 `T`，或作为 `c` 中字段的类型 `T`，或作为 `c` 中方法或构造函数的形式参数的类型 `T`，或作为 `c` 中方法的返回类型类型 `T`，`L1` 和 `L2` 应该返回相同的 `Class` 对象。

恶意的类加载器可能会违反这些属性。但它无法破坏系统类型的安全性，因为 Java 虚拟机对此进行了防范。

> 关于这些问题的进一步讨论，请参见 *The Virtual Machine Specification, Java SE 14 Edition* 以及由 Sheng Liang 和 Liang Branch 写的 *Dynamic Class Loading in the Java Virtual Machine*，收于 *Proceedings of OOPLA '98, published as ACM SIGPLAN Notices, Volume 30, October 1998*，第 36–44 页。Java 语言设计的基本原则是：运行时类型系统无法被 Java 语言编写的代码所破坏，即使是像 `ClassLoader` 和 `SecurityManager` 这样或其他敏感系统类的实现。

### 12.2.1 加载过程

加载过程由 `ClassLoader` 类及其子类实现。

`ClassLoader` 的不同子类可以实现不同的加载策略。特别是，类加载器可能会缓存类和接口的二进制表示，根据预期使用对其进行预取，或者一起加载一组相关的类。如果例如，由于类加载器缓存了旧版本而没有找到新编译的类版本，那么这些活动对于运行中的应用程序来说可能不是完全透明的。类加载器的责任是，仅在程序中那些在没有预取或分组加载的情况下可能发生错误的地方反映加载错误。

如果在类加载期间发生错误，则会在程序中（直接或间接）使用该类型的任何点抛出以下类 `LinkageError` 类的任一子类的实例：

- `ClassCircularError`：无法加载某个类或接口，因为它将成为自身的超类或超接口（§8.1.4, §9.1.3, §13.4.4）。
- `ClassFormatError`：声称为指定请求编译类或接口的二进制数据格式错误。
- `NoClassFoundError`：相关的类加载器未找到请求的类或接口的定义。

由于链接涉及新数据结构的分配，它可能会因 `OutOfMemoryError` 失败。

## 12.3 类和接口的链接

链接是将类或接口类型的二进制形式并将其组合到 Java 虚拟机的运行时状态中的过程，以便其执行。类或接口类型在链接之前总是会被加载。

链接涉及三种不同的活动：验证、准备和符号引用的解析。

链接的精确语义在 *The Java Virtual Machine Specification, Java SE 14 Edition* 的第 5 章中给出。这里我们从 Java 语言的角度给出了该过程的概述。

该规范允许在进行链接活动（以及由于递归导致的加载）时具有实现上的灵活性，前提是尊重 Java 语言的语义，在初始化类或接口之前已对其进行了完全的验证和准备，并且在链接期间检测到的错误是在程序执行某项可能链接到错误中类或接口的动作的程序点抛出的。

例如，实现可以选择仅在在使用时才单独解析类或接口中的每个符号引用（惰性解析或延迟解析），或者在验证类时一次性解析所有符号引用（静态解析）。这意味着在某些实现中，在类或接口已初始化之后，解析过程可能仍在继续。

由于链接涉及新数据结构的分配，它可能会因 `OutOfMemoryError` 失败。

### 12.3.1 二进制表示的验证

验证确保类或接口的二进制表示在结构上是正确的。例如，它检查每条指令是否有有效的操作码；每个分支指令是否跳转到某些其他指令的开头，而不是指令的中间；每个方法是否提供了结构上正确的签名；以及每条指令是否遵守 Java 虚拟机语言的类型规范。

如果在验证期间发生错误，则会在导致类被验证的程序点抛出以下 `LinkageError` 类的任一子类的实例：

- `VerifyError`：类或接口的二进制定义未能通过一系列所需的检查，以验证它是否遵守 Java 虚拟机语言的语义以及它是否不会破坏 Java 虚拟机的完整性。（某些示例参见 §13.4.2, §13.4.4, §13.4.9 和 §13.4.17。）

### 12.3.2 类或接口类型的准备

准备涉及为类或接口创建静态字段（类变量和常量）并将这些字段初始化为默认值（§12.4.5）。这不需要执行你的任何源代码；静态字段的显式初始化器是在初始化（§12.4）准备的一部分中执行的。

> Java 虚拟机的实现可以在准备阶段准备额外的数据结构，以便后续对类或接口的操作更高效。一种特别有用的数据结构是“方法表”或其他数据结构，它允许在类的实例上调用任何方法，而不需要在调用时对超类搜索。

### 12.3.3 符号引用的解析

类或接口的二进制表示使用其他类和接口的二进制名称（§13.1）符号地引用其他类和接口的字段、方法和构造函数。对于字段和方法，这些符号引用包括字段或方法所属的类或接口类型的名称，以及字段或方法本身的名称，带有适当的类型信息。

在检查符号引用是否正确之前，它必须经过解析，其中符号引用会被检查，并被替换为直接引用，如果该引用被重复使用，则可以被更高效地处理。

如果在解析期间发生错误，将抛出一个错误。最常见的情况下，这将是类 `IncompatibleChangeError` 类的任一子类的实例，但也可能是 `IncompatibleChangeError` 的某些子类的实例，甚至是 `IncompatibleChangeError` 类的实例。此错误可能会在程序中直接或间接使用该类型符号引用的任何点抛出：

- `IllegalAccessError`：遇到一个符号引用指定了字段的使用或赋值、方法的调用或类的实例化，但包含引用的代码没有访问权限，因为该字段或方法被声明为 private、protected 或包访问（非 public），或者因为该类未声明为 public。这可能发生，例如，原本为 public 的字段在另一个引用它的类编译后被更改为 private（§13.4.7）；或者如果一个 public 类所在的包在另一个引用它的模块编译后不再由其模块导出（§13.3）。
- `InstantiationError`：遇到一个用于类实例创建符号引用，但无法创建实例，因为该引用实际上指向一个接口或抽象类。这可能发生，例如，一个原本抽象的类在另一个引用它的类编译后被更改为抽象类（§13.4.1）。
- `NoSuchFieldError`：遇到一个引用特定类或接口中特定字段的符号引用，但该类或接口不包含该名称的字段。这可能发生，例如，一个字段声明在另一个引用它的类编译后被删除了（§13.4.8）。
- `NoSuchMethodError`：遇到一个引用特定类或接口中特定方法的符号引用，但该类或接口不包含具有该签名的方法方法。这可能发生，例如，一个方法在另一个引用它的类编译后被删除了（§13.4.12）。

此外，如果一个类声明了无法找到实现的本地方法，则可能会抛出 `LinkageError` 的子类 `UnsatisfiedLinkError`。该错误将在方法被使用时发生，或者更早发生，取决于 Java 虚拟机实现所使用的何种解析策略（§12.3）。

## 12.4 类和接口的初始化

类的初始化包括执行其静态初始化器以及在类中声明的静态字段（类变量）的初始化器。

接口的初始化包括执行在接口中声明的字段（常量）的初始化器。

### 12.4.1 初始化发生的时机

类或接口类型 T 将在以下任意一种情况首次出现之前立即进行初始化：

- T 是一个类，并且创建了 T 的实例。
- 调用了由 T 声明的静态方法。
- 对由 T 声明的静态字段进行了赋值。
- 使用了由 T 声明的静态字段，且该字段不是常量变量 (§4.12.4)。

当一个类被初始化时，它的超类也会被初始化（如果它们之前未被初始化），任何声明了默认方法 (§9.4.3)的超接口 (§8.1.5)也会被初始化（如果它们之前未被初始化）。接口的初始化本身不会导致其任何超接口的初始化。

对静态字段 (§8.3.1)的引用会导致声明该字段的类或接口的初始化，即使它是通过子类、子接口或实现接口的类的名称被引用的。

在类 `Class` 和包 `java.lang.reflect` 中调用某些反射方法会导致类或接口的初始化。

在任何其他情况下，类或接口都不会被初始化。

> 注意，编译器可能会在接口中生成合成方法，即既没有显式声明也没有隐式声明的默认方法 (§13.1)。这些方法会触发接口的初始化，尽管源代码并没有指示该接口应该被初始化。

其意图是让类或接口类型有一组初始化器将其置于一个一致的状态，并且该状态是其他类观察到的第一个状态。静态初始化器和类变量初始化器按照文本顺序执行，并且可能引用类中声明的、在文本上出现在其声明之后的类变量，尽管这些类变量在作用域内 (§8.3.3)。

此限制旨在编译时检测出大多数循环或其他异常的初始化。

初始化代码不受限制的这一事实允许构建此类示例：即在类变量仍保持其初始默认值时就可以观察到它的值，但此类示例在实践中很少见。（同样也可以为实例变量初始化构建此类示例 (§12.5)）。Java 语言的完整功能在这些初始化器中都是可用的；程序员必须格外小心。这种力量给代码生成器带来了额外的负担，但由于 Java 语言是并发的 (§12.4.2)，这种负担在任何情况下都会产生。

#### 示例 12.4.1-1. 超类在子类之前初始化

```java
class Super {
    static { System.out.print("Super "); }
}

class One {
    static { System.out.print("One "); }
}

class Two extends Super {
    static { System.out.print("Two "); }
}

class Test {
    public static void main(String[] args) {
        One o = null;
        Two t = new Two();
        System.out.println((Object)o == (Object)t);
    }
}
```

该程序产生：

```
Two false
```

类 `One` 从未初始化，因为它没有被主动使用，因此从未被链接。类 `Two` 只有在它的超类 `Super` 初始化后才被初始化。

#### 示例 12.4.1-2. 只有声明静态字段的类被初始化

```java
class Super {
    static int taxi = 1729;
}

class Sub extends Super {
    static { System.out.print("Sub "); }
}

class Test {
    public static void main(String[] args) {
        System.out.println(Sub.taxi);
    }
}
```

该程序只打印：

```
1729
```

因为类 `Sub` 从未被初始化；对 `Sub.taxi` 的引用是对实际声明在类 `Super` 中的字段的引用，并且不会触发类 `Sub` 的初始化。

#### 示例 12.4.1-3. 接口初始化不会初始化超接口

```java
interface I {
    int i = 1, ii = Test.out("ii", 2);
}

interface J extends I {
    int j = Test.out("jj", 3), jj = Test.out("jj", 4);
}

interface K extends J {
    int k = Test.out("k", 5);
}

class Test {
    public static void main(String[] args) {
        System.out.println(J.i);
        System.out.println(K.j);
    }

    static int out(String s, int i) {
        System.out.println(s + "=" + i);
        return i;
    }
}
```

该程序产生：

```
1
j=3
jj=4
3
```



# 12.4.2 详细初始化过程

由于 Java 语言是并发的（§12.4.2），初始化类或接口需要一个唯一的初始化锁 `LC`。对于每个类或接口，Java 虚拟机负责处理同步。初始化过程假设类对象处于以下四种状态之一：

- 该类对象已通过验证但尚未完全初始化。
- 该类对象正在由另一个线程初始化。
- 该类对象已完全初始化并可以使用。
- 该类对象处于错误状态，因为尝试初始化失败了。

初始化 `c` 的过程如下：

1. 在初始化锁 `LC` 上同步。
2. 如果类对象显示初始化正在由另一个线程进行，则释放 `LC` 并等待该初始化完成，此时重复执行此过程。
3. 如果类对象显示初始化正在由当前线程进行，则这必须是递归初始化请求。释放 `LC` 并正常完成。
4. 如果类对象显示已完成初始化，则不需要执行进一步操作。释放 `LC`。
5. 如果类对象处于错误状态，则初始化不可。释放 `LC` 并抛出 `NoClassFoundError`。

否则，记录类对象的初始化正在由当前线程进行，并释放 `LC`。

然后初始化 `c` 的常量变量（§4.12.4, §8.3.2）。

接下来，如果 `c` 是类而不是接口，让 `sc` 为其超类，让 `SI₁, ..., SIn` 为 `c` 声明了至少一个默认方法的所有超接口。接口的顺序由对 `c` 直接实现的每个接口的递归枚举给出（按照 `implements` 子句的顺序）。如果 `c` 直接实现了接口 `I`，在遍历 `I` 的超接口（按照 `extends` 子句的顺序）之前返回 `I`。

对于列表 `[SC, SI₁, ..., SIn]` 中的每个 `s`，如果 `s` 未被初始化，则递归执行此过程。如有必要，先验证并准备 `s`。

如果 `s` 的初始化由于抛出异常而异常终止，则获取 `LC`，将类对象标记为错误，通知所有等待线程，释放 `LC` 并异常完成，传播导致初始化 `s` 的异常。

接下来，通过查询其类加载器确定 `c` 是否启用了断言（§14.10）。

接下来，按照文本顺序执行类的初始化和静态初始化器或接口的字段初始化器，假设它们是一个代码块。

如果初始化器的执行正常完成，则获取 `LC`，将类对象标记为完全初始化，通知所有等待线程，释放 `LC` 并正常完成此操作。

否则，初始化器通过抛出某些异常 `E` 异常终止。如果类 `E` 不是 `Error` 或其子类，则创建一个 `ExceptionInitializerError` 的新实例并以 `E` 为参数，并在后续步骤中使用该对象替换 `E`。如果由于内存无法创建 `ExceptionInitializerError` 的新实例，则使用 `OutOfMemoryError` 对象替换 `E` 以便后续步骤使用。

获取 `LC`，将类对象标记为错误，通知所有等待线程，释放 `LC` 并根据上一步中确定的 `E` 或其替换对象异常地完成此过程。

一个实现可以通过跳过第 1 步中的锁获取（以及第 4/5 步中的释放）来优化此过程，前提是它可以确定类的初始化已经完成。从内存模型的角度来看，如果获取了锁将会存在的所有“发生于”（happens-before）序关系，在执行该优化时依然存在。

代码生成器需要保留类或接口可能初始化的点，插入上述描述的初始化过程的调用。如果此初始化过程正常完成且类对象已完全初始化并准备好使用，则对初始化过程的调用就不再是必要的，并且可以从代码中消除——例如，通过补丁将其移除或重新生成代码。

在某些情况下，如果能够确定一组相关类型的初始化顺序，编译时分析可能能够从生成的代码中消除许多对类型是否已初始化的检查。然而，这种分析必须充分考虑并发性，以及初始化代码不受限制的这一事实。

# 创建新类实例

当对类实例创建表达式（§15.9）的评估导致类实例化时，一个新的类实例被显式地创建。

在以下情况下，可能会隐式地创建新的类实例：

- 加载包含字符串字面量的类或接口（§13.10.5）可能会创建一个新的 `String` 对象来表示该字面量。（如果之前已经 intern 过表示相同 Unicode 代码点序列的字符串，则不会发生这种情况。）
- 执行带有装箱转换（§15.7）的操作。装箱转换可能会为任何原始类型关联包装类（`Boolean`, `Byte`, `Short`, `Character`, `Integer`, `Long`, `Float`, `Double`）创建一个该包装类的新对象。
- 执行不是常量表达式（§15.29）一部分的字符串拼接运算符 `+`（§15.18.1）总是创建一个新的 `String` 对象来表示结果。字符串拼接运算符还可能为原始类型的值创建临时包装对象。
- 评估方法引用表达式（§15.13.3）或 `lambda` 表达式（§15.27.4）可能需要创建一个实现函数式接口类型的类的新实例。

这些情况中的每一种都指明了一个特定的构造方法（§8.8），作为类实例创建过程的一部分，使用指定的参数（可能为空）进行调用。

## 创建新类实例

每当创建一个类实例时，都会为它分配内存空间，以容纳类类型中声明的所有实例变量以及该类类型每个子类声明的所有实例变量，包括可能被隐藏的所有实例变量（§8.3）。

如果没有足够的空间为对象分配内存，则类实例的创建将以 `OutOfMemoryError` 异常终止。否则，新对象中的所有实例变量（包括在父类中声明的变量）都将初始化为它们的默认值（§4.12.5）。

在将新创建对象的引用作为结果返回之前，将处理指定的构造方法，使用以下过程初始化新对象：

1. 将构造方法的参数分配给此构造方法调用新创建的参数变量。
2. 如果此构造方法以对同类中另一个构造方法的显式构造方法调用（§8.8.7.1）开始（使用 `this`），则评估参数，并使用这相同的五个步骤递归地处理构造方法调用。如果构造方法调用异常终止，则此过程也将由于相同原因异常终止；否则，继续执行第 5 步。
3. 此构造方法不是以对同类中另一个构造方法的显式构造方法调用（使用 `this`）开始。如果这是一个 `Object` 以外的类，则此构造方法将从父类构造方法的显式或隐式调用（使用 `super`）开始。评估参数，并使用这五个步骤递归地处理该子类构造方法调用。如果该构造方法调用异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 4 步。
4. 执行此类的实例初始化器和实例变量初始化器，为该类赋值，分配实例变量初始化器的值。如果在执行这些类初始化器的过程中发生异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 5 步。
5. 执行构造方法的体。Java 语言规定，在对象完全初始化之前，执行被覆盖的方法。如果在这些初始化过程中发生异常终止，则方法将异常终止。

### Example 12.5-1. 实例化创建

```java
class Point {
    int x = 1;

    Point() {
        x = 1;
    }
}

class ColorPoint extends Point {
    String s = new String("hello");

    ColorPoint() {
        super();
    }
}

class Test {
    int color = 0xFFFF;

    Test() {
        super();
    }

    public static void main(String[] args) {
        ColorPoint cp = new ColorPoint();
        System.out.println(cp.x);
        System.out.println(cp.s);
        System.out.println(cp.color);
    }
}
```

在此例中，当 `new ColorPoint()` 被评估时，一个新的 `ColorPoint` 实例被创建。为它分配内存空间以容纳 `Point` 类型中声明的所有实例变量以及 `ColorPoint` 类子类中声明的所有实例变量，包括可能被隐藏的所有实例变量。如果没有足够的空间为对象分配内存，则类实例的创建将以 `OutOfMemoryError` 终止。否则，新对象中的所有实例变量（包括在父类中声明的变量）都将初始化为它们的默认值。

在将新创建对象的引用作为结果返回之前，将处理指定的构造方法。以下过程：

1. 将 `ColorPoint` 构造方法的参数分配给此构造方法调用新创建的参数变量。
2. 如果此构造方法以对 `ColorPoint` 同类中另一个构造方法的显式构造方法调用（使用 `this`）开始，则评估参数，并使用这相同的五个步骤递归地处理构造方法调用。如果构造方法调用异常终止，则此过程也将由于相同原因异常终止；否则，继续执行第 5 步。
3. 此构造方法不是以对 `ColorPoint` 同类中另一个构造方法的显式构造方法调用（使用 `this`）开始。如果这是一个 `Object` 以外的类，则此构造方法将从父类 `Point` 构造方法的显式或隐式调用（使用 `super`）开始。评估参数，并使用这五个步骤递归地处理该子类构造方法调用。如果该构造方法调用异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 4 步。
4. 执行此类的实例初始化器和实例变量初始化器，为该类赋值，分配实例变量初始化器的值。如果在执行这些类初始化器的过程中发生异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 5 步。
5. 执行构造方法的体，使用以下过程初始化新对象：Java 语言规定，在对象完全初始化之前，执行被覆盖的方法。

由于 `ColorPoint` 构造方法包含对 `Point` 构造方法的显式调用（使用 `super`）：

1. 将 `Point` 构造方法的参数分配给此构造方法调用新创建的参数变量。
2. 如果此构造方法（`Point`）以对 `Point` 同类中另一个构造方法的显式构造方法调用（使用 `this`）开始，则评估参数，并使用这相同的五个步骤递归地处理构造方法调用。如果构造方法调用异常终止，则此过程也将由于相同原因异常终止；否则，继续执行第 5 步。
3. 此构造方法不是以对 `Point` 同类中另一个构造方法的显式构造方法调用（使用 `this`）开始。如果这是一个 `Object` 以外的类，则此构造方法将从父类 `Object` 构造方法的显式或隐式调用（使用 `super`）开始。评估参数，并使用这五个步骤递归地处理该子类构造方法调用。如果该构造方法调用异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 4 步。
4. 执行此类的实例初始化器和实例变量初始化器，为该类赋值，分配实例变量初始化器的值。如果在执行这些类初始化器的过程中发生异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 5 步。
5. 执行构造方法的体，使用以下过程初始化新对象：Java 语言规定，在对象完全初始化之前，执行被覆盖的方法。

由于 `Point` 构造方法包含对 `Object` 构造方法的显式调用（使用 `super`）：

1. 将 `Object` 构造方法的参数分配给此构造方法调用新创建的参数变量。
2. 如果此构造方法（`Object`）以对 `Object` 同类中另一个构造方法的显式构造方法调用（使用 `this`）开始，则评估参数，并使用这相同的五个步骤递归地处理构造方法调用。如果构造方法调用异常终止，则此过程也将由于相同原因异常终止；否则，继续执行第 5 步。
3. 此构造方法不是以对 `Object` 同类中另一个构造方法的显式构造方法调用（使用 `this`）开始。由于 `Object` 没有父类，此步被跳过。
4. 执行此类的实例初始化器和实例变量初始化器，为该类赋值，分配实例变量初始化器的值。如果在执行这些类初始化器的过程中发生异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 5 步。
5. 执行构造方法的体，使用以下过程初始化新对象：Java 语言规定，在对象完全初始化之前，执行被覆盖的方法。

由于 `Object` 构造方法没有初始化体，且没有父类，它直接完成。现在，`Point` 构造方法继续其执行：

4. 执行此类的实例初始化器和实例变量初始化器，为该类赋值，分配实例变量初始化器的值。如果在执行这些类初始化器的过程中发生异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 5 步。
5. 执行构造方法的体，使用以下过程初始化新对象：Java 语言规定，在对象完全初始化之前，执行被覆盖的方法。

在 `Point` 构造方法的体中，执行了 `x = 1`。现在，`ColorPoint` 构造方法继续其执行：

4. 执行此类的实例初始化器和实例变量初始化器，为该类赋值，分配实例变量初始化器的值。如果在执行这些类初始化器的过程中发生异常终止，则此过程也将由于相同原因异常终止。否则，继续执行第 5 步。
5. 执行构造方法的体，使用以下过程初始化新对象：Java 语言规定，在对象完全初始化之前，执行被覆盖的方法。

在 `ColorPoint` 构造方法的体中，执行了 `s = new String("hello")` 和 `color = 0xFFFF`。现在，`ColorPoint` 实例已完全初始化。

### Example 12.5-2. 实例化创建期间动态分派

```java
class Super {
    Super() { printThree(); }
    void printThree() { System.out.println("three"); }
}

class Test extends Super {
    int three = (int)Math.PI; // 即 3
    void printThree() { System.out.println(three); }
    public static void main(String[] args) {
        Test t = new Test();
        t.printThree();
    }
}
```

此程序产生输出：

```
0
3
```

这表明在 `Super` 构造方法中对 `printThree` 的调用并没有调用 `Super` 类中的 `printThree` 定义，而是调用了 `Test` 类中重写的 `printThree` 定义。因此，该方法在 `Test` 的字段初始化器执行之前运行，这就是为什么第一个输出值是 0，即 `three` 字段初始化的默认值。随后在 `main` 方法中对 `printThree` 的调用使用了相同的定义，所以打印了值 3。

## 类实例的终结

Java 编程语言没有规定终结器何时会被调用，仅规定它会在对象的存储空间被重用之前发生。

Java 编程语言没有规定由哪个线程来调用任何给定对象的终结器。

> 需要注意的是，可能有许多终结器线程处于激活状态（这在大型共享内存多处理器上有时是必要的），并且如果一个大型数据结构变成垃圾，那么该数据结构中每个对象的 `finalize` 方法都可能同时被调用，每个终结器的调用都运行在不同的线程中。

Java 编程语言对 `finalize` 方法的调用不加顺序限制。终结器可以以任何顺序被调用，甚至可以并发调用。

例如，如果一组未终结对象的循环链组变得不可达（或变为对终结器可达），则所有对象将同时变为可终结。这些对象的终结器可能会以任何顺序被调用，甚至使用多个线程并发调用。如果自动存储管理器随后发现这些对象是不可达的，那么它们的存储空间就可以被回收。

实现一个类以使得一组对象在所有对象都变得不可达时，按特定顺序调用一组类终结器的方法是直接的。定义这样一个类留给读者作为练习。

可以保证，在调用终结器时，调用它的线程不会持有任何用户可见的同步锁。

如果在终结过程中抛出未捕获的异常，该异常将被忽略且该对象的终结将终止。

对象构造函数的完成 happens-before（§17.4.5） 其 `finalize` 方法的执行（在 happens-before 的正式意义上）。

在类 `Object` 中声明的 `finalize` 方法不执行任何操作。`Object` 类声明了 `finalize` 方法这一事实意味着，任何类的 `finalize` 方法都可以调用其超父类的 `finalize` 方法。这应该始终这样做，除非程序员的意图是将父类终结器中的对象置为空。（与构造函数不同，终结器不会自动调用父类的终结器；这种调用必须显式地编码。）

为了效率考虑，实现类可能会跟踪那些没有重写 `Object` 类 `finalize` 方法、或以简单方式重写该方法的类。

例如：

```java
protected void finalize() throws Throwable {
    super.finalize();
}
```



### 执行

### 类实例的终结

#### 12.6

我们鼓励实现将对象视为拥有一个未重写的终结器，并按照 §12.6.1 中的描述更高效地终结它们。

终结器可以被显式调用，就像任何其他方法一样。

`java.lang.ref` 包描述了弱引用，它与垃圾收集和终结相互作用。对于任何与 Java 编程语言有特殊交互的 API，实现者必须意识到 `java.lang.ref` API 施加的任何要求。本规范不以任何方式讨论弱引用。详情请参阅 API 文档。

#### 12.6.1 实现终结

每个对象都可以通过两个属性来描述：它可能是可达的、对终结器可达的或不可达的；它可能是未终结的、可终结的或已终结的。

*   **可达（reachable）对象**：指从任何活动线程的任何潜在后续计算中都可以访问的对象。
*   **对终结器可达（finalizer-reachable）对象**：可以通过某些引用链从某个可终结对象到达，但无法从任何存活线程到达。
*   **不可达（unreachable）对象**：无法通过这两种方式到达。
*   **未终结（unfinalized）对象**：终结器从未被自动调用过。
*   **已终结（finalized）对象**：终结器已经被自动调用过。
*   **可终结（finalizable）对象**：终结器从未被自动调用过，但 Java 虚拟机可能会最终自动调用其终结器。

对象 `o` 直到被终结，直到它的构造函数调用了 `o` 上的 `Object` 构造函数且该调用成功完成（即没有抛出异常）。在终结之前对对象字段的任何写入操作都必须对该对象的终结可见。此外，对该对象字段的任何终结前读取操作都不应看到在对象终结开始之后发生的写入。

优化程序的转换可以被设计为减少可达对象的数量，使其少于直观认为是可达的数量。例如，Java 编译器或代码生成器可能会将不再使用的变量或参数设为 `null`，以导致此类对象的存储空间可能更早地回收。

另一个示例发生在对象字段中的值存储在寄存器中时。此时程序可以访问对象而不是堆。请注意，这种优化仅在引用是可达的情况下才允许。例如，考虑守护者模式：

```java
class Foo {
    private Object guardian = new Object() {
        protected void finalize() throws Throwable {
            /* finalize() */
        }
    };
}
```



如果一个对象的终结器被调用，则内存模型必须决定何时 `y` 是同步的使得 `so(x, y)` (§17.4) 且 `y comes-before de`，则 `x` 必须是可达的。

### 12.6.2 与内存模型的交互

本节描述了终结与内存模型的交互。每次执行都有若干可达性点。在每个可达性点，一组对象被标记为不可达，另一部分对象被标记为可终结。这些可达性点也是根据 `java.lang.ref` 包提供的规则检查、入队和清除引用的点。

在点 `di` 处被认为可达的对象仅是那些可以通过应用这些规则证明是可达的那些：

- 如果存在一个对类 `c` 静态字段的写入 `w1`，`w1` 写入的值是引用 `B` 的引用，`c` 被一个可达的类加载器加载，且不存在对 `v` 的写入 `w2` 使得 `hb(w2, w1)` 不成立且 `w1` 和 `w2` 在 `di` 之前，则对象 `B` 在 `di` 处是确定可达的。
- 如果存在对 `A` 的元素 `v` 的写入 `w1`，`w1` 写入的值是引用 `B` 的引用，且不存在对 `v` 的写入 `w2` 使得 `hb(w2, w1)` 不成立且 `w1` 和 `w2` 在 `di` 之前，则对象 `B` 从 `A` 是确定可达的。
- 如果对象 `C` 从对象 `B` 可达，且对象 `B` 从 `A` 是可达的，则 `C` 从 `A` 是可达的。

如果对象 `x` 在 `di` 处被标记为不可达，则：

- `x` 在 `di` 处从静态字段不是确定可达的；且
- 线程 `t` 中在 `di` 之后的所有对 `x` 的活跃使用必须发生在 `x` 的终结调用中，或作为线程 `t` 执行 `di` 之后的 `x` 引用的结果；
- 所有在 `di` 之后看到 `x` 引用的读取必须看到 `di` 处不可达对象的元素的写入，或者看到 `di` 之后发生的写入。

如果满足以下至少一个条件，则操作 `a` 是对 `x` 的活跃使用：

- `a` 读取或写入 `x` 的元素
- `a` 锁定或释放 `x`，且存在对 `x` 的锁操作发生在 `x` 终结调用之后
- `a` 写入引用 `x`
- `a` 是对象 `y` 的活跃使用，且 `x` 从 `y` 是确定可达的

如果对象 `x` 在 `di` 处被标记为可终结的，则：

- `x` 必须在 `di` 处被标记为不可达；且
- `di` 必须是 `x` 被标记为可终止的唯一地方；且
- 发生在终结器调用之后的动作必须发生在 `di` 之后。

## 12.7 类和接口的卸载

Java 编程语言的实现可能会卸载类。

当且仅当一个类或接口定义的类加载器可以像 §12.6 所示被垃圾收集器回收时，该类或接口可能会卸载。

由引导加载器加载的类和接口不能被卸载。

类卸载是一种有助于减少内存的优化。显然，程序的语义不应依赖于系统是否以及如何选择实现诸如卸载之类的优化。这样做将损害程序的移植性。因此，一个类或接口是否已卸载，对程序来说应该是透明的。

然而，如果类 `C` 在其定义加载器可能仍可达时被卸载，那么 `C` 可能会被重新加载。人们可以确保这种情况不会发生。即使该类没有被任何当前加载的加载器引用，它也可能被尚未加载的某个类或接口 `D` 引用。当 `D` 被 `C` 的定义加载器加载时，其执行可能会导致 `C` 的加载。

重新加载可能不是透明的，例如，如果类具有静态变量（其状态将会丢失）、静态初始化器（可能会产生副作用）或原生方法（可能会保留静态状态）。此外，类对象依赖于其身份标识。因此，通常情况下，以完全透明的方式重新加载类或接口是不可能的。

由于我们无法保证卸载一个加载器可达的类或接口不会导致重新加载，且重新加载从不是透明的，但卸载必须是透明的，因此在其加载器可能仍可达时卸载类或接口。类似的推理过程可以推断出，由引导加载器加载的类和接口是可以被卸载的。

必须论证如果定义类加载器可以被回收，卸载类 `C` 是安全的。如果定义加载器可以被回收，那么永远不存在指向它的存活引用（这包括不存活但可能被终结器复活的引用）。反过来，只有当对于该加载器定义的类（包括 `C`），从其实例或代码中都没有任何存活引用时，这种情况才成立。

类卸载是一种优化，对于加载大量类并在一段时间后停止使用其中大多数类的应用来说是有意义的。此类应用的示例是 Web 浏览器，但也有其他应用。此类应用的特征是它们通过显式使用类加载器来管理类。因此，上述策略对它们非常有效。

## 12.8 程序退出

当发生以下两种情况之一时，程序会终止其所有活动并退出：

- 所有非守护线程均终止。
- 某个线程调用了 `Runtime` 类或 `System` 类的 `exit()` 方法，且该退出操作未被安全计数器禁止。

# 第 13 章 二进制兼容性

Java 编程语言的开发工具应该在源代码可用时，根据需要支持自动重新编译。特定的实现还可能将类型的源码和二进制文件存储在版本控制数据库中，并实现一个 `ClassLoader`，该类使用数据库的完整性机制，通过向客户端提供二进制兼容的类型版本来防止链接错误。

要广泛分发的包和类的开发者面临着一套不同的问题。在互联网（这是我们广泛分发系统的第一个例子）中，自动重新编译直接或间接依赖于要更改类型的预存二进制文件通常是不现实或不可能的。相反，本规范定义了一组开发者允许对包、类或接口类型进行的更改，同时保持与预存二进制文件的兼容性（即不破坏兼容性）。

在《SOM 中版本间的二进制兼容性》（Release-to-Release Binary Compatibility in SOM，Forman, Corner, Danforth, and Raper，Proceedings of OOPSLA '95）框架内，Java 编程语言的二进制文件在作者识别的所有相关转换下都是兼容的（在添加实例变量方面有一些例外）。使用他们的方案，以下是 Java 编程语言支持的一些重要的二进制更改列表：

- 重新实现现有的方法、构造函数和初始化器以提高性能。
- 修改方法或构造函数，使其对某些输入返回值，而这些输入之前可能抛出正常不应发生的异常，或因进入无限循环或导致死锁而失败。
- 向现有类或接口中添加新的字段、方法或构造函数。
- 删除类的 `private` 字段、方法或构造函数。
- 当更新整个包时，删除该包内类和接口的包访问权限字段、方法或构造函数。
- 重新排序现有类型声明中的字段、方法或构造函数。
- 在类层级结构中向上移动方法。
- 重新排序类或接口的直接接口列表。
- 在类型层次结构中插入新的类或接口类型。

本章规定了所有实现均保证的二进制兼容性的最低标准。当混合了已知并非来自兼容来源的类和接口二进制文件时，Java 编程语言保证其兼容性，这些来源已被修改。当类和接口二进制文件混合时，Java 编程语言保证兼容性，尽管它们已知并非来自兼容来源，其来源已被修改。这些来源的二进制文件是兼容的。关于 Java 平台版本之间的兼容性讨论超出了本章的范围。

本章首先列举了对包（13.3）、类（13.4）和接口（13.5）的可能更改，说明哪些是保证的，哪些不是。Java SE 14 的二进制文件之间的兼容性取决于二进制文件如何映射。有时会使用 `JVMS §x.y` 形式来指示这些更改对预存二进制文件的影响。

## 13.1 二进制的形态

程序必须以 Java 虚拟机指定的格式编译，或者由类加载器映射到该格式。类或接口声明必须具有某些属性。类或接口声明具有以下属性：

1. 类或接口必须以其*二进制名称*命名，符合以下约束：
   - 顶级类型（7.6）是规范名。
   - 成员类型（8.5, 9.5）由其直接封闭类型的二进制名组成，后跟 `$`，以及成员名。
   - 本地类（14.3）由其直接封闭类型的二进制名组成，后跟 `$`，以及非空数字、类的名。
   - 匿名类（15.9.5）由其直接封闭类型的二进制名组成，后跟 `$`，以及非空数字。
   - 泛型类或接口的类型变量（8.1.2, 9.1.2）由其直接封闭类型的二进制名组成，后跟 `$`，以及类型变量名。
   - 泛型方法（8.4.4）由声明方法的类型二进制名组成，后跟 `$`，以及方法的描述符（JVMS §4.3.3），后跟 `$`，以及类型变量名。
   - 泛型构造函数（8.8.4）由声明构造函数的类型二进制名组成，后跟 `$`，以及构造函数的描述符（JVMS §4.3.3），后跟 `$`，以及类型变量名。

2. 指向另一个类或接口类型的引用必须是符号性的，使用类型的二进制名。

3. 常量变量字段（4.12.4）的引用在编译时解析为常量变量初始化器所指示的值 `v`。

   如果此类字段是静态的，则在二进制文件中不存在该引用，包括声明该字段的类或接口。此类字段必须始终看起来已初始化（12.4.2）；字段的默认初始值（如果与 `v` 不同）永远不会被观察到。

   如果此类字段是非静态的，则在二进制文件中不应存在该字段的引用，但在包含该字段的类中除外（这将类而不是接口，因为接口只有静态字段。）类应该在创建实例时（12.5）代码将字段的值设置为 `v`。

## 13.1 二进制兼容性的形式

4. 给定一个表示类 `c` 中字段访问的合法表达式，其引用了名为 `f` 的字段，该字段 `f` 不是常量变量且在（可能是不同的）类或接口 `D` 中声明，我们定义*字段引用的限定类型*（qualifying type of the field reference）如下：

- 如果该表达式通过简单名称引用，那么如果 `f` 是当前类或接口的成员，则令 `τ` 为 `c`；否则，令 `τ` 为 `f` 所成员的最内层作用域类型声明。无论何种情况，`τ` 都是该引用的限定类型。
- 如果该表达式具有 `TypeName.f` 的形式，其中 `TypeName` 表示一个类或接口，则由 `TypeName` 所指示的类型就是该引用的限定类型。
- 如果该表达式具有 `ExpressionName.f` 或 `Primary.f` 的形式，那么：
    - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交叉类型 `V_1 & ... & V_n` (§4.9)，则该引用的限定类型是 `V_1`。
    - 否则，`ExpressionName` 或 `Primary` 的编译时类型就是该引用的限定类型。
- 如果该表达式具有 `super.f` 的形式，那么 `c` 的超类就是该引用的限定类型。
- 如果该表达式具有 `TypeName.super.f` 的形式，那么由 `TypeName` 所指示的类的超类就是该引用的限定类型。

对 `f` 的引用必须被编译为指向该引用类型擦除（§4.6）的符号引用，加上字段的简单名 `f`。该引用还必须包含指向字段声明类型擦除的符号引用，以便验证器可以检查该类型是否符合预期。

5. 给定类或接口 `c` 中的一个方法调用表达式或方法表达式，其引用了在（可能是不同的）类或接口 `D` 中声明（或隐式声明 §9.2）的名为 `m` 方法，我们定义*方法调用的限定类型*（qualifying type of the method invocation）如下：

- 如果 `D` 是 `Object`，则表达式的限定类型为 `Object`。
- 否则：
    - 如果该方法通过简单名称引用，那么如果 `m` 是当前类或接口 `c` 的成员，令 `τ` 为 `c`；否则，令 `τ` 为 `m` 所成员的最内层作用域类型声明。无论何种情况，`τ` 都是该方法调用的限定类型。
- 如果该表达式具有 `TypeName.m` 或 `ReferenceType::m` 的形式，那么由 `TypeName` 或 `ReferenceType` 所指示的类型就是方法调用的限定类型。
- 如果该表达式具有 `ExpressionName.m` 或 `Primary.m` 或 `ExpressionName::m` 或 `Primary::m` 的形式，那么：
    - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交叉类型 `V_1 & ... & V_n` (§4.9)，则方法调用的限定类型是 `V_i`。
    - 否则，`ExpressionName` 或 `Primary` 的编译时类型就是方法调用的限定类型。
- 如果该表达式具有 `super.m` 或 `super::m` 的形式，那么超类 `c` 就是方法调用的限定类型。
- 如果该表达式具有 `TypeName.super.m` 的形式，且 `TypeName` 指示一个类 `x`，则 `x` 的超类就是方法调用的限定类型；如果 `TypeName` 指示一个接口 `x`，则 `x` 就是方法调用的限定类型。

对方法的引用必须在编译时解析为指向该调用限定类型擦除（§4.6）的符号引用，加上方法签名（§8.4.2）的擦除。该方法的签名必须包含以下由 §15.12.3 确定的所有内容：

- 方法的简单名
- 参数的数量以及每个参数的类型
- 指向每个参数类型的符号引用

对方法的引用还必须包含指向返回类型擦除的符号引用，或者指示的方法为 `void` 且不返回值。

6. 给定类或接口 `c` 中的一个类实例创建表达式 (§15.9)、一个显式构造函数调用语句 (§8.8.7.1) 或具有 `ClassType :: new` 形式（§15.13）的方法引用表达式，引用了在（可能是不同的）类或接口 `D` 中声明的构造函数 `m`，我们定义构造函数调用的限定类型如下：

- 如果该表达式具有 `new D(...)` 或 `ExpressionName.new D(...)` 或 `Primary.new D(...)` 或 `D :: new` 的形式，则调用的限定类型为 `D`。
- 如果该表达式具有 `new D(...) ({...})` 或 `ExpressionName.new D(...) ({...})` 或 `Primary.new D(...) ({...})` 的形式，则表达式的限定类型为该表达式的编译时类型。
- 如果该表达式具有 `super(...)` 或 `ExpressionName.super(...)` 或 `Primary.super(...)` 的形式，则表达式的限定类型为 `c` 的直接超类。
- 如果该表达式具有 `this(...)` 的形式，则表达式的限定类型为 `C`。

对构造函数的引用必须在编译时解析为指向调用限定类型擦除（§4.6）的符号引用，加上构造函数的签名（§8.8.2）。构造函数的签名必须同时包含两项：

- 构造函数的参数数量
- 指向每个形式参数类型的符号引用

类或接口的二进制表示必须包含以下所有内容：

1. 如果它是一个类且不是 `Object`，则包含指向该类直接超类擦除的符号引用。
2. 如果有每个直接超接口，则包含指向每个直接超接口擦除的符号引用。
3. 对类或接口中声明的每个字段的规范，给出字段的简单名和指向字段擦除的符号引用。
4. 如果它是一个类，则包含每个构造函数的擦除签名。
5. 对于类或接口中声明的每个方法（对于接口，排除其隐式方法 §9.2），包含上述描述的擦除签名和返回类型。

实现该类或接口所需的代码：

- 对于接口，字段初始化器的代码以及每个代码块方法的实现（§9.4.3）。
- 对于类，字段初始化器的代码、实例化和静态初始化器的代码、每个代码块方法的实现（§8.4.7），以及每个构造函数的实现。

每个类型必须包含足够恢复其规范形式（canonical §6.7）的信息。

每个成员类型必须包含足够恢复其源码级访问修饰符的信息。

每个嵌套类和嵌套接口必须包含其直接外层类型的符号引用（§8.1.3）。

每个类必须包含所有成员类型的符号引用（§8.5），以及出现在其方法、构造函数、静态初始化器、实例化和字段初始化器中的局部类和匿名类。

每个接口必须包含所有成员类型的符号引用（§9.5），以及出现在其默认方法和字段初始化器中的局部类和匿名类。

11. Java 编译器生成的构造如果不对应于源码中显式或隐式声明的构造，则被标记为*合成的*（synthetic），除非该生成的构造是类初始化方法（JVMS §2.9）。

12. Java 编译器生成的构造如果对应于源码中隐式声明的形式参数，则被标记为*强制的*（mandated）（§8.8.1, §8.8.9, §8.9.3, §15.9.5.1）。

以下形式参数是在源码中隐式声明的：

- *非私有*内部成员类的构造函数的第一个形式参数（§8.8.1, §8.8.9）。
- 内部类或局部类（非静态上下文中）的匿名类的构造函数的第一个形式参数（§15.9.5.1）。
- 枚举类型中隐式声明的 `valueOf` 方法的形式参数*名*（§8.9.3）。

作为参考，以下构造是在源码中隐式声明的，但由于只有形式参数可以在*类*文件中被标记为强制的，因此它们没有标记为强制的（JVMS §4.7.24）：

- 类和枚举类型的默认构造函数（§8.8.9, §8.9.2）
- 匿名构造函数（§15.9.5.1）
- 枚举类型的取值和 `valueOf` 方法（§8.9.3）
- 枚举类型的某些公共字段（§8.9.3）
- 接口的某些公共方法（§9.2）
- 容器注解（§9.7.5）

对应于模块声明的类文件必须具有以下类文件的属性：该类的二进制名称为 `module-info`，且没有超类、没有超接口、没有字段且没有方法。此外，模块的二进制表示必须包含所有内容：

- 模块名称的规范，作为对 `module` 关键字后指示的名称的符号引用。此外，该规范必须包含该模块是普通（normal）还是开放（open）的（§7.7）。
- 由 `requires` 指令表示的每个依赖的规范，作为对该指令指示的模块名称的符号引用（§7.7.1）。此外，该规范必须包含该依赖是否是传递的（transitive）。
- 由 `exports` 或 `opens` 指令表示的每个包的规范，作为对指令指示的包名称的符号引用（§7.7.2）。此外，如果指令是限定的（qualified），则该规范必须提供对指令子句指示的模块名称的符号引用。
- 由 `uses` 指令表示的每个服务的规范，作为对指令指示的类型名称的符号引用（§7.7.3）。
- 由 `provides` 指令表示的服务提供者的规范，作为对指令 `with` 子句指示的类型名称的符号引用（§7.7.4）。此外，规范必须提供对指令指示的服务类型名称的符号引用。

接下来的章节讨论了对类和接口类型声明可能进行的更改，这些更改不会破坏与现有二进制文件的兼容性。在上述翻译要求下，Java 虚拟机及其类格式支持这些更改。任何其他有效的二进制格式（例如在上述要求下由类加载器映射回类文件的压缩或加密表示）也必须支持这些更改。

## 13.2 什么是二进制兼容，以及什么不是

对类型的更改与现有二进制文件是二进制兼容的（等同于二进制兼容）。

二进制文件被编译为依赖其他类和接口的可访问成员和构造函数。为了保持二进制兼容性，类或接口应将其可访问成员和构造函数及其存在和行为视为与其用户之间的契约。

Java 编程语言的设计是为了防止契约的添加以及意外的名称冲突破坏二进制兼容性。具体而言，增加更多重载特定方法名的方法不会破坏与现有二进制文件的二进制兼容性。现有二进制文件将用于方法查找的方法签名是在编译时由重载解析算法选择的（§13.5.12）。

> 如果 Java 编程语言的设计是使得执行的特定方法在运行时确定的，那么这种歧义可能会在运行时被检测到。这种规则意味着，添加额外的重载方法以导致调用处产生歧义，可能会破坏与无限数量现有二进制文件的兼容性。更多讨论请参见 §13.4.23。

二进制兼容性不等同于源码兼容性。特别是，§13.4.6 中的示例表明，从一组无法共同编译的源码中可以产生一组兼容的二进制文件。这种示例是典型的：添加了一个新声明，更改了源代码中未更改部分的某个名称的含义，而该未更改部分的现有二进制文件保留了该名称完全限定的先前含义。产生一致的源码集需要提供与之前的含义相对应的限定名称或字段访问表达式。

## 13.3 包和模块的演进

向包中添加顶层类或接口类型可能不会破坏与现有二进制文件的兼容性，前提是新类型没有重用之前分配给某个不相关类型的名称。如果新类型重用了之前分配给不相关类型的名称，则可能会导致冲突，因为这两种类型的二进制文件无法被同一个类加载器加载。

顶层类和接口类型的更改，如果它们不是公共的，且分别不是某个公共类型的超类或超接口，则仅影响其声明所在包内的类型。即使此处描述了其他不兼容的情况，只要该包受影响的二进制文件一起更新，这些类型就可以被删除或进行更改。

如果一个模块被声明导出或者一个包被更改为不导出该包，或者为一组不同的朋友导出或开放该包，当链接一个需要但不再具有访问该包的公共和保护类型的现有二进制文件时，将抛出 `IllegalAccessError`。对于已广泛分发的模块，不需要进行更改。

如果一个模块没有被声明导出或开放给包，那么将模块更改为导出或开放该包不会破坏与现有二进制文件的兼容性。然而，更改包可能会阻止程序启动，因为读取该模块的任何模块也可能读取导出同名包的其他模块。

向模块声明中添加 `requires` 指令，或向 `requires` 指令添加 `transitive` 修饰，不会破坏与现有二进制文件的兼容性。然而，可能会阻止程序启动，因为该模块现在可能读取多个导出同名包的模块。

在模块声明中删除 `requires` 指令，或从 `requires` 指令中删除 `transitive` 修饰，可能会破坏任何依赖该指令或修饰在引用该模块导出的类型时读取该模块可见性的现有二进制文件。当链接来自现有二进制文件的此类引用时，可能会抛出 `IllegalAccessError`。

在模块声明中添加或删除 `uses` 或 `provides` 指令不会破坏与现有二进制文件的兼容性。

## 13.4 类的演进

本节描述了类及其成员、构造函数声明的更改对现有二进制文件的影响。

### 13.4.1 抽象类

如果一个未声明为抽象的类被更改为声明为抽象，那么尝试创建该类新实例的现有二进制文件将在链接时抛出 `InstantiationError`，或者（如果使用了反射方法）在运行时抛出 `InstantiationException`；因此，不建议对广泛分发的类进行此类更改。

将一个声明为抽象的类更改为不再声明为抽象不会破坏与现有二进制文件的兼容性。

### 13.4.2 final 类

如果一个未声明为 final 的类被更改为 `final`，那么当加载该类的现有子类的二进制文件时，将抛出 `VerifyError`，因为 final 类可以有子类；不建议对广泛分发的类进行此类更改。

将一个声明为 `final` 的类更改为不再为 `final` 不会破坏与现有二进制文件的兼容性。

### 13.4.3 公共类

将一个未声明为公共的类更改为声明为公共不会破坏与现有二进制文件的兼容性。

将一个声明为公共的类更改为不声明为公共，那么当链接一个不再具有访问该类类型权限的现有二进制文件时，将抛出 `IllegalAccessError`；不建议对广泛分发的类进行此类更改。

### 13.4.4 超类和超接口

如果一个类将成为自身的超类，则在加载时抛出 `ClassCircularError`。当新编译的二进制文件与现有二进制文件加载时可能导致此类循环的类层次结构不建议在广泛分发的类中实现。

更改类类型的直接超类或直接接口集不会破坏与现有二进制文件的兼容性，前提是该类的超类或超接口总集没有丢失任何成员。

如果对直接超类或直接接口集的更改导致任何类或接口不再是超类或超接口，那么当加载修改后的类的二进制文件时，可能会导致链接错误。此类更改不建议在广泛分发的类中使用。

## 例 13.4.4-1 更改父类

假设有一个测试程序：

```
```



# 二进制兼容性

## 类的演化 13.4

```java
class Hyper { char h = 'h'; }

class Super extends Hyper { char s = 's'; }

class Test extends Super {

    public static void printH(Hyper h) {
        System.out.println(h.h);
    }

    public static void main(String[] args) {
        printH(new Super());
    }
}
```

被编译并执行后，产生输出：

```
s
```

假设随后编译了 `Super` 类的新版本：

```java
class Super { char s = 's'; }
```

此版本的 `Super` 类不再是 `Hyper` 类的子类。如果我们此时使用新版本的 `Super` 运行现有的 `Hyper` 和 `Test` 二进制文件，则会在链接时抛出 `VerifyError`。验证器认为 `new Super()` 的结果不能作为参数来替换 `Hyper` 类型的形式参数，因为 `Super` 不是 `Hyper` 的子类。

考虑如果没有验证步骤可能会发生什么，将是很有启发意义的：程序可能会运行并打印：

```
s
```

这表明，如果没有验证器，Java 类型系统可能会因链接不一致的二进制文件而被击败，尽管每个文件都是由正确的 Java 编译器产生的。

教训是，缺乏验证器或未能使用验证器的实现将无法维护类型安全，因此它不是一个有效的实现。

多捕获子句 (§14.20) 中的替代方案不是彼此的子类或父类，这一要求仅是源码限制。假设以下客户端代码是合法的：

```java
try {
    throwAorB();
} catch(ExceptionA | ExceptionB e) {
    ...
}
```

其中在客户端编译时，`ExceptionA` 和 `ExceptionB` 没有子类/父类关系，那么当客户端执行时，`ExceptionA` 和 `ExceptionB` 具有这种关系对于客户端来说是二进制兼容的。

这比于其他情况，在其他情况下，对客户端具有二进制兼容性的类转换对于该客户端来说可能不是源码兼容的。

## 13.4.5 类类型参数

添加或删除类的类型参数本身对二进制兼容性没有任何影响。

如果此类类型参数被用在字段或方法的类型中，可能会产生更改上述类型所带来的正常影响。

重命名类的类型参数对预有的二进制文件没有影响。

更改类类型参数的第一个边界可能会更改任何在其自身类型中使用该参数的成员的擦除 (§4.6)，这可能会影响二进制兼容性。此类边界的更改类似于方法或构造函数类型参数第一个边界的更改 (§13.4.13)。

更改任何其他边界对二进制兼容性没有影响。

## 13.4.6 类体成员声明

添加一个实例（对应 `static`）成员，如果该成员与父类或子类的实例（对应 `static`）成员具有相同的名称和访问权限（对于字段），或相同的名称、访问权限、签名和返回类型（对于方法），不会导致与预有的二进制文件产生不兼容。即使正在链接的类集合会遇到编译错误，也不会发生错误。

删除一个未声明为 `private` 的类成员或构造函数，如果该成员或构造函数被预有的二进制文件使用，可能会导致链接错误。

### 13.4.6-1 更改类体

```java
class Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}

class Super extends Hyper {
    void hello() { System.out.println("hello from Super"); }
}

class Test {
    public static void main(String[] args) {
        new Super().hello();
    }
}
```

此程序产生输出：

```
hello from Super
```

假设生成了 `Super` 类的新版本：

```java
class Super extends Hyper {}
```

那么，重新编译 `Super` 并使用原始 `Test` 和 `Hyper` 二进制文件执行此新二进制文件，将产生输出：

```
hello from Hyper
```

正如预期。

`super` 关键字可以用于访问在父类中声明的方法，绕过当前类中声明的任何方法。表达式 `super.Identifier` 在编译时解析为父类 `S` 中的方法 `m`。如果方法 `m` 是实例方法，则在运行时调用的方法是与 `m` 签名相同的方法，且该方法是包含 `super` 表达式的类的直接父类的成员。

### 13.4.6-2 更改父类

```java
class Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}

class Super extends Hyper {
}

class Test extends Super {
    public static void main(String[] args) {
        new Test().hello();
    }

    void hello() {
        super.hello();
    }
}
```

此程序产生输出：

```
hello from Hyper
```

假设生成了 `Super` 类的新版本：

```java
class Super extends Hyper {
    void hello() { System.out.println("hello from Super"); }
}
```

那么，如果重新编译了 `Super` 和 `Hyper` 但没有编译 `Test`，则使用现有 `Test` 二进制文件运行新二进制文件将产生输出：

```
hello from Super
```

正如你预期的那样。

## 13.4.7 成员和构造函数的访问

更改成员或构造函数的声明访问以允许更少的访问可能会破坏与预有二进制文件的兼容性，在解析这些二进制文件时导致链接错误。如果将访问修饰符从包访问更改为私有；从保护更改为包；从 `public` 更改为保护，则允许更少的访问。因此，不建议将广泛分发的类的成员或构造函数更改为更具访问性。

可能令人惊讶的是，二进制格式定义使得将成员更改为较低访问权限不会导致链接错误。

### 例 13.4.7-1 更改访问权限

如果包定义了类：

```java
package points;

public class Point {
    int x, y;

    protected void print() {
        System.out.println("*" + x + "," + y + "*");
    }
}
```

被程序使用：

```java
class Test extends points.Point {
    public static void main(String[] args) {
        Test t = new Test();
        t.print();
    }

    protected void print() {
        System.out.println("*Test*");
    }
}
```

那么这些类通过编译且 `Test` 执行产生输出：

```
*Test*
```

如果将方法 `print` 更改为 `public`，然后仅重新编译 `Point` 类，并与之前的 `Test` 二进制文件执行，不会发生链接错误。即使在编译时由保护方法重写 `public` 方法是不恰当的（正如 `Test` 类除非更改为 `public` 则无法重新编译所示），这种情况也会发生。

允许父类将保护方法更改为 `public` 而不破坏二进制文件，有助于二进制文件的稳定性。替代方案（即此类更改会导致链接错误）将产生二进制不兼容性。

## 13.4.8 字段声明

广泛分发的程序不应向客户端暴露任何字段。除了下文的二进制兼容性问题外，这通常是良好的工程实践。向类添加字段可能会破坏与未重新编译的现有二进制文件的兼容性。

假设引用类型为 `τ` 的字段 `f`。进一步假设 `f` 是在 `τ` 的父类 `s` 中的实例（对应静态）字段，且 `f` 的类型为 `x`。

如果在 `s` 的父类（或 `τ` 本身）中添加与 `f` 名称相同且类型为 `x` 的新字段，可能会发生链接错误。只有在满足上述的基础上满足以下之一时，才会发生此类链接错误：

- 新字段的访问权限比旧字段低。
- 新字段是静态（对应实例）字段。

特别，当引用的类由于字段访问之前引用了类型的父类字段而无法重新编译时，不会发生链接错误。具有此类引用的先前编译类将继续引用在父类中声明的字段。

### 例 13.4.8-1 添加字段声明

```java
class Hyper { String h = "hyper"; }

class Super extends Hyper { String s = "super"; }

class Test {
    public static void main(String[] args) {
        System.out.println(new Super().h);
    }
}
```

此程序产生输出：

```
hyper
```

假设产生了一个新版本的类 `Super`：

```java
class Super extends Hyper {
    String s = "super";
    int h = 0;
}
```

那么，重新编译 `Hyper` 和 `Super`，并使用 `Test` 的旧二进制文件执行生成的二进制文件，将产生输出：

```
hyper
```

`Hyper` 的 `h` 是由 `Test` 的原始二进制文件输出的。虽然起初看起来可能很意外，但它的目的是减少运行时发生的不兼容情况。在理想世界中，每当任何源文件发生变化时，所有需要重新编译的文件都应该重新编译，从而消除此类意外。但这种大规模的重新编译通常是不现实或可能的，特别是在互联网环境中。而且正如之前提到的，重新编译有时需要对源代码进行进一步更改。

另一个例子，如果程序：

```java
class Hyper { String h = "Hyper"; }

class Super extends Hyper {
}

class Test extends Super {
    public static void main(String[] args) {
        String s = new Test().h;
        System.out.println(s);
    }
}
```

被编译并执行，它将产生输出：

```
Hyper
```

假设随后编译了一个新版本的类 `Super`：

```java
class Super extends Hyper { char h = 'h'; }
```

如果将生成的二进制文件与现有的 `Hyper` 和 `Test` 二进制文件一起使用，输出仍然是：

```
Hyper
```

即使编译这些二进制文件的源代码：

```java
class Hyper { String h = "Hyper"; }
class Super extends Hyper { char h = 'h'; }
class Test extends Super {
    public static void main(String[] args) {
        String s = new Test().h;
        System.out.println(s);
    }
}
```

会导致编译错误，因为 `main` 方法源代码中的 `h` 现在会被解释为指向引用在 `Super` 中声明的 `char` 字段，而 `char` 类型的值不能赋值给 `String` 类型。

从类中删除一个字段将破坏与任何引用该字段的预存二进制文件的兼容性，并且当这种来自预存二进制文件的引用被链接时，将抛出 `NoSuchFieldError`。只有私有字段可以从在广泛分发的集群中安全地删除。

出于二进制兼容性的考虑，添加或删除一个类型涉及类型变量（§4.4）或参数化类型（§4.5）的字段 `f`，等同于添加（或删除）一个同名字段，其类型为类型 `f` 的擦除（§4.6）。

## 13.4.9 final 字段和静态常量变量

如果一个未声明为 `final` 的字段被更改为声明为 `final`，可能会破坏尝试为该字段分配新值的预存二进制文件的兼容性。

> **13.4.9-1. 将变量改为 final**

```java
class Super { char s; }

class Test extends Super {
    public static void main(String[] args) {
        Super x = new Super();
        x.s = 'a';
        System.out.println(x.s);
    }
}
```

该程序产生输出：

```
a
```

假设产生了一个新版本的类 `Super`：

```java
class Super { final char s = 'b'; }
```

如果在不编译 `Test` 的情况下重新编译 `Super`，那么使用现有的 `Test` 二进制文件运行新的二进制文件将导致 `IllegalAccessError`。

删除 `final` 关键字或更改字段初始化值不会破坏与现有二进制文件的兼容性。

如果一个字段是常量变量（§4.12.4），而且它是 `static` 的，那么删除 `final` 关键字或更改其值不会导致预存二进制文件无法运行而破坏兼容性，但除非重新编译，否则它们将看不到该字段使用的任何新值。这一结果是支持条件编译（§14.22）决定的副作用。（人们可能会反对：如果使用发生在常量表达式（§15.29）中则看不到新值，而在其他地方则可见。事实并非如此；预存二进制文件根本就看不到新值。）

在广泛分发的代码中避免“非常量常量”问题的最佳方法是使用静态变量处理不太可能改变的值。除了真正的数学常数外，我们建议在源代码中稀疏地使用静态变量。

如果需要 `final` 的只读性质，更好的选择是声明一个私有静态变量和一个合适的静态方法来获取其值：

```java
private static int N;
public static int getN() { return N; }
```

而不是：

```java
public static final int N = ...;
```

如果 `N` 需要是只读的，使用以下代码没有问题：

```java
public static int N = ...;
```



## 13.4.10 static 字段

如果一个未声明为 `private static` 的字段被更改为声明为 `static`，或反之，如果该字段被一个期望另一种字段的预存二进制文件使用，则会导致链接错误，特别是 `IncompatibleClassChangeError`。不建议在广泛分发的代码中进行此类更改。

## 13.4.11 transient 字段

添加或删除字段的 `transient` 修饰符不会破坏与预存二进制文件的兼容性。

## 13.4.12 方法和构造函数声明

向类添加方法或构造函数声明不会破坏与任何预存二进制文件的兼容性，即使由于之前的调用引用了类型不兼容的父类方法或构造函数，导致该类型无法重新编译。具有此类引用的之前编译的类将继续引用父类中声明的方法或构造函数。

假设有一个具有限定类型 $T$ 的方法引用 $m$。进一步假设 $m$ 实际上是在 $T, S$ 的父类中声明的实例（或为 `static`）方法。

如果在子类中添加一个类型为 $x$ 且签名和返回类型与 $m$ 相同的新方法，且该子类是 $T$ 的父类，则可能会链接错误。只有在满足以下任一条件时才会发生链接错误：
- 新方法的访问权限比旧方法低。
- 新方法是 `static`（或实例）方法。

从类中删除方法或构造函数将破坏任何引用该方法或构造函数的预存二进制文件的兼容性；当链接预存二进制文件时将抛出 `NoSuchMethodError`。只有在没有匹配签名和返回类型的方法时才会发生此类错误。

如果类的源代码不包含构造函数，则隐式声明默认构造函数。添加一个多个构造函数将阻止默认构造函数的。

## 13.4.13 方法和构造函数的类型参数

添加或删除方法或构造函数的类型参数本身对二进制兼容性没有产生影响。

如果此类类型参数用于方法或构造函数的类型中，则具有正常影响。

重命名方法或构造函数的类型参数对预存二进制文件没有影响。

更改方法或构造函数的第一个边界可能会更改使用类型参数的成员的擦除（§4.6），这可能会影响二进制兼容性。具体而言：
- 如果类型参数用于字段的类型，其效果相当于删除了该字段并添加了一个同名且类型为类型参数擦除的字段。
- 如果类型参数用于方法的任何形式参数的类型，但不是方法的返回类型，其效果相当于该方法被删除，并替换为一个新方法，其中上述形式参数的类型现在变为类型参数的擦除。
- 如果类型参数用于方法的返回类型，但不是方法的任何形式参数的类型，其效果相当于该方法被删除，并替换为一个新方法，其返回类型现在变为类型参数的擦除。
- 如果类型参数既用于方法的返回类型，又用于该方法一个或多个形式参数的类型，其效果相当于该方法被删除，并替换为一个新方法，其返回类型现在变为类型参数的擦除，且上述形式参数的类型现在变为类型参数的擦除。

更改任何其他边界对二进制兼容性没有影响。

## 13.4.14 方法和构造函数的形式参数

更改方法或构造函数形式参数的名称不会影响预存二进制文件。

更改方法名称，或更改构造函数的形式参数类型，会创建一个具有新签名的方法或构造函数，并产生删除旧签名的方法或构造函数以及添加具有新签名的方法或构造函数的组合效果。

将方法最后一个形式参数的类型从 `T[]` 更改为类型 `T` 的可变长度参数（§8.4.1）（即变为 `T...`），反之亦然，不会影响预存二进制文件。

为了二进制兼容性，添加或删除一个签名涉及类型变量（§4.4）或泛型类型（§4.5）的方法或构造函数 $m$，其结果等同于添加（相应地删除）一个另一个等价的方法，该方法的签名是 $m$ 签名的擦除（§4.6）后的签名。

## 13.4.15 方法结果类型

更改方法的返回结果类型、将结果类型替换为 `void` 或将 `void` 替换为结果类型，其效果等同于删除旧方法并添加一个具有新结果类型或新 `void` 结果的新方法（见 §13.4.12）。

为了二进制兼容性，添加或删除一个类型涉及类型变量（§4.4）或泛型类型（§4.5）的方法或构造函数 $m$，等同于添加（相应地删除）一个另一个等价的方法，该方法的返回类型是 $m$ 返回类型的擦除（§4.6）后的类型。

## 13.4.16 抽象方法

将一个声明为 `abstract` 的方法改为不再声明为 `abstract` 不会破坏与现有二进制文件的兼容性。

将一个未声明为 `abstract` 的方法改为声明为 `abstract` 将破坏之前调用过该方法的现有二进制文件的兼容性，并导致 `AbstractMethodError`。

示例 13.4.16-1. 将方法更改为 abstract

```java
class Super { void out() { System.out.println("Out"); } }

class Test extends Super {

    public static void main(String[] args) {

        Test t = new Test();

        System.out.println("Way ");

        t.out();

    }

}
```

该程序产生以下输出：

Way
Out

假设产生了类 `Super` 的新版本：

```java
abstract class Super {

    abstract void out();

}
```

如果重新编译了 *Super* 但没有重新编译 *Test*，那么使用现有的 *Test* 二进制文件运行新的二进制文件将导致 `AbstractMethodError`，因为类 *Test* 没有方法 `out` 的实现，因此（或应该）是 *abstract* 的。

## 13.4.17 final 方法

将一个声明为 `final` 的方法改为不再声明为 `final` 不会破坏与现有二进制文件的兼容性。

将一个未声明为 `final` 的实例方法改为声明为 `final` 可能会破坏依赖于重写方法的现有二进制文件的兼容性。

示例 13.4.17-1. 将方法更改为 final

```java
class Super { void out() { System.out.println("out"); }}

class Test extends Super {

    public static void main(String[] args) {

        Test t = new Test();

        t.out();

    }

    void out() { super.out(); }

}
```

该程序产生以下输出：

out

假设产生了类 *Super* 的新版本：

```java
class Super { final void out() { System.out.println("!"); } }
```

如果重新编译了 *Super* 但没有重新编译 *Test*，那么使用现有的 *Test* 二进制文件运行新的二进制文件将导致 `VerifyError`，因为类 *Test* 不当地尝试重写实例方法 `out`。

将一个未声明为 `final` 的（静态）方法改为声明为 `final` 不会破坏现有二进制文件的兼容性，因为该方法无法被重写。

## 13.4.18 native 方法

添加或删除方法的 `native` 修饰符不会破坏与现有二进制文件的兼容性。

类型更改对未重新编译的现有 native 方法的影响超出了本规范的范围，应在实现部分的描述中提供。鼓励（但不是要求）实现者通过限制此类影响的方式来实现 native 方法。

## 13.4.19 静态方法

如果一个未声明为 `private` 的方法也被声明为 `static`（即类方法）并被更改为非静态（即实例方法），或者反之被更改声明为静态，这可能会破坏与现有二进制文件的兼容性。

## 13.4.20 synchronized 方法

添加或删除方法的 `synchronized` 修饰符不会破坏与现有二进制文件的兼容性。

## 13.4.21 方法和构造函数的 throws

更改方法或构造函数的 `throws` 子句不会破坏与现有二进制文件的兼容性。

## 13.4.22 方法和构造函数的体

更改方法或构造函数的体不会破坏与现有二进制文件的兼容性。

`final` 关键字并不意味着该方法可以被内联；它意味着该方法不能被重写。

为了二进制兼容性，我们建议在运行时对方法进行内联和优化。

## 13.4.23 方法和构造函数的重载

添加重载现有方法或构造器的新方法不会破坏与现有二进制文件的兼容性。

添加新的重载方法或构造函数可能会导致编译时错误，如果这些签名在编译时是更具体的。

示例 13.4.23-1. 添加重载方法

```java
class Super {

    static void out(float f) {

        System.out.println("float");

    }

}

class Test {

    public static void main(String[] args) {

        Super.out(2);

    }

}
```

该程序产生以下输出：

float

假设产生了类 `Super` 的新版本：

```java
class Super {

    static void out(float f) { System.out.println("float"); }

    static void out(int i) { System.out.println("int"); }

}
```

如果重新编译了 *Super* 但没有重新编译 *Test*，那么使用现有的 *Test* 二进制文件运行仍然产生输出：

float

然而，如果重新编译了 *Test* 并使用这个新的 *Super*，输出将是：

int

正如之前的情况下可能直观预期的那样。

## 13.4.24 方法重写

如果在子类中添加一个实例方法并重写了父类中的方法，现有二进制文件的调用将找到子类方法，这些二进制文件不受影响。

如果在类中添加一个类方法，除非引用的类型是子类类型，否则该方法将无法找到。

## 13.4.25 静态初始化

添加、删除或更改类的静态初始化（§8.7）不会影响现有二进制文件。

## 13.4.26 枚举的演进

在枚举中添加或重新排序常量不会破坏现有二进制文件的兼容性。

如果现有二进制文件尝试访问已不存在的枚举常量，客户端将在运行时失败并抛出 `NoSuchFieldError`。因此，对于广泛发布的枚举，不建议进行此类更改。

在所有其他方面，枚举的二进制兼容性规则与类相同。

## 13.5 接口的演进

本节描述了接口及其成员定义的更改对现有二进制文件的影响。

## 13.5.1 接口

将一个未声明的接口更改为声明 `public` 不会破坏现有二进制文件的兼容性。

如果将一个声明为 `public` 的接口更改为非 `public`，那么当链接需要但不再访问该接口类型的现有二进制文件时，将抛出 `IllegalAccessError`，因此对于广泛发布的接口，不建议进行此类更改。

## 13.5.2 超接口（Superinterfaces）

接口层级的变化导致错误的方式与类层级的变化相同，如 §13.4.4 所示。特别是，当更改导致类的任何先前的超接口不再是超接口时，会破坏与预存二进制文件的兼容性，导致 `VerifyError`。

## 13.5.3 接口成员

向接口中添加 `abstract`、`private` 或 `static` 方法不会破坏与预存二进制文件的兼容性。

向 `c` 的超接口中添加字段，可能会继承自 `c` 的某个父类的字段。如果原始引用指向实例字段，将导致 `IncompatibleClassChangeError`。如果原始引用是一个赋值操作，将导致 `IllegalAccessError`。

从接口中删除成员可能会导致预存二进制文件出现链接接错误。

### 13.5.3-1. 删除接口成员

```java
interface I { void hello(); }

class Test implements I {

    public static void main(String[] args) {

        I anI = new Test();

        anI.hello();

    }

    public void hello() { System.out.println("hello"); }

}
```

该程序产生输出：

hello

假设编译了接口 `I` 的新版本：

如果重新编译了 `I` 但没有编译 `Test`，则使用现有的 `Test` 二进制文件运行新的二进制文件将导致 `NoSuchMethodError`。

## 13.5.4 接口类型参数

接口类型参数的变化与对类类型参数进行类似更改的影响相同。

## 13.5.5 字段声明

更改接口中字段声明的考虑因素与类中 `static final` 字段的考虑因素相同，如 §13.4.8 和 §13.4.9 所示。

## 13.5.6 接口方法声明

更改接口方法声明的考虑因素包括更改类中方法的考虑因素，如 §13.4.7、§13.4.14、§13.4.15、§13.4.21、§13.4.22 和 §13.4.23 所示。

添加默认方法或将方法从抽象更改为默认不会破坏与预存二进制文件的兼容性，但如果预存二进制文件尝试调用该方法，可能会导致 `IncompatibleClassChangeError`。如果限定类型 `T` 是两个接口 `i` 和 `j` 的子类型，且 `i` 和 `j` 都声明了具有相同签名和结果的默认方法，且 `i` 和 `j` 都不是对方的子接口，就会发生此错误。

换句话说，添加默认方法是二进制兼容的更改，因为它不会在编译时或调用时引入错误。在实践中，意外冲突的风险发生在向非 `final` 类中添加默认方法时。在发生冲突的情况下，向类中添加方法不太可能触发 `LinkageError`，但子类中对方法的意外重写可能会导致不可预测的方法行为。两种更改都可能导致编译时错误。

### 13.5.6-1. 添加默认方法

```java
interface Painter {

    default void draw() {

        System.out.println("Here's a picture...");

    }

}

interface Cowboy {}

public class CowboyArtist implements Cowboy, Painter {

    public static void main(String... args) {

        new CowboyArtist().draw();

    }

}
```

该程序产生输出：

Here's a picture...

假设向 `Cowboy` 中添加了默认方法：

```java
interface Cowboy {

    default void draw() {

        System.out.println("Bang!");

    }

}
```

如果重新编译了 `Cowboy` 而没有编译 `CowboyArtist`，则使用现有的 `CowboyArtist` 二进制文件运行新的二进制文件将通过链接，但在 `main` 尝试调用 `draw()` 时会导致 `IncompatibleClassChangeError`。

## 13.5.7 注解类型的演变

注解类型的行为与其他任何接口完全相同。在注解类型中添加或删除元素类似于添加或删除方法。对于注解类型的其他更改还有重要的考虑因素，例如使注解类型可重复 (§9.6.3)，但这些对 Java 虚拟机二进制文件的链接没有影响。相反，此类更改会影响操作注解的反射 API 的行为。这些 API 的文档说明……

## 14.1 语句的正常完成和异常完成

“正常完成”和“异常完成”术语也适用于表达式的求值 (§15.6)。表达式能够异常完成的唯一原因是抛出了异常，或者抛出了给定值的 throw，或者运行时异常或错误 (§11 (Exceptions), §15.6)。

如果语句求值一个表达式，表达式的异常完成始终会导致语句的立即异常完成，原因相同。执行模式模式的后续步骤将不执行。

除非本章另有说明，子语句的异常完成会导致语句本身的立即异常完成，原因相同，且执行模式模式的后续步骤将不执行。

除非另有说明，如果语句求值的所有表达式和子语句都正常完成，则语句正常完成。

## 14.2 块

块是括号内的语句、局部类声明和局部变量声明语句的序列。

```
Block:
 { [BlockStatements] }
```

```
BlockStatements:
 BlockStatement [BlockStatement]
```

```
BlockStatement:
 LocalVariableDeclarationStatement
 ClassDeclaration
 Statement
```

块的执行方式是从左到右顺序执行每个局部变量声明语句和其他语句。如果所有这些块语句都正常完成，则块正常完成。如果这些块语句中的因任何原因异常完成，则块按该原因异常完成。

如果局部类声明包含 `public`、`protected` 或 `private` 任何访问修饰符（§6.6），或 `static` 修饰符（§8.1.1），则将导致编译时错误。

局部类声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

## 示例 14.3-1. 局部类声明

以下示例说明了上述规则的几个方面：

```java
class Global {

    class Cyclic {}

    void foo() {

        new Cyclic(); // 创建一个 Global.Cyclic

        class Cyclic extends Cyclic {} // 循环定义

        {

            class Local {}{

                class Local {} // 编译错误
```



## 局部类声明示例

```java
class Global {
    static class Cyclic {}

    void foo() {
        class Cyclic extends Cyclic {} // 编译错误

        class Local {} // 编译错误

        class AnotherLocal {
            void bar() {
                class Local {} // OK
            }
        }

        class Local {} // OK，不在前一个 Local 的作用域内
    }
}
```

`foo` 的第一个方法创建了成员类 `Global.Cyclic` 的实例，而不是局部类 `Cyclic` 的实例，因为该语句出现在局部类声明的作用域之前。

局部类声明的作用域包含其声明（而不只是其体）这一事实意味着局部类 `Cyclic` 的定义确实是循环的，因为它继承了自身而不是 `Global.Cyclic`。因此，局部类 `Cyclic` 的声明在编译时被拒绝。

由于局部名称不能在同一个方法（构造函数或初始化器，取决于情况）中重新声明，因此 `Local` 的第二次和第三次声明会导致编译错误。然而，可以在另一个更深嵌套的类（如 `AnotherLocal`）范围内重新声明 `Local`。

`Local` 的最后一个声明是合法的，因为它发生在任何先前的 `Local` 声明的作用域之外。

## 14.4 局部变量声明语句

局部变量声明语句声明一个或多个局部变量名。

```text
LocalVariableDeclarationStatement:
    LocalVariableDeclaration;

LocalVariableDeclaration:
    {VariableModifier} LocalVariableType VariableDeclarList

LocalVariableType:
    UnannType
    var
```

关于 `UnannType` 参见 §8.3。为了方便起见，展示了 §4.3、§8.3 和 §8.4.1 中的以下产生式：

```text
VariableModifier:
    Annotation
    final

VariableDeclarList:
    VariableDeclaration (, VariableDeclaration)

VariableDeclaration:
    VariableDeclarationId [= VariableInitializer]

VariableDeclarationId:
    Identifier [Dims]

Dims:
    [Annotation] { } {[Annotation]} []

VariableInitializer:
    Expression
    ArrayInitializer
```

每个局部变量声明语句都立即包含在一个块（block）中。局部变量声明语句可以与块中的其他语句自由混合。

除了局部变量声明语句，局部变量可以通过基础 `for` 语句（§14.14.1）、增强 `for` 语句（§14.14.2）或 `try-with-resources` 语句（§14.20.3）的头部声明。

局部变量声明上的注解修饰符规则规定在 §9.7.4 和 §9.7.5。

如果 `final` 作为局部变量声明的修饰符出现多次，则将导致编译错误。

如果 `LocalVariableType` 为 `var` 且满足以下任一条件，则将导致编译错误：

- 列出了多一个 `VariableDeclarator`（变量声明符）。
- `VariableDeclaratorId` 具有一个或多个括号对。
- `VariableDeclarator` 缺少初始化器。
- `VariableDeclarator` 的初始化器是一个 `ArrayInitializer`（数组初始化器）。
- `VariableDeclarator` 的初始化器包含对变量的引用。

### 示例 14.4-1. 使用 `var` 声明的局部变量

```java
var a = 1;                      // 合法

var b = 2, c = 3.0;         // 非法：多个声明符

var d[] = new int[4];       // 非法：额外的括号对

var e;                       // 非法：无初始化器

var f = { 6 };               // 非法：数组初始化器

var g = (7);                 // 非法：初始化器自引用
```

这些限制有助于避免对 `var` 所表示的类型产生困惑。

## 14.4.1 局部变量声明符和类型

局部变量声明中的每个声明符都声明一个局部变量，其名称是声明符中出现的 `Identifier`（标识符）。

如果可选关键字 `final` 出现在声明开头，则被声明的变量是 `final`（§14.12.4）。

局部变量的声明类型确定如下：

- 如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中没有出现括号对，则表示该局部变量的类型。
- 如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号对，则局部变量的类型由 §10.2 规定。
- 如果 `LocalVariableType` 为 `var`，则令 $\tau$ 为初始化器表达式在被处理为未出现在赋值上下文中、因此是一个独立表达式时的类型（§15.2）。局部变量的类型是 $\tau$ 相对于 $\tau$ 提到的所有合成类型变量的向上投影（§4.10.5）。

如果 $\tau$ 是空类型（null type），则将导致编译错误。

初始化器被处理为未出现在赋值上下文中，如果它是 lambda 表达式（§15.27）或方法引用表达式（§15.13），则发生错误。

### 示例 14.4.1-1. 使用 `var` 声明的局部变量类型

以下代码说明了使用 `var` 声明的变量的类型划分：

```java
var a = 1; // a 类型为 int

var b = java.util.List.of(1, 2); // b 类型为 List<Integer>

var c = "x"; // c 类型为 CharSequence

var d = new Object(); // d 类型为 Object

var e = (CharSequence & String>); // e 类型为 CharSequence & String

var f = () -> "hello"; // 非法：lambda 不在上下文

var g = null; // 非法：空类型
```

注意，使用 `var` 的变量不能具有显式类型。

向上投影应用于初始化器以确定变量的类型。如果初始化器包含捕获变量，这会将初始化器映射到不包含捕获变量的类型。虽然可以允许变量类型包含捕获变量，但通过投影，我们强制捕获变量的作用域永远小于包含它的语句。捕获变量不会“泄漏”到后续语句。

类型为 `float` 的局部变量总是 float 值集合中的元素（§4.2.3）；同样类型为 `double` 的局部变量总是 double 值集合中的元素。局部类声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

## 14.4.2 局部变量声明的执行

局部变量声明语句是可执行语句。每次执行它时，声明符都从左到右处理。如果声明符有初始化器，则求值初始化器并将其赋值给变量。

- 如果声明符没有初始化器，则对变量的任何引用必须先对变量赋值，否则将根据确定赋值（Definite Assignment）规则发生错误。

每个初始化器（第一个之外）只有在前一个初始化器正常完成后后才会被求值。

局部变量声明的执行只有在最后一个初始化器正常完成后才会正常完成。

如果局部变量声明不包含初始化器，则执行它总是正常完成。

## 14.5 语句

Java 编程语言有很多语句。大多数语句对应 C 和 C++ 语言中的语句，但有些是独特的。

与 C 和 C++ 一样，Java 编程语言的 `if` 语句存在所谓的悬空 `else` 问题，如下所示性的格式示例所示：

```java
if (door.isVisible())
    if (resident.isVisible())
        resident.greet("Hello!");
else door.bell.ring(); // 悬空 else
```

问题是外部和内部 `if` 语句都可能拥有该 `else` 子句。在这种情况下，人们可能会推断程序员希望 `else` 子句属于外部语句。

Java 编程语言像 C、C++ 以及之前的许多编程语言一样，任意规定 `else` 子句属于它可能属于的最内层 `if`。这一规则由以下文法捕获：

### 块与语句

语句：
- 不带末尾子语句的语句
- 标记语句
- `if-then` 语句
- `if-then-else` 语句
- `while` 语句
- `for` 语句

非短 `if` 语句：
- 不带末尾子语句的语句
- 不带短 `if` 的标记语句
- 非短 `if` 的 `if-then-else` 语句
- `while` 语句
- `for` 语句

不带末尾子语句的语句：
- 块
- 空语句
- 表达式语句
- 断言语句
- `switch` 语句
- `do` 语句
- `break` 语句
- `continue` 语句
- `return` 语句
- 同步语句
- `throw` 语句
- `try` 语句
- `yield` 语句

为了方便起见，此处显示了 §14.9 中的以下产生式：

```text
IfThenStatement:
    if ( Expression ) Statement

IfThenElseStatement:
    if ( Expression ) StatementNoShortIf else Statement

IfThenElseStatementNoShortIf:
    if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

语句在语法上分为两类：可能以没有 `else` 分句的 `if` 语句（“短 `if` 语句”）结尾的语句，以及明确不会这样结尾的语句。

只有那些明确不会以短 `if` 语句结尾的语句，才可以在带有 `else` 分句的 `if` 语句中作为 `else` 关键字之前的直接子语句。

这条简单的规则防止了“悬空 `else`”问题。带有“非短 `if`”限制的语句的执行行为与没有“非短 `if`”限制的同类语句的执行行为相同；这种区分完全是为了解决语法上的困难。

## 14.6 空语句

空语句什么都不做。

```text
EmptyStatement:
    ;
```

空语句的执行总是正常完成。

## 14.7 标记语句

语句可以带有标记前缀。

```text
LabeledStatement:
    Identifier : Statement

LabeledNoShortIf:
    Identifier : StatementNoShortIf
```

标识符被声明为直接包含的语句的标记。与 C 和 C++ 不同，Java 编程语言没有 `goto` 语句；标识符语句用于标记语句内任何地方出现的 `break` 或 `continue` 语句（§14.15, §14.16）。

标记语句标记的作用域是直接包含的语句。如果在标记的作用域内将标记语句的名称作为另一个标记语句的标记，则是一个编译错误。

不限制将相同的标识符用标记以及包、类、接口、方法、字段、参数或局部变量的名称。使用标识符标记语句不会遮蔽（§6.4.2）具有同名的包、类、接口、方法、字段、参数或局部变量。将标识符作为类、接口、方法、字段、局部变量或异常处理器的参数（§14.20）使用，不会遮蔽同名的语句标记。

标记语句是通过执行直接包含的语句来执行的。

如果语句被一个标识符标记，且所包含的语句因为与相同标识符的 `break` 而导致异常终止，则标记语句正常完成。在语句异常终止的所有其他情况下，标记语句都以相同的原因导致异常终止。

### 示例 14.7-1 标记与标识符

以下代码取自 `String` 类及其 `indexOf` 方法，其中标记最初命名为 `test`。将标记更改为与局部变量 `i` 相同的名称不会在 `i` 声明的作用域内遮蔽该标记。因此，代码是有效的。

```java
class Test {
    char[] value;
    int offset, count;

    int indexOf(TestString str, int fromIndex) {
        char[] v1 = value, v2 = str.value;
        int max = offset + (count - str.count);
        int start = offset + ((fromIndex < 0) ? 0 : fromIndex);

        for (int i = start; i <= max; i++) {
            int n = str.count, j = i, k = str.offset;
            while (n-- != 0) {
                if (v1[j++] != v2[k++])
                    continue;
            }
            return i - offset;
        }
        return -1;
    }
}
```

标识符 `max` 也可以作为语句标记；该标记不会遮蔽标记语句内的局部变量 `max`。

## 14.8 表达式语句

某些类型的表达式可以通过在其后加上分号作为语句使用。

```text
ExpressionStatement:
    StatementExpression;

StatementExpression:
    Assignment
    PreIncrementExpression
    PreDecrementExpression
    PostIncrementExpression
    PostDecrementExpression
    MethodInvocation
    ClassInstanceCreationExpression
```

表达式语句通过求值表达式来执行；如果表达式有值，则该值会被丢弃。

表达式语句的执行正常完成，当且仅当表达式语句的求值正常完成。

与 C 和 C++ 不同，Java 编程语言仅允许某些形式的表达式作为表达式语句。例如，使用方法调用表达式（§15.12）是合法的：

```java
System.out.println("Hello world"); // OK
```

但使用带括号表达式（§15.8.5）是不合法的：

```java
(System.out.println("Hello world"));   // illegal
```

注意，Java 编程语言不允许“转换为 void”——`void` 不是一种类型——因此传统的编写表达式语句的技巧例如：

```java
(void); ...; // 错误！
```

不起作用。另一方面，Java 编程语言允许在 `if-then` 语句、`if-then-else` 语句、`while` 语句、`for` 语句和 `for-each` 语句中使用最实用的表达式类型。

## 14.9 if 语句

当类层次结构在静态初始化中包含循环依赖时，如下例所示：

```java
public class Foo {
    public static void main(String[] args) {
        Baz.testAsserts();
        // 在 Baz 初始化后执行。
    }
}

class Bar {
    static {
        // 在 Baz 初始化之前执行！
    }
}

class Baz extends Bar {
    static void testAsserts() {
        boolean enabled = false;
        assert enabled = true;
        System.out.println("Asserts " + (enabled ? "enabled" : "disabled"));
    }
}
```



调用 `Baz.testAsserts()` 会导致 `Baz` 初始化。在此之前，必须初始化 `Bar`。`Bar` 的静态初始化器再次调用 `Baz.testAsserts()`。由于当前线程正在进行 `Baz` 初始化，第二次调用将立即返回，尽管 `Baz` 尚未初始化（§12.4.2）。

根据上述规则，如果在未启用断言的情况下执行上述程序，它必须打印：

- Asserts enabled
- Assert disabled

禁用的断言语句不执行任何操作。特别是，`Expression1` 或 `Expression2` 都不会被评估。禁用的断言语句的执行始终正常完成。

断言语句的执行首先是评估 `Expression1`。如果结果的类型为 `Boolean`，则对其进行自动拆箱转换（§5.1.8）。

如果由于某些原因 `Expression1` 的评估或随后的自动拆箱转换（如果有）异常终止，则断言语句将以相同原因异常终止。

否则，通过根据 `Expression1` 的值进行选择继续执行：

- 如果值为 `true`，则不采取进一步操作，且断言语句正常完成。
- 如果值为 `false`，则执行行为取决于是否存在 `Expression2`：
  - 如果存在 `Expression2`，则对其进行评估。然后：
    - 如果评估由于某些原因异常终止，则断言语句将以相同原因异常终止。
    - 如果评估正常完成，则创建一个 `AssertionError` 实例，其“详细消息”为 `Expression2` 的评估结果值：
      - 如果实例创建由于某些原因异常终止，则断言语句将以相同原因异常终止。
      - 如果实例创建正常完成，则断言语句通过抛出新创建的 `AssertionError` 对象而异常终止。
  - 如果不存在 `Expression2`，则创建一个没有“详细消息”的 `AssertionError` 实例：
    - 如果实例创建由于某些原因异常终止，则断言语句将以相同原因异常终止。
    - 如果实例创建正常完成，则断言语句通过抛出新创建的 `AssertionError` 对象完成。

通常情况下，在程序开发和测试期间启用断言，而在部署时禁用以提高性能。

由于断言可能被禁用，程序不能假设断言包含的表达式会被评估。因此，这些布尔表达式通常不应该有副作用。这样的布尔表达式不应影响评估完成后可见的任何状态。在断言中包含的布尔表达式有副作用并不是非法的，但通常是不恰当的，因为它可能导致程序行为根据断言的启用或禁用而变化。

鉴于此，不应在公共方法中使用断言进行参数检查。参数检查通常是方法契约的一部分，无论是否启用了断言，都必须维护该契约。

使用断言进行参数检查的次要问题是，错误的参数可能会导致不适当的运行时异常（例如 `IllegalArgumentException`、`ArrayIndexOutOfBoundsException` 或 `NullPointerException`）。断言失败不会抛出适当的异常。再次，在公共方法上使用断言进行参数检查并不是非法的，但通常是不恰当的。设计意图是 `AssertionError` 永远不会被捕获，但也可以这样做，因此 `try` 语句的规则处理出现在 `try` 块中的断言应与当前对 `throw` 语句的处理类似。

## 14.11 switch语句

`switch` 语句根据表达式的值将控制转移到多个语句或表达式之一。

```
SwitchStatement:
switch ( Expression ) SwitchBlock
```

`Expression` 被称为选择表达式。选择表达式的类型必须是 `char`、`byte`、`short`、`int`、`Character`、`Byte`、`Short`、`Integer`、`String` 或枚举类型（§8.9），否则将发生编译错误。

## 14.11.1 Switch块

`switch` 语句和 `switch` 表达式（§15.28）的体被称为 switch块。本小节介绍了适用于所有 switch块的通用规则，无论它们出现在 `switch` 语句还是 `switch` 表达式中。其他小节介绍了适用于 `switch` 语句中的 switch块（§14.11.2）或 `switch` 表达式中的 switch块（§15.28.1）的附加规则。

```
SwitchBlock:
{ SwitchRule {SwitchRule} }
{ SwitchBlockStatementGroup } {SwitchLabel : } }
```

```
SwitchRule:
SwitchLabel -> Expression ;
SwitchLabel -> Block
SwitchLabel -> ThrowStatement
```

```
SwitchBlockStatementGroup:
SwitchLabel : {SwitchLabel :} BlockStatements
```

```
SwitchLabel:
case CaseConstant {, CaseConstant}
default
```

### CaseConstant
`ConditionalExpression`

一个 switch块可以由以下之一组成：

- switch 规则，使用 `->` 引入 switch 规则表达式、switch 规则块或 switch 规则抛出语句，
- switch 标签语句组，使用 `:` 引入 switch 标签语句。

每个 switch 规则和 switch 标签语句组都以 switch 标签开始，该标签是 case 标签或 default 标签。一个 switch 标签语句组允许多个标签。

一个 case 拥有一个或多个 case 常量。每个 case 常量必须是常量表达式（§15.29）或枚举常量的名称（§8.9.1）。

switch 语句或 switch 表达式体与选择表达式的类型 `T` 兼容，仅当满足以下条件时：

- 如果 `T` 不是枚举类型，则 switch 块的 case 常量是 `T` 的赋值兼容类型。
- 如果 `T` 是枚举类型，则 switch 块的 case 常量是该枚举类型的枚举常量。

一个 case 必须是常量，否则将发生编译错误。

## 块与语句

在 C 和 C++ 中，switch 语句的体可以是一个语句，带有标签的语句不需要立即包含在该语句中。考虑以下简单的循环：

```c
for (i = 0; i < n; ++i) foo();
```

其中 `n` 已知为正数。可以使用称为 Duff 设备的技巧在 C 或 C++ 中展开循环，但这在 Java 语言中不是有效的代码：

```c
int q = (n+7) / 8;
switch (n%8) {
    case 0: do { foo();
    case 7: foo();
    case 6: foo();
    case 5: foo();
    case 4: foo();
    case 3: foo();
    case 2: foo();
    case 1: foo();
} while (--q > 0);
}
```

幸运的是，这种技巧似乎并不被广泛为人知或使用。此外，它现在不再需要了；这种代码转换属于先进优化编译器的领域。

## 14.11.2 switch 语句的 switch块

除了 switch 块的通用规则（§14.11.1）外，switch语句中的 switch 块还有进一步的规则。也就是说，switch语句的 switch 块必须满足以下所有条件，否则将发生编译错误：

- switch 块最多关联一个默认标签（default label）。
- switch 块中的每个 switch 规则表达式都是语句表达式（§14.8）。

switch 语句与 switch 表达式的区别在于哪些表达式可以出现在 switch 块箭头（`->`）右侧，即哪些表达式可以作为 switch 规则表达式。在 switch 语句中，只有语句表达式可以作为 switch 规则表达式，但在 switch 表达式中，任何表达式都可以使用（§15.28.1）。



## 14.11.3 switch 语句的执行

`switch` 语句的执行首先求值选择器表达式。然后：

- 如果选择器表达式的评估异常完成，则整个 `switch` 语句也因相同原因异常完成。
- 否则，如果选择器表达式的求值结果为 `null`，则抛出 `NullPointerException`，且整个 `switch` 语句因该原因异常完成。
- 否则，如果选择器表达式的求值结果类型为 `Character`、`Byte`、`Short` 或 `Integer`，则进行拆箱转换（§5.1.8）。如果该转换异常完成，则整个 `switch` 语句因相同原因异常完成。

如果选择器表达式的评估正常完成且结果为 `null`，且随后的拆箱转换（如果有）正常完成，则通过确定与 `switch` 块关联的 `switch` 标签是否匹配选择器表达式的值（§14.11.1）来继续执行 `switch` 语句。然后：

- 如果没有 `switch` 标签，则整个 `switch` 语句正常完成。
- 如果有 `switch` 标签，则适用以下情况之一：
  - 如果它是 `switch` 规则表达式的 `switch` 标签，则该 `switch` 规则表达式必然是一个语句表达式（§14.11.2）。评估该语句表达式。如果评估正常完成，则语句正常完成。如果评估结果是一个值，则将其丢弃。
  - 如果它是 `switch` 块的 `switch` 标签，则执行该块。如果该块正常完成，则 `switch` 语句正常完成。
  - 如果它是 `switch` 规则 `throw` 语句的 `switch` 标签，则执行该 `throw` 语句。
  - 如果它是 `switch` 标签组的 `switch` 标签，则按顺序执行 `switch` 块中 `switch` 标签之后的所有语句。如果这些语句正常完成，则 `switch` 语句正常完成。
  - 否则，`switch` 块中没有跟在匹配 `switch` 标签之后的语句，`switch` 语句正常完成。

如果 `switch` 块中任何语句或表达式的执行异常完成，则按如下方式处理：

- 如果语句的执行因无标签的 `break` 而异常完成，则不采取进一步操作，且 `switch` 语句正常完成。

> 因带标签的 `break` 导致的异常完成由标签语句的通用规则（§14.7）处理。

- 如果语句或表达式的执行因任何其他原因异常完成，则 `switch` 语句因相同原因异常完成。

> 因 `yield` 语句导致的异常完成由 `switch` 表达式的通用规则（§15.28）处理。

### 14.11.3-1 switch 语句中的贯穿

选择器匹配 `switch` 规则的标签时，执行由 `switch` 标签引入的 `switch` 规则表达式或语句，不再执行其他内容。在语句组 `switch` 标签的情况下，执行 `switch` 块中 `switch` 标签之后的所有语句，包括出现在后续 `switch` 标签之后的语句。其效果是在 C 和 C++ 中，语句的执行可以“贯穿标签”。

例如，该程序：

```java
class TooMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.print("*one ");
            case 2: System.out.print("*two ");
            case 3: System.out.println("*many");
        }
    }

    public static void main(String[] args) {
        howMany(3);
        howMany(2);
        howMany(1);
    }
}
```

该程序包含一个 `switch` 块，其中每个 `case` 的代码都会进入下一个 `case` 的代码。结果是，程序打印：

```
many
too many
one too many
```

贯穿可能是细微 bug 的原因。如果代码不希望这种方式贯穿 `case`，则可以使用 `break` 语句来指示何时应该转移控制，或者使用 `switch` 规则，如下程序所示：

```java
class TwoMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.println("one");
                break; // 退出 switch
            case 2: System.out.println("two");
                break; // 退出 switch
            case 3: System.out.println("many");
                break; // 无需，但是良好的风格
        }
    }

    static void howManyAgain(int k) {
        switch (k) {
            case 1 -> System.out.println("one");
            case 2 -> System.out.println("two");
            case 3 -> System.out.println("many");
        }
    }

    public static void main(String[] args) {
        howMany(1);
        howMany(2);
        howMany(3);
        howManyAgain(1);
        howManyAgain(2);
        howManyAgain(3);
    }
}
```

## 14.12 while 语句

`while` 语句重复执行一个表达式和一个语句，直到该表达式的值为 `false`。

```
WhileStatement:
while ( Expression ) Statement

WhileStatementNoIf:
while ( Expression ) StatementNoIf
```

表达式的类型必须是 `boolean` 或 `Boolean`，否则将发生编译错误。
`while` 语句的执行首先求值表达式。如果结果是 `Boolean`，则进行拆箱转换（§5.1.8）。

如果表达式的评估或随后的拆箱转换（如果有）因原因异常完成，则 `while` 语句因相同原因异常完成。

否则，根据结果进行选择继续执行：

- 如果值为 `true`，则执行包含的语句。然后进行选择：
  - 如果语句正常完成，则重新执行整个 `while` 语句，从重新评估表达式开始。
  - 如果语句执行异常，参见 §14.12.1。
- 如果表达式的可能拆箱后的值为 `false`，则不采取进一步操作，`while` 语句正常完成。

如果表达式的可能拆箱后的值在第一次评估时为 `false`，则不执行语句。

### 14.12.1 while 语句的异常完成

包含语句的异常完成按如下方式处理：

- 如果语句的执行因无标签的 `break` 而异常完成，则不采取进一步操作，`while` 语句正常完成。
- 如果语句的执行因无标签的 `continue` 而异常完成，则重新执行整个 `while` 语句。
- 如果语句的执行因带标签的 `continue` 而异常完成，则进行选择：
  - 如果 `while` 语句有标签 `L`，则重新执行整个 `while` 语句。
  - 如果 `while` 语句没有标签 `L`，则 `while` 语句因带标签的 `continue` 异常完成。
- 如果语句的执行因任何其他原因异常完成，则 `while` 语句因相同原因异常完成。

> 因带标签的 `break` 导致的异常完成由标签语句的通用规则（§14.7）处理。

## 14.13 do 语句

`do` 语句重复执行一个语句和一个表达式，直到该表达式的值为 `false`。

```
DoStatement:
do Statement while ( Expression ) ;
```

表达式的类型必须是 `boolean` 或 `Boolean`，否则将发生编译错误。
`do` 语句的执行首先执行语句。然后进行选择：

- 如果语句的执行正常完成，则求值表达式。如果结果类型为 `Boolean`，则对其进行拆箱转换 (§5.1.8)。

如果表达式求值或随后的拆箱转换（如果有）由于某些原因异常终止，则 `do` 语句以相同原因异常终止。

否则，将根据结果的值进行选择：

- 如果值为 `true`，则再次执行整个 `do` 语句。
- 如果值为 `false`，则不采取进一步后续操作，且 `do` 语句正常完成。
- 如果语句的执行异常终止，请参阅 §14.13.1。

执行 `do` 语句始终至少执行一次其包含的语句。

### 14.13.1 do 语句的异常终止

包含的语句的异常终止按以下方式处理：

- 如果语句的执行因为无标签的 `break` 而异常终止，则不采取进一步后续操作，且 `do` 语句正常完成。
- 如果语句的执行因为无标签的 `continue` 而异常终止，则求值表达式。然后，将根据结果的值进行选择：
  - 如果值为 `true`，则再次执行整个 `do` 语句。
  - 如果值为 `false`，则不采取进一步后续操作，且 `do` 语句正常完成。
- 如果语句的执行因为带有标签 `L` 的 `continue` 而异常终止，则存在一种选择：
  - 如果 `do` 语句带有标签 `L`，则求值表达式。然后，存在一种选择：
    - 如果表达式的值为 `true`，则再次执行整个 `do` 语句。
    - 如果表达式的值为 `false`，则不采取进一步后续操作，且 `do` 语句正常完成。
  - 如果 `do` 语句不带标签 `L`，则 `do` 语句因为带有标签 `L` 的 `continue` 而异常终止。
- 如果语句的执行因为其他原因异常终止，则 `do` 语句以相同原因异常终止。

> 因带标签的 `break` 导致异常终止的情况由标签语句的通用规则 (§14.7) 处理。

### 示例 14.13-1. do 语句

以下是 `Integer` 类 `toHexString` 方法的一种可能的实现方式：

```java
public static String toHexString(int i) {
    StringBuffer buf = new StringBuffer(8);
    do {
        buf.append(Character.forDigit(i & 0xF, 16));
        i >>>= 4;
    } while (i != 0);
    return buf.reverse().toString();
}
```

必须生成一个数字，`do` 语句是一种适当的控制结构。

## 14.14 for 语句

`for` 语句有两种形式：

- 基础 `for` 语句。
- 增强 `for` 语句。

```
ForStatement:
BasicForStatement
EnhancedForStatement

ForStatementNoShortIf:
BasicForStatementNoShortIf
EnhancedForStatementNoShortIf
```

## 14.14.1 基础 for 语句

基础 `for` 语句执行某些初始化代码，然后重复执行一个表达式、一个语句和一个更新代码，直到表达式的值为 `false` 为止。

```
BasicForStatement:
for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement

BasicForStatementNoShortIf:
for ( [ForInit] ; [Expression] ; [ForUpdate] ) StatementNoShortIf

ForInit:
StatementExpressionList
LocalVariableDeclaration

ForUpdate:
StatementExpressionList

StatementExpressionList:
StatementExpression ( , StatementExpression )*
```

表达式必须具有 `boolean` 或 `Boolean` 类型，否则将发生编译错误。

在基础语句的 `ForInit` 部分声明的局部变量的作用域和遮蔽在 §6.3 和 §6.4 中规定。

### 14.14.1.1 for 语句的初始化

`for` 语句的执行首先是执行 `ForInit` 代码：

- 如果 `ForInit` 代码是语句表达式列表 (§14.8)，则按从左到右的顺序求值；它们的值（如果有）将被丢弃。如果任何表达式的求值由于某些原因异常终止，则 `for` 语句以相同原因异常终止；异常终止的表达式右侧的任何 `for` 语句表达式都不会被求值。
- 如果 `ForInit` 代码是局部变量声明 (§14.4)，其执行方式类似于在块中出现的局部变量声明。局部变量声明的执行由于任何原因异常终止，`for` 语句以相同原因异常终止。
- 如果不存在 `ForInit` 部分，则不采取任何操作。

### 14.14.1.2 for 语句的迭代

接下来执行 `for` 迭代，如下所示：

- 如果表达式存在，则对其求值。如果结果类型为 `Boolean`，则对其进行拆箱转换 (§5.1.8)。如果表达式求值或随后的拆箱转换（如果有）由于某些原因异常终止，则 `for` 语句以相同原因异常终止。

> 否则，将根据表达式的存在以及（如果表达式存在）其产生的值进行选择，见下方的项目符号。

- 如果表达式不存在，或者表达式存在且其求值产生的结果（包括任何可能的拆箱）为 `true`，则执行包含的语句。然后，存在一种选择：
  - 语句的执行正常完成，则按顺序执行以下两个步骤：
    1. 首先，如果存在 `ForUpdate` 部分，则按从左到右的顺序求值表达式；它们的值（如果有）将被丢弃。如果任何表达式的求值由于某些原因异常终止，则 `for` 语句以相同原因异常终止；异常终止的表达式右侧的任何 `for` 语句表达式都不会被求值。如果不存在 `ForUpdate` 部分，则不采取操作。
    2. 第二，执行下一次 `for` 迭代。
  - 如果语句的执行异常终止，参阅 §14.14.1.3。
- 如果表达式存在且求值产生的结果（包括任何可能的拆箱）为 `false`，则不采取进一步后续操作，且 `for` 语句正常完成。

表达式（可能拆箱）的值在第一次求值时为 `false`，则不执行语句。

如果表达式不存在，`for` 语句能够正常完成的唯一方法是使用 `break` 语句。

### 14.14.1.3 for 语句的异常终止

包含的语句的异常终止按以下方式处理：

- 如果语句的执行因为无标签的 `break` 而异常终止，则不采取进一步后续操作，且 `for` 语句正常完成。
- 如果语句的执行因为无标签的 `continue` 而异常终止，则按顺序执行以下两个步骤：
  1. 首先，如果存在 `ForUpdate` 部分，则按从左到右的顺序求值表达式；它们的值（如果有）将被丢弃。如果不存在 `ForUpdate` 部分，则不采取操作。
  2. 第二，执行下一次 `for` 迭代。
- 如果语句的执行因为带有标签 `L` 的 `continue` 而异常终止，则存在一种选择：
  - 如果 `for` 语句带有标签 `L`，则按顺序执行以下两个步骤：
    1. 首先，如果存在 `ForUpdate` 部分，则按从左到右的顺序求值表达式；它们的值（如果有）将被丢弃。如果不存在 `ForUpdate` 部分，则不采取操作。
    2. 第二，执行下一次 `for` 迭代。
  - 如果 `for` 语句不带标签 `L`，则 `for` 语句因为带有标签 `L` 的 `continue` 而异常终止。
- 如果语句的执行因为其他原因异常终止，则 `for` 语句以相同原因异常终止。

> 因带标签的 `break` 导致异常终止的情况由标签语句的通用规则 (§14.7) 处理。

## 14.14.2 增强型 for 语句

增强 `for` 语句的形式如下：

```
EnhancedForStatement:
for ( {VariableModifier} LocalVariableType VariableDeclaratorId : Expression ) Statement

EnhancedForStatementNoShortIf:
for ( {VariableModifier} LocalVariableType VariableDeclaratorId : Expression ) StatementNoShortIf
```

为了方便起见，此处展示了 §4.3、§8.3、§8.4.1 和 §14.4 中的产生式：

```
VariableModifier:
Annotation
final

LocalVariableType:
UnannType
var

VariableDeclaratorId:
Identifier [Dims]

Dims:
{ [Annotation] } [ [Annotation] ]*
```



# 增强 for 语句

增强 for 语句的头部声明了一个局部变量，其名称为由 `VariableDeclaratorId` 给出的标识符。

如果关键字 `final` 出现在声明的开头，当 `LocalVariableType` 为 `var` 且 `VariableDeclaratorId` 具有一个或多个括号对，则所声明的变量会导致编译时错误。

`Expression` 的类型必须是原始类型 `Iterable` 的子类型或数组类型（§10.1），否则将发生编译时错误。

局部变量的类型确定如下：

- 如果 `LocalVariableType` 是一个 `UnannType`，且在 `UnannType` 或 `VariableDeclaratorId` 中没有出现括号对，则 `UnannType` 表示局部变量的类型。
- 如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号对，则局部变量的类型由 §10.2 指定。
- 如果 `LocalVariableType` 为 `var`，则 $τ$ 根据 `Expression` 的类型推导如下：
    - 如果 `Expression` 是数组类型，则 $τ$ 是该数组类型的组件类型。
    - 否则，如果 `Expression` 的类型对于某些类型 $x$ 是 `Iterable<X>` 的子类型，则 $τ$ 是 $X$。
    - 否则，`Expression` 的类型是原始类型 `Iterable` 的子类型，且 $τ$ 是 `Object`。

局部变量的类型是相对于 $τ$（§4.10）中提到的所有合成类型变量的向上投影（upward projection）。

局部变量的作用域和屏蔽（shadowing）在 §6.3 和 §6.4 中规定。

当执行增强语句时，局部变量在每次循环迭代中都会初始化为 `expression` 产生的数组或 `Iterable` 的后续元素。增强语句的精确含义通过翻译为基础 for 语句给出，如下：

- 如果 `Expression` 的类型是 `Iterable` 的子类型，则翻译如下。

如果 `Expression` 的类型对于某些类型参数 $x$ 是 `Iterable<X>` 的子类型，则令 $I$ 为 `java.util.Iterator<X>` 类型；否则，令 $I$ 为原始 `java.util.Iterator`。

增强语句等价于如下形式的基础 for 语句：

```java
for (I #i = Expression.iterator(); #i.hasNext(); ) {
    (VariableModifier) TargetType Identifier = (TargetType) #i.next();
}
```

`#i` 是一个自动生成的标识符，与增强 for 语句发生点作用域内（§6.3）的任何其他标识符（自动生成的或其他）都不同。

如果增强 for 语句头部中局部变量的声明类型是引用类型，则 `TargetType` 为该声明类型；否则，`TargetType` 是 $I$ 的类型参数捕获转换（$5.1.10）的上界，如果 $R$ 是原始的则为 `Object`。

例如，代码：

```java
List<? extends Integer> l = ...;
for (float i : l) { ... }
```

将被翻译为：

```java
for (Iterator<Integer> #i = l.iterator(); #i.hasNext();) {
    float #i0 = (Integer)#i.next();
}
```

- 否则，`Expression` 必然具有数组类型 $T[]$。

令 $L1... Lm$ 为紧邻增强语句之前的（可能为空的）标签序列。

增强 for 语句等价于如下形式的基础 for 语句：

```java
T[] #a = Expression;
L1; L2... Lm;
for (int #i = 0; #i < #a.length; #i++) {
    {VariableModifier} TargetType Identifier = #a[#i];
    Statement
}
```

`#a` 和 `#i` 是自动生成的标识符，与增强语句发生点作用域内的任何其他标识符（自动生成的或其他）都不同。

`TargetType` 是增强 for 语句头部中局部变量的声明类型。

## 示例 14.14-1. 数组增强型 for

以下程序计算整数数组的和，展示了数组的增强型 for 的用法：

```java
int sum(int[] a) {
    int sum = 0;
    for (int i : a) sum += i;
    return sum;
}
```

## 示例 14.14-2. 增强型 for 与自动拆箱转换

以下程序将增强 for 语句与自动拆箱结合，将直方图转换为频率表：

```java
Map<String, Integer> histogram = ...;
double total = 0;
for (int i : histogram.values())
    total += i;
for (Map.Entry<String, Integer> e : histogram.entrySet()) {
    System.out.println(e.getKey() + " " + e.getValue() / total);
}
```

# 14.15 break 语句

break 语句跳转出封装语句。

```
BreakStatement:
break [Identifier] ;
```

有两种 break 语句：

- 不带标签的 break 语句
- 带有标签的 break 语句

不带标签的 break 语句跳转出 `switch`、`while` 或 `for` 封装语句。

带有标签的 break 语句跳转出带有该标签的 `switch`、`while` 或 `for` 封装语句。如果 break 语句位于 `try` 块中，则先执行 `try` 块对应的 `finally` 块（§14.20），然后再跳转到目标。

描述使用“尝试跳转”而非仅仅是“跳转”，如果 break 语句内部存在 `try` 块。在跳转之前 `try` 块的 `finally` 块会按顺序从内部到外部执行。

### 示例 14.15-1. break 语句

在以下示例中，数学图由数组的数组表示。图由一组节点和一组边组成，每条边都是指向某个节点或节点自身的数组。在本示例中假设没有冗余边；即对于任意两个节点 $P$ 和 $Q$，即使 $Q$ 等于 $P$，从 $P$ 到 $Q$ 也最多只有一条边。

节点由索引表示，对于使得数组引用 `edges[i]` 不抛出 `ArrayIndexOutOfBoundsException` 的 $i$ 和 $j$，存在从节点 $i$ 到节点 $j$ 的边。

`loseEdges` 方法的任务给定整数 $i$ 和 $j$，通过复制给定图来构造新图，删除从节点 $i$ 到节点 $j$ 的边（如果有）以及从节点 $j$ 到节点 $i$ 的边（如果有）。

```java
class Graph {
    int edges[][];

    public Graph(int[][] edges) { this.edges = edges; }

    public Graph loseEdges(int i, int j) {
        int n = edges.length;
        int[][] newedges = new int[n][];

        for (int k = 0; k < n; k++) {
            edgelist: {
                int z;
                search: {
                    if (k == i) {
                        for (z = 0; z < edges[k].length; z++) {
                            if (edges[k][z] == j) break search;
                        }
                    } else if (k == j) {
                        for (z = 0; z < edges[k].length; z++) {
                            if (edges[k][z] == i) break search;
                        }
                    }
                    // 没有需要删除的边，共享此列表。
                    newedges[k] = edges[k];
                    break edgelist;
                }
                // 复制列表，删除位置 z 处的边。
                int m = edges[k].length - 1;
                int[] ne = new int[m];
                System.arraycopy(edges[k], 0, ne, 0, z);
                System.arraycopy(edges[k], z + 1, ne, z, m - z);
                newedges[k] = ne;
            } // edgelist
        }
        return new Graph(newedges);
    }
}
```

对两个语句标签 `edgelist` 和 `search` 的使用以及 `break` 语句的使用。这使得拷贝列表并省略一条边的代码可以在两个独立的测试之间共享：即从节点 i 到节点 j 的边的测试，以及从节点 j 到节点 i 的边的测试。

# 14.16 continue 语句

`continue` 语句只能出现在 `while`、`do` 或 `for` 语句中；这三类语句被称为迭代语句。控制传递到迭代语句的循环继续点。

```
ContinueStatement:
continue [Identifier];
```

`continue` 语句有两种类型：

- 无标签的 `continue` 语句。
- 带有标签 `Identifier` 的 `continue` 语句。

不带标签的 `continue` 语句尝试将控制传递到最内层的嵌套 `while`、`do` 或 `for` 语句；该嵌套语句即 continue 目标，然后立即结束当前迭代并开始新的迭代。

带有标签 `Identifier` 的 `continue` 语句尝试将控制传递到具有相同标签 `Identifier` 的外层带标签语句 (§14.7)；这被称为 continue 目标，然后立即结束当前迭代并开始新的迭代。在这种情况下，continue 目标必须是一个 `while`、`do` 或 `for` 语句，否则会发生编译时错误。

如果 `continue` 语句没有 continue 目标，则为编译时错误。

如果 continue 目标包含任何封装该 `continue` 语句的方法、构造函数、实例初始化器、静态初始化器、lambda 表达式或 switch 表达式，则为编译时错误。也就是说，不存在非局部跳转。

执行不带标签的 `continue` 语句会异常完成，原因是无标签的 `continue`。

执行带有标签 `Identifier` 的 `continue` 语句始终会异常完成，原因是带有标签 `Identifier` 的 `continue`。

由此可见，`continue` 语句始终异常完成。

请参见 `while` 语句（§14.12）、`do` 语句（§14.13）和 `for` 语句（§14.14）的描述，以讨论由于 `continue` 导致的异常终止的处理。

前面的描述使用了“尝试传递控制”而非仅仅是“传递控制”，是因为如果 continue 目标内部存在任何包含该 `continue` 语句子句的 `try` 语句（§14.20），在控制传递到 continue 目标之前，这些 `try` 语句的任何 `finally` 将按照从内部到外部顺序执行。`finally` 子句的异常完成可能会中断由 `continue` 语句引发的控制传递。

### 示例 14.16-1 continue 语句

在 Graph (§14.15) 中，其中一个 `break` 语句用于结束最外层 `for` 循环主体的执行。如果 `for` 循环带有标签，可以将此 `break` 替换为 `continue`：

```java
class Graph {
    int edges[][];

    public Graph(int[][] edges) { this.edges = edges; }

    public Graph loseEdges(int i, int j) {
        int n = edges.length;
        int[][] newedges = new int[n][];

        edgelists:
        for (int k = 0; k < n; k++) {
            int z;
            search:
            if (k == i) {
                for (z = 0; z < edges[k].length; z++) {
                    if (edges[k][z] == j) break search;
                }
            } else if (k == j) {
                for (z = 0; z < edges[k].length; z++) {
                    if (edges[k][z] == i) break search;
                }
            }
            // 无需要删除的边；共享此列表。
            newedges[k] = edges[k];
            continue edgelists;
        }

        // 复制列表，省略位置 z 处的边。
        int m = edges[k].length - 1;
        int[] ne = new int[m];
        System.arraycopy(edges[k], 0, ne, 0, z);
        System.arraycopy(edges[k], z + 1, ne, z, m - z);
        newedges[k] = ne;
        // edgelists
        return new Graph(newedges);
    }
}
```

使用哪一种（如果两种都有的话）很大程度上取决于编程风格。

# 14.17 return 语句

`return` 语句将控制返回给方法的调用者（§8.4, §15.12）或构造函数（§8.8, §15.9）。

```
ReturnStatement:
return [Expression];
```



# return 语句

`return` 语句有两种类型：

- 无值的 `return` 语句。
- 带有值 `Expression` 的 `return` 语句。

`return` 语句尝试将控制传递给最内层嵌套构造函数、方法或 lambda 表达式的调用者；该嵌套声明或表达式被称为 return 目标。在带有值 `Expression` 的 `return` 语句情况下，`Expression` 的值成为调用的值。

如果 return 目标没有 return 目标，则为编译时错误。

如果 return 目标包含 (i) 封装该 `return` 语句的实例或静态初始化器，或 (ii) 封装该 `return` 语句的 switch 表达式，则为编译时错误。

如果无值 `return` 语句的 return 目标是一个方法且该方法未声明为 `void`，则为编译时错误。

如果带有值 `Expression` 的 `return` 语句的 return 目标是构造函数或声明为 `void` 方法，则为编译时错误。

如果带有值 `Expression` 的 `return` 语句的 return 目标是一个声明了返回类型 T 的方法，且 `Expression` 的类型与 T 不兼容（§5.2），则为编译时错误。

执行无值的 `return` 语句始终异常完成，原因是无值的 `return`。

执行带有值 `Expression` 的 `return` 语句首先对 `Expression` 进行求值；如果 `Expression` 的求值由于某些原因异常完成，则 `return` 语句因该原因异常完成。如果 `Expression` 的求值正常完成产生值 V，则 `return` 语句异常完成。

# throw 语句

`throw` 语句会导致异常（§11.2）抛出。如果没有找到相应的 `try` 语句，则在调用所属线程组的 `uncaughtException` 方法后终止线程执行（§17 线程与锁）。

```
ThrowStatement:
    throw Expression ;
```

`throw` 语句中的 `Expression` 必须表示一个与 `Throwable` 兼容（§5.2）的引用类型的变量或值，或者表示空引用，否则将发生编译时错误。

`Expression` 的引用类型将始终是一个类类型（因为接口类型无法赋值给 `Throwable`）且不是泛型的（`Throwable` 的子类不能是泛型）。

必须满足以下条件之一，否则将发生编译时错误：

- `Expression` 的类型是非检查异常类（§11.1）或空类型（§4.1）。
- `throw` 语句包含在 `try` 语句（§14.20）中且该 `try` 语句能够抛出 `Expression` 类型的异常。（在这种情况下我们说 throw 被 `try` 语句捕获）。
- `throw` 语句包含在方法或构造函数声明中，且 `Expression` 的类型赋值给 throws 子句（§8.4.6, §8.8.5）中的至少一种类型。

throw 语句可以指定的异常参见 §11.2.2。

`throw` 语句首先求值 `Expression` 然后：

- 如果 `Expression` 的求值由于某些原因异常完成，则 `throw` 因该原因异常完成。
- 如果 `Expression` 的求值正常完成产生非空值 V，则 `throw` 语句异常完成，原因是值为 V 的 `throw`。
- 如果 `Expression` 的求值正常完成产生空值，则创建一个 `NullPointerException` 类的实例 V' 并代替空值抛出。`throw` 语句异常完成，原因是值为 V' 的 `throw`。

如果存在任何包含 `throw` 语句的外层 `try` 语句（§14.20），则在控制向外传递时，这些 `try` 语句的任何 `finally` 子句将执行，直到抛出的值被捕获。注意 `finally` 子句的异常完成可能会中断由 `throw` 语句引发的控制传递。

如果 `throw` 语句包含在方法声明或 lambda 表达式中，但其值没有被包含它的 `try` 语句捕获，则方法的调用将因为 `throw` 而异常地终止。

如果 `throw` 语句包含在构造函数声明中，但其值没有被包含它的 `try` 语句捕获，则被调用的构造函数所产生的类创建异常将因为 `throw` 而异常地终止（§15.9.4）。

如果 `throw` 语句包含在静态初始化器（§8.7）中，则编译时检查（§11.2.3）确保其值要么始终是一个未检查的异常，要么其值被包含它的 `try` 语句捕获。在运行时，尽管有此项检查，如果该值仍未被包含 `throw` 语句的 `try` 语句捕获，且该值是 `Error` 类或其子类的实例，则将其重新抛出；否则，它被封装在 `ExceptionInInitializerError` 对象中，然后抛出（§12.4.2）。

如果 `throw` 语句包含在实例初始化器（§8.6）中，则编译时检查（§11.2.3）确保其值始终是一个未检查的异常，或者其值被包含它的 `try` 语句捕获，或者抛出异常的类型（或其任一超类）出现在类的每个构造方法的 `throws` 子句中。

按照惯例，用户声明的可抛类型通常应声明为 `Exception` 类的子类，`Exception` 是 `Throwable` 类的子类（§11.1.1）。

# synchronized 语句

`synchronized` 语句代表执行线程获取一个互斥锁（§17.1），执行一个块，然后释放锁。在执行线程拥有锁期间，其他线程均无法获取该锁。

```
SynchronizedStatement:
    synchronized ( Expression ) Block
```

`Expression` 的类型必须是引用类型，否则将发生编译错误。

`synchronized` 语句的执行首先是评估 `Expression`。然后：

- 如果 `Expression` 的评估由于某些原因异常地完成，则 `synchronized` 语句因相同原因异常地终止。
- 否则，如果 `Expression` 的值为 `null`，则抛出 `NullPointerException`。
- 否则，让 `Expression` 的非空值为 v。执行线程锁定与 v 关联的监视器。然后执行 Block，接着有两种选择：
    - 如果 Block 的执行正常完成，则解锁监视器且 `synchronized` 语句正常完成。
    - 如果 Block 的执行由于任何原因异常地完成，则解锁监视器且 `synchronized` 语句因相同原因异常地终止。

通过 `synchronized` 语句获取的锁与通过 `synchronized` 方法隐式获取的锁相同（§8.4.3.6）。同一个线程可以多次获取锁。

获取与对象关联的锁本身并不能防止其他访问对象的字段或调用对象上的未同步方法。其他线程也可以以常规方式使用 `synchronized` 方法或 `synchronized` 语句来实现互斥。

## 示例 14.19-1. synchronized 语句

```java
class Test {
    public static void main(String[] args) {
        Test t = new Test();
        synchronized(t) {
            synchronized(t) {
                System.out.println("made it!");
            }
        }
    }
}
```

此程序产生输出：

`made it!`

注意，如果不允许单个线程多次锁定监视器，则该程序将导致死锁。

# try 语句

`try` 语句执行一个块。如果抛出了值且 `try` 语句有一个或多个可以捕获它的 catch 子句，则控制将转移到第一个 catch 子句。如果 `try` 语句有一个 `finally` 子句，无论 `try` 块是正常完成还是异常地完成，也无论 catch 子句是否先获得控制权，都会执行另一个代码块。

```
TryStatement:
    try Block Catches
    try Block [Catches] Finally
    TryWithResourcesStatement

Catches:
    CatchClause { CatchClause }

CatchClause:
    catch ( CatchFormalParameter ) Block

CatchFormalParameter:
    VariableModifier CatchType VariableDeclaratorId

CatchType:
    UnannClassType (| ClassType)

Finally:
    finally Block
```

关于 `UnannClassType` 参见 §8.3。为了方便起见，这里显示了来自 §4.3、§8.3 和 §8.4.1 的产生式：

```
VariableModifier:
    Annotation
    final

VariableDeclaratorId:
    Identifier [Dims]

Dims:
    [Annotation] [] [[Annotation] [] ]
```

紧跟关键字 `try` 之后的 Block 称为该 `try` 语句的 try 块。紧跟关键字 `finally` 之后的 Block 称为该 `try` 语句的 finally 块。

`try` 语句可以有 catch 子句，也称为异常处理器。一个 catch 子句精确声明一个参数，该参数被称为异常参数。

如果 `final` 作为异常参数声明的修饰符出现多次，则为编译错误。异常参数的作用域和遮蔽在 §6.3 和 §6.4 中规定。

此处，具有两个替代方案的多异常 catch 子句已被翻译为针对每个替代方案的两个单异常 catch 子句。Java 编译器并不被要求也不建议通过这种复制代码的方式来编译多异常 catch 子句，因为可以在类文件中不重复地表示多异常 catch 子句。

finally 子句确保在执行 try 块以及任何可能执行的 catch 块之后执行 finally 块，无论控制流如何离开 try 块或 catch 块。finally 块的处理更为复杂，因此分别描述了带有 finally 块和不带 finally 块的 try 语句的两种情况（§14.20.1, §14.20.2）。

如果 try 语句是 try-with-resources 语句，允许省略 catch 子句和 finally 子句（§14.20.3）。

## 14.20.1 try-catch 的执行

不带 finally 块的 try 语句通过首先执行 try 块执行。然后有如下选择：

- 如果 try 块的执行正常完成，则不采取进一步操作，try 语句正常完成。
- 如果 try 块的执行因为抛出一个值 V 而异常完成，则有如下选择：
  - 如果 V 的运行时类型与（§5.2） try 语句中的可捕获异常类赋值兼容，则选择第一个（最左边的）此类 catch 子句。将值 V 赋值给所选 catch 子句的参数，并执行 catch 语句的块，然后有如下选择：
    - 如果该块正常完成，则 try 语句正常完成。
    - 如果该块由于任何原因异常完成，则 try 语句因相同原因异常完成。
- 如果 V 的运行时类型与 try 语句中任何 catch 子句的可捕获异常类不赋值兼容，则 try 语句由于抛出值 V 而异常完成。
- 如果 try 块的执行由于任何其他原因而异常完成，则 try 语句因相同原因异常完成。

### 示例 14.20.1-1. 捕获异常

```java
class BlewIt extends Exception {
    BlewIt() { }
    BlewIt(String s) { super(s); }
}

class Test {
    static void blowUp() throws BlewIt { throw new BlewIt(); }

    public static void main(String[] args) {
        try {
            blowUp();
        } catch (RuntimeException r) {
            System.out.println("Caught RuntimeException");
        } catch (BlewIt b) {
            System.out.println("Caught BlewIt");
        }
    }
}
```

在这里，异常 `BlewIt` 由方法 `blowUp` 抛出。`main` 方法体中的 try-catch 语句有两个 catch 子句。异常的运行时类型是 `BlewIt`，它不能赋值给 `RuntimeException` 类型的变量，但可以赋值给 `BlewIt` 类型的变量，因此该示例的输出为：

`Caught BlewIt`

## 14.20.2 try-finally 和 try-catch-finally 的执行

带有 finally 块的 try 语句通过首先执行 try 块执行。然后有如下选择：

- 如果 try 块的执行正常完成，则执行 finally 块，然后有如下选择：
  - 如果 finally 块正常完成，则 try 语句正常完成。
  - 如果 finally 块由于原因 S 异常完成，则 try 语句因原因 S 异常完成。
- 如果 try 块的执行因为抛出一个值 v 而异常完成，则有如下选择：
  - 如果 v 的运行时类型与 try 语句中任何 catch 子句的可捕获异常类赋值兼容，则选择第一个（最左边的）此类 catch 子句。将值 v 赋值给所选 catch 子句的参数，并执行 catch 子句块。然后有如下选择：
    - 如果 catch 块正常完成，则执行 finally 块。然后有如下选择：
      - 如果 finally 块正常完成，则 try 语句正常完成。
      - 如果 finally 块由于任何原因异常完成，则 try 语句因相同原因异常完成。
    - 如果 catch 块由于原因 R 异常完成，则执行 finally 块。然后有如下选择：
      - 如果 finally 块正常完成，则 try 语句因原因 R 异常完成。
      - 如果 finally 块由于原因 s 异常完成，则 try 语句因原因 s 异常完成（原因 R 被丢弃）。
- 如果 V 的运行时类型与 try 语句中任何 catch 子句的可捕获异常类不赋值兼容，则执行 finally 块。然后有如下选择：
  - 如果 finally 块正常完成，则 try 语句由于抛出值 V 而异常完成。
  - 如果 finally 块由于原因 S 异常完成，则 try 语句因原因 s 异常完成（值 V 的抛出被丢弃并忽略）。
- 如果 try 块的执行由于任何其他原因 R 而异常完成，则执行 finally 块，然后有如下选择：
  - 如果 finally 块正常完成，则 try 语句因原因 R 异常完成。
  - 如果该块由于原因 S 异常完成，则 try 语句因原因 S 异常完成（原因 R 被丢弃）。

### 示例 14.20.2-1. 使用 finally 处理意外异常

```java
class BlewIt extends Exception {
    BlewIt() { }
    BlewIt(String s) { super(s); }
}

class Test {
    static void blowUp() throws BlewIt {
        throw new NullPointerException();
    }

    public static void main(String[] args) {
        try {
            blowUp();
        } catch (BlewIt b) {
            System.out.println("Caught BlewIt");
        } finally {
            System.out.println("Uncaught Exception");
        }
    }
}
```



该程序产生输出：

```
Uncaught Exception
Exception in thread "main" java.lang.NullPointerException
at Test.blowUp(Test.java:7)
at Test.main(Test.java:11)
```

方法 `blowUp` 抛出的 `NullPointerException`（它是 `RuntimeException` 的一种）没有被 `main` 方法中的 `try` 语句捕获，因为 `NullPointerException` 无法赋值给 `Blewit` 类型的变量。这导致 `finally` 子句执行，随后执行的 `main` 方法（它是测试程序的唯一线程）因为一个未捕获的异常而终止，这通常会导致打印异常名称和简单的回溯轨迹。然而，本规范并不要求回溯轨迹。

创建回溯轨迹的问题在于，异常可以在程序的某处创建，并在另一处被抛出。在异常中存储堆栈轨迹是非常昂贵的，除非它实际上被抛出（此时可以在回溯栈时生成）。我们并不强制要求每个异常都包含堆栈轨迹。

一个独立表达式（§15.2）。局部变量的类型是 $\tau$ 相对于 $\tau$ 中提到的所有合成类型变量的向上投影（§4.10.5）。

如果 $r$ 是空类型，则为编译错误。

在资源规范中被声明或引用为资源的变量，其类型必须是 `AutoCloseable` 的子类型，否则将发生编译错误。

在资源规范中声明的变量的作用域和遮蔽在 §6.3 和 §6.4 中规定。

资源按照从左到右的顺序初始化。如果资源初始化失败（即其初始化器抛出异常），则 `try-with-resources` 语句到目前初始化的所有资源都将被关闭。如果所有资源都成功初始化，则 `try` 块按正常执行，然后 `try-with-resources` 的所有非空资源都将被关闭。

资源按照初始化的相反顺序进行关闭。只有当资源被初始化为非空值时，才会被关闭。关闭一个资源时抛出的异常不会阻止其它资源的关闭。如果之前由初始化器、`try` 块或资源的关闭抛出了异常，则该异常将被抑制（suppressed）。

资源规范指示多个资源的 `try-with-resources` 语句被处理为多个 `try-with-resources` 语句，每个语句都有一个指示单个资源的资源规范。当具有 $n$ 个资源（$n > 1$）的 `try-with-resources` 语句被翻译时，结果是一个具有 $n-1$ 个资源的 `try-with-resources` 语句。在经过 $n$ 次翻译后，会有 $n$ 个嵌套的 `try-catch-finally` 语句，整体翻译完成。

## 14.20.3.1 基础 try-with-resources

没有 `catch` 子句或 `finally` 子句的 `try-with-resources` 语句被称为基础 `try-with-resource` 语句。

如果一个基础 `try-with-resource` 语句的形式如下：

```
try (VariableAccess ...)

Block
```

则通过以下翻译，将资源首先转换为局部变量声明：

```
try (T #r = VariableAccess ...) {

Block

}
```

$\tau$ 是由 `VariableAccess` 表示的变量类型，#r 是一个自动生成的标识符，它与 `try-with-resources` 语句发生时作用域内的任何其他标识符（自动生成的或其他）都不同。然后根据本节的其余部分翻译 `try-with-resources` 语句。

基础 `try-with-resources` 语句的含义如下：

```
try ((VariableModifier) R Identifier = Expression ...)

    Block
```

由以下翻译为局部变量声明和 `try-catch-finally` 语句给出：

```
{

    final {VariableModifierNoFinal} R Identifier = Expression;

    Throwable #primaryExc = null;

    try ResourceSpecification_tail

        Block

    catch (Throwable #t) {

        #primaryExc = #t;

        throw #t;

    }

    {

        if (Identifier != null) {

            if (#primaryExc != null) {

                try {

                    Identifier.close();

                } catch (Throwable #suppressedExc) {

                    #primaryExc.addSuppressed(#suppressedExc);

                }

            } else {

                Identifier.close();

            }

        }

    }

}
```

如果存在 `final`，则 `VariableModifierNoFinal` 定义为不带 `final` 的 `VariableModifier`。

#t、#primaryExc 和 #suppressedExc 是自动生成的标识符，它们与 `try-with-resources` 语句发生时作用域内的任何其他标识符（自动生成的或其他）都不同。

如果资源规范指示一个资源，则 `ResourceSpecification_tail` 为空（且 `try-catch-finally` 语句本身不是一个 `try-with-resources` 语句）。

485

如果资源规范指示 $n > 1$ 个资源，则 `ResourceSpecification_tail` 由资源规范中指示的第 2、第 3、...到第 $n$ 个资源组成，顺序相同（`try-catch-finally` 语句本身是一个 `try-with-resources` 语句）。

基础 `try-with-resources` 语句的到达性性和定义赋值规则由上述翻译隐式规定。

在管理单个资源的基础 `try-with-resources` 语句中：

- 如果资源的初始化因为抛出值 $v$ 而异常终止，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止。
- 如果资源的初始化正常完成，且 `block` 块因为抛出值 $V$ 而异常终止，那么：
  - 资源的自动关闭正常完成，然后 `try-with-resources` 语句因为抛出值 $V$ 而异常终止。
  - 资源的自动关闭因为抛出值 $V_2$ 而异常终止，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止，并将 $V_2$ 添加到 $V$ 的抑制异常列表中。
- 资源的初始化正常完成，且资源的自动关闭因为抛出值 $V$ 而异常终止，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止。

在管理多个资源的基础 `try-with-resources` 语句中：

- 如果资源的初始化因为抛出值 $V$ 而异常终止，那么：
  - 所有成功初始化的资源（可能为零）的自动关闭正常完成，然后 `try-with-resources` 语句因为抛出值 $V$ 而异常终止。
  - 所有成功初始化的资源（可能为零）的自动关闭因为抛出值 $V_1...V_n$ 而异常终止，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止，并将剩余的值 $V_1...V_n$ 添加到 $V$ 的抑制异常列表中。

# 块与语句

# try 语句 14.20

- 如果所有资源的初始化都正常完成，且 `try` 块因为抛出值 $V$ 而异常终止，那么：
  - 如果所有初始化资源的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止。
  - 如果一个或多个初始化资源的自动关闭因为抛出值 $V_1...V_n$ 而异常终止，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止，并将剩余的值 $V_1...V_n$ 添加到 $V$ 的抑制异常列表中。
- 如果每个资源的初始化都正常完成，且 `try` 块正常完成，那么：
  - 如果某个已初始化资源的自动关闭因为抛出值 $V$ 而异常终止，随后所有初始化资源的关闭正常完成，则 `try-with-resources` 语句因为抛出值 $V$ 而异常终止。
  - 如果某个已初始化资源的自动关闭因为抛出值 $V_2...V_n$ 而异常终止，则 `try-with-resources` 语句因为抛出值 $V_1$ 而异常终止，并将 $V_2...V_n$ 添加到 $V_1$ 的抑制异常列表中（$V_1$ 是左侧资源关闭的异常，$V_n$ 是右侧资源关闭的异常）。

## 14.20.3.2 扩展 try-with-resources

带有至少一个 `catch` 子句和/或 `finally` 子句的 `try-with-resources` 语句被称为扩展 `try-with-resources` 语句。

扩展 `try-with-resources` 语句的含义：

```
try ResourceSpecification

  Block

[Catches]

[Finally]
```

由以下翻译为嵌套在 `try-catch` 或 `try-finally` 或 `try-catch-finally` 语句中的基础 `try-with-resources` 语句给出：

487

```
try {

    try ResourceSpecification

    Block

  }

  [Catches]

  [Finally]
```

该翻译的效果是将资源规范放在 `try` 语句内部。这使得扩展 `try-with-resources` 语句的 `catch` 子句能够捕捉由于自动初始化或关闭引起的异常。

此外，在执行 `finally` 块时，所有资源都已关闭（或尝试关闭），符合 `finally` 关键字的意图。

## 14.21 yield 语句

`yield` 语句通过导致的 switch 表达式（§15.28）产生特定值来传输控制。

YieldStatement:
yield Expression ;

`yield` 语句尝试传输控制到封装的 switch 表达式；该封装表达式（称为 yield 目标）立即正常完成，Expression 的值成为 switch 表达式的值。

如果 `yield` 语句没有 yield 目标，则为编译错误。

如果 yield 目标包含封装 `yield` 语句的方法、构造函数、实例初始化器、静态初始化器或 lambda 表达式，则为编译错误。也就是说，不存在非局部跳转。

如果 `yield` 语句的 Expression 是 `void`（§15.1），则为编译错误。`yield` 语句的执行首先求值 Expression。如果 Expression 的求值由于某种原因异常终止，则 `yield` 语句由于该原因异常终止。Expression 求值正常产生值 v，则 `yield` 语句异常终止，原因是值为 v 的 yield。

可见，`yield` 语句总是异常终止的。

# 示例 14.21-1. yield 语句

在下面的示例中，yield 语句用于为包含它的 switch 表达式产生一个值。

```java
class Test {

    enum Day {

        MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,

        SATURDAY, SUNDAY

    }

    public int calculate(Day d) {

        return switch (d) {

            case SATURDAY, SUNDAY -> d.ordinal();

            default -> {

                int len = d.toString().length();

                yield len*len;

            }

        };

    }

}
```

## 14.22 不可达语句

如果语句因为不可达而无法执行，则是一个编译错误。

本节专门对“可达（reachable）”一词进行精确解释。其核心是：从构造函数、方法、实例初始化器或静态初始化器的开始，必须存在某种可能的执行路径可以到达该语句本身。分析考虑了语句的结构。除了对条件表达式为常量 `true` 的 `while`、`do` 和 `for` 语句进行特殊处理外，在流分析中不考虑表达式的值。

例如，Java 编译器会接受以下代码：

```java
{
    int n = 5;
    while (n > 7) k = 2;
}
```



# 14.22 不可达语句

如果语句因为不可达而无法执行，则是一个编译错误。

本节专门对“可达（reachable）”一词进行精确解释。其核心是：从构造函数、方法、实例初始化器或静态初始化器的开始，必须存在某种可能的执行路径可以到达该语句本身。分析考虑了语句的结构。除了对条件表达式为常量 `true` 的 `while`、`do` 和 `for` 语句进行特殊处理外，在流分析中不考虑表达式的值。

例如，Java 编译器会接受以下代码：

```java
{
    int n = 5;
    while (n > 7) k = 2;
}
```

尽管 `n` 的值在编译时是已知的，且原则上可以在编译时确定对 `k` 的赋值永远不会执行。

本节的规则定义了两个技术术语：

- 语句是否可达的
- 语句是否可以正常完成

这里的定义规定，只有当语句是可达的时，它才能正常完成。

为了缩短规则的描述，使用了常用的缩写 "iff" 来表示“当且仅当（if and only if）”。

如果在 `break` 目标范围内，要么没有 `try` 块包含该 `break` 语句的 `try` 语句，要么存在 `try` 块包含该 `break` 语句的 `try` 语句，且这些 `try` 语句的所有 `finally` 子句都能正常完成，则一个可达的 `break` 语句可以退出该语句。

> 该定义基于 §14.15 中围绕“尝试转移控制权”的逻辑。

如果在 `do` 语句范围内，要么没有 `try` 块包含该 `continue` 语句的 `try` 语句，要么存在 `try` 块包含该 `continue` 语句的 `try` 语句，且这些 `try` 语句的 `finally` 子句都能正常完成，则 `continue` 语句可以完成该语句。

规则如下：

- 作为构造函数、方法、实例初始化器、静态初始化器、`lambda` 表达式或 `switch` 表达式体的块是可达的。
- 非 `switch` 块的空块当且仅当它是可达的时，是可以正常完成的。
- 非 `switch` 块的非空块当且仅当其最后一个语句可以正常完成时，是可以正常完成的。
- 非 `switch` 块的非空块中的第一个语句当且仅当该块是可达的时，是可达的。
- 非 `switch` 块的非空块中的其他任何语句 `s` 当且仅当 `s` 前的语句可以正常完成时，是可达的。
- 局部类声明语句当且仅当它是可达的时，是可以正常完成的。
- 局部变量声明语句当且仅当它是可达的时，是可以正常完成的。
- 空语句当且仅当它是可达的时，是可以正常完成的。
- 如果满足以下至少一个条件，则标签语句可以正常完成：
  - 包含的语句可以正常完成。
  - 存在一个退出该标签语句的可达 `break` 语句。
- 包含的语句当且仅当标签语句是可达的时，是可达的。
- 表达式语句当且仅当它是可达的时，是可以正常完成的。
- `if-then` 语句当且仅当它是可达的时，是可以正常完成的。
- `then` 语句当且仅当 `then` 语句是可达的时，是可达的。
- `if-then-else` 语句当且仅当 `then` 语句可以正常完成或 `else` 语句可以正常完成时，是可以正常完成的。
- `then` 语句当且仅当 `if-then-else` 语句是可达的时，是可达的。
- `else` 语句当且仅当 `if-then-else` 语句是可达的时，是可达的。

这种对 `if` 语句的处理（无论它是否有 `else` 部分）是相当不寻常的。理由在本节的末尾。

- `assert` 语句当且仅当它是可达的时，是可以正常完成的。
- `switch` 块为空或仅包含 `switch` 标签的 `switch` 语句是可以正常完成的。
- `switch` 块由 `switch` 标签语句组组成的 `switch` 语句，如果满足以下至少一个条件时，是可以正常完成的：
  - `switch` 块中的最后一个语句可以正常完成。
  - 在最后一个 `switch` 块语句组之后至少存在一个 `switch` 标签。
  - `switch` 块不包含 `default` 标签。
  - 存在一个退出该 `switch` 语句的可达 `break` 语句。
- `switch` 块由 `switch` 规则组成的 `switch` 语句，当且仅当满足以下至少一个条件时，是可以正常完成的：
  - 其中一个 `switch` 规则引入了 `switch` 规则表达式（该表达式必然是一个语句表达式）。
  - 其中一个 `switch` 规则引入了可以正常完成的 `switch` 规则块。
  - 其中一个 `switch` 规则引入了包含退出该 `switch` 语句的可达 `break` 语句的 `switch` 规则块。
- `switch` 块当且仅当其 `switch` 语句是可达的时，是可达的。

`switch` 块中由 `switch` 标签语句组组成的语句当且仅当 `switch` 块可达且满足以下至少一个条件时，是可达的：

  - 它带有 `case` 或 `default` 标签。
  - `switch` 块中存在其之前的语句，且该之前的语句可以正常完成。

- `switch` 块中的 `switch` 规则块当且仅当 `switch` 块是可达的时，是可达的。
- `switch` 块中的 `switch throw` 语句当且仅当块是可达的时，是可达的。
- 如果满足以下至少一个条件，则 `while` 语句可以正常完成：
  - `while` 语句是可达的，且条件表达式不是值为 `true` 的常量表达式 (§15.29)。
  - 存在一个退出该 `while` 语句的可达 `break` 语句。
- 包含的语句当且仅当 `while` 语句是可达的且条件表达式不是值为 `false` 的常量表达式时，是可达的。
- 如果满足以下至少一个条件，则 `do` 语句可以正常完成：
  - 包含的语句可以正常完成且条件表达式不是值为 `true` 的常量表达式 (§15.29)。
  - `do` 语句包含一个无标签的可达 `continue` 语句，且该 `do` 语句是包含该 `continue` 语句的最内 `while` 或 `for` 语句，且该 `continue` 语句继续该 `do`，且条件表达式不是值为 `true` 的常量表达式。
  - `do` 语句包含一个带有标签 L 的可达 `continue` 语句，且该 `do` 语句带有标签 L，且该 `continue` 语句继续该 `do`，且条件表达式不是值为 `true` 的常量表达式。
  - 存在一个退出该 `do` 语句的可达 `break` 语句。
- 包含的语句当且仅当 `do` 语句是可达的时，是可达的。
- 如果满足以下至少一个条件，则基本 `for` 语句可以正常完成：
  - `for` 语句是可达的，存在条件表达式，且条件表达式不是值为 `true` 的常量表达式 (§15.29)。
  - 存在一个退出该 `for` 语句的可达 `break` 语句。
- 包含的语句当且仅当 `for` 语句是可达的且条件表达式不是值为 `false` 的常量表达式时，是可达的。
- 增强 `for` 语句当且仅当它是可达的时，是可以正常完成的。
- `break`、`continue`、`return`、`throw` 或 `yield` 语句无法正常完成。
- `synchronized` 语句当且仅当包含的语句可以正常完成时，是可以正常完成的。
- 包含的语句当且仅当 `synchronized` 语句是可达的时，是可达的。
- `try` 语句当且仅当满足以下两个条件时，是可以正常完成的：
  - `try` 块可以正常完成或任何 `catch` 块可以正常完成。
  - 如果 `try` 语句有 `finally` 块，则 `finally` 块可以正常完成。
- `try` 块当且仅当 `try` 语句是可达的时，是可达的。
- `catch` 块 `c` 当且仅当满足以下两个条件时，是可达的：
  - `c` 参数的类型是未检查的异常、`Exception` 或 `Exception` 的超类，或者 `try` 块中的某些表达式或 `throw` 语句是可达的且可以抛出值与 `c` 参数类型赋值兼容 (§5.2) 的异常。（表达式是可达的当且仅当包含它的最内层语句是可达的。）参见 §15.6 关于表达式的正常完成和异常完成。
  - `try` 语句中不存在更早的 `catch` 块 `A`，其 `c` 参数的类型与 `A` 参数的类型相同或是 `A` 参数类型的子类。
- `catch` 块的体当且仅当 `catch` 块是可达的时，是可达的。
- 如果存在 `finally` 块，它当且仅当 `try` 语句是可达的时，是可达的。

人们可能期望 `if` 语句按以下方式处理：

# 示例 14.21-1. `yield` 语句

在下面的示例中，`yield` 语句用于为包含它的 `switch` 表达式产生一个值。

```java
class Test {

    enum Day {

        MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,
        SATURDAY, SUNDAY
    }

    public int calculate(Day d) {

        return switch (d) {
            case SATURDAY, SUNDAY -> d.ordinal();
            default -> {
                int len = d.toString().length();
                yield len * len;
            }
        };
    }
}
```



尽管 `n` 的值在编译时是已知的，且原则上可以在编译时确定对 `k` 的赋值永远不会执行。

本节的规则定义了两个技术术语：

- 语句是否可达的
- 语句是否可以正常完成

这里的定义规定，只有当语句是可达的时，它才能正常完成。

为了缩短规则的描述，使用了常用的缩写 "iff" 来表示“当且仅当（if and only if）”。

如果在 `break` 目标范围内，要么没有 `try` 块包含该 `break` 语句的 `try` 语句，要么存在 `try` 块包含该 `break` 语句的 `try` 语句，且这些 `try` 语句的所有 `finally` 子句都能正常完成，则一个可达的 `break` 语句可以退出该语句。

> 该定义基于 §14.15 中围绕“尝试转移控制权”的逻辑。

如果在 `do` 语句范围内，要么没有 `try` 块包含该 `continue` 语句的 `try` 语句，要么存在 `try` 块包含该 `continue` 语句的 `try` 语句，且这些 `try` 语句的 `finally` 子句都能正常完成，则 `continue` 语句可以完成该语句。

规则如下：

- 作为构造函数、方法、实例初始化器、静态初始化器、lambda 表达式或 switch 表达式体的块是可达的。
- 非 switch 块的空块当且仅当它是可达的时，是可以正常完成的。
- 非 switch 块的非空块当且仅当其最后一个语句可以正常完成时，是可以正常完成的。
- 非 switch 块的非空块中的第一个语句当且仅当该块是可达的时，是可达的。
- 非 switch 块的非空块中的其他任何语句 `s` 当且仅当 `s` 前的语句可以正常完成时，是可达的。
- 局部类声明语句当且仅当它是可达的时，是可以正常完成的。
- 局部变量声明语句当且仅当它是可达的时，是可以正常完成的。
- 空语句当且仅当它是可达的时，是可以正常完成的。
- 如果满足以下至少一个条件，则标签语句可以正常完成：
  - 包含的语句可以正常完成。
  - 存在一个退出该标签语句的可达 `break` 语句。
- 包含的语句当且仅当标签语句是可达的时，是可达的。
- 表达式语句当且仅当它是可达的时，是可以正常完成的。
- if-then 语句当且仅当它是可达的时，是可以正常完成的。
- then-语句当且仅当 then-语句是可达的时，是可达的。
- if-then-else 语句当且仅当 then-语句可以正常完成或 else-语句可以正常完成时，是可以正常完成的。
- then-语句当且仅当 if-then-else 语句是可达的时，是可达的。
- else-语句当且仅当 if-then-else 语句是可达的时，是可达的。

这种对 if 语句的处理（无论它是否有 else 部分）是相当不寻常的。理由在本节的末尾。

- assert 语句当且仅当它是可达的时，是可以正常完成的。
- switch 块为空或仅包含 switch 标签的 switch 语句是可以正常完成的。
- switch 块由 switch 标签语句组组成的 switch 语句，如果满足以下至少一个条件时，是可以正常完成的：
  - switch 块中的最后一个语句可以正常完成。
  - 在最后一个 switch 块语句组之后至少存在一个 switch 标签。
  - switch 块不包含 default 标签。
  - 存在一个退出该 switch 语句的可达 `break` 语句。
- switch 块由 switch 规则组成的 switch 语句，当且仅当满足以下至少一个条件时，是可以正常完成的：
  - 其中一个 switch 规则引入了 switch 规则表达式（该表达式必然是一个语句表达式）。
  - 其中一个 switch 规则引入了可以正常完成的 switch 规则块。
  - 其中一个 switch 规则引入了包含退出该 switch 语句的可达 `break` 语句的 switch 规则块。
- switch 块当且仅其 switch 语句是可达的时，是可达的。

switch 块中由 switch 标签语句组组成的语句当且仅当 switch 块可达且满足以下至少一个条件时，是可达的：

  - 它带有 case 或 default 标签。
  - switch 块中存在其之前的语句，且该之前的语句可以正常完成。

- switch 块中的 switch 规则块当且仅当 switch 块是可达的时，是可达的。
- switch 块中的 switch throw 语句当且仅当块是可达的时，是可达的。
- 如果满足以下至少一个条件，则 while 语句可以正常完成：
  - while 语句是可达的，且条件表达式不是值为 `true` 的常量表达式（§15.29）。
  - 存在一个退出该 while 语句的可达 `break` 语句。
- 包含的语句当且仅当 while 语句是可达的且条件表达式不是值为 `false` 的常量表达式时，是可达的。
- 如果满足以下至少一个条件，则 do 语句可以正常完成：
  - 包含的语句可以正常完成且条件表达式不是值为 `true` 的常量表达式（§15.29）。
  - do 语句包含一个无标签的可达 `continue` 语句，且该 do 语句是包含该 `continue` 语句的最内 while 或 for 语句，且该 `continue` 语句继续该 do，且条件表达式不是值为 `true` 的常量表达式。
  - do 语句包含一个带有标签 L 的可达 `continue` 语句，且该 do 语句带有标签 L，且该 `continue` 语句继续该 do，且条件表达式不是值为 `true` 的常量表达式。
  - 存在一个退出该 do 语句的可达 `break` 语句。
- 包含的语句当且仅当 do 语句是可达的时，是可达的。
- 如果满足以下至少一个条件，则基本 for 语句可以正常完成：
  - for 语句是可达的，存在条件表达式，且条件表达式不是值为 `true` 的常量表达式（§15.29）。
  - 存在一个退出该 for 语句的可达 `break` 语句。
- 包含的语句当且仅当 for 语句是可达的且条件表达式不是值为 `false` 的常量表达式时，是可达的。
- 增强 for 语句当且仅当它是可达的时，是可以正常完成的。
- `break`、`continue`、`return`、`throw` 或 `yield` 语句无法正常完成。
- synchronized 语句当且仅当包含的语句可以正常完成时，是可以正常完成的。
- 包含的语句当且仅当 synchronized 语句是可达的时，是可达的。
- try 语句当且仅当满足以下两个条件时，是可以正常完成的：
  - try 块可以正常完成或任何 catch 块可以正常完成。
  - 如果 try 语句有 finally 块，则 finally 块可以正常完成。
- try 块当且仅当 try 语句是可达的时，是可达的。
- catch 块 c 当且仅当满足以下两个条件时，是可达的：
  - c 参数的类型是未检查的异常、Exception 或 Exception 的超类，或者 try 块中的某些表达式或 throw 语句是可达的且可以抛出值与 c 参数类型赋值兼容（§5.2）的异常。（表达式是可达的当且仅当包含它的最内层语句是可达的。）参见 §15.6 关于表达式的正常完成和异常完成。
  - try 语句中不存在更早的 catch 块 A，其 c 参数的类型与 A 参数的类型相同或是 A 参数类型的子类。
- catch 块的体当且仅当 catch 块是可达的时，是可达的。
- 如果存在 finally 块，它当且仅当 try 语句是可达的时，是可达的。

人们可能期望 if 语句按以下方式处理：

# 第15 章
## 表达式

程序中的大部分工作通过求值表达式完成，可能是为了它们的副作用（例如给变量赋值），也为了它们的值（这些值可以作为较大表达式中的操作数，或影响语句的执行顺序，或者两者兼有）。本章规定了表达式的含义及其求值规则。

### 15.1 求值、记法与结果

当程序中的表达式被求值时，结果表示以下三者之一：

- 一个变量（§4.1）（在 C 中，这被称为 lvalue）
- 一个值（§4.2, §4.3）
- 无（该表达式被认为是 void）

如果表达式表示一个变量，且后续求值需要一个值，则使用该变量的值。在这种语境下，如果表达式表示一个值，我们可以简单地说表达式的值。值转换（§5.1）应用于每一个产生值的表达式的结果，包括使用类型 float 或 double 类型的值时。

一个表达式表示为“无”，当且仅当它是一个方法调用（§15.2），且该调用触发了一个不返回值的方法，即声明为 void 的方法（§8.4）。此类表达式只能用作表达式语句（§14.8）或 lambda 体中的唯一表达式（§15.2.2），因为表达式可能出现的任何其他语境都要求该表达式表示某些内容。作为方法调用的表达式语句或 lambda 体也可以调用一个产生结果的方法；在这种情况下，方法返回的值会被静默地丢弃。

表达式的求值可能会产生副作用，因为表达式可能包含嵌入的赋值、递增运算符、递减运算符、方法调用，以及在 switch 表达式中的任意语句。

表达式出现在以下位置之一：

- 正在声明的某个（类或接口）类型的声明：在字段初始化器中、静态初始化器中、实例化器中、构造函数声明中、方法声明中或注解中。
- 包声明或顶层类型声明上的注解。

### 15.2 表达式的形式

表达式可以大致归类为以下语法形式之一：

- 表达式名（§6.5.6）
- 初级表达式（§15.8 - §15.13）
- 一元运算符表达式（§15.14 - §15.16）
- 二元运算符表达式（§15.17 - §15.24, 以及 §15.26）
- 三元运算符表达式（§15.25）
- Lambda 表达式（§15.27）
- switch 表达式（§15.28）

运算符之间的优先级通过语法产生式的层次结构进行管理。最低优先运算符是 lambda 表达式的箭头 `->`，随后是赋值运算符。因此，所有表达式在语法上都包含 `LambdaExpression` 和 `AssignmentExpression` 非终端中：

```
Expression:
LambdaExpression
AssignmentExpression
```

当某些表达式出现在特定的语境中时，它们被视为多值表达式（poly expressions）。以下形式的表达式可能是多值表达式：

- 括号表达式（§15.8.5）
- 类实例创建表达式（§15.9）
- 方法调用表达式（§15.12）
- 方法引用表达式（§15.13）
- 条件表达式（§15.25）
- Lambda 表达式（§15.27）
- switch 表达式（§15.28）

决定这些形式之一的表达式是否为多值表达式的规则，给出在指定这些表达式形式的各个章节中。

不是多值表达式的表达式是独立表达式（standalone expressions）。独立表达式是指在被确定为不是多值表达式时上述形式的表达式，以及所有其他形式的表达式。所有其他形式的表达式被称为具有独立形式。

### 15.3 表达式的类型

如果至少满足以下一个条件，则 if-then 语句可以正常完成：

- if-then 语句是可达的，且条件表达式不是一个值为 true 的常量表达式。
- then-语句可以正常完成。

if-else 语句是可达的，当且仅当 if-then 语句是可达的且条件表达式不是一个值为 false 的常量表达式。
如果 then-语句可以正常完成或 else-语句可以正常完成，则 if-else 语句可以正常完成。

then-else 语句是可达的，当且仅当 if-else 语句可达的且条件表达式不是一个值为 false 的常量表达式。
else-else 语句是可达的，当且仅当 if-then-else 语句可达的且条件表达式不是一个值为 true 的常量表达式。

这种方法与其他控制结构保持一致。然而，为了方便地将 if 语句用于“条件编译”，实际规则有所不同。

例如，以下语句会导致编译时错误：

```
while (false) { x=3; }
```

因为语句 `x=3;` 是不可达的；但表面上相似的案例

```
if (false) { x=3; }
```

并没有导致编译时错误。优化编译器可能会意识到语句 `x=3;` 永远不会执行，并可能选择从生成的类文件中省略该语句的代码，但在此处指定的特定意义上，语句 `x=3;` 不被视为“不可达”。

这种差异化处理的理由是允许程序员定义类似“标志”变量，例如：

```java
static final boolean DEBUG = false;
```

然后编写如下代码：

```java
if (DEBUG) { x=3; }
```

其意图是可以在不更改程序文本的情况下，将 DEBUG 的值从 false 改为 true 或反之进行编译。

条件编译有一个注意事项。如果一组使用“标志”变量——更准确地说，任何常量变量（§4.12）——的类被编译并省略，仅仅分发包含该标志定义的类版本是不够的。使用标志的类将看不到它的新值，因此它们的行为是意外的。

另一个“内联”常量变量值的原因是 switch 语句。它们是唯一依赖表达式的语句，switch 语句的每个 case 标签必须是与其他值不同的常量表达式。如果在编译时证明没有重复标签，将值内联到类文件中可以确保运行时没有重复标签——这是一个良好的属性。

### 1. 条件编译

如果：

```java
class Flags { static final boolean DEBUG = true; }

class Test {

    public static void main(String[] args) {

        if (Flags.DEBUG) {

            System.out.println("DEBUG");

        }

    }

}
```

编译并执行，它输出：

```
DEBUG
```

假设产生了类 Flags的新版本：

```java
class Flags { static final boolean DEBUG = false; }

class Test {

    public static void main(String[] args) {

        if (Flags.DEBUG) {

            System.out.println("DEBUG");

        }

    }

}
```

这种行为发生在 Flags 是接口时，在修改后的示例中：

```java
interface Flags {

    boolean DEBUG = true;

}
```

事实上，因为接口的字段并不总是静态且最终的，我们注意到但不建议，如果原始类型字段可能会发生变化，其值可以用惯用方式表示为：

```java
interface Flags {

    boolean debug = Boolean.valueOf(true).booleanValue();

}
```



确保该值不是常量表达式。对于其他类型存在类似的惯用方法。

# 不可达语句

# 块与语句

请注意，一个类型声明为 `final` 的类类型 `f` 的表达式，其值保证要么是一个空引用，要么是一个类本身为 `f` 的对象，因为 `final` 类型没有子类。

## 15.4 FP-严格表达式

如果表达式的类型为 `float` 或 `double`，那么关于表达式的值取自哪个值集 {§4.2.23} 就存在疑问。这受值集转换规则 (§5.1.13) 的支配；这些规则取决于该表达式是否为 `FP`-严格。

每个常量表达式 (§15.29) 都是 `FP`-严格的。

如果一个表达式不是常量表达式，则考虑包含该表达式的所有类声明、接口声明和方法声明。如果 `any` 这样的声明带有 `strictfp` 修饰符 (§8.1.1.3, §8.4.3.5, §9.1.1.2)，则该表达式是 `FP`-严格的。

如果一个类、接口或方法 `x` 被声明为 `strictfp`，则 `x` 以及 `x` 内部的任何类、接口、方法、构造函数、实例初始化器、静态初始化器或变量都被认为是 `FP`-严格的。

> 注意，注解的元素值 (§9.7) 始终是 `FP`-严格的，因为它始终是一个常量表达式。

因此，一个表达式不是 `FP`-严格的当且仅当它不是常量表达式，且没有出现在任何带有 `strictfp` 修饰符的声明中。

在 `FP`-严格表达式内部，所有中间值必须是 `float` 值集或 `double` 值集的元素，这意味着所有 `FP`-严格表达式的结果必须通过对单精度和双精度格式的操作数的 IEEE 754 算术来预测。

在非 `FP`-严格的表达式内部，允许实现具有灵活性，可以使用扩展的指数范围来表示中间结果；粗略来说，其结果是在仅使用 `float` 值集或 `double` 值集可能导致溢出或下溢的情况下，计算可能会产生“正确答案”。

## 15.5 表达式与运行时检查

如果表达式的类型是原始类型，则表达式的值是该原始类型。

如果表达式的类型是引用类型，那么被引用对象的类，甚至该值是引用对象的引用还是空引用，在编译时并不一定已知。在 Java 语言中，有少数地方被引用对象的实际类会以一种无法从表达式类型推出的方式影响程序执行。它们如下：

- 方法调用 (§15.12)。用于调用 `o.m(...)` 的特定方法是根据 `o` 的类型的类或接口中的方法来选择的。对于实例方法，`o` 的运行时值所引用的对象的类参与了其中，因为子类可能会重写父类中已声明的特定方法，从而调用该重写方法。（重写的方法可能选择不选择进一步调用原始方法。）

- `instanceof` 运算符 (§15.20.2)。类型为引用类型的表达式可以使用 `instanceof` 进行测试，以找到表达式运行时值引用的对象的类，或者转换为其他引用类型。

- 强制转换 (§15.16)。操作数表达式运行时值引用的对象的类可能与强制转换符指定的类型不兼容。对于引用类型，这可能需要运行时检查，如果在运行时确定的被引用对象类无法转换为目标类型，则抛出异常。

- 对引用类型数组组件的赋值 (§10.5, §15.13, §15.26.1)。类型检查规则允许如果 `s` 是 `t` 的子类型，则将类型 `s[]` 视为 `t[]` 的子类型，但对数组组件的赋值需要运行时检查，类似于为强制转换执行检查。

- 异常处理 (§14.20)。只有当抛出的异常对象的类是 catch 句中形式参数的 `instanceof` 类型时，异常才会被 catch 句捕获。

对象的类不是静态已知的情况会导致运行时错误。

此外，还存在静态已知类型在运行时可能不准确的情况。这种情况可能出现在产生编译未检查警告的程序中。这些警告针对无法在静态上保证安全的的操作，并且由于它们涉及不可重化类型 (§4.7)，无法立即进行动态检查。因此，在程序执行过程后期的动态检查可能会检测到不一致性并导致运行时错误。

运行时错误只会在以下情况下发生：

- 在一种情况下，操作数表达式值引用的对象的实际类与强制转换符指定的目标类型不兼容 (§5.5, §15.16)；在这种情况下将抛出 `ClassCastException`。

- 在为了确保对不可重化类型的操作的有效性而引入的分析生成的强制转换中 (§4.7)。

- 在引用类型数组组件的赋值中，值引用的对象的实际类与数组的实际运行时组件类型不兼容 (§10.5, §15.13, §15.26.1)；在这种情况下将抛出 `ArrayStoreException`。

- 当异常未被 try 语句的 catch 句捕获时 (§14.20)；第一个遇到异常的控制线程终止。

## 15.6 求值的正常完成与异常完成

每个表达式都有一个求值模式，其中会执行某些步骤。如果所有步骤都执行且没有抛出异常，则该表达式为正常完成。然而，如果表达式求值抛出了异常，则该表达式为异常完成。异常完成总有一个相关的原因，该原因总是带有给定值的抛出。预定义运算符抛出运行时异常如下：

- 类实例创建表达式 (§15.9)、数组创建表达式 (§10.2)、方法引用表达式 (§15.13)、数组初始化表达式 (§10.6)、字符串连接运算符 (§15.18) 或 lambda 表达式 (§27.4) 如果可用内存不足，将抛出 `OutOfMemoryError`。

- 数组创建表达式 (§10.2) 如果任何维度表达式的值小于零，则抛出 `NegativeArraySizeException`。

- 数组访问表达式 (§15.10.4) 如果数组引值为空，则抛出 `NullPointerException`。

- 数组访问表达式 (§15.10.4) 如果数组索引为负或大于或等于数组长度，则抛出 `ArrayIndexOutOfBoundsException`。

- 字段访问表达式 (§15.11) 如果对象引值为空，则抛出 `NullPointerException`。

- 方法调用 (§15.12) 如果目标引用为空，则抛出 `NullPointerException`。

- 强制转换表达式 (§15.16) 如果在运行时发现强制转换不当，则抛出 `ClassCastException`。

- 整数除法 (§15.17.2) 或整数取模 (§15.17.3) 运算符如果右操作数表达式的值为零，则抛出 `ArithmeticException`。

- 引用类型数组组件的赋值 (§15.26.1)、方法调用表达式 (§15.12) 或前置或后置自增 (§15.14.3, §15.15.2) 可能由于装箱转换 (§15.7) 而抛出 `OutOfMemoryError`。

- 引用类型数组组件的赋值 (§15.26.1) 当要赋值的值与数组的组件类型不兼容时，抛出 `ArrayStoreException`。

- switch 表达式 (§15.28) 如果没有 switch 匹配选择表达式的值，则抛出 `IncompatibleClassChangeError`。

如果执行方法体时抛出了异常，则方法调用也可能导致抛出异常。

如果执行构造函数时抛出了异常，则类实例创建表达式也可能导致抛出异常。

在求值过程中还可能发生各种链接错误和虚拟机错误。根据其性质，此类错误难以预测且难以处理。

如果发生异常，则一个或多个表达式的评估可能会在它们正常模式评估的所有步骤完成之前终止；此类表达式被称为“异常完成（complete abruptly）”。

如果对表达式的评估需要对一个子表达式进行评估，那么子表达式的异常完成总是会导致表达式本身的异常完成，且具有相同的原因，并且正常模式评估中的所有后续步骤将不会被执行。

“正常完成（complete normally）”和“异常完成（complete abruptly）”术语也适用于语句的执行（§14.1）。语句可能因为多种原因导致异常完成，而不仅仅是因为抛出了异常。

## 15.7 评估顺序

Java 编程语言保证操作符的操作数似乎是按照特定的评估顺序进行评估的，即从左到右。

> 建议代码不要关键性依赖此规范。当每个表达式最多包含一个作为最外层操作的副作用时，代码通常更清晰；且当代码不依赖于表达式从左到右评估的结果具体会产生哪种异常时。

### 15.7.1 先评估左操作数

二元运算符的左操作数似乎在右操作数的任何部分被评估之前就已经被完全评估。

如果该运算符是复合赋值运算符（§15.26.2），则对左操作数的评估包括：记住左操作数所指代的内容，以及获取并保存该变量的值以用于隐含的二元操作。

如果二元运算符的左操作数异常完成，则右操作数的任何部分似乎未被评估过。

#### 示例 15.7.1-1. 先评估左操作数

在下面的代码中，`*` 运算符的左操作数包含一个对变量的赋值，而右操作数包含一个对该变量的引用。引用产生的值将反映出赋值先发生的事实。

```java
class Test1 {
    public static void main(String[] args) {
        int i = 2;
        int j = (i=3) * i;
        System.out.println(j);
    }
}
```

该程序产生输出：

9

不允许对 `*` 运算符的评估产生 6 而不是 9。

#### 示例 15.7.1-2. 复合赋值运算符中的隐式左操作数

在下面的程序中，两个赋值语句在加法运算符的右操作数被评估之前，都获取并记了左操作数的值（即 9），此时该变量被设置为 3。

```java
class Test2 {
    public static void main(String[] args) {
        int a = 9;
        a += (a = 3); // 第一个示例
        System.out.println(a);
        int b = 9;
        b = b + (b = 3); // 第二个示例
        System.out.println(b);
    }
}
```

该程序产生输出：

12
12

不允许任何一个赋值（`a` 的复合赋值，`b` 的简单赋值）产生结果 6。

见 §15.26.2 中的示例。

#### 示例 15.7.1-3. 左操作数评估的异常完成

```java
class Test3 {
    public static void main(String[] args) {
        int j = 1;
        try {
            int i = forgetIt() / (j = 2);
        } catch (Exception e) {
            System.out.println(e);
            System.out.println("Now j = " + j);
        }
    }
    static int forgetIt() throws Exception {
        throw new Exception("I'm outta here!");
    }
}
```

该程序产生输出：

```
java.lang.Exception: I'm outta here!
Now j = 1
```

也就是说，运算符 `/` 的左操作数 `forgetIt()` 在右操作数被评估以及其嵌入的对 `j` 赋值 2 之前抛出了异常。

### 15.7.2 在操作之前评估操作数

Java 编程语言保证运算符的每个操作数（条件运算符 `&&`、`||` 和 `?:` 除外）在运算符的任何部分执行之前被完全评估。

如果二元运算符是整数除法 `/` (§15.17.2) 或整数取模 `%` (§15.17.3)，其执行可能会抛出 `ArithmeticException`，但该异常仅在二元运算符的两个操作数都已完成评估且仅在这些评估正常完成的情况下才会抛出。

#### 示例 15.7.2-1. 操作之前的操作数评估

```java
class Test {
    public static void main(String[] args) {
        int divisor = 0;
        try {
            int i = 1 / (divisor * loseBig());
        } catch (Exception e) {
            System.out.println(e);
        }
    }
    static int loseBig() throws Exception {
        throw new Exception("Shuffle off!");
    }
}
```

该程序产生输出：

```
java.lang.Exception: Shuffle off!
```

而不是：

```
java.lang.ArithmeticException: / by zero
```

因为除法操作在 `loseBig()` 调用之前就先发生了除以零异常。

### 15.7.3 评估遵循括号和优先级

Java 编程语言显式地遵循括号，隐式地遵循运算符优先级。

在浮点计算的情况下，此规则也适用于 `infinity` 和 `NaN`。具体而言，例如测试程序：

```java
strictfp class Test {
    public static void main(String[] args) {
        double d = 8e37;
        System.out.println(4.0 * d * 0.5);
        System.out.println(2.0 * d);
    }
}
```

打印结果：

Infinity
1.6e38

因为第一个表达式溢出了，而第二个没有。

### 15.7.4 参数列表从左到右评估

在方法调用、构造函数调用或类实例创建中，参数表达式出现在括号内，并用逗号分隔。每个参数表达式在其右侧的任何参数表达式之前都已被完全评估。

如果一个参数表达式的评估异常完成，则其右侧的任何参数表达式似乎未被评估过。

#### 示例 15.7.4-1. 方法调用时的评估顺序

```java
class Test1 {
    public static void main(String[] args) {
        String s = "going";
        print3(s, s, s = "gone");
    }
    public static void print3(String a, String b, String c) {
        System.out.println(a + b + c);
    }
}
```

该程序产生输出：

going, going, gone

因为对 `s` 赋值 "gone" 发生在 `print3` 的前两个参数被评估之后。

#### 示例 15.7.4-2. 参数表达式的异常完成

```java
class Test2 {
    static int id;
    public static void main(String[] args) {
        try {
            test(id = 1, oops(), id = 3);
        } catch (Exception e) {
            System.out.println(e + " id=" + id);
        }
    }
    static int test(int a, int b, int c) {
        return 0;
    }
    static int oops() throws Exception {
        throw new Exception("oops");
    }
}
```

该程序产生输出：

java.lang.Exception: oops id=1



System.out.println(j);

}

}

```

该程序产生输出：

9

不允许对 `*` 运算符的评估产生 6 而不是 9。

#### 示例 15.7.1-2. 复合赋值运算符中的隐式左操作数

在下面的程序中，两个赋值语句在加法运算符的右操作数被评估之前，都获取并记了左操作数的值（即 9），此时该变量被设置为 3。

```java
class Test2 {

    public static void main(String[] args) {

        int a = 9;

        a += (a = 3); // 第一个示例

        System.out.println(a);

        int b = 9;

        b = b + (b = 3); // 第二个示例

        System.out.println(b);

    }

}
```

该程序产生输出：

12
12

不允许任何一个赋值（a 的复合赋值，b 的简单赋值）产生结果 6。

见 §15.26.2 中的示例。

#### 示例 15.7.1-3. 左操作数评估的异常完成

```java
class Test3 {

    public static void main(String[] args) {

        int j = 1;

        try {

            int i = forgetIt() / (j = 2);

        } catch (Exception e) {

            System.out.println(e);

            System.out.println("Now j = " + j);

        }

    }

    static int forgetIt() throws Exception {

        throw new Exception("I'm outta here!");

    }

}
```

该程序产生输出：

```
java.lang.Exception: I'm outta here!
Now j = 1
```

也就是说，运算符 `/` 的左操作数 `forgetIt()` 在右操作数被评估以及其嵌入的对 j 赋值 2 之前抛出了异常。

### 15.7.2 在操作之前评估操作数

Java 编程语言保证运算符的每个操作数（条件运算符 `&&`、`||` 和 `?:` 除外）在运算符的任何部分执行之前被完全评估。

如果二元运算符是整数除法 `/` (§15.7.2) 或整数取模 `%` (§15.17.3)，其执行可能会抛出 `ArithmeticException`，但该异常仅在二元运算符的两个操作数都已完成评估且仅在这些评估正常完成的情况下才会抛出。

#### 示例 15.7.2-1. 操作之前的操作数评估

```java
class Test {

    public static void main(String[] args) {

        int divisor = 0;

        try {

            int i = 1 / (divisor * loseBig());

        } catch (Exception e) {

            System.out.println(e);

        }

    }

    static int loseBig() throws Exception {

        throw new Exception("Shuffle off!");

    }

}
```

该程序产生输出：

```
java.lang.Exception: Shuffle off!
```

而不是：

```
java.lang.ArithmeticException: / by zero
```

因为除法操作在 `loseBig()` 调用之前就先发生了除以零异常。

### 15.7.3 评估遵循括号和优先级

Java 编程语言显式地遵循括号，隐式地遵循运算符优先级。

在浮点计算的情况下，此规则也适用于 `infinity` 和 `NaN`。具体而言，例如测试程序：

```java
strict class Test {

    public static void main(String[] args) {

        double d = 8e37;

        System.out.println(4.0 * d * 0.5);

        System.out.println(2.0 * d);

    }

}
```

打印结果：

Infinity
1.6e38

因为第一个表达式溢出了，而第二个没有。

### 15.7.4 参数列表从左到右评估

在方法调用、构造函数调用或类实例创建中，参数表达式出现在括号内，并用逗号分隔。每个参数表达式在其右侧的任何参数表达式之前都已被完全评估。

如果一个参数表达式的评估异常完成，则其右侧的任何参数表达式似乎未被评估过。

#### 示例 15.7.4-1. 方法调用时的评估顺序

```java
class Test1 {

    public static void main(String[] args) {

        String s = "going";

        print3(s, s, s = "gone");

    }

    public static void print3(String a, String b, String c) {

        System.out.println(a + b + c);

    }

}
```

该程序产生输出：

going, going, gone

因为对 s 赋值 "gone" 发生在 `print3` 的前两个参数被评估之后。

#### 示例 15.7.4-2. 参数表达式的异常完成

```java
class Test2 {

    static int id;

    public static void main(String[] args) {

        try {

            test(id = 1, oops(), id = 3);

        } catch (Exception e) {

            System.out.println(e + " " + id=" + id);

        }

    }

    static int test(int a, int b, int c) {

        return 0;

    }

    static int oops() throws Exception {

        throw new Exception("oops");

    }

}
```

该程序产生输出：

java.lang.Exception: oops id=1

相比之下，整数加法和乘法在 Java 语言中是证明满足结合律的。

例如 `a+b+c`，其中 a、b 和 c 都是局部变量（这一简化假设避免了涉及线程和 volatile 变量的问题），无论评估为 `(a+b)+c` 还是 `a+(b+c)`，都总是产生相同的答案；如果表达式 `b+c` 在代码附近出现，智能的 Java 编译器可能可以使用这个公共子表达式。

```java
return a + b + c;

static int oops() throws Exception {

    throw new Exception("oops");

}
```

此程序产生输出：

```
java.lang.Exception: oops, id=1
```

因为对 id 的赋值没有执行。

## 15.7.5 其他表达式的求值顺序

某些表达式的求值顺序没有由这些通用规则完全覆盖，因为这些表达式有时必须指定异常条件。以下类型表达式的求值顺序详细说明：

- 类实例创建表达式 (§15.9.4)
- 数组创建表达式 (§15.10.2)
- 数组访问表达式 (§15.10.4)
- 方法调用表达式 (§15.12.4)
- 方法引用表达式 (§15.13.3)
- 涉及数组组件的赋值 (§15.26)
- lambda 表达式 (§15.27.4)

## 15.8 基础表达式

基础表达式包括最简单的几种表达式，其他表达式都由它们构造：字面量、对象创建、字段访问、方法调用、方法引用和数组访问。带括号的表达式在语法上也被视为基础表达式。

Primary:
PrimaryNoNewArray
ArrayCreationExpression

### 基础表达式

PrimaryNewArray:
Literal
ClassLiteral
this
TypeName . this( )
ClassInstanceExpression
FieldAccess
MethodInvocation
MethodReference

Java 语言语法的这部分有两个不同之处。首先，人们可能期望简单的名称（如局部变量和方法参数）是基础表达式。由于技术原因，在引入后置表达式稍后，名称与基础表达式分在了一起 (§15.14)。技术原因与仅有一个 token 预测的 Java 程序的左到右解析有关。考虑表达式 `[z]` 和 `((z))`。第一个是带括号的数组访问 (§15.10.3)，第二个是转换 (§15.16)。在跟在 `[` 符号的地方，从左到右解析会将 `z` 归约为 `Name`。在转换的上下文中，如果 `Name` 是基础表达式的选项之一，我们在不向前看两个 token 的情况下无法判断 `z` 是带括号的数组访问还是转换。语法通过将 `Name` 和 `Primary` 分开并在某些其他规则中允许（`ClassCreationExpression`、`MethodInvocation` 和 `PostfixExpression`，尽管它们直接使用了标识符）来解决了 `Name` 是否应该被视为基础表达式的问题。

另一个异常特征是表达式 `new int[][]` 中潜在的语法歧义，在没有适当语法技巧的情况下，它可能被解释为多维数组的创建。这种歧义通过将 `Primary` 拆分为 `PrimaryNoNewArray` 来解决（这与 §14.5 中的 `dangling else` 问题类似）。

## 15.8.1 字面量形式

字面量 (§3.10) 表示一个固定值。为了方便，这里显示了来自 §3.10 的产生式：

Primary Expressions 15.8

Literal:
IntegerLiteral
FloatingPointLiteral
BooleanLiteral
CharacterLiteral
StringLiteral
NullLiteral

字面量的类型如下：

- 以 `L` 或 `l` 结尾的整数字面量 (§3.10.1) 类型为 `long` (§4.2.1)。
- 任何其他整数字面量的类型为 `int` (§4.2.1)。
- 以 `F` 或 `f` 结尾的浮点字面量 (§3.10.2) 类型为 `float`，其值必须是 `float` 值集合 (§4.2.3)。
- 任何其他浮点字面量的类型为 `double`，其值必须是 `double` 值集合 (§4.2.3)。
- 布尔字面量 (§3.10.3) 类型为 `boolean` (§4.2.5)。
- 字符字面量 (§3.10.4) 类型为 `char` (§4.2.1)。
- 字符串字面量 (§3.10.5) 类型为 `String` (§4.3.3)。
- `null` 字面量 (§3.10.7) 类型为 `null` 类型 (§4.1)；其值为空引用。

语法错误的求值总是正常完成。

## 15.8.2 类字面量

类字面量是一个由类、接口、数组或基本类型的名称，或伪类型 `void` 后面跟 `.` 和 token `class` 组成的表达式。

```
ClassLiteral:
TypeName . class
NumericType . class
boolean . class
void . class
```

`TypeName` 必须表示可访问的类或接口类型 (§6.6)。如果 `TypeName` 表示不可访问的类或接口类型或或类型变量，则为编译错误。

`C.class` (其中 `C` 是类、接口或数组类型的名称，§4.3) 类型为 `Class<C>`。`p.class` (其中 `p` 是基本类型的名称，§4.2) 类型为 `Class<B>`，其中 `B` 是类型 `p` 的表达式在装箱转换后的类型 (§5.1.7)。

`void.class` (§8.4.5) 类型为 `Class<Void>`。

类字面量求值为由当前实例类的加载器 (§12.2) 定义的命名类型（或 `void`）的 `Class` 对象。

## 15.8.3 this

关键字 `this` 只能在以下上下文中使用：

- 在实例方法或默认方法的体中 (§8.4.7, §9.4.3)
- 在类的构造函数的体中 (§8.8.7)
- 在类的实例初始化器中 (§8.6)
- 在类的实例变量的初始化器中 (§8.3.2)
- 用于表示接收者参数 (§8.4)

如果它出现在任何其他地方，将发生编译错误。

关键字 `this` 只有在允许的情况下才能在 lambda 中使用。否则，将发生编译错误。

当作为基础表达式使用时，关键字 `this` 表示对调用该方法的实例的引用。`this` 的类型是 `this` 所在的类或接口。

lambda 表达式中 `this` 的值与周围环境中 `this` 所表示的值相同。

关键字 `this` 也被用于显式构造函数语句 (§8.7)。默认方法提供了访问 `this` 的独特能力。结果，`this` 可能具有接口类型。

示例 15.8.3-1. this

```java
class IntVector {

    int[] v;

}
```

```java
boolean equals(IntVector other) {

  if (this == other) {

    return true;

  }

  if (v.length != other.v.length) {

    return false;

  }

  for (int i = 0; i < v.length; i++) {

    if (v[i] != other.v[i]) return false;

  }

  return true;

}
```

`IntVector` 类实现了 `equals` 方法，比较两个向量。如果 `other` 向量是调用 `equals` 方法的向量对象，则可以跳过长度和值的比较。`equals` 方法通过比较引用来实现。

## 15.8.4 限定 this

任何嵌套实例 (§8.1.3) 都可以通过式限定关键字 `this` 来引用。让 `TypeName` 为类型 `τ`，让整数 `n` 为所在的类或接口的第 n 个嵌套类型声明。形式 `TypeName.this` 的表达式的值是第 n 个嵌套实例。

该表达式的类型是 `τ`。如果表达式出现在不是类或 `τ` 的内部内部类中，则为编译错误。

## 15.8.5 带括号的表达式

带括号的表达式是一个基础表达式，其类型是包含表达式的类型，其在运行时等于包含表达式的值。它也表示变量。

括号的使用只影响求值顺序，一个特殊情况外：`(-2147483648)` 和 `(-9223372036854775808L)` 是合法的，但 `-(2147483648)` 和 `-(9223372036854775808L)` 是非法的。这是因为十字面量只允许作为减法运算符的操作数 (§3.10.1)。

特别是，表达式周围是否存在括号（除上述注的情况外）不会以任何方式影响：

- 类型为 `float` 或 `double` 的表达式的值的值集选择（§4.2.3）。
- 变量是否被确定赋值、在为真时确定赋值、在为假时确定赋值、确定未赋值、在为真时确定未赋值或在为假时确定未赋值 (§16 (确定赋值))。

如果带括号的表达式出现在特定类型的目标类型 $\tau$ 上文中（§5 (转换与上下文)），则其包含的表达式同样出现在相同类型的目标类型 $\tau$ 上文中。

如果包含的表达式有多值表达式（§15.2），则带括号的表达式也是多值表达式。否则，它是一个独立表达式。

如果包含的表达式与目标类型 $\tau$ 兼容，则带括号的多值表达式与 $\tau$ 兼容。

## 15.9 类实例创建表达式

实例创建表达式用于创建作为类实例的新对象。

```
ClassInstanceCreationExpression:
UnqualifiedClassInstanceCreationExpression
ExpressionName . UnqualifiedClassInstanceCreationExpression
Primary . UnqualifiedClassInstanceCreationExpression
```

```
UnqualifiedClassInstanceCreationExpression:
new [TypeArguments]
ClassOrInterfaceToInstantiate ([ArgumentList] ) [ClassBody]
```

```
ClassOrInterfaceToInstantiate:
[Annotation] Identifier (. [Annotation] Identifier)
[TypeArgumentsOrDiamond]
```

```
TypeArgumentsOrDiamond:
TypeArguments
<>
```



为了方便起见，此处显示了 §15.12 中的后续产生式：

# 表达式

## 类实例创建表达式

### ArgumentList

```
Expression ( , Expression)
```

类实例创建表达式指定一个要实例化的类，后面可能跟着类型参数（§4.5.1）或者当被实例化的类是泛型时（§8.1.2）的菱形（`<>`），随后是构造函数的（可能为空）实际值参数列表。

如果类的类型参数列表为空——即菱形形式 `<>`——则类型将通过推断。在 `<` 和 `>` 之间留空格是合法的，尽管从风格角度上强烈不建议这样做。

如果构造函数是泛型的，则构造函数的类型参数也可以相似地被推断或显式传递。如果显式传递，构造函数的类型参数将紧跟在 `new` 关键字之后。

如果类实例创建表达式为构造函数提供了类型参数，但对类的类型参数使用了菱形形式，则会导致编译错误。

> 引入此规则是因为泛型类类型参数的推断可能会影响泛型构造函数类型参数的约束。

如果 `TypeArguments` 紧跟在 `new` 之后或紧跟在 `(` 之前，如果任何类型参数是通配符（§4.5.1），则为编译错误。

类实例创建表达式可以抛出的异常指定于 §11.2.1。

类实例创建表达式有两种形式：

- **未限定的类实例创建表达式**以关键字 `new` 开始。未限定的类实例创建表达式可用于创建类的实例，无论该类是顶层（§7.6）、成员（§8.5, §9.5）、局部（§14.3）还是匿名类（§15.9.5）。
- **限定的类实例创建表达式**以 `Primary` 表达式或 `ExpressionName` 开始。限定的类实例创建表达式允许创建内部成员类及其匿名子类的实例。

未限定和限定的类实例创建表达式都可以可选地以类体结束。此类类实例创建表达式声明了一个匿名类（§15.9.5）并创建了该类的实例。

## 类实例创建表达式

如果类实例创建表达式在类的类型参数上使用了菱形形式，并且出现在赋值上下文或调用上下文中（§5.2, §5.3），则它是一个多值表达式（§15.2）。否则，它是一个独立表达式。

当通过类实例创建表达式创建类的实例时，我们称该类被实例化了。类实例化涉及确定要实例化的类（§15.9.1）、新创建实例的闭包实例（如果有）（§15.9.2）以及用于创建新实例的调用构造函数（§15.9.3）。

### 15.9.1 确定正在实例化的类

如果 `ClassOrInterfaceTypeInstantiate` 带有 `TypeArguments`（而不是 `<>`），则 `ClassOrInterfaceTypeInstantiate` 必须表示一个良好的参数化类型（§4.5），否则将产生编译错误。

如果 `ClassOrInterfaceTypeInstantiate` 带有 `<>`，但 `ClassOrInterfaceTypeInstantiate` 中的 `Identifier` 所标识的类型不是泛型，则产生编译错误。

如果类实例创建表达式以类体结尾，则正在实例化的类是一个匿名类。那么：

- 如果类实例创建表达式是未限定的，则：
  - `ClassOrInterfaceTypeInstantiate` 中的 `Identifier` 必须表示一个可访问的非 final 且非枚举类型的类，或者一个可访问的接口（§6.6）。否则发生编译错误。
  - 如果 `ClassOrInterfaceTypeInstantiate` 中的 `Identifier` 表示类 `c`，则声明一个 `c` 的匿名子类。如果存在 `TypeArguments`，则 `c` 具有由 `TypeArguments` 提供的类型参数；如果存在 `<>`，则 `c` 将在 §15.9.3 中推断类型参数；否则，`c` 没有类型参数。子类的体由 `ClassBody` 给出，正在实例化的类是该匿名子类。
  - 如果 `ClassOrInterfaceTypeInstantiate` 中的 `Identifier` 表示接口 `i`，则声明一个实现 `i` 的 `Object` 的匿名子类。如果存在 `TypeArguments`，则 `i` 具有由 `TypeArguments` 提供的类型参数；如果存在 `<>`，则 `i` 将在 §15.9.3 中推断类型参数；否则，`i` 没有类型参数。子类的体从实例创建表达式给出的 `ClassBody` 推断。正在实例化的类是该匿名子类。

- 如果类实例创建表达式是限定的，则：
  - `ClassOrInterfaceToInstantiate` 中的 `Identifier` 必须无歧地表示一个可访问、非 final、非枚举类型的内部类，并且是 `Primary` 表达式或 `ExpressionName` 编译时类型的成员。否则发生编译错误。
  - 令 `ClassOrInterfaceToInstantiate` 中的 `Identifier` 表示类 `c`。声明一个 `c` 的匿名直接子类。如果存在 `TypeArguments`，则 `c` 具有由 `TypeArguments` 提供的类型参数；如果存在 `<>`，则 `c` 将在 §15.9.3 中推断类型参数；否则，`c` 没有类型参数。子类的体是实例创建表达式给出的 `ClassBody`。正在实例化的类是该匿名子类。

如果类实例创建表达式没有声明匿名类，则：

- 如果类实例创建表达式是未限定的，则：
  - `ClassOrInterfaceToInstantiate` 中的 `Identifier` 必须表示一个可访问、非抽象且非枚举类型的类。否则产生编译错误。
  - 正在实例化的类由 `ClassOrInterfaceToInstantiate` 指定。如果存在 `TypeArguments`，则该类具有由 `TypeArguments` 提供的类型参数；如果存在 `<>`，则该类将在 §15.9.3 中推断类型参数；否则，该类没有类型参数。
- 如果类实例创建表达式是限定的，则：
  - `ClassOrInterfaceToInstantiate` 必须无歧地表示一个可访问、非抽象、非枚举类型的内部类，是 `Primary` 表达式或 `ExpressionName` 编译时类型的成员。
  - 正在实例化的类由 `ClassOrInterfaceToInstantiate` 指定。如果存在 `TypeArguments`，则该类具有由 `TypeArguments` 提供的类型参数；如果存在 `<>`，则该类将在 §15.9.3 中推断类型参数；否则，该类没有类型参数。

### 15.9.2 确定闭包实例

令 `c` 为正在实例化的类，`i` 为正在创建的实例。如果 `c` 是内部类，则 `i` 可能有一个直接闭包实例（§8.1.3），确定方式如下：

- 如果 `c` 是一个匿名类，则：
  - 如果类实例创建表达式发生在静态上下文中，则 `i` 没有直接包围的实例。
  - 否则，`i` 的直接包围的实例是 `this`。
- 如果 `c` 是一个局部类，则：
  - 如果 `c` 发生在静态上下文中，则 `i` 没有直接包围的实例。
  - 否则，如果类实例创建表达式发生在静态上下文中，则会发生编译时错误。
  - 否则，令 `o` 为 `c` 的直接包围的类型声明。令 `n` 为一个整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法包围的类型声明。`i` 的直接包围的实例是 `this` 的第 `n` 个词法包围的实例。
- 如果 `c` 是一个内部成员类，则：
  - 如果类实例创建表达式发生在静态上下文中，则会发生编译时错误。
  - 否则，如果 `c` 是包含类实例创建表达式出现处的类的成员，令 `o` 为 `c` 所属类的直接包围的类。令 `n` 为一个整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法包围的类型声明。`i` 的直接包围的实例是 `this` 的第 `n` 个词法包围的实例。
  - 否则，会发生编译时错误。
- 如果类实例创建表达式是限定的，则 `i` 的直接包围的实例是作为 `Primary` 表达式或 `ExpressionName` 的对象。

如果 `c` 是匿名类，且其直接父类 `s` 是一个内部类，则 `i` 可能对于 `s` 有直接包围的实例，确定方式如下：

- 如果 `s` 是一个局部类，则：
  - 如果 `s` 发生在静态上下文中，则 `i` 对于 `s` 没有直接包围的实例。
  - 否则，如果类实例创建表达式发生在静态上下文中，则会发生编译时错误。
  - 否则，令 `o` 为 `s` 的直接包围的类型声明。令 `n` 为一个整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法包围的类型声明。`i` 对于 `s` 的直接包围的实例是 `this` 的第 `n` 个词法包围的实例。
- 如果 `s` 是一个内部类，则：
  - 如果类实例创建表达式未限定，则：
    - 如果类实例创建表达式发生在静态上下文中，则会发生编译时错误。
    - 否则，如果 `s` 是包含类实例创建表达式出现处的类的成员，令 `o` 为 `s` 所属类的直接包围的类。令 `n` 为一个整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法包围的类型声明。`i` 对为 `s` 的直接包围的实例是 `this` 的第 `n` 个词法包围的实例。
    - 否则，会发生编译时错误。
  - 如果类实例创建表达式是限定的，则 `i` 对于 `s` 的直接包围的实例是作为 `Primary` 表达式或 `ExpressionName` 的对象。

### 15.9.3 选择构造函数及其参数

令 `c` 为被实例化的类。创建 `c` 的一个实例 `i`，在编译时选择 `c` 的一个构造函数。

首先，构造函数的实际参数确定如下：

- 如果 `c` 是匿名类且其直接父类为 `s`，则：
  - 如果 `s` 不是内部类，或者 `s` 是发生在静态上下文中的局部类，则构造函数的参数是类实例创建表达式的参数列表。
  - 否则，构造函数的第一个参数是 `i` 对于 `s` 的直接包围的实例（15.9.2），后续参数是类实例创建表达式的参数列表，按出现顺序确定。
- 如果 `C` 是局部类或私有成员类，则构造函数的参数是类实例创建表达式的参数列表，按出现顺序确定。
- 如果 `C` 是非私有成员类，则构造函数的第一个参数是 `i` 对于 `s` 的直接包围的实例（15.9.2），后续参数是类实例创建表达式的参数列表，按出现顺序确定。
- 否则，构造函数的参数是类实例创建表达式的参数列表，按出现顺序确定。

其次，构造函数及其相应的 `throws` 子句和返回类型确定如下：

如果类实例创建表达式没有使用 `<`，则

- 如果 `C` 不是匿名类，则：
  令 `τ` 为 `C` 后跟的类类型。使用经过修改的 §15.12.2 过程来选择 `T` 的构造函数并确定其 `throws` 子句。
  如果 `T` 中没有唯一的适用且可访问的构造函数（6.6），则报错。
  否则，所选构造函数对应的返回类型为 `T`。
- 如果 `C` 是匿名类，则：
  使用经过修改的 §15.12.2 过程来选择 `C` 直接父类的一个构造函数，并确定其 `throws` 子句。
  如果 `C` 直接父类中没有唯一的适用且可访问的构造函数，则报错。
  否则，所选构造函数对应的返回类型为 `T`。

如果类实例创建表达式使用了 `<`，则

- 如果 `c` 不是匿名类，令 `d` 与 `c` 相同。如果 `c` 是匿名类，令 `d` 为 `c` 的父类或接口。
- 如果 `D` 是类，`c_1...c_p` 为 `D` 的构造函数。如果 `D` 是接口，令 `c_1...c_n` 为包含零参数构造函数的单例（`n=1`）。

为了选择一个，我们临时将 `m_1...m_n` 视为 `D` 的成员。根据类实例创建表达式的参数表达式，使用 §15.12.2 规定的过程选择 `m_1...m_n` 中的一个。

如果没有唯一的特定的适用且可访问的方法，则报错。

否则，当 `m_j` 为所选方法时：

- 如果 `c` 不是匿名类，则选择 `c_j` 为 `C` 的构造函数。
- 所选构造函数的 `throws` 子句与为 `m_j` 确定的 `throws` 子句相同。
- 对应所选构造函数的返回类型为 `m_j` 确定的返回类型（§15.12.2.6）。
- 如果 `c` 是一个匿名类，则 `c` 的匿名构造函数被选择为 `c` 的构造函数。它的体包含对 `c_j` 的显式构造调用（§8.8.7.1）。
- 所选构造函数的 `throws` 子句包含为 `m_j` 确定的 `throws` 子句中的异常。
- 对应所选构造函数的返回类型是匿名类类型。

如果类实例创建表达式是一个多式表达式，则其与目标类型的兼容性由 §18.5.2.1 确定，并使用 `m_j` 作为所选方法 `m`。

在最终确定类实例创建的目标类型以及对应所选构造函数的返回类型之前，可能会多次发生与目标类型的兼容性测试。例如，一个嵌套的调用表达式可能需要测试类实例创建表达式与不同方法的形式参数类型的兼容性。

如果 `c` 是一个匿名类，那么它的超类或超接口（§15.9.5）是为 `m_j` 确定的返回类型（§15.12.2.6）。

如果超类或超接口，或其中的任何子表达式（“子表达式”）包含参数化类型的类型参数、通配符类型参数的边界以及数组类型的元素类型（但不排除类型变量的边界），且具有以下形式之一，则为编译错误：

- 未声明为类型参数的类型变量（例如由捕获转换产生的类型）。
- 交叉类型。
- 类或接口类型，其中该类或接口的声明在出现该类实例创建表达式的类或接口中是不可访问的。

如果类实例创建表达式的参数与其派生自调用类型（§15.12.2.6）的目标类型不兼容，则为编译错误。

如果编译声明可以通过变长参数调用（§15.12.2.4）适用，其中构造函数调用类型的最后一个形式参数类型为 `F_n[]`，则如果 `F_n` 的擦除在调用点处不可访问，则为编译错误。

类实例创建表达式的类型是上述定义的对应所选构造函数的返回类型。

### 15.9.4 类实例创建表达式的运行时评估

在运行时，类实例创建表达式的评估如下。

首先，如果类实例创建表达式是限定的类实例创建表达式，则求值限定的主表达式。如果限定表达式求值结果为 `null`，则抛出 `NullPointerException`，并且类实例创建异常终止。如果限定表达式异常终止，则因相同原因也发生异常终止。

接下来，为新的类实例分配空间。如果空间不足以分配对象，则类实例创建表达式的评估通过抛出 `OutOfMemoryError` 异常终止。

新对象包含指定类类型及其所有子类中声明的所有字段的新实例。当每个新字段被创建时，它将被初始化为其默认值（§4.12.5）。

接下来，从左到右评估构造函数的实际参数。如果任何参数的评估异常终止，则其右侧的参数表达式将不被评估，且类实例创建表达式因相同原因异常终止。

接下来，调用指定类类型的所选构造函数。这将导致为类类型的每个超类至少调用一个构造函数。此过程可以通过显式构造调用语句（§8.8.7.1）指定，并在 §12.5 中详细说明。

类实例创建表达式的值是指新创建的指定类对象的引用。每当评估该表达式时，都会创建一个新对象。

#### 示例 15.9.4-1. 评估顺序与内存溢出检测

如果类实例创建表达式的评估发现没有足够的内存执行创建操作，则抛出 `OutOfMemoryError`。此检查发生在任何参数表达式评估之前。

因此，例如，测试程序：

```java
class List {
  int value;
  List next;
  static List head = new List(0);
  List(int n) { value = n; next = head; head = this; }
}

class Test {
  public static void main(String[] args) {
    int id = 0, oldid = 0;
    try {
      for (;;) {
        ++id;
        new List(id);
      }
    } catch (Error e) {
      List.head = null;
      System.out.println(e.getClass() + " " + (oldid=id));
    }
  }
}
```

打印：

```
class java.lang.OutOfMemoryError, false
```



因为在评估参数表达式 `oldid = id` 之前检测到了内存溢出条件。

将其与数组创建表达式的处理进行比较，对于后者，内存溢出条件是在评估维度表达式 (§15.10.2) 后检测到的。

## 15.9.5 匿名类声明

匿名类由 Java 编译器从类实例创建表达式自动派生。

匿名类永远不是抽象的 (§8.1.1.1)。

匿名类永远不是 final 的 (§8.1.1)。

> 匿名类在强制转换中不是 final 的事实，特别是强制转换允许的收窄转换 (§5.5)。在子类化中同样感兴趣的是，尽管匿名类是非 final 的，但无法通过 extends 子句声明匿名类的子类 (§8.1.4)。

匿名类始终是内部类 (§8.1.3)；不是静态的 (§8.1.2)。匿名类的超类或超接口由类实例创建表达式给出 (§15.9.1)，并在选择构造函数时推断必要的类型参数 (§15.9.3)。

如果类实例创建表达式对匿名类使用 `<>`，则对于匿名类中声明的所有非私有方法，其方法声明仿佛标记了 `@Override` (§9.6.4)。

> 当使用 `<>` 时，程序员可能无法预期推断的结果。因此，匿名类的超类型可能无法预期，且匿名类中声明的方法可能无法预期覆盖超类型方法。将此类方法视为标记了 `@Override`（如果它们没有显式标记了 `@Override`）有助于避免错误的程序。

### 15.9.5.1 匿名构造函数

匿名类不能显式声明构造函数。相反，为匿名类隐式声明一个构造函数。具有直接超类 `s` 的匿名类的构造函数形式如下：

- 如果 `s` 不是内部类，或者 `s` 是在静态上下文中的局部类，则为声明 `c` 的类实例创建表达式的每个实际参数有一个形式参数。

类实例创建表达式的实际参数用于确定 `s` 的构造函数 `cs`，如 §15.9.3 所示。匿名构造函数的每个形式参数类型必须与 `cs` 相应的形式参数类型相同。

构造函数体包含一个形式为 `super(...)` 的显式构造调用 (§8.8.7.1)，其中实际参数是按声明顺序的形式参数。调用超类构造函数 `cs`。

- 否则，`c` 的构造函数的第一个形式参数表示 `i` 相对于 `s` 的紧闭实例的值 (§15.9.2, §15.9.3)。该参数的类型是紧闭 `s` 声明的类。

构造函数对于声明匿名类的类实例创建表达式的每个实际参数还有一个额外的形式参数。第 `n` 个形式参数 `s` 对应第 `n` 个实际参数。

匿名构造函数的参数必须与 `cs` 对应的形式参数相同。

构造函数包含一个显式的构造函数调用 (§8.8.7.1)，形式为 `o.super(...)`，其中 `o` 是构造函数的第一个参数，实际参数是按照它们声明顺序排列的构造函数的后续形式参数。要调用的父类构造函数是 `cs`。

在所有情况下，匿名构造函数的 `throws` 子句必须列出根据 §15.9.3 由匿名构造函数包含的显式父类调用语句抛出的所有检查异常，以及匿名类的任何实例初始化器或实例变量初始化器抛出的所有检查异常。

请注意，匿名构造函数的签名可能会引用不可访问的类型（例如，如果该类型出现在父类构造函数 `cs` 的签名中）。这本身不会在编译时或运行时引起任何错误。

## 15.10 数组创建与访问表达式

### 15.10.1 数组创建表达式

数组创建表达式用于创建新数组 (§10 (Arrays))。

```
ArrayCreationExpression:
    new PrimitiveType DimExprs [Dims]
    new ClassOrInterfaceType DimExprs [Dims]
    new PrimitiveType Dims ArrayInitializer
    new ClassOrInterfaceType Dims ArrayInitializer
```

```
DimExprs:
    DimExpr {DimExpr}
```

```
DimExpr:
    [Annotation] [ Expression ]
```

为了方便起见，这里展示了 §4.3 中的以下产生式：

```
Dims:
    [Annotation] [ ] {[Annotation] [ ]}
```

数组创建表达式创建一个对象，该对象是一个新数组，其元素类型由 `PrimitiveType` 或 `ClassOrInterfaceType` 指定。如果 `ClassOrInterfaceType` 表示可重构类型 (§4.7)，则为编译错误。否则，`ClassOrInterfaceType` 可以命名任何命名的引用类型，即使是抽象类类型 (§8.1.1.1) 或接口类型。

这意味着数组创建表达式中的元素类型不能是参数类型，除非所有参数都参数化为无界通配符。

`DimExpr` 内部每个维度表达式的类型必须是可以转换为 (§5.1.8) 整数类型的类型，否则将发生编译错误。

每个维度表达式都经过一元数值提升 (§5.6)。提升后的类型必须是 `int`，否则将发生编译错误。

数组创建表达式的类型是一个数组类型，可以通过删除 `new` 关键字、每个 `DimExpr` 表达式和数组初始化器后的数组创建表达式来表示。

例如，创建表达式的类型：

```
new double[3][3][]
```

类型为：

```
double[][][]
```

### 15.10.2 数组创建表达式的运行时

在运行时，数组创建表达式的求值行为如下：

- 如果没有维度表达式，则有一个数组初始化器。新分配的数组将根据 §10.6 的描述用数组初始化器提供的值进行初始化。数组初始化器的值成为数组创建表达式的值。

否则，则没有数组初始化器，且：

- 首先，从左到右求值维度表达式。如果任何表达式求值异常终止，则右侧的表达式将不再求值。
- 然后，检查维度表达式的值。如果任何 `DimExpr` 表达式的值小于 0，则抛出 `NegativeArraySizeException`。
- 接着，为新数组分配空间。如果空间不足以分配数组，则通过抛出 `OutOfMemoryError` 使数组创建表达式的求值异常终止。
- 然后，如果出现单个 `DimExpr`，则创建一个指定长度的一维数组，数组的每个组件都初始化为其默认值 (§4.12.5)。
- 否则，如果出现 `n` 个 `DimExpr`，则数组创建实际上执行一组深度为 `n-1` 的嵌套循环，以创建隐含的数组数组。

多维数组的每一层不需要具有相同长度的数组。

#### 例 15.10.2-1。数组创建求值

在具有一个或多个维度表达式数组创建表达式中，每个维度表达式在其右侧任何维度表达式的部分之前都会被完全求值。因此：

```java
class Test1 {
    public static void main(String[] args) {
        int i = 4;
        int ia[] = new int[i][i=3];
        System.out.println("[" + ia.length + "," + ia[0].length + "]");
    }
}
```

打印：

```
[4, 3]
```

因为在第二个维度表达式将 `i` 设置为 3 之前，第一个维度被计算为 4。

如果维度表达式的求值异常终止，则其右侧任何维度表达式的部分都未被求值过。因此：

```java
class Test2 {
    public static void main(String[] args) {
        int[][] a = { { 00, 01 }, { 10, 11 } };
        int i = 99;
        try {
            a[val()] = i++;
        } catch (Exception e) {
            System.out.println(e + ", i=" + i);
        }
    }
    static int val() throws Exception {
        throw new Exception("unimplemented");
    }
}
```

打印：

```
java.lang.Exception, i=99
```

因为执行了将 `i` 设置为 1 的赋值。

#### 例 15.10.2-2. 多维数组创建

声明：

```java
float[][] matrix = new float[3][3];
```

在以下情况下等价于：

```java
float[][] matrix = new float[3][];
for (int d = 0; d < matrix.length; d++)
    matrix[d] = new float[3];
```

以及：

```java
Age[][][][] Aquarius = new Age[6][10][8][12];
```

等价于：

```java
Age[][][][] Aquarius = new Age[6][10][8][];
for (int d1 = 0; d1 < Aquarius.length; d1++) {
    for (int d2 = 0; d2 < Aquarius[d1].length; d2++) {
        for (int d3 = 0; d3 < Aquarius[d1][d2].length; d3++) {
            Aquarius[d1][d2][d3] = new Age[12];
        }
    }
}
```

此示例留下了第五维（即包含 `Age` 对象的数组），仅初始化为空引用。这些数组可以以后填充，例如：

```java
Age[] Hair = { new Age("quartz"), new Age("topaz") };
Aquarius[1][9][6] = Hair;
```

#### 例 15.10.2-3. OutOfMemoryError 与维度表达式求值

```java
class Test3 {
    public static void main(String[] args) {
        int len = 0, oldlen = 0;
        Object[] a = new Object[0];
        try {
            for (;;) {
                ++len;
                Object[] temp = new Object[oldlen=len];
                temp[0] = a;
                a = temp;
            }
        } catch (Error e) {
            System.out.println(e + " " + (oldlen==len));
        }
    }
}
```

此程序产生输出：

```
java.lang.OutOfMemoryError true
```

因为在维度表达式 `oldlen = len` 求值后检测到内存溢出。

将此与类实例创建表达式 (§15.9) 进行比较，后者在评估参数表达式 (§15.9.4) 之前检测内存溢出情况。

### 15.10.3 数组访问表达式

数组访问表达式指的是作为数组组件的变量。

```
ArrayAccess:
    ExpressionName [ Expression ]
    PrimaryNoNewArray [ Expression ]
```

数组访问表达式包含两个子表达式：数组引用表达式（左中括号之前的）和索引表达式（括号内的）。

> 注意，数组引用表达式可以是一个名称，或任何不是数组创建表达式的初级表达式 (§15.10)。

数组引用表达式的类型必须是数组类型（称之为 `T[]`，且数组组件的类型为 `T`），否则会发生编译错误。

索引表达式将进行一元数值提升 (§5.6)。提升后的类型必须是 `int`，否则会发生编译错误。

数组访问表达式的类型是对 `T` 应用类型转换 (§5.1.10) 之后的结果。

数组访问表达式的结果是一个类型为 `T` 的变量，即由索引表达式的值所选中的数组变量。

这个生成的变量是数组的组件，它永远不会被视为 `final`，即使数组引用表达式指向一个 `final` 变量。

### 15.10.4 数组访问表达式的运行时评估

在运行时，数组访问表达式的评估行为如下：

- 首先，评估数组引用表达式。如果该评估异常完成，则数组访问也以相同原因异常完成，且不评估索引表达式。
- 否则，评估索引表达式。如果该评估异常完成，则数组访问以相同原因异常完成。
- 否则，如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。

否则，数组引用表达式的值确实指向一个数组。如果 `arrayIndex` 的值大于或等于数组的长度，则抛出 `ArrayIndexOutOfBoundsException`。

否则，数组访问的结果是数组中一个类型为 `T` 的变量，该变量由索引表达式的值所选中。

#### 示例 15.10.4-1. 数组引用被评估

在数组访问中，括号左侧的表达式在括号内的任何表达式被评估之前都会被完全评估。例如，在（诚然疯狂的）表达式 `a[(a=b)][3]` 中，表达式 `a` 在表达式 `(a=b)[3]` 评估之前被完全评估；这意味着在评估 `(a=b)[3]` 期间，`a` 的原始值被获取并记住。由 `a` 的原始值引用的数组由另一个数组（可能是同一个数组）的第 3 个元素索引，而该数组由 `b` 引用，现在也被 `a` 引用。

因此，程序：

```java
class Test1 {
    public static void main(String[] args) {
        int[] a = { 11, 12, 13, 14 };
        int[] b = { 0, 1, 2, 3 };
        System.out.println(a[(a=b)[3]]);
    }
}
```

打印结果：

```
14
```

因为这个疯狂表达式的值等同于 `a[b[3]]` 或 `a[3]` 或 `14`。

#### 示例 15.10.4-2. 数组引用评估的异常完成

如果括号左侧表达式的评估异常完成，则括号内表达式的任何部分都不会被评估。因此，程序：

```java
class Test2 {
    public static void main(String[] args) {
        int index = 1;
        try {
            skedaddle()[index++];
        } catch (Exception e) {
            System.out.println(e + ", index=" + index);
        }
    }
    static int[] skedaddle() throws Exception {
        throw new Exception("Ciao");
    }
}
```

打印结果：

```
java.lang.Exception: Ciao, index=1
```

因为嵌入的向 `index` 赋值 2 操作从未发生。

#### 示例 15.10.4-3. null 数组引用

如果数组引用表达式产生 `null` 而不是数组引用，则在运行时抛出 `NullPointerException`，但是在数组访问表达式的所有部分都已评估之后，且仅在这些评估正常完成的情况下。因此，程序：

```java
class Test3 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada()[index=2]++;
        } catch (Exception e) {
            System.out.println(e + ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```

打印结果：

```
java.lang.NullPointerException, index=2
```

因为嵌入的向 `index` 赋值 2 操作发生在检查 null 数组引用表达式之前。作为一个相关的示例，程序：

```java
class Test4 {
    public static void main(String[] args) {
        int[] a = null;
        try {
            int i = a[vamoose()];
            System.out.println(i);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
    static int vamoose() throws Exception {
        throw new Exception("Twenty-three");
    }
}
```

始终打印：

```
java.lang.Exception: Twenty-three
```

## 15.11 字段访问

字段访问表达式可以使用点运算符引用对象或数组的字段。

```
FieldAccess:
    Primary . Identifier
    super . Identifier
```



# 字段访问表达式

字段访问表达式的类型是字段的类型，否则会发生编译错误。

## 15.11.1 使用初级表达式的字段访问

注意，在确定使用哪个字段时，使用的是 `Primary` 表达式的类型，而不是运行时引用的实际对象的类。

### 示例 15.11.1-1. 字段访问的静态绑定

```java
class S { int x = 0; }

class T extends S { int x = 1; }

class Test1 {

    public static void main(String[] args) {

        T t = new T();

        System.out.println("t.x=" + t.x + " when("t", t));

        S s = new S();

        System.out.println("s.x=" + s.x + " when("s", s));

        s = t;

        System.out.println("s.x=" + s.x + " when("s", s));

    }

    static String when(String name, Object t) {

        return name + "=" + ((S)t).x;

    }

}
```

打印结果：
```
t.x=1
s.x=0
s.x=0
```

```java
return when " + name + " holds a " 
+ t.getClass() + " at run time.
```

该程序产生以下输出：

```
t.x=1 when t holds a class T at run time.
s.x=0 when s holds a class S at run time.
s.x=0 when s holds a class T at run time.
```

最后一行显示，所访问的字段并不取决于所引用对象的运行时类；即使 `s` 持有一个指向类 `T` 对象的引用，表达式 `s.x` 指向的也是类 `S` 的 `x`，因为表达式 `s` 的类型是 `S`。类 `T` 的对象包含两个命名为 `x` 的字段，一个属于类 `T`，另一个属于其父类。

这种对字段访问缺乏动态查找机制[允许]程序通过简单的实现来高效运行。延迟绑定和重写机制是可用的，但仅在使用实例方法时有效。考虑以下使用实例方法访问字段的示例：

```java
class S { int x = 0; int z() { return x; } }

class T extends S { int x = 1; int z() { return x; } }

class Test2 {

  public static void main(String[] args) {

    T t = new T();

    System.out.println("t.z()=" + t.z() + " " + when("t", t));

    S s = new S();

    System.out.println("s.z()=" + s.z() + " " + when("s", s));

    s = t;

    System.out.println("s.z()=" + s.z() + " " + when("s", s));

  }

  static String when(String name, Object t) {

    return "when " + name + " holds a " + t.getClass() + " at run time.";

  }

}
```

现在的输出是：

```
t.z()=1 when t holds a class T at run time.
s.z()=0 when s holds a class S at run time.
s.z()=1 when s holds a class T at run time.
```

最后一行显示，所访问的方法确实取决于所引用对象的运行时类；当 `s` 持有一个指向类 `T` 对象的引用时，表达式 `s.z()` 指向方法 `T` 的 `z`，尽管表达式 `s` 的类型是 `S`。类 `T` 的方法 `z` 重写了类 `S` 的 `z`。

## 15.11.2 使用 super 访问父类成员

`super.Identifier` 形式指向当前对象的字段 `Identifier`，但将当前对象视为该类父类的一个实例。

`T.super.Identifier` 形式指向与 `T` 对应的词法作用实例的字段名 `Identifier`，但将该实例视为 `T` 父类的实例。

使用关键字 `super` 的形式仅在类的实例方法、实例初始化器或构造函数中，或者在类的实例变量初始化器中有效。如果它们出现在其他任何地方，将发生编译错误。

这些情况与类声明中可以使用 `this` 关键字的情况完全相同（§15.8.3）。

如果使用关键字 `super` 的形式出现在 `Object` 类的声明中，则是编译错误，因为 `Object` 没有父类。

假设字段访问表达式 `super.f` 出现在类 `C` 中，且 `C` 的直接父类是类 `S`。如果 `S` 中的 `f` 从类 `C` 可访问（§6.6），那么 `super.f` 被处理为在类 `S` 的体中具有表达式 `this.f`。否则，将发生编译错误。

> 因此，`super.f` 可以访问类 `S` 中可访问的字段，即使该字段被类 `C` 中字段 `f` 的声明所隐藏。

假设字段访问表达式 `T.super.f` 出现在类 `C` 中，且类 `T` 的直接父类是一个全限定名为 `S` 的类。如果 `f` 从 `C` 可访问，那么 `T.super.f` 被处理为在类 `S` 的体中具有表达式 `this.f`。否则，将发生编译错误。

因此，`T.super.f` 可以访问类 `S` 中可访问的字段，即使该字段被类 `T` 中字段 `f` 的声明所隐藏。

如果当前类不是类 `T` 的内部类或 `T` 本身，则是编译错误。

### 示例 15.11.2-1. super 表达式

```java
interface I {
    int x = 0; 
}

class T1 implements I { int x = 1; }

class T2 extends T1 { int x = 2; }

class T3 extends T2 {
    int x = 3;

    void test() {
        System.out.println("*x=\t\t" + x);
        System.out.println("*super.x=\t\t" + super.x);
        System.out.println("((T2)this).x=\t" + ((T2)this).x);
        System.out.println("((T1)this).x=\t" + ((T1)this).x);
        System.out.println("((I)this).x=\t" + ((I)this).x);
    }
}

class Test {
    public static void main(String[] args) {
        new T3().test();
    }
}
```

该程序产生以下输出：

```
x=3
super.x=2
((T2)this).x=2
((T1)this).x=1
((I)this).x=0
```

在类 `T3` 中，`super.x` 的效果与 `((T2)this).x` 相同。注意，由于访问权限，`super.x` 并没有指定类型转换。

## 15.12 方法调用

方法调用表达式用于调用类或实例。

```
MethodInvocation:
    MethodName ( ArgumentList )
    TypeName . [TypeArguments] Identifier ( ArgumentList )
    ExpressionName . [TypeArguments] Identifier ( ArgumentList )
    Primary . [TypeArguments] Identifier ( ArgumentList )
    super . [TypeArguments] Identifier ( ArgumentList )
    TypeName . super . [TypeArguments] Identifier ( ArgumentList )

ArgumentList:
    { Expression }
```

由于存在重载的可能性，在编译时解析方法比解析字段要更复杂。由于存在实例方法的可能性，在运行时调用方法也更复杂。方法调用的确定在 §15.12.3 中规定。

方法调用表达式可能抛出的异常类型可以在 §11.2 中指定。

如果任何类型参数是通配符（§4.5.1），则是编译错误。

如果满足以下所有条件，则方法调用是一个多表达式（poly expression）：

- 计算调用出现在赋值上下文中或调用上下文中（§5.2, §5.3）。
- 如果调用是限定的（即除第一个以外的任何 `MethodInvocation`），则省略到 `Identifier` 的左侧。

要调用的方法由以下小节确定，泛型（§8.4.4）和

### 15.12.1 编译时步骤 1：确定类或接口

在编译时处理方法调用的第一步是确定要调用的方法名以及搜索哪个类或接口。

方法名由紧邻 `MethodInvocation` 左括号的 `MethodName` 或 `Identifier` 指定。

对于搜索的类或接口，有六种情况，取决于 `MethodInvocation` 左括号之前的形式：

- 如果形式是 `MethodName`，即一个 `Identifier`，那么：
    - 如果 `Identifier` 出现在方法声明的作用范围内（§6.3, §6.4.1），则：
        - 如果存在该方法的包围类型声明，令 `au` 为最内层的类型声明。搜索的类或接口是 `au`。
        这种搜索策略被称为“梳子规则”（comb rule）。它实际上是在嵌套类的父类层次中查找方法之前，先在包围类及其父类层次中查找方法。示例见 §6.5.7.1。
    - 否则，方法声明可能通过一个或多个单静态导入或按需静态导入处于范围内。没有需要搜索的类或接口，因此稍后确定方法（15.12.2.1）。

- 如果形式是 `TypeName . [TypeArguments] Identifier`，则要搜索的类型是 `TypeName` 指定的类型。

- 如果形式是 `ExpressionName . [TypeArguments] Identifier`，则搜索的类或接口是由 `ExpressionName` 指定变量的声明类型 `au`（如果 `au` 是类或接口类型），或者是 `au` 的上界（如果 `au` 是类型变量）。

- 如果形式为 `Primary . [TypeArguments] Identifier`，则令 `τ` 为 `Primary` 表达式的类型。如果 `τ` 是类类型或接口类型，或者 `τ` 的上界是一个类型变量，则要搜索的类或接口为 `τ`。如果 `τ` 不是引用类型，则为编译时错误。

- 如果形式为 `super . [TypeArguments] Identifier`，则要搜索的类是包含该方法调用声明的类的父类。令 `τ` 为紧接包含该方法调用的类型声明。如果 `τ` 是 `Object` 类或 `τ` 是一个接口，则为编译时错误。

- 如果形式为 `TypeName . super . [TypeArguments] Identifier`，则：
    - 如果 `TypeName` 既不表示类也不表示接口，则为编译时错误。
    - 如果 `TypeName` 表示一个类 `C`，则要搜索的类是 `C` 的父类。如果 `C` 不是当前类的词法闭包类型声明，或者 `C` 是 `Object` 类，则为编译时错误。令 `τ` 为紧接包含该方法调用的类型声明。如果 `τ` 是 `Object` 类，则为编译时错误。
    - 否则，`TypeName` 表示要搜索的接口 `I`。令 `τ` 为紧接包含该方法调用的类型声明。如果 `I` 不是 `τ` 的直接超接口，或者存在 `τ` 的某个其他父类或直接超接口 `J`，使得 `J` 是 `I` 的子类型，则为编译时错误。

`TypeName . super` 语法是重载的：传统上，`TypeName` 指向词法闭包的类声明，目标是该类的父类，因为该调用在词法闭包类型声明中是一个未限定的 `super`。

```java
class Superclass {
    void foo() { System.out.println("Hi"); }
}
class Subclass extends Superclass {
    void foo() { throw new UnsupportedOperationException(); }
}
Runnable tweak = new Runnable() {
    void run() {
        Subclass.super.foo(); // 获取 'println' 行为
    }
};
```

为了支持对超接口中默认方法的调用，`TypeName` 也可以指向当前类或接口的直接超接口，目标是该超接口。

```java
interface Superinterface {
    default void foo() { System.out.println("Hi"); }
}

class Subclass2 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); };

    void tweak() {
        Superinterface.super.foo(); // 获取 'println' 行为
    }
}
```

没有语法支持这些形式，即：在词法闭包的类类型声明中调用超接口方法，就好像该调用在词法闭包类型声明中的形式为 `InterfaceName.super` 一样。

```java
class Subclass3 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); };

    Runnable tweak = new Runnable() {
        void run() {
            Subclass3.Superinterface.super.foo(); // 非法
        }
    }
}
```

解决方法是在词法闭包类型声明中引入一个私有方法，来执行接口 `super` 调用。

### 15.12.2 编译时步骤 2：确定方法签名

第二步在上一步定义的类型中搜索成员方法。该步骤使用方法名和参数表达式来定位既可访问又适用的方法，即可以在给定参数上正确调用的声明。

可能有多个方法，在这种情况下将选择最具体的一个。最具体方法的描述符（签名加返回类型）是运行时用于执行方法分派的方法。

某些包含隐式类型 lambda 表达式（§15.27.1）或不精确方法引用（§15.13.1）的参数表达式会被适用性测试忽略，因为在选择调用的目标类型之前无法确定它们的含义。另一方面，只有参数表达式——而不是调用的目标类型——影响适用性测试，即使方法调用表达式是一个多态表达式。

确定适用性的过程始于确定可能适用的方法（§15.12.2.1）。然后，为了确保与 Java SE 5.0 之前的 Java 编程语言兼容，过程分为三个阶段：

- **第一阶段**执行重载解析，但不允许装箱或拆箱转换，或使用变长方法调用。如果在此阶段没有找到适用方法，则处理继续到第二阶段。
  这保证了任何在 SE 5.0 之前的 Java 编程语言中有效的调用，都不会因为引入变长方法、隐式装箱和/或拆箱而被视为歧义。然而，变长方法（§8.4）的声明可能会改变为给定方法调用所选择的方法，因为变长方法在第一阶段被视为固定长度参数的方法。例如，声明一个已经声明了 `m(Object)` 的类会导致 `m(Object)` 不再被用于某些调用表达式（如 `m(null)`），因为 `m(Object[])` 更具体。

- **第二阶段**执行重载解析，同时允许装箱和拆箱，但仍然禁止使用变长方法调用。如果在此阶段没有找到适用方法，则处理继续到第三阶段。
  这确保了如果一个方法通过固定长度参数的方法调用是适用的，则绝不会通过变长方法调用被选择。

- **第三阶段**允许重载与变长方法结合。如果一个方法通过严格调用（第一阶段，§15.12.2）、宽松调用（第二阶段，§15.12.2.3）或变长调用（第三阶段，§15.12.2.4）适用的，则该方法是适用的。

为了检查适用性，分析的输入是参数列表。如果在其中一个阶段中识别出多个适用方法，则按照第 15.12.2.5 节规定选择最具体的一个。



注意重载解析独立于目标类型。这是出于两个原因：

- 第一，它使用用户模型更易用且更不容易出错。方法的含义（即与名称对应的声明）是如此基础的，不至于依赖微妙的上下文提示。（相比之下，其他程序的行为取决于目标类型而不同；但对于一组共享相同名称和参数个数的任意方法，可以做出这种保证）。
- 第二，它允许其他属性——例如方法是否为多态表达式（`§15.12`）或对条件表达式进行分类（`§15.25`）——在确定目标类型之前依赖于方法名的含义。

### 示例 15.12.2-1 方法的适用性

```java
class Doubler {
    static int two() { return two(1); }
    private static int two(int i) { return 2*i; }
}
class Test extends Doubler {
    static long two(long j) { return j+j; }
}

public static void main(String[] args) {
    System.out.println(two(3));
    System.out.println(Doubler.two(3)); // 编译错误
}
```

对于类 `Doubler` 内部的方法调用 `two(1)`，有两个名为 `two` 的可访问方法，但只有一个是适用的，因此在运行时执行该方法。

对于类 `Test` 内部的方法调用 `two(3)`，有两个适用方法，但只有类 `Test` 中的那个是可访问的，因此在运行时执行该方法（参数 `3` 被转换为类型 `long`）。

对于方法调用 `Doubler.two(3)`，搜索的是 `Doubler` 类（而不是 `Test` 类）中名为 `two` 的方法；由于唯一的适用方法是不可访问的，因此此方法调用导致了编译错误。

另一个示例是：

## 15.12 方法调用表达式 EXPRESSIONS

```java
class ColoredPoint {
    int x, y;
    byte color;
    void setColor(byte color) { this.color = color; }
}
class Test {
    public static void main(String[] args) {
    ColoredPoint cp = new ColoredPoint();
    byte color = 37;
    cp.setColor(color);
    cp.setColor(37); // 编译时错误
    }
}
```

在这里，第二次调用 `setColor` 时发生了编译时错误，因为在编译时无法找到适用的方法。字面量 `37` 的类型是 `int`，并且无法通过调用转换（invocation conversion）转换为 `byte`。在变量 `color` 初始化时使用的赋值转换（Assignment conversion）执行了从 `int` 类型到 `byte` 的隐式转换，这是允许的，因为值 `37` 足够小，可以用 `byte` 类型表示；但这种转换不允许用于调用转换。

如果方法 `setColor` 被声明为接收 `int` 而不是 `byte`，那么两种调用都是正确的；第一次调用将被允许，因为调用转换允许从 `byte` 到 `int` 的宽转换。然而，在 `setColor` 的体中需要一个收窄强制转换：

```java
void setColor(int color) { this.color = (byte)color; }
```

这是一个重载歧义的示例。考虑以下程序：

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }
class Test {
    static void test(ColoredPoint p, Point q) {
        System.out.println("ColoredPoint, Point*");
    }
    static void test(Point p, ColoredPoint q) {
        System.out.println("Point, ColoredPoint*");
    }
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        test(cp, cp); // 编译时错误
    }
}
```

此示例在编译时产生错误。问题在于有两个适用且可访问的 `test` 声明，且没有一个比另一个更具体。因此，该方法调用是歧义性。

如果添加了第三个 `test` 定义：

```java
static void test(ColoredPoint p, ColoredPoint q) {
    System.out.println("*ColoredPoint, ColoredPoint*");
}
```

那么它将比其他两个更具体，方法调用将不再具有歧义性。

### 示例 15.12.2.- 在方法选择时不考虑返回类型

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }
class Test {
    static int test(ColoredPoint p) {
        return p.color;
    }
    static String test(Point p) {
        return "Point";
    }
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        String s = test(cp); // 编译时错误
    }
}
```

在这里，方法 `test` 最具体的描述是接收 `ColoredPoint` 类型参数的。由于方法的返回类型为 `int`，因此发生了编译时错误，因为 `int` 无法通过赋值转换转换为 `String`。这个示例表明，方法的的结果不参与重载方法的解析，因此返回 `String` 的第二个 `test` 方法未选中，尽管它允许示例程序无错误地编译。

### 示例 15.12.2-3. 选择最具体的方法

最具体的方法是在编译时选择的；它的描述符决定了运行时实际执行哪个方法。如果类中添加了新方法，使用旧类定义编译的源代码可能不会使用该新方法，即使重新编译会导致其使用该方法。

因此，考虑两个编译单元，一个用于类 `Point`：

```java
package points;
public class Point {
    public int x, y;
    public Point(int x, int y) { this.x = x; this.y = y; }
    public String toString() { return "*"; }
    public String toString(String s) {
        return "(" + x + "," + s + ")";
    }
}
```

另一个用于类 `ColoredPoint`：

```java
package points;
public class ColoredPoint extends Point {
    public static int RED = 0, GREEN = 1, BLUE = 2;
    public static String[] COLORS = {"red", "green", "blue"};
    public byte color;

    public ColoredPoint(int x, int y, int color) {
        super(x, y);
        this.color = (byte)color;
    }

    /**
     * 将参数的所有相关字段拷贝到此对象。
     */
    public void adopt(Point p) { 
        this.x = p.x; this.y = p.y; 
    }

    public String toString() {
        String s = COLORS[color];
        return super.toString(s);
    }
}
```

现在考虑使用 `ColoredPoint` 的第三个编译单元：

```java
import points.*;
class Test {
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint(6, 6, ColoredPoint.RED);
        ColoredPoint cp2 = new ColoredPoint(3, 3, ColoredPoint.GREEN);
        cp.adopt(cp2);
        System.out.println("cp: " + cp);
    }
}
```

输出是：

`cp: (3,3)`

编写 `Test` 类的程序员期望看到 green，因为实际参数 `ColoredPoint` 有一个 `color` 字段，并且 `color` 似乎是“相关字段”。注意，通过最具体的方法（唯一的适用方法），`adopt` 方法的签名表示有一个参数，且参数类型为 `Point`。该签名成为 `Test` 类的二进制表示的一部分并在方法调用中使用。

假设程序员报告了这个错误，`points` 包的维护者在深量后决定通过向 `ColoredPoint` 添加一个方法来修复它：

```java
public void adopt(Point p) {
  if (p instanceof ColoredPoint) {
    this.color = ((ColoredPoint)p).color;
  }
  this.x = p.x; this.y = p.y;
}
```

如果程序员使用新的 `ColoredPoint` 二进制运行旧的 `Test`，输出是：

`(3,3)`

如果重新编译 `Test` 的源码，Java 编译器将发现现在有两个适用方法，且更具体的那个签名是“一个类型为 ColoredPoint 的参数”，运行程序将产生预期的输出：

`(3,3)`

对于此类问题，`points` 包的维护者可以通过对 `adopt` 方法编写防御性代码，让 `ColoredPoint` 兼容新编译的代码和旧代码：

```java
public void adopt(Point p) {
  if (p instanceof ColoredPoint) {
    this.color = ((ColoredPoint)p).color;
  }
  this.x = p.x; this.y = p.y;
}
```

理想情况下，每当依赖的代码发生变化时，都应该重新编译。然而，在不同组织维护不同类的环境中，这是不可行的。对类演变问题进行防御性编程可以使升级的代码更加健壮。关于二进制兼容性和类型演变的详细讨论，见 `§13`（二进制兼容性）。

### 15.12.2.1 识别适用方法

搜索编译时步骤1确定的类或接口，寻找对该方法调用适用的成员方法；继承自超类和超接口的成员也包含在此搜索中。

此外，如果方法调用的形式是 `MethodName` —— 即单个标识符，那么对适用方法的搜索还将检查由方法调用发生编译单元（`§7.5.3`, `§7.5.4`）中的静态导入声明和按需静态导入声明的所有成员方法，且这些方法在方法调用出现的地方未被遮蔽。

方法对方法调用是适用的，当且仅当以下所有条件均满足：

- 成员名称与方法调用中的方法名称相同。
- 该成员对于方法调用出现的类或接口是可访问的（`§6.6`）。成员在方法调用处是否访问取决于访问修饰符（public, protected, 无修饰符（包）或 private）、编译时步骤1确定的类或接口的继承关系，以及方法调用出现的位置。
- 如果成员是参数数为 $n$ 的固定参数方法，则方法调用的参数个数等于 $n$，并且对于所有 $i$ ($1 \le i \le n$)，方法调用的第 $i$ 个参数与第 $i$ 个参数的类型潜在兼容。
- 如果成员是参数数为 $n$ 的变长参数方法，则对于所有 $i$ ($1 \le i \le n-1$)，方法调用的第 $i$ 个参数与第 $i$ 个参数的类型潜在兼容；且当方法的第 $n$ 个参数类型为 $T[]$ 时，满足以下任一即可：
    - 方法调用的参数个数等于 $n$。
    - 方法调用的参数个数等于 $n$，且方法调用的第 $n$ 个参数潜在兼容 $\tau$ 或 $T[]$。
    - 方法调用的参数个数为 $m$，其中 $m > n$，且对于所有 $i$ ($n \le i \le m$)，方法调用的第 $i$ 个参数潜在兼容 $\tau$。
- 如果方法调用包含了式类型，且成员是泛型方法，则类型参数的数量等于类型参数的数量。

此句意味着，非泛型方法对于提供式类型参数的调用可能是适用的。事实上，它可能证明是适用的。在这种情况下，类型参数将被简单忽略。

该规则源于兼容性问题和替换原则。由于接口或超类可以独立于其子类是泛型的，它们用非泛型方法覆盖泛型方法。然而，覆盖方法（非泛型）必须适用于泛型方法的调用，包括那些

# 表达式

## 方法调用表达式 15.12

显式地传递类型参数。否则，子类型将无法替换其泛型超类类型。

如果搜索没有产生至少一个潜在适用的方法，则发生编译时错误。

根据以下规则，表达式与目标类型可能是潜在兼容的：

- 如果 Lambda 表达式简体`15.27`) 满足以下所有条件，则该 Lambda 表达式与函数式接口类型 $T$ (`§9.8`) 可能是潜在兼容的：
    - $T$ 的函数类型数组简体`9.9`) 与该 Lambda 表达式相同。
    - 如果 $T$ 的函数类型具有 `void` 返回类型，则 Lambda 体是一个语句表达式简体`14.8`) 或 `void` 兼容块简体`15.27.2`)。
    - 如果 $T$ 的函数类型具有（非 `void`）返回类型，则 Lambda 体是一个表达式或值兼容块简体`15.27.1`)。
- 如果方法引用表达式简体`15.13`) 的 $T$ 的函数类型元数（arity）为 $n$，且当方法引用表达式目标元数为 $n$ 的函数类型时至少存在一个适用的方法简体`15.13.1`)，并且满足以下条件之一：
    - 方法引用表达式具有 `ReferenceType :: [TypeArguments]` 标识符的形式，且至少一个潜在适用的方法要么是 (i) `static` 且支持元数 $n$，或 (ii) 非 `static` 且支持元数 $n-1$。
    - 方法引用表达式具有其他形式，且至少一个潜在适用的方法不是 `static`。
- 如果类型变量是候选方法的类型参数，则 Lambda 表达式或方法引用表达式与该类型可能是潜在兼容的。
- 如果括号表达式简体`15.8.5`) 所包含的表达式与该类型潜在兼容，则该括号表达式也与该类型可能是潜在兼容的。
- 如果条件表达式简体`15.25`) 的第二个和第三个操作数表达式都与该类型潜在兼容，则该条件表达式与该类型可能是潜在兼容的。
- 如果 switch 表达式简体`15.28`) 的所有结果表达式都与该类型潜在兼容，则该 switch 表达式与该类型可能是潜在兼容的。
- 类实例创建表达式、方法调用表达式或独立形式的表达式简体`15.2`) 与任何类型都是潜在兼容的。

潜在适用性的定义超出了基础的元数检查，它考虑了函数式接口类型的存在和“形状”。在涉及类型推断的情况下，作为方法调用参数出现的 Lambda 表达式在重载解析完成之前无法确定正确类型。这些规则允许仍然考虑 Lambda 表达式的形式，从而丢弃那些可能导致歧义错误的明显错误的目标类型。

### 15.12.2.2 第 1 阶段：匹配严格调用适用的元数方法

参数表达式被认为对于潜在适用方法的适用性具有“相关性”（pertinent），除非它具有以下形式之一：

- 隐式类型化 Lambda 表达式简体`15.27.1`)。
- 不精确方法引用表达式简体`15.13.1`)。
- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则对应目标类型（从 $m$ 的签名派生）的显式类型化 Lambda 表达式或不精确方法引用表达式是 $m$ 的类型参数。
- 其体为不与适用性相关的表达式的显式类型化 Lambda 表达式。
- 其体为块的显式类型化 Lambda 表达式，其中至少有一个结果表达式不与适用性相关。
- 包含的表达式不与适用性相关的括号表达式简体`15.8.5`)。
- 第二个或第三个操作数不与适用性相关的条件表达式简体`15.25`)。

令 $m$ 为元数为 $n$ 形式参数类型为 $E_1 ... E_n$ 的潜在适用方法简体`15.12.2.1`)，令 $e_1, ..., e_n$ 为方法调用的实际参数表达式。那么：

- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则它们的适用性按照 `§18.5.1` 指定进行推断。
- 如果 $m$ 是泛型方法且方法调用提供了显式类型参数，令 $R_1 ... R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，令 $U_1, ..., U_p$ 为方法调用中给出的显式类型参数。如果满足以下两个条件，则 $m$ 通过严格调用是**适用**的：



### 15.12.2.2 第 1 阶段：识别严格调用适用的方法

令 $m$ 为元数为 $n$、形式参数类型为 $F_1 \dots F_n$ 的潜在适用方法（§15.12.2.1），令 $e_1, \dots, e_n$ 为方法调用的实际参数表达式。那么：

- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则其适用性按照 §18.5.1 进行推断。

- 如果 $m$ 是泛型方法且方法调用提供了显式类型参数，令 $R_1 \dots R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，令 $U_1, \dots, U_p$ 为方法调用中给出的显式类型参数。如果满足以下条件，则 $m$ 通过严格调用是**适用**的：

    - $1 \le i \le n$，如果 $e_i$ 与适用性相关（§15.12.2），则 $e_i$ 在严格调用上下文中与 $F_i[R_i:=U_i], \dots, R_n:=U_n]$ 兼容（§5.3）。

    - $1 \le l \le p$，$U_l <: B_l[R_l:=U_l], \dots, R_p:=U_p]$。

- 如果 $m$ 不是泛型方法，则对于 $1 \le i \le n$，如果 $e_i$ 在严格调用上下文中与 $F_i$ 兼容（§5.3）或 $e_i$ 不与适用性相关，则 $m$ 通过严格调用是**适用**的。

如果没有找到通过严格调用适用的方法，则适用方法的搜索继续进入第 2 阶段（§15.12.2）。否则，在严格调用适用的方法中选择最具体的方法（§15.12.5）。Lambda 表达式或不精确方法表达式的含义不足以确定目标类型，这些表达式被忽略，直到重载解析完成。

### 15.12.2.3 第 2 阶段：识别松散调用适用的方法

令 $m$ 为元数为 $n$、形式参数类型为 $F_1 \dots F_n$ 的潜在适用方法（§15.12.2.1），令 $e_1, \dots, e_n$ 为方法调用的实际参数表达式。那么：

- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则其适用性按照 §18.5.1 进行推断。

- 如果 $m$ 是泛型方法且方法调用提供了显式类型参数，令 $R_1 \dots R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，令 $U_1, \dots, U_p$ 为方法调用中给出的显式类型参数。如果满足以下条件，则 $m$ 通过松散调用是**适用**的：

    - $1 \le i \le n$，如果 $e_i$ 与适用性相关（§15.12.2），则 $e_i$ 在松散调用上下文中与 $F_i[R_i:=U_i], \dots, R_n:=U_n]$ 兼容（§5.3）。

    - $1 \le l \le p$，$U_l <: B_l[R_l:=U_l], \dots, R_p:=U_p]$。

- 如果 $m$ 不是泛型方法，则对于 $1 \le i \le n$，如果 $e_i$ 在松散调用上下文中与 $F_i$ 兼容（§5.3）或 $e_i$ 不与适用性相关。

如果没有找到通过松散调用适用的方法，则继续搜索适用方法的方法（§15.12.3）。否则，在松散调用适用的方法中选择最具体的方法（§15.12.5）。Lambda 表达式或不精确方法表达式的含义不足以确定目标类型，这些表达式被忽略，直到重载解析完成。

### 15.12.2.4 第 3 阶段：识别变长调用适用的方法

其中变长方法的形式参数类型为 $F_1, \dots, F_{n-1}, F_n$，令方法的 $i$ 个变长参数类型定义如下：

- 对于 $i \le n-1$，方法的 $i$ 个变长参数类型为 $F_i$。
- 对于 $i \ge n$，方法的 $i$ 个变长参数类型为 $F_n$。

令 $m$ 为变长元数的潜在适用方法（§15.12.2.1），令 $T_1, \dots, T_k$ 为 $m$ 的前 $k$ 个变长参数类型，令 $e_1, \dots, e_k$ 为方法调用的实际参数。

- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则方法的适用性按照 §18.5.1 进行推断。

- 如果 $m$ 是泛型方法且方法调用提供了显式类型参数，则 $R_1, \dots, R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，令 $U_1, \dots, U_p$ 为方法调用中给出的显式类型参数。那么 $m$ 通过变长调用是**适用**的，如果满足：

    - $1 \le i \le k$，如果 $e_i$ 与适用性相关（§15.12.2.2），则 $e_i$ 在松散调用上下文中与 $T_i[R_i:=U_i], \dots, T_k[R_k:=U_k]$ 兼容（§5.3）。

    - $1 \le i \le p$，$U_i <: B_i[R_i:=U_i], \dots, U_p:=U_p]$。

- 如果 $m$ 不是泛型，则对于 $1 \le i \le k$，如果 $e_i$ 在松散调用上下文中与 $T_i$ 兼容（§5.3）或 $e_i$ 不与适用性相关。

如果没有找到通过变长调用适用的方法，则发生编译时错误。否则，在变长调用适用的方法中选择最具体的方法（§15.12.5）。

### 15.12.2.5 选择最具体的方法

如果多个成员方法都既可访问又适用于方法调用，则需要选择一个来提供运行时描述符。

- 设 $P_1, \dots, P_n$ 为 $MT_S$ 的形式参数类型，并已适配 $MT_T$ 的类型参数。设 $P_1', \dots, P_n'$ 为 $S$ 函数类型（不含捕获）的形式参数类型，并已适配 $MT_T$ 的类型参数。设 $Q_1, \dots, Q_n$ 为 $MT_T$ 的形式参数类型。那么，对于所有的 $i$ ($1 \leq i \leq n$)，$Q_i <: P_i$ 且 $Q_i = P_i'$。

通常情况下，该规则断言从 $S$ 和 $\tau$ 派出的形式参数类型是相同的。但在 $S$ 是通配符参数化类型的情况下，检查更为复杂，以便允许捕获变量出现在形式参数类型中：首先，$\tau$ 的每个形式参数类型必须是 $S$ 的捕获的对应的形式参数类型的子类型；其次，在将通配符映射到其边界（§9.9）后，结果函数类型的形式参数类型是相同的。

设 $R_S$ 为 $MT_S$ 的返回类型，并已适配 $MT_T$ 的类型参数，设 $R_T$ 为 $MT_T$ 的返回类型。必须满足以下条件之一：

- $e$ 是一个显式类型的 lambda 表达式（§15.27.1），且满足以下任一：

  - $R_T$ 为 void。

  - $R_S <: R_T$。

  - $R_S$ 和 $R_T$ 是函数接口类型，且至少存在一个结果表达式，并且对于 $e$ 的每个结果表达式，$R_S$ 都比 $R_T$ 具体。

- 具有块主体的 lambda 表达式的结果定义在 §15.27.2 中；具有表达式主体的 lambda 表达式的结果直接为主体本身。

- $R_S$ 是基本类型，$R_T$ 是引用类型，且至少存在一个结果表达式，并且 $e$ 的每个结果表达式都是基本类型的独立表达式（§15.2）。

- $R_S$ 是引用类型，$R_T$ 是基本类型，且至少存在一个结果表达式，并且 $e$ 的每个结果表达式都是引用类型的独立表达式或多态表达式。

- $e$ 是一个精确方法表达式（§15.13.1），且满足以下任一：

  - $R_T$ 为 void。

  - $R_S <: R_T$。

  - $R_S$ 是基本类型，$R_T$ 是引用类型，且方法引用的编译时声明的返回类型为基本类型。

  - $R_S$ 是引用类型，$R_T$ 是基本类型，且方法引用的编译时声明的返回类型为引用类型。

- $e$ 是带括号的表达式，对于第二个和第三个操作数，这些条件之一递归应用于所包含的表达式。

- $e$ 是一个 `switch` 表达式，并且对于它的每个结果表达式，这些条件之一递归应用。

一个方法 $m_1$ 比另一个方法 $m_2$ *严格具体*（strictly specific），当且仅当 $m_1$ 比 $m_2$ 具体且 $m_2$ 不比 $m_1$ 具体。

如果一个方法对于方法调用是极大具体（maximally specific）的，则意味着它是可访问且适用的，并且没有其他可访问且适用的方法比它更具体。

如果恰好只有一个极大具体方法，那么该方法实际上是最具体的方法；它一定比任何其他可访问且适用的方法都具体。随后，它将按照 15.12.3 中指定的进行进一步的编译时检查。

可能不存在最具体的方法，因为存在两个或多个方法是极大具体的方法。在这种情况下：

- 如果所有极大具体方法都具有覆盖等价的签名（§8.4.2），并且所有极大具体方法中恰好有一个是具体的（即既不是*抽象*的也不是默认的），那么该方法就是最具体的方法。

- 否则，如果所有极大具体方法都具有覆盖等价的签名，且所有极大具体方法都是*抽象*或默认的，且这些方法的声明具有相同的擦除参数类型，并且根据下面的规则至少有一个极大具体方法是被优选的，则在优选的极大具体方法子集中任意选择一个作为最具体方法。此时该最具体方法被认为是*抽象*的。

如果一个极大具体方法满足以下条件，则它是被优选的：

- 它的签名是每个极大具体方法签名的子签名；且

- 它的返回类型 $R$（可能是 *void*），其中 $R$ 与每个极大具体方法的返回类型相同，或者 $R$ 是引用类型且是每个极大具体方法返回类型的子类型（在两个方法具有相同签名的情况下，对任何类型参数进行适配（§8.4.4）后）。

如果根据上述规则不存在优选方法，则一个极大具体方法在满足以下条件时是**优选**的：

- 它的签名是每个极大具体方法签名的子签名；且

- 与目标类型兼容。

最具体方法抛出的类型派生方式如下：

1. 如果该具体方法是泛型的，首先对 `throws` 子句进行适配。如果具体方法不是泛型的，但至少一个可用方法是泛型的，则首先擦除 `throws` 子句。

2. 然后，抛出的类型包括满足每个类型 $E$：

    - $E$ 出现在某个 `throws` 子句中。

    - 对于每个 `throws` 子句，$E$ 是该子句中所述类型的子类型。

### 15.12.2.6 调用类型

方法的*调用类型*是一个表示目标参数、结果（返回类型或 `void`）以及异常类型的类型。其确定方式如下：

- 如果方法是泛型的且方法调用提供了类型参数，设 $P_i$ 为方法的类型参数，$T_i$ 为方法调用提供的类型参数 $(1 \le i \le p)$。

- 如果为了使方法可用需要检查转换，则调用类型的参数类型通过 $[P_i:=T_i, \dots, P_p:=T_p]$ 应用于方法的参数类型，且调用类型的返回类型和异常类型为方法的返回类型和异常类型的擦除。

- 如果为了使方法可用不需要检查转换，则调用类型通过 $[P_i:=T_i, \dots, P_p:=T_p]$ 应用于方法。

- 如果方法不是泛型的，则：

  - 如果为了使方法可用需要检查转换，则调用类型的参数类型为方法的参数类型，且调用类型的返回类型和异常类型为方法的返回类型和异常类型的擦除。

  - 否则，如果所选方法与 `Object` 类（§4.3.2）的 `getClass` 方法相同，则调用类型与方法相同，但返回类型为 `Class<? extends [tau]>`，其中 $tau$ 是通过 §15.12.1 确定的类型，$[tau]$ 表示 $tau$ 的擦除。

  - 否则，调用类型与方法类型相同。

### 15.12.3 编译时步骤 3：所选方法是否合适？

如果方法调用存在最具体方法声明，则该声明被称为方法调用的 `编译时声明`。

如果方法的参数与其目标类型不兼容（从编译时声明的调用类型派生），则为编译时错误。

如果编译时声明可以通过变长调用来适用，且该方法调用类型的最后一个形式参数类型为 $F_n[]$，则如果该类型 $F_n$ 的擦除在调用点是不可访问的（§6.6），则为编译时错误。

如果编译时声明为 `void`，则方法调用必须是一个顶层表达式（即表达式语句中的 `Expression`，或 `for` 语句中的 `ForInit` 或 `ForUpdate` 部分），否则会发生编译时错误。此类方法调用不产生值，且只能在不需要值的情况下使用。

此外，编译时声明是否合适可能取决于左括号之前方法调用表达式的形式，如下所示：

- 如果形式为 `MethodName` —— 即仅为 `Identifier` 且编译时声明是实例方法：

  - 如果方法调用发生在静态上下文中（§8.1.3），则会发生编译时错误。

  - 否则，令 `c` 为该编译时声明作为成员的直接外部类。如果该方法调用没有被 `c` 的内部类直接包含，则会发生编译时错误。

- 如果形式为 `TypeName . [Arguments] Identifier`，则编译时声明必须是 `static` 的，否则会发生编译时错误。

- 如果形式为 `ExpressionName . [Arguments] Identifier` 或 `Primary . [TypeArguments] Identifier`，则编译时声明不能是在接口中声明的 `static` 方法，否则会发生编译时错误。

- 如果形式为 `super . [Arguments] Identifier`，则：

  - 如果编译时声明是 `abstract` 的，则会发生编译时错误。

  - 如果方法调用发生在静态上下文中，则会发生编译时错误。

- 如果形式为 `TypeName.super . [Arguments] Identifier`，则：

  - 如果编译时声明是 `abstract` 的，则会发生编译时错误。

  - 如果方法调用发生在静态上下文中，则会发生编译时错误。

- 如果 `TypeName` 声明了一个类 `c`，则如果方法调用没有被 `c` 或 `c` 的内部类直接包含，则会发生编译时错误。

- 如果 `TypeName` 表示一个接口，令 `τ` 为直接外部方法方法的类型声明。如果存在一个与编译时声明不同的方法，它覆盖（§9.4.1）了 `τ` 的直接父类或直接父接口的编译时声明，则会发生编译时错误。

在父接口覆盖了在祖父接口中声明的方法的情况下，此规则防止了子接口通过简单地将祖父接口添加到其父接口列表中来“跳过”覆盖。访问祖父接口功能的正确方法是通过直接父接口，且仅当该接口选择暴露所需的行为时可行。（或者，程序员也可以自由定义一个额外的父接口，该接口通过 `super` 方法调用来暴露所需的行为）。

### 15.12 方法调用表达式

编译时参数类型和编译时结果按如下方式确定：

- 如果方法调用的编译时声明不是签名多态方法，则：

  - 编译时参数类型是编译时声明中形式参数的类型。

  - 编译时结果是编译时声明调用类型的结果（§15.12.2.6）。

- 如果方法调用的编译时声明是签名多态方法，则：

  - 编译时参数类型是实际参数表达式的类型。作为空字面量 `null`（§3.10.7）的参数表达式被视为具有 `Void` 类型。

  - 编译时结果确定为：

    - 如果该签名多态方法是 `void` 或具有除 `Object` 以外的返回类型，则编译时结果是编译时声明调用类型的结果（§15.12.2.6）。

    - 否则，如果方法调用表达式是一个表达式语句，则编译时结果为 `void`。

    - 否则，如果方法调用表达式是类型转换表达式（§15.16）的操作数，则编译时结果是类型转换表达式类型的擦除类型（§4.6）。

    - 否则，编译时结果为签名多态方法的返回类型 `Object`。

如果满足以下所有条件，则该方法是签名多态的：

- 它在 `java.lang.invoke.MethodHandle` 类或 `java.lang.invoke.VarHandle` 类中声明。

- 它具有一个单一的变长参数（§8.4.1），其声明类型为 `Object[]`。

- 它是 `native` 的。

随后，以下编译时信息将与方法调用关联，供运行时使用：

- 方法名。

- 方法调用的限定类型（§13.1）。

- 参数数量和编译时参数类型，按顺序排列。

- 调用方式，按如下方式计算：

  - 如果编译时声明具有 `static` 修饰符，则调用方式为 `static`。

  - 否则，如果方法调用左括号之前的形式为 `super . Identifier` 或 `TypeName . super . Identifier` 形式，则调用方式为 `super`。

  - 否则，如果方法调用的限定类型是接口，则调用方式为 `interface`。

  - 否则，调用方式为 `virtual`。

如果编译时声明调用类型的结果不是 `void`，则通过对编译时声明的返回类型应用捕获转换（§5.10）获取方法调用的类型。

### 15.12.4 方法调用的运行时评估

在运行时，方法调用需要五个步骤。首先，可能计算目标引用。其次，求值参数表达式。第三，检查调用方法的访问权限。第四，执行方法代码。第五，创建激活帧，必要时执行同步，并将控制转移到方法。

#### 15.12.4.1 计算目标引用（必要时）

根据方法调用的形式，有六种情况需要考虑：

- 如果调用为 `MethodName` —— 即仅为 `Identifier` —— 则：

  - 如果调用方式为 `static`，则没有目标引用。

  - 否则，令 `r` 为该方法作为成员的直接外部类型声明，令 `n` 为 `r` 是包含该方法的类型声明中的整数。目标引用是第 `n` 个外部实例。如果不存在第 `n` 个外部实例，则发生编译错误。

- 如果形式为 `TypeName . [Arguments] Identifier`，则没有目标引用。

- 如果形式为 `ExpressionName . [Arguments] Identifier`，则：

  - 如果调用方式为 `static`，则没有目标引用。求值 `ExpressionName` 但结果被丢弃。

  - 否则，目标引用是 `ExpressionName` 所表示的值。

- 如果形式为 `Primary . [TypeArguments] Identifier`，则：

  - 如果调用方式为 `static`，则没有目标引用。求值 `Primary` 表达式但结果被丢弃。

  - 否则，求值 `Primary` 表达式并将其结果用作目标引用。

在任何情况下，如果 `Primary` 表达式求值异常中止，则任何参数表达式似乎都未求值，且方法调用因相同原因异常中止。

- 如果形式为 `super . [Arguments] Identifier`，则目标引用是 `this` 的值。



# 表达式

## 方法调用表达式 15.12

如果形式为 `TypeName . super . [Arguments] Identifier`，如果 `TypeName` 表示一个类，则目标引用是 `TypeName.this` 的值；否则，目标引用是 `this` 的值。

### 示例 15.12.4.1-1. 目标引用与静态方法

当由于调用方法是静态而计算并丢弃目标引用时，不会检查该引用是否为 `null`：

```java
class Test1 {
    static void mountain() {
        System.out.println("Monadock");
    }
    static Test1 favorite() {
        System.out.print("Mount ");
        return null;
    }
    public static void main(String[] args) {
        favorite().mountain();
    }
}
```

输出：

```
Mount Monadock
```

在这里 `favorite()` 返回 `null`，但抛出了 `NullPointerException`。

### 15.12.4.1-2. 方法调用期间的求值顺序

对于实例方法调用（§15.12），有一个表达式表示要调用的对象。在方法调用的任何参数表达式部分被求值之前，该表达式似乎已经完全求值。

因此，例如：

```java
class Test2 {
    public static void main(String[] args) {
        String s = "one";
        if (s.startsWith(s = "two")) {
            System.out.println("oops");
        }
    }
}
```

在 `.startsWith` 之前的 `s` 出现被首先求值，在参数表达式 `s = "two"` 之前。因此，字符串 `"one"` 的引用被记录为目标引用，在此之前局部变量 `s` 被更改为字符串 `"two"`。结果是为目标对象 `"one"` 调用了带有参数 `"two"` 的 `startsWith` 方法，因此调用的结果为 `false`，因为字符串 `"one"` 并不以 `"two"` 开头。因此测试程序没有打印 `"oops"`。

### 15.12.4.2 求值参数

求值参数列表的过程取决于被调用的方法是固定数组还是可变方法（§8.4.1）。

如果调用的方法是可变方法 $m$，它必然具有 $n > 0$ 个形式参数。$m$ 的最后一个形式参数类型必然是某个 $T$ 的 `T[]` 类型，且 $m$ 必然是用 $k \ge 0$ 个实际参数表达式调用的。

如果用 $k \neq n$ 个实际参数表达式调用 $m$，或者用 $k = n$ 个实际参数表达式调用 $m$ 且第 $k$ 个表达式的类型与 `T[]` 不赋值兼容，则如果参数列表 $(e₂, ..., eₙ₋₁, ..., eₖ)$ 被写为擦除形式 $(e₂, ..., eₙ₋₁, \text{new } T[](e₂, ..., eₖ))$，则对其进行求值，其中 `|T[]|` 表示 `T[]` 的擦除（§4.6）。

前段落是为了处理在具有擦除泛型的 Java 虚拟机中发生的泛型类型与数组之间的交互。具体来说，如果数组参数的元素类型 $\tau$ 是不可重构的（non-reifiable），例如 `List<String>`，则必须对数组创建表达式（§15.10）采取特别关注，因为数组元素必须是可重构的。通过擦除列表中最后一个表达式的类型，我们确保了获得一个可重构的元素类型。由于由于数组创建表达式出现在调用上下文中（§5.3），可能存在从具有可重构元素的数组类型到具有不可重构元素的数组类型的未检查转换。Java 编译器需要在在此转换时给出一个编译时的未检查警告（unchecked warning）。Oracle 的 Java 编译器参考实现将此未检查警告识别为更具信息量的未检查数组创建。

参数表达式（可能按上述方式重写）现在被求值以产生*参数值*。每个参数值恰恰对应方法的 $n$ 个形式参数中的之一。

参数表达式（如果有）按从左到右的顺序求值。如果右侧任何参数的求值似乎已经完成求值，且方法调用由于相同原因异常终止。求值第 $j$ 个参数表达式的原因是第 $j$ 个参数值，对于 $1 \le j \le n$。随后按照下文所述使用参数值继续求值。

### 15.12.4.3 检查类型和方法的可访问性

在本节中：

- 令 $D$ 为包含方法调用的类。
- 令 $\tau$ 为方法调用的限定类型（§13.1）。
- 令 $m$ 为在编译时确定的方法名（§15.12.3）。

Java 编程语言的实现必须作为链接（linkage）的一部分确保 $\tau$ 是可访问的：

- 如果 $\tau$ 与 $D$ 在同一个包中，则 $\tau$ 是可访问的。
- 如果 $\tau$ 与 $D$ 在不同的包中，且它们的包在同一个模块中，且 $\tau$ 是 `public` 或 `protected`，则 $\tau$ 是可访问的。
- 如果 $\tau$ 与 $D$ 在不同的包中，且它们的包在不同的模块中，且 $\tau$ 导出其包到 $D$ 的模块，且 $\tau$ 是 `public` 或 `protected`，则 $\tau$ 是可访问的。

如果 $\tau$ 是受保护的，它在编译时必然是一个嵌套类型，其可访问性受包含其声明的类型的可访问性的影响。然而，在链接期间，其可访问性不受包含其声明的类型的可访问性的影响。此外，在链接期间，一个 `protected T` 可以作为 `public T` 被访问。编译时访问控制（§6.6）与运行时访问控制之间的这些差异由于 Java 虚拟机的限制。

实现还必须确保在链接期间方法 $m$ 仍然可以在 $T$ 或 $T$ 的超类型中找到。如果找不到 $m$，则发生 `NoSuchMethodError`（它是 `IncompatibleClassChangeError` 的子类）。如果可以找到 $m$，令 $C$ 为声明 $m$ 的类型。实现必须确保在链接期间，$C$ 中 $m$ 的声明是可访问的：

- 如果 $m$ 是 `public`，则 $m$ 是可访问的
- 如果 $m$ 是 `protected`，则当 (i) $D$ 与 $C$ 在同一个包中，或 (ii) $D$ 是 $C$ 的子类型时，$m$ 是可访问的
- 如果 $m$ 是 `private`，则当 $D$ 与 $C$ 在同一个包中，或 $D$ 是 $C$ 的子类型，或 $D$ 被 $C$ 包含时，$m$ 是可访问的

如果 $\tau$ 不可用，则发生 `IllegalAccessError`。如果 $m$ 是接口，则实现必须检查引用类型实现了该接口。如果目标类型没有实现该接口，则发生 `IncompatibleClassChangeError`。

### 15.12.4.4 定位要调用的方法

定位方法的策略取决于调用模式：

- 如果调用方法是静态的，不需要目标引用且不允许重写。类或接口 $C$ 的 $m$ 是要调用的那个。
- 否则，要调用实例方法且存在目标引用。如果目标引用为 `null`，则在此处抛出 `NullPointerException`。

否则，目标引用被认为引用目标对象并将作为调用方法中 `this` 的值。然后考虑调用模式的其他三种可能性：

- 如果调用模式是 `super`，不允许重写。类或接口 $C$ 的 $m$ 是要调用的那个。如果 $m$ 是抽象的，则抛出 `AbstractMethodError`。
- 如果调用模式是 `virtual`，且 $r$ 和 $m$ 共同指示签名多态方法（§15.12.3），则目标对象是 `java.lang.MethodHandle` 或 `java.lang.VarHandle` 的实例。目标对象封装了与编译时方法调用匹配的状态。匹配的细节见《Java虚拟机规范，Java SE 14 和 Java SE Platform API》。如果匹配成功，则直接并立即调用由 `MethodHandle` 引用的方法，或者直接并立即访问 `VarHandle` 实例表示的变量，在任何情况下都不执行 §15.12.4 中的过程。如果匹配失败，抛出 `java.lang.invoke.WrongMethodTypeError`。
- 否则，调用模式是接口或虚。

如果 $C$ 中的方法 $m$ 是 `private` 的，则它是要调用的方法。否则，可能会发生重写。使用下文指定的动态方法查找来定位要调用的方法。查找过程从 $R$ 开始，$R$ 是目标对象的运行时类。注意，对于接口模式，$R$ 必然实现 $T$；对于虚模式，$R$ 必然是 $T$ 或 $T$ 的子类。如果目标对象是数组，则 $R$ 是表示数组类型的“类”。

动态方法查找过程如下。令 $s$ 为要搜索的类，从 $R$ 开始。然后：

1. 如果 $s$ 包含重写 $R$ 的类或接口中 $m$ 的声明（§8.4.8.1），则该重写方法是要调用的方法，程序终止。
2. 否则，如果 $s$ 有超类，则使用直接超类替换 $s$ 递归地执行此查找程序的第 1 步和第 2 步；要调用的方法（如果有）是递归调用此查找程序的结果。
3. 如果通过前两个步骤没有找到任何方法，则在 $s$ 的超接口中搜索适当的方法。

一个具有以下属性的方法集被视为候选方法：

- (i) 每个方法都声明在 $s$ 的某个（直接或间接）超接口中；
- (ii) 每个方法都具有方法调用阶段所需的名称和描述符；
- (iii) 每个方法都是非静态且非私有的；
- (iv) 对于每个该方法，如果该方法的接口是 $r$，则在 $I$ 的某个子接口中没有其他方法满足条件 (i) 至 (iii) 且声明在其中的方法。

如果该集合包含一个默认方法（default method），则其中一个一个方法即为要调用的方法。否则，从该集合中选择一个抽象方法（abstract method）作为要调用的方法。

动态方法查找可能会导致以下错误：

- 如果要调用的方法是抽象的，将抛出 `AbstractMethodError`。
- 如果要调用的方法是默认方法，且在上述步骤 3 的候选方法集中出现了多个默认方法，将抛出 `IncompatibleClassChangeError`。
- 如果调用模式是接口且要调用的方法既不是公共的也不是私有的，将抛出 `IllegalAccessError`。

上述过程（如果在无错误的情况下终止）将在程序中所有类和接口已经过一致编译的情况下，找到一个非抽象的、访问的方法进行调用。然而，如果并非如此，则可能会发生上述各种错误；关于 Java 虚拟机在这种情况下行为的更多细节，请参见《Java 虚拟机规范，Java SE 14 版》。

动态查找过程虽然在此处进行了描述，但将被隐式地实现，作为每类方法分发表构造和使用的副作用，或者为了高效分发而构造的其他每类结构的结果。

### 示例 15.12.4.4-1. 方法重写与方法调用

```java
class Point {
    final int EDGE = 20;
    int x, y;
    void move(int dx, int dy) {
        x = dx; y += dy;
        if (Math.abs(x) >= EDGE || Math.abs(y) >= EDGE)
            clear();
    }
    void clear() {
        System.out.println("Point clear");
    }
}
```

子类 `ColoredPoint` 扩展了其父类 `Point` 定义的 `clear` 抽象。它通过用自己的方法重写 `clear` 方法来实现，该方法使用 `super.clear()` 形式调用父类的 `clear` 方法。

每当 `clear` 用的目标对象是 `ColoredPoint` 时，就会调用此方法。正如此测试程序的输出所示，即使是 `Point` 类中的 `move` 方法，当 `this` 的类为 `ColoredPoint` 时也会调用 `ColoredPoint` 类的 `clear` 方法：

```java
class ColoredPoint extends Point {
    void clear() {
        System.out.println("ColoredPoint clear");
        super.clear();
    }
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        System.out.println("p.move(20,20):");
        p.move(20, 20);

        ColoredPoint cp = new ColoredPoint();
        System.out.println("cp.move(20,20):");
        cp.move(20, 20);

        Point p2 = new ColoredPoint();
        System.out.println("p.move(20,20), p colored:");
        p2.move(20, 20);
    }
}
```

输出如下：

```
p.move(20,20):
  Point clear
cp.move(20,20):
  ColoredPoint clear
  Point clear
p.move(20,20), p colored:
  ColoredPoint clear
  Point clear
```

重写看起来像是“晚期绑定引用”；在示例中，这意味着 `Point.move` 体中对 `clear` 的引用（这实际上是 `this.clear` 的语法缩写）调用的是一个“晚期”选择的方法（在运行时，根据 `this` 所引用的对象的运行时类进行选择），而不是一个“早期”选择的方法（在编译时，仅根据 `this` 的类型进行选择）。这为程序员提供了一种扩展抽象的强大方式，是面向对象编程的核心思想之一。

### 示例 15.12.4.4-2. 使用 super 进行方法调用

超类的被重写的实例方法可以通过关键字 `super` 来访问，从而访问直接超类的成员，并跳过包含该方法调用的类中的任何重写声明。

在访问实例变量时，`super` 的含义与 `this` (§15.11.2) 相同，但这种等效性对于方法调用并不成立。这一点通过示例得到了证明：

```java
class T1 {
    String s() { return "1"; }
}
class T2 extends T1 {
    String s() { return "2"; }
}
class T3 extends T2 {
    String s() { return "3"; }
    void test() {
        System.out.println("s()=\"" + s());
        System.out.println("super.s()=\"" + super.s());
        System.out.println("((T2)this).s()=\"" + ((T2)this).s());
        System.out.println("((T1)this).s()=\"" + ((T1)this).s());
    }
}
```

产生的输出：

```
s() = 3
super.s() = 2
((T2) this).s() = 3
((T1) this).s() = 3
```

向 `T1` 和 `T2` 的强制转换并没有改变被调用的方法，因为要调用的实例方法是根据 `this` 所引用对象的运行时类选择的。强制转换不会改变对象的类；它只检查该类与指定类型是否兼容。

### 15.12.4.5 创建帧、同步、传输控制

某个类中的方法 $m$ 已确定为要调用的方法。现在创建一个新的激活帧，包含目标引用（如果有）和参数值（如果有），以及该方法所需的其他信息（栈指针计数等）。如果没有足够的内存来创建此类激活帧，将抛出 `StackOverflowError`。

新创建的激活帧成为当前激活帧。在参数值赋值给相应的局部变量之前，它们将经过标识转换 (§5.1)。

如果方法的擦除与编译时声明不同，或者任何参数值不是其子类或子接口的实例，将抛出 `ClassCastException`。

如果 $m$ 是原生方法但必要的代码未加载或否则无法链接，将抛出 `UnsatisfiedLinkError`。

如果该方法是同步的，控制将转移到方法体。当方法体执行完毕（无论是正常还是异常）时，对象将自动解锁。

### 示例 15.12.4-5. 被调用的方法签名与编译时签名不同

考虑以下声明：

```java
abstract class C<T> {
    abstract T id(T x);
}

class D extends C<String> {
    String id(String x) { return x; }
}
```

现在，给定一个调用：

```java
C c = new D();
c.id(new Object()); // ClassCastException
```

被调用的方法 `D.id()` 的擦除与其编译时声明 `C.id()` 的签名不同。前者接受 `String` 参数，而后者接受 `Object` 参数。调用在执行方法之前就会发生 `ClassCastException`。

这种情况只有在程序产生编译时未检查警告（§4.8, §5.1.6, §5.1.9, §8.4.1, §8.4.3, §15.13.2, §15.12.4, §15.27.3）时才会出现。

实现可以通过构建桥接方法来强制这些语义。在上面的示例中，将在类 `D` 中创建如下桥接方法：

```java
Object id(Object x) { return id((String) x); }
```

这就是 Java 虚拟机在响应上面所示 `c.id(new Object())` 调用时实际调用的方法，它将执行强制转换并失败，正如要求。

## 15.13 方法引用表达式

方法引用表达式用于引用方法的调用而不实际执行该调用。某些形式的方法引用表达式允许将类实例化简体（§15.9）或数组创建简体（§15.10）视为像方法调用一样。



## 15.13 方法引用表达式

如果方法引用表达式的形式为 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，若 `ExpressionName` 或 `Primary` 的类型不是引用类型，则会导致编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier`，令 $\tau$ 为紧邻包含该方法引用表达式的类型声明。如果 $\tau$ 是 `Object` 类或 $\tau$ 是接口，则会导致编译时错误。

如果方法引用表达式的形式为 `TypeName . super :: [TypeArguments] Identifier`，则：

* 如果 `TypeName` 表示一个类 $c$，则若 $c$ 不一定是当前类的直接父类，或者 $c$ 是 `Object` 类，则会导致编译时错误。
* 如果 `TypeName` 表示一个接口 $I$，则令 $\tau$ 为紧邻包含该方法引用表达式的类型声明。如果 $I$ 不是 $\tau$ 的直接父接口，或者存在 $\tau$ 的其他超父类或直接父接口 $J$，使得 $J$ 是 $I$ 的子类型，则会导致编译时错误。
* 如果 `TypeName` 表示一个变量，则会导致编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName . super :: [TypeArguments] Identifier`，若该表达式出现在静态上下文中，则会导致编译时错误。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，则：

* 如果 `ClassType` 表示一个可访问的（§6.6）、非抽象的且不是枚举类型的类，否则会导致编译时错误。
* 如果 `ClassType` 表示一个泛型类型（§4.5），若其任何一个类型参数为通配符，则会导致编译时错误。
* 如果 `ClassType` 表示一个原始类型（§4.8），若在 `::` 之后存在 `TypeArguments`，则会导致编译时错误。

如果方法引用表达式的形式为 `ArrayType :: new`，则 `ArrayType` 必须表示一个可重化的（§4.7）类型，否则会导致编译时错误。

实例方法（§15.2.4.1）的目标引用可以通过使用 `ExpressionName`、`Primary` 或 `super` 的方法引用表达式提供，也可以在方法调用时后提供。新类实例（§15.9.2）的紧邻包含实例通过词法包含的实例 `this`（§8.1.3）提供。

当一个类型的多个成员方法具有相同名称，或一个类具有多个构造函数时，将根据方法引用表达式所的目标函数接口（见 §15.13.1）选择适当的方法或构造函数。

以下是一些方法引用表达式，首先没有目标引用，然后带有目标引用：

```
String::length // 实例方法
System::currentTimeMillis // 静态方法
List<String>::size // 泛型类型的显式类型参数
List:::size // 泛型类型的推断类型参数
int[]::clone
T::tvarMember

System.out.println(
"abc"::length
foo[x]::bar
(test ? list.replaceAll(String::trim) : list) : iterator
super::toString())
```

以下是一些方法引用表达式：

```
String::valueOf // 需要重载解析
Arrays::sort // 从上下文推断类型参数
Arrays::<String>sort // 显式类型参数
```

以下是表示对象或数组延迟创建的方法引用表达式：

```
ArrayList<String>:::new      // 泛型类型的构造函数
ArrayList:::new                          // 推断类型参数
Foo::<Integer>::new                     // 用于泛型类
          // 用于泛型构造函数
Bar<String>::<Integer>::new             // 泛型类，泛型构造函数
Outer::new                              // 内部类构造函数
int[]::new                              // 数组创建
```

无法指定特定的签名进行匹配，例如 `Arrays::sort(int)`。相反，函数接口提供了作为重载解析算法输入的参数（§15.12.2）。这应该适用于大多数场景；当出现需要精确控制的少数情况时，可以使用 lambda 表达式。

在分隔符之前的类名中使用类型参数语法（如 `List<String>:::size`）会引发区分 `<` 作为类型参数括号和 `<` 作为小于运算符的解析问题。从理论上讲，这比允许在强制转换表达式中使用类型参数并不差；但区别在于，这种情况只在遇到标记时出现；随着方法引用表达式的引入，每个表达式的开头可能都是泛型类型。

## 15.13.1 方法引用的编译时声明

方法引用表达式的编译时声明是该表达式所引的方法。在特殊情况下，编译时声明实际上并不存在，而是一个表示类实例创建或数组创建的虚拟方法。编译时声明的选择取决于表达式的目标函数类型，正如方法调用的编译时声明取决于调用参数（§15.12.3）。

搜索编译时声明的过程类似于 §15.12.1 和 §15.12.2 中的方法调用过程，如下：

首先，确定要搜索的类型：

* 如果方法引用表达式的形式为 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，则搜索类型为 `::` 标记之前的表达式类型。
* 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，则搜索类型为应用于 `ReferenceType` 的转换转换（§5.1.10）的结果。
* 如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier`，则搜索类型为包含该方法引用的类的父类类型。
* 如果方法引用表达式的形式为 `TypeName . super :: [TypeArguments] Identifier`，则如果 `TypeName` 表示一个类，则搜索类型为该类的父类；否则 `TypeName` 表示一个接口，则包含该方法引用的类或接口对应的父接口类型为搜索类型。
* 对于另外两种形式（涉及 `:: new`），所引方法是虚拟的，没有要搜索的类型。

其次，给定具有 $n$ 个参数的目标函数类型，识别一组潜在可能的方法：

* 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，则潜在可能的方法包括：
    > 搜索类型中，对于名为 `Identifier`、参数个数为 $n$、具有类型参数 `TypeArguments` 且与方法引用位于同一类的方法调用潜在可能的（§15.12.2.1）成员方法；加上
    > 搜索类型中，对于名为 `Identifier`、参数个数为 $n-1$ 的方法调用潜在可能的成员方法。

## 15.13 方法引用表达式 EXPRESSIONS

具有类型参数 `TypeArguments`，并且与方法引用表达式出现在同一个类中。

考虑了两种不同的元参数个数，$n$ 和 $n-1$，以考虑到这种形式可能指向静态方法或实例方法的可能性。

* 如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，则潜在适用的方法是一组与 `ClassType` 的构造函数对应的逻辑方法。
* 如果 `ClassType` 是一个原始类型，但它不是某个原始类型的非静态成员类型，则候选的逻辑成员方法是 §15.9.3 中指定的、使用 `<` 省略类类型参数的类实例创建方法。否则，候选的逻辑成员方法是 `ClassType` 的构造函数，它们被视为返回类型为 `ClassType` 的方法。
* 在这些方法中，潜在适用的方法是：对于元参数个数为 $n$、具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类的方法调用，潜在适用的逻辑方法。
* 如果方法引用表达式的形式为 `ArrayType :: new`，则考虑单个逻辑方法。该方法具有类型为 `int` 的单个参数，返回 `ArrayType`，且没有 `throws` 子句。如果 $n=1$，这是唯一潜在适用的方法；否则，没有潜在适用的方法。
* 对于所有其他形式，潜在适用的方法是待搜索类型的成员方法，这些方法对于命名为 `Identifier`、元参数为 $n$具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类的方法调用是潜在用的。

最后，如果没有潜在适用的方法，则没有编译时声明。

否则，给定一个具有参数类型 $P_1, ..., P_n$ 的目标函数类型和一组潜在适用的方法，编译时声明的选择方式如下：

* 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，则将执行两次针对最特定适用方法的搜索。每次搜索均如 §15.12.2.2 至 §15.12.2.5 所示，并带有以下下文说明。每次搜索产生一个适用方法集合，并可能指定该集合中的一个最特定方法。

### 方法引用表达式

在 §15.12.2.4 指定错误的情况下，适用方法集合为空。在 §15.12.2.5 指定错误的情况下，没有最特定方法。

在第一次搜索中，方法引用被处理为具有类型为 $P_1$, ..., $P_n$ 的参数表达式的调用。类型参数（如果有）由方法引用表达式给出。

在第二次搜索中，如果 $P_1, ..., P_n$ 不空且 $P_1$ 是 `ReferenceType` 的子类型，则该方法引用表达式被处理为具有类型为 $P_2$, ..., P_n$ 的参数表达式的方法调用表达式。如果 `ReferenceType` 是一个原始类型，并且存在该 $G<...>$ 的泛化是 $P_1$ 的超类型，则待搜索类型是应用捕获转换（§5.1.10）于 $G<...>$ 的结果；否则，待搜索类型与第一次搜索的类型相同。类型参数（如果有）由方法引用表达式给出。

如果第一次搜索产生了一个特定的 `static` 方法，且第二次搜索产生的适用方法集合不包含非静态方法，则编译时声明为第一次搜索的最特定方法。

否则，如果第一次搜索产生的适用方法集合不包含 `static` 方法，且第二次搜索产生了一个 `non-static` 最特定方法，则编译时声明为第二次搜索的最特定方法。

否则，没有编译时声明。

* 对于所有其他形式的方法引用表达式，将执行一次针对最特定适用方法的搜索。搜索如 §15.12.2.2 至 §15.12.2.5 所示，并带有以下下文说明。

方法引用被处理为具有类型为 $P_1$, ..., $P_n$ 的参数表达式的调用；类型参数（如果有）由方法引用表达式给出。

如果搜索导致 §15.12.2.2 至 §15.12.2.5 指定的错误，或者最特定适用方法是 `static`，则没有编译时声明。

否则，编译时声明为最特定适用方法。

如果方法表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，且编译时声明为静态（`static`），且 `ReferenceType` 不是简单名或限定名（§6.2），则为编译级错误。

如果方法表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName.super :: [TypeArguments] Identifier`，且编译时声明为抽象（`abstract`），则为编译级错误。

如果方法表达式的形式为 `TypeName.super :: [TypeArguments] Identifier`，且 `TypeName` 表示一个接口，并且存在一个不同于编译时声明的方法，该方法覆盖（§8.4.8, §9.4.1）了来自其声明的直接父类或直接接口的编译时声明，则为编译级错误。

如果方法表达式的形式为 `ClassType :: new`且在确定实例时会发生编译错误，则为编译级错误。

形式为 `ReferenceType :: Identifier` 的方法引用有不同的解释方式。如果 `Identifier` 指向一个实例，那么隐式方法与 `Identifier` 指向静态方法相比多出一个参数。

歧义的一个示例是：

```
interface Fun<T,R> { apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    int size(C arg) { return 0; }
}
```

```
void test() {
    Fun<C, Integer> f1 = C::size;
    // 错误：实例方法 size()
    // 还是静态方法 size(Object)?
}
```

这种歧义无法通过提供一个比静态方法更具体的实例方法来解决：

```
interface Fun<T,R> { apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    int size(C arg) { return 0; }
}
```

```
void test() {
    Fun<C,Integer> f = C::size;
    // 正确：引用的是实例方法 size()
}
```

为了方便起见，当使用泛型名称来引用实例方法（其中接收者成为第一个参数）时，将使用目标类型来确定参数。这便于使用 `Pair::first` 代替 `Pair<String,Integer>::first`。类似，像 `Pair::new` 这样的方法引用被处理为“菱”实例创建（`new Pair<>()`）。由于菱是隐式的，这种形式不会实例化原始类型；事实上，没有办法表示对原始类型构造函数的引用。

对于某些方法引用表达式，无论目标函数类型如何，只有一种可能的编译时声明和一种可能的调用类型（§15.12.2.6）。此类方法引用表达式被称为精确的（exact）。不是精确的方法引用表达式被称为活跃的（act）。

以 `Identifier` 结尾的方法引用如果满足以下条件，则是精确的：

* 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，则 `ReferenceType` 不表示原始类型。
* 待搜索类型只有一个名称为 `Identifier` 的方法，且该方法对于方法引用表达式所在的类或接口是可访问的。

### 方法引用表达式

* 该方法不是可变参数的（§8.4.1）。
* 如果该方法是泛型的（§8.4.4），则该方法引用表达式提供类型参数（`TypeArguments`）。

形式为 `ClassType :: [TypeArguments] new` 的方法引用表达式如果满足以下所有条件，则它是精确的（exact）：

* `ClassType` 所表示的类型不是原始类型，也不是原始类型的非静态成员类型。
* `ClassType` 所表示的类型恰好有一个构造函数，该构造函数对于方法引用表达式出现的类或接口是可访问的。
* 该构造函数不是可变参数的。
* 如果该构造函数是泛型的，则该方法引用表达式提供类型参数（`TypeArguments`）。

形式为 `ArrayType :: new` 的方法引用表达式始终是精确的。

## 15.13.2 方法引用的类型

方法引用表达式在赋值上下文、调用上下文或转换上下文中与目标 T 兼容，当且仅当 T 是一个函数接口类型（§9.8）且该表达式与从 T 导出的基础类型的函数类型同合（congruent）。

基础目标类型从 T 如下导出：

* 如果 T 是一个通配符参数化的函数接口类型，则基础目标类型是 T 的非通配符参数化（§9.9）。
* 否则，基础目标类型为 T。

方法引用表达式与函数类型同合，当且仅当以下两个条件均为真时：

* 函数类型标识了与该引用对应的单个编译时声明。
* 以下任一条件为真：
  * 函数类型的结果为 `void`。
  * 函数类型的结果为 R，且将捕获转换（§5.1.10）应用于所选编译时声明的调用类型（§15.12.2.6）的返回类型的结果为 R'（其中 R 是用于推断 R' 的目标类型，且 R 和 R' 均不是 `void`，且 R' 在赋值上下文中与 R 兼容）。

如果编译时声明的适用需要未检查转换（unchecked conversion），且该转换在调用上下文中会导致未检查警告，则会发生编译时未检查警告，除非被 `@SuppressWarnings`（§9.6.4.5）抑制。

如果上述描述的返回类型 R' 与函数类型的返回类型 R 兼容需要未检查转换，且该转换在赋值上下文中会导致未检查警告，则会发生编译时未检查警告，除非被 `@SuppressWarnings`（§9.6.4.5）抑制。

如果方法引用与目标类型 T 兼容，则该表达式的类型 U 是从 T 导出的目标类型。

如果 U 或 U 的函数类型所涉及的任何类或接口从方法引用出现的类或接口而言都是不可访问的（§6.6），则为编译时错误。



## 方法引用兼容性

对于 `U` 的每个非静态成员方法 `m`，如果 `U` 的函数类型的签名与 `m` 的签名相同，则认为 `U` 的函数类型重写了（override）方法 `m`，并且可能会发生 `$8.4.8.3` 中指定的任何编译时错误或未检查警告。

对于编译时声明调用中 `throws` 子句中列出的每个异常类型 `X`，`X` 或 `X` 的父类必须在 `U` 的函数类型的 `throws` 子句中被，否则将发生编译时错误。

兼容性定义的关键在于：方法引用兼容当且仅当等效的 lambda 表达式 `(x, y, z) -> exp.<T1,T2>method(x, y, z)` 是兼容的。（这是非正式的，并且某些问题使得难以或无法通过这种重写来正式地定义语义）。

这些兼容性为将一个接口转换为另一个提供了方便：

```
Task t = () -> System.out.println("hi");
Runnable r = t::invoke();
```

实现可以被优化，使得当传递 lambda 派生的对象时，在将其转换为各种类型时，可以进行优化。与 lambda 表达式不同，方法引用可以与泛型同合，因为 lambda 表达式不需要这种语法来声明类型参数。例如，以下程序是合法的：

```
interface ListFactory {
  <T> List<T> make();
}

ListFactory lf = ArrayList::new;
List<String> ls = lf.make();
```

## 13.3 方法引用的运行时评估

在运行时，方法引用的评估与类实例化相似，只要其产生一个对象。

首先，如果方法引用以 `ExpressionName` 或 `Primary` 开头，则评估子表达式。如果子表达式结果为 `null`，则抛出 `NullPointerException`，方法引用异常中止。如果子表达式异常中止，方法引用也由于相同原因异常中止。

接下来，分配一个具有以下属性的新类实例，或者引用现有的类实例。如果要创建新实例但空间不足，方法引用通过抛出 `OutOfMemoryError` 异常。

方法引用的值具有以下属性：

- 类实现了目标接口类型，如果目标类型是交集类型，则实现文中提到的每个其他类型。

- 对于 `U` 的每个成员方法 `m`，如果 `U` 的函数类型的签名与 `m` 的签名相同，则该方法的体会调用该方法、创建一个类实例或创建一个数组。如果调用方法的结果不是 `void`，则在任何必要的转换 (§5.2) 后返回调用的结果。

如果被重写的类型擦除与其函数类型的签名不同，则在方法调用或对象创建之前，调用方法的体会检查每个参数值是否为对应参数类型的实例；如果不是，则抛出 `ClassCastException`。

- 类没有重写函数接口的其他方法，尽管它可以重写 `Object` 类的方法。

调用方法的体取决于方法引用的形式，如下：

- 如果形式为 `expressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，则调用方法的体具有编译时声明的调用表达式的效果。调用表达式的运行时评估由 §15.12.4.3 和 §15.12.4.5 规定，其中：
  - 调用模式按照 §15.12.3 导出。
  - 目标引用是评估方法引用时确定的 `ExpressionName` 或 `Primary` 的值。
  - 调用方法的参数是调用方法的形式参数。

- 如果形式为 `ReferenceType :: [TypeArguments] Identifier`，则调用方法的体同样具有调用表达式的效果。调用表达式的运行时评估由 §15.12.4.3、§15.12.4.4 和 §15.12.4.5 规定，其中：
  - 如果编译时声明是实例方法，则目标引用是调用方法的第一个形式参数。否则，没有目标引用。

- 如果形式为 `super :: [TypeArguments] Identifier` 或 `TypeName.super :: [TypeArguments] Identifier`，则调用方法的体具有该方法引用表达式的编译时声明的方法调用表达式的效果。方法调用表达式的运行时求值在 §15.12.4.3、§15.12.4.4 和 §15.12.4.5 中规定，其中：
  - 调用方法是 `super`。
  - 如果方法引用表达式以命名一个类的 `TypeName` 开头，则目标引用是方法引用表达式求值点 `TypeName` 的值。否则，目标引用是方法引用表达式求值点 `this` 的值。
  - 方法调用表达式的参数即为该调用方法的形式参数。

- 如果形式为 `ClassType :: [TypeArguments] new`，则调用方法的体具有形式为 `new [TypeArguments] ClassType(Aj, ..., An)` 的类实例创建的效果，其中参数 `Aj, ..., An` 是该调用方法的形式参数，且：
  - 新对象的包围实例（如果有）源自方法引用表达式的位置，如 §15.9.2 指定。
  - 要调用的构造函数是与方法引用的编译时声明对应的构造函数 (§15.13.1)。

- 如果形式为 `Type[] :: new (k ≥ 1)`，则调用方法的体具有与 `new Type[size]^k` 数组创建表达式相同的效果，其中 `size` 是调用方法的大小参数。（符号 `[]^k` 表示 k 个括号对序列。）

如果调用方法的体具有方法调用表达式的效果，则方法调用的编译时参数类型和编译时结果在 §15.12.3 中规定。为了确定编译时结果，如果方法调用的结果为 `void`，则方法调用表达式是一个表达式；如果方法调用的结果非 `void`，则是 `return` 语句的表达式。

方法引用表达式求值的时机比 lambda 表达式 (§15.27.4) 更复杂。当方法引用表达式在 `::` 分隔符之前有一个表达式（而不是类型）时，该子表达式会被求值。求值结果被存储，直到对应函数式类型的方法被调用；届时，该结果即为调用的目标引用。这意味着 `::` 分隔符之前的表达式仅在程序遇到方法引用表达式时求值，且在函数式类型的后续调用中不会重新求值。

将 `null` 的处理与其在方法调用期间的处理进行对比是非常有趣的。当求值方法调用时，修饰调用的 `Primary` 可能求值为 `null` 但不会抛出 `NullPointerException`。这发生在被调用方法是静态方法时（尽管调用的语法暗示实例方法）。由于由 `Primary` 修饰的方法引用表达式的适用方法禁止是静态的 (§15.13.1)，方法引用表达式的求值更为简单——`Primary` 总是会抛出 `NullPointerException`。

## 15.14 后缀表达式

后缀表达式包括后缀运算符 `++` 和 `--` 的使用。名称不被视为主表达式 (§15.8)，但在语法中被单独处理以避免某些歧义。它们仅在后缀表达式的优先级层面上才是互换的。

```
PostfixExpression:
    Primary
    ExpressionName
    PostIncrementExpression
    PostDecrementExpression
```

### 15.14.1 表达式名称求值

名称求值的规则在 §15.6 中给出。

### 15.14.2 后缀递增运算符 `++`

跟随 `++` 的后缀表达式是一个后缀表达式。

```
PostIncrementExpression:
    PostfixExpression ++
```

后缀表达式的结果必须是一个可转换为 (§15.8) 数字类型的变量，否则将发生编译时错误。后缀表达式的类型是该变量的类型。后缀表达式的结果不是变量，而是一个值。

在运行时，如果操作数的求值异常完成，则后缀表达式也因相同原因异常完成且不进行递增。否则，将值 `1` 加到变量的值上并将和存回变量中。在加法之前，会对值 `1` 执行二值数值提升 (§15.6)。如有必要，在存储之前通过收窄原始类型转换 (§15.3) 对和进行收窄，并/或通过装箱转换 (§15.7) 转换为变量的类型。后缀表达式的值是存储新值之前的值。注意，上述的二值数值提升可能包括拆箱转换 (§15.8) 和值集转换 (§15.13)。如有必要，在存储到变量之前对和应用值集转换。

声明为 `final` 的变量在访问此类 `final` 变量并作为表达式时不能被递增，其结果是一个值而不是变量。因此，它不能作为后缀运算符的操作数。

### 15.14.3 后缀递减运算符 `--`

跟随 `--` 的后缀表达式是一个后缀表达式。

```
PostDecrementExpression:
    PostfixExpression --
```

后缀表达式的结果必须是一个可转换为 (§15.8) 数字类型的变量，否则将发生编译时错误。后缀表达式的类型是该变量的类型。后缀表达式的结果不是变量，而是一个值。

在运行时，如果操作数的求值异常完成，则后缀表达式也因相同原因异常完成且不进行递减。否则，从变量的值中减去值 `1` 并将差存回变量中。在减法之前，会对值 `1` 执行二值数值提升 (§15.6)。如有必要，在存储之前通过收窄原始类型转换 (§15.3) 对差进行收窄，并/或通过装箱转换 (§15.7) 转换为变量的类型。后缀表达式的值是存储新值之前的值。注意，上述的二值数值提升可能包括拆箱转换 (§15.8) 和值集转换 (§15.13)。如有必要，在存储到变量之前对差应用值集转换。

声明为 `final` 的变量在访问此类 `final` 变量并作为表达式时不能被递减，其结果是一个值而不是变量。因此，它不能作为后缀运算符的操作数。

## 15.15 一元运算符

运算符 `+`、`-`、`++`、`--`、`~`、`!` 以及转换运算符 (§15.16) 称为一元运算符。一元表达式是应用于操作数的一元运算符，或者是一个 switch 表达式 (§15.28)。

```
UnaryExpression:
    PreIncrementExpression
    PreDecrementExpression
    + UnaryExpression
    - UnaryExpression
    UnaryExpressionNotPlusMinus

PreIncrementExpression:
    ++ UnaryExpression

PreDecrementExpression:
    -- UnaryExpression

UnaryExpressionNotPlusMinus:
    PostfixExpression
    ~ UnaryExpression
    ! UnaryExpression
    CastExpression
    SwitchExpression
```

带有一元运算符的表达式从右到左分组，因此 `~--x` 等同于 `~(--x)`。

这部分语法包含了一些技巧以避免两种潜在的语法歧义。第一个潜在的歧义会出现在诸如 `(p)+q` 的表达式中，这对于 C 或 C++ 程序员来说，看起来像是对单元 `+` 操作 `(p)` 的类型转换，或两个数量 `p` 和 `q` 的二元加法。在 C 和 C++ 中，解析器在解析时通过执行有限的语义分析来解决这个问题，以便它知道 `p` 是一个类型名或变量名。

Java 采取了不同的方法。`+` 运算符必须是数值型的，且所有涉及强制转换值的类型都是已知关键字。因此，如果 `p` 是命名基本类型的关键字，那么 `(p)+q` 只能被解释为一元表达式的强制转换。然而，如果 `p` 不是命名基本类型的关键字，那么 `(p)+q` 只能解释为二元算术操作。`-` 运算符也适用类似的说明。语法将 `CastExpression` 拆分为多种情况，以做出这种区分：

```
CastExpression:
    (PrimitiveType) UnaryExpression
    (ReferenceType[AdditionalBound]) UnaryExpressionNotPlusMinus
    (ReferenceType[AdditionalBound]) LambdaExpression
```

非终端符 `UnaryExpression` 排除所有一元运算符，`UnaryExpressionNotPlusMinus` 排除所有可能作为二元运算符的一元运算符，在 Java 中即 `+` 和 `-`。

第二个潜在的歧义是表达式 `(p++)` 对于 C 或 C++ 程序员来说，可能可能是括号化表达式的前缀递增，也可能是强制转换的开始，例如在 `(p++)q` 中。与之前一样，C 和 C++ 的解析器知道 `p` 是类型名或变量名。仅使用单标记向前查找且在解析期间不进行语义分析的解析器无法判断当 `++` 是向前查找的内容时，`p` 应该被视为原始表达式还是留待稍后作为 `CastExpression`。

在 Java 中，`++` 运算符的结果必须是数值型的，且所有涉及强制转换值的类型都是已知关键字。因此，如果 `p` 是命名基本类型的关键字，那么 `(p)++` 只能解释为前缀递增表达式的强制转换，并且 `++` 后面最好有一个如 `q` 的操作数。然而，如果 `p` 不是命名基本类型的关键字，那么 `(p)++` 只能解释为 `p` 的前缀递增。`-` 运算符也适用类似的说明。因此，非终端符 `UnaryExpressionNotPlusMinus` 也排除了前缀运算符 `++` 和 `--`。

### 15.15.1 前缀递增运算符 `++`

位于 `++` 运算符之前的一元表达式是前缀递增表达式。

该一元表达式的结果必须是可以转换为数值类型（§5.1.8）的类型的变量，否则将发生编译错误。

前缀递增表达式的类型是变量的类型。前缀递增表达式的结果不是变量，而是一个值。

在运行时，如果操作数的求值异常完成，则前缀递增表达式因相同的原因异常完成，且不发生递增。否则，将值 `1` 加到变量的值上，并将和存回变量中。在加法之前，会对值 `1` 和变量的值执行二元数值提升（§5.6）。如果必要，在存储之前，通过收窄基本类型转换（§5.1.3）将和进行缩小，并/或通过装箱转换（§5.1.7）转换为变量的类型。前缀递增表达式的值是存储新值后变量的值。

注意，上述二元数值提升可能包括拆箱转换（§5.1.8）和值集转换（§5.1.13）。如有必要，在存入变量之前，会对和应用值集转换。

声明为 `final` 的变量在此类 `final` 变量被用作表达式时不能增加，其结果是一个值而不是变量。因此，它不能作为前缀递增运算符的操作数。

### 15.15.2 前缀递减运算符 `--`

位于 `--` 运算符之前的一元表达式是递减表达式。

该一元表达式的结果必须是可以转换为数值类型（§5.1.8）的变量，否则将发生编译错误。

前缀递减表达式的类型是变量的类型。前缀递减表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的求值异常完成，则前缀递减表达式因相同的原因异常完成，且不发生递减。否则，从变量的值中减去值 `1`，并将差存回变量中。在减法之前，会对值 `1` 和变量的值执行二元数值提升（§5.6）。如有必要，在存储之前，通过收窄基本类型转换（§5.1.3）将差进行缩小，并/或通过装箱转换（§5.1.7）转换为变量的类型。前缀递减表达式的值是存储新值后变量的值。

注意，上述二元数值提升可能包括拆箱转换（§5.1.8）和值集转换（§5.1.13）。如有必要，在存入变量之前，会对差应用值集转换。

声明为 `final` 的变量在此类 `final` 变量被用作表达式时不能递减，其结果是一个值而不是变量。因此，它不能作为前缀递减运算符的操作数。

### 15.15.3 一元加运算符 `+`

一元 `+` 运算符的操作数表达式的类型必须是可以转换为基本类型（§5.1.8）的类型，否则将发生编译错误。

对操作数执行一元数值提升（§5.6）。一元加表达式的类型是操作数的提升类型。一元加表达式的结果不是变量，而是一个值。

在运行时，如果操作数的求值异常完成，则一元加表达式因相同的原因异常完成。否则，一元加表达式的值就是提升后的操作数值。

### 15.15.4 一元减运算符 `-`

一元 `-` 运算符的操作数表达式的类型必须是可以转换为数值类型（§5.1.8）的类型，否则将发生编译错误。

对操作数执行一元数值提升（§5.6）。一元减表达式的类型是操作数的类型。

在运行时，一元减表达式的值是提升值的算术取反。对于整数值，取反等同于减零。Java 语言使用补码表示整数，此处会发生溢出但不会抛出异常。对于所有整数 `x`，`-x` 等于 `(~x)+1`。

对于浮点值，取反并非减零，因为如果 `x` 是 `+0.0`，`-x` 就是 `-0.0`。一元减反转浮点数的符号。感兴趣的特殊情况：

- 如果操作数为 `NaN`，结果为 `NaN`。（参见 §4.2.3）。
- 如果操作数为无穷大，结果为相反符号的无穷。
- 如果操作数为零，结果为相反符号的零。

### 15.15.5 位取反运算符 `~`

一元 `~` 运算符的操作数表达式的类型必须是可以转换为基本整型（§5.1.8）的类型，否则将发生编译错误。



对操作数执行一元提升（§5.6）。一元位取反表达式的类型是操作数的类型。

在运行时，一元位取反表达式的值是提升值的取反。在所有情况下，`~x` 等于 `(-x)-1`。

## 15.15.6 逻辑取反运算符 !

一元 `!` 运算符的操作数表达式的类型必须是 `boolean`，否则将发生编译错误。

一元逻辑取反表达式的类型为 `boolean`。

在运行时，必要时操作数进行拆箱转换（§5.1.8）。如果（可能转换后的）操作值为 `false`，则一元逻辑取反表达式的值为 `true`；反之为 `false`。

## 15.16 转换表达式

转换表达式在运行时将一个数值类型的值转换为另一种类型的相似值；或在编译时确认表达式的类型为 `boolean`；或在运行时检查引用值所引的对象类是否与指定的引用类型或类型列表兼容，或体现了基本类型的值。

```
CastExpression:
(PrimitiveType) UnaryExpression
(ReferenceType[AdditionalBound]) UnaryExpressionNotPlusMinus
(ReferenceType[AdditionalBound]) LambdaExpression
```

为了方便，这里显示了 §4.4 中的以下产生式：

```
AdditionalBound:
& InterfaceType
```

括号及其包含的类型或类型列表有时被称为转换运算符。

# 转换表达式 (Cast Expressions)

如果转换操作符包含类型列表，即一个 `ReferenceType` 后面跟着一个或多个 `AdditionalBound` 项，则必须满足所有条件，否则将发生编译时错误：

- `ReferenceType` 必须表示类类型或接口类型。
- 所有列出的类型的擦除（§4.6）必须两两不相同。
- 任意两个列出的类型不能是同一个泛型接口不同参数化的子类型。

由转换表达式引入的转换（§5.5）的目标类型，是转换操作符中出现的 `PrimitiveType` 或 `ReferenceType`（如果后面没有紧跟 `AdditionalBound` 项），或者是由转换操作符中出现的 `ReferenceType` 和 `AdditionalBound` 项所表示的交集类型。

转换表达式的类型是对该目标类型应用捕获转换（§5.1.10）的结果。

> 转换可用于显式地“标记” lambda 表达式或方法引用表达式，以提供适当程度的灵活性；目标类型可以是表示交集类型的类型列表，前提是该交集产生了一个函数接口（§9.8）。

转换表达式的结果不是变量，而是一个值，即使操作数表达式求值的结果是一个变量。

转换操作符对 `float` 或 `double` 类型值集（§4.2.3）的选择没有影响。因此，在非 FP 严格（§15.4）的表达式中向 `float` 类型转换并不一定会导致该值被转换为值集中的一个元素，且在非 FP 严格的表达式中向 `double` 类型转换也不一定会导致其值被转换为 `double` 值集中的一个元素。

如果操作数的编译时类型无法通过转换转换（§5.5）转为目标类型，则会发生编译时错误。否则，转换表达式的结果是转换为目标类型的值。

# 乘法运算符 (Multiplicative Operators)

运算符 `*`、`/` 和 `%` 被称为乘法运算符。

```
* (乘法)
/ (除法)
% (取余数)
```

乘法运算符具有相同的优先级，并且是左结合的。

## 乘法运算符 (Multiplication Operator)

二元运算符 `*` 执行乘法，产生其操作数的乘积。左侧操作数是乘数，右侧操作数是因数。

浮点数乘法的结果由 IEEE 754 规则决定：

- 如果任一操作数为 `NaN`，则结果为 `NaN`。
- 如果结果不是 `NaN`，如果两个操作数的符号相同，则结果为正；如果操作数符号不同，则结果为负。
- 如果乘积大无法表示，则结果为相应符号的无穷。
- 如果乘积小无法表示，根据渐进下溢（§4.2.2），结果为规格数或零。

对于整数乘法，结果是操作数的乘积。如果乘积大无法表示该类型，则发生整数溢出。

## 除法运算符 (Division Operator)

二元运算符 `/` 执行除法，产生其操作数的商。左侧操作数是被除数，右侧操作数是除数。

浮点数除法的结果由 IEEE 754 规则决定：

- 如果任一操作数为 `NaN`，则结果为 `NaN`。
- 如果结果不是 `NaN`，如果两个操作数的符号相同，则结果为正；如果操作数符号不同，则结果为负。
- 无穷除以无穷的结果为 `NaN`。
- 无穷除以有限值的结果为带符号的无穷。
- 有限值除以无穷的结果为带符号的零。
- 零除以零的结果为 `NaN`；零除以任何其他有限值的结果为带符号的零。
- 非零值除以零的结果为带符号的无穷。

对于整数除法，商向 0 舍入。如果除法结果的值为 0，则会抛出 `ArithmeticException`。

## 取余运算符 (Remainder Operator)

二元运算符 `%` 计算除法的余数。左侧操作数是被除数，右侧操作数是除数。结果的符号始终与被除数的符号相同。

# 15.17 乘法运算符表达式

- 如果除法表达式不是 FP 严格的（FP-strict）：
  - 如果除法表达式的类型为 `float`，则根据实现的任意选择 `float` 值或浮点扩展指数（float-extended-exponent）值。
  - 如果除法表达式的类型为 `double`，则根据实现的任意选择 `double` 值或双精度扩展指数（double-extended-exponent）值。

接下来，必须从所选的值集中选择一个值来表示商。

如果商的绝对值大到无法表示，我们称该操作为溢出；结果将是具有适当符号的无穷大。

否则，商将使用 IEEE 754 “舍入最近值”模式舍入到所选值集中最近的值。Java 编程语言要求支持 IEEE 754 (§4.2.4) 定义渐进下溢。

尽管可能会发生溢出、下溢、除以零或信息丢失，但评估浮点除法运算符 `/` 永远不会抛出运行时异常。

# 15.17.3 余数运算符 %

二元运算符 `%` 被认为产生其操作数在隐式除法后的余数；左侧操作是被除数，右侧操作数是除数。

在 C 和 C++ 中，余数运算符只接受整数操作数，但在 Java 语言中，它也接受浮点操作数。

对于经过二元数值提升（§5.6）后为整数的操作数，余数运算产生的结果值满足 `(a/b)*b + (a%b)` 等于 `a`。

即使在被除数为该类型中绝对值最大的负整数，且除数为 `-1` 的特殊情况下（余数为 0），该等式依然成立。

根据此规则可以得出，余数运算只有在被除数为负时才为负，只有在被除数为正时才为正。此外，结果的绝对值始终小于除数的绝对值。

如果整数余数运算符的除数为 0，则抛出 `ArithmeticException`。

# 示例 15.17-3-1. 整数余数运算符

```
class Test1 {
    public static void main(String[] args) {
        int a = 5%3; // 2
        int b = 5/3; // 1
        System.out.println("5%3 produces " + a + "\n (note that 5/3 produces " + b + ")");
    }
}
```

该程序产生输出：

```
5%3 produces 2 (note that 5/3 produces 1)
5%-(-3) produces 2 (note that 5/-(-3) produces -1)
(-5)%3 produces -2 (note that (-5)/3 produces -1)
(-5)/(-3) produces -2 (note that (-5)/(-3) produces 1)
```

由 `%` 运算符计算的浮点余数运算结果与 IEEE 754 定义的余数运算产生的结果不同。IEEE 754 余数运算计算的是非截断除法后余数的余数，因此其行为是……相反地，Java 语言定义的浮点操作上的 `%` 行为在方式上类似于整数余数运算符；这可以与 C 语言库函数 `fmod` 进行比较。IEEE 754 余数运算可以通过库程序 `Math.remainder` 来计算。

浮点余数运算的结果由 IEEE 754 算术规则决定：

- 如果任一操作数为 `NaN`，则结果为 `NaN`。
- 如果结果不是 `NaN`，则结果的符号等于被除数的符号。
- 如果被除数为无穷大、除数为 0，或两者兼有，则结果为 `NaN`。
- 如果被除数为有限值且除数为无穷大，则结果等于被除数。
- 如果被除数为零且除数为有限值，则结果等于被除数。
- 在其余情况下（即既不涉及无穷大、零或 `NaN`），被除数 `n` 除以除数 `d` 得到的浮点余数 `r` 由数学关系 `r = n - (d · q)` 定义，其中 `q` 是一个整数，当 `n` 为负时 `q` 为负，仅当 `n` 为正时 `q` 为正，且其绝对值在不超过 `n` 和 `d` 的真实数学商的绝对值的情况下尽可能大。

评估浮点余数运算符 `%` 永远不会抛出运行时异常，即使右侧操作数为 0。也不会发生溢出、下溢或精度丢失。

# 示例 15.17.3-2. 浮点余数运算符

```
class Test2 {
    public static void main(String[] args) {
        double a = 5.0%3.0; // 2.0
        System.out.println("5.0%3.0 produces " + a);

        double b = 5.0%(-3.0); // 2.0
        System.out.println("5.0%(-3.0) produces " + b);

        double c = -5.0%3.0; // -2.0
        System.out.println("(-5.0)%3.0 produces " + c);

        double d = (-5.0)%(-3.0); // -2.0
        System.out.println("(-5.0)%(-3.0) produces " + d);
    }
}
```

该程序产生输出：

```
5.0%3.0 produces 2.0
5.0%(-3.0) produces 2.0
(-5.0)%3.0 produces -2.0
(-5.0)%(-3.0) produces -2.0
```

# 15.18 加法运算符

`+` 和 `-` 运算符被称为加法运算符。它们具有相同的优先级且在语法上是左结合的（从左到右分组）。

如果 `+` 的一个操作数为 `String`，则该操作是字符串拼接。否则，`+` 的每个操作数类型必须转换为数值类型，否则会导致编译错误。字符串拼接的结果是一个 `String` 对象引用，左操作数的字符位于右操作数的字符之前。

对于基本类型，实现可以直接从基本类型转换为字符串以消除包装对象的创建。为了提高重复字符串拼接的性能，Java 编译器可以使用 `StringBuilder` 或类似技术来减少中间 `String` 对象的数量。

示例表达式：

```
"The square root of 2 is " + Math.sqrt(2)
```

产生结果：

```
"The square root of 2 is 1.4142135623730951"
```

无论通过类型分析确定如何确定，该运算符都是左结合的。在某些情况下需要注意以得到所需的结果。例如，表达式：

```
a + b + c
```

始终被视为：

```
(a + b) + c
```

因此，表达式：

```
1 + 2 + "fiddlers"
```

结果是：

```
"3 fiddlers"
```

但表达式：

```
"fiddlers" + 1 + 2
```

结果是：

```
"fiddlers 12"
```

# 示例 15.18.1-2. 字符串拼接与条件判断

在这个幽默的示例中：

```
class Bottles {
    static void printSong(Object stuff, int n) {
        String plural = (n == 1) ? "" : "s";
        loop: while (true) {
            System.out.println(n + " bottle" + plural
                + " of " + stuff + " on the wall,");
            System.out.println(n + " bottle" + plural
                + " of " + stuff + " on the wall;");
            System.out.println("You take one down "
                + "and pass it around;");
            n--;
            plural = (n == 1) ? "" : "s";
            if (n == 0)
                break loop;
            System.out.println(n + " bottle" + plural
                + " of " + stuff + " on the wall!");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        printSong("slime", 3);
    }
}
```

`printSong` 方法将打印一首童歌的版本。`stuff` 的常用值包括 "pop" 和 "beer"；`n` 的常用值是 100。以下是运行该程序后产生的输出：

3 bottles of slime on the wall,
3 bottles of slime;
You take one down and pass it around;
2 bottles of slime on the wall!

2 bottles of slime on the wall,
2 bottles of slime;
You take one down and pass it around;
1 bottle of slime on the wall!

1 bottle of slime on the wall,
1 bottle of slime;
You take one down and pass it around;
No bottles of slime on the wall!

在代码中，注意在适当的情况下仔细通过条件判断生成单数 "bottle" 而不是复数 "bottles"：注意如何使用字符串连接运算符来拆分长长的常量字符串：

> "You take one down and pass it around"

分为两部分，以避免源代码中出现不方便的过长行。

### 15.18.2 数值类型的加法运算符 (+ 和 -)

当二元运算符 `+` 应用于两个数值类型的操作数时，它执行加法运算，产生操作数的和。

二元运算符 `-` 执行减法运算，产生两个数值型操作数的差值。

在操作数上执行二元数值型提升（§5.6）。

注意，二元数值型提升会执行值集转换（§5.1.13）并执行自动拆箱转换（§5.1.8）。

# 加法运算符

数值型操作数上加法表达式的类型是其操作数的提升类型。

如果此提升后的类型是 `int` 或 `long`，则执行整数算术。

如果此提升后的类型是 `float` 或 `double`，则执行浮点算术。

如果操作数表达式没有副作用，则加法是交换律运算。

当所有操作数均为相同类型时，整数加法具有结合律。

浮点加法不具有结合律。

如果整数加法溢出，结果是按照某些大位阶补码格式表示的数学和的低位。如果发生溢出，结果的符号与两个操作数值的数学和的符号不同。

浮点加法的结果是使用以下 IEEE 754 算术规则确定的：

- 如果任一操作数是 `NaN`，则结果为 `NaN`。
- 两个相反无穷大之和为 `NaN`。
- 两个相同符号无穷大之和为该符号的无穷大。
- 一个无穷大和一个有限值的和等于该无穷大操作数。
- 两个相反零之和为正零。
- 两个相同符号零之和为该符号的零。
- 零与非零有限值的和等于该非零操作数。
- 两个幅度相等且符号相反的非零有限值的和为正零。

在其他情况下，即既不涉及无穷大、零或 `NaN`，且操作数具有相同符号或不同幅度，将计算精确的数学和。然后选择一个浮点值：

- 如果加法表达式是 FP 严格的（§15.4）：
    - 如果加法表达式的类型是 `float`，则必须选择 float 值集。
    - 如果加法表达式的类型是 `double`，则必须选择 double 值集。
- 如果加法表达式不是 FP 严格的：
    - 如果加法表达式的类型是 `float`，则可以根据实现的意愿选择 float 值集或 float 扩展指数值。
    - 如果加法表达式的类型是 `double`，则可以根据实现的意愿选择 double 值集或 double 扩展指数值。

接下去，必须从所选的值集中选择一个值来表示和。

如果和的幅度太大到无法表示，我们称该操作溢出；此时结果则为具有适当符号的无穷大。

否则，使用 IEEE 754 舍入模式将和舍入到所选值集中最近的值。

二元运算符 `-` 执行减法运算，产生两个数值型操作数的差值。在操作数上执行二元数值型提升（§5.6）。注意，二元数值型提升会执行值集转换（§5.1.13）并执行自动拆箱转换（§5.1.8）。



# 浮点数加法规则

- 如果任一操作数是 `NaN`，则结果为 `NaN`。
- 两个相反无穷大之和为 `NaN`。
- 两个相同符号无穷大之和为该符号的无穷大。
- 一个无穷大和一个有限值的和等于该无穷大操作数。
- 两个相反零之和为正零。
- 两个相同符号零之和为该符号的零。
- 零与非零有限值的和等于该非零操作数。
- 两个幅度相等且符号相反的非零有限值的和为正零。

在其他情况下（即既不涉及无穷大、零或 `NaN`，且操作数具有相同符号或不同幅度），将计算精确的数学和。然后选择一个浮点值：

- 如果加法表达式是 FP 严格的（§15.4）：
    - 如果加法表达式的类型是 `float`，则必须选择 float 值集。
    - 如果加法表达式的类型是 `double`，则必须选择 double 值集。
- 如果加法表达式不是 FP 严格的：
    - 如果加法表达式的类型是 `float`，则可以根据实现的意愿选择 float 值集或 float 扩展指数值集。
    - 如果加法表达式的类型是 `double`，则可以根据实现的意愿选择 double 值集或 double 扩展指数值集。

接下来，必须从所选的值集中选择一个值来表示和。

如果和的幅度太大到无法表示，我们称该操作溢出；此时结果则为具有适当符号的无穷大。

否则，使用 IEEE 754 舍入模式将和舍入到所选值集中最近的值。

# 二元减法运算符 `-`

二元运算符 `-` 执行减法运算，产生两个数值型操作数的差值。在操作数上执行二元数值型提升（§5.6）。注意，二元数值型提升会执行值集转换（§5.1.13）并执行自动拆箱转换（§5.1.8）。

# 移位运算符

`<<`（左移）、`>>`（符号右移）和 `>>>`（无符号右移）称为移位运算符。

```java
ShiftExpression:
AdditiveExpression << ShiftExpression
AdditiveExpression >> ShiftExpression
AdditiveExpression >>> ShiftExpression
```

`n << s` 的值是向左移动 s 位；这等同于乘以 $2^s$。

`n >> s` 的值是向右移动 s 位并符号扩展。对于非负的 $n$，这等同于整数除法 floor(n / 2^s)。

`n >>> s` 的值是向右移动 s 位并零扩展，其中：

- 如果 $n$ 为正，则与 `n >> s` 相同。
- 如果 $n$ 为负且左操作数类型为 `int`，则结果等于 `(n >> s) + (2 << ~s)`。
- 如果 $n$ 为负且左操作数类型为 `long`，则结果等于 `(n >> s) + (2LL << ~s)`。

注意，由于移位运算符右侧操作数的隐式掩码，移位距离 s 在移动 `int` 值时等于 31-$s$，在移动 `long` 值时等于 63-$s$。

# 关系运算符

数值比较运算符 `<`、`>`、`<=`、`>=` 以及 `instanceof` 运算符称为关系运算符。

```java
RelationalExpression:
ShiftExpression
RelationalExpression < ShiftExpression
RelationalExpression > ShiftExpression
RelationalExpression <= ShiftExpression
RelationalExpression >= ShiftExpression
RelationalExpression instanceof ReferenceType
```

关系运算符在语法上是左结合的（从左到右分组）。

然而，这并没有用。例如，`a<b<c` 解析为 `(a<b)<c`，这始终是一个编译时错误，因为 `a<b` 的类型始终是 `boolean`，而 `<` 不是布尔值的运算符。

关系表达式的类型始终是 `boolean`。

## 15.20.1 数值比较运算符 `<`、`<=`、`>`、`>=`

数值比较运算符的每个操作数的类型必须是可以转换为（§5.1.8）原始数值类型的类型，否则会发生编译时错误。

对操作数执行二元数值提升（§5.6）。

> 请注意，二元数值提升会执行值集转换（§5.1.13）并可能执行拆箱转换（§5.1.8）。

如果操作数的提升后类型为 `int` 或 `long`，则执行有符号整数比较。

如果提升后类型为 `float` 或 `double`，则执行浮点数比较。

浮点数的比较是精确进行的，无论其所表示的值取自于何种值集合。

根据 IEEE 754 标准的规定，浮点数比较的结果如下：

- 如果任一操作数是 `NaN`，则结果为 `false`。
- 除 `NaN` 以外的所有值都是有序的，其中负无穷小于所有有限值，正无穷大于所有有限值。
- 正零和负零被认为是相等的。

例如，`-0.0<0.0` 为 `false`，`-0.0<=0.0` 为 `true`。

> 然而，`Math.min` 和 `Math.max` 方法将负零视为严格小于正零。

在考虑上述浮点数因素的情况下，以下规则适用于整数操作数，或除 `NaN` 以外的浮点操作数：

- 如果左侧操作数的值小于右侧操作数的值，则由 `<` 运算符产生的值为 `true`，否则为 `false`。
- 如果左侧操作数的值小于或等于右侧操作数的值，则由 `<=` 运算符产生的值为 `true`，否则为 `false`。
- 如果左侧操作数的值大于右侧操作数的值，则由 `>` 运算符产生的值为 `true`，否则为 `false`。
- 如果左侧操作数的值大于等于右侧操作数的值，则由 `>=` 运算符产生的值为 `true`，否则为 `false`。

## 15.20.2 类型比较运算符 `instanceof`

`instanceof` 运算符的 `RelationalExpression` 操作数的类型必须是引用类型或空类型，否则将产生编译时错误。

如果 `instanceof` 运算符后面提到的 `ReferenceType` 未表示可实例化的（§4.7）引用类型，则将产生编译时错误。

如果将 `RelationalExpression` 转换为 `ReferenceType` 的强制转换会被拒绝为编译时错误（§15.16），则 `instanceof` 关系表达式同样产生编译时错误。在这种情况下，`instanceof` 表达式的结果永远不会为 `true`。

在运行时，如果 `RelationalExpression` 的值不为空且转换为 `ReferenceType` 时不抛出 `ClassCastException`，则 `instanceof` 运算符的结果为 `true`。否则结果为 `false`。

### 15.20.2-1 `instanceof` 运算符示例

```java
class Point { int x, y; }
class Element { int atomicNumber; }
class Test {
    public static void main(String[] args) {
        Point p = new Point();
        Element e = new Element();
        if (e instanceof Point) { // 编译时错误
            System.out.println("I get your point!");
            p = (Point)e; // 编译时错误
        }
    }
}
```

该程序会导致编译时错误。强制转换 `(Point)e` 是错误的，因为 `Element` 或其任何子类（此处未显示）的实例都不可能是 `Point` 的任何子类的实例。`instanceof` 表达式由于完全相同的原因也是错误的。

相反，如果 `Point` 类是 `Element` 的子类（尽管在这个例子中这是一个不可认的奇怪想法）：

```java
class Point extends Element { int x, y; }
```

那么强制转换是可能的，尽管它需要运行时检查，并且 `instanceof` 表达式届将是合理且有效的。强制转换 `(Point)e` 永远不会抛出异常，因为如果 `e` 的值无法正确转换为类型 `Point`，则它将不会被执行。

# 相等性运算符

`==`（等于）和 `!=`（不等于）运算符被称为相等性操作符。

```java
EqualityExpression:
RelationalExpression
EqualityExpression == RelationalExpression
EqualityExpression != RelationalExpression
```

相等性运算符在语法上是左结合的（它们从左到右分组）。

然而，这基本上没有任何用处。例如，`a==b=c` 被解析为 `(a==b)=c`。`a==b` 的结果类型是 `boolean`，因此 `c` 必须是 `boolean` 类型，否则会发生编译时错误。因此，`a=b==c` 并不会测试 `a`、`b` 和 `c` 是否全部相等。

如果操作数表达式没有副作用，相等性运算符具有交换律。

相等性运算符与关系操作符类似，但它们的优先级较低。因此，当 `a<b` 和 `c<d` 具有相同的真值时，`a<b<c` 为 `true`。

相等性运算符可以用于比较两个数值类型（§5.1.8）操作数、两个 `boolean` 或 `Boolean` 类型的操作数、两个均为引用类型或空类型的操作数。所有其他情况都会导致编译时错误。

相等表达式的类型始终是 `boolean`。

在所有情况下，`a!=b` 产生的结果与 `!(a==b)` 相同。

如果相等性运算符的操作数都是数值类型，或者其中一个是数值类型而另一个可以转换为（§5.1.8）数值类型，则执行二元数值提升。

# 位运算符与逻辑运算符

## 包含或表达式 (`InclusiveOrExpression`)

```java
InclusiveOrExpression:
ExclusiveOrExpression
InclusiveOrExpression | ExclusiveOrExpression
```

这些运算符具有不同的优先级，其中 `&` 的优先级最高，而 `|` 的优先级最低。

这些运算符在语法上都是左结合的（从左到右分组）。

如果异或表达式没有副作用，则每个运算符都满足交换律。

每个运算符都满足结合律。

位运算符和逻辑运算符可用于比较两个数值类型的操作数，或两个布尔类型的操作数。所有其他情况都会导致编译时错误。

## 15.22.1 整数位运算符 `&`、`^`、`|`

当运算符 `&`、`^` 或 `|` 的两个操作数的类型均可转换为原始整数类型（§5.1.8）时，首先会对操作数进行二元数值提升（§5.6）。

位运算符表达式的类型是操作数提升后的类型。

对于 `&`，结果值是操作数值的按位与。

对于 `^`，结果值是操作数值的按位异或。

对于 `|`，结果值是操作数值的按位或。

例如，表达式的结果：

```java
0xff00 & 0xf0f0
```

结果是：

```java
0xf000
```

表达式的结果：

```java
0xff00 ^ 0xf0f0
```

结果是：

```java
0x0ff0
```

表达式的结果：

```java
0xff00 | 0xf0f0
```

结果是：

```java
0xffff
```

## 15.22.2 布尔逻辑运算符 `&`、`^`、`|`

当 `&`、`^` 或 `|` 运算符的两个操作数类型均为 `boolean` 或 `Boolean` 时，位运算符表达式的类型为 `boolean`。在所有情况下，操作数根据需要进行拆箱转换（§5.1.8）。

对于 `&`，如果两个操作数的值均为 `true`，则结果为 `true`；否则结果为 `false`。

对于 `^`，如果操作数的值不同，则结果为 `true`；否则结果为 `false`。

对于 `|`，如果两个操作数的值均为 `false`，则结果为 `false`；否则结果为 `true`。

# 15.23 条件与运算符 `&&`

条件与运算符 `&&` 类似于 `&`（§15.22.2），但仅当其左侧操作数的值为 `true` 时才求值其右侧操作数。

```java
ConditionalAndExpression:
InclusiveOrExpression
ConditionalAndExpression && InclusiveOrExpression
```

条件与运算符在语法上是左结合的（从左到右分组）。

条件与运算符对于副作用和结果值都是完全结合的。也就是说，对于任何表达式 `a`、`b` 和 `c`，求值表达式 `((a) && (b)) && (c)` 的结果与求值表达式 `(a) && ((b) && (c))` 的结果相同，且产生的副作用发生顺序也相同。

条件与运算符的每个操作数必须类型为 `boolean` 或 `Boolean` 类型，否则将发生编译时错误。

条件与表达式的类型始终是 `boolean`。

在运行时，首先求值左侧操作数表达式；如果结果类型为 `Boolean`，则对其进行拆箱转换（§5.1.8）。

如果结果值为 `false`，则条件与表达式的值为 `false`，且不求值右侧操作数表达式。

如果左侧操作数的值为 `true`，则求值右侧表达式；如果结果类型为 `Boolean`，则对其进行拆箱转换（§5.1.8）。结果值成为条件与表达式的值。

因此，`&&` 计算的结果与 `boolean` 操作数的 `&` 相同。区别仅在于右侧操作数表达式是有条件求值的，而不是总是求值。

# 15.24 条件或运算符 `||`

条件或运算符 `||` 类似于 `|`（§15.22.2），但仅当其左侧操作数的值为 `false` 时才求值其右侧操作数。

```java
ConditionalOrExpression:
ConditionalAndExpression
ConditionalOrExpression || ConditionalAndExpression
```

条件或运算符对于副作用和结果在语法上都是左结合的。也就是说，对于任何表达式 `a`、`b` 和 `c`，求值表达式 `((a) || (b)) || (c)` 的结果与求值表达式 `(a) || ((b) || (c))` 的结果相同，且产生的副作用发生顺序也相同。

条件或运算符的每个操作数必须类型为 `boolean` 或 `Boolean`，否则将发生编译时错误。

条件或表达式的类型始终是 `boolean`。

在运行时，首先求值左侧操作数表达式；如果结果类型为 `Boolean`，则对其进行拆箱转换（§5.1.8）。

如果结果值为 `true`，则条件或表达式的值为 `true`，且不求值右侧操作数表达式。

如果左侧操作数的值为 `false`，则求值右侧表达式；如果结果类型为 `Boolean`，则对其进行拆箱转换（§5.1.8）。结果值成为条件或表达式的值。

因此，`||` 在 `boolean` 或 `Boolean` 操作数上的计算结果与 `|` 相同。区别仅在于右侧操作数表达式是有条件求值的，而不是总是求值。

# 15.25 条件运算符 `? :`

条件运算符 `? :` 使用一个表达式的布尔值来决定应该求值两个表达式中的哪一个。

```java
ConditionalExpression:
ConditionalOrExpression
ConditionalOrExpression ? Expression : ConditionalExpression
ConditionalOrExpression ? Expression : LambdaExpression
```

条件运算符在语法上是右结合的（从右到左分组）。`a?b:c?d:e?f:g` 等于 `a?b:(c?d:(e?f:g))`。

第一个表达式类型必须为 `boolean` 或 `Boolean`，否则将发生编译时错误。

如果第二个或第三个操作数表达式任一为 `void` 方法的调用，则是编译时错误。

事实上，根据表达式语句的语法（§14.8），不允许出现条件表达式。

根据第二个和第三个操作数的类型，条件表达式分为三类：布尔条件表达式、数值条件表达式和引用条件表达式。分类规则如下：

如果第二个和第三个操作数表达式均为布尔表达式，则该条件表达式为布尔条件表达式。

为了对条件进行分类，以下表达式均为布尔表达式：

- 独立形式（§15.2）且类型为 `boolean` 或 `Boolean` 的表达式。
- 括号起来的布尔表达式（§15.8.5）。
- `Boolean` 类的实例创建表达式（§15.9）。



# 条件表达式分类

- 方法调用表达式（§15.12），其最具体的方法（§15.12.2.5）返回类型为 `boolean` 或 `Boolean`。

  > 注意，对于泛型方法，这是实例化参数前的类型。

- 布尔条件表达式。

- 结果表达式均为布尔表达式的 switch 表达式（§15.28）。

如果第二个和第三个操作数表达式均为数值表达式，则该条件表达式为数值条件表达式。

为了条件进行分类，以下表达式均为数值表达式：

- 独立形式（§15.2）且可转换为数值类型（§4.2, §15.1.8）的表达式。
- 括号起来的数值表达式（§15.8.5）。
- 可转换为数值类型的类的实例创建表达式（§15.9）。
- 方法调用表达式（§15.12），其最具体的方法（§15.12.2.5）返回类型可转换为数值类型。

  > 注意，对于泛型方法，这是实例化参数前的类型。

- 数值条件表达式。
- 结果表达式均为数值表达式的 switch 表达式（§15.28）。

否则，该条件表达式为引用条件表达式。

# 15.25 条件运算符 `? :` 表达式

确定条件表达式类型的类型取决于条件表达式的种类，具体将在接下来的章节中进行概述。

下表总结了上述规则，通过给出第二和第三操作数的所有可能类型，对应条件表达式的类型。`bnp(..)` 表示应用二元数值提升。形式“τ|bnp..”用于一个操作数是 `int` 类型的常数表达式且可能可以在 `τ` 中表示的情况，其中如果该操作数无法在 `τ` 中表示，则使用二元数值提升。操作数类型 `Object` 表示除 `null` 类型以及 `Boolean, Byte, Short, Character`, `Integer`, `Long`, `Float`, `Double` 之外的任何引用类型。

## 表 15.25-A. 条件表达式类型（基本类型第三操作数，第一部分）

| | byte | short | char | int |
|---|---|---|---|---|
| **第二操作数 ↓** | | | | |
| byte | byte | short | `bnp(byte,char)` | `bnp(byte,int)` |
| Byte | byte | short | `bnp(Byte,char)` | `bnp(Byte,int)` |
| short | short | short | `bnp(short,char)` | `bnp(short,int)` |
| Short | short | short | `bnp(Short,char)` | `bnp(Short,int)` |
| char | `bnp(char,byte)` | `bnp(char,short)` | char | `bnp(char,int)` |
| Character | `bnp(Character,byte)` | `bnp(Character,short)` | char | `bnp(Character,int)` |
| int | `bnp(int,byte)` | short | `bnp(int,short)` | `bnp(int,char)` | int |
| Integer | `bnp(Integer,byte)` | `bnp(Integer,short)` | `bnp(Integer,char)` | int |
| long | `bnp(long,byte)` | `bnp(long,short)` | `bnp(long,char)` | `bnp(long,int)` |
| Long | `bnp(Long,byte)` | `bnp(Long,short)` | `bnp(Long,char)` | `bnp(Long,int)` |
| float | `bnp(float,byte)` | `bnp(float,short)` | `bnp(float,char)` | `bnp(float,int)` |
| Float | `bnp(Float,byte)` | `bnp(Float,short)` | `bnp(Float,char)` | `bnp(Float,int)` |
| double | `bnp(double,byte)` | `bnp(double,short)` | `bnp(double,char)` | `bnp(double,int)` |
| Double | `bnp(Double,byte)` | `bnp(Double,short)` | `bnp(Double,char)` | `bnp(Double,int)` |
| boolean | `bnp(Boolean,byte)` | `bnp(Boolean,short)` | `bnp(Boolean,char)` | `bnp(Boolean,Integer)` |
| Boolean | `bnp(Boolean,byte)` | `bnp(Boolean,short)` | `bnp(Boolean,Character)` | `bnp(Boolean,Integer)` |
| null | `bnp(null,byte)` | `bnp(null,short)` | `bnp(null,Character)` | `bnp(null,Integer)` |
| Object | `bnp(Object,byte)` | `bnp(Object,short)` | `bnp(Object,Character)` | `bnp(Object,Integer)` |

## 表 15.25-B. 条件表达式类型（基本类型第三操作数，第二部分）

| 第三操作数 → | long | float | double | boolean |
|---|---|---|---|---|
| **第二操作数 ↓** | | | | |
| byte | `bnp(byte,long)` | `bnp(byte,float)` | `bnp(byte,double)` | `lub(byte,Boolean)` |
| Byte | `bnp(byte,long)` | `bnp(byte,float)` | `bnp(byte,double)` | `lub(byte,Boolean)` |
| short | `bnp(short,long)` | `bnp(short,float)` | `bnp(short,double)` | `lub(short,Boolean)` |
| Short | `bnp(short,long)` | `bnp(short,float)` | `bnp(short,double)` | `lub(short,Boolean)` |
| char | `bnp(char,long)` | `bnp(char,float)` | `bnp(char,double)` | `lub(char,Boolean)` |
| Character | `bnp(Character,long)` | `bnp(Character,float)` | `bnp(Character,double)` | `lub(Character,Boolean)` |
| int | `bnp(int,long)` | `bnp(int,float)` | `bnp(int,double)` | `lub(Integer,Boolean)` |
| Integer | `bnp(integer,long)` | `bnp(integer,float)` | `bnp(integer,double)` | `lub(Integer,Boolean)` |
| long | long | `bnp(long,float)` | `bnp(long,double)` | `lub(long,Boolean)` |
| Long | long | `bnp(long,float)` | `bnp(long,double)` | `lub(Long,Boolean)` |
| float | `bnp(float,long)` | float | `bnp(float,double)` | `lub(float,Boolean)` |
| Float | `bnp(float,long)` | float | `bnp(float,double)` | `lub(Float,Boolean)` |
| double | `bnp(double,long)` | `bnp(double,float)` | double | `lub(Double,Boolean)` |
| Double | `bnp(double,long)` | `bnp(double,float)` | double | `lub(Double,Boolean)` |
| boolean | `bnp(Boolean,long)` | `bnp(Boolean,float)` | `bnp(Boolean,double)` | boolean |
| Boolean | `bnp(Boolean,long)` | `bnp(Boolean,float)` | `bnp(Boolean,double)` | boolean |
| null | `bnp(null,long)` | `bnp(null,float)` | `bnp(null,double)` | `lub(null,Boolean)` |
| Object | `bnp(Object,long)` | `bnp(Object,float)` | `bnp(Object,double)` | `lub(Object,Boolean)` |

## 表 15.25-C. 条件表达式类型（引用第三操作数，第一部分）

| 第三操作数 → | Byte | Short | Integer |
|---|---|---|---|
| **第二操作数 ↓** | | | |
| byte | byte | short | `bnp(byte,Character)` | `bnp(byte,Integer)` |
| Byte | byte | short | `bnp(byte,Character)` | `bnp(byte,Integer)` |
| short | short | short | `bnp(short,Character)` | `bnp(short,Integer)` |
| Short | short | short | `bnp(short,Character)` | `bnp(short,Integer)` |
| char | `bnp(char,byte)` | `bnp(char,short)` | char | `bnp(char,Integer)` |
| Character | `bnp(Character,byte)` | `bnp(Character,short)` | char | `bnp(Character,Integer)` |
| int | `bnp(int,byte)` | short | `bnp(int,Character)` | int |
| Integer | `bnp(Integer,byte)` | short | `bnp(Integer,Character)` | int |
| long | `bnp(long,byte)` | `bnp(long,short)` | `bnp(long,Character)` | `bnp(long,Integer)` |
| Long | `bnp(Long,byte)` | `bnp(Long,short)` | `bnp(Long,Character)` | `bnp(Long,Integer)` |
| float | `bnp(float,byte)` | `bnp(float,short)` | `bnp(float,Character)` | `bnp(float,Integer)` |
| Float | `bnp(Float,byte)` | `bnp(Float,short)` | `bnp(Float,Character)` | `bnp(Float,Integer)` |
| double | `bnp(double,byte)` | `bnp(double,short)` | `bnp(double,Character)` | `bnp(double,Integer)` |
| Double | `bnp(Double,byte)` | `bnp(Double,short)` | `bnp(Double,Character)` | `bnp(Double,Integer)` |
| boolean | `bnp(Boolean,byte)` | `bnp(Boolean,short)` | `bnp(Boolean,Character)` | Integer |
| Boolean | `bnp(Boolean,byte)` | `bnp(Boolean,short)` | `bnp(Boolean,Character)` | Integer |
| null | `bnp(null,byte)` | `bnp(null,short)` | `bnp(null,Character)` | Integer |
| Object | `bnp(Object,byte)` | `bnp(Object,short)` | `bnp(Object,Character)` | Integer |

## 表 15.25-D. 条件表达式类型（引用第三操作数，第二部分）

| 第三操作数 → | Long | Float | Double | Boolean |
|---|---|---|---|---|
| **第二操作数 ↓** | | | | |
| byte | `bnp(byte,long)` | `bnp(byte,float)` | `bnp(byte,double)` | `lub(byte,Boolean)` |
| Byte | `bnp(byte,long)` | `bnp(byte,float)` | `bnp(byte,double)` | `lub(byte,Boolean)` |
| short | `bnp(short,long)` | `bnp(short,float)` | `bnp(short,double)` | `lub(short,Boolean)` |
| Short | `bnp(short,long)` | `bnp(short,float)` | `bnp(short,double)` | `lub(short,Boolean)` |
| char | `bnp(char,long)` | `bnp(char,float)` | `bnp(char,double)` | `lub(char,Boolean)` |
| Character | `bnp(Character,long)` | `bnp(Character,float)` | `bnp(Character,double)` | `lub(Character,Boolean)` |
| int | `bnp(int,long)` | `bnp(int,float)` | `bnp(int,double)` | `lub(Integer,Boolean)` |
| Integer | `bnp(integer,long)` | `bnp(integer,float)` | `bnp(integer,double)` | `lub(Integer,Boolean)` |
| long | long | `bnp(long,float)` | `bnp(long,double)` | `lub(long,Boolean)` |
| Long | long | `bnp(long,float)` | `bnp(long,double)` | `lub(Long,Boolean)` |
| float | `bnp(float,long)` | float | `bnp(float,double)` | `lub(float,Boolean)` |
| Float | `bnp(float,long)` | float | `bnp(float,double)` | `lub(Float,Boolean)` |
| double | `bnp(double,long)` | `bnp(double,float)` | double | `lub(Double,Boolean)` |
| Double | `bnp(double,long)` | `bnp(double,float)` | double | `lub(Double,Boolean)` |
| boolean | `bnp(Boolean,long)` | `bnp(Boolean,float)` | `bnp(Boolean,double)` | boolean |
| Boolean | `bnp(Boolean,long)` | `bnp(Boolean,float)` | `bnp(Boolean,double)` | boolean |
| null | `bnp(null,long)` | `bnp(null,float)` | `bnp(null,double)` | `lub(null,Boolean)` |
| Object | `bnp(Object,long)` | `bnp(Object,float)` | `bnp(Object,double)` | `lub(Object,Boolean)` |

## 表 15.25-E. 条件表达式类型（引用第三操作数，第三部分）

| 第三操作数 → | null | Object |
|---|---|---|
| **第二操作数 ↓** | | |
| byte | `lub(Byte,null)` | `lub(Byte,Object)` |
| Byte | | `lub(Byte,Object)` |
| short | `lub(Short,null)` | `lub(Short,Object)` |
| Short | | `lub(Short,Object)` |
| char | `lub(Character,null)` | `lub(Character,Object)` |
| Character | | `lub(Character,Object)` |
| int | `lub(Integer,null)` | `lub(Integer,Object)` |
| Integer | | `lub(Integer,Object)` |
| long | `lub(Long,null)` | `lub(Long,Object)` |
| Long | | `lub(Long,Object)` |
| float | `lub(Float,null)` | `lub(Float,Object)` |
| Float | | `lub(Float,Object)` |
| double | `lub(Double,null)` | `lub(Double,Object)` |
| Double | | `lub(Double,Object)` |
| boolean | `lub(Boolean,null)` | `lub(Boolean,Object)` |
| Boolean | | `lub(Boolean,Object)` |



| null | null | lub(null,Object) |

| Object | Object | |

随后对所选的操作数表达式进行求值，并将结果值转换为下述规则确定的条件表达式的类型。

此转换可能包括装箱或拆箱转换（§5.1.7, §5.1.8）。

未被选中的操作数表达式在该条件表达式的特定求值过程中进行求值。

## 15.25.1 布尔条件表达式

布尔条件表达式是独立的表达式（§15.2）。

布尔条件表达式的类型按如下方式确定：

- 如果第二个和第三个操作数的类型均为 `Boolean` 类型，则该条件表达式的类型为 `Boolean`。
- 否则，条件表达式的类型为 `boolean`。

## 15.25.2 数值条件表达式

数值型条件表达式是独立的表达式（§15.2）。

数值型条件表达式的类型按如下方式确定：

- 如果第二个和第三个操作数的类型相同，则该类型为条件表达式的类型。
- 如果第二个或第三个操作数是原始类型 $T$，而另一个的类型是应用装箱转换（§5.1.7）到 $T$ 的结果，则条件表达式的类型为 $T$。
- 如果其中一个操作数的类型为 `Byte` 类型，而另一个的类型为 `short` 或 `Short`，则条件表达式的类型为 `short`。
- 如果其中一个操作数的类型为 $T$（$T$ 为 `short` 或 `char`），而另一个操作数是类型为 `int` 的常量表达式（§15.29），且其值可以在类型 $T$ 中表示，则条件表达式的类型为 $T$。
- 如果其中一个操作数的类型为 $T$（$T$ 为 `Byte`、`Short` 或 `Character`），而另一个操作数是类型为 `int` 的常量表达式，其值可以在类型 $U$ 中表示（$U$ 是对 $T$ 应用拆箱转换的结果），则条件表达式的类型为 $U$。
- 否则，对第二个和第三个操作数应用通用数值提升（§5.6），条件表达式的类型为第二个和第三个操作数的提升后类型。

该数值提升执行了值转换（§5.1.13）并可能执行拆箱转换（§5.1.8）。

## 15.25 条件运算符 ? : 表达式

引用条件表达式如果出现在赋值上下文或调用上下文中则为多态表达式（poly expression）（§5.2, §5.3）。否则，它是独立表达式。

当多态引用条件表达式出现在目标类型为 $\tau$ 的特定类型上下文中，其第二个和第三个操作数表达式也同样出现在目标类型为 $\tau$ 的相同上下文中。

如果多态引用条件表达式的第二个和第三个操作数表达式与目标类型 $\tau$ 兼容，则该表达式与之兼容。

多态引用条件表达式的类型与其目标类型相同。独立引用条件表达式的类型按如下方式确定：

- 如果第二个和第三个操作数的类型相同（可能是空类型），则该类型为条件表达式的类型。
- 如果第二个或第三个操作数之一的类型为空类型，而另一个操作数的类型为引用类型，则条件表达式的类型为该引用类型。
- 否则，第二个和第三个操作数分别为类型 $S_1$ 和 $S_2$。令 $T_1$ 为对 $S_1$ 应用装箱转换得到的类型，$T_2$ 为对 $S_2$ 应用装箱转换得到的类型。条件表达式的类型为对 `lub($T_1, T_2$)` 应用捕获转换（§5.1.10）的结果。

由于引用条件表达式可以是多态表达式，它们可以“传递”到其操作数。这允许 Lambda 表达式和方法引用表达式作为操作数出现：

```java
return ... ? (x -> x) : (x -> -x);
```

它允许使用额外信息来改进泛型方法调用的类型检查。在 Java SE 8 之前，此赋值是类型安全的：

```java
List<String> ls = Arrays.asList(null);
```

但这种是不安全的：

```java
List<String> ls = ... ? Arrays.asList() : Arrays.asList("a","b");
```

上述规则使得这两个赋值均被视为类型安全的。

注意，条件表达式并不需要包含多态表达式作为操作数才能成为多态表达式。它仅仅根据其所处的上下文就是多态表达式。例如，在下面的代码中，条件表达式是一个多态表达式，每个操作数都被认为处于指向 `Class<? super Integer>` 的赋值文中：

```java
Class<? super Integer> choose(boolean b,
Class<Integer> c1,
Class<Number> c2) {
return b ? c1 : c2;
}
```

如果该条件表达式不是多态表达式，将发生编译错误，因为其类型将是 `lub(Class<Integer>,Class<Number>)=Class<? extends Number>` 这与 `choose` 的返回类型不兼容。

## 15.26 赋值运算符

AssignmentExpression:

ConditionalExpression

Assignment

Assignment:

LeftHandSide AssignmentOperator Expression

LeftHandSide:

ExpressionName

ArrayAccess

AssignmentOperator:

(Expression)

=

+=

-=

*=

%=

&=

|=

^=

>>=

<<=

>>=

此检查类似于收窄转换（§5.5, §15.16），不同之处在于如果检查失败，将抛出 `ArrayStoreException` 而不是 `ClassCastException`。

如果类 RC 不可赋值给类型 SC，则不发生赋值并抛出 `ArrayStoreException`。

否则，将右侧操作数的引用值存储到所选的组件中。

否则，则需要以下三个步骤：

- 首先，求值左侧操作数以产生一个变量。如果该评估异常完成，则赋值表达式也因相同原因异常完成；右侧操作数不会被求值且不发生赋值。
- 否则，求值右侧操作数。如果该评估异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，将右侧操作数的值转换为左侧变量的类型，经过值集转换（§5.1.13）转换到适当的标准值集（不是扩展指数值集），并将转换结果存储在该变量中。

## 示例 15.26.1-1. 数组组件的简单赋值

```java
class ArrayReferenceThrow extends RuntimeException { }
class IndexThrow extends RuntimeException { }
class RightHandSideThrow extends RuntimeException { }

class IndexSimpleArrayAssignment {
    static Object[] objects = { new Object(), new Object() };
    static Thread[] threads = { new Thread(), new Thread() };

    static Object[] arrayThrow() {
        throw new ArrayReferenceThrow();
    }

    static int indexThrow() {
        throw new IndexThrow();
    }

    static Thread rightThrow() {
        throw new RightHandSideThrow();
    }

    static String name(Object q) {
        String sq = q.getClass().getName();
        int k = sq.lastIndexOf('.');
        return (k < 0) ? sq : sq.substring(k+1);
    }
}
```

## 表达式

## 赋值运算符 15.26

```java
static void testFour(Object[] x, int j, Object y) {
String sx = x == null ? "null" : name(x[0]) + "s";
String sy = name(y);
System.out.println();
try {
    System.out.print(sx + "[throw] = => ");
    x[indexThrow()] = rightThrow();
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
try {
    System.out.print(sx + "[throw]" + sy + " = => ");
    x[indexThrow()] = y;
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
try {
    System.out.print(sx + "[++ j]" + sy + " => ");
    x[j] = rightThrow();
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
try {
    System.out.print(sx + "[++ j]" + sy + " => ");
    x[j] = y;
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
}

public static void main(String[] args) {
try {
    System.out.print("[throw]throw==> ");
    arrayThrow()[indexThrow()] = rightThrow();
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
try {
    System.out.print("[throw]throw=Thread==> ");
    arrayThrow()[indexThrow()] = new Thread();
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
try {
    System.out.print("[throw]1=Thread==> ");
    arrayThrow()[1] = rightThrow();
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
try {
    System.out.print("[throw]1=Thread==> ");
    arrayThrow()[1] = new Thread();
    System.out.println("Okay!");
} catch (Throwable e) { System.out.println(name(e)); }
}

testFour(null, 1, new StringBuffer());
testFour(null, 9, new Thread());
testFour(objects, 1, new StringBuffer());
testFour(objects, 9, new StringBuffer());
testFour(objects, 9, new Thread());
testFour(threads, 1, new StringBuilder());
testFour(threads, 1, new Thread());
testFour(threads, 9, new StringBuilder());
testFour(threads, 9, new Thread());
}
```

该程序产生输出：

```
throw[throw]=throw => ArrayReferenceThrow
throw[throw]=Thread => ArrayReferenceThrow
throw[1]=throw => ArrayReferenceThrow
throw[1]=Thread => ArrayReferenceThrow
null[throw]=throw => IndexThrow
null[throw]=StringBuffer => IndexThrow
null[1]=throw => RightHandSideThrow
null[1]=StringBuffer => NullPointerException
null[throw]=throw => IndexThrow
null[throw]=Thread => IndexThrow
null[9]=throw => RightHandSideThrow
null[9]=throw => NullPointerException
Objects[throw]=throw => IndexThrow
Objects[throw]=StringBuffer => IndexThrow
Objects[1]=throw => RightHandSideThrow
Objects[1]=StringBuffer => Okay!
Objects[throw]=throw => IndexThrow
Objects[throw]=Thread => IndexThrow
Objects[1]=throw => RightHandSideThrow
Objects[1]=StringBuffer => Okay!
Objects[throw]=throw => IndexThrow
Objects[throw]=StringBuffer => IndexThrow
Objects[9]=throw => ArrayIndexOutOfBoundsException
Threads[throw]=throw => IndexThrow
Threads[throw]=StringBuffer => IndexThrow
Threads[1]=throw => RightHandSideThrow
Threads[9]=throw => ArrayIndexOutOfBoundsException
Threads[throw]=throw => IndexThrow
Threads[throw]=Thread => IndexThrow
Threads[1]=throw => RightHandSideThrow
Threads[1]=StringBuffer => ArrayStoreException
Threads[throw]=throw => IndexThrow
Threads[throw]=StringBuffer => IndexThrow
Threads[9]=throw => ArrayIndexOutOfBoundsException
Threads[throw]=throw => IndexThrow
Threads[throw]=Thread => IndexThrow
Threads[9]=throw => RightHandSideThrow
Threads[9]=Thread => ArrayIndexOutOfBoundsException
```

## 15.26 赋值运算符

## 表达式

所有情况中最有趣的是倒数第十三个：`Threads[throw]=StringBuffer`，它的情况是如果将 `StringBuffer` 存储到 `Threads` 数组中将抛出 `ArrayStoreException`，因为左侧是 `Threads` 数组的引用，右侧是 `StringBuffer`。在编译时，`testFour` 的左侧类型为 `Object`，而右侧类型为 `Object`。

## 15.26 复合赋值运算符

复合赋值表达式 `E1 op= E2` 等价于 `E1 = (T)(E1 op E2)`，其中 `T` 是 `E1` 的类型，且 `E1` 只被求值一次。例如，以下代码是正确的：

```java
short x = 3;
x += 4;
```

结果相当于：

```java
short x = x + 4;
```

在运行时，按以下方式评估表达式。如果左侧操作数不是数组表达式，则：

- 首先，求值左侧操作数以产生一个变量。如果该评估异常完成，则赋值表达式也因相同原因异常完成；右侧操作数不会被求值且不发生赋值。
- 否则，保存左侧操作数的值并求值右侧操作数。如果该评估异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，使用保存的左侧变量值和右侧操作数的值执行复合运算符指示的运算。如果该运算异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，将运算结果转换为左侧变量的类型，经过值转换（§5.1.13）转换到适当的标准值集（不是扩展指数值集），并将转换结果存储在变量中。

如果左侧操作数是数组表达式（§15.10.3），则：

- 首先，求值左侧访问表达式的数组引用子表达式。如果该评估异常完成，则赋值表达式也因相同原因异常完成；左侧表达式的索引子表达式和右侧操作数都不会被求值且不发生赋值。
- 否则，求值左侧访问表达式的索引子表达式。如果该评估异常完成，则赋值表达式也因相同原因异常完成且右侧操作数不会被求值且不发生赋值。
- 否则，如果数组引用子表达式的值为 `null`，则不发生赋值并抛出 `NullPointerException`。



## 赋值操作符

- 否则，如果索引子表达式的值小于零或大于等于数组的长度，则不发生赋值并抛出 `ArrayIndexOutOfBoundsException`。

- 否则，使用索引子表达式的值选择数组引用子表达式所引用的数组组件。该组件的值被保存，然后求值右侧操作数。如果该评估异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。

对于简单赋值运算符，右侧操作数的求值发生在数组引用子表达式和索引子表达式检查之前；但对于复合赋值运算符，右侧操作数的求值发生在这些检查之后。

- 否则，考虑上一步中选定的数组组件，其值已被保存。这是一个变量；调用其类型为 `s`。同时，令 `τ` 为赋值操作符左侧操作数的类型，该类型在编译时确定。

- 如果 `T` 是基本数据类型，则 `S` 必然与 `T` 相同。

数组组件的保存值和右侧操作数的值被用于执行由复合赋值操作符所指示的二元操作。

如果此操作异常终止（唯一的情况是整数除以零 —— 见 §15.17.2），则赋值表达式也因相同的原因异常终止，且不发生赋值。

否则，二元操作的结果将转换为所选数组组件的类型，并根据值转换 (§5.1.13) 转换为适当的标准值集（而非扩展精度值集），并将转换后的结果存储到数组组件中。

- 如果 `T` 是引用类型，则它必须是 `String`。由于类 `String` 是一个最终类（final class），`S` 也必须是 `String`。

> 因此，赋值操作符需要满足的运行时检查对于复合赋值操作符是不需要的。

数组组件的保存值和右侧操作数的值被用于执行二元操作（字符串拼接）（这必然是 `+=`）。如果此操作异常终止，则赋值表达式也因相同的原因异常终止，且不发生赋值。

否则，二元操作的 `String` 结果被存储到数组组件中。

### 示例 15.26.2-1. 赋值给数组组件

```java
class ArrayReferenceThrow extends RuntimeException { }
class IndexThrow extends RuntimeException { }
class RightHandSideThrow extends RuntimeException { }

class IllustrateCompoundArrayAssignment {
    static String[] strings = { "Simon","Garfunkel" };
    static double[] doubles = { Math.E, Math.PI };

    static String[] stringsThrow() {
        throw new ArrayReferenceThrow();
    }
    static double[] doublesThrow() {
        throw new ArrayReferenceThrow();
    }

    static int indexThrow() {
        throw new IndexThrow();
    }
    static String stringThrow() {
        throw new RightHandSideThrow();
    }
    static double doubleThrow() {
        throw new RightHandSideThrow();
    }
    static String name(Object q) {
        String sq = q.getClass().getName();
        int k = sq.lastIndexOf('.');
        return (k < 0) ? sq : sq.substring(k+1);
    }
    static void testEight(String[] x, double[] z, int j) {
        String sx = (x == null) ? "null" : "Strings";
        String sz = (z == null) ? "null" : "doubles";
        System.out.println(sz);
        try {
            System.out.print(sx + " [ + [throw]+=throw => ");
            x[indexThrow()] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sz + " [ + [throw]+=throw => ");
            z[indexThrow()] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sx + " [ + [throw]+=heh => ");
            x[indexThrow()] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sz + " [ + [throw]+=12345 => ");
            z[indexThrow()] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sx + " [ + [throw]+=throw => ");
            x[j] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sz + " [ + [throw]+=throw => ");
            z[j] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sx + " [ + [throw]+=heh => ");
            x[j] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sz + " [ + [throw]+=12345 => ");
            z[j] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
    }

    public static void main(String[] args) {
        try {
            System.out.print("throw[1]+=throw => ");
            stringsThrow()[1] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[1]+=throw => ");
            doublesThrow()[1] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[1]+=heh => ");
            stringsThrow()[1] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[1]+=12345 => ");
            doublesThrow()[1] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[null]+=throw => ");
            stringsThrow(null) += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[null]+=throw => ");
            doublesThrow(null) += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[null]+=heh => ");
            stringsThrow(null) += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print("throw[null]+=12345 => ");
            doublesThrow(null) += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sx + "[" + j + "]+=throw => ");
            strings[j] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sz + "[" + j + "]+=throw => ");
            doubles[j] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sx + "[" + j + "]+=heh => ");
            strings[j] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
        try {
            System.out.print(sz + "[" + j + "]+=12345 => ");
            doubles[j] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
    }
}
```

### 示例 15.26.2-2. 复合赋值的左侧值在赋值右侧之前被保存

```java
class Test {
    public static void main(String[] args) {
        int k = 1;
        int[] a = { 1 };
        k += (k = 4) * (k + 2);
        a[0] += (a[0] = 4) * (a[0] + 2);
        System.out.println("k==" + k + " and a[0]==" + a[0]);
    }
}
```

此程序输出为：

```
k==25 and a[0]==25
```

值 1 被复合赋值操作符 `+=` 保存，在其右侧操作数 `(k = 4) * (k + 2)` 求值之前。该右侧操作数的求值随后将 4 赋值给 k，计算 k+2 的值 6，并将 4 乘以 6 得到 24。此结果加到保存的值 1 上得到 25，然后由赋值操作符存储到 k 中。使用 a[0] 的情况适用于相同的分析。

简而言之，语句：

```java
k += (k = 4) * (k + 2);
a[0] += (a[0] = 4) * (a[0] + 2);
```

的行为与以下语句完全相同：

```java
k = k + (k = 4) * (k + 2);
a[0] = a[0] + (a[0] = 4) * (a[0] + 2);
```

## Lambda 表达式

Lambda 表达式类似于方法：它提供了一个形式参数列表和一个主体——一个用参数表示的表达式或代码块。

### 15.27 Lambda 表达式

Lambda 表达式始终是多表达式（§15.2）。

如果 Lambda 表达式出现在程序赋值上下文（§5.2）、调用上下文（§5.3）或类型转换上下文（§5.5）之外的地方，则会导致编译错误。

Lambda 表达式的求值产生一个函数式接口的实例（§9.8）。Lambda 表达式的求值不会导致表达式体的执行；相反，可能会在之后调用函数式接口的适当方法时发生。

以下是一些 Lambda 表达式的示例：

```java
() -> { } // 无参数；结果为 void
() -> 42 // 无参数，表达式体
() -> null // 无参数，表达式体
() -> { return 42; } // 无参数，带有返回的块体
() -> { System.gc(); } // 无参数，void 块体
() -> { // 带有多个返回的复杂块体
    if (true) return 12;
    else {
        int result = 15;
        for (int i = 1; i < 10; i++)
            result *= i;
        return result;
    }
}
```

```java
(int x) -> x+1 // 单一声明类型参数
(int x) -> { return x+1; } // 单一声明类型参数
(x) -> x+1 // 单一推断类型参数
x -> x+1 // 括号可选 // 单一推断类型参数
(String s) -> s.length() // 单一声明类型参数
(Thread t) -> { t.start(); } // 单一声明类型参数
s -> s.length() // 单一推断类型参数
t -> { t.start(); } // 单一推断类型参数
(int x, int y) -> x+y // 多个声明类型参数
(x, y) -> x+y // 多个推断类型参数
(int x, final y) -> x+y // 非法：不能混合推断类型和声明类型
(x, final y) -> x+y // 非法：推断类型不能带有修饰符
```



这种语法的优势是减少了简单 Lambda 表达式周围的括号噪音，这在 Lambda 表达式作为方法的参数或其体是另一个 Lambda 表达式时特别有益。它还清晰地区分了表达式形式和语句形式，避免了歧义或对 `;` 标记的过度依赖。当需要括号来区分整个 Lambda 表达式或其体表达式时，自然支持括号（就像在运算符优先级不明确的其他情况下一样）。

该语法存在一些解析挑战。Java 语言一直要求向前查找以在 `(` 标记之后区分类型和表达式：后续内容可能是类型转换或括号表达式。当泛型在类型中引入了二进制运算符 `<` 和 `>` 时，情况变得更加糟糕。Lambda 引入了新的可能性：随后的标记可能描述类型、表达式或 Lambda 参数列表。某些标记可能表示带有注解的参数列表（例如 `(final x);` 一连排名称、一个 `;`；未嵌套）；并且在遇到 `)` 之后的 `-` 之前无法做出决定。思考如何高效解析这种最简单的方法是使用状态机：每个状态代表可能解释的子集（类型、表达式或参数），当机器转换到一个集合只有一个元素的状态时，解析器就知道是哪种情况了。这很难映射到固定循环语法。

没有特殊的空值形式：零参数的 Lambda 表达式表示为 `() -> ...`。显而见的特殊情况 `-> ...` 不可行，因为它引入了表达式和列表之间的歧义：`(x)`。

Lambda 表达式不声明类型。虽然在语义上这样做是有意义的，但自然的语法（在参数列表之前带有类型列表）引入了混乱的歧义。例如：

```java
foo(x < y, z > (w) -> v)
```

这可能是 `foo` 的单参数调用（一个强制转换为 x 的泛型 Lambda），也可能是 `foo` 的双参数调用，两个参数都是比较的结果，第二次比较是将 z 与 Lambda 表达式进行比较。（严格来说，Lambda 表达式作为关系运算符 `>` 的操作数是无意义的，但那是构建语法的薄弱假设）

使用类型转换解决歧义是有先例的，这本质上禁止了在非原始类型转换后使用 `-` 及其后续内容（§15.15），但将此方法扩展到泛型 Lambda 将涉及对语法的侵入性更改。

## 15.27.1 Lambda 参数

Lambda 表达式的形式参数（如果有）通过圆括号括起来的逗号分隔标识符列表或逗号分隔的参数限定符列表来指定。在参数限定符列表中，每个参数限定符由可选的修饰符、一个类型（或 `var`）以及一个指定参数名称的标识符组成。在标识符列表中，每个标识符指定参数名称。

如果 Lambda 表达式没有形式参数，则在 `->` 和 Lambda 体之前会出现一对空括号。

如果 Lambda 表达式恰好有一个形式参数，且该参数由标识符而不是参数限定符指定，则标识符周围的括号可以省略。

LambdaParameters:
`( [LambdaList] )`

`Identifier`

LambdaParameterList:
`LambdaParameter (, LambdaParameter)`

`Identifier (, Identifier)`

LambdaParameter:
`{VariableModifier} LambdaParameterType VariableDeclaratorId`

`VariableArityParameter`

LambdaParameterType:
`UnannType`
`var`

为了方便，这里显示了 §8.4、§8.3 和 §4.3 的产生式：

VariableArityParameter:
`{VariableModifier} UnannType`

VariableModifier:
`Annotation`

VariableDeclaratorId:
`Identifier`

Dims:
`{[Annotation]}`

只有当 Lambda 表达式的形式参数通过参数限定符指定时，才能声明为 `final` 或带有注解。如果形式参数由标识符指定，则该形式参数不是 `final` 且没有注解。

Lambda 表达式的形式参数可以是变长参数，通过参数限定符中类型后的省略号 `...` 表明。一个 Lambda 表达式最多允许一个变长参数。如果变长参数出现在限定符列表的最后一个位置之前的任何地方，则会导致编译错误。

Lambda 表达式的每个形式参数要么具有推断类型要么具有声明类型：

- 如果形式参数通过使用 `var` 的参数限定符指定，或者通过标识符代替参数限定符指定，则该参数具有推断类型。该类型根据 Lambda 表达式的目标函数式接口推断（§15.27.3）。
- 如果形式参数通过不使用 `var` 的参数限定符指定，则该形式参数具有声明类型。声明类型的确定如下：
  - 如果形式参数不是变长参数，当 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号时，声明类型为 `UnannType`，见 §10.2。
  - 如果形式参数是变长参数，则声明类型为数组类型 §10.2。

在以下 Lambda 参数列表之间没有区别：

```java
(int... x) -> BODY

(int[] x) -> BODY
```

无论函数式接口的抽象方法是固定长度还是变长的，两者都可以使用。由于 Lambda 表达式从不直接调用，在函数式接口使用 `int[]` 的地方使用 `int...` 对周围程序没有影响。在 Lambda 体中，变长参数被视为类似于数组类型的参数。

所有形式参数都具有声明类型的 Lambda 表达式被称为显式类型化的。所有形式参数都具有推断类型的 Lambda 表达式被称为隐式类型化的。没有形式参数的 Lambda 表达式是显式类型化的。

> 如果 Lambda 表达式是隐式类型，则其 Lambda 体根据其所出现的上下文进行解释。具体来说，体中表达式的类型、体抛出的受检异常以及体中代码的类型正确性都取决于为形式参数推断出的类型。这意味着形式参数的推断必须在尝试类型检查 Lambda 体“之前”发生。

如果 Lambda 表达式声明了一个具有声明类型的形式参数和一个具有推断类型的形式参数，则会导致编译错误。

此规则防止在形式参数中混合使用推断类型和声明类型，例如 `(x, int y) -> BODY` 或 `(var x, int y) -> BODY`。请注意，如果所有形式参数都具有推断类型，语法将防止混合使用标识符和 `var` 参数说明，例如 `(x, y) -> BODY` 或 `(var x, y) -> BODY`。

关于形式参数声明上的类型注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

如果 `final` 作为形式参数声明的修饰符出现超过一次，则为编译错误。

如果形式参数的 `LambdaParameterType` 为 `var` 且该形式参数的 `VariableDeclaratorId` 包含一个或多个括号对，则为编译错误。

形式参数声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

Lambda 表达式声明两个同名的形式参数将为编译错误。（也就是说，它们的声明提到了同一个 `Identifier`。）

在 Java SE 8 中，禁止使用 `_` 作为 Lambda 参数的名称，并且不鼓励将其作为其他变量的名称（§4.12.3）。从 Java SE 9 开始，`_` 是一个关键字 (§3.9)，因此在任何上下文中不能用作变量名。

如果被声明为 `final` 的形式参数在 Lambda 表达式体内部赋值，则为编译错误。

当调用 Lambda 表达式时（通过方法调用表达式 (§15.12)），实际参数表达式的值将初始化 Lambda 体中出现的每个新创建参数变量，每个变量具有声明或推断的类型。`Identifier` 或直接在 `LambdaParameterList` 或 `LambdaParameters` 中的标识符可以在 Lambda 体中作为简单名称来引用该形式参数。

类型为 `float` 的 Lambda 表达式形式参数包含 `float` 值集中的元素；类似地，类型为 `double` 的 Lambda 表达式形式参数始终包含 `double` 值集中的一个元素。Lambda 表达式类型为 `float` 的形式参数不允许包含属于 `float-extended-exponent` 值集但又不属于 `float` 值集的元素，Lambda 表达式类型为 `double` 的形式参数也不允许包含属于 `double-extended-exponent` 值集但又不属于 `double` 值集的元素。

## 15.27.2 Lambda 体

Lambda 体可以是一个单一表达式或一个代码块 (§14.2)。与方法体一样，Lambda 体描述了在每次发生调用时将执行的代码。

LambdaBody:
- `Expression`
- `Block`

与匿名类声明中出现的代码不同，Lambda 体中出现的名称含义、`this` 和 `super` 关键字的含义，以及递归声明引用的可访问性，与周围上下文相同（但 Lambda 参数引入了新名称）。

Lambda 表达式体中对这种 `this`（无论是显式的还是隐式的）的透明性——即将其视为与周围上下文相同的情形——为实现提供了更大的灵活性，并防止了体中未限定名称的合并依赖于重载解析。

从实践上来说，Lambda 表达式需要引用自身（为了递归调用自身或调用其其他方法）是不寻常的，而常见的是使用名称来引用原本会被遮蔽的外部类（例如 `this.toString()`）。如果 Lambda 表达式确实需要引用自身（例如通过 `this`），则应该使用方法引用或匿名内部类。

如果块中的每个 `return` 语句的形式都是 `return;`，则该 Lambda 体是 void 兼容的（void-compatible）。

如果 Lambda 无法正常完成 (§14.2) 且块中的每个 `return` 语句的形式都是 `return Expression;`，则该 Lambda 体是值兼容的（value-compatible）。

如果 Lambda 体既不是 void 兼容的不是值兼容的，则为编译错误。

在值兼容的块级 Lambda 体中，结果表达式是任何可能产生调用值的表达式。具体而言，对于受体限制的格式为 `return Expression;` 的语句，`Expression` 都是结果表达式。

以下 Lambda 体是 void 兼容的：

```java
() -> {}

() -> { System.out.println("done"); };
```

以下是值兼容的：

```java
() -> { return "done"; }

() -> { if (...) return 1; else return 0; }
```

这些是两者兼备的：

```java
() -> ( throw new RuntimeException(); )

() -> ( while (true); )
```

此者都不是：

```java
() -> { if (...) return "done"; System.out.println("done");
```

void/值兼容的处理以及体中名称的含义共同有助于最大限度地减少对给定上下文中特定目标类型的依赖，这对于实现和程序员的理解是有用的。虽然表达式可以根据目标类型通过重载分配不同的类型，但未限定变量的含义和 Lambda 体的基本结构不会改变。

注意，void/值兼容的定义并不是严格的属性：“能够正常完成”取决于常量表达式的值，而这些常量表达式可能包含引用常量变量的名称。

任何在 Lambda 表达式中使用但未声明的局部变量、形式参数或异常参数必须被声明为 `final` 或是有效 final（effectively final, §14.2.4），否则在尝试使用时会发生编译错误。

任何在 Lambda 体中使用但未声明的局部变量必须在 Lambda 体之前被确定赋值 (§15.6 (Definite Assignment))，否则会发生编译错误。

内部类体中 (§8.1.3) 也适用类似的变量规则。对有效 final 变量的限制禁止了对动态变化的局部变量的访问，因为捕获这些变量可能会引入并发问题。与 `final` 限制相比，它减轻了程序员的文书负担。

对有效 final 变量的限制包括标准循环变量，但不包括增强型 for 循环变量，后者在循环的每次迭代中被视为不同的变量 (§14.2.2)。

以下 Lambda 体演示了有效 final 变量的使用。

```java
void ml(int x) {
    int y = 1;
    foo() -> x+y;
    // 合法：x 和 y 都是有效 final。
}
```

```java
void m2(int x) {
    int y;
    y = 1;
    foo(() -> x+y);
    // 合法：x 和 y 都是有效 final。
}
```

```java
void m3(int x) {
  int y;
  if (...) y = 1;
  foo(() -> x+y);
  // 非法：y 是有效 final，但未被赋值。
}
```

```java
void m4(int x) {
  int y;
  if (...) y = 1;
  else y = 2;
  foo(() -> x+y);
  // 合法：x 和 y 都是有效 final。
}
```

```java
void m5(int x) {
  int y;
  if (...) y = 1;
  else y = 2;
  foo(() -> x+y);
  // 非法：y 不是有效 final。
}
```

```java
void m6(int x) {
  foo(() -> x+1);
  x++;
  // 非法：x 不是 final。
}
```

```java
void m7(int x) {
  foo(() -> x=1);
  // 非法：x 不是 final。
}
```

```java
void m8() {
  int y;
  foo(() -> y=1);
  // 非法：y 在 Lambda 之前未赋值。
}
```

```java
void m9(String[] arr) {
  for (String s : arr) {
    foo(() -> s);
    // 合法：s 是有效 final
    （每次迭代都是新变量）
  }
}
```

```java
void m10(String[] arr) {
  for (int i = 0; i < arr.length; i++) {
    foo(() -> arr[i]);
    // 非法：i 不是 final
    （它被自增）
  }
}
```

## 15.27.3 Lambda 表达式的类型

Lambda 表达式在赋值上下文、调用上下文或类型转换上下文中目标类型 T 兼容，如果 T 是函数接口类型 (§9.8) 且表达式与从 T 导出的函数类型一致。

目标类型 T 的导出如下：

- 如果 T 是泛配符化的函数接口且 Lambda 表达式是显式类型，则推断为 §18.5.3。
- 如果 T 是泛配符化的函数接口且 Lambda 表达式是隐式类型，则为 T 的非泛配符参数化 (§9.9)。
- 否则，目标类型为 T。

Lambda 表达式与函数类型一致当且仅当满足以下条件时：

- 函数类型没有参数。
- Lambda 参数的数量与函数类型的参数类型数量相同。
- 如果 Lambda 表达式是显式类型，其形式参数类型与函数类型的参数类型相同。
- 假设 Lambda 参数类型与函数类型的参数类型相同，那么：
  - 如果函数的返回类型为 void，则 Lambda 体是语句表达式 (§14.8) 或 void 兼容块。
  - 如果函数的返回类型是（非 void）类型 R，则要么 (i) Lambda 体在赋值上下文中兼容 R，要么 (ii) Lambda 体是值兼容块，且每个结果表达式 (§15.27.2) 在赋值上下文中兼容 R。

## Lambda 表达式

如果 lambda 表达式与目标类型 T 兼容，则该表达式的类型 U 是从 T 派生出的基础类型（ground type）。

如果 lambda 表达式所出现的类或接口与 U 或 U 的函数类型相遇的任何类或接口均不可访问的（见 §6.6），则将产生编译时错误。

对于 U 的每个非静态成员 m，如果 U 的函数类型具有 m 签名的子签名（subsignature），则可能会发生一个类型为 U 并视为覆盖了 m 的命名方法，以及 §8.4.8.3 中指定的任何编译时错误或未检查警告。

在 lambda 表达式体中可以抛出受检异常（checked exception），这会导致编译时错误，如 §11.2.3 所示。

显式类型 lambda 的参数要求与函数类型的参数完全匹配。虽然可以更灵活一些——例如允许装箱或逆变——但这种泛用性似乎并没有必要的，而且与类声明中重写机制的工作方式不一致。程序员在编写 lambda 表达式时应当知道目标是哪种函数类型，因此他应该确切地知道必须覆盖哪个签名。（相比之下，方法引用的情况并非如此，因此在使用它们时允许更大的灵活性。）此外，参数类型的更大灵活性会增加类型推断和重载解析的复杂性。

注意，虽然在严格的调用上下文中不允许装箱，但 lambda 结果的装箱总是允许的——也就是说结果表达式出现在赋值上下文中，无论封装 lambda 表达式的上下文是如何。然而，如果一个显式 lambda 表达式是重载方法的参数，最具体的检查（§15.12.2.5）倾向于选择避免对 lambda 结果进行装箱或拆箱的方法签名。

如果 lambda 的体是一个语句表达式（即允许单独作为语句存在的表达式），则它与产生 void 结果的函数类型兼容；任何结果都会被丢弃。例如，以下两种方式都是合法的：

```java
// Predicate 有一个布尔结果
java.util.function.Predicate<String> s = s -> list.add(s);

// Consumer 有一个 void 结果
```



`java.util.function.Consumer<String> c = s -> list.add(s);`

通常情况下，形式为 `() -> expr` 的 lambda（其中 `expr` 是语句表达式）根据目标类型被解释为 `() -> { return expr; }` 或 `() -> { expr; }`。

## 15.27.4 Lambda 表达式的运行时评估

在运行时，lambda 表达式的评估类似于类实例创建表达式的评估，因为其正常完成会产生一个对象的引用。lambda 表达式的评估与 lambda 体的执行是有区别的。

要么分配并初始化一个具有以下属性的类的新实例，要么引用一个具有以下属性的类的现有实例。如果需要创建新实例但空间不足以分配，则 lambda 表达式的评估将通过抛出 `OutMemoryError` 异常终止。

这意味着评估 lambda 表达式的结果（或序列化和反序列化 lambda 表达式的结果）的身份是不可预测的，因此，身份敏感的操作（如引用等效性 §15.21.3、对象锁定 §14.19）在 Java 编程语言的不同实现中，甚至在同一实现中的不同 lambda 表达式上，都可能产生不同的结果。

lambda 表达式的值指向一个具有以下属性的类实例引用：

- 该类实现了目标函数接口类型；如果目标类型是交类型，则实现了交类型中提到的每一个其他接口类型。
- 当 lambda 表达式类型为 `U` 时，对于 `U` 的每个非静态成员方法 `m`。

如果类型 `U` 的签名与 `m` 的签名相同，则该类声明覆盖了 `m`。该方法体具有评估 lambda 体（如果它是表达式）或执行 lambda 体（如果它是代码块）的效果；如果需要结果，则从方法返回该结果。

如果被覆盖类型的擦除在签名上与 `U` 的函数类型的擦除不同，则在评估或执行 lambda 体之前，方法体会检查每个参数值是否为 `U` 的函数类型中对应参数类型擦除的子类或子接口的实例；如果不是，将抛出 `ClassCastException`。

- 该类没有覆盖目标函数接口类型或上述其他其他接口类型的其他其他方法，尽管它可能会覆盖 `Object` 类的方法。

这些规则旨在为 Java 编程语言的实现提供灵活性，因为：

- 并不每次评估都分配一个新对象。
- 评估表达式产生的对象不需要属于不同的类（例如，如果体是相同的）。
- 评估的产物不需要属于同一个类（例如，捕获的局部变量可能会倾向于此）。
- 如果存在“现有实例”，它可能在之前的 lambda 评估并未被创建（例如，它可能在封装类的初始化期间被分配）。

如果目标函数接口是 `java.io.Serializable` 的子类型，生成的对象将自动成为可序列化类的实例。使派自 lambda 表达式的对象可序列化可能会带来额外的运行时开销和安全影响，因此 lambda 派生对象并不要求“默认”是可序列化的。

## 15.28 switch 表达式

switch 表达式根据表达式的值将控制转移到多个语句或表达式之一；该表达式的所有可能值都必须被处理，并且所有的语句和表达式必须为 switch 表达式的结果产生一个值。

SwitchExpression:

```
switch ( Expression ) SwitchBlock
```

`Expression` 是选择表达式。选择表达式的类型必须是 `char`、`byte`、`short`、`int`、`Character`、`Byte`、`Short`、`Integer`、`String` 或枚举类型（§8.9），否则将出错。

switch 和 switch 语句的体（§14.11）被称为 switch 块。switch 块的通用规则（无论出现在 switch 表达式还是 switch 语句中）见 §14.11。此处显示了 §14.11 中的以下产生式：

```
SwitchBlock:
{ SwitchRule }
SwitchStatementGroup [SwitchLabel : }
```

```
SwitchRule:
SwitchLabel -> Expression
SwitchLabel -> Block
SwitchLabel -> ThrowStatement
```

```
SwitchStatementGroup:
SwitchLabel : BlockStatements
```

### 表达式

### 15.28.1 switch 表达式的 Switch Block

```
SwitchLabel:
case CaseConstant [, CaseConstant]
default
```

```
CaseConstant:
ConditionalExpression
```

除了 switch 块的通用规则（§14.11.1），switch 表达式还有进一步的规则。也就是说，switch 块必须满足以下所有条件，否则将出错：

- 如果选择表达式的类型不是枚举类型，则 switch 块必须有一个 `default` 标签。
- 如果选择表达式的类型是枚举类型，则 (i) switch 块关联的 case 集合包含了该枚举类型的每一个常量，且 (ii) switch 块最多有一个 `default` 标签。

> 当 case 标签覆盖了所有枚举常量时，允许但并不要求 `default` 标签。

- 如果 switch 块由 switch 规则组成，则任何 switch 规则不能正常完成（§14.22）。
- 如果 switch 块由 switch 语句组成，则 switch 块中的最后一个语句不能正常完成，且 switch 块在最后一个语句组后不再有任何标签。

与 switch 语句不同，switch 表达式不能空 switch 块。此外，switch 表达式与 switch 语句的区别在于 switch 块中箭头（`->`）右侧可以使用的表达式。在 switch 表达式中，任何表达式都可以作为 switch 规则表达式，但在 switch 语句中，只有语句可以作为规则（§14.11.1）。

switch 表达式的结果确定如下：

- 如果 switch 块由 switch 规则组成，则依次考虑每个 switch 规则：
- 如果 switch 规则形式为 `... -> Expression`，则 `Expression` 是 switch 表达式的结果。
- 如果 switch 规则形式为 `... -> Block`，则 Block 中任何直接包含在 `yield` 语句中且 `yield` 目标为给定的 switch 表达式的表达式，都是 switch 表达式的结果。
- 如果 switch 块由带有 switch 标签的语句组成，则 switch 块中直接包含在 yield 语句中的、其 yield 目标为给定的 switch 表达式的每一个表达式，都是该 switch 表达式的结果表达式。

如果 switch 表达式没有结果表达式，则将产生编译时错误。

如果 switch 表达式出现在赋值上下文或调用上下文中（#5.2, #5.3），则它是一个多值表达式（poly expression）。否则，它是一个独立表达式。

当多值 switch 表达式出现在具有目标类型 $\tau$ 的特定类型上下文中，其结果同样出现在具有目标类型 $\tau$ 的相同类型的上下文中。

如果多值 switch 表达式的每个表达式都与目标类型 $\tau$ 兼容，则该表达式也与 $\tau$ 兼容。

多值 switch 表达式的类型与其目标类型相同。

独立 switch 表达式的类型确定如下：

- 如果所有结果表达式具有相同的类型（可能是空类型 (#4.1)），则该类型为 switch 表达式的类型。
- 否则，如果每个结果表达式的类型为 `boolean` 或 `Boolean`，则对每个类型为 `Boolean` 的结果表达式应用去箱转换 (#5.18)，且 switch 表达式类型为 `boolean`。
- 否则，如果每个结果表达式的类型都能转换为数值类型 (#5.1.8)，则 switch 表达式的类型为对结果表达式应用通用数值提升 (#5.6) 的结果。
- 否则，对每个具有原始类型的结果表达式应用装箱转换 (#5.1.7)，之后，switch 表达式的类型为对结果类型的最小上界 (#4.10.4) 应用捕获转换 (#5.1.10) 的结果。

## 15.28.2 switch 表达式的运行时求值

switch 表达式的求值首先求值选择器表达式。然后：

- 如果求值选择器表达式异常完成，则 switch 表达式也以相同的原因异常完成。
- 否则，如果求值选择器表达式的结果为 `null`，则抛出 `NullPointerException`，整个 switch 表达式因该原因异常完成。
- 否则，如果求值选择器表达式的结果类型为 `Character`、`Byte`、`Short` 或 `Integer`，则对其进行去箱转换（§5.1.8）。如果该转换异常完成，则 switch 表达式以相同的原因异常完成。

如果求值选择器表达式正常完成且结果为非空，且后续的去箱转换（如果有）正常完成，则继续求值 switch 表达式，确定与 switch 块关联的 switch 标签是否匹配选择器表达式的值（§14.11.1）。然后：

- 如果没有 switch 标签匹配，则抛出 `IncompatibleClassError`，整个 switch 表达式因该原因异常完成。
- 如果匹配 switch 标签，则适用以下情况：
  - 如果它是 switch 规则表达式的 switch 标签，则求值该表达式。如果求值结果是一个值，则 switch 表达式以相同的值正常完成。
  - 如果它是 switch 规则块的 switch 标签，则执行该块。如果该块正常完成，则 switch 表达式正常完成。
  - 如果它是 switch 规则 throw 语句的 switch 标签，则执行该语句。
  - 否则，执行 switch 块中匹配的 switch 标签之后的所有语句。如果这些语句正常完成，则 switch 表达式正常完成。

如果 switch 块中任何语句或表达式的执行异常完成，则按如下方式处理：

- 如果表达式的执行异常完成，则 switch 表达式以相同的原因异常完成。
- 如果语句的执行因带有值 V 的 `yield` 而异常完成，则 switch 表达式正常完成，且 switch 表达式的值为 V。
- 如果语句的执行因带有值的 `yield` 以外的任何原因异常完成，则 switch 表达式以相同的原因异常完成。

## 15.29 常数表达式

常量表达式：表达式

常量表达式是一个表示原始类型或 String 的表达式，它不会异常完成且仅由以下内容组成：

- 原始类型字面量和 String 字面量（3.10）
- 强制转换到原始类型和强制转换到 String（§15.16）
- 一元运算符 `+`、`~` 和 `!`
- 乘法运算符 `*`、`/`、`%`（15.17）
- 加法运算符 `+` 和 `-`（15.18）
- 位移运算符 `<<`、`>>`、`>>>`（15.19）
- 关系运算符 `<`、`<=`、`>`、`>=`（但不包括 `instanceof`）（§15.20）
- 相等性运算符 `==` 和 `!=`（§15.21）
- 位运算和逻辑运算符 `&`、`|`、`^`（§15.22）
- 逻辑与运算符 `&&` 和逻辑或运算符 `||`（§15.23, 15.24）
- 三元运算符 `? :`（§15.25）
- 括号表达式（§15.8），其包含的表达式为常量表达式。
- 引用常量变量的简单名（6.5）。
- 形式为 `TypeName . Identifier` 的限定名（6.5.2），引用常量变量（12.4）。

String 的常量表达式总是会被池化（interned），使用 `String.intern()` 方法。

常量表达式始终被视为严格计算（§15.4），即使它出现在不被视为严格计算的上下文中。常量表达式用于 switch 语句和 switch 表达式的标签（14.11,15.28），并在类或接口初始化（12.4.2）中具有特殊意义。

### 示例 15.29-1. 常数表达式

```
true
(short)(1*2*3*4*5*6)
Integer.MAX_VALUE / 2
2.0 * Math.PI
"The integer " + Long.MAX_VALUE + " is mighty big."
```

# 16 章 确定赋值

每个局部变量（14.4）和每个 `final` 字段（4.12.4, §8.3.1.2）在访问其值时必须有一个确定的赋值。

访问变量简单名（或对于字段，其通过 `this` 限定的简单名）出现在表达式中，除非作为简单赋值运算符 `=`（§15.26.1）的左操作数。

对于局部变量或 `final` 字段 `x` 的每次访问，在访问之前必须已确定赋值，否则将产生错误。

同样，每个 `final` 变量最多被赋值一次；在对其赋值时，它必须是确定未赋值的。

当且仅当变量简单名（或对于字段，其通过 `this` 限定的简单名）出现在赋值运算符的左侧时，定义为赋值。

对于每个 `final` 变量的赋值，在赋值之前必须是确定未赋值的，否则将产生错误。

本章的剩余部分将详细解释“在之前确定赋值”和“在之前确定未赋值”这两个词的含义。

确定赋值的理念是：局部变量或 `final` 字段的赋值必须在所有可能的执行路径上发生。同样，确定未赋值的理念是：在赋值任何可能的执行路径上都不允许发生其他赋值。

该分析考虑了语句和表达式的结构；它还对运算符 `!`、`&&`、`||` 和 `? :` 以及布尔值常量表达式提供了特殊处理。

除了对条件布尔运算符 `&&`、`||` 和 `? :` 以及布尔值常量表达式进行特殊处理外，流分析不考虑表达式的值。

## 示例 16-1. 确定性赋值考虑语句和表达式的结构

Java 编译器识别出 `k` 在代码中被访问（作为方法调用的参数）之前已经确定赋值：

```
{
  int k;
  if (v > 0 && (k = System.in.read()) >= 0)
    System.out.println(k);
}
```

因为该访问仅发生在表达式的值：

```
v > 0 && (k = System.in.read()) >= 0
```

为真时，且只有在对 `k` 的赋值被执行（更准确地说，求值）时，该值才为真。

同样，Java 编译器会识别代码中的：

```
{
  int k;
  while (true) {
    k = n;
    if (k > 5) break;
    n = 6;
  }
  System.out.println(k);
}
```

变量 `k` 被 `while` 语句确定赋值了，因为表达式 `true` 永远不会为假值，所以只有 `break` 语句会导致 `while` 语句正常完成，而 `k` 在 `break` 语句之前已经确定赋值。

另一方面，以下代码：

```
{
  int k;
  while (n < 4) {
    k = n;
    if (k >= 5) break;
    n = 6;
  }
  System.out.println(k); /* 在此语句之前 k 未“确定赋值” */
}
```

必须被 Java 编译器拒绝，因为从确定性赋值的规则来说，在这种情况下 `while` 语句无法保证执行其体。

## 示例 16-2. 确定性赋值不考虑表达式的值

Java 编译器应对代码产生编译错误：

```
{
  int k;
  int n = 5;
  if (n > 2)
    k = 3;
  System.out.println(k); /* 在此语句之前 k 未“确定赋值” */
}
```

尽管 `n` 的值在编译时是知的，且原则上可以在编译时知道对 `k` 的赋值将始终执行（正确求值）。但 Java 编译器必须按照本节列出的规则运行。规则只识别常量表达式；在本示例中，表达式 `n > 2` 不是 §15.29 中定义的常量表达式。

另一个例子，Java 编译器会接受以下代码：

```
void flow(boolean flag) {
  int k;
  if (flag)
    k = 3;
  else
    k = 4;
  System.out.println(k);
}
```

就 `k` 的确定性赋值而言，这是可以的，因为本节列出的规则允许判断无论 `flag` 为真为假，`k` 都有值。但规则不接受以下变化：

```
void flow(boolean flag) {
  int k;
  if (flag)
    k = 3;
  if (!flag)
    k = 4;
  System.out.println(k); /* 在此语句之前 k 未“确定赋值” */
}
```

因此，编译此程序会导致产生编译错误。

- 变量在表达式为真执行后是否确定赋值；
- 变量在表达式为真执行后是否确定未赋值；
- 变量在表达式为假执行后是否确定赋值；
- 变量在表达式为假执行后是否确定未赋值。

在这里，*true* 和 *false* 指代表达式的值。

例如，局部变量 `k` 在表达式求值后被确定赋了值：

```
a > 4 && (k=m) > 5
```



当表达式为 `true` 时是，但当表达式为 `false` 时不是（因为如果 `a` 为假，则对 `k` 的赋值不一定执行（更准确地说，求值））。

短语“v 在 `x` 之后确定赋值”（其中 `v` 是局部变量，`x` 是语句或表达式）意味着“如果 `x` 正常完成，则 `v` 在 `x` 之后确定赋值”。如果 `x` 异常完成，赋值可能没有发生，此处说明的规则考虑了这一点。

该定义的一个奇特结果是，“v 在 `break` 之后确定赋值”始终为真！因为 `break` 语句永远不会正常完成，所以如果 `break` 语句正常完成，则 `v` 已赋值的命题是空为真的。

语句“v 在 `x` 之后确定未赋值”（其中 `v` 是变量，`x` 是语句或表达式）意味着“如果 `x` 正常完成，则 `v` 在 `x` 之后确定未赋值”。

该定义的另一个奇特结果是，“v 在 `break` 之后确定未赋值”是空为真的，由于 `break` 语句永远不会正常完成，如果 `break` 语句正常完成，则 `v` 未被赋值的命题为真。（就此而言，如果 `break` 语句正常完成，月亮是绿奶酪做的也是空为真的。）

总而言，在执行完语句或表达式后，变量 `v` 有四种可能性：

- `v` 是确定赋值且未赋值。
- `v` 是确定未赋值且未赋值。
- `v` 不是确定赋值且未赋值。
- `v` 不是确定未赋值且已赋值。

# 确定赋值与表达式

- $v$ 在 $a && b$ 之后是[未]赋值的，当且仅当当 $a$ 为真时，$v$ 在 $a && b$ 之后是[未]赋值的，且当 $a$ 为假时，$v$ 在 $a && b$ 之后是[未]赋值的。

## 16.1.3 条件或运算符 ||

- $v$ 在 $a || b$ ($15.24) 之后是[未]赋值的，当 $a$ 为真时，$v$ 在 $a$ 之后是[未]赋值的，且当 $b$ 为真时，$v$ 在 $b$ 之后是[未]赋值的。
- $v$ 在 $a || b$ 当 $a$ 为假时，$v$ 在 $b$ 之后是[未]赋值的。
- $v$ 在 $a$ 之前是[未]赋值的，当且仅当 $v$ 在 $a || b$ 之前是[未]赋值的。
- $v$ 在 $b$ 之前是[未]赋值的，当且仅当 $a$ 为假时，$v$ 在 $a$ 之后是[未]赋值的。
- $v$ 在 $a || b$ 之后是[未]赋值的，当 $a$ 为真时，$v$ 在 $a || b$ 之后是[未]赋值的，且当 $a$ 为假时，$v$ 在 $a || b$ 之后是[未]赋值的。

## 16.1.4 逻辑非运算符 !

- $v$ 在 $!a$ ($15.15.6) 之后是[未]赋值的，当 $a$ 为真时，$v$ 在 $a$ 之后是[未]赋值的。
- $v$ 在 $!a$ 当 $a$ 为假时，$v$ 在 $a$ 之后是[未]赋值的。
- $v$ 在 $a$ 之前是[未]赋值的，当且仅当 $v$ 在 $!a$ 之前是[未]赋值的。
- $v$ 在 $!a$ 之后是[未]赋值的，当 $a$ 为真时，$v$ 在 $!a$ 之后是[未]赋值的，且当 $a$ 为假时，$v$ 在 $!a$ 之后是[未]赋值的。

这等于说 $v$ 在 $!a$ 之后是[未]赋值的，当且仅当 $v$ 在 $a$ 之后是[未]赋值的。

## 16.1.5 条件运算符 ? :

假设 $b$ 和 $c$ 是布尔值表达式。

- $v$ 在 $a ? b : c$ ($15.25) 之后是[未]赋值的，当 $a$ 为真时，$v$ 在 $b$ 之后是[未]赋值的，且当 $c$ 为真时，$v$ 在 $c$ 之后是[未]赋值的。
- $v$ 在 $a ? b : c$ 当 $a$ 为假时，$v$ 在 $b$ 之后是[未]赋值的，且当 $c$ 为假时，$v$ 在 $c$ 之后是[未]赋值的。
- $v$ 在 $a$ 之前是[未]赋值的，当且仅当 $v$ 在 $a ? b : c$ 之前是[未]赋值的。
- $v$ 在 $b$ 之前是[未]赋值的，当且仅当 $a$ 为真时，$v$ 在 $a$ 之后是[未]赋值的。
- $v$ 在 $c$ 之前是[未]赋值的，当且仅当 $a$ 为假时，$v$ 在 $a$ 之后是[未]赋值的。

# 确定赋值

确定赋值与表达式 16.1

- 如果 $v$ 在 $a ? b : c$ 为真时在 $a ? b : c$ 之后是[未]赋值的，且为假时在 $a ? b : c$ 之后是[未]赋值的，那么 $v$ 在 $a ? b : c$ 之后就是[未]赋值的。

假设 $b$ 和 $c$ 是不是布尔值的表达式。

- 如果 $v$ 在 $b$ 之后是[未]赋值的，且 $v$ 在 $c$ 之后是[未]赋值的，那么 $v$ 在 $a ? b : c$ 之后就是[未]赋值的。
- $v$ 在 $a$ 之前是[未]赋值的，当且仅当 $v$ 在 $a ? b : c$ 之前是[未]赋值的。
- $v$ 在 $b$ 之前是[未]赋值的，当且仅当 $a$ 为真时，$v$ 在 $a$ 之后是[未]赋值的。
- $v$ 在 $c$ 之前是[未]赋值的，当且仅当 $a$ 为假时，$v$ 在 $a$ 之后是[未]赋值的。

## 16.1.6 switch 表达式

假设一个 $switch$ 表达式 ($\S15.28$) 具有结果表达式 $e_j, ..., e_n$，它们均为布尔值。

只有当该 $switch$ 表达式的 switch 块由标记语句组 ($\S14.11.1$) 组成时，以下规则才适用：

- 如果 switch 块中每个可能退出 $switch$ 表达式的带有表达式 $e$ ($\S14.21$) 的 `yield` 语句在为真时，$v$ 在 $e$ 之后都是确定赋值的，那么 $v$ 在 $switch$ 表达式之后（为真时）是确定赋值的。
- 如果 switch 块中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句在为假时，$v$ 在 $e$ 之后都是确定赋值的，那么 $v$ 在 $switch$ 表达式之后（为假时）是确定赋值的。
- 如果 switch 块中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句在为真时，$v$ 在 `yield` 语句之前都是确定未赋值的，且 $v$ 在 $e$ 之后都是确定未赋值的，那么 $v$ 在 $switch$ 表达式之后（为真时）是确定未赋值的。
- 如果 switch 块中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句在为假时，$v$ 在 `yield` 语句之前都是确定未赋值的，且 $v$ 在 $e$ 之后都是确定未赋值的，那么 $v$ 在 $switch$ 表达式之后（为假时）是确定未赋值的。
- $v$ 在选择器表达式之前是[未]赋值的，当且仅当 $v$ 在 $switch$ 表达式之前是[未]赋值的。
- $v$ 在 switch 块中第一个 switch 标记语句组的第一个语句之前是[未]赋值的，当且仅当 $v$ 在选择器表达式之后是[未]赋值的。
- $v$ 在 switch 块中任何其他 switch 标记语句组的第一个语句之前是[未]赋值的，当且仅当 $v$ 在选择器表达式之后是[未]赋值的，$v$ 在前一个语句之后是[未]赋值的。

只有当 switch 表达式由 switch 规则 ($\S14.11$) 组成时，以下规则才适用：

- $v$ 在 switch 表达式之后（为真时）是确定赋值的，当且仅当对于每个 switch 规则，以下任之一成立：
    - 它引入了 switch 规则 $e$，且在为真时，$v$ 在 $e$ 之后是确定赋值的。
    - 它引入了 switch 块 $B$，且对于 $B$ 中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句，为真时 $v$ 在 $e$ 之后都是确定赋值的。
    - 它引入了 switch throw 语句。
- $v$ 在 switch 表达式之后（为假时）是确定赋值的，当且仅当对于每个 switch 规则，以下任之一成立：
    - 它引入了 switch 规则 $e$，且在为假时，$v$ 在 $e$ 之后是确定赋值的。
    - 它引入了 switch 块 $B$，且对于 $B$ 中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句，为假时 $v$ 在 $e$ 之后都是确定赋值的。
    - 它引入了 switch throw 语句。
- $v$ 在 switch 表达式之后（为真时）是确定未赋值的，当且仅当对于每个 switch 规则，以下任之一成立：
    - 它引入了 switch 规则 $e$，且在为真时，$v$ 在 $e$ 之后是确定未赋值的。
    - 它引入了 switch 块 $B$，且对于 $B$ 中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句，为真时 $v$ 在 `yield` 语句之前都是确定未赋值的，且 $v$ 在 $e$ 之后都是确定未赋值的。
    - 它引入了 switch throw 语句。

## 16.1.7 其他布尔类型表达式

假设 $e$ 是布尔类型的表达式，但不是布尔表达式、逻辑非表达式 $!a$、逻辑与表达式 $a && b$、逻辑或表达式 $a || b$ 或条件表达式 $a ? b : c$。

- $e$ 为真时，$v$ 在 $e$ 之后是[未]赋值的。
- $e$ 为为假时，$v$ 在 $e$ 之后是[未]赋值的。

## 16.1.8 赋值表达式

考虑表达式 $a = b, a += b, a -= b, a *= b, a /= b, a %= b, a <<= b, a >>= b, a &= b, a |= b$ 或 $a ^= b$ ($\S15.26$)。

- $v$ 在赋值表达式之后是确定赋值的，当且仅当：
    - $a$ 是 $V$，
    - $v$ 在 $b$ 之后是确定赋值的。
- $v$ 在赋值表达式之后是未赋值的，当且仅当 $a$ 不是 $V$ 且 $v$ 在赋值之后是未赋值的。
- $v$ 在 $a$ 之前是[未]赋值的，当且仅当 $v$ 在赋值表达式之前是[未]赋值的。
- $v$ 在 $b$ 之前是[未]赋值的，当且仅当 $v$ 在 $a$ 之后是[未]赋值的。

注意，如果 $a$ 是 $V$ 且在复合表达式（如 $a *= b$）之后未赋值，则将必然发生编译错误。上述确定赋值的第一条规则对于复合赋值包含了“$a$ 是 $V$”这一子句，以便 $V$ 在代码后续位置被认为已赋值；“是 $V$”这一子句不影响程序是否可或会导致编译错误的二进制决策，但它会影响代码中有多少点被视为错误，在实践中它可以提高错误报告的质量。类似的备注适用于上述确定赋值第一条规则中包含连词“$a$ 不是 $V$”。

## 16.1.9 运算符 ++ 和 --

- $v$ 在 `++a` ($\S15.15.1), `--a` ($\S15.15.2), `a++` ($\S15.14.2) 或 `a--` ($\S15.14.3) 之后是确定赋值的，当且仅当 $a$ 是 $V$ 或 $v$ 在操作数表达式之后是确定赋值的。
- $v$ 在 `++a`, `--a`, `a++` 或 `a--` 之后是未赋值的，当且仅当 $a$ 不是 $V$ 且 $v$ 在之后是未赋值的。
- $v$ 在 $a$ 之前是[未]赋值的，当且仅当 $v$ 在 `++a`, `--a`, `a++` 或 `a--` 之前是[未]赋值的。

# 确定赋值

- $v$ 在 switch 表达式之后（为假时）是确定未赋值的，当且仅当对于每个 switch 规则，以下任之一成立：
    - 它引入了 switch 规则 $e$，且在为假时，$v$ 在 $e$ 之后是确定未赋值的。
    - 它引入了 switch 块 $B$，且对于 $B$ 中每个可能退出 $switch$ 表达式的带有表达式 $e$ 的 `yield` 语句，$v$ 在 `yield` 语句之前都是确定未赋值的，且在为假时，$v$ 在 $e$ 之后都是确定未赋值的。
    - 它引入了 switch throw 语句。
- $v$ 在 switch 块中任何 switch 规则或规则语句之前是[未]赋值的，当且仅当 $v$ 在选择器表达式之后是[未]赋值的。
- 假设一个 $switch$ 表达式具有结果表达式 $e_1, ..., e_n$，它们都不是布尔值。
- $v$ 在 switch 表达式之后是[未]赋值的，当且仅当所有条件均成立：
    - $v$ 在每个可能退出 switch 表达式的 `yield` 语句之前都是[未]赋值的。
    - 对于 switch 块中的每个 switch 规则，$v$ 在该规则引入的 switch 规则表达式、switch 块或规则 throw 语句之后都是[未]赋值的。
- $v$ 在 switch 表达式的选择器表达式之前是[未]赋值的，当且仅当 $v$ 在 switch 表达式之前是[未]赋值的。
- $v$ 在 switch 块中某个 switch 标记语句组的第一个语句之前是[未]赋值的，当且仅当以下两个条件都成立：
    - $v$ 在 switch 表达式的选择器表达式之后是[未]赋值的。
    - 如果该 switch 标记语句组不是 switch 块中的第一个，则 $v$ 在前一个 switch 标记语句组的最后一个语句之后是[未]赋值的。
- $v$ 在 switch 块中并非 switch 标记语句组第一个语句的语句之前是[未]赋值的，当且仅当 $v$ 在前一个语句之后是[未]赋值的。

# 确定赋值 (DEFINITE ASSIGNMENT)

## 确定赋值与表达式

### 16.1.10 其他表达式

如果一个表达式不是布尔常量表达式 --，且不是前增表达式 `++a`、前减表达式 `--a`、后增表达式 `a++`、后减表达式 `a--`、逻辑完备表达式 `!a`、条件与表达式 `a && b`、条件或表达式 `a || b`、三元表达式 `a ? b : c`、表达式，或 lambda 表达式，

- 如果该表达式没有子表达式，则 v 在表达式之前是[未]赋值的。

此情况适用于字面量、变量名、`this`（包括限定的和未限定的）、无参数的未限定类创建表达式、包含不含表达式的初始化器的数组创建表达式、超类字段访问表达式、无参数的未限定和类型限定的方法调用、无参数的方法调用，以及超类方法引用表达式和类型限定方法引用表达式。

- 如果该表达式有子表达式，则 v 在其直接子表达式之后是[未]赋值的。

在“变量 v 在方法调用后可以被确定赋值”这一断言背后，存在着微妙的推理。就其本身、表面值和限定性而言，这种断言并不总是成立，因为调用的方法可能会执行赋值。但必须记住，对于 Java 编程语言而言，确定赋值的概念仅适用于空 final（blank final）变量。如果 v 是一个空局部变量，那么只有声明 v 的该方法可以对 v 执行赋值。如果包含 v 声明的类的构造函数或初始化器可以对 v 执行赋值，则没有方法可以对 v 执行赋值。最后，显式构造函数调用 (§8.7.1) 被特殊处理 (§16.9)；尽管它们在语法上与包含方法调用的表达式语句相似，但它们不是表达式语句，因此本节的规则不适用于显式构造函数调用。

如果表达式是 lambda 表达式，则适用以下规则：

- 如果 v 在表达式之前是[未]赋值的，则 v 在表达式之后是[未]赋值的。
- 如果 v 在 lambda 表达式之前是确定赋值的，则 v 在 lambda 表达式 (§15.27.2) 或块之前是确定赋值的。

没有规则允许 v 在 lambda 体之前被确定为未赋值。在 lambda 体之前已确定赋值的变量在之后可能会变为未赋值，因此我们不能得出在执行体时该变量无法赋值的结论。

对于表达式 x 的任何直接子表达式 y（其中 x 不是 lambda 表达式），如果满足任一条件，则 v 在 y 之前是[未]赋值的：

- y 是 x 最左侧的直接子表达式，且 v 在 x 之前是[未]赋值的。
- y 是二元运算符右操作数，且 v 在左操作数之后是[未]赋值的。
- x 是数组访问，y 是括号内的子表达式，且 v 在括号之前的子表达式之后是[未]赋值的。
- x 是主方法调用表达式，y 是方法调用表达式中的第一个参数表达式，且 v 在计算目标的主表达式之后是[未]赋值的。
- x 是方法调用表达式或类实例创建表达式；y 是参数表达式但不是第一个；且 v 在 y 左侧的参数表达式之后是[未]赋值的。
- x 是限定的类实例创建表达式，y 是类实例创建表达式中的第一个参数表达式，且 v 在计算限定的主表达式之后是[未]赋值的。
- x 是数组创建表达式；y 是维度表达式但不是第一个；且 v 在 y 左侧的维度表达式之后是[未]赋值的。
- x 是通过数组初始化器初始化的数组创建表达式；y 是 x 左侧的维度表达式；且 v 在维度表达式之后是[未]赋值的。

## 16.2 确定赋值与语句

### 16.2.1 空语句

### 16.2.2 块

- 空 `final` 成员字段 `v` 在 `v` 范围内任何方法的体体块 (§14.2) 之前是确定赋值的（并且不是确定未赋值的），并且在 `v` 范围内声明的任何类的声明之前同样是确定赋值的。
- 局部变量 `v` 在声明 `v` 的构造函数、方法、实例初始化器或静态初始化器的体块之前是确定未赋值的（并且不是确定赋值的）。
- 设 `c` 是在 `v` 范围内声明的类。那么 `v` 在 `c` 中声明的任何构造函数、方法、实例初始化器或静态初始化器的体块之前是确定赋值的；`v` 在 `c` 的声明之前是确定赋值的。

请注意，没有任何规则允许我们得出结论，`v` 在 `c` 中声明的任何构造函数、方法、实例初始化器或静态初始化器的体块之前是确定未赋值的。我们可以非正式地得出结论，`v` 在这些体块之前不是确定未赋值的，但没有必要显式规定这样的规则。

- `v` 在空块之后是确定未赋值的，当且仅当 `v` 在块之前是[未]赋值的。
- `v` 在非空块之后是确定未赋值的，当且仅当 `v` 在最后一个语句之后是[未]赋值的。
- `v` 在块的第一条语句之前是[未]赋值的，当且仅当 `v` 在块之前是[未]赋值的。
- `v` 在块中任何其他语句 `s` 之前是[未]赋值的，当且仅当 `v` 在 `s` 之前的语句之后是[未]赋值的。

我们说 `v` 在块 `B` 中到处都是确定未赋值的，当且仅当：

- `v` 在 `B` 之后是确定未赋值的。
- `v` 在每个表达式 `V=e, V+=e, V-=e, V*=e, V/=e, V%=e, V<<=e, V>>=e, V&=e, V|=e, V^=e` 之后都是确定赋值的。
- `v` 在每个表达式 `V++`, `--V` 或 `++` 之前都是确定赋值的。

这些条件是不直观的，需要一些解释。考虑简单的赋值 `V=e`。如果 `V` 在 `e` 之后是确定赋值的，那么：

- 赋值发生了，且 `V` 是空赋值的。在这种情况下，赋值实际上不会发生，我们可以假设 `V` 没有在被赋值。
- `V` 已经由之前的表达式赋值了。在这种情况下，当前的赋值会导致编译时错误。

因此，我们可以得出结论：如果满足条件的程序没有错误，那么 `B` 中的任何对 `V` 的赋值都不会发生。

### 16.2.3 局部类声明语句

- `v` 在局部类声明语句简体14.3)之后是[未]赋值的，当且仅当 `v` 在该声明语句之前是[未]赋值的。

### 16.2.4 局部变量声明语句

- `v` 在不含初始化器的局部变量声明语句简体14.4)之后是[未]赋值的，当且仅当 `v` 在声明语句之前是[未]赋值的。
- `v` 在包含至少一个初始化器的局部变量声明语句之后是确定赋值的，当且仅当 `v` 在最后一个变量初始化器之后是确定赋值的，或者声明中的最后一个初始化器不在声明 `v` 的声明符中。
- `v` 在包含至少一个初始化器的局部变量声明语句之后是确定未赋值的，当且仅当 `v` 在最后一个变量初始化器之后是确定未赋值的，且声明中的最后一个初始化器不在声明 `v` 的声明符中。
- `v` 在局部变量声明语句的第一个初始化器之前是[未]赋值的，当且仅当 `v` 在声明语句之前是[未]赋值的。
- `v` 在局部变量声明语句中除第一个以外的任何初始化器 `e` 之前是确定赋值的，意味着 `v` 在 `e` 左侧的初始化器之后是确定赋值的，或者 `e` 左侧的初始化表达式在声明 `v` 的声明符中。
- `v` 在局部变量声明语句中除第一个以外的任何初始化器 `e` 之前是确定未赋值的，意味着 `v` 在 `e` 左侧的初始化器之后是确定未赋值的，且 `e` 左侧的初始化表达式不在声明 `v` 的声明符中。

### 16.2.5 标记语句

- `v` 在标记语句 `L : s` (简体14.7) 之后是[未]赋值的，当且仅当 `v` 在 `s` 之后是[未]赋值的，且 `v` 在每个可能退出标记语句 `L : s` 的 `break` 语句之前都是[未]赋值的。
- `v` 在 `s` 之前是[未]赋值的，当且仅当 `v` 在 `L : s` 之前是[未]赋值的。

## 16.2.6 表达式语句

- `v` 在表达式语句 `e` (§14.8) 之后[未]赋值，当且仅当它在 `e` 之后为[未]赋值。
- `v` 在 `e` 之前[未]赋值，当且仅当它在 `e` 之前为[未]赋值。

## 16.2.7 if 语句

以下规则适用于语句 `if (e) S` (§14.9.1)：

- `v` 在 `if (e) S` 之后[未]赋值，当且仅当 `v` 在 `S` 之后为[未]赋值，且当 `e` 为假时 `v` 在之后为[未]赋值。
- `v` 在 `e` 之前[未]赋值，当且仅当 `v` 在 `if (e) S` 之前为[未]赋值。
- `v` 在 `S` 之前[未]赋值，当且仅当 `e` 为真时 `v` 在之后为[未]赋值。

以下规则适用于语句 `if (e) S else T` (§14.9.2)：

- `v` 在 `if (e) S else T` 之后[未]赋值，当且仅当 `v` 在 `S` 之后为[未]赋值，且 `v` 在 `T` 之后为[未]赋值。
- `v` 在 `e` 之前[未]赋值，当且仅当 `v` 在 `if (e) S else T` 之前为[未]赋值。
- `v` 在 `S` 之前[未]赋值，当且仅当 `e` 为真时 `v` 在之后为[未]赋值。
- `v` 在 `T` 之前[未]赋值，当且仅当 `e` 为假时 `v` 在之后为[未]赋值。

## 16.2.8 assert 语句

以下规则同时适用于语句 `assert e1` 和语句 `assert e1 : e2` (§14.10)：

- `v` 在 `e1` 之前[未]赋值，当且仅当 `v` 在 `assert` 语句之前为[未]赋值。
- `v` 在 `assert` 语句之后确定已赋值，当且仅当 `v` 在 `assert` 语句之前确定已赋值。
- `v` 在 `assert` 语句之后确定为未赋值，当且仅当 `e1` 为真时 `v` 在之后确定为未赋值。

以下规则适用于语句 `assert e1 : e2`：

- `v` 在 `e2` 之前[未]赋值，当且仅当 `e1` 为假时 `v` 在之后为[未]赋值。

## 16.2.9 switch 语句

- `V` 在 switch 语句（§14.11）之后[未]赋值，当且仅当以下所有条件都成立：
  - `V` 在每一个可能退出 switch 语句的 `break` 语句（§14.15）之前为[未]赋值。
  - 对于 switch 块中的每个 switch 规则（§14.11.1），`V` 在该 switch 规则引入的 switch 规则表达式、switch 规则块或 switch 规则 throw 语句之后为[未]赋值。
  - 如果 switch 块中存在带标签的语句组，`V` 在最后一个带标签语句组的最后一个块语句之后为[未]赋值。
  - 如果 switch 块中没有 default 标签，或者 switch 以 switch 标签后跟的 `}` 分隔符结束，则 `V` 在选择器表达式之后为[未]赋值。
- `V` 在 switch 语句的选择器表达式之前[未]赋值，当且仅当 `V` 在 switch 语句之前为[未]赋值。
- `V` 在 switch 块中由 switch 规则引入的 switch 规则表达式、switch 规则块或 switch throw 语句之前[未]赋值，当且仅当 `V` 在 switch 语句的选择器表达式之后为[未]赋值。
- `V` 在 switch 块中 switch 标签语句组的第一个块语句之前[未]赋值，当且仅当以下条件都成立：
  - `V` 在 switch 语句的选择器表达式之后为[未]赋值。
  - 如果 switch 标签语句组不是 switch 块中的第一个，则 `V` 在上一个 switch 标签语句组的最后一个块语句之后为[未]赋值。
- `V` 在 switch 块中不是 switch 标签语句组第一个的块语句之前[未]赋值，当且仅当 `V` 在一个块语句之后为[未]赋值。

## 16.2.10 while 语句

- `V` 在 `while (e) s`（§14.12）之后[未]赋值，当且仅当 `e` 为假时 `V` 在之后为[未]赋值，且 `V` 在每一个以 while 语句为目标的 `break` 语句之前为[未]赋值。
- `v` 在 `e` 之前确定已赋值，当且仅当 `V` 在 while 语句之前确定已赋值。
- `v` 在 `e` 之前确定为未赋值，当且仅当以下条件都成立：
  - `V` 在 while 语句之前确定为未赋值。
  - 假设 `v` 在 `e` 之前确定为未赋值，则 `V` 在 `S` 之后确定为未赋值。
  - 假设 `v` 在 `e` 之前确定为未赋值，则 `V` 在每一个以 while 语句为目标的 `continue` 语句之前确定为未赋值。
- `v` 在 `s` 之前[未]赋值，当且仅当 `e` 为真时 `v` 在之后为[未]赋值。

## 16.2.11 do 语句

- `v` 在 `do S while (e)` 之后[未]赋值（§14.13），当且仅当 `e` 为假时 `v` 在之后为[未]赋值，且 `V` 在每一个以 do 语句为目标的 `break` 语句之前为[未]赋值。
- `v` 在 `s` 之前确定已赋值，当且仅当 `v` 在 do 语句之前确定已赋值。
- `v` 在 `s` 之前确定为未赋值，当且仅当以下条件都成立：
  - `V` 在 do 语句之前确定为未赋值。
  - 假设 `v` 在 `s` 之前确定为未赋值，则 `e` 为真时 `V` 在之后确定为未赋值。
- `v` 在 `e` 之前[未]赋值，当且仅当 `v` 在 `s` 之后为[未]赋值，且 `V` 在每一个以 do 语句为目标的 `continue` 语句之前为[未]赋值。

## 16.2.12 for 语句

这里的规则涵盖基础 for 语句（§14.14.1）。增强 for 语句（§14.14.2）由基础语句定义，因此未提供特殊规则。

- `v` 在 for 语句之后[未]赋值，当且仅当以下任一条件成立：
  - 不存在条件表达式，或者当条件表达式为假时 `v` 在条件表达式之后为[未]赋值。
  - `v` 在每一个以 for 语句为目标的 `break` 语句之前为[未]赋值。
- `v` 在 for 语句初始化部分之前[未]赋值，当且仅当 `v` 在 for 语句之前为[未]赋值。
- `v` 在 for 语句条件部分之前确定已赋值，当且仅当 `v` 在 for 语句初始化部分之后确定已赋值。
- `v` 在 for 语句条件部分之前确定为未赋值，当且仅当以下条件都成立：
  - `V` 在 for 语句初始化部分之后确定为未赋值。
  - 假设 `v` 在条件部分之前确定为未赋值，则 `e` 为真时 `V` 在之后确定为未赋值。
- `v` 在包含的语句之前[未]赋值，当且仅当以下任一条件成立：
  - 存在条件表达式，且当表达式为真时 `v` 在条件表达式之后为[未]赋值。
  - 不存在条件表达式，且 `v` 在 for 语句条件部分之前为[未]赋值。
- `v` 在 for 语句增量部分之前[未]赋值，当且仅当 `v` 在包含的语句之后为[未]赋值，且 `v` 在每一个以 for 语句为目标的 `continue` 语句之前为[未]赋值。

### 16.2.12.1 for 语句的初始化部分

- 如果 for 语句的初始化部分是局部变量声明，应用 §16.2.4 的规则。
- 否则，如果初始化部分为空，则 `v` 在初始化部分之前为[未]赋值，则 `v` 在初始化部分之后为[未]赋值。
- 否则，应用三个规则：
  - `v` 在初始化部分之后[未]赋值，当且仅当 `v` 在初始化部分的最后一个语句之后为[未]赋值。
  - `v` 在初始化部分的第一个语句之前[未]赋值，当且仅当 `v` 在初始化部分之前为[未]赋值。
  - `v` 在初始化部分除第一个以外的表达式语句 `s` 之前[未]赋值，当且仅当 `v` 在 `s` 之前的语句之后为[未]赋值。

### 16.2.12.2 for 的增量部分

- 如果 for 语句的增量部分为空，则 `v` 在增量部分之前为[未]赋值，则 `v` 在增量部分之后为[未]赋值。
- 否则，应用三个规则：
  - `v` 在增量部分之后[未]赋值，当且仅当 `v` 在增量部分的最后一个语句之后为[未]赋值。
  - `v` 在增量部分的第一个语句之前[未]赋值，当且仅当 `v` 在增量部分之前为[未]赋值。
  - `v` 在增量部分除第一个以外的表达式语句 `s` 之前[未]赋值，当且仅当 `v` 在 `s` 之前的语句之后为[未]赋值。

## 16.2.13 break, yield, continue, return 和 throw 语句

- 根据惯例，我们认为 `v` 在任何 `break`、`yield`、`continue`、`return` 或 `throw` 语句之后均为[未]赋值（§14.15, §14.21, §14.16, §14.17, §14.18）。
- 在带有表达式 `e` 的 `yield` 语句、带有表达式 `e` 的 `return` 语句或带有表达式 `e` 的 `throw` 语句中，`v` 在语句之前[未]赋值，当且仅当 `v` 在 `yield`、`return` 或 `throw` 语句之前为[未]赋值。

> “在语句或表达式正常结束之后[未]赋值”。因为 `break`、`yield`、`continue`、`return` 或 `throw` 语句永远不会正常结束，所以它们空值满足了这一概念。

## 16.2.14 synchronized 语句

- `v` 在 `synchronized (e) s`（§14.19）之后[未]赋值，当且仅当 `v` 在 `s` 之后为[未]赋值。
- `v` 在 `e` 之前[未]赋值，当且仅当 `v` 在 `synchronized (e) S` 语句之前为[未]赋值。
- `v` 在 `s` 之前[未]赋值，当且仅当 `v` 在 `e` 之后为[未]赋值。

## 16.2.15 try 语句

这些规则适用于每一个 try 语句（§14.20），无论其是否带有 finally 块。

# 确定赋值与语句

- `v` 在 try 块之前是[未]赋值的，当且仅当 `v` 在 try 语句之前是[未]赋值的。
- `v` 在 catch 块之前是确定赋值的，当且仅当 `v` 在 try 块之前是确定赋值的。
- `v` 在 catch 块之前是确定未赋值的，当且仅当满足以下所有条件：
  - `v` 在 try 块之后是确定未赋值的。
  - `v` 在属于 try 块的每一个 `return` 语句之前都是确定未赋值的。
  - 在属于 try 块的每一个形式为 `throw e` 的语句中，`v` 在 `e` 之前都是确定未赋值的。
  - `v` 在 try 块中发生的每一个 `assert` 语句之后都是确定未赋值的。
  - `v` 在属于 try 块的每一个 `break` 语句之前都是确定未赋值的，且该 `break` 目标包含（或就是）try 语句。
  - `v` 在属于 try 块的每一个 `continue` 语句之前都是确定未赋值的，且该 `continue` 目标包含 try 语句。

如果 try 语句没有 finally 块，则此规则也适用：

- `v` 在 try 语句之后是[未]赋值的，当且仅当 `v` 在 try 块之后是[未]赋值的，且 `v` 在 try 语句中每一个 catch 块之后都是[未]赋值的。

如果 try 语句确实有 finally 块，则这些规则也适用：

- `v` 在 try 语句之后是确定赋值的，当且仅当以下至少至少一个：
  - `v` 在 try 块之后是确定赋值的，且 `v` 在 try 语句中每一个 catch 块之后都是确定赋值的。
  - `v` 在 finally 块之后是确定赋值的。
- `v` 在 try 语句之后是确定未赋值的，当且仅当 `v` 在 finally 块之后是确定未赋值的。
- `v` 在 finally 块之前是确定赋值的，当且仅当 `v` 在 try 语句之前是确定赋值的。

# 确定赋值与参数

- `V` 在 finally 块之前是确定未赋值的，当且仅当满足以下所有条件：
  - `V` 在 try 块之后是确定未赋值的。
  - `V` 在属于 try 块的每一个 `return` 语句之后都是确定未赋值的。
  - 在属于 try 块的每一个形式为 `throw e` 的语句中，`V` 在 `e` 之后都是确定未赋值的。
  - `V` 在 try 块中发生的每一个 `assert` 语句之后都是确定未赋值的。
  - `V` 在属于 try 块的每一个 `break` 语句之前都是确定未赋值的，且该 `break` 目标包含（或就是）try 语句。
  - `V` 在属于 try 块的每一个 `continue` 语句之前都是确定未赋值的，且该 `continue` 目标包含 try 语句。
  - `V` 在 try 语句的每一个 catch 块之后都是确定未赋值的。

- 方法或构造函数的正式参数 `v` (§8.4.1, §8.8.1) 在方法或构造函数体之前是确定赋值的（而且不是确定未赋值的）。
- catch 子句的异常参数 `v` (§14.20) 在 catch 子句体之前是确定赋值的（而且不是确定未赋值的）。

# 16.4 确定赋值与数组初始化器

- `v` 在空数组初始化器 (§10.6) 之后是[未]赋值的，当且仅当 `v` 在空数组初始化器之前是[未]赋值的。
- `v` 在非空数组初始化器之后是[未]赋值的，当且仅当 `v` 在数组初始化器中最后一个变量初始化器之后是[未]赋值的。
- `v` 在数组初始化器中第一个变量初始化器之前是[未]赋值的，当且仅当 `v` 在数组初始化器之前是[未]赋值的。
- 如果 `v` 在数组初始化器中 `e` 左侧的变量初始化器之后是[未]赋值的，则 `v` 在数组初始化器中任何其他变量初始化器 `e` 之前都是[未]赋值的。

# 16.5 确定赋值与常量

- 确定变量在常量之前是确定赋值还是确定未赋值的规则 (§8.9) 给出 §16.8 中。

> 这是因为常量本质上是一个静态 字段(§8.3.1.1, §8.3.1.2)，由类实例表达式(§15.9) 初始化。

- `v` 在包含 `v` 范围的常量类体声明之前是确定赋值的；`v` 在常量之前是确定赋值的。
- `v` 在包含 `v` 范围的常量类体声明之前是确定赋值的；`v` 在常量之后是确定赋值的。

常量类体内任何结构的确定赋值/未赋值状态由类的常规规定。

- `v` 在常量的第一个参数之前是[未]赋值的，当且仅当它在常量之前是[未]赋值的。
- `v` 在 `y`（常量的某个参数）之前是[未]赋值的，当且仅当 `v` 在 `y` 左侧的参数之后是[未]赋值的。

# 16.6 确定赋值与匿名类

- `v` 在包含 `v` 范围的匿名类声明(§15.9.5) 之前是确定赋值的；`v` 在匿名类创建之后是确定赋值的。

如果匿名类是由常量隐式定义的，则适用 §16.5 的规则。

# 16.7 确定赋值与成员类型

设 `c` 为一个类，且 `v` 为 `c` 的一个空 final 字段。那么：

- `v` 在任何成员类型(§8.5) 之前是确定未赋值的（而且不是确定赋值的）。
设 `c` 为一个包含 `v` 范围的类。那么：

- `v` 在 `c` 的声明之前是确定赋值的（而且不是确定未赋值的）。

# 16.8 确定赋值与静态初始化器

设 `c` 为一个包含 `v` 范围的类。那么：

- `v` 在常量(§8.9.1) 或静态初始化器(§8.3.2) 之前是确定赋值的。

> 注意，没有规则允许我们 `v` 在静态初始化器之前是确定未赋值的。我们可以非正式地得出 `v` 在任何静态初始化器之前不是未赋值的结论，但没有必要规定这样的规则。

设 `c` 为一个类，且 `v` 为 `c` 中声明的空 静态 final 字段。那么：

- `v` 在 `c` 的第一个常量、静态初始化器或静态变量初始化器之前是确定未赋值的（而且不是确定赋值的）。
- `v` 在 `c` 的除第一个之外的常量、静态初始化器或静态变量初始化器之前是[未]赋值的，当且仅当 `v` 在之前的常量、静态初始化器或静态变量初始化器之后是[未]赋值的。

设 `c` 为一个类，且 `v` 为 `c` 父类中声明的空 静态 final 字段。那么：

- `v` 在 `c` 的每一个常量之前是确定赋值的（而且不是确定未赋值的）。
- `v` 在 `c` 的静态初始化器体之前是确定赋值的（而且不是确定未赋值的）。
- `v` 在 `c` 的每一个静态变量初始化器之前是确定赋值的（而且不是确定未赋值的）。

# 16.9 确定赋值、构造函数与实例初始化器

设 `c` 为一个包含 `v` 范围的类。那么：

- `v` 在 `c` 的实例变量初始化器(§8.3.2) 之前是确定赋值的，当且仅当 `v` 在 `c` 的声明之前是确定赋值的。

> 注意，没有规则允许我们 `v` 在实例变量初始化器之前是确定未赋值的。我们可以非正式地得出 `v` 在任何实例初始化器之前不是未赋值的结论，但没有必要规定这样的规则。

设 `c` 为一个类，且 `v` 为 `c` 中声明的空 final 非静态 字段。那么：

- `v` 在 `c` 的左侧实例初始化器(§8.6) 或实例变量初始化器之前是确定未赋值的（而且不是确定赋值的）。
- `v` 在 `c` 的除第一个之外的实例初始化器或实例变量初始化器之前是[未]赋值的，当且仅当 `v` 在之前的实例初始化器或实例变量初始化器之后是[未]赋值的。

以下规则适用于类 `c` 的构造函数(§8.8.7) ：

- `v` 在备用构造函数调用(§8.8.7) 之后是确定赋值的（而且不是确定未赋值的）。
- `v` 在显式或隐式父类构造函数调用(§8.8.7) 之前是确定未赋值的（而且不是确定赋值的）。
- 如果 `c` 没有实例初始化器或实例变量初始化器，则 `v` 在显式或隐式父类构造函数调用之后不是确定赋值的（而且是确定未赋值的）。
- 如果 `c` 至少有一个实例初始化器或实例变量初始化器，则 `v` 在显式或隐式父类构造函数调用之后是[未]赋值的，当且仅当 `v` 在 `c` 的最右侧实例初始化器或实例变量初始化器之后是[未]赋值的。

设 `c` 为一个类，且 `v` 为 `c` 父类中声明的空 final 成员 字段。那么：

- `v` 在 `c` 的构造函数或实例初始化器体块之前是确定赋值的（而且不是确定未赋值的）。
- `v` 在 `c` 的每个实例变量初始化器之前都确定被赋值了（而且重要的是，它没有被确定为未赋值）。

# 第 17 章
## 线程与锁

虽然前面的章节中的大部分讨论只关注代码在一次执行一条语句或表达式时的行为（即由单个线程执行），但 Java 虚拟机可以同时支持许多执行线程。这些线程独立地执行代码，这些代码操作于存储在共享主内存中的值和对象。线程可以通过拥有多个硬件处理器、通过对单个硬件处理器进行时间分片处理，或者通过对多个硬件处理器进行时间分片处理来实现支持。

线程由 `Thread` 类表示。用户创建线程的唯一方法是创建该类的一个对象；每个线程都与这样一个对象相关联。当在相应的 `Thread` 对象上调用 `start()` 方法时，线程将启动。

线程的行为，特别是在没有正确同步的情况下，可能是令人困惑且违背直觉的。本章描述了多线程程序的语义；它包含了哪些规则，即对于由多个线程更新的共享内存，其读取操作可以看到哪些值。由于该规范与不同硬件架构的内存模型相似，这些语义被称为 Java 编程语言内存模型。如果没有产生混淆，我们将简单地这些这些规则“内存模型”。

这些语义并没有规定多线程程序应该如何执行。相反，它们描述了多线程程序允许表现的行为。任何仅产生允许行为的执行策略都是接受的执行策略。

### 17.1 同步

Java 编程语言提供了多种线程间的通信机制。这些方法中最基础的是同步，它是使用监视器（monitors）实现的。Java 中的每个对象都与一个监视器相关，线程可以锁定或解锁。一次只有一个线程可以持有监视器的锁。任何尝试锁定该锁的其他线程都会被阻塞，直到它们获取到该监视器的锁。线程可以多次锁定特定的监视器；每次解锁都会撤销一次锁定操作的效果。

`synchronized` 语句 (§14.19) 指向对象引用；然后它尝试对该对象的监视器执行锁定操作，在锁定操作成功完成之前不会继续执行。执行锁定操作后，将执行 `synchronized` 语句的主体。如果主体的执行完成（无论是正常还是异常），都会自动对该监视器执行解锁操作。

`synchronized` 方法 (§8.4.3.6) 在被调用时会自动执行锁定操作；在锁定操作成功完成之前不会执行其主体。如果该方法是实例方法，它将锁定与调用该方法的实例相关的监视器（即在执行期间将被称为 `this` 的对象）。如果该方法是静态的，它将锁定与定义该方法的类的 `Class` 对象相关的监视器。如果方法主体的执行完成（无论是正常还是异常），都会自动对该监视器执行解锁操作。

Java 编程语言既不防止也不要求检测死锁条件。对于线程持有（直接或间接持有）多个对象锁的程序，应该使用传统的避免死锁技术，在必要时创建不会产生死锁的高级锁原语。

其他机制，如 `volatile` 变量的读写以及 `java.util.concurrent` 包中类的使用，提供了同步的替代方法。

### 17.2 等待集与通知

每个对象除了有一个关联的监视器外，还有一个关联的等待集（wait set）。等待集是线程的集合。

当对象首次创建时，其等待集是空的。将线程添加到等待集和从等待集中移除线程的基本操作是原子的。等待集完全由 `Object.wait`、`Object.notify` 和 `Object.notifyAll()` 方法进行操作。

等待集的操作还会受到线程中断状态以及 `Thread` 类中处理中断的方法的影响。此外，`Thread` 类用于睡眠和连接其他线程的方法具有源自等待和通知操作的属性。

#### 17.2.1 等待

等待动作发生在调用 `wait()`，或定时形式的 `wait(long milliseconds)` 和 `wait(long milliseconds, int nanoseconds)` 时。

> 参数为零的 `wait(long milliseconds)` 调用或带有两个零参数的 `wait(long milliseconds, int nanoseconds)` 调用，等同于调用 `wait()`。

如果线程从等待中返回时没有抛出 `InterruptedException`，则该线程从等待中正常返回。

假设线程 `t` 是在对象 `m` 上执行 `wait` 方法的线程，令 `n` 为 `t` 在 `m` 上执行且未与解锁操作匹配的锁定操作次数。发生以下操作之一：

- 如果 `n` 为 0（即线程 `t` 尚未拥有目标 `m` 的锁），则抛出一个 `IllegalMonitorStateException`。
- 如果是定时等待且 `nanoseconds` 参数不在 0–999999 范围内，或 `milliseconds` 参数为负数，则抛出一个 `IllegalArgumentException`。
- 如果线程 `t` 被中断，则抛出一个 `InterruptedException` 并将 `t` 的中断状态设置为 `false`。

否则，将发生以下序列：

1. 线程 `t` 被添加到对象 `m` 的等待集中，并在 `m` 上执行 `n` 次解锁操作。
2. 线程 `t` 在其被从 `m` 的等待集中移除 之前，将不执行任何后续指令。该线程可以通过以下任何一种操作从等待集中移除，并在此后的某个时间恢复执行：
   - 在 `t` 中对 `m` 执行的 `notify` 动作被选中从等待集中移除。
   - 在 `m` 上执行的 `notifyAll` 动作。
   - 对 `wait` 执行的中断动作，一个将 `t` 从 `m` 等待集中移除的内部动作，发生在至少 `millisecs` 毫秒加上 `nanoseconds` 纳秒之后。
3. 线程 `t` 在 `m` 上执行 `n` 次锁定操作。
4. 如果 `t` 因为中断被从 `m` 的等待集中移除，将自动对该监视器执行解锁操作。

#### 17.2.2 通知

通知动作发生在调用 `notify` 和 `notifyAll` 时。假设 `t` 是在对象 `m` 上执行这些任方法的线程，令 `n` 为 `t` 在 `m` 上执行且未与解锁操作匹配的锁定操作次数。发生以下操作之一：

- 如果 `n` 为 0，则抛出一个 `IllegalMonitorStateException`。这是因为线程 `t` 未拥有 `m` 的锁。
- 如果 `n` 大于 0 且是 `notify` 动作，则如果 `m` 的等待集不为空，将从 `m` 的等待集中选取并移除一个线程 `u`。对于从等待集中移除哪个线程没有保证。从等待集的移除使得 `u` 在等待动作中恢复执行。请注意，在 `t` 完全释放 `m` 的监视器之前，`u` 在等待时的锁无法成功。
- 如果 `n` 大于 0 且是 `notifyAll` 动作，则所有线程都从 `m` 的等待集中移除并恢复执行。请注意，一次只有一个线程可以锁定恢复等待时所需的监视器。

#### 17.2.3 中断

中断动作发生在调用 `Thread.interrupt`，以及定义为间接调用它的方法（如 `ThreadGroup.interrupt`）。

假设 `t` 是调用 `u.interrupt` 的线程，其中 `t` 和 `u` 可能同一个线程。此动作会导致 `u` 的中断状态被设置为 `true`。

此外，如果存在某个对象 `m` 的等待集包含 `u`，则 `u` 将从 `m` 等待集中移除。这使得 `u` 在等待动作中恢复执行，以防该等待在重新锁定 `m` 监视器后抛出 `InterruptedException`。

#### 17.2.4 等待、通知与中断的交互

上述规范允许我们确定若干与等待（wait）、通知（notification）和中断（interruption）交互相关的属性。

如果线程在等待时既收到了通知又被中断，它可能：

- 从 `wait` 正常返回，但仍有一个挂起的中断（换句话说，调用 `Thread.interrupted` 将返回 `true`）
- 通过抛出 `InterruptedException` 从 `wait` 返回

该线程可能重置其中断状态并从 `wait` 调用中正常返回。

同样地，通知不会因为中断而丢失。假设对象 `m` 的等待集上有一个线程集合 `s`，并且另一个线程对 `m` 执行了 `notify` 操作。那么：

- `s` 中的至少有一个线程必须从 `wait` 正常返回，或者
- `s` 中的所有线程都必须通过抛出 `InterruptedException` 退出 `wait`。

请注意，如果一个线程既被中断又通过 `notify` 被唤醒，且该线程通过抛出 `InterruptedException` 从 `wait` 返回，那么等待集中的其他某个线程必须被通知。

### 17.3 Sleep 与 Yield

`Thread.sleep` 导致当前执行的线程睡眠指定的持续时间（临时停止执行），这取决于系统计时器和调度器的精度与准确性。线程不会丢失对任何监视器（monitors）的所有权，执行的恢复将取决于调度以及执行该线程的处理器的可用性。

值得注意的是，`Thread.sleep` 和 `Thread.yield` 都不具有任何同步语义。特别是，在调用 `Thread.sleep` 或 `Thread.yield` 之前，编译器不需要将寄存器中写入的缓存刷新到共享内存；在调用 `Thread.sleep` 或 `Thread.yield` 之后，编译器不需要重新加载缓存在寄存器中的值。

例如，在以下（有错误的）代码段中，假设 `this.done` 是一个非 `volatile` 的布尔字段：

```
```



```
while (!this.done)
  Thread.sleep(1000);
```

编译器可以只读取一次字段 `this.done`，并在循环的每次执行中重用缓存的值。这意味着即使另一个线程改变了 `this.done` 的值，循环也永远不会终止。

## 17.4 内存模型

内存模型描述了在给定程序和该程序的执行轨迹（execution trace）的情况下，该执行轨迹是否为程序的合法执行。Java 语言内存模型的工作原理是检查执行轨迹中的每次读取，并检查该读取所观察到的写入是否根据规则是有效的。

内存模型描述了程序可能的行为。实现者可以自由地产生任何喜欢的代码，只要程序的所有最终执行产生的结果是可以被内存模型预测的即可。

> 这为实现者执行各种代码转换提供了极大的自由，包括操作的重排序和消除不必要的同步。

### 17.4.1 同步错误的程序可能表现出意料之外的行为

Java 编程语言的语义允许编译器和微处理器执行优化，这些优化可能与同步错误的代码交互，产生看似矛盾的行为。以下是同步程序表现出意料之外行为的一些示例。

考虑表 17.4-A 所示的示例程序轨迹。该程序使用了局部变量 `r1`、`r2` 以及共享变量 `A` 和 `B`。初始状态下 `A B == 0`。

#### 表 17.4-A. 语句排序导致的意外结果 - 原始代码

| Thread 1 | Thread 2 |
| :--- | --- |
| 1: r2 = A; | 3: r1 = B; |
| 2: B = 1; | 4: A = 2; |

结果 `r2 == 2` 且 `r1 == 1` 似乎是不可能的。直觉上，在执行过程中，指令 1 或指令 3 应该先执行。如果指令 1 先执行，它不应该能看到指令 4 的写入；如果指令 3 先执行，它不应该能看到指令 2 的写入。

如果执行表现出这种行为，我们就知道指令 4 在指令 1 之前，指令 1 在指令 2 之前……以此类推直到在指令 4 之前。这在表面上是荒谬的。

编译器允许在任意线程中重排序指令，只要这不影响该线程在隔离状态下的效果。如果指令 1 与指令 2 进行重排序（如表 17.4-B 中的轨迹所示），那么很容易看到出现 `r2 = 2` 且 `r1 = 1` 的结果。

#### 表 17.4-B. 语句重排序导致的意外结果 - 有效的编译器转换

| Thread 1 | Thread 2 |
| :--- | --- |
| B = 1; | r1 = B; |
| r2 = A; | A = 2; |

对于某些程序员来说，这种行为可能看起来是“损坏的”。然而，应该的是这段代码的同步是不正确的：

- 一个线程中有一个写入，
- 另一个线程对同一个变量进行读取，
- 写入和读取没有通过同步进行排序。

这种情况是数据竞态（§17.4.5）的一个示例。当代码包含数据竞态时，往往可能产生违反直觉的结果。

几种机制可以产生表 17.4-B 中的重排序。Java 虚拟机实现中的即时编译器（JIT）可能会重新排列代码或处理器。此外，运行 Java 虚拟机的架构的内存层次也可能使其看起来代码被重排序了。另一个意外结果的示例见表 17.4-C。初始状态下 `p == q` 且 `p.x == 0`。

#### 表 17.4-C. 转发替换导致的意外结果

| Thread 1 | Thread 2 |
| :--- | --- |
| r1 = p; | r6 = p; |
| r2 = r1.x; | r6.x = 3; |
| r3 = q; | |
| r4 = r3.x; | |
| r5 = r2; | |

现在考虑这种情况：Thread 2 中对 `r6.x` 的赋值发生在 Thread 1 第一次读取 `r1.x` 和读取 `r3.x` 之间。如果编译器决定重用 `r2` 的值，那么 `r2` 和 `r5` 将为 0，而 `r4` 将为3。从程序员的角度来看，`p.x` 存储的值从 0 变成了 3。

#### 表 17.4-D. 转发替换导致的意外结果

| Thread 1 | Thread 2 |
| :--- | --- |
| r1 = p; | r6 = p; |
| r2 = r1.x; | r6.x = 3; |
| r3 = q; | |
| r4 = r3.x; | |
| r5 = r2; | |

内存模型确定了程序中每个点可能的值。每个线程在隔离状态下的行为必须受该线程语义的支配，异常是每次读取所看到的值是由内存模型确定的。当我们提到这一点时，我们说程序遵循线程内语义。要确定执行中线程 `t` 的动作是否合法，我们只需按照本规范的其他部分，在单线程上下文评估线程 `t` 的实现。

每当评估 `t` 生成线程间动作时，它必须与程序顺序中之前的线程间动作 `a` 匹配。如果 `a` 是读取，那么对 `t` 的后续评估将使用内存模型确定的可见值。

本节提供了 Java 编程内存模型的规范，但涉及 final 字段的问题除外见 §17.5。

## 17.4.1 共享变量

可以在线程之间共享的内存被称为共享内存或堆内存。

所有实例字段、静态字段和数组元素都存储在堆内存中。在本章中，我们使用术语“变量”来同时指代字段和数组元素。

局部变量（§14.4）、形式方法参数（§8.4.1）和异常处理器参数（§14.20）永远不会在线程之间共享，且不受内存模型的影响。

对同一个变量的两次访问（读取或写入），如果至少有一个访问是写入操作，则认为这两个访问是冲突的。

## 17.4.2 动作

线程间动作是由一个线程执行，但可以被另一个线程直接检测到或影响的动作。程序可能执行的线程间动作有几种：

- 读取（正常的，或非 volatile 的）。读取变量。
- 写入（正常的，或非 volatile 的）。写入变量。
- 同步动作，包括：
  - volatile 读取。对变量进行 volatile 读取。
  - volatile 写入。对变量进行 volatile 写入。
  - 锁（Lock）。锁定监视器（monitor）。
  - 解锁（Unlock）。解锁监视器。
  - 线程的（合成的）第一个和最后一个动作。
  - 启动线程或检测线程终止的动作（§17.4.4）。
- 外部动作。外部动作是在执行过程之外可观测的动作，并且其结果基于执行过程之外的环境。
- 线程分散动作（§17.4.9）。线程分散动作仅由处于无限循环中的线程执行，且在该循环中没有执行任何内存、同步或外部动作。如果一个线程执行了线程分散动作，随后将是无限次的线程分散动作。

引入线程分散动作是为了建模一个线程如何导致所有其他线程停滞并无法进展。

本规范仅关注线程间动作。我们不需要关注线程内动作（例如，两个局部变量相加并将结果存储在第三个局部变量中）。如前所述，所有线程都需要遵守 Java 程序正确的线程内语义。我们通常简短地将线程间动作称为 *actions*（动作）。

动作 a 由元组 `< t, k, v, u >` 描述，包含：

- t - 执行该动作的线程
- k - 动作的类型
- v - 动作涉及的变量或监视器

对于锁动作，v 是被锁定的监视器；对于解锁动作，v 是正在解锁的监视器。

如果该动作是（volatile 或非 volatile 的）读取，v 是被读取的变量。

如果该动作是（volatile 或非 volatile 的）写入，v 是被写入的变量。

- u - 动作的任意标识符

动作元组还包含一个额外的组件，该组件包含了执行该动作的线程所感知的外部动作的结果。这可能包括关于动作成功或失败的信息，以及该动作读取的任何值。

外部动作的参数（例如，写入套接字的哪些字节）不属于外部动作元组的一部分。这些参数是由线程内部的其他动作设置的，可以通过检查线程内语义来确定。它们在内存模型中没有被显式讨论。

在非终止的执行中，并非所有外部动作都是可观测的。非终止执行和可观测动作在 §17.4.9 中讨论。

## 17.4.3 程序与程序顺序

在每个线程 t 执行的所有线程间动作中，*t 的程序顺序*（program order of t）是一个全序，反映了根据 t 的线程内语义执行这些动作的顺序。

如果所有动作都发生在一个与程序顺序一致的全序（执行顺序）中，则该动作集合是顺序一致的（sequentially consistent），并且对变量 v 的每次读取 r 都能看到写入 w 对 v 写入的值，并满足：

- w 在执行顺序中位于 r 之前，且
- 没有其他写入 w' 使得在执行顺序中 w 位于 w' 之前，且 w' 又位于 r 之前。

顺序一致性是对程序执行中的可见性和排序所做出的一项非常强的保证。在顺序一致的执行中，对于所有个体的动作（如读取和写入）存在一个全序，该全序与程序顺序一致，且每个个体动作都是原子的，并立即对每个线程可见。如果一个程序没有数据竞态，那么该程序的所有执行都将表现得是顺序一致的。

顺序一致性和无数据竞态允许出现那些本应被视为原子操作但实际上并非原子的操作组所引起的错误。如果我们使用顺序一致性作为内存模型，我们所开发的许多编译器优化将是非法的。例如，在表 17.4-C 的轨迹中，一旦发生了对 p.x 的写入，后续对 location 的读取就必须看到该值。

## 17.4.4 同步顺序

每次执行都有一个同步顺序。同步顺序是执行中所有同步动作的全序。对于每个线程 t，t 中同步动作（§17.4.2）的同步顺序与程序顺序（§17.4.3）一致。

同步动作诱导了如下定义的关系：

- 监视器 m 上的解锁动作与 m 上后续的所有动作同步于（synchronizes-with）（其中“后续”是根据同步顺序定义的）。
- 对 volatile 变量 v 的写入（§8.3.1.4）与任何线程对 v 的后续读取同步于（其中“后续”是根据同步顺序定义的）。
- 启动线程的动作与该线程的第一个动作同步于。
- 一个对象的默认值写入与该对象构造开始的任何后续动作同步于。
- 线程 T1 的结束动作与任何线程 T2 检测到 T1 已终止的动作同步于（通过调用 T1.join() 实现）。
- 线程 T1 中断 T2 与 T2 中到被中断的任何动作同步于（通过抛出 InterruptedException 实现）。

同步的源被称为 *release*（释放），而目标被称为 *acquire*（获取）。

## 17.4.5 先发生顺序

两个动作可以被先发生关系（happens-before relationship）排序。

如果我们有两个动作 x 和 y，hb(x, y) 表示：

- 如果 x 和 y 是同一线程的动作，且在程序顺序中 x 位于 y 之前，则 hb(x, y)。
- 对象的构造结束到该对象开始的任何后续动作之间存在一个先发生边（§12.6）。
- 如果一个动作同步于后续动作 y，则有 hb(x, y)。
- 如果 hb(x, y) 且 hb(y, z)，则 hb(x, z)。

先发生关系定义了数据竞态发生的条件。

一个同步边集合 S 是充分的，如果它是最小集合，使得 S 与程序顺序的传递闭包确定了执行中所有的先发生边。该集合是唯一的。

从上述定义可以得出：
- 监视器的解锁发生于该监视器的后续后续锁定。
- 对 volatile 字段的写入（§8.3.1.4）发生于该字段的后续读取。
- 对线程调用 start() 发生在被启动线程中的任何动作之前。
- 线程中的所有动作发生于任何其他线程成功从该线程的 join() 返回之前。
- 任何对象的默认初始化发生于程序的任何其他动作（默认写入除外）之前。

当程序包含两个冲突访问（§17.4.1）且没有被先发生关系排序时，认为它包含数据竞态。

线程间动作之外的操作语义，例如数组长度的读取（§10.7）、检查转换的执行（§5.5, §15.16）以及虚方法的调用（§15.12），并不直接受数据竞态的影响。

> 因此，数据竞态无法导致返回错误的数组长度等错误行为。

# 线程与锁

程序员不需要通过推断重排序来确定其代码是否包含数据竞态。因此，在确定其代码是否已正确同步时，他们也不需要推断重排序。一旦确定代码已通过正确同步，程序员就不需要担心重排序会影响其代码。

程序必须经过正确的同步，以避免出现当代码被重排序时可能观察到的那类反直觉的行为。使用正确的同步并不能保证程序的整体行为是正确的。然而，它的使用允许程序员以一种简单的方式推断程序的可能行为；一个正确同步的程序的行为对可能的重排序的依赖程度要少得多。如果没有正确的同步，可能会出现非常诡异、困惑且反直觉的行为。

我们说，如果变量 $v$ 的读取操作 $r$ 被允许观察到对 $v$ 的写入操作 $w$，如果执行轨迹的发生于（happens-before）偏序满足：

- $r$ 不在 $w$ 之前排序（即不存在 $hb(r, w)$），
- 不存在插入到 $v$ 的写入操作 $w'$（即不存在写入 $w'$ 使得 $hb(w', w)$ 且 $hb(w', r)$）。

通俗地说，如果存在发生于序排序来阻止该读取，则读取 $r$ 就被允许看到写入 $w$ 的结果。

如果一个动作集合 $A$ 是发生于序一致的，如果：对于 $A$ 中的所有读取操作 $r$，其中 $W(r)$ 是 $r$ 看到的写入操作，既不满足 $hb(r, W(r))$，也不存在 $A$ 中的写入操作 $w$ 使得 $w.v = r.v$ 且 $hb(W(r), w)$ 且 $hb(w, r)$。

在发生于序一致的动作集中，每个读取都能看到一个根据发生于序被允许其看到的写入。

示例 17.4.5-1。表 17.4.5-A，初始状态 $A == B == 0$。轨迹 $r2 == 0$ 且 $r1 == 0$ 仍然是发生于序一致的，因为存在某些执行顺序，使得每个读取都能看到相应的写入。

#### 表 17.4.5-A. 发生于序一致性允许的，但顺序一致性不允许的行为

| 线程 1 | 线程 2 |
| --- | --- |
| B = 1; | A = 2; |
| r2 = A; | r1 = B; |

由于没有同步，每个读取都可以看到初始值的写入或来自另一个线程的写入。显示这种行为的执行顺序如下：

```
1: B = 1;
3: A = 2;
2: r2 = A; // 看到初始写入 0
4: r1 = B; // 看到初始写入 0
```

另一个发生于序一致的执行顺序是：

```
1: r2 = A; // 看到 A = 2 的写入
3: r1 = B; // 看到 B = 1 的写入
2: B = 1;
4: A = 2;
```



在此执行中，读取看到了发生在执行顺序后方的写入。这似乎是反直觉的，但发生于序一致性允许允许。允许读取看到后续写入有时会产生不可接受的行为。

# 17.4.6 执行

一个执行 $E$ 由元组 $\langle P, A, po, so, W, V, sw, hb \rangle$ 描述，包含：

- `P` - 一个程序
- `A` - 动作集合
- `po` - 程序序，对于每个线程 $t$，它是 $t$ 在 $A$ 中执行的所有动作的全序。
- `so` - 同步序，它是 $A$ 中所有同步动作的全序。
- `W` - 写入-看到函数，对于 $A$ 中的每个读取 $r$，给出 $W(r)$，即 $r$ 在执行 $E$ 中看到的写入操作。
- `V` - 写入值函数，对于 $A$ 中的每个写入 $w$，给出 $V(w)$，即 $w$ 在 $E$ 中写入的值。
- `sw` - 同步于（synchronizes-with），同步动作的偏序。
- `hb` - 发生于（happens-before），动作的偏序。

注意，同步于和发生于的元素由执行的其他组件以及形成良好执行的规则（§17.4.7）唯一确定。

如果一个执行的动作集合是发生于序一致的，则该执行是发生于序一致的（§17.4.5）。

# 17.4.7 良好的执行

我们只考虑良好的执行。如果执行 $E = \langle P, A, po, so, W, V, sw, hb \rangle$ 满足以下条件，则该执行是良好的：

1. 每个读取都看到执行中对同一变量的写入。
   volatile 变量的所有读取和写入都是 volatile 动作。对于 $A$ 中的所有读取 $r$，我们有 $W(r) \in A$ 且 $W(r).v = r.v$。变量 $r.v$ 是 volatile 的当且仅当 $r$ 是 volatile 读取时，变量 $w.v$ 是 volatile 的当且仅当 $w$ 是 volatile 写入时。
2. 发生于序是一个偏序。
   发生于序由同步序边和程序序的传递闭包给出。它必须是一个有效的偏序：自反、传递性和反对称性。
3. 执行遵守线程内一致性。
   对于每个线程 $t$，$t$ 在 $A$ 中执行的动作与该线程在初始化时按程序序生成的动作相同，其中每个读取 $r$ 看到值 $V(W(r))$，前提是每个读取 $r$ 看到由内存模型定义的值。每个读取看到的值由内存模型决定。程序序必须反映根据 $P$ 的线程内语义执行动作的程序序。
4. 执行是*发生于序一致的*（§17.4.6）。
5. 执行遵守同步序一致性。
   对于 $A$ 中的所有 volatile 读取 $r$，不满足 $so(r, W(r))$，也不存在 $A$ 中的写入 $w$ 使得 $w.v = r.v$ 且 $so(W(r), w)$ 且 $so(w, r)$。

# 17.4.8 执行与因果关系要求

我们使用 $f_d$ 表示通过将 $f$ 的定义域限制为 $d$ 得到的函数。对于 $d$ 中的所有 $x$，$f_d(x)=f(x)$，而对于不在 $d$ 中的 $x$，$f_d(x)$ 是未定义的。

我们使用 $p_d$ 表示偏序 $p$ 对 $d$ 中元素的限制。对于 $d$ 中的所有 $x,y$，$p_d(x,y)$ 有定义当且仅当 $p(x,y)$ 有定义。

良好的执行 $E = \langle P, A, po, so, W, V, sw, hb \rangle$ 通过*提交*动作 $A$ 来验证。如果 $A$ 中的所有动作都可以提交，则执行满足因果关系要求。

从空集 $C_0$ 开始，执行一系列步骤，从动作集合 $A$ 中提取动作并添加到提交集 $C_i$，以获得新的提交集 $C_{i+1}$。为了证明这一点，对于每个 $C_i$，我们需要一个包含 $C_i$ 的执行。

一个执行 $E$ 满足 Java 内存模型的要求，当且仅当存在动作集合 $C_0, C_1, \dots$，使得：

- $C_0$ 是空集
- $C_i$ 是 $C_{i+1}$ 的真子集
- $A = \cup(C_0, C_1, \dots)$ 是有限的。如果 $A$ 是无限的，则序列 $C_0, C_1, \dots$ 可以是无限的，且其并必须等于 $A$。
- 良好的执行 $E_i, \dots$，其中 $E_i = \langle P, A_i, po_i, so_i, W_i, V_i, sw_i, hb_i \rangle$。

给定动作集合 $C_0, \dots$ 和执行 $E_i, \dots$，$C_i$ 中的每个动作都必须属于 $E_i$。$C_i$ 中的所有动作在 $E_i$ 和 $E_j$ 中具有相同的发生于序和同步序。形式上：

1. $C_i$ 是 $A_i$ 的子集
2. $hb_i[C_i] = hb_j[C_i]$
3. $so_i[C_i] = so_j[C_i]$
4. $V_i[C_{i,j}] = V_j[C_{i,j}]$
5. $W_i[C_{i,j}] = W_j[C_{i,j}]$

$C_i$ 中写入产生的值在 $E_i$ 和 $E_j$ 中必须相同。只有 $C_{i,j}$ 中的读取需要在 $E_i$ 中看到与在 $E_j$ 中相同的写入。形式上：

执行 $E_i$ 中不在 $C_{i,j}$ 中的所有读取都必须看到发生于它们的写入。$C_i - C_{i,j}$ 中的每个读取 $r$ 在 $E_i$ 和 $E_j$ 中都能看到写入，但在 $E_i$ 中看到的写入与其在 $E_j$ 中看到的不同。形式上：

6. 对于 $A_i - C_{i,j}$ 中的任何读取 $r$，有 $hb_i(W(r), r)$
7. 对于 $(C_i - C_{i,j})$ 中的任何读取 $r$，我们有 $W_i(r) \in C_{i,j}$ 且 $W_j(r) \in C_{i,j}$。

对于 $E_i$，如果存在足够的同步边（synchronizes-with-edges），且存在一个释放-获取对（release-acquire pair）先（§17.4.5）于你提交的操作，那么该对必须出现在所有的 $E_j$ 中，其中 $j \ge i$。形式化如下：

- 设 $ssw$ 为所有在 $hb$ 的传递归约中但不在 $po$ 中的 $sw$ 边集合。我们称 $ssw$ 为 $E_i$ 的充分同步边；如果 $ssw(x, y)$ 和 $hb(y, z)$ 都在 $C_i$ 中，则对于所有 $j \ge i$，$sw(x, y)$ 均存在。
- 如果动作 $y$ 被提交，则所有发生在其之前的动作也都被提交。
- 如果 $y$ 在 $C_i$ 中，$x$ 是一个外部动作且 $hb(x, y)$，则它们在 $C_j$ 中。

## 17.4.8-1 先发生一致性并不充分

先发生一致性（Happens-before consistency）是一组必要但非充分的约束。仅仅强制先发生一致性会允许不可接受的行为发生——那些违反了我们为程序建立的要求的行为。例如，先发生一致性允许值“凭空出现”。通过详细检查轨迹（trace） 17.4.8-A 可以看出这一点。

| 线程 1 | 线程 2 |
|---|---|
| `r1 = x;` | `r2 = y;` |
| `if (r1 != 0) y = 1;` | `if (r2 != 0) x = 1;` |

17.4.8-A 中的代码是正确同步的。这看起来可能令人惊讶，因为它没有执行任何同步动作。但请记住，当一个程序以顺序一致的方式执行且没有数据竞态时，该程序就是正确同步的。如果这段代码以顺序一致的方式执行，每个动作将按照程序顺序发生，且两个写入操作都不会发生。由于没有写入，就不可能存在数据竞态：该程序是正确同步的。

由于该程序是正确同步的，我们允许的行为是顺序一致的行为。然而，该程序存在一种执行是先发生一致的但不是顺序一致的：

```
r1 = x; // 看到 x = 1 的写入
y = 1;
r2 = y; // 看到 y = 1 的写入
x = 1;
```

这个结果是先发生一致的：没有一种先发生关系阻止它的发生。然而，它显然是不可接受的：没有一种顺序一致的执行会产生这种行为。允许读取执行顺序中后出现的写入这一事实，可能会导致不可接受的行为。

虽然允许读取看到执行顺序中后出现的写入有时是不如人愿的，但有时它也是必要的。正如我们在上面看到的，表 17.4.5-A 中的轨迹要求读取看到执行顺序中后发生的写入。由于读取在每个线程中都先出现，因此执行顺序中的第一个动作必须是读取。如果该读取无法看到后发生的写入，那么它无法看到该变量初始值之外的任何值。这显然不能反映所有的行为。

我们将读取可以看到写入的问题称为*因果关系*（causality），因为在类似表 17.4.8-A 中的情况下会出现此类问题。在这种情况下，读取导致了写入的发生，而写入导致了读取的排序。动作没有“原因”。因此，我们的内存模型需要一种方法来确定哪些读取可以看到写入。

它还将看到由这些 final 字段引用的任何对象或数组的版本，其版本至少与这些 final 字段一样新。

## 示例 17.5-1 Java 内存模型中的 final 字段

下面的程序说明了 final 字段与普通字段的比较。

```java
class FinalFieldExample {
    final int x;
    int y;
    static FinalFieldExample f;

    public FinalFieldExample() {
        x = 3;
        y = 4;
    }

    static void writer() {
        f = new FinalFieldExample();
    }

    static void reader() {
        if (f != null) {
            int i = f.x; // 保证看到 3
            int j = f.y; // 可能会看到 0
        }
    }
}
```

类 `FinalFieldExample` 有一个 final 字段 `x` 和非 final 字段 `y`。一个线程可能执行 `writer` 方法，而另一个线程可能执行 `reader` 方法。

由于 `writer` 方法在对象构造函数完成后写入了 `f`，因此 `reader` 将保证看到 `f.x` 正确初始化的值；它将读取值 3。`f.y` 不是 final 的；因此 `reader` 方法不保证能看到 `f` 的值为 4。

## 示例 17.5-2 用于安全性的 final 字段

final 字段的设计是为了允许提供必要的安全保障。考虑以下程序。`Global.s`：一个线程（我们将其称为线程 1）执行：

```java
Global.s = "/tmp/usr".substring(4);
```

而另一个线程（线程 2）执行：

```java
String myS = Global.s;
if (myS.equals("/tmp")) System.out.println(myS);
```

String 对象旨在是不可变的，且字符串操作不执行同步处理。虽然 String 的实现没有任何数据竞态条件

### 17.5.1 final 字段的语义

令 `o` 为一个对象，`c` 为 `o` 的构造函数，在其中写入了 final 字段 `f`。当 `c` 退出时（无论是正常退出还是异常退出），会对 `o` 的 final 字段 `f` 冻结（freeze）。

注意，如果一个构造函数调用了另一个构造函数，被调用的构造函数设置了 final 字段，该 final 字段的冻结发生在被调用构造函数的结束时。

对于每次执行，读取行为受到两个额外偏序的影响：解引用链 `dereferences(c)` 和内存链 `mc(c)`，它们被视为执行的一部分（因此对于任何特定执行来说是固定的）。这些偏序必须满足以下约束（不需要有唯一解）：

- 解引用链：如果操作 `a` 是未初始化 `o` 的线程 `t` 对对象 `o` 字段的读，则必须存在线程 `t` 的某个读取操作 `r`，它看到了 `r` 解用的 `o` 的地址，即 `dereferences(r, a)`。
- 内存链：内存链排序有几项约束：
  - 如果 `r` 是看到 `w` 的读取操作，则必须满足 `mc(w, r)`。
  - 如果 `r` 和 `a` 是解引用 `dereferences(r, a)` 的操作，则必须满足 `mc(r, a)`。

给定一个 `w`、一个冻结 `f`、一个操作 `a`（不是对 final 字段的读取）、一个对 `f` 冻结的 final 字段的读取 `r1` 以及一个读取 `r2`，使得 `hb(w,f)`, `hb(f,a)`, `mc(a, r1)` 和 `dereferences(r1, r2)`，则确定 `r2` 可以看到哪些值。

我们考虑 `hb(w, r2)`。（这种发生之前的排序不会与其他发生之前的排序发生传递闭合。）

注意解引用顺序是自反射的，`r1` 可以与 `r2` 相同。

对于 final 字段的读取，被认为发生在 final 字段读取之前的写入操作仅是通过 final 字段语义推导出的那些。

### 17.5.2 在构造期间读取 final 字段

在构造该对象的线程内对对象的 final 字段的读取是根据发生之前的规则排序的。如果读取发生在构造函数中设置字段之后，它将看到 final 字段已赋值，否则它将看到默认值。

### 17.5.3 final 字段的后续修改

在某些情况下（例如反序列化），系统需要在构造后更改对象的 final 字段。final 字段可以通过反射和其他依赖于实现的方法更改。只有在一种模式下这种操作具有合理的语义：即构造一个对象，然后读取该对象的 final 字段，直到对对象 final 字段的所有更新都完成。在对对象 final 字段的所有更新完成之前，该对象不应对其他线程可见，也不应读取 final 字段。final 字段的冻结既发生在设置该 final 字段的构造函数结束时，也发生在通过反射或其他特殊机制修改 final 字段的立即之后。

尽管如此，仍有许多复杂性。final 字段在字段声明中被初始化为常量表达式 (§15.29)，对 final 字段的更改可能无法被观察，因为对 final 字段的使用在编译时替换为常量表达式的值。

另一个问题是规范允许对 final 字段进行激进优化。在线程内部，允许对 final 字段的读取与未在构造函数中发生的 final 字段修改进行重排序。

## 示例 17.5.3-1 final 字段的激进优化

```java
class A {
    final int x;

    A() {
        x = 1;
    }
}
```



```java
v++;
counts[id] = v;
}

public static void main(String[] args) {
  for (int i = 0; i < LENGTH; ++i) {
    (threads[i] = new WordTearing(i)).start();
  }
}
```

# 17.7 double 和 long 的非原子处理

对于 Java 编程语言内存模型而言，对非 `volatile` 的 `long` 或 `double` 值的单次写入被视为两个独立的写入：分别写入每个 32 位的半部分。这可能导致一种情况：线程从某次写入看到了 64 位值的第一个 32 位，而从另一次写入看到了后 32 位。

对 `volatile` `long` 和 `double` 值的写入和读取始终是原子的。

引用的写入和读取始终是原子的，无论它们被实现为 32 位还是 64 位值。

某些实现可能会发现将对 64 位 `long` 或 `double` 值的单次写入操作分为两个对相邻 32 位值的写入操作是方便的。出于效率考虑，这种行为取决于具体的实现；Java 虚拟机的实现可以自由地选择对 `long` 和 `double` 值进行原子写入，也可以分两次写入。

鼓励 Java 虚拟机实现尽可能避免拆分 64 位值。鼓励程序员将共享的 64 位值声明为 `volatile`，或正确地同步其程序，以避免可能出现的复杂性。

# 第 18 章 类型推断

各种编译时分析需要对尚不可知的类型进行推理。其中最主要的是泛型方法可用性测试 (§18.5.1) 和泛型方法调用类型推断 (§18.5.2)。泛而言之，我们将对未知类型进行推理的过程称为类型推断。

在高级层次上，类型推断可以分解为三个过程：

- **归约（Reduction）**：获取一个关于表达式或类型的兼容性断言（称为约束公式），并将其归约为推断变量的一组界（bounds）。通常情况下，约束公式会归约为其他约束公式，这些公式必须递归地归约。遵循一个程序来识别这些额外的约束公式，并最终通过界集来表达推断类型在何种条件下使每个约束公式为真。
- **合并（Incorporation）**：维护一组推断变量的界，确保在添加新界时这些界是一致的。由于一个变量的界有时会影响另一个变量可能的选择，此过程在这些相互依赖的变量之间传播界。
- **解析（Resolution）**：检查推断变量的界，并确定与这些界兼容的实例化（instantiation）。它还决定了相互依赖的推断变量的解析顺序。

这些过程紧密交互：归约可以触发合并；合并可能导致进一步的归约；而解析可能会导致进一步的合并。

- §18.1 更精确地定义了作为中间结果的概念以及用于表示这些内容的符号。
- §18.2 详细描述了归约。
- §18.3 详细描述了合并。
- §18.4 详细描述了解析。
- §18.5 定义了如何使用这些推断工具来解决某些编译时分析问题。

与《Java 语言规范》Java SE 7 版相比，推断的重要变化包括：

- 支持将 lambda 表达式和方法引用作为方法调用参数。
- 泛化为通过多项式（poly expressions）来定义推断，这些表达式在推断完成后可能没有定义良好的类型。这对于改进嵌套泛型方法和菱形构造函数调用的推断具有显著效果。
- 描述了如何使用推断来处理通配符参数化的函数接口目标类型以及最特定方法分析。
- 澄清了推断可用性测试（仅涉及调用参数）与调用类型推断（包含目标类型）之间的区别。
- 延迟所有推断变量（即使是具有下界的变量）的解析，直到推断类型，以便获得更好的结果。
- 改进了相互依赖（或自依赖）变量的推断行为。
- 消灭了 bug 和潜在的混淆来源。本次修订可能更仔细、精确地处理了特定版本上下文与子类型（subtyping）之间的区别，并通过对应相应的非推断关系来描述这种关系。在故意偏离非推断关系的地方，这些被显式地标识出来。
- 为未来的演进奠定基础：对推断的增强或新应用将更容易集成到规范中。

## 18.1 概念与符号

本节定义了推断变量、约束公式和界，这些术语将贯穿本章。它还介绍了符号表示。

### 18.1.1 推断变量

推断变量是类型的元变量（meta-variables）——即允许对类型进行抽象推理的特殊名称。为了将它们与类型变量区分开来，推断变量用希腊字母表示，主要是 $\alpha$。

“类型”一词在本章中被泛指，包含包含推断变量的类类型语法。真正的类型（proper type）排除了此类提到推断变量的“类型”。涉及推断变量的断言是关于通过将每个推断变量替换为真正的类型而产生的每个类型的断言。

### 18.1.2 约束公式

约束公式是关于兼容性或子类型的断言，可能涉及推断变量。这些公式可能采取以下形式之一：

- `Expression → T`：表达式在宽松的调用上下文中与类型 `T` 兼容 (§5.3)。
- `S → T`：类型 `S` 在宽松的调用上下文中与类型 `T` 兼容 (§5.3)。
- `S <: T`：引用类型 `S` 是引用类型 `T` 的子类型 (§4.10)。
- `S <= T`：参数 `S` 被类型参数 `T` 包含 (§4.5)。
- `S = T`：类型 `S` 与类型 `T` 相等。
- `Expression throws T`：表达式抛出的异常与类型 `T` 兼容。
- `Method throws T`：方法抛出的异常与类型 `T` 兼容。

约束公式的示例：

- `Collections.singleton("hi")` 具有约束公式，通过归约，将是 $\alpha$。
- `Arrays.asList(1, 2.0)` 具有约束公式，通过归约，将是 $\alpha$。

### 18.1.3 界

在推断过程中，维护一组关于推断变量的界。界具有以下形式之一：

- `S = T`，其中 `S` 或 `T` 是推断变量。
- `S <: T`，其中 `S` 或 `T` 是推断变量。
- `S <= T`，其中 `S` 或 `T` 是推断变量。

## 18.2 归约

当推断开始时，通常会根据类型参数声明列表 $P_1, ..., P_p$ 以及相关的推断变量 $\alpha_1, ..., \alpha_p$ 生成一个绑定集。该绑定集的生成方式如下。对于 $l$ ($1 \le l \le p$)：

- 如果 $P_l$ 没有 `TypeBound`（类型边界），则在集合中出现绑定 $\alpha_l <: \text{Object}$。
- 否则，对于 `TypeBound` 中由 `&` 隔开的每个类型 $T$，集合中出现绑定 $\alpha_l <: T[P_1:=\alpha_1, ..., P_p:=\alpha_p]$；如果 $\alpha_l$ 没有适当的上界（仅有依赖关系），则绑定 $\alpha_l <: \text{Object}$ 也会出现在集合中。

归约是将一组约束公式 (§18.1.2) 简化以产生一个绑定集 (§18.1.3) 的过程。

逐一考虑每个约束公式。本节中的规则规定了如何将公式归约为以下一种或两者：

- 一个绑定或集合，它将与“当前”绑定集合并。初始情况下，当前绑定集为空。
- 进一步的约束公式，将递归地归约。

当没有更多待归约的约束公式时，归约完成。

> 归约步骤的结果始终是*保可靠性的* (soundness-preserving)：如果一个推断变量的实例化满足归约后的约束和绑定，它也将满足原始约束。另一方面，归约不是*保完备性的* (completeness-preserving)：可能存在满足原始约束但*不满足* 归约后的约束或绑定的推断实例化。这是由于算法固有的局限性，以及为了避免复杂性的考虑。其影响之一是，某些表达式的类型参数推断无法找到解决方案，但如果程序员显式地插入类型，它们就可以是类型安全的。

### 18.2.1 表达式兼容性约束

形式为 `⟨Expression → τ⟩` 的约束公式归约如下：

- 如果 $\tau$ 是一个适当类型，当该表达式在松散调用文中与 $\tau$ 兼容 (§18.5.3) 时，约束归约为 `true`，否则为 `false`。
- 否则，如果该表达式是类型为 $S$ 的独立表达式 (§15.2.2)，约束归约为 `⟨S → τ⟩`。
- 否则，该表达式是一个多态表达式 (§15.2)。结果取决于表达式的形式：
  - 如果表达式是形式为 `(Expression)` 的括号表达式，则约束归约为 `⟨Expression → τ⟩`。
  - 如果表达式是类实例创建表达式或方法调用表达式，则约束归约为绑定集 $B_j$，该绑定集将用于确定表达式与目标类型 $\tau$ 的兼容性，定义见 §18.5.2.1。（对于类实例创建表达式，用于推断的相应“方法”定义在 §15.9.3 中。）此绑定集可能包含新变量，以及这些新变量与 $\tau$ 中的推断变量之间的依赖关系。
  - 如果该表达式是形式为 `e1 ? e2 : e3` 的条件表达式，则约束归约为两个约束公式 `⟨e2 → τ⟩` 和 `⟨e3 → τ⟩`。
  - 如果该表达式是 lambda 表达式或方法引用表达式，结果如下所示：
  - 如果该表达式是带有结果表达式 $e_1, ..., e_n$ 的 `switch` 表达式，则约束归约为 $n$ 个约束公式 `⟨e1 → τ⟩, ..., ⟨en → τ⟩`。

通过将泛型方法调用视为多态依赖关系，我们改进了嵌套调用的推断行为。例如，以下代码在 Java 7 中是不合法的，但在 Java 8 中是合法的：

```java
ProcessBuilder b = new ProcessBuilder(Collections.emptyList());
// ProcessBuilder 的构造函数需要 List<String>
```

当外部和嵌套推断同时发生时，问题变得更加复杂。例如：

```java
List<String> ls = new ArrayList<>(Collections.emptyList());
```



我们的方法是将嵌套调用推出的绑定（在本例中为简单的 `α <: Object`）“提升”到外部推断过程中（在本例中，对于类型 `ArrayList<?β>` 尝试推断 `β`）。我们还推断了嵌套变量与外部推断变量之间的依赖关系（`List<?β>` 将归约为依赖关系 `α = β`）。这样，嵌套调用中的推断变量就可以等待外部调用提供的额外信息（基于赋值目标 `β = String`）。

形式为 `<LambdaExpression → τ>` 且 `τ` 至少包含一个推断变量的约束公式归约如下：

- 如果 `τ` 不是函数接口类型（§9.8），则约束归约为 `false`。
- 否则，令 `τ'` 为从 `τ` 导出的基础目标类型（所示）。如果 `τ'` 是函数接口类型，我们检查 lambda 表达式是否与 `τ'` 兼容。如果是，约束归约为 `true`；否则归约为 `false`。

# 类型推断

## 归约

### 18.2

+ 否则，如果目标为 `τ` 时，该方法引用不存在潜在适用的方法，则该约束归约为 `false`。

+ 否则，如果该方法引用是精确的（§15.13.1），则令 `P₁, …, Pₙ` 为 `T` 的函数类型的参数类型，而 `F₁, …, Fₖ` 为潜在适用方法的参数类型。该约束归约为一组新的约束，如下：

+ - 在 `n = k + 1` 的特殊情况下，参数类型 `Pⱼ` 用作调用的目标引用。方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`。该约束归约为 `P₁ <: ReferenceType`，并且对于所有的 `i`（`2 ≤ i ≤ n`），`Pᵢ → Fᵢ₋₁`。

+ - 在其他情况下，`n = k`，且该约束归约为对于所有的 `i`（`1 ≤ i ≤ n`），`Pᵢ → Fᵢ`。

+ - 如果函数的返回值不是 `void`，令 `R` 为其返回类型。那么，如果潜在适用编译时声明的结果是 `void`，则该约束归约为 `R' → R`，其中 `R'` 是对潜在适用方法的返回类型应用类型转换的结果。

+ 否则，方法引用是不精确的（inexact），且：

+ - 如果函数的参数类型有一个不是有效类型，则约束归约为 `false`。

> 由于 §18.5 中对不精确方法引用处理以及 §18.5.2 对目标类型的替换，这种情况永远不会出现。

+ 否则，执行对编译时声明的搜索，如 §15.13.1 指定。如果方法引用没有编译时声明，则约束归约为 `false`。否则，存在编译时声明，并且（令 `R` 为函数类型的结果）：

+ > 如果 `R` 是 `void`，则约束归约为 `true`。

+ > 否则，如果方法引用省略了 `TypeArguments`，则编译时声明是一个泛型方法，且其返回类型提到了类型参数中的至少一个，那么：

+ > > 如果 `R` 提到了函数类型参数中的中的一个，则约束归约为 `false`。在这种情况下，关于 `R` 的约束可能会导致推断变量绑定到一个作用域外类型。由于将推断变量实例化为作用域外类型是没有意义的，每当出现这种情况时我们都会放弃。这种简化不是保持完备性的。

+ > > 如果 `R` 没有提到函数类型类型参数中的任何一个，则约束归约为边界 `Bⱼ`，该边界在 §8.5.2 中用于确定方法的返回类型，`Bⱼ` 可能包含新的推断变量，以及这些变量与 `T` 中的推断变量之间的依赖关系。确定泛型方法返回类型的策略遵循本节早期用于泛型调用的模式。这可能涉及“提升”到外部上下文，并在两组推断变量之间进行推断。

+ 否则，令 `R'` 为对调用的返回类型（§15.2.6）应用类型转换（§5.10）的结果。如果 `R'` 是 `void`，则约束归约为 `false`；否则，约束归约为 `⟨R' → R⟩`。

### 18.2.2 兼容性约束

形式为 `⟨S → T⟩` 的约束归约如下：

+ 如果 `S` 和 `T` 是有效类型，如果 `S` 与 `T` 在松散调用上下文兼容（§5.3），则约束归约为 `true`，否则归约为 `false`。

+ 否则，如果 `S` 是基本类型，令 `S'` 为对 `S` 应用装箱转换（§5.7）的结果，则约束归约为 `⟨S' → T⟩`。

+ 否则，如果 `T` 是基本类型，令 `T'` 为对 `T` 应用装箱转换（§5.7）的结果，则约束归约为 `⟨S = T'⟩`。

+ 否则，如果 `T` 是形式为 `G<T₁, ..., Tₙ>` 的参数化类型，且存在形式为 `G<...>` 的类型是 `S` 的超类型，但原始类型 `G` 是 `S` 的超类型，则约束归约为 `true`。

+ 否则，如果 `T` 是形式为 `G<T₁, ..., Tₙ>[]ᵏ` 的数组类型，且不存在形式为 `G<...>[]ᵏ` 的类型是 `S` 的超类型，但原始类型 `G[]ᵏ` 是 `S` 的超类型，则约束归约为 `true`。（符号 `[]ᵏ` 表示 `k` 维数组类型）。

+ 否则，约束归约为 `⟨S → T⟩`。第四种和第五种情况的隐式转换使用可能会导致未检查的转换使用，这些转换不是保持完备性的；例如，如果 `T` 是 `long`，`S` 可能会被扩展为 `T`。在这些情况下通常不清楚转换是否必要。同样，对于未检查转换，除非必要，否则推断倾向于避免它们。

### 18.2.3 子类型约束

形式为 `S <: T` 的约束归约如下：

+ 如果 `S` 和 `T` 是有效类型，如果 `S` 是 `T` 的子类型（§4.4），则约束归约为 `true`，否则归约为 `false`。

+ 否则，如果 `S` 是空类型，则约束归约为 `true`。

+ 否则，如果 `T` 是空类型，则约束归约为 `false`。

+ 否则，如果 `S` 是推断变量 `α`，则约束归约为 `α <: T`。

+ 否则，如果 `T` 是推断变量 `α`，则约束归约为 `S <: α`。

+ 否则，如果 `T` 是参数化类或接口类型，令 `A₁, …, Aₙ` 为 `T` 的类型参数。如果 `S` 也是参数化类或接口类型，具有类型参数 `B₁, …, Bₙ`，则约束归约为以下新的约束：对于所有的 `i`（`1 ≤ i ≤ n`），`Bᵢ <: Aᵢ`。

+ 否则，如果 `T` 是数组类型 `T'[]`，则确定 `S` 的数组类型中的最具体的类型 `S'[]`。如果没有数组类型，则约束归约为 `false`。否则：

+ > 如果 `S'` 和 `T'` 都不是基本类型，则约束归约为 `⟨S' → T'⟩`。

+ > 否则，如果 `S'` 和 `T'` 是相同的基本类型，则约束归约为 `true`，否则归约为 `false`。

+ 否则，如果 `T` 是类型变量，有三种情况：

+ > 如果 `S` 是以 `T` 为元素的交集类型，则约束归约为 `true`。

+ > 否则，约束归约为 `false`。

+ 否则，如果 `T` 是交集类型 `I₁ & ... & Iₙ`，约束归约为以下新的约束：对于所有的 `i`（`1 ≤ i ≤ n`），`S <: Iᵢ`。

形式为 `⟨S <: T⟩` 的约束，其中 `S` 和 `T` 是类型参数（§4.5.1），归约如下：

+ `T` 是类型：

+ - 如果 `S` 是类型，则约束归约为 `⟨S = T⟩`。

+ - 如果 `S` 是通配符，则约束归约为 `true`。

+ - 如果 `T` 是形式为 `?` 的通配符，则约束归约为 `true`。

+ - 如果 `T` 是形式为 `? extends T'` 的通配符：

+ - - 如果 `S` 是类型，则约束归约为 `⟨S <: T'⟩`。

+ - - 如果 `S` 是形式为 `?` 的通配符，则约束归约为 `⟨Object <: T'⟩`。

+ - - 如果 `S` 是形式为 `? extends S'` 的通配符，则约束归约为 `⟨S' <: T'⟩`。

+ - - 如果 `S` 是形式为 `? super S'` 的通配符，则约束归约为 `⟨Object = T'⟩`。

+ - 如果 `T` 是形式为 `? super T'` 的通配符：

+ - - 如果 `S` 是类型，则约束归约为 `⟨T' <: S⟩`。

+ - - 如果 `S` 是形式为 `? super S'` 的通配符，则约束归约为 `⟨T' <: S'⟩`。

+ - - 否则，约束归约为 `false`。

### 18.2.4 类型等价约束

形式为 `⟨S = T⟩` 的约束公式（其中 `S` 和 `T` 是类型）按如下方式归约：

- 如果 `S` 和 `T` 是具体类型，则约束归约为 `true`（如果它们相同）或 `false`（如果它们不同）。

> 此规则未考虑到直接作为交集类型元素出现的推断变量（而不是嵌套在参数化类型中）。由于对类型参数声明的限制（§4.4），此类交集类型在实践中不会出现。

- 否则，约束归约为 `false`。

形式为 `⟨S = T⟩` 且 `S` 和 `T` 是类型参数（§4.5.1）的约束公式，按如下方式归约：

- - 如果 `S` 和 `T` 是类型，约束按上述描述归约。
- - 如果 `S` 的形式为 `?` 且 `T` 的形式为 `?`，约束归约为 `true`。
- - 如果 `S` 的形式为 `?` 且 `T` 的形式为 `extends T'`，约束归约为 `⟨Object = T'⟩`。
- - 如果 `S` 的形式为 `extends S'` 且 `T` 的形式为 `?`，约束归约为 `⟨S' = Object⟩`。
- - 如果 `S` 的形式为 `extends S'` 且 `T` 的形式为 `extends T'`，约束归约为 `⟨S' = T'⟩`。
- - 如果 `S` 的形式为 `super S'` 且 `T` 的形式为 `super T'`，约束归约为 `⟨S' = T'⟩`。
- - 否则，约束归约为 `false`。

### 18.2.5 检举异常约束

形式为 `⟨LambdaExpression → throws T⟩` 的约束公式按如下方式归约：

- - 如果 `T` 不是函数接口类型（§9.8），约束归约为 `false`。
- - 否则，按照 §15.27.3 规定确定 lambda 表达式的目标函数类型。如果找不到有效的函数类型，约束归约为 `false`。
- - 否则，如果该 lambda 表达式是隐式类型化的，且函数的参数类型中有一个或多个不是具体类型，则约束归约为 `false`。

> 这种情况由于 §18.5.2.2 中对目标类型应用的替换，在实践中永远不会出现。

- - 否则，如果函数类型的返回类型既不是 `void` 也不是具体类型，约束归约为 `false`。

> 这种情况由于 §18.5.2.2 中对目标类型应用的替换，在实践中永远不会出现。

- - 否则，令 `E₁, ..., Eₙ` 为函数类型 `throws` 子句中不是具体类型的类型。如果 lambda 表达式是隐式类型化的，令其参数类型为函数的参数类型。如果 lambda 表达式体是一个包含多类型结果的表达式或块，令目标返回类型为函数的返回类型。令 `X₁, ..., Xₘ` 为 lambda 表达式体可以抛出的检举异常类型（§11.2）。此时有两种情况：

- - - 如果 `n = 0`（函数的 `throws` 子句仅包含具体类型），则如果存在 `i (1 ≤ i ≤ m)` 使得 `Xᵢ` 不是 `throws` 子句中任何具体类型的子类型，则约束归约为 `false`；否则，约束归约为 `true`。
- - - 如果 `n > 0`，约束归约为一组子类型约束：对于所有的 `i (1 ≤ i ≤ m)`，如果 `Xᵢ` 不是 `throws` 子句中任何具体类型的子类型，则约束包含所有的 `j (1 ≤ j ≤ n)` 的 `Xᵢ <: Eⱼ`。

形式为 `⟨MethodReference → throws T⟩` 的约束公式按如下方式归约：

- - 如果 `T` 不是函数接口类型（§9.8），约束归约为 `false`。
- - 否则，按照 §15.27.3 规定确定方法引用的目标函数类型。如果找不到有效的函数类型，约束归约为 `false`。
- - 否则，如果该方法引用是隐式类型化的，且函数的参数类型中有一个或多个不是具体类型，约束归约为 `false`。

> 这种情况由于 §18.5.2.2 中对目标类型应用的替换，在实践中永远不会出现。

- - 否则，如果函数类型的返回类型既不是 `void` 也不是具体类型，约束归约为 `false`。

> 这种情况由于 §18.5.2.2 中对目标类型应用的替换，在实践中永远不会出现。

- - 否则，令 `E₁, ..., Eₙ` 为函数类型 `throws` 子句中不是具体类型的类型。如果方法引用是隐式类型化的，令其参数类型为函数的参数类型。如果方法引用体是一个包含多类型结果的表达式或块，令目标返回类型为函数的返回类型。令 `X₁, ..., Xₘ` 为方法引用体可以抛出的检举异常类型（§11.2）。此时有两种情况：

- - - 如果 `n = 0`（函数的 `throws` 子句仅包含具体类型），则如果存在 `i (1 ≤ i ≤ m)` 使得 `Xᵢ` 不是 `throws` 子句中任何具体类型的子类型，则约束归约为 `false`；否则，约束归约为 `true`。
- - - 如果 `n > 0`，约束归约为一组子类型约束：对于所有的 `i (1 ≤ i ≤ m)`，如果 `Xᵢ` 不是 `throws` 子句中任何具体类型的子类型，则约束包含所有的 `j (1 ≤ j ≤ n)` 的 `Xᵢ <: Eⱼ`。

## 18.3 合并

在推断过程中，随着边界的产生和增长，可能根据原始边界的断言推导出新的边界。合并过程识别这些新边界并将其添加到边界集中。

合并可能发生在两种场景。一种场景是边界集包含了互补边界对；这产生了新的约束公式，如 §18.3.1 所示。另一种场景是边界集包含了涉及捕获转换的边界；这产生了新的边界并可能产生新的约束公式，如 §18.3.2 所示。在两种情况下，任何新的约束公式都会被归约，任何新边界都会被添加到边界集中。这可能会触发进一步的合并；最终集合将达到不动点且无法推导出更多边界。

如果边界集的合并已达到不动点，且该集合不包含边界 `false`，则该边界集具有以下属性：

- 对于推断变量的每一个具体下界 `L` 和具体上界 `U`，`L <: U`。

- 给定依赖关系 `α = β`，`α` 的每一个界都匹配 `β` 的一个界，反之亦然。
- 给定依赖关系 `α <: β`，`α` 的每一个下界都是 `β` 的下界，且 `β` 的每一个上界都是 `α` 的上界。
- 在归约子类型约束时（§18.2.3），不会生成新的捕获变量。
- 不追求扩展的继承路径。

关于合并能够达到固定点的断言略微简化了问题。基于 Kennedy 和 Pierce 的工作——*论变性命名子类型的可判定性*（On Decidability of Nominal Subtyping of Variance），该属性可以通过证明界中可能出现的类型集合是有限的来证明。该论证依赖于两个假设：

该规范目前尚未保证这些属性（它在归约子类型约束时对通配符的处理是不精确的，且没有检测扩展的继承路径），但在未来的版本中可能会这样做。（这不是一个新问题：Java 的子类型算法存在不终止的风险）。

### 18.3.1 界的互补对

在本节中，`S` 和 `T` 是推断变量或类型，而 `U` 是普通类型。为了方便，形式为 `α = T` 的界也可以匹配形式为 `T = α` 的界。

当界集包含的一对匹配以下规则之一的界时，将蕴含一个新的约束公式：

- `α = S` 和 `α = T` 蕴含 `⟨S <: T⟩`
- `α = S` 和 `α <: T` 蕴含 `⟨S <: T⟩`
- `α = S` 和 `T <: α` 蕴含 `⟨T <: S⟩`
- `S <: α` 和 `α <: T` 蕴含 `⟨S <: T⟩`
- `α = U` 和 `S = T` 蕴含 `⟨S[α:=U] = T[α:=U]⟩`
- `α = U` 和 `S <: T` 蕴含 `⟨S[α:=U] <: T[α:=U]⟩`

当界集包含一对界 `α <: S` 和 `α <: T` 时，如果对于所有 `i` (`1 ≤ i ≤ n`)，当 `Sᵢ` 和 `Tᵢ` 为类型（而非通配符）时，约束公式 `Sᵢ = Tᵢ` 是隐含的，则存在一个形式为 `G<S₁, ..., Sₙ>` 的 `S` 的上类型和一个形式为 `G<T₁, ..., Tₙ>` 的 `T` 的上类型（对于某个泛型类或接口 `G`）。

### 18.3.2 涉及捕获转换的界

当边界集包含形式为 `G<α₁, ..., αₙ> = capture(G<A₁, ..., Aₙ>)` 的界时，如果符合以下条件，则隐含新的界并可能隐含新的约束公式。

设 `P₁, ..., Pₙ` 代表 `G` 的类型参数，`B₁, ..., Bₙ` 代表这些类型参数的界。设 `θ` 代表替换 `[P₁:=α₁, ..., Pₙ:=αₙ]`。设 `R` 是一个不是推断变量的类型（但一定是普通类型）。

根据 §18.1.3 的规定，从 `P₁, ..., Pₙ` 的声明界中隐含一组关于 `α₁, ..., αₙ` 的界集。
此外，对于所有 `i` (`1 ≤ i ≤ n`)：

- 如果 `Aᵢ` 不是通配符，则隐含界 `αᵢ = Aᵢ`。
- 如果 `Aᵢ` 是形式为 `?` 的通配符：
    - `αᵢ = R` 隐含界 `false`
    - `αᵢ <: R` 隐含约束公式 `⟨Bᵢθ <: R⟩`
    - `R <: αᵢ` 隐含界 `false`
- 如果 `Aᵢ` 是形式为 `extends T` 的通配符：
    - `αᵢ = R` 隐含界 `false`
    - 如果 `Bᵢ` 是 `Object`，则 `αᵢ <: R` 隐含约束公式 `⟨T <: R⟩`
    - 如果 `T` 是 `Object`，则 `αᵢ <: R` 隐含约束公式 `⟨Bᵢθ <: R⟩`
    - `R <: αᵢ` 隐含界 `false`
- 如果 `Aᵢ` 是形式为 `super T` 的通配符：
    - `αᵢ = R` 隐含界 `false`
    - `αᵢ <: R` 隐含约束公式 `⟨Bᵢθ <: R⟩`
    - `R <: αᵢ` 隐含约束公式 `⟨R <: T⟩`

## 18.4 解析

给定一个不包含界 `false` 的界集，该界集提到的推断变量的子集可能被解析。这意味着可能会为每个推断变量向集中添加一个满意的实例化，直到所有请求的变量都有实例化。

界集中的依赖关系可能要求按照特定顺序解析变量，或者解析额外的变量。依赖关系指定如下：

- 给定以下形式之一的界，其中 `τ` 是推断变量 `β` 或提到 `β` 的类型：
    - `α = τ`
    - `α <: τ`
    - `τ = α`
    - `τ <: α`

如果 `α` 出现在另一个形式为 `G<..., α, ...> = capture(G<..., ...>)` 的界的左侧，则 `β` 依赖于 `α` 的解析。否则，`α` 依赖于 `β` 的解析。

- 推断变量 `α` 出现在形式为 `G<..., α, ...> = capture(G<..., ...>)` 的界的左侧，依赖于其中所有其他推断变量的解析。
- 推断变量 `α` 依赖于推断变量 `β` 的解析，如果存在一个推断变量 `γ`，使得 `α` 依赖于 `γ` 的解析且 `γ` 依赖于 `β` 的解析。
- 推断变量 `α` 依赖于自身的解析。

给定一组需要解析的推断变量，`U` 为该集合以及依赖集合中至少一个变量解析的所有变量的并集。

如果 `U` 中的每个变量都有实例化，则解析成功。
否则，设 `{α₁, ..., αₙ}` 为 `U` 的非空子集，使得 (i) 对于所有 `i` (`1 ≤ i ≤ n`)，`αᵢ` 依赖于某个尚未实例化的变量 `β` 的解析，且 (ii) 存在 `j` 使得 `αᵢ` 依赖于 `αⱼ` 的解析。

# 类型推断

## 推断的用途

实例化推断变量的第一种方法是从变量的边界推导出实例化结果。然而，有时复杂的依赖关系意味着结果不在变量的边界之内。在这种情况下，将执行一种不同的实例化方法，类似于类型捕获（§5.1.10）：引入新的类型变量，其边界由推断变量的边界推导得出。请注意，“捕获”变量的下界是仅使用适当的类型计算的：这对于避免尝试对未实例化的类型变量进行计算至关重要。

## 18.5 推断的用途

使用上述定义的推断过程，在编译时执行以下分析。

### 18.5.1 调用适用性推断

给定一个未提供显式类型参数的方法调用，确定一个潜在泛型方法 `m` 是否适用的过程如下：

- 其中 `P₁, …, Pₚ` (`p ≥ 1`) 是 `m` 的类型参数，令 `α₁, …, αₚ` 为推断变量，并令 `θ` 为替换 `[P₁:=α₁, …, Pₚ:=αₚ]`。

- 根据 §18.1.3 的描述，从 `P₁, …, Pₚ` 的声明边界生成初始边界集 `B₀`。

- 对于所有的 `i` (`1 ≤ i ≤ p`)，如果 `Pᵢ` 出现在 `m` 的 `throws` 子句中，则隐含边界 `throws αᵢ`。这些边界（如果有）与 `B₀` 合并产生一个新的边界集 `B₁`。

- 如下生成一组约束公式集合 `C`。

令 `F₁, …, Fₙ` 为 `m` 的形式参数类型，令 `e₁, …, eₖ` 为调用的实际参数表达式。那么：

- 通过严格调用测试适用性：

如果 `k ≠ n`，或者存在一个 `i` (`1 ≤ i ≤ n`) 使得 `eᵢ` 与适用性相关（§15.2.2.2）且 (i) `eᵢ` 是基本类型 `Fᵢ` 的独立表达式，或者 (ii) `Fᵢ` 是基本类型但 `eᵢ` 不是基本类型的独立表达式；则该方法不适用，且不需要继续推断。

否则，`C` 包含对于所有 `eᵢ` 与适用性相关的 `i` (`1 ≤ i ≤ k`)，其映射结果为 `eᵢ → Fᵢθ`。

- 通过松散调用测试适用性：

如果 `k ≠ n`，该方法不适用，且不需要继续推断。

否则，`C` 包含对于所有 `eᵢ` 与适用性相关的 `i` (`1 ≤ i ≤ k`)，其结果为 `eᵢ → Fᵢθ`。

- 通过可变长度调用测试适用性：

令 `F'₁, …, F'ₖ` 为 `m` 的第一个可变长度参数类型（§15.12.2.4）。`C` 包含对于所有 `eᵢ` 与适用性相关的 `i` (`1 ≤ i ≤ k`)，其结果为 `eᵢ → F'ᵢθ`。

- `C` 被归约（§18.2），生成的边界与 `B₁` 合并产生一个新的边界集 `B₂`。

- 最后，如果 `B₂` 不包含边界 `false` 且 `B₂` 中所有推断变量的解析成功（§18.4），则该方法 `m` 是适用的。

考虑以下方法调用和赋值：

```
```



# 类型推断

## 推断的用途 18.5

```java
List<Number> ln = Arrays.asList(1, 2.0);
```

必须根据 `§15.12` 的描述识别出调用的特定适用方法。唯一潜在适用的方法 (`§15.12.2.1`) 声明如下：

```java
public static <T> List<T> asList(T... a)
```

显而易见（由于长度的原因），该方法既不通过严格调用 (`§15.12.2.2`)，也不通过松散调用 (`§15.12.2.3`)。但由于没有其他候选方法，在第三阶段将检查该方法通过可变长度调用的适用性。

初始边界集 $B_i$ 是单个推断变量 $\alpha$ 的平凡上界：

```
{ α <: Object }
```

初始约束公式集如下：

```
{ <1 → α, <2.0 → α> }
```

这些被归约为一个新的边界集 $B_i$；

然后，为了测试该方法是否适用，我们尝试解析这些边界。我们成功了，产生了读者所需的复杂实例化：

```
{ α <: Object, Integer <: α, Double <: α }
```

```
α = Number & Comparable<? extends Number & Comparable<?>>
```

我们已经证明了该方法是适用的；由于没有其他候选方法，它是最适用的。

为了完成方法调用的类型检查，我们必须确定它是否与目标类型 `List<Number>` 兼容。

在上一节中，用于证明适用性的边界 $B_2$ 为：

```
{ α <: Object, Integer <: α, Double <: α }
```

新的约束公式集如下：

```
{ List<α> → List<Number> }
```

该兼容性约束为 $\alpha$ 产生了一个等值边界，该边界包含在新的边界集 $B_3$ 中：

```
{ α <: Object, Integer <: α, α = Number }
```

这些边界可以被显易解决：

```
α = Number
```

最后，我们对 `asList` 的声明返回类型进行替换，以确定该方法调用具有 `List<Number>`；显然，这与目标类型兼容的。

这种推理策略与 Java SE 7 版的《Java 语言规范》（The *Java Language Specification*）不同，后者会像我们在上一节中所做的那样，根据其下界（在考虑调用的目标类型之前）来实例化 $\alpha$。这将导致类型错误，因为结果类型不是 `List<Number>` 的子类型。

在各种特殊情况下，根据 $B_2$ 中出现的边界，我们尽早解析一个表现为调用返回类型的实例。这样做是为了避免通常的约束 $\theta \rightarrow$ 不保持完备性的不幸情况。遗憾的是，通过尽早解析变量，我们无法利用本可以推导出的边界。在某些情况下，如果从调用表达式（从而包含隐式 lambda 表达式）推导出的边界存在于 $B_2$ 中，可能会导致不同的结果。尽管有这些限制，该策略在典型用例中仍允许得到合理的结果，并且与 Java SE 7 版的《Java 语言规范》中的算法向后兼容。

## 18.5.2.2 额外参数约束

所选方法的调用类型在考虑了由方法调用表达式参数表达式可能隐含的额外约束后确定，如下：

- 如果方法调用表达式是一个多态表达式（poly expression），令 $B_j$ 为 `§18.5.2.1` 中生成的边界集，用于证明与方法调用的实际目标类型兼容。
- 如果方法调用表达式不是多态表达式，令 $B_j$ 为通过归约产生的相同边界集，用于证明 $m$ 在 `§18.5.1` 中适用。

（虽然在 `§18.5.1` 和 `§18.5.2.1` 中必须证明边界集中的推理变量是可以解析的，但这些解析步骤产生的实例化不视为 $B_j$ 的部分。）

- 约束公式集 $C$ 的生成如下。

令 $e_j, ..., e_k$ 为方法调用表达式的实际表达式。

如果 $m$ 通过严格或松散调用适用，令 $F_j, ..., F_k$ 为 $m$ 的形式参数类型；如果 $m$ 通过变长参数调用适用，令 $F'_j, ..., F'_k$ 为 $m$ 的前 $k$ 个变长参数的类型（`§18.5.12.4`）。

令 $\Theta$ 为 `§18.5.1` 中定义的替换 $[P_i :=\alpha_i, ..., P_j :=\alpha_j]$，用于将 $m$ 的类型参数替换为推理变量。

那么，对于所有 $i$ ($1 \le i \le k$)：

- 如果 $e_i$ 与适用性无关
- 根据 $e_i$ 的形式，可能包含额外的约束：
    - 如果 $e_i$ 是一个 `LambdaExpression`，$C$ 包含 `LambdaExpression → throws F_iΘ`，并在 lambda 体中搜索额外的约束：
        - 对于块状 lambda 体，搜索递归地应用于其每一个结果表达式上。
        - 对于多态类实例创建表达式或多态方法调用表达式，$C$ 包含在 `§18.5.2` 在推导多态表达式的调用类型时生成的集合 $c$ 中出现的所有约束公式。
    - 对于括号表达式，搜索递归地应用于包含的表达式上。
    - 对于条件表达式，搜索递归地应用于第二个和第三操作数上。
    - 对于 lambda 表达式，搜索递归地应用于 lambda 体上。
    - 对于 switch 表达式，搜索递归地应用于其每一个结果表达式上。

- 如果 $e_i$ 是一个 `MethodReference`，$c$ 包含 `MethodReference → F_iθ`。

- 如果 $e_i$ 是多态类创建表达式或多态方法调用表达式，$c$ 包含在 `§18.5.2` 在推导多态表达式的调用类型时生成的集合 $c$ 中出现的所有约束公式。

- 如果 $e_i$ 是括号表达式，这些规则递归地应用于包含的表达式上。

- 如果 $e_i$ 是条件表达式，这些规则递归地应用于第二个和第三操作数上。

- 如果 $e_i$ 是 switch 表达式，这些规则递归地应用于其每一个结果表达式上。

- 当 $c$ 不空时，重复以下过程，从边界 $B_i$ 开始并将新边界累积到当前边界集中：

    1. 从 $c$ 中选择一个约束子集，满足以下属性：没有输入变量可以影响另一个约束的输出变量。输入变量和输出变量的术语定义在文所示。如果推理变量 $\alpha$ 依赖于推理变量 $\beta$ (`§3.4`)，则 $\alpha$ 可以影响推理变量 $\beta$，或者存在推理变量 $\gamma$ 使得 $\alpha$ 可以影响 $\gamma$ 且 $\gamma$ 可以影响 $\beta$。

如果该子集为空，则在依赖图中存在循环（cycles）。在这种情况下，考虑 $c$ 中参与依赖循环（cycles）且不依赖于循环（cycles）之外任何约束的约束。从这些被考虑的约束中选择一个约束，如下：

- 如果任何一个被考虑的约束具有 `<Expression → T>` 形式，则所选约束是这些约束中此类形式的一个，且包含了所有具有此类形式的约束左侧的表达式。
- 如果没有被考虑的约束具有 `<Expression → T>` 形式，则所选约束为第一个。

2. 解析所有所选约束的输入变量 $\alpha_1, ..., \alpha_n$。

3. 如果 $T_1, ..., T_n$ 是 $\alpha_1, ..., \alpha_n$ 的实例化，则替换 $[\alpha_j:=T_j; ..., \alpha_n=T_n]$ 应用于每一个循环。

4. 将替换产生的约束归约并合并到当前边界集中。

5. 最后，如果 $B_4$ 不空，则解析 $B_4$ 中的边界变量。

如果推理变量 $\alpha_1, ..., \alpha_n$ 成功实例化为 $[T_1, ..., T_n]$，令 $\theta'$ 为替换 $[P_j:=T_j; ..., P_n=T_n]$。那么：

- 如果在 `§18.5.1` 的约束集归约过程中，方法的适用不需要检查转换，则 $m$ 调用的参数类型通过 $\theta'$ 应用于 $m$ 类型的参数类型获得，且调用类型的返回类型和抛出类型由 $m$ 类型的返回类型和抛出类型的擦除给出。
- 如果方法的适用不需要检查转换，则 $m$ 的调用类型通过 $\theta'$ 应用于 $m$ 的类型获得。

如果 $B_4$ 包含边界 `false`，或者解析失败，则发生编译错误。

归约额外参数约束的过程可能需要仔细地排序 `<Expression → T>`、`<LambdaExpression →throws T>` 和 `<MethodReference →throws T>` 形式的约束公式。为了便于这种排序，这些约束的输入变量定义如下：

### 输入变量定义

- 对于 `LambdaExpression → τ`：
    - 如果 $\tau$ 是推断变量，则它是（唯一的）输入变量。
    - 如果 $\tau$ 是函数式接口类型，且可以从 $\tau$ 推导出一个函数类型 (`§15.27.3`)，则输入变量包括：(i) 如果 lambda 表达式是隐式类型指定的，则函数类型参数类型中提到的推断变量；以及 (ii) 如果函数类型的返回类型 $\mathcal{R}$ 不是 `void`，则对于 lambda 体中的每个结果表达式 $e$（或者如果体本身是一个表达式的话），`⟨e → ℛ⟩` 的输入变量。
    - 否则，没有输入变量。

- 对于 `LambdaExpression → throws τ`：
    - 如果 $\tau$ 是推断变量，则它是（唯一的）输入变量。
    - 如果 $\tau$ 是函数式接口类型，并且可以像 `§15.27.3` 描述的那样推导出函数类型，则输入变量包括：(i) 如果 lambda 表达式是隐式类型指定的，则函数类型参数类型中提到的推断变量；以及 (ii) 函数类型返回类型中提到的推断变量。
    - 否则，没有输入变量。

- 对于 `MethodReference → τ`：
    - 如果 $\tau$ 是推断变量，则它是（唯一的）输入变量。
    - 如果 $\tau$ 是带有函数类型的函数式接口类型，且该方法引用是不精确的 `§15.13.1`，则输入变量是函数类型参数类型中提到的推断变量。
    - 否则，没有输入变量。

- 对于 `MethodReference → throws τ`：
    - 如果 $\tau$ 是推断变量，则它是（唯一的）输入变量。
    - 如果 $\tau$ 是带有函数类型的函数式接口类型，且该方法引用是不精确的 `§15.13.1`，则输入变量是函数类型参数类型和函数类型返回类型的推断变量。
    - 否则，没有输入变量。

- 对于 `Expression → τ`，如果 $Expression$ 是一个括号表达式：
    - 当 $Expression$ 包含的表达式为 $Expression'$ 时，输入变量是 `⟨Expression → τ⟩` 的输入变量。

- 对于 `<ConditionalExpression → T`：
    - 当条件表达式的形式为 $e_1 ? e_2 : e_3$ 时，输入变量为 `⟨e_2 → T⟩` 和 `⟨e_3 → T⟩`。

- 对于 `<SwitchExpression → T`：
    - 当 switch 结果表达式为 $e_1, ..., e_n$ 时，输入变量为所有 $i$ ($1 \le i \le n$) `⟨e_j → T⟩` 的输入变量。

- 对于所有其他约束公式，没有输入变量。

## 18.5.3 函数式接口参数化推断

当一个具有显式参数类型 $P_1, ..., P_n$ 的 lambda 表达式目标是一个带有至少一个通配符参数的函数类型 $F<A_1, ..., A_m>$ 时，可以按照如下方式推导出 $F$ 的参数化作为该 lambda 表达式的基类型。

令 $Q_j, ..., Q_m$ 为类型 $F<\alpha_j, ..., \alpha_m>$ 的函数参数，其中 $\alpha_j, ..., \alpha_m$ 是新的接口变量。

如果 $n \neq k$，则不存在有效的参数化。否则，形成一组约束公式，其中对于所有 $i$ ($1 \le i \le n$) `⟨P_i = Q_i⟩`。该约束公式被归约形成边界 $B$。

如果 $b$ 包含边界 `false`，则不存在有效的参数化。否则，按照如下方式构造函数式接口类型 $F<A'_1, ..., A'_m>$，对于 $1 \le i \le m$：

- 如果 $B$ 包含对 $\alpha_i$ 的实例化 (18.1.3)，则 $A'_i = T$。
- 否则，$A'_i = A_i$。

如果 $A'_1, ..., A'_m$ 不是一个良好的类型（即参数不在其边界范围内），或者 $F<A'_1, ..., A'_m>$ 不是 $A_m$ 的子类型，则不存在有效的参数化。推断出的参数化是以下情况：如果所有参数都是类型，则为 $F<A'_1, ..., A'_m>$；如果一个或多个类型参数仍是通配符，则为 $F<A'_1, ..., A'_m>$ 的非通配符参数化 (9.9)。

为了确定通配符参数化函数式接口的类型，我们必须用特定类型“实例化”通配符类型参数。“默认”方法是将通配符替换为它们的边界，如 `§9.8` 所示，但在 lambda 表达式的显式参数类型与通配符边界对应的情况下，这将产生伪错误。例如：

```java
Predicate<? super Integer> p = (Number n) -> n.equals(n);
```

该 lambda 表达式是 `Predicate<Number>`，它是 `Predicate<? super Integer>` 的子类型。尽管如此，这里的分析虽然是用类型推断来描述的，但是有意简化的。更强大的策略可能会从等性约束中推断，但这将引入很多复杂性。

## 18.5.4 更具体的推断

在测试一个方法是否比另一个更具体时，需要测试一个方法是否比另一个更具体。令 $m_1$ 为第一个方法，$m_2$ 为第二个方法。当 $m_2$ 有类型参数 $P_1, ..., P_n$ 时，令 $\alpha_1, ..., \alpha_p$ 为推断变量，并 $\theta$ 为替换 $[P_1:\alpha_1, ..., P_n:\alpha_p]$。

令 $e_1, ..., e_k$ 为表达式。那么：

- 如果 $m_1$ 和 $m_2$ 是可用的 (`§15.12.2`)，则 $S_1, ..., S_k$ 为 $m_1$ 的参数类型。
- 如果 $m_2$ 是可用的 (`§15.12.3`)，则 $T_1, ..., T_k$ 为 $\theta$ 应用于参数类型的结果。

确定 $m_1$ 比 $m_2$ 更具体的过程如下：

- 首先，根据 $P_1, ..., P_n$ 生成一个初始边界 $B$，见 18.1.3。
- 第二，对于所有 $i$ ($1 \le i \le k$) 生成一组约束公式或边界。

如果 $T_i$ 是具体类型，则如果 $S_i$ 比 $T_i$ 更具体 (`§15.12.5`)，结果为真，否则为假（注意 $S_i$ 总是具体类型）。

否则，如果 $S_i$ 和 $T_i$ 都不是函数类型，则生成约束公式 $S_i < T_i$。

否则，如果 $S_i$ 的接口是 $T_i$ 接口的超接口（或者当 $T_i$ 是交类型时，$S_i$ 的某个接口是 $T_i$ 的超接口），则生成约束公式 $S_i < T_i$。

否则，令 $MT_{S_i}$ 为 $S_i$ 的函数类型，$MT_{T_i}$ 为 $T_i$ 的函数类型。如果 $MT_{S_i}$ 和 $MT_{T_i}$ 的形式参数数量或类型参数数量不同，或者类型参数相同但但不具有相同的类型参数 (`§8.4.4`)，则结果为假。否则，根据 $MT_{S_i}$ 和 $MT_{T_i}$ 的类型参数、参数类型和返回类型生成以下约束公式或边界：

- 令 $A_1, ..., A_n$ 为 $MT_{S_i}$ 的类型参数，$B_1, ..., B_n$ 为 $MT_{T_i}$ 的类型参数。令 $\theta'$ 为替换 $[B_1:=A_1, ..., B_n:=A_n]$。那么，对于所有 $j$ ($1 \le j \le n$)：
    - 如果 $A_j$ 的边界提到了 $A_1, ..., A_n$ 之一且 $B_j$ 的边界不是具体类型，则为假。
    - 否则，其中 $x$ 是 $A_j$ 的边界，$y$ 是 $B_j$ 的边界，`⟨X = y θ'⟩`。

简化并不是保持完备性的（相同的注释也适用于下方对形式参数类型和返回类型的处理）。

- 令 $U_1, ..., U_k$ 为 $MT_S$ 的形式参数类型，令 $V_1, ..., V_k$ 为 $MT_T$ 的形式参数类型。那么，对于所有的 $j$ ($1 \le j \le k$)：
    > 如果 $U_j$ 提到了 $A_{i_1}, ..., A_{i_n}$ 中的一个且 $V_j$ 不是适当类型，则为 `false`。
    > 否则，如果 $V_j \le U'_j$，且 $U'_1, ..., U'_k$ 是 $MT'_S$ 的形式参数类型，$A'_{i_1}, ..., A'_{i_n}$ 是 $MT'_S$ 的类型参数，则 `⟨V_j[B_1:=A'_{i_1}, ..., B_n:=A'_{i_n}] = U'_j⟩`。



- 令 $R_S$ 为 $MT_S$ 的返回类型，$R_T$ 为 $MT_T$ 的返回类型。那么：

  > 如果 $R_S$ 且 $e_j$ 是显式类型的 lambda 表达式，且 $R_T$ 不是适当类型，则为 `false`。

  > 如果 $R_T$ 为 `void`，则为 `true`。

  > 否则，如果 $R_S$ 和 $R_T$ 是函数接口类型，且 $e_j$ 至少有一个结果表达式，则对于 $e_j$ 中的每个结果表达式，重复整个第二个步骤，以推导出在给定结果表达式下 $R_S$ 比 $R_T$ 更具体的约束条件。

- 否则，如果 $R_S$ 是基本类型而 $R_T$ 不是，且 $e_i$ 至少有一个结果表达式，且 $e_i$ 的每个结果表达式都是基本类型的独立表达式（§15.2)，则为 `true`。

- 否则，如果 $R_T$ 是基本类型而 $R_S$ 不是，且 $e_j$ 至少有一个结果表达式，且 $e_i$ 的每个结果表达式都是引用类型或多项表达式的独立表达式，则为 `true`。

- 否则，$<R_S <: R_T \theta$。

- 否则，如果 $e_i$ 是精确方法引用：

  - $R_T$ 为 void，为 `true`。

  - 否则，如果 $R_S$ 是基本类型而 $R_T$ 不是，且 $e_i$ 的编译时声明有返回类型，则为 `true`。

  - 否则，如果 $R_S$ 是基本类型且 $R_S$ 不是（注：此处原文可能有误），且 $e_i$ 的编译时声明有引用类型，则为 `true`。

  - 否则，$R_S <: R_T \theta$。

- 否则，如果 $e_i$ 是带括号表达式，则这些由 $R_S$ 和 $R_T$ 导出的约束规则将递归地应用于包含的表达式。

- 否则，如果 $e_i$ 是条件表达式，则这些由 $R_S$ 和 $R_T$ 导出的约束规则将递归地应用于第二个和第三个操作数中的每一个。

- 否则，如果 $e_i$ 是 switch 表达式，则这些由 $R_S$ 和 $R_T$ 导出的约束规则将递归地应用于其每个结果表达式。

- 否则，为 `false`。

- 第三，如果 $m_2$ 是由任意变量调用且具有 $k+1$ 个参数指定的，那么 $S_{k+1}$ 是 $m_1$ 的 $k+1$ 变量数组参数类型，$T_{k+1}$ 是 $\theta$ 应用于 $m_2$ 的 $k+1$ 变量数组参数类型的结果，则生成约束 $<S_{k+1} <: T_{k+1}$。

- 第四，生成的边界和约束公式被归并与 $B$ 结合，以产生边界集 $B'$。

- 如果 $B'$ 不包含边界 $false$，且 $B'$ 中所有推断变量的解析成功，则 $m_1$ 比 $m_2$ 更具体。否则，$m_1$ 不比 $m_2$ 更具体。

## 推断的用途

## 第 19 章 语法

本章重复了第 4、6-10、14 和 15 章给出的语法法，以及第 3 章词法语法的部分，并使用了 §2.4 中的符号。

### 来自 §3（词法结构）的产生式

- `Identifier`: `IdentifierChars` 不是 `Keyword` 或 `BooleanLiteral` 或 `NullLiteral`
- `IdentifierChars`: `JavaLetter` [`JavaLetterDigit`]
- `JavaLetter`: 任意作为 "Java letter" 的 Unicode 字符
- `JavaLetterDigit`: 任意作为 "Java letter-digit" 的 Unicode 字符
- `TypeError`: `Identifier` 不是 `var`
- `UnqualifiedMethodIdentifier`: `Identifier` 不是 `var`
- `Literal`: `IntegerLiteral`, `FloatingPointLiteral`, `BooleanLiteral`, `CharacterLiteral`, `NullLiteral`

### 来自 §4（类型、值和变量）的产生式

- `Type`: `PrimitiveType` | `ReferenceType`
- `PrimitiveType`: [`Annotation`] `NumericType` [`Annotation`] `boolean`
- `NumericType`: `IntegralType`, `FloatingPointType`
- `IntegralType`: (以下之一) `byte` `short` `char`
- `FloatingPointType`: (以下之一) `float` `double`
- `ReferenceType`: `ClassOrInterfaceType`, `TypeVariable`, `ArrayType`
- `ClassOrInterfaceType`: `ClassType`, `InterfaceType`
- `ClassType`: [`Annotation`] `Identifier` [`TypeArguments`]
- `PackageName`: [`Annotation`] `Identifier` [`TypeArguments`]
- `ClassOrInterfaceType`: [`Annotation`] `Identifier` [`TypeArguments`]
- `InterfaceType`: `ClassType`
- `TypeVariable`: [`Annotation`] `Identifier`
- `ArrayType`: `PrimitiveType` `Dims` | `ClassOrInterfaceType` `Dims` | `TypeVariable` `Dims`
- `Dims`: [`Annotation`] `[]`
- `TypeParameter`: [`TypeParameterModifier`] `Identifier` [`TypeBound`]
- `TypeParameterModifier`: `Annotation`
- `TypeBound`: `extends` `TypeVariable` `ClassOrInterfaceType` [`AdditionalBound`]
- `AdditionalBound`: `InterfaceType`
- `TypeArguments`: `<` `TypeArgumentList` `>`
- `TypeArgumentList`: `TypeArgument` (, `TypeArgument`)
- `TypeArgument`: `ReferenceType` `Wildcard`
- `Wildcard`: [`Annotation`] [`WildcardBounds`]
- `WildcardBounds`: `extends` `ReferenceType` `superType`

### 来自 §6（名称）的产生式

- `ModuleName`: `Identifier` `ModuleName` `Identifier`
- `PackageName`: `Identifier` `PackageName` `Identifier`
- `TypeName`: `TypeIdentifier` `PackageTypeName` `Identifier`
- `ExpressionName`: `Identifier` `AmbiguousName` `Identifier`
- `MethodName`: `UnqualifiedMethodIdentifier`
- `PackageTypeName`: `Identifier` `PackageTypeName` `Identifier`
- `AmbiguousName`: `Identifier` `AmbiguousName` `Identifier`

### 来自 §7（包和模块）的产生式

- `CompilationUnit`: `OrdinaryCompilationUnit` `ModularCompilationUnit`
- `OrdinaryCompilationUnit`: [`PackageDeclaration`] [`ImportDeclaration`] [`TypeDeclaration`]
- `ModularCompilationUnit`: [`ImportDeclaration`] `ModuleDeclaration`
- `PackageDeclaration`: [`PackageModifier`] `package` `Identifier` (`Identifier`);
- `PackageModifier`: `Annotation`
- `ImportDeclaration`: `SingleTypeImportDeclaration` `TypeImportOnDemandDeclaration` `SingleStaticImportDeclaration` `StaticImportOnDemandDeclaration`
- `SingleTypeImportDeclaration`: `import` `TypeName`;
- `TypeImportOnDemandDeclaration`: `import` `PackageTypeName` `.*`;
- `SingleStaticImportDeclaration`: `import` `static` `TypeName` `.` `Identifier`;
- `StaticImportOnDemandDeclaration`: `import` `static` `TypeName` `.*`;
- `TypeDeclaration`: `ClassDeclaration` `InterfaceDeclaration`;
- `ModuleDeclaration`: [`Annotation`] [`open`] `module` `Identifier` { `ModuleDirective` }
- `ModuleDirective`: `requires` [`RequiresModifier`] `ModuleName`; `exports` `PackageName` [`to` `ModuleName`, `ModuleName`]; `opens` `PackageName` [`to` `ModuleName`, `ModuleName`]; `uses` `TypeName`; `provides` `TypeName` `with` `TypeName` (`TypeName`);
- `RequiresModifier`: (以下之一) `transitive` `static`

### 来自 §8（类）的产生式

- `ClassDeclaration`: `NormalClassDeclaration` | `EnumDeclaration`
- `NormalClassDeclaration`: [`ClassModifier`] `class` `Identifier` [`TypeParameters`] [`Superclass`] [`Superinterfaces`] `ClassBody`
- `ClassModifier`: (以下之一) `Annotation` `public` `protected` `private` `abstract` `static` `final` `strictfp`
- `TypeParameters`: `<` `TypeParameterList` `>`
- `ParameterList`: `TypeParameter` (, `TypeParameter`)
- `Superclass`: `extends` `ClassType`
- `Superinterfaces`: `implements` `InterfaceTypeList`
- `InterfaceTypeList`: `InterfaceType` (, `InterfaceType`)
- `ClassBody`: { `ClassBodyDeclaration` }
- `ClassBodyDeclaration`: `ClassMemberDeclaration` `InstanceInitializer` `StaticInitializer` `ConstructorDeclaration`
- `ClassMemberDeclaration`: `FieldDeclaration` `MethodDeclaration` `ClassDeclaration` `InterfaceDeclaration`;
- `FieldDeclaration`: {`FieldModifier`} `UnannType` `VariableDeclaratorList`;
- `FieldModifier`: (以下之一) `Annotation` `public` `protected` `private` `static` `final` `transient` `volatile`
- `VariableDeclaratorList`: `VariableDeclarator` ( , `VariableDeclarator`)
- `VariableDeclarator`: `VariableDeclaratorId` [= `VariableInitializer`]
- `VariableDeclaratorId`: `Identifier` [`Dims`]
- `VariableInitializer`: `Expression` | `ArrayInitializer`

```
UnannType:
UnannPrimitiveType
UnannReferenceType
```

```
UnannPrimitiveType:
NumericType
boolean
```

```
UnannReferenceType:
UnannClassOrInterfaceType
UnannTypeVariable
UnannArray
```

```
UnannClassOrInterfaceType:
UnannClassType
UnannInterfaceType
```

```
UnannClassType:
TypeIdentifier [TypeArguments]
PackageName . [Annotation] TypeIdentifier [TypeArguments]
UnannClassOrInterfaceType . [Annotation] TypeIdentifier
[TypeArguments]
```

```
UnannInterfaceType:
UnannClassType
```

```
UnannTypeVariable:
TypeIdentifier
```

```
UnannArrayType:
UnannPrimitiveType Dims
UnannClassOrInterfaceType Dims
UnannTypeVariable Dims
```

```
MethodDeclaration:
{MethodModifier} MethodHeader MethodBody
```

```
MethodModifier:
(one of)
Annotation public protected private
abstract static final synchronized native strict fp
```

```
MethodHeader:
Result MethodDeclarator [Throws]
TypeParameters [Annotation] Result MethodDeclarator [Throws]
```

```
Result:
UnannType
void
```

```
MethodDeclarator:
Identifier ({ ReceiverParameter , } [FormalParameterList] ) [Dims]
```

```
ReceiverParameter:
[Annotation] UnannType [Identifier .] this
```

```
FormalParameterList:
FormalParameter { , FormalParameter
```

```
FormalParameter:
{VariableModifier} UnannType VariableDeclaratorId
VariableArityParameter
```

```
VariableArityParameter:
{VariableModifier} UnannType [Annotation] ... Identifier
```

```
VariableModifier:
Annotation
final
```

```
Throws:
throws ExceptionTypeList
```

```
ExceptionTypeList:
ExceptionType { , ExceptionType}
```

```
ExceptionType:
ClassType
TypeVariable
```

```
MethodBody:
Block;
```

```
InstanceInitializer:
Block
```

```
StaticInitializer:
static Block
```

```
ConstructorDeclaration:
{ConstructorModifier} ConstructorDeclarator [Throws] ConstructorBody
```

```
ConstructorModifier:
(one of)
Annotation public protected private
```

```
ConstructorDeclarator:
[TypeParameters] SimpleTypeName
([ReceiverParameter , ] [FormalParamList] )
```

```
SimpleTypeName:
TypeIdentifier
```

```
ConstructorBody:
{ [ExplicitConstructorInvocation] [BlockStatements] }
```

```
ExplicitConstructorInvocation:
[TypeArguments] this ([ArgumentList]);
[TypeArguments] super ([ArgumentList]);
ExpressionName . [TypeArguments] super ([ArgumentList]);
Primary . [TypeArguments] super ([ArgumentList]);
```

```
EnumDeclaration:
{ClassModifier} enum TypeIdentifier [Superinterfaces] EnumBody
```



## Enum 定义

```
EnumBody:
{ [EnumConstantList] [, ] [EnumBodyDeclarations] }
```

```
EnumConstantList:
EnumConstant {, EnumConstant}
```

```
EnumConstant:
{EnumConstantModifier} Identifier [ <[ArgumentList> ] ] [ClassBody]
```

```
EnumConstantModifier:
Annotation
```

```
EnumBodyDeclarations:
; [ClassBodyDeclaration]
```

## 来自 §9 (接口) 的产生式

```
InterfaceDeclaration:
NormalInterfaceDeclaration
AnnotationTypeDeclaration
```

```
NormalInterfaceDeclaration:
[InterfaceModifier] interface TypeIdentifier [TypeArguments]
[ExtendsInterfaces] InterfaceBody
```

```
InterfaceModifier:
(one of)
Annotation public protected private
abstract static strictfp
```

```
ExtendsInterfaces:
extends InterfaceTypeList
```

```
InterfaceBody:
{ InterfaceMemberDeclaration }
```

```
InterfaceMemberDeclaration:
ConstantDeclaration
InterfaceMethodDeclaration
ClassDeclaration
InterfaceDeclaration
;
```

```
ConstantDeclaration:
[ConstantModifier] UnannType VariableDeclarList;
```

```
ConstantModifier:
(one of)
Annotation public
static final
```

```
InterfaceMethodDeclaration:
[InterfaceMethodModifier] MethodHeader MethodBody
```

```
InterfaceMethodModifier:
(one of)
Annotation public private
abstract default static strictfp
```

```
AnnotationTypeDeclaration:
[InterfaceModifier] @ interface TypeIdentifier AnnotationTypeBody
```

```
AnnotationTypeBody:
{ AnnotationTypeMemberDeclaration }
```

```
AnnotationTypeMemberDeclaration:
AnnotationTypeElementDeclaration
ConstantDeclaration
InterfaceDeclaration
;
```

```
AnnotationTypeElementDeclaration:
[AnnotationTypeElementModifier] UnannType Identifier ( ) [Dims]
[DefaultValue];
```

```
AnnotationTypeElementModifier:
(one of)
Annotation public
abstract
```

```
DefaultValue:
default ElementValue
```

## 注解语法

```
Annotation:
NormalAnnotation
MarkerAnnotation
SingleElementAnnotation
```

```
NormalAnnotation:
@ TypeName ([ElementValuePairList])
```

```
ElementValuePairList:
ElementPair {, ElementPair}
```

```
ElementPair:
Identifier = ElementValue
```

```
ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation
```

```
ElementValueArrayInitializer:
{ [ElementList] [, ] }
```

```
ElementList:
ElementValue {, ElementValue}
```

```
MarkerAnnotation:
@ TypeName
```

```
SingleElementAnnotation:
@ TypeName ( ElementValue )
```

## 来自 §10 (数组) 的产生式

```
ArrayInitializer:
{ [VariableInitializerList] [, ] }
```

```
VariableInitializerList:
VariableInitializer (, VariableInitializer)
```

## 来自 §14 (块与语句) 的产生式

```
Block:
{ [BlockStatements] }
```

```
BlockStatements:
BlockStatement {BlockStatement}
```

```
BlockStatement:
LocalVariableDeclarationStatement
ClassDeclaration
Statement
```

```
LocalVariableDeclarationStatement:
LocalVariableDeclaration ;
```

```
LocalVariableDeclaration:
{VariableModifier} LocalVariableType VariableDeclaratorList
```

```
LocalVariableType:
UnannType
var
```

```
Statement:
StatementWithoutTrailingSubstatement
LabeledStatement
IfThenStatement
IfThenElseStatement
WhileStatement
ForStatement
```

```
StatementNoShortIf:
StatementWithoutTrailingSubstatement
LabeledStatementNoShortIf
IfThenElseStatementNoShortIf
WhileStatementNoShortIf
ForStatementNoShortIf
```

```
StatementWithoutTrailingSubstatement:
Block
EmptyStatement
ExpressionStatement
AssertStatement
SwitchStatement
DoStatement
BreakStatement
ContinueStatement
ReturnStatement
SynchronizedStatement
ThrowStatement
TryStatement
YieldStatement
```

```
EmptyStatement:
;
```

```
LabeledStatement:
Identifier : Statement
```

```
LabeledStatementNoShortIf:
Identifier : StatementNoShortIf
```

```
ExpressionStatement:
StatementExpression ;
```

```
StatementExpression:
Assignment
PreIncrementExpression
PreDecrementExpression
PostIncrementExpression
PostDecrementExpression
MethodInvocation
ClassInstanceCreation
```

### 条件与循环语句

```
IfThenStatement:
if ( Expression ) Statement
```

```
IfThenElseStatement:
if ( Expression ) StatementNoShortIf else Statement
```

```
IfThenElseStatementNoShortIf:
if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

```
AssertStatement:
assert Expression ;
assert Expression : Expression ;
```

```
SwitchStatement:
switch ( Expression ) SwitchBlock
```

```
SwitchBlock:
{ SwitchRule {SwitchRule} }
{ SwitchBlockStatementGroup } {SwitchLabel :} }
```

```
SwitchRule:
SwitchLabel -> Expression ;
SwitchLabel -> Block
SwitchLabel -> ThrowStatement
```

```
SwitchBlockStatementGroup:
SwitchLabel : {SwitchLabel :} BlockStatements
```

```
SwitchLabel:
case CaseConstant [, CaseConstant]
```

```
CaseConstant:
ConditionalExpression
```

```
WhileStatement:
while ( Expression ) Statement
```

```
WhileStatementNoShortIf:
while ( Expression ) StatementNoShortIf
```

```
DoStatement:
do Statement while ( Expression ) ;
```

```
ForStatement:
BasicForStatement
EnhancedForStatement
```

```
ForStatementNoShortIf:
BasicForStatementNoShortIf
EnhancedForStatementNoShortIf
```

```
BasicForStatement:
for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement
```

```
BasicForStatementNoShortIf:
for ( [ForInit] ; [Expression] ; [ForUpdate] ) StatementNoShortIf
```

```
ForInit:
StatementExpressionList
LocalVariableDeclaration
```

```
ForUpdate:
StatementExpressionList
```

```
StatementExpressionList:
StatementExpression { , StatementExpression }
```

```
EnhancedForStatement:
for ( {VariableModifier} LocalVariableType VariableDeclaratorId : Expression ) Statement
```

```
EnhancedForStatementNoShortIf:
for ( {VariableModifier} LocalVariableType VariableDeclaratorId : Expression ) StatementNoShortIf
```

### 跳转与控制语句

```
BreakStatement:
break [Identifier] ;
```

```
YieldStatement:
yield Expression ;
```

```
ContinueStatement:
continue [Identifier] ;
```

```
ReturnStatement:
return [Expression] ;
```

```
ThrowStatement:
throw Expression ;
```

```
SynchronizedStatement:
synchronized ( Expression ) Block
```

### Try 语句

```
TryStatement:
try Block Catches
try Block [Catches] Finally
TryWithResourcesStatement
```

```
Catches:
CatchClause {CatchClause}
```

```
CatchClause:
catch ( CatchFormalParameter ) Block
```

```
CatchFormalParameter:
{VariableModifier} CatchType VariableDeclaratorId
```

```
CatchType:
UnannClassType | ClassType
```

```
Finally:
finally Block
```

```
TryWithResourcesStatement:
try ResourceSpecification Block [Catches] [Finally]
```

```
ResourceSpecification:
( ResourceList [;] )
```

```
ResourceList:
Resource {; Resource }
```

```
Resource:
{VariableModifier} LocalVariableType Identifier = Expression
VariableAccess
```

## 来自 §15 (Expressions) 的产生式

```
Primary:
PrimaryNoNewArray
ArrayCreationExpression
```

```
PrimaryNoNewArray:
Literal
ClassLiteral
this
TypeName . this
( Expression )
ClassInstanceCreationExpression
FieldAccess
ArrayAccess
MethodInvocation
MethodReference
```

```
ClassLiteral:
{ } . class
NumericType { } . class
boolean { } . class
void . class
```

```
ClassInstanceCreationExpression:
UnqualifiedClassInstanceCreationExpression
ExpressionName . UnqualifiedClassInstanceCreationExpression
Primary . UnqualifiedClassInstanceCreationExpression
```

```
UnqualifiedClassInstanceCreationExpression:
new [TypeArguments]
ClassOrInterfaceToInstantiate ( [ArgumentList] ) [ClassBody]
```

```
ClassOrInterfaceToInstantiate:
[Annotation] Identifier { [Annotation] Identifier
[TypeArgumentsOrDiamond]
```

```
TypeArgumentsOrDiamond:
TypeArguments
<>
```

### 字段访问

```
FieldAccess:
Primary . Identifier
super . Identifier
TypeName . super . Identifier
```

### 数组访问

```
ArrayAccess:
ExpressionName [ Expression ]
PrimaryNoNewArray [ Expression ]
```

### 方法调用

```
MethodInvocation:
MethodName ( [ArgumentList] )
TypeName . [TypeArguments] Identifier ( [ArgumentList] )
ExpressionName . [TypeArguments] Identifier ( [ArgumentList] )
Primary . [TypeArguments] Identifier ( [ArgumentList] )
super . [TypeArguments] Identifier ( [ArgumentList] )
TypeName . super . [TypeArguments] Identifier ( [ArgumentList] )
```

### 参数列表

```
ArgumentList:
Expression {, Expression}
```

### 方法引用

```
MethodReference:
ExpressionName :: [TypeArguments] Identifier
Primary :: [TypeArguments] Identifier
ReferenceType :: [TypeArguments] Identifier
super :: [TypeArguments] Identifier
TypeName . super :: [TypeArguments] Identifier
```



# 数组创建表达式

```
ClassType :: [TypeArguments] new
ArrayType :: new
```

```
new PrimitiveType DimExpr [Dims]
new ClassOrInterfaceType DimExpr [Dims]
new PrimitiveType Dims ArrayInitializer
new ClassOrInterfaceType Dims ArrayInitializer
```

# DimExpr

```
DimExpr { DimExpr }
```

```
[Annotation] [ Expression ]
```

# 语法

## Expression

```
LambdaExpression
AssignmentExpression
```

## LambdaExpression

```
LambdaParameters -> LambdaBody
```

## LambdaParameters

```
( [LambdaParameterList] )
Identifier
```

## LambdaParameterList

```
LambdaParameter ( , LambdaParameter )
Identifier { , Identifier }
```

## LambdaParameter

```
{VariableModifier} LambdaParameterType VariableDeclaratorId
Variableity
```

## LambdaParameterType

```
UnannType
var
```

## LambdaBody

```
Expression
Block
```

## AssignmentExpression

```
ConditionalExpression
Assignment
```

## Assignment

```
LeftHandSide AssignmentOperator Expression
```

## LeftHandSide

```
ExpressionName
FieldAccess
ArrayAccess
```

## AssignmentOperator

```
(one of) *= /= += -= <<= >>= >>>= &= ^= |=
```

## ConditionalExpression

```
ConditionalOrExpression ? Expression : ConditionalExpression
ConditionalOrExpression ? Expression : LambdaExpression
```

## ConditionalOrExpression

```
ConditionalAndExpression
ConditionalOrExpression || ConditionalAndExpression
```

## ConditionalAndExpression

```
InclusiveOrExpression
ConditionalAndExpression && InclusiveOrExpression
```

## InclusiveOrExpression

```
ExclusiveOrExpression
InclusiveOrExpression | ExclusiveOrExpression
```

## ExclusiveOrExpression

```
AndExpression
ExclusiveOrExpression ^ AndExpression
```

## AndExpression

```
EqualityExpression
AndExpression & EqualityExpression
```

## EqualityExpression

```
RelationalExpression
EqualityExpression == RelationalExpression
```

## RelationalExpression

```
ShiftExpression
RelationalExpression <= RelationalExpression
```

## ShiftExpression

```
AdditiveExpression
ShiftExpression << AdditiveExpression
```

## AdditiveExpression

```
MultiplicativeExpression
AdditiveExpression + MultiplicativeExpression
```

## MultiplicativeExpression

```
UnaryExpression
MultiplicativeExpression / UnaryExpression
```

## UnaryExpression

```
PreIncrementExpression
PreDecrementExpression
ExpressionPlusMinus
CastExpression
SwitchExpression
```

## PreIncrementExpression

```
UnaryExpression++
```

## PreDecrementExpression

```
UnaryExpression--
```

## ExpressionPlusMinus

```
PostfixExpression
~ UnaryExpression
```

## CastExpression

```
( PrimitiveType ) UnaryExpression
```

## SwitchExpression

```
switch ( Expression ) SwitchBlock
```

## ConstantExpression

```
Expression
```

# 附录 A. 有限许可

规范: JSR-389 Java SE 14
Version: 14
Status: Final Release
发布: March 2020
Copyright © 1997-2020, Oracle America, Inc.
保留所有权利。

## 有限许可

1. 评估许可。规范特此授予你一项全额支付的、非独占的、不可传输的、全球许可（无转许可权），根据规范的知识产权，查看、下载、使用和复制规范仅用于内部评估，包括：(i) 开发运行在规范实现上的应用程序，前提此类应用程序未实现规范的任何部分；(ii) 与任何第三方讨论规范；以及(iii) 在口头或书面通信中摘录规范的简短部分，前提此类摘录总体不构成规范的重要部分。

2. 合规实现的分发许可。规范还授予你永久的、非独占的、不可传输的、全球范围的全额支付、免版税的许可（无转许可权），根据任何适用版权（受下文第 4 条限制），创建/或分发规范的实现：(a) 完全实现规范，包括其所有的接口和功能；(b) 不修改、子集或以其他方式扩展规范空间，或包含规范要求的或实施的规范之外的公共或受保护包、Java 接口、字段或方法；以及(c) 通过此类规范的技术兼容性（包括满足适用 TCK 用户指南的要求）（“合规实现”）。上述许可明确取决于不在其范围之外。本许可未授予任何其他用途的许可（例如，在合理使用范围之外修改规范，或将规范分发给第三方）。此外，本许可未授予对规范或其许可人的任何商标、服务标记或商业名称的任何权利、所有权或利益。

3. 传递条件。在对所授予的任何关于使用你的独立实现或其衍生产品的许可中，你无需包含前段落中的 (a)-(c) 限制或任何其他“传递”要求。但是，除了满足前段落中 (a)-(c) 限制的独立实现（及其衍生产品）外，你既不能：(a) 向你的许可人授予或以其他方式传递任何规范适用的知识产权；也不 (b) 授权你的许可人对其实现与相关规范的符合性做出任何声明。

4. 关于专利许可的互惠性。对于上述第 2 条授予许可所涵盖的、会被所有技术上可行的实现所侵犯的任何权利要求，该许可取决于你向任何寻求你方的方的提供公平、合理且非歧视（FRAND）条款的基于你专利权的永久的、非独占的、不可传输的、全球许可——即被所有技术上可行的实现所侵犯或可能被侵犯的专利许可，以开发、分发和使用合规实现。

b. 对于规范所有且受上述第 2 条授予许可所涵盖的任何专利权利，无论在实现规范时能否以技术上可行的方法避免其侵权，如果你在履行作为规范负责人的职责过程中对规范发起了权利主张，导致了其他实体侵犯了你的专利权利，则该许可对于此类权利应终止。

c. 同样对于规范所有且受上述第 2 条授予许可所涵盖的任何专利权利，侵犯的在根据此类许可实施本规范时，可以通过技术上可行的方法避免此类主张；对于此类主张，如果您对规范主方发起诉讼，指控规范的制造、已制造、使用、要约出售、销售或进口合规实现侵犯了您的专利权，则本许可应终止。

5. 定义。在本协议中：“独立实现”（Independent Implementation）是指对规范的实现，该实现既不源自规范主方的源代码或二进制代码材料（除非获得规范主方提供的适当当且独立的许可），也不包含规范主方的任何源代码或二进制代码材料；“许可方名称命名空间”（Licensor Name Space）是指以“java”、“javax”、“com.oracle”、“com.sun”或 Oracle America, Inc. 通过 Java 社区兼容性工具包或其认可的继承者或替代者随后采用的任何等效命的公共类或接口声明；“技术兼容性工具包”（Technology Compatibility Kit）或“TCK”是指由规范主方提供的与规范相应的测试套件及配套的 TCK 用户指南，该套件在 (i) 在您允许商业用途的独立实现首次发布前 120 天由规范主方提供，或 (ii) 在此类发布后 120 天以上提供，且您选择对其对规范的实现进行测试。

如果您违反本协议或在上述授予许可的范围之外行动，本协议将在无需规范主方通知的情况下立即终止。

## 免责声明

本规范按“现状”提供。规范主方不提供任何明确或暗示的陈述或保证，包括但不限于对销销性、特定用途的适用性、不侵权（包括由于规范的任何实践或实施导致的不侵权）或规范内容适用于任何用途的保证。本文档不代表在任何产品中发布或实施规范的任何部分的任何承诺。此外，规范可能包含技术性不准确或排版错误。

## 责任限制

在法律允许的范围内，在任何情况下，规范主方或其许可方均不对任何损害负责，包括但不限于收入、利润或数据的损失，或特殊的、间接的、后果性的、偶然或惩罚性的损害，无论由何种引起，无论何种责任理论，由于您拥有、实施或以其他方式使用规范而引起或与其任何方式相关的损害，即使规范主方和/或其许可方已被告知发生此类损害的可能性。

您将赔偿、补偿并确保规范主方及其许可方免受因以下情况引起或导致的任何索赔：(i) 您对规范的使用；(ii) 使用或分发您的 Java 应用程序、applet 和/或 (iii) 任何提供给您的规范后续版本或发布版本与根据本许可为您提供的规范不兼容的任何索赔。

## 限制权利授予

美国政府：如果本规范是由美国政府或代表美国政府，或由美国政府主承包商或分包商（在任何层级）获取，则政府对软件及随附文档的权利应仅如本许可规定的所示；这符合 48 C.F.R. 227.7201 至 227.7202-4（适用于国防部 (DoD) 采购）以及 48 C.F.R. 2.101 和 12.212（适用于非国防部采购）。

## 报告

如果您向规范主方提供有关规范的任何意见或建议（“反馈”），您特此：(i) 同意此类反馈是在基于非所有且非保密的基础上提供的，且 (ii) 授予规范主方永久的、非独占的、全球范围的全额付费的不可撤销的许可，允许通过多级分许可人进行分许可，以便出于任何目的纳入、披露且不受限于使用反馈。

## 通用条款

与本协议相关的任何行动将受加利福尼亚州和美国联邦法的管辖。《联合国国际货物销售合同》及任何司法管辖区的法律选择规则均不适用。

规范受美国出口管制法律限制，并可能受其他国家进出口规定的限制。被许可方同意严格遵守所有此类法律，并承认其在交付给被许可方后根据需要获得出口、再出口或进口的许可。
