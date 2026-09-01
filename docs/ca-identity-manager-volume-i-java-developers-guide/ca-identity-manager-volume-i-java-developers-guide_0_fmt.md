
# CA Identity Manager Volume I：Java 开发者指南我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。![](img/image_rsrc8PK.jpg)

# 前言

我的《CA IdentityMinder（原 CA Identity Manager）编程》系列由三本书组成：

- 《CA Identity Manager 第一卷：Java 开发者指南》，适用于入门级别。
- 《CA Identity Manager 第二卷：通过示例代码学习》，适用于进阶水平。
- 《CA Identity Manager：自定义连接器指南》，为自定义连接器开发者编写。

请访问书籍网站获取更多详情。

## 关于本书

你将学习到：

- `CA IdentityMinder` 管理概念
- `CA IdentityMinder` 编程概念
- 如何开发业务逻辑任务处理程序（Business Logic Task Handler）及示例代码。
- 如何创建自定义工作流及工作流 API 示例代码。
- 如何实现参与者解析 API（Participant Resolver API）及示例代码。
- 如何实现事件监听器 API（Event Listener API）及示例代码。
- 如何实现逻辑属性 API（Logical Attribute API）及示例代码。
- 如何实现验证规则（Validation Rules）及示例代码。
- 如何实现电子邮件通知及示例代码。
- 如何实现通知规则 API（Notification Rule API）及示例代码。
- 如何实现任务执行 Web 服务（TEWS）及示例代码。

## 本书适用对象

本书适用于具备少量 Java 编程基础，并希望学习如何通过 API 实现 `CA IdentityMinder` 要求的初。

![](img/image_rsrc8PM.jpg)

## 规范

本文档使用了以下文本规范：

| 规范 | 含义 |
| :--- | :--- |
| **粗体** | 粗体表示书名 |
| *斜体* | 斜体表示强调或占位符变量 |
| `等宽` | 等宽字体表示语言和语法元素 |

## 客户支持

我们随时欢迎读者的反馈。请告诉我们你对这本书的看法。请访问网站获取更多详情：

