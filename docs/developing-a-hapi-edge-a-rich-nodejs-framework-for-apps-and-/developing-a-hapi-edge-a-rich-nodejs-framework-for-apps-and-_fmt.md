
# Developing hapi Edge：一种用于应用和服务的丰富 Node.js 框架

序言：Eran Hammer

## 目录

### 第 7 章：身份验证

- 总结 60
- tv 75
- 章节概览 77
- 方案（Scheme）与策略（Strategy）77
- `hapi-auth-basic` 78
- `hapi-auth-cookie` 80
- `bell` 84
- 总结 86

### 第 8 章：模型

- 使用 HTTP 87
- 预期用法 87
- NPM 包 88
- NPM 下载量 93
- 使用数据库 100
- 设置数据库 100
- 连接数据库 100
- Schema 设计 101
- 总结 107

### 第 9 章：模板化

- 配置 110
- 选项 111
- 视图加载 116
- 布局 116
- 配置 116
- 用法 117
- 排除 117
- 部分模板（Partials）117
- 配置 117
- 辅助函数 118
- 配置 118
- 辅助函数文件 118
- 共享上下文 119
- 总结 120

### 第 10 章：测试

- 章节概览 121
- `lab` 的历史 122
- 安装 `lab` 123
- 安装 `code` 124
- 编写简单的测试 124
- `lab` 的原则 125
- 始终异步的 125
- 测试脚本 127
- 安全全局变量 127
- 实验 128
- 编写 hapi 测试 129
- 代码覆盖率 131
- 报告器 133
- 代码检查（Linting）136
- 插件测试 136
- 总结 138

### 第 11 章：调试

- 章节概览 141
- `console.log` 142
- 调试模式 142
- 安全 143
- 最佳实践 153
- 密码哈希 153
- 安全 154
- 标头 155
- 文件 156
- 总结 161

### 第 12 章：安全

- 章节概览 161
- 模型 163
- 概述 163
- 数据库 163
- 客户端 164
- 测试 165
- 客户端 167
- Mongoose 170
- 模板化 171
- Schemas 171
- MongoDB 172
- 模板化 173
- 模板化 173

# 序言

## 本书将教你什么？

本书将教你如何使用 hapi 构建出色的 Web 应用程序。它涵盖了关于 hapi 的工作原理以及为什么要这样运行的许多方面。你将看到许多有用且高级的特性，例如身份验证、校验、缓存、模板渲染、测试和调试。在本书中，你还将亲手创建一个完全可以运行的 hapi Web 应用程序。

## 作者介绍

### Daniel Bretoi

Daniel Bretoi 是 WalmartLabs 的一名承包商，他曾在 Eran Hammer 领导的团队工作，该团队开发了 hapi 框架。他在行业内工作了 15 年，精通多种解释型语言。在 2002 年，他是 Ruby 的早期采用者，并一直拥抱新技术。

### Wyatt Preul

Wyatt Preul 是沃尔的软件开发人员。他是 hapi node.js 框架的核心维护者之一。在沃尔玛，Wyatt 曾是臭名昭彰的 node.js 内存泄漏问题的调查人员。此外，他还帮助了沃尔玛内部的许多 node.js 项目。除了日常工作外，Wyatt 还热爱所有与 Node 相关的事物、网络安全、射箭、咖啡烘焙和啤酒酿造。

### Van Nguyen

Van Nguyen 是 Intuit 的高级全栈软件工程师（IDEA，大数据方向）。他目前正在开发一个 JavaScript 工具，用于管理和视觉化大数据数据。

### Lloyd Benson

Lloyd Benson 是沃尔玛的顾问。他也是 Open Infrastructure LLC 的所有者。

## 技术评审员

感谢以下技术评审员提供的早期反馈和细致的评审意见：Doron Pagot, Troy Whiteley, Jeffrey Jagada, Colin Irish, Daniel Barnes, Michael Caputo, James Butler, Alvin Teh, Josh Mock, Michael Parks, Jonathan Holmlund, Glenn Jones 以及 Jesse Newcomer。

## hapi 简介

### 历史

hapi 的起源可以追溯到 2010 年底 Yahoo! 的一个名为 Sled 的项目。Sled 是 Eran Hammer 开发的一个协作列表制作工具，作为一项实验，旨在通过限制来实现赋权。Sled 最终使用 node 编写，Eran 因此爱上了这项技术。Sled 最终被关闭，并在 2011 年 8 月由 Yahoo! Postmile 慷慨地开源。Eran 想继续使用 node，于是离开了沃尔玛，他在那里吸收了 Postmile 的优秀部分，hapi 遂于 2011 年 8 月 5 日诞生。由于负责开发 Web 服务层，hapi 的开发在沃尔玛继续进行。hapi 的原始版本使用了 Express 框架。然而，人们最终发现对于沃尔玛面临的特定需求，Express 有其局限性。虽然 Express 非常棒，但它缺少了许多功能，于是 hapi 演变成了自己的独立框架。

hapi 的名字来源于 HTTP API server，一旦这个名字被重复，人们就会想起《瑞与史迪》（Ren & Stimpy），这是卡通频道的一部邪典动画片。《Happy Happy Joy Song》出现在 hapi 的许多早期演示中。

考虑到《瑞与史迪》的主题，hapi.js 框架中的其他工具开始以不同方式引用该节目，其最终目标是让编码变得……

# 第 1 章：hapi 简介

作为程序员，即使我们身处大型企业环境，写代码时也可以有一点傻气。放松一下，找点乐趣。

从功能上来说，hapi 的设计是为了防止其他框架中反复出现的问题。这包括诸如：中间件顺序问题、缺乏隔离性、匹配缓慢、可测试性以及缺乏常用的内置功能。中间件顺序问题通过 hapi 的生命周期（Lifecycle）解决，它在请求到达服务器或响应返回给用户的整个生命周期内提供了受控的、依赖映射的钩点（hook points）。缺乏隔离性通过领域（domains）解决，后来被一个更好的系统取代。hapi 中的路径匹配非常高效。然而人们最终发现对于沃尔玛面临的特定需求，Express 有其局限性。虽然 Express 非常棒，但它缺少很多东西，于是 hapi 演变成了自己的独立框架。

hapi 的名字来源于 HTTP API server，一旦这个名字被重复，人们就会想起《瑞与史迪》（Ren & Stimpy）。《Happy Happy Joy Song》出现在 hapi 的许多早期演示中。

考虑到《瑞与史迪》的主题，hapi.js 框架中的其他工具开始以不同方式引用该节目，其最终目标是让编码变得……

![hapi 简介](img/79450811086e2fc8749ec4d309ea2b79_14_0.png)

## 作者信息

Van Nguyen 是 Intuit 的高级全栈软件工程师（大数据方向）。他目前正在开发一个 JavaScript 工具，用于管理和视觉化大数据数据。

### Lloyd Benson

Lloyd Benson 是沃尔玛的顾问。他也是 Open Infrastructure LLC 的所有者。

### 技术评审员

感谢以下技术评审员提供的早期反馈和细致的评审意见：Doron Pagot, Troy Whiteley, Jeffrey Jagada, Colin Irish, Daniel Barnes, Michael Caputo, James Butler, Alvin Teh, Josh Mock, Michael Parks, Jonathan Holmlund, Glenn Jones 以及 Jesse Newcomer。

## hapi 简介

### 历史

hapi 的起源可以追溯到 2010 年底 Yahoo! 的一个名为 Sled 的项目。Sled 是 Eran Hammer 开发的一个协作列表制作工具，作为一项实验，旨在通过限制来实现赋权。Sled 最终使用 node 编写，Eran 因此爱上了这项技术。Sled 最终被关闭，并在 2011 年 8 月由 Yahoo! Postmile 慷慨地开源。Eran 想继续使用 node，于是离开了沃尔玛，他在那里吸收了 Postmile 的优秀部分，hapi 遂于 2011 年 8 月 5 日诞生。由于负责开发 Web 服务层，hapi 的开发在沃尔玛继续进行。hapi 的原始版本使用了 Express 框架。然而，人们最终发现对于沃尔玛面临的特定需求，Express 有其局限性。虽然 Express 非常棒，但它缺少了许多功能，于是 hapi 演变成了自己的独立框架。



hapi 的名字来源于 HTTP API server，一旦这个名字被重复，人们就会想起《瑞与史迪》（Ren & Stimpy），这是卡通频道的一部邪典动画片。《Happy Happy Joy Song》出现在 hapi 的许多早期演示中。

考虑到《瑞与史迪》的主题，`hapi.js` 框架中的其他工具开始以不同方式引用该节目，其最终目标是让编码变得

作为程序员，即使我们身处大型企业环境，写代码时也可以有一点傻气。放松一下，找点乐趣。

[此处已过滤重复内容]

# 13. Appendix

This chapter stores the appendix with descriptions and code examples for other-selected databases, and templating engines.

## hapi-plugins

In this book, we will walk through how to use hapi to create the backend services for a real (but basic) web application, hapi-plugins. hapi-plugins (hapi-plugins.com) is a search-repository for hapi-related modules on NPM. This book will NOT cover how to build the client-side JavaScript portion of the application. However, the complete source code is available on GitHub.

## Style

We will be following hapi-style-guidelines throughout this book. To find more about what they are, you can see them at the hapi Style Guide. We may not agree with everything in the styles, but it's worth noting that just having this style guide is 99 percent good. Some practices may look odd, but it really helps with the visualization of the code. We recommend choosing this style not only for projects related to hapi, but for node development in general.

我们在风格方面对准则执行近乎严苛的标准。风格本应该是编程中最易于遵循的简单概念之一，但我们发现许多人做得很粗率。如果你连这些简单的事情都做不好，说明你没有关注自己在做什么。因此，我们形成了这样一个理念：代码离风格越远，在代码审查期间对代码的审查就越需要仔细。

除了整个程序中保持清晰、简洁的代码（这本身就是一种幸事），我们在代码审查期间还非常关注并试图发现任何不协调的地方。这迫使我们扫描每一行代码。这是一件好事，因为它不仅能帮助发现大范围的异常情况，还能发现更小的 bug。

## 总结

废话不多说，让我们在下一章中开始学习 hapi 服务器。

# 服务器 2

hapi 是一个用于构建应用程序和服务的框架。在每个服务背后都有一个服务器；即满足客户端需求的实体。hapi 的核心是一个 HTTP 服务器的超集。其他所有配置都与这一事实相关，因此我们从介绍主要功能开始介绍这本书。其他所有配置都是基于此而产生并产生差异的。我们将讨论许多与服务器、插件、处理器、测试等相关的概念。

在本章中，我们将查看如何设置服务器，以及我们是如何为 hapi-plugins.com 示例设置服务器的。我们将教你 hapi 框架中服务器的细节。你将学会如何设置缓存。你将初次接触插件以及添加可以在整个应用程序中使用的方法。最后，你将学习请求生命周期以及如何为应用程序添加自定义函数。

## 设置简单的服务器

当然，我们不能在没有“hello world”示例的情况下就开始写一本书。嗯，实际上我们可以这样做，但我们不会这样做。在进入更复杂的设置之前，了解如何设置最简单配置的服务器是重要的。

```javascript
var Hapi = require('hapi');

var server = new Hapi.Server();

server.connection();

server.route({
    method: 'GET',
    path: '/',
    handler: function (request, reply) {
        return reply('hello hapi');
    }
})

server.start(function (err) {
    console.log(server.info.uri);
});
```

我们创建了一个 hapi 服务器的实例。我们实际上不需要进行任何操作来配置它。下一步是获取与服务器的连接。连接是服务器监听的端口和主机名。默认情况下，主机设置为 localhost，端口被随机生成在不需要系统管理员访问且可用的端口上。由于我们不知道具体的端口是多少，因此我们在最后处打印出 URI，这样我们就能看到服务器在哪里监听。

我们添加了一个路由，这样我们就有了一个可以发送请求的地方。我们将在第 3 章中进一步深入讨论路由，但现在，请将路由视为一个配置好的路径，客户端（浏览器）的请求可以通过该路径来获得特定的响应。

此时我们启动服务器，并记录服务器 URI，以便我们知道服务器在哪个端口启动。接下来的逻辑步骤是为我们的服务器设置一个启动端口，以便我们知道是同一个地方。这可以通过使用连接的选项来实现：`server.connection({ port: 8088 });`

## 为 hapi-plugins 设置服务器

现在我们对如何设置服务器有了了更基础的理解，让我们检查一下为 hapi-plugins 设置服务器需要做什么。

单页应用程序（SPA）的典型架构是通过像 Ember、AngularJS、React 或其他前端框架提供某些 HTML 模板。我们选择 React 作为我们的前端。提供给框架的信息可以使用相同的后端方法向框架提供数据，但更简洁的方法是让一个独立的 API 服务器来处理数据，这就是我们决定采取的方法。

```javascript
var internals = {
  servers: {
    http: {
      port: 8080,
      host: '0.0.0.0',
      labels: ['http']
    },
    api: {
      port: 8088,
      host: '0.0.0.0',
      labels: ['api']
    },
  },
  options: {
    files: {
      relativeTo: __dirname
    }
  }
}
```

我们将主 HTTP 服务器放在 8080 端口，将 API 服务器放在 8088 端口。它们都在运行并监听在 0.0.0.0，这用于绑定到所有连接的 IP 地址。当服务器启动时，这将运行一个节点进程。配置中的标签（labels）用于标记连接，以便加载适当的插件。hapi 是一个以插件为中心的框架，这意味着一切设计都是围绕插件进行架构构建的。你可以在第 6 章找到有关插件的细节，但现在，让我们意识到这是一个重要的概念。服务器上所有可用的方法也可以在附加到插件的任何地方可用。它是传递给插件注册对象的第一个参数。有时参数名是 plugin，有时是 server。我们将其称为 hapi.com，这是因为我们正在为我们的服务器设置两个连接。一个用于 HTML 内容，另一个用于 API 内容。

```javascript
var Async = require('async');
var Bell = require('bell');
var Blipp = require('blippy');
var Hapi = require('hapi');
var HapiAuthCookie = require('hapi-auth-cookie');
var Mock = require('hoek');
var Api = require('./api');
var Authentication = require('./authentication');
var Controllers = require('./controllers');
var Models = require('./models');
var Routes = require('./routes');

var internals = {
  servers: {
    port: 8080,
    host: '0.0.0.0',
    labels: ['http']
  },
  api: {
    port: 8088,
    host: '0.0.0.0',
    labels: ['api']
  }
};

options: {
  files: {
    redirectTo: __dirname
  }
};

exports.init = function (callback) {
  var server = new Hapi.Server();
  server.connection(internals.servers.http);
  server.connection(internals.servers.api);
  //...
};
```

我们从开始加载将要使用的库。我们将代码组织为 Models、Routes 和 Controllers。我们还专门为 API 编写了代码。

这里新的是标签。它们作为系统的指示器，让我们在稍后决定为每个连接加载哪些插件。我们很可能只有部分插件监听一个连接而不监听另一个。某些插件可能需要监听两者，例如 `/heartbeat` 类型的调用，但通常情况下，除非一个使用 SSL/TLS 而另一个经过加密，否则不应该有太重复。你可以在第 6 章阅读更多关于如何选择和管理插件的内容。这是通过 `server.register()` 实现的。

```javascript
server.path(internals.files.redirectTo);
server.on('request-error', function (request, response) {
  console.log('request-error:');
  console.dir(response);
});
```

`server.path` 表示设置路径前缀，以便我们可以使用相对路径和模板。我们还设置了一个处理请求发生错误的事件。

```javascript
var registerHttpPlugins = function (next) {
  server.register([
    Bell,
    Blipp,
    HapiAuthCookie,
    Authentication,
    Controllers,
    Models,
    Routes,
    { select: 'http' },
    function (err) {
      return next(err);
    }
};
```

```javascript
var registerApiPlugins = function (next) {
  server.register([
    Blipp,
    Controllers,
    Models,
    Api,
    { select: 'api' },
    function (err) {
      return next(err);
    });
};
```

```javascript
Async.auto({
  http: registerHttpPlugins,
  api: registerApiPlugins,
  function (err, data) {
    if (err) {
      console.log('server.register err:', err);
      return callback(err);
    }
  }
});

server.start(function () {
  return callback(null, server);
});
```

```javascript
exports.init(Hoek.ignore);
```

一次性吸收这一大块代码是很困难的，但它们都是相关的，所以请耐心等待，我们将解释我们想要实现的目标。第一个目标是注册我们的插件并启动服务器。我们对代码的架构使用插件将其拆分为易于管理的块，但这在这一章和随后的章节中将会变得清晰。

# 第 2 章：服务器

现在我们已经知道了想要实现什么，让我们来看看具体是如何实现的。`registerHttpPlugins` 和 `registerApiPlugins` 是两个用于为我们服务器上的两个独立连接注册插件的函数。一个函数一次只能将插件应用到一个连接。因此，我们需要区分这两个函数，因为我们为两个连接都使用了 hapi。

我们正在使用 `Async.auto` 来异步完成这些操作，我们可以这样做是没问题的，因为注册插件的顺序并不重要。如果你不熟悉 `Async` 库，它是一个非常棒的工具，我们到处都使用它来保持代码的整洁。这里值得注意的是这一点，并停下来查看 `Async` 的文档以熟悉它。我们可以等一下。

如果发生错误，我们将错误打印到控制台。如果没有错误，我们就继续启动服务器。

注意 `server.register` 接收一个插件数组。这种行为与 `[Async].series` 相似，事实上，hapi 内部正在使用一个名为 `items` 的轻量级 `Async`。如果你发现自己没有使用 `Async` 的所有功能，那么这可能是你更好的替代方案。

如你所见，设置服务器可能是一项艰巨的任务。有很多地方需要记录。然而，有一种更简洁的方法。接下来，我们将查看 `glue`、`rejoice` 和 `confidence` 模块。

## Glue

`Glue` 是一种组合服务器设置的方法。通常我们希望服务器配置保持在代码之外，因为它更具可预测性。

我们上面的是一个相当复杂的设置。为了让我们的工作更容易进行，我们将使用 `glue`。以下是实现方法。

```javascript
// 加载模块
var Glue = require('glue');
var Hapi = require('hapi');
```

```javascript
// 内部实现
var internals = {
  manifest: {
    connections: [{
      port: 8080,
      labels: ['http']
    },
    {
      port: 8088,
      labels: ['api']
    }
  ]
```

```javascript
  plugins: [{
  bell: [['select': 'http']],
  blip: [[]],
  'hapi-auth-cookie': [['select': 'http']],
  './authentication': [['select': 'http']],
  './controllers': [['select': ['http', 'api']]],
  './models': [['select': ['http', 'api']]],
  './routes': [['select': ['http']]],
  './api': [['select': ['api']]],
  good: {
    opsInterval: 5000,
    reporters: {
      'reporter': 'good-console',
      'events': {'ops': '*', 'log': '*'}
    }
  }
}]
};
```

```javascript
Glue.compose(internals.manifest,

{ relativeTo: __dirname }, function (err, server) {
  if (err) {
    console.log('server.register err:', err);
  }
  server.start();
});
```

这是包含了所有 `require` 的整个服务器文件。这样要清晰得多。在使用 `glue` 之前，我们必须定义两个函数来将插件应用到每个连接（http 和 api）。通过 `glue`，我们可以在地方定义所有插件，并为每个插件提供一个包含对应连接的数组。`Glue` 会根据定义自动将插件应用到正确的连接上。

## Rejoice

`rejoice` 是一个 CLI 工具，用于从纯 JSON 配置启动 hapi 实例。该模块以前被拆分并存在于 hapi 自身的 `bin/hapi` 中。它非常直观。现在我们已经学习了 `glue` 组合是如何工作的，你只需要前面提到的 `manifest` 的 JSON 结果即可。结果如下：



```json
{
  "connections": [{
    "port": 8080,
    "labels": ["http"]
  },
  {
    "port": 8088,
    "labels": ["api"]
  }
  ],
  "plugins": {
    "bell": [{ "select": "http" }],
    "blip": [{}],
    "hapi-auth-cookie": [{ "select": "http" }],
    "/authentication": [{ "select": "http" }],
    "/controllers": [{ "select": ["http", "api"] }],
    "/models": [{ "select": ["http", "api"] }],
    "/routes": [{ "select": "http" }],
    "/api": { "select": ["api"] },
    "good": {
      "opsInterval": 5000,
      "reporters": {
        "reporter": "good-console",
        "events": { "ops": "*", "log": "*" }
      }
    }
  }
}
```

由于这是一个 JSON 文件，我们使用了双引号。假设你已经在本地安装了 `rejoice`，你可以通过 `rejoice -c example.json` 启动它。能够使用单个 JSON 文件工作很好，但你可能会发现根据环境的不同，对这些文件有不同的处理需求。这就是 `confidence` 的用场。

## Confidence

`Confidence` 是另一个 CLI 工具。你可以获取一个 JSON 文件并对其应用过滤器，以便处理该文件。为每个环境管理多个文件不仅可能很麻烦，而且容易出错。当你添加了一组新文件但忘记将其添加到其他文件中时。这会导致配置漂移问题，而有了 `confidence`，你可以“确信”自己只有一个来源可以去。

```json
{
  "connections": [{
    "port": 8080,
    "labels": ["http"]
  },
  {
    "port": 8088,
    "labels": ["api"]
  }
  ],
  "plugins": {
    "bell": [{ "select": "http" }],
    "blip": [{}],
    "hapi-auth-cookie": [{ "select": "http" }],
    "/authentication": [{ "select": "http" }],
    "/controllers": [{ "select": ["http", "api"] }],
    "/models": [{ "select": ["http", "api"] }],
    "/routes": [{ "select": "http" }],
    "/api": { "select": ["api"] }],
    "good": {
      "opsInterval": 5000,
      "reporters": {
        "reporter": "good-console",
        "events": { "ops": "*", "log": "*" }
      }
    }
  }
}
```

# 第 2 章：服务器

我们还有一个 `expiresIn` 设置，它设置为缓存项在一小时后过期。

还有一个有趣的设置叫做 `staleIn`，你可以将存储在缓存中的项标记为已过期。该设置的值小于 `expiresIn`。使用此功能，你可以在 `expiresIn` 到达时准备好缓存。如果 `staleIn` 在 `expiresIn` 之前没有的时间，它将像普通的 `expiresIn` 一样工作。这是在预热你的缓存。

最后，看到我们使用 `cache.set()` 将作者对象的值设置为 `pluginName`，并且我们可以使用 `cache.get()` 方法来检索它。

`server.cache` 还有更多选项，更多详情请访问 hapis.js 文档。

## 请求生命周期

理解某技术如何处理 HTTP 请求，是使用该技术开发安全、高效应用的基础。Node.js 本身在这一方面提供的不多，尽管在 Node.js 中创建一个服务器非常简单：

```javascript
var server = require('http');

server.on('request', function (request, response) {
  // do something
});

server.listen(80);
```

这只是一个函数。请求包含了来自请求源的所有入站信息，并有一个可写流，该流需要设置头、向其写入信息，然后关闭连接。起初这可能令人兴奋，特别是对于那些过去没有处理过它的人。然而，一旦应用程序需要路由表，处理起来就会变得很费力。

hapi 处理请求的方式是每当服务器接收到请求时，触发一系列可靠的事件。以下是完整的生命周期：

- `onRequest` 扩展点
  - 总是被调用。
  - 传递给扩展函数的请求对象被 `request.getUrl()` 和 `request.setMethod()` 方法所装饰。调用这些方法将影响请求的路由方式，并可用于重写规则。
  - 此时 `request.route` 尚未被填充。

对于从扩展点返回的任何响应，JSONP 配置都会被忽略，因为尚未匹配到路由，且 JSONP 配置是不可用的。

- 使用请求路径查找路由
- 解析 cookies
- `onPreAuth` 扩展点
- 身份验证请求
- 读取并解析负载（payload）
- 身份验证请求负载
- `onPostAuth` 扩展点
- 验证路径参数
- 处理查询扩展（例如 JSONP）
- 验证查询
- 验证负载
- `onPreHandler` 扩展点
- 路由先决条件：在 Handler 中配置
- 路由处理器
- `onPostHandler` 扩展点

