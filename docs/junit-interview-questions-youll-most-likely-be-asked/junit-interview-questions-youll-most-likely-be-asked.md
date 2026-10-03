
# JUnit 面试题：你最可能被问到的问题

## 面试真题

你可能会被问到的

![](img/35a30a68f7643b185635310e7a25e3fa_0_0.png)

> 免费提供

2 项能力测试，可在网站下载

## JUnit 面试真题

复习这些典型的面试题并思考你将如何回答。阅读列出的答案；你将找到最佳答案以及相关的策略和建议。

## 规则

### 1: JUnit 的 Rules 功能是什么？

答案：

Rules 允许以非常灵活的方式添加或重新定义测试类中每个测试方法的行为。

### 2: 你如何使用 TemporaryFolder Rule 来创建一个在测试结束时保证会被删除的文件？

答案：

```java
@Rule public TemporaryFolder folder = new TemporaryFolder();
@Test void someTest() { File f = folder.newFile("file"); }
```

### 3: ExternalResource Rule 是起什么作用的？

答案：

ExternalResource Rule 是一种规则，它允许在测试开始和结束时定义资源的初始化和析构。

### 4: 与 setup 和 tear down 方法相比，ExternalResource 有什么优势？

答案：

External Resource 允许将与单个资源相关的逻辑定位到单个类，该类可以在多个测试中重用。

### 5: ErrorCollector Rule 是起什么作用的？

答案：

ErrorCollector Rule 允许在发现第一个问题后继续执行测试（例如，收集表格中的所有错误行并一次报告它们）。

### 6: 你如何使用 Timeout Rule 来确保类中的每个测试方法的运行时间不会超过 20 毫秒？

答案：

```java
@Rule public Timeout globalTimeout = new Timeout(20);
```

### 7: 你如何使用 ExpectedException Rule 来确保抛出一个带有特定消息的异常？

答案：

```java
@Rule public ExpectedException thrown = new ExpectedException();
@Test public void someTest() {
    thrown.expect(NullPointerException.class);
    thrown.expectMessage("Error happened");
    throw new NullPointerException("Error happened");
}
```

### 8: TestName Rule 是起什么作用的？

答案：

TestName Rule 允许在测试中访问当前测试的名称。

### 9: TestWatcher Rule 是起什么作用的？

答案：

TestWatcher Rule 允许记录测试操作，而不对其进行修改。

### 10: Verifier Rule 是起什么作用的？

答案：

Verifier Rule 允许提供逻辑，使测试看起来像是通过或失败。

### 11: 你如何使用 MethodRule 在每个测试之前打印某些内容？

答案：

```java
public class SomeRule implements MethodRule {
    @Override public Statement apply(final Statement base, FrameworkMethod method, Object target) {
        return new Statement() {
            @Override public void evaluate() throws Exception {
                System.out.println("foo");
                base.evaluate();
            }
        };
    }
}
```

### 12: 假设你用 JUnit 编写了一个集成测试，因为它依赖于一个有时会失败的外部资源导致是不稳定的（flaky）。你如何利用 JUnit 的特性来自动重试几次使用资源的测试？

答案：

我们可以编写一个 Rule，简单地重试失败的测试（捕获 `AssertionError`；例如；然后再次调用 statement）。

### 13: 假设有一个用 JUnit 编写的集成测试，因为它依赖于一个有时会失败的外部资源导致是不稳定的。你如何利用 JUnit 的特性来自动重试几次使用资源的测试？

答案：

我们可以编写一个 Rule，简单地重试失败的测试（捕获 `AssertionError`；例如；然后再次调用 statement）。

### 14: 我们很多时候使用随机数据编写测试以增加发现 Bug 的机会并进行探索性测试。当测试失败时，我们如何重现这些测试？

答案：

我们可以使用由 `ExternalResource` 提供的随机对象，以便在测试失败时保存种子（seed）。

### 15: 我们如何通过自动失败运行时间增加50%的测试来跟踪系统性能？

答案：

我们可以添加一个 Rule 来跟踪运行时间，当时间过长时使其失败。

### 16: 描述 Rule 实现如何在运行时注入它们的逻辑。

答案：

Rule 仅仅接收一个 `Statement`，它代表将执行的测试方法。它可以通过在执行之前、之后或替换执行任务来装饰该 statement 的执行。

### 17: 你如何添加自动日志来打印每个测试消耗的时间？

答案：

我们可以创建一个 LoggingRule，它将在每个测试结束后跟踪并记录执行时间。

### 18: 单个测试类中可以提供多少个 Rule？

答案：

没有限制，因为 Rule 是可组合的。

## 断言

### 19: 你如何断言测试中的某些条件为真？

答案：

使用 `assertTrue()` 方法，例如 `assertTrue(condition)` 来断言某些条件为真。

### 20: 为什么断言方法有一个可选的 String 参数？

答案：

为了指定一个可以从失败消息中理解的详细且易于读的理由。

### 21: 如果在同一个测试方法中有多个断言，且其中一个失败了，下一个断言还会执行吗？为什么？

答案：

不会执行下一个，因为失败的断言会抛出 `AssertionError` 并停止方法的执行。

### 22: `assertEquals` 的作用是什么？

答案：

`assertEquals` 断言传递给它的两个对象是否相等。

### 23: 为什么同时需要 `assertTrue()` 和 `assertEquals()`？

答案：

由于 `assertEquals` 更具体，它在失败时可以提供更好的信息，并能更好地表达意图。

### 24: `assertEquals()` 和 `assertSame()` 有什么区别？

答案：

`assertEquals()` 使用 `equals()` 比较对象，而 `assertSame()` 使用引用比较（`==`）。

### 25: 断言两个数组相等的正确方法是什么？为什么？

答案：

`assertEquals` 是断言两个数组相等的正确方法，因为它能正确地比较它们的值（即通过比较每个元素来进行的直观方式），而不是使用与 `==` 相同的普通相等性方法。

### 26: 如果你在逻辑上得出一个测试应该失败的结论；停止它的正确方法是什么？不使用 `assertTrue(false)` 之类的方法？为什么？

答案：

使用 `fail()`，因为它清晰地表达了代码的意图。它没有使用晦涩的结构，而是恰好做到了“正确的事”。

### 27: 为什么 double 类型的 `assertEquals()` 方法接收三个 double 参数？

答案：

是因为另一个参数用于指定两个 double 之间允许的差异。

### 28: 你如何在测试中断言某个方法抛出了异常？

答案：

在测试的 `@Test` 注解中指定 `expected=Exception` 来断言测试中抛出了特定异常。

### 29: 为什么在以下示例中使用 `fail()`？

```java
try {
    doSomething();
    fail();
} catch (Exception e) {
    assertEquals("Bad thing", e.getMessage());
}
```

答案：

为了确保在没有抛出预期异常时测试会失败，因此使用了 `fail()`。

### 30: `assertEquals()` 的参数顺序重要吗？

答案：

是的，`assertEquals()` 的参数顺序很重要，因为第一个参数指定测试预期的值，第二个参数是实际看到的结果。JUnit 依赖于这个顺序来提供友好的错误信息。

### 31: `assertThat()` 是什么？

答案：

`assertThat()` 是一种新的断言类型，使用匹配器（matchers）来实现更具可读性的断言。

### 32: 使用 `assertThat()` 断言变量等于字符串 "hello"。

答案：

`assertThat(variable, equalTo("Hello"));`

### 33: 使用 `assertThat()` 断言变量是特定类的实例。

答案：

`assertThat(variable, instanceOf(SomeClass.class));`

### 34: 使用 `assertThat()` 断言字符串包含 "abc"。

答案：

`assertThat(variable, containsString("abc"));`

### 35: 使用 `assertThat()` 断言列表包含 "Hello"。

答案：

`assertThat(list, hasItem("Hello"));`

### 36: 使用 `assertThat()` 断言列表包含 "Foo" 或 "Bar"。

答案：

`assertThat(list, anyOf(hasItem("Foo"), hasItem("Bar")));`

### 37: 使用 `assertThat()` 断言列表包含 "Foo" 和 "Bar"。

答案：

`assertThat(list, allOf(hasItem("Foo"), hasItem("Bar")));`

### 38: 使用 `assertThat()` 断言数字大于 4。

答案：

`assertThat(number, is(greaterThan(4)));`

### 39: 使用 `assertThat()` 断言字符串在忽略大小写的情况下等于字符串 "Foo"。

答案：

