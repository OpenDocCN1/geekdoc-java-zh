
# 在 Spring MVC 中配置处理程序映射优先级

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/configure-the-handler-mapping-priority-in-spring-mvc/>

通常，在 Spring MVC 开发中，您可能会混合使用多个处理程序映射策略。

例如，使用[`ControllerClassNameHandlerMapping`](http://web.archive.org/web/20190214230856/http://www.mkyong.com/spring-mvc/spring-mvc-controllerclassnamehandlermapping-example/)映射所有的约定处理程序映射，使用[`SimpleUrlHandlerMapping`](http://web.archive.org/web/20190214230856/http://www.mkyong.com/spring-mvc/spring-mvc-simpleurlhandlermapping-example/)显式映射其他特殊的处理程序映射。

```java
<beans ...>

  <bean class="org.springframework.web.servlet.handler.SimpleUrlHandlerMapping">
    <property name="mappings">
      <value>
        /index.htm=welcomeController
        /welcome.htm=welcomeController
        /main.htm=welcomeController
        /home.htm=welcomeController
      </value>
    </property>
    <property name="order" value="0" />
  </bean>

  <bean class="org.springframework.web.servlet.mvc.support.ControllerClassNameHandlerMapping">
    <property name="caseSensitive" value="true" />
    <property name="order" value="1" />
  </bean>

  <bean id="welcomeController"
    class="com.mkyong.common.controller.WelcomeController" />

  <bean class="com.mkyong.common.controller.HelloGuestController" />

</beans>
```

在上述情况下，指定处理程序映射优先级很重要，这样就不会导致冲突。您可以通过`order`属性设置优先级，其中顺序值越低优先级越高。

## 下载源代码

Download it – [`SpringMVC-HandlerMapping-Priority-Example.zip`](http://web.archive.org/web/20190214230856/http://www.mkyong.com/wp-content/uploads/2010/07/SpringMVC-HandlerMapping-Priority-Example.zip)（8 KB）

## 参考

1. [`ControllerClassNameHandlerMapping`示例](http://web.archive.org/web/20190214230856/http://www.mkyong.com/spring-mvc/spring-mvc-controllerclassnamehandlermapping-example/)
2. [`SimpleUrlHandlerMapping`示例](http://web.archive.org/web/20190214230856/http://www.mkyong.com/spring-mvc/spring-mvc-simpleurlhandlermapping-example/)

[spring mvc](http://web.archive.org/web/20190214230856/http://www.mkyong.com/tag/spring-mvc/)

![](img/8c64e470f3ee14780fbb5c55adc79994.png)
