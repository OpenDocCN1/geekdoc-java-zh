
# Java / J2EE 面试常见问题（工作面试题）

免费

包含 2 份能力测试，可在网站下载

# Java / J2EE 面试题

回顾这些典型的面试题，并思考你会如何回答它们。阅读列出的答案；你将找到最佳答案以及相关的策略和建议。

# 架构与协议

## 1: J2EE 架构的设计目标是什么？

以下是 J2EE 架构的设计目标：

- **服务可用性**：应用程序应保持 24 * 7 小时可用。业务依赖应用程序，而不需要客户代表。
- **数据连接**：应用程序应该能够连接到主机系统和其他遗留系统，以确保业务功能正常进行。
- **可访问性**：用户应该从任何地方、通过任何电子设备连接应用程序。
- **用户交互**：用户应该能够从桌面电脑、笔记本电脑、PDA 和移动设备连接应用程序。
- **灵活性**：架构的设计方式应让开发者专注于业务组件模型（业务逻辑），而其他服务由服务器处理。

## 2: J2EE 架构师的角色是什么？

以下是 J2EE 架构师的角色：

- 系统蓝图行为的可视化
- 创建系统蓝图
- 定义系统元素如何协同工作
- 定义非功能性需求和功能性需求
- 将非功能性需求集成到功能系统中

## 3: 架构和设计之间有什么区别？

架构定义了结构问题、通信协议、数据访问、同步以及子系统的分类。它还定义了组件接口的架构设计。

在设计中，我们为每个接口定义要创建的组件、输入、输出、算法和数据结构。简之，设计者描述了每个组件的内部细节。

## 4: 架构分析中执行哪些活动？

在架构分析中将执行以下活动：

- **用例图**：开发此以描述高层系统功能。
- **类图**：开发此以类和方法的形式描述功能。
- **协作图**：开发此描述每个类之间如何通信。
- **时序图**：开发此描述操作序列。

## 5: 架构设计中执行哪些活动？

在架构设计中将执行以下活动：

- 决定将使用的框架（例如：远程方法调用 `RMI`）。
- 定义软件和硬件需求。
- 定义性能参数和实现方法。
- 分析是否复用现有组件或技术。
- 定义系统的业务逻辑、安全和性能。

## 6: 面向对象设计中执行哪些活动？

在面向对象设计中将执行以下活动：

- 决定类如何与包交互。
- 创建依赖关系。
- 创建部署图。
- 决定组件是否存在于部署中。

## 7: 多层架构的组件有哪些？

以下是多层架构的组件：

- **表现层**：该层存在前端组件，用于展示表现内容。
- **资源层**：该层存在后端组件，用于与数据库通信。
- **业务层**：该层存在的组件用于提供业务逻辑。

## 8: 多层客户端/服务器架构的优势是什么？

以下是多层客户端/服务器架构的优势：

- 可以独立对业务逻辑或用户界面进行修改。
- 客户端在不知道数据来源和有多少台服务器的情况下访问数据。
- 数据库连接可以池化，以便多个用户共享，而无需为每个用户请求数据库。
- 中间层组件（业务逻辑）可以使用任何标准编程语言（如 `C` 或 `Java`）。

## 9: 开发者的责任是什么？

以下是开发者的责任：

- 使用 `Java` 编写系统业务逻辑。
- 将 `Java` 组件与第三方组件集成。
- 控制访问并设置事务参数。
- 创建查找 bean 的本地接口和创建业务逻辑的远程接口。
- 创建部署描述。

## 10: 应用组装器的责任是什么？

以下是应用组装器的责任：

- 构建表现层，即用户界面。
- 指定事务管理的需求。
- 为所有 bean 方法设置事务参数。
- 定义安全角色并分配权限。
- 为方法指定通配符 (`*`)。

## 11: Bean 部署器的责任是什么？

以下是 Bean 部署器的责任：

- 将字段映射到数据库列并管理持久化。
- 定义用户、组、角色并管理安全。
- 使用部署工具并生成包装类。
- 映射用户角色和组。
- 确保所有部署的 bean 都分配了事务参数。

## 12: 第三方软件在 EJB 框架中扮演什么角色？

提供软件的第三方公司可以扮演三个角色之一：

- **组件提供者**：负责对象建模、编程、架构和业务过程。
- **容器提供者**：负责在运行时提供环境。
- **应用服务器提供者**：负责提供开发分布式应用程序的平台。它通常包含提供运行时环境的容器。

## 13: 解释 MVC 架构。

MVC 代表模型-视图-控制器（Model View Controller）架构。MVC 中执行的操作解释如下：

- **模型（Model）**：开发者创建系统的业务逻辑
- **视图（View）**：开发者创建展示逻辑
- **控制器（Controller）**：开发者接收请求并传输响应

## 14: 解释 EAR、WAR 和 JAR。

- **EAR** 代表企业存档（Enterprise Archive）。它包含了 Web、EJB 和客户端组件。所有组件都打包在一个名为 `.ear` 的压缩文件中。
- **WAR** 代表 Web 归档（Web Archive）。它包含了与 Web 应用程序相关组件。所有组件都打包在一个名为 `.war` 的压缩文件中。
- **JAR** 代表 Java 归档（Java Archive）。它包含了构成 API（应用程序编程接口）的所有类文件和库文件。所有组件都打包在一个名为 `.jar` 的压缩文件中。

## 15: 解释 JTA、JNDI 和 JMS。

- **JTA** 代表 Java 事务 API（Java Transaction API）。它用于协调和管理企业信息系统中的事务。
- **JNDI** 代表 Java 命名目录接口（Java Naming Directory Interface）。用于从目录服务中访问信息。
- **JMS** 代表 Java 消息服务（Java Messaging Service）。用于通过消息系统接收和发送消息。

## 16: 解释 EDI。

EDI 代表电子数据交换（Electronic Data Interchange）。它用于通过作为传输媒介的增值网络（VAN）交换数据。

EDI 安装成本昂贵，且需要交换客户端进行定制。EDI 还需要依赖 X12 标准来交换文档。

## 17: 什么是 EAI？

EAI 代表企业应用集成（Enterprise Application Integration）。它将一个或多个应用程序视为单个应用程序，并要求在正确的时间将数据传输到相应的系统。

例如，在整合销售和会计系统时，必须向会计部门发送销售订单以生成发票。此外，会计部门必须向销售部门发送发票以更新销售人员的数据。

该系统自动处理应用程序之间的事务，消除了人为错误。

## 18: 在 Java 中支持 XML 的意图是什么？

支持 XML 的意图是：

- 确保 Java 开发者更容易理解 XML 并使用 XML，同时让 XML 开发者使用 Java
- 为 Java 提供默认标准，以确保实现的一致性和兼容性
- 确保 Java 平台能够高质量集成

## 19: 业务层与用户界面之间通信使用哪些协议？

业务层与用户界面之间通信使用的协议如下：

- **HTTP**：代表“超文本传输协议”（Hyper Text Transfer Protocol）
- **JMS**：代表“Java 消息服务”（Java Messaging Service）
- **RMI**：代表“远程方法调用”（Remote Method Invocation）
- **CORBA**：代表“通用对象请求代理架构”（Common Object Request Broker Architecture）
- **DCOM**：代表“分布式组件对象模型”（Distributed Component Object Model）

# 你可能被问到的 Java / J2EE 面试题

## 20: HTTP 协议的优缺点是什么？

以下是 HTTP 协议的优点：

- 无状态且防火墙友好
- HTTP 服务器更容易负载均衡和扩展

以下是 HTTP 协议的缺点：

- 难以维护用户会话
- 与 JSP 和 servlet 的通信有限

## 21: 解释 JRMP。

JRMP 代表 Java 远程方法对象协议（Java Remote Method Object Protocol）。它被远程方法调用（`RMI`）用于将 Java 对象作为参数传递。

由于 Java 依赖对象序列化（将对象封装为流），`RMI` 依赖 `JRMP` 协议将对象从一个 JVM（Java 虚拟机）传输到另一个。

## 22: CORBA 的优缺点是什么？

以下是 CORBA 的优点：

- 支持异构对象
- 扩展了 ORB（对象请求代理）的能力

以下是 CORBA 的缺点：

- 无法传递对象，只能传递参数
- 只能传递接受的数据类型

## 23: 解释 DCOM。

DCOM 代表分布式组件对象模型（Distributed Component Object Model）。它通过远程方法调用来传递对象。

DCOM 构建在 ORPC（对象过程调用）之上，用于支持远程对象。DCOM 包含了多种接口和交互方式，可以使用多种编程语言创建。

## 24: 解释 J2EE 的功能。

以下是 J2EE 的功能：

- **性能**：在短时间内完成操作
- **可扩展性**：支持负载增加
- **可用性**：系统 24 小时持续可用
- **灵活性**：硬件的变化不会影响系统
- **安全性**：信息不会被破解
- **可重用性**：系统可以被重用

## 25: 解释系统架构和参考架构。

系统架构代表产品。它包含了系统功能、接口和约束。

参考架构代表风格。它是特定领域的设计原则。

## 26: 解释最佳实践（Best Practice）。

最佳实践可以定义为：

- 驱动组件设计的技术
- 适用于工作类似项目的成员
- 考虑设计或系统需求

## 27: 解释 JEE 分层。

JEE 包含以下分层：

- **客户端层（Client Tier）**：代表向服务器发送请求的浏览器。该层使用的技术有 `HTML`、`Applet` 或非 Java 程序。
- **中间层（Middle Tier）**：由展示层、业务层和集成层组成。用户界面使用 `JSP` 创建在展示层。业务逻辑使用 `EJB` 创建在业务层。数据库对象创建在集成层。
- **后端（Backend）**：构成企业信息系统（EIS），用于存储数据。

## 28: 展示层遵循哪些最佳实践？

展示层的最佳实践解释如下：

- 将文本标记语言（`HTML`）与 `Java` 分离
- 始终在 Bean 类中编写业务逻辑
- 使用 `JSP` 模板和注释
- 使用模型视图控制器（`MVC`）模式
- 使用自定义库和标签处理器

## 29: MVC 使用什么类型的组件？

MVC 代表模型-视图-控制器。模型、视图和控制器的组件解释如下：

- **应用程序**代表模型，构成系统状态。系统状态作为业务逻辑创建在 Bean 类中
- **用户界面**代表视图，使用 Java Pages 创建
- 从客户端接收的请求总是控制器，使用 `Servlet` 创建

## 30: J2EE 系统在全球经济中运营需要哪些要求？

J2EE 系统在全球运营需要具备以下要求：

- **财务考虑**：购买物品的支付方式应包含多种形式，因为并非所有访问者都有信用卡。此外，每个政府都有自己的税收、海关限制和关税
- **语言要求**：应用程序应支持多种语言，并适用于特定国家
- **法律差异**：每个国家的海关法和隐私要求不同，每个政府对图像、思想和演讲都有限制

## 31: DAO 应遵循哪些最佳实践？

DAO 代表数据访问对象（Data Access Object）。DAO 应遵循的最佳实践如下：

- DAO 不应与业务逻辑紧耦合
- 每个企业 Bean 应该关联一个 DAO 类
- DAO 仅应用于从数据库访问数据
- DAO 的编写方式应允许跨架构和数据库能力
- DAO 的编写方式应支持可移植性

## 32: 解释指南（Guideline）。

指南是指由专业公认的组织或协会开发的关于操作的规则或协议。它还包括在项目活动期间需要遵守的已批准的正式专有标准。指南的示例是：分析师尝试通过最大化内容来减少网络流量。

## 33: VO（值对象）中应该遵循哪些最佳实践？

VO 代表值对象（Value Object）。值对象中应遵循的最佳实践解释如下：

- VO 应该包含带有 `get` 和 `set` 方法业务对象
- VO 应该用相应的值更新模型 bean 对象
- VO 不应该引用服务器上的对象
- VO 应该代表来自服务器的数值

## 34: 会话 Bean 外观（Session Bean Facade）中应该遵循哪些最佳实践？

以下是会话 Bean 外观中应遵循的最佳实践：

- 它应该减少对应用程序服务器的远程调用
- 对调用实体 Bean 组的方法应用事务范围（transactional scope）
- 简化客户端，使业务逻辑仅在应用程序服务器上执行
- 代码编写方式应该识别权限并提供灵活性和重用性

## 35: 模型视图控制器（MVC）有哪些优点？

以下是 MVC 的优点：

- 将数据模型与用户交互及数据显示分离，并明确了应用设计
- 允许以多种形式和由大量用户查看数据
- 通过将功能与表示分离来增强重用性
- 增加灵活性并提高扩展性
- 封装应用程序功能并便于维护
- 支持增量更新并划分部署

## 36: MVC 有哪些设计上的问题？

以下是 MVC 的设计问题：

- 组件感知不到其他组件的实现细节
- 必须仔细处理延迟问题和通信量，否则在分布式系统中会导致可扩展性问题
- 如果 Model 不稳定，MVC 将难以维护，因为控制器大部分是基于 Model 编写的

## 37: 解释 MVC 的适用性。

MVC 适用于以下情况：

- 如果应用足够大且是分布式的
- 如果应用寿命较长
- 接口和后端的可移植性最重要的
- 为了便于维护和重用
- 由多个开发者开发应用
- 以多种方式查看并操纵数据

## 38: 解释模式（Patterns）在 J2EE 框架中的性质。

模式是指特定语境中解决业务问题的反复解决方案。语境是指问题存在的情况或环境。问题是需要调查且必须解决的，并通过因果关系指定。

## 39: 解释框架模式（Framework Patterns）。

以下被称为框架模式：

- **代理模式（Proxy Pattern）**：`EJB` 远程接口是代理模式的示例。它拥有的方法可以将方法调用委托给对象
- **工厂方法（Factory Method）**：`EJB Home` 接口是工厂方法的示例。它有一个独立且可重用的类，通过通用接口引用对象
- **抽象工厂方法（Abstract Factory Method）**：`EJB Home` 接口是抽象工厂方法的示例。它是从具体子类创建抽象类实例的过程
- **装饰器（Decorator）**：`EJBObject` 是装饰器模式的示例。装饰器的功能是它是对客户端可见的

## 40: 部署器（Deployer）的活动有哪些？

部署器执行以下活动：

- 将开发阶段创建的企业级包（`EAR`）文件部署到 J2EE 应用程序服务器中
- 修改部署描述符并配置 J2EE 应用程序
- 确保企业级包文件（`EAR`）格式正确并符合 J2EE 规范
- 在 J2EE 应用程序服务器中安装或部署企业级包文件

## 41: 哪些模式属于集成层（Integration Tier）？

以下模式属于集成层：

- **DAO**：数据访问对象（Data Access Object）检索数据源并提供透明的数据访问
- **服务激活器（Service Activator）**：这被用于 `EJB` 组件并支持异步处理

## 42: 表现层（Presentation Tier）模式有哪些？

以下是表现层模式：

- **前端控制器（Front Controller）**：用于处理和管理来自客户端的请求
- **装饰器过滤器（Decorating Filter）**：用于特定请求的预处理和后处理
- **复合视图（Composite View）**：用于为子组件创建视图
- **分发视图（Dispatch View）**：用于与前端控制器协作查看视图助手模式并推迟处理查看活动
- **视图助手（View Helper）**：用于封装逻辑和格式表示

## 43: 解释业务层（Business Tier）模式。

以下是业务层模式：

- **会话外观（Session Facade）**：隐藏业务对象的复杂性并集中处理工作流
- **值对象（Value Object）**：用于在不同层之间交换数据
- **服务定位器（Service Locator）**：隐藏服务的复杂性和查找
- **业务委托（Business Delegate）**：用于分离服务层和表现层
- **值对象组装器（Value Object Assembler）**：用于构建

## 44: 解释 EIS。

EIS 代表企业信息系统（Enterprise Information System）。它存在于集成层并支持与企业相关的业务。访问 EIS 需要：

- 事务信息
- 安全信息
- 应用模型知识

## 45: EIS 和应用程序服务器的系统级合约有哪些？



## 答案

以下是 EIS 和应用程序服务器的系统级合约：

