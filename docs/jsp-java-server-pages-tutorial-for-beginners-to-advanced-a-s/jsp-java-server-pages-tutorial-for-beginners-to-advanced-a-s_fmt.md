
# JSP (Java Server Pages) 入门到高级教程：分步指南

作者：Ravi Prasad

# 第 3 章：架构

## JSP 处理过程

# 第 4 章：生命周期

## JSP 遵循的路径

1. JSP 编译
2. JSP 初始化
3. JSP 执行
4. JSP 清理

# 第 5 章：语法

## JSP 元素

- 脚本段 (Scriptlet)
- JSP 声明 (Declarations)
- JSP 表达式 (Expression)
- JSP 注释
- 注释测试
- JSP 指令 (Directives)
- JSP 动作 (Actions)
- JSP 隐式对象
- 控制流语句
- 决策语句
- 循环语句
- JSP 运算符
- JSP 字面量

# 第 6 章：指令

- JSP - page 指令 (page Directive)
- 属性 (Attributes)
- include 指令
- taglib 指令

# 第 7 章：动作 (Actions)

## 常用属性

- Id 属性
- scope 属性

## 核心动作

- `<jsp:include>` 动作
- 示例
- include 动作示例
- `<jsp:useBean>` 动作
- `<jsp:setProperty>` 动作
- `<jsp:getProperty>` 动作
- 示例
- 在 JSP 中使用 JavaBeans
- `<jsp:forward>` 动作
- 示例
- `<jsp:plugin>` 动作
- `<jsp:element>` 动作
- `<jsp:attribute>` 动作
- `<jsp:body>` 动作
- `<jsp:text>` 动作

# 第 8 章：隐式对象

- request 对象
- response 对象
- out 对象
- session 对象
- application 对象
- config 对象
- pageContext 对象
- page 对象
- exception 对象

# 第 9 章：客户端请求

- HttpServletRequest 对象
- HTTP Header 请求示例
- HTTP Header 响应示例
- 自动刷新 Header 示例

# 第 10 章：服务器响应

- HttpServletResponse 对象
- HTTP Header 响应示例
- 自动刷新 Header 示例

# 第 11 章：HTTP 状态码

- 设置 HTTP 状态码的方法
- HTTP 状态码示例

# 第 12 章：HTTP 状态 407 - 需要认证

- Apache Tomcat/5.5.29

# 第 13 章：表单处理

- 表单处理中的方法
- GET 方法
- POST 方法
- 使用 JSP 读取表单数据
- 使用 URL 的 GET 方法示例

# 第 14 章：使用 GET 读取表单数据

- 使用表单的 GET 方法示例
- 使用表单的 POST 方法示例
- 将选择框数据传递给 JSP 页面

# 第 15 章：读取选择框数据

- 读取所有表单参数

# 第 16 章：过滤器 (Filters)

- Servlet Filter 方法
- JSP Filter 示例
- Web.xml 中的 JSP Filter 映射
- 使用多个过滤器

## Filter 应用顺序

# 第 17 章：Cookie 处理

- Cookie 的结构
- Servlet Cookies 方法
- 使用 JSP 设置 Cookie

### 第 1 步：创建 Cookie 对象
### 第 2 步：设置有效期
### 第 3 步：将 Cookie 发送到 HTTP 响应头中

- 示例
- 使用 JSP 读取 Cookie
- 示例
- 找到 Cookie 名称和值
- 使用 JSP 删除 Cookie
- 示例
- Cookie 名称和值
- 找到 Cookie 名称和值

# 第 18 章：会话跟踪 (Session Tracking)

- 在 Web 客户端和服务器之间维持 Session
- Cookies
- 隐藏表单字段
- URL 重写
- session 对象
- 会话跟踪示例
- 欢迎访问我的网站
- 欢迎回到我的网站
- 删除会话数据

# 第 19 章：文件上传

- 创建文件上传表单
- 编写后端 JSP 脚本

# 第 20 章：处理日期

- 获取当前日期

# 第 21 章：显示当前日期

- Mon Jun 21 21:46:49 GMT+04:00 2010
- 日期比较
- 使用 SimpleDateFormat 进行日期格式化

# 第 22 章：显示当前日期

- Mon 2010.06.21 at 10:06:44 PM GMT+04:00
- SimpleDateFormat 格式代码

# 第 23 章：页面跳转

# 第 24 章：访问计数器

- 示例

# 第 25 章：自动刷新

- 动态页面
- 自动刷新示例
- 自动 Header 示例

# 第 26 章：发送邮件

- 动态内容
- 发送邮件

# 第 27 章：使用

- 动态页面
- 使用 servlet

# 第 28 章：标准标签库 (JSTL)

- 核心库
- 核心标签
- 格式化标签
- SQL 标签
- XML 标签
- 函数

# 第 29 章：数据库

- 第 1 步
- 第 2 步
- 第 3 步
- SELECT 操作
- INSERT 操作
- DELETE 操作

# 第 30 章：XML

- 动态页面
- 展示 XML
- 使用 JSP 创建 XML

# 第 31 章：JavaBeans

- 普通页面
- 访问 JavaBeans
- 访问属性

# 第 32 章：自定义标签

- “Hello”
- 访问标签
- 访问属性

# 第 33 章：表达式语言 (EL)

- 基础语法
- 在 JSP 中
- 在 servlets 中
- pageContext 对象
- param 对象
- scope 对象
- header 对象

# 第 34 章：用户代理 (User Agent)

- 示例

# 第 35 章：异常处理

- 异常异常
- 运行时异常
- 错误
- 使用 exception 对象

# 第 36 章：try/Catch 块

- 使用 servlet

# 第 37 章：调试

- `System.out.println()`
- 调试工具
- 使用调试器
- 使用注释
- 客户端与服务器
- 重要提示

# 第 38 章：安全

- 基于角色
- 基于表单
- servlet 中的程序化安全

# 第 39 章：国际化 (i18n)

- 检测本地语言
- 示例
- 设置
- 日期
- 货币
- 百分比

SSI 确实是用于简单的包含，而不是用于那些使用数据、建立数据库连接等的“真实”程序。

## 对比 JavaScript

JavaScript 可以在客户端动态生成 HTML，但很难与 Web 服务器交互以执行诸如数据库访问和图像处理等复杂任务。

## 对比 静态 HTML

当然，普通的 HTML 无法包含动态信息。

## 接下来是什么？

我将一步步教你如何配置环境以开始学习 JSP。我假设你在 Java 编程方面拥有良好的实战经验，以便继续学习 JSP。

如果你不熟悉 Java 编程语言，我们建议你先阅读你的 Java 教程以了解 Java 编程。

# 第 2 章：环境搭建

开发环境是你开发 JSP 程序、测试它们并最终运行它们的地方。

本教程将引导你搭建 JSP 开发环境，其中涉及以下步骤：

## 搭建 Java 开发工具包 (JDK)

这一步涉及下载 Java 软件开发包 (SDK) 的实现，并相应地设置 `PATH` 环境变量。

你可以从 Oracle 的 Java 网站下载 SDK – Java SE Downloads。

一旦下载了 Java 实现，请按照给出的说明进行安装和配置。最后，将 `PATH` 和 `JAVA_HOME` 环境变量指向包含 `java` 和 `javac` 的目录，通常分别为 `java_install_dir/bin` 和 `java_install_dir`。

如果你在 Windows 上运行并将 SDK 安装在 `jdk1.5.0_20` 中，你需要在你的 `C:\autocec.bat` 文件中添加该行。

```
set PATH = C:\jdk1.5.0_20;bin;%PATH%
set JAVA_HOME = C:\jdk1.5.0_20
```

或者，在 Windows NT/2000/XP 上，你也可以右键点击“我的电脑”，选择“属性”，然后点击“高级”，最后点击“环境变量”。然后更新 `PATH` 值并点击“确定”按钮。

在 Unix（Solaris, Linux 等）上，如果 SDK 安装在 `/usr/local/jdk1.5.0_20` 且你使用 C shell，你会将以下内容放入 `.shrc` 文件。

```
setenv PATH /usr/local/jdk1.5.0_20/bin:$PATH
setenv JAVA_HOME /usr/local/jdk1.5.0_20
```

或者，如果你使用如 Borland JBuilder、IntelliJ IDEA 或 Sun ONE Studio 等集成开发环境 (IDE)，编译并运行一个简单的程序以确认 IDE 知道你将 Java 安装在了哪里。

## 搭建 Web 服务器：Tomcat

市场上有很多支持 JavaServer Pages (JSP) 和 Servlets 开发的 Web 服务器。某些 Web 服务器可以免费下载，Tomcat 就是其中之一。

Apache Tomcat 是 JavaServer Pages 和 Servlet 技术的开源软件实现，可以作为独立的服务器用于测试 JSP 和 Servlets，并可以与 Apache Web 服务器集成。以下是在你的机器上设置 Tomcat 的步骤：

1. 从 `https://tomcat.apache.org/` 下载最新版本的 Tomcat。
2. 一旦下载了安装包，请将二进制发行包解压到方便的位置。例如，在 Windows 上的 `C:\apache-tomcat-5.5.29` 或 Linux/Unix 上的 `/usr/local/apache-tomcat-5.5.29`，并创建指向这些位置的 `CATALINA_HOME` 环境变量。

可以通过在 Windows 机器上执行以下命令启动 Tomcat ——

```
%CATALINA_HOME%\bin\startup.bat
```

或

```
C:\apache-tomcat-5.5.29\bin\startup.bat
```

可以通过在 Unix (Solaris, Linux 等) 机器上执行以下命令启动 Tomcat ——

```
$CATALINA_HOME/bin/startup.sh
```

或

```
/usr/local/apache-tomcat-5.5.29/bin/startup.sh
```

成功启动后，通过访问 `http://localhost:8080` 可以看到 Tomcat 的默认页面。如果你看到此页面，说明你已成功启动了 Tomcat。恭喜！

6. Web 服务器以静态 HTML 内容的形式将 HTTP 响应转发到您的浏览器。
7. 最后，网页浏览器处理 HTTP 响应中动态生成的 HTML 页面，就像处理静态页面一样。

所有提到的步骤都可以在图中看到——

通常情况下，JSP 引擎会检查是否已经存在该文件的 servlet，以及 JSP 的修改日期是否早于该 servlet。如果 JSP 比生成的 servlet 要旧，则 JSP 容器会假设 JSP 尚未发生变化，且生成的 servlet 仍然与 JSP 内容匹配。这使得过程比其他脚本语言（如 PHP）更高效，因此速度也更快。

在某种程度上，JSP 页面只是编写 servlet 的另一种方式，而不需要成为 Java 编程高手。除了翻译阶段外，JSP 页面的处理方式与普通 servlet 完全相同。

# 第 4 章：生命周期

在本章中，我们将讨论 JSP 的生命周期。理解 JSP 底层功能的关键在于理解它们所遵循的简单生命周期。这类似于：

JSP 生命周期被定义为从创建到销毁的过程。Servlet 生命周期额外多了一个步骤，即需要将 JSP 编译为 servlet。

## JSP 遵循的路径

以下是 JSP 遵循的路径——

1. 编译
2. 初始化
3. 执行
4. 清理

JSP 生命周期的四个主要阶段与 Servlet 生命周期非常相似。这四个阶段在下方描述——

## JSP 编译

当浏览器请求 JSP 时，JSP 引擎首先检查是否需要编译该页面。如果该页面从未被编译过，或者 JSP 自上次编译以来被修改过，则 JSP 引擎将编译该页面。

编译过程涉及三个步骤：

1. 解析 JSP。
2. 将 JSP 转换为 servlet。
3. 编译 servlet。

## JSP 初始化

当容器加载一个 JSP 时，它会在处理请求之前调用 `jspInit()` 方法。如果您需要执行特定于 JSP 的初始化，请重写 `jspInit()` 方法——

```java
public void jspInit() {
    // 初始化代码...
}
```

通常，初始化只执行一次，并且与 servlet init 方法一样，您通常会在 `jspInit` 方法中初始化数据库连接、打开文件并创建查找表。

## JSP 执行

JSP 生命周期的这一阶段代表了直到 JSP 被销毁的所有请求的交互。

每当浏览器请求 JSP 且页面已加载并初始化时，JSP 引擎会调用 JSP 中的 `_jspService()` 方法。

`_jspService()` 方法接受 `HttpServletRequest` 和 `HttpServletResponse` 作为其参数，如下——

```java
void _jspService(HttpServletRequest request, HttpServletResponse response) {
    // 服务处理代码...
}
```

JSP 的 `jspService` 方法是根据请求调用的。它负责为该请求生成响应，而且该方法还负责对所有 HTTP 方法（即 GET、POST、DELETE 等）生成响应。

## JSP 清理

JSP 生命周期的销毁阶段代表 JSP 从容器中移除的过程。

`jspDestroy` 方法是 servlet `destroy` 方法在 JSP 中的对应项。当您需要执行任何清理工作（如释放数据库连接或关闭文件）时，请重写 `jspDestroy`。

`jspDestroy()` 方法具有以下形式——

```java
public void jspDestroy() {
    // 您的清理代码放在这里。
}
```

# 第 5 章：语法

在本章中，我们将讨论 JSP 中的语法。我们将理解与 JSP 开发相关的语法（即元素）的基本用法。

## JSP 元素

JSP 的元素在下方描述——

## 脚本段 (Scriptlet)

脚本段可以包含任意数量 Java 语言语句、变量或方法声明，或者在页面脚本语言中有效的表达式。

以下是脚本段的语法——

```
<% code fragment %>
```

您可以编写脚本段的 XML 等价形式——

```
<% code fragment %>
```

（注：此处 OCR 文本是碎片化的，我将根据可用片段提供逻辑流。）

将 JavaBean 的属性插入输出中。

- 5 `jsp:forward`：将请求者重定向到新页面。
- 6 `jsp:plugin`：生成特定浏览器的代码，为 Java 插件创建 `OBJECT` 或 `EMBED` 标签。
- 7 `jsp:element`：动态定义 XML 元素。
- 8 `jsp:attribute`：定义动态定义的 XML 元素的属性。
- 9 `jsp:body`：定义动态定义的 XML 元素的体。
- 10 `jsp:text`：用于在 JSP 页面和文档中写入模板文本。

我们将在单独的章节 JSP - Actions 中解释 JSP 动作。

JSP 支持九个自动定义的变量，这些变量也称为隐式对象。

这些变量是——

## JSP 隐式对象

| 序号 | 对象与描述 |
| --- | --- |
| 1 | request：这是与请求关联的 `HttpServletRequest` 对象。 |
| 2 | response：这是与客户端响应关联的 `HttpServletResponse` 对象。 |
| 3 | out：这是用于向客户端发送输出的 `PrintWriter` 对象。 |
| 4 | session：这是与请求关联的 `HttpSession` 对象。 |
| 5 | application：这是与应用上下文关联的 `ServletContext` 对象。 |
| 6 | config：这是与页面的 `ServletConfig` 对象。 |
| 7 | pageContext：它封装了对特定服务器功能的使用，如更高性能的 `JSPWriters`。 |
| 8 | page：这仅仅是 `this` 的同义词，用于调用翻译后的 servlet 类定义的方法。 |
| 9 | Exception：对象允许指定的 JSP 访问异常数据。 |

我们将在单独的章节 JSP - Implicit Objects 中解释隐式对象。

## 控制流语句

你可以在你的 JSP 编程中使用 Java 的所有 API 和构建模块，包括决策语句、循环等。

## 决策语句

`if...else` 块的起始类似于普通的脚本段（Scriptlet），但脚本段在每行结束时都会关闭，并在脚本标签之间包含 HTML 文本。



# JSP 控制流与动作详解

## 控制流语句

你可以在 JSP 编程中使用 Java 的所有 API 和构建模块，包括决策语句、循环等。

### 决策语句

`if...else` 块的起始类似于普通的脚本段，但脚本段在每行结束时都会关闭，并在脚本标签之间包含 HTML 文本。

```jsp
<%! int day = 3; %>
<html>
<head><title>IF...ELSE Example</title></head>
<body>
<% if (day == 1 || day == 7) { %>
<p> Today is weekend</p>
<% } else { %>
<p> Today is not weekend</p>
<% } %>
</body>
</html>
```

上述代码将生成以下结果：

Today is not weekend

现在来看 `switch...case` 块，它使用 `out.println()` 在脚本段内部编写，方式略有不同——

```jsp
<%! int day = 3; %>
<html>
<head><title>SWITCH...CASE Example</title></head>
<body>
<%
switch(day) {
case 0:
out.println("It's Sunday.");
break;
case 1:
out.println("It's Monday.");
break;
case 2:
out.println("It's Tuesday.");
break;
case 3:
out.println("It's Wednesday.");
break;
case 4:
out.println("It's Thursday.");
break;
case 5:
out.println("It's Friday.");
break;
default:
out.println("It's Saturday.");
}
%>
</body>
</html>
```

上述代码将生成以下结果——

It's Wednesday.

### 循环语句

你还可以在你的 JSP 编程中使用 Java 中的基本循环块：`for`、`while` 和 `do...while` 块。

#### for 循环示例

```jsp
<%! int fontSize; %>
<html>
<head><title>FOR LOOP Example</title></head>
<body>
<% for(fontSize=14; fontSize<=18; fontSize++) { %>
<p style="font-size:<%=fontSize%>px;">Text sample</p>
<% } %>
</body>
</html>
```

上述代码将生成以下结果：

Text sample (14px)

Text sample (15px)

Text sample (16px)

Text sample (17px)

Text sample (18px)

> **注**：原文示例中 `for` 循环代码不完整，此处根据逻辑补全了预期结构（如 `<%=fontSize%>`）以保持理解。

#### while 循环示例

```jsp
<%! int fontSize = 14; %>
<html>
<head><title>WHILE Loop Example</title></head>
<body>
<% while(fontSize <= 18) { %>
<p style="font-size:<%=fontSize%>px;">Text sample</p>
<% fontSize++; } %>
</body>
</html>
```

> **注**：原文中 `while` 循环语法在 Java 中是错误的（误用了 `for` 循环语法），此处已修正为标准 `while` 循环结构并补全逻辑。

#### do...while 循环示例

```jsp
<%! int fontSize; %>
<html>
<head><title>DO...WHILE Loop Example</title></head>
<body>
<% fontSize=14; do { %>
<p style="font-size:<%=fontSize%>px;">Text sample</p>
<% } while(fontSize++<=18); %>
</body>
</html>
```

上述代码将生成以下结果：

Text sample (14px)

Text sample (15px)

Text sample (16px)

Text sample (17px)

Text sample (18px)

---

## JSP 指令

### include 指令

该指令的通用用法形式如下：

```jsp
<%@ include file = "relative url" %>
```

`include` 指令中的 `file` 实际上是一个相对 URL。如果你只指定带有关联路径的文件，JSP 编译器将假设该文件与你的 JSP 在同一目录下。

你可以通过以下方式编写上述语法的 XML 等效代码：

```jsp
<jsp:directive.include file = "relative url" />
```

关于 include 指令的更多信息，请查看[include 指令]。

### taglib 指令

Java Pages API 允许你定义类似于 HTML 或 XML 标签的自定义 JSP 标签；标签库是一组实现自定义行为的定义标签。

`taglib` 声明你的 JSP 页面使用一组自定义标签，标识标签库的位置，并提供了识别 JSP 页面中自定义标签的方法。

`taglib` 指令遵循下方的语法：

```jsp
<%@ taglib uri="uri" prefix="prefixOfTag" %>
```

