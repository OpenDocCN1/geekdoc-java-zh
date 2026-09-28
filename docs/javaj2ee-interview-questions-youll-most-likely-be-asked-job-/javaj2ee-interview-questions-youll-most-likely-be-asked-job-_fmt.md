
# Java／J2EE 高频面试题 (工作面试题系列)

![](img/262b08009c468cf9baa4946ee1711f87_0_0.png)

![](img/262b08009c468cf9baa4946ee1711f87_2_0.png)

回顾这些典型的面试题，并思考你会如何回答。阅读列出的答案；你将找到最佳答案以及相关的策略和建议。

## 第1章 架构与协议

### 1：Web 服务器（Web Server）和应用程序服务器（Application Server）之间有什么区别？

答案：

Web 服务器在互联网上运行。它使用 `HTTP` 协议通过互联网将客户端请求发送到位于其他地方的服务器，从服务器检索请求的信息，或向服务器提交所发送的信息。`ASP`、`JSP`、`Servlets`、服务器端 `JavaScript` 和 `CGI` 脚本都可以在 Web 服务器上运行。Web 服务器仅充当中间层，传递或检索请求，并提供 `HTML` 页面结果。它不涉及任何处理或数据处理。应用程序服务器使用 `HTTP` 或其他协议为客户端提供业务逻辑。应用程序服务器可以是一个 `GUI`，其中涉及运行在计算机、Web 服务器或其他应用程序服务器上的某些业务逻辑或数据处理程序。它向客户端暴露业务逻辑。

### 2：J2EE 架构中包含了哪些技术？

答案：

J2EE 架构包含以下技术：

- a) `JAX-RPC`，基于 `XML` 的 `RPC` 的 Java API
- b) `JSP` 或 Java Server Pages（Java 页面）
- c) `EJB` 或 Enterprise Java Beans（企业级 Java Bean）
- d) Java Servlets
- e) J2EE Connector Architecture（连接器架构）
- f) J2EE Management Model（管理模型）
- g) J2EE Deployment API（部署 API）
- h) `JMX` Management Extensions（管理扩展）
- i) 容器授权
- j) `JAXR` 或 XML 注册表
- k) `JMS` Message Service（消息服务）
- l) `JNDI` Naming and Directory Interface（命名与目录接口）
- m) `JTA` Transaction（事务处理）
- n) `CORBA` Common对象请求代理
- o) `JDBC` 数据连接

### 3：Spring 框架有哪些好处？

答案：

Spring 是一个轻量级框架，提供了各种类型的支持。它通过使用反转控制（`IoC`）、面向切面编程（`AOP`）和依赖注入（`DI`）来简化开发。它将业务逻辑与基础设施分离。

### 4：区分 SAX 和 DOM 解析器

答案：

`SAX`（XML Simple API）是一种基于事件的解析器，它逐节点读取文档，速度较快且内存占用小。`DOM`（文档对象模型）将整个 `XML` 文档加载到内存中形成树结构，允许对数据进行随机访问和修改，但速度较慢且消耗更多内存。

### 5：组件和服务之间有什么区别？

答案：

J2EE 组件是用于特定用途软件单元，例如 `Applets`、`Servlets`、`Session Bean` 和 `Entity Bean`。服务是同步或异步定义的约。

### 6：J2EE 的设计目标是什么？

答案：

J2EE 的设计目标如下：

- 可用性：应用程序应 24 小时可用。
- 数据连接：应用程序应该连接到大型机和其他遗留系统。
- 可访问性：用户应该从任何地方、通过任何电子设备（桌面电脑、笔记本电脑、`PDA`、手机）访问应用程序。
- 用户交互：用户应该与应用程序进行交互。
- 灵活性：架构的设计应让开发者只需专注于组件模型（业务逻辑），其他服务由服务器处理。

### 7：J2EE 架构师的角色是什么？

答案：

架构师的角色包括：

- 系统的行为视觉化。
- 创建系统蓝图。
- 定义系统元素如何工作。
- 定义非功能性需求和功能需求。
- 将非功能性需求集成到功能系统中。

### 8：架构和设计之间有什么区别？

答案：

架构定义结构问题、通信协议、数据访问、同步和子系统分类。它还定义了接口的架构设计。在设计中，我们为每个接口定义的组件、输入、输出、算法和数据结构。简单来说，设计师描述每个组件的内部细节。

### 9：架构分析包含哪些活动？

答案：

架构分析将执行以下活动：

- 用例图（Use case diagram）：用于描述高层系统功能。
- 类图（Class Diagram）：用于描述类和方法的功能。
- 协作图（Collaboration Diagram）：用于描述类之间如何通信。
- 序列图（Sequence Diagram）：用于描述操作序列。

### 10：架构设计包含哪些活动？

答案：

架构设计将执行以下活动：

- a) 框架（例如：远程方法调用 `RMI`）将使用的内容将待决定
- b) 定义软件和硬件需求
- c) 定义性能参数和实现方法
- d) 分析是否重用现有组件或技术
- e) 定义系统的业务逻辑、安全性和性能

### 11：面向对象设计执行了哪些活动？

答案：

在面向对象设计中将执行以下活动：

- a) 决定类如何与包（packages）交互
- b) 创建依赖关系图
- c) 创建部署图
- d) 决定组件（软件）是否存在于部署文件夹中

### 12：多层架构的组成部分有哪些？

答案：

以下是多层架构的组成部分：

- a) 表示层（Presentation Tier）：该层存在前端组件，用于显示表现层
- b) 资源层（Resource Tier）：该层存在后端组件，用于与数据库通信
- c) 业务层（Business Tier）：该层中的组件用于为系统提供业务逻辑

### 13：多层客户端/服务器架构的优势有哪些？

答案：

以下是多层客户端/服务器架构的优势：

- a) 可以独立地对业务逻辑或用户界面进行更改
- b) 客户端轻松访问数据，而无需知道数据来自何处以及系统有多少可用服务器
- c) 数据库（`DB`）连接可以池化，以便多个用户可以共享数据，而无需为每个用户向数据库请求
- d) 中间层组件（业务逻辑）可以使用任何标准编程语言（如 `C` 或 `Java`）编写

### 14：Bean 开发者（bean developer）的职责是什么？

答案：

以下是 Bean 开发者的职责：

- a) 使用 `Java` 编写系统的业务逻辑
- b) 将 `Java` 组件与第三方组件集成
- c) 控制访问并设置事务参数
- d) 创建查找 bean 的本地接口（home interface）和创建业务逻辑的远程接口（remote interface）
- e) 创建部署描述符 `xml`

### 15：应用程序（application assembler）的职责是什么？

答案：

以下是应用程序程序的职责，即：

- a) 构建表现层用户界面
- b) 指定事务管理的需求
- c) 为所有 bean 方法设置事务参数
- d) 定义安全角色并分配权限
- e) 为方法指定通配符字符 (`*`)

### 16：Bean 部署器（bean deployer）的职责是什么？

答案：

以下是 Bean 部署器的职责：

- a) 将字段映射到数据库（`DB`）列并管理持久化
- b) 定义用户、组、角色并管理安全
- c) 使用部署工具生成封装类
- d) 映射用户角色和组
- e) 确保所有部署的 bean 都分配了事务参数

### 17：第三方软件在 EJB 框架中扮演什么角色？

答案：

提供软件的第三方公司可以扮演以下三个角色之一：

- a) 组件供应商（Component Provider）：负责对象建模、编程、架构和业务流程的
- b) 容器供应商（Container Provider）：负责在运行时为服务器提供环境
- c) 应用程序服务器供应商（Application Server Provider）：负责提供开发分布式应用的平台。它通常包含提供运行时环境的容器

### 18：解释 MVC 架构。

答案：

`MVC` 代表模型-视图-控制器（Model View Controller）架构。`MVC` 中执行的活动如下：

- a) 在模型（Model）中，开发者创建系统的业务逻辑
- b) 在视图（View）中，开发者创建表现逻辑
- c) 在控制器（Controller）中，开发者接收请求并传输响应

### 19：解释 EAR、WAR 和 JAR。

答案：

`EAR` 代表企业归档（Enterprise Archive）。它包含了 Web、`EJB` 和客户端组件。所有组件都打包在一个名为 `.ear` 的压缩文件中。

`WAR` 代表 Web 归档（Web Archive）。它包含了与 Web 应用相关的所有组件。所有组件都打包在一个名为 `.war` 的压缩文件中。

`JAR` 代表 Java 归档（Java Archive）。它包含了构成 `API`（应用程序编程接口）的所有类文件和库文件。所有组件都打包在一个名为 `.jar` 的压缩文件中。

### 20：解释 JTA、JNDI 和 JMS。

答案：

`JTA` 代表 Java 事务 API（Java Transaction API）。用于协调和管理跨企业信息系统的事务。

`JNDI` 代表 Java 命名目录接口（Java Naming Directory Interface）。用于从目录服务访问信息。

`JMS` 代表 Java 消息服务（Java Messaging Service）。用于通过消息系统接收和发送消息。

### 21：解释 EDI。

答案：

`EDI` 代表电子数据交换（Electronic Data Interchange）。用于通过作为传输媒介的增值网络（`VAN`）交换数据。

`EDI` 的安装成本昂贵，并且需要交换客户端进行定制。`EDI` 还依赖 `X12` 标准来交换文档。

### 22：解释 EAI。

答案：

`EAI` 代表企业应用集成（Enterprise Application Integration）。这把一个或多个应用程序视为单个应用程序，并要求在正确的时间将数据传输到相应的系统中。

例如在集成销售和会计系统时，销售部门需要发送销售订单到会计部门以生成发票。此外，会计部门必须发送发票给销售部门以更新销售数据。

该系统自动处理事务。

### 23：Java 中支持 XML 的意图是什么？

答案：

支持 `XML` 的意图是：

- a) 确保 平台
- b) 为 `Java` 提供标准
- c) 确保高质量

### 24：业务层和用户界面之间通信使用哪些协议？

答案：

业务层和用户界面之间通信使用以下协议：

- a) `HTTP`：代表“超文本传输协议”（Hyper Text Transfer Protocol）
- b) `JMS`：代表“Java 消息服务”（Java Messaging Service）
- c) `RMI`：代表“远程方法调用”（Remote Method Invocation）
- d) `CORBA`：代表“通用对象体系架构”（Common Object Broker Architecture）
- e) `DCOM`：代表“分布式组件模型”（Distributed Component Object Model）

### 25：HTTP 协议的优点和缺点是什么？

答案：

`HTTP` 协议的优点是：

- a) 无状态且防火墙友好
- b) 更容易进行负载均衡和扩展

`HTTP` 协议的缺点是：

- a) 难以维护会话
- b) 与 `JSP` 和 servlet 的通信有限

### 26：解释 JRMP。

答案：

`JRMP` 代表 Java 远程方法协议（Java Remote Method Protocol）。远程方法调用（`RMI`）使用它来传递 `Java` 对象。由于 `Java` 依赖对象序列化将对象封装为流，`RMI` 依赖 `JRMP` 协议在 `JVM`（Java 虚拟机）之间传输对象。

### 27：CORBA 的优势和缺点是什么？

答案：

`CORBA` 的优势是：

- a) 支持异构对象
- b) 扩展了 `ORB`（对象请求代理）的能力

`CORBA` 的缺点是：

- a) 无法传递对象，只能传递参数
- b) 只能传递接受的数据类型

### 28：解释 DCOM。

答案：

`DCOM` 代表分布式组件模型（Distributed Component Model）。它使用 `ORPC`（对象远程过程调用）协议来支持远程对象。

`ORPC` 构建在 `RPC`（远程过程调用）之上，并与运行时服务交互。`DCOM` 支持多个接口，可以使用各种编程语言创建组件。语言示例：`Java`、`C`、`Visual Basic` 等。`DCOM` 在 `Windows` 平台上广泛使用。

### 29：解释 J2EE 架构的能力。

答案：

J2EE 架构的能力如下：

- a) 性能：在短时间范围内执行功能
- b) 可扩展性：即使服务器负载增加也能支持
- c) 可用性：跨始终可访问 24*7
- d) 灵活性：硬件或架构的变更不会影响系统
- e) 安全性：信息无法被黑客攻击和修改
- f) 可复性：为系统创建的组件可以重复使用并节省开发时间

### 30：解释系统架构（System architecture）和参考架构（Reference architecture）。

答案：

系统架构将架构视为一种产品。它包含了所提系统的组件功能、接口、约束条件和交互作用。这是应用设计实现的基础。

参考架构将架构视为一种方法或风格。对于特定的领域，参考架构指的是连贯的设计原则。

## 第 2 章 适用性与最佳实践

### 31：解释为了获得更好性能而应该遵循的最佳实践。

答案：

以下实践可以提高 J2EE 应用的性能：

- a) **更好的资源管理**是获得更佳性能的关键。你可以通过创建限制性资源、池化或缓存资源，以及在特定资源不再被使用时立即释放内存来实现这一点。
- b) 通过更好的会话、`EJB`、`JNDI` 初始上下文等设计模式来**最小化网络开销**。
- c) 通过按引用传递并将引用声明为 `transient` 来**最小化序列化成本**。
- d) **超时机制**确保空闲对象不会长时间占用内存
- e) **仅对 JDBC 对象应用所需的权限**，并确保它们在不使用时释放，这将释放资源和内存。
- f) **将数据库自动提交（auto-commit）设置为 false**
- g) **使用虚拟代理（Virtual Proxy）**确保仅在需要时将所需的字段加载到内存中。

### 32：Struts、Spring 和 Hibernate 如何提高性能的？

答案：

`Struts`、`Spring` 和 `Hibernate` 结合使用可以帮助你创建设计优化、更轻量且自给的 Web 应用。`Struts` 负责 Web 应用框架，`Hibernate` 是形成数据库层的 `ORM` 网络，而 `Spring` 是企业级应用框架。如果你正在构建新应用，可以使用 `Spring` 和 `Hibernate`，因为 `Spring` 可以替代 `Struts`。`Spring` 基于控制反转（Inversion of Control）和依赖注入（Dependency Injection）模式原理工作，这些原则指导了更佳的 J2EE 设计模式。`Struts` 拥有包含 `JSP`、`Servlets`、`Java Beans`、特殊标签和消息的 `MVC` 框架。`Hibernate` 是可移植的，并支持对象到关系数据库的映射。它在建立数据库连接和维护事务方面比 `JDBC` 好得多。`Struts`、`Spring` 和 `Hibernate` 协同工作时，提供了一个经过验证的设计模式框架和更好的连接性。

### 33：垃圾回收（Garbage Collection）如何帮助提高性能？

答案：

垃圾回收释放用于存储对象和数据的内存，从而在 `JVM` 中释放出更多空间，用于存储正在使用的新对象。这些额外空间可以用于内存交换和处理，并且是持续的。`JVM` 使用栈和堆来清除过时的对象引用，并在访问该对象的程序或代码块退出时对其取消分配。这是一个复杂的过程，其中内存会被多次交换，以确保在 `JVM` 确认该对象不再被引用之前，数据在任何被引用时都是可用的。

### 34：解释最佳实践（Best Practice）。

答案：

最佳实践可以定义如下：

- a) 在组件层级驱动你的应用设计的技术
- b) 参与类似项目的其他团队成员所认可的流程
- c) 考虑了设计或系统需求
- d) 适用于整个软件开发生命周期

### 35：解释 J2EE 分层（tiers）。

答案：

J2EE 具有以下分层：

- a) 客户端（Client Tier）：它代表向服务器发送请求的浏览器。该层使用的接口是 `HTML` 浏览器、`Java` 应用、`applet` 或非 `Java` 应用。

### 36：表示层（presentation layer）应该遵循哪些最佳实践？

答案：

表示层应遵循的最佳实践解释如下：

- a) 将超文本标记语言 (`HTML`) 与 `Java` 分离
- b) 始终在 Bean 类中编写业务逻辑
- c) 使用 `JSP` 模板和注释
- d) 使用模型-视图-控制器（`MVC`）模式
- e) 使用自定义库和标签处理器（tag handlers）

### 37：MVC 使用什么类型的组件？

答案：

`MVC` 代表模型-视图-控制器（Model View Controller）。模型、视图和控制器使用的组件解释如下：

- a) 应用代表模型（Model），它构成了系统的状态。系统状态通过 Bean 类中的业务逻辑创建
- b) 用户界面代表视图（View），使用 Java Server Pages（`JSP` 页面）创建
- c) 从客户端接收的请求始终是控制器（Controller），使用 `Servlets` 创建

### 38：J2EE 系统在全球经济中运行必须具备什么要求？

答案：

J2EE 系统为了在全球范围内运行必须具备以下条件：

- a) 财务考虑：购买物品的支付方式应包含多种形式，因为并非所有访问者都有信用卡。此外，政府有自己的税收、海关限制和关税。
- b) 语言需求：应用应该支持多种语言并且必须是具体的。
- c) 法律差异：每个国家的海关法和隐私要求不同，每个政府对图像、思想、演讲都有限制。

### 39：DAO 中应该遵循哪些最佳实践？

答案：

`DAO` 代表数据访问对象（Data Access Object）。`DAO` 中遵循的最佳实践是：

- a) `DAO` 不应与业务逻辑紧耦合



- b) 每个 bean 都应该与 DAO 关联
- c) DAO 只用于访问数据
- d) DAO 的编写方式允许跨模式
- e) 支持可移植性

### 40: 解释指南

答案：
指南指的是由专业组织开发的业务规则或协议。它还包括在项目期间为了减少流量而遵循的标准。

### 41: VO 中应该遵循哪些最佳实践？

答案：
VO 代表值对象。VO 中遵循的最佳实践是：
- a) VO 应该包含 get 和 set 方法
- b) VO 应该相应的值更新模型 bean
- c) VO 不引用服务器对象
- d) VO 代表来自服务器的值

### 42: 会话 bean facade 应该遵循哪些最佳实践？

答案：
- a) 它应该减少对服务器的远程调用
- b) 对调用实体 bean 应用事务范围
- c) 简化客户端代码，使业务逻辑仅在服务器上执行
- d) 代码编写方式应识别用户权限并提供灵活性和复用性

### 43: 模型-视图-控制器（MVC）有什么优点？

答案：
MVC 的优点如下：
- a) 将数据模型与用户交互及数据显示分离，并明确了应用设计
- b) 允许大量用户以多种形式查看数据
- c) 通过分离功能与表示层增强了复用性
- d) 增加了灵活性并改进了扩展性
- e) 封装了应用功能并便于维护
- f) 支持增量更新和划分部署

### 44: MVC 存在哪些设计问题？

答案：
MVC 的设计问题如下：
- a) 组件感知其他组件的实现细节
- b) 延迟问题和通信量必须仔细处理，否则在分布式系统中会导致可扩展性问题
- c) 如果模型不稳定，MVC 很难维护，因为控制器大部分是基于模型编写的

### 45: 解释 MVC 的适用性。

答案：
MVC 适用于以下情况：
- a) 如果应用足够大且分布式
- b) 如果应用生命周期较长
- c) 接口和后端的可移植性最重要
- d) 便于维护和复用
- e) 由多个开发者开发应用
- f) 以多种方式查看数据并对其操作

### 46: 解释 J2EE 框架中模式的重要性。

答案：
模式是指在特定语境下解决问题的反复出现的解决方案。语境是指问题存在的情况或环境。问题是需要调查且必须解决的事物，并通过因果关系指定。

### 47: 解释框架模式。

答案：
以下被称为框架模式：
- a) **代理模式**：`EJB` 远程接口是代理模式的一个示例。它拥有的方法可以将方法调用委托给对象
- b) **工厂方法**：`EJB Home` 接口是工厂方法的一个示例。它包含一个独立的可重用类，通过通用接口引用对象
- c) **抽象工厂方法**：`EJB home` 接口是抽象工厂方法的一个示例。它有一个从具体子类创建抽象类实例的程序
- d) **装饰器**：`EJDataObject` 是装饰器模式的一个示例。装饰器的功能是它对客户端是可见的

