
# Struts 2 URL 标记示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-url-tag-example/>

下载：[Struts2-URL-Tag-Example.zip](http://web.archive.org/web/20190307231639/http://www.mkyong.com/wp-content/uploads/2010/07/Struts2-URL-Tag-Example.zip)

Struts 2 的`url`标签用于创建一个 URL 并以文本格式输出。它本身从不工作，但它可以为其他标签提供 URL，如`<s:a>`创建超链接或`<img>`呈现图像。本教程展示了 Struts 2 `url`标签的 5 个常见用例。

## 1. 动作类

转发请求的操作类。

`URLTagAction.java`

```java
package com.mkyong.common.action;

import com.opensymphony.xwork2.ActionSupport;

public class URLTagAction extends ActionSupport{

	public String execute() {
		return SUCCESS;
	}

}
```

## 2. URL 标记示例

下面的 5 个例子展示了 Struts 2 `url`标签的使用。

1. 创建一个图像 URL。

   ```java
   <img src="<s:url valueimg/man.jpg"/>" />
   ```

   输出（假设根上下文名是`Struts2Example`）

   ```java
   <img src="/Struts2Exampimg/man.jpg" />
   ```

2. 创建一个“Google”文本并将其链接到`http://www.google.com`。

   ```java
   <a href="<s:url value="http://www.google.com"  />" target="_blank">Google</a>
   ```

   输出

   ```java
   <a href="http://www.google.com" target="_blank">Google</a>
   ```

   当你定义的 URL 值以`http`或`www`开头时，Struts 2 会按原样渲染，不会像示例 1 那样添加额外的根上下文名。

3. 创建一个带`id`参数的动作 URL，并以文本格式输出。

   ```java
   <s:url action="urlTagAction.action" >
       <s:param name="id">123</s:param>
   </s:url>
   ```

   输出

   ```java
   /Struts2Example/urlTagAction.action?id=123
   ```

4. 创建一个带`name`参数的动作 URL，并通过`<s:property>`与`<s:a>`标签结合。

   ```java
   <s:url action="urlTagAction.action" var="urlTag" >
       <s:param name="name">mkyong</s:param>
   </s:url>
   <a href="<s:property value="#urlTag" />" >URL Tag Action (via property)</a>
   ```

   输出

   ```java
   <a href="/Struts2Example/urlTagAction.action?name=mkyong" >URL Tag Action (via property)</a>
   ```

5. 创建一个带`age`参数的动作 URL，并通过`%{urlTag}`与`<s:a>`标签结合。

   ```java
   <s:url action="urlTagAction.action" var="urlTag" >
       <s:param name="age">99</s:param>
   </s:url>
   <s:a href="%{urlTag}">URL Tag Action (via %)</s:a>
   ```

   输出

   ```java
   <a href="/Struts2Example/urlTagAction.action?age=99">URL Tag Action (via %)</a>
   ```

完整的 JSP 页面代码…

`url.jsp`

```java
<%@ taglib prefix="s" uri="/struts-tags" %>
<html>
<head>
</head>

<body>
<h1>Struts 2 URL tag example</h1>

<ol>
<li>
<img src="<s:url valueimg/man.jpg"/>" />
</li>

<li>
<a href="<s:url value="http://www.google.com"  />" target="_blank">Google</a>
</li>

<li>
<s:url action="urlTagAction.action" >
    <s:param name="id">123</s:param>
</s:url>
</li>

<li>
<s:url action="urlTagAction.action" var="urlTag" >
    <s:param name="name">mkyong</s:param>
</s:url>
<a href="<s:property value="#urlTag" />" >URL Tag Action (via property)</a>
</li>

<li>
<s:url action="urlTagAction.action" var="urlTag" >
    <s:param name="age">99</s:param>
</s:url>
<s:a href="%{urlTag}">URL Tag Action (via %)</s:a>
</li>

</ol>

</body>
</html>
```

## 3. struts.xml

链接一下~

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>
    <constant name="struts.devMode" value="true" />
    <package name="default" namespace="/" extends="struts-default">

	<action name="urlTagAction" 
		class="com.mkyong.common.action.URLTagAction" >
		<result name="success">pages/url.jsp</result>
	</action>

    </package>		
</struts>
```

## 4. 演示

`http://localhost:8080/struts2example/urltagaction.action`

**输出**

![Struts 2 url tag example](img/c8bd6ee1d03694c1c8d9c71ecf2e4977.png "Struts2-Url-Tag-Example")

## 参考

1. [Struts 2 URL 标记文档](http://web.archive.org/web/20190307231639/http://struts.apache.org/2.0.14/docs/url.html)

[struts2](http://web.archive.org/web/20190307231639/http://www.mkyong.com/tag/struts2/) [url](http://web.archive.org/web/20190307231639/http://www.mkyong.com/tag/url/)