在这里，`uri` 属性解析为容器理解的位置，`prefix` 属性告知哪些标记部分是自定义动作。

你可以通过以下方式编写上述语法的 XML 等效代码：

```jsp
<jsp:directive.taglib uri = "uri" prefix = "prefixTag" />
```

关于 taglib 指令的更多信息，请查看[Taglib 指令]。

---

# 第 7 章：动作

在本章中我们将讨论 JSP 中的动作。这些动作使用 XML 语法来控制 servlet 引擎的行为。你可以动态插入文件、重用 JavaBeans 组件、将用户跳转到另一个页面或为 Java 插件生成 HTML。

动作元素只有一种语法，因为它符合 XML 标准：

```jsp
<jsp:action_name attribute = "value" />
```

动作元素基本上是预定义的函数。下表列出了这些 JSP 动作：

| 序号 | 语法 | 目的 |
|---|---|---|
| 1 | `jsp:include` | 在请求时包含文件。 |
| 2 | `jsp:useBean` | 查找或实例化 JavaBean。 |
| 3 | `jsp:setProperty` | 设置 JavaBean 的属性。 |
| 4 | `jsp:getProperty` | 将 JavaBean 的属性插入输出。 |
| 5 | `jsp:forward` | 将请求者转发到新页面。 |
| 6 | `jsp:plugin` | 生成特定浏览器的代码，为 Java 插件创建 `OBJECT` 或 `EMBED` 标签。 |
| 7 | `jsp:element` | 动态定义 XML 元素。 |
| 8 | `jsp:attribute` | 定义动态定义的 XML 元素的属性。 |
| 9 | `jsp:body` | 定义动态定义的 XML 元素的体。 |
| 10 | `jsp:text` | 用于在 JSP 页面和文档写入模板文本。 |

## 通用属性

所有动作元素共有两个属性：`id` 属性和 `scope` 属性。

### id 属性

`id` 属性唯一标识动作元素，允许在 JSP 页面内部引用它。如果动作创建了对象的实例，可以通过隐式对象 `PageContext` 使用 `id` 值引用它。

### scope 属性

此属性标识动作的生命周期。`id` 属性和 `scope` 属性直接相关，因为 `scope` 属性决定与之关联对象的寿命。`scope` 有四个可能的值：`page`、`request`、`session` 和 `application`。

## <jsp:include> 动作

此动作将文件插入生成的页面中。语法如下：

```jsp
<jsp:include page = "relative URL" flush="true" />
```

与 `include` 指令（在 JSP 页面翻译为 servlet 时插入文件）不同，此动作在请求动作时插入文件。

下表列出了与 include 动作相关的属性：

| 序号 | 属性 | 描述 |
|---|---|---|
| 1 | `page` | 要包含的页面的相对 URL。 |
| 2 | `flush` | 布尔属性，决定包含资源在包含之前其缓冲区是否被刷新。 |

### 示例

我们如下定义以下文件：(a) `date.jsp` 和 (b) `main.jsp`。

以下是 `date.jsp` 文件的内容：

```jsp
<p>今天的日期: <%= (new java.util.Date()).toString() %></p>
```

以下是 `main.jsp` 文件的内容：

```html
<html>
<head>
<title>Include 动作示例</title>
</head>
<body>
<h2>include 动作示例</h2>
<jsp:include page = "date.jsp" flush="true" />
</body>
</html>
```

现在我们将所有这些文件放在根目录下并访问 `main.jsp`。你将收到以下输出：

> **include 动作示例**
>
> 今天的日期：12-Sep-2010 14:54:22

## <jsp:useBean> 动作

该动作是非常动态的。它使用 `id` 和 `scope` 变量查找现有对象。如果未找到对象，它将尝试创建指定的对象。

加载 bean 的最简单方法如下：

```jsp
<jsp:useBean id = "name" class = "package.class" />
```

一旦加载了 bean，你可以使用 `jsp:setProperty` 和 `jsp:getProperty` 动作来修改和检索 bean 的属性。

下表列出了与 bean 动作相关的属性：

| 序号 | 属性 | 描述 |
|---|---|---|
| 1 | `class` | bean 的完整包名。 |
| 2 | `type` | 指定引用对象的变量类型。 |
| 3 | `beanName` | `java.beans.Beans` 类 `instantiate()` 方法指定的 bean 名称。 |

在给出与这些动作相关的有效示例之前，我们现在讨论 `jsp:setProperty` 和 `jsp:getProperty` 动作。

## <jsp:setProperty> 动作

`setProperty` 动作设置 Bean 的属性。在此之前必须已经定义了 Bean。使用 `setProperty` 的基本方法有两种：

1. 你可以在 `jsp:useBean` 元素之后但在外部使用 `id`，如下：

```jsp
<jsp:useBean id = "myName" ... />
<jsp:setProperty name = "myName" property = "someProperty" .../>
```

在这种情况下，无论实例化了新 bean 还是发现了现有 bean，`setProperty` 都会执行。

2. 另一个 `setProperty` 可以出现在 `jsp:useBean` 元素体内的上下文如下所示：

```jsp
<jsp:useBean id = "myName" ... >
    <jsp:setProperty name = "myName" property = "someProperty" .../>
</jsp:useBean>
```

只有在实例化了新 bean 时，`setProperty` 才会执行。

下表列出了与 `setProperty` 动作相关的属性：

| 序号 | 属性 | 描述 |
|---|---|---|
| 1 | `name` | 要设置的 bean。Bean 必须已定义。 |
| 2 | `property` | 你想要设置的属性。 |
| 3 | `value` | 分配给给定属性的值。如果参数值为 null 或参数不存在，则忽略 `setProperty` 动作。 |
| 4 | `param` | `param` 属性是要接收的请求参数的名称。 |

## <jsp:getProperty> 动作

`getProperty` 动作用于检索给定属性的值并转换为字符串，最后将其插入输出中。

`getProperty` 动作只有两个属性，都是必需的。`getProperty` 动作的语法如下：

```jsp
<jsp:useBean id = "myName" ... />
...
<jsp:getProperty name = "myName" property = "someProperty" />
```

下表列出了与 `getProperty` 动作相关的必需属性：

| 序号 | 属性 | 描述 |
|---|---|---|
| 1 | `name` | 要检索的 Bean。Bean 必须已定义。 |
| 2 | `property` | 要检索的属性名称。 |



| 序号 | 属性 | 描述 |
| :--- | :--- | :--- |
| 2 | `property` | `property` 属性是要检索的 Bean 属性名称。 |

## 示例

让我们定义一个将在示例中进一步使用的 test bean：

```java
/* File: TestBean.java */
package action;

public class TestBean {
    private String message = "No message specified";

    public String getMessage() {
        return message;
    }
    public void setMessage(String message) {
        this.message = message;
    }
}
```

编译代码生成 `TestBean.class`，并确保你已将 `TestBean.class` 复制到 `C:\apache-tomcat-7.0.2\webapps\WEB-INF\classes` 文件夹，并且 `CLASSPATH` 变量也应设置正确。

现在在 `main.jsp` 中使用代码，它加载此 Bean 并设置/获取简单的 String 参数：

```jsp
<html>
<head>
<title>Using JavaBeans in JSP</title>
</head>
<body>
<center>
<h2>Using JavaBeans in JSP</h2>
<jsp:useBean id="test" class="action.TestBean" />
<jsp:setProperty name="test" property="message" value="Hello JSP..." />
<jsp:getProperty name="test" property="message" />
</center>
</body>
</html>
```

运行结果：

> 收到一条消息....
> Hello JSP...

# 在 JSP 中使用 JavaBeans

## `<jsp:forward>` 动作

`<jsp:forward>` 动作会终止当前页面的执行，并将请求转发到另一个资源，例如静态页面、另一个 JSP 页面或 Java Servlet。

以下是 `<jsp:forward>` 动作的语法：

```jsp
<jsp:forward page="相对 URL" />
```

下表列出了与 `<jsp:forward>` 动作相关的必要属性：

| 序号 | 属性 | 描述 |
| :--- | :--- | :--- |
| 1 | `page` | 应该包含另一个资源的相对 URL，例如静态页面、另一个 JSP 页面或 Java Servlet。 |

### 示例

让我们重用以下两个文件：`date.jsp` 和 `main.jsp`。

**date.jsp** 文件内容：

```jsp
<p>今天的日期: <%= new java.util.Date().toLocaleString() %></p>
```

**main.jsp** 文件内容：

```jsp
<html>
<head>
<title>forward 动作示例</title>
</head>
<body>
<center>
<h2>forward 动作示例</h2>
<jsp:forward page="date.jsp" />
</center>
</body>
</html>
```

现在将所有这些文件都放在根目录下，并尝试访问 `main.jsp`。这将显示如下所示的结果（主页面的内容被舍弃，只显示了转发页面的内容）：

> 今天的日期：12-Sep-2010 14:54:22

## `<jsp:plugin>` 动作

`<jsp:plugin>` 动作用于将 Java 组件插入到 JSP 页面中。它确定浏览器类型并根据需要插入 `<object>` 或 `<embed>` 标签。

如果需要的插件不存在，它将下载插件并执行 Java 组件。该组件可以是 Applet 也可以是 JavaBean。

`<jsp:plugin>` 动作具有多个属性，对应于用于格式化 Java 组件的常用 HTML 标签。`<jsp:param>` 元素也可以用于向 Applet 或 Bean 发送参数。

以下是使用 `<jsp:plugin>` 动作的典型语法：

```jsp
<jsp:plugin type="applet" codebase="dirname" code="MyApplet.class" width="60" height="80">
    <jsp:param name="color" value="red" />
    <jsp:param name="background" value="black" />
    <jsp:fallback>
        无法初始化 Java 插件
    </jsp:fallback>
</jsp:plugin>
```

如果你感兴趣，可以使用某些 applet 尝试此动作。`<jsp:fallback>` 元素可以用于在组件失败时指定发送给用户的错误字符串。

## `<jsp:element>`、`<jsp:attribute>` 和 `<jsp:body>` 动作

`<jsp:element>`、`<jsp:attribute>` 和 `<jsp:body>` 动作用于动态定义 XML 元素。“动态”一词非常重要，因为这意味着 XML 元素可以在运行时生成，而不是编译时生成。

以下是一个动态定义 XML 元素的简单示例：

```jsp
<%@page language="java" contentType="text/html"%>
<html xmlns="http://www.w3.org/1999/xhtml" xmlns:jsp="http://java.sun.com/JSP/Page">
<head>
<title>生成 XML 元素</title>
</head>
<body>
<jsp:element name="xmlElement">
    <jsp:attribute name="xmlElementAttr">
        属性值
    </jsp:attribute>
    <jsp:body>
        XML 元素的体内容
    </jsp:body>
</jsp:element>
</body>
</html>
```

这将在运行时产生以下 HTML 代码：

```html
<html xmlns="http://www.w3.org/1999/xhtml" xmlns:jsp="http://java.sun.com/JSP/Page">
<head><title>生成动作</title></head>
<body>
<xmlElement xmlElementAttr="属性值">
XML 元素的体内容
</xmlElement>
</body>
</html>
```

## `<jsp:text>` 动作

`<jsp:text>` 可用于在 JSP 页面和文档中编写模板文本。以下是该动作的简单语法：

```jsp
<jsp:text>模板数据</jsp:text>
```

模板的主体不能包含其他元素；它只能包含文本和 EL 表达式（注意：EL 表达式将在随后的章节中解释）。注意，在 XML 文件中，你不能使用像 `${whatever > 0}` 这样的表达式，因为大于符号是非法的。相反，请使用 `gt` 形式，例如 `${whatever gt 0}`，或者另一种方法是将值嵌入到 CDATA 中。

### 示例

如果你需要包含 DOCTYPE 声明：

```jsp
<jsp:text>
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 1.0//EN" "http://www.w3.org/TR/REC/html4/strict.dtd">
</jsp:text>
<html>
<head><title>JSP 动作</title></head>
<body>
<h2>欢迎来到 JSP</h2>
</body>
</html>
```



<jsp:text>
</jsp:text>

在本章中，我们将讨论隐式对象（Implicit Objects）。这些是每个页面都可用的 Java 对象。

| 序号. | 对象与描述 |
| :--- | :--- |
| 1 | `request` | 这是一个 `HttpServletRequest` 对象。 |
| 2 | `response` | 这是一个 `HttpServletResponse` 对象。 |
| 3 | `out` | 这是一个 `JspWriter` 对象。 |
| 4 | `session` | 这是一个 `HttpSession` 对象。 |
| 5 | `application` | 这是一个 `ServletContext` 对象。 |
| 6 | `config` | 这是一个 `ServletConfig` 对象。 |
| 7 | `pageContext` | 这是一个 `pageContext` 对象。 |
| 8 | `page` | 这是一个 `page` 对象。 |
| 9 | `Exception` | 这是一个 `Exception` 对象。 |

## request 对象

`request` 对象是 `javax.servlet.http.HttpServletRequest` 的实例。每当客户端请求 JSP 时，服务器都会创建一个新对象来表示该请求。

`request` 对象提供了获取头部信息的方法。我们将在随后的章节“客户端请求”中介绍与请求相关的所有方法。

## response 对象

`response` 对象是 `javax.servlet.http.HttpServletResponse` 的实例。正如服务器创建请求对象一样，它也会创建一个表示响应的对象。

`response` 对象还定义了创建新头部的接口。通过它 JSP 程序员可以添加 cookie 或状态码。

## out 对象

`out` 对象是 `javax.servlet.jsp.JspWriter` 实例，用于向响应发送内容。初始 `JspWriter` 的实例化取决于页面是否启用缓冲区。可以通过页面指令的 `buffered='false'` 属性轻松关闭缓冲区。

`JspWriter` 对象包含许多与 `java.io.PrintWriter` 类相同的方法。然而，`JspWriter` 许多许多处理缓冲的实例方法。

## session 对象

`session` 对象是 `javax.servlet.http.HttpSession` 的实例，其行为与 Java Servlet 中的会话行为完全一致。`session` 对象用于跟踪客户端请求之间的会话。我们将在随后的章节“会话跟踪”中介绍会话的所有用法。

## application 对象

`application` 对象是对生成的 Servlet 的 `ServletContext` 对象的直接封装。该对象代表了 JSP 页面的整个生命周期。该对象在 JSP 页面初始化时创建，并在 JSP 页面被 `jspDestroy()` 方法移除时被移除。

通过向 `application` 添加属性，可以确保组成 Web 应用程序的所有 JSP 文件都能访问它。我们将在“JSP - 访问计数器”章节中检查应用对象的使用。

## config 对象

`config` 对象是 `javax.servlet.ServletConfig` 的实例化，它是对生成的 servlet 的 `ServletConfig` 对象的直接封装。

此对象允许 JSP 程序员访问 Servlet 或 JSP 引擎的初始化参数，例如路径或文件位置。

以下 `config` 方法是你唯一可能用到的方法，且其用法非常简单：
`config.getServletName();`

它返回 servlet 名称，即在 `WEB-INF/web.xml` 文件定义的 `<servlet-name>` 元素包含包含字符串。

## pageContext 对象

`pageContext` 对象是 `javax.servlet.PageContext` 对象的实例。`pageContext` 对象用于表示整个 JSP 页面。

此对象旨在作为访问页面信息的一种手段，同时避免了大多数实现细节。

此对象存储了每个请求的 `request` 和 `response` 对象。`application`、`config`、`session` 和 objects 是通过访问该对象的属性派生的。

`pageContext` 对象还包含有关发布到 JSP 页面的指令的信息，包括缓冲区信息、`errorPageURL` 和页面范围（page scope）。

`pageContext` 定义了几个字段，包括 `PAGE_SCOPE`、`REQUEST_SCOPE`、`SESSION_SCOPE` 和 `APPLICATION_SCOPE`，它支持超过 40 个方法，其中一半继承自 `javax.servlet.jsp.JspContext` 类。

重要方法之一是 `removeAttribute`。该方法接受一个或两个参数。例如，`pageContext.removeAttribute("attrName")` 从所有范围中删除属性，而以下代码将其从页面范围中删除——`pageContext.removeAttribute("attrName", PAGE_SCOPE);`

`pageContext` 的使用可以在“JSP - 文件上传”章节中进行检查。

## page 对象

此对象是对页面实例的实际引用。它可以被认为是一个代表整个 JSP 页面的对象。

`page` 对象实际上是此对象的直接同义词。

## exception 对象

`exception` 对象是一个封装器，包含了上一个页面抛出的异常。它通常用于对错误状况生成适当的响应。

我们将在“JSP - 异常处理”章节介绍该对象的完整用法。

# 第9 章：客户端请求

在本章中，我们将讨论 JSP 中的客户端请求。当浏览器请求网页时，会向 Web 服务器发送大量信息。这些信息无法直接读取，因为它们是作为 HTTP 请求头的一部分传输的。你可以检查 HTTP 协议以获取更多相关信息。

下表列出了来自浏览器的重要头部信息。这些信息在 Web 编程中频繁使用——

| 序号 | 头部与描述 |
| --- | --- |
| 1 | `Accept` | 此头部指定了浏览器或其他客户端可以处理的 MIME 类型。`image/png` 或 `image/jpeg` 是两种常见的可能。 |
| 2 | `Accept-Charset` | 此头部指定了浏览器可以用于显示信息的字符集。例如，ISO-8859-1。 |
| 3 | `Accept-Encoding` | 此头部指定了浏览器知道如何处理的编码类型。`gzip` 或 `compress` 是两种常见的可能。 |
| 4 | `Accept-Language` | 此头部指定了客户端偏好的语言，以防 servlet 生成多种语言的结果。例如 `en-us` 等。 |
| 5 | `Authorization` | 此头部用于客户端在访问密码保护的网页时识别自己的身份。 |
| 6 | `Connection` | 此头部指示客户端是否可以处理持久 HTTP 连接。持久连接允许客户端或其他浏览器通过单个请求检索多个文件。`Keep-Alive` 的值意味着应该使用持久连接。 |
| 7 | `Content-Length` | 此头部仅适用于 POST 请求，并给出 POST 数据的大小（字节为）。 |
| 8 | `Cookie` | 此头部将 cookie 返回给之前发送给浏览器的服务器。 |
| 9 | `Host` | 此头部指定了与原始 URL 相同的主机和端口。 |
| 10 | `If-Modified-Since` | 此头部指示客户端仅在页面在指定日期之后发生更改时才需要页面。如果没有更新版本，服务器将发送代码 304 表示 `Not Modified`（未修改）头部。 |
| 11 | `If-Unmodified-Since` | 此头部是 `If-Modified-Since` 的反向；它指定只有当文档早于指定日期时操作才成功。 |
| 12 | `Referrer` | 此头部指示引用页面的 URL。例如。 |
| 13 | `User-Agent` | 此头部识别浏览器和其他客户端。 |

## HttpServletRequest

`request` 对象是 `javax.servlet.http.HttpServletRequest` 的实例。`request` 对象提供了获取信息的方法。