- **连接管理（Connection Management）**：允许应用和 J2EE 组件连接 EIS。这带来了可扩展的环境并支持多个客户端访问。
- **事务管理（Transaction Management）**：支持对 EIS 的事务访问。它使用事务管理器。

## 46: 解释资源适配器（Resource Adapter）

资源适配器是企业信息系统（EIS）的系统级合约。它被应用程序客户端或服务器用于连接 EIS。它与应用程序协作支持安全、事务和连接池。它位于应用程序服务器地址空间内。

## 47: 解释数据缓存

数据缓存特性如下：

- 减少应用程序所需的网络连接
- 减少应用程序所需的共享内存
- 减少数据查找时间
- 消除内存泄漏
- 确保开发环境中的缓存模拟部署或生产环境

## 48: 解释服务定位器（Service Locator）

为了访问 J2EE 内部的常用服务（如 JMS 工厂、EJB 对象、数据源等），使用了服务定位器。服务定位器使用 `Java Naming and Directory Interface (JNDI)` API，这需要初始上下文。它查找所需服务并传递交给请求者。

## 49: 解释如何防止性能问题

- 如果应用只需要本地访问，则永远不要使用 EJB 对象而使用 Java 对象。
- 如果你想在同一个 Bean 容器和虚拟机内访问另一个 Bean，请使用本地接口。
- 使用单一远程调用并合并所有数据。
- 修改不必要的变量并控制序列化。

## 50: 解释一个安全指南

安全机制目的是通过整合现有环境来支持端到端安全。这一过程被称为**身份管理（Identity Management）**。

安全通过在所有应用领域和操作系统（OS）中创建用户账户来实现。此外，安全指南还应支持授权和身份验证。

## Servlets

## 51: 解释 Servlets

Servlets 是运行在 Web 服务器上的程序。Servlet 的作用是：

- 接收/读取客户端发送的请求
- 获取请求信息并生成响应
- 格式化响应并将信息发送给客户端

Servlet 并不限于在 Web 服务器或应用程序服务器中使用，它们也可以嵌入邮件服务器和 FTP 服务器中。

## 52: 解释 Servlets 的 GET 和 POST 请求

GET 和 POST 请求分别由 `doGet()` 和 `doPost()` 方法处理。这两个方法都接受 `HttpServletRequest` 和 `HttpServletResponse` 作为参数，并抛出 `IOException` 和 `ServletException`。

```java
public void doGet(HttpServletRequest myRequest,
    HttpServletResponse myResponse) throws IOException, ServletException {
}
```

```java
public void doPost(HttpServletRequest myRequest,
    HttpServletResponse myResponse) throws IOException, ServletException {
}
```

在 GET 请求情况下，传递给服务器的所有参数在浏览器中都是可见的，但在 POST 请求情况下，参数是不可见的。

## 53: 解释 Servlet 生命周期

可以通过以下三个核心方法来解释 Servlet 生命周期：

- **`init()`**：该方法在 Web 容器加载 Servlet 时被调用。该方法只创建一次 Servlet 实例，对于随后的每个请求，实例化的线程将处理该请求。
- **`service()`**：该方法通过实例化的线程从服务器获取响应，该线程会调用 `doGet()` 或 `doPost()` 方法。
- **`destroy()`**：该方法在服务器卸载 Servlet 时被调用。

## 54: Servlet 在何处以及如何获取初始化参数？

我们可以在 `web.xml` 文件中为每个 Servlet 定义初始化参数：

```xml
<web-app>
  <servlet>
    <servlet-name>MyMessageServlet</servlet-name>
    <servlet-class>com.message.MessageServlet</servlet-class>
    <init-param>
      <param-name>city</param-name>
      <param-value>Chennai</param-value>
    </init-param>
  </servlet>
</web-app>
```

在 Servlet 中，我们可以使用 `getInitParameter("city")` 获取该值。

## 55: Servlet 如何接收 HTML 表单数据的值？

假设 HTML 表单有以下文本字段：

```html
<input type="text" name="user_name"/>
```

Servlet 可以通过以下方法接收表单值：

```java
String username = request.getParameter("user_name");
```

## 56: 假设你不知道 HTML 表单字段的名称。是否可能在不知道表单字段名称的情况下在 Servlet 中获取值？

是的。在**不知道**表单字段名称的情况下获取所有 HTML 表单字段值是可能的。

在 Servlet 中，我们可以使用 `request.getParameterNames()` 方法获取所有表单名称，然后使用 `request.getParameterValues(parameterName)` 方法逐个获取值。

## 57: 是否可以从 `doPost` 调用 `doGet`？

是的。可以从 `doPost()` 调用 `doGet()` 方法。如果 Servlet 需要同时处理 GET 和 POST 请求，就可以这样做。

根据请求类型（GET / POST），`service()` 方法调用 `doPost()` 方法，然后由其调用 `doGet()` 方法。

## 58: 解释 `init` 方法的语法

`init` 方法的语法如下所示：

```java
public void init() throws ServletException {
    // 随后的代码...
}
```

```java
public void init(ServletConfig myConfig) throws ServletException {
    super.init(myConfig);
    // 随后的代码...
}
```

因此，只有通过 `init()` 方法才能获取到配置参数。

## 59: 从 `doPost` 调用 `doGet` 方法的优点是什么？

以下是从 `doPost()` 方法中调用 `doGet()` 方法的优点：

- 默认情况下，通过 `doGet()` 方法支持 HEAD 请求。
- 默认情况下，通过 `doGet()` 方法支持 OPTIONS 请求。
- 默认情况下，通过 `doGet()` 方法支持 TRACE 请求。

## 60: 如何从 Servlet 向浏览器发送压缩后的 Web 页面？

为了发送压缩内容，我们首先必须接受下面的编码：

```java
String myEncoding = request.getHeader("Accept-Encoding");
```

然后，我们必须在浏览器中设置如下的编码：

```java
response.setHeader("Content-Encoding", "gzip");
```

这种显示压缩内容的方法可以节省大量的下载时间。

## 61: 解释状态码

对于每个 HTTP（超文本传输协议）请求，Servlet 会从服务器发送一个状态码和一条消息。状态码是一个表示服务器响应是否成功的数字。

因此，如果 Servlet 从服务器获取了响应，那么在头部中，服务器将把状态码发送为 200，消息发送为 OK。

## 62: 解释状态码 200 和 404 的含义

- 如果 Servlet 从服务器获取了响应，那么在头部中，服务器将发送状态码 **200**，消息为 **OK**。
- 如果 Servlet 不存在，服务器将设置状态码为 **404**。默认消息为 **File Not Found**。

## 63: 解释 `sendRedirect` 方法

`sendRedirect()` 方法接受一个 URL（统一资源定位符）作为参数，如下：

```java
response.sendRedirect(myURL)
```

`sendRedirect()` 方法将客户端跳转到另一个页面并设置状态码为 302。

## 64: 如果页面不存在，如何显示错误消息？

如果请求的页面不可用，服务器返回状态码 404。

例如：

```java
String myName = request.getParameter("user_name");
if (myName == null) {
    response.sendError(response.SC_NOT_FOUND, "name is null");
}
```

在上面的代码中，`sendError()` 方法用于发送参数为空的错误信息。

## 65: 设置头部的方法有哪些？

以下是用于设置头部的方法：

- **`setContentType()`**：所有 Servlet 都使用此方法设置浏览器中显示的内容类型（plain/html）。
- **`addCookie()`**：该方法用于在浏览器头部中插入 Cookie。
- **`sendRedirect()`**：当用户重定向到另一个页面时，该方法在浏览器中设置状态码为 302。

## 66: 从头部中可以获取哪些值？

以下是从头部中可以获取的值：

- **`Cookie`**：获取头部中的 Cookie 值。
- **`Content-type`**：获取浏览器中显示的内容类型。
- **`Content-length`**：获取浏览器中显示的内容长度。
- **`Cache-control`**：使用此标识浏览器内容是否被缓存。
- **`Host`**：响应来源 URL 的主机名和端口。

## 67: 解释 MIME

MIME 代表**多用途互联网邮件扩展（Multipurpose Internet Mail Extensions）**。在头部中，我们总是可以从服务器获取响应的 MIME 类型。

当服务器向浏览器/客户端发送响应时，头部默认内容类型为 `text/html`。

## 68: 解释常用的 MIME 类型

常用的 MIME 类型如下：

- **`text/html`**：用于在浏览器中作为 HTML 加载内容。
- **`image/png`**：用于在浏览器中加载 PNG 图片文件。
- **`application/pdf`**：用于在浏览器中加载 PDF 文件。
- **`video/mpeg`**：用于在浏览器中加载 MPEG 视频文件。
- **`audio/midi`**：用于在浏览器中加载 MIDI 音频文件。

## 69: 什么是 Cookie？

每当访问网页时，某些信息（文本信息，如访问者填写的表单字段值、添加到购物车的书籍等）会被存储在网络浏览器中。

这在以下场景中非常有用：如果同一个访问者再次访问页面，信息将从浏览器而不是服务器提供，从而减少服务器负载并缩短加载响应所需的时间。

## 70: Cookie 的优点有哪些？

以下是 Cookie 的优点：

- 访问者只需登录一次，随后的访问就不需要再次登录。
- 识别特定用户并显示添加到购物车的物品。
- 跟踪用户的兴趣并显示相应的广告。
- 减轻服务器负载。
- 为访问者提供更快的响应。

## 71: 如何设置和获取 Cookie？

我们可以按照如下方式添加 Cookie：

```java
Cookie myCookie = new Cookie("name", request.getParameter("name"));
response.addCookie(myCookie);
```

上述代码将在 `myCookie` 对象中添加一个 Cookie。

我们可以按照如下方式获取 Cookie：

```java
Cookie[] myCookies = request.getCookies();
Cookie myCookie = myCookies[0];
System.out.println(myCookie.getValue());
```

上述代码从 `myCookie` 对象中获取 Cookie。

## 72: Cookie 的缺点有哪些？

以下是 Cookie 的缺点：

- 在公共计算机上浏览网站时，Cookie 会存储访问者的电子邮件地址，从而允许他人发送垃圾邮件。
- 宝贵的个人信息可能被他人从 Cookie 对象中窃取。
- 信用卡详情等敏感信息保存在 Cookie 中，会导致金钱损失。

因此，不应使用 Servlet 使用 Cookie 存储敏感信息。

## 73: 跟踪访问者浏览网页的选项有哪些？

可以使用以下机制跟踪浏览网页的访问者：

- **Cookies**：可以为每个页面维护 Cookie 以跟踪访问者。
- **隐藏表单字段**：使用 `<input>` 标签，我们可以存储用户输入的值。
- **URL 重写**：在此，我们可以将用户输入的数据附加到服务器。
- **Session**：在此，我们可以将用户输入的值存储在 Session 中。

## 74: 如何从 Session 中存储和检索值？

如下所示可以将值存储在 Session 中：

```java
HttpSession mySession = request.getSession(true);
mySession.setAttribute("mobile", request.getParameter("mobile"));
```

在上述代码中，手机号存储在 Session 对象 ‘mobile’ 中。

如下所示可以从 Session 中检索值：

```java
mySession.getAttribute("mobile");
```

在上述代码中，从 Session 对象 ‘mobile’ 中检索手机号。

## 75: 解释会话跟踪（Session Tracking）

Session 跟踪是维护用户会话的一种极佳解决方案。它使用 `HttpSession` API 来查找会话对象并创建新的会话对象。

Session 跟踪用于存储客户端的上下文，因为服务器不知道客户端的信息。例如，在在线购物车中，访问者经常向购物车添加一些物品，突然由于网络问题，他与网页断开了连接。一旦网络问题解决，访问者将能够在 Session 跟踪帮助下看到添加到购物车的物品。

## 76: JSP 的目的是什么？

JSP 指 **Java Server Pages（Java 服务器页面）**。它是一种服务端编程语言，使我们能够创建静态 HTML 的同时生成动态内容。

使用 JSP，我们可以借助 JSP 对象和结构创建表示层来显示网页中的内容。JSP 受到广泛支持，它可以与任何 Web 服务器配合使用，并在不更改源代码的情况下在所有操作系统上运行。

开发者创建一个 `.jsp` 文件，当终端用户从浏览器调用它时，它会在后台转换为 Servlet。但终端用户只需查看网页中内容的 HTML 呈现即可。

## 77: 什么是 JSP 结构？

为了构建网页，JSP 使用了以下 3 种结构：

- **脚本元素（Scripting Elements）**：允许我们在 JSP 页面代码中指定 Java 代码。
- **指令（Directives）**：允许我们控制 JSP 页面的结构。
- **动作（Actions）**：允许我们在 JSP 页面中使用现有组件。

## 78: 什么是脚本元素？

脚本元素用于在 JSP 页面中插入 Java 代码。JSP 有 3 种脚本元素。它们是：

- **表达式（Expressions）**：标签 `<%= ... %>` 用于定义表达式，用于在网页中显示动态输出。
- **脚本段（Scriptlets）**：标签 `<% ... %>` 用于声明脚本段，用于定义 Java 代码，通过它我们可以包含动态内容处理。
- **声明（Declarations）**：标签 `<%! ... %>` 用于指定声明。

## 79: 什么是预定义对象？

以下是预定义对象：

- **`request`**：用于获取请求信息。
- **`response`**：用于发送响应。
- **`session`**：用于跨请求存储数据。
- **`out`**：用于向响应写入内容。

## 80: 解释会话跟踪（Session Tracking）

会话跟踪是一种用于在用户多次请求之间维持状态的机制。由于 HTTP 是无状态协议，会话跟踪允许服务器记住用户。

## 81: 如何在 JSP 中显示值？

可以使用表达式或脚本段在 JSP 中显示值：

```jsp
<%= value %>
```

## 82: JSP 中的预定义对象有哪些？

以下是预定义对象：

- **`request`**：用于获取请求数据。
- **`response`**：用于发送响应。
- **`session`**：用于管理会话数据。
- **`out`**：用于输出内容。

## 83: 解释 JSP 指令（Directives）

JSP 指令用于为 JSP 页面提供全局信息。有三种：

- **`page`**：用于定义页面特定属性。
- **`include`**：在翻译时包含文件。
- **`taglib`**：用于导入标签库。

## 84: 举例说明如何使用 page 指令

*(原文未提供具体示例代码，此处保留标题占位)*



答案：

下面的代码描述了如何使用 `page` 指令：

```jsp
<%@ page import="java.util.ArrayList" %>
<%@ page import="com.core.MyList,com.core.MyVector" %>
<%@ page contentType="text/plain" %>
```

## 85: 解释 page 指令属性：import, session, buffer 和 extends。

答案：

`page` 指令属性 `import`、`session`、`buffer` 和 `extends` 解释如下：

- a) `import`：用于导入 Java 类文件
- b) `session`：用于设置是否启用 Session
- c) `buffer`：用于设置缓冲区大小（单位为 KB）
- d) `extends`：用于声明 JSP 的父类

## 86: 解释 page 指令属性：autoflush, info, errorPage 和 isErrorPage。

答案：

`page` 指令属性 `autoflush`、`info`、`errorPage` 和 `isErrorPage` 解释如下：

- a) `autoflush`：用于指定输出是否自动刷新
- b) `info`：用于在 Java 页面中设置静态值
- c) `errorPage`：发生异常时提供错误处理页的 URL
- d) `isErrorPage`：用于设置当前页面是否作为错误页面

# 87: 页面指令（page directive）的等 XML 语法是什么？

答案：

`page` 指令可以在 XML 中声明如下：

```xml
<jsp:directive.page import="java.util.ArrayList" />
```

我们可以在 Java 页面（Java Server Pages）中使用上述代码，它是 `page` 指令的 XML 兼容语法。

# 88: 如何在 XML 语法中显示动态参数值？

答案：

在 JSP 中，我们可以通过以下代码利用 XML 语法来显示动态参数值：

```jsp
<html>
<body>
  <% String strValue = request.getParameter("myParam"); %>
  The parameter value is
  <jsp:expression>strValue</jsp:expression>
</body>
</html>
```

