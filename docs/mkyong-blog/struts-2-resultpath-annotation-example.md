
# Struts 2 `@ResultPath` 注释示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-resultpath-annotation-example/>

在 Struts 2 中，`@ResultPath` 注释用于控制 Struts 2 将在哪里找到存储的结果或 JSP 页面。默认情况下，它会从 `WEB-INF/content/` 文件夹中找到结果页面。

不知道为何 Struts 2 注释将 `WEB-INF/content/` 设置为默认文件夹，但大多数应用程序不会将结果页面放在这个 `WEB-INF/content/` 文件夹中。这只是 Struts 2 的约定，而不是标准的文件夹结构。我更希望 Struts 2 将根路径作为默认文件夹。

## `@ResultPath` 示例

### 1. 默认结果路径

一个登录动作类，设置为 `/User` 命名空间，重定向到 `pages/login.jsp` 页面。

假设 `Struts2Example` 是您的上下文 servlet 名称。

```java
@Namespace("/User")
@Result(name="success", location="pages/login.jsp")
public class LoginAction extends ActionSupport {
}
```

访问它：

```java
http://localhost:8080/Struts2Example/User/login.action
```

Struts 2 将从默认位置找到 `login.jsp` 结果页面：

```java
/Struts2Example/WEB-INF/content/User/pages/login.jsp
```

### 2. 自定义结果路径

如果您 JSP 结果页面存储在其他位置，您可以使用 `@ResultPath` 注释对其进行更改。

```java
@Namespace("/User")
@ResultPath(value="/")
@Result(name="success", location="pages/login.jsp")
public class LoginAction extends ActionSupport {
}
```

再次访问它：

```java
http://localhost:8080/Struts2Example/User/login.action
```

现在，Struts 2 将从不同的位置找到 `login.jsp` 结果页面：

```java
/Struts2Example/User/pages/login.jsp
```

## 全局 `@ResultPath`

`@ResultPath` 只适用于类级别。要全局应用它，您可以在 `struts.xml` 文件中配置它。

**struts.xml**

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">
<struts>
    <constant name="struts.convention.result.path" value="/"/>
</struts>
```

## 参考

1. [Struts 2 `@ResultPath` 注释文档](http://web.archive.org/web/20190302163359/http://struts.apache.org/2.1.8.1/docs/convention-plugin.html#ConventionPlugin-ResultPathannotation)

[struts2](http://web.archive.org/web/20190302163359/http://www.mkyong.com/tag/struts2/)
