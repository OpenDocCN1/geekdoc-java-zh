
# RESTful Java Web 服务：最可能问到的面试题

![](img/f2d5f7dd81c54b5511f7cf51f16b5c04_0_0.png)

回顾这些典型的面试题，并思考你将如何回答它们。阅读列出的答案；你将找到最佳答案以及相关的策略和建议。

# RESTful 基础 / 注解

## 1: 在哪些场景下 RESTful Web 服务优于 SOAP 服务？

答案：

在以下情况下，优选 RESTful Web 服务：

- a) Web 服务是完全无状态的。
- b) 数据可以被缓存以提高性能。
- c) 服务消费者和提供者之间可以达成数据模式（Schema）。
- d) 带宽有限。

## 2: 在 REST 设计范式中，你如何引用或标识资源？

答案：

资源通过其唯一的 URL 进行标识。

## 3: REST 是无状态还是有状态的客户端服务器架构？

答案：

REST 是无状态的客户端服务器架构。

## 4: 列出用于构建和部署 RESTful Web 服务的 JAVA API。

答案：

- a) 用于 XML 服务的 JAVA API (`JAX-WS`) 以及
- b) 用于 XML RESTful 服务的 JAVA API (`JAX-RS`)。

## 5: RESTful Web 服务的接口是如何描述的？

答案：

RESTful Web 服务接口通过注解（Annotations）来描述。服务消费者和提供者之间可以对数据达成一致。

## 6: 列出 RESTful 的实现方式。

答案：

`Jersey`、`REasy`、`Restlet`。

## 7: 在计划使用 RESTful 服务时，需要 Jersey 吗？

答案：

是的，使用 `Jersey 6.0`。

## 8: 资源是如何定位的？

答案：

资源通过唯一的 URI 进行定位。

## 9: 在 REST 架构中，状态是如何表示的？

答案：

在 REST 架构中，通过 URI 来表示状态。

## 10: RESTful 接口是如何描述的？

答案：

通过 URI 模板（URI templates）描述。

## 11: Jersey 是什么？

答案：

`Jersey` 是 `JAX-RS` 的实现。

## 12: JSON 是什么？

答案：

`JSON` 是一种数据交换格式。

## 13: 链接的用途是什么？

答案：

用于超媒体（hypermedia links）。

## 14: JAX-RS 客户端 - Jersey Client API 是什么？

答案：

（此处根据原文逻辑，跳转至 15 人力资源面试题）

## 15: 什么是幂等方法？

答案：

如果多次调用方法不会产生副作用，则称它是幂等的。

## 16: 为什么 PUT 方法是幂等的？

答案：

重复调用不会产生副本。

## 17: HttpMethod 的作用是什么？

答案：

`@HttpMethod` 注解用于关联 HTTP 方法。

## 18: 列出常见的 HTTP 注解。

答案：

`@GET`、`@POST`、`@DELETE`。

## 19: 定义根类（Root class）。

答案：

带有 `@Path` 注解的 POJO（普通 Java 对象）。

## 20: 什么是资源方法？

答案：

带有 `@Path` 注解的类方法。

## 21: 如何指定资源的相对路径？

答案：

使用 `@Path` 注解来指定相对路径。

## 22: 变量如何在 URI 中嵌入？

答案：

变量在花括号中嵌入，例如 `{username}`。

## 23: 如何获取方法参数的值？

答案：

在方法参数上使用 `@PathParam` 注解来获取。

## 24: 如何为变量 username 定义正则表达式？

答案：

```
@Path("users/{username:[a-zA-Z][a-zA-Z0-9]*}")
```

## 25: 如果正则表达式匹配会发生什么？

答案：

会发生 404（未找到）响应。

## 26: 下列代码指向同一个资源吗？

```
@Path("/test/")
@Path("/test")
```

答案：

是的。默认情况下它们指向同一个资源，尽管 `Jersey` 有一种重定向机制但它是禁用的。

## 27: 解释如何指定返回给客户端的资源的 MIME 类型。

答案：

`@Produces` 注解用于此目的。例如：

```
@Produces("text/plain")
```

## 28: @Produces 只能应用于方法级别吗？

答案：

错误。它可以既应用于类级别，也可以应用于方法级别。

## 29: RESTful 资源可以覆盖 @Produces 注解吗？给出示例。

答案：

是的。在以下示例中，默认 MIME 类型被设置为 `text/plain`，但 `doGetAsHtml` 方法将其覆盖为 `text/html`。

```
@Path("/testResource")
@Produces("text/plain")
public class TestResource {
  @GET
  public String doGetAsPlainText() {
    ...
  }

  @GET
  @Produces("text/html")
  public String doGetAsHtml() {
    ...
  }
}
```

## 31: 如何在同一个 @Produces 声明中声明多个媒体类型？

答案：

```
@Produces("application/plain","application/xml","application/json")
```

## 32: 假设有一个资源类能够为 GET 请求产生多个 MIME 媒体类型。将如何选择响应方法？

答案：

资源方法的选择取决于客户端在请求头中声明的最可接受的媒体类型。例如：`Accept: text/plain`。

## 33: 你将如何指定 RESTful 资源可以使用的表示的 MIME 媒体类型？

答案：

使用 `@Consumes` 注解。

## 34: 编写一个在 POST 请求时触发并接受 text/plain 作为输入的方法。

答案：

```
@POST
@Consumes("text/plain")
public void postMessage(String message) {
...
}
```

## 35: @Consumes 可以应用于哪些级别？

答案：

`@Consumes` 可以同时应用于类级别和方法级别。

## 36: 给出一个声明多个媒体类型的 @Consumes 声明的例子？

答案：

```
@POST
@Consumes("application/plain","application/xml")
public void postMessage(String message) {
...
}
```

## 37: RESTful Web 服务支持多种类型的响应（MIME 格式）吗？

答案：

RESTful Web 服务通过遵循 HTTP 确实支持多种类型的响应（MIME）格式，例如：`XML`、`JSON`、`PLAIN` 等。

## 38: RESTful Web 服务通常支持哪两种响应格式？

答案：

`XML` 和 `JSON`。

## 39: 在设计 RESTful Web 服务时，什么构成了系统的资源？

答案：

任何具有表示的系统概念都应该被暴露为资源。

## 40: HATEOAS 是什么意思？

答案：

超媒体作为应用程序状态引擎（HATEOAS）意味着会话中的交换状态既不在客户端也不在服务器保留。所有必要的信息都存储在交换的 HTTP 消息中。

## 41: 定义统一接口约束（Uniform Interface Constraint）？

答案：

统一接口约束绑定了 RESTful Web 服务的架构；由于这种约束，客户端可以使用相同的接口与任何服务进行通信。

# 部署 RESTful Web 服务

## 42: 写出用于声明根资源的 JAX-RS 部署无关抽象类。

答案：

`JAX-RS` 提供了一个名为 `Application` 的部署无关抽象类来声明根资源。

## 43: 如何使用 JAX-RS Application 类声明根资源和提供类？

答案：

Web 服务需要扩展 `Application` 类来声明根资源和提供类，例如：

```
public class MyApplication extends Application {
    public Set<Class<?>> getClasses() {
        Set<Class<?>> s = new HashSet<Class<?>>();
        s.add(HellResource.class);
        return s;
    }
}
```

## 44: 给出一个使用 Servlet 3.0 配合 @ApplicationPath 进行 JAX-RS 应用部署的例子。

答案：

```
@ApplicationPath("resources")
public class MyApplication extends PackagesResourceConfig {
    public MyApplication() {
        super("org.test.rest;org.test1.rest");
    }
}
```

## 45: 如何在 pom.xml 中为 Servlet 3.0 配置 maven-war-plugin？

答案：

```
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-war-plugin</artifactId>
<version>2.1.1</version>
<configuration>
<failOnMissingWebXml>false</failOnMissingWebXml>
</configuration>
</plugin>
```

## 46: 是否可以在 web.xml 中声明 JAX-RS 应用细节？

答案：

可以，但这仅在复杂的部署场景下是首选。

## 47: 你将如何在 web.xml 中声明 JAX-RS 应用细节？

答案：

根据 `JAX-RS 1.1` 规范，实现 `Application` 的类的全限定名必须在 `JAX-RS` 应用的 `web.xml` 的 `<servlet-name>` 元素中声明。

```
这在实现 Servlet 3.0 的 Web 容器中受支持。
<web-app>
<servlet>
  <servlet-name>org.test.rest.MyApplication</servlet-name>
</servlet>
...
<servlet-mapping>
  <servlet-name>org.test.rest.MyApplication</servlet-name>
  <url-pattern>/resources</url-pattern>
</servlet-mapping>
...
</web-app>
```

在 servlet 声明中不需要 `<servlet-class>` 元素。

## 48: 使用 Servlet 3.0 扩展机制声明 RESTful 资源，web.xml 中用哪个元素定义基础资源 URI。

答案：

使用 `<servlet-mapping>` 来定义基础资源 URI。

## 49: 你正在使用 Servlet 2.0 并在 web.xml 中声明 Jersey 特有的 servlet。你将如何配置它？

答案：

我们需要声明 servlet：

```
<web-app>
<servlet>
  <servlet-name>org.test.rest.MyApplication</servlet-name>
  <servlet-class>org.test.rest.MyApplication</servlet-class>
</servlet>
...
<servlet-mapping>
  <servlet-name>org.test.rest.MyApplication</servlet-name>
  <url-pattern>/resources</url-pattern>
</servlet-mapping>
...
</web-app>
```

## 50: 你正在使用 Servlet 3.0 并想要声明 Jersey 特有的应用。你将如何配置它？

答案：

```
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-war-plugin</artifactId>
<version>2.1.1</version>
<configuration>
<failOnMissingWebXml>false</failOnMissingWebXml>
</configuration>
</plugin>
```

## 51: 基于参数注解（parameter-based annotations）的目的是什么？

答案：

基于参数的注解用于从请求中提取信息。

## 52: 你将使用哪个注解从 URL 中提取查询参数？

答案：

`@QueryParam`

## 53: 如何为资源方法参数声明默认值？

答案：

使用 `@DefaultValue` 来声明资源方法参数的默认值。

```
@Path("/test")
@GET
public Response getName(@DefaultValue("1") @QueryParam("id") int id){
  ...
}
```

## 54: 如果请求的查询参数无法解析为资源方法参数，会发生什么？

答案：

返回 HTTP 404 (Not Found) 响应。

## 55: 资源方法的查询参数只能使用基本类型？

答案：

