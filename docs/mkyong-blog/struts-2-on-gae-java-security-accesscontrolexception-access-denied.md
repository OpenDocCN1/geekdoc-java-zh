
# GAE 上的 Struts 2 – Java Security AccessControlException：拒绝访问

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/google-app-engine/struts-2-on-gae-java-security-accesscontrolexception-access-denied/>

## 问题

在 Google App Engine（SDK v1.6.3.1）上开发 Struts 2（v2.3.1.2），本地开发时，遇到“`java.security.AccessControlException: access denied`”错误？

![struts 2 on gae access denied error](img/d1491cb180fdf6f02349a9906128f639.png "struts2-gae-access-denied-error")

## 解决办法

通常，这是因为你在`struts.xml`文件中打开了 **devMode**。

*文件：`struts.xml`*

```
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>
	<constant name="struts.devMode" value="true" /> 
	//...
</struts>
```

当你打开`devMode`时，Struts 2 将试图写入磁盘进行日志记录，这被 GAE 拒绝，因为它只能写入谷歌数据存储。

要解决这个问题，您必须删除`struts.xml`文件中的`devMode`语句。

**注意**

简而言之，Struts 2 的`devMode`在 GAE 环境中不受支持。

## 参考

1. [Struts 2.1.8 在 App Engine 的本地服务器上遇到了 AccessControlException](http://web.archive.org/web/20220607032907/https://groups.google.com/group/google-appengine-java/browse_thread/thread/b78fea68441eaf4e/4eec677cef795e03)

<input type="hidden" id="mkyong-current-postId" value="10856">
