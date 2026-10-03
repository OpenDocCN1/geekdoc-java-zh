
# Java 网络周刊，第 169 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-web-weekly-169>

本周有很多关于 Java 9 的有趣文章。

**开始了……**

## 1. Spring 和 Java

#### [>>一个不错的 API 设计宝石：战略模式与兰达斯](https://web.archive.org/web/20220627083232/https://blog.jooq.org/2017/03/17/a-nice-api-design-gem-strategy-pattern-with-lambdas/)【jooq.org】

`lambda`表达式和函数接口的引入允许我们重新思考设计并简化策略设计模式（以及许多其他模式）。

#### [>> Spring Boot 与安全事件同执行器](https://web.archive.org/web/20220627083232/http://blog.codeleak.pl/2017/03/spring-boot-and-security-events-with-actuator.html)【codeleak.pl】

Spring Boot 执行器附带用户友好的支持**处理审计和安全事件**。

简单地说，我们需要做的就是为预定义的事件定义一个监听器。

#### [>>琥珀计划将彻底改变 Java](https://web.archive.org/web/20220627083232/https://www.sitepoint.com/project-amber-will-revolutionize-java/)【sitepoint.com】

Java 终于迎来了许多新的变化。这些包括局部变量类型推断、泛型枚举、数据类和模式匹配。

“十年前我们已经有了其他语言的版本”的帖子来了。

#### [>>完全可配置的 Spring MVC 映射](https://web.archive.org/web/20220627083232/https://blog.frankel.ch/fully-configurable-mappings-spring-mvc/#gsc.tab=0)【frankel.ch】

只需一点点努力，我们也可以将引导致动器的特性应用到非引导应用程序中。

#### [>>Spring IntelliJ IDEA 2017.1](https://web.archive.org/web/20220627083232/https://blog.jetbrains.com/idea/2017/03/spring-data-improvements-in-intellij-idea-2017-1/)【jetbrains.com】

IntelliJ IDEA 获得了更多面向 Spring 的特性。

#### [>>开合的原理往往不是你想的那样](https://web.archive.org/web/20220627083232/https://blog.jooq.org/2017/03/20/the-open-closed-principle-is-often-not-what-you-think-it-is/)【jooq.org】

开闭原则的实用方法不包括不惜任何代价追求开放。

#### [>> JDK 9 Rampdown 第二阶段：工艺方案](https://web.archive.org/web/20220627083232/http://mail.openjdk.java.net/pipermail/jdk9-dev/2017-March/005666.html)【mail.openjdk.java.net】

JDK 9 rampdown 二期刚刚开工。

#### [>>调整到强封装的更好工具](https://web.archive.org/web/20220627083232/http://mail.openjdk.java.net/pipermail/jigsaw-dev/2017-March/011763.html)【mail.openjdk.java.net】

JDK 中的内部 API 不应该被使用，但是它们被多个框架使用，这些框架现在遇到了错误。

JDK 9 将为这些情况提供一个特殊的解决方案。

#### 同样值得一读：

*   #### [>>冬眠小技巧：如何使用冬眠的原生引导 API](https://web.archive.org/web/20220627083232/http://www.thoughts-on-java.org/hibernate-tips-use-hibernates-native-bootstrapping-api/)

*   #### [>>春网-流量-第一步](https://web.archive.org/web/20220627083232/http://www.java-allandsundry.com/2017/03/spring-web-flux-first-steps.html)【java-allandsundry.com】

*   #### [>> How to find out which statement failed in JDBC batch update](https://web.archive.org/web/20220627083232/https://vladmihalcea.com/2017/03/21/how-to-find-which-statement-failed-in-a-jdbc-batch-update/)【vladmihalcea.com】

**网络研讨会和演示：**

*   #### [**>>网络研讨会录制：用格拉德勒和智能理念复合构建 2017.1**](https://web.archive.org/web/20220627083232/https://blog.jetbrains.com/idea/2017/03/webinar-recording-composite-builds-with-gradle/)【jetbrains.com】

**升级时间：**

*   #### [>> Spring clouds are flowing with birds. 1 release](https://web.archive.org/web/20220627083232/https://spring.io/blog/2017/03/16/spring-cloud-stream-chelsea-rc1-released)【spring.io】

*   #### [>> ORM 5.2](https://web.archive.org/web/20220627083232/http://in.relation.to/2017/03/16/hibernate-orm-529-final-release/) Ninth bug fix release

*   #### [>> IntelliJ 理念 2017.1 中对 Java 9 模块的支持](https://web.archive.org/web/20220627083232/https://blog.jetbrains.com/idea/2017/03/support-for-java-9-modules-in-intellij-idea-2017-1/)【jetbrains.com】

*   #### [>> Spring vault 1.0 RC1 is now on sale](https://web.archive.org/web/20220627083232/https://spring.io/blog/2017/03/16/spring-vault-1-0-rc1-is-now-available)【spring.io】

