
# Java 周刊，第 259 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-259>

**开始了……**

## 1. Spring 和 Java

### 反应式编程与关系数据库

[spring.io](https://web.archive.org/web/20220625165854/https://spring.io/blog/2018/12/07/reactive-programming-and-relational-databases)

简要了解一下`R2DBC`为什么可能会赢得将反应式编程模型与`RDBMS`堆栈集成的竞赛。非常刺激。

### 什么是 Java 对象 equals() 契约？

[dolszewski.com](https://web.archive.org/web/20220625165854/http://dolszewski.com/java/java-object-equals-contract/)

一篇快速的文章，描述了当我们的实现没有遵守这个基本的但经常被误解的 Java 契约时会发生什么。

### Micronaut 教程：第二部分：轻松分布式追踪、JWT 安全和 AWS Lambda 部署

[infoq.com](https://web.archive.org/web/20220625165854/https://www.infoq.com/articles/micronaut-tracing-security-serverless)

本系列的第二部分使用基于 JVM 的 Micronaut 框架深入探讨了**高级解决方案**。

### 如何用 Hibernate 事件监听器拦截实体变化

[vladmihalcea.com](https://web.archive.org/web/20220625165854/https://vladmihalcea.com/hibernate-event-listeners/)

还有一篇文章详细介绍了**如何使用事件监听器机制将实体更改复制到其他数据库表**。非常酷。

#### 同样值得一读：

- [JMS 3.0：介入！](https://web.archive.org/web/20220625165854/https://www.tomitribe.com/blog/jms-3-0-get-involved/) [tomitribe.com]
- [How to use Joor](https://web.archive.org/web/20220625165854/https://blog.jooq.org/2018/12/07/how-to-unit-test-your-annotation-processor-using-joor/) [blog.jooq.org] to conduct unit test on your annotation processor
- [Delete the original character string](https://web.archive.org/web/20220625165854/https://marxsoftware.blogspot.com/2018/12/jdk12-dropping-raw-string-literals.html) from JDK 12 [marxsoftware.blogspot.com]
- [Automatic cache invalidation by changing data capture](https://web.archive.org/web/20220625165854/https://debezium.io/blog/2018/12/05/automating-cache-invalidation-with-change-data-capture/) [vladmihalcea.com]

#### 网络研讨会和演示：

- [测试 Spring 应用及其服务](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/test-spring-apps-services) [infoq.com]
- [Spring 提示：Bootiful Google 云平台](https://web.archive.org/web/20220625165854/https://spring.io/blog/2018/12/12/spring-tips-bootiful-google-cloud-platform) [spring.io]
- [容器——它们的用途是什么？](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/containers-net) [infoq.com]
- [Sleuth 如何勇敢地破解“太多代码”案例](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/spring-sleuth-brave) [infoq.com]
- [零到多云](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/spring-cloud-pipelines-spinnaker) [infoq.com]
- [Expect the unexpected：如何优雅地处理错误](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/handling-error-circuit-breaker) [infoq.com]
- [Great migration：从单体到面向服务](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/airbnb-soa-migration) [infoq.com]
- [用于软件测试的深度学习 AI：是否可能？](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/software-testing-deep-learning) [infoq.com]
- [AI、企业与你：介绍与验证](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/ai-primer-enterprise) [infoq.com]
- [Netflix 的全周期开发者](https://web.archive.org/web/20220625165854/https://www.infoq.com/presentations/netflix-devops) [infoq.com]
- [Netflix 的 Sangita Narayanan 谈提升开发者体验](https://web.archive.org/web/20220625165854/https://www.infoq.com/podcasts/improving-developer-experience-netflix) [infoq.com]

#### 升级时间：

- [Spring Tools 4.0.2 发布](https://web.archive.org/web/20220625165854/https://spring.io/blog/2018/12/05/spring-tools-4-0-2-released) [spring.io]
- [Spring IO Platform Cairo-SR6](https://web.archive.org/web/20220625165854/https://spring.io/blog/2018/12/06/spring-io-platform-cairo-sr6) [spring.io]
- [Spring REST Docs 2.0.3. 发布](https://web.archive.org/web/20220625165854/https://spring.io/blog/2018/12/10/spring-rest-docs-2-0-3-release) [spring.io] 和 [Spring REST Docs 1.2.6. 发布](https://web.archive.org/web/20220625165854/https://spring.io/blog/2018/12/10/spring-rest-docs-1-2-6-release)
- [GitHub Desktop 1.5 简化合并冲突解决](https://web.archive.org/web/20220625165854/https://www.infoq.com/news/2018/12/github-desktop-1.5-released) [infoq.com]
- [Hibernate ORM 6.0.0.Alpha1 发布](https://web.archive.org/web/20220625165854/http://in.relation.to/2018/12/06/hibernate-orm-600-alpha1-out/)
- [IntelliJ IDEA 2018.3 带来对即将推出的 Java 12 的支持、Spring Boot 增强等](https://web.archive.org/web/20220625165854/https://www.infoq.com/news/2018/12/intellij-idea-2018.3) [infoq.com]

## 2. 技术和思考

### 界面编程限制

[blog.frankel.ch](https://web.archive.org/web/20220625165854/https://blog.frankel.ch/limits-programming-interface/)

提醒你严格遵守这个基本的编程原则并不总是最好的选择。

### 有没有可能出现一个没有办公室政治的公司？

[daedtech.com](https://web.archive.org/web/20220625165854/https://daedtech.com/company-no-office-politics/)

虽然办公室政治不可避免，但还是有一些健康的办公室政治值得一探究竟。

#### 同样值得一读：

- [连续基础设施与 Ansible、Molecule 和 TravisCI](https://web.archive.org/web/20220625165854/https://blog.codecentric.de/en/2018/12/continuous-infrastructure-ansible-molecule-travisci/) [blog.codecentric.de]
- [将敏捷开发应用于工业机械](https://web.archive.org/web/20220625165854/https://www.infoq.com/articles/agile-developing-industrial-machinery) [infoq.com]
- [再见，EdgeHTML](https://web.archive.org/web/20220625165854/https://blog.mozilla.org/blog/2018/12/06/goodbye-edge/) [infoq.com]
- [#账单预测](https://web.archive.org/web/20220625165854/https://www.mnot.net/blog/2018/12/06/predictions) [mnot.net]

## 3. 漫画

本周我最喜欢的迪尔伯特。

- [写下自己的绩效评估](https://web.archive.org/web/20220625165854/https://dilbert.com/strip/2018-12-12) [dilbert.com]
- [马盲为开办公计划](https://web.archive.org/web/20220625165854/https://dilbert.com/strip/2018-12-08) [dilbert.com]
- [行业术语](https://web.archive.org/web/20220625165854/https://dilbert.com/strip/2018-12-06) [dilbert.com]

## 4. 本周精选

[减去](https://web.archive.org/web/20220625165854/https://sivers.org/subtract) [sivers.org]

下一期 [Java 周刊，第 260 期](/web/20220625165854/https://www.baeldung.com/java-weekly-260) 上一期 [Java 周刊，第 258 期](/web/20220625165854/https://www.baeldung.com/java-weekly-258)
