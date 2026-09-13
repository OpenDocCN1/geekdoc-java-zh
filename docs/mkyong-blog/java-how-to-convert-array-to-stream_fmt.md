
# Java——如何将数组转换成流

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/java8/java-how-to-convert-array-to-stream/>

在 Java 8 中，可以使用`Arrays.stream`或`Stream.of`将数组转换成流。

## 1. 对象数组

对于对象数组，`Arrays.stream`和`Stream.of`返回相同的输出。

`TestJava8.java`

```java
package com.mkyong.java8;

import java.util.Arrays;
import java.util.stream.Stream;

public class TestJava8 {

    public static void main(String[] args) {

        String[] array = {"a", "b", "c", "d", "e"};

        //Arrays.stream
        Stream<String> stream1 = Arrays.stream(array);
        stream1.forEach(x -> System.out.println(x));

        //Stream.of
        Stream<String> stream2 = Stream.of(array);
        stream2.forEach(x -> System.out.println(x));
    }

}
```

输出

```java
a
b
c
d
e
a
b
c
d
e
```

查看 JDK 源代码。

`Arrays.java`

```java
/**
 * Returns a sequential {@link Stream} with the specified array as its
 * source.
 *
 * @param <T> The type of the array elements
 * @param array The array, assumed to be unmodified during use
 * @return a {@code Stream} for the array
 * @since 1.8
 */
public static <T> Stream<T> stream(T[] array) {
    return stream(array, 0, array.length);
}
```

`Stream.java`

```java
/**
 * Returns a sequential ordered stream whose elements are the specified values.
 *
 * @param <T> the type of stream elements
 * @param values the elements of the new stream
 * @return the new stream
 */
@SafeVarargs
@SuppressWarnings("varargs") // Creating a stream from an array is safe
public static<T> Stream<T> of(T... values) {
    return Arrays.stream(values);
}
```

**注意**

对于对象数组，`Stream.of`方法在内部调用`Arrays.stream`。

## 2. 原始数组

对于原始数组，`Arrays.stream`和`Stream.of`将返回不同的输出。

`TestJava8.java`

```java
package com.mkyong.java8;

import java.util.Arrays;
import java.util.stream.IntStream;
import java.util.stream.Stream;

public class TestJava8 {

    public static void main(String[] args) {

        int[] intArray = {1, 2, 3, 4, 5};

        // 1\. Arrays.stream -> IntStream
        IntStream intStream1 = Arrays.stream(intArray);
        intStream1.forEach(x -> System.out.println(x));

        // 2\. Stream.of -> Stream<int[]>
        Stream<int[]> temp = Stream.of(intArray);

        // Cant print Stream<int[]> directly, convert / flat it to IntStream
        IntStream intStream2 = temp.flatMapToInt(x -> Arrays.stream(x));
        intStream2.forEach(x -> System.out.println(x));

    }

}
```

输出

```java
1
2
3
4
5
1
2
3
4
5
```

查看 JDK 源代码。

`Arrays.java`

```java
/**
 * Returns a sequential {@link IntStream} with the specified array as its
 * source.
 *
 * @param array the array, assumed to be unmodified during use
 * @return an {@code IntStream} for the array
 * @since 1.8
 */
public static IntStream stream(int[] array) {
    return stream(array, 0, array.length);
}
```

`Stream.java`

```java
/**
 * Returns a sequential {@code Stream} containing a single element.
 *
 * @param t the single element
 * @param <T> the type of stream elements
 * @return a singleton sequential stream
 */
public static<T> Stream<T> of(T t) {
    return StreamSupport.stream(new Streams.StreamBuilderImpl<>(t), false);
}
```

**该用哪个？**

对于对象数组，两者都调用相同的`Arrays.stream`（参考示例 1，JDK 源代码）。对于原始数组，我也更倾向于使用`Arrays.stream`，因为它直接返回固定大小的`IntStream`，更容易操作。

*使用甲骨文 JDK 1.8.0_77 测试的 PS*

## 参考

1. [数组 JavaDoc](http://web.archive.org/web/20220320175655/https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html)
2. [流 JavaDoc](http://web.archive.org/web/20220320175655/https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html)
3. [如何打印一个数组，java 和 java 8 的例子](http://web.archive.org/web/20220320175655/http://www.mkyong.com/java/java-how-to-print-an-array/)
