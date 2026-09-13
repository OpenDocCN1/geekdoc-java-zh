
# 如何在 JSF 中跳过验证

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/how-to-skip-validation-in-jsf/>

## 问题

参见下面 JSF 的例子：

```java
<h:inputSecret id="password" value="#{user.password}" 
    size="20" required="true" label="Password">
    <f:validateRegex pattern="((?=.*\d).{6,20})" />
</h:inputSecret>

<h:message for="password" style="color:red" />

<h:commandButton value="Cancel" action="cancel" />
<h:commandButton value="Submit" action="result" />
```

如果您单击“取消”按钮，密码验证将被触发，并阻止您继续进入取消页面，这是没有意义的。有没有办法绕过 JSF 的验证？

## 解决办法

要跳过验证，向取消按钮添加`immediate="true"`属性。

```java
<h:inputSecret id="password" value="#{user.password}" 
    size="20" required="true" label="Password">
</h:inputSecret>

<h:message for="password" style="color:red" />

<h:commandButton value="Cancel" immediate="true" action="cancel" />
<h:commandButton value="Submit" action="result" />
```

[jsf2](http://web.archive.org/web/20190116132727/http://www.mkyong.com/tag/jsf2/) [validation](http://web.archive.org/web/20190116132727/http://www.mkyong.com/tag/validation/)

![](img/1355d307ad31f424033effb012051516.png)