不是。可以使用自定义类型。

## 56: 查看以下资源方法。如果请求中不存在查询参数，资源方法参数 'id' 的值是什么？

```
@Path("/test")
@GET
public Response getName(@QueryParam("id") int id){
...
}
```

答案：

如果不存在，Java 基本类型获得 Java 定义的默认值。在给定情况下，`id` 将为 `0`。

## 57: 查看以下资源方法。如果请求中不存在查询参数，资源方法参数 'firstName' 的值是什么？

```
@Path("/test")
@GET
public Response getLastName(@QueryParam("firstName") String firstName){
...
}
```

答案：

如果查询参数不存在，对象类型将获得 `null`。在给定情况下，`firstName` 将为 `null`。

## 58: 如果未指定默认值且请求中不存在参数，List<T> 类型的资源方法参数设置什么默认值？

答案：

空列表。

## 59: 写出从 URL 路径段提取信息的基于参数的注解

答案：

`@MatrixParam`

## 60: 使用哪些基于参数的注解从 HTTP 头部提取信息？

答案：

`@HeaderParam`

## 61: 写出从 cookie 相关的 HTTP 头部提取信息的基于参数注解

答案：

`@CookieParam`

## 62: 你想获取 HTML 表单提交的参数作为资源方法的参数。你倾向于使用哪个注解？

答案：

`@FormParam`

`@FormParam` 将被首选，因为它从 MIME 媒体类型 `application/x-www-form-urlencoded` 的请求中提取参数。它也符合 HTML 表单指定的编码。

## 63: 给出一个处理 POST HTML 表单的资源方法的示例？

答案：

```
@POST
@Consumes("application/x-www-form-urlencoded")
public void post(@FormParam("name") String name) {
...
}
```

## Responses（响应）

## 64: 是否可以从资源方法向 HTTP 请求返回响应？

答案：

可以。可以使用 `Response` 和 `Response.ResponseBuilder` 构建响应。例如：`return Response.created(createdUri).build();`。

## 65: 编写一个响应 Post 请求、消耗 application/xml 并向自定义响应添加实体主体的资源方法？

答案：

```
@POST
@Consumes("application/xml")
public Response post(String content) {
URI uri = ...

String createdContent = create(content);
return Response.created(uri).entity(createdContent).build();
}
```

## Sub Resources（子资源）

## 66: 定义根资源类？

答案：

当一个类被带有 `@Path` 注解时，它被称为根资源类。

## 67: @Path 可以用在根资源类的方法上吗？

答案：

可以。这允许将资源分组在一起并允许可重用性。此类方法被称为子资源方法。

> 问题 68, 69, 70, 和 71 基于以下根资源类。



@Path("/cars")
public class CarsResource {
    @GET
    @Produces("application/json", "application/xml")
    public WebResourceList getMyResources() { ... }
}

@GET
@Path("/model")
@Produces("application/json", "application/xml")
public WebResourceList getModels() { ... }

@GET
@Path("/make")
@Produces("application/json", "application/xml")
public WebResource getMakesList() { ... }

# 68: 当请求 URL 为 /cars 时，被调用的方法名称是什么？

答案：

`getMyResources()` 会被调用，因为它没有注解。

# 69: 使用什么请求 URL 来调用 `getMakes()` 资源方法？

答案：

`/cars/make`

# 70: 使用请求 URL 'cars/model' 时会调用哪个请求响应方法？

答案：

`getModels()`

# 71: 当请求 URL 为 /cars/test 时，被调用的方法名称是什么？

答案：

请求 URL 将无法匹配任何资源，并将返回 HTTP 状态 404。

# 问题 72, 73, 74 基于以下根资源类。

@Path("/hello")
public class Hello {
    ...
    @Path("/testparam")
    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String getLastName(@RequestParam("firstName") String firstName) {
        return firstName + " " + "MyLastName";
    }
    ...
}

72: 如果请求 URL 为：

`/hello/testparam?`

结果是什么？

答案：

`null MyLastName`

73: 如果请求 URL 为：

`/hello/testparam?name=MyFirstName?`

结果是什么？

答案：

`null MyLastName`

74: 为了得到以下结果，请求的 URL 应该是？

## MyFirstName MyLastName

答案：

`/hello/testparam?firstName=MyFirstName`

## 75: 什么是子资源定位方法？

答案：

这些是没有用资源方法设计标识符（`@Get`, `@Post` 等）进行注解的方法。

# 76: 给出一个子资源定位方法的示例。

答案：

`ItemResource` 是一个根资源类，`getItemContentResource()` 是一个子资源定位方法。对于请求 URL 路径 "item/content"，首先会匹配根资源，然后匹配并调用子资源定位器。

@Path("/item")
public class ItemResource {

    @Path("/content")
    public ItemContentResource getItemContentResource() {
        ...
    }
}

# 77: JAX-RS 支持条件 GET 和 PUT HTTP 请求吗？

答案：

是的，JAX-RS 支持条件 GET 和 PUT HTTP 请求。

# 78: 条件 GET 和 PUT HTTP 请求的处处是什么？

答案：

条件 GET 和 PUT HTTP 请求有助于节省带宽，从而提高客户端处理的效率。

# 79: 假设静态内容自上一次请求以来没有更改。对于 GET 请求，应该发送什么响应来节省带宽？

答案：

一个 Not Modified (304) 响应。

# 80: 假设当客户端发送 PUT 请求时表示已被修改。应该向其发送什么响应？

答案：

一个 Precondition Failed (412) 响应。

# 81: 解决导致丢失更新问题的 Precondition Failed (412) 响应的正确方法是什么？

答案：

可以使用条件 PUT 来避免丢失更新问题。

# 82: 如何构建资源类的 URI？

# 83: 假设静态内容自上一次请求以来没有更改。对于 GET 请求，应该发送什么响应来节省带宽？

答案：

一个 Not Modified (304) 响应。

# 84: 假设当客户端发送 PUT 请求时表示已被修改。应该向其发送什么响应？

答案：

一个 Precondition Failed (412) 响应。

# 85: 导致丢失更新问题的 Precondition Failed (412) 响应的正确方法是什么？

答案：

条件 PUT 可以避免丢失更新问题。

# 86: `UriBuilder` 只能用于构建新 URI 吗？

答案：

不是。它也可以用于从现有 URI 构建 URL。

# 87: 哪个 JAX-RS 类用于安全地构建 URI？

答案：

`javax.ws.rs.core.UriBuilder`

# 88: 使用 `java.net` 构建 URI 安全方便吗？

答案：

不。

# 89: `javax.ws.rs.core.UriBuilder` 只能用于构建新 URI 吗？

答案：

不是。它也可以用于从现有 URI 构建 URL。

# 90: 如何构建资源类的 URI？

答案：

资源类的 URI 通常是根据部署的基础 URI 构建的。

# 91: 如何在资源类中获取 `UriInfo`？

答案：

可以使用 `@Context` 注解获取实例。

# 92: 如果你有 `UriInfo`，你可以获取哪些 URI？

答案：

我们可以获取应用程序的基础 URI、请求 URI 和绝对路径 URI。

# 93: 如何在资源类中获取 `UriInfo`？

答案：

可以使用 `@Context` 注解获取实例。

# 94: 如果你有 `UriInfo`，你可以获取哪些 URI？

答案：

我们可以获取应用程序的基础 URI、请求 URI 和绝对路径 URI。

# 95: 如果从请求 URI 中减去查询组件，你会得到什么？

答案：

绝对路径 URI。

# 96: 使用查询参数构建 URI 的示例。

答案：

```
UriBuilder.fromUri("http://localhost/").path("{a}").queryParam("name", "{value}").build("segment", "value");
```

# 97: 如何从 RESTful get 方法返回 HTTP 错误？

答案：

可以通过抛出异常以更好的方式返回 HTTP 响应。

# 98: 编写一个在任何原因处理失败时抛出异常的 RESTful get 方法。

答案：

在给定的示例中，如果未找到请求的测试，将抛出一个 Jersey 特有异常。

@Path("test/{testid}/")
public Item getItem(@PathParam("testid") String testid) {
    Item i = getTestss().get(testid);
    if (i == null)
        throw new NotFoundException("testid, " + testid + ", is not found");
    return i;
}

`NotFoundException` 是扩展 `WebApplicationException` 的 Jersey 特有异常。

# 99: 如果 RESTful get 方法抛出 `WebApplicationException`，实际发送了什么 HTTP 响应？

答案：

发送带有 404 状态码且响应体中包含可选消息的 HTTP 响应。

# 100: 你希望将现有异常映射到响应，而不是在你的 RESTful 资源方法中抛出 `WebApplicationException` 实例。如何实现？

JAX-RS 提供 `javax.ws.ext.ExceptionMapper<E extends Throwable>` 来将异常映射到响应。

@Provider
public class EntityNotFoundMapper implements ExceptionMapper<javax.persistence.EntityNotFoundException> {
    public Response toResponse(javax.persistence.EntityNotFoundException ex) {
        return Response.status(404).entity(ex.getMessage()).type("text/plain").build();
    }
}

## 生命周期

# 101: 一个类被标记为 `@Provider`。这说明什么？

答案：

被标记为 provider 的类意味着它对 JAX-RS 运行时感兴趣。

# 102: 什么时候会创建根资源类的新实例？

答案：

当请求 URI 路径匹配根资源时，会创建一个根资源类的新实例。根资源类是每个请求创建一个。

# 103: 除了基于请求的资源类创建外，Jersey 还支持哪些生命周期？

答案：

Jersey 支持：基于 Web 应用程序的根资源实例创建、基于 Web 会话的创建、基于请求的创建。

# 104: 你如何使用 Jersey 声明一个单例资源类？

答案：

Jersey 提供 `@Singleton` 注解来支持基于 Web 应用程序的根资源创建。

@Singleton
@Path("/exroot")
public class RootResource {
}

你最可能遇到的 RESTful Java Web 服务面试题 53

# 105: 如果我们想为一个 Web 会话创建一个资源类实例，可以使用哪个 Jersey 注解？

答案：

`@Session` 允许将资源类实例存储为会话属性，从而允许它在会话中共享。

## 106: 如何在资源方法中获取 `SecurityContext`？

答案：

使用 `@Context` 注解获取 `SecurityContext`。在下面的示例中，资源方法名为 'sc' 的参数被标记为 `@SecurityContext` 以获取 `SecurityContext`。例如 `@Path("test")`

public TestResource get(@Context SecurityContext sc) {
    ...
}

## 注入