`assertThat(string, is(isEqualToIgnoringCase("Foo")));`

### 40: 使用 `assertThat()` 断言变量为 null。

答案：

`assertThat(variable, is(nullValue()));`

### 41: 编写一个自定义匹配器，断言整数在两个数字之间。

```java
public class InRange extends TypeSafeMatcher<Integer> {
    private int from;
    private int to;
    public InRange(int from, int to) {
        this.from = from;
        this.to = to;
    }
    @Override
    public void describeTo(Description description) {
        description.appendText(String.format("between (%d, %d)", from, to));
    }
    @Override
    protected boolean matchesSafely(Integer item) {
        return item > from && item < to;
    }
    @Factory
    public static <T> Matcher<Integer> between(int from, int to) {
        return new InRange(from, to);
    }
}
```

### 42: 使用 `assertThat()` 断言 Map 包含键 "foo" 值为 "bar"。

答案：

```java
assertThat(map, hasEntry("foo", "bar"));
```

### 43: 使用 `assertThat()` 断言 Map 包含键 "foo"。

答案：

```java
assertThat(map, hasKey("foo"));
```

### 44: 使用 `assertThat()` 断言 Map 包含值 "bar"。

答案：

```java
assertThat(map, hasValue("bar"));
```

### 45: 使用 `assertThat()` 断言集合中的所有字符串都等于 "foo"。

答案：

```java
assertThat(list, everyItem(isEqualTo("foo")));
```

### 46: `assertFalse()` 是什么？

答案：

`assertFalse` 断言给定的布尔值等于 false。

### 47: `fail()` 是什么？

答案：

`fail()` 导致当前执行的测试失败。

### 48: `assertNotNull()` 是什么？

答案：

`assertNotNull()` 断言给的对象不是 null。

### 49: `assertNull()` 是什么？

答案：

`assertNull()` 断言给的对象为 null。

### 50: `assertSame()` 是什么？

答案：

`assertSame()` 断言给两个对象是同一个实例。

### 51: `assertNotSame()` 是什么？

答案：

`assertNotSame()` 断言给两个对象不是同一个实例。

### 52: `assertEquals()` 是什么？

答案：

`assertEquals()` 使用 `equals()` 方法断言两个对象相等。

### 53: `assertNotEquals()` 是什么？

答案：

`assertNotEquals()` 使用 `equals()` 方法断言两个对象不等。

### 54: `assertThrows()` 是什么？

答案：

`assertThrows()` 断言在代码执行期间抛出了特定异常。

### 55: `assertTimeout()` 是什么？

答案：

`assertTimeout()` 断言代码在指定时间内完成。

### 56: `assertNotTimeout()` 是什么？

答案：

`assertNotTimeout()` 断言代码执行时间超过了指定时间。

### 57: `assertArrayEquals()` 是什么？

答案：

`assertArrayEquals()` 断言两个数组的长度和内容相等。

### 58: `assertArrayEqualsEquals()` 是什么？

答案：

`assertArrayEqualsEquals()` 断言两个 double 数组在指定的误差（delta）内相等。

### 71: 如何指定某个测试必须在给定的时间范围内完成？

答案：

在测试的 `@Test` 注解中指定 `timeout=timeoutInMillis` 来规定某个测试必须在给定的时间范围内完成。

### 72: 普通测试类的构造函数可以有参数吗？

答案：

不可以，普通测试类的构造函数不能有参数，因为 JUnit 不知道如何实例化它们。

### 73: 测试类中的设置方法（set up methods）是什么？

答案：

设置方法用于准备测试所需的对象，并在该类中的多个测试方法之间共享这些对象。

### 74: 测试类中的拆卸方法（Tear down methods）是什么？

答案：

拆卸方法用于清理对象并撤销测试所执行的任何操作，以防止对其他测试产生影响。

### 75: 必须指定设置方法和拆卸方法吗？

答案：

不需要指定设置方法和拆卸方法。这是因为它们是帮助更好地编写测试的可选选项，并非必不可。你可以在没有它们的情况下运行测试。

### 76: 如果指定了拆卸方法，也必须声明设置方法吗？

答案：

不需要，因为它们是可选的，使用其中一个并不意味着必须使用另一个。

### 77: 如何指定一个方法为设置方法？

答案：

使用 `@Before` 注解该方法，以指定其为设置方法。

### 78: 如何指定一个方法为拆卸方法？

答案：

使用 `@After` 注解该方法，以指定其为拆卸方法。

### 79: 如何指定仅在测试类中运行一次的设置代码？

答案：

将其放在带有 `@BeforeClass` 注解的方法中，以指定为整个测试类运行一次的设置代码。

### 80: 如何指定仅在整个测试类中运行一次的拆卸代码？

答案：

将其放在带有 `@AfterClass` 注解的方法中，以指定为整个测试类运行一次的拆卸代码。

### 81: 请给出一个 @BeforeClass/ @AfterClass 方法的有效声明。

答案：

`@BeforeClass public static void setUpAll() {}`

注意，重要的部分是它包含 `static` 关键字。

## 运行测试

### 82: 如果在同一个类中有多个测试方法且其中一个失败了，下一个方法还会执行吗？为什么？

答案：



是的，因为 JUnit 在单个方法失败时不会停止执行，下一个方法仍会被执行。

# 83: 测试方法有哪些不同的可能结果？

答案：

成功、失败和错误是测试方法的不同可能结果。

# 84: 失败和错误之间的区别是什么？

答案：失败是指断言失败，而错误是指抛出了未预期的异常。

# 85: 下述测试会通过吗？为什么？

```java
@Test
public void someTest() {
    Thread t = new Thread() {
        public void run() {
            throw new RuntimeException();
        }
    };
    t.start();
    t.join();
}
```

答案：

是的，它会通过，因为异常是在与测试线程不同的线程中抛出的；JUnit 无法得知错误发生，因此不会让测试失败。

## 86: 设置方法什么时候运行？

答案：

设置方法在每个测试方法运行之前运行。

## 87: 拆卸方法什么时候运行？

答案：

拆卸方法在每个测试方法运行之后运行。

# 88: 如果测试失败，应该运行拆卸方法吗？为什么？

答案：

是的，因为测试失败并不意味着不应该执行拆卸代码。这对于确保状态被清理很有用，就像在生产代码中使用 `finally` 关键字所做的那样。

# 89: 如果测试出现错误，应该运行拆卸方法吗？为什么？

答案：

是的，因为测试失败并不意味着不应该执行拆卸代码。这对于确保状态被清理很有用，就像在生产代码中使用 `finally` 关键字所做的那样。

# 90: 如果设置方法抛出异常，测试方法还会运行吗？为什么？

答案：

不会，因为错误会导致测试用例不知道测试本身所需的设置是否已经执行；因此它无法在未知状态下执行测试。

# 91: 如果测试成功通过，但其拆卸方法抛出了异常，测试还会被视为通过吗？为什么？

答案：

不通过，因为拆卸代码可以用于全局断言（例如确保所有临时文件都已删除），而它的失败可能意味着测试代码本身存在问题。

# 92: 对于整个测试类，拆卸代码应该运行多少次？

答案：

将其放在带有 `@AfterClass` 注解的方法中，以指定为整个测试类运行一次的拆卸代码。

# 93: 如果在设置方法中初始化一个成员，在注解中声明，该成员在不同测试方法之间共享吗？

答案：

不共享，因为每个测试方法都会创建一个测试类的新实例。

# 94: 静态成员在不同的测试方法之间共享吗？

答案：是的，静态成员在类的测试方法之间共享。

## 95: 写一个执行测试的 main 方法。

答案：

```java
public static void main(String[] args) {
    JUnitCore.main(MyTest.class);
}
```

## 96: Enclosed 运行器做什么？

答案：Enclosed 运行器运行外部类的所有内部类。

# 97: Categories 运行器开启什么？

答案：Categories 运行器只运行标记了目标类别的类和方法，或者是该类的子类。你也可以排除类别。

# 98: 如何使用 Categories 创建快速测试套件？

答案：

```java
@Category(FastTests.class)
public class A {
    @Test
    public void test() {}
}
```

# 99: 在一次测试运行中可以提供多个包含的类别吗？为什么？

答案：不可以提供多个包含的类别，因为 Category 注解接收单个类。

# 100: 可以同时提供一个包含类别和一个排除类别吗？为什么？

答案：可以同时提供一个包含类别和一个排除类别，因为这两个注解并不互斥。

## 101: 如何标记一个测试不运行？