| 序号 | 方法与描述 |
| --- | --- |
| 1 | `getCookies()` | 返回一个包含所有已发送 Cookie 对象的数组。 |
| 2 | `getHeaderNames()` | 返回头部的枚举。 |
| 3 | `getHeader(String name)` | 以 String 形式返回指定请求头部的值。 |
| 4 | `getParameterNames()` | 返回参数的枚举。 |
| 5 | `getSession()` | 返回与此请求关联的会。 |
| 6 | `getSession(boolean create)` | 返回当前会，如果没有会，则创建一个。 |
| 7 | `getLocale()` | 返回偏好的本地区域（Locale）。 |
| 8 | `getAttribute(String name)` | 以 Object 形式返回命名属性的值。 |
| 9 | `getInputStream()` | 使用二进制数据检索请求体。 |
| 10 | `getAuthType()` | 返回保护 servlet 的认证方案名称。 |
| 11 | `getCharacterEncoding()` | 返回正文中使用的字符编码名称。 |
| 12 | `getContentType()` | 返回请求体的 MIME 类型。 |
| 13 | `getPath()` | 返回请求 URI 中指示上下文的部分。 |
| 14 | `getServletPath()` | 返回调用 JSP 的请求 URL 部分。 |
| 15 | `getMethod()` | 返回所执行的 HTTP 方法名称。 |
| 16 | `getParameter(String name)` | 以 String 形式返回请求参数的值。 |
| 17 | `getParameterValues(String name)` | 返回给定参数的值数组。 |
| 18 | `getPathInfo()` | 与 URL 关联的额外路径信息。 |
| 19 | `getProtocol()` | 返回请求使用的协议名称和版本。 |
| 20 | `getQueryString()` | 返回请求 URL 中路径后的查询字符串。 |
| 21 | `getRemoteAddr()` | 返回发送请求的客户端的网络协议（IP）地址。 |
| 22 | `getRemoteHost()` | 返回发送请求的客户端的全主机名。 |
| 23 | `getRemoteUser()` | 返回执行此请求的用户登录。 |
| 24 | `getURI()` | 返回请求 URL 从协议名称到查询字符串的部分。 |
| 25 | `getRequestedId()` | 返回客户端识别的会话 ID。 |

返回一个包含 String 对象的数组，其中包含给定请求参数的所有值；如果参数不存在则返回 null。

`boolean isSecure()`
返回一个布尔值，表示此请求是否是通过安全通道（如 HTTPS）发送的。

`int getContentLength()`
返回请求体的长度（字节），该长度由输入流提供；如果长度未知则返回 -1。

`int getHeader(String name)`
以 int 类型返回指定标头的值。

`int getServerPort()`
返回接收此请求的端口号。

## HTTP 头部请求示例

以下示例演示了如何使用 `HttpServletRequest` 的 `getHeaderNames()` 方法来读取 HTTP 头部信息。该方法返回一个枚举（Enumerationation），其中包含了与当前 HTTP 请求相关的头部信息。

一旦我们获取了 `Enumeration`，就可以按照标准方式遍历它。我们使用 `hasElements()` 方法确定何时停止，并使用 `nextElement()` 方法获取每个参数的名称。

```
<%@page import = "java.io.*,java.util.*" %>

<html>

<head>

<title>HTTP Header Request Example</title>

</head>

<body>

<center>

<h2>HTTP Header Request Example</h2>

<table width="100%" border="1" align="center">

<tr bgcolor="#949494">

<th>Header Name</th>

<th>Header Value</th>

</tr>

<%

Enumeration headerNames = request.getHeaderNames();

while(headerNames.hasElements()) {

String parameterName = (String)headerNames.nextElement();

out.print("<tr><td>" + parameterName + "</td></tr>\n");

String parameterValue = request.getHeader(parameterName);

out.print("<tr><td>" + parameterValue + "</td></tr>\n");

}

%>

</table>

</center>

</body>

</html>
```

现在，让我们将上述代码放入 `main.jsp` 中并尝试访问它。

## HTTP 头部请求示例（输出结果）

| 头部名称 (Header Name) | 值 (Value(s)) |
| --- | --- |
| accept | /* |
| accept-language | en-us |
| user-agent | Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; InfoPath.2; MS-RTC LM 8) |
| accept-encoding | gzip, deflate |
| host | localhost:8080 |
| connection | Keep-Alive |
| cache-control | no-cache |

你可以尝试以类似的方式处理所有方法。

# 第 10 章：服务器响应 (Server Response)

在本章中，我们将讨论 JSP 中的服务器响应。当 Web 服务器对 HTTP 请求做出响应时，响应通常由状态行、一些响应头部、一个空行以及正文文档组成。一个典型的响应如下：

```
HTTP/1.1 200 OK
Content-Type: text/html
Header2: ...
HeaderN: ...
(空行)
<!doctype ...>
<html>
<head>...</head>
<body>
...
</body>
</html>
```

状态行包含 HTTP 版本（示例中 `HTTP/1.1`）、状态码（示例中 `200`）以及一个与状态码对应的简短消息（示例中 `OK`）。

以下是从 Web 服务器返回浏览器的最常用的 HTTP 1.1 响应头部摘要。这些头部在 Web编程中被频繁使用：

| 序号 | 头部及描述 |
| --- | --- |
| 1 | `Allow` | 此头部指定服务器支持的请求方法（GET, POST 等）。 |
| 2 | `Cache-Control` | 此头部指定响应文档可以缓存的情况。它可以是 `public`（公共）、`private`（私有）或 `no-cache`（不缓存）等。`public` 表示文档可缓存；`private` 表示文档针对单个用户且只能存储在代理（非共享）缓存中；`no-cache` 表示文档永远不被缓存。 |
| 3 | `Connection` | 此头部指示浏览器是否使用持久 HTTP 连接。值 `close` 指示浏览器不使用持久连接，`keep-alive` 表示使用持久连接。 |
| 4 | `Content-Disposition` | 此头部允许你请求浏览器询问用户将响应保存为指定名称的文件。 |
| 5 | `Content-Encoding` | 此头部指定页面在传输过程中的编码方式。 |
| 6 | `Content-Language` | 此头部表示文档编写使用的语言。例如：en, en-us, ru 等。 |
| 7 | `Content-Length` | 此头部指示响应中的字节数。只有当浏览器使用持久（keep-alive）HTTP 连接时，才需要此信息。 |
| 8 | `Content-Type` | 此头部给出响应文档的 MIME（多用途互联网邮件扩展）类型。 |
| 9 | `Expires` | 此头部指定内容何时被认为已过期且不再被缓存。 |
| 10 | `Last-Modified` | 此头部指示文档最后一次更改的时间。客户端随后可以缓存文档，并在稍后的请求中通过 `If-Modified-Since` 请求头部提供日期。 |
| 11 | `Location` | 此头部指定重定向的地址。 |
| 12 | `Refresh` | 此头部指定在多久后刷新页面。 |
| | `Retry-After` | 此头部指定在多久后重试请求。 |
| | `Set-Cookie` | 此头部允许向浏览器设置 Cookie。 |
| | `Server` | 此头部指定生成响应的服务器。 |
| | `Vary` | 此头部指定根据哪些请求头部来决定缓存。 |
| | `WWW-Authenticate` | 此头部要求客户端进行身份验证。 |



# 自动刷新 Header 示例

```html
<title>自动刷新 Header 示例</title>
</head>
<body>
<center>
<h2>自动刷新 Header 示例</h2>
%%
// 设置刷新时间、自动重载时间为 5 秒
response.setHeader("Refresh", 5);

// 获取当前时间
Calendar calendar = new GregorianCalendar();

String am_pm;
int hour = calendar.get(Calendar.HOUR);
int minute = calendar.get(Calendar.MINUTE);
int second = calendar.get(Calendar.SECOND);

if(calendar.get(Calendar.AM_PM) == 0) {
  am_pm = "AM";
} else {
  am_pm = "PM";
}
String CT = "hour:" + ":" + second + ":" + am_pm;
out.println("Current Time is: " + CT + "\n");
%%
</center>
</body>
</html>
```

现在将上述代码放入 `main.jsp` 中并访问它。这将每隔 5 秒显示一次当前系统时间，如下所示。运行 JSP。你将收到输出：

## 自动刷新 Header 示例

Current Time is: 9:44:50 PM

你可以尝试以类似的方式实现其他方法。

# 第 11 章：HTTP 状态码

在本章中，我们将讨论 JSP 中的 HTTP 状态码。HTTP 请求和 HTTP 响应消息格式相似，具有以下结构：

- 初始状态行 + CRLF（回车 + 换行符，即换行）
- 零或多个响应头行 + CRLF
- 一个空行（即 CRLF）
- 可选的消息体，如文件、查询数据或查询输出。

例如，服务器响应头如下所示：

```text
HTTP/1.1 200 OK
Content-Type: text/html
Header2: ...
...
HeaderN: ...

(空行)
<!doctype...
<head>...</head>
<body>
</body>
</html>
```

状态行由 HTTP 版本（示例中的 `HTTP/1.1`）、状态码（示例中的 `200`）以及一个与状态码对应的非常短的说明（示例中的 `OK`）组成。

下表列出了 Web 服务器可能返回的 HTTP 状态码及相关消息：

| Code | Description |
|---|---|
| 100 | Continue | 服务器仅收到了请求的一部分，只要未被拒绝，客户端应继续发送请求。 |
| 101 | Switching Protocols | 服务器切换协议。 |
| 200 | OK | 请求正常。 |
| 201 | Created | 请求完成，并创建了新资源。 |
| 202 | Accepted | 请求已接受处理，但处理尚未完成。 |
| 203 | Non-authoritative Information | 非权威信息。 |
| 204 | No Content | 无内容。 |
| 205 | Reset Content | 重置内容。 |
| 206 | Partial Content | 部分内容。 |
| 300 | Multiple Choices | 链接列表；用户可以选择链接并跳转到该位置。最多五个地址。 |
| 301 | Moved | 请求的页面已移动到新的 URL。 |
| 302 | Found | 请求的页面临时移动到新的 URL。 |
| 303 | See Other | 可以在不同的 URL 下找到请求的页面。 |
| 304 | Not Modified | 未修改。 |
| 305 | Use Proxy | 使用代理。 |
| 306 | Unused | 此代码用于之前的版本。现不再使用，但保留了该代码。 |
| 307 | Temporary Redirect | 请求的页面临时移动到新的 URL。 |
| 400 | Bad Request | 服务器无法理解请求。 |
| 401 | Unauthorised | 请求的页面需要用户名和密码。 |
| 402 | Payment Required | 你尚不能使用此代码。 |
| 403 | Forbidden | 禁止访问请求的页面。 |
| 404 | Not Found | 服务器找不到请求的页面。 |
| 405 | Method Not Allowed | 请求中指定的方法不允许。 |
| 406 | Not Acceptable | 服务器只能生成客户端不接受的响应。 |
| 407 | Proxy Authentication Required | 在处理此请求之前，必须向代理服务器进行身份验证。 |
| 408 | Request Timeout | 请求耗时超过了服务器准备等待的时间。 |
| 409 | Conflict | 由于冲突无法完成请求。 |
| 410 | Gone | 请求的页面不再可用。 |
| 411 | Length Required | 未定义 "Content-Length"。服务器将不接受该请求。 |
| 412 | Precondition Failed | 请求中给出的前提条件被服务器评估为假。 |
| 413 | Request Entity Too Large | 服务器不接受请求，因为请求实体过大。 |
| 414 | Request-url Too Long | 服务器不接受请求，因为 URL 太长。这发生在你将带有长查询信息的 "post" 请求转换为 "get" 请求时。 |
| 415 | Unsupported Media Type | 服务器不接受请求，因为不支持媒体类型。 |
| 417 | Expectation Failed | 期望失败。 |
| 500 | Internal Server Error | 请求未完成，服务器遇到了意外状况。 |
| 501 | Not Implemented | 请求未完成，服务器不支持该功能。 |
| 502 | Bad Gateway | 请求未完成，服务器从上游服务器接收到无效响应。 |
| 503 | Service Unavailable | 服务不可用。 |
| 504 | Gateway Timeout | 网关超时。 |
| 505 | HTTP Not Supported | 服务器不支持此项。 |

# 设置状态码的方法

| No. | Method | Description |
|---|---|---|
| 1 | `setStatus(int statusCode)` | 设置响应的状态码。 |
| 2 | `sendRedirect(String url)` | 将客户端重定向到新的 URL。 |
| 3 | `sendError(int statusCode, String message)` | 向客户端发送错误响应。 |
| 4 | `setHeader(String name, String value)` | 设置响应中的特定头部。 |
| 5 | `addHeader(String name, String value)` | 向响应添加头部。 |
| 6 | `setContentType(String type)` | 设置响应的内容类型。 |
| 7 | `setCharacterEncoding(String encoding)` | 设置响应的字符编码。 |

JSP 根据情况使用以下方法自动处理数据解析：

- `getParameter(String name)`：你调用 `request.getParameter()` 方法获取参数值。
- `getParameterValues(String name)`：如果参数出现多次并返回多个值，则调用此方法。
- `getParameterNames()`：如果你想获取当前请求中所有参数的完整列表，请调用此方法。
- `getInputStream()`：调用此方法读取来自客户端的二进制数据流。

```html
<body>
</html>
```

现在在你浏览器的地址栏中输入 `http://localhost:8080/main.jsp?first_name=ZARA&last_name=ALI`。这将生成以下结果 ——

# 第 14 章：使用 GET 方法读取表单数据

* 名字 (First Name)：ZARA
* 姓 (Last Name)：ALI

## 使用表单 GET 方法示例

以下是一个使用 HTML 表单和提交按钮传递两个值的示例。我们将使用相同的 JSP `main.jsp` 来处理此输入。

```html
<html>
<body>
<form action="main.jsp" method="GET">
First Name: <input type="text" name="first_name">
<br />
Last Name: <input type="text" name="last_name">
<input type="submit" value="Submit" />
</form>
</body>
</html>
```

将此此 HTML 保留在 `Hello.htm` 文件中，并将其放入 `<Tomcat-installation-directory>/webapps/ROOT` 目录。当你访问 `http://localhost:8080/Hello.htm` 时，你将收到以下输出。

First Name:

Last Name:

<p>尝试输入名字和姓并点击提交按钮，在运行 tomcat 的本地机器上查看结果。根据提供的输入，它将生成与上述示例中提到的类似的结果。

## 使用表单 POST 方法示例

让我们对上面的 JSP 进行一些小的修改，以同时处理 GET 和 POST 方法。下面是 `main.jsp` JSP 程序，用于处理通过 GET 或 POST 方法由浏览器提供的输入。

事实上，上面的 JSP 没有变化，因为只是了传递参数的方法，并且没有将二进制数据传递给 JSP 程序。与文件处理相关的概念将在单独的章节中解释，在那个章节我们需要读取二进制数据流。

```html
<html>
<head>
<title>使用 GET 和 POST 方法读取表单数据</title>
</head>
<body>
<center>
<h1>使用 POST 方法读取数据</h1>
<ul>
<li><p><b>First Name:</b>
<%= request.getParameter("first_name")%
</p></li>
<li><p><b>Last Name:</b>
<%= request.getParameter("last_name")%
</p></li>
</ul>
</center>
</body>
</html>
```

以下是 `Hello.htm` 文件的内容 ——

```html
<html>
<body>
<form action="main.jsp" method="POST">
First Name: <input type="text" name="first_name" /><br>
Last Name: <input type="text" name="last_name" />
<input type="submit" value="Submit" />
</form>
</body>
</html>
```

现在让我们将 `main.jsp` 和 `hello.htm` 保放在 `<Tomcat-installation-directory>/webapps/ROOT` 目录中。当你访问 `http://localhost:8080/Hello.htm` 时，你将收到以下输出。

First Name:

Last Name:

尝试输入名字和姓并点击提交按钮，在运行 tomcat 的本地机器上查看结果。

根据提供的输入，你将收到与上述示例相似的结果。

## 向 JSP 程序传递复选框数据

当需要选择多个选项时，使用了复选框（Checkboxes）。

是一个带有两个复选框的表单的 **HTML 代码，CheckBox.htm** 示例。

```html
<html>
<body>
<form action="main.jsp" method="POST" target="_blank">
<input type="checkbox" name="maths" checked="checked" /> Maths
<input type="checkbox" name="physics" /> Physics
<input type="checkbox" name="chemistry" checked="checked" /> Chemistry
<input type="submit" value="Submit" />
</form>
</body>
</html>
```

上述代码将生成以下结果 ——

Maths Physics Chemistry

下面是处理浏览器提供的输入的 `main.jsp` JSP 程序。

```html
<html>
<head>
<title>读取复选框数据</title>
</head>
<body>
<h1>读取复选框数据</h1>
<ul>
<li><p><b>Maths:</b>
<%= request.getParameter("maths")%
</p></li>
<li><p><b>Physics:</b>
<%= request.getParameter("physics")%
</p></li>
<li><p><b>Chemistry:</b>
<%= request.getParameter("chemistry")%
</p></li>
</ul>
</body>
</html>
```

上述程序将生成：

# 第 15 章：读取复选框数据

* Maths Flag：开启
* Physics Flag：空
* Chemistry Flag：开启

## 所有表单参数

以下使用 `getParameterNames()` 方法来确定可用参数的通用示例。一旦我们有了 `Enumeration`，就可以使用 `hasMoreElements()` 方法进行循环。

```jsp
<%@ page import="java.io.*;java.util.*;" %>
<html>
<head>
<title>表单参数</title>
</head>
<body>
<center>
<h1>表单参数</h1>
<table width="100%" border="1" align="center">
<tr><th>参数名称</th><th>参数值(s)</th></tr>
<%
  Enumeration paramNames = request.getParameterNames();
  while(paramNames.hasMoreElements()) {
    String paramName = (String)paramNames.nextElement();
    String paramValue = request.getParameter(paramName);
    out.print("<tr><td>" + paramName + "</td><td>" + paramValue + "</td></tr>");
  }
%>
</table>
</center>
</body>
</html>
```

你可以尝试上面的 JSP 来读取表单数据。

# 第 16 章：过滤器

在本章中，我们将讨论 JSP 中的过滤器（Filters）。Servlet 和 JSP 过滤器是用于以下目的的 Java 类：

1. 在客户端访问资源之前拦截请求。
2. 在服务器发送回客户端之前处理请求。

规范建议了各种类型的过滤器：

1. 身份验证过滤器
2. 数据压缩过滤器
3. 加密过滤器
4. 触发资源访问过滤器
5. 图像转换过滤器
6. 日志和审计过滤器
7. MIME-TYPE 链过滤器
8. 分词过滤器
9. XML 过滤器

过滤器部署在部署文件 `web.xml` 中，然后映射到 servlet 或 JSP 名称或 URL 模式。部署文件 `web.xml` 位于 `<Tomcat-installation-directory>\conf` 目录。

当 JSP 容器启动你的应用程序时，它会为你在部署文件中声明的每个过滤器创建一个实例。过滤器按照声明的顺序执行。

## Servlet Filter 方法

过滤器只是实现 `javax.servlet.Filter` 接口的 Java 类。`javax.servlet.Filter` 接口定义了三个方法：

### 方法与描述

| 方法 | 描述 |
|---|---|
| `public void doFilter(ServletRequest, ServletResponse, FilterChain)` | 每当由于客户端对链终端资源的请求而通过链传递请求/响应对时，容器都会调用此方法。 |
| `public void init(FilterConfig filterConfig)` | Web 容器调用此方法以指示过滤器已进入服务。 |
| `public void destroy()` | Web 容器调用此方法以指示过滤器已退出服务。 |

## JSP 过滤器示例

下面的示例显示了每次访问任何 JSP 文件时，如何打印客户端的 IP 地址和当前日期时间。这个示例将让你对 JSP 过滤器有一个基本的了解，但你可以使用该概念编写更复杂的过滤器应用程序。

```java
// Import required java libraries
import java.io.*;
import javax.servlet.*;
import java.util.*;
```



```java
// Implements Filter class
public class LogFilter implements Filter {
    public void init(FilterConfig config) throws Exception {
        // Get init parameter
        String testParam = config.getParameter("test-param");
        System.out.println("Test Param: " + testParam);
    }
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain)
        throws IOException, SQLException {
        // Get the IP address of the client machine
        String ipAddress = request.getRemoteAddr();

        // Log the IP address and current timestamp.
        System.out.println("IP " + ipAddress + ", Time " + new Date().toString());

        // Pass request back down the filter chain
        chain.doFilter(request, response);
    }
    public void destroy() {
        /* Called before the Filter instance is removed
           from service the web container*/
    }
}
```

以通常方式编译 `LogFilter.java`，并将你的 `LogFilter.class` 文件放入 `<Tomcat-installation-directory>/webapps/ROOT/WEB-INF/classes` 中。

## Web.xml 中的 JSP Filter Mapping

过滤器的定义并映射到 URL 或 JSP 文件名的方式，与 Servlet 定义并映射到 web.xml 中 URL 模式的方式相同。在部署描述符 web.xml 中创建 filter 标签条目。

```xml
<filter>
  <filter-name>LogFilter</filter-name>
  <filter-class>LogFilter</filter-class>
  <init-param>
    <param-name>test-param</param-name>
    <param-value>Initialization Parameter</param-value>
  </init-param>
