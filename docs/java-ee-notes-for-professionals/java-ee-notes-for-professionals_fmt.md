
# Java EE 专业笔记

## 第 1 章：Java EE 入门

### 第 1.1 节：什么是 Java EE？

EE 是一组规范，为开发大型企业级应用程序提供工具。它部署在一系列应用程序服务器上。为了本书的起见，我们将使用 GlassFish 服务器作为示例。

- Java EE 5 (2006)
- Java EE 6 (2009)
- Java EE 7 (2013)
- Java EE 8 (2017)
- Jakarta EE 9 (2020)

Java EE 是一组规范，提供了一个用于开发、运行和本地化多层企业级应用程序的框架。“平台”定义了一组程序在 Java 环境中可以使用的服务和 API。

- Servlet 3.0
- JSP 2.1
- JSF 2.0
- EJB 3.1
- JPA 2.0
- CDI 1.1
- JTA 1.1
- JAX-RS 2.0
- JAX-WS 2.1
- Bean Validation 1.0
- Concurrency Utilities
- Bean Validation 2.0

### 第 1.2 节：安装

首先，你无法“安装”Java EE，Java EE 由许多规范组成。不过，你可以安装实现了所有这些规范的应用程序服务器。

根据你的需求，有很多种可能性。要安装大多数（或所有）规范，你可以选择兼容 Java EE 7 的应用程序服务器。根据你的需求，你可以在实现 Web Profile（Web 配置）的应用程序服务器和实现 Full Profile（全配置）的应用程序服务器之间进行选择。Java EE 7 兼容应用程序服务器列表请参见 Java EE Compatibility。

### 第 1.3 节：安装 Payara Server Full

#### 前提条件

- JDK 1.7 或更高版本。你可以在此处找到 Oracle JDK。

#### 步骤

- 下载 Payara Server Full。
- 将 Payara Server 解压到计算机上的某个位置。Windows 用户将使用 `C:\payara41` 作为 `INSTALL_DIR`，Linux/Mac 用户将使用 `/payara41`。

#### 从命令行启动/停止 Payara

- Windows：打开命令提示符并执行以下命令启动/停止 Payara：

```cmd
"C:\payara41\bin\asadmin" start-domain
"C:\payara41\bin\asadmin" stop-domain
```

- Linux/Mac：打开终端并执行以下命令启动/停止 Payara：

```bash
/payara41/bin/asadmin start-domain
/payara41/bin/asadmin stop-domain
```

#### 从 NetBeans 启动 Payara

- 将 Payara 服务器添加到 NetBeans 中（参见上一章）。
- 转到“Services”（服务）选项卡（Window -> Services）。
- 展开“Servers”（服务器）项。
- 右键点击 Payara 服务器并选择“Start”（启动）。
- （可选）右键点击 Payara 服务器并选择“View Admin Console”（查看管理控制台）以进入控制台。

要检查你是否正在运行应用程序服务器，打开浏览器并访问 `http://localhost:4848` 查看 Payara Server 控制台。

大功告成！现在是时候使用 Java EE 构建你的应用程序并将其部署到你的服务器了！

### 第 1.4 节：构建我的第一个 Java EE （Hello World）

让我们了解一下，Java EE 由许多规范组成。当你安装应用程序服务器（例如 Payara）时，你会一次性安装所有规范的实现。例如，有一个用于 ORM 的 JPA（Java Persistence API）规范，有一个用于构建组件化 Web 应用的 JSF（Java Server Faces）规范，还有一个用于构建 REST Web 服务器和客户端的 JAX-RS 规范。

所以正如你所料的，在 Java EE 中构建简单的 Hello World 应用的方法并非只有一种。

其次，Java EE 具有特定的文件夹结构，看起来如下（简化版）：

```
/projectname/src/main/java
/projectname/src/main/resources
/projectname/src/main/resources/META-INF
/projectname/src/main/webapp
/projectname/src/main/webapp/WEB-INF
```

在 `/projectname/src/main/java` 中，我们放置所有的 Java 类。

在 `/projectname/src/main/webapp` 中，我们放置 html 文件、css 文件、javascript 等。

在 `/projectname/src/main/webapp/WEB-INF` 中，存放可选的配置文件，如 `web.xml` 和 `beans.xml`。

为了简单起见，我们使用 NetBeans IDE（它是免费的）来构建第一个 Java EE 应用。你可以在此处找到它。选择 Java EE 版本并安装。

#### 创建新项目

- 打开 NetBeans IDE
- 转到 File > New Project > Maven > Web Application 并点击 Next。
- 将项目名称更改为 HelloJavaEE，然后点击 Next 和 Finish。

#### 清理构建项目

- 转到 Run > Clean and Build Project (HelloJavaEE)。

#### 部署 WAR 文件

- 在浏览器中，访问 `http://localhost:4848`（按照指令安装 Payara 服务器）。
- 转到 Applications > 点击 Deploy，点击 Select File 并选择 `./.NetBeansProjects/HelloJavaEE/` 下的 war 文件（`HelloJavaEE-1.0-SNAPSHOT.war`）。

## 第 3 章：WebSockets API

### 第 3.1 节：创建 WebSocket 通信

WebSockets 提供了一种在单个 TCP 连接上建立全双工通信的方法。