答案：对该方法使用 `@Ignore` 注解来标记其不运行。

# 102: @Ignore 注解可以应用于方法以外的地方吗？

答案：可以，它可以应用于类上，用以忽略该类中的所有测试方法。

# 103: JUnit 的参数化运行器做什么？

答案：参数化允许在给定的输入集上执行相同的测试。

# 104: 什么是 JUnit 的 ParallelComputer？

答案：JUnit 的 ParallelComputer 允许并行执行测试。

# 105: ParallelComputer 的 classes 和 methods 选项有什么区别？

答案：classes 选项在多线程中运行测试，但单个类中的所有测试按顺序执行；methods 选项允许在多线程中运行所有内容。

## 106: 类测试方法的执行顺序是怎样的？

答案：类的测试方法按照它们声明的顺序执行。

# 你最可能被问到的 JUnit 面试题 33

## 110: 如果某些测试需要连接互联网才能运行，你将如何启用将它们分离，以便你通常可以运行所有测试，但当你在地铁上没有网络连接时，你可以运行所有不需要网络连接的测试？

答案：

我们可以为所有需要连接互联网的测试标记一个特定的类别，然后创建一个排除这些测试的套件。这将使我们能够随时运行那个不依赖网络的测试套件。

## 111: 在运行良好的项目中，测试套件通常增长得很快，运行测试花费的时间最终比我们预期的要长。你可以使用哪个 JUnit 特性来缩短运行所有测试的时间？

答案：

我们可以使用 `ParallelComputer` 运行测试，它允许在多个线程中并发执行。

## 112: 你如何允许客户以表格的形式提供测试数据，其中他们提供输入值和预期输出？

答案：

我们可以使用 `Parameterized` 运行器。它会直接从文件中读取数据，并为之创建相应的测试方法。

## 单元测试与 JUnit 特性

## 113: JUnit 为多线程测试提供原生支持吗？请解释。

答案：

不，JUnit 没有为多线程测试提供任何原生支持；相反，它将不同线程中的错误处理留给程序员和其他工具。这是因为线程控制并不容易，特别是在不了解当前领域问题的情况下。

## 114: 你如何使用 JUnit 假设来确保在不是 2011 年时停止执行测试？

答案：

```java
AssumeThat(Calendar.getInstance().get(Calendar.YEAR), is(equalTo(2011)));
```

## 115: JUnit 为存桩提供什么支持？

答案：

JUnit 不提供任何对存桩的支持，将其留给程序员和外部库。

## 116: JUnit 为模拟提供什么支持？

答案：

JUnit 不提供任何对模拟的支持，将其留给程序员和外部库。

## 117: 什么是 JUnit？

答案：

JUnit 是一个用于 Java 单元测试的测试框架。

## 118: 什么是单元测试？

答案：

单元测试是编写自动测试的行为，以与其他对象隔离的方式测试单元（通常是类）。

## 119: 你认为为每个对象的方法编写一个测试是良好的测试规范吗？

答案：

不是。这是因为良好的单元测试通常测试对象的行为，而不是测试它的单个方法，因此，一次使用几个方法作为测试对象特定功能的一部分来编写测试会更有意义。

## 120: 什么是隔离单元测试？

答案：

隔离单元测试在不依赖其其他依赖项的情况下检查该对象。这意味着即使该对象使用了网络、文件系统、数据库等，我们也不允许它实际使用这些对象，但它仍然认为正在使用它们。通过这样做，我们隔离了它们并确保任何失败都是由对象本身的错误引起的。

## 121: 你预计每秒可以运行多少个隔离的测试？

答案：

通常是一千个甚至更多，因为隔离测试通常非常快，这是确保你的测试确实隔离了它们所测试的对象的另一个优势。

## 122: 你会在什么时候为 getter 方法编写单元测试？

答案：

通常，如果 getter 方法除了返回对象之外没有进行其他工作，那么测试它是不值得的。但如果它在此之外做了任何额外工作，就应该对其进行测试。

## 123: JUnit 测试可以是抽象的。这有什么好的使用用例吗？

答案：

它可以用于测试接口。我们可以编写一个单一测试，检查实现是否遵循了接口的所有预期行为。然后，子类为每个新实现对该抽象测试进行测试，并为其提供一个具体的实例进行测试。

## 124: 什么是测试固件？

答案：

测试固件是测试环境的名称。

## 125: 为什么 JUnit 会重新实例化该类？

答案：

为了确保每个测试都在新的状态下运行。

## 126: 什么是测试覆盖率？

答案：

测试覆盖率是在测试期间执行代码的百分比。

## 127: 100% 的覆盖率能保证代码是正确的吗？

答案：

不能，它只意味着每一行代码都被执行了，并不代表所有可能的逻辑路径或边界情况都经过了测试。

## 128: 你如何过滤测试？

答案：

你可以使用类别或标签来包含或排除特定的测试。

## 129: 你如何对测试进行排序？

答案：

你可以使用 JUnit 5 中的 `@Order` 注解来指定执行顺序。

## 130: JUnit 5 的优势是什么？

答案：

它提供了更具模块化的架构和对现代功能的更好的支持。

## 131: 如何从 JUnit 4 迁移到 JUnit 5？

答案：

通过使用 `vintage` 引擎处理遗留测试。

## 132: 为什么 TestCase 的构造函数中需要参数？

答案：

在旧版本的 JUnit 中，它被用于命名测试。

## 133: Description 类的作用是什么？

答案：

`Description` 描述要运行的测试。它可以是一个单一测试，也可以是测试的组合。

## 134: 你如何创建一个执行测试的请求？

答案：

通过 `Request.request()` 方法。

## 135: 你如何创建一个执行类中测试的请求？

答案：

通过 `Request.classes()` 方法。

## 136: 你如何创建一个执行特定方法的请求？

答案：

通过 `Request.method()` 方法。

## 146: JUnitCore 如何报告它运行的测试的状态？

答案：

JUnitCore 返回一个 `Result` 对象，该对象包含了测试执行的各种不同统计数据。

## 147: 什么是 JUnit XML 格式？它的用途是什么？

答案：

JUnit XML 格式是一种用于输出测试执行结果的格式。各种工具使用该格式来解析 JUnit 结果并对其进行操作（如播放声音、显示统计数据等）。

## 148: @RunWith 注解指定了什么？

答案：

`@RunWith` 指定了用于运行给定类中测试的 `Runner` 对象。

## 149: Runner 接口代表什么？

答案：

`Runner` 运行测试并通知系统执行进度。

## 150: 什么是 ParentRunner？

答案：

`ParentRunner` 是一个通用的 `Runner` 实现，它执行 Runner 应该执行的大部分常规工作。它是扩展 JUnit 的良好起点。

# JUnit4.x

## 参数化测试

### 151: 你如何使用 Parameterized 对一组输入运行给定的测试？

答案：

```java
@RunWith(Parameterized.class)
public class DemoTest {
    private String s1;
    private String res;

    public DemoTest(String s1, String result) {
        this.s1 = s1;
        this.res = res;
    }

    @Parameters
    public static Collection<Object[]> create() {
        return Arrays.asList(new Object[][]{ { "ks", "shobana" } });
    }

    @Test
    public void mytest1() {
        System.out.println(s1 + "" + res);
    }
}
```

### 152: 参数化测试的功能是什么？

答案：

参数化测试提供了使用不同值反复运行同一个测试的功能。测试类应该被标记上 `@RunWith(Parameterized.class)` 注解。该类应包含一个带有 `@Parameters` 注解的公共静态方法。

### 153: 描述 @parameter 注解。

答案：

返回列表（数组）作为测试数据集。

示例：

```java
public static Collection<Object[]> my_data1() {
    Object[][] my_data1 = {...};
    return Arrays.asList(my_data1);
}
// collection -> Collection<Object[]>
// Array -> Arrays.asList(my_data1)
```

## 预期异常测试

### 154: 你如何使用 Junit 测试预期异常？

答案：

```java
@Test(expected = NullPointerException.class)
public void processDeal(boolean isActive) {
    deal = null;
    if (isActive == true) {
        deal = new Deal();
    }
    deal.getDealResp();
}
```

`Deal` 对象根据条件创建。因此，当调用 `getDealResp()` 函数时，会产生空指针异常。

## 时间测试

### 155: 如果测试方法在一定时间后没有返回，你将如何标记测试失败？

答案：

```java
@Test(timeout = 2000)
public void calcSalary() {
    int sal = 20;
    while (sal == 10) {
        sal++;
    }
}
```

