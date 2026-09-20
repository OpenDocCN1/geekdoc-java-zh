
# 2020 第27届亚太地区软件工程会议 (APSEC) ｜｜ Java 项目如何使用弱引用？

## 摘要

编程语言拥有垃圾回收系统来自动管理内存，但由于内存管理的局限性，仍可能出现问题。弱引用被提出作为解决此类问题的方案。然而，开发者在使用弱引用时通常需要考虑内存布局。在本文中，我们调查了开源项目对弱引用的使用。更具体地说，我们调查了 Java 对象的领域、弱引用的引入时机、使用方法以及是否存在针对引用的测试代码。调查显示，弱引用被 73 个代码库、约 102 个报告者使用，且弱引用在测试代码中最为常见。

```java
WeakReference<Socket> ret = new WeakReference<Socket>(socket);

Socket s = ret.get();

if (s == null) {
    // 如果对象已被回收
} else {
    // 如果对象仍在堆中
}
```

图 1. 类 `WeakReference` 的示例

## 1. 引言

垃圾回收（GC）是许多编程语言中用于自动管理内存的系统 [1]。GC 将开发者从手动管理内存中解放出来，因为 GC 会自动收集不可达的对象。当一个对象不可达或无法通过其他对象的可达性确定时，被其他对象引用的对象是可达的且不会收集，因为它们被连接为不可达。从其他对象引用的对象是不可达的，不可达的对象会被自动收集。

然而，通过 GC 进行内存管理仍然存在问题。如果一个未来将不再使用的对象从其他对象**可达**（原文为“不可达”，根据上下文推测应为“可达”），它将不会被 GC 回收。结果导致对象留在内存中，引起内存泄漏。

在 GC 中，开发者无法指定特定对象来指示回收。作为开发者指定要回收哪个对象的方法，弱引用（WR）在 GC 机制中相对于强引用被提出。仅被 WR 引用的对象不被处理并被 GC 回收。因此，通过使用一个 WR 对象，可以将其指定为 GC 目标。然而，有效地使用 WR 有一些考虑因素。首先，开发者需要知道被弱引用对象被回收的时机。只要至少有一个来自其他对象的引用，对象就不会被回收，GC 只回收仅被 WR 引用的对象。因此，无法预测一个对象从强引用变为弱引用的何时，并设计该对象在不再需要时被回收。其次，我们需要确定 GC 回收由 WR 引用的对象的时机。GC 并不是在对象成为 GC 目标时立即收集，而是在 WR 中插入一个空指针。

关于 GitHub 代码库的各种研究数据 [3]，以及一些解决 Java 内存泄漏问题的研究 [4, 5]。然而，目前还没有关于 WR 使用情况的调查研究。在开源软件中，我们调查了使用 WR 的 Java 项目领域、WR 的引入时间、方法、测试的存在以及失败的案例。

## 2. Java 中的弱引用

Java 语言提供了两个用于 WR 的类。

- `java.lang.WeakReference<T>`
- `java.util.WeakHashMap<K,V>`（原文为 `HashMap`，根据上下文应为 `WeakHashMap`）

前者是用于类型 T 的 WR 类。图 1 展示了一个如何使用 `WeakReference` 的示例。后者和普通的哈希映射（`java.util.HashMap<K,V>`）具有相同的功能。区别在于，当弱引用对象被回收时，键值对的值会丢失；如果没有对值对象的引用，它将与键对象一起被回收。键对象的键值对不再一定会被从 `WeakHashMap` 中移除。这过的优点是开发者不需要担心删除不必要的键值对。

## 3. 研究问题

- **RQ1（领域）**：我们的目标是理解哪些领域的项目使用了 WR，以及它们使用了哪些特性。
- **RQ2（引入时间）**：我们调查了每个项目引入 WR 的时间，以理解引入 WR 的目的。引入被分为两类：(1) 实现新功能和 (2) 维护现有功能。
- **RQ3（使用方法）**：我们试图找出 WR 是如何被使用的。通过了解我们在现实世界中如何使用 WR，我们可以理解 WR 的主要用途以及使用 WR 的典型模式。
- **RQ4（测试）**：在软件开发中进行测试是可能的。我们调查了使用 WR 的代码是否经过充分测试。
- **RQ5（失败案例）**：为了确定 WR 是否困难，我们调查了是否存在开发者因意外问题而停止使用 WR 的情况。
- **RQ6（性能）**：为了检查 WR 对性能是否有效，我们在开源项目上进行了性能测试。我们调查了使用 WR 的代码与修改为不使用 WR 的代码是否存在差异。

## 4. 研究方法

### 4.1 研究对象

程序是重复 Borges 等人 [3] 在实验中使用的 202 个项目。他们将 202 个项目分为以下领域：

- 应用程序软件 (Application)
- 系统软件 (System)
- Web 库和框架 (Web)
- 非 Web 库和框架 (Non-web)
- 工具 (Tools)
- 文档（Doc.）

我们使用 GitHub 代码搜索 API 来确定每个项目是否使用了 WR。使用 `WeakReference` 和 `WeakHashMap` 两个关键词执行代码搜索，确定了每个项目是否使用了 WR。

