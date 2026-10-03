
# `ClassNotFoundException: com.thoughtworks.xstream.io.HierarchicalStreamReader`

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/classnotfoundexception-com-thoughtworks-xstream-io-hierarchicalstreamreader/>

## 问题

Spring MVC 中的 XML 开发，通过 OXM，命中“`HierarchicalStreamReader`”类未发现异常。

```java
Caused by: java.lang.ClassNotFoundException: com.thoughtworks.xstream.io.HierarchicalStreamReader
	at org.apache.catalina.loader.WebappClassLoader.loadClass(WebappClassLoader.java:1516)
	at org.apache.catalina.loader.WebappClassLoader.loadClass(WebappClassLoader.java:1361)
	at java.lang.ClassLoader.loadClassInternal(ClassLoader.java:320)
	... 49 more
```

## 解决办法

类“`HierarchicalStreamReader`”属于“`xstream.jar`”。如果您使用的是 Maven，那么在您的 `pom.xml` 文件中声明以下依赖关系：

```xml
<dependency>
	<groupId>com.thoughtworks.xstream</groupId>
	<artifactId>xstream</artifactId>
	<version>1.3.1</version>
</dependency>
```

**Note**

For Ant user, just download the `xstream.jar` from [http://xstream.codehaus.org/](http://web.archive.org/web/20190306164910/http://xstream.codehaus.org/) directly.

[spring mvc](http://web.archive.org/web/20190306164910/http://www.mkyong.com/tag/spring-mvc/)