测试将在 2000 毫秒后终止并标记为失败，因为这是一个无限循环，其耗时将超过指定的时间（2000）。

### 156: 在 Junit 中写一个简单的测试类。

答案：

```java
class DemoTest {
    @Test
    public void dispName() {
        String s1 = "shobhana";
        Assert.assertEquals(8, s1.length());
    }
}
```

### 157: Assert 类的静态导入的用途是什么？

答案：

如果静态导入了 `org.junit.Assert.*`，则可以直接使用 Assert 方法，而无需类名 Assert（如上一个问题所示）。

```java
import static org.junit.Assert.*;
....
assertEquals(8, s1.length());
```

## 忽略测试

### 158: 你将如何跳过尚未准备好测试的方法？

答案：

```java
@Ignore("This method is not ready for testing")
@Test
public void calcSalary() {
    System.out.println("Calculate salary");
}
```

### 159: 我们可以忽略需要测试的类吗？

答案：可以。该类中的所有方法都将被测试跳过。

```java
@Ignore("This class is not ready for testing")
public class DemoTest {
    @Test
    public void method1() {
      ...
    }
    @Test
    public void method2() {
      ...
    }
}
```

## 套件测试

### 160: 我们可以一起运行多个单元测试用例吗？

答案：可以。使用 Suite 测试（套件测试），可以将多个单元测试用例打包并一起运行。

### 161: 运行套件测试使用了注解？

答案：用于运行套件测试的注解有：

- `@RunWith`
- `@Suite`

### 162: 你如何在 JUnit3 中实现 Suite 测试？

答案：

我们可以在 JUnit3 中实现套件测试：

- 通过在测试类中调用 `suite()` 方法
- 可以调用或添加另一个 `Test` 和 `testsuite`
- 在下面的代码示例中，`DemoTest` 类及其测试方法 `dispName()` 将添加到套件中

```java
public static Test suite() {
  TestSuite ts = new TestSuite();
  ts.addClass(DemoTest.class);
  return ts;
}
```

### 163: 你如何在 JUnit4 中实现套件？

答案：

```java
@RunWith(Suite.class)
@SuiteClasses({
    Test1.class,
    Test2.class,
    Test3.class
})
public class MyTestSuite {}
```

### 164: 我们可以向套件传递参数吗？

答案：可以，通过使用参数化运行器或自定义套件运行器。

### 165: JUnit4 如何处理套件测试？

答案：JUnit4 使用 `@Suite` 和 `@SuiteClasses` 注解将多个测试组合。

### 166: 我们可以按特定顺序运行测试吗？

答案：可以，你可以使用 `@Order` 注解配合 `@FixedMethodOrder.class`。

### 167: 如何确保 JUnit 测试顺序？

答案：在测试方法上使用 `@Order(int)`（适用于 JUnit 5）。



### 168: JUnit 3 和 4 的区别是什么？

答案：

- JUnit 3 使用继承（扩展 `TestCase`）。
- JUnit 4 使用注解（`@Test`）。

### 169: 如何从命令行运行测试？

答案：使用 JUnit 控制台或构建工具如 Maven (`mvn test`) 或 Gradle (`gradle test`)。

### 170: 如何在 IDE 中运行测试？

答案：右键点击测试类或方法，并选择“Run 'TestName'”。

### 177: 你如何验证两个对象引用点是否指向不同的对象？

答案：

- a) 使用 `assertNotSame(...)`

```java
List fruitList = new ArrayList();
List vegList = new ArrayList();
```

```java
assertNotSame("Both objects should not be\n", fruitList, vegList);
```

### 178: 我们可以重载 assert equals 方法吗？

答案：

是的。每个函数语句都会确认测试通过或失败。

```java
public class DemoTestClass extends TestCase {
    public void calcSal() {
        assertEquals(5, (int) Math.max(5,10)); // 测试失败
        assertEquals(5, (int) Math.min(5,10)); // 测试通过
    }
}
```

### fail() 函数

### 179: 如果测试失败，你将如何显示消息？

答案：

- a) 使用 `fail()` 方法。

```java
@Test
public void calcSalTest() {
    if (sal == 0)
        fail("Test failed");
}
```

### 180: 你将如何在测试用例中抛出异常？

答案：

```java
@Test
public void calcSalTest() {
    Deal deal = null;
    try {
        if (sal > 20000) {
            deal = new Deal();
        }
        deal.goForShopping();
        fail("Test failed. Null Pointer exception.");
    } catch (Exception e) {
        ...
    }
}
```

### 处理 Throwable（异常对象）

### 181: 你将如何在不使用 fail() 的情况下处理异常？

答案：

- a) 使用 `AssertionFailedError`。
- b) 识别问题的来源而不是显示调用 `fail()` 位置。

```java
import junit.framework.AssertionFailedError;
public void DemoTest1() {
    try {
        calcSal();
    } catch (SQLException sqlex) {
        AssertionFailedError afer = new AssertionFailedError(sqlex.getMessage());
        afer.initCause(sqlex);
    }
}
```

### 182: 当从测试方法中调用声明为“受检异常”（checked exceptions）的方法时，你将如何处理？

答案：

在测试代码本身中声明这类方法是不够的。它们应该通过以下方式处理：

- a) Java 的 try/catch
- b) junit 的 Expected 属性

### 测试类与注解

### 183: JUnit 中的“Fixtures”（测试固件）一术语什么意思？

答案：

测试类包含许多测试方法，它可以扩展其他类。测试方法之间应该是相互独立的。每个测试方法的执行都会创建一个实例对象。这个实例对象被称为称为 fixtures（测试固件）。

### 184: 什么是 Testrunner（测试运行器）？

答案：

Testrunner 是：

- a) 一个运行 Test 类中定义的所有测试方法的 Java 程序
- b) 跟踪测试的成功和失败并通过图形化界面进行报告
- c) 红条表示失败，绿条表示成功

### 185: 你将如何现在测试方法之前/之后执行方法？

答案：

- a) 使用注解 `@Before` 和 `@After`
- b) 如果定义了带有 before 或 after 的方法，它们将分别在测试方法之前或之后执行

示例：

```java
public class status{
    @Before 
    void my_function1(){...}
    @Test 
    public void my_function3(){...}
    @After 
    void my_function2(){...}
}
```

在这里，测试方法是 ‘my_function3’。由于 my_function1 和 my_function2 是用注解 ‘before’ 和 ‘after’ 定义的，my_function1 将在测试方法 ‘my_function3’之前执行，my_function2 将在之后执行。

### 186: `@BeforeClass` 的目的是什么？

答案：

当一个无参数的方法定义为 `@BeforeClass` 时，它会在所有测试方法之前执行一次。在 BeforeClass 中分配的任何外部资源应在所有测试方法结束后释放。

### 187: 给出一个 ‘Before’ 注解的示例。

答案：

示例：

```java
public class status{
  @Before 
  void my_function1(){...}
  @Test 
  void my_function2(){...}
  @Test 
  public void my_function3(){...}
}
```

在这里，测试方法是 ‘my_function2’ 和 ‘my_function3’。my_function1 被定义为 ‘Before’，因此它在 ‘my_function2’ 和 ‘my_function3’ 之前执行。

### 188: `@AfterClass` 的目的是什么

答案：

当一个无参数的方法定义为 `@AfterClass` 时，它会在所有测试方法之后执行。即使 “beforeclass” 方法抛出异常，“AfterClass”也会运行。

示例：

```java
public class status{
  @Test 
  void my_function2(){...}
  @Test 
  public void my_function3(){...}
  @AfterClass 
  void my_function1(){...}
}
```

在这里，测试方法是 'my_function2' 和 'my_function3'。my_function1 被定义为 'AfterClass'。

### 189: 给出给定内容的执行顺序。

答案：

```java
public class status{
  @Before 
  void my_function1(){...}
  @Test 
  void my_function2(){...}
  @Test 
  public void my_function3(){...}
  @After 
  void my_function4(){...}
}
```

顺序：

- my_function1 (Before)
- my_function2 (Test)
- my_function3 (Test)
- my_function4 (After)

### 190: testcase 和 run 之间是什么关系？

答案：

### 191: 处理异常的方法有哪些？

答案：

- a) 使用 `fail()`
- b) 使用 try-catch 块

### 192: 你如何设置/获取测试名称？

答案：

- a) 使用 `getName()` 和 `setName()`
- b) getName() 返回测试的

