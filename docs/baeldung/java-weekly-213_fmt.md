
# Java 周刊，第 213 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-213>

**开始了……**

## 1. Spring 和 Java

### [熏蒸思想终极代码利用数据流分析](https://web.archive.org/web/20221208143837/https://blog.jetbrains.com/idea/2018/01/fumigating-the-idea-ultimate-code-using-dataflow-analysis/)【blog.jetbrains.com】

深入探究 IntelliJ 中的代码检查是如何工作的。

### [不可修改对不可修改 10](https://web.archive.org/web/20221208143837/https://marxsoftware.blogspot.com/2018/01/schopenhauers-law-immutability.html)【marxsoftware.blogspot.com】

需要理解的一个重要概念是——**不可修改的集合不一定是不可修改的**。

简单地说，如果包含的元素是可变的，那么整个集合显然是可变的，即使集合本身可能是不可修改的。

### [在 Servlet API 中提炼重定向语义](https://web.archive.org/web/20221208143837/https://blog.frankel.ch/refining-redirect-semantics-servlet-api/#gsc.tab=0)【blog.frankel.ch】

不幸的是，`HttpServletResponse.sendRedirect()` 返回 HTTP 302 而不是 303，所以如果我们需要实现 Post/Redirect/Get 模式，我们可能需要手动处理它。

### 同样值得一读

- [IntelliJ 理念启动 2018.1 早期接入计划](https://web.archive.org/web/20221208143837/https://blog.jetbrains.com/idea/2018/01/intellij-idea-starts-2018-1-early-access-program/)【blog.jetbrains.com】
- [甲骨文和 Java 语言上的 EE 博客](https://web.archive.org/web/20221208143837/https://blog.sourced-bvba.be//article/2018/01/18/on-oracle-and-java-ee/)【sourced-bvba.be】
- [Spring Boot 2：从下拉向导度量迁移到微米](https://web.archive.org/web/20221208143837/http://www.nurkiewicz.com/2018/01/spring-boot-2-migrating-from-dropwizard.html)【nurkiewicz.com】
- [Cotrim's 2017 Review and 2018 Outlook](https://web.archive.org/web/20221208143837/https://www.infoq.com/news/2018/01/Kotlin1718)【infoq.com】
- [EE4J code begins its open source journey](https://web.archive.org/web/20221208143837/https://www.infoq.com/news/2018/01/EE4JCodeArrives)【infoq.com】
- [更快的数组排序原语来到 Java？](https://web.archive.org/web/20221208143837/https://marxsoftware.blogspot.com/2018/01/faster-dual-pivot-quicksort.html)【Marx software.blogspot.com】
- [Five Tips of High Performance Thread-Safe Java from Concurrent Hashmap](https://web.archive.org/web/20221208143837/http://vmlens.com/articles/5_tips_from_concurrent_hashmap/)【vmlens.com】

### 网络研讨会和演示

- [How to use the open service proxy API](https://web.archive.org/web/20221208143837/https://www.infoq.com/presentations/pivotal-service-broker-api?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq.com】 to build the Spring service for the cloud native platform
- [CredHub 和安全凭证管理](https://web.archive.org/web/20221208143837/https://www.infoq.com/presentations/credhub?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq.com】
- [Cloud Foundry networking: enabling microservices to communicate directly](https://web.archive.org/web/20221208143837/https://www.infoq.com/presentations/pcf-networking-microservices)【infoq.com】
- [PKS：企业级 Kubernetes](https://web.archive.org/web/20221208143837/https://www.infoq.com/presentations/pks-kubernetes)【infoq.com】
- `"t0", "t1", "T2", "T7", "t8"` and Cotrim's `"T3"` fresh asynchronous `"T3"` `"infoq.com's"` `"T4", "T5", "T6"`

### 升级时间

- [春天框架 5.0.3 和 4.3.14 现在可用](https://web.archive.org/web/20221208143837/https://spring.io/blog/2018/01/23/spring-framework-5-0-3-and-4-3-14-available-now)【spring.io】
- [春云队长 1.0 RC1 发布](https://web.archive.org/web/20221208143837/https://spring.io/blog/2018/01/19/spring-cloud-skipper-1-0-rc1-released)【spring.io】
- [冬眠 ORM 5.3.0.beta1 发布](https://web.archive.org/web/20221208143837/http://in.relation.to/2018/01/18/hibernate-orm-530-beta1-release/)【in.relation.to】
- [FlexyPool 2 已经发布](https://web.archive.org/web/20221208143837/https://vladmihalcea.com/flexypool-2-released/)
- [Spring data released by ingels SR10 and Kai SR3](https://web.archive.org/web/20221208143837/https://spring.io/blog/2018/01/24/spring-data-ingalls-sr10-and-kay-sr3-released)【spring.io】
- [冬眠搜索 5.9.0 刚刚发布](https://web.archive.org/web/20221208143837/http://in.relation.to/2018/01/24/hibernate-search-5-9-0-CR1/)【in.relation.to】

## 2. 技术与思考

### [一场假想的咨询演出](https://web.archive.org/web/20221208143837/https://www.daedtech.com/hypothetical-consulting-gig/)【daedtech.com】

这是一份普通的咨询工作的样子🙂

### 同样值得一读

- [Don't be fooled by 100% code coverage](https://web.archive.org/web/20221208143837/http://ordepdev.me/posts/code-coverage)【ordepev.me】
- [That should be a microservice, right? Keep these six factors in mind](https://web.archive.org/web/20221208143837/https://content.pivotal.io/blog/should-that-be-a-microservice-keep-these-six-factors-in-mind)【content.pivotal.io】
- [Why should every software developer become a consultant](https://web.archive.org/web/20221208143837/https://www.daedtech.com/software-developer-consultant/)【daedtech.com】
- [When you have a blockchain, everything looks like a nail](https://web.archive.org/web/20221208143837/https://techblog.bozho.net/blockchain-everything-looks-like-nail/)【techblog.bozho.net】
- [国籍论证](https://web.archive.org/web/20221208143837/http://blog.cleancoder.com/uncle-bob/2018/01/18/TheCitizenshipArgument.html)【blog.cleancoder.com】

## 3. 漫画

本周我最喜欢的迪尔伯特。

### [荒谬绝对](https://web.archive.org/web/20221208143837/http://dilbert.com/strip/2018-01-25)【dilbert.com】

### [数据封装](https://web.archive.org/web/20221208143837/http://dilbert.com/strip/2018-01-18)【dilbert.com】

### [无法预料的问题](https://web.archive.org/web/20221208143837/http://dilbert.com/strip/2018-01-22)【dilbert.com】

## 5. 本周精选

### [JavaScript 框架的残酷生命周期](https://web.archive.org/web/20221208143837/https://stackoverflow.blog/2018/01/11/brutal-lifecycle-javascript-frameworks/)【stackoverflow.blog】
