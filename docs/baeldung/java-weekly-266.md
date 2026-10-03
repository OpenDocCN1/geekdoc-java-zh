
# Java 周刊，第 266 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-266>

**开始了……**

## 1. Spring 和 Java

### 测试 CDI Beans 和 Java SE 下的持久层

这是一篇关于使用 Weld 测试 JPA 层和业务逻辑层之间的交互而不会导致容器部署开销的好文章。

原文链接：<https://web.archive.org/web/20221205122837/http://in.relation.to/2019/01/23/testing-cdi-beans-and-persistence-layer-under-java-se/>

### 向测试项目添加输入和输出参数动作

使用`@Parameter`注释在 TestProject 插件中创建参数化动作的简单例子。

原文链接：<https://web.archive.org/web/20221205122837/https://www.petrikainulainen.net/programming/testing/adding-input-and-output-parameters-to-testproject-actions/>

### 如何用 JPA 和 Hibernate 对 SQL 保留关键字进行转义

解决这个问题的几种方法——在`@Table`和`@Column`注释中显式使用转义符，以及使用全局 Hibernate 属性。

原文链接：<https://web.archive.org/web/20221205122837/https://vladmihalcea.com/escape-sql-reserved-keywords-jpa-hibernate/>

### 用键盘锁保护 Spring Boot Admin 和 Actuator 端点

帮助您保护管理应用程序本身及其监控的应用程序的执行器端点的全面指南。

原文链接：<https://web.archive.org/web/20221205122837/https://blog.codecentric.de/en/2019/01/securing-spring-boot-admin-actuator-endpoints-keycloak/>

### 同样值得一读

- 使用 JDK 12 压缩数字格式自定义压缩数字模式：<https://web.archive.org/web/20221205122837/https://marxsoftware.blogspot.com/2019/01/custom-compact-number-patterns.html>
- 厄拉多塞的筛子：<https://web.archive.org/web/20221205122837/https://blog.frankel.ch/sieve-eratosthenes/>
- 为什么、何时以及如何使用 JPA 和 Hibernate 进行 DTO 投影：<https://web.archive.org/web/20221205122837/https://thoughts-on-java.org/dto-projections/>
- Spring Data Redis：使用 Sentinel 实现高可用：<https://web.archive.org/web/20221205122837/https://michaelcgood.com/spring-data-redis-sentinel/>
- 代码审查清单：Java 并发：<https://web.archive.org/web/20221205122837/https://medium.com/@leventov/code-review-checklist-java-concurrency-49398c326154>
- 克服标准并行流的局限性：<https://web.archive.org/web/20221205122837/https://github.com/pivovarit/parallel-collectors>
- 使用嵌入式 Elasticsearch 在随机端口上运行 JUnit 5 集成测试：<https://web.archive.org/web/20221205122837/https://vanwilgenburg.wordpress.com/2019/01/22/embedded-elasticsearch-junit5-spring-boot/>

### 网络研讨会和演示

- Spring 技巧：Reactor 上下文：<https://web.archive.org/web/20221205122837/https://spring.io/blog/2019/01/30/spring-tips-the-reactor-context>
- 精彩的播客：与 Spring Boot 工程师 Madhura Bhave 的访谈：<https://web.archive.org/web/20221205122837/https://spring.io/blog/2019/01/25/a-bootiful-podcast-an-interview-with-spring-boot-engineer-madhura-bhave>
- 重新思考遗留问题和单体系统：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/monolith-legacy-rethinking>
- 在初创公司中构建机器学习 MVP：<https://web.archive.org/web/20221205122837/https://www.infoq.com/podcasts/building-machine-learning-mvp>
- 在 Kubernetes 上部署应用程序所需了解的一切：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/kubernetes-deployment-primitives>
- Kubernetes 解剖：主要组件介绍：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/kubernetes-yaml>
- p 到 v 到 c：将一切引入容器的价值：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/containers-infrastructure-virtualization>
- 测量标准至关重要——从简单到有效：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/metrics-grouping>
- 学习热爱类型系统：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/type-system-typescript-flow-graphql>
- Intel 的云原生转型：<https://web.archive.org/web/20221205122837/https://www.infoq.com/presentations/intel-cloud-native-microservices>

### 升级时间

- Spring Tools 4.1.1 发布：<https://web.archive.org/web/20221205122837/https://spring.io/blog/2019/01/25/spring-tools-4-1-1-released>
- Spring IO 平台 Cairo-SR7：<https://web.archive.org/web/20221205122837/https://spring.io/blog/2019/01/24/spring-io-platform-cairo-sr7>
- Spring IO 平台 Brussels-SR16：<https://web.archive.org/web/20221205122837/https://spring.io/blog/2019/01/24/spring-io-platform-brussels-sr16>
- Spring Cloud Greenwich 已发布：<https://web.archive.org/web/20221205122837/https://spring.io/blog/2019/01/23/spring-cloud-greenwich-release-is-now-available>

## 2. 技术和思考

### 用行为驱动开发和面向接口设计开发微服务

这两套设计原则的集成可以帮助您创建定义良好的服务，这些服务可以很好地协同工作。

原文链接：<https://web.archive.org/web/20221205122837/https://www.infoq.com/articles/microservices-bdd-interface-oriented>

### 这 4 道质量关每个 SRE 队晋级前都必须检查代号

一套比较的质量测量，其中机器学习和人工智能融合在一起，易于实现，可以帮助你阻止糟糕的发布被部署到生产。

原文链接：<https://web.archive.org/web/20221205122837/https://blog.overops.com/the-4-quality-gates-every-sre-team-must-check-before-promoting-code/>

### 同样值得一读

- 使用 GCP 身份感知代理进行 API 认证：<https://web.archive.org/web/20221205122837/https://bravenewgeek.com/api-authentication-with-gcp-identity-aware-proxy/>
- AWS：如何通知 root 账号登录：<https://web.archive.org/web/20221205122837/https://advancedweb.hu/2019/01/30/root_login_notifications/>
- Microsoft 在 Azure API 管理中宣布 OpenAPI 规范 V3 的预览版：<https://web.archive.org/web/20221205122837/https://www.infoq.com/news/2019/01/openapi-v3-support-azure-apim>

## 3. 漫画

本周我最喜欢的迪尔伯特。

- 极品：<https://web.archive.org/web/20221205122837/https://dilbert.com/strip/2019-01-30>
- 新形态：<https://web.archive.org/web/20221205122837/https://dilbert.com/strip/2019-01-29>
- 自动驾驶汽车：<https://web.archive.org/web/20221205122837/https://dilbert.com/strip/2019-01-24>

## 4. 本周精选

### 正则表达式教程——举例说明

原文链接：<https://web.archive.org/web/20221205122837/https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285>

下一期 [Java 周刊，第 267 期](/web/20221205122837/https://www.baeldung.com/java-weekly-267)

上一期 [Java 周刊，第 265 期](/web/20221205122837/https://www.baeldung.com/java-weekly-265)
