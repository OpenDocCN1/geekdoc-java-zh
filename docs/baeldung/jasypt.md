
# Jasypt 简介

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/jasypt>

![相关图示](img/b808e9503a721fd8002f00c4cc71c674.png)

想要真正、**实时地洞察正在运行的身份验证流程**是非常困难的。流程的某些部分可能对我们完全隐藏；如果完整的授权过程需要从远程 OAuth 生产服务器重定向，那么每次调试都必须经过该生产服务器。实际上，这在本地进行调试是行不通的，我们无法重现确切的状态，也无法检查底层实际发生的事情。这并不理想。

为了应对这些挑战，我们构建了 Lightrun，一个实时生产环境调试工具，帮助您通过代码级信息理解复杂流程。您无需远程调试器，无需停止正在运行的服务，即可添加日志、获取快照（虚拟断点）和收集指标，最重要的是，这一切都是**实时的且没有副作用**。

通过本 5 分钟教程，了解如何使用 Lightrun 调试此类场景：

[>> 使用 Lightrun 调试身份验证和授权](/web/20220524032115/https://www.baeldung.com/lightrun-n-security)

## 1. 概述

在本文中，我们将关注`[Jasypt](https://web.archive.org/web/20220524032115/http://www.jasypt.org/index.html)` (Java 简化加密)库。

`Jasypt`是一个 Java 库，它允许开发人员以最小的精力为项目添加基本加密功能，而无需深入了解加密协议的实现细节。

## 2. 使用简单加密

假设我们正在构建一个 Web 应用程序，用户在其中提交账户私有数据。我们需要将该数据存储在数据库中，但以纯文本形式存储是不安全的。一种处理方法是，在数据库中存储加密数据，并在特定用户检索时对其进行解密。

要使用非常简单的算法进行加密和解密，我们可以使用来自 `Jasypt` 库的`[BasicTextEncryptor](https://web.archive.org/web/20220524032115/http://www.jasypt.org/api/jasypt/1.8/org/jasypt/util/text/BasicTextEncryptor.html)`类：

```java
BasicTextEncryptor textEncryptor = new BasicTextEncryptor();
String privateData = "secret-data";
textEncryptor.setPasswordCharArray("some-random-data".toCharArray());
```

然后我们可以使用`encrypt()`方法加密明文：

```java
String myEncryptedText = textEncryptor.encrypt(privateData);
assertNotSame(privateData, myEncryptedText);
```

如果想将给定用户的私有数据存入数据库，可以存储`myEncryptedText`，而不违反任何安全限制。若要将数据解密回纯文本，可以使用`decrypt()`方法：

```java
String plainText = textEncryptor.decrypt(myEncryptedText);

assertEquals(plainText, privateData);
```

我们看到解密后的数据等同于之前加密的明文数据。

## 3. 单向加密

前面的示例不是执行身份验证的理想方式，尤其是当我们想要存储用户密码时。理想情况下，我们会加密密码，但无法解密。当用户尝试登录时，我们会对其输入的密码进行加密，并将其与数据库中存储的加密密码进行比较。这样，我们就不必操作明文密码。

我们可以使用`BasicPasswordEncryptor`类执行单向加密：

```java
String password = "secret-pass";
BasicPasswordEncryptor passwordEncryptor = new BasicPasswordEncryptor();
String encryptedPassword = passwordEncryptor.encryptPassword(password); 
```

然后，将已加密的密码与尝试登录的用户密码进行比较，而无需解密数据库中已存储的密码：

```java
boolean result = passwordEncryptor.checkPassword("secret-pass", encryptedPassword);

assertTrue(result);
```

## 4. 配置加密算法

我们可以使用更强的加密算法，但需要为 JVM 安装[Java Cryptography Extension (JCE) 无限强度管辖策略文件](https://web.archive.org/web/20220524032115/http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html)（安装说明包含在下载文件中）。

在 `Jasypt` 中，我们可以通过使用`StandardPBEStringEncryptor`类并使用`setAlgorithm()`方法来定制强加密：

```java
StandardPBEStringEncryptor encryptor = new StandardPBEStringEncryptor();
String privateData = "secret-data";
encryptor.setPassword("some-random-passwprd");
encryptor.setAlgorithm("PBEWithMD5AndTripleDES");
```

我们将加密算法设置为`PBEWithMD5AndTripleDES`。

接下来，加密和解密的过程与之前使用`BasicTextEncryptor`类相同：

```java
String encryptedText = encryptor.encrypt(privateData);
assertNotSame(privateData, encryptedText);

String plainText = encryptor.decrypt(encryptedText);
assertEquals(plainText, privateData);
```

## 5. 使用多线程解密

当我们在多核机器上运行时，我们希望并行处理解密以获得良好的性能。为此，我们可以使用`[PooledPBEStringEncryptor](https://web.archive.org/web/20220524032115/http://www.jasypt.org/api/jasypt/1.9.0/org/jasypt/encryption/pbe/PooledPBEStringEncryptor.html)`并调用`setPoolSize()` API 来创建池。池中的每个加密器可以被不同的线程并行使用：

```java
PooledPBEStringEncryptor encryptor = new PooledPBEStringEncryptor();
encryptor.setPoolSize(4);
encryptor.setPassword("some-random-data");
encryptor.setAlgorithm("PBEWithMD5AndTripleDES");
```

最好将池大小设置为等于机器的核心数量。加密和解密的代码与前面的示例相同。

## 6. 在其他框架中的使用

最后需要指出的是，`Jasypt`库可以与许多其他库集成，当然包括`Spring`框架。我们只需创建一个配置，就可以为 Spring 应用程序添加加密支持。如果我们使用`Hibernate`作为数据访问框架来存储敏感数据，我们也可以将`Jasypt`与之集成。

关于这些集成以及其他一些框架的说明，可以在[Jasypt 主页](https://web.archive.org/web/20220524032115/http://www.jasypt.org/)的`Guides`部分找到。

## 7. 结论

在本文中，我们看到了`Jasypt`库，它通过使用经过充分测试的加密算法，帮助我们创建更安全的应用程序。它提供了易于使用的简单 API。

所有这些示例和代码片段的实现都可以在[GitHub 项目](https://web.archive.org/web/20220524032115/https://github.com/eugenp/tutorials/tree/master/libraries-security)中找到——这是一个 Maven 项目，因此它应该很容易导入和运行。
