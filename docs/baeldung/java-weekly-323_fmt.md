
# Java 周刊，第 323 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-323>

## 1. Spring 和 Java

### [>> RSocket 入门：Spring Boot 服务器](https://web.archive.org/web/20220630012348/https://spring.io/blog/2020/03/02/getting-started-with-rsocket-spring-boot-server) [spring.io]

对 RSocket 的一个很好的概述，RSocket 是一个用于微服务的**反应式消息协议**，它通过 TCP 或 WebSockets 工作。

### [>> Spring 自动布线——这是一种魔法——第一部分](https://web.archive.org/web/20220630012348/https://blog.scottlogic.com/2020/02/25/spring-autowiring-its-a-kind-of-magic.html) [blog.scottlogic.com]

深入了解 Spring 如何使用反射将依赖关系自动连接到一个只有一个构造函数的 bean 类中，而没有使用`@Autowire`。

### [>> 教程：用 Ktor 在 Kotlin 中编写微服务——一个连接系统的多平台框架](https://web.archive.org/web/20220630012348/https://www.infoq.com/articles/microservices-kotlin-ktor/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]

快速浏览一下 Ktor，一个来自 JetBrains 的用于构建多平台客户端和服务器应用程序的 Kotlin 框架。

#### 同样值得一读：

* [>> 序列化记录](https://web.archive.org/web/20220630012348/https://www.javaspecialists.eu/archive/Issue276.html) [javaspecialists.eu]
* [>> 尽在和新的 groupid—Maven Central 上的 Oracle JDBC 公司驱动程序](https://web.archive.org/web/20220630012348/https://medium.com/oracledevs/all-in-and-new-groupids-oracle-jdbc-drivers-on-maven-central-a76d545954c6) [medium.com]
* [>> Hibernate 慢查询日志](https://web.archive.org/web/20220630012348/https://vladmihalcea.com/hibernate-slow-query-log/)
* [>> 向后兼容线程：使用 Method Handles 实现自旋等待](https://web.archive.org/web/20220630012348/https://4comprehension.com/jdk8-on-spin-wait/) [4comprehension.com]
* [>> 使用 jOOQ-Refaster 模块自动迁移已弃用的 jOOQ API](https://web.archive.org/web/20220630012348/https://blog.jooq.org/2020/02/25/use-the-jooq-refaster-module-for-automatic-migration-off-of-deprecated-jooq-api/) [blog.jooq.org]
* [>> Q&A：OpenJDK](https://web.archive.org/web/20220630012348/https://www.infoq.com/news/2020/02/OpenJDK-Verburg-Borges/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]，与 Microsoft 的 Martijn Verburg 和 Bruno Borges 一起
* [>> CVE 报告发布：Reactor Netty](https://web.archive.org/web/20220630012348/https://spring.io/blog/2020/02/27/cve-reports-published-for-reactor-netty) [spring.io]

#### 网络研讨会和演示：

* [>> 一个精彩的播客：Spring Cloud Contract 负责人 Marcin Grzejszczak 谈 Spring Cloud Contract、Spring Cloud Sleuth、持续集成等](https://web.archive.org/web/20220630012348/https://spring.io/blog/2020/02/28/a-bootiful-podcast-spring-cloud-contract-lead-marcin-grzejszczak-on-spring-cloud-contract-spring-cloud-sleuth-continuous-integration-and-more) [spring.io]
* [>> Spring 与关系数据库的连接](https://web.archive.org/web/20220630012348/https://www.infoq.com/presentations/spring-reactive-relational-database/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]
* [>> 如何与 Spring Boot 高效协作](https://web.archive.org/web/20220630012348/https://www.infoq.com/presentations/spring-boot-di-devtools-autocompletion/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]
* [>> Spring Data 的新特性是什么？](https://web.archive.org/web/20220630012348/https://www.infoq.com/presentations/spring-data-enhancements/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]
* [>> 大规模高分辨率遥测](https://web.archive.org/web/20220630012348/https://www.infoq.com/presentations/high-resolution-telemetry/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]
* [>> 平台揭开神秘面纱：Cloud Foundry、Kubernetes、Eirini 和 Knative](https://web.archive.org/web/20220630012348/https://www.infoq.com/presentations/cloud-foundry-kubernetes-project-eirini-kative/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]

#### 升级时间：

* [>> Spring Boot 2.2.5 发布](https://web.archive.org/web/20220630012348/https://spring.io/blog/2020/02/27/spring-boot-2-2-5-released) [spring.io] 和 [>> Spring Boot 2.1.13 发布](https://web.archive.org/web/20220630012348/https://spring.io/blog/2020/02/27/spring-boot-2-1-13-released) [spring.io]
* [>> Spring Data Moore SR5 和 Lovelace SR16 发布](https://web.archive.org/web/20220630012348/https://spring.io/blog/2020/02/26/spring-data-moore-sr5-and-lovelace-sr16-released) [spring.io]

## 2. 技术

### [>> Kubernetes 的 init container 的多功能性](https://web.archive.org/web/20220630012348/https://blog.frankel.ch/versatility-kubernetes-initcontainer/) [blog.frankel.ch]

initContainer 的介绍，它允许我们在运行时定制不可变图像的执行。

#### 同样值得一读：

* [>> SQL DISTINCT 不是函数](https://web.archive.org/web/20220630012348/https://blog.jooq.org/2020/03/02/sql-distinct-is-not-a-function/) [blog.jooq.org]
* [>> Spy vs. Spy——也称为“测试的两面性”](https://web.archive.org/web/20220630012348/https://blog.codecentric.de/en/2020/02/spy-vs-spy-aka-the-two-sides-of-the-testing-coin/) [blog.codecentric.de]
* [>> 关于接口隔离原则你需要知道的一切](https://web.archive.org/web/20220630012348/https://reflectoring.io/interface-segregation-principle/) [reflectoring.io]

## 3. 沉思

### [>> 疏通 Bug 管道](https://web.archive.org/web/20220630012348/https://www.satisfice.com/blog/archives/487131) [satisfice.com]

一篇关于测试系统的好文章，目的是**发现所有的错误**，如果发现了，可能会对我们的客户造成影响。

#### 同样值得一读：

* [>> 架构中的大象](https://web.archive.org/web/20220630012348/https://martinfowler.com/articles/value-architectural-attribute.html) [martinfowler.com]
* [>> Aeron 是消息解决方案的好选择吗？](https://web.archive.org/web/20220630012348/https://blog.scottlogic.com/2020/02/28/is-aeron-a-good-choice-for-a-messaging-solution.html) [blog.scottlogic.com]
* [>> 用 Testcontainers 和一种数据库系统进行 Quarkus 测试](https://web.archive.org/web/20220630012348/https://blog.codeleak.pl/2020/02/testcontainers-with-quarkus-tests.html) [blog.codeleak.pl]
* [>> 关于按小时计费的一个温和提议](https://web.archive.org/web/20220630012348/https://daedtech.com/a-modest-proposal-for-hourly-billing/) [daedtech.com]
* [>> Equifax 黑客被控犯罪](https://web.archive.org/web/20220630012348/https://www.infoq.com/news/2020/02/equifax-charges/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]

## 4. 漫画

本周我最喜欢的迪尔伯特。

### [>> 采购部](https://web.archive.org/web/20220630012348/https://dilbert.com/strip/2020-02-28) [dilbert.com]

### [>> 实用主义者](https://web.archive.org/web/20220630012348/https://dilbert.com/strip/2020-02-25) [dilbert.com]

### [>> 未命名](https://web.archive.org/web/20220630012348/https://dilbert.com/strip/2020-03-03) [dilbert.com]

## 5. 本周精选

### [>> 大多数远程公司不告诉你的远程工作](https://web.archive.org/web/20220630012348/https://doist.com/blog/remote-work-mental-health/) [doist.com]

Next **»** [Java Weekly, Issue 324](/web/20220630012348/https://www.baeldung.com/java-weekly-324) **«** Previous [Java Weekly, Issue 322](/web/20220630012348/https://www.baeldung.com/java-weekly-322)