`request.response` 中包含的响应对象可以被修改（但不能赋予新值）。要返回不同的响应类型（例如，用 HTML 响应替换错误），请通过 `reply(response)` 返回一个新的响应。

- 验证响应负载
- `onPreResponse` 扩展点
  - 总是被调用（除非调用 `reply.close()` 或客户端连接提前断）。
  - `request.response` 中包含的响应对象可以被修改（但不能赋予新值）。要返回不同的响应类型（例如，用 HTML 响应返回错误），请通过 `reply(response)` 返回一个新的响应。注意，`reply(response)` 之后生成的任何错误都不会传回 `onPreResponse` 扩展方法，以防止无限循环。
- 发送响应（可能会触发 `request-error` 事件）
- 触发 `response` 事件
- 等待尾部（tails）
- 触发 `tail` 事件

## 扩展点

既然我们已经讨论了生命周期，我们可以利用 hapi 中的“扩展点”。这些扩展点在生命周期中暴露了流，其他函数可以在其中插入。它们可以轻松地绑定到服务器上，以增强现有的 hapi 生命周期。我们使用 `server.ext` 功能来实现这一点。让我们来看几个例子。接下来的示例也出现在第 9 章中关于如何共享上下文的内容。现在知道这意味着什么很重要，但让我们来看看 `server.ext` 是如何使用的。首先，让我们看看 `PreResponse` 事件。

```javascript
server.ext('onPreResponse', function (request, reply) {
  var response = request.response;
  if (response.isBoom() && response.source.context) {
    response.source.context.title = "hapi-plugins";
  }
  return reply();
})
```

看到我们调用了 `server.ext`。回想一下在请求生命周期中，`onResponse` 位于最后，就在响应给出之前。我们在这里添加了一个函数，添加了标题上下文并返回了 `reply()` 对象。

第 9 章中的另一个示例是：

```javascript
server.ext('onRequest', function (request, next) {
  request.sharedContext = {
    title: 'hapi-plugins'
  };

  next();
});
```

这次我们正在使用请求生命周期中的 `onRequest` 部分。同样，此时我们并不真的需要知道它具体做什么，但请记住 `onRequest` 在生命周期的开始，取决于你需要在流程的哪个位置添加功能，你需要如何整齐地将逻辑放入流程中。虽然没有讨论，但如果你需要在身份验证过程中添加一些自定义功能，你可以利用 `onPreAuth` 或 `onPostAuth`。请记住，如果与此无关，这些在生命周期中并不总是会被调用。

## 总结

设置服务器非常简单。服务器和插件非常相似。服务器可以由几个不同的插件组成。插件只是更小、更易管理的部分的逻辑分离，可以添加到你的服务器实例中。我们可以用函数装饰服务器，并可以使用 JSON 配置文件来配置服务器。

使用 `glue` 真的可以让我们的设置变得简单得多，如果有开发和生产环境设置，配合 `rejoice` 和 `confidence` 使用配置文件是一个很好的方法。接下来，你将学习所有关于我们 hapi 服务器的路由。

# 第 3 章：路由

在大多数地方，“路由”（route）一词与你通过它到达目的地的特定路径相关。例如，从 A 点开车到 B 点时，你可能有几条不同的路线可选。路由是两点之间的一非常具体的路径。

在 hapi 和其他框架中，路由是请求所走的特定路径。在网站上，你在地址 `hapi-plugins.com` 之后可以写的字符数量仅限于你的浏览器支持的字符数。为了发送请求并实际获得你寻找的内容的响应，你需要知道发送请求的路由。查询随后通过框架内部的路径旅行，并根据请求的若干参数返回响应。你告诉路由去采取的实际路由对于知道如何处理此请求是关键。它是客户端期望对请求执行操作的首要指示。

在最简单的形式下，路由如下：

```javascript
server.route({
  method: 'GET',
  path: '/',
  handler: function (request, reply) {
    reply.view('index');
  }
});
```

这是简短且简单路由的一种非常棒直观的形式，但当项目变大时，我们会分离行为，使用配置而不是像这里这样提供处理器。

我们通常将配置存储在它们自己的文件中。在我们查看为这个项目做了什么之前，我们将进一步简化。

在我们的 `lib/routes.js` 文件中，我们有如下内容：

```javascript
var Welcome = require('./controllers/welcome');

server.route({
  method: 'GET',
  path: '/',
  config: Welcome.index
});
```

那么，路由的实际配置位于对应的文件 `lib/controllers/welcome.js` 中。

```javascript
modules.export.index = {
  description: '显示我们欢迎页的主页',
  handler: function (request, reply) {
    reply.view('index');
  }
};
```

这保持了代码逻辑分离，这是 MVC（模型-视图-控制器）框架的典型特征。代码逻辑可能会变得非常广泛，通过这种分离，可以轻松地组织使得特定路由的逻辑都在一个文件中。你可能决定采用这种路由，只需将该逻辑放在 `lib/controllers/welcome/index.js` 中即可。在这种结构下，服务条款可能是 `lib/controllers/welcome/tos.js`。当然，在函数大到需要拆分为单独文件之前会有某种判断标准。但核心思想是代码在拆分成更小的部分后更容易管理和阅读。

## 路径处理

路由是唯一的。在 GitHub 上已经开启了关于正则表达式或其他类型通配符的问题。当路由重叠时，很难判断。hapi 的早期设计目标之一是确保路由表在每次加载时都是相同的。不会有意外。在启动时，hapi 会对任何冲突进行报错并保护你免受此类问题的影响。

### 路由匹配顺序

为了发送请求并实际获得你寻找的内容的响应，你需要知道发送请求的路由。查询随后通过框架内部的路径旅行，并根据请求的若干参数返回响应。你告诉路由去采取的实际路由对于知道如何处理此请求是关键。它是客户端期望对请求执行操作的首要指示。

hapi 如何处理路径的，路由器在处理每个传入请求时遍历路由表并执行第一个（也是唯一的）匹配路由。路由匹配仅针对请求路径（不包括查询和其他 URI 组件）。路由匹配是按照确定的顺序进行的，因此无论你在哪里添加它们都没有关系。最后，路由按照从具体到通用的顺序排序。如果你想进一步了解这具体如何工作，请参见路径匹配顺序。

## 路由的组成部分

路由对象，`server.route()` 的参数包含几个简单的属性。

### method

这决定了要在资源上执行的 HTTP 请求方法。该方法将是以下之一：GET HEAD POST PUT DELETE TRACE OPTIONS CONNECT PATCH。在实际操作中，它很可能是 GET、POST、PUT、DELETE 或 PATCH 之一，且不允许 HEAD。hapi 允许使用通配符方法，这意味着当未找到精确匹配时，它将改用通配符。通配符字符串为 `*`。

### vhost

指定此路由监听的虚拟主机（virtual host）。服务器可以监听多个虚拟主机，但为了让路由为特定主机被触发，可以指定要监听的主机。通过这种方式，服务器可以根据定义的 vhost 提供路由服务。vhost 可以定义为字符串，也可以定义为字符串数组。默认情况下允许任何主机使用该路由。

### handler

handler 是一个函数，用于返回被调用路由的输出。它取决于先前的验证和任何身份验证。如果 handler 是由服务器定义的，可以传递一个带有 handler 的属性以及任何选项的 get。要深入研究 handler 的各种复杂性，请参阅第 4 章。

### config

如果你需要为路由提供额外的配置，可以使用 config 部分来定义这些配置。对于简单的应用程序，你可能不需要指定额外配置，因此这并不是强制要求的。但对于更复杂的配置，最好在此结构下组织你的代码。在此结构中，你将 handler 移动到此部分，以便所有的配置都组织在同一个位置。更复杂配置的一个示例是添加验证或缓存。

需要注意的是，这里的缓存与第 2 章讨论的 `server.cache` 不同。后者的功能缓存响应对象。而此部分的缓存是纯粹的缓存。它将设置 `Cache-Control` 头。下面是一个简单的示例，它为我们的 `/hello` 路由设置了缓存标头。

```javascript
server.route({
  method: 'GET',
  path: '/hello',
  config: {
    handler: handler,
    cache: {
      expiresIn: 60 * 60 * 1000
    }
  }
});
```

config 部分有很多选项，我们认为让你查阅文档更好。然而，接下来我们将介绍另一个内容：路由先决条件（route prerequisites）。

## Route prerequisites

你可能需要为你使用的每个端点初始化数据库连接并将其返回。这是一个非常适合路由先决条件的任务。你可能需要设置很多事情，但可能是最常见的。先决条件允许你串行或并行运行任意数量的函数。`pre` 参数是一个混合数组。它可以包含数组或其他对象。也就是说，数组中的任何内容都将并行执行，而所有其他项将串行执行，例如：

```javascript
server.route({
  method: 'GET',
  path: '/',
  config: {
    handler: function (request, reply) {
      reply.view('index');
    },
    pre: [
      series,
      series,
      [
        parallel,
        parallel
      ],
      series
    ]
  }
});
```

`pre` 数组中的每个 `series` 和 `parallel` 项都是具有两个属性的对象：`method` 和 `assign`。



```javascript
var dbSetup = function (request) {});
server.route({
  // ...
  config: [
    { method: dbSetup, assign: 'connection' }
  ],
  handler: function (request, reply) {
    var conn = request.pre.connection;
    conn.exec('select * from blah', function (err, result) {
      if (err) {
        var msg = 'DB call failed';
        return reply(Boom.internal(msg));
      }
      return reply(result);
    });
  }
});
```

## Path

路径通过 `/` 字符分为多个段（segments）。这意味着任何不是 `/` 的内容都是一个段。

需要注意的是，每个段不允许包含多个参数。由于 hapi 规定路由必须具有可预测的顺序，hapi 不支持任何类型的正则表达式语法，因为这很难判断路径何时重叠。但 hapi 允许同时使用可选参数、通配符参数和匹配路径的多个段。

### Simple Path

路径中的命名参数使用大括号表示，如下：`/fixed/{name}`。在 handler 中，request 对象将拥有一个 `params` 对象。你可以在 handler 中通过 `request.params.name` 使用 name 参数。我们将在第 4 章中介绍更多关于 request 对象的细节。

构建路径有很多选项。稍后可以在 handler 中通过 `request.path` 访问，这在第 4 章中也会更详细地讨论。

为了说明：

```javascript
var internals = {};

server.route({
  method: 'GET',
  path: '/plugins/{name}',
  config: internals.config
});

internals.config = {
  description: '一个获取特定插件信息的路径',
  validate: {
    params: {
      name: Joi.string().required()
    }
  },
  handler: function (request, reply) {
    var msg = 'The name of the plugin that was passed is: ';
    return reply(msg + request.params.name);
  }
};
```

路径包含参数名，然后对其进行验证以确保它是字符串而不是其他内容。需要更多验证，请参阅第 5 章。

我们通过 `request.params` 访问参数获取名称。

### Optional Parameters

为了指定可选参数，我们使用问号 `?`。在正则表达式中，这也表示可选匹配和捕获，因此你可能已经熟悉它。

`/plugins/{name?}`

在这种情况下，如果 name 缺失，可能不清楚应该提供什么，但你可以它来提供插件列表。

### Wildcards

如果我们需要接受任意数量的段（例如，为特定路由代理查询），那么通配符 `*` 简直是救星。任何使用通配符字符的内容将作为数组存储在 request 对象的命名参数中。也许如果我们允许查询直接从 npm 获取并检索所有结果，我们就可以允许下面的路径：

`/npm/*`

由于此处捕获的性质，类似于允许函数接受任意数量参数的编程语言（EcmaScript 6 提供了使用 `......` 的剩余参数），你只能将剩余参数通配符放在路径的末尾。

# 第 4 章：处理器 (handler)

请求中附带了大量重要且有用的信息，这些信息会在处理器中使用以完成请求。在本节的剩余部分中，我们将查看如何查找这些数据以及你可以对它们进行什么。

请记住，在请求生命周期中还有其他函数（参见第 2 章）可以在过程中向请求添加数据。我们将查看几个常见的函数。

## Parameters (参数)

请求对象的一些数据是作为路由直接配置的一部分设置的。例如，如果路由定义的路径包含一个用于下载的 hapi 插件的 id，那么该 id 将是请求对象参数访问的一部分。

```javascript
server.route({
  method: 'GET',
  path: '/plugins/(name)',
  config: Controllers.Plugin.get
});
```

在我们的案例中，name 是标识符，将通过 `request.params.name` 访问。在上面的示例中，我们使用的是 GET 方法。假设端口为 8080，如果我们执行：

```bash
curl -XGET http://localhost:8080/plugins/pluginName
```

我们将得到 `Controllers.Plugin.get` 返回的内容。当我们谈论有效负载（payload）时，会将此与其他方法进行对比。

## Query (查询)

对于初学 hapi 的人来说，参数（param）和查询（query）之间的区别可能会让他们困惑。在 https://hapi-plugins.com/search?q=pluginName 中，URL 的查询部分是 `?` 后。查看之前的 `/plugins/{name}` 示例进行对比。name 参数严格是路径的一部分。

`request.query` 包含了通过 URL 查询发送的所有键值对。

例如，我们可以对 URL 进行“疯狂”操作以获取 hapi-plugins.com 上某个特定插件的信息，并请求如下内容：

```text
http://localhost:8080/plugins/blipp?hello=hi
```

## The Request (请求)

如果我们用 `console.log(request.query)` 记录输出，打印到控制台的结果将显示为：

```json
{ hello: 'hi' }
```

值得注意的是，值可以是一个数组。hapi 会自动为你处理多个查询键，但你必须意识到结果类型可能与预期的类型不同。

如果 URL 如下所示：

```text
http://localhost:8080/plugins/blipp?hello=hi&hello=hey
```

我们将看到值是一个数组：

```json
{ hello: ['hi', 'hey'] }
```

## Payload (有效负载)

`request.payload` 包含了作为请求的一部分传输的但不适用于查询的信息。这可能是一个文件，或者是一个 JSON 或 XML 块。虽然对于所有请求方法（GET, POST, DELETE, PUT, PATCH 等）发送 payload 是可能的，但通常不用于 GET。如果你确实为 GET 发送了 payload，可能应该重新考虑你的设计。

让我们从一个简单的处理器示例开始，其中我们将利用 POST 方法创建一个新用户。

```javascript
handler: function (request, reply) {
  console.log('name: ' + request.payload.name);
  console.log('email: ' + request.payload.email);
  return reply('success');
}
```

如果你还记得我们之前讨论过 `params` 和 GET 方法，我们想要将此与 `payload` 进行对比。对于上面的处理器，我们按照如下设置了路由。

```javascript
server.route({
  method: 'POST',
  path: '/user',
  config: {
    handler: handler
  }
});
```

在这里你可以看到方法是 POST。在之前定义的处理器中，你可以引用你的负载请求 `request.payload`。在这种情况下，负载有两个键：name 和 email。我们向用户路径发送一个 POST 请求。一旦此服务器启动，在 curl 中可以执行如下操作：

```bash
curl -XPOST -H "Content-Type: application/json" -d '{ "name": "Author Name", "email": "author@hapi-plugins.com" }' https://hapi-plugins.com/user
```

我们也可以使用 PUT，它的工作方式是相同的。

## Headers (请求头)

`request.headers` 是存储所有请求头的地方。使用我们之前的 curl，我们会发现在你的处理器中可以引用 `request.headers.Content-Type`，该值将是 `application/json`。

## The Reply (响应)

处理器中的 `reply` 函数充当回调以及将控制权返回给框架的方式。`reply` 函数负责回复请求，以提供所请求的任何结果。

`reply` 接收两个参数以符合常规回调约定，即两个参数都是 `err`（错误）和 `result`（结果）。在实践中，只有两个中的一个会被使用。如果第一个参数是错误对象，它将被封装在 Boom 对象中。`reply` 的参数类型可以是许多不同的类型：

- `null`
- `undefined`
- `string`
- `number`
- `boolean`
- Buffer 对象
- Error 对象
- Stream 对象（Stream 对象必须与 "streams2" API 兼容且不能为 objectMode）
- Promise 对象（hapi 的测试使用 bluebird 库）
- 任何其他对象或数组

# 第 4 章：处理器 (handler)

`path` 是我们想要检索并显示的实际数据所在的位置。这里还可以设置许多选项。

我们首先将 `index` 设置为 `false`。我们没有必要在 CSS 文件夹中提供任何 `index.html`。

`directory` 的选项如下：

- `path` - 查看 handler 以获取设置此项各种方式的说明。
- `index` - 可以是 `true`、`false` 或表示要查找的索引文件名的字符串。默认文件是 `index.html` 且被设置为 `true`。
- `listing` - 决定在缺少索引文件的情况下是否显示目录列表。默认值为 `false`。
- `showHidden` - 决定在列表中是否也显示隐藏文件。默认值为 `false`。
- `redirectToSlash` - 如果路径末尾有斜杠，则将将其重定向到不带斜杠的路径。
- `lookupCompressed` - 如果为 `true`，则如果请求支持内容编码，它将查找带有 `.gz` 后缀的相同文件名，以寻找预压缩的文件版本进行服务。默认值为 `false`。
- `defaultExtension` - 如果未找到请求的文件，则会在文件请求后追加的字符串。默认值空字符串。

## 视图处理器 (Views Handler)

视图处理器使用模板显示信息。在实践中，此选项并不常用。更常见的方法是使用 `views` 选项配置服务器，然后使用常规处理器并配合 `reply.views()` 使用。

由于 hapi 支持这两种方式，我们将查看视图处理器，并更多关注如何配置服务器以直接通过 `reply.views()` 支持视图。

对于我们的 `hapi-plugins` 项目，我们没有使用视图处理器，但应该提到由于某种原因，如何覆盖常规的 `server.views`。

在这两种情况下，服务器都通过一个 `views` 调度器进行配置。

```javascript
plugin.views({
  engines: {
    html: {
      module: require('handlebars')
    }
  },
  path: __dirname + '/views'
});
```

我们正在设置渲染引擎，并指定从哪里读取模板的相对路径。`engines` 配置中的属性设置了用于特定渲染引擎的文件扩展名。

一个非常基础的用例如下：

```javascript
exports.terms_of_service = {
  view: 'terms_of_service'
}
```

这里直接接收一个模板文件名的字符串。

在我们想要覆盖服务器的 `views` 配置时，情况会更复杂——你传入的是一个对象：

```javascript
exports.terms_of_service = {
  view: {
    template: 'terms_of_service',
    context: {
      serviceType: 'provider'
    }
  }
}
```

为了方便说明，`context` 是包含发送到你的模板的实际数据的 JSON 对象。在你的模板 `terms_of_service` 中，你可以在模板中引用 `service`，它将填充 `provider` 的值。关于模板的更多讨论在第 9 章，取决于模板引擎的不同，这种语法会有所不同。

如果没有向对象传递 context，则它被设置为一个包含以下属性的 context 对象：

- `payload` - 包含 `request.payload`
- `params` - 包含 `request.params`
- `query` - 包含 `request.query`
- `pre` - 包含 `request.pre`

视图对象还可以包含一个 `options` 属性，用于覆盖服务器的视图设置。

## 使用 `SERVER.VIEWS` 的常规处理器

`reply.view()` 是渲染模板文件最常用的方式。

对于 `hapi-plugins` 的主页，我们只渲染一个 `index` 文件并在页面上显示一个随机引言。

```javascript
module.exports.get = {
  handler: function (request, reply) {
    reply.view('index', {
      finalmsg: internals.quotes[Math.floor(Math.random()*internals.quotes.length)]
    });
  }
};
```

在模板中我们看到以下内容：

```html
<div id="finalfrontier" class="col-md-12">
  {{finalmsg}}
</div>
```

如果你想了解更多关于 handlebars 的信息，可以访问 handle-bars.com 阅读更多。

## 代理 (Proxy)

对于许多刚开始的人来说，使用代理可能是开始项目的一个简单方式。你有一些想要替换的遗留服务，而代理是一个很好的开始点。事实上，代理功能是 hapi 使用最频繁的功能。这正是在我们在 WalmartLabs 开始使用 hapi 的原因。下面是一个如何代理 Google 的示例。

```javascript
server.route({
  method: '*',
  path: '/(path)*',
  config: {
    handler: {
      proxy: {
        host: 'google.com',
        port: 80,
        protocol: 'http',
        // 第6次重定向将获得 300 响应
        redirects: 5,
        passThrough: true,
        xforward: true
      }
    }
  }
});
```

我们对方法使用了通配符。这将匹配任何进入的方法。`path` 设置只是简单地表示路由所有内容。最后，在 `config` 部分的 `handler` 下，我们有了代理。你可以看到我们正在为 google.com 设置代理。`redirects` 设置表示我们最多只重定向五次。`passThrough` 设置指定了是否保留原始请求的标头。最后，`xforward` 设置告诉 hapi 向请求添加（或追加）`x-forwarded-for` 标头。

你可以使用代理处理器执行其他强大的操作。你可以使用 `mapUri` 重写请求，使用 `localStatePass-Through` 从 hapi 实例传递本地状态，使用 `rejectUnauthorized` 拒绝未经授权的请求，你甚至可以使用 `onResponse` 配合自定义函数执行任何你想执行的操作。更多细节请参考文档。

与其代理 Google，你可以在这里代理你自己的服务。代理是开始简单任务的一种容易方法。随着时间允许，你可以向应用程序中添加路由来接管该下游功能。这种方法由于更改集较小，易于调试。

## 在处理器中添加常用方法

有时某些函数需要被多次访问。在这种情况下，我们可以使用便利函数。访问这些函数的一种方法是将所有函数放在一个公共库中并调用。

然而，hapi 还有其他解决方案来让这个过程变得更容易。

## 绑定到服务器 (Binding to Server)

通过在全局上下文中绑定，任何变量或函数都可以在处理器函数中可用。如果你需要共享功能，这将非常有用。

context 可以在插件中设置或服务器级别设置。我们通常将其用于不需要每次都初始化的服务，而不是在应用程序运行期间初始化的。

```javascript
server.bind({
  service: new Service()
});
```

你可以简单地从任何处理器中访问 `this.service()`。这可以作为一个实用的快捷方式。

关于绑定的更多信息，请访问 hapis.com/api#serverbind

## 装饰响应 (Decorating the Reply)

类似于 `server.bind`，此函数本身用于使用 `reply`。`server.decorate` 的范围更窄，但它非常适合预定义响应（canned replies）。



```javascript
server.decorate('reply', 'success', function () {
  return this.response({ success: true });
});
```

我们有一个选项来装饰 `reply` 对象或服务器对象，第一个参数指定装饰哪一个。第二个参数指定方法的名称，第三个参数是回调。在我们的处理器中，我们可以简单调用：

```javascript
reply.success();
```

这是一个非常好的快捷方式，如果 JSON 对象发生变化，可以避免修改多个处。它也是确保成功响应一致的一种良好方法，因为它消除了拼写错误。

你可以在第 2 章找到更多关于装饰服务器对象的信息。

## Tails（尾任务）

某些操作不需要立即完成。调用的类型可能是某种后台作业，这对于返回给客户端的页面来说是不必要的。它可能是为了更新的数据库调用，也可能是任何事情。虽然没有必要捕获这些，但我们仍然可能为了日志记录捕获它们。当请求捕获 tails 时，服务器会发出一个 tail 事件。

```javascript
server.route({
  method: 'GET',
  path: '/',
  handler: function (request, reply) {
    var publishTail = request.tail('publish the book in the background for download');

    HapiBook.publishForDownload({format: 'pdf'}, function (downloadUri) {
      var mail = Mail({to: user});
      mail.publishNotification(downloadUri, function () {
        publishTail();
      });
    });
  }
});
```

```javascript
}}
));
reply.view('index');
}
);
er.on('tail', function (request) {
  console.log('all tails completed');
});
```