因此，我们使用 `<jsp:expression>` 标签在 Web 浏览器中显示动态参数值。

# 89: 请举例说明包含指令（include directive）。

答案：

`include` 指令用于在 Java 页面代码中包含一个文件。以下代码描述了如何使用 `include` 指令。

```jsp
<%@ include file="header.jsp" %>
```

在上述代码中，我们使用了 `include` 指令来包含一个文件，该文件将在运行时处理并在浏览器中显示。

# 90: 包含指令（include directive）的等 XML 语法是什么？

答案：

`include` 指令可以在 XML 中声明如下：

```xml
<jsp:include page="footer.jsp" flush="true" />
```

我们可以在 Java 页面中使用上述代码，它是 `include` 指令的 XML 兼容语法。

# 91: jsp:plugin 元素的作用是什么？

答案：

`jsp:plugin` 元素用于在 Web 页面中包含 Applet。它是 `applet` 标签的替代方案。`jsp:plugin` 元素可以如下使用：

```xml
<jsp:plugin type="applet" code="HeaderApplet.class" width="900" height="250">
</jsp:plugin>
```

在上述代码中，我们使用了四个属性：`type`、`code`、`width` 和 `height`。要显示 Applet，`type` 的值应指定为 `applet`，`code` 的值应包含 Applet 的名称。

# 92: jsp:params 元素的作用是什么？

答案：

`jsp:params` 元素用于向 Web 页面中的 Applet 传递参数值。`jsp:params` 元素可以如下使用：

```xml
<jsp:plugin type="applet" code="HeaderApplet.class" width="900" height="250">
  <jsp:params>
    <jsp:param name="MyParam1" value="MyValue1" />
    <jsp:param name="MyParam2" value="MyValue2" />
  </jsp:params>
</jsp:plugin>
```

在上述代码中，我们在 `jsp:plugin` 元素内部使用了 `jsp:params`，`jsp:param` 元素用于指定参数名称的值。

# 93: 创建 bean 类时需要考虑哪些重要点？

答案：

以下是创建 bean 类时需要考虑的重要点：

- a) bean 类应该有一个空构造函数（无参数构造函数）
- b) bean 类不应该包含公共的实例变量或字段
- c) bean 类应该有 getter 和 setter 方法来访问持久化值

# 94: 你将如何在 JSP 中包含 bean 类？

答案：

如下所示在 JSP 中包含 bean 类：

```jsp
<jsp:useBean id="service" class="com.MyService" />
```

在上述代码中，`id` 属性用于为类 `MyService` 创建一个名为 `service` 对象。上述代码也可以如下所示编写：

```jsp
<% com.MyService service = new com.MyService(); %>
```

`MyService` 类包含在脚本段（scriptlet）中，需要在 `page` 指令中导入该类。

# 95: 你将如何为 bean 类设置属性值？

答案：

如下所示在 JSP 中设置 bean 类的属性值：

```jsp
<jsp:useBean id="service" class="com.MyService" />
<jsp:setProperty name="service" property="serviceName" value="<%= request.getParameter("serviceName") %>" />
```

在上述代码中，使用了 `jsp:setProperty` 元素，它包含 `property` 属性来指定 bean 属性名称，`name` 属性应包含 bean 类的对象名称。

# 96: 你将如何在 JSP 中包含标签库（tag library）？

答案：

如下所示在 JSP 中包含标签库：

```jsp
<%@ taglib uri="servicejsp-taglib.tld" prefix="servicejsp" />
```

在上述代码中，`taglib` 指令有 2 个属性：`uri` 和 `prefix`。`uri` 包含标签库描述符文件（tag library descriptor file）的值，在该文件中我们指定了使用 `prefix` 属性中指定的值调用的类名。`prefix` 值表示包含在标签库描述符中的类对象名称。

# 97: 你将如何将一个 JSP 的内容包含另一个中？

答案：

我们必须使用 `RequestDispatcher` 类将一个 JSP 的内容包含另一个中。例如，查看以下代码：

```java
String myURL = "test.jsp";
RequestDispatcher dispatcher = request.getRequestDispatcher(myURL);
dispatcher.include(request, response);
```

# 98: 你将如何将一个 JSP 转发到另一个？

答案：

我们需要使用 `RequestDispatcher` 类。如下所示：

```java
String myURL = "test.jsp";
RequestDispatcher dispatcher = request.getRequestDispatcher(myURL);
dispatcher.forward(request, response);
```

# 99: 你将如何包含 JSP 的内容？

答案：

我们必须使用 `RequestDispatcher` 类。如下所示：

```java
String myURL = "test.jsp";
RequestDispatcher dispatcher = request.getRequestDispatcher(myURL);
dispatcher.include(request, response);
```

# 100: 你将如何包含 CSS？

答案：

如下所示：

```html
<link rel="stylesheet" href="style.css" type="text/css" />
```

## 109: 远程接口（remote interfaces）有哪些方法？

答案：

以下是远程接口的方法：

- a) `getEJBHome()`：返回会话 bean（session bean）home 接口的引用
- b) `getPrimaryKey()`：此方法返回会话 bean 的主键
- c) `getHandle()`：返回 EJB 对象的句柄（handle）
- d) `isIdentical()`：此方法测试传递的 java bean 对象与被调用的企业级 java bean 对象是否相同
- e) `remove()`：此方法移除一个 bean（会话）对象

## 110: home 接口（home interfaces）有哪些方法？

答案：

以下是 home 接口的方法：

- a) `getEJBMetaData()`：此方法允许客户端获取企业级 bean（enterprise bean）的信息
- b) `remove(Handle handle)`：移除通过句柄标识的 EJB 对象。句柄通过 `getHandle()` 方法获取
- c) `remove(Object primaryKey)`：移除通过主键标识的 EJB 对象
- d) `getHomeHandle()`：获取 home 对象的句柄。客户端使用此对象存储指向实体 bean 远程接口的引用

## 111: 本地（local）和远程（remote）接口提供哪些服务？

答案：

以下是本地和远程接口提供的服务：

- a) 返回会话对象的 home 接口
- b) 移除会话对象
- c) 委托会话 bean 实例的方法调用
- d) 测试会话对象是否与另一个会话对象相同

## 112: 解释会话 bean 如何暴露给客户端。

答案：

会话 bean 通过以下方式暴露给客户端：

- a) `EJBHome` 创建会话 bean 和 `EJBObject` 的实例
- b) `EJBObject` 提供对会话 bean 方法的访问
- c) 存根（stub）作为远程 `EJBObject` 的代理
- d) 调用调度机制由绑定类（tie class）提供，它将代理绑定到 `EJBObject`

## 113: 解释本地客户端（local client）。

答案：

会话 bean 的客户端也称为本地客户端。该本地客户端通过本地（`javax.ejb.EJBLocalObject`）和本地 home（`javax.ejb.EJBLocalHome`）接口访问会话 bean。

本地客户端位于与会话 bean 相同的 JVM 中，它们是取决于位置的。该本地客户端的对象以引用方式作为参数传递给方法。

## 114: 解释远程客户端（remote client）。

答案：

会话 bean 的客户端也称为远程客户端。该远程客户端通过远程（`javax.ejb.EJBObject`）和远程 home（`javax.ejb.EJBHome`）接口访问会话 bean。

远程客户端从基于 CORBA 的应用程序访问 EJB 容器中的会话 bean，该应用程序使用远程方法调用互联网互操作 ORB 协议（Internet Inter-ORB Protocol），这是一个非 Java 的程序。

## 115: 什么时候我们必须使用 EJB？

答案：

在以下场景中我们需要使用 EJB（企业级 Java Beans）——会话 bean 和实体 bean：

- a) 为了跨方法调用存储客户端信息，使用有状态会话 bean（stateful session bean）
- b) 持久化数据，使用实体 bean（entity bean）
- c) 向应用程序服务器或 EJB 容器通信活跃客户端的存在，使用有状态会话 bean
- d) 为了调用 EJB 容器的池化功能，使用无状态会话 bean（stateless session bean）

## 116: 如何管理 bean 的持久化。

答案：

管理 bean 持久化有两种方式。它们是：

- a) BMP（bean 管理持久化）：在这种情况下，我们编写 bean 类来管理持久化
- b) CMP（容器托管持久化）：在这种情况下，容器负责管理持久化

## 117: 解释 bean 管理持久化（BMP）。

答案：

实体 bean 实现 bean 管理持久化。在这种情况下，bean 通过直接数据库（DB）调用来存储和检索信息。

实体 bean 使用 JDBC（Java 数据库连接）或 SQL 从数据库中存储和检索信息。

## 118: 解释容器托管持久化（CMP）。

答案：

实体 bean 实现容器托管持久化。在这种情况下，容器使用标准 API 访问数据库。

容器托管持久化使得应用程序可以使用任何数据库。容器还提供了工具，将实体 bean 的实例变量映射到底层数据库（DB）的调用。

## 119: 解释你如何创建一个无状态会话 bean 的 home 接口。

答案：

无状态会话 bean 的 home 接口可以如下创建：

```java
import javax.ejb.*;
import java.rmi.*;

public interface MYSLSRemote extends EJBHome {
    public MySLSRemote create() throws RemoteException, CreateException;
}
```

此接口作为 EJB 对象的工厂。bean 代码中的 `create()` 方法对应 `ejbCreate()` 方法。

## 120: 解释你如何创建一个无状态会话 bean 的远程接口。

答案：

无状态会话 bean 的远程接口可以如下创建：

```java
import javax.ejb.*;
import java.rmi.*;

public interface MYSLSRemote extends EJBObject {
    public String getMessage() throws RemoteException;
}
```

客户端在需要调用 EJB 对象时使用此接口。该接口的责任是将后续调用委托给企业级 bean 代码。

## 121: 解释 InitialContext。

答案：

`InitialContext` 是一个充当 JNDI（Java 命名和目录接口）的类。

`InitialContext` 包含允许客户端命名服务的信息（JNDI、CORBA 和 DNS 域命名服务）。

如果调用 `InitialContext` 出现问题，将抛出 `javax.naming.NamingException`。

## 122: EJB 池化的好处是什么？

答案：

EJB 池化的好处是：

- a) 与多个用户共享资源
- b) 在部署描述符中指定池的实例
- c) 允许处理请求

## 123: 在实体 bean 和数据之间使用 DAO 的好处是什么？

答案：

在实体 bean 和数据之间使用 DAO（数据访问对象）的好处是：

- a) 编写代码（实体 bean）
- b) 迁移
- c) 它支持其他供应商
- d) 为通信提供额外层
- e) 允许跨模式和数据库

## 124: 解释 EJB 容器管理实体 bean 生命周期的作用。

答案：

EJB 容器管理实体 bean 生命周期的作用如下：

- a) 为池填充 bean 集
- b) 客户端从 home 调用 `create()` 方法

## 127: CMP 有哪些缺点？

答案：

CMP（容器托管持久化）的缺点有：

- a) 可移植性：可能会丢失其他 EJB 容器的可移植性
- b) 算法：只能使用容器支持的持久化算法
- c) 效率：考虑到性能，生成的 SQL 有时并不高效
- d) 访问：开发者无法查看

## 128: BMP 有哪些缺点？

答案：

BMP（bean 管理持久化）的缺点有：

- a) 特定数据库：由于开发了特定数据的实体 bean，如果需要访问多个数据库，bean 开发者必须重写代码
- b) SQL 知识：bean 必须具备 SQL 知识
- c) 时间：开发用于管理持久化的 bean 需要五倍的时间

## 129: 如何使用 BMP 实现持久化？

答案：

通过以下两种类型的方法可以使用 BMP 实现持久化：

- a) `ejbLoad`：此方法用于启动与企业级 java bean 容器的数据库通信
- b) `ejbStore`：此方法通过手动编码使用 JDBC API 存储数据

## 130: 解释查找方法（finder methods）。

答案：

## 你可能经常遇到的 Java / J2EE 面试题



查找方法以 `find` 为前缀，并在实体 bean 的 home 接口中创建。

例如，`findByPrimaryKey()` 是一个查找方法，用于从 home 接口通过唯一的主键对象识别实体 bean 对象。

```java
MyRemoteHome myHome = (MyRemoteHome)
javax.rmi.PortableRemoteObject.narrow(initialContext.lookup("java:obj/book"),
MYRemoteHome.class);
```

`Book book = myHome.findByPrimaryKey("91-7822-323-6");`

上面的示例演示了开发者如何使用 `findByPrimaryKey` 来检索数据。

## # 131: 实体 bean 生命周期的状态有哪些？

答案：

以下是实体 bean 生命周期的状态：

- **空状态（Null state）**：在此状态下，bean 的实例不存在
- **池状态（Pooled state）**：在此状态下，bean 的实例存在但未与任何实体 bean 对象关联
- **就绪状态（Ready state）**：在此状态下，bean 的实例与实体 bean 对象关联并具有身份标识

## # 132: 容器在实体 bean 生命周期调用了哪些方法？

答案：

在实体 bean 生命周期期间，会调用以下方法：

- **ejbActivate()**：当 bean 实例就绪并与池中的实体 bean 对象关联时，调用此方法
- **ejbLoad()**：容器使用此方法从数据源调用数据
- **ejbStore()**：该方法用于容器将数据持久化地存储在数据资源中
- **ejbRemove()**：通过此方法移除与 bean 关联的实例，由 home 接口或远程接口调用
- **ejbPassivate()**：该方法用于 EJB 容器将 bean 实例从 EJB 对象解关联并发送到池中

## # 133: 实体 bean（entity beans）的用途是什么？

答案：

以下是实体 bean 的用途：

- a) 对具有唯一身份的对象进行建模，这些对象被多个客户端共享
- b) 强制数据完整性和持久化
- c) 对数据源中的记录建模，而不是与客户端保持会话
- d) 用于 BMP（Bean 管理持久化）或 CMP（容器托管持久化）
- e) 缓存数据从而重用数据并防止频繁的数据库连接

## # 134: 部署描述符（deployment descriptor）中指定了哪些元素？

答案：

部署描述符指定了以下元素：

- a) **session**：将 bean 定义为 session bean 而不是实体 bean
- b) **session-type**：我们可以将 session 定义为无状态或有状态
- c) **enterprise-beans**：通过此项，我们可以将 bean 声明为 session bean 或实体 bean
- d) **ejb-name**：用于指定 session 或实体 bean 的唯一名称
- e) **ejb-jar**：这是部署描述符的根元素
- f) **ejb-class**：用于指定企业 bean 类
- g) **home**：用于指定企业 bean 的接口
- h) **remote**：用于指定企业 bean 的远程接口
- i) **transaction-type**：用于指定事务是由 EJB 容器执行还是企业 bean 执行的。

## # 135: 解释如何为有状态的 session bean（stateful session bean）创建 home 接口。

答案：

我们可以如下所示为有状态的 session bean 创建 home 接口：

```java
import java.rmi.*;
import javax.ejb.*;

public interface MySFSSRemoteHome extends EJBHome {
    public MySFSSRemote create(int i) throws RemoteException, CreateRemoteException;
}
```

home 接口中的 `create()` 方法对应于 bean 代码中的 `ejbCreate()` 方法。

## # 136: 解释如何为有状态的 session bean（stateful session bean）创建远程接口（remote interface）。

答案：

我们可以如下所示为有状态的 session bean 创建远程接口：

```java
import java.rmi.*;
import javax.ejb.*;

public interface MySFSSRemote extends EJBObject {
    public int size() throws RemoteException;
}
```

## 你可能经常遇到的 Java / J2EE 面试题

有状态 session bean 的远程接口用于客户端调用 bean 实例上的方法。

## # 137: 解释如何创建有状态的 session bean（stateful session bean）。

答案：

我们可以如下所示创建有状态的 session bean：

```java
import java.rmi.*;
import javax.ejb.*;

public class MySFSBean implements SessionBean {
    private SessionContext context;
    private int iCount;

    public void ejbCreate() {}
    public void ejbActivate() {}
    public void ejbPassivate() {}
    public void ejbRemove() {}
    public void create(int iParam) {
        this.iCount = iParam;
    }
    public int size() {
        return iCount;
    }
}
```