### 193: ‘createResult’ 和 ‘run’ 的目的是什么？

答案：

- a) `createResult` 创建一个 Result 对象

### 194: 测试用例的结果是？

答案：

### 195: 你将如何在 JUnit 中处理异常？

答案：

### 在套件（suite）中测试吗？

答案：

- a) 使用 `setName` 方法。当用新名称作为参数调用此方法时，它将被设置为“套件”（suite）的名称。

示例：

```java
setName("suite_newn_name");
```

- b) 使用 `getName`，将检索套件名称。

示例：

```java
getName();
```

- c) 使用 `testCount()`，将检索套件中的测试数量。

示例：

```java
testCount();
```

### 200: 描述函数 ‘testAt’。

答案：

当需要在特定索引处进行测试时，使用 `testAt` 函数，它会返回指定索引处的测试。

示例：

```java
int my_test_id = 13;
testAt(my_test_id);
```

### 人力资源问题

回顾这些典型的面试问题，并思考你会如何回答它们。阅读列出的答案；你将找到最佳答案以及相关的策略和建议。

### 1: 你会如何处理负能量的同事？

答案：

每个人都必须与负能量的同事打交道——最好的办法就是保持积极。你可以尝试与该同事建立关系或以某种方式与他们交流，即使你的努力遭遇了冷遇，也必须保持积极的态度。最重要的是，要强调你绝不会让同事的负能量影响到你的工作或生产力。

### 2: 如果你目击同事在上网、看书等浪费公司时间的行为，你会怎么办？

答案：

面试官希望看到你意识到员工浪费公司时间对公司是多大的不利，并且你认为这不是可以轻视的事情。解释你将如何遵守公司政策，无论这包括你亲自与同事交谈、直接向主管汇报该行为，还是与人力资源部门的人士谈。

### 3: 你如何处理自己与其他员工之间的竞争？

答案：

健康的竞争可能是一件好事，最好专注于其中的积极方面。不要提到你与其它同事之间的冲突，转而要关注保持动力以跟上他人出色工作的动力，以及同事如何成为你一个极好的支持网络，帮助你取得新的成功。

### 4: 什么时候与同事社交是恰当的？

答案：

这个问题有两个极端答案（一直社交，或从不社交），在大多数情况下，你的面试官会希望看到你处于两者之间。与同事建立稳固的关系非常重要，但绝不能以牺牲工作完成为代价。理想情况下，关系的建立可以通过团队协作练习和特殊项目，也可以在休息室进行。

### 5: 告诉我你上一份工作中发生重大改变的经历，以及你是如何处理的。

答案：

提供该情况的背景，包括旧系统、变化是什么、如何实施以及变化的结果，并包括你对每一步的感受。确保你对旧系统的最初想法是中立的，并且你的兴奋感随着新变化的的每一步而增加，因为面试官会乐于看到你的适应能力。

### 6: 在委派任务时，你如何选择哪些任务分配给哪些团队成员？

答案：

面试官希望通过这个问题了解你的思维过程，请务必为你的选择提供详尽的理由。解释你根据每个人的个人特长来委派任务，或者你如何喜欢每个人同时正在处理的其他项目数量，以实现最理想的匹配。

### 7: 告诉我们你曾为同事或主管为你自己坚信不疑的事挺声的经历。

答案：

虽然向面试官解释冲突情况可能困难，但这是一个展示你的热情、信念以及对信仰奉献的绝佳机会。不仅向面试官解释情况，还要详细说明为什么为这个问题维护立场很重要，以及你的同事或主管是如何回应的。

### 你最可能被问到的 JUnit 面试问题

### 如何衡量工作表现，并在必要时进行调整？

回答：

这个问题的答案非常明确——肯定的——但你需要展示出你对以及为什么这很重要的认知。接受反馈和批评是一回事，但该过程中最重要的部分是将将其落实到你的日常工作中。保持良好的态度，并表达出你总是感激建设性的反馈。

### 20: 什么激发了你的灵感？

回答：

你可能会从大自然、阅读成功故事或掌握某项困难任务中获得灵感，但重要的是你的灵感应该是基于积极面的，并且在灵感出现时能够倾听并捕捉它。让这个答案主要保持在职业领域，但在适用情况下，也可以稍微延伸到个人生活中的创意活动，这反过来也能帮助你实现职业目标。

### 21: 你如何激励他人？

回答：

可能是一个困难的问题，因为通常很难察觉灵感对他人的影响。与其提供你激励过某人的具体例子，不如关注你在职业生活中所运用的通用原则，例如以身作则。如果可能，请将其与某个激励过你的人所拥有的特质联系起来，并讨论你如何在自己的工作中修改或模仿了这种特质。

### 22: 你是如何做决策的？

回答：

这是一个让你通过果断力、自信和组织能力来惊艳面试官的绝佳机会。确保你概述了一个决策过程，并强调了权衡选项的重要性，以及信任直觉的重要性。如果你能熟练且从容地回答这个问题，面试官将信任你作为一名工作者的能力。

### 23: 对你来说，最难做出的决策是什么？

回答：

解释你与决策的关系，以及你在做出选择时所采取过程的总体概述。如果你在某类特定的决策上经常感到挣扎（例如涉及他人的决策），请务必解释为什么这类决策对你来说很困难，以及你目前正致力于提高自己的技能。

### 24: 在做出艰难的决策时，你是如何收集信息的？

回答：

当你面临一个艰难的选择时，最好从尽可能多的来源收集信息。引导面试官了解你从不同领域的人那里获取信息的过程，首先听取你领域专家的建议、同事或其他客户的反馈，并对你过去的经验进行分析观察。

### 25: 告诉我也一个你做出的结果不佳决策。

回答：

诚实和透明是面试官会欣赏的优秀价值观——概述你所做的选择、你为什么那样做、你糟糕决策的结果——最后（这非常重要！）你从该决策中学习到了什么。给面试官一个理由，让他们相信你将来不会再次做出类似的决策。

### 26: 你能够快速做出决策吗？

回答：

你可能能够快速做出决策，但请确保也传达出你做出明智、周全决策的能力。讨论快速决策的重要性以及你是如何做到的，以及每个决策首先必须获得充分信息的必要性。

### 27: 什么是客户服务？

回答：

客户服务可以代表许多意义——这个问题中最重要的考虑因素是你有一个创造性的答案。通过提供一个超越基础定义的自信回答，展示你跳出框架思考的能力，这能显示出你真正考虑过自己对“照顾客户”含义的个人观点。你对客户所持有的周全考虑将说明一切。

### 28: 告诉我也一次你为客户额外付出努力的经历。

回答：

提供一个你确实付出了额外努力的例子是很重要的——小心不要把对你来说投入很大的事情与雇主本该要求你做的事情混淆。提供一个客户问题的案例、你做了什么来解决它，以及客户反馈的方式。

### 38: 你对公司监控互联网使用情况怎么看？

回答：

通常情况下，大多数公司会对员工的互联网使用情况进行某种程度的监控——面试期间并不是反抗这种做法的最佳时机。相反，应该关注积极的一面，例如它如何提高某些容易在丰富信息世界中迷失的员工的生产力。

### 39: 你对我们公司的第一印象是什么？

回答：

显然，这应该是一个积极的回答！从公司的信息或目标中挑选出几个你特别认同或与你的经验相关的关键部分，并讨论你为什么认为这些使命如此重要。

### 40: 谈谈你对业务的个人哲学。

回答：

你的个人业务哲学应该是深思熟虑过的，并且与公司的使命和目标保持一致。专注于积极方面，例如它能提供的服务以及人们在业务中获得的教训，并对你哲学的来源提供见解。

### 41: 在业务模式中，最重要的是：销售、客户服务、营销、管理等？

回答：

对于许多职位，根据你所工作的领域类型定制此答案可能是一个很好的策略，并解释为什么业务的某个方面是关键。然而，通过解释每个方面对整体功能都是不可或缺的，你可以向面试官展示更强的业务敏锐度，并可能在他的脑海中作为一个特别清醒的候选人脱颖而出。

### 42: 你如何跟进领域的新闻和新兴趋势？

回答：

面试官想看到你对你领域目前正在发生的事情有所了解。教育在大学毕业后停止是不重要的，最成功的候选人已经有了一份经常查阅的资源列表，以便他们能够保持关注并参与到发展趋势中。

### 43: 你遵守公司的社交媒体政策会有问题吗？

回答：