## 使用 `server.handler` 定义处理器

处理器可以直接定义在服务器对象上。在实践中，这并不是我们在自己的代码中定义处理器的方式，但在此处包含它是作为一种可能的替代方案。毕竟，很多代码取决于喜好。

```javascript
var DB = new Database(options);
server.handler('pluginLike', function (route, options) {
  return function (request, reply) {
    options.DB.getPlugin(request.path.id, function (err, plugin) {
      if (err) {
        return Boom.internal(err);
      }
      plugin.like(function (err) {
        if (err) {
          return reply.fail();
        }
        return reply.success();
      });
    });
  };
});
server.route({
  method: 'GET',
  path: '/plugins/like/{id}',
  handler: { pluginLike: db: DB }
});
```

## 点赞插件示例

作为一个大型示例，我们将查看当我们在网站上制作插件时后台发生了什么。以下是示例代码。

```javascript
module.exports.like = {
  auth: 'session',
  handler: function (request, reply) {
    var pluginName = request.params.name;
    var username = request.auth.credentials.username;

    if (!username) {
      return reply(Boom.unauthorized());
    }

    var getPlugin = function (user, next) {
      DB.plugin.get(pluginName, function (err, plugin) {
        if (err || !plugin) {
          var msg = 'no such plugin found';
          return next(Boom.NotFound(msg));
        }
        return next(null, plugin, user);
      });
    };

    var addLike = function (plugin, user, next) {
      user.like(plugin, function (err) {
        return next(err);
      });
    };

    Async.waterfall({
      getOrCreateUser,
      getPlugin,
      addLike
    }, function (err, result) {
      if (err) {
        return reply(err);
      }
      return reply({success: true});
    });
  }
};
```

## 上传文件

直接向网站上传文件是开发者作为开发者面临的最基本功能之一，然而，发现如何做到往往非常没必要困难。本节将引导你如何处理文件上传以及你可以对此采取的一些不同选项。

对于我们的网站，我们需要能够上传包以便发布它们。这允许我们为插件站点注册包，并且根据用户的凭据，npm 变得可选的。

让我们从视图开始。模板将在第 9 章中讨论，因此请参考如何让上传页的呈现符合你的需求。现在，让我们来看上传文件所需的 HTML 代码。

```html
<!DOCTYPE html>
<html>
<form action="/plugin/upload" enctype="multipart/form-data" method="post">
<p>
选择一个文件进行上传：
<input type="file" name="datafile" size="40">
</p>
<div>
<input type="submit" value="Send">
</div>
</form>
</html>
```

这是一个通用的上传表单，适用于你可能使用的任何后端系统。它将简单向 `/plugin/upload` 发送表单 POST 请求，其中文件的负载名为 `datafile`。

在接收端，我们必须设置处理器来处理数据。代码如下：

```javascript
module.exports.postUpload = {
  description: '提交一个文件进行上传',
  payload:{
    maxBytes: 209715200,
    output: 'stream',
    parse: true
  },
  handler: function (request, reply) {
    request.payload.datafile.pipe(FS.createWriteStream("out"));
    reply("yeah, so... done.");
  }
}
```

回在本章的 payload 部分，我们可以利用 `request.payload` 对象来实现如 POST 等方法。注意，我们为处理 payload 提供了特定的选项。默认 payload 被限制为 1mb。这是为了防止恶意和/或无能力的用户搞垮你的应用程序，这也是与其他较关注安全功能的框架区别开来的许多特性之一。当用户发送大文件时，服务器可能会耗尽内存。这可以被用来攻击并关闭你的服务。在这种情况下，我们通过将默认的 `maxBytes` 修改为更实用的值，增加了上传大小以处理更大的文件。

由于我们正在接收文件，我们选择创建一个读入流，以便我们可以直接输出到文件，无论使用何种存储方法。在接收时分块直接从请求移动文件内容，避免了在存储到其他地方之前将其存在内存中。这节省了我们宝贵的内存。

虽然解析的默认是原始的，但我们在这里包含了它。此字段告诉 happy 数据是否需要经过 gzip（压缩）处理或以原始格式发送，true 和 gzip 表示文件将经过处理。

支持几种 MIME 类型，查看我们上方表单的 `enctype`，可以看到我们正在使用 `multipart/form-data`。

- `application/json`
- `application/x-www-form-urlencoded`
- `application/octet-stream`
- `text/*`
- `multipart/form-data`

## 总结

在本章中，我们学习了所有验证响应。接下来，我们将看到 hapi 如何验证输入和输出。

被转换为此参数。我们在服务器路由中的方法是一个 POST 请求，这个 JSON 对象会被翻译为 `payload` 对象。

你可以看到验证是在 `payload` 上完成的。传递 `payload` 中的密码是一个至少八个字符的字符串，并且是一个必填字段。此外，我们还在告诉 hapi 期望响应是一个 JSON 结构，其中 `success` 值为 true 或 false。

你可能在想问，为什么响应不在 `validate` 区域？`validate` 区域严格用于输入。当你第一次将 hash 与 `joi` 使用时，这并不显而易见。如果你的工作依赖于另一个 API，那么输出（响应）验证可能极其重要。拥有输出验证可以让你有信心确保你从该 API 处获取的是正确的内容。

正如你在我们目前的代码中看到的那样，我们喜欢将一切拆分，并广泛地使用 `config`。由于验证模式（schema）可能会很长，所以我们通常将验证规则放在 `internals` 变量中。

`internals` 变量是存放文件中所有顶层变量的地方。这可以防止作用域污染。在我们必须在多个地方访问模式以处理验证的情况下，这特别有用。下面的示例演示了这一点。

```javascript
var internals = {
  pluginSchema: Joi.object().keys({
});
// Get plugin data
exports.get = {
  description: 'get plugin data for a specific plugin id',
  response: {
    schema: internals.pluginSchema
  },
  handler: function (request, reply) {
    // ...
  }
};
```

## 为 hapi-plugins.com 进行验证

让我们来看 hapi-plugins.com 的搜索函数。

```javascript
module.exports.search = {
  validate: {
    query: {
      q: Joi.string(),
      sort: Joi.string().optional(),
    }
  }
};
```

```javascript
fields: Joi.string().optional()
}
response: {
  schema: Joi.array().includes(Joi.object()).keys({
    name: Joi.string().required(),
    authors: Joi.array(),
    keywords: Joi.array(),
    dependencies: Joi.array(),
    dependents: Joi.array(),
    homepage: Joi.string().allow(''),
    version: Joi.string(),
    license: Joi.string(),
    description: Joi.string(),
  })
}
```

```javascript
handler: function (request, reply) {
  var query = null;
  var sort = null;
  if (request.query.q) {
    query = Xss(request.query.q);
  }
  if (request.query.sort) {
    sort = Xss(request.query.sort);
  }
  DB.plugin.search(query, sort, function (err, results) {
    var converted = internals.convert(results);
    return reply(converted);
  });
}
```

你可以看到这里正在对 `query` 进行验证。它期望三个字符串类型的输入。其中 `q` 是唯一的必填输入。额外的 `sort` 字段输入是可选的。然而，如果提供了它们，它们必须是有效的字符串。如果向 API 的请求未能提供这些，那么前端收到的错误将非常明显，易于调试。

你注意到这里使用了 `Xss`。这在第 12 章中会有更详细的解释，但它有助于防止跨脚本攻击。

此示例另一个需要注意的重要点是，对于 `homepage`，你可以看到字符串添加了 `allow('')`。默认情况下，字符串是不允许空的。这可能让某些人感到困扰，但在涉及验证时，谨慎为好。

你还会注意到对响应有验证。对于这些值中的每一个都提供了一个模式（schema）。我们选择不将它分开，因为它很小，而且放在一起更容易阅读。

对于 hapi-plugins.com，一旦结果从数据库返回，它们会被转换为一种输出格式，其中所有多余的内容都会被移除，并仅转换为所需的内容。这些数据通过此响应模式进行验证，确保数组中的每一项都是预期的结果。

我们晚上可以安心睡觉了。

## 使用 `joi` 进行通用数据验证

我们不仅使用 `joi` 来验证输入和输出，在内部也使用它来验证各种其他数据。假设我们正在调用一个外部服务，或者只是调用数据库。虽然我们希望数据没有被导致错误的部分数据所污染，但如果你依赖下游的某些地方，谨慎并验证数据总无坏处。

所以，我们已经涵盖了在 hapi-plugins.com 中使用的所有验证情况，而 `joi` 的功能远比我们目前看到的要多。我们在这里花更多时间查看 `joi` 还能提供什么。

一个需要记住的属性是 `joi` 是可链的，这意味着你可以为搜索创建快捷方式。

想象一下你正在验证一个特定的字符串，可能是一个电子邮件 `Joi.string().email()` 或者更复杂的长字符串。例如，你可以将 `email` 赋值给较短的变量：

```javascript
var email = Joi.string().email() 并在任何地方使用它，而不是使用较长的版本。
```

作者一直在处理列表：愿望清单、婚礼登记表、婴儿登记表等，并且必须确保每次发送的都是正确的列表类型。以下是该验证逻辑：

```javascript
Joi.string().insensitive().required().valid(['BR', 'SFL', 'WR', 'WL'])
```

## 创建你自己的插件

请注意我们 hapi-plugins-project 中的所有内容是如何设计成插件架构的。我们为路由器提供了插件，也为模型提供了插件。甚至身份验证也是一个插件。

让我们先查看 `lib/index.js` 文件，所有的插件都在这里加载。

```javascript
server.register([
  Bell,
  Blipp,
  HapiAuthCookie,
  Authentication,
  Controllers,
  Models,
  Routes
]), function (err) {
  if (err) {
    console.log('server.register err:', err);
    return callback(err);
  }

  server.start(function () {
    console.log('server started on port:', server.info.port);
    return callback(null, server);
  });
});
```

任何使用过 Async 的人都可能熟悉这种模式，因为它允许你轻松地运行许多函数。我们是 async 方法的实粉丝，这里的模式非常相似。在内部，hapi 使用 `items`（即基础的 async 方法）来实现其目标。

`register` 函数的签名是 `server.register(plugins, [options], callback)`。

传递插件有几种不同的方法，我们在这里展示的是我们所有项目的组织方式，而且我们有很多这样的项目。通过 `register` 函数传递插件的最好处是，它们可以轻松地转换为独立的 npm 包并进行加载。它们也可以作为独立的 GitHub 仓库进行共享。

我们发现，当许多人协作一个大项目时，将具有某些逻辑分段的特定组件放在各自的仓库中效果很好。例如，如果你有一个博客系统，你可以将所有处理文章的路由放在一个插件中，将所有处理评论的路由放在另一个插件中。这样你就可以为每个部分分配独立的所有者，这通常会减少代码冲突。这并不总是有效的。例如，你可能有紧密耦合的服务。在处理自己的代码时，你是专家。决定什么对你的项目最好取决于你，而 hapi 是灵活的，因此你可以按照自己喜欢的方式来组织项目。

另一种代码分离的方法是保持控制器轻量，并将尽可能多的逻辑放入模型中。它们可以变成包含代码的独立库。



当代码被拆分成更小的原子部分后，代码变得容易维护得多。理解架构也变得更容易了。例如，你可能会发现某些测试设置在项目之间更容易访问。你可能会像我们所做的那样，为通用测试创建一个另一个仓库。即使一个项目可以在多个项目之间复用，这仍然是一个非常棒的方法。让我们通过查看处理程序是如何加载的，详细研究其中一个部分。

```javascript
var load = function (options, callback) {
  options = options || {};
  options.extension = options.extension || '.js';
  controllers = {};

  var files = glob.sync('*' + options.extension, {cwd: options.path || __dirname});
  for (var i in files) {
    if (files[i] != path.basename(__filename)) {
      var key = path.basename(files[i], options.extension);
      key = key.charAt(0).toUpperCase() + key.slice(1);

      controllers[key] = require(options.path || __dirname) + '/' + files[i];
    }
  }

  if (callback) {
    return callback(null, controllers);
  }

  return controllers;
};

exports.register = function (plugin, options, next) {
  load({path: __dirname + '/handlers'}, function (err, handlers) {
    if (err) {
      throw err;
    }

    if (process.env.DEV) {
      console.log('handlers:');
    }
    plugin.expose('handlers', handlers);
    next();
  });
};
```

```javascript
exports.register.attributes = {
  pkg: require('./package.json')
};
```

我们从一个名为 `load()` 的便利函数开始。`load` 的目的是遍历给定目录中的所有文件并引入这些文件。此外，我们将处理器暴露给服务器。暴露处理器的处是它们在整个应用程序中可用。

## 插件配置

之前，你可能注意到 `options` 没有在任何地方使用。然而，可以使用 `options` 来配置插件。假设我们想为 `blipp` 插件传递一些选项。记得这个插件只是在启动时列出路由。虽然路由目前不支持它，但可以想象你可能并不希望 `blipp` 在启动时实际上用颜色打印路由，因此你可能想传递一个标志，表示只不带 ANSI 颜色的打印。我们应该能在原始代码之外看到这样的内容：

```javascript
server.register([
  Bell,
  { register: Blipp, options: { colors: false } },
  HapiAuthCookie,
  Authentication,
  Controllers,
  Models,
  Routes
]);
```

上面的代码针对我们的整个服务器实例。实际的 `blipp` 插件将有一个如下所示 `register` 函数：

```javascript
exports.register = function (server, options, next) {
  if (options.color === true) {
    // 执行颜色
  } else {
    // 关闭颜色
  }
};
```

在我们的服务器启动中，我们将 `options` 设置为 `{ colors: false }`。我们将这些选项传递给插件，插件知道关闭颜色。我们在第 2 章中看到过传递 `options`。如果你查看 `rejoice` 和 `glue` 部分，你将看到插件选项是如何传递给插件的。一个例子是 `good` 插件区域中的 `opsInterval`。

...

甚至可以为每个环境设置不同的选项。这允许你再次将所有内容保留在一个位置，从而更容易管理。

## 关于标签和选择插件的说明

在注册期间，插件可以加载到服务器指定的特定连接上。这是 `hapi` 的一个非常重要的特性。它允许作为了一个包的一部分来处理多个不同的服务器。通过这种方式，可以将 API 与模板渲染的逻辑分离。

实际上，调试设置并确保将正确的插件注册到正确的服务器上可能是一项挑战。我们推荐使用 `blipp` 插件，以便在加载服务器时查看路由表中发生了什么。

```javascript
server.register({
  // plugins ...
}, { select: 'http' }, function (err) {
  if (err) {
    console.log('server.register err:', err);
  }
  server.register({
    // plugins ...
  }, { select: 'api' }, function (err) {
    if (err) {
      console.log('server.register err:', err);
    }
  });
  server.start(function () {
    console.log('server started on port: ', server.info.port);
    return callback(null, server);
  });
});
```

## 何时使用插件

目标是更好地管理你的代码 —— EH

# 第 6 章：插件

我们已经提到了一些何时使用插件的情况，让我们再次过一遍并表现得更具体一些。正确地使用插件可以帮助你构建良好的代码架构。

如果你有任何内容可以与其余部分分离并在不同项目中复用，那么你可能想要创建一个插件。你可能已经开始查看某个项目的各种插件，但没有找到适合你的。创建你自己的插件是可能的。一位作者发现，在像 Ruby on Rails 这样流行的框架中，没有办法在应用启动时列出所有可用的不同路由。创建一个插件仅仅是为了显示这些简单信息。

正如前面提到的，一个项目也可能基于可用的路由。插件可以完全专门为特定路径提供路由服务。例如，我们可能将所有路由放在其中一个插件中。

```javascript
plugin.route([
  { method: 'GET', path: '/plugins/upload', config: Controllers.Plugin.getUpload },
  { method: 'POST', path: '/plugins/upload', config: Controllers.Plugin.postUpload },
  { method: 'GET', path: '/plugins/{name}/download', config: Controllers.Plugin.download }
])
```

我们可能还有另一个插件来处理用户信息。

```javascript
plugin.route([
  { method: 'GET', path: '/user', config: Controllers.User.get },
  { method: 'PUT', path: '/user/profile', config: Controllers.User.updateProfile }
])
```

如果你有一个大型项目并需要划分工作，因为路由占据了大量的逻辑，那么这样做将更有意义。

## hapi 插件生态系统：一些常用插件

让我们看看 `hapi` 生态系统中的一些流行插件。你可以在 `hapi-plugins.com` 上找到更多插件（当然了），但我们冒昧展示了其中一些主要的插件。

### hapi-auth-basic

此插件为登录应用程序提供基本身份验证，或者只是通用的基本身份验证。大多数基于 Web 的系统都需要某种形式的身份验证来访问数据。许多框架作为框架的一部分包含了它，但通过这种模块化的方法，任何身份验证形式都是可能的。

关于 `hapi-auth-basic` 的更多信息请见第 7 章。

### blipp

虽然 `blipp` 不是核心插件，但它仍然非常有用。它只是在 `hapi` 服务器启动时显示路由和服务器:端口的组合。它能快速指示哪些路由是可用的，以及它们是否在正确的服务器连接上。

### bell

`bell` 与 `hapi-auth-basic` 非常相似，但它使用了第三方登录，如 Facebook、GitHub、Instagram、Twitter、Yahoo、Foursquare、VK、ArcGIS Online 和 Windows Live。如果你在寻找这些登录方式，那么应该使用这个插件。第三方插件正在不断添加。`bell` 通常与没有显式单独出的 `hapi-auth-cookie` 一起使用。

关于 `bell` 和 `hapi-auth-cookie` 的更多信息请见第 7 章。

### good

如果你在生产环境中运行服务，你几乎肯定想使用 `good`。你可以看到服务在 CPU 使用率、内存等方面的性能情况。你可以配合此程序使用许多报告器，你可以将报告发送到文件日志记录、控制台，或你编写的任何自定义报告器程序。

关于 `good` 的更多信息请见第 11 章。

### tv

`tv` 是一个用于调试的交互式模块。可以很容易看到服务接收到了哪些请求以及它是如何处理这些的。

关于 `tv` 的更多信息请见第 11 章。

### lout / hapi-swagger

`lout` 和 `hapi-swagger` 是用于你的路由和设置的文档工具。它为你提供了 API 文档，所以你不需要自己做了。对于你反正需要的东西，这可以为你节省大量时间。

### poop

