

# 如何在 Wicket 中获取 Web 应用程序的根上下文

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/wicket/how-do-get-root-context-of-a-web-application-in-wicket/>

在 Wicket 中，您可以使用下面的方法来获取项目的“根上下文”。

```java
WebApplication.get().getServletContext().getServletContextName()
```

举个例子：

```java
public static String getRootContext() {
    String rootContext = "";

    WebApplication webApplication = WebApplication.get();
    if (webApplication != null) {
        ServletContext servletContext = webApplication.getServletContext();
        if (servletContext != null) {
            rootContext = servletContext.getServletContextName();
        } else {
            // do nothing
        }
    } else {
        // do nothing
    }

    return rootContext;
}
```

[context](http://web.archive.org/web/20190114230103/http://www.mkyong.com/tag/context/) [wicket](http://web.archive.org/web/20190114230103/http://www.mkyong.com/tag/wicket/)