### 48: 部署器的活动有哪些？

答案：
部署器执行以下活动：
- a) 将开发阶段创建的企业归档文件 (EAR) 划分到 J2EE 应用服务器中
- b) 修改部署描述并配置 J2EE 应用程序
- c) 确保企业归档文件 (EAR) 格式正确并符合 J2EE 规范
- d) 在 J2EE 应用服务器中安装或部署企业归档文件 (EAR)

### 49: 属于集成层的模式有哪些？

答案：
以下模式属于集成层：
- a) **DAO**：数据访问对象检索数据源并提供透明的数据访问
- b) **服务激活器**：这用于 `EJB` 组件并支持异步处理

### 50: 解释表现层模式。

答案：
以下是表现层模式：
- a) **前端控制器**：用于处理和管理来自客户端的请求
- b) **装饰器过滤器**：用于对特定请求进行预处理和后处理
- c) **组合视图**：用于从多个组件创建一个视图
- d) **分发视图**：与前端控制器配合使用，用于视图助手模式并推迟视图处理的活动
- e) **视图助手**：用于封装逻辑和格式化显示

### 51: 解释业务层模式。

答案：
以下是业务层模式：
- a) **会话门面**：隐藏业务对象的复杂性并集中处理工作流
- b) **值对象**：用于在不同层之间交换数据
- c) **服务定位器**：用于隐藏业务服务的创建复杂查找。它还定位服务工厂
- d) **业务委托**：分离服务层和表现层，并为服务提供代理和外面接口
- e) **值对象装配器**：用于从数据源构建对象

### 52: 解释 EIS。

答案：
EIS 代表企业信息系统。它存在于集成层并为企业提供基础设施相关信息。
访问 EIS 非常复杂，需要以下知识：
- a) 与事务相关的信息
- b) 与安全相关的信息，以及
- c) 应用程序编程模型知识

### 53: EIS 和应用服务器的系统级合约是什么？

答案：
以下是 EIS 和 J2EE 应用服务器的系统级合约：
- a) **连接管理** 合约允许应用程序和 J2EE 组件连接到 EIS。这导致了可扩展的环境并支持许多客户端访问 EIS
- b) **事务管理** 合约支持对 EIS 的事务相关访问。它使用事务管理器来管理事务
- c) **安全** 合约允许获得 EIS 的安全访问。这减少了对 EIS 的威胁并保护了信息

### 54: 解释资源适配器。

答案：
资源适配器是企业信息系统（EIS）的系统级合约。它被应用程序客户端或服务器连接 EIS。
它与应用服务器协作以支持安全、事务和连接池。它用于应用程序服务器的地址空间内。

### 55: 解释数据缓存。

答案：
数据缓存功能解释如下：
- a) 缓存功能解释如下文
- b) 缓存功能解释如下文
- c) 缓存功能解释如下文
- d) 缓存功能解释如下文
- e) 缓存功能解释如下文

### 56: 解释服务定位器。

答案：
服务定位器用于隐藏业务服务的创建复杂性和查找。它还定位服务工厂。服务定位器使用 `Java` 命名目录接口 (`JNDI`) API，这需要初始上下文。

### 57: 解释如何防止性能问题。

答案：
可以通过以下方式防止性能问题：
- a) 如果服务需要本地访问，则使用本地对象
- b) 如果你想访问同一个 bean，则使用本地接口
- c) 使用单次调用代替多次调用
- d) 修改不变量
- e) 为了避免 `JNDI`，缓存

### 58: 解释安全准则。

答案：
安全机制的目的是通过集成环境支持端到端安全。安全通过在所有领域创建用户账户来处理。此外，安全应支持授权身份验证。

### 59: Servlet 使用哪些类和接口？

答案：
Servlet 依赖于两个包：`javax.servlet` 和 `javax.servlet.http`。`javax.servlet` 包包含与 servlet 细节相关的接口和类。`javax.servlet.http` 包包含与 http 请求和响应相关的接口和类。

### 60: ServletContext() 方法的作用是什么？

答案：
`ServletContext()` 方法用于设置和检索 servlet 的初始配置，包括会话、连接和服务器详情。该方法返回一个 `ServletConfig` 对象，包含所有初始参数。所有范围范围参数都使用 `ServletConfig` 对象设置，`ServletContext()` 方法返回该对象及其初始参数。需要考虑的一个方面是，垃圾回收器不会释放为 `ServletConfig` 对象分配的内存，因此

### 61: 解释 HttpServlet 中的方法。

答案：
`HttpServlet` 是一个抽象类，包含了在 http 服务器上使用的 `get` 和 `post` 函数。开发者需要重写这些方法以确保在考虑业务逻辑的情况下工作。由于它是抽象类，开发者必须至少重写一个方法，而 `doGet()` 方法是通常被重写的那个。最好也重写 `getLastModified()` 方法以实现缓存，从而进一步实现智能的条件 `GET` 和 `HEAD` 操作。
尽管 `doTrace()` 和 `doOptions()` 方法也可用，但它们并没有被重写。只有在你想管理资源时，才需要重写 `init()` 和 `destroy()` 方法。

### 62: 解释 HttpSession 中的方法。

答案：
`HttpSession` 接口将 HTTP 客户端关联到 HTTP 服务器。会话存储了关于用户身份和状态的详细信息，这些信息跨越页面或请求。它包含了允许开发者设置会话值和获取当前会话值的方法。
- a) `getSessionContext()` 返回包含当前会话的会话上下文
- b) `isNew()` 如果服务器开启了一个新会话且客户端尚未加入则返回 true
- c) `getCreationTime()` 返回当前会话创建的时间
- d) `getId()` 返回当前会话的唯一 ID，`HttpSession` 接口中还有更多方法提供关于当前会话的更多信息，这有助于进一步了解客户端。这些信息被用于验证关键登录会话，以及用户在网站上花费的时间。

### 63: Applet 可以与 Servlet 通信吗？解释。

答案：
Applet 绝对可以与 Servlet 通信。可以通过三种可能的方式之一实现。这可以使用 HTTP 通信（可以是基于文本或基于对象的）、Socket 通信或 `RMI` 实现。无论哪种情况，你都需要按照下述步骤来实现通信：
- a) 首先获取服务器 URL
- b) 向主机 URL 建立连接
- c) 初始化连接并将缓存设置为 `false`，将 `doOutput` 和 `doInput` 设置为 `true`
- d) 创建一个 `ByteArrayOutputStream` 来存储要传递的数据长度，最后创建输出流，将数据实际写入缓冲区。

### 64: 当数据库发生变化时，HTML 表单中的数据会自动刷新吗？解释。

答案：
JSP 动态创建页面。页面可能包含 `html`、`dhtml`、`wml` 或任何其他标记语言。但一旦页面生成，即使数据库中有新数据，也必须显式地重新加载才能获取最新数据。JSP 只拥有在加载到页面之前从数据库获取数据时可用的数据。但可以通过其他方式实现动态刷新，例如显式页面重新加载，但不推荐这样做，因为将涉及向服务器发送另一个请求和响应。可以使用 `ServerSocket` 通过加载的 applet 从服务器接收新数据。但这也相当昂贵，因为它持用了大量资源。最简单的方法是使用 `JavaScript` 按固定间隔刷新页面，这样它会像每次页面刷新一样向服务器发送请求，但这里是自动完成的。

### 65: 区分 ServletContext 和 ServletConfig。

答案：
`ServletContext` 接口包含了用于 servlet 与服务器容器之间通信的方法。它处理有关 servlet 请求和响应的 MIME 类型以及服务器等详细信息。`ServletContext` 类型的对象包含在 `ServletConfig` 对象中，`ServletConfig` 包含了 servlet 的初始化参数。由于 `ServletContext` 代表单个 Servlet，而 `ServletConfig` 对于 JVM 内的所有 Servlet 是通用的，这使得 `ServletContext` 是局部参数，而 `ServletConfig` 是全局参数。`getServletContext()` 方法用于 `ServletContext` 中获取配置对象的详细信息。`ServletConfig` 使用 `getServletContext()` 方法获取上下文对象的详细信息。

### 66: 哪个性能更好 – JSP 还是 Servlet？解释。

答案：
Servlet 包含应用程序的 Java 组件，而 JSP 是 Web 组件。JSP 用于动态 Web 页面，其中 Java 代码在服务器标签内连同客户端的 `HTML`、`JavaScript` 和 `CSS` 代码一起使用。JSP 页面在第一次请求时会被编译成一个 java servlet 类。Java Servlets 是运行在服务器上的 Java API 程序。与 JSP 页面类似，当应用程序第一次请求 servlet 时，它会被编译并产生一个实例。



默认情况下，Servlet 不是线程安全的。开发者可以通过使用同步或在 `service` 方法中使用局部变量来使其线程安全。`service` 方法只创建一次实例，对于后续请求，由实例化线程提供服务。

### 68: 如何在 doGet()、doPost() 和 service() 之间选择？

Answer:

当客户端提交 GET 请求时调用 `doGet()` 方法。当提交 POST 请求时调用 `doPost()` 方法。`service()` 方法对每个请求都会调用，并将请求调度给 `doGet` 或 `doPost`。

### 69: 解释 Servlet。

Answer:

Servlet 是运行在服务器上的程序。Servlet 的目的是：

- 接收客户端的请求
- 获取请求信息并生成响应
- 格式化响应并发送客户端

Servlet 不限于用于 Web 服务器，也可以嵌入邮件服务器和 FTP 服务器。

### 70: 解释 Servlet 的 GET 和 POST 请求。

Answer:

GET 和 POST 请求分别由 `doGet` 和 `doPost` 方法处理。这两个方法接收 `HttpServletRequest` 和 `HttpServletResponse` 作为参数并抛出 `IOException` 和 `ServletException`。

```java
public void doGet(HttpServletRequest request, HttpServletResponse response) throws IOException, ServletException {
}
public void doPost(HttpServletRequest request, HttpServletResponse response) throws IOException, ServletException {
}
```

在 GET 请求的情况下，传递给服务器的所有参数在浏览器中可见的，但在 POST 请求的情况下，参数不可见。

### 71: 解释 Servlet 生命周期。

Answer:

Servlet 生命周期可以通过以下三个方法来解释：

- init: 当 servlet 被浏览器触发时调用此方法。此方法只创建一次 servlet 实例，对于后续请求，由实例化线程提供服务。
- service: 此方法通过实例化线程从服务器获取响应，该线程调用 `doGet` 或 `doPost` 方法。
- destroy: 当服务器卸载 servlet 时调用此方法。

### 72: Servlet 在哪里如何获取初始化参数？

Answer:

我们可以在 `web.xml` 文件中为每个 servlet 定义初始化参数，如下：

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

在 Servlet 中，我们可以使用 `getInitParameter("city")` 获取值。

### 73: Servlet 如何接收 HTML 表单数据的值？

Answer:

假设 html 表单有以下文本字段：

```html
<input type="text" name="user_name"/>
```

Servlet 可以通过以下方法接收表单值：

```java
String username = request.getParameter("user_name");
```

### 74: 假设你不知道 html 表单字段的名称。是否可以在不知道表单字段名称的情况下在 Servlet 中获取这些值？

答案：

是的。可以在不知道表单字段名称的情况下获取所有 html 表单字段的值。

在 Servlet 中，我们可以使用 `request.getParameterNames()` 方法来获取所有表单字段的名称，然后通过 `request.getParameterValues(parameterName)` 方法逐个获取值。

### 75: 是否可以从 doPost 中调用 doGet？

答案：

是的。可以从 `doPost` 方法中调用 `doGet` 方法。如果 servlet 需要同时处理 GET 和 POST 请求，就可以这样做。

根据请求类型（GET / POST），服务方法调用 `doPost` 方法，然后由它调用 `doGet` 方法。

### 76: 解释 init 方法的语法。

答案：

`init` 方法的语法所示：

```java
public void init() throws ServletException {
    //代码如下...
}
public void init(ServletConfig myConfig) throws ServletException {
    super.init(myConfig)
    //代码如下...
}
```

因此，只有通过 `init` 方法才能获取配置参数。

### 77: 从 doPost 中调用 doGet 方法有什么优点？

答案：

从 `doPost` 方法中调用 `doGet` 方法的优点如下：

- a) 默认情况下，通过 `doGet` 方法接收 HEAD 请求的支持
- b) 默认情况下，通过 `doGet` 方法接收 OPTIONS 请求的支持
- c) 默认情况下，通过 `doGet` 方法接收 TRACE 请求的支持

### 78: 如何从 Servlet 向浏览器发送压缩后的网页？

答案：

要发送压缩内容，首先我们按照如下接受编码：

```java
String myEncoding = request.getHeader("Accept-Encoding");
```

然后，我们必须在浏览器中设置编码：

```java
response.setHeader("Content-Encoding", "gzip");
```

这种显示压缩结果的方法可以节省大量的下载时间。

### 79: 解释状态码。

答案：

对于每个 HTTP（超文本传输协议）请求，servlet 会从服务器发送一个状态码和一个消息。状态码是一个表示服务器响应是否成功的数字。

所以，如果 servlet 收到来自服务器的响应，那么在头部中，服务器将发送状态码 200 且消息为 OK。

### 80: 解释状态码 200 和 404 的含义。

答案：

如果 servlet 从服务器收到响应，我们将从头部中获取状态码 200。默认情况下，状态码 200 的消息被设置为 OK。

如果从浏览器无法访问 servlet，或者 servlet 不存在，服务器将在头部设置状态码为 404。默认情况下，消息被设置为 File Not Found（文件未找到）。

### 81: 解释 sendRedirect 方法。

答案：

`sendRedirect` 方法接受 URL（统一资源定位符）作为参数，如下：

```java
response.sendRedirect(myURL)
```

`sendRedirect` 方法将请求转发到指定的 URL，用于将客户端从一个页面重定向到另一个页面。

### 82: 如果特定页面或 servlet 不可用，如何显示错误消息？

答案：

如果请求的页面、servlet 或参数在服务器上不可用，服务器将返回状态码 404。

例如：

```java
String myName = request.getParameter("user_name");
if(myName == null)
{
    response.sendError(response.SC_NOT_FOUND, "user_name is null");
}
```

在上述代码中，如果参数值为 null，则使用 `sendError` 方法向浏览器发送消息。

### 83: 哪些方法用于设置头部（header）值？

答案：

以下是用于在头部设置值的方法：

- a) `setContentType`: 所有 servlet 都使用的此方法
- b) `addHeader`: 该方法用于添加新的头部
- c) `setHeader`: 该方法用于设置现有头部的值

### 84: 哪些方法用于获取头部（header）值？

答案：

以下是用于获取头部值的方法：

- a) `getHeader`: 该方法用于获取特定头部的值
- b) `getHeaders`: 该方法用于获取特定头部的所有值
- c) `getNames`: 该方法用于获取所有的头部名称

### 85: 解释 MIME。

答案：

MIME 代表 Multipurpose Internet Mail Extensions（多用途互联网邮件扩展）。它是一种指示媒体类型性质的标准。在 servlet 中，它用于告诉浏览器正在发送什么类型的内容。

### 86: 解释最常用的 MIME 类型。

答案：

以下是常用的 MIME 类型：

- `text/html`: 用于 HTML 文档
- `image/png`: 用于 PNG
- `application/pdf`: 用于 PDF 文档
- `video/mpeg`: 用于 MPEG 视频
- `audio/midi`: 用于 MIDI 音频

### 87: 什么是 Cookie？

答案：

当访问者浏览页面时，某些信息（如访问者输入的字段值、添加到购物车的项目等）会存储在浏览器中。这在以下场景中非常有用：如果同一个访问者再次访问，信息将从浏览器而非服务器提供，从而减少服务器负载和加载所需的时间。



### 88: Cookie 有什么优点？

答案：

以下是 cookie 的优点：

- 访问者只需要登录一次，随后的访问不需要登录
- 识别特定用户并显示在购物车中添加的项目
- 跟踪用户的兴趣并显示相应的广告
- 减少服务器负载
- 为访问者提供更快的响应

# 89: 如何设置和获取 cookie？

答案：

我们可以如所述添加 cookie：

```java
Cookie myCookie = new Cookie("name", request.getParameter("name"));
response.addCookie(myCookie);
```

上述代码将在 `myCookie` 对象中添加一个 cookie。

我们可以如所述获取 cookie：

```java
Cookie[] myCookies = request.getCookies();
if (myCookies != null && myCookies.length > 0) {
    Cookie myCookie = myCookies[0];
    System.out.println(myCookie.getValue());
}
```

上述代码从 `myCookie` 对象获取 cookie 值。

### 90: Cookie 有什么缺点？

答案：

- 从公共计算机访问网站时，cookie 会存储访问者的电子邮件地址，导致他人发送垃圾邮件
- 价值个人信息从 cookie 对象中被窃取
- 信用卡详情等敏感信息被 cookie 保留，会导致损失

因此，不应使用 cookie 存储敏感信息。

# 91: 跟踪浏览页面的访问者有哪些方案？

答案：

可以使用以下机制跟踪浏览页面的访问者：

- Cookies: 每个页面可以维护一个 cookie 来跟踪访问者
- 隐藏表单字段: 使用 `input` 标签存储用户重写的值
- URL 重写: 在这种情况下，我们可以将用户输入附加到服务器
- Session: 在这种情况下，我们可以将用户输入存储在 Session 中

# 92: 如何在 session 中存储和检索值？

答案：

如下所示值存储在 session 中：

```java
HttpSession session = request.getSession();
session.setAttribute("key", "value");
```

检索值：

```java
String value = (String) session.getAttribute("key");
```

```java
HttpSession mySession = request.getSession(true);
session.setValue("mobile", request.getParameter("mobile"));
```

在上述代码中，手机号被存储在 session 对象 `mobile` 中。

可以像下面一样从 session 获取该值：

```java
session.getValue("mobile");
```

在上述代码中，从 session 对象 `mobile` 中获取了手机号。

# 93: 解释会话跟踪（Session tracking）。

答案：

会话跟踪是维护用户会话的一种极佳技术解决方案。它使用 `HttpSession` API 来查找会话并创建新的会话。

会话跟踪用于存储关于客户端的上下文信息，因为服务器并不知道客户端的信息。例如，在在线购物购物车中，访问者经常向购物车添加一些物品，突然之间由于网络问题，他与网页断开了连接。一旦网络问题解决，访问者将能够在会话跟踪的帮助下看到购物车中添加的物品。

# 第 4 章

# JSP

## 94: 为什么我们应该避免在 JSP 中使用脚本段（scriptlets）？

**答案：**

虽然脚本段在 JSP 中被广泛使用，但由于以下原因，理想情况下应该避免使用。

- a) 可读性 – JSP 文件中断断续续的脚本段代码完全不可读。至少如果代码是写在一个块中的，那么这些代码是可读的。JSP 中遵循的通用编码方法是在需要的地方打开和关闭脚本标签并包含服务端逻辑。这降低了可读性，进一步影响了可维护性。
- b) 可维护性 – 代码的重复程度使其无法包含在多个地方，而且管理分散在客户端脚本和 HTML 之间的杂乱脚本段代码非常困难。
- c) 可重用性 – 脚本段代码无法重用，因为它们没有被写为命名块。这进一步使得它们的可替换性降低，且不符合面向对象的原则（JAVA/J2EE 面试中常见问题）。
- d) 可调试性 – 如果脚本段代码出现任何问题，用户将收到空白页面，这导致脚本段无法调试。
- f) 可测试性 – 由于脚本段分散在页面上，不适用于单元测试。
- g) 面向对象概念缺失 – 脚本段代码没有在块下命名，因此它们不可继承的，你无法对它们应用组合原则。因此，当我们使用脚本段时，面向对象编程的基本概念就丢失了。

