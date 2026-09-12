
# Java 中遍历 Map 的不同方法

> 原文：<https://medium.com/javarevisited/different-ways-to-iterate-through-map-in-java-4c3761584f83?source=collection_archive---------1----------------------->

学习在 Java 中遍历 `Map` 对象的不同方法。

![](img/b933a50c426699adec8cb9fa6d44794f.png)

图片来自 [unsplash](https://unsplash.com/@marjan_blan?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

让我们创建一个地图：

```
Map<String , String> fruits = new HashMap<>();
fruits.put("apple" , "🍏" );
fruits.put("banana" , "🍌" );
fruits.put("grapes", " 🍇" );
```

## 方法 1：Java 8 `forEach` 方法

```
fruits.forEach(
    (k, v) -> System.out.println("Key : " + k + " value : " + v)
);
```

## 方法 2：通过获取 `Map` 条目进行循环

```
Set<Map.Entry<String, String>> entries = fruits.entrySet();
for(Map.Entry<String,String> entry : entries) {
    String key = entry.getKey();
    String value = entry.getValue();
    System.out.println(key + " <--> " + value);
}
```

注意：如果我们使用 `for-each` 循环，不要忘记检查 `Map` 是否不为空，否则它将抛出 `NullPointerException`。

## 方法 3：在 `forEach` 循环中使用 `Map` 的键

得到 `keys` 的地图：

```
Set<String> keys = fruits.keySet();
for(String key : keys) {
    String value = fruits.get(key);
    System.out.println(key + " <--> " + value);
}
```

## 方法 4：使用 `Iterator on entries of Map`

我们可以为 `map` 的 `entrySet` 创建迭代器，然后使用它遍历地图的每个条目。

```
Set<Map.Entry<String, String>> entries = fruits.entrySet();
Iterator<Map.Entry<String, String>> iterator = entries.iterator();
while (iterator.hasNext()) {
    Map.Entry<String, String> entry = iterator.next();
    String key = entry.getKey();
    String value = entry.getValue();
    System.out.println(key + " <--> " + value);
}
```

如果你只想要钥匙，你可以通过：

```
Set<String> keys = fruits.keySet();
```

如果您只想要地图的值：

```
Collection<String> values = fruits.values();
```

感谢阅读📖。希望你喜欢这个。如果你发现任何错别字或错误给我一个私人说明📝谢谢🙏 😊。

关注我 [JavaScript Jeep🚙💨](https://medium.com/u/f9ffc26e7e69?source=post_page-----98efbae5e8aa----------------------)。

**请捐款** [**此处**](https://www.paypal.com/paypalme2/jagathishSaravanan) **。你捐款的 80%捐给了需要食物的人🥘。提前感谢。**

其他**你可能喜欢的 Java 文章**探索：

- [2019 年 Java 开发者路线图](https://javarevisited.blogspot.com/2019/10/the-java-developer-roadmap.html)
- [2019 年 Java 和 Web 开发者应该学会的 10 件事](http://javarevisited.blogspot.sg/2017/12/10-things-java-programmers-should-learn.html#axzz53ENLS1RB)
- [Java 开发者应该知道的 10 个测试工具](http://javarevisited.blogspot.sg/2018/01/10-unit-testing-and-integration-tools-for-java-programmers.html)
- [5 个框架 Java 开发者应该学会的 2019 年](http://javarevisited.blogspot.sg/2018/04/top-5-java-frameworks-to-learn-in-2018_27.html)
- [5 门课程学习 Java 中的大数据和 Apache Spark](http://javarevisited.blogspot.sg/2017/12/top-5-courses-to-learn-big-data-and.html)
- [10 门课程学习 DevOps for 每一个 Java 程序员都应该阅读](https://javarevisited.blogspot.com/2018/09/10-devops-courses-for-experienced-java-developers.html)
- [Java 开发人员在日常工作中使用的 10 个工具](http://javarevisited.blogspot.sg/2017/03/10-tools-used-by-java-programming-Developers.html#axzz55lrMRnNC)
- [成为更好的 Java 开发人员的 10 个技巧](https://javarevisited.blogspot.com/2018/05/10-tips-to-become-better-java-developer.html)
