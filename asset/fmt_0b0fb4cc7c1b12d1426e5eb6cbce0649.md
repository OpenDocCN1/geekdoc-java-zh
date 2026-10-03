
在 `main` 方法（第 6–14 行）中，使用整数 3、4 和 5 调用了 `maximum`。当编译器遇到这些内容时，它首先寻找接受三个 `int` 参数的方法。不存在这样的方法，因此编译器寻找可以使用的泛型方法并找到了 `generic maximum`。然而，请记住，泛型方法的参数必须是引用类型。因此，编译器将三个 `int` 值装箱为 `Integer` 对象，并指定它们传递给 `maximum`。类 `Integer`（包 `java.lang`）实现了 `Comparable<Integer>` 接口，使得方法 `compareTo` 按照 `Integer` 的顺序比较两个值。当返回表示最大值的 `Integer` 时，我们使用 `%d` 格式说明符输出它，这会输出一个 `int` 原型类型值。方法的返回值作为 `int` 输出。

第 11 行传递给 `maximum` 的 `double` 参数也发生了类似的过程。每个 `double` 都被自动装箱为 `Double` 对象并传递给 `maximum`。再次，这是允许的，因为 `Double`（包 `java.lang`）实现了 `Comparable<Double>` 接口。返回的 `Double` 返回并使用格式说明符 `%f` 输出，这会输出一个 `double` 原型类型值。因此，`maximum` 的返回值被拆箱并作为 `double` 输出。第 13 行对 `maximum` 的调用接收了三个 `String`，它们也是 `Comparable<String>` 对象。我们特意在每次方法调用中将最大值放置在不同的位置（第 9、11 和 13 行），以说明泛型方法始终能找到最大值，无论它在参数列表中的位置如何。

# 第 20 章 泛型类与方法

## 擦除与类型参数的上界

当编译器将 `maximum` 翻译成字节码时，它会进行擦除，用实际类型替换类型参数。在 20.3 中，所有泛型类型都被替换为 `Object`。实际上，所有类型参数都被替换为类型参数的上界，该上界在类型参数部分中指定。20.6 通过展示删除类型参数部分后的方法源代码，说明了 `maximum` 类型的擦除，类型参数 `T` 被替换为上界。`Comparable<>` 的擦除结果为 `Comparable`。

```java
public static Comparable maximum(Comparable x, Comparable y, Comparable z)
{
    Comparable max = x; // 假设 x 最初是最大的
    if (y.compareTo(max) > 0)
        max = y; // y 是目前
    if (z.compareTo(max) > 0)
        max = z; // z 是最大的
    return max; // 返回最大的对象
}
```

**图 20.** 执行编译器擦除后的泛型方法。

擦除后，方法 `maximum` 指定它返回 `Comparable` 类型。然而，调用方法并不期望接收一个 `Comparable`。它期望接收与传递 `maximum` 的参数相同类型——在本例中为 `Integer`、`Double` 或 `String`。当编译器替换方法声明中的类型参数信息时，它也会在每次方法调用中插入强制转换操作，以确保返回值是调用者预期的类型。因此，第 9 行（20.5）对 `maximum` 的调用之前有一个 `Integer` 转换，如下：

> `(Integer) maximum(3, 4, 5)`

第 11 行对 `maximum` 的调用之前有一个 `Double` 转换，如下：

> `(Double) maximum(6.6, 8.8, 7.7)`

第 13 行对 `maximum` 的调用之前有一个 `String` 转换，如下：

> `(String) maximum("pear", "apple", "orange")`

在每情况下，泛型方法的类型都是从参数推出的。

## 20.5 重载泛型方法

泛型方法可以像其他方法一样重载。泛型方法可以使用相同的名称但不同的参数进行重载。例如，泛型方法 20.3 可以重载为。

## 20.6 泛型类

数据结构的概念（如栈）可以独立于类型进行理解。泛型为软件重用提供了很好的机会。一旦你有了泛型类，可以使用简单的符号来指示应该使用的类型。

```java
// Fig. 20.7: Stack.java
// Stack 泛型类声明
import java.util.ArrayList;
public class Stack<T> {
    private final ArrayList<T> elements; // ArrayList 栈元素

    // 无参数构造函数创建一个默认大小的栈
    public Stack() {
        this(10); // 默认栈大小
    }

    // 构造函数创建一个指定数量元素的栈
    public Stack(int capacity) {
        int initCapacity = capacity > 0 ? capacity : 10; // 校验
        elements = new ArrayList<T>(initCapacity); // 创建 ArrayList
    }

    // 将元素推入栈中
    public void push(T pushValue) {
        elements.add(pushValue); // 将 pushValue 置于 Stack 上
    }

    // 如果栈不为空则返回栈顶元素；抛出 EmptyStackException
    public T pop() {
        if (elements.isEmpty()) // 如果栈为空
            throw new EmptyStackException("Stack is empty, cannot pop");
        return elements.remove(elements.size() - 1);
    } // end Stack<T>
}
```

**图 20.7** Stack 泛型类声明。

