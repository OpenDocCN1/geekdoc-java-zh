
# Baeldung 每周评论 26

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/2014-week-review-26>

## 1. Java 和 Spring

#### [> > 项目拼图：二期](https://web.archive.org/web/20220521210404/http://mreinhold.org/blog/jigsaw-phase-two)

`Mark Reinhold` 刚刚宣布了 `JDK 9` Java 模块系统的下一步。看起来这是一个比第一轮更体面的计划——采取一口大小的块，并将它们一个接一个地集成到平台中，而不是一个大的改变。手指交叉。

#### [> > 冬眠和 UUID 标识符](https://web.archive.org/web/20220521210404/http://vladmihalcea.com/2014/07/01/hibernate-and-uuid-identifiers/)

真正有用和详细的**看看 `Hibernate` uuid**——虽然我已经用这些小标识符工作了很多年，但我仍然从这一个中学到了很多。我也喜欢众包的方式来仔细检查信息和获得建议。

#### [> > Spring 4：基于 `CGLIB` 的代理类，没有默认构造函数](https://web.archive.org/web/20220521210404/http://blog.codeleak.pl/2014/07/spring-4-cglib-based-proxy-classes-with-no-default-ctor.html)

这就是 Spring 变得更容易的原因——以前用 `CGLIB` 代理的 beans 需要一个默认的构造函数，Spring 4 之后就不再需要了。因此——**构造注入现在对于这些 beans 也是可能的**——这使得测试它们变得容易多了。

#### [> > 弹性与春天的缓存抽象](https://web.archive.org/web/20220521210404/https://altfatterz.blogspot.ro/2014/06/flexibility-with-springs-cache.html)

Spring 中缓存的实际例子——冷静地使用`@Profile`在两个不同的缓存提供者（在本例中是 `Hazelcast` 和 `Ehcache`）之间透明地切换。酷豆。

最后——我本周注意到的一些官方的春天的东西：

*   > > **[Spring Security / Spring Data integration 原型](https://web.archive.org/web/20220521210404/https://github.com/rwinch/spring-security-data/tree/spel#readme)**——美好的事物

*   > > **[春季数据 Dijkstra SR1 发布](https://web.archive.org/web/20220521210404/https://spring.io/blog/2014/06/30/spring-data-dijkstra-sr1-released)**——春季数据 bug 修复——趁热拿起来

*   > > **[性能–调整 Spring Petclinic 示例应用](https://web.archive.org/web/20220521210404/https://spring.io/blog/2014/07/03/springone2gx-2013-replay-performance-tuning-the-spring-petclinic-sample-application)**–网上研讨会回放

*   > > **[Spring 下一代](https://web.archive.org/web/20220521210404/https://spring.io/blog/2014/07/03/springone2gx-2013-replay-tooling-for-spring-s-next-generation)** 的工具——网上研讨会回放

## 2. 技术

#### [> > 你可能不需要消息队列](https://web.archive.org/web/20220521210404/http://techblog.bozho.net/?p=1455)

我非常同意这一点，无论是具体的还是更广泛的说法：“**你可能不需要 X**”，其中 X 可以是任何数量的东西。复杂性是一件偷偷摸摸的事情，在设计系统时，你需要毫不留情。添加 `MQ` 可能——十有八九——是不成熟的优化和错误的举措。

所以我们有我们的本周文章——去读两遍。

#### [> > 微服固](https://web.archive.org/web/20220521210404/http://www.mattstine.com/2014/06/30/microservices-are-solid/)

从固体原理的角度来看，这是一篇关于微服务的有趣文章。

## 3. 沉思

#### [> > 个人冥想软件](https://web.archive.org/web/20220521210404/http://www.mdswanson.com/blog/2014/06/29/meditations-on-software.html)

很好的精神食粮——这是一篇速读，所以你没有借口🙂

#### [> > 面试时不该做的事](https://web.archive.org/web/20220521210404/http://dandreamsofcoding.com/2014/06/29/interviewing-is-hard/)

一个很好的面试指南——里面有一些有趣的花絮，我希望我在 8 年前读过（并消化掉）🙂

#### [> > 绞杀应用](https://web.archive.org/web/20220521210404/http://martinfowler.com/bliki/StranglerApplication.html)

这一条引起了我的共鸣——因为到目前为止我已经参与了两次“大重写”，两次我们都应该至少尝试**利用这种方法，而不是实际重写系统**。省下你自己去那个特别的兔子洞的麻烦，去读这个吧。

#### [> > P、NP 和决策问题（真的没那么糟糕）](https://web.archive.org/web/20220521210404/http://www.daedtech.com/p-np-and-decision-problems-really-its-not-that-bad)

算法复杂性和 P 与 NP 的即兴介绍。不错的读物——勾起了对学校的有趣回忆。
