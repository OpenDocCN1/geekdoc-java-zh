
# Java 周刊，第 191 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-191>

本周有很多关于 Java 9 的有趣文章。

**开始了……**

## 1. Spring 和 Java

#### [**>>甲骨文欲将 Java EE 移至开源基础**](https://web.archive.org/web/20220524025600/https://www.infoq.com/news/2017/08/oracle-open-sourcing-javaee?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq.com】

Java EE 团队正在考虑转向开源的第三方基金会。

我认为这将是向前迈进的一大步，我希望事情真的会这样发展🙂

#### [**>>Java 9 孵化器模块将如何改变 Java 的未来**](https://web.archive.org/web/20220524025600/http://blog.takipi.com/how-java-9-incubator-modules-will-change-the-future-of-java/)【takipi.com】

孵化器模块将是 JPMS 的一个有趣的特征——它们将允许未完成的或实验性的 API 的安全引入。

#### [**>>Spring Boot 2.0 中引入执行器端点**](https://web.archive.org/web/20220524025600/https://spring.io/blog/2017/08/22/introducing-actuator-endpoints-in-spring-boot-2-0)【spring.io】

Spring Boot 2.0 为执行器带来了许多重要的（也很酷的）**变化**，同时支持 Spring MVC、Spring WebFlux 和 Jersey。

#### [**>>Vavr、Collections 和 Java Stream API Collectors**](https://web.archive.org/web/20220524025600/http://4comprehension.com/vavr-collections-and-java-stream-api-collectors/)【4comprehension.com】

原来**流 API 收集器可以很容易地与 Vavr**（以前的 Javaslang）集合一起使用，甚至可以与像`Option`或`Try`这样的工具一起使用。

#### [**>>快进 Vavr 1.0**](https://web.archive.org/web/20220524025600/http://blog.vavr.io/fast-forward-to-vavr-1-0/)【blog.vavr.io】

更名后的 Javaslang 即将推出新名称下的第一个完整版本——这将包括许多变化，如将主要工件分割成较小的工件，以及 Java 互操作性的改进。

#### [**>>JVM 语言的兴衰**](https://web.archive.org/web/20220524025600/https://blog.frankel.ch/rise-fall-jvm-languages/#gsc.tab=0)【frankel.ch】

我总是觉得观察我们生态系统的高级状态很有趣。

我在这里要注意的是，我也希望在那里看到 Clojure。

#### 同样值得一读：

* #### [**>>Spring Boot 休息 API 错误处理指南**](https://web.archive.org/web/20220524025600/https://www.toptal.com/java/spring-boot-rest-api-error-handling)【toptal.com】
* #### [**>>Dormancy Tip: How to map the association to the map**](https://web.archive.org/web/20220524025600/https://www.thoughts-on-java.org/hibernate-tips-map-association-map/)【thoughts-on-java.org】
* #### [**>>使用冬眠对实现审计日志的最佳方式**](https://web.archive.org/web/20220524025600/https://vladmihalcea.com/2017/08/22/the-best-way-to-implement-an-audit-log-using-hibernate-envers/)【vladmihalcea.com】
* #### [**>>取消可完成未来**](https://web.archive.org/web/20220524025600/http://blog.tremblay.pro/2017/08/supply-async.html)【blog.tremblay.pro】
* #### [**>>如何在放心中有效使用 Groovy GPath 第三部分：GPath XML**](https://web.archive.org/web/20220524025600/http://james-willett.com/2017/08/rest-assured-gpath-xml/)【james-willett.com】

**网络研讨会和演示：**

* #### [**>>迁移加速到 Java 9**](https://web.archive.org/web/20220524025600/https://www.infoq.com/presentations/speedment-java9)【infoq.com】

**升级时间：**