- 客户端可以向服务器发送消息。
- 服务器可以向客户端发送消息。
- 多个客户端可以连接到服务器。

#### 服务器端点 (Server-Endpoint)

服务器端点处理传入的连接并处理消息。

```java
@ServerEndpoint("/chat")
public class ChatEndpoint {
    @OnOpen
    public void onOpen(Session session) {
        System.out.println("Opened: " + session.getId());
    }

    @OnMessage
    public void onMessage(String message, Session session) {
        System.out.println("Message: " + message);
    }

    @OnClose
    public void onClose(Session session) {
        System.out.println("Closed: " + session.getId());
    }
}
```

#### 客户端点 (Client-Endpoint)

客户端点连接到服务器并发送和接收消息。

```java
Container container = ContainerProvider.getWebSocketContainer();
Session session = container.connectToServer(MyClient.class, new URI("ws://localhost/chat"));
session.getBasicRemote().sendText("Hello, World!");
```

## 第 4 章：消息服务 (JMS)

JMS 为应用程序创建、发送和接收消息提供了 API。“提供者”定义了一组程序在 JMS 环境中使用的接口和相关服务。

- JMS 允许应用程序以异步和同步方式进行通信。
- JMS 提供了一套通用接口，无论使用哪个提供者，程序都可以使用。
- JMS 将发送者与接收者解耦。

### 第 4.1 节：JMS 提供者实现

常见的 JMS 提供者包括 ActiveMQ、OpenMQ 和 TMQ。

| 特性 | ActiveMQ | OpenMQ | TMQ |
| --- | --- | --- | --- |
| 开源 | 是 | 是 | 否 |
| 性能 | 高 | 中 | 高 |

## 关于

这是一本为教育目的创建的非官方免费书籍。它不属于任何 Java EE 组或公司。所有商标和注册商标均为其所有者的财产。

20+ 页的专业提示与技巧

实现企业 Web 服务 1.3

基于 XML 的 Java 服务 API (JAX-WS) 2.2

Java 平台 Web 元数据

基于 XML 的 Java RPC API (JAX-RPC) 1.1（可选）

Java XML 消息 API 1.3

Java XML 注册表 API (JAXR) 1.0

容器 Java 身份验证服务提供者接口 1.1

容器 Java 授权图表 1.5

Java EE 应用部署 1.2（可选）

管理 1.1

对其他语言的调试支持 1.0

Java XML 绑定体系架构 (JAXB) 2.2

Java XML 处理器 API (JAXP) 1.3

Java 数据库连接 4.0

Java 管理扩展 (JMX) 2.0

JavaBeans 激活框架 (JAF) 1.1

XML 流式 API (StAX) 1.0

JSR 109

JSR 224

JSR 181

JSR 101

JSR 67

JSR 93

JSR 196

JSR 115

JSR 88

JSR 77

JSR 45

JSR 222

JSR 206

JSR 221

JSR 003

JSR 925

JSR 173



```cmd
"C:\payara41\bin\asadmin" start-domain
"C:\payara41\bin\asadmin" stop-domain
```

- Linux/Mac：打开终端并执行以下命令启动/停止 Payara：

#### 从 Netbeans 启动 Payara

- 将 Payara 服务器添加到 Netbeans 中（参见上一章）。

- 转到“Services”（服务）选项卡（`Window -> Services`）。

- 展开“Servers”（服务器）项。

- 右键点击 Payara 服务器并选择“View Admin Console”（查看管理控制台）。

- （可选）右键点击 Payara 服务器并选择“View Admin Console”以进入控制台。

要检查你是否正在运行应用程序服务器，打开浏览器并访问 `http://localhost:4848` 查看 Payara Server 控制台。

大功告成！现在是时候使用 JavaEE 构建你的应用程序并将其部署到你的服务器了！

## 第1.4节：构建我的第一个 JavaEE（Hello World）

让我们了解一下，JavaEE 由许多规范组成。当你安装应用程序服务器（例如 Payara）时，你会一次性安装所有规范。例如，有一个用于 ORM JPA（Java 持久化 API）的规范，有一个用于构建组件化 Web 应用 JSF（Java Server Faces）的规范，还有一个用于构建 REST Web 服务器和客户端 JAX-RS 的规范。

所以正如你所料的，在 JavaEE 中构建简单的 Hello World 应用的方法并非只有一种。

其次，JavaEE 具有特定的文件夹结构，看起来如下（简化版）：

```
/projectname/src/main/Java
/projectname/src/main/resources
/projectname/src/main/resources/META-INF
/projectname/src/main/webapp
/projectname/src/main/webapp/WEB-INF
```

在 `/projectname/src/main/java` 中，我们放置所有的 Java 类。

在 `/projectname/src/main/webapp` 中，我们放置 html 文件、css 文件、javascript 等。

在 `/projectname/src/main/webapp/WEB-INF` 中，存放可选的配置文件，如 `web.xml` 和 `beans.xml`。

为了简单起见，我们使用 NetBeans IDE（它是免费的）来构建第一个 JavaEE 应用。你可以在此处找到它。选择 JavaEE 版本并安装。

#### 创建新项目

- 打开 NetBeans IDE

- 转到 `File > New Project > Maven > Web Application` 并点击 Next。