- 书籍网站：[`www.caidentitymanagerbook.com`](http://www.caidentitymanagerbook.com)
- 博客及更新内容：[`caidentitymanager.blogspot.com`](http://caidentitymanager.blogspot.com)

如需向我们发送普通反馈或问题，请直接发送电子邮件。请查看网站上的我的邮箱。

## 下载源代码

请访问我们的网站：[`www.caidentitymanagerbook.com`](http://www.identitymanagerbook.com)

### 6.3.1 编程

### 6.3.2 代码示例

### 6.3.3 用例

## 6.4 验证规则

### 6.4.1 编程

### 6.4.2 代码示例：任务级验证

### 6.4.3 代码示例：目录级验证

## 6.5 邮件通知

### 6.5.1 如何实现邮件通知

### 6.5.2 代码示例：邮件模板

### 6.5.3 代码示例：通过 Service API 发送邮件通知

## 6.6 通知规则 API

### 6.6.1 编程

### 6.6.2 代码示例

### 6.6.3 用例

### 6.6.4 通知规则与邮件模板限制以及 Service API

## 6.7 任务执行 Web 服务（TEWS）

### 6.7.1 代码示例

## 6.8 其他概念

## 6.9 结论

# 附录 A：导入工作流

# 附录 B：热部署

# 第一章 引言

`CA IdentityMinder` 的核心特性是不需要自定义代码即可进行自定义，但在本书中讨论自定义代码。使用自定义代码有两个主要原因：

- 用于管理的控制台。
- 用于交互的用户控制台。

## 1.1 为什么我们需要自定义代码

`CA IdentityMinder` 的核心特性是不需要自定义代码即可进行自定义，但在本书中我们将讨论自定义代码。使用自定义代码有两个主要原因：

- 自定义复杂的业务逻辑。
- 灵活的工作流管理。

在 `CA IdentityMinder` 中，你可以使用自定义代码来扩展平台的功能。在 `CA IdentityMinder` 中实现自定义代码有多种方法：

- `CA IdentityMinder` 是一个身份生命周期管理平台。
- `CA IdentityMinder` 提供了一个用于身份相关流程自动化的强大框架。

`CA IdentityMinder` 还允许你通过 API 和连接器与其他第三方系统集成。这确保了身份数据在整个企业中同步。

## 1.2 本书涵盖的内容

本书提供了一份在 `CA IdentityMinder` 中使用自定义代码的全面指南。我们将涵盖以下主题：

- 第一章：`CA IdentityMinder` 简介及自定义代码。
- 第二章：`CA IdentityMinder` 的管理。
- 第三章：工作流概念 - 理解工作流如何工作。
- 第四章：业务逻辑任务处理器 - 如何实现自定义逻辑。
- 第五章：工作流 - 如何设计和管理工作流。
- 第六章：其他 API - 使用可用的 API 进行自定义开发。

## 1.3 技术术语

为了避免新学者产生困惑，这里有一些技术术语：

### 端点（Endpoint）

端点是存储或管理用户数据的目标。端点的示例可以是 Microsoft Active Directory、SAP、数据库、Unix 工作站或应用程序。

### 用户（User）vs 全局用户（Global User）vs 账户（Account）

在 `CA IdentityMinder` 中，有三种与身份相关的实体：

用户是指由 `CA IdentityMinder` 服务器维护的用户信息。用户存储在 `CA IdentityMinder` 用户存储（User Store）中。

全局用户是指由配置服务器（Provisioning Server）维护的用户信息。它存储在配置目录（Provisioning Directory）中。

账户是指端点中的用户信息。例如，Active Directory 中的账户。

下图显示了用户、全局用户和账户之间的关系。某些用户拥有对应的全局用户。当用户接收到配置角色时，配置服务器会创建一个全局用户。当服务器启动配置过程时，全局用户中的某些属性会被配置到账户中。

连接器（Connector）是与端点的软件接口。`Provisioning Server` 使用 `connector` 与端点进行通信。它将 `Provisioning Server` 的操作转换为端点的更改，例如“在 Microsoft Exchange 端点上创建一个新的电子邮件账户”。

`Connector Servers` 是一个管理连接器的服务器组件。连接器服务器有两种类型：

- `CA IAM Connector Server`（`CA IAM CS`）管理用 Java 编写的连接器。
- `C++ Connector Server`（`CCS`）管理用 C++ 编写的连接器。

连接器和代理（Connectors and Agents），某些连接器需要在其管理的系统中安装代理程序，以便完成通信周期。

`Connector Xpress` 是 `CA IdentityMinder` 的一个实用，用于管理动态连接器、将动态连接器映射到端点以及为端点建立路由规则。你可以使用它来配置动态连接器，允许对 SQL 数据库和 LDAP 目录进行配置和管理。

### 附加组件

在安装 `CA IdentityMinder` 时，会自动安装 `WorkPoint` 工作流引擎和 `WorkPoint Designer`。这些组件允许你将 `CA IdentityMinder` 任务置于工作流控制之下，并修改现有的工作流过程定义或创建新定义。

`Provisioning Manager` 是管理全局用户和配置服务器选项的图形化界面。你也可以使用 `Provisioning Manager` 来管理端点或账户。

## 1.5 服务器配置

本书假设你已经安装并配置了：

- `CA IdentityMinder` 和用户存储库（user store）。
- `Provisioning Server`、`provisioning manager` 和 `provisioning directory`。
- `Connector server`
- `Wokpoint designer`

我的建议是配置一个 `Microsoft Active Directory` 端点、账户模板以及配置角色（provisioning role）。你应该在 `IDM` 系统中拥有一些用户和账户。

### 用户存储属性

在书中，我们要求 `City`（城市）和 `telephone number`（电话号码）作为主要属性，但其他章节还需要额外的属性。我们将创建 3 个管理任务：

- `Update Location and Ext Number`（更新位置和分机号），几乎用于每个章节。
  - 需要属性：`L`（或 `City`）
  - 需要属性：`telephoneNumber`。
  - 在第 2 章中，我们的 `Express` 策略示例需要 `state`（州）。
- `Update office`（更新办公室），用于第 6 章：仅限 `Logical Attribute API`。
  - 需要属性：`L`（或 `City`，与上一个相同）。
- `Update Employee Number`（更新员工编号），用于第 6 章：仅限 `Validation Rule`。
  - 需要属性：`employee number`。

请检查 `Management Console`（管理控制台），选择 `Directory > User Store (Cooperate Store) > User` 并检查属性。

![](img/image_rsrc8PT.jpg)

图 1-4 显示显示名称。

### 全局用户属性

在 `Management Console` 中，选择 `Directory > Provisioning Store > Global User` 并检查属性 `Physical Name`（物理名称）和 `eTCity`。

![](img/image_rsrc8PU.jpg)

图 1-5 显示 `eTCity` 的显示名称。

### 属性映射

在 `Management Console` 中，选择 `Environment > your environment > Advanced Settings > Provisioning` 并检查属性映射：`User Attribute l` 映射到 `Provisioning Attribute eTCity`。

![](img/image_rsrc8PV.jpg)

图 1-6 显示属性映射。

## 1.6 结论

我们介绍了自定义代码和服务器配置的优势。在下一章中，你将学习 `CA IdentityMinder` 管理的基本概念。

# 第 2 章 管理概念

如果你熟悉 `CA IdentityMinder`，可以快速跳过这一章。在本章中，你将学习：

- 如何创建 `admin task`（管理任务）。
- 配置（provisioning）是如何运作的。
- `Identity Policy Set`（身份策略集）和 `Policy Xpress` 如何工作。
- 理解提交的任务和事件。

要在一个章节中解释所有的管理功能是困难的。我们将只关注与编程相关的某些部分。如果你是 `CA IdentityMinder` 的新手，可能会因为功能太多而容易迷失。我们将使用 `admin task` 作为主要主题。

## 2.1 需求与设计

在本章中，我们将通过管理员工具实现需求。

### 需求

我们的需求需要一个界面来修改城市和分机电话号码。需求可以写为如下步骤：

- `Step1`：以管理员身份登录 `Identity Manager User Console`，并选择表单“Update location and Ext Number”。
  - 从下拉菜单中选择 `city`。
  - 填写 `extension number`。
  - 点击 `submit`（提交）。
- `Step 2`：系统更新用户属性：
  - 根据 `city value` 更新 `city` 属性并设置 `country`。
  - 连接 `office number` 和 `extension number`。
- `Step 3`：系统更新账户属性：`city` 和 `telephone number`。

### 设计

我们将通过以下方式实现每个需求的步骤：

- `Step 1`：提供界面。
  - 创建 `admin tasks` 和带有 2 个属性的界面：`city` 和 `extension number`。
- `Step 2`：处理。
  - 我们使用 `Policy Set` 将 `city` 映射到 `country`。
  - 我们使用 `Policy Xpress` 拼接 `office number` 和 `extension number`。
- `Step 3`：配置（Provisioning）。
  - 配置 `attribute mapping`（属性映射）。
  - 执行 `account synchronization`（账户同步）。

![](img/image_rsrc8PW.jpg)

图 2-1 显示如何实现需求。

## 2.2 创建管理任务

`Admin tasks` 是主要功能之一。几乎所有需求都从管理任务开始。`Admin task` 是用户在 `CA IdentityMinder` 中可以执行的行政功能。`Admin Tasks` 可能是 `Create User`、`View User`、`Modify User`、`Reset User` 等。我们在 `home > tasks` 下可以看到。

![](img/image_rsrc8PX.jpg)

图 2-2 显示控制台中的任务。

我们将从管理任务开始：

- 登录 `Admin Console`。
- 点击 `Admin Tasks`。
- 然后选择 `Create new Admin Task` 并点击 `OK`。

![](img/image_rsrc8PY.jpg)

图 2-3 显示菜单。

选择管理任务后，将显示 5 个标签页（见下）：

1. `Profile tab`（配置标签页）包含基本信息（`name`），如何在菜单中显示，主对象和操作，当同步工作时。
2. `Search tab`（搜索标签页），涉及 `profile tab` 中的主对象，如何搜索主对象。
3. `Tabs tab`（标签标签页）用于添加标签。
4. `Fields tab`（字段标签页）显示此管理任务中的字段。
5. `Events tab`（事件标签页）显示提交任务后将生成哪些事件。

![](img/image_rsrc8PZ.jpg)

图 2-4 显示创建任务时的 5 个标签页。

### 2.2.1 Profile Tab

在 `profile tab` 中有 5 个部分：

#### 1. General Information（常规信息）

有 3 个字段：

| Field Name | Value | Description |
| :--- | :--- | :--- |
| Name | Update Location and Ext Number | 任务将显示在菜单中 |
| Tag | BookUpdateLocNo | 任务的唯一值 |
| Description | Example for Administrative | 描述 |

![](img/image_rsrc8R0.jpg)

图 2-5 显示菜单上的名称。

#### 2. 如何在菜单中显示？

`Admin Task` 有界面，因此我们必须决定界面在哪里。有 3 个字段：

| Field Name | Value | Description |
| :--- | :--- | :--- |
| Task Order | 1 | 指定在菜单中的显示顺序。![](img/image_rsrc81.jpg) |
| Category | Book Example | 类别作为屏幕顶部的标签显示，按数字降序排列。![](img/image_rsrc8R2.jpg) |
| Category Order | 11 |  |
| Category 2 | Tasks | 指定二级/三级类别，作为标签列表下方的链接出现。![](img/image_rsrc8R3.jpg) |
| Category 2 Order | 0 |  |
| Category 3 | Basic |  |
| Category 3 Order | 0 |  |

![](img/image_rsrc8R4.jpg)

图 2-6 显示类别值。

#### 3. 主对象和操作是什么？

非常重要。这就像是在问问题：你想做什么？我想修改用户信息。所以主对象应该是 `user`，操作应该是 `modify`。

| Field Name | Value | Description |
| :--- | :--- | :--- |
| Primary Object | User | 指定任务的操作的对象。 |
| 操作 | 修改 | 指定在对象上执行的操作。 |

#### 4. 同步

本节描述了提交此任务后的同步行为。共有 2 类同步：

- `User Synchronization` 意味着任务将与设置了“身份策略”的用户进行同步。
- `Account Synchronization` 意味着此任务中的任何修改都将与全局用户和账户同步。

有 3 个选项可以告诉我们何时执行同步：



- `None`：什么都不做，不进行同步。
- `On Task completion`：意味着任务完成后将触发同步。
- `On Every Event`：当任务提交后，会生成许多事件。将在每个事件完成时发生同步。此选项可能会影响性能，因为同步可能会发生多次。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| User Synchronization | On Task completion |我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。任务完成后将与设置了“身份策略”的用户同步 |
| Account Synchronization | On Task completion | 任务完成后将同步端点上的账户 |
| ![](img/image_rsrc8R5.jpg) | | |

图 2-7 显示了屏幕上的值。

## 5. 附加功能

本节中的所有属性在我们编程时都非常有用。我们将在下一章中介绍更多细节。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Hide In Menus | 不勾 | 如果勾选，此任务将不在菜单中显示。 |
| Public Task | 不勾 | 如果勾选，此任务可以在未登录的情况下调用。 |
| Enable Auditing | check | 如果勾选，在审计数据库中记录此任务。 |
| Enable Workflow | 勾 | 如果勾选，在事件级别启用工作流。 |
| Enable Web Services | 勾 | 如果勾选，此任务可以通过网络服务调用。 |
| Workflow Process | 不 thing | 如果选择，支持任务层级的工作流。 |
| Task Priority | Medium | 决定执行任务的顺序。 |
| Business Logic Task Handlers | 不 thing | 关联业务逻辑任务处理器。 |
| ![](img/image_rsrc8R6.jpg) | | |

图 2-8 显示了屏幕上的值。

不要提交，选择“Search（搜索）”标签。

### 2.2.2 Search 标签

根据你的主对象，某些任务需要搜索界面。在 Profile（个人资料）标签页中，我们选择的主对象是“User（用户）”，操作是“Modify（修改）”。因此，在我们修改用户之前，我们需要搜索用户进行修改。如果你的主对象是“NONE”，则没有必要搜索。

| ![](img/image_rsrc8R7.jpg) | | |

图 2-9 显示了示例屏幕：搜索用户。

在 Search 标签页上，点击 Browse（浏览），选择屏幕 Name：“Default Search Screen（默认搜索界面）”，Type：“Standard Search Screen（标准搜索界面）”。

| ![](img/image_rsrc8R8.jpg) | | |

图 2-10 选择界面“Default User Search（默认用户搜索）”。

不要提交，点击“Tabs（标签页）”标签进入下一节。

### 2.2.3 Tabs 标签

在用户界面上，一个管理任务可以有很多标签页。每个标签页都有不同的目的。下图显示了管理任务“Modify User（修改用户）”有 5 个标签页的示例。每个标签页都有自己的屏幕。

| ![](img/image_rsrc8R9.jpg) | | |

图 2-11 显示了管理 Modify User 中的标签示例。

在本节中，你必须回答三个问题：

- 是什么类型的标签？
- 此管理任务内部有多少个标签页？
- 每个标签页内部是什么屏幕？

#### 标签类型

有 3 种标签控制器（Tab Controller）：

- `Standard Tab Controller`，每个标签将显示在管理任务的顶部。我们可以从顶部选择任何标签。
- `Wizard Tab Controller`，它将以逐步的方式显示，按钮将为“Next（下一步）”。用户必须检查每个屏幕。
- `Sequence Tab Controller`，我们在屏幕上看不到任何标签，但用户将看到“next（下一步）”按钮。

| ![](img/image_rsrc8RA.jpg) | | |

图 2-12 显示标签类型的比较。

在我们的代码中，我们选择了 `Standard Tab Controller`。

#### 此管理任务内部有多少个标签页？

从下方的下拉菜单添加标签。在我们的示例中，我们要修改用户，所以我们选择了 Profile（个人资料）。（`UserProfile`）

| ![](img/image_rsrc8RB.jpg) | | |

图 2-13 显示如何添加标签。

#### 每个标签页内部是什么屏幕

每个标签必须有一个屏幕，我们点击铅笔（Pencil）图标来添加屏幕。

| ![](img/image_rsrc8RC.jpg) | | |

图 2-14 显示添加屏幕的“Pencil（铅笔）”图标。

然后点击 Browse（浏览）选择屏幕。

| ![](img/image_rsrc8RD.jpg) | | |

图 2-15 显示选择屏幕的 Browse 按钮。

我们的原型需要 2 个属性，因此我们需要创建一个新屏幕。因此，我们选择了“New（新建）”按钮。

| ![](img/image_rsrc8RE.jpg) | | |

图 2-16 显示了我们的原型。

| ![](img/image_rsrc8RF.jpg) | | |

图 2-17 显示如何创建新屏幕。

然后我们添加屏幕名称和标签：

| 字段名称 | 值 |
| :--- | :--- |
| Name | Update Location and Ext Number |
| Tag | UpdateLocationandExtNumber |

所以我们在屏幕上需要 2 个属性，点击铅笔图标添加属性。

| ![](img/image_rsrc8RG.jpg) | | |

图 2-18 显示添加属性的铅笔图标。

第一个是用户属性：`City`。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Attribute Name | City | 与用户属性同步 |
| Style | Dropdown | 下拉框 |
| Name | City | 显示在屏幕上的标签 |
| Source of options | Simple List | 简单列表 |
| ![](img/image_rsrc8RH.jpg) | | |

图 2-19 显示了属性值。

所以我们在屏幕上需要 2 个属性，点击铅笔图标添加属性。

| ![](img/image_rsrc8RJ.jpg) | | |

图 2-20 显示了属性的值。

| ![](img/image_rsrc8KK.jpg) | | |

图 2-21 显示了选择屏幕。

| ![](img/image_rsrc8RM.jpg) | | |

图 2-22 显示了确认屏幕。

你已经完成了这一步。点击“Fields（字段）”标签。

### 2.2.4 Fields 标签

此标签的好消息是，你不需要做任何事情。你只需要查看字段。你会看到在“Update Location and Ext Number”屏幕中使用的字段：`ExtNumber` 和 `City`。其他属性是主对象 User。

| ![](img/image_rsrc8RN.jpg) | | |

图 2-23 显示字段标签。

然后点击“submit（提交）”。

### 2.2.5 Event 标签

Event 标签中的列表在我们创建管理任务时不会立即显示。将在提交创建管理任务后显示。

进入 Modify Admin Task（修改管理任务）菜单。从下拉菜单中选择类别并输入“book”。选择任务“Update Location and Ext Number”并点击 Select（选择）按钮。

| ![](img/image_rsrc8RP.jpg) | | |

图 2-24 显示搜索管理任务屏幕。

选择 Event（事件）标签，你会看到事件列表。在本章中，我们不对事件标签进行任何操作。

| ![](img/image_rsrc8RR.jpg) | | |

图 2-25 显示 Event 标签。

### 将生成多少个事件？

生成的事件数量和类型取决于主对象、操作和标签。

| ![](img/image_rsrc8RS.jpg) | | |

图 2-26 显示事件生成的关系。

### 2.2.6 Role Use 标签

此标签将显示谁可以使用此管理任务。现在你什么也看不见。

| ![](img/image_rsrc8RT.jpg) | | |

图 2-27 显示 Role Use 标签。

我们将管理角色“System Manager”添加到此管理任务中。选择 Roles and Tasks（角色与任务）> Admin Roles（管理角色）> Modify Admin role（修改管理角色）> 选择 Admin Role“System Manager”并点击 Tasks 标签。

| ![](img/image_rsrc8RU.jpg) | | |

图 2-28 显示管理角色屏幕。

滚动到屏幕底部，选择按类别筛选 `Book Example` 并添加任务 `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)`。

| ![](img/image_rsrc8RV.jpg) |

图 2-29 显示了我们选择的任务。

## 2.3 配置（Provisioning）

本主题的目标是理解配置（配置）是如何运作的。实现配置需要 4 个配置步骤：

1. 步骤 1：获取端点（Endpoint）
   - `Endpoint` 可以是 `Microsoft Active Directory` 或数据库。
2. 步骤 2：创建账户模板（Account Template）
   - 关联到 `endpoint`。
   - `Account template` 定义了全局用户与账户之间的属性映射。
3. 步骤 3：创建配置角色（Provisioning Role）
   - 关联到 `account templates`。
   - 一个配置角色可以拥有多个 `account templates`。
4. 步骤 4：将用户添加到配置角色中。

整个步骤如图所示。

| ![](img/image_rsrc8RW.jpg) |

图 2-30 显示了所有步骤和相关界面。

### 2.3.1 账户模板与属性映射

`Account templates` 定义了（全局）用户如何在受管的 `endpoint` 中表示。默认情况下，`account templates` 使用 `Rule String`（规则字符串）定义映射，例如 `%USA%` 或 `%UC%`。你可以在官方文档 `Administration Guide` 中查看更多详情。定义映射有两种方式：

1. `Rule String`：官方文档为某些属性定义了 `Rule String`，并非所有属性。
2. `Global User attributes`（全局用户属性）：如果没有 `Rule String` 映射，你可以使用这种。格式为 `%#<attribute name>%`。

例如，账户模板中的城市（city）属性，你可以放置：

- `Rule String`: `%UC%`
- `Global User attributes`: `%eTCity%`

两种方式得到的结果相同。下图显示了账户模板中全局用户属性的城市（city）值。

| ![](img/image_rsrc8RX.jpg) |

图 2-31 显示了账户模板中的全局用户属性。

另一个使用全局用户属性的示例是图中的账户容器（account container）。例如，如果 `eTGlobalUser` 具有 `eTLocation=northamerica`，那么容器将是 `eTADSOrgUnitName=Users`, `eTADSOrgUnitName=NorthAmerica`。这些值都是全局用户属性。

| ![](img/image_rsrc8RY.jpg) |

图 2.32 显示了账户模板和全局用户属性界面。

### 2.3.2 配置目录（Provisioning Directory）

你可以从配置目录中获取全局用户属性。你必须使用 `Client LDAP`（如 `JXplorer`）连接配置目录。你可以从 `Management Console` 获取配置存储信息。选择 `Provisioning store` 并检查 `URL`。

| ![](img/image_rsrc8RZ.jpg) |

图 2-33 显示了配置目录的连接性。

#### 全局用户（Class: `eTGlobalUser`）

在配置目录内部，浏览到路径 `eTGlobalUserContainerName=Global Users, eTNamespaceName=CommonObjects, dc=im, dc=eta`，该位置保留了所有全局用户。

选择一个用户，你可以看到属性名称和值。（你可以在账户模板中使用此属性名称。）

| ![](img/image_rsrc8S0.jpg) |

图 2-34 显示了全局用户的路径和属性 `eTCity`。

#### 账户（Class: `eTADAccount`）

如果你已经在端点 `Active Directory` 中拥有一些账户，那么请浏览路径 `eTADSDirectoryName=<Endpoint Name>, eTNamespaceName=ActiveDirectory, dc=im, dc=eta`。它代表 `Endpoint (Active Directory)`。

| ![](img/image_rsrc8S1.jpg) |

图 2-35 显示了账户对象的属性。

位于 `eTADSDirectory` 路径下的对象 `eTADAccount` 代表账户（Account）。如果你直接在账户对象（`eTADAccount`）中修改某些值，该值将立即反映在 Active Directory 的值上。例如，我们将 `eTADSl`（代表城市 City）的值从“New York”更改为“New York Test”，并查看 Active Directory，值也会随之改变。

| ![](img/image_rsrc8S2.jpg) |

图 2-36 显示了 `eTADAccount` 与 AD Account 的关系。

我们不建议直接在账户对象（`eTADAccount`）内部更改任何值，因为 CA IdentityMinder 将其视为内部处理。当你进行编程并尝试修改值但遇到错误时，这可能对调试有用。你可能会打印该值并直接放入账户对象中。看看是否允许。

访问全局用户或账户的另一种选择是使用 `Provisioning Manager`，但你无法从界面看到属性名称。

### 2.3.3 属性映射：用户 - 全局用户 - 账户

为了更好地理解，本节描述了从用户到全局用户以及从全局用户到账户的属性映射。

#### 用户存储（User Store）

从 `Management Console` 检查用户存储连接信息，并使用任何 LDAP 客户端（如 `JXplorer`）登录用户存储。

| ![](img/image_rsrc8S3.jpg) |

图 2.-37 显示了用户存储的连接性。

我们可以在 `Management Console` 中看到属性映射：用户属性到全局用户属性。在 `Management Console` 中，选择 `Environment > your environment > Advanced Settings > Provisioning > Attribute Mappings`。

| ![](img/image_rsrc8S4.jpg) |

图 2-38 显示了 Management Console 中的映射。

图中显示了从用户到账户的属性映射。在 `Management Console` 中，用户将全局用户属性 `eTCity` 映射到账户模板（Account Template）。

| ![](img/image_rsrc8S5.jpg) |

图 2-39 显示了映射。

### 2.3.4 同步（Synchronization）

我们学习了用户到账户的属性映射，接下来需要学习它是如何工作的。

#### 当全局用户创建时？

在配置角色（provisioning role）中，我们使用默认值 = all。

| ![](img/image_rsrc8S6.jpg) |

图 2-40 显示了全局用户创建时。

#### 属性同步时？

在任务中选择“Account Synchronization”选项将触发配置。

| ![](img/image_rsrc8S7.jpg) |

图 2-41 显示了同步下拉菜单。

#### 什么是用户同步？

用户同步下拉菜单将涉及配置策略集。我们将讨论配置策略集。

| ![](img/image_rsrc8S8.jpg) |

图 2-42 显示了同步下拉菜单。

## 2.4 配置策略集（Policy Set）和 Xpress

回到我们的示例，我们创建：

- `Policy Set` 映射城市到国家。
- `Policy Xpress` 拼接号码和扩展。

| ![](img/image_rsrc8S9.jpg) |

图 2-43 显示了如何实现需求。

### 2.4.1 配置策略集（Policy Set）

配置策略是在用户满足特定条件时发生的业务变更。打开 CA IdentityMinder 控制台并选择 `Policies` 标签页，点击菜单 `Create Policy Set`。

| ![](img/image_rsrc8SA.jpg) |

图 2-44 显示了“Create Policy Set”菜单。

#### Profile 标签卡

第一个标签卡 Profile，放置如下值：



| Field Name | Value | Description |
| :--- | :--- | :--- |
| Name | Set Address |我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。策略集名称 |
| Category | Book Example | 类别名称 |
| Description | Set Address | |

不要点击提交，点击`Policies Tab`。

| ![](img/image_rsrc8SB.jpg) |
| 图 2-45 显示了“Profile”标签页中的值 |

## Policies 标签页

此标签页包含两个部分：`Policy Set Member Rule` 和 `Identity Policies`。`Policy Set Member Rule` 说明配置策略适用于谁？在我们的示例中，我们使用默认值 = all，这意味着所有用户都符合此成员规则。

| ![](img/image_rsrc8SC.jpg) |
| 图 2-46 显示了成员规则等于所有用户 |

接下来，我们需要创建一个配置策略：当城市为“New York”时设置地址。点击`Add`按钮，放置值：

| Field Name | Value |
| :--- | :--- |
| Policy Name | New York Address |
| Policy Condition | |
| City | New York |
| Action on Apply Policy | |
| Country | United States |

| ![](img/image_rsrc8SH.jpg) |
| 图 2-47 显示了定义配置策略的界面 |

点击“OK”，将返回`Policies`界面。

| ![](img/image_rsrc8SJ.jpg) |
| 图 2-48 显示了 Policies 任务的完成 |

点击添加按钮添加其他城市。

| 策略名称 | 策略条件 | 应用策略时的操作选择“将<单值-用户属性>设置为<值>” |
| :--- | :--- | :--- |
| 多伦多地址 | City =Toronto | Country =Canada |
| 布埃诺斯艾利斯办公室 | City=Buenos Aires | Country =Argentina |
| 东京办公室 | City=Tokyo | Country =Japan |
| 伦敦办公室 | City=London | Country =United Kingdom |
| 圣保罗办公室 | City=Sao Paulo | Country =Brazil |
| 迪拜办公室 | City=Dubai | Country =UAE |
| 墨尔本办公室 | City=Melbourne | Country =Australia |

点击最后一个标签“所有者 (Owners)”。

## 所有者标签

此标签说明谁可以管理此`Identity Policy Set`。我们想要添加管理员角色“System Manager”来管理此策略。

| ![](img/image_rsrc8SK.jpg) |
| 图 2-49 显示了将“System Manager”添加为所有者的界面 |

当用户更改城市并提交管理员任务时，`Identity Policy Set` 将评估`Member Rule`和`Policy Set`。

| ![](img/image_rsrc8SM.jpg) |
| 图 2-50 显示了 Identity Policy Set 的工作原理。 |

`Identity Policy Set` 有一些局限性，因为其条件基于用户的属性或角色成员关系。接下来，我们将创建`Policy Xpress`来提供更多功能。

## 2.4.2 Policy Xpress

`Policy Xpress` 允许你在`CA IdentityMinder`中创建复杂的业务逻辑（策略），而无需开发自定义代码。`Policy Xpress` 比`Identity Policy Set`更灵活。它可以访问逻辑属性并捕获事件。在本节，我们将创建`Policy Xpress`来解决该需求：当用户输入扩展号时，我们将按照格式`<phone number>x<extension number>`更新电话号码。

选择标签“Policies”和子菜单“Create Policy Xpress Policy”。选择“Create a new object of type Policy Xpress”。

| ![](img/image_rsrc8SN.jpg) |
| 图 2-51 显示了 Create Policy Xpress Policy 菜单 |

### Profile 标签（配置页）

按照下表设置`Policy Xpress`的值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Policy Type | Submitted Task | 定义触发策略的监听器。当任务被提交时，我们的 Policy Xpress 将执行。 |
| Category | Book Example | 类别名称 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 CA IdentityMinder 中处于激活状态 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| 图 2.52 显示了配置页界面的值 |

点击标签“Events（事件）”。

### Events 标签（事件页）

`Policy Xpress` 可以捕获管理员任务的事件，包括 UI 操作和任务提交。此标签说明此`Policy Xpress`将在何时执行。我们希望在任务完成时执行此`Policy Xpress`，因此我们设置如下值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 Policy Xpress 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉菜单选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 Policy Xpress 的事件 |

### Data 标签（数据页）

此标签设计用于获取数据。在将其设置回之前，我们必须捕获某些值。我们计划创建如下条件：

`If city == “New York” then set Telephone number + “x” + extension number from screen`

因此我们需要获取数据：城市、电话号码和扩展号（逻辑属性）。点击“Add Data Element”添加数据。对于城市属性，按照下表选择值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型。 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 Get 函数。 |
| Attribute Name | City (l) | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| 图 2-54 显示了获取城市数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `|ExtNumber|` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| 图 2-55 显示了获取电话和扩展号数据的界面：`|ExtNumber|` |

完成此步骤后，点击 Entry Rule（入口规则）标签。

### Entry Rules 标签（入口规则）

Entry Rules 是主条件。它告诉我们要关注什么。我们的示例是城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| 图 2-56 显示了 Entry Rule |

### Action Rules 标签（动作规则）

在此标签，我们将创建条件：

`If city == “New York” then set Telephone number + “x” + extension number from screen`

我们在 Action Rule 中定义 IF，并在 Add 中定义 THEN。

| ![](img/image_rsrc8SV.jpg) |
| 图 2-57 显示了城市条件 |

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | Set New York Telephone | 动作名称 |
| Action Rule Conditions | | |
| City | New York | IF 的类型 |

点击“Add Match”按钮，填写如下所示的值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 动作名称 |
| Category | Attributes | 数据元素组 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Set | Set 函数 |
| Attribute Name | Business Phone (Telephone Number) | 我们的属性 |

为表中的其他城市添加条件：

| Action Rule Conditions | Set Business Phone (telephoneNumber) |
| :--- | :--- |
| City =Toronto | |
| Buenos Aires | |
| Tokyo | |
| London | |
| Sao Paulo | |
| Dubai | |
| Melbourne | |

| ![](img/image_rsrc8SW.jpg) |
| 图 2-58 显示了 Action Rules 的条件 |

点击提交按钮创建 Policy Xpress。我们将 Advanced（高级）标签保持为默认值。

## 2.5 工作原理

### 2.5.1 UI 如何工作

#### Form（表单）

我们有两个界面：搜索界面和表单界面。

#### Search Screen（搜索界面）

我们在创建管理员任务时定义搜索界面：

*   在 profile 标签页中，我们选择 User 为主对象，选择 Modify。
*   在 search 标签页中，我们选择默认搜索界面“Default User Search”。

| ![](img/image_rsrc8SX.jpg) |
| 图 2-59 显示了 Default User Search 界面 |

结果的数量取决于你的管理员角色的范围。你可以从“Roles and Tasks”标签进行检查，选择菜单“Modify Admin Role Members/Administrators”并选择“Members”标签。查看“此角色管理哪些用户对象？”这一项。

此表单来自“Tabs”选项卡中的 Admin Task（管理员任务）。我们在“Profile”选项卡上创建（因为只有一个选项卡，所以不显示标签名称），并添加了屏幕名称“Update Location and Ext Number”。

- 字段`City`：该字段填充用户的当前属性。
- 字段`Ext Number`：该字段是逻辑属性值。

修改`City`和`Ext`值并点击提交。

| ![](img/image_rsrc8SY.jpg) |
| 图 2-60 显示了表单 |

### 2.5.2 查看已提交的任务

查看已提交的任务（View Submitted Task）对于开发者理解 CA IdentityMinder 的行为非常重要。管理员任务提交后，你可以去“View Submitted Task”检查状态。选择“System”选项卡，选择菜单“View Submit Task”并点击`Search`。

| ![](img/image_rsrc8SZ.jpg) |
| 图 2-61 显示了查看已提交的任务界面 |

找到你提交的任务，它应该是最新的。点击图标`![](img/image_rsrc8T0.jpg)`查看内部详情。

| ![](img/image_rsrc8T1.jpg) |
| 图 2-62 显示了我们提交的任务。 |

提交的任务详情中有两个有趣的地方。

- `Task History` 告诉我们匹配了多少 Identity Policy Set（身份策略集）或 Policy Xpress。
- `Included Event` 告诉我们生成了多少事件。

| ![](img/image_rsrc8T2.jpg) |
| 图 2-63 显示了任务历史和包含事件 |

按顺序生成了 7 个事件：

1. **事件编号 1：修改用户 (Modify user)**

此事件`Modify user`的生成是因为我们修改了用户的属性：`city`。该事件是在我们提交任务后生成的（主对象为“User”，操作为“Modify”）。选择铅笔`pencil`图标查看更多详情。它将在提交任务后显示新值和旧值。

| ![](img/image_rsrc8T3.jpg) |
| 图 2-64 显示事件 1：修改用户的生成，是因为我们修改了 city 属性。 |

| ![](img/image_rsrc8T4.jpg) |
| 图 2-65 显示事件 1：修改用户完成后，city 属性已更改。 |

2. **事件编号 2：同步用户 (Synchronize user)**

此事件的生成是因为我们在管理员任务中选择了`User Synchronization: On task completion`（用户同步：任务完成时开启）。当此事件生成时，它将触发我们的策略集：`Set Office Address`。

| ![](img/image_rsrc8T5.jpg) |
| 图 2-66 显示事件 2 是由用户同步选项生成的。 |

3. **事件编号 3：修改用户 (Modify user)**

此事件由`Policy Xpress`生成。`Policy Xpress`设置了`Business Phone`的值。在此事件完成后，`User Store`中的电话号码属性值已更改。

| ![](img/image_rsrc8T6.jpg) |
| 图 2-67 显示事件 3 由 policy Xpress 生成以修改电话号码。 |

4. **事件编号 4：修改用户 (Modify user)**

此事件由`Identity Policy Set`生成。`Identity Policy Set`设置了属性`country`。在此事件完成后，`User Store`中的国家属性值已更改。

| ![](img/image_rsrc8T7.jpg) |
| 图 2-68 显示事件 4 由 Identity Policy Set 生成，修改了 country 属性。 |

5. **事件编号 5：同步配置角色并为用户添加账户。**

此事件的生成是因为用户拥有配置角色且选择了`User Synchronization`选项。此事件用于在`Endpoint`中创建账户。如果你在`Endpoint`中已经有了账户，此事件将不执行操作。你可以在`TASK SESSION`中查看账户创建详情：创建 0，更新 0，重创建 0，失败 0。

| ![](img/image_rsrc8T8.jpg) |
| 图 2-69 显示了事件 5 的详情。 |

6. **事件编号 6：同步用户 (Synchronize User)**

此事件在修改用户事件后由`Policy Xpress`生成。我们之所以知道这一点，是因为“Attribute Changed”（属性已更改）中的值来自`Policy Xpress`的值。

| ![](img/image_rsrc8T9.jpg) |
| 图 2.70 显示了事件 6 的详情。 |

7. **事件编号 7：与账户同步用户属性事件详情**

此事件的生成是因为我们在管理员任务屏幕上选择了`Account Synchronization: On Task Complete`（账户同步：任务完成时开启）选项。此事件将更新全局用户和账户的属性。

| ![](img/image_rsrc8TA.jpg) |



图我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。2-71 显示了事件 7 的详情。

在所有事件完成后，去 CA IdentityMinder 的 `User Store`、`Provisioning Directory` 和 `Endpoint`（Active Directory）检查用户属性。

![](img/image_rsrc8TB.jpg)

图 2-72 显示了用户、全局用户和账户的属性。

提交管理员任务时，你必须知道：

- 将生成多少个事件？
- 哪个组件生成的事件？
- 事件预期的结果是什么？

![](img/image_rsrc8TC.jpg)

图 2-73 显示了我们示例中的所有事件。

## 局限性

我们的管理员任务具有一些局限性：

- 无法在管理员任务中显示扩展号码的当前值。
- 无法直接验证扩展号码。

![](img/image_rsrc8TD.jpg)

图 2-74 显示了更新扩展号码时的消息。

## 2.6 总结

在本章中我们：

- 学习了如何创建管理员任务。
- 学习了配置的工作原理。
- 学习了 Policy Set 和 Policy Xpress 如何工作。
- 理解了提交的任务和事件。

# 第 3 章 编程概念与 IDE 配置

在本章中，我们将学习：

- 同步阶段与异步阶段的概念。
- IDE 配置。

## 3.1 API 概述

IdentityMinder 编程分为两类：

- Java 编程：执行逻辑和集成。
- 连接器编程：用于自定义连接器。

连接器部分请参考另一本书。我们首先关注 Java 编程。本章介绍了每个 API 的功能。

### 同步阶段与异步阶段

在开始任何 API 概念之前，你需要理解同步阶段与异步阶段。管理员任务的执行分为以下两个阶段：

- **同步阶段**：在任务提交期间对用户进行处理。任务尚未被拆解为事件。
- **异步阶段**：在用户显示响应后处理。任务已被拆解为事件。它可能需要几小时到一个月的时间。

![](img/image_rsrc8TE.jpg)

图 3-1 显示了同步与异步阶段。

### 3.1.1 业务逻辑任务处理器 API（BLTH）

业务逻辑任务处理器 `BLTH` API 可以在管理员任务级别执行逻辑。`BLTH` 在同步阶段运行，它可以在任务渲染前执行，也可以在任务提交后（创建事件之前）执行。

![](img/image_rsrc8TF.jpg)

图 3-2 显示了业务逻辑任务处理器 API 在任务之前和之后的工作。

此 API 非常有用，我们将频繁使用。我们可以从 `BLTH` 访问用户存储。

`BLTH` 示例：

- 管理员执行管理员任务；`BLTH` 可以初始化屏幕上的某些值。
- 管理员提交管理员任务；`BLTH` 验证屏幕上的字段。
- 管理员提交管理员任务；`BLTH` 执行逻辑或修改用户存储中的用户属性。

### 3.1.2 工作流 API

工作流 API 在真实世界需求中非常重要。工作流可以在管理员任务级别或事件级别工作。

在以下情况下需要工作流时：

- 你的需求需要审批。
- 业务逻辑需要很长的处理时间。我们可以使用工作流在事件级别实现业务逻辑。它将在异步阶段运行。
- 如果用户的办公室在纽约，则此任务需要 2 个审批者。如果用户的办公室在伦敦，则此任务需要额外一个审批者。
- 该需求要求在入职日期启用账户。

### 3.1.3 参与者解析 API（Participant Resolver API）

该 API 作为工作流的一部分。参与者解析 API 回答问题：谁是审批者。我们可以为查找审批者实现条件。

示例：

- 我们希望经理的经理作为审批者。

![](img/image_rsrc8TH.jpg)

图 3-4 显示工作流具有需要参与者解析 API 的审批者。

### 3.1.4 事件监听器 API（Event Listener API）

我们可以实现自定义监听器来监听事件。当事件发生时，事件监听器会在特定的执行状态下执行业务逻辑：之前、之后、失败、批准、拒绝。事件监听器在异步阶段运行。

示例：

- 用户创建成功后，向消息队列（MQ）发送消息。
- 如果管理员在任何修改用户事件上选择拒绝，监听器将写入日志文件。

![](img/image_rsrc8TJ.jpg)

图 3-5 显示事件监听器 API 可以监听事件。

### 3.1.5 逻辑属性 API（Logical Attribute API）

逻辑属性 API 显示属性的方式与其在用户目录中物理存储的方式不同。当你的属性在多个屏幕中共享，且你不想在每个屏幕上对值进行翻译逻辑处理时，应使用此 API。

示例：

- 你有一个物理属性 `BusinessCategory`，其值为代码形式：1001、2001 或 3001，但在屏幕上显示为广告、零售或电信。

![](img/image_rsrc8TK.jpg)

图 3-6 显示逻辑属性 API 在屏幕上将物理值转换为逻辑值。

### 3.1.6 验证规则（Validation Rules）

它用于在屏幕上验证字段的值。你可以在以下位置编写规则：

- 任务级：它将在特定屏幕上进行验证。
- 目录级：它将在任何屏幕上每次对该字段进行验证。

示例：

- 员工编号必须全为数字。

### 3.1.7 邮件模板（Email Template）

从 CA IdentityMinder 发送邮件有 2 种方式：

- 邮件通知策略。
- 邮件模板。

邮件模板 API 是其中之一。我们可以通过编写模板文件来实现。

### 3.1.8 通知规则（Notification Rule）

通知规则决定谁接收邮件。通知规则仅在邮件模板未使用。

示例：

- 在任务更新位置完成后向 HR 经理发送邮件。
  - 邮件模板用于生成邮件内容以及 Determine 何时该发送邮件。
  - 通知规则用于获取 HR 经理的电子邮箱地址。

### 3.1.9 任务执行 Web 服务（TEWS）

如果我们希望第三方系统执行我们的管理任务，必须启用 `TEWS` 功能。`TEWS` 将管理任务作为 Web 服务提供者启用。

示例：

- 用户使用 Web 门户修改地址。门户调用企业服务总线（ESB），然后 ESB 调用管理任务的 Web 服务来更新地址。

## 3.2 任务阶段

我们已经讨论过同步阶段和异步阶段的概述。本节将解释管理任务执行的阶段细节，以及每个 API 何时会被执行。

你现在不需要记住所有内容，当你练习书中的示例时，你会自然地记住它们。

### 3.2.1 同步阶段操作

1. 用户选择要执行的管理任务。
   - 业务逻辑任务处理程序 API：调用 `handleStart()` 方法。

2. 选择了管理任务主体，但尚未显示。
   - 业务逻辑任务处理程序 API：调用 `handleSetSubject()` 方法。
   - 字段的默认值可以使用 JavaScript 或硬编码初始化。
   - 与物理属性关联的字段将自动从数据存储中填充相应的数据。

3. CA IdentityMinder 显示并填充任务屏幕。
   - 逻辑属性：调用方法 `toLogical()` 来转换物理属性。

4. 当用户点击验证按钮（如果你有）或用户更改标签页或你有在更改时进行验证的逻辑时，CA IdentityMinder 在数据输入期间调用验证规则。

5. 用户提交任务屏幕。
   - 调用验证规则。
   - 逻辑属性 API：调用方法 `validate()` 执行字段级验证。
   - 逻辑属性 API：调用方法 `toPhysical()` 将逻辑属性转换回相应的物理属性。
   - 业务逻辑任务处理程序 API：调用方法 `handleValidation()` 执行任务级验证。

6. 用户提交任务屏幕。

   如果发生验证错误，错误将立即报告给用户。允许用户纠错误并重新提交任务。

7. CA IdentityMinder 为任务实例化事件。

   在成功完成所有验证后，CA IdentityMinder 会创建事件。每个事务由一个事件表示。

8. 任务进入异步阶段进行处理。

有 3 个主要的 API：业务逻辑任务处理程序、验证规则和逻辑属性在同步阶段执行。下面的图片显示提交管理任务后的屏幕。消息“任务待处理（Task pending）”意味着该任务后面有事件在处理，或者异步阶段从现在开始。

![](img/image_rsrc8TM.jpg)

图 3-7 显示显示任务待处理的屏幕。

### 3.2.2 异步阶段操作

1. CA IdentityMinder 发布事件。

2. 事件监听器执行审批前的更新。
   - 事件监听器 API：调用 `before()`。

3. 自定义对象在处理期间执行操作。
   - 参与者解析 API：如果工作流指定了工作流活动的参与者（审批者），调用方法 `resolve()`。
   - 工作流 API：`start`。如果启用了工作流，且事件映射到工作流过程，则工作流中的活动必须完成。

4. 事件监听器执行执行前的更新。
   - 工作流导致关联事件的批准或拒绝。
   - 当工作流被批准时，CA IdentityMinder 执行关联事件。
     - 事件监听器 API：调用 `approve()` 或 `reject()`。

5. CA IdentityMinder 执行事件。

6. 事件监听器执行后续操作。
   - 事件监听器 API：调用 `after()`。

7. CA IdentityMinder 生成邮件通知。
   - 调用邮件模板 API 和通知规则。

有 5 个 API：事件监听器、工作流、参与者解析、邮件模板和通知规则在异步阶段使用。

## 3.3 配置 IDE

我们使用 Eclipse 开发代码。请从书中下载。

### 类路径

请检查项目属性（Properties）> Java 构建路径（Build Path）。

如果你使用的是版本 12.6：

- 创建类路径变量：`IDM_LIB`
  - 选择窗口 > 首选项 > 类路径变量 > 新建。
  - 设置路径为 `/server\IdentityMinder.ear\library`。
    - 如果使用 WebLogic，所有的 `jar` 位于 `APP-INF\lib`。

![](img/image_rsrc8TN.jpg)

图 3-8 显示类路径变量。

如果你使用的是版本 12.5，移除所有我的 `jar`：

- 从部署文件夹 `/server\IdentityMinder.ear\library` 添加所有 `jar`。
  - 如果使用 WebLogic，所有的 `jar` 位于 `APP-INF\lib`。
- 从 `/server>IdentityMinder.ear\user_console.war\WEB-INF\lib` 添加 `identitymanager.jar`。

### 导入项目

- 运行 Eclipse 并选择导入 > 将现有项目导入工作区。
- 浏览归文件，选择项目并点击完成。

![](img/image_rsrc8TP.jpg)

图 3-9 显示导入项目。

- 任务执行 Web 服务允许管理员任务作为 Web 服务提供程序。

CA 通过书架 > CA IdentityMinder > 编程 > Javadoc 编程参考提供每个 API 的 Java 文档。下一章将详细介绍业务逻辑任务处理器 API。

# 第 4 章 业务逻辑任务处理器

业务逻辑任务 Handler API（或 `BLTH`）用于在管理员任务层级执行业务逻辑的 API。业务逻辑任务处理器具有以下独特特性：

- 业务逻辑任务 Handler API 在管理员任务会话级别工作。
- 业务逻辑任务 Handler API 在同步阶段执行。
  - 这意味着用户必须等待逻辑执行完成。
- 业务逻辑任务 Handler API 必须在任何事件创建之前完成。
- 业务逻辑任务 Handler API 适用于：
  - 验证和格式化任务屏幕字段。
  - 强制执行需要立即响应（同步）的自定义业务逻辑。

## 4.1 编程与配置概念

业务逻辑任务 Handler API 可以通过 Java 或服务器端 JavaScript 实现。本书仅使用 Java 语言。对于服务器端 JavaScript，可以查阅详细的官方文档。我们将使用 `java` 作为所有 API 的统一语言，并且还可以从 Java 工具库中受益。

### 4.1.1 编程

实现业务逻辑任务 Handler API，我们只需创建一个 `java` 类并扩展 `BLTHAdapter` 类并重写方法。每个方法都是回调方法，将在管理员任务的生命周期内执行。你可以根据需求实现部分或所有方法：

- `handleStart()`：在任务开始时执行。
- `handleSetSubject()`：在从搜索结果中选择主体（例如选择用户）后执行。它用于设置屏幕上的初始值。
- `handleValidation()`：在用户提交任务后执行。用于验证逻辑。
- `handleSubmission()`：在 `handleValidation()` 之后执行。用于执行逻辑处理。

#### 开发步骤

1. 编写扩展 `BLTHAdapter` 的 `java` 代码。
2. 编译并确保没有错误，且使用的 `JDK` 版本与服务器版本一致。
3. 将类文件（包括包文件夹）复制到文件夹 `\IdentityMinder.ear\custom` 中。

### 4.1.2 配置

业务逻辑任务处理器可以通过两种范围进行配置：

- **全局业务逻辑任务处理器**：此级别意味着它将应用于所有管理员任务。当调用任何管理员任务时，我们的 `java` 代码都会执行。
- **特定任务的业务逻辑任务处理器**：此 `java` 代码将在配置的特定管理员任务中执行。此范围在本书中使用频率最高。

#### 全局业务逻辑任务处理器

它们在管理台中配置，选择 Home > Environments > `<your server>` > Advanced Settings > Business Logic Task Handlers。

![](img/image_rsrc8TR.jpg)

图 4-1 显示了全局业务逻辑任务处理器的屏幕。

你可以点击 `New` 按钮配置业务逻辑任务处理器。配置屏幕上的每个字段与特定任务业务逻辑任务处理器相同。

#### 特定任务的业务逻辑任务处理器

此级别适用于特定的管理员任务。步骤如下：

1. 以管理员身份登录 Identity Manager 用户控制。
2. 搜索管理员任务名称。
3. 点击 `Business Logic Task Handlers` 按钮，然后点击 `Add` 按钮指定特定的 `java` 类名。

![](img/image_rsrc8TS.jpg)

图 4-2 显示了任务特定性的 `Business Logic Task Handlers` 按钮。

## 4.2 任务会话

任务会话是执行任务的实例。在任务执行期间，业务逻辑任务处理器可以访问当前任务会话中的信息。任务会话信息可以通过 `BLTHContext` 获取。接口提供了检索当前任务会话中托管对象运行时实例的方法，例如：

- 方法 `getUser()`：获取参与当前任务的 `User` 对象。
  - 请注意，如果管理员任务的主对象是 `User`（例如修改用户），则 `getUser()` 将有效。如果你的管理员任务是修改端点，则调用 `getUser()` 没有意义。
- 获取任何关系对象（如角色和组组）。

`BLTHContext` 继承自许多父接口：

- `TaskInfo`：关于当前任务的信息，例如：`getSubject()` 返回主对象。
- `IMContext`：提供关于会话的方法，用于在 API 之间共享会话。该接口还提供了 `getAuxDataRoot()` 方法访问辅助数据树的根节点。
- `ProviderAccessor`：提供直接访问数据存储中任何托管对象的权限。我们将在下一节中讨论托管对象。

## 4.3 访问托管对象

托管对象是指数据存储中的对象，如用户或帐户。业务逻辑任务处理器可以通过以下 2 方式访问托管对象：

### 通过 ProviderAccessor

`Provider Access` 是 `BLTHContext` 的父类：

- 可以访问任何托管对象。
- 可以访问托管对象的任何属性。
- 当调用 `modifyObject()` 时，对托管对象进行的任何更改都会立即持久化到数据存储中。
  - 不会生成事件，也不会执行工作流审批、审计或安全检查。

### 通过 Context

本章中的 `Context` 指 `BLTHContext`，其他章节指 `WorkflowContext`、`EventContext` 等。

- 限制访问任务会话，包括任务的主体（主对象）和主体的关系。
  - 例如管理员任务：修改用户。上下文可以访问 `User` 对象。
- 限制访问属性。
  - 例如如果管理员任务只定义了城市属性，则无法访问国家属性。
- 更改在事件完成后将提交。
  - 例如你使用 `BLTHContext` 修改城市，但用户事件（内部事件）会被拒绝。城市属性将不会提交。

CA IdentityMinder 为任务生成事件，并可以执行工作流审批、审计和安全检查。

![](img/image_rsrc8TT.jpg)

图 4-3 显示了访问托管对象的 2 种方式。

下表比较了 `BLTHContext` 和 `ProviderAccessor` 的区别：

| 主题 | ProviderAccessor | BLTHContext |
| --- | --- | --- |
| 访问对象 | 可以访问任何托管对象 | 仅访问任务会话相关的对象 |
| 访问属性 | 可以访问任何属性 | 限制访问，取决于你如何定义管理员任务 |



| 修改值 | 调用 `modifyObject()` 时，修改的值立即提交到数据存储中 | 在事件完成之前，值不会提交 |
| --- | --- | --- |
|我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。事件 | 不生成额外的事件 | 与任务相关的事件 |

我们将在下一节和后续章节中通过示例涵盖更多托管对象的细节。

## 4.4 代码示例

在 CA IdentityMinder 编程部分，我们使用名为 `IdmCode` 的 `java` 项目。我们重用上一节的管理员任务。我们将仅使用业务逻辑任务 Handler API 执行管理员任务，因此需要禁用上一节的 Identity Policy Set 和 Policy Xpress。

![](img/image_rsrc8TU.jpg)

图 4-4 显示通过取消勾选启用框来禁用 Identity Policy Set 和 Policy Xpress。

### 4.4.1 基础编程：`BLTHAdapter` 和生命周期

此示例逐步演示业务逻辑任务处理器的基础编程。CA IdentityMinder 编程始终分为两个部分：编码和配置。此示例仅演示业务逻辑任务 Handler API 的生命周期。我们将打印到日志文件中。

#### 代码

1. 运行 Eclipse 并选择 `java` 类：

   - 包：`com.book.idm.blth`
   - 类：`BasicLifeCycle`
   - 扩展 `BLTHAdapter`

以下列表显示了我们的代码：

```java
package com.book.idm.blth;

import com.netegrity.imapi.BLTHAdapter;
import com.netegrity.imapi.BLTHContext;

public class BasicLifeCycle extends BLTHAdapter {
    @Override
    public void handleStart(BLTHContext blthContext) throws Exception {
        System.out.println("UpdateLocationExtNumber:handleStart");
    }

    @Override
    public void handleSetSubject(BLTHContext blthContext) throws Exception {
        System.out.println("UpdateLocationExtNumber:handleSetSubject");
    }

    @Override
    public void handleValidation(BLTHContext blthContext) throws Exception {
        System.out.println("UpdateLocationExtNumber:handleValidation");
    }

    @Override
    public void handleSubmission(BLTHContext blthContext) throws Exception {
        System.out.println("UpdateLocationExtNumber:handleSubmission");
    }
}
```

2. 编译并复制类（包括包文件夹 `com.book.idm.blth`）到文件夹 `\IdentityMinder.ear\custom`。

#### 配置

有两种类型的配置：全局业务逻辑任务处理器和特定任务的业务逻辑任务处理器。我们在所有示例中都选择了特定任务的业务逻辑任务处理器。

1. 搜索管理任务名称：`Update Location and Ext Number`。

2. 点击 `Business Logic Task Handlers` 按钮，然后点击 `Add` 按钮指定 Java 类名。

3. 如下所示填写值：

| 字段名称 | 值 | 描述 |
| --- | --- | --- |
| Name | `BLTHExample` | 业务逻辑任务处理器的名称 |
| Java Class | `com.book.idm.blth.BasicLifeCycle` | 我们放在 `custom` 文件夹中的 Java 类名 |

![](img/image_rsrc8TV.jpg)

图 4-5 显示了业务逻辑任务处理器的详情界面。

4. 点击 `ok` 并提交此管理任务。

#### 工作原理

我们可以通过以下步骤通过管理任务执行我们的代码：

1. 以管理员身份登录 Identity Manager 用户控制台。

2. 选择标签页 `Book Example`，并选择菜单 `Basic`。

3. 选择管理任务：`Update Location and Ext Number`。

![](img/image_rsrc8TW.jpg)

图 4-6 显示了选择管理任务。

日志文件显示：

`| INFO [STDOUT] UpdateLocationExtNumber:handleStart`

4. 然后搜索并选择一些用户。当管理任务显示时，日志文件将显示：

`| INFO [STDOUT] UpdateLocationExtNumber:handleSetSubject`

![](img/image_rsrc8TX.jpg)

图 4-7 显示了管理任务的显示界面。

5. 修改城市属性（你必须修改城市值）并提交管理任务，日志将显示：

`| INFO [STDOUT] UpdateLocationExtNumber:handleValidation INFO [STDOUT] UpdateLocationExtNumber:handleSubmission`

你将看到业务逻辑任务处理器的生命周期，以及 `BLTHAdapter` 的每个方法何时执行。

### 4.4.2 通过 `BLTHContext` 修改用户属性

此示例将演示如何使用 `BLTHContext`：

- 将城市属性修改为“New City”。
- 从父接口获取有关当前任务的信息：`TaskInfo`。

#### 代码

1. 编译 Java 代码：`com.book.idm.blth.ModifyUserByBLTHContext`。

2. 复制类（包括包文件夹 `com.book.idm.blth`）到文件夹 `\IdentityMinder.ear\custom`。

#### 配置

1. 以管理员身份登录 Identity Manager 用户控制台。

2. 选择标签页 `Roles and Tasks`，并选择菜单 `modify admin task`。

3. 搜索并选择管理任务名称：`Update Location and Ext Number`。

4. 点击 `Business Logic Task Handlers` 按钮，然后点击图标 `pencil`。

![](img/image_rsrc8TY.jpg)

图 4-8 显示了修改 Java 类的“pencil”图标。

5. 如下所示修改值：

| 字段名称 | 值 | 描述 |
| --- | --- | --- |
| Java Class | `com.book.idm.blth.ModifyUserByBLTHContext` | 我们放在 `custom` 文件夹中的 Java 类 |

![](img/image_rsrc8TZ.jpg)

图 4-9 设置了新 Java 类的值。

#### 工作原理

我们可以通过以下步骤通过管理任务执行我们的代码：

1. 以管理员身份登录 Identity Manager 用户控制台。

2. 选择标签 `Book Example`，并选择菜单 `Basic`。

3. 选择管理任务：`Update Location and Ext Number`。

4. 然后搜索并选择一些用户。

5. 修改城市属性（你必须修改城市值）并提交管理任务。

#### 访问用户对象

城市属性的结果将是“New City”。无论你在屏幕上选择什么值都不重要，因为我们的代码设置了该值。我们在 `handleSubmission()` 方法中设置了城市属性。

```java
//Access User Object
User user = blthContext.getUser();
user.setAttribute("l", "New City");
```

在代码中，我们通过 `BLTHContext.getUser()` 访问用户对象并设置属性：`city`。有趣的一点是属性名称。用户对象使用用户存储中表示的属性名称。小写的 `L` 表示城市。你可以使用任何 LDAP 客户端连接用户存储并查看用户属性。

![](img/image_rsrc8U0.jpg)

图 4-10 显示了属性。

#### 获取当前任务信息

从父接口获取有关当前任务的信息：`TaskInfo`。

```java
//Get information about the current task from parent interface: TaskInfo
```

在代码中，我们通过 `BLTHContext.getUser()` 访问用户对象并设置属性：`city`。有趣的一点是属性名称。用户对象使用用户存储中表示的属性名称。小写的 `L` 表示城市。你可以使用任何 LDAP 客户端连接用户存储并查看用户属性。

3. 选择管理员任务：“更新位置和分机（Update Location and Ext Number）”。

4. 搜索并选择某些用户。

5. 修改城市属性（必须修改城市值），并在电话分机号中输入值“xxxxxx”。提交管理员任务。

![](img/image_rsrc8U6.jpg)

图 4-16 显示了我们任务的值。

## 使用 `ProviderAccessor`

使用 `providerAccessor` 意味着 `ProviderAccessor` 的任何方法都是 `BLTHContext` 的父类。例如：`getUserProvider()`、`getGroupProvider()` 等。方法名将以单词 `provider` 结尾。每个托管对象类型（如 `User`、`Group` 和 `Organization`）都与一个程序对象关联，您使用它来访问托管对象的数据。

```java
User user = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
```

`BLTHContext` 有父接口：`ProviderAccessor`。当我们调用 `getUserProvider()` 时，它返回 `UserProvider`。`UserProvider` 拥有方法 `findUser()`。



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。findUser(TSContext context, java.lang.String name, AttributeRightsCollection attributes)
```

此方法需要 3 个参数：

- `context`：当前任务会话的上下文。我们的代码使用了 `BLTHContext`。
- `name`：要检索的用户名。该名称可以是唯一名称，也可以是友好名称。我们的代码使用了用户的唯一名称。

```java
// 从 taskString 获取唯一名称
userid = blthContext.getUser().getUniqueName();
```

- `attributes`：`AttributeRight` 对象的集合，每个对象包含一个属性名称和权限请求。我们的代码传递了空值。

我们从 `ProviderAccessor` 获取用户对象。我们可以修改电话号码属性。该属性名称与用户存储中物理属性的名称相同。

```java
user.setAttribute("telephoneNumber", "212-222-2222x1234");
user.modifyObject();
```

我们通过 `ProviderAccessor` 修改托管对象时，更改的是对象的本地（内存中）表示。要将更改持久化到数据存储中，我们需要调用 `modifyObject()`。更改将直接应用于数据存储。此时不会生成 Identity Manager 事件，也不会执行工作流审批、审计或安全检查。

## 在用户存储中检查结果

我们做了两件事：更改城市属性以及我们的 Java 代码使用 `AccessProvider` 修改了电话号码。使用 LDAP 客户端连接用户存储，我们将看到电话号码值已经更改。

![](img/image_rsrc8U7.jpg)

图 4-17 显示电话号码属性已更改

## 在已提交任务屏幕中检查结果

选择菜单：查看提交的任务（view submitted task），在标签页下：系统（system）。选择我们的任务，你将看到内部的事件。

![](img/image_rsrc8U8.jpg)

图 4-18 显示所有事件

点击 `Modify User` 事件查看属性更改：

- 城市属性来自屏幕，用于修改用户存储中的值。
- 电话号码，我们使用 `ProviderAccessor` 修改的。因此，`Modify User` 事件中的属性发生了变化，我们看不到来自 `ProviderAccessor` 的值，而只能看到来自屏幕的值。

![](img/image_rsrc8U9.jpg)

图 4-19 显示提交后属性的更改

## 修改的顺序

现在有两个属性需要配置（provisioning）：城市和电话号码：

- 城市值来自屏幕。
- 电话号码值来自 `ProviderAccessor`。
  - 在屏幕上，我们输入了值“xxxxxx”。
  - 最终结果是“212-222-2222x1234”。

如果你的环境配置了配置和 Active Directory（AD）账户，你将看到端点中的电话属性为“212-222-2222x1234”。

![](img/image_rsrc8UA.jpg)

图 4-20 电话号码已配置到端点

我们可以逐步解释为如下：

- 步骤 1：当用户提交管理员任务时，执行 `handleSubmission()` 方法。当调用 `modifyObject()` 方法时，电话号码将完成提交。
- 步骤 2：已生成 `modify user` 事件。当 `modify user` 事件完成时，CA IdentityMinder 将提交城市值。
- 步骤 3：`Synchronize User` 事件，与此无关。它将触发 `Policy Set`。
- 步骤 4：`Synchronize User Attribute with Account` 将从配置目录并将属性配置到端点。

![](img/image_rsrc8UB.jpg)

图 4-21 显示配置的步骤

### 4.4.4 BLTHContext 和 ProviderAccessor

这个例子是一个为了更好地理解 `BLTHContext` 和 `ProviderAccessor` 的实验。我们将尝试同时使用这两个 API 更新城市和电话属性。让我们看看发生了什么。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.blth.ModifyUserByBoth`
2. 将类（包括包文件夹 `com.book.idm.blth`）复制到文件夹 `\IdentityMinder.ear\custom`。

#### 配置

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签 `Roles and Tasks`（角色与任务），选择菜单 `modify admin task`（修改管理员任务）。
3. 搜索并选择我们的管理员任务名称：`Update Location and Ext Number`。
4. 点击按钮 `Business Logic Task Handlers`（业务逻辑任务处理器），然后点击图标 `pencil`（铅笔）。
5. 按如下所示修改值。

| 字段名称 | 值 | 说明 |
| :--- | :--- | :--- |
| Java Class | `com.book.idm.blth.ModifyUserByBoth` | 我们放在 custom 文件夹中的 Java 类 |

我们可以通过以下步骤通过管理员任务执行我们的代码：

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页：`Book Example` 并选择菜单：`Basic`。
3. 选择管理员任务：“Update Location and Ext Number”。
4. 然后搜索并选择某些用户。

## 使用 BLTHContext 修改属性

让我们看看代码在 `handleSubmission()` 方法中的第一个版本。我们注释了所有关于 `ProviderAccessor` 的内容。

```java
//Using BLTHConext
User user1 = blthContext.getUser();
user1.setAttribute("l", "New City");
user1.setAttribute("telephoneNumber", "111111");
//Using ProviderAccessor
```

```java
//Using BLTHConext
User user1 = blthContext.getUser();
user1.setAttribute("l", "New City");
user1.setAttribute("telephoneNumber", "111111");
//Using ProviderAccessor
/*
String userid = user1.getUniqueName();
User user2 = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
user2.setAttribute("l", "New Town");
user2.setAttribute("telephoneNumber", "2222222");
user2.modifyObject();
*/
```

执行管理员任务：`Update Location and Ext Number`。我们将得到电话属性错误。

![](img/image_rsrc8UC.jpg)

图 4-22 显示了错误

我们得到了关于 `telephoneNumber` 的错误。当你使用 `BLTHContext` 修改属性时，你必须关注管理员任务中定义的字段。

![](img/image_rsrc8UD.jpg)

图 4-23 显示管理员任务中定义的所有属性

`BLTHContext` 可以修改管理员任务中定义的任何属性。如果你尝试修改范围之外的任何属性（例如：电话号码），将得到异常。

## 使用 ProviderAccessor 修改属性

在我们代码的下一个版本中，我们注释了问题的行（修改电话号码）并取消了 `ProviderAccessor` 部分。编译并部署到服务器。

```java
public void handleSubmission(BLTHContext blthContext) throws Exception {
    Using BLTHConext
    User user1 = blthContext.getUser();
    user1.setAttribute("l", "New City");
    //user1.setAttribute("telephoneNumber", "111111");
    //Using ProviderAccessor
    String userid = user1.getUniqueName();
    User user2 = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
    user2.setAttribute("l", "New Town");
    user2.setAttribute("telephoneNumber", "2222222");
    user2.modifyObject();
}
```

再次执行管理员任务并查看结果。在屏幕上，我们选择了城市值：Toronto。

![](img/image_rsrc8UE.jpg)

图 4-24 我们更改城市值为 Toronto

现在我们有三个地方设置了城市属性：

1. 屏幕上设置为“Toronto”。
2. `BLTHContext` 修改城市值为“New City”。
3. `ProviderAccessor` 修改城市值为“New Town”。

哪一个是获胜者？最终结果是：

- 城市是“New City”。
- 电话号码是“2222222”。

![](img/image_rsrc8UF.jpg)

图 4-25 显示了最终结果

我们可以逐步看到：

- 步骤 1：用户输入城市属性值为“Toronto”。
- 步骤 2：`BLTHContext` 覆盖城市属性值为“New City”但未提交。
- 步骤 3：`ProviderAccessor` 将城市属性值提交为“New Town”（新镇）。现在城市属性已更改为“New Town”。
- 步骤 4：当修改 `User` 事件完成时，`CA IdentityMinder` 从由 `BLTHContext` 修改过的任务中提交城市属性值。

步骤 1–3 发生在同步阶段。步骤 2 和 3 由业务逻辑任务处理器执行。步骤 4 属于异步阶段。

![](img/image_rsrc8UG.jpg)

图 4-26 显示了修改的执行序列

### 4.4.5 业务逻辑任务处理器和屏幕

在本示例中，我们将编写程序从管理员任务（admin task）的屏幕中获取数据。此用示展示了：

- 如何获取当前分机号码并显示在屏幕上。
- 验证用户输入。分机号码必须存在且仅为数字。
- 展示如何向用户回传错误消息。
- 使用会话属性（session attribute）在方法之间共享分机号码。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.blth.ModifyUserAndScreen`
2. 将类（包含包文件夹 `com.book.idm.blth`）拷贝到文件夹 `\IdentityMinder.ear\custom`。

#### 配置

1. 以管理员身份登录 `Identity Manager User Console`。
2. 选择标签页 `Roles` 和 `Tasks`，并选择菜单 `modify admin task`。
3. 搜索并选择我们的管理员任务名称：`Update Location and Ext Number`（更新位置和分机号）。
4. 点击 `Business Logic Task Handlers` 按钮，然后点击图标 `pencil`。
5. 按照如下所示修改值。

| 字段名称 | 值 |  |
| :--- | :--- | :--- |
| Java Class | `com.book.idm.blth.ModifyUserAndScreen` | 我们放在 custom 文件夹中的 Java 类 |

#### 工作原理

我们可以通过以下步骤通过管理员任务执行我们的代码：

1. 以管理员身份登录 `Identity Manager User Console`。
2. 选择标签页：`Book Example` 并选择菜单：`Basic`。
3. 选择管理员任务：`Update Location and Ext Number`。
4. 然后搜索并选择一些用户。

#### `handleSetSubject()`：在屏幕上显示当前电话号码

`handleSetSubject()` 方法在屏幕初始化显示时调用。因此我们在此方法内部实现设置显示分机号。

![](img/image_rsrc8UH.jpg)

图 4-27 分机号的当前值已显示在屏幕上

设置分机号码，我们需要做两件事：

- 获取当前电话号码。
- 设置屏幕逻辑属性的值：`|ExtNumber|`。

获取当前电话号码并不新奇，我们使用 `ProviderAccessor` 获取该值。

```java
String userid = blthContext.getUser().getUniqueName();
User user = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
String telephoneNumber = (String) user.getAttribute("telephoneNumber");
```

请想象管理员任务的屏幕。当我们定义管理员任务时：

- 在管理员任务内部，有标签页（tabs）。
- 我们的管理员任务有一个配置标签页（profile tab）。
- 在标签页内部，有一个屏幕（screen）。
- 在屏幕内部，有字段（fields）。

![](img/image_rsrc8UJ.jpg)

图 4-28 显示了管理员任务配置中的标签页屏幕

在管理员任务内部，我们有标签页。我们调用方法 `getTaskTabHandlers()` 返回此管理员任务的所有标签页。

```java
Vector<TabHandler> tabs = blthContext.getTaskTabHandlers();
for (TabHandler tab : tabs) {
```

我们的管理员任务有一个配置标签页，所以我们需要检查 `ProfileTabHandler` 的类型。如果你有多个配置标签页，你需要条件来检查屏幕的标签名（tag name）。我们检查屏幕标签名 `BookBasicUpdateLocationAndExtNo`。（在我们的示例中只有一个标签页，你可以跳过此条件）

```java
// 检查标签类型
if (tab instanceof ProfileTabHandler) {
    ProfileTabHandler profileTab = (ProfileTabHandler) tab;
    String screenName = profileTab.getScreenHandler().getScreen().getTag();
    if (screenName.equals("BookBasicUpdateLocationAndExtNo")) {
```

我们可以通过使用 `updateRawData()` 方法设置屏幕上的值。

```java
HashMap<String, String> data = new HashMap<String, String>();
data.put("|ExtNumber|", telephoneNumber.substring(telephoneNumber.indexOf("x") + 1));
...
profileTab.updateRawData(data);
```

在屏幕内部，我们有字段。我们创建一个新的 `HashMap` 对象。我们放入键值对，键的名称 `|ExtNumber|` 来自于管理员任务中的屏幕定义。如果你想设置城市属性，可以使用与用户存储（user store）相同的属性名。城市属性使用“l”作为键。

#### `handleValidation()`：验证用户输入

在用户提交管理员任务后，如果分机号码为空或输入了某些字符，将显示错误。

![](img/image_rsrc8UK.jpg)

图 4-29 显示了错误消息

我们必须重写 `handleValidation()` 方法。我们可以通过 `getRawData()` 方法从屏幕获取任何字段。如果你不确定字段名称，可以通过该方法打印。

CA IdentityMinder 自带了一个预定义的业务逻辑任务处理器，它会在创建对象之前检查对象可能存在的重复。例如，新创建的角色（role）的名称必须是唯一的。当角色即将被创建时，预定义的业务逻辑任务处理器会验证新角色的名称是否已经存在。如果名称已存在，该处理器将抛出一个异常，指示角色名称必须唯一，管理员借此更改名称并重新提交任务。

我们可以通过 `ProviderAccessor` 搜索角色名称。



```java
boolean isUnique = false;
try {
    //Search by friendlyName
    AccessRole role = blthContext.getAccessRoleProvider().findAccessRole(roleName);
} catch (NoSuchObjectException e) {
    isUnique = true;
}
if (!isUnique) {
    IMSException imsEx = new IMSException();
    imsEx.addUserMessage("The role name must be unique");
    throw imsEx;
}
```

### 在达到最大登录次数后禁用用户账户

当用户连续登录失败三次后，该账户在数据存储中会被立即禁用。由于账户是直接在数据存储中更新的，而不是在任务会话中，因此 CA IdentityMinder 不会为此操作生成事件，且可能与此操作相关的任何工作流审批、审计和安全检查都会被跳过。在最后登录尝试后，会通过自定义消息提示用户账户已禁用。

用例说明用户账户直接在数据存储中更新（禁用）。此用例意味着使用`ProviderAccessor`直接更新用户属性。（如需直接更新账户属性，请参阅第二卷）

### 在自注册期间将用户分配到组

一个以“福利管理员”（Benefits Administrator）职衔进行自注册的用户将被分配到 HR 组。此更新是在任务会话中完成，通过调用`RelationshipTabHandler`中的`assignResources()`实现。此更新会触发`AddToGroupEvent`事件，使得组分配可以受审计和工作流审批。

我们使用业务逻辑任务处理器按如下代码修改标签页中的值值。

```java
For (TabHandler tab : tabs) {
    RelationshipTabHandler rTab = (RelationshipTabHandler) tab;
    rTab.assignResources(groups);
}
```

### 为新用户分配“经理”（manager）属性

管理员希望在屏幕上显示配置之前设置“经理”值。可以编写一个业务逻辑任务处理器，实现`handleSetSubject()`方法进行初始化。该方法会将管理员的名称分配给经理名称属性。如果管理员名称不可用，则抛出异常。

我们在`handleSetSubject`方法中编写代码来初始化经理属性。

```java
public void handleSetSubject(BLTHContext blthContext) throws Exception {
    String managerId = blthContext.getAdminFriendlyName();
    if (managerId == null) {
        throw new IMSException("administrator’s name is not available");
    }
    HashMap<String, String> screenFields = new HashMap<String, String>();
    screenFields.put("managerId", managerId);
    tab.updateRawData(screenFields);
}
```

## 4.6 结论

在本章中，我们学习了业务逻辑任务处理器 API 概念的基本编程。我们可以总结如下笔记：

### 实现业务逻辑任务处理器

- 包含两个步骤：编码和配置。
- 对于编码，你必须编写一个扩展`BLTHAdapter`的 Java 类并根据需要重写方法。
  - `handleStart()`：当用户选择管理员任务时调用。
  - `handleSetSubject()`：用于在显示前设置字段。
  - `handleValidation()`：用于验证。
  - `handleSubmission()`：当用户提交并在验证后执行。
  - 编译并复制到文件夹`\IdentityMinder.ear\custom`。
- BLTH 配置有两个级别：全局配置和特定任务配置。

### 访问托管对象

- 有两种方式：通过`ProviderAccessor`和`BLTHConext`（任务会话）。
- 对于 BLTH，我们必须考虑：
  - 什么是主对象？
  - 修改的属性是否在管理员任务中定义？

### 编程笔记

- 代码中的用户属性名称是用户存储器中的物理名称。
- 你可以使用`getRawData()`和`setRawData()`访问屏幕上的值。
- 可以通过`IMSException`对象在屏幕上显示消息。
- 可以使用 session 保持值并在方法之间共享。

业务逻辑任务处理器 API 在同步阶段执行业务逻辑。在异步阶段，我们使用工作流来执行业务逻辑。下一章是工作流。

# 第 5 章 工作流

CA IdentityMinder 官方文档关于工作流的细节并不多。我们从前面的章中学习了一些基本概念：

- 如果需求需要审批者，则你需要工作流。
- 工作流在异步阶段运行。
- 工作流可以有很长的寿命。可能花费一小时或一个月的时间。
- 业务逻辑任务处理器在工作流开始之前完成。

在本章中，你将学习工作流 API 以及如何创建自定义工作流。

## 5.1 工作流概念

你必须在管理控制（Management Console）中启用工作流。默认情况下，工作流是禁用的。

### 配置：管理控制

1. 在管理控制台中，选择一个环境（Environment）。
2. 进入高级设置（Advanced Settings），工作流（Workflow）。
3. 勾选`Enabled`复选框并点击保存（Save）。
4. 重启应用程序服务器。

![](img/image_rsrc8UM.jpg)

图 5-1 显示了管理控制中的工作流属性。

在事件映射表中，事件与全局工作流之间有一些映射。

### 5.1.1 默认工作流功能

在本节中，我们将学习 CA IdentityMinder 中的默认工作流功能。我们涵盖以下主题：

- 工作流级别（Workflow Level）：工作流可以运行管理员任务或事件。
- 选择工作流（Select Workflows）：哪些工作流可以执行。
- 策略基础（Policy Base）：启动工作流的条件。
- 审批者的任务和屏幕。
- 审批者（Approver）：谁是审批者。
- 结果（Expected Outcome）：最终结果：批准或拒绝。

#### 工作流级别

工作流可以在管理员任务和/或事件级别运行。应该选择哪个级别？取决于需求。例如，我们有一个管理员任务“修改用户”，我们的管理员任务有两个标签页：配置标签页（Profile Tab）和访问角色（Access Role）。因此，事件将从此管理员任务生成并分为两组：

- 第一组事件来自配置标签页；当用户属性被修改时会生成事件。
- 第二组事件来自访问角色标签页；当我们添加或删除访问角色时会生成事件。

![](img/image_rsrc8UN.jpg)

图 5-2 显示了示例管理员任务的所有事件。

我们有两个请求：从配置标签页修改用户属性的请求，以及另一个从访问标签页添加/删除角色的请求。

- 场景 1：所有请求（修改用户属性和添加/删除角色）都需要一个工作流进行审批，我们应该指定工作流为管理员任务级别。
- 场景 2：仅修改用户属性请求（配置标签页）需要审批者，我们应该指定工作流为事件级别：`ModifyUserEvent`。
- 场景 3：仅添加角色请求（访问标签页）需要审批者，我们应该指定工作流为事件级别：`AssignAccessRoleEvent`。
- 场景 4：任何请求（修改用户属性和添加/删除角色）都需要经理作为第一个审批者。
  - 修改用户属性请求需要 HR 经理作为第二个审批者。
  - 添加角色请求需要 IT 经理作为第二个审批者。

我们将第一个审批工作流指定管理员任务级别，并将 HR 和 IT 工作流指定事件级别：`ModifyUserEvent`和`AssignAccessRoleEvent`。此情况如下所示。

![](img/image_rsrc8UP.jpg)

图 5-3 显示了场景 4 的工作流。

#### 管理员任务级别

管理任务（admin task）工作流需要设置属性`TASK_LEVEL=true`。你将在示例代码中看到它。要在管理任务级别启用工作流，你需要进行配置：

- 在`Profile`标签页上，勾选`Enable Workflow`（启用工作流）复选框。
- 在`Profile`标签页上，点击流程标签旁的铅笔图标。将显示工作流配置界面。

| ![](img/image_rsrc8UR.jpg) |
| 图 5-4 显示了如何在管理任务级别配置工作流 |

#### 事件级别（Event Level）

要在事件级别启用工作流，你需要进行配置：

- 在`Profile`标签页上，确认已勾选`Enable Workflow`。
- 在`Events`标签页上，点击事件上的铅笔图标。将显示工作流映射界面，并选择一个流程模板。

| ![](img/image_rsrc8US.jpg) |
| 图 5-5 显示了如何在事件级别配置工作流 |

## 选择工作流（Select Workflows）

你可以从下拉菜单中选择工作流。CA IdentityMinder 提供了三个默认流程模板：

- `SingleStepApprovalProcess`：适用于一个主审批人，当未找到主审批人时使用默认参与者。
- `TwoStageApprovalProcess`：适用于两个主审批人，当未找到主审批人时使用默认参与者。
- `EscalationApprovalProcess`：适用于一个主审批人，当未找到主审批人时使用默认参与者。该工作流的主审批人可以升级给另一个审批人。

你可以创建更多自定义工作流，稍后我们会详细介绍。

## 策略基础（Policy Base）

基于策略的是启动工作流前的条件。下面的图片显示了策略基础：如果用户城市是纽约，则需要工作流：`TwoStageApprovalProcess`。

| ![](img/image_rsrc8UT.jpg) |
| 图 5-6 显示了工作流策略基础的界面 |

如果请求不符合任何条件，事件或管理任务将在不通过工作流的情况下执行。

## 审批人任务（Approver’s Task）

如果工作流需要审批人，我们需要一个界面让审批人执行批准或拒绝的操作。下图显示了选择审批任务的界面：

| ![](img/image_rsrc8UU.jpg) |
| 图 5-7 显示了审批人界面的配置。 |

下图显示了审批人界面的示例。图标 ![](img/image_rsrc8UW.jpg)

| 图 5-8 显示了审批人界面 |

你可以通过创建新的管理任务来创建新的审批人任务。你必须选择操作类型为“Approve Event”（批准事件）或“Approve Task”（批准任务）。

## 审批人（Approver）

如果工作流需要审批人，我们需要指定谁是审批人。我们可以从`Participant Resolver`（参与者解析器）下拉列表中选择审批人类型。它提供了获取审批人的条件。

| ![](img/image_rsrc8UX.jpg) |
| 图 5-9 显示了下拉列表：Participant Resolver |

如果获取审批人的需求复杂，你可以通过`Participation Resolver API`进行编程。我们将在下一章中学习`Participation Resolver API`。

## 预期结果（Expected Outcome）

处理工作流时，我们应该始终意识到结果：批准或拒绝。例如，我们有一个包含两个标签的管理任务：`Profile`标签和`Access Role`标签。我们有一个`Business Logic Task Handler`，并且设置了三个工作流：一个在管理任务级别，一个用于`ModifyUserEvent`，另一个用于`AssignAccessRoleEvent`。下图显示了所有可能的结果。

| ![](img/image_rsrc8UY.jpg) |
| 图 5-10 显示了所有结果示例 |

如果你使用`ProviderAccessor API`，必须意识到`ProviderAccessor`会直接更新用户存储，而不依赖于工作流。下图显示`City`的初始值为多伦多。然后我们使用`ProviderAccessor API`将`City`属性修改为纽约。无论工作流被拒绝还是批准，市的最终值都是纽约。

| ![](img/image_rsrc8UZ.jpg) |
| 图 5-11 显示了 ProviderAccessor API 修改属性值 |

### 5.1.2 Workpoint 设计器概念（Workpoint Designer Concept）

CA IdentityMinder 内部的工作流是由`WorkPoint Designer`工具创建的。`WorkPoint Designer`是第三方软件并与 CA IdentityMinder 集成。你可以通过命令`<admin_tools>\WorkPoint\bin\Designer.bat`运行 Workpoint Designer。

| ![](img/image_rsrc8V0.jpg) |
| 图 5-12 显示了 Workpoint Designer 的启动界面 |

你需要检查配置文件`workpoint-client.properties`。该文件位于`<admin_tools>\WorkPoint\conf`文件夹。J2EE Client 配置必须与你的应用服务器匹配。

## 流程 vs. 任务（Processes vs. Jobs）

Process（流程）和 Job（任务）是 Workpoint 的技术术语。

- Processes（流程）是业务进行并通常重复的功能。
- Jobs（任务）是流程的实例。

例如，如果`Process`是一个订单履行流程的计划，那么具体的案例（或`Jobs`）就是实际的订单。Process 类似于`java`中的`Class`，而 job 是`java class`的对象或实例。

### 流程（Processes）

运行 Workpint Designer，从菜单中选择“Open Process”（打开流程）。双击名为“SingleStateApproval”的流程，你将看到该流程。

| ![](img/image_rsrc8V1.jpg) |
| 图 5-13 显示了流程“SingleStateApproval” |

### 任务（Jobs）

从菜单中选择“Open Job”（打开任务）。双击名为“SingleStateApproval”的流程，你将看到该流程。（如果 Process 是订单履行流程的计划，具体的案例或 Jobs 就是实际的订单。Process 类似于 java 中的 Class，job 是 java class 的对象或实例。）

| ![](img/image_rsrc8V2.jpg) |
| 图 5-14 显示了任务 |

### 帮助（Help）

点击菜单“Help”，将显示帮助内容。你可以选择“process definition”和“job definition”。

| ![](img/image_rsrc8V3.jpg) |
| 图 5-15 显示了 Workpoint 的帮助 |

另一个 Workpoint 文档位于`<admin_tools>\Workpoint\docs`。

## 5.2 自定义工作流（Custom Workflow）

IdentityMinder 官方没有具体说明如何创建自定义工作流。本章剩余部分将介绍如何创建。

### 为什么我们需要自定义工作流？

第一个原因是默认模板工作流不符合我们的需求。例如，你可能需要三个审批人，而默认只支持两个。

第二个原因是我们在工作流期间需要与其他系统集成或执行某些业务逻辑。例如：

- 工作流期间，我们需要调用 Web 服务。
- 如果用户位于北美，则需要第二个审批人。我们需要创建路由路径来检查用户。

本节包含两个部分：

- IdentityMinder 的工作流：你将学习与 IdentityMinder 相关的工作流规则。
- Workpoint 编程：我们将介绍一些 Workpoint 功能。

### 5.2.1 Workflow 与 IdentityMinder

当你为 IdentityMinder 创建工作流时，必须遵循以下规则：

#### 规则 1

必须从`Start`节点开始并在`Stop`节点结束。这是一个合理的规则，工作流必须有起点和终点。在 Workpoint 设计器中，从菜单拖入节点。

| ![](img/image_rsrc8V4.jpg) |
| 图 5-16 显示了 Workpoint 中的 Start 和 Stop 节点 |

#### 规则 2

在进入`Stop`节点之前必须有`Approve`或`Reject`节点。（工作流只有一个拒绝节点是不合理的）

任何工作流，在完成工作流之前，都需要将状态设置为`Approve`或`Reject`。我们需要告诉 IdentityMinder 最终结果，是批准还是拒绝。

拖入自动化节点并设置配置：（你将在示例代码中看到详情，不用担心）

- 在 resources 标签页中：选择 external。
- 在 agents 标签页中，对于批准状态，选择“Notify IM Approver”（通知 IM 审批人），对于拒绝状态，选择“Notify IM Reject”（通知 IM 拒绝）。

| ![](img/image_rsrc8V5.jpg) |
| 图 5-17 显示了 Stop 之前的批准和拒绝状态 |

#### 规则 3：审批人配置（如果你需要审批人）



如果你需要审批人，必须执行以下操作（你可以在示例代码中查看详情）：

- 将活动节点拖入画布。
- 在`resources`标签页中选择`IMApprovers`。
- 在`agents`标签页中选择`Nobody AutoComplete`作为异步代理。
- 在`user data`标签页中，按照下表设置值（示例中包含详细步骤说明：基础自定义工作流）。

| Name | Type | Description |
| :--- | :--- | :--- |
| ACTION_PERFORMED | Text | 用于转换 |
| PARTICIPANT_ID | Text | 审批人 ID |
| PARTICIPANT_NAME | Text | 链接到属性文件 |
| PARTICIPANT_DESCRIPTION | Text | 链接到属性文件 |

## 规则 4：在管理员任务级别的工作流（可选）

默认情况下，工作流可以在事件级别运行。如果你想让工作流在管理员任务级别运行，必须：

- 选择流程的`User Data`并添加`TASK_LEVEL = true`。

## 5.2.2 工作点组件

我们将介绍 Workpoint Designer 的基本组件。

### 活动节点

活动代表业务流程中的一个步骤。根据活动完成的方式，共有 3 种类型的活动。节点的显示方式有所不同。

| Node | Type | Description |
| :--- | :--- | :--- |
| ![](img/image_rsrc8V6.jpg) | 人工自动 | 它将由人员完成，用于审批人。 |
| ![](img/image_rsrc8V7.jpg) | 活动自动 | 需要特殊的代码来完成活动。 |
| ![](img/image_rsrc8V8.jpg) | 服务器自动 | WorkPoint Server 自动完成此活动。 |

如果你需要审批人，请选择节点类型`Automated by a person`。

如果你必须执行任何逻辑或调用任何后端，请选择节点类型`Automated by server`。例如，你有逻辑来调用 Web 服务，当逻辑完成时，Workpoint 将移动到下一个节点。你编写任何特殊代码。

如果你选择节点类型`Automated by activity`来调用 Web 服务，当逻辑完成后，它不会移动到下一个节点。流程将停止。你必须编写特殊代码来完成该节点的活动，然后 Workpoint 才会移动到下一个节点。（`Approve`和`Reject`节点已有用于完成活动的代码。）

下图显示了 3 种活动/节点：

- 节点`App Admin`是活动：人工自动。
- 节点`Call Web Servcies`是活动：服务器自动。
- 节点`Approve`和`Reject`是活动：活动自动。

| ![](img/image_rsrc8V9.jpg) |
| :--- |
| 图 5-18 显示了 3 种活动 |

### 转换（Transition）

转换是工作图中连接两个不同节点的线。转换可以是无条件的，也可以是有条件的。有条件的转换与转换选择脚本相关联。

我们使用转换作为工作流中的选择路径。下图显示了带有条件的转换。例如，如果部门等于中心，则进入发送工单，然后发送邮件并完成工作流。

| ![](img/image_rsrc8VA.jpg) |
| :--- |
| 图 5-19 显示了 3 个有条件的转换。 |

### 延迟节点

延迟代表业务流程中的暂停或保持。例如，在配置过程中，我们创建了用户，但必须等待到入职日期，然后才会启用该用户。如果用户的城市是纽约，我们将在早上 6 点为用户添加角色。

| ![](img/image_rsrc8VB.jpg) |
| :--- |
| 图 5-20 显示了延迟的示例 |

### 分类（Category）

类别是对象的组。类别可用于过滤设计器中的告警、邮件、脚本、流程和节点模板列表。类别帮助我们导入和导出工作流。

### 参数（Parameters）

当我们编写代码时，Workpoint 提供了一些参数：

- `ClientContext`：对于 CA IdentityMinder，`ClientContext`是构建`WorkflowContext`的必需参数。`WorkflowContext`是`ProviderAccessor` API 的子类。
- `SymbolTable`：它用于向 WorkPoint Server 返回结果值。我们通常在`Delay`节点中使用`SymbolTable`来回答延迟多久。
- `JobData`：它包含任务级别的数据。我们使用`JobData`在节点之间共享数据。
- `ActivityInstData`：它包含节点级的数据。我们通常在`Transition`中使用`ActivityInstData`。

## 5.3 代码示例

本章的示例将包含 2 部分：

- Workpoint 和代码
- 配置

我们将使用上一章中的管理员任务。请禁用上一章中与管理员任务`Update Location and Ext number`相关的 Identity Policy Set、`policy Xpress`和`Business Logic Task Handler API`。

| ![](img/image_rsrc8VC.jpg) |
| :--- |
| 图 5-21 显示了管理员任务 |

我们可以通过以下方式移除`Business Logic Task Handler`：

1. 搜索我们的管理员任务名称：`Update Location and Ext Number`。
2. 点击`Business Logic Task Handlers`按钮，然后点击减号图标移除 Business Logic Task Handler。
3. 点击确定并提交。

| ![](img/image_rsrc8VD.jpg) |
| :--- |
| 图 5-22 显示了移除 Business Logic Task Handler 的图标 |

### 5.3.1 工作流：单个审批人

我们将创建一个有一个审批人的基本工作流并将其部署到 CA IdentityMinder。此示例仍然不需要任何编程。

如果你不想手动创建工作流，可以导入工作流，请参见附录 A。

#### Workpoint 和代码

1. 运行 Workpoint 设计。
2. 创建新流程，点击顶部的：

   | ![](img/image_rsrc8VE.jpg) |
   | :--- |
   | 图 5-23 显示“New Process” |

3. 在`general`标签页中按如下表填写值：

   | Name | Value | Description |
   | :--- | :--- | :--- |
   | Name | One Approver | Name 字段包含工作流名称 |
   | Reference | Example | Reference 字段包含唯一标识 |

4. 点击`OK`。下图显示了`general`标签页中的值。

   | ![](img/image_rsrc8VF.jpg) |
   | :--- |
   | 图 5-24 显示`general`标签页中的值 |

5. 根据规则 1，流程必须以`Start`节点开始并以`Stop`节点结束。从菜单拖节点到画布。

   | ![](img/image_rsrc8VG.jpg) |
   | :--- |
   | 图 5-25 显示“Start”和“Stop” |

6. 根据规则 2，流程在`Stop`节点之前必须有`Approve`或`Reject`状态。从菜单拖`Activity`节点。

   | ![](img/image_rsrc8VH.jpg) |
   | :--- |
   | 图 5-26 显示“Activity” |

   点击节点（`Node3`）并按下表填写：

   | Tab | Field Name | Value | Description |
   | :--- | :--- | :--- | :--- |
   | General | Approve |  | Name 字段包含活动名称 |
   | Resources | Assignment | External | Resource 页面识别执行活动的资源。对于 CA IdentityMinder，选择 External。 |
   | Agents | Asynchronous | Notify Approve | 此值对于 CA IdentityMinder 是必需的。选择脚本`Notify Approve`。 |

   | ![](img/image_rsrc8VJ.jpg) |
   | :--- |
   | 图 5-27 显示带有脚本`Notify Approve`的`resources`标签页 |

   然后点击确定。下一步我们将做 Reject 状态（`Node4`）。它与审批活动几乎相同，但脚本代理是`Notify Reject`。

   | Tab | Field Name | Value | Description |
   | :--- | :--- | :--- | :--- |
   | General | Reject |  | Name 字段包含活动名称 |
   | Resources | Assignment | External | 对于 CA IdentityMinder，选择 External。 |
   | Agents | Asynchronous | Notify Reject | 此值对于 CA IdentityMinder 是必需的。选择脚本`Notify Reject`。 |

   | ![](img/image_rsrc8VK.jpg) |
   | :--- |
   | 图 5-28 显示带有脚本`Notify Reject`的`agents`标签页 |

   完成此步骤后，我们的画布应显示所示。

   | ![](img/image_rsrc8VM.jpg) |
   | :--- |
   | 图 5-29 显示画布 |

7. 对于审批人，将`Activity`节点拖入画布。

   | ![](img/image_rsrc8VN.jpg) |
   | :--- |
   | 图 5-30 显示活动节点 |

   规则 3：如果我们有审批人，必须设置某些属性。右键点击审批节点并选择属性。审批人节点需要如下配置：

   | Tab | Field Name | Value | Description |
   | :--- | :--- | :--- | :--- |
   | General | Name | Approver | Name 字段包含活动名称 |
   | Resources | Assignment | Any | 此值对于 CA IdentityMinder 是必需的。选择资源：`IM Approvers`。 |
   | Include | IM Approvers |  |  |
   | 代理 | 代理 | 无自动填充（Nobody AutoComplete） | （可选）选择“无自动填充”作为异步列表。 |
   | 用户数据 | 参见下表 | CA IdentityMinder 的必要属性 |  |

   | ![](img/image_rsrc8VP.jpg) |
   | :--- |
   | 图 5-31 显示了审批者的资源选项卡 |

   `agents`选项卡中的`Nobody AutoComplete`脚本是一个可选步骤。该脚本将计算审批者的数量。如果`approver`为 0，此脚本将完成此节点并移动到下一个节点。

   | ![](img/image_rsrc8VR.jpg) |
   | :--- |
   | 图 5-32 显示了审批者的可选步骤、代理选项卡 |

   该表显示了用户数据选项卡的值。

   | 名称 | 类型 | 值 |
   | :--- | :--- | :--- |
   | `ACTION_PERFORMED` | 文本 | none |
   | `PARTICIPANT_ID` | 文本 | Approval |
   | `PARTICIPANT_NAME` | 文本 | `imstask.label.singlestepapproval.approvalstep.name` |
   | `PARTICIPANT_DESCRIPTION` | 文本 | `imstask.label.singlestepapproval.approvalstep.description` |

   | ![](img/image_rsrc8VS.jpg) |
   | :--- |
   | 图 5-33 显示了审批者的用户数据选项卡 |

   属性`PARTICIPANT_NAME`和`PARTICIPANT_DESCRIPTION`链接到属性文件：`<server>/IdentityMinder.ear/custom/resourceBundle/IMSResources.properties`。

   ```properties
   SingleStepApprovalimstask.label.singlestepapproval.approvalstep.name=Primary Approver
   imstask.label.singlestepapproval.approvalstep.description=Identity Manager 向主审批者发送第一条请求。如果找到，主审批者可以批准或拒绝该任务或事件。
   ```

   这些属性的值在设置`approver`时将显示在屏幕上。你可以添加新属性并将其设置为`approver`节点。

   | ![](img/image_rsrc8VT.jpg) |
   | :--- |
   | 图 5-34 显示了屏幕上的属性值 |

### 7. 转换

拖动转换连接节点之间：

- 从`Approve`到`Stop`节点，定义为`Unconditional`（无条件）。
- 从`Reject`到`Stop`节点，定义为`Unconditional`（无条件）。
- 从`Start`到`Approver`节点，定义为`Unconditional`（无条件）。
- 拖动从`Approver`到`Approve`节点的连接，定义类型为`condition`（条件）。选择现有脚本：`Approved`。
- 拖动从`Approver`到`Reject`节点的连接，定义类型为`condition`（条件）。选择现有脚本：`Rejected`。所有连接显示如下所示。

| ![](img/image_rsrc8VU.jpg) |
| :--- |
| 图 5-35 显示了转换的属性 |

| ![](img/image_rsrc8VV.jpg) |
| :--- |
| 图 5-36 显示了完整的工作流 |

### 8. 设置管理员任务级别工作流

我们想在管理任务级别看到此工作流。在画布上右键点击并选择`User Data`选项卡。选择类型`Text`，输入名称：`TASK_LEVEL`，值为`true`，然后点击`Add`。

| ![](img/image_rsrc8VW.jpg) |
| :--- |
| 图 5-37 显示了进程的属性 |

点击保存按钮。

![](img/image_rsrc8VX.jpg)

此工作流将自动部署到 CA IdentityMinder。

#### 配置

工作流有两种配置方式：`admin task level`和`event level`。本示例将使用`admin task level`的工作流。

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择`Roles`和`Tasks`选项卡，选择菜单`modify admin task`。
3. 搜索我们的管理任务名称：`Update Location and Ext Number`。
4. 验证`Workflow`复选框已勾选。
5. 选择图标`pencil`以添加工作流。

   | ![](img/image_rsrc8VY.jpg) |
   | :--- |
   | 图 5-38 显示在管理任务中启用工作流 |

6. 选择我们的工作流`Example: One Approver`。如果你看不到工作流，说明你可能漏掉了添加工作流属性的步骤（`TASK_LEVEL=true`）。
7. 对于`Approval Task`（审批界面），选择`Approve Admin Task`。
8. `Participant Resolver`是审批者。选择`List of Users`并选择`Add Users`。选择一个审批者。你可以使用自己的用户作为审批者。
9. 点击`OK`按钮，然后再次提交以完成任务修改。

   | ![](img/image_rsrc8VZ.jpg) |
   | :--- |
   | 图 5-39 显示管理任务中的工作流配置 |

#### 工作原理

我们可以按照以下步骤执行工作流：

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择选项卡：`Book Example`，并在`Book Example`选项卡中选择`Admin Task`：`Update Location and Ext Number`，然后搜索并选择某些用户。
3. 修改城市属性并提交管理任务。

提交任务后，你将看到消息`Alert: Task pending`。这意味着工作流正在异步阶段运行。

### 审批过程

1. 提交后，如果你以`approver`身份登录，将看到等待审批的列表。

   | ![](img/image_rsrc8W0.jpg) |
   | :--- |
   | 图 5-40 显示任务等待审批 |

2. 当你点击此任务时，你将看到`approve`或`reject`按钮。点击`approve`按钮。

   | ![](img/image_rsrc8W1.jpg) |
   | :--- |
   | 图 5-41 显示带有 approve 和 reject 按钮的审批者任务 |

### 在查看提交任务屏幕中查看工作流作业

在`System`选项卡下选择`View submitted task`，选择我们的任务。

| ![](img/image_rsrc8W2.jpg) |
| :--- |
| 图 5-42 显示在查看提交任务中的我们的任务 |

点击`pencil`图标查看内部详情。在`Task Workflow Job View`部分，点击`pencil`图标，我们将看到我们的工作流。



| ![](img/image_rsrc8W3.jpg) |
| --- |
| 图我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。5-43 显示管理任务级别的工作流 |

### 在 `Workpoint designer` 中查看作业

查看作业的另一种方法：运行 `Workpoint designer`，选择菜单 `open Jobs`，然后双击我们的工作流。

#### 工作流作业 ID

Workpoint 将打开新标签页，显示所有作业。在 `view submitted task` 屏幕上，通过 `Workpoint designer` 选择 `pencil` 图标显示。

| ![](img/image_rsrc8W4.jpg) |
| --- |
| 图 5-44 显示工作流中的作业 |

| ![](img/image_rsrc8W5.jpg) |
| --- |
| 图 5-45 显示工作流 |

### 5.3.2 工作流：按城市延迟

此示例展示了高级技术。如果城市值为 `New York`，流程将延迟 10 分钟。如果城市是其他值，则不会延迟。工作流显示在图中。

#### Workpoint 和代码

1. 运行 `Workpoint designer`。

2. 创建新进程，点击 `File > New > New Process`。

3. 在 `general` 选项卡输入下表的值，然后点击 `OK`。

| 字段名称 | 值 | 描述 |
| --- | --- | --- |
| `Name` | `Example : Delay` | Name 字段标识进程名称 |
| `Reference` | `BookEx.Delay` | Reference 字段包含唯一名称 |

| ![](img/image_rsrc8W7.jpg) |
| --- |
| 图 5-47 显示 general 中的值 |

4. 根据规则 1，流程从 `Start` 节点开始并以 `Stop` 节点结束。从菜单拖动节点到画布。

| ![](img/image_rsrc8W8.jpg) |
| --- |
| 图 5-48 显示“Start”和“Stop” |

5. 根据规则 2，流程在 `Stop` 节点之前必须有 `Approve` 或 `Reject` 状态。从菜单拖入 `Activity` 节点。我们不需要 `reject`，所以只拖入一个节点。配置与 `approve` 节点相同，但我们命名为 `Commit`。

| 选项卡 | 字段名称 | 值 | 描述 |
| --- | --- | --- | --- |
| `General` | `Commit` | Name 字段包含活动名称 |
| `Resources` | `Assignment` | `External` | 对于 CA IdentityMinder，选择 `External` |
| `Agents` | `Asynchronous` | `Notify IM Approve` | 此值为 CA IdentityMinder 所需。选择脚本 `Notify IM Approve` |

提示：你可以通过 `CRLT+C` 从其他进程复制 `Approved` 节点并粘贴到我们的进程中。

6. 将 `Delay` 节点拖到画布。

| ![](img/image_rsrc8W9.jpg) |
| --- |
| 图 5-49 显示“Delay”节点 |

双击 `Activity` 节点（图中第 4 个节点）并添加如下配置：

| 选项卡 | 字段名称 | 值 | 描述 |
| --- | --- | --- | --- |
| `General` | `Delay 10 Minutes` | Name 字段包含活动名称 |

在 `Evaluation Date` 选项卡中，选择 `Script Calculated Delay`。点击新图标创建新脚本。

![](img/image_rsrc8WA.jpg)

图 5-50 显示了创建新脚本的图标。

在 General（通用）选项卡中，将名称设置为“Delay 10 Minutes”，并选择 `Statement` 选项卡。

| 选项卡 | 字段名称 | 值 |
| --- | --- | --- |
| General | Name | Delay 10 Minutes |
| Statements | Statement Type | Java |
| Java Class | `com.book.idm.workflow.DelayForNYFlow` |
| Method | `delay10Minutes` |
| Parameters | `SymbolTable` |

![](img/image_rsrc8WB.jpg)

图 5-51 显示了脚本界面。

我们需要参数 `SymbolTable`，因为我们的 Java 代码将结果延迟时间设置到了对象 `SymbolTable`。

### 7. 将“Server Automated”（服务器自动化）拖到画布上

我们将编写一些业务逻辑。

![](img/image_rsrc8WC.jpg)

图 5-52 显示了服务器自动化节点。

双击节点（图片中的节点 5）并按如下所示添加配置：

| 选项卡 | 字段名称 | 值 | 描述 |
| --- | --- | --- | --- |
| General | Name | Check City Value | Name 字段包含该名称。 |
| Resources | Assignment | External | 此工作分配选项允许外部应用程序向 WorkPoint 数据库中插入资源分配。 |

选择 agents（代理）选项卡，点击 new 按钮添加新脚本。

| 选项卡 | 字段名称 | 值 |
| --- | --- | --- |
| General | Name | IsNewYorkCity |
| Statements | Statement Type | Java |
| Java Class | `com.book.idm.workflow.DelayForNYFlow` |
| Method | `checkCityValue` |
| Parameters | `ClientContext`, `ThisJobData`, `ThisActivityInstData` |

然后点击 ok 完成新脚本创建。

![](img/image_rsrc8WD.jpg)

图 5.53 显示了新脚本界面。

点击 user data（用户数据）选项卡，我们将为转换添加值。User Data 允许以名称/值数据对的形式保存自定义应用程序数据。在我们的需求中，我们希望在用户数据中保留城市值。

| Name | Type | Value |
| --- | --- | --- |
| city | Text | none |

对于初始值，我们将值设置为 none。我们稍后将在编程部分详细介绍。

![](img/image_rsrc8WE.jpg)

图 5-54 显示了用户数据。

点击“add”按钮，然后点击 ok 完成。

### 8. 在节点之间拖入转换线并将类型定义为无条件（unconditional）

- 从“Start”（开始）到“Is New York City”节点。
- 从“Delay 10 Minutes”到 Commit（提交）节点。
- 从“Commit”到“Stop”（停止）节点。

![](img/image_rsrc8WF.jpg)

图 5-55 显示了节点之间的转换。

### 9. 我们为城市等于 New York（纽约）的情况定义条件转换

- 从“Is New York City”节点拖入转换线到“Delay 10 Minutes”节点。
- 选择类型：Conditional（条件）。
- 选择 create new script（创建新脚本）。
- 输入名称：`City == New York`。
- 点击 next（下一个）按钮。

![](img/image_rsrc8WG.jpg)

图 5-56 显示了条件转换界面。

- 点击第一列：左操作数，选择 `SourceActivity.UD.city`。
- 第二列：比较，选择 `String =`。
- 第三列：右操作数，输入值“new york”。
- 点击 finish（完成）结束该步骤。

![](img/image_rsrc8WH.jpg)

图 5-57 显示了条件转换语句界面。

在这一步中，我们创建了条件。如果 `SourceActivity.UD.city == new York`，则走此路径。

### 10. 我们必须为城市不等于 New York 的情况定义另一个条件转换

- 从“Is New York City”节点拖入转换线到“Commit”节点。
- 选择类型：Conditional（条件）。
- 选择 create new script（创建新脚本）。
- 点击 next（下一个）按钮。
- 输入名称：`City != New York`。
- 点击第一列：左操作数，选择 `SourceActivity.UD.city`。
- 第二列：比较，选择 `String !=`。
- 第三列：右操作数，输入值“new york”。
- 点击 finish（完成）结束该步骤。

![](img/image_rsrc8WJ.jpg)

图 5-58 显示了条件转换语句界面。

### 11. 点击保存图标，整个工作流应该如图片所示

![](img/image_rsrc8WK.jpg)

图 5-59 显示了完整的工作流。

### 12. 将 Java 类复制到“custom”文件夹

（与 Business Logic Task Handler 代码在同一文件夹）

- `com.book.idm.workflow.DelayForNYFlow`
- `com.book.idm.workflow.WorkpointHelper`

我们稍后将详细介绍 Java 代码。

#### 配置

在此示例中，我们将在事件级别指定我们的工作流。

1. 搜索我们的管理员任务名称：Update Location and Ext Number（更新位置和分机）。
2. 确保勾选 Enable Workflow（启用工作流），并移除之前示例中的工作流以防混淆。

![](img/image_rsrc8WM.jpg)

图 5-60 显示了启用工作流的选择框和移除之前的工作流。

3. 选择 events 选项卡并点击事件 `ModifyUserEvent` 铅笔图标。
4. 选择我们的工作流“Example: Delay for NY”。
5. 点击 OK 按钮然后再次提交以完成任务修改。

![](img/image_rsrc8WN.jpg)

图 5-61 显示了 ModifyUserEvent 中的工作流。

#### 工作原理

1. 以管理员身份登录 Identity Manager 用户控制。
2. 选择选项卡：Book Example 并选择管理员任务：“Update Location and Ext Number”，然后搜索并选择一些用户。
3. 修改城市属性并提交管理员任务。

### 查看提交的任务

在“System”选项卡下选择“View submitted task”（查看已提交的任务），选择我们的任务。点击铅笔图标查看详情。

![](img/image_rsrc8WP.jpg)

图 5-62 显示了我们的任务。

向下滚动直到看到事件名称：Modify user。点击“铅笔”图标查看工作流详情。

![](img/image_rsrc8WR.jpg)

图 5-63 显示了 ModifyUserEvent。

查看“Event Workflow Job View”部分并选择铅笔图标查看工作流。如果你将城市属性更改为 New York，你会看到流程停止且节点延迟 10 分钟。等待 10 分钟后，它将完成工作流。

![](img/image_rsrc8WS.jpg)

图 5-64 显示用户更新城市为 New York 任务。

如果你将城市属性改为其他值，它将直接进入节点而无需等待。

### 节点：Check City Value

该节点的配置如下：

- 在 user data 选项卡中，我们设置名称和值：`city=none`。
- 在 agents 选项卡中，我们选择脚本 `IsNewYorkCity`。
- Java 类名：`com.book.idm.workflow.DelayForNYFlow`。
- 方法名：`isNewYorkCity`。
- 参数：`ClientContext`, `SymbolTable`, `ThisJobData`, `ThisActivityInstData`。

![](img/image_rsrc8WT.jpg)

图 5-65 显示自动化节点的配置。

在 `checkCityValue` 方法中，参数必须与脚本参数顺序和值完全匹配（`ClientContext clientContext`, `JobData thisJobData`, `ActivityInstData thisactivityInstData`）：

- `ClientContext` —— 需要构建 `WorkflowContext`。
- `JobData` —— 需要构建 `WorkflowContext`。
- `ActivityInstData` —— 用于访问 user data 选项卡中的“city”值。

```java
public void checkCityValue(ClientContext clientContext, JobData thisJobData,ActivityInstData thisactivityInstData){User user = null;WorkflowContext workflowContext = null;try{// 获取上下文 workflowContext = WorkpointHelper.getWorkflowContext(clientContext,thisJobData);user = WorkpointHelper.getUser(workflowContext);System.out.println("City : New Value ="+user.getAttribute("l"));System.out.println("City : Old Value ="+user.getLastCommittedAttribute("l"));//将新值存入用户数据 thisactivityInstData.setUserData("city",user.getAttribute("l").toLowerCase());}catch(Exception e){e.printStackTrace();}}
```

我们必须获取 `WorkflowContext`。`WorkflowContext` 是与 CA IdentityMinder 交互的主要 API。

```java
workflowContext = WorkpointHelper.getWorkflowContext(clientContext,thisJobData);
```

```java
public static WorkflowContext getWorkflowContext(ClientContext clientContext,JobData thisJobData) throws WorkPointEJBException,Exception{
    TableID jobTableId = thisJobData.getJobID();
    Job job = Job.queryByID(clientContext, jobTableId, true);
    //Get the idJobUserDataTable 
    imsIdUD = job.getUserData("ims-id");
    String imsId = (String)imsIdUD.getVariableValue();
    String envOid = (String)job.getUserData("ime-id").getVariableValue();
    WorkflowContext workflowContext = (new WorkflowCallbackHelper()).generateWorkflowContext(imsId,envOid);
    return workflowContext;
}
```

`WorkflowCallbackHelper.generateWorkflowContext` 需要 2 个参数：`ims-id` 和 `ime-id`。这些 ID 在任务创建时生成。你可以搜索该任务（流程实例），在画布上点击右键并查看任务的 user data（用户数据）标签卡。我们的代码通过 `queryByID()` 方法获取当前任务，然后通过 `getUserData()` 方法获取 `ims-id` 和 `ime-id`。

顺带一下，获取 `WorkflowContext` 的代码模式可以直接复制并复用。

![](img/image_rsrc8WU.jpg)

图 5-66 显示了 user data 标签卡中的 `ims-id` 和 `ime-id`。

下一行显示了如何从 workflow context 中获取 User 对象。我们创建了返回用户对象的工具方法 `getUser()`。

```java
user = WorkpointHelper.getUser(workflowContext);
```

我们使用 `getSubject()` 方法返回管理员任务的主对象。我们的管理员任务以 `User` 为主对象。如果你尝试在主对象不是用户的的管理员任务中调用此方法，你将得到错误。



```java
public static User getUser(WorkflowContext workflowContext) throws Exception{
    ManagedObject managedObject = workflowContext.getSubject();
    if(managedObject instanceof User){
        return (User)managedObject;
    }else{
        throw new IllegalArgumentException("Managed Object is not User");
    }
}
```

`WorkflowContext` 继承了 `IMContext`、`IMPersistentContext`、`ProviderAccessor`、`ServiceProvider` 和 `TaskInfo`。更多细节请参考官方 Java 文档。它与 `BLTHContext` 几乎相同，但区别在于 `WorkflowContext` 继承了 `EventContext`。

请注意，流程有两个级别：管理员任务级别和事件级别。如果你的流程运行在管理员任务级别，并尝试调用父类 `EventContext` 的任何方法，你将得到意外的结果。

我们有另一个方法 `getUser(EventContext context)`。你必须确保你的流程运行在用户事件上。下面的代码显示了如何从事件获取用户对象。

```java
IMEvent evt= workflowContext.getEvent();      
User user = ((UserEvent)evt).getUser();
```

我们在 `WorkpointHelper.java` 中的 `getUser()` 方法可以在你的项目中复用。我们对流程编程有额外的说明。

### 注意事项 1：`WorkflowContext`，如何正确调用父类 `EventContext` 中的方法

- 如果流程运行在管理员任务级别，不要调用父类 `EventContext` 的方法。
- 确保你进行了正确的类型转换。例如：
  - 流程关联到事件 `ModifyUserEvent`，你可以通过 `UserEvent` 转换对象（`ModifyUserEvent` 是 `UserEvent` 的子类）：

    ```java
    User user = ((UserEvent)evt).getUser();
    ```

  - 流程关联到事件 `AddToGroupEvent`，你可以通过 `GroupEvent` 转换（`AddToGroupEvent` 是 `GroupEvent` 的子类）：

    ```java
    Group group = ((GroupEvent)evt).getGroup();
    ```

这与 `BLTHContext` 相同，当你使用 `getSubject()` 方法时，请检查管理员任务的主对象。

我们代码的下一行打印了值。它演示了如何访问新值和旧值。

```java
System.out.println("City : New Value ="+user.getAttribute("l"));
System.out.println("City : Old Value ="+user.getLastCommittedAttribute("l"));
```

下一行代码显示了如何在 User Data 标签卡中设置值。在 User Data 标签卡中，我们添加了键值对（`city=none`）。这段代码将值修改为新用户的城市属性。

```java
//将新值放入 User Data
thisactivityInstData.setUserData("city",user.getAttribute("l").toLowerCase());
```

跳转（Transition）使用 User Data 中的 `city` 来决定路径。如果发生异常（默认值为“none”），它将进入“City != New York”路径。因此你应该注意流程内部的异常。

![](img/image_rsrc8WV.jpg)

图 5-67 显示了用户数据与跳转之间的关系。

### 跳转（Transition）

跳转是节点之间的连接。你可以通过点击条件标签卡中的笔图标来编辑跳转中的条件。

![](img/image_rsrc8WW.jpg)

图 5-68 显示了用于编辑条件的铅笔图标。

在我们的示例中，我们使用了条件向导（condition wizard）。在条件标签卡中，有许多创建条件的方法，你也可以进行编程（但不推荐）。

提交后无法编辑条件，但你可以更改语句类型或删除此脚本并创建一个新的。（某些情况下，由于存在引用你无法删除，如果你不想删除引用，建议更改名称。）

![](img/image_rsrc8WX.jpg)

图 5-69 显示了语句类型的列表。

### 跳转条件中使用 Java 代码

跳转可以使用 Java 代码；你需要在 `SymbolTable` 中设置 TRUE 或 FALSE。例如，跳转“City == New York”，我们可以这样写：

```java
boolean result = false;
if(city.equalsIgnoreCase("new york")){
    result = true;
}
symbolTable.add("Result1").setValue(0);
```

关于 `SymbolTable` 的更多细节请参阅 Workpoint 文档。我们需要从 User Data 获取城市值。跳转是“源节点”和“目标节点”之间的连接。

图 5-70 显示了两种方法从源节点访问城市值。

第一种方法：传递参数。`SourceActivity` 表示源节点，`UD` 表示 User Data，你需要填写 `city`。

![](img/image_rsrc8WZ.jpg)

图 5-71 显示了参数中的 `SourceActivity.UD`。

对于编程，你只需声明 `String` 参数：

```java
public void isCityEqualNewYork(String city,SymbolTable symbolTable,JobData thisJobData,JobTranData jobTransData){
    System.out.println("通过传递 SourceActivity.UD 获取的城市:"+city);
}
```

第二种方法，通过源节点 ID 查询。这种方法你需要两个参数：`JobData` 和 `JobTranData`。

![](OEBPS/image_rsrc8X0.jpg)

图 5-72 显示了参数中的 `JobData` 和 `JobTranData`。

`ThisJobData` 表示流程实例。`ThisJobTransitionData` 表示此跳转的实例。下面的代码显示了如何从源节点访问用户数据。

```java
TableID sourceJobNodeID = jobTransData.getSourceJobNodeID();
ActivityInstData sourceActivity = thisJobData.getActivityByNodeID(sourceJobNodeID);
String cityUD = sourceActivity.getUserData("city").getVariableValue();
System.out.println("通过 sourceJobNodeID 获取的城市:"+cityUD);
```

我们使用 `jobTransData` 获取源 ID，然后通过它查询源节点。当我们获取源节点时，就可以获取 User Data。

### 注意事项 2：保持跳转条件简单

我的建议是保持跳转条件简单。你应该使用条件向导。避免在跳转中使用任何复杂的逻辑。例如，我们有两个跳转：“City == New York”和“City != New York”。如果你在“City == New York”跳转中进行编程计算，你需要在另一个跳转中也进行编程。这意味着你做了两次。

建议在源节点中进行逻辑处理或计算，并在用户数据中保留纯结果。跳转只使用结果来确定路径。这样更容易维护。

### 延迟（Delay）

延迟的概念非常直观：你希望该节点持续到何时。你只需要在 `SymbolTable` 的 `result1` 中放入格式为“yyyy-MM-dd HH:mm:ss”的日期时间值即可。

```java
public void delay10Minutes(SymbolTable symbolTable){
    Date current = new Date();
    Calendar calendar = Calendar.getInstance();
    calendar.setTime(current);
    calendar.set(Calendar.MINUTE, calendar.get(Calendar.MINUTE)+10);
    //yyyy-MM-dd HH:mm:ss
    SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
    String executeTime = simpleDateFormat.format(calendar.getTime());
    SymbolData r1 = symbolTable.add("Result1");
    r1.addValue(executeTime);
}
```

延迟节点支持在评估日期选项页中通过配置延迟时间。详情请参阅工作点文档。

## 节点提交（Node Commit）

我们有一条规则：在完成工作流之前必须进行通过或拒绝。在这个示例中，我们只需要一条路径。因此我们只需要通过状态，但我们将名称命名为“Commit（提交）”。

## 错误工作流

有时，你在工作流上进行编程会遇到一些错误。你应该取消你的任务或事件。我们不应该在系统中留下未完成的流程。你可以在“查看已提交的任务（View Submitted task）”中取消。

![](img/image_rsrc8X1.jpg)

图 5-73 显示了查看提交任务屏幕中的取消事件按钮。

## 5.3.3 分类（Category）

分类是对象的组。我们可以使用分类来过滤对象。这对于管理我们的工作流非常有用。在这个示例中，你将学习：

- 如何创建分类并将对象添加到分类中。
- 使用库搜索对象。
- 导出工作流。

### 创建分类

1. 点击菜单 `Library（库）` > `Category（分类）`。

   ![](img/image_rsrc8X2.jpg)

   图 5-74 显示了库菜单中的分类菜单。

2. 点击新建（new）按钮并输入名称“BookExample”。

   ![](img/image_rsrc8X3.jpg)

   图 5-75 显示了新建按钮。

### 将对象添加到分类

选择我们的流程和脚本并添加分类。

- 流程（Process）
  - 在画布上点击右键。
  - 选择属性（properties）并选择标签页：`category（分类）`。
  - 选择“BookExample”并点击添加按钮。
- 节点（`Activity`、`Automated`、`Server Automated`、`Delay`、`Transition`）：你不需要操作，它将遵循流程的分类。
- 节点或转换内部的脚本
  - 编辑脚本。
  - 选择标签页 `category（分类）`。
  - 选择“BookExample”并点击添加按钮。

![](img/image_rsrc8X4.jpg)

图 5-76 显示了脚本的分类。

### 按分类过滤

在我们添加分类后，我们可以在转换的条件或节点的代理人（agents）中进行过滤。

![](img/image_rsrc8X5.jpg)

图 5-77 显示了用于过滤的分类按钮。

### 导出工作流

我们可以导出工作流并导入到 UAT 或生产环境。

- 选择菜单 `File（文件）` > `Export（导出）`。
- 输入文件名并点击下一步。
- 你可以使用分类进行过滤。
- 我们通常导出我们选择的对象：`Category（分类）`、`Process（流程）` 和 `Script（脚本）`。

![](img/image_rsrc8X6.jpg)

图 5-78 显示了导出菜单和按分类过滤的导出屏幕。

请查看附录 A，我们有关于导入工作流的详情。

## 5.4 工作点编程（WorkPoint Programming）

现在你学习了一些 Workpoint 示例。这一部分在你学习了一些示例代码后，包含额外的概念。

### 5.4.1 `Activity`、`Server Automated` 和 `Automated`

有 3 种节点：`Activity` ![](img/image_rsrc8X7.jpg)、`Server Automated` ![](img/image_rsrc8V8.jpg) 和 `Automated` ![](img/image_rsrc8V7.jpg)。我们有 3 种活动、自动化和服务器自动化的类型。在“常规（general）”标签页中有复选框。下面的图片显示了复选框与节点类型之间的关系。

![](img/image_rsrc8X8.jpg)

图 5-79 显示了复选框与节点类型之间的关系。

### 5.4.2 `Server Automated` 和 `Automated` 的脚本

`Server Automated` ![](img/image_rsrc8V8.jpg) 和 `Automated` ![](img/image_rsrc8V7.jpg) 的脚本是不同的。如果你使用节点 `Automate` 来实现业务逻辑，你必须编写额外的代码通过代码完成活动。下面的图片显示我们使用了 Automate 节点“Check City Value”，在逻辑完成后流程没有继续移动。

![](img/image_rsrc8X9.jpg)

图 5-80 显示流程停止在自动化节点且不再移动。

我们可以通过添加代码完成活动来修复上面的图片。

```java
public void completeActivity(ClientContext cc,ActivityInstData ad,SymbolTable st) throws Exception{
    short workitem = Short.parseShort((String)st.getSymbol("WorkItemIteration").getPrimaryValue());
    WorkItemEntry workItemEntry = WorkItemEntry.queryByID(cc, ad.getActivityInstID(),workitem);
    short currentState = workItemEntry.getWorkStateID();
    if (currentState == WorkItemConst.WORK_STATE_AVAILABLE) {
        workItemEntry.changeState(WorkItemConst.WORK_STATE_OPEN);
    }
    workItemEntry.changeState(WorkItemConst.WORK_STATE_COMPLETE);
}
```

**注意 3：使用服务器自动化实现业务逻辑。（推荐）**

关于这个主题，我们建议使用服务器自动化。你不需要担心完成活动。

### 5.4.3 （此处重复标题）

`Server Automated` ![](img/image_rsrc8V8.jpg) 和 `Automated` ![](img/image_rsrc8V7.jpg) 的脚本是不同的。如果你使用节点 `Automate` 实现业务逻辑，你必须编写额外的代码通过代码完成活动。下面的图片显示我们使用了 Automate 节点“Check City Value”，在逻辑完成后流程没有继续移动。

![](img/image_rsrc8X9.jpg)

图 5-80 显示流程停止在自动化节点且不再移动。

我们可以通过添加代码完成活动来修复上面的图片。

```java
public void completeActivity(ClientContext cc,ActivityInstData ad,SymbolTable st) throws Exception{
    short workitem = Short.parseShort((String)st.getSymbol("WorkItemIteration").getPrimaryValue());
    WorkItemEntry workItemEntry = WorkItemEntry.queryByID(cc, ad.getActivityInstID(),workitem);
    short currentState = workItemEntry.getWorkStateID();
    if (currentState == WorkItemConst.WORK_STATE_AVAILABLE) {
        workItemEntry.changeState(WorkItemConst.WORK_STATE_OPEN);
    }
    workItemEntry.changeState(WorkItemConst.WORK_STATE_COMPLETE);
}
```

**注意 3：使用服务器自动化实现业务逻辑。（推荐）**

关于这个主题，我们建议使用服务器自动化。你不需要担心完成活动。

### 5.4.3 `Server Automated` 和 `Automated` 的脚本

代理脚本可以是同步的（Synchronous）或异步的（Asynchronous）。了解什么是同步或异步：

- 同步脚本意味着脚本的状态规则。



异步脚本意味着脚本的脚本脚本。

| ![](img/image_rsrc8XA.jpg) |
| --- |
| 图 5-81 显示了代理脚本 |

同步脚本与状态更改在同一事务中执行。异步脚本独立执行。需要知道：

- 如果你使用脚本修改`User Data`，脚本必须同步执行。
- 如果你想完成活动，脚本必须异步执行。

注意 4：服务器自动化的代理脚本应指定为同步。

### 5.4.4 保存作业对象 (Saving Objects)

在官方文档：编程指南中，工作流中有一个“保存作业”主题。

什么是保存对象？`Job`是流程的实例。保存作业意味着你想在节点之间共享某些值。例如：

- 你有节点 1 连接节点 2，节点 2 连接节点 3。
- 节点 1 修改值`X=1`
- 节点 3 可以看到`X`

因此我们需要在流程级别的用户数据中声明变量`X`。这与为工作流指定`TASK_LEVEL`的步骤相同。

| ![](img/image_rsrc8XB.jpg) |
| --- |
| 图 5-82 显示了流程属性中的用户数据标签页 |

官方文档告诉开发者在异步时保存`Job`的`User Data`。这需要特殊的代码。

所有同步脚本必须使用`ThisJobData`或`ThisActivityInstData`来获取`User Data`。

当你在异步脚本中保存作业时，必须编写如下代码：

```javascript
var jobTableId = ThisJobData.getJobID();
var job = Job.queryByID(ClientContext,jobTableId,true);
job.setUserData("Test","Pass");
job.save();
```

### 5.4.5 搜索引用 (Search reference)

有时，由于某些引用，你无法删除某些对象。例如，你想删除脚本，但由于引用而报错。你想知道哪个流程或作业使用了该脚本。点击菜单`library` > `scripts`，对`script`点击右键并选择`search references（搜索引用）`或`search dialog（搜索对话框）`。搜索对话框提供了更多选项，如果你想搜索作业，请勾选对话框中的`jobs`选项。

| ![](img/image_rsrc8XD.jpg) |
| --- |
| 图 5-84 显示搜索引用 |

注意 5：在删除流程之前删除相关的作业。

如果你在删除作业之前先删除了进程（process），当你想要删除脚本时会遇到麻烦。你选择脚本并搜索引用；你会看到某些作业引用了脚本。由于你已经删除了进程，你无法访问所有相关的作业。你必须一个一个打开作业并删除每一个作业。

因此，我们建议在删除进程之前删除所有相关的作业。

## 5.5 用例示例

官方 CA IdentityMinder 文档讨论了用例示例。请参阅“Programming Guides › Programming Guide for Java › Workflow API › Workflow API Overview › Use Case Examples”获取完整详细信息。

### 根据`User`对象属性确定工作流方向

`CreateUserEvent`工作流过程中的第一个活动是一个自动化活动，它引出了三个条件条件跳转。每个跳转的条件脚本从事件包含的`User`对象中获取电子邮件（email）属性。工作流过程执行的下一个活动由条件脚本的结果决定，如下所示：

- 跳转`CA.COM SUFFIX`指向一个审批者：HR 经理（HR Manager）。
- 跳转`SECURITY.COM SUFFIX`指向 2 个审批者：HR 经理和 IT 经理（IT Manager）。
- 跳转`EMAIL INVALID`拒绝工作流。

文档提到，在每个跳转中使用条件脚本来获取电子邮件。你可以使用 Java 代码编写跳转的条件。

| ![](img/image_rsrc8XE.jpg) |
| --- |
| 图 5-85 显示了用例的工作流 |

### 在工作流过程中更新 CA IdentityMinder 对象

在在上一个用例示例中，假设跳转`CA.COM SUFFIX`的条件脚本已更新，用于检查电子邮件属性是否为空。如果为空，脚本将根据用户的 ID 和默认后缀`ca.com`构造电子邮件地址。脚本将该地址分配给`User`对象的`email`属性。然后脚本返回`true`，并按照上一个示例中的方式执行跳转。当 CA IdentityMinder 完成事件的执行时，更新后的对象将被保存。

这里有 2 个很有意思的点：

- 跳转`CA.COM SUFFIX`的条件脚本已更新，用于检查电子邮件属性是否为空。
  - 你可以在跳转“CA.COM SUFFIX”的条件脚本内部编写逻辑。
- 脚本将地址分配给`User`对象的`email`属性。
  - 我们可以通过`ProviderAccessor`和`Workflow Context`将地址分配给`email`属性。对于这种情况，我们必须使用`Workflow context`，原因有两个。第一个是`CreateUserEvent`。我的意思是事件完成之前用户尚未被创建。第二个原因是，此工作流需要审批者。如果被拒绝，我们需要考虑结果。

我们计划修改`workflow context`中的`email`属性，你必须在创建管理任务时在`fields`标签页中定义`email`属性。

### 使用第三方数据从工作流过程中验证对象

`CreateUserEvent`工作流过程包含一个自动化活动，该活动从第三方数据库获取新用户的评分。首先，活动脚本调用`Workflow API`获取事件以及事件中的`User`对象。然后，在脚本获取用户评分后，它使用工作流引擎的`API`将评分写入活动的`User Data`中，最后完成活动。引导该活动的跳转脚本随后使用工作流引擎的`API`从`User Data`中检索评分并对其进行评估，以确定工作流过程的后续走向。

我们可以使用服务器自动化（server automated）中的脚本来调用第三方数据。例如，你调用第三方来获取类型并确定路径。

| ![](img/image_rsrc8XF.jpg) |
| --- |
| 图 5-86 显示了工作流调用第三方数据 |

## 5.6 结论

在本章中，你学习了`workflow context API`或如何创建自定义工作流。我们可以将工作流的概念总结为：

创建工作流之前的检查列表：

- 工作流的级别是什么？管理任务级别（admin task level）还是事件级别
- 哪一个工作流？从 3 个默认工作流中选择还是创建一个新的自定义工作流？
- 工作流开始之前是否需要策略（或条件）？
- 审批者使用哪个界面（任务）？
- 谁是审批者？
- 结果是什么？

自定义工作流的规则

- 规则 1：必须以“Start”（开始）节点开始并以“Stop”（停止）节点结束
- 规则 2：在进入 Stop 节点之前必须有`Approve`批准）或`Reject`拒绝）
- 规则 3：`Approver Configuration`审批者配置（如果你需要审批者）
- 规则 4：工作流位于管理任务级别（可选）

自定义工作流的注意事项

- 注意 1：`WorkflowContext`正确调用来自父类（`EventContext`）的方法。
- 注意 2：保持跳转条件的简单。
- 注意 3：使用服务器自动化实现业务逻辑。（建议）
- 注意 4：服务器自动化的`Agent script`应该被指定为同步。
- 注意 5：在删除进程之前删除相关作业。

你可能认为认为`workflow API`很难，我建议你只需记住本章中的规则和注意事项。关于编程细节，请参阅包含大量示例的第二卷书籍。你会熟悉它的。业务逻辑任务处理器（business logic task handler）和工作流在实际项目中非常有用。下一章，我们将介绍其余 API。

# 第 6 章：其他 API

我们学习了用于开发业务逻辑 2 个主要的`API`：同步阶段下的业务逻辑任务处理器和异步阶段下的工作流。本章中的这些 API 是实现目标的工具。

本章中有很多细节。你可能不需要关注所有的 API。我的观点如下表所示：

| API 名称 | 频率 | 用途 |
| :--- | :--- | :--- |
| `Participant Resolver API` | 有时 | 确定审批者 |
| `Event Listener API` | 经常 | 事件发生时执行自定义业务逻辑 |
| `Logical Attribute API` | 罕见 | 在物理和逻辑属性之间转换 |
| `Validation Rules` | 有时 | 验证值 |
| `Email & Notification Rule API` | 有时 | 发送邮件 |
| `Task Execution Web Service` | 有时 | 将管理任务启用 Web 服务 |

## 6.1 Participant Resolver API

`Participant Resolver API`是工作流的一部分。`Participant Resolver API`决定工作流中的参与者。参与者是被授权审批的人员。

如果工作流需要审批（例如 SingleStepApproval），你需要在配置界面选择参与者。

| ![](img/image_rsrc8G.jpg) |
| --- |
| 图 6-1 显示了参与者界面 |

CA IdentityMinder 为参与者提供了配置条件，详情请参官方文档“Types of Participant Resolvers”。当不支持配置条件时，我们需要参与者 API。

### 6.1.1 编程

使用`Participant Resolver API`，你必须创建一个扩展`ParticipantResolverAdapter`的类并重写`resolve()`方法；返回包含参与者列表的。

```
public Vector resolve(ParticipantResolverContext ctx, Hashtable data, String approvalNodeName)
```

工作流传递了 3 个参数。第一个类似于`BLTHContext`或`WorkflowContext`。第二个参数`HashTable`具有键值`TASK_TAG`包含任务名称。最后一个参数字符串包含工作流中的节点名称。

### 6.1.2 代码示例：Participant Resolver API

此示例使用了工作流；SingleStepApproval。SingleStepApproval 工作流有 2 个审批者；主审批者和默认审批者。主审批者调用我们的`ParticipantResolver`代码。对于默认审批者，我们使用管理员。

我们的需求是主审批者是经理或经理是审批者。如果用户没有经理，则使用经理。如果用户没有经理，则跳到默认审批者。

代码

3. 编译我们的 Java 代码：`com.book.idm.etc.MgrOfMgrParticipantResolver`

# 4. 拷贝类（包含包文件夹`com.book.idm.etc`）到文件夹`\<server>\IdentityMinder.ear\custom`

#### 配置：管理控制台

1. 在管理控制台中，点击`Environments`环境。
2. 点击环境名称。
3. 点击`Advanced Settings`高级设置。
4. 点击`Workflow Participant Resolvers`工作流参与者解析器。
5. 点击`new`按钮并按表赋值：

| 字段名称 | 值 | 说明 |
| :--- | :--- | :--- |
| Name | `MgrOfMgrParticipantResolver` | 参与者解析器的名称 |
| Class | `com.book.idm.etc.MgrOfMgrParticipantResolver` | 我们 Java 类名称 |

#### 配置：Identity Manager 用户控制台

1. 以`administrator`登录 Identity Manager 用户控制台。
2. 搜索我们的管理员任务：`Update Location and Ext Number`。
   - 请禁用业务逻辑任务处理器`policy Xpress`或上一个示例中的工作流。
3. 选择标签页`event`并点击`ModifyUserEvent`。
4. 选择非策略策略的工作流：`singleStepApproval`。
   - 对于主审批者：
     - 审批任务下拉菜单，选择`Approve Modify User`。
     - 参与者解析器下拉菜单，选择`Custom: MgrOfMgrParticipantResolver`。
   - 对于默认审批者：
     - 审批任务下拉菜单，选择`Approve Modify User`。
     - 参与者解析器下拉菜单，选择您的`administrator`。

| ![](img/image_rsrc8XH.jpg) |
| :--- |
| 图 6-2 显示了工作流配置 |

#### 工作原理

你必须准备 3 个用户：`user A`、`user B`和`user C`。登录用户数据存储并检查属性`managerID`：

- `User A`的`managerID` = `user B`
- `User B`的`managerID` = `user C`
- `User C`的`managerID` = “”

以`administrator`登录 Identity Manager 用户控制台，选择标签页：`Book Example`。

### 用例 1：修改用户 A，参与者是经理的经理

4. 选择管理员任务：`Update Location and Ext Number`，然后搜索并选择`user A`。修改城市属性并提交管理员任务。
5. 以`user C`登录，你应该能看到审批请求。

### 用例 2：修改用户 B，参与者是经理

1. 再次选择管理员任务：`Update Location and Ext Number`并选择`user B`。修改城市属性并提交管理员任务。
2. 以`user C`登录，你应该能看到审批请求。

### 用例 3：修改用户 C，没有经理

1. 再次选择管理员任务：`Update Location and Ext Number`并选择`user C`。修改城市属性并提交管理员任务。
2. 以`administrator`登录，你应该能看到审批请求。

## 查找经理的经理

我们使用`ProviderAccess`查找经理。获取用户，然后查找属性`managerID`，通过`managerID`搜索经理，以此此类推，直到找到经理的经理。

```java
String userId = ctx.getSubject().getFriendlyName();
User user = ctx.getUserProvider().findUser(userId, null);
String managerID = user.getAttribute("managerID");
User managerUser = ctx.getUserProvider().findUser(managerID, null);
String mgrOfMgrID = managerUser.getAttribute("managerID");
User mgrOfMgrUser = ctx.getUserProvider().findUser(mgrOfMgrID, null);
resolver.add(mgrOfMgrUser);
```

## 添加参与者

代码非常直观。我们创建一个`Vector`对象并将作为参与者的`User`对象添加到该对象中。

```java
Vector resolver = new Vector();
resolver.add(mgrOfMgrUser);
```

## 没有经理的经理

如果用户没有经理的经理，我们将返回经理。

```java
if(mgrOfMgrID == null || mgrOfMgrID.trim().length()==0){
    System.out.println(userId+" has only manager "+managerID);
    resolvers.add(managerUser);
    return resolvers;
}
```

如果没有审批者，直接返回空 vector。

### 6.1.3 用例示例

在官方文档（Programming Guide for Java > Workflow API > Participant Resolver API > Participant Resolver Overview > Use Case Example）中提供了一个用例示例。

### 将组的管理员分配为参与者

每当用户被添加到组`HR`时，都需要工作流审批。`custom participant resolver`将该组的管理员分配为工作流活动中的参与者。当用户被添加到`HR`时，事件`AddToGroupEvent`进入工作流控制范围，在指定的参与者批准活动之前，该活动无法成功完成。

此工作流运行特定事件级别的`AddToGroupEvent`。我们可以编写条件：如果组名等于“HR”，则返回审批者；如果组名不等于“HR”，则返回空 vector。



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。public Vector resolve(ParticipantResolverContext ctx, Hashtable userData, String approvalNodeName) throws Exception {
    Vector resolver = new Vector();
    AddToGroupEvent event = (AddToGroupEvent)ctx.getEvent();
    String groupName = event.getGroup().getFriendlyName();
    if(groupName.equals("HR")){
        resolver = event.getGroup().getAdmins(null);
    }
    return resolver;
}
```

从事件中获取组。我们可以通过`getAdmins()`方法获取该组的管理员。更多详情请参 Java 文档。

## 6.2 事件监听器 API

当`CA IdentityMinder`执行管理员任务时，它会将任务分解为各个组件事件。每个事件代表任务执行期间要执行的特定操作，例如，`CreateUserEvent`是添加新用户。

事件监听器监听特定的事件或一组事件。当事件发生时，事件监听器会执行适用于该事件和当前事件状态的自定义业务逻辑。

### 6.2.1 编程

对于事件监听器 API，你必须创建一个扩展`EventListener`的`java class`。

### 6.2.2 代码示例：事件监听器

我们的示例展示了监听器的生命周期。它使用标准输出。

```java
public void before(EventContext ctx) {
    // 在预审批期间执行自定义逻辑
}
public void approved(EventContext ctx) {
    // 在已批准状态下执行自定义逻辑
}
public void rejected(EventContext ctx) {
    // 在已拒绝状态下执行自定义逻辑
}
public void after(EventContext ctx) {
    // 在执行后执行自定义逻辑
}
public void failed(EventContext ctx) {
    // 在执行状态后执行自定义逻辑
}
```

每个方法返回`EventListenerAdapter`的常量：`BREAK`或`CONTINUE`。一个事件可以有多个监听器。如果返回`BREAK`，意味着不再处理当前状态的后续监听器。如果返回`CONTINUE`，则意味着该事件监听器的处理完成。我的建议是始终返回`CONTINUE`，这不会破坏未来的其他监听器。

1. 以管理员身份登录 Identity Manager 用户控制。

2. 选择标签页：`Book Example`，并选择菜单`Update Location and Ext Number`。

3. 在`Book Example`标签页中选择管理员任务：`Update Location and Ext Number`，然后搜索某些用户。修改城市属性并提交管理员任务。你可以在日志文件中看到消息。该消息不会立即出现，你必须等待事件开始。

```text
| 2013-10-27  INFO  [STDOUT] =============>LifeCycleEventListener:before |
```

4. 以审批者身份登录，你将看到审批任务并点击批准。查看日志文件中的消息。

```text
| 2013-10-27  INFO  [STDOUT] =============>LifeCycleEventListener:approved2013-10-27  INFO  [STDOUT] =============>LifeCycleEventListener:after |
```

### 监听器级别（Listener Level）

我们将监听器级别设置为`ModifyUserEvent`。这意味着我们的程序只监听一种事件类型：`ModifyUserEvent`。如果我们将监听器级别更改为`User`，则意味着它监听所有与用户相关的事件。

| ![](img/image_rsrc8XK.jpg) |
| :---: |
| 图 6-4 显示了事件监听器级别配置 |

如果你选择`*`，则意味着此监听器将监听所有事件。

### 6.2.3 代码示例：事件生成（Event Generating）

事件生成不是监听器的功能，而是上下文（context）的特性。我们的示例将展示如何生成新事件：将用户添加到组。此示例代码需要一个名为“IT”的组。如果你没有该组，可以创建一个新组或修改代码来更改组名。

我们可以通过`EventContext`生成新事件。`EventContext`可以在当前任务中生成次级事件。`EventContext`拥有`generateEvent()`方法。

```text
| void generateEvent(java.lang.String className,java.lang.Object primary,java.lang.Object secondary,java.lang.String workflowID)throws java.lang.Exception
```

第一个参数`className`是为要生成的事件进行实例化的类的全限定名。事件类位于`com.netegrity.ims.events`包中。你可以在 Java 文档中查看详情，但我建议在管理控制台 > Environments > Advance Settings > Event List 查看，那里是最新的。

第二个和第三个参数是`primary`和`secondary`对象，你可以查看上面的图片。最后一个参数是`workflowID`。工作流过程名称（例如`SingleStepApproval`）映射到正在生成的事件。如果你不需要任何工作流，只需传递`null`。

| ![](img/image_rsrc8XM.jpg) |
| :---: |
| 图 6-5 显示了事件列表（Event List） |

此示例显示了如果城市属性 == “new york”，则我们将用户添加到组“IT”。

#### 代码（Code）

1. 编译我们的 Java 代码：`com.book.idm.etc.NewYorkCityEventListener`

2. 将类（包括包文件夹`com.book.idm.etc`）复制到文件夹`\IdentityMinder.ear\custom`

#### 配置（Configuration）

1. 在管理控制台中，点击`Environments`。

2. 点击将使用该事件监听器的环境名称。

3. 点击`Advanced Settings`。

4. 点击`Event Listeners`。

5. 点击`new`按钮并按下表填值。

| 字段名称 | 值 | 说明 |
| :--- | :--- | :--- |
| Name | `NewYorkCityEventListener` | 事件监听器的名称 |
| Class | `com.book.idm.etc.NewYorkCityEventListener` | Java 类的名称 |
| Listener Level | `ModifyUserEvent` | 该类监听的事件 |

6. 点击`Restart Environment`。

#### 配置：Identity Manager 用户控制（Configuration: Identity Manager User Console）

1. 以管理员身份登录 Identity Manager 用户控制。

2. 检查我们的管理员任务名称：`Update Location and Ext Number`：

   * 移除所有业务逻辑任务处理器和 Policy Xpress。
   * 移除上一个示例中的工作流。

#### 工作原理（How it works）

执行管理员任务：`Update Location and Ext Number`。

1. 以管理员身份登录 Identity Manager 用户控制。

2. 在`Book Example`标签页中选择管理员任务：`Update Location and Ext Number`，然后搜索某些用户。将城市属性更改为“New York”并提交管理员任务。

3. 转到已提交的任务并选择详情。你将看到事件“Add user to group”。

| ![](img/image_rsrc8XN.jpg) |
| :---: |
| 图 6-6 显示了生成的事件“Add user to group” |

你可以搜索组“IT”并查看成员关系以检查结果。

### 特定的管理员任务（Specific admin task）

我们通过配置指定事件，通过代码指定管理员任务。我们添加了条件来检查管理员任务标签。

```java
if(!"BookBasicUpdateLocAndExtNo".equalsIgnoreCase(evtCtx.getAdminTask().getTaskTag())){return CONTINUE;}
```

### 事件生成（Event generation）

此代码显示了事件生成：`AddToGroupEvent`。我们查找组`IT`并传递给方法`generateEvent()`。结果是用户被添加到组“IT”。

```java
if(city.equalsIgnoreCase("new york")){Group group = evtCtx.getGroupProvider().findGroup("IT",null);evtCtx.generateEvent("com.netegrity.ims.events.AddToGroupEvent",user,group, null);}
```

### 6.2.4 用例示例（Use Case Examples）

我们查看了官方文档中所有用例示例的代码（Programming Guide for Java > Event Listener > Event Listener API > Use Case Examples）。

#### 将用户添加到 Microsoft Exchange（Add a user to Microsoft Exchange）

当用户成功添加到 Exchange 时，IdentityMinder 调用与`AssignRoleEvent`相关的监听器的`after()`方法。`after()`方法的实现使用 Exchange API 将用户添加。访问 Exchange 需要的信息（`SERVER_NAME`、`ADMIN_ID`、`ADMIN_PASSWORD`等）包含在 IdentityMinder 的自定义属性中。

在`EventListenerAdapter`的`init()`方法中获取自定义属性。参见本章末。

#### 为组分配创建规则（Create a rule for group assignments）

当创建用户时，IdentityMinder 调用与`CreateUserEvent`相关的监听器的`after()`方法。`after()`方法的实现评估用户属性如`Job Title`、`Security Level`和`Department`，将用户分配到一个或多个组。对于每个组分配，实现生成次级事件`AddToGroupEvent`。该次级事件可以接受工作流审批和审计。

在此用例中，你必须通过检查职位来编写条件。如果匹配，你可以生成新事件：`AddToGroupEvent`。这与我们的事件生成示例相同。

### 使用用户数据更新 RDBMS（Update an RDBMS with user data）

假设用户信息如`user ID`、`user name`、`email address`和组成关系存储在 RDBMS 中。每当发生用户级事件（`CreateUserEvent`、`ModifyUserEvent`等）时，必须更新 RDBMS 中的用户记录。事件执行后，IdentityMinder 调用与用户事件相关的监听器的`after()`方法。该方法的实现从传入`init()`方法的 IdentityMinder 环境中检索 RDBMS 连接参数，然后更新 RDBMS 中的用户记录。

我们在`after()`方法中实现更新数据库。在管理控制台配置中，我们选择监听`user`级别。这意味着 Java 类将执行于所有用户的事件（`CreateUserEvent`、`ModifyUserEvent`等）。

### 将事件发布到 JMS 队列（Post events to a JMS queue）

在任何事件成功执行后，IdentityMinder 调用与所有事件相关的监听器的`after()`方法。该监听器将所有事件写入特定的 Java Message Service（JMS）队列。队列的 Java 命名和目录接口（JNDI）名称以及`jndi.properties`文件中的信息可以通过 IdentityMinder 环境的属性进行配置。`after()`方法实现使用 JNDI 信息向队列发布一个简单的对象消息。

这与之前相同，重写方法`after()`并向 JMS 发送消息。在管理控制台中配置时选择`*`，它将在每个事件发生时执行。

## 6.3 逻辑属性 API

逻辑属性 API 用于在逻辑属性（显示在屏幕上）和物理属性（存储用户数据存储中）之间进行转换。逻辑属性处理程序的执行发生在任务处理的同步阶段。

### 逻辑属性

逻辑属性值显示在任务屏幕字段中。逻辑属性名称出现在竖线（`|`）之间。例如，扩展逻辑属性显示为`|Extension|`。

| ![](img/image_rsrc8XP.jpg) |
| :---: |
| 图 6-7 显示了逻辑属性 |

逻辑属性值不直接与数据存储关联或写入数据存储器。它需要通过逻辑属性处理程序进行处理。

### 预定义逻辑属性

CA IdentityMinder 为某些目的预定义了逻辑属性，例如`|passwordConfirm|`、`|oldPassword|`。我们可以使用或对其进行自定义。更多细节请参阅办公文档。

### 物理属性

物理属性是底层数据存储（如 LDAP 用户目录）的属性。如果任务屏幕字段配置了物理属性，则输入字段字段的值将写入数据存储器。

### 6.3.1 编程

创建一个扩展`LogicalAttributeAdapter`的 Java 类并重写方法：

* `public void toLogical(LogicalAttributeContext apiContext) throws java.lang.Exception`
  * 将值从物理属性转换为逻辑属性。

* `public void toPhysical(LogicalAttributeContext apiContext) throws java.lang.Exception`
  * 将值从逻辑属性转换为物理属性。

* `public void initializeOptionList(LogicalAttributeContext apiContext) throws java.lang.Exception`
  * 如果你想将值渲染为列表，则需要实现此方法并返回一个`Vector`作为屏幕上的显示值列表。

* `public void initialize(LogicalAttributeContext apiContext) throws java.lang.Exception`
  * 在创建用户或创建任何对象时，此方法设置属性的初始值。

### 6.3.2 代码示例

我们的示例展示了如何将城市（物理属性）转换为办公室代码（逻辑属性）。屏幕将显示办公室代码。当用户选择办公室代码时，它将把办公室代码的值转换为城市值。

| ![](img/image_rsrc8XR.jpg) |
| :---: |
| 图 6-8 显示了用户更新办公室的屏幕 |

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.OfficeCodeLogicalAttr`

2. 将类（包括包文件夹`com.book.idm.etc`）复制到文件夹`<server>\IdentityMinder.ear\custom`

#### 配置：管理控制台

1. 在管理控制台中，点击`Environments`。

2. 点击将使用逻辑属性的环境名称。

3. 点击`Advanced Settings`。

4. 点击`Logical Attribute Handlers`。

5. 点击新建按钮并输入如下值：

| 字段名称 | 值 | 说明 |
| :--- | :--- | :--- |
| Name | `OfficeCodeLogicalAttr` | 逻辑属性名称 |
| Class | `com.book.idm.etc. OfficeCodeLogicalAttr` | Java 类名 |
| Object Type | `User` | 具有逻辑属性的对象类型 |
| Logical Attributes |  |  |
| Name | `officeCodeList` | 代码中使用的名称。 |
| Attribute Name | `|officeCodeList|` | 在管理员任务屏幕上显示的名称 |
| Option List | `Check` | 告诉 CA IdentityMinder，此属性是列表 |
| Name | `officeCode` | 代码中使用的名称。 |
| Attribute Name | `|officeCode|` | 在管理员任务屏幕上显示的名称 |
| Physical Attributes |  |  |



| Name | `officeCodePhyAttr` | 代码中使用的名称。 |
| --- | --- | --- |
| Attribute Name | `l` | （小写 L）用户存储中城市属性的名称。 |

![](img/image_rsrc8XS.jpg)

图 6-9 显示管理控制台中的逻辑属性配置。

6. 点击 `Restart Environment` 按钮。

#### 配置：Identity Manager 用户控制台

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签 `Roles and Tasks`，并选择菜单 `create admin task`。
3. 创建管理员任务，输入如下值：

| 字段名称 | 值 | 说明 |
| --- | --- | --- |
| Tab: Profile | | |
| Name | `Update Office` | 管理员任务名称 |
| Tag | `BookBasicUpdateOffice` | 管理员任务标签 |
| Description | `Example for Logical Attribute` | 管理员任务描述 |
| Category | `Book Example` | 管理员任务显示的位置。 |
| Category Order | `11` | |
| Category 2 | `Task` | |
| Category 3 | `Basic` | |
| Primary Object | `User` | 我们想更新城市，所以你必须选择对象 `user`，以及操作 `modify`。 |
| Action | `Modify` | |
| 为了测试，你可以禁用某些值。 | | |
| User Synchronization and Account Synchronization: off | | |
| Enable Auditing, Enable Workflow, Enable Web Services: uncheck | | |
| Tab: Search | | |
| Search Screen | `Default User Search` | 搜索用户的屏幕 |

4. 对于 Tab: Tabs：

   - 选择标准标签控制器。
   - 从列表中选择 `Profile(UserProfile)`，并点击符号 `(+)`。
   - 选择屏幕文本字段处的浏览按钮。
   - 点击新建按钮创建新屏幕，并选择标准配置配置界面。
   - 输入值：
     - Name: `Book Example: Update Office`
     - Tag: `BookBasicUpdateOffice`
   - 添加属性：`|officeCode|`
     - Attribute Name: `|officeCode|`
     - Style: `Drop down`
   - 添加属性：`|officeCodeList|`
     - Attribute Name: `|officeCodeList|`
     - Style: `Hidden`
   - 添加属性：`City`
     - Attribute Name: `City`
     - Style: `Hidden`

![](img/image_rsrc8XT.jpg)

图 6-10 显示了各项的配置。

5. 提交以完成任务创建。

将此任务添加到管理员角色。

1. 选择标签 `Roles and Tasks`，并选择菜单 `create admin task`。
2. 选择角色管理器：
   - 选择标签 `task`。
   - 按类别 `Book Example` 过滤。
   - 选择添加任务：`Update Office`。
3. 提交以完成角色修改。

#### 工作原理

执行管理员任务：`Update Office`。

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签 `Book Example`，并选择菜单 `update office`。
3. 搜索用户，屏幕将显示办公室下拉列表。
4. 修改代码属性并提交。

你可以通过登录用户存储器、搜索修改后的用户来检查结果。用户存储中的城市属性为 `l`。

#### 方法：`toLogical()`

该方法将值从物理属性转换为逻辑属性。代码包含三个步骤：

- 第一步：从物理属性获取值。
- 第二步：映射，从物理转换为逻辑。你可以有其他方式进行转换。
- 第三步：将值设置回逻辑属性。

```java
private String ATTR_REFER_PHY = "officeCodePhyAttr";

@Override
public void toLogical(LogicalAttributeContext ctx) throws Exception {
    //获取物理属性值
    String city = ctx.getPhysicalAttributeName(ATTR_REFER_PHY);
    String cityValue = ctx.getPhysicalAttributeValue(city);
    //从物理值到逻辑的映射
    String officeCodeValue = indexPhysicalAsKey.get(cityValue);
    if(officeCodeValue!=null) {
        //设置逻辑值
        String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
        ctx.setLogicalAttributeValue(officeCode, officeCodeValue);
    }
}
```

我们的代码中可以逐步解释：

第一步：当我们进行配置时，从物理属性获取值，变量 `officecodePhyAttr` 链接到用户数据存储中的属性 `l`。

![](img/image_rsrc8XU.jpg)

图 6-11 显示了物理属性的属性映射。

逻辑属性处理器的执行发生在任务处理的同步阶段。如果与第三方系统交互时的响应时间存在问题，可以在 `Pre-approval`（预审批）状态下使用事件监听器来实现相同的目标。

这意味着，如果你想调用第三方来转换属性值，你应该关注响应时间，因为逻辑属性 API 是在同步阶段执行的。

### 步骤 3：最后一行代码将值设置回逻辑属性值

```java
ctx.setLogicalAttributeValue(officeCode, officeCodeValue);
```

#### 方法：`toPhysical()`

该方法是 `toLogical()` 的反操作。步骤相同，但方向相反。

- 步骤 1：查找逻辑属性值。
- 步骤 2：映射，将其转换为物理值。
- 步骤 3：将值设置回物理属性。

```java
@Override
public void toPhysical(LogicalAttributeContext ctx) throws Exception {
    //step 1
    String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
    String officeCodeValue = ctx.getLogicalAttributeValue(officeCode);
    //step 2
    String cityValue = indexLogicalAsKey.get(officeCodeValue);
    //step 3
    String city = ctx.getPhysicalAttributeName(ATTR_REFER_PHY);
    ctx.setPhysicalAttributeValue(city, cityValue);
}
```

#### 管理任务中的属性

我们在屏幕上声明了 3 个字段：

- 2 个逻辑属性：`officeCode`（下拉列表）和 `officeCodeList`（隐藏）对于下拉列表是必须的。
- 1 个物理属性：`City`（城市，隐藏），我们需要它，因为我们要填充城市属性。因此，城市属性必须存在于管理任务上下文中。

#### 方法：`initializeOptionList()`

如果你想为此逻辑属性提供下拉列表，你必须实现此方法。你只需要将向量设置为逻辑属性值。

```java
ctx.setLogicalAttributeMultiValue(officeCodeList,officeCodes);
```

请确保你检查了配置页面中的选项列表。

![](img/image_rsrc8XV.jpg)

图 6-12 显示了选项列表的复选框。

#### 方法：`initialize()`

此方法仅在任务创建时执行，例如创建用户、创建账户。此方法用于逻辑属性的初始值。

对于修改任务，此方法从不执行。我们的示例从未调用过此方法。如果你想执行此方法，必须将操作更改为“create”（创建）（主对象是用户）。然后再次执行此管理任务，你将看到此方法设置了默认值“006NY”。

```java
@Override
public void initialize(LogicalAttributeContext ctx) throws Exception {
    String officeCodeName = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
    String officeCodeValue = ctx.getLogicalAttributeValue(officeCodeName);
    if(officeCodeValue == null || officeCodeValue.trim().length()==0) {
        ctx.setLogicalAttributeValue(officeCodeName, "006NY");
    }
}
```

#### 方法：`validate()`

`validate()` 方法将在用户提交任务时执行。你可以通过选择空值并点击提交来测试我们的代码。

```java
@Override
public void validate(LogicalAttributeContext ctx) throws Exception {
    String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
    String officeCodeValue = ctx.getLogicalAttributeValue(officeCode);
    if(officeCodeValue==null || officeCodeValue.trim().length()==0) {
        IMSException e = new IMSException();
        e.addUserMessage("Invalid office value");
        throw e;
    }
}
```

![](img/image_rsrc8XW.jpg)

图 6-13 显示了 `validate()` 方法执行期间异常。

#### 屏幕定义的逻辑属性 vs 我们的逻辑属性

当你创建屏幕时，可以创建屏幕定义的逻辑属性。屏幕定义的逻辑属性仅针对一个屏幕定义。它们不能与其他屏幕共享，但逻辑属性是可以共享的。

### 6.3.3 用例

请参考官方文档：Programming guide > Logical Attribute > Use Case Examples。

##### 从数据源格式化数据

在用户目录中，电话号码存储在物理属性 `phone` 中。它有 10 位数字——例如 `9785551212`。此物理属性与逻辑属性 `formatted_phone` 关联。

此用例需要重写 `toLogical()` 以返回格式化后的电话，并重写方法 `toPhysical()` 以从格式化后的电话转换为数字。

```java
@Override
public void toLogical(LogicalAttributeContext ctx) throws Exception {
    //step 1
    String empNo = ctx.getPhysicalAttributeName("employeeNumber");
    String empNoValue = ctx.getPhysicalAttributeValue(empNo);
    //step2
    String validEmpNoValue = queryByPhysicalID(validEmpNoValue);
    // step 3
    if(empNo!=null) {
        String validEmpNo = ctx.getLogicalAttributeName("validEmployeeValue");
        ctx.setLogicalAttributeValue(validEmpNo, validEmpNoValue);
        return;
    }
    throw new IMSException("invalid employee number");
}
```

##### 验证数据输入

物理属性 `employeeNumber` 存在于数据源中，并映射到逻辑属性 `validEmployeeNumber`。当用户在任务屏幕上的 `validEmployeeNumber` 属性分配员工编号并点击提交后，CA IdentityMinder 会调用自定义逻辑属性处理器进行查询，以确保该员工编号在数据源中。如果不存在，将抛出异常。

##### 为任务屏幕添加下拉列表

此用例要求用户提供他们购买的服务类型——Gold（金）、Silver（银）或 Bronze（铜）。这些选项以下拉列表的形式呈现。此用例与我们的示例相同。你需要实现 `initializeOptionList()` 返回服务类型 Gold、Silver 或 Bronze。

## 6.4 验证规则

属性验证规则有助于验证用户在屏幕上输入的值是否符合格式。用户输入可以是正则表达式、JavaScript 或 Java 实现。本书将重点关注 Java 编程。对于正则表达式和 JavaScript，可以查看官方文档示例（但缺少 Java 编程验证规则）。

##### 验证规则类型

- 任务级验证：直接针对特定任务屏幕的验证规则。你可以在任务配置期间定义规则。
- 目录级验证：验证属性值，但应用于所有任务。它是全局范围的。你需要在 `directory.xml` 中定义规则。

### 6.4.1 编程

对于任务级验证，你需要实现 `TaskValidator` 并重写 `validate()` 方法。

```java
public boolean validate(BLTHContext ctx, String attrValue, StringRef changedValue, StringRef errorMsg) throws AttributeValidationException
```

对于目录级验证，你需要扩展 `AttributeValidator` 并重写 `validate()` 方法。它与任务验证几乎相同，但有一些细节。你将在我们的示例中看到。

```java
public boolean validate(Object attrValue, StringRef changedValue, StringRef errorMsg) throws AttributeValidationException
```

### 6.4.2 代码示例：任务级验证

此示例需要 Employee Number 属性，请检查你的用户存储。我们的需求使用的是员工编号属性。验证规则为：

- 员工编号必须是数字。
- 最大 4 位。
- 如果用户输入 1-3 位，格式将填充 `0` 作为前缀。例如：2，正确的格式将是 `0002`。

![](img/image_rsrc8XX.jpg)

图 6-14 显示了更新员工编号的用户屏幕。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.EmployeeNumberTaskValidator`。
2. 将类（包括包文件夹 `com.book.idm.etc`）复制到 `\IdentityMinder.ear\custom` 文件夹中。

# 配置：身份管理器用户控制台

1. 以管理员身份登录身份管理器用户控制台。
2. 选择 `Roles`（角色）和 `Tasks`（任务）选项卡，选择菜单 `create admin task`（创建管理员任务）。
3. 创建 `admin task`，输入如下值：

| 字段名称 | 值 | 描述 |
| --- | --- | --- |
| **Tab: Profile（标签页：配置）** | | |
| Name | `Update Employee Number` | 管理员任务名称 |
| Tag | `BookBasicUpdateEmployeeNumber` | 管理员任务标签名称 |
| Description | `Example for Validation` | 任务描述 |
| Category | `Book Example` | 任务显示的位置。 |
| Category Order | `11` | |
| Category 2 | `Task` | |
| Category 3 | `Basic` | |



| Primary Object | User | 我们想更新员工编号，因此必须选择对象`user`（用户）和操作`modify`（修改）。 |
|---|---|---|
| Action | Modify | |
| | | 为了测试，你可以禁用某些值。<br>* `User Synchronization` 和 `Account Synchronization`：关闭。<br>* `Enable Auditing`、`Enable Workflow`、`Enable Web Services`：取消勾选。 |
| **Tab: Search（标签页：搜索）** | | |
| Search Screen | Default User Search | 搜索用户的界面 |

##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。4. 对于 `Tab: Tabs`（标签页：标签）

- 选择标准标签控制器。
- 从列表中选择`Profile(UserProfile)`，并点击符号`+`。
- 点击屏幕文本字段处的浏览按钮。
- 点击`new`按钮创建新界面，并选择标准配置配置界面。
- 输入值：
  - `Name`：`Update Employee Number`
  - `Tag`：`BookBasicUpdateEmployeeNumber`
- 添加属性：`Employee Number`
  - `Attribute Name`：`Employee Number`
  - `Style`：`Text`
  - `Name`：`Employee Number`
  - `Validation Java Class`：`com.book.idm.etc.EmployeeNumberTaskValidator`
- 点击`apply`按钮完成。
- 点击`ok`。

![](img/image_rsrc8XY.jpg)

图 6-15 显示了员工编号属性的配置。

5. 提交完成任务创建。

## 将任务添加到管理员角色

1. 选择选项卡：`Roles`和`Tasks`，选择菜单`modify admin role`。
2. 选择角色`system manager`。
   - 选择选项卡：`task`。
   - 按分类过滤：`Book Example`。
   - 选择添加任务：`Update Employee Number`。
3. 点击`submit`完成管理员角色的修改。

#### 工作原理

执行管理员任务：`Update employee number`。

1. 以管理员身份登录身份管理器用户控制台。
2. 选择选项卡：`Book Example`，选择菜单`update employee number`。
3. 搜索一个用户，屏幕将显示员工编号的文本字段。
4. 修改员工编号属性，并点击`submit`。

#### 方法`validate()`

有 2 种错误情况：

- 输入了 5 位员工编号。

![](img/image_rsrc8XZ.jpg)

图 6-16 显示了通过返回值的错误。

- 输入了任意字符。

![](img/image_rsrc8Y0.jpg)

图 6-17 显示了通过异常的错误。

有 2 种返回错误消息的方法，你可以选择一种：

- 返回`false`并通过`errorMsg.reference`设置消息。

```java
if(attrValue.trim().length()>4){errorMsg.reference = "Employeer Number can not more than 4 digits";return false;}
```

- 抛出异常并将消息作为参数。

```java
try{...int employeeNo = new Integer(attrValue);...}catch(Exception e){throw new AttributeValidationException("Employeer Number:invalid format");}
```

尝试输入一个数字，例如`1`，并提交。登录用户存储库，员工编号将显示为`0001`。我们可以使用`changedValue.reference`参数修改值。

```java
int employeeNo = new Integer(attrValue);DecimalFormat format = new DecimalFormat("0000");changedValue.reference = format.format(employeeNo);
```

任务级验证提供了`BLTHContext`作为参数。你可以使用`BLTHContext`从托管对象中搜索某些属性，例如你必须检查新值必须是唯一的。

### 6.4.3 代码示例：目录级验证

此示例将使用与任务级验证相同的需求。请从管理员任务`update employee number`中禁用任务级验证。

- 搜索管理员任务：`update employee number`。
- 转到选项卡：`tabs`并修改界面：`Update Employee Number`。
- 移除验证 Java 类的值：`com.book.idm.etc.EmployeeNumberTaskValidator`。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.EmployeeNumberDirValidator`。
2. 将类（包括包`com.book.idm.etc`）复制到文件夹`\IdentityMinder.ear\custom`。

#### 配置：管理控制台

1. 在管理控制台中，点击`Directory`。
2. 点击用户存储目录的名称。
3. 点击底部的`export`按钮。你会得到一个`xml`文件。
4. 使用文本编辑器打开`xml`文件。
5. 你需要修改 2 个地方：
   - 在元素`<ImsManagedObjectAttrValidation>`下添加验证规则。请查阅官方文档检查 XML 架构。

```xml
<ValidationRule name="Employee Number pattern" description="Validates employee number" messageid="4002"><Java class="com.book.idm.etc.EmployeeNumberDirValidator"/></ValidationRule><ValidationRuleSet name="Employee Number format"description="validate employee number format"><ValidationRule name="Employee Number pattern"/></ValidationRuleSet>
```

   - 5.2 为`employeeNumber`添加属性`validationruleset =”Employee Number format"`。

```xml
<ImsManagedObjectAttrValidation physicalname="Employee Number"description="Employee Number"valuetype="String"maxlength="0"validationruleset="Employee Number format"/>
```

6. 返回用户存储库。
7. 点击`next`并选择我们的`xml`文件。

#### 工作原理

执行管理员任务：`Update employee number`。

1. 以管理员身份登录身份管理器用户控制台。
2. 选择选项卡：`Book Example`，选择菜单`update employee number`。
3. 搜索一个用户，屏幕将显示员工编号的文本字段。
4. 修改员工编号属性，并点击`submit`。

#### 方法`validate()`

有 2 种显示错误的方法。这与任务级验证几乎相同，区别在于如何获取消息：

- 如果你返回`false`，则不需要设置消息。消息来自`xml`文件。
- 如果你抛出异常，消息来自属性文件：`IMSException.properties`。

```java
try{...}catch(Exception e){throw new AttributeValidationException("Employee Number",attrValue.toString(),"4002","invalid format");}
```

![](img/image_rsrc8Y1.jpg)

图 6-18 显示了来自`IMSException.properties`文件的`messageid`。

## 规则集

在管理控制台中，点击用户存储目录。向下滚动直到规则集部分。点击内部链接，即可看到详情。

![](img/image_rsrc8Y2.jpg)

图 6-19 显示了管理控制台中的设置。

测试后禁用目录级验证。我们将在第二本书中使用员工编号。

## 6.5 邮件通知

本节是一个特殊主题。它是下一个 API：`Notification Rule API`的。CA IdentityMinder 官方文档在管理指南中有邮件通知主题，而不是在编程指南中。

### 配置 SMTP

在启动邮件通知之前，你需要检查 SMTP 配置。在处理邮件通知之前要检查两项。第一项是 SMTP 配置，即 SMTP 服务器：

- Jboss：检查`jboss_home\server\default\deploy\mail-service.xml`。
- WebLogic：检查 JNDI 名称为`nete/Mail`的邮件会话。
- WebSphere：检查名为`mailMail`的邮件会话对象。

请参官方文档管理指南 > email notifications > configure SMTP Setting。

第二项是`iam_im.ear\config\com\netegrity\config`文件夹下的`email.properties`文件。该文件用于特定的发件人地址。

有 2+1 种实现电子邮件通知的方法。官方文档介绍了 2 种发送邮件的方法。本书提供了另一种发送邮件的方法。

## 1. 邮件通知策略

- 无需编码即可创建电子邮件通知。
- 邮件通知策略是`Policy Xpress`策略。你可以创建策略何时应该运行的条件（入口规则）。
- 位于`System`选项卡下，选择`Email`菜单。

## 2. 邮件模板

- 需要代码（`JSP/java`语法）。
- 支持动态内容（在内容中包含 if-else 条件判断）。
- 支持`Notification Rule API`。

邮件通知策略和邮件模板都依赖于任务的完成或事件的结果（通过、拒绝或失败）。你不能在任何随想的时间发送邮件。例如，你可能有很长的流程步骤：

- 步骤 1：HR 员工更新用户的办公室地址。
- 步骤 2：发送邮件提醒经理审批。
- 步骤 3：发送修复工单，然后向 HR 员工发送关于工单号的邮件。
- 步骤 4：向设施系统发送 Web 服务请求以申请访问办公室的权限。Web 服务响应成功后向 HR 员工发送邮件。如果请求失败，向 IT 管理员发送邮件。
- 步骤 5：等待到预期的入职日期，发送邮件确认用户和 HR 员工。

对于长流程，你必须分析何时需要通知邮件。本书有一个通过`java` API 发送邮件的技巧。

## 3. 服务 API

- 可以随时发送邮件。
- 支持动态内容。你可以使用任何流行的框架，如`velocity`。
- 请注意，`CA IdentityMinder`文档未提到这种方法。请自担风险使用。

### 6.5.2 代码示例：邮件模板

此示例展示了如何实现邮件模板。理解邮件模板对于下一个主题`Notification Rule API`是必须的。我们的示例代码将在管理员成功执行管理员任务：`Update Location and Ext Number`后发送邮件。

#### 代码

1. 定位文件`Update Location and Ext Number.tmpl`。
2. 将文件拷贝到文件夹`<server>\IdentityMinder.ear\custom\emailTemplates\default\completed`。

#### 配置：管理控制台

1. 在`Management Console`中，点击`Environments`。
2. 点击环境名称。
3. 点击`Advanced Settings`。
4. 点击`Email`。
5. 勾选选择框`Tasks e-mail enabled`。

![](img/image_rsrc8Y3.jpg)

图 6-20 显示任务邮件启用配置。

6. 向下滚动直到看到`Send e-mail when the following tasks are completed or during workflow`。
   - 在`Admin Task Name`中，从下拉列表中选择`Equal`并输入值：`Update Location and Ext Number`。
   - `Update Location and Ext Number`将显示在搜索结果中。选中该任务复选框并点击添加按钮。
   - 你应该在任务表中看到任务`Update Location and Ext Number`。

![](img/image_rsrc8Y4.jpg)

图 6-21 显示为邮件模板添加任务。

7. 点击保存按钮。
8. 点击`Restart Environment`按钮。

#### 工作原理

执行管理员任务：`Update Location and Ext Number`。

1. 以管理员身份登录`Identity Manager User Console`。
2. 选择选项卡：`Book Example`，并选择菜单`Update Location and Ext Number`。
3. 搜索一个用户，屏幕将显示城市下拉列表。
4. 修改城市属性并点击提交。

### 接收邮件

在管理员提交后，用户应该收到内容如下所示的邮件：

![](img/image_rsrc8Y5.jpg)

图 6-22 显示邮件内容。

打开文件`Update Location and Ext Number.tmpl`，你将看到邮件内容的代码。它们有特殊的变量，如`_to`或`_taskContextInformation`。`_to`表示邮件的接收者。我们将在`notification rule API`中涵盖更多细节。`_taskContextInformation`是任务上下文。有关更多详情请参阅管理指南。

```java
<%_to = _util.getNotifiers("USER", "");_cc = "";_bcc = "" ;_subject = "Update Location and Ext Number";%>User:<%var imsEventContexts  = _taskContextInformation.getExposedEventContexts();if(imsEventContexts != null){var eventContext = imsEventContexts.get(0);template.add(eventContext.getPrimaryObjectName());}%>has been updated location and ext number successfully.
```

如果你没有收到邮件或屏幕上显示错误，请检查日志文件。`SMTP`可能不正确。

如果你没有收到邮件，但管理员收到了邮件且主题为`Update Location and Ext Number Completed`，这意味着`CA IdentityMinder`使用默认模板：`defaultTask.tmpl`发送邮件。请检查文件夹名称`default/completed`，且管理员任务应与我们的模板名称完全匹配。某些修改可能需要重启服务器或环境。

## 6.5.3 代码示例：通过 Service API 邮件通知

此示例展示了如何通过`CA IdentityMinder`服务发送邮件。我们将使用业务逻辑任务处理器来发送邮件。请禁用上一个示例中的邮件模板。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.SendEmail`。
2. 将类（包括包文件夹`com.book.idm.etc`）拷贝到文件夹`<server>\IdentityMinder.ear\custom`。

### 配置：Identity Manager User Console

1. 以管理员身份登录`Identity Manager User Console`。
2. 选择选项卡：`Roles and Tasks`，并选择管理员任务。
3. 搜索管理员任务：`Update Location and Ext Number`。
4. 点击按钮`Business Handlers`。
5. 点击添加并输入以下值：

| 字段名 | 值 | 描述 |
|---|---|---|
| Name | `SendEmail` | 逻辑处理器名称 |
| Class | `com.book.idm.etc.SendEmail` | Java 类 |

6. 点击确定并提交任务。

#### 工作原理

执行管理员任务：`Update Location and Ext Number`。

1. 以管理员身份登录用户控制台。

### Service API

代码非常直接。你可以通过`sendMail()`方法发送邮件。



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。InternalServiceAccessor.getEmailProvider().sendMail(from,to,cc,bcc,encoding,priority,subject,body);
```

我们可以通过配置 `email.properties` 中的调用 `getAdminEmailID()` 获取管理员邮箱。

```java
String adminEmail = InternalServiceAccessor.getEmailProvider().getAdminEmailID();
String from = adminEmail;
```

我们可以通过 `ProviderAccessor` 获取收件者邮箱（因为管理员任务中不存在邮件属性）。

```java
User user = ctx.getUserProvider().findUser(ctx.getUser().UniqueName(), null);
String toEmail = user.getAttribute("mail");
String to = toEmail;
```

此示例使用业务逻辑任务处理器发送邮件（在任务完成前发送）。如果你想在任务完成后发送邮件，请通过监听器中的 `after()` 方法发送邮件。

## 6.6 Notification Rule API

此 API 仅用于邮件模板。它决定了谁接收邮件通知。

### 6.6.1 编程

你需要创建一个扩展 `NotificationRuleAdapter` 的 Java 类并重写 `evaluate()` 方法。

`public Vector evaluate(NotificationRuleContext ctx, Hashtable templateParams)`

- 将邮件地址放入 `Vector` 对象并返回。第一个参数上下文与其他 API 基本相同。第二个参数 `templateParams` 保留了邮件模板中可能指定的自定义数据键值对。

### 6.6.2 代码示例

此示例需要上一个示例：邮件模板。因此你需要在任务完成时启用邮件模板。我们的需求是当管理员执行管理员任务：`Update Location and Ext Number` 时，必须向用户发送邮件并抄送经理。如果他们没有经理，可以跳过抄送邮件。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.ManagerNotificationRule`。
2. 将类（包括包文件夹 `com.book.idm.etc`）拷贝到文件夹 `<server>\IdentityMinder.ear\custom`。

3. 修改 `email template` 文件夹下的文件 `Update Location and Ext Number.tmpl`。为 `_cc` 添加通知规则名称。

```text
_cc = _util.getNotifiers("ManagerNotificationRule","param1=A,param2=B");
```

#### 配置：控制台（Management Console）

1. 在管理控制台中，点击 `Environments`（环境）。
2. 点击环境名称。
3. 点击 `Advanced Settings`（高级设置）。
4. 点击 `Notification Rules`（通知规则）。

| 字段名称 | 值 | 说明 |
| --- | --- | --- |
| Name | `ManagerNotificationRule` | 通知规则名称 |
| Class | `com.book.idm.etc.ManagerNotificationRule` | Java 类名 |

5. 点击保存并重启环境。

#### 工作原理

执行管理员任务：`Update Location and Ext Number`。

1. 以管理员身份登录 Identity Manager User Console。
2. 选择标签页：Book Example，并选择菜单 `Update Location and Ext Number`。
3. 搜索用户，屏幕将显示城市下拉列表。
4. 修改城市属性并点击提交。

#### 邮件收件者

我们使用 `ProviderAccessor` 查找用户的经理，然后获取属性“mail”，并将电子邮件地址添加到向量中返回。

```java
String emailManager = manager.getAttribute("mail");
if (emailManager != null || emailManager.trim().length() != 0) {
    emails.add(emailManager);
}
```

#### 模板参数

在邮件模板中，我们添加通知规则。

```text
_cc = _util.getNotifiers("ManagerNotificationRule","param1=A,param2=B");
```

`"param1=A,param2=B"` 是模板参数。我们可以从参数 `templateParams` 获取这些值。

```java
public Vector evaluate(NotificationRuleContext ctx, Hashtable templateParams) {
    Enumeration keys = templateParams.keys();
    while (keys.hasMoreElements()) {
        Object key = keys.nextElement();
        System.out.println("parameter: " + key + "=" + templateParams.get(key));
    }
}
```

### 6.6.3 用例

我们在官方文档中实现了用例示例（Programming Guide for Java › Notification Rule API › API Overview > Use Case Examples）。

#### 通知单个用户

当用户数据被修改时，获取用户姓名并根据请求状态抄送（cc）该用户。

编写通知规则代码时，你可以从上下文中获取用户名并添加后缀作为邮件地址。你必须在邮件模板的 `_cc` 中调用通知规则。

```java
String userName = ctx.getSubject().getFriendlyName();
String email = userName + "@somedomain.com";
emails.add(email);
```

#### 通知用户组

当用户被创建并添加到组中时，获取组名（从传递到通知规则的上下文中信息），并关于新组成员抄送（cc）该组。

我们在事件 `AddToGroupEvent` 下编写邮件模板，因此主对象是组。我们获取组名，并将组名作为上下文中信息添加到邮件模板中，然后传递给通知规则。

```java
String groupName = _eventContextInformation.getPrimaryObjectName();
_cc = _util.getNotifiers("NotificationRule","group=" + groupName);
```

### 6.6.4 通知规则与邮件模板的限制及服务 API

关于邮件模板和通知规则存在一些问题：

- 通知规则仅与邮件模板配合工作，对于服务 API 并不是必需的。
- 通知规则的目标是确定邮件收件者。虽然我们可以使用服务 API（`InternalServiceAccessor.getEmailProviderService()`），我们可以访问收件者：`to`、`cc` 和 `bcc`。可以使用上下文搜索邮件属性。
- 邮件模板支持动态内容，但你需要学习新的 JSP 标签库。
- 如果使用邮件模板，可能需要学习新的标签库，例如 `_taskContextInformation`。如果你选择服务 API，可以使用简单的 Java 代码或流行的 Java 框架（如 Apache Velocity）来生成邮件内容。
- 邮件模板在任务或事件（失败、完成等）条件下运行。
- 而服务 API 可以在代码中的任何时间调用。

## 6.7 任务执行 Web 服务（TEWS）

许多人对任务执行 Web 服务感到困惑。任务执行 Web 服务（或称 TEWS）将管理员任务作为 Web 服务的生产者。它不是消费者。TEWS 是一个 Web 服务接口，允许第三方客户端应用程序向 CA IdentityMinder 提交远程任务。

![](img/image_rsrc8Y6.jpg)

图 6-23 显示了 TEWS 如何工作。

### 6.7.1 代码示例

我们开发了一个 Java 客户端来消费 TEWS。我们想通过 Java Web 服务执行管理员任务：`Update Location and Ext Number`。

请禁用所有之前的代码：Policy Xpress、工作流、验证和邮件通知。

#### 配置：控制台

1. 在管理控制台中，点击 `Environments`。
2. 点击使用 Web 服务的环境名称。
3. 点击 `Advanced Settings`。
4. 点击 `Web Services`。
5. 填写如下值：

| 字段名称 | 值 | 说明 |
| --- | --- | --- |
| Enable Execution | Check | 勾选启用该环境的任务执行 Web 服务（TEWS）。 |
| Enable WSDL Generation | Check | 勾选启用该环境的 WSDL 生成。 |
| Enable admin_id | Check | TEWS 使用发送到 Web 服务的 SOAP 消息中的管理员 ID 来验证请求。如果未选择此选项，则使用生成请求的用户 ID 来验证请求。 |
| SiteMinder Authentication | none | 对于身份验证，在我们的示例中我们使用 `none`。 |

![](img/image_rsrc8Y7.jpg)

图 6-24 显示管理控制台。

#### 配置：Identity Manager User Console

1. 登录 User Console。
2. 选择 `Roles` 和 `Tasks`。选择 `Admin Tasks`。
3. 选择 `Update Location and Ext Number`。
4. 选择 `Enable Web Services`。
5. 点击 `Submit` 保存更改。

![](img/image_rsrc8Y8.jpg)

图 6-25 显示管理员任务。

#### 代码

我们通过 BWS 使用 Java 调用管理员任务：`Update Location and Ext Number`。

```bash
java -cp lib/axis.jar;lib/log4j-1.2.jar;lib/wsdlj-1.5.jar;lib/commons-logging-1.0.jar;lib/commons-discovery...../.............................

......................................................................jar;lib/commons-discovery-0.2.jar;lib/jaxrpc.jar;lib/axis.jar;lib/axis.jar;lib/log4j-1.2.jar;lib/wsdl org.axis.wsdl.WSDL2 -wrapArrays=true http://<host>:8080/idm/TEWS?wsdl
```

2. 将生成的代码复制到 eclipse。
3. 在 eclipse 中打开 Java 代码：`com.book.idm.etcClient`。
4. 检查必需参数。

   - `userId` 是你想修改的用户。
   - `adminDN` 是执行此任务的人。我们将详细说明。
   - `City` 和 `extNumber` 是我们想要修改的值。

```java
String userId = "allmi01";
String adminDN = "uid=superuser,ou=users,ou=na,dc=host,dc=com";
String city = "New York";
String extNumber = "1234";
```

#### 工作原理

1. 从 eclipse 中执行我们的 Java 代码：`TEWSClient`。
2. 登录到用户存储目录并检查城市属性。

代码开始的 Java 类名与管理员任务的标签相同：`BookLocAndExtNumber`。该任务代码有两个标签页：搜索标签页和配置标签页。

```java
BookBasicLocAndExtNumber task = new BookLocAndExtNumber();
...
task.setBookLocAndExtNumberSearch(search);
...
task.setBookLocAndExtNumberUserProfileTab(profileTab);
```

对于搜索标签页，我们使用过滤器按 ID 进行搜索。

```java
11.SearchFilter[] filters = new BookBasicLocAndExtNumberSearchFilter[1];
BookBasicLocAndExtNumberSearchFilter filter = new BookBasicLocAndExtNumberSearchFilter();
filter.setIndex(new BigInteger("0"));
filter.setField("%USER_ID%");
filter.setOp(OperatorType.EQUALS);
filter.setValue(userId);
filters[0] = filter;
search.setFilter(filters);
```

我们在配置标签页对象中设置城市和 `extNumber` 属性。

```java
BookBasicLocAndExtNumberUserProfileTab profileTab = new BookBasicLocAndExtNumberUserProfileTab();
profileTab.setL(city);
profileTab.set_BAR_ExtNumber_BAR_(extNumber);
```

在我们的代码中，还有两个额外的文件：`LogHandler.java` 和 `client-config.wsdd`。这些文件是 Axis 客户端日志器的辅助工具。你可以看到服务器和客户端之间的 SOAP 消息。可以使用此 XML 作为 SOAP UI 或任何 Web 服务工具中的请求。

#### SOAP 请求

```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <soapenv:Body>
    <TaskContext xmlns="http://tews6/wsdl">
      <admin_id>uid=superuser,ou=users,ou=na,dc=host,dc=com</admin_id>
    </TaskContext>
    <BookBasicUpdateLocAndExtNo xmlns="http://tews6/wsdl">
      <BookBasicUpdateLocAndExtNoSearch>
        <Filter index="0">
          <Field>%USER_ID%</Field>
          <Op>EQUALS</Op>
          <Value>allmi01</Value>
        </Filter>
      </BookBasicUpdateLocAndExtNoSearch>
      <BookBasicUpdateLocAndExtNoUserProfileTab>
        <l>New York</l>
        <_BAR_ExtNumber_BAR_>1234</_BAR_ExtNumber_BAR_>
      </BookBasicUpdateLocAndExtNoUserProfileTab>
    </BookBasicUpdateLocAndExtNo>
  </soapenv:Body>
</soapenv:Envelope>
```

#### SOAP 响应



```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns="http://tews6/wsdl" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.xmlsoap.org/soap/envelope/ http://schemas.xmlsoap.org/soap/envelope/">
  <soapenv:Body>
    <ImsStatus version="6.0">
      <transactionId>cb40e808-a5029bf5-aeacf1a7-1401ca</transactionId>
    </ImsStatus>
  </soapenv:Body>
</soapenv:Envelope>
```

## 身份验证与授权

在管理控制台中：Web 服务属性中，由于我们检查了 `enable admin_id`（允许身份冒充），我们可以传递任何管理员 DN 作为执行管理员任务的用户。

```java
ctx.setAdmin_id(adminDN);
```

如果你取消勾选 `enable admin_id`（允许身份冒充），则你需要进行身份验证。你必须选择 SiteMinder 身份验证，并修改代码进行身份验证。

```java
Tews6SoapBindingStub stub = (Tews6SoapBindingStub) _port;
stub.setUsername("SuperAdmin");
stub.setPassword("test");
stub.setMaintainSession(true);
stub._setProperty("Cookie", "SMCHALLENGE=YES");
```

对于授权，你可能需要在 `web.xml` 中进行配置。请参考官方文档《Java 编程指南 > 执行 Web 服务 > 授权》。

## 公共任务

当你定义管理员任务时，有一个复选框：`public task`（公共任务）。公共任务意味着对于未登录 CA IdentityMinder 的用户可用。默认的公共任务是忘记密码和自我注册。公共任务可以用于第三方在无需身份验证的情况下从 CA IdentityMinder 查询或获取数据。

![](img/image_rsrc8Y9.jpg)

图 6-26 显示了管理员任务配置中的公共任务复选框。

TEWS 公共任务的客户端代码需要修改 3 个地方：搜索、端口类型和上下文。如果你修改了 `public task` 复选框，需要从 WSDL 重新生成 Java 代码。

对于搜索，你不能使用搜索过滤器。你必须使用搜索主题（search subject），因为公共任务的设计是为了自修改的。

```java
BookBasicUpdateLocAndExtNoSearchSubject[] subjects =
    new BookBasicUpdateLocAndExtNoSearchSubject[1];
BookBasicUpdateLocAndExtNoSearchSubject subject =
    new BookBasicUpdateLocAndExtNoSearchSubject();
subject.setUID("uid=allmi,ou=users,ou=northamerica,dc=server,dc=com");
subject.setIndex(new BigInteger("0"));
subjects[0] = subject;
search.setSubject(subjects);
task.setBookBasicUpdateLocAndExtNoSearch(search);
```

端口类型和上下文必须更改为公共任务。

```java
Tews6PublicPortType portType = locator.getTews6PublicPort();
// Tews6PortType portType = locator.getTews6Port();
PublicTaskContext ctx = new PublicTaskContext();
// TaskContext ctx = new TaskContext();
ctx.setAdmin_id(adminDN);
```

## 6.8 补充概念

### 访问用户自定义属性

业务逻辑任务处理器、逻辑属性、事件监听器等都有自定义属性。

![](img/image_rsrc8YA.jpg)

图 6-27 显示了自定义属性。

我们可以通过重写 `com.netegrity.imapi.LifeCycle` 接口的 `init(java.util.Hashtable imeProperties)` 方法来访问这些属性。你可以将这些值存储在类变量并在其他方法中使用。

```java
@Override
public void init(Hashtable imeProperties) throws Exception {
    System.out.println(imeProperties.get("param1"));
}
```

### 访问托管对象

`EventContext`、`LogicalAttributeContext`、`NotificationRuleContext`、`ParticipantResolverContext` 等扩展了 `ProviderAccessor`。它们可以像 BL（业务逻辑）一样执行或修改托管对象。

`Logger` 类提供了以下方法：

```java
logDebugMessage(String message)
logErrorMessage(String message)
logInfoMessage(String message)
logWarningMessage(String message)
```

## 6.9 总结

在本章中，我们完成了所有的 API。见下表：

| API 名称 | 阶段 | 类型 | 备注 |
| --- | --- | --- | --- |
| Participant Resolver | 确定工作流参与者 | A | 在工作流配置 |
| Event Listener | 监听事件 | A | 事件组 |
| Logical Attribute | 逻辑属性与物理属性之间的转换 | S | 共享；目录级适用于所有 |
| Validation Rule | 验证用户在屏幕上输入的值符合符合格式 | S | 任务级或目录级 |
| Email Notification | 发送邮件 | S 或 A | 收件者和内容 |
| Notification Rule | 决定哪些用户接收邮件 | S | 与邮件模板配合使用 |

建议获取第二卷，其中包含许多高级示例。主要的 API 是业务逻辑任务处理器和工作流。

# 附录 A：导入工作流

从书籍网站下载代码。请使用代码 `120140924`。

## 工作流

- 启动 IdentityMinder Server。
- 运行 WorkPoint Designer。
- 选择文件 > 导入。
- 选择文件 `IdmCodeWorkflow.zip`。
- 选择全部。

![](img/image_rsrc8YB.jpg)

图 A-1 显示导入界面。

- 当屏幕询问是否导入到空数据库时，选择“否”。点击下一步。
- 当屏幕显示此导入将，选择“将所有对象视为新对象”。点击下一步。
- 屏幕询问“如果遇到重复名称或引用”，选择重命名导入的名称或引用以确保唯一。点击下一步。
- 对话框将显示我们导入的代码列表，点击完成。
- 选择打开进程并验证。你应该看到一个以“BookEx.”开头的进程。

![](img/image_rsrc8YC.jpg)

图 A-2 显示了所有流程。

# 附录 B：热部署

CA IdentityMinder 不支持热部署。当你在 `<IdentityMinder>/custom` 文件夹中更新代码时，应用程序服务器将不会加载你的类。有几种解决方法：

## 重启服务器或重新部署 IdentityMinder.ear

在更新代码后，你必须重启或重新部署。这种解决方案非常耗时，不适用于开发过程。

## OSGi

新版本的应用程序支持 OSGi 规范。OSGi 允许在运行时动态加载类。请检查你的应用程序服务器文档。

## 重命名代码

我更喜欢这种方法。它非常简单且不需要时间。CA IdentityMinder 需要两个要素：配置和代码。例如，我的代码是 `MyCode.java`。

- **BLTH**
  - **代码**：我将代码重命名为 `MyCode1.java`，编译并复制到文件夹 `customcustom`。
  - **配置**：更新管理任务中 `BLTH` 的 Java 类名。
- **Workflow**
  - **代码**：我将代码重命名为 `MyCode1.java`，编译并复制到文件夹 `custom`。
  - **配置**：更新节点中的代理脚本。

你也可以在 `Listener` 和其他 API 中执行相同的操作。

# 代码：DGUJK101

```text
DGUJK101
```
