
# 使用 Swagger 3 和 Spring Boot 2 + Spring Security 的 API 文档

> 原文：<https://medium.com/javarevisited/api-documentation-using-swagger-3-with-spring-boot-2-spring-security-5a0d2b0996ee?source=collection_archive---------0----------------------->

想为 Spring Boot 2 应用程序编写 API 文档吗？嗯，使用开放 API 规范非常简单。

## 什么是开放 API 规范？

开放 API 规范是 Rest APIs 的标准 API 描述格式。

## 什么是 Swagger？

Swagger 是 SmartBear 提供的一个实现该规范的开源工具。它可以帮助你设计、构建、记录和使用你的 Rest API。

在本文中，我们将看看如何记录我们的 Rest APIs，并使用 Swagger UI 将其可视化。那么，让我们开始实施吧…

在 Spring Boot 应用程序中使用 Swagger 打开 Api Spec 3.0

首先，您需要在 `pom.xml` 或 `build.gradle` 文件中添加以下依赖项：

> Maven：

```
<dependency>
   <groupId>io.springfox</groupId>
   <artifactId>springfox-boot-starter</artifactId>
   <version>3.0.0</version>
</dependency>
```

> Gradle：

```
implementation group: 'io.springfox', name: 'springfox-boot-starter', version: '3.0.0'
```

现在，您需要创建一个如下所示的 Swagger 配置 Java 类：

```
@Configuration
public class SwaggerConfig {

    private ApiInfo apiInfo() {
        return new ApiInfo("MyApp Rest APIs",
                "APIs for MyApp.",
                "1.0",
                "Terms of service",
                new Contact("test", "www.org.com", "test@emaildomain.com"),
                "License of API",
                "API license URL",
                Collections.emptyList());
    }

    @Bean
    public Docket api() {
        return new Docket(DocumentationType.OAS_30)
                .apiInfo(apiInfo())
                .select()
                .apis(RequestHandlerSelectors.any())
                .paths(PathSelectors.any())
                .build();
    }
}
```

你需要用 `@Configuration` 注释来注释这个类。第一个方法 `apiInfo()` 用于添加关于 API 的定制信息，然后在 `api()` 方法中调用。

`api()` 方法通过方法链接使用构建器模式，并返回 Spring Bean `Docket` 来确定生成各种文档的配置。在我们的例子中，我们提供的文档类型是 Open Api Spec 3.0。

这里，我们通过使用 `RequestHandlerSelectors.any()` 和 `PathSelectors.any()` 为所有 API 和路径创建文档，但是如果您愿意，您可以配置您希望 Swagger 为其生成文档的特定 API 或路径。

## 具有 Spring 安全性的 Swagger 配置

如果您在应用程序中启用了 Spring 安全性，那么您需要将相同的安全性添加到您的 Swagger 配置类中，这样您的 Swagger APIs 将受到保护，如果您试图通过 SwaggerUI 调用您的 API，它也会要求在那里提供身份验证。

例如，如果在您的应用程序中使用 JWT 身份验证，那么您的 Swagger 配置文件应该如下所示：

```
@Configuration
public class SwaggerConfiguration {
    public static final String AUTHORIZATION_HEADER = "Authorization";

    private ApiInfo apiInfo() {
        return new ApiInfo("MyApp Rest APIs",
                "APIs for MyApp.",
                "1.0",
                "Terms of service",
                new Contact("test", "www.org.com", "test@emaildomain.com"),
                "License of API",
                "API license URL",
                Collections.emptyList());
    }

    @Bean
    public Docket api() {
        return new Docket(DocumentationType.OAS_30)
                .apiInfo(apiInfo())
                .securityContexts(Arrays.asList(securityContext()))
                .securitySchemes(Arrays.asList(apiKey()))
                .select()
                .apis(RequestHandlerSelectors.any())
                .paths(PathSelectors.any())
                .build();
    }

    private ApiKey apiKey() {
        return new ApiKey(AUTHORIZATION_HEADER, "JWT", "header");
    }

    private SecurityContext securityContext() {
        return SecurityContext.builder()
                .securityReferences(defaultAuth())
                .build();
    }

    List<SecurityReference> defaultAuth() {
        AuthorizationScope authorizationScope
                = new AuthorizationScope("global", "accessEverything");
        AuthorizationScope[] authorizationScopes = new AuthorizationScope[1];
        authorizationScopes[0] = authorizationScope;
        return Arrays.asList(new SecurityReference(AUTHORIZATION_HEADER, authorizationScopes));
    }
}
```

