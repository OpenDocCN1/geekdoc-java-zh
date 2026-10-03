
# JAX-RS 教程

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/tutorials/jax-rs-tutorials/>

![jax-rs tutorials](img/7474c9efd9598e9dd12102e2178c46e1.png "jaxrs-tutorials")

Java API for RESTful Web Services（**JAX-RS**），是一套为开发者提供 REST 服务的 API。JAX-RS 是 Java EE6 的一部分，使开发者开发 REST web 应用变得容易。

在这一系列的 JAX-RS 教程中，我们同时使用了 [Jersey](http://web.archive.org/web/20220706180444/https://jersey.java.net/) 和 [RESTEasy](http://web.archive.org/web/20220706180444/http://www.jboss.org/resteasy) ，流行的 JAX-RS 实现。

快乐学习 JAX🙂

## 快速启动

一些快速使用 JAX-RS 的例子。

*   [Jersey hello world 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jersey-hello-world-example/)

    Jersey 框架创建一个简单的 REST 风格的 web 应用程序。

*   [RESTEasy hello world 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/resteasy-hello-world-example/)

    RESTEasy 框架创建一个简单的 REST 风格的 web 应用程序。

## 基本示例

开发 REST 服务的基本注释和函数。

*   [JAX-RS @Path URI 匹配示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jax-rs-path-uri-matching-example/)

    JAX-RS URI 匹配示例。

*   [JAX-RS @PathParam 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jax-rs-pathparam-example/)

    将`@Path`中定义的 URI 参数注入 Java 方法的简单方法。

*   [JAX-RS @QueryParam 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jax-rs-queryparam-example/)

    示例获取 URI 路径中的查询参数，以及如何定义可选参数。

*   [JAX-RS @MatrixParam 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jax-rs-matrixparam-example/)

    获取 URI 路径中矩阵参数的示例。

*   [JAX-RS @FormParam 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jax-rs-formparam-example/)

    获取 HTML post 表单参数值的示例。

*   [JAX-RS @HeaderParam 和 @Context 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jax-rs-headerparam-example/)

    展示了如何使用`@HeaderParam`和`@Context`来获取 HTTP 头。

*   [从 JAX-RS 下载文本文件](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-text-file-from-jax-rs/)

    示例输出一个文本文件供用户下载。

*   [从 JAX-RS 下载图像文件](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-image-file-from-jax-rs/)

    示例输出图像文件供用户下载。

*   [从 JAX-RS 下载 pdf 文件](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-pdf-file-from-jax-rs/)

    示例输出 pdf 文件供用户下载。

*   [从 JAX-RS 下载 excel 文件](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-excel-file-from-jax-rs/)

    示例输出 excel 文件供用户下载。

## 文件上传示例

如何处理 JAX-RS 中的多部分数据？

*   [Jersey 中的文件上传示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/file-upload-example-in-jersey/)

    Jersey 中的文件上传很容易。

*   [RESTEasy 中的文件上传示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/file-upload-example-in-resteasy/)

    RESTEasy 中处理文件上传的两种方式。

## 使用 XML

JAX-RS 中的 XML 支持。

*   [Jersey + JAXB 的 XML 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-xml-with-jersey-jaxb/)

    Jersey + JAXB 将对象映射到 XML 和从 XML 映射。

*   [RESTEasy + JAXB 的 XML 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-xml-file-from-jax-rs-with-jaxb-resteasy/)

    RESTEasy + JAXB 将对象映射到 XML 和从 XML 映射。

## 使用 JSON

JAX-RS 的 JSON 支持。

*   [Jersey + Jackson 的 JSON 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/json-example-with-jersey-jackson/)

    Jersey + Jackson 将对象映射到 JSON 和从 JSON 映射。

*   [RESTEasy + Jackson 的 JSON 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/integrate-jackson-with-resteasy/)

    RESTEasy + Jackson 将对象映射到 JSON 和从 JSON 映射。

*   [RESTEasy + JAXB + Jackson 的 JSON 示例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/download-json-from-jax-rs-with-jaxb-resteasy/)

    RESTEasy + JAXB + Jackson 将对象映射到 JSON 和从 JSON 映射。

## RESTful Java 客户端

创建一个 RESTful Java 客户端来执行“GET”和“POST”请求，以操作 json 数据。

*   [使用 java.net.URL 的 RESTful Java 客户端](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/restfull-java-client-with-java-net-url/)

*   [带 Apache HttpClient 的 RESTful Java 客户端](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/restful-java-client-with-apache-httpclient/)

*   [带有 RESTEasy 客户端的 RESTful Java 客户端](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/restful-java-client-with-resteasy-client-framework/)

*   [RESTful Java 客户端和 Jersey 客户端](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/restful-java-client-with-jersey-client/)

## JAX-RS + Spring

将 JAX-RS 与 Spring 框架集成。

*   [Jersey + Spring 集成实例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jersey-spring-integration-example/)

    将 Jersey 与 Spring 框架整合。

*   [RESTEasy + Spring 集成实例](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/resteasy-spring-integration-example/)

    将 RESTEasy 与 Spring 框架集成。

## 常见错误消息

JAX-RS 开发中的一些常见错误信息。

*   [RESTEasy 无法扫描 WEB-INF 中的 JAX-RS 注释，ZLIB 输入流意外结束](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/resteasy-unable-to-scan-web-inf-for-jax-rs-annotations/)

*   [ClassNotFoundException: org.jboss.resteasy.plugins.providers.multipart.MultipartInput](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/classnotfoundexception-org-jboss-resteasy-plugins-providers-multipart-multipartinput/)

*   [RESTEasy – 找不到类型为 multipart/form-data 的消息正文读取器](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/resteasy-could-not-find-message-body-reader-for-type-multipartform-data/)

*   [RESTEasy – 找不到类型为 xx、媒体类型为 application/xml 的响应对象的 MessageBodyWriter](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/resteasy-could-not-find-messagebodywriter-for-response-object-of-typexx-of-media-type-applicationxml/)

*   [将消息体注入到公共 org.codehaus.jackson.jaxrs.JacksonJsonProvider 的单例中是非法的](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/illegal-to-inject-a-message-body-into-a-singleton-into-public-org-codehaus-jackson-jaxrs-jacksonjsonprovider/)

*   [Jersey: resourceConfig 实例不包含任何根资源类](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/jersey-the-resourceconfig-instance-does-not-contain-any-root-resource-classes/)

*   [ClassNotFoundException: com.sun.jersey.spi.container.servlet.ServletContainer](http://web.archive.org/web/20220706180444/http://www.mkyong.com/webservices/jax-rs/classnotfoundexception-com-sun-jersey-spi-container-servlet-servletcontainer/)

## 参考

1.  [Jersey 官网](http://web.archive.org/web/20220706180444/https://jersey.java.net/)

2.  [Jersey 用户指南](http://web.archive.org/web/20220706180444/https://jersey.java.net/nonav/documentation/latest/user-guide.html)

3.  [RESTEasy 官网](http://web.archive.org/web/20220706180444/http://www.jboss.org/resteasy)

4.  [RESTEasy 用户指南](http://web.archive.org/web/20220706180444/http://docs.jboss.org/resteasy/docs/2.2.1.GA/userguide/html/)

5.  [维基百科 REST 解释](http://web.archive.org/web/20220706180444/https://en.wikipedia.org/wiki/Java_API_for_RESTful_Web_Services)

<input type="hidden" id="mkyong-current-postId" value="9716">