# 107: 你可以在你的 RESTful 资源类的什么位置使用注入？

答案：

注入可以在字段、bean 的 setter 方法、构造函数参数以及资源/子资源方法的参数上执行。

# 108: 给出一个在字段上进行注入的例子？

答案：

@Path("student")
public class StudentResource {

    @DefaultValue("20")
    @PathParam("age")
    private int age;
    ...
}

# 109: 如何将值注入到 RESTful 资源类的构造函数参数中？

答案：

`@PathParam` 注解用于此目的。例如：

@Path("student")

```java
public class StudentResource(@PathParam("id") int id) { ... }
...
```

你最可能遇到的 RESTful Java Web 服务面试题 57

# 110: 给出一个在资源方法参数上注入的例子？

答案：

@GET

public String get(@Context UriInfo ui) { ... }

# 111: 是否可以在子资源方法参数上使用注入？

答案：

可以的。它的实现方法与资源方法参数的的方法相同。

例如

@Path("sub")

@GET

public String get(@PathParam("sid") String sid) { ... }

# 112: 对于生命周期并非每个请求一次的资源类，注入有哪些限制？

答案：

对于非每个请求的资源类，无法在与提取请求参数相关的注解的字段上进行注入。

# 113: 对于非每个请求的资源类，带有 `@Context` 注解的字段注入会有效吗？

答案：

可以的。对于 `@Context` 注解，将注入一个线程本地代理（thread local proxy）。

## 114: `@RequestParam` 注解用在哪里？

答案：

`@RequestParam` 注解只能用于资源方法和子资源方法。

# 115: 假设你正在使用 servlet 部署一个 JAX-RS 。使用 `@Context` 可以获得什么？

答案：

`ServletConfig`, `ServletContext`, `HttpServletRequest` 和 `HttpServletResponse`。

## 参数提取

## 116: 在资源类中可以提取什么类型的参数？

答案：

一个资源类可以提取以下参数：查询（Query）、URI 路径、表单（Form）、Cookie、头部（Header）、矩阵（Matrix）

# 117: 哪个 JAX-RS 注解用于检索与请求或响应相关的 JAVA 类型？

答案：

`javax.ws.rs.core.Context` 注解

# 118: 你如何获取请求头部和 cookie 的信息？

答案：

使用 `javax.ws.rs.core.HttpHeaders` 接口来获取头部和 cookie 参数的映射。例如：

GET

```
public String getHeaders(@Context HttpHeaders hh) {
    MultivaluedMap<String, String> headers = hh.getHeaders();
    MultivaluedMap<String, String> cookies = hh.getCookies();
    ...
}
```

## 119: 你希望检索有关请求的信息。哪个接口可以提供这些信息？

答案：

`javax.ws.rs.core.UriInfo` 接口提供了查询和路径参数的映射。例如：

RESTful Java Web 服务面试题 51

```java
public String get(@Context UriInfo ui) {
    ...
}
```

# 120: 哪个注解用于提取表单？

答案：

`@FormParam` 用于提取表单参数。

# 121: 一个表单向你的资源提交了 'name'。使用哪个注解来提取它？

答案：

`@FormParam` 用于提取表单参数。

## 122: 写一个获取表单参数映射的资源方法。

答案：

@POST
@Consumes("application/x-www-form-urlencoded")
public void post() {
    ...
}

# 123: 什么是 URI 模板？

答案：

在 URI 语法中嵌入变量的 URI 称为 URI 模板。

# 124: 你如何在你的资源方法中使用变量路径片段？

答案：

`@PathParam` 注解允许我们在资源方法中使用变量路径片段。例如：

@Path("/employees/{firstName}")
public class EmployeeResource {
    @GET
    @Produces("text/plain")
    public String getEmployee(@PathParam("firstName") String firstName) {
        ...
    }
}

## Jersey

## 126: Jersey 使用什么来解析传入的请求？

答案：

使用 `javax.ws.rs.ext.MessageBody`，它是用于将流转换为 JAVA 类型的提供者接口。

# 127: Jersey 使用什么来创建响应响应？

答案：

Jersey 使用 `javax.ws.rs.ext.MessageBodyWriter` 创建输出消息。`MessageBodyWriter` 是用于将 JAVA 类型转换为流的提供者接口。

问题 128 和 129 基于以下内容：

@Path("/hello")
public class Hello {
    ...
    @Path("/student")
    @GET
    @Produces(MediaType.TEXT_XML)
    public Student getStudent() {
        return new Student(22,"Name","ABC");
        ...
    }
}

@XmlRootElement(name="RS_Student")

```java
public class Student {
    public int id;
    public String name;
    public String location;

    public Student(){}
    public Student(int id, String name, String location){
        this.id = id;
        this.name = name;
        this.location = location;
    }
}
```

## 128: 如果你使用 URI /hello/student 调用资源方法，输出是什么？

答案：

<RS_Student>

<id>22</id>

<name>Name</name>

<location>ABC</location>

</RS_Student>

# 129: 如果从 Student 类中移除 `@XmlRootElement`，代码还能编译通过吗？如果你使用 URI /hello/student 调用资源方法，输出是什么？

答案：

代码可以正常编译，但在运行时会遇到错误。



当学生资源方法被调用时抛出 `javax.ws.rs.WebApplicationException`。

## JSON

### 130: Jersey 实现如何支持 JSON？

答案：

`Jersey-JSON` 模块包含了一组 `JAX-RS MessageBodyReader<T>` 和 `MessageBodyWriter<T>` 提供者，它们为 RESTful Web 服务提供了 JSON 支持。

### 131: Jersey 实现是否提供了基于 JAXB 的 JSON 支持？什么时候应该使用这种方法？

答案：

是的。Jersey 支持基于 JAXB 的方法，当你想要利用某些 JAXB 特性时就应该使用它。

### 132: 请列出 Jersey 支持的 JSON 方式。

答案：

Jersey 支持基于 POJOs、JAXB 以及 `JSONObject`/`JSONArray` 的 JSON 支持。

### 133: 当你在资源方法中想要将任何 Java 对象映射为 JSON 并反之时，使用哪种 JSON 方式？

答案：

POJO 方式。

### 134: 在资源方法中使用基于 JAXB 或 JSONObject/JSONArray 的 JSON 支持有什么局限性？

答案：

当你在资源方法中使用基于 JAXB 或 `JSONObject` / `JSONArray` 的 JSON 支持时，资源方法可以消费和产生的 Java 类型非常有限。

### 135: 假设你想使用 Jersey JSON POJO 支持在资源方法中将 JAVA 对象映射为 JSON 并反之。你会如何启用它？

答案：

需要将 `JSONConfiguration.FEATURE_POJO_MAPPING` 参数设置为 `TRUE`。这可以通过 `web.xml` 实现。

### 136: 给出一个在客户端侧配置 POJO 映射特性的示例。

答案：

将使用 `DefaultClientConfig`，通过在 features 中将 `JSONConfiguration.FEATURE_POJO_MAPPING` 设置为 `true` 来配置 POJO 支持。例如：

```java
ClientConfig config = new DefaultClientConfig();
config.put(JSONConfiguration.FEATURE_POJO_MAPPING, Boolean.TRUE);
Client myClient = Client.create(config);
```

### 137: 给出一个使用 servlet 初始化参数在 web.xml 中启用 JSONConfiguration.FEATURE_POJO_MAPPING 的示例。

答案：

```xml
<init-param>
  <param-name>com.sun.jersey.api.json.POJOMappingFeature</param-name>
  <param-value>true</param-value>
</init-param>
```

### 138: 请列出 Jersey 中让产生/消费 JSON 和 XML 数据更容易的 JSON 方式？

答案：

JAXB JSON 方式节省了大量时间，因为它确实让开发者产生/消费 JSON 和 XML 数据变得更加简单。它是简单的，因为带有 JAXB 注解的 POJOs 被视为简单的 JAVA beans。

### 139: 在哪种情况下，Jersey 的 JAXB JSON 方式不是首选？

答案：

当我们需要处理非常特定的 JSON 格式时，Jersey 的 JAXB JSON 方式并不理想。原因在于很难找到合适的方法来产生和消费非常特定的格式。

### 140: 给出一个可以与 JAXB JSON 方式配合使用的 JAXB Bean 示例。

答案：

用于 JSON 的 JAXB bean 只是带有 JAXB 注解的 JAVA Bean。例如：

```java
@XmlRootElement
public class TestBean {
    public String name;
    public int id;

    public TestBean() {}
    public TestBean(String name, int id) {
        this.name = name;
        this.id = id;
    }
}
```

### 141: 如何从资源方法产生 JSON？

答案：

资源方法可以注上 `@Produces("application/json")` 注解以产生 application / JSON 响应。

```java
@GET
@Produces("application/json")
public MyTestBean getMyBean() {
    return new TestBean("abc", 1);
}
```

其中 `TestBean` 是一个带有 JAXB 注解的 bean。

问题 142, 143, 144 是基于以下带有 JAXB 注解的类：

```java
@XmlRootElement
public class TestBean {
    public String name;
    public int id;

    public TestBean() {}
    public TestBean(String name, int id) {
        this.name = name;
        this.id = id;
    }
}

@Path("/hello")
public class Hello {
...
@GET
@Path("/json")
@Produces("application/json")
public MyJaxbBean getMyBean() {
    return new TestBean("abc", 1);
}
```

### 142: 如果请求的 URL 是 /hello/json，结果是什么？

答案：

`"name":"abc", "id":"1"`

### 143: 在 TestBean 类中进行什么修改可以从 JSON 响应中移除 id？

答案：

`id` 字段可以注上 `@Transient`。

```java
@Transient
public int id;
```

### 144: 如何使用 JAXB 调整 JSON 格式将 JSON 响应中的 'name' 更改为 'app-name'？

答案：

在 `TestBean` 中，我们必须对 `name` 注上 `@XmlElement(name="app-name")`。

```java
@XmlElement(name="app-name")
public String name;
```

### 145: 如何为 TestBean 添加命名空间？

答案：

```java
@XmlElement(namespace="mynamespace")
public class TestBean {
...
```

### 146: 列出可以使用 JSONConfiguration 以不同方式序列化 JSON 的 JSON 方式。

答案：

通过 `JSONConfiguration`，可以使用以下 JSON 方式：`MAPPED`, `NATURAL`, `JETTISON_MAPPED`, `BADGERFISH`。

### 147: 请列出 JSONConfiguration 的默认 JSON 方式。

答案：

`JSONConfiguration` 的默认 JSON 方式是 `MAPPED`。