在上述代码中，有状态的 session bean是由 EJB 容器创建的。

## # 138: 什么是访问方法（accessor methods）？

答案：

访问方法用于获取或设置 bean 的值。例如：

- `getName()`
- `setName(String name)`

## # 139: 解释实体（Entity）。

答案：

实体是一个表示数据库表中的行数据的对象。它具有唯一标识并由 EJB 容器持久化。实体 bean 通过 `EntityContext` 访问数据。

## # 140: 解释 getJBHome、getJBLocalHome 和 getCallerPrincipal。

答案：

- `getJBHome()`：企业 bean 的远程接口。
- `getJBLocalHome()`：企业 bean 的本地接口。
- `getCallerPrincipal()`：识别调用 bean 实例。

## # 141: 解释 getRollBack、setRollBack 和 getUserTransaction。

答案：

- `getRollBack()`：使用此方法标识现有事务是否已回滚。
- `setRollBack()`：使用此方法将特定事务的 bean 实例设置为回滚。
- `getUserTransaction()`：此方法不应由实体 bean 调用，因为它返回 `javax.transaction.UserTransaction`

## # 142: 解释事务（Transaction）。

答案：

事务是一个执行单个原子操作的任务。如果任务执行失败，事务将撤销或回滚。事务通常被称为 ACID。ACID 指原子性、一致性、隔离性和持久性。

## # 143: 容器托管事务可用哪些属性？

答案：

以下是容器托管事务的属性：

- a) **Required（需要）**：在此情况下，如果事务不存在，容器将启动新事务。
- b) **RequiresNew（需要新建）**：在此情况下，容器为每次方法调用创建一个新事务。
- c) **Supports（支持）**：在此情况下，bean 可以在无事务执行。
- d) **NotSupported（不支持）**：在此情况下，bean 不能在事务中被调用。
- e) **Never（从不）**：在此情况下，bean 永远不会执行事务。
- f) **Mandatory（强制）**：在此情况下，每次方法调用都要求有事务上下文。

## # 144: 容器如何管理多个事务？

答案：

EJB 容器通过以下两种方式管理多个事务：

- a) EJB 容器实例化企业 bean，允许数据库处理任何与事务处理相关的问题。
- b) EJB 容器对企业 bean 实例的状态状态获取排斥锁，从而实现多个事务对实例访问的序列化。

## # 145: 解释 JTS。

答案：

JTS 指 Java 事务服务（Java Transaction Service）。它规范了 Java 事务接口（API）的管理器实现。它支持分布式事务，即由多个事务管理器支持跨系统的多个数据库。通过 JTS，容器确保事务可以跨越多个容器。

## # 146: EJB 容器提供哪些服务？

答案：

EJB 容器提供以下服务：

- a) 事务管理：容器管理事务的启动、加入、回滚和提交
- b) 生命周期管理：它包括 bean 的创建、销毁、激活和惰性化
- c) 持久化：bean 不显式地从数据库检索或存储数据，而是通过容器的帮助完成
- d) 状态管理：容器自动管理 bean 对象的状态
- e) 远程访问（分布式）：容器通过 RMI 和 IIOP 协议支持分布式的远程访问
- f) 安全性：容器代表企业级豆（enterprise beans）自动执行所有安全检查

## # 147: EJB 框架作为架构的优点是什么？

答案：

以下是 EJB 框架作为架构的优点：

- a) EJB 架构是分布式的、可扩展的、可移植的、事务的多层次且安全的
- b) EJB 服务器自动为企业级 bean 组件管理线程、生命周期、事务和持久化等服务
- c) 企业级 bean 组件与平台无关，即它们可以在任何操作系统上执行
- d) EJB 组件仅包含业务逻辑；因此开发者被允许自由维护系统级代码

## # 148: 解释 session bean 的生命周期。

答案：

session bean 的生命周期可以描述如下：

- a) 使用 JNDI（Java 命名目录接口）服务，客户端调用 bean 的本地对象（home object）
- b) 本地引用用于创建 EJBObject，从而创建 bean 类的实例
- c) 调用 session bean 的 bean 类被分配一个会话上下文（session context）
- d) 本地引用用于调用 EJB Object 的方法，并将方法调用传递给 session bean
- e) session bean 然后将结果返回给 EJBObject，再由其将其返回给远程接口

## # 149: 抽象持久化模式（abstract persistence schema）包含哪些信息？

答案：

抽象持久化模式包含以下信息：

- a) 为了管理每个实体 bean，它有一个 `ejb-name` 字段，其值必须是唯一的
- b) 为了指定查询，每个实体 bean 使用 `abstract-schema-name`，其值必须是唯一的
- c) 可以使用 `ejb-relation` 字段指定 ejb 的关系
- d) 为了指定关系角色，我们必须使用 `ejb-relationship-role` 字段

## # 150: EJB 客户端有哪些类型？

答案：

企业 Java Bean 客户端有两种类型。它们是：

- a) 本地客户端（Home client）：本地客户端始终存在企业 java bean 容器内部
- b) 远程客户端（Remote client）：远程客户端始终存在企业 java bean 容器外部

可以通过事务管理器从多个客户端访问企业 java bean 容器中的企业 bean 对象。

# 国际化与本地化（Internationalization and Localization）

## # 151: 什么是国际化？

答案：

国际化是制作或准备代码以支持多种语言的过程。国际化既涉及向客户端呈现输出的应用程序，也涉及可以转换为相应语言和字符集的数据。因此，国际化允许应用程序适应新的语言和区域。

## # 152: 什么是本地化？

答案：

本地化是对支持特定语言或区域的国际化应用程序进行适配。本地化涉及将数据翻译成特定语言并将其维护在文件中，以便应用程序访问。该文件可以是一个属性文件（property file）。因此，本地化提供了国际化应用程序对特定国家或区域的适配。

## # 153: 什么是 locale（区域）？

答案：

Locale 是包含特定区域和信息的环境。在本地化过程中，国际化应用程序被适配到特定的 locale。每个国家都有自己的 locale。例如，美国有 `en_US`，意大利有 `it_IT` 等。在这里，`en` 代表“语言”。在这里，`it` 代表语言意大利语，而 `IT` 代表“区域差异”，即国家名称意大利。

## # 154: 国际化应用程序的特征是什么？

答案：

以下是国际化应用程序的特征：

- a) 应用程序将有一个 `.ear` 文件（企业归档文件），可以在范围内执行
- b) 图形用户界面标签和消息不是硬编码在程序中的，而是动态检索的
- c) 为了支持新语言，不需要重新编译

## # 155: 识别 locale 的元素有哪些？

答案：

locale 通过以下标识识别：

- 语言（Language）：它是语言。例如，`en` 代表英语
- 区域差异（Regional Variation）：它是国家名称，例如 `US` 代表美国
- 变体（Variant）：它是变体。例如，`FR` 代表法国
- 系统（System）：它是系统。例如，`WIN` 代表 Windows

## # 156: 可以使用 java.util.Properties 进行本地化吗？

答案：

我们可以使用 `java.util.Properties` 进行本地化。例如：

```java
Properties appProp = new Properties();
String strProp = "Properties.txt";
appProp.load(new FileInputStream(strProp));
String serviceValue = appProp.getProperty("key");
```

## # 157: 解释 ResourceBundle。

答案：

`ResourceBundle` 是属于 `java.util` 的一个类。它定义了组织特定区域资源的命名规范。

## # 158: ResourceBundle 的特征有哪些？

答案：

`ResourceBundle` 具有以下特征：

- a) 内容可以翻译成不同的语言
- b) 让应用程序同时处理多个 locale
- c) 可以应用程序以支持额外的 locale

## # 159: 解释字符集（Character Sets）。

答案：

字符集是一组图形或文本符号，映射到正整数，称为代码点（code points）。美国信息交换标准（ASCII）字符集用于英语。它包含大小写字母、标点符号。例如，B 的 ASCII 代码是 66。ASCII 仅适用于英语。

## # 160: 解释 Unicode。

答案：

Unicode 定义了一个通用标准的（ISO10646）字符集。它代表了全世界使用的字符集，并且可以扩展。因此，Unicode 是 ISO 8859 字符集的替代。Java 使用 Unicode 2.x 进行编码。每个 Unicode 字符使用 2 个字节。Java 将 String 对象表示为编码后的 Unicode。

## # 161: 解释 UTF。

答案：

UTF 代表 Unicode 转换格式。是一种编码格式，以 1 字节、2 字节和 3 字节存储字符。在这里 U 也代表通用字符（UCS）。UTF-8 比 Unicode 更紧凑、高效，是广泛使用的编码方案。Java 推荐 UTF-8，因为它与现有网页内容兼容并提供了对 Unicode 字符集的访问。

## # 162: 解释 Collation（排序）和 Collator（排序器）。

答案：

Collation 是一种根据特定区域习俗对字符串进行排序的过程。不同语言的字母不同，我们需要一种独特的方法按语言排序字符串。Collator 是属于 `java.text` 包的抽象类。它用于提供区域敏感的字符串比较，从而实现 Collation 过程。

## # 163: JSP 中使用哪些属性来控制编码？

答案：

在 JSP 中，有两个属性用于页面指令（page directive）来控制编码。它们是：

- contentType：在其中，我们可以指定我们将使用的字符集和内容的格式

```jsp
<%@ page contentType="text/html; charset=ISO-8859-1" %>
```

在上面的行代码中，我们使用了内容的 html 格式和 ISO-8859 字符集。

- b) pageEncoding: 在此处，我们可以指定将用于字符显示的字符集。

```jsp
<%@ pageEncoding="UTF-8" %>
```

在上面的行代码中，我们使用了 UTF-8 类型的编码。

## # 164: 解释 Format 类。

答案：

Format 是一个属于 `java.text` 包的类。它是一个抽象类，用于格式化本地（locale）信息：例如消息、日期和数字。

Format 类使用 `format()` 方法：

- a) 将本地对象格式化为字符串，以及
- b) 使用 `parseObject()` 将字符串转换为对象



## 165: 如果需要部署在不同的本地（locales）中，应用程序的哪些方面需要进行更改？

答案：

如果需要部署在不同的本地，以下是需要更改的方面：

- a) 内容、数字和日期的呈现
- b) 组件上的标签
- c) 颜色、声音和图像
- d) 页面显示数据的排序（Collation）
- e) 读写文本文件内容

## 166: Java 支持哪些字体名称和字体样式？

答案：

Java 支持的 5 种字体名称是：`Serif`、`Sans-serif`、`Monospaced`、`Dialog` 和 `DialogInput`。

Java 支持的 4 种字体样式是：`bold`（粗体）、`italic`（斜体）、`plain`（常规）和 `bolditalic`（粗斜体）。这些是映射到操作系统默认安装的物理字体的标准名称。字体名称和样式的映射由 `font.properties` 处理。

## 167: Java 用于创建国际化应用的特性有哪些？

答案：

以下是用于创建国际化应用的 Java 特性：

- a) `java.util.Properties` 类用于获取特定文本（键）的本地值
- b) `java.util.Collator` 和 `CollatorKey` 类用于根据本地单词对数据排序
- c) `java.text.NumberFormat` 和 `DateFormat` 类用于格式化货币、数字和日期
- d) `java.io.InputStreamReader` 和 `OutputStreamWriter` 用于读写文件
- e) `contentType`、`pageEncoding` 和 `java.util.Locale` 属性用于 JSP 中
- f) `java.util.ResourceBundle` 类用于处理本地化文本

## 168: Format 类的子类有哪些？

答案：

`java.text.Format` 有三个子类。它们是：

- a) `java.text.NumberFormat`：用于格式化货币和数字
- b) `java.text.DateFormat`：用于格式化时间和日期
- c) `java.text.MessageFormat`：用于格式化文本消息

## 169: 解释为什么 UTF-8 被认为是最佳的编码选择？

答案：

UTF-8 被认为是最佳编码选择的原因如下：

- a) 它被几乎所有可用的网络浏览器支持
- b) 它提供了最广泛的字符集覆盖范围
- c) 它提供了高效的数据传输

## 170: 本地化（localizing）JSP 页面的方法有哪些？

本地化 JSP 页面有两种方法。它们是：

- 为每个本地（locale）创建一个 JSP 文件，并将其存储在服务器上不同的目录中。根据客户端请求的本地，调用相应的 JSP 来显示相应的本地化内容。
- 创建一个单一的 JSP 并使用具有本地特定自定义标签的 `ResourceBundle`。这样，当客户端请求页面时，标签会从对应本地的资源包中访问文本。

## 171: 为每个本地（locale）分别创建 JSP 的优势是什么？

以下是为每个本地创建 JSP 的优势：

- **定制化支持**：这为每个本地的内容结构和显示的定制化提供了完全支持。
- **源文件清晰性**：每个本地的所有属性文件、资源包和 JSP 均保存在一个目录中。

## 172: 解释 I18N 和 L10N。

I18N 代表国际化（Internationalization），其中 'I' 表示首字母，18 代表首字母和尾字母 'N' 之间的 18 个字符。

L10N 代表本地化（Localization），其中 'L' 表示首字母，10 代表首字母和尾字母 'N' 之间的 10 个字符。

## 173: 解释 InputStreamReader。

`InputStreamReader` 是一个属于 `java.io` 包的类。它用于将字节流转换为字符，即它读取字节并根据提供的编码将其转换为字符。`InputStreamReader` 类接受 `String` 类型的编码参数并将字节转换为字符。我们可以通过使用 `getEncoding()` 方法识别 `InputStream` 类使用的编码类型。

## 174: 解释 OutputStreamWriter。

答案：

`OutputStreamWriter` 是一个属于 `java.io` 包的类。它用于将数据从字符转换为字节流，即它根据提供的字符编码转换字符。`write()` 方法调用编码转换器来转换可用的字符。

## 175: 使用 ResourceBundle 的优势和缺点是什么？

答案：

以下是使用 `ResourceBundle` 的优势：

- **定制化支持**：这为每个本地的内容结构和显示定制化提供了完全支持。
- **源文件清晰性**：每个本地的所有属性文件、资源包和 JSP 均保存在一个目录中。

以下是使用 `ResourceBundle` 的缺点：

- **难以定制**：定制页面非常困难。
- **兼容性**：页面必须兼容。

## 176: 什么是设计模式（Design Patterns）？

答案：

设计模式是为特定问题提供解决方案的程序。它还确保对象使用的始终是同一个实例。

## 177: 解释 GoF。

答案：

GoF 指“四人帮”（Gang of Four）。它指的是四位作者：Ralph Johnson、Richard Helm、John Vliss 和 Erich Gamma，他们编写了《设计模式：可复用对象的要素》一书并于1995年出版。从那时设计模式变得流行。

## 178: 设计模式的类型有哪些？

答案：

设计模式有三种。它们是：

- 创建型设计模式（Creational Design Pattern）：用于创建对象。
- 结构型设计模式（Structural Design Pattern）：与对象和类的组合有关。
- 行为设计模式（Behavioral Design Pattern）：与对象的职责和交互有关。

## 179: 各种创建型设计模式有哪些？

答案：

以下是创建型设计模式：

- a) 工厂方法（Factory Method）：它是最常用的模式。
- b) 抽象工厂（Abstract Factory）：该模式用于创建一组多个类型的对象。
- c) 构建器（Builder）：这是另一种创建对象的方法，类似于工厂和抽象工厂。
- d) 单例（Singleton）：这是开发者经常使用的最重要模式之一。
- e) 原型（Prototype）：该模式等同于克隆。

## 180: 解释单例（Singleton）。

答案：

单例模式的意图是确保一个类只有一个实例，并且它是全局访问点。它还确保使用单例实例的对象始终使用同一个单一实例。

```java
final public class Singleton {
    private Singleton() {
    }
}
```

上面的代码说明了如何创建一个单例类。

## 181: 解释工厂方法（Factory Method）。

答案：

工厂方法的意图是指定一个创建对象的接口，但允许子类来决定要实例化的具体类。

