
# Struts 2 推送标签示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-push-tag-example/>

Download It – [Struts2-Push-Tag-Example.zip](http://web.archive.org/web/20190304032830/http://www.mkyong.com/wp-content/uploads/2010/07/Struts2-Push-Tag-Example.zip)

Struts 2 "`push`"标签用于将值推到栈顶，以便于访问或引用。参见一个完整的“`push`”标签示例：

## 1. 行动

操作类仅转发请求。

**PushTagAction.java**

```java
package com.mkyong.common.action;

import com.opensymphony.xwork2.ActionSupport;

public class PushTagAction extends ActionSupport{

	public String execute() throws Exception {

		return SUCCESS;
	}
}
```

## 2. 豆

一个简单的 `Person` 类，稍后会将它放入堆栈以便于访问。

**Person.java**

```java
package com.mkyong.common;

public class Person{

	private String firstName = "This is firstName";
	private String lastName = "This is lastName";

	public String getFirstName() {
		return firstName;
	}
	public String getLastName() {
		return lastName;
	}
}
```

## 3. 推送标签示例

它显示了"`push`"标签的使用。

**push.jsp**

```java
<%@ taglib prefix="s" uri="/struts-tags" %>
<html>
<head>
</head>

<body>
<h1>Struts 2 push tag example</h1>

<h2>1. Normal way</h2>
<s:bean name="com.mkyong.common.Person" var="personBean" />
First name : <s:property value="#personBean.firstName" /><br/>
Last name: <s:property value="#personBean.lastName" /><br/>

<h2>2. Push way</h2>
<s:push value="#personBean" >
First name : <s:property value="firstName" /><br/>
Last name: <s:property value="lastName" /><br/>
</s:push>

</body>
</html>
```

它是如何工作的？

正常情况下，如果你想得到豆子的属性，可以像`<s:property value="#personBean.firstName"/>`一样引用。使用"`push`"标签，可以将"`#personBean`"推到栈顶，直接访问属性`<s:property value="firstName"/>`。两者返回相同的结果，只是访问机制不同。

`push`标签可以帮你少输入几个字符，但除此之外没有太多实际价值。

## 4. struts.xml

链接一下~

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>
 	<constant name="struts.devMode" value="true" />
	<package name="default" namespace="/" extends="struts-default">

		<action name="pushTagAction" 
			class="com.mkyong.common.action.PushTagAction" >
			<result name="success">pages/push.jsp</result>
		</action>

	</package>
</struts>
```

## 5. 演示

`http://localhost:8080/struts2example/pushTagAction.action`

**输出**

![Struts 2 push tag example](img/72e8f8b3dc280f2faa314575e90a7dc8.png "Struts2-Push-Tag-Example")

## 参考

1. [Struts 2 推送标签文档](http://web.archive.org/web/20190304032830/http://struts.apache.org/2.1.8/docs/push.html)

[struts2](http://web.archive.org/web/20190304032830/http://www.mkyong.com/tag/struts2/)
