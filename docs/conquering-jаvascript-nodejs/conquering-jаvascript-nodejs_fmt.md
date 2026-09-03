

# 征服 JavaScript：Node.js

# 征服 JavaScript

毫无疑问，JavaScript 是可用最卓越且最常用的客户端编程语言之一。近年来，JavaScript 的使用范围不断扩大，现在它也被用于服务器端开发。Node.js 是一个极其流行的 JS 框架，旨在用于快速 Web 和应用程序的开发。

**征服 JavaScript：** Node.js 帮助读者掌握 Node.js 框架，以实现更快、更健壮的开发。本书是一份详细的指南，帮助开发者和编码人员利用 Node.js 实现更多功能。它简要介绍了基础知识，然后进入更高级、更的练习，帮助读者快速获得所需的知识。

**核心特性：**

- 讨论如何使用 Node.js 解决现实实际问题
- 提供全栈开发的完整覆盖
- 涵盖使用 Node.js 服务器端开发

这本书对于 Node.js 开发者以及参与游戏开发、移动应用、渐进式应用（现在甚至是桌面应用）的人员来说，都是非常有价值的参考书。

## 关于系列丛书

《征服 JavaScript》系列涵盖了广泛的主题，专门涉及 JavaScript 编程生态系统，如框架和库。该系列的每本书都专注于一个单一主题，并详细阐述该主题，特别关注真实世界的用法和以代码为中心的方法，遵循行业标准的编码范式，以帮助学习者获得对现实项目实用的专业知识。

该系列书籍的一些关键方面包括：

- 清晰易懂的文字，涵盖各种 JavaScript 相关的主题，并按相关性排序。
- 特别关注实践练习，提供大量的代码示例和程序。
- 引导式的 JS 编码方法，带有分步教程和演示。
- 高度强调技能的现实实用性，从而剔除冗余和很少使用的概念以及臃肿软件。
- 广泛的参考文献和资源，帮助读者从书中获得最大收益。

《征服 JavaScript》系列书籍假设对编码基础有基本的了解。

《征服 JavaScript》由 Sufyan bin Uzair 编辑，他是一位在计算领域拥有十年经验的作家和教育者。Sufyan 拥有多个学位，并在全球的大学和机构任教。到此为止，Sufyan 已编写和编辑了 50 多本书，为该系列带了丰富的经验。可以在 `sufyanism.com` 了解更多关于他的作品。

# 征服 JavaScript

Node.js

# 第 3 章 应用开发 II 55

# 第五步：测试与维护 63

流到底是什么？ 65

# 第 4 章 应用开发 III 83

为什么 NODE.JS 是最好的物联网 (IoT) 解决方案？ 83

NODE.JS 对 IoT 的具体优势是什么？ 84

- 使用 Node.js 进行应用开发 84
- Node.js IoT 协议易于与 Node.js 集成 84
- Node.js 是一种强大且快速的编程语言 85
- Node.js 是一种可扩展且资源高效的编程语言 85
- Node.js 提供数据安全 85

安全的身份验证 86

使用 Node.js 创建 API 非常简单 86

我可以在哪里开始用 Node.js 开发 IoT 项目？ 86

如何为 IoT 选择最佳数据库？ 87

如何让大数据为 IoT 项目发挥作用 88

该项目的未来架构将能够随之增长 89

对项目代码的工作是优化的下一步 89

实时 IoT 分析 89

一些基于 Node.js 的 IoT 应用有哪些示例？ 90

Uber 90

代码教程 91

模式 (Schema) 详述 92

MongoDB 中的地理空间索引 97

总结 103

# 第 5 章 代码优化 105

- 什么让 NODE.JS 的性能如此特别？ 106

运行到完成、单线程行为 106

检测内存泄漏 106

什么是事件循环以及它是如何工作的？ 107

事件循环与 NODE.JS 性能 107

为 Node.js 应用设置、运行和分析性能测试 107

在 Node.js 中创建性能测试分析 108

复制大型分布式系统 109

配置我们的监控 109

设置 Node.js 性能测试环境 110

运行我们的测试 110

如何让 Node.js 运行得更快 110

前端工具链 110

任务运行器和模块打包器 110

CSS 的模块和预处理器 111

图像 111

HTTP/2 和 SSL/TLS 111

使用缓存 112

改进数据管理技术 113

## 实现这一目标最有效的方法是什么？ 113

负载均衡 114

安全的客户端侧身份验证 115

保持轻量级且紧凑的代码 115

通过 WebSockets 与服务器有效通信 116

异步代码 116

同步代码 117

异步代码 117

查询增强 117

## 提高数据库性能/优化的基本策略概述 118

不惜代价避免使用 `SELECT` 118

使用 `WHERE` 子句 118

使用 `LIMIT` 对查询结果进行采样 118

避免选择唯一选项 119

根据需要使用通配符（百分号）字符 119

在非高峰时间运行查询 120

## 不使用会话 (Session) 120

脚本的追踪与日志 120

Winston 120

Morgan 121

Bunyan 121

并行性 121

| NODE.JS 加密准则 | 122 |
| :--- | :--- |
| 为什么 Node.js 存在安全问题？ | 122 |
| 主要 NODE.JS 安全关注点和建议 | 122 |
| 验证用户输入以限制 XSS 攻击 | 122 |
| 应不惜代价避免数据泄露 | 123 |
| 使用安全检查工具 (Linters) | 123 |
| 每个请求都应该实现访问控制 | 123 |
| 使用加密进行反序列化 | 124 |
| 执行 HTTP 响应头 | 124 |
| 创建日志和监控系统 | 125 |
| 身份验证应该是强大且彻底的 | 125 |
| 定期扫描应用程序漏洞 | 126 |
| 使用 Fluid 构建安全补丁流水线 | 126 |
| 通用提示 | 127 |
| 查看我们的命名规范 | 127 |
| 函数应该在何处模块化 | 128 |
| 正确的注释方式 | 128 |
| 调试时，注意上下文 | 128 |
| 解构赋值 (Destructuring) | 129 |
| 不要重犯同样的错误 | 129 |
| 回调礼仪 | 129 |
| 务必双检回调问题 | 129 |
| 在回调中进行返回 | 130 |
| 仅在同步代码中使用 `try-catch` | 131 |
| 尽可能远离它 | 131 |
| 有效地使用异步模式 | 132 |
| 错误纠正 | 132 |
| 操作错误 | 132 |
| 处理操作错误 | 132 |

编程错误 132

作为异步

# 第 6 章 总结 135

Node.js 的职业前景 135

与其他框架一起使用 Node.js 137

利用 Node.js 的优势是什么 138

框架及其类型 138

用于 Node.js 的 Web 开发框架 142

Loopback 142

Total 142

我们如何选择应用框架？ 143

Node.js 与 React 兼容吗？ 144

Angular 应用 144

Angular 与 React 结合 146

引言 146

前提条件 146

开发阶段 147

项目结构 147

Node.js API 148

练习 149

如何创建一个生产就绪的项目 152

总结 153

参考文献 155

索引 159

## Zeba Academy – 征服 JavaScript

《征服 JavaScript》系列书籍由 Zeba Academy 团队成员编写，由 Sufyan bin Uzayr 领导，成员包括：

- Divya Sachdeva
- Jaskiran Kaur
- Simran Rao
- Aruqqa Khateib
- Suleymen Fez
- Ibbi Yasmin
- Alexander Izbassar

Zeba Academy 是一家教育科技（EdTech）企业，主要为 STEM 领域的学习者开发课程和内容，并为全球学习者和教育者提供教育咨询和指导。

此外，Zeba Academy 还积极致力于在独体国家运营 IT 学校，目前正与许多大学和机构合作。

欲更多信息，请访问 `https://zeba.academy`

## 引言

本章内容

- Node.js 基础知识
- Node.js 的特性
- 优点与缺点

本章将让我们了解 Node.js 的基础知识，包括它大量的特性、模块和基础设施。稍后我们将讨论使用 Node.js 的优缺点。

JavaScript 毫无疑问是可访问的最知名且最常用的客户端编程语言之一。它主要用于在线前端开发，但也是跨平台开发领域非常有价值的选择。它还因用于许多其他知名生态系统而闻名，包括 React Native、PhoneGap、Titanium、Apache、NativeScript 和 Appcelerator。JavaScript 的使用范围近年来不断扩大，现在也用于服务器端开发。Node.js 无疑是 Web 开发领域这一巨大转变的幕后功臣。

开发者社区中的一些人将名为 Node.js 的技术誉为“下一个 Ruby on Rails”。然而，它并不是万灵妙药，也不适用于所有的编程场景。它的入门门槛低得惊人，因为该框架是为以下广泛使用的 JavaScript 创建的，而且使用 Node 构建应用程序的理由——特别是低延迟、实时应用——正变得越来越具有说服力。

Node.js 是一个运行时环境，Node.js 拥有一个开源且跨平台的 JavaScript 运行时环境，是几乎适用于任何任务的流行工具。Node.js 在浏览器之外运行 V8 JavaScript 引擎，而该引擎是 Google Chrome 的核心。因此，Node.js 运行极快。

这使得 Node.js 可以处理数百个并发连接，而不会产生线程并发控制的开销，而这可能是错误产生的主要来源。

Node.js 还带有一个更大的 JavaScript 模块库，极大地促进了 Node.js Web 应用程序的构建。

`Node.js = 运行时环境 + JavaScript 库`

简单来说，这意味着整个网站可以运行在单一“栈”上，允许你专注于项目的业务目标，而不是开发和维护。由于 Node.js 是开源的，它是完全免费的，并由全球开发者社区不断更新。需要记住，Node.js 是一个运行时环境，而不是像传统应用程序那样的框架或库。

运行时环境（也称为 RTE）是一组开发者可以编写代码的 Web API，以及一个读取代码的 JavaScript 引擎。这使其变得轻量、适应且易于部署，所有这些将帮助你优化和加速应用程序项目。

数据类型：Node.js 包含了许多与 JavaScript 相似的数据类型。

- 布尔（Boolean）
- 未定义（Undefined）
- 空（Null）
- 字符串（String）
- 数字（Number）

## 弱类型：Node.js 提供弱类型，这意味着你不需要提前定义变量将放入什么类型的数据。在 Node.js 中，我们使用 `var` 关键字来声明任何类型的变量。

## 示例：

```javascript
// 存储数字数据类型
var a = 40;
console.log(typeof a);
// 变量存储字符串数据类型
a = "GOOD MORNING";
console.log(typeof a);
// 变量存储布尔数据类型
a = false;
console.log(typeof a);
// 变量存储未（无值）数据类型
b = No value;
console.log(typeof a);
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

## 示例：

```javascript
var company = {
Name: "JOHNNY DEPP",
Address: "LOS ANGELIS",
Contact: "+1198665432109",
Email: "johnny.depp@yahoo.org"
};
// 显示对象信息
console.log("Data of Customer:", customer);
// 显示变量类型
console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数数量。

## 示例：

```javascript
// Node.js 中的函数通过使用 function 关键字定义，
// 后跟函数的名称和参数。
// 在 Node.js 中，我们不需要为参数声明数据类型。

function divide(num1, num2) {
    return num1 / num2;
}
console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

## 示例：

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};
// 显示对象信息
console.log("Data of Customer:", customer);
// 显示变量类型
console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

## 示例：

```javascript
function divide(num1, num2) {
    return num1 / num2;
}
console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

## 示例：

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};
// 显示对象信息
console.log("Data of Customer:", customer);
// 显示变量类型
console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

## 示例：

```javascript
function divide(num1, num2) {
    return num1 / num2;
}
console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

## 示例：

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};
// 显示对象信息
console.log("Data of Customer:", customer);
// 显示变量类型
console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

## 示例：

```javascript
function divide(num1, num2) {
    return num1 / num2;
}
console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

## 示例：

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};
// 显示对象信息
console.log("Data of Customer:", customer);
// 显示变量类型
console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

示例：

```javascript
function divide(num1, num2) {
    return num1 / num2;
}
console.log(divide(10, 2));
```




```javascript
function divide(
1, num2) {
    
 num1 /
2;



.


(1
, 2





.
```

# Zeba Academy – 征服 JavaScript

《征服 JavaScript》系列书籍由 Zeba Academy 团队成员编写，由 Sufyan bin Uzayr 领导，成员包括：

- Divya Sachdeva
- Jaskiran Kaur
- Simran Rao
- Aruqqa Khateib
- Suleymen Fez
- Ibbi Yasmin
- Alexander Izbassar

Zeba Academy 是一家教育科技（EdTech）企业，主要为 STEM 领域的学习者开发课程和内容，并为全球学习者和教育者提供教育咨询和指导。

此外，Zeba Academy 还积极致力于在独体国家运营 IT 学校，目前与许多大学和机构合作。

欲更多信息信息，访问访问://zeba.academy

## 引言

### 本章内容

- Node.js 基础知识
- Node.js 的特性
- 优点与缺点

本章将让我们了解 Node.js 的基础知识，包括它大量的特性、模块和基础设施。稍后我们将讨论使用 Node.js 的优缺点。

JavaScript 毫无疑问是可访问的最知名且最常用的客户端编程语言之一。它主要用于在线前端开发，但也是跨平台开发领域非常有价值的选择。它还因用于许多其他知名生态系统而闻名，包括 React Native、PhoneGap、Titanium、Apache、NativeScript 和 Appcelerator。JavaScript 的范围近年来不断扩大，现在也用于服务器端开发。Node.js 无疑是 Web 开发领域这一巨大转变的幕后功臣。

开发者社区中的一些人将名为 Node.js 的技术誉为“下一个 Ruby on Rails”。然而，它并不是万灵妙药，也不适用于所有的编程场景。它的入门门槛低得惊人，因为该框架是为广泛使用的 JavaScript 创建的，而且使用 Node 构建应用程序的理由——特别是低延迟、实时应用——正变得越来越具有说服力。

# 2 ■ 征服 JavaScript

Node.js 是一个运行时环境，Node.js 拥有一个开源且跨平台的 JavaScript 运行时环境，是几乎适用于任何任务的流行工具。Node.js 在浏览器之外运行 V8 JavaScript 引擎，而该引擎是 Google Chrome 的核心。因此，Node.js 运行极快。

这使得 Node.js 可以处理数百个并发连接，而不会产生线程并发控制的开销，而这可能是错误产生的主要来源。

Node.js 还带有一个更大的 JavaScript 模块库，极大地促进了 Node.js Web 应用程序的构建。

`Node.js = 运行时环境 + JavaScript 库`

简单来说，这意味着整个网站可以运行在单一“栈”上，允许你专注于项目的业务目标，而不是开发和维护。由于 Node.js 是开源的，它是完全免费的，并由全球开发者社区不断更新。需要记住，Node.js 是一个运行时环境，而不是像传统应用程序那样的框架或库。

运行时环境（也称为 RTE）是一组开发者可以编写代码的 Web API，以及一个读取代码的 JavaScript 引擎。这使其变得轻量、适应且易于部署，所有这些将帮助你优化和加速应用程序项目。

### 数据类型

Node.js 包含了许多与 JavaScript 相似的数据类型。

- 布尔（Boolean）
- 未定义（Undefined）
- 空（Null）
- 字符串（String）
- 数字（Number）

## 弱类型

Node.js 提供弱类型，这意味着你不需要提前定义变量将放入什么类型的数据。在 Node.js 中，我们使用 `var` 关键字来声明任何类型的变量。

### 示例

```javascript
// 存储数字数据类型

var a = 40;

console.log(typeof a);

// 变量存储字符串数据类型

a = "GOOD MORNING";

console.log(typeof a);

// 变量存储布尔数据类型

a = false;

console.log(typeof a);

// 变量存储未（无值）数据类型

b = No value;

console.log(typeof a);
```

### 对象和函数

Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

#### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数数量。

# 4 征服 JavaScript

### 示例

```javascript
// Node.js 中的函数通过使用 function 关键字定义，
// 后跟函数的名称和参数。
// 在 Node.js 中，我们不需要为参数声明数据类型。

function divide(num1, num2) {
  return num1 / num2;
}

console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

### 示例

```javascript
function divide(num1, num2) {
  return num1 / num2;
}

console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

### 示例

```javascript
function divide(num1, num2) {
  return num1 / num2;
}

console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

### 示例

```javascript
function divide(num1, num2) {
  return num1 / num2;
}

console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

### 示例

```javascript
function divide(num1, num2) {
  return num1 / num2;
}

console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```

函数：Node.js 中的函数通过使用 `function` 关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要检查参数的数量。

### 示例

```javascript
function divide(num1, num2) {
  return num1 / num2;
}

console.log(divide(10, 2));
```

对象和函数：Node.js 对象与 JavaScript 对象相同，它们类似于变量，并包含类型为“名称:值”对的多个值。程序中的名称和值用冒号分隔，每对之间用逗号分隔。

### 示例

```javascript
var company = {
  Name: "JOHNNY DEPP",
  Address: "LOS ANGELIS",
  Contact: "+1198665432109",
  Email: "johnny.depp@yahoo.org"
};

// 显示对象信息

console.log("Data of Customer:", customer);

// 显示变量类型

console.log("Data of Customer:", typeof customer);
```




##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。函数

在 Node.js 中，函数通过使用`function`关键字定义，后跟函数的名称和参数。在 Node.js 中，我们不需要为参数声明数据类型，也不需要声明参数的类型。

参数类型可以是：

- 布尔值（Boolean）
- 空值（null）
- 字符串（String）
- 数字（Number）

## 简介

## 文本编辑器

这里是你编写代码的地方。编辑器包括 Windows 记事本、OS Edit 命令、Brief、Epsilon、EMACS 以及 vim 或 vi 等。在不同的操作系统上，文本编辑器的名称和版本可能有所不同。例如，可以使用 Windows 记事本，而 vim 或 vi 可以在 Windows、Linux 或 UNIX 上使用。源文件是包含你用编辑器生成的源码的文件。在 Node.js 项目中，源文件通常使用`.js`后缀。在开始编程之前，请确保你已经安装了文本编辑器，并且具备足够的编写计算机程序、将其保存到文件以及运行它的知识。

## Node.js 运行时

JavaScript 用于编写源文件中的源码。你的 JavaScript 代码将使用 Node.js 解释器进行解释和执行。Node.js 分发支持 SunOS、Linux、Mac OS 和 Windows 操作系统，以及 32 位 (386) 和 64 位 (amd64) x86 CPU 架构。

## 在此处下载 Node.js 存档

Node.js 下载提供最新版本的 Node.js 可安装 zip 文件。本书编写时各种操作系统上的可用版本列下所示。

| OS | 获取名称 |
| :--- | :--- |
| Windows | `node-v18.2.0-x64.msi` |
| Linux | `node-v18.2.0-Linux-x64.tar.gz` |
| Mac | `node-v18.2.0-darwin-x64.tar.gz` |
| SunOS | `node-v18.2.0-sunos-x64.tar.gz` |

## UNIX/LINUX/MAC OS X 和 SUNOS 安装

下载并提取`node-v6.3.1-osname.tar.gz`存档到`/tmp`，然后根据你的操作系统架构将提取出的文件移动到`/usr/local/nodejs`目录。

## Windows 安装

要安装 Node.js，请运行 MSI 文件并按照说明操作。

## 征服 JavaScript

安装程序默认使用`C:\Program Files\nodejs`中的 Node.js 包。Windows 上的 PATH 环境变量应由安装程序设置为`C:\Program Files\nodejs`目录。重启任何打开的命令提示符使更改生效。

### Node.js 具有许多特性

以下是使 Node.js 成为架构师首选的关键特性：

- **异步和事件驱动**：Node.js 库中的 API 都是异步的（非阻塞的），这意味着 Node.js 服务器永远不会等待 API 的数据，而在访问上一个 API 后移动到下一个 API，并通过名为 Node.js 的通知机制帮助服务器从上一个请求中获取响应。
- **速度**：Node.js 库的代码执行速度极快，因为它构建在 Google Chrome 的 V8 JavaScript 引擎之上。
- **单线程**：它使用带有事件循环的单线程模型，具有非常高的可扩展性。事件方法允许服务器以非阻塞和可扩展的方式响应，与生成受限线程处理请求的传统服务器不同。它利用单线程程序可以处理比 Apache HTTP Server 等传统服务器多得多的请求。
- **无数据缓冲**：在 Node.js 应用中，数据永远不会缓冲。这些程序只是分段输出数据。
- **许可证**：MIT 许可证规范了 Node.js 的发布。

### 谁在使用 Node.js？

以下指向一个 GitHub 页面的链接，其中列出了 Node.js 项目、应用程序和企业的详尽列表。eBay、General Electric、GoDaddy、Microsoft、PayPal、Uber、Wikipedia、Yahoo! 和 Yammer 只是列表上的少数公司。

### 你何时应该使用 Node.js？

Node.js 证明是优秀技术伙伴的领域如下：

- I/O 密集型应用程序
- 流式数据应用程序
- 实时运行的大数据应用程序 (DIRT)
- 基于 JSON API 的应用程序
- 单页的应用程序

## NODE.JS 的优势

当 CTO 或技术专业人员在考虑 Node.js 对我们的 Web 应用、技术可扩展性、速度、性能、应用限制等优缺点时，必须考虑几个要素。你的应用程序进入市场的速度取决于你在此阶段做出的决策。

在互联网上，JavaScript 是最广泛使用的客户端语言。在 2009 年 Node.js 发布后，它变得极其简单。让我们来看看使用 Node.js 的优势。

### 可扩展性非常直观

Node.js 最具吸引力的特性是它易扩展。通过向现有系统添加新节点，应用程序可以进行水平扩展。

### 易于理解

大多数开发者熟悉 JavaScript，因为它是最常用的编程语言之一。由于几乎所有的浏览器都支持 JavaScript，这使得代码投入运行变得容易得多。

### 以交付卓越结果而闻名

如前所述，Node.js 理解代码，Google 的 V8 JavaScript 引擎将代码编译为机器码。运行时环境提高了代码性能。

### 缓存的优势

单个元素也可以在 Node.js 运行时环境中缓存。第一个模块每次被请求时都会缓存到程序内存中。由于缓存有助于程序更快地加载网页并更快速地响应用户，开发者不需要重复执行代码。

### 允许你构建自己的应用程序

Node.js 的另一个优势是其在创建应用和软件方面的灵活性。在实施规则方面，Ruby on Rails 缺乏这种能力。

### 同时处理大量请求

由于 Node.js 提供了使用非阻塞 I/O 系统的选项，开发者可以一次处理多个查询。竞争平台如 Ruby 或 Python 管理并发查询方面不如该系统。

### Node.js 是一个具有高度灵活性的框架

Node.js 以可扩展性闻名，这意味着你可以对其进行修改和扩展以匹配你的个人需求。JSON 也可以用于提供 Web 服务器和客户端之间交换数据的方法。它还内置了用于创建 HTTP、TCP 和 DNS 服务器等 API。

### 大型且活跃的群体提供社区支持

Node.js 有一个庞大且活跃的开发者社区，一直对其开发做出贡献。

### 全栈 Node.js

Node.js 是后端功能完备的选择。

### API 不稳定：不稳定 API 导致重大代码更改

频繁的 API 更新以及随之缺乏稳定性是大多数开发者必须应对的 Node.js 主要问题之一。因此，开发者被迫定期更新访问代码以确保符合当前版本的 Node.js API。

### 如果你没有库支持系统，你的代码可能会受到损害

许多 Node.js NPM 注册表和库质量差、不完整且描述糟糕。因此，如果业余人员使用 Node.js 构建 Web 应用程序，这种监控的缺失将变得复杂。

## 思考 JavaScript

只有当具备项目专业知识且素质良好的人参与时，你的项目才能成功。由于 Node.js 是一项拥有大量工具和模块的开源技术，维持高代码标准可能会很困难。选择最佳 IT 合作伙伴来为您设计 Web 应用程序以获得卓越成果是令人兴奋的。

## 难以维护的代码

由于异步处理方式的本质性，该技术在事实上依赖于回调函数（callbacks）。这种方法会在队列中的每个任务执行后立即运行，确保多个队列中的任务仍在后台运行。当用户接收到过量复杂的回调时，就会发生“回调地狱”（Callback Hell）。这种情况使得代码维护变得更加困难。

### 执行重型任务时，性能会降低

尽管 Node.js 具有单线程和事件驱动的优势，但也意味着它在执行密集的 CPU 计算时性能不佳。

## 核心概念

这是一个基于 JavaScript 的框架，用于构建在线聊天应用程序、视频流网站、单页应用以及一系列其他 I/O 密集型 Web 应用。它基于 Google Chrome 中的 JavaScript V8 引擎，被大型企业和小型企业使用（例如 Netflix、Paypal、NASA 和 Walmart 等）。

数千名开发者使用 Node.js 是因为它是开源且完全免费的。与 Java 或 PHP 等服务端技术相比，它具有许多优点，使其成为更优的选择。

该应用程序运行在单个进程中，而不是为每个请求创建一个新线程。因为标准库包含一组异步 I/O 原语，这些原语不允许 JavaScript 代码发生阻塞，而且 Node.js 中的库通常使用非阻塞范式创建，因此阻塞行为是特例。当 Node.js 执行 I/O 操作（例如从网络读取数据、访问数据库或访问文件系统）时，它不会挂起线程并浪费 CPU 周期等待响应，而是在收到响应后立即重启操作。这允许 Node.js 处理成百个并发连接，而不会产生线程并发的开销。

## 导言

控制，这可能是错误的主要来源。Node.js 有一个巨大的优势，因为数百万为浏览器编写 JavaScript 的前端开发者现在除了生成客户端代码外，现在还可以生成服务器端代码，而无需学习新语言。

你不需要等待所有用户的浏览器更新就能在 Node.js 中利用新的 ECMAScript 标准，因为你可以通过切换 Node.js 版本来选择使用哪个 ECMAScript 版本，你还可以通过带有标志执行 Node.js 来激活特定的实验性功能。

## 有很多库

npm 凭借其简单的结构，帮助了 Node.js 生态系统的增长，npm 注册表现在存储了超过 100 万个你可以免费使用的开源包。

## NODE.JS 历史简述

信不信，Node.js 只有 13 岁。JavaScript 已经 26 岁了，而 Web 已经 33 岁了。在技术领域，13 年并不是一个长的时期，但 Node.js 似乎已经存在了很久。为了客观描述这一切，我们将在本章中构建 Node.js 历史的蓝图。