职场中的社交媒体问题已成为日益严重的问题，许多公司现在都制定了社交媒体的使用政策。面试官会希望确保你在遵守公司标准方面没有问题，并且在办公室内部和网上都能保持一致、专业的形象。

### 44: 谈谈目前 X 行业面临的最大问题之一。

回答：

如果你从事你的职业领域，并花时间研究趋势和新发展，你应该能够展示出对行业中不断出现的问题和潜在解决方案的认识。在参加面试之前研究一些最新新闻，并准备好充分讨论当前事件。

### 45: 你认为在我们的公司取得成功需要什么？

回答：

在面试之前研究该公司。了解公司的使命和主要目标，以及公司里一些标志性人物，并记住他们是如何取得成功的。将你的回答集中在你可以实现的特定目标上，帮助公司实现其目标。

### 46: 你在这个职业领域工作最喜欢心的部分是什么？

回答：

这个问题是一个讨论你工作中最喜欢的某些方面的机会，并突出你为什么是该职位的绝佳候选人。选择你喜欢的这些元素，这些元素要与你被聘用在该职位后将要做的内容相关。记住对工作中可能获得的机会保持热情和兴奋。

### 47: 你认为未来 10 年你的职业会发生什么变化？

回答：

如果你密切关注目前职业中正在发生的事情，并努力跟上领域的新兴趋势，你应该能够为面试官提供几个关于你的职业或领域可能向何处发展的预测。这种洞察力和这种意识水平显示了雇主非常重要的投入精神和兴趣。

### 48: 你从哪里寻找灵感？

回答：

灵感可以来自任何地方，面试官想看到你的想法同样多样化。提到你获得灵感的多个地方，或者你发现自己在头脑风暴的环境。此外，详细说明你是如何记录灵感并在以后对其进行扩展的。

### 49: 如何在职场实现创造力？

回答：



向面试官展示你能够在职场中在不违反公司价值观的情况下利用资源和进行创新能力是非常重要的。解释你的灵感通常从何而来（示例可以包括列清单或思维导图等练习），并将其与工作中某个需要创造力帮助的特定任务联系起来。

## 50：你如何推动他人创造想法？

回答：

如果你处于主管职位，这可能要求员工提交特定数量的想法，或者完成定期的头脑风暴练习，以锻炼他们的创意肌肉。然而，你也可以通过提问推动他人创造想法。

## 51：描述你的创造力。

回答：

尽量将答案控制在专业范围内，但如果你在某些令人深刻的方面有创造力背景，不要害怕将其包含进来。最好的创造力回答将与解决问题、目标设定以及在职场寻找创新方法有关（只要它们不占用工作时间）。

# 索引

## JUnit 面试题

## Rules

- 1: `JUnit` 的 Rules 功能是什么？

- 2: 如何使用 `TemporaryFolder` Rule 创建一个测试结束时会被删除的文件？

- 3: `ExternalResource` Rule 起什么作用？

- 4: 相比 setup 和 teardown，`ExternalResource` 有什么优势？

- 5: `ErrorCollector` Rule 起什么作用？

- 6: 如何使用 `Timeout` Rule 确保每个测试方法的运行时间不超过 20 毫秒？

- 7: 如何使用 `ExpectedException` Rule 确保抛出特定异常并带有特定消息？

- 8: `TestName` Rule 起什么作用？

- 9: `TestWatcher` 起什么作用？

- 10: `Verifier` Rule 起什么作用？

- 11: 如何使用 `MethodRule` 在每个测试之前打印某些内容？

- 12: 假设你有一个用 `JUnit` 写的集成测试，因为它依赖有时会失败的外部资源而是不稳定的。你将如何利用 `JUnit` 的功能来自动重试几次？

- 13: 假设我们在测试中使用了一些特殊的测试对象，我们希望它们在进入错误状态时自动失败失败，而不需要在每个测试方法中显式调用断言；例如对 mock 对象的期望。我们可以这样做吗？

- 14: 我们很多时候使用随机数据编写测试以增加发现漏洞的机会并进行探索性测试。此类测试的主要问题是它失败后并不保证再次失败。我们如何让 `JUnit` 帮助我们重现这些失败的测试？

- 15: 如何通过自动让突然比之前运行慢例如 50% 的测试失败来跟踪系统性能？

- 16: 描述允许 Rule 实现注入其逻辑到测试运行中的接口。

- 17: 你如何添加自动日志来打印每个测试的时间

# 你可能会被问到的 JUnit 面试题

18: 单个测试类中可以提供多少条规则 (Rules)?

## 断言 (Assertions)

19: 你如何在测试中断言某个条件为真？

20: 为什么断言方法有一个可选的 `String` 类型参数？

21: 如果在同一个测试方法中有多个断言且其中一个失败了，下一个还会执行吗？为什么？

22: `assertEquals` 的作用是什么什么？

23: 为什么同时需要 `assertTrue()` 和 `assertEquals()`？

24: `assertEquals()` 和 `assertSame()` 之间有什么区别？

25: 断言两个数组相等的正确方法是什么？为什么？

26: 如果你在逻辑上得出测试应该失败的结论，停止它的正确方法是什么？在不使用 `assertTrue(false)` 等方法的情况下？为什么？

27: 为什么用于 double 类型的 `assertEquals()` 方法接收三个 double 参数？

28: 你将如何在测试中断言某个方法被抛出异常？

29: 为什么在接下来的示例中使用 `fail()`？

30: `assertEquals()` 的参数顺序重要吗？

31: `assertThat()` 是什么？

32: 使用 `assertThat()` 断言变量等于字符串 "hello"。

33: 使用 `assertThat()` 断言变量是某个特定类的实例。

34: 使用 `assertThat()` 断言字符串包含 "abc"。

35: 使用 `assertThat()` 断言列表包含 "Hello"。

36: 使用 `assertThat()` 断言列表包含 "Foo" 或 "Bar"。

37: 使用 `assertThat()` 断言列表既包含 "Foo" 又包含 "Bar"。

38: 使用 `assertThat()` 断言一个数字大于 4。

39: 使用 `assertThat()` 断言一个字符串在忽略大小写的情况下等于字符串 "Foo"。

40: 使用 `assertThat()` 断言变量为 `null`。

41: 编写一个自定义的匹配器（matcher）来断言一个整数在两个数字之间。

42: 使用 `assertThat()` 断言 Map 包含键 "foo"。

43: 使用 `assertThat()` 断言 Map 包含键 "foo"。（注：原文重复）

44: 使用 `assertThat()` 断言 Map 包含值 "bar"。

45: 使用 `assertThat()` 断言集合中的所有字符串都等于 "foo"。

46: `assertFalse` 做了什么？

47: `fail(fail)` 做了什么？

48: `assertNotNull()` 做了什么？

49: `assertNull()` 做了什么？

50: `assertSame()` 做了什么？

51: `assertNotSame()` 做了什么？

52: `JUnit` 的所有断言在哪里声明？它们是如何对测试类可见的？

53: 抛出 `AssertionError` 的测试结果是什么？为什么？

54: 你可以在 Java 中直接使用 "assert" 关键字吗？

55: 什么是 Hamcrest 匹配器 (Matcher)？

56: 为什么这个断言不会通过？`assertEquals(new MyClass(1), new MyClass(1))`

57: 新的 `assertThat()` 语法会废弃旧的断言吗？

58: `JUnit` 如何实现基本数据类型的断言？

59: 有办法让 "assert" 关键字与 `JUnit` 配合工作吗？

60: 针对大于数字？

61: 你如何在 JVM 中启用断言（使用 assert 关键字）？

62: `JUnit` 同时提供 `assertTrue()` 和 `assertFalse()` 的原因是什么？

63: 你在单个测试方法中可以放置多少个断言？

## 测试类 (Test Classes)

64: 如何标记一个方法为测试方法？

65: 测试方法有效的可见性是什么？为什么？

66: 测试方法有效的返回类型是什么？

67: `JUnit` 是否要求测试方法必须以 "test" 开头命名？

68: 测试类需要特定的注解吗？

69: 如何标记一组测试以便在套件（suite）中运行？

70: 测试方法中必须捕获所有检查异常 (checked exceptions) 吗？

71: 你如何指定某个测试应该在给定的时间范围内完成？

72: 普通测试类的构造函数可以有参数吗？

73: 测试类中的 set up 方法是什么？

74: 测试类中的 tear down 方法是什么？

75: 你必须设置 set up 和 tear down 方法吗？为什么？

76: 如果你指定了 tear down 方法，也必须声明 set up 方法吗？