为了增加安全性，需要添加 `apiKey()` 和 `securityContext()` 方法来使用默认的认证方法。

现在，您需要在您的 `WebSecurityConfig.java` 类中做一些更改，将认证 API（如果您启用了 Spring Security）和 Swagger 相关 URL 列入白名单，然后在 `configure()` 方法中默认授权来自这些白名单 URL 的请求，这样对于这些 URL 它就不会要求您授权。

```
private static final String[] AUTH_WHITELIST = {
        "/authenticate",
        "/swagger-resources/**",
        "/swagger-ui/**",
        "/v3/api-docs",
        "/webjars/**"
};

@Override
protected void configure(HttpSecurity httpSecurity) throws Exception {
    httpSecurity
            .cors()
            .and()
            .csrf()
            .disable()
            .headers()
            .frameOptions()
            .deny()
            .and()
            // dont authenticate this particular request
            .authorizeRequests().antMatchers(AUTH_WHITELIST).permitAll().
            // all other requests need to be authenticated
                    anyRequest().authenticated().and().
            // make sure we use stateless session; session won't be // used to store user's state.
                    exceptionHandling().authenticationEntryPoint(jwtAuthenticationEntryPoint).and().sessionManagement()
            .sessionCreationPolicy(SessionCreationPolicy.STATELESS);
    // Add a filter to validate the tokens with every request
    httpSecurity.addFilterBefore(jwtRequestFilter, UsernamePasswordAuthenticationFilter.class);
}
```

完成这些更改并启动应用程序后，您应该能够看到 Swagger-UI 网页，如下所示：

**网址**：`http://<app-root>/swagger-ui/index.html`

现在，要在 Swagger UI 上标记您的 API 或提供每个 API 的描述，您需要对 API 使用一些注释：

- `@Api`：在类级别使用 `tags` 或 `value` 属性，将其定义为 Swagger 资源。
- `@ApiOperation`：用在 API 方法级别，用 `value` 或 `tags` 属性来描述操作。

根据需要，可以在 API 上使用不同的注释。同样可以参考 Swagger API 文档。

Swagger 还配置了一个 API 端点来查看所有 API 及其详细信息，您可以通过 Postman 测试/执行这些信息。

- API URL：`http://<app-root>/v3/api-docs`
- 方法类型：`GET`

它应该会返回如下类似的响应：

```
openapi: 3.0.0
info:
  version: 1.0.0
  title: Sample API
  description: A sample API to illustrate OpenAPI concepts
paths:
  /list:
    get:
      description: Returns a list of stuff              
      responses:
        '200':
          description: Successful response
```

希望您现在能够看到应用程序的 API 文档和 Swagger UI。

编码快乐！！

您可能喜欢的其他 REST API 教程和课程：

- [Top 10 REST API Interview Questions for Java and Spring Developers](https://javarevisited.blogspot.com/2022/01/top-5-courses-to-learn-swagger-or-open.html)
- [10 Best Java Web Services, REST, SOAP and API Courses for Beginners](https://javarevisited.blogspot.com/2022/01/top-5-courses-to-learn-swagger-or-open.html)
- [Top 5 Courses to Learn Swagger or Open API](https://javarevisited.blogspot.com/2022/01/top-5-courses-to-learn-swagger-or-open.html)

如果你不是 Medium 成员，我强烈推荐你加入 Medium，阅读不同领域伟大作家的精彩故事。你可以在[这里加入 Medium](https://medium.com/@somasharma_81597/membership)。
