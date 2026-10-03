
# 如何在 JSF 添加全局导航规则？

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/how-to-add-a-global-navigation-rule-in-jsf/>

## 问题

全局导航规则是适用于所有页面的规则。例如，应用允许每个页面访问“注销”导航规则。有办法在 JSF 配置吗？

## 解决办法

在 JSF 中，导航规则支持通配符，您可以使用“`*`”来指定适用于所有页面的导航规则。

```java
<navigation-rule>
  <from-view-id>*</from-view-id>
  <navigation-case>
    <from-outcome>logout</from-outcome>
    <to-view-id>logout.xhtml</to-view-id>
  </navigation-case>
</navigation-rule>
```

在本例中，您的 Web 应用程序中的所有页面都能够访问“`logout`”导航。

看另一个例子：

```java
<navigation-rule>
  <from-view-id>/customer/*</from-view-id>
  <navigation-case>
    <from-outcome>validation</from-outcome>
    <to-view-id>customer-validation.xhtml</to-view-id>
  </navigation-case>
</navigation-rule>
```

这条规则适用于所有以前缀`/customer/`开头的页面。

## 注意

“`*`”通配符功能在 JSF 中有所限制，因为只能使用一个“`*`”，并且它必须位于`from-view-id`字符串的末尾。例如：

它可以正常工作：

```java
<from-view-id>/customer/*</from-view-id>
```

但以下写法都不适用：

```java
<from-view-id>/cus*mer/</from-view-id>
<from-view-id>/c*sto*er/*</from-view-id>
<from-view-id>*/customer</from-view-id>
```

[jsf](http://web.archive.org/web/20190223132221/http://www.mkyong.com/tag/jsf/) [jsf2](http://web.archive.org/web/20190223132221/http://www.mkyong.com/tag/jsf2/) [navigation rule](http://web.archive.org/web/20190223132221/http://www.mkyong.com/tag/navigation-rule/)
