
# 在 JSF 2.0 中自定义验证错误消息

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/customize-validation-error-message-in-jsf-2-0/>

标准 JSF 转换和验证错误消息太详细、太专业，有时不太容易让人理解。在本文中，它向您展示了如何在 JSF 2.0 中定制标准转换或验证错误消息。

## 概要指南

1. 从`jsf-api-2.x.jar`的`Messages.properties`文件中找到您的消息密钥。
2. 创建您自己的属性文件，放置您在上面的`Messages.properties`文件中找到的相同消息键，并用您的自定义错误消息覆盖它。
3. 在`faces-config.xml`中注册您的属性文件，将其作为应用程序级别。
4. 完成了。

## 1. 消息.属性

所有 JSF 标准转换和验证错误消息都存储在`Messages.properties`文件中，该文件可以从`jsf-api-2.x.jar`、`javax\faces\messages.properties`中找到，见下图：

![jsf2-Custom-Validation-Error-Example-1](img/a8af84b3ba063c5f85b91e2f8ce9129b.png "jsf2-Custom-Validation-Error-Example-1")

请参见`Messages.properties`文件的一部分：

```java
...
# ===================================================================
# Converter Errors
# ===================================================================
javax.faces.converter.DateTimeConverter.DATE={2}: ''{0}'' could not be understood as a date.
javax.faces.converter.DateTimeConverter.DATE_detail={2}: ''{0}'' could not be understood as a date. Example: {1} 
...
# ====================================================================
# Validator Errors
# ====================================================================
javax.faces.validator.LengthValidator.MAXIMUM={1}: Validation Error: Length is greater than allowable maximum of ''{0}''
javax.faces.validator.LengthValidator.MINIMUM={1}: Validation Error: Length is less than allowable minimum of ''{0}''
... 
```

比如：

1. `<f:validateLength minimum="5" maximum="10" />`：如果最大长度验证失败，JSF 得到`javax.faces.validator.LengthValidator.MAXIMUM`。如果最小长度验证失败，JSF 得到`javax.faces.validator.LengthValidator.MINIMUM`。

2. `<f:convertDateTime pattern="d-M-yyyy" />`：如果日期验证失败，JSF 得到`javax.faces.converter.DateTimeConverter.DATE_detail`。

**注意**

如果您不确定哪个键匹配哪个验证器标签，只需显示一次错误消息，并与`Messages.properties`进行比较，然后您就会知道要覆盖哪个键。

## 2. 自定义错误消息

创建一个名为`MyMessage.properties`的属性文件（可以是您喜欢的任何名称），将消息键和自定义错误消息放入其中。稍后，将该属性文件放入项目资源文件夹中。

**MyMessage.properties**

```java
javax.faces.converter.DateTimeConverter.DATE={2}: ''{0}'' could not be understood as a date.
javax.faces.converter.DateTimeConverter.DATE_detail=Invalid date format.

javax.faces.validator.LengthValidator.MINIMUM=Minimum length of ''{0}'' is required. 
```

现在，您将自定义`javax.faces.validator.LengthValidator.MINIMUM`的验证错误消息和`javax.faces.converter.DateTimeConverter.DATE_detail`的转换错误消息。

**注意**

对于`XXX_detail`消息键，您还必须覆盖其父键（摘要消息），即不带`_detail`后缀的`XXX`；否则，JSF 将忽略您新的自定义错误消息，并继续从`Messages.properties`中获取标准错误消息，这可能是 JSF 2.0 中的一个 bug？

## 3. 注册消息包

在`faces-config.xml`中注册您的自定义属性文件，将其作为应用程序级别。

**faces-config.xml**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<faces-config

    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee 
    http://java.sun.com/xml/ns/javaee/web-facesconfig_2_0.xsd"
    version="2.0">
     <application>
	  <message-bundle>
	  	com.mkyong.MyMessage
	  </message-bundle>
     </application>
</faces-config> 
```

## 4. 演示

一个 JSF 页面，同时添加`<f:validateLength />`和`<f:convertDateTime />`验证。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html    
      xmlns:h="http://java.sun.com/jsf/html"
      xmlns:f="http://java.sun.com/jsf/core"
      >
    <h:body>

    	<h1>Customize validation error message in JSF 2.0</h1>

	<h:form>

		<h:panelGrid columns="3">

			Enter your username :

			<h:inputText id="username" value="#{user.username}" 
				size="20" required="true" label="Username">
				<f:validateLength minimum="5" maximum="10" />
			</h:inputText>

			<h:message for="username" style="color:red" />

			Enter your DOB :

			<h:inputText id="dob" value="#{user.dob}" 
				size="20" required="true" label="Date of Birth">
				<f:convertDateTime />
			</h:inputText>

			<h:message for="dob" style="color:red" />

		</h:panelGrid>

		<h:commandButton value="Submit" action="result" />

	</h:form>	
    </h:body>
</html> 
```

当验证失败时，现在显示您的自定义错误消息。

![jsf2-Custom-Validation-Error-Example-2](img/3f5836b04916439cebd2186e8aad1cf7.png "jsf2-Custom-Validation-Error-Example-2")

## 下载源代码

Download It – [JSF-2-Custom-Validation-Error-Message-Example.zip](http://web.archive.org/web/20210305084916/http://www.mkyong.com/wp-content/uploads/2010/10/JSF-2-Custom-Validation-Error-Message-Example.zip) (11KB)

## 参考

1. [JSF 2 号&资源包](http://web.archive.org/web/20210305084916/http://www.mkyong.com/jsf2/jsf-2-0-and-resource-bundles-example/)

Tags : [error message](http://web.archive.org/web/20210305084916/https://mkyong.com/tag/error-message/) [jsf2](http://web.archive.org/web/20210305084916/https://mkyong.com/tag/jsf2/) [validation](http://web.archive.org/web/20210305084916/https://mkyong.com/tag/validation/)
