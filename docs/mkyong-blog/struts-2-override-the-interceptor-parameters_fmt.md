
# Struts 2 覆盖了拦截器参数

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-override-the-interceptor-parameters/>

在 Struts 2 中，您可以通过通用的`<param>`标记来设置或覆盖拦截器参数。参见下面的例子：

```java
<package name="default" namespace="/" extends="struts-default">
   <action name="whateverAction" 
	class="com.mkyong.common.action.WhateverAction" >
	<interceptor-ref name="workflow">
		<param name="excludeMethods">whateverMethod</param>
	</interceptor-ref>
	<result name="success">pages/whatever.jsp</result>
   </action>		
</package>
```

然而，在上面的代码片段中，action 类被声明为它自己的拦截器，这将导致继承`defaultStack`拦截器的立即丢失。

如果您想保留`defaultStack`拦截器，并覆盖工作流的`excludeMethods`参数，该怎么办？没问题，试试这个：

```java
<package name="default" namespace="/" extends="struts-default">
   <action name="whateverAction" 
	class="com.mkyong.common.action.WhateverAction" >
	<interceptor-ref name="defaultStack">
		<param name="workflow.excludeMethods">whateverMethod</param>
	</interceptor-ref>
	<result name="success">pages/whatever.jsp</result>
   </action>		
</package>
```

上面的代码片段将保留`defaultStack`拦截器，并覆盖工作流参数。

## 参考

1. [Struts 2 拦截器文档](http://web.archive.org/web/20190214225208/http://struts.apache.org/2.1.8/docs/interceptors.html)
2. [Struts 2 工作流拦截器文档](http://web.archive.org/web/20190214225208/http://struts.apache.org/2.0.14/docs/workflow-interceptor.html)

[interceptor](http://web.archive.org/web/20190214225208/http://www.mkyong.com/tag/interceptor/) [struts2](http://web.archive.org/web/20190214225208/http://www.mkyong.com/tag/struts2/)