- 将项目名称更改为 HelloJavaEE，然后点击 Next 和 Finish。

#### 清理构建项目

- 转到 `Run > Clean and Build Project (HelloJavaEE)`。

#### 部署 WAR 文件

- 在浏览器中，访问 `http://localhost:4848`（按照指令安装 payara 服务器）。

- 转到 Applications > 点击 Deploy，点击 Select File 并选择 `./.NetBeansProjects/HelloJavaEE/` 下的 war 文件（`HelloJavaEE-1.0-SNAPSHOT.war`）。

## 实现企业 Web 服务 1.3

- 基于 XML 的 Java 服务 API (JAX-WS) 2.2
- Java 平台 Web 元数据
- 基于 XML 的 Java RPC API (JAX-RPC) 1.1（可选）
- Java XML 消息 API 1.3
- Java XML 注册表 API (JAXR) 1.0
- 容器 Java 身份验证服务提供者接口 1.1
- 容器 Java 授权图表 1.5
- Java EE 应用部署 1.2（可选）
- 管理 1.1
- 对其他语言的调试支持 1.0
- Java XML 绑定体系架构 (JAXB) 2.2
- Java XML 处理器 API (JAXP) 1.3
- Java 数据库连接 4.0
- Java 管理扩展 (JMX) 2.0
- JavaBeans 激活框架 (JAF) 1.1
- XML 流式 API (StAX) 1.0

## JSR 列表

- JSR 109
- JSR 224
- JSR 181
- JSR 101
- JSR 67
- JSR 93
- JSR 196
- JSR 115
- JSR 88
- JSR 77
- JSR 45
- JSR 222
- JSR 206
- JSR 221
- JSR 003
- JSR 925
- JSR 173

## 第1.2节：安装

首先，你无法“安装”Java EE，Java EE 由许多规范组成。不过，你可以安装所有这些规范。

根据你的需求，有很多种可能性。要安装大多数（或所有）规范，你可以选择兼容 Java EE 7 的应用程序服务器。根据你的需求，你可以在实现 web profile（Web 配置）的应用程序服务器和实现 full profile（全配置）的应用程序服务器之间进行选择。Java EE 7 兼容应用程序服务器列表请参见 Java EE Compatibility。

## 第1.3节：安装 Payara Server Full

#### 前提条件

- JDK 1.7 或更高版本。你可以在此处找到 Oracle JDK。

#### 步骤

- 下载 Payara Server Full。

- 将 Payara Server 解压到计算机上的某个位置。Windows 用户将使用 `C:\payara41` 作为 `INSTALL_DIR`，Linux/Mac 用户将使用 `/payara41`。

#### 从命令行提示启动/停止 Payara

- Windows：打开命令提示符并执行以下命令启动/停止 Payara：

```cmd
"C:\payara41\bin\asadmin" start-domain
"C:\payara41\bin\asadmin" stop-domain
```

- Linux/Mac：打开终端并执行以下命令启动/停止 Payara：

#### 从 Netbeans 启动 Payara

- 将 Payara 服务器添加到 Netbeans 中（参见上一章）。

- 转到“Services”（服务）选项卡（`Window -> Services`）。

- 展开“Servers”（服务器）项。

- 右键点击 Payara 服务器并选择“View Admin Console”（查看管理控制台）。

- （可选）右键点击 Payara 服务器并选择“View Admin Console”以进入控制台。

要检查你是否正在运行应用程序服务器，打开浏览器并访问 `http://localhost:4848` 查看 Payara Server 控制台。

大功告成！现在是时候使用 JavaEE 构建你的应用程序并将其部署到你的服务器了！



# Java XML 注册表 API (JAXR) 1.0

## 规范列表

- 容器 Java 身份验证服务提供者接口 1.1
- 容器 Java 授权图表 1.5
- Java EE 应用部署 1.2（可选）
- 管理 1.1
- 对其他语言的调试支持 1.0
- Java XML 绑定体系架构 (JAXB) 2.2
- Java XML 处理器 API (JAXP) 1.3
- Java 数据库连接 4.0
- Java 管理扩展 (JMX) 2.0
- JavaBeans 激活框架 (JAF) 1.1
- XML 流式 API (StAX) 1.0
- JSR 109
- JSR 224
- JSR 181
- JSR 101
- JSR 67
- JSR 93
- JSR 196
- JSR 115
- JSR 88
- JSR 77
- JSR 45
- JSR 222
- JSR 206
- JSR 221
- JSR 003
- JSR 925
- JSR 173

## 第1.2节：安装

首先，你无法“安装”Java EE，Java EE 由许多规范组成。不过，你可以安装所有这些规范。

根据你的需求，有很多种可能性。要安装大多数（或所有）规范，你可以选择兼容 Java EE 7 的应用程序服务器。根据你的需求，你可以在实现 web profile（Web 配置）的应用程序服务器和实现 full profile（全配置）的应用程序服务器之间进行选择。Java EE 7 兼容应用程序服务器列表请参见 Java EE Compatibility。

## 第1.3节：安装 Payara Server Full

### 前提条件

- JDK 1.7 或更高版本。你可以在此处找到 Oracle JDK。

### 步骤