JavaScript 是由 Netscape 开发的一种计算机语言，作为用于操作 Netscape 浏览器内 Web 页面的脚本工具。Netscape 的营收模式包括提供 Web 服务器或集成 Netscape LiveWire（一种允许人们使用服务端 JavaScript 创建动态页面的工具）。遗憾的是，Netscape LiveWire 失败了，而得益于 Node.js，服务端 JavaScript 才刚刚获得关注。

> Node.js 起起的时间节点结束了一个关键因素。就在几年前，“Web 2.0”服务（如 Flickr、Gmail 等）开始将 JavaScript 确认为一种更相关的语言，向世界展示了现代 Web 体验是什么样的。

随着浏览器竞争为消费者提供最佳性能，JavaScript 引擎得到了巨大的改进。主要的浏览器开发团队坚持不懈地增加对 JavaScript 的支持，并寻找加速 JavaScript 执行的方法。由于竞争的结果，Node.js 引擎 V8（也称为 Chrome V8，因为它是 Chromium 项目的开源 JavaScript 引擎）得到了显著改进。

## 思考 JavaScript

- 2009：Node.js 诞生，创建了第一形式的 npm。
- 2010：Express 诞生，创建了第一形式的 npm。
- 2011：创建了 npm 1.0 版本；大型公司开始采用 Node.js（LinkedIn, Uber 等），Hapi 诞生。
- 2012：采用继续快速进行。
- 2013：第一个博客平台 ghost 采用 Node.js，Ko 诞生。
- 2014：重大分叉：io.js 引入（带有 ES6 支持）。
- 2015：Node.js 基金会诞生；Io.js 与 Node.js 合并并发布了 Node.4 版本。
- 2016：创建了 Node.6；创建了 Yarn 并发生了 leftpad 事件。
- 2017：创建了 Node.js 8；HTTP/2；VS 在测试套件中引入 Node.js。
- 2018：创建了 Node.js 10 和 11，ES 模块处于实验模式。
- 2019-2022：创建了 Node.js 12-18。

Node.js 的时序发展。

## 如何安装 Node.js

Node.js 可以通过多种方式设置。官方包可以在 https://nodejs.dev/en/download/ 获取所有主要平台。包管理器是安装 Node.js 的一种非常方便的方法。在这种情况下，每个操作系统都有自己的。

Node.js 有一个巨大的优势，因为数百万为浏览器编写 JavaScript 的前端开发者现在除了生成客户端代码外，还可以生成服务器端代码，而无需学习新语言。

你不需要等待所有用户的浏览器更新就能在 Node.js 中利用新的 ECMAScript 标准，因为你可以通过切换 Node.js 版本来选择使用哪个 ECMAScript 版本，你还可以通过带有标志执行 Node.js 来激活特定的实验性功能。

## 导言

## 要使用 Node.js，你需要了解多少 JavaScript？

要达到对自己的才华充满信心是很重要的。在进入 Node.js 之前，我们建议你掌握以下概念：

- 词法结构 (Lexical structure)
- 表达式 (Expressions)
- 类型 (Types)
- 类 (Classes)
- 变量 (Variables)
- 箭头函数 (Arrow functions)
- 循环 (Loops)
- 作用域 (Scopes)
- 数组 (Arrays)
- 字面量 (Literals)
- 分号 (Semicolons)
- 严格模式 (Strict mode)
- ECMAScript 6

## 思考 JavaScript

## NODE.JS 与浏览器：有什么区别？

JavaScript 是浏览器和 Node.js 都使用的语言。构建基于浏览器的应用程序与开发 Node.js 是不同的。尽管 JavaScript 被不断使用，但存在一些关键区别使得体验非常不同。对于经常使用 JavaScript 的前端开发者来说，Node.js 提供了一个巨大的优势：用同一种语言编写前端和后端的能力。处于独特的地位。

## 生态系统发生了变化

在大多数情况下，你在与浏览器中的 DOM 或其他 Web 平台 API（如 Cookies）交互。这些在 Node.js 中并不存在。你没有`document`、`window`或任何其他浏览器提供的对象。此外，我们无法访问 Node.js 通过模块提供的所有精美 API，例如文件系统访问。另一个显著区别是，在 Node.js 中，你对环境拥有控制权。除非你创建一个可以在任何地方部署的开源应用程序，否则你已经知道自己将使用哪个 Node.js 版本，而在浏览器环境中，你无法自由选择想看到的内容。这意味着我们可以使用由 Node.js 版本导入的任何现代 ES6-7-9 JavaScript。由于演进如此迅速，浏览器更新缓慢，我们可能在 Web 上使用较早的 JavaScript/ECMAScript 版本。可以使用 Babel 将我们的代码转换为 ES5 兼容后再发送到浏览器，但在 Node.js 中我们不需要它。另一个区别是 Node.js 支持两种 CommonJS 和 ES 模块系统，尽管 ES 模块标准直到现在才在浏览器中实现。但实际上，这意味着在 Node.js 中，我们可以同时使用`require()`和`import`，而在浏览器中，我们只能使用`import`。

## 使用 NODE.JS 的 WEB 应用架构

Node.js 是一个基于 JavaScript 的平台，用于构建 I/O 密集型 Web 应用，如聊天应用、多媒体流网站等。它基于 Google Chrome 的 V8 JavaScript 引擎。它是一种在服务器上运行并由连接互联网的客户端浏览器渲染以访问所有资源的 Web 软件。

一个典型的 Web 应用由以下元素组成：

- 客户端（Client）是向服务器发送请求并与其交互的用户。
- 服务器接收客户端的请求，然后执行必要的操作并将结果返回给客户端。它充当前端与存储数据之间的桥梁，允许用户操作信息。
- 数据库（database）是存储 Web 应用数据的地方。根据客户端请求对数据进行创建、修改或删除。

## Node.js 服务器架构

Node.js 使用“单线程事件循环”（Single Threaded Event Loop）设计来管理多个并发客户端。Node.js 处理模型使用 JavaScript 的事件模型和 JavaScript 回调机制。它基于两个核心思想：

- 异步模型
- I/O 活动是不阻塞的。

### 异步模型

与许多最流行的 Web 框架不同，Node.js 从一开始就鼓励异步编码。

在 Node.js 中，在函数名之前使用`async`来创建一个异步函数。结果是，异步方法返回一个隐式的`Promise`。异步函数有助于通过事件循环异步编写基于 promise 的代码。异步函数总是返回一个值。要等待 promise 完成，请在异步函数内部使用`await`函数。这强制代码等待 promise 完成并返回结果。

使用以下命令从 npm 在 Node.js 中安装 async：

```bash
npm i async
```

使用`needle()`函数在我们的 Node.js 应用中使用`async`。

**示例：** 在 Node.js 中创建一个异步函数来计算整数的平方。

- 为我们的项目创建一个文件夹。
- 要在项目文件夹中初始化`package.json`文件，运行下面的命令。
  `npm init -y`
- 使用以下命令安装 async：
  `npm i async`
- 创建一个`server.js`文件并将下面的代码粘贴到其中。

使用`npm start`运行以下代码：

```javascript
var async = require("async");

function square(x) {
  return new Promise((resolve) => {
```




在学习开发异步代码时，有几个关键点需要记住；否则你的代码将经常以意想不到的方式执行。

## 避免使用同步函数，转而使用异步函数

`Node.js`核心中的许多函数都有同步和异步版本。在大多数情况下，使用异步函数将显著有利；你为什么要用`Node.js`呢？以`fs.readFile`为例来对比这两者：

```javascript
var fs = require('fs');

fs.readFile('example.file', 'utf8', function (error, document) {
  if (error) {
    return console.log(error);
  }
  console.log(document);
});

//=====================

var data = fs.readFileSync('example.file', 'utf8');
console.log(data);
```

仅仅看这些代码段，同步版本看起来更紧凑。然而，异步变体之所以难以编写是有其原因的。在同步版本中，世界会暂停，直到文件读取完成——我们的进程将停留在那里，等待操作系统完成（操作系统处理所有文件系统任务）。

相反，异步版本并没有暂停时间；相反，在文件读取完成后会调用回调函数。在此期间，我们的进程可以执行其他代码。当读取或保存单个或两个文件时，同步和异步 I/O 之间的区别可能忽略不微。然而，当我们有许多需要文件或数据库 I/O 的请求时，尝试同步处理这些 I/O 对性能是非常不利的。

## 回调（Callbacks）

在`Node.js`中，回调是异步操作的基础范式。作为异步函数最后一个参数提供的函数通常被称为回调。函数生成的任何返回值或错误消息都会传递给回调。

## 事件发射器（Emitter of Events）

`Node.js`的另一个基本用法是事件发射器。`require('events')`是`Node.js`中的一个函数对象`{[native code]}`。

### 异步代码

在编写异步代码时，有几个关键点需要记住；否则你的代码将经常以意想不到的方式执行。

相反，异步版本并没有暂停时间；相反，在文件读取完成后会调用回调函数。在此期间，我们的进程可以执行其他代码。

### 非阻塞 I/O 操作

`Node.js`核心许多许多都有同步和异步版本。在大多数情况下，使用异步函数将显著有利；你为什么要用`Node.js`呢？

### 回调

在`Node.js`中，回调是异步操作的基础范式。作为异步函数最后一个参数提供的函数通常被称为回调。函数生成的任何返回值或错误消息都会传递给回调。

### 同步回调 vs 异步回调

考虑以下：

```javascript
// 同步回调示例
function square(x) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(Math.pow(x, 4));
    }, 5000);
  });
}

async function output(x) {
  const ans = await square(x);
  console.log(ans);
}

output(16);
```

```javascript
// 异步回调
const fs = require('fs');

fs.readFile('example.file', 'utf8', function (error, document) {
  if (error) {
    return console.log(error);
  }
  console.log(document);
});
```



# 简介

- 用户向服务器发送请求（阻塞或非阻塞）以执行任务。
- 请求首先通过服务器的事件队列（Event Queue）发送。
- 事件队列按顺序将请求发送到事件循环（Event Loop）。事件循环检查请求类型（阻塞或非阻塞）。
- 不需要外部资源的非阻塞请求将由事件循环处理，并将响应返回给请求客户端。
- 对于阻塞请求，会分配一个单线程进行处理，以便使用外部资源完成任务。
- 当过程完成后，请求将路由到事件循环，由其将响应返回给客户端。

## Node.js 是前端框架还是后端框架？

Node.js 有时会被开发者误解为仅用于构建服务器的后端工具。事实并非如此：Node.js 既可以用于前端，也可以用于后端。Node.js 框架之所以在开发灵活且可扩展后端的开发者中流行，原因之一是它们事件驱动、非阻塞的特性。另一方面，前端开发者在自己的工作中也能同样清晰地感受到 Node.js 的这些优势。Node.js 包含`env`属性，它存储了进程启动时设置的所有环境变量。

让我们来看看为什么 Node.js 适用于后端和前端开发的几个原因：

- 得益于 Express.js 和 Meteor.js 等框架，JavaScript 是开发后端和前端代码的通用语言。一些流行的技术栈，如 MERN 使用 Express.js 作为后端（一种 Node.js 框架）。前端和后端之间可以复用组件。
- 开发效率和生产力：通过减少多种语言之间的上下文切换，可以节省大量的开发者时间。因为后端和前端技术相似，两端使用 JavaScript 可以提高性能。

## 征服 JavaScript

- 巨大的社区：在线社区的大小影响了成功开发周期完成的速度。如果你遇到问题，很有可能别人已经解决过它并在 Stack Overflow 上分享了解决方案。Node.js 在其流行的运行时及其包方面主要依赖这个活跃且参与度高的社区。

## 什么时候应该使用 Node.js？

- 聊天：聊天应用程序是 Node.js 的最佳示例之一。它是一种数据密集、轻量级、高流量且运行在多个平台上的应用程序。它也是一个很好的学习用例，因为它简单，并且涵盖了在 Node.js 应用中常见的多数特性和范式。
- 基于对象数据库的 API：除了实时应用外，Node.js 还可以用于暴露对象数据库中的数据。Node.js 工作时不需要数据转换，也不会阻碍与 JSON 存储数据之间的不匹配。如果我们使用 Rails，则需要将你的 JSON 模型转换为二进制模型。只有当数据被 AngularJS、Backbone.js 等其他框架消费时，我们才能通过 HTTP 将它们发布为 JSON。我们使用 Node.js 为客户端提供 JSON 对象以及供其使用的 REST API。此外，我们无需在从数据库读取或写数据时担心转换 JSON。总而言之，我们在服务器-客户端和数据库通信中使用统一的数据序列化格式。
- 流式数据：在典型的 Web 平台中，HTTP 响应和请求被视为独立的事件处理。从字面意义上说，它们是流。这可以创建一些真正神奇的功能。例如，我们可以在文件上传的同时对其进行处理。这是因为数据是以流传递的，允许我们实时处理它。对于实时视频和音频编码，这是可能的。这也可以用于在不同源之间代理数据。

## Node.js 的框架及其各种形式

每种 Web 应用技术都配有一套框架，在开发过程中协助特定的用用例。对于 Node.js，有三种框架可供选择。

### MVC（模型视图控制器）框架

视图（Views）、模型（Models）和控制器（Controllers）是 MVC 架构的三个部分，划分了应用程序逻辑。这种划分有助于关注分离，使应用程序易于扩展和维护。Express.js 就是 MVC 框架的一个示例。

### 全栈 MVC 框架

这些框架用于构建实时应用，因为它们包含了各种库、脚手架、模板引擎和其他开发工具。它还可以处理应用程序的后端和前端开发。

### REST API 框架

凭借著名的 REST API 体验支持，该框架以极快速度构建应用而闻名。这意味着我们不需要担心网络应用架构风格带来的问题。

让我们来看几个最流行的 Node.js 框架。

### Express.js

Node.js 框架无疑是 Express.js。它以经典的代码架构和简单的方法而闻名。因为 Express.js 的学习曲线低，即使对 Node.js 编程技能和环境有基本的了解也足够。Express 是所有 Node.js 应用的首选要求，因为它轻松地补充了 Node.js 闪快的 I/O 操作和单线程特性。许多大型公司，如埃森哲、Twitter、Uber 和 IBM 都使用 Express 开发应用。

### Koa.js

Koa.js 是构建各种在线服务（通常称为 API）的理想选择。通过使用类栈的方法，Koa 成功处理了 HTTP 中间件，使 API 开发变得简单而愉快。此外，它规范了 Node 错误，因为不同类型的信息可以使用相同的 URL 向访问者表示不同的内容，例如电子商务网站中的个性化内容、页面翻译、多种格式等。Koa 的主要优势是它具有与 Express 相同的灵活性，且更加灵活。此外，在开发代码方面它的复杂性较低。

### Socket.io

Socket.io 是一个 JavaScript 库，允许你创建实时应用并实现服务器与 Web 客户端之间的双向通信。这个库框架允许我们创建需要使用 WebSockets 的应用。WhatsApp 是持续运行以进行实时更新的后台进程良好示例。此外，它只需几行代码即可提供实时分析。Patreon、Barolo 和 Beppo 在内的许多公司都在 Socket.io。

### Hapi.js

Hapi 是既开源又可商用的 Web 应用服务器。它以创建 REST API、代理服务器和各种其他桌面应用而闻名。因为 Hapi 极其可靠且安全，它包含了许多插件，所以我们不必担心使用未经许可的中间件。

## 如何选择 Node.js 托管服务？

一旦我们为应用程序开发项目选择了 Node.js，就必须选择一个托管服务。

托管服务是一家管理服务器的公司，并允许人们通过更大的网络（如互联网）开发和分发内容。我们访问过的每个网站都托管在服务器上，而服务器是任何应用程序不可或缺的。

以下是七种不同的 Node.js 托管服务的比较。有些是免费的，有些是收费的，有些则提供基础版和高级服务的混合。由于每个服务的特性略有不同，我们突出了它们的优缺点，以便您为项目选择最的一个。

### 亚马逊云服务

使用 Amazon Web Services (AWS) Elastic Beanstalk 服务，我们可以安装一个高可用的 Node.js Web 应用。这是一个容器技术，允许将捆好的简单应用程序（PaaS）部署到 AWS 上作为平台即服务，且相对简单。我们对运行应用程序的服务器拥有完全的控制权，并且可以在同一台服务器上同时运行多个应用，从而降低了运营成本。

**优点：** 价格合理，在论坛、计划和文档方面提供了大量的帮助。

**缺点：** AWS 的学习曲线非常陡峭，特别是对于从未使用过的人来说是如此，对于那些从未管理过自己服务器的人来说更是如此。

### Google 云计算平台 (Google Cloud Platform)

GCP（Google 云计算平台）是一家专门从事容器支持、分析、大数据、机器学习和 Google Kubernetes Engine 的云公司。由于 Google 是 Docker 和 Kubernetes（一种用于自动化应用部署、扩展和管理的流行技术）的粉丝，因此 GCP 的集成水平是顶尖的。它毕竟是 Google，在分析、统计和机器学习领域也非常擅长。如果项目范围或资金非常有限，还可以访问 GCP 的免费层级。

**优点：** Google Kubernetes Engine 是入门 Kubernetes 的最直接的方法。大数据拥有海量的工具。出色的机器学习解决方案已经就绪并可供使用。

**缺点：** GCP 是该组中最新的。

### Heroku

Heroku 起初仅支持 Ruby on Rails，但现在已扩展到包括各种语言和环境，包括 Node.js。Heroku 允许与多种第三方服务（如 SendGrid 和 Redis）进行简单集成并支持多区域部署。

**优点：** Heroku 拥有免费层级且易用（即使对于新手开发者也是如此）。可以免费访问优秀的支持文档，还有许多可以立即安装的插件和服务选择。

**缺点：** 一旦离开免费层级，Heroku 就会变得昂贵得无法接受。此外，虽然开始使用 Heroku很快，但较大的应用往往需要更长时间来部署。

### Microsoft Azure

Microsoft Azure 是一个云平台，允许开发者快速轻松地创建、安装和管理复杂的网站和 Web 应用程序。这是一个可靠的平台，在不同地理区域具有极高的可用性和灵活性。得益对 Windows 和 Linux 计算机的支持，你可以实时监控托管在 Azure 上的所有 Node.js ，并实现自动扩展。

**优点：** 一项免费服务，允许你在每个数据中心托管多达十个应用。在 Azure 中扩展或缩小你的 Node.js 应用也非常简单，或者只需根据流量激活 Azure 自动缩放。

**缺点：** 部署可能需要很长时间，如果你需要你的 OpenShift 有快速周转，那么这可能不是最佳选择。

### RedHat OpenShift Online

RedHat OpenShift Online 是初级开发者的热门选择，提供永久免费的 Node.js 托管——无需试用，完全免费。无忧的 PaaS 云托管，让我们能够完全专注于增强你的应用。

**优点：** OpenShift Online 是另一个支持自动扩展的平台，因此如果你的应用流量出现意外波动，你将获得保护。可以免费访问内置私有数据库并支持多个区域。

**缺点：** 尽管托管是免费的，但我们限于只有一个项目。

### ZEIT

由 Next.js 的开发者推出的该 JavaScript 框架提供了一个零配置的托管平台。它原生支持单体仓库（monorepos），且部署速度快。它具有竞争力的价格和大量的免费层级。ZEIT 现在可以为你开启 CI/CD（持续集成、持续交付），让我们能够轻松实现无服务器化。现在它是一项由 AWS 和 Microsoft Azure 支持的云服务；对于初学者和专家来说都是极佳的选择。

**优点：** 单页应用 API 的极佳解决方案。它非常简单使用、设置，并可以在几分钟内获取 CI/CD。免费层级提供了巨大的价值。

**缺点：** 目前重点是无状态和静态应用。它们不提供数据库或长期存储选项。我们不得不依赖转向如 MongoDB Atlas、AWS CosmosDB、Google Cloud SQL 或类似的云解决方案。

### DigitalOcean

DigitalOcean 是一个 VPS 提供商，同时也提供几种针对 Node.js 的特定功能和产品。在他们简单的设置过程中，可以使用一键式 Node.js 设置方法，这将在新创建的 droplet 上为我们安装并准备好一切。DigitalOcean Spaces 也是存储文件的绝佳之处。他们还有一个 Kubernetes 集群，可用于更复杂的架构。

**优点：** 成本——虚拟专用服务器的设置通常更便宜。用户界面直观，DigitalOcean 提供了许多一键镜像来帮助我们快速上手。

**缺点：** 它比云提供商需要更高水平的理解和参与。

## V8 JavaScript 引擎

驱动 Google Chrome 的 JavaScript 引擎被称为 V8。它是解析我们的 JavaScript 并在 Chrome 中运行的组件。JavaScript 引擎（也称为 V8）解析并执行 JavaScript 代码。浏览器提供 DOM 和其他 Web平台 API（它们共同创建了运行时环境）。JavaScript 引擎的独特之处在于它不受运行它的浏览器的影响。Node.js 的出现得益于这一关键特性。V8 在 2009 年被选为 Node.js 提供动力，随着 Node.js 的流行，V8 演变成了驱动惊人数量服务端 JavaScript 代码的引擎。得益于 V8（它还通过 Electron 这样的项目驱动桌面应用），Node.js 生态系统是庞大的。

### 其他 JS 框架

其他浏览器有它们自己的 JavaScript 引擎，你可以在这里找到：

- SpiderMonkey 是 Firefox 的一个插件。
- JavaScriptCore 可于 Safari 中（也称为 Nitro）。
- Edge 起初基于 Chakra；但它最近使用 Chromium 和 V8 引擎进行了重构。

还有许多此类引擎。所有这些引擎都支持 ECMA ES-262 标准，通常称为 ECMAScript，这与 JavaScript 的标准相同。

### 追求卓越

V8 用 C++ 编写并定期更新。它是可移植的，可以在 Mac、Windows、Linux 以及其他多种操作系统上运行。在这个 V8 介绍中，我们将忽略 V8 的实现细节，因为可以在更权威的网站上获取它们（例如 V8 官方网站！），而且它们会随时间改变，且经常发生巨大的变化。V8 与其他 JavaScript 引擎一样，不断改进以优化 Web 和 Node.js 环境。多年来，网上一直存在性能竞赛，我们（作为用户和开发者）从中受益匪浅，因为我们年年都都能获得更快、更优化的机器。

## 编译

尽管 JavaScript 通常被认为是一种解释性语言，但现代 JavaScript 引擎不仅仅是解释；它们还进行编译。这从 2009 年 Spider Monkey JavaScript 编译器包含在 Firefox 3.5 中开始就开始演变，并且大家都在效仿。V8 在内部通过即时编译（JIT）编译 JavaScript 以加速执行。这听起来可能违背直觉，但自 2004 年 Google Maps 发布以来，JavaScript 已从一个通常执行几行代码的语言变成了可以在浏览器中运行数万到数十万行代码的程序。我们的应用程序不再仅仅是几个验证规则或简单的脚本，它们现在可以在浏览器中运行数小时。在这个新的世界中，编译 JavaScript 是意义意义，虽然准备 JavaScript 可能需要更长的时间，但一旦完成，其性能将比纯解释性代码高得多。

### 使用命令行运行 Node.js 程序

使用全局可用的`node`命令并传递要运行的文件名是运行 Node.js 程序最流行的方法（假设 Node.js 已安装）。

你可以通过输入以下命令调用你的主 Node.js 应用 app.js：

```
node app.js
```

我们在前面的命令中显式地告诉 shell 运行我们的脚本节点。也可以使用“shebang”行将此信息集成到你的 JavaScript 程序中。“shebang”是文件的开头行，它通知操作系统在运行脚本时使用哪种解释器。JavaScript 的第一行如下：

```
#!/usr/bin/node
```

上面，我们显式地指定了解释器的绝对路径。虽然在每个操作系统的 bin 文件夹中可能都找不到 node，但所有系统都包含 env。我们可以指示 OS 运行带有参数`node`的 env`：

```
#!/usr/bin/env node
```

```
//your code
```

该文件必须具有执行权限才能使用 shebang。通过运行以下命令，我们可以获取 app.js 的执行权限：

```
chmod u+x app.js
```

在运行命令之前，确保我们和 app.js 文件处于同一个目录。

### 自动重启应用程序

当程序发生变化时，必须在 bash 中重新执行 node 命令；为了自动重启应用程序，利用了 nodemon 模块。将 nodemon 模块全局安装到系统路径中。

```
npm i -g nodemon own
```

Nodemon 也可以作为开发依赖安装。

```
npm i --save-dev nodemon own
```

这种本地安装的 nodemon 可以通过在 npm 脚本中使用 npm start 或 npx nodemon 来启动。通过输入 nodemon 后紧跟应用程序文件的名称来运行程序。

```
nodemon app.js
```

### 结束 Node.js 程序的最佳方法是什么？

Node.js 应用有多种终止方式。在终端执行程序时，我们可以通过按下 CTRL+C 来退出，但我们在这里讨论的是通过程序化的终止程序。让我们从最极端的方式开始，并发现为什么我们应该避免使用它。`process.exit()` 是 process 核心模块中的一个有用函数，用于以程序化的方式退出 Node.js 程序。

当 Node.js 执行此代码时，进程会被立即停止。这意味着任何待处理的回调、网络请求、文件系统访问或写入 stdout 或 stderr 的进程将被强制中断。如果这是可以接受的，我们可以向操作系统传递一个表示退出码的整数：

```
process.exit (1);
```

默认退出码为 0，表示操作成功。不同的退出码具有不同的含义，我们希望在自己的系统中用它们与其他程序通信。我们还可以自定义`exitCode`属性：

```
process.exitCode = 1;
```

Node.js 将在程序完成后返回退出码。当所有处理完成后，软件会优雅地退出。我们一直使用 Node.js 启动服务器，比如这个 HTTP 服务器：

```javascript
const express = require('express');

const app = express();

app.get('/', (req, res) => {

  res.send('Hi!');

});

app.listen(3000, () => console.log('Server ready'));
```



这个程序将永远关闭。如果你执行`process.exit()`，当前挂起或运行中的请求将被杀死。这不是一个愉快的情况。

允许运行中的请求在终止前完成是更优。在这种情况下，我们必须向命令发送`SIGTERM`信号，并用进程信号处理器处理它：

```javascript
const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.send('Hi!');
});

const server = app.listen(3000, () => {
  console.log('Server ready');
});