## 5. 结果

### 5.1 RQ1：弱引用使用的领域

调查显示，WR 在 73 个代码库、约 102 个报告者中使用，且 WR 在测试代码中最为常见。结果：WR 在 73 个代码库中使用，在 202 个项目中的 44 个项目中使用。在 202 个项目中，WR 在 Web 领域中最为常见。在 System 领域中，WR 在 73 个项目中的最为常见。

![图 2：项目领域](img/5f9b873328e6d5db22a6fa7023ebdf4_20.png)

### 5.2 RQ2：弱引用的引入时间

我们调查了每个项目引入 WR 的时间，以理解引入 WR 的目的。引入分为两种：(1) 创建新功能和 (2) 维护现有功能。在第一种情况下，WR 是随着功能的引入的；在第二种情况下，WR 是为了维护现有功能。

| 文件创建 | 文件更新 |
| :--- | :--- |
| `WeakReference` | 247 | 81 |
| `WeakHashMap` | 75 | 29 |
| 总计 | 322 | 110 |

### 5.3 RQ3：弱引用如何被使用

我们通过调查 55 个项目，试图找出 WR 是如何被使用的。我们将 WR 的使用归纳为几类：

- 测试
- 内存泄漏预防
- 缓存实现
- 避免不必要的处理
- API 实现

| 用例 | 使用 WR 的次数 |
| :--- | :--- |
| 测试 | 37 |
| 内存泄漏预防 | 25 |
| 缓存 | 17 |
| API 实现 | 13 |
| 避免不必要的处理 | 6 |

WR 在测试代码中是常见的。在内存泄漏预防中，WR 是常见的。在缓存实现中，WR 是常见的。在避免不必要的处理中，WR 也是常见的。此外，GC 并不是在对象成为 GC 目标时立即收集，而是在 WR 中插入一个空指针。

#### 代码示例

**图 3(a) 使用 WR 进行测试**

```java
public void testDisposeDetaches() {
    Disposable d = Disposables.empty();
    WeakReference<Disposable> wr = new WeakReference<Disposable>(d);
    TestObserver to = new TestObserver(d);
    to.test();
    d = null;
    System.gc();
    assertNull(wr.get());
}
```
开发者可以使用这段测试代码检查内存泄漏的存在。

**图 3(b) 将弱引用位图作为中间产品以防止内存泄漏**

```java
class LineChartRenderer {
    WeakReference<Bitmap> mBitmap = null;
    void draw(Canvas canvas) {
        Bitmap bitmap = mBitmap?.get();
        if (bitmap == null) {
            bitmap = Bitmap.create(...);
            mBitmap = new WeakReference<>(bitmap);
        }
        canvas.drawBitmap(bitmap, 0, 0, null);
    }
}
```
如果对象被回收，且 WR 在进程开始前创建了新对象并对该新对象创建了 WR，则中间产品可以被回收；如果执行相同的性能操作，且中间产品未被回收，则可以节省计算，因为对象不需要重新创建。

**图 3(c) 避免不必要的处理**

```java
class SizeListener implements SizeListener {
    WeakReference<Size> mSizeRef;
    SizeListener(Size size) {
        mSizeRef = new WeakReference<>(size);
    }
    boolean onDraw() {
        Size size = mSizeRef.get();
        if (size != null) size.check();
        else return true;
    }
}
```
图 3(c) 展示了避免不必要的处理的示例。以对象作为输入，且对象已被回收，GC 不会对该对象进行处理（图 1 中的第 9 行）。

在缓存用例中，代码模式是内存泄漏预防。区别在于，在防止内存泄漏的情况下，中间产品是被弱引用的；而在缓存的情况下，计算对象是被弱引用的。通过对结果进行弱引用，如果对象被回收，可以保存计算以防止内存泄漏，而不会从具有相同计算结果的对象产生。

### 5.4 RQ4：针对弱引用的测试

步骤：针对表 1 中项目的任务执行了 RQ4。在发现的 95 个源文件中，没有使用 WR。我们检查了 58 个源文件中的每一个是否存在测试代码。如果存在代码，我们检查了测试代码是否使用了 WR。

结果：58 个源文件中有 38 个存在测试代码。我们检查了这 38 个源文件的测试，发现只有十个源文件存在 WR 测试，这约占 58 个源文件的六分之一，且使用了 WR。

### 5.5 RQ5：弱引用引入失败的案例

步骤：针对表 1 中的项目执行了 RQ5。我们检查了包括关键词 `WeakReference` 和 `WeakHashMap` 的项目变更历史，以查看是否存在停止使用 WR 的情况。在本研究中，我们利用 WR 类不再被使用这一事实作为停止使用 WR 的依据。

| 项目名称 | 失败次数 |
| :--- | :--- |
| Reactive/RxJava | 1 |
| spring-projects/spring-framework | 2 |
| bumptech/glide | 2 |
| 总计 | 5 |

