
# Java 中的 Switch 语句和表达式（JEP 361）

> 原文：<https://medium.com/javarevisited/switch-statement-expression-in-java-jep-361-cb62cd0b9e68?source=collection_archive---------1----------------------->

## 用 Java Switch 语句和表达式提高代码可读性

> 最初发表于 <https://asyncq.com/switch-statement-expression-in-java-jep-361>

![](img/0b9b58c2b1321d7390b549ba636cb49b.png)

## 开关声明

在用编程语言编写逻辑时，我们经常会遇到需要根据用户输入执行特定逻辑的情况。为此，我们通常使用`if-else`语句，但有时`switch`语句是更清晰、更可读的选择。`switch`语句允许基于多个条件分支执行代码，其语法如下：

```
switch (expression) {
    case value1:
        // 执行代码块1
        break;
    case value2:
        // 执行代码块2
        break;
    default:
        // 执行默认代码块
}
```

在传统`switch`语句中，每个`case`分支通常需要`break`语句来终止执行，否则会发生“穿透”（fall-through），导致后续分支也被执行。这种设计虽然灵活，但容易引发错误，降低代码可读性。