## 95: JSP 编译是什么意思？

答案：

当客户端第一次请求页面时，JSP 文件会被编译并存储在内存中。你也可以使用 Java 命令行中的 `jspc` 命令来预编译 JSP 文件。其语法为 `jspc [options] <file_name>`。当你想要向用户隐藏源代码时可以执行此操作。你可以预编译最终的 JSP 文件，这些文件将作为包存储在 `jsp` 包下。你可以指定各种参数，例如源目录、目标目录、失败编译的文件名以及成功编译的文件名、第一个 JSP 的目标类名，除了预编译之外还有许多其他选项。

## 96: JSP 中的生命周期方法有哪些？

答案：

JSP 基本上三个生命周期方法：`jspInit()`、`jspService()` 和 `jspDestroy()`。`jspInit()` 方法在 JSP 页面首次被请求时仅调用一次。它将包含初始化客户端与服务端通信所需的所有初始参数。`jspService()` 方法每次浏览器请求页面时都会调用，该方法接受请求和响应对象作为参数。`jspDestroy()` 在 JSP 实例不再需要时被调用。这是 jsp 实例调用的最后一个方法。

## 97: 如何在 JSP 页面内部设置和删除 cookie？

答案：

在 JSP 页面内部设置或删除 cookie 均使用响应对象的 `addCookie` 方法。区别在于 `setMaxAge()` 和 `setPath()` 方法，这些方法将待删除 cookie 的年龄设置为零，并将路径设置为当前。示例代码段将进一步说明：

```jsp
<%
// 创建新 cookie
Cookie myNewCookie = new Cookie("myName", "myValue");
response.addCookie(myNewCookie);

// 删除 cookie
Cookie myNewCookie1 = new Cookie("myNewName", null);

// 这将 cookie 的年龄设置为零
myNewCookie1.setMaxAge(0);
myNewCookie1.setPath("/");
response.addCookie(myNewCookie1);
%>
```

## 98: JSP 的作用是什么？

答案：

JSP 指 Java Server Pages（Java 服务器页面）。它是一种服务端编程语言，使我们能够创建静态 HTML 并生成动态内容。

使用 JSP，我们可以借助 JSP 对象和结构创建表示层，在网页中显示内容。JSP 得到了广泛支持，它可以与任何 Web 服务器配合使用，并在不更改源代码的情况下在所有操作系统上运行。

开发者创建表示层以通过 JSP 对象和结构在网页中显示内容。

## 99: 什么是 JSP 构造（constructs）？

答案：

JSP 使用以下三种构造来构建页面：

a) 脚本段（Scriptlets）：允许在页面中使用 Java 代码
b) 指令（Directives）：用于控制页面的整体结构
c) 动作（Actions）：允许使用组件

## 100: 什么是脚本元素（scripting elements）？

答案：

脚本元素用于在页面中插入 Java 代码。JSP 有三种类型的脚本元素，它们是：

- a) 表达式（Expressions） – `<%= %>` 用于显示输出
- b) 脚本段（Scriptlets） – `<% %>` 用于定义代码处理
- c) 声明（Declarations） – `<%! %>` 用于定义方法
- d) taglib: 这用于定义自定义标签并导入现有的标签库

## 106: 请举例说明如何使用 page 指令。

答案:

下面的代码描述了如何使用 page 指令：

```jsp
<%@ page import="java.util.ArrayList" %>
<%@ page import="com.core.MyList, com.core.MyVector" %>
<%@ page contentType="text/plain" %>
```

在上述代码中，我们使用了 page 指令来导入 Java 类、自定义类，并设置浏览器中内容类型的显示格式。

## 107: 解释 page 指令的属性：import, session, buffer 和 extends。

答案:

page 指令的属性：import, session, buffer 和 extends 解释如下所示：

- a) import: 此属性用于导入 Java 类文件
- b) session: 此属性用于将 session 设置为 true 或 false
- c) buffer: 此属性用于以千字节（KB）设置缓冲区值
- d) extends: 此属性用于在 Java 页面中声明父类

## 108: 解释 page 指令的属性：autoflush, info, errorPage 和 isErrorPage。

答案:

page 指令的属性：autoflush, info, errorPage 和 isErrorPage 解释如下所示：

- a) autoflush: 此属性用于指定输出是否应该自动刷新
- b) info: 此属性用于在 Java 页面中设置静态值
- c) errorPage: 此属性用于在 JSP 处理过程中抛出任何异常时提供 Java 页面的相对 URL
- d) isErrorPage: 此属性用于将值设置为 true 或 false

## 109: page 指令的等效 XML 语法是什么？

答案:

page 指令可以如下所示在 XML 中声明：

```xml
<jsp:directive.page import="java.util.ArrayList" />
```

我们可以在 Java 页面中使用上述代码行，它是 page 指令的与 XML 兼容的语法。

## 110: 如何在 XML 语法中显示动态参数值？

答案:

在 JSP 中，我们可以通过以下代码利用 XML 语法显示动态参数值：

```jsp
<html>
<body>
<%
  String strValue = request.getParameter("myParam");
%>
The parameter value is
<jsp:expression>strValue</jsp:expression>
</body>
</html>
```

所以，我们使用了 `<jsp:expression>` 标签在 Web 浏览器中显示动态参数值。

## 111: 请举例说明 ‘include’ 指令。

答案:

‘include’ 指令用于在 Java 页面代码中包含一个文件。下面的代码描述了如何使用 include 指令：

```jsp
<%@ include file="header.jsp" %>
```

在上述代码中，我们使用了 include 指令来包含一个文件，该文件将在运行时被处理并在浏览器中显示。

## 112: include 指令的等效 XML 语法是什么？

答案:

‘include’ 指令可以如下所示在 XML 中声明：

```xml
<jsp:include page="footer.jsp" flush="true" />
```

我们可以在 Java 页面中使用上述代码行，它是 include 指令的与 XML 兼容的语法。

### 113: jsp:plugin 元素的作用是什么？

答案:

`jsp:plugin` 元素用于在网页中包含 applet。它是 applet 标签的替代方案。`jsp:plugin` 元素可以如下所示使用：

```jsp
<jsp:plugin type="applet" code="HeaderApplet.class" width="900" height="250">
</jsp:plugin>
```

在上述代码中，我们使用了四个属性：type, code, width 和 height。要显示 applet，type 的值应指定为 ‘applet’，code 的值应包含 applet 的名称。

### 114: jsp:params 元素的作用是什么？

答案:

`jsp:params` 元素用于向网页传递参数值。`jsp:params` 元素可以如下所示使用：

```jsp
<jsp:plugin type="applet" code="HeaderApplet.class" width="900" height="250">
  <jsp:params>
    <jsp:param name="MyParam1" value="MyValue1" />
    <jsp:param name="MyParam2" value="MyValue2" />
  </jsp:params>
</jsp:plugin>
```

在上述代码中，我们在 `jsp:plugin` 元素内部使用了 `jsp:params`，`jsp:param` 元素用于指定参数名称和值。

## 115: 创建 bean 类时需要考虑的重要点有哪些？

答案:

以下是创建 bean 类时需要考虑的重要点：

- bean 类应该有一个空参数构造函数或零参数构造函数
- bean 类不应包含公共实例变量或字段
- bean 类应该具有 getter 和 setter 方法来访问持久化值

### 116: 你如何在 JSP 中包含 bean 类？

答案:

如下所示在 JSP 中包含 bean 类：

```jsp
<jsp:useBean id="service" class="com.MyService" />
```

在上述代码中，我们使用了 `jsp:useBean` 动作来声明并实例化一个 JavaBean 组件。

## 124: 解释细粒度（fine-grained）和粗粒度（coarse-grained）接口

答案：

当接口包含较大的组件块或一组细粒度组件，而不是散落在应用程序中的较小组件块时，它就变成了粗粒度的。细粒度组件是较小的代码或数据单元，根据需要通过关系相互连接。一个区分客户（Customer）和账户（Account）对象的经典示例：在粗粒度接口中，客户对象将包含账户号和余额的详情。在细粒度接口中，客户详情是独立的、地址详情是独立的、账户详情也是独立的，且它们都通过关系链接在一起。

### 125: 解释 Session bean（会话豆）和 Entity bean（实体豆）之间的区别

答案：

实现 Enterprise Bean 接口的 Java 类是 Entity Bean。这些通常用于包含数据实体。Entity Bean 有两种类型：CMP（容器管理持久化）或 BMP（豆管理持久化）。Session bean 可以是有状态的（Stateful）或无状态的（Stateless）。会话首先在客户端和 servlet 之间建立。有状态的会话在客户端和服务端之间的各种方法调用之间维护一个状态。无状态的会话在方法调用之间不维护状态。Session bean 用于调用业务方法和逻辑，而 Entity bean 是实际包含数据的数据库对象。Entity bean 是持久的，而 Session bean 是瞬态的。

## 126: 你对 EJB 拦截器（Interceptor）了解些什么？

答案：

拦截器是其调用优先级高于被调用方法的方法。通常，拦截器用于在方法处理之前检查和验证传递的参数或进行安全检查。拦截器的另一个用途是在不影响 EJB 其他代码的情况下记录日志和分析操作。拦截器可以是方法级、类级或包级。默认级拦截器适用于应用程序中的所有 EJB。当存在多个拦截器时，首先调用默认级拦截器。类级拦截器适用于类中的所有方法，其优先级次于默认拦截器。方法级拦截器在方法执行之前被调用，在三种类型的拦截器中优先级最低。

### 127: 扩展并解释 ACID。

答案：

ACID 是 Atomic（原子性）、Consistent（一致性）、Isolation（隔离性）和 Durable（持久性）的缩写，是 EJB 事务的基本准则。

- a) Atomic（原子性） – 意味着事务要么执行所有，要么完全不执行。
- b) Consistent（一致性） – 所有事务必须保持一致，开发者必须在事务级别和应用程序级别确保这种一致性。
- c) Isolation（隔离性） – 事务必须允许独立运行，不受其他进程或事务的干扰。
- d) Durable（持久性） – 要求所有属于事务的数据在事务完成之前永久地写入存储系统中。这将确保数据不会丢失。



## 128: EJB 如何帮助管理数据库实体映射？

答案：

EJB 支持四种实体关系：一对一、一对多、多对一和多对多。EJB 拦截器注解用于映射数据库实体关系。拦截器定义在单独的包中，作为头文件与主 Java 类中包含的基础 Java 包一起引入。所有的数据库连接和关系映射都是使用 Hibernate 在后台完成的。在需要的地方包含类级和方法级拦截器，这将执行所需的映射并从数据库中获取详情。

## 129: EJB 组件必须创建哪些类/接口？

答案：

为 EJB（企业级 Java Bean）组件必须创建以下类/接口：

- a) Home 接口 (`EJBHome`)
- b) Remote 接口 (`EJBObject`)
- c) 业务逻辑（bean 类）
- d) 上下文对象 (`Context objects`)
- e) XML 部署描述符

## 130: Enterprise Java Beans 有哪些类型？

答案：

## 133: 什么是部署描述符（deployment descriptor）？

答案：

部署描述符是一个 XML 文件（扩展标记语言），在其中我们指定 EJB 的事务、安全和持久化细节。在此文件中，我们还指定了如何部署应用程序（J2EE）的每个部分或组件。

EJB 容器在运行时根据部署描述符中指定的值自动调用服务。

## 134: 什么是 bean 类（bean class）？

答案：

bean 类是由豆开发者创建的 Java 类，包含业务逻辑实现方法。根据 Enterprise Java Bean 的要求，bean 类继承自 `javax.ejb.EntityBean` 或 `javax.ejb.SessionBean`。

## 135: 解释上下文对象（context object）。

答案：

上下文对象包含关于实例当前状态的信息。企业 Java Bean 容器使用上下文对象协调事务、安全、持久化等系统服务，EJB 容器为每个 EJB 实例生成上下文对象。SessionBean 有 `SessionContext`，而 EntityBean 有 `EntityContext`。

## 136: Session bean 有哪些类型？

答案：

session bean 有两种类型，它们是：

- a) 有状态会话豆（Stateful session bean）：在整个方法调用（业务逻辑）过程中维护数据状态，即维护特定客户端会话
- b) 无状态会话豆（Stateless session bean）：在方法调用过程中不维护数据状态。这种豆利用了 EJB 的池化功能。

## 137: 远程接口（remote interfaces）有哪些方法？

答案：

以下是远程接口的方法：

- a) `getEJBHome()`: 返回 session bean home 接口的引用
- b) `getPrimaryKey()`: 此方法返回 session bean 的主键
- c) `getHandle()`: 返回 EJB 对象的句柄（handle）
- d) `isIdentical()`: 此方法测试传递的企业 bean 对象是否与调用的企业 bean 对象相同
- e) `remove()`: 此方法移除一个豆（会话）对象

## 138: Home 接口（home interfaces）有哪些方法？

答案：

以下是 home 接口的方法：

- a) `getEJBMetaData()`: 此方法允许客户端获取关于关企业 bean 的信息
- b) `remove(Handle handle)`: 通过句柄移除 EJB 对象。句柄通过 `getKey()` 方法检索
- c) `remove(Object primaryKey)`: 通过主键移除 EJB 对象
- d) `getHomeHandle()`: 获取 home 对象的句柄。客户端使用此对象存储指向实体 bean 远程 home 接口的引用

## 139: 本地接口和远程接口提供哪些服务？

答案：

以下是本地接口和远程接口提供的服务：

- a) 返回 session 对象的 home 接口
- b) 移除 session 对象
- c) 委托 session bean 实例的方法调用
- d) 测试 session 对象是否与另一个 session 对象相同

## 140: 解释 session bean是如何暴露给客户端的。

答案：

session bean 通过以下方式暴露给客户端：

- a) `EJBHome` 创建 session bean 实例和 `EJBObject`
- b) `EJBObject` 为会话豆（session bean）的方法提供了访问支持
- c) Stub（Stub）作为远程 `EJBObjects` 的代理
- d) 调用和分发机制由 tie 类提供，该类将代理绑定到 `EJBObject`

## 141: 解释本地客户端（local client）。

答案：

会话豆的客户端称为本地客户端。本地客户端通过本地接口（`javax.ejb.EJBLocalObject`）和本地 home 接口（`javax.ejb.EJBLocalHome`）访问会话豆。

本地客户端作为会话豆存在于 JVM 内部，它们是依赖于位置的。本地客户端通过引用方式将对象作为参数传递的方法。

## 142: 解释远程客户端（remote client）。

答案：

会话豆的客户端称为远程客户端。远程客户端通过远程接口（`javax.ejb.EJBObject`）和远程 home 接口（`javax.ejb.EJBHome`）访问会话豆。

远程客户端通过 EJB 容器访问基于 CORBA 的应用程序，该应用程序使用远程方法调用互联网拦截对象中间件协议（Internet Inter ORB Protocol），这是一种非 Java 的程序。

## 143: 我们什么时候需要使用 EJB？

答案：

在以下场景中我们需要使用 EJB（Enterprise Java Beans - 会话豆和实体豆）：

- a) 为了跨方法调用存储客户端信息，使用有状态会话豆（stateful session bean）
- b) 对于持久化数据，使用实体豆（entity bean）
- c) 向应用程序服务器或 EJB 容器通信活动客户端的存在，使用有状态会话豆
- d) 为了调用 EJB 容器的池化功能，使用无状态会话豆（stateless session bean）

## 144: 如何管理豆的持久化？

答案：

管理豆持久化有两种方法。它们是：

- a) BMP（豆管理的持久化）：在这种情况下，我们可以通过管理一个豆类来管理持久化
- b) CMP（容器管理的持久化）：在这种情况下，容器负责管理持久化

## 145: 解释豆管理的持久化（bean managed persistence）。

答案：

实体豆实现了豆管理的持久化。在这种情况下，豆通过直接的 DB（数据库）调用来存储和检索信息。

实体豆使用 JDBC（Java 数据库连接）或 SQLJ 从数据库中存储和检索信息。

## 146: 解释容器管理的持久化（container managed persistence）。

答案：

实体豆实现了容器管理的持久化。在这种情况下，容器使用标准 API 访问数据库。

容器管理的持久化使得应用程序可以使用任何数据库。容器还提供了工具，将实体豆的实例变量映射到对底层 DB（数据库）的调用。

## 147: 解释你将如何创建无状态会话豆的 home 接口。

答案：

无状态会话豆的 home 接口可以如下：

```java
import javax.ejb.*;
import java.rmi.*;
public interface MYSLSRemoteHome extends EJBHome {
    public MySLSRemote create() throws RemoteException, CreateException;
}
```

该接口作为 EJB 对象的工厂。豆代码中的 `create()` 方法对应于 `ejbCreate()` 方法。

## 148: 解释你将如何创建无状态会话豆的远程接口（remote interface）。

答案：

无状态会话豆的远程接口可以如下：

```java
import javax.ejb.*;
import java.rmi.*;
public interface MYSLSRemote extends EJBObject {
    public String getMessage() throws RemoteException;
}
```

该接口在客户端需要调用 EJB 对象时使用。该接口的职责是将后续调用委托给企业豆（enterprise bean）。

## 149: 解释 InitialContext。

答案：

`InitialContext` 是一个类，作为客户端与 JNDI（Java 命名目录接口）的接口。`InitialContext` 包含了允许客户端绑定命名服务如 JNDI、CORBA 和 DNS（域名命名服务）的信息。

如果 `InitialContext` 对象出现问题或在调用其方法之一时出现问题，会抛出 `javax.naming.NamingException`。

## 150: EJB 容器中池化（pooling）的好处是什么？

答案：

以下是 EJB 容器中豆池化的好处：

- a) 与多个用户共享资源
- b) 我们可以在部署描述符中指定用于池化和重用的实例
- c) 允许服务器（应用程序）处理高流量请求

## 151: 在实体豆和资源之间使用 DAO 的好处是什么？

答案：

以下是使用 DAO（数据访问对象）的好处：

- a) CMP（容器管理的持久化）支持多个数据库
- b) 它支持非数据类型
- c) 它支持遗留应用程序
- d) 它支持各种 SQL 服务器
- e) 它提供了可移植性

## 152: 解释 EJB 容器在管理生命周期中的作用。

答案：

以下是 EJB 容器的作用：

- a) 容器用实例填充池
- b) 容器调用豆类中的 `create()` 方法
- c) 容器返回 home 对象的引用
- d) 容器调用豆类中的 `ejbPassivate` 方法
- e) 容器为客户端调用实体豆的业务方法
- f) 容器最终将豆移动到池

## 153: CMP 的好处是什么？

答案：

以下是 CMP（容器管理的持久化）的好处：

- a) 它具有特定的容器搜索功能
- b) 它支持所有现有的数据库

## 154: BMP 的好处是什么？

答案：

以下是 BMP（豆管理的持久化）的好处：

- a) 实体豆代码是独立于容器的
- b) 可以使用 Java 数据库连接 API（应用程序接口）访问数据库
- c) 它支持非数据类型
- d) 它支持各种 SQL 服务器

## 155: CMP 的缺点是什么？

答案：

以下是 CMP（容器管理的持久化）的缺点：

- a) 可移植性：可能会丢失其他 EJB 的移植性
- b) 算法：可以使用容器支持的算法
- c) 效率：考虑到性能，生成的 SQL 有时是高效的
- d) 访问：源代码开发者无法访问视图

## 156: BMP 的缺点是什么？

答案：

以下是 BMP（豆管理的持久化）的缺点：

- a) 特定数据库：由于开发了特定数据库的豆，如果需要访问多个数据库，豆开发者必须重写代码
- b) SQL 知识：豆提供者必须具备 SQL 知识
- c) 时间：开发豆持久化的豆需要花费 5 倍的时间

## 157: 如何使用 BMP 实现持久化？

答案：

