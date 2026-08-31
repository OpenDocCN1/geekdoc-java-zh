
# Java 周刊，第 421 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-421>

## 1. Spring 和 Java

[**> > 使用 Spring 事务性注释的最佳方式**](https://web.archive.org/web/20221208143841/https://vladmihalcea.com/spring-transactional-annotation/)【vladmihalcea.com】

让我们重温一下过去的美好时光 `@Transactional`：正确的抽象层**，传播策略，隔离级别，只读事务**，等等！

[**> > 用 Spring 数据动态插入和更新 JPA**](https://web.archive.org/web/20221208143841/https://thorben-janssen.com/dynamic-inserts-and-updates-with-spring-data-jpa/)【thorben-janssen.com】

动态地**只包含与 Spring 数据 JPA 的插入/更新**相关的字段——这是一个隐藏的性能宝石，在某些场景中非常有用。

[**> > Spring 数据 JDBC–我如何才能对聚合根进行部分更新？**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/20/spring-data-jdbc-how-can-i-do-a-partial-update-of-an-aggregate-root)【spring.io】

**在 Spring 数据 JDBC 中处理部分更新**：减少了对聚集根、定制方法和原始 SQL 的查看。

#### 同样值得一读：

*   [**> > 根据 VDC 研究**](https://web.archive.org/web/20221208143841/https://blogs.oracle.com/java/post/java-is-1-choice-for-cloud-according-to-2021-vdc-research)【blogs.oracle.com】，Java 是云的首选
*   [**> > Java 集合的常见操作**](https://web.archive.org/web/20221208143841/https://reflectoring.io/common-operations-on-java-collections/)【reflectoring.io】
*   [**> > 用自定义 `RestTemplate` `HttpMessageConverter` 解析 CSV 响应**](https://web.archive.org/web/20221208143841/https://tech.asimio.net/2022/01/13/Parsing-CSV-responses-with-a-custom-RestTemplate-HttpMessageConverter.html)【tech.asimio.net】
*   [**> > JPA 和 Hibernate 中的 `flush mode`——它是什么以及如何改变它**](https://web.archive.org/web/20221208143841/https://thorben-janssen.com/flushmode-in-jpa-and-hibernate/)【thorben-janssen.com】
*   [**> > 用 `resilience4j` 处理 `WebClient`**](https://web.archive.org/web/20221208143841/https://arnoldgalovics.com/resilience4j-webclient/)【arnoldgalovics.com】
*   [**> > Java 语言如何更好地支持组合和委托**](https://web.archive.org/web/20221208143841/https://minborgsjavapot.blogspot.com/2022/01/how-java-language-could-better-support.html)【minborgsjavapot.com】

**网络研讨会和演示：**

*   [**> > Java 的 2022 年计划——Java 新闻播报 #18**](https://web.archive.org/web/20221208143841/https://inside.java/2022/01/13/insidejava-newscast-018/)【inside.java】
*   [**> > 第 21 集：JEP 421 与定案弃案**](https://web.archive.org/web/20221208143841/https://inside.java/2022/01/12/podcast-021/)【inside.java】
*   [**> > 一段精彩播客：春云数据流传奇 Sabby Anandan**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/13/a-bootiful-podcast-spring-cloud-data-flow-legend-sabby-anandan)【spring.io】

**升级时间：**

*   [**> > Spring Boot 2.5.9**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/20/spring-boot-2-5-9-available-now) **和 2.6.3 现已上市**【spring.io】
*   [**> > 冬眠 ORM 5.6.4.Final 发布**](https://web.archive.org/web/20221208143841/https://in.relation.to/2022/01/19/hibernate-orm-564/)
*   [**> > 春安 6.0.0-M1 和 5.7.0-M1 现已推出**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/17/spring-security-6-0-0-m1-and-5-7-0-m1-available-now)【spring.io】
*   [**> > 春假文档 2.0.6.发布**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/17/spring-rest-docs-2-0-6-release)【spring.io】
*   [**> > 春季数据 2021.1 SR1 和 2021.0 SR8 发布**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/14/spring-data-2021-1-sr1-and-2021-0-sr8-released)【spring.io】
*   [**> > 第一春数据 2022.0.0 和 2021.2.0 里程碑发布**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/14/first-spring-data-2022-0-0-and-2021-2-0-milestones-released)【spring.io】
*   [**> > Spring 框架 6.0.0-M2 和 5.3.15 现已可用**](https://web.archive.org/web/20221208143841/https://spring.io/blog/2022/01/13/spring-framework-6-0-0-m2-and-5-3-15-available-now)【spring.io】
*   [**> > 弹力栈 7.16.3 发布**](https://web.archive.org/web/20221208143841/https://www.elastic.co/blog/elastic-stack-7-16-3-released)【elastic.co】
*   [**> > micronaut 3.2.6**](https://web.archive.org/web/20221208143841/https://github.com/micronaut-projects/micronaut-core/releases)【github.com】

## 2. 技术

[**> > 微服务基准测试 Kafka vs Chronicle：哪个快 750 倍？**](https://web.archive.org/web/20221208143841/http://blog.vanillajava.blog/2022/01/benchmarking-kafka-vs-chronicle-for.html)【blog.vanillajava.blog】

一个比较 `Chronicle Queue` 和 `Apache Kafka` 的有趣基准测试——**Kafka 可能不是这项工作的最佳工具，尤其是对于延迟密集型应用程序！**

**同样值得一读：**

*   [**> > 两阶段提交**](https://web.archive.org/web/20221208143841/https://martinfowler.com/articles/patterns-of-distributed-systems/two-phase-commit.html)【martinfowler.com】
*   [**> > 网飞数据平台**](https://web.archive.org/web/20221208143841/https://netflixtechblog.com/auto-diagnosis-and-remediation-in-netflix-data-platform-5bcc52d853d1)【netflixtechblog.com】
*   [**> > 关于微服务起步的真相**](https://web.archive.org/web/20221208143841/https://arnoldgalovics.com/truth-about-microservices/)【arnoldgalovics.com】
*   [**> > 一个很少见到，但很有用的 SQL 特性：对应**](https://web.archive.org/web/20221208143841/https://blog.jooq.org/a-rarely-seen-but-useful-sql-feature-corresponding/)【blog.jooq.org】
*   [**> > 服务对服务呼叫模式——多集群入口**](https://web.archive.org/web/20221208143841/http://www.java-allandsundry.com/2022/01/service-to-service-call-pattern-multi.html)【java-allandsundry.com】
*   [**> > 您正在运行不受信任的代码！**](https://web.archive.org/web/20221208143841/https://blog.frankel.ch/running-untrusted-code/)【blog.frankel.ch】
*   [**> > 如何周期性调用一个 Lambda 函数**](https://web.archive.org/web/20221208143841/https://advancedweb.hu/how-to-periodically-call-a-lambda-function/)【advancedweb.hu】
*   [**> > 如何在 GraphQL API 中实现访问控制**](https://web.archive.org/web/20221208143841/https://advancedweb.hu/how-to-implement-access-control-in-a-graphql-api/)【advancedweb.hu】

## 3. 沉思

[**> > 损耗成本**](https://web.archive.org/web/20221208143841/https://benjiweber.co.uk/blog/2022/01/12/cost-of-attrition/)【benjiweber.co.uk】

失去一个人并不能总是通过雇佣一个新的替代者来补偿！一个关于更多隐性损耗成本的好观点。

**同样值得一读：**

*   [**> > 把事情写下来（2022）**](https://web.archive.org/web/20221208143841/https://abdullin.com/write-things-down/)【abdullin.com】
*   [**> > 用户故事、任务和 bug 的吉拉模板**](https://web.archive.org/web/20221208143841/https://blog.codecentric.de/en/2022/01/jira-template-user-story-tasks-bugs/)【blog.codecentric.de】
*   [**> > 实验是整个网飞数据科学的一大重点**](https://web.archive.org/web/20221208143841/https://netflixtechblog.com/experimentation-is-a-major-focus-of-data-science-across-netflix-f67923f8e985)【netflixtechblog.com】

## 4. 漫画

本周我最喜欢的迪尔伯特。

[**> > 北极熊预测**](https://web.archive.org/web/20221208143841/https://dilbert.com/strip/2022-01-19)【dilbert.com】

[**> >**](https://web.archive.org/web/20221208143841/https://dilbert.com/strip/2022-01-16)【dilbert.com】

[**> > 卡特伯特不制定规则**](https://web.archive.org/web/20221208143841/https://dilbert.com/strip/2022-01-15)【dilbert.com】

## 5. 本周精选

[**> > 2022 年 Java 冠军大会**](https://web.archive.org/web/20221208143841/https://jchampionsconf.com/speakers.html)

Next **»** [Java Weekly, Issue 422](/web/20221208143841/https://www.baeldung.com/java-weekly-422) **«** Previous [Java Weekly, Issue 420](/web/20221208143841/https://www.baeldung.com/java-weekly-420)
