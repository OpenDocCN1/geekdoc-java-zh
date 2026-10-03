
# Spring MVC 重定向视图示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/spring-mvc-redirectview-example/>

在 Spring MVC 中，`org.springframework.web.servlet.view.RedirectView`，顾名思义，视图重定向到另一个绝对的、上下文相对的或当前请求相对的 URL。在本教程中，我们向您展示了一个使用`RedirectView`类的完整示例。

## 1. 重定向视图

声明一个`RedirectView` bean，命名为`DummyRedirect`，重定向到 URL`DummyRedirectPage.htm`。

*文件：`spring-views.xml`*

```java
<beans ...>
   <!-- Redirect view -->
   <bean id="DummyRedirect"
	   class="org.springframework.web.servlet.view.RedirectView">
           <property name="url" value="DummyRedirectPage.htm" />
    </bean>
</beans>
```

## 2. 控制器

一个返回名为`DummyRedirect`的`ModelAndView`的控制器，它是一个`RedirectView`视图。

*文件：`DummyController.java`*

```java
package com.mkyong.common.controller;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import org.springframework.web.servlet.ModelAndView;
import org.springframework.web.servlet.mvc.AbstractController;

public class DummyController extends AbstractController{

	@Override
	protected ModelAndView handleRequestInternal(HttpServletRequest request,
		HttpServletResponse response) throws Exception {

		return new ModelAndView("DummyRedirect");

	}
}
```

## 3. Spring 配置

声明了所有映射。

*文件：`mvc-dispatcher-servlet.xml`*

```java
<beans ...>

  <bean
  class="org.springframework.web.servlet.mvc.support.ControllerClassNameHandlerMapping" />

   <bean class="com.mkyong.common.controller.DummyController" />

   <bean class="org.springframework.web.servlet.handler.SimpleUrlHandlerMapping">
       <property name="mappings">
            <props>
                <prop key="/DummyRedirectPage.htm">dummyRedirectController</prop>
            </props>
        </property>
    </bean>

    <bean id="dummyRedirectController"
         class="org.springframework.web.servlet.mvc.ParameterizableViewController">
	 <property name="viewName" value="DummyPage" />
    </bean>

    <bean id="viewResolver"
          class="org.springframework.web.servlet.view.InternalResourceViewResolver" >
          <property name="prefix">
                <value>/WEB-INF/pages/</value>
           </property>
          <property name="suffix">
                <value>.jsp</value>
          </property>
          <property name="order" value="1" />
     </bean>

     <bean class="org.springframework.web.servlet.view.XmlViewResolver">
	   <property name="location">
	       <value>/WEB-INF/spring-views.xml</value>
	   </property>
	   <property name="order" value="0" />
     </bean>

</beans>
```

## 4. 它是如何工作的？

1. 访问网址`http://localhost:8080/SpringMVC/dummy.htm`。

2. `ControllerClassNameHandlerMapping`匹配了`DummyController`并返回一个`ModelAndView("DummyRedirect")`。

3. `XmlViewResolver`匹配后返回一个 URL`DummyRedirectPage.htm`。

```java
<bean id="DummyRedirect"
	   class="org.springframework.web.servlet.view.RedirectView">
       <property name="url" value="DummyRedirectPage.htm" />
    </bean>
```

4. `SimpleUrlHandlerMapping`匹配后返回一个控制器`dummyRedirectController`。

```java
<bean class="org.springframework.web.servlet.handler.SimpleUrlHandlerMapping">
        <property name="mappings">
            <props>
                <prop key="/DummyRedirectPage.htm">dummyRedirectController</prop>
            </props>
        </property>
    </bean>
```

5. `ParameterizableViewController`控制器`dummyRedirectController`返回一个名为`DummyPage`的视图。

```java
<bean id="dummyRedirectController"
        class="org.springframework.web.servlet.mvc.ParameterizableViewController">
	<property name="viewName" value="DummyPage" />
    </bean>
```

6. `InternalResourceViewResolver`对其进行匹配并返回最终的 JSP 页面，`/WEB-INF/pages/DummyPage.jsp`。

```java
<bean id="viewResolver"
	   class="org.springframework.web.servlet.view.InternalResourceViewResolver" >
          <property name="prefix">
              <value>/WEB-INF/pages/</value>
           </property>
          <property name="suffix">
             <value>.jsp</value>
          </property>
          <property name="order" value="1" />
    </bean>
```

7. URL 更改为`http://localhost:8080/SpringMVC/DummyRedirectPage.htm`。

**Redirect 前缀**

另外，如果你配置了`InternalResourceViewResolver`，你可以在视图名称中使用`redirect:`前缀来解析重定向视图。例如，

*文件：`DummyController.java`*

```java
//...
public class DummyController extends AbstractController{

	@Override
	protected ModelAndView handleRequestInternal(HttpServletRequest request,
		HttpServletResponse response) throws Exception {

		return new ModelAndView("redirect:DummyRedirectPage.htm");

	}
}
```

**使用场景**

其中一个使用场景是应用`RedirectView`概念来解决 [Spring MVC 中的重复表单提交](http://web.archive.org/web/20190217092728/http://www.mkyong.com/spring-mvc/handling-duplicate-form-submission-in-spring-mvc/)。

## 下载源代码

下载它 – [SpringMVC-RedirectView-Example.zip](http://web.archive.org/web/20190217092728/http://www.mkyong.com/wp-content/uploads/2010/08/SpringMVC-RedirectView-Example.zip) (7KB)

## 参考

1. [RedirectView Javadoc](http://web.archive.org/web/20190217092728/http://static.springsource.org/spring/docs/2.5.x/api/org/springframework/web/servlet/view/RedirectView.html)

2. [SpringSource RedirectView 解释](http://web.archive.org/web/20190217092728/http://static.springsource.org/spring/docs/2.0.x/reference/mvc.html#mvc-redirecting)

3. [到底如何使用 RedirectView？](http://web.archive.org/web/20190217092728/http://forum.springsource.org/archive/index.php/t-42435.html)

[spring mvc](http://web.archive.org/web/20190217092728/http://www.mkyong.com/tag/spring-mvc/)