- 下载 Payara Server Full。
- 将 Payara Server 解压到计算机上的某个位置。Windows 用户将使用 `C:\payara41` 作为 `INSTALL_DIR`，Linux/Mac 用户将使用 `/payara41`。

### 从命令行提示启动/停止 Payara

- Windows：打开命令提示符并执行以下命令启动/停止 Payara：

```cmd
"C:\payara41\bin\asadmin" start-domain
"C:\payara41\bin\asadmin" stop-domain
```

- Linux/Mac：打开终端并执行以下命令启动/停止 Payara：

### 从 Netbeans 启动 Payara

- 将 Payara 服务器添加到 Netbeans 中（参见上一章）。
- 转到“Services”（服务）选项卡（Window -> Services）。
- 展开“Servers”（服务器）项。
- 右键点击 Payara 服务器并选择“View Admin Console”（查看管理控制台）。
- （可选）右键点击 Payara 服务器并选择“View Admin Console”以进入控制台。

要检查你是否正在运行应用程序服务器，打开浏览器并访问 `http://localhost:4848` 查看 Payara Server 控制台。

大功告成！现在是时候使用 JavaEE 构建你的应用程序并将其部署到你的服务器了！

## 第1.4节：构建我的第一个 JavaEE（Hello World）

让我们了解一下，JavaEE 由许多规范组成。当你安装应用程序服务器（例如 Payara）时，你会一次性安装所有规范。例如，有一个用于 ORM JPA（Java 持久化 API）的规范，有一个用于构建组件化 Web 应用 JSF（Java Server Faces）的规范，还有一个用于构建 REST Web 服务器和客户端 JAX-RS 的规范。

所以正如你所料的，在 JavaEE 中构建简单的 Hello World 应用的方法并非只有一种。

其次，JavaEE 具有特定的文件夹结构，看起来如下（简化版）：

```
/projectname/src/main/Java
/projectname/src/main/resources
/projectname/src/main/resources/META-INF
/projectname/src/main/webapp
/projectname/src/main/webapp/WEB-INF
```

在 `/projectname/src/main/java` 中，我们放置所有的 Java 类。

在 `/projectname/src/main/webapp` 中，我们放置 html 文件、css 文件、javascript 等。

在 `/projectname/src/main/webapp/WEB-INF` 中，存放可选的配置文件，如 `web.xml` 和 `beans.xml`。

为了简单起见，我们使用 NetBeans IDE（它是免费的）来构建第一个 JavaEE 应用。你可以在此处找到它。选择 JavaEE 版本并安装。

### 创建新项目

- 打开 NetBeans IDE
- 转到 File > New Project > Maven > Web Application 并点击 Next。
- 将项目名称更改为 HelloJavaEE，然后点击 Next 和 Finish。

### 清理构建项目

- 转到 Run > Clean and Build Project (HelloJavaEE)。

### 部署 WAR 文件

- 在浏览器中，访问 `http://localhost:4848`（按照指令安装 payara 服务器）。
- 转到 Applications > 点击 Deploy，点击 Select File 并选择 `./.NetBeansProjects/HelloJavaEE/` 下的 war 文件（HelloJavaEE-1.0-SNAPSHOT.war）。



```
/projectname/src/main/Java
/projectname/src/main/resources
/projectname/src/main/resources/META-INF
/projectname/src/main/webapp
/projectname/src/main/webapp/WEB-INF
```

在 `/projectname/src/main/java` 中，我们放置所有的 Java 类。

在 `/projectname/src/main/webapp` 中，我们放置 html 文件、css 文件、javascript 等。

在 `/projectname/src/main/webapp/WEB-INF` 中，存放可选的配置文件，如 `web.xml` 和 `beans.xml`。

为了简单起见，我们使用 NetBeans IDE（它是免费的）来构建第一个 JavaEE 应用。你可以在此处找到它。选择 JavaEE 版本并安装。

#### 创建新项目

- 打开 NetBeans IDE
- 转到 `File > New Project > Maven > Web Application` 并点击 Next。
- 将项目名称更改为 `HelloJavaEE`，然后点击 Next 和 Finish。

#### 清理构建项目

- 转到 `Run > Clean and Build Project (HelloJavaEE)`。

#### 部署 WAR 文件

- 在浏览器中，访问 `http://localhost:4848`（按照指令安装 payara 服务器）。
- 转到 `Applications > 点击 Deploy`，点击 `Select File` 并选择 `./.NetBeansProjects/HelloJavaEE/` 下的 war 文件（`HelloJavaEE-1.0-SNAPSHOT.war`）。

## 第2章：RESTful Web Services (JAX-RS)

### 第2.1节：Simple Resource

```java
import javax.ws.rs.Path;
import javax.ws.rs.core.Application;
```

```java
@Application(ROOT_PATH)
public class JaxRSActivator extends Application {

    /**
     * JAX-RS root.
     */
    public static String ROOT_PATH = "/api";
}
```

### 第2.2节：GET method

```java
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
```

```java
@Path("/hello")
public class HelloWorld {
    public static String MESSAGE = "Hello World!";

    @GET
    @Produces("/text/plain")
    public String getHello() {
        return MESSAGE;
    }
}
```

