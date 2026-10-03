
# Java 周刊，第 201 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-201>

本周有很多关于 Java 9 的有趣文章。

**开始了……**

## 1. Spring 和 Java

#### [**>>用`jshell`学习 Java**](https://web.archive.org/web/20221208143856/https://www.javaspecialists.eu/archive/Issue250.html) [javaspecialists.eu]

对`JShell`的快速介绍使得不用`public static void main()`方法就能探索 Java 成为可能🙂

#### [**>>数据类为 Java**](https://web.archive.org/web/20221208143856/http://cr.openjdk.java.net/~briangoetz/amber/datum.html) [openjdk.java.net]

全面解释即将推出的 Java 新特性——数据类。

#### [**>>Hibernate 提示：如何将实体属性映射到可选的**](https://web.archive.org/web/20221208143856/https://www.thoughts-on-java.org/hibernate-tips-map-entity-attribute-optional/) [thoughts-on-java.org]

不幸的是，`Hibernate`和`JPA 2.2`不支持将`Optional`作为属性类型，但是通过一点小技巧，我们仍然可以使用`Optional`作为 getter 方法的返回类型。

#### [**>>Bean 验证基准再探**](https://web.archive.org/web/20221208143856/http://in.relation.to/2017/10/31/bean-validation-benchmark-revisited/)

三个最流行的`Bean`验证实现的一个有趣的性能比较——`Hibernate Validator 6.x.x`比以往任何时候都快。

#### 同样值得一读：