### 148: 使用哪种 JSONConfiguration 的 JSON 方式可以避免手动工作并确定如何处理单个项目？

答案：

`NATURAL`。

### 149: 使用 NATURAL 方式，数组和列表将被映射为什么？

答案：

JAVA 数组和列表。

### 150: 假设你在使用 NATURAL 方式且你的资源方法返回数字和布尔值。它们将被映射为什么？

答案：

JAVA 数字和布尔值。

### 151: 使用 JSONConfiguration 的 NATURAL 方式时不需要关心 XML 属性，属性名称是什么？

答案：

原始名称 (Original names)

### 152: 如何告诉 RESTful 资源使用自然 JSON？

答案：

```java
JSONConfiguration.natural().build();
```

### 153: 哪种 JSON 方式从 JavaScript 角度最难读？

答案：

Badgerfish 方式。

### 154: 如果 Badgerfish JSON 方式从 JavaScript 角度最难读，你为什么要使用它？

答案：

当我们需要确保 JAXB bean 可以完美地写入 JSON，而不关心任何格式、命名空间等时，它是用的。

### 155: 如何使用 Badgerfish 方式构建 JSONConfiguration 实例？

答案：

```java
JSONConfiguration.badFish().build();
```

### 156: 在 RESTful 资源中使用底层 JSON 支持时使用哪些类？

答案：

使用底层 JSON 支持时，RESTful 资源使用 `JSONObject` 和 `JSONArray` 类。这些类是 Jison 项目的一部分。

### 157: 在 RESTful 资源中使用底层 JSON 支持有什么优势？

答案：

使用底层 JSON 支持的用处在于我们可以对产生和消费的 JSON 格式拥有完全控制。

### 158: 在 RESTful 资源中使用底层 JSON 支持有什么缺点？

答案：

在 RESTful 资源中使用底层 JSON 支持意味着开发者将处理数据模型对象，与使用 JAXB 方式相比这是一项复杂的任务。

### 159: 给出一个构造 JSONObject 的示例？

答案：

构造 JSON 对象比构造带有 JAXB 注解的 bean 实例更复杂。

```java
JSONObject myObject = new JSONObject();
try {
    myObject.put("name", "MyName");
    myObject.put("age", 22);
} catch (JSONException ex) {
    //log it
}
```

## Links

### 160: 既然 RESTful API 必须由超文本驱动，JAX-RS 提供了哪个类来简化 URI 创建？

答案：

`UriBuilder`

### 161: 除了 UriBuilder，还提供了哪个 Jersey 注解支持 URI 创建？

答案：

Jersey 提供了用于实体类字段的 `@Ref` 注解。

### 162: 如果使用 Jersey 的 @Ref 注解创建 URI，适当的 URI 何时如何注入字段的？

答案：

Jersey 负责将适当的 URI 注入字段，并在序列化之前由 message body writer 完成。

声明式超链接支持以过滤的形式提供。首先，应用程序必须声明对 `jersey-server-linking` 模块的依赖：

```xml
<dependency>
  <groupId>com.sun.jersey</groupId>
  <artifactId>jersey-server-linking</artifactId>
  <version>${jersey-version}</version>
</dependency>
```

### 163: Jersey 如何提供声明式超链接支持？

答案：

通过过滤器的形式提供。应用程序必须声明对 `jersey-server-linking` 模块的依赖。

```xml
<dependency>
  <groupId>com.sun.jersey</groupId>
  <artifactId>jersey-server-linking</artifactId>
  <version>${jersey-version}</version>
</dependency>
```

然后必须在应用程序中安装该过滤器。

### 164: 如何在 web.xml 中为应用程序安装声明式超链接过滤器？

答案：

可以使用 `init-param` 实现。例如：

```xml
<init-param>
  <name>com.sun.jersey.spi.container.ContainerResponseFilters</name>
  <param-value>com.sun.jersey.server.linking.LinkFilter</param-value>
</init-param>
```

### 165: 假设你想使用注解向响应中添加 HTTP Link 头部。你正在使用 Jersey 实现。你将如何实现这一点？

答案：

我们必须对字段使用 `@Link` 注解，以便在响应中插入 HTTP Link 头部。例如：

```java
@Link(
    value=@Ref("widgets/${resource.nextId}"),
    rel="next"
)
```

`@Ref` 注解的属性可以如上所示。

### 166: 可以使用 @Links 注解添加多个 link 头部吗？

答案：

是的，支持。

## J-RS Client - Jersey Client API

### 167: 为什么基于 Java 的 API 不是编写 RESTful 客户端的理想选择？

答案：

基于 Java 的 API 关注请求和响应的客户端-服务器约束。它们关注 URI 标识的资源，而 URI 是 RESTful 服务的关键。

### 168: 写出基于 Java 的客户端 API。

答案：

`Apache HTTP client API`, `java.net.HttpURLConnection` 等。

### 169: 使用 Jersey client API，哪个 JAVA 类封装了 URI？

答案：

使用 Jersey client API 时，资源由 `WebResource` 实例表示，它封装了 URI。

### 170: 在使用 Jersey client API 时，将资源表示为 JAVA 类型有什么好处？

答案：

如果将资源表示为 JAVA 类型，那么配置、传递和注入该资源将变得非常容易。

### 171: Jersey Client API 如何安全地构建 URI？

答案：

它使用 `UriBuilder` 和 `UriTemplate` 来安全地构建 URI。

### 172: Jersey Client API 支持哪些 JAVA 类型？

答案：

支持 `byte[]`, `String`, `InputStream`, `File`, `DataSource`, JAXB beans。Jersey Client API 还有对 JSON 和 MIME Multipart 的支持。

### 173: Jersey Client API 如何利用已有的 Apache HTTP client 或 java.net.HttpURLConnection 实现？

答案：

Jersey Client API 提供了对封装 `HttpURLConnection` 和 Apache HTTP client 的支持，从而防止用户为简单任务编写过代码。

### 174: 是否可以使用 Apache HTTP client 向 RESTful 资源发送 POST 请求？

答案：

可以。可以实现，但使用 Jersey Client API 会简单得多。

### 175: 请给出一个使用 Jersey Client API 向 RESTful 资源发送 POST 请求的示例。

答案：

```java
form = new Form();
form.add("x", "xx");
form.add("y", "yy");

Client c = Client.create();

WebResource r = c.resource("http://localhost:8089/form");
JAXBBean bean = r.type(MediaType.APPLICATION_FORM_URLENCODED_TYPE).accept(MediaType.APPLICATION_JSON_TYPE).post(JAXBean.class, form);
```

### 176: 使用 Jersey Client API 向 Web 资源发送 post 请求时，你是否为 Form 实例编写了序列化代码？

答案：

不需要。这由 API 处理。

### 177: 创建 Jersey Client 实例并配置其以执行自动重定向。

答案：

```java
Client c = Client.create();
c.getProperties().put(ClientConfig.PROPERTY_FOLLOW_REDICTS, true);
```

### 178: 如何使用 ClientConfig 对象创建 Jersey Client？

答案：

```java
ClientConfig cc = new DefaultClientConfig();
cc.getProperties().put(ClientConfig.PROPERTY_FOLLOW_REDICTS, true);
Client c = Client.create(cc);
```

### 179: 使用 Jersey Client API，何时可以获取 WebResource 实例？

答案：

为了获取 `WebResource` 实例，必须先创建并配置 client 实例。

### 180: 给出一个使用 Jersey Client API 创建 URI 为 "http://localhost:8081/abc" 的 Web 资源引用示例。

答案：

```java
Client c = Client.create();
c.getProperties().put(ClientConfig.PROPERTY_FOLLOW_REDICTS, true);
WebResource r = c.resource("http://localhost:8081/abc");
```



# 181: 为什么建议复用配置好的 Client 实例来创建 Web resources？

回答：

优先考虑复用 `Client` 实例，因为 `Client` 实例是昂贵的资源。

# 182: 为什么在多个线程之间共享 Client 实例和 WebResource 实例是安全的？

回答：

由于创建 Web resources、构建请求和接收响应都是线程安全的，因此在多个线程之间共享 `Client` 实例和 `WebResource` 实例是安全的。

# 183: 假设你有一个 WebResource 实例 'r'。你将如何发送带有 application/json、application/xml Accept 头部以及非标准头部 X-FOO 为 test 的 GET 请求？

回答：

```java
String response = r.accept(MediaType.APPLICATION_JSON_TYPE, MediaType.APPLICATION_XML_TYPE).header("X-FOO", "test").get(String.class);
```

# 184: 假设你想向一个具有 JAVA 类型请求实体的资源发送 POST 请求。你将如何发送 POST 请求？

回答：

```java
WebResource r = c.resource("http://localhost:8081/abc");
String request = "hello";
String response = r.accept(MediaType.APPLICATION_JSON_TYPE, MediaType.APPLICATION_XML_TYPE).header("X-FOO", "test").post(JAXBean.class, form);
```

（注：184 的 OCR 文本跨页显示，此处根据标准的 Jersey API 使用方法进行了重构）

## 185: Jersey Client API 中如何处理错误？

回答：

你可以使用 try-catch 块处理 `WebApplicationException` 或执行请求期间抛出的异常。

## 186: Jersey Client API 如何发送自定义头部？

回答：

在 `WebResource` 实例上使用 `.header(name, value)` 方法。

## 187: Jersey Client API 如何处理查询参数？

回答：

在 `WebResource` 实例上使用 `.queryParam(name, value)` 方法。

## 188: Jersey Client API 如何处理路径参数？

回答：

使用带有占位符的 `.path(path)` 方法并调用 `.build()`。

## 189: 如何读取响应？

回答：

使用 `.type(String.class)` 方法，然后调用请求方法 `.get()` 或 `.post()`。

## 190: Client 和 WebResource 的区别是什么？

回答：

`Client` 是用于创建资源的入口，而 `WebResource` 代表特定的资源。

```java
ClientFilter filterC = ...
WebResource r = c.resource(...);
r.addFilter(filterC);
```

## 198: 请求构建完成后，过滤器的应用顺序是什么？

答案：

filterA, filterB 和 filterC

## 199: 接收响应后，过滤器的应用顺序是什么？

答案：

filterC, filterB 和 filterA

## 200: 请列 Jersey Client API 支持的两种过滤器。

答案：

一个 GZIP 内容编码过滤器 (`GZIPContentEncodingFilter`) 和一个日志过滤器 (`LoggingFilter`)。

## 201: Jersey Client API 中 GZIPContentEncodingFilter 的作用是什么？

