
# Java 网络周刊，第 134 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-web-weekly-134>

去年年初，我决定跟踪我的阅读习惯，并在 Baeldung 上分享最好的东西。从那以后就没错过一篇评论。

**开始了……**

## 1. Spring 和 Java

#### [> > 零周转发布 RebelLabs 开发者生产力报告](https://web.archive.org/web/20220812065924/https://www.infoq.com/news/2016/07/zeroturnaround-report)【infoq.com】

让我们从 RebelLabs 的年度报告开始，提供一些关于我们生态系统趋势的非常有趣的见解。

#### [> > 我们如何修复所有数据库连接泄露](https://web.archive.org/web/20220812065924/http://in.relation.to/2016/07/14/how-we-fixed-all-database-connection-leaks/)

非常酷，简单介绍了**大型 Hibernate 测试套件中的连接泄漏是如何处理的**。

#### [> > JUnit 5——早期试驾——第 1 部分](https://web.archive.org/web/20220812065924/https://www.infoq.com/articles/JUnit-5-Early-Test-Drive)【infoq.com】

提前了解即将到来的 JUnit 5。

#### [> > 反应式编程笔记第三部分：一个简单的 HTTP 服务器应用](https://web.archive.org/web/20220812065924/https://spring.io/blog/2016/07/20/notes-on-reactive-programming-part-iii-a-simple-http-server-application) [ spring.io ]

随着第 5 版的推出，反应式编程即将迎来春天——我们现在已经知道了。

问题是——在哪些情况下它会产生重大影响，以及我们如何在 Spring 5 发布之前使用它。

这一期文章很好地回答了这两个问题。

#### [> > 自定义审计日志用 Spring 和 Hibernate](https://web.archive.org/web/20220812065924/http://techblog.bozho.net/custom-audit-log-with-spring-and-hibernate/)【bozho.net】

在有些项目中，您可以使用一些更好的审计方法。还有一些代码库，如果没有重大而痛苦的重构，这是不可能的。幸运的是，还有一种干净的手动审计方式。

**同样值得一读：**

*   #### [> > How does persistence and consolidation work in JPA](https://web.archive.org/web/20220812065924/https://vladmihalcea.com/2016/07/19/jpa-persist-and-merge/) [vladmihalcea.com]

*   #### [> > Java JIT compiler is very good at optimizing](https://web.archive.org/web/20220812065924/https://blog.jooq.org/2016/07/19/the-java-jit-compiler-is-darn-good-in-optimization/) [jooq.org]

*   #### [> > 排序列表](https://web.archive.org/web/20220812065924/http://www.javaspecialists.eu/archive/Issue239.html) 爪哇专家。欧盟

*   #### [> > Spring-managed hibernation event monitor](https://web.archive.org/web/20220812065924/http://techblog.bozho.net/spring-managed-hibernate-event-listeners/) [bozho.net]

*   #### [> > Null 和非空 @DiscriminatorValue 选项](https://web.archive.org/web/20220812065924/http://in.relation.to/2016/07/19/null-andnot-null-discriminator-values/)

*   #### [> > xplr：用于迁移到 Maven](https://web.archive.org/web/20220812065924/http://www.adam-bien.com/roller/abien/entry/xplr_utility_for_migrations_to)【adam-bien.com】的实用程序

*   #### [> > Robot Framework Tutorial 2016–File Processing](https://web.archive.org/web/20220812065924/https://blog.codecentric.de/en/2016/07/robot-framework-tutorial-2016-file-processing/) [ Codecentric.de ]

*   #### [> > Bean Validation 2.0——一个新的 JSR 诞生了！](https://web.archive.org/web/20220812065924/http://beanvalidation.org/news/2016/07/15/bean-validation-2-0-is-coming/)【beanvalidation.org】

**网络研讨会和演示：**

*   #### [> > CQRS 与 Java](https://web.archive.org/web/20220812065924/http://blog.eisele.net/2016/07/cqrs-with-java-and-lagom.html) 【eisele.net】

*   #### [> > Adam Thornhill's code of crime scene, Git and static analysis, Clojure](https://web.archive.org/web/20220812065924/https://www.infoq.com/interviews/tornhill-static-analysis) [infoq.com]

*   #### [> > 现场网络研讨会：IntelliJ IDEA 2016.2](https://web.archive.org/web/20220812065924/https://blog.jetbrains.com/idea/2016/07/live-webinar-whats-new-in-intellij-idea-2016-2/)【jetbrains.com】的新功能

**升级时间：**

*   #### [> > Spring AMQP 1.6.1 现已可用](https://web.archive.org/web/20220812065924/https://spring.io/blog/2016/07/18/spring-amqp-1-6-1-available-now) spring.io

*   #### [> > IntelliJ IDEA 2016.2.1 EAP 更新 Kotlin 支持到 1.0.3](https://web.archive.org/web/20220812065924/https://blog.jetbrains.com/idea/2016/07/intellij-idea-2016-2-1-eap-updates-kotlin-support-to-1-0-3/) 【jetbrains.com】