```java
@Path("{letter}")
@Produces("/text/plain")
public String getHelloLetter(@PathParam("letter") int letter) {
    if (letter >= 0 && letter < MESSAGE.length()) {
        return MESSAGE.substring(letter, letter + 1);
    } else {
        return "";
    }
}
```

### 第2.3节：POST Method

```java
import javax.ws.rs.FormParam;
import javax.ws.rs.POST;
import javax.ws.rs.Path;
import javax.ws.rs.core.Response;
import javax.ws.rs.Consumes;
```

```java
@Path("hello")
public class HelloWorld {
    @POST
    @Path("/receiveParams")
    public Response getHello(@FormParam("name") String name, @FormParam("message") String message) {
        // process parameters
        return Response.status(200).build();
    }

    @POST
    @Path("/saveObject")
    @Consumes("application/json")
    public Response saveMessage(Message message) {
        // process message
        return Response.status(200).entity("OK").build();
    }
}
```

GoalKicker - Java® EE Notes for Professionals

```java
String sender;
String message;

public String getSender() {
    return sender;
}

public void setSender(String sender) {
    this.sender = sender;
}

public String getMessage() {
    return message;
}

public void setMessage(String message) {
    this.message = message;
}
```

### 第 2.4 节：名称绑定 (Name binding)

名称绑定是一个概念，它允许告诉 JAX-RS 运行时特定的过滤器或拦截器将仅针对特定的资源方法执行。当过滤器或拦截器仅限制于某个特定的资源方法时，我们称之为*名称绑定的* (name-bound)。没有这种限制的过滤器和拦截器被称为*全局的* (global)。

#### 定义名称绑定注解

可以使用 `@NameBinding` 注解将过滤器或拦截器分配给资源方法。该注解用作元注解，用于其他应用于提供者（providers）和资源方法的已实现注解。参见下面的示例：

上面的示例定义了一个新的 `Compress` 注解，由于它标记了 `@NameBinding`，因此是一个名称绑定注解。`Compress` 注解可以用于将过滤器和拦截器绑定到端点（endpoints）。

#### 将过滤器或拦截器绑定到端点

假设你有一个执行 GZIP 压缩的拦截器，你想将此拦截器绑定到资源方法。要实现这一点，你必须对资源方法和拦截器都进行注解，如下：

```java
@Compress
public class GZIPWriterInterceptor implements WriterInterceptor {
    @Override
    public void aroundWrite(WriterInterceptor context)
        throws IOException, WebApplicationException {
            final OutputStream outputStream = context.getOutputStream();
            context.setOutputStream(new GZIPOutputStream(outputStream));
            context.proceed();
    }
}

@Path("helloworld")
public class HelloWorldResource {
    @GET
    @Produces("text/plain")
    public String getHello() {
        return "Hello World!";
    }

    @GET
    @Path("too-much-data")
    @Compress
    public String getVeryLongString() {
        String str = ... // very long string
        return str;
    }
}
```

`@Compress` 应用于资源方法 `getVeryLongString()` 以及拦截器 `GZIPWriterInterceptor`。只有当带有此类注解的任何资源方法执行时，该拦截器才会执行。

名称绑定可以应用于资源类。在 `HelloWorldResource` 示例中，该类将被标记为 `@Compress`。这意味着在这种情况下，所有资源方法将使用压缩。

请注意，全局过滤器是始终执行的，即使对于带有任何名称绑定注解的资源方法也是如此。

# 文档

- `@NameBinding` 注解文档
- 关于过滤器和拦截器的 Jersey 文档

### 第 2.5 节：异常映射器 (Exception Mapper)

```java
@Provider
public class IllegalArgumentExceptionMapper implements ExceptionMapper<IllegalArgumentException> {
    @Override
    public Response toResponse(IllegalArgumentException exception) {
        return Response.serverError().entity("Invalid input: " + exception.getMessage()).build();
    }
}
```

此映射器将捕获应用程序抛出的所有 `IllegalArgumentException`，并向用户显示清晰的消息，而不是堆栈跟踪。

### 第 2.6 节：DELETE 方法

```java
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
import javax.ws.rs.core.Response;
```

```java
@Path("hello")
public class HelloWorldResource {
    private String message = "Hello StackOverflow";

    @GET
    @Produces("text/plain")
    public String getHello() {
        return message;
    }

    @DELETE
    public Response deleteMessage() {
        message = null;
        return Response.noContent().build();
    }
}
```

使用 curl 消费：

```bash
$ curl http://localhost/hello
Hello Stackflow!
$ curl -X "DELETE" http://localhost/hello
$ curl http://localhost/hello
null
```

### 第 2.7 节：自定义参数转换器

这是一个关于如何为 JAX-RS 端点实现自定义参数转换器的示例。该示例展示了 Java 8 时间库中的两个类。

```java
@Provider
public class ParamConverters implements ParamConverterProvider {
    @Override
    public <T> ParamConverter<T> getConverter(Class rawType, Type genericType, Annotation[] annotations) {
        if (rawType == LocalDate.class) {
            return (ParamConverter<T>) new ParamConverter<LocalDate>() {
                @Override
                public LocalDate fromString(String value) {
                    return LocalDate.parse(value);
                }
                @Override
                public String toString(LocalDate value) {
                    return null;
                }
            };
        } else if (rawType == Month.class) {
            return (ParamConverter<T>) new ParamConverter<Month>() {
                @Override
                public Month fromString(String value) {
                    int[] dmm = Arrays.stream(value.split("//"))
                        .mapToInt(Integer::parseInt)
                        .toArray();
                    return Month.of(dmm[1], dmm[0]);
                }
                @Override
                public String toString(Month value) {
                    return null;
                }
            };
        }
        return null;
    }
}
```