答案：

`GZIPContentEncodingFilter` 用于压缩 `Content-Encoding` 为 `gzip` 的请求实体。如果响应实体使用 `Content-Encoding: gzip` 压缩，它也会进行解压缩。

## 202: Jersey Client APIs LoggingFilter 的作用是什么？

你最可能被问到的 RESTful Java Web Services 面试题

答案：

`LoggingFilter` 用于将请求和响应头信息记录到声明的输出流中。

## 203: 假设为 Jersey Client APIs LoggingFilter 未声明输出流。LoggingFilter 将会在哪里记录请求和响应头？

答案：

`LoggingFilter` 将在 `System.out` 记录请求和响应头。

本页特意留空

# 人事（HR）面试问题

回顾这些典型的面试题，并思考你会如何回答。阅读列出的答案；你将找到最佳答案以及相关的策略和建议。

# 1: 请描述一次你向同事传达困难或复杂构想的经历。

答案：

先向面试官简要解释该想法，然后概述为什么有必要向同事进一步拆解。最后，用简洁的步骤解释该想法，以便面试官直观看到你的沟通能力和化繁为简的技巧。

# 2: 你发现在什么种情况下沟通比较困难？

答案：

即使是出色的沟通者通常也会发现某些特定情况很难有效沟通，因此不要害怕诚实地回答这个问题。请务必解释你提到的那个特定情况对你来说为什么困难，并尝试选择一个不寻常的答案，例如语言障碍或在困难时期，而不是像“与上级对话”这样的情况。

# 3: 良好沟通的关键要素是什么？

答案：

良好沟通的某些要素包括：不受干扰的环境、听者的反馈，以及说话者在必要时进行的修正或澄清。在必要时参考基础沟通模型，并提议与面试官进行角色扮演演练，以展示你的技能。

# 4: 请讲述一次你通过沟通解决问题的经历？

答案：

在商业世界中，通过沟通解决问题是关键，因此请从你之前的工作中选择一个具体的场景，描述当时你是如何通过冲突中有效沟通来处理混乱局面的。解释情况的背景以及你采取的沟通步骤，并以讨论为什么通过沟通解决问题对最终结果如此重要作为结尾。

# 5: 请讲述一次你与另一同事发生争议的经历。你是如何解决该情况的？

答案：

确保使用一个具体的案例，并逐步说明场景、你采取了什么处理措施，以及最终是如何解决的。中间步骤——即你如何处理争议——显然是最具决定性的——描述你使用的沟通类型，以及你如何通过妥协达成共识。冲突解决是任何员工都应该具备的重要技能，面试官将通过此来判断你卷入争议的概率，以及一旦发生争议，他们被迫介入争议的概率。

# 6: 你是能迅速与人建立关系，还是需要更多时间来了解他们？

答案：

这两个选项都可以展示良好的特质，因此确定哪种风格更适合你。强调你在建立关系时采取的步骤而非特定风格，并简要总结为什么这种方式对你最有效。

# 7: 请描述一次你不得不通过办公室政治来解决问题的经历。

答案：

尝试聚焦于这个问题中的积极方面，以便利用该情况取得优势。不要负面描述你的前任雇主，而是使用一个极小的案例（例如文书工作或个人问题），突出你是如何巧妙地处理特定实例的。举你为了达成结果而使用的沟通技巧或解决问题的能力的例子。

# 8: 请讲述一次你说服他人承担艰巨任务的经历？

答案：

这个问题是一个展示你领导力和沟通能力的机会。虽然提供具体的场景本身作为背景很重要，但要重点放在你是如何说服他人的，以及哪些策略最有效。

# 9: 请讲述一次你成功说服一个群体接受你建议的经历。

你最可能被问到的 RESTful Java Web Services 面试题 99

答案：

这个问题旨在判断你的机变能力和沟通技巧。解释你是如何考虑到群体内部不同视角的，并创建了一份对所有成员都有吸引力和说服力的演示文稿。此外，你还可以通过提供建议本身的细节（展示其执行得有多好）来增强建议的说服力。

# 10: 请讲述一次你与他人发生矛盾的经历。

答案：

这个问题的关键在于展示你已经成长了。最重要的是，告诉面试官你是如何处理的。虽然在面试期间你可能觉得提出自己的要求有些不自在，但雇主希望看到你对所申请的公司正在进行批判性思考，正如他们正对你进行批判性审视一样。

# 11: 请讲述一次你调解员工之间冲突的经历。

答案：

对于那些正在应聘主管角色的人来说，这是一个特别重要的问题——从具体情况开始，并解释你是如何有效沟通的。例如，你是否引入了妥协？你是否做出了行政决策？

# 12: 你最看重的三件事是什么？

答案：

你对职位的前三点期望应该与雇主对员工期望的三点相似，这样就能清楚你与工作非常匹配。例如，雇主想要一个具备良好实践经验的候选人——而你想要一个能够让你充分发挥教育和技能的职位。雇主想要一个愿意接受新挑战并开发新系统以增加销售或生产力的候选人——而你想要一个能推你并提供发展、创造和领导新倡议机会的职位。雇主想要一个能够成长并长期留任的候选人——而你想要一个提供稳定性并相信建立强大团队的职位。在申请之前研究一下雇主在寻找什么，并将你的目标与他们的匹配。

# 13: 你是如何评估你想要加入的公司的？

答案：

面试官想知道你是一个清楚自己想要什么以及如何获得它的人。不要害怕说明你对公司的具体需求（但要尽量确保这些需求与公司匹配——最好在申请之前），并在回答中表现出自信和果断。

# 14: 你能接受 ________ 的薪水为这份工作吗？

答案：

如果这个问题的答案是否定的，这在第一次面试中可能是一个导致交易失败的因素，因为你可能没有很大的还价空间。你可以尝试通过突出你拥有的特定经验以及这如何让你更有胜任力来增加筹码，但要意识到在流程的这一阶段处理这一点非常困难。建议在申请之前了解行业标准，如果可能的话，了解公司标准。

# 15: 你为什么选择上一份工作？

答案：

通过了解引导你选择上一份工作的因素，面试官能够去感受一下激励你的动力类型。请保持这些内容具有职业导向，并对职业生涯早期阶段保持热情，以及你对进入该领域感到多么兴奋。

## 16：你离开上一份工作已经多久了？为什么？

回答：

务必对所有的职业空窗期准备好解释，并确保这是一个专业的理由。不要提到你在找工作时可能遇到的困难，而要关注积极的方面，例如追求业外兴趣，或者回到学校接受进深教育。

## 17：你还在寻找其他类型的职位？

回答：

这个问题的答案可以向面试官展示你正处于人才市场上且很有需求。提到你申请过或看过的与你领域密切相关、或与你正在面试的职位相似的工作。不要提到那些为了走投无路申请的与你领域完全无关的兼职。

## 18：你曾在工作中受过纪律处分吗？

回答：

希望答案否——但如果你确实在工作中因为某些事情受到过处分，请务必确保能够彻底解释。详细说明你从该情况中学习到了什么，并反思在这个过程中你是如何成长的。

## 19：你的时间安排是怎样的？

回答：

你的时间安排显然应该尽可能开放，任何时间上的空隙都应该得到解释和说明。避免询问假期或私假（以及其他福利），并向面试官传达你对工作的严谨态度。

## 20：我可以联系你的现任雇主吗？

回答：

如果可能，让面试官联系你的现任雇主作为证明是最好的。然而，如果不联系你的雇主很重要，请委婉地解释原因，例如你刚开始找工作，还没有机会通知他们你正在寻找其他工作。不过要谨慎使用这个理由，因为雇主可能会怀疑你是否在他们这里工作的同时寻找更好的机会。

## 21：你是否有任何可以为我们业务带来价值的人脉？（此处应为：你是否有任何可以为我们业务带来价值的贵人脉？）

回答：

如果你能带来知识、人介绍或其他新雇主可以建立人脉的其他联系，那就太棒了。但是，请确保你没有提供任何前任雇主的客户，或以任何方式违反合同协议。

## 22：你多久可以开始工作？

回答：

虽然你希望确保如果公司对雇用你有兴趣可以尽快开始工作，但如果你还有另一份工作，请务必至少提前两周通知。虽然你的新雇主可能急于让你开始，但他们会希望雇佣一个因给予充分通知而受重的员工，这样他们就不必担心你最终会把他们陷入困境。

## 23：你的上任雇主会说你是为什么离开的？

回答：

这个问题的关键在于，雇主的回答必须和你对离开原因的回答一致。例如，如果你告诉雇主你离开是为了寻找一个职业晋升机会更大的职位，那么你的雇主最好不要说你是因为缺勤太多而被解雇的。诚实是你求职过程中的关键。

## 24：你积极寻找工作多久了？

回答：

如果你没有积极找工作很长时间，那是最好的，因为时间太长可能会面试官怀疑为什么没有其他人雇佣过你。如果已经过了一段时间，请务必解释原因，并保持积极。也许你还没有遇到许多能为你提供足够挑战，或与你的教育背景和经验充分匹配的机会。

## 25：当你没来上班时怎么办？

回答：

显然，唯一可以接受的缺勤时间是真正的紧急情况或你真的病了——所以现在不要开始提到你计划因假期或家庭生日而缺勤的时间。或者，你可以告诉面试官你对工作有多么投入，你如何总是努力全身心投入，并在每次上班时都投入相同的工作，即使在你感到身体微不适时。

## 26：你缺勤最常见的原因是什么？

回答：

如果你有一个经常性缺勤的原因，现在是揭露它的时候了——但在面试期间这样做会对你的个人形象产生负面影响。理想情况下，你只会在极端疾病或其他紧急情况下缺勤。

## 27：你的出勤记录情况如何？

回答：

务必诚实地回答这个问题，但理想情况下，你已经付出了努力来证明你很少缺勤或迟到这一事实。然而，如果你的出勤有空隙，请用适当的原因简要解释它们，确保强调你对工作的投入和可靠性。

## 28：你从哪里听到这个职位的？

回答：

这看起来像是一个简单的问题，但答案实际上可以反映你的很多信息。如果你是由朋友或在该公司的其他员工推荐的，这是一个提到你人关系的绝佳机会（如果那人的表现良好！）。然而，如果你是从招聘会或工作安置中介等地听说的，你可能希望关注你发现如此绝佳的机会有多高兴。

## 29：在做用人决定时，还有什么你想让我知道的吗？

回答：

