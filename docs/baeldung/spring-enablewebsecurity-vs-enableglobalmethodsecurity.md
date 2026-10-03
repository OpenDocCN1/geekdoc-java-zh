
# `@EnableWebSecurity` 与 `@EnableGlobalMethodSecurity` 对比

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/spring-enablewebsecurity-vs-enableglobalmethodsecurity>

## 1. 概览

我们可能希望在 Spring Boot 应用程序的不同路径中应用多个安全过滤器。

在本教程中，我们将了解两种定制安全性的方法——通过使用 [`@EnableWebSecurity`](https://web.archive.org/web/20220628132448/https://docs.spring.io/spring-security/site/docs/current/api/org/springframework/security/config/annotation/web/configuration/EnableWebSecurity.html) 和 [`@EnableGlobalMethodSecurity`](https://web.archive.org/web/20220628132448/https://docs.spring.io/spring-security/site/docs/current/api/org/springframework/security/config/annotation/method/configuration/GlobalMethodSecurityConfiguration.html) 。

为了说明不同之处，我们将使用一个简单的应用程序，其中包含一些管理资源和经过身份验证的用户资源。我们还会给它一个包含公共资源的部分，我们很乐意让任何人下载。

## 2. Spring Boot 安全

### 2.1. Maven 依赖性

无论我们采用哪种方法，为了安全起见，我们首先需要添加`spring-boot-starter`依赖：

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

### 2.2. Spring Boot 自动配置

在类路径上有了 Spring Security， [Spring Boot 安全自动配置](/web/20220628132448/https://www.baeldung.com/spring-boot-security-autoconfiguration "Spring Boot Security Auto-Configuration")的`WebSecurityEnablerConfiguration`为我们激活了`@EnableWebSecurity`。这将 Spring 的默认安全配置应用于我们的应用程序。

**默认安全配置激活了 HTTP 安全过滤器和安全过滤器链**，并对我们的端点应用基本认证。

## 3. 保护我们的端点

对于第一种方法，让我们从创建一个扩展了`WebSecurityConfigurerAdapter`的`MySecurityConfigurer`类开始，并用`@EnableWebSecurity`对它进行注解：

```java
@EnableWebSecurity
public class MySecurityConfigurer extends WebSecurityConfigurerAdapter {
}
```

通过扩展适配器，我们获得了 Spring Security 其他防御的好处，同时还能够添加定制。

### 3.1. 快速查看默认 Web 安全性

首先，让我们看看`WebSecurityConfigurerAdapter`的默认`configure`方法，这样我们就知道要覆盖什么：

```java
@Override
protected void configure(HttpSecurity http) {
    http.authorizeRequests((requests) -> requests.anyRequest().authenticated());
    http.formLogin();
    http.httpBasic();
}
```

这里我们看到，我们收到的任何请求都经过身份验证，并且我们有一个基本的表单登录来提示输入凭证。

当我们想使用`HttpSecurity` DSL 时，可以写成：

```java
http.authorizeRequests().anyRequest().authenticated()
  .and().formLogin()
  .and().httpBasic()
```

### 3.2. 要求用户拥有适当的角色

现在让我们配置安全性，只允许拥有`ADMIN`角色的用户访问`/admin`端点，并只允许拥有`USER`角色的用户访问`/protected`端点。我们通过重写`configure`方法的`HttpSecurity`参数来实现：

```java
@Override
protected void configure(HttpSecurity http) {
    http.authorizeRequests()
      .antMatchers("/admin/**")
      .hasRole("ADMIN")
      .antMatchers("/protected/**")
      .hasRole("USER");
}
```

### 3.3. 放宽对公共资源的安全保护

我们不需要对公共的`/hello`资源进行认证，所以我们将配置`WebSecurity`不为它们做任何事情。像之前一样，让我们重写`WebSecurityConfigurerAdapter`的`configure`方法，但这次是`WebSecurity`重载：

```java
@Override
public void configure(WebSecurity web) {
    web.ignoring()
      .antMatchers("/hello/*");
}
```

### 3.4. 替换 Spring 的默认安全性

虽然我们的大部分需求可以通过扩展`WebSecurityConfigurerAdapter`来满足，但有时我们可能想要完全替换 Spring 的默认安全配置。为此，我们可以实现`WebSecurityConfigurer`接口而不是扩展`WebSecurityConfigurerAdapter`。

我们应该注意到，**通过实现`WebSecurityConfigurer`, 我们会失去 Spring 的标准安全防御**，所以在走这条路之前我们应该非常仔细地考虑。

## 4. 使用注解保护我们的端点

为了使用注解驱动的方法来应用安全性，我们可以使用`@EnableGlobalMethodSecurity`。

### 4.1. 使用安全注解要求用户拥有适当的角色

现在让我们使用方法注解来配置安全性，只允许`ADMIN`用户访问`/admin`端点，允许`USER`用户访问`/protected`端点。让我们通过在`@EnableGlobalMethodSecurity`注解中设置`jsr250Enabled=true`来启用 [JSR-250](https://web.archive.org/web/20220628132448/https://jcp.org/aboutJava/communityprocess/final/jsr250/index.html) 注解：

```java
@EnableGlobalMethodSecurity(jsr250Enabled = true)
@Controller
public class AnnotationSecuredController {
    @RolesAllowed("ADMIN")
    @RequestMapping("/admin")
    public String adminHello() {
        return "Hello Admin";
    }

    @RolesAllowed("USER")
    @RequestMapping("/protected")
    public String jsr250Hello() {
        return "Hello Jsr250";
    }
}
```

### 4.2. 强制所有公共方法具有安全性

当我们使用注解作为实现安全性的方式时，可能会忘记注解方法。这将无意中造成安全漏洞。为了防止这种情况，**我们应该拒绝对所有没有授权注解的方法的访问**。

### 4.3. 允许访问公共资源

Spring 的默认安全性强制对所有端点进行认证，不管我们是否添加了基于角色的安全性。尽管我们前面的例子对`/admin`和`/protected`端点应用了安全性，但是我们仍然希望允许访问`/hello`中基于文件的资源。

虽然我们可以再次扩展`WebSecurityConfigurerAdapter`，但 Spring 为我们提供了一个更简单的选择。用注解保护了方法之后，我们现在可以添加`WebSecurityCustomizer`来开放`/hello/*`资源：

```java
public class MyPublicPermitter implements WebSecurityCustomizer {
    public void customize(WebSecurity webSecurity) {
        webSecurity.ignoring()
          .antMatchers("/hello/*");
    }
}
```

或者，我们可以简单地创建一个 bean，在我们的配置类中实现它：

```java
@Configuration
public class MyWebConfig {
    @Bean
    public WebSecurityCustomizer ignoreResources() {
        return (webSecurity) -> webSecurity
          .ignoring()
          .antMatchers("/hello/*");
    }
}
```

当 Spring Security 初始化时，它会调用它找到的任何`WebSecurityCustomizer`，包括我们的。

## 5. 测试我们的安全性

既然我们已经配置了安全性，就应该检查它的行为是否符合预期。根据我们选择的安全方法，我们有一个或两个自动化测试选项：向应用程序发送 Web 请求，或直接调用控制器方法。

### 5.1. 通过 Web 请求进行测试

对于第一个选项，我们将创建一个带有`@TestRestTemplate`的`@SpringBootTest`测试类：

```java
@RunWith(SpringRunner.class)
@SpringBootTest(webEnvironment = RANDOM_PORT)
public class WebSecuritySpringBootIntegrationTest {
    @Autowired
    private TestRestTemplate template;
}
```

现在，让我们添加一个测试来确保公共资源可用：

```java
@Test
public void givenPublicResource_whenGetViaWeb_thenOk() {
    ResponseEntity<String> result = template.getForEntity("/hello/baeldung.txt", String.class);
    assertEquals("Hello From Baeldung", result.getBody());
}
```

我们还可以看到当我们尝试访问受保护资源时会发生什么：

```java
@Test
public void whenGetProtectedViaWeb_thenForbidden() {
    ResponseEntity<String> result = template.getForEntity("/protected", String.class);
    assertEquals(HttpStatus.FORBIDDEN, result.getStatusCode());
}
```

这里我们得到了`FORBIDDEN`响应，因为匿名请求没有所需的角色。

因此，无论选择哪种安全方法，我们都可以使用这种方法来测试安全应用程序。

### 5.2. 通过自动布线和注解进行测试

现在让我们看看第二个选项。让我们设置一个`@SpringBootTest`并自动连接`AnnotationSecuredController`：

```java
@RunWith(SpringRunner.class)
@SpringBootTest(webEnvironment = RANDOM_PORT)
public class GlobalMethodSpringBootIntegrationTest {
    @Autowired
    private AnnotationSecuredController api;
}
```

让我们从使用`@WithAnonymousUser`测试可公开访问的方法开始：

```java
@Test
@WithAnonymousUser
public void givenAnonymousUser_whenPublic_thenOk() {
    assertThat(api.publicHello()).isEqualTo(HELLO_PUBLIC);
}
```

现在我们已经访问了公共资源，让我们使用`@WithMockUser`注解来访问受保护的方法。

首先，让我们用一个具有`USER`角色的用户来测试 JSR-250 保护的方法：

```java
@WithMockUser(username="baeldung", roles = "USER")
@Test
public void givenUserWithRole_whenJsr250_thenOk() {
    assertThat(api.jsr250Hello()).isEqualTo("Hello Jsr250");
}
```

现在，当用户没有正确的角色时，让我们尝试访问相同的方法：

```java
@WithMockUser(username="baeldung", roles = "NOT-USER")
@Test(expected = AccessDeniedException.class)
public void givenWrongRole_whenJsr250_thenAccessDenied() {
    api.jsr250Hello();
}
```

我们的请求被 Spring Security 拦截，抛出了`AccessDeniedException`。

我们只能在选择基于注解的安全性时使用这种方法。

## 6. 注解注意事项

当我们选择基于注解的方法时，有一些要点需要注意。只有当通过公共方法入口进入一个类时，带注解的安全性才会被应用。

### 6.1. 间接方法调用

前面，当我们调用带注解的方法时，看到安全性被成功应用。然而，现在让我们在同一个类中创建一个没有安全注解的公共方法，并让它调用带注解的`jsr250Hello`方法：

```java
@GetMapping("/indirect")
public String indirectHello() {
    return jsr250Hello();
}
```

现在让我们仅使用匿名访问来调用`/indirect`端点：

```java
@Test
@WithAnonymousUser
public void givenAnonymousUser_whenIndirectCall_thenNoSecurity() {
    assertThat(api.indirectHello()).isEqualTo(HELLO_JSR_250);
}
```

我们的测试通过了，因为“安全”方法被调用，却没有触发任何安全性。换句话说，**没有安全性被应用于同一类内部的调用**。

### 6.2. 对不同类的间接方法调用

现在让我们看看当未受保护的方法调用不同类上的带注解方法时会发生什么。

首先，让我们用带注解的方法`differentJsr250Hello`创建一个`DifferentClass`：

```java
@Component
public class DifferentClass {
    @RolesAllowed("USER")
    public String differentJsr250Hello() {
        return "Hello Jsr250";
    }
}
```

现在，让我们将`DifferentClass`自动连接到控制器中，并添加一个不受保护的`differentClassHello`公共方法来调用它：

```java
@Autowired
DifferentClass differentClass;

@GetMapping("/differentclass")
public String differentClassHello() {
    return differentClass.differentJsr250Hello();
}
```



最后，让我们测试调用，看看我们的安全性是否得到了加强：

```java
@Test(expected = AccessDeniedException.class)
@WithAnonymousUser
public void givenAnonymousUser_whenIndirectToDifferentClass_thenAccessDenied() {
    api.differentClassHello();
}
```

因此，我们看到，虽然我们的安全注释在调用同一个类中的另一个方法时不会受到尊重，但当我们调用不同类中的一个带注释的方法时，它们会受到尊重。

### 6.3. 最后要注意的是

我们应该确保正确配置我们的`@EnableGlobalMethodSecurity`。如果我们不这样做，那么不管我们所有的安全注释，它们都不会有任何效果。

例如，如果我们使用 JSR-250 注释，但是我们指定了`prePostEnabled=true`而不是`jsr250Enabled=true`，那么我们的 JSR-250 注释将什么也不做！

```java
@EnableGlobalMethodSecurity(prePostEnabled = true)
```

当然，我们可以声明我们将使用不止一种注释类型，方法是将它们都添加到我们的`@EnableGlobalMethodSecurity`注释中：

```java
@EnableGlobalMethodSecurity(jsr250Enabled = true, prePostEnabled = true)
```

## 7. 当我们需要更多的时候

相比于 JSR-250，我们还可以使用[弹簧法安全](/web/20220628132448/https://www.baeldung.com/spring-security-method-security "Introduction to Spring Method Security")。这包括为更高级的授权场景使用更强大的 [Spring 安全表达式](/web/20220628132448/https://www.baeldung.com/spring-security-expressions)语言（SpEL）。我们可以通过设置`prePostEnabled=true`在我们的`EnableGlobalMethodSecurity`注释上启用 SpEL：

```java
@EnableGlobalMethodSecurity(prePostEnabled = true)
```

此外，当我们想要根据用户是否拥有一个域对象来实施安全性时，我们可以使用 [Spring 安全访问控制列表](/web/20220628132448/https://www.baeldung.com/spring-security-acl)。

我们还应该注意，当我们编写反应式应用程序时，我们使用`@EnableWebFluxSecurity`和`@EnableReactiveMethodSecurity`来代替。

## 8. 结论

在本教程中，我们首先看了如何使用集中的安全规则方法和`@EnableWebSecurity`来保护我们的应用程序。

然后，我们在此基础上，通过配置我们的安全性，将这些规则放在它们影响的代码附近。我们通过使用`@EnableGlobalMethodSecurity`并注释我们想要保护的方法来做到这一点。

最后，我们介绍了一种替代方法，可以为不需要安全性的公共资源放松安全性。

与往常一样，GitHub 上的示例代码[可用。](https://web.archive.org/web/20220628132448/https://github.com/eugenp/tutorials/tree/master/spring-boot-modules/spring-boot-security)
