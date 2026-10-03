
# Java 网络周刊，第 175 期

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-web-weekly-175>

本周有很多关于 Java 9 的有趣文章。

**开始了……**

## 1. Spring 和 Java

#### [> > IBM 和红帽对 Java 模块投“不”票【竖锯】](https://web.archive.org/web/20220626074958/https://www.infoq.com/news/2017/05/no-jigsaw)【infoq.com】

Java 9 计划在 3 个月后发布，但是 Jigsaw 仍然是一个很大的争议。

有趣的是，投反对票的组织确实对 OSGi 感兴趣。

#### [**> >从战壕中跃出:用 HTTP Request Builders**](https://web.archive.org/web/20220626074958/https://www.petrikainulainen.net/programming/spring-framework/spring-from-the-trenches-cleaning-up-our-test-code-with-http-request-builders/)【petrikainulainen.net】清理我们的测试代码

使用 HTTP 请求构建允许我们在编写 Spring MVC 测试时避免重复。

#### [> > Java 服务加载器 vs Spring 工厂加载器](https://web.archive.org/web/20220626074958/https://blog.frankel.ch/java-service-loader-vs-spring-factories/#gsc.tab=0) [ frankel.ch ]

我们不需要额外的库来受益于 Java 中的 IoC 我们可以简单地使用`ServiceLoader`类。它也可以很容易地与 Spring 集成。

#### [> >豆验证 2.0 公审](https://web.archive.org/web/20220626074958/http://beanvalidation.org/news/2017/04/26/bean-validation-2-0-up-for-public-review/)【beanvalidation.org】

新的 Bean 验证 JSR 可供审查，所以如果你想产生影响，这是你的机会。

#### [> > Java 9 资源——演讲、文章、博客、书籍和课程](https://web.archive.org/web/20220626074958/http://blog.codefx.org/java/java-9-resources-talks-articles-blogs-books-courses/)【codefx.org】

Java 9 应该很快就会发布，所以是时候熟悉新工具了。

#### [> >终极指南——与 JPA 和 Hibernate 的关联映射](https://web.archive.org/web/20220626074958/http://www.thoughts-on-java.org/ultimate-guide-association-mappings-jpa-hibernate/)【thoughts-on-java.org】

Hibernate 关联映射实用综合指南。

#### [> >如何用 Hibernate 5](https://web.archive.org/web/20220626074958/https://vladmihalcea.com/2017/05/02/how-to-get-access-to-database-table-metadata-with-hibernate-5/)【vladmihalcea.com】获取数据库表元数据

事实证明，Hibernate 也可以用于访问数据库元数据。

#### 同样值得一读:

*   #### [> >爪哇收藏视图](https://web.archive.org/web/20220626074958/http://blog.vavr.io/java-collection-views/) vavr。io

*   #### [> > Lessons in Abstraction: What can FP teach OOP](https://web.archive.org/web/20220626074958/https://www.sitepoint.com/oop-learn-about-abstraction-from-fp/) [sitepoint.com]

*   #### [> >斯博克测试框架 vs JUnit](https://web.archive.org/web/20220626074958/http://blog.codepipes.com/testing/spock-vs-junit.html)【codepipes.comT4

*   #### [>同和棱角分明的](https://web.archive.org/web/20220626074958/https://developer.okta.com/blog/2017/04/26/bootiful-development-with-spring-boot-and-angular)【developer . okta . com】

**网络研讨会和演示:**

*   #### [> > High performance management language](https://web.archive.org/web/20220626074958/https://www.infoq.com/presentations/performance-managed-languages) [infoq.com]

*   #### [> >爪哇中的性能测试](https://web.archive.org/web/20220626074958/https://www.infoq.com/presentations/java-performance-testing?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq . com】T5

*   #### [>>Scala Days 2017——杰普森主题演讲](https://web.archive.org/web/20220626074958/https://aphyr.com/posts/343-scala-days-2017-jepsen-keynote)【【aphyr.com】T4

**升级时间:**

*   #### [>春季会议 1.3.1 发布](https://web.archive.org/web/20220626074958/https://spring.io/blog/2017/04/27/spring-session-1-3-1-released) 春天。io

*   #### [> >春天为阿帕奇卡夫卡 2.0 里程碑一可用](https://web.archive.org/web/20220626074958/https://spring.io/blog/2017/04/27/spring-for-apache-kafka-2-0-milestone-1-available) 春天。io

*   #### [>>IntelliJ IDEA 2017。1 .3 经济活跃人口开放](https://web.archive.org/web/20220626074958/https://blog.jetbrains.com/idea/2017/04/intellij-idea-2017-1-3-eap-is-open/)【jetbrains . com】T5

*   #### [> >春娥平台布鲁塞尔——SR2](https://web.archive.org/web/20220626074958/https://spring.io/blog/2017/04/28/spring-io-platform-brussels-sr2)T3春天。IO