在这种模式中，客户端永远无法知道具体的类被实例化并返回。但客户端只需要知道抽象接口。与工厂方法（Factory Method）模式相关的接口和类有：

- a) `javax.ejb.EJBHome`
- b) `javax.ejb.EJBLocalHome`
- c) `java.text.Collator`
- d) `java.net.SocketFactory`
- e) `java.net.ContentHandlerFactoryFactory`

点 a) 和 b) 属于 J2EE，其余属于 J2SE。

## 183: 解释原型模式（Prototype pattern）。

答案：

原型模式的意图是使用原型实例定义要创建的对象类型，并通过复制该原型来创建新对象。这个概念与 `java.lang.Object` 的 `clone()` 方法相同。该模式允许我们在运行时删除或添加对象。它还允许我们通过修改现有结构来定义新对象，并减少对子类的类的需求。该模式还允许我们以抽象的方式配置应用程序。

## 184: 在什么场景下创建抽象工厂模式（Abstract Factory pattern）？

答案：

在以下场景下必须创建抽象工厂模式：

- a) 当提议的系统需要独立，并且不想知道对象是如何表示、创建和组合的时
- b) 当相关对象旨在通过强制约束来一起使用时
- c) 当我们只想为用户提供接口而不提供其实现时

## 185: 各种结构性设计模式有哪些？

答案：

以下是各种结构性设计模式：

- a) 装饰器模式（Decorator pattern）：该模式被认为是策略模式的“外壳”
- b) 组合模式（Composite pattern）：该模式与迭代器（Iterator）和解释器（Interpreter）一起使用
- c) 代理模式（Proxy pattern）：该模式用于受控的访问
- d) 适配器模式（Adapter pattern）：该模式用于访问不兼容的接口
- e) 桥接模式（Bridge pattern）：该模式用于将主功能与实现解耦
- f) 享量模式（Flyweight pattern）：该模式允许人们高效地利用对象

## 186: 解释代理模式（Proxy pattern）。

答案：

代理模式为对象提供一个占位符，以控制对另一个对象的访问。常见的应用是虚拟代理和远程代理。代理（Surrogate）是代理模式的另一个名称。在这种模式中，应用程序存在于另一个工作空间，但远程代理隐藏了这一事实。虚拟代理可以根据需要创建对象。

## 187: 门面模式（Facade pattern）的好处有哪些？

答案：

以下是门面模式的益处：

- a) 为复杂的子系统提供简单的接口，且不会减少子系统的选项
- b) 它可以保护客户端不受子系统组件复杂性的影响
- c) 促进客户端与子系统之间的松耦合
- d) 每个子系统使用自己的门面模式，从而减少了子系统之间的耦合

## 188: 在什么场景下创建适配器模式（Adapter pattern）？

我们在以下场景中使用或创建适配器模式：

- 针对一个与没有兼容接口的类协作的可重用类
- 对象没有兼容的接口，但它想使用现有的类
- 我们不想使用接口，但想使用现有的子类

## 189: 解释组合模式（composite pattern）。

组合模式的意图是允许客户端执行不代表层次结构的对象。这种场景通常出现在门户应用程序中。该模式定义了包含复杂对象和原始对象的类层次结构。这使得添加新组件变得更容易。该模式还提供了一个可以管理的接口，提供了一个灵活的结构。

## 190: 装饰器模式（Decorator pattern）的好处有哪些？

以下是装饰器模式的益处：

- 与静态继承相比，该模式提供了更大的灵活性
- 帮助开发者简化代码和目标类，通过开发功能来实现，而无需编写所有行为
- 在此模式中，更改是通过编写新类来完成的，这增强了扩展性特征

## 191: 各种行为性设计模式（behavioral design patterns）有哪些？

以下是各种行为性设计模式：

- a) 策略模式（Strategy）：这是最频繁使用的模式之一
- b) 迭代器（Iterator）：该模式解释了如何循环遍历对象
- c) 模板方法（Template Method）：该模式帮助我们巩固对工厂方法和策略模式的理解
- d) 中介者模式（Mediator）：该模式作为中间层组件起作用
- e) 观察者模式（Observer）：该模式是一种发布/订阅模型
- f) 责任链模式（Chain of Responsibility）：该模式用于以链的形式传递消息
- g) 备忘录（Memento）：该模式用于恢复和备份对象的状态
- h) 命令模式（Command）：该模式将调用者与执行者分离
- i) 状态模式（State）：在此模式中，对象改变其类并修改其行为
- j) 访问者模式（Visitor）：在此模式中，对象在元素的结构上操作
- k) 解释器模式（Interpreter）：在此模式中，使用语法来解释句子

## 192: 解释策略模式（Strategy pattern）。

答案：

策略模式的意图是创建一个功能族，将其封装起来并将它们创建为可交换的整体。在这里，功能独立于使用它的客户端。策略（Policy）是策略模式的另一个名称。该模式为子类化提供了替代。该模式通过在其类内部定义行为，消除了条件语句。

## 193: 中介者模式（Mediator pattern）的好处有哪些？

答案：

以下是中介者模式的益处：

- a) 提供集中式控制
- b) 独立的对象
- c) 组件变得更容易开发
- d) 该模式解耦了其他组件

## 194: 什么时候使用迭代器模式（Iterator pattern）？

答案：

我们在以下场景下必须使用迭代器模式：

- 访问集合不需要知道内部结构
- 当我们需要支持多次遍历时
- 当我们需要一个通用的接口来遍历时

## 195: 解释解释器模式（Interpreter pattern）。

答案：

解释器模式的意图是使用解释器定义语言的语法，解释器用于解释句子。

使用这种模式，很容易扩展和更改语法。该模式用于对效率要求较高的场景。

## 196: 与命令模式（Command pattern）相关的 J2EE 特性有哪些？

答案：

以下是与命令模式相关的两个 J2EE 特性：

- 根据容器（web）接收到的 HTTP（超文本传输）请求类型，调用 JSP 或 Servlet
- 根据分发到 Message beans 的消息内容，由这些 beans 调用业务逻辑

## 197: 什么时候使用访问者模式（Visitor pattern）？

答案：

访问者模式用于以下场景：

- 在对象类具有不同接口的许多对象上执行操作
- 执行无关且独立的操作
- 避免类被无关的操作所污染
- 定义新操作但对象的结构很少变化

## 198: 解释模板方法（Template Method）。

答案：

模板方法模式的意图是定义函数的骨架并将步骤留给子类。这让子类能够在不修改函数结构的情况下重新定义函数。这是由 `HttpServlet` 实现的。该模式提供了一种重用代码和避免重复的技术。如果我们想在子类中使用变算法而在一个类中使用不变算法，那么必须使用这种模式。

## 199: 解释责任链（Chain of Responsibility）。

答案：

该模式的意图是避免将发送者的请求与由多个对象的接收者集成。请求以链的形式传递，直到对象处理请求。该模式在职责分配给对象时减少了耦合并提高了灵活性。它还允许一组类表现得像一个类。当请求需要由多个对象处理且处理器未知且请求是动态的时，我们使用这种模式。

## 200: 备忘录（Memento）和状态（State）模式的好处有哪些？

答案：

以下是备忘录模式的益处：

- a) 该模式保护了封装对象的边界
- b) 该模式简化了原始对象（originator）

以下是状态模式的优点：

- a) 对象的状态是局部的，并且每个状态都对行为进行了划分
- b) 对象的状态转换总是显式的

# 消息传递

## 201: 什么是消息？

答案：

## 202: 解释中间层。

答案：

中间层由称为中间件的应用程序组成，提供以下服务和业务解决方案：

- a) **消息传递**：接收和发送数据的能力
- b) **安全性**：对用户进行授权身份验证的能力
- c) **命名**：通过名称识别资源的能力
- d) **数据库管理**：访问数据库（DB）服务器的能力

## 203: 解释 MOM。

答案：

MOM 指的是面向消息的中间件（Message Oriented Middleware），主要用于消息传递。它是允许应用程序在企业内部接收、发送和创建消息的基础设施。

MOM 通常以不同的格式快速地交换和交付消息。MOM 的优势是它是事件驱动的。有多种消息传递供应商：例如：HP、IBM、BEA、Oracle 等。

## 204: 解释同步通信。

答案：

同步通信是一种通信方法，其中发出请求的客户端在请求者收到响应之前会被阻塞，无法处理任何后续命令。

这种通信发生在双方之间：客户端（浏览器）和服务器。这种通信的一个例子是信用卡授权。在这里，一旦刷了卡，接收方将等待服务器对交易进行批准的响应。

## 205: 解释异步通信。

答案：

异步通信是一种通信方法，其中发出请求的客户端永远不会被阻塞，他/她可以继续处理其他进程或事务。异步通信的一个例子是电子邮件。即使你关闭了电脑，人们也可以向你发送电子邮件。一旦你启动电脑，邮件客户端就会加载你的消息。

## 206: 解释 JMS。

答案：

JMS 指的是 Java 消息服务（Java Messaging Service）。它是一种允许软件开发人员实现应用程序松耦合的中间件。它提供了一个 API（应用程序编程接口），通过该 API 我们可以接收、发送、读取和创建企业系统消息。JMS 是一种面向消息的产品，相当昂贵且复杂。它提供了一个接口（Java）来编写基础设施代码，并允许轻松快速地构建解决方案。

## 207: JMS 支持哪些消息模型？

答案：

Java 消息服务支持两种类型的消息模型。它们是：

- a) 发布/订阅（Publish/subscribe）：在此模型中，客户端可以发布消息或订阅任何类型的消息
- b) PTP：PTP 指点对点模型，其中消息是基于一对一发送的

JMS 规范要求消息供应商必须支持上述模型中的任何一个以符合规范。

## 208: 同步消息传递的优点是什么？

答案：

以下是同步消息传递的优点：

- a) 同步消息传递要求双方（客户端和服务器）处于激活状态。如果其中一方未激活，事务将无法成功



- b) 在继续下一个操作或过程之前，必须确认消息。如果没有确认，则消息不被视为已处理

## 209: 异步消息传递的优点是什么？

答案：

以下是异步消息传递的优点：

- a) 这种类型的传递不受故障的影响很大，因为它不需要或期望确认
- b) 这种类型的消息不受软件、硬件或网络层的影响
- c) 通常情况下，消息不会丢失，但可能会延迟
- d) 如果流量增加，这种消息传递效果更好，因为它将请求积压留在队列中

## 210: 在什么场景下采用异步消息传递？

答案：

以下是我们采用异步消息传递的场景：

- a) 如果我们不需要立即响应
- b) 如果我们需要高容量的事务处理能力
- c) 如果我们想要一个高效的消息系统来使用硬件系统

## 211: JMS 的优势是什么？

答案：

以下是 Java 消息服务的优点：

- a) 它提供了一种轻松集成不兼容系统的方法
- b) 它支持异步通信方法
- c) 它提供对一种或多种类型通信的支持
- d) 它提供对事务类型消息的支持
- e) 它提供对保证类型消息的支持

## 212: JMS 的组件有哪些？

答案：

以下是 JMS 的组件：

- a) **消息（Messages）**：指应用程序之间传递的数据，定义了消息所包含的信息类型
- b) **客户端（Clients）**：指可以接收和发送消息的应用程序
- c) **对象（Objects）**：指由管理员维护和创建、供 JMS 客户端使用的 JMS 对象
- d) **JMS 提供者（JMS Provider）**：指运行 JMS 应用程序的主机应用程序。它提供了消息应用程序所需的底层设备

## 213: JMS 中如何处理异常？

答案：

JMS 使用 `ExceptionListener` 接口，如果在执行或运行时发生任何问题，将通过该接口通知应用程序。此接口识别 JMS 提供者的问题详情并与 JMS 客户端进行通信。

要处理异常，我们必须使用接受参数的 `onError` 方法。

## 214: JMS 中如何确认消息？

答案：

JMS 通过以下方式确认消息：

- **CLIENT_ACKNOWLEDGE（客户端确认）**：由客户端确认消息
- **DUPS_OK_ACKNOWLEDGE（重复检查确认）**：如果 JMS 提供者失败，则会发生消息重复
- **AUTO_ACKNOWLEDGE（自动确认）**：在这种情况下，会话（session）确认客户端

## 215: 解释 JMS 的消息头。

答案：

JMS 使用以下消息头：

- **MessageID（消息 ID）**：用于唯一标识每条消息
- **Priority（优先级）**：9 为最高，0 为最低。不能保证高优先级消息先于低优先级消息执行
- **DeliveryMode（交付模式）**：此消息头用于定义 JMS 为持久性（Persistent）或非持久性（Non-persistent）
- **Redelivered（重发）**：用于通知客户端他/她之前接收过该消息
- **Expiration（过期时间）**：用于以毫秒设置消息

## 216: JMS 的主体格式有哪些？

答案：

以下是 JMS 的正文格式：

- **TextMessage（文本消息）**：格式为字符串，用于交换 XML 数据
- **ByteMessage（字节消息）**：用于匹配旧版消息
- **ObjectMessage（对象消息）**：表示对象集合或单个可序列化对象
- **MapMessage（映射消息）**：类似于 HashMap，具有键值对
- **StreamMessage（流式消息）**：表示用于顺序读取的原始值流

## 217: JMS 中的管理对象有哪些类型？

答案：

在 JMS 中，有两种类型的管理对象。它们分别关于

- a) Destination（目的地）：包含由 JMS 供应商提供的配置信息。目的地在 PTP中使用队列（queue），在发布/订阅中使用主题（Topic）
- b) ConnectionFactory（连接工厂）：通过 JNDI 查找提供到 Java 消息服务的物理连接。它包含 IP 地址并允许 JMS 创建连接

## 218: JMS 中哪些对象用于接收和创建消息？

答案：

以下对象以下用于接收和创建消息：

- a) MessageConsumer（消息消费者）：用于接收发送到目的地的消息
- b) MessageProducer（消息生产者）：用于创建发送到目的地的消息
- c) MessageSelector（消息选择器）：用于过滤符合指定标准的消息
- d) MessageListener（消息监听器）：用于异步处理和接收消息

## 219: 解释消息消费者（Message Consumer）。

答案：

MessageConsumer 用于向特定的目的地同步或异步接收消息，该目的地由会话对象创建。

同步通信的情况下，消费者调用 `receiveNoWait` 等任意方法；在异步通信的情况下，客户端注册 `MessageListener` 并启动消费者。

Java Messaging Service 中的几乎所有消息都在客户端之间以异步方式交换，生产者永远不会收到接收者的确认。

## 220: 解释消息生产者（Message Producer）。

答案：

MessageProducer 用于通过 PTP 或发布/订阅（pub/sub）发送消息。在 PTP（点对点）模型中，目标称为队列（queue），在发布/订阅模型中，目标称为主题（Topic）。

在生产者中，我们可以使用 `setDeliveryMode` 方法将投送模式设置为非持久化（NON-PERSISTENT）或持久化（PERSISTENT）。非持久化模式的开销较小，因为消息不会记录在服务器或数据库中。

我们还可以使用 `setPriority` 设置消息优先级。0 表示低优先级，9 表示高优先级。我们还可以使用 `setTimeToLive` 以毫秒为单位指定消息的寿命。

## 221: 解释消息选择器（Message Selector）。

答案：

MessageSelector 属于 String 对象，用于过滤不符合特定标准的消息。

消息选择器可以检查头部并比较 String 中存在的表达式。表达式示例包括算术运算符、关系运算符、字符串字面量和逻辑运算符。

## 222: 解释消息监听器（Message Listener）。

答案：

为了异步处理消息，我们必须实例化 `MessageListener` 接口。我们需要执行以下步骤来异步处理和接收消息：

- a) 创建实现 `MessageListener` 接口的对象并调用 `onMessage` 方法
- b) 使用 `setMessageListener` 方法在 Java / J2EE 面会话对象中注册
- c) 使用 `Connection` 对象的 `start` 方法开始接收消息

## 223: PTP 通信需要哪些类、接口和步骤？

答案：

以下是点对点（Point-To-Point）通信所需的类、接口和步骤：