</filter>

<filter-mapping>
  <filter-name>LogFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

上面的过滤器将应用于所有 servlet 和 JSP，因为我们在配置中指定了 `/*`。如果你只想对少数 servlet 或 JSP 应用过滤器，可以指定特定的 servlet 或 JSP 路径。

现在调用任何 servlet 或 JSP，你将在你的 Web 服务器日志中看到生成的日志。你可以使用 Log4j logger 将日志记录到单独的文件。

## 使用多个过滤器

你的 Web 可能会定义多个具有特定目的的各种过滤器。假设你定义了两个过滤器 `AuthenFilter` 和 `LogFilter`。其余过程将如上文所示，但你需要按照下文所示创建一个不同的映射 -

```xml
<filter>
  <filter-name>LogFilter</filter-name>
  <filter-class>LogFilter</filter-class>
  <init-param>
    <param-name>test-param</param-name>
    <param-value>Initialization Parameter</param-value>
  </init-param>
</filter>

<filter>
  <filter-name>AuthenFilter</filter-name>
  <filter-class>Auth Filter</filter-class>
  <init-param>
    <param-name>test-param</param-name>
    <param-value>Initialization Parameter</param-value>
  </init-param>
</filter>

<filter-mapping>
  <filter-name>LogFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>

<filter-mapping>
  <filter-name>AuthenFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

## 过滤器应用顺序

web.xml 中 `filter-mapping` 元素的顺序决定了 Web 容器包含过滤器到 servlet 或 JSP 的顺序。要反转过滤器顺序，你只需要反转 web.xml 文件中的 `filter-mapping` 元素。

例如，上面的示例将应用 `LogFilter`，然后应用 `AuthenFilter` 到任何 servlet 或 JSP；下面的示例将反转顺序：

```xml
<filter-mapping>
  <filter-name>AuthenFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>

<filter-mapping>
  <filter-name>LogFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

## 第17 章：Cookies 处理

在本章中我们将 JSP 中的 Cookies 处理。Cookies 是存储在客户端的文本文件，用于各种目的。使用 servlet 技术识别和返回用户涉及三个步骤：

- 服务器脚本将一组 cookies 设置到浏览器。例如名称、年龄或识别码等。
- 浏览器存储这些信息以供将来使用。
- 当浏览器下次向 Web 服务器发送任何请求时，会将这些 cookies 发送到服务器。

本章将教你如何使用 JSP 设置、访问和删除 cookies。

## Cookie 的结构

Cookies 通常设置在 HTTP 头部中（尽管 JavaScript 也可以设置 cookie）。设置 cookie 的 JSP可能会可能会如下头部：

```http
HTTP/1.1 200 OK
Date: Fri, 04 Feb 2000 21:03:38 GMT
Server: Apache/1.3 (UNIX)
Set-Cookie: name=xyz; expires=Fri, 04 Nov-2000 22:03:38 GMT; path=/; domain=tutorials.com
```

`Set-Cookie` 头部包含键值对、过期日期和路径。浏览器将保留这些信息直到过期日期。如果用户指向匹配路径和域的任何页面，会将 cookie 重送到服务器。浏览器的头部可能如下 –

```http
GET / HTTP/1.0
Connection: Keep-Alive
User-Agent: Mozilla/4.0 (compatible; Win98; NT)
Host: demo.com:1126
Accept: image/gif,*
Accept-Encoding: gzip
Accept-Language: en
Accept-Charset: iso-8859-1,utf-8
Cookie: name=xyz
```

随后 JSP 脚本将通过 `request.getCookies()` 获取 cookies。

## Servlet Cookies 方法

下表列出了在 JSP 中操作 cookie 时关联对象的有用方法：

| 序号 | 方法与描述 |
| :--- | :--- |
| 1 | `public void setDomain(String pattern)`: 该方法设置 cookie 应用域；例如 tutorialpoint.com。 |
| 2 | `public String getDomain()`: 该方法获取 cookie 应用域；例如 tutorialpoint.com。 |
| 3 | `public void setMaxAge(int expiry)`: 该方法设置 cookie 过期前应经过多少时间（秒）。如果不设置，cookie 将仅对当前会话有效。 |
| 4 | `public int getMaxAge()`: 该方法返回以秒为单位的 cookie 最大年龄。默认情况下，-1 表示 cookie 持到浏览器关闭。 |
| 5 | `public String getName()`: 该方法返回 cookie 的名称。创建后无法更改。 |
| 6 | `public void setValue(String newValue)`: 该方法设置与 cookie 关联的值。 |
| 7 | `public String getValue()`: 该方法获取与 cookie 关联的值。 |
| 8 | `public void setPath(String uri)`: 该方法设置 cookie 应用路径。如果不指定路径，cookie 将适用于当前页面及其子目录的所有 URL。 |
| 9 | `public String getPath()`: 该方法获取 cookie 应用路径。 |
| 10 | `public void setSecure(boolean flag)`: 该方法设置布尔值，指示 cookie 是否仅通过加密连接（即 SSL）发送。 |
| 11 | `public void setComment(String purpose)`: 该方法指定描述 cookie 目的的注释。如果浏览器向用户展示 cookie，则该注释很有用。 |
| 12 | `public String getComment()`: 该方法返回描述 cookie 目的的注释，如果 cookie 没有注释则返回 null。 |

## 在 JSP 中设置 Cookies

在 JSP 中设置 cookies 三个步骤：

### 步骤 1：创建 Cookie 对象

你调用 `Cookie` 构造函数并传入 cookie 名称和 cookie 值，两者都是字符串。

```java
Cookie cookie = new Cookie("key", "value");
```

请记住，名称或值都不应包含空格或以下任何字符：

`[]() = "" / ? @ : ;`

### 步骤 2：设置最大年龄

你使用 `setMaxAge` 指定 cookie 有效时长（秒）。以下代码将设置一个 24 小时的 cookie。

```java
cookie.setMaxAge(60*24);
```

### 步骤 3：将 Cookie 发送到 HTTP 响应头部

你使用 `response.addCookie` 在 HTTP 响应头部中添加 cookie，如下：

```java
response.addCookie(cookie);
```

### 示例

让我们将上述代码放入 `main.jsp` 文件中，并在接下来的 HTML 页面中使用它——

```html
<html>
<body>
<form action="main.jsp" method="GET">
First Name: <input type="text" name="first_name">
<br />
Last Name: <input type="text" name="last_name" />
<input type="submit" value="Submit" />
</form>
</body>
</html>
```

将上述 HTML 内容保存在一个名为 `hello.jsp` 的文件中，并将 `hello.jsp` 和 `main.jsp` 放在 `Tomcat-installation-directory/webapp/ROOT` 目录下。当你访问 `http://localhost:8080/hello.jsp` 时，这里是表单的实际输出。

First Name:

Last Name:

尝试在屏幕上输入 First Name 和 Last Name，这会设置两个 Cookie：`firstName` 和 `lastName`。当你下次点击 Submit 按钮时，这些 Cookie 将被传回服务器。

在下一节中，我们将解释你如何在你的 Web 应用程序中访问这些 Cookie。

## 使用 JSP 读取 Cookies

要读取 Cookie，你需要通过调用 `HttpServletRequest` 的 `getCookies()` 方法来创建一个 `javax.servlet.Cookie` 对象的数组。循环遍历该数组，并使用 `getName()` 和 `getValue()` 方法来访问每个 Cookie 及其关联的值。

### 示例

现在让我们来读取上一个示例中设置的 Cookie ——

```html
<html>
<head>
<title>Reading Cookies</title>
</head>
<body>
```

```jsp
<%
Cookie cookie = null;
Cookie[] cookies = null;

// 获取与此域关联的 Cookies 数组
cookies = request.getCookies();

if (cookies == null) {
    out.println("<h2>Found Cookies Name and Value</h2>");
} else {
    for (int i = 0; i < cookies.length; i++) {
        cookie = cookies[i];
        out.print("Name: " + cookie.getName() + ", ");
        out.print("Value: " + cookie.getValue() + " <br>");
    }
}
// 等等，OCR 在此处有逻辑错误
%>
```

```html
</body>
</html>
```

让我们将上述代码放入 `main.jsp` 文件并访问它。如果你将 `first_name cookie` 设置为 "John"，并将 `last_name cookie` 设置为 "Player"，那么运行 `http://localhost:8080/main.jsp` 将显示以下结果 ——

Found Cookies Name and Value

Name : first_name, Value: John

Name : last_name, Value: Player

## 使用 JSP 删除 Cookies

删除 Cookie 非常简单。如果你想删除一个 Cookie，只需要按照以下步骤操作 ——

1. 读取一个已存在的 Cookie 并将其存储在 Cookie 对象中。
2. 使用 `setMaxAge()` 方法将 cookie 期设置为零以删除已存在的 Cookie。
3. 将此 cookie 添加回响应头。

### 示例

接下来的示例将向你展示如何删除名为 `first_name` 的现有 Cookie，当你下次运行 `main.jsp` 时，它将为 `first_name` 返回 null 值。

```html
<html>
<head>
<title>Reading Cookies</title>
</head>
```



```html
<body>
<center>
<h1>Reading Cookies</h1>
</center>
<%
Cookie cookie = null;
Cookie[] cookies = null;

// 获取与此域关联的 Cookies 数组
cookies = request.getCookies();

if (cookies != null) {
  out.println("<h2> Found Cookies Name and Value</h2>");

  for (int i = 0; i < cookies.length; i++) {
    cookie = cookies[i];

    if(cookie.getName().compareTo("first_name") == 0) {
      cookie.setMaxAge(0);
      response.addCookie(cookie);
      out.print("Name: " + cookie.getName() + " ");
      out.println("Value: " + cookie.getValue() + "<br/>");
    }
  }
} else {
  out.println();
  out.println("<h2>No cookies found</h2>");
}
%>
</body>
</html>
```

让我们将上述代码放入 `main.jsp` 文件并尝试访问它。它将显示如下：

# Cookies Name and Value

Deleted cookie : first_name

Name : first_name, Value: John

Name : last_name, Value: Player

现在再次运行 `http://localhost:8080/main.jsp`，它应该只显示一个 Cookie 如下 ——

# Found Cookies Name and Value

Name : last_name, Value: Player

你可以在 Internet 中手动删除你的 Cookie。从工具菜单开始并选择 Internet。

# 第18 章：会话跟踪

在本章中，我们将讨论会话跟踪。HTTP 是一个无状态协议，JSP 默认为每个客户端创建一个新的 `HttpSession` 对象。禁用会话跟踪需要通过设置页面指令属性为 false，如下：

```jsp
<%@page session="false"%>
```

JSP 引擎通过隐式 `session` 对象将 `HttpSession` 暴露出来。由于 `session` 对象已经提供给 JSP 程序员，可以立即开始从对象中存储和检索数据。

这里是 `session` 对象提供的常用方法总结：

| 序号 | 方法 & 描述 |
|---|---|
| 1 | `public Object getAttribute(String name)` | 返回会话中绑定到指定名称的对象，如果没有绑定该名称则返回 null。 |
| 2 | `public Enumeration getAttributeNames()` | 返回包含绑定到此会话的所有名称的枚举。 |
| 3 | `public long getCreationTime()` | 返回会话创建的时间，自 1970 年 1 月 1 日起的毫秒数。 |
| 4 | `public String getId()` | 返回分配给此会话的唯一标识符字符串。 |
| 5 | `public long getLastAccessedTime()` | 返回上次与此会话相关的请求时间，自 1970 年 1 月 1 日起的毫秒数。 |
| 6 | `public int getInactiveInterval()` | 返回客户端访问之间保持此会话开启的最大间隔（秒）。 |
| 7 | `public void invalidate()` | 使会话失效并解除绑定到它的所有对象。 |
| 8 | `public boolean isNew()` | 如果客户端尚不知道会话，或者客户端选择加入会话，则返回 true。 |
| 9 | `public void removeAttribute(String name)` | 从此会话中移除绑定到指定名称的对象。 |
| 10 | `public void setAttribute(String name, Object value)` | 将值绑定到指定名称的会话中。 |

# Cookies

服务器可以为每个客户端分配 Cookie。这种方法可以在客户端发送请求时保持会话。

# 隐藏表单字段

服务器可以发送 session ID，如下：

```html
<input type="hidden" name="session">
```

# URL 重写

你可以在 URL 末尾添加 session id，例如：`http://tutorialsp.com/file?sessionid=12345`

# 会话对象

服务器可以使用 Cookie 来标识会话。这种方法在客户端不支持 Cookie 时可以使用：

- 1. 页面请求
- 2. 访问网站
- 3. 存储信息

# 在客户端与服务器之间会话

你可以在 Internet 中手动删除你的 Cookie。

此方法使用指定的名称将对象绑定到此会话。

`public void setMaxInactiveInterval(int interval)`

此方法指定了客户端请求之间在 servlet 容器失效此会话之前的时间间隔（单位为秒）。

## 会话跟踪示例

此示例描述了如何使用 `HttpSession` 对象来查找会话的创建时间和最后访问时间。如果不存在会话，我们将为请求关联一个新的会话。

```jsp
<%@page import "java.io.*,java.util.*" %>
```

```java
// 获取会话创建时间。
Date createdAt = new Date(session.getCreationTime());
// 获取此网页的最后访问时间。
Date lastAccessTime = new Date(session.getLastAccessedTime());
```

```java
String title = "Welcome to my website";
Integer visitCount = new Integer(0);
String visitCountKey = new String("visitCount");
String userIDKey = new String("userID");
String userID = new String("ABCD");
```

```java
// 检查这是否是网页的新访客。
if (session.isNew()) {
    title = "Welcome to my website";
    session.setAttribute(userIDKey, userID);
    session.setAttribute(visitCountKey, visitCount);
}
visitCount = (Integer)session.getAttribute(visitCountKey);
visitCount = visitCount + 1;
userID = (String)session.getAttribute(userIDKey);
session.setAttribute(visitCountKey, visitCount);
```

```html
<html>
<head>
<title>Session Tracking</title>
</head>
```

```html
<body>
<center>
<h1>Session Tracking</h1>
</center>
```

```html
<table border="1" align="center">
<tr bgcolor="#949494">
<th>Session info</th>
<th>Value</th>
</tr>
<tr>
<td>id</td>
```

```html
<td><% out.print(session.getId()); %> </td>
</tr>
<tr>
<td>Creation Time</td>
<td><% out.print(createdAt); %> </td>
</tr>
<tr>
<td>Time of Last Access</td>
<td><% out.print(lastAccessTime); %> </td>
</tr>
<tr>
<td>User ID</td>
<td><% out.print(userID); %> </td>
</tr>
<tr>
<td>Number of visits</td>
<td><% out.print(visitCount); %> </td>
</tr>
</table>
</body>
</html>
```

现在将上述代码放在 `main.jsp` 中并尝试访问 `http://localhost:8080/main.jsp`。一旦运行该 URL，你将收到以下结果 =

# 欢迎来到我的网站

# 会话信息

| info type | value |
| :--- | :--- |
| id | 0AE3EC93FF44E3C5255B4351B77ABB2D5 |
| Creation Time | Tue Jun 08 17:26:40 GMT+04:00 2010 |
| Time of Last Access | Tue Jun 08 17:26:40 GMT+04:00 2010 |
| User ID | ABCD |
| Number of visits | 0 |

现在尝试第二次运行同一个 JSP，你将收到以下结果。

# 欢迎回到我的网站

# 会话信息

| info type | value |
| :--- | :--- |
| id | 0AE3EC93FF44E3C5255B4351B77ABB2D5 |
| Creation Time | Tue Jun 08 17:26:40 GMT+04:00 2010 |
| Time of Last Access | Tue Jun 08 17:26:40 GMT+04:00 2010 |
| User ID | ABCD |
| Number of visits | 1 |

## 删除会话数据

当你完成用户会话数据的处理时，你有几种选择：

- 1. **移除特定属性** — 你可以调用 `public void removeAttribute(String name)` 方法来删除与特定键关联的值。
- 2. **删除整个会话** — 你可以调用 `public void invalidate()` 方法来丢弃整个会话。
- 3. **设置会话超时** — 你可以调用 `public void setMaxInactiveInterval(int interval)` 方法单独为会话设置超时时间。
- 4. **注销用户** — 对于支持 2.4 的服务器，你可以调用 `logout` 来让客户端登出 Web 服务器并失效属于该用户的所有会话。
- 5. **web.xml 配置** — 如果你使用 Tomcat，除了上述方法外，你还可以如下所示在 `web.xml` 文件中配置会话超时。

```xml
<session-config>
  <session-timeout>15</session-timeout>
</session-config>
```

超时时间以分钟表示，Tomcat 中的默认超时时间为 30 分钟。

`getMaxInactiveInterval()` 方法返回该会话以秒为单位的超时时间。如果你的会话在 `web.xml` 中配置为 15 分钟，`getMaxInactiveInterval()` 将返回 900。

## 第19 章：上传

在本章中，我们将讨论如何上传文件。

## 创建表单

现在让我们如何创建

- 1. 表单应设置为 **POST**。
- 2. 表单 enctype 应设置为 **multipart/form-data**。
- 3. 输入框类型应为 **file**。
- 4. 输入框应具有 `name` 属性。
- 5. 输入框应具有 `size` 属性。
- 6. 文件将被上传到服务器。

```html
<html>
<head>
<title>File Upload</title>
</head>
<body>
  <h3>File Upload</h3>
  <form action="Upload" method="post" enctype="multipart/form-data">
    <input type="file" name="file" size="50" />
    <br>
    <input type="submit" value="Upload" />
  </form>
</body>
</html>
```

这将显示结果。

## 后端写入

让我们考虑

- 1. 文件应设置为。
- 2. 使用以下代码。

## 选择文件上传

- 1. 文件应设置为。
- 2. 使用以下代码。

```xml
<web-app>
  <context-param>
    <description>存储文件的位置</description>
    <param-name>file-upload</param-name>
    <param-value>c:\tomcat-5.2.9\webapp\data</param-value>
  </context-param>
</web-app>
```

以下是用于

- 1. 文件应设置为。
- 2. 使用以下代码。

```jsp
<%@page import "java.io.*,java.servlet.*" %>
<%@ page import = "javax.servlet.http.*" %>
<%@ page import = "org.apache.commons.fileupload.*" %>
<%@ page import = "org.apache.commons.fileupload.disk.*" %>
<%@ page import = "org.apache.commons.fileupload.servlet.*" %>
<%@ page import = "org.apache.commons.fileupload.output.*" %>
```

