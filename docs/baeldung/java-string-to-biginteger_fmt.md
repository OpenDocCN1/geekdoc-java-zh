
# 在 Java 中将字符串转换为大整数

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-string-to-biginteger>

## 1. 概观

在本教程中，我们将演示如何将`String`转换为`BigInteger`。`BigInteger`通常用于处理非常大的数值，这通常是任意算术计算的结果。

## 2. 转换十进制（基数为 10）整数字符串

为了将一个小数`String`转换成`BigInteger`，我们将**使用`BigInteger(String value)`构造函数**：

```
String inputString = "878";
BigInteger result = new BigInteger(inputString);
assertEquals("878", result.toString());
```

## 3. 转换非十进制整数字符串

**当使用默认的`BigInteger(String value)`构造函数**将一个非十进制的`String`转换成十六进制时，我们可能会得到一个`NumberFormatException`：

```
String inputString = "290f98";
new BigInteger(inputString);
```

这个异常可以用两种方式处理。

一种方法是**使用`BigInteger(String value, int radix)`构造函数**：

```
String inputString = "290f98";
BigInteger result = new BigInteger(inputString, 16);
assertEquals("2690968", result.toString());
```

在本例中，我们将基数或基数指定为 16，用于将十六进制转换为十进制。

另一种方法是先**将非十进制`String`转换成`byte`数组，然后使用`BigInteger(byte[] bytes)`构造函数**：

```
byte[] inputStringBytes = inputString.getBytes();
BigInteger result = new BigInteger(inputStringBytes);
assertEquals("290f98", new String(result.toByteArray()));
```

这给了我们正确的结果，因为`BigInteger(byte[] bytes)`构造函数将包含二进制补码二进制表示的`byte`数组转换为`BigInteger`。

## 4. 结论

在本文中，我们研究了几种在 Java 中将`String`转换为`BigInteger`的方法。

像往常一样，本教程中使用的所有代码示例都可以从 GitHub 上的处获得。
