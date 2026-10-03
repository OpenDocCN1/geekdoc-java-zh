
# CA Identity Manager 第一卷：Java 开发者指南：针对 CA Identity Manager R12.6我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。![](img/image_rsrc8PK.jpg)

# 前言

`CA IdentityMinder Volume I: Java Developer's Guide` 将引导你通过 Java 编程来扩展 `CA IdentityMinder` 的功能。你将学习基础管理概念、`CA IdentityMinder` 的 API、如何创建自定义工作流以及相关示例。

我的 `CA IdentityMinder`（原名为 `CA Identity Manager`）编程系列丛由三本书组成：

- `CA Identity Manager Volume I: Java Developer's Guide`，适用于入门级。
- `CA Identity Manager Volume II: Learn by Example Code`，适用于进阶级。
- `CA Identity Manager: Custom Connectors Guide`，适用于自定义连接器开发人员。

请访问书籍网站获取更多详细信息。

## 关于本书

你将学习到：

- `CA IdentityMinder` 管理概念
- `CA IdentityMinder` 编程概念
- 如何开发业务逻辑任务处理程序（Business Logic Task Handler）及示例代码。
- 如何创建自定义工作流（Custom Workflows）及工作流 API 示例代码。
- 如何实现 `Participant Resolver API` 及示例代码。
- 如何实现 `Event Listener API` 及示例代码。
- 如何实现 `Logical Attribute API` 及示例代码。
- 如何实现 `Validation Rules`（验证规则）及示例代码。
- 如何实现 `Email Notification`（邮件通知）及示例代码。
- 如何实现 `Notification Rule API` 及示例代码。
- 如何实现 `Task Execution Web Service (TEWS)`（任务执行 Web 服务）及示例代码。

## 本书对象

本书适用于了解 Java 编程并希望学习通过 API 实现 `CA IdentityMinder` 需求的初学者。

![](img/image_rsrc8PM.jpg)

## 约定

本文使用了以下文本约定：

| 约定 | 含义 |
| :--- | :--- |
| 粗体 | 粗体表示书名 |
| 斜体 | 斜体表示强调或占位符变量 |
| 等宽字体 | 等宽字体表示语言和语法元素 |

## 客户支持

我们欢迎读者的反馈。请告诉我们对本书的看法。请访问网站获取更多详细信息：