```java
<%
File file;
int maxSize = 5000 * 1024;
int maxMemSize = 5000 * 1024;
ServletContext context = pageContext.getServletContext();
String filePath = context.getInitParameter("file-upload");

// 验证内容类型
String contentType = request.getContentType();

if ((contentType.indexOf("multipart/form-data") >= 0)) {
    DiskFileItemFactory factory = new DiskFileItemFactory();
    // 内存中存储的最大大小
    factory.setSizeThreshold(maxMemSize);

    // 大于 maxSize 的数据保存位置
    factory.setRepository(new File("c:\\temp"));

    // 创建一个新的文件上传处理器
    ServletFileUpload upload = new ServletFileUpload(factory);

    // 要更新的最大文件大小。
    upload.setMaxSize(maxSize);

    try {
        // 解析请求以获取文件项。
        List fileitems = upload.parseRequest(request);

        // 处理上传的文件项
        Iterator i = fileitems.iterator();

        out.println("<html>");
        out.println("<head>");
        out.println("<title>File Upload</title>");
        out.println("</head>");
        out.println("<body>");
```

```java
while (i.hasNext()) {
    FileItem fi = (FileItem)i.next();
    if (!fi.isFormField()) {
        // 获取上传的文件参数
        String fileName = fi.getFileName();
        String filename = fi.getName();
        boolean isInMemory = fi.isInMemory();
        long sizeBytes = fi.getSize();
        // 写入文件
        if (fileName.indexOf("\\") >= 0) {
            file = new File(filePath + fileName.substring(fileName.lastIndexOf("\\")));
        } else {
            file = new File(filePath + fileName.substring(fileName.lastIndexOf("\\") + 1));
        }
        fi.write(file);
        out.println("文件名: " + fileName + "<br>");
    }
}
out.println("</body>");
out.println("</html>");
```

```java
} catch (Exception ex) {
    System.out.println(ex);
}
} else {

    out.println("<html>");

    out.println("<head>");

    out.println("<title>Servlet 上传</title>");

    out.println("</head>");

    out.println("<body>");

    out.println("<p>没有上传文件</p>");

    out.println("</body>");

    out.println("</html>");

}

}
%>
```



现在尝试使用你上面创建的 HTML 表单上传文件。当你访问 `http://localhost:8080/UploadFile.htm` 时，它将显示以下结果。这将帮助你从本地机器上传任何文件。

文件上传 -

请选择一个文件进行上传 -

如果你的 JSP 脚本工作正常，你的文件应该上传到 `c:\apache-tomcat-5.5.29\webapps\data\` 目录。

# 第 20 章：处理日期

在本章中，我们将讨论如何在 JSP 中处理数据。使用 JSP 的最重要优势之一是你可以使用核心 Java 中提供的所有方法。我们将带你介绍 `java.util` 包中提供的 `Date` 类；该类封装了当前的日期和时间。

`Date` 类支持两个构造函数。第一个构造函数用当前日期和时间初始化对象。

```
Date()
```

以下构造函数接受一个参数，等于于自 1970 年 1 月 1 日午夜以来经过的毫秒数。

```
Date(long millisec)
```

一旦你有了一个 `Date` 对象，你就可以调用任何以下支持方法来处理日期 ——

## 方法与描述

| 序号 | 方法与描述 |
| :--- | :--- |
| 1 | `boolean after(Date date)` 如果调用的 `Date` 对象包含的日期比 `date` 指定的日期晚，则返回 `true`，否则返回 `false`。 |
| 2 | `boolean before(Date date)` 如果调用的 `Date` 对象包含的日期比 `date` 指定的日期早，则返回 `true`，否则返回 `false`。 |
| 3 | `Object clone()` 复制调用的 `Date` 对象。 |
| 4 | `int compareTo(Date date)` 比较调用的对象的值与 `date` 的值。如果值相等，返回 `0`。如果调用的对象比 `date` 早，返回负值。如果调用的对象比 `date` 晚，返回正值。 |
| 5 | `int compareTo(Object obj)` 如果 `obj` 是 `Date` 类，则操作方式与 `compareTo(Date)` 相同。否则，它抛出 `ClassCastException`。 |
| 6 | `boolean equals(Object date)` 如果调用的 `Date` 对象包含与 `date` 指定的日期和时间，则返回 `true`，否则返回 `false`。 |
| 7 | `long getTime()` 返回自 1970 年 1 月 1 日午夜以来经过的毫秒数。 |
| 8 | `int hashCode()` 返回调用的对象的哈希码。 |
| 9 | `void setTime(long time)` 设置 `time` 指定的时间和日期，该时间表示自 1970 年 1 月 1 日午夜以来经过的毫秒数。 |
| 10 | `String toString()` 将调用的 `Date` 对象转换为字符串并返回结果。 |

## 获取当前日期和时间

在 JSP 程序中，获取当前日期和时间非常简单。你可以使用带有 `toString()` 方法的 `Simple` 对象如下所示打印当前日期和时间 -

```jsp
<% page import = "java.io.*,java.util.*,javax.servlet.*" %>

<html>

<head>

<title>显示当前日期和时间</title>

</head>

<body>

<center>

<h1>显示当前日期和时间</h1>

</center>

<%

    Date date = new Date();

    out.print("<h2 align=\"center\">"+date.toString()+"</h2>");

%>

</body>

</html>
```

现在让我们将代码保存在 `CurrentDate.jsp` 中，然后使用 URL `http://localhost:8080/CurrentDate.jsp` 调用此 JSP。你将收到以下内容

## 第 21 章：显示当前日期和时间

Mon Jun 21 21:46:49 GMT+04:00

使用 URL `http://localhost:8080/CurrentDate.jsp` 刷新页面。你会发现每次刷新时秒数都会有所不同。

## 日期比较

如前面的章节所述，你可以在 JSP 脚本中使用所有的 Java 方法。在需要比较两个日期的情况下，请考虑以下几点：

1. 你可以使用 `getTime()` 方法获取两个对象对象自 1970 年 1 月 1 日午夜以来经过的毫秒数，然后比较这些值。
2. 你可以使用 `before()`、`after()` 和 `equals()` 方法，因为例如 `new Date(date)` 会返回 true。
3. 你可以使用 `compareTo()` 方法；该方法由 `Comparable` 接口定义并由 `Date` 实现。

## 使用 SimpleDateFormat 进行日期格式化

`SimpleDateFormat` 是一个用于以语言区域敏感的方式格式化和解析日期的具体类。`SimpleDateFormat` 允许你从选择任何用户定义的日期时间格式模式开始。让我们按照如下方式修改上面的示例

```jsp
<%@ page import = "java.io.*,java.util.*,javax.servlet.*" %>

<html>

<head>

<title>显示当前日期和时间</title>

</head>

<body>

<center>

<h1>显示当前日期和时间</h1>

</center>

<%

    Date date = new Date();

    SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy.MM.dd HH:mm:ss z");

    out.print("<h2 align=\"center\">"+dateFormat.format(date)+"</h2>");

%>

</body>

</html>
```

将上面的代码保存在 `CurrentDate.jsp` 中，然后使用 URL `http://localhost:8080/CurrentDate.jsp` 调用此 JSP。你将得到以下结果 -

Mon Jun 21 21:46:49 GMT+04:00

使用 `SimpleDateFormat` 格式化日期。`SimpleDateFormat` 允许你从选择任何用户定义的日期时间格式模式开始。

## 格式代码

要指定时间，使用以下模式字符串：

| 字符 | 描述 | 示例 |
| :--- | :--- | :--- |
| G | 纪元 | AD |
| y | 年 | 2001 |
| M | 月 | 07 |
| d | 日 | 21 |
| h | 小时 (12小时制) | 10 |
| H | 小时 (24小时制) | 23 |
| m | 分钟 | 06 |
| s | 秒 | 44 |
| S | 毫秒 | 234 |
| E | 星期 | Tuesday |
| F | 周数 | 360 |
| w | 周几 | July |
| a | 上午下午 | PM |
| k | 小时 (0-23小时) | 24 |
| K | 小时 (0-11小时) | 0 |
| z | 时区 | Eastern Standard Time |
| ' | 转义符 |  |

# 第 22 章：页面跳转

跳转

在本章中，我们将讨论 JSP 中的页面跳转。页面跳转通常用于当文档移动到新位置且我们需要将客户端发送到新位置时。这可能是由于负载均衡或简单的随机化。

请求另一个页面的简单方法是使用响应对象的 `sendRedirect()` 方法。以下是方法的签名：

```java
public void sendRedirect(String location) throws IOException
```

该方法带有状态码和新页面位置将响应发回浏览器。你也可以结合 `setStatus()` 和 `setHeader()` 方法来实现相同的跳转：

```java
String site = "http://www.newpage.com";

response.setStatus(response.SC_MOVED_TEMPORARILY);

response.setHeader("Location", site);
```

## 示例

此示例了 JSP 如何跳转到另一个位置 —

```jsp
<%@ page import = "java.io.*,java.util.*" %>

<html>

<head>

<title>页面跳转</title>

</head>

<body>

<center>

<h1>页面跳转</h1>

</center>

<%

// 要跳转的新位置

String site = new String("http://www.photofuntools.com");

response.setStatus(response.SC_MOVED_TEMPORARILY);

response.setHeader("Location", site);

%>

</body>

</html>
```

现在让我们将上面的代码保存在 `PageRedirection.jsp` 中，并使用 URL `http://localhost:8080/PageRedirection.jsp` 调用此 JSP。这将带你进入指定的 `http://www.photofuntools.com`。

# 第 23 章：访问计数器

访问计数器

在本章中，我们将讨论 JSP 中的访问计数器。访问计数器可以告诉你网站上特定页面的访问次数。通常你第一次进入首页时，会在 `index.jsp` 页面上挂载访问计数器。

## 示例

此示例展示了如何使用 JSP 统计特定页面的总访问次数。如果你想统计整个网站的总访问次数，则需要在所有的 JSP 页面中包含相同的代码。

```jsp
<%@ page import="java.io.*,java.util.*" %>

<html>

<head>

<title>JSP 中的 application 对象</title>

</head>

<body>

<%

Integer hitsCount = (Integer)application.getAttribute("hitCounter");

if(hitsCount==null || hitsCount == 0) {

/* 第一次访问 */

out.println("Welcome to my website!");

hitsCount = 1;

} else {

/* 再次访问 */

out.println("Welcome back to my website!");

hitsCount += 1;

}

application.setAttribute("hitCounter", hitsCount);

%>

<p>Total number of visits: <%= hitsCount%></p>

</body>

</html>
```

让我们将上述代码放入 `main.jsp` 中，并使用 URL `http://localhost:8080/main.jsp` 调用此 JSP。这将显示访问计数值，该值会随着你刷新页面而增加。你可以尝试使用不同的浏览器访问页面，你会发现访问计数器会随着每次访问不断增加，你将收到如下结果——

Welcome to my website!

Total number of hits: 12

## 访问计数器重置

当你重启应用程序（即 Web 服务器）时，这将重置你的应用程序变量，计数器将重置为零。为了避免这种损失，请考虑以下几点：

- 定义一个带有计数字段数据库表，假设名为 `hitcount`。为其赋值为 0。
- 每次访问时，读取表获取 `hitcount` 的值。
- 将 `hitcount` 的值加1并用新值更新表。
- 显示 `hitcount` 的新值为总页面访问次数。
- 如果你想统计所有页面的访问次数，请对所有页面实现上述逻辑。

# 第 25 章：自动刷新

在本章中，我们将讨论 JSP 中的自动刷新。考虑一个显示实时游戏得分、股票市场状况或货币汇率的网页。对于所有此类页面，你需要定期使用浏览器的刷新或重新加载按钮刷新你的 Web 页面。

JSP 通过提供一种机制使这项工作变得简单，你可以构建网页，使其在给定的间隔后自动刷新。

刷新 Web页面最简单的方法是使用响应对象的 `setHeader()` 方法。以下是该方法的签名：

此方法向浏览器发送 "Refresh" 头部，并带有一个整数值，表示以秒为单位的时间间隔。

## 页面自动刷新示例

在接下来的示例中，我们将使用 `setHeader()` 方法设置 `Refresh` 头部。这将有助于模拟数字时钟——

```jsp
<%@ page import "java.io.*,java.util.*" %>

<html>

<head>

<title>Auto Refresh Header Example</title>

</head>

<body>

<center>

<h2>Auto Refresh Header Example</h2>

<%

// 设置刷新自动加载时间为5秒

response.setHeader("Refresh", 5);

// 获取当前时间

Calendar calendar = new GregorianCalendar();

String am_pm;

int hour = calendar.get(Calendar.HOUR);

int minute = calendar.get(Calendar.MINUTE);

int second = calendar.get(Calendar.SECOND);

if(calendar.get(Calendar.AM_PM) == 0)

    am_pm = "AM";

else

    am_pm = "PM";

String CT = hour+":"+minute+":"+second+": " + am_pm;

out.print("Current Time: " + CT + "\n");

%>

</center>

</body>

</html>
```

现在将上述代码放入 `main.jsp` 并尝试访问它。它将每隔5秒显示一次当前系统时间，如下。只需运行 JSP 并等待结果即可——

## 自动刷新头部示例

Current Time is: 9:44:50

# 第 26 章：发送电子邮件

在本章中，我们将讨论如何使用 JSP 发送电子邮件。要使用 JSP 发送电子邮件，你需要在你的机器上安装 Java API 和 Java 激活框架 (JAF)。

- 1. 你可以从 Java 标准网站下载最新版本的 JavaBeans（版本 1.2）。
- 2. 你可以从 Java 标准网站下载最新版本的 JavaBeans Activation Framework JAF（版本 1.0.2）。

下载并解压这些文件到新创建的顶层目录中。你会发现这两个应用程序都有多个 jar 文件。你需要在 CLSPATH 中添加 `mail.jar` 和 `activation.jar` 文件。

## 发送简单电子邮件

这是一个从你的机器发送简单电子邮件的示例。假设你的本地已连接到互联网并能够发送电子邮件。确保 Java Email API 包和 JAF 包中的所有文件都已在 CL 中可用。

```jsp
<%@ page import="java.io.*,java.util.*,javax.mail.*" %>

<%@ page import="javax.mail.internet.*,javax.activation.*" %>

<%@ page import="javax.servlet.http.*,javax.servlet.*" %>

<%

String result;

// 需要指定收件人邮箱 ID

String to = "abcd@gmail.com";

// 需要指定发件人邮箱 ID

String from = "mohd@gmail.com";

// 假设你从本地发送电子邮件

String host = "localhost";

// 获取系统属性

Properties properties = System.getProperties();

// 设置邮件服务器

properties.setProperty("mail.smtp.host", host);

// 获取默认 Session 对象。

Session mailSession = Session.getInstance(properties);

try {

// 创建默认的 MimeMessage 对象。

MimeMessage message = new MimeMessage(mailSession);

// 设置头部的 From: 字段。

message.setFrom(new InternetAddress(from));

// 设置 To: 字段。

message.addRecipient(Message.RecipientType.TO, new InternetAddress(to));

// 设置 Subject: 头部

message.setSubject("This is the Subject!");

// 现在设置实际消息

message.setText("This is actual message");

// 发送消息

transport.send(message);

result = "Sent message successfully...";

} catch (MessagingException mex) {

  result = "Error: unable to send";

  mex.printStackTrace();

}

%>

<html>

<head>
```



# 第27 章：使用 JSP 发送电子邮件

使用 URL `http://localhost:8080/main.jsp` 调用此 JSP。这将帮助向 `abcd@gmail.com` 发送。结果：Sent message successfully...

如果你想向多个收件人发送邮件，使用以下方法指定收件人：

1.  `type` – 将是 `TO`、`CC` 或 `BCC`。这里 `CC` 代表抄送，`BCC` 代表密抄。
2.  `addresses` – 这是邮箱 ID 的数组。你需要使用 `InternetAddress()` 方法指定邮箱 ID。

```java
void addRecipients(Message.RecipientType type)
```

## 发送 HTML 电子邮件

这是一个从你的机器发送 HTML 电子邮件的示例。假设你的本地已连接到互联网并能够发送电子邮件。确保 Java Email API 包和 JAF 包中的所有文件都已在 classpath 中可用。此示例与上一个非常相似，只是这里我们使用了 `setContent()` 方法，其第二个参数为 `"text/html"` 以指定 HTML 内容。

使用此示例，你可以按需要发送 HTML 内容。

```jsp
<%@ page import="java.io.*,java.util.*,javax.mail.*" %>
<%@ page import="javax.mail.internet.*,javax.activation.*" %>
<%@ page import="javax.servlet.http.*,javax.servlet.*" %>
<%
String result;

// 需要指定收件人邮箱 ID
String to = "abcd@gmail.com";

// 需要指定发件人邮箱 ID
String from = "mohd@gmail.com";

// 假设你从本地发送电子邮件
String host = "localhost";

// 获取系统属性
Properties properties = System.getProperties();

// 设置邮件服务器
properties.setProperty("mail.smtp.host", host);

// 获取默认 Session 对象。
Session mailSession = Session.getInstance(properties);

try {
    // 创建默认的 MimeMessage 对象。
    MimeMessage message = new MimeMessage(mailSession);

    // 设置头部的 From: 字段。
    message.setFrom(new InternetAddress(from));

    // 设置 To: 字段。
    message.addRecipient(Message.RecipientType.TO, new InternetAddress(to));

    // 设置 Subject: 头部
    message.setSubject("This is the Subject!");

    // 现在设置实际消息
    message.setText("This is actual message", "text/html");

    // 发送消息
    transport.send(message);

    result = "Sent message successfully...";

} catch (MessagingException mex) {
    result = "Error: unable to send";
    mex.printStackTrace();
}
%>
<html>
<head>
<title>Send Email using JSP</title>
</head>
<body>
<center>
<h1>Send Email using JSP</h1>
</center>
</body>
</html>
```

```java
// 设置 To: header 的 header 字段。
message.addRecipient(Message.RecipientType.TO, new InternetAddress(to));
```

```java
// 设置 Subject: header 字段
message.setSubject("This is the Subject Line!");
```

```java
// 发送实际的 HTML 消息，大小任意
message.setContent("<h1>This is this actual message</h1>", "text/html");
```

```java
// 发送消息
Transport.send(message);
result = "Sent message successfully...";
} catch (MessagingException ex) {
    ex.printStackTrace();
    result = "Error: unable to send message...";
}
```

```html
<html>
<head>
<title>使用 JSP 发送 HTML 邮件</title>
</head>
<body>
<center>
<h1>使用 JSP 发送邮件</h1>
</center>
</body>
</html>
```

```html
<p align="center">
<%
    out.println("Result: " + result + "\n");
%>
</p>
```

让我们使用上面的 JSP 向给定的邮件 ID 发送 HTML 消息。

## 在邮件中发送附件

以下是一个从你的机器发送带附件邮件的示例——

```jsp
<% page import="java.io.*,java.util.*,javax.mail.*"%>
<% page import="javax.mail.internet.*,javax.activation.*"%>
<% page import="javax.servlet.http.*,javax.servlet.*" %>
```