*   #### [> >春娥平台雅典](https://web.archive.org/web/20220626074958/https://spring.io/blog/2017/04/28/spring-io-platform-athens-sr5)——SR5春。IO

*   #### [> >阿苏系统基于 LLVM](https://web.archive.org/web/20220626074958/https://www.infoq.com/news/2017/05/azul-falcon)【infoq . com】推出新的 Java 语言(一种计算机语言，尤用于创建网站)实时编译器猎鹰

*   #### [>莫克托 2.8.24 出局](https://web.archive.org/web/20220626074958/https://github.com/mockito/mockito/blob/release/2.x/doc/release-notes/official.md#2824-2017-05-01)【github . com】T5

## 2. 技术

#### [> >简单的查询字符串，它呢？](https://web.archive.org/web/20220626074958/http://in.relation.to/2017/04/27/simple-query-string-what-about-it/)

原来 Lucene 的`SimpleQueryParser` 现在暴露在更高级别的 Hibernate DSL 中——非常酷。

#### [> >【红色代码】](https://web.archive.org/web/20220626074958/https://henrikwarne.com/2017/04/28/code-rot/) 【亨利 kwarne . com】

**代码随时间退化**是一个自然而普遍的问题。为了避免进一步的代码污染和衰退，尽早识别和修复这种情况是很重要的。

**[> >让你的测试自动化与你对话](https://web.archive.org/web/20220626074958/http://www.ontestautomation.com/let-your-test-automation-talk-to-you/)**【ontestautomation.com】

干净代码原则是普遍适用的——测试自动化也不例外🙂

**同样值得一读:**

*   #### [>了解何时使用兔子 q 或阿帕奇](https://web.archive.org/web/20220626074958/https://content.pivotal.io/blog/understanding-when-to-use-rabbitmq-or-apache-kafka)卡夫卡内容。枢轴。io

*   #### [> > Product route (also known as "road map")](https://web.archive.org/web/20220626074958/https://blog.codecentric.de/en/2017/04/product_routes/) codecentric.de

*   #### [> > Output of a truly random process](https://web.archive.org/web/20220626074958/https://horicky.blogspot.com/2017/04/an-output-of-truly-random-process.html) [horicky.blogspot.com]

## 3. 沉思

#### [> >开发者霸权:软件开发者应该运行软件开发的疯狂想法](https://web.archive.org/web/20220626074958/http://www.daedtech.com/developer-hegemony-the-crazy-idea-that-software-developers-should-run-software-development/)【daedtech.com】

《开发者霸权》——这本书也是本周的“精选”。

我刚刚开始读它，它是我知道我最终会读完的少数几本非音频书籍之一。

#### [> >软件手艺好生意好](https://web.archive.org/web/20220626074958/http://www.daedtech.com/software-craftsmanship-is-good-business/)【daedtech.com】

收益递减法则也适用于原始开发技能。从某种意义上来说，比起编写复杂的汇编代码，更关注能给客户带来更多利润的良好实践更有意义。

#### [> >成为一名通晓多种语言的程序员](https://web.archive.org/web/20220626074958/https://www.infoq.com/news/2017/05/being-polyglot-programmer?utm_campaign=infoq_content&utm_source=infoq&utm_medium=feed&utm_term=Java)【infoq.com】

成为一名通晓多种语言的程序员并不是要掌握多种工具，而是要**运用文艺复兴式的方法来拓宽你的视野**——最终提高你的技能。

#### 同样值得一读:

*   #### [>采访德克 龙博](https://web.archive.org/web/20220626074958/http://blog.code-cop.org/2017/04/interview-dirk-rombauts.html)【【code-cop.org】T4

*   #### [**> > Next part: Postscript introduction**](https://web.archive.org/web/20220626074958/http://www.daedtech.com/whats-next-epilogue-of-a-book-launch/) [daedtech.com]

*   [**> >更快、更高、更强:产业数字化如何重新定义价值创造**](https://web.archive.org/web/20220626074958/http://www.allthingsdistributed.com/2017/05/industry-digitalization-value-creation.html)【allthingsdistributed.com】

## 4. 漫画

本周我最喜欢的迪尔伯特。

#### [> >直说吧](https://web.archive.org/web/20220626074958/http://dilbert.com/strip/2012-08-18)【dilbert.com】

#### [> >销售工作的一半](https://web.archive.org/web/20220626074958/http://dilbert.com/strip/2012-08-13)【dilbert.com】

#### 我可以给你倒杯水吗？【dilbert.com】

## 5. 本周精选

埃里克的书终于在本周出版了。如果你对我们的行业、行业的运行方式以及未来十年的发展方向感兴趣，请不要错过这个:

#### [> >埃里克·迪特里希的开发者霸权](https://web.archive.org/web/20220626074958/http://www.daedtech.com/book/)【daedtech.com】