- 书籍网站：[`www.caidentitymanagerbook.com`](http://www.caidentitymanagerbook.com)
- 博客及更新内容：[`caidentitymanager.blogspot.com`](http://caidentitymanager.blogspot.com)

如需向我们发送普通反馈或任何问题，只需发送电子邮件。请查看网站上的我的邮箱。

## 下载源代码

请访问我们的网站：[`www.caidentitymanagerbook.com`](http://www.identitymanagerbook.com)

## 商标

`CA IdentityMinder`、`CA Identity Manager` 和 `CA SiteMinder` 是 `CA Technologies` 的注册商标。

| ![](img/image_rsrc8PN.jpg) | 请接受我的歉意：DELAY:我原计划在 2013 年 9 月出版本书，但推迟了近一年。GRAMMAR:请对语法错误向我道歉。审核过程可能需要长达 3 个月。希望我的下一次发布能解决此问题。NO POLICY XPRESS:Policy Xpress 很容易学习。我们可能不需要入门级书籍。EXAMPLES:我知道有些示例可以通过 Policy Xpress 实现，但我通过编程实现了所有示例，因为我想展示如何使用 API。NO BASIC LEVEL:我很歉，某些读者可能会抱怨这本书不适合初学者。我将通过增加奖励章节和视频演示来修复。请访问我的博客。SUPPORT:我是一名全职程序员。我可能无法立即回复您的邮件。请等待 24 小时的回复。我的时区是纽约东部时间 EST。此致，Kosakarika |
| :--- | :--- |
| **关于作者** 我是一名 Java 开发者，住在纽约。经验：<br>* 前端：ExtJS, JQuery, 内容管理(WebSphere Portal), Portlet (WebSphere/Weblogic/SUN Portal)<br>* SOA：Rule JBoss Drools/Guvnor, ESB(ServiceMix/Camel) 和 BPEL(WebSphere Process Server)<br>* IDM 和 SSO：`CA IdentityMinder`、`CA SiteMinder` 和 `SUN Access Manager`。<br>* 实现过多线程、高并发实时经纪项目：<br>* Sun Certified Java Programmer 1.2<br>* Sun Certified Business Component Developer 1.3<br>* IBM Certified Developer - IBM WebSphere Portal Developer V6.1<br>* IBM Certified Developer - Web Services Development for WebSphere V6.1<br>* IBM System Administrator - WebSphere Application Server V6.1<br>* IBM Enterprise Developer - IBM WebSphere Studio V5.0 |

Copyright © 2014 W. Kosakarika

版权所有。未经作者事先书面许可，本书的任何部分不得再复制、存储在检索系统中或以任何形式或通过任何手段传输，但在文章或评论中嵌入的简短引用除外。

在编写本书时，已尽一切努力确保所呈现信息的准确性。然而，本书中包含的信息按无任何保证（无论是明示还是暗示）出售。作者将对本书直接或间接引起或可能引起的任何损害承担责任。

作者已努力通过正确使用大写字母提供书中提到的所有公司和产品的商标信息。然而，作者无法保证这些信息的准确性。

首次出版：2014 年 9 月

# 目录

- 第 1 章 引言
  - 1.1 为什么我们需要自定义代码
  - 1.2 本书涵盖的内容
  - 1.3 技术术语
  - 1.4 `CA IdentityMinder`
  - 1.5 配置
  - 1.6 结论
- 第 2 章 管理
  - 2.1 需求
  - 2.2 创建
    - 2.2.1 配置文件
    - 2.2.2 搜索
    - 2.2.3 角色
    - 2.2.4 标识
  - 2.3 准备
    - 2.3.1 账户
    - 2.3.2 目录
    - 2.3.3 身份
    - 2.3.4 身份
  - 2.4 身份
    - 2.4.1 身份
    - 2.4.2 策略
  - 2.5 如何工作
    - 2.5.1 如何工作
    - 2.5.2 任务
  - 2.6 结论
- 第 3 章 编程概念
  - 3.1 `CA IdentityMinder APIs`
    - 3.1.1 业务逻辑任务处理程序 (BLTH)
    - 3.1.2 工作流 API
    - 3.1.3 参与者解析 API
    - 3.1.4 事件监听器 API
    - 3.1.5 逻辑属性 API
    - 3.1.6 验证规则
    - 3.1.7 邮件通知
    - 3.1.8 规则规则 API
    - 3.1.9 任务执行 Web 服务 (TEWS)
  - 3.2 任务阶段
    - 3.2.1 同步操作
    - 3.2.2 异步操作
  - 3.3 配置 IDE
  - 3.4 结论
- 第 4 章 业务逻辑任务处理程序
  - 4.1 编程和配置概念
    - 4.1.1 编程
    - 4.1.2 配置
  - 4.2 任务会话
  - 4.3 托管对象的访问
  - 4.4 代码示例
    - 4.4.1 基础编程：BLTHAdapter 和生命周期
    - 4.4.2 通过 BLTHContext 修改用户属性
    - 4.4.3 通过 ProviderAccessor 修改用户属性
    - 4.4.5 业务逻辑任务处理器与屏幕。
  - 4.5 用例案例示例
  - 4.6 结论
- 第 5 章 工作流
  - 5.1 工作流概念
    - 5.1.1 默认工作流特性
    - 5.1.2 工作点设计器概念
  - 5.2 自定义工作流
    - 5.2.1 工作流与 `CA IdentityMinder`
    - 5.2.2 工作点组件
  - 5.3 代码示例
    - 5.3.1 工作流：单个审批人
    - 5.3.2 工作流：按城市延迟
    - 5.3.3 分类
  - 5.4 工作点编程
    - 5.4.1 节点、服务器自动化与自动化
    - 5.4.2 服务器自动化与自动化的脚本脚本
    - 5.4.3 代理脚本可以指定为同步或异步。
    - 5.4.4 保存作业对象
    - 5.4.5 引用参考
  - 5.5 用例案例示例
  - 5.6 结论
- 第 6 章：额外 API
  - 6.1 参与者解析器 API
    - 6.1.1 编程
    - 6.1.2 代码示例：参与者解析器 API
    - 6.1.3 用例示例
  - 6.2 事件监听器 API
    - 6.2.1 编程
    - 6.2.2 代码示例：事件监听器 API
    - 6.2.3 代码示例：事件生成
    - 6.2.4 用例示例
  - 6.3 逻辑属性 API
    - 6.3.1 编程
    - 6.3.2 代码示例
    - 6.3.3 用例
  - 6.4 验证规则
    - 6.4.1 编程
    - 6.4.2 代码示例：任务级验证
    - 6.4.3 代码示例：目录级验证
  - 6.5 邮件通知
    - 6.5.1 如何实现邮件通知
    - 6.5.2 代码示例：邮件模板
    - 6.5.3 代码示例：通过 Service API 邮件通知
  - 6.6 通知规则 API
    - 6.6.1 编程
    - 6.6.2 代码示例
    - 6.6.3 用例
      - 6.6.3 通知规则与邮件模板的局限性及 Service API
  - 6.7 任务执行 Web 服务 (TEWS)
    - 6.7.1 代码示例
  - 6.8 额外概念
  - 6.9 结论
- 附录 A：导入工作流
- 附录 B：热部署

# 第 1 章 引言

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

## 1.1 为什么我们需要自定义代码

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

## 1.2 本书涵盖的内容

- 第 1 章：引言
- 第 2 章：管理
- 第 3 章：概念
- 第 4 章：业务逻辑处理器
- 第 5 章：工作流
- 第 6 章：额外 API

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

`CA IdentityMinder` 的核心特性是不需自定义代码即可实现自定义，但在本书中我们将讨论自定义代码。自定义代码有两个原因：

- 处理复杂的业务逻辑。
- 与自定义的外部系统进行集成。

## 1.3 技术术语

这里有一些初学者需要的术语，以避免混淆。

### 端点 (Endpoint)

它是用户数据在配置后的去向地。端点的示例可以是 Microsoft Active Directory、SAP、UNIX 工作站、Windows PC 或应用程序。

### 用户 (User) vs. 全局用户 (Global User) vs. 账户 (Account)

在 `CA IdentityMinder` 中，有两个主要的服务器：`CA IdentityMinder` 配置服务器（我们简称为“配置服务器”）。

用户 (User) 指由 `CA IdentityMinder` 维护的用户信息。用户存储在 `CA IdentityMinder` 用户 Store 中。

全局用户 (Global User) 指由配置服务器维护的用户信息。它存储在 `CA Directory` 中。

账户 (Account) 指端中的用户信息。例如 Active Directory 中的帐户。

下图显示了用户、全局用户和账户之间的关系。某些用户具有相应的全局用户。当用户接收到配置角色时，配置服务器将创建一个全局用户。当服务器启动配置过程时，全局用户中的某些属性将被配置到帐户中。

## 1.4 `CA IdentityMinder` 组件

我们将仅解释与自定义代码相关的组件。

### 服务器

安装 `CA IdentityMinder` 时需要两个服务器：

`CA IdentityMinder Server` 执行 `CA IdentityMinder` 内部的任务。`CA IdentityMinder` 是 Java 台。

配置服务器管理端点系统上的帐户。如果 `CA IdentityMinder` 安装将支持帐户配置，则需要此服务器。

### 用户 Store 和配置目录

`CA IdentityMinder User Store` 是由 `CA IdentityMinder Server` 维护的用户存储。通常，这是一个包含公司需要管理的用户身份的现有存储。

配置目录，是由配置服务器维护的用户存储。它是 `CA Directory` 的一个实例，并包含了全局用户，全局用户将配置目录中的用户与 Microsoft Exchange、Active Directory 和 SAP 等端点上的帐户关联起来。

### 连接器

连接器是与端点的软件接口。`Provisioning Server` 使用连接器与端点通信。它将 `Provisioning Server` 的操作转换为端点上的更改，例如“在 Microsoft Exchange 端点上创建一个新的电子邮件账户”。

`Connector Servers` 是一个管理连接器的服务器组件。连接器服务器有两种类型：

- `CA IAM Connector Server` (`CA IAM CS`) 管理用 `Java` 编写的连接器。
- `C++ Connector Server` (`CCS`) 管理用 `C++` 编写的连接器。

由于连接器和代理程序（Agents），某些连接器需要在其管理的系统中安装一个代理程序以完成通信周期。

`Connector Xpress` 是 `CA IdentityMinder` 的实用程序，用于管理动态连接器、将动态连接器映射到端点以及为端点建立路由规则。你可以使用它配置动态连接器，允许对 SQL 数据库和 LDAP 目录进行配置和服务。

### 其他组件

`WorkPoint` 工作流引擎和 `WorkPoint Designer` 在安装 `CA IdentityMinder` 时会自动安装。这些组件允许你将 `CA IdentityMinder` 任务置于工作流控制下，并修改现有的工作流定义或创建新定义。



`Provisioning Manager`我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。一个管理全局用户和配置服务器选项的图形化界面。你也可以使用 `Provisioning Manager` 来管理端点或账户。

## 1.5 服务器配置

本书假设你已经安装并配置了：

- `CA IdentityMinder` 和用户库。
- `Provisioning Server`、`Provisioning Manager` 和 `Provisioning Directory`。
- `Connector Server`。
- `Workpoint Designer`。

我的建议是配置一个 `Microsoft Active Directory` 端点，配置账户模板和配置服务角色会更好。你应该在 `IDM` 系统中拥有一些用户和账户。

### 用户库属性

在书中，我们要求 `City` 和 `telephone number` 属性作为主要属性，但其他章节还需要额外的属性。我们将创建 3 个管理任务：

- `Update Location and Ext Number`，几乎用于每一个章节。
  - 需要属性：`L`（或 `City`）。
  - 需要属性：`telephoneNumber`。
  - 在第 2 章节中，我们的 `Express` 策略示例需要 `state`。
- `Update Office`，用于第 6 章节：仅限 `Logical Attribute API`。
  - 需要属性：`L`（或与之前的 `City` 相同）。
- `Update Employee Number`，用于第 6 章节：仅限 `Validation Rule`。
  - 需要属性：`employee number`。

请检查 `Management Console`，选择 `Directory` > `User Store`（`Cooperate Store`）> `User` 并检查属性。

| ![](img/image_rsrc8PT.jpg) |
| --- |
| 图 1-4 显示显示名称 |

### 全局用户属性

在 `Management Console` 中，选择 `Directory` > `Provisioning Store` > `Global User` 并检查属性 `Physical Name` 和 `eTCity`。

| ![](img/image_rsrc8PU.jpg) |
| --- |
| 图 1-5 显示 `eTCity` 的显示名称 |

### 属性映射

在 `Management Console` 中，选择 `Environment` > `your environment` > `Advanced Settings` > `Provisioning` 并检查属性映射：`User Attribute` `l` 映射到 `Provisioning Attribute` `eTCity`。

| ![](img/image_rsrc8PV.jpg) |
| --- |
| 图 1-6 显示属性映射 |

## 1.6 结论

我们介绍了自定义代码和服务器配置的优势。在下一章中，你将学习 `CA IdentityMinder` 管理的基本概念。

# 第 2 章 管理概念

如果你熟悉 `CA IdentityMinder`，可以快速跳过本章。在本章中，你将学习：

- 如何创建管理任务。
- 配置（`Provisioning`）是如何工作的。
- `Identity Policy Set` 和 `Policy Xpress` 是如何工作的。
- 理解已提交的任务和事件。

在一个章节中解释所有的管理功能是困难的。我们将只关注与编程相关的部分。如果你是 `CA IdentityMinder` 的新手，可能会因为许多功能而容易迷失。我们将使用 `Admin Task` 作为主要主题。

## 2.1 要求

在本章中，我们将通过管理员工具实现需求。

### 需求

我们的需求需要一个界面来修改 `city`（城市）和分机电话号码（`extension telephone number`）。需求可以写为如下步骤：

- `Step 1`：以管理员身份登录 `Identity Manager User Console`，并选择表单“Update Location and Ext Number”。
  - 从下拉菜单选择 `city`。
  - 填写 `extension number`。
  - 点击 `submit`。
- `Step 2`：系统更新用户属性：
  - 更新 `city` 属性并根据 `city value` 设置 `country`。
  - 拼接 `office number` 和 `extension number`。
- `Step 3`：系统更新账户属性：`city` 和 `telephone number`。

### 设计

我们将通过以下方式实现每个需求的步骤：

- `Step 1`：提供界面。
  - 创建 `Admin Tasks` 和带有 2 个属性的界面：`city` 和 `extension number`。
- `Step 2`：处理。
  - 我们使用 `Policy Set` 将 `city` 映射到 `country`。
  - 我们使用 `Policy Xpress` 拼接 `office number` 和 `extension number`。
- `Step 3`：配置（`Provisioning`）。
  - 配置 `attribute mapping`。
  - 执行 `account synchronization`。

| ![](img/image_rsrc8PW.jpg) |
| --- |
| 图 2-1 显示如何实现需求。 |

## 2.2 创建管理任务

`Admin Tasks` 是主要功能之一。几乎所有的需求都从 `Admin Tasks` 开始。`Admin Task` 是用户在 `CA IdentityMinder` 中可以执行的管理功能。`Admin Tasks` 可以是 `Create User`、`View User`、`Modify User`、`Reset User Password` 等。我们可以在菜单 `home` 或 `users > tasks` 下看到管理任务。

| ![](img/image_rsrc8PX.jpg) |
| --- |
| 图 2-2 显示控制台中的管理任务 |

我们将从创建 `Admin Tasks` 开始。

- 以管理员身份登录 `Admin Console`。
- 点击标签页 `Roles and Tasks` > `Admin Tasks` > `Create Admin Task`。
- 然后选择“Create a new Admin Task”并点击 `OK`。

| ![](img/image_rsrc8PY.jpg) |
| --- |
| 图 2-3 显示管理任务菜单 |

当你选择创建管理任务时，屏幕将显示 5 个标签页（见下文）：

1. `Profile tab` 包含常规信息（`name`）、如何在菜单中显示、什么是主对象和操作（`action`）、`Synchronization` 何时工作以及扩展编程。（注：原文中有处拼写错误）
2. `Search tab` 与 `primary object` 相关；你如何搜索 `primary object`。
3. `Tabs tab` 用于添加任务。
4. `Fields tab` 显示 `admin task` 中有多少个字段。
5. `Events tab` 显示提交管理任务后将生成多少事件。

| ![](img/image_rsrc8PZ.jpg) |
| --- |
| 图 2-4 显示创建任务时的 5 个标签页 |

### 2.2.1 Profile Tab

在 `Profile tab` 中有 5 个部分：

#### 1. General Information

有 3 个字段：

| Field Name | Value | Description |
| :--- | :--- | :--- |
| Name | Update Location and Ext Number | 任务名称将在菜单中显示 |
| Tag | `BasicUpdateLocNo` | 任务的唯一值 |
| Description | Example for Administrative | 描述 |

| ![](img/image_rsrc8R0.jpg) |
| --- |
| 图 2-5 显示菜单上的名称 |

#### 2. 如何在菜单中显示？

`Admin Task` 有界面，所以我们必须决定界面在哪里。有 3 个字段：

| Field Name | Value | Description |
| :--- | :--- | :--- |
| Task Order | 1 | 指定在菜单中的显示顺序 ![](img/image_rsrc8R1.jpg) |
| Category | Book Example | 类别作为标签页显示在屏幕顶部，按数字降序 ![](img/image_rsrc8R2.jpg) |
| Category Order | 11 |  |
| Category 2 | Tasks | 指定第二/三级类别，作为类别标签列表下方的链接出现 ![](img/image_rsrc8R3.jpg) |
| Category 2 Order | 0 |  |
| Category 3 | Basic |  |
| Category 3 Order | 0 |  |

| ![](img/image_rsrc8R4.jpg) |
| --- |
| 图 2-6 显示类别值 |

#### 3. 什么是主对象和操作？

这非常重要。它就像是问题：你想做什么？我想修改用户信息。所以主对象应该是 `user`，操作应该是 `modify`。

| Field Name | Value | Description |
| :--- | :--- | :--- |
| Primary Object | User | 指定任务操作的对象 |
| Action | Modify | 指定在对象上执行的操作 |

本节描述了提交此任务后的同步行为。共有 2 种同步：

- `User Synchronization`（用户同步）：任务将与“设置了身份策略”的用户进行同步。
- `Account Synchronization`（账户同步）：此任务中的任何修改都将与全局用户和账户同步。

有 3 种选择可以指定何时执行同步：

- `None`（无）：什么都不做，不进行同步。
- `On Task completion`（任务完成后）：意味着任务完成后将触发同步。
- `On Every Event`（每个事件）：当任务提交后，会生成许多事件。将在每个事件完成时发生同步。此选项可能会影响性能，因为同步可能会发生多次。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| 用户同步 | 任务完成后 | 任务完成后将与带有“身份策略”的用户进行同步 |
| 账户同步 | 任务完成后 | 任务完成后将同步端点中的账户 |

| ![](img/image_rsrc8R5.jpg) |
| --- |
| 图 2-7 显示了屏幕上的值 |

#### 4. 附加功能

本节中的所有属性在我们编程时都非常有用。我们将在下一章中介绍更多细节。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| 在菜单中隐藏 | 不勾选 | 如果勾选，此任务将不在菜单中显示。 |
| 公共任务 | 不勾选 | 如果勾选，此任务无需登录即可调用 |
| 启用审计 | 勾选 | 如果勾选，在审计数据库中记录此任务 |
| 启用工作流 | 勾选 | 如果勾选，在事件级别启用工作流。 |
| 启用 Web 服务 | 勾选 | 如果勾选，此任务可以通过 Web 服务调用 |
| 工作流流程 | 无 | 如果选择，则支持任务级的工作流。 |
| 任务优先级 | 中级 | 决定执行任务的顺序。 |
| 业务逻辑任务处理器 | 无 | 关联业务逻辑任务处理器。 |

| ![](img/image_rsrc8R6.jpg) |
| --- |
| 图 2-8 显示了屏幕上的值 |

不要提交，选择“Search”（搜索）标签页。

### 2.2.2 Search 标签页

根据您的主对象，某些任务需要搜索屏幕。在 `Profile` 标签页中，我们选择的主对象是“User”（用户），操作是“Modify”（修改）。因此在修改用户之前，我们需要搜索用户以进行修改。如果您的主对象是“NONE”（无），则不需要搜索。

| ![](img/image_rsrc8R7.jpg) |
| --- |
| 图 2-9 显示了示例屏幕：搜索用户 |

在 `Search` 标签页上，点击 `Browse`（浏览），选择屏幕名称：“Default Search Screen”（默认搜索屏幕），类型：“Standard Search Screen”（标准搜索屏幕）。

| ![](img/image_rsrc8R8.jpg) |
| --- |
| 图 2-10 选择屏幕“Default User Search” |

不要提交，点击“Tabs”（标签）标签页进入下一节。

### 2.2.3 Tabs 标签页

在用户屏幕上，一个管理员任务可以有多个标签页。每个标签都有不同的用途。下面的图显示了管理员任务“Modify User”（修改用户）具有 5 个标签的示例。每个标签都有自己的屏幕。

| ![](img/image_rsrc8R9.jpg) |
| --- |
| 图 2-11 显示了管理员 Modify User 中的标签示例 |

在本节中，你必须回答三个问题：

- 是什么类型的标签？
- 此管理员任务内部有多少个标签？
- 每个标签内部的屏幕是什么？

#### 标签类型

有 3 种 `Tab Controller`（标签控制器）：

- `Standard Tab Controller`（标准标签控制器）：每个标签将显示在管理员任务的顶部。我们可以从顶部选择任何标签。
- `Wizard Tab Controller`（向导标签控制器）：它将分步显示，且按钮将为“Next”（下一步）。用户必须检查每个屏幕。
- `Sequence Tab Controller`（顺序标签控制器）：我们在屏幕上看不到任何标签，但用户会看到“Next”（下一步）按钮。

| ![](img/image_rsrc8RA.jpg) |
| --- |
| 图 2-12 显示了标签类型的比较 |

在我们的代码中，我们选择了 `Standard Tab Controller`。

#### 此管理员任务内部有多少个标签？

从下方的下拉菜单添加标签。在我们的示例中，我们要修改用户，所以我们选择了 Profile（`UserProfile`）。

| ![](img/image_rsrc8RB.jpg) |
| --- |
| 图 2-13 显示了如何添加标签 |

#### 每个标签内部的屏幕

每个标签都必须有一个屏幕，我们点击铅笔（`Pencil`）图标来添加屏幕。

| ![](img/image_rsrc8RC.jpg) |
| --- |
| 图 2-14 显示了添加屏幕的“Pencil”图标 |

然后点击 `Browse`（浏览）选择屏幕。

| ![](img/image_rsrc8RD.jpg) |
| --- |
| 图 2-15 显示了选择屏幕的 Browse 按钮 |

我们的原型需要 2 个属性，因此我们需要创建一个新屏幕。所以我们选择“New”（新建）按钮。

| ![](img/image_rsrc8RE.jpg) |
| --- |
| 图 2-16 显示了我们的原型 |

| ![](img/image_rsrc8RF.jpg) |
| --- |
| 图 2-17 显示了如何创建新屏幕 |

然后添加屏幕名称和标签：

| 字段名称 | 值 |
| :--- | :--- |
| Name | Update Location and Ext Number |
| Tag | UpdateLocationandExtNumber |

所以我们在屏幕上需要 2 个属性，点击铅笔图标添加属性。

| ![](img/image_rsrc8RG.jpg) |
| --- |
| 图 2-18 显示了添加属性的铅笔图标 |

第一个是 City Name，链接到用户属性：`city`。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Attribute Name | City | 从用户属性选择 |
| Style | Dropdown | 显示样式 |
| Name | City | 将在屏幕上显示 |
| Source of options | Simple List | 显示样式 |

| ![](img/image_rsrc8RH.jpg) |
| --- |
| 图 2-19 显示了 `city` 属性 |

| ![](img/image_rsrc8JI.jpg) |
| --- |
| 图 2-20 显示了 Ext Number 的值 |

| ![](img/image_rsrc8RK.jpg) |
| --- |
| 图 2-21 显示了选择屏幕 |

| ![](img/image_rsrc8LM.jpg) |
| --- |
| 图 2-22 显示了确认屏幕 |

你已经完成了这一长步骤。然后点击“Fields”（字段）标签页。

### 2.2.4 Fields 标签页

此标签的好消息是，你不需要做什么。你只需要检查字段。你会看到在“Update Location and Ext Number”屏幕中使用的字段 `ExtNumber` 和 `City`。其他属性是主对象所需的。

| ![](img/image_rsrc8RN.jpg) |
| --- |
| 图 2-23 显示了字段标签页 |

然后点击“submit”（提交）。

### 2.2.5 Event 标签页

事件列表在我们创建管理员任务时不会立即显示。它会在提交创建管理员任务后显示。

进入 `Modify Admin Task` 菜单。从下拉菜单选择类别并输入“book”。选择任务“Update Location and Ext Number”并点击 `Select`（选择）按钮。

| ![](img/image_rsrc8RP.jpg) |
| --- |
| 图 2-24 显示了搜索管理员任务屏幕 |



选择 Events 标签，你会看到事件列表。在本章中，我们不我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。事件标签页进行任何操作。

| ![](img/image_rsrc8RR.jpg) |
| --- |

`图 2-25 显示了 Events 标签页`

### 将生成多少事件？

事件的数量和类型取决于主对象、操作和标签。

| ![](img/image_rsrc8RS.jpg) |
| --- |

`图 2-26 显示了事件生成的关系`

### 2.2.6 Role Use 标签页

此标签将显示谁可以使用此管理员任务。现在你什么都没看到。

| ![](img/image_rsrc8RT.jpg) |
| --- |

`图 2-27 显示了 Role Use 标签页`

我们将管理员角色“System Manager”添加到此管理员任务。选择 Roles and Tasks（角色与任务）> Admin Roles（管理员角色）> Modify Admin role（修改管理员角色）> 选择管理员角色“System Manager”并点击 Tasks（任务）标签页。

| ![](img/image_rsrc8RU.jpg) |
| --- |

`角色屏幕`

滚动到屏幕底部，按类别“Book Example”筛选并添加任务“Update Location and Ext Number (BookBasicUpdateLocAndExtNo)”。

| ![](img/image_rsrc8RV.jpg) |
| --- |

`图 2-29 显示了选择我们的任务。`

## 2.3 配置 (Provisioning)

本主题的目标是理解配置的工作原理。实现配置需要以下 4 个配置步骤：

1. 步骤 1：获取端点 (Endpoint)
   - 端点可以是 Microsoft Active Directory 或数据库。
2. 步骤 2：创建账户模板
   - 链接到端点。
   - 账户模板定义了全局用户与账户之间的属性映射。
3. 步骤 3：创建配置角色 (Provisioning Role)
   - 链接到账户模板。
   - 一个配置角色可以拥有多个账户模板。
4. 步骤 4：将用户添加到配置角色

整个步骤如图片所示。

| ![](img/image_rsrc8RW.jpg) |
| --- |

`图 2-30 显示了所有步骤和相关界面。`

### 2.3.1 账户模板与属性映射

账户模板定义了（全局）用户如何在受管端点中被表示。默认情况下，账户模板使用规则字符串（Rule String）定义映射，例如 `%USA%` 或 `%UC%`。您可以在官方文档《管理指南》(Administration Guide)中查看更多详细信息。定义映射有两种方式：

1. 规则字符串：官方文档为某些属性定义了规则字符串，但并非所有属性。
2. 全局用户属性：如果没有规则字符串映射，则可以使用此项。格式为 `%#<attribute name>%`。

例如，账户模板中的城市（city）属性，您可以放置：

- 规则字符串：`%UC%`
- 全局用户属性：`%#eTCity%`

两种方式的结果相同。下图显示了账户模板中全局用户的属性城市值。

| ![](img/image_rsrc8RX.jpg) |
| --- |

`图 2-31 显示了账户模板中的全局用户属性。`

另一个使用全局用户属性的示例是图片中的账户容器（container）。例如，如果 `eTGlobalUser` 具有 `eTLocation=northamerica`，那么容器将是 `eTADSOrgUnitName=Users`、`eTADSOrgUnitName=NorthAmerica`。这些值都是全局用户属性。

| ![](img/image_rsrc8RY.jpg) |
| --- |

`图 2.32 显示了账户模板和全局用户属性界面`

### 2.3.2 配置目录 (Provisioning Directory)

您可以从配置目录获取全局用户属性。您必须使用 LDAP 客户端（如 JXplorer）连接配置目录。您可以从管理控制台（Management Console）获取配置存储信息。选择配置存储并检查 URL。

| ![](img/image_rsrc8RZ.jpg) |
| --- |

`图 2-33 显示了配置目录的连接性。`

#### 全局用户（类：`eTGlobalUser`）

在配置目录内部，浏览到路径 `eTGlobalUserContainerName=Global Users, eTNamespaceName=CommonObjects, dc=im, dc=eta`，这里保留了所有全局用户。

选择一个用户，您可以查看属性名称和值。（您可以在账户模板中使用此属性名称）

| ![](img/image_rsrc8S0.jpg) |
| --- |

`图 2-34 显示了全局用户的路径和属性 `eTCity`。`

#### 账户（类：`eTADAccount`）

如果您已经在端点 Active Directory 中拥有某些账户，请浏览路径 `eTADSDirectoryName=<Endpoint Name>, eTNamespaceName=ActiveDirectory, dc=im, dc=eta`。它代表端点（Active Directory）。

| ![](img/image_rsrc8S1.jpg) |
| --- |

`图 2-35 显示了账户对象的属性`

### 2.3.2 账户详情

`eTADSDirectory` 路径下的对象 `eTADAccount` 代表账户。如果您直接在账户对象 (`eTADAccount`) 中修改某些值，该值将立即反映在 Active Directory 中。例如，我们将 `eTADSl`（代表 City）的值从“New York”更改为“New York Test”，查看 Active Directory，该值也会随之更改。

| ![](img/image_rsrc8S2.jpg) |
| --- |

`图 2-36 显示了 `eTADAccount` 与 AD 账户之间的关系`

我们不建议直接在账户对象 (`eTADAccount`) 内部更改任何值，因为 CA IdentityMinder 将其视为一个内部处理过程。当您进行编程并尝试修改值但遇到错误时，这可能对调试有用。您可以打印该值并直接将其放入账户对象。让我们看看是否允许。

访问全局用户或账户的另一种选择是使用配置管理器 (Provisioning Manager)，但您无法从界面看到属性名称。

### 2.3.3 属性映射：用户 - 全局用户 - 账户

为了更好地理解，本节描述了从用户到全局用户以及从全局用户到账户的属性映射。

#### 用户存储 (User Store)

从管理控制台检查用户存储连接信息，并使用任何 LDAP 客户端（如 JXplorer）登录用户存储。

| ![](img/image_rsrc8S3.jpg) |
| --- |

`图 2.-37 显示了用户存储连接性`

我们可以在管理控制台中查看属性映射：用户属性到全局用户属性的映射。在管理控制台中，选择环境 (Environment) > 您的环境 > 高级设置 (Advanced Settings) > 配置 (Provisioning) > 属性映射 (Attribute Mappings)。

| ![](img/image_rsrc8S4.jpg) |
| --- |

`图 2-38 显示了管理控制台中的属性映射`

下图显示了如何从用户映射城市属性。用户的属性 `l` 通过管理控制台中的属性映射映射到全局用户的属性 `eTCity`。全局用户的属性通过账户模板映射到账户。

| ![](img/image_rsrc8S5.jpg) |
| --- |

`图 2-39 显示了从用户到账户的属性映射`

### 2.3.4 同步 (Synchronization)

我们学习了如何从用户映射属性，下一步我们需要学习它是如何工作的。

#### 创建了全局用户？

当用户拥有配置角色时，将创建全局用户。在我们的示例中，使用默认值 = all。

| ![](img/image_rsrc8S6.jpg) |
| --- |

`图 2-40 显示了何时创建全局用户`

#### 属性同步？

如果您在管理任务的“每个事件”中选择 `账户同步 (Account Synchronization)` 选项，将开始同步。

| ![](img/image_rsrc8S7.jpg) |
| --- |

`图 2-41 显示了账户同步下拉菜单`

#### 什么是用户同步？

管理任务中的 `用户同步 (User Synchronization)` 下拉菜单将触发身份集 (Identity Set)。我们将在下一个主题中讨论身份集。

| ![](img/image_rsrc8S8.jpg) |
| --- |

`图 2-42 显示了用户同步下拉菜单`

## 2.4 身份集 (Identity Set) 与 Policy Xpress

回到我们示例的需求，我们创建了：

- 策略集：将城市映射到国家
- Policy Xpress：拼接办公室号码和分机号。

| ![](img/image_rsrc8S9.jpg) |
| --- |

`图 2-43 显示了如何实现需求。`

### 2.4.1 身份集

身份策略是用户满足某些条件时发生的一系列业务更改。打开 IdentityMinder 管理控制台，选择策略（Policies）选项卡，点击子菜单 `创建身份集 (Create Identity Set)`。

| ![](img/image_rsrc8SA.jpg) |
| --- |

`图 2-44 显示了“创建身份集”菜单`

#### Profile 选项卡

在第一个选项卡 Profile 中，放置以下值：

| 字段名称 | 值 | 描述 |
| --- | --- | --- |
| Name | Set Office Address | 策略集名称 |
| Category | Book Example | 类别名称 |
| Description | Set Office Address | |

不要点击提交，点击策略（Policies）选项卡。

| ![](img/image_rsrc8SB.jpg) |
| --- |

`图 2-45 显示了 Profile 选项卡中的值`

#### Policies 选项卡

此选项卡包含部分：策略集成员规则 (Policy Set Member Rule) 和身份策略 (Identity Policies)。策略集成员规则告诉策略适用于谁？在我们的示例中，我们使用默认值 = all，这意味着所有用户都符合此成员规则。

| ![](img/image_rsrc8SC.jpg) |
| --- |

`图 2-46 显示成员规则 == 所有用户`

接下来，我们需要创建一个身份策略：当城市 = “New York”时设置地址。点击添加 (Add) 按钮，放置值：

| 字段名称 | 值 |
| --- | --- |
| Policy Name | New York Address |
| Policy Condition | |
| City | New York |
| Action on Apply Policy | |
| Country | United States |
| | |

点击“确定”，将返回策略（Policies）界面。

| ![](img/image_rsrc8SH.jpg) |
| --- |

`图 2-47 显示了定义身份策略的界面`

| ![](img/image_rsrc8SJ.jpg) |
| --- |

`图 2-48 显示了策略任务的完成`

为其他城市点击添加按钮。

| 策略名称 | 策略条件 | 应用策略时的操作选择“设置<单值用户属性>为<值>” |
| --- | --- | --- |
| Toronto Address | City =Toronto | Country =Canada |
| Buenos Aires Office | City=Buenos Aires | Country =Argentina |
| Tokyo Office | City=Tokyo | Country =Japan |
| London 办公室 | City=London | Country =United Kingdom |
| 圣保罗办公室 | City=Sao Paulo | Country =Brazil |
| 迪拜办公室 | City=Dubai | Country =UAE |
| 墨尔本办公室 | City=Melbourne | Country =Australia |

点击最后一个标签页“Owners”（所有者）。

#### Owners 标签页

此标签页告诉我们谁可以管理此 `Identity Policy Set`。我们想要添加管理员角色“System Manager”来管理此策略集。

| ![](img/image_rsrc8SK.jpg) |
| --- |

`图 2-49 显示了添加“System Manager”为所有者的界面`

当用户更改城市并提交管理员任务时，`Identity Policy Set` 将评估 `Member Rule`（成员规则）和 `Policy Set`（策略集）。

| ![](img/image_rsrc8SM.jpg) |
| --- |

`图 2-50 显示了 `Identity Policy Set` 的工作。`

`Identity Policy Set` 有一些局限性，因为条件基于用户的属性或角色成员。接下来，我们将创建 `Policy Xpress` 来提供更多功能。

### 2.4.2 Policy Xpress

`Policy Xpress` 允许你在 `CA IdentityMinder` 中创建复杂的业务逻辑（策略），而无需开发自定义代码。`Policy Xpress` 比 `Identity Policy Set` 更灵活。它可以访问逻辑属性并捕获事件。在本节中，我们将创建 `Policy Xpress` 来解决需求。当用户输入扩展分号时，我们将更新电话号码格式为 `<phone number>x<extension number>`。

选择“Policies”（策略）标签页和子菜单“Create Policy Xpress Policy”（创建 Policy Xpress 策略）。选择“Create a new object of type Policy Xpress”（创建一个类型为 Policy Xpress 的新对象）。

| ![](img/image_rsrc8SN.jpg) |
| --- |

`图 2-51 显示了创建 Policy Xpress Policy 的菜单`

#### Profile（配置）标签页

按照下表设置 `Policy Xpress` 的值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| --- | --- | --- |
| Name | Set Telephone Number | 策略名称 |
| Policy Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Category | Book Example | 类别名称 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| --- |

`图 2.52 显示了配置界面的取值`

点击“Events”（事件）标签页。

#### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task`（管理员任务）的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| --- | --- | --- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| --- |

`图 2-53 显示了 `Policy Xpress` 的事件`

#### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`（城市）、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| --- | --- | --- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| --- |

`图 2-54 显示了获取数据的界面：City`

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| --- | --- | --- |
| Name | TelephoneNumber | 数据名称 |



| Category | Attributes | 数据元素组。 |
|---|---|---|
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![图 2-55 获取数据：Telephone 和逻辑属性 `ExtNumber`](img/image_rsrc8ST.jpg)

当完成此步骤后，点击 `Entry Rule`（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![图 2-56 入口规则条件界面](img/image_rsrc8SU.jpg)

完成此步骤并点击 `Action Rules`（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`IF city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

![图 2-57 操作规则条件：New York](img/image_rsrc8SW.jpg)

点击 `Action Rule` 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![图 2.52 配置界面的取值](img/image_rsrc8SP.jpg)

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

![图 2-53 `Policy Xpress` 的事件](img/image_rsrc8SR.jpg)

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![图 2-54 获取数据的界面：City](img/image_rsrc8SS.jpg)

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![图 2-55 获取数据：Telephone 和逻辑属性 `ExtNumber`](img/image_rsrc8ST.jpg)

当完成此步骤后，点击 `Entry Rule`（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![图 2-56 入口规则条件界面](img/image_rsrc8SU.jpg)

完成此步骤并点击 `Action Rules`（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`IF city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

![图 2-57 操作规则条件：New York](img/image_rsrc8SW.jpg)

点击 `Action Rule` 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![图 2.52 配置界面的取值](img/image_rsrc8SP.jpg)

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

![图 2-53 `Policy Xpress` 的事件](img/image_rsrc8SR.jpg)

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![图 2-54 获取数据的界面：City](img/image_rsrc8SS.jpg)

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![图 2-55 获取数据：Telephone 和逻辑属性 `ExtNumber`](img/image_rsrc8ST.jpg)

当完成此步骤后，点击 `Entry Rule`（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![图 2-56 入口规则条件界面](img/image_rsrc8SU.jpg)

完成此步骤并点击 `Action Rules`（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`IF city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

![图 2-57 操作规则条件：New York](img/image_rsrc8SW.jpg)

点击 `Action Rule` 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![图 2.52 配置界面的取值](img/image_rsrc8SP.jpg)

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

![图 2-53 `Policy Xpress` 的事件](img/image_rsrc8SR.jpg)

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![图 2-54 获取数据的界面：City](img/image_rsrc8SS.jpg)

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|---|---|---|
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |



| ![](img/image_rsrc8ST.jpg) |

图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber`。

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |

图 2-56 显示了入口规则条件界面。

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |

图 2-57 显示了操作规则条件：`New York`。

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |

图 2.52 显示了配置界面的取值。

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |

图 2-53 显示了 `Policy Xpress` 的事件。

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |

图 2-54 显示了获取数据的界面：`City`。

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |

图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber`。

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |

图 2-56 显示了入口规则条件界面。

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |

图 2-57 显示了操作规则条件：`New York`。

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |

图 2.52 显示了配置界面的取值。

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |

图 2-53 显示了 `Policy Xpress` 的事件。

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |

图 2-54 显示了获取数据的界面：`City`。

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |

图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber`。

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |

图 2-56 显示了入口规则条件界面。

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |



| 图 2-57 显示了操作规则条件 | `New York` |

点击 `Action Rule` 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `Set Telephone Number` | 策略名称 |
| `Category` | `Book Example` | 类别名称 |
| `Type` | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| `Priority` | `0` | 数字越小，优先级越高 |
| `Enable` | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| `Run Once` | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `State` | `Task completed` | 告诉此 `Policy Xpress` 执行的时机 |
| `Event Name` | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

```
如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号
```

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `City` | 数据名称 |
| `Category` | `Attributes` | 数据元素组。 |
| `Type` | `User Attribute` | 根据所选类别指定数据元素类型 |
| `Function` | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| `Attribute Name` | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| 图 2-54 显示了获取数据的界面：`City` |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `TelephoneNumber` | 数据名称 |
| `Category` | `Attributes` | 数据元素组。 |
| `Type` | `User Attribute` | 指定数据元素类型 |
| `Function` | `Get` | `Get` 函数。 |
| `Attribute Name` | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `ExtensionNumber` | 数据名称 |
| `Category` | `Attributes` | 数据元素组。 |
| `Type` | `User Attribute` | 指定数据元素类型 |
| `Function` | `Get` | `Get` 函数。 |
| `Attribute Name` | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| 图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 `Entry Rule`（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 `Action Rules`（操作规则）标签页

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

```
如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号
```

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| 图 2-57 显示了操作规则条件 | `New York` |

点击 `Action Rule` 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `Set Telephone Number` | 策略名称 |
| `Category` | `Book Example` | 类别名称 |
| `Type` | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| `Priority` | `0` | 数字越小，优先级越高 |
| `Enable` | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| `Run Once` | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `State` | `Task completed` | 告诉此 `Policy Xpress` 执行的时机 |
| `Event Name` | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

```
如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号
```

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `City` | 数据名称 |
| `Category` | `Attributes` | 数据元素组。 |
| `Type` | `User Attribute` | 根据所选类别指定数据元素类型 |
| `Function` | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| `Attribute Name` | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| 图 2-54 显示了获取数据的界面：`City` |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `TelephoneNumber` | 数据名称 |
| `Category` | `Attributes` | 数据元素组。 |
| `Type` | `User Attribute` | 指定数据元素类型 |
| `Function` | `Get` | `Get` 函数。 |
| `Attribute Name` | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `ExtensionNumber` | 数据名称 |
| `Category` | `Attributes` | 数据元素组。 |
| `Type` | `User Attribute` | 指定数据元素类型 |
| `Function` | `Get` | `Get` 函数。 |
| `Attribute Name` | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| 图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 `Entry Rule`（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 `Action Rules`（操作规则）标签页

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

```
如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号
```

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| 图 2-57 显示了操作规则条件 | `New York` |

点击 `Action Rule` 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| `Name` | `Set Telephone Number` | 策略名称 |
| `Category` | `Book Example` | 类别名称 |
| `Type` | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| `Priority` | `0` | 数字越小，优先级越高 |
| `Enable` | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| `Run Once` | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |



| ![](img/image_rsrc8SP.jpg) |
| :---: |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| :---: |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| :---: |
| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| :---: |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| :---: |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| :---: |
| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| :---: |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| :---: |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| :---: |
| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| :---: |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| :---: |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| :---: |
| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| :---: |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| :---: |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| :---: |
| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| :---: |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| :---: |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| :---: |
| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| :---: |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |



| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |
| :--- | :--- | :--- |
| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |
| ![](img/image_rsrc8SS.jpg) |
| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |
| ![](img/image_rsrc8ST.jpg) |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |
| ![](img/image_rsrc8SP.jpg) |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |
| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |



| Name | City | 数据名称 |
|---|---|---|
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持`Get`函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![](img/image_rsrc8SS.jpg)

图 2-54 显示了获取数据的界面：City

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get`函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get`函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![](img/image_rsrc8ST.jpg)

图 2-55 显示了获取数据：Telephone 和逻辑属性`ExtNumber`

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules`是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![](img/image_rsrc8SU.jpg)

图 2-56 显示了入口规则条件界面

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在`Action Rules`中创建`IF` `THEN`：

![](img/image_rsrc8SW.jpg)

图 2-57 显示了操作规则条件 | New York

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的`Policy Xpress`将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在`CA IdentityMinder`中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![](img/image_rsrc8SP.jpg)

图 2.52 显示了配置界面的取值

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress`可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此`Policy Xpress`何时执行。我们希望此`Policy Xpress`在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| State | Task completed | 告诉此`Policy Xpress`执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

![](img/image_rsrc8SR.jpg)

图 2-53 显示了`Policy Xpress`的事件

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number`和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持`Get`函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![](img/image_rsrc8SS.jpg)

图 2-54 显示了获取数据的界面：City

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get`函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | `Get`函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![](img/image_rsrc8ST.jpg)

图 2-55 显示了获取数据：Telephone 和逻辑属性`ExtNumber`

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules`是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![](img/image_rsrc8SU.jpg)

图 2-56 显示了入口规则条件界面

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在`Action Rules`中创建`IF` `THEN`：

![](img/image_rsrc8SW.jpg)

图 2-57 显示了操作规则条件 | New York

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的`Policy Xpress`将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在`CA IdentityMinder`中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![](img/image_rsrc8SP.jpg)

图 2.52 显示了配置界面的取值

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress`可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此`Policy Xpress`何时执行。我们希望此`Policy Xpress`在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| State | Task completed | 告诉此`Policy Xpress`执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

![](img/image_rsrc8SR.jpg)

图 2-53 显示了`Policy Xpress`的事件

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number`和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
|:---|:---|:---|
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持`Get`函数。 |
| Attribute Name | `City (l)` | 必需属性 |



| 伦敦办公室 | City=London | Country =United Kingdom |

| 圣保罗办公室 | City=Sao Paulo | Country =Brazil |

| 迪拜办公室 | City=Dubai | Country =UAE |

| 墨尔本办公室 | City=Melbourne | Country =Australia |

点击最后一个标签页“Owners”（所有者）

### Owners 标签页

此标签页告诉我们谁可以管理此`Identity Policy Set`。我们想要添加管理员角色“System Manager”来管理此策略集。

| ![](img/image_rsrc8SK.jpg) |

| 图 2-49 显示了添加“System Manager”为所有者的界面 |

当用户更改城市并提交管理员任务时，`Identity Policy Set` 将评估`Member Rule`（成员规则）和`Policy Set`（策略集）。

| ![](img/image_rsrc8SM.jpg) |

| 图 2-50 显示了`Identity Policy Set`的工作。 |

`Identity Policy Set` 有一些局限性，因为条件基于用户的属性或角色成员。接下来，我们将创建`Policy Xpress`来提供更多功能。

### 2.4.2 Policy Xpress

`Policy Xpress`允许你在`CA IdentityMinder`中创建复杂的业务逻辑（策略），而无需开发自定义代码。`Policy Xpress`比`Identity Policy Set`更灵活。它可以访问逻辑属性并捕获事件。在本节中，我们将创建`Policy Xpress`来解决需求。当用户输入扩展分号时，我们将更新电话号码格式为`<phone number>x<extension number>`。

选择“Policies”（策略）标签页和子菜单“Create Policy Xpress Policy”（创建 Policy Xpress 策略）。选择“Create a new object of type Policy Xpress”（创建一个类型为 Policy Xpress 的新对象）。

| ![](img/image_rsrc8SN.jpg) |

| 图 2-51 显示了创建 Policy Xpress Policy 的菜单 |

### Profile（配置）标签页

我们按照下表设置`Policy Xpress`的值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| Name | Set Telephone Number | 策略名称 |

| Policy Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的`Policy Xpress`将执行。 |

| Category | Book Example | 类别名称 |

| Priority | 0 | 数字越小，优先级越高 |

| Enable | Check | 此策略在`CA IdentityMinder`中处于激活 |

| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |

| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress`可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此`Policy Xpress`何时执行。我们希望此`Policy Xpress`在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| State | Task completed | 告诉此`Policy Xpress`执行的时机 |

| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |

| 图 2-53 显示了`Policy Xpress`的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number`和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| Name | City | 数据名称 |

| Category | Attributes | 数据元素组。 |

| Type | User Attribute | 根据所选类别指定数据元素类型 |

| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持`Get`函数。 |

| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |

| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| Name | TelephoneNumber | 数据名称 |

| Category | Attributes | 数据元素组。 |

| Type | User Attribute | 指定数据元素类型 |

| Function | Get | Get 函数。 |

| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| Name | ExtensionNumber | 数据名称 |

| Category | Attributes | 数据元素组。 |

| Type | User Attribute | 指定数据元素类型 |

| Function | Get | Get 函数。 |

| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |

| 图 2-55 显示了获取数据：Telephone 和逻辑属性`ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules`是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |

| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在`Action Rules`中创建`IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |

| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| Name | Set Telephone Number | 策略名称 |

| Category | Book Example | 类别名称 |

| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的`Policy Xpress`将执行。 |

| Priority | 0 | 数字越小，优先级越高 |

| Enable | Check | 此策略在`CA IdentityMinder`中处于激活 |

| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |

| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress`可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此`Policy Xpress`何时执行。我们希望此`Policy Xpress`在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |

| :--- | :--- | :--- |

| State | Task completed | 告诉此`Policy Xpress`执行的时机 |

| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |

| 图 2-53 显示了`Policy Xpress`的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：



`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![](img/image_rsrc8SS.jpg)

图 2-54 显示了获取数据的界面：`City`

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `ExtensionNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![](img/image_rsrc8ST.jpg)

图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber`

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![](img/image_rsrc8SU.jpg)

图 2-56 显示了入口规则条件界面

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

![](img/image_rsrc8SW.jpg)

图 2-57 显示了操作规则条件 | New York

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `Set Telephone Number` | 策略名称 |
| Category | `Book Example` | 类别名称 |
| Type | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | `0` | 数字越小，优先级越高 |
| Enable | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![](img/image_rsrc8SP.jpg)

图 2.52 显示了配置界面的取值。

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | `Task completed` | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |

![](img/image_rsrc8SR.jpg)

图 2-53 显示了 `Policy Xpress` 的事件。

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![](img/image_rsrc8SS.jpg)

图 2-54 显示了获取数据的界面：`City`

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `ExtensionNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![](img/image_rsrc8ST.jpg)

图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber`

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![](img/image_rsrc8SU.jpg)

图 2-56 显示了入口规则条件界面

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

![](img/image_rsrc8SW.jpg)

图 2-57 显示了操作规则条件 | New York

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `Set Telephone Number` | 策略名称 |
| Category | `Book Example` | 类别名称 |
| Type | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | `0` | 数字越小，优先级越高 |
| Enable | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![](img/image_rsrc8SP.jpg)

图 2.52 显示了配置界面的取值。

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | `Task completed` | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |

![](img/image_rsrc8SR.jpg)

图 2-53 显示了 `Policy Xpress` 的事件。

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![](img/image_rsrc8SS.jpg)

图 2-54 显示了获取数据的界面：`City`

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `ExtensionNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

![](img/image_rsrc8ST.jpg)

图 2-55 显示了获取数据：`Telephone` 和逻辑属性 `ExtNumber`

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

![](img/image_rsrc8SU.jpg)

图 2-56 显示了入口规则条件界面

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

![](img/image_rsrc8SW.jpg)

图 2-57 显示了操作规则条件 | New York

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `Set Telephone Number` | 策略名称 |
| Category | `Book Example` | 类别名称 |
| Type | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | `0` | 数字越小，优先级越高 |
| Enable | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![](img/image_rsrc8SP.jpg)

图 2.52 显示了配置界面的取值。

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | `Task completed` | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |

![](img/image_rsrc8SR.jpg)

图 2-53 显示了 `Policy Xpress` 的事件。

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

![](img/image_rsrc8SS.jpg)

图 2-54 显示了获取数据的界面：`City`

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | `Get` 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

点击最后一个标签页“Owners”（所有者）。

### Owners 标签页

此标签页告诉我们谁可以管理此 `Identity Policy Set`。我们想要添加管理员角色“System Manager”来管理此策略集。

![](img/image_rsrc8SK.jpg)

图 2-49 显示了添加“System Manager”为所有者的界面。

当用户更改城市并提交管理员任务时，`Identity Policy Set` 将评估 `Member Rule`（成员规则）和 `Policy Set`（策略集）。

![](img/image_rsrc8SM.jpg)

图 2-50 显示了 `Identity Policy Set` 的工作。

`Identity Policy Set` 有一些局限性，因为条件基于用户的属性或角色成员。接下来，我们将创建 `Policy Xpress` 来提供更多功能。

### 2.4.2 Policy Xpress

`Policy Xpress` 允许你在 `CA IdentityMinder` 中创建复杂的业务逻辑（策略），而无需开发自定义代码。`Policy Xpress` 比 `Identity Policy Set` 更灵活。它可以访问逻辑属性并捕获事件。在本节中，我们将创建 `Policy Xpress` 来解决需求。当用户输入扩展分号时，我们将更新电话号码格式为 `<phone number>x<extension number>`。

选择“Policies”（策略）标签页和子菜单“Create Policy Xpress Policy”（创建 Policy Xpress 策略）。选择“Create a new object of type Policy Xpress”（创建一个类型为 Policy Xpress 的新对象）。

![](img/image_rsrc8SN.jpg)

图 2-51 显示了创建 Policy Xpress Policy 的菜单。

### Profile（配置）标签页

我们按照下表设置 `Policy Xpress` 的值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `Set Telephone Number` | 策略名称 |
| Policy Type | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Category | `Book Example` | 类别名称 |
| Priority | `0` | 数字越小，优先级越高 |
| Enable | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

![](img/image_rsrc8SP.jpg)

图 2.52 显示了配置界面的取值。

点击“Events”（事件）标签页。

### Events（事件）标签页



`Policy Xpress` 可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | City | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 根据所选类别指定数据元素类型 |
| Function | Get | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |

| ![](img/image_rsrc8SS.jpg) |
| 图 2-54 显示了获取数据的界面：City |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | TelephoneNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | Business Phone (Telephone Number) | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | ExtensionNumber | 数据名称 |
| Category | Attributes | 数据元素组。 |
| Type | User Attribute | 指定数据元素类型 |
| Function | Get | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |

| ![](img/image_rsrc8ST.jpg) |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| 图 2-57 显示了操作规则条件 | New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | Set Telephone Number | 策略名称 |
| Category | Book Example | 类别名称 |
| Type | Submitted Task | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | 0 | 数字越小，优先级越高 |
| Enable | Check | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | Do not Check | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |

| ![](img/image_rsrc8SP.jpg) |
| 图 2.52 显示了配置界面的取值 |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获`Admin Task`管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | Task completed | 告诉此 `Policy Xpress` 执行的时机 |
| Event Name | Update Location and Ext Number (BookBasicUpdateLocAndExtNo) | 从下拉列表中选择任务名称 |

| ![](img/image_rsrc8SR.jpg) |
| 图 2-53 显示了 `Policy Xpress` 的事件 |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`



因此，我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |
| ![](img/image_rsrc8SS.jpg) |  |  |
| 图 2-54 显示了获取数据的界面：City |  |  |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | Get 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `ExtensionNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |
| ![](img/image_rsrc8ST.jpg) |  |  |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |  |  |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| --- |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| --- |
| 图 2-57 显示了操作规则条件：New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `Set Telephone Number` | 策略名称 |
| Category | `Book Example` | 类别名称 |
| Type | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | `0` | 数字越小，优先级越高 |
| Enable | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |
| ![](img/image_rsrc8SP.jpg) |  |  |
| 图 2.52 显示了配置界面的取值 |  |  |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | `Task completed` | 告诉我们此 `Policy Xpress` 执行的时机 |
| Event Name | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |
| ![](img/image_rsrc8SR.jpg) |  |  |
| 图 2-53 显示了 `Policy Xpress` 的事件 |  |  |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此，我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |
| ![](img/image_rsrc8SS.jpg) |  |  |
| 图 2-54 显示了获取数据的界面：City |  |  |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | Get 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `ExtensionNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |
| ![](img/image_rsrc8ST.jpg) |  |  |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |  |  |

当完成此步骤后，点击 Entry Rule（入口规则）标签页。

### Entry Rules（入口规则）标签页

`Entry Rules` 是主条件。它告诉我们我们感兴趣的内容。我们的示例是对城市值不为空。

| ![](img/image_rsrc8SU.jpg) |
| --- |
| 图 2-56 显示了入口规则条件界面 |

完成此步骤并点击 Action Rules（操作规则）标签页。

### Action Rules（操作规则）标签页

在此标签页中，我们将创建条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

在 `Action Rules` 中创建 `IF` `THEN`：

| ![](img/image_rsrc8SW.jpg) |
| --- |
| 图 2-57 显示了操作规则条件：New York |

点击 Action Rule 按钮，按照下表设置值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `Set Telephone Number` | 策略名称 |
| Category | `Book Example` | 类别名称 |
| Type | `Submitted Task` | 定义触发策略的监听器。当任务提交时，我们的 `Policy Xpress` 将执行。 |
| Priority | `0` | 数字越小，优先级越高 |
| Enable | `Check` | 此策略在 `CA IdentityMinder` 中处于激活 |
| Run Once | `Do not Check` | 指定策略是否仅运行一次。对于我们的策略，不勾选，并在每次符合标准时运行。 |
| ![](img/image_rsrc8SP.jpg) |  |  |
| 图 2.52 显示了配置界面的取值 |  |  |

点击“Events”（事件）标签页。

### Events（事件）标签页

`Policy Xpress` 可以捕获 `Admin Task` 管理员任务的事件，包括 UI 和任务提交。此标签页告诉我们此 `Policy Xpress` 何时执行。我们希望此 `Policy Xpress` 在我们的任务完成时执行，因此我们设置了如下值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| State | `Task completed` | 告诉我们此 `Policy Xpress` 执行的时机 |
| Event Name | `Update Location and Ext Number (BookBasicUpdateLocAndExtNo)` | 从下拉列表中选择任务名称 |
| ![](img/image_rsrc8SR.jpg) |  |  |
| 图 2-53 显示了 `Policy Xpress` 的事件 |  |  |

### Data（数据）标签页

此标签页设计用于获取数据。我们必须在将其设置回系统之前捕获某些值。我们计划创建如下条件：

`如果 city == “New York” 则设置电话号码 + “x” + 屏幕上的扩展号`

因此，我们需要获取数据：`City`、`Telephone number` 和扩展号（逻辑属性）。点击“Add Data Element”（添加数据元素）来添加数据。对于城市属性，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `City` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 根据所选类别指定数据元素类型 |
| Function | `Get` | 定义相同数据的可能变体。大多数数据元素仅支持 `Get` 函数。 |
| Attribute Name | `City (l)` | 必需属性 |
| ![](img/image_rsrc8SS.jpg) |  |  |
| 图 2-54 显示了获取数据的界面：City |  |  |

对于电话号码，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `TelephoneNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | Get 函数。 |
| Attribute Name | `Business Phone (Telephone Number)` | 必需属性 |

对于扩展号，按照下表选择值：

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `ExtensionNumber` | 数据名称 |
| Category | `Attributes` | 数据元素组。 |
| Type | `User Attribute` | 指定数据元素类型 |
| Function | `Get` | Get 函数。 |
| Attribute Name | `ExtNumber` | 我们的逻辑属性 |
| ![](img/image_rsrc8ST.jpg) |  |  |
| 图 2-55 显示了获取数据：Telephone 和逻辑属性 `ExtNumber` |  |  |

# 查看提交的任务

查看提交的任务对于开发者理解 `CA IdentityMinder` 的行为非常重要。在提交了管理员任务后，你可以去“查看提交的任务”中检查状态。选择 `System`（系统）标签页，选择菜单 `View Submit Task`（查看提交的任务）并点击 `Search`（搜索）。

| ![](img/image_rsrc8SZ.jpg) |
| --- |
| 图 2-61 显示了查看提交的任务界面 |

找到你提交的任务，应该是最新的一个。点击图标 `![](img/image_rsrc8T0.jpg)` 查看内部详情。

| ![](img/image_rsrc8T1.jpg) |
| --- |
| 图 2-62 显示了我们提交的任务。 |

提交任务详情中有 2 个有趣的地方：

- `Task History`（任务历史）告诉我们匹配了多少身份策略集（Identity Policy Set）或 `Policy Xpress`。
- `Included Event`（包含事件）告诉我们生成了多少个事件。

| ![](img/image_rsrc8T2.jpg) |
| --- |
| 图 2-63 显示了任务历史和包含事件 |

按顺序生成了 7 个事件：

1. **事件 1：修改用户**

   生成此 `Modify user`（修改用户）是因为我们修改了用户的属性：`city`（城市）。它是在提交任务后生成的（主对象为 `User`，操作为 `Modify`）。选择 `pencil`（铅笔）图标查看更多详细信息。它将在提交任务后显示新值和旧值。

   | ![](img/image_rsrc8T3.jpg) |
   | --- |
   | 图 2-64 显示生成事件 1：修改用户是因为我们修改了 `city` 属性。 |

   此事件完成后，`User Store`（用户存储库）中的 `city` 属性将发生更改。

   | ![](img/image_rsrc8T4.jpg) |
   | --- |
   | 图 2-65 显示事件 1：修改用户完成后，`city` 属性已更改。 |

2. **事件 2：同步用户**

   生成此事件是因为当我们在管理员任务中选择下拉菜单 `User Synchronization: On`（用户同步：开启）任务完成时。当此事件生成时，它将触发我们的策略集：`Set Office Address`（设置办公室地址）。

   | ![](img/image_rsrc8T5.jpg) |
   | --- |
   | 图 2-66 显示通过 `User Synchronization` 生成了事件 2。 |

3. **事件 3：修改用户**

   此事件由 `Policy Xpress` 生成。`Policy Xpress` 设置了 `Business Phone`（业务电话）的值。此事件完成后，`User Store` 中的 `telephone number`（电话号码）属性值已更改。

   | ![](img/image_rsrc8T6.jpg) |
   | --- |
   | 图 2-67 显示事件 3 由 `Policy Xpress` 生成以修改电话号码。 |

4. **事件 4：修改用户**

   此事件由 `Identity Policy Set`（身份策略集）生成。`Identity Policy` 设置了属性 `country`（国家）。此事件完成后，`User Store` 中的 `country` 属性值已更改。

   | ![](img/image_rsrc8T7.jpg) |
   | --- |
   | 图 2-68 显示事件 4 由 `Identity Policy Set` 生成修改属性 `country`。 |

5. **事件 5：同步配置角色并为用户添加账户**

   生成此事件是因为用户具有配置角色且选择了 `User Synchronization`（用户同步）选项。此事件用于在 `Endpoint`（终端）中创建账户。如果你已经在 `Endpoint` 中拥有账户，则此事件将无操作。你可以在 `TASK SESSION` 中查看账户创建详情：创建：0，更新：0，重建：0，失败：0。

   | ![](img/image_rsrc8T8.jpg) |
   | --- |
   | 图 2-69 显示了事件 5 的详情。 |



6. **事件我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。6：同步用户**

此事件在修改用户事件后由`Policy Xpress`生成。我们知道这一点，是因为`Attribute Changed`（属性更改）中的值来自`Policy Xpress`。

| ![](img/image_rsrc8T9.jpg) |
| --- |
| 图 2.70 显示了事件 6 的详情。 |

7. **事件 7：与账户同步用户属性的事件详情**

生成此事件是因为我们在管理员任务屏幕上选择了`Account Synchronization: On Task Complete`（账户同步：任务完成后开启）选项。此事件将更新全局用户和账户的属性。

| ![](img/image_rsrc8TA.jpg) |
| --- |
| 图 2-71 显示了事件 7 的详情。 |

在所有事件完成后，去 CA IdentityMinder 的`User Store`、`Provisioning Directory`（配置目录）和`Endpoint`（`Active Directory`）检查用户属性。

| ![](img/image_rsrc8TB.jpg) |
| --- |
| 图 2-72 显示了用户、全局用户和账户的属性。 |

提交管理员任务时，你需要知道：

* 将生成多少个事件？
* 哪个组件生成事件？
* 事件的预期结果是什么？

| ![](img/image_rsrc8TC.jpg) |
| --- |
| 图 2-73 显示了我们示例中的所有事件。 |

### 限制性

我们的管理员任务有一些限制：

* 它无法显示分机号的当前值。
* 分机号没有验证。
* 如果我们只更改分机号而不更改城市值，CA IdentityMinder 将认为此任务中没有发生变化。

我们可以通过编程轻松修复这些局限性。

| ![](img/image_rsrc8TD.jpg) |
| --- |
| 图 2.-74 显示我们只更新分机号而不更新`city`属性时的消息。 |

## 2.6 结论

在本章中，我们创建了管理员任务并使用管理员工具来实现需求。我们学习了：

* 如何创建管理员任务。
* 配置是如何工作的。
* `Identity Policy Set`和`Policy Xpress`如何工作。
* 理解事件。

## 3 编程概念与配置 IDE

在本章中，我们将学习：

* 同步和异步阶段。
* API 概览。
* 配置 IDE。

## 3.1 API 概览

CA IdentityMinder 有 2 类型的编程：

* `Java`（Java 编程）：执行逻辑。
* `Connector`（连接器）：用于连接终端。

连接器在另一书中。我们将首先关注 Java 编程。

### 同步与异步阶段

在开始任何 API 之前，你需要理解同步与异步阶段。

管理员任务的执行分为以下两个阶段：

* **同步阶段**：在任务提交期间处理用户响应。此时任务尚未拆解为事件。
* **异步阶段**：在任务提交后处理用户响应。任务已拆解为事件。它可能需要一小时到一个月。

| ![](img/image_rsrc8TE.jpg) |
| --- |
| 图 3-1 显示同步和异步阶段。 |

### 3.1.1 业务逻辑处理 API（BLTH）

业务逻辑处理或`BLTH API`可以在管理员任务级别执行逻辑。BLTH 在同步阶段运行，它可以在任务提交后、任何事件发生前执行。

| ![](img/image_rsrc8TF.jpg) |
| --- |
| 图 3-2 显示业务逻辑处理 API 在任务之前之后工作。 |

此 API 非常有用，我们将频繁使用。我们可以从 BLTH 访问存储库。

BLTH 示例：

* 管理员执行管理员任务；BLTH 屏幕上初始化某些值。
* 管理员提交管理员任务；BLTH 验证屏幕上的字段。
* 管理员提交管理员任务；BLTH 执行逻辑或修改存储库中的属性。

### 3.1.2 工作流 API

`Workflow API`在现实需求中非常重要。工作流可以在管理员任务级别或事件级别工作。

| ![](img/image_rsrc8TG.jpg) |
| --- |
| 图 3-3 显示工作流可以在管理员任务级别或事件级别特定。 |

在以下情况下需要工作流：

* 你的需求需要审批。
* 业务逻辑需要很长的处理时间。我们可以使用工作流在事件级别实现业务逻辑。它将在异步阶段运行。

书中，我们将学习如何通过软件`WorkPoint`创建自定义工作流。

工作流示例：

* 如果用户办公室在纽约，此任务需要 2 个审批者。如果用户办公室在伦敦，此任务需要额外的审批者。
* 需求在入职日期启用账户。

### 3.1.3 参与者解析 API

此 API 是工作流的一部分。`Participant Resolver API`回答问题：谁是审批者？我们可以为查找审批者实现条件。

示例：

* 我们希望经理的经理是审批者。

| ![](img/image_rsrc8TH.jpg) |
| --- |
| 图 3-4 显示工作流有一个需要参与者解析 API 的审批者。 |

### 3.1.4 事件监听器 API

我们可以实现自定义监听器来监听事件。当事件发生时，事件监听器会在执行的特定状态下执行业务逻辑：执行前、之后、失败、批准、拒绝。事件监听器在异步阶段运行。

示例：

* 用户创建成功后，向 MQ 发送消息。
* 如果管理员在任何修改用户事件上拒绝了请求，监听器将写入日志文件。

| ![](img/image_rsrc8TJ.jpg) |
| --- |
| 图 3-5 显示了事件监听器 API 可以监听事件。 |

### 3.1.5 逻辑属性 API（Logical Attribute API）

逻辑属性 API 显示属性的方式与其在用户目录中的物理存储方式不同。当属性在多个屏幕中共享，且你不想在每个屏幕上执行值的转换逻辑时，应使用此 API。

示例：

* 你有一个物理属性`BusinessCategory`，其存储值为代码：`1001`、`2001`或`3001`，但在屏幕上显示为广告、零售或电信。

| ![](img/image_rsrc8TK.jpg) |
| --- |
| 图 3-6 显示了逻辑属性 API 在屏幕上将物理值转换为逻辑值。 |

### 3.1.6 验证规则（Validation Rules）

用于验证屏幕上的字段值。你可以在以下位置编写规则：

* 任务级：它将在特定屏幕上进行验证。
* 目录级：它将在任何屏幕上每次对该字段进行验证。

示例：

* 员工编号必须全数字。

### 3.1.7 邮件模板（Email Template）

从 CA IdentityMinder 发送邮件有 2 种方式：

* 邮件通知策略。
* 邮件模板。

邮件模板 API 是其中一种。我们可以通过编写模板文件来实现。

### 3.1.8 通知规则（Notification Rule）

通知规则决定了谁接收邮件。通知规则仅在邮件模板未使用。

示例：

* 在任务更新位置完成后，向 HR 经理发送邮件。
  * 邮件模板用于生成邮件内容以及决定何时应该发送邮件。
  * 通知规则用于获取 HR 经理的邮箱地址。

### 3.1.9 任务执行 Web 服务（TEWS）

如果我们希望第三方系统执行我们的管理任务，则必须启用 TEWS 功能。TEWS 将管理任务作为 Web 服务的提供者。

示例：

* 用户使用 Web 门户修改地址。门户调用企业服务总线（ESB），然后 ESB 调用管理任务的 Web 服务来更新地址。

## 3.2 任务阶段（Task Phases）

我们已经讨论了同步和异步阶段的概述。本节将解释管理任务执行的阶段细节，以及每个 API 何时会被执行。

你现在不需要记住所有内容，当你练习书中的示例时，你会自动记住它们。

### 3.2.1 同步阶段操作

1. 用户选择一个管理任务进行执行。
   * 业务逻辑任务处理器 API：调用`handleStart()`方法。

2. 管理任务主体被选中，但尚未显示。
   * 业务逻辑任务处理器 API：调用`handleSetSubject()`方法。
   * 字段的默认值可以使用 JavaScript 或硬编码初始化。
   * 与物理属性关联的字段将自动从数据存储填充相应的数据。

3. CA IdentityMinder 显示并填充任务屏幕。
   * 逻辑属性：调用方法`toLogical()`以转换物理属性。

4. 当用户点击验证按钮（如果你有）、用户更改标签页或你有在更改时验证的逻辑时，CA IdentityMinder 在数据输入期间调用验证规则。

5. 用户提交任务屏幕。
   * 调用验证规则。
   * 逻辑属性 API：调用方法`validate()`执行字段级验证。
   * 逻辑属性 API：调用方法`toPhysical()`将逻辑属性转换回对应的物理属性。
   * 业务逻辑任务处理器 API：调用方法`handleValidation()`执行任务级验证。

6. 用户提交任务屏幕。

   如果发生验证错误，错误将立即报告给用户。允许用户纠正错误并重新提交任务。

7. CA IdentityMinder 为任务实例化事件。

   在成功完成所有验证后，CA IdentityMinder 创建事件。每个事务都由一个事件表示。

8. 任务进入异步阶段进行处理。

   有 3 个主要的 API：业务逻辑任务处理器、验证规则和逻辑属性在同步阶段执行。下面的图片显示了提交管理任务后的屏幕。消息“Task pending”（任务处理中）意味着该任务后面有事件处理，或者异步阶段从现在开始。

| ![](img/image_rsrc8TM.jpg) |
| --- |
| 图 3-7 显示了显示 Task pending 的屏幕。 |

### 3.2.2 异步阶段操作

1. CA IdentityMinder 发布事件。

2. 事件监听器执行审批前的属性更新。
   * 事件监听器 API：调用方法`before()`。

3. 自定义对象在工作流处理执行执行。
   * 参与者解析 API：如果工作流指定了工作流活动的参与者（审批者），调用方法`resolve()`返回参与者列表。
   * 工作流 API：`start`。如果启用了工作流且事件映射到工作流过程，则工作流过程中的活动必须在事件完成之前完成。

4. 事件监听器执行执行前的属性更新。
   * 工作流过程会导致事件的批准或拒绝。
   * 当工作流过程被批准时，CA IdentityMinder 执行关联事件。
     * 事件监听器 API：调用方法`approve()`或`reject()`。

5. CA IdentityMinder 执行事件。

6. 事件监听器执行执行后操作。
   * 事件监听器 API：调用方法`after()`。

7. CA IdentityMinder 生成邮件通知。
   * 调用邮件模板 API 和通知规则 API。

有 5 个 API：事件监听器、工作流、参与者解析、邮件模板和通知规则在异步阶段使用。

## 3.3 配置 IDE

我们使用 Eclipse 开发代码。请从书籍网站下载。

### 类路径（Class path）

请检查`Project Properties > Java Build Path`。

如果你使用 12.6 版本：

* 创建类路径变量：`IDM_LIB`
  * 选择`windows > preference > class path variable > new`
  * 设置路径为`/server/IdentityMinder.ear/library`
    * 如果你使用 WebLogic，所有的 jar 包都位于`APP-INF/lib`。

| ![](img/image_rsrc8TN.jpg) |
| --- |
| 图 3-8 显示了类路径变量。 |

如果你使用 12.5 版本，请移除我所有的 jar 包：

* 从 deploy 文件夹`/server/IdentityMinder.ear/library`添加所有 jar 包。
  * 如果你使用 WebLogic，所有的 jar 包都位于`APP-INF/lib`。
* 从`/server/IdentityMinder.ear/user_console.war/WEB-INF/lib`添加`identitymanager.jar`。

### 导入项目（Import projects）

* 运行 Eclipse 并选择`import > Existing projects into Workspace`。
* 浏览归档文件，选择项目并点击 finish。

| ![](img/image_rsrc8TP.jpg) |
| --- |
| 图 3-9 显示了导入项目。 |

## 3.4 总结

本章介绍了 CA IdentityMinder 的 9 个 API：它们是什么以及在何时执行。我们已经解释了任务阶段：同步阶段和异步阶段。

* 同步阶段：业务逻辑任务处理器、验证规则和逻辑属性。
* 异步阶段：事件监听器、工作流、参与者解析、邮件模板和通知规则。
* 任务执行 Web 服务将管理任务作为 Web 服务的提供者。

CA 通过 bookshelf > CA IdentityMinder > programming > Javadoc Programming Reference 提供每个 API 的 java doc。下一章将详细介绍业务逻辑任务处理器 API。

# 第 4 章 业务逻辑任务处理器

Business Logic Task Handler API 或`BLTH`是在管理任务级执行业务逻辑的 API。业务逻辑任务处理器具有独特特性：

* 业务逻辑任务处理器 API 在管理任务会话级工作。
* 业务逻辑任务处理器 API 在同步阶段执行。
  * 这意味着用户必须等待直到逻辑执行完成。
* 业务逻辑任务处理器 API 必须在任何事件创建之前完成。
* 业务逻辑任务处理器 API 适用于：
  * 验证和格式化任务屏幕字段。
  * 强制执行需要立即响应（同步）的自定义业务逻辑。

## 4.1 编程与配置概念

业务逻辑任务处理器 API 可以通过 Java 或服务端 JavaScript 脚本实现。本书仅使用 Java 语言。对于服务端 JavaScript 脚本，您可以参阅详尽的官方文档。我们将使用`java`作为所有 API 的统一语言，并且也可以从`java`工具类库中获益。

### 4.1.1 编程

要实现业务逻辑任务处理器 API，我们只需要创建一个`java`类并扩展`BLTHAdapter`类，然后重写方法。每个方法都是在管理任务生命周期期间执行的回调方法。您可以根据需求实现某些或全部方法：

* `handleStart()`：在任务开始时执行。
* `handleSetSubject()`：在从搜索结果中选择主体（例如选择用户）后执行。它设置屏幕上的初始值。
* `handleValidation()`：在用户提交任务后执行。用于验证。
* `handleSubmission()`：在`handleValidation()`之后执行。用于执行逻辑。

### 开发步骤

1. 编写扩展`BLTHAdapter`的`java`代码。
2. 编译并确保没有错误，且使用的`JDK`版本与服务器版本相同。
3. 将类文件（包括包文件夹）拷贝到文件夹`\IdentityMinder.ear\custom`。

### 4.1.2 配置

业务逻辑任务处理器可以通过两种范围进行配置：

* 全局业务逻辑任务处理器：此级别意味着它适用于所有管理任务。每当调用任何管理任务时，我们的`java`代码都会执行。
* 任务特定业务逻辑任务处理器：此`java`代码将在配置的特定管理任务中执行。此范围在书中频繁使用。

#### 全局业务逻辑任务处理器

它们在管理控制台中通过通过选择`Home > Environments > <your server> > Advanced Settings > Business Logic Task Handlers`进行配置。

![](img/image_rsrc8TR.jpg)

| 图 4-1 显示了全局业务逻辑任务处理器的界面。 |
| --- |

您可以点击`New`按钮来配置业务逻辑任务处理器。配置屏幕上的每个字段与任务特定业务逻辑任务处理器相同。

#### 任务特定业务逻辑任务处理器

此级别适用于特定的管理任务。步骤如下：

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 搜索管理任务名称。
3. 点击`Business Logic Task Handlers`按钮，然后点击`Add`按钮指定`java`类名。

![](img/image_rsrc8TS.jpg)

| 图 4-2 显示了任务特定的`Business Logic Task Handlers`按钮。 |
| --- |

## 4.2 任务会话

任务会话是执行中任务的实例。在任务执行期间，业务逻辑任务处理器可以访问当前任务会话中的信息。任务会话信息可以通过`BLTHContext`获取。接口提供了检索当前任务会话中托管对象运行实例的方法，例如：

* 方法`getUser()`：检索参与当前任务的`User`对象。
  * 请注意，如果管理任务具有主对象`User`（例如`modify user`），则`getUser()`将有效。如果您的管理任务是`modify endpoint`，则调用`getUser()`没有意义的。
* 获取任何关系对象（如角色和组）。

`BLTHContext`继承自许多父接口：

* `TaskInfo`：关于当前任务的信息；例如`getSubject()`返回主对象。
* `IMContext`：提供关于用于在 API 之间共享会话的方法。该接口还提供了`getAuxDataRoot()`方法访问辅助数据树的根。
* `ProviderAccessor`：提供直接访问数据存储中任何托管对象的权限。我们将在下一节讨论托管对象。

## 4.3 访问托管对象



托管对象我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。指数据存储中的对象，例如`user`或`account`。业务逻辑任务处理器可以通过以下两种方式访问托管对象：

### 通过 ProviderAccessor

`ProviderAccessor`是`BLTHContext`的父类：

- 可以访问任何托管对象。
- 可以访问托管对象中的任何属性。
- 当调用`modifyObject()`时，对托管对象的任何更改都会立即持久化到数据存储中。
  - 不生成事件，也不执行工作流审批、审计或安全检查。

### 通过 Context

本章中的 Context 指`BLTHContext`，但其他章节指`WorkflowContext`、`EventContext`等。

- 限制访问任务会话，包括任务主体（主对象）和主体的关系。
  - 例如管理任务：`Modify User`。上下文只能访问作为此任务托管对象的`User`对象。
- 限制访问属性：
  - 例如，如果管理任务只定义了`user`对象的`city`属性，您无法访问`user`对象的`country`属性。
- 更改将在事件完成后提交。
  - 例如，如果您使用`BLTHContext`修改`city`属性，但用户修改事件失败或工作流（事件内部）被拒绝，则`city`属性将不会提交。
  - CA IdentityMinder 为任务生成事件，并可以执行工作流审批、审计和安全检查。

![](img/image_rsrc8TT.jpg)

图 4-3 显示了访问托管对象的 2 种方式。

下表比较了`BLTHContext`和`ProviderAccessor`之间的差异。

| 主题 | ProviderAccessor | BLTHContext |
| :--- | :--- | :--- |
| 访问对象 | 可以访问任何托管对象。 | 仅访问与任务会话相关的对象。 |
| 访问属性 | 可以访问任何属性。 | 根据您定义管理任务的时间限制访问。 |
| 修改值 | 当调用`modifyObject()`时，修改后的值会立即提交到数据存储中。 | 在事件完成之前值不会提交。 |
| 事件 | 不生成额外的事件。 | 与任务相关的事件有关。 |

我们将在下一节和章节中通过示例介绍托管对象的更多细节。

## 4.4 代码示例

在 CA IdentityMinder 编程中，我们使用名为`IdmCode`的 java 项目。我们复用了上一章中的管理任务。我们将仅使用业务逻辑任务处理器 API 执行管理任务，因此我们需要禁用上一章中的 Identity Policy Set 和 policy Xpress。

![](img/image_rsrc8TU.jpg)

图 4-4 显示通过取消勾选启用框来禁用 Identity Policy Set 和 Policy Xpress。

### 4.4.1 基础编程：BLTHAdapter 和生命周期

此示例逐步演示了业务逻辑任务处理器的基础编程。CA IdentityMinder 编程始终需要两个部分：编码和配置。此示例仅展示业务逻辑任务处理器 API 的生命周期。我们将打印到日志文件中。

#### 代码

1. 运行 eclipse 并选择 java 类：
   - 包：`com.book.idm.blth`
   - 类：`BasicLifeCycle`
   - 扩展`BLTHAdapter`

下面的列表显示了我们的代码：

```java
package com.book.idm.blth;
import com.netegrity.imapi.BLTHAdapter;
import com.netegrity.imapi.BLTHContext;
public class BasicLifeCycle extends BLTHAdapter{
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

2. 编译并复制类（包含包文件夹`com.book.idm.blth`）到文件夹`\IdentityMinder.ear\custom`。

#### 配置

有两种类型的配置：全局业务逻辑任务处理器和特定任务的业务逻辑任务处理器。在所有示例中，我们选择了特定任务的业务逻辑任务处理器。

1. 搜索我们的管理员任务名称：Update Location and Ext Number（更新位置和分机号）。
2. 点击`Business Logic Task Handlers`按钮，然后点击`Add`按钮指定特定的 Java 类名。
3. 如下所示填写值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | `BLTHExample` | 业务逻辑任务处理器的名称 |
| Java Class | `com.book.idm.blth.BasicLifeCycle` | 我们放在 custom 文件夹中的 Java 类名 |

![](img/image_rsrc8TV.jpg)

图 4-5 显示了“业务逻辑任务处理器详情”屏幕界面。

4. 点击 ok 并提交此管理员任务。

#### 工作原理

我们可以通过以下步骤通过管理员任务执行我们的代码：

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页：`Book Example`并选择菜单：`Basic`。
3. 选择管理员任务：`Update Location and Ext Number`。

![](img/image_rsrc8TW.jpg)

图 4-6 显示了选择管理员任务。

日志文件显示：

```text
INFO [STDOUT]UpdateLocationExtNumber:handleStart
```

4. 然后搜索并选择一些用户。当管理员任务显示时，日志文件将显示：

```text
INFO  [STDOUT]  UpdateLocationExtNumber:handleSetSubject
```

![](img/image_rsrc8TX.jpg)

图 4-7 显示了管理员任务屏幕显示。

5. 修改城市属性（你必须修改城市的值）并提交管理员任务，日志将显示：

```text
INFO [STDOUT] UpdateLocationExtNumber:handleValidation
INFO [STDOUT] UpdateLocationExtNumber:handleSubmission
```

你将看到业务逻辑任务处理器的生命周期，以及`BLTHAdapter`的每个方法的执行情况。

### 4.4.2 通过 BLTHContext 修改用户属性

此示例将演示如何使用`BLTHContext`：

- 将城市属性修改为“New City”。
- 从父接口获取当前任务信息：`TaskInfo`。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.blth.ModifyUserByBLTHContext`。
2. 复制类（包含包文件夹`com.book.idm.blth`）到文件夹`\IdentityMinder.ear\custom`。

#### 配置

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页`Roles and Tasks`并选择菜单`modify admin task`。
3. 搜索并选择我们的管理员任务名称：`Update Location and Ext Number`。
4. 点击`Business Logic Task Handlers`按钮，然后点击图标`pencil`。

![](img/image_rsrc8TY.jpg)

图 4-8 显示了修改 Java 类的“铅笔”图标。

5. 如下所示修改值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Java Class | `com.book.idm.blth.ModifyUserByBLTHContext` | 我们放在 custom 文件夹中的 Java 类 |

![](img/image_rsrc8TZ.jpg)

图 4-9 设置了新 Java 类的值。

#### 工作原理

我们可以通过以下步骤通过管理员任务执行我们的代码：

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页：`Book Example`并选择菜单：`Basic`。
3. 选择管理员任务：`Update Location and Ext Number`。
4. 然后搜索并选择一些用户。
5. 修改城市属性（你必须修改城市的值）并提交管理员任务。

#### Access 用户对象

城市属性的结果将是“New City”。无论你在屏幕上选择了什么值，都不重要，因为我们的代码设置了该值。我们在`handleSubmission()`方法中设置了城市属性。

```java
//Access User Object
User user = blthContext.getUser();
user.setAttribute("l", "New City");
```

在代码中，我们通过`BLTHContext.getUser()`访问用户对象并设置属性：`city`。有一个有趣的地方是属性名称。用户对象使用了代表用户存储中的属性名称。`L`的小写表示城市。你可以使用任何 LDAP 客户端连接用户存储并查看用户的属性名称。

![](img/image_rsrc8U0.jpg)

#### Access 信息

在代码中，我们通过`BLTHContext.getUser()`访问用户对象并设置属性：`city`。有一个有趣的地方是属性名称。用户对象使用了代表用户存储中的属性名称。`L`的小写表示城市。你可以使用任何 LDAP 客户端连接用户存储并查看用户的属性名称。

3. 选择管理员任务：“Update Location and Ext Number”（更新位置和分机）。
4. 搜索并选择某些用户。
5. 修改城市属性（必须修改城市值）并在分机号中输入值“xxxxxx”。提交管理员任务。

![](img/image_rsrc8U6.jpg)

图 4-16 显示我们任务的值。

#### 使用 ProviderAccessor

使用`providerAccessor`意味着`ProviderAccessor`的任何方法都是`BLTHContext`的父类。例如：`getUserProvider()`、`getGroupProvider()`等。方法名将以单词`provider`结尾。每个托管对象类型（如`User`、`Group`和`Organization`）都与一个提供对象关联，您可以使用该对象访问托管对象的数据。

```java
User user = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
```

`BLTHContext`有一个父接口：`ProviderAccessor`。当我们调用`getUserProvider()`时，它返回`UserProvider`。`UserProvider`拥有方法`findUser()`。

```java
findUser(TSContext context, java.lang.String name, AttributeRightsCollection attributes)
```

该方法需要 3 个参数：

- `context`：当前任务会话的上下文。我们的代码使用了`BLTHContext`。
- `name`：要检索的用户名称。该名称可以是唯一名称或友好名称。我们的代码使用了用户的唯一名称。

```java
//从任务中获取唯一名称
String userid = blthContext.getUser().getUniqueName();
```

- `attributes`：一个`AttributeRight`对象的集合，每个对象包含一个属性名称和一个权限请求。我们的代码传递了`null`值。

我们从`ProviderAccessor`获取用户对象。我们可以修改电话号码属性。属性名称与用户存储中物理属性的名称相同。

```java
user.setAttribute("telephoneNumber", "212-222-2222x1234");
user.modifyObject();
```

我们通过`ProviderAccessor`修改托管对象，这实际上是在改变对象的本地（内存中）表示。要将更改持久化到数据存储器，我们需要调用`modifyObject()`。更改将直接应用于数据存储器。此时不会生成 Identity Manager 事件，也不会执行工作流审批、审计或安全检查。

#### 在用户存储中检查结果

我们做了两件事：更改了城市属性，我们的 Java 代码使用`AccessProvider`修改了电话号码。使用 LDAP 客户端连接到用户存储，我们将看到电话号码值已经更改。

![](img/image_rsrc8U7.jpg)

图 4-17 显示电话号码属性已更改。

#### 在查看提交的任务屏幕中检查结果

选择菜单：view submitted task（查看已提交的任务），在标签页下：`system`。选择我们的任务，你将看到内部的事件。

![](img/image_rsrc8U8.jpg)

图 4-18 显示所有事件。

点击`Modify User`事件查看属性更改：

- 城市属性来自修改用户存储中值的屏幕界面。
- 电话号码，我们使用`ProviderAccessor`修改的。因此，在`Modify User`事件中属性发生了变化，但我们看不到来自`ProviderAccessor`的值，只能看到来自屏幕的值。

![](img/image_rsrc8U9.jpg)

图 4-19 显示提交后的属性更改。

#### 修改的顺序

现在我们有两个需要配置的属性：城市和电话号码：

- 城市值来自屏幕。
- 电话号码值来自`ProviderAccessor`。
  - 在屏幕上，我们输入了值“xxxxxx”。
  - 最终结果是“212-222-2222x1234”。

如果你的环境配置了配置和 Active Directory 账户，你将看到端点中的电话属性为“212-222-2222x1234”。

![](img/image_rsrc8UA.jpg)

图 4-20 电话号码已配置到端点。

我们可以逐步解释如下：

- 步骤 1：当用户提交管理员任务时，执行`handleSubmission()`方法。当调用`modifyObject()`方法时，电话号码将被提交。
- 步骤 2：生成了`Modify user`事件。当`modify user`事件完成后，CA IdentityMinder 将提交城市值。
- 步骤 3：`Synchronize User`事件，与此无关。它将触发`Policy Set`（策略集）。
- 步骤 4：`Synchronize User Attribute with Account`将属性从配置目录同步并到端点。

![](img/image_rsrc8UB.jpg)

图 4-21 显示配置步骤。

### 4.4.4 BLTHContext 和 ProviderAccessor

这个示例是一种为了更好地理解`BLTHContext`和`ProviderAccessor`而进行的实验。我们将尝试同时使用这两个 API 更新城市和电话属性。让我们看看发生了什么。

#### 代码

1. 编译我们的 Java 代码：`com.book.idm.blth.ModifyUserByBoth`。
2. 将类（包括包文件夹`com.book.idm.blth`）复制到文件夹`\IdentityMinder.ear\custom`。

#### 配置

1. 以管理员身份登录 Identity Manager User Console。
2. 选择标签页`Roles`（角色）和`Tasks`，并选择菜单`modify admin task`。
3. 搜索并选择我们的管理员任务名称：`Update Location and Ext Number`。
4. 点击`Business Logic Task Handlers`按钮，然后点击“铅笔”图标。
5. 如下所示修改值。

| 字段名称 | 值 |
| :--- | :--- |



| Java Class | `com.book.idm.blth.ModifyUserByBoth` | 我们的 Java 类 |
| --- | --- | --- |

按照以下步骤执行我们的代码：

1.我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。以管理员身份登录 Identity Manager User Console。
2. 选择标签页 `Roles` 和 `Tasks`，并选择菜单 `modify admin task`。
3. 搜索并选择我们的管理员任务名称：`Update Location and Ext Number`。
4. 点击 `Business Logic Task Handlers` 按钮，然后点击“铅笔”图标。
5. 如下所示修改值。

```java
public void handleSubmission(BLTHContext blthContext) throws Exception {
// 使用 BLTHContext
User user1 = blthContext.getUser();
user1.setAttribute("l", "New City");
//user1.setAttribute("telephoneNumber", "111111");
// 使用 ProviderAccessor
String userid = user1.getUniqueName();
User user2 = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
user2.setAttribute("l", "New Town");
user2.setAttribute("telephoneNumber", "2222222");
user2.modifyObject();
}
```

| ![](img/image_rsrc8UC.jpg) |
| --- |
| 图 4-22 显示错误 |

| ![](img/image_rsrc8UD.jpg) |
| --- |
| 图 4-23 显示所有属性 |

| ![](img/image_rsrc8UE.jpg) |
| --- |
| 图 4-24 我们将城市值更改为 Toronto |

| ![](img/image_rsrc8UF.jpg) |
| --- |
| 图 4-25 显示最终结果 |

- 步骤 3：`ProviderAccessor` 将城市（city）属性值提交为“New Town”。现在城市属性已更改为“New Town”。
- 步骤 4：当用户事件完成时，`CA IdentityMinder` 从由 `BLTHContext` 修改过的任务中提交城市属性值。

步骤 1–3 发生在同步阶段。步骤 2 和 3 由业务逻辑任务处理器执行。步骤 4 属于异步阶段。

| ![](img/image_rsrc8UG.jpg) |
| --- |
| 图 4-26 显示了修改的序列图 |

### 4.4.5 业务逻辑任务处理器和屏幕

在本示例中，我们将通过编写程序来从管理员任务的屏幕中获取数据。此示例展示了：

- 如何获取当前分机号并将其显示在屏幕上。
- 验证用户输入。分机号必须存在且只能是数字。
- 显示如何向用户发送错误消息。
- 使用会话属性在方法之间共享分机号。

### 代码

1. 编译我们的 Java 代码：`com.book.idm.blth.ModifyUserAndScreen`。
2. 将类（包含包文件夹 `com.book.idm.blth`）复制到文件夹 `\IdentityMinder.ear\custom`。

### 配置

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择 `Roles` 和 `Tasks` 选项卡，并选择菜单 `modify admin task`。
3. 搜索并选择我们的管理员任务名称：`Update Location and Ext Number`。
4. 点击 `Business Logic Task Handlers` 按钮，然后点击 `pencil` 图标。
5. 如下所示修改值。

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Java Class | `com.book.idm.blth.ModifyUserAndScreen` | 我们放在 custom 文件夹中的 Java 类 |

### 工作原理

我们可以按照以下步骤通过管理员任务执行我们的代码：

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择选项卡：`Book Example`，并选择菜单：`Basic`。
3. 选择管理员任务：`Update Location and Ext Number`。
4. 然后搜索并选择一些用户。

#### `handleSetSubject()`：在屏幕上显示当前电话号码

当屏幕初始显示时，会调用 `handleSetSubject()` 方法。因此，在这个方法内部实现设置显示分机号。

| ![](img/image_rsrc8UH.jpg) |
| --- |
| 图 4-27 分机号当前值已显示在屏幕上 |

设置分机号，我们需要做两件事：

- 获取当前电话号码。
- 设置屏幕逻辑属性的值：`|ExtNumber|`。

获取当前电话号码并不新，我们使用 `ProviderAccessor` 获取该值。

```java
String userid = blthContext.getUser().getUniqueName();
User user = blthContext.getUserProvider().findUser(blthContext.getTSContext(), userid, null);
String telephoneNumber = (String)user.getAttribute("telephoneNumber");
```

请想象管理员任务的屏幕。当我们定义管理员任务时：

- 在管理员任务内部，有选项卡（tabs）。
- 我们的管理员任务有一个 profile 选项卡。
- 在选项卡内部，有一个屏幕（screen）。
- 在屏幕内部，有字段（fields）。

| ![](img/image_rsrc8UJ.jpg) |
| --- |
| 图 4-28 显示管理员任务配置中的选项卡屏幕 |

在管理员任务内部，有选项卡。我们调用方法 `getTaskTabHandlers()` 返回此管理员任务的所有选项卡。

```java
Vector<TabHandler> tabs = blthContext.getTaskTabHandlers();
for (TabHandler tab : tabs) {
```

我们的管理员任务中有一个 profile 选项卡，因此我们需要检查 `ProfileTabHandler` 的类型。如果你有很多 profile 选项卡，你需要一个条件来检查屏幕的标签名。我们检查屏幕标签名 `BookBasicUpdateLocationAndExtNo`。（在我们的示例中只有一个选项卡，你可以跳过此条件。）

```java
// 检查选项卡类型
if (tab instanceof ProfileTabHandler) {
    ProfileTabHandler profileTab = (ProfileTabHandler) tab;
    String screenName = profileTab.getScreenHandler().getScreen().getTag();
    if(screenName.equals("BookBasicUpdateLocationAndExtNo")){
}
```

我们可以使用 `updateRawData()` 方法在屏幕上设置值。

```java
HashMap<String, String> data = new HashMap<String, String>();
data.put("|ExtNumber|", telephoneNumber.substring(telephoneNumber.indexOf("x") + 1));
...
profileTab.updateRawData(data);
```

在屏幕内部，有字段。我们创建一个新的 `HashMap` 对象。我们放入键值对，键的名称 `|ExtNumber|` 来自管理员任务中的屏幕定义。如果你想设置城市属性，可以使用与用户存储（user store）相同的属性名。城市属性使用“l”作为键。

### `handleValidation()`：验证用户输入

当用户提交管理员任务后，如果分机号为空或输入了字符，错误将被部署。

| ![](img/image_rsrc8UK.jpg) |
| --- |
| 图 4-29 显示错误消息 |

我们必须重写 `handleValidation()` 方法。我们可以通过 `getRawData()` 方法从屏幕获取任何字段。如果你不确定字段名称，可以通过 `getRawData()` 方法打印。它是一个 `HashMap` 对象，键由字段名表示。

```java
String extNumber = (String) profileTab.getRawData().get("|ExtNumber|");
```

你可以从屏幕获取值并执行以下逻辑：

```java
String extNumber = (String) profileTab.getRawData().get("|ExtNumber|");
if (extNumber == null) {
} else {
    try {
        int number = new Integer(extNumber);
    } catch (NumberFormatException ne) {
    }
```

### 显示错误消息

通过抛出 `IMSException` 对象来显示错误。你可以通过 `addUserMessage()` 方法在屏幕上放置消息。

```java
IMSException imsEx = new IMSException();
imsEx.addUserMessage("Telephone number can't empty");
throw imsEx;
```

### 会话属性：在方法之间传递值



我们已经验证了电话号码，可以通过会话将值传递给`handleSubmission()`方法。`BLTHContext`提供会话属性供方法和其他 API 共享数据。

```java
public void handleValidation(BLTHContext blthContext) throws Exception {
    // 设置值到会话
    blthContext.setSessionAttribute("extNumber", number);
}
public void handleSubmission(BLTHContext blthContext) throws Exception {
    // 从会话获取值
    Integer extNumber = (Integer) blthContext.getSessionAttribute("extNumber");
}
```

## 4.5 用例示例

CA IdentityM 官方文档提供了用例示例，但没有提供编程细节。本节将为你提供关于这些示例的一些思路。

请参阅 Programming Guides › Programming Guide for Java › Business Logic Handler API › Business Logic API Overview › Use Case Examples。

### 检查组成员限制是否达到

当管理员通过提交修改组任务尝试向组添加成员时，访问组管理对象以确定当前成员的数量。如果组达到了最大人数，则抛出异常。

对于修改组任务，我们可以使用`blthContext.getGroup()`。我们调用`getMembers()`返回组内的所有成员。我们可以检查大小。

```java
Vector users = blthContext.getGroup().getMembers(ObjectType.USER, null);
System.out.println("user size : "++users.size());
```

请注意，`Group`类拥有`getUsers()`和`getMembers()`方法：

- `getUsers()`方法仅返回用户对象。
- `getMembers()`方法根据参数`ObjectType`返回任何对象。详情请参见 Java 文档：`ObjectType`。

CA IdentityMinder 附带了一个预定义的业务逻辑任务处理器，它会在对象创建之前检查对象可能的重复性。例如，新创建的角色名称必须是唯一的。当角色准备被创建时，预定义的业务逻辑任务处理器会验证新角色的名称是否已经存在。如果名称存在，处理器将抛出一个异常，指示角色名称必须唯一，管理员有机会更改名称并重新提交任务。

我们可以使用`ProviderAccessor`搜索角色名称。

```java
boolean isUnique = false;
try{
    //Search by friendlyName
    AccessRole role = blthContext.getAccessRoleProvider().findAccessRole(roleName);
}catch(NoSuchObjectException e){
    isUnique = true;
}
if(!isUnique){
    IMSException imsEx = new IMSException();
    imsEx.addUserMessage(“The role name must be unique”);
    throw imsEx;
}
```

## 在最大失败登录尝试后禁用用户账户

当用户连续登录失败三次后，账户将在数据存储中被立即禁用。由于账户是直接在数据存储中更新的，而不是在任务会话中，`CA IdentityMinder`不会为此操作生成事件，任何可能与此操作相关的工作流审批、审计和安全检查都将被跳过。在最后登录尝试后，自定义消息会提示用户该账户已禁用。

用例提到用户账户直接在数据存储中进行更新（禁用）。此用例意味着使用`ProviderAccessor`直接更新用户属性。（有关如何直接更新账户属性，请参阅第第二卷）

## 在自注册期间将用户分配到组

以“福利管理员”（Benefits Administrator）头衔进行自注册的用户将被分配到 HR 组。此更新是在任务会话中完成，通过调用`RelationshipTabHandler`中的`assignResources()`实现。此更新会触发`AddToGroupEvent`事件，允许组分配受到审计和工作流审批的影响。

我们使用业务逻辑任务处理器通过如下代码修改选项页中的值。

```java
for (TabHandler tab : tabs) {
    RelationshipTabHandler rTab = (RelationshipTabHandler)tab;
    rTab.assignResources(groups);
}
```

### 为新用户分配“经理”（manager）属性

管理员想在屏幕上显示配置界面之前设置“经理”的值。可以编写一个业务逻辑任务处理器，实现`handleSetSubject()`方法进行初始化。该方法会将管理员的名称分配给经理名称属性。如果管理员名称不可用，则抛出异常。

我们在`handleSetSubject`方法中编写代码来初始化经理属性。

```java
public void handleSetSubject(BLTHContext blthContext) throws Exception {
    String managerId = blthContext.getAdminFriendlyName();
    if(managerId == null){
        throw new IMSException(“administrator’s name is not available”);
    }
    HashMap<String, String> screenFields = new HashMap<String, String>();
    screenFields.put(“managerId”, managerId);
    tab.updateRawData(screenFields);
}
```

## 4.6 结论

在本章中，我们学习了业务逻辑任务处理器 API 概念的基本编程。我们可以做如下总结：

### 实现业务逻辑任务处理器

- 有 2 个步骤：编码和配置。
- 对于编码，你必须编写扩展`BLTHAdapter`的 Java 类并根据需要重写方法。
  - `handleStart()`：当用户选择管理员任务时调用。
  - `handleSetSubject()`：用于在显示之前设置字段。
  - `handleValidation()`：用于验证。
  - `handleSubmission()`：在用户提交、验证后执行。
  - 编译并复制到文件夹`\IdentityMinder.ear\custom`。
- BLTH 配置有 2 个级别：全局和特定任务级别。

### 访问托管对象

- 有 2 种方式：通过`ProviderAccessor`和`BLTHConext`（任务会话）。
- 对于`BLTH`，我们必须考虑：
  - 主对象是什么？
  - 修改的属性是否在管理员任务中定义？

### 编程笔记

- 代码中的用户属性名称是用户存储中的物理名称。
- 你可以使用`getRawData()`和`setRawData()`访问屏幕上的值。
- 可以通过`IMSException`对象在屏幕上显示消息。
- 可以使用 session 保持值并在方法之间共享。

业务逻辑任务处理器 API 在同步阶段执行业务逻辑。在异步阶段，我们使用工作流来执行业务逻辑。下一章是工作流。

# 第 5 章 工作流

`CA IdentityMinder`官方文档关于工作流的细节并不多。我们从前面的章节中学了一些基本概念：

- 如果需求需要审批者，则你需要工作流。
- 工作流在异步阶段运行。
- 工作流可以持续很长时间。它可能需要一小时或一个月的时间。
- 业务逻辑任务处理器在工作流开始之前完成。

在本章中，你将学习工作流 API 以及如何创建自定义工作流。

## 5.1 工作流概念

你必须在管理控制台（Management Console）中启用工作流。默认情况下，工作流是禁用的。

### 配置：管理控制台

1. 在管理控制台中选择环境（Environment）。
2. 转到 Advanced Settings，Workflow。
3. 勾选 Enabled 复选框，并点击 Save。
4. 重启应用程序服务器。

![](img/image_rsrc8UM.jpg)

图 5-1 显示了管理控制台中的工作流属性。

在事件映射表中，事件与全局工作流过程之间有一些默认映射。这意味着当表中的任何事件启动时，都将执行工作流。我们不修改任何值。

### 5.1.1 默认工作流功能

在本节中，我们将学习`CA IdentityMinder`中的默认工作流功能。我们涵盖以下主题：

- 工作流级别：工作流可以运行管理员任务级别。
- 选择工作流：哪些工作流可以执行。
- 策略基础：它是启动工作流的条件。
- 审批者的任务和屏幕。
- 审批者：谁是审批者。
- 预期结果：最终结果：通过或拒绝。

### 工作流级别

工作流可以在管理员任务和/或事件级别运行。应该是什么级别？这取决于需求。例如，我们有一个管理员任务“修改用户”，我们的管理员任务有 2 个选项页：配置选项页（Profile Tab）和访问角色选项页（Access Role Tab）。因此，从此管理员任务生成的事件分为两组：

- 第一组事件来自配置选项页；当用户属性被修改时，会生成事件。
- 第二组事件来自访问角色选项页；当我们添加或删除访问角色时，会生成事件。

![](img/image_rsrc8UN.jpg)

图 5-2 显示了示例管理员任务的所有事件。

我们有 2 个请求：从配置选项页修改用户属性的请求，另一个从访问角色选项页添加/删除角色的请求。

- **场景 1**：所有请求（修改属性和添加角色）都只需要一个工作流进行审批，我们将工作流指定为管理员任务级别。
- **场景 2**：仅修改用户属性请求（配置选项页）需要审批者，我们将工作流指定为事件级别：`ModifyUserEvent`。
- **场景 3**：仅添加角色请求（访问角色选项页）需要审批者，我们将工作流指定为事件级别：`AssignAccessRoleEvent`。
- **场景 4**：任何请求（修改属性和添加角色）都需要经理作为第一个审批者。
  - 修改属性请求需要 HR 经理作为第二个审批者。
  - 添加角色请求需要 IT 经理作为第二个审批者。

我们将第一个审批工作流指定为管理员任务级别，并将 HR 和 IT 工作流指定为事件级别：`ModifyUserEvent`和`AssignAccessRoleEvent`。此案例如下所示。

![](img/image_rsrc8UP.jpg)

图 5-3 显示了场景 4 的工作流。

#### 管理员任务级别

管理任务（admin task）的工作流需要设置属性`TASK_LEVEL=true`。你将在示例代码中看到它。要在管理任务级别启用工作流，你需要进行以下配置：

- 在`Profile`标签页上，勾选`Enable Workflow`复选框。
- 在`Profile`标签页上，点击工作流流程标签旁的铅笔图标。将显示工作流配置屏幕。

| ![](img/image_rsrc8UR.jpg) |
| 图 5-4 显示了如何在管理任务级别配置工作流 |

#### 事件级别

要在事件级别启用工作流，你需要进行以下配置：

- 在`Profile`标签页上，确认`Enable Workflow`已勾选。
- 在`Events`标签页上，点击事件上的铅笔图标。将显示工作流映射屏幕，并选择一个流程模板。

| ![](img/image_rsrc8US.jpg) |
| 图 5-5 显示了如何在事件级别配置工作流 |

### 选择工作流

你可以从下拉菜单中选择工作流。CA IdentityMinder 提供了三个默认流程模板：

- `SingleStepApprovalProcess`：适用于一个主审批人，当未找到主审批人时使用默认参与者。
- `TwoStageApprovalProcess`：适用于两个主审批人，当未找到主审批人时使用默认参与者。
- `EscalationApprovalProcess`：适用于一个主审批人，当未找到主审批人时使用默认参与者。此工作流的主审批人可以升级给另一个审批人。

你可以创建更多自定义工作流，我们稍后会详细介绍。

### 策略基础（Policy Base）

策略基础是启动工作流前的条件。下面的图片显示了策略基础：如果用户的城市是纽约，则需要工作流：`TwoStageApprovalProcess`。

| ![](img/image_rsrc8UT.jpg) |
| 图 5-6 显示了工作流策略基础屏幕 |

如果请求不符合任何条件，事件或管理任务将在不通过工作流的情况下执行。

### 审批人任务

如果工作流需要审批人，我们需要一个界面让审批人执行批准或拒绝的操作。下面的图片显示了选择审批任务的屏幕：

| ![](img/image_rsrc8UU.jpg) |
| 图 5-7 显示了审批人屏幕的配置。 |

下面的图片显示了审批人屏幕示例。图标 ![](img/image_rsrc8UV.jpg) 意味着该值已更改。你可以点击来回滚该值。

| ![](img/image_rsrc8UW.jpg) |
| 图 5-8 显示了审批人屏幕 |

你可以通过创建新的管理任务来创建新的审批人任务。你必须选择操作为“Approve Event”（批准事件）或“Approve Task”（批准任务）。

### 审批人

如果工作流需要审批人，我们需要指定谁是审批人。我们可以从`Participant Resolver`下拉菜单中选择审批人类型。它提供了获取审批人的条件。

| ![](img/image_rsrc8UX.jpg) |
| 图 5-9 显示了下拉菜单：`Participant Resolver` |

如果你的获取审批人需求复杂，你可以使用`Participation Resolver API`进行编程。我们将在下一章学习`Participation Resolver API`。

### 预期结果

在处理工作流时，我们应该始终意识到结果：批准或拒绝。例如，我们有一个包含 2 个标签页的管理任务：`Profile`标签页和`Access Role`标签页。我们有一个`Business Logic Task Handler`并设置了 3 个工作流：一个在管理任务级别，一个针对`ModifyUserEvent`，另一个针对`AssignAccessRoleEvent`。下面的图片显示了所有结果。

| ![](img/image_rsrc8UY.jpg) |
| 图 5-10 显示了所有结果示例 |

如果你使用`ProviderAccessor API`，你需要意识到`ProviderAccessor`直接更新用户存储，而不依赖于工作流。下面的图片显示 City 的初始值为多伦多。然后我们使用`ProviderAccessor API`将`City`属性修改为纽约。无论工作流被拒绝还是批准，市的最终值都是纽约。

| ![](img/image_rsrc8UZ.jpg) |
| 图 5-11 显示了`ProviderAccessor API`修改属性值 |

### 5.1.2 Workpoint Designer 概念

CA IdentityMinder 内部的工作流是由`WorkPoint Designer`工具创建的。`WorkPoint Designer`是第三方软件并与 CA IdentityMinder 集成。你可以通过命令`<admin_tools>\WorkPoint\bin\Designer.bat`运行`Workpoint Designer`。

| ![](img/image_rsrc8V0.jpg) |
| 图 5-12 显示了 Workpoint Designer 的启动界面 |

你需要检查配置文件`workpoint-client.properties`。该文件位于文件夹`<admin_tools>\WorkPoint\conf`中。`J2EE Client Configuration`必须与你的应用程序服务器匹配。

### 进程（Processes）与任务（Jobs）

Process 和 Job 是 Workpoint 的技术术语。

- `Processes`是业务进行并通常重复的功能。
- `Jobs`是进程实例。

例如，如果`Process`是订单履行流程的计划，那么具体的案例（或`Jobs`）就是实际的订单。`Process`类似于 Java 中的`Class`，而`job`是该 Java 类的对象或实例。

### 进程（Processes）

运行`Workpint Designer`，从菜单中选择“Open Process”。双击名为“SingleStateApproval”的进程，你将看到该流程。

| ![](img/image_rsrc8V1.jpg) |
| 图 5-13 显示了进程“SingleStateApproval” |

### 任务（Jobs）

从菜单中选择“Open Job”。双击名为“SingleStateApproval”的进程，你将看到该进程的任务。（如果你执行了某个包含工作流`SingleStateApproval`的管理任务）

| ![](img/image_rsrc8V2.jpg) |
| 图 5-14 显示了任务 |

### 使用帮助（Help）



点击菜单“Help”，帮助内容将以弹出窗口显示。你可以选择“process definition”和“job definition”。

| ![](img/image_rsrc8V3.jpg) |

|我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。图 5-15 显示了 Workpoint Designer |

另一个 Workpoint 位于`<admin_tools>\Workpoint\docs`。

## 5.2 自定义工作流

CA IdentityMinder 官方文档没有详细说明如何逐步创建工作流。本章的其余部分将展示如何创建自定义工作流。

### 为什么我们需要自定义工作流？

第一个原因是，默认模板工作流不符合我们的需求。例如，你可能需要 3 个审批人，而默认支持最多 2 个。

第二个原因是，我们需要与其他系统集成或在工作流期间执行某些业务逻辑。例如：

* 在工作流期间，我们需要调用 Web 服务。

* 如果用户位于北美，则需要第二个审批人。我们必须创建一个路由路径来检查用户位置。

本节包含 2 部分。

* CA IdentityMinder 的工作流：你将学习与 CA IdentityMinder 相关的的工作流规则。

* Workpoint 编程：我们将介绍一些 Workpoint API 功能。

### 5.2.1 工作流与 CA IdentityMinder

当你为 CA IdentityMinder 创建工作流时，必须遵循这些规则：

规则 1：必须以`Start`节点开始并以`Stop`节点结束。

这是一个合理的规则，工作流必须有起点和终点。在 Workpoint designer 中，你从菜单中拖入节点。

| ![](img/image_rsrc8V4.jpg) |

| 图 5-16 显示了 Workpoint Designer 中的 Start 和 Stop 节点 |

规则 2：在进入`Stop`节点之前，必须有`Approve`或`Reject`节点。

任何工作流，在完成工作流之前，都需要将状态设置为`Approve`或`Reject`。我们需要告诉 CA IdentityMinder 最终结果是批准还是拒绝。

拖入自动化节点并设置配置：（你将在示例代码中看到详细信息，不用担心）

* 在`resources`标签页中：选择 external

* 在`agents`标签页中，对于批准状态，选择`Notify IM Approver`；对于拒绝状态，选择`Notify IM Reject`

| ![](img/image_rsrc8V5.jpg) |

| 图 5-17 显示了 Stop 之前的批准和拒绝状态 |

工作流并不总是需要批准和拒绝，但工作流在节点停止之前至少有一个批准节点。（工作流只有一个拒绝节点是不逻辑的）

规则 3：审批人配置（如果你需要审批人）

如果你需要审批人，你必须：（你将在示例代码中看到详细信息）

* 将活动节点拖到画布上

- 在 resources（资源）选项卡中：选择`IMApprovers`

- 在 agents（代理）选项卡中：选择`Nobody AutoComplete`为异步 

- 在 user data（用户数据）选项卡中，设置下表中的值：（我们在示例“基础自定义工作流”中有详细的步骤说明。）

| Name | Type | Description |

| :--- | :--- | :--- |

| `ACTION_PERFORMED` | Text | 用于转换 |

| `PARTICIPANT_ID` | Text | 审批者 ID |

| `PARTICIPANT_NAME` | Text | 链接到属性文件 |

| `PARTICIPANT_DESCRIPTION` | Text | 链接到属性文件 |

### 规则 4：在管理任务级别运行工作流（可选）

默认情况下，工作流可以在事件级别运行。如果你想工作流在管理任务级别运行，你必须：

- 选择进程的用户 Data（用户数据）并添加`TASK_LEVEL = true`

### 5.2.2 Workpoint 组件

我们将介绍 Workpoint 设计器的基本组件。

### 活动节点 (Activity Node)

活动代表业务流程中的一个步骤。根据活动完成的方式，有 3 种类型的活动。节点的显示方式也不同。

| 节点 | 类型 | 说明 |

| :--- | :--- | :--- |

| ![](img/image_rsrc8V6.jpg) | 由人工自动 | 由人员完成，用于审批者。 |

| ![](img/image_rsrc8V7.jpg) | 由活动自动 | 需要特殊的代码来完成活动 |

| ![](img/image_rsrc8V8.jpg) | 由服务器自动 | WorkPoint Server 自动完成此活动 |

如果你需要审批者，请选择节点类型“Automated by a person（由人工自动）”。

如果你必须执行任何逻辑或调用后端，请选择节点类型“Automated by server（由服务器自动）”。例如，你有逻辑调用 Web 服务，当逻辑完成后，Workpoint 将移动到下一个节点。你不需要编写任何特殊代码。

如果你选择节点类型“Automated by activity（由活动自动）”来调用 Web 服务，逻辑完成后不会移动到下一个节点。进程将停止。你必须编写特殊代码来完成此节点的活动，然后 Workpoint 才会移动到下一个节点。（`Approve`和`Reject`节点具有完成活动的代码）

下图显示了 3 种活动/节点。

- 节点“App Admin”是活动：Automated by a person。

- 节点“Call Web Servcies”是活动：Automated by server。

- 节点`Approve`和`Reject`是活动：Automated by activity。

| ![](img/image_rsrc8V9.jpg) |

| 图 5-18 显示了 3 种活动 |

#### 转换 (Transition)

转换是工作流上连接两个不同节点的线。转换可以是无条件的，也可以是有条件的。条件转换关联有一个转换选择脚本。

我们使用转换作为工作流中的选择路径。下图显示了带有条件的转换。例如，如果部门（division）等于中心（central），则进入发送 ticket，然后发送邮件并完成工作流。

| ![](img/image_rsrc8VA.jpg) |

| 图 5-19 显示了 3 个条件转换。 |

#### 延迟节点 (Delay Node)

延迟代表业务流程中的暂停或挂起。例如，在配置过程中，我们创建了用户，但必须等待到入职日期，然后才能启用该用户。如果用户的城市是纽约，我们将在早上 6 点为用户添加角色。

| ![](img/image_rsrc8VB.jpg) |

| 图 5-20 显示了延迟的示例 |

#### 分类 (Category)

类别是对象的组。类别可用于过滤设计器内的告警、邮件、脚本、进程和节点模板的列表。类别可以帮助我们导入和导出工作流。

#### 参数 (Parameters)

当我们编写代码时，Workpoint 提供了一些参数：

- `ClientContext`：对于 CA IdentityMinder，`ClientContext`是构建`WorkflowContext`的一个必选参数。`WorkflowContext`是`ProviderAccessor` API 的子类。

- `SymbolTable`：它用于返回给 WorkPoint Server。我们通常在延迟节点中使用`SymbolTable`来回答延迟多久。

- `JobData`：它包含任务级的数据。我们使用`JobData`在节点之间共享数据。

- `ActivityInstData`：它包含节点级的数据。我们通常在转换中使用`ActivityInstData`。

## 5.3 代码示例

本章的示例将包含两个部分： 

- Workpoint 和代码

- 配置。

我们将使用上一章中的管理任务。请禁用上一章中与管理任务“Update Location and Ext number”相关的 Identity Policy Set、policy Xpress 和 Business Logic Task Handler API。

| ![](img/image_rsrc8VC.jpg) |

| 图 5-21 显示了管理任务 |

我们可以通过以下方式移除 Business Logic Task Handler：

- 搜索我们的管理任务名称：Update Location and Ext Number

- 点击“Business Logic Task Handlers”按钮，然后点击减号图标以移除 Business Logic Task Handlers

- 点击确定并提交。

| ![](img/image_rsrc8VD.jpg) |

| 图 5-22 显示了移除 Business Logic Task Handler 的图标 |

#### 5.3.1 工作流：单个审批者

我们将创建一个有一个审批者的基本工作流并将其部署到 CA IdentityMinder。此示例仍然不需要任何编程。

如果你不想创建工作流，可以导入我们的示例工作流，更多详细信息请参见附录 A：导入工作流。

Workpoint 和代码

1. 运行 Workpoint 设计器。

2. 点击顶部的菜单创建新进程

| ![](img/image_rsrc8VE.jpg) |

| 图 5-23 显示了“New Process” |

3. 在 general 选项卡中输入值：

| Name | Value |

| :--- | :--- |

| Example: OneApprover | 标识符 |

| Reference | 包含名称 |

点击确定。如下所示。

| ![](img/image_rsrc8VF.jpg) |

| 图 5-24 显示了 general 值 |

4. 根据规则 1，工作流必须从`Start`节点开始，并在`Stop`节点结束。从画布拖入节点。

| ![](img/image_rsrc8VG.jpg) |

| 图 5-25 显示了“Start”和“Stop” |

5. 根据规则 2，在`Stop`节点之前流程必须有`Approve`或`Reject`状态。从菜单拖入`Activity`。

| ![](img/image_rsrc8VH.jpg) |

| 图 5-26 显示了节点“Activity” |

点击节点（上图中的 Node3）并输入下表值：

| Tab | Field Name | Value | Description |

| :--- | :--- | :--- | :--- |

| General | Name | Approve | 名称字段包含活动名称 |

| Resources | Assignment | External | 资源识别执行活动的人或机器。对于 CA IdentityMinder，选择 External |

| Agents | Asynchronous | Notify Approve | 这是 CA IdentityMinder 的必选值。选择脚本`Notify Approve` |

| ![](img/image_rsrc8VJ.jpg) |

| 图 5-27 显示了带有脚本“Notify Approve”的 resources 和 agents 选项卡 |

接下来要做 Reject 状态（Node4）。它与审批活动相似，但脚本是`Notify Reject`。

| Tab | Field Name | Value | Description |

| :--- | :--- | :--- | :--- |

| General | Name | Reject | 名称字段包含活动名称 |

| Resources | Assignment | External | 对于 CA IdentityMinder，选择 External |

| Agents | Asynchronous | Notify Reject | 这是 CA IdentityMinder 的必选值。选择脚本`Notify Reject` |

| ![](img/image_rsrc8VK.jpg) |

| 图 5-28 显示了带有脚本“Notify Reject”的 agents 选项卡 |

完成此步骤后，我们的画布应该显示如下。

| ![](img/image_rsrc8VM.jpg) |

| 图 5-29 显示了画布 |

6. 对于审批者，在画布上拖入`Activity`节点

| ![](img/image_rsrc8VN.jpg) |

| 图 5-30 显示了活动节点 |

规则 3：如果我们有审批者，我们必须设置某些属性。右键点击审批者节点并选择属性。审批者节点需要如下配置：

| Tab | Field Name | Value | Description |

| :--- | :--- | :--- | :--- |

| General | Name | Approver | 名称字段包含活动名称 |

| Resources | Assignment | Any | 这是 CA IdentityMinder 的必选值。选择资源：`IMApprovers` |

| Include | IMApprovers | | |

| Agents | Agents | Nobody AutoComplete | （可选）在异步列表中选择“Nobody AutoComplete” |

| ![](img/image_rsrc8VP.jpg) |

| 图 5-31 显示审批者的资源 (resources) 标签页

代理标签页中的`Nobody AutoComplete`脚本是一个可选步骤。此脚本将计算审批者的数量。如果`approver`为`0`，此脚本将完成此节点并移动到下一个节点。

| ![](img/image_rsrc8VR.jpg) |

| 图 5-32 显示审批者的可选步骤、代理 (agents) 标签页

表格显示了用户数据 (user data) 标签的值。

| Name | Type | Value |

| :--- | :--- | :--- |

| `ACTION_PERFORMED` | Text | none |

| `PARTICIPANT_ID` | Text | Approval |

| `PARTICIPANT_NAME` | Text | imstask.label.singlestepapproval.approvalstep.name |

| `PARTICIPANT_DESCRIPTION` | Text | imstask.label.singlestepapproval.approvalstep.description |

| ![](img/image_rsrc8VS.jpg) |

| 图 5-33 显示审批者的用户数据 (user data) 标签页

属性`PARTICIPANT_NAME`和`PARTICIPANT_DESCRIPTION`链接到属性文件`<server>/IdentityMinder.ear/custom/resourceBundle/IMSResources.properties`。

```
SingleStepApprovalimstask.label.singlestepapproval.approvalstep.name=Primary Approver
imstask.label.singlestepapproval.approvalstep.description=Identity Manager sends the first request to the primary approver. If found, the primary approver can approve or reject the task or event.
```

当您设置`approver`时，这些属性值将显示在屏幕上。您可以添加新属性并将其设置为`approver`节点。

| ![](img/image_rsrc8VT.jpg) |

| 图 5-34 显示屏幕上的属性值

### 7. 拖拽转换 (Transition) 连接节点

- 从`Approve`到`Stop`节点，定义为`Unconditional`（无条件）

- 从`Reject`到`Stop`节点，定义为`Unconditional`（无条件）

- 从`Start`到`Approver`节点，定义为`Unconditional`（无条件）

- 并且拖拽从`Approver`到`Approve`节点的连接，定义类型为条件。选择现有脚本：`Approved`。

| ![](img/image_rsrc8VU.jpg) |

| 图 5-35 显示转换 (transition) 的属性

- 拖拽从`Approver`到`Reject`节点的连接，定义类型为条件。选择现有脚本：`Rejected`。所有连接显示如下所示。

| ![](img/image_rsrc8VV.jpg) |

| 图 5-36 显示完整工作流

### 8. 我们想在管理员任务级别查看此工作流。在画布上右键点击并选择`User Data`标签页。选择类型`Text`，输入名称：`TASK_LEVEL`值为`true`并点击`Add`。

| ![](img/image_rsrc8VW.jpg) |

| 图 5-37 显示进程的属性

点击保存按钮。![](img/image_rsrc8VX.jpg) 此工作流将自动部署到 CA IdentityMinder。

### 配置

工作流配置有 2 种方式：管理员任务级别事件级别。本示例将使用管理员任务级别的工作流。

5. 以管理员身份登录 Identity Manager 用户控制台。

6. 选择标签页`Roles`和`Tasks`，并选择菜单`modify admin task`。



7. 搜索我们的管理员任务名称：`Update Location and Ext Number`。

8. 验证 `Workflow`我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。复选框已勾选。

9. 选择图标 `pencil` 以添加工作流。

| ![](img/image_rsrc8VY.jpg) |
| --- |
| 图 5-38 显示在管理员任务中启用工作流 |

10. 选择我们的工作流 `Example: One Approver`。如果您没看到工作流，说明您可能漏掉了添加工作流属性的步骤（`TASK_LEVEL=true`）。

11. 对于 `Approval Task`（审批者屏幕），选择 `Approve Admin Task`。

12. `Participant Resolver` 是谁是审批者。选择 `List of Users` 并选择 `Add Users`。选择一个审批者。您可以使用自己的用户作为审批者。

13. 点击 `OK` 按钮然后再次提交以完成任务修改。

| ![](img/image_rsrc8VZ.jpg) |
| --- |
| 图 5-39 显示管理员任务中的工作流配置 |

## 如何工作

我们可以按照以下步骤执行我们的工作流：

1. 以管理员身份登录 Identity Manager 用户控制台。

2. 选择标签页：`Book Example` 并从 `Book Example` 标签页选择管理员任务：`Update Location and Ext Number`，然后搜索并选择一些用户。

3. 修改 `city` 属性并提交管理员任务。

提交任务后，您将看到消息 `Alert: Task pending`。这意味着工作流正在异步阶段运行。

### 审批过程

1. 提交后，如果您以 `approver` 身份登录，将看到等待审批的列表。

| ![](img/image_rsrc8W0.jpg) |
| --- |
| 图 5-40 显示任务等待审批 |

2. 当您点击此任务内部时，您将看到 `approve` 或 `reject` 按钮。点击 `approve` 按钮。

| ![](img/image_rsrc8W1.jpg) |
| --- |
| 图 5-41 显示带有 `approve` 和 `reject` 按钮的审批者任务 |

### 在查看提交的任务屏幕查看工作流作业

在 `System` 标签页下选择 `View submitted task`，选择我们的任务。

| ![](img/image_rsrc8W2.jpg) |
| --- |
| 图 5-42 显示查看提交任务中的我们的任务 |

点击 `pencil` 图标查看详情。在 `Task View` 区域看到我们的工作流。

| ![](img/image_rsrc8W3.jpg) |
| --- |
| 图 5-43 显示查看提交任务中的任务 |

### 在 Workpoint 设计中查看工作流作业

在 `Workpoint` 中选择 `Jobs`。这显示工作流 ID。

| ![](img/image_rsrc8W4.jpg) |
| --- |
| 图 5-44 显示管理员任务级别的工作流 |

| ![](img/image_rsrc8W5.jpg) |
| --- |
| 图 5-45 显示工作流 |

### 5.3.2 工作流：按城市延迟

此示例显示了高级技术。如果 `city` 等于 `New York`，将延迟 10 分钟。否则，则不会。

| ![](img/image_rsrc8W6.jpg) |
| --- |
| 图 5-56 显示工作流 |

#### Workpoint 和代码

1. 选择 `File > New Process`。

2. 在 `general` 标签页输入值。

| Field Name | Value | Description |
| --- | --- | --- |
| `Name` | `Example : Delay` | 名称字段标识工作流 |
| `Reference` | `BookEx` | 引用字段包含唯一名称 |

| ![](img/image_rsrc8W7.jpg) |
| --- |
| 图 5-47 显示 general 中的值 |

3. 根据规则 1，流必须从 `Start` 节点开始并以 `Stop` 节点结束。

| ![](img/image_rsrc8W8.jpg) |
| --- |
| 图 5-48 显示 `Start` 和 `Stop` 节点 |

4. 根据规则 2，流在 `Stop` 节点之前必须有 `Approve` 或 `Reject` 状态。拖入 `Activity` 节点。我们的需求不需要 `reject`，所以我们拖入了一个节点。配置为 `Commit`。

| Field Name | Value | Description |
| --- | --- | --- |
| `General` | `Commit` | 名称字段包含活动名称 |
| `Resources` | `External` | 对于 CA IdentityMinder，选择 `External` |
| `Agents` | `Asynchronous` | `Notify IM Approve`。这是 CA IdentityMinder 需要的。选择脚本 `Notify IM Approve` |

提示：你可以使用 `CRLT+C` 从其他进程复制 `Approved` 节点并粘贴到我们的工作流。

6. 将 `Delay` 节点拖入画布。

| ![](img/image_rsrc8W9.jpg) |
| --- |
| 图 5-49 显示 `Delay` 节点 |

双击 `Activity` 节点（图中节点 4）并添加如下配置：

| Field Name | Value | Description |
| --- | --- | --- |
| `General` | `Delay 10 Minutes` | 名称字段包含活动名称 |

在 `Evaluation Date` 标签页中，脚本 `Calculated Delay`。点击图标 `new` 创建新脚本。

![](img/image_rsrc8WA.jpg)

图 5-50 显示创建新脚本的图标。

在 `general` 标签页中，将名称设置为 `Delay 10 Minutes` 并选择标签 `Statement`。

| Tab | Field Name | Value |
| --- | --- | --- |
| `General` | `Delay 10 Minutes` | |
| `Statements` | `Statement Type` | `Java` |
| `Java Class` | `com.book.idm.workflow.DelayForNYFlow` | |
| 方法 | `delay10Minutes` | |
| 参数 | `SymbolTable` | |

| ![](img/image_rsrc8WB.jpg) |
| --- |
| 图 5-51 显示了脚本界面。 |

我们需要参数 `SymbolTable`，因为我们的 Java 代码将结果延迟时间设置到了对象 `SymbolTable` 中。

7. 将“Server Automated（服务器自动化）”拖动到画布上。我们将编写一些业务逻辑。

| ![](img/image_rsrc8WC.jpg) |
| --- |
| 图 5-52 显示了节点 server automated |

双击节点（图片中的 `Node 5`）并按如下所示添加配置：

| 标签页 | 字段名 | 值 | 描述 |
| --- | --- | --- | --- |
| General（通用） | Name | Check City Value | Name 字段包含名称。 |
| Resources（资源） | Assignment（分配） | External（外部） | 此工作分配选项允许外部应用程序将资源分配插入到 WorkPoint 数据库。 |

选择 `agents` 标签页，点击 `new` 按钮添加新脚本。

| 标签页 | 字段名 | 值 |
| --- | --- | --- |
| General | Name | IsNewYorkCity |
| Statements | Statement Type | Java |
| Java Class | `com.book.idm.workflow.DelayForNYFlow` | |
| Method | `checkCityValue` | |
| Parameters | `ClientContext, ThisJobData, ThisActivityInstData` | |

然后点击 `ok` 完成新脚本创建。

| ![](img/image_rsrc8WD.jpg) |
| --- |
| 图 5.53 显示了新脚本界面 |

点击 `user data（用户数据）` 标签页，我们将为转换添加值。User Data 允许以名称/值数据对的形式保存自定义应用程序数据。在我们的需求中，我们希望在用户数据中保留城市值。

| Name | Type | Value |
| --- | --- | --- |
| `city` | `Text` | `none` |

对于初始值，我们将值设为 `none`。我们将在稍后的编程部分进行详细介绍。

| ![](img/image_rsrc8WE.jpg) |
| --- |
| 图 5-54 显示了用户数据 |

点击“add（添加）”按钮，然后点击 `ok` 完成。

8. 拖动转换并在节点之间定义类型为 `unconditional（无条件）`：

- 从“Start（开始）”到“Is New York City”节点。
- 从“Delay 10 Minutes”到 Commit（提交）”节点。
- 从“Commit”到“Stop（停止）”节点。

| ![](img/image_rsrc8WF.jpg) |
| --- |
| 图 5-55 显示了节点之间的转换 |

9. 我们将为城市等于 New York 时定义条件转换。

- 将转换从“Is New York City”拖动到“Delay 10 Minutes”节点。
- 选择类型：`Conditional（条件判断）`。
- 选择创建新脚本。
- 输入名称：`City == New York`。
- 点击 `next（下一步）` 按钮。

| ![](img/image_rsrc8WG.jpg) |
| --- |
| 图 5-56 显示了条件转换界面 |

- 点击第一列：左操作数，选择 `SourceActivity.UD.city`。
- 第二列：比较，选择 `String =`。
- 第三列：右操作数，输入值 `new york`。
- 点击 `finish（完成）` 完成该步骤。

| ![](img/image_rsrc8WH.jpg) |
| --- |
| 图 5-57 显示了条件转换语句界面 |

在此步骤中，我们创建了条件。如果 `SourceActivity.UD.city == new York`，则走此路径。

10. 我们必须在城市不等于 New York 时定义另一个条件转换。

- 将转换从“Is New York City”拖动到 Commit 节点。
- 选择类型：`Conditional`。
- 选择创建新脚本。
- 点击 `next` 按钮。
- 输入名称：`City != New York`。
- 点击第一列：左操作数，选择 `SourceActivity.UD.city`。
- 第二列：比较，选择 `String !=`。
- 第三列：右操作数，输入值 `new york`。
- 点击 `finish` 完成该步骤。

| ![](img/image_rsrc8WJ.jpg) |
| --- |
| 图 5-58 显示了条件转换语句界面 |

11. 点击 `save（保存）` 图标，整个工作流应如下所示。

| ![](img/image_rsrc8WK.jpg) |
| --- |
| 图 5-59 显示了完整的工作流 |

12. 将 Java 类复制到文件夹“custom”中。（与 Business Logic Task Handler 代码位于同一文件夹）

- `com.book.idm.workflow.DelayForNYFlow`
- `com.book.idm.workflow.WorkpointHelper`

我们稍后将详细介绍 Java 代码。

### 配置

在此示例中，我们将在事件级别指定我们的工作流。

1. 搜索我们的管理任务名称：`Update Location and Ext Number`。

2. 确保选中了 `Enable Workflow（启用工作流）` 复选框，并移除之前的示例工作流以防混淆。

| ![](img/image_rsrc8WM.jpg) |
| --- |
| 图 5-60 显示了启用工作流选中框和移除之前的工作流 |

3. 选择 `events` 标签页并点击事件 `ModifyUserEvent` 的 `pencil（铅笔）` 图标。

4. 选择我们的工作流 `Example: Delay for NY`。

5. 点击 `OK` 按钮然后再次提交以完成任务修改。

| ![](img/image_rsrc8WN.jpg) |
| --- |
| 图 5-61 显示了 ModifyUserEvent 中的工作流。 |

### 工作原理

1. 以管理员身份登录 Identity Manager 用户控制台。

2. 选择标签页：`Book Example` 并选择管理任务：“Update Location and Ext Number”，然后搜索并选择一些用户。

3. 修改城市属性并提交管理任务。

#### 查看已提交的任务

在“System”标签页下选择“View submitted task（查看提交的任务）”，选择我们的任务。点击 `pencil` 图标查看详情。

| ![](img/image_rsrc8WP.jpg) |
| --- |
| 图 5-62 显示了任务 |

滚动到“Event”部分查看 ModifyUserEvent。

| ![](img/image_rsrc8WR.jpg) |
| --- |
| 图 5-63 显示了任务 |

在“View Event”中点击图标查看工作流。如果更改城市为 New York，将进入此路径。

| ![](img/image_rsrc8WS.jpg) |
| --- |
| 图 5-64 显示了任务，当城市为 New York 时 |

如果更改城市为其他值，将等待 10 分钟。

#### `Delay 10 Minutes`

节点具有以下配置：

- 在 `user data` 标签页中，设置 `city=none`。
- 在 `agents` 标签页，选择脚本 `IsNewYorkCity`。
- Java 类：`com.book.idm.workflow.DelayForNYFlow`
- 方法：`checkCityValue`
- 参数：`ClientContext, ThisJobData, ThisActivityInstData`

| ![](img/image_rsrc8WT.jpg) |
| --- |
| 图 5-65 显示了自动化节点的配置 |

在 `checkCityValue` 方法中，参数顺序和值必须完全匹配（`ClientContext, JobData,ActivityInstData`）。

- `ClientContext` 需要构建 `WorkflowContext`。
- `JobData` 需要构建 `WorkflowContext`。
- `ActivityInstData` 用于访问用户数据标签页中的 `city`。

```java
public void checkCityValue(ClientContext clientContext, JobData thisJobData,ActivityInstData thisactivityInstData){
    User user = null;
    WorkflowContext workflowContext = null;
    try{
        //获取上下文
        workflowContext = WorkpointHelper.getWorkflowContext(clientContext,thisJobData);
        user = WorkpointHelper.getUser(workflowContext);
        System.out.println("City : New Value ="+user.getAttribute("l"));
        System.out.println("City : Old Value ="+user.getLastCommitted("l"));
        //将新值放入用户数据
        thisactivityInstData.setUserData("city",user.getAttribute("l").toLowerCase());
    } catch(Exception e){
        e.printStackTrace();
    }
}
```

我们必须获取 `WorkflowContext`。`WorkflowContext` 是与 CA IdentityMinder 交互的主 API。

```java
workflowContext = WorkpointHelper.getWorkflowContext(clientContext,thisJobData);
```

CA IdentityMinder 提供了 `WorkflowCallbackHelper`。使用 `generateWorkflowContext()` 获取工作流上下文。创建一个工具类 `WorkpointHelper` 和方法 `generateWorkflowContext`。你可以在项目中复用该类。

`WorkflowCallbackHelper.generateWorkflowContext` 需要 `2` 参数：`ims-id` 和 `ime-id`。这些 ID 在任务创建时生成。你可以搜索该任务（流程实例），在画布上点击右键，并查看任务的用户数据（user data）标签页。我们的代码通过 `queryByID()` 方法获取当前任务，然后通过 `getUserData()` 方法获取 `ims-id` 和 `ime-id`。



顺便提一下，代码获取`WorkflowContext`的模式，你只需复制并复用即可。

| ![](img/image_rsrc8WU.jpg) |

图 5-66 显示了用户数据标签页中的`ims-id`和`ime-id`。

下一行显示了如何从流程上下文获取`User`对象。我们创建了工具方法`getUser()`来返回用户对象。

```java
user = WorkpointHelper.getUser(workflowContext);
```

我们使用方法`getSubject()`返回管理员任务的主对象。我们的管理员任务以`User`为主对象。如果你尝试在主对象不是用户的管理员任务中调用此方法，你将会得到错误。

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

`WorkflowContext`扩展了`IMContext`、`IMPersistentContext`、`ProviderAccessor`、`ServiceProvider`和`TaskInfo`。更多细节请参考官方 Java 文档。它与`BLTHContext`相似，不同在于`WorkflowContext`扩展了`EventContext`。

请注意流程有两个`2`级：管理员任务级别、事件级别。如果你的流程运行在管理员任务级别，并尝试调用父类`EventContext`的任何方法，将得到意外的结果。

我们有另一个方法`getUser(EventContext context)`。你必须确保你的流程运行在用户事件。下面的代码显示了如何从事件获取用户对象。

```java
IMEvent evt= workflowContext.getEvent();
User user = ((UserEvent)evt).getUser();
```

我们在`WorkpointHelper.java`中的方法`getUser()`可以在你的项目中复用。我们对流程编程有额外的说明。

**注意 1：`WorkflowContext`正确调用来自父类（`EventContext`）的方法。**

- 如果流程运行在管理员任务级别，不要调用来自父类`EventContext`的方法。
- 确保执行了正确的类型转换。例如：
  - 流程关联到事件`ModifyUserEvent`，你可以通过`UserEvent`转换对象（`ModifyUserEvent`是`UserEvent`的子类）。

```java
User user = ((UserEvent)evt).getUser();
```

  - 流程关联到事件`AddToGroupEvent`，你可以通过`GroupEvent`转换（`AddToGroupEvent`是`GroupEvent`的子类）。

```java
Group group = ((GroupEvent)evt).getGroup();
```

这与`BLTHContext`相同，在使用方法`getSubject()`时，请检查管理员任务的主对象是什么。

代码的下一行打印值。它演示了如何访问新值和旧值。

```java
System.out.println("City : New Value ="+user.getAttribute("l"));
System.out.println("City : Old Value ="+user.getLastCommittedAttribute("l"));
```

下一行代码显示了如何在用户数据标签页中设置值。在用户数据标签页中，我们添加键值对（city=none）。这段代码将值修改为新用户的城市属性。

```java
// 将新值放入用户数据
thisactivityInstData.setUserData("city",user.getAttribute("l").toLowerCase());
```

`Transition`使用用户数据中的城市来决定路径。如果发生异常（默认值为“none”），它将进入“City != New York”路径。因此，你应该意识到流程内部的异常。

| ![](img/image_rsrc8WV.jpg) |

图 5-67 显示了用户数据与跳转（transition）之间的关系。

### Transition（跳转）

`Transition`是节点之间的连接。你可以通过点击条件标签页中的铅笔图标来编辑跳转中的条件。

| ![](img/image_rsrc8WW.jpg) |

图 5-68 显示了编辑条件的铅笔图标。

在我们的示例中，我们使用了条件向导。在条件标签页中，有许多创建条件的方法。你也可以进行编程（但不推荐）。

提交后无法编辑条件，但你可以更改语句类型或删除此脚本并创建一个新的。（某些情况下，由于存在某些引用，你无法删除，如果你不想删除引用，我建议更改名称。）

| ![](img/image_rsrc8WX.jpg) |

图 5-69 显示了跳转中语句类型的列表。

#### 带有 Java 代码的跳转条件

你可以在跳转中使用 Java 代码；你需要向符号表中设置最终结果为 TRUE 或 FALSE。`Transition`将引用`SymbolTable`中“Result1”的值来决定路径。例如，跳转“City == New York”，我们可以编写如下代码：

```java
boolean result = false;
if(city.equalsIgnoreCase("new york")){
    result = true;
} 
symbolTable.add("Result1").setValue(0,result);
```

关于`SymbolTable`类的更多细节，请参阅 Workpoint 帮助文档。

我们需要从节点“Check City Value”的用户数据中获取城市值。`transition`是“源节点”和“目标节点”之间的连接。

| ![](img/image_rsrc8WY.jpg) |

图 5-70 显示了跳转的源和目标。

有`2`种从源节点的用户数据中访问城市值的方法。

**第一种方法：传递参数。**你必须放入`SourceActivity.city`。`SourceActivity`是源节点，`UD`是用户数据。

| ![](img/image_rsrc8WZ.jpg) |

图 5-71 显示了参数中的`SourceActivity.UD`。

```java
public void isCityEqualYork(String city, SymbolTable symbolTable, JobData thisJobData, JobTranData jobTransData){
// 根据城市在符号表中设置 Result1
    System.out.println("Get city by SourceActivity :"+city);
}
```

**第二种方法，通过源节点查找。**这种方法需要两个参数：`JobData`和`JobTranData`。

| ![](img/image_rsrcX0.jpg) |

图 5-72 显示了参数中的`JobData`和`JobTranData`。

`ThisJobData`是流程实例。`ThisTransitionData`是该跳转的实例。下面的代码显示了如何从源节点访问用户数据。

```java
ID sourceNodeID = jobTransData.getSourceNodeID();
ActivityInstData sourceActivity = thisJobData.getActivityByNodeID(sourceNodeID);
String cityUD = sourceActivity.getUserData("city").getVariableValue();
System.out.println("Get city by sourceNodeID :"+cityUD);
```

**注意 2：保持跳转条件简单**

建议是保持跳转条件简单。你应该使用条件向导。避免在跳转中使用复杂的逻辑。例如，有两个跳转：“City == New York”和“City != New York”。如果你在“City == New York”跳转中进行编程，你需要在另一个跳转中也进行编程。这意味着你要做两次。

建议在源节点中进行逻辑处理或计算，并在用户数据中保留原始结果。`transition`只使用结果来决定路径。这样更容易维护。

### Delay（延迟）

延迟的概念非常直观：你希望该节点持续多久。你只需在`SymbolTable`的`result1`中放入格式为“yyyy-MM-dd HH:mm:ss”的日期时间值。

```java
public void delay10Minutes(SymbolTable symbolTable){
    Date current = new Date();
    Calendar calendar = Calendar.getInstance();
    calendar.setTime(current);
    calendar.set(Calendar.MINUTE, calendar.get(Calendar.MINUTE)+10);
    SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
    String executeTime = simpleDateFormat.format(calendar.getTime());
    SymbolData r1 = symbolTable.add("Result1");
    r1.addValue(executeTime);
}
```

`Delay`节点通过评估日期标签页中的配置支持延迟时间。更多细节请参见 Workpoint 文档。

### Node 节点

我们有一个规则：在完成流程之前必须进行通过或拒绝。在我们的示例中，我们只需要一条路径。所以我们只需要通过状态，但我们将其命名为“Commit”。

# 工作流错误

有时，你在工作流上进行编程时会遇到一些错误。你应该取消任务或事件。我们不应该在系统中留下未完成的流程。你可以在`View Submitted task`（查看提交的任务）中取消。

| ![](img/image_rsrc8X1.jpg) |

图 5-73 显示了提交任务界面中的取消事件按钮。

## 5.3.3 分类（Category）

`Category`是对象的组。我们可以使用`Category`来过滤对象。这对于管理工作流非常有帮助。在本示例中，你将学习：

- 如何创建分类并将对象添加到分类中。
- 使用库搜索对象。
- 导出工作流。

### 创建分类

1. 点击菜单`Library`（库）>`Category`（分类）。

| ![](img/image_rsrc8X2.jpg) |

图 5-74 显示了库菜单中的分类菜单。

2. 点击`new`按钮并输入名称“BookExample”。

| ![](img/image_rsrc8X3.jpg) |

图 5-75 显示了新建按钮。

### 将对象添加到分类中

选择我们的进程和脚本并添加分类。

- 进程（Process）
  - 在画布上右键点击。
  - 选择`properties`（属性）并选择标签页：`category`（分类）。
  - 选择“BookExample”并点击添加按钮。
- `Node`（活动、自动化、服务器自动化、延迟、转换），不需要操作，它将遵循进程的分类。
- `Node`内部或转换中的脚本
  - 编辑`script`（脚本）。
  - 选择标签页`category`。
  - 选择“BookExample”并点击添加按钮。

| ![](img/image_rsrc8X4.jpg) |

图 5-76 显示了脚本的分类。

### 通过分类过滤

添加分类后，我们可以在转换的条件或节点的代理中进行过滤。

| ![](img/image_rsrc8X5.jpg) |

图 5-77 显示了用于过滤的分类按钮。

### 导出工作流

我们可以导出工作流并导入到 UAT 或生产环境。

- 选择菜单`File`（文件）>`Export`（导出）。
- 输入文件名并点击`next`（下一步）。
- 你可以使用`category`进行过滤。
- 我们通常导出完成过的对象：`Category`、`Process`和`Script`。

| ![](img/image_rsrc8X6.jpg) |

图 5-78 显示了导出菜单和按分类过滤的导出屏幕。

请参阅`appendix A`，关于导入工作流的详细信息。

## 5.4 工作点编程

现在你已经学习了一些工作点示例。这一部分在你学习了一些示例代码后，包含了额外的概念。

### 5.4.1 活动、服务器自动化和自动化

有 3 种节点：`Activity` ![](img/image_rsrc8X7.jpg)、`Server Automated` ![](img/image_rsrc8V8.jpg)和`Automated` ![](img/image_rsrc8V7.jpg)。我们有 3 种活动、自动化和服务器自动化。在`general`（常规）标签页中有复选框。下图显示了复选框与节点类型之间的关系。

| ![](img/image_rsrc8X8.jpg) |

图 5-79 显示了复选框与节点类型之间的关系。

### 5.4.2 服务器自动化和自动化的脚本

`Server Automated` ![](img/image_rsrc8V8.jpg)和`Automated` ![](img/image_rsrc8V7.jpg)的`Script`是不同的。如果你使用`Automate`节点实现业务逻辑，你必须编写额外的代码通过代码完成活动。下图显示我们使用`Automate`节点“Check City Value”，且流程在逻辑完成后没有继续移动。

| ![](img/image_rsrc8X9.jpg) |

图 5-80 显示流程停在自动化节点处没有继续移动。

我们可以通过添加完成活动的代码来修复上面的图片。

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

**注意 3：使用服务器自动化实现业务逻辑。（建议）**

此主题，我们建议使用服务器自动化。你不需要担心完成活动。

### 5.4.3 代理脚本可以指定为同步或异步

让我们了解工作流中的同步或异步是什么：

- `Synchronous Scripts`（同步脚本）意味着资源的脚本、同步代理脚本和状态规则。
- `Asynchronous Scripts`（异步脚本）意味着异步代理脚本、邮件脚本和报警脚本。

`Agent scripts`（代理脚本）通常用于更改数据库或调用操作。`Agent script`可以是同步的也可以是异步的。

| ![](img/image_rsrc8XA.jpg) |

图 5-81 显示了代理脚本界面。

同步代理脚本与状态更改在同一个事务中执行。异步代理脚本在状态更改事务之外执行，因此是独立完成。所以有一些需要知道的事：

- 如果你使用脚本修改节点的`User Data`（用户数据），脚本必须在同步模式下执行。
- 如果你想完成活动，脚本必须在异步模式下执行。

**注意 4：服务器自动化的代理脚本应指定为同步。**当你执行业务逻辑时，请指定你的脚本类型。

### 5.4.4 保存作业对象

在官方文档：编程指南中，`Workflow API`下有一个`Saving Objects`（保存对象）主题。

什么是保存对象？

`Job`是进程的实例。`Saving object`意味着保留某些值以便在内部节点之间共享。例如：

- 你有节点 1 连接到节点 2，节点 2 连接到节点 3。
- 节点 1 修改值`X =1`。
- 节点 3 可以看到值`X`。

因此我们必须在进程的用户数据中声明变量`X`。在画布上右键点击，选择`user data`标签页并输入名称。这与工作流时的步骤相同。

| ![](img/image_rsrc8XB.jpg) |



## User Data我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。图 5-82 显示了进程中的 `user data` 标签页。

官方文档告诉在异步模式下保存 `User Data` 时要注意缓存。这需要特殊的代码。

所有同步脚本必须使用 `ThisJobData` 或 `ThisActivityInstData` 来获取 `User Data`。

![](img/image_rsrc8XC.jpg)

图 5-83 同步脚本从参数访问作业。

对于只读，你可以使用 `ThisJobData` 或 `ThisActivityInstData`。当你想在异步脚本中保存作业时，必须编写如下代码：

```java
var jobTableId = ThisJobData.getJobID();
var job = Job.queryByID(ClientContext,jobTableId,true);
job.setUserData("Test","Pass");
job.save();
```

### 5.4.5 搜索引用

有时由于引用，无法删除某些对象。例如，你想删除脚本，但因为引用报错。你想知道哪些进程或作业使用了该脚本。点击菜单 `library > scripts`，并在 `script` 上右键，选择 `search references`（搜索引用）或 `search dialog`（搜索对话框）。搜索对话框提供了更多选项，如果你想搜索作业，请勾选对话框中的 `jobs` 选框。

![](img/image_rsrc8XD.jpg)

图 5-84 显示了搜索引用。

注意 5：在删除进程之前删除相关作业。

如果你在删除作业之前删除进程，删除脚本将会变得复杂。你选择脚本并搜索引用；你会看到一些作业引用脚本。由于你已经删除了进程，无法访问所有相关作业。你必须逐个打开并删除每个作业。

所以我们建议在删除进程之前删除所有相关作业。

## 5.5 用例示例

CA IdentityMinder 官方文档讨论了用例示例。请参见 `Programming Guides › Programming Guide for Java › Workflow API › Workflow API Overview › Use Case Examples` 了解完整细节。

### 根据 User 对象属性确定工作流方向

`CreateUserEvent` 工作流过程中的第一个活动是一个自动化活动，该活动引出了三个条件条件跳转。每个跳转中的条件脚本会从事件包含的 `User` 对象中获取 `email` 属性。工作流过程执行的下一个活动由条件脚本的结果决定，如下：

- 跳转到 `CA.COM SUFFIX` 指向一个审批者：`HR Manager`（HR 经理）。
- 跳转到 `SECURITY.COM SUFFIX` 指向两个审批者：`HR Manager` 和 `IT Manager`（IT 经理）。
- 跳转到 `EMAIL INVALID` 拒绝工作流。

文档提到在每个跳转中使用条件脚本来获取 `email`。你可以使用 Java 代码编写跳转的条件。

![](img/image_rsrc8XE.jpg)

图 5-85 显示了用例的工作流。

### 在工作流过程中更新 CA IdentityMinder 对象

在以前的用例示例中，假设跳转 `CA.COM SUFFIX` 的条件脚本已更新更新，用以检查 `email` 属性是否为空。如果为空，脚本将根据用户的 ID 和默认后缀 `ca.com` 构建电子邮件地址。脚本将该地址分配给 `User` 对象的 `email` 属性。然后脚本返回 `true`，并按照上例执行跳转。当 `CA IdentityMinder` 完成事件执行时，将保存更新的对象。

这里有两个有趣点：

- 跳转 `CA.COM SUFFIX` 的条件脚本被更新更新，用以检查 `email` 属性是否为空。
  - 你可以在跳转 `CA.COM SUFFIX` 的条件脚本内部执行该逻辑。
- 脚本将地址分配给 `User` 对象的 `email` 属性。
  - 我们可以通过 `ProviderAccessor` 和 `Workflow Context` 将地址分配给 `email` 属性。在这种情况下，由于两个原因，我们必须使用 `Workflow context`。第一个原因是 `CreateUserEvent`。我的意思是，事件完成之前用户尚未被创建。第二个原因是，此工作流需要审批者。如果被拒绝，我们必须考虑结果。

我们计划在 `workflow context` 中修改 `email` 属性，在创建管理任务时，你必须确保在 `fields` 标签中定义了 `email` 属性。

### 使用第三方数据从工作流过程中验证对象

`CreateUserEvent` 的工作流过程包含一个自动化活动，该活动从第三方数据库获取新用户的信用评分。首先，活动脚本调用 `Workflow API` 获取事件以及事件中的 `User` 对象。然后，在脚本获取用户的信用评分后，它使用工作流引擎的 API 将信用评分写入活动的 `User Data` 中，并最终完成活动。从该活动的跳转脚本随后使用 `workflow engine’s API` 从 `User Data` 中获取信用评分并对其进行评估，以确定工作流过程的后续步骤。

我们可以使用服务器自动化（server automated）脚本来调用第三方数据。例如，你调用第三方获取类型并确定路径。

![](img/image_rsrc8XF.jpg)

图 5-86 显示工作流调用第三方数据。

## 5.6 结论

在本章中，你学习了 `workflow context API` 或如何创建自定义工作流。我们可以将工作流的概念总结为：

**创建工作流前的检查列表：**

- 工作流的级别是什么？`admin task level`（管理任务级）或 `event level`（事件级）。
- 哪个工作流？从 3 个默认工作流中选择还是创建一个新的自定义工作流？
- 工作流开始前需要策略（或条件）吗？
- 审批者使用哪个屏幕（任务）？
- 谁是审批者？
- 结果是什么？

**自定义工作流的规则：**

- 规则 1：必须以 `Start` 节点开始并以 `Stop` 节点结束。
- 规则 2：在进入 `Stop` 节点之前必须有 `Approve`（通过）或 `Reject`（拒绝）。
- 规则 3：`Approver Configuration`（审批配置，如果你需要审批者）。
- 规则 4：管理任务层级的工作流（可选）。

**自定义工作流的注意事项：**

- 注意 1：`WorkflowContext` 正确调用来自父类（`EventContext`）的方法。
- 注意 2：保持跳转条件的简单性。
- 注意 3：使用 `server automated` 实现业务逻辑。（建议）
- 注意 4：`server automated` 的 `Agent script` 应被指定为同步。
- 注意 5：在删除进程之前删除相关作业。

你可能认为 `workflow API` 很难，我建议你只需记住本章中的规则和注意事项。对于编程细节，请参阅书籍第二卷，其中包含大量示例。你会熟悉它的。业务逻辑任务处理器和工作流在实际项目中非常有用。在下一章，我们将介绍剩余的 API。

# 第 6 章：其他 API

我们学习了用于开发业务逻辑的两个主要 API：同步阶段下的 `business logic task handler` 和异步阶段下的 `workflow`。本章中的这些 API 是实现目标的工具。

本章中有许多细节。你可能不需要关注所有的 API。我的观点是，我在下表中给出了总结：

| API 名称 | 频率 | 目的 |
| :--- | :--- | :--- |
| `Participant Resolver API` | 有时 | 决定谁是审批者 |
| `Event Listener API` | 经常 | 事件发生时执行自定义业务逻辑 |
| `Logical Attribute API` | 罕见 | 在物理属性和逻辑属性之间转换 |
| `Validation Rules` | 有时 | 验证值 |
| `Email & Notification Rule API` | 有时 | 发送电子邮件 |
| `Task Execution Web Service` | 有时 | 启用管理任务作为 Web 服务 |

## 6.1 Participant Resolver API

`Participant Resolver API` 是工作流的一部分。`Participant Resolver API` 决定工作流中的审批者。审批者是授权审批工作的人。

如果工作流需要审批（例如 `SimpleApproval`），你需要在配置中选择审批者。

![](img/image_rsrc8G.jpg)

图 6-1 显示审批者界面。

`CA IdentityMinder` 为审批者提供了配置条件，更多详情请参见文档“审批者类型”。当不支持配置条件时我们需要审批者。

### 6.1.1 编程

使用 `Participant Resolver API`，你必须创建一个自 `ParticipantAdapter` 的类并重写 `resolve()` 方法。返回值是参与者的向量。

```java
public Vector resolve(ParticipantResolverContext ctx, Hashtable data, String approvalNodeName)
```

从工作流传递了三个参数。第一个是类似于 `EventContext` 或 `WorkflowContext`。第二个参数 `HashTable` 包含 `TASK_TAG`。最后一个参数 `string` 是工作流中的节点名称。

### 6.1.2 代码示例：Participant Resolver API

此示例使用了 `SimpleApproval` 工作流。`SimpleApproval` 工作流有两个审批者：主审批者和默认审批者。主审批者调用我们的 `ParticipantResolver` 代码。对于默认审批者，我们使用我们的管理员。

我们的需求是主审批者是 `manager` 或 `manager` 是审批者。如果用户没有 `manager`，则使用 `manager`。如果用户没有 `manager`，则跳到默认审批者。

代码：

1. 编译我们的 Java 代码：`com.book.idm.etc.MgrOfMgrParticipantResolver`。
2. 将类（包含包 `com.book.idm.etc`）复制到文件夹 `<server>\IdentityMinder.ear\custom`。

### 配置工作流

1. 搜索我们的管理员任务名称：`Update Location and Ext Number`。
   - 请禁用上一个示例中的业务逻辑任务处理器、`policy Xpress` 或工作流。
2. 选择标签事件并点击 `ModifyUserEvent`。
3. 选择非基于策略的工作流：`singleStepApproval`。
   - 针对主审批人（Primary Approver）：
     - 在 `Approval Task` 下拉菜单中，选择 `Approve Modify User`。
     - 在 `Participant Resolver` 下拉菜单中，选择 `Custom:MgrOfMgrParticipantResolver`。
   - 针对默认审批人（Default Approver）：
     - 在 `Approval task` 下拉菜单中，选择 `Approve Modify User`。
     - 在 `Participant Resolver` 下拉菜单中，选择您的管理员。

![](img/image_rsrc8XH.jpg)

图 6-2 显示了工作流配置。

### 工作原理

你必须准备 3 个用户：`user A`、`user B` 和 `user C`。登录用户数据存储并检查属性 `managerID`：

- `User A` 的 `managerID = user B`。
- `User B` 的 `managerID = user C`。
- `User C` 的 `managerID = ""`。

以 `administrator` 身份登录 Identity Manager 用户控制，选择标签：`Book Example`。

#### 案例 1：修改用户 A，参与者是经理的经理（Manager of Manager）

1. 选择 `Admin Task`：“Update Location and Ext Number”，然后搜索并选择 `user A`。修改城市属性并提交管理员任务。
2. 以 `user C` 身份登录，你应该看到审批请求。

#### 案例 2：修改用户 B，参与者是经理（Manager）

1. 再次选择 `Admin Task`：“Update Location and Ext Number”并选择 `user B`。修改城市属性并提交管理员任务。
2. 以 `user C` 身份登录，你应该看到审批请求。

#### 案例 3：修改用户 C，没有经理

1. 再次选择 `Admin Task`：“Update Location and Ext Number”并选择 `user C`。修改城市属性并提交管理员任务。
2. 以 `administrator` 身份登录，你应该看到审批请求。

### 查找经理的经理

我们使用 `ProviderAccess` 查找经理。获取用户后，查找属性 `managerID`，并通过 `managerID` 搜索经理，直到找到经理的经理。

```java
String userId = ctx.getSubject().getFriendlyName();
User user = ctx.getUserProvider().findUser(userId, null);
String managerID = user.getAttribute("managerID");
User managerUser = ctx.getUserProvider().findUser(managerID, null);
String mgrOfMgrID = managerUser.getAttribute("managerID");
User mgrOfMgrUser = ctx.getUserProvider().findUser(mgrOfMgrID, null);
resolver.add(mgrOfMgrUser);
```

### 添加参与者

代码非常简单。我们创建一个 vector 对象并将作为参与者的 `User` 对象添加到该对象中。

```java
Vector resolver = new Vector();
resolver.add(mgrOfMgrUser);
```

### 没有经理的经理

如果用户没有经理的经理，我们将返回经理：

```java
if(mgrOfMgrID == null || mgrOfMgrID.trim().length()==0){
    System.out.println(userId+" has only manager "+managerID);
    resolvers.add(managerUser);
    return resolvers;
}
```

如果没有审批人，则直接返回空 vector。

### 6.1.3 用例示例

官方文档（`Programming Guide for Java > Workflow API > Participant Resolver API > Participant Resolver Overview > Use Case Example`）中提供了一个用例示例。

#### 将组的管理员分配为参与者

每当用户被添加到 `HR` 组时，都需要进行工作流审批。自定义参与者解析器会将该组的管理员分配为工作流活动中的参与者。当用户被添加到 `HR` 时，事件 `AddToGroupEvent` 将进入工作流控制，在指定的参与者批准该活动之前，活动无法成功完成。

此工作流运行特定事件层级的 `AddToGroupEvent`。我们可以编写条件：如果组名等于“HR”，则返回审批人；如果组名不等于“HR”，则返回空 vector。

```java
public Vector resolve(ParticipantResolverContext ctx, Hashtable userData, String approvalNodeName) throws Exception {
    Vector resolver = new Vector();
    AddToGroupEvent event = (AddToGroupEvent)ctx.getEvent();
    String groupName = event.getGroup().getFriendlyName();
    if(groupName.equals("HR")){
        resolver = event.getGroup().getAdmins(null);
    }
    return resolver;
}
```

我们从 `event` 获取组。我们可以通过方法 `getAdmins()` 获取此组的管理员。请查看 Java 文档获取更多详情。

## 6.2 事件监听器 API（Event Listener API）

当 `CA IdentityMinder` 执行管理员任务时，它会将任务分解为各个组件事件。每个事件代表任务执行期间要执行的特定操作，例如 `CreateUserEvent` 表示添加新用户。

事件监听器监听特定事件或一组事件。当事件发生时，事件监听器执行适用于该事件和当前事件状态的自定义业务逻辑。

### 6.2.1 编程

对于事件监听器 API，你必须创建一个扩展 `EventListenerAdapter` 的 Java 类并根据需要覆盖方法。

- `int before(EventContext evtCtx)`：在预审批（Pre-approval）状态执行自定义业务逻辑。



`int approved(EventContext evtCtx)`：在已批准（Approved）状态执行自定义业务逻辑。

`int rejected(EventContext evtCtx)`：在已拒绝（Rejected）状态执行自定义业务逻辑。

`int after(EventContext evtCtx)`：在执行后（Post）状态执行自定义业务逻辑。

`int failed(EventContext evtCtx)`：在失败（Failed）状态执行自定义业务逻辑。

方法返回 `BREAK`我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。或 `CONTINUE`。`BREAK` 表示没有更多监听器，`CONTINUE` 表示处理下一个监听器。

### 6.2.2 代码示例：事件监听器

示例显示了监听器的生命周期。它使用标准输出。

### 代码

1. 编译 Java 代码：`com.book.etc.LifeCycleEventListener`

2. 将类（包含包 `com.book.etc`）复制到 `\IdentityMinder.ear\custom`

### 配置

1. 在控制台中，点击 `Environments`（环境）。

2. 点击使用事件监听器的环境名称。

3. 点击 `Advanced Settings`（高级设置）。

4. 点击 `Listenersers`。

5. 点击新建按钮并输入如下值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | `LifeCycleEventListener` | 监听器名称 |
| Class | `com.book.etc.LifeCycleEventListener` | 我们的 Java 类 |
| Listener Level | `ModifyUserEvent` | 类监听的事件 |

| ![](img/image_rsrc8XJ.jpg) |
| 图 6-3 显示了事件监听器配置 |

6. 重启环境 (Restart Environment)

| 2013-10-27 INFO [STDOUT] =============>LifeCycleEventListener:approved2013-10-27 INFO [STDOUT] =============>LifeCycleEventListener:after |

## 监听器级别 (Listener Level)

我们将监听器级别设置为 `ModifyUserEvent`。这意味着我们的程序只监听一种事件类型：`ModifyUserEvent`。如果我们将监听器级别改为 `User`，则意味着它监听所有与用户相关的事件。

| ![](img/image_rsrc8XK.jpg) |
| 图 6-4 显示了监听器级别的配置 |

如果你选择 `*`，意味着此监听器将监听所有事件。

### 6.2.3 代码示例：事件生成

事件生成不是 `Listener` 的特性，而是上下文（context）的特性。我们的示例将展示如何生成新事件；将用户添加到组。此示例代码需要一个名为“IT”的组。如果你没有该组，可以创建一个新组或修改代码更改组名。

我们可以通过 `EventContext` 生成新事件。`EventContext` 可以在当前任务内生成一个次级事件。`EventContext` 拥有方法 `generateEvent()`。

```
void generateEvent(java.lang.String className,java.lang.Object primary,java.lang.Object secondary,java.lang.String workflowID) throws java.lang.Exception
```

第一个参数 `className` 是为要生成的事件实例化的类的全限定名。事件类位于 `com.netegrity.ims.events` 包中。你可以在 java doc 中查看详细信息，但我建议在管理控制台 > Environments > Advance Settings > Event List 中查看，那里是最新的。

| ![](img/image_rsrc8XM.jpg) |
| 图 6-5 显示了事件列表 (Event List) |

第二个和第三个参数是 `primary` 和 `secondary` 对象类型，你可以参考上面的图片。最后一个参数是 `workflowID`。工作流过程的名称（例如 `SingleStepApproval`）映射到生成的事件。如果你不需要任何工作流，只需传递 `null`。

此示例展示了如果 `city attribute == “new york”`，我们将用户添加到组“IT”中。

### 代码

1. 编译我们的 java 代码：`com.book.idm.etc.NewYorkCityEventListener`

2. 将类文件（包含包文件夹 `com.book.idm.etc`）复制到文件夹 `\IdentityMinder.ear\custom`

### 配置

1. 在管理控制台中，点击 `Environments`。

2. 点击将使用事件监听器的环境名称。

3. 点击 `Advanced Settings`。

4. 点击 `Event Listeners`。

5. 点击 `new` 按钮并按下表赋值：

| 字段名 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name | `NewYorkCityEventListener` | 事件监听器的名称 |
| Class | `com.book.idm.etc.NewYorkCityEventListener` | Java 类名 |
| Listener Level | `ModifyUserEvent` | 该类监听的事件 |

6. 点击 `Restart Environment`。

#### 配置：Identity Manager 用户控制台

1. 以管理员身份登录 Identity Manager User Console。

2. 检查我们的管理员任务名称：`Update Location and Ext Number`：

   - 移除所有业务逻辑任务处理器和 Policy Xpress。

   - 移除上一个示例中的工作流。

#### 运行原理

执行管理员任务：`Update Location and Ext Number`。

1. 以管理员身份登录 Identity Manager User Console。

2. 在“Book Example”选项卡中选择管理员任务：“Update Location and Ext Number”，然后搜索某些用户。将城市属性更改为“New York”并提交管理员任务。

3. 查看已提交的任务，并选择详情。你将看到事件“Add user to group”。

| ![](img/image_rsrc8XN.jpg) |
| 图 6-6 显示了生成的事件 "Add user to group" |

你可以搜索组“IT”并查看其成员关系以检查结果。

#### 特定的管理员任务

我们通过配置指定事件，通过代码指定管理员任务。我们添加了条件来检查管理员任务的 tag。

```
if(!"BookBasicUpdateLocAndExtNo".equalsIgnoreCase(evtCtx.getAdminTask().getTaskTag())){return CONTINUE;}
```

#### 事件生成

此代码展示了事件生成：`AddToGroupEvent`。我们查找组 `IT` 并将其传递给方法 `generateEvent()`。结果是用户被添加到组“IT”中。

```
if(city.equalsIgnoreCase("new york")){Group group = evtCtx.getGroupProvider().findGroup("IT",null);evtCtx.generateEvent("com.netegrity.ims.events.AddToGroupEvent",user,group, null);}
```

### 6.2.4 用例示例

我们梳理了官方文档中所有用例的代码（Programming Guide for Java > Event Listener API > Event Listener API Overview > Use Case Examples）。

#### 将用户添加到 Microsoft Exchange（特定事件监听器）

当用户被成功添加到管理员角色 `Exchange Users` 时，CA IdentityMinder 会调用与事件 `AssignAdminRoleEvent` 关联的事件监听器的 `after()` 方法。`after()` 方法的实现使用 Exchange API 将用户添加到 Exchange 系统。访问 Exchange 服务器所需的信息（`SERVER_NAME`、`ADMIN_ID`、`ADMIN_PASSWORD` 等）包含在 CA IdentityMinder 环境的用户定义属性中。CA IdentityMinder 环境属性会被传递给 `EventListenerAdapter` 的 `init()` 方法。

在这个用例中，你只需要重写 `after()` 方法并编写程序将用户添加到 Microsoft exchange。对于 `init()` 方法，你可以在用户定义属性中获取。请参见本章末尾的示例代码。

#### 为组分配创建规则（特定事件监听器）

当用户被创建时，CA IdentityMinder 会调用与事件 `CreateUserEvent` 关联的事件监听器的 `after()` 方法。`after()` 方法的实现评估用户属性（如 `Job Title`、`Security Level` 和 `Department`），将用户分配到一个或多个组。对于每个组分配，实现会生成次级事件 `AddToGroupEvent`。此次级事件可以接受工作流审批和审计。

在这个用例中，你必须通过检查职位等来编写条件。如果匹配，你可以生成新事件：`AddToGroupEvent`。这与我们的示例：事件生成相同。

#### 使用用户数据更新 RDBMS（类级别事件监听器）

假设用户信息（如 `user ID`、`user name`、`email address` 和组成员关系存储在 RDBMS 中。每当发生任何用户级事件（`CreateUserEvent`、`ModifyUserEvent` 等）时，必须更新 RDBMS 中的用户记录。事件执行后，CA IdentityMinder 会调用与用户事件关联的事件监听器的 `after()` 方法。该方法的实现从传递给 `init()` 方法的 CA IdentityMinder 环境属性中检索 RDBMS 连接参数，然后更新 RDBMS 中的用户记录。

在这个用例中，我们在 `after()` 中实现数据库更新逻辑。在管理控制台配置中，我们选择监听 `user` 级别。这意味着 Java 类将在所有用户事件上执行。

#### 将事件发布到 JMS 队列（所有监听器）

在任何事件成功执行后，CA IdentityMinder 会调用所有事件监听器的 `after()` 方法。此监听器将所有事件写入特定的 Java 消息服务（JMS）队列。队列的 JNDI 名称和 `jndi.properties` 文件中的信息可以通过 CA IdentityMinder 环境属性进行配置。`after()` 方法的实现使用 JNDI 信息发布简单的对象消息。

这与之前相同，重写 `after()` 方法并发送到 JMS。在管理控制台中配置 `*`，它将在每个事件发生时执行。

## 6.3 逻辑属性 API

逻辑属性 API 用于在逻辑属性（显示在屏幕上）和物理属性（存储在用户数据存储中）之间进行转换。逻辑属性处理器的执行发生在任务处理的同步阶段。

### 逻辑属性

逻辑属性值显示在任务屏幕字段中。逻辑属性名称出现在垂直线（|）之间。例如，扩展逻辑属性显示为 `|Extension|`。

| ![](img/image_rsrc8XP.jpg) |
# 图 6-7 显示了逻辑属性

逻辑属性值并不直接关联或写入数据存储器。它需要通过逻辑属性处理程序（logical attribute handler）进行处理。

## 预定义逻辑属性

CA IdentityMinder 为某些目的预定义了逻辑属性，例如 `passwordConfirm`、`oldPassword`。我们可以使用或自定义它们。更多细节请参阅办公文档。

## 物理属性

物理属性是底层数据存储器（如 `LDAP` 等用户目录）的属性。如果任务屏幕字段配置了物理属性，则在字段中输入的值将写入数据存储器。

### 6.3.1 编程

创建一个扩展 `LogicalAttributeAdapter` 的 `java` 类并重写以下方法：

*   `public void toLogical(LogicalAttributeContext apiContext) throws java.lang.Exception`
    *   将物理属性的值转换为逻辑属性值。

*   `public void toPhysical(LogicalAttributeContext apiContext) throws java.lang.Exception`
    *   将逻辑属性的值转换为物理属性值。

*   `public void initializeOptionList(LogicalAttributeContext apiContext) throws java.lang.Exception`
    *   如果你想将值以列表的形式渲染，你需要实现此方法并返回一个 `Vector` 作为屏幕上的显示值列表。

*   `public void initialize(LogicalAttributeContext apiContext) throws java.lang.Exception`
    *   在创建用户或创建任何对象时，此方法设置属性的初始值。

### 6.3.2 代码示例

我们的示例展示了将城市（物理属性）转换为办公室代码（逻辑属性）。屏幕将显示办公室代码。当用户选择办公室代码时，它将把办公室代码的值转换为城市值。

| ![](img/image_rsrc8XR.jpg) |
| 图 6-8 显示了更新办公室的用户屏幕 |

### 代码

1. 编译我们的 `java` 代码：`com.book.idm.etc.OfficeCodeLogicalAttr`

2. 将类（包含包文件夹 `com.book.idm.etc`）复制到文件夹 `<server>\IdentityMinder.ear\custom` 中。

#### 配置：管理控制台 (Management Console)

1. 在管理控制台中，点击 `Environments`。

2. 点击将使用逻辑属性的环境名称。

3. 点击 `Advanced Settings`。

4. 点击 `Logical Attribute Handlers`。

5. 点击 `new` 按钮并输入如下值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Name | `OfficeCodeLogicalAttr` | 逻辑属性的名称 |
| Class | `com.book.idm.etc.OfficeCodeLogicalAttr` | `java` 类名 |
| Object Type | `User` | 拥有逻辑属性的对象类型 |
| Logical Attributes | | |
| Name | `officeCodeList` | 代码中使用的名称。 |
| Attribute Name | `\|officeCodeList\|` | 在管理员任务屏幕上显示的名称 |
| Option List | Check | 告诉 CA IdentityMinder 该属性是一个列表 |
| Name | `officeCode` | 代码中使用的名称。 |
| Attribute Name | `\|officeCode\|` | 在管理员任务屏幕上显示的名称 |
| Physical Attributes | | |
| Name | `officeCodePhyAttr` | 代码中使用的名称。 |
| Attribute Name | `l` | (小写字母 L) 用户存储中城市属性的名称。 |

| ![](img/image_rsrc8XS.jpg) |
| 图 6-9 显示了管理控制中的逻辑属性配置 |

6. 点击 `Restart Environment` 按钮。

#### 配置：Identity Manager 用户控制台 (User Console)

1. 以 `administrator` 身份登录 Identity Manager 用户控制台。

2. 选择标签页 `Roles` 和 `Tasks`，并选择菜单 `create admin task`。

3. 创建管理员任务，输入如下值：

| 字段名称 | 值 | 描述 |
| :--- | :--- | :--- |
| Tab: Profile | | |
| Name | `Update Office` | 管理员任务的名称 |
| Tag | `BookBasicUpdateOffice` | 管理员任务的标签名称 |
| Description | `Example for Logical Attribute` | 管理员任务的描述 |
| Category | `Book Example` | 管理员任务显示的位置 |
| Category Order | `11` | |
| Category 2 | `Task` | |
| Category 3 | `Basic` | |



| Primary Object | `User` | 我们想更新城市，所以必须选择对象用户（user），并操作修改（modify）。 |
| ---|---|---|
| Action | `Modify` | |

为了测试，你可以禁用某些值。

- User Synchronization and Account Synchronization：off。
- Enable Auditing、Enable Workflow、Enable Web Services：uncheck。

### Tab: Search

| Search Screen | `Default User Search` | 用于搜索用户的屏幕 |
|---|---|---|

### 4. 针对标签页 Tab: Tabs

选择标准标签页控制器。

从列表中选择 `Profile(UserProfile)` 并点击符号 `(+)`。

点击屏幕文本字段处的 `browse` 按钮。

点击 `new` 按钮创建新屏幕，并选择标准配置屏幕 screen。

输入值：

- Name: `Book Example: Update Office`
- Tag: `BookBasicUpdateOffice`

添加属性：`\|officeCode\|`

- Attribute Name: `\|officeCode\|`
- Style: `Drop down`
- Name: `Office Code`
- 点击 `apply` 按钮完成。

添加属性：`\|officeCodeList\|`

- Attribute Name: `\|officeCodeList\|`
- Style: `Hidden`
- 点击 `apply` 按钮完成。

添加属性：`City`

- Attribute Name: `\|City\|`
- Style: `Hidden`
- 点击 `apply` 按钮完成。

点击 `ok`。

![](img/image_rsrc8XT.jpg)

图 6-10 显示了属性配置。

### 5. 提交完成

将此任务添加到角色。

1. 选择标签页 `Roles` 和 `Tasks`，选择菜单 `create admin task`。
2. 以 `administrator` 身份登录 Identity Manager 用户控制台。
3. 选择标签 `Book Example`，屏幕将显示办公室代码。
4. 修改属性并点击提交。

### 工作原理

执行管理员任务：Update office。搜索用户，检查属性。

#### 方法：`toLogical()`

此方法将物理属性的值转换为逻辑属性。该代码包含三个步骤：

- 步骤 1：从物理属性获取值。
- 步骤 2：映射，从物理属性转换为逻辑属性。你可能有其他转换方式。我们的代码使用映射进行转换。
- 步骤 3：将值设置逻辑属性。

```java
private String ATTR_REF_PHY = "officeCodePhyAttr";

@Override
public void toLogical(LogicalAttributeContext ctx) throws Exception {
    // 获取物理属性值
    String city = ctx.getPhysicalAttributeName(ATTR_REF_PHY);
    String cityValue = ctx.getPhysicalAttributeValue(city);

    // 从物理映射到逻辑
    String officeCodeValue = indexPhysicalAsKey.get(cityValue);
    if (officeCodeValue != null) {
        // 设置逻辑值
        String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
        ctx.setLogicalAttributeValue(officeCode, officeCodeValue);
    }
}
```

步骤 1：当我们进行配置时，变量 `officeCodePhyAttr` 链接到用户存储中的属性 `l`。

![](img/image_rsrc8XU.jpg)

图 6-11 显示了物理属性的属性映射。

步骤 2：映射，我们有一个辅助对象 `indexPhysicalAsKey` 类来转换为逻辑值。在真实世界的需求中，你可能有某些转换逻辑。官方文档提到：

> 逻辑属性处理器的执行发生在任务处理的同步阶段。如果与第三方系统交互时的响应时间是一个问题，可以使用预审批状态（Pre-approval state）期间事件监听器来实现相同的目标。

步骤 3：代码最后一行是将值设置回逻辑属性。

#### 方法：`toPhysical()`

此方法是 `toLogical()` 的反操作。步骤相同但方向相反。

### 步骤 3：将值写回物理属性

```java
@Override
public void toPhysical(LogicalAttributeContext ctx) throws Exception {
    // step 1
    String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
    String officeCodeValue = ctx.getLogicalAttributeValue(officeCode);

    // step 2
    String cityValue = indexLogicalAsKey.get(officeCodeValue);

    // step 3
    String city = ctx.getPhysicalAttributeName(ATTR_REFER_PHY);
    ctx.setPhysicalAttributeValue(city, cityValue);
}
```

#### 管理任务中的属性

我们在屏幕上声明了 3 个字段：

- 2 个逻辑属性：`officeCode`（下拉列表）和 `officeCodeList`（隐藏）对于下拉列表是必选的。
- 1 个物理属性：城市（City，隐藏），我们需要它是因为我们要填充城市属性。因此，城市属性必须存在于管理任务上下文中。

#### 方法：`initializeOptionList()`

如果你想为此逻辑属性提供下拉列表，则必须实现此方法。你只需将向量设置为逻辑属性值。

```java
ctx.setLogicalAttributeMultiValue(officeCodeList, officeCodes);
```

确保你在配置页面中检查了选项列表。

![](img/image_rsrc8XV.jpg)

图 6-12 显示了选项列表的复选框。

#### 方法：`initialize()`

此方法仅在创建任务时执行，例如创建用户、创建账户。此方法用于设置逻辑属性的初始值。

对于修改任务，此方法从未执行过。我们的示例从未调用过此方法。如果你想执行此方法，必须将操作更改为“创建”（create）（主对象是用户）。然后再次执行此管理任务，你将看到此方法设置了默认值“006NY”。

```java
@Override
public void initialize(LogicalAttributeContext ctx) throws Exception {
    String officeCodeName = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
    String officeCodeValue = ctx.getLogicalAttributeValue(officeCodeName);

    if (officeCodeValue == null || officeCodeValue.trim().length() == 0) {
        ctx.setLogicalAttributeValue(officeCodeName, "006NY");
    }
}
```

#### 方法：`validate()`

`validate()` 方法在用户提交任务时执行。你可以通过选择空值并点击提交来测试我们的代码。

```java
@Override
public void validate(LogicalAttributeContext ctx) throws Exception {
    String officeCode = ctx.getLogicalAttributeName(ATTR_OFFICE_CODE);
    String officeCodeValue = ctx.getLogicalAttributeValue(officeCode);

    if (officeCodeValue == null || officeCodeValue.trim().length() == 0) {
        IMSException e = new IMSException();
        e.addUserMessage("Invalid office value");
        throw e;
    }
}
```

![](img/image_rsrc8XW.jpg)

图 6-13 显示了 `validate()` 方法期间的异常。

#### 屏幕定义的逻辑属性 vs 我们的逻辑属性

当你创建屏幕时，可以创建屏幕定义的逻辑属性。屏幕定义的逻辑属性仅针对单个屏幕定义。它们不能与其他屏幕共享，但逻辑属性本身是可以共享的。

## 6.3.3 用例

参考官方文档：Programming guide > Logical Attribute > Use Case Examples。

### 从数据源格式化数据

在用户目录中，电话号码以物理属性 `phone` 的形式存储。它有 10 位数字——例如 `9785551212`。该物理属性与逻辑属性 `formatted_phone` 相关。

此用例需要重写 `toLogical()` 以返回格式化后的电话，并重写方法 `toPhysical()` 将格式化后的电话转换为数字。

### 验证数据输入

数据源存在物理属性 `employeeNumber`，它映射到逻辑属性 `validEmployeeNumber`。当用户在任务屏幕上为 `validEmployeeNumber` 属性分配员工编号并点击提交后，CA IdentityMinder 会调用自定义逻辑属性处理器来查询数据源，以确保提供的员工编号存在于 `employeeNumber` 中。如果不存在，逻辑属性处理器将抛出异常。

此用例查询数据库并在逻辑属性和物理属性之间进行转换。

```java
@Override
public void toLogical(LogicalAttributeContext ctx) throws Exception {
    // step 1
    String empNo = ctx.getPhysicalAttributeName("employeeNumber");
    String empNoValue = ctx.getPhysicalAttributeValue(empNo);

    // step 2
    String validEmpNoValue = queryByPhysicalID(validEmpNoValue);

    // step 3
    if (empNo != null) {
        String validEmpNo = ctx.getLogicalAttributeName("validEmployeeValue");
        ctx.setLogicalAttributeValue(validEmpNo, validEmpNoValue);
        return;
    }

    throw new IMSException("invalid employee number");
}
```

（等待，查看下方的逻辑）

任务屏幕要求客户提供他们购买的服务类型——金级（Gold）、银级（Silver）或铜级（Bronze）。这些选项在与逻辑属性 `serviceType` 关联的下拉列表中。当客户选择服务级别并点击提交时，CA IdentityMinder 会调用逻辑属性处理器，将所选的服务级别转换为对应的物理属性值（1、2 或 3），并将该值分配给物理属性 `type`。

此用例与我们的示例相同。你必须实现 `initializeOptionList()` 来返回服务类型：金级、银级或铜级，并实现方法 `toPhysical()` 将服务类型（金级、银级或铜级）转换为物理属性值（1、2 或 3）。

## 6.4 验证规则

属性验证规则有助于验证用户在屏幕上输入的值符合格式。验证规则可以是正则表达式、JavaScript 或 Java 实现。本书将关注 Java 编程。正则表达式和 JavaScript 可以查看官方文档中的示例。

- 任务级验证：针对特定任务。你可以在任务屏幕配置期间定义规则。
- 目录级验证：应用于所有任务。它是全局范围的。需要在 `directory.xml` 中定义。

### 6.4.1 编程

对于任务级验证，你必须实现 `TaskValidator` 并重写 `validate()` 方法。

```java
public boolean validate(BLTHContext ctx, String attrValue, StringRef changedValue, StringRef errorMsg) throws AttributeException
```

对于目录级验证，你需要扩展 `AttributeValidator` 并重写 `validate()` 方法。它与任务级非常相似，但有一些细节。请见示例。

```java
public boolean validate(Object attrValue, StringRef changedValue, StringRef errorMsg) throws AttributeException
```

### 6.4.2 代码示例：任务级验证

此示例需要属性 `Employee Number`，请检查你的用户存储。我们的需求使用 `employeeNumber` 属性。验证规则如下：

- 员工编号必须是数字。
- 最大 4 位。
- 如果用户输入 1-3 位数字，格式将在前面填充 0。例如：2，正确的格式将是 `0002`。

![](img/image_rsrc8XX.jpg)

图 6-14 显示更新员工编号的用户屏幕。

### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.EmployeeNumberTaskValidator`
2. 将类（包含包 `com.book.idm.etc`）复制到 `\IdentityMinder.ear\custom` 文件夹。

#### 配置：Identity Manager 控制台

1. 以管理员身份登录 Identity Manager 控制台。
2. 选择 Roles and Tasks 选项卡，并选择 `create admin taskget`。
3. 创建管理任务，输入如下值：

| 字段名称 | 值 | 描述 |
|---|---|---|
| Tab: Profile |  |  |
| Name | `Update Employee Number` | 管理任务名称 |
| Tag | `BookBasicUpdateEmployeeNumber` | 管理任务标签 |
| Description | `Example for Validation` | 管理任务描述 |
| Category | `Book Example` | 管理任务显示的位置 |
| Category Order | `11` |  |
| Category 2 | `Task` |  |
| Category 3 | `Basic` |  |
| Primary Object | `User` | 我们想更新员工编号，所以必须选择用户对象和修改操作。 |
| Action | `Modify` |  |

为了测试，你可以禁用某些值。

- 用户同步和账户同步：关闭。
- 启用审计、启用工作流、启用 Web 服务：取消勾选。

### 标签页：搜索

| 搜索界面 | 默认用户搜索 | 搜索用户的界面 |
|---|---|---|
|  |  |  |

### 4. 关于标签页：标签（Tabs）

选择标准标签页控制器。

从列表中选择 `Profile`（`UserProfile`），并点击符号 `(+)`。

选择屏幕文本字段处的浏览按钮。

点击 `new` 按钮创建新界面，并选择一个标准配置界面界面。

输入值：

- 名称：`Update Employee Number`
- 标签：`BookBasicUpdateEmployeeNumber`
- 添加属性：`Employee Number`
  - 属性名称：`Employee Number`
  - 样式：`Text`
  - 名称：`Employee Number`
  - 校验 Java 类：`com.book.idm.etc.EmployeeNumberTaskValidator`
- 点击 `apply` 按钮完成。
- 点击 `ok`。

![](img/image_rsrc8XY.jpg)

图 6-15 显示了工号属性的配置。

### 5. 提交完成任务创建

#### 将任务添加到管理员角色

1. 选择标签页：`Roles and Tasks`，并选择菜单 `modify admin role`。
2. 选择角色 `system manager`。
   - 选择标签页：`task`
   - 按分类筛选：`Book Example`



*我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。选择添加任务：`Update Employee Number`。

3. 点击`submit`完成管理员角色的修改。

### 工作原理

执行管理员任务：`Update employee number`。

1. 以管理员身份登录身份管理器用户控制台（User Console）。
2. 选择标签页：`Book Example`，并选择`update employee number`。
3. 搜索一个用户，屏幕将显示工号作为文本字段。
4. 修改工号属性，并点击`submit`。

#### 方法 `validate()`

错误有 2 种情况：

* 输入 5 位数字工号。

![](img/image_rsrc8XZ.jpg)

图 6-16 显示了通过返回值产生的错误。

* 输入任意字符。

![](img/image_rsrc8Y0.jpg)

图 6-17 显示了通过异常产生的错误。

有 2 种返回消息的方法，你可以选择其中一种。

* 返回`false`并通过`errorMsg.reference`设置消息。

```java
if(attrValue.trim().length()>4){
    errorMsg.reference = "Employeer Number can not more than 4 digits";
    return false;
}
```

* 抛出异常并将消息作为参数。

```java
try{
    ...
    int employeeNo = new Integer(attrValue);
    ...
}catch(Exception e){
    throw new AttributeValidationException("Employeer Number:invalid format");
}
```

尝试输入一个数字，例如`1`，并提交。登录用户库，工号将显示为`0001`。我们可以通过`changedValue.reference`参数修改值。

```java
int employeeNo = new Integer(attrValue);
DecimalFormat format = new DecimalFormat("0000");
changedValue.reference = format.format(employeeNo);
```

任务级校验提供了`BLTHContext`作为参数。你可以使用`BLTHContext`从受管理对象搜索某些属性，例如你必须检查新值必须是唯一的。

### 6.4.3 代码示例：目录级校验

此示例将使用与任务级校验相同的需求。请从管理员任务`update employee number`中禁用任务级校验。

* 搜索管理员任务：`update employee number`。
* 转到标签页：`tabs`并修改界面：`Update Employee Number`。
* 校验 Java 类的值：`com.book.idm.etc.EmployeeNumberTaskValidator`。

### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.EmployeeNumberDirValidator`。
2. 将类（包括包文件夹`com.book.idm.etc`）复制到文件夹`\IdentityMinder.ear\custom`。

#### 配置：管理控制台

1. 在管理控制台中，点击`Directory`。
2. 点击用户库目录名称。
3. 点击页面底部的`export`按钮。你将获得一个`xml`文件。
4. 使用文本编辑器打开`xml`文件。
5. 你必须修改 2 个地方：
   * 在元素`<ImsManagedObjectAttrValidation>`下添加校验规则。请查阅官方文档中的 XML schema。

```xml
<ValidationRule name="Employee Number pattern" description="Validates employee number" messageid="4002"><Java class="com.book.idm.etc.EmployeeNumberDirValidator"/></ValidationRule>
<ValidationRuleSet name="Employee Number format" description="validate employee number format"><ValidationRule name="Employee Number pattern"/></ValidationRuleSet>
```

   * 为`employeeNumber`属性添加`validationruleset` =`Employee Number format"`。

```xml
<ImsManagedObjectAttr physicalname="employeeNumber" description="Employee Number" displayname="Employee Number" valuetype="String" maxlength="0" validationruleset="Employee Number format"/>
```

6. 返回管理控制台，选择我们使用的用户库目录。
7. 点击`update`按钮并选择我们的`xml`文件。点击`next`和`finish`按钮。屏幕将在控制台中显示消息，点击`continue`并重启环境。

### 工作原理

执行管理员任务：`Update employee number`。

4. 以管理员身份登录身份管理器用户控制台。
5. 选择标签页：`Book Example`，并选择`update employee number`。
6. 搜索一个用户，屏幕将显示工号作为文本字段。
7. 修改工号属性，并点击`submit`。

#### 方法 `validate()`

返回消息有 2 种方法，你可以选择其中一种。

* 返回`false`并通过`errorMsg.reference`设置消息。

```xml
<ValidationRule name="Employee Number pattern" description="Validates employee number" messageid="4002"><Java class="com.book.idm.etc.EmployeeNumberDirValidator"/></ValidationRule>
<ValidationRuleSet name="Employee Number format" description="validate employee number format"><ValidationRule name="Employee Number pattern"/></ValidationRuleSet>
```

* 为`employeeNumber`属性添加`validationruleset` =`Employee Number format"`。

```xml
<ImsManagedObjectAttr physicalname="employeeNumber" description="Employee Number" displayname="Employee Number" valuetype="String" maxlength="0" validationruleset="Employee Number format"/>
```

* 抛出异常并将消息作为参数。

```java
try{
    ...
    int employeeNo = new Integer(attrValue);
    ...
}catch(Exception e){
    throw new AttributeValidationException("Employeer Number:invalid format");
}
```

![](img/image_rsrc8Y1.jpg)

图 6-18 显示了来自`IMSException.properties`的消息 ID。

#### 校验集

在管理控制台中点击用户库目录。向下滚动直到校验集。点击内部链接，你将会看到详情。

![](img/image_rsrc8Y2.jpg)

图 6-19 显示了控制台中的校验集。

测试后禁用目录级校验。我们将在第二部分中使用工号。

### 6.5 电子邮件通知

部分是一个特殊主题。它用于下一个 API：`Notification Rule`。CA IdentityMinder 官方文档在管理指南中有电子邮件通知，而不是在编程指南。

#### 配置 SMTP

在启动电子邮件通知之前，你需要检查 SMTP 配置。在处理电子邮件通知之前有 2 个需要检查的项目。第一个是 SMTP 配置，即 SMTP 服务器。

* JBoss：检查`jboss_home\server\default\deploy\mail-service.xml`。
* WebLogic：检查 JNDI 名称为`nete/Mail`的会话。
* WebSphere：检查名为`mailMail`的会话对象。

请查看官方文档“管理指南 > 电子邮件通知 > 配置 SMTP”。

第二个是`iam_im.ear\config\com\netegrity\config`文件夹下的`email.properties`文件。

### 6.5.1 如何实现电子邮件通知

有 2+1 种实现电子邮件通知的方法。官方文档介绍了 2 种发送电子邮件的方法。本书提供了另一种发送方法。

1. 电子邮件通知策略。
   * 创建电子邮件通知不需要代码。
   * 电子邮件通知策略是 Policy Xpress 策略。你可以创建触发策略运行的条件。
   * 它在`System`标签页下，选择`Email`菜单。
2. 电子邮件模板。
   * 需要代码（JSP/Java 语法）。
   * 支持动态内容（内容中包含`if-else`条件）。
   * 支持`Notification Rule` API。

邮件通知策略和邮件模板都取决于任务完成情况或事件结果（批准、拒绝或失败）。你不能在任何随心的时间发送邮件。例如，你可能有一个很长的流程步骤：

- 步骤 1：HR 人员更新用户的办公室。
- 步骤 2：发送邮件提醒经理进行审批。
- 步骤 3：发送修复工单，然后向 HR 人员发送邮件告知工单号。
- 步骤 4：向设施系统发送 Web 服务请求以申请访问权限。Web 服务响应成功后向 HR 人员发送邮件。如果请求失败，则向 IT 管理员发送邮件。
- 步骤 5：等待到预期的入职日期，发送邮件确认用户和 HR 人员。

对于长流程，你必须分析何时需要通知邮件解决方案。本书提供了一个通过 Java API 发送邮件的技巧。

## 3. Service API

- 可以随时发送邮件。
- 支持动态内容。你可以使用任何流行的框架，如`velocity`。
- 请注意，CA IdentityMinder 文档未提到这种方法。请自担风险使用。

### 6.5.2 代码示例：邮件模板

此示例展示了如何实现邮件模板。理解邮件模板对于下一个主题通知规则 API（Notification Rule API）是必要的。我们的示例代码将在管理员执行管理任务“更新位置和分机号”成功后发送邮件。

### 代码

1. 找到文件`Update Location and Ext Number.tmpl`。
2. 将文件拷贝到文件夹`<server>\IdentityMinder.ear\custom\emailTemplates\default\completed`。

### 配置：管理控制台（Management Console）

1. 在管理控制台中，点击`Environments`。
2. 点击环境名称。
3. 点击`Advanced Settings`。
4. 点击`Email`。
5. 勾选框框`Tasks e-mail enabled`。

![](img/image_rsrc8Y3.jpg)

图 6-20 显示任务邮件启用配置。

6. 向下滚动直到看到“当以下任务完成或在工作流期间发送邮件”（Send e-mail when the following tasks are completed or during workflow）。
   - 在 Admin Task Name（管理任务名称）中，从下拉菜单选择`Equal`并输入值：`Update Location and Ext Number`。
   - `Update Location and Ext Number`将出现在搜索结果中。选中该任务的复选框并点击添加按钮。
   - 你应该在任务列表中看到任务`Update Location and Ext Number`。

![](img/image_rsrc8Y4.jpg)

图 6-21 显示为邮件模板添加任务。

7. 点击保存按钮。
8. 点击`Restart Environment`（重启环境）按钮。

### 工作原理

执行管理任务：`Update Location and Ext Number`。

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页`Book Example`，并选择菜单`Update Location and Ext Number`。
3. 搜索一个用户，屏幕将显示城市下拉菜单。
4. 修改城市属性并点击提交。

### 收到邮件

在管理员提交后，用户应该收到内容如下的邮件：

![](img/image_rsrc8Y5.jpg)

图 6-22 显示邮件内容。

打开文件`Update Location and Ext Number.tmpl`，你将看到邮件内容的代码。它们有特殊的变量，如`_to`或`_taskContextInformation`。`_to`表示邮件收件者。我们将在通知规则 API 中涵盖更多细节。`_taskContextInformation`是任务上下文。更多详情请参见管理指南。

```jsp
<% _to = _util.getNotifiers("USER", ""); _cc = ""; _bcc = "" ; _subject = "Update Location and Ext Number";%>User:<%var imsEventContexts = _taskContextInformation.getExposedEventContexts(); if(imsEventContexts != null) { var eventContext = imsEventContexts.get(0); template.add(eventContext.getPrimaryObjectName()); }>%has been updated location and ext number successfully.
```

如果你没有收到邮件或屏幕显示错误，请检查日志文件。SMTP 可能不正确。

如果你没有收到邮件，但管理员收到了邮件且主题为“Update Location and Ext Number Completed”，这意味着 CA IdentityMinder 使用默认模板：`defaultTask.tmpl`发送邮件。请检查文件夹名称`default/completed`，管理任务应与我们的模板名称完全匹配。某些修改可能需要重启服务器或环境。

## 6.5.3 代码示例：通过 Service API 发送邮件通知

此示例展示了如何通过 CA IdentityMinder 服务发送邮件。我们将使用业务逻辑任务处理程序发送邮件。请禁用上一个示例中的邮件模板。

### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.SendEmail`。
2. 将类（包括包文件夹`com.book.idm.etc`）拷贝到文件夹`<server>\IdentityMinder.ear\custom`。

### 配置：Identity Manager 用户控制台

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页`Roles and Tasks`，并选择菜单`modify admin task`。
3. 搜索管理任务：`Update Location and Ext Number`。
4. 点击按钮`Business Logic Task Handlers`（业务逻辑任务处理程序）。
5. 点击添加并输入如下值：

| 字段名称（Field Name） | 值（Value） | 说明（Description） |
| --- | --- | --- |
| Name（名称） | `SendEmail` | 业务逻辑任务处理程序的名称 |
| Class（类） | `com.book.idm.etc.SendEmail` | Java 类名 |

6. 点击确定并提交任务。

### 工作原理

执行管理任务：`Update Location and Ext Number`。

1. 以管理员身份登录 Identity Manager 用户控制台。
2. 选择标签页`Book Example`，并选择菜单`Update Location and Ext Number`。
3. 搜索一个用户，屏幕将显示城市下拉菜单。
4. 修改城市属性并点击提交。

### Service API

代码非常直观。你可以通过`sendMail()`方法发送邮件。

```java
InternalServiceAccessor.getEmailService().sendMail(from,cc,encoding,contentType,subject,body);
```

可以在配置中通过`getAdminID()`获取管理员邮件。



`String adminEmail = InternalServiceAccessor.getEmailService().getAdminID();`

可以通过 `ProviderAccessor` 获取邮件收件者。因为：

```java
User user = ctx.getUserProvider().findUser(ctx.getUser().UniqueName(), null);
String to = user.getAttribute("mail");
```

## 6.6 通知规则 API (Notification Rule API)

此 API 仅配合邮件模板使用。它决定了谁接收邮件。

### 6.6.1 编程

你必须创建一个扩展 `NotificationRuleAdapter` 的 Java 类并重写 `evaluate()` 方法。

```java
Vector evaluate(NotificationRuleContext ctx, Hashtable templateParams)
```

- 第一个参数 `ctx` 与其他 API 相似。
- 第二个参数 `templateParams` 保留了邮件模板中指定的自定义数据值对。

### 6.6.2 代码示例

此示例需要之前的示例：邮件模板。需要在任务完成时启用邮件模板。我们的需求是在管理员执行管理任务 `Update Location and Ext Number` 时，向用户发送邮件并抄送经理。如果他们没有经理，可以跳过抄送。

### 代码

1. 编译我们的 Java 代码：`com.book.idm.etc.ManagerNotificationRule`。
2. 将类（包括包文件夹 `com.book.idm.etc`）拷贝到文件夹 `<server>\IdentityMinder.ear\custom`。
3. 修改邮件模板文件夹中的 `Update Location and Ext Number.tmpl`。为 `_cc` 添加通知规则名称。

```java
_cc = _util.getNotifiers("ManagerNotificationRule","param1=A,param2=B");
```

### 配置：管理控制台

1. 在管理控制台中，点击 `Environments`。
2. 点击环境名称。
3. 点击 `Advanced Settings`。
4. 点击 `Notification Rules`。

| 字段名称 (Field Name) | 值 (Value) | 说明 (Description) |
| :--- | :--- | :--- |
| Name (名称) | `ManagerNotificationRule` | 通知规则的名称 |
| Class (类) | `com.book.idm.etc.ManagerNotificationRule` | Java 类名 |

5. 点击保存并重启环境。

### 工作原理

执行管理任务：`Update Location and Ext Number`。

如果你想在任务完成后发送邮件，请在 `after()` 方法的监听器中发送邮件。

1. 以 `administrator` 身份登录 `Identity Manager User Console`。
2. 选择标签页：`Book Example`，并选择菜单 `Update Location and Ext Number`。
3. 搜索用户，屏幕将显示城市下拉列表。
4. 修改城市属性并点击 `submit`。

## 邮件收件人

我们使用 `ProviderAccessor` 查询用户的经理，然后获取属性 `"mail"`，并将电子邮件地址添加到向量并返回。

```java
String emailManager = manager.getAttribute("mail");
if (emailManager != null || emailManager.trim().length() != 0) {
    emails.add(emailManager);
}
```

## 模板参数

在邮件模板中，我们添加了通知规则。

```java
_cc = _util.getNotifiers("ManagerNotificationRule","param1=A,param2=B");
```

`"param1=A,param2=B"` 是模板参数。我们可以从参数 `templateParams` 中获取这些值。

```java
public Vector evaluate(NotificationRuleContext ctx,Hashtable templateParams){
    Enumeration keys = templateParams.keys();
    while (keys.hasMoreElements()) {
        Object key = keys.nextElement();
        System.out.println("parameter: " + key + "=" + templateParams.get(key));
    }
}
```

### 6.6.3 用例

我们在官方文档（Programming Guide for Java › Notification Rule API › API Overview > Use Case Examples）中实现了用例示例。

#### 通知单个用户

当用户数据被修改时，检索用户名称并将请求的状态状态抄送给该用户。

通过编写通知规则代码，你可以从上下文中获取用户名并添加后缀作为邮件地址。你必须在邮件模板的 `_cc` 中调用通知规则。

```java
String userName = ctx.getSubject().getFriendlyName();
String email = userName+"@somedomain.com";
emails.add(email);
```

#### 通知用户组

当用户被创建并添加到组时，检索组名（从传递到通知规则的上下文信息中），并关于新组成员通知该组。

我们在事件 `AddToGroupEvent` 下编写了邮件模板，因此主对象是组。我们获取组名并将组名作为上下文信息添加到邮件模板中，传递给通知规则。

```java
String groupName = _eventContextInformation.getPrimaryObjectName();
_cc = _util.getNotifiers("NotificationRule","group="+groupName);
```

### 6.6.3 通知规则与邮件模板的限制以及服务 API

关于邮件模板和通知规则存在一些问题：

- 通知规则仅配合邮件模板工作，且 Service API 不需要通知规则。
- 通知规则的目标是邮件收件人是谁。虽然可以使用 Service API (`InternalServiceAccessor.getEmailProviderService()`) 访问收件人：`to`、`cc` 和 `bcc`。我们可以使用上下文搜索邮件属性。
- 邮件模板支持动态内容，但你需要学习新的 JSP 标签库。
- 如果使用邮件模板，可能需要学习新的标签库，例如 `_taskContextInformation`。如果你选择 Service API，可以使用简单的 Java 代码或流行的 Java 模板框架（如 Apache Velocity）生成邮件内容。
- 邮件模板在任务或事件、失败、完成等条件下运行。
- 而 Service API 可以在代码中的任何时候调用。

## 6.7 任务执行 Web 服务 (TEWS)

许多人对任务执行 Web 服务感到困惑。任务执行 Web 服务或 TEWS 将管理任务作为 Web 服务的生产者，而不是消费者。TEWS 是一个 Web 服务接口，允许第三方客户端应用程序向 CA IdentityMinder 提交远程任务。

![](img/image_rsrc8Y6.jpg)

*图 6-23 显示了 TEWS 的工作原理*

### 6.7.1 代码示例

我们开发了一个 Java 客户端来消费 TEWS。我们想通过 Java Web 服务执行我们的管理任务：`Update Location and Ext Number`。

请禁用之前代码：Policy Xpress、工作流、验证和邮件通知。

#### 配置：管理控制台

1. 在管理控制台中，点击 `Environments`。
2. 点击使用 Web 服务的环境名称。
3. 点击 `Advanced Settings`。
4. 点击 `Web Services`。
5. 如下所示填写值：

| 字段名称 | 值 | 说明 |
| :--- | :--- | :--- |
| Enable Execution | Check | 勾选以启用该环境的任务执行 Web 服务 (TEWS)。 |
| Enable WSDL Generation | Check | 勾选以启用该环境的 WSDL 生成。 |
| Enable admin_id | Check | TEWS 使用发送到 Web 服务的 SOAP 消息中的 admin ID 来身份验证请求。如果未选择此选项，则使用生成请求的用户 ID 来身份验证请求。 |
| SiteMinder Authentication | none | 对于身份验证，在我们的示例中使用了 none。 |

![](img/image_rsrc8Y7.jpg)

*图 6-24 显示了管理控制台*

#### 配置：Identity Manager 用户控制台

1. 登录 `User Console`。
2. 选择 `Roles and Tasks` 标签页。选择 `Admin Tasks`。选择 `Modify Admin Task`。
3. 搜索并选择管理任务：`Update Location and Ext Number`。
4. 选择 `Enable Web Services`。
5. 点击 `Submit` 保存更改。

![](img/image_rsrc8Y8.jpg)

*图 6-25 显示了管理任务配置*

### 代码

1. 使用 `Axis` API 从 WSDL 生成 Java 代码。我们使用命令 `WSDL2Java` 生成 Java 代码。请检查所有 jar 文件的路径。

```bash
java -cp lib/axis.jar;lib/log4j-1.2.jar;lib/commons-logging-1.0.jar;lib/commons-discovery-0.2.jar;lib/jaxrpc-1.5.jar;. org.apache.axis.wsdl.WSDL2Java -wrapArrays=true http://<host>:8080/idm/TEWS?wsdl
```

2. 将生成的代码拷贝到 eclipse。
3. 在 eclipse 中打开 Java 代码：`TEClient`。
4. 检查所需的参数：
   - `userId` 是你想修改的用户。
   - `adminDN` 是执行此任务的名称。稍后详细介绍。
   - `City` 和 `extNumber` 是我们想要修改的值。

```java
String userId = "allmi01";
String adminDN = "uid=superuser,ou=users,ou=na,dc=host,dc=com";
String city = "New York";
String extNumber = "1234";
```

### 工作原理

1. 从 eclipse 中运行我们的 Java 代码：`TEClient`。
2. 登录用户存储目录并检查城市属性。

代码从一个与管理任务标签同名的 Java 类开始：`BasicUpdateLocAndExtNumber`。该代码管理任务有两个标签页：搜索标签页和个人资料标签页。

```java
BasicUpdateLocAndExtNumber task = new BasicUpdateLocAndExtNumber();
...
task.setBasicUpdateLocAndExtNumberSearch(search);
...
task.setBasicUpdateLocAndExtNumberUserProfileTab(profileTab);
```

3. 对于搜索标签页，我们使用用户 ID 过滤器进行搜索。

```java
BasicUpdateLocAndExtNumberSearchFilter[] filters = new BasicUpdateLocAndExtNumberSearchFilter[1];
BasicUpdateLocAndExtNumberSearchFilter filter = new BasicUpdateLocAndExtNumberSearchFilter();
filter.setIndex(new BigInteger("0"));
filter.setField("%USER_ID%");
filter.setOp(OperatorType.EQUALS);
filter.setValue(userId);
filters[0] = filter;
search.setFilter(filters);
```

4. 我们在个人资料标签页中设置城市和 `extNumber` 属性。

```java
BasicUpdateLocAndExtNumberUserProfileTab profileTab = new BasicUpdateLocAndExtNumberUserProfileTab();
profileTab.setL(city);
profileTab.set_BAR_ExtNumber_BAR_(extNumber);
```

在我们的代码中，还有两个文件：`LogHandler.java` 和 `client-config.wsdd`。这些文件是 Axis 客户端日志器的辅助文件。你可以看到服务器和客户端之间的 soap 消息。你可以将此 xml 作为请求在 SOAP UI 或任何 Web 服务工具中使用。

SOAP Request

```xml
<?xml version="1.0" encoding="UTF-8"?><soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><soapenv:Body><TaskContext xmlns="http://tews6/wsdl"><admin_id>uid=superuser,ou=users,ou=na,dc=host,dc=com</admin_id></TaskContext><BookBasicUpdateLocAndExtNo xmlns="http://tews6/wsdl"><BookBasicUpdateLocAndExtNoSearch><Filter index="0"><Field>%USER_ID%</Field><Op>EQUALS</Op><Value>allmi01</Value></Filter></BookBasicUpdateLocAndExtNoSearch><BookBasicUpdateLocAndExtNoUserProfileTab><l>New York</l><_BAR_ExtNumber_BAR_>1234</_BAR_ExtNumber_BAR_></BookBasicUpdateLocAndExtNoUserProfileTab></BookBasicUpdateLocAndExtNo></soapenv:Body></soapenv:Envelope>
```

SOAP 响应

```xml
<?xml version="1.0" encoding="UTF-8"?><soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns="http://tews6/wsdl" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.xmlsoap.org/soap/envelope/ http://schemas.xmlsoap.org/soap/envelope/" ><soapenv:Body><ImsStatus version="6.0" ><transactionId>cb40e808-a5029bf5-aeacf1a7-1401ca</transactionId></ImsStatus></soapenv:Body></soapenv:Envelope>
```

## 身份验证与授权

在控制台中：Web 服务属性中，由于我们检查了选项 `enable admin_id`（允许身份冒充），我们可以传递任何管理员 DN 作为执行管理员任务的用户。

```java
ctx.setAdmin_id(adminDN);
```

如果您取消勾选 `enable admin_id` 选项（允许身份冒充），则需要进行身份验证。您必须选择 `SiteMinder Authentication`，并且修改代码以进行身份验证。



```java
Tews6SoapBindingStub stub = (Tews6SoapBindingStub) _port;stub.setUsername("SuperAdmin");stub.setPassword("test");stub.setMaintainSession(true);stub._setProperty("Cookie","SMCHALLENGE=YES");
```

对于授权，您可能需要在`web.xml`中进行配置。请参考官方文档`Java Programming Guide > Task Execution Web Service > Authorization`。

## 公共任务

当您定义管理员任务时，有一个复选框：`public task`。公共任务意味着任务适用于未登录 CA IdentityMinder 的用户。默认的公共任务是忘记密码和自注册。公共任务可以用于第三方在无需身份验证的情况下从 CA IdentityMinder 查询或获取数据的需求。

![](img/image_rsrc8Y9.jpg)

图 6-26 显示管理员任务配置中的公共任务复选框

公共任务 TEWS 的客户端代码需要更改 3 个地方：`search`、`port type` 和`context`。如果您修改了复选框`public task`，则需要从 WSDL 重新生成 Java 代码。

对于`search`，您不能使用搜索过滤器。您必须使用搜索主题，因为公共任务设计用于自修改。

```java
BookBasicUpdateLocAndExtNoSearchSubject[] subjects = newBookBasicUpdateLocAndExtNoSearchSubject[1];BookBasicUpdateLocAndExtNoSearchSubject subject = newBookBasicUpdateLocAndExtNoSearchSubject();subject.setUID("uid=allmi,ou=users,ou=northamerica,dc=server,dc=com");subject.setIndex(new BigInteger("0"));subjects[0] = subject;search.setSubject(subjects);task.setBookBasicUpdateLocAndExtNoSearch(search);
```

端口类型和上下文必须更改为公共任务。

```java
Tews6PublicPortType portType = locator.getTews6PublicPort();
//Tews6PortType portType = locator.getTews6Port();
PublicTaskContext ctx = new PublicTaskContext();
//TaskContext ctx = new TaskContext();//ctx.setAdmin_id(adminDN);
```

## 6.8 附加概念

### 用户自定义属性

业务逻辑任务处理器、逻辑属性、事件监听器等都有用户自定义属性。

![](img/image_rsrc8YA.jpg)

图 6-27 显示用户自定义属性

我们可以通过重写接口`com.netegrity.imapi.LifeCycle`的方法`init(java.util.Hashtable imeProperties)`来访问这些属性。您可以将这些值保留在类变量并在其他方法中使用。

```java
@Override
public void init(Hashtable imeProperties) throws Exception {
System.out.println(imeProperties.get("param1"));
}
```

### 访问托管对象

`EventContext`、`LogicalAttributeContext`、`NotificationRuleContext`、`ParticipantResolverContext`等扩展了`ProviderAccessor`。它们可以像`BLTHContext`或`Workflow`上下文一样执行搜索或修改托管对象。

### logErrorMessage

上下文扩展了`Logger`。`Logger`类提供了 4 个日志方法。它向应用程序服务器记录消息。

- `logDebugMessage(java.String message, boolean addDetail)`

- `logErrorMessage(java.String message, boolean addDetail)`

- `logInfoMessage(java.String message, boolean addDetail)`

- `logWarningMessage(message, boolean addDetail)`

如果`addDetail`为 true，它将打印有关管理员 DN、任务名称的详细信息。请参见 Java 文档。

## 6.9 总结

在本章中我们涵盖了业务逻辑任务处理器和工作流的所有 API。API 如下所示：

| API 名称和目的 | 阶段 | 类型 | 注意事项或限制 |

| :--- | :--- | :--- | :--- |

| 确定工作流活动中的参与者 | A | | 仅用于工作流 |

| 监听事件。执行自定义业务逻辑 | A | 在控制台中配置 | 监听特定事件；监听一组事件；事件监听器可以生成事件；流属于事件 |

| 在逻辑属性（显示在屏幕上）和物理属性（存储在数据存储中）之间转换 | S | 逻辑属性 | 逻辑属性可以与任何屏幕共享；屏幕定义属性 |

| 验证规则：验证用户在屏幕上输入的值符合正确的格式 | S | 任务级验证；目录级验证 | 任务级仅限定义的屏幕；目录级适用于所有屏幕 |

| 电子邮件通知：发送电子邮件 | S 或 A | 通知策略（Xpress 策略）；邮件模板；Service API | 通知策略对邮件接收者和内容有限制；Service API 需要编程 |

| 通知规则：决定用户接收电子邮件 | S 或 A | | 配合电子邮件使用 |

| 任务执行 Web 服务：Web 服务生产者。允许第三方客户端应用程序提交远程任务 | - | 取决于配置：是否启用了 admin_id？是否是公共任务？ | 需要配置身份验证和授权；阶段：A 或 S |

建议获取第二卷，其中包含许多高级示例。

# 附录 A：导入工作

请从书籍网站下载代码。请使用代码：120140924

导入工作

- 启动 IdentityMinder 服务器

- 运行 WorkPoint Designer

- 选择文件 > 导入

- 选择文件`IdmCodeWorkflow.zip`

- 选择全选

![](img/image_rsrc8YB.jpg)

图 A-1 显示导入屏幕

- 当屏幕询问是否导入到空数据库时，选择“否”。点击下一步。

- 当屏幕显示此导入将时，选择“将所有对象视为新对象”。点击下一步。

- 屏幕询问“如果遇到重复名称或引用”，重命名导入的名称或引用以唯一。点击下一步。

- 对话框将我们的导入代码列表，点击完成

- 选择打开进程并验证。你应该看到以“BookEx.”开头的流程。

![](img/image_rsrc8YC.jpg)

| 图 A-2 显示了所有流程 |

## 附录 B：热部署

CA IdentityMinder 不支持热部署。当你更新`<IdentityMinder>/custom`文件夹中的代码时，应用程序服务器不会加载你的类。有几种方法可以解决这个问题：

### 重启服务器或重新部署 IdentityMinder.ear

在更新代码后，你必须重启或重新部署。这种解决方案非常耗时，不适用于开发过程。

### OSGi

新版本的应用程序服务器支持`OSGi`规范。`OSGi`允许在运行时动态加载类。请检查你的应用程序服务器文档。

### 重命名代码

我更喜欢这种方法。它非常简单且不需要时间。CA IdentityMinder 需要两个要素：配置和代码。例如，我的代码是`MyCode.java`。

*   **BLTH**

    *   **Code**：将代码重命名为`MyCode1.java`，编译并拷贝到“custom”文件夹。

    *   **Configuration**：在管理任务的`BLTH`中更新 Java 类名。

*   **Workflow**

    *   **Code**：将代码重命名为`MyCode1.java`，编译并拷贝到“custom”文件夹。

    *   **Configuration**：更新节点中的代理脚本。

你也可以在 Listener 和其他 API 中执行同样的操作。

# 代码 : DGUJK101