* [**>>Build a reactive system**](https://web.archive.org/web/20221208143856/https://www.infoq.com/articles/Reactive-Systems-Akka-Actors-DomainDrivenDesign) [infoq.com] by using `Akka`'s Actor model and domain-driven design
* [**>>Turn any repurchase into a software factory: explore Spring 5 and Kotlin**](https://web.archive.org/web/20221208143856/https://medium.com/the-composition/turn-any-repo-into-a-software-factory-exploring-spring-5-and-kotlin-2f58283421a2) [medium.com]
* [**>>diff-q spring-data-gemfire spring-data-geode**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/10/26/diff-q-spring-data-gemfire-spring-data-geode) [spring.io]
* [**>>Use JMC and JMH to squeeze another 10% speed increase out of jOOQ**](https://web.archive.org/web/20221208143856/https://blog.jooq.org/2017/11/01/squeezing-another-10-speed-increase-out-of-jooq-using-jmc-and-jmh/) [blog.jooq.org]
* [**>>The best way to map a @NaturalId business key with JPA and Hibernate**](https://web.archive.org/web/20221208143856/https://vladmihalcea.com/2017/10/31/the-best-way-to-map-a-naturalid-business-key-with-jpa-and-hibernate/) [vladmihalcea.com]
* [**>>Watin: An Alternative Navigator**](https://web.archive.org/web/20221208143856/https://blog.frankel.ch/alternative-navigator-vaadin/#gsc.tab=0) [blog.frankel.ch]
* [**>>IntelliJ IDEA 2017.3 公开预告**](https://web.archive.org/web/20221208143856/https://blog.jetbrains.com/idea/2017/10/intellij-idea-2017-3-public-preview/) [blog.jetbrains.com]
* [**>>Master your own reactive power realization. Part I - Publisher**](https://web.archive.org/web/20221208143856/https://medium.com/@olehdokuka/mastering-own-reactive-streams-implementation-part-1-publisher-e8eaf928a78c) [medium.com]

**网络研讨会和演示：**

* [**>>Use AKKA to interrupt development**](https://web.archive.org/web/20221208143856/https://www.infoq.com/presentations/reactive-events-streaming-api) [infoq.com]
* [**>>Spring tip: Spring Shell**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/11/01/spring-tips-spring-shell) [spring.io]
* [**>>Homomorphism：也就是说，它是什么**](https://web.archive.org/web/20221208143856/https://www.infoq.com/presentations/homoiconicity) [infoq.com]

**升级时间：**

* [**>>Spring Security RC1 发布**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/11/01/spring-security-5-0-0-rc1-released) [spring.io]
* [**>>Spring REST Docs 2.0.0.RC1**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/10/30/spring-rest-docs-2-0-0-rc1) [spring.io]
* [**>>Reactor Bismuth -SR3 现在可用**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/10/27/reactor-bismuth-sr3-is-now-available) [spring.io]
* [**>>Hibernate Search 5.6、5.7、5.8 的 bug 修复发布**](https://web.archive.org/web/20221208143856/http://in.relation.to/2017/10/26/hibernate-search-5-6-4-and-5-7-3-and-5-8-2/)
* [**>>Hibernate Validator 6.0.4.Final 发布**](https://web.archive.org/web/20221208143856/http://in.relation.to/2017/10/25/hibernate-validator-604-final-out/)
* [**>>Spring Web Services 3.0.0.RELEASE/2.4.2.RELEASE 发布出来了！**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/10/30/spring-web-services-3-0-0-release-2-4-2-release-is-out) [spring.io]
* [**>>Spring Session RC1 发布**](https://web.archive.org/web/20221208143856/https://spring.io/blog/2017/11/01/spring-session-2-0-0-rc1-released) [spring.io]
* [**>>Spring Tool Suite 3.9.1 发布**](https://web.archive.org/web/20221208143856/https://www.infoq.com/news/2017/10/sts-released) [infoq.com]

## 2. 技术和思考

#### [**>>定制您的敏捷方法：从您想要的结果开始**](https://web.archive.org/web/20221208143856/https://www.infoq.com/articles/agile-approach-results) [infoq.com]

速度是能力的当前度量，而不是项目进度的度量——跟踪已完成的故事而不是故事点更有意义——那些随时间变化的价值。

**同样值得一读：**

* [**>>Applying blockchain in the supply chain field - building a blockchain-enabled supply chain platform**](https://web.archive.org/web/20221208143856/https://blog.codecentric.de/en/2017/10/applying-the-blockchain-in-the-supply-chain-domain-building-a-solution-blockcentric-3/) [blog.codecentric.de]
* [**>>Using event procurement，一个模糊且快速变化的领域**](https://web.archive.org/web/20221208143856/http://blog.sapiensworks.com/post/2017/10/30/Is-DDD-ES-CQRS-changing-domain) [blog.sapiensworks.com]
* [**>>Trust your pipeline: automatically test an end-to-end Java application**](https://web.archive.org/web/20221208143856/https://medium.com/@eliasnogueira/trust-your-pipeline-automatically-testing-an-end-to-end-java-application-4a33232180c3) [medium.com]
* [**>>管理编码练习的难度**](https://web.archive.org/web/20221208143856/http://blog.code-cop.org/2017/10/difficulty-of-coding-exercises.html) [blog.code-cop.org]
* [**>>用 ReactJS、Redux 和 Electron 开发现代离线应用——第一部分——简介**](https://web.archive.org/web/20221208143856/https://blog.codecentric.de/en/2017/10/developing-modern-offline-apps-reactjs-redux-electron-part-1/) [blog.codecentric.de]
* [**>>运行一个成功的开源项目**](https://web.archive.org/web/20221208143856/https://waynebeaton.wordpress.com/2017/10/26/running-a-successful-open-source-project/) [waynebeaton.wordpress.com]
* [**>>借助简历成为软件专家**](https://web.archive.org/web/20221208143856/https://www.daedtech.com/become-software-specialist-help-resume/) [daedtech.com]

## 3. 漫画

本周我最喜欢的迪尔伯特。

#### [**>>为了更好的老板的 App**](https://web.archive.org/web/20221208143856/http://dilbert.com/strip/2017-11-01) [dilbert.com]

#### [**>>机器人不是机器人**](https://web.archive.org/web/20221208143856/http://dilbert.com/strip/2017-10-28) [dilbert.com]

#### [**>>巨魔无职**](https://web.archive.org/web/20221208143856/http://dilbert.com/strip/2017-10-27) [dilbert.com]

## 4. 本周精选

#### [**>>如何跟踪和监控关键的 Java 应用程序指标**](https://web.archive.org/web/20221208143856/https://stackify.com/java-application-metrics/) [stackify.com]
