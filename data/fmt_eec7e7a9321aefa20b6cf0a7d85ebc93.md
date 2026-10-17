
# UML 图表绘制

## 表 1.5（续）UML 时序图组件

| 序号 | 组件名称 | UML 符号及组件用途 |
|---|---|---|
| 2.1 | 同步消息 | - 从发送者发送的消息基于等待语义。<br>- 等待语义是指发送者在传输下一条连续消息之前，需要接收者对每条消息进行确认。<br>- 同步消息的符号是带实心箭头箭头的实线。<br><br>![Object a : Class A, Object b : Class B, 1 : Synchronous Message()] |
| 2.2 | 返回消息 | - 它代表对同步消息的回复。<br><br>![Object a : Class A, Object b : Class B, 1 : Synchronous Message(), 2 : Reply Message] |
| 2.3 | 异步消息 | - 此类消息由发送者发送给接收者，不需要接收者的确认。<br>- 该功能允许发送者向接收者发送任意数量的消息。<br><br>![Object a : Class A, Object b : Class B, 1 : Asynchronous_Message_1, 2 : Asynchronous_Message_2, 3 : Asynchronous Message_3] |
| 2.4 | 创建消息 | • 创建消息代表场景中对象的实例化。<br>• 它包含一个名为 `<<create>>` 的刻线。<br><br>![Object a: Class A Object b: Class B 1 : Creating an instance of object() <<create>>](https://example.com/image1) |
| 2.5 | 销毁消息 | • 销毁消息代表场景中对象生命周结束。<br>• 它包含一个名为 `<<destroy>>` 的刻线。<br>• 销毁在视觉上用一个指向对象生命末尾的大 X 来表示。<br><br>![Object a: Class A Object b: Class B 1 : Creating an instance of object() <<create>> 2 : Destruction of an Object() <<destroy>>](https://example.com/image2) |
| 3 | 片段 (Fragments) | • 片段代表场景中的一组条件消息或循环消息。<br>• 最关键的片段是 `opt`、`alt`、`loop`。<br>• 每个片段都由一个矩形框表示，该框封装了这些消息，左上角的标签代表片段的类型。 |
| 3.1 | Opt | • 此片段代表一个简单的 IF 场景。<br>• 只有当 `opt` 片段中定义的条件保持为真时，才会执行消息。<br>• 条件不满足的情况下，控制将跳出片段。<br>• 条件技术上称为守卫（Guard）。<br><br>![opt [Condition] 1: Message_1 2: Message_2](https://example.com/image3) |

### 表 1.5（续）UML 时序图组件

| 序号 | 组件名称 | UML 符号及组件用途 |
|---|---|---|
| 3.2 | Alt | • 此片段代表 IF ELSE 场景。<br>• 此片段在矩形区域内有两个分区。<br>• 当 `alt` 第一个分区定义的条件保持为真时，第一个分区中的消息才会被执行。<br>• 否则，执行 `alt` 片段第二个分区中的消息。![image](0.478, 0.290, 0.715, 0.439) |
| 3.3 | Loop | • 此片段代表一组重复执行的消息，直到 `loop` 片段中定义的条件不再保持为真。<br>• 此片段在矩形区域内有两个分区。<br>• 只有当 `alt` 片段中第一个分区定义的条件保持为真时，第一个分区中的消息才会被执行。![image](0.478, 0.558, 0.715, 0.672) |
| 4 | 片段嵌套 | 根据对多个条件验证或对嵌套条件集重复执行的需求，这种嵌套概念可以应用于不同类型的片段。 |

## 1.1.5 UML 协作图

大多数组件在 UML 时序图和 UML 协作图之间是通用的。表 1.6 包含了 UML 协作图唯一组件的细节。

### 表 1.6 UML 协作图的唯一组件

| 序号 | 组件名称 | UML 符号及组件用途 |
|---|---|---|
| 1 | 对象 | • 它代表系统的实体，实体通过消息与系统的其他实体进行交互。<br>• 在 UML 协作图中，对象没有生命线或控制焦点。![image](https://example.com/object_a_class_a.png) |
| 2 | 连 (Link) | • 连接允许任意两个对象之间的通信。<br>• 它表示为不带箭头的实线，因此它代表双向通信。![image](https://example.com/object_a_class_a.png) |
| 3 | 自连接 (Self Link) | • 自连接连接到自身。![image](https://example.com/object_a_class_a.png) |
| 4 | 正向刺激 (Forward stimulus) | • 它代表从发送者（第一个对象）到接收者（第二个对象）的移动。<br>• 可以是时序图中讨论的五种消息类型之一。![image](https://example.com/object_a_class_a.png) |
| 5 | 反向刺激 (Reverse stimulus) | • 它代表从接收者（第二个对象）到发送者（第一个对象）的响应。<br>• 它可以是时序图中讨论的五种消息类型之一。![image](https://example.com/object_a_class_a.png) |

## 1.1.6 状态图

表 1.7 包含了状态机组件的细节。

### 表 1.7 状态机组件

| 序号 | 组件名称 | UML 符号及组件用途 |
|---|---|---|
| 1 | 初始状态 | 它代表系统的开始状态。 |
| 2 | 结束状态 | 它代表系统的结束状态。 |
| 3 | 流结束 | 它代表状态机路径的异常终止，不视为系统的一部分。 |
| 4 | 状态 (State) | 它代表被考虑对象的状态。<br>使用以下属性描述：<br>i. Name – 名称。<br>ii. Entry – 进入系统前执行的动作。<br>iii. Do – 在状态内执行的动作。<br>iv. Exit – 退出系统所需的动作。 |
| 5 | 转换 (Transition) | 箭头表示从一个状态到另一个状态的移动，由源状态的完成触发。 |
| 6 | 自转换 | 它代表状态内部转换。 |
| 7 | 汇合点 (Junction Point) | • 其目的是合并不同状态的输入流。<br>输入不是同步的；如果流到达状态，它将继续，无需等待来自其他状态的流。 |

### 表 1.7（续）状态机组件

| 序号 | 组件名称 | UML 符号及组件用途 |
|---|---|---|
| | | ![image](https://example.com/diagram1.png) |
| 8 | 选择点 (Choice Point) | - 选择点根据其设计具有一个输入或多个输出。<br>- 每个输出流都附加了一个条件。<br>如果满足条件，流将沿着相应的输出进行。![image](https://example.com/diagram2.png) |
| 9 | 浅历史 (Shallow History) | - 状态的浅历史指向同一层级结构上最近访问的状态。![image](https://example.com/diagram3.png) |
| 10 | 深历史 (Deep History) | - 状态的深历史指向最近访问的简单状态。![image](https://example.com/diagram4.png) |
| 11 | 子状态机状态 (Submachine state) | - 子机状态是一个未来可能作为另一个状态图场景的状态。![image](https://example.com/diagram5.png) |

## 1.1.7 UML 类图

表 1.8 包含了 UML 类图组件的详细信息。

### 表 1.8 UML 类图的组件

| 序号 | 组件名称 | UML 符号及组件的作用 |
| --- | --- | --- |
| 1 | 类 (Class) | • 每个类都有三个部分，即：<br>i. 顶部部分表示类的名称，<br>ii. 中间部分表示类的结构（属性），以及<br>iii. 底部部分表示类的行为（操作）<br><br>![Class Diagram](image_url)<br><br>• 属性（Attribute）表示描述对象状态的属性。<br>• 语法：可见性 属性名 : 数据类型<br>• 数据类型示例有：`Int`, `Char`, `Float`, `String`, `Date`, `Time`, `Money`, `Dollars`, `Colour`, `Country`, `Postal Code`, `Address`, 等。 |
| | 可见性符号 | 访问修饰符 |
| | `+` | 公有 (Public) |
| | `#` | 保护 (Protected) |
| | `-` | 私有 (Private) |
| | | 衍生属性是通过其他属性计算或得出的属性，在名称前用斜杠 (`/`) 表示。<br>• 语法：`/可见性 属性名:数据类型`<br>• 可见性 操作名 (输入参数) 表示类可以执行的操作或函数。<br>• 输入参数采用与属性相同的语法。<br>• 不返回值的方法（即 `void` 方法）应给出一个返回类型 `void`。 |
| 2 | 类关系 (Class Relationships) | 类关系有七种类型，即关联、单向关联、依赖、聚合、组合、泛化、实现。 |
| 2.1 | 关联 (Association) | 当两个类之间相互通信时，使用关联来连接这两个类。<br><br>![Association Diagram](image_url) |

### 表 1.8（续） UML 类图的组件

| 序号 | 组件名称 | UML 符号及组件的作用 |
| --- | --- | --- |
| 2.2 | 单向关联 (Directed Association) | • 当两个类通过优先考虑单向通信的方式连接时，它们通过单向关联连接。<br><br>![Class1, Class 2, +Attribute, 关联名称, +Attribute, +Operation(), +Operation()] |
| 2.3 | 依赖 (Dependency) | • 当一个类的存在依赖于另一个类的存在时，它们使用依赖连接。<br><br>![Class1, Class 2, +Attribute, +Attribute, +Operation(), +Operation()] |
| 2.4 | 聚合 (Aggregation) | • 它表示一种“部分”关系。<br>• `Class1` 的多个实例可以与 `Class2` 关联。<br>• 聚合意味着一种子类可以独立于父类存在的关系。<br><br>![Class1, Class 2, +Attribute, +Attribute, +Operation(), +Operation()] |
| 2.5 | 组合 (Composition) | • 它表示一种“整体”关系。<br>• 组合意味着子类无法独立于父类存在的关系。<br><br>![Class1, Class 2, +Attribute, +Attribute, +Operation(), +Operation()] |
| 2.6 | 泛化 (Generalization) | • 泛化代表了继承的概念。<br>• 它表示父类与其子类之间的关系。<br><br>![父类, +Attribute, +Operation(), 子类 1, 子类 2, +Attribute, +Attribute, +Operation(), +Operation()] |

### 表 1.8（续） UML 类图的组件

| 序号 | 组件名称 | UML 符号及组件的作用 |
|---|---|---|
| 2.7 | 接口与实现角色 (Interface & role of Realization) | * 接口有两种类型：提供接口和依赖接口。<br>* 提供接口是类提供的功能。<br>* 依赖接口是另一个类所需的功能。<br>* 实现是由类实现的接口。<br>* 可见性 属性名:数据类型<br>* 操作名 (输入参数) 表示类可以执行的操作或函数。<br>* 输入参数采用与属性相同的语法。<br>* 方法不返回值的方法（即 `void` 方法）应给出一个返回类型 `void`。<br>![Realization](image_url) |
| 3 | 实现 (Realization) | * 接口有两种类型：提供接口和依赖接口。<br>* 提供接口是类提供的功能。<br>* 依赖接口是另一个类所需的功能。<br>* 实现是由类实现的接口。<br>* 可见性 属性名:数据类型<br>* 操作名 (输入参数) 表示类可以执行的操作或函数。<br>* 输入参数采用与属性相同的语法。<br>* 方法不返回值的方法（即 `void` 方法）应给出一个返回类型 `void`。<br>![Realization](image_url) |

## 1.1.8 UML 组件图

表 1.9 包含了 UML 组件图组件的详细信息。

### 表 1.9 组件图的组件

| 序号 | 组件名称 | UML 符号及组件的作用 |
| --- | --- | --- |
| 1 | 组件 (Component) | 组件是系统中的模块化部分。<br>* 它封装了其内部实现。<br>* 它们是可替换的。 |
| 2 | 接口 (Interface) | * 接口有两种类型：提供接口和依赖接口。<br>* 提供接口是类提供的功能。<br>* 依赖接口是另一个类所需的功能。<br>* 实现是由类实现的接口。<br>* 可见性 属性名:数据类型<br>* 操作名 (输入参数) 表示类可以执行的操作或函数。<br>* 输入参数采用与属性相同的语法。<br>* 方法不返回值的方法（即 `void` 方法）应给出一个返回类型 `void`。<br>![Interface](image_url) |
| 3 | 实现 (Realization) | * 接口有两种类型：提供接口和依赖接口。<br>* 提供接口是类提供的功能。<br>* 依赖接口是另一个类所需的功能。<br>* 实现是由类实现的接口。<br>![Realization](image_url) |

### 1.1.9 UML 部署图

表 1.10 包含了 UML 部署图组件的详细信息。

### 表 1.10 部署图的组件

| 序号 | 组件名称 | UML 符号及组件的作用 |
| ------ | --- | --- |
| 1 | 节点 (Node) | 具有内存和处理能力的计算资源。<br>- 节点有两种类型：设备节点和执行环境节点。<br>- 设备节点代表应用服务器、工作站、移动设备、嵌入式设备等。<br>- 执行环境节点代表操作系统、工作流引擎、浏览器、容器、Web 服务器、数据库系统等。 |
| 2 | 制件 (Artifact) | |
| 3 | 端口 (Port) | - 端口允许设备节点与执行环境节点之间的通信。<br>- 它也允许节点与外部环境之间的通信。 |

### 表 1.10（续） UML 部署图的组件

| 序号 | 组件名称 | UML 符号及组件的作用 |
|---|---|---|
| 4 | 关联 (Association) | • 它表示两个参与关系的类之间的双向通信。<br><br>![Component, Association Name, Component 1] |
| 5 | 单向关联 (Directed Association) | • 它表示两个参与关系的类之间的单向通信。<br><br>![Directed Association] |
| 6 | 依赖 (Dependency) | • 它表示一个节点的存在是否依赖于另一个节点。<br><br>![Dependency] |

# 第 2 章

## Webmed 医疗服务系统的 UML 图设计

医疗服务如今需求巨大，因为它确实有助于管理医院或诊所。医疗服务系统的范围每天都在扩大，在全球范围内都是如此。这些解决方案之一包括提高对医疗服务和健康政策的意识。该系统的目标是通过技术帮助即时提供医疗援助。

## 2.2 主要功能及其描述

该系统的主要功能及其描述如下：

- 注册（Register）—— 此功能作为一种会员功能，允许用户（患者或护理人员）在网站上注册，以访问所有资源。
- 登录（Login）—— 此功能验证用户身份以提供访问权限。
- 设施（Facilities）—— 此功能允许我们访问网站上提供的所有选项。
- 注销（Logout）—— 这允许我们购买保险，或为消耗的医疗服务付费。
- 财务（Finance）—— 健康 A–Z：此功能提供所有疾病的详细信息。
- 资源（Resources）—— 此功能包含子功能，即症状检查、健康计算器、寻找医生、保险指南和救护车服务。
- 药物和补充剂（Drugs and supplements）—— 此功能提供药品在线配送。该功能根据医生的处方和患者的在线购买意愿发放药物。
- 新闻与专家（News and experts）—— 此功能提供健康意识和当前的健康威胁。
- 支付（Payment）—— 此功能处理所消耗服务的费用。该功能分为两个子功能，即针对已发布服务的支付以及针对在线药品配送的支付。
- 反馈（Feedback）—— 此功能收集用户对本网站的评论。
