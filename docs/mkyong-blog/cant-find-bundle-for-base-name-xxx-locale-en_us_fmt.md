
# 找不到基本名称 xxx，区域设置 en_US 的包

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/cant-find-bundle-for-base-name-xxx-locale-en_us/>

## 问题

在 JSF Web 应用中，在应用层加载一个消息包，如下：

**faces-config.xml**

```java
<?xml version="1.0" encoding="UTF-8"?>
<faces-config
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
    http://java.sun.com/xml/ns/javaee/web-facesconfig_2_0.xsd"
    version="2.0">
    <application>
        <message-bundle>
            com.mkyong.payment_error
        </message-bundle>
    </application>
</faces-config>
```

页面渲染时，遇到“找不到基本名称`com.mkyong.payment_error`、区域设置`en_US`的包”错误。

## 解决办法

显然，包或属性文件（`com.mkyong.payment_error.properties`）丢失了，请确保名称匹配，并正确放置在资源文件夹中。

## Eclipse 用户

此问题通常发生在 Eclipse IDE 环境中，因为它默认不会复制`.properties`文件扩展名。因此，请确保属性文件存在于运行时的`classes`文件夹中，并且 Web 应用可以找到该文件。

[jsf2](http://web.archive.org/web/20190224212715/http://www.mkyong.com/tag/jsf2/)

![](img/3e072f25f11cc9085d56f53f648f0401.png)