process.on('SIGTERM', () => {
  server.close(() => {
    console.log('Process terminated');
  });
});
```

`SIGKILL`是一个指示进程立即停止工作的信号，它理想情况下行为应该像`process exit()`一样。`SIGTERM`信号指示进程优雅退出。它是由`upstart`、`supervisors`等管理器发送的信号。该信号可以从程序内部的另一个函数发送：

```javascript
process.kill(process.pid, 'SIGTERM');
```

或者，我们可以从另一个运行的`Node.js`程序或系统上任何知道`PID`的软件获取我们想要终止的进程`PID`。

## 基础知识回顾

在当今竞争激烈的世界中，对于企业来说，拥有快速、安全且灵活的`Web`应用开发能力至关重要。对于企业公司，高效的移动性是优先级列表的第一位，其次是决策能力和实时智能。多年来，`Node.js`已证明是一个极好的企业级应用开发平台，满足了所有上述要求。它异常增长的原因之一就在于此。在我们深入研究之前，让我们来看看`Node.js`是什么。

通俗地说，`Node.js`通过在`WebSockets`上使用推送技术在实时在线应用中脱颖而出。但是什么让它如此独特？
它的独特之处在于它将基于无状态`Web`和请求-响应的老标准进行了现代化。当我们使用`Node.js`通过双向连接最终进入实时`Web`应用领域时，此时服务器和客户端都可以通过自由共享数据来发起通信。此前，只有客户端有发起通信的权限，情况就完全不同。

然而，将`Node.js`与其他技术区别开的是……

## 34 征服 JavaScript

（注：第 34 页提供的文本似乎不完整或处于句子中间。）

## 要求

- 需要`HTML`、`CSS`、`JavaScript`、`JQuery`和`Node.js`技能。
- 你的本地电脑上应该安装了`Node.js`。

## 在 NODE.JS 中，你如何制作 WEBSOCKET API？

当你听到“实时 Web 应用”时，脑海中第一个浮现的词是什么？当然是`WebSockets`。通知、消息系统和界面的实时修改只是这种通信方式用处的寥寥例子。只要我们不将其它用于复杂的流程，处理起来就相对简单。
但如果你只想在应用中使用`WebSockets`呢？那完全是另一回事了。

`WebSockets`通常用于通知、聊天和消息传递等功能。在大多数情况下，我们最终会得到一个`WebSocket`网关，向所有或部分已连接的`WebSocket`客户端广播消息。事实上，大部分通信是单向的。消息从`Web`服务器（`WebSocket`服务器）传输到已连接的客户端。这就是`WebSocket`连接，更具体地说，是多个`WebSocket`连接。

那么，如果我们决定使用新的`WebSocket`服务器在发送消息之外传输和接收指令，会发生什么？

## UndeRESTimated (不可估量的 REST)

`REST`架构是使用`undeRESTimated`实现`API`最典型的技术。它是标准化的、易于学习的、为人知的且广泛使用的。你有时甚至会忘记它有多用。如果我告诉你`REST`可以帮助保持你的架构更整洁呢？这听起来像是个谎言，但事实如此。

当你使用`REST`时，每个端点只负责一个操作，该操作由`HTTP`方法和`URL`决定。用户创建由端点`POST/users`处理，而`GET/users`返回用户列表。这难道不直观吗？

大多数`API`框架在实现时都需要拆分每个端点。`Express`是一个极佳的例子。它是最广泛使用的`Node.js API`框架。即使它排除了`MVC`和`ADR`等流行的解决方案，它也鼓励我们编写更整洁的代码。你觉得它是怎么做到的吗？让我们来看看我们拥有的代码。

```javascript
const express = require("express");

const router = express.Router();

const userCreateAction = (req, res, next) => {
  // handle user creation
};

router.post("/users", userCreateAction);
```

上面的示例可能是标准`POST`端点的定义插图。这里重要的是最后部分。每个端点的实现函数都是不同的。在示例中它被称为`userCreateAction`。`REST`在设计上没有一个负责处理所有活动的单一入口。相反，`WebSocket`是一项独特的技术。

### 单点故障（在入口处）

`WebSocket`并没有让创建可扩展且易于维护的应用变得更容易。默认情况下，所有消息都在一个位置处理。

```javascript
class UserService {
  constructor (WebSocket) {
    this.WebSocket = WebSocket
  }

  createUser(userDTO) {
    // create user
    this.WebSocket.to("general").emit(
      // message to be broadcaster
    )
  }
}

io.on("connection", socket => {
  socket.join("general");
  socket.on("disconnect", () => {
    // handle disconnected user
  });
});
```

它只适用于简单的告警或广播服务。但如果我们把指令加入其中会发生什么呢？考虑以下场景：我们希望根据用户消息执行一些操作。

```javascript
io.on("connection", socket) => {
  socket.join("general");
  socket.on("message", message => {
    if (message.type === "CREATE_USER") {
      // create user logic
    } else if (message.type === "GET_USER") {
      // retrieve user logic
    }

    if (message.type === "DELETE_USER") {
      // delete user logic
    }
  });

  socket.on("disconnect", () => {
    // handle disconnected user
  });
}
```

如果不处理得当，代码将变得杂乱。即使你将业务逻辑转移到服务中，那些`if`语句仍然会存在。那么，解决它的方案有哪些？

作为契约的消息：我们应该做的第一件事是修改消息的结构。我们可以将其视为契约，而不是发送随机数据。这是`RPC`通信协议的常见特性，我们不仅可以描述输入数据，还可以描述我们想要的操作。以下是一个结构良好的消息示例：

```json
{
  "type": "create-new-game",
  "payload": {
    "username": "SomeUsername"
  }
}
```

每个操作应该分配一个单一处理器。例如，如果我们想创建一个新游戏，我们需要发送一条带有`create-new-game`操作类型的消息，并为它构建一个处理器。

```javascript
class CreateNewGameHandler {
  constructor(games) {
    this.games = games;
  }

  handle(message) {
    // handler implementation
  }
}

CreateNewGameHandler.TYPE = "create-new-game";
module.exports = CreateNewGameHandler;
```

下一步是让你的`WebSocket`消息处理器代码摆脱`if`语句的疯狂。我们可以简单地使用“契约-处理器”对从条件判断切换到`Set`。

```javascript
const CreateNewGameHandler = require("./engine/create-new-game");

const handlers = {
  [CreateNewGameHandler.TYPE]: new CreateNewGameHandler(games)
};
```

在对象中，操作是键，其处理器是值。当然，可以使用`RxJS`的`Subject`来实现这一点。

```javascript
class Handlers {
  constructor(handlers) {
    this.handlers = handlers;
  }

  handle(message) {
    if (!this.handlers[message.type]) {
      throw new Error('No handler for ' + message.type);
    }

    this.handlers[message.type].handle(message);
  }
}

module.exports = Handlers;
```

不要让你的处理器特定于`WebSocket`，要保持它们的独立性。你如何管理连接的客户端？将注入到处理器中的事件（`Events`）引入进来是有益的。

```javascript
const Handlers = require("./handlers");
const CreateNewGameHandler = require("./engine/create-new-game");
const LeaveGameHandler = require("./engine/leave-game");

const handlers = {
  [CreateNewGameHandler.TYPE]: new CreateNewGameHandler(games),
  [LeaveGameHandler.TYPE]: new LeaveGameHandler(games)
};

io.on("connection", socket => {
  socket.on("message", message => {
    handlers.handle({
      ...message,
      socketID: socket.id
    });
  });

  socket.on("disconnect", () => {
    handlers.handle({
      type: LeaveGameHandler.TYPE,
      socketID: socket.id
    });
  });
});
```

然后，直接从我们的处理器中，你可以发布任意数量的事件。

```javascript
class CreateNewGameHandler {
  constructor(games, eventBus) {
    this.games = games;
    this.eventBus = eventBus;
  }

  handle(message) {
    const game = this.games.createNewGame(message,
    payload.username);

    this.eventBus.next({
      type: "game-created",
      targets: game.players().map(player => player.id),
      payload: {
        gameId: game.id
      }
    });
  }
}
```

订阅者应该监听这些事件，并在提供给客户端之前转换为`WebSocket`消息。

```javascript
const { Subject } = require("rxjs");

const eventBus = new Subject();

eventBus.subscribe(message => {
  message.targets.forEach(id => {
    io.to(id).emit("message", {
      type: message.type,
      payload: message.payload
    });
  });
});
```

### HTTP 与 WebSockets

这是在说没有`WebSocket`创建聊天应用是不可能的吗？`HTTP`长轮询是一种有帮助的策略。客户端提交查询，服务器保持开启状态直到有新数据。一旦数据出现并被客户端接收，就会发出新的请求，并反复执行。然而，`HTTP`长轮询有一个巨大的缺点，就是会消耗大量的服务器资源。

## Socket.io 教程构建聊天室应用

在下面的`Socket.io`教程中，我们将如何使用原生`JS`前端和`Node.js`服务器制作一个简单的聊天应用。

## 44 征服 JavaScript

## 代码教程

你必须首先使用默认的`package.json`文件来建立项目。现在让我们来谈谈项目中使用的模块。

- 根据`expressjs.com`的介绍，`Express`是一个用于`node`的快速、无见解且简单的`Web`框架。
- `Nodemon`是一个实用程序，通过在检测到目录中的文件更改时自动重启，来辅助基于`node.js`的应用开发。
- `Babel` – `Babel`是一个工具链，可以将`ECMAScript 2015+`代码转换为现代和旧版浏览器及环境中向后兼容的`JavaScript`版本。
- `Socket.IO`提供实时的基于事件的双向通信。

## SOCKET.IO 不是什么？

`Socket.IO`是一个`WebSocket`的实现，但它不等同于`WebSocket`实现。尽管`Socket.IO`在尽可能使用`WebSocket`作为传输层，但每个数据包都包含额外的元数据。因此，`WebSocket`客户端将无法连接到`Socket.IO`服务器，而`Socket.IO`客户端也无法连接到普通的`WebSocket`服务器。

完成这一步后，我们需要设置服务器并安装所有所需的依赖。我们需要构建一个`index.js`文件并安装`socket.io`和`express`来开始。可以使用以下命令：`npm install express socket.io`和`npm install --save-dev nodemon`以及`touch index`，我们将在`index.js`中设置本地服务器和简单的`socket`连接。目前，这就是我们在后端需要做的所有工作。一旦你提交了合适的请求，连接就会建立。通过日志记录的消息可以显而易见（如下所示）。

```javascript
const express = require("express");
const socket = require("socket.io");

// App setup
const PORT = 5000;
const app = express();
```

```javascript
const server = app.listen(PORT, function () {
  console.log(`Listening on port ${PORT}`);
  console.log(`http://localhost:${PORT}`);
});

// Static files
app.use(express.static("public"));

// Socket setup
const io = socket(server);

io.on('connection', function (socket) {
  console.log("Made socket connection");
});
```

### 你现在必须准备前端

让我们从创建`public`文件夹以及`index.html`和`main.js`文件开始。我们还可以包含`style.css`。`index.html`的骨架如下所示。我们只需要一些可以引用的`HTML`标签，以及项目项目包含的`Socket.io`脚本。在包含了`WebSocket`脚本后，`index.html`文件应该如下所示。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1.0" />
  <title>Socket.io 简单聊天</title>
  <link rel="stylesheet" href="./style.css" />
</head>
<body>
```



<div class="container">

  <div class="inbox">

    <div class="inbox __people">

      <h4>活跃用户</h4>

    </div>

    <div class="inbox __messages">

      <div class="messages __history"></div>

      <div class="fallback"></div>

    </div>

  </div>

</div>

```html
<form class="message_form">

  <input type="text" class="message_form__input" placeholder="输入消息" />

  <button class="message_form__button" type="submit">

    发送

  </button>

</form>

<div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/socket.io/2.3.0/socket.io.js"></script>

  <script src="main.js"></script>

</div>

</body>

</html>
```

然后，在前端，你必须建立连接。在`main`中，我们只需要在`js`中写一行代码：`const socket = io();`

正如我们所见，在访问页面并加载`socket`后，连接就会建立。下一步是处理新用户连接（包括用户本身）、新消息，以及最重要的——正在打字的用户。

在`socket`中传输数据（如事件）有两种方式。一种方法是用户向所有人（包括用户自己）发送事件，另一种是用户向所有其他实例发送事件。其概念是显示所有活跃用户的列表。因此，当用户连接时，他们必须通知其他人并更新当前用户列表。

```javascript
const activeUsers = new Set();

io.on("connection", function (socket) {

  console.log("Made socket connection");

  socket.on("new user", function (data) {

    socket.userId = data;

    activeUsers.add(data);

    io.emit("new user", [...activeUsers]);

  });

  socket.on("disconnect", () => {

    activeUsers.delete(socket.userId);

    io.emit("user disconnected", socket.userId);

  });

});
```

当用户连接时，他们会发送一个包含其用户名信息的事件。在`socket`上，你应该设置`userId`属性。当用户断开时，我们从列表中移除他们。

```javascript
const socket = io();

const inboxPeople = document.querySelector(".inbox__people");

let userName = "";

const newUserConnected = (user) => {

  const time = new Date();

  const formattedTime = time.toLocaleString("en-US", { hour: "numeric", minute: "numeric" });

  inboxPeople.innerHTML += `<div class="user">${user} <span class="time">${formattedTime}</span></div>`;

};

socket.on("new user", (data) => {

  newUserConnected(data);

});

socket.on("user disconnected", (user) => {

  // 从 UI 中移除用户

});
```

## 48 征服 JavaScript

显示新消息的函数在接收到`socket`数据后立即调用。在表单提交的监听器中，消息被发送到服务器。

```javascript
const inputField = document.querySelector(".message_form input");

const messageForm = document.querySelector(".message_form");

const messageBox = document.querySelector(".messages__history");

const addNewMessage = ({ user, message }) => {

  const time = new Date();

  const formattedTime = time.toLocaleString("en-US", { hour: "numeric", minute: "numeric" });

  const receivedMsg = `

<div class="incoming_message">

  <div class="received_message">

    <p>${message}</p>

    <div class="message_info">

      <span class="message_author">${user}</span>

      <span class="time_date">${formattedTime}</span>

    </div>

  </div>

</div>`;

  const myMsg = `

<div class="outgoing_message">

  <div class="sent_message">

    <p>${message}</p>

    <div class="message_info">

      <span class="message_author">${user}</span>

      <span class="time_date">${formattedTime}</span>

    </div>

  </div>

</div>`;

  messageBox.innerHTML += user === userName ? myMsg : receivedMsg;

};
```

## 应用开发 | 49

```javascript
// ... (之前的逻辑)
```

等等，实现方式：

```javascript
messageForm.addEventListener("submit", (e) => {

  e.preventDefault();

  if (!inputField.value) {

    return;

  }

  socket.emit("chat message", {

    message: inputField.value,

    nick: userName,

  });

  inputField.value = "";

});

socket.on("chat message", function (data) {

  addNewMessage({ user: data.nick, message: data.message });

});
```

## 50 征服 JavaScript

```javascript
const server = app.listen(PORT, function () {

  console.log('Listening on port ${PORT}');

  console.log('http://localhost:${PORT}');

});

// Static files

app.use(express.static("public"));
```

```javascript
// Socket setup

const io = socket(server);

const activeUsers = new Set();

io.on("connection", function (socket) {

  console.log("Made socket connection");

  socket.on("new user", function (data) {

    socket.userId = data;

    activeUsers.add(data);

    io.emit("new user", [...activeUsers]);

  });

  socket.on("disconnect", () => {

    activeUsers.delete(socket.userId);

    io.emit("user disconnected", socket.userId);

  });

});

socket.on("chat message", function (data) {

  io.emit("chat message", data);

});

socket.on("typing", function (data) {

  socket.broadcast.emit("typing", data);

});
```

在客户端，应该检查`inputField`的按键监听器以及`typing`的`socket`监听器。这两项以及`main.js`的最终版本见下方。

```javascript
const socket = io();

const inboxPeople = document.querySelector(".inbox__people");

const inputField = document.querySelector(".message_form__input");

const messageForm = document.querySelector(".message_form");

const message = document.querySelector(".messages__history");

const fallback = document.querySelector(".fallback");

let userName = ""

const newUserConnected = (user) => {

  userName = user || `${Math.floor(Math.random() * 1000000)}`;

  socket.emit("new user", userName);

  addToUsersBox(userName);

};

const addToUsersBox = (userName) => {

  if (!document.querySelector(`.${userName}-userlist`)) {

    return;

  }

  const userBox = `<div class="chat_ib ${userName}-userlist">

<h5>${userName}</h5>

</div>`;

  inboxPeople.innerHTML += userBox;

};

const addNewMessage = ({ user, message }) => {

  const time = new Date();

  const formattedTime = time.toLocaleString("en-US", {

    hour: "numeric", minute: "numeric"

  });

  const receivedMsg = `

<div class="incoming__message">

<div class="received__message">

<p>${message}</p>

<div class="message__info">

<span class="message__author">${user}</span>

<span class="time_date">${formattedTime}</span>

</div>

</div>

</div>`;

  const myMsg = `

<div class="outgoing__message">

<div class="sent__message">

  <p>${message}</p>

  <div class="message__info">

    <span class="time_date">${formattedTime}</span>

  </div>

</div></div>`;

  messageBox.innerHTML += user === userName ? myMsg : receivedMsg;

};

// 创建新用户，因此我们生成 nickname事件

newUserConnected();

messageForm.addEventListener("submit", (e) => {

  e.preventDefault();

  if (!inputField.value) {

    return;

  }

  socket.emit("chat message", {

    message: inputField.value,

    nick: userName,

  });

  inputField.value = "";

});

inputField.addEventListener("keyup", () => {

  socket.emit("typing", {

    isTyping: inputField.value.length > 0,

    nick: userName,

  });

});

socket.on("new user", function (data) {

  data.map((user) => addUserToBox(user));

});

socket.on("user disconnected", function (userName) {

  document.querySelector(`.${userName}-userlist`).remove();

});

socket.on("chat message", function (data) {

  addNewMessage({ user: data.nick, message: data.message });

});

socket.on("typing", function (data) {

  const { isTyping, nick } = data;

  if (!isTyping) {

    fallback.innerHTML = "";

    return;

  }

  fallback.innerHTML = '<p>${nick} is typing...</p>';

});
```




## 总结

正如我们所见，使用 `Socket.io` 创建具有基础聊天消息功能的聊天应用（或任何其他 Web 应用）并不困难。我们希望你发现使用 `JavaScript` 可以做很多许多有趣的事情，而这节简短的 `Socket.io` 课程演示了使用这种策略有多简单。只要对 `Node.js` 有一点了解，上述描述的所有代码片段、提示和技巧都应该是浅俗易懂的。正如我们所看到的，对方法进行一些简单的调整可以使 `WebSocket` 代码更具灵活性和可维护性。

![](img/0910e964adc1d4e011635b07233a41cb_74_0.png)

# 应用开发 II

本章内容：

- 流媒体应用
- 使用 `Node.js` 构建应用
- 关键词与语法

在上一章中，我们学习了如何使用 `Socket.io` 开发基于聊的应用程序。在本章中，我们将研究另一种基于视频流媒体的应用开发。在进入代码部分之前，我们必须稍微了解流媒体应用及其基本要求。

在创建流媒体应用时，必须考虑几个因素，包括功能、所需的技术栈和成本分析。考虑到所有因素并为您的客户提供更好的用户体验，需要仔细的规划、执行、产品测试、监控和性能维护等。以下是创建流媒体应用的分步指南。

`Disney` 在 2019 年发布了它的越顶传输（`OTT`）服务，截至 2021 年 7 月，该公司已拥有 116 万用户。

## 56 征服 JavaScript

`OTT` 平台拥有了如 `Netflix`、`YouTube`、`Amazon Prime`、`HBO Max` 等巨头的 7100 万用户。

## 第一步：进行市场研究

创建流媒体应用的第一步是识别流媒体生态系统。因此，需要进行市场研究以理解流媒体应用及其功能。

`VOD` 有两种类型：基于电视流的 `VOD`，而 `OTT` 是基于互联网的。`OTT` 有三大大类：

- 订阅制的视频点播
- 交易制的视频点播
- 广告支持的视频点播

`OTT` 和 `VOD` 应用为用户提供了更多选择，而以前局限于电影院。

## 音乐流媒体应用

在线音乐流媒体应用经历了巨大的增长，成为线下销售之外音乐行业的主要贡献者。虽然流媒体应用提供订阅制服务，但其他提供付费内容。

# 电竞流媒体应用

像 `Twitch` 这样的电竞流媒体非常受欢迎。它是一个流媒体服务，你可以流传输社区上传的内容。其中一些应用程序支持聊天室和实时比分。

理解痛点并根据解决方案构建流媒体应用需要考虑用例。

## 第二步：识别特征

为了提供服务和内容访问，流媒体应用需要特定的功能。如果应用允许免费模式（例如，某些内容免费但用户必须为其他内容付费），则高级访问功能是必要的。因此，根据用例，我们需要为构建流媒体平台选择一些关键元素。

## 基本特征

登录、配置管理、管理面板和其他流媒体应用的基础。虽然开发简单的功能看起来并不困难，但我们必须考虑用户访问、个性化和用户体验等因素。

例如，如果流媒体服务具有社交媒体 `API` 连接和双重验证等安全功能。身份验证系统可以通过向设备发送密码或一次性密码来增加额外的用户验证层。同样地，个性化功能允许用户添加多个账户配置以进行配置管理。用户还可以指定他们的位置，以便根据本地流媒体市场进行定制。理解不同的服务集成（例如用于用户位置更新的地图服务集成）需要识别此类功能。

或者在正在进行电竞直播活动时，这取决于具体的用场景。

以 `YouTube` 为例，其整个应用模型都是基于用户生成的内容，使得视频上传选项变得不可或缺。除了支持该功能的服务（如视频格式选项），添加描述、视频缩略图、音频和元数据（标题和标签）也是需要考虑的一些重要因素。

## 可选额外功能

根据用场景，流媒体应用程序还需要许多复杂的功能。例如，高级搜索工具允许您的客户在程序中定位到他们喜爱的标题和节目。除了高级搜索选项外，还有其他功能：

- 提供了多种支付方式：为客户提供多样化的支付方式可以让他们更轻松地订阅您的流媒体服务或在线购买特定内容。我们甚至可以接受加密货币作为支付方式，因为数字货币目前已被许多国家接受。

- 多语言支持是面向全球消费者的流媒体应用的必备功能。例如，`Netflix` 为其网站上的标题提供不同语言的音频。

- 应用内聊天：通过启用应用内聊天，用户将能够与平台上的其他用户联系，并分享对各种类型内容的体验。

- 主播可以在自己的频道上主持或直播流，供其他用户消费内容。主播可以在 `Twitch` 和 `YouTube` 等应用上为其他用户进行直播。

- 私有直播是一项允许广播者将其视频私密地广播给单个用户、一组用户或特定区域的功能。`Discord` 是提供这种私有直播选项的软件之一。

## 第 3 步：技术栈完成

需要考虑每个应用程序技术栈的各个部分。技术栈有许多不同方面需要考虑，从开发框架到部署平台不等。然而，如果我们正在寻找一种可靠的视频流媒体软件，我们不必别处寻找。

- 数据传输的比特率控制或编码
- 部署平台
- 存储或数据库
- 用于改进各种功能的集成

现在让我们来探索流媒体应用的一些技术细节。

## 在线视频流协议

流传输是在数据下载或加载之前将其传输到您的设备的过程。这减少了内存占用，并允许您在不中断的情况下流访问数据。执行此类流的标准被称为流媒体协议。

## MPEG-DASH

`MPEG-DASH` 是一种流媒体协议，全称为“基于 `HTTP` 的动态自适应流媒体”。它将视频内容划分成小块，并根据网络强度调整质量以实现不中断的流传输。视频流将由数据库或源服务器划分为许多几秒钟的部分。此外，服务器会对这些段进行索引并编码，以便不同的设备使用不同的编码标准进行流传输。

## HLS

`HLS` 或 `HTTP` 实时直播，是一种与 `MPEG-DASH` 类似的流媒体协议。它将视频转换为可下载的 `HTTP` 文件，并使用 `HTTP` 协议将其发送到用户的设备。这些设备能够以播放视频的方式播放 `HTTP` 文件。因此，它可以在任何连接互联网的设备上运行，`HLS` 是开发流媒体应用的极佳选择。

## RTMP

对于视频直播，采用了 `RTMP`（实时消息传输协议）。例如，大多数音乐会的高清直播都使用 `RTMP` 协议。然而，流源和用户设备之间存在 10~20 秒的延迟。同时使用 `RTMP` 和 `HLS` 协议是流媒体应用减少延迟的最有效方法之一。`RTMP` 协议提供高清直播支持，而 `HLS` 使用自适应比特率流传输来减少延迟。

## WebRTC

`WebRTC` 是一种使用流媒体协议的实时通信协议。对于数据馈送流传输，它作为插件工作，不需要原生应用程序。`WebRTC` 通过允许音频/视频流实时传输来实现点对点通信。`WebRTC` 用于 `Google Meet`、`Zoom` 以及其他类似应用的视频会议。

## 流媒体平台

这些是允许内容进行流传输的平台。例如，基于云的解决方案是更改比特率（`VBR`）的视频流媒体应用的理想选择。为了适应复杂的视频部分，它会修改数据传输率。因此，它会在复杂段处获取更多数据，而如果数据传输需求较少，编码器将降低速率进行优化。我们可以通过自定义处理函数利用云服务开发触发函数。通过此类触发器，可以实现流媒体应用中改进视频质量比特率控制。

构建流媒体应用的若干云平台。

相应地，我们需要选择要在流媒体应用使用的分发基础设施。例如，如果我们真的想在 `Google Play Store` 上发布您的应用，我们需要一个与 `Android` 兼容的原生流平台。也要考虑 `iOS`、桌面操作系统和其他平台。

## 内容分发网络

诸如 `HLS` 或 `MPEG-DASH` 等流媒体协议将视频切成小块，并通过内容分发网络（`CDN`）传递到设备。它指的是一个全球分布的网络。以下是选择正确 `CDN` 的一些优势：

- `CDN` 使用全球分布的服务器来减轻单个服务器的压力。
- 它允许收集用户统计数据，如需求和消费模式。
- 然而，流源和用户设备之间存在 20–30 秒的延迟。

流媒体应用的最佳 `CDN` 是：

