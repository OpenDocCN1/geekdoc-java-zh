
# Struts 2 参数标记示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-param-tag-example/>

Download It – [Struts2-Param-Tag-Example.zip](http://web.archive.org/web/20190304031549/http://www.mkyong.com/wp-content/uploads/2010/07/Struts2-Param-Tag-Example.zip)

Struts 2 "`param`"标签用于参数化其他标签。但是，当您声明了"`param`"标记时，可以用两种方式定义"参数值":

1. `value`属性。
2. "`param`"标记的开始和结束之间的文本。

举个例子：

```
<param name="fruit">Banana</param>  {Case 1}
<param name="fruit" value="Banana"/> {Case 2}
```

在 Struts 2 中，两者具有完全不同的含义。在"Case 1"中，该值被视为`java.lang.String`对象；而在"Case 2"中，该值被视为`java.lang.Object`对象。

上面的陈述最好用一些例子来说明：

## 示例 1

通过"`param`"标记将一个"字符串"值设置到 bean 属性中，您必须这样声明：

```
<s:bean name="com.mkyong.common.Person" var="personBean">
	<s:param name="nickName">mkyong</s:param>
</s:bean>
```

而不是：

```
<s:bean name="com.mkyong.common.Person" var="personBean">
	<s:param name="nickName" value="mkyong"></s:param>
</s:bean>
```

如果您在"`value`"属性中声明了"字符串"值，Struts 2 将会忽略它。

## 示例 2

通过"`param`"标签将一个`java.lang.Object`对象设置到 bean 属性中，声明如下：

```
<s:bean name="com.mkyong.common.Fruit" var="fruitBean">
	<s:param name="fruitName">Banana</s:param>
</s:bean>

<s:bean name="com.mkyong.common.Person" var="personBean">
	<s:param name="favorFruit" value="#fruitBean"></s:param>
</s:bean>
```

## 示例 3

对于原始类型，你可以自由地在任何地方声明它，它就像一个魔咒一样起作用。

```
<s:bean name="com.mkyong.common.Person" var="personBean">
	<s:param name="age" value="99"></s:param>
</s:bean>
// or
<s:bean name="com.mkyong.common.Person" var="personBean">
	<s:param name="age">99</s:param>
</s:bean>
```

"`param`"标签不仅可用于 bean 标签，它几乎适用于所有需要参数化的其他标签。在 Struts 2 中，"`param`"标签确实是一个令人困惑的标签，许多新的 Struts 2 开发者会陷入这个愚蠢的陷阱，并疑惑为什么一个简单的"String" setter 方法不起作用。希望 Struts 2 团队将来能设计出更用户友好的标签。

## Struts 2 参数标记示例

一个完整的 Struts 2 "`param`"标签示例。

## 1. 动作

转发请求的操作类。

**ParamTagAction.java**

```
package com.mkyong.common.action;

import com.opensymphony.xwork2.ActionSupport;

public class ParamTagAction extends ActionSupport{

	public String execute() {
		return SUCCESS;
	}

}
```

## 2. Bean

两个 beans，稍后用"`param`"标签初始化。

**Person.java**

```
package com.mkyong.common;

public class Person{

	private String nickName;
	private int age;
	private Fruit favorFruit;

	public String getNickName() {
		return nickName;
	}
	public void setNickName(String nickName) {
		this.nickName = nickName;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	public Fruit getFavorFruit() {
		return favorFruit;
	}
	public void setFavorFruit(Fruit favorFruit) {
		this.favorFruit = favorFruit;
	}

	public String getFruitName(){
		return this.favorFruit.getFruitName();
	}

}
```

**Fruit.java**

```
package com.mkyong.common;

public class Fruit{

	private String fruitName;

	public String getFruitName() {
		return fruitName;
	}

	public void setFruitName(String fruitName) {
		this.fruitName = fruitName;
	}

}
```

## 3. `param`标签示例

一个 JSP 页面显示了"`param`"标签的使用。

**我的钱.jsp**

```
<%@ taglib prefix="s" uri="/struts-tags" %>
<html>
<head>
</head>

<body>
<h1>Struts 2 param tag example</h1>

<s:bean name="com.mkyong.common.Fruit" var="fruitBean">
	<s:param name="fruitName">Banana</s:param>
</s:bean>

<s:bean name="com.mkyong.common.Person" var="personBean">
	<s:param name="nickName">ah pig ah dog</s:param>
	<s:param name="age">99</s:param>
	<s:param name="favorFruit" value="#fruitBean"></s:param>
</s:bean>

<h2>PersonBean</h2>
<ol>
<li>NickName property : <s:property value="#personBean.nickName" /></li>
<li>Age property : <s:property value="#personBean.age" /></li>
<li>Fruit property : <s:property value="#personBean.fruitName" /></li>
</ol>
</body>
</html>
```

## 4. `struts.xml`

链接一下~

```
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>
 	<constant name="struts.devMode" value="true" />
	<package name="default" namespace="/" extends="struts-default">

		<action name="paramTagAction" 
			class="com.mkyong.common.action.ParamTagAction" >
			<result name="success">pages/param.jsp</result>
		</action>

	</package>
</struts>
```

## 5. 演示

*http://localhost:8080/struts2example/paramtagaction.action*

**输出**

![Struts 2 param tag example](img/1c65e50370dec86a6a8ae8e1140f3690.png "Struts2-Param-Tag-Example")

## 参考

1. [Struts 2 参数标签文档](http://web.archive.org/web/20190304031549/http://struts.apache.org/2.0.14/docs/param.html)

[struts2](http://web.archive.org/web/20190304031549/http://www.mkyong.com/tag/struts2/)