通过以下两种类型的方法来实现持久化数据。它们是：

- `ejbLoad`：该方法用于与企业 Java 豆容器启动数据库通信
- `ejbStore`：该方法用于通过手动编码使用 JDBC API 存储数据

## 158: 解释查找方法（finder methods）。

答案：

查找方法以 `find` 为前缀，并在实体豆的 home 接口中创建。例如，`findPrimaryKey()` 是查找方法，用于根据唯一主键对象从 home 接口识别实体豆对象。

```java
MyRemoteHome myHome = (MyRemoteHome) java.rmi.PortableRemoteObject.narrow(initialContext.lookup("java:obj/book"), MyRemoteHome.class)
Book book = myHome.findPrimaryKey("91-7822-323-6");
```

上述示例演示了 bean 开发人员如何使用 findByPrimaryKey 来检索数据。

## 159: 实体 bean（Entity bean）生命周期的状态有哪些？

答案：

以下是实体 bean 生命周期的状态：

- a) 空状态（Null state）：在此状态下，bean 的实例不存在
- b) 池化状态（Pooled state）：在此状态下，bean 的实例存在，但未与任何实体 bean 对象关联
- c) 就绪状态（Ready state）：在此状态下，bean 的实例与实体 bean 对象关联，并具有身份标识

## 160: 容器在实体 bean 生命周期周期内调用了哪些方法？

答案：

在实体 bean 生命周期周期内，会调用以下方法：

- a) `ejbActivate()`：当 bean 实例就绪并与池中的实体 bean 对象关联时，会调用此方法
- b) `ejbLoad()`：容器使用此方法从数据源调用数据
- c) `ejbStore()`：容器使用此方法将数据持久化地存储在数据资源中
- d) `ejbRemove()`：通过此方法移除与 bean 关联的实例，并从 home 接口或远程接口调用
- e) `ejbPassivate()`：EJB 容器使用此方法将 bean 实例与 EJB 对象解关联并发送到池中

## 161: 实体 bean（entity beans）的用途是什么？

答案：

以下是实体 bean 的用途：

- a) 具有唯一标识的领域对象，供多个客户端共享
- b) 强制数据完整性和持久化
- c) 数据源中的记录，而不是与客户端维护会话
- d) 用于 BMP（Bean 管理持久化）或 CMP（容器托管持久化）
- e) 缓存数据从而重用数据并防止频繁的数据库连接

## 162: 部署描述符（deployment descriptor）中指定了哪些元素？

答案：

部署描述符指定了以下元素：

- a) session：将 bean 定义为 session bean 而不是实体 bean
- b) session-type：我们可以将 session 定义为无状态（stateless）或有状态（stateful）
- c) `enterprise-beans`：使用此项，可以将 bean 声明为 session bean 或实体 bean
- d) `ejb-name`：用于指定 session bean 或实体 bean 的唯一名称
- e) ejb-jar：这是部署描述符的根元素
- f) ejb-class：用于指定企业 bean 的类
- g) home：用于指定企业 bean 的 home 接口
- h) remote：用于指定企业 bean 的远程接口
- i) transaction-type：用于指定事务是由 EJB 容器执行还是企业 bean 执行

## 163: 解释如何为有状态 session bean（stateful session bean）创建 home 接口。

答案：

我们可以按照如下方式为有状态 session bean 创建 home 接口：

```java
import java.rmi.*;
import javax.ejb.*;

public interface MySFSRemoteHome extends EJBHome {
    public MySFSRemoteHome create(int i) throws
    RemoteException, CreateException;
}
```

home 接口中的 `create()` 方法对应于 bean 代码中的 `ejbCreate()` 方法。

## 164: 解释如何为有状态 session bean 创建远程接口（remote interface）。

答案：

我们可以按照如下方式为有状态 session bean 创建远程接口：

```java
import java.rmi.*;
import javax.ejb.*;
public interface MySFSSRemote extends EJBObject {
    public int size() throws RemoteException;
}
```

当客户端想要调用 EJB 对象时，它们必须使用这个远程接口。EJB 容器负责将调用委托给实际的 bean 代码。

## 165: 解释如何创建一个有状态 session bean 类（stateful session bean class）。

答案：

我们可以按照如下方式创建有状态 session bean 类：

```java
import javax.ejb.*;
public class MySFSBean implements SessionBean {
    private SessionContext sContext;
    private int iCount;
    public void ejbCreate(int myParam) throws CreateException {
        this.iCount = myParam;
    }
    public void ejbActivate() {}
    public void ejbPassivate() {}
    public void ejbRemove() {}
    public int size() {
        return iCount;
    }
}
```



在上述代码中，当 bean 被创建时，计数器被赋予参数值。根据规范，我们必须实现业务方法 `size` 以及所有的 `ejbRemove`、`ejbActivate` 和 `ejbPassivate` 方法。

### 166: 什么是访问方法（accessor methods）？

答案：

当我们使用容器托管持久化（container managed persistence）时，为了访问数据存储，我们不直接使用读写方法。相反，我们使用作为访问方法的 `get` 和 `set` 方法。

例如，`getName()` 和 `setName(String name)` 是字段 `name` 的访问方法。

## 167: 解释 EntityContext。

答案：

EJB 容器通过 EntityContext 提供实体 bean 实例。EntityContext 提供与实体 bean 实例关联的任何对象引用，包括 EJB 对象、EJB 本 对象以及主键。

### 对 EJB 对象、EJB 本 对象和主键的访问

## 168: 解释 getEntityHome, getLocalHome 和 getCallerPrincipal。

答案：

- `getEJBHome()`：返回企业 bean 的远程接口。
- `getEJBLocalHome()`：返回企业 bean 的本地接口。
- `getCallerPrincipal()`：标识调用者主体。

## 169: 解释 getRollBack, setRollBack 和 getUserTransaction。

答案：

- `getRollBack()`：通过此方法可以标识现有事务是否已设置为回滚。
- `setRollBack()`：通过此方法，我们可以设置特定事务的结果。
- `getUserTransaction()`：此方法不应由实体 bean 调用，返回 `javax.transaction.UserTransaction`。

### 170: 解释事务（Transaction）。

答案：

事务是一个执行工作单元或原子操作的任务。如果任务执行失败，事务将撤销或回滚。事务通常被称为 ACID。ACID 指原子性、一致性、隔离性和持久性。

## 171: 容器托管事务可用哪些事务属性？

答案：

以下是容器托管事务：

- a) **Required（需要）**：在此情况下，如果事务不存在，容器将启动新事务。
- b) **RequiresNew（需要新事务）**：在此情况下，容器为方法调用创建事务。
- c) **Supports（支持）**：在此情况下，bean 可以在没有事务的情况下执行。
- d) **Unsupported（不支持）**：在此情况下，bean 不能在事务中调用。
- e) **Never（从不）**：在此情况下，bean 永远不会执行事务。
- f) **Mandatory（强制）**：在此情况下，每次方法调用都需要事务上下文。

## 172: 容器如何管理多个事务？

答案：

容器通过以下两种方式管理多个事务：

- a) EJB 容器实例化多个企业 bean，从而允许数据库处理与事务处理相关的所有问题。
- b) EJB 容器对企业 bean 的数据库状态获取排他锁，从而实现多个事务对实例的序列化访问。

### 173: 解释 JTS。

答案：

JTS 指 Java Transaction Service。它指定了 Java Transaction API 的事务管理器实现。它支持分布式事务，即由多个事务管理器支持多个数据库。通过 JTS，容器确保事务可以跨越多个容器。

### 174: EJB 容器提供哪些服务？

答案：

EJB 容器提供以下服务：

- a) **事务管理**：容器管理事务的启动、参与、回滚和提交。
- b) **生命周期管理**：包括 bean 的创建、销毁、激活和钝化。
- c) **持久化**：bean 不直接从数据库检索或存储数据，而是通过容器的帮助完成。
- d) **状态管理**：容器自动管理 bean 对象的状态。
- e) **远程访问（分布式）**：容器借助 RMI 和 IIOP 协议支持分布式的远程访问。
- f) **安全性**：容器会代表企业豆（Enterprise Beans）自动执行所有的安全检查。

## 175: EJB 框架作为架构有哪些优点？

答案：

EJB 框架作为架构的优点如下：

- a) EJB 架构是分布式的、可扩展的、可移植的、事务性的、多层的且安全的。
- b) EJB 服务器自动为企业豆组件管理线程、生命周期、事务和持久化等服务。
- c) 企业豆组件与平台无关，即它们可以在任何操作系统上执行。
- d) EJB 组件仅包含业务逻辑，因此允许开发者自由维护系统级代码。

### 176: 解释会话豆（Session Bean）的生命周期。

答案：

会话豆的生命周期可以如下：

- a) 使用 JNDI（Java 命名目录接口）服务，客户端定位豆的家对象（home object）。
- b) 使用家对象引用创建 EJBObject，从而创建豆类的实例。
- c) 被称为会话豆的豆类被分配一个会话上下文（session context）。
- d) 使用家引用调用 EJB 对象上的方法，并将方法调用传递给会话豆。
- e) 会话豆将结果返回给 EJB 对象，后者再将结果返回给远程接口。

## 177: 抽象持久化模式（abstract persistence schema）包含哪些信息？

答案：

抽象持久化模式包含以下信息：

- a) 为了管理每个实体，它有一个 `ej-name` 字段，其值必须是唯一的。
- b) 为了指定查询，每个实体豆使用 `abstract-schema-name`，其值必须是唯一的。
- c) 可以 `ejb-relation` 字段指定 ej 的关系。
- d) 为了指定关系角色，我们必须使用 `ejb-relationship-role` 字段。

### 178: EJB 客户端有哪些类型？

答案：

企业 Java Bean 客户端有两种类型。它们是：

- a) **家客户端（Home client）**：家客户端始终存在于企业 Java Bean 容器内部。
- b) **远程客户端（Remote client）**：远程客户端始终存在于企业 Java Bean 容器外部。

可以通过事务管理器让多个客户端访问企业 Java Bean 容器中的企业豆对象。

## 第 6 章：国际化与本地化

### 179: 什么是全球化（Globalization 或 G11N）？

答案：

全球化是为了使为本地市场创建的软件产品适用于全球市场所采用的方法。在使本地产品适用于全球市场时，需要考虑许多方面，而全球化涵盖了这些方面。其重点是面向全球市场营销完整的企业解决方案和管理支持。在这里，法律和经济因素受到了重视。在全球范围内，术语、图形、插图、使用的符号、颜色、字符集、字体、排版、格式、语言和样式都需要被考虑。

### 180: 什么是国际化（Internationalization）？

答案：

国际化是制作或准备代码以支持多种语言的过程。国际化既涉及向客户端呈现输出数据的应用程序，也涉及可以转换为相应语言和字符集的数据。因此，国际化允许应用程序适应新的语言和地区。

### 181: 什么是本地化（Localization）？

答案：

本地化是适应支持特定语言或区域的国际化应用程序。本地化涉及将数据翻译成特定语言并将其维护在文件中，以便应用程序访问它。该文件可以是一个属性文件（property file）。因此，本地化提供了国际化应用程序对特定国家或地区的适配。

### 182: 什么是区域（Locale）？

答案：

区域是一个包含特定区域和地区信息的环境。在本地化过程中，国际化应用程序会被适配到特定的区域。每个国家都有自己的区域。例如，美国拥有 `en_US` 区域，意大利拥有 `it_IT` 区域等。在这里，`en` 代表“语言”，`IT` 代表“地区”。这里 `it` 代表意大利语，而 `IT` 代表“区域差异”，即国家名称意大利。

### 183: 国际化应用程序的特征是什么？

答案：

国际化应用程序的特征如下：

- a) 应用程序将有一个 `.ear` 文件（企业归档文件），可以在全球范围内执行。
- b) 图形用户界面标签和消息不是硬编码在程序中的，而是存储在外部并动态检索。
- c) 日期和货币以终端用户所在的地区和语言显示。
- d) 为了支持新语言，应用程序不需要重新编译。

### 184: 区域（locale）是通过哪些元素标识的？

答案：

区域通过以下三个元素标识：

- a) **语言（Language）**：它是区域的基本标识。它包含一个有效的 ISO 639 标准（两个字母的语言代码）。每个国家都有一个或多个语言，通过两个字母来识别语言。例如，英语的 `en` 和法语的 `fr`。
- b) **区域差异（Regional Variation）**：它是国家的标识符。它包含一个有效的 ISO 3166 标准（两个字母的国家代码）。例如，法国的 `FR` 和美国的 `US`。
- c) **变体（Variant）**：它是国家或特定系统的标识符。它包含...例如，`WIN` 代表 Windows，`MAC` 代表 Macintosh。

### 185: 可以用 java.util 进行本地化吗？

答案：

我们可以使用 `java.util.Properties` 进行本地化。该类表示字符并以流的形式保存。例如：

```java
Properties appProp = new Properties();
String strProp = "usr/MyProp.txt";
appProp.load(new BufferedInputStream(new FileInputStream(strProp)));
String serviceValue = appProp.getProperty("serviceKey");
```

Properties 类表示区域。

### 186: 解释资源包（ResourceBundle）。

答案：

`ResourceBundle` 是一个属于 `java.util` 的类。它定义了区域的命名规范，并用于按区域组织资源。ResourceBundle 拥有特定区域的对象并可以加载终端用户。

### 187: ResourceBundle 有哪些特性？

答案：

ResourceBundle 具有以下特性：

- a) 内容可以本地化，即内容可以翻译成不同的语言。
- b) 让应用程序处理多个区域。
- c) 应用程序可以修改以支持额外的区域。

### 188: 解释字符集（Character Sets）。

答案：

字符集是一组图形或文本符号，映射到称为代码点（code points）的正整数。美国标准信息交换代码（ASCII）字符集用于表示英语。它包含大写和小写字母、数字、标点符号和符号。例如，B 的 ASCII 编码是 66。ASCII 仅适用于英语。因此，为了支持其他语言，创建了 ISO 8859 字符集。

### 189: 解释 Unicode（Unicode码）。

答案：

Unicode 定义了一个通用且标准的（ISO 10646）字符集。它代表了全球使用的所有字符集并可以扩展。因此，Unicode 是 ISO 8859 字符集的替代。Java 使用 Unicode 2.x 对字符编码。每个 Unicode 字符使用 2 个字节。Java 将字符串对象和字符表示为编码后的 Unicode。因此，用 Java 语言编写的程序可以处理多种语言的数据。

### 190: 解释 UTF。

答案：

UTF 代表 Unicode 转换格式。它是一种多字节编码格式，以 1 到 3 个字节存储字符。这里 U 也代表通用字符集（UCS）。UTF 比 Unicode 更紧凑、更高效，是广泛使用的编码方案。Java 推荐 UTF-8，因为它与现有的网络内容兼容，并且可以访问 Unicode 字符集。UTF-8 表示 UTF 的 8 位形式。

### 191: 解释排序（Collation）和排序器（Collator）。

答案：

排序（Collation）是一个根据特定区域习惯对字符串进行排序的过程。不同语言的字母表不同，因此我们需要一种独特的方法根据语言对字符串进行排序。排序功能被引入属于 `java.text` 包的抽象类 `Collator` 中。它用于提供与区域敏感的字符串比较，在 Java 编程语言中执行排序过程。

### 192: JSP 中使用哪些属性来控制编码？

答案：

在 JSP 中，页面指令（page directive）中使用了两个属性来控制编码。它们是：

- a) **contentType**：在其中，我们可以指定将要使用的字符集和内容的格式 `<@ page contentType="text/html; charset=ISO-8859-1" %>`。在上面的代码行中，我们使用了 html 格式和内容的 ISO-8859 字符集。
- b) **pageEncoding**：在其中，我们可以指定内容显示时使用的字符集 `<@ page pageEncoding="UTF-8" %>`。在上面的代码行中，我们使用了 UTF-8 类型的编码。

### 193: 解释 Format 类。

答案：

`Format` 是属于 `java.text` 包的类。它是一个抽象类，用于格式化本地化信息：例如：消息、日期和数字。

Format 类使用 `format()` 方法：

- a) 将本地化对象格式化为字符串
- b) 使用 `parseObject()` 将字符串转换为对象

### 194: 如果应用需要部署在不同的区域，它的哪些方面需要进行更改？

答案：

如果需要部署在不同的区域，以下方面需要进行更改：

- a) 内容、数字和日期的呈现方式
- b) 组件上的标签
- c) 颜色、声音和图像
- d) 页面中显示数据的排序（顺序）
- e) 读取和写入文本文件内容

### 195: Java 支持哪些字体名称和字体样式？

答案：

Java 支持的五种字体名称是：Serif（衬线）、Sans-serif（无衬线）、Monospaced（等宽）、Dialog（对话）和 DialogInput（对话输入）。

Java 支持的四种字体样式是：bold（粗体）、italic（斜体）、plain（正体）和 bold-italic（粗斜体）。这些是标准名称，它们映射到操作系统默认安装的物理字体。字体名称和样式的映射由 `font.properties` 处理。

### 196: Java 用于创建国际化应用的特性有哪些？

答案：

以下是用于创建国际化应用程序的 Java 特性：

- a) `java.util.Properties` 类用于获取特定文本（键）的本地化值
- b) `java.util.Collator` 和 `CollatorKey` 类用于根据本地化单词对数据排序
- c) `java.text.NumberFormat` 和 `DateFormat` 类用于格式化货币、数字和日期
- d) `java.io.InputStreamReader` 和 `OutputStreamWriter` 用于文件的读写
- e) 在 JSP 中使用了 `contentType`、`pageEncoding` 和 `java.util.Locale` 属性
- f) `java.util.ResourceBundle` 类用于处理本地化文本

### 197: Format 类的子类有哪些？

答案：

`java.text.Format` 类有三个子类。它们是：

- a) `java.text.NumberFormat`：用于格式化货币和数字
- b) `java.text.DateFormat`：用于格式化时间和日期
- c) `java.text.MessageFormat`：用于格式化文本消息

### 198: 解释为什么 UTF-8 被认为是最佳编码选择？

答案：

UTF-8 被认为是最佳编码选择的原因如下：

- 它被几乎所有可用的网络浏览器支持
- 它提供了最广的字符集覆盖范围
- 它提供了高效的数据传输

### 199: 本地化 JSP 页面的方法有哪些？

答案：

本地化 JSP 页面有两种方法。它们是：

- 为每个区域创建一个 JSP 文件，并将其存储在服务器的不同目录中。根据客户端请求的区域，调用相应的 JSP 来显示相应的本地化内容
- 创建单个 JSP 并使用具有特定区域特定自定义标签的 `ResourceBundle`。这样，当客户端请求页面时，标签会从资源包中访问对应区域的文本

### 200: 为每个区域创建 JSP 的优势是什么？

答案：

以下是为每个区域创建 JSP 的优势：

- a) **个性化支持**：这为为每个区域自定义内容的结构和显示提供了完全支持
- b) **源文件清晰度**：每个区域的所有属性文件、资源包和 JSP 都保存在一处

### 201: 解释 I18N 和 L10N。

答案：

I18N 代表国际化（Internationalization），其中“I”代表首字母，18 代表首字母和尾字母之间的 18 个字符，“N”代表末尾字母。

L10N 代表本地化（Localization），其中“L”代表首字母，10 代表首字母和尾字母之间的 10 个字符，“N”代表末尾字母。

### 202: 解释 InputStreamReader。

答案：

`InputStreamReader` 是一个属于 `java.io` 包的类。它用于将字节转换为字符，即它根据编码读取字符。

### 203: 解释 OutputStreamWriter。

答案：

`OutputStreamWriter` 是一个属于 `java.io` 包的类。它用于将字符转换为字节流，即它根据编码写入字符。

### 204: 在 JSP 中使用 ResourceBundle 的优点和缺点是什么？

答案：

在 JSP 中使用 ResourceBundle 的优点是：

