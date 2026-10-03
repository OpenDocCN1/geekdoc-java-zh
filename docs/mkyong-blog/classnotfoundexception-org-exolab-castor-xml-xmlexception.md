
# `ClassNotFoundException: org.exolab.castor.xml.XMLException`

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring3/classnotfoundexception-org-exolab-castor-xml-xmlexception/>

## 问题

在 Spring OXM（对象 XML 映射）中，当将一个对象转换为 XML 文件时，会遇到以下错误消息：

```java
Caused by: java.lang.ClassNotFoundException: org.exolab.castor.xml.XMLException
	at java.net.URLClassLoader$1.run(URLClassLoader.java:200)
	at java.security.AccessController.doPrivileged(Native Method)
	at java.net.URLClassLoader.findClass(URLClassLoader.java:188)
	at java.lang.ClassLoader.loadClass(ClassLoader.java:307)
	at sun.misc.Launcher$AppClassLoader.loadClass(URLClassLoader.java:301)
	at java.lang.ClassLoader.loadClass(URLClassLoader.java:252)
	at java.lang.ClassLoader.loadClassInternal(ClassLoader.java:320)
	... 29 more
```

Spring OXM 中是否包含[Castor 数据绑定框架](http://web.archive.org/web/20190121170502/http://www.castor.org/)？

## 解决办法

Castor 是 `spring-oxm.jar` 中的一个可选依赖项。要在 Spring OXM 中使用 Castor 来编组和解组 XML，请将这个 Castor 依赖项添加到您的 Maven `pom.xml` 文件中。

```xml
<dependencies>

		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-oxm</artifactId>
			<version>3.0.5.RELEASE</version>
		</dependency>

		<!-- Uses Castor for XML -->
		<dependency>
			<groupId>org.codehaus.castor</groupId>
			<artifactId>castor</artifactId>
			<version>1.2</version>
		</dependency>

		<!-- Castor need this -->
		<dependency>
			<groupId>xerces</groupId>
			<artifactId>xercesImpl</artifactId>
			<version>2.8.1</version>
		</dependency>

	</dependencies>
```

[oxm](http://web.archive.org/web/20190121170502/http://www.mkyong.com/tag/oxm/) [spring3](http://web.archive.org/web/20190121170502/http://www.mkyong.com/tag/spring3/) ![](img/b99b2b274c86c86f8e438fb26df1a17a.png)
