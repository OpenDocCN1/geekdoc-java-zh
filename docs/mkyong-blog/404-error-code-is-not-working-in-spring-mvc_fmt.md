
# 404 错误代码在 Spring MVC 中不起作用

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-mvc/404-error-code-is-not-working-in-spring-mvc/>

## 问题

在 Spring MVC 应用程序中，404 错误代码配置正确。请参见下面的 `web.xml` 片段。

*文件：`web.xml`*

```java
<web-app ...>

  <servlet>
    <servlet-name>mvc-dispatcher</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
  </servlet>

  <servlet-mapping>
    <servlet-name>mvc-dispatcher</servlet-name>
    <url-pattern>*.htm</url-pattern>
  </servlet-mapping>

  //...
  <error-page>
    <error-code>404</error-code>
    <location>/WEB-INF/pages/404.htm</location>
  </error-page>

</web-app>
```

然而，当用户访问任何不存在的资源时，它将**显示一个空白页面，而不是 `404.htm`**。

## 解决办法

404 错误代码配置正确，但会导致“**`servlet` 容器和 Spring 的 `DispatcherServlet` 之间的扩展处理冲突**”。要解决这个问题，请尝试将 `404.htm` 更改为其他文件扩展名，例如 `404.jsp`。

*文件：`web.xml`*

```java
<web-app ...>

  <servlet>
    <servlet-name>mvc-dispatcher</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
  </servlet>

  <servlet-mapping>
    <servlet-name>mvc-dispatcher</servlet-name>
    <url-pattern>*.htm</url-pattern>
  </servlet-mapping>

  //...
  <error-page>
    <error-code>404</error-code>
    <location>/WEB-INF/pages/404.jsp</location>
  </error-page>

</web-app>
```

现在，当用户访问任何不存在的资源时，它会转到 `404.jsp` 页面。