- a) 使用 JNDI（Java 命名目录接口）查找 `QueueConnectionFactory` 对象。JNDI 名称根据消息供应商而异
- b) 通过 `QueueConnectionFactory` 对象获取 `QueueConnection` 对象。如果启用了安全性，必须提供用户名和密码
- c) 通过 `QueueConnection` 获取带有提供者的 `QueueSession`
- d) 通过 JNDI 查找获取队列（queue）
- e) 通过 `QueueConnection` 创建用于接收和发送消息的 `QueueSession`、`QueueReceiver` 或 `QueueSender`
- f) 关闭 `QueueConnection`，这将关闭 `QueueReceiver`、`QueueSender` 和 `QueueSession`

## 224: Pub/Sub 通信需要哪些类、接口和步骤？

答案：

以下是发布/订阅（Pub/Sub）通信所需的类、接口和步骤：

- a) 使用 JNDI（Java 命名目录接口）查找 `TopicConnectionFactory` 对象。JNDI 名称根据消息供应商而异
- b) 通过 `TopicConnectionFactory` 对象获取 `TopicConnection` 对象。如果启用了安全性，必须提供用户名和密码
- c) 通过 `TopicConnection` 获取带有提供者的 `TopicSession`
- d) 通过 JNDI 查找获取队列（queue）
- e) 通过 `TopicSession` 创建用于订阅和发布消息的 `TopicSubscriber` 或 `TopicPublisher`
- f) 关闭 `TopicConnection`，这将关闭 `TopicSubscriber`、`TopicPublisher` 和 `TopicSession`

## 225: 解释 MDB。

答案：MDB 指消息驱动豆（Message Driven Bean）。每当消息到达目标（队列或主题）时，容器（EJB）就会部署该组件（无状态）。

MDB 是一个接收消息的消费者，因为它实现了 `javax.jms.MessageListener` 接口。与 Java Messaging Service 类似，消息驱动豆以相同的方式接收消息。

在 MDB 的情况下，Enterprise Java Bean 容器确保每当发送消息时，该豆都注册在特定的目标中。

# 安全与遗留连接

## 226: 企业资源面临着哪些各种安全威胁？

答案：

以下是企业资源面临的安全威胁：

- a) 机密信息泄露：无意或有意地让没有法律权利的人获取信息
- b) 信息修改：无意或有意地修改数据
- c) 责任制受破坏：这被称为身份盗用
- d) 受保护资源的滥用：这被称为服务盗用
- e) 影响可用性的滥用：数据修改导致企业系统中断

## 227: 解释身份验证（Authentication）和授权（Authorization）。

答案：

身份验证是验证许可进入安全场域或网站的用户凭据的过程。例如，只有注册用户才有权登录提供邮件服务的网站。授权是验证许可访问或接收请求资源的用户角色的过程。例如，用户无法修改文档，因为他没有该角色或未被授权修改特定文档。

## 228: 解释 Java 中提供的某些安全包。

答案：

以下是 Java 中提供的安全包：

- a) `java.security`：这包含用于安全、身份验证和授权（访问控制）的类和接口
- b) `java.security.interfaces`：包含用于加密的接口：数字签名算法 (DSA) 和 Rivest、Shamir、Adleman 非对称密码算法 (RSA)
- c) `java.security.cer`：包含用于管理和解析证书的接口和类
- d) `java.security.spec`：包含用于 DSA、RSA 和证书的规范接口和类

## 229: Java 安全管理器在 Applets 中执行了哪些操作？

答案：以下是 Java 安全管理器在 applet 中执行的操作操作：

- a) 删除文件、写入文件和读取文件
- b) 修改线程的属性（例如：优先级）
- c) 更新或访问系统属性
- d) 接受、等待或打开套接字或网络连接

## 230: Java Applets 有哪些安全限制？

答案：以下是 Java applet 的安全限制：

- a) applet 不允许定义本地方法或加载库，但可以使用自己的代码
- b) 它无法在主机上写入或读取文件
- c) 网络连接仅适用于下载的主机
- d) 它无法启动程序
- e) 限制读取系统属性

## 231: Applet 能读取哪些系统属性？

答案：以下是 applet 限制读取的系统属性：

- a) `user.name`：指用户名
- b) `user.home`：指用户目录
- c) `user.dir`：指当前工作目录
- d) `java.home`：指 Java 安装目录
- e) `java.class.path`：指 Java 的类路径

## 232: 访问控制的策略有哪些？

答案：以下是可能的访问控制策略：

- a) 一旦用户通过身份验证，调用的所有进程都会继承访问权限
- b) 一旦组件通过身份验证，上下文对所有其他可信组件可用
- c) 当组件准备好伪装调用者时，由调用者对被调用组件进行身份验证

## 233: J2EE 支持哪些身份验证机制？

答案：J2EE 容器支持以下身份验证机制：

- a) HTTP basic：包含参数的 URL 请求
- b) HTTP digest：包含加密参数的 URL 请求
- c) FORM based：使用用户名和密码进行验证
- d) HTTPS mutual：允许执行安全事务

## 234: 解释加密通信。

答案：数据可以通过称为密码学（Cryptography）的机制进行加密。在该机制中，数据使用匹配的密钥进行加密和解密。加密有两种类型：

- 对称：在这种情况下，接收者和发送者都拥有相同的解密和加密消息的密钥
- 非对称：这被称为公钥加密，密钥被分为公钥和私钥。每个密钥都有解密由另一个用户加密数据的能力

## 235: 解释数字证书（Digital Certificates）。

答案：数字证书是为私钥持有者的一种著名解决方案，用于将公钥放在名为数字证书的包中，并使用受信任机构 CA（证书授权）的私钥进行签名。数字证书解决了接收方对公钥不可信的问题。VeriSign 是颁发数字证书的领导者，CA 受全球信任且广众所周知。VeriSign 的公钥随浏览器和 Web 服务器分发。

## 236: 解释安全套接层 (SSL)。

答案：

安全套接层（SSL）是一种确保访问互联网隐私性的协议。这些协议有助于应用程序相互通信，从而防止窃听。安全套接层提供服务器认证、数据加密和消息完整性保障。在 SSL 中，所有数据都经过加密后跨网络进行传输。它使用端口 443 在服务器之间传输消息。它还使用服务器和双向认证模式来传输消息。

## 237: Web 容器执行哪些安全检查？

答案：

Web 容器执行以下安全检查：

- a) 确保对请求进行解密
- b) 确保请求中是否存在任何授权约束
- c) 确保请求包含授权或认证要求
- d) 应用程序资源受认证和授权约束的组合保护

## 238: 解释使用 Java 的遗留连接 (legacy connectivity)。

答案：

遗留连接方法基于使用两层架构的客户端-服务器模型。它不基于 Web，并使用企业信息系统（EIS）来检索和处理数据。企业信息系统有一个提供 API（应用程序编程接口）来处理和访问数据以及 EIS 功能。客户端通过编程方式使用 API 连接并访问 EIS。

企业信息系统适配器的关键在于可重用性。独立厂商使用具有高度可用性和重用性的编程语言开发适配器。

## 239: 解释 EIS 中的认证。

答案：

为了访问企业信息系统的信息，J2EE 组件需要遵循一套单独的安全程序。信息存在于保护域中，因此企业信息系统层运行在独立的环境中。在这种情况下，容器尝试调用 J2EE 组件认证来获取资源。这种机制被称为容器托管资源管理器签名（container managed resource manager sign）。

## 240: 解释 CSI。

答案：

CSI 指通用安全互操作性协议（Common Secure Interoperability Protocol）。企业 Java Bean 容器支持此协议，该协议属于对象管理组（OMG）。CSI v2 是通过 IIOP 进行安全调用的标准。IIOP 指互联网 ORB 协议（Internet Inter-ORB Protocol）。它是身份断言机制，该功能处理中间实体。

## 241: 解释 EIS 适配器。

答案：

企业信息系统有一个适配器提供 API（应用程序编程接口）来处理和访问数据以及 EIS 功能。客户端通过编程方式使用 API 连接并访问 EIS。

企业信息系统适配器的关键在于可重用性。独立厂商使用具有高度可用性和重用性的编程语言开发适配器。

## 242: 解释使用 J2EE 连接器的遗留连接。

答案：

开发者使用 JDBC（Java 数据库连接）CCI 来访问数据，而不是使用适配器方法，因为后者非常耗时。Java 连接器架构（Java Connector Architecture）几乎受到了所有最新的 WebLogic 和 WebSphere 服务器的支持。

通过使用 Java 连接器架构（JCA），企业信息系统服务（EIS）厂商无需为每个应用程序服务器定制适配器。此外，应用程序服务器无需添加代码来连接到企业信息系统（EIS）。

## 243: 解释资源适配器 (Resource Adapter)。

答案：

资源适配器指的是 `javax.resource.spi` 和 `javax.resource.cci` 包中接口的实现。当你访问一个使用原生库访问企业信息系统的资源时，需要在系统级引入软件库。

资源适配器默认实现了连接器系统的企业信息系统适配器，其中包含了安全和事务管理。

资源适配器在客户端层也有用于访问 EIS 应用程序的 API。它也被用于服务器（应用程序）环境中。

## 244: 解释系统契约 (System contract)。

答案：

系统契约定义为双方之间支持协作和互利互交互的协议。例如，EIS 和服务器（应用程序）协作支持连接管理、安全和事务等机制。使用系统契约，组件提供者专注于应用程序的展示和业务逻辑开发。通过这种方式，我们从提供者那里获得一组执行业务任务的功能。

## 245: 解释 JCA 的集成策略。

答案：

如今开发者的主要工作是将新系统与旧系统集成。集成可以通过以下方式进行：

- a) 入站集成技术（Inbound Integration Technique）：在这种情况下，请求由外部系统向我们的系统发起



- b) 出站集成技术（Outbound Integration Technique）：在这种情况下，请求由我们的系统向其他系统发起

# 246: 系统契约的类型有哪些？

答案：

有三种系统契约。它们是：

- a) 安全管理：这允许服务器（应用程序）使用安全相关属性连接到 EIS
- b) 事务管理：这允许事务从服务器（应用程序）传播到 EIS
- c) 连接管理：描述了容器（J2EE）与适配器之间建立连接池和销毁连接的协议

# 247: 配置安全属性的方法有哪些？

答案：

以下是配置安全属性的方法：

- a) 主体映射（Principal mapping）：用于在服务器（应用程序）中连接或组合 EIS
- b) 配置身份（Configured Identity）：在这种情况下，资源适配器在连接到 EIS 时使用身份连接
- c) 凭据映射（Credentials mapping）：在这种情况下，服务器和 EIS 的凭据进行映射
- d) 调用者冒充（Caller Impersonation）：EIS 中使用的此主体与应用程序服务器匹配

# 248: CCI API 哪些部分？

答案：

CCI 指的是通用客户端接口（Common Client Interface）。CCI API 包含四个部分：

- a) 连接接口（Connection Interface）：创建到企业信息系统的连接
- b) 交互接口（Interaction Interface）：在 EIS 上执行命令称为交互接口
- c) 集接口（ResultSet Interface）：封装 EIS 的查询结果
- d) 元数据接口（Metadata Interface）：检查 EIS 元数据

# 249: 解释 ManagedConnectionFactory 和 ManagedConnection。

答案：

`ManagedConnectionFactory` 是一个接口，由 `UCConnectionFactory` 类（服务器调用适配器的入口）实现，该类创建 `UCConnectionFactory` 和 `UCManagedConnection` 类。

`ManagedConnection` 是一个接口，由 `UCManagedConnection` 类实现。该类封装了适配器连接类 `UCConnection`。

`ManagedConnectionFactory` 和 `ManagedConnection` 都用于 JCA（Java 连接器架构）适配器。

# 250: 数据库完整性约束的缺点有哪些？

答案：

数据库完整性约束的缺点如下：

- a) 逻辑重复：当数据库完整性规则更改时，可能会出现逻辑重复，需要修改业务逻辑代码
- b) DBMS 约束不可迁移性：使用过程化触发器通常会导致不可迁移性，因为每个厂商遵循自己的标准
- c) 未受控的数据库配置：由于约束存在于服务器（J2EE）之外，配置是在数据库工具中完成的

# 人力资源问题

回顾这些典型的面试问题，并思考你将如何回答它们。阅读列出的答案；你将找到最佳答案，以及相关的策略和建议。

## 1：你从什么地方汲取灵感？

回答：

灵感可以来自任何地方，面试官希望看到你的灵感同样是多元的。提到获取灵感的多个来源，或者你发现自己进行头脑风暴的环境。此外，详细说明你是如何记录灵感或稍后对其进行扩展的。

## 2：你如何在工作中表现出创造力？

回答：

向面试官证明你能够在工作中善于资源且具有创新精神，同时不超出公司价值观的底线，是非常重要的。解释你的灵感通常源自何处（例如可以包括列清单或思维导图等练习），并将其与工作中某项需要创造力的特定任务联系起来。

## 3：你如何促使他人产生创意？

回答：

如果你处于管理岗位，这可能要求员工提交特定数量的创意，或者完成定期的灵感激发练习，以锻炼你的创造力。然而，你也可以通过创造更多自己的创意来促使周围的人。此外，与面试官讨论“提问”作为激发灵感和改变方式的重要性。

## 4：描述一下你的创造力。

回答：

尽量将此答案控制在专业领域，但如果你在职业经历之外的某些创意领域拥有令人印象深刻的背景，不要害怕将其包含在答案中。关于创造力的最佳答案将与解决问题的能力、目标设定，以及在工作中寻找创新方法处理项目或完成销售联系起来。然而，办公室之外的热情也是棒的（只要它们不会占用你的工作时间或精神空间）。

## 5：你更倾向于在工作中获得更多的权力还是更多的责任？

回答：

这两个选项各有优缺点，面试官会更感兴趣地看到你能够对这个问题提供一个批判性的回答。获得更多权力可能意味着更大的决策权，对于具有卓越领导能力的人来说可能非常棒；而更大的责任对于那些寻求在职业生涯中稳步发展的人来说是一个绝佳的机会。

## 6：当小组中的有人没有做出应有的贡献时，你会怎么办？

回答：

如果你面试的是管理职位，这个问题尤为重要——解释你识别问题的方法，以及你将如何找该个人进行单独谈来讨论他们的贡献。理解建立对话的过程很重要，以便向该个人清晰地传达你的期望，给他们机会回应，并明确哪些需要改变。之后，与该小组成员制定一个行动计划，确保他们的贡献与小组内的其他人持平。

## 7：请告诉我一次你做过超出权限范围的决策经历。

回答：

虽然对这个问题的回答可能表现出你非常果断和自信，但也可能让雇主认为你是一个潜在的问题员工。相反，最好的办法是将问题重新聚焦于你承担了额外责任的例子，因此你不得不做出超出正常权限（但在特定情况下已授予你权限）的决策。讨论决策的权重如何影响了你的决策过程，以及该情况的结果。

## 8：你乐意向主管反映纠纷吗？

回答：

如果出现问题，雇主希望知道你会以及时且恰当的方式处理它。强调你过去很少与主管发生纠纷，但如果发生此类情况，你觉得完全乐意与相关人员讨论它，以找到令双方都满意的解决方案。

## 9：如果你在上一份工作中担任负责人，你会做什么不同的改变？

回答：

无论你对事情如何运行得更好有多少想法，或者对你之前工作的管理层有多少意见，在回答这个问题时都要保持积极态度。对如何处理某事以提高效率或提高销量进行深思熟虑的反思是可以的，但确保你所有的建议都集中在让事情变得更好，而不是通过谈论他人来消除浪费或负面情绪。

## 10：你认为雇主应该对工作表现良好的员工给予表扬和奖励吗？

回答：

在完成艰巨任务后获得认可总是很棒的，但有很多雇主可能会通过问这个问题来推断你是否是一个高维护成本的员工。虽然你可能感激奖励或表扬，但向面试官传达这样一点是重要的：你不需要赞誉来确信自己工作良好。如果你正在面试一个由你负责表扬其他员工的管理职位，请强调表扬对提高团队士气的重要性。

