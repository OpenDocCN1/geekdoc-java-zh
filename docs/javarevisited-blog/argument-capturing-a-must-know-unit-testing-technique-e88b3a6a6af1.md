
# 一个必须知道的单元测试技术

> 原文：<https://medium.com/javarevisited/argument-capturing-a-must-know-unit-testing-technique-e88b3a6a6af1?source=collection_archive---------3----------------------->

![](img/e291af2e601167574eff33738438a657.png)

`@Captor`是 [mockito 库](https://site.mockito.org/) 中的一个注释，它与`ArgumentCaptor`类一起使用，用于捕获传递给被模仿对象的方法的参数。它总是与`verify()`一起使用，以检索调用模拟依赖关系中的方法时传递的参数。它是一个有用的工具，可以让我们为测试创建额外的断言，从而使我们的单元测试更加准确。

这里我们有一个`留言簿`类，它将把一个`的留言簿`保存到`的留言簿库`。`guestsBookRepository`是该类的一个依赖项，如果我们要编写一个单元测试，我们必须模拟它。你认为模拟将足以准确地测试这个类吗？

如果我们要模仿这个类的依赖性并试着测试它。我们唯一能做的就是验证与`guest book repository`对象的交互，但是我们不能检查准确传递的数据。

原因是我们没有控制用于生成`guestEntry`的`guest book utils`类。这种约束在[单元测试](/javarevisited/top-10-courses-to-learn-eclipse-junit-and-mockito-for-java-developers-4de1e8d62b96)术语中称为`硬连线依赖`。我们说这是硬连线的，因为这个类目前没有注入它的机制。

这个测试不准确，因为我们没有检查传递给`save()`方法的值

如果在这一点上，我们要花一些时间来考虑 OOD（[面向对象设计](/javarevisited/my-favorite-courses-to-learn-object-oriented-programming-and-design-in-2019-197bab351733?source=collection_home---4------0-----------------------)），也许我们会得出这样的结论：需要用`guest book utils`做一些事情来允许我们自己更准确地测试这个类。

是否应该去掉[静态方法](https://javarevisited.blogspot.com/2011/11/static-keyword-method-variable-java.html)调用？要不要注入一个工厂？可能有很多事情我们可以让这个类更易测试。但是很可能需要重构。

重构没有错，我支持重构，我相信我们应该一直努力提高我们代码库的质量。不幸的是，在现实生活中，有时我们不得不推迟这种决定，特别是在非常大和复杂的代码库中，或者当我们需要满足紧迫的期限时。

当然，推迟重构的副作用会是技术债的产生。也许我们会在另一个故事中更多地讨论[重构](https://javarevisited.blogspot.com/2020/12/top-5-course-to-improve-coding-skills.html#axzz6k4XBgTw4)，但现在让我们看看`@Captor`如何在不改变我们的生产代码的情况下帮助我们。

> **也许是正确的做法，但不是合适的时机。**

在这个单元测试的替代实现中，我们将使用`@Captor`来创建一个更精确的测试版本。请注意，我们现在有了额外的断言。这是可能的，因为我们的`guest entry captor`正在记录传递给`save()`方法的值。

多亏了`@Captor`注释，更精确的测试成为可能

机制非常简单，以下是步骤总结：

1. 创建一个类型为`ArgumentCaptor`的对象，使用通用参数指定要捕捉的对象的类型。
2. 用`@Captor`注释注释该对象。
3. 在您通常的模拟验证中，调用`capture()`方法来启用捕获
4. 使用 captor 对象的`getValue()`方法获取记录的值，并将它们赋给一个变量。
5. 添加附加断言

> **记住，要掌握** [**单元测试的技巧**](/javarevisited/5-courses-to-learn-junit-and-mockito-in-2019-best-of-lot-f217d8b93688) **你需要了解如何使用你的工具以及何时使用它们。**

如果你喜欢这个故事，请给我们一些掌声👏[**跟随我们简介**](/@javing.uk)[Javing](http://www.javing.uk)是一家总部位于伦敦的敏捷 Java 软件咨询公司。