- a) **易于维护**：我们只需要修改 JSP 即可反映所有区域的更改
- b) **结构一致性**：所有区域的页面遵循相同的结构，只有数据不同
- c) **易于扩展**：我们可以轻松定义一个新的 ResourceBundle 来支持新区域

使用 ResourceBundle 的缺点是：

- a) **难以自定义**：很难为每个区域自定义结构
- b) **兼容性**：编码必须兼容

## 第 7 章：设计模式



## 205: 如何确保一个类是单例？单例类的缺点是什么？

**回答：**

单例类是允许形成实例实例类。它要么没有构造函数，要么有一个有构造函数并使用 `getInstance()` 方法来创建唯一的实例。你通过遵循标准模式来使类成为单例，例如同步 `getInstance()` 方法，或者在使用 Java 5 或更高版本时使用枚举。另一种常用方法被称为尽早初始化，即在类加载时无论是否被使用都会实例化。

线程安全的单例类可以通过同步静态 `getInstance()` 方法定义。使用内部静态辅助类也是实现单例类的有效方法。

单例类的主要缺点是它不可重用。我们只能创建该类的一个实例。它们没有遵循单一职责原则这一事实对单例类不利。它们为程序员提供的灵活性有限，且无法被子类。单例类定义中的同步块可能会系统变慢。

## 206: 什么是设计模式？

**回答：**

设计模式是面向设计者的程序，为特定背景下存在的问题提供解决方案。

设计模式用于解决软件工程过程中出现的常见问题。它还解释了问题的原因、可行的解决方案以及它的益处。有了设计模式，可以很容易识别新问题。

## 207: 设计模式的好处有哪些？

**回答：**

以下是设计模式的益处：

- a) 快速关注特定问题的解决方案
- b) 激发软件设计人员带来独特且新的想法
- c) 解决现实世界的问题并为设计讨论提供建议
- d) 记录领域特定的实践，从而在文档中记录知识
- e) 定义解决方案的场景、影响和结果

### 208: 解释 GoF。

**答案：**

GoF 指的是 Gang of Four（四人帮）。它指的是著名的四位作者：Ralph Johnson、Richard Helm、John Vlissides 和 Erich Gamma，他们在1995年编写并出版了《设计模式：可用面向对象架构的基础》一书。从那时起，设计模式变得更加流行。

### 209: 设计模式有哪些类型？

**答案：**

设计模式有三种类型。它们是：

- a) 创建型模式 (Creational Design Pattern)：这些是用于创建对象的对象的模式
- b) 结构型模式 (Structural Design Pattern)：这些模式与对象和类的组合有关
- c) 行为模式 (Behavioral Design Pattern)：这些模式与对象的职责和交互有关

### 210: 有哪些创建型设计模式？

**答案：**

以下是创建型模式：

- a) 工厂方法 (Factory Method)：这是最常用的模式
- b) 抽象工厂 (Abstract Factory)：这种模式用于创建一组多于一种类型的对象
- c) 构建器 (Builder)：这种模式是另一种创建对象的方法，类似于工厂方法和抽象工厂
- d) 单例模式 (Singleton)：这种模式是开发者频繁使用的最重要的模式之一
- d) 原型模式 (Prototype)：这种模式可以比克隆

## 211: 解释单例模式 (Singleton)。

**答案：**

单例模式的意图是确保一个类只有一个实例，并且它应该是全局访问点。它还确保了使用单例实例的对象始终使用同一个单例实例。

```
final public class Singleton {
    private Singleton() {
    }
}
```

上面的代码说明了如何创建一个单例类。

## 212: 解释工厂方法 (Factory Method)。

**答案：**

工厂方法的意图是指定一个创建对象的接口，但允许子类来决定要实例化的适当类。在这种模式中，客户端将永远不知道被实例化和返回的具体类。但客户端只需要知道抽象接口。与工厂方法模式相关的接口和类包括：

- a) `javax.ejb.EJBHome`
- b) `javax.ejb.EJBLocalHome`
- c) `java.text.Collator`
- d) `java.net.SocketFactory`
- e) `java.net.ContentHandlerFactory`

点 a) 和 b) 属于 J2EE，其余属于 J2SE。

## 213: 解释原型模式 (Prototype pattern)。

**答案：**

原型模式的意图是使用原型实例定义要创建的对象类型，并通过复制此原型来创建新对象。这个概念与 `java.lang.Object clone()` 方法相同。

这种模式允许我们在运行时删除或添加对象。它还允许通过修改现有的结构来定义新对象，并减少对子类的需求。这种模式还允许我们动态地用类配置应用程序。

## 214: 在什么场景下创建抽象工厂模式 (Abstract Factory pattern)？

**答案：**

在以下场景下必须创建抽象工厂模式：

- a) 当建议的系统需要是独立的，并且不想知道对象是如何表示、创建和组合的时
- b) 当旨在通过强制约束来让相关的对象一起使用时
- c) 当我们只想向用户提供接口而不是其实现时

### 215: 有哪些结构型设计模式？

**答案：**

以下是各种结构型设计模式：

- a) 装饰器模式 (Decorator pattern)：这种模式被认为是策略模式的皮壳
- b) 组合模式 (Composite pattern)：这种模式与迭代器 (Iterator) 和解释器 (Interpreter) 一起使用
- c) 代理模式 (Proxy pattern)：这种模式在需要控制访问时使用
- d) 适配器模式 (Adapter pattern)：这种模式用于访问不兼容的接口
- e) 桥接模式 (Bridge pattern)：这种模式用于将主功能与实现解耦
- f) 外观模式 (Facade pattern)：这种模式用于简化接口
- g) 享元模式 (Flyweight pattern)：这种模式允许人们高效地利用对象

## 216: 解释代理模式 (Proxy pattern)。

**答案：**

代理模式为对象提供一个占位符以控制对另一个对象的访问。常见的应用是虚拟代理和远程代理。代理（Surrogate）是代理模式的另一个名称。

在这种模式中，应用程序存在另一个工作空间，但远程代理隐藏了这一事实。虚拟代理可以根据需要创建对象。

## 217: 外观模式 (Facade pattern) 有什么好处？

**答案：**

以下是外观模式的好处：

- a) 为复杂的子系统提供简单的接口，而不是最小化子系统的选项
- b) 它可以保护客户端免受系统复杂性的影响
- c) 促进客户端和子系统之间的松耦合
- d) 每个子系统使用自己的外观模式，从而减少子系统之间的耦合

## 218: 在什么场景下创建适配器模式 (Adapter pattern)？

**答案：**

我们在以下场景下使用或创建适配器模式：

- a) 创建一个可重用的类，该类与没有该接口的类协作
- b) 当对象没有兼容的接口但我们想使用它时
- c) 我们想使用子类

## 219: 解释组合模式 (composite pattern)。

**答案：**

组合模式的意图是允许客户端执行层次结构。这种情况通常出现在门户应用程序中。这种模式定义了包含复杂对象的层次结构。这使得添加变得更容易。

## 220: 装饰器模式 (Decorator pattern) 有什么好处？

**答案：**

以下是装饰器模式的好处：

- a) 与静态继承相比提供了更大的灵活性
- b) 帮助开发者简化代码和目标
- c) 在这种模式中，更改是通过编码完成的

### 221: 有哪些设计模式？

**答案：**

以下是各种行为模式：

- a) 策略模式 (Strategy)：这是最常用的模式之一
- b) 迭代器 (Iterator)：这种模式解释了如何遍历对象
- c) 模板方法 (Template Method)：这种模式帮助我们强化工厂方法和策略模式
- d) 中介者 (Mediator)：这种模式作为中间层组件
- e) 观察者模式 (Observer)：这种模式是发布/订阅模型
- f) 责任链模式 (Chain of Responsibility)：这种模式用于链式传递
- g) 备忘模式 (Memento)：这种模式用于恢复和备份对象的状态
- h) 命令模式 (Command)：这种模式将调用者与执行者分离
- i) 状态模式 (State)：在这种模式中，对象改变其类并修改行为
- j) 访问者模式 (Visitor)：在这种模式中，对象对元素的结构进行操作
- k) 解释器模式 (Interpreter)：在这种模式中，语法被用于解释句子

## 222: 解释策略模式 (Strategy pattern)。

**答案：**

策略模式的意图是创建一个功能族，将其封装，并将它们创建为可交换的。在这里，功能独立于使用它的客户端。策略是策略模式的另一个名称。这种模式为静态继承提供了替代方案。这种模式通过在类内部定义行为消除了对条件语句的需求。

## 223: 中介者模式 (Mediator pattern) 有什么好处？

**答案：**

- 提供集中控制
- 独立组件变得更容易更简单的开发，因为它们不需要相互传递消息
- 协议（对象）被简化了
- 组件更加通用，因为它们不包含通信的逻辑
- 这种模式解耦了其他组件

### 224: 什么时候你会选择迭代器模式 (Iterator pattern)？

**答案：**

我们必须在以下场景使用迭代器模式：

- a) 在不需要知道对象的表示或内部结构的情况下访问集合对象
- b) 当我们需要支持多个遍历对象在
- c) 当我们需要一个通用的接口来遍历集合中的各种结构时

### 225: 请解释解释器模式（Interpreter pattern）。

**答案：**

解释器模式的意图是用解释器定义语言的语法，该解释器用于解释该语言中的句子。使用这种模式可以很容易扩展和更改语法，而且语法实现非常直观。当效率是首要考虑因素时可以使用这种模式。

### 226: 与命令模式（Command pattern）相关的 J2EE 特性有哪些？

**答案：**

以下是命令模式相关的两个 J2EE 特性：

- a) 根据容器（web）接收到的 HTTP（超文本传输）请求类型，调用 JSP 或 Servlet
- b) 根据分发到消息豆（Message beans）的消息内容，由消息豆调用业务逻辑

### 227: 你何时会使用访问者模式（Visitor pattern）？

**答案：**

访问者模式用于以下场景：

- a) 对具有不同接口的许多对象执行操作，而这些对象依赖于具体类
- b) 对对象执行无关且独立的操作
- c) 避免无关的操作导致类臃肿
- d) 定义新操作，但对象的结构很少变化

### 228: 请解释模板方法（Template Method）。

**答案：**

模板方法模式的意图是定义函数的骨架并将步骤推迟到子类中执行。这使得子类可以在不修改函数结构的情况下重新定义函数。这是通过 `HttpServlet` 实现的。这种模式提供了一种重用代码以避免重复的技术。如果我们要在子类中使用变化的算法而在一个类中使用不变化的算法，那么我们必须使用这种模式。

### 229: 请解释责任链模式（Chain of Responsibility）。

**答案：**

该模式的意图是避免将发送者的请求与接收者集成，请求由多个对象处理。请求以链的形式传递，直到某个对象处理该请求。

当将责任分配给对象时，这种模式减少了耦合并提高了灵活性。它还允许一组类表现得像单个类一样。当请求需要由多个对象处理、且处理器未知且请求是动态的时，我们使用这种模式。

### 230: 备忘录模式（Memento）和状态模式（State）的优点是什么？

**答案：**

以下是备忘录模式的优点：

- a) 该模式保留了所封装对象的边界
- b) 该模式简化了对象（源源者）

以下是状态模式的优点：

- d) 对象的状态是局部的，对于每个状态它划分了行为
- e) 对象的状态转换始终是显式的

# 第8章

# 消息（Messaging）

### 231: 什么是消息（Messages）？

**答案：**

消息是指本地机器或远程机器上的数据单元，可以在网络上传输或共享。数据可以是简单的文本，也可以是复杂的结构（例如：`HashMap`）。

在 Java 上下文中，通过对对象进行序列化，可以通过将数据转换为字节、在网络上传输或共享、创建对象的副本等方式轻松地转换消息。

### 232: 请解释中间层（middle tier）。

**答案：**

中间层由称为中间件的应用程序组成，该程序提供以下服务和业务解决方案：

- a) **消息（Messaging）**：接收和发送数据的能力
- b) **安全（Security）**：授权和验证用户的能力
- c) **命名（Naming）**：识别资源名称的能力
- d) **数据库管理（Database Management）**：访问 DB（数据库）服务器的能力

### 233: 请解释 MOM。

**答案：**

MOM 指消息面向型中间件（Message Oriented Middleware），主要用于消息传递。它是使应用程序能够在企业内部接收、发送和创建消息的基础设施。

MOM 通常以可靠且快速的方式以不同的格式交换和交付消息。MOM 的优势是它是事件驱动的。有多种消息供应商：

示例：HP、IBM、BEA、Oracle 等。

## 234: 请解释同步通信（synchronous communication）。

**答案：**

同步通信是一种通信方法，其中发出请求的客户端在接收到响应之前会被阻塞，无法处理任何后续命令。这种通信发生在双方之间：客户端（浏览器）和服务器。这种类型的通信的一个例子是信用卡授权。在这里，一旦刷了卡，接收方将等待服务器的响应以批准交易。

## 235: 请解释异步通信（asynchronous communication）。

**答案：**

异步通信是一种通信方法，其中发出请求的客户端永远不会被阻塞，他/她可以继续处理或其他进程或事务。异步通信的一个例子是电子邮件。即使关关电脑，人们也可以向你发送电子邮件。一旦你启动电脑，邮件客户端将加载你的消息。

### 236: 请解释 JMS。

**答案：**

JMS 指 Java消息服务（Java Messaging Service）。它是一种允许软件开发人员松耦合应用程序的中间件。它提供了一个 API（应用程序接口），通过该 API 我们可以接收、发送、读取和创建企业系统消息。JMS 是一种面向消息的产品，昂贵且复杂。它提供了一个接口（Java）来编写基础设施代码，并允许快速快捷地构建解决方案。

### 237: JMS 支持哪些消息模型？

**答案：**

Java Messaging Service 支持两种消息模型。

它们是：

- a) 发布/订阅（Publish/subscribe）：在该模型中，客户端可以发布或订阅
- b) PTP：PTP 指点对点模型，其中消息被发送到某一个点

JMS 规范要求消息供应商应支持上述任何一种模型。

### 238: 同步消息（synchronous messaging）的优点有哪些？

**答案：**

以下是同步消息的优点：

- a) 同步消息需要双方（客户端和服务器）处于激活状态。如果其中一方不活跃，事务将无法成功
- b) 在继续下一步操作或处理之前，消息必须被确认

### 239: 异步消息（asynchronous messaging）的优点有哪些？

**答案：**

以下是异步消息的优点：

- a) 这种类型的消息不受失败影响，因为它不需要或期望确认
- b) 这种类型的消息在软件、硬件或网络层面不受影响
- c) 通常情况下，消息不会丢失，但可能会延迟
- d) 当流量增加时，这种消息工作效果更好，因为它将请求留在队列中

## 240: 你在何时会使用异步消息？

**答案：**

以下是我们使用异步消息的场景：

- a) 如果我们不需要立即响应
- b) 如果我们需要对事务进行大量处理
- c) 如果我们希望使用高效的消息系统来使用系统

### 241: JMS 的优势有哪些？

**答案：**

以下是 Java消息服务的优势：

- a) 它提供了一种轻松集成不兼容系统的方法
- b) 它支持异步通信方法
- c) 它支持一种或多种通信类型
- d) 它支持事务型消息传递
- e) 它支持保证型消息传递

### 242: JMS 的组件有哪些？

**答案：**

以下是 JMS 的组件：

- a) 消息（Messages）：指应用程序之间传递的数据，定义了消息包含的信息类型
- b) 客户端（Clients）：指接收和发送消息的应用程序
- c) 对象（Objects）：由管理员维护和创建供 JMS 客户端使用的 JMS 对象
- d) JMS 提供者：运行 JMS 应用程序的主机应用程序，提供了消息应用程序所需的底层

### 243: 如何处理异常？

**答案：**

JMS 使用 `ExceptionListener` 接口，在执行或运行时发生任何问题时通过该接口通知应用程序。该接口识别 JMS 提供者的问题详情并告知 JMS 客户端。

为了处理异常，我们需要使用 `onError` 方法，该方法接受 `JMSException` 作为参数。该对象应该通过 `setExceptionListener` 方法注册，该方法接受会话中的参数监听器。

### 244: JMS 是如何确认消息的？

**答案：**

JMS 通过以下方式确认消息：

- a) `CLIENT_ACKNOWLEDGE`：由客户端通过调用 `acknowledge` 方法来确认消息。
- b) `DUPS_OK_ACKNOWLEDGMENT`：如果 JMS 供应商者失败，可能会发生消息重复。只有当消费者能够容忍重复消息时，我们才使用此模式。
- c) `AUTO_ACKNOWLEDGMENT`：在这种情况下，会话会自动为每条消息确认客户端。

## 245: 解释 JMS 的消息头（message headers）。

**答案：**

JMS 使用以下消息头：

- a) `JMSMessageID`：用于唯一标识每条消息。
- b) `JMSPriority`：优先级 9 最高，0 最低。不能保证高优先级消息比低优先级消息先执行。
- c) `JMSDeliveryMode`：此头部用于定义 JMS 交付模式为持久性（Persistent）或非持久性（Non-persistent）。
- d) `JMSRedelivered`：用于告知客户端其之前是否接收过该消息。
- e) `JMSExpiration`：用于以毫秒为单位设置消息过期时间。



## 246: JMS 的正文格式有哪些？

答案：

以下是 JMS 的消息正文格式：

- a) `TextMessage`：格式为 `String`，用于交换 XML 数据。
- b) `ByteMessage`：用于匹配旧版消息。
- c) `ObjectMessage`：表示对象集合或可序列化对象。
- d) `MapMessage`：类似于 `HashMap`，具有键值对。
- e) `StreamMessage`：表示用于顺序读取的原始类型值之流。

## 247: JMS 中管理对象的类型有哪些？

答案：

在 JMS 中，有两种类型的管理对象。它们是：

- a) `Destination`（目的地）：包含与 JMS 供应商提供的配置相关的信息。目的地在 PTP（点对点）模式中使用队列（`queue`），在发布/订阅（pub/sub）模式中使用主题（`Topic`）。
- b) `ConnectionFactory`（连接工厂）：通过 JNDI 查找提供到 Java Messaging Service 的物理连接。它包含 IP 地址并允许 JMS 创建连接。

## 248: JMS 中使用哪些对象来接收和创建消息？

答案：

在 JMS 中使用以下对象来接收和创建消息：

- a) `MessageConsumer`（消息消费者）：用于接收发送到目的地的消息。
- b) `MessageProducer`（消息生产者）：用于创建发送到目的地的消息。
- c) `MessageSelector`（消息选择器）：用于过滤符合标准的消息。
- d) `MessageListener`（消息监听器）：用于异步处理和接收消息。

## 249: 解释 MessageConsumer（消息消费者）。

答案：

`MessageConsumer` 用于同步或异步接收由会话对象创建的特定目的地的消息。

在同步通信的情况下，消费者调用 `receive()` 或 `receiveNoWait()` 方法；在异步通信的情况下，客户端注册 `MessageListener` 并启动消费者。

Java Messaging Service 中的几乎所有消息都在客户端之间进行异步交换，生产者永远不会接收消费者的确认。

## 250: 解释 MessageProducer（消息生产者）。

答案：

`MessageProducer` 用于通过 PTP 或发布/订阅发送消息。在 PTP（点对点）模型中，目的地被称为队列（`queue`），在发布/订阅模型中，目的地被称为主题（`Topic`）。

在生产者中，我们可以使用 `setDeliveryMode()` 方法将交付模式设置为非持久性（`NON_PERSISTENT`）或持久性（`PERSISTENT`）。非持久性的开销较小，因为消息不会记录在服务器或数据库中。

我们还可以使用 `setPriority()` 方法设置消息优先级。0 表示低优先级，9 表示高优先级。我们还可以使用 `setTimeToLive()` 方法指定以毫秒为单位的消息生存时间。