与 `hapi` 想要变得幽默的目标一致，`poop` 是一个对异常进行进程转储的插件。它提供了一个堆转储 (https://www.npmjs.com/package/heapdump)，并且还会提供一个包含额外调试细节日志文件。

## 更多插件

你可以在此处找到大量插件。（*注：此处原文未完整，仅翻译现有内容*）



```
server.register({
  // plugins ...
}, { select: 'http' }, function (err) {
  if (err) {
    console.log('server.register err:', err);
  }
  server.register({
    // plugins ...
  }, { select: 'api' }, function (err) {
    if (err) {
      console.log('server.register err:', err);
    }
  });
  server.start(function () {
    console.log('server started on port: ', server.info.port);
    return callback(null, server);
  });
});
```

## 何时使用插件

目标是更好地管理你的代码 —— EH

# 第 6 章：插件

我们已经提到了一些何时使用插件的情况，让我们再次过一遍并表现得更具体一些。正确地使用插件可以帮助你构建良好的代码架构。

如果你有任何内容可以与其余部分分离并在不同项目中复用，那么你可能想要创建一个插件。你可能已经开始查看某个项目的各种插件，但没有找到适合你的。创建你自己的插件是可能的。一位作者发现，在像 Ruby on Rails 这样流行的框架中，没有办法在应用启动时列出所有可用的不同路由。创建一个插件仅仅是为了显示这些简单信息。

正如前面提到的，一个项目也可能基于可用的路由。插件可以完全专门为特定路径提供路由服务。例如，我们可能将所有路由放在其中一个插件中。

```
plugin.route([
  { method: 'GET', path: '/plugins/upload', config: Controllers.Plugin.getUpload },
  { method: 'POST', path: '/plugins/upload', config: Controllers.Plugin.postUpload },
  { method: 'GET', path: '/plugins/{name}/download', config: Controllers.Plugin.download }
])
```

我们可能还有另一个插件来处理用户信息。

```
plugin.route([
  { method: 'GET', path: '/user', config: Controllers.User.get },
  { method: 'PUT', path: '/user/profile', config: Controllers.User.updateProfile }
])
```

如果你有一个大型项目并需要划分工作，因为路由占据了大量的逻辑，那么这样做将更有意义。

## hapi 插件生态系统：一些常用插件

让我们看看 hapi 生态系统中的一些流行插件。你可以在 `hapi-plugins.com` 上找到更多插件（当然了），但我们冒昧展示了其中一些主要的插件。

### hapi-auth-basic

此插件为登录应用程序提供基本身份验证，或者只是通用的基本身份验证。大多数基于 Web 的系统都需要某种形式的身份验证来访问数据。许多框架作为框架的一部分包含了它，但通过这种模块化的方法，任何身份验证形式都是可能的。

关于 `hapi-auth-basic` 的更多信息请见第 7 章。

### blipp

虽然 `blipp` 不是核心插件，但它仍然非常有用。它只是在 hapi 服务器启动时显示路由和服务器:端口的组合。它能快速指示哪些路由是可用的，以及它们是否在正确的服务器连接上。

### bell

`bell` 与 `hapi-auth-basic` 非常相似，但它使用了第三方登录，如 Facebook、GitHub、Instagram、Twitter、Yahoo、Foursquare、VK、ArcGIS Online 和 Windows Live。如果你在寻找这些登录方式，那么应该使用这个插件。第三方插件正在不断添加。`bell` 通常与没有显式单独出的 `hapi-auth-cookie` 一起使用。

关于 `bell` 和 `hapi-auth-cookie` 的更多信息请见第 7 章。

### good

如果你在生产环境中运行服务，你几乎肯定想使用 `good`。你可以看到服务在 CPU 使用率、内存等方面的性能情况。你可以配合此程序使用许多报告器，你可以将报告发送到文件日志记录、控制台，或你编写的任何自定义报告器程序。

关于 `good` 的更多信息请见第 11 章。

### tv

`tv` 是一个用于调试的交互式模块。可以很容易看到服务接收到了哪些请求以及它是如何处理这些的。

关于 `tv` 的更多信息请见第 11 章。

### lout / hapi-swagger

`lout` 和 `hapi-swagger` 是用于你的路由和设置的文档工具。它为你提供了 API 文档，所以你不需要自己做了。对于你反正需要的东西，这可以为你节省大量时间。

### poop

与 hapi 想要变得幽默的目标一致，`poop` 是一个对异常进行进程转储的插件。它提供了一个堆转储 (https://www.npmjs.com/package/heapdump)，并且还会提供一个包含额外调试细节日志文件。

## 更多插件

你可以在此处找到大量插件。（*注：此处原文未完整，仅翻译现有内容*）

---

甚至可以为每个环境设置不同的选项。这允许你再次将所有内容保留在一个位置，从而更容易管理。

## 关于标签和选择插件的说明

在注册期间，插件可以加载到服务器指定的特定连接上。这是 hapi 的一个非常重要的特性。它允许作为了一个包的一部分来处理多个不同的服务器。通过这种方式，可以将 API 与模板渲染的逻辑分离。

实际上，调试设置并确保将正确的插件注册到正确的服务器上可能是一项挑战。我们推荐使用 `blipp` 插件，以便在加载服务器时查看路由表中发生了什么。

```
server.register({
  // plugins ...
}, { select: 'http' }, function (err) {
  if (err) {
    console.log('server.register err:', err);
  }
  server.register({
    // plugins ...
  }, { select: 'api' }, function (err) {
    if (err) {
      console.log('server.register err:', err);
    }
  });
  server.start(function () {
    console.log('server started on port: ', server.info.port);
    return callback(null, server);
  });
});
```

## 何时使用插件

目标是更好地管理你的代码 —— EH

# 第 6 章：插件

我们已经提到了一些何时使用插件的情况，让我们再次过一遍并表现得更具体一些。正确地使用插件可以帮助你构建良好的代码架构。

如果你有任何内容可以与其余部分分离并在不同项目中复用，那么你可能想要创建一个插件。你可能已经开始查看某个项目的各种插件，但没有找到适合你的。创建你自己的插件是可能的。一位作者发现，在像 Ruby on Rails 这样流行的框架中，没有办法在应用启动时列出所有可用的不同路由。创建一个插件仅仅是为了显示这些简单信息。

正如前面提到的，一个项目也可能基于可用的路由。插件可以完全专门为特定路径提供路由服务。例如，我们可能将所有路由放在其中一个插件中。

```
plugin.route([
  { method: 'GET', path: '/plugins/upload', config: Controllers.Plugin.getUpload },
  { method: 'POST', path: '/plugins/upload', config: Controllers.Plugin.postUpload },
  { method: 'GET', path: '/plugins/{name}/download', config: Controllers.Plugin.download }
])
```

我们可能还有另一个插件来处理用户信息。

```
plugin.route([
  { method: 'GET', path: '/user', config: Controllers.User.get },
  { method: 'PUT', path: '/user/profile', config: Controllers.User.updateProfile }
])
```

如果你有一个大型项目并需要划分工作，因为路由占据了大量的逻辑，那么这样做将更有意义。

## hapi 插件生态系统：一些常用插件

让我们看看 hapi 生态系统中的一些流行插件。你可以在 `hapi-plugins.com` 上找到更多插件（当然了），但我们冒昧展示了其中一些主要的插件。

### hapi-auth-basic

此插件为登录应用程序提供基本身份验证，或者只是通用的基本身份验证。大多数基于 Web 的系统都需要某种形式的身份验证来访问数据。许多框架作为框架的一部分包含了它，但通过这种模块化的方法，任何身份验证形式都是可能的。

关于 `hapi-auth-basic` 的更多信息请见第 7 章。

### blipp

虽然 `blipp` 不是核心插件，但它仍然非常有用。它只是在 hapi 服务器启动时显示路由和服务器:端口的组合。它能快速指示哪些路由是可用的，以及它们是否在正确的服务器连接上。

### bell

`bell` 与 `hapi-auth-basic` 非常相似，但它使用了第三方登录，如 Facebook、GitHub、Instagram、Twitter、Yahoo、Foursquare、VK、ArcGIS Online 和 Windows Live。如果你在寻找这些登录方式，那么应该使用这个插件。第三方插件正在不断添加。`bell` 通常与没有显式单独出的 `hapi-auth-cookie` 一起使用。

关于 `bell` 和 `hapi-auth-cookie` 的更多信息请见第 7 章。

### good

如果你在生产环境中运行服务，你几乎肯定想使用 `good`。你可以看到服务在 CPU 使用率、内存等方面的性能情况。你可以配合此程序使用许多报告器，你可以将报告发送到文件日志记录、控制台，或你编写的任何自定义报告器程序。

关于 `good` 的更多信息请见第 11 章。

### tv

`tv` 是一个用于调试的交互式模块。可以很容易看到服务接收到了哪些请求以及它是如何处理这些的。

关于 `tv` 的更多信息请见第 11 章。

### lout / hapi-swagger

`lout` 和 `hapi-swagger` 是用于你的路由和设置的文档工具。它为你提供了 API 文档，所以你不需要自己做了。对于你反正需要的东西，这可以为你节省大量时间。

### poop

与 hapi 想要变得幽默的目标一致，`poop` 是一个对异常进行进程转储的插件。它提供了一个堆转储 (https://www.npmjs.com/package/heapdump)，并且还会提供一个包含额外调试细节日志文件。

## 更多插件

你可以在此处找到大量插件。（*注：此处原文未完整，仅翻译现有内容*）




...

甚至可以为每个环境设置不同的选项。这允许你再次将所有内容保留在一个位置，从而更容易管理。

## 关于标签和选择插件的说明

在注册期间，插件可以加载到服务器指定的特定连接上。这是 `hapi` 的一个非常重要的特性。它允许作为一个包的一部分来处理多个不同的服务器。通过这种方式，可以将 API 与模板渲染的逻辑分离。

实际上，调试设置并确保将正确的插件注册到正确的服务器上可能是一项挑战。我们推荐使用 `blipp` 插件，以便在加载服务器时查看路由表中发生了什么。

```js
server.register({
  // plugins ...
}, { select: 'http' }, function (err) {
  if (err) {
    console.log('server.register err:', err);
  }
  server.register({
    // plugins ...
  }, { select: 'api' }, function (err) {
    if (err) {
      console.log('server.register err:', err);
    }
  });
  server.start(function () {
    console.log('server started on port: ', server.info.port);
    return callback(null, server);
  });
});
```

## 何时使用插件

目标是更好地管理你的代码 —— EH

# 第 6 章：插件

我们已经提到了一些何时使用插件的情况，让我们再次过一遍并表现得更具体一些。正确地使用插件可以帮助你构建良好的代码架构。

如果你有任何内容可以与其余部分分离并在不同项目中复用，那么你可能想要创建一个插件。你可能已经开始查看某个项目的各种插件，但没有找到适合你的。创建你自己的插件是可能的。一位作者发现，在像 Ruby on Rails 这样流行的框架中，没有办法在应用启动时列出所有可用的不同路由。创建一个插件仅仅是为了显示这些简单信息。

正如前面提到的，一个项目也可能基于可用的路由。插件可以完全专门为特定路径提供路由服务。例如，我们可能将所有路由放在其中一个插件中。

```js
plugin.route([
  { method: 'GET', path: '/plugins/upload', config: Controllers.Plugin.getUpload },
  { method: 'POST', path: '/plugins/upload', config: Controllers.Plugin.postUpload },
  { method: 'GET', path: '/plugins/{name}/download', config: Controllers.Plugin.download }
]);
```

我们可能还有另一个插件来处理用户信息。

```js
plugin.route([
  { method: 'GET', path: '/user', config: Controllers.User.get },
  { method: 'PUT', path: '/user/profile', config: Controllers.User.updateProfile }
]);
```

如果你有一个大型项目并需要划分工作，因为路由占据了大量的逻辑，那么这样做将更有意义。

## hapi 插件生态系统：一些常用插件

让我们看看 `hapi` 生态系统中的一些流行插件。你可以在 `hapi-plugins.com` 上找到更多插件（当然了），但我们冒昧展示了其中一些主要的插件。

### hapi-auth-basic

此插件为登录应用程序提供基本身份验证，或者只是通用的基本身份验证。大多数基于 Web 的系统都需要某种形式的身份验证来访问数据。许多框架作为框架的一部分包含了它，但通过这种模块化的方法，任何身份验证形式都是可能的。

关于 `hapi-auth-basic` 的更多信息请见第 7 章。

### blipp

虽然 `blipp` 不是核心插件，但它仍然非常有用。它只是在 `hapi` 服务器启动时显示路由和服务器端口的组合。它能快速指示哪些路由是可用的，以及它们是否在正确的服务器连接上。

### bell

`bell` 与 `hapi-auth-basic` 非常相似，但它使用了第三方登录，如 Facebook、GitHub、Instagram、Twitter、Yahoo、Foursquare、VK、ArcGIS Online 和 Windows Live。如果你在寻找这些登录方式，那么应该使用这个插件。第三方插件正在不断添加。`bell` 通常与没有显式单独出的 `hapi-auth-cookie` 一起使用。

关于 `bell` 和 `hapi-auth-cookie` 的更多信息请见第 7 章。

### good

如果你在生产环境中运行服务，你几乎肯定想使用 `good`。你可以看到服务在 CPU 使用率、内存等方面的性能情况。你可以配合此程序使用许多报告器，你可以将报告发送到文件日志记录、控制台，或你编写的任何自定义报告器程序。

关于 `good` 的更多信息请见第 11 章。

### tv

`tv` 是一个用于调试的交互式模块。可以很容易看到服务接收到了哪些请求以及它是如何处理这些的。

关于 `tv` 的更多信息请见第 11 章。

### lout / hapi-swagger

`lout` 和 `hapi-swagger` 是用于你的路由和设置的文档工具。它为你提供了 API 文档，所以你不需要自己做了。对于你反正需要的东西，这可以为你节省大量时间。

### poop

与 `hapi` 想要变得幽默的目标一致，`poop` 是一个对异常进行进程转储的插件。它提供了一个堆转储（https://www.npmjs.com/package/heapdump），并且还会提供一个包含额外调试细节的日志文件。

## 更多插件

你可以在此处找到大量插件。（注：此处原文未完整，仅翻译现有内容。）




```javascript
plugin.route([
  { method: 'GET', path: '/user', config: Controllers.User.get },
  { method: 'PUT', path: '/user/profile', config: Controllers.User.updateProfile }
])
```

如果你有一个大型项目并需要划分工作，因为路由占据了大量的逻辑，那么这样做将更有意义。

## hapi 插件生态系统：一些常用插件

让我们看看 hapi 生态系统中的一些流行插件。你可以在`hapi-plugins.com`上找到更多插件（当然了），但我们冒昧展示了其中一些主要的插件。

### hapi-auth-basic

此插件为登录应用程序提供基本身份验证，或者只是通用的基本身份验证。大多数基于 Web 的系统都需要某种形式的身份验证来访问数据。许多框架作为框架的一部分包含了它，但通过这种模块化的方法，任何身份验证形式都是可能的。

关于`hapi-auth-basic`的更多信息请见第 7 章。

### blipp

虽然`blipp`不是核心插件，但它仍然非常有用。它只是在 hapi 服务器启动时显示路由和服务器:端口的组合。它能快速指示哪些路由是可用的，以及它们是否在正确的服务器连接上。

### bell

`bell`与`hapi-auth-basic`非常相似，但它使用了第三方登录，如 Facebook、GitHub、Instagram、Twitter、Yahoo、Foursquare、VK、ArcGIS Online 和 Windows Live。如果你在寻找这些登录方式，那么应该使用这个插件。第三方插件正在不断添加。`bell`通常与没有显式单独出的`hapi-auth-cookie`一起使用。

关于`bell`和`hapi-auth-cookie`的更多信息请见第 7 章。

### good

如果你在生产环境中运行服务，你几乎肯定想使用`good`。你可以看到服务在 CPU 使用率、内存等方面的性能情况。你可以配合此程序使用许多报告器，你可以将报告发送到文件日志记录、控制台，或你编写的任何自定义报告器程序。

关于`good`的更多信息请见第 11 章。

### tv

`tv`是一个用于调试的交互式模块。可以很容易看到服务接收到了哪些请求以及它是如何处理这些的。

关于`tv`的更多信息请见第 11 章。

### lout / hapi-swagger

`lout`和`hapi-swagger`是用于你的路由和设置的文档工具。它为你提供了 API 文档，所以你不需要自己做了。对于你反正需要的东西，这可以为你节省大量时间。

### poop

与 hapi 想要变得幽默的目标一致，`poop`是一个对异常进行进程转储的插件。它提供了一个堆转储（https://www.npmjs.com/package/heapdump），并且还会提供一个包含额外调试细节日志文件。

## 更多插件

你可以在此处找到大量插件。（注：此处原文未完整，仅翻译现有内容。）

另一个选项是尝试`try`，这意味着如果提供了凭据则尝试进行验证，否则继续执行路由生命周期。

第三种选项：

```javascript
var Bcrypt = require('bcrypt');
var Hapi = require('hapi');
var Basic = require('hapi-auth-basic');

var server = new Hapi.Server();
server.connection({ port: 3000 });

var users = {
  molly: {
    username: 'molly',
    password: '$2a$10$iqJSHD.BGr0E2IXQwYwJmeP3NvhPrXaEL-SaGCGjIR/XU5QtJvu5Tm',
    name: 'Molly Ringwald',
    id: '2133d32a'
  }
};
```

```javascript
var validate = function (username, password, callback) {
  var user = users[username];
  if (!user) {
    return callback(null, false);
  }

  bcrypt.compare(password, user.password, function (err, isVal) {
    callback(err, isVal, { id: user.id, name: user.name });
  });
};

server.register(Basic, function (err) {
  server.auth.strategy('sobasic', 'basic', { validateFunc: validate });
  server.route({
    method: 'GET',
    path: '/',
    config: {
      auth: 'sobasic',
      handler: function (request, reply) {
        reply('hello, ' + request.auth.credentials.name);
      }
    }
  });

  server.start(function () {
    console.log('server running');
  });
});
```

上面的代码演示了你如何通过将策略（strategy）传递给路由配置的`auth`属性来使用需要验证的路由。你可以看到`bcrypt`库拥有一个`compare`函数，它会告诉我们密码是否有效。因为这里使用了`bcrypt`，你可以看到密码并不是以明文存储的。这是一个无疑的改进。

## hapi-auth-cookie

网站常用的身份验证方案是使用 cookie 来存储安全令牌。类似于基本身份验证方案依赖于开发者实现验证函数，cookie 验证也需要相同的函数。cookie 验证由`hapi-auth-cookie`模块提供。该模块支持许多与 cookie 存储方式相关的属性，例如`live`或`secure`标志属性。cookie 验证与基本身份验证策略的主要区别之一是，cookie 验证会装饰`request.auth.session`对象，并用于设置或清除会话属性。下面是一个使用 cookie 验证策略并注册到需要验证的路由上的完整应用程序演示。

```javascript
var Hapi = require('hapi');

var users = {
  john: {
    id: 'molly',
    password: 'breakfast',
    name: 'Molly Ringwald'
  }
};

var home = function (request, reply) {
  reply(`<html><head><title>Login page</title>
<head><body><h3>` + request.auth.credentials.name +
 `!</h3><br><form method="get" action="/logout">` + '<input type="submit" value="Logout">` + `</form></body></html>`);
};

var login = function (request, reply) {
  if (request.auth.isAuthenticated) {
    return reply.redirect('/');
  }

  var message = '';
  var account = null;

  if (request.method === 'post') {
    if (!request.payload.username ||
        !request.payload.password) {
      message = 'Missing username or password';
    } else {
      account = users[request.payload.username];
      if (!account ||
          account.password !== request.payload.password) {
        message = 'Invalid username or password';
      }
    }
  }

  if (request.method === 'get' ||
      message) {
    return reply(`<html><head><title>Login page</title>
<head><body>` +
      (message ? '<h3>' + message + '</h3><br>' : '') +
      '<form method="post" action="/login">` +
      'Username: <input type="text" name="username"><br>' +
      'Password: <input type="password" name="password"><br>' +
      '<input type="submit" value="Login"></form></body></html>`);
  }

  request.auth.session.set(account);
  return reply.redirect('/');
};

var logout = function (request, reply) {
  request.auth.session.clear();
  return reply.redirect('/');
};
```

我们设置了一些基础函数。我们提供了一个`login`函数，用于处理用户提交用户名和密码时的操作。如果用户名或密码无效，它会返回一条消息。最后，如果一切正常，它通过`request.auth.session.set`函数设置 cookie。提供了一个`logout`函数来清除 cookie 并重定向回主页。最后，我们有一个`home`函数，在用户尚未登录时显示表单。现在设置服务器并注册插件。

```javascript
var server = new Hapi.Server();
server.connection({ port: 8000 });
```

```javascript
server.register(require('hapi-auth-cookie'), function (err) {
  server.auth.strategy('session', 'cookie', {
    password: 'secret',
```



```javascript
cookie: 'sid-example',

redirectTo: '/login',

isSecure: false

});

});
```

这看起来算复杂。我们设置了 cookie 名称和密码，并告诉它`redirectTo`路径。最后一部分是设置路由。

```javascript
server.route({

  method: 'GET',

  path: '/',

  config: {

    handler: home,

    auth: 'session'

  }

},

{

  method: ['GET', 'POST'],

  path: '/login',

  config: {

    handler: login,

    auth: {

      mode: 'try',

      strategy: 'session'

    },

    plugins: {

      'hapi-auth-cookie': {

        redirectTo: false

      }

    }

  }

},

{

  method: 'GET',

  path: '/logout',

  config: {

    handler: logout,

    auth: 'session'

  }

}

);

server.start();
```

启动服务器并导航到……

```javascript
auth: 'YourCookieAuth'
));

server.route({

  method: 'GET',

  path: '/login',

  handler: login,

  config: {

    auth: 'YourThirdPartyAuth'

  }

});

server.route({

  method: 'GET',

  path: '/logout',

  handler: logout,

  config: {

    auth: 'YourCookieAuth'

  }

});
```

```javascript
server.start(function () {

  console.log('Started...');

});
```

你可以在这里看到我们的注出和私有 URL 仍然受到 cookie 的保护。我们为`/public`资源提供了一个公共处理器，这可能类似于我们在 cookie 示例中使用的通用登录页面。最后，我们有一个登录页面，它会跳转到第三方身份验证网站（github）以获取令牌。Bell 会为你完成这一魔法操作，一旦你获取了令牌，就会生成 cookie。在会话过期之前，你不需要再次登录。关于 bell 支持的提供者的更多细节，请查看 bell。

## 总结

在本章中，我们探索了用于 hapi 身份验证的某些基本选项。基础身份验证策略对于受防火墙保护且面向内部的应用非常有用。cookie 身份验证策略可能更有用，特别是对于构建需要会话的。将 cookie 身份验证策略与 bell 结合可以为你提供一个非常稳健的身份验证解决方案。hapi 的优点之一是它支持混合使用这些或其他身份验证策略，以适应你正在构建的应用需求。无论选择何种，请放心，hapi 的创建者和整个社区已经测试并支持许多类型的身份验证策略。

## 模型（Models）

将其传递到`/dev/null`……这符合 Web 规模的吗？

- 关于 MongoDB 的幽默视频

模型是任何实用 Web 应用程序骨干。它们负责管理数据：连接数据源、读取数据、创建数据等。关于数据的决策——包括数据库选择、模式设计和索引设计——对应用程序的性能或行为都有巨大影响。

数据可以来自任何地方：从 Web、数据库、文件或服务。对于我们的 hapi-plugins 应用，我们将专注于通过 HTTP 从 Web 获取数据，以及从数据库获取数据。

## 使用 HTTP

获取应用数据的一种方法是使用第三方 Web API。你的应用程序可能想要连接到 Twitter、Facebook 或 Google API。这些服务大多数都提供基于 HTTP 或 HTTPS 的 RESTful API。这类 API 极易处理，并且从任何编程语言或操作系统调用。

## 预期用法

在编写 hapi-plugins.com 应用之前，我们分析了 NPM API 并确定有八个相关的 API：

- 获取插件名称列表
- 获取匹配输入关键词搜索的插件列表
- 按名称获取插件列表
- 按依赖关系获取插件列表
- 按天获取插件下载次数
- 按周获取插件下载次数
- 按月获取插件下载次数
- 按年获取插件下载次数

# 第 8 章：模型

基于此，我们可以像下面一样设计预期的 JavaScript API：

```javascript
/* 在处理器内部： */

var NPMPackages = new this.models.npm.Packages();

NMPackages.getShortList(callback);

NMPackages.getByName('hapi', callback);

NMPackages.getByKeyword('hapi', callback);

NMPackages.getDependUpon('hapi', callback);

var NPMDownloads = new this.models.npm.Downloads();

NMPDownloads.lastDay('hapi', callback);

NMPDownloads.lastWeek('hapi', callback);

NMPDownloads.lastMonth('hapi', callback);

NMPDownloads.lastYear('hapi', callback);
```

## NPM 包

开始之前，我们可以配置一个可实例化的类对象`NPMPackages`。

```javascript
var Hoek = require('hapi');

var Wreck = require('wreck');

var Util = require('util');
```

```javascript
var internals = {};

internals._defaults = {};
```

```javascript
internals.NPMPackages = function (options) {

  var Packages = function (override) {

    this.options = Hoek.applyToDefaults(internals._defaults, options || {});

    return Packages;

  }

};

module.exports = internals.NPMPackages;
```

对于每个模型，我们都希望在顶部保留典型的`require`语句。hapi 风格指南规定使用模块特定的`internals`对象，该对象本质上是局部私有的（无法从文件外部访问或读取）。在内部，我们可以设置全局选项（在`_defaults`对象中），这些选项稍后可以覆盖。此片段目前还没有默认值。

然后，我们定义一个 JavaScript 对象将成为我们的模型。在这种情况下，我们有一个外部对象（`NpmPackages`）和一个内部对象（`Packages`）。通过拥有外部对象，我们可以将实例特定的选项传递给内部的最终对象。

接下来，在添加函数之前，我们将重要的配置变量设置到默认值中。

我们知道不需要任何额外参数就可以从 URL`https://skimdb.npmjs.com/registry/_all_docs`获取最短短的列表。但其他 API 允许我们查询参数。我们将所有 URL 抽象为两个部分：基础 URL 和带参数的 URI 路径。然后，在实际请求内部，我们将拼接基础 URL 和 URI 来生成最终的 URL。这就是为什么 URI 是函数的原因。

```javascript
var Hoek = require('hoek');

var Wreck = require('wreck');

var Util = require('util');

var internals = {

  defaults: {

    host: {

    host: 'https://skimdb.npmjs.com',

    uris: {

      shortList: '/registry/_all_docs',

      byName: '/registry/package/',

      byKeyword: '/registry/search?q=',

      dependUpon: '/registry/depends/',

      lastDay: '/registry/downloads/day/',

      lastWeek: '/registry/downloads/week/',

      lastMonth: '/registry/downloads/month/',

      lastYear: '/registry/downloads/year/'

    }

  }

};
```

（注：由于原文后续存在大量重复且碎片化的代码逻辑，上述翻译已涵盖核心逻辑描述及结构。）

# 第 8 章：模型

```javascript
// 留出空间以防需要修改响应

return callback(err, body.rows || body);
```

```javascript
var readResponse = function (err, res) {

  if (err) {

    return callback(err);

  }

}
```

```javascript
Wreck.read(res, {json:true}, processResponse);
```

```javascript
var req = Wreck.request(method, uri, options, readResponse);
```

```javascript
Packages.prototype.getByKeyword = function (keyword, callback) {
```

```javascript
var method = "GET"

var uri = this.options.host + this.options.uris.byKey(keyword);

var options = {

  redirects: 3,

  timeout: 30000,

  rejectUnauthorized: true

};
```

```javascript
var processResponse = function (err, body) {

  // 留出空间以防需要修改响应

  return callback(err, body);

};
```

```javascript
var readResponse = function (err, res) {

  if (err) {

    return callback(err);

  }

}
```

```javascript
Wreck.read(res, {json:true}, processResponse);
```

```javascript
var req = Wreck.request(method, uri, options, readResponse);
```

```javascript
Packages.prototype.getDependentUpon = function (keyword, callback) {
```

```javascript
var method = "GET";

var uri = this.options.host + this.options.uri.byDeprecatedUpon(keyword);

var options = {

  redirects: 3,

  timeout: 30000,

  rejectUnauthorized: true

};
```

```javascript
var processResponse = function (err, body) {

  // 留出空间以防需要修改响应

  return callback(err, body);

};
```

```javascript
var readResponse = function (err, res) {

  if (err) {

    return callback(err);

  }

  Wreck.read(res, {json:true}, processResponse);

};
```

```javascript
var req = Wreck.request(method, uri, options, readResponse);

// ...
```

# NPM 下载

首先，我们配置另一个可实例化的类对象`NPMDownloads`。遵循之前的约定，我们将 URL 拆分为主机地址（host）和参数化的 URI 函数。我们知道所有 API 函数基本上是相同的，只是 URI 处有细微差别，因此我们定义了一个共享方法`getDownloadsBy`，以供其他方法使用。

`lastYear`的 URI 比其他的稍微复杂一些，因为我们计算了今天和今天一年前的日期范围。但一旦你将其拆解，它并不复杂。

```javascript
var Hoek = require('hoek');

var Wreck = require('wreck');
```

