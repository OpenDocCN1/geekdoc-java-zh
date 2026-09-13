
# spring——如何在 bean 中访问 message source(message source aware)

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring/spring-how-to-access-messagesource-in-bean-messagesourceaware/>

在上一个教程中，您可以通过 `ApplicationContext` 获得消息源。但是对于获取 `MessageSource` 的 bean，您必须实现 `MessageSourceAware` 接口。

## 例子

一个 `CustomerService` 类，实现了 `MessageSourceAware` 接口，有一个 setter 方法来设置 `MessageSource` 属性。

在 Spring 容器初始化期间，如果任何类实现了 `MessageSourceAware` 接口，Spring 将自动通过 `setMessageSource(MessageSource messageSource)` setter 方法将 `MessageSource` 注入到该类中。

```java
package com.mkyong.customer.services;

import java.util.Locale;

import org.springframework.context.MessageSource;
import org.springframework.context.MessageSourceAware;

public class CustomerService implements MessageSourceAware
{
	private MessageSource messageSource;

	public void setMessageSource(MessageSource messageSource) {
		this.messageSource = messageSource;
	}

	public void printMessage(){
		String name = messageSource.getMessage("customer.name", 
    			new Object[] { 28, "http://www.mkyong.com" }, Locale.US);

    	System.out.println("Customer name (English) : " + name);

    	String namechinese = messageSource.getMessage("customer.name", 
    			new Object[] { 28, "http://www.mkyong.com" }, 
                        Locale.SIMPLIFIED_CHINESE);

    	System.out.println("Customer name (Chinese) : " + namechinese);
	}

}
```

运行它

```java
package com.mkyong.common;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class App 
{
    public static void main( String[] args )
    {
    	ApplicationContext context = 
    		new ClassPathXmlApplicationContext(
			    new String[] {"locale.xml","Spring-Customer.xml"});

    	CustomerService cust = (CustomerService)context.getBean("customerService");
    	cust.printMessage();
    }
}
```

所有 properties 文件和 XML 文件都复用自上一个 [ResourceBundleMessageSource 教程](http://web.archive.org/web/20190213133419/http://www.mkyong.com/spring/spring-resource-bundle-with-resourcebundlemessagesource-example/)。下载它 – [Spring-MessageSource-Example.zip](http://web.archive.org/web/20190213133419/http://www.mkyong.com/wp-content/uploads/2010/03/Spring-MessageSource-Example.zip)
