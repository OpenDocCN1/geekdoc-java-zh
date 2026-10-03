

# 休眠错误：线程“main”中的异常 `java.lang.NoClassDefFoundError: antlr/ANTLRException`

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/hibernate/hibernate-error-exception-in-thread-main-java-lang-noclassdeffounderror-antlrantlrexception/>

这是由于缺少 `antlr` 库造成的。这通常发生在你调用 Hibernate 的查询语句的时候。

```java
Exception in thread "main" java.lang.NoClassDefFoundError: antlr/ANTLRException
	at org.hibernate.hql.ast.ASTQueryTranslatorFactory.createQueryTranslator(ASTQueryTranslatorFactory.java:35)
	at org.hibernate.engine.query.HQLQueryPlan.<init>(HQLQueryPlan.java:74)
	at org.hibernate.engine.query.HQLQueryPlan.<init>(HQLQueryPlan.java:56)
	at org.hibernate.engine.query.QueryPlanCache.getHQLQueryPlan(QueryPlanCache.java:72)
	at org.hibernate.impl.AbstractSessionImpl.getHQLQueryPlan(AbstractSessionImpl.java:133)
	at org.hibernate.impl.AbstractSessionImpl.createQuery(AbstractSessionImpl.java:112)
	at org.hibernate.impl.SessionImpl.createQuery(SessionImpl.java:1623)
	at com.mkyong.common.App.main(App.java:23)
Caused by: java.lang.ClassNotFoundException: antlr.ANTLRException
	at java.net.URLClassLoader$1.run(URLClassLoader.java:200)
	at java.security.AccessController.doPrivileged(Native Method)
	at java.net.URLClassLoader.findClass(URLClassLoader.java:188)
	at java.lang.ClassLoader.loadClass(ClassLoader.java:307)
	at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:301)
	at java.lang.ClassLoader.loadClass(ClassLoader.java:252)
	at java.lang.ClassLoader.loadClassInternal(ClassLoader.java:320)
	... 8 more
```

## 解决办法

可以从 [Antlr 官网](http://web.archive.org/web/20190308011741/http://www.antlr.org/) 下载该库。

或者，在 Maven 的 `pom.xml` 中添加依赖项：

```xml
<dependency>
	<groupId>antlr</groupId>
	<artifactId>antlr</artifactId>
	<version>2.7.7</version>
</dependency>
```

`hibernate`<input type="hidden" id="mkyong-postId" value="2640">

