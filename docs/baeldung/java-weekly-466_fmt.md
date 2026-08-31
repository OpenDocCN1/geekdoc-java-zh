
# Java 周刊，第 466 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-466>

## 1. Spring 和 Java

[>> Spring Boot 3.0 Goes GA](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/24/spring-boot-3-0-goes-ga) Spring.io

期待已久的 Spring Boot 版来了！哦——这么多好东西，都基于 Java 17，更好的原生支持，还有很多值得探索的地方！

[>> Spring Integration 6.0 goes GA](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/29/spring-integration-6-0-goes-ga) Spring.io

还有，认识一下 `Spring Integration 6`：基于 Java 17，支持 AOT 和 GraalVM，增强的插装，以及 Jakarta EE 10。

[>> 反应性积垢性能：案例分析](https://web.archive.org/web/20221204204959/https://quarkus.io/blog/reactive-crud-performance-case-study/) Quarkus.io

关于基准测试的棘手本质：如何一步一步地将基准测试从 `1 RPS` 提高到 `26K RPS`！

### 同样值得一读

- [>> Spring Boot 3 和 Spring Framework 6 使用 Java 17 和 Jakarta EE 9，用 GraalVM 支持原生 Java](https://web.archive.org/web/20221204204959/https://www.infoq.com/news/2022/11/spring-6-spring-boot-3-launch/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)（InfoQ.com）
- [>> 异常 Java：`StackTrace` 扩展 `Throwable`](https://web.archive.org/web/20221204204959/https://foojay.io/today/unusual-java-stacktrace-extends-throwable/)（Foojay.io）
- [>> 贡献 `BigInteger.parallelMultiply()` 给 OpenJDK](https://web.archive.org/web/20221204204959/https://www.javaspecialists.eu/archive/Issue305-Contributing-BigInteger.parallelMultiply-to-OpenJDK.html)（JavaSpecialists.eu）
- [>> 文章：Java 冠军乔希·朗论 Spring Framework 6 与 Spring Boot 3](https://web.archive.org/web/20221204204959/https://www.infoq.com/articles/josh-long-spring-6/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)（InfoQ.com）
- [>> 流言蜚语：闲聊街区的活动总线](https://web.archive.org/web/20221204204959/https://foojay.io/today/metaphorical-programming-gossips-event-bus/)（Foojay.io）
- [>> Jakarta REST 3.1：Jakarta EE 10 有什么新鲜事？](https://web.archive.org/web/20221204204959/https://blog.payara.fish/whats-new-in-jakarta-rest-3.1-in-jakarta-ee-10)（Blog.payara.fish）

### 网络研讨会和演示

- [Spring Tips：通往 Spring Framework 6 之路：全新提前编译引擎和 GraalVM](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/23/spring-tips-the-road-to-spring-framework-6-the-new-ahead-of-time-compilation-engine-and-graalvm)（Spring.io）
- [>> 如何使用 Java 记录与 Quarkus](https://web.archive.org/web/20221204204959/https://blog.sebastian-daschner.com/entries/java-records-quarkus-enterprise)（Blog.sebastian-daschner.com）
- [>> 演示：面向 Java 开发者的 DevOps](https://web.archive.org/web/20221204204959/https://www.infoq.com/presentations/devops-java-devs/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)（InfoQ.com）
- [>> 展示：在 Java 中使用共享内存映射文件](https://web.archive.org/web/20221204204959/https://www.infoq.com/presentations/java-shared-memory-files/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)（InfoQ.com）
- [>> #92：Clojure：一种将改变你思考编程方式的语言](https://web.archive.org/web/20221204204959/https://nurkiewicz.com/92)（Nurkiewicz.com）

### 升级时间

- [>> Spring Boot 2.6.14 和 2.7.6 现已上市](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/24/spring-boot-2-6-14-available-now) / [2.7.6 现已上市](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/24/spring-boot-2-7-6-available-now)（Spring.io）
- [>> Spring Framework 6.0.2 现已可用](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/24/spring-framework-6-0-2-available-now)（Spring.io）
- [>> Spring Modulith 0.1 发布](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/24/spring-modulith-0-1-released)（Spring.io）
- [>> Spring Batch 5.0 GA](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/24/spring-batch-5-0-goes-ga)（Spring.io）
- [>> Spring Vault 3.0 GA](https://web.archive.org/web/20221204204959/https://spring.io/blog/2022/11/28/spring-vault-3-0-goes-ga)（Spring.io）
- [>> Quarkus 2.14.2.Final 发布](https://web.archive.org/web/20221204204959/https://github.com/quarkusio/quarkus/releases/tag/2.14.2.Final)（Quarkus.io）
- [>> Camel 3.18.4 发布](https://web.archive.org/web/20221204204959/https://github.com/apache/camel/releases/tag/camel-3.18.4)（Apache.org）

## 2. 技术与思考

[>> 网页缓存](https://web.archive.org/web/20221204204959/https://blog.frankel.ch/web-caching/)（Blog.frankel.ch）

通过缓存提高性能的各种方法的详尽目录：客户端、浏览器和服务器端。有趣的读物。

### 同样值得一读

- [>> `registry.k8s.io`：更快、更便宜、普遍可用（GA）](https://web.archive.org/web/20221204204959/https://kubernetes.io/blog/2022/11/28/registry-k8s-io-faster-cheaper-ga/)（Kubernetes.io）
- [>> 嘘……Kubernetes 的秘密其实不是秘密！](https://web.archive.org/web/20221204204959/https://auth0.com/blog/kubernetes-secrets-management/)（Auth0.com）
- [>> Kubernetes 的 6 个行之有效的云成本管理实践](https://web.archive.org/web/20221204204959/https://reflectoring.io/blog/2022/2022-11-24-6-cloud-cost-management-practices/)（Reflectoring.io）
- [>> 你做错了——招一个 DevRel](https://web.archive.org/web/20221204204959/https://foojay.io/today/youre-doing-it-wrong-recruiting-a-devrel/)（Foojay.io）
- [>> 按照惯例映射事件类型](https://web.archive.org/web/20221204204959/https://event-driven.io/en/hot_to_map_event_type_by_convention/)（Event-driven.io）
- [>> Web 资源缓存：客户端](https://web.archive.org/web/20221204204959/https://blog.frankel.ch/web-caching/client/)（Blog.frankel.ch）
- [>> 使用 `UNION`、`INTERSECT` 的最佳方式，以及与 Hibernate 的 `EXCEPT`](https://web.archive.org/web/20221204204959/https://vladmihalcea.com/hibernate-union-intersect-except/)（Vladmihalcea.com）
- [>> 事业画布](https://web.archive.org/web/20221204204959/https://blog.scottlogic.com/2022/11/29/The-career-canvas.html)（Blog.scottlogic.com）
- [>> 规则助你走得更快](https://web.archive.org/web/20221204204959/https://blog.scottlogic.com/2022/11/30/rules-help-you-go-faster.html)（Blog.scottlogic.com）

## 4. 漫画

- [>> 幸存者的罪恶感](https://web.archive.org/web/20221204204959/https://dilbert.com/strip/2022-12-03)（Dilbert.com）
- [>> 一切照旧](https://web.archive.org/web/20221204204959/https://dilbert.com/strip/2022-12-02)（Dilbert.com）
- [>> 道格伯特帮忙裁员](https://web.archive.org/web/20221204204959/https://dilbert.com/strip/2022-12-01)（Dilbert.com）

## 5. 本周精选

[>> 我是一个有着果蝇般记忆力的多产程序员](https://web.archive.org/web/20221204204959/https://hynek.me/articles/productive-fruit-fly-programmer/)（Hynek.me）