结果：表 IV 显示了每个项目中的用例。WR 引入失败，十个项目中有三个未能引入 WR 引用，在上述三个项目中发生了五次引入 WR 的失败情况。

- **RxJava 和 Glide** 曾引入 `WeakReference` 类。失败导致被引用对象比预期更早地被清除，导致了对对象的处理失败；换句话说，问题的发生是因为开发者在使用 WR 时没有考虑工作任务的回收。
- **Spring-framework** 中，引入 `WeakHashMap` 失败了。`WeakHashMap` 的使用导致结果执行速度增加。然而，它被用在一个多进程系统中，在这种情况下执行速度较慢，问题的发生是因为开发者在 UI 中没有深入理解 `WeakHashMap` 的特性。

### 5.6 RQ6：弱引用的性能影响

选择项目 "bumptech/glide" 作为实验对象。Glide 是一个用于 Android 的图像库。它内部有一个用于图像数据的缓存。原始 Glide 代码使用 WR，对比版本为在相同情况下未使用 WR 的发布版本。通过比较两者的性能，检查 WR 是否有用。

在性能测试中，使用 Glide 的两类 Android 应用程序是：

1.  具有数据引用的应用程序，以及
2.  无引用的应用程序。

应用程序 1 对数据有引用。应用程序 2 在加载后立即删除引用。该应用程序没有图像数据引用。

加载了 400 张 JPEG 图片，平均 4 MB，总大小为 1.6 GB。图像通过 HTTP 加载，并设置了一个使用 HFS 分布数据的服务器。环境：Android 8.1 (Core) 和 1GB RAM。

实验结果如下所示，所有的 "aborted" 都是相同的。加载 200 张图像后，应用程序在内存执行 `GB` 之后立即被强制终止。此类终止的原因被认为是应用程序引用的图像数据对象没有在适当的时间被回收，导致了内存溢出。

表 V 中的 "completed" 是使用 WR 的原始 Glide 与没有图像数据引用的应用程序的结合。在这里，“completed" 表示所有图像都已成功加载。"completed" 的实现是因为图像数据被妥善回收了，由于 Glide 中使用了对数据的弱引用，因此没有发生内存泄漏。

## 6. 威胁效度

在本研究中，代码和历史是手动分析的，没有对实验结果进行过多的定量解释，对研究问题的回答是定性的，例如 WR 的用例以及引入 WR 的情况。因此，检查本研究中的代码和历史是充分的。

## 7. 结论与未来工作

在本研究中，我们调查了 Java 项目的弱引用使用。我们设置了 RQ，即弱引用使用的领域、引用的引入、对弱引用的测试、弱引用引入失败的案例以及经历的影响。

- WR 主要在创建新文件时引入，在开发者遇到意外问题时引入。因此，WR 应该被谨慎引入。在调查 202 个项目时，WR 在 73 个项目中使用。其中，WR 在 System 领域中最为常见。对于性能，WR 存在很强的需求。
- 存在一些开发者因意外问题而停止使用 WR 的情况。为了避免此类问题，WR 的引入需要非常谨慎。我们在开源项目上进行了实验，确认 WR 对性能是有效的。在所有引用数据的应用中，原始库在使用 WR 时发生了异常（原文逻辑似有反，此处保留原意）。仍然，对于一次性处理 1 GB 数据并对其进行操作，重复加载和卸载是可能的。在这种情况下，使用 WR 的现有库运行良好，而修改后的库则异常终止。

我们要定义弱引用的代码模式。我们还尝试通过开发一种机制，向开发者建议使用定义的模式来自动弱引用的使用。

## 参考文献

[1] P. Wilson, "Unsafe garbage collection techniques," in *Memory Management*, Springer, 1992, pp. 1–12.
[2] "Reference Objects and Glide," http://www.android.com/articles/
[3] H. Borges, A. Ho, and M. T. Valentin, "Understanding the effect of popularity of github repositories," in *the 3rd International Conference on Software Maintenance and Evolution*, 2006, pp. 331–344.
[4] J. Garcia-Vazquez, G. Bavota, M. D. Data, D. German, and Pollard, "Memory leaks and changes: tangling properties of objects," in *the 15th International Conference on Program Compilation*, 2015, pp. 218–228.
[5] W. Power and S. Seifert, "Visualization reference patterns for memory leaks in java," in *European Conference on Object-Oriented Programming*, Springer, 1999, pp. 116–134.
[6] R. Sharma, S. Kumar, and S. Nag, "Removal of array memory leaks in java," in *the 9th International Conference on Compiler Construction*, 2000, p. 50–66.

## 表 1：高星项目

| 项目 | 星数 |
| :--- | :--- |
| Reactive/RxJava | 36206 |
| elasticsearch/elasticsearch | 35955 |
| spring-projects/spring-boot | 30988 |
| square/okhttp | 29609 |
| google/guava | 27988 |
| philJay/MPAndroidChart (原 filthy/AndroidChart) | 26609 |
| spring-projects/spring-framework | 24612 |
| bungee/gradle (原 bungee/gradle) | 23869 |
| square/testframework | 21002 |
| zxing/zxing | 20623 |
