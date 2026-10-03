
# Java 周刊，第 347 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-weekly-347>

## 1. Spring 和 Java

[**> > 用 Spring Boot 2.3 打造高效的 Docker 镜像**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/14/creating-efficient-docker-images-with-spring-boot-2-3) [spring.io](https://spring.io)

不再有 Docker 文件：利用分层 jar 和构建包为 Spring Boot 应用程序创建高效的 Docker 镜像。

[**> > 用 Kotlin 和 Testcontainers 测试 Spring Boot 应用程序**](https://web.archive.org/web/20220626110355/https://rieckpil.de/testing-spring-boot-applications-with-kotlin-and-testcontainers/) [rieckpil.de](https://rieckpil.de)

有效地使用 Kotlin 和 Testcontainers：克服递归泛型类型定义，以及新的`@DynamicPropertySource`注解。

[**> > Spring 的轻量级 JPA/Hibernate 替代品**](https://web.archive.org/web/20220626110355/https://4comprehension.com/lightweight-jpa-hibernate-alternatives/?utm_source=feedly&utm_medium=rss&utm_campaign=lightweight-jpa-hibernate-alternatives) [4comprehension.com](https://4comprehension.com)

以及 Hibernate/JPA 的另外两个轻量级选择：Spring Data JDBC 和 JDBC Template。

#### 同样值得一读：

* [**> > Spring Boot 2.4 的配置文件处理修改**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/14/config-file-processing-in-spring-boot-2-4) [spring.io](https://spring.io)
* [**> > 使用 JPA 和 Hibernate 进行批量更新和删除**](https://web.archive.org/web/20220626110355/https://vladmihalcea.com/bulk-update-delete-jpa-hibernate/) [vladmihalcea.com](https://vladmihalcea.com)
* [**> > 使用 Resilience4j 进行时间限制**](https://web.archive.org/web/20220626110355/https://reflectoring.io/time-limiting-with-resilience4j/) [reflectoring.io](https://reflectoring.io)
* [**> > 扩展 JUnit 5**](https://web.archive.org/web/20220626110355/https://www.mscharhag.com/java/junit5-custom-extensions) [mscharhag.com](https://www.mscharhag.com)
* [**> > 微软在 Azure 服务总线**](https://web.archive.org/web/20220626110355/https://www.infoq.com/news/2020/08/jms-2-amqp-service-bus-preview/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com](https://www.infoq.com)
* [**> > 使用 Spring Boot DevTools 优化你的开发循环**](https://web.archive.org/web/20220626110355/https://reflectoring.io/spring-boot-dev-tools/) [reflectoring.io](https://reflectoring.io)
* [**> > Records 和模式匹配终于确定在 Java 16**](https://web.archive.org/web/20220626110355/https://www.infoq.com/news/2020/08/java16-records-instanceof/?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java) [infoq.com](https://www.infoq.com)
* [**> > 在 Hibernate 中建模自引用关联**](https://web.archive.org/web/20220626110355/https://thorben-janssen.com/self-referencing-associations/) [thorben-janssen.com](https://thorben-janssen.com)

**网络研讨会和演示：**

* [**> > 一个精彩的播客：RSocket everywhere 和 Maciej Walkowiak 在 Spring Cloud AWS 上**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/14/a-bootiful-podcast-rsocket-everywhere-and-maciej-walkowiak-on-spring-cloud-aws) [spring.io](https://spring.io)
* [**> > 首映：RSocket Revolution**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/13/premiering-the-rsocket-revolution) [spring.io](https://spring.io)

**升级时间：**

* [**> > Spring Boot 2.4.0-M2 现已可用**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/14/spring-boot-2-4-0-m2-is-now-available) [spring.io](https://spring.io) 和 [**> > Spring Boot 2.3.3 现已可用**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/13/spring-boot-2-3-3-available-now) [spring.io](https://spring.io)
* [**> > Spring Framework 5.3.0-M2 现已可用**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/11/spring-framework-5-3-0-m2-available-now) [spring.io](https://spring.io)
* [**> > Spring Security 5.4.0-RC1 发布**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/14/spring-security-5-4-0-rc1-released) [spring.io](https://spring.io) 和 [**> > Spring Security 5.3.4、5.2.6、5.1.12、5.0.18、4.2.18 发布**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/12/spring-security-5-3-4-5-2-6-5-1-12-5-0-18-4-2-18-released) [spring.io](https://spring.io)
* [**> > Spring Data Neumann SR3 发布**](https://web.archive.org/web/20220626110355/https://spring.io/blog/2020/08/12/spring-data-neumann-sr3-released) [spring.io](https://spring.io)

## 2. 技术

[**> > 分布式系统的模式：预写日志**](https://web.archive.org/web/20220626110355/https://martinfowler.com/articles/patterns-of-distributed-systems/wal.html) [martinfowler.com](https://martinfowler.com)

满足预写日志（WAL）模式：克服分布式系统或任何其他数据密集型系统中刷新存储数据结构时的故障。

**同样值得一读：**

* [**> > 分布式系统的模式：分段日志**](https://web.archive.org/web/20220626110355/https://martinfowler.com/articles/patterns-of-distributed-systems/log-segmentation.html) [martinfowler.com](https://martinfowler.com)
* [**> > 分布式系统的模式：法定人数**](https://web.archive.org/web/20220626110355/https://martinfowler.com/articles/patterns-of-distributed-systems/quorum.html) [martinfowler.com](https://martinfowler.com)
* [**> > 如何用服务控制策略（SCP）完全锁定 AWS 账户**](https://web.archive.org/web/20220626110355/https://advancedweb.hu/how-to-completely-lock-down-an-aws-account-with-a-service-control-policy-scp/) [advancedweb.hu](https://advancedweb.hu)
* [**> > 找到那个 bug！用搜索引擎当程序员**](https://web.archive.org/web/20220626110355/https://codewithoutrules.com/2020/08/17/search-engine-programmers/) [codewithoutrules.com](https://codewithoutrules.com)

## 3. 沉思

[**> > 日期时间陷阱**](https://web.archive.org/web/20220626110355/https://blog.frankel.ch/date-time-gotchas/) [blog.frankel.ch](https://blog.frankel.ch)

几个世纪以来日历的一些有趣变化，令人愉快的阅读：儒略历到公历、二战、1973 年石油危机等。

**同样值得一读：**

* [**> > Telltale：网飞应用监控简化**](https://web.archive.org/web/20220626110355/https://netflixtechblog.com/telltale-netflix-application-monitoring-simplified-5c08bfa780ba) [netflixtechblog.com](https://netflixtechblog.com)
* [**> > 社交媒体问题**](https://web.archive.org/web/20220626110355/https://jacquesmattheij.com/the-social-media-problem/) [jacquesmattheij.com](https://jacquesmattheij.com)

## 4. 漫画

本周我最喜欢的迪尔伯特。

* [**> > 社交媒体中毒**](https://web.archive.org/web/20220626110355/https://dilbert.com/strip/2020-08-18) [dilbert.com](https://dilbert.com)
* [**> > 乐于助人的建议**](https://web.archive.org/web/20220626110355/https://dilbert.com/strip/2020-08-12) [dilbert.com](https://dilbert.com)

## 5. 本周精选

**[> > 变得疯狂、惊人、疯狂成功的 5 个步骤……或者随便什么](https://web.archive.org/web/20220626110355/https://markmanson.net/how-to-be-insanely-successful)** [markmanson.net](https://markmanson.net)

Next **»** [Java Weekly, Issue 348](/web/20220626110355/https://www.baeldung.com/java-weekly-348) **«** Previous [Java Weekly, Issue 346](/web/20220626110355/https://www.baeldung.com/java-weekly-346)