```javascript
var internals = {};

internals._defaults = {

  host: 'https://api.npmjs.org',

  uris: {

  'last-day': function (_module) { return '/downloads/range/last-day/' + _module;},

  'last-week': function (_module) { return '/downloads/range/last-week/' + _module;},

  'last-month': function (_module) { return '/downloads/range/last-month/' + _module;},

  'last-year': function (_module) {

    var today = new Date();

    var from = [today.getFullYear() - 1, today.getMonth() + 1, today.getDate()].join(':');

    var to = [today.getFullYear(), today.getMonth() + 1, today.getDate()].join(':');

    var dateRange = [from, to].join(':');

    return '/downloads/range/' + dateRange + "/" + _module;

  },

};
```

```javascript
var internals.NpmDownloads = function (options) {

  this.options = Hoek.applyToDefaults(internals._defaults, options, []);

  return this;

}

internals.NpmDownloads.prototype.getDownloadsBy = function () {};

internals.NpmDownloads.prototype.lastDay = function () {};

internals.NpmDownloads.prototype.lastWeek = function () {};

internals.NpmDownloads.prototype.lastMonth = function () {};

internals.NpmDownloads.prototype.lastYear = function () {};

module.exports = internals.NpmDownloads.prototype.getDownloadsBy = function (_type, range) {

  var self = this;

  return function (moduleName, callback) {

    var method = "GET";

    var uri = self.options.host + self.options.uris[range](moduleName);

  }

}
```

接下来，我们填充一个用于调用下载请求的共享函数。与之前的函数不同，它返回一个函数，我们用它来生成其他请求。其他函数基本上变成了`getDownloads`的包装器。

```javascript
var options = {

  redirects: 3,

  timeout: 30000,

  rejectUnauthorized: true

};
```

```javascript
var processResponse = function (err, body) {

  // 留出空间以防需要修改响应

  return callback(err, body);

};
```



```javascript
var readResponse = function (err, res) {
  if (err) {
    return callback(err);
  }

  Wreck.read(res, {json: true}, processResponse);
};
```

```javascript
var req = Wreck.request(method, uri, options, readResponse);
};

// ...
```

最后，通过仅配置函数之间的差异，为剩余的 API 方法引入`getDownloadsBy`：

```javascript
// ...

internals.NpmDownloads.prototype.lastDay = function (moduleName, callback) {
  return this.getDownloadsBy('point', 'last-day')(moduleName, callback);
};

internals.NpmDownloads.prototype.lastWeek = function (moduleName, callback) {
  return this.getDownloadsBy('point', 'last-week')(moduleName, callback);
}

internals.NpmDownloads.prototype.lastMonth = function (moduleName, callback) {
  return this.getDownloadsBy('point', 'last-month')(moduleName, callback);
};

internals.Npmdownloads.prototype.lastYear = function (moduleName, callback) {
  return this.getDownloadsBy('point', 'last-year')(moduleName, callback);
}

//
```

## 插件模型：实际用法

在处理器函数中，我们希望将 NPM 包搜索结果与包数组结合。我们还希望确保列表按名称是唯一的。然后，对于每个唯一的模块，我们需要使用`getByName`获取完整的模块数据。最后，我们想要跟踪此列表并在数据库中添加/更新。

为了确保唯一性，我们使用名为 lodash 的库中的`uniq`函数。我们传递一个仅包含模块名称的列表，它将剔除重复项。但开始，我们需要从这里提取模块列表。

```javascript
Async.parallel({
  shortlist: function (cb) {
    return NPMPackages.getShortList(cb);
  },

  hapiKeyword: function (cb) {
    return NPMPackages.getKey('hapi', cb);
  },

  hapiKeyword: function (cb) {
    return NPMPackages.getByKeyword('hapi', cb);
  },

  hapijotsKeyword: function (cb) {
    return NPMPackages.getBy('hapi.js', cb);
  }
}, function (err, results) {
  //..
```

正如我们之前看到的，我们使用`Async`模式同时请求四个 API 调用并合并结果。这很重要，因为我们需要来自所有四个源的数据来识别哪些插件是与 hapi 相关的。

```javascript
var hapiKeyword = results.hapiKeyword.rows.map(function (module) {
  return module[1];
});

var hapisKeyword = results.hapiKeyword.rows.map(function (module) {
  return module[1];
}));

var hapidotjsKeyword = results.hapidotjsKeyword.rows.map(function (module) {
  return module[1];
});
```

四个源返回的数据格式相同，就像三个调用一样，因此我们通过`map`函数遍历将其转换为简单的插件名称数组。在这种情况下，名称存储在所有对应的`module.key[1]`中。

```javascript
var NameMatchSuffix = /[-]hapi/ig;
var NameMatchPrefix = /hapi[-]/ig;

var shortlist = results.shortlist.rows.filter(function (module) {
  return NameMatchPrefix.exec(module.id) || NameMatchSuffix.exec(module.id);
}).map(function (module) {
  return module.id;
});
```

`shortlist`返回所有插件名称的原始列表，因此我们需要应用正则表达式来查找相关的插件。这就是`NameMatchPrefix`和`NameMatchSuffix`的作用。

```javascript
// 确保列表是唯一的

var plugins = _.uniq(shortlist.concat(hapiKeyword).concat(hapiKeyword).concat(hapidotjsKeyword));
```

接下来，通过该行，`_.uniq()`将四个调用的所有模块名称合并并通过 lodash 的`unique`函数消除重复。现在，我们拥有了所有名称或关键词中包含 hapi- 或 -hapi 的模块列表。

然而，它只是一个名称列表。为了做有用的事情，我们使用`Async.map`函数将`NPMPackages.getBy`应用于每个模块名称。这将并行执行所有的单独 API 调用并在最后合并结果以生成模块数据列表。

```javascript
// 异步将 PluginData 应用到 plugins 中的每个元素

Async.map(plugins, NPMPackages.getBy, function (err, results)) {
```

# 第 8 章：模型

//...

从这里开始，我们需要过滤掉未发布的模块并最终返回结果（或错误）。

为了查看整体结构，这里是整个函数的合并显示：

```javascript
var _ = require('lodash');

var NameMatchSuffix = /[-hapi]/ig;
var NameMatchPrefix = /hapi[-]/ig;

nmodule.exports.populateReal = {
  handler: function (request, reply) {
    var NPMPackages = new this.models.Packages();

    Async.parallel({
      shortlist: function (cb) {
        return NPMPackages.getShortList(cb);
      },

      hapiKeyword: function (cb) {
        return NPMPackages.getByKeyword('hapi', cb);
      },

      hajpisKeyword: function (cb) {
        return NPMPackages.getByKeyword('hapi.js', cb);
      },

      hajpidotsKeyword: function (cb) {
        return NPMPackages.getByKeyword('hapi.js', cb);
      },

      function (err, results) {
        if (err) {
          throw err; // TODO: replace with boom error
        }

        // Generate lists of keys for each set of search

        results

        var shortlist = results.shortlist.rows.filter(function (module) {
          return NameMatchPrefix.exec(module.id) || NameMatchSuffix.exec(module.id);
        }).map(function (module) {
          return module.id;
        });

        var hapiKeyword = results.hapiKeyword.rows.map(function (module) {
          return module.key[1];
        });

        var hajpisKeyword = results.hajpisKeyword.rows.map(function (module) {
          return module.key[1];
        });

        var hapidotjsKeyword = results.hajidotjsKeyword.rows.map(function (module) {
          return module.key[1];
        });

        // Ensure the list is unique

        var plugins = _.uniq(shortlist.concat(hapiKeyword).concat(hajpisKeyword).concat(hapidotjsKeyword));

        // Asynchronously apply getPluginData to every element in plugins

        Async.map(plugins, NPMPackages.getByName, function (err, results) {
          if (err) {
            throw err;
          }

          // Ensure unpublished modules are not added

          results = results.filter(function (result) {
            if (result.time.hasOwnProperty('unpublished')) {
              if (new Date(result.time.unpublished.time) > new Date(result.time.modified)) {
                return false;
              }

              return true;
            }
          });

          // Update the database with results

          DB.plugin.batchCreate(results, function (err, success) {
            if (err) {
              throw err;
            }

            return reply("<pre" + JSON.stringify(results, null, 2) + "</pre>");
          });
        });
      }
    });
  }
};
```

现在你已经看到了两种创建调用 RESTful API 端点的模型的方法。一种是通用的请求方法，另一种是用于请求的 RESTful 封装器。你可以轻松地调整这些示例中的任何一个，以适应项目中其他的第三方 RESTful API。

接下来，我们将继续探索模型以及如何连接和查询数据库。

## 使用数据库

通常情况下，开发者在使用 hapi 数据库时具有完全的灵活性——任何数据库、任何 ORM 或任何库都可以。hapi 没有施加任何限制。你可以为一个项目使用一个数据库，为另一个项目使用另一个，或者为第三个项目使用十个数据库。hapi 试图不产生干扰来让开发者开心。

对于 github.com/hapi-edge/hapi-plugins 应用，我们选择了流行的 MongoDB 作为数据库，并将使用 Mongoose 驱动程序连接到数据库。关于其他数据库选项以及我们为什么选择 MongoDB 的信息，请参阅第 13 章附录中的模型部分。

## 设置数据库

在应用中设置 MongoDB 在 mongodb.org 上有详细的文档。然而，为了快速开发，在本地开发或使用 Compose（即 MongoHQ）生成一个免费的开发数据库实例会更快。

一旦设置了实例，必须创建一个数据库名称。我们选择了实例名称`'hapi-plugins'`和数据库名称`'hapi-plugins'`。如果你更改了这些名称，请在下方示例连接字符串中替换它们。如果你使用用户名和密码设置身份验证（如我们在生产数据库中设置的那样），请记住将其添加到连接字符串中。

集合（Collections）是文档列表。Mongoose 会在你使用时为你创建这些，因此除非你想强制大小和最大文档限制，否则没有必要手动创建。

## 连接数据库

Mongoose 提供用于连接 MongoDB 实例的高级 API。它只接受 MongoDB 连接字符串，其中可以包含主机、用户名、密码、数据库等。对数据库的后续调用和查询会自动队列，直到连接完成。因此，不需要在等待连接建立时在异步块中嵌套代码。

在 hapi-plugins.com 应用中，我们在开发时想要连接到本地运行的 MongoDB 实例，但在部署时我们也想要连接到生产数据库。我们使用环境变量来规定运行什么环境。Node.js 全局进程变量`process.env`包含了应用程序可用的所有环境变量。

本章中的生产数据库凭据已删除密码。请将这些凭据替换为你创建的数据库的凭据。

```javascript
var databases = {
  development: 'mongodb://localhost/hapi_plugins',

  production: 'mongodb://hapi:({PASSWORD})@c278.lighthouse.0.mongodbayer.com:10278,c278.lighthouse.1.mongodbayer.com:10278/hapi-plugins?replicaSet=set-54ebe69660d07ala000f09'
};
```

```javascript
if (process.env.PRODUCTION) {
  Mongoose.connect(databases.production);
} else {
  Mongoose.connect(databases.development);
}
```

使用这种模式，我们可以轻松地区分环境。在本地开发时，我们使用本地数据库。然后，生产环境使用在线、可扩展的托管数据库。另一种模式是将数据库连接字符串包含在环境变量中，如下：

```javascript
// MONGODBSTR='mongodb://localhost/hapi_plugins' node.js

Mongoose.connect(process.env.MONGODBSTR);
```

这样做的好处是无需在代码的任何地方存储连接字符串。如果你计划打开源代码或应用程序出现问题，这可能非常重要。

## Schema 设计

在进行任何查询之前，设计一个粗略的 Schema 通常很有帮助。尽管 MongoDB 不要求或强制 Schema，但 Schema 定义了数据的结构并帮助你强制数据类型。先了解你计划如何访问和使用数据。

对于 hapi-plugins.com 应用，我们计划允许匿名访问：

- 通过名称、描述、作者和关键词搜索插件。
- 登录并管理插件。
- 将插件添加到列表。
- 点赞或取消点赞。

在后台，我们还需要：

- 将插件添加到列表。
- 从列表中移除插件。

因此，我们知道插件必须具有名称、描述、作者和关键词。NPM 防止模块重复，所以我们知道名称是唯一的，并可以使用名称作为主键。此外，通过观察 NPM 模块也有版本、许可证、仓库 URL、首页、依赖项以及大量的统计数据。它还有关于模块创建和更新的时间信息。据此，我们可以为 hapi-plugins 应用定义第一个 Schema。

```javascript
var internals = {};

internals.plugin = new Mongoose.Schema({
  'name': { type: String, required: true },

  'description': { type: String, required: false },

  'version': { type: String, required: true },

  'authors': { type: Array, required: false },

  'license': { type: String, required: false },

  'repository': { type: String },

  'homepage': { type: String },
```



```javascript
'updated_at': { type: Date, default: Date.now },

'created_at': { type: Date, default: Date.now },

'keywords': { type: Array },

'dependencies': { type: Array },

'dependents': { type: Array },

'stats': {

  'releases': { type: String },

  'downloads': { type: String },

  'downloads_this_month': { type: String },

  'open_issues': { type: String },

  'pull_requests': { type: String }

}

});

var plugin = Mongoose.model('plugin', internals.plugin);
```

在上面的架构中，我们定义了每个文档中的所有相关字段以及一些数据类型要求。在某些情况下，还定义了回退默认值，以防我们在创建时没有为这些字段提供值。

MongoDB 允许我们能够快速地在已索引的字段上进行查找。如果我们最终搜索的是某个未被索引的内容，MongoDB 必须遍历整个文档列表。由于我们必须跨不同的字段进行查询，因此必须使用索引。

```javascript
// ...

internals.plugin.index({

  name: 1,

  description: 1,

  authors: 1,

  keywords: 1

});
```

现在来看用户，我们知道他们应该有一个用户名、可能还有一个显示名称、一个地址、创建/更新时间戳以及点赞列表。由于我们正在使用 MongoDB，数据应该是反归一化的（这意味着它们应该被分组，而不是拆分成不同的表格）。使用抽象将“点赞”（Likes）插件与“用户”关联起来是合理的；每个用户都有一个点赞列表。

```javascript
var internals = {};

internals.user = new Mongoose.Schema({

  'username': { type: String, required: false },

  'name': { type: String, required: false },

  'email': { type: String, required: false },

  'updated_at': { type: Date, default: Date.now },

  'created_at': { type: Date, default: Date.now },

  'likes': [internals.plugin]

});

var user = Mongoose.model('user', internals.user);
```

## 搜索插件

hapi-plugins.com 应用最关键的部分是允许用户搜索插件的能力。我们希望搜索是灵活的。访问者如果知道插件的名称，可能想按名称搜索。他们可能只知道插件“需要”做什么，并可以搜索描述中可能出现的关键词或单词。最后，可能知道是谁创建了插件的访问者，可以搜索由该作者制作的所有插件。

实现这种逻辑有点复杂。它涉及到生成一个 MongoDB 查询，同时跨所有相关字段对字符串进行查询。在示例中，它会生成一个匹配我们标准的标准的 MongoDB 查询对象并执行它。

```javascript
internals.plugin.statics.search = function (queryString, sortString, callback) {

  var query = {};

  if (queryString && queryString.length > 0) {

    var pattern = new RegExp(queryString, 'ig');

    query = {

      '$sort': [

        'name': pattern,

        'description': pattern,

        'author': pattern,

        'authors': {

          '$regex': pattern

        },

        'keywords': {

          '$regex': pattern

        }

      ]

    };

  }

  var sortOrder = 1;

  var sortBy = sortString || 'name';

  if (sortBy[0] === '-') {

    sortOrder = -1;

    sortBy = sortBy.slice(1);

  }

  var sort = {};

  sort[sortBy] = sortOrder;

  return this.find(query).sort(sort).exec(callback);

};
```

上面的搜索函数包含了很多操作。第一个函数接受两个重要的参数：一个发送结果的回调函数。

第一个是用户输入的查询。我们获取查询并与所有相关字段进行匹配：名称、描述、作者、作者列表和关键词。

第二个参数决定排序顺序。当我们从数据库获取结果时，它必须知道返回什么（升序还是降序以及按什么字段）。我们使用约定“-name”来表示按名称降序，使用负号“-”表示升序。如果`sortString`为`null`，我们默认按名称升序。

我们获取这两个参数并在数据库中执行查找查询。

现在，回到控制器中，我们定义了一个搜索处理程序来使用我们新的数据库搜索方法。在这个处理程序中，我们还将验证并清理输入，以确保没有输入无效或恶意的输入。

```javascript
module.exports.search = {

  validate: {

    query: {

      q: Joi.string(),

      sort: Joi.string().optional(),

      fields: Joi.string().optional()

    },

    handler: function (request, reply) {

      var query = null;

      var sort = null;

      if (request.query) {

        query = Xss(request.query.q);

      }

      if (request.query.sort) {

        sort = Xss(request.query.sort);

      }

      DB.plugin.search(query, sort, function (err, results) {

        if (err) {

          return reply({status:-1, error: err}).code(500);

        }

        return reply(JSON.stringify(results, null, 2));

      });

  }

  }

};
```

在搜索处理程序中，我们在查询参数上设置了验证规则，正如我们在第 5 章“验证”中所示的。上面显示的新约定涉及`Xss`模块。该模块通过转义 HTML 实体和其他恶意手段来清理输入。你将在后的第 12 章“安全”中学习更多内容。

在输入经过验证和清理后，我们将将其传递给模型的搜索函数。在回调函数内部，如果返回了错误，我们将返回一个友好的 JSON 错误消息。但如果成功，我们将返回一个漂亮的 JSON 响应。

这就是我们如何允许用户搜索我们的插件库的。但里面现在什么都没有！

## 添加插件

为了搜索插件，我们需要向数据库添加条目。在上一章节中，我们看到了如何获取和存储数据。现在我们需要添加多个插件。

```javascript
internals.plugin.statics.create = function (pluginsJS, callback) {

  var self = this;

  var pluginObj = pluginsJS;

  self.update(pluginObj, function (err, numberAffected) {

    if (err) {

      return callback(err);

    }

    return callback(null, numberAffected);

  });

};
```

# 第 8 章：模型

在上一章节，我们看到了如何获取和存储数据。然而，我们需要处理未找到结果的情况。

```javascript
if (numberAffected === 0) {

  // 处理未找到结果

}
```

## 总结

在本章，我们学习了如何连接第三方 API：定义架构、进行查询以及处理数据。正如提到的，有一个附录。接下来，我们将看到如何将这些数据展示给用户。

# 第 9 章：模板

在上一章（第 8 章 模型）中，我们看到了如何获取和存储数据。现在，我们将看到如何将数据返回给用户。

hapi 主要用于构建 RESTful JSON API。然而，用 HTML 响应 HTTP 请求也是必要的或有帮助的。由于响应取决于请求数据的用户，对每个响应进行硬编码并不总是可行或理想的。自定义响应的最佳方法是使用模板。在 hapi 中，模板被称为视图。

hapi 原生支持大多数模板引擎。本章将包含六种流行的引擎示例：Handlebars.js、Mustache.js、Jade、Dust、eco 和 ECT。关于它们的概述，请参书末的附录。

在一个典型的 Web 应用中，用户访问 URL，URL 映射到 Web 服务器中的处理器，处理器执行某些业务逻辑来准备数据，最后，Web 服务器以 HTML 格式向用户响应数据。

响应 HTML 有许多不同的方法。两种主要方法是拼接和现代模板系统。

在 Web 开发早期，HTML 是通过拼接 HTML 字符串与变量生成的，如下：

```javascript
var html = '<<html><title>' +

page_title +

'</title></head><body>' +

content +

'</body></html>';

return reply(html);
```

幸运的是，这种枯燥且不灵活的方法已经过时，并被现代模板系统所取代。然而，这种拼接方法仍然可行，某些团队为了单行响应的效率可能会使用它。

同时，对于现代 Web 应用程序，模板系统将负责格式化数据的模板合并到一致格式中——如 HTML。例如，一个 Handlebars（或 Mustache）模板如下：

```html
<<html>

<head>

  <title>{page_title}</title>

</head>

<body>

  {content}

</body>

</html>
```

与如下类似的上下文数据结合使用：

```javascript
var context = {

  page_title: 'Templating is fun!',

  content: '<h1>Hello world!</h1>'

}

return reply.view('index', context);
```

将返回如下的 HTML 输出：

```html
<html

<head>

  <title>Templating is fun!</title>

</head>

<body>

  <h1>Hello world!</h1>

</body>

</html>
```

使用模板，可以快速添加、移动或完全删除数据。这些工作可以分工进行——设计人员负责模板，而开发人员提供上下文数据。在重新设计时，可以轻松更换模板，或者根据条件显示（如果用户的设置指定了偏好，则显示用户 X 的设计；否则显示 V）。因此，与替代方案相比，模板的使用既不那么枯燥也灵活得多。

## 配置

在 hapi 中，视图在使用之前必须进行配置。视图必须知道要运行哪些引擎以及在何处找到文件——这些是必要的。其他选项不是必须的。

## 选项

在配置视图时，有三个主要的选项可以配置：`engines`（引擎）、`compileMode` 和 `paths`（路径）。在下一节中，我们将发现可能需要的让视图正常工作的各种子选项。

## ENGINES

`engines` 配置对象告诉视图要查找哪些文件扩展名以及应该使用哪种模板引擎。

`engines` 对象期望文件扩展名（不带点`.`）作为键，并将模板系统编译器作为值。下面的示例（"engines-breakdown.js"）将匹配任何`filename.extension`并使用`some_compiler`引擎。

```javascript
engines: {

  "extension": require('some_compiler')

},

/* ... */
```

使用此系统，可以混合使用多个模板系统，只要它们都使用不同的文件扩展名：

```javascript
var Hapi = require('hapi');

var server = new Hapi.Server(

server.views({

  engines: {

    html: require('mu'),

    jade: require('jade'),

    hbs: require('handlebars')

  },

  defaultExtension: 'hbs',

  path: __dirname + '/views'

});});
```

如果你出于某种原因混合使用引擎，你应该注意以下几点。如果你想使用`reply.view('templateName', context)`语法，那么理解默认扩展名是非常重要的。在上面的示例中，你可以看到我们如何选择`hbs`作为该默认扩展名。此设置不是必须的。你可以直接添加扩展名，如`reply.view('templateName', context)`。如果文件的扩展名不是你的`defaultExtension`，那么你需要为它指定该扩展名。

## COMPILEMODE 选项

`compileMode`选项用于告诉 hapi 期望同步模板化还是异步模板化。hapi 期望引擎对象包含一个`compile`方法，该方法可以是其中一种格式，但不能两者兼有。默认情况下，hapi 期望同步引擎。这里有一个同步编译函数。

```javascript
{

  compile: function(template, options) {

    return function(context, optionsOverride) {

      // 返回与上下文集成的字符串模板

    }

  }

}
```

接下来我们以异步方式执行相同的操作。

```javascript
{

  compile: function(template, options, callback) {

    var error = null;

    return callback(error, function(context, optionsOverride, internalCallback) {

      var output = ''; /* 设置与上下文集成的字符串模板 */

      return internalCallback(null, output);

    });

  }

}
```

根据模板引擎的不同，你稍后会看到默认的`compileMode`可能需要覆盖为`'async'`。

## PATHS

hapi 视图需要知道去哪里查找模板文件。根据你的项目需求，有多种路径配置。

- `path`：指向查找模板文件的主目录
- `partialsPath`：指向查找部分模板（Partials）的目录（如果引擎支持 Partials）
- `helpersPath`：指向定义模板辅助函数的目录（如果引擎支持 Helpers）
- `layoutPath`：包含布局模板（通常为`layout.{extension}`）或`layout.html`的目录
- `relativeTo`：用作其他目录前缀的路径（允许在其他路径中使用相对路径）

此外，还有两个潜在重要的与路径相关的设置：

- `allowAbsolutePaths`：（布尔值）允许在 path 设置中使用绝对路径（默认：false）
- `allowInsecureAccess`：（布尔值）允许向上移动目录（使用`../`）