## 251: 解释 MessageSelector（消息选择器）。

答案：

`MessageSelector` 属于 `String` 对象，用于过滤不符合指定标准的消息。消息选择器可以检查头部并与 `String` 中存在的表达式进行比较。表达式的示例包括算术运算符、关系操作符、字符串字面量和逻辑运算符。

## 252: 解释 MessageListener（消息监听器）。

答案：

为了异步处理消息，我们必须实例化 `MessageListener` 接口。我们需要执行以下步骤来异步处理和接收消息：

- a) 创建实现 `MessageListener` 接口的对象并调用 `onMessage()` 方法。
- b) 使用 `setMessageListener()` 方法向会话对象注册。
- c) 使用 `Connection` 对象的 `start()` 方法开始接收消息。

## 253: PTP 通信需要哪些类、接口和步骤？

答案：

以下是点对点（PTP）通信所需的类、接口和步骤：

- a) 使用 JNDI（Java 命名和目录接口）查找获取 `QueueConnectionFactory` 对象。JNDI 名称根据消息供应商而异。
- b) 通过 `QueueConnectionFactory` 对象获取 `QueueConnection` 对象。如果启用了安全性，必须提供用户名和密码。
- c) 通过 `QueueConnection` 获取 `QueueSession` 提供者。
- d) 通过 JNDI 查找获取队列（`queue`）。
- e) 通过 `QueueSession` 创建用于接收和发送消息的 `QueueReceiver` 或 `QueueSender`。
- f) 关闭 `QueueConnection`，这将关闭 `QueueReceiver`、`QueueSender` 和 `QueueSession`。

## 254: Pub/Sub 通信需要哪些类、接口和步骤？

答案：

以下是发布/订阅（Pub/Sub）通信所需的类、接口和步骤：

- a) 使用 JNDI（Java 命名和目录接口）查找获取 `TopicConnectionFactory` 对象。JNDI 名称根据消息供应商而异。
- b) 通过 `TopicConnectionFactory` 对象获取 `TopicConnection` 对象。如果启用了安全性，必须提供用户名和密码。
- c) 通过 `TopicConnection` 获取 `TopicSession` 提供者。
- d) 通过 JNDI 查找获取主题（`Topic`）。
- e) 通过 `TopicSession` 创建用于接收和发送消息的 `TopicSubscriber` 或 `TopicPublisher`。
- f) 关闭 `TopicConnection`，这将关闭 `TopicSubscriber`、`TopicPublisher` 和 `TopicSession`。

### 255: 解释 MDB。

答案：

MDB 指 Message Driven Bean（消息驱动 Bean）。它是每当消息到达目的地（队列或主题）时，由容器（EJB）调用的组件（无状态）。

MDB 是一个接收消息的消费者，因为它实现了 `javax.jms.MessageListener` 接口。与 Java Messaging Service 类似，消息驱动 Bean 也以相同的方式接收消息。

在 MDB 的情况下，Enterprise Bean 容器确保该 Bean 注册在特定的目的地。

## 256: 企业资源面临哪些安全威胁？

答案：

以下是企业资源面临的安全威胁：

- a) 机密信息泄露：无意或故意地将信息提供给没有法律权利的人；信息修改：无意或故意地修改数据。
- b) 责任追究失效：这被称为身份盗取；滥用保护资源：这被称为服务盗取。
- c) 损害可用性的滥用：数据修改导致企业系统中断。

## 257: 解释 Authentication（认证）和 Authorization（授权）。

答案：

**Authentication（身份认证）**是验证许可进入安全区域或网站的用户凭据的过程。例如，只有注册用户才有权登录提供邮件服务的网站。**Authorization（授权）**是验证许可访问或接收请求资源的用户角色的过程。例如，用户无法修改文档，因为他没有该角色或未被授权修改特定文档。

## 258: 解释 Java 中提供的某些安全包。

答案：

以下是 Java 中提供的某些安全包：

- a) `java.security`：包含安全、认证和授权（访问控制）的类和接口。
- b) `java.security.interfaces`：包含加密的接口：数字签名算法 (DSA) 和 Rivest-Shamir-Adleman 非对称加密算法 (RSA)。
- c) `java.security.cert`：包含用于管理和解析证书的接口和类。
- d) `java.security.spec`：包含 DSA、RSA 和证书的规范接口和类。

## 259: Java Security Manager 在 Applets 中执行了哪些操作？

答案：

以下是 Java Security Manager 在 applet 中执行的操作：

- a) 删除文件、写入文件和读取文件
- b) 修改线程的属性（例如：优先级）
- c) 更新或访问系统属性
- d) 接受、等待或打开套接字或网络连接

## 260: Java applets 有哪些安全限制？

答案：

以下是 Java applets 的安全限制：

- a) Applet 不允许定义方法或加载库，但可以使用自己的代码
- b) 它不能在执行它的远程机器或宿主机上写入或读取文件
- c) 网络连接仅在下载该 applet 的宿主机上可用
- d) 它不能在宿主机上启动程序
- e) 它被限制读取系统属性

## 261: applet 无法读取哪些系统属性？

答案：

以下是 applet 被限制读取的系统属性：

- a) `user.name`：指用户的账户名称
- b) `user.home`：指用户的家目录
- c) `user.dir`：指用户的当前工作目录
- d) `java.home`：指 Java 的安装目录
- e) `java.class.path`：指 Java 的类路径

## 262: 访问控制的策略是什么？

答案：

以下是访问控制的潜在策略：

- a) 一旦用户通过身份验证，由用户调用的所有进程都继承对已验证上下文的访问权限
- b) 一旦组件通过身份验证，该上下文将对所有其他可信组件可用
- c) 一旦组件准备好冒充调用者，调用者将对调用的组件进行身份验证

## 263: J2EE 支持哪些认证机制？

答案：

J2EE 中的容器支持以下认证机制：

- a) HTTP Basic：包含带有参数的 URL 请求
- b) HTTP Digest：包含带有加密参数的 URL 请求
- c) Form Based：使用用户名和密码进行验证
- d) HTTPS Mutual：允许执行安全事务

### 264: 解释加密通信。

答案：

数据可以通过一种称为密码学（Cryptography）的机制进行加密。在这种机制中，数据使用匹配的密钥进行加密和解密。加密有两种类型：

- a) 对称：在这种情况下，接收者和发送者都拥有加解密信息的公共密钥
- b) 非对称：它被称为公钥加密，其中一个密钥被分为公钥和私钥。每个密钥都有解密其他用户加密数据的能力。

### 265: 解释数字证书。

答案：

数字证书是私钥持有者的一种著名解决方案，将公钥放在一个名为“数字证书”的包中，并使用受信任机构 CA（证书颁发机构）的私钥进行签名。

数字证书解决了公钥在接收时可能不可信的问题。VeriSign 是发行数字证书的领导者，CA 受全球信任且众所周知。VeriSign 的公钥随浏览器和网络服务器分发。

## 266: 解释安全套接层（SSL）。

答案：

安全套接层（SSL）是一种确保访问互联网时隐私性的协议。这些有助于应用程序相互通信，从而防止发生窃听。安全套接层提供了服务器身份验证、数据加密和消息完整性。在 SSL 中，所有数据都会被加密然后在网络上传输。它使用端口 443 在跨服务器之间传输消息。它还使用服务器认证和双向认证模式来传输消息。

## 267: Web 容器执行了哪些安全检查？

答案：

Web 容器执行以下安全检查：

- a) 确保它必须解密请求
- b) 确保请求中存在任何授权约束
- c) 确保请求包含授权或身份验证要求
- d) 请求的资源受到身份验证和授权约束组合的保护

## 268: 解释使用 Java 的遗留连接（Legacy connectivity）。

答案：

遗留连接方法基于使用二层架构的客户端/服务器模型。它不是基于 Web 的，并使用企业信息系统（EIS）来检索和处理数据。

企业信息系统有一个适配器，它提供了 API（应用程序编程接口）用于处理和访问数据以及 EIS 功能。客户端通过编程方式使用 API 连接并访问 EIS。

企业信息系统适配器的关键在于可重用性。独立的供应商使用具有高度可用性和可重用性的编程语言来开发适配器。

### 269: 解释 EIS 中的认证。

答案：

为了从企业信息系统访问信息，J2EE 组件需要遵循一套单独的安全程序。

信息存在于受保护的域中，因此企业信息系统层在独立环境中运行。在这种情况下，容器尝试调用 J2EE 组件身份验证来获取资源。这种机制被称为容器管理的资源管理器（Container Managed Resource Manager）。

### 270: 解释 CSI。

答案：

CSI 指通用安全互操作性（Common Secure Interoperability）。它属于对象管理组（OMG）。CSI v2 是 IIOP（互联网 ORB 协议）的标准，支持身份断言（identity assertion）。

## 271: 解释 EIS 适配器。

答案：

企业信息系统有一个适配器，提供了 API（应用程序编程接口）用于处理和访问数据以及 EIS 功能。客户端通过编程方式使用 API 连接并访问 EIS。

企业信息系统适配器的关键在于可重用性。独立的供应商使用具有高度可用性和可重用性的编程语言来开发适配器。

## 272: 解释使用 JEE 的遗留连接。

答案：

开发者使用 JDBC（Java 数据库连接）访问数据而不是使用适配器，因为这样做非常耗时。Java 连接架构（JCA）在 WebLogic 和 WebSphere 的最新服务器中都得到了支持。

通过使用 Java 连接架构（JCA），企业信息系统供应商无需为每个应用服务器定制适配器。

## 273: 解释资源适配器（Resource Adapter）。

答案：

资源适配器是指 `javax.resource.spi` 和 `javax.resource.cci` 包接口的实现。当你尝试访问资源时需要系统级的软件库。

资源适配器默认实现了企业信息系统的系统合约，包括安全和事务管理。

适配器在客户端层也具有访问 EIS 的 API。它用于服务器环境。

## 274: 解释系统合约（System contract）。

答案：

系统合约定义为双方之间的协议，以支持协作和互利的互动。例如，EIS 和服务器协作以支持连接管理、安全和事务等机制。

使用系统合约，组件提供者专注于应用程序的业务逻辑开发。通过这种方式，我们从提供者那里获得一组用于执行业务任务的功能。

## 275: 解释 JCA 的集成策略。

答案：

现在开发者的主要工作是将新系统与旧系统集成。集成可以通过以下方式进行：

- a) 入站集成技术：在这种情况下，请求由外部系统发起到我们的系统。
- b) 出站集成技术：在这种情况下，请求由我们的系统发起到其他系统。

### 276: 系统合约有哪些类型？

答案：

系统合约有三种。它们是：

- a) 安全管理：允许服务器（应用程序）使用安全相关属性连接 EIS。
- b) 事务管理：允许事务从服务器（应用程序）传播到 EIS。
- c) 连接管理：描述了容器（J2EE）与适配器之间建立连接池和销毁连接的协议。

## 277: 配置安全属性有哪些方法？

答案：

以下是配置安全属性的方法：

- a) **主体映射**：用于在服务器（应用程序）连接或组合 EIS（企业信息系统）时。
- b) **配置身份**：在此情况下，连接到 EIS 时使用资源适配器身份连接。
- c) **凭据映射**：在此情况下映射服务器和 EIS 的凭据。
- d) **调用者伪装**：EIS 中使用的此主体与应用程序服务器匹配。

## 278: CCI API 包含哪些部分？

答案：

CCI 指通用客户端接口（Common Client Interface）。CCI API 包含以下四个部分：

- a) **连接接口**：创建到企业信息系统的连接。
- b) **交互接口**：在 EIS 上命令执行指令，称为交互接口。
- c) **结果集接口**：封装来自 EIS 的查询结果。
- d) **元数据接口**：允许检查 EIS 元数据。

## 279: 解释 ManagedConnectionFactory 和 ManagedConnection。

答案：

`ManagedConnectionFactory` 是一个接口，由类 `UCManagedConnectionFactory` 实现（服务器调用适配器的切入点），该类创建 `UConnectionFactory` 和 `UCManagedConnection` 类。`ManagedConnection` 是一个接口，由 `UCManagedConnection` 类实现。该类封装了适配器连接（物理）类 `UCConnection`。`ManagedConnectionFactory` 和 `ManagedConnection` 都用于实现 JCA（Java 连接器架构）适配器。

## 280: 数据库完整性约束有哪些缺点？

答案：

以下是数据库（DB）完整性约束的缺点：

- a) **逻辑重复**：当数据库完整性规则发生变化时，可能会逻辑重复，这需要修改业务逻辑代码。
- b) **DBMS 约束的可移植性差**：使用过程触发器通常会导致不可移植性，因为每个供应商都遵循自己的标准。
- c) **不受控的数据库配置**：由于约束存在于服务器（J2EE）之外，配置是使用数据库厂商工具完成的。

## 人力资源问题

回顾这些典型的面试问题，并思考你会如何回答。阅读列出的答案；你将在找到最佳答案以及相关的策略和建议。

### 1: 请告诉我一次你未能按截止日期完成任务的经历。



# 面试常见问题及回答指南

## 1. 你是否曾错过截止日期？如果有，你是如何处理的？

答案：

理想情况下这种情况没有发生过——但如果发生过，请确保使用一个微不足道的例子来说明情况，强调那是多久以前的事了，并确保你已经尽了全力确保按时完成。此外，请务必包括你在更好地管理时间或安排任务优先级方面学到了什么，以满足未来所有的截止日期。

## 2. 你在工作时如何消除干扰？

答案：

随着技术的进步和沟通的便利，每天都会出现新的干扰。你的面试官会希望看到你通过一个例子展示你为了保持任务状态而采用的惯常做法，来证明你仍然能够专注于工作，并且你的生产力没有受到影响。

## 3. 请告诉我你曾在一个有每周或每月配额的任务上工作的经历。你成功的频率如何？

答案：

你的数据将说明一切，你必须诚实地回答这个问题。如果你经常达到配额，请务必以自信的方式强调这一点，并且不要羞于指出你在这一方面的优势。如果你的统计数据并不理想，请尝试指出它们在你离职前有所增加的趋势，并对未来可以改进的方法进行反思。

## 4. 请告诉我一次你遇到严苛的截止日期的经历，以及你是如何完成它的。

答案：

解释你是如何安排任务优先级，或者将任务的部分分配给其他团队成员，以应对严苛的截止日期。具体说明为什么截止日期很严苛可能会有帮助——确保清楚这不是由于你个人的拖延导致的。最后，解释你是如何成功满足截止日期的，以及最终达成目标付出了什么努力。

## 5. 当你手上有多个项目时，如何保持组织有序？

答案：

面试官将希望看到你能够很好地管理你的时间和工作——能够同时处理多个项目，并给每个项目提供应有的关注，是员工能力和效率的极佳体现。回顾这些工作的典型流程，直到设定目标和优先级，并向面试官解释这些步骤，这样他或她可以看到你是如何管理时间的。

## 6. 你在工作日花多少时间处于“自动驾驶”状态？

答案：

虽然你可能好奇雇主是否想通过这个问题来看你的工作效率有多高（例如，工作太精通以至于不需要思考），但在几乎所有的情况下，雇主都希望看到你在不断思考、分析和处理工作场所中发生的事情。即使事情运行顺利，通常也有某些机会可以让事情变得更高效或增加销售或生产力。

## 7. 你如何处理截止日期？

答案：

处理截止日期最重要的部分是安排任务优先级并设定完成目标，最重要的是保持冷静。解释你在压力下如何管理时间。

## 8. 请介绍一下你的解决问题过程。

答案：

你的解决问题过程应该概述问题、提出可能的解决方法以及制定清晰计划。保持你的答案简洁且有组织，并解释解决的步骤。

## 9. 工作中哪些事情会让你感到压力？

答案：

最好避开负面因素，保持这个答案简单。虽然回答工作中没有任何事情让你感到压力不会让面试官信服，请关注你通常如何应对压力，例如召开状态会议。

## 10. 当你感到压力时你看起来是什么样的？你是如何解决的？

答案：

这是一个陷阱题——你的面试官希望听到你在压力时看起来没有任何变化，并且没有让负面情绪干扰你的生产力。至于你如何解决压力，最好是你已经掌握了解决方案，例如简单的深呼吸并数到10，让自己重新回到任务上。

## 11. 你能多任务处理吗？

答案：

有些人可以，有些人则不行。多任务处理最重要的部分是时刻保持头脑清醒，明确要做什么，以及每个任务属于什么优先级。解释你是如何评估任务以确定优先级的，以及如何管理时间以确保所有任务都高效完成。

## 12. 你每周工作多少小时？

答案：

许多人会被这个问题误导，认为回答的时间越多越好——然而，这可能会让雇主怀疑，为什么你需要花费更多的时间才能完成别人可以在更短时间内完成的工作。给出一个你完成某项工作所需的合理时间预估，并解释说你在需要时也愿意额外工作。

## 13. 你每天检查几次电子邮件？

答案：

虽然雇主希望看到你紧跟现代技术，但重要的是，你每天检查电子邮件的次数应该相对较低——可能每天只有二到三次（取决于你所处的领域）。检查电子邮件在工作场所通常是一个很大的干扰，虽然保持联系是重要的，但很多通信内容完全可以在早上和下午统一处理。

## 14. 你最大的成就是什么？

答案：

你最大的成就应该是对你来说具有特别意义，并且你能够充满激情地谈论它的——面试官能够从中看出这一点。请务必为这个问题准备好答案，并确保解释清楚你是如何取得成功的，以及你从这段经历中学习到了什么。

## 15. 是什么驱动着你？

答案：

最好的方法是关注你工作中的一个关键方面，将其作为你日常工作的“驱动力”。无论是客户服务、创造改变，还是进一步提升技能和获得经验的机会，让面试官看到你对职业充满的热情以及对该职位的奉献精神都是至关重要的。

## 16. 当你失去动力时，你会做什么？

答案：

优秀的候选人会回答说他们很少失去动力，因为他们已经采取了策略来保持灵感，而且他们对自己的目标保持专注。此外，如果你能解释自己受实现目标和进步的驱动，也可能会给面试官留下深刻印象，因为小成功始终是重新获得动力的好方法。

## 17. 你空闲时间喜欢做什么？

答案：

你在这里回答的内容并不如你**不**回答的内容重要——面试官不想听你喜欢喝什么、参加派对或沉迷于夜生活。相反，选择几个能体现稳定和成熟的活动作为重点，且这些活动不会影响你的出勤工作和工作效率，例如阅读、烹饪或摄影。这也是向面试官展示你是一个全面发展、有趣且充满活力的个性的绝佳机会，他们会乐意雇佣你。

## 18. 你与其他员工相比有什么独特之处？

答案：

这个问题是一个突出你为公司带来的、他人无法具备的特定技能组合和热情的绝佳机会。如果你无法准确概述你与其他员工的不同之处，面试官又如何看到它呢？请准备好一份详尽的大纲，说明你将提供什么，以帮助公司实现他们的目标。

## 19. 为什么你是担任该职位的最佳人选？

答案：

提前为这个问题准备一个简短的回答，因为这是面试中另一个非常常见的话题（问题的变体包括：“为什么我应该选择你而不是候选人 B？”以及“你能为我们公司提供什么候选人 B 不能提供的？”）。确保你的陈述听起来不像背诵的，并突出你最独特的特质，向面试官说明为什么他/她必须优先雇佣你。包括关于你的经验以及特殊项目或你获得的认可的具体细节，这些细节让你脱颖而出，并表现出你对该职位最大的热情、投入和热忱。

## 20. 成功需要什么？

答案：

努力工作、热情、动力和对学习的投入——这些都是对“成功”这一模糊概念的可能回答。你选择其中哪种价值观作为成功的首要手段，或者选择它们的组合，这并不重要。然而，绝对关键点在于，无论你选择哪种价值观，都必须在你的态度、经验和目标中清晰地表现出来。