```java
<%
String result;

// 需要指定收件者的邮件 ID。
String to = "abcd@gmail.com";

// 需要指定发件者的邮件 ID
String from = "mcmohd@gmail.com";

// 假设我们正在从本地发送邮件
String host = "localhost";

// 获取系统属性对象
Properties properties = System.getProperties();

// 设置邮件服务器
properties.setProperty("mail.smtp.host", host);

// 获取默认 Session 对象。
Session mailSession = Session.getDefaultInstance(properties);

try {
    // 创建一个 MimeMessage 对象。
    MimeMessage message = new MimeMessage(mailSession);

    // 设置 From: header 的 header 字段。
    message.setFrom(new InternetAddress(from));

    // 设置 To: header 的 header 字段。
    message.addRecipient(Message.RecipientType.TO, new InternetAddress(to));

    // 设置 Subject: header 字段
    message.setSubject("This is the Subject Line!");

    // 创建消息部分
    BodyPart messageBody = new MimeBodyPart();

    // 填充消息
    messageBody.setText("This is this message");

    // 创建一个多部分消息
    Multipart multipart = new MimeMultipart();

    // 设置文本消息部分
    multipart.addBodyPart(messageBody);

    // 第二部分是附件
    messageBody = new MimeBodyPart();

    String filename = "file.txt";

    DataSource source = new FileDataSource(filename);

    messageBody.setDataHandler(new DataHandler(source));

    messageBody.setFileName(filename);

    multipart.addBodyPart(messageBody);

    // 发送完整的消息部分
    message.setContent(multipart);

    // 发送消息
    Transport.send(message);

    String title = "Send Email";

    String result = "Sent message successfully...";

} catch (MessagingException mex) {
    mex.printStackTrace();
    result = "Error: unable to send message....";
}
%>
```

```html
<head>
<title>使用 JSP 发送附件邮件</title>
</head>
<body>
<center>
<h1>使用 JSP 发送附件邮件</h1>
</center>
<p align="center">
<% out.println("Result: " + result + "\n");%>
</p>
</body>
</html>
```

现在让我们运行上面的 JSP，向给定的邮件 ID 发送文件作为附件以及同条消息。

## 用户身份验证部分

如果需要为邮件服务器提供用户 ID 和密码进行身份验证，你可以按照如下方式设置这些属性：

```java
props.setProperty("mail.user", "myuser");
props.setProperty("mail.password", "mypawd");
```

其余的邮件发送机制保持如上文所示。

## 使用表单发送邮件

你可以使用 HTML 表单来接收邮件参数，然后可以使用 `request` 对象来获取所有信息，如下：

```java
String to = request.getParameter("to");
String from = request.getParameter("from");
String subject = request.getParameter("subject");
String messageText = request.getParameter("body");
```

一旦获取了所有信息，你就可以使用上述程序发送邮件。

# 第 28 章：标准标签库 (JSTL) 教程

在本章中，我们将理解 JSP 中不同的标签。Java 页面标签库 (JSTL) 是一组实用的 JSP 标签，它封装了许多 JSP 应用共同的核心功能。

JSTL 支持常见的结构化任务，如迭代和条件、用于处理 XML 文档、国际化标签以及 SQL 标签。它还提供了一个将现有自定义标签与 JSTL 标签集成框架。

## 安装 JSTL 库

要开始使用 JSP 标签，你首先需要安装 JSTL 库。如果你使用的是 Tomcat 容器，请按照以下步骤操作：

**步骤 1** – 下载 JSTL 分发。

**步骤 2** – 将 JAR 文件复制到你的目录。

要使用任何这些标签，你需要在顶部包含 `taglib` 指令。

## JSTL 标签分类

JSTL 标签可以根据其功能分类为：

1.  核心标签 (Core Tags)
2.  格式化标签 (Formatting tags)
3.  SQL 标签 (SQL tags)
4.  XML 标签 (XML tags)
5.  函数 (Functions)

## 核心标签

核心标签组是最常用的标签。以下是包含核心库的语法：

```jsp
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
```

下表列出了核心标签：

| 序号 | 标签 | 描述 |
|---|---|---|
| 1 | `<c:out>` | 用于表达式。 |
| 2 | `<c:set>` | 在作用域内设置结果。 |
| 3 | `<c:remove>` | 从特定的作用域移除变量。 |
| 4 | `<c:catch>` | 捕获发生的 `Throwable` 并可选地暴露。 |
| 5 | `<c:if>` | 条件为真时执行主体的条件标签。 |
| 6 | `<c:choose>` | 互斥操作标签，由 `<when>` 和 `<otherwise>` 标记。 |
| 7 | `<c:when>` | `<choose>` 的子标签，当条件为真时包含其主体。 |
| 8 | `<c:otherwise>` | `<choose>` 的子标签，当所有之前的条件为假时运行。 |
| 9 | `<c:import>` | 获取绝对或相对 URL 并将其内容暴露给页面、`String` 或 `Reader`。 |
| 10 | `<c:forEach>` | 基础迭代标签，接受许多集合类型并支持子集功能。 |
| 11 | `<c:forTokens>` | 对由分隔符分隔的标记进行迭代。 |
| 12 | `<c:param>` | 为 `import` 标签的 URL 添加参数。 |
| 13 | `<c:redirect>` | 重定向到一个 URL。 |
| 14 | `<c:url>` | 创建带有可选查询参数的 URL。 |

## 格式化标签

JSTL 格式化标签用于格式国际化网站的文本、日期、时间和数字。以下是包含格式化库的语法：

```jsp
<%@taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
```

下表列出了格式化 JSTL 标签：

| 序号 | 标签 | 描述 |
|---|---|---|
| 1 | `<fmt:formatNumber>` | 使用特定的精度或格式渲染数值值。 |
| 2 | `<fmt:parseNumber>` | 解析数字、货币或百分比的字符串表示。 |
| 3 | `<fmt:formatDate>` | 使用提供的样式和模式格式化日期和时间。 |
| 4 | `<fmt:parseDate>` | 解析日期和时间的字符串表示。 |
| 5 | `<fmt:bundle>` | 加载供其标签主体使用的资源包。 |
| 6 | `<fmt:setLocale>` | 将给定的区域存储在区域配置变量中。 |
| 7 | `<fmt:setBundle>` | 加载资源包并通过包的配置变量将其存储在命名的作用域变量中。 |
| 8 | `<fmt:timeZone>` | 为嵌套在其体内的时间格式化或解析操作指定时区。 |
| 9 | `<fmt:setTimeZone>` | 将给定的时区存储在时区配置变量中。 |
| 10 | `<fmt:message>` | 显示国际化消息。 |
| 11 | `<fmt:requestEncoding>` | 设置请求字符编码。 |

# SQL 标签

JSP SQL 标签库提供了用于与关系型数据库（RDBMS）如 Oracle、MySQL 或 Microsoft SQL Server 交互的标签。

以下是在 JSP 中引入 JSTL SQL 库的语法：

```jsp
<%@taglib prefix="sql" uri="http://java.sun.com/jsp/jstl/sql"%>
```

下表列出了 SQL JSTL 标签：

| 序号 | 标签 | 描述 |
|---|---|---|
| 1 | `<sql:setDataSource>` | 创建一个仅适用于原型制作的简单 `DataSource`。 |
| 2 | `<sql:query>` | 执行在体内或通过 `sql` 属性定义的 SQL 查询。 |
| 3 | `<sql:update>` | 执行在体内或通过 `sql` 属性定义的 SQL 更新。 |
| 4 | `<sql:param>` | 将 SQL 语句中的参数设置为指定指定的值。 |
| 5 | `<sql:dateParam>` | 将 SQL 语句中的参数设置为指定的 `java.util.Date` 值。 |
| 6 | `<sql:transaction>` | 提供具有共享连接的嵌套数据库操作元素，配置为将所有语句作为一个事务来执行。 |

# XML 标签

JSTL 标签提供了一种以 JSP 为中心创建和操作 XML 文档的方法。以下是在 JSP 中引入 JSTL XML 库的语法。

JSTL XML 标签库拥有用于与 XML 数据交互的自定义标签。这包括解析 XML、转换 XML 数据以及基于 XPath 表达式的流控制。

```jsp
<%@taglib prefix="x" uri="http://java.sun.com/jsp/jstl/xml" %>
```



在继续后续示例之前，您需要将两个 XML 和 XPath 相关的库复制到您的 `<Tomcat 安装目录>\lib` 中——

- 1. `Xercesimpl.jar` - 从 https://www.apache.org/dist/xerces/j/ 下载
- 2. `xalan-j` - 从 http://xml.apache.org/xalan-j/index.html 下载

以下是 JSTL 标签列表——

| 序号 | 标签与描述 |
|---|---|
| 1 | `<x:out>` 类似于 `<%= ... %>`，用于 XPath 表达式。 |
| 2 | `<x:parse>` 用于解析通过属性或标签主体指定的 XML 数据。 |
| 3 | `<x:set>` 将变量设置为 XPath 表达式的值。 |
| 4 | `<x:if>` 评估测试 XPath 表达式，如果为真，则处理其正文。如果条件为假，则忽略该正文。 |
| 5 | `<x:forEach>` 用于遍历 XML 文档中的节点。 |
| 6 | `<x:choose>` 简单条件标签，为互斥的条件操作建立上下文，由 `<when>` 和 `<otherwise>` 标签标记。 |
| 7 | `<x:when>` `<choose>` 的子标签，如果其表达式求值为 'true' 则包含其正文。 |
| 8 | `<x:otherwise>` `<choose>` 的子标签，跟在 `<when>` 标签之后，仅当所有先前的条件求值为 'false' 时才运行。 |
| 9 | `<x:transform>` 对 XML 文档应用 XSL 转换 |

# JSTL 函数

JSTL 包含许多标准函数，其中包含常用的字符串处理函数。以下是在 JSP 中引入 JSTL 函数库的语法——

```jsp
<%@taglib prefix="fn" uri="http://java.sun.com/jsp/jst/functions" %>
```

下表列出了各种 JSTL 函数——

| 序号 | 函数与描述 |
|---|---|
| 1 | `fn:contains()` 测试输入字符串是否包含指定的子字符串。 |
| 2 | `fn:containsIgnoreCase()` 忽略大小写地测试输入字符串是否包含指定的子字符串。 |
| 3 | `fn:endsWith()` 测试输入字符串是否以指定的后缀结束。 |
| 4 | `fn:escapeXml()` 转义可以解释为 XML 标记的字符。 |
| 5 | `fn:indexOf()` 返回字符串中首次出现指定子字符串的索引。 |
| 6 | `fn:join()` 将数组的所有元素连接成一个字符串。 |
| 7 | `fn:length()` 返回集合中的项数或字符串中的字符数。 |
| 8 | `fn:replace()` 返回将输入字符串中所有指定出现替换后的字符串。 |
| 9 | `fn:split()` 将字符串拆分为子字符串数组。 |
| 10 | `fn:startsWith()` 测试输入字符串是否以指定的前缀开头。 |
| 11 | `fn:substring()` 返回字符串的子集。 |
| 12 | `fn:substringAfter()` 返回指定子字符串之后的字符串子集。 |
| 13 | `fn:substringBefore()` 返回指定子字符串之前的字符串子集。 |
| 14 | `fn:toLowerCase()` 将字符串的所有字符转换为小写。 |
| 15 | `fn:toUpperCase()` 将字符串的所有字符转换为大写。 |
| 16 | `fn:trim()` 字符串两端的空格。 |

# 第 9 章：数据库访问

在本章中，我们将讨论如何使用 JSP 访问数据库。假设您已经熟悉了 JDBC 的工作原理。在通过 JSP 访问数据库之前，请确保已正确配置环境。关于如何使用 JDBC 访问数据库的更多细节，可以参考我们的教程。

## 创建表

要在 TEST 数据库中创建 Employees 表，请使用以下步骤——

步骤 1
`cd \Program Files\MySQL\bin`

步骤 2
如下登录数据库——
`C:\Program Files\MySQL\bin> mysql -u root -p`
输入密码：***

步骤 3
如下所示在 TEST 数据库中创建 Employees 表——

```sql
mysql> create table Employees (

id int not null,

age int not null,

first varchar (255),

last varchar (255)

);

Query OK;
```

## 创建数据

让我们在表中创建几条记录——

```sql
mysql> INSERT INTO Employees VALUES (100, 18, 'Zara', 'Ali');

Query OK, 1 row affected (0 sec)

mysql> INSERT INTO Employees VALUES (101, 25, 'Mahnaz', 'Fatma');

Query OK, 1 row affected (0 sec)

mysql> INSERT INTO Employees VALUES (102, 30, 'Zaid', 'Khan');

Query OK, 1 row affected (0 sec)

mysql> INSERT INTO Employees VALUES (103, 28, 'Sumit', 'Mittal');

Query OK, 1 row affected (0 sec)
```

## SELECT 操作

以下示例展示了如何在 JSP 编程中使用 JSTL 执行 SQL 语句——

```jsp
<%@page import="java.io.*,java.util.*,java.sql"%>
<%@page import="javax.servlet.http.*,javax.servlet.*" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/sql" prefix="sql" %>
```

```jsp
<html>
<head>
<title>SELECT 操作</title>
</head>
<body>
<sql:setDataSource var="snapshot" driver="com.mysql.jdbc.Driver"
  url="jdbc:mysql://localhost/TEST"
  user="root" password="pass123"/>
<sql:query dataSource="${snapshot}" result="result">
SELECT * from Employees;
</sql:query>
<table border="100%">
<tr>
<th>Emp ID</th>
<th>First Name</th>
<th>Last Name</th>
<th>Age</th>
</tr>
<c:forEach var="row" items="${result.rows}">
<tr>
<td><c:out value="${row.id}"/></td>
<td><c:out value="${row.first}"/></td>
<td><c:out value="${row.last}"/></td>
<td><c:out value="${row.age}"/></td>
</tr>
</c:forEach>
</table>
</body>
</html>
```

访问上述 JSP，将显示以下结果——

| Emp ID | First Name | Last Name | Age |
|---|---|---|---|
| 100 | Zara | Ali | 18 |

## INSERT 操作

以下示例展示了我们如何在 JSP 编程中使用 JSTL 执行 SQL INSERT 语句——

```jsp
<%@page import="java.io.*,java.util.*,java.sql"%>
<%@page import="javax.servlet.http.*,javax.servlet.*" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
<%@taglib uri="http://java.sun.com/jsp/jstl/sql" prefix="sql"%>
```

```jsp
<html>
<head>
<title>INSERT 操作</title>
</head>
<body>
<sql:setDataSource var="snapshot" driver="com.mysql.jdbc.Driver"
  url="jdbc:mysql://localhost/TEST"
  user="root" password="pass123"/>
<sql:update dataSource="${snapshot}" var="result">
INSERT INTO Employees VALUES (104, 2, 'Nuha', 'Ali');
</sql:update>
<sql:query dataSource="${snapshot}" var="result">
SELECT * FROM Employees;
</sql:query>
<table border="1" width="100%">
<tr>
<th>Emp ID</th>
<th>First Name</th>
<th>Last Name</th>
<th>Age</th>
</tr>
<c:forEach var="row" items="${result.rows}">
<tr>
<td><c:out value="${row.id}"/></td>
<td><c:out value="${row.first}"/></td>
<td><c:out value="${row.last}"/></td>
<td><c:out value="${row.age}"/></td>
</tr>
</c:forEach>
</table>
</body>
</html>
```

访问上述 JSP，将显示以下结果：

| 员工 ID | 名字 | 姓 | 年龄 |
| --- | --- | --- | --- |
| 100 | Zara | Ali | 18 |
| 101 | Mahnaz | Fatma | 25 |
| 102 | Zaid | Khan | 30 |
| 103 | Sumit | Mittel | 28 |
| 104 | Nuha | Ali | 20 |

## DELETE 操作

```jsp
<%@page import="java.io.*,java.util.*,java.sql.*" %>
<%@page import="javax.servlet.http.*,javax.servlet.*" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/sql" prefix="sql" %>
<html>
<head>
<title>DELETE Operation</title>
</head>
<body>
<sql:setDataSource var="snapshot" driver="com.mysql.jdbc.Driver"
url="jdbc:mysql://localhost/TEST"
user="root" password="pass123"/>
<c:set var="empid" value="103"/>
<sql:update dataSource="${snapshot}" var="count">
DELETE FROM Employees WHERE Id = ?
<sql:param value="${empid}" />
</sql:update>
<sql:query dataSource="${snapshot}" var="result">
SELECT * FROM Employees;
</sql:query>
<table border="1" width="100%">
<tr>
<th>Emp ID</th>
<th>First Name</th>
<th>Last Name</th>
<th>Age</th>
</tr>
<c:forEach var="row" items="${result.rows}">
<tr>
<td><c:out value="${row.id}"/></td>
<td><c:out value="${row.first}"/></td>
<td><c:out value="${row.last}"/></td>
<td><c:out value="${row.age}"/></td>
</tr>
</c:forEach>
</table>
</body>
</html>
```

访问上述 JSP，将显示以下结果 -

| 员工 ID | 名字 | 姓 | 年龄 |
| --- | --- | --- | --- |
| 100 | Zara | Ali | 18 |
| 101 | Mahnaz | Fatma | 25 |
| 102 | Zaid | Khan | 30 |

## UPDATE 操作

以下示例展示了如何使用 JSTL JSP 编程执行 SQL UPDATE 语句：

```jsp
<%@ page import="java.io.*,java.util.*,java.sql.*" %>
<%@ page import="javax.servlet.http.*,javax.servlet.*" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/sql" prefix="sql" %>
```

```jsp
<html>
<head>
<title>UPDATE Operation</title>
</head>
<body>
<sql:setDataSource var="snapshot" driver="com.mysql.jdbc.Driver"
url="jdbc:mysql://localhost/TEST"
user="root" password="pass123"/>
<c:set var="empid" value="102"/>
<sql:update dataSource="${snapshot}" var="count">
UPDATE Employees SET last='Ali' WHERE id = ?
<sql:param value="${empid}" />
</sql:update>
<sql:query dataSource="${snapshot}" var="result">
SELECT * FROM Employees;
</sql:query>
<table border="1" width="100%">
<tr>
<th>Emp ID</th>
<th>First Name</th>
<th>Last Name</th>
<th>Age</th>
</tr>
<c:forEach var="row" items="${result.rows}">
<tr>
<td><c:out value="${row.id}"/></td>
<td><c:out value="${row.first}"/></td>
<td><c:out value="${row.last}"/></td>
<td><c:out value="${row.age}"/></td>
</tr>
</c:forEach>
</table>
</body>
</html>
```

访问上述 JSP，将显示以下结果

| 员工 ID | 名字 | 姓 | 年龄 |
| --- | --- | --- | --- |
| 100 | Zara | Ali | 18 |
| 101 | Mahnaz | Fatma | 25 |
| 102 | Zaid | Ali | 30 |

# 第 30 章：XML 数据

当你通过 HTTP 发送 XML 数据时，使用 JSP 来处理和输出 XML 文档是合理的；例如 RSS 文档。由于 XML 文档仅仅是一组文本，通过 JSP 创建它比创建 HTML 文档要简单得多。

## 从 JSP 发送 XML

你可以像发送 HTML 一样使用 JSP 发送 XML 内容。唯一的区别是，必须将页面的内容类型设置为 `text/xml`。设置内容类型使用如下 `@page` 指令：

```jsp
<%@page contentType="text/xml"%>
```

以下示例展示了如何向浏览器发送 XML 内容：

```jsp
<%@page contentType="text/xml"%>
<books>
<book>
<name>History</name>
<author>Zara</author>
<price>100</price>
</book>
</books>
```



使用不同的浏览器访问上述 XML 以查看效果。

## 在 JSP 中处理 XML

