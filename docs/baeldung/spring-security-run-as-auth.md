
# Spring Security–运行身份认证

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/spring-security-run-as-auth>

## 1. 概述

在本教程中，我们将通过一个简单的场景来说明如何在 Spring Security 中使用 Run-As 身份验证。

Run-As 的非常高级的解释如下：一个用户可以作为另一个拥有不同特权的主体执行某些逻辑。

## 2. `RunAsManager`

我们需要做的第一件事是设置我们的`GlobalMethodSecurity`并注入一个`RunAsManager`。该管理器负责为临时`Authentication`对象提供额外的特权：

```java
@Configuration
@EnableGlobalMethodSecurity(securedEnabled = true)
public class MethodSecurityConfig extends GlobalMethodSecurityConfiguration {
    @Override
    protected RunAsManager runAsManager() {
        RunAsManagerImpl runAsManager = new RunAsManagerImpl();
        runAsManager.setKey("MyRunAsKey");
        return runAsManager;
    }
}
```

通过覆盖`runAsManager`，我们替换了基类中的默认实现——它只是返回一个`null`。

还要注意`key`属性——框架用它来保护/验证临时`Authentication`对象（通过此管理器创建的），产生的`Authentication`对象是一个`RunAsUserToken`。

## 3. 安全配置

为了验证临时`Authentication`对象，我们将设置一个`RunAsImplAuthenticationProvider`：

```java
@Autowired
public void configureGlobal(AuthenticationManagerBuilder auth) throws Exception {
    ...
    auth.authenticationProvider(runAsAuthenticationProvider());
}

@Bean
public AuthenticationProvider runAsAuthenticationProvider() {
    RunAsImplAuthenticationProvider authProvider = new RunAsImplAuthenticationProvider();
    authProvider.setKey("MyRunAsKey");
    return authProvider;
}
```

我们使用与管理器中相同的密钥来设置此提供者，以便它能够检查`RunAsUserToken`身份验证对象是否使用相同的密钥创建。

## 4. `@Secured`控制器

现在，让我们看看如何使用运行-身份认证替换：

```java
@Controller
@RequestMapping("/runas")
class RunAsController {

    @Secured({ "ROLE_USER", "RUN_AS_REPORTER" })
    @RequestMapping
    @ResponseBody
    public String tryRunAs() {
        Authentication auth = SecurityContextHolder.getContext().getAuthentication();
        return "Current User Authorities inside this RunAS method only " + 
          auth.getAuthorities().toString();
    }
}
```

这里最核心的是新角色——`RUN_AS_REPORTER`。这是 Run-As 功能的触发器——因为前缀的存在，框架会以不同的方式处理它。

当请求通过此逻辑执行时，我们会得到：

*   `tryRunAs()`方法之前的当前用户权限为[`ROLE_USER`]
*   `tryRunAs()`方法内部的当前用户权限为[`ROLE_USER`, `ROLE_RUN_AS_REPORTER`]
*   临时`Authentication`对象仅在`tryRunAS()`方法调用期间替换现有的认证对象

## 5. 服务层

最后，让我们实现实际的逻辑——一个简单的同样受保护的服务层：

```java
@Service
public class RunAsService {

    @Secured({ "ROLE_RUN_AS_REPORTER" })
    public Authentication getCurrentUser() {
        Authentication authentication = 
          SecurityContextHolder.getContext().getAuthentication();
        return authentication;
    }
}
```

请注意：

*   要访问`getCurrentUser()`方法，我们需要`ROLE_RUN_AS_REPORTER`角色
*   所以我们只能在`tryRunAs()`控制器方法中调用`getCurrentUser()`方法

## 6. 前端

接下来，我们将使用一个简单的前端来测试 Run-As 功能：

```java
<html>
<body>
Current user authorities: 
    <span sec:authentication="principal.authorities">user</span>
<br/>
<span id="temp"></span>
<a href="#" onclick="tryRunAs()">Generate Report As Super User</a>

<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
<script type="text/javascript">
function tryRunAs(){
    $.get( "/runas" , function( data ) {
         $("#temp").html(data);
    });
}
</script>
</body>
</html>
```

当用户触发"**以超级用户**身份生成报告"动作时，他们将在临时上下文中获得`ROLE_RUN_AS_REPORTER`权限。

## 7. 结论

在本快速教程中，我们探索了一个使用 Spring Security [Run-As 认证替换](https://web.archive.org/web/20220815034334/https://docs.spring.io/spring-security/site/docs/4.0.3.RELEASE/reference/htmlsingle/#runas)特性的简单示例。

本教程基于 GitHub 上的[代码库](https://web.archive.org/web/20220815034334/https://github.com/eugenp/tutorials/tree/master/spring-security-modules/spring-security-web-rest-custom)。
