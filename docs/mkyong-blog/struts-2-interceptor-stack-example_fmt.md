
# Struts 2 拦截器堆栈示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts2/struts-2-interceptor-stack-example/>

通常，同一组拦截器可以应用于不同的动作类，例如：

```
<package name="default" namespace="/" extends="struts-default">

    <action name="checkInAction" 
	class="com.mkyong.common.action.CheckInAction" >
	<interceptor-ref name="timer"/>
        <interceptor-ref name="logger"/>
	<interceptor-ref name="defaultStack" />
	<result name="success">pages/checkIn.jsp</result>
    </action>

    <action name="checkOutAction" 
	class="com.mkyong.common.action.CheckOutAction" >
	<interceptor-ref name="timer"/>
        <interceptor-ref name="logger"/>
	<interceptor-ref name="defaultStack" />
	<result name="success">pages/checkOut.jsp</result>
    </action>

</package>
```

在上述情况下，它有许多重复的工作，根本不能重用。

幸运的是，Struts 2 附带了拦截器栈，允许开发人员将一组拦截器组合成一个名为“栈名”的单元，动作可以通过“栈名”引用它。

**最佳实践**

建议始终将同一组拦截器分组到拦截器栈中，以消除重复工作，并提高项目的可重用性。

```
<package name="default" namespace="/" extends="struts-default">

     <interceptors>
       	<interceptor-stack name="defaultStackWithLog">
             <interceptor-ref name="timer"/>
             <interceptor-ref name="logger"/>
	     <interceptor-ref name="defaultStack" />
        </interceptor-stack>
    </interceptors>

    <action name="checkInAction" 
	class="com.mkyong.common.action.CheckInAction" >
	<interceptor-ref name="defaultStackWithLog"/>
	<result name="success">pages/checkIn.jsp</result>
    </action>

    <action name="checkOutAction" 
	class="com.mkyong.common.action.CheckOutAction" >
	<interceptor-ref name="defaultStackWithLog"/>
	<result name="success">pages/checkOut.jsp</result>
    </action>

</package>
```

在上面更新的示例中，声明了一个拦截器堆栈，名为`defaultStackWithLog`，它包括`timer`、`logger`和`defaultStack`拦截器，并通过`interceptor-ref`元素将其引用为普通拦截器。

## 参考

1. [Struts 2 拦截器文档](http://web.archive.org/web/20190214233721/http://struts.apache.org/2.1.8/docs/interceptors.html)

[interceptor](http://web.archive.org/web/20190214233721/http://www.mkyong.com/tag/interceptor/) [struts2](http://web.archive.org/web/20190214233721/http://www.mkyong.com/tag/struts2/)