在使用 JSP 处理 XML 之前，你需要将以下两个库拷贝到 `Tomcat/lib`：

- `Xerces.jar` - 从 https://www.apache.org/dist/xerces/ 下载
- `xalan.jar` - 从 https://www.apache.org/dist/xalan/ 下载

在 `books.xml` 中放入以下内容：

```xml
<books>
  <book>
    <name>History</name>
    <author>Zara</author>
    <price>100</price>
  </book>
  <book>
    <name>History</name>
    <author>Nuha</author>
    <price>2000</price>
  </book>
</books>
```

尝试位于同一目录下的 `main.jsp`：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jst/core" %>
<%@ taglib prefix="x" uri="http://java.sun.com/jsp/jst/xml" %>
<html>
<head>
<title>JSTL x:parse</title>
</head>
<body>
<h3>Books Info</h3>
<c:import var="bookInfo" url="books.xml"/>
<x:parse xml="${bookInfo}" var="output"/>
第一个书籍的名字是：<c:out select="${output[1]/name}" /><br/>
第二个书籍的价格是：<c:out select="${output[2]/price}" />
</body>
</html>
```

使用 `http://localhost:8080/main.jsp` 访问上述 JSP，将显示以下结果：

Books Info:
第一个书籍的名字是： History
第二个本书的价格：2000

## 使用 JSP 格式化 XML

考虑以下 XSL 样式表 `style.xsl`：

```xml
<?xml version="1.0"?>
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
<xsl:output method="html" indent="yes"/>
<xsl:template match="">
<html>
  <body>
    <xsl:apply-templates/>
  </body>
</html>
</xsl:template>
<xsl:template match="books">
<table border="1" width="100%">
<xsl:for-each select="book">
<tr>
<td><xsl:value-of select="name"/></td>
<td><xsl:value-of select="author"/></td>
<td><xsl:value-of select="price"/></td>
</tr>
</xsl:for-each>
</table>
</xsl:template>
</xsl:stylesheet>
```

现在考虑以下 JSP 文件：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jst/core" %>
<%@ taglib prefix="x" uri="http://java.sun.com/jsp/jst/xml" %>
<html>
<head>
<title>JSTL x:transform</title>
</head>
<body>
<h3>set var:</h3>
<c:set var="xmltext">
<books>
<book>
<name>History</name>
<author>Zara</author>
<price>100</price>
</book>
<book>
<name>History</name>
<author>Nuha</author>
<price>2000</price>
</book>
</books>
</c:set>
<c:import url="http://localhost:8080/style.xsl" var="xslt"/>
<x:transform xml="${xmltext}" xslt="${xslt}"/>
</body>
</html>
```

将显示以下结果：

Books Info:
History Zara 100
History Nuha 2000

要了解更多关于使用 JSTL 处理 XML 的信息，可以查看 JSP 标准标签库（JSP Standard Tag Library）。

# 第 31 章：JavaBeans

JavaBean 是一种根据 JavaBeans API 规范编写并编码的特殊构造 Java 类。以下是区分 JavaBean 与其他 Java 类的特征：

1. 它提供了一个默认的无参构造函数。
2. 它应该是可序列化的，并实现 `Serializable` 接口。
3. 它可能有许多可读或可写的属性。
4. 它可能为属性提供许多“getter”和“setter”方法。

# JavaBean 属性

JavaBean 属性是可以被对象用户访问的命名属性。该属性可以是任何 Java 数据类型，包括你定义的类。JavaBean 可以是可读、可写、只读或只写的。JavaBean 属性通过 JavaBean 实现类中的两个方法访问——

| 序号 | 方法与描述 |
|---|---|
| 1 | `getPropertyName()` 例如，如果属性是 `firstName`，你的方法名将是 `getFirstName()` 以读取该属性。该方法称为访问器（accessor）。<br>`setPropertyName()` 例如，如果属性是 `firstName`，你的方法名将是 `setFirstName()` 以写入该属性。该方法称为变更器（mutator）。 |

只读属性只有 `getProperty()` 方法，只写属性只有 `setProperty()` 方法。

# JavaBean 示例

考虑一个带有属性的学生类：

```java
package com.tutorial.point;

public class StudentsBean implements java.io.Serializable {

    private String firstName = null;
    private String lastName = null;
    private int age = 0;

    public StudentsBean() {
    }

    public String getFirstName() {
        return firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public int getAge() {
        return age;
    }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    public void setAge(Integer age) {
        this.age = age;
    }
}
```

# 访问 JavaBean

`useBean` 动作声明了一个用于 JSP 的 JavaBean。一旦声明完成，该 bean 就会变成一个脚本变量，可以被 JSP 中的脚本元素以及其他自定义标签访问。`useBean` 标签的完整语法如下：

```
<jsp:useBean id = "bean's name" scope = "bean's scope" typeSpec/>
```

根据你的需求，`scope` 属性的值可以是 `page`、`request`、`session` 或 `application`。`id` 属性的值可以是任何值，只要它在同一个 JSP 的其他 `useBean` 声明中是唯一的。

接下来的示例展示了如何使用 `useBean` 动作：

```html
<html>
<head>
<title>useBean Example</title>
</head>
<body>
<jsp:useBean id = "date" class = "java.util.Date" />
<p>The date/time is <%= date %></p>
</body>
</html>
```

你将获得以下结果 --
The date/time is Thu 30 11:18:11 GST 2010

## 访问 JavaBeans 属性

除了 `<jsp:useBean...>` 动作外，你还可以使用 `<jsp:getProperty/>` 动作来访问方法。这里是完整语法：

```
<jsp:useBean id = "id" class = "bean's class" scope = "bean's scope">
<jsp:setProperty name = "bean's id" property = "property name" value = "value"/>
<jsp:getProperty name = "bean's id" property = "property name"/>
</jsp:useBean>
```

属性引用了之前通过 `useBean` 动作引入 JSP 的 JavaBean 的 `id`。`property` 属性是应该调用的 get 或 set 方法。

接下来的示例展示了如何使用该语法访问数据：

```html
<html>
<head>
<title>get and set properties Example</title>
</head>
<body>
<jsp:useBean id = "students" class = "com.tutorialspoint.StudentsBean">
<jsp:setProperty name = "students" property = "firstName" value = "Zara"/>
<jsp:setProperty name = "students" property = "lastName" value = "Ali"/>
<jsp:setProperty name = "students" property = "age" value = "10"/>
</jsp:useBean>
<p>Student First Name:
<jsp:getProperty name="students" property="firstName"/>
</p>
<p>Student Last Name:
<jsp:getProperty name="students" property="lastName"/>
</p>
<p>Student Age:
<jsp:getProperty name="students" property="age"/>
</p>
</body>
</html>
```

现在让我们使用 CLASSPATH 中可用 `StudentsBean.class`。访问上面的 JSP。将显示以下结果：

Student First Name: Zara
Student Last Name: Ali
Student Age: 10

## 第 3 章：自定义标签

在本章中，我们将讨论 JSP 中的自定义标签。自定义标签是用户定义的 JSP 语言元素。当包含自定义标签的 JSP 页面被翻译成 servlet 时，该标签会被转换为对名为 tag handler（标签处理程序）的对象的操作。然后，当 JSP 页面的 servlet 执行时，Web 容器会调用这些操作。

JSP 标签扩展允许你创建可以直接插入 JSP 页面的新标签。JSP 2.0 规范引入了简单标签处理程序（Simple Tag Handlers）来编写这些自定义标签。

要编写自定义标签，你可以简单地扩展 `SimpleTagSupport` 类并重写 `doTag()` 方法，在其中你可以放置用于生成标签内容的代码。

## 创建 "Hello" 标签

假设你想定义一个自定义标签名称 `<ex:Hello>`，并且你想以不带正体的方式使用它：

```html
<ex:Hello>
```

要创建一个自定义 JSP 标签，必须先创建一个作为处理器的 Java 类。现在我们如下所示创建 `HelloTag` 类：

```java
package com.tutorialpoint;

import javax.servlet.jsp.tagext.*;
import javax.servlet.jsp.*;
import java.io.*;

public class HelloTag extends SimpleTagSupport {

    public void doTag() throws JspException, IOException {
        JspWriter out = getJspContext().getOut();
        out.print("Hello Tag!");
    }
}
```

上面的代码简单，`doTag()` 方法使用 `getJspContext()` 获取当前的 JspContext，并将 "Hello Tag!" 发送到当前的 JspWriter 对象。让我们将上述类拷贝到环境目录。最后，创建以下库文件：`webapp/WEB-INF/custom.tld`

```xml
<taglib>
  <lib-version>1.0</lib-version>
  <jsp-version>2.0</jsp-version>
  <short-name>TLD</short-name>
  <tag>
    <name>Hello</name>
    <class>com.tutorialpoint.HelloTag</class>
    <body-content>empty</body-content>
  </tag>
</taglib>
```

让我们如下所示在 JSP 中使用上述自定义标签：

```jsp
<%@ taglib prefix="ex" uri="WEB-INF/custom.tld"%>
<html>
<head>
<title>A sample custom tag</title>
</head>
<body>
  <ex:Hello/>
</body>
</html>
```

调用上面的 JSP 将产生如下结果：
Hello Tag!

## 访问标签体

正如标准标签所示，你可以在标签体中包含消息。假设你想定义一个名为 `<ex:Hello>` 的自定义标签，并且你想以带有正体的方式使用它：

```html
<ex:Hello>
  This is message
</ex:Hello>
```

让我们对上述标签代码进行以下更改以处理标签体：

```java
package com.tutorialpoint;

import javax.servlet.jsp.tagext.*;
import javax.servlet.jsp.*;
import java.io.*;

public class HelloTag extends SimpleTagSupport {

    StringWriter sw = new StringWriter();