## 11：你认为领导者具备最重要的特质是什么？

回答：

在任何业务中，领导者都需要许多重要的技能，而这个问题的核心部分在于你解释为什么你选择强调的这种特质是重要的。尝试选择诸如沟通技巧或激励他人的能力，并将其与你在团队中展示该特质的特定实例联系起来。

## 12：请告诉我一次发生不可预见问题的经历。你是如何处理的？

回答：

在压力下保持善于利用资源和冷静是非常重要的。面试官希望看到你如何系统化地处理问题。清晰地概述情况，包括解决方案和结果。

## 13：你能否给我举一个例子，说明你在上一份工作中能够改进某个目标？

回答：

这里的重点应该放在你为公司创造了切实成果的改进上。提高效率无疑是一个重要因素，但雇主也在寻找诸如销售额增加或开支减少的具体结果。详细解释你的过程，尽可能提供具体的数字。

## 14：请告诉我一次主管没有为项目提供足够指导的经历。

回答：

虽然许多雇主希望员工遵循特定的指南而没有太决策权，但能够在模糊的指导下启动项目并独立完成也是重要的。给出你提问的例子，并说明你是如何判断某个问题是需要询问主管的，还是你可以自己决定的。

## 15：请告诉我一次你负责领导一个项目的经历。

回答：

向面试官介绍项目的整个过程，就像你对任何团队成员做的那样。解释项目的目标、必要的步骤，以及你是如何分配任务的。包括结果，以及由于这次领导机会你学到了什么。

## 16：请告诉我你向前雇主提出的一个后来被实施的建议。

回答：

雇主希望看到你对改进公司和做出自己的贡献感兴趣——提供一个你在之前的工作中创造积极变化的具体例子。解释你是如何想到这个主意的，你的主管是如何接收的，以及其他员工对想法实施的看法。

## 17：请告诉我一次你发现工作中某事可以更高效地执行的方法。

回答：

关注你想法的积极方面。重要的是不要负面地评价你的旧公司或老板，不要详细阐述某个系统有多么低效。相反，解释你看到提高生产力或简化流程的机会，并用通用的步骤解释你是如何实施更好的系统的。

## 18：你认为领导和管理人员之间是否存在区别——你的哪个优势更大？

回答：

两者之间是有区别的——领导通常是主意的天才，充满热情、富有魅力，并具备组织和激励他能力；而经理是那些确保系统运行、促进运营、做出权威决策，并对整体成功的各个方面（甚至是最微的决策）承担巨大责任的人。考虑其中哪一点最适用于该职位，并解释你如何胜任这一角色，提供你过去经验的具体案例。

## 19：你是在领导角色中工作得更好，还是作为团队成员工作得更好？

回答：

考虑面试官在你的职位上看重什么样的特质，并表达你如何体现这一角色是非常重要的。如果你是一个领导者，要突出你的优秀想法、动力和激情，以及激励周围其他人行动的能力。如果你在团队工作中表现出色，请关注你对当前任务的投入、你的合作与沟通能力，以及保持事情顺畅运行的能力。

## 20：请告诉我有一次你在工作中发现某些影响了你（或他人）生产力问题的经历——你是如何处理的？

回答：

尽量不要过多关注之前工作的负面方面，而是选择一个你发现积极且快速解决方案来提高生产力的案例。重点描述你是如何注意到这个机会的、如何向主管提出解决方案的，以及该改变是如何实施的（最重要的是，谈谈你是如何领导这项变革倡议的）。这是你展示解决问题能力、机智多谋的特质以及领导能力的绝佳机会。

## 21：在目标和任务明确的工作中，你的表现如何？

回答：

在回答这个问题时，考虑该职位本身是非常重要的——显然，如果你能够在一个目标和任务明确的工作中脱颖而出，那是最好的（特别是如果你处于初级职位或销售职位）。然而，如果你申请的是具有领导角色或需要创意资产职能的职位，请务必关注你额外喜欢开发和实施自己想法时所面临的挑战。

## 22：在一个让你拥有巨大决策权的工作中，你的表现如何？

回答：

面试官想知道，如果被录用，你不会是那种需要不断监督，或者每一步都索要建议、授权或反馈的员工类型。解释你在果断、高效的环境中工作得良好，并且你期待在你的职位上采取主动。

## 23：如果你看到其他员工有任何不诚实或违背道德的行为，你会做什么？

回答：

在目击其他员工有不诚实行为的情况下，最好的方式始终是根据公司政策采取行动——如果你不知道该公司的具体政策，可以直说你将根据政策进行处理，并向相关的负责人汇报。如果你了解公司的政策（例如，如果你正在自己的公司内部寻求晋升），那么最好根据政策具体列出你的行动方案。

## 24：请告诉我一次你自学了某些知识，这些知识在日后帮助了你的职业生涯的经历。

回答：

这个问题很重要，因为它让面试官能够洞察你对学习和进取的奉献程度。仅从你的个人生活中选择一个例子，并提供一个简短的小故事，说明你学到的教训。然后，清楚、详尽地解释这一教训是如何转化为你在工作中可用的技能或实践的。

## 25：请告诉我一次你在工作中开发出一个项目想法的经历。

回答：

选择一个你开发的项目想法，该想法应与你在新职位中可能完成的项目具有典型性。概述你的想法来自哪里、你为了确保其成功和相关性做了什么样的研究、项目中包含哪些步骤以及最终结果。提供具体的改进前后数据，以展示你的成功。

## 26：请告诉你一次在项目中承担风险的经历。

回答：

无论这种风险涉及的是像在资源或时间有限的情况下承担重大项目等复杂的事情，还是仅仅自愿承担一项超出你经验领域的任务，都要表现出你愿意走出舒适区并尝试新事物。提供具体的例子说明你所做的某事为什么具有风险性，并解释你在过程中学到了什么——这如何为你日后在职业生涯中面临的工作目标做好了准备。

## 27：对于想要进入这个领域的人，你会告诉他们什么？

回答：

这个问题让你成为专家——并将向面试官展示你拥有知识和经验，可以与简历上的任何培训和教育相呼应。提供你的知识作为对进入该领域的人可能遇到的意外情况的建议，并务必以积极的建议结束，例如真正取得成功所需的对工作的激情或奉献。

## 28：请告诉你一次没能赶上截止日的经历。

回答：

理想情况下，这种情况没有发生过——如果发生过，请确保你使用一个小例子来说明情况，强调那是多久以前的事了，并确保你已经尽了所能确保遵守截止日。此外，务必包括你在更好地管理时间或对任务进行优先级排序方面学到了什么，以满足未来的所有截止日。

## 29：你在工作时如何消除干扰？

回答：

随着技术的进步和沟通的便利性增加，新的干扰每天都会产生。你的面试官将希望看到你仍然专注于工作，以及你采用了什么样的例行方法来保持任务状态。

## 30：请告诉你一次在有周标准或月标准的职位上工作的经历。你成功的频率有多高？

回答：

你的数据将说明一切，你必须诚实地回答这个问题。如果你经常达成指标，请务必以自信的方式强调这一点。如果你的数据并不理想，尝试指出你在就业结束期间的增长趋势。

或者消除不必要的工作。引导面试官进入一个通用场景，并通过你组织和设定优先顺序的能力展示你的胜任能力，最重要的是保持冷静。

## 35: 请谈谈你个人的解决问题过程。

回答：

你的个人解决问题过程应该包括：概述问题、提出可能的解决办法，以及制定一个通向解决方案的清晰行动计划。保持你的回答简明且逻辑清晰，并用简洁、冷静的方式解释这些步骤，显示出即使在压力下也能保持头脑。

## 36: 工作中哪些事情会让你感到压力？

回答：

由于最好远离负面因素，请保持这个回答简短且简单。虽然回答“工作中没有任何事会让你感到压力”对面试官来说可能不太可信，但请将答案保持在一个通用的原则上，例如当团队成员没有履行承诺时，然后关注你通常用来应对压力的解决方案，例如召开每周状态会议或在项目过程中设置间歇性截止日期。

## 37: 当你对某事感到压力时看起来是什么样的？你是如何解决的？

回答：

这是一个陷阱题——面试官想听到的是，当你压力大时你的看起来并没有任何变化，而且你不会让负面情绪干扰你的工作效率。至于你如何解决压力，最好是你掌握了一了一种简单的解决方案，比如通过深呼吸并数到10来让自己回到当前任务中。

## 38: 你能多任务处理吗？

回答：

有些人人可以，有些人则不行。多任务处理最重要的部分是始终保持清醒，清楚做什么以及每个任务的优先级是什么。解释你是如何评估任务以确定优先级的，以及你如何管理时间以确保所有任务都能高效完成。

## 39: 你每周工作多少小时？

回答：

很多人会被这个问题骗，认为工作时间越长越好——然而，这可能会让雇主怀疑为什么你需要花费那么长时间才能完成别人可以在更短时间内完成的工作。对完成一项工作所需的时间给出一个合理的估计，并解释你在任何需要时也愿意额外工作。

## 40: 你每天检查几次邮件？

回答：

虽然雇主希望看到你紧跟现代技术，但你每天检查邮件的次数相对较低也是重要的——可能每天二到三次（取决于你所处的具体领域）。检查邮件通常是工作场所中非常分心的事情，虽然保持联系很重要，但很多信件完全可以在早上和下午统一处理。

## 41: 描述一次你向同事传达困难或复杂想法的经历。

回答：

首先向面试官简要地解释这个词这个想法，然后概述为什么需要向同事进一步拆解它。最后，用简洁的步骤解释这个想法，让面试官能够看到你的沟通能力和化化复杂的技巧。

## 42: 你觉得在什么情况下沟通比较困难？

回答：

即使是优秀的沟通者通常也会发现某些特定情况更难进行有效沟通，因此不要害怕诚实地回答这个问题。务必解释为什么你所提到的那个特定情况对你来说很困难，并尝试选择一个不寻常的答案，例如语言障碍或困难时期，而不是像与权威人士说话这种情况。

## 43: 良好沟通的关键要素是什么？

回答：

良好沟通的某些要素包括：免受干扰的环境、听者的反馈，以及说话者在必要时进行的修订或澄清。在需要时参考基本的沟通模型，并提议与面试官进行角色扮演演示以展示你的技能。

## 44: 请谈谈一次你通过沟通解决问题的经历。

回答：

在商业世界中通过沟通解决问题是关键，因此请从你之前的工作选择一个特定的情况，在其中你通过在冲突中有效沟通处理了复杂的局面。解释情况的基础，以及你采取的沟通步骤，并讨论为什么通过沟通解决问题对最终结果如此重要。

## 45: 请谈谈一次你与另一员工发生争议的经历。你是如何解决该情况的？

回答：

确保使用一个具体的案例，并逐步解释场景、你做了什么来处理它，以及最终是如何解决的。中间步骤，即你如何处理争议，显然是最关键的——描述你使用的沟通类型，以及你如何通过妥协达成共识。冲突解决是任何员工都应该具备的重要技能，也是面试官寻找的技能，以判断你卷入纠纷的概率，以及如果发生纠纷，他们被迫卷其中的概率有多大。

## 46: 你与人建立关系得很快，还是需要更多时间来了解他们？

回答：

这两个选项任何一个都可以展示良好的品质，因此确定哪种风格更适合你。强调你在建立关系过程中采取的步骤而非特定的风格，并简要总结为什么这种方法对你有效。

## 47: 描述一次你必须通过办公室政治来解决问题的经历。

回答：

尝试在这个问题中关注积极方面，这样你就可以利用该情况转化为优势。不要负面地描述你之前的雇主，而是使用一个极小的实例（例如文书工作或某个特定个人）来突出你是如何巧妙处理的。给出你为了达成结果而使用的沟通技能示例。

## 48: 请谈谈一次你说服他人承担艰巨任务的经历。

回答：

这个问题是一个展示你领导力和沟通技巧的机会。虽然特定情况本身作为背景很重要，但重点放在你是如何说服他人的以及哪些策略最有效。

## 49: 请谈谈一次你成功说服群体接受你的建议的经历。

回答：

这个问题旨在衡量你的应变能力和沟通技巧。解释你是如何考虑到群体的不同观点的，并创造出一个对所有成员都有吸引力和说服力的方案。此外，你还可以通过提供细节来增加建议本身的权重，展示它是如何执行得良好的。

## 50: 请谈谈一次你与他人发生过问题的经历，从事后看来，你希望换一种方式处理。

回答：



这个问题的关键在于展示你的反思能力和学习过程。解释情况、你当时是如何处理的、结果如何，最后你现在会如何处理。最重要的是，告诉面试官你之前的解决方案给那人的关系带来了什么压力，或者你是否希望当时能更坚定地维护自己的主张？虽然你不应该详述你之前处理得有多糟糕，但最重要的是展示你由于这次冲突获得了成长并达到了更深层次的理解。

## 51: 请谈谈一次你调解员工之间冲突的经历。

回答：

对于应聘主管职位的人来说，这是一个特别重要的问题——从特定情况开始，并解释你是如何与每个人进行有效沟通的。例如，你是否引入了妥协？你是否做出了行政决策？或者你是否作为调解员并鼓励员工自行得出结论？

最后，祝你好运！

# 目录

# Java / J2EE 面试题

# 架构与协议

- 1: J2EE 架构的设计目标是什么？
- 2: J2EE 架构师的角色是什么？
- 3: 架构和设计有什么区别？
- 4: 架构分析中执行了哪些活动？
- 5: 架构设计中执行了哪些活动？
- 6: 面向对象设计中有哪些活动？
- 7: 多层架构的组件有哪些？
- 8: 多层客户端服务器架构的优点是什么？
- 9: Bean 开发者的责任是什么？
- 10: 应用组装器的责任是什么？
- 11: 第三方部署器的责任是什么？
- 12: 第三方软件在 EJB 框架中的作用是什么？
- 13: 解释 MVC 架构。
- 14: 解释 EAR、WAR 和 JAR。
- 15: 解释 JTA、JNDI 和 JMS。
- 16: 解释 EDI。
- 17: 解释 EAI。
- 18: 在 Java 中支持 XML 的意图是什么？
- 19: 业务层和用户界面之间通信使用了哪些协议？
- 20: HTTP 协议的优缺点是什么？
- 21: 解释 JRMP。
- 22: CORBA 的优缺点是什么？
- 23: 解释 DCOM。
- 24: 解释 J2EE 架构的能力。
- 25: 解释系统架构和参考架构。

## 适用性与最佳实践

- 26: 解释最佳实践。
- 27: 解释 J2EE 的层。
- 28: 表现层应该遵循哪些最佳实践？
- 29: MVC 中使用了什么类型的组件？
- 30: J2EE 系统在全球经济中运行必须满足什么要求？
- 31: DAO 中应该遵循哪些最佳实践？
- 32: 解释指南。
- 33: VO 中应该遵循哪些最佳实践？
- 34: Session Bean 门面中应该遵循哪些最佳实践？
- 35: 模型视图控制器有什么好处？
- 36: MVC 有哪些设计上的问题？
- 37: 解释 MVC 的适用性。
- 38: 解释模式在 J2EE 框架中的性。
- 39: 解释框架模式。
- 40: 部署器的活动有哪些？
- 41: 属于集成层模式有哪些？
- 42: 解释表现层模式。
- 43: 解释业务层模式。
- 44: 解释 EIS。
- 45: EIS 和应用服务器的系统级控制有哪些？
- 46: 解释资源适配器。
- 47: 解释数据缓存。
- 48: 解释服务定位器。
- 49: 解释如何防止性能问题。
- 50: 解释安全指南。

## Servlets

