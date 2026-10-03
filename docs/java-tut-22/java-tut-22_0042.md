
# 问题和练习：控制流语句

> 原文：[`docs.oracle.com/javase/tutorial/java/nutsandbolts/QandE/questions_flow.html`](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/QandE/questions_flow.html)

## 问题

1. Java 编程语言支持的最基本的控制流语句是 ___ 语句。

2. ___ 语句允许任意数量的可能执行路径。

3. ___ 语句类似于`while`语句，但在循环的 ___ 处评估其表达式。

4. 如何使用`for`语句编写一个无限循环？

5. 如何使用`while`语句编写一个无限循环？

## 练习

1. 考虑以下代码片段。

```java
if (aNumber >= 0)
    if (aNumber == 0)
        System.out.println("first string");
else System.out.println("second string");
System.out.println("third string");
```

   1. 如果`aNumber`为 3，你认为代码会产生什么输出？

   2. 编写一个包含上述代码片段的测试程序；将`aNumber`设为 3。程序的输出是什么？是否符合你的预期？解释输出为何是这样的；换句话说，代码片段的控制流是什么？

   3. 仅使用空格和换行符，重新格式化代码片段，使控制流更易于理解。

   4. 使用大括号，`{` 和 `}`，进一步澄清代码。

检查你的答案