- `Amazon Cloudfront` 是一个全功能云平台，在 42 个国家拥有 216 个接入节点。
- `Limelight Networks` 在 70 个国家拥有 130 个接入节点，是主要的 `CDN` 供应商之一。
- `Microsoft Azure` 在 65 个国家拥有近 129 个接入节点，提供带有存储功能的全功能云平台。
- `KeyCDN` 在 23 个国家拥有 34 个接入节点，支持 `HLS` 协议。
- `Akamai` 在 30 个国家拥有 60 个接入节点，支持 `HLS`、`HDS` 和 `DASH` 协议。

应用开发 II ■ 63

- 空间启发式：利用 `UI` 空间中的各种元素可能会大有益；例如，你可以引入负空间来获得更沉浸式的体验。

- 我们可以通过考虑流媒体应用内容的可访问性，构建出最佳体验的 `UI`。

# 第 5 步：测试与维护

流媒体应用测试是我们开发策略中的重要方面，因为它确保了我们的 `UI`、后端服务器、`API` 集成和其他组件能够良好运行。使用 `Selenium` 和 `Appium` 等自动化技术将将帮助我们缩短运行各种测试的时间，允许我们的公司精调应用性能。

我们需要为流媒体应用运行以下几种类型的测试：

- `UX` 测试用于保证用户体验在所有设备上保持一致性。一致性、导航和功能性都将在跨平台进行测试。

- 负载测试模拟系统的峰值需求，以检查你的应用程序是否能够处理增加的负载。当数百万用户从多个地方从你的应用程序中消费内容时，负载测试变得至关重要。

- 性能测试检查服务器响应用户内容请求时的可靠性、稳定性和性能，无论带宽或平台如何。此类测试将允许我们确保无故障的流媒体服务并提高应用性能。

- 检查语言清晰度、内容的文化恰当性、个性化以及针对本地客户支付的准确货币格式都是本地化测试的一部分。这是一项关键检查，以确保内容本地化符合用户的选择。

保持最佳性能需要跟踪许多 `KPI` 并精调应用程序的功能。另一方面，维护需要理解程序的堆栈和架构设计，以便实现应用功能。

# 64 涉及 JavaScript

## 创建一个流媒体应用程序的成本是多少？

在计算制作流媒体应用程序的成本时，必须考虑几个因素。它取决于功能的复杂性、开发者的参与模式以及其他各种方面。了解成本有助于制定出产生最佳结果的稳健开发策略。

## 取决于功能的成本

在决定如何开发流媒体应用时，功能性极关重要。例如，如果我们正在创建一个 `SVOD`（按需付费的视频点播）`OTT`（过顶传输流媒体电视）应用，我们需要为各种不同人口统计学特征的消费者提供多种功能。多种视频分辨率选项（如 `4K` 或 `1080P`）以及多语言音频调整可能需要很长时间的开发。基础功能（如用户登录和个人资料管理）的设计时间较短，因为它们不那么复杂。问题是，我们如何确定精确的成本？答案是开发时间。然而，它取决于应用程序的类型、规模和特征。建立流媒体应用程序的成本不仅基于基于成本，还包括市场研究、构思、测试和维护等成本。

## 使用 NODE.JS 进行应用开发

如果我们打算创建一个具有许多连接同时运行的流媒体 `Web` 应用程序，`Node` 的才华无疑对我们有益。在 `Web` 应用程序中播放视频时，`Node.js` 是理想的选择，因为它将数据分割成片段并快速播放大型视频。

## 视频游戏的流

数据分段发送到客户端而不是一次性发送，这就是流（`Streams`）的特性。在 `Node.js` 中，有的流以难于处理、甚至更难以理解而闻名。`Dominic Tarr` 认为“流是 `Node` 最大且最被低估的概念”。即使是 `Redux` 的创建者、`Reactjs` 核心团队成员 `Dan Abramov` 也对 `Node` 的流感到恐畏。

应用开发 II ■ 65

### 到底是什么流？

流是构建 `Node.js` 应用程序的核心原理之一。它们是一种处理数据的方法，按顺序读取输入并写入输出。流是一种高效处理读取/写入文件、网络对话或任何端到端数据流的技术。流的特点是，它们不是像传统方法那样一次性将文件读入内存，而是逐段读取数据块，在处理其内容而不将其完全存储在内存中。这使得流在处理海量数据时极其有用。例如，文件的大小可能会超过你分配的内存空间，如果不将完整文件读入内存，将很难处理。在这种情况下，流来救场。使用流处理较小的数据位来读取更大的文件是可行的。以 `YouTube` 或 `Netflix` 这样的“流式”服务为例：这些服务不需要你下载所有的视频和音频流。相反，浏览器以连续块流的形式接收电影，允许接收者几乎立即开始观看和收听。

另一方面，流不仅用于处理视频或海量数据。它们还提供了编写“可组合”（`composable`）代码的机会。当我们考虑可组合性进行设计时，我们是在确保多个组件可以以特定方式组合以获得相同的结果。在 `Node.js` 中使用流，你可以通过在较小的代码段之间管道（`pipe`）数据来创建强大的代码块。

为什么使用流而不是其他数据处理方法？流相比其他数据处理方法具有两个显著优势：

- 内存效率：意味着我们在处理数据之前不需要将大量数据加载到内存中。

- 时间效率：一旦收到数据，立即开始处理所需的时间比等待完整载荷传输要少得多。

在 `Node` 中，有四种不同的 `streams.js` 类型：

- 可写（`Writable`）：数据可以写入流。例如，`fs.createWriteStream()` 允许我们使用流将数据写入文件。

## 66 涉及 JavaScript

- 可读（`Readable`）：可以读取的数据流。例如，`fs.createReadStream()` 允许我们读取文件内容。

- 双工流（`Duplex streams`）可以在两个方向上进行读取和的流。以互联网为例。

- 能够修改或转换数据的流被称为套接转换（`socket transforms`）。在文件压缩的情况下，我们可以将压缩数据写入文件并从文件中接收压缩数据。

如果我们以前处理过 `Node.js`，可能遇到过流。例如，在基于 `Node.js` 的 `HTTP` 服务器中，请求是一个读取流，响应是一个可写流。可能使用了 `fs` 模块，它允许你与可读和可写的文件流进行交互。当你使用 `Express` 与客户端接口时，都会使用流，因为 `TCP` 套接字、`TLS` 栈和其他连接都是构建在 `Node.js` 流上的。在我们处理的每个数据库连接驱动程序中也会流。

## 现实示例

创建可读流的最有效方法是什么？我们首先创建并初始化可读流。

```javascript
const Stream = require('stream')

const readableStream = new Stream.Readable()
```

初始化后，我们可以向流传输数据：

```javascript
readableStream.push('ping!')

readableStream.push('pong!')
```

# 异步方式迭代器

在处理流时，强烈建议使用异步迭代器。根据 `Axel Rauschmayer` 博士的说法，异步迭代是一种异步获取数据容器内容的机制（这意味着在获取项目之前，当前“任务”可能会被中断）。值得注意的是，在流内部使用了 `readable` 事件迭代器实现。从可读流（`readable streams`）读取数据时，我们可以使用异步迭代器：

```javascript
import * as fs from 'fs';

async function logChunks(readable) {

  for await (const chunk of readable) {

    console.log(chunk);

  }

}

const readable = fs.createReadStream(

  'tmp/test.txt', {encoding: 'utf8'});

logChunks(readable);

// 输出:

// This is a test!\n
```

同样，可以使用字符串来捕获可读流的内容：

```javascript
import {Readable} from 'stream';

async function readableToString2(readable) {

  let result = '';

  for await (const chunk of readable) {

    result += chunk;

  }

  return result;

}

const readable = Readable.from('Good noon !',

{encoding: 'utf8'});

asassert.deepEqual(await readableToString2(readable),

'Good morning!');
```

由于我们打算返回一个 `Promise`，因此在这种情况下我们必须使用异步函数。至关重要的是不要在 `EventEmitter` 中使用异步方法，目前还没有机制可以检测在事件处理器内部抛出的拒绝（`rejection`），会导致难以追踪的问题和内存泄漏。目前的最佳实践是将异步函数的内容封装在 `try/catch` 块中并以此方式处理问题，尽管这很容易出错。一旦进入 `Node` 核心，该 `pull` 请求将修复此问题。

## 使用 Readable Stream() 从迭代对象创建可读流

# 68 ■ 征服 JavaScript

`Readable.from(iterable, [options])` 是一个便利函数，用于从包含数据的可迭代对象的迭代器构建可读流。迭代对象有两种类型：同步和异步。`options` 参数是可选的，可以用于指定文本编码等其他内容。

```javascript
const { Readable } = require('stream');

async function * generate() {

  yield 'hello';

  yield 'streams';

}

const readable = Readable.from(generate());

readable.on('data', (chunk) => {

  console.log(chunk);

});
```




## 读取模式

有两种读取模式可用。根据 Streams API，读取流可以处于两种状态之一：流动（flowing）或暂停（halted）。无论处于流动模式还是暂停模式，可读流都可以处于对象模式（object mode）或模式。

- 在流动模式下，数据会自动从底层系统读取，并通过 `Emitter` 接口使用事件尽可能快地传递给应用程序。
- 在暂停模式下，必须直接使用 `stream.read()` 方法从流中读取数据块。

要从流动模式的流中读取数据，我们可以监听 `data` 事件并附加一个回调函数。当数据块可用时，可读流会广播 `data` 事件，您的回调就会执行。请看这里。

```javascript
var fs = require("fs");

var data = '';

var readerStream = fs.createReadStream('file.txt'); // 创建一个可读流

readerStream.setEncoding('UTF8'); // 设置编码为 utf8。

// 处理流事件 --> data, end, and error
```

```javascript
readerStream.on('data', function(chunk) {
  data += chunk;
})

readerStream.on('end', function() {
  console.log(data);
});

readerStream.on('error', function(err) {
  console.log(err.stack);
});

console.log("Program Ended");
```

`fs.createReadStream` 函数创建了一个可读流。流最初处于静态状态。一旦我们监听 `data` 事件并附加回调函数，它就开始流动。随后，数据块被读取并传递给回调函数。`data` 事件的发射频率由流的实现者决定的。例如，在 HTTP 请求中，我们每读取几 KB 数据可能会产生一个 `data` 事件。在从文件读取数据时，我们可能会在读取一行后广播一次 `data` 事件。当没有更多数据可读时（end），流会产生 `end` 事件。我们在片段中监听此事件，以便在它发生时收到通知。当没有更多数据可读时（end），流会产生 `end` 事件。我们在上面的代码中监听此事件，以便在结束时收到通知。

此外，如果发生错误，流将发射并警告用户。

在暂停模式下，必须不断对流调用 `read()`，直到所有数据都被读取，如下例所示：

```javascript
var fs = require('fs');
var readableStream = fs.createReadStream('file.txt');
var data = '';
var chunk;

readableStream.on('readable', function() {
  while ((chunk=readableStream.read()) != null) {
    data += chunk;
  }
});

readableStream.on('end', function() {
  console.log(data);
});
```

## 70 征服 JavaScript

`read()` 函数返回从内部缓冲区中读取的数据。如果没有数据，则返回 `null`。可读流最初处于静态状态。一旦我们监听 `data` 事件并附加回调函数，它就开始流动。随后，数据块被读取并传递给回调函数。`data` 事件的发射频率由流的实现者决定。例如，在 HTTP 请求中，我们每读取几 KB 数据可能会产生一个 `data` 事件。在从文件读取数据时，我们可能会在读取一行后广播一次 `data` 事件。当没有更多数据可读时（end），流会产生 `end` 事件。我们在上面的代码中监听此事件，以便在结束时收到通知。

在暂停模式下，可以指定到流动模式。可读流可以通过以下几种方式转换为流动模式：
- 将异步函数的内容封装在 `try/catch` 块中并以此方式处理问题，尽管这很容易出错。一旦进入 Node 核心，该 pull 请求将修复此问题。

`read()` 函数返回从内部缓冲区中读取的数据。如果没有数据，则返回 `null`。可读流最初处于静态状态。一旦我们监听 `data` 事件并附加回调函数，它就开始流动。随后，数据块被读取并传递给回调函数。`data` 事件的发射频率由流的实现者决定。例如，在 HTTP 请求中，我们每读取几 KB 数据可能会产生一个 `data` 事件。在从文件读取数据时，我们可能会在读取一行后广播一次 `data` 事件。当没有更多数据可读时（end），流会产生 `end` 事件。我们在上面的代码中监听此事件，以便在结束时收到通知。

此外，如果发生错误，流将发射并警告用户。

在暂停模式下，必须不断对流调用 `read()`，直到所有数据都被读取，如下例所示：

```javascript
var fs = require('fs');
var readableStream = fs.createReadStream('file.txt');
var data = '';
var chunk;

readableStream.on('readable', function() {
  while ((chunk=readableStream.read()) != null) {
    data += chunk;
  }
});

readableStream.on('end', function() {
  console.log(data);
});
```

- 将 `data` 传递到流动模式。可读流可以通过以下几种方式转换为流动模式：
- 将 `data` 传递到写入流。

作为一个示例，请考虑以下内容：

```javascript
var fs = require('fs');
var readableStream = fs.createReadStream('file.txt');
var writableStream = fs.createWriteStream('file.txt');

readableStream.setEncoding('utf8');

readableStream.on('data', function (chunk) {
  writableStream.write(chunk);
});
```

# 应用开发 II ■71

上面的代码是简单的。它只是从输入读取并发布到目标。如果指定了回调，将作为 `finish` 事件的监听器。当我们调用 `writable.end()` 时，我们是在告诉写入流不再有数据了。通过广播 `drain` 事件，写入流会在管道完成后通知我们。

管道（Piping）是一种允许我们将一个流的输出供给另一个流的方法。它通常用于从一个流获取数据并将其输出传递给另一个流。管道操作的数量是不限制的。换句话说，管道是一种分阶段处理流数据的技术。

```javascript
// 现在不允许写入更多！
```

我们也可以使用迭代器写入写入流，这是被推荐的。

```javascript
import * as util from 'util';
import * as stream from 'stream';
import * as fs from 'fs';
import {once} from 'events';
```

# 72 征服 JavaScript

```javascript
const finished = util.promisify(stream.finished); // (A)

async function writeIterableToFile(iterable, filePath) {
  const writable = fs.createWriteStream(filePath, {encoding: 'utf8'});

  for (const chunk of iterable) {
    if (!writable.write(chunk)) { // (B)
      // 处理背压
      await writable.once('drain');
    }
  }
  writable.end(); // (C)
  // 等待完成。如果出错则抛出异常。
  await finished(writable);
}

await writeIterableToFile(['One', ' line of text.\n'], 'tmp/log.txt');
assert.equal(fs.readFileSync('tmp/log.txt', {encoding: 'utf8'}),
  'One line of text.\n');
```

## 管道 (Pipeline)

`stream.pipeline` 在 Node 10.x 中引入 ()。这是一个用于跨流进行管道、传输失败、正确清理并在管道完成后提供回调的模块。

使用 `pipeline` API 可以简单地连接一系列流，并在管道完成后获得通知。

一个高效 gzip 潜在大视频文件的管道：

```javascript
const { pipeline } = require('stream');
const fs = require('fs');
const Zlib = require('zlib');
```

```javascript
pipeline(
  fs.createReadStream('The.Matrix.780p.mkv'),
  zlib.createGzip(),
  fs.createWriteStream('The.Matrix.780p.mkv.gz'),
  (err) => {
    if (err) {
      console.error('Pipeline failed', err);
    } else {
      console.log('Pipeline succeeded');
    }
  }
);
```

由于 `pipe` 是危险的，因此应该使用 `pipeline`。

# Stream（流）模块

它是软件的一部分，允许我们在 Node.js 中创建流模块，该模块是所有流式 API 的基础。`stream` 模块是预装的 Node.js 原生模块。`stream` 对象是 `EventEmitter` 类的实例，在 Node 中，它用于处理异步事件。因此，流本质上是基于事件的。

要使用 `stream` 模块，请访问：

```javascript
const stream = require('stream');
```

`stream` 模块可以创建新的流实例。要消费流，我们通常不需要使用 `stream` 模块。

## 带流的 Node APIs

由于其优势，许多 Node.js 核心模块都包含了原生流处理能力，其中最著名的是：

- `net.Socket` 是构建流的主要 Node API，并是后续大多数 API 的基础。
- `stdin` 命令返回一个连接到 `stdin` 进程的流。
- `stdout` 函数返回一个连接到 `stdout` 进程的流。

## 74 征服 JavaScript

- `stderr` 函数返回一个附加到 `stderr` 的流。
- `createReadStream()` 在 `fs` 文件中产生一个可读流。
- `createWriteStream()` 建立带有可写流的文件网络。
- `connect()` 建立流连接。
- `HTTP.request()` 返回一个作为 `HTTP.ClientRequest` 类实例的可写流。
- `zlib.createGzip()` 使用 gzip（压缩算法）将数据压缩到流中。
- `zlib.createGunzip()` 是一个解压缩 gzip 流的函数。
- `zlib.createDeflate()` 使用 deflate（一种压缩方法）将数据压缩到流中。
- `zlib.createInflate()` 是一个解压缩 deflate 流的函数。

以下是可读流历史中的一些关键日期：

- `error` – 触发以信号表示发生了写入/管道错误。
- `pipeline` – 当可读流被管道（pipe）到可写流时，可写流发出此事件。
- `unpipe` – 当读取流取消管道时触发，以防止管道到目标流。

所有这些都是关于 Node.js 的基础知识。Node.js 最基础且最强大的元素是流、管道和链式调用。流确实可以帮助你编写且高效的 I/O 代码。Node.js 还有一个名为 BOB 的策略，旨在改进 Node.js 的流式数据接口，包括内部和未来的公共 API。

通过这种流，客户端不会一次性下载整个电影；而是下载视频的前几秒，并等待前面的视频完成后再下载接几秒。在开发在线应用时，开发者经常遇到各种媒体文件，其中某些可能很难处理。在本文中，我们将使用 Node.js 制作自己的视频流服务器。如果你按照此教程一步步操作，你将能够在 Node.js 中创建一个可以在你自己的项目中使用的视频流服务器。

# 应用开发 II ■ 75

## 项目概述

在开始编码之前，让我们从高层角度看看我们的应用将如何工作。在上面的图中，浏览器在左侧，服务器在右侧。你的网站上有一个 HTML5 视频元素，其源指向 `/video` 端点。

视频元素首先向服务器发送请求，之后头部（header）将交付视频所需的字节数。例如，视频开始时的请求范围将从第 0 字节开始，因此是 `0-`。服务器将返回 `206` HTTP 状态码，表示它正在返回带有适当响应头响应和内容长度的部分材料。视频元素从响应头中接收到的一个消息，指示视频未完成。因此，视频元素将播放之前下载的内容。视频元素将继续发送请求，直到没有可用的字节为止，此时循环将重复。

# 应用的优缺点

既然我们已经知道了应用将如何工作，现在让我们来看看使用这种过程的一些优缺点。

我们的流服务器创建起来将相当简单，正如我们在应用程序摘要中预测的那样。本质上，我们正在构建一个文件系统并交给客户端。我们的服务器将允许我们选择电影中的时间，并决定返回的负载大小。我们选择了 1 MB 是合适的，但我们可以根据需要进行设置。

然而，由于我们软件的简单性，服务器和视频播放器的运行效果并不如我们所愿。本质上，对于我们已经请求的内容，视频播放器只会请求我们当前观看的电影部分。我们可能会多次请求某些相同的资源。

## 代码教程

从开始：

我们将首先创建一个新文件夹并安装 npm：

```bash
npm init
```

## 76 征服 JavaScript

现在安装 nodemon 和 Express：

```bash
npm install --save express nodemon
```

由于你的视频元素是一个空文件夹，我们需要创建一个 HTML 文件。该 HTML 文件看起来应该是这样的：

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Video Streaming With Node</title>
  <style>
    body {
      margin: 0;
      padding: 20px;
      background-color: rgb(240, 240, 240);
    }
    video {
      width: 100%;
      max-width: 800px;
      display: block;
      margin: 0 auto;
    }
  </style>
</head>
<body>
  <video id="video" controls>
    <source src="/video" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</body>
</html>
```

# /video 端点

之后，我们将处理视频请求。代码看起来如下：

```javascript
const express = require('express');
const fs = require('fs');
const path = require('path');
const app = express();