## 21. 这个职位对你来说最大的挑战是什么？

答案：

保持这个答案积极正面，并专注于该职位可以提供的增长和学习机会。请确保无论挑战是什么，都显而易见你已经准备好并渴望应对它，并且你对获得这份工作需要什么有充分的认识。

## 22. 你描述自己是内向者还是外向者？

答案：

这两种性格都有益的特质，你的回答可能取决于你所从事的工作类型。然而，一个成功的领导者可以是内向的也可以是外向的，同样，优秀的团队成员也可以是任何一种。这个问题的关键方面在于具备所需的自我意识，以准确地描述你自己。

## 23. 你不具备哪些积极的性格特质？

答案：

如果面试官向你提一个关于你的缺点或缺乏积极特质的棘手问题，最好让你的回答轻松简单——例如，表达你对自己能力的极度自信，然后以（相当谦虚地）承认自己偶尔可以做得更谦虚一些。

## 24. 你学过的最重要教训是什么？

答案：

虽然这是一个非常宽泛的问题，但面试官会更有兴趣听你对这个价值的重视程度。你最大的教训可能与导师、父母或教授曾经对你说过的话有关，或者你可能从由你领域领先专家撰写的书中汲取了。无论教训是什么，最重要的是你能提供一个例子说明你是如何将其融入生活的。

## 25. 你是否经历过这样一种情况：你的某个优势在另一种环境下变成了劣势？

答案：

通过对这个问题给出答案来表现自我意识是重要的，但你要确保这个弱点是相对微不足道的，并且在大多数情况下仍然是一项优势。例如，你可能是一个热衷的读者，阅读任何能找到的读物，但在开车上班的路上看路牌广告可能是一个危险的想法。

## 26. 谁是你生命中影响你最大的人？

答案：

给影响过你生活的人给出一个具体的例子（以及名字），并提供一个关于你们之间分享的相关轶事。如果他们的影响与你的职业生活有关那就太好了，但这个问题也开启了讨论你个人生活的可能性。面试官想看到你能够建立人际联系并工作。

## 27. 你认为自己是“细节型”还是“全局型”的人？

答案：

这两种特质都是优点，最好的方法是你可以将两者都融入你的回答中。选择一种作为你的主要类型，并结合经验来说。然后解释另一种类型如何适应你的工作。

## 28. 你最大的恐惧是什么？

答案：

公开且不尴尬地透露你最大的恐惧是向雇主展示自信的好方法。选择一个你正在努力克服的恐惧，例如对于像你这样似乎不可能的失败恐惧，并带有清晰的目标和行动。尽管固守像蜘蛛这样简单的答案很有诱惑力，但请远离这些，因为它们并不能告诉面试官关于你的真实信息。

## 29. 你喜欢什么样的挑战？

答案：

你喜欢的挑战应该展示出你方面的主动性或增长潜力，并且应该符合你的职业目标。雇主会在这里评估一致性，因为他们会批判性地分析你期待的挑战与最终目标之间的关系。

## 30. 说一次你尴尬的经历。你是如何处理的？

答案：

没有人想在面试中提到自己尴尬的时刻，最好避免此类轶事。然而，不要回避提供一个简短的概述，随后展示你能够付之一笑的能力。向面试官证明那个事件对你没有产生重大影响。

## 31. 你最大的缺点是什么？

答案：

这是面试中另一个经常被问的问题之一，所以你应该已经准备好了答案。尝试想出一个在另一种环境下实际上是一项优势的弱点——例如，“我非常注重细节并喜欢确保每件事都正确，所以我有时在分配任务给他人时很困难。”然而，不要试图掩盖明显的缺点——如果你在该领域缺乏实战经验，请提到你期待获得进一步学习知识的绝佳机会。

## 32. 用三个形容词来描述你在工作环境中的状态最合适？

答案：

虽然这三个形容词可能已经出现在你简历的某处，但不要害怕再次使用它们来突显你的最佳特质。这是一个你向面试官推销自己的机会，并指出你具备而其他候选人不具备的特质。使用你能想到的最具体、最准确的词汇，并简要说明你是如何体现这些特质的。

## 33. 用三个形容词来描述你在个人生活中状态最合适？

答案：

理想情况下，描述你个人生活的三个形容词应该与描述你职业生活的形容词相似。雇主非常看重一致性，虽然他们可能理解你在办公室之外有另一种性格，但最好在工作和日常生活中都采用相似的行为准则。

## 34. 你属于哪种类型的员工？

答案：

这是一个突出你一些巨大资产的机会。刻画你的一些才能，例如：专注的、自我驱动的、注重细节的、热情的、勤奋的、分析型的或关注客户服务的。在这里要避开你的弱点，始终专注于你能为公司带来的所有美好品质。

## 35. 讲讲你工作中最快乐的一天。

答案：

你工作中最快乐的一天应该包含你最大的职业成就之一，以及带给你的感受。专注于你完成的内容，并确保详细说明这项成就对你来说有多意义或多么满足。

## 36. 讲讲你工作中最糟糕的一天。

答案：

这可能是因为你犯了所有的错误而变得最糟糕，也可能是因为你刚刚和好朋友大吵了一架，但请确保这个回答集中在专业领域。尝试使用一个工作中发生了不可控事件的例子（例如，团队重要成员突然辞职，导致你们与客户的会议失败），并关注对无法控制局面的挫败感。保持这个回答简短，并务必以对从那一天中学到的反思结尾。

## 37. 你对什么充满热情？

答案：

尽可能让回答集中在专业领域，但讨论一些你所感兴趣的个人问题也是合适的（例如环境保护或在汤厨房当志愿者）。坚持非争议性的话题，并在解释该话题如何激发你的灵感以及如何积极参与其中时，让你的热情流露出来。此外，如果你选择了一个个人爱好，请确保它不会影响你的工作投入或生产力。

## 38. 你最常收到的批评是什么？

答案：

对这个问题给出诚实、坦诚的回答可以给面试官留下深刻印象（当然，这需要伴以对你正在如何改进的解释），但要确保这种批评是微不足道的或与你的职业无关。

## 39. 在哪种工作环境中你最成功？

答案：

在面试之前，请务必研究公司和具体的职位。调整你的回答以适应你将要从事的工作，并解释为什么你喜欢这种环境而不是其他环境。然而，具备适应能力也极其重要，所以对其他环境也要保持灵活性。

## 40. 你是一个情绪化的人吗？

答案：

最好关注你的积极情绪——热情、快乐、动力——并避开其他可能导致你看起来失衡的极端情绪。虽然你想要表现出对工作的兴奋之情，但务必随时保持冷静，以便让面试官知道你不是那种会让情绪主宰你并影响工作的人。

## 41. 公司进行最好的广告方式是什么？

答案：

如果你申请的是营销以外的任何职业职位，这个问题可能是为了展示你的批判性思维能力以及为你的回答提供反思性的支持。因此，你选择的具体方法并不重要，重要的是你是如何选择的。例如，口碑广告很重要，因为客户天生信任信息来源；而社交媒体广告很重要，因为它可以快速且廉价地触达新客户。

## 42. 获得新客户还是留住老客户更好？

答案：

在几乎所有情况下，留住老客户更好，而且你能清晰阐述原因这一点很重要。首先，新客户给公司的成本通常比留住老客户更高，而且新客户更有可能转向其他公司。此外，留住老客户是为公司提供稳定骨干的好方法，也能获得新客户，因为他们可能会向朋友推荐你的公司。

## 33. 从竞争对手手中赢得客户的最佳方法是什么？

答案：

关于如何从竞争对手手中赢得客户，有很多种观点，除非你知道面试官遵循特定的思想或做法，否则最好让这个回答保持泛化。不要使用绝对化的语言，而是专注于一两个策略的益处，并对这些方式在实际应用中如何成功展现清晰且具有批判性的理解。

## 44. 你对公司监控互联网使用情况有什么看法？

答案：

通常来说，大多数公司会对员工的互联网使用进行某种程度的监控——在面试中并不是反抗这种做法的最佳时机。相反，要关注积极方面，即这种做法如何提高某些容易在丰富信息世界中迷失员工的生产力。

## 45. 你对我们公司的第一印象是什么？

答案：

显然，这应该是一个积极的回答！从公司的信息或目标中挑选出几个你特别认同或与你的经验相关的关键组成部分，讨论你为什么认为这些使命是如此重要。

## 46. 谈谈你的个人商业哲学。

答案：

你的个人商业哲学应该是经过深思熟虑的，并与公司的使命和目标保持一致。专注于积极方面，例如它能提供的服务以及人们在商业中获得的教训，并对你哲学的来源提供见解。

## 47. 你认为在我们的公司取得成功的关键是什么？

答案：

在面试前对公司进行研究。了解公司的使命和主要目标，以及公司内部的一些知名人物，并记住他们是如何取得成功的。将你的回答集中在你可以实现的特定目标上，以帮助公司实现其目标。

## 52. 你在这个职业领域工作中最喜欢的部分是什么？

答案：

这个问题是一个讨论你工作中你喜欢的某些方面的机会，并突出为什么你是该特定职位的理想人选。选择你喜欢的工作元素，且这些元素要与你被录用后可能从事的工作内容相关。记住对你在工作中可能获得的机会保持热情和兴奋。

## 53. 你认为你的职业在未来 10 年内会发生什么变化？

答案：

如果你关注自己职业的现状，并努力跟上你所在领域的新趋势，你应该能够为面试官提供几个关于你的职业或领域可能向何种方向发展的预测。这种洞察力和意识水平显示了雇主非常看重的奉献精神和兴趣。

## 54. 请描述一次你向同事传达困难或复杂想法的经历。

答案：

首先向面试官简要解释一下这个想法，然后概述为什么需要向同事进一步拆解它。最后，用简洁的步骤解释这个想法，以便面试官看到你的沟通能力和简化复杂问题的技巧。

## 55. 你发现在什么情况下很难进行沟通？

答案：

即使是优秀的沟通者通常也会发现某些特定情况很难进行有效沟通，因此不要害怕诚实地回答这个问题。务必解释你提到的特定情况对你来说为什么很困难，并尝试选择一个不常见的答案，例如在困难时期存在语言障碍，而不是像与职位更高的人说话这样的情况。

## 56. 良好沟通的关键组成要素是什么？

答案：

良好沟通的一些要素包括：不受干扰的环境、听者的反馈，以及说话者在必要时的修正或澄清。在必要时参考基本的沟通模型，并提议与面试官进行角色扮演演练以展示你的技能。

## 57. 请告诉我一次你通过沟通解决问题的经历？

答案：

通过沟通解决问题是商业世界的关键，因此请从你之前的工作选择一个特定情况，在那个情况下，你通过有效的冲突沟通化处理了复杂的局面。解释情况背景，以及你采取的沟通步骤，并以讨论为什么通过沟通解决问题对你的最终结果如此重要作为结束。

## 58. 请告诉我一次你与另一员工发生争议的经历。你是如何解决该情况的？

答案：

确保使用具体的案例，并逐步解释该场景、你做了什么来处理它，以及最终是如何解决的。中间步骤，即你如何处理争议，显然是最具决定性的——描述你使用的沟通类型，以及你如何通过妥协达成共识。冲突解决是任何员工都应该拥有的重要技能，也是面试官会寻找的技能，以判断你卷入争议的可能性有多大，以及如果发生争议，他们被迫卷入的可能性有多大。

## 59. 你是能够快速地与人建立关系，还是需要更多时间来了解他们？

答案：

这两个选项都可以表现出良好的品质，因此请确定哪种风格更适合你。强调你在建立关系过程中所采取的步骤，而不是特定的风格，并简要总结为什么这种方法最适合你。

## 60. 请描述一次你必须通过办公室政治来解决问题的经历。

答案：

尝试关注这个问题中的积极方面，这样你就可以利用该情况转化为你的优势。不要负面地描述你之前的雇主，而是要用极小的实例（例如文书工作或某个人）来突出你是如何机智地处理特定实例的。给出你为了达成解决方案而使用的沟通技巧或解决问题的能力的例子。

## 61. 请告诉我一次你说服他人承担一项艰巨任务的经历？

答案：

这个问题是一个展示你的领导能力和沟通能力的机会。虽然提供特定情况作为背景很重要，但重点应放在你是如何能够说服他人的。

## 62. 请告诉我一次你成功说服一个群体的经历。

答案：

这个问题是一个展示你的领导能力和沟通能力的机会。虽然提供特定情况作为背景很重要，但重点应放在你是如何能够说服他人的。

## 63. 请告诉我一次你与他人发生问题后，事后看来，你希望自己换一种方式处理它。

答案：

这个问题是一个展示你的领导能力和沟通能力的机会。虽然提供特定情况作为背景很重要，但重点应放在你是如何能够说服他人的。

## 64. 请告诉我一次你在员工之间进行谈判的经历。

答案：

对于那些应聘主管角色的人来说，这是一个特别重要的问题——从一个特定情况开始，解释你是如何进行有效沟通的。例如，你引入了妥协吗？你做出了行政决定吗？



# 65：为什么你的技能与我们公司的目标非常匹配？

回答：

如果你之前研究过这家公司，那么回答这个问题应该没有问题。确定公司的几个主要目标，并解释你所拥有的特定技能如何有助于这些目标。此外，思考你的经验和技能如何转化为帮助公司扩展目标，并实现更远的目标。如果你的前公司有类似的目标，请给出一个具体的例子说明你是如何帮助公司实现它的。

# 66：你认为这份工作包含哪些内容？

回答：

确保在进入面试之前对该职位进行了充分研究。阅读所有能找到的职位描述（最好直接从雇主的网站或招聘公告中获取），并记录关键职责、责任和要求的经验。没有什么比让面试官看到一个完全不知道自己在面试什么工作的候选人更有损了。

# 67：关于这份工作或公司，你还有什么想了解的吗？

回答：

如果你事先了解过这家公司，这是一个展示你在面试前付出了努力的绝佳机会。关于公司使命与当前行业趋势的关系，与面试官进行有趣且相关的对话。此外，在离开之前弄清楚你对特定职位所需的任何信息——这样如果面试官打电话给你录取通知，你就准备好回答了。

# 68：你是该职位的最佳人选吗？

回答：

是的！提供具体的细节说明你为什么胜任该职位，并确保讨论（并展示）你对这个新机会、工作以及公司的毫无抑制的热情和兴奋。

# 69：你是如何为这次面试准备的？

回答：

这个问题的关键在于确保你已经做了充分准备！在面试之前，请务必对公司、其目标和提供的服务进行研究，并尽可能地了解特定职位。此外，了解公司的历史以及当前组织中的关键人物也会有所帮助。

# 70：如果你被聘用到这里，你第一天会做什么？

答案：

虽然许多人会以一种无聊的方式回答这个问题（即描述标准的第一天流程），但这个问题实际上是一个绝佳的机会，让你向面试官展示为什么你会是一个优秀的人才。除了培训或入职引导等事项外，还要强调你有多喜欢与主管和同事见面，或者你将花一天的大部分时间提问并熟悉所有的新环境。

# 71：你查看过我们公司的网站吗？

答案：

显然，在来面试之前，你应该查看过公司的网站并对其进行一些初步研究。如果由于某种原因你没有看，千万不要说你看过，因为面试官可能会通过询问相关的具体问题来揭穿你。如果你确实看过了公司网站，现在是提到你在上面看到的令你特别感兴趣的内容，或你特别支持的价值观的好时机。

# 72：你简历中的 X 经验与这个职位有什么关系？

答案：

许多申请者的简历中会有一些经验无法明确转化为所涉及的特定工作。然而，要准备好被问及这类看似无关的经验，并准备好一个回答，考虑到这两者之间可能的相似技能集或培训。

# 73：你为什么想得到这个职位？

答案：

将这个回答积极地集中在该特定职位的某些上，这些方面可以让你进一步提升技能、获得新经验，或者成为你做某些你特别喜欢的事情的机会。不要告诉面试官你已经找了很久工作，或者薪水非常有吸引力，否则你会显得缺乏动力且机会主义。

# 74：你的背景与这个职位有什么相关性？

答案：

理想情况下，这应该从你的简历中显而易见。但在经验与职位关联较松散的情况下，请确保你在面试前已对工作和公司进行了充分研究。这样，你就能智能地将你拥有的经验和技能与新职位所需的类似技能联系起来。具体解释你的技能将如何转化，并使用“准备”和“学习”等词汇来描述你的背景。你的前景职位应该描述为一个“机会”以及一个“成长和发展”的机会。

# 75：你对我们公司的使命感觉如何？

答案：

面试前研究公司是非常重要的——如果你已经这样做了，这个问题就不会让你措手不及。最好的答案是简单、直接，并表现出对当前使命的了解。提供几个简短的陈述说明你为什么认为该使命的重要性，并指出你有兴趣在支持该使命的公司工作。

最后，祝你好运！

# 目录

# Java/J2EE 面试题

## 架构与协议

- 1：`Web Server` 和 `Application Server` 有什么区别？
- 2：`J2EE` 架构中包含了哪些技术？
- 3：`Spring` 的好处是什么？
- 4：区分 `SAX` 和 `DOM` 解析器。
- 5：组件（`component`）和服务（`service`）之间有什么区别？
- 6：`J2EE` 架构的设计目标是什么？
- 7：`J2EE` 架构师（`Architect`）的角色有哪些？
- 8：架构（`architecture`）和设计（`design`）之间有什么区别？
- 9：架构分析（`Architectural Analysis`）中执行哪些活动？
- 10：架构设计（`Architectural Design`）中执行哪些活动？
- 11：面向对象设计（`object oriented design`）中执行哪些活动？
- 12：多层架构（`multi-tier architecture`）的组件有哪些？
- 13：多层客户端服务器架构的优点是什么？
- 14：`Bean` 开发者（`bean developer`）的责任是什么？
- 15：应用组装器（`application assembler`）的责任是什么？
- 16：`Bean` 部署器（`bean deployer`）的责任是什么？
- 17：第三方软件在 `EJB` 框架中扮演什么角色？
- 18：解释 `MVC` 架构。
- 19：解释 `EAR`、`WAR` 和 `JAR`。
- 20：解释 `JTA`、`JNDI` 和 `JMS`。
- 21：解释 `EDI`。
- 22：解释 `EAI`。
- 23：在 Java 中支持 `XML` 的意图是什么？
- 24：业务层和用户界面之间通信使用的协议有哪些？

## 你最可能被问到的 JAVA/JEE 面试题

- 25：`HTTP` 协议的优缺点是什么？
- 26：解释 `JRMP`。
- 27：`CORBA` 的优缺点是什么？
- 28：解释 `DCOM`。
- 29：解释 `J2EE` 架构的能力。
- 30：解释系统架构（`System architecture`）和参考架构（`Reference architecture`）。

## 适用性与最佳实践

- 31：解释为了提高性能而应遵循的最佳实践
- 32：`Struts`、`Spring` 和 `Hibernate` 如何帮助提高性能？
- 33：垃圾回收（`Garbage Collection`）如何影响性能？
- 34：解释性能最佳实践
- 35：`J2EE` 有哪些最佳实践？
- 36：解释性能最佳实践
- 37：提供几个简短的陈述说明你为什么认为该使命的重要性，并指出你有兴趣在支持该使命的公司工作。
- 38：解释 `MVC` 的最佳实践。
- 39：解释 性能最佳实践
- 40：解释 `MVC` 的最佳实践
- 41：解释 性能最佳实践
- 42：解释 `MVC` 的最佳实践
- 43：解释 性能最佳实践
- 44：解释 `MVC` 的最佳实践
- 45：解释 性能最佳实践
- 46：解释 `MVC` 的最佳实践
- 47：解释 性能最佳实践
- 48：解释 `MVC` 的最佳实践
- 49：解释 性能最佳实践
- 50：解释 `MVC` 的最佳实践
- 51：解释 性能最佳实践
- 52：解释 `MVC` 的最佳实践
- 53：解释 性能最佳实践
- 54：解释 `MVC` 的最佳实践
- 55：解释 性能最佳实践
- 56：解释 `MVC` 的最佳实践
- 57：解释 性能最佳实践
- 58：解释指南