- 51: 解释 Servlets。
- 52: 解释 Servlets 的 GET 和 POST 请求。
- 53: 解释 Servlet 的生命周期。
- 54: Servlet 在哪里以及如何获取初始化参数？
- 55: Servlet 如何接收 html 表单数据的值？
- 56: 假设你不知道 html 表单字段的名称。可以在不知道表单名称的情况下在 Servlet 中获取值吗？
- 57: 是否可以从 doPost 中调用 doGet？
- 58: 解释 init 方法的语法。
- 59: 从 doPost 中调用 doGet 方法有什么优点？
- 60: 如何从 Servlet 向浏览器发送压缩的网页？
- 61: 解释状态码。
- 62: 解释状态码 200 和 404 的含义。
- 63: 解释 sendRedirect 方法。
- 64: 如果特定页面或 Servlet 不可用，我们如何如何显示错误信息？
- 65: 用于设置标头值的方法有哪些？
- 66: 从标头中可以检索哪些值？
- 67: 解释 MIME。
- 68: 解释最常用的 MIME 类型。
- 69: 什么是 Cookie？
- 70: Cookie 的优点是什么？
- 71: 如何设置和获取 cookie？
- 72: 跟踪访问者浏览网页的选项有哪些？
- 73: 如何从 session 中存储和检索值？
- 74: 解释会话跟踪。

## JSP

- 76: JSP 的目的是什么？
- 77: 什么是 JSP 构造？
- 78: 什么是脚本元素？
- 79: 最常用的 JSP 对象有哪些？
- 80: 如何在 JSP 中获取参数值？
- 81: 如何在 JSP 中显示动态参数值？
- 82: 除了 request、session 和 out 之外，还有哪些预定义的 JSP 对象？
- 83: 解释 JSP 指令。
- 84: 举例说明如何使用 page 指令。
- 85: 解释 page 指令属性：import, session, buffer, 和 extends。
- 86: 解释 page 指令属性：autoflush, info, errorPage, 和 isErrorPage。
- 87: page 指令的对应 XML 语法是什么？
- 88: 如何在 XML 语法中显示动态参数值？
- 89: 举例说明 'include' 指令。
- 90: include 指令的对应 XML 语法是什么？
- 91: jsp:plugin 元素的作用是什么？
- 92: jsp:tag 的作用是什么？
- 93: 创建 bean 时有哪些重要点？
- 94: 你将如何包含一个 bean？
- 95: bean 的属性有哪些？
- 96: 你将如何包含一个 tag？
- 97: 将如何包含另一个页面？
- 98: 将如何转发请求？
- 99: page 的属性有哪些？
- 100: JSP 的好处是什么？

## EJB

- 101: EJB 的特征是什么？
- 102: EJB 有哪些属性？
- 103: 解释 EJB。
- 104: 解释 EJB。
- 105: 什么是描述符？
- 106: 什么是 bean？
- 107: 解释上下文。
- 108: EJB 有哪些类型？
- 109: EJB 有哪些方法？
- 110: EJB 有哪些接口？
- 111: EJB 提供了哪些服务？
- 112: session 如何暴露给客户端？
- 113: 解释本地。
- 114: 解释远程。
- 115: 什么时候我们使用 EJB？
- 116: 如何管理持久化？
- 117: 解释容器持久化。
- 118: 解释容器持久化。
- 119: 如何为 stateless bean 创建 ？
- 120: 如何为 stateless bean 创建远程接口？
- 121: InitialContext。
- 122: 容器对 EJB 有什么好处？
- 123: 什么是实体持久化？
- 124: 容器如何管理实体生命周期？
- 125: CMP 有什么好处？
- 126: BMP 有什么好处？
- 127: CMP 的缺点有哪些？
- 128: BMP 的缺点有哪些？
- 129: 如何使用 BMP 实现？
- 130: 解释查找方法。
- 131: 实体生命周期有哪些？
- 132: 容器调用了哪些方法？
- 133: 实体的用途有哪些？
- 134: 部署描述符中有哪些内容？
- 135: 如何为 stateful bean 创建 home 接口？
- 136: 如何为 stateful bean 创建远程接口？
- 137: 如何创建一个 stateful 类？
- 138: 访问器方法有哪些？
- 139: 解释实体上下文。
- 140: 解释 EJBHome、EJBLocal 和 getPrincipal。
- 141: 解释 RollBack、setRollBack 和 getUserTransaction。
- 142: 解释事务。
- 143: 容器管理的事务属性有哪些？
- 144: 容器如何管理多个事务？
- 145: 解释 JTS。
- 146: EJB 容器提供了哪些服务？
- 147: 作为架构的 EJB 框架？
- 148: session bean 的生命周期。
- 149: 抽象持久化方案包含什么信息？
- 150: EJB 客户端的类型？

## 国际化与本地化

- 151: 什么是国际化？
- 152: 什么是本地化？
- 153: 什么是区域？
- 154: 国际化应用程序具有哪些特征？
- 155: 通过哪些元素可以识别区域？
- 156: 是否可以使用 java.util 包进行本地化？
- 157: 解释 ResourceBundle。
- 158: ResourceBundle 有哪些功能？
- 159: 解释字符集。
- 160: 解释 Unicode。
- 161: 解释 UTF。
- 162: 解释排序和比较器。
- 163: JSP 中用于控制编码的属性有哪些哪些？
- 164: 解释 Format 类。
- 165: 如果要部署在不同的区域，应用程序的哪些方面需要变化？
- 167: 用于创建国际化应用的 Java 特性有哪些？
- 168: Format 类的子类有哪些？
- 169: 解释为什么 UTF-8 被认为是最好的编码选择。
- 170: JSP 页面本地化的方法有哪些？
- 171: 为每个语言区域创建 JSP 的优点是什么？
- 172: 解释 I18N 和 L10N。
- 173: 解释 InputStreamReader。
- 174: 解释 OutputStreamWriter。
- 175: 在 JSP 中使用 ResourceBundle 的优缺点分别是什么？

# 设计模式

- 176: 什么是设计模式？
- 177: 设计模式有什么处？
- 178: 解释 GoF。
- 179: 设计模式的哪些类型？
- 180: 各种创建型设计模式有哪些？
- 181: 解释单例模式。
- 182: 解释工厂方法模式。
- 183: 解释原型模式。
- 184: 在什么场景下你会创建抽象工厂模式？
- 185: 各种结构型设计模式有哪些？
- 186: 解释代理模式。
- 187: 门面模式有什么处？
- 188: 在什么场景下你会创建适配器模式？
- 189: 解释组合模式。
- 190: 装饰器模式有什么处？
- 191: 各种行为型设计模式有哪些？
- 192: 解释策略模式。
- 193: 中介者模式有什么处？
- 194: 什么时候会使用迭代器模式？
- 195: 解释解释器模式。
- 196: 与命令模式相关的 J2EE 模式有哪些？
- 197: 什么时候会使用访问模式？
- 198: 解释模板方法。
- 199: 解释责任链模式。
- 200: 备忘模式和状态模式有什么处？

# 消息传递

- 201: 什么是消息？
- 202: 解释中间层。
- 203: 解释消息队列模型。
- 204: 解释同步通信。
- 205: 解释异步通信。
- 206: 解释 JMS。
- 207: JMS 支持哪些消息模型？
- 208: 同步消息传递有什么处？
- 209: 异步消息传递有什么处？
- 210: 我们在什么场景下选择异步消息？
- 211: JMS 有哪些优点？
- 212: JMS 的组件有哪些？
- 213: JMS 中如何处理异常？
- 214: JMS 中如何确认消息确认？
- 215: 解释 JMS 的消息头。
- 216: JMS 的消息体格式有哪些？
- 217: JMS 中的管理对象分哪些类型？
- 218: JMS 中用于接收和创建消息的对象有哪些？
- 219: 解释消息消费者。
- 220: 解释消息生产者。
- 221: 解释消息选择器。
- 222: 解释消息监听器。
- 223: PTP 通信需要哪些类、接口和步骤？
- 224: Pub/Sub 通信需要哪些类、接口和步骤？
- 225: 解释 MDB。

# 安全与遗留系统连接

- 226: 企业级资源面临的各种安全威胁有哪些？
- 227: 解释身份验证和授权。
- 228: 解释 Java 中可用的某些安全包。
- 229: Java 安全管理器在 Applets 中执行了哪些操作？
- 230: Java applet 有哪些安全限制？
- 231: applet 无法读取哪些系统属性？
- 232: 访问控制的策略有哪些？
- 233: J2EE 支持哪些认证机制？
- 244: 解释加密通信。
- 235: 解释数字证书。
- 236: 解释安全套接层。
- 237: Web 容器执行哪些安全检查？
- 238: 解释使用 Java 的遗留系统连接。
- 239: 解释 EIS 中的认证。
- 240: 解释 CSI。
- 241: 解释 EIS 适配器。
- 242: 解释使用 J2EE 连接器的遗留系统连接。
- 243: 解释资源适配器。
- 244: 解释系统合同。
- 245: 解释 JCA 的集成策略。
- 246: 系统合同的类型有哪些？
- 247: 配置安全属性的方法有哪些？
- 248: CCI API 包含哪些部分？
- 249: 解释管理连接工厂和管理连接。
- 250: 数据库完整性约束的缺点是什么？

你可能被到的 Java / J2EE 面题

# HR 问题

- 1: 你在哪里寻找灵感？
- 2: 你如何在工作中实现创造力？
- 3: 你如何促使他人创造创意？
- 4: 描述一下你的创造力。
- 5: 在工作中你更倾向于获得更多的权力还是责任？
- 6: 当小组中的有人没有按分贡献时，你会做什么？
- 7: 请告诉我一次你做过超出你权限范围的决策。
- 8: 纠纷时向主管反映你感到舒服吗？
- 9: 如果你负责上一份工作，你会做哪些不同的改变？
- 10: 你认为雇主是否应该对表现良好的员工给予表扬或奖励？
- 11: 你认为领导者具备最重要的特质是什么？
- 12: 当出现不可预见的问题时你会如何处理？
- 13: 能举例说明你在之前工作中完成某个目标的经历吗？
- 14: 当主管没有提供足够指导时，你是如何做的？
- 15: 请 true一次你负责某个项目的经历。
- 16: 请 true一次你提出的并在后被采纳的建议。
- 17: 请 true一次你发现工作中某些方面可以更高效的方法。
- 18: 领导和管理之间有什么区别——哪一个是你更擅长的？
- 19: 你更倾向于担任领导角色还是作为团队成员工作？
- 20: 请 true一次你发现某些事情影响了你（或他人）效率的情况——你做了什么？
- 21: 在目标明确的工作中，你表现如何？
- 22: 在拥有决策权的工作中你表现如何？
- 23: 如果你看到其他员工有不实行为，你会怎么办？

# 你可能被到的 Java / JEE 面题

- 24: 请 true一次你自学并在以后对职业生涯有所帮助的经历。
- 25: 请 true一次你开发某个项目的经历。
- 26: 请 true一次你曾在项目中承担风险的经历。
- 27: 对于想要进入这个领域的人，你会建议他们什么？
- 28: 请 true一次你错过截止日期的经历。
- 29: 你在工作时如何消除干扰？
- 30: 请 true一次你在有每周指标的职位上工作的经历。你的成功率有多大？
- 31: 请 true一次你完成严苛截止日的经历，以及你是如何完成的。
- 32: 当你手上有多个项目时，你如何保持条理？



## 面试题列表

- 33: 在工作日中你有多少时间处于“自动驾驶”状态？
- 34: 你如何处理截止日期？
- 35: 描述一下你解决问题的流程。
- 36: 工作中哪些事情会让你感到压力？
- 37: 当你对某事感到压力时状态是怎样的？你是如何解决的？
- 38: 你能多任务处理吗？
- 39: 你每周工作多少小时？
- 40: 你每天检查多少次邮件？
- 51: 请告诉我一次你调解其他员工之间冲突的经历。

## 以下标题可能也很有用

1. 你最可能问到的 .NET 面试题
2. 你最可能问到的 200 道面试题
3. 你最可能问到的 Access VBA 编程面试题
4. 你最可能问到的 Adobe ColdFusion 面试题
5. 你最可能问到的高级 Excel 面试题
6. 你最可能问到的高级 Java 面试题
7. 你最可能问到的高级 AS4 面试题
8. 你最可能问到的 AJAX 面试题
9. 你最可能问到的算法面试题
10. 你最可能问到的安卓开发面试题
11. 你最可能问到的 Ant & Maven 面试题
12. 你最可能问到的 Apache Web Server 面试题
13. 你最可能问到的人工智能面试题
14. 你最可能问到的 ASP.NET 面试题
15. 你最可能问到的自动化软件测试面试题
16. 你最可能问到的 Base SAS 面试题
17. 你最可能问到的 BEA WebLogic Server 面试题
18. 你最可能问到的 C & C++ 面试题
19. 你最可能问到的 C# 面试题
20. 你最可能问到的 C++ 内部面试题
21. 你最可能问到的 CCNA 面试题
22. 你最可能问到的云计算面试题
23. 你最可能问到的计算机体系架构面试题
24. 你最可能问到的计算机网络面试题
25. 你最可能问到的 Java Java 面试题
26. 你最可能问到的数据结构与算法面试题
27. 你最可能问到的数据仓库面试题
28. 你最可能问到的 EJB 3.0 面试题
29. 你最可能问到的 Entity Framework 面试题
30. 你最可能问到的 Fedora & RHEL 面试题
31. 你最可能问到的 GNU 开发面试题
32. 你最可能问到的 Hibernate, Spring & Struts 面试题
33. 你最可能问到的 HTML, XML 和 CSS 面试题
34. 你最可能问到的 HTML5 面试题
35. 你最可能问到的 IBM WebSphere 应用程序服务器面试题
36. 你最可能问到的 iOS SDK 面试题
37. 你可能会问到的 Java / J2EE 设计模式面试题
38. 你最可能问到的 Java / J2EE 面试题
39. 你最可能问到的 Java 服务面试题
40. 你最可能问到的 JavaScript 面试题
41. 你最可能问到的 JavaFaces 面试题
42. 你最可能问到的 JDBC 面试题
43. 你最可能问到的 jQuery 面试题
44. 你最可能问到的 JSP-Servlet 面试题
45. 你最可能问到的 Junit 面试题
46. 你最可能问到的 Java/JEE 面试题
47. 你最可能问到的 Linux 命令面试题
48. 你最可能问到的 Linux 面试题
49. 你最可能问到的 Linux 系统管理员面试题
50. 你最可能问到的 Mac OS Snow Leopard 面试题
51. 你最可能问到的 Microsoft Access 面试题
52. 你最可能问到的 Microsoft Excel 面试题
53. 你最可能问到的 Microsoft PowerPoint 面试题
54. 你最可能问到的 Microsoft Word 面试题
55. 你最可能问到的 MySQL 面试题
56. 你最可能问到的 NetSuite 面试题
57. 你最可能问到的网络面试题
58. 你最可能问到的 OOP 面试题
59. 你最可能问到的操作系统面试题
60. 你最可能问到的 Oracle DBA 面试题
61. 你最可能问到的 Oracle E-Business Suite 面试题
62. 你最可能问到的 Oracle PL/SQL 面试题
63. 你最可能问到的 Perl 编程面试题
64. 你最可能问到的 PHP 面试题
65. 你最可能问到的 PMP 面试题
66. 你最可能问到的 Python 面试题
67. 你最可能问到的 RESTful Java 服务面试题
68. 你最可能问到的 Ruby 面试题
69. 你最可能问到的 Ruby Rails 面试题
70. 你最可能问到的 SAP ABAB 面试题
71. 你最可能问到的 SAP HANA 面试题
72. 你最可能问到的 SAS 编程指南面试题
73. 你最可能问到的 Selenium 测试工具面试题
74. 你最可能问到的 Silverlight 面试题
75. 你最可能问到的软件仓库面试题
76. 你最可能问到的软件测试面试题
77. 你最可能问到的 SQL Server 面试题
78. 你最可能问到的 Tomcat 面试题
79. 你最可能问到的 UML 面试题
80. 你最可能问到的 Unix 面试题
81. 你最可能问到的 Unix Shell 编程面试题
82. 你最可能问到的 VB.NET 面试题
83. 你最可能问到的 Windows Server 2008 R2 面试题
84. 你最可能问到的 XLQP, XSLT, XPath, XFORMS &Query 面试题
85. 你最可能问到的 XML 面试题

## 完整列表请访问

www.vibrantpublishers.com

## 注释
