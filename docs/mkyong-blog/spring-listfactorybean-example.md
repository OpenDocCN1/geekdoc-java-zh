
# Spring ListFactoryBean 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring/spring-listfactorybean-example/>

`ListFactoryBean`类为开发人员提供了在 Spring 的 Bean 配置文件中创建具体列表集合类（`ArrayList`和`LinkedList`）的方法。

这里有一个`ListFactoryBean`的例子，它会在运行时实例化一个`ArrayList`，并将其注入到一个 Bean 属性中。

```java
package com.mkyong.common;

import java.util.List;

public class Customer 
{
	private List lists;
	//...
}
```

Spring 的 bean 配置文件。

```xml
<beans 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">

	<bean id="CustomerBean" class="com.mkyong.common.Customer">
		<property name="lists">
			<bean class="org.springframework.beans.factory.config.ListFactoryBean">
				<property name="targetListClass">
					<value>java.util.ArrayList</value>
				</property>
				<property name="sourceList">
					<list>
						<value>1</value>
						<value>2</value>
						<value>3</value>
					</list>
				</property>
			</bean>
		</property>
	</bean>

</beans>
```

或者，您也可以使用 util schema 和`<list>`来实现同样的事情。

```xml
<beans 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
	xmlns:util="http://www.springframework.org/schema/util"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans-2.5.xsd
	http://www.springframework.org/schema/util
	http://www.springframework.org/schema/util/spring-util-2.5.xsd">

	<bean id="CustomerBean" class="com.mkyong.common.Customer">
		<property name="lists">
			<util:list list-class="java.util.ArrayList">
				<value>1</value>
				<value>2</value>
				<value>3</value>
			</util:list>
		</property>
	</bean>

</beans>
```

记得包括 util 模式，否则您将遇到以下错误：

```xml
Caused by: org.xml.sax.SAXParseException: 
	The prefix "util" for element "util:list" is not bound.
```

运行它……

```java
package com.mkyong.common;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class App {
	public static void main(String[] args) {
		ApplicationContext context = new ClassPathXmlApplicationContext(
				"SpringBeans.xml");

		Customer cust = (Customer) context.getBean("CustomerBean");
		System.out.println(cust);

	}
}
```

输出：

```java
Customer [lists=[1, 2, 3]] Type=[class java.util.ArrayList]
```

您已经实例化了`ArrayList`，并在运行时将其注入到`Customer`的`lists`属性中。

## 下载源代码

Download It – [Spring-ListFactoryBean-Example.zip](http://web.archive.org/web/20190302163354/http://www.mkyong.com/wp-content/uploads/2010/03/Spring-ListFactoryBean-Example.zip) (5KB)

## 参考

1. [ListFactoryBean Javadoc](http://web.archive.org/web/20190302163354/http://static.springsource.org/spring/docs/2.5.x/api/org/springframework/beans/factory/config/ListFactoryBean.html)

[spring](http://web.archive.org/web/20190302163354/http://www.mkyong.com/tag/spring/)