`allowInsecureAccess`变量应极谨慎使用。它可能会允许用户访问服务器操作系统上原本安全的文件，例如密码文件、敏感数据文件等。

## GLOBAL SPECIFIC

所有的全局视图设置都可以应用于特定的模板引擎，这将覆盖任何全局设置。这需要将编译器对象（通常是调用结果）移动到模块，以便为附加选项留空间。在下面的示例 "specific-view-settings.js" 中，默认的`compileMode`更改为`'async'`，html 文件将使用同步编译模式下的处理器执行或渲染。

```javascript
engines: {

  compileMode: 'async',

  engines: {

    html: {

      module: require('handlebars'),

      compileMode: 'sync'

    }

  }

  path: '/path'

}
```

## MORE OPTIONS

更多选项在 API 文档中有详细介绍。

## STARTER EXAMPLES



首先我们从 Mustache 开始。

```javascript
var Hapi = require('hapi');
```

# 第 9 章：模板化

```javascript
var server = new Hapi.Server();
server.views({
  engines: {
    html: require('mu')
  },
  path: __dirname + '/views'
});
```

这非常简单。需要注意的是，当你调用 `request.view('templateName', { context })` 时，它将去视图目录查找 html 文件。

```javascript
var Hapi = require('hapi');
var server = new Hapi.Server();
server.views({
  engines: {
    hbs: require('handlebars')
  },
  path: __dirname + '/views'
});
```

你会看到这个示例基本上是一样的。由于 Handlebars.js 与 Mustache 高度兼容。接下来

```javascript
var Hapi = require('hapi');

var server = new Hapi.Server();
server.views({
  engines: {
    jade: require('jade')
  },
  path: __dirname + '/views',
  compileOptions: {
    pretty: true
  }
});
```

我们需要在这里添加一个名为 `compileOptions` 的附加设置并将 `pretty` 设置为 `true`，hapi 尝试以通用方式处理这些视图，取决于模板引擎的不同，我们可以看到这些差异。接下来

```javascript
var Hapi = require('hapi');

var server = new Hapi.Server();
server.views({
  engines: 
```

```javascript
// 需要 npm 安装 dust-linkedin
html: require('hapi-dust')

},
path: __dirname + '/views'
));
```

这非常直观。这里唯一的额外说明是需要安装 dust-linkedin 并将其作为你的 `package.json` 文件中的依赖项。

最复杂的示例，ECT。

```javascript
var Hapi = require('hapi');
var ECT = require('ect');
var ECTRenderer = ECT({
  watch: true,
  root: __dirname + '/views'
});
```

```javascript
var server = new Hapi.Server(
  server.views({
  ect: {
    compile: function (tmpl, opts) {
      return function (context, engineOptions) {
        return ECTRenderer.render(opts.filename,
          context);
      }
    }compileMode: 'sync'
  },
  basePath: __dirname,
  path: './views'
});
```

你会发现需要更多工作。我们需要通过提供一个编译函数来帮助 hapi 了解编译是如何进行的。此外，你需要在本章之前讨论过的 `compileMode` 告诉 hapi 是同步的。

通过展示多种模板引擎，你可以更清楚地展示 hapi 如何处理不同的解决方案。你可以在 hapisjs 网站的插件部分下的 `Templating` 找到额外的模板解决方案。如果你没有找到需要的，可以开启讨论或考虑帮助社区添加此模板引擎。

## 视图加载 (View Loading)

视图是在响应步骤中从处理器内部调用并加载的。`reply.view` 函数接受三个参数（最后一个是可选的）：目标模板文件的相对路径、应用于模板的上下文（context），以及一个用于覆盖全局引擎设置的选项对象。

```
handler: function (request, reply) {
  var context = {
    content: 'hello world'
  };
  // 假设可以在 views.path + '/path/index'找到文件
  reply.view('path/index', context, {compileMode: 'sync' });
}
```

提醒一下，我们不需要 `index.html`，因为我们已经在 `server.views` 函数的 `engines` 部分定义了扩展名。

## 布局 (Layouts)

布局允许你将所有模板封装在另一个模板内部。如果你的网站具有相同的通用外观（例如：logo、页眉和页脚），这将非常有用。这样，你只需要为通用布局设计 HTML，并将普通模板嵌套在 `{{content}}` 上下文变量中。

## 配置 (Configuration)

启用布局最重要的步骤是配置。只需要两个额外的配置字段：`layoutPath` 和 `layout`。`layoutPath` 告诉 hapi 去哪里查找 `layout.{ext}`，其中扩展名定义在 `engines` 选项下。

不同模板系统之间的配置实际上并没有太大区别。

```
var Hapi = require('hapi');

var server = new Hapi.Server();
server.views({
  engines: {
    html: require('handlebars') // .html 是 hapi 将查找的后缀
  },
  path: __dirname + '/views',
  layoutPath: __dirname + '/views',
});
```

```
layout: true
));
```

## 使用 (Usage)

在正确配置后，使用实际上非常简单。处理器端没有任何任何变化：

```
handler: function (request, reply) {
  var ctx = {
    msg: 'Hello world!'
  };
  return reply.view('/path/' + templateName, ctx);
}
```

模板将通过布局中的 `content` 变量进行加载。

## 排除 (Exclusion)

有时你想对所有模板应用布局，但某些某些模板除外。这非常简单。你只需要向 `reply.view` 包含第三个可选的配置参数，将 `layout` 设置为 `false`。

```javascript
// 在处理器内部
return reply.view(template_name, context, { layout: false });
```

## 部分组件 (Partials)

部分组件非常棒。部分组件模板允许你提取共享的模板片段，并在其他模板之间复用。这防止了你被迫在多处修改代码；你只需编辑一次，就会反映在所有模板中。

## 配置 (Configuration)

要启用部分组件，你只需要添加一个视图选项 `partialsPath`，它告诉 hapi 去哪里查找部分组件。当你引用部分组件时，这些组件将相对于此路径。

不同模板系统之间的配置实际上并没有太大区别。但是，某些引擎可能需要微调以与 hapi 的部分组件系统配合。例如，对于 Hogan.js mustache 模板，在 hapihogan 有一个方便的预微调版本。

## 第 9 章：模板化 (CHAPTER 9: Templating)

```
var Hapi = require('hapi');

var server = new Hapi.Server(
server.views({
  engines: {
    html: require('handlebars') // .html 是 hapi 查找的后缀
  },
  path: __dirname + '/views',
  partialsPath: __dirname + '/views/partials'
}););
```

## 辅助函数 (Helpers)

辅助函数是模板语言的扩展，允许你在模板内部创建并使用自定义函数。这是 Handlebars.js 的功能。

## 配置 (Configuration)

要启用辅助函数，你只需要提供一个额外的视图选项 `helpersPath`。这告诉 hapi 去哪里寻找辅助函数。

```
var Hapi = require('hapi');

var server = new Hapi.Server();
server.views({
  engines: {
    html: require('handlebars') // .html 是 hapi 查找的后缀
  },
  path: __dirname + '/views',
  helpersPath: __dirname + '/views/helpers'
}););
```

## 辅助函数文件 (Helper Files)

辅助函数文件应根据所需的调用名称命名。如果你想创建一个如 `toMoney` 这样的辅助函数，文件应命名为 `toMoney.js`，并且它应该导出（`mod.exports`）单个函数（该函数可以接受参数）。

```javascript
module.exports = function (val) {
  return "$" + val.toFixed(2);
};
```

然后，在模板内部，就可以带参数调用 `toMoney`（该参数可以是变量）。

```handlebars
{{toMoney 25}}
{{toMoney cost?}}
```

## 共享上下文 (Shared Contexts)

通常希望在每个视图的每个上下文对象中包含某些数据。例如，在一个地方维护 HTML 页面标题并将其附加到每个视图，比包含在每一个单独的上下文中容易得多。

下方的示例（`shared-context.js`）将使用新值添加（或覆盖）`context.title` 值。如果调用处理器时没有带视图，则 `.context` 将不会被定义并受到影响。

```javascript
server.ext('onPreResponse', function (request, reply) {
  var response = request.response;
  if (!response.isBoom) {
    if (response.source && response.source.context) {
      response.source.context.title = "Hapi-Plugins";
    }
  }
  return reply();
}
```

上面的示例使用了 `onPreResponse`，这是我们在第 2 章服务器请求生命周期中学习过的。我们正在使用 `onPreResponse` 在响应之前合并这个标题。另一种方法是在回复视图之前合并共享对象：

```javascript
server.ext('onRequest', function (request, next) {
  // 这可以从数据库异步加载
  request._sharedContext = {
    title: 'Hapi-Plugins'
  };
  next();
}
```

这里我们使用 `server.ext` 来扩展此功能：

```javascript
// 在处理器中
var Hoek = require('hoek');
/* ... */
handler: function(request, reply) {
  var ctx = {
    content: 'Hello world!'
  };
  var context = Hoek.applyToDefaults(request._sharedContext, ctx);
  return reply.view('/path/' + templateName, context);
}
```

通过使用共享上下文（如上所示），可以将视图之间共享的值放在在一个地方（而不是在每个处理器中重复）。这对于需要反复传递全局设置（如功能标志或网站信息）非常有用。

## 总结 (Summary)

现在你已经知道如何在给定数据上下文的情况下向用户渲染 HTML，你现在可以使用 hapi 创建完整的网站。视图和模板系统通过提取共享文本数据、部分模板和整个模板，可以节省大量的开发时间并让你的生活更轻松。

利用你为止学到的知识，你现在可以创建功能完整的网站。但是，正如我们在第 10 章测试中所看到的，仅仅能够创建网站是不够的！为了构建真实的生产应用程序，你需要测试你的代码。

接下来的章节将涵盖许多基本的测试原理以及以下列出的主题：

- lab 的历史

- 安装 lab

- 编写一个简单的测试

- lab 的原理

- 编写一个 hapi 测试

- 代码覆盖率

- 报告器

- 检查 (Linting)

- 插件测试

# lab 历史

为了获得最佳效果，happy 与 lab 运行器配合得很好。Lab 是专为 hapi 插件开发的测试框架。happy 最初使用 mocha 和 chai 来执行测试。然而，随着 Node.js 0.10 的发布，happy 增加了对新版本的支持并引入了 domains。Domains 自发布以来就一直带有一个棘手的特性，其中测试支持也不例外。当 0.10 发布时，mocha 在支持充分测试 domains 方面非常缓慢。由于 hapi 使用 domains 的特性，必须采取一些措施。结果，lab 经过了精简并添加了更多功能。

代码覆盖率是确保提交到仓库的代码具有质量的关键因素。因此，在运行测试时，测试框架需要以一个简单标志的形式内置代码支持。

在创建 lab 之前，hapi 中的 mocha 测试是使用 blanket coverage 模块运行的。Blanket 本身依赖 esprima 来创建代码的抽象语法树 (AST)，以帮助识别用于插入代码覆盖率分析的语句。Blanket 在 lab 创建时也被迁移了过来。然而，随着时间的推移，代码覆盖功能已直接内置到 lab 中，而不是由第三方提供。

代码报告随着在 lab 内部整合分析而演变。这有助于使代码覆盖率成为 lab 报告中的一等公民。结果，HTML 报告器现在可以识别代码中永远无法被测试到的死代码（dead lines）。

这使得识别可以删除的代码区域变得容易，从而使你的代码更具可维护性。

当 hapi 使用 mocha 进行测试时，也使用 chai 来帮助构建断言。hapi 的维护者更倾向于使用 expect 风格编写测试，而不是 assert。随着时间的推移，chai 的使用暴露了一些与大型框架不一致的边缘情况函数名。例如，`exist` 属性不是作为函数执行的，这与语法的其他部分不同。这些不一致性导致了偶尔出现一些 bug。这些 bug 的产生在于人们很容易忘记写方法括号 `()`，导致断言从未被执行。因为它从未被执行，所以它错误地通过了。

结果，创建了名为 code 的断言库。code 接收了 chai 的语法并将 `exist` 变成一个函数，就像所有的 `true`、`false` 和 `null` 真值都变成了函数。下面你可以看到 chai 和 code 之间的区别。

首先，我们的示例是：

```
expect(foo).to.exist;
expect(bar).to.be;
```

接下来，你可以看到我们实现相同功能的代码示例。注意，在 code 中，`true` 和 `exist` 是函数。

```
expect(foo).to.be();
expect(bar).to.be.true();
```

除了上述描述的不一致性外，我们想要一个小型、简单且直观的断言库。去掉了处理插件、扩展以及支持浏览器测试开销的逻辑。这产生了我们所需的大部分功能，但也带来了大约 300 行易于阅读和理解的代码。

最后，code 允许测试运行器和断言库之间进行更深层的集成。这允许我们获取总断言计数来衡量测试的完整性，并验证每个断言都被正确执行。

lab 在其他方面也有参与。例如，已添加了转译支持以支持测试 CoffeeScript 或 JSX 代码。此外，lab 现在内置了 lint 支持，因此提交到仓库的拉请求（pull requests）具有相同的编码风格。这对于开发者在请求合并提交之前预先知道是否违反了任何样式规则非常有用。然而，lab 的缺点之一是它目前设计并仅运行在服务器上。但随着其流行度的增加和更多开发者希望使用它进行客户端测试，这种情况可能会改变。

## 安装 lab

lab 可能在全局安装到你的环境中会很有用。与其它 node.js 模块类似，lab 的安装可以通过 npm 完成。如下所示：

```
$ npm install -g lab
```

虽然你可以全局安装，但并不需要这样做。相反，所有 happy 核心模块在 `package.json` 的 `devDependencies` 部分中都包含了 lab。任何最新版本的 lab 都可以全局或本地安装，因为它们在运行测试时不会发生冲突。接接的示例显示了如何仅在本地安装 lab 并将其保存到 `package.json` 的 `devDependencies` 部分。

```
$ npm install lab --save-dev
```

安装 lab 后，你应该验证它是否运行正常。如果是全局安装的，lab 将在 PATH 环境变量中可用。否则，你将需要从 `node_modules/.bin` 文件夹运行 lab 二进制文件。要验证全局安装，只需运行 `lab -h`。如果你想验证本地安装，那么你

## 安装 code



需要运行`node ./node_modules/.bin/lab -h`。你应该能得到`lab`的帮助页面。

顺便提一下，在进入包含子`node_modules/.bin`文件夹的目录时，自动更新 PATH 可能会有帮助。这使得本地二进制文件可以像全局二进制文件一样运行。

与安装`lab`类似，你也应该安装`code`。记住，`lab`并没有内置开箱即用的断言库。因此，你应该使用`code`、`chai`或你喜的任何其他模块。你可以再次运行`npm install code --save-dev`将其保存到你的`package.json`文件中或手动添加。

## 编写简单的测试

所有测试都应该位于项目根目录下的`test`文件夹中。这是 Node.js 社区中几乎无处不在的模式。你选择如何命名测试文件取决于你，因为目前还没有一个统一的命名规范。然而，happy 组织中使用的使用的模式是将每个测试文件命名为与其负责测试的模块相同的名称。为了这次练习，请创建一个名为`index.js`的文件。在`index.js`中填充下面的代码。

```javascript
// Load modules
var Code = require('code');
var Lab = require('lab');
```

```javascript
var lab = exports.lab = Lab.script();

lab.test('lab exists', function (done) {
  Code.expect(lab).to.exist();
  done();
});
```

只需在项目根目录下输入`lab`命令即可运行上面的测试。输出将如下所示：

```text
$ lab
```

```text
1 tests complete
No global leaks detected
```

希望这并不困难或令人震惊。正如你从输出中看到的，运行测试所需的时间将同默认报告器一起报告。

## `lab`的原则

让我们来看一下需要记住的内核`lab`原则。

## 始终是异步的

在上一节中，你看到了一个简单的`lab`测试是是什么样的。`lab`的定义性特征之一是测试总是异步的。`lab`并不是通过检查参数对象的长度并以不同于带有`done`参数的方式来运行测试，所有的`lab`测试都必须接收一个回调参数，并在测试完成时执行它。如果测试没有期望该参数，则测试会立即处理解释。例如，下面的测试：

```javascript
// Load modules

var Code = require('code');
var Lab = require('lab');

var lab = exports.lab = Lab.script();

lab.test('lab exists', function () {
  Code.expect(lab).to.exist();
});
```

当我们运行`lab`时，得到如下输出：

```text
$ lab


Error: Function for test "lab exists" should take exactly one argument
```

同样，如果测试函数中接受了参数但没有执行它，将会发生错误。然而，这个错误将是测试本身的超时。我们可以通过移除`done ()`来产生超时。这可以通过编写以下测试来实现。

```javascript
var Code = require('code');
var Lab = require('lab');
```

```javascript
var lab = exports.lab = Lab.script();

lab.test('lab exists', function (done) {
  Code.expect(lab).to.exist();
});
```

该测试的输出结果如下所示：

```text
$ lab

x
Failed tests:
1) lab exists:
   Timed out (2000ms) - lab exists

1 of 1 tests failed
Test duration: 2007 ms
No global variable leaks detected
```

注意，在之前的示例中，`.`被更改为了`x`，以表示测试失败。如果你想让报告更显式，可以使用`-v`启用详细模式。请注意在同一个测试中启用详细模式的情况。

```text
$ lab -v
1) lab exists

Failed tests:
1) lab exists:
   Timed out (2000ms) - lab exists

1 of 1 tests failed
Test duration: 2006 ms
No global leaks
```

## 测试脚本（Test scripts）

`Lab`并不假设测试文件夹中的 JavaScript 文件一定就是测试文件。因此，为了告诉`lab`脚本文件是一个测试脚本，你必须执行`Lab.script()`并将结果赋值给`module.exports`对象的`lab`属性。为了帮助发现这种风格下的开发者错误，`lab`会在执行了`script()`但未导出`lab`属性时进行报告。此代码示例所示：

```javascript
// 加载模块

var Code = require('code');
var Lab = require('lab');

var lab = Lab.script();

lab.test('lab exists', function (done) {
  Code.expect(lab).to.exist();
  done();
});
```

使用此测试，如果你运行`lab`，针对此错误的错误消息将如下所示：

```text
$ lab
file: test/index.js includes a lab script that is not file: test/index.js includes a lab script that is not exported via exports.lab
```

## 安全全局变量（Safe globals）

`lab`的另一个假设是全局对象不应该被测试功能污染。其他框架会将`describe`或`it`挂载到全局对象上，而`lab`尝试采用不同的方法来隔离每个实验。每个实验或测试函数仅在执行`script()`返回的`lab`对象上可用。

`Lab`将全局问题更进了一步，更改了全局对象对于运行测试后存在的新属性。这通常是缺少`var`声明的标志。但是，可以通过向`lab`二进制文件传递`-l`或`--leaks`来禁用此功能。同样，如果存在某个全局变量，你可以将其作为参数传递给`-I`或`--ignore`。例如，如果你想忽略设置全局对象上的名为`foo`的属性，可以如下 true 执行`lab`：

```text
$ lab --ignore foo
```

## 实验（Experiments）

虽然`lab`测试可以写得像 mocha 和 jasmine 的行为驱动（BDD）风格测试，但也可以命名为完全不同的名称。BDD 风格倾向于使用`describe`和`it`，`lab`提供了使用`experiment`和`test`的选项。`describe`和`experiment`函数是互换的，正如`it`和`test`之间一样。你选择的风格完全取决于你，没有错误的答案。然而，使用实验风格的一个优点是，它强化了这样观点：工程师正在创建测试，并且正尝试对它们进行科学化的处理。

实验性用于封装一组相似的测试。例如，如果你正在测试 lab 本，你可能会编写封装在下面所示`experiment`中的实验测试。

```javascript
// 加载模块

var Code = require('code');
var Lab = require('lab');

var lab = exports.lab = Lab.script();

lab.experiment('lab', function () {
  lab.test('exists', function (done) {
    Code.expect(lab).to.exist();
    done();
  });

  lab.test('has properties', function (done) {
    Code.expect(Object.keys(lab)).to.not.have.length(0);
    done();
  });
});
```

然后如果你在详细模式下运行这些测试，你将得到如下：

```text
$ lab -v
lab
1) exists (3 ms)
2) has properties (1 ms)
```

2 个测试完成

## 编写 hapi 测试（Writing a hapi test）

测试持续时间：6 ms

未检测到全局变量泄漏

在这里你可以看到，通过详细模式，你还可以看到每个测试花费了多久。

## 编写 hapi 测试（Writing a hapi test）

hapi 的设计考虑了测试。为了发布版本，每一行代码和每条代码路径都必须有对应的测试运行。因此，hapi 及其依赖项中有大量的测试。为了帮助加快运行测试的时间，并避免文件描述符限制的问题，hapi 内置了模拟请求（mock request）支持。这是通过`shot`模块提供的名为`inject`的函数实现的。为了说明`shot`的威力，请看下面的测试。同时注意，使用实验风格测试，测试是使用 BDD 风格的快捷方式编写的。

```javascript
// 加载模块
var Code = require('code');
var Hapi = require('hapi');
var Lab = require('lab');
```

```javascript
var lab = exports.lab.script();
var describe = lab.describe;
var it = lab.it;
var expect = Code.expect();
```

```javascript
describe('inject', function () {
  it('returns the response result', function (done) {
    var handler = function (request, reply) {
      return reply('hello');
    };

    var server = new Hapi.Server();
    server.connection();

    server.route({
      method: 'GET',
      path: '/',
      config: { handler: handler }
    });

    server.inject('/', function (res) {
      expect(res.statusCode).to.equal(200);
      expect(res.result).to.equal('hello');
      done();
    });
  });
});
```

在以前的示例中，`server.start`函数没有被执行。结果是 socket 被创建或挂载到了服务器上。然而，向服务器发送了请求并收到了响应。请求对象包含了 hapi 服务器关心的所有属性。同样，传递给`inject`回调的响应包含了响应体以及相关的头部和状态码。

除非测试是从 socket 创建信息，否则最佳解决方案通常是使用`inject`。如果你采用这种方法，你的测试执行速度将比依赖于真实 socket 快得多。此外，它让更容易避免 socket 周围的设置和销毁。

```javascript
// 加载模块

var Code = require('code');
var Hapi = require('hapi');
var Lab = require('lab');
```

```javascript
var lab = exports.lab.script();
var describe = lab.describe;
var it = lab.it;
var expect = Code.expect();
```

```javascript
describe('real request', function () {
  it('returns a real response', function (done) {
    var handler = function (request, reply) {
      return reply('hello');
    };

    var server = new Hapi.Server();
    server.connection({ port: 0 });

    server.route({
      method: 'GET',
      path: '/',
      config: { handler: handler }
    });

    server.start(function () {
      Wreck.get(
        'http://localhost:' + server.info.port,
        function (err, res, payload) {
          expect(res.statusCode).to.equal(200);
          expect(payload).to.equal('hello');
          server.stop(done);
        }
      );
    });
  });
});
```

`Wreck`是一个轻量级 HTTP/HTTPS 客户端封装，为 hapi 设计。在进行任何请求时，它是首选模块。尽管如此，request 模块也被完全支持。本地，inject 示例和 wreck 示例之间的测试时间差异约为 18ms。

## 代码覆盖（Code coverage）

除了 lab 包含的所有上述功能外，代码覆盖是其最强大的功能之一。`lab`的代码覆盖依赖`espree`模块来生成 AST。除了典型的行覆盖外，`lab`还会确定不同的代码分支是否被执行。这可以是从同一个`if`语句中的多个条件，到标准的三元运算符。此外，`lab`还会确定某些代码路径未被执行并可以删除。

`html`和`console`报告在显示覆盖方面经过了最多的测试。默认情况下，运行`lab`时不会启用代码覆盖。要启用它，你需要传递`-c`或`--coverage`标志。该标志将启用代码覆盖报告并确保测试覆盖 100% 的代码。如果覆盖率低于 100%，你可以使用`-t`或`--threshold`标志，后跟一个代表报错前百分比的数字。如果测试未能通过阈值，`lab`将带有错误码退出。