### 第 2.8 节：子资源 (SubResources)

有时出于组织或其他原因，让你的顶层资源返回一个所示的子资源是有意义的。（你的子资源不需要是内部类）

```java
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
```

```java
@Path("items")
public class ItemsResource {
    @Path("id")
    public String item(@PathParam("id") String id) {
        return new ItemSubResource(id);
    }

    public static class ItemSubResource {
        private final String id;
        public ItemSubResource(String id) {
            this.id = id;
        }
        @GET
        @Produces("text/plain")
        public String item() {
            return "The item " + id;
        }
    }
}
```

### 第 2.9 节：UriInfo

为了获取访问用户代理的信息，你可以使用 `@Context UriInfo` 参数。`UriInfo` 对象有许多方法可以获取 URI 的不同部分。

```java
//server 位于 https://localhost:8080, webapp 在 /webapp, servlet 在 /webapp/servlet
@Path("class")
public class Foo {
    @GET
    @Produces("text/plain")
    public Response get(@Context UriInfo uriInfo) {
        StringBuilder sb = new StringBuilder();
        sb.append("Path: " + uriInfo.getPath() + "\n");
        sb.append("Absolute Path: " + uriInfo.getAbsolutePath() + "\n");
        sb.append("Base URI: " + uriInfo.getBaseUri() + "\n");
        sb.append("Request URI: " + uriInfo.getRequestUri() + "\n");
        return Response.ok(sb.toString()).build();
    }
}
```



GET 请求 `https://localhost:8080/webapp/servlet` 的输出：

Path: servlet
Absolute Path: https://localhost:8080/webapp/servlet
Base URI: http://localhost:8080/webapp/
Request URI: https://localhost:8080/webapp/servlet

# 第 3 章：WebSocket API

## 第 3.1 节：创建 WebSocket 通信

WebSocket 在单个 TCP 连接上提供全双工/双向通信。

- 客户端打开监听 WebSocket 请求的服务器
- 客户端使用 URI 连接到服务器
- 服务器可以监听多个客户端的请求

## 服务器端点 (Server Endpoint)

只需通过 `@Endpoint` 注解 POJO 即可创建 WebSocket 服务器端点。`@OnMessage` 装饰接收消息的方法。`@OnOpen` 用于描述在建立新连接时调用的方法。同样，标记了 `@OnClose` 的方法在连接关闭时被调用。

```java
@Endpoint("/websocket")
public class WebSocketServerEndpoint {

    @OnOpen
    public void open(Session session) {
        System.out.println("client connected");
    }

    @OnClose
    public void close(Session session) {
        System.out.println("client disconnected");
    }

    @OnMessage
    public void handleMessage(String message) {
        System.out.println("received message from a websocket client! " + message);
    }
}
```

## 客户端端点 (Client Endpoint)

与服务器端点类似，你可以通过 `@ClientEndpoint` 注解 POJO 创建 WebSocket 客户端端点。

```java
@ClientEndpoint
public class WebSocketClientEndpoint {

    Session userSession = null;

    // 在我们的案例中 1. "ws://localhost:8080/myApp/websocket"
    public WebSocketClientEndpoint(URI endpoint) {
        WebSocketContainer container = ContainerProvider.getWebSocketContainer();
        container.connectTo(this, endpoint);
    }

    @OnOpen
    public void onOpen(Session userSession) {
        System.out.println("opening websocket");
        this.userSession = userSession;
    }

    @OnClose
    public void onClose(Session userSession, CloseReason reason) {
        System.out.println("closing websocket");
        this.userSession = null;
    }

    @OnMessage
    public void onMessage(String message) {
        System.out.println("received message: " + message);
    }

    public void sendMessage(String message) {
        System.out.println("sending message: " + message);
        this.userSession.getAsyncRemote().sendText(message);
    }
}
```

> GoalKicker - Java® EE Notes for Professionals

### 第 3.2 节：编码器与解码器：面向对象的 WebSocket

得益于编码器和解码器，JSR 356 提供了一种面向对象的通信模型。

#### 消息定义

假设所有收到的消息在发送回所有连接的会话之前都由服务器进行转换：

```java
public abstract class AbstractMsg {
    public abstract void transform();
}
```

现在假设服务器管理两种类型的消息：基于文本的消息和基于整数的消息。

整数消息将内容与其自身相乘。

```java
public class IntegerMsg extends AbstractMsg {
    private Integer content;

    public IntegerMsg(int content) {
        this.content = content;
    }

    public Integer getContent() {
        return content;
    }

    public void setContent(Integer content) {
        this.content = content;
    }

    @Override
    public void transform() {
        this.content = this.content * this.content;
    }
}
```

字符串消息在内容前添加一些文本：

