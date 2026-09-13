

# 如何将 Wicket 改为部署模式？

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/wicket/how-to-change-wicket-to-deployment-mode/>

## 问题

默认情况下，Wicket 运行在开发模式下。如何切换到生产模式？

```java
WebApplication:759 - [WicketApplication] Started Wicket version 1.4.17 in development mode
********************************************************************
*** WARNING: Wicket is running in DEVELOPMENT mode.              ***
***                               ^^^^^^^^^^^                    ***
*** Do NOT deploy to your live server(s) without changing this.  ***
*** See Application#getConfigurationType() for more information. ***
********************************************************************
```

## 解决办法

据我所知，有两种方法可以将 Wicket 更改为在部署（生产）模式下运行：

```java
WebApplication:759 - [WicketApplication] Started Wicket version 1.4.17 in deployment mode
```

## 1. `web.xml`

第一种方法是在 `web.xml` 中添加一个“配置”上下文参数。

*文件：`web.xml`*

```xml
<web-app ...>

    <context-param>
        <param-name>configuration</param-name>
        <param-value>deployment</param-value>
    </context-param>

    ...
</web-app>
```

## 2. Wicket `getConfigurationType()`

第二种方法是覆盖 Wicket 应用程序的 `getConfigurationType()` 方法。

*文件：Wicket 应用程序类*

```java
import org.apache.wicket.Application;
import org.apache.wicket.protocol.http.WebApplication;

public class WicketApplication extends WebApplication {

    @Override
    public String getConfigurationType() {

        return Application.DEPLOYMENT;

    }
}
```

**注意**

Wicket 应用程序始终具有最高优先级。例如，如果 `web.xml` 为“development”，而 Wicket 应用程序为“deployment”，Wicket 将以“deployment”模式运行。

[deployment](http://web.archive.org/web/20190309231822/http://www.mkyong.com/tag/deployment/) [wicket](http://web.archive.org/web/20190309231822/http://www.mkyong.com/tag/wicket/)