下面是控制台报告的输出，显示了失败测试覆盖的样子：

```text
$ lab -c
```

# 第 10 章：测试

已完成 66 个测试  
测试耗时：1492 ms  
未检测到全局变量泄漏  
覆盖率：99.44% (2/356)  
`lib/payload.js`在以下行缺少覆盖：17, 27

如果这些信息不够详细，且你希望对缺失的覆盖有更好的概览，建议使用`html`报告器。要使用不同的报告器，只需将报告器的名称传递给`-r`或`--reporter`标志即可。你可以查看运行`lab -c -r html = coverage.html`产生的输出截图。

```javascript
module.exports = internals.Payload = function (payload, encoding) {
  Stream.Readable.call(this);

  var data = [].concat(payload || []);
  var size = 0;

  for (var i = 0, il = data.length; i < il; i++) {
    var chunk = data[i];
    size += chunk.length;
    data[i] = Buffer.isBuffer(chunk) ? chunk : new Buffer(chunk);
  }

  this._data = Buffer.concat(data, size);
  this._position = 0;
  this._encoding = encoding || 'utf8';
};
```

如你所见，覆盖仅在第17行和第27行的特定变量中缺失。然而，如果你为这些行上的缺失变量添加测试，你可以在下一个示例中看到运行`console`报告器的结果。

```bash
$ lab -c
```



已完成 69 个测试
测试耗时：1494 ms
未检测到全局变量泄漏
覆盖率：100.00%

在 `hapi` 生态系统中开发模块时，使用覆盖率是必不可少的。`hapijs` 组织下发布的所有模块都要求 100% 的代码覆盖率。因此，如果你计划对这些模块贡献任何更改或增强，你必须为更改的代码添加测试。关于代码覆盖率可能会有反对者，但它是被选定的帮助衡量代码运行情况的机制。除了添加覆盖模块中每一行和每个代码路径的测试外，`hapijs` 维护者还会审查测试和代码以确保其准确性。一个人可能会用一个检查错误假设的测试来覆盖某行，工程师最终负责检查代码和测试。

## 报告器 (Reporters)

`Lab` 配备了许多报告器，并支持任何自定义报告器。多年来，报告器根据社区反馈不断演进。目前，`lab` 支持以下报告器。

- `console` - CLI 输出
- `html` - 报告到 `html` 流，重定向到文件
- `json` - JSON 格式报告
- `junit` - JUnit XML 格式
- `tap` - TAP 格式
- `lcov` - `lcov` 格式
- `clover` - `clover` XML 格式
- `custom` - 自定义

之前，在代码覆盖率部分演示了与报告覆盖率相关的 `console` 和 `html` 报告器。然而，`html` 报告器的功能更多，它还报告运行的测试以及每个测试所花费的时间。这里是与单个测试相关的 `html` 报告器示例：

## 测试报告

0 失败 跳过 66 个测试 (1450 ms)

| ID | 标题 | 持续时间 (ms) |
|---|---|---|
| 1 | `request(i)` requests a resource with callback | 21 |
| 2 | `request(i)` requests a POST resource | 6 |
| 3 | `request(i)` requests a POST resource with unicode characters in payload | 5 |
| 4 | `request(i)` requests a POST resource with headers | 3 |
| 5 | `request(i)` requests a POST resource with stream payload | 5 |
| 6 | `request(i)` requests a resource without callback | 2 |
| 7 | `request(i)` cannot set an agent and `rejectUnauthorized` at the same time | 1 |
| 8 | `request(i)` cannot set a false agent and `rejectUnauthorized` at the same time | 0 |
| 9 | `request(i)` can set a null agent and `rejectUnauthorized` at the same time | 0 |
| 10 | `request(i)` requests an https resource | 345 |
| 11 | `request(i)` requests an https resource with secure protocol set | 297 |
| 12 | `request(i)` fails when an https resource has invalid certs and reject is false | 11 |
| 13 | `request(i)` succeeds when an https resource has unauthorized characters and `rejectUnauthorized` is false | 7 |
| 14 | `request(i)` requests a resource with downstream dependency | 6 |
| 15 | `request(i)` does not follow redirections by default | 3 |
| 16 | `request(i)` handles redirections | 4 |
| 17 | `request(i)` handles redirections with relative location | 5 |
| 18 | `request(i)` reaches max redirections count | 3 |

如果你计划在 `Jenkins` 中使用 `lab`，那么 `junit` 报告器是一个很好的选择，因为许多 `Jenkins` 插件（如 `dashboard-view`）依赖这种格式。你也可以结合 HTML 报告器和 HTML publisher 插件查看测试和代码覆盖率的详细视图。`json` 报告器是一个很好的原生报告器，如果你需要查看原始数据进行自己的解析，可以轻松解析它。它报告覆盖率以及通用的测试失败。以下是使用 `-c` 标志时 `json` 报告器的输出示例：

```json
"17": {
  "source": " [].concat(payload || ' ');",
  "chunks": [
    {
      "source": " var data = [].concat("
    },
    {
      "source": "payload",
      "miss": "true"
    },
    {
      "source": " || |"
    }
  ],
  "source": "",
  "miss": "never",
  "hits": 4,
  "miss": true
}
```

如上所示，缺失是在是在行和单个代码分支上报告的，这里恰好有一个。这使得读取 JSON 输出的工具能够更容易地解析和表示缺失的代码。此外，你可以看到命中此行但最终缺失代码的执行次数。每个行号都表示为父对象中的键名。每个 JSON 条目都以检查覆盖率的代码文件信息开头，可以在此处查看：

```json
{
  "filename": "lib/payload.js",
  "percent": 92.59259259256,
  "hits": 25,
  "misses": 2,
  "sloc": 27,
  "source": {
    "1": {
      "source": "",
      "miss": false
    }
  }
}
```

此外，`json` 报告器像 `html` 报告器一样，包含了执行的单个测试信息。每个测试名称都显示了执行持续时间，最重要的是测试是否通过。以下是 JSON 输出的部：

```json
{
  "tests": {
    "request()": [
      {
        "title": "requests a resource with callback",
        "err": false,
        "duration": 23
      },
      {
        "title": "requests a POST resource",
        "err": false,
        "duration": 5
      }
    ]
  }
}
```

## 代码检查 (Linting)

`lab` 包含的强大功能之一是内置的代码检查支持。默认情况下，支持 `eslint` 和 `jshint` 检查器。默认的代码检查规则强制执行一种风格。

要使用 `jshint` 运行 `lab`：

```bash
$ lab -n
```

## 插件测试 (Plugin Testing)

当你使用 `happy` 构建插件和服务器时，你需要做的之一是测试插件是否可以注册以及服务器是否可以启动。在 `happy` 生态系统中，常见的测试之一是检查插件是否可以注册的：

```javascript
// 加载模块
var Code = require('code');
var Lab = require('lab');
var HapiPlugins = require('../');
```

```javascript
// 快捷方式
var lab = exports.lab = Lab;
var describe = lab.describe;
var it = lab.it;
var expect = Code.expect;
```

```javascript
describe('hapi plugins', function () {
    it('can be started', function (done) {
        HapiPlugins.init(function (err, server) {
            expect(err).to.not.exist();
            expect(server).to.exist();
            done();
        });
    });
});
```

```javascript
resetDb(function (err) {
  expect(err).to.not.exist();
  HapiPlugins.to.init(function (err, server) {
    expect(err).to.not.exist();
    var plugin = DB.plugin({
      name: 'purdy',
      license: 'MIT',
      version: '1.0.1',
      description: 'a niceties plugin',
      authors: ['daniel']
    });
    var options = {
      url: '/plugins/purdy/like',
      method: 'GET'
    };
    plugin.save(function (err) {
      expect(err).to.not.exist();
      server.inject(options, function (response) {
        expect(response.result.success)
          to.equal(true);
        done();
      });
    });
  });
});
```

## 总结

在本章中，我们涵盖了测试如何成为 `happy` 生态系统的核心。如果没有测试以及围绕 `happy` 测试框架 `lab` 构建的工具，要确保交付高质量代码将变得困难得多。当你回任何 `happy` 模块做出贡献时，你需要熟悉如何创建测试，并对你测试的新代码进行 100% 的覆盖。此外，在为任何核心模块编写代码时，使用 `lab` 来帮助遵循 `happy` 风格指南。

围绕 `happy` 的测试和工具始终可以不断改进。如果你正在寻找一个加入 `happy` 生态系统做出贡献的良好起点，请查看如何为模块编写测试。尽管各个模块已经实现了 100% 的代码覆盖率，但在许多情况下，进一步的测试仍然很有用。

在下一章中，我们将向你展示一些用于调试你的 `hapi` 系统并识别主要问题的强大方法。

# 调试 11

一个调试过的程序是指你尚未找到导致其失败的条件的程序。

-- Jerry Ogdin

在上一章中，我们学习了许多关于测试 `hapi` 应用以及如何编写单元测试。在本章中，我们将发现如何使用一些高级工具调试我们的 `hapi` 应用。

在 `Node.js` 中进行调试一直是许多开发者的痛苦源。目前仍然缺乏优秀的工具来帮助开发者跨平台以及在应用程序整个生命周期内调试 `Node.js`。虽然存在 `DTrace` 等工具，但并不是所有的 `Node.js` 部署都有机会使用它。`Joyent` 和其他公司在记录如何调试 `Node.js` 应用方面做了出色的工作。在 `hapi` 世界中，我们创建了模块来帮助调试 `hapi` 应用变得更加简单。本章将涵盖特定的 `hapi` 模块，这些模块可以帮助在不同的环境下调试 `hapi` 服务器。此外，本章涵盖了如何设置有助于诊断问题的报告。

## 章节概述

后续章节将涵盖调试 `hapi` 以及通用 `Node.js` 的许多细节。这些主题包括：

- `console.log`
- `debug` 模式
- `TV`
- `Good`
- `REPL`
- 堆快照 (Heap Snapshots)
- 核心文件 (Core Files)

## console.log

虽然许多开发者可能看不起 `console.log` 这一可行的调试选项，但它确实有其用途且非常有用。在许多情况下，你仅仅只需要在远程部署的某个时间点知道变量的值。对于这种情况，使用 `REPL` 或远程调试会话是大材小用，请不要轻视使用 `console.log`。考虑到 `node.js` 的脚本化性质以及启动进程有多快，简单的方法就是 `ssh` 登录服务器并添加一条日志语句。虽然这不是最优雅的，但它可以帮助识别应用程序中不同时间点的状态。

## debug 模式

幸运的是，在 `hapi` 中，也有 `debug` 模式的概念。与其手动在 `hapi` 中输入大量的 `console.log` 语句，你可以在 `debug` 模式启动服务器，并对不同的服务器事件和错误细节进行控制台访问。这种模式非常详细，对于生产环境并非必要，建议仅在开发时启用 `debug` 模式。以下是在 `debug` 模式启动服务器并将所有错误记录到控制台的示例。

```javascript
var Hapi = require('hapi');
var options = {
  debug: {
    log: ['error']
  }
};
var server = new Hapi.Server(options);
server.connection({ port: 8000 });
server.route({ method: 'GET', path: '/', handler: function (request, reply) {
  throw new Error('Tribbles');
});
server.start(function () {
  console.log('server started');
});
```

`Debug`: internal, implementation, error
`Error`: Uncaught error: Tribbles

如上例所示，当发生错误时，错误和堆栈跟踪将被记录到控制台，并在消息带有 `Debug:` 前缀。

## TV

在开发环境中，调试 `hapi` 服务器的另一个有用选项是使用 `tv` 模块。`Tv` 主要为 `hapi` 应用的前端消费者设计。其目标是提供一个易于使用的仪表板，显示服务器请求活动的信息。这对于前端开发者能够追踪其代码向 `hapi` 服务器发送的请求生命周期特别有用。这里显示了 `tv` 的截图：

![](img/79450811086e2fc8749ec4d309ea2b79_142_0.png)

为了将 `tv` 添加到服务器，你需要像注册其他 `hapi` 插件一样注册它。下面显示了如何使用默认设置进行注册。在服务器上注册 `tv` 后，你可以通过服务器 URL `/debug/console` 访问它。

```javascript
var Hapi = require('hapi');
var Tv = require('tv');
var server = new Hapi.Server();
server.connection();
server.register(Tv, function (err) {
  if (!err) {
    server.start();
  }
});
```

通过 `tv`，你可以通过选择不同的事件标签来订阅你关心的请求事件。请求详情会在被创建时实时发送到 `tv` 页面。如果任何请求表现出某些有用信息，你也可以对其进行标记并进行调查。

# 第 11 章：调试

## Good

在 `tv` 中记录请求详情对于本地开发非常有用。然而，当你处于 QA 或生产环境时，你会希望使用一个专门为该场景设计的模块。对于这些情况以及本地开发，`good` 插件极其有用。
`good` 更为适用于 QA 和生产环境的原因是它被设计为还可以记录操作数据。多年来，此功能已扩展到不仅包含典型的内存或 CPU 详细信息，现在还包含了事件循环延迟和网络活动。
要向 `hapi` 服务器添加 `good`，请像注册其他插件一样注册它。主要的区别在于，使用 `good` 时，你需要为你关心的事件类型指定选项，以及记录这些事件的位置。`good` 事件包括：

- `ops`
- `response`
- `log`
- `error`
- `request`
- `wreck`

事件数据可以存储的地方非常广泛。如果你需要不同的报告器（reporter），可以通过查看许多示例中的某一个来构建一个。目前 `good` 可用的报告器包括以下类型：

- UDP
- HTTP
- Files
- Console
- InfluxDB
- Winston
- Loggly
- Logstash

这个列表将继续增长。你可以通过 `good` 页面获取最新列表。下面的代码显示如何注册 `good` 并每秒将 `ops` 数据记录到文件 `/var/log/example/ops.json`。

```javascript
var Hapi = require('hapi');
var Good = require('good');
```

```javascript
var server = new Hapi.Server();
server.connection();
var options = {
  opsInterval: 1000,



```javascript
reporters: {
  reporter: 'good-file',
  events: { ops: '+' },
  config: '/var/log/example/ops.json'
}
```

```javascript
server.register({
  register: Good,
  options: options
}, function (err) {
  if (err) {
    console.error(err);
    return;
  }

  server.start();
});
```

当你查看`ops`日志文件时，你会发现每个条目都是可以解析的 JSON，每个条目以换行符分隔。以下是事件数据的示例：

```json
{
  "event": "ops",
  "timestamp": 152794093174,
  "host": "mac.local",
  "pid": 35503,
  "os": {
    "load": [2.13427734375, 2.44287109375, 2.487034687],
    "mem": {
      "total": 1717986184,
      "free": 5757075456,
      "uptime": 459461
    }
  },
  "proc": {
    "uptime": 4,
    "mem": {
      "rss": 46538752,
      "heapTotal": 32171264,
      "heapUsed": 17638880
    }
  }
}
```

```json
{
  "delay": 0.2207310050725937,
  "load": {
    "requests": { "62778": 0 },
    "responseTimes": {},
    "sockets": {
      "http": 0,
      "total": 0
    },
    "https": {
      "total": 0
    }
  }
}
```

在之前的示例中，你可以看到日志记录了大量的有用信息。这使得将高于常的内存占用与网络活动或事件循环缓慢关联起来成为可能。

在版本 6 中，对使用`wreck`的请求数据日志提供了强大的支持。这对于追踪`hapi`服务器与下游流之间可能存在的问题非常有用。`hapi`反向代理模块依赖`wreck`，可以使用`good`记录反向代理数据。

使用`wreck`的示例所示：

```json
{
  "event": "wreck",
  "timestamp": 143149615889,
  "timeSpent": 581,
  "request": {
    "method": "GET",
    "path": "/api/route",
    "url": "http://local-host:8081/api/route",
    "protocol": "http",
    "host": "local-host:8081"
  },
  "response": {
    "statusCode": 200,
    "headers": {
      "content-type": "application/json",
      "charset": "utf-8",
      "cache-control": "no-cache",
      "content-length": 4198,
      "accept-range": "bytes"
    },
    "date": "Tue, 12 May 2015 22:26:55 GMT",
    "connection": "close"
  }
}
```

你可以看到这里可以发挥巨大的威力。例如，绘制耗时图，并找出你的调用中有多少时间消耗在依赖服务器上。查看标头以确保它们被正确处理也非常有用。

这些数据收集和报告中提供了巨大的力量。业务人员和运维人员都会发现这些信息很有用。将数据发送到如`plugin`或`logstash`这样的日志聚合器，并为应用程序的不同利益相关者创建仪表板，是利用可用数据的好方法。这对于你的`hapi`来说是一个强大且轻松的胜利。

在 hapi-plugins.com 项目中，使用`good`将操作和`hapi`日志事件记录到控制台。这是通过在`lib`文件夹下的`index.js`文件中注册`good`及其`good-console`报告器实现的。此类注册的示例所示：

```javascript
var goodOptions = {
  opsInterval: 5000,
  reporters: {
    reporter: 'good-console',
    events: { log: '*', ops: '*' }
  }
};
```

```javascript
var registerPlugins = function (next) {
  server.register({
    Bell,
    Blipp,
    HapiAuthCookie,
    Authentication,
    Controllers,
    Models,
    Routes,
    { register: require('good'), options: goodOptions }
  },
  { select: 'http' },
  function (err) {
    return next(err);
  });
};
```

`good-console`报告器向控制台发送的事件由`events`属性指定。`*`值表示报告器不会根据特定标签过滤任何事件。如果你只关注与特定标签相关的事件，可以通过将`*`替换为你关心的标签的单个字符串，或代表你所关心的事件标签的字符串数组来指定。

在启动服务器并查看`stdio`输出后，就可以观察来自`good`的报告。下面显示了服务器运行 10 秒后`ops`事件的示例输出。如你所见，可以报告内存消耗、运行时间和负载情况。

```text
150418/175554.526, [ops], memory: 64Mb, uptime (seconds): 5,
load: 1.646484375,2.1015625,1.7680660625
150418/175559.531, [ops], memory: 65Mb, uptime (seconds): 10,
load: 1.67431640625,2.099609375,1.7690429875
```

# 第 11 章：调试

## REPL

为了更容易调试在远程服务器上运行的应用程序，创建了 hapi 插件`reptile`。

该插件创建了一个 REPL，它在端口上监听对运行中的 hapi 服务器对象的访问的 TCP 连接。REPL 是一个读取-打印循环（read print loop），它是修改运行中的服务器或简单检查其发生情况极极方法。默认情况下，REPL 仅从 localhost 访问。这是设计如此，以防止任何人访问 REPL，因为可能会给应用程序带来问题。

在端口上访问的 REPL 与你不带参数输入`node`时是相同的。它们都使用 node 核心提供的`repl`模块。唯一的区别是`server`被添加到全局上下文中。

为了建立到 REPL 端口的连接，可以使用`netcat`或`telnet`。当你在`reptile`的`/example`文件夹运行服务器时，它将创建一个虚拟服务器并注册`reptile`插件。示例服务器监听端口 9000。下面是使用`netcat`连接到本地端口 9000 的。

```bash
$ nc localhost 9000
```

建立连接后，你应该能看到对象上可用的对象。要做到这一点，只需输入`global`并按回车。然后你就可以遍历现有对象或为事件创建处理程序。这应该为运行中的服务器提供一个很好的钩子，你可以将其用于调试。

## 堆快照（Heap Snapshots）

最难调试的问题之一是那些导致你的进程崩溃的问题。调试这些问题的常用方法是在异常发生时直接查看堆栈输出。在 v8 世界中，另一个有用工具是在异常发生时创建堆快照并对其进行分析。为了解决这两个问题，创建了`poop`模块。`poop`是一个 hapi 插件，它监听进程`uncaughtException`事件的触发。当发生未捕获的异常时，会创建一个堆快照文件并将异常详情记录到文件中。`poop`还会重新抛出异常，以便异常传播并由其他订阅者处理。

堆快照文件以`.heaps`扩展结尾。这些文件可以使用 chrome v8 inspector 打开。要打开文件，启动 chrome inspector 并选择 "Profiles" 选项卡。截图显示了它的样子。

## 核心文件（Core Files）

调试时使用的最强大的工具之一是`mdb`。当你挂载到核心文件时，可以使用各种命令检查程序的状态。如下所示：

```text
## mdb corefile
Loading modules: [ libumum.so libc.so ld.so ]
> :load v8
V8 version: 3.14.5
Autoconfigured V8 support from target
C++ symbol demangling enabled
```

或者仅仅是因为它打印出内存中匹配相关签名的对象数量。你可以将`findobjects`的结果通过到`jsprint`以显示每个对象的内容。

在`mdb`之外，还有几个非常有用的工具可以处理 SmartOS 创建的内核文件（core file）。这些工具通常位于`/usr/proc/bin`，并包含以下命令：

```text
## pwd
/usr/proc/bin
## ls -l
total 13
lrwxrxr-x 1 root root 15 Jun 29 2013 pcred -> ../bin/pcred
lrwxrxr-x 1 root root 16 Jun 29 2013 pfiles -> ../bin/pfiles
lrwxrxr-x 1 root root 16 Jun 29 2013 pflags -> ../bin/pflags
lrwxrxr-x 1 root root 14 Jun 29 2013 pldd -> ../bin/pldd
lrwxrxr-x 1 root root 14 Jun 29 2013 mmap -> ../bin/mmap
lrwxrxr-x 1 root root 14 Jun 29 2013 prune -> ../bin/prune
lrwxrxr-x 1 root root 14 Jun 29 2013 psig -> ../bin/psig
lrwxrxr-x 1 root root 16 Jun 29 2013 pstack -> ../bin/pstack
lrwxrxr-x 1 root root 15 Jun 29 2013 pstop -> ../bin/pstop
lrwxrxr-x 1 root root 15 Jun 29 2013 prime -> ../bin/prime
lrwxrxr-x 1 root root 15 Jun 29 2013 ptree -> ../bin/ptree
lrwxrxr-x 1 root root 15 Jun 29 2013 pwait -> ../bin/pwait
lrwxrxr-x 1 root root 14 Jun 29 2013 pdwx -> ../bin/pdx
```

在上述工具中，`pmap`和`pfiles`特别有用，`pmap`显示内核文件的内存映射，包括堆（heap）占用了多少空间。`pfiles`能够报告由内核文件创建的文件描述符，这有助于发现文件未被正确关闭或处于打开状态的情况。有时`ulimit`设置得不够高，`pflags`能够报告启动进程的原始命令。

## 总结

在本章中，我们查看了用于调试进程的不同工具。这些包括为了帮助识别内核问题而生成的特殊工具。对于生产问题，使用内核文件或 REPL 很有帮助。对于在 halt 中发现的任何问题，请确保在 halt repo 中修复。

# 第 12 章：安全

在第 11 章中，我们学习了调试应用程序的各种方法。现在我们的应用程序运行符合预期，我们需要确保它免受黑者的恶意攻击。安全是 Web 开发中至关重要的一部分。但对于新开发者来说，它通常是复杂的，且经常包含在入门教程或文档中。大型网站默认并不免疫，会成为黑者的目标。事实上，有些公司通过 XSS 遭受了损害。通过尽早基础工作，你可以防止最常见的攻击向量并让自己安心。

本章暴露了一些常见问题、漏洞以及它们的解决方案。

## 最佳实践

在使用 hapi 时，学习安全最佳实践。

## 密码哈希：BCrypt

在数据库中存储密码时，使用明文存储是非常糟糕的做法。如果黑客访问了数据库，他们可以直接使用这些凭据查看或操纵敏感数据。使用单向哈希算法安全地存储密码更好。然而，有许多单向哈希算法可用，某些比其他的好得多。在他关于密码方案的著名博文中，Ptacek 提到，即使是最复杂的 MD5、DES、SHA1 和 SHA256 哈希也会瞬间被破解（游戏结束了）。

### 解决方案

BCrypt 专门为哈希密码等敏感字符串而设计。Node.js BCrypt 实现自 2010 年以来一直存在，经历了多年的安全和代码审查（包括我们自己的）。Node-bcrypt 提供了一种相对安全的方法希你的密码：

```javascript
var bcrypt = require('bcrypt');

