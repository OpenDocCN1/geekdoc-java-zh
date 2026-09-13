
# Hibernate 教程

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/tutorials/hibernate-tutorials/>

![Hibernate tutorials](img/c18eeb0e982a211a0af761f2bd03a156.png "Hibernate tutorials")

[Hibernate](http://web.archive.org/web/20210509043846/https://www.hibernate.org/)，由 Gavin King 创造，被称为 Java 开发者最好的、占主导地位的对象/关系持久化（ORM）工具（现在是 support。网）。它提供了许多优雅和创新的方法来简化 Java 中的关系数据库处理任务。

Hibernate 在很多方面都很棒，但它需要被恰当地使用。在本教程中，它提供了许多使用 Hibernate3 的逐步示例和解释。

页（page 的缩写）的教程更新到 Hibernate v3.6.1.Final。

## 休眠快速启动

Hello World 示例来体验 Hibernate 框架。

- [Maven 2+Hibernate 3.2.3+MySQL 5.0 示例（XML 映射）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/quick-start-maven-hibernate-mysql-example/)

  MySQL 数据库中 Hibernate 3.2.3 示例，带有经典的 hbm 映射。

- [Maven 2+Hibernate 3.2.3+MySQL 5.0 示例（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/maven-hibernate-annonation-mysql-example/)

  MySQL 数据库中 Hibernate 3.2.3 示例，带 Hibernate/JPA 注释。

- [Maven 3+Hibernate 3.6.3+Oracle 11g 示例（XML 映射）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/maven-3-hibernate-3-6-oracle-11g-example-xml-mapping/)

  Oracle 数据库中的 Hibernate 3.6 示例，带有经典的 hbm 映射。

- [Maven 3+Hibernate 3.6.3+Oracle 11g 示例（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/maven-3-hibernate-3-6-oracle-11g-example-annotation/)

  Oracle 数据库中的 Hibernate 3.6 示例，带 Hibernate/JPA 注释。

## 休眠关联（表关系）

Hibernate 中如何定义一对一、一对多、多对多的表关系？

- [一对一示例（XML 映射）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-one-to-one-relationship-example/)

  Hibernate 一对一示例与 hbm 映射文件。

- [一对一示例（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-one-to-one-relationship-example-annotation/)

  Hibernate 一对一示例带注释代码。

- [一对多示例（XML 映射）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-one-to-many-relationship-example/)

  Hibernate 一对多示例与 hbm 映射文件。

- [一对多示例（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-one-to-many-relationship-example-annotation/)

  Hibernate 一对多示例带注释代码。

- [多对多示例（XML 映射）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-many-to-many-relationship-example/)

  Hibernate 多对多示例（连接表中没有额外的列）带有 hbm 映射文件。

- [多对多示例（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-many-to-many-relationship-example-annotation/)

  Hibernate 多对多示例（连接表中没有额外的列）带有注释代码。

- [多对多示例–连接表+额外列（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-many-to-many-example-join-table-extra-column-annotation/)

  Hibernate 多对多示例（连接表中有额外列）带注释代码。

- [题外话：理解逆键工作，举例及解释](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/inverse-true-example-and-explanation/)

  “逆”是 Hibernate 中最令人困惑的关键词，但你必须清楚地理解这一点，才能微调你的关系表现。

## Hibernate/JBoss 工具+Eclipse IDE

学习如何使用 Hibernate 工具是必须的！

- [在 Eclipse IDE 中安装 Hibernate/JBoss 工具](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-install-hibernate-tools-in-eclipse-ide/)

  在你的 Eclipse IDE 中安装 Hibernate。

- [生成 Hibernate 映射文件&注释用 Hibernate 工具](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-generate-code-with-hibernate-tools/)

  自动为你生成 Hibernate 代码。

## 休眠日志记录

如何在 Hibernate 中进行日志记录。

- [在 Hibernate 中配置日志记录–SLF4j+Log4j](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-configure-log4j-in-hibernate-project/)

  将 SLF4j+Log4j 与 Hibernate 集成。

- [在 Hibernate 中配置日志记录–Logback](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-configure-logging-in-hibernate-logback/)

  集成 Logback 和 Hibernate。

## 休眠连接池

如何在 Hibernate 中配置数据库连接池。

- [在 Hibernate 中配置 C3P0 连接池](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-configure-the-c3p0-connection-pool-in-hibernate/)

  将 C3P0 与 Hibernate 集成。

- [在 Hibernate 中配置 DBCP 连接池](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-configure-dbcp-connection-pool-in-hibernate/)

  集成 Apache DBCP 和 Hibernate。

## 休眠级联

Hibernate cascade 用于自动管理对方的状态。

- [级联示例（保存、更新、删除和删除-孤儿）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-cascade-example-save-update-delete-and-delete-orphan/)

  级联示例中的保存、更新、删除和删除孤儿。以及删除和删除孤儿之间的区别。

- [级联和逆之间的不同](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/different-between-cascade-and-inverse/)

  许多 Hibernate 开发者对级联和逆之间的不同感到困惑，下面是解释。

- [Cascade–JPA&Hibernate 注释常见错误](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/cascade-jpa-hibernate-annotation-common-mistake/)

  初学者或有经验的 Hibernate 开发者犯的一个超级容易的常见注释错误——Hibernate 中的 JPA cascade 注释？

## Hibernate 查询语言（HQL）

Hibernate 自己的数据操作语言，它很类似于数据库 SQL 语言。

- [Hibernate 查询示例（HQL）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-query-examples-hql/)

  HQL CRUD 示例，选择、更新、删除和批量插入（不支持单次插入）。

- [Hibernate 参数绑定示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-parameter-binding-examples/)

  用“命名参数”和“位置参数”的方法将参数绑定到 HQL。

- [如何在 Hibernate 查询中嵌入 Oracle 提示](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-embed-oracle-hints-in-hibernate-query/)

  一种在 Hibernate 查询中嵌入 Oracle 提示以提高 Oracle 查询性能的技巧。

## 休眠标准

Hibernate Criteria API 是 Hibernate 查询语言（HQL）的替代产品。在许多可选的搜索标准中，这总是一个好的解决方案。

- [Hibernate 条件示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-criteria-examples/)

  条件示例——基本查询、排序查询、限制查询和结果分页。

## 休眠本机 SQL

在某些场景中，Hibernate HQL 或 Criteria 仅仅是不够的，在这里你可以直接使用原生数据库 SQL 语言。

- [Hibernate 原生 SQL 查询示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-native-sql-queries-examples/)

  一个展示如何在 Hibernate 中使用原生 SQL 的指南。

## Hibernate 命名查询

出于可维护性的目的，命名查询允许开发人员将 HQL 放入 XML 映射文件或注释中，您只是不希望所有的 HQL 语法分散在 Java 代码中。🙂

- [Hibernate 命名查询示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-named-query-examples/)

  在 XML 文件和注释中处理命名查询。

## 休眠事务

所有与 Hibernate 事务相关的事情。

- [Hibernate 事务处理示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-transaction-handle-example/)

  一个使用 Hibernate 事务的简单标准示例。

## 冬眠高级技术

一些 Hibernate 高级技术，很少使用但是实用的技巧（数据过滤器和拦截器）。

- [Hibernate 数据过滤器示例–XML 和注释](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-data-filter-example-xml-and-annotation/)

  Hibernate 数据过滤器用于过滤从数据库中检索的数据，下面是使用 XML 或注释中的数据过滤器的指南。

- [Hibernate interceptor 示例–审计日志](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-interceptor-example-audit-log/)

  Hibernate interceptor 用于拦截 CRUD 操作等 Hibernate 事件，这是使用 Hibernate interceptor 实现审计日志的详细示例。

## 休眠性能

一些调整会让你的 Hibernate 运行得更快🙂

- [动态插入属性示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-dynamic-insert-attribute-example/)

  使用动态插入来避免在 SQL INSERT 语句中包含未修改的属性。

- [动态更新属性示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-dynamic-update-attribute-example/)

  使用动态插入来避免在 SQL UPDATE 语句中包含未修改的属性。

- [Hibernate mutable 示例（类和集合）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-mutable-example-class-and-collection/)

  使用 mutable 关键字避免生成不必要的 SQL 语句。

- [Hibernate–抓取策略示例](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-fetching-strategies-examples/)

  Hibernate 抓取策略用于优化 Hibernate 生成的 select 语句，这是任何 Hibernate 开发人员必须学习的技能。

- [session.get()和 session.load()]

  理解什么时候应该使用 get 或 load 来检索对象以免对数据库造成不必要的冲击。

## 将 Hibernate 与其他框架集成

Hibernate 与其他框架集成的例子。



- [Struts + Hibernate 集成](http://web.archive.org/web/20210509043846/http://www.mkyong.com/struts/struts-hibernate-integration-example/)
  
  用 Struts 框架集成 Hibernate 的例子。

- [Struts + Spring + Hibernate 集成](http://web.archive.org/web/20210509043846/http://www.mkyong.com/struts/struts-spring-hibernate-integration-example/)
  
  将 Hibernate 与 Struts 和 Spring 框架集成在一起的例子。

- [Spring + Hibernate 集成](http://web.archive.org/web/20210509043846/http://www.mkyong.com/spring/maven-spring-hibernate-mysql-example/)
  
  用 Spring 框架集成 Hibernate 的例子。

- [Spring + Hibernate 集成（注释）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/spring/maven-spring-hibernate-annotation-mysql-example/)
  
  用 Spring 框架集成 Hibernate 的例子（注释版）。

## 休眠常见问题

一些常见的回答问题：

- [如何从不同目录加载 `hibernate.cfg.xml`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-load-hibernate-cfg-xml-from-different-directory/)
  
  默认情况下，Hibernate 在项目类路径下查看 `hibernate.cfg.xml`，下面是从指定文件夹加载的指南。

- [如何以编程方式添加 Hibernate XML 映射文件（`hbm.xml`）](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-add-hibernate-xml-mapping-file-hbm-xml-programmatically/)
  
  以编程方式加载 `hibernate.cfg.xml` 的技巧。

- [Hibernate 数据库方言列表](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-dialect-collection/)
  
  不同类型数据库厂商的方言集合列表。

- [`show_sql`、`format_sql` 和 `use_sql_comments`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-display-generated-sql-to-console-show_sql-format_sql-and-use_sql_comments/)
  
  配置 Hibernate 将生成的 SQL 语句显示到控制台。

- [如何显示 Hibernate SQL 参数值——P6Spy](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-display-hibernate-sql-parameter-values-solution/)
  
  使用 P6Sqpy 第三方库显示 Hibernate SQL 参数值。

- [如何显示 Hibernate SQL 参数值——Log4j](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-display-hibernate-sql-parameter-values-log4j/)
  
  使用 Log4j 显示 Hibernate SQL 参数值。

- 如何在 Hibernate 中调用存储过程
  
  不建议将业务逻辑放入存储过程，没关系，在 Hibernate 中仍然允许调用存储过程。

- [如何在 Hibernate 中使用 database reserved 关键字](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/how-to-use-database-reserved-keyword-in-hibernate/)
  
  在一些特殊情况下，你可能需要在你的 Hibernate 类中使用 database 关键字（不推荐），这里有一个技巧来实现它。

- 如何将图像保存到数据库
  
  这是一个演示如何使用 Hibernate 将图像保存到数据库的教程。

## 休眠常见错误

以下是 Hibernate 开发中常见错误消息的列表。

- [如果列名为关键字，如 DESC，则无法插入](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-unable-to-insert-if-column-named-is-keyword-such-as-desc/)

- [休眠——找不到 C3P0ConnectionProvider](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-could-not-find-c3p0connectionprovider/)

- [Hibernate——不推荐使用类型注释配置](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-the-type-annotationconfiguration-is-deprecated/)

- [`java.lang.ClassNotFoundException: javassist.util.proxy.MethodFilter`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/java-lang-classnotfoundexception-javassist-util-proxy-methodfilter/)

- [记住序数参数是从 1 开始的！——HibernateTemplate](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/remember-that-ordinal-parameters-are-1-based-hibernatetemplate/)

- [`org.hibernate.AnnotationException: Unknown Id.generator`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/org-hibernate-annotationexception-unknown-id-generator/)

- [需要一个 `AnnotationConfiguration` 实例来使用](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-an-annotationconfiguration-instance-is-required-to-use/)

- [`java.lang.NoClassDefFoundError: org/dom4j/DocumentException`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-initial-sessionfactory-creation-failed-java-lang-noclassdeffounderror-orgdom4jdocumentexception/)

- [`java.lang.NoClassDefFoundError: org/apache/commons/logging/LogFactory`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-initial-sessionfactory-creation-failed-java-lang-noclassdeffounderror-orgapachecommonslogginglogfactory/)

- [`java.lang.NoClassDefFoundError: org/apache/commons/collections/SequencedHashMap`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-initial-sessionfactory-creation-failed-java-lang-noclassdeffounderror-orgapachecommonscollectionssequencedhashmap/)

- [`java.lang.NoClassDefFoundError: net/sf/cglib/proxy/CallbackFilter`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-initial-sessionfactory-creation-failed-java-lang-noclassdeffounderror-netsfcglibproxycallbackfilter/)

- [`java.lang.NoClassForFounderOr: com/mchange/v2/c3p0/DataSources`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-errorinitial-sessionfactory-creation-failed-java-lang-noclassdeffounderror-commchangev2c3p0datasources/)

- [`java.lang.NoClassDefFoundError: org/hibernate/annotations/common/reflection/ReflectionManager`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-initial-sessionfactory-creation-failed-java-lang-noclassdeffounderror-orghibernateannotationscommonreflectionreflectionmanager/)

- [`java.lang.NoClassDefFoundError: antlr/ANTLRException`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-exception-in-thread-main-java-lang-noclassdeffounderror-antlrantlrexception/)

- [`java.lang.NoClassDefFoundError: javax/transaction/Synchronization`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/hibernate-error-java-lang-noclassdeffounderror-javaxtransactionsynchronization/)

- [`java.lang.ClassFormatError: 类文件中非本机或抽象的方法中缺少代码属性…`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/java-lang-classformaterror-absent-code-attribute-in-method-that-is-not-native-or-abstract-in-class-file/)

- [`java.lang.NoSuchMethodError: org.objectweb.asm.ClassWriter`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/java-lang-nosuchmethoderror-org-objectweb-asm-classwriter/)

- [`java.lang.ClassNotFoundException: javax.persistence.Entity`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/java-lang-classnotfoundexception-javax-persistence-entity/)

- [`java.lang.ClassNotFoundException: javax.transaction.TransactionManager`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/java-lang-classnotfoundexception-javax-transaction-transactionmanager/)

- [`java.lang.ClassFormatError: 类文件中非本机或抽象的方法中缺少代码属性…`](http://web.archive.org/web/20210509043846/http://www.mkyong.com/hibernate/java-lang-classformaterror-absent-code-attribute-in-method-that-is-not-native-or-abstract-in-class-file/)

## 跑题了

- 为什么我的项目选择 Hibernate 框架？
  
  我喜欢在未来项目中实现 Hibernate 的原因。

## 休眠引用

- [Hibernate 官方文档](http://web.archive.org/web/20210509043846/http://docs.jboss.org/hibernate/stable/core/reference/en/html/)

- [Hibernate Wiki](http://web.archive.org/web/20210509043846/https://en.wikipedia.org/wiki/Hibernate_%28Java%29)

Tags: [hibernate](http://web.archive.org/web/20210509043846/https://mkyong.com/tag/hibernate/) [tutorials](http://web.archive.org/web/20210509043846/https://mkyong.com/tag/tutorials/)

`<input type="hidden" id="mkyong-current-postId" value="4264">`
