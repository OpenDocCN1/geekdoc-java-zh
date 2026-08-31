
# Java 周刊，第 198 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-198>

## 1. Spring 和 Java

### [>> JUnit 5 教程：编写嵌套测试](https://web.archive.org/web/20220524005626/https://www.petrikainulainen.net/programming/testing/junit-5-tutorial-writing-nested-tests/)【petrikainulainen.net】

旧的 JUnit 中有时完全没有分层测试。

### [>> 标杆 JDK `String.replace()` vs 阿帕奇 Commons `StringUtils.replace()`](https://web.archive.org/web/20220524005626/https://blog.jooq.org/2017/10/11/benchmarking-jdk-string-replace-vs-apache-commons-stringutils-replace/)【blog.jooq.org】

原来 **`String.replace()`在内部使用了`Pattern`类**——这导致了许多不必要的分配🙂

### [>> 如何用 JPA 和 Hibernate 连接不相关的实体](https://web.archive.org/web/20220524005626/https://vladmihalcea.com/2017/10/10/how-to-join-unrelated-entities-with-jpa-and-hibernate/)【vladmihalcea.com】

“连接”互不引用的实体的快速指南。

### [>> 日蚀宝典](https://web.archive.org/web/20220524005626/https://www.infoq.com/articles/eclipse-collections)【infoq.com】

`Eclipse`集合是标准集合 API 的一个有趣的替代品。

#### 同样值得一读：

*   [>> `Flyway` and Introduction to Version-based Database Migration](https://web.archive.org/web/20220524005626/https://www.thoughts-on-java.org/flyway-getting-started/) [thoughts-on-java.org]
*   [>> Junit 5 - 快速教程](https://web.archive.org/web/20220524005626/http://blog.codeleak.pl/2017/10/junit-5-basics.html) [blog.codeleak.pl]
*   [>> Routing request, using Chunyun Zuul server to dynamically refresh the route](https://web.archive.org/web/20220524005626/http://tech.asimio.net/2017/10/10/Routing-requests-and-dynamically-refreshing-routes-using-Spring-Cloud-Zuul-Server.html) [tech.asimio.net]
*   [>> Oracle Bone Inscriptions announced that it plans to open source all the features of its JDK, and solve the shortcomings of Java EE](https://web.archive.org/web/20220524005626/https://www.infoq.com/news/2017/10/javaone-opening) [infoq.com]
*   [>> Implement the function list data structure in Cotrim](https://web.archive.org/web/20220524005626/http://www.java-allandsundry.com/2017/10/kata-implementing-functional-list-data.html) [java-allandsundry.com]
*   [>> IntelliJ IDEA 2017.3 EAP：可配置命令行缩短器和更多](https://web.archive.org/web/20220524005626/https://blog.jetbrains.com/idea/2017/10/intellij-idea-2017-3-eap-configurable-command-line-shortener-and-more/)【blog.jetbrains.com】

**网络研讨会和演示：**

*   [>> 现实世界 Java 9](https://web.archive.org/web/20220524005626/https://blog.jetbrains.com/idea/2017/10/real-world-java-9/)【blog.jetbrains.com】
*   [>> 春天提示：Bootiful，无功斯卡拉](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/11/spring-tips-bootiful-reactive-scala)【spring.io】
*   [>> Dave Sayer - 道路没有服务器：Chunyun function](https://web.archive.org/web/20220524005626/https://www.youtube.com/watch?v=I2Yu3YoC-mw) [youtube.com]

**升级时间：**

*   [>> 春安 M5 发布](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/10/spring-security-5-0-0-m5-released)【spring.io】
*   [>> Spring Boot 2.0.0 M5 现在可用](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/12/spring-boot-2-0-0-m5-available-now)【spring.io】
*   [>> 春天 AMQP 2.0.0 发布可用](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/05/spring-amqp-2-0-0-release-available)【spring.io】
*   [>> 春天工具套件 3.9.1 发布](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/12/spring-tool-suite-3-9-1-released)【spring.io】
*   [>> 春云流 1.3 谬嘎](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/06/spring-cloud-stream-1-3-goes-ga)【spring.io】
*   [>> Spring data released by ingels SR8](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/11/spring-data-ingalls-sr8-released)【spring.io】
*   [>> 春天框架 4.3.12 现已可用](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/10/spring-framework-4-3-12-available-now)【spring.io】
*   [>> 弹簧跳马 1.1.0 正式版和 M3 可用](https://web.archive.org/web/20220524005626/https://spring.io/blog/2017/10/06/spring-vault-1-1-0-ga-and-2-0-0-m3-available)【spring.io】

## 2. 技术

### [>> 真正不可变的构建](https://web.archive.org/web/20220524005626/https://blog.frankel.ch/truly-immutable-builds/#gsc.tab=0)【blog.frankel.ch】

确保构建中尽可能多的**方面是不可变的**——即使经过很长一段时间，也会产生更可靠的构建。

#### 同样值得一读：

*   [>> Set Cassandra Cluster in Aws](https://web.archive.org/web/20220524005626/https://techblog.bozho.net/setting-cassandra-cluster-aws/) [techblog.bozho.net]
*   [>> 爪哇开发人员的 NoSQL 选项，第二部分](https://web.archive.org/web/20220524005626/https://developer.okta.com/blog/2017/10/10/nosql-options-for-java-developers-part-ii)【developer.okta.com】
*   [>> Introduction gluon: a new machine learning library from AWS and Microsoft](https://web.archive.org/web/20220524005626/https://aws.amazon.com/blogs/aws/introducing-gluon-a-new-library-for-machine-learning-from-aws-and-microsoft/) [aws.amazon.com]

## 3. 沉思

### [>> 如何像人一样做代码评审（上）](https://web.archive.org/web/20220524005626/https://mtlynch.io/human-code-reviews-1/)【mtlynch.io】

做好代码评审非常有趣，但一般来说**也是交流**。

#### 同样值得一读：

*   [>> Importance of performance in development](https://web.archive.org/web/20220524005626/https://www.daedtech.com/importance-performance-development-side/) [daedtech.com]
*   [>> Preface to Building Evolutionary Architecture](https://web.archive.org/web/20220524005626/https://martinfowler.com/articles/evo-arch-forward.html) [martinfowler.com]

## 4. 漫画

本周我最喜欢的迪尔伯特。

### [>> 不善谈判](https://web.archive.org/web/20220524005626/http://dilbert.com/strip/2017-10-12)【dilbert.com】

### [>> 更糟糕的谈判](https://web.archive.org/web/20220524005626/http://dilbert.com/strip/2017-10-10)【dilbert.com】

### [>> 用营销搞定](https://web.archive.org/web/20220524005626/http://dilbert.com/strip/2017-10-07)【dilbert.com】

## 5. 本周精选

### [>> 一步步指导 Tomcat 性能监控](https://web.archive.org/web/20220524005626/https://stackify.com/tomcat-performance-monitoring/)【stackify.com】
