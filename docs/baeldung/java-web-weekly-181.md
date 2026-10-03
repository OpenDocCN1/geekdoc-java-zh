
# Java 周刊，第 181 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-web-weekly-181>

本周有很多关于 Java 9 的有趣文章。

**开始了……**

## 1. Spring 和 Java

#### [>>用 JUnit 5 进行清洁器参数化测试](https://web.archive.org/web/20220626193834/http://blog.codeleak.pl/2017/06/cleaner-parameterized-tests-with-junit-5.html) [blog.codeleak.pl]

`JUnit 5`带来了许多令人兴奋的新特性——其中之一肯定是对参数化测试的**原生支持。**

#### [>>用 JPA 和 Hibernate 映射`@DiscriminatorColumn`的最佳方法](https://web.archive.org/web/20220626193834/https://vladmihalcea.com/2017/06/13/the-best-way-to-map-the-discriminatorcolumn-with-jpa-and-hibernate/) [vladmihalcea.com]

绘制`@DiscriminatorColumn`的快速而全面的指南。

**同样值得一读:**

*   [>>社区到底该不该接手 JSF.next？](https://web.archive.org/web/20220626193834/http://arjan-tijms.omnifaces.org/2017/06/should-community-take-over-jsfnext-or.html) [arjan-tijms.omnifaces.org]
*   [>>使用 Kotlin 的`apply()`函数进行动态 SQL 与 jOOQ](https://web.archive.org/web/20220626193834/https://blog.jooq.org/2017/06/09/using-kotlins-apply-function-for-dynamic-sql-with-jooq/) [jooq.org]
*   [>>使用 Spring Boot、CXF 和 Swagger 实现 API](https://web.archive.org/web/20220626193834/http://tech.asimio.net/2017/06/12/Implementing-APIs-using-Spring-Boot-CXF-and-Swagger.html) [tech.asimio.net]
*   [>>不喜欢依赖注入](https://web.archive.org/web/20220626193834/https://engineering.snagajob.com/dont-like-dependency-injection-898de93dc8d3) [engineering.snagajob.com]
*   [>>使用精确的 Java 方法参数](https://web.archive.org/web/20220626193834/https://minborgsjavapot.blogspot.com/2017/06/use-precise-java-method-parameters.html) [minborgsjavapot.blogspot.com]
*   [>>IntelliJ IDEA 2017.2 EAP：在调试器中过滤数组和集合，Java 9 的模块依赖图等](https://web.archive.org/web/20220626193834/https://blog.jetbrains.com/idea/2017/06/intellij-idea-2017-2-eap-filtering-arrays-and-collections-in-debugger-module-dependency-diagram-for-java-9-and-more/) [jetbrains.com]

**网络研讨会和演示:**

*   [>>物联网的战略思考](https://web.archive.org/web/20220626193834/https://www.infoq.com/presentations/embeded-iot-mqtt?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com]
*   [>>现实版 Java 9](https://web.archive.org/web/20220626193834/https://www.infoq.com/presentations/java9-flow-stream-api) [infoq.com]

**升级时间:**

*   [>>Spring Framework 4.3.9 现已可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/07/spring-framework-4-3-9-available-now) [spring.io]
*   [>>Spring Boot 1.5.4 现已可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/spring-boot-1-5-4-available-now) [spring.io]
*   [>>Spring Boot 1.4.7 现已可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/spring-boot-1-4-7-available-now) [spring.io]
*   [>>Spring Data Ingalls SR4 和 Hopper SR11 发布](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/spring-data-ingalls-sr4-and-hopper-sr11-released) [spring.io]
*   [>>CVE-2017-4995：Spring Security 4.2.3 发布](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/cve-2017-4995-spring-security-4-2-3-released) [spring.io]
*   [>>Spring Cloud Pipelines M5 发布](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/07/spring-cloud-pipelines-1-0-0-m5-released) [spring.io]
*   [>>Spring for Apache Kafka 1.2.2 和 1.1.6 可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/spring-for-apache-kafka-1-2-2-and-1-1-6-available) [spring.io]
*   [>>Spring AMQP 1.6.10 和 1.7.3 可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/spring-amqp-1-6-10-and-1-7-3-available) [spring.io]
*   [>>Spring Integration 4.3.10 可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/08/spring-integration-4-3-10-is-available) [spring.io]
*   [>>Spring Framework 5.0 RC2 现在可用](https://web.archive.org/web/20220626193834/https://spring.io/blog/2017/06/14/spring-framework-5-0-rc2-available-now) [spring.io]
*   [>>Hibernate Search 5.8.0.Beta3 发布，分析器配置更简单，AWS 兼容性和 DI 集成](https://web.archive.org/web/20220626193834/http://in.relation.to/2017/06/13/hibernate-search-5-8-0-Beta3/)

## 2. 技术

#### [>>“有效的 Java”可能如何影响 Kotlin 的设计——第一部分](https://web.archive.org/web/20220626193834/https://hackernoon.com/how-effective-java-may-have-influenced-the-design-of-kotlin-part-1-45fd64c2f974) [hackernoon.com]

一个非常有趣的分析，关于“有效的 Java”中的一些中心点如何塑造了 Kotlin 的设计。

#### [>>使用 WebCrypto API 的电子签名](https://web.archive.org/web/20220626193834/https://techblog.bozho.net/electronic-signature-using-webcrypto-api/) [techblog.bozho.net]

使用 WebCrypto API“放置”电子签名的有趣想法。

**同样值得一读:**

*   [>>Square 的机器人工程师 Jack Wharton 在 ETE 接受 InfoQ 采访](https://web.archive.org/web/20220626193834/https://www.infoq.com) [www.infoq.com]
*   [>>JSON Feed 与 Hugo](https://web.archive.org/web/20220626193834/https://bitquabit.com/post/json-feed-with-hugo/) [bitquabit.com]
*   [>>使用 AWS Greengrass 解锁设备数据的价值](https://web.archive.org/web/20220626193834/http://www.allthingsdistributed.com/2017/06/unlocking-value-device-data-aws-greengrass.html) [allthingsdistributed.com]
*   [>>当你尝试高可用性日志记录并以“大部分可用”告终——如何使用 TCP 和 HAProxy 以及 GELF 设置日志回溯](https://web.archive.org/web/20220626193834/https://vanwilgenburg.wordpress.com/2017/06/12/haproxy-logging-logback-gelf/) [vanwilgenburg.wordpress.com]
*   [>>Kotlin 的一个 SonarQube 插件——铺路](https://web.archive.org/web/20220626193834/https://blog.frankel.ch/sonarqube-plugin-kotlin/1/#gsc.tab=0) [frankel.ch]

## 3. 沉思

#### [>>慢网站的隐藏费用](https://web.archive.org/web/20220626193834/http://www.daedtech.com/hidden-costs-slow-websites/) [daedtech.com]

拥有一个慢速网站的成本可能比你想象的要高，所以在性能上投资总是一个好主意。

**同样值得一读:**

*   [>>开发者招聘流程已损坏](https://web.archive.org/web/20220626193834/https://builttoadapt.io/the-developer-hiring-process-is-broken-672bf273c183) [builttoadapt.io]
*   [>>工具不重要](https://web.archive.org/web/20220626193834/http://www.ontestautomation.com/the-tool-is-not-important/) [ontestautomation.com]
*   [>>自由软件开发：与你的买家交谈](https://web.archive.org/web/20220626193834/http://www.daedtech.com/freelance-software-development-buyers/) [daedtech.com]

## 4. 漫画

#### 本周我最喜欢的迪尔伯特。

#### [>>晚了两个小时](https://web.archive.org/web/20220626193834/http://dilbert.com/strip/2016-05-13) [dilbert.com]

#### [>>很难成为被误解的天才](https://web.archive.org/web/20220626193834/http://dilbert.com/strip/2016-05-14) [dilbert.com]

#### [>>我的欧洲假期明天开始](https://web.archive.org/web/20220626193834/http://dilbert.com/strip/2016-05-02) [dilbert.com]

## 5. 本周精选

#### [>>9 个登录你的 Java 应用程序的罪过](https://web.archive.org/web/20220626193834/https://stackify.com/9-logging-sins-java/) [stackify.com]
