

# 休眠错误：`java.lang.NoClassDefFoundError: javax/transaction/Synchronization`

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/hibernate/hibernate-error-java-lang-noclassdeffounderror-javaxtransactionsynchronization/>

## 问题

这是由于缺少`jta.jar`造成的，通常发生在 Hibernate 事务开发中。

```java
java.lang.NoClassDefFoundError: javax/transaction/Synchronization
    at org.hibernate.impl.SessionImpl.<init>(SessionImpl.java:213)
    at org.hibernate.impl.SessionFactoryImpl.openSession(SessionFactoryImpl.java:473)
    at org.hibernate.impl.SessionFactoryImpl.openSession(SessionFactoryImpl.java:497)
    at org.hibernate.impl.SessionFactoryImpl.openSession(SessionFactoryImpl.java:505)
    at com.mkyong.common.App.main(App.java:13)
Caused by: java.lang.ClassNotFoundException: javax.transaction.Synchronization
    at java.net.URLClassLoader$1.run(Unknown Source)
    at java.security.AccessController.doPrivileged(Native Method)
    at java.net.URLClassLoader.findClass(Unknown Source)
    at java.lang.ClassLoader.loadClass(ClassLoader.java:?)
    at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:?)
    at java.lang.ClassLoader.loadClass(ClassLoader.java:?)
    at java.lang.ClassLoader.loadClassInternal(ClassLoader.java:?)
    ... 5 more
```

## 解决办法

你可以从默认的 Maven central、JBoss 或 Java.net 库下载`jta.jar`。

### 1. Maven 中央存储库

```xml
<dependencies>
    <dependency>
        <groupId>javax.transaction</groupId>
        <artifactId>jta</artifactId>
        <version>1.1</version>
    </dependency>
</dependencies>
```

### 2. JBoss Maven 资源库

添加 JBoss Maven 存储库：

```xml
<repositories>
    <repository>
        <id>JBoss repository</id>
        <url>http://repository.jboss.com/maven2/</url>
    </repository>
</repositories>
```

并定义`jta.jar`明细：

```xml
<dependencies>
    <dependency>
        <groupId>javax.transaction</groupId>
        <artifactId>jta</artifactId>
        <version>1.1</version>
    </dependency>
</dependencies>
```

### 3. Java.net Maven 知识库

添加 Java.net Maven 资源库：

```xml
<repositories>
    <repository>
        <id>Java 2</id>
        <url>http://download.java.net/maven/2/</url>
    </repository>
</repositories>
```

并定义`jta1.0.1B.jar`明细：

```xml
<dependencies>
    <dependency>
        <groupId>javax.transaction</groupId>
        <artifactId>jta</artifactId>
        <version>1.0.1B</version>
    </dependency>
</dependencies>
```

## 注意

或者，你可以包含`javaee.jar`，它位于 J2EE SDK 的文件夹下。`javaee.jar`包含`javax/transaction/Synchronization`类。

[hibernate](http://web.archive.org/web/20190117070027/http://www.mkyong.com/tag/hibernate/)

