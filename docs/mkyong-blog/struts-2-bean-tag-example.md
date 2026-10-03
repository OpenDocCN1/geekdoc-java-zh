
# Struts 2 bean 标记示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-bean-tag-example/>

Download It – [Struts2-Bean-Tag-Example.zip](http://web.archive.org/web/20190225125854/http://www.mkyong.com/wp-content/uploads/2010/07/Struts2-Bean-Tag-Example.zip)

Struts 2 "`bean`"标签用于在 JSP 页面中实例化一个类。在本教程中，您将使用"`bean`"标记实例化一个名为"`HelloBean`"的类，通过"`param`"元素设置其属性并打印出值。

## 1. 简单豆

一个简单的类，稍后使用`bean`标签来实例化它。

**HelloBean.java**

```java
package com.mkyong.common.action;

public class HelloBean{

	private String msg;

	public String getMsg() {
		return msg;
	}

	public void setMsg(String msg) {
		this.msg = msg;
	}

}
```

## 2. 动作

转发请求的操作类。

**BeanTagAction.java**

```java
package com.mkyong.common.action;

import com.opensymphony.xwork2.ActionSupport;

public class BeanTagAction extends ActionSupport{

	public String execute() {
		return SUCCESS;
	}

}
```

## 3. Bean 标记示例

一个 JSP 页面，展示了如何使用"`bean`"标记实例化"`HelloBean`"。

在"`bean`"标签中，您可以通过"`var`"属性为 bean 分配一个名称，之后您可以通过`#var_bean_name`访问该 bean，或通过`#var_bean_name.property`访问其属性值。

**bean.jsp**

```java
<%@ taglib prefix="s" uri="/struts-tags" %>
<html>
<head>
</head>

<body>
<h1>Struts 2 Bean tag example</h1>

<s:bean name="com.mkyong.common.action.HelloBean" var="hello">
  <s:param name="msg">Hello Bean Tag</s:param>
</s:bean>

The HelloBean's msg property value : <s:property value="#hello.msg"/>

</body>
</html>
```

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

	<action name="beanTagAction" 
	    class="com.mkyong.common.action.BeanTagAction" >
	    <result name="success">pages/bean.jsp</result>
	</action>

    </package>
</struts>
```

## 5. 演示

*http://localhost:8080/struts2example/beanTagAction.action*

**输出**

![Struts 2 bean tag example](img/755673560e928c180a3c250b38a3c5d4.png "Struts2-Bean-Tag-Example")

## 参考

1. [Struts 2 Bean 标签文档](http://web.archive.org/web/20190225125854/http://struts.apache.org/2.0.14/docs/bean.html)

[struts2](http://web.archive.org/web/20190225125854/http://www.mkyong.com/tag/struts2/)
