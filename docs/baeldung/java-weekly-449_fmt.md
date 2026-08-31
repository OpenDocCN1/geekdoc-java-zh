
# Java 周刊，第 449 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-449>

## 1. Spring 和 Java

- [并行垃圾收集器 Java 的 SIP](https://web.archive.org/web/20220809143400/https://inside.java/2022/08/01/sip062/)【inside.java】

  `并行 GC` 速成班，其对吞吐量/延迟的影响，以及用于调优的常见配置参数。

- [Spring Data JDBC——使用序列生成主键](https://web.archive.org/web/20220809143400/https://thorben-janssen.com/spring-data-jdbc-sequence/)【thorben-janssen.com】

  了解 `BeforeConvertCallback`，从 Spring Data JDBC 的数据库序列中获取下一个自动递增的 `id`。

- [如何在 Spring Boot 应用中集成 Hibernate 多租户特性和 Spring Data JPA](https://web.archive.org/web/20220809143400/https://spring.io/blog/2022/07/31/how-to-integrate-hibernates-multitenant-feature-with-spring-data-jpa-in-a-spring-boot-application)【spring.io】

  关于如何在 Spring Boot 应用程序中使用 Hibernate 的多重租用和 Spring Data JPA 的实用指南。

### 同样值得一读

- [如何使用 PostgreSQL 的 JSONB 数据类型搭配 Hibernate](https://web.archive.org/web/20220809143400/https://thorben-janssen.com/persist-postgresqls-jsonb-data-type-hibernate/)【thorben-janssen.com】

- [用 Spring Data 寻找数据的 5 种方法](https://web.archive.org/web/20220809143400/https://springbootlearning.medium.com/5-ways-to-find-data-with-spring-data-91766c74fa8e)【springbootlearning.medium.com】

- [用特征标志测试基于时间的特征](https://web.archive.org/web/20220809143400/https://reflectoring.io/date-time-feature-flags/)【reflectoring.io】

- [从 Java 中调用存储过程的最佳方法：用 jOOQ](https://web.archive.org/web/20220809143400/https://blog.jooq.org/the-best-way-to-call-stored-procedures-from-java-with-jooq/)【blog.jooq.org】

- [使用 EasyRandom 和 Lombok `toBuilder` 来提高你的单元测试的可维护性](https://web.archive.org/web/20220809143400/https://jvwilge.github.io/en/2022/08/01/easy-random-to-builder.html)【jvwilge.github.io】

### 网络研讨会和演示

- [一个精彩的播客：RabbitMQ 养兔人丹·卡文](https://web.archive.org/web/20220809143400/https://spring.io/blog/2022/07/28/a-bootiful-podcast-rabbitmq-rabbit-herder-dan-carwin)【spring.io】

- [Java Q&A；莱登、瓦尔哈拉、琥珀，以及更多！——Java News Cast #30](https://web.archive.org/web/20220809143400/https://www.youtube.com/watch?v=ZaGnGs9TeNc)【YouTube.com】

- [现实生活中的 Java 模块](https://web.archive.org/web/20220809143400/https://inside.java/2022/08/01/java-modules-irl/)【inside.java】

- [织机与结构化并发的 Java 异步编程全教程——JEP Café #13](https://web.archive.org/web/20220809143400/https://inside.java/2022/08/02/jepcafe13/)【inside.java】

### 升级时间

- [Hibernate ORM 6.1.2.Final 发布](https://web.archive.org/web/20220809143400/https://in.relation.to/2022/08/03/hibernate-orm-612-final/)

- [Spring for Apache Kafka 2.9.0 可用](https://web.archive.org/web/20220809143400/https://spring.io/blog/2022/08/02/spring-for-apache-kafka-2-9-0-available)【spring.io】

- [Spring Cloud OpenFeign 3.0.8 现已推出](https://web.archive.org/web/20220809143400/https://spring.io/blog/2022/07/27/spring-cloud-openfeign-3-0-8-is-now-available)【spring.io】

- [Spring Authorization Server 即将发布 1.0](https://web.archive.org/web/20220809143400/https://spring.io/blog/2022/07/28/spring-authorization-server-is-going-1-0)【spring.io】

- [GraalVM Community Edition 22.2.0](https://web.archive.org/web/20220809143400/https://github.com/graalvm/graalvm-ce-builds/releases/tag/vm-22.2.0)【github.com/graalvm】

- [Oracle Helidon 3.0.0](https://web.archive.org/web/20220809143400/https://github.com/oracle/helidon/releases)【github.com/oracle】

- [Micronaut Framework 3.5.4 发布](https://web.archive.org/web/20220809143400/https://micronaut.io/2022/07/29/micronaut-framework-3-5-4-released/)【micronaut.io】

- [Netflix Conductor v3.10.2](https://web.archive.org/web/20220809143400/https://github.com/Netflix/conductor/releases)【github.com/Netflix】

- [Elastic Stack 8.3.3 发布](https://web.archive.org/web/20220809143400/https://www.elastic.co/blog/elastic-stack-8-3-3-released)【elastic.co】

- [JHipster 发布 v7.9.0](https://web.archive.org/web/20220809143400/https://www.jhipster.tech/2022/07/31/jhipster-release-7.9.0.html)【jhipster.tech】

- [Quarkus 2.11.1.Final 和 2.10.4.Final 发布](https://web.archive.org/web/20220809143400/https://quarkus.io/blog/quarkus-2-11-1-final-released/)【quarkus.io】

## 2. 技术与思考

- [比较低延迟消息队列中持久性的方法](https://web.archive.org/web/20220809143400/http://blog.vanillajava.blog/2022/08/comparing-approaches-to-durability-in.html)【vanilla-java.blog】

  通过网络将数据复制到辅助系统是否比同步到磁盘更快？也许有争议，但值得看一看基准！

### 同样值得一读

- [为什么 DevOps 治理对启用开发人员速度至关重要](https://web.archive.org/web/20220809143400/https://www.infoq.com/articles/devops-governance-developer-velocity/)【infoq.com】

- [什么是重构？](https://web.archive.org/web/20220809143400/https://blog.thecodewhisperer.com/permalink/what-is-refactoring)【blog.thecodewhisperer.com】

- [关于化妆品与编程中的内函数](https://web.archive.org/web/20220809143400/https://blog.frankel.ch/on-cosmetics-vs-intrinsics-programming/)【blog.frankel.ch】

- [Jetpack Compose 1.2 包含懒人网格，支持 Google 字体，还有更多](https://web.archive.org/web/20220809143400/https://www.infoq.com/news/2022/07/jetpack-compose-1-2/)【infoq.com】

- [数据网格——一个数据移动和处理平台@Netflix](https://web.archive.org/web/20220809143400/https://netflixtechblog.com/data-mesh-a-data-movement-and-processing-platform-netflix-1288bcab2873)【netflixtechblog.com】

## 3. 漫画

本周我最喜欢的迪尔伯特。

- [筹备 CEO](https://web.archive.org/web/20220809143400/https://dilbert.com/strip/2022-08-04)【dilbert.com】

- [元宇宙气候变化](https://web.archive.org/web/20220809143400/https://dilbert.com/strip/2022-08-03)【dilbert.com】

- [基金长 COVID 支持组](https://web.archive.org/web/20220809143400/https://dilbert.com/strip/2022-07-30)【dilbert.com】

## 4. 本周精选

有趣的阅读：

[请停止引用 TIOBE](https://web.archive.org/web/20220809143400/https://blog.nindalf.com/posts/stop-citing-tiobe/)【nindalf.com】

[« Previous：Java Weekly，第 448 期](/web/20220809143400/https://www.baeldung.com/java-weekly-448)
