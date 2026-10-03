
# Spring Security：检查用户是否来自“记住我”cookie

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring-security/spring-security-check-if-user-is-from-remember-me-cookie/>

这个 Spring 安全示例向您展示了如何检查一个用户是否从“remember me”cookie 登录。

```java
private boolean isRememberMeAuthenticated() {

    Authentication authentication = 
        SecurityContextHolder.getContext().getAuthentication();
    if (authentication == null) {
        return false;
    }

    return RememberMeAuthenticationToken.class.isAssignableFrom(authentication.getClass());
}

@RequestMapping(value = "/admin/update**", method = RequestMethod.GET)
public ModelAndView updatePage() {

    ModelAndView model = new ModelAndView();

    if (isRememberMeAuthenticated()) {	
        model.setViewName("/login");	
    } else {
        model.setViewName("update");
    }

    return model;

}
```

在 Spring 安全标记中，您可以这样编码：

```java
<%@taglib prefix="sec" uri="http://www.springframework.org/security/tags"%>
<%@page session="true"%>
<html>
<body>

    <sec:authorize access="isRememberMe()">
        <h2># This user is login by "Remember Me Cookies".</h2>
    </sec:authorize>

    <sec:authorize access="isFullyAuthenticated()">
        <script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>

        <script>
            (adsbygoogle = window.adsbygoogle || []).push({});
        </script>
        <h2># This user is login by username / password.</h2>
    </sec:authorize>

</body>
</html>
```

**Note**

`isRememberMe()` – 如果当前主体是“记住我”用户，则返回 `true`。

`isFullyAuthenticated()` – 如果用户不是匿名用户或“记住我”用户，则返回 `true`。

## 参考

1. [Spring Security，Spring EL for expression 概述](http://web.archive.org/web/20190304003401/http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#overview)
2. [AuthenticationTrustResolverImpl JavaDoc](http://web.archive.org/web/20190304003401/http://docs.spring.io/spring-security/site/docs/3.0.8.RELEASE/apidocs/org/springframework/security/authentication/AuthenticationTrustResolverImpl.html)
3. [春安记得我的例子](http://web.archive.org/web/20190304003401/http://www.mkyong.com/spring-security/spring-security-remember-me-example/)

[spring security](http://web.archive.org/web/20190304003401/http://www.mkyong.com/tag/spring-security/) ![](img/c363498b81236b7380a66cb83e858bfa.png)
