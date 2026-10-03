
# Struts 2 – 开发模式示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-development-mode-example/>

在 Struts 2 开发中，这应该是要学习的第一个可配置值。为了启用 Struts 2 开发模式，您可以通过给予**自动配置和属性文件重新加载**和**额外的日志记录和调试**特性来显著提高您的 Struts 2 开发速度。

自动重新加载功能确实是一个便捷的特性。每次我在属性文件或 XML 配置文件中做出更改时，应用程序无需重新启动即可生效。默认情况下，Struts 2 开发模式是禁用的。

## 启用 Struts 2 开发模式

在 struts 属性文件或 XML 配置文件中将`struts.devMode`值设置为`true`。

**struts.properties**

```java
struts.devMode = true
```

**struts.xml**

```java
<struts>
    <constant name="struts.devMode" value="true" />
</struts>
```

## 禁用 Struts 2 开发模式

在 struts 属性文件或 XML 配置文件中将`struts.devMode`设置为`false`。

**struts.properties**

```java
struts.devMode = false
```

**struts.xml**

```java
<struts>
    <constant name="struts.devMode" value="false" />
</struts>
```

开发模式仅适用于开发或调试环境。在生产环境中，**您必须禁用它**。它会对性能产生显著影响，因为整个应用程序配置和属性文件会在每次请求时重新加载，同时还会提供大量额外的日志和调试信息。在提交 Struts 配置文件之前，请确保开发模式已关闭。我见过很多意外提交的情况——提交时启用了开发模式，然后有人直接抓取源代码用于 QA 环境。坦白说，QA 很少会做性能测试，他们只确保功能正常，最终导致启用了开发模式的应用程序被部署到生产环境。猜猜结果如何？您很快就会接到客户打来的大量抱怨电话……

## 参考

1. [Struts 2 开发模式文档](http://web.archive.org/web/20190225092948/http://struts.apache.org/2.1.8/docs/devmode.html)

[struts2](http://web.archive.org/web/20190225092948/http://www.mkyong.com/tag/struts2/)
