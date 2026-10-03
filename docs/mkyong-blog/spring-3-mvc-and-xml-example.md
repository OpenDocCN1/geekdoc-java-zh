
# Spring 3 MVC 和 XML 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/spring-3-mvc-and-xml-example/>

在 Spring 3 中，`mvc:annotation-driven`的一个特性是支持将对象转换为 XML 文件，如果 JAXB 在项目类路径中的话。

在本教程中，我们将向您展示如何将返回对象转换为 XML 格式，并通过 Spring `@MVC`框架将其返回给用户。

使用的技术：

1. Spring 3.0.5 发布版
2. JDK 1.6
3. Eclipse 3.6
4. Maven 3

**JAXB in JDK6**

JAXB 包含在 JDK6 中，因此您无需手动包含 JAXB 库，只要对象使用了 JAXB 注解进行标注，Spring 就会自动将其转换为 XML 格式。

## 1. 项目依赖

没有额外的依赖，您只需要在 Maven `pom.xml`中包含 Spring MVC。

```xml
<properties>
    <spring.version>3.0.5.RELEASE</spring.version>
</properties>

<dependencies>

    <!-- Spring 3 dependencies -->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-core</artifactId>
        <version>${spring.version}</version>
    </dependency>

    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-web</artifactId>
        <version>${spring.version}</version>
    </dependency>

    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-webmvc</artifactId>
        <version>${spring.version}</version>
    </dependency>

</dependencies>
```

## 2. 模型 + JAXB

一个简单的 POJO 模型并使用 **JAXB 注解**进行了标注，稍后将这个对象转换成 XML 输出。

```java
package com.mkyong.common.model;

import javax.xml.bind.annotation.XmlElement;
import javax.xml.bind.annotation.XmlRootElement;

@XmlRootElement(name = "coffee")
public class Coffee {

    String name;
    int quanlity;

    public String getName() {
        return name;
    }

    @XmlElement
    public void setName(String name) {
        this.name = name;
    }

    public int getQuanlity() {
        return quanlity;
    }

    @XmlElement
    public void setQuanlity(int quanlity) {
        this.quanlity = quanlity;
    }

    public Coffee(String name, int quanlity) {
        this.name = name;
        this.quanlity = quanlity;
    }

    public Coffee() {
    }

}
```

## 3. 控制器

在方法返回值中添加`@ResponseBody`，[Spring 文档](http://web.archive.org/web/20190214225812/http://static.springsource.org/spring/docs/3.0.x/javadoc-api/org/springframework/web/bind/annotation/ResponseBody.html)中没有太多细节。

据我所知，当 Spring 遇到以下情况时：

1. 使用 JAXB 注解的对象
2. 类路径中存在 JAXB 库
3. 启用了`mvc:annotation-driven`
4. 返回方法使用`@ResponseBody`注解

它会自动处理转换。

```java
package com.mkyong.common.controller;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.ResponseBody;
import com.mkyong.common.model.Coffee;

@Controller
@RequestMapping("/coffee")
public class XMLController {

    @RequestMapping(value="{name}", method = RequestMethod.GET)
    public @ResponseBody Coffee getCoffeeInXML(@PathVariable String name) {

        Coffee coffee = new Coffee(name, 100);

        return coffee;

    }

}
```

## 4. `mvc:annotation-driven`

在您的一个 Spring 配置 XML 文件中，启用`mvc:annotation-driven`。

```xml
<beans 
    xmlns:context="http://www.springframework.org/schema/context"
    xmlns:mvc="http://www.springframework.org/schema/mvc" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="
        http://www.springframework.org/schema/beans     
        http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
        http://www.springframework.org/schema/context 
        http://www.springframework.org/schema/context/spring-context-3.0.xsd
        http://www.springframework.org/schema/mvc
        http://www.springframework.org/schema/mvc/spring-mvc-3.0.xsd">

    <context:component-scan base-package="com.mkyong.common.controller" />

    <mvc:annotation-driven />

</beans>
```

**注意**

或者，您可以声明`spring-oxm.jar`依赖并包含以下`MarshallingView`来处理转换。使用此方法，您无需在方法中标注`@ResponseBody`。

```xml
<beans ...>
    <bean class="org.springframework.web.servlet.view.BeanNameViewResolver" />

    <bean id="xmlViewer" 
        class="org.springframework.web.servlet.view.xml.MarshallingView">
        <constructor-arg>
          <bean class="org.springframework.oxm.jaxb.Jaxb2Marshaller">
            <property name="classesToBeBound">
                <list>
                    <value>com.mkyong.common.model.Coffee</value>
                </list>
            </property>
          </bean>
        </constructor-arg>
    </bean>
</beans>
```

## 5. 演示

URL：`http://localhost:8080/spring MVC/rest/coffee/arabica`

![spring mvc and xml example demo](img/897ebdce7b4bf2c9ba797ae3abc90b7a.png "spring-mvc-xml-demo")

## 下载源代码

下载 – [SpringMVC-XML-Example.zip](http://web.archive.org/web/20190214225812/http://www.mkyong.com/wp-content/uploads/2011/07/SpringMVC-XML-Example.zip)（7 KB）

## 参考

1. [Spring MVC 和 Rss 示例](http://web.archive.org/web/20190214225812/http://www.mkyong.com/spring-mvc/spring-3-mvc-and-rss-feed-example/)
2. [mvc:annotation-driven 的 JavaDoc](http://web.archive.org/web/20190214225812/http://static.springsource.org/spring/docs/3.0.x/spring-framework-reference/html/mvc.html#mvc-annotation-driven)
3. [Jaxb2Marshaller JavaDoc](http://web.archive.org/web/20190214225812/http://static.springsource.org/spring-ws/sites/1.5/apidocs/org/springframework/oxm/jaxb/Jaxb2Marshaller.html)
4. [ResponseBody JavaDoc](http://web.archive.org/web/20190214225812/http://static.springsource.org/spring/docs/3.0.x/javadoc-api/org/springframework/web/bind/annotation/ResponseBody.html)

[spring mvc](http://web.archive.org/web/20190214225812/http://www.mkyong.com/tag/spring-mvc/) [spring3](http://web.archive.org/web/20190214225812/http://www.mkyong.com/tag/spring3/) [xml](http://web.archive.org/web/20190214225812/http://www.mkyong.com/tag/xml/)