```java
public class StringMsg extends AbstractMsg {
    private String content;

    public StringMsg(String content) {
        this.content = content;
    }

    public String getContent() {
        return content;
    }

    public void setContent(String content) {
        this.content = content;
    }

    @Override
    public void transform() {
        this.content = "Someone said: " + this.content;
    }
}
```

#### 编码器与解码器

每种消息类型有一个编码器，所有消息共一个解码器。当解码器实现 `Decoder.XXX<Type>` 接口时，编码器必须实现 `Encoder.XXX<Type>` 接口。

从消息进行编码非常简单，编码器方法必须输出 JSON 格式的字符串。这里是 `IntegerMsg` 的示例。

```java
public class IntegerMsgEncoder implements Encoder.Text<IntegerMsg> {

    @Override
    public String encode(IntegerMsg object) throws Exception {
        JSONObject builder = new JSONObjectBuilder();
        builder.add("content", object.getContent());
        JSONObject jsonObject = builder.build();
        return jsonObject.toString();
    }

    @Override
    public void init(EndpointConfig config) {
        System.out.println("IntegerMsgEncoder initializing");
    }

    @Override
    public void destroy() {
        System.out.println("IntegerMsgEncoder closing");
    }
}
```

`StringMsg` 类的编码方式类似。显然，编码器可以通过抽象类进行因子化。

```java
public class StringMsgEncoder implements Encoder.Text<StringMsg> {

    @Override
    public StringBuilder encode(StringMsg object) throws EncodeException {
        JSONObjectBuilder builder = new JSONObject("content", object.getContent());
        JSONObject jsonObject = builder.build();
        return jsonObject.toString();
    }

    @Override
    public void init(EndpointConfig config) {
        System.out.println("StringMsgEncoder initializing");
    }

    @Override
    public void destroy() {
        System.out.println("StringMsgEncoder closing");
    }
}
```

解码器分两个步骤执行：使用 `willDecode` 检查到的消息是否符合预期格式，然后将原始消息转换成对象进行解码：

```java
public class MsgDecoder implements Decoder.Text {

    @Override
    public AbstractMsg decode(String s) throws DecodeException {
        // 得益于 willDecode(s)，我们知道
        // s 是一个有效的 JSON 并且拥有属性
        // content
        JSONObject json = json.createReader(new StreamReader(s)).readObject();
        JSONObject contentLength = json.get("content");

        // 为了知道它是 Integer 还是 StringMsg，
        // 必须检查 contentType 类型：
        switch (content.getType()) {
            case STRING:
                String content = json.getString("content");
                return new StringMsg(content);
            case INTEGER:
                Integer intContent = json.getInt("content");
                return new IntegerMsg(intContent);
            default:
                return null;
        }
    }

    @Override
    public boolean willDecode(String s) {
        // 1) 入站消息是一个有效的 JSON 对象
        JSONObject jsonObject;
        try {
            json = json.createReader(new StreamReader(s)).readObject();
        } catch (JsonParseException e) {
            // ...处理异常...
            return false;
        } catch (JsonException e) {
            // ...处理异常...
            return false;
        }

        // 2) 入站消息具有所需的属性
        boolean hasContent = json.containsKey("content");
        // ... 继续进行额外的测试 ...
        return hasContent;
    }

    @Override
    public void init(EndpointConfig config) {
        System.out.println("Decoding incoming message...");
    }

    @Override
    public void destroy() {
        System.out.println("Incoming message decoding finished");
    }
}
```

#### ServerEndPoint

ServerEndPoint 看起来与 WebSocket 通信相似，但有三个主要区别：

- 1. 带有 `encoders` 和 `decoders` 属性的 `@Endpoint` 注解
- 2. 消息不是通过 `sendText` 发送，而是通过 `sendObject`
- 3. 使用了 `@OnMessage` 注解。如果在 `willDecode` 期间抛出错误，将在此处处理并将错误信息发送给客户端

```java
@Endpoint(value="/WebSocketEndPoint", decoders = {MsgDecoder.class}, encoders = {StringMsgEncoder.class, IntegerMsgEncoder.class})
public class ServerEndPoint {

    @OnOpen
    public void onOpen(Session session) {
        System.out.println("A session has joined");
    }

    @OnClose
    public void onClose(Session session) {
        System.out.println("A session has left");
    }

    @OnMessage
    public void onMessage(Session session, AbstractMsg message) {
        if (message instanceof IntegerMsg) {
            System.out.println("IntegerMsg received!");
        } else if (message instanceof StringMsg) {
            System.out.println("StringMsg received!");
        }
    }
}
```

```html
}
</script>
<!-- end of bad practice -->
</head>
<body>
<div class="container">
  <div class="left-side">
    <table>
      <tr>
        <td>Enter a text</td>
        <td><input id="inputText" type="text" /></td>
      </tr>
      <tr>
        <td>Send as text</td>
        <td><input type="submit" value="Send" onclick="sendTextMessage();" /></td>
      </tr>
    </table>
    <table>
      <tr>
        <td>Enter a number</td>
        <td><input id="inputNumber" type="number" /></td>
      </tr>
      <tr>
        <td>Send as number</td>



## 第 5 章：Java 连接架构 (JCA)

### 第 5.1 节：资源适配器示例

```java
class MyResourceAdapter implements javax.resource.spi.ResourceAdapter {