这是你向面试官进行最后推销自己的绝佳机会——利用这段时间提醒面试官你为什么胜任该职位，以及你能为公司带来什么其他人无法提供的价值。表达你对为一家追求 X 任务的公司工作的感到兴奋。

## 30：告诉我一次你没有满足截止日的经历。

回答：

理想情况下，这没有发生过——但如果发生了，请确保你使用一个较小的例子来说说明情况，强调那是多久以前的事，并确保你已经尽所能确保了截止日期。此外，务必包括你在更好地管理时间或优先考虑任务方面学到了什么，以满足未来所有的截止日期。

## 31：你在工作时如何消除干扰？

回答：

随着技术的进步和通信的便利，新的干扰每天都在产生。你的面试官想要看到你仍然能够专注于工作，并且你的生产力没有受到影响，通过一个展示你为了保持任务状态而采用的常规流程示例。

## 32：告诉我一次你在每周或每月有配额需要完成工作的经历。你成功的频率有多高？

回答：

你的数据会说明一切，你必须诚实地回答这个问题。如果你经常能达到配额，请务必以自信的方式强调这一点，并且不要羞于指出你在这一方面的优势。如果你的统计数据并不理想，尝试指出它们在你雇佣期结束时有所增加的趋势，并对未来可以如何改进的方法进行反思。

## 33：告诉我一次你满足了一个艰难的截止日的经历，以及你是如何完成它的。

回答：

解释你是如何优先考虑任务的，或者如何将任务的部分分配给其他团队成员，以应对艰难的截止日期。具体说明截止日期为什么艰巨可能会有益——请确保这不是你个人拖延的结果。最后，解释你是如何成功满足截止日的，以及最终实现目标付出了什么。

## 34：当你手头有多个项目时，你如何保持组织有序？

回答：

面试官将希望查看你是否能够管理时间并良好工作——能够同时处理多个项目并仍然给每个项目提供应有的关注，是员工能力的极佳标志。描述一个典型的目标设定和优先级排序流程，并将这些步骤解释给面试官，以便他或她能看到你是如何管理时间的。

## 35：在工作日期间你有多少时间是处于“自动驾驶”状态的？

回答：

虽然你可能好奇雇主是否在通过这个问题来查看你的效率（例如，工作得太精通以至于不需要思考），但在几乎所有情况下，雇主都希望看到你不断思考、分析和处理正在发生的事情。

职场。即使一切进展顺利，通常在某些地方也有提高效率、增加销售额或生产力的机会。强调你对持续发展的投入，并传达出处于“自动驾驶”状态不利于实现那类成功。

## 36: 你是如何处理截止日期的？

回答：

处理紧迫截止日期最重要的部分是对任务进行优先级排序并设定完成目标，以及委派或消除不必要的工作。引导面试官进入一个通用场景，通过你组织和设定优先顺序的能力来展示你的胜任能力，最重要的是要保持冷静。

## 37: 请谈谈你个人的解决问题流程。

回答：

你的个人解决问题流程应该包括概述问题、提出可能的解决方案，以及制定一个通向解决的清晰行动计划。保持回答简洁且有条理，并用简洁、冷静的方式解释这些步骤，显示出即使在压力下也能保持头脑。

## 38: 工作中哪些事情会让你感到压力？

回答：

由于最好远离负面因素，请保持这个回答简明扼要。虽然回答工作中没有任何事情会让你感到压力在面试官看来可能不太可信，但请将答案控制在一个通用的原则上，例如团队成员没有履行承诺时，然后专注于你通常采用的应对这种压力的解决方案，例如召开每周状态会议或在项目过程中设置间歇性的截止日期。

## 39: 你对某事感到压力时看起来是什么样的？你是如何解决的？

回答：

这是一个陷阱题——面试官想听到的是你在压力大时看起来没有变化，并且你不会让负面情绪干扰你的生产力。至于你如何解决压力，最好是你掌握一个简单的解决方案，例如只需深呼吸并数到 10，以此迫使自己重新回到手头的任务中。

## 40: 你能同时处理多个任务吗？

回答：

有些人可以，有些人则不行。多任务处理最重要的部分是始终保持头脑清醒，知道需要做什么，以及每个任务属于什么优先级。解释你如何评估任务以确定优先级，以及你如何管理时间以确保所有任务都能高效地完成。

## 41: 你每周工作多少小时？

你最可能被问到的 RESTful Java Web 服务面试题

回答：

很多人会被这个问题误导，认为回答小时数越多越好——然而，这可能会让雇主怀疑，为什么你必须工作这么多小时才能完成其他人在更短时间内就能完成的工作。对你完成一项工作所需的时间给出一个合理的估算，并解释你在需要时也愿意额外工作。

## 42: 你每天检查多少邮箱？

回答：



虽然雇主希望看到你紧跟现代技术，但你每天检查邮件的次数相对较低也同样重要——也许每天二到三次（取决于你所在的具体领域）。在职场中，检查邮件往往是一个极大的分心之物，虽然保持联系很重要，但很多往来邮件完全可以简单地在早上和下午集中处理。

## 43: 请谈谈一次你为了完成项目而额外加班的经历。

**回答：**

让雇主看到你对工作充满投入，并在需要或工作要求时愿意投入额外时间，是非常重要的。然而，在解释你为什么被要求加班时要小心——例如，你是否是因为在过程早期的目标设定不当而导致必须留晚？或者从更积极的角度来看，你是否是因为客户在短时间内要求提前截止日期而加班？强调你的能力以及每次都付出 110% 努力的意愿。

## 44: 请谈谈一次你的表现超出职位职责和要求的经历。

**回答：**

如果你是该职位的优秀候选人，这应该是一个容易回答的问题——选择一个你真正超越了职责范围、付出了额外工作或自愿承担新责任的时刻。保持谦虚，对学习机会表示感谢，并对自己能够再次这种表现表示信心。

## 45: 你的驱动力是什么？

**回答：**

如果你是该职位的优秀候选人，这应该是一个容易回答的问题——选择一个你真正超越了职责范围、付出了额外工作或自愿承担新责任的时刻。保持谦虚，对学习机会表示感谢，并对自己能够再次这种表现表示信心。

## 46: 你接受反馈吗？

**回答：**

很多人会被这个问题误导，认为回答小时数越多越好——然而，这可能会让雇主怀疑，为什么你必须工作这么多小时才能完成其他人在更短时间内就能完成的工作。对你完成一项工作所需的时间给出一个合理的估算，并解释你在需要时也愿意额外工作。

## 47: 描述你典型的一天。

**回答：**

虽然雇主希望看到你紧跟现代技术，但你每天检查邮件的次数相对较低也同样重要——也许每天二到三次（取决于你所在的具体领域）。在职场中，检查邮件往往是一个极大的分心之物，虽然保持联系很重要，但很多往来邮件完全可以简单地在早上和下午集中处理。

## 48: 请谈谈一次你超越要求的。

**回答：**

让雇主看到你对工作充满投入，并在需要或工作要求时愿意投入额外时间，是非常重要的。然而，在解释你为什么被要求加班时要小心——例如，你是否是因为在过程早期的目标设定不当而导致必须留晚？或者从更积极的角度来看，你是否是因为客户在短时间内要求提前截止日期而加班？强调你的能力以及每次都付出 110% 努力的意愿。

## 49: 你接受批评吗？

**回答：**

这是一个陷阱题——面试官想听到的是你在压力大时看起来没有变化，并且你不会让负面情绪干扰你的生产力。至于你如何解决压力，最好是你掌握一个简单的解决方案，例如只需深呼吸并数到 10，以此迫使自己重新回到手头的任务中。

## 50: 什么能激励了你？

**回答：**

你可能会从自然、阅读或掌握一项困难的任务中获得灵感。保持冷静是重要的。

## 51: 你如何激励他人？

**回答：**

这是一个陷阱题——面试官想听到的是你在压力大时看起来没有变化，并且你不会让负面情绪干扰你的生产力。至于你如何解决压力，最好是你掌握一个简单的解决方案，例如只需深呼吸并数到 10，以此迫使自己重新回到手头的任务中。

## 23: 嵌入变量在 URI 语法中是如何表示的？

## 24: 如何在 RESTful 资源中获取方法参数的值？

## 25: 如何为变量（例如 `username`）定义正则表达式？

## 26: 如果 URI 嵌入变量的正则表达式没有匹配成功，会发生什么？

## 27: 以下内容会指向同一个资源吗？

## 28: 解释如何指定发送到客户端的资源的 MIME 媒体类型（MIME media types）？

## 29: `@Produces` 只能应用于方法级别 true 吗？

## 30: 在 RESTLess 资源中可以覆盖 `@Produces` 注解吗？请出一个示例。

## 31: 如何在同一个 `@Produces` 声明中声明多个媒体类型？

## 32: 假设有一个资源类能够为 GET 请求产生多个 MIME 媒体类型。将如何选择响应？

## 33: 你将如何指定 RESTful 资源可以使用的表示的 MIME 媒体类型？

## 34: 编写一个在 POST 请求时触发并接受 `text/plain` 作为输入的方法。

## 35: `@Consumes` 可以应用于哪些级别？

## 36: 给出一个在 `@Consumes` 声明中声明多个媒体类型的示例？

## 37: RESTful Web 服务支持多种类型的响应（MIME）格式吗？

## 38: RESTful 服务通常支持哪两种响应格式？

## 39: 在设计 RESTful Web 服务时，什么构成了系统的资源？

## 40: HATEOAS 是什么意思？

## 41: 定义统一接口约束（Uniform Interface Constraint）？

# 部署 RESTful Web 服务

## 42: 写出用于声明根资源的 JAX-RS 部署无关抽象类。

## 43: 如何使用 JAX-RS `Application` 类声明根资源和提供者（provider）类？

## 44: 给出一个使用 `@ApplicationPath` Servlet 3.0 的 JAX-RS 应用部署示例。

## 45: 如何在 `pom.xml` 中为 Servlet 3.0 配置 `maven-war-plugin`？

## 46: 是否可以在 `web.xml` 中声明 JAX-RS 应用的细节？

## 47: 你将如何在 `web.xml` 中声明 JAX-RS 应用的细节？

## 48: 使用 Servlet 3.0 扩展机制声明 RESTful 资源，`web.xml` 中使用哪个元素来定义基础资源 URI？

## 49: 你正在使用 Servlet 2.x 并在 `web.xml` 中声明 Jersey 特定的 servlet。你将如何配置它？

## 50: 你正在使用 `ServletConfig` 2.x，并通过在 `web.xml` 中声明包让 Jersey 自动选择 `PackagesResourceConfig` 实现。你将如何配置它？