app.get('/video', (req, res) => {
  const range = req.headers['range'];
  if (!range) {
    return res.status(416).send('No Content');
  }

  const parts = range.split("-");
  const start = parseInt(parts[0].substring(6), 10);
  const end = parts[1] ? parseInt(parts[1], 10) : fs.statSync(path.join(__dirname, 'video', 'The.Matrix.780p.mkv')).size - 1;
  const chunk = (end - start + 1) * 1;
  const file = fs.createReadStream(path.join(__dirname, 'video', 'The.Matrix.780p.mkv'), {
    start,
    end
  });

  const head = {



```javascript
'Content-Range': `bytes ${start}-${end}/${fileSize}`,

'Accept-Ranges': 'bytes',

'Content-Type': 'video/mp4',

'Content-Length': chunk,

};

res.writeHead(206, head);

file.pipe(res);

});

const fileSize = fs.statSync(path.join(__dirname, 'video', 'The.Matrix.780p.mkv')).size;

app.listen(8000, () => {

  console.log('Listening on port 8000');

});
```

# 应用开发 II ■ 79

## 创建响应头

我们现在必须创建要发送回的响应头。首先，将`end-start + 1`乘以内容长度。将创建`headers`对象。我们必须在`content range`中利用初始字节、结束字节和视频大小，如下：

```javascript
const headers = {
  'Content-Range': 'bytes ${end}/${videoSize}',
  ... // 这仅仅表示此区域还有额外的代码。

  It 是代码的一部分。
}
```

视频播放器使用代码来确定视频进到的程度。随后，我们将指定要返回的数据类型。添加视频类型和长度。你的`headers`对象应该像这样：

```javascript
const headers = {
  'Content-Range': 'bytes ${end}/${videoSize}',
  'Accept-Ranges': 'bytes',
  'Content-Length': contentLength,
  'Content-Type': 'video/mp4',
}
```

我们现在必须为请求组合响应。状态码 206 表示我们只发送消息的一部分。我们还需要对`headers`进行如下以下更改：

```javascript
// HTTP 206 Partial Content

res.writeHead(206, headers);
```

为了生成流，我们将使用文件系统库，并将视频路径作为参数，并在`options`中完成`start`和`end`：

```javascript
const videoStream = fs.createReadStream(videoPath, {
  start, end
});
```

# 80 攻克 JavaScript

`videoStream`是完全自包含的。我们必须将其管道到接收到的响应中：

```javascript
videoStream.pipe(res);
```

如果按照步骤步骤操作，文件应该像这样：

```javascript
const express = require("express");

const app = express();

const fs = require("fs");
```

```javascript
app.get("/", function (req, res) {
  res.sendFile(__dirname + "/index.html");
});

app.get("/video", function (req, res) {
  const range = req.headers.range;

  if (range) {
    res.status(400).send("Requires Range header");
  }

  const videoPath = "Chris-Do.mp4";

  const videoSize = fs.statSync("Chris-Do.mp4").size;

  const CHUNK_SIZE = 16 * 4;

  const start = Number(range.replace(/\D/g, ""));

  const end = Math.min(start + CHUNK_SIZE, videoSize);

  const contentLength = end - start + 1;

  const headers = {
    "Content-Range": "bytes ${start}-${end}",
    "Accept-Ranges": "bytes",
    "Content-Length": contentLength,
    "Content-Type": "video/mp4"
  };

  res.writeHead(206, headers);

  const videoStream = fs.createReadStream(videoPath, {
    start, end
  });

  videoStream.pipe(res);
});
```

```javascript
app.listen(8000, function () {
  console.log("Listening on port 8000!");
});
```

在完成之前，只需在你的`package`中添加`"start": "nodemon index.js"`。JSON 文：

```json
"scripts": {
  "start": "nodemon index.js" // 这是需要添加的主行
}
```



只需运行`npm start`即可看到最终结果。

##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。总结

在本节中，我们学习了如何使用 Node.js 创建自己的视频流服务器。我们首先详细介绍了项目架构，然后讨论了使用简单方法的优缺点。然后，通过构建视频端点、解析范围和创建响应头，我们可以开始构建应用程序。

## 应用开发 III

- IoT 概念
- 使用 Node.js 构建应用
- 关键字与语法

IoT 技术仍然非常年轻，它是为了响应市场对控制广泛范围设备、传感器和其他设备的需求而演变的。每个设备都有自己的接口，因此需要一个能够处理大量数据的统一系统。

今天，超过半的企业使用物联网（IoT）来构建新产品。越来越多的开发者正在寻找最有效的方法来设计 IoT 平台，利用现有的编程语言和工具。由于这是一个新领域，虽然没有一成不变的答案，但许多企业仍在寻求开发 IoT 倡议的最佳方法。

## 为什么 NODE.JS 是最佳解决方案？

在当今世界，智能设备变得越来越普遍。智能手表、微波炉、洗衣机甚至家都是这些例子。它们都与你的智能手机完美同步。

DOI: 10.1201/97810033557469-4

## 84 精通 JavaScript

我们只需下载一个应用程序，允许您管理智能设备执行的数十个过程。这就是 IoT 魔法开始的地方。它允许我们实时将移动应用程序与家里所有的智能技术同步。

我们使用各种计算机语言来构建此类解决方案，包括 Python、Java、C++ 和 Ruby。它们可以处理 IoT 系统的建立并做得很好。然而，对于专门为此目的创建的编程语言，它们与 JavaScript 相比都显得黯然无色，JavaScript 最适合处理 IoT。JavaScript 本身并不理想，但这就是 Node.js 发挥作用的地方。Node.js 提供了庞大的社区、大量的库以及在大型项目中可靠运行而不消耗大量服务器资源的能力。Node 是执行代码的服务器端环境。它被开发者用于创建大型多功能项目。它是一个非常强大的工具，但也非常简单。对于不熟悉 JavaScript 的开发者，他们也能使用它。

首先，我们想消除那些未看过仓库的人传播的 Node.js 误解。

对于 IoT 平台和应用开发，NODE.JS 的确切优势是什么？

首先，Node.js 是一个开源的跨平台运行时，被各种规模的企业用于创建快速、可扩展的应用程序。它是一个程序员积极使用的强大工具。

### 使用 Node.js 开发应用

Node.js 还拥有庞大的社区、大量的库以及在大型项目中可靠运行而不消耗大量服务器资源的能力。这是选择 Node.js 开发 IoT 的几个原因。

### IoT 协议易于 Node.js 集成

集成是 IoT 最重要的方面之一。IoT 应用广泛使用的 MQTT 协议被 Node.js 支持，使其能够简单地访问第三方服务并为各种场景做好准备。后端集成正在进行。

# 应用开发 III 85

MQTT.js 被所有云服务提供者的 Node.js SDK 使用。通过 MQTT，它可以可靠地将数百万消息路由到 AWS 端点和其他设备。

## 86 征服 JavaScript

### 安全的认证

Tokens、auth0、jwt 以及其他认证机制适用于 Node.js 应用。从物联网（IoT）的视角来看，每种机制都有其独特的优缺点。Tokens 很有用，但它们并不是完全安全的。它们是一种极好的认证技术，可以让你识别特定的用户并决定是否为其提供访问权限。

IoT 生态系统会将加密的令牌或登录/密码数据存储在固件中。如果有人拥有设备的物理访问权限，就可以窃取令牌，这对于 jwt 和 auth0 也是如此。

通过将任何服务器端认证工具集成到 Node.js 框架中，我们可以使用它们并使用 Node Package Manager（npm）手动完成此操作：passport、auth0 和 jwt。此外，还有用于集成云服务的包，如 Azure IoT hub Node.js 或 AWS-IoT。IoT 生态系统会将加密的令牌或登录/密码数据存储在固件中。如果有人拥有设备的物理访问权限，就可以窃取令牌，这对于 jwt 和 auth0 也是如此。通过将任何服务器端认证工具集成到 Node.js 框架中，你可以直接使用它们。我们可能可以使用 Node Package Manager 手动完成此操作：passport、auth0 和 jwt。还有用于集成云服务的包，如 Azure IoT hub 或 AWS-IoT。

## 使用 Node.js 创建 API 非常简单

构建 API的能力是 Node.js 的另一个优势。例如，LinkedIn 的开发者首次使用 Node.js 开发工具创建了移动 API。Node.js 框架被用于在该平台上构建 Web 服务和 API。因为使用 Node.js 开发 API 只需几行代码，因此可以快速完成。

### 从哪里开始使用 Node.js 开发 IoT 项目？

当我们开始构建一个 IoT 项目时，脑海中第一个问题通常是：从哪里开始？是先设计架构，还是选择我们所需的所有模块？也许你应该从数据库开始？

这比看起来要容易得多。第一步是设计一个包含所有字段的数据库架构。我们需要它来充分发挥你的项目的价值。如果没有它，由于系统架构糟糕，可能会导致请求延迟，甚至在开发过程中陷入停滞。数据库是 IoT 项目中最脆弱的部分，也是最难修改的部分。架构应该尽可能具有适应性，并适用于新技术的集成。

最佳解决方案是采用分层模型—视图—控制器（MVC）模式，其中每个系统组件在整体方案中都有自己的角色，并遵循 MVC 设计。

在我们决定数据库架构后，考虑数据将如何更新、更新频率以及数量。几乎所有的 IoT 服务都为你的问题提供了现成的解决方案。例如，AWS IoT 包含一种“规则（Rules）”功能，允许开发者或 DevOps 人员安排数据。我们可以选择数据存储在何处、使用哪个数据库、运行哪个脚本进行额外的数据处理。我们应该熟悉服务的运行机制，以避免重复造轮子。像 AWS 这样的服务设计初目的是让你的生活变得更轻松，如果我们不利用它们，就错失了机会。

### 如何为 IoT 选择最佳数据库？

现代数据库可以连接到 IoT 数据库；然而，这取决于开发者如何实现连接。在选择数据库之前，我们必须确定它是否适合我们提供给用户的功能。以下是该数据库的主要功能列表：

- 支持索引且设计灵活。
- 用户友好的方案，能够承受海量数据。
- 支持数据导出和导入。
- 使用各种参数进行多功能搜索。
- 具有很高的性价比。

在启动 IoT 项目时，取决于每个人来决定优先考虑哪些功能。然而，在项目中使用多个不同的数据库并不是坏主意。可能项目的设计非常复杂，以至于只有一个数据库能够满足所有功能需求。要记住：对于简单的操作，你不需要强大的数据库；相反，应该使用高度专门的数据库。

- InfluxDB：自 2013 年以来，InfluxDB 一直是 IoT 的最佳数据库。它是一个用 Go 语言创建的开源时序数据库。它为 IoT 设计卓越，这有助于它的持续流行。
- CrateDB 是一种用 Java 开发的开源分式 SQL 数据库。它的主要优势是它提供的库列表，例如 Facebook Presto、Apache Lucene 和 Elasticsearch，这些不需要任何额外的配置就能让你的生活变得简单。该数据库非常适合集成到各种 IoT 平台。
- MongoDB 是一个免费的 NoSQL 数据库。它是每个编写过 Node.js 项目的开发者的好朋友。它简单易用，具有类似于 JSON 的架构，与 JavaScript 配合得很好。MongoDB 可能不是构建 IoT 平台的理想答案，但将 Node.js 集成到平台它是理想的。
- Amazon DynamoDB 是一个闭源的时序数据库，是 Amazon 在线服务之一。最好与该公司提供的其他服务一起使用，例如 Cloudtable 或 IBMix。在这种情况下，AWS IoT 为构建高负载项目提供了一个强大的框架。单独使用此数据库是一个坏主意，但有许多不同的替代品可以实现相同的目的。在比较了几个现代数据库后，我们可以得出什么结论？我们都适合 IoT 开发，但每种都有自己的能力。因此，根据你的需求做出明智的决定。

### 如何让大数据为 IoT 项目服务

因此，在我们的 IoT 项目中，我们选择了主要的选栈，通过数据库和服务器的架构，现在是时候开始开发了。第一步是确定项目的哪个部分负载最重以及如何对其进行优化。如果我们利用复杂的解决方案（例如 AWS IoT 配合 DynamoDB），无论容量 AWS 都会承担。相比之下，如果我们在自己的服务器上构建，有一些解决方案可以帮助我们。让我们注意以下几点，以便我们的优化工作更加顺畅。

## 90 征服 JavaScript

现代世界的一切都必须实时运行，并具有简洁清晰的界面来显示数据。对于那些在快速工作和保持生产环境简单之间取得平衡的人来说，数据分析开发是一项重大挑战。许多人认为，使用预先解决方案并根据我们的项目需求进行定制是最好的。如果我们的项目不需要极其特殊的特性，这是最佳方法。某人、某地可能已经处理过你的问题并制定了解决方案。那么为什么不直接使用它呢？然而，因为没有两个 IoT 项目是相同的，你必须仔细考虑产品的细节。

如果我们需要构建实时分析，但时间紧迫，AWS 是一个很好的起点。我们也可以依靠互联网，根据开源代码寻找解决方案，这些代码可以轻松地集成到系统并使用。

当然，我们可以将 Web 客户端连接到 IoT 并直接输出数据，但这可能会产生安全忧虑。了解我们给了用户什么、他们应该如何授权，以及系统是否能够管理用户及其访问级别至关重要。理想的是将 IoT 分为服务器上不同的 WebSockets，它将过滤数据且不会对 IoT 产生直接影响。我们应该记住，在开发通过 WebSocket 的数据时必须避免内存泄漏。此外，当涉及到数据准备和传输到分析时，尽量不要让事情复杂化。

浏览器的能力用于确定所有的 JavaScript 动作。如果数据流过大，浏览器可能会变慢或可能崩溃。对于经验丰富的编码员来说，这不是问题，因为他们处理的是延迟、并发和数据过滤。始终考虑项目的目标受众，并根据他们的需求来定制一切。大多数开发者使用流行的框架或库来创建单页 Web 应用（angular 或 react）。

### 什么是基于 Node.js 的 IoT 应用的一些示例？

Node.js 生态系统的成熟性对 IoT 至关重要。但什么时候你应该使用 Node.js 呢？这里是生活中的一些实例：

## Uber

Uber 的主要行程执行引擎基于 Node.js。做出这一决定的关键由于是异步、分析大量数据的能力、简洁的代码以及低廉实现成本。

## 代码教程

现在有很多公司致力于开发“类 Uber”应用。理论是如果在马拉松期间创建一个可以在朋友需要时帮助他们的东西似乎会很有趣！

以下是我们在经过思考后同定的功能：

- 只需点击按钮，居民就可以请求他们所在地区最近的警察。它将发送一个“求救信号”，提醒附近的警察。
- 该地区的任何警察都会收到用户位置的提醒，并可以选择接受请求并解决问题。
- 一个评分量表。
- 从位置、已解决的案件等收集的数据可以通过某些创新的用户界面组件显示在地图上或使用图表显示。

你现在创建的每个应用都有几个关键组件：

- 在后端，有一个面向客户端的程序（你在浏览器或手机屏幕上看到的那个）。
- 入站的客户端请求和信息通过服务器进行路由。
- 信息。
- 存储在一个可以被查询的数据库中。

MongoDB 将是你后端的数据库。它更容易理解，并为地理空间数据提供了广泛的查询技术，这是我们项目所需要的。

对于我们的后端逻辑，我们将利用 Node.js。因为前端和后端用相同的语言编写，我们就不必担心学习新的语言或语法了。

## 92 征服 JavaScript

你将在前端使用 HTML5、CSS3、JavaScript 以及 Google Maps 和 Places API。
我们假设用户已经熟悉 JavaScript，并对 NodeJS 和 MongoDB 的运行原理有基本的了解。
让我们开始吧！

长期以来，开发者一直依赖 MongoDB 来创建应用程序。它的学习曲线很短，它的适应性使开发者能够快速、轻松地创建应用程序。
MongoDB 是我最喜欢的数据库之一，因为它帮助我快速构建想法原型并展示概念验证。
在开始之前确保你已经安装了 MongoDB 和 NodeJS。在编写本章时，MongoDB 的最新版本是 5.0。

## Schema 设计

由于我们正在使用 MongoDB，你在其中保存的所有内容都是文档集合（collection）。
让我们创建一个`citizensData`集合来收集公民信息，创建一个`policeData`集合来存储警察信息。现在，打开终端窗口并输入`mongo`来启动 mongo shell。一旦打开，输入以下命令查看现有的 MongoDB 数据库列表。

```
show DBS
```

为了存储我们应用的数据，你需要一个新的数据库。让我们将其称为`myUberApp`。我们可以通过输入来创建一个数据库：

```
use myUberApp
```

如果不存在，该命令将生成一个新的数据库。如果已存在，则指示 Mongo 在此数据库上运行以下过程。Mongo 将数据组织成集合。表（Tables）与集合类似。要查看已有的集合，输入：

```
show collections
```

`badge-id` 也可以作为警察的用户名。出于身份验证目的，你可能提供一个电子邮件地址和密码字段（密码不会被暴露）。保存相关信息的数据集。

```json
{
  "userId": "01",
  "displayName": "Cop 1",
  "phone": "01",
  "email": "cop01@gmail.com",
  "earnedRatings": 21,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "7th Cross Rd, Kalyan Nagar, Bengaluru, Karnataka 560043",
    "coordinates": [
      77.63873160000002,
      12.99871
    ]
  }
}
```

```json
{
  "userId": "02",
  "displayName": "Cop 2",
  "phone": "02",
  "email": "cop02@gmail.com",
  "earnedRatings": 10,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "HAL 2nd Stage, Indiranagar, Bengaluru, Karnataka 56038",
    "coordinates": [
      77.6411579999999,
      12.97185
    ]
  }
}
```

```json
{
  "userId": "03",
  "displayName": "Cop 3",
  "phone": "03",
  "email": "cop03@gmail.com",
  "earnedRatings": 15,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "Swamy Vivekananda Rd, Jogupalya, Bengaluru, Karnataka 560007",
    "coordinates": [
      77.620474000000,
      12.972814
    ]
  }
}
```

```json
{
  "userId": "04",
  "displayName": "Cop 4",
  "phone": "04",
  "email": "cop04@gmail.com",
  "earnedRatings": 11,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "406, MG Road, Shanthala Nagar, Shivaji Nagar, Bengaluru, Karnataka 560001",
    "coordinates": [
      77.6054709999999,
      12.975614
    ]
  }
}
```

```json
{
  "userId": "05",
  "displayName": "Cop 5",
  "phone": "05",
  "email": "cop05@gmail.com",
  "earnedRatings": 15,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "869, 12th Main Rd, Koramangala Block, Koramangala, Bengaluru, Karnataka 560034",
    "coordinates": [
      77.62710779999998,
      12.9279232
    ]
  }
}
```

```json
{
  "userId": "06",
  "displayName": "Cop 6",
  "phone": "06",
  "email": "cop06@gmail.com",
  "earnedRatings": 21,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "869, 12th Main Rd, Koramangala Block, Koramangala, Bengaluru, Karnataka 560034",
    "coordinates": [
      77.62710779999998,
      12.9279232
    ]
  }
}
```



```json
"address": "7th Cross Rd, Domlur I Stage Stage 2, Domlur, Bengaluru, Karnataka 560071",
"coordinates": [
  77.63873160000002,
  12.99871
]
```

## 96 征服 JavaScript

```text
12.9609857
}
```

在你的终端中，输入以下命令从此 JSON 文件导入数据：

```bash
mongoimport --DB myUberApp --collection policeData --drop --file ./path/to/json.json
```

现在，在开始构建数据库之前，我们应该熟悉 MongoDB（或任何数据库）中的索引是如何运作的。索引是一种数据结构或数据的特定排列方式，允许你快速搜索信息。这使你能够访问结果，而无需搜索整个数据库。

例如，假设你按照姓名的升序顺序在一书中存储了学生信息，这意味着我们在`name`（姓名）字段上有一个索引。这样的话，如果我们需要查找一个名叫 Tyrion 的人的信息，我们可以立即找到它，而无需查看其他学生。

然而，如果相同的信息是按身高升序排列记录的，那么通过姓名查找某人的信息将变得困难。因为学生不再按照姓名顺序保存，我们可能需要扫描和搜索许多行数据，这可能会花费很长时间。但是，现在可以进行不同类型的查询。例如，获取身高在 4 到 5 英尺之间的儿童信息。在那种情况下，Tyrion 的信息可能被立即获取，因为不同的数据库支持不同类型的索引。支持 MongoDB 的索引完整列表可以在此处找到。

所以，如果你输入以下命令：

```javascript
DB.policeData.find().pretty()
```

返回`policeData`集合中包含的所有文档，即警察的完整列表。我们可以使用命令`db.policeData.find({userId: "01"})`来获取`userId`为`"01"`的特定警察的信息。

# 应用开发 III 97

```json
{
  "id": ObjectId("57e75af5eb1b8edc94406943"),
  "userId": "01",
  "displayName": "Cop 1",
  "phone": "01",
  "email": "cop01@gmail.com",
  "earnedRatings": 21,
  "totalRatings": 25,
  "location": {
    "type": "Point",
    "address": "Kalyan Nagar, Bengaluru, Karnataka 560034, India",
    "coordinates": [
      77.6399711000003,
      13.0280047
    ]
  }
}
```

## MongoDB 中的地理空间索引

可以使用地理空间索引在文档中存储 GeoJSON 对象。GeoJSON 对象具有各种形状和大小，包括 Point、LineString 和 Polygon。如果你查看`.find()`命令的结果，我们会注意到每个位置都是一个带有`type`字段和`coordinates`字段的对象。这非常重要，因为当你的 GeoJSON 对象`type`为`Point`类型时，可以使用`$near`命令查询特定经纬度特定距离范围内的点。

我们需要在`location`字段上构建一个 2D 球索引（地理索引）以及其内部的`type`字段以便使用。2D 球索引可用于计算类似于地球的球体上的几何结构。这包含了 MongoDB 中的地理搜索，例如包含、交叉和接近性搜索。

所以，在你的 mongo shell 中，输入：

```javascript
db.policeData.createIndex({"location": "2dsphere"})
```

要获取从给定坐标对的最近到最远的文档，请使用以下语法：

```javascript
DB.<collectionName>.find({
  <fieldName>: {
    $near: {
      $geometry: {
        type: "Point",
        coordinates: [<longitude>, <latitude>]
      },
      $minDistance: <distance in metres>,
      $maxDistance: <distance in metres>
    }
  }
}).pretty()
```

`$minDistance`和`$maxDistance`是两个可以用于计算距离的变量。像`distance`这样的字段是可选的。现在，运行此命令查找纬度 12.9718915 和经度 77.641154499999977 2 公里内的所有警察。

```javascript
DB.policeData.find({
  location: {
    $near: {
      $geometry: {
        type: "Point",
        coordinates: [77.641154499999977, 12.9718915]
      },
      $maxDistance: 2000
    }
  }
}).pretty()
```

就是这些了：输出将包含一个文档列表。完美！让我们将相同的逻辑应用于 Web 服务器。这个`package.json`文件应该被下载并保存到我们项目文件夹的根目录下（命名为`package.json`），然后`cd`到包含文件的目录并从终端执行它。

```bash
npm install
```

这里是我们将使用的一些包的概述：

- Express 是一个 Web 框架。
- Underscore 是用于函数式编程的工具。
- Body-parser 解析传入的请求。
- Consolidate 使模板引擎以一致的方式工作。
- MongoDB 驱动用于与数据库交互。
- Socket.io 处理会话。
- Debug 是用于调试的库。

# 应用开发 III 99

```javascript
var http = require("http");

var express = require("express");

var consolidate = require("consolidate");

var _ = require("underscore");

var bodyParser = require("body-parser");

var routes = require("./routes");

var mongo = require("mongodb").MongoClient;

var app = express();

app.use(bodyParser.urlencoded({extended: true}));

app.use(bodyParser.json({limit: "10mb"})

app.set("views", "views");

app.use(express.static("./public"));

app.set("view engine", "html");

app.engine("html", consolidate.underscore);

var portNumber = 7000;

http.createServer(app).listen(portNumber, function() {
  console.log("Server listening at port " + portNumber);

  var url = "mongodb://localhost:27017/myWebApp";

  mongo.connect(url, function(err, db) {
    if (err) console.log(err);

    console.log("Connected to Database");

    routes.initialize(app, db);
  });
});
```

# 应用开发 III 101

```javascript
function initialize(app, DB) {
  // 对 /cps 的 GET 请求必须返回本地警察列表
  app.get("/cps", function(req, res) {
    /*
     * 从请求中提取经度和纬度信息。
     * 然后，使用 MongoDB 的地理空间查询获取最近的警察，
     * 并将结果返回给客户端。
     */
  });
}

exports.initialize = initialize;
```

## 102 征服 JavaScript

为了让此功能生效，我们需要将坐标作为查询字符串传递到请求。在另一个单独的文件，我们将编写数据库操作。因此，创建一个名为`DB-operations.js`的新文件，并写入以下内容：

```javascript
function fetchNearestCops(DB, coordinates, callback) {
  DB.collection("policeData").createIndex({
    "location": "2dsphere"
  }, function() {
    DB.collection("policeData").find({
      location: {
        geometry: {
          type: "Point",
          coordinates: coordinates
        },
        maxDistance: 2000
      }
    }).toArray(function(err, results) {
      if (err) {
        console.log(err);
      } else {
        callback(results);
      }
    });
  });
}

exports.fetchNearestCops = fetchNearestCops;
```

此函数接受三个参数：DB 实例、按[经度,纬度]顺序排列的坐标数组，以及返回查询结果的回调函数。

如果我们之前已经对所选字段生成了索引，那么在查询之前如果已经执行过，你可能希望跳过创建索引步骤。

现在我们只需要在处理程序内部调用此函数。因此，修改我们的路由。这是其对应的 JS 代码：

```javascript
var dbOperations = require("./db-operations");

function initialize(app, DB) {
  // "/cops?lat=12.971895&lng=77.6411544999997"
  app.get("/cops", function(req, res) {
    // 将查询字符串转换为数字
    var latitude = Number(req.query.lat);
    var longitude = Number(req.query.lng);

    dbOperations.fetchNearestCops(
      DB,
      [longitude, latitude],
      function(results) {
        // 结果应该作为 JSON 返回给客户端
        res.json({
          cops: results
        });
      }
    );
  });
}

exports.initialize = initialize;
```

就是这些了！在终端中通过 node.js 运行 app，登录浏览器并访问`http://localhost:8000/cops?lat=12.971895&lng=77.64115449999997`。

我们应该收到一个包含空数组或包含警察数据数组的 JSON 响应，这取决于你提供的查询字符串。同时，请查看 GitHub 仓库以获取源代码！

## 总结

在本章中，我们尝试涵盖了与 IoT 项目开发相关的广泛主题，这些主题可以用于高负载系统。首先，开发者必须识别 IoT 平台所需的功能，并使用他们手头现有的工具进行实现。编程世界并非停滞不前，各种问题的新解决方案每天都在涌现。我们必须时刻关注所有出现的新事物，否则就会会被时代抛弃。IoT 平台训练了我们需要保持纪律，而且它不会轻易容忍错误。数据丢失或处理错误可能会对公司以及所有依赖该解决方案的用户产生灾难性的影响。开发团队必须始终以最好的方式处理项目，预测平台可能遇到的所有问题。首先，识别架构，以及将使用的外部解决方案以及如何管理它们。我们永远不知道你的解决方案是否完全可行，但在真实项目上进行测试总比事后诸悔要好。当然，情况并非总是如此；在某些情况下，开发者必须偏离指南，但他们必须证明他们所建立目标的合理性。永远不要过度依赖某项单一的技术或服务，并始终愿意尝试新事物。也许一个新的库或框架可以解决你一直以来在使用旧技术时遇到的所有问题。决定我们将如何测试它，因为大数据在任何情况下构建和监控都是困难的。如果我们以审慎的态度对待一切，那么我们都是正确的。

# 代码优化

## 本章内容

- 高效的代码编写
- 错误处理
- 代码安全

在上一节中，我们学习了如何使用 Node.js 创建一个基于物联网的应用程序。现在在本章中，我们将探讨 Node.js 的效率和性能。我们将集中在缓存、负载均衡和应用程序监控上。

在设计 Web 应用程序时，JavaScript 是脑海中浮出的唯一编程语言。因为它易于学习，它是 Web 应用开发中最流行的编程语言，与其他语言配合良好，并可以用于创建各种应用程序。然而，根据最近的趋势调查，Node.js 不仅开启了一项新趋势，而且正在捕捉后端编程的所有动力。

随着竞争变得日益激烈，企业正积极寻找工具、技术和框架，以便他们通过单一解决方案对许多操作系统保持强有力的控制。此外，许多组织认为 Node.js 是服务器端开发的理想替代方案，以满足对在所有平台上流畅成功运行的应用的持续需求。

DOI: 10.1201/97810033357469-5

## 106 征服 JavaScript

由于 Node.js 是一个高度稳定且可靠的 JavaScript 框架，像 Google、Microsoft、Netflix、LinkedIn 等高流量大公司渴望使用它。在设计 Web 应用程序时，性能至关重要。我们将讨论 Node.js。

### 是什么让 NODE.JS 的性能如此特别？

V8 是最快的引擎之一，驱动了 Node.js。事件循环允许 Node.js 进行并发处理，这意味着不需要等待第一个任务完成即可开始。

## 什么是事件循环？它是如何工作的？

事件循环是一种将长时间运行的操作拆分为可管理区块的技术。它可以作为线程的替代方案。该技术类似于脉动；Node.js 扫描队列并启动新任务。如果有任何需要的任务，Node.js 将其引导调用栈。

## 事件循环与 NODE.JS 性能

为了避免写入文件、网络查询和执行大型计算等长时间运行的同步操作，理解 Node.js 的单线程特性至关重要。让我们来看一个例子：我们想创建一个有两个端点的 Node.js 应用：一个用于文件上传，另一个用于搜索用户信息。通常情况下，获取用户配置 API 的频率高于文件上传端。如果在编写 Node.js 程序时不使用事件循环进程，Node.js 可能会占用用户配置 API，而用户正在上传文件。

## 检测内存泄漏

如果程序分配了某些内存后没有清理，对象将不断堆积直到内存资源耗尽，导致崩溃。正如我们在之前的博客“内存泄漏”中提到的，密切关注情况至关重要。为了解决它的局限性，V8 引擎使用了两种垃圾回收：

- 标记-清除（mark sweep）：比扫描慢，但可以清除工作内存中的所有垃圾。
- 扫描（scavenge）：快速，但不会移除未引用的项目。换句话说，它是不完全的。

## 108 征服 JavaScript

- 让我们从一个简单的性能测试工具开始：Artillery。它是用 Node.js 语言编写的。
- 当我们设置 Artillery 时，它会对你的 Node.js 应用进行定期查询。
- 我们可以告诉 Artillery 请求哪些端点、以多快的速率以及持续多久等。

让我们来看一个基础测试配置。

```yaml
Config:
  target: "https://artillery.io"

  phases:
    - duration: 45
      arrivalRate: 15

  defaults:
    headers:
      x-my-service-auth: "9874018382710021882985667"

  scenarios:
    - flow:
        get:
          URL: "/docs"
```



我们正在告诉 Artillery我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。以 15 的速率对你的端点进行请求 45 秒，这大约等同于有 15 个访问访问该 URL。运行以下命令进行测试：

我们使用 `artillery` 运行 `config.yml`。

### 在 Node.js 中创建性能测试配置

性能测试配置指定了你的性能测试将如何执行。例如，如果我们开始运行一个电子商务网站，我们可以预期全天范围内都有稳定的客户活动。或者，如果我们的应用程序是用于订票的，我们将在短时间内看到大量流量，即票务订单开启的时间。

因此，我们的性能测试环境也应该是类似的。我们可以根据需要创建尽可能多的测试配置，并按我们喜欢的任何顺序运行它们。

## 复制大规模分布式系统

当应用程序达到一定规模时，流量水平可能会变得极高且不可预测。我们还可以按照预期的用户百分比对 Node.js 应用进行测试，如果检测到性能下降，我们可以回退到先前的执行状态，即典型的流量水平。这种技术的关键优势在于，我们可以在实际生产应用程序上进行测试，因此我们不必再担心测试结果与真实情况不符。

我们需要数据来找出为什么我们的程序加载如此缓慢。在获取数据后，我们需要使用 Node.js 性能监控对我们的应用程序进行评估。

## 配置我们的监控

所有应用程序在它们所做的事情上都是优秀的，但都需要某种类型的监控。这些监控工具帮助我们更好地理解应用程序重要的性能指标。在进行性能测试之前，我们应该更好地了解需要满足什么样的性能基准。我们的 SLA（服务水平协议）和 KPI（关键性能指标）是什么？哪些关键措施可以帮助我们更好地理解性能问题？

- 带有 API 运行：API 有多种价位和功能。根据需求选择最合适的工具至关重要。为了检查性能，我们应该尽可能获取数据。

以下是一个很好的起点：

- 基础架构数据：我们几乎肯定需要运行应用程序的主机的数据。我们可以在运行在云端的应用程序原始版本中接收这些数据。这些信息将包括主机的 CPU 使用率、内存使用和连接信息。

- 应用程序监控：这些工具位于应用程序代码内部，能够记录信息，例如函数如何被调用/执行、我们提出了哪些问题等。

# 征服 JavaScript

- 聚合日志：聚合日志使得搜索和可视化我们的日志数据变得简单。我们可以为每个 API 的性能绘制图表并记录。

### 设置 Node.js 性能测试环境

云托管可能是设置测试基础设施最高效的方法。为了消除请求延迟和数据偏差，云托管确保测试在同一台机器和同一时间位置执行。

### 运行我们的测试

在启动命令行配置后，我们在这个阶段将收到发往 Node.js 应用的请求。我们可以使用所选的监控来查看事件循环是否正常工作、对 Node.js 的请求时间是否超过预期，以及连接是否超时。使用 Artillery 和 Retrace 等工具对 Node.js 的速度和性能进行性能测试可能帮助我们发现性能退化。

### 如何让 Node.js 运行更快

让我们来看几种让 Node.js 运行更快的技术。提高 JavaScript 性能的技术包括：

## 前端工具

在前端，发送到浏览器的内容尽可能少至关重要。这特别包括图片、JavaScript 和 CSS 文件。模块打包器（例如 `webpack`, `Parcel`, `Rollup`）和任务运行器参与了实现这一可能性的过程（例如 `Gulp`, `Grunt` 等）。

### 任务运行器和模块打包器

模块打包器是构建工具，它们将一组模块及其依赖项合并成单个文件或文件集合。之后，这种压缩化后的输出可以在生产环境中使用。压缩化过程随我们使用的工具而异，但在大多数情况下，我们可以利用 JavaScript ES6 版本的标准化格式作为代码模块。可以进行复杂的转换，例如缩短多字符变量名或采用与原始代码相当的更短语法，以及将多个 JavaScript 文件合并为一个以减少网络查询。CSS 压缩也是如此；删除了多余的空格和注释，以便浏览器更容易解释代码。

## CSS 的模块和预处理器

在压缩化方面，CSS 在减少页面加载期间的浏览器请求方面并无不同。`post-CSS`、`Sass` 和 `LESS` 等 CSS 预处理器提供了变量、函数和混入。

## 图片

在将代码发送到浏览器时，我们还需要考虑图片。通常情况下，照片越大越好。

## HTTP/2 和 SSL

使用 HTTP/2 需要安全传输层（TLS）和套字层安全（SSL）协议。Node.js 的功能让设置 HTTP/2 变得非常费力。HTTP/2 具有以下特性：

- 头部压缩：移除多余头部并强制对所有头部压缩。
- 多复用：允许在单个 TCP 连接上同时检索资源。

多复用用于减少发送到服务器的请求。建立 HTTP 连接的时间通常比发送数据的时间更高。

## 使用缓存

缓存是提高应用速度的流行方法。发生在客户端和服务器端。客户端缓存是临时存储 HTML 页面、CSS 样式表、JS 脚本和多媒体资产的过程。缓存通过在浏览器或内容分发网络（CDN）中保留频繁请求的信息来节省成本。客户端缓存发生在浏览器或 CDN 缓存数据时。这种想法是，如果用户访问网站后离开，网站不应再次下载所有资源。

这通过 HTTP 缓存头部变得可行。缓存头部分为两类：

- 过期日期：指示必须再次请求资源。
- 缓存控制：`max age` 指示资源的有效期。

除非并且资源具有缓存头部，否则浏览器只有在缓存过期后才会重新请求资源。这种方法也有一些缺点。例如，如果资源发生了变化怎么办？必须以某种方式破坏缓存。通过在资源 URL 中添加版本号，我们可以使用缓存破坏方法来解决此问题。使用 Node.js 技术如 `webpack`，这非常简单。

定期进行缓存是提高性能的一种极佳方法。缓存可能很困难，因此我们需要工具来帮助；我们可以有效地缓存应用程序，例如：

- `Redis` 缓存设计用于在单线程中处理缓存数据请求，并且是完全异步的。考虑尝试一下。它是一个易于使用的 API，用于管理我们的客户端和服务器端缓存。
- `Memcached` 是一种分布式内存系统，可以在多个节点上保存数据。它利用了具有哈希表功能的哈希方案。这些设计确保了添加或删除服务器节点不会影响键到服务器节点的映射。
- `Node-set` 的缓存 `get` 和 `delete` 方法与 `Memcached` 的方法几乎等同。它有一个超时机制，当超时过期时从缓存中删除数据。
- `Nginx` 将有助于负载均衡。`Nginx` 将有助于对静态文件进行缓存，使应用程序能够专注于其他任务。它具有极低的内存占用和高并发性。

## 改进数据管理技术

优化数据管理技术对性能至关重要，因为它简化了系统流程并提高了应用程序的整体效率。我们可能会思考 Node.js 应用程序中哪些部分可以进行优化。从查看如何管理数据开始。Node.js 程序可能会因为 CPU/IO 密集型任务（例如数据库查询或缓慢的 API 请求）而变慢。在 Node.js 项目中，数据是通过发送 API 请求并返回响应来获取的。

## 实现此点的有效方法是什么？

分页（Pagination）是一种常见的方法，它将响应划分为内容批，可以在保留提供给用户客户端的大量数据的同时，优化响应。

过滤（Filtering）是一种实用的策略，因为它允许客户端根据其自身的标准来限制结果。这会减少总调用次数和显示的结果数量，同时也允许用户根据其需求更精确地确定是否提供了所需的资源。在 REST API 设计中，这两个原则被频繁使用。

# 征服 JavaScript

数据获取有两种方式，即为获取不足（underfetching）和获取过度（overfetching）。前者提供了比客户端所需的更多的数据，而后者则未能提供必要的数据，导致需要后续调用不同的端点来完成数据收集。这两个问题可能会在客户端侧出现，其结果是 API 扩展不足。GraphQL 解决了这种情况，因为服务器不需要猜测客户端想要什么；客户端指定它们的请求并准确地获得它们想要的内容。

## 负载均衡

创建能够处理大量连接的高性能应用程序是一个典型的挑战。为了维持连接，一种频繁的选择是分配流量。负载均衡是这种方法的术语。为了管理多个连接，Node.js 允许我们克隆应用程序实例。这可以通过单台多核服务器或多个服务器来实现。引入的 `cluster` 模块可以通过生成新的进程工作线程（每个 CPU 核心一个）在多核服务器上扩展 Node.js 应用，这些线程都会同时运行并连接到单个主进程，允许进程共享服务器端口。它充当一个单一的大型多线程 Node.js 服务器。我们可以使用 `cluster` 模块来实现负载均衡，并使用轮询（round-robin）技术将传入的连接分配到环境中众多 CPU 核心上的所有工作线程。

使用 PM2 进程管理器来保持应用程序无限运行是另一种选择。它通过在发生代码更新或错误时重启程序来防止停机。PM2 包含一个集群功能，允许我们在所有核心上运行数多个进程，而无需担心修改代码以适应原生的 `cluster` 模块。单集群设计有缺点；我们计划从单服务器架构转变为带有反向负载均衡的多服务器架构。

它（NGINX）允许在多个 Node.js 服务器上进行负载均衡，并提供多种负载均衡策略：

- 轮询（Round robin）：将新请求路由到列表中的下一个服务器。
- 最少连接（Least connections）：将新请求路由到活动连接最少的服务器。
- IP 哈希（IP hash）：将客户端 IP 地址哈希后发送到相应的服务器。

## 代码优化 ■ 115

当使用多个应用程序服务器时，代理功能保护 Node.js 服务器免受直接互联网流量的影响，并赋予我们很大的自由度。

## 安全客户端认证

如果你想为用户提供定制化体验，大多数 Web 应用必须保留状态。如果用户可以登录我们的网站，我们需要跟踪他们的会话（sessions）。

在实现有状态认证时，我们通常会生成随机会话标识符，将会话详情保存在服务器上。我们可以使用像 `Redis` 这样的中央存储解决方案来存储会话数据，或使用 IP 哈希方法（负载均衡）来确保在将有状态解决方案扩展到跨多个服务器的负载均衡应用程序时，用户始终能到达同一个 Web 服务器。使用单个服务器有一些缺点，例如，如果该服务器需要维修，就会导致问题。

另一种可扩展的方法是使用 JWT 的无状态认证，可能更好。它的好处是始终可访问的，无论哪个系统为用户提供服务。当用户登录时，典型的 JWT 实现会生成一个令牌（token）。该令牌是包含所需信息的 JSON对象的 base64 编码。客户端获取令牌，并用于验证所有 API 请求。

## 保持代码的轻量与紧凑

在设计移动端和 Web 应用时，确保我们使用了保持代码库最小化的原则。这适用于客户端和服务器代码。结果是延迟和加载时间将缩短。对于保持代码简洁，单页 Web 应用（SPA）是一个极佳的选择。假设我们的 Web 应用有一个页面，页面上有几个 JavaScript 文件。当我们在浏览器中访问此页面时，它会对其发起六次 HTTP 调用。

Node.js 有许多开源库和模块。在开发阶段，我们应该考虑为什么使用某个框架而不是另一个。关键点是，使用框架应该是值得的。这并不是说选择

# 征服 JavaScript

是一个糟糕的主意。框架是极好的。它们具有可扩展性并有明显的优势。只有当框架能让我们的代码更容易理解时才使用它。

### 使用 WebSocket 进行有效的服务器通信

HTTP 请求/响应模型长期以来一直是互联网的基础。在应用程序中，WebSocket 是 HTTP 的替代方案。它们允许客户端和服务器进行双向长期的通信。一旦建立了通道，它将保持开启状态，允许客户端和服务器快速可靠地进行通信。

HTTP 对于数据共享和客户端驱动的通信是有效的。通过 WebSocket，服务器可以在客户端未显式请求之前向其传递消息，允许它们同时对话。这对于实时和长期通信是理想的。

## 异步编码

Node.js 使用单线程并发架构。为了提供非阻塞的操作流，Node.js 大量使用异步代码。得益于异步 I/O，在第一次传输完成之前其他处理就可以继续。同步编码可能会导致我们的网站无法访问。它采用了阻塞操作，可能会导致我们的主线程阻塞，从而导致网页速度大幅下降。我们可以利用队列来监控异步工作流，允许我们附加额外的任务并添加额外的回调，而不会停止主线程。

查看以下示例：

## 代码优化 ■ 117

在使用 Node.js 文件系统时，我们在两种模型中都使用了文件读取操作。

## 同步

```javascript
const fs = require('fs');

const content = fs.readFileSync("app.txt", "utf8");

console.log(content);

console.log('waiting for the file to read......');
```

## 异步

```javascript
//引入文件系统模块
const fs = require('fs');

//readFile() 读取文件 - 注意：原文为 readFileSync
fs.readFile("app.txt", "utf8", function (err, content) {
  if (err) {
    return console.log(err);
  }
  // 读取文件
  console.log(content);
});

console.log('waiting for the file to read.....');
```

所有操作都会挂起，直到同步片段完成数据处理。在向控制台打印数据和消息之前，`readFileSync` 将读取文件并将其数据存储在内存中。

当系统进行其他活动时，控制台消息将异步异步打印。尽管它是最后一条命令，“waiting for the file to read”也会在文件内容之前打印。当文件被读取时，将调用回调函数。使用异步方法我们的应用程序将运行得更快，并且可以避免所谓的“回调地狱”。

## 查询增强

考虑对包含超过百万行数据的数据库表进行查询。该数据库获取数据终点的程序会对我们应用程序的性能产生重大影响。糟糕的查询会减慢应用程序的速度，让用户感到沮丧。查询优化是解决问题的解决方案。

## 118 征服 JavaScript

### 提高数据库性能优化的基本策略概述

## 尽可能避免 SELECT *

这似乎是选择列的最而易见的方法对吧？然而，我们应该记住这个问题可能花费多少时间。使用更分离的技术来查询表中的列。使用 `SELECT` 语句精确查询我们所需的数据，避免额外的数据库抓取负载。考虑一个名为 `Customers` 的表，其中包含 `FirstName`, `LastName`, `City`, `State`, `Zip`, `PhoneNumber` 和 `Notes` 字段。以下两个查询可以 `SELECT FirstName, LastName, City, State` 和 `Zip`。

## 第一个查询

```sql
SELECT *
FROM Customers
```

## 第二个查询

```sql
SELECT FirstName, LastName, Address, City, State, Zip
FROM Customers
```

尽管我们不需要此数据库中的所有字段，但初始查询将拉取所有字段。因为第二个查询只返回所需的字段，因此它是执行 `SELECT` 语句更有效的方法。在使用 `INSERT` 和 `UPDATE` 命令时，也应该应用相同的原则。

## 使用 WHERE 子句

查询的目的是从我们的数据库中检索相关记录。`WHERE` 子句有助于过滤记录并根据约束限制拉取的记录数量。`WHERE` 子句充当了 `HAVING` 子句的角色，在过滤数据集之前选择记录。SQL 中的 `WHERE` 语句快得多，因为它们减少了数据库引擎处理的数据量。

## 使用 LIMIT 采样查询结果

`LIMIT` 只返回指定数量的记录。当使用 `LIMIT` 对数据集实施限制时，请确保结果是理想且相关的。例如，如果我们的 `Customer` 表有 500 条记录，而我们只需要前 100 条，`LIMIT` 是一种抽样所需结果的高效技术，同时避免了剩余的 400 条记录。

这里有一个示例：

```sql
SELECT FirstName, LastName, Address, City, State, Zip
FROM Customers LIMIT 100
```

#### 避免 CHOOSE A UNIQUE OPTION

通过通过分组来消除重复记录以产生唯一结果。我们表中的 `Customers` 作为一个示例。

```sql
SELECT DISTINCT Name, Surname, State, Zip FROM Customers
```

一些常见的名字和姓氏，例如 Johnny Depp，可能会被分在一起。结果是，记录的数量将是不正确的。当表中包含大量名为“David Smith”的客户时，此查询可能运行很长时间。使用更精确、高效的查询，例如：

```sql
SELECT FirstName, LastName, State, Zip FROM Customers
```

记录的数量也将是正确的。

## 根据需要使用通配符（百分号）字符

如果你想 `SELECT` 名字以字母“Avi”开头的消费者：

第一个查询

```sql
SELECT FirstName from Customers where FirstName like '%avi%'
```

第二个查询 2

```sql
SELECT FirstName from Customers where FirstName like 'avi%'
```



在第一个查询中，将检索到如`Avishek`、`Avinash`或`Avik`等`FirstNames`。这种方法我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。低很的，因为如果`FirstNames`包含字母“Avi”，它可能会返回意想不到的结果，例如`David`、`Xavier`或`Davin`。使用第二个查询可以更高效地执行此通配符。

### 在非峰时段运行查询

当并发用户数最低时，应该在生产数据库中运行分析和数据管理查询；通常在凌晨 3 点到凌晨 5 点之间。

查看这篇关于 MySQL 查询性能增强的文章。它包含了重要的 MySQL 提示，将帮助我们提高查询编写技巧。

## 不要使用会话

会话信息保存在内存中。随着我们应用流量的增加，产生产生会话，可能会导致巨大的服务器负担。我们必须找到保存会话数据的方法或减少会话中保留数据量的方法。使用外部会话存储，如`Redis`、`Nginx`或`MongoDB`。为了提高速度，建议尽可能避免存储会话状态。

## 脚本的跟踪和日志

我们可以使用日志来跟踪应用程序的活动。程序执行期间可能会发生致命错误（尽管我们的应用在测试时运行正常）。我们必须快速接收输入，确定哪些代码包含错误，并在用户发现问题之前修复。

`Console.log()`（记录标准输出 stdout）和`console.error()`是 Node.js 中两种常用的日志方法。然而，有更高效、可扩展的第三方日志库。

## Winston

`Winston`是一种简单、通用且极其多功能的异步日志器。它改进了日志的灵性和扩展性。根据 NPM ，它是最流行的日志器。

## Morgan

它是 Node.js 应用程序的中间件，用于记录 HTTP 请求。`Morgan`提供关于我们应用如何使用的见解，以及对可能威胁我们应用的潜在错误问题的警告。`Morgan`是 Node.js 开发者最信任的 HTTP 日志器。`Morgan`旨在像 Apache 和 Nginx 服务器那样记录失败到访问日志或错误日志。

## Bunyan

`Bunyan`是一种以 JSON 格式保存日志条目的简单日志器。更多详细信息可以从页面访问。

## 并行

在请求远程服务、数据库调用或文件系统访问时，确保并行执行流。任务并行化减少了延迟并消除了任何阻塞过程。

# 122 征服 JavaScript

# Node.js 加密指南

Node.js 会受到各种形式的 Web 应用攻击，就像任何其他编程语言或框架一样。尽管 Node.js 默认是安全的，但第三方包可能需要额外的安全措施来保护我们的网站。

## 为什么 Node.js 会存在安全问题？

开源应用的开源特性带来了许可和安全方面的问题。此外，静态和动态代码分析等安全检测技术在检测开源漏洞方面是行之不力的。

我们必须检查解释依赖关系的 NPM 索引文件以寻找 Node.js 中的开源部分。尽管如此，这些索引文件并不包含任何被重用的开源部分。开源项目有时会被开源社区重新利用，以缩短产品上市时间、加速开发并增加功能。因此，商业开发者和开源开发者都能够将代码片段、函数和方法嵌入到文件中。此外，许多 Node.js Web 开发项目使用的并非官方的 Node.js 许可。

## Node.js 安全忧事项与建议

由于 Node.js 的安全漏洞，我们可能会受到中间人攻击、代码注入和复杂的持续性威胁。以下是可能导致这些缺陷的 Node.js 安全忧事项概述，以及一些可能的解决方案：

### 验证用户输入以限制 XSS 攻击

#### 问题 5.1

跨站脚本（或 XSS）允许黑客将存在漏洞的客户端脚本注入到许多人查看的网页中。漏洞的客户端脚本可能导致数据泄露。此外，黑客可以访问 JavaScript 代码。由于用户输入未经过审核，导致了这种情况。结果，如果用户在搜索框中输入的内容在数据库中未被发现，它将以相同的方式返回给他们。因此，黑客可以在搜索框中输入 JS 代码而不是产品名称，从而运行类似的 JS 代码。

#### 解决方案

我们可以检查用户的输入。可以使用输出编码方法或带有内置编码框架的 Jade 引擎等工具来防止 Node.js 中的 XSS 攻击。我们还可以使用`XSS-filters`或`Validator.js`来。

### 必须尽一切避免数据泄露

#### 问题 5.2

不要只依赖前端提供的内容；还要考虑我们将提供前端的内容。我们可以轻松地将对象的所有信息传输到前端，并且显示我们想要的内容。另一方面，黑客可以快速检测到从后端发送的隐藏数据。

#### 解决方案

只需交付所需的信息。如果我们只需要姓和名，只需从数据库中提取它们即可。这需要我们付出一点精力，但是非常值得的。

### 使用安全代码检查工具（Linters）

#### 问题 5.3

漏洞可以自动扫描。此外，我们可以在编写代码时检测到基础安全问题。

#### 解决方案

可以使用如`eslint-plugin-security`等代码检查工具作为解决方案。如果我们采用不安全的编程方式，这种安全代码检查工具会告警我们。

### 每个请求都应该实现访问控制

#### 问题 5.4

这通常与应用程序对特定 URL 或内部区域的用户权限进行何种程度的彻底评估有关。因此，我们可以利用访问暴露来阻止应用程序的区域（例如管理员仪表板），使得没有适当角色的用户无法访问它。

#### 解决方案

消除此漏洞的最佳方法是手动测试需要特定用户权限的应用模块。为了避免访问令牌在客户端通过 JWT（JSON Web Token）授权令牌或 Cookie 发生被篡改的可能性，中间件和访问控制规则应构建在服务器端。

### 使用加密进行反序列化

#### 问题 5.5

通过远程代码实现或 API 调用对缺陷对象进行反序列化和应用是不安全反序列化的示例。CSRF（跨站请求伪造）攻击是这类攻击的名称。由于这种攻击，终端用户被迫在合法的 Web 应用上执行非想要的操作。由于黑客无法观察伪造的响应，CSRF 攻击针对状态更改请求。攻击者可以使用社交工程技术（例如通过电子邮件或聊天发送链接）来诱骗受害者执行异常行为。CSRF 可以强制修改状态请求，例如电子邮件 ID 转换和资金转账。对于管理员用户，CSRF 可能会破坏整个 Web 应用。

#### 解决方案

我们必须防止 CSRF 攻击以减少此类黑客行为或攻击。Node.js 中的防伪令牌可以实现这一点。防 CSRF 令牌用于避免一点击攻击，并检查和验证用户请求的有效性。

### HTTP 响应头的执行

#### 问题 5.6

Express 是最广泛使用的 Node.js Web 应用框架之一。然而，Express 在设计时并没有考虑安全性。因此，旧版本的 Express 可能会带来安全风险。

#### 解决方案

为了确保程序的安全，我们必须使用维护和更新的版本。事实上，通过向我们的应用添加额外的安全相关 HTTP 头部，我们可以防止许多不常见的攻击。最流行的框架（如 CORS）可以提高我们 API 的安全性，但应考虑使用 Helmet，它可以添加更多头部来保护我们的项目。

Helmet 可用于保护 Express 和 Node.js 应用。它是一组中间件函数，只需一行代码即可运行以防止跨站脚本和中间人攻击。

### 创建日志和监控系统

#### 问题 5.7

Node.js 的安全还包括日志记录和监控。毕竟，我们的目标是从上保护系统。为此我们需要日志和监控。

#### 解决方案

某些黑客想要禁用我们的程序，这在没有日志的情况下无法发现。然而，监控将帮助我们。数据对于识别暴露和入侵至关重要。应用程序内部发生的一切都会被记录和监控。

### 身份验证应该是强大且彻底

#### 问题 5.8

另一种典型的漏洞是不完整、脆弱或故障的身份验证机制。这可能是因为许多开发者认为它是安全的。

#### 解决方案

最有效的选项之一是使用当前的 OAuth、Firebase Auth 或 Okta。如果我们想使用 Node.js 身份验证解决方案，请注意以下几点：在构造密码时，永远不要使用 MD5；相反使用 Scrypt 或 Bcrypt。确保在用户名或密码错误时不会提示用户，并限制失败的登录尝试。我们还需要会话策略。

### 定期扫描应用漏洞

#### 问题 5.9

在 Node.js 生态系统中，我们可以安装各种库和模块。许多模块在我们的项目中每天都会被使用。因此，存在安全风险。如果我们使用他人编写的代码，我们就无法确定它是安全的。

#### 解决方案

我们必须定期自动扫描漏洞来解决此问题。这有助于找到具有相似缺陷的依赖项。我们还可以利用 NPM 分析进行简单的监控；但是，我们应该考虑使用`Retire.js`、`White Source Renovate`、`OWASP Dependency-Check`、`OSS INDEX`、`Acutine`和`NODEJSSCAN`等工具。

### 使用 Fluid 构建安全补丁流水线

#### 问题 5.10

安全配置漏洞发生在 Web 服务器或应用未受保护或使用不足的安全标准时。由于此缺陷，应用栈的多个方面（应用容器、数据库、服务器等）都是脆弱的。脆弱的流水线是安全配置攻击的常见来源，例如阶段或开发区域的凭据进入了创建。这使得应用暴露为阶段或开发区域设置，导致安全松散。

#### 解决方案

最好的做法是将三个环境（开发、测试和生产环境）保持一致，但使用不同的凭据和访问权限。如果在 Node.js 代码中使用了默认的包设置和用户账户密码，黑客可能会针对弱凭据的登录表单进行暴力字典攻击。另一方面，默认的包设置会为恶意黑客留下漏洞缺口。

## 通用技巧

Node.js 是一个流行的轻量级 JavaScript 框架，允许我们构建复杂的服务器端和客户端。为了充分利用这个应用程序运行时环境，开发者必须像编写其他语言一样编写整洁的 Node.js 代码。

## 查看我们的命名规范

在编写整洁且一致的 Node.js 代码时，从检查如何命名 JavaScript 组件（如类、函数、常量和变量）开始是一个极佳的起点。遵循在 JavaScript 社区中广泛接受的编码标准和规则的风格指南是这里的最佳策略。在为函数和变量命名时使用小驼峰命名法（lowerCamel）。它们的名称应该是具有描述性的，但不应过长。应避免使用单字符变量名和不常见的缩写。

```javascript
// 错误

function set_Price() {

}
```

```javascript
// 正确

function setPrice() {

}
```

类名应使用首字母大写的大驼峰命名法（UpperCamelCase），如下所示。

```javascript
class SomeClassExample {
```

在命名常量时，可以使用整个单词的大写，如下所示：

```javascript
// 错误

function set_Price() {

}
```

# 128 攻克 JavaScript

```javascript
// 正确

function setPrice() {

}
```

我们在声明中使用下划线来区分具有多个名称的常量和变量名。

```javascript
var DAYS_UNTIL_TOMORROW = 1;
```

## 函数应该进行模块化的位置

为每个活动创建一个函数是清理代码杂乱的简单方法。如果函数的名称暗示它执行了多于此的操作，我们应该拆分功能并创建一个新函数。如果我们保持较小的功能部分，我们的代码看起来会更整洁。我们还可以使用主`init()`函数来保存应用程序结构。这允许我们重用例程而无需编写重复代码。执行单一活动的函数也更容易调试或修改，因为它们不需要扫描代码库来查找依赖项，也不需要弄清楚哪个代码块执行了特定操作。

## 正确的注释

注释是 Node.js 代码的重要组成部分，因为它们有助于澄清复杂的章节并解释高级技术。它们定义了某些代码的操作，让其他程序员能够更好地理解。在注释时，避免对无关要点进行多余描述。在创建注释时，一个良好的原则是解释我们“为什么”这样做，而将“如何做”交给代码。

## 调试时，注意上下文

在软件开发中，调试是不可避免的，而且并不总是容易的。在编写 Node.js 时，有很多选择。例如，`console.log`是一个常用的工具，允许我们以简单快速的方式排除问题。

然而，如果我们不清理日志，控制台可能会变成一团糟。我们应该考虑实现生产环境调试。控制台无法无法提供足够的信息来判断活动应用中错误的严重程度。这并不是说我们不应该使用控制台，而是我们应该使用能够提供解决问题所需所有调试信息的工具。使用像`Raygun`这样的调试工具，我们可以发现代码中的问题。

# 代码优化 ■ 129

## 解构

解构赋值是将对象或数组等复杂数据结构拆分为较小部分的极佳技术。它允许我们快速访问数组项和对象属性。

## 不要犯两次同样的错误

最后一点涉及软件开发中著名的 DRY 原则（不要重复），它通过数据归一化和抽象来消除程序模式中的重复。某些强制要求的技巧属于编码风格范畴。

## 回调礼仪

模块应该暴露错误优先的回调接口。它的写法应该是这样的：

```javascript
module.exports = function (dragonName, callback) {

  //在此处处理事务

  var dragon = createdDragon(dragon name);

  // 第一个参数是错误

  // 在这种情况下它是 null，但如果发生错误，

  // 应该在这里提供一个新的 Error 对象。

  return callback(null, dragon);

}
```

## 始终双重检查回调问题

为了进一步理解为什么需要这样做，请从一个在所有可能方面都是坏的示例开始，并修复它。

```javascript
// 这个示例是**损坏的**；我们将尽快修复它：

var fs = require('fs');

function readJSON(filePath, callback) {

  fs.readFile(filePath, function(err, data) {

    callback(JSON.parse(data));

  });

}

readJSON('./package.json', function (err, pkg) { ... }
```

这个`JSON`函数的第一个问题是它从不检查执行期间是否发生了错误。始终留意它们。改进后的版本是：

```javascript
// 这个示例仍然是损坏，但我们正在

// 改进它！

function readJSON(filePath, callback) {

  fs.readFile(filePath, function(err, data) {

    // 在这里检查是否发生了错误

    if (err) {

      // 将错误传递给回调

      // 保留错误

      callback(err);

    }

    // 将结果传递给回调

    callback(null, data);

  })

}
```

## 关于回调的返回

之前的示例中的一个问题是如果发生错误，执行将停止。根据提供的文本重新评估：

```javascript
// 这个示例仍然是损坏，但我们正在努力

// 改进它！

function readJSON(filePath, callback) {

  fs.readFile(filePath, function(err, data) {

    // 在这里检查是否发生了错误

    if (err) {

      // 将错误传递给回调

      // 保留错误

      callback(err);

    }

    // 将结果传递给回调

    callback(null, data);

  })

}
```

# 代码优化 ■ 131

## 仅在同步代码中使用 Try-Catch

我们快成功了！另一个需要考虑的项目是`JSON.parse`。如果`JSON.parse`无法将字符串转换为合适的格式，它会抛出异常。

```javascript
// 这个示例是**可以的**！

function readJSON(filePath, callback) {

  fs.readFile(filePath, function(err, data) {

    var parsedJson;

    // 处理错误

    if (err) {

      return callback(err);

    }

    // 解析 JSON

    try {

      parsedJson = JSON.parse(data);

    } catch (exception) {

      return callback(exception);

    }

    // 一正常

    callback(null, parsedJson);

  })

}
```



##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。尽可能远离

由于 Node 需要大量的回调和高阶函数的使用，绑定特定上下文是困难的。如果我们采用实用的方法，将节省大量的时间和工作。当然，在某些情况下原型更有效，但尽量避免它们。制作一个小模块。

以类 Unix 的方式进行：开发者应该创建由良好接口组成的软件，这样问题就可以被隔离，并在未来版本中修改以适应新功能。不要制造死星；保持基础。一个模块应该只做一件事，并把它做好。

## 代码优化 ■ 133

由程序在程序执行时同时发生，而不会提示程序阻塞并等待结果。异步输入/输出是一个没有回调函数且无法读取未定义属性的功能。

### 处理程序员错误

由于这些问题是 Bug，在应用程序崩溃之前，我们并不知道应用程序处于什么状态。当这种情况发生时，进程控制系统（如 `supervisor` 或 `monit`）会重启应用程序。

## 总结

在本节中，我们查看了 Node.js 如何影响前端工具、HTTP/2 如何增强 Node.js 性能、专门的缓存解决方案，以及提高 Node.js 性能的数据处理方法。然后，我们讨论了如何在 Node.js 项目中使用负载均衡来管理多个连接、有状态和无状态客户端身份验证的区别，以及 WebSockets 如何在客户端和服务器之间提供可靠的连接。现在，我们需要利用 Node.js 的性能特性，创建出消费者会喜欢的应用程序。Node.js 的性能优化是一个庞的话题，有许多领域需要涵盖。一些流行的方法可以帮助我们获得更高的性能结果：

- 更新到 Node.js 的最新稳定版本。
- 可以使用 Node.js 定时器调度任务。
- 应该优先访问局部变量。
- 移除任何不再使用的 `.js` 库。
- 删除任何不再使用的代码行。
- 通过定义良好的执行上下文来避免全局变量。

然而，在实施这些优化技术时，不要忘记 SSL/TLS 和 HTTP/2 等安全实践。由于 Node.js 模块和框架允许应用开发者和工程师设计复杂且独特的系统，它们也让这些系统暴露在许多安全漏洞之中。如果应用开发者跟上最新的 Node.js 安全实践，将能够为用户构建更安全的解决方案。整洁、易懂的代码也有助于为易于维护的程序建立坚实的基础。

## 笔记

- 1. Morgan-npm。
- 2. Node-Bunyan-Trent。

## 总结

- Node.js 与其他框架和工具的使用
- React 结合 React
- Node.js 与 Angular

上一章教了我们代码优化、安全和通用的 Node 建议。现在在本章中，我们将学习关于 Node.js 的职业前景以及可以与 Node.js 一起设计各种应用程序的其他框架。

## NODE.JS 的职业前景

Node.js 是一种软件开发技术，可用于解决服务器和 Web 应用程序的各种问题。它是被最广泛使用和最著名的技术之一。Node.js 是一种开源且免费的编程语言，运行在 Windows、Linux 和 Unix 等多种平台上。

为了更深入地理解这项技术及其重要性，下面详细介绍了 Node.js 的一些细节：

- 使用 Node.js 动态生成网页内容。
- Node.js 也用于服务器创建、打开、读取、写入、删除和关闭文件。

## 136 攻克 JavaScript

- 也可以使用 Node.js 表单数据。
- Node.js 允许我们在数据库中添加、删除和修改。
- Node.js 通过允许我们关注下一个请求，消除了等待需求并简化了流程。
- 单线程和非阻塞编程（两者都是异步编程）都可以在 Node.js 中运行。它具有很高的内存效率。

大多数人从前端开发开始职业，使用 HTML、JavaScript 和 CSS 创建应用程序。为了让功能更强大、方便，必须向项目和 Node 引入额外的技术。其中一种技术就是 JS。应用开发、游戏开发和产品创建都是 Node.js 专家可能的职业路径。

软件开发人员的职位一直需求巨大。所有领域，包括前端开发、UX/UI 开发、服务器管理和后端开发，都需要经验丰富且技能熟练的团队。在软件工程和 Node 提供的职业职位以及收入方面，全栈开发是连接行业的新领域。JavaScript 是一项能够做出重大贡献的技能。在投入大量时间并对该主题获得足够的权威后，人们在加薪、晋升和职业发展方面获得丰厚的回报。

是一些关于 Node.js 的有趣事实，将使我们学习它：

- 持续的需求

Node.js 的流行程度一直在增长。事实上，Node.js 的流行程度已经超过了 Java（目前最流行的编程语言）。

- Node.js 开发的就业机会更多

公司出于各种原因采用 Node.js，包括缩短开发时间、更低的服务器要求和无与伦比的扩展性。LinkedIn 等公司使用它是因为它大大缩短了它们的开发时间，并使 Netflix 的加载时间提高了 70%。Medium、《纽约时报》PayPal 以及科技行业的其他知名公司都在使用 Node.js。初创公司正在追赶这一趋势，将 Node.js 加入到它们的技术栈中。Node.js 的优势主要归功于它的非阻塞事件循环属性，这允许它快速管理大量请求，从而实现更大的扩展性。

- JavaScript 被广泛利用

Node.js 最棒的一点是它与 JavaScript 配合。JavaScript 是创建应用程序最流行、最简单的方法。构建浏览器端通常需要 JavaScript 配合 PHP、Ruby、Python 等其他编程语言。我们可以开始设计。例如，Sails 和 Express 是 Node.js 框架，它们帮助我们在简化开发流程的同时处理背景的复杂性。

- 这有助于快速开发、提高生产力，最关重要的是还有助于无缝测试和调试。它们提供了工具和插件，使原型设计和应用开发变得更容易。Node.js 框架还提高了应用程序的性能和扩展性。

- 要成为全栈开发者，我们必须理解前端和后端。总体来说，随着对 Node.js 需求的增加，Node.js 开发对于新手和经验丰富的开发者来说都是前景前景。

## 与其他框架和工具配合 JS

通过采用包含基础架构、模板引擎和集成库的框架，我们可以使用 Node.js 构建可扩展的、高性能的网站和应用。它们促进并加速了服务器端的开发。Node.js 框架在抽象设计中持有占位符部分。要创建一个完整的 Web 应用程序，我们只需要输入自己的代码。它负责 Web 的其余结构。它们还帮助开发者定义 Web 应用的控制和流。

## 138 攻克 JavaScript

### 使用 NODE.JS 框架的优势是什么？

Node.js 有许多内置功能，如果我们不是专家，可能很难关注这些功能。例如，Sails 和 Express 是 Node.js 框架，它们帮助我们在简化开发流程的同时处理背景的复杂性。快速开发、提高生产力，最关重要的是还有助于无缝测试和调试。它们提供了工具和插件，使原型设计和应用开发变得更容易。Node.js 框架还提高了应用程序的性能和扩展性。

### JS 框架及其类型

- **全栈：** 全栈 MVC 框架为开发者提供了一站式服务。它们提供脚手架、内置模板引擎、WebSocket 支持和核心 UI 库等。全栈 JS 框架可以创建实时、可扩展的 Web 应用。仅使用 JavaScript 控制后端和前端。
- **微框架：** 它们是用于实现特定开发目标的小框架。与全栈框架相比，它们更灵活，提供的配置更多，且不那么具有主观性。
- **Rest API 框架：** 这些是专为构建强大的 API 设计的服务器端框架。在我们的服务器上，我们可以创建一个简单的 REST API 来处理 CRUD（增删改查）查询。

## 使用 NODE.JS 开发 Web 应用程序的框架

有几个框架，其中包括：

- **Express.JS：** Express.js 用于创建后端服务，如 Web socket、Web API 和其他互联网服务。它是免费的

摘要 ■ 139

基于 MIT 许可证分发的开源软件，它基于 Sinatra 微框架。

Express.JS 框架具有以下重要特性：

- Express 是一个 Node.js 层，它在 Node.js 之上提供了在线应用开发工具，如基础路由、中间件、模板引擎和静态文件服务。
- 它非常简单，且不会对 Node.js 性能造成压力。它被用于创建现代的在线应用和 Web API。
- 对于代码分段，Express 利用了模型-视图-控制器（MVC）结构。
- 灵活且能够适应个人需求。
- 设置了中间件来处理 HTTP 请求和响应。
- 这是一个尖端的对象关系映射（ORM）程序，它使我们能够执行高昂的 CRUD 操作。
- Uber、PayPal、IBM 等更多公司使用 Express.js 进行服务器开发。

**Meteor**：这是一个用于创建和部署 JavaScript Web、桌面和移动端应用的免费开源框架。该框架用于 Node.js 的快速原型设计。

Meteor 的其他优势包括：

- 我们可以创建一套可在所有平台（包括 Web、桌面、iOS 和 Android）运行的单一源代码。
- 关系型数据库 MongoDB 可以与 Meteor 配合使用。
- Js 是一种有助于数据同步的编程语言。
- Meteor 有一个名为 Live Reload（实时加载）的内置功能，允许我们无需重新编译浏览器页面即可看到代码逻辑。
- Meteor 有一个开发响应式用户界面的平台。
- 应用程序持续使用单一语言，这提高了一致性。
- 网页可以实时更新。

# 140 ■ 征服 JavaScript

- Sails 是一个构建在 Node JS 之上的具有 MVC 设计的 JavaScript 框架。它是以简单方式设计企业级应用和在线 API 的最佳选择。更多的数据请求、自动生成 JavaScript 对象表示（JSON）请求以及额外的 HTTP 能力都是 Sails 升级版 Rails 版本的 MVC 软件设计的一部分。
- Waterline 是 Sails 包含的一个强力 ORM，它为任何公共数据库提供了简单的数据访问层。
- Sails 拥有蓝图（blueprints）和脚手架（scaffolds），我们可以利用它们无需编写代码即可快速启动应用的后端。
- 我们 Sails 应用中的每个路由都支持 Web sockets，并且它们将翻译传入的 socket 消息。
- Nest.js：Nest.js 是最具前瞻性的 Node js 框架之一，用于创建动态且可扩展的企业和业务应用。凭借大量的库选择，它为我们这样的开发者提供了完全的灵活性。Nest 的主要编程语言是进阶 JavaScript 和 TypeScript。
- 由于启用了 TypeScript，Nest 有了保障。Js 具有健壮的类型系统并遵循优秀的编码规范。
- 它是一个多范式框架，实现了 OOP（面向对象编程）、FP（函数式编程）和 FRP（函数式反应编程）等原则。
- 它自带后端生产力加速器。它提供了一个高度可扩展的生态系统，允许创建全服务器端的应用程序。
- Nest CLI 是一个强大的工具，允许我们为 Web 应用创建多个预构建的功能。
- Koa：Express.js 团队创建了 Koa，这是一个高度扩展的 Node.js 最小 Web 框架。一个 Koa Web 应用类似于包含一组中间件函数的对象。当用户提出请求时，Koa 将这些函数放在栈中并执行它们。
- 即使在最低层的中间件级别，高层 JavaScript 也提高了兼容性和健壮性。它提供了内容协商、缓存新鲜度、代理支持、弹出窗口和重定向功能。它提供了一个中间件框架，中间件可以在不集成到核心的情况下进行扩展，从而减少内存占用。最关键的一点是，我们可以工作而无需等待回调。

- Hapi：得益于输入验证，它是最安全、简单的 Node.js 框架之一。Hapi.js 框架具有一些主要特性，包括：
  - 它的架构基于插件的。
  - 拥有强大的生态系统和大量的安全默认设置。
  - Paypal Hapi 框架通过快速执行 JavaScript 模板引擎为客户交付动态内容，该引擎被迪士尼等大型企业使用。
  - 它非常具有扩展性，并支持许多第三方插件。这些插件使得创建可以处理数千人的实时聊天程序成为可能。
  - 它便于为开发者创建详细文档。

- Derby：这是一个用于 Node.js 在线应用开发的全栈框架。它以支持“Racer 引擎”而闻名，允许许多用户实时处理同一数据。此 Node 框架使用 Share DB 的操作转换（Operational Transformation）服务，利用复杂的冲突解决算法进行离线访问、实时更新和快速交互。
  - Derby.js 将服务器和客户端浏览器结合，允许在单个文件中编写后端和前端代码。
  - Derby 使用模板进行数据渲染；因此，不需要在服务器端创建昂贵的 DOM 实现。
  - Derby.js 在服务器上生成模板的 HTML 输出，以加快页面加载速度。
- 它提供全面的搜索引擎优化（SEO）辅助。
- Derby.JS 在客户端浏览器上使用快速、原生的 DOM 操作技术进行渲染。

# 142 征服 JavaScript

Loopback

LoopBack 是一个 Node.js 和 TypeScript API MVC 框架，允许我们快速开发由后端系统组成的 API 和微服务。Loopback 以无缝的方式将其 API 连接到数据源。

- 内置的 API 浏览器和内置客户端，允许我们动态地探索它。
- 使用 MySQL、MongoDB、Oracle 从模式创建数据模型。
- 它包含一个基础的 CLI 用于快速原型设计。
- 它支持 Android、iOS 和 Web。
- 可以使用附加组件进行文件管理、第三方登录等。

Adonis

Adonis 是一个 JavaScript MVC 框架，支持 Express、Koa 和 MEAN 技术栈。基于 PHP 的 Laravel 对它有很大影响，它们之间有很多相似之处。

- Adonis.js 提供了一个包含许多标准功能的健壮环境。
- 它构建在依赖注入和 IOC（反转控制）之上。
- 路由组、基于子域的路由和资源都由 Adonis 的路由层支持。

# 征服 JavaScript

- 短信应用
- 聊天应用
- 社交媒体应用
- 虚拟世界中的模拟器
- 多人游戏
- 协作软件
- 最小可行性产品 (MVP)

## NODE.JS 与 REACT 兼容吗？

Node.js 允许我们在后端创建可扩展且快速的 RESTful API。相比之下，React 是用于构建交互式用户界面的前端框架。我们可以结合这两个工具快速创建复杂且可扩展的 Web 应用。

Node 是托管和运行 React Web 服务器最广泛的平台。毕竟，Node 包管理器 (NPM) CLI 允许我们使用 NPM 安装任何包。此外，Node 可以使用 Webpack 及其他插件将 React 应用程序编译成单个文件。

## 为什么在 Web 应用开发中要同时使用 NODE.JS 和 REACT？

对于 Web 应用开发，有独特的理由来利用 Node.js 和 React 这一“王牌组合”。以下是几个例子：

- 扩展能力：可以构建动态、海量、数据驱动的互联网应用，这些应用在多个设备上都有响应式。在处理重大项目和维护网站性能时，具有可扩展性将非常有优势。

- MERN 栈二号：MongoDB、Express、React 和 Node.js 成了 MERN 栈。没有比这些框架更好的组合能带给我们独特的维度了。通过 React.js，MERN 栈支持 Node.js。因此，我们可以使用 Node 和 React 的组合创建 Web 应用。

## 总结 ■ 145

- 基于 JSON 的 API：由于 React.js 的高代码重用率和快速代码共享的能力，为 Web 开发创建 JSON API 非常简单。而 Node.js 能够胜任这项任务。

- 基于 JSON 的 API：由于 React.js 的高代码重用率和快速代码共享的能力，为 Web 开发创建 JSON API 非常简单。这是 Node.js 能够做到的。

- 实时数据：由于我们的业务应用需要持续的服务器连接，如果它处理实时数据管理或想要构建数据流应用，我们应该利用 Node.js。

- 快速进展：通过将 React 和 Node 结合用于 Web 开发，我们可以获得极高的投资回报并节省资金和时间。毕竟，这些技术的结合为创建加载快速、易于维护的网站提供了极佳的框架。

- 特殊领域；单页应用：我们的公司是否需要具有异步数据加载的单页应用？如果是，我们应该选择 React 配 Node 作为后端，因为它允许我们使用回调函数创建一个轻量级的后端模型。

- 前后端使用相同语言：开发者通过结合 Node 和 React，可以避免学习 Python 或 Ruby 等困难的后端语言。他们可以使用 Node 编写服务端代码，使用 React 编写前端代码，而无需切换框架或编程语言。

- 服务器流量很大：当开发者进行 Web 开发时，Node.js 和 React 的组合可能有助于平衡服务器请求和负载。

- 进程管理：React 和 Node 结合提供了一个组织良好的 Web 开发流程。毕竟，这些技术是可扩展、高效且快速的。如果我们一起使用它们，它们可以帮助我们创建高功能的网站。

- JavaScript 使用得更频繁：对于前端和后端编码，Node 配合 React 允许我们发挥 JavaScript 的全部威力。由于我们可以使用单一语言处理一切，这在我们在开发网站或 Web 应用时提供了更多的灵活性和便利性。

# 征服 JavaScript

## 如何使用 NODE.JS 创建 ANGULAR 应用程序

我们可以通过多种方法创建 Angular 应用并将其部署到生产环境。一种方法是使用 Node.js 或 Java 创建 Angular，另一种方法是创建 Angular 并使用 NGINX Web 服务器交付静态内容。使用 Node.js 时，我们还必须处理服务器代码；例如，我们必须使用 `node` 来加载 `index.html` 页面。

### 简介

Angular 是开发在线应用的 JavaScript 框架，它不需要浏览器打开。我们需要一个系统在浏览器中同时加载 Angular 的 `index.html`（单页）以及它所有的依赖项（CSS 和 JS 文件）。此示例中的 Web 服务器是 `node`，它加载 Angular 资源并从 Angular 应用获取 API。

### 前提条件

对于此，有几个前提条件。我们需要在笔记本电脑上安装 node.js，并理解 HTTP 的工作原理。如果我们想在笔记本电脑上练习并运行它，就需要这些工具。

- `ngx-bootstrap`
- Node.js
- Angularscript
- Typescript
- VSCode

### 项目练习

这是一个小型项目，展示了如何使用 Node.js 创建和运行 Angular 应用程序。我们有一个简单的软件，允许我们添加人员、在侧边计数，并随时检索他们。

当我们添加用户时，我们会向 node.js 服务器发送 API 调用以存储用户，并在检索他们时从服务器获取相同的数据。在下方的视频中，我们可以查看网络调用。

该项目的 GitHub 页面可以在此处找到。我们可以在自己的机器上克隆并运行它。



// clone the project

`https://github.com/bbachi/angular-Node.js-example.git`

```
// install and start the project
npm install
npm start
```

此项目只需要少量 `Node.js`。如果你是 `Node.js` 的新手，不要担心；这段简要描述将让我们上手此项目。如果我们已经熟悉 `Node.js`，可以跳过此节。对于服务端应用，`Node.js` 是一个异步事件驱动的 `JavaScript` 运行时环境。`Node.js` 的最新版本是 12，我们可以从此链接下载。我们可以下载 `Node.js` 包并安装它。`Node.js` 版本可以通过此命令来确定。

```
var x = 10;
var y = 20;
var z = x + y;
console.log(z);
```

## 开发阶段

## Node 的 API

在服务器上，我们使用 `express` 和 `nodemon`。`Express` 是一个快速、无意见且简单的 `Node.js` Web 框架，而 `nodemon` 是一个在文件变化时刷新我们 API 的库。让我们安装这两个依赖。将此作为开发依赖安装，因为 `nodemon` 仅用于开发。

```
npm install express --save
npm install nodemon --save-dev
```

这是所有的内容。`Node.js` API 的 JSON

```json
{
  "name": "angular-Node.js-example",
  "version": "1.0.0",
  "description": "node server",
  "main": "index.js",
  "scripts": {
    "dev": "nodemon index.js 3080",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/bbachi/angular-Node.js-example.git"
  },
  "author": "Bhargav Bachaina",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/bbachi/angular-Node.js-example/issues"
  },
  "homepage": "https://github.com/bbachi/angular-Node.js-example#readme",
  "dependencies": {
    "express": "^4.17.1"
  },
  "devDependencies": {
    "nodemon": "^2.0.2"
  }
}
```

## 总结 ■ 149

导入 `express` 并定义两个路由：`/api/users` 和 `/api/user`，以及一个监听在 3080 端口的服务器。可以在此处找到 `server.js` 文件。为了处理 HTTP 请求对象中的数据，我们利用了 `body-parser`。

```javascript
const express = require('express');
const app = express()
const bodyParser = require("body-parser");
port = 3080;
```

```javascript
const users = [];
```

```javascript
app.use(bodyParser.json());
```

```javascript
app.get('/api/users', (req, res) => {
  res.json(users)
});
```

```javascript
app.post('/api/user', (req, res) => {
  const user = req.body.user;
  users.push(user);
  res.json("user added")
});
```

```javascript
app.get('/', (req, res) => {
  res.send('App Works !!!!')
});
```

```javascript
app.listen(port, () => {
  console.log(`Server listening on the port: ${port}`);
});
```

当我们使用命令 `npm run demand` 启动 `Node.js` API 时，无论修改哪个文件，它都会自动更新。

## ANGULAR 应用

`Node.js` API 现在可以通过 3080 端口访问。现在是时候查看一下 `Angular` 应用了。`my-app` 文件夹包含了完整的 `Angular` 应用。通过命令 `ng new my-app`，我们可以构建一个新应用。我不会在这里发布所有文件；相反，我们可以在上面的 `Github` 站点或此处查看所有它们。

## 攻克 JavaScript

让我们来看一些关键文件。这是一个使用 node API 的服务文件。

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Injectable({
  providedIn: 'root'
})
export class AppService {
  constructor(private http: HttpClient) { }
  rootURL = '/api';
  getUsers() {
    return this.http.get(this.rootURL + '/users');
  }
  addUser(user: any) {
    return this.http.post(this.rootURL + '/user/', {user});
  }
}
```

订阅这些请求并从 API 获取数据的应用组件如下代码所示：

```typescript
import { Component, OnDestroy } from '@angular/core';
import { FormGroup, FormControl, Validators } from '@angular/forms';
import { AppService } from './app.service';
import { takeUntil } from 'rxjs/operators';
import { Subject } from 'rxjs';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
```

## 总结 ■ 151

```typescript
export class AppComponent implements OnDestroy {
  constructor(private appService: AppService) {}
  title = 'angular-Node.js-example';
  userForm = new FormGroup({
    firstName: new FormControl('', Validators.required),
    lastName: new FormControl('', Validators.required),
    email: new FormControl('', Validators.required)
  });
  users: any[] = [];
  userCount = 0;
  destroy$: Subject<boolean> = new Subject<boolean>();
  onSubmit() {
    this.appService.addUser(this.userForm.value);
    pipe(takeUntil(this.destroy$)).subscribe(data => {
      console.log('message:::', data);
      this.userCount = this.userCount + 1;
      console.log(this.userCount);
      this.userForm.reset();
    });
  }
  getAllUsers() {
    this.appService.getUsers().pipe(takeUntil(this.destroy$)).subscribe((users: any[]) => {
      this.users = users;
    });
  }
  ngOnDestroy() {
    this.destroy$.next(true);
    this.destroy$.unsubscribe();
  }
}
```

## 152 攻克 JavaScript

### Angular 和 Node API 的协同工作

在开发期间，`Angular` 应用运行在 4200 端口，由 `webpack` 开发服务器支持，3080 端口上由 `Node.js` API 支持。

这两者应该以某种方式进行交互。所有的 API 调用都可以被代理到 `Node.js` API。`Angular` 内置了代理技术。首先，我们必须定义位于 `my-app` 文件夹中的 `proxy.conf.json`。

```json
{
  "api": {
    "target": "http://localhost:3080",
    "secure": false
  }
}
```

如果我们检查该文件，我们会注意到所有以 `/api` 开头的路径都将重定向到 `http://localhost:3080`，这是 `Node.js` API 运行的地方。随后必须在 `angular.json` 的 `serve` 部分下定义 `proxyConfig` 键。

```bash
// Node.js API (终端 1)
npm run dev
// Angular app (终端 2)
npm start
```



### 如何创建一个生产就绪的项目

在`webpack`开发服务器的支持下，`Angular`应用运行在`4200`端口。当在生产环境中运行时，情况并非如此。我们必须创建`Angular`项目并使用`node`服务器。

## 156 参考文献

- 17. 安装 Node.js 的五种方法 https://www.nodejsdesignpatterns.com/blog/5-ways-to-install-node-js/，访问于 2022 年 7 月 17 日。
- 18. Node.js 概览 -://en.wikipedia.org/wiki/Node.js，访问于 2022 年 7 月 17 日。
- 19. 最新 LTS 版本: 18.14.0 - https://nodejs.org/en/download/，访问于 2022 年 7 月 17 日。
- 20. Node.js 与浏览器的区别 https://nodejs.org/en/learn/differences-between-nodejs-and-the-browser/，访问于 2022 年 7 月 17 日。
- 21. Node.js 是用于前端还是后端？ - https://www.simplelearn.com/tutorials/nodejs-tutorial/nodejs-backend#:text=Frontend%20%20Backend..:as,%20with%20as%2020backend, 访问于 2022 年 7 月 18 日。
- 22. Anna Dbiua-Node.js 的用途？ - https://relevant.software/blog/why-and-to-use-node#:text=Real-time%20applications,users%20at%20the%20same%20time, 访问于 2022 年 7 月 18 日。
- 23. MVC 框架 - 简介 https://www.tutorialspoint.com/mvc_framework/mvc_framework_introduction.html，访问于 2022 年 7 月 18 日。
- 24. 启示中的四个框架 https://www.toptal.com/nodejs/nodejs-frameworks-comparison，访问于 2022 年 7 月 18 日。
- 25. Kristopher Sandoval - 构建 Web API 的 Node.js 框架 https://nordicaps.com/13-node-frameworks-to-build-web-apis/，访问于 2022 年 7 月 18 日。
- 26. 什么是 Google 云平台 (GCP)？ https://www.edureka.com/blog/what-is-google-cloud-platform/，访问于 2022 年 7 月 18 日。
- 27. Shailendra Chaura - 什么是 Microsoft Azure? https://www.dotnetneticks.com/learn/azure/getting-started-with-microsoft-azure-platform，访问于 2022 年 7 月 18 日。
- 28. Shyamli Jha - 什么是 Microsoft Azure：工作原理与服务 https://www.simplelearn.com/tutorials/azure-tutorial/what-is-azure，访问于 2022 年 7 月 19 日。
- 29. Red Hat OpenShift Online https://access.redhat.com/products/openshift-online-red-hat，访问于 2022 年 7 月 19 日。
- 30. JavaScript 引擎 https://nodejs.org/en/learn/the-v8-javascript-engine/，访问于 2022 年 7 月 19 日。
- 31. Mahipal Nella - 为什么为 IoT 应用选择 NodeJS https://www.decipherzone.com/blog-detail-nodejs-for-iot-applications#:text=The%20%preliminary%20reason%20for%20NodeJS.machine%20code%20with%20faster%20execution, 访问于 2022 年 7 月 19 日。
- 32. Andeep Panda - 让你的 Node.js Web 应用更快的技巧 https://www.sitepoint.com/10-tips-make-node-js-web-app-faster/，访问于 2022 年 7 月 19 日。
- 33. Roshan Kumar - 为物联网系统选择合适数据库的步骤 https://thenewstack.com/4-steps-to-select-the-right-database-for-your-internet-of-things-system/，访问于 2022 年 7 月 19 日。
- 34. Traci Ruether – 什么是 CDN 以及为什么它对直播至关重要？https://www.wowza.com/blog/cdn-live-streaming，访问于 2022 年 7 月 19 日。
- 35. 为什么 Node.js 是单线程的？https://www.quora.com/Why-is-Node-js-single-threaded-is-it-a-constraint-of-the-V8-engine-of-the-JavaScript-language-itself，访问于 2022 年 7 月 19 日。
- 36. 为什么在 IoT 应用中使用 Node.js 开发？https://evontech.com/component/easyblog/use-node-js-development-for-iot-applications-top-reasons.html?item=159，访问于 2022 年 7 月 19 日。
- 37. Sandeep Panda – 让你的 Node.js Web 应用更快 https://www.sitepoint.com/10-tips-make-node-js-web-app-faster/，访问于 2022 年 7 月 19 日。
- 38. 使用 Node.js 构建视频流服务器？https://blog.logrocket.com/build-video-streaming-server/，访问于 2022 年 7 月 19 日。
- 39. Max Wilber – 针对直播活动的私有平台 https://www.dacast.com/blog/7-live-streaming-solutions-for-private-events/，访问于 2022 年 7 月 20 日。
- 40. Node.js 事件循环 https://www.geeksforgeeks.org/node-js-event-loop/，访问于 2022 年 7 月 20 日。
- 41. Ben Lutkevich – CDN（内容分发网络）https://www.techtar.com/search-networking/definition/CDN-content-delivery-network，访问于 2022 年 7 月 20 日。
- 42. 开源安全详解 https://snyk.io/series/open-source-security/，访问于 2022 年 7 月 20 日。
- 43. Hardik Shah – 如何制作流应用：功能、技术栈与成本分析 https://www.simform.com/blog/how-to-make-a-streaming-app/，访问于 2022 年 7 月 20 日。
- 44. 如何成为全栈开发者 https://bootcamp.cnn.com/edu/blog/how-to-become-full-stack-developer/，访问于 2022 年 7 月 20 日。
- 45. 使用 Node.js 和 Express.js 构建简单的 HTTP/2 服务器 https://webapp.com/http2-node/，访问于 2022 年 7 月 20 日。
- 46. Oskar Petr – 如何使用 Node.js 创建现代 Angular 应用 https://javascript.info/how-to-create-your-first-angular-app-with-node-js-982b8cf61a8c5fd,访问于 2022 年 7 月 20 日。
- 47. 为 Web 开发选择 Node.js 的五个理由 https://edwise.medium.com/5-reasons-to-choose-node-js-for-web-development-74ebd26,访问于 2022 年 7 月 21 日。
- 48. WebSocket API https://developers.mozilla.org/en-US/docs/Web/API/WebSockets_API，访问于 2022 年 7 月 21 日。
- 49. Mateusz Pulsik – Socket.io 教程：Web 开发中的实时通信 https://tsh.io/socket-io-tutorial-real-time-communication/，访问于 2022 年 7 月 21 日。
- 50. Martin Fietkiewicz – WebSockets vs HTTP：优劣比较 https://ably.com/topic/websockets-vs-http，访问于 2022 年 7 月 21 日。

## 索引

### A
- 访问控制 (Access control), 123–124
- Adonis.js, 142–143
- 使用 node.js 框架的优势 (Advantages of utilizing node.js), 138
- 聚合日志 (Aggregated logs), 110
- Amazon Cloudfront, 61
- Amazon DynamoDB, 88
- Amazon Web Services (AWS), 26–27
- Angular 应用, 149
- Node.js 的 API, 148
- 与 Node APIs 协同工作, 152
- 生产就绪项目 (production-ready project), 152–153
- 应用监控 (Application monitoring), 109
- 应用开发 (Application development), 35, 55, 83
- 使用 node.js 构建应用 (building application with node.js), 36
- 身份验证 (Authentication), 125–126
- node.js 存档 (Archive of node.js), 7
- 异步 (async), 99
- 异步编码 (Asynchronous coding), 20–21, 116–117
- 异步模式 (Asynchronous fashion), iterator, 66–68
- 异步函数 (Asynchronous functions), 19–20
- 异步模型 (Asynchronous model), 17–19
- 异步 (Asynchronous), 132–133
- 异步模式 (Async patterns), 有效使用, 132
- 小模块 (little module), 制作, 131–132
- 仅使用同步代码 (sync code, using only try-catch), 131
- node.js 职业项目 (Career projects of node.js), 135
- node.js 的需求 (demand for node.js), 136
- 成为全栈开发者 (full-stack developer, becoming), 137
- JavaScript, 137
- node.js 开发中的机会 (job opportunities in node.js development), 136–137
- 薪资范围 (salary packages), attractive, 137
- CDNs, 见 内容分发网络 (Content distribution networks)
- 特性 (Characteristics), 识别, 57
- 基础特性 (basic characteristics), 57–58
- 可选额外内容 (optional extras), 58
- 聊天应用 (Chat applications), 24
- 聊天室应用和 Socket.io 教程, 43

### C
- 缓存获取 (Cache’s get), 113
- 缓存 (Caching), 112–113
- 优势 (advantages of), 10
- 回调规范 (Callback etiquette), 129
- 回调地狱 (Callback hell), 12, 22, 97
- 回调 (Callbacks), 20–23, 129
- 缓存的优势 (caching, advantages of), 10
- 社区支持 (community support), 大规模且活跃
- 卓越结果 (exceptional results, delivering), 10
- 灵活性 (flexibility), 11
- 全栈 node 的优势 (full-stack js node's advantages), 10
- 长度处理 (handling with length of node), 11
- 自己的应用 (own applications, allowing to build), 11
- 可扩展性和 node.js (scalability and node.js), 9
- 简单理解 (simple to comprehend), 9
- 作为单编程语言的 node.js (single programming language, node.js as), 10
- RTMP (实时消息协议), 59–60
- WebRTC, 60
- 测试与维护 (testing and upkeep), 63
- 视频端点 (video endpoint), 76–78
- 视频游戏 (video games, streams for), 64
- WebSocket API, 37

### D
- 大数据和 IoT 项目 (Big data and IoT projects), 88–89
- 布尔值 (Boolean value), 71
- 浏览器 (Browser, node.js), 16–17
- node.js 中的“缓冲区”（Buffer” in node.js), 4
- 错误 (Bugs), 132
- Bunyan, 121
- 开发与设计 (development and design), 62–63
- 物联网 (IoT), node.js 的优势, 84
- node 提供的安全性 (security provided by node), 85
- 在 node.js 中开发 IoT (developing IoT in node.js), 86–87
- IoT 项目的数据工作 (data work for IoT projects), 88–89
- 地理索引 (geospatial indexes in), 97–103
- 为 IoT 选择正确的数据库 (picking the correct database for IoT), 87–88
- 作为强大快速的编程语言 node.js (power and quick programming language, node.js as), 85
- 项目代码 (project’s code, working with), 89
- 项目架构 (project’s architecture), 89
- 作为可扩展且资源高效的编程语言 node.js (scalable and resource-efficient programming language, node.js as), 85
- 模式设计 (schema’s design), 92–97
- 服务器端身份验证 (server-side authentication), 86
- 物联网 (IoT) 解决方案, node js, 83–84
- 市场表现 (market performing), 56
- 电竞流应用 (eSports streaming apps), 57
- 音乐流应用 (music streaming apps), 56–57
- 带有流的 node APIs (node APIs with streams), 73–75
- 范围 (range, 识别), 78
- APIs, 86, 108, 148
- 应用的劣势 (disadvantages of the application), 75
- 异步模式中的迭代器 (asynchronous fashion, iterator in), 66–68
- WebSockets, 36
- WebSocket 的定义 (WebSockets, definition of), 36
- WebSocket 的工作 (WebSockets, working of), 36
- 特性 (characteristics, 识别), 57
- 基础特性 (basic characteristics), 57–58
- 可选额外内容 (optional extras), 58
- 内容分发网络 (Content distribution networks), 61
- 数据库与托管 (database and hosting), 62–63
- 读取模式 (reading modes), 68–70

# 索引 ■ 161

- 公民警察应用, 91
- 客户端身份认证, 115
- 代码优化, 105
- 异步编码, 116–117
- 回调有效性, 129
- 客户端身份认证, 115
- 正确的注释方式, 128
- 数据库/优化, 改进,
  - 基础策略, 118
  - LIMIT, 118–119
  - 使用离峰时间, 120
  - SELECT 语句, 118
  - WHERE 子句, 118
  - 使用通配符, 119–120
- 调试, 128–129
- 解构赋值, 129
- 双重检查回调以发现问题, 129
- 异步模式的有效利用, 132
- 回调的返回值, 130
- 小模块, 131–132
- 同步代码，仅在 try-catch 中使用，131
- 加密指南, 122
- 错误纠正, 132
- 异步性, 132–137
- 操作中的错误, 121
- 编程中的错误, 123–133
- 运行错误的处理, 132
- 程序员故障的处理, 133
- 事件循环, 107
- 事件循环与 node.js, 性能, 107
- 缓存, 112–113
- 数据管理技术的改进, 111
- HTTP/2 和 SSL/TLS, 111–112
- 图像, 111
- 大规模分布式系统的克隆, 109
- 让 node.js 运行得更快, 110
- CSS 的模块和预处理器, 111
- 创建性能测试分析概览, 108
- 运行测试, 110
- 设置、运行和分析性能测试, 107–108
- 设置 node.js 性能测试环境, 110
- 任务运行器和模块包, 110–111
- 前端工具, 110
- 函数, 128
- 负载均衡, 114–115
- 保持代码权重与紧凑, 115–116
- 命名规范, 127–128
- 并行性, 121
- 查询增强, 117
- 程序模式中的请求方法, 129
- 脚本的追踪与日志, 120
- Bunyan, 121
- Morgan, 121
- Winston, 120–121
- node.js 的安全问题与建议, 122
- 身份认证, 125–126
- 使用 fluid 构建安全补丁的流水线, 126–127
- 数据泄露, 123
- 使用加密进行反序列化, 124
- HTTP 响应头, 124–125
- 创建日志和监控系统, 125
- 请求实现访问控制, 123–124
- 定期扫描应用漏洞, 126
- 安全限制的利用, 123
- XSS 攻击，通过验证用户输入进行限制, 122–123
- node.js 的安全问题, 122
- node.js 的特殊性, 106
- 内存泄漏的检测, 106–107
- 执行到完成的单线程行为, 106
- 同步编码, 116, 117
- WebSockets, 有效的服务器通信, 116

# 162 索引

- 执行重计算任务时的性能下降, 122
- 社区支持, 10
- 紧凑代码, 115–116
- Connect(), 74
- connect-redis, 100
- Console.log(), 120
- 用 Node.js 编写的控制应用程序, 5
- Node.js 下载, 7
- 软件开发的 DRY 原则, 129

# E

- ECMAScript, 13, 30
- 生态系统，变化, 16–37
- 使用加密进行反序列化, 124
- 加密指南, 122
- 结束 node.js 程序, 32–33
- node.js 的环境搭建, 6
- node.js 存档, 7
- 本地环境的设置, 6
- node.js 的运行时, 7
- 文本编辑器, 7
- 内容分发网络 (CDN), 112
- 内容分发网络 (CDNs), 61
- 数据库与托管, 62
- 核心概念, 12–13
- GradeDB, 88
- CreateReadStream(), 74
- CreateWriteStream(), 74
- CSS 的模块和预处理器, 111

- 错误纠正, 122
- 数据库性能/优化的改进策略, 118
  - LIMIT, 118–119
  - SELECT 语句, 118
  - 使用离峰时间运行查询, 120
  - WHERE 子句, 118
  - 使用通配符, 119–120
- 数据泄露, 123
- 数据管理技术的改进, 113
  - 异步, 132–133
  - 编程中的错误, 132–133
  - 运行错误的处理, 132
  - 操作中的错误, 132
  - 程序员故障的处理, 133
- node.js 提供的安全, 85
- 数据类型, 2
- 调试, 128–129
- node.js 的需求, 136
- Dependency.js, 141–142
- 使用加密反序列化, 124
- 解构赋值, 129
- DigitalOcean, 29
- node.js 的缺点, 11
- API 不稳定性, 11
- 代码维护的难度, 12
- 优化的代码, 11–12
- 视频流应用, 57
- EventEmitter, 20, 42
- 异步编码, 20–21
- 事件循环, 22, 107
- 事件循环与 node.js, 性能, 107
- 缓存, 112–113
- CSS 的模块和预处理器, 111
- 数据管理技术的改进, 113
- 前端工具, 110
- HTTP/2 和 SSL/TLS, 111–112
- 图像, 111
- 大规模分布式系统的克隆, 109
- 让 node.js 运行得更快, 110
- 创建性能测试概览, 186
- 运行测试, 110
- 设置、运行和分析性能测试, 107–108
- 设置 node.js 性能测试环境, 110
- 任务运行器和模块包, 110–111

# 163 索引

- Hapi.js 框架, 26, 141
- 请求头, 79–81
- 事件队列, 22
- 事件发射器, 20
- 异步编码, 20–21
- node.js 作为卓越的技术伙伴, 8–9
- node.js 交付, 10
- Express, 44
- Express.js, 25, 138–139, 148
- 外部资源, 22
- 安装 node.js, 14
- JavaScript 知识, 15–16
- HLS, 见 视频流
- 托管服务选择, 26
- Amazon Web Services (AWS), 26–27
- DigitalOcean, 29
- Google Cloud Platform (GCP), 27
- Heroku, 27
- Microsoft Azure, 28
- RedHat OpenShift Online, 28

- node.js 的特性, 8
- 过滤, 113
- node.js 的灵活性, 11
- node.js 框架, 25
- 模型视图控制器 (MVC) 框架, 25
- REST API 框架, 25
- Express.js, 25
- Hapi.js, 26
- Koa.js, 25–26
- Socket.io, 26
- HTTP.request(), 74
- HTTP/2 和 SSL/TLS, 111–112
- HTTP 头, 111
- 视频流 (HLS), 59
- HTTP 响应头, 124–125
- HTTP 与 WebSockets, 43
- 前端工具, 110
- 前端/后端框架, 23–24
- 前端部分, 45–53
- 成为全栈开发者, 137
- 全栈 node.js 优势, 110
- 功能性, 64
- Node.js 中的函数, 3–4–127
- 图像, 111
- 应用内聊天, 58
- index.js 文件, 44
- InfluxDB, 88
- 基础设施数据, 109
- 安装 node.js, 14
- 内部通信, 41–49
- 物联网 (IoT), node.js 的优势, 84
- 使用 node.js 创建 API, 86
- 代码教程, 91
- Schema 设计, 92–97
- node.js 提供的安全, 85
- 在 node.js 中开发 IoT 项目, 86–87
- 基于 node.js 的 IoT 应用, 90

- GCP, 见 Google Cloud Platform
- GeoJSON 对象, 97
- MongoDB 中的地理空间索引, 97–103
- GitHub 页面, 146
- GitHub wiki 页面, 28
- Google Cloud Platform (GCP), 27
- Google Kubernetes Engine, 27
- GraphQL, 114
- Uber, 90
- node.js 集成 IoT 协议, 84–85

# 164 索引

- 让大数据适用于 IoT 项目, 88–89
- LoopBack, 142
- 弱类型, 3
- 小驼峰命名, 127
- MongoDB 中的地理空间索引, 97–103
- 为 IoT 选择最佳数据库, 87–88
- 强大且快速的语言, node.js, 85
- 项目代码的使用, 89
- 项目的未来架构, 89
- 实时 IoT 分析, 89–90
- 服务端架构, 86
- node.js 作为 IoT 解决方案, 83–84
- Morgan, 121
- MPEG-DASH, 59
- MQTT.js, 85
- 多语言支持, 58
- 多种视频分辨率选项, 84
- 多路复用, 111
- 流应用, 56–57
- MVC 框架, 25

JavaScript, 1, 9, 10, 13, 16, 23
- 知识, 15
- JavaScript Object Notation (JSON), 140
- node.js 开发工作机会, 136–137
- JSON, 见 JavaScript Object Notation

- 命名规范, 127–128
- Nest.js, 140
- Net.Socket, 73
- Netscape LiveWire, 13
- Netscape Navigator browser, 77
- Nginx, 114
- Node.js Architecture, 22
- Node APIs with stream, 73–75
- NodeJS, 91–92
- Nodemon, 44
- Node-packaged modules (NPM), 85
- Node-RED, 85
- Node-set, 113
- 非阻塞 I/O 操作, 21

# 索引 165

- 对象数据库，24
- 离峰时间运行查询，120
- 在线视频流，其相关协议，59
- 优化，113
- OTT 服务，跨越传输 (Over-the-top) 服务
- 跨越传输 (OTT) 服务，55
- node.js 允许构建的自有应用，11
- 可读流 (Readable stream)，68–69, 70
- readFileSync(),117
- 读取模式，68–70
- readJSON 函数，130
- 实时 IoT 分析，89–90
- 实时消息传输协议 (RTMP)，59–60
- RedHatShift Online，28
- Redis 缓存，113
- 程序模式中的重复消除，129
- 将 node.js 作为资源高效的编程语言，85
- REST APIs 的框架，25
- Expression.js，25
- Hapi.js，26
- Koa.js，25–26
- Socket.io，26
- REST 架构，37
- RTE，运行时环境 (Runtime environment)
- RTMP，见 实时消息传输协议
- 运行时环境，2
- node.js 的运行时，7
- 执行到完成 (Run-to-completion)，node.js 的单线程行为，106

- 分页，113
- 并行性，121
- 并行操作，121
- PATH 环境变量，8
- 支付选项，58
- 性能测试，63
- 性能测试配置的创建，108
- pipeline ()，72–73
- 平台即服务 (PaaS)，27
- PM 进程管理器，114
- 将 .js 作为强大的编程语言，85
- 私有流，58
- process.exit，32
- 生产就绪项目的处理，152–153
- 程序员错误的处理，133
- 正在处理代码，89
- 项目的未来架构，89

- Sails，140
- 具有吸引力的薪资包，137
- 可扩展性与 node.js，9
- 将 node.js 作为可扩展且高效的编程语言，85
- 定期扫描应用程序漏洞，126
- Schema 的设计，92–97
- 脚本的追踪与日志记录，120
- Bunyan，121
- Morgan，121
- Winston，120–121

- 使用离峰时间运行查询增强，120
- 将 node.js 作为快速编程语言，85

- 范围 (Range)，识别，78
- React
- node.js 与 React 的兼容性，144
- 使用 node.js 和 React 进行 Web 应用开发，144–145
- read() 函数，70
- 安全套层 (SSL)，112
- node.js 的安全问题与建议，122
- 身份验证，125–126
- 为安全补丁构建流水线，126–127
- 数据泄露，123
- 使用加密进行反序列化，124
- HTTP 响应头，124–125
- 创建日志与监控系统，125
- 实现的请求访问控制，123–124
- 定期扫描应用程序漏洞，126
- 字符串及字符串函数，4
- 使用 try-catch 的同步代码，131
- 同步编码，116, 117
- 同步函数，19–20

- 任务运行器 (Task runners)，110–111
- 技术栈的完成，58
- HTTP 实时媒体传输 (HLS)，59
- MPEG-DASH，59
- 在线视频流，其相关协议，59
- nRTMP (实时消息传输协议)，59–60
- 安全换行符的使用，123
- 验证用户输入以限制 XSS 攻击，122
- node.js 的安全问题，122
- SELECT DISTINCT，119
- SELECT 语句，118
- WebRTC，60
- 文本编辑器，7
- /video 端点，76–78
- 线程池，22
- TLS，见 传输层安全 (Transport layer security)
- Total Perfect，143
- 传输层安全 (TLS)，111–112
- 服务器架构，异步模块，17–19
- 服务端身份认证，86
- “Shebang”行，31
- SIGKILL，33
- sigTERM 信号，32
- 将 node.js 作为单编程语言，10
- 单线程快速，8
- Socket.io，26, 36, 43, 44, 55, 99
- 聊天室应用及，43
- 前端部分的准备，45–53
- node.js 的安全性，106
- 内存泄漏检测，106–107
- 执行到完成，单线程行为，106

- Spider 编译器，30
- SSL，见 安全套层
- stderr 函数，74
- stdin 命令，73
- 可写流 (writable stream)，70–72
- writable.end() 方法，71
- 流式测试，63
- 流式数据，24
- 流式编程，56
- 流模块，73
- 流 (Streams)，65–66
- 与 node.js 的流，73
- 视频流，64

- V8 引擎，29–30
- 自动重启应用程序，31
- 编译，30
- 对卓越的追求，30

- 使用命令行运行 node.js，30–31

- WebSocket，36, 116
- 有效服务器通信，116
- 视频游戏，64
- WebSocket API，37
- 聊天室应用及，43

- 消息结构，39–41
- “跨越传输 2.0” 服务，13
- Web 应用开发，138
- Adonis，142–143
- Derby.js，141–142
- Express，138–139
- Hapi.js 框架，141
- Koa Web 应用，140–141
- LoopBack，142
- Meteor，139
- Nest.js，140
- Sails，140

- 水线 (Waterline)，140
- 单点故障，38–39
- 预估，37–38
- 工作原理，36
- 使用 WHERE 子句，118
- 通配符字符，119–120
- Windows 安装，7–8
- Winston，120–121
- 可写流 (writable stream)，70–72

- Total Platform，143
- 使用 node.js 和 React 进行，144–145

- 验证用户输入以限制 XSS 攻击，122–123

- 使用 node.js 的 Web 应用架构，5, 17
- 异步函数，19
- 事件触发器与回调，20
- 异步代码，20–21
- node.js 服务器架构，17
- 异步模型，17–19
- 非阻塞 I/O 操作，21
- 回调，21–23
- Web 应用的框架，143–144
- WebRTC，60
- WebSocket 消息，40

- YouTube，58

- ZEIT，28–29
- Zlib.createDeflate(),74
- Zlib.createGunzip(),74
- Zlib.createGzip(),74
- Zlib.createInflate(),74