77: 你如何指定一个方法为 set up 方法？

78: 你如何指定一个方法为 tear down 方法？

79: 你如何指定对整个测试类只执行一次的 set up 代码？

80: 你如何指定对整个测试类只执行一次的 tear down 代码？

81. 指定一个有效的 `@BeforeClass` 和 `@AfterClass` 方法声明。

## 运行测试 (Running Tests)

82: 如果在同一个类中有多个测试方法且其中一个失败了，下一个还会执行吗？为什么？

83: 测试方法所有可能的可能有哪些？

84: 失败 (failure) 和错误 (error) 之间有什么区别？

85: 下述测试会通过吗？为什么？

86: set up 方法在什么时候运行？

87: tear down 方法什么时候运行？

88: 如果测试失败，tear down 方法会运行吗？

89: （原文缺失或由上下文暗示）

90: 如果抛出异常，tear down 方法会运行吗？

91: 如果测试通过，tear down 方法会运行吗？

92: 如果测试失败，tear down 方法会运行吗？

93: 如果测试抛出异常，tear down 方法会运行吗？

94: set up 方法被调用了多少次？

95: tear down 方法被调用了多少次？

96: 静态成员之间共享的吗？

97: 编写一个并行执行测试的方法。

98: `Enclosed` 运行器做了什么？

99: `Categories` 运行器启用了什么？

100: 你如何使用 `Categories` 创建一个套件？

101: 在一次运行中可以提供多个类别吗？

102: 可以同时提供包含类别和排除类别吗？

103: 你如何标记测试不运行？

104: `@Ignore` 注解可以应用于方法以外的地方吗？

105: 参数化运行器 (Parameterized Runner) 做了什么？

106: 什么是 `ParallelComputer`？

107: `ParallelComputer` 的类和方法之间有什么区别？

108: 类中测试方法的执行顺序是怎样的？

109: 如果一个类包含 setup 或 tear down 但没有测试方法，尝试运行它会发生什么？

110: 如果某些测试需要网络连接才能运行，你如何分离它们，以便在地铁上没有网络的情况下可以运行所有不需要连接的测试？

111. 在良好的项目中，测试套件通常增长很快，运行测试花费的时间超过预期。你可以使用哪种 `JUnit` 功能来缩短运行时间？

112. 你如何允许客户以输入值和预期输出的形式提供测试数据？

113. `JUnit` 支持多线程测试吗？

114. 你如何使用假设 (assumption) 来确保在不是 2011 年时不执行测试？

115. `JUnit` 为存桩 (stubbing) 提供什么支持？

116. `JUnit` 为模拟 (mocking) 提供什么支持？

117. 什么是 `JUnit`？

118. 什么是单元测试？

119. 你认为为每个对象的方法编写测试是良好的测试做法吗？

# 你可能会被到的 JUnit 面试题

- 129: 当一个 void 函数不通过“参数”或“实例变量”返回数据时，测试该方法的其他方法有哪些？

## JUnit 3

- 130: 你将如何声明一个旧式测试类（`JUnit 3` 格式）以便在 `JUnit 4` 中执行？

- 131: 迁移到 `JUnit 4` 风格的测试用（不再需要继承 `TestCase`）有什么好处？

- 132: 为什么 `JUnit 3` 中 `TestCase` 的构造函数需要一个 String 参数？

## JUnit API

- 133: `JUnit` 中 `Request` 对象的作用是什么？

- 134: 你如何创建一个请求来执行某个类中的测试？

- 135: 你如何创建一个请求来执行一组类的测试？

- 136: 你如何创建一个请求来执行类中的某个特定方法？

- 137: `Description` 类的作用是什么？

- 138: 如何从 `Request` 对象中过滤某些测试？

- 139: 如何按特定顺序对测试进行排序？

- 140: 假设我们想要过滤复合测试的 `Descriptions`，你如何知道一个描述包含多个测试？

- 141: 假设我们想要过滤原子测试的 `Descriptions`，你如何知道一个描述是否包含单个测试？

- 142: 如何过滤总数少于 10 个测试的 `Descriptions`？

- 143: 什么是 `RunListener`？它如何被使用？

- 144: 附加在测试运行时执行逻辑以指示进度的最佳方法是什么？

- 145: 当测试被忽略时（例如因为标记了 `@Ignore`），`RunListener` 会收到通知 吗？

- 146: `JUnitCore` 如何报告它所运行的测试状态？

- 147: 什么是 JUnit XML 格式？它的用途是什么？

- 148: `@RunWith` 注解指定了什么？

- 149: `Runner` 接口代表什么？

- 150: 什么是 `ParentRunner`？

## JUnit4.x

- 151: 你如何使用 `Parameterized` 来针对几个输入运行一个给定的测试？

- 152: 参数化测试的功能是什么？

- 153: 描述 `@Parameter` 注解。

- 154: 你将如何使用 `JUnit` 测试预期的异常？

- 155: 如果测试方法在一定时间后没有返回，将如何标记测试失败？

- 156: 在 `JUnit` 中编写一个简单的测试类。

- 157: 静态导入（static import）Assert 类的作用是什么？

- 158: 你将如何跳过一个尚未准备好测试的方法？

- 159: 我们可以忽略一个需要测试的类吗？

- 160: 我们如何同时运行多个单元测试用例？

- 161: 用于运行套件测试（suite）的注解有哪些？

- 162: 你如何在 `JUnit3` 中实现套件测试？

- 163: 你将如何在 `JUnit4` 中使用注解实现套件测试？

- 164: 在 `JUnit3` 中，你如何将一个类中存在的测试套件方法添加到另一个类的 `suite()` 方法中？

- 165: 你能让 `JUnit3` 的 `suite()` 方法在 `JUnit4` 中工作吗？

- 166: 是否需要为每个需要测试的类编写一个单独的测试类？

- 167: 哪些测试方法应该被声明为静态（static）？

- 168: `JUnit3` 支持多少测试运行器（test runners）？

- 169: 你可以测试类中的私有方法吗？

- 170: 我们可以如何测试一个方法？

- 171: 我们如何运行多个单元测试用例？

- 172: 我们如何运行测试？

- 173: 如何按顺序排序测试？

- 174: 如何从 `Request` 对象中过滤出某些测试？

- 175: 如何知道一个描述是否包含多个测试？

- 176: 如何知道一个描述是否包含单个测试？

- 177: 如何过滤总数少于 10 个测试的 `Descriptions`？

- 178: 什么是 `RunListener`？它如何被使用？

- 179: 附加在测试运行时执行逻辑以指示进度的最佳方法是什么？

- 180: 当测试被忽略时（例如因为标记了 `@Ignore`），`RunListener` 会收到通知 吗？

- 181: `JUnitCore` 如何报告它所运行的测试状态？

- 182: 什么是 JUnit XML 格式？它的用途是什么？

- 183: `@RunWith` 注解指定了什么？

- 184: `Runner` 接口代表什么？

- 185: 什么是 `ParentRunner`？

- 186: 你如何使用 `Parameterized` 来针对几个输入运行一个给定的测试？

- 187: 参数化测试的功能是什么？

- 188: 描述 `@Parameter` 注解。

- 189: 你将如何使用 `JUnit` 测试预期的异常？

- 190: 如果测试方法在一定时间后没有返回，将如何标记测试失败？

- 191: 在 `JUnit` 中编写一个简单的测试类。

- 192: 静态导入（static import）Assert 类的作用是什么？

- 193: 你将跳过一个尚未准备好测试的方法？

- 194: 我们可以忽略一个需要测试的类吗？

- 195: 我们如何同时运行多个单元测试用例？

- 196: 用于运行套件测试（suite）的注解有哪些？

- 197: 你如何在 `JUnit3` 中实现套件测试？

- 198: 你将如何在 `JUnit4` 中使用注解实现套件测试？

- 199: 在 `JUnit3` 中，你如何将一个类中存在的测试套件方法添加到另一个类的 `suite()` 方法中？

- 200: 你能让 `JUnit3` 的 `suite()` 方法在 `JUnit4` 中工作吗？

## 测试类与注解

- 1: 是否需要为每个需要测试的类编写一个单独的测试类？

- 2: 哪些测试方法应该被声明为静态（static）？

- 3: `JUnit3` 支持多少测试运行器（test runners）？

- 4: 你可以测试类中的私有方法吗？

- 5: 我们可以如何测试一个方法？

- 6: 我们如何运行多个单元测试用例？

- 7: 我们如何运行测试？