# 请求参数

## 51: 基于参数的注解目的是什么？

## 52: 你将使用哪个注解从请求 URL 的 Query 组件提取查询参数（query parameters）？

## 53: 如何声明资源方法参数的默认值？

## 54: 如果请求 URL Query 组件中的查询参数无法解析为资源方法参数，会发生什么？

## 55: 资源方法参数的查询参数只能使用基本类型吗？

## 56: 查看以下资源方法。如果请求中不存在查询参数，资源方法参数 `id` 的值是多少？

## 57: 查看以下资源方法。如果请求中不存在查询参数，资源方法参数 `firstName` 的值是多少？

## 58: 如果没有指定默认值且请求中不存在必要参数，类型为 `List<T>` 的资源方法参数设置了什么默认值？

## 59: 写出用于从 URL 路径段中提取信息的基于参数的注解名称？

## 60: 使用哪些基于参数的注解来从 HTTP 请求头中提取信息？

## 61: 写出用于与 cookie 相关的 HTTP 头提取信息的基于参数的注解名称？

## 62: 你想获取 HTML 表单 POST 的参数作为资源方法的参数。你更倾向于使用哪个注解？

## 63: 给出一个处理 POST 的 HTML 表单的资源方法示例？

# 响应

## 64: 可以从资源方法向 HTTP 请求返回响应吗？

## 65: 编写一个资源方法，响应 Post 请求，消耗 `application/xml` 并向自定义响应中添加实体体？

# 子资源

## 66: 定义根资源类（root resource classes）？

## 67: `@Path` 可以用于根资源类的方法上吗？

## 68: 当请求 URL 为 `/cars` 时，调用哪个方法？

## 69: 你将使用哪个请求 URL 来调用 `getMakes()` 资源方法？

## 70: 哪个方法会在请求 URL `/cars/model` 被调用时响应？

## 71: 当请求 URL 为 `/cars/test` 时，调用哪个方法？

## 72: 如果请求 URL 为：`/hello/testparam`，结果会是什么？

## 73: 如果请求 URL 为：`/hello/testparam?name=MyFirstName`，结果会是什么？

## 74: 为了得到结果 `MyFirstName MyLastName`，请求 URL 应该是什么？

## 75: 什么是子资源定位方法（sub-resource locator methods）？

## 76: 子资源定位方法的示例。

## 77: JAX-RS 支持条件 GET 和 PUT HTTP 请求吗？

## 78: 条件 GET 和 PUT HTTP 请求有什么用处？

## 79: 假设静态内容自上一个请求以来没有变化。请求应该是怎样的？

## 80: 如果请求 URL 为：`/hello/testparam`，结果会是什么？

## 81: 导致 412 Precondition Failed 响应的正确方法是什么？

## 82: 你将指定 RESTful 资源可以使用的表示的 MIME 类型？

## 83: `@Consumes` 可以应用于哪些级别？

## 84: RESTful Web 服务支持多种响应（MIME）格式吗？

## 85: RESTful 服务通常支持哪两种响应格式？

## 86: 给出一个在 `@Consumes` 声明中声明多个媒体类型的示例？

## 87: 假设有一个资源类能够为 GET 请求产生多个 MIME 媒体类型。将如何选择响应？

## 88: 如果请求中不存在查询参数，资源方法参数 `id` 的值是多少？

## 89: 如果请求中不存在查询参数，资源方法参数 `firstName` 的值是多少？

## 90: 如果没有指定默认值且请求中不存在必要参数，类型为 `List<T>` 的资源方法参数设置了什么默认值？

## 91: 写出用于从 URL 路径段中提取信息的基于参数的注解名称？

## 92: 使用哪些基于参数的注解来从 HTTP 头中提取信息？

## 93: 写出用于与 cookie 相关的 HTTP 头提取信息的基于参数的注解名称？

## 94: 你想获取 HTML 表单 POST 的参数作为资源方法的参数。你更倾向于使用哪个注解？

## 95: 给出一个 POST 的 HTML 表单的资源方法示例？

# 构建 URI

## 96: 可以从资源方法向 HTTP 请求返回响应吗？

## 97: 编写一个资源方法，响应 Post 请求，消耗 `application/xml` 并向自定义响应中添加实体体？

## 98: 使用 `java.net.URI` 构建 URI 是否安全方便？

## 99: 应该使用哪个 JAX-RS 类来构建 URI？

## 100: `javax.ws.rs.core.UriBuilder` 只能用于构建 URI 吗？

## 101: 你通常如何构建 URI？

## 102: 如何在资源类中获取 `UriInfo`？

## 103: 如果你有 `UriInfo`，你会得到什么 URI？

## 104: 如果从请求中减去查询组件，你会得到什么？

## 105: 给出一个使用查询参数构建 URI 的示例。

# 你可能会被问到的 RESTful Java Web 服务面试题

## 117: 哪个 JAX-RS 注解用于获取请求或响应相关的 JAVA 类型？

## 118: 如何获取有关请求头（request headers）和 Cookie 的信息？

## 119: 你希望获取有关请求 URI 组件的信息。哪个接口可以为你提供这些信息？

## 120: 哪个注解用于从 HTML 表单提取表单参数？

## 121: 一个表单正向你的资源提交一个名为 `name` 的 HTML 字段。编写一个提取该名称的资源方法？

## 122: 编写一个资源方法获取提交到它的表单参数映射（map）。

## 123: 编写一个包含以下请求的资源方法：`GET /employee?name=abc&age=33`

## 124: 什么是 URI 路径模板（URI path templates）？

## 125: 如何在你的资源方法中使用变量 URI 路径片段？

## Jersey

## 126: Jersey 使用什么来解析传入的请求？

## 127: Jersey 使用什么来创建输出的响应？

## 128: 如果使用 URI: `/hello/student` 调用学生资源方法，输出将是什么？

## 129: 如果从 `Student` 类中删除 `@XmlRootElement`，代码还能编译吗？如果使用 URI: `/hello/student` 调用学生资源方法，输出将是什么？

## JSON

## 130: Jersey 的实现如何支持 JSON？

## 131: Jersey 实现是否提供了基于 JAXB 的 JSON 支持？什么时候应该使用这种方法？

## 132: 列出 Jersey 支持的 JSON 处理方法。

## 133: 在 Web资源方法中，当你想要将任何 JAVA 对象映射到 JSON 以及反之时，使用哪种 JSON 处理方法？

## 134: 在 Web资源方法中使用 JAXB 或 `JSONObject` / `JSONArray` JSON 支持的局限性是什么？

## 135: 假设你想在 Web资源方法中使用 Jersey 的 POJO JSON 支持将 JAVA 对象映射到 JSON 并反之。你将如何启用它？

## 136: 给出一个在客户端配置 POJO 映射特性的示例。

## 137: 给出一个在 `web.xml` 中使用 servlet 初始化参数启用 `JSONConfiguration.FEATURE_POJO_MAPPING` 的示例。

## 138: 列出 Jersey 的哪种 JSON 处理方法可以更容易生成/消费 JSON 和 XML 数据？

## 139: 在什么场景下，不倾向于使用 JAXB JSON 方法？

## 140: 给出一个可以与 JAXB JSON 方法配合使用的 JAXB Bean。

## 141: 你如何从请求的方法生成 JSON？

## 142: 如果请求的 URL 是：`/hello/json`，结果将是什么？

## 143: 你会在 `TestBean` 类中做什么修改，以便从 JSON 响应中移除 `id`？

## 144: 你将如何通过使用 JAXB 调整 JSON 格式，以便将 JSON 响应中的属性 `name` 改为 `app-name`？

## 145: 如何为 `TestBean` 添加命名空间（namespace）？

## 146: 列出可以配合 `JSONConfiguration` 以不同方式序列化 JSON 的 JSON 标记。

## 147: 默认 `JSONConfiguration` 的 JSON 标记是为了避免手动操作并确定如何处理各个项目吗？

## 149: 使用 NATURAL JSON 标记，JAVA 数组和列表将如何被映射？

## 150: 假设你正在使用 NATURAL JSON 标记，并且你的资源方法返回一个包含 JAVA 数字和布尔值的实例。它们将被映射为什么？

## 151: 由于在使用 `JSONConfiguration` 的 NATURAL 标记时不需要关心 XML 属性，返回的属性名称将是什么？

## 152: 如何告诉你的 RESTful 资源使用 NATURAL JSON 标记？

## 你可能会被问到的 RESTful Java Web 服务面试题

## 153: 从 JavaScript 的角度来看，哪种 JSON 标记可视性最差？

## 154: 如果 Badgerfish JSON 标记从 JavaScript 角度来看可视性最差，为什么要使用它？

## 155: 如何使用 Badgerfish 标记构建 `JSONConfiguration` 实例？

## 156: 在 RESTful 资源中使用低级 JSON 支持时，使用了哪些类？

## 157: 在 RESTful 资源中使用低级 JSON 支持有什么优势？

## 158: 在 RESTful 资源中使用低级 JSON 支持有什么劣势？

## 159: 给出一个构造 `JSONObject` 的示例？

## 链接

## 160: 既然 RESTful API 是超文本驱动的，JAX-RS 提供了哪个类来简化 URI 的创建？

## 161: 除了 `UriBuilder`，还提供了哪个 Jersey 注解来支持 URI 创建？

## 162: 如果使用 Jersey 的 `@Ref` 注解创建 URI，适当的 URI 是何时以及如何注入到字段中的？

## 163: Jersey 如何提供对声明式超链接（declarative hyperlinking）的支持？

## 164: 你如何在 `web.xml` 中为你的应用程序安装声明式超链接过滤器？

## 165: 假设你想使用注解向响应中添加 HTTP Link 头部。你正在使用 Jersey 实现。你将如何实现这一点？

## 166: 能通过使用 `@Links` 注解添加多个 link头部吗？

## JAX-RS Client - Jersey Client API

## 167: 为什么基于 JAVA 的客户端 API 不是编写 RESTful 客户端的理想选择？

## 168: 列出基于 JAVA 的客户端 API。

## 169: 使用 Jersey client API，哪个 JAVA 类封装了 URI？

## 170: 在使用 Jersey client API 时，将资源表示为 JAVA 类型有什么好处？

## 你可能会被问到的 RESTful Java Web 服务面试题

## 171: Jersey Client API 如何安全地构建 URI？

## 172: Jersey Client API 支持哪些 JAVA 类型？

## 173: Jersey Client API 如何使用 `java.net.HttpConnection`？

