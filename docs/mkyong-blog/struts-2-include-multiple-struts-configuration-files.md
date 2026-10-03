
# Struts 2–包含多个 Struts 配置文件

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-include-multiple-struts-configuration-files/>

Struts 2 带有“`include file`”特性，将多个 Struts 配置文件包含到一个单元中。

## 单个 Struts 配置文件

让我们看一个糟糕的 Struts 2 配置示例。

`struts.xml`

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>

<package name="default" namespace="/" extends="struts-default">
</package>

<package name="audit" namespace="/audit" extends="struts-default">
	<action name="WelcomeAudit">
		<result>pages/welcome_audit.jsp</result>
	</action>
</package>

<package name="user" namespace="/user" extends="struts-default">
	<action name="WelcomeUser">
		<result>pages/welcome_user.jsp</result>
	</action>
</package>

</struts>
```

在上面的 Struts 配置文件中，它将所有的“用户”和“审计”设置放在一个文件中，这是不推荐的，必须避免。您应该将这个`struts.xml`文件分成更多更小的模块相关部分。

不要认为这是一个案例研究，它确实发生在[真实生活中](http://web.archive.org/web/20190214223406/http://www.mkyong.com/struts/struts-multiple-configuration-files-example/)。我见过许多 Struts 1 或 2 开发者将所有内容都分组到一个 Struts 配置文件中。事实上，许多人仍然不知道 Struts 的`include file`特性。

## 多个 Struts 配置文件

在 Struts 2 中，您应该总是为每个模块分配一个 Struts 配置文件。在这种情况下，您可以创建三个文件：

1. `struts-audit.xml`–将所有审计模块设置放在这里。
2. `struts-user.xml`–将所有用户模块设置放在这里。
3. `struts.xml`–使用默认设置并包含`struts-audit.xml`和`struts-user.xml`。

`struts-audit.xml`

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>

<package name="audit" namespace="/audit" extends="struts-default">
	<action name="WelcomeAudit">
		<result>pages/welcome_audit.jsp</result>
	</action>
</package>

</struts>
```

`struts-user.xml`

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>

<package name="user" namespace="/user" extends="struts-default">
	<action name="WelcomeUser">
		<result>pages/welcome_user.jsp</result>
	</action>
</package>

</struts>
```

`struts.xml`

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts PUBLIC
"-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
"http://struts.apache.org/dtds/struts-2.0.dtd">

<struts>

<package name="default" namespace="/" extends="struts-default">
</package>

<include file="user/struts-user.xml"></include>
<include file="audit/struts-audit.xml"></include>

</struts>
```

看看文件夹结构是什么样的

![Struts 2 multiple config file folder structure](img/680f2c4b0aba7c8f310c3c3b6b1ec5c7.png "struts2-mutiple-config-file")

下载此示例 – [Struts2-Multiple-Struts-Config-Files-Example.zip](http://web.archive.org/web/20190214223406/http://www.mkyong.com/wp-content/uploads/2010/06/Struts2-Mutiple-Struts-Config-Files-Example.zip)

## 参考

1. [http://www.mkyong.com/struts/struts-multiple-configuration-files-example/](http://web.archive.org/web/20190214223406/http://www.mkyong.com/struts/struts-multiple-configuration-files-example/)
2. [http://www.mkyong.com/struts2/struts-2-namespace-configuration-example-and-explanation/](http://web.archive.org/web/20190214223406/http://www.mkyong.com/struts2/struts-2-namespace-configuration-example-and-explanation/)

[configuration file](http://web.archive.org/web/20190214223406/http://www.mkyong.com/tag/configuration-file/) [struts2](http://web.archive.org/web/20190214223406/http://www.mkyong.com/tag/struts2/)
