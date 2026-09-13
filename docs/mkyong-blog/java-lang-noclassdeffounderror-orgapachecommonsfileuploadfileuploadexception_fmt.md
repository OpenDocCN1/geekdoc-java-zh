
# Java.lang.NoClassDefFoundError: org/Apache/commons/fileupload/FileUploadException

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts/java-lang-noclassdeffounderror-orgapachecommonsfileuploadfileuploadexception/>

## 问题

在 Struts 框架中，在文件上传过程中遇到以下异常。

```
javax.servlet.ServletException: Servlet execution threw an exception

root cause

java.lang.NoClassDefFoundError: org/apache/commons/fileupload/FileUploadException
	java.lang.Class.getDeclaredConstructors0(Native Method)
	java.lang.Class.privateGetDeclaredConstructors(Unknown Source)
	java.lang.Class.getConstructor0(Unknown Source)
	java.lang.Class.newInstance0(Unknown Source)
	java.lang.Class.newInstance(Unknown Source)
```

## 解决办法

Struts 使用`commons-fileupload.jar`库进行文件上传过程。您必须将此库包含到项目依赖项库文件夹中。

1. 从[官方网站](http://web.archive.org/web/20190223081913/http://commons.apache.org/fileupload/)获取`commons-fileupload.jar`。
2. 从 Maven 存储库中获取`commons-fileupload.jar`。

```
<dependency>
    <groupId>commons-fileupload</groupId>
    <artifactId>commons-fileupload</artifactId>
    <version>1.2.1</version>
</dependency>
```

[struts](http://web.archive.org/web/20190223081913/http://www.mkyong.com/tag/struts/)