## Servlet

- 59：`Servlet` 使用了哪些类和接口？
- 60：`ServletContext` 的作用是什么？
- 61：`HttpServlet` 的方法有哪些？
- 62：`HttpSession` 的方法有哪些？
- 63：`Servlet` 如何通信？
- 64：数据何时会刷新？
- 65：`ServletContext` 和 `ServletConfig` 的区别。
- 66：如何实现 `Servlet` 线程？
- 67：`JSP` 还是 `Servlet` 更好？
- 68：`doGet()` 和 `doPost()` 方法有哪些？
- 69：解释 `Servlet`。
- 70：`GET` 和 `POST` 请求。
- 71：解释 `Servlet` 的生命周期。
- 72：`Servlet` 如何获取参数？
- 73：`Servlet` 如何接收表单数据？
- 74：在不知道字段名的情况下 `Servlet` 如何获取值？
- 75：可以从 `doPost` 调用吗？
- 76：解释 `init` 方法的语法。
- 77：从 `doPost` 调用有什么处？
- 78：如何向浏览器发送压缩页面？
- 79：解释状态码。
- 80：解释状态码 `200` 和 `404` 的含义。
- 81：解释 `sendRedirect` 方法。
- 82：如果特定的页面或 `servlet` 不可用，如何显示消息？
- 83：设置头部值的方法有哪些？
- 84：从头部中可以检索哪些值？
- 85：解释 `MIME`。
- 86：解释最常用的 `MIME` 类型。
- 87：什么是 `Cookie`？
- 88：`Cookie` 的优点是什么？
- 89：如何设置和获取 `Cookie`？
- 90： `Cookie` 的缺点是什么？
- 91：有哪些选项可以跟踪网页浏览？
- 92：如何从会话存储并检索值？
- 93：解释会话跟踪。

## JSP

- 94：为什么在 `JSP` 中要避免脚本段（`scriptlets`）？
- 95：`JSP` 编译是什么意思？
- 96：`JSP` 内部有哪些生命周期方法？
- 97：如何在 `JSP` 中设置和删除 `Cookie`？
- 98：`JSP` 的用途是什么？
- 99：`JSP` 构造结构（`constructs`）有哪些？
- 100：脚本元素有哪些？
- 101：最常用的 `JSP` 对象有哪些？
- 102：解释如何在 `JSP` 中获取参数值。
- 103：如何在 `JSP` 中显示动态参数值？
- 104：索引 187
- 105：解释 `JSP` 指令。
- 106：举例说明如何使用 `page` 指令。
- 107：解释 `page` 指令属性：`import`、`session`、`buffer` 和 `extends`。
- 108：解释 `page` 指令属性：`autoflush`、`info`、`errorPage` 和 `isErrorPage`。
- 109：`page` 指令对应的 `XML` 语法是什么？
- 110：如何在 `XML` 语法中显示动态参数值？
- 111：举例解释 `include` 指令。
- 112：`include` 指令对应的 `XML` 语法是什么？
- 113：`jsp:plugin` 元素有什么用？
- 114：`jsp:params` 元素有什么用？
- 115：创建 `bean` 类时需要考虑哪些重要点？
- 116：你如何在 `JSP` 中包含一个 `bean` 类？
- 117：你如何为 `bean` 类设置属性值？
- 118：你如何在 `JSP` 中引入标签库？
- 119：你如何将一个 `JSP` 的内容包含另一个 `JSP` 中？
- 120：你如何从 `JSP` 页面转发请求？
- 121：你将如何在目标页面中解释相对 `URL`？
- 122：你如何关联 `bean` 类中的所有属性？

## EJB

- 123：解释术语“`Required`”、“`RequiresNew`”、“`Supports`”、“`NotSupported`” 和“`Mandatory`”。
- 124：解释细粒度接口和粗粒度接口（`interfaces`）。
- 125：解释 `Session bean` 和 `Entity bean` 之间的区别。
- 126：你对 `EJB Interceptor`（拦截器）了解什么？
- 127：展开并解释 `ACID`。
- 128：`EJB` 如何帮助管理数据库实体映射？
- 129：创建 `EJB` 组件必须创建哪些类/接口？
- 130：企业级 `Java Beans` 有哪些类型？
- 131：解释 `EJBHome` 接口。
- 132：解释 `EJBObject` 接口。
- 133：什么是部署描述（`deployment descriptor`）？
- 134：什么是 `bean` 类？
- 135：解释上下文对象（`context object`）。
- 136：`session bean` 有哪些类型？
- 137：远程接口（`remote interfaces`）有哪些方法？
- 138：`home` 接口有哪些方法？
- 139：本地和远程接口提供了哪些服务？
- 140：解释 `session bean` 如何暴露给客户端。
- 141：解释本地客户端（`local client`）。
- 142：解释远程客户端（`remote client`）。
- 143：什么时候必须使用 `EJB`？
- 144：如何管理 `bean` 的持久化？
- 145：解释 `bean` 管理持久化（`bean managed persistence`）。
- 146：解释容器托管持久化（`container managed persistence`）。
- 147：解释如何创建无状态 `session bean` 的 `home` 接口。
- 148：解释如何创建无状态 `session bean` 的远程接口。
- 149：解释 `InitialContext`。
- 150：`EJB` 容器中池化的好处是什么？
- 151：在实体 `bean` 和数据资源之间使用 `DAO` 有什么好处？
- 152：解释 `EJB` 容器在管理实体 `bean` 生命周期中的作用。
- 153：`CMP` 有哪些好处？
- 154：`BMP` 有哪些好处？
- 155：`CMP` 有哪些缺点？
- 156：`BMP` 有哪些缺点？
- 157：如何使用 `BMP` 实现持久化？
- 158：解释查找方法（`finder methods`）。
- 159：实体 `bean` 生命周期周期的状态有哪些？
- 160：容器在实体 `bean` 生命周期周期内调用了哪些方法？
- 161：实体 `bean`（`entity beans`）有什么用？
- 162：部署描述中指定了哪些元素？
- 163：解释如何为有状态 `session bean` 创建 `home` 接口。
- 164：解释如何为有状态 `session bean` 创建远程接口。
- 165：解释如何创建一个有状态 `session bean` 类。
- 166：什么是访问方法（`accessor methods`）？
- 167：`EntityContext`（实体上下文）。
- 168：解释 `getEJBHome`、`getEJBLocalHome` 和 `getCallerPrincipal` 方法。
- 169：解释 `getRollBack`、`setRollBack` 和 `getGetUserTransaction` 方法。
- 170：解释 `Transaction`（事务）。
- 171：容器托管事务可用哪些事务属性？
- 172：容器如何管理多个事务？
- 173：解释 `JTS`。
- 174：`EJB` 容器提供了哪些服务？
- 175：`EJB` 框架作为架构的好处是什么？
- 176：解释 `session bean` 的生命周期。
- 177：抽象持久化模式（`persistence schema`）包含哪些信息？
- 178：`EJB` 客户端有哪些类型？

## 国际化与本地化（Internationalization and Localization）

- 179：什么是全球化（`Globalization` 或 `G11N`）？
- 180：什么是国际化（`internationalization`）？
- 181：什么是本地化（`localization`）？
- 182：什么是 `locale`（区域）？
- 183：国际化应用的特征有哪些？
- 184：通过哪些元素识别 `locale`？
- 185：是否可以使用 `java.util` 包进行本地化？
- 186：解释 `ResourceBundle`。
- 187：`ResourceBundle` 有哪些特性？
- 188：解释字符集（`Character Sets`）。
- 189：解释 `Unicode`。
- 190：解释 `UTF`。
- 191：解释排序（`Collation`）和排序器（`Collator`）。
- 192：`JSP` 中使用了哪些属性？
- 193：解释 `Format` 类。
- 194：应用中有哪些不同的 `locale`？
- 195：Java 支持哪些字体名称（`font names`）？
- 196：国际化应用程序有哪些特性？
- 197：`Format` 类的子类有哪些？
- 198：编码（`encoding`）是什么？
- 199：什么是本地化页面？
- 200：`locale` 的优势是什么？
- 201：`I18N` 和 `L0N` 是什么？
- 202：解释 `InputStreamReader`。
- 203：解释 `OutputStreamWriter`。
- 204：使用 `ResourceBundle` 有哪些特性？

## 设计模式（Design Patterns）

- 205：什么是一个类？
- 206：哪些设计模式？
- 207：模式的好处是什么？
- 208：解释 `GoF`（设计模式）。
- 209：设计模式有哪些类型？
- 210：哪些创建型设计模式（`Creational Design Patterns`）？
- 211：解释 `Singleton`（单例模式）。
- 212：解释 `Factory Method`（工厂方法模式）。
- 213：解释 `Prototype`（原型模式）。
- 214：在哪些场景下创建 `Abstract Factory`（抽象工厂）？
- 215：哪些结构型设计模式（`structural design patterns`）？
- 216：解释 `Proxy`（代理模式）。
- 217：`Façade`（外观模式）的好处是什么？
- 218：在哪些场景下创建 `Adapter`（适配器模式）？
- 219：解释 `composite`（组合模式）。
- 220：`Decorator`（装饰模式）的好处是什么？
- 221：哪些行为型设计模式（`behavioral design patterns`）？
- 222：解释 `Strategy`（策略模式）。
- 223：`mediator`（中介者模式）的好处是什么？
- 224：什么时候使用 `Iterator`（迭代器模式）？
- 225：解释 `Interpreter`（解释器模式）。
- 226：与 `command`（命令模式）相关的 `JEE` 特性有哪些？
- 227：什么时候使用 `Visitor`（访问者模式）？
- 228：解释 `Template Method`（模板方法模式）。
- 229：解释 `Chain of Responsibility`（责任链模式）。
- 230：`Memento`（备忘录模式）和 `State`（状态模式）的好处是什么？

## 消息传递（Messaging）

- 231：什么是消息（`Messages`）？



# 中间层与消息传递

## 核心概念

- 232: 解释中间层（middle tier）。
- 233: 解释 MOM（消息队列模型）。
- 234: 解释同步通信。
- 235: 解释异步通信。

## JMS (Java Message Service)

- 236: 解释 JMS。
- 237: JMS 支持哪些消息模型？
- 238: 同步消息的好处是什么？
- 239: 异步消息的好处是什么？
- 240: 我们在什么场景下使用异步消息？
- 241: JMS 有哪些优势？
- 242: JMS 有哪些组件？
- 243: JMS 中如何处理异常？
- 244: JMS 中是如何确认消息的？
- 245: 解释 JMS 的消息头（message headers）。
- 246: JMS 的正文格式（body formats）有哪些？
- 247: JMS 中的管理对象（administered objects）有哪些类型？
- 248: JMS 中用于接收和创建消息的对象有哪些？
- 249: 解释 Message Consumer（消息消费者）。
- 250: 解释 Message Producer（消息生产者）。
- 251: 解释 Message Selector（消息选择器）。
- 252: 解释 Message Listener（消息监听器）。
- 253: PTP（点对点）通信需要哪些类、接口和步骤？
- 254: Pub/Sub（发布/订阅）通信需要哪些类、接口和步骤？
- 255: 解释 MDB（消息驱动 Bean）。

# 安全与遗留连接

## 安全威胁与机制

- 256: 进入企业资源有哪些各种安全威胁？
- 257: 解释 Authentication（身份验证）和 Authorization（权限控制）。
- 258: 解释 Java 中可用的一些安全包。
- 259: Java 安全管理器（Security Manager）在 Applet 中执行了哪些操作？
- 260: Java Applet 有哪些安全限制？
- 261: Applet 无法读取哪些系统属性？

## 访问控制与加密

- 262: 访问控制策略有哪些？
- 263: J2EE 支持哪些身份验证机制？
- 264: 解释加密通信。
- 265: 解释数字证书。
- 266: 解释安全套接层 (SSL)。
- 267: Web 容器执行了哪些安全检查？

## 遗留连接与 JCA

- 268: 解释遗留连接性 (legacy connectivity)。
- 269: 解释 Java 中的身份验证。
- 270: 解释 CSI。
- 271: 解释适配器 (adapter)。
- 272: 使用 J2EE 的遗留连接性。
- 273: 解释资源适配器 (Resource Adapter)。
- 274: 解释系统合约 (System contract)。
- 275: 解释 JCA 的策略。
- 276: 系统合约的类型？
- 277: 如何配置安全属性？
- 278: CCI 部分有哪些？
- 279: 解释 ManagedConnectionFactory 和 ManagedConnection。
- 280: DB 约束有哪些？

# HR 面试问题

## 职业素养与时间管理

- 1: 请讲述一次你没有按截止日期完成任务的情况。
- 2: 你在工作时如何消除干扰的？
- 3: 请讲述一次你在有截止日期的情况下工作的经历。你是如何成功的？
- 4: 请讲述一次你遇到困难截止日期的情况，你是如何完成它的。
- 5: 当你手头有多个项目时，如何保持条理？
- 6: 你每天工作中花多少时间在“自动驾驶”模式下工作？
- 7: 你如何处理截止日期？

## 问题解决与压力管理

- 8: 请讲述你解决问题的流程。
- 9: 工作中哪类事情会让你感到压力？
- 10: 当你对某事感到压力时，你是如何解决的？
- 11: 你能多任务处理吗？
- 12: 你每周工作多少小时？
- 13: 你每天检查几次邮件？

## 成就与动机

- 14: 你最大的成就是什么？
- 15: 是什么在激励着你？
- 16: 当你失去动力时你会怎么办？
- 17: 你在空闲时间喜欢做什么？
- 18: 是什么让你与众不同？
- 19: 为什么你是该岗位的最佳人选？
- 20: 成功需要什么条件？
- 21: 这个职位对你最大的挑战是什么？

## 性格特质与自我认知

- 22: 你把自己描述为内向型还是外向型？
- 23: 你具备哪些积极的特质？
- 24: 你学过的最大的教训是什么？
- 25: 请讲述一次你的长处变成劣势的情况。
- 26: 谁对你的生活影响力最大？
- 27: 你认为自己是“注重细节型”还是“大局型”的人？
- 28: 你最大的恐惧是什么？
- 29: 你喜欢哪种挑战？
- 30: 请讲述一次你感到尴尬的经历。你是如何处理的？
- 31: 你的最大缺点是什么？
- 32: 用三个形容词来描述你的工作状态。
- 33: 用三个形容词来描述你的个人生活。
- 34: 你是哪种类型的员工？

## 工作体验与价值观

- 35: 请讲述你工作中最开心的一天。
- 36: 请讲述你工作中最糟糕的一天。
- 37: 你对什么充满热情？
- 38: 你最常收到的批评是什么？
- 39: 你在什么样的工作环境中最成功？
- 40: 你是一个情绪化的人吗？

## 商业洞察与行业认知

- 41: 公司广告最好的方式是什么？
- 42: 获取新客户还是留住老客户更好？
- 43: 从竞争对手手中赢得客户的最佳方法是什么？
- 44: 你如何看待互联网的使用？
- 45: 你对我们公司的第一印象是什么？
- 46: 谈谈你的业务理念。
- 47: 业务模式中最重要的是：销售、客户服务、营销等？
- 48: 你如何关注社交媒体的新闻和趋势？
- 49: 遵守社交媒体政策会有问题吗？
- 50: 请讲述今天行业面临的最大问题之一。
- 51: 你认为在我们公司成功需要什么？
- 52: 你在这个领域工作中最喜欢的部分是什么？
- 53: 你认为你的职业在未来 10 年会发生什么？

## 沟通与冲突解决

- 54: 请描述一次你向同事传达复杂想法的经历。
- 55: 在什么情况下你觉得难以沟通？
- 56: 良好沟通的关键要素有哪些？
- 57: 请讲述一次你通过沟通解决问题的经历。
- 58: 请讲述一次你与同事发生冲突的情况。你是如何解决的？
- 59: 你是快速与人建立关系，还是需要花更多时间了解他们？
- 60: 请描述一次你必须通过办公室斗争来解决问题的经历。

> **注意**：原文中第 61-100 条问题与第 54-60 条内容高度重复，此处仅保留核心题目编号供参考，完整列表请见原文档。

# 技术面试题目分类索引

## 综合技术栈

- 1. 访问
- 2. 200
- 3. VBA
- 4. ColdFusion
- 5. 高级
- 6. 高级 JAVA
- 7. 高级 SAS
- 8. AJAX
- 9. 算法
- 10. Android 开发
- 11. Ant & Maven
- 12. Apache Web 服务器
- 13. 人工智能
- 14. ASP.NET
- 15. 自动化测试
- 16. 基础 SAS
- 17. IBM WebSphere 服务器
- 18. C 与 C++
- 19. C#
- 20. C++ 内部
- 21. CCNA
- 22. 云计算
- 23. 计算机体系
- 24. 计算机网络
- 25. 核心 Java
- 26. 数据结构与算法
- 27. 数据仓库
- 28. EJB 3.0
- 29. Entity Framework
- 30. Fedora & RHEL
- 31. GNU 开发
- 32. Hibernate, Spring & 字符串
- 33. HTML, XML
- 34. HTML5
- 35. IBM WebSphere 服务器
- 36. iOS SDK
- 37. Java / J2EE 设计模式
- 38. Java / J2EE 面试
- 39. Java 消息服务
- 40. JavaScript
- 41. Java 服务器
- 42. JDBC
- 43. jQuery
- 44. JSP-Servlet
- 45. JUnit
- 46. Linux 命令
- 47. Linux
- 48. Linux 系统管理员
- 49. Mac OS X Lion
- 50. Mac OS X Snow Leopard

## 专项面试题库

- 51. 你可能会被问 Microsoft Access 面题
- 52. 你可能会被问 Microsoft Excel 面题
- 53. 你可能会被问 Microsoft Powerpoint 面题
- 54. 你可能会被问 Microsoft Word 面题
- 55. 你可能会被问 MySQL 面题
- 56. 你可能会被问 NetSuite 面题
- 57. 你可能会被问网络面试题
- 58. 你可能会被问 OOPS 面题
- 59. 你可能会被问 操作系统面试题
- 60. 你可能会被问 Oracle DBA 面题
- 61. 你可能会被问 Oracle E-Business Suite 面题
- 62. 你可能会被问 ORACLE PL/SQL 面题
- 63. 你可能会被问 Perl 编程面试题
- 64. 你可能会被问 PHP 面题
- 65. 你可能会被问 PMP 面题
- 66. 你可能会被问 Python 面题
- 67. 你可能会被问 RESTFUL Java Web Services 面题
- 68. 你可能会被问 Ruby 面题
- 69. 你可能会被问 Ruby on Rails 面题
- 70. 你可能会被问 SAP ABAP 面题
- 71. 你可能会被问 SAP HANA 面题
- 72. 你可能会被问 SAS 编程指南面试题
- 73. 你可能会被问 Selenium 测试工具面试题
- 74. 你可能会被问 Silverlight 面题
- 75. 你可能会被问 软件仓库面试题
- 76. 你可能会被问 软件测试面试题
- 77. 你可能会被问 SQL Server 面题
- 78. 你可能会被问 Tomcat 面题
- 79. 你可能会被问 UML 面题
- 80. 你可能会被问 Unix 面题
- 81. 你可能会被问 UNIS 编程面试题
- 82. 你可能会被问 VB.NET 面题
- 83. 你可能会被问 Windows Server 2008 R2 面题
- 84. 你可能会被问 XLXP, XSLT, XPATH, XFORMS & XQuery 面试题
- 85. 你可能会被问 XML 面题

## 资源链接

访问获取完整列表：[www.vibrantpublishers.com](http://www.vibrantpublishers.com)
