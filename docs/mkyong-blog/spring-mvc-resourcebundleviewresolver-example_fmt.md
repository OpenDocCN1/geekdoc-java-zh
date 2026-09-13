
# Spring MVC ResourceBundleViewResolver 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/spring-mvc-resourcebundleviewresolver-example/>

在 Spring MVC 中，`ResourceBundleViewResolver`用于解析“基于视图 beans 中名为”的视图。属性”文件。

默认情况下，`ResourceBundleViewResolver`将从文件`views.properties`中加载视图 beans，该文件位于项目类路径的根目录下。但是，这个位置可以通过`basename`属性覆盖，例如：

```java
<beans ...>
	<bean class="org.springframework.web.servlet.view.ResourceBundleViewResolver">
		<property name="basename" value="spring-views" />
	</bean>
</beans>
```

在上面的例子中，它从`spring-views.properties`加载视图 beans，它位于项目类路径的根。

**注意**

`ResourceBundleViewResolver`具有从不同资源包中为不同区域设置加载视图 beans 的能力，但这种用例很少需要。

`ResourceBundleViewResolver`示例向您展示了它的工作原理：

## 1. 控制器

一个控制器类，返回一个视图，名为`WelcomePage`。

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

## 2. ResourceBundleViewResolver

在 Spring 的 bean 配置文件中注册`ResourceBundleViewResolver`，将默认的视图 bean 位置更改为`spring-views.properties`。

```java
<beans 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans 
	http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">

  <bean 
  class="org.springframework.web.servlet.mvc.support.ControllerClassNameHandlerMapping" />

	<!-- Register the bean -->
	<bean class="com.mkyong.common.controller.WelcomeController" />

	<bean class="org.springframework.web.servlet.view.ResourceBundleViewResolver">
		<property name="basename" value="spring-views" />
	</bean>

</beans>
```

## 3. 查看 beans

将每个视图 bean 声明为普通的资源包样式（键和消息），其中：

1. `WelcomePage`是要匹配的视图名称。
2. `.`（类）是视图的类型。
3. `.url`是视图的 url 位置。

*文件：`spring-views.properties`*

```java
WelcomePage.(class)=org.springframework.web.servlet.view.JstlView
WelcomePage.url=/WEB-INF/pages/WelcomePage.jsp
```

**注意**

将此`spring-views.properties`文件放在项目类路径上。

**它是如何工作的？**

当控制器返回视图名称`WelcomePage`时，`ResourceBundleViewResolver`将在`spring-views.properties`文件中查找以`WelcomePage`开头的键，并将对应的视图 URL`/WEB-INF/pages/WelcomePage.jsp`返回给`DispatcherServlet`。

## 下载源代码

下载它 – [SpringMVC-ResourceBundleViewResolver-Example.zip](http://web.archive.org/web/20190210095000/http://www.mkyong.com/wp-content/uploads/2010/08/SpringMVC-ResourceBundleViewResolver-Example.zip)（7 KB）

## 参考

1. [ResourceBundleViewResolver 文档](http://web.archive.org/web/20190210095000/http://static.springsource.org/spring/docs/2.5.x/api/org/springframework/web/servlet/view/ResourceBundleViewResolver.html)

[spring mvc](http://web.archive.org/web/20190210095000/http://www.mkyong.com/tag/spring-mvc/)