方法 `push` (23–26) 使用 `ArrayList` 方法将推入的项附加到 `ArrayList` 的末尾。`ArrayList` 中的最后一个元素代表栈的顶部（top）。

方法 `pop` (29–36) 首先确定是否正尝试从空栈中弹出元素。如果是，第 32 行将抛出 `EmptyStackException`（在图 20.8 中定义），否则，图 20.7 中的第 35 行通过移除底层 `ArrayList` 中的最后一个元素来返回栈顶顶部元素。

`EmptyStackException`（图 20.8）提供了一个无参数构造函数和一个单参数构造函数。无参数构造函数设置了默认错误消息，单参数构造函数设置了自定义错误消息。

作为泛型方法，当编译一个泛型类时，编译器会对该类的类型参数进行擦除，并将其替换为它们的上界。对于类 `Stack`（图 20.7），未指定上界，因此使用了默认的上界 `Object`。泛型类类型参数的作用范围是整个类。然而，类型参数不能用于类静态变量的声明。

```java
// Fig. 20.8: EmptyStackException.java
// EmptyStackException 类声明
public class EmptyStackException extends RuntimeException
{
    // 无参数构造函数
    public EmptyStackException()
    {
        this("Stack is empty");
    }
    // 单参数构造函数
    public EmptyStackException(String message)
    {
        super(message);
    }
} // end class EmptyStackException
```

**图 20.8** 图 20.7 的泛型类

测试使用 `Stack` 泛型（图 20.7）的图 20.7 泛型类。现在，让我们考虑应用（图 20.9）并初始化 `Stack<Double>`（读作 "Stack of Double"）和 `Stack<Integer>`（读作 "Stack of Integer"）类型的变量。`Double` 和 `Integer` 类型在图 20.7 中是未知的，而是栈的类型参数。编译器将它们替换为类型参数，以便它可以执行类型检查并在必要时插入强制转换操作。我们稍后将详细讨论强制转换操作。第 12–13 行实例化了容量为 5 的 `doubleStack` 和容量为 10（默认）的 `integerStack`。第 16–21 行调用方法 `testPushDouble`（第 25–36 行）、`testPopDouble`（第 39–59 行）、`testPushInteger`（第 62–73 行）和 `testPopInteger`（第 76–96 行），来演示此示例中的两个栈。

```java
// Fig. 20.9: StackTest.java
// Stack 泛型类测试程序
public class StackTest
{
    public static void main(String[] args)
    {
        double[] doubleElements = {1.1, 2.2, 3.3, 4.4, 5.5};
        int[] integerElements = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        // 创建一个 Stack<Double> 和一个 Stack<Integer>
        Stack<Double> doubleStack = new Stack<>(5);
        Stack<Integer> integerStack = new Stack<>();
    }
}
```

**图 20.9** Stack 泛型类测试程序。（3 部分第 1 部分）。

```java
// 将 doubleElements 的元素推入 doubleStack
testPushDouble(doubleStack, doubleElements);
testPopDouble(doubleStack); // 从 doubleStack 弹出
```

```java
// 将 integerElements 的元素推入 integerStack
testPushInteger(integerStack, integerElements);
testPopInteger(integerStack); // 从 integerStack 弹出
```

```java
// 测试 double 栈的 push 方法
private static void testPushDouble(
    Stack<Double> stack, double[] values)
{
    System.out.printf("%nPushing elements onto doubleStack%n");
}
```

```java
// 将元素推入栈中
for (double value : values) 
{
    System.out.printf("%.1f ", value);
    stack.push(value); // 推入 doubleStack
}
}
```

```java
// 测试 double 栈的 pop 方法
private static void testPopDouble(Stack<Double> stack)
{
    // 从栈弹出元素
    try {
        System.out.printf("%nPopping elements from doubleStack%n");
        double popValue = stack.pop(); // 从栈中元素
        // 移除栈中所有元素
        while (true) {
            popValue = stack.pop(); // 从 doubleStack 弹出
            System.out.printf("%.1f ", popValue);
        }
    } catch (EmptyStackException emptyStackException) {
        System.err.println();
        emptyStackException.printStackTrace();
    }
}
```

```java
// 测试 integer 栈的 push 方法
private static void testPushInteger(
    Stack<Integer> stack, int[] values)
{
    System.out.printf("%nPushing elements onto integerStack%n");
}
```

Fig. 20.9 | Stack 泛型类测试程序。（3 部分第 2 部分。）

```java
// 将元素推入栈中
for (int value : values)
{
    System.out.printf("%d ", value);
    stack.push(value); // 推入 integerStack
}
}
```

```java
// 测试 integer 栈的 pop 方法
private static void testPopInteger(Stack<Integer> stack)
{
    // 从栈弹出元素
    try {
        System.out.printf("%nPopping elements from integerStack%n");
        int popValue = stack.pop(); // 从栈中元素
        // 移除栈中所有元素
        while (true) {
            popValue = stack.pop(); // 从 integerStack 弹出
            System.out.printf("%d ", popValue);
        }
    } catch (EmptyStackException emptyStackException) {
        System.err.println();
        emptyStackException.printStackTrace();
    }
}
```