* #### [**>>Hibernation ORM 5.1.10. Finally released**](https://web.archive.org/web/20220524025600/http://in.relation.to/2017/08/18/hibernate-orm-5110-final-release/)
* #### [**>>休眠验证器 6.0.2.最终发布**](https://web.archive.org/web/20220524025600/http://in.relation.to/2017/08/22/hibernate-validator-602-final-out/)
* #### [**>>Hibernation search 5.8.0 是第一个候选版本！**](https://web.archive.org/web/20220524025600/http://in.relation.to/2017/08/16/hibernate-search-5-8-0-CR1/)
* #### [**>>IntelliJ IDEA 2017.2.3 RC 出**](https://web.archive.org/web/20220524025600/https://blog.jetbrains.com/idea/2017/08/intellij-idea-2017-2-3-rc-is-out/)【blog.jetbrains.com】
* #### [**>>Chunyun Dalston SR3 现已上市**](https://web.archive.org/web/20220524025600/https://spring.io/blog/2017/08/21/spring-cloud-dalston-sr3-is-now-available)【spring.io】
* #### [**>>IntelliJ IDEA 2017.2.2：科特林 1.1.4，性能更好更有**](https://web.archive.org/web/20220524025600/https://blog.jetbrains.com/idea/2017/08/intellij-idea-2017-2-2-kotlin-1-1-4-better-performance-and-more/)【blog.jetbrains.com】

## 2. 技术

#### [**>>利用数据库的力量‘解绑’**](https://web.archive.org/web/20220524025600/https://www.confluent.io/blog/leveraging-power-database-unbundled/)【confluent.io】

“拆分”数据库使得在多个服务之间共享数据库成为可能，而不会导致不必要的耦合。

#### [**>>代码气味：深度嵌套代码**](https://web.archive.org/web/20220524025600/https://blog.jetbrains.com/idea/2017/08/code-smells-deeply-nested-code/)【jetbrains.com】

重构包含多个嵌套的`for`和`if`语句的**代码**的一个很酷的案例研究。

**同样值得一读：**

* #### [**>>拔键值商店**](https://web.archive.org/web/20220524025600/https://techblog.bozho.net/stubbing-key-value-stores/)【techblog.bozho.net】
* #### [**>>不是所有重要的事情都是你的核心业务**](https://web.archive.org/web/20220524025600/https://blog.codecentric.de/en/2017/08/not-everything-vital-also-core-business/)【codecentric.de】
* #### [**>>API 作为基础设施：未来证明带版本控制**](https://web.archive.org/web/20220524025600/https://stripe.com/blog/api-versioning)【stripe.com】
* #### [**>>Git：创建自我审查和合并请求的指南**](https://web.archive.org/web/20220524025600/https://advancedweb.hu/2017/08/22/git-commit/)【advancedweb.hu】
* #### [**>>中步骤间共享状态使用 Guice**](https://web.archive.org/web/20220524025600/http://www.thinkcode.se/blog/2017/08/16/sharing-state-between-steps-in-cucumberjvm-using-guice)【thinkcode.se】

## 3. 沉思

#### [**>>透视微服务的架构适配度**](https://web.archive.org/web/20220524025600/https://www.infoq.com/articles/Microservices-Architectural-Fitness)【infoq.com】

微服务**不是普遍适用的架构**的配方。

像其他任何事情一样——当有具体问题需要解决时，它们需要被应用。

#### [**>>你大概误会 TDD**](https://web.archive.org/web/20220524025600/https://www.daedtech.com/probably-misunderstanding-tdd/)【daedtech.com】

关于 TDD 有很多误解，这里有一些最有趣的误解。

**同样值得一读：**

* #### [**>>护栏，而不是监狱栏杆**](https://web.archive.org/web/20220524025600/http://blog.thecodewhisperer.com/permalink/guard-rails-not-prison-bars)【thecodewhisperer.com】
* #### [**>>代码规则要被打破吗？**](https://web.archive.org/web/20220524025600/https://www.daedtech.com/code-rules-meant-broken/)【daedtech.com】

## 4. 漫画

本周我最喜欢的迪尔伯特。

#### [**>>强烈反对**](https://web.archive.org/web/20220524025600/http://dilbert.com/strip/2011-08-04)【dilbert.com】

#### [**>>注意广度**](https://web.archive.org/web/20220524025600/http://dilbert.com/strip/2011-09-21)【dilbert.com】

#### [**>>伦理**](https://web.archive.org/web/20220524025600/http://dilbert.com/strip/2012-09-14)【dilbert.com】

## 5. 本周精选

本周，我终于宣布了即将在《我的休息与春天》课程中推出的新内容——都与 Spring 5 有关（以及即将到来的价格变化）：

#### [**>>`REST With Spring`**](/web/20220524025600/https://www.baeldung.com/rest-with-spring-course#master-class)即将推出新模块