*   #### [> > Apache Tomcat 8.5.4 可用](https://web.archive.org/web/20220812065924/https://mail-archives.apache.org/mod_mbox/www-announce/201607.mbox/%3Cc0350dff-7a64-1153-5694-855448a0adb1%40apache.org%3E)【apache.org】

*   #### [> > Apache Shiro 1.2.6 发布](https://web.archive.org/web/20220812065924/https://mail-archives.apache.org/mod_mbox/shiro-announce/201607.mbox/%3CCAH9eYVoNaddyLsYkNX861EX3euRKhuqnhcW62rqb6uC1Crc1NQ%40mail.gmail.com%3E)【apache.org】

## 2. 技术

#### [> > 关于微服务最难的部分：你的数据](https://web.archive.org/web/20220812065924/http://blog.christianposta.com/microservices/the-hardest-part-about-microservices-data/)【christianposta.com】

数据当然是做好微服务最复杂的部分，根据我的经验，这是团队在这类实施中失败的首要原因。

例如，**跨多个系统获得正确的事务边界是一个很难解决的问题**，尤其是在没有很好地理解系统中要实现的语义以及在开始时没有一组明确的自我施加的限制的情况下。

#### [> > 一种更有效地测试你的用户界面的方法](https://web.archive.org/web/20220812065924/http://www.ontestautomation.com/an-approach-to-test-your-user-interface-more-efficiently/)【ontestautomation.com】

快速、有趣的阅读使用了我所知甚少的模式——模型-视图-视图模型。

**同样值得一读：**

*   #### [> > 物联网分析平台](https://web.archive.org/web/20220812065924/https://blog.codecentric.de/en/2016/07/iot-analytics-platform/) codecentric.de

*   #### [> > DDD Decoding-Aggregation and root explanation of aggregation (Part 1)](https://web.archive.org/web/20220812065924/http://blog.sapiensworks.com/post/2016/07/14/DDD-Aggregate-Decoded-1) [sapiensworks.com]

*   #### [> > DDD decoding-aggregation and root explanation of aggregation (part 2)](https://web.archive.org/web/20220812065924/http://blog.sapiensworks.com/post/2016/07/14/DDD-Aggregate-Decoded-2) [sapiensworks.com]

*   #### [> > DDD decoding-aggregation and root explanation of aggregation (3)](https://web.archive.org/web/20220812065924/http://blog.sapiensworks.com/post/2016/07/14/DDD-Aggregate-Decoded-3) [sapiensworks.com]

## 3. 沉思

#### [> > 如何去辉煌你的代码](https://web.archive.org/web/20220812065924/http://www.daedtech.com/un-clever-code/)【daedtech.com】

我喜欢通读这些听众的问题，因为这是一个很好的改变。

另外，顺便提一下，`writing a feature without using the if keyword anywhere`当然是度过周末的好方法🙂

#### [> > 如何给你的流程添加静态分析](https://web.archive.org/web/20220812065924/http://www.daedtech.com/add-static-analysis-process/)【daedtech.com】

介绍如何思考、期望和如何涉足静态分析的深水区。

#### [> > 管理快速增长](https://web.archive.org/web/20220812065924/https://dandreamsofcoding.com/2016/07/18/managing-rapid-growth/)【dandreamsofcoding.com】

在过去的几年里，**我工作的公司已经从 2 家增长到了 600-700 多家**（上次我检查的时候）。

经历这种增长肯定是一段相当长的旅程，这篇文章就如何做好这一点提出了一些很好的观点。

#### [> > 灵感来源](https://web.archive.org/web/20220812065924/http://www.daedtech.com/sources-of-inspiration/)【daedtech.com】

快速阅读，坚实的阅读清单和一些灵感。

**同样值得一读：**

*   #### [> > DockerCon 2016 主题演讲](https://web.archive.org/web/20220812065924/https://matt.aimonetti.net/posts/2016/06/27/dockercon-2016-keynote/)【matt.aimonetti.net】

*   #### [> > 无服务器架构的缺点](https://web.archive.org/web/20220812065924/http://martinfowler.com/articles/serverless.html#drawbacks) [martinfowler.com]

*   #### [> > 为什么我从未注册的网站会有数据泄露？](https://web.archive.org/web/20220812065924/https://www.troyhunt.com/why-am-i-in-a-data-breach-for-a-site-i-never-signed-up-for/) 【troyhunt.com】

*   #### [> > 举办公共代码静修](https://web.archive.org/web/20220812065924/http://blog.code-cop.org/2016/07/hosting-public-coderetreats.html) [code-cop.org]

## 4. 漫画

本周我最喜欢的迪尔伯特。

#### [> > 你为什么拒绝我在脸书的好友请求？](https://web.archive.org/web/20220812065924/http://dilbert.com/strip/2011-01-24)【dilbert.com】

#### [> > 我像信任你一样信任他们](https://web.archive.org/web/20220812065924/http://dilbert.com/strip/2011-01-05)【dilbert.com】

#### [> > 说出你的想法](https://web.archive.org/web/20220812065924/http://dilbert.com/strip/2011-01-10)【dilbert.com】

## 5. 本周精选

#### [> > 蝗虫经济](https://web.archive.org/web/20220812065924/http://www.ribbonfarm.com/2013/04/03/the-locust-economy/)【ribbonfarm.com】