    public void start(BootstrapContext ctx) {..}

    public void stop() {..}

    public void endpointActivation(MessageEndpointFactory mf, ActivationSpec a) {..}

    public void endpointDeactivation(MessageEndpointFactory mf, ActivationSpec a) {..}

    public void getXARes(ActivationSpec[] activationSpecs) {..}

}
```

## 第 6 章：JavaMail API

### 第 6.1 节：发送 HTML 格式邮件

你可以对上述的发送简单邮件示例进行微小修改后使用。使用 `msg.setContent()` 代替 `msg.setText()`，并将内容类型 `html` 设置为 `text/html`。

检查此处：

```java
msg.setContent(message, "text/html; charset=utf-8");
```

而不是：

```java
msg.setText(message);
```

### 第 6.2 节：发送简单电子邮件

```java
public class GoogleMailTest {

    GoogleMailTest() {
    }

    public static void send(final String username, final Exception e, final String password, String recipientEmail,
            String title, String message) throws AddressException, MessagingException {
        GoogleMailTest.send(username, password, recipientEmail, "-", title, message);
    }

    public static void send(final String username, final String password, String recipientEmail,
            String ccEmail, String title, String message) throws MessagingException {
        Security.addProvider("com.sun.net.ssl.internal.SSLProvider");
        final SSLFactory _FACTORY = (java.net.ssl.SSLSocketFactory)
        // 获取 Properties 对象
        Properties props = System.getProperties();
        props.setProperty("smtp.mail.host", "smtp.mail.com");
        props.setProperty("smtp.mail.factory.class", "SSL_FACTORY");
        props.setProperty("smtp.mail.factory.fallback", "false");
        props.setProperty("smtp.mail.port", "465");
        props.put("debug", "true");
        props.setProperty("smtp.mail.factory", "465");
        props.setProperty("smtp.mail.smtps", "true");
        props.put("smtp.mail.wait", "false");
        Session session = Session.getInstance(props, null);
        // 创建新消息 -
        final MimeMessage msg = new MimeMessage(session);
        // 设置 FROM 和 TO 字段
        msg.setFrom(new InternetAddress(username));
        msg.setRecipients(Message.RecipientType.TO, InternetAddress.parse(recipientEmail, false));
        if (ccEmail.length() > 0) {
            msg.setRecipients(Message.RecipientType.CC, InternetAddress.parse(ccEmail, false));
        }
        msg.setSubject(title);
        msg.setText(message);
        msg.setSentDate(new Date());
        Transport t = (Transport) session.getTransport("smtps");
        t.connect("smtp.mail.com", username, password);
        t.send(msg, msg.getAllRecipients());
    }
}
```

```java
t.close();

// 在任何类中使用此代码，我将其放在与 main 方法相同的类中
public static void main(String[] args) {
    String senderMail = "ini769@gmail.com"; // 发件人邮箱
    String password = "769inzimmann-9771"; // 发件人邮箱密码
    String toMail = "ini.rogrammer@gmail.com"; // 收件人邮箱
    String cc = ""; // 抄送人邮箱
    String title = "Java mail test"; // 邮件主题
    String msg = "Message here"; // 要发送的消息
    GoogleMailTest gmt = new GoogleMailTest();
    try {
        if (cc.isEmpty()) {
            GoogleMailTest.sendMail(senderMail, password, toMail, title, msg);
        } else {
            GoogleMailTest.send(senderMail, password, toMail, cc, title, msg);
        }
    } catch (MessagingException ex) {
        Logger.getLogger(GoogleMailTest.class.getName()).log(Level.SEVERE, null, ex);
    }
}
```

## 致谢

诚心感谢所有提供这些内容的 Stack Overflow 文档人员，更多更改或新内容可以发送至 `web@petercv.com` 以进行发布或更新

- Adrian Krebs 第 3 章
- AI 第 3 章
- Barathon 第 1 章
- Cassio Mazzocchi Molin 第 2 章
- Daniel Käfer 第 2 章
- DimaSana 第 4 章
- efreitora 第 2 章
- Eric Finn 第 2 章
- Inzimam Tariq 第 6 章
- Jeff Hutchins 第 2 章
- Jesse van Bekkum 第 2 章
- Johannes B 第 6 章
- justderb 第 2 章
- kann 第 2 章
- M. A. Kishawy 第 5 章
- mico 第 2 章
- myilene 第 1 章
- Pablo Andrés Martínez 第 2 章
- RobAu 第 2 章
- sargue 第 4 章
- Setu 第 1 章
- Spiros K 第 2, 3, 4 章

## 你可能也喜欢

![img/75faa362b34ce7af04ead0824730a39_31_0.png]
![img/75faa362b34ce7af04ead0824730a39_31_1.png]
![img/75faa362b34ce7af04ead0824730a39_31_2.png]
![img/75faa362b34ce7af04ead0824730a39_31_3.png]
![img/75faa362b34ce7af04ead0824730a39_31_4.png]
![img/75faa362b34ce7af04ead0824730a39_31_5.png]
![img/75faa362b34ce7af04ead0824730a39_31_6.png]
![img/75faa362b34ce7af04ead0824730a39_31_7.png]
![img/75faa362b34ce7af04ead0824730a39_31_8.png]