*   #### [>> Spring Cloud Dalston RC1 released](https://web.archive.org/web/20220627083232/https://spring.io/blog/2017/03/21/spring-cloud-dalston-rc1-released)【spring.io】

*   #### [>> Chunyun Task 1.2.0.M2 is now on sale](https://web.archive.org/web/20220627083232/https://spring.io/blog/2017/03/21/spring-cloud-task-1-2-0-m2-is-now-available)【spring.io】

## 2. 技术

#### [**>>参加技术面试**](https://web.archive.org/web/20220627083232/https://aphyr.com/posts/340-acing-the-technical-interview)【aphyr.com】

你就是这样让面试官讨厌你的🙂

#### [>>务实看待孤立测试](https://web.archive.org/web/20220627083232/http://blog.thecodewhisperer.com/permalink/taking-a-pragmatic-view-of-isolated-tests)【thecodewhisperer.com】

通过暴露过度的耦合和不足的内聚性，编写隔离测试会极大地影响系统的设计。

#### [>>【无穷大】坏默认超时](https://web.archive.org/web/20220627083232/https://techblog.bozho.net/infinity-bad-default-timeout/)【techblog.bozho.net】

是的，将超时设置为无穷大或忽略它们很可能不是一个好主意。

#### [>>别忘了价值对象！](https://web.archive.org/web/20220627083232/https://plainoldobjects.com/2017/03/19/dont-forget-about-value-objects/)【plainoldobjects.com】

值对象是处理字符串类型滥用的一个好方法。在强类型语言中工作，利用这些是很有意义的。

#### 同样值得一读：

*   #### [>> Build distributed runtime](https://web.archive.org/web/20220627083232/https://blog.codecentric.de/en/2017/03/building-a-distributed-runtime-for-interactive-queries-in-apache-kafka-with-vertx/)

    of interactive query in Apache Kafka with Vert.x【codecentric.de】

*   #### [>>更多测试数据的烦恼](https://web.archive.org/web/20220627083232/http://www.ontestautomation.com/more-troubles-with-test-data/)【ontestautomation.com】

*   #### [>> Distribute election volunteers at polling stations](https://web.archive.org/web/20220627083232/https://techblog.bozho.net/distributing-election-volunteers-polling-stations/)【techblog.bozho.net】

*   #### [**>> Project Amber: Java language features**](https://web.archive.org/web/20220627083232/https://marxsoftware.blogspot.com/2017/03/project-amber.html)【marxsoftware.blogspot.com】

    with small scale and productivity.

## 3. 沉思

#### [>>产品是——不是——是——不是](https://web.archive.org/web/20220627083232/https://martinfowler.com/articles/lean-inception/product-is-isnot.html)【martinfowler.com】

有时候，首先澄清一个想法不是什么，会更容易探索和解释这个想法🙂

#### [>>软件性能还重要吗？](https://web.archive.org/web/20220627083232/http://lemire.me/blog/2017/03/20/does-software-performance-still-matter/)【lemire.me】

软件性能是至关重要的，不应该被忽视，但是归根结底，代码的绝对值才是最重要的。

#### [>>不要只是标记它——修复它！](https://web.archive.org/web/20220627083232/http://www.daedtech.com/dont-just-flag-fix/)【daedtech.com】

关于问题的信息，没有实际的解决方案——这不是一个好办法。

**同样值得一读：**

*   #### [**>> Is Dr Calvin in the room?**](https://web.archive.org/web/20220627083232/http://blog.cleancoder.com/uncle-bob/2017/03/16/DrCalvin.html)【cleancoder.com】

*   #### [>> Turn the hobby of science and technology into a sideline](https://web.archive.org/web/20220627083232/http://www.daedtech.com/turning-tech-hobbies-into-side-hustle/)【daedtech.com】

*   #### [**>> Two flavors of technical opportunists: missionaries and mercenaries**](https://web.archive.org/web/20220627083232/http://www.daedtech.com/the-flavors-of-technical-opportunists-missionaries-and-mercenaries/)【daedtech.com】

*   #### [>>让天空的八分之一和 Devoxx 旅程开始吧！](https://web.archive.org/web/20220627083232/http://raibledesigns.com/rd/entry/let_the_okta_and_devoxx)【raibledesigns.com】

## 4. 漫画

本周我最喜欢的迪尔伯特。

#### [>>你怎么会有黑眼圈](https://web.archive.org/web/20220627083232/http://dilbert.com/strip/2013-08-27)【dilbert.com】

#### 我妈妈把一暖瓶咖啡放在我的婴儿床里把我养大的【dilbert.com】

#### [>>咄咄逼人的招聘人员寻找被动的求职者](https://web.archive.org/web/20220627083232/http://dilbert.com/strip/2013-08-10)【dilbert.com】

## 5. 本周精选

#### [>>开源（几乎）一切](https://web.archive.org/web/20220627083232/http://tom.preston-werner.com/2011/11/22/open-source-everything.html)【tom.preston-werner.com】
