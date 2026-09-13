
# `ClassNotFoundException: com.sun.syndication.feed.WireFeed`

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/classnotfoundexception-com-sun-syndication-feed-wirefeed/>

## 问题

用 Spring MVC 开发 RSS，扩展了“`AbstractRssFeedView`”，在应用程序启动时出现以下错误信息。

```java
Caused by: java.lang.NoClassDefFoundError: com/sun/syndication/feed/WireFeed
	at java.lang.Class.getDeclaredConstructors0(Native Method)
	at java.lang.Class.privateGetDeclaredConstructors(Class.java:2389)
	at java.lang.Class.getDeclaredConstructors(Class.java:1836)
	//...
Caused by: java.lang.ClassNotFoundException: com.sun.syndication.feed.WireFeed
	at org.apache.catalina.loader.WebappClassLoader.loadClass(WebappClassLoader.java:1516)
	at org.apache.catalina.loader.WebappClassLoader.loadClass(WebappClassLoader.java:1361)
	at java.lang.ClassLoader.loadClassInternal(ClassLoader.java:320)
	... 41 more
```

## 解决办法

Spring MVC 使用“[罗马](http://web.archive.org/web/20190225093251/http://java.net/projects/rome/)”来生成 RSS 提要。对于 Maven，在`pom.xml`文件中包含下面的依赖关系。

```xml
<dependency>
	<groupId>net.java.dev.rome</groupId>
	<artifactId>rome</artifactId>
	<version>1.0.0</version>
</dependency>
```

[spring mvc](http://web.archive.org/web/20190225093251/http://www.mkyong.com/tag/spring-mvc/)![](img/969687f39547cd47c77ce11e3527f5d5.png)
