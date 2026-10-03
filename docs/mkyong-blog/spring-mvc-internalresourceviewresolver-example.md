
# Spring MVC InternalResourceViewResolver 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/spring-mvc-internalresourceviewresolver-example/>

在 Spring MVC 中，`InternalResourceViewResolver`用于根据预定义的 URL 模式解析“内部资源视图”（简单来说，就是最终输出，JSP 或 HTML 页面）。此外，它允许您为视图名称添加一些预定义的前缀或后缀（前缀 + 视图名称 + 后缀），并生成最终的视图页面 URL。

**什么是内部资源视图？**

在 Spring MVC 或任何 Web 应用中，为了遵循良好实践，通常建议将整个视图或 JSP 文件放在 `WEB-INF` 文件夹下，以防止通过手动输入的 URL 直接访问。这些位于 `WEB-INF` 文件夹下的视图被称为内部资源视图，因为它们只能由 Servlet 或 Spring 的控制器类访问。

以下示例显示了 `InternalResourceViewResolver` 的工作方式：

## 1. 控制器

一个返回视图的控制器类，视图名为 `WelcomePage`。

```java
//...
public class WelcomeController extends AbstractController{

	@Override
	protected ModelAndView handleRequestInternal(HttpServletRequest request,
		HttpServletResponse response) throws Exception {

		ModelAndView model = new ModelAndView("WelcomePage");

		return model;
	}
}
```

## 2. InternalResourceViewResolver

在 Spring 的 Bean 配置文件中注册 `InternalResourceViewResolver` Bean。

```java
<beans
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">

   <bean
   class="org.springframework.web.servlet.mvc.support.ControllerClassNameHandlerMapping" />

	<!-- 注册 Bean -->
	<bean class="com.mkyong.common.controller.WelcomeController" />

	<bean id="viewResolver"
    	      class="org.springframework.web.servlet.view.InternalResourceViewResolver" >
              <property name="prefix">
                  <value>/WEB-INF/pages/</value>
               </property>
              <property name="suffix">
                 <value>.jsp</value>
              </property>
        </bean>

</beans>
```

现在，Spring 将以如下方式解析视图名称 `WelcomePage`：

> 前缀 + 视图名 + 后缀 = `/WEB-INF/pages/WelcomePage.jsp`

## 下载源代码

下载 – [SpringMVC-InternalResourceViewResolver-Example.zip](http://web.archive.org/web/20220907153704/http://www.mkyong.com/wp-content/uploads/2010/08/SpringMVC-InternalResourceViewResolver-Example.zip)（7 KB）

## 参考

1. [InternalResourceViewResolver 文档](http://web.archive.org/web/20220907153704/http://static.springsource.org/spring/docs/2.5.6/api/org/springframework/web/servlet/view/InternalResourceViewResolver.html)

<input type="hidden" id="mkyong-current-postId" value="6538">
