
# Java 周刊，第 192 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-192>

本周有很多关于 Java 9 的有趣文章。

**开始了……**

## 1. Spring 和 Java

#### [**>>如何用 JPA 2.2 映射日期时间 API**](https://web.archive.org/web/20220525140347/https://www.thoughts-on-java.org/map-date-time-api-jpa-2-2/)【thoughts-on-java.org】

`JPA 2.2`终于支持新的 Java 日期/时间 API 了。

#### [**>>@Contended 自 Java 9**](https://web.archive.org/web/20220525140347/http://www.javaspecialists.eu/archive/Issue249.html)【javaspecialists.eu】

Java 9 将试图封装我们不应该使用的内部系统类（但我们经常使用）。`@Contended`注释就是这些工具之一——让我们看看如何在 Java 9 中访问它。

#### [**>>你不是编译器！**](https://web.archive.org/web/20220525140347/https://blog.frankel.ch/you-not-compiler/#gsc.tab=0)【frankel.ch】

编程测试很酷，但是很明显，它们确实测试了开发人员很少的一部分技能。总而言之，没那么有用。

#### [**>>规划你的 Java 9 更新**](https://web.archive.org/web/20220525140347/http://blog.codefx.org/java/planning-your-java-9-update/)【codefx.org】

Java 9 即将推出（希望如此），并带来大量新的 API 和语言特性，其中包括模块。模块化应用程序应该经过深思熟虑和仔细规划。

#### [**>>Java API for RESTful Web Services 2.1 发布**](https://web.archive.org/web/20220525140347/https://www.infoq.com/news/2017/08/JAX-RS-2.1-released)【infoq.com】

**JAX-RS 2.1 终于发布了**，它有一堆很酷的新特性。

#### [**>>代码气味：突变**](https://web.archive.org/web/20220525140347/https://blog.jetbrains.com/idea/2017/08/code-smells-mutation/)【blog.jetbrains.com】

简而言之——改变你直接迭代的东西是个坏主意🙂

#### [**>>JUnit 5 教程：用 Gradle 运行单元测试**](https://web.archive.org/web/20220525140347/https://www.petrikainulainen.net/programming/testing/junit-5-tutorial-running-unit-tests-with-gradle/)【petrikainulainen.net】

在某些场景下，运行`JUnit 5`测试可能会有点棘手——重要的是要记住，**JUnit 5 被分成几个不同的工件**，您可以分别利用它们。

#### [**>>Java 云托管服务上的成本降低策略**](https://web.archive.org/web/20220525140347/https://www.infoq.com/articles/java-cloud-cost-reduction?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq.com】

云资源可能很贵，尤其是当你被迫为你不需要的资源付费的时候。这里有一些技巧来确保你只为你实际使用的东西付费。

#### [**>>惯用 Java 流 API 偷看**](https://web.archive.org/web/20220525140347/http://4comprehension.com/idiomatic-peeking/)【4comprehension.com】

围绕 Java Stream API 中的`peek()`方法有许多争议——在这里您可以看到这些是什么以及如何正确使用该方法。

#### 同样值得一读：

*   #### [**>>动态添加拦截器到内置的 CDI bean**](https://web.archive.org/web/20220525140347/http://arjan-tijms.omnifaces.org/2017/08/dynamically-adding-interceptor-to-build.html)【arjan-tijms.omnifaces.org】

*   #### [**>>JUnit 5 教程：用 Maven 运行单元测试**](https://web.archive.org/web/20220525140347/https://www.petrikainulainen.net/programming/testing/junit-5-tutorial-running-unit-tests-with-maven/)【petrikainulainen.net】

*   #### [**>>Hibernate 提示：如何从多对一关联中删除子实体**](https://web.archive.org/web/20220525140347/https://www.thoughts-on-java.org/hibernate-tips-how-to-delete-child-entities/)【thoughts-on-java.org】

*   #### [**>>使用 JPA 和 Hibernate 将投影查询映射到 DTO（数据传输对象）的最佳方式**](https://web.archive.org/web/20220525140347/https://vladmihalcea.com/2017/08/29/the-best-way-to-map-a-projection-query-to-a-dto-with-jpa-and-hibernate/)【vladmihalcea.com】

*   #### [**>>本地化的 Spring Boot 安全错误消息**](https://web.archive.org/web/20220525140347/https://blog.codecentric.de/en/2017/08/localization-spring-security-error-messages-spring-boot/)【codecentric.de】