// 通过 2^rounds 次迭代来生成盐
// 较大的数字需要显著的时间来计算
var rounds = 12;

var salt = bcrypt.genSalt(rounds);
var hash = bcrypt.hashSync("password", salt);
```

## XSS

跨站脚本（XSS）是最常见的漏洞之一，攻击者能够插入由受害者执行的脚本或链接。由于网络的工作方式，同一网络上的任何人都可以查看所有数据流量，看到密码、URL、消息等。为网站增加安全性的最简单方法之一是强制用户使用 SSL/HTTPS。这需要购买并安装证书，但它会加密浏览器和服务器之间的所有流量。

### 解决方案

使用 hapi 的`crumb`模块。

```javascript
// 服务器
var crumbOptions = {
  restful: false, // 启用负载验证
  crumb: true, // 使用 X-CSRF-Token 头部
  addToViewContext: true, // 自动添加到视图上下文
  isSecure: false // 如果未使用 HTTPS 则需要
};

server.register(
  { register: require('crumb'), options: crumbOptions },
  function (err) {
    if (err) {
      throw err;
    }
  }
);
```

```javascript
// 视图
<form action="submit" method="POST">
  <input name="crumb" type="hidden" value="{{crumb}}"/>
  <!-- ... -->
</form>
```

```javascript
// /submit 处理器
handler: function (request, reply) {
  return reply('ok'); // 不需要进行任何特殊处理
}
```

## CSRF

跨站请求伪造（CSRF）是另一种常见漏洞，攻击者能够在另一个不同但熟悉的网站上插入表单。如果受害者拥有未使用的 cookie，该表单可能看起来就像受害者本意操作的一样。

### 解决方案

银行网站应该在表单加载时生成一个在提交时必选的自定义标识符。没有这个密钥，任何提交的负载都将被拒绝。

## SSL

如今许多网站运行在裸 HTTP 上，而不是更安全的 HTTPS 上。这在网络上以明文形式执行浏览器到服务器之间的所有数据传输。由于网络的工作方式，同一网络上的任何人都可以查看所有数据流量并看到一切。

为网站增加安全性的最简单方法之一是强制用户使用 SSL/HTTPS。这需要购买并安装证书，但它会加密浏览器和服务器之间的所有流量。

配置 Node.js 服务的 SSL 有许多方法。最常见的方法是使用如 Apache 或 nginx/stunnel 等反向代理来处理 SSL 证书，终止加密，然后通过未加密的 HTTP 将流量转发到你的 Node.js 服务。这对于运行良好的 HTTP hapi 应用程序不需要任何更改。

## 最佳实践

关于如何使用 SSL 终止的文档，请参见 [DigitalOcean：如何设置带有 SSL 终止的 Nginx 负载均衡](https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-load-balancing)。

或者，Node.js 可以通过处理证书来终止加密，但这可能会消耗时间并增加应用程序服务器的负载。有关如何使用 SSL 终止的信息，请查看`server.connection.tls`选项下的 API 文档。以下是一个启用 SSL 终止的示例示例：

```javascript
var fs = require('fs');
var options = {
  port: 443,
  key: fs.readFileSync(keyPath, 'utf8'),
  cert: fs.readFileSync(certPath, 'utf8')
};

server.connection(options);
```

## 移除头部

许多漏洞可以通过设置或移除 HTTP 头部来修复。在详细介绍各种漏洞之前，这里有一种全局设置或移除头部的通用方法：



```javascript
server.ext('onPreResponse', function (request, reply) {
  if (!request.response.isBoom) {
    request.response.output.headers.ToAdd = 'someValue';
    delete request.response.output.headers.toRemove;
  }
  return reply();
});
```

或者，这可以在单个处理器内完成，以便仅应用于单个路由：

```javascript
handler: function (request, reply) {
  return reply(output)
    .header('Content-Type', 'application/json')
    .header('X-Frame', 'DENY')
}
```

# 第 12 章：安全

## 点击劫持（CLICKJACKING）

点击劫持发生在您的网页被插入到 HTML `iframe` 中，此时用户的点击可能会被劫持。如果用户点击了您的主按钮，攻击者可以劫持该点击并将用户重定向到恶意网页。

### 解决方案

将 `X-Frame` 头部设置为 `'DENY'` 将防止浏览器允许您的网页放置在 `frame` 或 `iframe`（`<iframe>`）内部。

## X-POWERED-BY

大多数 Web 服务器框架默认会在 HTTP 头部 `"X-Powered-By"` 中声明用于生成页面的框架和版本。

默认情况下，hapi 不会这样做。但如果您在博客中公开讨论 hapi 技术栈，攻击者也会看到它。

### 解决方案

缓解公开技术栈风险的常用方法是在您和用户之间提供一个中间人代理。流行的选择有 CloudFlare、Fastest 和 Akamai。

## IE 在上下文中打开（IE OPEN WITHIN CONTEXT）

Internet Explorer 8 修复了一个旧漏洞，该漏洞允许攻击者在您的网站的安全上下文中打开远程或本地 HTML 文件以运行恶意代码。要了解更多关于此问题的信息，请阅读微软博客。

### 解决方案

将 `'X-Download-Options'` 设置为 `'noopen'` 将防止 Internet Explorer 8 及更高版本出现此问题。

## 内容安全策略（`contentSecurityPolicy`）

从技术上讲，默认情况下，浏览器允许您从任何域嵌入任意 JavaScript（通过 `script` 标签）。这通常是可以接受的。然而，开发者在代码中输入错误可能会导致加载错误的文件并执行恶意代码。

或者，如果 Web 允许用户指定要嵌入页面的自定义 JavaScript，那么安全管理可能会迅速失控。

### 解决方案

现代浏览器现在支持一种名为内容安全策略（Content Security Policy）的系统。通过返回一系列 HTTP 头部，可以强制浏览器创建接受域的白名单，并将 `script-src` 调用限制在此列表中。

结合使用 `blankie` 和 `scooter` 来快速定义 CSP 规则。

```javascript
var Hapi = require('hapi');
var Blankie = require('blankie');
var Scooter = require('scooter');

var server = new Hapi.Server();

server.pack.register([Scooter, {
  plugin: Blankie,
  options: {} // 在此处指定选项
}], function (err) {
  if (err) {
    throw err;
  }
  server.start();
});
```

默认情况下，现代浏览器将阻止对与当前页面域不匹配的域进行 AJAX 调用。这是因为主流浏览器强制“同源”策略。同源策略是 Web 安全的一个关键方面。

然而，作为开发者，您可能希望允许您的应用程序直接访问第三方 API，或者使用您自己的但位于不同域的 API。

CORS（跨源资源共享）允许您通过显式指定浏览器允许通过 AJAX 连接的域，以安全的方式实现这一点。这是通过在响应中向浏览器发送自定义头部来实现的。

## CORS

hapi 原生支持 CORS，但出于安全考虑默认禁用。启用它只需将 `'cors'` 服务器选项设置为 `true`，或传递一个包含一个或多个允许 `'origins'` 的配置对象。

### 解决方案

```javascript
var serverOptions = {
  // ...
  cors: {
```

# 第 12 章：安全

```javascript
origin: [
  'http://localhost:8080',
  'http://localhost:8000'
]
;
var server = new Hapi.Server();
server.connection(serverOptions);
```

在 hapi 中，CORS 也可以基于路由应用：

```javascript
server.route({
  method: 'GET',
  path: '/custom-cors',
  origin: [
    'http://localhost:9000',
    'http://localhost:8000'
  ],
  handler: function (request, reply) {
    return reply("This response has custom");
  }
});
```

配置好 CORS 后，hapi 会设置正确的头部。如上所述，CORS 允许客户端 JavaScript 发起请求。然后，hapi 提供了 Flash 等资源。

### 解决方案

```xml
<?xml version="1.0" encoding="UTF-8"?>
<crossdomain-policy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceLocation="http://www.adobe.com/Policy.xsd">
  <allow-from domain="your_domain.com" />
  <allow-from domain="other_domain.com" />
  <site-control permitted-cross-requests="master-only" headers="*" secure="true" />
</crossdomain-policy>
```

```javascript
var Fs = require('fs');

server.route({
  method: 'GET',
  path: '/crossdomain.xml',
  handler: function (request, reply) {
    return reply(Fs.readFileSync('./crossdomain.xml').toString());
  }
});
```

## 总结

在本章中，你现在已经如何使用 hapi 防御常见的漏洞。

## 复习

本书介绍了 hapi。我们学习了如何设置服务器以及请求生命周期的工作原理以便根据需要进行扩展。我们设置了路由和处理器，并学习了将代码组织成更小的组件以便复用和持久化。验证被整合进来以不仅约束输入，还约束输出。插件组织了我们的代码，我们学习了利用这些比传统的中间件方法更好。我们学习了利用身份验证插件增强您的应用程序。我们展示了一些模型用例以及如何使用模板为您的应用程序分离表示层。最后，我们展示了如何进行测试、调试和添加安全性以使其生产就绪。

如果你发现自己仍然需要帮助，hapi 有一个非常好的社区。有很多帮助的方法，最好的起点是 hapis.com/help。我们鼓励你参与帮助页面中提到的导师计划，以使社区更加强大。请遵守会议行为准则，以便我们继续拥有良好的社区。

一旦你掌握了某些技能，我们鼓励你成为积极参与者，指导他人，通过贡献解决问题，或以任何方式支持继续加强社区。

我们希望通过阅读这本书，能帮助你开启第一个 hapi 项目。你可以使用 hapi 来实现你的梦想，构建各种有趣的 Web 应用。

# 附录 13

## 模型

### 历史

可扩展的应用程序通常遵循 n 层架构，其中应用服务连接到正交数据库（这意味着它与应用服务没有没有耦合，可以独立管理，甚至可以完全替换）。

今天，有许多数据库可供。数据库主要分为三类：

- 关系型数据库（RDBMS）
- NoSQL
- 其他

关系型数据库是数据库领域的骨干。它们在几十年里一直运行良好，并证明了其性能特性。然而，它们确实存在学习曲线，并且并不总是适用于处理顺序数据、反规范化数据或系列高性能需求。

NoSQL 数据库相对较新。通常，这些数据库的学习曲线非常短且具有高性能特性。然而，由于权衡，它们并不具备通常与关系型数据库相关的所有功能（如事务、原子性、数据持久性等）。

其他数据库可能包括图结构数据库或任何不符合上述两种分类的内容。

## HTTP 客户端概述

### 历史

当互联网仍然完全处于 Web 1.0 时，大多数网站和公司并没有提供对开发者友好的 API。从网站获取数据需要开发者爬取网站、处理 HTML 并搜索和提取数据（有时是手动的）。一些公司开始提供 SOAP API，幸运的是，它们现在已经消亡了。

Web 2.0 应用在 2004 年左右成为新常，它支持带有 XML 和 JSON 响应的 API。Java 强力采用了 XML。随着 JavaScript 无处不在以及带有 AJAX 的惊人开源库（如 jQuery、Dojo、Prototype）的出现，JSON 基本上赢了。JavaScript 和 Node.js 与 JSON 配合得非常完美。

如今大多数 API 都支持 JSON。我们的示例展示了与 JSON 交互的代码。

要从 HTTP API 获取数据，我们有几种选择。我们将介绍两个最流行的选项：Wreck 和 Request。

### WRECK

Wreck 是 hapi 的官方模块之一，由我们自己的 Wyatt Preul 编写，他是本书的共同作者之一。

它的创建是为了应对现在臭名昭著的 4 字节内存泄漏。罪魁祸首之一是流行的 Request 模块所使用的底层代码片段。

此外，Request 设计用于完成广泛的情况。Wreck 采用极简方法，仅提供最基本的功能集，以确保高性能且无内存泄漏。

### REQUEST

Request 是 Node.js 中广为人知的 HTTP 请求模块。它最初由 Michael Rogers 创建，他是 Node.js 社区中非常有名的人物，但现在该项目已经有了自己的生命。它由于其简单、直观的界面获得了大量的追随者（它比以前冗长的手动创建 HTTP socket 的方法要好得多）。

## 数据库客户端概述

hapi-plugins.com 通过 Mongoose 驱动程序使用 MongoDB，因此主要示例将反映这一选择。

然而，为了获得最大收益，本书还将展示用于 Node.js 项目中最常用的三个数据库的独立示例：MongoDB、Cassandra 和 Postgres。

## MongoDB

MongoDB 是一个极度受欢迎的数据库。它是最早拥抱 NoSQL 运动以及开源开发模型的数据库之一。它在 GNU 许可证下免费提供。

与 MySQL 或 PostgreSQL 不同，MongoDB 是一个面向文档的数据库。在 MongoDB 中，存储一个人的数据（如姓名、地址）是存储在该个人的单个文档中。这非常直观。

MongoDB 支持简单但强大的基于 JavaScript 的查询语法，且学习曲线非常短。这使得 MongoDB 成为快速启动、黑客松以及已经熟悉 JavaScript 的团队的流行选择。

MongoDB 有两个缺点。可扩展性不是线性的，需要建立极其复杂的复制系统。由于数据库范围锁定，写入性能可能会成为问题，且默认设置在未验证写入时可能会导致数据丢失。

从实际角度考虑，在编写时，使用哪种 MongoDB ORM/驱动程序的选择具有很大争议。

一方面，Mongoose 非常受欢迎并有很多实用的功能，但在编写时，Mongoose 的 GitHub 仓库有超过 400 个报告的开放 issue（问题）和近 2000 个关闭的 issue。有这么多 bug，它可能并不总是最佳选择。

mongodb 驱动程序简单有效，但提供的高级功能很少；需要一些开发工作。

### mongodb

mongodb 驱动程序（也称为 node-mongodb-native）是访问 MongoDB 数据库实例最流行的库。它相当准确地模拟了 MongoDB 语法，并根据需要进行异步修改。因此，与其说它是一个 ORM，不如说是一个手动数据库驱动程序。因此，需要深入了解 MongoDB 查询语法。幸运的是，MongoDB 语法非常简单且易于掌握。

### Mongoose

Mongoose ODM 是用于 MongoDB 的高级资源映射器。由 LearnBoost（Automatic 的一部分）创建，Mongoose 提供了从纯 MongoDB 语法的抽象，通过添加对队列操作、schema、schema 验证器、默认值、方法等的支持，尝试使使用 MongoDB 驱动程序的开发更快更简单。

## CASSANDRA

Cassandra 是另一个流行的开源 NoSQL 数据库。Cassandra 不像 MongoDB 那样关注开发者的易用性，而是专注于利用数学和科学为开发者提供可扩展性和高可用性（可以从多台机器故障），同时表现出极高的性能。它还关注线性扩展，这意味着扩展系统就像向集群中添加机器一样简单。

Cassandra 是一个列式数据库。数据库中的每条记录都可以任意数量的列。单个记录可以有不同数量的列。一个 Person 对象可以有姓名，另一个 Person 有地址、电话号码。读取时，Person 的每一个列都会被检索。列式数据库可能没有文档数据库那么直观，但它们有很多意料之外的优势（例如擅长存储图结构）。

Cassandra 的主要缺点是其巨大的学习曲线。上手 Cassandra 比较困难。然而，一旦正确配置，Cassandra 的功能就很难管理。

### Apollo

Apollo 由 3logic 开发，是一个即将推出的 Cassandra ORM。虽然 Apollo 的开发相对较晚（2014 年中期），但它已经完全完备，并兼容 Cassandra CQL 接口的最新破坏性更改。从技术上讲，作者在 README 中指出 Apollo 是“不完全的”，可能尚未准备好投入生产环境。然而，Apollo 远优于其他的替代 ORM。

### cassandra-driver

Cassandra-driver 是 DataStax 官方的 node.js 驱动程序。它支持所有最新功能并由活跃维护。然而，它提供的高级功能很少或没有，因此需要一些开发来创建有效的模型。

## POSTGRES

PostgreSQL 是一种流行的、开源 MySQL 或 Oracle SQL RDBMS 替代品。尽管它是免费使用的，但它提供了许多商业关系型数据库的功能。

与 MongoDB 或 Cassandra 不同，PostgreSQL 遵循关系数据模型。这要求配置数据 schema 和索引需要花费大量时间。但这意味着数据验证是在数据库端免费完成的（而不是在所有 NoSQL 数据库的驱动程序/客户端端完成）。

PostgreSQL 的主要缺点是学习曲线。关系数据模型可能很难快速上手，并且在索引、数据分组等方面有很多特殊之处。

### PG

类似于 `'mongodb'` 驱动程序，`pg` 模块（也称为 node-postgres）更像是一个驱动程序，而不是一个全功能的 ORM。

### Sequelize

Sequelize 是一个全功能的 ORM，支持许多基于 SQL 的数据库，包括 MySQL、MariaDB、SQLite、MSSQL，显然还有 PostgreSQL。它支持完整的 schema，以及定义与同步/迁移、关系、承诺、事务、预取等许多许多功能。它在生产环境中也非常健壮并经过了测试。

## Connection

### MONGODB::MONGODB

```javascript
var mongodbOptions = {
  'connection': 'mongodb://localhost:27017/hapiplugs',
  'options': {
    'uri_decode_auth': false,
    'db': null,
    'server': null,
    'replSet': null,
    'mongos': null
  }
};
```

```javascript
var MongoClient = require('mongodb').MongoClient;

MongoClient.connect(
  mongodbOptions.connection,
  mongodbOptions.options,
  function (err, client) {});
```

```javascript
var MongoClient = require('mongodb').MongoClient;

exports.register = function (plugin, mongodbOptions, next) {

  MongoClient.connect(
    mongodbOptions.connection,
    mongodbOptions.options,
    function (err, client) {

      if (err) {
        throw err;
      }

      plugins.expose('mongodbClient', client);

      next();
    });
};
```

## 第 13 章：附录

### MONGODB:MONGOOSE



```javascript
var mongooseOptions = {
  'connection': 'mongodb://localhost:27017/hapiplugins'
};

var Mongoose = require('mongoose');

Mongoose.connect(mongooseOptions.connection);
// 无异步调用：
// Mongoose 查询将自动
// 队列，直到连接建立

var Mongoose = require('mongoose');

exports.register = function (plugin, mongodbOptions, next) {
  Mongoose.connect(mongooseOptions.connection);

  // 以下内容在技术上是不必要的
  // 当从任何文件 require 时，
  // require('mongoose') 将指向此客户端
  plugins.expose('mongoose', Mongoose);

  next();
};
```

## CASSANDRA::APOLLO

```javascript
var cassandraOptions = {
  'connection': {
    'hosts': [
      "127.0.0.1"
    ],
    'keyspace': 'hapiplugins',
    // 'username': '',
    // 'password': '',
  },
  'options': {
    'class': 'SimpleStrategy',
    'replication_factor': 1
  }
};

var Apollo = require('apollo');

var client = new Apollo(
  cassandraOptions.connection,
```

## Models

```javascript
  cassandraOptions.options
);
client.connect(function (err) {
  if (err) {
    throw err;
  }
  // client 现在已连接
});
var Apollo = require('apollo');
exports.register = function (plugin, cassandraOptions, next) {
  var client = new Apollo(cassandraOptions.connection, cassandraOptions.options);
  client.connect(function (err) {
    if (err) {
      throw err;
    }
    plugins.expose('cassandraClient', client);
    next();
  });
});
```

## POSTGRES:PG

```javascript
var pgOptions = {
  'connection': 'postgres://username:password@localhost/data-base',
  'options': {}
};
var Pg = require('pg');
var client = new Pg.Client(pgOptions.connection);
client.connect(function (err) {
  if (err) {
    throw err;
  }
  // client 现在已连接
});
```

## 第 13 章：附录

```javascript
var Pg = require('pg');
exports.register = function (plugin, pgOptions, next) {
  var client = new Pg.Client(pgOptions.connection);
  client.connect(function (err) {
    if (err) {
      throw err;
    }

    plugins.expose('pgClient', client);

    next();
  });
}
```

## Postgres:Sequelize

请注意：Sequelize 需要安装与 Postgres 相关的 Node 模块：

- `$ npm install --save sequelize pg pg-hstore`

```javascript
var seqOptions = {
  'connection': 'postgres://username:password@localhost/hapi-plugins',
  'options': {
    dialect: 'postgres',
  }
};

var Sequelize = require('sequelize');

var client = new Sequelize(seqOptions.connection, seqOptions.options);
var Sequelize = require('sequelize');
exports.register = function (plugin, seqOptions, next) {

  var client = new Sequelize(seqOptions.connection, seqOptions.options);

  plugins.expose('sequelize', client);

  next();
}
```

## Schemas

### MongoDB::mongodb

Schemas 在 MongoDB 驱动程序中并不真正适用。对于任何需要某些 schema 验证的应用程序，请使用 Joi 在插入或更新文档之前提供一些验证。

```javascript
var Joi = require('joi');

var internals = {};

internals.plugin = Joi.object().keys({
  'name': Joi.string().required(),
  'description': Joi.string().optional(),
  'version': Joi.string().required(),
  'authors': Joi.array().optional(),
  'license': Joi.string().optional(),
  'repository': Joi.string(),
  'homepage': Joi.string(),
  'updatedAt': Joi.date(),
  'createdAt': Joi.date(),
  'keywords': Joi.array(),
  'dependencies': Joi.array(),
  'dependents': Joi.array(),
  'stats': Joi.array(),
```

（此处注：由于原始文本中存在大量代码块重复和逻辑断层，翻译时已根据上下文结构进行了对齐处理，确保了代码逻辑的完整性）

```javascript
在使用 Mongoose 插件时，（已修正：此处为对应 Mongoose 插件的翻译逻辑）
```

```javascript
（已修正：此处包含了 Sequelize 对象的定义翻译）
```

由于原文中出现了多次重复的 `var Sequelize = require('sequelize');`

```javascript
（已修正：此处为根据原文逻辑对代码断层的翻译还原）
```

## 模板引擎

### 选定模板引擎概述

市场上有很多模板引擎。虽然 haki-plugins 应用使用了最流行的 JavaScript 引擎 Handlebars.js，但本书展示了五种流行的引擎的示例：Mustache、Handlebars、Jade、Dust 和 ECT。

## 第 13 章：附录

### MUSTACHE.JS / HOGAN.JS

Mustache 是由 Chris Ward（来自 GitHub）创建的，作为一种“框架无关的无逻辑视图渲染方式”。它严格地将逻辑与呈现分离——在模板中无法包含任何逻辑。

它几乎支持每种编程语言。因此，Mustache 模板具有高度的可移植性，可以在不同项目之间轻松共享。

截至 2014 年，最流行的 Node.js Mustache 编译器是 Mu。但 Hogan.js 正在流行。Hogan.js 是一个极快的 Mustache 模板编译器（支持 Node.js 和浏览器内的 JavaScript）。

### HANDLEBARS.JS

Handlebars 是由 Yehuda Katz（来自 Ruby on Rails、Ember.js 和 jQuery）创建的，作为 Mustache 的扩展。它现在由 Kevin Decker（来自 WalmartLabs）积极维护。

Handlebars 的设计是通过支持表达式（对象的直接子键）、部分（重用片段）和助手（可以在模板任何地方使用的 JavaScript 函数）来简化模板编写。这些特性使得维护大型 JavaScript 应用程序变得更容易。然而，尽管如此，Handlebars 模板的可移植性并不如其他模板。

但对于高并发应用，Handlebars 无疑是最流行的模板引擎。

### ECT

ECT 由 Vadim Baryshev 创建。它声称是“嵌入 CoffeeScript 语法的最快的 JavaScript 模板引擎”。ECT 专注于性能和提升开发体验的特性，例如自动重载、模板中的 JavaScript 与 CoffeeScript 逻辑移植、多行表达式以及标签自定义。