## 174: 是否可以使用 Apache HTTP client 向 RESTful 资源发送 POST 请求？

## 175: 使用 Jersey client API 给出一个 POST 请求的示例。

## 176: 在发送 POST 请求时，如何编写 Form 序列化？

## 177: 创建一个 `Client` 实例并配置自动重定向。

## 178: 如何使用 `ClientConfig` 创建 `Client`？

## 179: 使用 Jersey client API 何时可以获取 `WebResource` ？

## 180: 使用 Jersey client API 创建指向 `http://localhost:8081/abc` 的。

## 181: 为什么建议复用 `Client` 实例来创建 `WebResources`？

## 182: 在多个线程之间共享 `Client` 实例和 `WebResource` 实例安全吗？

## 183: 假设你有 `WebResource` 实例 `r`。如何发送一个 Accept 为 `application/json`、`application/xml` 以及非标准头部 `X-FOO` 为 `test` 的 GET 请求？

## 184: 假设你想发送实体为 JAVA 类型的 POST 请求。



# RESTful Java Web 服务面试题

## 核心问题

185: 如果未使用 `ClientResponse` 类型且响应状态大于或等于 300，会抛出什么异常？

186: 如果未使用 `ClientResponse` 类型且响应状态大于或等于 300，你将如何获取 `ClientResponse`？

187: 如何从 `WebResource` 创建新的 `WebResources`？

188: 给出一个以字节流处理响应实体的示例？

189: 为什么在字节流读取响应实体后关闭输入流很重要？

## 过滤器相关

190: 在编写 RESTful 客户端，过滤器的作用是什么？

191: 哪些注解允许 `Client` 和 `WebResource` 类添加 `ClientFilter` 实例？

192: `WebResource` 从哪里继承过滤器？

193: 哪些注解允许 `Client` 和 `WebResource` 类添加 `ClientFilter` 实例？

194: 你想使用 `LoggingFilter` 跟踪客户端与服务器之间的通信。假设你正在使用 Jersey client API。你将如何配置 `LoggingFilter`？

195: 何时可以 `WebResource` 添加额外的过滤器？

196: 请求的过滤器应用顺序是什么？

197: 响应的过滤器应用顺序是什么？

198: 在构建请求后，过滤器的应用顺序是什么？

199: 在接收响应后，过滤器的应用顺序是什么？

200: Jersey Client APIs 支持哪两个 `GZIPContentEncodingFilter` 过滤器？

201: Jersey Client APIs 的 `LoggingFilter` 作用是什么？

202: 假设 Jersey Client APIs 的 `LoggingFilter` 没有声明输出流。`LoggingFilter` 将在何处记录请求和响应头部？

# 人资源面试问题

1: 请描述一次你向同事传达困难或复杂观点的经历。

2: 在什么情况下，你觉得沟通起来困难？

3: 良好沟通的关键要素是什么？

4: 请告诉我一次你通过沟通解决问题的经历。

5: 请告诉我一次你与另一位员工发生冲突的经历。你是如何解决该情况的？

6: 你是很快与人建立关系，还是需要更多时间来了解他们？

7: 请描述一次你必须通过处理办公室政治来解决问题的经历。

8: 请告诉我一次你说服他人承担某项艰巨任务的经历。

9: 请告诉我一次你成功说服群体接受你提议的经历。

10: 请告诉我一次你与他人发生矛盾的经历，事后看来，你希望当时能有不同的处理方式。

11: 请告诉我一次你调解其他员工之间冲突的经历。

12: 你在某个职位上看重最重要的三件事是什么？

13: 你是如何评估你想要加入的公司的？

14: 你能接受 ________ 薪资的工作吗？

15: 你为什么选择你的上一份工作？

16: 你离开上一份工作已经多久了？原因是什么？

17: 你还在寻找其他类型的工作？

18: 你在工作中受过纪律处分？

19: 你的时间安排是怎样的？

20: 我可以联系你现任雇主吗？

21: 你是否有任何可以为我们的业务带来价值的人脉？

22: 你多久可以开始工作？

23: 你的上任雇主会说你离开的原因是什么？

24: 你积极寻找工作多久了？

25: 在什么情况下你不来上班？

26: 你缺勤最常见的原因是什么？

# 你最可能被问到的 RESTful Java Web 服务面试题

27: 你的考勤记录如何？

28: 你从哪里听到这个职位的？

29: 在做招聘决策时，还有什么你想让我知道的吗？

30: 请告诉我一次你没能赶截止日的经历。

31: 你在工作时如何消除干扰？

32: 请告诉我一次你在有每周或每月配额指标的职位上工作的经历。你成功的频率有多高？

33: 请告诉我一次你面对严苛截止日的经历，以及你是如何完成任务的。

34: 当你手头有多个项目时，你如何保持有条理？

35: 在工作日期间，你有多少时间处于“自动驾驶”状态？

36: 你是如何处理截止日的？

37: 请告诉我你个人的解决问题流程。

38: 工作中哪些事情会让你感到压力？

39: 当你对某事感到压力时看起来是什么样的？你是如何解决它的？

40: 你能多任务同时处理吗？

41: 你每周工作多少小时？

42: 你每天检查几次邮箱？

43: 请告诉我一次你为了完成项目而加班的经历。

44: 请告诉我一次你的表现超出工作职责和要求的经历。

45: 你对工作的态度是怎样的？

46: 你会把工作带回家吗？

47: 向我描述一下一个典型的工作日。

48: 请告诉我一次你在上一份工作中额外付出的精力。

49: 你是否乐意接受对工作表现的反馈和批评，并根据需要进行调整？

50: 什么在给你灵感？

51: 你如何激励他人？

# 以下部分标题可能也有用

- 1. 你可能被问到的 .NET 面试题
- 2. 你可能被问到的 200 道面试题
- 3. 你可能被问到的 Access VBA 编程面试题
- 4. 你可能被问到的 Adobe Fusion 面试题
- 5. 你可能被问到的高级 Excel 面试题
- 6. 你可能被问到的高级 JAVA 面试题
- 7. 你可能被问到的高级 SAS 面试题
- 8. 你可能被问到的 AJAX 面试题
- 9. 你可能被问到的算法面试题
- 10. 你可能被问到的 Android 开发面试题
- 11. 你可能被问到的 Ant & Maven 面试题
- 12. 你可能被问到的 Apache Web 服务器面试题
- 13. 你可能被问到的人工智能面试题
- 14. 你可能被问到的 ASP.NET 面试题
- 15. 你可能被问到的自动化软件测试面试题
- 16. 你可能被问到的基础 SAS 面试题
- 17. 你可能被问到的 BEAR 面试题
- 18. 你可能被问到的 C & C++ 面试题
- 19. 你可能被问到的 C# 面试题
- 20. 你可能被问到的 C++ 面试题
- 21. 你可能被问到的 CCNA 面试题
- 22. 你可能被问到的云计算面试题
- 23. 你可能被问到的计算机架构面试题
- 24. 你可能被问到的计算机网络面试题
- 25. 你可能被问到的 Java Java面试题
- 26. 你可能被问到的数据结构与算法面试题
- 27. 你可能被问到的数据仓库面试题
- 28. 你可能被问到的实体面试题
- 29. 你可能被问到的 Entity Framework面试题
- 30. 你可能被问到的 Linux面试题
- 31. 你可能被问到的算法面试题
- 32. 你可能被问到的 Struts 面试题
- 33. 你可能被问到的 HTML 面试题
- 34. 你可能被问到的 HTML5面试题
- 35. 你可能被问到的 IBM WebSphere面试题
- 36. 你可能被问到的 iOS面试题
- 37. 你可能被问到的 Java 设计模式面试题
- 38. 你可能被问到的 Java EE面试题
- 39. 你可能被问到的 Java Messaging面试题
- 40. 你可能被问到的 JavaScript 面试题
- 41. 你可能被问到的 JavaFaces面试题
- 42. 你可能被问到的 JDBC 面试题
- 43. 你可能被问到的 jQuery 面试题
- 44. 你可能被问到的 Servlet 面试题
- 45. 你可能被问到的 JUnit 面试题
- 46. 你可能被问到的 Linux 命令面试题
- 47. 你可能被问到的 Linux 面试题
- 48. 你可能被问到的 Linux 系统面试题
- 49. 你可能被问到的 Mac OS 面试题
- 50. 你可能被问到的 Mac OS Snow Lion面试题
- 51. 你可能被问到的 Microsoft Access 面试题
- 52. 你可能被问到的 Microsoft Excel 面试题
- 53. 你可能被问到的 Microsoft Powerpoint面试题
- 54. 你可能被问到的 Microsoft Word 面试题
- 55. 你可能被问到的 MySQL 面试题
- 56. 你可能被问到的 NetSuite 面试题
- 57. 你可能被问到的 网络面试题
- 58. 你可能被问到的 OOOPS 面试题
- 59. 你可能被问到的 操作系统面试题
- 60. 你可能被问到的 Oracle DBA 面试题
- 61. 你可能被问到的 Oracle E-Business Suite面试题
- 62. 你可能被问到的 ORACLE/SQL 面试题
- 63. 你可能被问到的 Perl 编程面试题
- 64. 你可能被问到的 PHP 面试题
- 65. 你可能被问到的 PMP 面试题
- 66. 你可能被问到的 Python 面试题
- 67. 你可能被问到的 RESTful Java Web Services面试题
- 68. 你可能被问到的 Ruby 面试题
- 69. 你可能被问到的 Ruby on Rails 面试题
- 70. 你可能被问到的 SAP ABAP 面试题
- 71. 你可能被问到的 SAP HANA 面试题
- 72. 你可能被问到的 SAS 编程面试题
- 73. 你可能被问到的 Selenium 测试面试题
- 74. 你可能被问到的 Overight 面试题
- 75. 你可能被问到的 软件仓库面试题
- 76. 你可能被问到的 软件测试面试题
- 77. 你可能被问到的 SQL Server 面试题
- 78. 你可能被问到的 Tomcat 面试题
- 79. 你可能被问到的 UML 面试题
- 80. 你可能被问到的 Unik 面试题
- 81. 你可能被问到的 UNIX Shell 面试题
- 82. 你可能被问到的 VB.NET 面试题
- 83. 你可能被问到的 Windows Server 2008 R2 面试题
- 84. 你可能被问到的 XLXP, XSLT, XPath, XFORMS & XQuery 面试题
- 85. 你可能被问到的 XML 面试题

# 访问完整列表请访问

www.vibrantpublishers.com

# 笔记