*   #### [**>>第一个 Vavr 教程**](https://web.archive.org/web/20220525140347/http://blog.vavr.io/first-vavr-tutorial/)【blog.vavr.io】

**网络研讨会和演示：**

*   #### [**>>Spring Cloud Data Flow 提示与技巧：与 Shell 交互**](https://web.archive.org/web/20220525140347/https://spring.io/blog/2017/08/29/spring-cloud-data-flow-tips-tricks-interacting-with-the-shell)【spring.io】

*   #### [**>>软件产品交付中的速度意味着什么？**](https://web.archive.org/web/20220525140347/https://www.infoq.com/presentations/speed-software-delivery)【infoq.com】

**升级时间：**

*   #### [**>>Hibernate Search 5.5、5.6、5.7 的错误修正已发布**](https://web.archive.org/web/20220525140347/http://in.relation.to/2017/08/24/hibernate-search-5-5-8-and-5-6-3-and-5-7-2/)

*   #### [**>>jOOQ 3.10 支持 JPA 属性转换器**](https://web.archive.org/web/20220525140347/https://blog.jooq.org/2017/08/24/jooq-3-10-supports-jpa-attributeconverter/)【jooq.org】

*   #### [**>>IntelliJ IDEA 2017.2：更智能、更整洁、更快速**](https://web.archive.org/web/20220525140347/https://www.infoq.com/news/2017/08/intellij-idea-2017.2?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq.com】

*   #### [**>>IntelliJ IDEA 2017.2：Spring Boot 改进**](https://web.archive.org/web/20220525140347/https://blog.jetbrains.com/idea/2017/08/intellij-idea-2017-2-spring-boot-improvements/)【jetbrains.com】

*   #### [**>>Spring Cloud Edgware M1 现已发售**](https://web.archive.org/web/20220525140347/https://spring.io/blog/2017/08/29/spring-cloud-edgware-m1-is-now-available)【spring.io】

## 2. 技术

#### [**>>混沌世界中的稳定：Postgres 如何让事务原子化**](https://web.archive.org/web/20220525140347/https://brandur.org/postgres-atomicity)【brandur.org】

对 Postgres 内部的超级深入探究。

**同样值得一读：**

*   #### [**>>选择事件架构**](https://web.archive.org/web/20220525140347/https://www.infoq.com/news/2017/08/selecting-event-architecture)【infoq.com】

## 3. 沉思

#### [**>>扩展你的自由职业：雇佣他人**](https://web.archive.org/web/20220525140347/https://www.daedtech.com/scale-freelancing-hiring-others/)【daedtech.com】

嗯，你可能应该从找一个好的律师和会计师开始——几乎每个国家都是如此🙂

**同样值得一读：**

*   #### [**>>强化学习概述**](https://web.archive.org/web/20220525140347/https://horicky.blogspot.com/2017/08/reinforcement-learning-overview.html)【horicky.blogspot.com】

*   #### [**>>如何在领域驱动设计中处理业务规则**](https://web.archive.org/web/20220525140347/http://blog.sapiensworks.com/post/2017/08/23/Handling-Business-Rules-DDD)【blog.sapiensworks.com】

*   #### [**>>什么时候止损？**](https://web.archive.org/web/20220525140347/https://offbeattesting.com/2017/08/24/when-do-you-cut-your-losses/)【offbeattesting.com】

*   #### [**>>2050 年的网络**](https://web.archive.org/web/20220525140347/https://jacquesmattheij.com/the-web-in-2050)

*   #### [**>>只是执行命令**](https://web.archive.org/web/20220525140347/http://blog.cleancoder.com/uncle-bob/2017/08/28/JustFollowingOders.html)【blog.cleancoder.com】

*   #### [**>>代码审查的春季大扫除**](https://web.archive.org/web/20220525140347/https://www.daedtech.com/spring-cleaning-code-review/)【daedtech.com】

## 4. 漫画

本周我最喜欢的迪尔伯特。

#### [**>>闲聊**](https://web.archive.org/web/20220525140347/http://dilbert.com/strip/2013-03-05)【dilbert.com】

#### [**>>抱怨丸**](https://web.archive.org/web/20220525140347/http://dilbert.com/strip/2011-05-12)【dilbert.com】

#### [**>>远程工作**](https://web.archive.org/web/20220525140347/http://dilbert.com/strip/2013-04-26)【dilbert.com】

## 5. 本周精选

`REST With Spring 2.0`发布的最后一天（星期五）：

#### [**>>REST With Spring 2.0 大师班**](/web/20220525140347/https://www.baeldung.com/rest-with-spring-course#master-class)