    public void doTag() throws JspException, IOException {
        getJspBody().invoke(sw);
        getJspContext().getOut().println(sw.toString());
    }
}
```

在这里，调用产生的输出首先被捕获到与标签关联的 `StringWriter` 中。我们需要如下修改 TLD 文件：

```xml
<taglib>
  <lib-version>1.0</lib-version>
  <jsp-version>2.0</jsp-version>
  <short-name>Example TLD with Body</short-name>
  <tag>
    <name>Hello</name>
    <class>com.tutorialpoint.HelloTag</class>
    <body-content>scriptless</body-content>
  </tag>
</taglib>
```

现在我们如下所示带正体调用标签：

```jsp
<%@ taglib prefix="ex" uri="WEB-INF/custom.tld"%>
<html>
<head>
<title>A sample custom tag</title>
</head>
<body>
  <ex:Hello>
    This is a message body
  </ex:Hello>
</body>
</html>
```



</ex:Hello>

</body>

</html>

```

你将获得以下结果：
This is message body

## 自定义标签属性

你可以与自定义标签一起使用各种属性。为了接受属性值，自定义标签类需要实现如下所示的 JavaBean setter 方法：

```java
package com.tutorialpoint;

import javax.servlet.jsp.tagext.*;
import javax.servlet.jsp.*;
import java.io.*;

public class HelloTag extends SimpleTagSupport {

    private String message;

    public void setMessage(String msg) {
        this.message = msg;
    }

    StringBuilder sw = new StringBuilder();

    public void doTag() throws JspException, IOException {
        if (message != null) {
            /* 使用属性中的消息 */
            JspWriter out = getJspContext().getOut();
            out.println(message);
        } else {
            /* 使用标签体中的消息 */
            getJspBody().invoke(sw);
            getJspContext().getOut().println(sw.toString());
        }
    }
}
```

属性名为 "message"，所以 setter 方法是 `setMessage()`。现在我们使用 `<attribute>` 元素在 TLD 中添加此属性：

```xml
<taglib>
  <lib-version>1.0</lib-version>
  <jsp-version>2.0</jsp-version>
  <short-name>Example TLD with Body</short-name>
  <tag>
    <name>Hello</name>
    <class>com.tutorialpoint.HelloTag</class>
    <body-content>scriptless</body-content>
    <attribute>
      <name>message</name>
    </attribute>
  </tag>
</taglib>
```

让我们如下所示带 message 属性使用 JSP：

```jsp
<%@tag prefix="ex" uri="WEB-INF/custom.tld"%>
<html>
<head>
<title>A sample custom tag</title>
</head>
<body>
<ex:Hello message="This is custom tag" />
</body>
</html>
```

这将产生以下结果--
This is custom tag

考虑为属性包含以下属性：

| S.No. | Property & Purpose |
| --- | --- |
| 1 | name: 定义属性的名称。对于特定标签，每个属性名必须是唯一的。 |
| 2 | required: 指定此属性是必须的还是可选的。可选为 false。 |
| 3 | rtexprvalue: 声明标签属性的表达式值有效。 |
| 4 | type: 定义属性的 java 类类型。默认假设为 String。 |
| 5 | description: 可以提供信息性描述。 |
| 6 | fragment: 声明此属性值应该被视为 JspFragment。 |

以下是指定属性属性的示例：

```xml
<attribute>
  <name>attribute_name</name>
  <required>false</required>
  <type>java.util.Date</type>
  <fragment>false</fragment>
</attribute>
```

如果你正在使用属性，可以如下修改你的 TLD：

```xml
<attribute>
  <name>attribute_name1</name>
  <required>false</required>
  <type>java.util.Boolean</type>
  <fragment>false</fragment>
</attribute>
```

```xml
<attribute>
  <name>attribute_name2</name>
  <required>true</required>
  <type>java.util.Date</type>
</attribute>
```

## 第 33 章节：表达式语言 (EL)

JSP 表达式语言 (EL) 使得能够轻松访问存储在 JavaBeans 组件中的应用程序数据，JSP EL 允许你创建 (a) 算术表达式和 (b) 逻辑表达式。在 JSP 表达式中，你可以使用整数、浮点数、字符串、用于布尔值的内置构造 `true` 和 `false`，以及 `null`。

### 简单语法

通常，当你在 JSP 标签中指定属性值时，你直接使用字符串。例如 -

```jsp
<jsp:setProperty name="box" property="perimeter" value="100"/>
```

JSP EL 允许你为这些任何一个属性值指定表达式。JSP EL 的简单语法如下：

```
${expr}
```

这里 `expr` 指定的是表达式本身。JSP EL 中最常用的运算符是 `.` 和 `[]`。这两个运算符允许你访问 Java Beans 和内置对象的各种属性。

例如，上述语法 `<jsp:setProperty>` 可以用表达式写为 -

```jsp
<jsp:setProperty name="box" property="perimeter" value="${2.box.width+2.height}"/>
```

当 JSP 编译属性中的 `${}` 形式时，它会生成代码来评估表达式并替换表达式的值。
你还可以在标签的模板文本中使用 JSP EL 表达式。例如，`<jsp:text>` 标签简单地将其内容插入到 JSP 的正文中。以下 `<jsp:text>` 声明将 `<h1>Hello JSP!</h1>` 插入到 JSP 输出中 -

```jsp
<jsp:text>
<h1>Hello JSP!</h1>
</jsp:text>
```

你现在可以使用与用于属性时相同的 `${}` 语法，在 `<jsp:text>` 标签（或任何其他标签）的正文中包含一个 JSP 表达式。

```jsp
<jsp:text>
Box Perimeter: is ${2.box.width + 2.box.height}
</jsp:text>
```

（注）

EL 表达式可以使用括号来分组子表达式。例如，`${(1 + 2) * 3}` 等于 9，而不是 7。

要禁用 EL 表达式的评估，你只需指定页面指令的 `isELIgnored` 属性 -

```jsp
<% page isELIgnored = "true/false" %>
```

该属性的有效值为 `true` 和 `false`。如果是 `true`，当 EL 表达式出现在静态文本或标签属性中时将会被忽略。如果是 `false`，EL 表达式将由容器评估。

### EL 中的基本运算符

JSP 表达式语言 (EL) 支持 Java 支持的大多数算术和逻辑运算符。下表列出了最常用的运算符 –

| 序号 | 运算符 & 描述 |
|---|---|
| 1 | . | 访问 bean 属性或 Map 条目 |
| 2 | [] | 访问数组或 List 元素 |
| 3 | () | 分组子表达式以改变评估顺序 |
| 4 | + | 加法 |
| 5 | - | 减法或值的取反 |
| 6 | * | 乘法 |
| 7 | / or div | 除法 |
| 8 | % or mod | 取模（余数） |
| 9 | == or eq | 测试相等性 |
| 10 | != or ne | 测试不相等性 |
| 11 | < or lt | 测试小于 |
| 12 | > or gt | 测试大于 |
| 13 | <= or le | 测试小于或等于 |
| 14 | >= or ge | 测试大于或等于 |
| 15 | && or and | 测试逻辑与 AND |
| 16 | \|\| or or | 测试逻辑或 OR |
| 17 | ! or not | 一元布尔取反 |
| 18 | empty | 测试变量值为空 |

### JSP EL 中的函数

JSP 表达式语言 (EL) 允许在表达式中使用函数。这些函数定义在自定义标签库中。函数的用法语法如下：

`${ns:func(param1, param2, ...)}`

`ns` 是函数的命名空间，`func` 是函数名，`param1` 是第一个参数。例如，函数 `fn:length` 是 JSTL 库的一部分。该函数可以用于获取字符串的长度。

```jsp
${fn:length("my string")}
```

要使用任何函数库（标准或自定义），你必须在服务器上安装库，并在 JSP 中使用 `<taglib>` 指令，如 JSTL 章节中所说明的那样。

### JSP EL 隐式对象

JSP 表达式语言支持以下隐式对象 –

| 序号 | 隐式对象 & 描述 |
|---|---|
| 1 | pageScope | page 范围变量 |
| 2 | requestScope | request 范围变量 |
| 3 | sessionScope | session 范围变量 |
| 4 | applicationScope | application 范围变量 |
| 5 | param | 字符串格式的参数 |
| 6 | paramValues | 集合格式的参数 |
| 7 | header | 字符串格式 请求头 |
| 8 | headerValues | 集合格式的请求头 |
| 9 | init | 初始化参数 |
| 10 | cookie | Cookie 值 |

### pageContext

当前页面的 PageContext 对象。你可以像使用变量一样在表达式中使用这些对象。以下示例将帮助你理解这些概念 –

#### pageContext 对象

pageContext 对象提供了对 pageContext 对象的访问。通过 pageContext 对象，你可以访问请求对象。例如，要访问请求的查询字符串，可以使用以下表达式 –

```jsp
${pageContext.request.queryString}
```

#### 范围对象 (Scope Objects)

pageScope、requestScope、sessionScope 和 applicationScope 变量提供了对每个范围内变量的访问。例如，如果你需要显式访问 application 范围中的变量，可以通过 `applicationScope.box` 进行访问。

#### param 和 paramValues 对象

param 和 paramValues 对象提供了对通过 `request.getParameter` 和 `request.getParameterValues` 方法通常获取的参数值的访问。例如，要访问名为 `order` 的参数，使用表达式 `${param.order}` 或 `${param["order"]}`

```jsp
<%@page import = "java.io.*,java.util.*" %>
<% String title = "Accessing Request Param"; %>
<html>
<head>
<title><% out.print(title); %></title>
</head>
<body>
<!-- 这里是内容 -->
</body>
</html>
```

## 第 34 章节：用户示例

## 第 35 章节：异常处理

在本章节中，我们将讨论如何在 JSP 中处理异常。

JSP 提供选项为每个页面指定错误页面 (Error Page)。每当页面抛出异常时，JSP 容器会自动调用错误页面。

### 检查异常 (Checked exceptions)

检查异常通常是无法预见的用户错误。例如，如果要打开一个文件但找不到该文件，就会发生异常。这些异常不能简单地忽略。

### 运行时异常 (Runtime exceptions)

运行时异常可能是程序员本可以避免的异常。与检查异常相反，运行时异常在编译时被忽略。

### 错误 (Errors)

这些根本不是异常，而是发生在用户控制之外的问题。错误通常在你的代码中被忽略，因为你很少能对其做什么。例如，如果发生栈溢出，就会产生错误。

### 使用异常对象 (Using Exception Object)

异常对象是 Throwable 子类的实例（例如 `java.lang.NullPointerException`），并且仅在错误页面中可用。下表列出了 Throwable 类提供的重要方法。

| 序号 | 方法 & 描述 |
|---|---|
| 1 | public String getMessage() | 返回关于发生异常的详细消息。此消息在 Throwable 构造函数中初始化。 |
| 2 | public Throwable getCause() | 返回 Throwable 对象表示的异常。 |
| 3 | public String toString() | 返回类名与 getMessage() 结果拼接。 |
| 4 | public void printStackTrace() | 将 toString() 的结果连同堆栈轨迹打印到 System.err（错误输出流）。 |
| 5 | public StackTraceElement [] getStackTrace() | 返回包含堆栈轨迹每个元素的数组。0 表示调用栈的顶端，数组的最后一个元素表示调用栈底端的方法。 |
| 6 | public Throwable fillStackTrace() | 用当前堆栈轨迹填充此 Throwable 对象的堆栈轨迹，添加堆栈轨迹中的任何先前信息。 |

```html
<body>
<%
// 抛出异常以调用错误页面
int x = 1;

if (x == 1) {
    throw new RuntimeException("Error condition!!!");
}
%>
</body>
</html>
```

现在我们来编写一个错误处理 JSP `ShowError.jsp`，如下所示。请注意，错误处理页面包含了指令 `<% page isErrorPage = "true" %>`。该指令会导致 JSP 编译器生成异常实例变量。

```jsp
<%@ page isErrorPage = "true" %>
```

```html
<html>
<head>
<title>Show Error Page</title>
</head>
<body>
<h1>Opps...</h1>
<p>抱歉，发生了一个错误。</p>
<pre>这里是异常堆栈跟踪：<% exception.printStackTrace(response.getWriter()); %></pre>
</body>
</html>
```

访问 `main.jsp`，你将得到类似下面的输出——
java.lang.RuntimeException: Error condition!!!

......

Opps...

抱歉，发生了一个错误。

这里是异常堆栈跟踪：

### 使用 JSTL 标签处理错误页面

你可以使用 JSTL 来编写错误页面 `ShowError.jsp`。该页面的逻辑与上面的示例几乎相同，具有更好的结构和更多的信息——

```jsp
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@page isErrorPage = "true" %>
```

```html
<html>
<head>
<title>Show Error Page</title>
</head>
<body>
<h1>Opps...</h1>
<table width="100%" border="1">
<tr valign="top">
<td width="40%"><b>Error: </b></td>
<td>${pageContext.exception} </td>
</tr>
<tr valign="top">
<td><b>URI: </b></td>
<td>${pageContext.errorData.requestURI} </td>
</tr>
<tr valign="top">
<td><b>Status code: </b></td>
<td>${pageContext.errorData.statusCode} </td>
</tr>
</table>
</body>
</html>
```



```html
<tr valign="top">
<td><b>Stack trace: </b></td>
<td>
<c:forEach var="trace" items="${pageContext.stackTrace}">
<p>${trace}</p>
</c:forEach>
</td>
</tr>
```

```html
</table>
</body>
</html>
```

访问 `main.jsp`，将生成如下页面——

## 第 36 章：Opps...

**Error:** `java.lang.RuntimeException: Error condition!!!`

**URI:** `/main.jsp`

**Status code:** 500

`org.apache.jsp.main_jsp_jspService(main_jsp.jsp_JspBase.java:65)`

`org.apache.jasper.runtime.HttpJspBase.service(HttpJspBase.java:68)`

**Stack trace:** `javax.servlet.http.HttpServlet.service(HttpServlet.java:722)`

`org.apache.jasper.servlet.JspServlet.service(JspServlet.java:265)`

`javax.servlet.http.HttpServlet.service(HttpServlet.java:722)`

## 使用 Try..Catch 块

如果你想在同一个页面中处理错误，并希望采取某些操作而不是触发错误页面，你可以利用 `try...catch` 块。

以下是一个如何使用 `try...catch` 块的简单示例。我们将以下代码放入 `main.jsp` 中：

```html
<html>
<head>
<title>Try..Catch Example</title>
</head>
<body>
<%
try {
  int i = 1;
  i = 0;
  out.println("The answer is " + i);
}
catch (Exception e) {
  out.println("An exception occurred: " + e.getMessage());
}
%>
</body>
</html>
```

访问 `main.jsp`，它应该生成类似下面的输出：

```
An exception occurred: / by zero
```

# 第 37 章：调试

在本章中，我们将讨论如何调试 JSP。测试/调试 JSP 和 Servlet 总是很困难的。JSP 和 Servlet 往往涉及大量的客户端/服务器交互，导致错误容易发生但难以重现。

以下是一些可能帮助你进行调试的提示和建议。

## 使用 System.out.println()

`System.out.println()` 很容易使用，可以作为标记来测试某些代码是否被执行。我们也可以打印变量。考虑以下额外点：

1. 由于 `System` 对象是核心 Java 对象的一部分，因此可以在任何地方使用，而不需要安装额外的类。这包括 Servlets、JSP、RMI、EJBs、普通的 Bean 和类以及独立应用程序。

2. 与停止在断点处相比，写入 `System.out` 不会对应用程序的正常执行流产生太大干扰，这使得它在时机至关重要时非常有价值。

以下是使用 `System.out.println()` 的语法：

```
System.out.println("Debugging message");
```

下面的示例显示了如何使用 `System.out.print()`：

```jsp
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<html>
<head><title>System.out.println()</title></head>
<body>
<c:forEach var="counter" begin="1" end="10" step="1">
  <c:out value="${counter-5}"/><br>
  <% System.out.println("counter = " + pageContext.findAttribute("counter")); %>
</c:forEach>
</body>
</html>
```

访问上面的 JSP，浏览器将显示以下结果：

- -4
- -3
- -2
- -1
- 0
- 1
- 2
- 3
- 4
- 5

如果你使用的是 Tomcat，你还会在日志目录下的 `stdout.log` 末尾发现这些行：

```
counter = 1
counter = 2
counter = 3
counter = 4
counter = 5
counter = 6
counter = 7
counter = 8
counter = 9
counter = 10
```

你可以这种方式将变量和其他信息引入系统日志，通过分析这些可以找到问题的根源或各种原因。

## 使用 JDK Logger

**J2SE** 日志框架旨在为运行在 JVM 中的任何类提供日志服务。我们可以利用这个框架来记录任何信息。让我们使用 JDK API 重写示例：

```jsp
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@page import="java.util.logging.Logger" %>
<html>
<head><title>Logger.info</title></head>
<body>
<% Logger logger = Logger.getLogger(this.getClass().getName()); %>
<c:forEach var="counter" begin="1" end="10" step="1">
  <c:set var="myCount" value="${counter-5}" />
  <c:out value="${myCount}"/><br>
  <%
    String message = "counter = " + pageContext.findAttribute("counter") + " myCount = " + pageContext.findAttribute("myCount");
    logger.info(message);
  %>
</c:forEach>
</body>
</html>
```

访问上面的 JSP，浏览器将显示以下结果（此处原文未提供具体输出内容，但根据上文应为日志输出）。

上面的代码会在浏览器中生成类似下面的输出，但你可以在 `stdout.log` 中看到这些信息。我们可以使用 logger 来记录信息，根据严重性来调试。

你可以使用 Log4J 框架根据其严重性级别发送消息。

## 调试工具

NetBeans 是一个免费的开源 Java 开发环境，支持 Java 应用和 Web 应用开发。

NetBeans 支持以下调试功能：

1. 断点
2. 逐步执行代码
3. 视点

你可以参考 NetBeans 文档了解上述调试功能。

## 使用 JDB 调试器

你可以调试 JSP 和 Servlet，可以使用 `jdb` 命令来调试应用。

要调试 JSP 或 Servlet，你可以调试 `sun.servlet.HttpServer`，然后观察 `HttpServer` 如何响应 HTTP 请求。

大多数调试器通过自动知道如何调试 Applet 而隐藏了细节。在它们对 JSP 这样做之前，你必须通过以下方式帮助你的调试器：

1. 设置调试器的类路径。这有助于找到 `sun.servlet.Server` 以及调试器相关的类。
2. 设置调试器的类路径。这有助于找到你的 JSP 和支持类，`ROOT/WEB-INF/classes`。

一旦有了服务器类路径，就可以调试 `sun.servlet.HttpServer`。你可以在感兴趣的 JSP 中设置断点，然后使用网络浏览器向服务器请求该 JSP（`http://localhost:8080/JSPToDebug`）。执行会在断点处停止。

## Internet Explorer 使用 Shift 刷新

# 第 38 章：安全

JSP 和 Servlet 为 Web 应用提供了多种机制来保护应用程序。资源是通过声明式的受保护的，通过在应用部署描述符中标识它们并为它们分配角色来实现。

提供了多个层级的身份验证，范围从使用标识符和密码的普通身份验证到使用证书的复杂身份验证。

## 基于角色的认证

Servlet 规范中的身份验证机制使用名为基于角色的安全（role-based security）的技术。其思想不是在用户级别限制资源，而是创建角色并根据角色来限制资源。

你可以在 `tomcat-users.xml` 文件中定义不同的角色，该文件位于 Tomcat 目录下的 `conf` 中。下面是一个示例：

```xml
<?xml version='1.0' encoding='utf-8'?>
<tomcat-users>
  <role name="tomcat"/>
  <role name="role1"/>
  <role name="manager"/>
  <role name="admin"/>
  <user username="tomcat" password="tomcat" roles="tomcat"/>
  <user username="role1" password="tomcat" roles="role1"/>
  <user username="both" password="tomcat" roles="tomcat,role1"/>
  <user username="admin" password="secret" roles="admin,manager"/>
</tomcat-users>
```

此文件定义了用户名、密码和角色之间的简单映射。注意，给用户可能拥有多个角色；例如，用户名="both" 属于 "tomcat" 且角色为 "role1"。

一旦你识别并定义了不同的角色，就可以使用 `WEB-INF` 目录下 `web.xml` 文件中的 `<security-constraint>` 元素对不同的 Web 应用资源设置基于角色的安全限制。

以下是 `web.xml` 中的示例条目：

```xml
<web-app>
...
  <security-constraint>
    <web-resource-collection>
      <web-resource-name>SecuredBookSite</web-resource-name>
      <url-pattern>/secured/*</url-pattern>
      <http-method>GET</http-method>
      <http-method>POST</http-method>
    </web-resource-collection>
    <auth-constraint>
      <description>
        Let only managers use this app
      </description>
      <role-name>manager</role-name>
    </auth-constraint>
  </security-constraint>

  <security-role>
    <role-name>manager</role-name>
  </security-role>

  <login-config>
    <auth-method>BASIC</auth-method>
  </login-config>
</web-app>
```

上述条目意味着：

1. 任何对匹配 `/secured/*` URL 的 HTTP GET 或 POST 请求都将受到安全限制。
2. 具有 manager 角色的人员将获得访问受保护资源的权限。
3. `login-config` 元素用于描述 BASIC 形式的身份验证。

如果你正在浏览包括 `/secured` 目录的任何 URL，将显示请求用户名和密码的对话框。如果你提供了用户 "admin" 和密码 "secret"，那么你就可以访问匹配 `/secured/` 的 URL，因为你已经定义了允许访问此资源的 manager 角色用户。

## 基于表单的认证

当你使用该身份验证方法时，必须提供一个登录表单来提示用户输入用户名和密码。以下是 `login.jsp` 的简单代码。这有助于创建一个相同目的的表单：

```html
<html>
<body bgcolor="#ffffff">
<form method="POST" action="j_security_check">
<table>
  <tr>
    <td>Login (登录)</td>
    <td><input type="text" name="j_username"></td>
  </tr>
  <tr>
    <td>Password (密码)</td>
    <td><input type="password" name="j_password"></td>
  </tr>
</table>
<input type="submit" value="Login! (登录!)">
</form>
</body>
</html>
```

你必须确保登录表单必须包含 name 命名为 `j_username` 和 `j_password` 的表单元素。`<form>` 标签中的 `action` 必须是 `j_security_check`。

必须使用 POST 作为表单方法。同时，你将不得不修改 `<login-config>` 标签将 `auth-method` 指定为 FORM：

```xml
<web-app>
  ...
  <security-constraint>
    <web-resource-collection>
      <web-resource-name>SecuredBookSite</web-resource-name>
      <url-pattern>/secured/*</url-pattern>
      <http-method>GET</http-method>
      <http-method>POST</http-method>
    </web-resource-collection>
    <auth-constraint>
      <description>Let only managers use this app</description>
      <role-name>manager</role-name>
    </auth-constraint>
  </security-constraint>
  <security-role>
    <role-name>manager</role-name>
  </security-role>
  <login-config>
    <auth-method>FORM</auth-method>
    <form-login-config>
      <form-login-page>/login.jsp</form-login-page>
      <form-error-page>/error.jsp</form-error-page>
    </form-login-config>
  </login-config>
</web-app>
```

如果你正在浏览包括 `/secured` 目录的任何 URL，将显示登录表单。如果你提供了用户 "admin" 和密码 "secret"，那么你就可以访问匹配 `/secured/` 的 URL，因为你已经定义了允许访问此资源的 manager 角色用户。

## 区域语言

下划线。例如，“en_US”代表美国的英语区域。

在构建全球网站时，有许多项目需要注意。本教程将不会提供这些细节，但将为你提供一个很好的示例，说明如何通过区分不同的位置（即区域语言，locale）向互联网社区提供不同语言的网页。

JSP 可以根据请求者的区域语言（locale）选取站点版本，并根据当地语言、文化和需求提供相应的站点版本。以下是返回 `Locale` 对象的请求对象方法：`request.getLocale()`

## 检测区域语言

以下是你可以用于检测请求者位置、语言以及区域语言的重要 locale 方法。以下所有方法都会显示请求者浏览器中设置的国家名称和语言。

| 序号 | 方法与描述 |
|---|---|
| 1 | **`String getCountry()`**<br>该方法返回该区域语言对应的、ISO 3166 2 位格式的大写国家/地区代码。 |
| 2 | **`String getDisplayCountry()`**<br>该方法返回一个适用于显示给用户的区域国家名称。 |
| 3 | **`String getLanguage()`**<br>该方法返回该区域语言对应的、ISO 639 格式的小写语言代码。 |
| 4 | **`String getDisplayLanguage()`**<br>该方法返回一个适用于显示给用户的区域语言名称。 |
| 5 | **`String getISO3Country()`**<br>该方法返回该区域语言国家的三位字母缩写。 |
| 6 | **`String getISO3Language()`**<br>该方法返回该区域语言的三位字母缩写。 |

## 示例

以下示例展示了如何在 JSP 中为请求显示语言及关联国家：



# JSP 国际化示例

## 检测区域设置

```jsp
<%@ page import = "java.io.*,java.util.Locale" %>
<%@ page import = "javax.servlet.*,javax.servlet.http.*" %>
<%
// 获取客户端的 Locale
Locale locale = request.getLocale();
String language = locale.getLanguage();
String country = locale.getCountry();
%>
```

```jsp
<html>
<head>
<title>Detecting Locale</title>
</head>
<body>
<center>
<h1>Detecting Locale</h1>
</center>
<p align="center">
<%
out.print("Language : " + language + "<br/>");
out.print("Country : " + country + "<br/>");
%>
</p>
</body>
</html>
```

## 语言设置

JSP 可以输出用西欧语言编写的页面，如英语、西班牙语、德语、法语、意大利语、荷兰语等。在这里设置 `Content-Language` 头部对于正确显示所有字符非常重要。

另一个重点是使用 HTML 实体显示所有特殊字符；例如，“`&#241;`”代表“ñ”，“`&#161;`”代表“¡”，如下所示：

```jsp
<%@ page import = "java.io.*;java.util.Locale" %>
<%@ page import = "javax.servlet.*,javax.servlet.http.*" %>
```

```jsp
// 设置响应内容类型
response.setContentType("text/html");
```

```jsp
// 设置西班牙语代码
response.setHeader("Content-Language", "es");
String title = "En Español";
%>
```

```jsp
<html>
<head>
<title><% out.print(title); %></title>
</head>
<body>
<center>
<h1><% out.print(title); %></h1>
</center>
<div align="center">
<p>En Español</p>
<p>¡Hola Mundo!</p>
</div>
</body>
</html>
```

## 特定区域日期

你可以使用 `java.text.DateFormat` 类及其静态 `getDateTimeInstance()` 方法来格式化特定区域的日期。以下是如何格式化给定区域日期的示例：

```jsp
<%@ page import = "java.io.*,java.util.Locale" %>
<%@ page import = "javax.servlet.*,javax.servlet.http.*" %>
<%@ page import = "java.text.DateFormat,java.util.Date" %>
<%
String title = "Locale Dates";

// 获取客户端的 Locale
Locale locale = request.getLocale();

String date = DateFormat.getDateTimeInstance(DateFormat.FULL,
DateFormat.SHORT,
locale).format(new Date());
%>
```

```jsp
<html>
<head>
<title><% out.print(title); %></title>
</head>
<body>
<center>
<h1><% out.print(title); %></h1>
</center>
<div align="center">
<p>Date: <% out.print(date) %></p>
</div>
</body>
</html>
```

## 特定区域货币

你可以使用 `java.text.NumberFormat` 类及其静态 `getCurrencyInstance()` 方法将数字（`long` 或 `double` 类型）格式化为特定区域的货币。以下是格式化给定区域货币的示例：

```jsp
<%@ page import = "java.io.*,java.util.Locale" %>
<%@ page import = "javax.servlet.*,javax.servlet.http.*" %>
<%@ page import = "java.text.NumberFormat,java.util.Date" %>
<%
String title = "Locale Specific Currency";

// 获取客户端的 Locale
Locale locale = request.getLocale();

NumberFormat nf = NumberFormat.getCurrencyInstance(locale);
String formattedCurr = nf.format(1000000);
%>
```

```jsp
<html>
<head>
<title><% out.print(title); %></title>
</head>
<body>
<center>
<h1><% out.print(title); %></h1>
</center>
<div align="center">
<p>Formatted Currency: <% out.print(formattedCurr); %></p>
</div>
</body>
</html>
```

## 特定区域百分比

你可以使用 `java.text.NumberFormat` 类及其静态 `getInstance()` 方法获取特定区域的百分比。以下示例展示了如何格式化给定区域的百分比：

```jsp
<%@ page import = "java.io.*,java.util.Locale" %>
<%@ page import = "javax.servlet.*,javax.servlet.http.*" %>
<%@ page import = "java.text.NumberFormat,java.util.Date" %>
<%
String title = "Locale Specific Percentage";

// 获取客户端的 Locale
Locale locale = request.getLocale();

NumberFormat nf = NumberFormat.getInstance(locale);
String formattedPerc = nf.format(0.51);
%>
```

```jsp
<html>
<head>
<title><% out.print(title); %></title>
</head>
<body>
<center>
<h1><% out.print(title); %></h1>
</center>
<div align="center">
<p>Formatted Percentage: <% out.print(formattedPerc); %></p>
</div>
</body>
</html>
```