- 8: 如何按特定顺序排序测试？

- 9: 如何从 `Request` 对象中过滤出某些测试？

- 10: 如何知道一个描述是否包含多个测试？

- 11: 如何知道一个描述是否包含单个测试？

- 12: 如何过滤总数少于 10 个测试的 `Descriptions`？

- 13: 什么是 `RunListener`？它如何被使用？

- 14: 附加在测试运行时执行逻辑以指示进度的最佳方法是什么？

- 15: 当测试被忽略时（例如因为标记了 `@Ignore`），`RunListener` 会收到通知 吗？

- 16: `JUnitCore` 如何报告它所运行的测试状态？

- 17: 什么是 JUnit XML 格式？它的用途是什么？

- 18: `@RunWith` 注解指定了什么？

- 19: `Runner` 接口代表什么？

- 20: 什么是 `ParentRunner`？

- 21: 你如何使用 `Parameterized` 来针对几个输入运行一个给定的测试？

- 22: 参数化测试的功能是什么？

- 23: 描述 `@Parameter` 注解。

- 24: 你将如何使用 `JUnit` 测试预期的异常？

- 25: 如果测试方法在一定时间后没有返回，将如何标记测试失败？

- 26: 在 `JUnit` 中编写一个简单的测试类。



## JUnit 面试题

- 27: 静态导入（`static import`）`Assert` 类的作用是什么？
- 28: 你将如何跳过一个尚未准备好测试的方法？
- 29: 我们可以忽略一个需要测试的类吗？
- 30: 我们如何同时运行多个单元测试用例？
- 31: 用于运行套件测试（`suite`）的注解有哪些？
- 32: 你如何在 JUnit3 中实现套件测试？
- 33: 你将如何在 JUnit4 中使用注解实现套件测试？
- 34: 在 JUnit3 中，你如何将一个类中存在的测试套件方法添加到另一个类的 `suite()` 方法中？
- 35: 你能让 JUnit3 的 `suite()` 方法在 JUnit4 中工作吗？

## HR 面试题

- 1: 你如何处理负面的同事？
- 2: 你在同事在上网或看书时如何处理？
- 3: 你如何处理同事之间的竞争？
- 4: 什么时候与同事社交是合适的？
- 5: 描述一次工作发生重大变化时的经历。
- 6: 在分配任务时，你如何决定分配给哪些成员？
- 7: 描述一次你为坚信的事情维护立场。
- 8: 描述一次帮助他人完成工作的经历。
- 9: 团队合作的挑战是什么？
- 10: 你是否重视多样性？
- 11: 你如何处理多样性？
- 12: 获得新客户还是留住老客户更好？
- 13: 描述一次你为了完成工作加班的经历。
- 14: 描述一次你表现超出要求的经历。
- 15: 你对工作的态度是什么？
- 16: 你会把工作带回家吗？
- 17: 描述你典型工作的一天。
- 18: 描述一次你为客户额外付出的努力。
- 19: 你是否愿意接受对你的反馈和批评，并进行调整？
- 20: 是什么在激励你？
- 21: 你如何激励他人？
- 22: 你如何做决定？
- 23: 对你来说最难的决定是什么？
- 24: 在做出艰难决定时，你如何收集信息？
- 25: 描述一次你没有达到预期的决策。
- 26: 你能够快速决定吗？
- 27: 什么是客户服务？
- 28: 描述一次你为客户额外付出的努力。
- 29: 你如何获得客户的信任？
- 30: 描述一次当客户感到愤怒或激动时，你是如何处理的。

## 相关面试题系列

- 1. 你可能被问到的 .NET 面试题
- 2. 你可能被问到的 200 道面试题
- 3. 你可能被问到的 Access VBA 编程面试题
- 4. 你可能被问到的 Adobe Cold 面题
- 5. 你可能被问到的高级 Excel 面题
- 6. 你可能被问到的高级 JAVA 面题
- 7. 你可能被问到的高级 SAS 面题
- 8. 你可能被问到的 AJAX 面题
- 9. 你可能被问到的算法面试题
- 10. 你可能被问到的 Android 开发面试题
- 11. 你可能被问到的 Ant & Maven 面题
- 12. 你可能被问到的 Apache Web Server 面题
- 13. 你可能被问到的人工智能面试题
- 14. 你可能被问到的 ASP.NET 面题
- 15. 你可能被问到的自动化软件测试面试题
- 16. 你可能被问到的 Base SAS 面题
- 17. 你可能被问到的 BEA WebLogic Server 面题
- 18. 你可能被问到的 C & C++ 面试题
- 19. 你可能被问到的 C# 面试题
- 20. 你可能被问到的 C++ 内部面试题
- 21. 你可能被问到的 CCNA 面题
- 22. 你可能被问到的云计算面试题
- 23. 你可能被问到的计算机架构面试题
- 24. 你可能被问到的计算机网络面试题
- 25. 你可能被问到的 Core Java 面题
- 26. 你可能被问到的数据结构与算法面试题
- 27. 你可能被问到的数据仓库面试题
- 28. 你可能被问到的 EJB 3.0 面题
- 29. 你可能被问到的 Entity Framework 面题
- 30. 你可能被问到的 Fedora & RHEL 面题
- 31. 你可能被问到的 GNU 开发面试题
- 32. 你可能被问到的 Hibernate, Spring & Struts 面题
- 33. 你可能被问到的 HTML, XML 和 CSS 面题
- 34. 你可能被问到的 HTML5 面题
- 35. 你可能被问到的 IBM WebSphere 服务器面试题
- 36. 你可能被问到的 iOS SDK 设计模式面试题
- 37. 你可能被问到的 Java / J2EE 面题
- 38. 你可能被问到的 Java / J2EE 面题
- 39. 你可能被问到的 Java Messaging Service 面题
- 40. 你可能被问到的 JavaScript 面题
- 41. 你可能被问到的 JavaFaces 面题
- 42. 你可能被问到的 JDBC 面题
- 43. 你可能被问到的 jQuery 面题
- 44. 你可能被问到的 JSP-Servlet 面题
- 45. 你可能被问到的 JUnit 面题
- 46. 你可能被问到的 Linux 命令面试题
- 47. 你可能被问到的 Linux 面题
- 48. 你可能被问到的 Linux 系统管理员面试题
- 49. 你可能被问到的 Mac OS X Lion 面题
- 50. 你可能被问到的 Mac OS X Snow Leopard 面题
- 51. 你可能被问到的 Microsoft Access 面题
- 52. 你可能被问到的 Microsoft Excel 面题
- 53. 你可能被问到的 Microsoft PowerPoint 面题
- 54. 你可能被问到的 Microsoft Word 面题
- 55. 你可能被问到的 MySQL 面题
- 56. 你可能被问到的 NetSuite 面题
- 57. 你可能被问到的网络面试题
- 58. 你可能被问到的 OOP 面题
- 59. 你可能被问到的操作系统面试题
- 60. 你可能被问到的 Oracle DBA 面题
- 61. 你可能被问到的 Oracle EBS 面题
- 62. 你可能被问到的 Oracle PL/SQL 面题
- 63. 你可能被问到的 Perl 编程面试题
- 64. 你可能被问到的 PHP 面题
- 65. 你可能被问到的 PMP 面题
- 66. 你可能被问到的 Python 面题
- 67. 你可能被问到的 RESTful Java Web 面题
- 68. 你可能被问到的 Ruby 面题
- 69. 你可能被问到的 Ruby on Rails 面题
- 70. 你可能被问到的 SAP ABAP 面题
- 71. 你可能被问到的 SAP HANA 面题
- 72. 你可能被问到的 SAS 编程指南面试题
- 73. 你可能被问到的 Selenium 测试面试题
- 74. 你可能被问到的 Silverlight 面题
- 75. 你可能被问到的软件仓库面试题
- 76. 你可能被问到的软件测试面试题
- 77. 你可能被问到的 SQL Server 面题
- 78. 你可能被问到的 Tomcat 面题
- 79. 你可能被问到的 UML 面题
- 80. 你可能被问到的 Unix 面题
- 81. 你可能被问到的 Unix Shell 编程面试题
- 82. 你可能被问到的 VB.NET 面题
- 83. 你可能被问到的 Windows Server 2008 R2 面题
- 84. 你可能被问到的 XLQP, XSLT, XPath, XFORMS 及查询面试题
- 85. 你可能被问到的 XML 面题

访问完整列表请访问：`www.vibrantpublishers.com`

## 注意事项
