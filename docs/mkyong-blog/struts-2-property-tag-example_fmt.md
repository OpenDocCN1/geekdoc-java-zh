
# Struts 2 属性标记示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-property-tag-example/>

下载：[Struts2-Property-Tag-Example.zip](http://web.archive.org/web/20190304031403/http://www.mkyong.com/wp-content/uploads/2010/07/Struts2-Property-Tag-Example.zip)

Struts 2 的`property`标记用于从一个类中获取属性值，如果没有指定，它将默认为当前操作类（堆栈顶部）的属性。本教程展示了如何使用`property`标签从当前的 Action 类和其他 bean 类中获取属性值。

## 1. Action

一个 Action 类，有一个`name`属性。

**PropertyTagAction.java**

```java
package com.mkyong.common.action;

import com.opensymphony.xwork2.ActionSupport;

public class PropertyTagAction extends ActionSupport{

	private String name = "Name from PropertyTagAction.java"; 

	public String getName() {
		return name;
	}

	public String execute() throws Exception {

		return SUCCESS;
	}
}
```

## 2. Bean

一个简单的 Java 类，有一个`name`属性。

**Person.java**

```java
package com.mkyong.common;

public class Person {

	private String name = "Name from Person.java"; 

	public String getName() {
		return name;
	}
}
```

## 3. 属性标签示例

它展示了如何使用`property`标记从`PropertyTagAction`和`Person`类中获取`name`属性值。

**property.jsp**

```java
<%@ taglib prefix="s" uri="/struts-tags" %>
<html>
<head>
</head>

<body>
<h1>Struts 2 property tag example</h1>

<h2>1. Call getName() from propertyTagAction.java</h2> 
<s:property value="name" />

<h2>2. Call getName() from Person.java</h2> 
<s:bean name="com.mkyong.common.Person" var="personBean" />
<s:property value="#personBean.name" />

</body>
</html>
```

`property.jsp`页面是由`PropertyTagAction`操作返回的成功结果页面。如果在`property.jsp`页面中指定了`<s:property value="name" />`，它将默认为当前 Action 类`PropertyTagAction.getName()`的属性。

## 4. struts.xml

链接一下~

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>
 	<constant name="struts.devMode" value="true" />
	<package name="default" namespace="/" extends="struts-default">

		<action name="propertyTagAction" 
			class="com.mkyong.common.action.PropertyTagAction" >
			<result name="success">pages/property.jsp</result>
		</action>

	</package>
</struts>
```

## 5. 演示

`http://localhost:8080/struts2example/propertytagaction.action`

**输出**

![Struts 2 property tag example](img/c1fbfdca6580aab7bcc462678813c2cd.png "Struts2-Property-Tag-Example")

## 参考

1. [Struts 2 属性标签文档](http://web.archive.org/web/20190304031403/http://struts.apache.org/2.0.14/docs/property.html)

[struts2](http://web.archive.org/web/20190304031403/http://www.mkyong.com/tag/struts2/)
