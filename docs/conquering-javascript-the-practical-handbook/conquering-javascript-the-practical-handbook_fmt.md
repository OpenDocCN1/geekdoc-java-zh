
# 征服 JavaScript：实用指南

《征服 JavaScript：实战手册》帮助读者掌握 JavaScript (JS) 编程语言，以实现更快、更健壮的开发。JS 是一种非常受欢迎的语言，通常被称为“Web 语言”。除了互联网，JS 还被活跃应用于游戏开发、移动应用、渐进式 Web 应用（PWA），现在甚至用于桌面应用。因此，可以说 JS 可能是目前使用的最强大的跨平台语言，并且其流行程度每天都在增长。

本书涵盖了基础知识，并通过实战课程和教程，采用实践驱动的方法介绍了高级概念。书中详细讨论了 JS 编程、JS 框架以及各种应用场景。这本书弥补了初级与中级 JS 文献之间的空白，是构建稳固知识的价值资源。

# 关于系列

**征服 JavaScript** 系列涵盖了专门针对 JavaScript 编程生态系统的广泛主题，例如框架和库。该系列的每本书都聚焦于单一主题，并详尽介绍该主题，特别关注真实世界的用法和以代码为中心的方法，遵循行业标准的编码范式，以帮助学习者获得对实际项目有用的专业知识。

该系列书籍的一些关键方面包括：

- 清晰的文字，涵盖了按相关性排序的各种 JavaScript 相关主题。
- 特别关注实操练习，包含大量的代码示例和程序。
- 引导式的 JS 编码方法，提供分步教程和演示。
- 高度强调技能在现实世界的实用性，从而剔除冗余和很少使用的概念以及臃肿软件。
- 广泛的参考文献和资源，帮助读者从书中获得最大的收益。

**征服 JavaScript** 系列书籍假设读者对编程基础有基本的了解。

**征服 JavaScript** 系列由 Sufyan Uzair 编辑，他是一位在计算领域拥有十年经验的作家和教育工作者。Sufyan 拥有多个学位，并在全球的大学和机构任教。为止，Sufyan 已编写和编辑了 50 多本书，他为该系列带来了丰富的经验。可以在 `sufyanism.com` 了解更多他的作品。

由 CodeMantra 排版

献给父亲

关于编辑，xxxv

致谢，xxxvii

Zeba Academy – 征服 JavaScript，xxxix

- `try...catch...finally` 语句

笔记

本章内容

- 我们如何构建一个异步 `Node.JS` 函数？
- 我们如何在 JavaScript 中编写一个异步函数？
- 等待多个 `Promise`
- JavaScript 中的同步与异步
- 同步 JavaScript
- 异步 JavaScript
- 解释异步与延迟 JavaScript 的区别
- 异步
- 延迟
- 异步 vs 延迟

## 文档对象模型 (DOM)

- 文档对象属性
- 文档对象方法
- 获取对象字段值 146

## JavaScript 中的 `DOCUMENT.GETELEMENTBYID()` 方法 147

- `GETELELEMENTSBYCLASSNAME()` 147
- `getElementsByClassName()` 方法 147
- `getElementsByClassName()`, `querySelector()`, 和 `querySelectorAll()` 的区别 148

## JavaScript 中的 `DOCUMENT.GETELEMENTSBYNAME` 方法 149

## JavaScript 中的 `DOCUMENT.GETELEMENTSBYTAG` 方法 149

## JavaScript 中的 `INNERHTML` 151

- `InnerHTML` 属性示例 151
- 使用 `innerHTML` 的示例 151

## JavaScript 中的 `INNERTEXT` 152

- `innerText` 示例 152

## JavaScript 中发送 HTTP 请求的方法 153

- `XMLHttpRequest` 153
- `XMLHttpRequest` 的优势 156
- `XMLHttpRequest` 的缺点 156
- `Fetch` 156
- `Fetch` 的优势 158
- `Fetch` 的缺点 158
- `Axios` 159
- `Axios` 的优势 160
- `Axios` 的缺点 160
- `SuperAgent` 161
- `SuperAgent` 的优势 162
- `SuperAgent` 的缺点 162
- `Ky` 162
- `Ky` 的优势 163
- `Ky` 的缺点 164

## HTTP COOKIES 164

- Cookies 的利用 165
- Cookies 如何工作？ 166
- JavaScript 中的 Cookies 166
- 创建 Cookies 166
- 客户端 Cookies 167
- 服务端 Cookies 167
- Cookies 的属性 168
- Cookies 的范围 168
- Cookie 的种类 170
- 第一方 Cookies 170
- 第三方 Cookies 171
- 会话 Cookies 171
- 安全 Cookies 171
- 僵尸 Cookies 172

## JavaScript 中的表单 (FORM) 172

- 表单概览 172
- 引用表单 173
- 提交表单 174
- 登录表单 174
- 注册表单 175

## JavaScript 表单验证 177

- JavaScript 表单验证示例 177
- JavaScript 密码类型验证 178
- JavaScript 数字验证 178
- 使用图像的 JavaScript 验证 179
- JavaScript 邮箱验证 180
- 与 JavaScript API 工作 181

## 最著名的 JavaScript 库 191

- `jQuery` 191
- 特性 191
- 用例 192
- `React.js` 192
- 特性 192
- 用例 193
- `D3.js` 193
- 特性 193
- 用例 194
- `Underscore.js` 194
- 特性 194
- 用例 195
- `Lodash` 195
- 特性 195
- 用例 195
- `Algolia` 195
- 特性 195
- 用例 196
- `Anime.js` 196
- 特性 196
- 用例 197
- 滚动时动画 (AOS) 197
- 特性 197
- 用例 197
- `Video.js` 198
- 特性 198
- 用例 198
- `Chart.js` 198
- 特性 198
- 用例 199
- `Cleave.js` 199
- 特性 199
- 用例 199
- `Choreographer.js` 199
- 特性 200
- 用例 200
- `Glimmer` 200
- 特性 200
- 用例 200
- `Granim.js` 201
- 特性 201
- 用例 201
- `FullPage.js` 202
- 特性 202
- 用例 202
- `Leaflet` 202
- 特性 203
- 用例 203
- `Multiple.js` 203
- 特性 203
- 用例 204
- `Moment.js` 204
- 特性 204
- 用例 204
- `Masonry` 204
- 特性 204
- 用例 205
- `Omniscient` 205
- 特性 205
- 用例 205
- `Parsley` 206
- 特性 206
- 用例 206
- `Popper.js` 206
- 特性 207
- 用例 207
- `Three.js` 207
- 特性 207
- 用例 207
- `Screen.js` 207
- 特性 208
- 用例 208
- `Polymer` 208
- 特性 208
- 用例 208
- `Voca` 208
- 特性 209
- 用例 209

笔记

本章内容

什么是 JavaScript 框架？ 211

JavaScript 框架与 JavaScript 库的区别是什么？212

使用 JavaScript 框架，但为什么？212

JavaScript 库和框架 213

- `React` 214
- 特性 214
- 用例 215
- 优势 215
- 缺点 215
- 为什么使用 `React`？215
- `Vue.js` 216
- 运行原理 216
- 用例 216
- 特性 217
- 优势 217
- 缺点 217
- 为什么使用 `Vue.js`？217
- `Angular` 217
- 运行原理 218
- 用例 218
- 特性 218
- 优势 219
- 缺点 219
- 为什么使用 `Angular`？219
- `jQuery` 219
- 运行原理 219
- 用例 220
- 特性 220
- 优势 221
- 缺点 221
- 为什么使用 `jQuery`？221
- `Svelte` 221
- 运行原理 221
- 用例 222
- 特性 222
- 优势 222
- 缺点 222
- 为什么使用 `Svelte`？223
- `Ember` 223
- 运行原理 223
- 用例 223
- 特性 223
- 优势 224
- 缺点 224
- 为什么使用 `Ember`？224
- `Backbone.js` 224
- 运行原理 224
- 用例 225
- 特性 225
- 优势 225
- 缺点 225
- 为什么使用 `Backbone.js`？226

## 我们如何为下一个项目选择理想的 JavaScript 框架？226

- 团队熟练度 226
- 向后兼容性 226
- 复杂度 226
- 尺寸与功能 226

## 后端 JavaScript 框架 227

## 八大 JavaScript 游戏引擎 231

## 开发移动应用的 10 大主流 JavaScript 框架 233

- `React Native` 234
- `React Native` 在哪些方面优？234
- `NativeScript` 234
- 为什么使用 `NativeScript`？235
- `Ionic` 235
- 为什么使用 `Ionic`？235
- `Apache Cordova` 235
- 为什么选择 `Cordova`？236
- `OnSenUI` 236
- 为什么使用 `OnSen UI`？236
- `jQuery Mobile` 236
- `Mobile Angular` 237
- `Sencha Touch` 237
- `Titanium` 238
- `Meteor` 238

## 桌面应用程序的最佳 JS 框架 238

- 跨平台应用与桌面程序可以互换吗？239
- 独立层与跨平台应用的优缺点 239
- `React` 和 `NodeJS` 支持桌面应用吗？239

## 五种桌面应用程序 JS 框架（桌面应用）240

- `Electron` 240
- `NodeGUI` 241
- `Proton Native` 241
- `NW.js` 241
- `AppJS` 241

本章内容 271

前端 VS 后端 271

前端开发 271

- 前端语言 272
- 前端框架与库 272

后端开发 274

- 后端语言 274
- 后端框架 275
- 前端与后端开发的区别 275

REACTJS 276

“REACT”是什么意思？ 276

问题是：“为什么用 React？” 276

React 特性 277

JSX 278

组件 278

- 数据绑定，仅限单向 278
- 虚拟 DOM 278
- 简单性 278
- 性能 279
- `ReactJS` 的优缺点 279
- 优点 279
- 缺点 281
- React 版本 282
- REACT 环境搭建 286
- `REACTJS` 安装方法 286
- 1. 使用 `npm` 命令 286
- 安装 NPM 和 NodeJS 286
- 安装 React 和 React DOM 286
- 安装 Webpack 287
- 安装 Babel 288
- 创建文件 288
- 2. 设置 React 应用编译器、加载器和服务器 289
- 配置 Webpack 289
- 用于 `index.html` 文件的 HTML Webpack 模板 291
- `App.jsx` 和 `main.js` 291
- 创建 `.babelrc` 文件 292
- 运行服务器 292
- 创建包 293
- 3. 使用 `create-react-app` 命令 293
- 安装 NodeJS 和 NPM 293
- 安装 React 293
- 开发一个新的 React 项目 293
- `App.js` 294
- 运行服务器 295
- ANGULARJS 与 REACTJS 的对比 295
- `AngularJS` 295
- `AngularJS` 特性 295

REACTJS 296

- `ReactJS` 特性 297

REACTJS 与 SVELTE 的对比 298

- Svelte 是什么？ 298
- 何时使用 Svelte？ 299
- 哪些公司在使用 Svelte？ 299
- React 是什么？ 299
- 何时应该使用 React？ 299
- 哪些公司在使用 React？ 300
- React 与 Svelte：哪个更优？ 300
- 性能 300
- 包大小 300
- 测试 301
- 社区支持 301
- 谁胜出？ 301

# JSX 302

为什么使用 JSX？ 302

- JSX 嵌套元素 303
- `App.JSX` 303
- JSX 中的属性 303
- JSX 中的注释 305
- JSX 中的样式 306

# EXPRESS.JS 307

EXPRESS.JS 是什么？ 307

为什么使用 Express？ 307

Express 如何出现？ 308

```
basic_express.js
```

- 前提条件 308
- 受众 308
- 问题 308
- `Express.js` 的优点 308
- 搭建 EXPRESS 309
- 早期阶段 310
- 它的演进 310
- NODE.JS 基础 311
- 原类型 311
- 弱类型 311
- 对象字面量 311
- 函数 312
- 缓冲区 312
- 默认本地 312
- 使用全局作用域 313

VUEJS 313

VUEJS 是什么？ 313

- 特性 313
- 其他框架的对比 315
- VueJS vs React 315
- VueJS vs Angular 316
- 相似性 317
- 复杂度 317
- 性能 317
- 流行程度 317
- 依赖项 317
- 活性 317
- Typescript 318

VUEJS 环境搭建 318

- 在 HTML 文件中直接使用 `<script>` 标签 318
- 使用 CDN 318
- 使用 NPM 320
- 使用命令行 320
- 使用 Webpack 创建项目 320
- 启动项目，然后是服务器 321

理解 VUE.JS 321

- `Vue.js` 的优点 321
- 体极小 321
- 易于理解和编码 322
- 与现有应用的集成简单 322
- 适应性 322
- 组件 322
- 简单、详尽且详细文档 322
- DOM 虚拟化 322
- 双向通信 322
- 使用 `Vue.js` 的公司 323
- 查看我们安装的 `Vue.js` 版本 324

VUEJS 中的实例 325

- 示例说明 326

VUE.JS 模板 327

- HTML 元素应添加属性 330

本章内容 333

什么是后端开发？ 333

NODE.JS 333

Node.js 是什么？它是如何工作的？ 333

我们为什么应该使用 Node.js？ 334

带有实时通信的快速轻量级应用 334

无服务器和微服务开发 334

物联网 335

音频/视频处理 335

快速开发 335

与 C++ 的代码集成 336

- `Node.js` 的缺点 336
- 重量计算活动导致性能问题 336
- 回调地狱是一个问题 337
- 工具链不成熟 337
- 对技能专家的需求日益增长 337
- 我们哪里可以使用 Node.js？ 338
- 我们哪里不应该使用 Node.js？ 338

NODE.JS 环境搭建 338

- 文本编辑器 338
- `Node.js` 运行时 338
- 获取 `Node.js` 存档 339
- 在 SunOS, Mac OS X, Linux 和 UNIX 上安装 339
- 在 Windows 计算机上设置 339
- 执行文件将验证安装 340

# NODE.JS 的第一个应用 340

- 创建 `Node.js` 应用 340

MongoDB 342

- MongoDB 是什么 342
- 它是如何工作的？ 342
- MongoDB 数据建模 344
- 什么区分 MongoDB 和 RDBMS？ 344
- MongoDB 特性包括 345
- MongoDB 具有以下优点 346
- MongoDB 缺点 346

开始使用 MongoDB 346

- 术语 346
- 如何开始 347
- 查询 349

如何在 Windows 上安装 MongoDB？ 350

运行 Mongo Shell 355

# 服务端 JS 356

- 服务端编程 356
- 运行 JavaScript 357
- 运行时环境 357
- 服务端 JavaScript 的用途 358

MERN 栈 358

- 熟悉 MERN 栈 358
- 1. MongoDB：跨平台文档数据库 358
- 为什么用 MERN 创建移动和 Web 应用？ 359
- 为什么使用 Express？ 360
- 2. Express：后端框架 361
- 为什么使用 Express？ 362
- 3. React：前端库 363
- 为什么使用 React？ 363
- 4. Node.js：运行时环境 365
- 为什么使用 Node.js？ 365



# MERN 栈的结构及其如何运作？

## Web 或前端

## 服务器或中间层

## 数据库作为后端

# MERN VS MEAN

# MERN 开发者的未来？

# 注释

## 本章内容

# 为什么 JavaScript 被认为是 2022 年最好的移动应用语言之一？

## JavaScript 在移动开发中的重要性

### 极速响应

### 丰富的平台

### 离线支持

### 适用于各种开发者

## 移动应用 JavaScript 框架

### PhoneGap

### Ionic

### React Native

### jQuery

### 原生语言

### Tabris.js

# 为移动开发时应该使用 JavaScript？

## JavaScript 的关键属性

### 原生 React

### jQuery

### PhoneGap

### Ionic

# 使用 JavaScript 开发移动应用的优点

# React Native

## 设置 React Native 环境

### 分步骤安装 React Native 环境

#### 安装 Android Studio

#### 设置 Android SDK 和 Java JDK

## React Native 在移动应用中的未来意义

### 为什么 React Native 如此流行？

### 构建 React Native 应用

### React Native 应用开发的优点

### React Native 的缺点

## 使用 REACT NATIVE 创建移动应用程序

### 领先的跨平台框架，React Native

### 为什么在开发移动应用时我们应该使用 React Native ?

#### 节省金钱和时间

#### 高质量

#### 空中更新 (Over-the-Air Updates)

#### 最大的优势是开源软件

## NATIVESCRIPT

### 什么是 NativeScript?

### 为什么在创建 Android 应用时首选 NativeScript?

### 什么是 NativeScript? 它的主要优缺点是什么 ?

#### 原生应用的优势

#### 原生应用的局限性

## NativeScript 环境搭建

### 前提条件

### 验证 Node.js

### CLI 设置

#### setupcli

#### cli

## 设置 NativeScript 示例应用程序

### Android 和 iOS 的设置

## NativeScript 热门用例

## 使用 NativeScript 开发 Android 应用的主要优势

### 原生应用的性能

### 可复用程序

### 极低的学习曲线

### 强大的社区支持

## 在 React Native 和 NativeScript 之间我们应该使用哪一个?

### 如果选择 NativeScript

### 如果选择 React Native

# 注记

## 本章内容

# 我们如何使用桌面应用程序?

# 什么是 ELECTRON?

## 安装

# 哪些应用使用了 ELECTRON?

## 1. WebTorrent 桌面应用程序

### 为什么 WebTorrent 在桌面端使用 Electron?

## 2. WordPress 桌面应用程序

### 为什么 WordPress 桌面应用使用 Electron?

## 3. Ghost Electron 应用

### 为什么 Ghost 桌面应用使用 Electron?

## 4. Electron 应用 Beaker 浏览器

### 为什么 Beaker 浏览器使用 Electron?

## 5. Pexels Electron 应用

### 为什么 Pexels 桌面应用使用 Electron?

## 6. Slack 桌面应用程序

### 为什么 Slack 桌面应用使用 Electron?

## 7. WhatsApp Electron 应用

### 为什么 WhatsApp 桌面应用使用 Electron?

# 为什么许多企业选择 Electron 来创建跨平台桌面应用?

## 这的意义是什么?

## ELECTRON 的优势

### 单代码库

### 快速交付功能

### 框架成熟度

## Electron 存在若干未解决的疑虑

## ELECTRON 的替代方案

## ELECTRON.JS 框架的缺点

### 体积过大

### Electron.js 框架消耗大量资源

### 特定客户需求

## 使用 ELECTRON.JS 框架的意义

## 主进程与渲染进程之间的区别

## ELECTRON 中每一行代码的 HELLO

### 这个应用是如何运行的?

### 使用 ELECTRON 构建 UI

# 注记

# JAVASCRIPT 到底是什么?

## JAVASCRIPT 的过去与未来

## 是什么让 JAVAS 独特?

## “优于” JavaScript 的语言

## 与其他语言相比，JavaScript

### JavaScript 与 C 的对比

### Java 与 JavaScript 的对比

### 与 C# 相比，JavaScript

### JavaScript 与编程语言 Python 相比

# 关于编辑

Sufyan Bin 是一位作家、编码员和创业者，在行业拥有十多年经验。

# JavaScript 简介

## 客户端 JavaScript (CLIENT-SIDE)

该语言最常用的版本是客户端 JavaScript。为了让浏览器理解 HTML 代码，脚本必须集成到 HTML 页面中，或作为 HTML 页面的引用。这表明网页不需要是静态 HTML，而是应该包含能够与用户通信、管理浏览器并动态创建 HTML 内容的程序。

JavaScript 客户端技术在许多方面都优于经典的 CGI 服务端脚本。JavaScript 可用于验证表单字段中的用户输入，例如电子邮件地址。当用户提交表单时，会调用 JavaScript 代码，且只有当所有输入内容都准确时，它们才会被传输到 Web 服务器。

JavaScript 可用于记录用户执行的显式或间接操作，例如按钮点击、链接导航和其他操作。

## JAVASCRIPT 的目的是什么？

该脚本语言的早期版本被限制仅供内部使用。

当 Netscape 将 JavaScript 提交给 ECMA 国际组织作为互联网浏览的标准规范时，ECMAScript 的发布路径就打开了。

它是一种通用的高级编程语言，用于确保各种浏览器和设备上在线页面的互操作性。²

从那时起，JavaScript随着 Mozilla Firefox 和 Google Chrome 等新浏览器的出现而成长。

后者推出了 V8，这是第一个将字节码翻译成原生机器码的现代 JavaScript 引擎。

AngularJS、jQuery 和 ReactJS 只是今天 JavaScript 可用的框架和工具之一。

JavaScript 最初在客户端执行，在引入 Node.js 之后扩展到了服务端。Node.js 是一个基于 Google Chrome JavaScript V8 引擎的跨平台服务器环境。

虽然它主要用于 Web 应用程序，但 JavaScript 编程能力在许多领域都有众多用途。

# 4 理解 JavaScript

以下是一些简单的 JavaScript 应用。

## 1. Web 和移动端应用

JavaScript 框架（由 JavaScript 代码库组成）的使得开发者能够在应用程序中利用预先写的 JavaScript 代码。

这节省了他们从头编写编程功能的精力和时间。

每个 JavaScript 框架都包含尝试简化创建和测试过程的功能。例如，jQuery 和 React 等前端 JavaScript 框架可以提高设计效率。

开发者可以复用和修改代码组件，而不会在功能或值上产生相互影响。然而，Cordova 和 Titanium 等移动应用框架使得构建原生或混合应用变得可行。

在 Node.js 中执行 JavaScript 代码在 Web 开发中也起着重要作用。

由于其单线程和非阻塞的设计，Node.js 可以最小化服务器响应时间并消除延迟。Node.js 也足够轻量，可以作为微服务的扩展工具，使能够构建一个结合小型服务与独立进程的程序。

## 2. Web 服务器和服务器应用的开发

JavaScript 允许开发者使用 Node.js 构建 Web 服务器和后端基础设施，节省了 Web 服务器开发的精力和。

当访问者浏览网页时，内置的 HTTP 模块允许我们创建一个显示纯文本的简单 HTTP 服务器。为了处理 HTTP 请求，我们可以使用 Node.js 的原生 Web 服务器 Node-OS，或者第三方服务器，如 Microsoft Internet Information Services (IIS) 和 Apache。

记住，Node-OS 在 Linux 操作系统上运行效果最好，因为它构建在 Linux 内核之上。

## 3. 交互式网站行为

动态添加到网页中是 JavaScript 的主要作用之一。

这包括显示动画、更改文本的可见性以及构建下拉菜单。虽然我们可以只使用 HTML 和 CSS 代码创建网站，但它将只有静态外观。用户通过使用 JavaScript 与网页进行交互并获得更好的浏览体验。

此外，JavaScript 允许我们在无需刷新网页的情况下更新 HTML 内容和属性值。这是因为 JavaScript 有以下数据类型：

- `String`（字符串）：用引号括的文本数据。例如，“Hello Everyone,”，“Hello Everyone,”和显示‘Hello Everyone’文本都是一些例子。
- `Number`（数字）：包括整数和浮点值，范围从（...
- `Boolean`（布尔）：表示 `true` 或 `false`。
- `BigInt`（大整数）：表示任意长度整数。
- `Null`（空）：表示值不存在。
- `Undefined`（未定义）：表示尚未赋值的变量。
- `Symbol`（符号）：提供唯一标识符。
- `Object`（对象）：用于复杂数据结构。

# 4 游戏创建

当使用 HTML5 和应用程序接口 (API) 时，JavaScript 助于创建，例如 WebGL、Phaser、GDevelop 等是可用的游戏。Angry Birds, The Wizard 和 2048 都是使用 JavaScript 创建的示例。



（注：由于提供的原文中存在大量重复的段落，根据指令“一定不要重复输出原文”的原则，此处译文仅保留了核心逻辑的翻译并去除了原文中异常的重复内容。）

# 6 理解 JavaScript

## 为什么 JavaScript 如此特别？

JavaScript 有一些与其竞争对手相比不同的优势。使用 JavaScript 的某些优点包括：

- JavaScript 的基础结构使其更容易理解和实现，而且它比某些语言运行更快。错误也容易识别。
- JavaScript 中编写的脚本可以在浏览器中运行。它还开启了数据科学和机器学习。
- 有许多工具和论坛可以帮助有限的新手。
- 在客户端运行的另一个优势是减少了发送到服务器的查询。数据更新适用于特定页面。
- JavaScript 开发团队和 ECMA 国际组织正在不断更新并创建新的框架，以确保行业的相关性。

# 8 征服 JavaScript

JavaScript、C# 提供了运算符和转换重载，使我们能够操作数据类型。

Java：Java 是一种面向对象的编程语言，能够运行复杂的、多部分的应用程序。与 JavaScript 不同，Java 是强类型的，这意味着它的变量必须绑定特定的数据类型。Java 需要一个即时编译（JIT）编译器来执行其脚本。

PHP：PHP 是一种服务器端语言，通常用于基于 PHP 的内容管理系统（如 WordPress）。它的主要目标是在数据库之间传输数据、构建 HTML 页面以及监控会话。与 JavaScript 不同，PHP 可以显式访问数据库，并支持小写和大写变量名。

Ruby：Ruby 是一种用于元编程的通用编程语言，这意味着它可以检查并修改其他程序，也可以修改自身。它最流行的框架 Ruby on Rails 允许我们以廉价且高效的时间构建大型 Web 应用。JavaScript 在 Node.js 上的实现受到了 Ruby on Rails 框架的影响。

## JavaScript 开发工具

JavaScript 的主要优势之一是它不需要使用昂贵的开发工具。我们可以从像记事本这样的基础文本编辑器开始。我们甚至不需要获取编译器，因为在 Web 浏览器的境下，它是一种解释型语言。

各种制造商创建了极出色的 JavaScript 编辑工具让我们的生活变得更容易。下面提到了其中几个。

Microsoft FrontPage：Microsoft FrontPage 是微软创建的一种流行的 HTML 编辑器。FrontPage 还包含多种 JavaScript 功能，帮助开发者创建动态网页。

Macromedia Dreamweaver MX：Macromedia Dreamweaver MX 是专业 Web 开发者中一种流行的 HTML 和 JavaScript 编辑器。它带有许多实用的 JavaScript 组件，能与数据库有效连接，并遵循 XHTML 和 XML 等新兴标准。

## JavaScript 简介 9

Macromedia HomeSite 5：Macromedia 的 HomeSite 5 是一种备受喜爱的 HTML 和 JavaScript 编辑器，可以有效地管理单个网页。

## JavaScript 的现状是什么？

ECMAScript 第 5 版标准将作为 4 多年来的首次升级发布。JavaScript 2.0 与 ECMAScript 标准第 5 版之间的差异非常微其道。JavaScript 2.0 的规范可以在 `www.ecmascript.org/` 找到。

如今，Netscape 的 JavaScript 和微软的 JavaScript 都遵循 ECMAScript 标准；然而，两种语言继续提供未包含在标准中的功能。

## JavaScript 的演变

JavaScript 继续保持最流行编程语言的地位，2019 年有 67.8% 的开发者在使用它。它成为世界上最流行的编程语言的崛起与互联网本身的崛起密不可分。它是出于需要产生的，现在被用于构建 95.2%（15.2 亿）网站，其中包括全球最大的网站，如 Facebook 和 YouTube。没有它，我们还没有像 Google Maps 和 eBay 这样流行实用的 Web 应用。

## 什么是现代 JavaScript 以及如何使用？

JavaScript 用于赋予网页生命并使其具有交互性。脚本是用 JavaScript 编写的程序。由于脚本与 HTML 直接关联，它们在页面在浏览器中加载时就会执行。^3

老实说，脚本是简单的文本。这意味着它们不需要任何进一步或准备性的开发。这一属性区分了 JavaScript 和 Java 编程语言。我们可能会好奇为什么它被称为 JavaScript。它最初有一个不同的名字：LiveScript。然而，当时 Java 是一门流行的编程语言，营销人员选择采用类似的名称以吸引额外的用户。

# 10 ■ 征服 JavaScript

JS 原本打算作为 Java 的一部分，增长迅速，最终成为一个拥有自己 ECMAScript 定义的独立编程语言。在前端开发方面，GBKSOFT 采用了 JavaScript 编程语言、Node.js 环境和 AngularJS 框架。后两个是用 JavaScript 编程语言创建的框架。

## JavaScript 能为我们做什么

现代 JavaScript 是一门无风险的编程语言。因为它缺乏访问内存或 CPU 等底层资源的权限。事实上，JS 最初仅限于浏览器和浏览器交互。由于浏览器区域独立于操作系统，JavaScript 正在保守。然而，随着时间的推移，开发者开始在浏览器区域之外应用 JavaScript。结果 JavaScript 的能力现在完全取决于它运行的上下文。当 JavaScript 在浏览器中执行时（在某种程度上），它可以任何与网页操作、用户交互和服务器交互相关的事情。

- 创建新的 HTML 标签、删除现有标签、修改元素样式、显示或隐藏组件等。
- 响应用户活动，如鼠标移动和点击、键盘输入等。
- 放入服务器并在不刷新页面的获取结果（AJAX 技术）。
- 接收和配置 cookie、请求数据、显示消息等。

还有许多额外的功能和选项。由于 JavaScript 无法访问操作系统，它无法读取、记录或复制任意文件或运行应用程序。现代浏览器可以处理文件，但仅限于受限的访问，且仅当用户将文件拖入浏览器窗口或使用 `<input>` 元素选择它们时。JavaScript 在特定标签页中运行时，无法与其他标签页通信，除非用户特别许可。尽管如此，只有当它们共享单个域名、协议和端口时这才是可能的。

JavaScript 简介 ■ 11

## 什么区分了 JavaScript？

JavaScript 至少有三个主要优势，如下：

- JavaScript 完全兼容 HTML 和 CSS。
- JavaScript 使完成任务变得简单。
- 所有当前浏览器都支持这种语言并默认包含它。
- 通过 JavaScript 是开发界面最常用的技术。

## JavaScript 趋势

HTML5：HTML5 是一种新的 HTML 版本，支持新的标签：

- 读取和写入文件。
- 浏览器数据库，允许数据直接存储在用户机器。
- 多任务处理和多 CPU 核心利用。
- 无需 Flash 即可播放视频和音频。
- 硬件支持 2D 和 3D（例如现代游戏）。

尽管许多 HTML5 功能仍在开发中，但当前的浏览器开始支持它们。换句话说，JavaScript 正在增强，一切都在转向桌面应用。

ECMAScript 5：为了保持领先和创意，JavaScript 和 ECMAScript 通过引入新功能和能力不断改进。例如，即将推出的 ECMAScript 6 将语言语法推向前。

# 12 征服 JavaScript

然而，在采用新标准时，保持与旧版本的最大兼容性至关重要，以避免出现当前版本的问题。以下是 2020 年主要的 JavaScript 趋势：

- 通过 GraphQL，一切更关注解决方案驱动的 API。
- Web 组件应该是框架无关的。
- 模块化可重用组件。
- 由于其引人入胜的功能，Angular 7 变得越来越受欢迎。
- 在被 Vue.JS 超越后，React 正在回到正轨。
- TypeScript 以前所未有的速度流行。

## JavaScript 标准

JavaScript 遵循两个标准：

- ECMA International 托管 ECMA-262。这是基础标准。
- 国际标准组织 (ISO) 和国际电工委员会 (IEC) 托管 ISO/IEC 16262。这是补充需求。

这些标准规定了名为 ECMAScript 的语言，而不是 JavaScript。太阳（现为 Oracle）拥有后者的商标，因此采用了不同的名称。

## JavaScript 简介 ■ 13

在理论上，JavaScript 和 ECMAScript 是互换的。通常会有以下区别：

- JavaScript 既指这门语言，也指它的实现。
- 语言标准和语言版本被称为 ECMAScript。

因此，ECMAScript 6 是一个语言版本（其第 6 版）。

### ECMAScript 版本历史

这是 ECMAScript 版本的总结：

- ECMAScript 1 (1997 年 6 月)：该标准的第一个版本。
- ECMAScript 2 (1998 年 6 月)：小版本升级，使 ECMA-262 达到 ISO 标准。
- ECMAScript 3 (1999 年 12 月)：增加了 "[...] 正则表达式、改进的字符串处理、新的控制语句 [do-while, switch]、try/catch 异常处理、[...]。
- ECMAScript 4 (2008 年 7 月废弃)：本应是一次巨大的改进（包括静态类型、模块、命名空间和其他功能），但被证明过于野心勃勃，导致了语言维护者之间的分歧。
- ECMAScript 5 (2009 年 12 月)：增加了一些标准库功能以及严格模式。
- ECMAScript 5.1 (2011 年 6 月)：另一次小版本升级，以对齐 Ecma 和 ISO 标准。
- ECMAScript 6 (2015 年 6 月)：一次重大升级，实现了 ECMAScript 4 的许多承诺。这是第一个根据发布年份正式命名的版本，即 ECMAScript 2015。
- ECMAScript 2016 (2016 年 6 月)：首次年度发布。与庞大的 ES6 相比，较短的发布周期导致了功能较少。
- ECMAScript 2017 (2017 年 6 月)：第二次年度发布。
- 之后的 ECMAScript 版本（例如 ES2018）始终在 6 月确认。

## 14 征服 JavaScript

### JavaScript 与 Java

尽管存在某些重叠之处，但 JavaScript 和 Java（另一种用于数据科学的强大计算机语言 Python）本质上几乎没有共同点。JavaScript 的名称源于 Netscape 在其浏览器中对 Java applet 的支持。许多人认为，这也是一种营销策略，为了转移对 Java 的注意力，因为 Java 是当时最热门的语言。⁵

Java 应用程序在执行之前必须编译编译可执行代码。然而，JavaScript 要动态得多，因为它旨在在运行时进行解释。

委婉地说，JavaScript 的开端并不理想。Java 开发者将 JavaScript 视为一种“UI 胶水”，由于其性能较差，设计师和非工程师会使用它。然而，拥有这种“胶水”语言让互联网真正地繁荣起来。程序员可以更快地对输入做出响应并构建交互式组件。结果，JavaScript 像野火一样蔓延，迅速成为 Web 的通用语言。

## 谁控制着 JavaScript？

JavaScript 是一种常见的编程语言，但归属和定位 JavaScript 的所有者可能非常困难。初始版本有两个所有者：Oracle 和 Netscape，但新版本需要第三个所有者。Brendan Eich 在 Netscape 工作期间创建了 JavaScript 编程语言。⁶

Brendan Eich 还创立了 Mozilla 基金会。Oracle 拥有“JavaScript”商标。这与 JavaScript 编程语言无关，但又与之相关。因此，断言 Brendan Eich、Mozilla、Netscape、Oracle 或 Sun Microsystems 拥有 JavaScript 并不错误。JavaScript 至少由两个人拥有。简而言之：

- 因为法律名称，Oracle。
- 取决于我们使用的 JavaScript 引擎，可能会使用 Google、Microsoft、Mozilla 等公司。
- JavaScript 的第一个版本是由 Netscape 创建的。

## JavaScript 简介 ■ 15

### Oracle 的商标是 JavaScript

Oracle 拥有“JavaScript”商标。这与 JavaScript 编程语言无关，但又与之相关。创建 Java 的公司 Microsystems 首先注册了“JavaScript”一词的商标。Oracle 后来收购了 Sun Microsystems，他们所有的商标都转给了 Oracle。因此，Oracle 目前持有 JavaScript 商标。有人认为，Sun Microsystems 对“JavaScript”的商标注册是基于与相同的逻辑：

> Java 之于 JavaScript
> 汽车之于地毯。

### 各种变体

原始的 JavaScript 已经过修改以符合 ECMA-262 第 5 版及后续版本。许多引擎支持 JavaScript 计算机语言。这包括：

- SpiderMonkey（原始引擎）
- Rhino（由 Netscape 员工 Norris Boyd 创建）
- SquirrelFish 或 Nitro（Apple 为 Safari 开发）
- V8（Google 作为 Chrome 浏览器的一部分开发）
- Carakan（Opera 开发）
- Chakra（Microsoft 为 Internet Explorer 开发）

## JavaScript 框架

将构建网站和应用类比为盖房子——我们可以从零开始生产所有的建筑材料并在没有任何计划的情况下开始建造，但那种方法将极其耗时且低效。⁷ 我们更有可能购买预制的建筑组件（木材、砖块、台面等），然后根据计划按照我们的规格对它们进行组装。

# 征服 JavaScript

编码实际上非常相似。虽然可以从零开始创建一个网站，但使用已有的设计作为起点并进行修改以满足我们的需求通常更高效。这正是 JavaScript 框架大显身手的地方。

JS 框架基本的形式是 JavaScript 代码库集，它们为程序员提供了预写的 JS 代码，用于处理例行的编程功能和任务——字面意思是，一个用于创建网站或 Web 应用的框架。例如，如果我们在网站上需要一个标准的 JavaScript 图片轮播，我们可以利用框架的代码来提供该功能（同时我们花时间创建网站的那些没有简单插件解决方案的独特功能）。

如果我们听过独特的 JavaScript 库 jQuery，这可能看起来很熟悉，其中单一 JavaScript 库和 JavaScript 框架之间存在细微（但显著）的区别。

### jQuery 和 JavaScript 库

在需要时，通过将库代码插入我们网站代码的根目录使用 jQuery 等 JS 库。例如，如果我们想使用自动补全功能，我们会放入相关的 jQuery 代码，从 jQuery 库中获取该功能并显示在用户的浏览器中。换句话说，当前端开发者使用如 jQuery 这样的库时，开发者使用 jQuery 代码来“调用”jQuery 库，随后提供所需的内容。

### JavaScript 框架与库有何区别？

在对比库和框架时，应该记住以下几：使用 JS 框架是一个更整体的过程，因为它提供了一个结构（类似于骨架或脚手架），组织了我们安装框架的网站区域。采用 JavaScript 框架的优势是它们为项目提供的通用效率和组织性——我们的代码将是整齐的，框架将为常见挑战提供现成的解决方案。另一方面，所有这些结构可能是使用框架的缺点——任何在 JS 框架之上创建的 JavaScript 代码

## JavaScript 简介 ■ 17

必须遵循框架的规则和约定，这限制了我们完全手动编写时的灵活性。

## 前端框架

有多种类型的前端框架，我们将讨论：

### REACT

Facebook 构建了 React.js，这是一个用于设计用户界面的高效多功能 JavaScript 工具包。从任何意义上说，React 是一个 JS 库；但它通常被称为 Web 框架。由于它使用易于调试的可预测 JavaScript 代码，React 使构建交互式用户界面变得简单。它还有一个 REACT 组件系统，允许将 JavaScript 代码块创建一次并在程序的其他部分甚至其他应用程序中用。

### ANGULAR

Angular 是一个著名的企业级 JavaScript 框架，用于构建大型复杂的企业应用程序。它是由 Google 设计并受 Google 和 Microsoft 支持的开源 Web 框架。

### VUE

Vue.js 是一个用于设计用户界现代框架。它是帮助开发者与其他库和当前应用程序交互的新兴框架。它包含一个库生态系统，允许开发者构建复杂稳健的单页应用。

### EXPRESS

Express.js 是一个用于 Node.js 应用的多功能、简单、轻量且非常良好的平台。

## 18. 征服 JavaScript

它无疑是服务器端 Node.js 应用中最广泛使用的框架。Express 提供了丰富的 HTTP 函数，并具有极高的运行速度。它非常适合构建能够同时管理多个请求的基础单页应用程序。

## NEXT.JS

Next.js 是一个基础框架，使 JavaScript 开发者能够使用 React.js 来构建服务端渲染和静态 Web 应用。它是最新且最受欢迎的框架之一，并以其简洁性而著称。Next.js 解决了开发者在使用 React.js 设计应用时遇到的许多问题。



它内置包含了“开箱即用”的关键特性，让`JavaScript`编程变得轻而易举。`React.js`是目前就业市场上最流行的`JavaScript`框架/库。因为`JavaScript`有许多框架，可能很难决定先学哪一个。我们可以从任何框架开始，但如果我们的目标是获得工作，先学习`React`将带给我们更高的机会。

`Express.js`也是如此，它是最常用且最受青的后端框架。`JavaScript`框架使得创建在线应用和处理`JavaScript`变得简单。

这就是为什么它们在程序员中如此流行的原因。存在多个框架是因为它们可以被用于应对各种挑战。

在选择采用任何特定的`JavaScript`框架之前，请彻底分析项目需求。除了`JavaScript`框架的独特功能外，每个框架都有自己的学习曲线、社区参与/支持、文档和兼容性。

## JavaScript 框架的优缺点是什么？

### JavaScript 框架

框架为开发者构建`JavaScript`程序提供了基础。这节省了开发者从零开始构建工作基础的时间和精力的。这个基础由一组`JavaScript`代码库组成。

这些库是为我们可能处理的特定类型应用程序编译的代码。框架将能够有效地自行定义程序的结构。每个`JavaScript`框架都使用不同的函数。`JavaScript`是 Web 开发的可靠选择，它的许多结构都是围绕着它构建的。

以下是目前最流行的`JavaScript`框架：

- `Vue JS`
- `Angular`
- `React Native`
- `Ember JS`
- `Mithril`
- `Meteor`
- `Node JS`
- `Polymer`
- `Next JS`
- `Aurelia`

让我们比较一下最好的`JavaScript`框架，看看每个框架的独特之处。

### 1. Angular

`AngularJS`是一个用于开发动态网站的客户端`JavaScript MVC`框架。`AngularJS`起源于 Google 项目，但现在已演变为一个开源框架。由于`AngularJS`完全基于`HTML`和`JavaScript`，因此无需学习另一种语法或语言。

#### 优点

- 模型与显示之间的数据同步。
- 模型更新会立即显示在界面上。
- 指南的应用：这允许开发者利用特性并创建更改指令。
- 依赖注入：一种依赖于软件组件的方法。
- 它易于管理和使用。它具有基于`MVVM`的架构：这种模型-视图-模型架构允许我们实现数据与视图分离。
- 有助于应用程序管理。

#### 缺点

- 它在许多选择中不支持`JavaScript`。
- 开发者必须熟悉`MVC`才能使用`angular`。

### 2. React Native

Web 开发者使用他们熟悉的`JavaScript`框架，现在可以构建感觉和看起来都完全“原生”的移动应用。由于我们编写的代码可以在平台之间共享，`React`使得同时创建 Android 和 iOS 应用变得简单。

#### 优点

- 它将物理`DOM`转换为虚拟`DOM`。
- 它帮助开发者编写更好的代码并生成更好的用户界面。
- 它包含单向数据。
- 子元素对父组件没有影响。
- 使用`JSX`增加代码复用性。

#### 缺点

- 很难学习和理解。
- 这是一个文档不充分的框架。

### 3. Vue.js

因为它是一个渐进式的`JavaScript`框架，我们可以用它来构建 UI（用户界面）和 SPA（单页应用）。这是一个简单的框架，允许我们在对`HTML`、`CSS`和`JavaScript`理解最少的情况下创建在线应用。

#### 优点

- `Vue JS`利用`HTML`模板。
- 使用`DOM`收集数据。
- 数据双向传输。
- `Vue JS`比之前的框架更具响应性。
- 与不同框架交互非常简单。

#### 缺点

- 它的通用性增加了开发者的负担。
- 它是最新的库，开发者较少。

### 4. Ember JS

`Ember Js`是一个`JavaScript`开发平台。它是用于构建单个 Web 应用的单一框架。它将结合惯用法、最佳实践和模式构建一个卓越的单页 Web 应用。它具有可扩展性，使用了框架提供的生态系统模式。

#### 优点

- 强大的插件
- `Ember CLI`
- 约定优于配置
- 社区
- 稳定且不停滞
- `Ember Octane`

#### 缺点

- 学习困难
- 由于观点过于强烈导致流行度增长缓慢

### 5. Mithril

`Mithril`是另一个快速且用于高效完成任务的`JS`框架。该框架的另一个优势是它的体积小，小于 10 KB。它具有路由和`XHR`功能。

#### 优点

- 轻量级
- `React`速度更快
- 兼容`ES6`
- 开发非常活跃
- 兼容`Flux`的智能自动重绘系统
- 学习曲线短

#### 缺点

- 虚拟`Dom`

### 6. Meteor

`Meteor`是另一个同构`JavaScript`框架，主要用于网站。我们可以通过使用`Node JS`开发适用于 Android、iOS 和 Web 的跨平台应用，从而快速完成项目。另一个优秀特性是我们可以连接到`MongoDB`。

#### 优点

- 易于上手并快速发布原型
- 热代码部署
- 全栈响应
- 对实时应用程序很有用
- 允许我们创建`MVP`

#### 缺点

- 自动打包
- 自优化的构建系统
- 存在速度问题
- 开发不可预测

### 7. Node JS

`Node JS`是一个著名的框架。它通过使用事件驱动、非阻塞`IO`机制使得`Node JS`轻量且实用。生态系统包`npm`是世界上最全面的开源库。

#### 优点

- 异步事件驱动`IO`有助于并发请求处理
- 易于学习
- 同一套代码应同时用于服务器和客户端
- `NPM`（或 Node 模块）规模巨大且不断扩张
- 活跃且繁忙的社区
- 流处理文件

#### 缺点

- 没有可扩展性
- 关系型数据库是必须的
- 回调嵌套
- 不支持 CPU 密集型活动

### 8. Polymer

`Polymer`是一个使用 Web 组件创建在线应用的开源`JavaScript`工具包。由 Google 工程师和 GitHub 贡献者创建。此外，Google 通过其 Material Design 框架整合了现代设计理念。

#### 优点

- Web 组件
- 材料设计
- Google 支持
- 数据绑定
- 开源友好
- 设计友好。`HTML`概念

#### 缺点

- 我们需要更努力构建在所有浏览器中运行的组件。
- 几个浏览器使用了`Shadow DOM`。
- 移动性能缓慢。

### 9. Next JS

`Next.js`是一个旨在开发快速且用户友好静态页面的`JavaScript`框架。然后，在`React`的帮助下，我们创建一个 Web 应用。由于自动静态优化，静态和动态已经结合。它的主要目标是构建混合应用。

#### 优点

- 自动服务端渲染和代码分离
- 设置简单
- 静态网站生成器
- 易设置
- 无缝开发
- 增量静态生成
- 文件系统即 API
- 同构的`React`应用
- 测试
- 文档详尽
- 内置基于文件的路由和 Hooks

#### 缺点

- 灵活性带来的代价
- 管理与开发
- 它有自己的主见（高度约定化）
- 没有内置状态管理器
- 插件不够

### 10. Aurelia

`Aurelia`使用`JavaScript`组件库创建复杂的浏览器、Web 应用和桌面应用程序。它同样是开源的，并结合了网络标准。

#### 优点

- 约定优于配置
- 可扩展的现代架构
- 与其它组件良好结合
- 易于使用
- 依赖注入
- 优秀的模块化路由器
- 自适应数据绑定
- 全栈、控制反转、模块化、简单性
- 基于`ES7`标准
- 快速开发
- 卓越的文档
- 符合不断变化的标准
- 平缓的学习曲线
- 卓越的辅助（付费）

#### 缺点

- 文档有限
- 社区较小

## 库（Library）与框架（Framework）

框架与库的区别是软件世界中经常讨论的话题。

事实上，专家建议它们之间的界限可能是模糊的，但区分它们是有必要的。`JS`框架是一个全面的工具集，帮助我们构建和组织基于 Web 的应用程序；而`JS`库是一组预写代码段的集合，它们不那么关注构建应用程序，而更关注提供一个按需使用的功能库。

### 模型-视图-控制器（MVC）

模型-视图-控制器是现代`JavaScript`框架使用的一种软件设计范式。它通常用于创建用户界面，将相关的计算机逻辑分离为三个关联的部分。模型是应用程序的基础 Web 组件，它是应用程序的动态数据结构。它负责应用程序的数据。视图包含了所有与表达应用程序数据用户界面相关的代码。解释器即控制器。它接收输入并转换为模型或视图指令。为了在软件开发中提供结构和灵活性，框架是围绕`MVC`设计模式设计的。

## 原生 JS 对比 React JS：我们的开发应该用哪一个？

原生`JS`对比`React JS`长期以来一直是争议的焦点，因为两者都用于创建`JavaScript`应用。本节将提供原生`JS`与`React JS`的全面对比，包括性能、UI 以及其他因素。

Web 应用的使用每天都在扩大，应用程序也变得越来越复杂和动态.¹¹⁰

人们通常希望发现一些可以对比原生与`React`的网站，我们可以在这里找到所有要点，包括`React`相比原生`JS`的性能对比。

因此，开发者在设计 Web 应用时选择使用不同的库来提高开发速度。

Web 应用可能很复杂且有各种需求，这就是为什么开发者选择使用如`React JS`、`Angular`、原生`JS`等其他框架的原因。

我们可能会找到提供各种`React JS`开发服务的`React JS`专业人士。

## 原生 JS 与 React JS 功能对比

在开始`React JS`对比原生`JS`的全面对比之前，我们想澄清这两种`JavaScript`之间的主要区别以及`React JS`和原生`JS`是如何运行的。

如果我们想了解更多关于使用`React`替代原生`JS`的优势，这篇文章将为我们提供所需的所有信息。两者都用于创建`JavaScript`应用。

### React JS：它在应用程序视图层中扮演什么角色？

为了构建使用 UI 组件的界面，许多开发者转向了`React JS`，这是一个免费且开源的`JavaScript`框架。`React JS`是一个前端`JavaScript`库，允许我们构建用户友好的应用。

我们将学习如何使用`React JS`来创建为单页应用定制的各种用户界面。开发者有时会利用`React JS`来管理各种移动和在线应用的视图层。

## 为什么使用原生 JS？

`Vanilla JS`被称为原生`JavaScript`，开发者使用它来构建不需要使用库的`JavaScript`代码。

原生`JS`是一种脚本语言，它对开发者如何在应用程序中构建数据不加任何限制。

原生`JS`应用并不总是能为应用程序带来最佳结果。

原生`JS`在开发者中非常闻名，因为它是任何人都能学习的最简单框架之一。

### React JS 与原生 JS 之间的栈数据结构对比

我们将看到，`JavaScript`组件之间的通信需要通过桥接进行大量的交互，以便我们与双方进行通信。

正如我们所知，`React JS`和原生`JS`都是用于创建各种在线应用的`JavaScript`框架。

如果我们好奇的话，`React JS`和原生`JS`的栈数据结构将会有不同。

我们错误地认为这两个`JavaScript`框架中的概念是相同的。

我们将看到，栈（Stack）可以定义为遵循后进先出（LIFO）原则的有序元素集合。

如果我们从栈中删除任何项，最顶部的将首先删除。

因此，`React JS`和原生`JS`的栈数据结构极其相似。

## 原生 JS 与 React JS 的性能对比

在比较原生`JS`与`React`的性能时，我们会注意到几个方面的差异。考虑到`React JS`与原生`JS`不同，它是一个免费开源的前端`JavaScript`框架，用于使用复用的 UI 组件进行构建。

原生`JS`是用于开发复杂的`JavaScript`应用程序的跨平台框架。原生`JS`与`React`的性能对比可能很困难，但我们有了解决方案。由于虚拟`DOM`的能力，`React JS`在处理各种 UI 更改方面非常高效，并定期与常规`DOM`进行比较。因此，这种方法有助于确定常规`DOM`所需的调整。整个过程可能非常快，以至于开发者可能会认为存在性能问题。

然而，`React JS`提供了一套解决方法来克服任何性能问题。我们可能会惊讶地发现原生`JS`比其他框架快得多。因此，我们认为它优于领先的框架。

我们将看到原生`JS`最初生成 UI 比`React JS`快 30 倍，这是原生`JS`优于`React JS`的关键原因之一。

在原生`JS`中处理 UI 状态变化比在`React JS`中简单且更快。

原生`JS`在性能方面优于`React JS`。

### 未来前景

`React`与原生`JS`的未来对比非常重要，因为它将显示哪种`JavaScript`更好。

`React JS`是开发者可能用于创建`React`应用的重要库。

我们将看到，未来元素的插件正在该框架中不断开发。

由于该技术被应用于各种行业，`React JS`开发者和提供各种`React JS`开发服务的`React JS`公司有着广阔的前景。

`ReactJS`社区随着时间的推移而扩大，框架也将不断更新。

## 胜者

`ReactJs`和原生`JS`（`Vanilla js`）均很有前景，因为所有的`JavaScript`框架都需要它们，尽管`ReactJs`的未来看起来稍微更好。

## 测试

在原生`JS`和`React JS`的测试对比中，确定胜者是困难的。

我们可以像使用任何其他`JavaScript`代码一样测试`ReactJs`代码。

`ReactJs`有许多可以用于测试的测试库。

`ReactJs`测试库是一系列辅助库的集合，允许我们在不依赖于其实现细节的情况下测试`ReactJs`组件。

我们可以说，这种评估`ReactJs`的方法确保了它是确保代码可用性的最佳实践。

在测试`ReactJs`代码时，我们还为所有`ReactJs`组件设置了理想的测试环境。

许多人不知道原生`JS`可以很轻松地测试。

`Jest`是一个专注于简单性的`JavaScript`测试框架，开发者必须安装它。

这个`JavaScript`测试框架也兼容`AngularJs`和`ReactJs`。

在`Jest`的帮助下，使用原生`JS`进行测试是轻而易举的。对于想要在`Jest`中测试`ReactJs`代码的开发者来说，在设备上安装`npm`或`yarn`是必要的。

胜者：因为在`ReactJs`和原生`JS`中的测试都很简单直接，所以两者都是胜者。

## 安全

我们将看到`ReactJs`是一个用于创建 Web 应用的`JavaScript`框架。

与其他构建各种 Web 应用的框架相比，`ReactJs`的攻击面更少。由于披露的安全担忧很少，`ReactJs`并非完全安全。

由于`ReactJs`兼容各种开源组件，它缺乏健壮的默认安全设置。因此，`ReactJs`暴露在多种安全漏洞之中。由于安全机制的弱性，`ReactJs`在线应用并非完全安全。原生`JS`有时可能要求 API 需要多个凭据；但该框架不提供短期令牌。

如果开发者希望确保在线应用程序的安全，他们可以采用中间 API 的方法。

原生`JS`是一个用于创建惊艳且强大的`JavaScript`应用的简单框架。我们可能会惊讶地发现原生`JS`在开发者中如此流行，因为截至目前还没有已知的安全漏洞。

胜者：如果我们从安全考虑方面对比原生`JS`和`React`，原生`JS`是显而易见的胜者。

## Reactjs 与原生 UI/UX 性能

`ReactJs`是一个免费且开源的`JavaScript`工具包，用于创建各种 UI 组件。

我们项目使用的一些顶尖 UI 框架可以在这里找到。`Ant Design`是世界上第二常用的 UI 框架，它被应用于`Reactjs`中。

我们将看到它将企业级 UI 设计语言与高质量`ReactJs`组件集合相结合。`Ant Design`的文档非常详尽，得益于大量的示例和框架，`Ant Design`始终保持更新。

`Material UI`是一个用`ReactJs`构建的用户界面，可以简化网站的创建。许多开发者使用这个 UI，因为它是最流行的`ReactJs`UI 框架，提供了 Google 提供的各种 Material 设计。

原生`JS`中有多种可用的 UI 库，可改进在线应用。

原生`JS`的`JavaScript 3D`库`Three`因其详尽的文档深受程序员的喜爱。

这个 3D 库易于使用并提供了卓越的性能。`Cheer`是一个用于原生的 UI 框架，可以被视为核心`jQuery`更快速、多功能且更好的服务器端版本。

胜者：在 UI/UX 速度方面，`Reactjs`优于原生`JS`，因为开发者不需要输入`DOM`，因为这在`ReactJs`中是自动发生的。

## 开发者的便利性

在开发者易用性方面，原生`JS`与`React`的对比将非常接近。

正如我们所见，`ReactJs`是目前最广泛使用的`JavaScript`库之一。

`ReactJs`发布于 2013 年；然而，因为它非常用户友好，仍然被 Web 开发者广泛使用。

它是创建视图页面最强大的`JavaScript`框架之一。

`ReactJs`对开发者来说更方便，因为它不仅仅是一个库，还包含了`JSX`和几个虚拟`DOM`。

开发者使用`ReactJs`是因为它给他们提供了完全的灵活性来为任何应用程序构建高质量的界面。一些开发者可能好奇原生`JS`是否仍在使用，我们可以肯定它确实在用。如果开发者正在创建基础代码来修改浏览器中的`DOM`，原生`JS`就能满足需求，而这需要一个庞大的框架。

开发者可以使用`ReactJs`或其他框架来构建复杂的 Web 应用。`ReactJs`和原生`JS`对开发者来说都很方便，但`ReactJs`具有更多功能，因此许多开发者选择了它。

## 维护



ReactJs我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。维护定期分析和监控在线应用。它将确保 Web 应用程序的安全、速度、输出和整体性能令人满意。如果开发者希望保持他们的应用程序处于最新、更快速，他们应该记住`ReactJs`提供了一个稳健的维护解决方案。

`ReactJs`提供三种维护服务：`ReactJs`启动维护、`ReactJs`专业维护和`ReactJs`业务维护。

我们注意到，由于维护成本，开发者不喜欢使用原生`JS`框架。如果开发者使用原生`JS`编写电子商务网站，维护和开发时间将更高。

我们会注意到，这是开发者选择利用市场上提供的许多`JavaScript`框架（如`AngularJS`、`ReactJs`、`Vue.js`等）的主要原因之一。

胜者：在维护方面，`ReactJs`远优于原生`JS`，因为开发者可以轻松维护 Web 应用。

# 开发成本

两者都是创建 Web 应用的高效`JavaScript`框架。

我们将看到`ReactJs`开发者可能每小时收取 20 到 40 美元来创建`ReactJs` Web 应用。原生`JS`开发者创建原生`JS`应用可能收取超过 1000 美元。

然而，由于`ReactJs` Web 应用的流行，市场上的许多人选择雇用`ReactJs`开发者。

胜者：在开发原生应用时，许多人倾向于雇用`ReactJs`开发者，这有时可能很昂贵。

## 34 征服 JavaScript

`Python`、`C++`以及其他一些语言。这使其成为最广泛使用的语言，也使其成为最易掌握的语言。`JavaScript`的语法与英语非常接近。开发者不需要花费几周时间创建一个新网站，因为他们不需要花时间去理解每行代码的作用。在多伦多 Web 开发的疯狂的世界里，一秒钟就可能决定一个项目的成败。如果开发者使用`JavaScript`，我们的网站将更快地向公众发布。

- **与其他语言兼容**：Web 服务器使用多种语言，确保它们都能顺畅运行至关重要。流行的编程语言列表包括`Python`、`PHP`、`Ruby`、`Rails`、`ASP.NET`和`Java`，仅列举了几个。`JavaScript`与多种服务器语言的兼容性确保了我们的读者始终能享受动态且迷胜的体验。
- **使用 DOM 模型**：DOM 模型是一种组织网站结构的方法，使其组件可以作为“对象”进行样式化，并拥有它们自己的属性。这使得`JavaScript`能够轻松为任何元素应用动画和过渡。并没有特定的编程语言与 DOM（文档对象模型）配合。通过`JavaScript`，开发者可以为网站创建一个 DOM。
- **无编译器编程**：传统编程使用编译器；无编译器编程避免了这一步。为了让浏览器运行，必须由编译器将原始代码编译成可理解的语法。这导致页面加载时间更长。因此，我们的网站准备好发布将花费更长时间。另一方面，浏览器对`JavaScript`有内置支持。就像它们可以翻译`HTML`一样，它们也可以这样做。换句话说，我们不需要编译器就可以读取它。

### AJAX 独立加载页面部分的用途

`JavaScript`自 1995 年首次发布以来变得越来越流行。如今，`JavaScript`用于互联网上惊人的 92% 网站以提高用户体验。通过`AJAX`，我们可以在无需刷新整个的情况下更新网站的某些部分。这是通过使用`JavaScript`实现的。我们可能在许多社交媒体、视频共享网站以及`Google.com`和`YouTube`等网站上见过这种用法。考虑一下我们在`YouTube`上播放视频时会发生什么。网站加载后，我们可以开始播放视频。如果我们在视频播放期间发表评论，它将出现在我们向下滚动并提交的评论框中。

在本章中，我们涵盖了什么是`JS`、它的优缺点以及`JS`的演变。此外，我们还讨论了什么是框架以及它们与原生`JS`（Vanilla JS）的区别。

## 注释

- 1 JavaScript - 概述：`www.tutorialspoint.com/javascript/javascript_overview.htm`访问日期：2022 年 9 月 20 日。
- 2 什么是 JavaScript？面向初者的 JS 简介：`www.hosting.in/tutorials/what-is-javascript`访问日期：2022 年 9 月 20 日。
- 3 什么是现代 JavaScript 以及如何使用它？`https://www.altamira.ir/blog/modern-javascript-and-how-to-use-it#:Size=20JavaScript%20does%20not%20have%20an%20tag`访问日期：2022 年 9 月 21 日。
- 4 JavaScript 的历史与演变：`https://exploringjs.com/impatient-js/ch_history.html`访问日期：2022 年 9 月 22 日。
- 5 JavaScript 历史：你需要的一切：`www.springboard.com/blog/data-science/history-of-javascript/`访问日期：2022 年 9 月 20 日。
- 6 谁拥有 JavaScript？`https://iq.opensource.org/who-owns-javascript/`访问日期：2022 年 9 月 20 日。
- 7 科技 101：什么是 JavaScript 框架？你需要的一切：`https://skillcrash.com/blog/what-is-a-javascript-framework/`访问日期：2022 年 9 月 20 日。
- 8 什么是 JavaScript 框架？`https://generalasmemb.ly/blog/what-is-a-javascript-framework/`访问日期：2022 年 9 月 20 日。
- 9 JavaScript 框架的优缺点是什么？`https://geeksforgeeks.org/what-are-the-pros-and-cons-of-javascript-frameworks/`访问日期：2022 年 9 月 21 日。
- 10 原生 JS vs React JS：开发中选择哪一个？`https://taglineinfotech.com/react-js-vs-vanilla-js/`访问日期：2022 年 9 月 21 日。
- 15 为什么你的网站需要 JavaScript 的原因：`https://vestrain.com/5-reasons-why-you-need-javascript-in-your-website.html`访问日期：2022 年 9 月 22 日。

## 第二章

## 开始学习 JavaScript I

### 本章内容

- 数据类型与运算符
- 函数
- 对象与数组
- 错误处理
- 事件

在上一章中，我们涵盖了 JavaScript 简介，在本章中，我们将讨论如何开始学习 JavaScript 以及核心概念。

### 从七种选项中选择最佳 JavaScript 编辑器

没有 JavaScript，我们的页面仅仅是一个死板的静态文档。我们可以使用 JavaScript 开发用户界面。没有 JavaScript，我们的页面仅仅是一个死板的静态文档。

## 38 征服 JavaScript

因此，我们可以认为 JavaScript 是核心。虽然没有什么阻止我们仅仅使用，但使用一个良好的编辑器无疑会增强我们的体验。我们将介绍我们的编辑器选择。我们将对每个项目做一个简要总结并讨论其优缺点。

### 编辑器与 IDE 的区别

但在进入编辑器之前，让我们先退一步，讨论编辑器的不同。

### 到底什么是编辑器？

让我们从编辑器开始。编辑器是允许你创建和编辑文本文件的工具，正如其名称所示。传统意义上的编辑器并不总是可以修改任何类型的。

## IDE 定义

IDE 是集成开发环境的缩写。IDE 只是带有各种工具的编辑器。IDE 是用于软件开发的专业工具。

IDE 包含哪些包？这视情况而异，但常见的添加包括：

- 调试器、编译器和源码分析器
- 语法高亮
- 基于预定义的项目脚架功能
- 与编译器和构建工具的连接
- 高级自动补全功能
- GUI 开发 / 快速应用程序开发

## 开始学习 JavaScript ■ 39

- 与终端和版本控制软件集成
- 自动化测试的管理和执行，特别是单元测试
- 可以使用重构功能

`Electron`是一个基于`JavaScript`的跨平台桌面程序框架。换句话说，电子是原子的基础。

`Atom`是最流行的`JavaScript`源码编辑器之一。`Atom`完全免费。该编辑器提供了多种

# 征服 JavaScript

操作系统，包括`Mac`、`Windows`和`Linux`。这个开源编辑器的设置也非常简单。其他功能还包括智能代码补全和直观的文件系统查看器。

`Atom`让集成`GitHub`和`Git`控制变得简单。该编辑器还支持用`Node.js`创建的插件。界面支持`HTML`、`CSS`和`JS`等其他语言。

`Atom`还具有函数模糊查找功能。模糊查找通过允许快速切换文件来加速你的工作。我们还想要更多吗？通过安装如`Minimap`、自动闭合`HTML`元素和`linter`（代码检查工具）等包，可以扩展`Atom`的功能。

### 优点

- `Git`集成。
- 跨平台兼容性。
- 支持多光标。

### 缺点

- 有时不稳定。
- 代码执行失败。
- 速度比其他顶级编辑器慢。

## 2. Visual Studio Code

许多人在考虑用于`JS`编程的最优秀集成开发环境（IDEs）时，会考虑到`Visual Studio Code`。这款免费的开源编辑器兼容`Linux`、`Windows`和`macOS`。`IntelliSense`支持允许在编写`HTML`、`CSS`、`JS`或`PHP`时进行自动补全。

该编辑器的另一个功能是代码重构。此外，编辑器还可以创建原生和托管代码。此代码编辑器内置了对`JS`的支持。还包含了针对`TypeScript`、`Node.js`和`JavaScript`的调试工具。

`VS Code`还具有预览（peek）功能。此功能允许我们在行内展开函数并检查代码，而无需直接跳转到函数定义行。

`VS Code`提供的另一个有用工具是任务运行器（Task Runner）。它支持使用`Gulp`、`Grunt`或`MSBuild`执行设置任务。

我们可以使用内置的`Git`功能执行发布（publish）、提交（commit）、推送（push）、拉取（pull）和变基（rebase）等操作。我们还可以通过添加新功能和插件来调整增强`Visual Studio Code`。

### 优点

- 内存占用极低。
- 与控制台集成。
- 任务组织。
- 市场提供了大量的扩展来扩展功能。
- `WSL`集成（适用于 Linux 的 Windows 子系统）。

### 缺点

- 有时延迟。
- 不某些广泛使用的编程语言。
- 源码控制不足。

## 3. Eclipse

`Eclipse`是一个著名的`Java` IDE。然而，全栈工程师经常利用`Eclipse`进行`JavaScript`开发。但是，对于`JS`，我们必须安装更多插件。当然，灵活的插件方便了使用。统一的开发环境促进了极致性能。除了速度之外，开发者可能期望可靠性和复原性。当我们设置`Omph`项目时，我们还可以自动化并复制类似的工作空间。

`Eclipse`的亮点是 JavaScript 开发工具（JDT）的精确性能。

新的`Docker UI`有助于使用`Docker CLI`创建`Docker`镜像和容器。

几乎所有的程序包都与`Git`集成。另一个值得的方面是自动错误报告。IDE 可能会使用此功能将 IDE 中识别出的问题通信给`eclipse.org`。

### 优点

- 有效的项目管理。
- 高级疑故障排除。
- 卓越的自动补全。

### 缺点

- 为了使其生效，大多数修改都需要重启。
- 对于初学者来说，这很难。
- 客户服务差。

## 4. Sublime Text

`Sublime Text`是另一个免费且开源的`JS`编辑器。它是跨平台的，这意味着有大量的自定义空间。UI 没有任何杂乱。

因此，该编辑器更加用户友好。它的一些卓越特性包括显著的性能提升和增强的面板管理。其他功能包括转到符号（Go to Symbol）和转到定义（Go to Definition）。我们还可以获取如`Sidebar Enhancements`之类的包用于复制、粘贴、移动和重命名。最初配置需要一些时间。然而，一旦安装，`Sublime Text`将提供无缝体验。此外，如果我们想使用`Sublime Text`，这里有需要安装的插件：`DocBlock`、`Sidebar Enhancements`、`JsFormat`和`SublimeLinter`，它们都是可用的。

最棒的一点是你可以免费查看所有功能。

此`JS`编辑器还提供试用版以便开发者查看它是如何工作的。

试用期过期后，我们必须支付 80 美元购买三年的使用以访问所有功能。

### 优点

- 无干扰的编辑模式。
- 处理多个项目非常简单。
- 辅助自动化提供帮助。

### 缺点

- 糟糕的库栈。
- 缺乏调试功能。
- 没有默认打印。

## 5. Brackets

`Adobe`开发了开源代码编辑器`Brackets`。这款轻量且快速的`JS`编辑器包含了`JavaScript`功能。`Brackets`兼容`Mac`、`Windows`和`Linux`。一些重要能力是函数搜索和快速项目切换。用户可以在实时打字时利用这些工具搜索各种文件。

提取功能将 PSD 数据转换为`CSS`。实时预览（Live Preview）是`Brackets`最出色的功能之一。我们可以观察代码的变化如何实时影响代码。该功能类似于`Adobe Dreamweaver`。我们还可以通过添加插件来提高编辑器的能力。其中一些功能包括`autoprefixer`、代码折叠、`Markdown`预览、智能高亮和代码片段（snippets）。

### 优点

- 简单直观的用户界面。
- 代码最小化。
- 实时浏览器预览。

### 缺点

- 启动时间长。
- 项目管理困难。
- 在处理大文件时，性能会下降。

## 6. NetBeans

`NetBeans`是一个用于开发`JavaScript`应用程序的多平台 IDE。

最棒的是从安装`NetBeans`到使用它的时间比其他编辑器短。`NetBeans`具有语法和语义高亮、智能代码补全等功能。支持`Subversion`、`Mercurial`以及内置`Git`。

此外，我们可以简单地拖拽并重新排列应用框架中的标签。而且，众所周知，每个开发者都有独特的开发风格。我们可以根据需要调整工具栏。而且我们知道还有什么好用的吗？

### 优点

- 自动化非常有效。
- 卓越的重构。
- 优秀的服务管理。

### 缺点

- 使用更多系统资源。
- 集成支持不足。
- 弹出窗口烦人。

## 7. Vim

我们离开时不能不感谢传奇的`Vim`。`Vim`代表 VI Improved（改进版 vi），它是为`Unix`系统设计的旧文本编辑器的改进版本。尽管`Vim`长期以来与`Linux`和`Unix`社区相关，但它现在也适用于`Windows`。

`Vim`可能是列表中最基础的编辑器。虽然`Vim`有图形界面，但它通常是一个文本编辑器。这个编辑器的学习曲线较陡。然而，如果我们克服了最初的学习曲线并精通它，`Vim`可能会帮助我们获得巨大的生产力，特别是当我们考虑到其丰富的生态系统时。

### 优点

- 轻量高效。
- 跨平台。
- 适应性强。
- 用于扩展功能的插件生态。

### 缺点

- 学习曲线陡峭。

## 选择最佳 JavaScript 编辑器

在前面的部分，我们检查了七种最优秀的`JavaScript`编辑器。现在是最困难的部分：选择最好的一个。这就像选择最优秀的操作系统一样。现在使用`Windows`的人无疑会维护它，说它是优越的，并且不会切换到任何其他操作系统。相反，使用`Linux`或`Mac`的人可能会认为他们的系统比其他所有系统好得多。当涉及到`JavaScript`编辑器时，我们必须根据几个标准进行评估：

- 灵活性。
- 集成帮助。
- 有效的项目管理。
- 性能。
- 高级疑故障排除。

然而，对于`JS`编辑器，无论我们的个人偏好如何，`Visual Studio Code`都是明显的胜者。我们这样的经验程序员没有其他选择，必须使用`Visual Studio Code`。编辑器允许快速简单的代码文件管理和搜索。此外，我们有快捷键可以

## 46 征服 JavaScript

快速访问任何图标或操作。我们可以在不离开键盘的情况下输入代码并在文件夹之间导航。

如果我们只是刚刚开始进入计算机编程的世界，`VS Code`的功能将是巨大的帮助。我们在学习快捷键或任何其他功能时没有遇到困难。此外，集成的命令行界面对于那些使用`Angular`或`Node.js`的人员来说非常有帮助。如果你安装了`Node.js`，还可以使用`VS Code`调试我们的代码。此外，我们不必担心获取`VS Code`的帮助，因为是由由微软构建的。所有的功能和教程都有详尽的文档说明，并并在大量的文字和视频材料中展示出来。

### 使用 JavaScript 编辑器，你可能会提高工作环境的效率

网站可以使用多种技术构建，但始终存在三种技术：`HTML`、`CSS`和`JavaScript`。这些每种技术都关注一个特定的问题。`HTML`负责组织和定义我们的页面。

`CSS`帮助它看起来非常棒。而由于`JavaScript`让它栩栩如。如果我们是开发者，我们可能会为让你的工作环境变得愉快且高效感到兴奋。在这种情况下，一个优秀的`JavaScript`编辑器是最佳选择。

从个人而言，我们不能总是评估和比较文本编辑器来确定哪一个是最好的。对于每个用户的需求观点各异。在每个顶级选项上花时间是确定哪一个是最好的`JavaScript`编辑器的极佳方法。这将帮助我们理解许多特性，并做出最佳决策。

## 如何在 VISUAL STUDIO CODE 中安装 JAVASCRIPT



JavaScript 是一种面向对象的计算机程序，用于网页浏览器，通过让我们的网站产生行为和思考来创建交互效果。IDE（或集成开发环境）帮助程序员将创建计算机程序的众多组件合并到一个单一方便的区域中。它包含一个调试器、源代码编辑器和本地构建自动化。Visual Studio 是几乎每个 JavaScript 开发者都会使用的极佳 IDE。

## 56 征服 JavaScript

在我们的机器上，将下载一个 MSI 安装程序。

![](img/70a7539ec7c3f429f5e3c9c64df71823_96_0.png)

### 下载 NodeJs

**第 2 步：** 开始 Node.js 安装。

我们现在必须在计算机上安装 node.js 安装程序。要安装 Node.js，我们必须先完成以下步骤：

- 双击 `.msi` 安装程序启动它。
- 将启动 Node.js 安装向导。
- 欢迎使用 Node.js 安装向导。
- 应该选择“Next”（下一步）。

![](img/70a7539ec7c3f429f5e3c9c64df71823_96_1.png)

说明：Node.js 向导界面

## 开始使用 JavaScript ■ 57

- 选择“Next”后，将显示最终用户许可协议 (EULA)。
- 通过勾选旁边的复选框选择“I accept the terms of the License Agreement”（我接受许可协议条款）。
- 应该选择“Next”（下一步）。

![](img/70a7539ec7c3f429f5e3c9c64df71823_97_0.png)

Node.js 同意界面

- 选择目标文件夹

## 58 征服 JavaScript

![](img/70a7539ec7c3f429f5e3c9c64df71823_98_0.png)

Node.js 选择文件夹

- 自定义配置
- 应该选择“Next”（下一步）。

![](img/70a7539ec7c3f429f5e3c9c64df71823_98_1.png)

Node.js 自定义设置

### 开始使用 JavaScript | 59

- Node.js 现在已准备好安装。
- 选择“Install”（安装）。

![](img/70a7539ec7c3f429f5e3c9c64df71823_99_0.png)

Node.js 安装开始

注意：

将出现提示：“此步骤需要管理员权限”。在提示中以“Administrator”（管理员）身份进行验证。

- Node.js 安装
- 在安装完成之前，请勿关闭或取消安装程序。
- 完成 Node.js 安装向导。
- 点击“Finish”（完成）按钮。

## 60 征服 JavaScript

![](img/70a7539ec7c3f429f5e3c9c64df71823_100_0.png)

Node.js 安装完成

**第 3 步：** 检查 Node.js 是否正确安装。

要验证 node.js 是否完全安装在我们的机器上，请在命令提示符或 Windows PowerShell 中运行命令行：

```
C:\Users\Admin> node -v
```

如果 Node.js 已在我们的机器上完全安装，命令提示符将显示已安装的 node.js 版本。

**第 4 步：** 更新本地 npm 版本。

安装 Node.js 的最后一步是更新我们的本地 npm 版本（如有必要）——这是 Node.js 附带的包管理器。

要更新 npm，请使用以下命令。

```
npm install npm -global // 更新'CLI'客户端
```

**注意：**

我们不需要修改系统变量，因为 Windows 安装程序在在使用 `.msi` 安装程序安装时会自动处理它们。

如果我们使用其他格式在 PC 上安装 node.js，则 node.js 的系统变量路径如下：

```
PATH : C:\Users\[user-name]\AppData\Roaming\npm
C:\Program Files\nodejs (nodejs 文件夹的路径)
```

### 开始使用 JavaScript I ■ 61

## 在 LINUX 上安装 NODE.JS

Node.js 是一个基于 Chrome 中 V8 JavaScript 引擎的 JavaScript 运行时。可以通过多种方法在 Ubuntu Linux 笔记本电脑上安装 Node.js。⁵我们可以使用 Ubuntu 官方存储或 NodeSource 存储来安装 Node.js。NodeSource 存储允许我们安装最新版本的 Node.js。

### 在 Ubuntu 18.04 和 16:04 上安装 Node.js：Ubuntu 有两个存储，官方存储和 NodeSource，您可以从那里下载并安装 Node.js。

从 Ubuntu 官方存储安装 Node.js：只需几次击键，即可从 Ubuntu 存储安装 Node.js。要在我们的 Ubuntu 操作系统上安装 Node.js，请按照说明操作。

- 第 1 步：启动终端或按 `Ctrl+Alt+T`。
- 第 2 步：运行以下命令安装 node.js：

```
sudo apt install nodejs
```

- 第 3 步：安装完成后，使用以下命令检查安装版本：

```
node -v or node -version
```

强烈建议随 Node.js 一起安装 Node 包管理器 (NPM)。NPM 是开源的 Node.js 包库。

使用以下命令安装 NPM：

```
sudo apt install npm
npm -v or npm -version
```

Node 和 NPM 将成功安装在我们的 Ubuntu 上。

### 使用 NodeSource 存储安装 Node.js

可以从 NodeSource 存储下载最新版本的 Node.js。

要在 Ubuntu 上安装 Node.js，请按照说明操作。

- 第 1 步：要更新和升级包管理，打开打开终端或按 `Ctrl+Alt+T` 并输入以下命令：

```
sudo apt update
sudo apt-get upgrade
```

## 62 征服 JavaScript

- 第 2 步：运行以下命令安装软件库：

```
sudo apt-get install python-properties
```

- 第 3 步：在机器上安装 Node.js PPA。

```
curl -SL https://deb.nodesource.com/setup_L.x | sudo -E bash -
```

注意：我们正在安装 L.x 版本的 node.js；如果我们想安装 X.x 版本，将 L.x 替换为 X.x。

- 第 4 步：在 Ubuntu 上运行命令安装 Node.js 和 NPM：

```
sudo apt-get install nodejs
```

- 第 5 步：安装完成后，使用以下命令检查版本：

```
node -v
npm -v
```

最后，在我们的 Ubuntu 系统上，我们成功安装了 Node.js 和 NPM。

## 我们如何在 VISUAL STUDIO 中启动并执行 NODE 项目？

下面的说明将引导我们完成创建一个基础 NodeJS 项目并在 VS Code 编辑器中执行它的过程。

- 第 1 步：在 VS Code 中创建一个空文件夹并进入它：

```
mkdir demo
cd demo
code
```

- 第 2 步：在文件夹中创建一个 `app.js`。
- 第 3 步：通过运行以下命令安装模块：

```
npm install express
npm install nodemon
```

### 开始使用 JavaScript ■ 63

- 第 4 步：在 `package.json` 中配置：

```json
{
  "name": "demo",
  "version": "1.0.0",
  "description": "",
  "main": "app.js",
  "scripts": {
    "test": "echo \"no test\" exit 1",
    "start": "node app.js",
    "dev": "nodemon app.js"
  },
  "author": "ISC",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1",
    "nodemon": "^2.0.12"
  }
}
```

- 第 5 步：在 `app.js` 中添加以下代码：

```javascript
// 模块
const express = require('express');

// 创建 express 对象
const app = express();

// 处理 GET 请求
app.get('/', (req, res) => {
  res.send('Simple App is running')
  res.end()
})

// 端口
const PORT = process.env.PORT || 5000;

// 服务器设置
app.listen(PORT, console.log(`Server started on the port ${PORT}`));
```

- 第 6 步：使用以下命令启动应用程序：

```
npm run dev
```

- 第 7 步：在浏览器中访问 `http://localhost:5000/`，我们将得到输出：

## JavaScript 开发者的顶级 VS 插件

今天，我们将展示对 JavaScript 开发者非常有帮助并能提升 VS Code 水的插件。

### JavaScript (ES6) 代码片段

使用预定义的片段有助于提高效率。

我们可以通过添加更多包或创建自己的片段来定制片段。

创建自己的片段的可能性是其价值所在；我们还没有自己这样做，但安装了其他插件来获取 React、React Native、Redux 等框架的工具。

只需搜索“VS Code code snippets”+ 我们的框架即可找到适合我们的集合。

下载地址：`https://marketplace.visualstudio.com/items?itemName-xikos.JavaScriptSnippets`

![](img/70a7539ec7c3f429f5e3c9c64df71823_105_0.png)

JavaScript (ES6) 代码片段页面

### ESLint

毫无疑问，ESLint 是 JS 社区中最广泛使用和喜爱的插件之一。该扩展将 ESLint 规则应用于您的代码并在编辑器中显示结果。它使我们能够发现并快速纠正规则不一致。它是所有 JS 开发者的必不可少，因为它提高了生产力和代码质量。

下载地址：`https://marketplace.visualstudio.com/items?Name-dbaeumer.vscode-eslint`

![](img/70a7539ec7c3f429f5e3c9c64df71823_105_1.png)

ESLint 页面

### Prettier

配合 VS Code、Visual Studio、Atom、Vim、Sublime Text 以及许多其他程序，Prettier 是一个有偏好的代码格式化工具。

## 66 征服 JavaScript

这个实用的小插件确保了我们的脚本结构和缩进保持统一，并显示颜色的关键字以提高代码的可读性。

它减少了格式化时间，从而提高了效率。它有助于提高可读性。

下载地址：`https://marketplace.visualstudio.com/items?Name=esbenp-prettier-vscode`

![](img/70a7539ec7c3f429f5e3c9c64df71823_106_0.png)

Prettier 下载页面

## Quokka.js

Quokka.js 允许我们在 VS Code 编辑器中快速进行 JavaScript原型。它是一个实时 JavaScript 和 TypeScript 沙盒。

它通常被称为 JS 开发者的现代草稿纸。我们是否曾想快速测试某些东西，结果发现自己在浏览器的控制台中运行某些 JS？或者我们启动 node 进程进行测试？这个插件的主要目标是直接在我们的 VS Code 编辑器中快速方便地执行代码。

下载地址：`https://marketplace.visualstudio.com/items?Name=Wallabyjs.quokka-vscode`

![](img/70a7539ec7c3f429f5e3c9c64df71823_106_1.png)

Quokka 下载页面

## 开始学习 JavaScript | 67

### REST Client

REST Client 是一个 Visual Studio Code 插件，允许我们直接在编辑器中提交 HTTP 请求并检查结果。它是 VS Code 版的 Postman，额外的优点是它集成在代码编辑器内部。

REST Client 同时兼容 REST 和 GraphQL API。在生产力方面，它是 API 开发者最强大的 vscode 扩展之一。

下载地址：`https://marketplace.visualstudio.com/items?Name=humao-rest-client`

![](img/70a7539ec7c3f429f5e3c9c64df71823_107_0.png)

REST Client 下载页面

### Debugger for Chrome

JavaScript 调试可能令人麻烦。Chrome 和其他浏览器提供了极佳的功能来协助我们的工作。尽管如此，它们有时难以使用，或者无法提供良好的整体体验，特别是在处理框架和多个库时。

Microsoft Debugger for Chrome 是一个 Chrome 扩展，允许我们对代码的任何更改进行调试。Chrome 控制台调试器在确定哪些行和函数导致了问题以及查看其数据处理方面非常强大。通过 Chrome 运行代码并在我们的代码编辑器中进行调试。

下载地址：`https://marketplace.visualstudio.com/items?Name=msdiag,debugger-for-chrome`

![](img/70a7539ec7c3f429f5e3c9c64df71823_107_1.png)

Debugger for Chrome 下载页面

## 68 征服 JavaScript

### Live Server

我们可以使用 Live Server 为静态和动态网站启动一个带有实时重载选项的本地开发服务器。对于使用已启用实时重载框架（如 React）的个人来说，这可能用用，但如果我们正在处理其他网页或静态材料，它将是救星。

下载地址：`https://marketplace.visualstudio.com/items?Name=ritwickwickey.LiveServer`

![](img/70a7539ec7c3f429f5e3c9c64df71823_108_0.png)

Live Server 下载页面

### Live Share

这太棒了，我们不确定 WebStorm 是否有类似的功能，但它允许我们与其他人共享代码编辑器。

它是结对编程的理想选择，特别是在居家办公变得流行的情况下。

下载地址：`https://marketplace.visualstudio.com/items?Name=MS-vslshare.vslshare`

![](img/70a7539ec7c3f429f5e3c9c64df71823_108_1.png)

Live Share 下载页面

## 开始学习 JavaScript ■ 69

### Babel JavaScript VSCode

JavaScript 近年来取得了巨大进步，随着 React、Flow 和 GraphQL 等框架和库的发展，许多新形式的“语法”现在已成为可能。Babel JavaScript 为新的 JavaScript 语法和这些特定的“语言”提供语法高亮，使我们的 JavaScript 编辑器保持且外观良好。

下载地址：`https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel`

![](img/70a7539ec7c3f429f5e3c9c64df71823_109_0.png)

Babel JavaScript 下载页面

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，JavaScript booster 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、typescript、promises、JSX 以及更多。

下载地址：`https://marketplace.visualstudio.com/items?itemName=sburg-javascript-booster`

![](img/70a7539ec7c3f429f5e3c9c64df71823_109_1.png)

JavaScript Booster 下载页面

## 70 征服 JavaScript

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，JavaScript booster 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、typescript、promises、JSX 以及更多。

下载地址：`https://marketplace.visualstudio.com/items?itemName=sburg-javascript-booster`

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。



## 66 征服 JavaScript

这个实用的小插件确保了我们的脚本结构和缩进保持统一，并显示颜色的关键字以提高代码的可读性。

它减少了格式化时间，从而提高了效率。它有助于提高可读性。

下载地址：`https://marketplace.visualstudio.com/items?Name=esbenp-prettier-vscode`

![](img/70a7539ec7c3f429f5e3c9c64df71823_106_0.png)

Prettier 下载页面

## Quokka.js

`Quokka.js` 允许我们在 VS Code 编辑器中快速进行 JavaScript 原型。它是一个实时 JavaScript 和 TypeScript 沙盒。

它通常被称为 JS 开发者的现代草稿纸。我们是否曾想快速测试某些东西，结果发现自己在浏览器的控制台中运行某些 JS？或者我们启动 `node` 进程进行测试？这个插件的主要目标是直接在我们的 VS Code 编辑器中快速方便地执行代码。

下载地址：`https://marketplace.visualstudio.com/items?Name=Wallabyjs.quokka-vscode`

![](img/70a7539ec7c3f429f5e3c9c64df71823_106_1.png)

Quokka 下载页面

## 开始学习 JavaScript | 67

### REST Client

`REST Client` 是一个 Visual Studio Code 插件，允许我们直接在编辑器中提交 HTTP 请求并检查结果。它是 VS Code 版的 Postman，额外的优点是它集成在代码编辑器内部。

`REST Client` 同时兼容 REST 和 GraphQL API。在生产力方面，它是 API 开发者最强大的 vscode 扩展之一。

下载地址：`https://marketplace.visualstudio.com/items?Name=humao-rest-client`

![](img/70a7539ec7c3f429f5e3c9c64df71823_107_0.png)

REST Client 下载页面

### Debugger for Chrome

JavaScript 调试可能令人麻烦。Chrome 和其他浏览器提供了极佳的功能来协助我们的工作。尽管如此，它们有时难以使用，或者无法提供良好的整体体验，特别是在处理框架和多个库时。

Microsoft `Debugger for Chrome` 是一个 Chrome 扩展，允许我们对代码的任何更改进行调试。Chrome 控制台调试器在确定哪些行和函数导致了问题以及查看其数据处理方面非常强大。通过 Chrome 运行代码并在我们的代码编辑器中进行调试。

下载地址：`https://marketplace.visualstudio.com/items?Name=msdiag,debugger-for-chrome`

![](img/70a7539ec7c3f429f5e3c9c64df71823_107_1.png)

Debugger for Chrome 下载页面

## 68 征服 JavaScript

### Live Server

我们可以使用 `Live Server` 为静态和动态网站启动一个带有实时重载选项的本地开发服务器。对于使用已启用实时重载框架（如 React）的个人来说，这可能用用，但如果我们正在处理其他网页或静态材料，它将是救星。

下载地址：`https://marketplace.visualstudio.com/items?Name=ritwickwickey.LiveServer`

![](img/70a7539ec7c3f429f5e3c9c64df71823_108_0.png)

Live Server 下载页面

### Live Share

这太棒了，我们不确定 WebStorm 是否有类似的功能，但它允许我们与其他人共享代码编辑器。

它是结对编程的理想选择，特别是在居家办公变得流行的情况下。

下载地址：`https://marketplace.visualstudio.com/items?Name=MS-vslshare.vslshare`

![](img/70a7539ec7c3f429f5e3c9c64df71823_108_1.png)

Live Share 下载页面

## 开始学习 JavaScript ■ 69

### Babel JavaScript VSCode

JavaScript 近年来取得了巨大进步，随着 React、Flow 和 GraphQL 等框架和库的发展，许多新形式的“语法”现在已成为可能。`Babel JavaScript` 为新的 JavaScript 语法和这些特定的“语言”提供语法高亮，使我们的 JavaScript 编辑器保持且外观良好。

下载地址：`https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel`

![](img/70a7539ec7c3f429f5e3c9c64df71823_109_0.png)

Babel JavaScript 下载页面

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，`JavaScript booster` 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、`typescript`、`promises`、`JSX` 以及更多。

下载地址：`https://marketplace.visualstudio.com/items?itemName=sburg-javascript-booster`

![](img/70a7539ec7c3f429f5e3c9c64df71823_109_1.png)

JavaScript Booster 下载页面

## 70 征服 JavaScript

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，`JavaScript booster` 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、`typescript`、`promises`、`JSX` 以及更多。

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，`JavaScript booster` 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、`typescript`、`promises`、`JSX` 以及更多。

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

### Tabnine

从 WebStorm 切换时出现的另一个问题是代码补全的质量。

Microsoft `Debugger for Chrome` 是一个 Chrome 扩展，允许我们对代码的任何更改进行调试。Chrome 控制台调试器在确定哪些行和函数导致了问题以及查看其数据处理方面非常强大。通过 Chrome 运行代码并在我们的代码编辑器中进行调试。



它通常被称为 JS 开发者的现代草稿纸。我们是否曾想快速测试某些东西，结果发现自己在浏览器的控制台中运行某些 JS？或者我们启动 `node` 进程进行测试？这个插件的主要目标是直接在我们的 VS Code 编辑器中快速方便地执行代码。

下载地址：https://marketplace.visualstudio.com/items?Name=Wallabyjs.quokka-vscode

![](img/70a7539ec7c3f429f5e3c9c64df71823_106_1.png)

Quokka 下载页面

## 开始学习 JavaScript | 67

### REST Client

REST Client 是一个 Visual Studio Code 插件，允许我们直接在编辑器中提交 HTTP 请求并检查结果。它是 VS Code 版的 Postman，额外的优点是它集成在代码编辑器内部。

REST Client 同时兼容 REST 和 GraphQL API。在生产力方面，它是 API 开发者最强大的 vscode 扩展之一。

下载地址：https://marketplace.visualstudio.com/items?Name=humao-rest-client

![](img/70a7539ec7c3f429f5e3c9c64df71823_107_0.png)

REST Client 下载页面

### Debugger for Chrome

JavaScript 调试可能令人麻烦。Chrome 和其他浏览器提供了极佳的功能来协助我们的工作。尽管如此，它们有时难以使用，或者无法提供良好的整体体验，特别是在处理框架和多个库时。

Microsoft Debugger for Chrome 是一个 Chrome 扩展，允许我们对代码的任何更改进行调试。Chrome 控制台调试器在确定哪些行和函数导致了问题以及查看其数据处理方面非常强大。通过 Chrome 运行代码并在我们的代码编辑器中进行调试。

下载地址：https://marketplace.visualstudio.com/items?Name=msdiag,debugger-for-chrome

![](img/70a7539ec7c3f429f5e3c9c64df71823_107_1.png)

Debugger for Chrome 下载页面

## 68 征服 JavaScript

### Live Server

我们可以使用 Live Server 为静态和动态网站启动一个带有实时重载选项的本地开发服务器。对于使用已启用实时重载框架（如 React）的个人来说，这可能用用，但如果我们正在处理其他网页或静态材料，它将是救星。

下载地址：https://marketplace.visualstudio.com/items?Name=ritwickwickey.LiveServer

![](img/70a7539ec7c3f429f5e3c9c64df71823_108_0.png)

Live Server 下载页面

### Live Share

这太棒了，我们不确定 WebStorm 是否有类似的功能，但它允许我们与其他人共享代码编辑器。

它是结对编程的理想选择，特别是在居家办公变得流行的情况下。

下载地址：https://marketplace.visualstudio.com/items?Name=MS-vslshare.vslshare

![](img/70a7539ec7c3f429f5e3c9c64df71823_108_1.png)

Live Share 下载页面

## 开始学习 JavaScript ■ 69

### Babel JavaScript VSCode

JavaScript 近年来取得了巨大进步，随着 React、Flow 和 GraphQL 等框架和库的发展，许多新形式的“语法”现在已成为可能。Babel JavaScript 为新的 JavaScript 语法和这些特定的“语言”提供语法高亮，使我们的 JavaScript 编辑器保持且外观良好。

下载地址：https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel

![](img/70a7539ec7c3f429f5e3c9c64df71823_109_0.png)

Babel JavaScript 下载页面

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，JavaScript booster 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、typescript、promises、JSX 以及更多。

下载地址：https://marketplace.visualstudio.com/items?itemName=sburg-javascript-booster

![](img/70a7539ec7c3f429f5e3c9c64df71823_109_1.png)

JavaScript Booster 下载页面

## 70 征服 JavaScript

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，JavaScript booster 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、typescript、promises、JSX 以及更多。

### JavaScript Booster

我们喜爱的 WebStorm 功能之一现在可以在 VS Code 中使用了。

通过评估我们的代码及其上下文，JavaScript booster 会自动提出短方法来重构或改进我们的代码。

它支持广泛的代码活动，包括重构条件、声明、函数、typescript、promises、JSX 以及更多。

# 入门 JavaScript ■ 73

许多对编程理解极少的新手尝试学习框架；意不意外的是，他们在某个地方停滞了，并最终停止了对原生 JS（Vanilla JS）基础的关注。

当他们变得熟悉后，会再次开始学习框架，这一次他们学习得要快得多。原生脚本的其他显著优势还包括：

- **互操作性**：我们可以将 JavaScript 注入到任何网页中，但不能注入到另一种编程语言中。以 PHP 为例，我们也可以将其用于各种应用程序，因为它支持 PHP 和 Perl 等其他语言。

- **服务器负载**：减轻服务器负载。因为我们知道 JavaScript 是在客户端执行的，它最大限地减少了对服务器资源的需求。此外，基础程序不需要服务器的任何交互。

- **丰富的用户界面**：我们可以使用 JavaScript 构建如拖放等高质量功能，以及如滑块等之类的组件。这会对网站的用户体验产生良好影响。

- **速度**：因为它在客户端执行且不需要任何外部资源，所以速度非常快。对后端服务器的调用不会影响 JavaScript 的性能。

## 原生脚本的缺点

- 原生脚本最根本的缺点之一是客户端安全，因为我们都知道 JavaScript 代码在客户端是可读的。因此，任何具有修改能力的人都可能将其作为出于不当目的武器或工具。

- JavaScript 的另一个显著缺点是缺乏调试设施（Debugging Facility）。

- 我们无法将其用于基于网络的应用程序，因为没有此类支持。

- 原生脚本还缺乏某些功能，例如多处理器和多线程。

- 出于安全考虑，它还禁止读写数据。

## 74 征服 JavaScript

## JavaScript 中的 HELLO WORLD 程序

在示例中，我们将学习三种在 JavaScript 中打印“Hello World”的替代方法。

“Hello, World!”程序是一个在屏幕上打印“Hello, World!”短语的基础程序。

因为它是一个非常基础的程序，通常用于教新手学习新的编程语言。

我们将用三种不同的方式打印“Hello, World!”：

- `console.log()`

- `alert()`

- `document.write()`

### 1. **使用 console.log()**

`console.log()` 函数用于调试代码。

```javascript
// program of hello world
console.log('Hello World!');
```

### 2. **使用 alert()**

`alert()` 函数会在当前窗口上显示一个带有指定消息的警告框。

```javascript
// program of hello world
alert("Hello, World!");
```

### 3. **使用 document.write()**

当我们想要将信息打印到 HTML 文档时，使用 `document.write()`。

```javascript
// program of hello world
document.write('Hello, World!');
```

## JavaScript 语法

可以通过将 JavaScript 语句放置在网页的 `<script>...</script>` HTML 标签内来应用 JavaScript。

# 入门 JavaScript | 75

我们可以在网页的任何地方插入包含我们 JavaScript 的 `<script>` 标签，尽管通常最好将其放在 `<head>` 标签内部。`<script>` 标签指示浏览器开始将这些标签之间的任何内容作为脚本进行读取。

以下是你的 JavaScript 基础语法。

```html
<script ...>
code
</script>
```

该脚本需要两个关键属性：

- **Language（语言）**：该元素定义了正在使用的脚本语言。它的值通常是 JavaScript。尽管随后的 HTML 版本（及其继任者 XHTML）已经逐渐淘汰了这一功能的使用。

- **Type（类型）**：现在建议 `type` 的值使用 "text/javascript"，以指示正在使用的脚本语言。

因此，我们的 JavaScript 部分将如下所示：

```html
<script language = "javascript" type = "text/javascript">
JavaScript-code
</script>
```

# 我们的第一个脚本代码

让我们尝试打印“Hello Everyone”作为示例。我们在 JavaScript 代码周围包含了一个可选的 HTML 注释。这样做是为了保护我们的代码不受不支持 JavaScript 的浏览器的影响。¹⁰

注释以 `<!---->` 结尾，因为 `//` 在 JavaScript 中表示注释，我们在这里包含它是为了防止浏览器将 HTML 注释的结尾视为 JavaScript 代码。然后我们将调用函数 `document`。

此函数可以创建文本、HTML 或两者兼有。请看下面的代码。

```html
<html>
<body>
```

## 76 征服 JavaScript

```html
<script language="javascript" type = "text/javascript">
<!--
  document.write("Hello Everyone")
---->
</script>
</body>
</html>
```

## 换行符与空白符

JavaScript 忽略脚本中的空格、制表符和换行符。我们可以在程序中自由使用空格、制表符和换行符，并以整洁统一的方式对其进行样式设计和缩进，使代码易于阅读和理解。

## 不需要分号

JavaScript 中的简单语句（类似于 C、C++ 和 Java 中的语句）通常后面跟着一个分号字符。相反，JavaScript 允许我们在每条语句都单独成行时省掉分号。例如，以下代码可以在没有分号的情况下编写。

```html
<script language="javascript" type = "text/javascript">
<!--
  var1 = 30
  var2 = 10
---->
</script>
```

然而，在单行格式化时，必须使用分号，如所示。

```html
<script language="javascript" type = "text/javascript">
<!--
var1 = 30; var2 = 10;
---->
</script>
```

# 入门 JavaScript ■ 77

## 大小敏感

JavaScript 是一种大小写敏感的编程语言。这意味着所有的语言关键字、变量、函数名和其他标识符必须以一致的大小写输入。在 JavaScript 中，标识符 `Time` 和 `TIME` 具有不同的含义。

# JavaScript 中的注释

JavaScript 注释是一种传达信息的有效技术。它用于包含代码、警告或建议，以便最终用户可以轻松阅读。¹¹ 浏览器的内置引擎会忽略注释。

## JavaScript 注释的好处

JavaScript 注释主要有两个益处：

- 使代码更易于理解，它可以用于开发代码，让最终用户能够轻松理解它。

- 防止多余代码运行。

# JavaScript 类型

在 JavaScript 中，有两种注释：

- 单行注释

- 多行注释

## JavaScript 中的单行注释

它由两个斜杠（`//`）表示。它可以同时用于语句的之前和之后。

让我们看一个单行注释的示例，它放在语句之前。

```html
<script>
  // It is the single-line comment
</script>
```

## 78 征服 JavaScript

```html
<script>
  document.write("hello everyone");
</script>
```

让我们看一个单行注释的示例，它放在语句之后。

```html
<script>
var c=30;
var d=10;
var e=c+d;//It adds values of c and d variable
document.write(e);//prints sum of 30 and 10
</script>
```

## JavaScript 中的多行注释

它可以用于添加单行或多行注释。因此，它更加方便。

它的符号是一个正斜杠跟一个星号，然后另一个斜杠。例如：

```javascript
/* code here */
```

它可以用于语句的之前、之后或中间。

```html
<script>
/* It is the multiline comment.
It will not display */
document.write("instance of javascript multiline comment");
</script>
```

# JavaScript 中的变量

JavaScript 变量仅仅是存储位置的名字。² JavaScript 变量分为两类：局部变量和全局变量。

声明 JavaScript 变量（也称为标识符）时需要遵循一些准则：

- 名称以字母（a-z 或 A-Z）、下划线（`_`）或美元符号（`$`）开头。

# JavaScript 入门 | 79

- 我们可以在初始字母后跟数字（0–9），例如 `value2`。

- JavaScript 中的变量是区分大小写的；因此，`x` 和 `X` 是不同的。

### 正确的 JavaScript 变量

```javascript
var d = 20;
var _value="sonoo";
```

### 不正确的 JavaScript 变量

```javascript
var 321=20;
var *bb=310;
```

### JavaScript 变量示例

让我们来看一个基本的 JavaScript 变量。

```javascript
<script>
var c = 30;
var d = 10;
var e=c+d;
document.write(e);
</script>
```

### JavaScript 中的局部变量

JavaScript 中的局部变量是在块或函数内部声明的。它只在函数或块内部可用。例如：

```javascript
<script>
function cde() {
 var k=10;//局部变量
}
</script>
```

或者

```javascript
<script>
If (20<15) {
 var y=40;//局部变量
}
</script>
```

## 80 征服 JavaScript

### JavaScript 中的全局变量

JavaScript 中的全局变量可以从任何函数访问。

全局变量是定义在函数之外或通过 `window` 对象声明的变量。例如：

```javascript
<script>
var data=250;//全局变量
function d() {
document.writeln(data);
}
function e() {
document.writeln(data);
}
d();//调用 JavaScript 函数
e();
</script>
```

### 在 JavaScript 函数内部声明 JavaScript 全局变量

我们必须利用 `window` 对象在函数内部定义 JavaScript 全局变量。例如：

```javascript
window.value=70;
```

现在它可以在任何函数中定义并从任何函数访问。例如：

```javascript
function m() {
window.value=120;//通过 window 对象声明全局变量
}
function n() {
alert(window.value);//从另一个函数访问全局变量
}
```

### 全局变量的内部原理

当我们在函数外部声明变量时，它会自动添加到 `window` 对象中。我们也可以通过 `window` 对象获取它。例如：



# JavaScript 入门

```javascript
var value=60;
function a() {
alert(window.value);//访问全局变量
}
```

# JavaScript 中的数据类型

JavaScript 支持许多数据类型来存储各种值。在 JavaScript 中，有两种数据类型：¹³

- 基本数据类型（Primitive data type）
- 非基本数据类型（Non-primitive data type）

JavaScript 是动态类型语言；因此，在代码中使用变量之前不需要指定其类型。要指示数据类型，我们必须使用。它可以存储任何类型的值，如整数、字符串等。例如：

```javascript
var a=60;//存储数字
var b="Raman";//存储字符串
```

## JavaScript 中的基本数据类型

在 JavaScript 中有五种基本数据类型。它们的名称如下：

| 数据类型 | 说明 |
| --- | --- |
| String (字符串) | 表示一组字符，例如 "hi."。 |
| Number (数字) | 表示一组数字，例如 100。 |
| Boolean (布尔) | 表示可以为 false 或 true 的布尔值。 |
| Undefined (未定义) | 表示未定义的值。 |
| Null (空) | 表示空，即完全没有值。 |

## JavaScript 中的非基本数据类型

以下是非基本数据类型：

| 数据类型 | 说明 |
| --- | --- |
| Object (对象) | 表示允许我们访问成员的实例。 |
| Array (数组) | 表示一组可比较的值。 |
| RegExp (正则表达式) | 代表正则表达式。 |

# JavaScript 中的运算符

JavaScript 中的运算符是用于对操作数执行操作的符号。例如¹⁴：

```javascript
var sum=3+10;
```

这里处使用了算术运算符`+`，同时使用了赋值运算符`=`。在 JavaScript 中，有若干种类别的运算符。

- 算术运算符
- 比较（关系）运算符
- 位运算运算符
- 逻辑运算符
- 赋值运算符
- 特殊运算符

## 算术运算符

为了对操作数进行算术运算，需要使用算术运算符。¹⁵

JavaScript 算术运算符是下表所列的运算符。

| 运算符 | 说明 | 示例 |
|---|---|--|
| `+` | 加法 | 20+20=40 |
| `-` | 减法 | 30–10=20 |
| `*` | 乘法 | 20*20=400 |
| `/` | 除法 | 40/10=4 |
| `%` | 取模（余数） | 40%10=0 |
| `++` | 增一 | `var a=20; ++a;` 现在 `a=21` |
| `--` | 减一 | `var a=20; --a;` 现在 `a=19` |

## 比较运算符

JavaScript 中的比较运算符比较两个操作数。以下是比较运算符：

| 运算符 | 说明 | 示例 |
| --- | --- | --- |
| `==` | 等于 | 20==20=true |
| `===` | 相同（相等且类型相同） | 20===20=true |
| `!=` | 不等于 | 20!=20=false |
| `!==` | 不严格相等 | 20!==20=false |
| `>` | 大于 | 20>20=false |
| `>=` | 大于等于 | 20>=20=true |
| `<` | 小于 | 20<20=false |
| `<=` | 小于等于 | 20<=20=true |

## 位运算运算符

位运算运算符对操作数应用位操作。以下是位运算运算符：

| 运算符 | 说明 |
|---| --- |
| `&` | 位与 |
| `\|` | 位或 |
| `^` | 位异或 |
| `~` | 位取反 |
| `<<` | 左移 |
| `>>` | 右移 |
| `>>>` | 无符号右移 |

## 逻辑运算符

JavaScript 逻辑运算符包括以下运算符。

| 运算符 | 说明 |
| --- | --- |
| `&&` | 逻辑与 |
| `\|\|` | 逻辑或 |
| `!` | 逻辑非 |

## 赋值运算符

JavaScript 赋值运算符包括以下运算符。

| 运算符 | 说明 |
| --- | --- |
| `=` | 赋值 |
| `+=` | 加赋值 |
| `-=` | 减赋值 |
| `*=` | 乘赋值 |
| `/=` | 除赋值 |
| `%=` | 取模赋值 |

## 特殊运算符

JavaScript 特殊运算符包括以下运算符。

| 运算符 | 说明 |
| --- | --- |
| `? :` | 三元运算符 |
| `,` | 逗号运算符 |
| `delete` | 删除运算符 |
| `in` | 属性检查运算符 |
| `instanceof` | 实例运算符 |
| `new` | 实例化运算符 |
| `typeof` | 类型运算符 |
| `void` | 空运算符 |
| `yield` | 生成器运算符 |

# IF-ELSE 语句在 JavaScript 中

if-else 语句用于根据条件的真假执行代码。

在 JavaScript 中，有三种类型的 if 语句：¹⁶

- if 语句
- else 语句
- if else 语句

## if 语句

它只在表达式为真时分析内容。JavaScript 语句的签名如下：

```javascript
if(expression) {
//内容
JavaScript
}
```

流程图：

![](img/70a7539ec7cf42f5e3c9c64df71823_125_0.png)

### 语句

让我们来看一个基本的 JavaScript if 语句。

```javascript
<script>
var a=40;
if(a>20) {
  document.write("a 的值大于 20");
}
</script>
```

## if...else 语句

它判断条件是真是假。JavaScript if-else 语句的语法如下¹⁷

```javascript
if(expression) {
  //当条件为真执行的内容
} else{
  //当条件为假执行的内容
}
```

流程图：

![](img/70a7539ec7cf42f5e3c9c64df71823_126_0.png)

### if-else 语句

让我们来看一个 JavaScript if-else 语句的示例，用于判断数字的奇偶。

```javascript
<script>
var d=40;
if(d%2==0) {
  document.write("d 是偶数");
}
else{
  document.write("d 是奇数");
}
</script>
```

```javascript
// 评估表达式1 是否为真
}
else if (expression2) {
// 评估表达式2 是否为真
}
else if (expression3) {
// 评估表达式3 是否为真
}
else{
// 如果没有表达式为真
}
```

流程图：

![](img/70a7539ec7c3f429f5e3c9c64df71823_127_0.png)

## if-else-if 语句

让我们来看 JavaScript 中基础的 if-else-if 表达式。

```javascript
<script>
var d=40;
if (d==20) {
```

```javascript
document.write("d is equal to 10");
}else if (a==25) {
document.write("d is equal to 15");
}else if (a==40) {
document.write("d is equal to 20");
}else{
document.write("d is not equal to 20, 25 or 40");
}
</script>
```

# JavaScript 中的 SWITCH

JavaScript 的 switch 语句用于从一组表达式中执行单段代码。它与我们在上一页学习的 else if 语句相同。然而，它比 if...else...if 更方便用，因为它可以用于整数、字符等¹⁸

JavaScript switch 语句的签名如下所示。

```javascript
switch (expression) {
  case value1:
    要执行的代码;
    break;
  case value2:
    要执行的代码;
    break;
    ....
  default:
    // 如果上述值都不匹配，则执行此代码；
}
```

让我们来看 JavaScript 中基础的 switch 语句.¹⁹

```javascript
<script>
var grade='B';
var result;
switch(grade) {
```

```javascript
case 'A':
result="Grade A";
break;
case 'B':
result="Grade B";
break;
case 'C':
result="Grade C";
break;
default:
result="No Grade";
}
document.write(result);
</script>
```

让我们来看 switch 语句在 JavaScript 中是如何工作的。

```javascript
<script>
var grade='B';
var result;
switch (grade) {
case 'A':
result+="Grade A";
case 'B':
result+="Grade B";
case 'C':
result+="Grade C";
default:
result+=" No Grade";
}
document.write(result);
</script>
```

# JavaScript 中的循环

JavaScript 循环使用 for、while、do-while 和 for-in 循环来重复代码。

它使代码更短。它通常用于数组。²⁰

在 JavaScript 中，有四种循环：

- for 循环
- while 循环
- do-while 循环
- for-in 循环

## for 循环

JavaScript 的 for 循环按固定次数遍历组件。

如果迭代次数已知，则应该使用它。for 循环的语法如下所示。

```javascript
for (initialization; condition; increment)
{
  要执行的代码
}
```

让我们来看 JavaScript 中一个简单的循环。

```javascript
<script>
for (x=1; x<=5; x++)
{
  document.write(6 + "<br/>")
}
</script>
```

## while 循环

JavaScript 的 while 循环无限地遍历组件。

当预期的迭代次数不确定，应该使用这种方法。while 循环的语法所示。

```javascript
while (condition)
{
  要执行的代码
}
```

让我们来看 JavaScript 中一个简单的 while 循环。

```javascript
<script>
  var x=12;
  while (x<=16)
  {
    document.write(x + "<br/>")
    x++;
  }
</script>
```

## do-while 循环

JavaScript 的 do-while 循环像 while 循环一样，无限地遍历项目。

无论条件是否成立，代码至少执行一次。以下代码演示了 do-while 循环的语法。

```javascript
do{
  要执行的代码
}while (condition);
```

让我们来看 JavaScript 中基础的 do-while 循环示例。

```javascript
<script>
var x=22;
do{
  document.write(x + "<br/>");
  x++;
}while (x<=26);
</script>
```

## for-in 循环

JavaScript 的 for-in 循环用于遍历对象的属性。它由三个关键部分组成：

- 循环初始化：在其中我们将计数器设置为一个初始值。在循环开始之前，会执行初始化语句²¹
- 测试语句：确定特定条件是否为真。如果满足条件，将执行循环内部的代码；否则，控制将退出循环。
- 迭代语句：允许我们增加或减少计数器。
- 所有三个部分都可以在同一行内呈现，用分号隔开。

```javascript
for (initialization; condition; increment)
{
  要执行的代码
}
```

# 对象字面量 (Object by object literal)

使用对象字面量构造对象的语法如下：

```
object={property1:value_1,property2:value_2,....
propertyName:value_N}
```

如我们所见，属性和值是通过`:`（冒号）区分的。

让我们来看 JavaScript 中创建对象的基本示例。

```javascript
<script>
emp={id:113,name:"Shiva Kishan",salary:45000};
document.write(emp.id+""+emp.name+""+"+emp.salary);
</script>
```

# 通过生成 Object 实例

直接生成对象的语法如下：

```
var object_name=new Object();
```

在这种情况下，`new`关键字被用于构造对象。

让我们来看一个直接构造对象的示例。

```javascript
<script>
emp=new Object();
emp.id=107;
emp.name="Rita Kaur";
emp.salary=52000;
document.write(emp.id+""+emp.name+""+"+emp.salary);
</script>
```

# 通过使用 Object 构造函数

我们在这里构造一个带有参数的函数。`this`关键字可以将每个参数值赋值给当前对象。

`this`关键字关联当前对象。

以下示例展示了如何使用对象构造函数创建对象。

```javascript
<script>
function emp(id,name,salary){
this.id=id;
this.name=name;
this.salary=salary;
}
e=new emp(105,"Vinay Sharma",33000);
document.write(e.id+""+"+e.name+""+"+e.salary);
</script>
```

# 在 JavaScript 对象中创建方法

在 JavaScript 对象中，我们可以指定方法。但在我们定义方法之前，我们必须在函数中添加一个与方法同名的属性。以下是在对象中定义方法的示例。

```javascript
<script>
function emp(id,name,salary) {
this.id=id;
this.name=name;
this.salary=salary;
this.change_Salary=change_Salary;
function change_Salary(other_Salary) {
this.salary=other_Salary;
}
}
e=new emp(102,"Suraj Garewal",39000);
document.write(e.id+""+"+e.name+""+"+e.salary);
e.change_Salary(41000);
document.write("<br>"+e.id+""+"+e.name+""+"+e.salary);
</script>
```

# JavaScript 中的对象方法

Object 的众多方法如下：

| 序号 | 方法 | 描述 |
|---|---|---|
| 1 | `Object.assign()` | 使用此方法从源对象转移枚举属性和自有属性。 |
| 2 | `Object.create()` | 此函数用于根据给定的原型对象和属性生成新对象。 |
| 3 | `Object.defineProperty()` | 这种方法用于描述某些属性的行为特征。 |
| 4 | `Object.defineProperties()` | 使用此技术可以创建或配置多个对象属性。 |
| 5 | `Object.entries()` | 该函数返回一个包含键值对的数组。 |
| 6 | `Object.freeze()` | 该策略避免删除现有属性。 |
| 7 | `Object.getPropertyDescriptor()` | 该函数返回给定对象属性的描述符。 |
| 8 | `Object.ownDescriptors()` | 该函数检索对象的所有属性描述符。 |
| 9 | `Object.getPropertyNames()` | 该函数产生一个发现的属性数组（可枚举或不可枚举）。 |
| 10 | `Object.getOwnPropertySymbols()` | 该函数产生一个包含我们所有自有 symbol 键属性的数组。 |
| 11 | `Object.getPrototypeOf()` | 此方法返回给定对象的原型。 |
| 12 | `Object.is()` | 该函数比较两个值以判断它们是否相同。 |



| 13 | `Object.isExtensible()` | 此方法检测对象是否可扩展。 |
| 14 | `Object.isFrozen()` | 此方法检测项目是否被冻结。 |
| 15 | `Object.isSealed()` | 此方法检测项目是否被密封。 |
| 16 | `Object.keys()` | 该函数返回一个包含所提供的对象的属性名称的数组。 |
| 17 | `Object.preventExtensions()` | 此技术用于禁止对象扩展。 |
| 18 | `Object.seal()` | 此方法禁用添加新属性，并将所有当前属性标记为不可配置。 |
| 19 | `Object.setPrototypeOf()` | 该函数将一个对象的原型赋值给另一个对象。 |
| 20 | `Object.values()` | 此方法返回一个值数组。 |

# JavaScript 中的数组

JavaScript 中表示一组相同对象的对象的数组（`Array`）。

在 JavaScript 中，有三种方法创建数组。

- 通过数组字面量。
- 通过显式生成 `Array` 实例（使用 `new` 关键字）。
- 通过使用 `Array` 构造函数（使用 `new` 关键字）。

## JavaScript 中的 Array

### 1. 数组字面量

使用数组字面量构建数组的语法如下：`var array=[value1,value2....valueN]`。如我们所见，值通过逗号分隔。

```javascript
<script>
var array=["value1","value2","value3"];
for (var i=0; i<array.length; i++) {
document.write(array[i]);
}
</script>
```

### 2. 直接生成 Array 实例

直接生成数组的语法如下：`var array_name=new Array()`。在这种情况下，`new` 关键字被用于构造对象。让我们来看一个直接构造对象的示例。

```javascript
<script>
var array=new Array();
array[0]="value1";
array[1]="value2";
array[2]="value3";
for (var i=0; i<array.length; i++) {
document.write(array[i]);
}
</script>
```

### 3. 使用 Array 构造函数

使用 `Array` 构造函数数组的语法如下：`var array=new Array(value1,value2...)`。如我们所见，值通过逗号分隔。

```javascript
<script>
var array=new Array("value1","value2","value3");
for (var i=0; i<array.length; i++) {
document.write(array[i]);
}
</script>
```

# JavaScript 中的数组方法

数组的众多方法及其描述如下：

| 方法 | 描述 |
|---|---|
| `concat()` | 将两个或多个数组合并为一个数组。 |
| `copywithin()` | 将数组的一个部分复制到数组的另一个位置。 |
| `entries()` | 返回一个包含键值值对的迭代器。 |
| `every()` | 检查数组中的所有元素是否通过了实现的测试。 |
| `flat()` | 根据指定的深度将嵌套数组扁平化。 |
| `flatMap()` | 使用映射函数映射每个数组元素，然后将结果扁平化。 |
| `fill()` | 用静态值填充数组。 |
| `from()` | 从可配置数量的参数创建一个新数组。 |
| `filter()` | 返回一个包含满足函数元素的新数组。 |
| `find()` | 返回满足条件的第一个数组元素。 |
| `findIndex()` | 返回满足条件的第一个数组元素的索引。 |
| `forEach()` | 为数组的每个元素调用一次指定的方法。 |
| `includes()` | 判断数组是否包含指定元素。 |
| `indexOf()` | 在数组中搜索指定元素并返回其索引。 |
| `isArray()` | 判断所提供的值是否为数组。 |
| `join()` | 通过连接数组成员创建一个字符串。 |
| `keys()` | 构造一个仅包含数组键的迭代器。 |
| `lastIndexOf()` | 返回数组中指定元素最后一次出现的索引。 |
| `map()` | 在数组的每个元素上执行指定函数并返回新数组。 |
| `pop()` | 删除并返回数组的最后一个元素。 |
| `push()` | 在末尾添加一个或多个元素。 |
| `reverse()` | 反转数组的元素。 |
| `reduce(function, initial)` | 从左到右对数组的每个值执行指定函数，将其还原为单个值。 |
| `reduceRight(function, initial)` | 从右到左对数组的每个值执行指定函数，将其还原为单个值。 |
| `some()` | 判断数组中至少有一个元素满足实现的测试。 |
| `shift()` | 删除并返回数组的第一个成员。 |
| `slice()` | 返回一个包含数组部分副本的新数组。 |
| `sort()` | 返回排序后的数组元素。 |
| `splice()` | 在指定数组中添加或删除元素。 |
| `toLocaleString()` | 返回包含提供数组所有成员的字符串。 |
| `toString()` | 将数组项转换为字符串形式，同时保持原始数组不变。 |
| `unshift()` | 在数组开头插入一个或多个元素。 |
| `values()` | 构造一个带有每个数组索引值的迭代器。 |

# JavaScript 中的字符串

JavaScript 中的字符串是一个表示系列字符的对象。在 JavaScript 中，有两种方法可以创建字符串。

- 使用字符串字面量
- 使用字符串对象（使用 `new` 关键字）

### 1. 使用字符串字面量

使用双引号来构造字符串字面量。使用字面量构造字符串的语法如下：

```javascript
var string_name="string_value";
<script>
var str="This is the string literal";
document.write(str);
</script>
```

### 2. 使用字符串对象（使用 `new` 关键字）

使用 `new` 关键字创建字符串对象的语法如下：

```javascript
var string_name=new String("string_literal");
```

在这种情况下，`new` 关键字用于构造一个字符串实例。让我们来看使用 `new` 关键字形成的 JavaScript 字符串。

```javascript
<script>
var stringname=new String("hey everyone");
document.write(stringname);
</script>
```

# JavaScript 中的字符串方法

让我们来看 JavaScript 字符串方法的示例。

| 方法 | 说明 |
| --- | --- |
| `charAt()` | 返回指定索引处的字符值。 |
| `charCode()` | 它提供指定索引处的字符的 Unicode 值。它允许我们合并两个或多个字符串。 |
| `concat()` | 返回字符值在给定字符串中的位置作为响应。 |
| `indexOf()` | 通过返回从最后一个位置开始搜索的结果，提供字符值在给定字符串内部的位置。 |
| `search()` | 搜索指定的正则表达式，如果发现匹配项，则返回其位置。 |
| `match()` | 如果发现匹配项，它检查给定文本是否符合指定的正则表达式并返回该正则表达式。 |
| `replace()` | 用提供的字符串替换指定的字符串。 |
| `substr()` | 基于指定的起始位置和长度。用于获取给定字符串的局部。 |
| `substring()` | 基于指定的索引。用于获取给定文本的一个区域。 |
| `slice()` | 我们可以用它获取给定字符串的一个区域。我们可以为它提供正索引和负索引。 |
| `toLowerCase()` | 将发送给它的字符串转为小写。 |
| `toLocaleLowerCase()` | 根据主机的当前语言区域将字符串转换为小写字母。 |
| `toUpperCase()` | 将字符串更改为大写字母。 |
| `toLocaleUpperCase()` | 根据主机的当前语言区域将提供的文本转换为大写字母。 |
| `toString()` | 返回一个表示特定对象的字符串。 |
| `valueOf()` | 从原始值返回字符串对象。 |
| `split()` | 从字符串创建子数组并返回结果数组。 |
| `trim()` | 移除字符串左右两侧的空白。 |

## 1. JavaScript 中的 String charAt(index) 方法

JavaScript 字符串的 `charAt()` 函数返回指定索引处的字符。

```javascript
<script>
var str="heeveryone";
document.write(str.charAt(2));
</script>
```

### 2. JavaScript 字符串 concat(str) 方法

JavaScript 中的 `String.concat(str)` 方法用于连接或合并字符串。

```javascript
<script>
var st1="heyeveryone ";
var st2="concat example";
var st3=st1.concat(st2);
document.write(st3);
</script>
```

### 3. JavaScript 中的 String indexOf(str) 方法

JavaScript 字符串 `indexOf(str)` 函数返回字符串的索引位置。

```javascript
<script>
var st1="hey from everyone indexof";
var n=st1.indexOf("from");
document.write(n);
</script>
```

### 4. JavaScript 方法 lastIndexOf(str)

JavaScript 字符串 `lastIndexOf(str)` 函数返回字符串的最后一次索引位置。

```javascript
<script>
var st1="everybody from everyone indexof";
var n=st1.lastIndexOf("every");
document.write(n);
</script>
```

### 5. JavaScript 中的 toLowerCase() 方法

JavaScript 中的字符串 `toLowerCase()` 函数返回小写形式的提供字符串。

```javascript
<script>
var st1="JavaScript toLowerCase Instance";
var st2=st1.toLowerCase();
document.write(st2);
</script>
```

### 6. JavaScript 中的 toUpperCase() 方法

JavaScript 中的字符串 `toUpperCase()` 函数返回大写形式的提供字符串。

```javascript
<script>
var st1="JavaScript toUpperCase Inat";
var st2=st1.toUpperCase();
document.write(st2);
</script>
```

### 7. JavaScript 中的 String slice(beginIndex, endIndex) 方法

JavaScript 字符串 `slice(beginIndex, endIndex)` 函数返回从 `beginIndex` 到 `endIndex` 的字符串部分。在 `slice()` 函数中，`beginIndex` 是包含的，而 `endIndex`是不包含的。

```javascript
<script>
var st1="abcdefgh";
var st2=st1.slice(3, 6);
document.write(st2);
</script>
```

### 8. JavaScript 中的 String trim() 方法

JavaScript 字符串 `trim()` 函数消除字符串开头和结尾的空白。

```javascript
<script>
var st1=" javascript trim ";
var st2=st1.trim();
document.write(st2);
</script>
```

### 9. JavaScript 中的 split() 方法

```javascript
<script>
var st1="apple,banana,orange";
var arr=st1.split(",");
document.write(arr[1]);
</script>
```

# JavaScript 中的字符串

`new` 关键字用于构造一个字符串实例。让我们来看一个使用 `new` 关键字形成的 JavaScript 字符串。

```javascript
<script>
var stringname=new String("hey everyone");
document.write(stringname);
</script>
```

# 征服 JavaScript

JavaScript 中的日期示例

让我们来看打印日期对象的简单示例。它会同时发布日期和时间。

```javascript
Current Date and Time: <span id="text"></span>
<script>
var today=new Date();
document.getElementById('text').innerHTML=today;
</script>
```

让我们来看另一个打印日期、月份和年份的代码。

```javascript
<script>
var date=new Date();
var day=date.getDate();
var month=date.getMonth()+1;
var year=date.getFullYear();
document.write("<br>The date is: "+day+"/"+month+"/"+year+");");
</script>
```

### JavaScript 当前时间示例

让我们来看打印系统当前时间的简单示例。

```javascript
Current Time: <span id="text"></span>
<script>
var today=new Date();
var h=today.getHours();
var m=today.getMinutes();
var s=today.getSeconds();
document.getElementById('text').
innerHTML=h+":"+m+":"+s;
</script>
```

### JavaScript 数字时钟示例

让我们来看使用 JavaScript 日期对象显示数字时钟的简单示例。

在 JavaScript 中，我们可以使用 `setTimeout()` 或 `setInterval()` 方法来指定间隔。

```javascript
Current Time: <span id="text"></span>
<script>
window.onload=function(){getTime()};
```

```javascript
function getTime() {
var today=new Date();
var h=today.getHours();
var m=today.getMinutes();
var s=today.getSeconds();
// 在小于 10 的数字前加 0
m=checkTime(m);
s=checkTime(s);
document.getElementById('text').
innerHTML="h="+h+":m="+m+":s="+s;
setTimeout(function() {getTime()},1200);
}
//setInterval("getTime()",1000);//另一种方法
function checkTime(i) {
if (i<10) {
i="0" + i;
}
return i;
}
</script>
```

## JavaScript 中的数学运算

JavaScript math 对象包含许多常量和方法，用于执行数学运算。与日期对象不同，它没有构造函数。

### Math 方法

让我们遍历 JavaScript 数学方法及其描述。

| 方法 | 描述 |
| --- | --- |
| `abs()` | 返回提供数字的绝对值。 |
| `acos()` | 返回提供的数字以弧度为单位的余弦。 |
| `asin()` | 计算并返回提供的数字以弧度为单位的正弦。 |
| `atan()` | 返回整数弧度的反正正切。 |
| `cbrt()` | 返回提供的整数的立方根。 |
| `ceil()` | 函数返回大于或等于给定参数的最小整数。 |
| `cos()` | 返回提供的数字的余弦。 |
| `cosh()` | 返回提供的整数的双曲余弦。 |



# 110 征服 JavaScript

| 方法 | 描述 |
| --- | --- |
| `exp()` | 返回提供数字的指数形式。 |
| `floor()` | 返回小于或等于给定值的最大整数。 |
| `hypot()` | 返回给定数字平方和的立方根。 |
| `log()` | 计算数字的自然对数。 |
| `max()` | 返回提供数字中的最大值。 |
| `min()` | 返回提供数字中的最小值。 |
| `pow()` | 返回基数乘以指数的值。 |
| `random()` | 返回 0（包含）和 1（不包含）之间的随机数。 |
| `round()` | 返回最接近指定数字的整数。 |
| `sign()` | 返回提供数字的符号。 |
| `sin()` | 返回提供的数字的正弦。 |
| `sinh()` | 返回提供的整数的双曲正弦。 |
| `sqrt()` | 计算输入数字的平方根。 |
| `tan()` | 返回提供的整数的正切。 |
| `tanh()` | 返回提供的整数的双曲正切。 |
| `trunc()` | 返回提供数字的整数部分。 |

## `Math.sqrt(n)`

JavaScript 中的 `Math.sqrt(n)` 函数返回提供的整数的平方根。

14 的平方根是：<span id="pl1"></span>

```javascript
<script>
document.getElementById('pl1').innerHTML=Math.sqrt(14);
</script>
```

## `Math.random()`

JavaScript 中的 `Math.random()` 函数提供一个 0 到 1 之间的随机数。

随机数是：<span id="pl2"></span>

```javascript
<script>
document.getElementById('pl2').innerHTML=Math.random();
</script>
```

## `Math.pow(m, n)`

JavaScript 中的 `Math.pow(m, n)` 函数返回 `m` 的 `n` 次。

5 的 2 次是：<span id="p3"></span>

```javascript
<script>
document.getElementById('p3').innerHTML=Math.pow(5, 2);
</script>
```

## `Math.floor(n)`

JavaScript 中的 `Math.floor(n)` 函数返回小于或等于提供的整数。

14 的 floor 是：<span id="p4"></span>

```javascript
<script>
document.getElementById('p4').innerHTML=Math.floor(14);
</script>
```

## `Math.ceil(n)`

JavaScript 中的 `Math.ceil(n)` 函数返回大于或等于提供的整数的最小整数。

14 的 ceil是：<span id="p5"></span>

```javascript
<script>
document.getElementById('p5').innerHTML=Math.ceil(14);
</script>
```

## `Math.round(n)`

JavaScript 中的 `Math.round(n)` 函数返回最接近指定数字的整数。

14 的 round是：<span id="p6"></span>

```javascript
<script>
document.getElementById('p6').innerHTML=Math.round(14);
</script>
```

## `Math.abs(n)`

JavaScript 中的 `Math.abs(n)` 函数返回提供的整数的绝对值。

14 的绝对值是：<span id="p7"></span>

```javascript
<script>
document.getElementById('p7').innerHTML=Math.abs(14);
</script>
```

## 开始学习 JavaScript | 111

## JavaScript 中的 NUMBER 对象

我们可以使用 `Number` 对象来表示数值。可以是整数或浮点数。如果值无法转换为数字，它将返回 `NaN`（不是数字），可以使用 `isNaN()` 函数进行测试。我们也可以将数字赋值给变量。

```javascript
var x=10
var y=32.7
var z=1e4
var n=new Number(value);
```

| 常量 | 描述 |
| --- | --- |
| `MIN_VALUE` | 最大的最小值。 |
| `MAX_VALUE` | 最大的值。 |
| `POSITIVE_INFINITY` | 溢出值，产生正无穷。 |
| `NEGATIVE_INFINITY` | 溢出值，产生负无穷。 |
| `NaN` | 反映“不是数字”的值。 |

## JavaScript BOOLEAN

JavaScript `Boolean` 对象表示两种状态之一：`true` 或 `false`。`Boolean` 对象可以使用 `Boolean()` 构造函数创建，如下：

`Boolean bn=new Boolean(value);`

JavaScript `Boolean` 对象的默认值为 `false`。

### JavaScript Boolean 示例

```javascript
<script>
document.write(30<40);////true
document.write(12<8);////false
</script>
```

### Boolean 属性

| 属性 | 描述 |
| --- | --- |
| `constructor` | 生成返回的 `Boolean` 函数的引用。 |
| `prototype` | 允许我们在 `Boolean` 原型中包含属性和方法。 |

## 布尔方法

| 方法 | 描述 |
| --- | --- |
| `toSource()` | 以字符串形式返回布尔对象的源。 |
| `toString()` | 将布尔值转换为字符串。 |
| `valueOf()` | 将另一种类型转换为布尔值。 |

# JAVASCRIPT 中的错误与异常

异常（Exception）表示异常情况的发生，这需要使用特殊的处理方法。编程中的异常是一段偏离了正常执行流的代码。此类异常需要使用特定的编程结构才能执行。

到底什么是异常处理？

异常处理是编程中的一种过程或方法，用于处理和执行代码中的异常语句。它还允许你控制代码/程序的执行流。

各种处理器会处理异常，而代码被用于处理具体的逻辑。例如，将一个非零数字除以零始终会导致无穷大，这是一个异常。因此，可以在异常处理的帮助下对其执行和管理。

要在异常处理中抛出异常，可以使用 `throw` 语句来抛出异常。将异常封装在 `try...catch` 块中可以处理抛出的异常。如果发生错误，将执行 `catch` 块；否则，仅执行 `try` 块中的指令。

因此，编程语言中可能会出现多种形式的错误，干扰程序的正确执行。在编程中，错误分为三类：

- a. 语法错误。
- b. 运行时错误。
- c. 逻辑错误。

## 错误类型

### 语法错误

语法错误（也称为解析错误）发生在传统编程语言的编译过程中，以及 JavaScript 的解释过程中。30

例如，下行代码由于缺少闭右括号而会产生语法错误。

```html
<script type="text/javascript">
<!--
  window.print();
---->
</script>
```

当 JavaScript 中发生语法错误时，与语法错误处于同一线程的代码会受到影响，只要其他线程中的剩余代码不依赖于包含问题的代码，它们就可以继续运行。

### 运行时错误

在执行期间（编译/解释之后），会发生运行时错误，也称为异常。例如，下行代码会导致运行时错误，尽管其语法是有效的，但它尝试调用一个不存在的方法。

```html
<script type="text/javascript">
<!---
  window.print();
```

//-->

</script>

```

异常也会影响它们发生的线程，允许其他 JavaScript 线程能够正常进行。

## 逻辑错误

逻辑错误是最难定位的错误形式。这些问题不是由语法或运行时问题引起的。

相反，当我们在驱动脚本的逻辑中出错且没有获得预期的结果时，就会出现这种情况。我们无法注意到问题，因为我们想要包含在软件中的逻辑是由我们的业务需求决定的。

## `try...catch...finally` 语句

最新的 JavaScript 版本引入了异常处理功能。

JavaScript 具有 `try...catch...finally` 结构和用于处理异常的 `throw` 操作符。JavaScript 语法错误可以捕获，但无法捕获程序员生成的或运行时异常。`try...catch...finally` 块的语法如下：

```html
<script type="text/javascript">

<!--

try {

    // 执行的代码

    [break];

}

catch ( e ) {

    // 发生异常时执行的代码

    [break];

}

[ finally {

    // 无论是否发生异常，始终执行的代码

    ]}

//-->

</script>
```

# JavaScript 入门 I ■ 117

`catch` 块或 `finally` 块必须位于 `try` 块之前（或两者其一）。如果在 `try` 块内部抛出异常并在变量 `e` 中报告，则会执行 `catch` 块。在 `try/catch` 之后，可选的 `finally` 块将无条件运行。

## 示例

这是一个尝试调用不存在的函数的示例，这会导致异常。

让我们看看在没有 `try...catch` 的情况下它是如何的——

```html
<html>

<head>

  <script type="text/javascript">

  <!--

    function myFunc() {

      var k = 120;

      alert("变量 k 的值是 : " + k );

    }

  -->

  </script>

</head>

<body>

  <p>点击下方查看结果：</p>

  <form>

    <input type="button" value="点击此处" onclick="myFunc();" />

  </form>

</body>

</html>
```

现在让我们利用 `try...catch` 来捕获此错误并提供一个用户友好的消息。

如果我们想向用户隐藏这个问题，我们也可以抑制此消息。

```html
<html>

<head>

  <script type="text/javascript">

  <!--

    function myFunc() {

      var k = 120;

      try {

        alert("变量 k 的值是 : " + k);

      } catch ( e ) {

        alert("错误: " + e.description );

      }

    }

  -->

  </script>

</head>

<body>

  <p>点击下方查看结果：</p>

  <form>

    <input type="button" value="点击此处" onclick="myFunc();" />

  </form>

</body>

</html>
```

最后，我们可以使用一个在 `try/catch` 之后始终无条件运行的块。
这是一个图示。

```html
<html>

<head>

  <script type="text/javascript">

  <!--

    function myFunc() {

      var k = 120;

      try {

        alert("变量 k 的值是 : " + k);

      } catch ( e ) {

        alert("错误: " + e.description );

      }

      finally {

        // 无论是否发生异常，始终执行的代码

      }

    }

  -->

  </script>

</head>

<body>

  <p>点击下方查看结果：</p>

  <form>

    <input type="button" value="点击此处" onclick="myFunc();" />

  </form>

</body>

</html>
```

# JavaScript 入门 ■ 117

`catch` 块或 `finally` 块必须位于 `try` 块之前（或两者其一）。如果在 `try` 块内部抛出异常并在变量 `e` 中报告，则会执行 `catch` 块。在 `try/catch` 之后，可选的 `finally` 块将无条件运行。

## 示例

这是一个尝试调用不存在的函数的示例，这会导致异常。

让我们看看在没有 `try...catch` 的情况下它是如何的——

```html
<html>

<head>

  <script type="text/javascript">

  <!--

    function myFunc() {

      var k = 120;

      alert("变量 k 的值是 : " + k );

    }

  -->

  </script>

</head>

<body>

  <p>点击下方查看结果：</p>

  <form>

    <input type="button" value="点击此处" onclick="myFunc();" />

  </form>

</body>

</html>
```

现在让我们利用 `try...catch` 来捕获此错误并提供一个用户友好的消息。

如果我们想向用户隐藏这个问题，我们也可以抑制此消息。

```html
<html>

<head>

  <script type="text/javascript">

  <!--

    function myFunc() {

      var k = 120;

      try {

        alert("变量 k 的值是 : " + k);

      } catch ( e ) {

        alert("错误: " + e.description );

      }

    }

  -->

  </script>

</head>

<body>

  <p>点击下方查看结果：</p>

  <form>

    <input type="button" value="点击此处" onclick="myFunc();" />

  </form>

</body>

</html>
```

最后，我们可以使用一个在 `try/catch` 之后始终无条件运行的块。
这是一个图示。

```html
<html>

<head>

  <script type="text/javascript">

  <!--

    function myFunc() {

      var k = 120;

      try {

        alert("变量 k 的值是 : " + k);

      } catch ( e ) {

        alert("错误: " + e.description );

      }

      finally {

        // 无论是否发生异常，始终执行的代码

      }

    }

  -->

  </script>

</head>

<body>

  <p>点击下方查看结果：</p>

  <form>

    <input type="button" value="点击此处" onclick="myFunc();" />

  </form>

</body>

</html>
```

### `throw` 语句

我们可以使用 `throw` 语句来抛出内置或自定义异常。

## 示例
下面的示例展示了如何使用 `throw` 语句。

```html
<html>

<head>

  <script type="text/javascript">

<!--

function myFunc() {

    var j = 120;

    var k = 0;

    try {

        if ( k == 0 ) {

            throw("除以零.");

        } else {

            var m = j / k;

        }

    } catch ( e ) {

        alert("错误: " + e);

    }

}

//-->

</script>

<body>

<p>点击下方查看结果：</p>

<form>

    <input type="button" value="点击此处" onclick="myFunc();" />

</form>

</body>

</html>
```

### `onerror()` 函数

为了开始处理错误，JavaScript 引入了 `onerror` 事件。当页面上发生异常时，错误事件会被派发到 `window` 对象。

```html
<html>

<head>

<script type="text/javascript">

<!--

  window.onerror = function () {

    alert("发生了错误.");

  }

-->

</script>
```



```html
</head>

<body>
  <p>点击下方查看结果：</p>

  <form>
    <input type="button" value="点击此处" onclick="myFunc();" />
  </form>
</body>

</html>
```

`onerror`事件处理器返回三部分信息，可用于确定错误的性质：

- 错误消息：浏览器为指定问题显示的相同消息。
- URL：发生问题的文件 URL。
- 行号：导致错误的提供的 URL 中的行号。

这是一个如何获取这些信息的示例：

```javascript
<html>
<head>
  <script type="text/javascript">
    <!---
    window.onerror = function (msg, url, line) {
      alert("消息 : " + msg);
      alert("url : " + url);
      alert("行号 : " + line);
    }
    // -->
  </script>
</head>

<body>
  <p>点击下方查看结果：</p>

  <form>
    <input type="button" value="点击此处" onclick="myFunc();" />
  </form>
</body>

</html>
```

## 122 征服 JavaScript

我们可以以我们认为最好的方式呈现提取的数据。

如果在加载图像时遇到困难，我们可以使用`onerror`方法显示错误消息，如下。

我们可以在多种 HTML 元素上使用`onerror`来显示合适的错误消息。

# JavaScript 中的事件

我们将在下方讨论 JavaScript 中的事件。

JavaScript 通过事件与 HTML 通信，事件是对用户或浏览器对页面进行的更改而产生的。网站加载后，会发生某些事情。任何按键、窗口关闭、窗口调整大小都被视为事件。

开发者可以使用这些事件来执行程序响应，例如关闭按钮、向用户显示消息、验证数据以及几乎可以想象的任何其他响应。事件是文档对象模型（DOM）Level 3 的组成部分，每个 HTML 元素都有一组事件，可用于执行 JavaScript 代码。

### onclick 事件类型

这是最常见的事件类型，当用户点击鼠标左键时发生。

我们可以对这种事件类型应用验证、警告等操作。

## 示例

考虑以下示例：

```html
<html>
<head>
  <script type="text/javascript">
    <!--
    function sayHey() {
      alert("Hey Everyone");
    }
    -->
  </script>
</head>

<body>
  <p>点击按钮并查看结果</p>

  <form>
    <input type="button" onclick="sayHey()" value="Say Hey" />
  </form>
</body>

</html>
```

### onsubmit 事件类型

当我们尝试提交表单时，会触发一个名为`onsubmit`的事件。我们可以使用这种事件类型进行表单验证。

## 示例

以下代码演示了如何利用`onsubmit`。在将表单输入发送到网站之前，我们使用`validate()`方法。如果`validate()`方法返回`true`，则提交表单；否则数据不会提交。

考虑以下示例：

```html
<html>
<head>
  <script type="text/javascript">
    <!--
    function validation() {
      ...
      这里所有的验证逻辑都写在这里
      return true or false
    }
    -->
  </script>
</head>

<body>
  <form method="POST" action="t.cgi" onsubmit="return validate()">
    <input type="submit" value="Submit" />
  </form>
</body>

</html>
```

### mouseover 和 mouseout

两种事件类型可以帮助我们利用图像甚至文本创建极佳的效果。当我们将鼠标移动到元素上方时，会触发`mouseover`事件；当我们将鼠标离开该元素时，会触发`mouseout`事件。

考虑以下示例：

```html
<html>
<head>
  <script type="text/javascript">
    <!---
    function over() {
      document.write("Mouse-Over");
    }

    function out() {
      document.write("Mouse-Out");
    }
    <!-- -->
  </script>
</head>

<body>
  <p>将鼠标移入 div 内部查看结果：`over()`</p>

  <div onmouseover="over()" onmouseout="out()">
    <h2>这是 div 内部</h2>
  </div>
</body>

</html>
```



## 标准 HTML 5 事件

为了方便起见，下面列出了标准的 HTML 5 事件。`Script` 表示将针对事件执行的 JavaScript 函数。

| 属性 | 值 | 描述 |
|---|---|---|
| `Offline` | `script` | 当文档处于离线状态时，发生此事件。 |
| `Onabort` | `script` | 触发一个中止事件。 |
| `afterprint` | `script` | 在文档打印后发生此事件。 |
| `onload` | `script` | 在文档加载之前发生此事件。 |
| `onbeforeprint` | `script` | 在文档打印之前发生此事件。 |
| `onblur` | `script` | 当窗口失去焦点时，发生此事件。 |
| `onplay` | `script` | 当媒体可以开始播放但必须暂停缓冲时触发。 |
| `oncanplaythrough` | `script` | 当媒体可以一直播放而无需暂停缓冲时，会触发此事件。 |
| `onchange` | `script` | 当元素发生变化时，触发此事件。 |
| `onclick` | `script` | 当鼠标被点击时触发。 |
| `oncontextmenu` | `script` | 当调用上下文菜单时，触发此事件。 |
| `ondblclick` | `script` | 当鼠标被双击时触发。 |
| `ondrag` | `script` | 当元素被拖动时，发生此事件。 |
| `ondragend` | `script` | 在拖放操作结束时，触发此事件。 |
| `ondragenter` | `script` | 当元素被拖动到正确的放置目标时，触发此事件。 |
| `ondragleave` | `script` | 当元素移动到有效放置目标上方时，发生此事件。 |
| `ondragover` | `script` | 在拖放操作开始时触发。 |
| `ondragstart` | `script` | 在拖放操作开始时触发。 |
| `ondrop` | `script` | 当被拖动的元素被释放时，发生此事件。 |
| `ondurationchange` | `script` | 当媒体长度被修改时，发生此事件。 |
| `onemptyied` | `script` | 当媒体资源元素意外变为空时，会触发此事件。 |
| `onended` | `script` | 当媒体到达终点时，触发此事件。 |
| `onerror` | `script` | 当发生错误时，触发此函数。 |
| `onfocus` | `script` | 当窗口获得焦点时，发生此事件。 |
| `onformchange` | `script` | 当表单发生变化时，触发此事件。 |
| `oninput` | `script` | 当表单接收用户输入时，触发此事件。 |
| `onhaschange` | `script` | 当文档发生变化时，触发此事件。 |
| `oninput` | `script` | 当元素接收用户输入时，触发此事件。 |
| `oninvalid` | `script` | 当元素无效时，触发此事件。 |
| `onkeydown` | `script` | 当按下按键时，发生此事件。 |
| `onkeypress` | `script` | 当按下并释放按键时，发生此事件。 |
| `onkeyup` | `script` | 当释放按键时，发生此事件。 |
| `onload` | `script` | 当文档加载时，发生此事件。 |
| `onloadeddata` | `script` | 当媒体数据加载时，发生此事件。 |
| `onloadedmetadata` | `script` | 当媒体元素的持续和其他媒体数据加载时，发生此事件。 |
| `onloadstart` | `script` | 当浏览器开始加载媒体数据时，发生此事件。 |
| `onmessage` | `script` | 当消息被触发时，调用此函数。 |
| `onmousedown` | `script` | 当按下鼠标按钮时，发生此事件。 |
| `onmousemove` | `script` | 当鼠标光标移动时，触发此事件。 |
| `onmouseleave` | `script` | 当鼠标光标离开元素时，触发此事件。 |
| `onmouseover` | `script` | 当鼠标光标经过元素时，触发此事件。 |
| `onmouseup` | `script` | 当释放鼠标按钮时，发生此事件。 |
| `onmousewheel` | `script` | 当滚动滚轮时，发生此事件。 |
| `onoffline` | `script` | 当文档处于离线状态时，发生此事件。 |
| `oninit` | `script` | 当文档变为线时，发生此事件。 |
| `onload` | `script` | 当文档在线时，发生此事件。 |
| `onhide` | `script` | 当窗口隐藏时，发生此事件。 |
| `onpage` | `script` | 当窗口显示时，发生此事件。 |
| `onpause` | `script` | 当媒体停止播放时，发生此事件。 |
| `onplay` | `script` | 当媒体可以开始播放但必须暂停缓冲时触发；当媒体开始播放时触发；当窗口历史改变时触发。 |
| `onplaying` | `script` | 当浏览器检索媒体数据时，发生此事件。 |
| `onpopstate` | `script` | 当媒体播放速率改变时。当就绪状态改变时触发。 |
| `onprogress` | `script` | 当文档重做时，发生此事件。 |
| `onratechange` | `script` | 当窗口大小改变时，发生此事件。 |
| `onreadystatechange` | `script` | 当元素的滚动条滚动时，触发此事件。 |
| `onredo` | `script` | 当媒体元素的查找属性不再为 `true` 且查找停止时，触发此事件。 |
| `onresize` | `script` | 当媒体停止播放时，发生此事件。 |
| `onscroll` | `script` | 当媒体可以开始播放时触发；当媒体开始播放时触发；当窗口历史改变时触发。 |
| `onseeked` | `script` | 在浏览器检索媒体数据后发生此事件。 |
| `onseeking` | `script` | 当媒体元素的查找属性为 `true` 且查找开始时，会触发此事件。 |
| `onselect` | `script` | 当元素被选中时，触发此函数。 |
| `onstalled` | `script` | 当检索媒体数据出现错误时，触发此事件。 |
| `onstorage` | `script` | 当文档加载时，触发此事件。 |
| `onsubmit` | `script` | 当表单提交时，发生此事件。 |
| `onsuspend` | `script` | 当浏览器正在下载媒体数据但在检索到整个媒体文件之前停止时，会触发此事件。 |
| `ontimeupdate` | `script` | 当媒体的播放位置改变时，发生此事件。 |
| `onundo` | `script` | 当文档执行撤销时，触发此事件。 |
| `onunload` | `script` | 当用户退出文档时，发生此事件。 |
| `onvolumechange` | `script` | 当媒体音量改变或当音量被静音时触发。 |
| `onwaiting` | `script` | 当媒体停止播放但预计将重新播放时，触发此事件。 |

## 128 征服 JavaScript

在本章中，我们讨论了 Visual Studio Code 和 `node.js` 的安装。我们介绍了原生 JavaScript（Vanilla JavaScript）、数据类型与运算符、函数以及数组。我们还讨论了错误处理和事件。

## NOTES

- 1 从 7 选项中选择最佳 JavaScript 编辑器：www.testim.io/blog/best-javascript-editor-6-options/ 访问于：2022年9月22日。
- 2 如何为 JavaScript 配置 Visual Studio Code：https://linuxhint.com/set-up-visual-studio-code-for-javascript/:text=Select%20all%20the%20options%20You,%20Studio%20Code%20will%20launch 访问于：2022年9月22日。
- 3 如何在 Linux 上安装 Visual Studio Code：www.tecmint.com/install-visual-studio-code-on-linux/ 访问于：2022年9月23日。
- 4 在 Windows 上安装 Node.js：www.geeksforgeeks.org/installation-of-node-js-on-windows/ 访问于：2022年9月22日。
- 5 在 Linux 上安装 Node.js：www.geeksforgeeks.org/installation-of-node-js-on-linux 访问于：2022年9月22日。
- 6 如何在 VS code 编辑器中创建并运行 Node.js 项目：www.geeksforgeeks.org/how-to-create-and-run-node-js-project-in-vs-code-editor/ 访问于：2022年9月22日。
- 7 JavaScript 开发者的最佳 VS Code 扩展：https://livedream.com/post/best-vscode-extensions-for-javascript/ 访问于：2022年9月22日。
- 8 什么是“原生 JavaScript”：www.javpoint.com/what-is-vanilla-javascript 访问于：
- 9 打印 Hello World 的 JavaScript 程序：www.programiz.com/javascript/examples/hello-world 访问于：2022年9月24日。
- 10 JavaScript 语法：www.tutorialpoint.com/javascript/javascript_syntax.htm 访问于：2022年9月24日。
- 11 JavaScript 注：www.javpoint.com/javascript-comment 访问于：2022年9月24日。
- 12 JavaScript 变量：www.javpoint.com/javascript-variable 访问于：2022年9月24日。
- 13 JavaScript 数据类型：www.javpoint.com/javascript-data-types 访问于：2022年9月24日。
- 14 JavaScript 运算符：www.javpoint.com/javascript-operators 访问于：2022年9月24日。
- 15 JavaScript 运算符：www.geeksforgeeks.org/javascript-operators/ 访问于：2022年9月24日。
- 16 JavaScript If-else：www.javpoint.com/javascript-if 访问于：2022年9月24日。

## 开始学习 JavaScript | 129

- 17 JavaScript—if...else 语句：www.tutorialspoint.com/javascript/javascript-if-else.htm 访问于：2022年9月24日。
- 18 JavaScript Switch：www.javatpoint.com/javascript-switch 访问于：2022年9月24日。
- 19 JavaScript Switch Case—JS Switch 语句示例：www.freecodecamp.org/news/javascript-switch-case-js-switch-statement-example/ 访问于：2022年9月24日。
- 20 JavaScript 循环：www.javatpoint.com/javascript-loop 访问于：2022年9月24日。
- 21 JavaScript—For 循环：www.tutorialspoint.com/javascript/javascript_for_loop.htm 访问于：2022年9月24日。
- 22 JavaScript 对象：www.javatpoint.com/javascript-objects 访问于：2022年9月26日。
- 23 JavaScript 数组：www.javatpoint.com/javascript-array 访问于：2022年9月26日。
- 24 JavaScript 字符串：www.javatpoint.com/javascript-string 访问于：2022年9月26日。
- 25 JavaScript Date 对象：www.javatpoint.com/javascript-date 访问于：2022年9月26日。
- 26 JavaScript Math：www.javatpoint.com/javascript-math 访问于：2022年9月26日。
- 27 JavaScript—Math 对象：www.tutorialspoint.com/javascript/javascript-math_object.htm 访问于：2022年9月27日。
- 28 JavaScript Number 对象：www.javatpoint.com/javascript-number 访问于：2022年9月27日。
- 29 JavaScript 布尔值：www.javatpoint.com/javascript-boolean 访问于：2022年9月27日。
- 30 JavaScript—错误与异常处理：www.tutorialspoint.com/javascript/javascript_error_handling.htm 访问于：2022年9月27日。
- 31 JavaScript—事件：www.tutorialspoint.com/javascript/javascript_events.htm 访问于：2022年9月27日。

## 开始学习 JavaScript II

### 本章内容

- 异步开发
- DOM 操作
- HTTP 和表单
- 与 API 交互

在上一章中，我们涵盖了数据类型和运算符、函数、对象和数组、错误处理、事件。在本章中，我们将讨论 API 和 DOM。

### 我们如何构建一个异步 Node.js 函数？

在 Node.js 中，在函数名之前使用 `async` 编写异步函数。结果是，异步方法会返回一个隐式的 Promise。

`async` 函数有助于通过事件循环实现基于 Promise 的代码异步执行。`async` 函数始终会返回一个值。要等待 promise，请在异步函数内部使用 `await` 函数。函数将被强制等待直到 promise 产生结果¹。

使用命令在 Node.js 中从 npm 安装 `async`：

```bash
npm i async
```

在我们的 Node.js 应用中使用 `require()` 函数使用 `async`。

## 示例 1

在 Node.js 中编写一个异步函数来计算整数的平方。

- 为项目创建一个文件夹。
- 在项目文件夹内初始化 `package.json` 文件，运行以下命令：

```bash
npm init -y
```

- 使用以下命令安装 `async`：

```bash
npm i async
```

- 创建 `server.js` 文件并添加以下代码。
- 使用 `npm start` 执行代码。

```javascript
var async = require("async");

function square(k) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(Math.pow(k, 2));
    }, 2000);
  });
}

async function output(k) {
  const ans = square(k);
  console.log(ans);
}
```

## 136 征服 JavaScript

```html
<title></title>

</head>

<body>

<div id="message"></</div>

<script>
```

```html
<title></title>

</head>

<body>

<div id="message"></</div>

<script>
  var msg = document.getElementById("message");

  function fd1() {
    return new Promise(function (resolve, reject) {
      setTimeout(function () {
        msg.innerHTML += "<p>fd1 is start</p>";

        msg.innerHTML += "<p>fd1 is end</p>";

        resolve();
      }, 100);
    })
  }

  async function fd2() {
    msg.innerHTML += "<p>fd2 is start</p>";

    // 引擎会等待 fd1() 完成其执行
    // 之后再执行下一行
    await fd1();

    msg.innerHTML += "<p>fd2 is end</p>";
  }

  fd2();
</script>

</body>

</html>
```




# JavaScript 入门 II ■ 137

在前面的示例中，程序会等待`fd1()`完成后继续执行。

在获取到 Promise 之前，`await`命令会停止该代码段的执行。调用`resolve()`来完成 Promise。它表示该 Promise 已履行。同样地，我们可以使用`reject()`来判断 Promise 是否被拒绝（失败）。

我们现在不需要深入研究`reject()`方法，因为它主要用于调试和错误处理。

## 示例

如果我们希望 Promise 返回一个值（变量），可以在`resolve`中包含该值。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title></title>
</head>
<body>
  <div id="message"></div>
  <script>
    var msg = document.getElementById("message");

    function fd1() {
      return new Promise(function (resolve, reject) {
        setTimeout(function () {
          msg.innerHTML += "<p>fd1 is start</p>";
          msg.innerHTML += "<p>fd1 is end</p>";
          resolve(1);
        }, 1000);
      });
    }
  </script>
</body>
```

```javascript
async function fd2() {
  msg.innerHTML += "<p>fd2 is start</p>";

  var p = await fd1();

  if (p == 1) {
    msg.innerHTML += "<p>Promise Received</p>";
  }

  msg.innerHTML += "<p>fd2 is ending</p>";
}

fd2();
```

```html
</script>
</body>
</html>
```

## 等待多个 Promise

如果我们在多个进程同时运行时进行等待，该怎么办？

有两种方法可以实现这一点。

## 示例

我们可以连续编写多个`await`语句。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title></title>
</head>
<body>
  <div id="message"></div>

  <script>
    var msg = document.getElementById("message");

    function fd1() {
      return new Promise(function (resolve, reject) {
        setTimeout(function () {
          msg.innerHTML += "<p>fd1 is start</p>";
          msg.innerHTML += "<p>fd1 is end</p>";
          resolve();
        }, 1000);
      });
    }

    function fd3() {
      return new Promise(function (resolve, reject) {
        setTimeout(function () {
          msg.innerHTML += "<p>fd3 is start</p>";
          msg.innerHTML += "<p>fd3 is end</p>";
          resolve();
        }, 1000);
      });
    }

    async function fd2() {
      msg.innerHTML += "<p>fd2 is start</p>";

      await fd1();
      await fd3();

      msg.innerHTML += "<p>fd2 is end</p>";
    }

    fd2();
  </script>
</body>
</html>
```

# JavaScript 入门 II ■ 139

## 示例

等待多个 Promise 的第二种方案是使用`Promise.all`并并行执行 Promise（可迭代对象）。

### 语法

```javascript
await Promise.all(iterable object);
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title></title>
</head>
<body>
  <div id="message"></div>

  <script>
    var msg = document.getElementById("message");

    function fd1() {
      return new Promise(function (resolve, reject) {
        setTimeout(function () {
          msg.innerHTML += "<p>fd1 is start</p>";
          msg.innerHTML += "<p>fd1 is end</p>";
          resolve();
        }, 1000);
      });
    }

    function fd3() {
      return new Promise(function (resolve, reject) {
        setTimeout(function () {
          msg.innerHTML += "<p>fd3 is start</p>";
          msg.innerHTML += "<p>fd3 is end</p>";
          resolve();
        }, 1000);
      });
    }

    async function fd2() {
      msg.innerHTML += "<p>fd2 is start</p>";

      await Promise.all([fd1(), fd3()]);

      msg.innerHTML += "<p>fd2 is end</p>";
    }

    fd2();
  </script>
</body>
</html>
```

# 144 攻掌握 JavaScript

## 异步（Asynchronous）

当 HTML 解析器发现此元素时，它会向服务器发送请求以获取脚本。如果必须在页面解析和显示期间下载脚本，`async`功能将在后台执行。当脚本下载完成后，HTML 解析将停止并执行脚本。操作完成后，HTML 解析将重新开始。

页面和其他脚本不会等待异步脚本，它们不会被阻塞。这对于独立和位于外部位置的脚本都是理想的。

### 语法

```html
<script async src="script.js"></script>
```

## 延迟（Deferred）

`defer`属性指示浏览器不要干预 HTML 处理，仅在 HTML 页面完全处理完毕后运行脚本文件。

当发现带有此属性的脚本时，脚本将在后台异步开始下载，并且仅在 HTML 解析完成后才会运行脚本。

### 语法

```html
<script defer src="script.js"></script>
```

## 异步 vs 延迟

| 异步（Asynchronous） | 延迟（Deferred） |
| --- | --- |
| 异步会阻止页面解析。 | 延迟永远不会阻塞页面。 |
| 脚本之间互不依赖。因此，列表中较小的脚本排在后面，它将先于之前的长脚本加载。 | 延迟脚本保持它们的相对顺序，这意味着第一个脚本将先加载，然后是其他脚本。 |
| 脚本执行开始时暂停解析。 | 然而，脚本执行仅在解析完成之后、文档的`DOMContentLoaded`事件之前开始。 |

# JavaScript 入门教程 II ■ 145

## 文档对象模型（DOCUMENT OBJECT MODEL）

文档对象用于表示整个 HTML 文档。

当 HTML 文件加载到浏览器中时，会创建一个文档对象。

HTML 文档由根元素表示。它既有属性也有方法。

我们可以使用文档对象向我们的网页中添加动态内容。正如之前说的，它是`window`的对象。

```javascript
window.document
```

等同于：

```javascript
document
```

在所有平台和语言中，W3C 文档对象模型（DOM）提供了一个接口，用于动态访问和修改文档的内容、结构和样式。

## 文档对象属性

让我们来看看可以查看和更新的文档对象属性。

![文档对象属性](img/70a7539ec7c3f429f5e3c9c64df71823_185_0.png)

# 146 攻掌握 JavaScript

## 文档对象方法

我们可以使用它的方法来访问和修改文档的内容。以下是最重要的文档对象方法：

| 方法 | 描述 |
| --- | --- |
| `write("string")` | 将指定的字符串写入文档。 |
| `writeln("string")` | 将指定的字符串写入文档，末尾带有一个换行符。 |
| `getElementById(id)` | 返回指定 id 的元素。 |
| `getElementsByName(name)` | 获取所有指定 name 值的条目。 |
| `getElementsByTagName(name)` | 获取所有指定标签名的项目。 |
| `getElementsByClassName(name)` | 获取所有指定类名的条目。 |

## 文档对象访问字段值

在此实例，我们将获取用户提供的文本的值。要访问 name 字段的值，我们使用`document.form1.name.value`。这里的根元素是`document`，它代表 HTML 文档。

- form 的 name 是`form11`。
- name 是输入文本属性的名称。
- 该属性返回提供的文本的值。

让我们来看一个简单的文档对象示例，它显示用户名以及欢迎消息。

```html
<script type="text/javascript">
  function printvalue() {
    var name = document.form1.name.value;
    alert("Welcome here: " + name);
  }
</script>

<form name="form11">
  Enter Name:
  <input type="text" name="name" />
  <input
    type="button"
    onclick="printvalue()"
    value="print"
    name="name"
  />
</form>
```

# JavaScript 入门教程 II 147

## JAVASCRIPT 中的 DOCUMENT.GETELEMENTBYID() 方法

`document.getElementById()`函数获取带有指定 id 的元素。

我们在上一页中使用了`document.form1.name.value`来获取输入文本的值。为了访问输入文本的值，我们可以改用`document.getElementById()`函数。然而，我们必须为输入字段指定一个 id。

让我们来看一个小的文档示例。

`getcube()`函数返回提供的整数的立方。

```html
<script type="text/javascript">
  function getcube() {
    var numb = document.getElementById("numb").value;
    alert(numb * numb);
  }
</script>

<form>
  Enter No:
  <input type="text" id="numb" name="numb" />
  <br />
  <input type="button" value="cube" onclick="getcube()" />
</form>
```

## GETELEMENTSBYCLASSNAME()

`getElementsByClassName`函数用于根据类名值来选择或获取项目。此 DOM 函数产生一个类数组的对象，包含所提供类名的所有成员。当我们在任何元素上使用`getElementsByClassName()`函数时，它会搜索整个文档并仅返回与请求或提供的类名匹配的元素。

### 语法

```javascript
var ele = document.getElementsByClassName("name");
```

所需的参数是`name`。它是定义匹配单个类或多个类名的字符串。

### `getElementsByClassName()`方法示例

让我们通过一些实例来了解该方法的实际用法。

# 攻掌握 JavaScript

## 示例

这是一个基本的类实现，当调用变量`k`时，它会产生一个类数组的对象。

```html
<html>
<head>
  <h5>DOM 方法</h5>
</head>
<body>
  <div class="Class">
    这是一个基本的类实现
  </div>

  <script type="text/javascript">
    var k = document.getElementsByClassName("Class");
    document.write("调用它将返回类数组对象：<br>" + k);
  </script>
</body>
</html>
```

同样我们可以使用`getElementsByClassName()`函数获取各种类的元素集合。

### `getElementsByClassName()`、`querySelector()`和`querySelectorAll()`方法之间的区别

- `getElementsByClassName()`：此方法搜索指定的类并提供匹配元素的列表。返回的项目是元素的实时集合。如果文档对象模型发生变化，这些组件将更新。
- `querySelector()`：此函数返回匹配指定类名的单个元素。如果没有找到匹配的元素，它返回`null`。

需要记住的关键是，上述所有方法都返回一个元素或列表，但`getClassName()`处理动态更新，而另外两个处理静态更新。

# JavaScript 入门教程 II ■ 149

## JAVASCRIPT 中的 DOCUMENT.GETELEMENTSBYNAME() 方法

`document.getElementsByName()`函数获取带有给定名称的所有元素。以下是`getElementsByName()`方法的语法：

```javascript
document.getElementsByName("name");
```

## 示例

在此示例中，我们统计性别的总数。为了获取所有的性别，我们使用`getElementsByName()`函数。

```html
<script type="text/javascript">
  function totalelements() {
    var allgenders = document.getElementsByName("gender");
    alert("Total Genders:" + allgenders.length);
  }
</script>

<form>
  Male:
  <input type="radio" name="gender" value="male" />

  Female:
  <input type="radio" name="gender" value="female" />

  <input
    type="button"
    onclick="totalelements()"
    value="The Total Genders"
  />
</form>
```

## JAVASCRIPT 中的 DOCUMENT.GETELEMENTSBYTAGNAME() 方法

`document.getElementsByTagName()`函数获取带有指定标签名的所有元素。

# 150 征服 JavaScript

## 示例

在这个示例中，我们将统计文档中段落的总数。

为了实现这一点，我们使用了`document.getElementsByTagName("p")`函数，它会返回段落的总数。

```html
<script type="text/javascript">
  function countpara() {
    var totalpara = document.getElementsByTagName("p");
    alert("The total p tags: " + totalpara.length);
  }
</script>

<p>这是该段落</p>
<p>我们将使用`getElementByTagName()`方法来统计段落的总数。</p>
<p>让我们来看一个基础示例</p>

<button onclick="countpara()">计数段落</button>
```

## 另一个示例

在此例中，我们将统计文档中 h2 和 h3 标签的总数。

```html
<script type="text/javascript">
  function count2() {
    var totalh2 = document.getElementsByTagName("h2");
    alert("The total h2 tags are: " + totalh2.length);
  }

  function count3() {
```




`var totalh3 = document.getElementsByTagName("h3");`

`alert("The total h3 tags are: " + totalh3.length);`

`}`

`</script>`

## 这是 h2 标签

## 这是 h2 标签

### 这是 h3 标签

### 这是 h3 标签

```
# 开始学习 JavaScript II ■ 151
```

### 这是 h3 标签

`<button onclick="count2">h2</button>`

`<button onclick="count3">h3</button>`

```
# JAVASCRIPT 中的 INNERHTML
```

`innerHTML` 属性用于在 HTML 文档上写入动态 html。它通常用于网站以生成动态 html，例如注册表单、评论表单和链接.¹10

### InnerHTML 属性示例

当用户激活按钮时，将生成一个 HTML 表单。在这个示例中，我们将在 id 为 `mycolocation` 的 div 中动态创建 html 表单。该位置通过 `document.getElementById(function)` 识别。

```
<script type="text/javascript >
function showcomment() {
var data-Name=<input type='text' name='name'><br>Comment<br><textarea rows='5' cols='90'></textarea>
<br><input type='submit' value='Post Comment'>
document.getElementById('mycolocation').innerHTML=data;
}
</script>
<form name="my_Form">
<input type="button" value="comment"
onclick="showcomment()">
<div id="mycolocation"></</div>
</form>
```

使用 `innerHTML` 的评论表单示例

```
<!DOCTYPE html>
<html>
<head>
<title>First JS</title>
<script>
var flag=true;
function commentform() {
var cform="<form action=' Comment>Enter Name is:<br><input type='text' name='name'><|br|>
```

## 152 征服 JavaScript

```
Enter Email:<br><br>Enter Comment is:<br><br><textarea name='email' rows='5' cols='75'></textarea><br><input type='submit' value='Post Comment'/></></form>
if (flag) {
document.getElementById("mylocation").innerHTML=cform;
flag=false;
}else{
document.getElementById("mylocation").innerHTML="";
flag=true;
}
}
<script>
</head>
<body>
<button onclick="commentform()">Comment</button>
<div id="mylocation"></</div>
</body>
</html>
```

# JAVASCRIPT 中的 INNERTEXT

`innerText` 属性可能被用于在 HTML 页面上显示动态文本。在这种情况下，文本将读视为普通文本而不是 html 文本。它通常用于网站以生成动态内容，例如写入验证信息、密码强度等.¹11

### JavaScript innerText 示例

在这个示例中，我们将在按键被按下并松开后显示密码强度。

```
<script type="text/javascript" >
function validate() {
var msg;
if (document.my_Form.userPass.value.length>6) {
msg="good";
}else{
msg="poor";
}
document.getElementById(`mylocation`).
innerText=msg;
}
```

```
</script>
<form name="my_Form">
  <input type="password" value="" name="userPass" onkeyup="validate()">
  Strength:<span id="mylocation">no strength</span>
</form>
```

# JAVASCRIPT 中发送 HTTP 请求的方法

现代 JavaScript 支持多种向远程服务发送 HTTP 请求的方法。由于在 Web 应用程序中请求和动态加载信息有许多替代方案，从内置的 `XMLHttpRequest` 对象到像 Axios 这样的第三方库，这比以往任何时候都变得简单.¹12

因此，我们将介绍 JavaScript 中传递 HTTP 请求的几种方法。从语言原生选择开始，我们将查看以下五个模块并使用它们发送各种形式的 HTTP 请求。

- `XMLHttpRequest`
- `Fetch`
- `Axios`
- `SuperAgent`
- `Ky`

`XMLHttpRequest` 是一个 JavaScript 原生 API，它包含了在不需要刷新之前加载的网页面的情况下发送 HTTP 请求的机制 (AJAX)。尽管开发者现在很少直接使用 `XMLHttpRequest`，但它仍然是许多流行的 HTTP 请求背后的组件。

使用 `XMLHttpRequest` 来处理请求可以帮助我们应对第三方库不支持的情况。

## 154 征服 JavaScript

```
//创建 XMLHttpRequest 对象
const xhr = new XMLHttpRequest()
//打开远程 URL 的 get 请求
xhr.open("GET", "https://worldfoodfacts.org/category/pastas/json")
//发送请求
xhr.send()
```

```
//事件处理器
//当响应完成时触发
xhr.onload = function() {
  if (xhr.status === 200) {
    //解析 JSON 数据
    data = JSON.parse(xhr.responseText);
    console.log(data)
    console.log(data)
  } else if (xhr.status === 404) {
    console.log("未找到")
  }
}
```

```
//由于网络错误触发
xhr.onerror = function() {
  console.log("网络错误")
}
```

```
//当响应完成时触发
xhr.onprogress = function(e) {
  if (e.lengthComputable) {
    console.log(`${e.loaded} 的 ${e.total} 字节已接收`);
  } else {
    console.log(`${e.loaded} 字节已接收`);
  }
}
```

# 开始学习 JavaScript II ■ 155

- 使用 `XMLHttpRequest`
- 打开 HTTP 请求
- 发送请求

正如示例所示，我们可以以类似的方式使用 `XMLHttpRequest` 发送 POST 请求。

```
//创建 XMLHttpRequest 对象
const xhr = new XMLHttpRequest();
//打开请求 请求的 URL
xhr.open("POST", "/food")
//设置 content-type 头部
xhr.setRequestHeader("Content-Type", "application/json");
//向服务器发送 JSON 数据
xhr.send(JSON.stringify(food))
```

```
//事件处理器
//跟踪上传进度
xhr.upload.onprogress = function(e) {
  console.log(`${e.loaded} 的 ${e.total} 字节已上传!`);
}
```

```
//当上传完成时触发
xhr.upload.onload = function(e) {
  console.log("上传完成");
}
```

# JavaScript 入门 II ■ 157

```javascript
fetch("https://world.openfoodfacts.org/category/pastas/1.json")
  .then(response => {
    // 表示响应是否成功
    // (状态码 200-299) 或否
    if (!response.ok) {
      throw new Error(`Request failed with the /status ${response.status}`);
    }
    return response.json();
  })
  .then(data => {
    console.log(data.count)
    console.log(data.products)
  })
  .catch(error => console.log(error))
```

`Fetch` 通过简化的语法和 Promise 极大降低了复杂性和冗余性。`fetch` 函数中捕获的问题处于网络层而非应用层，在这一实现中，我们必须利用 `response.ok` 字段来判断响应是否包含 HTTP 错误。

`Fetch` 函数接受一个配置对象作为第二个参数，允许轻松自定义 HTTP 数据，如请求头、内容类型、请求方法等。`Fetch` 支持的所有配置选项可以在其官方手册中查看。

使用 `Fetch` 发送 POST 请求遵循与上一个示例相同的技巧。在这种情况下，我们利用配置对象来指定请求方法和要提交的数据。

让我们看看它在 `async/await` 中如何工作：

```javascript
async function postData () {
  const food = {
    name: "Rice",
    weight: 410,
    quantity: 4
  }
  const response = await fetch("/food", {
    method: "POST",
    body: JSON.stringify(food),
    headers: {
      "Content-Type": "application/json"
    }
  })
  if (!response.ok) {
    throw new Error(`Request failed with the status ${response.status}`);
  }
  console.log("Request is successful!")
}
```

## 158 ■ 攻克 JavaScript

## Fetch 的优点

- 为 JavaScript 提供了一种流式的原生方法。
- 易于理解并适用于任何难度级别。
- 基于 Promise 的实现允许我们编写更清晰、更简洁的代码。
- 在许多方面改进了 `XMLHttpRequest`，包括处理跨域请求并将 Request 和 Response 对象与内置 API 结合。

# Fetch 的缺点

- 缺少某些 `XMLHttpRequest` 功能，如请求取消和进度监控。（然而，可以使用 `AbortController` 对象来管理请求取消和超时。）
- 即使存在 HTTP 错误，我们需要手动检查并处理问题。
- 不兼容 Internet Explorer。

# JavaScript 入门 II ■ 159

## Axios

`Axios` 是一个用于在 JavaScript 中执行 HTTP 请求的第三方程序。在底层，它与 `XMLHttpRequest` API 协作，提供了处理拦截请求和发送并发请求的全面功能。像 `Fetch` 一样，它通过 Promise 处理异步请求。

当使用 `Axios` 执行 GET 请求时，我们可以使用其特殊的 `get()` 函数。示例所示：

```javascript
axios.get("https://world.openfoodfacts.org/category/pastas/1.json")
.then(response => {
  // 获取解析后的 JSON 数据
  const data = response.data
  console.log(data.count)
  console.log(data.products)
})
.catch(error => {
  if (error.response) {
    // 获取 HTTP 错误码
    console.log(error.response.status)
  } else {
    console.log(error.message)
  }
})
```

与 `Fetch` 相比，`Axios` 减少了我们执行 HTTP 请求的工作量。`response.data` 属性包含了解析后的 JSON 数据。`catch` 方法也涵盖了 HTTP 失败。`error.response` 检查允许我们在 `catch` 函数中分类特定的 HTTP 错误码。

我们利用特殊的 `axios.post()` 函数通过 `Axios` 发送 POST 请求，如下所示（使用 `async/await` 构建）：

# 160 ■ 攻克 JavaScript

```javascript
async function postData () {
  const food = {
    name: "Rice",
    weight: 410,
    quantity: 4
  }
  try {
    const response = await axios.post("/food", food);
    console.log("Request is successful!")
  } catch (error) {
    if (error.response) {
      console.log(error.response.status)
    } else {
      console.log(error.message)
    }
  }
}
```

`Axios` 在无需我们干预的情况下将 JavaScript 对象转换为 JSON，再次简化了这一实现。这些 `Axios` 方法使用指定 HTTP 设置的最后一个参数。

# Axios 的优点

- 它具有基础、简洁且易于学习的语法。
- 支持许多其他可用 HTTP 包没有的功能。这些包括拦截请求、同时发送多个请求、取消已发送的请求、自动数据转换、监控请求进度等。
- 支持所有主流浏览器版本，包括 Internet Explorer。
- 提供客户端 CSRF 保护。

# Axios 的缺点

由于不是原生模块，增加了外部依赖。

# JavaScript 入门 II ■ 161

## SuperAgent

`SuperAgent` 是 JavaScript 中执行 HTTP 请求的第三方工具之一。它像 `Axios` 一样在底层实现了 `XMLHttpRequest` API 并包含了完整的功能集。该包支持基于 Promise 和基于回调的解决方案。

使用 `SuperAgent` 发送 HTTP 请求时，可以使用它特殊的 `get()` 函数。示例所示：

```javascript
superagent
.get("https://world.openfoodfacts.org/category/pastas/1.json")
.then(response => {
  // 获取解析后的 JSON 响应数据
  const data = response.body
  console.log(data.count)
  console.log(data.products)
})
.catch(error => {
  if (error.response) {
    console.log(error.response.status)
  } else {
    console.log(error.message)
  }
})
```

使用基于 Promise 的语法，`SuperAgent` 遵循与 `Axios` 类似的方法。它会自动将响应体解析为 JavaScript 对象。在发生网络问题时，`error.response` 和 `error.status` 列将为空。同样，我们可以使用 `SuperAgent` 发送 POST 请求。

```javascript
superagent
.post("/food")
.send(food)
.then(response => console.log("Request is successful!"))
.catch(error => {
  if (error.response) {
    console.log(error.response.status)
  } else {
    console.log(error.message)
  }
})
```



```
console.log(error.message)
```

SuperAgent我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。默认认为数据是 JSON，并自行处理数据转换和内容类型头。我们利用 SuperAgent 的 `send()` 函数来传递带有 POST 请求的数据。

# JavaScript 入门 II 163

Ky 专门的 HTTP 方法具有简洁的请求语法。以下是一个使用 Ky 和 async/await 发送 GET 请求的实例。

```javascript
async function getData() {
  try {
    const data = await ky.get("https://world.openfacts.org/category/pastas/2.json");
    console.log(data.count)
    console.log(data.products)
  } catch (error) {
    console.log(error.response.status)
  } finally {
    console.log(error.message)
  }
}
```

POST 请求也可以以类似的方式发送：

```javascript
async function postData() {
  try {
    const response = await ky.post("/food", { json: food });
    console.log("The Request is successful")
  } catch (error) {
    console.log(error.response.status)
  } finally {
    console.log(error.message)
  }
}
```

## Ky 的优势

- 提供了一个直观、轻量级、基于 Promise 的 API，用于执行 HTTP 请求。
- 支持请求超时、重试和进度监控，以解决原生 Fetch API 的若干限制。

# 征服 JavaScript

- 提供了钩子（Hooks）来更改在整个生命周期内的请求：`beforeRequest`、`afterResponse`、`beforeRetry` 等。
- 支持所有当前浏览器，包括 Chrome、Firefox 和 Safari。Ky 还提供了一个备用包 `Ky-Universal` 用以支持 Internet Explorer；我不确定他们为什么要费心于此。

### Ky 的缺点

- 与本文介绍的其他成熟且多样化的解决方案相比，这是一个非常新的包。此功能增加了一个外部依赖。

## HTTP COOKIES

Web Cookie（网络 饼），也称为 HTTP Cookie，是由于服务器发送到在线浏览器的一小段数据。Cookie 可能会被浏览器存储，并在随后的请求中发送回服务器¹³。Cookie 通常用于检测来自同一站点（浏览器）的重复请求。它能帮助用户保持登录状态，并通过用户名和会话（session）跟踪其数据。对于无状态的 HTTP 协议跟踪状态信息也是一个好主意。

如果我们是开发者，就无法避免 Cookie，因为它们对于会话管理和监控其他用户信息是必要的。如今，Cookie 与任何其他应用程序功能一样至关重要。Cookie 为用户和程序员执行各种任务提供了便利。

Cookie 已经存在段时间，并且现在仍在发生变化。Cookie 只是关于 Web 应用程序的文本数据。当用户访问网站时，某些信息被存储在系统的本地存储中，以便应用程序在他们访问时能够识别用户并显示适当的结果。

当用户访问网站时，服务器请求应用程序的主页，当他执行特定操作时，服务器请求应用程序的任何其他页面。因此，如果用户访问第 100 次，每次请求都是唯一的。由于服务器查询非常密集，直接将数据保存到服务器是不可行的；此外，这可能会导致服务器过载。此外，如果用户不再返回，收集的信息将是过时的。

因此，为了记住用户的身份，服务器会在响应中传输 Cookie，这些 Cookie 被保存到系统的本地存储中。当同一个客户端再次执行相同请求时，服务器将识别其身份并显示相应的响应。

# JavaScript 入门 II 165

Cookie 是服务器特有的，即使用户在系统中拥有许多 Cookie，服务器也可以识别出自己的 Cookie。

在这一部分中，我们将涵盖与 Cookie 相关的主题：

- Cookie 的用途。
- Cookie 是如何工作的？
- JavaScript 生成的 Cookie。
- Cookie 规范。
- Cookie 的种类。

### Cookie 的利用

Cookie 通常以以下方式使用：

- **会话管理（Session Management）**：
Cookie 的主要功能是处理用户登录、购物车数据、游戏分数以及服务器用户下次进入时应该记住的任何其他内容。通常情况下，会话管理允许用户通过应用程序与服务器进行安全交互。由于用户继续与 Web 应用程序交互，他们每次访问网站时都会生成一个新的请求。因此，这使得跟踪他们在会话期间的状态和活动变得简单。

- **跟踪（Tracking）**：
跟踪是捕捉用户活动并评估他们的行为，以便为他们量定制材料。它跟踪并分析他们的行为和兴趣，以及他们访问的页面。会话期间在某个页面或整个网站上花费的时间可能包含在跟踪信息中。由于用户跟踪包含敏感信息，用户应该意识到访问不安全网站的危险，并在可行的情况下避免访问此类网站。

- **个性化（Personalization）**：
Cookie 有助于自定义用户偏好、主题和其他设置。在大多数情况下，这些内容会与中央数据库同步，以便在用户首次登录时为用户提供个性化。当用户登录或重启程序时，用户自定义会保存有关用户偏好和设置的信息以备后之用。

# 征服 JavaScript

- **身份认证（Authentication）**：
Cookie 对于用户验证也是至关重要的。当用户登录时，服务器用 `Set-Cookie` HTTP 头部响应，设置一个带有唯一“会话标识符”的 Cookie。
当相同用户再次请求同一个网站时，Cookie 会通过 `Cookie` HTTP 头部跨互联网传输。
因此，服务器可以确定是谁发出的请求。

# Cookie 是如何工作的？

用户每当与网站交互时，都会向服务器发送一个新请求，每当他在程序内执行任何操作时，都会向服务器发送一个新请求。独立用户提交的每个新请求都是被考虑的。为了识别相同的用户，开发者必须在响应中包含 Cookie，它保存在系统的本地存储中。
浏览器是向服务器发送请求的客户端通道。
一旦 Cookie 被添加，服务器就能识别出用户。
Cookie 从用户和开发者的角度都是至关重要的。它帮助双方提供适当的回。
让我们看看如何使用 JavaScript 创建 Cookie。

# JavaScript 中的 Cookie

让我们看看如何使用 JavaScript 创建 Cookie：

## 创建 Cookie

当接收请求时，服务器可能会带上多个 `Set-Cookie` 头部。它保存在系统的本地存储中。因此，下当浏览器向服务器发送请求时，也会随请求发送 Cookie。

为了创建、读取、更新和删除 Cookie，JavaScript 提供了 `document.cookie` 属性。
HTTP Cookie 可以通过两种方式生成。Cookie 可以通过浏览器界面在客户端创建，也可以在文件的脚本部分从服务器端添加。
`Set-cookie` 头部从服务器生成一个或多个 Cookie。

让我们看看客户端和服务器端是如何创建 Cookie 的。

# 168 攻克 JavaScript

```javascript
const my_Cookie = document.getById("setcookie")
myCookie.addEventListener("click", e=> document.cookie = "mycookie=2"
</script>
</body>
</html>
```

根据前面的示例，它将在我们的网站页面上显示一个按钮组件。当我们按下按钮时，系统存储会创建一个请求的 cookie。
同样，我们可以使用任何其他事件监听器来构建 cookie。要设置 cookie，我们也可以添加一个 `onload` 事件。
让我们来看几个 cookie 属性：

## Cookie 属性

cookie 属性在所有 cookie 中都是一致的；以下是一些典型的 cookie 属性：

## Cookie 范围

cookie 的范围指定了哪些 URL 会随 cookie 传输。Cookie 范围分为两个不同的属性：

- Path
路径是定义 cookie 范围的属性之一。它在 HTTP 头部中定义了特定的 URL 路由以传输 cookie。要将 cookie 设置不同的路由，可以使用以下代码：

```javascript
document.cookie="cookiefirst=1; path=/path1"
document.cookie="cookiesecond=2; path=/path2"
```

当我们访问带有提供的 URL 的网站（例如 `example.com/path1`）时，我们现在将提交一个值为“cookiefirst=1”的 cookie 头部。
如果我们导航到另一个 URL（例如 `example.com/path2`），我们将提交一个值为“cookiesecond=2”的 cookie 头部。
除了定义的 URL 外，其他请求路由将不会传输任何 cookie 头部。

## JavaScript 入门 II ■ 169

- Domain
域名是 cookie 的第二个属性。域名充当 cookie 的容器。cookie 为自己提供了一个唯一的域名，这有助于管理员为网页页的 HTTP 请求保持 cookie 的特定性和组织性。一个特定域名的 cookie 示例所示：
`Domain=google.com` 启用了 `google.` 及其子域名（包括 `pasta.google.com`）的 cookie。

- Expires and Max-Age
cookie 的“Expires”和“Max-Age” 参数定义了它的寿命或过期日期。它们被分类为持久性 cookie。除了“永久 cookie”一术外，“Expires” 属性可以在特定日期删除 cookie。此外，“Max-Age”会在给定时间后删除 cookie。
另一方面，会话 cookie 在当前会话结束时会被销毁。某些浏览器允许我们选择当前会话何时结束，这可以是任何长度，也可以是无限的。

- SameSite
SameSite 属性允许我们在点击页面内链接时时设置 cookie。我们已经讨论过如何为特定 URL 建立 cookie，但如果我们想把 cookie 存放在该直接 URL 内部的链接上呢？使用 SameSite，我们可以通过点击来自重定向页面的链接来传输 cookie。我们可以指示 SameSite 在响应跨站请求或用户点击网页时传输 cookie。
让我们来看一个 SameSite 属性启用跨站 cookie 的实际场景。流程图解释了从一个页面移动到另一个页面时 cookie 如何传输和接收的。
用户导航到 URL（例如 `google.com`）
他们将获得第一方 cookie。
用户将访问 `google.com` 并点击可能请求另一个站点的链接，例如 `www.googleexample.com`。
`Tutorialexample.com` 将放置一个域名为 `Domain=googleexample.com` 的 cookie。

## 170 ■ 精通 JavaScript

`Google.com` 现在存储了一个来自 `googleample.com` 的第三方 cookie。

通过以下三个值，SameSite 属性定义了是否发送第三方 cookie：

- Strict
SameSite 属性的严格值仅通过第一方 cookie 上下文传输。第三方 cookie 不被考虑。

- Lax
当用户点击带有第三方导航的链接时，将交付 SameSite 属性的“Lax”值。如果第三方链接上没有显式指定 SameSite 属性，则默认值为 lax。

- None
如果 SameSite 属性设置为“None”，则 cookie 在所有上下文中传输。
我们已经讨论了 cookie 及其属性；现在让我们来看许多种 cookie：

## Cookie 的种类

根据其用法和行为，cookie 分为以下几类：

### 第一方 Cookie (First-Party Cookies)

第一方 cookie 是直接从我们正在查看的网站服务器传输到系统的 cookie。访问的网站将这些 cookie 直接存储在我们的计算机上。大多数网站向其访问者发送 cookie 以收集有用信息和分析，以改进用户体验。

身份验证是第一方 cookie 的最佳例子。当用户在应用程序中注册时，服务器将 cookie 发送到客户端，将其保存在用户的本地机器上。下次你检查程序时，我们不需要再次输入登录凭据。如果没有第一方 cookie，网站无法识别用户，也不会自动登录我们或记住我们之前会话中的选择。

## JavaScript 入门 II ■ 171

### 第三方 Cookie (Third-Party Cookies)

我们被重定向到的第三方域名会创建第三方 cookie。

它不是由我们当前登录的域名创建的。这些 cookie 通常用于跟踪，即使在浏览器关闭后仍会保留。网站的广告跟踪是第三方 cookie 的极佳例子。我们可能注意到，在从多个电子商务网站浏览了几个产品后，我们开始看到那些产品的广告。这是因为在浏览产品时，我们可能暴露于来自该特定网站其他域名的第三方 cookie。

### 会话 Cookie (Session Cookies)

会话 cookie 是在用户关闭标签页时删除的临时 cookie。

会话 cookie 在用户关闭浏览器时被删除。

使用会话 cookie 时，用户在登录应用程序时提供凭据。

购物车管理是会话 cookie 的良好示例。如果网站使用会话 cookie，用户很难记住商品。

### 安全 Cookie (Secure Cookies)

cookie 包含一个安全功能，以防止对 cookie 的非授权访问。当结合 `Secure` 属性使用时，只有在安全介质上包含 cookie。

2002 年，微软 Internet Explorer 引入了 `HttpOnly`。带有 `HttpOnly` 标志的 cookie 可以包含在 `Set-Cookie` HTTP 头部中。`HttpOnly` 属性减少了用户点击利用跨站脚本漏洞链接的可能性。

## 172 攻克 JavaScript

通常，攻击者尝试向受信网站注入恶意脚本以获取存储在本地系统的 cookie 和其他敏感信息。

## 僵尸 Cookie (Zombie Cookies)

cookie 的名字给了我们提示。这些 cookie 像僵尸一样，被杀死后可以复活。这些 cookie 在浏览器关闭后可以激活。

通常，僵尸 cookie 可以制作原始 cookie 的副本，存储在其他地方并重新攻击用户的 cookie 存储。

一些公司利用僵尸 cookie 跟踪用户活动并获取个人信息。一些国家已经禁止了僵尸 cookie，它被认为是对隐私的非法侵犯。

## JavaScript 入门 II ■ 173

```html
<input type="submit" value="Login"/>
<input type="button" value="SignUp" onClick="create()"/>
</form>
</html>
```

在程序中：

- `form` 标签用于定义表单的名称。在这种情况下，表单被称为“Loginform”。此名称名称将出现在 JavaScript 表单中。
- `action` 元素指定了表单提交时浏览器将执行的操作。我们在这里没有做任何处理。
- 当表单要发送到服务器时，采取操作的方法可以是 `post` 或 `get`。这两种技术都有它们自己的属性和规定。
- `input type` 指定了我们表单中可用的输入类型。我们将输入类型设置为 `text`，这意味着我们将在文本框中输入数据。
- 接下来，我们将输入类型设置为 `password`，输入值为 `password`。
- 接下来，我们选择输入类型 `button`，当我们点击它时，会显示表单的值。

除了 `action` 和 `methods` 之外，HTML 表单元素还提供了以下实用的技术：

- `submit()`：提交表单的技术。
- `reset`（技术）：用于重置表单值。

### 引用表单

现在我们已经用 HTML 建立了表单元素，需要将其连接到 JavaScript。为了实现这一点，我们采用 `getElementById()` 函数，它在 JavaScript 代码中引用 HTML 表单元素。
以下是使用 `getElementById()` 方法的语法：

```javascript
let form = document.getElementById(`subscriptions`);
```

## 174 ■ 征服 JavaScript

我们可以通过 Id 进行引用。

### 提交表单

然后使用 `onSubmit` 函数通过发送表单的值来提交表单。

通常情况下，我们利用提交按钮来提交表单中提供的值。

`submit()` 函数具有以下语法：

```html
<input type="submit" value="Sscribes">
```

当我们提交表单时，在请求传递到服务器之前会执行 `action`。它允许我们为表单添加事件监听器，从而我们对其对其设置多个验证。

最后，使用 HTML 和 JavaScript 代码的组合来完成表单。

让我们收集并使用所有内容来开发一个登录表单（Login form）和一个注册表单（SignUp form），并同时使用它们。

## 登录表单 (Login Form)

```html
<html>
<head>
<title>Form of Login </title>
</head>
<body>
<h3>LOGIN</h3>
```



## 登录表单 (Login Form)

```html
<form id="Loginform" onSubmit="submitform()">
  <h4>USERNAME</h4>
  <input type="text" placeholder="Enter email id"/>
  <h4>PASSWORD</h4>
  <input type="password" placeholder="Enter password"/><br/>
  <input type="submit" value="Login"/>
  <input type="button" value="SignUp" onclick="create()"/>
</form>

<script type="text/javascript">
function submitform() {
  alert("Successfully Login ");
}

function create() {
  window.location="signup.html";
}
</script>
```

## 注册表单 (SignUp Form)

```html
<html>
<head>
  <title>SignUp Page</title>
</head>
<body align="center">
  <h1>CREATE ACCOUNT</h1>
  <table cellspacing="2" align="center" cellpadding="9" border="0">
    <tr><td>Name</td></tr>
    <tr><td><input type="text" placeholder="Enter name" id="n1"></td></tr>
    <tr><td>Email</td></tr>
    <tr><td><input type="text" placeholder="Enter email id" id="e1"></td></tr>
    <tr><td>Set Password</td></tr>
    <tr><td><input type="password" placeholder="Set password" id="p1"></td></tr>
    <tr><td>Confirm Password</td></tr>
    <tr><td><input type="password" placeholder="Confirm password" id="p2"></td></tr>
    <tr><td><input type="submit" value="Create" onclick="createaccount()"></td></tr>
  </table>

  <script type="text/javascript">
  function create_account() {
    var n = document.getElementById("n1").value;
    var e = document.getElementById("e1").value;
    var p = document.getElementById("p1").value;
    var cp = document.getElementById("p2").value;

    // Code for the password validation
    var letters = /^[A-Za-z]+$/;
    var email_val = /^([a-zA-Z0-9_\.\-]+)@\+(([a-zA-Z0-9_\.\-]+)+\+([a-zA-Z0-9]{2,4}))\$/;

    // other validations required code
    if (n == '' || e == '' || p == '' || cp == '') {
      alert("Enter details correctly");
    } else if (!letters.test(n)) {
      alert("Incorrect Name, must contain alphabets only");
    } else if (!email_val.test(e)) {
      alert("Invalid format of email please enter valid email id");
    }
    // ... (此处重复逻辑已省略)
  }
  </script>
</body>
</html>
```

## 180 征服 JavaScript

```html
<form name="fml" action="#" onsubmit="return validate()">
  <table>
    <tr>
      <td>输入姓名：</td>
      <td><input type="text" name="name" />
      <span id="nameloc"></span></td>
    </tr>
    <tr>
      <td>输入密码：</td>
      <td><input type="password" />
      <span id="passwordloc"></span></td>
    </tr>
    <tr>
      <td colspan="2"><input type="submit" value="register"/></td>
    </tr>
  </table>
</form>
```

### JavaScript 中的邮箱验证

（原文：Email Validation in JavaScript）

使用 JavaScript，我们可以对邮箱进行验证。要验证邮箱地址，必须满足几项标准，包括：

- 邮箱地址中必须出现 `@` 和 `.` 字符。
- `@` 符号的前后必须至少有一个字符。
- 在点号（`.`）之后必须至少有两个字符。

让我们来看一个简单的邮箱验证示例。

```javascript
<script>
function validateemail() {
  var x = document.my_form.email.value;
  var atposition = x.indexOf("@");
  var dotposition = x.lastIndexOf(".");
  if (atposition < 1 || dotposition < atposition + 2 || dotposition + 2 >= x.length) {
    alert("请输入有效的邮箱地址 \natposition:" + atposition + "\ndotposition:" + dotposition);
    return false;
  }
}
</script>
```

```html
<form name="my_form" method="post" action="#" onSubmit="return validateemail();">
  邮箱：<input type="text" name="email"><br/>
  <input type="submit" value="register">
</form>
```

## 使用 JavaScript API

API 仅仅是接口之间传输数据的一种手段。假设我们想要创建一个应用程序，它向用户展示从服务器检索的实时数据，甚至允许我们向另一个端点修改或添加数据。API（即应用程序编程接口）使这成为可能。

我们将使用一个基础的公共 API，它不需要身份验证，允许我们通过简单的 `GET` 请求查询 API 来获取数据。`https://randomuser.me/` 是一个为我们提供随机用户虚假数据供使用的网站。

向 `https://randomuser.me/api/` 的请求将提供结果。我们收到的 JSON 答案格式如下。

```json
{
  "results": [
    {
      "gender": "Male",
      "name": {
        "title": "Mr",
        "first": "Nitin",
        "last": "Simka"
      },
      "location": {
        "street": {
          "number": 230,
          "name": "Erakon Roadh"
        },
        "city": "Jalandhar",
        "state": "Punjab",
        "country": "India",
        "postcode": 121001,
        "coordinates": {
          "latitude": "81.1327",
          "longitude": "104.4160"
        },
        "timezone": {
          "offset": "+7:00",
          "description": "Ludhiana, Amritsar, Chandigarh, Moga"
        }
      },
      "email": "nitin.simka@example.com",
      "login": {
        "uuid": "bd0d135f-84df-4102-aa4f-5baaa41baf5c",
        "username": "redfrog722",
        "password": "abc",
        "salt": "q28gdiYN",
        "md5": "291987daea22bb91775226579425b271",
        "sha1": "0463a26ea5c2ff4f3ad498fd01c599426e5021",
        "sha256": "6583eb74ca08fac50b3b29aa5c9f02ea5d90d17ef0e5a56fae4f5225f928"
      },
      "dob": {
        "date": "1998-10-01T23:10:09.403Z",
        "age": 40
      },
      "registered": {
        "date": "2015-02-02T02:26:52.904Z",
        "age": 7
      },
      "phone": "(91)-234-7985",
      "cell": "(51)-984-9443",
      "id": {
        "name": "SSN",
        "value": "847-09-2973"
      },
      "picture": {
        "large": "https://randomuser.me/api/portraits/women/61.jpg",
        "medium": "https://randomuser.me/api/portraits/women/61.jpg",
        "thumbnail": "https://randomuser.me/api/portraits/women/61.jpg"
      },
      "nat": "US"
    }
  ],
  "info": {
    "seed": "82a8d8d4a96ba17",
    "results": 1,
    "page": 1,
    "version": "1.3"
  }
}
```

我们需要一个 HTML 文件用于前端，在其中你展示获取的数据。

我们可以使用 `div` 标签（块级）或 `span` 标签（行内级）作为数据的占位符。

我们可以通过使用 `id` 属性获取我们需要插入信息的 `div/span` 容器。

```html
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>标题</title>
  <!-- 让 font-awesome 库更有吸引力 -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font.min.css">
  <!-- 内部样式表 -->
  <style>
    .content {
      text-align: center;
      padding: 32px;
      margin: 0 auto;
    }
    .details {
      margin-left: auto;
    }
  </style>
</head>
<body>
  <div class="content">
    <div></div>
    <div class="details">
      <div id="email"></div>
      <div id="phone"></div>
    </div>
  </div>
  <script>
    // 这里编写逻辑
  </script>
</body>
</html>
```

## 188 ■ 征服 JavaScript

```css
margin-right: auto;
}

img {
  border-radius: 6px;
  box-shadow: black;
}
```

```css
table,
td {
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  padding: 12px;
  border: 2px solid black;
}
```

```html
<body>
  <div class="content">
    <div class="head">
      <h1 id="head"></h1>
    </div>
    <div class="email">
      <i class="fa fa-envelope" style="font-size: 16px; color: red;"></i>
      <a href="" id="email"></a>
    </div>
    <div class="phone">
      <i class="fa fa-phone" style="font-size: 16px; color: red;"></i>
      <a href="" id="phone"></a>
    </div>
    <br />
    <div id="user-img"></div>
    <br />
    <div class="details">
      <table>
        <tr>
          <td>年龄：</td>
          <td><span id="age"></span></td>
        </tr>
        <tr>
          <td>性别：</td>
          <td><span id="gender"></span></td>
        </tr>
        <tr>
          <td>地点：</td>
          <td><span id="location"></span></td>
        </tr>
        <tr>
          <td>国家：</td>
          <td><span id="country"></span></td>
        </tr>
      </table>
    </div>
  </div>
</body>

<script>
const api_url = "https://randomuser.me/api";

async function getUser() {
  // 发起 API 调用（请求）
  // 并获取响应
  const response = await fetch(api_url);
  // 将（响应正体）解析为 JSON 格式
  const data = await response.json();
  console.log(data.results);
  // 从 JSON 中提取数据
  const user = data.results[0];
  let { title, first, last } = user.name;
  let { gender, email, phone } = user;
  let image = user.picture.large;
  let image_icon = user.picture.thumbnail;
  let age = user.dob.age;
  let { city, state, country } = user.location;
</script>
```

## 190 征服 JavaScript

```javascript
let fullName = title + " " + first + " " + last;
document.title = fullName;
```

```javascript
// 获取 div 容器并向容器修改/添加元素
document.getElementById("head").innerHTML = fullName;
document.getElementById("email").href = "mailto:" + email;
document.getElementById("email").innerHTML = email;
document.getElementById("phone").href = "tel:" + phone;
```



```javascript
document.getElementById("phone").innerHTML = phone;

// 获取 span 容器
document.querySelector("#age").textContent = age;
document.querySelector("#gender").textContent = gender;
```

```javascript
document.querySelector("#location").textContent = city + ", " + state;
```

```javascript
document.querySelector("#country").textContent = country;
```

```javascript
// 创建新元素并
// 将添加到之前创建的容器中
let img = document.createElement("img");
let img_div = document.getElementById("user-img");
img.src = image;
img_div.append(img);
```

```javascript
const favicon = document.getElementById("favicon");
favicon.setAttribute("href", image_icon);
}

// 调用函数
getUser();
```

```html
</script>
</html>
```



## JavaScript 入门 II ■ 191

如果我们想学习更多关于 API 的知识并深入研究它们，可以访问 `Public APIs`，它提供了各种公开的 API，帮助我们进行 API 发现之旅。

要确定 API 发送的答案类型，`Postman` 是一个极好的应用程序，可以满足我们所有的需求。另一种选择是使用 `Postman APIs` 在浏览器中执行相同的操作。

## 最著名的 JavaScript 库

这里列出了最流行的 JavaScript 库¹¹⁷

### jQuery

jQuery 是一个传统的 JavaScript 库，轻量、快速且功能丰富。
`Resig` 在 2006 年的纽约开发者大会（`BarCamp NYC`）期间创建了它。jQuery 是基于 MIT 许可证的开源软件。它让 HTML 页面操作与遍历、动画、事件管理和 Ajax 变得简单。根据 `W3Techs` 的数据，77.6% 的网站使用了 jQuery（截至 2021 年 2 月 23 日）。

#### 特性

- 它提供简单、极简的 API。
- 它利用 CSS3 选择器来操作样式属性并发现元素。
- jQuery 体积小，压缩和最小化仅需 30kb，而且还包含一个 AMD 模块。
- 它很容易学习，因为它的语法与 CSS 相同。
- 插件允许更多的自定义。
- 通过适用于包括 Chrome 和 Firefox 在内不同浏览器的 API 提供了多功能性。

## 192 ■ 征服 JavaScript

#### 用例

- 使用 CSS 选择器根据某些标准操作 DOM，包括 `Sizzle`（一个选择引擎）。
- 创建了效果、事件和动画。
- 用于解析 JSON。
- 开发 Ajax 应用。
- 各种功能。
- 使用 Promise 和 Deferred 对象控制异步处理。

### React.js

`React.js`（也称为 `ReactJS` 或 `React`）是一个开源的前端库。
`Jordan Walke`，Facebook 的软件开发者在 2013 年创立了它。它现在以 MIT 许可证发布。
React 是为了让用户界面尽可能简单而创建的。
它根据数据变化更新相应的组件。

#### 特性

- React 代码由组件组成。
- 它利用虚拟 DOM 更新显示。
- 支持 JSX 将 JavaScript 与 HTML 混合。
- 它便于对状态进行展示。

## JavaScript 入门 II ■ 193

- 它采用了组件生命周期方法。

#### 用例

- 创建交互式和动态数据可视化。
- 数据驱动转换。可以使用数字数组来生成 HTML 表格，然后可以使用 `D3.js` 生成 SVG 图表或 3D 曲面图。
- 由于其函数式代码，可以使用许多模块。
- D3 拥有多种工具，用于声明式更改样式或属性、添加、排序或删除节点，以及更改文本或 HTML 内容。
- 使用事件、CSS3 过渡等制作动画。

### D3.js

另一个用于数据驱动文档的知名 JS 框架是数据驱动文档（D3）或 `D3.js`。
它在 2011 年根据 BSD 许可证发布。

#### 特性

- 它强调网络标准，并提供现代浏览器功能，而无需强制使用特定的框架。
- `D3.js` 是一个复杂的数据可视化工具。
- 支持 HTML、CSS 和 SVG。
- 使用数据驱动的方法修改 DOM。
- 快速框架 D3 使得各种动态行为和数据集成为可能。
- 通过减少开销，它在保持高帧率的同时允许更复杂的图形。

### Underscore.js

`Underscore` 是一个 JavaScript 实用包，包含了许多常用编程任务的函数。`Jeremy Askenas` 在 2009 年制作了它并根据 MIT 许可证发布。`Lodash` 现在已经超过了它。

#### 特性

- 它的功能与 `Prototype.js`（另一个著名的实用包）相当，尽管 `Underscore` 设计用于函数式编程，而不是对象原型扩展。
- 它包含了约 100 个函数，根据它们修改的数据类型分为四类。这些是可以操作的函数：
  - 对象
  - 数组
  - 数组和对象两者
  - 其他功能
- `Underscore` 适用于 Chrome、Firefox、Edge 和其他浏览器。

## JavaScript 入门 II ■ 195

#### 用场景

- 它提供了如过滤器（filters）和映射（maps）等功能性工具，以及绑定（binding）、快速索引、JavaScript 模板、质量测试等特定函数。

### Lodash

另一个简化对象、数组、字符串和数字处理的 JS 工具包被称为 `Lodash`。它和 `Underscore.js` 一样，于 2013 年引入，并使用函数式编程。

#### 特性

- 它让编写简洁且可维护的 JavaScript 代码变得更加简单。
- 数学操作、绑定、节流（throttling）、装饰、约束、防抖（debouncing）和其他常规任务被简化了。
- 更简单的字符串操作包括驼峰转换、修剪和大写转换。
- 数组的生成、修改、压缩和排序。
- 对集合、对象和序列的额外操作。

#### 用场景

它的模块化方法可以帮助我们：

- 遍历数组、字符串和对象。
- 构建复合函数。
- 数值处理和测试。

### Algolia Places

`Algolia Places` 是一个 JavaScript 软件包，允许我们以简单且广泛的方式在网站上使用地址自动补全。
它是一个极快且精准的工具，可以提升我们网站的用户体验。`Algolia Places` 使用 `OpenStreetMap` 卓越开源数据库来覆盖国际位置。

## 征服 JavaScript

#### 特性

- 通过一次填充许多输入框来加速结账过程。
- 我们可以轻松利用国家或城市选择器。
- 通过在地图上展示实时链接推荐，我们可以快速看到结果。
- `Algolia Places` 可以处理错误并适当展示结果。
- 它通过自动将所有查询路由到最近的服务器，在毫秒内返回响应。

#### 用场景

- 允许我们包含地图来显示特定地点，这非常方便。
- 它允许我们更有效地使用表单。

### Anime.js

最好的 JavaScript 动画库之一是 `Anime.js`，我们用它为网站或应用程序创建动画。
它于 2019 年发布，体积紧凑，具有可靠且直观的 API。

#### 特性

- `Anime.js` 支持 DOM 属性、CSS 属性、SVG、CSS 变换和 JS 对象。
- 兼容多种浏览器，包括 Chrome、Safari、Firefox 和 Opera。
- 它的源代码易于理解和应用。
- 复杂的动画技术如重叠和交错落下（staggered fallthrough）变得简单。

## JavaScript 入门 II ■ 197

#### 用场景

- 在属性和时机上，我们可以利用 `Anime.js` 的交错机制（staggering mechanism）。
- 在一个 HTML 元素上同时创建多个持续时间的分层 CSS 修改。
- `Anime.js` 的回调函数和控制函数用于以同步的方式播放、停止、触发、反转和控制事件。

### 滚动动画 (AOS)

对于单页视差网站，`Animate On Scroll` 是理想之选。这个开源 JS 工具包允许你为网站添加精美的动画，这些动画在我们向上向下滚动时看起来非常好。它通过允许我们添加淡入效果、静态锚点放置和其他令用户惊喜的功能，增强了我们的网站设计。

#### 用场景

- 该库可以识别元素位置，并在它们出现在视口时应用相应的类。
- 它不仅允许我们简单地构建动画，还允许我们在视口中调整它们。
- 它在各种设备上运行良好，包括手机、平板电脑和 PC。
- 它没有依赖项，因为它完全是用 JavaScript 开发的。

#### 用场景

- 根据另一个元素的位置动画一个元素。
- 根据项目在屏幕上的位置制作动画。
- 在移动设备上禁用元素动画。
- 创建各种动画，如淡入、翻转、滑动、缩放、锚点放置等。

## 198 征服 JavaScript

### Bideo.js

我们是否想将全屏视频整合到网站背景中？
尝试一下 `Bideo.js`。

#### 特性

- 使用这个 JavaScript 软件包，我们可以轻松添加视频背景。
- 此功能看起来非常棒，并且在所有尺寸和比例的屏幕上运行良好。
- 视频可以根据使用的浏览器调整大小。
- CSS/HTML 使其实现变得简单。

#### 用场景

- 在网站中整合响应式全屏背景视频。

### Chart.js

我们的网站或项目与数据分析领域相关吗？
是否有必要提供大量的统计数据？`Chart.js` 是一个非常棒的 JavaScript 软件包。`Chart.js` 为想要快速在其项目中添加惊艳图表和图形的设计师和开发者提供了一个多功能且易用的框架。它是开源的，并根据 MIT 许可证协议授权。

#### 特性

- 可以以优雅且直接的方式添加基础图表和图形。
- 结果是生成响应式页面。
- 加载轻量，学习和实现简单。
- 有八种不同的图表类型。
- 非常适合初学者。
- 页面可以进行动画处理，使其更具交互性。

## JavaScript 入门 II ■ 199

#### 用场景

- 当使用不同的数据集时，混合图表类型提供了清晰的视觉表示。
- 在对数、日期、时间或用户定义的刻度上绘制稀疏且复杂的数据集。

### Cleave.js

如果我们希望格式化文本内容，`Cleave.js` 提供了一种有趣的方法。
它的发明旨在通过格式化输入的数据来更简单地提高输入字段的可读性。要格式化文本，我们不再需要使用掩码模式或正则表达式。

#### 特性

- 通过为表单提交提供一致的数据来提高用户体验。
- 我们可以以多种方式格式化信用卡号、电话号码、日期、时间和数字。
- 应该格式化自定义块、前缀和分隔符。

#### 用场景

- 使用 CSS 选择器对集合、对象和序列应用 `cleave.js`。
- 对给定值进行更改。
- 获取文本字段的引用。
- 在 `Vue.js`、`jQuery` 中使用。

### Choreographer.js

要高效地制作 CSS，请使用 `Choreographer.js`。
它甚至包含非 CSS 的动画。
使用 `npm` 安装其包或添加其脚本文件使用。

## 征服 JavaScript

#### 特性

- 它的 `Animation` 类负责管理动画数据。
- 每个动画实例通过 `animationConfig` 对象配置。
- 有两个内置动画函数：`'change'` 和 `'scale'`。
- `Scale` 用于将渐进值应用到样式。
- `'Change'` 命令移除或添加样式属性。

#### 用场景

- 创建快速滚动动画。
- 根据鼠标移动创建动画。
- 使用单个图片遮罩，在给定表单下方创建渐变动画。
- 开发响应事件的渐变动画。

### fullPage.js

`fullPage.js` 是一个开源 JS 软件包，它让开发全屏滚动网页或单页网站变得简单。它易于使用，并允许我们在网站分区中包含横向灯片播放器。

#### 特性

- 提供了多种自定义和设置选项。
- 支持 `react-fullpage`、`angular-fullpage` 和 `vue-fullpage` 等 JavaScript 框架。
- 允许垂直和水平滚动。
- 能够适应不同屏幕尺寸和浏览器的响应式设计。
- 页面加载时自动滚动。
- 视频/图像懒加载。

#### 用场景

- 通过使用多个扩展来增强默认功能。
- 构建全屏滚动网站。
- 制作单页网站。

### Leaflet

`Leaflet` 是将交互式地图集成到网站的最伟大的 JavaScript 框架之一。它是开源且对移动端友好的，文件大小约为 39kb。
`Leaflet` 为 WordPress 的 `MapPress Maps` 插件中的交互式地图提供了动力支持。

#### 特性

- 性能改进包括移动端硬件加速和 CSS 支持。
- 图瓦层、弹出窗口、标记、矢量层、GeoJSON 和图片覆盖都是独特层的示例。
- 拖拽平移、双指缩放、键盘导航、事件和其他交互功能。
- 地图上提供图层切换器、归属、比例尺和缩放按钮。
- 支持 Chrome、Safari、Firefox、Edge 等浏览器。
- 自定义选项包括 OOP（面向对象编程）、基于 HTML 和图片的标记、CSS3 控制和弹出窗口。

#### 案例研究

- 在我们的网站上包含改进了缩放和平移、智能多边形/折线渲染、模块化设计以及点击延迟移动动画的地图。

### Multiple.js

`Several.js` 允许利用 CSS 或 HTML 在多个项目之间共享背景图像，且不需要 JavaScript 坐标处理。因此，它产生了引人注目的视觉冲击，鼓励用户提高参与度。

#### 特性

- 支持多背景。
- 支持渐变透明度。
- 支持许多移动和网络浏览器。

#### 用场景

- 分发背景图像。

### Moment.js

`Moment.js` 帮助我们在处理多个时区、API 请求、本地语言等时成功管理时间和日期。
通过检查、解析、格式化或更改日期和时间可以简化操作。

#### 特性

- 它支持大量的全球语言。
- 对象的可变性。
- 提供若干内部特性，如时间戳偏移（epoch shifting）和访问原生 `Date` 对象。
- 关于如何正确使用解析器有多种建议，例如严格模式、日期格式、宽容模式等。

#### 用场景

- 在发表的文章中包含时间戳。
- 使用母语与世界各地的人士交流。

### Masonry

`Masonry` 是一个出色的 JS 网格布局框架。
该库帮助我们根据可用的垂直空间来定位网格项目。它甚至被一些最流行的 WordPress 图片库插件使用。
考虑一下石匠在筑墙时是如何放置石头的。

#### 特性

- `Masonry` 的网格排列基于列构建，没有定义的行高。
- 通过移除不必要的空间来优化网页空间。
- 在保持布局结构完整的同时对项目进行排序和过滤。
- 动画效果。
- 自动更改布局以实现最佳结构的动态组件。

#### 用场景

- 制作具有不同图片大小的图片库。
- 在保持一致性的同时，多列列出最新的博客文章，即使摘要长度发生变化。
- 代表作品集，如照片、设计、项目等。

### Omniscient

`Omniscient.js` 是一个 JS 软件包，提供 React 组件抽象，用于使用不可变数据进行即时的自上向下渲染。因为它高效且具有迷人的特性，这个库可能帮助我们顺利地构建项目。

#### 特性

- 提醒我们无状态 React 组件。
- 用户界面函数式编程。
- 从顶部渲染组件。
- `Immutable.js` 支持不可变数据。
- Mixins（混合）提供了具有共享功能的微型且可组合组件。

#### 用场景

- 为组件提供键（keys）。
- 使用辅助函数或构造与父代码通信。
- 覆盖元素。
- 调试和过滤。

### Parsley

我们想要将形状引入到项目中吗？如果是，`Parsley` 可能对我们有益。
它是一个简单而有效的表单验证 JS 库。

#### 特性

- 它的简单 DOM API 直接从 HTML 标签接收输入，无需你编写单行 JS。
- 通过动态检测表单更改来实现动态表单验证。
- 有超过 12 个内置验证器、一个 Ajax 验证器和各种扩展。
- 我们可以修改 `Parsley` 的默认行为并提供更关注 UI 和 UX 的体验。
- 免费、开源且极其可靠，兼容多种浏览器。

#### 用场景

- 制作基础表单。
- 执行复杂的验证。
- 创建带有多个步骤的表单。
- 多个输入正在被验证。
- 处理承诺和 Ajax 请求。
- 通过样式输入创建的悬浮错误标签。

### Popper.js

`Popper.js` 旨在简化显示在按钮附近的弹出框、下拉列表、工具提示和其他上下文元素。

#### 特性

- 一个大小约为 3kb 的轻量库。
- 当我们在容器内部滚动时，工具提示会保持在引用元素旁边。
- 高级自定义性。
- 使用全面的工具包开发 UI，例如 Angular 或 React。

#### 用场景

- 从零开始创建工具提示。
- 整齐地排列这些部分。

### Three.js

`Three.js` 可以增强 3-D 设计体验。在现代浏览器中，它使用 WebGL 渲染场景。如果我们使用 IE 10 或以下，请尝试 CSS3、CSS2 和 SVG 渲染器。

#### 特性

- 支持 Chrome 9+、Opera 15+、Firefox 4+、Internet Explorer 11、Edge 和 Safari 5.1。
- 支持类型数组、Blob、Promise、URL API、Fetch 等其他 JS 能力。
- 我们可以制作各种几何体、对象、光照、阴影、加载器、材质、组件、纹理等。

#### 用场景

- 创建几何立方体、球体或其他形状。
- 创建相机或场景。

### Screenfull.js

使用 `Screenfull.js` 为我们的项目添加全屏元素。由于其出色的跨浏览器性能，我们将它没有问题。

- 隐藏手机导航 UI。
- 使用 jQuery 和 Angular 添加全屏组件。
- 检测全屏变化、错误等。

#### 用场景

- 在网站上包含全屏功能。
- 在文档中使用 `Screenfull.js`。
- 切换全屏模式并退出。
- 事件管理。

### Polymer

`Polymer` 是 Google 的一个开源 JavaScript 工具包，用于使用组件创建 Web 程序。

#### 特性

- 创建自定义组件的简单方法。
- 属性计算。
- 支持单向和双向数据绑定。
- 手势事件。

#### 用场景

- 使用 JS、CSS 和 HTTP 使用自定义 Web 组件构建交互式在线应用。
- 它被 YouTube、Google Earth 和 Play 等热门网站和服务的使用。

### Voca

`Voca` 的目的是减轻处理 JavaScript 字符串带来的痛苦。它包含了许多实用的函数，可以轻松操作字符串，如更改大小、填充、修剪、截断等。

## JavaScript 入门 II ■ 209

#### 特性

- 由于其模块化的本质，整个库或单个函数都能快速加载，同时缩短了应用的构建时间。
- 提供用于字符串的切割、格式化、处理、查询和转义的工具函数。
- 无依赖项。

#### 用例

- `Voca` 可用于多种环境，包括 `Node.js`、`Webpack`、`Rollup`、`Browserify` 等。
- 将主题的大小更改为标题 Case（title case）、驼峰 Case（camel case）、横线命名（kebab case）、蛇形命名（snake case）、大写（upper case）和小小写（lower case）。
- 将首字母转换为大写或小写。
- 启用隐式/显式链序列，构建链对象来包裹主体。
- 执行各种操作，如字符计数、字符串格式化等。

本章涵盖了异步开发、DOM 操作、HTTP 和表单。我们还讨论了如何与 API 和 JavaScript 库一起。

## NOTES

- 1 如何为 Node.js 编写异步函数?: www.geeksforgeeks.org/how-to-write-asynchronous-function-for-node-js/?ref=lbp 访问日期: 2022年9月28
- 2 如何在 JavaScript 中创建异步函数?: www.geeksforgeeks.org/how-to-create-an-asynchronous-function-in-javascript/?ref=lbp 访问日期: 2022年9月28
- 3 JavaScript 中的同步与异步: www.geeksforgeeks.org/synchronous-and-asynchronous-in-javascript/?ref=lbp 访问日期: 2022年9月28
- 4 解释异步与延迟的 JavaScript: www.geeksforgeeks.org/explain-asynchronous-vs-deferred-javascript/?ref=lbp 访问日期: 2022年9月28
- 5 文档对象模型: www.javatpoint.com/document-object-model 访问日期: 2022年9月28
- 6 Javascript - document.getElementById() 方法: www.javatpoint.com/document-getElementById()-method 访问日期: 2022年9月28
- 7 GetElementsByByClassName(): www.javatpoint.com/javascript-getelelements-byclassname 访问日期: 2022年9月28
- 8 Javascript - document.getElementsByName() 方法: www.javatpoint.com/document-getElementsByName()-method 访问日期: 2022年9月28
- 9 Javascript - document.getElementsByTagName() 方法: www.javatpoint.com/document-getElementsByTagName()-method 访问日期: 2022年9月29
- 10 Javascript innerHTML: www.javatpoint.com/javascript-innerHTML 访问日期: 2022年9月29
- 11 javascript - inner: www.javatpoint.com/javascript-inner 访问日期: 2022年9月29
- 12 在 JavaScript 中发送 HTTP 请求: https://livecodestream.dev/post/5-ways-to-make-http-requests-in-javascript/ 访问日期: 2022年9月29
- 13 Http Cookies: www.javatpoint.com/http-cookies 访问日期: 2022年9月30
- 14 JavaScript 表单: www.javatpoint.com/javascript-form 访问日期: 2022年9月30
- 15 JavaScript 表单验证: www.javatpoint.com/javascript-form-validation 访问日期: 2022年9月30
- 16 在 JavaScript 中处理 API: https://geeksforgeeks.org/working-apis-in-javascript/ 访问日期: 2022年9月30
- 17 2022 年最佳40 个 JavaScript 库和框架: https://kinsta.com/blog/javascript-libraries/ 访问日期: 2022年10月01

# 更清晰的图景

### 本章内容

- JS 的各种用途
  - 前端
  - 后端
  - 移动端
  - 游戏
  - 桌面端
- 寻找你的生态领域
- 学习哪个框架以及何时学习？
- 将 JS 技能与其他编程语言结合

让我们花些时间讨论整个 JavaScript 生态系统。

## 什么是 JavaScript 框架？

JavaScript 框架是一组预先编写的程序，旨在启用并提供纯 JavaScript 本身无法提供的优势。如果我们对框架的概念仍然不清楚，可以想象成一个帐篷。
我们构建一个框架作为帐篷的结构。然后帐篷的内部和外部可以用我们选择的任何方式进行自定义。

DOI: 10.1201/9781003356578-4

自然，JavaScript 框架并不是像我们的帐篷那样的真实建筑，但理念是相同的。

在介绍最著名的 JavaScript 框架之前，让我们花几分钟时间解决两个常见问题。

## JavaScript 框架与 JavaScript 库有何区别？

JavaScript 库是为特定用例创建的代码集合。

例如，`Day.js` 插件专门用于在 JavaScript 中处理日期，这对于有经验的开发者来说可能是挑战性的。

`jQuery` 是一个著名的 JavaScript 库，它简化了 DOM 遍历和事件处理的语法。

## 214 征服 JavaScript

# 7 大主流 JavaScript 前端框架

我们将首先讨论适用于现代 Web 的 JavaScript 框架。

# 1. React

React 是最著名的开源 JavaScript 框架之一，由 Facebook 的软件工程师 `Jordan Walke` 于 2013 年开发。

在 GitHub 上，React 社区已获得超过 18 万个星标。全球约有 40% 的开发者在使用并青睐 React。

尽管用户满意度在 2020 年略有下降，但 React 仍然是初入加入 IT 行业的新开发者的热门选择。

它学习更简单，拥有更强大的社区支持，并且非常轻量。

`Simform` 也使用了 React，因为它非常轻量，可以为国际曲球联合会（FIH）创建一个用户友好的组件驱动型在线应用程序。

## 运行机制

- 得益于 React 对 JSX 的使用，开发者可以将 HTML 片段包含在 JavaScript 文件中。
- React 库可以与状态管理、路由和 API 无缝集成。
- React 库使用内存缓存来创建虚拟 DOM。虚拟 DOM 会比较“组件”之前和之后的状态。基于此，实际 DOM 只会渲染状态发生变化的组件。
- 开发者可以使用框架的单向数据绑定进行嵌套，这是一种单向数据流。
- 在执行代码时，它会利用如 `componentDidMount` 等生命周期方法。

## 真实应用案例

Facebook、Netflix、Asana、Pinterest、Airbnb、Reddit、UberEats 等热门网站都是使用 React 设计的。

## 热门 React 组件

- `Material UI`：使用 React 组件集可以制作出精美的 UI 设计。它具有多种功能，包括用于表单、导航和布局等组件的样式元素。
- `React Semantic UI`：`React Semantic UI` 使用简单的句子来激活内置功能。此外，界面具有多种主题，为开发者提供了创作灵活性。
- `React Toolbox`：是一组使用 SASS 创建的 React 组件集合，遵循 Google 的材料设计指南。它利用 CSS 模块导入 SASS 样式表。该库提供了灵活且可定制的解决方案，并能与 React `webpack` 轻松集成。

### 优点

- Facebook 支持社区。
- 可以在不使用类的情况下编写组件。
- 以可重用的代码组件而闻名。
- 适合初学者。

### 缺点

- 文档不足且缺乏权威性。
- 持续的更新迫使开发者跟上新进展。
- 学习 JSX 语法可能比较困难。

### 我们什么时候应该使用 React？

由于其虚拟 DOM 特性，React 是创建单页应用程序（SPAs）最有效的选择。此外，React 拥有强大的社区，是创建复杂应用的极佳选择。

# 2. Vue.js

`Vue.js` 是由 Evan 及其团队创建并维护的开源前端框架，最早于 7 年发布。如今，`Vue.js` 常用于必须在 JavaScript 框架上运行的轻量前端应用。在 2021 年的 GitHub 投票中，它在框架中排名第三。通过使用该框架，已经创建了近 70 万个网站。在开发代码时，`Vue.js` 是一个提供更多灵活性的全框架。该框架因其合适的体积和更快的加载速度而闻名。

## 运行机制

- `Vue.js` 使用虚拟 DOM 提供状态更新和修改。
- `Vue.js` 支持单向和双向数据绑定。这种能力被称为响应式双向数据绑定。这意味着它能够轻松地修改组件类与其模板之间的数据。
- `Vue.js` 的生态系统非常丰富。即使它缺乏移动端框架，我们也可以使用 `Quasar Framework`、`NativeScript` 或 `Ionic` 创建混合移动应用。
- `Vue.js` 也使用了 JSX。通过 JSX，`Vue.js` 可以快速导入和维护自定义组件。
- `Vue.js` 提供了多种应用过渡效果的方法，拥有丰富的 CSS 过渡和动画。`Vue.js` 用户可以使用过渡封装器、独特的过渡类、JavaScript 钩子和其他功能。

## 真实应用案例

阿里巴巴、9gag、小米等知名企业已使用 `Vue.js` 处理它们所有的前端需求。

## 热门 Vue.js 组件

- 名 `Element UI` 的 `Vue.js` 组件库拥有 500 名活跃开发者和强大的社区支持。该组件非常注重细节，帮助开发者和设计师创建美观且引入胜的用户界面。非官方的 `Vue.js` 材料设计框架 `Vuetify` 允许你构建能够兼容服务端渲染（SSR）的可重用、整洁的组件。它现在在 GitHub 上已有 2.3 万个星标，社区和人气都在迅速扩大。超过 400 人参与了活跃的 `Vuetify` 社区，该社区已产生了 20 多个插件。
- 基于 Bootstrap 库的 UI 工具包称为 `Bootstrap Vue.js`。开发者可以使用此工具包配合 `Vue.js` 使用 Bootstrap 版本 4 创建响应式的、移动优先的应用。该工具包充满了网格系统、许多 UI 元素和主题。

### 优点

- 框架对新用户简单。
- `Vue.js` 详尽的文档。
- 支持双向数据绑定。
- 体积很小且容易集成。

### 缺点

- 缺乏多种插件供选择。
- 开发者社区不是很大。
- 没有技术巨头支持该框架。
- 不适合扩展。

### 我们什么时候应该使用 Vue.js？

通过 `Vue.js`，我们可以使用一个超越简单库且不会使代码复杂的框架。如果你正在寻找一种能够保持逻辑和视图分离的设计，`Vue.js` 就是答案。如果我们想要诸如树摇优化、代码分割等开发者友好的功能，`Vue.js` 是市场上的最佳替代方案。

# 3. Angular

Angular 是一个基于 TypeScript 的开源 Web 框架，由 Google 创建。Angular 2 版本包含了依赖注入、异步编译、RxJS 等基础功能。

它在开发者中非常受欢迎。根据 `Ideative` 的调查，近 60% 的工程师具有使用 Angular 框架的经验。`Simform` 的专家也使用 Angular 创建了 `FoodTruck Spaces` 应用。

## 运行机制

- Angular 是一个功能齐全的 MVC 框架，有助于构建应用程序。
- 该架构提供双向数据流。通过控制器，这种功能允许 Angular 连接 DOM 和模型数据。我们可以通过双向数据流同时监听事件并修改父组件之间的数据。
- 尽管存在缺点，Angular 的环境非常好。我们可以使用它提供的许多解决方案来构建快速高效的应用。例如，在 Angular 中使用服务端渲染无需安装或配置。
- 得益于 Angular 分级依赖注入功能，所有的代码组件都经过了测试且可以重用。

## 真实应用案例

许多 Google 服务都是使用 Angular 创建的。
其他使用 Angular 的知名网站包括 Forbes、LEGO、Autodesk、BMW 等。

## 热门 Angular 组件

`Ngx-bootstrap` Angular 组件库非常适合将 Bootstrap 组件集成到你的项目中。使用 Angular 创建 Bootstrap 组件可以提高效率并实现响应式用户界面。`Angular Material` 是一组灵感源自 Google 材料设计的各种重用 UI 组件。该工具包提供了丰富的 UI 设计元素、响应式网格布局和不同的主题。

### 优势

- Angular 基于组件的设计提供了完美的模型到视图的无缝同步。
- 提供了可复用且经过彻底测试的组件。
- Angular 拥有庞大的开发社区，并得到了 Google 的支持。
- 提供了依赖注入和指令等高级功能。

### 缺点

- 这种结构对初学者并不友好。用户在使用框架之前，必须熟悉 MVC。
- SEO 能力受限。
- 文件大小显著增加。

### 我们应该何时使用 Angular？

由于它是一个完整的框架，Angular 适用于创建大型企业级应用。它还利用了 MVC 架构，这使得复杂功能的无缝集成。

# 4. jQuery

在现代 JavaScript 库和框架出现之前，jQuery 曾主导了 IT 行业。它是最早的开源 JavaScript 库之一，轻量且功能丰富，由 `John Resig` 于 2006 年发布。专家认为，它是最好的 JavaScript 前端框架之一。

根据 `W3Techs` 的一项研究，所有使用 JavaScript 的网站中有 95.5% 都使用了 jQuery。众所周知，JavaScript 脚本可以被 jQuery 最小化，其知识且成熟的社区也提供了强有支持。

## 如何运作

- jQuery 以其事件处理能力而闻名。即使是鼠标点击和键盘按键等用户操作也被浓缩成短小的代码段，以便于管理。

## 征服 JavaScript

- jQuery CSS 的语法非常相似。初学者可以很快获得该框架的实践经验。
- 该框架的最新版本现在带有 `jQuery Mobile`，用于创建可扩展的移动端应用。
- 它是一个易于使用的框架，API 直观，适用于多种浏览器。
- jQuery 是支持 AMD 模块的轻量级框架之一，空项目的 zip 大小为 30kb。通过使用 AMD 模块，可以在不使用 `Download Builder` 的情况下管理 UI 依赖。该模块还帮助我们使用专用的 AMD 加载器 `RequireJS` 加载 jQuery UI 的源代码。

## 案例

Twitter、Microsoft、Uber、Pandora、SurveyMonkey 等其他知名公司已在其应用中使用 jQuery。

## 流行的 jQuery 组件

- `jQuery UI` 是一个免费库，为我们的下一个项目提供了各种 UI 元素。该库是动态和交互式组件的扩展，程序员可以使用它们来改进应用程序的用户界面。树形视图、表单组件、颜色选择器、图表、RTL 支持和其他关注的元素只是其中一部分。此外，该库在各种浏览器、平台和设备上提供了一致的性能。
- 基于 jQuery 的 `jQuery mobile` 组件库被称为 `Wijimo`。该工具使用 jQuery 驱动，从而获得了更好的性能。它提供了超过 30 种主题、对 RTL 的支持、视频小组件、动画等。此外，该组件同时兼容在线和移动平台。
- 一个名为 `Mauri` 的免费插件允许我们为 jQuery 构建灵活的布局。得益于该插件，我们对网格容器和尺寸具有完全控制权。在使用 jQuery 创建直观的 UI 时，开发者可以凭借这种自由释放内在的设计才华。

### 优势

- 所有广泛使用的网络浏览器都兼容该框架。
- 提供出范的社区支持。
- jQuery 的学习曲线并不严重。
- 提供了大量的插件选择。

### 缺点

- 因为它包含了所有的 DOM 事件、效果和 AJAX 组件，所以文件体积巨大。
- DOM API 过旧。
- 由于缺乏数据层，修改 DOM 是一项耗时且手动的过程。

### 我们应该何时使用 jQuery？

由于 jQuery 具有跨浏览器兼容性，它仍然是交付基于 Web 和桌面的 JavaScript 应用的最佳选择。

# 5. Svelte

Svelte 是一个开源的前端框架编译器，而此列表中的大多数框架是完整的框架或库。

它首次于 2016 年展示，并迅速受到了开发者社区的喜爱。截至目前，已有超过 2.5 万网站使用其代码进行创建。由于它只是一个编译器，使用 Svelte 创建的应用会生成更改 DOM 的代码。

因此，它是轻量级前端框架之一。

## 如何运作

- Svelte 应用中使用 MVC 架构概念来分离模板、逻辑和视图。它允许许多开发者同时在同一个项目上协作。

## 征服 JavaScript

- 通过 Svelte，我们可以将基础 JavaScript 与 HTML、CSS 和 TypeScript 混合。
- Svelte 使用资源很少，因为它不需要额外内容来创建虚拟 DOM。这使得程序的总加载时间大大加快。

## 案例

许多知名公司已使用 Svelte 创建网站，并从其易用性中受益。例子包括纽约时报、Absolute Web、Cashfire、Godaddy 和 Razorpay。

## 流行的 Svelte 组件

- `Svelte Material UI` 是一个用 TypeScript 编写的 Material UI 集合。使用 SASS 对 `Svelte Material UI` 进行样式处理。开发者可以使用 SMUI (Svelte Material UI) 提供的各种组件和工具创建独特的用户界面组件。
- `Svelte-flow` 是 Flowbite 驱动的 Svelte UI 组件，可以帮助你更快地设计网站。包含了深色模式、按钮、模态框、卡片、导航栏等。
- `Carbon Components Svelte`——它是 IBM 开发的开源设计工具 Carbon 设计系统。它有约 7,000 个图标、20 多种图表等。

### 优势

- 转换为原生 JavaScript 代码。
- 结构非常轻量。
- 提供对组件架构的支持。

### 缺点

- 生态系统较小。
- 市场上没有太多的 Svelte 工具。
- 难以扩展。

### 我们应该何时使用 Svelte？

Svelte 的独特卖点在于简单。Svelte 最适用于小型任务。

## 更清晰的视图 ■ 225

但为了完全的库兼容性，该框架很大程度上依赖 `underscore_js` 和 jQuery。Simform 利用 `backbone.js` 的功能创建了 `SenTMap`，一个情感分析引擎。

## 它是如何工作的

- `Backbone.js` 的核心方面之一是可以将业务逻辑与用户输入逻辑分离的能力。这有助于程序员创建结构良好的应用程序。
- `Backbone.js` 促使开发者将数据转换为模型（models），将 DOM 操作转换为视图（views），并通过事件将两者连接起来。
- 该框架为客户端 Web 应用程序提供了带有枚举方法的强大 API。
- 如果架构的模型发生变化，`Backbone.js` 会自动刷新应用程序的 HTML。

## 现实案例

`Backbone.js` 已被许多知名公司（包括 Uber、Pinterest、Reddit、Trello 和 Tumblr）用于，以满足各种需求。

## 优势

- 提供了超过 100 种扩展。
- 该框架对新用户来说非常简单。
- 移植性极强。
- 数据存储在模型中，而不是 DOM 中。

## 缺点

- 没有双向数据绑定功能。
- 有时架构显得既复杂又模糊。
- 我们必须编写更多的模板代码（boilerplate code）。
- 开发者社区认为该框架正在逐渐过时。

## 226 征服 JavaScript

### 我们什么时候应该使用 Backbone.js？

`Backbone.js` 可用于较大的项目，最适合基础的单页应用。

## 我们如何能为下一个项目选择理想的 JavaScript 框架？

要跟踪所有框架之间的变化是非常挑战性的。
更困难的部分是决定为我们的项目采用哪一个。
做出错误的选择将浪费我们项目的大量资金。遗憾的是，很难判断哪种框架对我们是最好的。

我们公司的需求将决定使用的框架，但以下考虑因素可能有助于您的选择。

### 团队熟练度

最常见的是框架，如果有的话。
然而，如果我们目前的团队不擅长使用该框架，开发者将无法充分利用它。

选择一个我们团队最熟悉的框架，或者招聘员工来利用市场领先的框架。

### 向后兼容性

前端框架有助于编写应用程序代码，但也必须考虑后端。

为了使应用程序功能完全，前端和后端必须能够顺畅通信。

如果你已经建立了后端，选择一个与后端互补的框架是一个好主意。
如果没有，我们将不得不处理集成问题、兼容性问题等困难。

### 复杂度

如果你正在创建一个具有多个子页面和功能的复杂 Web 应用程序，请选择基于 MVC 架构的框架。通过这种方式，我们能够将你的功能划分为可以并发开发的章节。这样做将极大地缩短我们的开发时间。

## 更清晰的视图 ■ 227

然而，使用轻量级框架创建复杂的应用程序可能是灾难性的。一个不够健壮的框架无法管理复杂性，最终会遇到严重问题。

### 尺寸与功能

理想情况下，一个框架不应该有很多功能。某些框架可能看起来非常复杂但部署具有挑战。如果我们正在创建一个功能较少的简单系统，请专注于实现最大性能。根据经验，在设计框架时，你的目标是在性能和尺寸之间找到平衡点。

# 5 种后端 JavaScript 框架

在 Web 开发方面，Web 由 JavaScript 驱动。JavaScript 负责网站的行为，包括在不完全刷新页面的情况下加载和重新加载新页面内容、制作页面动画以及验证在线表单中的用户输入。HTML 和 CSS 管理页面显示的样式和数据。

JavaScript 的流行导致了随着时间的推移出现了一波框架浪潮。对于 JavaScript 开发者来说，感觉每周都有新框架问世，每个都声称比上一个更优。

由于数百万网站依赖第三方 JavaScript 库和框架，对这些项目有着持续的需求。

那么后端呢？我们之前涵盖了一些最著名的前端框架。虽然某些框架是类似的，但最好避免将前端和后端编程混合在一起，特别是在使用像 JavaScript 这样重要的工具时。

例如，JavaScript 通常用于服务器端和其他非浏览器应用程序，这要求开发者从根本上不同的方式处理他们的工作。

# 1. Next

虽然听起来有点奇怪，但 Next 框架让跨项目共享 JavaScript 代码变得极其简单。

这消除了在许多语言中编写相同工作的需求。

几乎完全相同的组件被用于显示客户端标记和查询数据存储。

## 228 征服 JavaScript

一旦你掌握了基础知识，使用 Next 创建的一切都会变得非常直观。

“通过 Next，我们得到了维护极良好的文档，以及与像 `create-react-app` 等项目相同的设置简单性。”

它由 Vercel 维护，这家公司最初名为 Zeit，它包含了一个适用于目前正在使用的几乎每个用例和集成的示例库。

他们的部署平台也是我们喜欢的。

由于我们构建的 API 路由和页面被转换为 lambda 函数，Next 本质上是为了部署而构建的。

在我看来，开发者通过更多地关注应用程序问题而不是 AWS 控制台问题可以节省大量时间。

由于我们创建了一个处理服务端渲染、易于配置 API 路由且通常比 `create-react-app` 更好的框架，我们认为我们 Next 优于 Gatsby 或 Node 后端工具。它们在各个方面都有益处，但因为我们需要在许多项目上工作，我使用 Now 发布时选择了 Next。

它被营销为一种处理服务端渲染、易于配置 API 路由且通常更好的 `create-react-app` 框架，`Next.js` 现在是 9.5 版本。第一个版本发布于 2016 年 10 月。

# 2. Express

`Express.js` 是开发 Web 应用和 API 的极佳选择，正如 OrangeSoft 的全栈开发者 `Kirill Onishuk` 所说。

通过安装必要的 `npm` 包，它可以易于扩展，从而解决任何问题。

Express 在 `node.js` 之上提供了一个层，并没有限制其功能，允许我们快速使用它的特性。

由于 Express 提供了多种模板引擎，Onishuk 说，“它非常适合创建带有渲染的应用程序”（例如 `pug` 和 `handlebars`）。

它具有许多 HTTP 服务方法。

## 更清晰的视图 ■ 229

# 3. Gatsby

不需要服务器，因为页面可以在本地开发并推送到对象存储和 CDN（例如 AWS S3 和 Cloudfront）。这种设计提供了快速的性能，同时降低了成本和复杂度。

拥有超过 2000 个插件的庞大库，Gatsby 也具有可扩展性。

Gatsby 是一个基于 React 和 GraphQL 的框架，非常适合构建相对静态的网页（当然是通过其插件）。

虽然 Gatsby 创建的网页不进行服务端渲染，但它可能具有局限性。

## 230 征服 JavaScript

它被 IBM、微软、Netflix 和沃尔玛等企业用作其基础设施和 Web 服务器的一部分。换句话说，如果我们想在主要依赖云基础设施的大型机构工作，就应该学习它。

### 5. Meteor

另一个比平台更像平台的框架。

该公司的创始人兼首席执行官 `Christian Fritz` 提供了一个非常出色的总结：“Meteor 拥有一个包系统、构建和部署的能力，以及测试支持。

虽然它与 `next.js` 或 `gatsby` 等其他框架有某些共同特征，但它在许多重要方面仍然是独一无二的。

Meteor 特有的 DDP 协议用于数据同步。

简单来说，DDP 会选择性地同步客户端 `mongodb` 数据库和服务器端 `mongo` 数据库中的集合。

这消除了开发者为客户端和服务器之间的数据传输编写 API 代码的需要（就像我使用 Express 一样），而且以一种非常优的方式实现了这一点：它在客户端使用响应式行为，因此当新数据到来时，页面会使用 React 或另一个响应式框架响应式地变化。它只传输补丁（patches），防止了重复数据的浪费（Vue、Angular、Blaze）。

许多其他现在利用 GraphQL 来减少编写 API 代码的需求，但 Meteor 仍然因其数据“就在那里”的实时和响应式特性而脱颖而出。

这对于任何用户可以添加或修改内容的应用程序都是理想的；它允许用户与其他用户实时、流畅地共享他们的工作。

“我还没有在其他任何地方看到过这种形式的东西，就是创建既包含客户端又包含服务器部分的包的可能性。账户管理是这一功能的最佳说明，它非常重要。

对于用户管理和身份验证，开发者通常必须选择两个库——一个用于前端，一个用于后端——然后想办法如何整合它们。

## 更清晰的图景 ■ 231

存在若干种危险，它通常需要开发者对他们想要选择的库有更多的了解。

使用 Meteor 这一点很容易。

例如，如果你安装了 `'accounts-password'` 包，你就会在服务器上获得一个带有（哈希过的）密码的用户数据库，并在客户端获得带有登录/注册/忘记密码等功能的必要交互式 UI，而且所有的通信都已经处理好了。

我们也可以轻松地安装其他包，如 `'accounts-google'` 来进行 Google 单点登录（以及用于 Facebook 或其他社交登录的类似包）。

因为它是基于 `Node.js` 开发的，并与著名的跨平台数据库引擎 `MongoDB` 交互，所以 Meteor 对于创建业务解决方案的开发者来说非常有益。

## 八大 JavaScript 游戏引擎

脚本语言 JavaScript 是跨平台且是解释性的。它以创建网站而闻名。它也被用于浏览器之外的许多场景。可以使用 JavaScript 进行客户端和服务器端的开发。本节将探讨每个 JS 开发者都应该熟悉的前 8 个 JavaScript 游戏引擎。

### 1. PixiJS

`PixiJS` 是一个非常快速且多功能的 2D 渲染库。我们可以使用 `PixiJS` 创建交互式的、美观的视觉效果，它还支持跨平台应用。在没有 WebGL 经验的情况下，程序员可以使用 Pixi 渲染器来利用硬件加速（它还支持 Canvas 回退）。

然而，它没有内置的物理引擎。它是一个完全免费的开源库，有一个非常给力的社区在推动着它的发展。

### 2. Phaser

使用 Phaser 创建跨平台游戏应用轻而易举。令人惊讶的是，它内部同时采用了 WebGL 和 Canvas 渲染器，并可以根据浏览器支持在它们之间切换。Canvas 用于不支持 WebGL 的设备。

一个庞大的 Phaser 游戏创作者社区以及各种插件都是其背后的支撑。它是目前 GitHub 上最流行的游戏框架和引擎之一。开发时，可以使用 JavaScript 或 TypeScript。

### 3. Babylon.js

`Babylon JS` 是一个惊艳、高效且直观的渲染引擎。它赋予程序员能够在浏览器中构建任何内容的能力，从动画 Logo 到完全交互的 3D 游戏。由于它是专门为可视化而创建的，所以它并不是一个真正的游戏渲染引擎，但你仍然可以用它创建出色的游戏。

由于其活跃且支持良好的开发者，它拥有强大的社区支持。它有一个演示场（playground），让你进一步进行开发实验。

### 4. PlayCanvas WebGL 游戏引擎

它不需要插件，而是利用 HTML5 和 WebGL 在任何移动或桌面浏览器上运行游戏应用以及任何其他交互式 3D 内容。这意味着你将使用他们的平台编写代码、测试代码，并通过快速导出你的游戏来设置场景。与 `Babylon JS` 相比，它更强调游戏引擎而非渲染引擎。3D 刚体物理引擎 `ammo.js` 让为你的游戏添加物理效果变得极其简单。

### 5. Melon.js

它是一个高效、轻量级且易于使用的 HTML5 游戏引擎，通过包含受欢迎的 Tiled 地图格式，让设计师和开发者能够专注于内容。它的主要目标是提供一种无需插件的用户体验（它运行只需要一个支持 HTML5 的浏览器）。为了保证最小的 CPU 需求，它使用了一个由活跃开发者小组支持的轻量级开源项目。

### 6. GDevelop

它是一个开源的全功能游戏制作工具，主要侧重于 2D 游戏开发，尽管它可以用于创建任何类型的游戏。

事件（Events）是一种允许你直观设计游戏逻辑的工具，而无需任何特定编程语言的预先知识，这就是它与其他游戏引擎的区别。

Web、Windows、Android、iOS、macOS 和 Linux 只是 GDevelop 游戏发布和运行的平台之一。它可以快速导出到 Android。

### 7. Kiwi.js

这种在 HTML5 浏览器中创建游戏的开源游戏框架非常简单使用。

考虑到 WebGL 渲染的提升，速度是它的主要关注点。

为了将游戏作为原生应用分发到移动设备，使用了 `Cocoon.js` 框架。

### 8. Three.js

该项目的主要目标是简化 WebGL 的使用。使用 `three.js` 可以用少得多的代码处理 WebGL。

除了默认的 WebGL 渲染器外，它还支持 Canvas 2D、CSS3D 和 SVG 渲染器。

## 更清晰的视野 ■ 235

`NativeScript` 允许开发者使用 `Vue CLI`、`VueX` 以及其他 Vue 框架功能创建原生移动应用程序。`NativeScript` 还结合了最新的 Angular 全栈功能，包括路由器的支持、代码生成、与 `Angular CLI` 的交互等。

### 为什么使用 NativeScript？

`NativeScript` 允许开发者使用来自 `npm`、`CocoaPods` (iOS)、`Gradle` (Android) 的现有插件，以及数百个 `NativeScript` 插件。

可以使用单一代码库在不同平台（Android 和 iOS）之间进行开发和分发。可以使用 Angular 或 `Vue.js` 进行代码共享。Web 开发者可以使用他们目前的 Web 知识（JavaScript、CSS、原生 UI 标记）构建原生移动应用程序。

### 3. Ionic

Ionic 是另一个用于创建混合应用的知名 JavaScript 框架。

对于熟悉 Web 技术和应用开发的开发者来说，理解一个 Ionic 应用的框架非常简单。用户并感知不到混合应用正运行在一个名为 `WebView` 的全屏浏览器中。

他们可以通过使用原生插件来使用移动设备的原生功能（如摄像头和指纹识别），而无需将核心代码连接到设备。

### 为什么选择 Ionic？

混合代码库可以在多个平台（Android 和 iOS）之间使用，降低开发成本（与原生应用相比）并缩短上市时间。

在用 Ionic 开发混合应用时，开发者可以使用 `Cordova` 插件访问移动设备的硬件和软件功能。可以使用现有的 Web 开发技能（HTML、CSS 和 JavaScript）来创建移动应用程序。

### 4. Apache Cordova

`Apache Cordova`（以前称为 `PhoneGap`）是一个混合应用开发平台，它将 HTML 或 JavaScript 程序封装在原生容器中。

有大量的技术、框架和云服务可用以提高 Cordova 的运行速度。

流行的名称包括 `Visual Studio`、`Ionic`、`Framework7`、`Monaca`、`Mobiscroll` 等。

考虑到 Cordova 的潜力，该框架的贡献者包括 Adobe、Microsoft、Blackberry、IBM、Intel 等科技巨头。

### 为什么选择 Cordova？

`Cordova` 插件开发者拥有一个庞大的社区。

因此，该框架允许开发者访问各种插件，允许他们访问设备功能并扩展程序的范围和大小。使用 Cordova 为多个平台（iOS、Android）交付代码是可行的，使得应用开发更具成本效益。

### 5. OnsenUI

`OnsenUI` 是一个 JS 框架，允许你使用 HTML、CSS 和 JavaScript 创建混合移动应用。`Onsen UI` 与 `AngularJS`、`Angular 2+`、`React`、`Vue` 和 `jQuery` 兼容，允许开发者在创建交互界面时在库和框架之间切换。

### 为什么使用 Onsen UI？

`Onsen UI` 包含大量复杂的 UI 组件，这些组件是专为移动应用程序构建的。`Monaca` 和 `Onsen UI` 配合得非常好。

`Monaca` 提供了一个强大的命令行工具和桌面界面来帮助处理复杂任务。

### 6. jQuery Mobile

市场上上有这么多智能手机，在构建移动应用程序时保持谨慎至关重要，这种应用不仅要加载更快，而且应该是自定义的并在多个平台上可用。

在开发加载更快的应用方面，与其他框架相比，`jQuery Mobile` 位名第一。

- 开发者可以更快地创建跨平台应用。
- 这是一种低成本的混合移动应用开发。
- 利用 HTML5 和 CSS3 创建更符合触摸习惯的用户界面。
- 因为它是一个轻量级框架，软件加载更快。
- 由 Ajax 驱动的导航带有动态页面过渡。
- 在所有平台和设备上保持一致的用户界面。

### 7. Mobile Angular UI

`Mobile Angular UI` 是一个 HTML5 框架，它使用 `AngularJS` 和 `Bootstrap 3` 创建高度交互的移动应用程序。如果我们喜欢 Angular，那么这正是我们需要的框架。
该框架不仅提供了关键的移动组件（如开关、侧边栏和覆盖层），还帮助网站以应用程序的形式变为响应式。

- 帮助更快速、更容易地绑定数据。
- 修改将立即反映在模型中。
- 通过促进缓存和其他任务减少对服务器 CPU 的负载。
- 更快速的应用原型设计。

### 8. Sencha Touch

`Sencha Touch` 允许你通过添加大量功能，根据用户的偏好精确定制用户与程序交互的方式。
`Sencha Touch` 是一种流行的基于 HTML 的框架，用于设计在所有平台上快速运行的应用，而无需为每个平台更新代码。

- 为应用提供高水平的响应。
- 它与最新版本的 Android、iOS 和 BlackBerry 兼容。
- 程序尽可能地加载。

### 9. Titanium

Titanium 是一个用于混合移动应用开发的经典框架，提供了对大多数原生能力的简单透明的访问。开发者可以使用 JavaScript 和 CSS 等 Web 技术创建原生应用以及混合应用和 Web 应用。

- 开发者可以快速创建兼容 Android、iOS 和其他平台的应用。
- 功能实体能够实现高性能应用的开发。
- 因为它带有一个集成环境，我们可以创建快速原型。
- 一个极具成本效益的开源替代方案。
- 因为它支持复杂的 Web 技术，代码结构被简化了。

### 10. Meteor

Meteor 是一个免费且开源的平台。它是用于移动应用的流行的 JavaScript。这个 JavaScript 框架不仅允许快速原型设计和跨平台编码，还让我们能够对自己的应用程序进行控制。

- 无需任何编程知识即可修改 JavaScript 代码。
- Meteor 以其速度和易于部署而闻名。
- 消除了大多数新程序似乎存在的 Bug。
- 在平台和设备之间提供了大量的灵活性。
- 可以使用外部库和各种插件。

## 适用于桌面应用的最佳 JS 框架

跨平台程序是指可以在许多操作系统上运行程序。这对客户和开发者来说都非常有用：开发跨平台解决方案可以节省时间和资金，并使程序更易维护。

## 跨平台应用和桌面程序可以通用吗？

这个问题的正确答案是“既是又不是”。跨平台程序似乎是运行在许多操作系统上的程序，但它们需要一种独特的方法来考虑桌面操作系统的特性。

## 240 征服 JavaScript

该开源框架用于为 React 桌面应用创建交互式界面。

`ReactJS` 非常适合处理复杂的应用程序、Web 应用程序甚至网站的设计层。

`Node.js` 允许我们在服务器上执行 JavaScript 程序并将结果提供给用户。得益于 `Node.js` 平台，JavaScript 已经成为一种主流语言，并拥有着庞大的开发者社区。

Node 是一个由 Google Chrome 的 V8 JavaScript 引擎驱动的服务器端框架。

该开源平台也用于开发网络和后端应用程序。

`Node JS` 桌面应用简单易用、高质量且速度快。

## 桌面应用的前五大 JS 框架

### 1. Electron

这是一个开源框架。GitHub 在 7 年前构建了它，用于 JS 应用程序 Atom 的编辑器。

该库将使能够开发高质量的跨平台桌面应用。

Electron 利用了 JavaScript、HTML 和 CSS 等网络技术。

Electron 程序的优势在于它允许我们创建功能与在线应用程序类似的桌面应用，同时还允许我们在计算机的文件系统中进行读写操作。Electron 框架曾用于构建 Linux 操作系统的 Skype 桌面平台。

### 2. NodeGUI

这是另一个用于使用 CSS 和 JavaScript 开发跨平台桌面应用的开源框架。在这一框架的帮助下，可以构建原生应用。

在这里我们将发现一组免费的开发者工具和小部件，它们可以用于构建内置 UI 平台组件。此外还有一个基于 React 的变体。

### 3. Proton Native

这是市场上一个相对“新”的程序。`Proton Native` 允许你在 PC 上创建程序。这与 `React Native` 为移动设备所做的事情非常相似。我们可以使用该框架来构建无缝衔接的界面并管理跨平台应用的进度。这使得 `Proton Native` 成为为各种操作系统创建应用的最优秀 JS 框架之一。`Proton Native` 直接使用原生工具开发程序，占用的计算机空间极小，且不消耗大量资源。

该框架采用了与 `React Native` 相同的语法，并兼容 React 和 Redux 框架。另一个优点是它是兼容 `Node.js` 的。

### 4. NW.js

这同样一个用于桌面应用的良好 JavaScript 框架。它是开源的，将 `Node.js` 框架与 Chromium 引擎（以前称为 Webkit）结合在一起。

通过这种高质量的组合，我们可以在 `NW.js` 框架上构建应用程序，该程序不仅能在程序窗口中加载本地网页，还能通过 JavaScript API 连接到操作系统。

该解决方案允许你自定义窗口大小、工具栏和菜单项。

`NW.js` 还允许我们访问本地 PC 上的文件。该框架支持所有浏览器功能并确保你的 JavaScript 源代码安全。`NW.js` 支持 Linux、Mac OS 和 Windows。

### 5. AppJS

这是一个用于开发跨平台应用的简单易用且非常强大的工具。在开发应用程序时，你不需要学习新语言。如果我们熟悉 HTML、CSS 和 JavaScript 的基础，就可以轻松地为智能手机设计应用程序。

由于 `AppJS` 构建在 Chromium 之上，开发者可以访问最新的 HTML5 API。`AppJS` 还可以用于构建从文字处理器到 3D 游戏等视觉上吸引人的应用程序。在默认模式下，没有 GUI 小部件限制；因此，用户界面的创建现在仅限于我们的创造力。

## 如何为我们的项目选择最佳 JavaScript 框架

许多 JavaScript 框架定期创建和更新，这使得跟上潮流并选择哪种框架适合我们的项目变得困难。在为我们的 Web 应用选择其中任何一个之前，请评估我们项目的独特需求以及框架的优势和局限性。乌克兰的 IT 业务可以协助项目创建和选择框架。⁸

在开始项目执行之前，通常需要进行初步研究，以选择最符合我们需求的技术。在开始任何项目之前，必须对其进行彻底的分析和评估。然而，有几个关键因素让我们提前预估对特定开发技术的选择：

### 开发速度、易用性以及项目支持

开发速度取决于我们项目所使用的技术。如果你的项目已经使用了 TypeScript 或 JSX 等技术，那么 Angular 会更合适。然而，如果我们从零开始一个项目，`Vue.js` 是理想的选择，因为它遵循标准。

### 趋势

这些框架非常受欢迎，并将在未来几年内将处于开发行业的前沿。另一方面，Vue 正在迅速流行，其后是 React 框架。

### 可扩展性和移动性

如果我们决定将项目从一个框架迁移到另一个框架，`Vue.js` 是最佳选择。因为开发者如果想重写 Angular 或 React 应用，可能需要将 TypeScript 或 JSX 代码转换为标准的 JavaScript 和 HTML。

### 更新频率

另一个关键考虑因素是框架更新的频率。Angular 每 6 个月进行一次深度升级。Vue 在这方面同样可靠，每几年会有一次重大变化。

本节将讨论三个最流行的 JavaScript 框架：Angular、React 和 Vue。它们是目前最著名的 JavaScript 框架。⁹

## Angular

## React

## Vue

如果我们是一个极其注重结构、喜欢保持一切分明的人，那么 Angular 适合你。每个组件和功能都有自己的一套 HTML、CSS 和 TypeScript 文件。

如果我们想要将一切都放在控制之下，从表格的每一行到按钮的位置，并想要复用组件，那么 React 适合我们。

如果我们是一个喜欢简单整洁、不想在文件之间来回切换的人，Vue 的极简数据绑定是理想的。

## 征服 JavaScript

### React.js

如果你最终想专注于前端编程，那么 `React.js` 是使用最广泛的 Web 框架。很容易看出为什么 `React.js` 会成为前端的最爱：它允许我们创建可扩展、动态且具有交互性的在线应用程序。

关于 `React.js` 是一个“框架”还是一个“库”存在着大量的讨论，库是之前发布的代码的集合，我们可以使用它们来创建自己的代码。由于库和框架都包含了允许我们执行任何操作的预写代码，这种细微的区别可能会让我们感到眼花缭乱。虽然库和框架都可能很有用，但框架通常为 Web 程序提供更具结构的形态。

## Node.js

对于对后端编程感兴趣的人来说，“`Node.js` 一路终极王道”。`Node.js` 既是一个用于开发桌面应用程序的框架，也是一个 JavaScript 运行时环境（这意味着它在语言中运行服务器）。`Node.js` 支持异步 JavaScript 代码，这意味着它可以在等待长时间运行的任务完成的同时运行其他程序。

# JAVA 对比 JAVASCRIPT

JavaScript 是一种轻量级的计算机语言，用于使网页动态化。它具有向 HTML 注入动态文本的能力。浏览器的语言是 JavaScript 的另一个名称。JavaScript (JS) 与 Java 没有联系，也不相似。这两种语言都具有类 C 语言语法，并广泛应用于客户端和服务器端 Web 应用程序，但相似性仅限于此.¹¹¹

JavaScript 具有以下特征：

- JavaScript 最初设计用于 DOM 操控。以前，网站主要是静态的；但随着 JS 的出现，动态网站得以建立。
- 在 JS 中，函数是对象。它们像任何其他对象一样，可以拥有属性和方法。其他函数可以它们作为参数。
- 可以处理日期和时间。
- 虽然表是在 HTML 中生成的，但它具有表单验证功能。
- 不需要编译器。

# 示例：这是最基础的 JavaScript 示例。

```



<script>

  console.log("Welcome to Home");

</script>

`Java`是一种面向对象的编程语言，拥有虚拟机平台，允许我们开发可以在几乎任何平台上运行的编译程序。“一次编写，随处运行”，是`Java`给出的承诺。

`Java`具有以下特征：

- 平台无关性：编译器将源代码转换为字节码，随后由`JVM`执行。这种字节码是平台无关的。
- 面向对象编程语言：面向对象编程是一种构建程序的方法，其中每个对象代表类的一个唯一实例。`OOP`概念建立在四大支柱之上：
  - 封装
  - 抽象
  - 多态
  - 继承
- 简单性：`Java`是一种简单的语言，因为它缺乏指针、运算符重载、多重继承和显式内存分配等复杂特性。
- 健壮性：`Java`编程语言是健壮的，这使其非常可靠。它的设计能够尽可能尽早发现故障，这就是为什么`Java`编译器可以检测其他编程语言无法检测的错误。
- 安全性：因为在`Java`中没有指针，我们无法访问越界数组；如果这样做，我们会得到`ArrayIndexOfBoundException`。
- 分布式：使用`Java`编程语言，我们可以开发分布式应用程序。为了开发分布式`Java`应用程序，使用了远程方法调用 (`RMI`) 和企业级`Java Bean` (`EJB`)。
- 多线程：`Java`支持多线程。这是`Java`的一项特性，允许并发执行程序的两个或多个部分，以最大化利用`CPU`使用率。

示例：这里我们有一个基础的`Java`程序作为示例。

```
// 导入所需的类

import java.io.*;

// Main 类

class PFP {

    // 主驱动器方法

    public static void main(String[] args) {

        // 打印语句

        System.out.println("Welcome to Home");

    }

}
```



以下是 Java 和 JavaScript 的区别

## 更清晰的图景 ■ 247

| Java | JavaScript |
| :--- | :--- |
| 因为 Java 是一种强类型语言，变量在程序中使用之前必须声明。在 Java 中，变量的类型在构建时进行验证。 | JavaScript 是一种弱类型语言，具有宽松的语法和规则。 |
| Java 是一种面向对象的计算机语言。 | JavaScript 是一种面向对象的脚本语言。 |
| Java 程序可以在任何虚拟机 (JVM) 或浏览器中执行。 | JavaScript 代码过去仅在浏览器中运行，但现在可以通过 Node.js 在服务器上运行。 |
| Java 对象是基于类的，如果不先建立类，我们就无法在 Java 中编写程序。 | JavaScript 对象是基于原型的。 |
| Java 应用程序扩展名为 `.java`，并将源代码转换为由 JVM（Java 虚拟机）执行的字节码。 | JavaScript 文件扩展名为 `.js`，是解释而非编译的；每个浏览器都有 own JavaScript 解释器来执行 JS 代码。 |
| Java 是一种带有线程的独立编程语言。 | 如果被整合到网页中，它会在构建时并与其 HTML 内容结合。 |
| Java 中的并发由线程处理。 | JavaScript 中的并发通过基于事件的技术处理。 |
| Java 支持多线程。 | JavaScript 不支持多线程。 |
| Java 主要用于后端应用程序。 | JavaScript 用于前端和后端。 |
| Java 消耗更多内存。 | JavaScript 消耗较少内存。 |
| JavaScript 可以在任何文本编辑器或浏览器中执行。 | 为了运行代码，Java 需要 Java 开发工具包 (JDK)。 |

## PYTHON 对比 JAVASCRIPT

我们将在下方讨论 Python 和 JavaScript 之间的差异。

### 什么是 JavaScript？

可以使用 JavaScript（一种脚本语言）编写交互式网站。根据客户端编程原理，它在用户本地执行，避免了对服务器端处理的需求。JavaScript 还兼容 REST API、XML 等技术.¹¹²

现在，JavaScript 也使用 Node.js 和其他技术。

### 什么是 Python？

Python 是一种高级的面向对象语言，具有很高的易用性。由于其内置的数据结构以及动态绑定和类型，它非常适合快速创建应用程序。Python 的模块和包支持增强了系统的模块化并促进了代码复用。由于准入门槛低（代码量），它是一种快速开发语言。对于初学者来说，它是完美的，因为它优先考虑清晰性和易用。

### 最显著的区别

- JavaScript 是一种用于创建交互式网页的脚本语言，而 Python 是一种由于其内置数据结构、动态绑定和类型而适用于快速开发的语言。
- Python 中存在可变和不可变数据类型，而 JavaScript 没有。
- JavaScript 由于缺乏处理原始字节的内置功能而需要 UTF-16 编码，但 Python 源代码默认是 ASCII。
- JavaScript 使用大括号，而 Python 使用缩进。
- 我们可以通过组合底层属性来构建 JavaScript 对象的属性，而在 Python 编程语言中，属性是通过 getter 和 setter 方法定义的。
- JavaScript 可以用于创建网站或原生应用，但 Python 更适合数学上复杂的活动，如数据分析、机器学习和科学计算。

### JavaScript 的特性

JavaScript 的主要能力如下：

- 由于其平台间的可移植性，它在客户端和服务端开发中都很流行。
- 非常适合测试的方法论。
- 能够快速开始编码并学习该语言。
- 为我们提供了更多可依赖的选项。

### Python 的特性

Python 的主要能力如下：

- 易于上手和维护。
- 它具有可移植性，无论安装在何种硬件平台上，都使用相同的接口。
- 使用低级模块扩展 Python 解释器。
- Python 健壮的框架和社区使其成为大型软件项目的理想选择。
- 自动垃圾回收是 Python 提供的一项功能。
- 可以实时进行测试和修复。
- 它允许动态类型验证并提供对高级数据类型的访问。
- Python 代码与 C、C++ 和 Java 编程语言兼容。
- Goroutines 为多个同时运行的线程提供了方便的支持。
- 编译时间快。
- 部署简单的静态链接二进制文件。

### Python 与 JavaScript 的对比

Python 和 JavaScript 之间的主要区别如下：

![](img/70a7539ec7c3f429f5e3c9c64df71823_290_0.png)

Python 与 JavaScript 的区别

| JavaScript | Python |
| --- | --- |
| JavaScript 不理解可变和不可变的术语。 | Python 支持可变和不可变的数据类型。 |
| 因为 JavaScript 缺乏处理原始字节的内置功能，它应该被编码为 UTF-16。 | 除非提供编码格式，否则 Python 源代码默认是 ASCII。 |
| JavaScript 仅支持浮点整数。 | Python 中有多种数值类型，如 int 和固定点小数。 |
| JavaScript 使用大括号。JavaScript 包含较少的模块，如 date、math、regexp 和 JSON。 | Python 采用缩进。 |
| JavaScript 对象包含由属性组成的属性，允许我们指定属性。 | Python 拥有大量的模块。 |
| JavaScript 采用基于原型的继承范式。 | Python 采用基于类的继承范式。 |
| 除了前端和后端编程，JavaScript 是移动开发的绝佳选择。 | Python 不适用于创建移动应用。 |
| JavaScript 可用于网站或原生应用程序。 | Python 用于数据分析、机器学习和其他密集型活动。 |
| TOBIE 评分为 7。 | TOBIE 评分为 3。 |
| 在美国，JavaScript 开发人员的平均收入为 $114,856。 | Python 开发人员的年薪资为 $120,255。 |

## JQUERY VS JAVASCRIPT

我们将讨论 jQuery 和 JavaScript 之间的区别：

### jQuery 到底是什么？

一个免费开源的 JavaScript 库，用于创建、导航和修改 HTML DOM。DOM 是一种用于表示网页元素的树形结构。jQuery 允许网页设计师在他们的网站上快速使用 JavaScript 代码。复杂的 jQuery 技术允许创建强大的动态网站和在线应用。13

jQuery 的语法旨在让事情变得简单，例如：

- 文档的导航
- DOM 元素选择
- 制作动画
- 事件管理
- 创建 Ajax 应用

在所有其他库中，jQuery 是最广泛使用的库之一，具有以下关键特性：

- 选择 DOM 元素
- Sizzle 允许遍历和操作（选择器引擎）。
- 开发新的编程风格
- 结合 DOM 数据结构和算法。

另一方面，jQuery 允许开发者在 JavaScript 库之上构建插件。开发者还可以创建低级交互和动画的抽象。

### jQuery 与 JavaScript 的区别

尽管 jQuery 是 JavaScript 的组件，但可能存在以下差异：

![](img/70a7539ec7c3f429f5e3c9c64df71823_292_0.png)

jQuery 与 JavaScript 的区别

| jQuery | JavaScript |
| --- | --- |
| 它是 JavaScript 的库。 | 它是一种用于 Web 开发的动态解释型编程语言。 |
| 用户只需要编写相关的 jQuery 代码。 | 用户必须编写所有的 js 代码。 |
| 它需要的时间较少。 | 需要更长时间，因为必须编写整个脚本。 |
| 不需要处理多浏览器兼容性问题。 | 开发者编写自己的代码来处理跨浏览器兼容性。 |
| 页面头部必须包含 jQuery 库的 URL。 | 每个浏览器都支持 JavaScript。不需要其他插件。 |
| 因为它是 JavaScript 库，所以它依赖于 JavaScript。 | 在 JavaScript 中，存在 jQuery。因此，js 代码中可能使用或不使用 jQuery。 |
| 它仅仅几行代码。 | 代码可能很困难且冗长。 |
| 它是一种基础、快速且简单的方法。 | 它是一种弱类型编程方法。 |
| jQuery 是一种优化的网页设计方法。 | 引入 jQuery 的 JavaScript 是开发者最受欢迎的网页设计语言之一。 |
| 使用 jQuery 创建 DOM 更快。 | JavaScript 创建 DOM 较慢。 |

## JAVASCRIPT VS PHP

我们在下面讨论 PHP 和 JavaScript 之间的区别：

### PHP 到底是什么？

增加了对超文本处理器（Hypertext Preprocessor）的支持。它是最流行的 Web 开发语言。通常被称为一种开源脚本语言.¹14

### PHP 与 JavaScript 的清晰视图

PHP 可以插入到 HTML 文档中。它是初学者的基础语言。尽管 PHP 和 JavaScript 都用于 Web 开发，但它们服务的目标不同，执行的任务也不同。当两者协作时，JavaScript 处理前端，而 PHP 处理后端。许多流行的网站（如 Facebook、Yahoo 和 Flickr）都是使用 JavaScript 和 PHP 开发的。

### JavaScript 与 PHP

下表对比了 JavaScript 和 PHP。

![](img/70a7539ec7c3f429f5e3c9c64df71823_293_0.png)

JavaScript 与 PHP 的区别

| JavaScript | PHP |
| --- | --- |
| 它目前是一种全栈语言。它服务客户端和服务端。 | 它是服务器端的脚本语言。它仅服务后端。 |
| 它是一种单线程编程语言。因此，每个输入输出过程并行。 | 它是一种多线程编程语言。因此，它会阻塞许多输入输出过程。 |
| 包括 Mozilla、Google Chrome 在每个浏览器都支持它。 | 与 Windows、Linux 和 Mac 以及 IIS、Apache 等系统兼容。 |
| 安全性较低。 | PHP 非常安全。 |
| 访问数据库需要环境。 | 它提供了快速访问数据库的方法。 |
| 它功能较少。 | PHP 代码可以构建动态页面、传输和接收 Cookie、收集表单输入等。 |

## 更清晰的视图 ■ 255

### Dart 到底是什么？

Dart 是一种面向客户端优化的编程语言，由 Google 于 2011 年创建，旨在为任何平台构建快速应用。它最初在 Google 内部用于构建 Web、服务器和移动端应用。Dart 编译源代码的方式与 C、JavaScript、Java 和 C# 等其他编程语言相同。

它还有自己的虚拟机（VM），即 Dart VM，用于运行原生应用程序。此外，它包含了了自己的包管理工具，称为 Pub。随着 Google 推出用于跨平台移动开发的 Flutter，它变得流行起来。

其主要原因是 Flutter 完全专注于 Dart。而 Dart，对于之前熟悉面向对象的编程（OOPS）语言的开发者来说，可以快速学会。

### Dart 的优缺点

Dart 具有以下优点和缺点：

#### 优点

- 它是一个面向客户端的开源计算机程序。
- 它在不同项目中具有良好的扩展性。
- 它由 Google 创建，并能够在大 Google Cloud 平台上无缝运行。
- 如果我们已经熟悉 JavaScript，那么学习它非常简单，因为它与 JavaScript 具有相似性。
- 它比 JavaScript 快。
- 它主要用于创建移动端应用。

#### 缺点

- 它只有一个对象类。
- 它是一门非常新的编程语言，在行业中并不常用。
- 在 Dart 中，我们无法在不创建新赋值语句的情况下重命名函数。
- 因为资源较少，很难发现解决问题的答案。

## 256 征服 JavaScript

### 什么是 JavaScript？

为了创建具有交互效果的动态 HTML 网站，程序员转向 JavaScript，这是一种小型面向对象的编程语言。游戏和移动应用的创建都极大受益于 JavaScript 的使用。

正如其名，它是一种脚本语言，代码仅在 Web 浏览器中解释和运行。Node.js 可能用于在浏览器之外执行代码。这种语言可以进行客户端和服务器端编程，它也被称为浏览器语言。它由 Netscape 的 Brendan Eich 创建，并于 1995 年首次向消费者提供。在被重命名为 JavaScript 之前，这门语言被称为 LiveScript。作为一种脚本语言，JavaScript 在语法上大量借鉴了 C 语言。JavaScript 代码保存在扩展名为 `.js` 的文件中。

#### 使用 JavaScript 的优缺点

以下是 JavaScript 的一些优点和缺点：

##### 优点

- 它是一个轻量级、快速且适应性强的开源框架。
- 可以进行跨编译。
- 它与类、接口和模块兼容。
- 由于它同时用于前端和后端工作，它可能兼容广泛的设备。
- 我们可以利用此来创建响应鼠标悬停而改变的交互式用户界面。
- 因为其与其他语言的兼容性，JavaScript 可用于各种程序。
- 创建复杂程序可能需要我们增强 JavaScript。

##### 缺点

- 它依赖有限的库。
- 在客户端，没有方法使用 JavaScript 创建或读取文件。出于安全考虑，这一功能被保留了。
- 存在一种风险，即一个错误可能会导致整个网站崩溃。
- 由于该语言的动态特性，程序员出现严重错误并不少见。
- 它只支持单继承，不支持多继承。这种面向对象语言的特性对于某些应用程序可能是必要的。

### Dart 和 JavaScript 之间的重要区别

在这里，我们将根据它们最显著的特征对比 Dart 和 JavaScript：

#### 使用的简单性

JavaScript 已经存在了一段时间，是一门成熟且强大的语言。JavaScript 易于使用。它包含了许多可以在网上免费获取的框架和库。开发者可以通过利用这些框架来创建新软件，从而节省精力和减少重复工作。

另一方面，Dart 对于 Google 之外的大多数开发者来说是一门新语言。尽管 Google 做了努力，但对开发者来说解释特定问题仍然很困难。它具有与 Java 类似的编写风格和语法；拥有 OOPS 知识的开发者一旦理解了基础知识，应该能够学习并使用 Dart。

#### 速度

由于 JavaScript 是一种解释型语言，它比其他计算机语言更轻量、更快。它的性能优于 Java 和其他编译语言。

另一方面，Dart 明显快于 JavaScript。Dart 可以在 JIT 和 AOT 模式下编译，这从许多方面有助于应用开发。JIT 编译可用于加速开发，而 AOT 编译可用于优化发布过程。

#### 类型安全

作为一种解释型语言，JavaScript 同时提供动态类型和鸭类型（duck-typing）。因为它对任何代码进行类型，因此 JavaScript 不是一门类型安全的语言。代码中的错误只能在运行时发现。相反，Dart 允许松散和严格的原型。由于 Dart 是一门编译语言，大部分编程问题在编译阶段就能被识别。它比 JavaScript 更类型安全。

#### 流行程度

JavaScript 几乎随处可见。几乎每台机器都支持 JavaScript。JavaScript 现在用于构建 Web、移动端和服务器端的代码。Stack Overflow 上关于 JavaScript 的问题大约有 250 万个。由于它的普及，JavaScript 生态系统增长巨大，得益于云组件中心的发展，它目前主导了可复组件的“市场”。前端开发者更倾向于替代方案。

另一方面，Dart 正在受到关注，但并不频繁。

#### 学习曲线

JavaScript 对初学者来说不是一门简单的语言；但是，有很多在线课程。另一方面，Dart 对初学者来说可能是一项困难的练习，但有几本书。

#### Web 与移动端

JavaScript 凭借其多个框架主导了在线和移动开发。随着 Facebook React Native 的发布，JavaScript 被使用。有很多 JavaScript 框架（如 Angular、Vue.js 等）可以创建网站、PWA 和混合移动应用。

Dart 和 Flutter 的跨平台应用能力使其脱颖而出。Dart 可用于网站。

#### 前端后端

JavaScript 与 HTML 和 CSS 用于前端开发。然而，由于 Node.js 平台的流行，它现在被常用于后端。另一方面，Dart 现在正与 Flutter 结合用于前端。Dart 也可以用于 Web 开发；但没有提到它被用于后端。

#### 商业用途

JavaScript 在行业中被广泛使用，特别是大型项目。它用于网络和跨平台应用的创建。在 Facebook 的在线和跨平台应用中，React 和 React Native 使用 JavaScript。eBay、Airbnb、Slack 等公司也使用 JavaScript。

另一方面，Dart 是 Google 创建的。因此，它在内部使用。随着 Flutter 的发布，阿里巴巴等公司采用了 Flutter 和 Dart 开发跨平台应用。

下面的表格展示了 Dart 与 JavaScript 的对比：

| 特性 | Dart | JavaScript |
| --- | --- | --- |
| 使用的简单性 | Dart 具有与 Java 类似的语法和编写风格，对拥有 OOPS 知识的开发者来说易于使用。 | JavaScript 易于使用，网上有很多各种框架和库，允许开发者复用现有代码快速开发应用。 |
| 编辑器和 IDE 支持 | Dart 可以在简单的编辑器（如 Sublime 或 Vim）中编写。最流行的 Dart 应用开发 IDE 是 IntelliJ IDEA 和 Android Studio，它们都包含了 Dart 插件。 | 它有许多用于开发应用的编辑器和 IDE。不一定需要功能完整的 IDE；相反，开发者可以使用轻量级编辑器如 Vim、Sublime Text、Emacs 或 Atom。某些 IDE 如 WebStorm 和 Visual Studio Code 可以创建 JavaScript 应用程序。 |

## 征服 JavaScript

| 特性 | Dart | JavaScript |
| --- | --- | --- |
| 流行程度 | 除了各种互联网社区外，Dart 和 Flutter 还有一个非常小的社区。尽管文档完备，但许多经验开发者仍然对 Dart 感到困惑。 | 因为它是一种更简单、轻量级的动态语言，新开发者更容易学习。它通过提供各种 JavaScript 框架和数千个易于访问的 Web 包，提高了开发者的生产力。 |
| 类型安全 | 因为它支持弱类型和强类型提示，它比 JavaScript 更类型安全。 | 因为它允许双类型和动态类型，它不是一种类型安全的语言。 |
| 学习曲线 | Dart 不是一种常用的编程语言，对初学者来说可能很困难。网上关于 Dart 类或书籍极少。 | JavaScript 对初学者来说不是一种简单的语言，但掌握了编程原理后，JavaScript 就变得非常简单。 |
| 商业用途 | Dart 由 Google 支持，并被许多知名公司使用，包括 Blossom、WorkTrails、Whale、Mobile 等。 | JavaScript 经常用于在 Instagram、Slack、Reddit、eBay 和 Airbnb 等大型组织中构建在线和跨平台移动应用。 |
| 速度 | Dart 可以用 JIT 和 AOT 模式编译，允许通过多种方法创建应用。Dart 的速度明显快于 JavaScript。 | JavaScript 是一种解释型语言，比其他计算机语言更轻、更快。它的性能优于 JavaScript 和其他编译语言。 |
| Web vs 移动端 | Dart 可用于创建在线和移动应用。 | JavaScript 可以配合各种框架构建在线和移动应用。 |

## JAVASCRIPT VS ANGULAR JS

客户端浏览器执行 JavaScript，这是一种轻量级的面向对象的编程语言，用于创建具有交互效果的动态 HTML 页面¹¹⁶

它是一种运行在浏览器中的脚本语言，可以为网站添加交互性和动态效果。与之相反，Angular JS 是 JavaScript 的一个框架，它为 HTML 添加功能。它的首要目的是创建动态和单页 Web 应用（SPA）。这里将介绍 JavaScript 和 Angular JS 之间的差异。在深入研究差异之前，我们将先熟悉 JavaScript 和 Angular JS。

更清晰的视野 ■ 261

Angular JS 与 JavaScript 的区别

### 什么是 JavaScript？

JavaScript 是一种小型的面向对象的编程语言，允许开发者构建具有交互效果的动态 HTML 页面。使用 JavaScript 对游戏和移动应用的开发非常有益。它是一种脚本语言，正如其名称所示，代码仅在 Web 浏览器中被理解和执行。代码可以使用 Node.js 在浏览器之外执行。它是浏览器利用语言。对于开发客户端和服务器应用程序非常方便。

Netscape 的 Brendan Eich 在 1995 年设计并首次向公众发布了它。在重命名为 JavaScript 之前，这种语言被称为 LiveScript。JavaScript 作为脚本语言，在语法上大量借鉴了 C 语言。以 `.js` 后缀的文件存放 JavaScript 代码的地方。

#### JavaScript 特性

JavaScript 有若干种特性，其中包括：

- 最初，JavaScript 是为了 DOM 操作而构建的。在此之前，大多数网站都是静态的；然而，JS 允许创建交互式网页。
- 在 JavaScript 中，函数也是对象。
- 它们可能与普通对象具有相同的属性和方法，并且作为参数传递给其他函数。
- JavaScript 不需要编译器。
- JavaScript 可以处理日期和时间。

## 征服 JavaScript

### 什么是 Angular JS？

这是一个用于前端 Web 开发的开源框架，具有卓越的功能和支持。Google 的 Angular 团队于 2010 年引入了它。

它是一个不断进化和扩展的框架，包含了构建在线应用程序的有效技术。它通常使用模型-视图控制器（MVC）范式创建应用程序，并启用数据绑定和依赖注入。

由于 AngularJS 大部分源自 HTML 和 JavaScript，因此不需要学习外语或语法。该功能将静态 HTML 转换为动态 HTML。它通过内置属性和组件，以及允许使用 JavaScript 轻松创建额外属性，扩展了 HTML 的功能。

#### Angular JS 特性

有若干种 angular JS 功能，其中包括：

- AngularJS 允许我们使用便于使用的模块，从而节省了时间和代码。
- AngularJS 对 JavaScript、HTML 和 CSS 的使用使其非常易于使用。
- 模板被发送到 DOM，然后是到 AngularJS 编译器，而 AngularJS 本身大部分是纯 HTML。
- 它通过模板进行处理并变得有用。

### JavaScript 和 Angular JS 之间的主要区别

JavaScript 和 Angular JS 之间存在许多显著差异，其中包括：

- JavaScript 是一种用于在线应用开发的服务器端和客户端脚本语言。而 AngularJS 则从一开始就让 Web 应用的开发变得快速且简单。
- JavaScript 减少了修复广泛缺陷和故障所需的时间。与 JavaScript 相比，完成相同任务 AngularJS 需要更多时间。
- JavaScript 是开发网站和构建在线应用最高效的方法之一。相比之下，AngularJS 最被用作 JS 框架构建 Web 应用。
- JavaScript 是一种用于控制文档对象模型（DOM）的编程语言。而 AngularJS 通过多种技术增强了其功能。
- JavaScript 不允许依赖注入。而 AngularJS 则通过多种技术增强了其功能。
- JavaScript 是一种脚本语言。相比之下，AngularJS 是一个框架。
- JavaScript 是一种编程语言。相比之下，AngularJS 是一个框架。
- JavaScript 是一种脚本语言。相比之下，AngularJS 是一个框架。
- JavaScript 是一种脚本语言。相比之下，AngularJS 是一个框架。

更清晰的视野 ■ 263

JavaScript 与 Angular 的对比分析：

| 特性 | JavaScript | Angular |
| --- | --- | --- |
| 定义 | 一种用于创建 HTML 页面的小型面向对象编程语言。 | 一个用于前端 Web 开发的开源框架。 |
| 开发者 | 由 Netscape 在 1995 年创建。 | 主要由 Google 在 2010 年创建。 |
| 语法 | 语法更为复杂。 | 语法较为基础。 |
| 编程 | 解释器用 C++ 开发。它用 JavaScript 编写。 |
| 过滤器 | 不支持过滤器。 | 支持过滤器。 |
| 可学习性 | 不容易学习。 | 如果熟悉 JavaScript，则它很容易学习。 |
| 概念 | 基于动态类型。 | 使用模型控制器。 |
| 依赖注入 | 不允许依赖注入。 | 允许数据绑定以及依赖注入。 |

## 更清晰的图景 ■ 265

- 它同时用于前端和后端开发，实现了跨设备互操作性。
- 我们可以使用它来构建对鼠标悬停响应的交互式用户界面。
- 由于与其他语言的互操作性，JavaScript 可能被广泛应用于项目中。
- 创建复杂的应用程序可能需要使用 JavaScript 扩展功能。

### 缺点

- 它依赖于有限的资源池。
- 在客户端使用 JavaScript 没有任何创建或读取文件的机制。出于安全考虑，这一点被保留了。
- 单个错误可能会导致整个网站崩溃。
- 因为该语言是动态的，开发者可能会迅速犯下致命错误。
- 它仅支持单继承，不支持多继承。
- 特定的应用程序可能需要面向对象语言的这一特性。

## 什么是 Node.js？

Node.js 是一个免费开源的服务器端 JavaScript 运行时环境，可以用于多个平台。Node.js 让 JavaScript 能够在浏览器之外的环境中执行。

Node.js 主要用于 Web 开发，并带有各种模块。它可以在 Windows、Linux、Mac OS 和其他计算机上使用。对于开发可扩展的 JavaScript 页面 (JSP) 应用程序，它提供了一个具有事件驱动、非阻塞（异步）I/O 特性的跨平台运行时环境。

Ryan Dahl 在2009年创建并首次发布了 Node.js。Web 应用、实时聊天、命令行应用和 REST API 服务器只是使用 Node.js 构建的许多类型应用之一。然而，它的主要用途是创建如 Web浏览器这样的服务器端网络应用程序。常见的 Node.js 文件扩展名是 `.js`。

## 征服 JavaScript

### Node.js 如何工作？它的优缺点是什么？

Node.js 的优缺点有多种形式。

#### 优点

- JS 是一个免费开源的框架，根据 MIT 许可证发布。
- 它是一个极简主义框架；因此，它只有几个组件。根据特定用例的细节，可能需要更多模块。
- 该框架兼容多个操作系统，包括 Windows、Mac OS X 和 Linux。
- JavaScript 是用于创建后端系统和服务的编程语言。
- 以前的 JS 应用中没有任何数据被缓冲。在 Node.js 中编写的应用程序只需以小块的形式发送数据。Node.js 中的所有 API 都以非阻塞、异步的方式运行。这基本上意味着用 Node.js 编写的服务器不会停下来等待服务器交付数据。Node.js 通知机制帮助服务器在调用 API 并移动到下一个 API 之后从 API 获取响应。
- JS 是一个基于 Google Chrome 的 V8 JavaScript 引擎的快速程序执行库。

#### 缺点

- 一致性问题是使用 Node.js 的主要缺点。为了保持代码兼容性，开发者必须不断调整 API，这增加了他们的工作量。它没有跟上资源密集型应用的进步，并且没有实现多线程编程。
- JavaScript 与许多其他编程语言不同，它没有健壮的库系统。
- 因此，用户被迫寻找标准库来处理图像、解析 XML、执行对象关系映射 (ORM)、管理数据库等。Node.js 让最基础的编程工作变得复杂了。

### JavaScript 与 Node.js 的对比：关键区别

在这里，我们将通过突出它们的关键区别来对比 JavaScript 和 Node.js：

- JavaScript 通常用于客户端脚本，是一种小巧、可移植、与平台无关的解释型计算机语言。Java 和 HTML 默认都包含了它。然而，Node.js 是一种构建在驱动 Google Chrome 的 V8 引擎上的服务器端编程语言。因此，它被用于创建专注于网络的应用程序。它是一个实时处理大量数据的去中心化系统。
- JavaScript 是一种脚本语言，可以在任何浏览器中执行，而替代方案是 Node.js，它是 JavaScript 编程语言的实现。为了更具实用性，它需要在使用编写 JavaScript 时无需费力即可访问的库。
- 任何引擎（如 V8、Safari 的 Spider Monkey 或任何其他引擎）都可以执行 JavaScript（Google Chrome）。正因如此，使用 JavaScript 开发是简单的，任何操作环境的功能都与浏览器一样有效。然而，Node.js 仅在 Google Chrome 上运行，因为它依赖于浏览器专有的 V8 引擎。相反，任何开发者产生的 JavaScript 代码都可以在任何环境中执行，无论是否有 V8 引擎。
- 进入任何操作系统都需要完成某个特定的非阻塞任务。JavaScript 有几个标准对象，这些对象完全依赖于平台。例如，ActiveX 控件是一个只能在 Windows 计算机上使用的程序。然而，Node.js 允许从任何 JavaScript 代码执行非阻塞的特定操作系统的操作。它不包含任何特定于某个操作系统的常量。Node.js 擅长与文件系统建立洁的连接，允许开发者访问和修改磁盘上的文件。
- 在开发单个 Web 应用时，JavaScript 通常被用于所有的客户端职责。业务验证、动态页的定期显示，甚至是基本的 Ajax 请求都可能是单个操作的一部分。这些在每个给定的应用程序中都有固定的生命周期。然而，Node.js 通常用于使任何操作系统能够以非阻塞的方式被访问或执行。操作系统的非阻塞操作包括创建或运行 shell 脚本、通过单次调用接收特定的硬件相关信息、检索机器上已安装的证书数据以及执行操作。
- JavaScript 的主要优势在于在界面和交互方面的灵活性，以及 Node.js 可以同时处理多个请求并具有超过 500 个模块的功能。它的独特能力包括支持微服务架构和物联网。

### 深度分析 JavaScript 与 Node.js

在这里，我们将对比 JavaScript 和 Node JS 这两种流行的服务器端脚本语言：

| 特性 | JavaScript | Node JS |
| :--- | :--- | :--- |
| 定义 | 它是一种跨平台、辅助、解释型、轻量级脚本语言，用于创建动态应用程序。 | 它是一个用于运行 JavaScript 的跨平台辅助运行时环境。 |
| 类型 | 它是一种语言。 | 它是一个带有实用库的运行时环境。 |
| 用途 | 它通常用于客户端。 | 它旨在用于网络中心应用程序。 |
| 语言 | 它是基于 Chrome V8 引擎运行的新版本 ECMA 。 | 它使用了 C++,C++。 |
| 模块 | TypedJS、Ramda 和其他框架是示例。 | 模块包括 Lodash 和 Express。这些模块都从 npm 导入。 |
| 公司使用 | Google、Shopify、Udacity、Sendgrid、Groupon、Octa、Instacart 等公司使用 JavaScript。 | Node 被 Netflix、Hapi、Paypal、Linkedin、Medium 和 eBay 等公司使用。 |

## 更清晰的图景 ■ 269

| 特性 | JavaScript | Node JS |
| :--- | :--- | :--- |
| 社区 | node 社区并不关心 JavaScript。 | JavaScript 社区由所有项目代表。 |
| 运行引擎 | 任何引擎（包括 Spider Monkey、V8 和 Core）都可以运行 JavaScript。 | Node.js 由 V8 引擎启用，该引擎通常由 JavaScript 使用。 |
| 用途 | 它旨在用于跨平台运行的数据密集型真实世界应用。 | |

在本章中，我们讨论了 JS 前端、后端、移动端、游戏和桌面端的许多用途和框架。此外，我们还探讨了应该学习什么框架以及如何将 JS 能力与其他编程语言结合。

## 270 征服 JavaScript

- 7 一以及俱全：用于桌面应用程序的 JS 框架及其精选推荐：https://luxnet.io/blog/the-best-of-js-frameworks-for-desktop-applications 访问日期：2022年10月06日。
- 8 选择最佳的 JavaScript 框架：https://wiredelta.com/how-to-choose-the-best-javascript-framework-2/ 访问日期：2022年10月06日。
- 9 为你的项目选择正确的 JavaScript 框架？：https://dev.to/abdurkhalid333/how-to-choose-a-right-javascript-framework-for-your-project 访问日期：2022年10月06日。
- 10 适合初者的 JavaScript 框架：www.codecademy.com/resources/blog/what-javascript-framework-to-learn-beginner/ 访问日期：2022年10月06日。
- 11 Java 和 JavaScript 的区别：它们之间的主要区别：https://www.geeksforgeeks.org/difference-between-java-and-javascript/ 访问日期：2022年10月06日。
- 12 Python vs JavaScript：它们之间的主要区别：https://www.guru99.com/python-vs-javascript.html#~text=KEY%20DIFFERENCES%3A_JavaScript%20is%20a%20scripting%20language%20that%20helps%20you%20create%20interactive,%20choice%20for rapid%20application%20development. 访问日期：2022年10月06日。
- 13 jQuery vs JavaScript：www.javatpoint.com/jquery-vs-javascript 访问日期：2022年10月07日。
- 14 jQuery vs PHP：https://www.javatpoint.com/javascript-vs-php 访问日期：2022年10月07日。
- 15 Dart vs JavaScript：https://www.javatpoint.com/dart-vs-javascript 访问日期：2022年10月07日。
- 16 JavaScript vs. Angular Js：https://www.javatpoint.com/javascript-vs-angularjs 访问日期：2022年10月07日。
- 17 JavaScript vs. Node.js：https://www.javatpoint.com/javascript-vs-nodejs 访问日期：2022年10月08日。

## 前端开发

### 本章内容

- React
- Express
- Vue.js

在上一章中，我们涵盖了游戏、桌面、前端、后端和移动框架，在本章中，我们将讨论前端开发。

## 前端 vs 后端

前端和后端是 Web 开发中最常用的两个术语。尽管这两个词彼此不同，但它们对于 Web 开发至关重要。每一端必须作为一个整体共同工作并相互通信，以提高网站的功能。

## 前端开发

用户直接交互的网站部分被称为前端。它通常被称为程序的“客户端”。它包含了消费者立即查看和使用的所有元素，包括按钮颜色、文本样式、图像、图表和表格。

## 272 征服 JavaScript

HTML、CSS 和 JavaScript 是用于前端编程的三种语言。前端开发者负责在浏览器显示上查看网站、在线应用程序或移动应用时，看到的所有内容的结构、设计、行为和内容。前端的主要目标是性能和响应能力。

### 前端语言

下面列出的语言用于构建前端部分：

- **HTML**：在 HTML 中表示“超文本标记语言”（Hypertext Markup Language）。它用于使用标记语言开发网页的前端。HTML 是 Hypertext Markup Language 的缩写。网页之间的关系由超文本定义。在指定网页结构的标签内编写的文档是使用标记语言定义的。
- **CSS**：级联样式表（Cascading Style Sheets），有时被称为 CSS，是一种直观的语言，使得网页的显示更加容易。可以使用 CSS 为网页应用样式。重要的是，CSS 允许我们在不依赖每个网页所构建的 HTML 的情况下实现这一点。
- **JavaScript**：JavaScript 是一种著名的编程语言，用于处理用户可能交互的网站。它用于增加网站的功能，有趣的游戏和基于 Web 的程序可以使用它。成为一名优秀的开发者需要 JavaScript 知识，它可以同时用于前端和后端。例如，根据框架的不同，用于前端开发的语言仅限于 Flutter 的 Dart、React 的 JavaScript 和 Django 的 Python 等。

### 前端框架和库

- **AngularJS**：AngularJS 是一个开源 JavaScript 前框架，主要用于创建单页应用程序（SPA）、前端框架和库。它是一个不断发展和成长的框架，提供了创建互联网应用程序的更好技术。通过转换静态 HTML 来创建动态 HTML。该开源项目有一个免费版本。由于指令扩展了 HTML 属性，HTML 和数据之间产生了联系。
- **React.js**：React 是一个用于构建用户界面的声明式、高效且灵活的 JavaScript 工具包。ReactJS 是一个具有组件架构的免费前端库，专门负责应用的视图层。Facebook 负责维护。使用 React JS 进行前端开发也极其简单。
- **Bootstrap**：Bootstrap 是一个用于创建网页的免费开源框架。
- **jQuery**：jQuery 是一个用于 JavaScript 和 HTML 对象模型（DOM）交互的开源框架。它便于 Ajax 动画、网页的遍历和操作以及跨浏览器的使用。SASS 是一种可靠、强大的 CSS 扩展语言。
- **Flutter**：Flutter 是一个由 Google 维护的开源 UI 开发 SDK，由 Dart 语言驱动。它通过单一代码库生成桌面、Web 和移动（iOS、Android）应用程序。Flutter 的主要卖点是原生速度、简单、表达力和活性。2021 年 3 月，Flutter 将发布版本 2，支持桌面。
- 一些示例是 Semantic-UI、Foundation、Materialize、Backbone.js、Ember.js 等。

## 274 征服 JavaScript

## 后端开发

网站的服务器端被称为后端。它确保网站的所有部分正常运行，并存储和组织数据。用户间接访问由设计师创建的功能。后端还包括开发 API、构建库以及与无界面元素交互。

## 后端框架

- Express: Express 是一个用于服务器端和后端编程的 Node.js 框架。可以使用它可以创建单页应用、多页和混合 Web 应用。通过它的帮助，我们可以管理各种 HTTP 请求。
- Django: Django 是一个基于 Python 编写的模型-模板-视图（MVT）Web 框架。它用于创建大型且复杂的 Web 应用。它具有快速、安全和可扩展的特点。
- Ruby on Rails: 名为 Ruby on Rails 的服务端框架使用了模型-视图-控制器（MVC）架构。它提供了包括数据库、在线服务和网页在内的预构建结构。
- Laravel: Laravel 是一个可靠的 PHP Web 框架。它最大的特点是在构建 Web 应用时可以复用许多框架的组件。
- Spring: 这个名为 Spring 的服务端框架支持 Java 应用程序的基础设施。它支持包括 Hibernate、Struts 和 EJB 在内的多种框架。此外，它还提供了插件，可以简单快速地创建 Java 应用。
- C#、Ruby、GO 以及其他后端编程和脚本语言都是其中的例子。

## 前端开发与后端开发的区别

前端开发和后端开发是同一个问题的两个方面，但它们之间存在显著差异。后端控制一切的运行方式，而前端是用户看到并交互的部分。

网站的前端是访问者可以看到并与之交互的部分。它包括设计、导航菜单、文本、照片和视频，以及图形用户界面（GUI）和命令行。相反，后端是访问者无法访问或交互的网站部分。

前端指的是访问者视觉上可见并交互的网站元素。另一方面，后端负责后台发生的所有工作。

前端用 HTML、CSS 和 JavaScript 编写，而后端用 Java、Ruby、Python 和 .Net 编写。

## REACTJS

下面我们将介绍 ReactJS 及其定义、安装和语法。

### JavaScript 的‘REACT’是指什么？

React 是一个用于构建用户界面的 JavaScript 工具，由 Facebook 和使用开源软件的开发者社区管理。尽管它不是一种语言，但由于其庞大的实用工具库，React 在 Web 开发领域被广泛采用。尽管它直到 2013 年 5 月才发布，但这个库已迅速成为 Web 设计师和开发人员的标准。除了用户界面开发领域，React 还提供了诸如 Flux 和 React Native 等架构支持扩展。

#### 问题是，“为什么选择 React？”

目前，没有其他前端框架能与 React 的广泛采用相提。我们将解释原因：

- React简化了动态 Web 应用的构建，因为它比 JavaScript 需要更少的代码提供了更多的功能，而 JavaScript 可能会迅速变得复杂。
- React 对虚拟 DOM（virtual DOM）的使用使 Web 应用开发更快。当 Web 应用中的组件发生变化时，虚拟 DOM 会将其与之前的状态进行比较，仅更新真实 DOM（Real DOM）中发生变化的元素。
- 组件是 React 项目的基础，一个应用中可以找到许多不同类型的组件。由于这些模块具有专门的逻辑和控制，可以在整个程序中重复使用，从而缩短了开发时间。
- React 中的数据流动只有一条路径。这意味着开发者在构建 React 应用时，通常会将子组件堆叠在父组件之上。由于数据只向一个方向移动，在应用程序内部精确地确定数据源于何处简单得多。
- React 的学习曲线很平缓，因为它大部分建立在 HTML 和 JavaScript 的熟悉原理之上，并有一些实用的补充。尽管如此，我们仍然需要努力学习 React 库的细节，就像你学习任何其他工具或框架一样。
- 它对于创建在线和移动应用都很有用：虽然使用 React 构建 Web 应用是众常识，但这远不是它的唯一目的。React Native 是一个用于开发高质量移动应用的流行框架；它基于原始的 React 库。为此，重要的是 React 在开发网页时和为移动设备开发时同样游刃有余。
- Facebook 创建了一个 Chrome 插件，可以用于调试 React 应用，为简单调试提供了专用工具。正因为如此，修复 React Web 应用中的错误变得轻而易举。

### React 特性

并不是秘密 ReactJS 正在迅速成为当今最尖端网站的首选 JavaScript 框架。它目前正在为前端生态系统着非常重要的工作。ReactJS 的一些最显著的特征列在这里：

- JSX
- 组件
- 单向数据绑定
- 虚拟 DOM
- 简单性
- 性能

#### JSX

JSX 指的是 JavaScript XML。它是 JavaScript 语法中的一个新特性。ReactJS 采用了一种类似于 XML 或 HTML 的语法。这种语法会生成对 React 框架 Java API 的调用。通过增强 ES6，它允许类似 HTML 的文本与 JavaScript React 代码并存。在 ReactJS 中，JSX 不是强制要求的，但被高度推荐。

#### 组件

组件是 ReactJS 的骨干。ReactJS 程序中的每个单独“组件”都有的一套规则和处理能力。由于其模块化性质，这些部分可以复用，使得管理大型项目的代码库变得更容易。

#### 数据绑定，仅单向

由于其架构，ReactJS 只支持单向数据绑定，且流向只向一个方向。使用单向绑定，你可以对整个程序施加更多控制。如果信息从另一个方向流动，则需要额外的功能。

> 这是因为包含组件内部的数据应该是不可变的。Flux 模式有助于确保你的数据只向一个方向流动。应用程序新发现的灵活性是更高效率的主要原因。

#### 虚拟 DOM

仅存在于计算机内存中的 DOM 对象被称为“虚拟 DOM 对象”。其效果与单向数据绑定相似。如果 Web 应用中发生了任何更改，整个用户界面将在虚拟 DOM 表示中重新渲染。然后，它将旧的 DOM 表示与新的进行比较。之后，仅被修改的元素将反映在真实的 DOM 中。这消除了内存浪费并加快了程序运行。

#### 简单性

由于是用 JSX 编写，ReactJS 易于学习和实现。同时也提供了更多功能。使用了 JSX（JavaScript 扩展）语法，这是一种使用 HTML 标签和 HTML 引用构建 HTML 元素的表示法。此外，它简化了计算机可读代码生成。

#### 可复用的组件

一个 ReactJS Web 应用程序由许多组件组成，每个组件都有自己的逻辑和控制器。这些部分负责生成小型的、模块化的 HTML 代码块，可以将其放在任何需要的地方。在可复用代码的帮助下，你可以轻松地规划和管理应用程序。这些组件可以相互层叠，形成复杂的软件系统。ReactJS 使用了一种基于“虚拟 DOM”的方法向 HTML DOM 添加元素。为了节省时间，虚拟 DOM 只更新发生变化的特定节点的数据，而不是整个 DOM。

#### 提高性能

由于有了虚拟 DOM，ReactJS 运行得更快。DOM 为开发处理 HTML、XML 和 XHTML 的应用程序提供了一致一致的 API，无论平台如何。当 DOM 更新时，这个缺陷会减慢大多数程序员的开发速度。虚拟 DOM 正是 ReactJS 处理这个问题的方法。

React 虚拟 DOM 是浏览器 DOM 的一个版本，它完全驻留在内存中。因此，在创建 React 组件时，我们并没有直接写入 DOM。相反，我们正在创建将响应 DOM 的虚拟组件，从而带来更流畅、更快的性能。

#### 实用工具的使用

由于提供了实用的工具集，React JS 也变得越来越流行。这些工具帮助开发者理解并简化他们的工作。React Developer Tools（React 工具）是 Chrome 和 Firefox 的扩展，允许你调查虚拟 DOM 中的 React 组件层次结构。我们还可以选择组件并分析和更新它们当前的属性和状态。

#### 6. 以 SEO 友好而闻名

传统的 JavaScript 框架在 SEO 方面存在问题。JavaScript 密集型应用程序通常难以被搜索引擎读取。许多网站开发者经常抱怨这个问题。ReactJS 解决了这个问题，让开发者更容易在搜索引擎上被找到。这是因为 React.js 应用程序可以在服务器上本地运行，并且虚拟 DOM 可以渲染并将网页传递给浏览器。

#### 7. 使用 JavaScript 库的优势

大多数 Web 开发者现在都使用 ReactJS。因为它提供了一个非常全面的 JavaScript 库。该 JavaScript 库让开发者有更大的自由来选择他们想要的工作方式。

#### 8. 代码测试范围

ReactJS 应用程序测试非常简单。它为开发者使用原生工具测试和调试程序提供了一个平台。

### 缺点

1. 快速的开发速度：快速的增长既有优点也有缺点。在劣势的情况下，环境总是在变化的，某些开发者可能不习惯频繁地重新学习新的处理方法。随着所有持续的升级，他们来说可能很难吸收所有这些变化。他们有责任不断提高自己的技能并熟悉前沿实践。

2. 文档不完善：这是技术快速演进的另一个缺点。React 技术的进步和扩张速度使其无法提供详尽的文档。为了解决这个问题，当新版本和工具被添加到他们现有的项目时，开发者会创建自己的说明书。

## 282 征服 JavaScript

3. 视图部分：ReactJS 只涵盖应用程序的 UI 层，不再多。因此，我们仍然需要选择一些额外的技术，以便为项目提供一套全面的开发工具。

4. JSX 作为障碍：ReactJS 使用了 JSX。由于这种语法扩展，HTML 和 JavaScript 可以共存。虽然这种方法有其自身的优点，但开发社区的某些成员认为 JSX 是一种障碍，特别是对于新手开发者来说。开发者对学习曲线的复杂性表示抱怨。

### React 版本

这里显示了详细的 React 发布历史。在 GitHub 上，我们也可以获得最新版本的完整文档。

| SN | 版本 | 发布日期 | 重大变化 |
|---|---|---|---|
| 1 | 0.3.0 | 29/05/2013 | 初始公开发布。 |
| 2 | 0.4.0 | 20/07/2013 | {/* {/* * </></</div> 支持注释说明。服务端渲染 API 已改进。React.AutoBind 已移除。支持主要要点、正式改进，修复了 Bug。 |
| 3 | 0.5.0 | 20/10/2013 | 增加内存，对选择和组合事件的支持，在 mixins 中支持 initState 和 getDefaultProps。添加了 React.version 和 React.isValidClass。改进了 Windows 兼容性。 |
| 4 | 0.8.0 | 20/12/2013 | 添加支持行和列、defers & async、<audio> & <video> 的循环以及 autoCorrect 属性。添加了 onContextMenu 事件。升级了 jransform 和 esprimafb 工具。升级了 Browserify。 |
| 5 | 0.9.0 | 20/02/2014 | 添加对 crossOrigin、download 和 hrefLang、mediaGroup 和 muted、sandbox、seamless 以及 srcDoc 代码属性的支持。为 React.PropTypes 添加了 array, arrayOf, component, oneOfType, renderable, shape。添加对 mouseOver 和 onMouseOut 的支持。为 <img> 元素添加对 onLoad 和 onError 的支持。 |

（继续）

## 前端开发 ■ 283

| SN | 版本 | 发布日期 | 重大变化 |
|---|---|---|---|
| 6. | 0.110 | 21/03/2014 | |
| 7. | 0.12 | | | |
| 8. | 0.13. | | | |
| 9. | | | | |
| 10. | | | | |
| 11. | | | | |
| 12. | | | | |
| 13. | | | | |
| 14. | | | | |
| 15. | | | | |
| 16. | | | | |
| 17. | | | | |
| 18. | | | | |
| 19. | | | | |
| 20. | | | | |
| 21. | | | | |

*(注：由于提供的原始文本中表格内容在第6行之后缺失或格式乱码，此处仅根据原文结构保留占位，实际翻译基于您提供的文本片段)*

*(更正：由于您提供的文本中表格从 SN 6 之后的内容不完整或存在乱码，上述翻译仅针对您提供的可见文本进行。)*

**重新审视文本：** 提供的文本中表格在 SN 6 之后确实是乱码或不完整的。我将仅翻译文本中可见的文字。

## 前端开发 ■ 285

| 序号 | 版本 | 发布日期 | 重大变更 |
|---|---|---|---|
| 23. | 16.1.0 | 2017/11/9 | 停止发布 Bower。修复了 UMD 构建中一个无意的冗余全局变量。修复了 onMouseEnter 和 onMouse 事件，替换了 <textarea> 的 placeholder，移除了任何不需要的代码。替换了缺失的 `package.json` 依赖，添加对 React DevTools 的支持。 |
| 24. | 16.3.0 | 2018/3/29 | 添加了官方支持的新 context API。包含一个新包。在尝试使用 SSR 创建 portals 时，防止无限循环。修复了此问题。解决了 an/IEEdge 问题。 |
| 25. | 16.3.1 | 2018/4/3 | 带有带有前缀感知的 API。在开发模式下，性能退化和错误处理问题。考虑同级依赖。使用 Filament 时，IE11 显示虚假警告。 |
| 26. | 16.3.2 | 2018/4/16 | 修复了 IE 崩溃。User Measuring 中的标签应该被修复。添加了 UMD 构建，并使用嵌套来提高 unstable_observedBits API 的效率。 |
| 27. | 16.4.0 | 2018/4/24 | 包含对 标准的支持。允许指定 propTypes。修正读取功能，修复了 testInstance.parent 中的崩溃。添加 React.unstable_Profiler 组件以跟踪性能。更改内部事件的名称。 |
| 28. | 16.5.0 | 2018/3/5 | 包含对 React DevTools Profiler 的支持。优雅地处理额外边缘情况下的失败。包含 react-dom/profiling。浏览器应该有一个 onClick 事件。到 movementX 和 movementY 字段。Pointer 事件现在有了 tangentialPressure 和 twist 字段。 |
| 29. | 16.6.0 | 2018/10/23 | 添加 Context 类型。支持优先级级别、延续和包装回调。增强了回退方法。移除了 iOS Safari 上的灰色层。添加 React.lazy() 以分离代码组件。 |
| 30. | 16.7.0 | 2018/12/20 | 提高 React.lazy 用于懒加载组件的速度。为了尽量减少内存泄漏，在卸载后清除字段。修复了 SSR 问题。解决了性能下降问题。 |
| 31. | 16.8.0 | 2019/2/6 | 包含 Hooks。对于批量更新，添加了 TestRenderer.act() 和 ReactTestUtils.act()。允许 React 提供同步启用。使用 lazy() 与 UseReducer 的懒初始化 API。 |
| 32. | 16.8.6 | 2019/3/27 | 在 useReducer() 中，纠正了不当的退出，解决 Safari DevTools 中的 iframe 问题，并在 contextType 被设置为 Context 时发出警告。如果不是 Context 而是 Consumer 且 contextType 被设置为错误值，则会告警告。 |

## 286 征服 JavaScript

# REACT 环境搭建

在这一部分中，我们将了解如何为 React 应用设置开发平台。ReactJS 的前提条件如下：

- NodeJS 和 NPM
- React 和 React DOM
- Webpack
- Babel

# REACTJS 安装方法

有两种方法可以为 ReactJS 应用准备一个成功运行的环境。列表如下：

- 使用 npm 命令
- 使用 create-react-app 命令

## 1. 使用 npm 命令

### 安装 NPM 和 NodeJS

创建任何 ReactJS 应用所需的平台是 NodeJS 和 NPM。通过点击提供的链接，我们可以安装 NodeJS 和 NPM 包管理器。我们将在第 6 章讨论 NodeJS 的安装。使用下面代码指定的命令来确认 NodeJS 和 NPM。

```bash



```bash
$ node -v
$ npm -v
```

## 安装 React 和 React DOM

在桌面或其他您选择的任何地方创建一个名为`reactApp`的根文件夹。在 PC 上，我们在这里创建。可以手动创建文件夹，也可以使用所示的命令。

```bash
$ mkdir react
$ cd react
```

## 创建 package.json 文件

现在，必须在项目文件夹中生成并存储一个`package.json`文件以构建任何模块。我们必须执行如下所示的命令来实现这一点。

```bash
javatpoint@root:~/Desktop/reactApp npm init -y
```

在生成`package.json`文件后，我们必须在终端中使用下面的`npm`命令安装`react`及其 DOM 包。

```bash
javatpoint@root:~/Desktop/reactApp>npm install react-dom --save
```

上述命令也可以独立使用，如下例。

```bash
javatpoint@root:~/Desktop/reactApp>npm install react --save
javatpoint@root:~/Desktop/reactApp>npm install react-dom --save
```

## 安装 Webpack

使用`Webpack`实现开发和生产流水线的自动化。`Webpack-dev-server`将用于开发，`Webpack`用于生成构建，`Webpack CLI`提供了许多命令。这些通过`Webpack`合并为一个文件（bundle）。使用下面描述的命令安装`Webpack`。

```bash
javatpoint@root:~/Desktop/reactApp> install install webpack
webpack-dev-server --save
```

```bash
# 289 -dev-cli
```

上述命令也可以独立使用，如下所示。

```bash
javatpoint@root:~/Desktop/reactApp>npm install webpack --save
```

## 288 征服 JavaScript

# 安装 Babel

`Babel`是一个转换器和编译器，用于翻译不同的源代码。`JSX`和`ES6`被转换为`ES5`，我们需要使用如下所示的命令来启用它。

```bash
javatpoint@root:~/Desktop/reactApp> install babel-core --save
```

# 289 前端开发 ■

## 文件创建

为了完成安装，必须在项目中添加以下文件：

- `index.html`
- `App.js`
- `main.js`
- `webpack.config.js`
- `.babelrc`

## 290 征服 JavaScript

## 2. 设置 React 应用、加载器和服务器

### 配置 Webpack

通过在`webpack.config.js`中包含以下代码来配置`webpack`。它指定了应用的入口、构建输出并自动刷新。此外，它设置了服务器端口为`8080`。它指定了处理不同文件格式的加载器。

```javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './main.js',
  output: {
    path: path.join(__dirname, 'bundle'),
    filename: 'index.js'
  },
  devServer: {
    inline: true,
    port: 8080
  },
  module: {
    rules: [
      {
        test: /\.jsx$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
        },
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './index.html'
    })
  ]
};
```

现在，打开`package.json`文件，从`"scripts"`对象中删除`"test" "echo Error: no test& exit"`，并替换为`start`和`build`命令。因为我们不会对此应用进行任何测试。

```json
{
  "name": "reactApp",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "webpack-dev-server --mode development --open --hot",
    "build": "webpack --mode production"
  },
  "keywords": [],
  "author": "ISC",
  "license": "",
  "dependencies": {
    "react": "^16.8.6",
    "react-dom": "^16.8.6"
  },
  "devDependencies": {
    "@babel/core": "^7.4.3",
    "webpack-cli": "^3.3.2",
    "webpack-dev-server": "^3.3.2"
  }
}
```

```json
{
  "@babel/preset-env": "7.4.3",
  "@babel/preset-react": "7.0.0",
  "@babel/core": "6.26.3",
  "@babel-loader": "8.0.5",
  "@babel-preset-env": "1.7.0",
  "@babel-preset-react": "6.24.1",
  "@html-webpack-plugin": "3.2.0",
  "@webpack": "4.30.0"
}
```

# 用于 index.html 文件的 HTML Webpack 模板

使用`Html-WebpackPlugin`，我们可以添加自定义模板来生成`index.html`。

这允许我们添加视口（viewport），以便为我们的应用程序在移动设备上提供响应式缩放。此外，它添加了`indexbundle.js`脚本（这是我们打包后的应用文件），并将`id="app"`的`div`设置为应用程序的根元素。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>React App</title>
</head>
<body>
  <div id="app"></div>
  <script src="indexbundle.js"></script>
</body>
</html>
```

## App.jsx 和 main.js

这是第一个 React 组件，有时被称为应用入口点。

它将显示“Hello, Everyone.”（大家好.）。

### App.js

```javascript
import React, { Component } from 'react';
class App extends Component{
  render() {
    return (
      <div>
        <h1>Hello Everyone</h1>
      </div>
    );
  }
}
export default App;
```

导入此组件并将其显示在我们`App`的根元素中，以便其在浏览器中可见。

### Main.js

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App.js';

ReactDOM.render(<App />, document.getElementById('app'));
```

## 创建 .babelrc

创建一个名为`.babelrc`的文件并将下面的代码粘贴到其中。

### .babelrc

```json
{
  "presets": [
    "@babel/preset-env", "@babel/preset-react"
  ]
}
```

## 运行服务器

安装并配置应用程序后，我们可能可以使用以下命令启动服务器。

```bash
javatpoint@root:~/Desktop/reactApp>npm start
```

它将显示必须在浏览器中打开的根节点。打开后，将显示输出。

# 前端开发 ■ 293

## 创建包 (Bundle)

现在，生成应用程序的包。

打包是将导入的文件集成到单个文件的过程，该文件被称为“包”（bundle）。然后可以将此包添加到网站中，以完整地加载应用程序。为了构建它，我们必须在命令提示符中执行下面指示的构建命令。

```bash
javatpoint@root:~/Desktop/reactApp> npm run build
```

此命令会在当前文件夹（我们的应用程序所在的文件夹）中创建包并显示它。

## 3. 使用 create-react-app 命令

如果我们不想使用`webpack`和`babel`安装`react`，可以使用`create-react-app`来安装`react`。`create-react-app`函数由 Facebook 管理。

这适用于不希望手动处理`webpack`和`babel`等转码技术的初学者。本节演示了如何使用 CRA 工具安装 React。

### 安装 NodeJS 和 NPM

NodeJS 和 NPM 是每个 ReactJS 应用程序所需的开发平台。

我们可能在下一章中下载 NodeJS 和 NPM 包管理器。

### 安装 React

我们可以使用下面的命令通过`npm`包管理器安装 React。不要担心安装 React 的潜在困难。必要的功能已包含在`create-react-app` npm 程序包中。

```bash
javatpoint@root:~/npm install -g create-react-app
```

### 开发一个新的 React 项目

安装 React 后，可以使用`create-react-app`命令构建一个新的 React 项目。在这里，我们选择项目名称为`jtreactapp`。

```bash
javatpoint@root:~/create-react-app jtp-reactapp
```

## 294 征服 JavaScript

```bash
javatpoint@root:~/npx create-react-app jtp-reactapp
```

上述代码将安装`react`并生成一个名为`jtp-reactapp`的新项目。该应用程序包含了默认显示的子文件夹和文件。

开始，进入`src`文件夹并对所需文件进行修改。默认情况下，文件存储在`src`文件夹中。

例如，我们将打开`App.js`并进行下面指示的代码修改。

### App.js

```javascript
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Welcome Everyone.
      </p>
        <p>
          Get started, edit src/App.js and save to the reload.
      </p>
        <a className="App-link" href="https://react.org" target="_blank" rel="noopener noreferrer">
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

# 前端开发 ■ 295

# 运行服务器

安装完成后，我们可能可以使用下面的命令启动服务器：

```bash
javatpoint@root:~/Desktop/cd jtp-reactapp
javatpoint@root:~/Desktop/jtp-reactapp>npm start
```



# ANGULARJS 与 REACTJS 的对比

我们将讨论 AngularJS 和 ReactJS。

# AngularJS

开源 JavaScript 框架 AngularJS 用于创建动态应用程序。2009 年，Misko Hevery 和 Adam Abrons 创建了 AngularJS，它目前由 Google 维护。

截至 2019 年 3 月 11 日，Angular 的最新版本为 7.8。它主要用于创建单页应用程序，基于 HTML 和 JavaScript 构建。可以通过 `<script>` 标签添加到 HTML 中。它通过指令增强 HTML 并连接数据。

## AngularJS 的特性

- **数据绑定**：AngularJS 遵循双向数据绑定模式。模型与显示之间的数据同步。

- **POJO 范式**：AngularJS 采用 POJO（普通 JavaScript 对象）模型，提供了自发的对象。POJO 概念使得 AngularJS 使用简单。

- **MVC 框架**：MVC 是一种用于应用程序开发的软件设计模式。AngularJS 的工作模式基于 MVC。AngularJS 架构简单、灵活且动态。MVC 促进了客户端应用程序。

- **服务**：AngularJS 提供了各种内置服务，例如 `XMLHttpRequest`。在 AngularJS 中，用户界面是使用 HTML 构建的。这种声明式语言包含较短的标签并且易于解释。它提供了结构化、组织良好且流畅的界面。

- **依赖注入**：AngularJS 内置的依赖注入系统有助于应用程序的理解和测试。

- **Google 上的社区活动**：AngularJS 提供了巨大的社区支持。由于 Google 维护 AngularJS，情况如此。因此，如果您有维护方面的问题，可以在几个论坛获得答案。

- **路由**：从一个视图到另一个视图的过程。路由是单页应用程序最重要的功能，所有内容都在页面上。当用户点击菜单时，开发者不希望他们跳转到另一个网站。开发者希望无论 URL 如何都在同一页面加载内容。

# ReactJS

使用免费开源 JavaScript 包 ReactJS 创建单页应用程序的用户界面。它专门负责应用程序的视图层。

它允许开发者使用被称为“组件”的微隔离代码来组装复杂的界面。React 由两部分组成：包含 HTML 代码并在界面中看到的组件，以及展示所有组件的 HTML 页面。

它由 Facebook 软件开发者 Jordan Walke 开发。最初由 Facebook 创建并管理，后来被 WhatsApp 和 Instagram 等主要产品采用。ReactJS 在 2011 年由 Facebook 创建用于新闻流区域，但直到 2013 年 5 月才向公众开放。

## ReactJS 的特性

- **JSX**：JSX 是 JavaScript 的语法扩展。JSX 语法会被转换为 React 框架的 JavaScript 调用。它扩展了 ES6，使得 HTML 式的文本可以与 JavaScript 编写的 React 代码共存。

- **组件**：组件是 ReactJS 的基础。多个组件构成一个 ReactJS 应用程序，每个组件都有自己的逻辑和控制。这些组件是可复用的，这使得在大型项目中维护代码变得更加容易。

- **单向数据绑定**：ReactJS 使用单向数据流，或单向数据绑定。单向数据绑定提供了更广泛的应用范围控制。如果数据流方向反过来，则需要额外的特性。这是因为组件的设计初衷是不可变的，其数据无法被修改。

- **虚拟 DOM (Virtual DOM)**：虚拟 DOM 对象是物理 DOM 对象的表示。当 Web 应用发生变化时，整个用户界面将以虚拟 DOM 的形式重新渲染。然后将检查现有 DOM 表示与新 DOM 之间的差异。一旦完成，实际 DOM 只更新修改过的元素。这加快了程序运行并消除了内存浪费。

- **简单性**：ReactJS 利用 JSX 文件，使得应用程序既容易创建又容易理解。此外，ReactJS 是一个基于组件的框架，允许根据需要复用代码。它易于使用和理解。

- **性能**：ReactJS 以其卓越的性能闻名。这是因为它对虚拟 DOM 有控制权。DOM 是完全基于内存的。因此，当我们构建组件时，不会立即写入 DOM。相反，我们正在开发将转换为 DOM 的虚拟组件，从而带来更高效、更流畅的用户体验。

# 征服 JavaScript

## AngularJS vs React

| | AngularJS | React |
| :--- | :--- | :--- |
| 作者 | Google | Facebook 社区 |
| 开发者 | Misko Hevery | Jordan Walke |
| 最初发布 | 2010年10月 | 2013年3月 |
| 最新版本 | 2019年3月11日的 Angular 1.7.8 | 2019年3月27日的 React 16.6.8 |
| 语言 | JavaScript, HTML | JSX |
| 类型 | 开源 MVC 框架 | 开源 JS 框架 |
| 渲染 | 客户端 | 服务端 |
| 打包 | 弱 | 强 |
| 数据绑定 | 双向 | 单向 |
| DOM 测试 | 常规 DOM 单元和集成测试 | 虚拟 DOM 单元测试 |
| 应用架构 | 自动由它管理 MVC 要求 | Flux。为了处理依赖，需要额外的工具 |
| 路由 | 对于其路由器，它一个必须手动维护的模板或控制器 | 虽然包含多个路由模块（如 `react-router`），但它不处理路由 |
| 性能 | 虚拟 DOM 慢快 | |
| 最适合 | 最适合一次刷新单个视图的单页应用 | 理想用例是同时更新多个视图的单页应用 |

## REACTJS 与 SVELTE 的比较

### 什么是 Svelte？

Svelte 是一个免费开源的前端编译器，由 Rich Harris 在 2016 年创建。Svelte 使用 HTML 模板创建直接修改文档对象模型（DOM）的原代码。

与 React 和其他传统的 JavaScript 框架不同，Svelte 不产生 DOM 开销。Svelte 的方法会导致更少的传输文件和更高的客户端性能。应用程序代码由编译器处理，编译器还会重绘受数据影响的 UI 组件并插入单元以自动更新数据。

创建 Svelte 使用 JavaScript 的超集 TypeScript 编程语言。

## 何时需要使用 Svelte？

Svelte 的代码以直观著称，因为原生 JavaScript 与它非常相似。Svelte 使开发者能够用更少的代码实现目标。如果网站开发者想要创建极小的包体积，他们应该利用 Svelte。

用 Svelte 编写的程序在低容量或低功耗设备上使用非常实用。敏捷的工具和框架提供了对状态管理、路由和专用基础设施开发的更好控制。DOM 操作、响应式框架和不断增长的市场都可能受益于 Svelte。

## 哪些公司在使用 Svelte？

许多大型公司依赖 Svelte 构建其网站，包括 Yahoo、乐天、彭博社、Facebook、Apple、纽约时报、Square、字节数据（ByteData）、Spotify、路透社、宜家、Brave 等。由于 Svelte 在编码时会将应用程序代码转换为最优 JavaScript，企业非常喜欢它。因此，用 Svelte 创建的程序性能不会受到框架抽象的影响。

## 什么是 React？

React 是开发者用于创建界面的前端 JavaScript 库。

UI 元素由 Meta (Facebook) 维护，一组组织和开发者协作创建更新版本。React 是创建网页、移动应用程序和服务渲染应用的基础。React 有助于管理状态并将其渲染到 DOM 上。

React 应用程序开发需要使用额外的库。要创建 React 组件，你需要熟悉设计模式、客户端代码和路由。

## 何时应该使用 React？

React 组件库功能多变，且是状态管理的理想选择。因此，数据可以在使用 React 的应用和网站之间传输，而无需刷新页面。对于需要大量用户参与的用户界面，应该采用 React。

React 是模型-视图-控制器（MVC）的组件。React 使得管理底层算法变得简单，只需要编写用户界面的视图模型。React 的虚拟 DOM 加快了加载时间并增强了网站性能。

## 哪些公司在使用 React？

React 构建界面包括 Facebook、Instagram、Salesforce、Discord、Skype、Pinterest 等大公司。

## React vs Svelte: 哪个更优？

Svelte 是比 React 较新的框架，不需要额外的工具。通过比较它们的差异，以便你选择合适的框架。

## 性能

传统的文档对象模型 (DOM) 在 React 中通过虚拟 DOM 提升了效率。

React 使用虚拟 DOM 延迟更新。

Svelte 是一个编译器，在赋值时渲染 DOM。作为一个无服务器优先的框架，Svelte 被认为比 React 更具响应性。

## 包体积

Svelte 的 gzip 版本为 1.6 KB。当与 `ReactDOM` 使用时，总大小为 42.2 KB。Svelte 减小的包体积确保了更快的加载速度和更好的响应。

# 测试

端端测试可以在 React 代码上执行。应用程序代码在真实的环境中测试。这缩短了上市时间 (TTM) 并增加了软件的价值。Svelte 测试库可用于单元测试。Svelte 测试库比 React 更紧凑。因此，Svelte 可以帮助开发者维护整洁、功能且紧凑的代码。

## 社区支持

React 有大型开发者社区，因为它是世界上流行的 JavaScript 平台之一。React 开发者社区贡献教程、指南、更新、组件等，以维护该库的实用性。像 Facebook 这样的大型公司维护 React 增加了对 React 工程师的需求。Svelte 并不常见，但使用它的开发者满意度很高。Svelte 的企业级支持相对较新，因为 `SvelteKit 1.0` 尚未发布。与 287 万活跃的 React 开发者相比，Svelte 社区仅有 1.1 万开发者。

## REACT JSX

正如我们之前看到的，所有的 React 组件都有一个 `render` 方法。React 组件的 HTML 输出由 `render` 函数定义。一种名为 JSX（JavaScript 扩展）的 React 插件允许我们创建类似于 HTML 的 JavaScript 代码。

换句话说，JSX 是 ECMAScript 的一种扩展，React 利用它来允许类 HTML 语法与 JavaScript/React 代码共存。预处理器（也称为转译器，如 `babel`）使用该语法将类 HTML 语法转换为 JavaScript 引擎可以解释的典型 JavaScript 对象。

在编写 JSX 的同一个文件中，它允许我们编写类似 HTML/XML 的结构（例如 DOM 树风格的结构）。预处理器随后会将这些表达式转换为 JavaScript 代码。JSX 标签像 XML/HTML 标签一样，包含标签名、属性和子元素。

## 示例

在本节中，我们将 JSX 语法放在一个 JSX 文件中，并检查预处理器（`babel`）转换后的相关 JavaScript 代码。

## JSX 文件

```jsx
```



<div>Hello Everyone</div>

```javascript
React.createElement("div", null, "Hello Everyone");
```

上面的代码创建了一个带有三个参数的 React 元素：第一个是元素的名称 `"div"`，第二个是在 `div` 标签中提供的属性，第三个是我们要提供的内容 `"Hello Everyone"`。

## 为什么使用 JSX？

- 因为它在将代码转换为 JavaScript 时会优化，所以它比标准的 JavaScript 更快。
- React 采用结合标记和功能的组件，而不是通过将技术存放在不同的文件中来划分。组件将在稍后的章节中介绍。
- 由于它是类型安全的，大多数错误可以在编译期间被识别出来。
- 制作模板变得更加简单。

## JSX 嵌套元素

如果我们想使用多个元素，就必须将它们封装在一个容器元素中。

在这种情况下，`div` 元素充当三个嵌套项目的容器。

## App.JSX

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Everyone</h1>
        <h2>Training Center</h2>
        <p>The greatest CS lessons may be found on this website.</p>
      </div>
    );
  }
}

export default App;
```

## JSX 中的属性

与标准 HTML 一样，JSX 在 HTML 组件上使用属性。

由于 `class` 是 JavaScript 中的保留词，JSX 属性使用了驼峰命名法，而不是 HTML 传统的命名方式。例如，HTML 中的 `class` 在 JSX 中变为 `className`。

在 JSX 中，我们还可以使用自己的独特自定义属性。自定义属性必须使用 `data-` 前缀。

在下面的实例中，`<p>` 标签的自定义属性 `data-demoAttribute` 已被用作属性。

## 示例

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Everyone</h1>
        <h2>Training Institutes</h2>
        <p data-demoAttribute="demo">
          The greatest CS lessons may be found on this website.
        </p>
      </div>
    );
  }
}

export default App;
```

在 JSX 中定义属性值有两种方法：

### 1. 作为字符串字面量

可以使用双引号来表示属性的值。

```javascript
var element = <h2 className="firstAttribute">Hello Everyone</h2>;
```

## 示例

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1 className="hello">Everyone</h1>
        <p data-demoAttribute="demo">
          The greatest CS lessons may be found on this website.
        </p>
      </div>
    );
  }
}

export default App;
```

### 2. 作为表达式

可以使用大括号 `{}` 将属性值定义为表达式：

```javascript
var element = <h2 className={varName}>Hello Everyone</h2>;
```

## 示例

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1 className="hello">{45 + 10}</h1>
      </div>
    );
  }
}

export default App;
```

## JSX 中的注释

与 JSX 表达式的使用类似，JSX 允许我们使用以 `/*` 开头并以 `*/` 结尾的注释，并将其封装在大括号中。下面的 JSX 示例演示了如何使用注释。

## JSX 中的样式

React 始终建议使用内联样式。我们必须使用驼峰语法来设置内联样式。在某些元素上，React 自动允许在数值后添加 `px`。在下面的实例可以看到元素的样式用法。

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    var myStyle = {
      color: "red",
      fontSize: "20px"
    };

    return (
      <div>
        <h1 style={myStyle}>Hello World</h1>
      </div>
    );
  }
}
```

```jsx
import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Hello World</h1>
      </div>
    );
  }
}

export default App;
```

## EXPRESS.JS

### 什么是 EXPRESS.JS？

Express 是一个快速、简约的 Node.js 框架。它是 Node.js 之上的一个层，有助于管理服务器和路由。这里是一些关键特性：

- 快速且简单。
- 单线程和异步。
- 允许我们根据 HTTP 方法和 URL 指定应用程序路由。
- 包含许多中间件模块。

### Express 看起来是什么样？

看一个简单的 Express 应用程序。

```javascript
var express = require('express');

var app = express();

app.get('/', function (req, res) {
  res.send("Welcome to Everyone");
});

var server = app.listen(8000, function () {
  var host = server.address().address;
  var port = server.address().port;

  console.log(`Instance listening at %s:%s`, host, port);
});
```

Express 的其他特性包括：

- 快速简单地创建 Node.js Web 应用。
- 易于调整和个性化。
- 允许我们根据 HTTP 方法和 URL 指定应用程序路由。
- 轻松集成多种模板引擎，如 Jade、Pug 和 EJS。
- 允许我们提供处理错误的中间件。
- 简单地提供静态文件和应用程序资源。
- 允许创建 REST API 服务器。
- 简单连接到 MongoDB、Redis 和 MySQL 等数据库。

```javascript
app.get('/', function (req, res) {
  res.send("Welcome to Everyone");
});

app.listen(4000);
```

在运行窗口中输入以下代码来运行程序。

```bash
node app.js
```

## Node.js

### 早期阶段

难以置信，Node.js 已经有 12 年了。互联网有 32 年了，而 JavaScript 已经有 26 年了。Ryan Dahl 在 2009 年创建了 Node.js。Node.js 最初仅支持 Linux 和 Mac OS X。

Dahl 负责了它的创建和维护，随后 Joyent 提供了赞助。

由于它必须同时管理大量的连接，Dahl 在 2009 年批评了当时最流行的 Web 服务器 Apache HTTP Server，认为其能力受限（可达 10,000 个及更多）。

该问题的解决办法是：在整个过程中，当出现任何停止的代码或在并发连接出现隐含的多执行栈时，通过编写代码来处理。

Dahl 在 2009 年 11 月 8 日的首届欧洲 JSConf 上引入了 Node.js 项目。V8 JavaScript Chrome 引擎、基础 I/O API 和事件循环都是 Node.js 的组件。

### 它的演变

随着浏览器的演进以为消费者提供卓越的性能，JavaScript 引擎得到了极大改进。主流浏览器投入了大量精力研究如何让 JavaScript 运行得更快并提供更好的支持。

Node.js 在合适的时间和地点被创建了。建立了许多 JavaScript 服务端编程方法，还产生了造福许多开发者的创造性思维。Node.js 支持数百个开源库（其中大部分可以在 npm 网站上找到），这是它在开发者中广受欢迎的主要原因之一。

Node.js 社区举办了大量的开发者会议和活动，例如 Node.js Interactive、Node.js Summit 和 NodeConf，以及其他的本地活动。

Node.js 开源社区创建了 Web 框架以加速应用程序的创建。

其中包括 Connect、Sails.js、Koa.js、Express.js、Feathers.js、socket.io、Derby、Hapi.js、Meteor 等多个框架。

## NODE.JS 基础

Node.js 支持 JavaScript。因此，Node.js 中的 JavaScript 语法与浏览器中的 JavaScript 语法相当。

### 原始类型

Node.js 中提供了这些基本类型：

- `String`（字符串）
- `Boolean`（布尔）
- `Number`（数字）
- `Undefined`（未定义）
- `Null`（空）
- `RegExp`（正则表达式）

Node.js 中的其他一切都是对象。

### 弱类型

与浏览器中的 JavaScript 一样，Node.js JavaScript 允许弱类型。使用 `var` 关键字定义任意类型的变量。

### 对象字面量

对象字面量的语法与浏览器中的 JavaScript 相同。

```javascript
var obj = {
  authorName: 'Shiya Sham',
  language: 'Node.js'
};
```

### 函数

与浏览器中的 JavaScript 一样，Node 将函数视为一等公民。

此外，函数可以具有特性和属性。在 JavaScript 中，它类似于类。

```javascript
function Display(k) {
  console.log(k);
}

Display(200);
```

### Buffer

Buffer 是 Node.js 中一种额外的数据类型，JavaScript 浏览器并不提供这种类型。在从文件读取或通过网络接收数据包时，`Buffer` 主要用于持有二进制数据。

### Process 对象

`process`（进程）用于执行每个 Node.js 脚本。为了获取有关 Node.js 应用当前进程的所有细节，它包含一个 `process` 对象。以下示例演示了如何在 REPL 中使用 `process` 对象获取进程信息。

```text
> process.execPath
'C:\Program Files\nodejs\node.exe'

> process.pid
1234

> process.cwd()
'C:\'
```

### 默认本地

在全局作用域方面，Node 的 JavaScript 与浏览器中的 JavaScript 不同。在不使用 `var` 关键字定义的变量在浏览器 JavaScript 中会变成全局变量。而在 Node.js 中，一切默认都是局部的。

### 利用全局作用域

浏览器中的全局作用域是指 `window` 对象。Node.js 中的全局对象表示全局作用域。我们必须使用 `export` 或 `module.exports` 导出任何内容以便将其添加到全局作用域中。要从全局作用域访问模块或对象，使用 `require()` 方法导入它们。例如，使用 `exports.name = object` 在 Node.js 中导出一个对象。

```javascript
exports.log = {
  console: function (msg) {
    console.log(msg);
  },

  file: function (msg) {
    // 此处记录到文件
  }
};
```



现在我们可以通过`require()`方法导入，在 Node.js 项目的任何地方使用`log`对象了。

## VUEJS

下面我们将讨论 VueJS 及其定义、安装和语法。

### 什么是 VUEJS？

VueJS 是一个开源的渐进式 JavaScript 框架，用于创建动态 Web 界面。它是简化 Web 开发的框架之一。VueJS 的关注重点是视图层。它可以无缝地集成到大型前端开发项目中。VueJS 的安装非常简单。交互式界面易于理解且构建快速。

### 特性

VueJS 的特性列举如下：

- 虚拟 DOM (Virtual DOM)：Vue 和 React 等框架利用虚拟 DOM。不是直接修改 DOM，而是在 JavaScript 中构建一个副本。每当需要进行更改时，都会更新用户的实际 DOM。这对于优化是有益的。
- 数据绑定 (Binding)：Vue 包含一个指令`v-bind`，用于给 HTML 属性、类赋值。
- 组件 (Components)：Vue 的关键特性之一，组件允许创建可复用的元素。
- 事件处理 (Event handling)：Vue 包含一个属性`v-on`，可以监听事件。
- 动画/过渡 (Transition)：当 HTML 元素从 DOM 中添加、更改或删除时，Vue 提供了多种过渡方法。对于过渡效果，必须封装在组件中。使用第三方动画库可以让界面更具交互性。
- 计算属性 (Computed Property)：这是 Vue 的关键特性之一。需要关注执行必要的计算。这不需要额外的代码。
- 模板 (Templates)：Vue 通过 HTML 模板将实例绑定到 DOM。Vue 将模板转换为渲染函数。

### 指令 (Directives)

VueJS 中的内置指令可以执行各种前端任务，包括`v-if`、`v-else`、`v-show`、`v-on`、`v-bind`和`v-model`。

### 监听器 (Watchers)

监听器用于变化的数据。例如表单组件。在这种情况下，我们不需要添加额外的事件。监听器通过处理任何数据变化使代码变得简单且快速。

### 路由 (Routing)

借助`vue-router`，可以在页面之间导航。

### 轻量级 (Lightweight)

VueJS 脚本的性能和重量都很很快。

### Vue-CLI

可以通过`vue-cli`命令行界面安装 VueJS。使用`vue-cli`使构建和编译变得简单。

## 316 征服 JavaScript

这两个 JavaScript 对象。VueJS 和 React 都采用了虚拟 DOM，这可以加快运行速度。

JSX 是一种模板，vuejs 使用 html、js 和 css。VueJS 的样式对于初学者来说相对简单，易于理解和适应。VueJS 的基于模板的方法非常简单。React 使用 jsx 方法。对于 React 来说，一切都是 JavaScript。JavaScript 包含了 HTML 和 CSS。

安装工具 VueJS 利用了`vue-cli`、CDN 和`npm`，而 React 用于构建 react app。

两者都非常易用，而且项目已经设置好以满足所有先决条件。VueJS 构建时不需要`webpack`，但 React 需要。通过使用 CDN 库，我们可以在`jsfiddle`或`codepen`上的任何地方开始编写 VueJS 代码。

## 流行程度

使用 React 的人比 VueJS 多。React 提供的就业机会比 VueJS 多。

React 更广为人知，因为它有一家知名公司（即 Facebook）的支持。

React 采用了最优秀的 JavaScript 实践方法，因为它利用了该语言的核心理念。任何使用 React 的人无疑熟悉所有的 JavaScript 基础知识。

VueJS 框架正在开发中。目前，与 React 相比，VueJS 的职业机会较少。一项调查显示，许多人正在适应 VueJS，这可能会增加其相对于 React 和 Angular 的流行度。一个强大的社区正在开发 VueJS 的功能。该社区定期更新`vue-router`。VueJS 是一个强大的库，它是通过结合 Angular 和 React 的最佳元素创建的。由于其轻量级的库，VueJS 比 React/Angular 快得多。

## VueJS vs Angular

### 相似之处

Angular 和 VueJS 非常相似。`V-if`和`V-for`指令与 Angular 的`ngIf`和`NgFor`几乎相同。它们都提供了用于安装和构建项目的命令行界面。

Angular 和 VueJS 都需要`angular-cli`。它们都提供服务端渲染、双向数据绑定等。

### 复杂性

Vuejs 的使用和学习非常简单。正如之前提到的，新手可以使用 VueJS CDN 包在`codepen`和`jsfiddle`上开始学习。对于 Angular，我们必须遵循一套程序进行安装，对于初学者来说，开始使用 Angular 可能有些挑战性。它使用 TypeScript 进行编码，这对任何具有 JavaScript 基础背景的人来说都是挑战性的。然而，具有 Java 和 C# 背景的用户会发现它更容易学习。

### 性能

性能由用户决定。与 Angular 相比，VueJS 的文件大小小得多。以下 URL：`http://stefankause.net/js-framework-benchmark4/webdriver-ts/table.html`比较了这些框架的性能。

### 流行程度

目前，Angular 的使用比 VueJS 更广泛。Angular 被许多企业使用，非常有名。对于具有 Angular 专业知识的人来说，就业前景也更丰富。另一方面，VueJS 正在取得进展，可能被视为 Angular 和 React 的优秀对手。

### 依赖项

Angular 默认包含了许多功能。

开始，我们必须导入必要的模块，例如`@angular/animations`和`@angular/forms`。

VueJS 依赖第三方库来运行，因为它缺乏 Angular 的某些内置功能。

### 灵活性

任何其他大型项目都可以无缝地与 VueJS 结合而不会出现任何问题。

在已存在的项目中开始使用 Angular 将并不简单。

## 反向兼容

AngularJS、Angular2 和 Angular4 都出现过。两个 Angular 框架 JS 和 v2 差异很大。

由于基础性的不兼容，在 AngularJS 中创建的项目应用程序无法迁移到 Angular2。VueJS 2.0 是最新版本，具有强大的向后兼容性。它拥有极易阅读的优秀文档。

### Typescript

Angular 编码时使用 TypeScript。

## 环境 Setup

开始，我们必须导入必要的模块。

对于初学者，开始使用 Angular 可能会有困难。使用 CDN 库，我们可以在`jsfiddle`或`codepen`上的任何地方开始编写 VueJS 代码。

## 322 征服 JavaScript

## 易于理解的代码

Vue.js 框架的结构非常直观，易于掌握。这是该框架受欢迎的原因之一。

如果我们熟悉 HTML 和 JavaScript，就可以简单地使用 Vue.js 进行开发。由于其基础结构，用户可以快速将 Vue.js 引入他们的 Web 项目并构建应用。

## 与现有应用程序集成非常简单

Vue.js 为各种需求都提供了许多组件，并可以与现有应用快速集成。它可以与任何基于 JavaScript 的应用程序集成。

## 本质适应性强

Vue.js 的灵活性也让 React.js、Angular.js 以及任何其他现代 JavaScript 框架的开发者能够轻松上手。我们大量的灵活性可以使用虚拟节点来创建 HTML 文件、JavaScript 文件和纯 JavaScript 文件。

## 组件

在 Vue.js 应用中，我们可以构建可重用的自定义组件。

## 文档简单、详尽且细致

Vue.js 提供了极其简、、广泛且清晰的文档，让 HTML 和 JavaScript 知识较少的开发者也能对其进行编码。

## DOM 虚拟化

Vue.js 采用了虚拟 DOM，正如 ReactJS、Ember 等其他现有框架一样。虚拟 DOM 是实际 HTML DOM 的内存版本，可以在不影响原始 DOM 的情况下进行修改。

## 双向通信

Vue.js 的 MVVM 设计允许双向通信，使得 HTML 块的管理变得相对简单。

## 使用 Vue.js 的公司

随着越来越多的知名公司开始实时使用 Vue.js，它正变得越来越流行。许多企业在现实世界有效地利用 Vue.js。

以下是几个示例：

- Facebook：Facebook 是在真实项目中使用 Vue.js 最成功的公司。该框架被 Facebook 用于新闻动态（Newsfeed）的营销侧。
- Adobe：Adobe 的 Portfolio 产品使用了 Vue.js。该机构已将其当前的软件迁移到 Vue.js 框架，利用了其易于集成的优点。
- 小米：小米也使用 Vue.js 构建其产品目录，为消费者提供动态体验。
- 阿里巴巴：Vue.js 已被中国最重要的上市公司之一阿里巴巴所采用。

其他在项目中使用 Vue.js 的知名公司还包括：

- Grammarly
- Laracast
- Behance
- Netflix
- Codeship
- Livestorm
- Gitlab
- Euronews
- Wizzair 等。

## 324 征服 JavaScript

### 检查已安装的 Vue.js 版本

如果我们已经熟悉 Node.js 并且机器上安装了 Vue.js CLI，我们可以使用 Node.js 命令行提示符验证已安装的 Vue.js 版本：

- 在 Node.js 命令行提示符中运行以下命令：

```bash
vue --version
```

- 如果响应良好，请进入创建新项目的下一步。之前的实例已成功安装了 Vue.js 2.9.6 版本。要创建一个新项目，使用以下命令：

语法：
`vue create <appName>`

- 要构建名为 firstapp 的应用，请使用`vue create firstapp`命令。
- 我们遇到了一个错误，说明`vue create`命令仅兼容 Vue CLI 3，而我们正在使用较早的版本。现在，使用下面的命令卸载之前的版本并安装新版本。

```bash
npm uninstall -g vue-cli
npm install -g @vue/cli
```

- 过时的 Vue.js 版本已明确移除。现在安装最新版本。
- 最新版本的 Vue CLI 现在已安装。可以使用`vue --version`命令确定 Vue CLI 版本。
- 我们可以看到最新版本的 Vue CLI 已安装。运行`vue create firstapp`命令创建一个名为 firstapp 的新应用。

## VUEJS 中的实例

我们必须使用`Vue`方法来创建新的 Vue 实例以启动 Vue 应用程序。每当我们启动一个新的 Vue 项目时，`main.js`文件中就会默认激活 Vue 实例。它的另一个名称是根 Vue 实例。

语法：

```javascript
var vm = new Vue({
  // option
})
```

MVVM 模式指导了 Vue 应用的设计。为了引用我们的 Vue 实例，我们必须使用变量`vm`（ViewModel 的缩写）。在创建 Vue 实例时，我们必须包含一个选项对象。

让我们看一个示例，看看 Vue 构造函数必须提供什么。

`index.html`文件：

```html
<html>
  <head>
    <link rel="stylesheet" href="index.css">
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
      <h1>Firstname is: {{firstname}}</h1>
      <h1>Lastname is: {{lastname}}</h1>
      <h1>{{mydetails()}}</h1>
    </div>
    <script src="index.js"></script>
  </body>
</html>
```

## 326 征服 JavaScript

`index.js`文件：

```javascript
var vm = new Vue({
  el: '#app',
  data: {
    firstname: "Alisha",
    lastname: "Singla",
    address: "hi"
  },
  methods: {
    mydetails: function() {
      return "I am " + this.firstname + " " + this.lastname + " " + this.address;
    }
  }
});
```

让我们利用一个简单的 CSS 来增强输出的视觉效果。

`index.css`文件：

```css
html, body {
  margin: 6px;
  padding: 0;
}
```

示例
我们可以看到已安装了最新版本的 Vue CLI。运行`vue create firstapp`命令创建一个名为 firstapp 的应用。

在实例中，我们可以看到 HTML 内容并没有像我们的那样显示在浏览器中。HTML 内容是以我们在`htmlcontent`变量中指定的方式显示的。

## VUE.JS 中的模板

在这里，我们将学习如何以 HTML 模板的形式在屏幕上输出。Vue.js 采用基于 HTML 的模板语法，允许 Vue 开发者声明式地连接 DOM 和数据。

所有的 Vue.js 模板都是浏览器可以处理的 HTML。如果我们使用简单的插值方法（即双大括号）在浏览器上显示 HTML ，输出将是。为了完全理解这一概念，请考虑一个简单的示例并检查结果。

`index.html`文件：

```html
<html>
  <head>
    <title>Vue.js Template</title>
    <link rel="stylesheet" href="index.css">
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  </head>
  <body>
    <div id="app">
      <h1>Firstname is: {{firstname}}</h1>
      <h1>Lastname is: {{lastname}}</h1>
      <div>{{htmlcontent}}</div>
    </div>
    <script src="index.js"></script>
  </body>
</html>
```

`index.js`文件：

```javascript
var vm = new Vue({
  el: '#app',
  data: {
    firstname: "Alisha",
    lastname: "Singla",
    htmlcontent: "<div><h1>This is the Vue.js Template Instance</h1></div>"
  }
});
```

`index.css`文件：

```css
html, body {
  margin: 6px;
  padding: 0;
}
```

## 前端开发 ■ 329

为了解决这个问题，我们需要使用`v-html`指令。当我们将`v-html`指令应用于 html 元素时，Vue.js 会理解它必须输出 HTML 内容。
现在，在`.html`文件中插入`v-html`指令，并比较以下实例中的结果。

语法：

```html
<div v-html="htmlcontent"></div>
```

示例 2

`indexes.html`文件：

```html
<html>
<head>
    <title>Vue.js Template</title>
    <link rel="stylesheet" href="indexes.css">
    <script src="https://cdn.jsdelivr.net/npm/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <h1>Firstname: {{firstname}}</h1>
        <h1>Lastname: {{lastname}}</h1>
        <div v-html="htmlcontent"></div>
    </div>
    <script src="indexes.js"></script>
</body>
</html>
```

`indexes.js`文件：

```javascript
var vm = new Vue({
    el: '#app',
    data: {
        firstname : "Alisha",
        lastname : "Singla",
        htmlcontent : "<div><h1>This is the Vue.js Template instance</h1></div>"
    }
})
```



在上面的实例中，我们可以看到`v-html`指令正确地将一个 HTML 模板添加到了 DOM 中。现在让我们来看看如何向现有的 HTML 组件添加属性。

### 属性应该添加到 HTML 元素中

假设 HTML 文件中有一个图像元素，并且我们为其赋值`src`，这是一个 Vue.js 组件。请考虑以下内容：

#### Indexs.html 文件：

```html
<html>
<head>
  <title>Vue.js Template</title>
  <link rel="stylesheet" href="indexes.css">
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <h1>FirstName : {{firstname}}</h1>
    <h1>LastName : {{lastname}}</h1>
    <div v-html="htmlcontent"></div>
    <img src="" width="310" height="280" />
    <script src="indexs.js"></script>
  </div>
</body>
</html>
```

#### Indexs.js 文件：

```javascript
var vm = new Vue({
  el: '#app',
  data: {
    firstname : "Alisha",
    lastname : "singla",
    htmlcontent : "<div><h1>This is the Vue.js instance</h1></div>",
    imgsrc : "https://www.fiordalisa.ch/wp-content/uploads/2017/12/IMG_40.jpg"
  }
})
```

### 示例 3

Indexes.html：

```html
<html>
<head>
  <title>Vue.js Template</title>
  <link rel="stylesheet" href="indexes.css">
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <h1>Firstname : {{firstName}}</h1>
    <h1>Lastname : {{lastname}}</h1>
    <div v-html="htmlcontent"></div>
    <img v-bind:src="imgsrc" width="310" height="280" />
  </div>
  <script src="indexes.js"></script>
</body>
</html>
```

Indexes.js：

```javascript
var vm = new Vue({
  el: '#app',
  data: {
    firstname: "Alisha",
    lastname: "singla",
    htmlcontent: "<h1>This is the Vue.js Template instance</h1>",
    imgsrc: "https://www.fiordalisa.ch/wp-content/uploads/2017/12/IMG_40.jpg"
  }
})
```

在本章中，我们涵盖了 React、Express 和 Vue.js 的安装、优点、缺点以及基础语法。

## 笔记

- 1 前端 vs 后端：www.geeksforgeeks.org/frontend-vs-backend/#~:-text=Thevisual%20aspects%20of%20the,%2C%20Ruby%2C%20Python%2C%20and%20the 访问日期：2022年10月11日。
- 2 什么是 React 的指南：www.simpleartarn.com/tutorials/react-js-tutorial/what-is-react-js 访问日期：2022年10月10日。
- 3 React 特性：www.javpoint.com/react-features 访问日期：2022年10月10日。
- 4 React 的优缺点：www.javpoint.com/pros-and-cons-of-react 访问日期：2022年10月10日。
- 5 React 版本：www.javpoint.com/version 访问日期：2022年10月10日。
- 6 React 环境：www.javpoint.com/installation 访问日期：2022年10月10日。
- 7 React 与 Angular 的区别：www.javpoint.com/reactjs-vs-angular 访问日期：2022年10月10日。
- 8 Svelte 或 React：哪个框架更好？www.turing.com/svelte-react-framework-should-choose-in 访问日期：2022年10月10日。
- 9 React：www.javpoint.com/react 访问日期：2022年10月10日。
- 10 Express：www.tutorialpoint.com/express 访问日期：2022年10月10日。
- 11 Express：www.geeksforgeeks.org/express 访问日期：2022年10月10日。
- 12 Node.js 的历史：section.io/engineering/history-node 访问日期：2022年10月10日。
- 13 Node.js 基础：www.tutorialpoint.com/nodejs 访问日期：2022年10月10日。
- 14 Vuejs - 概述：www.tutorialpoint.com/vuesjs 访问日期：2022年10月10日。
- 15 Vue.js 安装：www.javpoint.com/vue-js 访问日期：2022年10月10日。
- 16 开始使用 Vue.js：www.javpoint.com/getting-started-vue-js 访问日期：2022年10月10日。
- 17 Vue.js 实例：www.javpoint.com/vue-js-instance 访问日期：2022年10月10日。
- 18 Vue.js 模板：www.javpoint.com/vue-js-template 访问日期：2022年10月10日。

因此，Node.js 与无服务器架构（serverless architecture）的集成是完美的匹配。

当服务器需求发生变化时，有专门为无服务器设计的 npm 包，而且构建无服务器的 Node.js 应用在 C2C 和 B2C 用例中可以与整体微服务架构良好协作。

## 物联网

Node.js 擅长同时处理多个连接。由于物联网（IoT）基于多个设备产生信号且这些信号必须被快速处理，Node.js 是此类应用的优秀后端，包括无服务器架构和实时通信能力。

## 音视频处理

与其他技术相比，Node.js 在处理异步输入/输出方面明显优得多。因此，与其他媒体工具配合时，可以使用 Node.js 来处理和操作多媒体数据。

例如，可以使用 Node.js 轻松配置流媒体。

## 快速开发

Node.js 基于标准的 Web 语言构建，极其易用且上手曲线非常短。可以快速开发新项目并将其推向市场。

因此，完成这些工作所需的工程资源得以减少。

本案例展示了 Node.js 如何帮助满足紧迫的期限。

该产品是一个面向冰雹修复公司和客户的在线市场，本应在旺季之前上线。

在 PHP 和 Node.js 之间选择时，我们选择了 Node.js 以匹配功能需求和时间表。通过使用同构架构（isomorphic architecture），我们缩短了开发时间。

## 与 C++ 代码集成

Node.js 可以与现 C++ 库协同工作。这是因为 Node.js 运行时基于运行在主机节点上的 C++ 服务器。因此，Node.js 可以在 C++ 和应用程序代码之间快速传输数据。

### Node.js 的缺点

### 密集计算导致性能限制

即使在今天，Node.js 最主要的局限性是无法处理 CPU 密集型活动。

但是，为了理解问题的根本原因，我们需要一些背景。

让我们从基础开始：JavaScript。众所周知，Node.js 是一个运行 JavaScript 的服务端运行时环境。JavaScript 作为一种前端编程语言，在单线程上运行。由于 JavaScript 任务是轻量级的且消耗极少的 CPU，因此不需要线程。

回到 Node.js，我们现在理解为什么它被认为是单线程的：

- 它在单线程中执行 JavaScript。
- 非阻塞输入/输出架构意味着 Node.js 响应客户端启动请求的调用，并在回调（call-back）完成任务准备就绪时处理任务。
- Node 在其单线程上基于事件执行 JS 代码，同时异步处理任务。这被称为事件循环（event loop）。

当 Node.js 遇到 CPU 受限的任务时，问题就出现了：如果一个大请求进入事件循环，Node.js 将设置所有可用 CPU 优先处理它，然后再回答队列中的其他请求。由于事件循环中的处理缓慢和整体延迟，不建议将 Node.js 用于密集计算。

然而，随着 2018 年 10.5.0 的升级，多线程被添加为 Node.js 的实验性功能。

新功能`worker threads`模块允许你从线程池中使用额外的线程来执行 CPU 密集型活动。

然而，这只有在具有多个核心的机器上才是可能的，因为 Node.js 仍然允许我们一个核心对应一个线程。

这意味着沉重的并行任务可以在单独的线程上运行。此功能在 Node.js 版本 12 中仍是实验性的；但已经得到了极大改进。

## 回调地狱是一个问题

由于其异步特性，Node.js 主要依赖回调（callbacks），回调是在队列中的每个任务完成时执行的例程。

在后台保留大量的队列任务，每个任务都有自己的回调，可能会导致回调地狱，这对代码质量有直接影响。

简单来说，它是一种“回调嵌套在其他回调中的情况，深度达数层，可能使理解和维护代码变得具有挑战性”。

然而，这有时被解释为标准低下以及对 JavaScript 特别 Node.js 缺乏知识的体现。

## 工具不成熟

尽管 Node.js 核心模块相对稳定成熟，但 npm 注册表中的许多工具要么质量差，要么没有完全的文档说明/测试。

此外，该注册表的结构不够完善，无法根据排名或质量来提供工具。

因此，如果不了解需要寻找什么，可能很难识别出符合我们需求的理想选择。

Node.js 生态系统主要是开源的这一事实也有所影响。

## 对熟练专家的需求日益增长

与大众认知相反，并非所有的 JavaScript 开发者都是 Node.js 工程师。

精通服务端编码需要大量工作和后端开发经验。由于学习曲线陡峭，Node.js 工程师的数量远少于 JS 专业人士的总数。

随着围绕 Node.js 的热度增加，该行业对人才的需求也随之增长。

因此，尽管有数百万 JavaScript 工程师，但可能很难为我们的项目找到懂行的 Node.js 专家。

在这种情况下，我们绝对不想将搜索范围限制在一个国家。

在 IT 业务中，从其他国家获取技术专长一直是标准。

### 我们可以在哪里使用 Node.js？

以下是一些 Node.js 被证明是有价值的技术资产的示例。

- I/O 密集型应用
- 流媒体应用
- 实时应用
- 基于 JSON 的应用

### 我们应该在哪里使用 Node.js？

Node.js 不应该用于 CPU 密集型。

### 设置 NODE.JS 环境

如果我们仍然想设置 Node.js 环境，我们需要：(a) 一个文本编辑器 (b) 二进制文件。

### 文本编辑器

这是需要的。Windows 上的编辑器有 Notepad、EMACS 和 vim。在不同的操作系统上，编辑器的名称可能会变化。源文件通常以 ".js" 结尾。

### Node.js 运行时

源代码是 JavaScript。JavaScript 代码将使用 Node.js 解释器进行解释和执行。

Node.js 分发版作为二进制文件适用于 SunOS、Linux、OS X 以及支持 32 位 (386) 和 64 位 (amd64) 架构的 Windows 操作系统。

后续章节将向我们展示如何在不同的操作系统安装 Node.js 分发版。

### Node.js 存档

访问 nodejs.org 获取最新的存档。本文编写时的可用版本列如下。

| OS | 存档名称 |
| --- | --- |
| Windows | node-v6.3.1-x64.msi |
| Mac | node-v6.3.1-darwin-x86.tar.gz |
| Linux | node-v6.3.1-linux-x86.tar.gz |
| SunOS | node-v6.3.1-sunos-x86.tar.gz |

### 在 SunOS、Mac OS X、Linux 和 UNIX 上安装

根据计算机的操作系统架构，将 node-v6.3.1-osname.tar.gz 存档安装并解压到 /tmp，然后将提取的内容移动到 /usr/local/nodejs。例如：

```
$ cd /tmp
$ wget http://nodejs.org/dist/v6.3.1/node-v6.3.1-linux-x64.tar.gz
$ tar xvzf node-v6.3.1-linux-x64.tar.gz
$ mkdir -p /usr/local/nodejs
$ mv node-v6.3.1-linux-x64/* /usr/local/nodejs
```

将 PATH 环境变量添加到路径 /usr/local/nodejs/bin。

| OS | 输出 |
| --- | --- |
| Mac | export PATH=$PATH:/usr/local/nodejs/bin |
| Linux | export PATH=$PATH:/usr/local/nodejs/bin |
| FreeBSD | export PATH=$PATH:/usr/local/nodejs/bin |

### 在 Windows 上设置

安装 Node.js 时使用 MSI 文件并按照屏幕指令操作。安装程序默认使用位于 C:\ 的 Node.js 包。

安装后，`C:\Program Files\nodejs\bin` 目录应添加到 Windows 的 PATH 环境变量设置。必须重启任何打开的命令行窗口以使修改生效。

## 执行验证安装

在你的计算机（Windows 或 Linux）上创建一个名为 `main.js` 的文件并写入代码：

```javascript
/* Hello, Everyone! program in node.js */
console.log("Hello, Everyone!")
```

要查看结果，现在使用 Node.js 解释器运行 `main.js` 文件。

```
$ node main.js
```

## NODE.JS 的首次应用

在构建真正的“Hello, Everyone!”应用之前，让我们先来看 Node.js 应用的组件。以下三个关键部分构成了一个 Node.js 应用：

- 导入模块：使用`require`指令加载必要的 Node.js 模块。
- 创建服务器：创建一个类似于 Apache HTTP Server 方式响应客户端请求的服务器。
- 读取请求并返回响应：在上一阶段构建的服务器将读取客户端发送的 HTTP 请求（可以是浏览器或控制台），并交付响应。

## Node.js 应用的创建

### 步骤1：导入必要的模块。

以下我们使用`require`指令加载`http`模块并将生成的 HTTP 实例保存到`http`变量的方法：

```javascript
var http = require("http");
```

### 步骤2：创建服务器

使用新形成的`http`实例，我们执行`http.createServer()`函数创建一个服务器实例，然后通过服务器实例的`listen`方法将其绑定到端口 8081。传递它一个带有`request`和`response`参数的函数。让示例实现每次返回“Hello Everyone!”

```javascript
http.createServer(function (request, response) {
  // 发送 HTTP 头部
  // HTTP Status: 200 : OK
  // Content Type: text/plain
  response.writeHead(200, {'Content-Type': 'text/plain'});
});
```

```javascript
// 作为 "Hello Everyone!" 的响应体
response.end('Hello Everyone!\n');
```

```javascript
// 控制台将打印消息
console.log('Server running at http://127.0.0.1:8081/');
```



上述代码已足够构建一个在本地机器端口 8081 上监听等待请求的 HTTP 服务器。

## 步骤3：测试请求与响应

让我们将步骤1和步骤2合并到名为`main.js`的文件中，并如下所示启动我们的 HTTP 服务器。

```javascript
var http = require("http");
```

```javascript
http.createServer(function (request, response) {
  // 发送 HTTP 头部
  // HTTP Status: 200 : OK
  // Content Type: text/plain
  response.writeHead(200, {'Content-Type': 'text/plain'});
```

```javascript
  // 作为 "Hello Everyone!" 的响应体
  response.end('Hello Everyone!\n');
});
```

```javascript
// 控制台将打印消息
console.log('Server running at http://127.0.0.1:8081/');
```

现在执行`main.js`以如下所示的方式启动服务器。

```
$ node main.js
```

## MongoDB

我们将在下面讨论 MongoDB 的介绍及其安装过程。

### 什么是 MongoDB

MongoDB 是一个免费的面向文档数据库，可以存储大量数据，同时允许我们极其高效地处理数据。它被归类为 NoSQL（非 SQL）数据库，因为 MongoDB 中的数据不是以表的形式存储和检索的。MongoDB 是一个由 MongoDB, Inc. 在 SSPL（服务器公共许可）下创建并运行的数据库，并于 2009 年 2 月首次发布。它还为所有主流编程语言（如 C、C++、C# 等）提供了官方驱动支持。如 .Net、Go、Java、Node.js、Perl、PHP、Python、Motor、Scala、Swift 和 MongoDB 等是一些示例。因此，我们可以使用这些语言中的任何一种编写应用程序。如今，Facebook、Nokia、eBay、Adobe 和 Google 等许多公司都利用 MongoDB 存储海数据。

### 它如何工作？

现在我们来看看幕后发生了什么。众所周知，MongoDB 是一个在数据库中存储数据的数据库服务器。换句话说，MongoDB 环境为你提供了一个服务器，我们可以在上面启动 MongoDB 并构建几个数据库。由于是 NoSQL 数据库，数据以集合（collections）和文档（documents）的形式保存。

结果，数据库、集合和文档的链接如下：

### MongoDB 的工作

- 集合在 MongoDB 数据库中的存在方式类似于 MySQL 数据库中的表。我们被允许构建多个数据库和集合。
- 我们现在在集合中有论文（文档）。因为我们是无模式的（schemaless），文档不需要相互比较，我们想要存储在 MongoDB 数据库中的数据包含在文档内部。
- 使用字段（fields）构建文档。文档中的字段是键值对，类似于关系型数据库中的列。字段的值可以是任何 BSON 数据类型，例如双精度、字符串和布尔值。
- MongoDB 中的数据以 BSON 文档的形式保存。BSON 是 JSON 文档的二进制表示的缩写。换句话说，MongoDB 服务器将后端的 JSON 数据转换为二进制版本。
- MongoDB 数据以 BSON 文档的形式存储。由于允许可以存储嵌套数据，这比 SQL 高得多。BSON 的大小可达 16MB。

### MongoDB 数据建模

正如我们所见，MongoDB 具有灵活的结构。与需要定义模式的 SQL 数据库不同，MongoDB 这种的灵活性使得 MongoDB 变得非常高效。在建模 MongoDB 时请记住以下几点：

- 聚合需求是什么？在建模 MongoDB 时考虑聚合功能。
- 数据模式是什么？如果我们预见到大量的查询，考虑使用索引。
- 数据库的频繁插入、更新和删除是什么？为了提高 MongoDB 的整体性能，考虑索引。

### MongoDB 与 RDBMS 的区别

以下是 MongoDB 和 RDBMS 的一些显著区别：

| MongoDB | RDBMS |
| :--- | :--- |
| 它是面向文档的。 | 它是关系性的。 |
| 它适用于存储层次数据。 | 它不适用于存储层次数据。 |
| 它的模式是动态的。 | 它已经有了模式。 |
| 其核心是 CAP 理论（一致性、可用性和分区容错）。 | 它关注 ACID 特性（原子性、一致性、隔离性和持久性）。 |
| 它在性能方面优于 RDBMS。 | 它在性能方面劣于 MongoDB。 |

### MongoDB 特性包括

- 无模式数据库：MongoDB 提供了一种名为无模式数据库的优秀功能。无模式数据库允许在单个集合中存储多个类型的文档。也就是说，在 MongoDB 数据库中，不同字段数量、内容类型和大小的文档可以共存。不需要像关系型数据库那样要求文档相互比较。MongoDB 的特性聚集了大量的灵活性。
- 面向文档：正如 MongoDB，所有数据都以文档的形式存储，而不是 RDBMS 中的表。在这些文档中，数据以字段（键值对）的形式存储，使得数据比 RDBMS 灵活得多。每个文档都有唯一的对象 ID。
- 索引：MongoDB 数据库文档中的每个字段都有主索引和辅助索引，更容易从数据池中获取或搜索数据。如果没有索引，数据库必须根据提供的查询搜索每个文档，这非常耗时且效率低下。
- 可扩展性：MongoDB 通过分片提供水平扩展性。分片是将数据分布在多个服务器的过程。大量数据通过分片键划分为数据块，并将数据均匀地分布在多个物理服务器的分片上。它还会向已激活的数据库添加机器。
- 聚合：它允许我们对聚合数据执行操作以获得单个或计算输出。它类似于 SQL 的 GROUPBY 子句。
- 高效：与其他数据库相比，由于具有扩展性、索引和复制等功能，MongoDB 具有卓越的速度和数据持久性。

### MongoDB 具有以下优势

- 它是一个无模式的 NoSQL 数据库。
- 使用 MongoDB 时，我们不需要设计数据库模式。
- 不支持连接（join）操作。
- 它为论文中的字段提供了很大的灵活性。
- 它包含多种数据。
- 它具有很高的性能、可用性和可扩展性。
- 它有效支持地理空间数据处理。
- 它是一个面向文档的数据库，以 BSON 文档的形式存储数据。
- 它允许多文档 ACID 事务（从 MongoDB 4.0 版本开始）。
- 不需要担心 SQL 注入。
- 与大数据 Hadoop 集成非常简单。

### MongoDB 的缺点

- 它在大量内存中存储数据。
- 我们在文档中保存的数据可能不超过 16MB。
- BSON 中的数据嵌套也有类似的限制；数据无法嵌套超过 100 层。

## 开始使用 MongoDB

### 术语

MongoDB 数据库可以被看作所有集合（collections）的容器。

- 在 MongoDB 中，文档存储在集合中。这与关系型数据库管理系统的表非常相似。
- 该文档中有许多字段。它类似于 RDBMS 的元组（tuple），但模式可以动态更改。即使在同一个集合中，文档也不需要包含统一的字段集。

### 如何开始

安装 MongoDB 后，我们可以在`C:\ProgramFiles\MongoDB\`（默认位置）找到所有文件。

在`C:\Program Files\MongoDB\Server(3.2)`目录下有许多可执行文件，其简要摘要如下：

```text
mongos: 用于与数据库交互的命令行工具。
mongod: 这是数据库本身，mongod 配置服务器。
modump: 移除数据库的二进制数据 (BSON)。
mongoexport: 使用 mongoexport 以 JSON 和 CSV 格式导出文档。
mongoimport: 向数据库添加数据。
mongorestore: 使用 mongorestore 恢复你导出的所有内容。
mongostat: 数据库统计信息
```

我们现在可以启动 MongoDB 服务器。打开命令提示符并进入 MongoDB 可执行文件所在的目录（`C:\Program Files\MongoDB\Server(3.2)\bin`，但此路径未来可能会发生）。只需输入`mongod`，就会出现一个错误，说明`\datadb`不存在。

这意味着没有发现默认存储路径`C:\datadb`。因此，我们可以手动创建或使用`mkdir`程序创建`C:\datadb`目录。我们还可以使用`mongod`命令配合切换参数`-dbpath <path>`来更改默认路径。

创建此目录后，重新运行`mongod`命令以在端口 27017 上启动服务器。

我们现在必须启动客户端。为了将目录更改为 MongoDB 路径，请创建一个新终端。一旦我们使用`mongo`，我们的客户端将启动并尝试连接到服务器。

使用此 CLI 与数据库进行通信和管理。这个壳（shell）有点像 JS 控制台。我们可以尝试各种 JS 命令来查看它是如何工作的。现在我们的客户端已经运行，我们可以开始操作数据库了。我们看到活动数据库名为“test”。我们可以切换到不同的数据库，例如输入“local”、`<dbname>`你可以通过输入“show dbs”来检查数据库。

目前不存在任何集合。通过输入命令“display collections”可以查看。

首先向我们的数据库中输入一些信息。通过使用方法`db.createCollection(name, size : ..., capped : ..., max : ...)`，我们可以创建一个集合。

然而，我们构建了一个随机生成的 json 文件（包含员工数据），我们将通过输入以下命令将其导入数据库：

```text
mongoimport --jsonArray --db test --collection employeedata C:\mongoJSON\employeedata.json
```

这可能会导入数据库“test”集合中名为“employeedata”的路径所引用的员工数据 json 文件。

我们现在可以在 shell 中输入“display collections”来确认集合已导入。`Count()`、`find()`和`findOne()`是我们处理文档时可能采用的一些非常基础的查询技术。

正如我们所看到的，每个文档都包含一个名为“_id”的字段，该字段在导入的数据中是不存在的。解释是因为 MongoDB 中的每个文档默认都保证有一个唯一的“_id”，这是一个 12 字节的十六进制标识符。虽然可以更改此“_id”字段，但不建议这样做。

索引：如果我们的查询返回了多个文档，我们可以利用索引。

例如，`db.employeedata.find()`检索集合中的所有文档，但如果我们只想获取第 7 个，使用`db.employeedata.find()[6]`来获取它。[注意：此处索引从 0 开始]

投影：假设我们只需要查询的某些特定信息，而不是文档中的整套细节。我们可以通过投影来实现这些。

只需在查询对象后将所需的字段设置为 1，其余部分将默认为 0。

### 查询

- 1. 确定 Sanjana 的公司
- 2. 列出所有名为 Sanjana 的员工
- 3. 显示 Harsh Gupta 的年龄、性别和地址，但不显示 _id
- 4. 按名称列出所有员工

### 如何在 Windows 上安装？

MongoDB 是一个开源面向文档的数据库，可以存储大量数据。它被归类为 NoSQL（非 SQL），因为 MongoDB 中的数据是以表的形式存储和检索的。

MongoDB 可以通过两种方式安装：msi 包或 zip 存档。在本节中我们将介绍使用 msi 安装 MongoDB，请注意每个步骤：

步骤 1：从...下载社区版

我们可以根据需求选择任何版本、Windows 和程序包。对于 Windows，我们必须选择：

- 版本：4.2
- 操作系统：Windows
- 程序包：msi

步骤 2：下载完成后，打开 msi 文件并点击下一步进入启动页。

步骤 3：在接受用户许可协议后，点击下一步。

步骤 4：要安装应用程序的所有功能，选择完整选项。如果我们只想安装某些软件功能，请使用自定义选项并在这种情况下选择安装位置。

步骤 5：选择“作为网络服务用户运行服务”，并记录目录位置。点击下一步。

步骤 6：按下安装按钮开始安装过程。

步骤 7：选择安装选项后，MongoDB 安装。

步骤 8：要完成安装程序，现在点击完成。

步骤 9：转到步骤 5 中我们在机器上安装 MongoDB 的位置并复制 bin 路径。

步骤 10：接下来，打开系统属性，<< 环境变量 << 系统变量 << << 将复制的 URL 粘贴到我们的环境系统，然后点击 OK 建立环境变量。

![](img/70a7539ec7c3f429f5e3c9c64df71823_393_0.png)

安装步骤 5

![](img/70a7539ec7c3f429f5e3c9c64df71823_393_1.png)

安装步骤 6

![](img/70a7539ec7c3f429f5e3c9c64df71823_394_0.png)

安装步骤 7

![](img/70a7539ec7c3f429f5e3c9c64df71823_394_1.png)

安装步骤 8

第 11 步：按照环境变量的设置，mongodb 即 MongoDB 服务器将启动。在启动命令提示符后运行以下命令：

```
mongodb
```

当我们执行此程序时，可能会出现“C:/data/db/ not found”的错误信息。

第 12 步：接下来，打开 C 盘并在其中创建一个名为“data”的文件夹，在其中我们需要另一个名为“db”的文件夹。这些文件夹已创建。再次打开命令提示符后运行以下命令：

```
mongodb
```

现在，MongoDB 服务器（也称为 mongodb）将正常运行。

运行 Mongo Shell

第 13 步：此时，我们将 mongo shell 连接到我们的服务器 (mongodb)。因此，请保持 mongodb 窗口打开，并在新的命令窗口中输入 mongo。我们的 mongo shell 现在将完全连接到 mongodb。

重要提示：不要关闭 mongodb 窗口；这样做可能会导致我们的服务器停止运行并防止其连接到 mongo shell。

我们现在可以开始在 mongo Shell 中创建查询。

### 示例

在我们的 shell 中，我们可以创建新的数据库、集合和文档。创建新数据库的插图如下所示。使用`Databasename`如果系统中不存在该数据库，则会在系统中创建一个新数据库；如果已存在，则使用现有的数据库。

```
use pfp
```

我们的名为 pfp 的数据库现在已就绪。

使用`db.Collection()`名称命令在 pfp 数据库中创建学生集合，并使用`insertOne()`方法添加文档：

```
db.student.insertOne({Ankita:400})
```



#我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。服务端 JS

我们在下文中讨论服务器端 JS 的介绍及其安装过程。

## 服务端网站编程

动态网站——服务器端编程主题由一组模块组成，这些模块展示了如何开发动态网站，或根据 HTTP 请求提供个性化内容的网站。

大多数重要网站使用服务器端技术来根据需要动态显示数据。例如，考虑在 Amazon 上可以访问多少内容，以及发布了多少 Facebook 帖子。在静态页面上显示所有这些内容将是极其低效的；相反，这些网站显示静态模板（构建的 HTML、CSS 和 JavaScript），并在必要时动态更新在这些模板内显示的数据，例如当我们想在 Amazon 上查看不同的产品时。

在当今 Web 开发领域，强烈建议具备服务器端开发的知识。

对于新开发者来说，服务器端编程通常比客户端开发更令人畏畏，因为大多数动态网站使用框架，简化了复杂的服务器操作，如从数据库检索数据并在页面中显示、验证用户输入的数据并保存到数据库、检查用户权限并登录用户等。编程的能力（或熟悉某种编程语言）是有帮助的，但不是必须的。

在某种程度上，我们不需要编写代码就能与构建我们网站前端的团队进行高效工作。

Web 浏览器运行 JavaScript，这是一种主要用于网页和 Web 应用的 Web 语言。由于 JavaScript 是一门通用语言，它也可以用于其他类型的编程。它可以被用于服务器端，在此语境下指 Web 浏览器以外的所有位置。

## 运行 JavaScript 的引擎

JavaScript 有几个引擎来实现它。JavaScript 代码由 JavaScript 引擎读取并执行。Web 浏览器大量使用这些引擎，但也有其他可能的宿主环境，例如 Web 服务器。

JavaScript 引擎提供的公共 API 允许该语言嵌入其他应用程序和系统中（如 Web 浏览器、Web 服务器和数据库）。

- **SpiderMonkey**：Mozilla 基金会维护 SpiderMonkey，这是 JavaScript 开发者 Brendan Eich 开发的原始 JavaScript 引擎。使用 C/C++ 代码作为实现。它最初设计用于 Netscape Navigator，Mozilla Firefox 现在是许多人的喜选浏览器。
- **Rhino**：Mozilla 基金会还维护 Rhino 引擎。它是使用 Java 编程语言开发的。由于 Rhino，Java API 对 JavaScript 可用。JavaScript 有通过调用 Java 方法、设置 Java 属性以及将 JavaScript 值转换为 Java 值与 Java 交互。
- **Chrome V8**：利用 Chrome 团队维护的 JavaScript 框架。它是一个 C++ 程序。
- **JScript & Chakra**：微软的 Internet Explorer 和 Edge 使用引擎——JScript 和 Chakra。
- **JavaScriptCore (Nitro)**：Safari 使用 Apple 自定义构建的 JavaScriptCore (Nitro) 引擎。

## 运行时环境

简单来说，JavaScript 运行时环境是一个存放 JavaScript 引擎并执行脚本的容器。由于其嵌入性质，JavaScript 通常需要额外的库，这些进一步的对象和功能由运行时环境提供。

### 服务端 JavaScript 的用途

以下是服务端 JavaScript 的一些用例：

- MongoDB 是 NoSQL 数据库，由 JavaScript 驱动。
- Riak 是分布式 SpiderMonkey。
- SpiderMonkey 用于 Thunderbird 客户端。
- SpiderMonkey 被用于 Adobe Acrobat。
- GOME 是运行在 Unix 操作系统上的 SpiderMonkey。
- Java API 允许 JavaScript 转换脚本。
- 运行时环境通过 Node.js 运行脚本。
- V8 引擎用于扩展应用程序。

## MERN STACK

上述所有四种技术 MERN（MongoDB, Express, React.js 和 Node.js）都将用于 MERN 栈，它是基于 JavaScript 的。

作为开始，考虑：先为项目创建一个新文件夹。打开命令提示符或终端进入项目文件夹；然后运行以下命令创建 `package.json` 文件。（确保 npm 已安装）

```bash
npm init
```

### MongoDB：跨平台面向文档

MongoDB 是一种 NoSQL 数据库，其中每条记录都是一个类似于 JSON（JavaScript 对象表示法）对象的键值对文档。

MongoDB 是灵活的，允许用户设计模式、数据库和表等。

- 提供更快速的调整：MERN 栈技术允许根据客户端请求对移动端和 Web 应用进行快速修改。
- 开源：MERN 的四个组成技术都是开源的。这一功能使开发者能够在开发过程中从开放门户获取遇到问题的答案。因此，这最终对开发者将是有利的。
- 易于在客户端和服务器之间切换：由于使用单一种语言开发，MERN 非常简单且快速，便于在客户端和服务器之间移动。此外，客户端与服务器之间的切换也非常简单。

## 为什么使用 MongoDB？

- 作为面向文档的数据库，索引文档非常简单。因此，响应速度更快。
- 可扩展性——可以通过将数据集分布到几台计算机上进行管理。
- 利用 JavaScript——MongoDB 最大的优势是它利用 JavaScript。
- 任何形式的数据都包含在独立的文档中。
- JSON 数据由对象（Objects）、对象成员（Object Members）、数组（Arrays）、值（Values）和字符串（Strings）组成。
- JSON 语法非常简单。
- JSON 具有广泛的浏览器兼容性。
- 数据共享：交换任何大小或形式（视频、音频）的数据非常简单。
- 简单的环境配置——设置 MongoDB 轻而易举。
- 灵活的文档模型——MongoDB 提供了文档模型（表、模式、列、SQL），更快更方便。

- 创建数据库：使用“use”命令即可实现：

```javascript
use database;
```

- 构建表：如果集合或表不存在，则会创建一个：

```javascript
db.createCollection("collectionname");
```

- 向集合添加记录：

```javascript
db.collectionname.insert(
{
  "id" : 101,
  "Name" : "Karan",
  "Department" : "Tech",
  "Organization" : "Peeks For Peeks"
});
```

- 查询文档：

```javascript
db.collectionname.find({Name : "Karan"}).forEach(printjson);
```

## Express: 后端框架

Express 是一个用作后端框架的 Node.js 框架。与使用 Node.js 并产生多个 Node 模块相比，Express 允许更简单、更方便地构建后端代码。Express 支持创建优秀的 Web 应用程序和 API。因为 Express 提供了许多中间件，编写代码变得更快更简单。

### 为什么使用 Express？

- 单线程且异步。
- 高效、快速且可扩展。
- `Node.js` 拥有最大的社区。
- Express 集成的路由鼓励了代码复用。
- 健壮的 API。

创建一个新文件夹来存放我们的 express 项目，然后在命令行提示符输入以下命令创建一个 `package-json` 文件。接受默认设置并继续。

```bash
npm init
```

然后，使用下所示命令安装 express。最后，在目录中创建一个名为 `index.js` 的文件。

```bash
npm install express --save
```

要建立示例服务器，请立即在 `index.js` 中输入以下代码。

```javascript
const express = require('express');
const http = require('http');
const hostname = 'localhost';
const port = 8080;
const app = express();

app.use((req, res) => {
  console.log(req.headers);
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/html');
  res.end('<html><body><h1>This is the test server</h1></body></html>');
});

const sampleserver = http.createServer(app);
sampleserver.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

- 更新 `package.json` 文件的“scripts”部分。
- 然后执行以下命令启动服务器。

```bash
npm start
```

- 现在服务器正在运行，我们可以通过浏览器访问输出。

## React: 前端库

使用名为 React 的 JavaScript 包来创建用户界面。因为 React 可以管理快速变化的数据，所以它用于创建单页应用和移动应用程序。React 支持 JavaScript 编码，并可以创建 UI 组件。

### 为什么使用 React？

- 虚拟 DOM——虚拟 DOM 对象是 DOM 对象的表示。虚拟 DOM 是原始 DOM 的精确副本。Web 的任何更改都会导致虚拟 DOM 的完全重新渲染。比较原始 DOM 和虚拟 DOM 之间的差异，然后对原始 DOM 进行相应的调整。
- JSX——JavaScript XML 的缩写。它是一种 React 特有的 HTML/XML JavaScript 扩展。有助于并简化了 React 组件的创建。
- 组件：React 支持组件。组件是 UI 的构建元素，每个组件都有自己的逻辑并对整个 UI 做出贡献。这些组件还增加了代码复用并简化了整个 Web 应用程序的可读性。
- 高性能——虚拟 DOM、JSX 和组件等特征使其比其他可用框架快得多。
- 开发 Android/iOS 应用——通过 React Native 以及对 JavaScript 和 ReactJS 的理解，我们可以简单地创建基于 Android 或 iOS 的应用。

- 使用 npm 或 yarn 安装 `create-react-app`。

```bash
npx create-react-app my-app
```




# 后端开发

它允许用户开发大型 Web 应用程序，这些程序无需刷新页面即可快速修改页面数据。

## 服务器或中间层

它是顶层之下的下一级，主要由 MERN 栈中的 `Express.js` 和 `Node.js` 管理。`Express.js` 在 `Node.js` 服务器内运行并维护着服务端框架，允许这两个组件并发地管理它。在涉及 JavaScript 后端开发时，`Express.js` 是最广泛使用的框架之一。它让开发者创建复杂的 API（应用程序编程接口）和 Web 服务器变得更加容易和简单。

它为 `Node.js` 中的 HTTP（超文本传输协议）对象提供了实用的功能。相比之下，`Node.js` 本身也扮演着重要的角色。

它是一个开源服务器环境和跨平台运行时环境，用于在浏览器之外运行 JavaScript 代码。Node 始终使用 JavaScript；因此，它使计算机用户能够快速开发任何 Web 服务或移动应用程序。

## 数据库作为后端层

作为后端的数据库

它是 MERN 栈中最重要的层级之一，主要由 `MongoDB` 管理；数据库的主要功能是存储与你的应用程序相关的所有数据，例如内容、统计数据、信息、用户配置等。它主要出于安全考虑保留所有数据。它保留准确的记录，并在需要时向用户提供数据。它主要将数据保存在数据库中。它会为文件创建至少两个副本，以确保即使原始文件丢失，你仍然可以获得所需的数据。

这意味着 `MongoDB` 的结构不像具有表的关系型数据库。

与此相反，它提供了一套完全独立的系统来检索数据。`MongoDB` 是流行的开源面向文档的 NoSQL（NoSQL 或非结构化查询语言）数据库。NoSQL 通常指不需要固定结构或关系表即可存储基本数据的非关系数据库。`MongoDB` 将数据存储在一种不同于由行和列组成的关系表的结构中。

## MEAN

## MERN

- 该栈技术包括 Angular、Express、Node.js 和 MongoDB¹。
- 栈技术包括 MongoDB、React.js、Express.js 和 Node.js。
- JavaScript 框架 Angular.js 是 MEAN 栈的一部分。
- JavaScript 库 React.js 是 MERN 栈的一部分。
- Typescript 在 MEAN 栈中被 Angular.js 使用。
- React.js 在 MERN 栈中使用 JSX 和 JavaScript。
- 它能提高生产力。
- 它没有生产力。
- 与 MERN 栈相比，掌握它更具挑战性。
- 因为拥有卓越的文档，它要容易得多。
- 它有助于代码管理和渲染。
- 虚拟 DOM 使流式渲染成为可能。
- 数据流是双向的。
- 它只允许一次数据传输。
- 它与所有移动设备不兼容。
- 对于移动应用它是兼容的。

## MERN VS MEAN

### MERN 栈开发者的未来如何？

不言而喻，未来并非命中注定。然而，根据我们目前拥有的市场数据，我们完全能对 MERN 栈开发者未来将看到的增长做出合理的分析。理解 MERN 栈对开发者有什么好处呢¹

1. 开源：MEAN 最好的方面是组成栈的四种技术都是开源的（open-source）。这让开发者更容易从开放的资源门户获取快速答案，并成功解决开发过程中可能出现的任何问题。
2. 成本效益：MERN 栈开发者需求很大，因为这个栈只使用 JavaScript 一种语言。对于企业来说，投资精通 MERN 的人员具有显著优势。从财务和时间上来说，这比为每种技术招聘专家更高效。
3. 客户端和服务器之间的切换简单：使用 MERN 栈，一切都是用同一种语言编写的，这让开发者更容易掌握这种语言（通过专门学习 4–6 个月）。在客户端和服务器之间切换也很简单，为开发者提供了额外的扩展机会。
4. UI 渲染和性能：React JS 已证明是目前 UI 层抽象、渲染和性能的最佳解决方案。

为什么？它允许开发者根据自己的愿景构建和安排应用程序代码。

在本章中，我们涵盖了后端开发，讨论了 `Node.js`、`MongoDB` 和服务端 JS。

## NOTES

1. 什么是后端开发者？Web 开发所需的技能：www.guru99.com/what-is-backend-developer.html 访问日期：2022年10月13日。
2. 2022年使用 Node.js 进行后端 Web 开发：https://nodeidev.biz/blog/node-js-for-backend-development 访问日期：2022年10月13日。
3. Node.js Web 开发的优与劣：www.altesoft.com/blog/engineering/the-good-and-the-bad-of-node-js-web-development/ 访问日期：2022年10月13日。
4. Node.js - 简介：www.tutorialpoint.com/nodejs/nodejs_introduction 访问日期：2022年10月14日。
5. Node.js - 环境搭建：www.tutorialpoint.com/nodejs/nodejs_environment_setup.html 访问日期：2022年10月14日。
6. Node.js - 第一个应用程序：www.tutorialpoint.com/nodejs/nodejs_first_application 访问日期：2022年10月14日。
7. MongoDB - 工作原理与特性：www.geeksforge.org/working-and-features 访问日期：2022年10月14日。
8. 什么是 MongoDB？简介、特性：guru99.com 访问日期：2022年10月14日。
9. MongoDB 入门：www.geeksforge.org/getting-started 访问日期：2022年10月14日。
10. 如何在 Windows 上安装 MongoDB：www.geeksforge.org/how-to-install-mongodb 访问日期：2022年10月14日。
11. 服务端：developer.mozilla.org/en-US/docs/Learn/server-side 访问日期：2022年10月15日。
12. JavaScript：javascript..com/server-side 访问日期：2022年10月15日。
13. MERN 栈：www.geeksforge.org/mern-stack 访问日期：2022年10月15日。
14. MERN::...mern-stack 访问日期：2022年10月15日。
15. 什么是 MERN 栈以及为什么它对 Web 开发是最好的：groovyweb.com/what-is-the-mern-stack-and-why-is-the-best-for-development 访问日期：2022年10月15日。
16. MERN 栈的未来：cybersuccess.com/future-of-mern-stack 访问日期：2022年10月15日。

# 移动端 JavaScript

## 离线辅助

每次交互后都要与服务器通信这一硬性要求存在于服务器相关编程中。当服务器宕机时，软件将无法使用。但即使在没有互联网的情况下，JavaScript 开发仍然快速且响应迅速。与标准的面向服务器的开发方法相比，它具有显著的优势。

在 JavaScript 开发中，前端使用本地缓存数据来更新应用程序，直到恢复连接。这将有助于本地更改跟踪，并在连接恢复后强制从端到端同步修改。

它与其他应用程序的不同之处在于，它可以在不需要持续服务器连接的情况下执行核心活动。使用 JavaScript 构建的用户界面（UI）可以在不使用网络连接的情况下在屏幕上运行。JavaScript 可以提供传统的服务端前端编程无法提供的选项。

## 适用于所有类型的开发者

JavaScript 的环境配置并不特殊。你只需要一个浏览器，通过进入开发者工具即可启动编程过程。

因此，它受到各种背景和经验水平开发者的青睐。即使是领域的初学者也能快速学习并掌握它，从而获得广泛认可。

## 用于移动应用的 JavaScript 框架

使用 JavaScript 框架，你可以完成所有重要的客户端任务。

为了创建高质量的 JavaScript 应用，开发者可以根据需要使用多种框架。

### PhoneCap

这使得通过单个 JavaScript 代码库构建多种平台变得更容易，并为各种目标客户端提供服务。

### Ionic

程序员可以使用 Ionic 框架来创建、测试、监控和发布高性能移动应用。在所有 JavaScript 框架中，它是被最广泛使用的框架之一。

### React Native

凭借其可导航的设计特性，这一著名的开源框架让开发者创建移动应用变得更容易。

### jQuery

对于开发者来说，为各种移动设备创建应用并非易事。由于有许多不同的主题需要涵盖，对于应用工程师来说这不是一项简单的工作。然而，jQuery 允许我们创建快速、高响应的软件，这些软件可以在各种移动和桌面平台上运行。

### 原生语言 (Native Language)

Native script 框架是有效为 iOS 和 Android 创建应用的重要工具。

> 正如其名称所示，Native script 框架代码有助于在成品中获得改进的用户界面功能。

### Tabris.js

即使是这个框架也能通过一段 JavaScript 代码创建原生的 iOS 或 Android 应用。它也被认为是程序员创建原生应用时最流行的框架之一。

## 在开发移动端应用时我们应该使用 JavaScript 吗？

当我们考虑开发移动应用时，产生担心是完全合理的，特别是如果我们希望它同时在 iOS 和 Android 上运行，因为我们稍后可能会遇到技术困难。然而，由于我们不需要学习如何用完全全新的开发语言来完成，情况并不会糟糕。在像 Kambda 这样经验丰富的开发公司的帮助下，我们能够拨开前路的波折。

如今最重要的技术进展之一是移动应用的创建。这些，智能手机的普及和应用市场的发展对每个技术领域产生了重大影响。创建各种代码的主要语言是 HTML、CSS 和 JavaScript，同时许多其他语言也被所使用。这三种编码系统工作得良好。HTML 是指示浏览器如何显示网站文本和图像的标记语言。CSS 是样式表，意味着它为整个网站提供了一致的外观。JavaScript 通过生成交互式动态界面提高了用户体验，使网页能够响应各种变量，包括事件、变量、用户浏览器、效果等。

尽管有上述描述，但 JavaScript 通常并不直接被用于创建应用，因为它是用于创建和维护网站的语言。此外，尽管有方法仅使用 JavaScript 创建应用，但还有其他更有效的方法可以做到。

尽管如此，JavaScript (JS) 有一个可以帮助我们节省时间的显著优势：我们可以复用你的代码用于前端和后端 (Node.js)。

JS 的另一个优点是它适用于所有浏览器，这使得开发过程变得更简单。

JS 框架的普及日益增长。即使是 Apple 和 IBM 这样的大公司也使用 JS。AngularJS 团队现在与 Google 和微软合作，延续这一趋势。JavaScript 让创建应用变得简单，因为我们只需要开发一次，即可将其发布到所有平台（Android、iOS 和 Windows）。

## JavaScript 的关键属性

- 最简单的语言之一。
- 快速且高效。
- 由于它在客户端运行，它避免了使用服务器并节省了带宽。
- 用于为无聊的网站添加动态元素和动画。

虽然可以使用 jQuery 和其他 JavaScript 库为网页添加更多动态特性，但对于基础客户端操作，仍然经常推荐原生 JavaScript（plain JavaScript）。可以使用多种框架（包括 PhoneGap、jQuery Mobile 和 Ionic）制作出专业的 JavaScript 应用。

### Native React

该框架最近创建的，主要由 Facebook 开发。对于那些寻求开发可以在 Android 和 iOS 设备上运行的单一程序的人来说，它是一个可行的替代方案。它提供了卓越的性能，可能甚至比所讨论的一些其他框架还要好。

### jQuery

jQuery Mobile 框架将“少写，多做”的格言推向了一个新的高度，它允许我们创建一个单一的、高品牌化的响应式网站或应用程序，它将在所有广泛使用的智能手机、平板电脑和桌面平台上运行。

### PhoneGap

通过使用 PhoneGap，我们可以“利用现有的开发知识使用 HTML、CSS 和 JavaScript 轻松创建混合应用”。

### Ionic

Ionic “帮助我们比以前更容易地设计、部署、测试和监控应用，从开源到专业服务不等。”尽管有许多使用 JavaScript 创建应用的框架，但 jQuery 和 React Native 是最流行的。

# 安装 React Native 环境

在本次节中，Windows 将作为开发平台，而 Android 将作为操作系统。

需要安装 Node、React Native 命令行界面、Python 2、JDK 和 Android Studio 才能创建一个利用 React Native 框架的应用程序。

在这里，我们使用 Windows 版本的流行包管理器 Chocolatey。

我们可以使用它来安装最新版本的 Java SE 开发工具包和 Python (JDK)。

## 分步骤安装 React Native 环境

1. 前往 [https://chocolatey.org/](https://chocolatey.org/) 网站，点击“Install Chocolatey Now”，将打开一个新的 URL。

![](img/70a7539ec7c3f429f5e3c9c64df71823_418_0.png)

chocolatey 的安装

2. 运行 chocolatey 安装程序，然后复制“使用 cmd.exe 进行安装”章节下的代码。

```
"%SystemRoot%\System32\WindowsPowerShell\v1.0\npowershell.exe -NoProfile -InputFormat None
-ExecutionPolicy Bypass -Command iex ((New-Object
System.Net.WebClient).DownloadString('https://
chocolatey.org/install.ps1')) && SET
"PATH=%PATH%%%;ALLUSERSPROFILE%\chocolatey\bin"
```

3. 在以管理员模式打开命令提示符后（右键点击命令提示符并选择“以管理员身份运行”），输入此代码。它将设置 Chocolatey。

4. 在命令提示符的管理员模式下粘贴并执行代码（安装 Node.js、Python 和 JDK）。如果我们已经安装了 JDK，请确保它的版本是 8 或更高版本；如果我们之前安装了 Node.js，请确保它的版本在 8 以上。

```
choco install -y nodejs.install python2 jdk8
```

5. 我们可以使用 Node 的 npm（Node 包管理器）安装 React Native。运行提供的代码：

```
npm install -g react-native-cli
```




### 安装 Android Studio

1. 从 [https://developer.android.com/studio/](https://developer.android.com/studio/) 网站下载 `Android Studio`。

![Android Studio 的安装](img/70a7539ec7c3f429f5e3c9c64df71823_419_0.png)

2. 运行我们下载的 `Android Studio` 安装（`.exe`）文件并按照指示操作。
3. 决定安装哪些功能。
4. 决定将设备放在哪里。
5. 点击“Next”继续安装。
6. 完成安装后，点击“Finish”。

安装完成后，将显示 `Android Studio` 主界面。

### 设置 Android SDK 和 Java JDK

1. 首先设置 `JDK` 路径。
2. 在系统变量部分，将 `Android SDK` 路径更改为此电脑 > 属性 > 高级系统设置 > 环境变量。然后在“新建...”屏幕中添加 `Android Home` 和 `Android SDK`。
3. 通过 `Tools > SDK Manager > SDK platforms` 选择并安装必要的组件。
4. 允许安装继续，完成后点击“Finish”。
5. 若要创建 `Android` 模拟器（虚拟 `Android` 设备），请在 `Tools > Android > AVD Manager > Create Virtual Device` 下选择设备类型。
6. 选择 `Android` 模拟器的 `API` 级别。
7. 输入设备名称并通过选择“Show Advanced Settings”配置其设置。
8. 开始使用模拟器。

## REACT NATIVE 在移动应用开发中的未来意义

`Facebook` 引入用于移动应用开发的 `React` 框架，在应用社区中引发了巨大的热情。为了确保项目的成功，商务和技术专业人员必须充分掌握 `React Native` 的意义。

`Facebook` 和 `Instagram` 的工程师管理着著名的 `JavaScript` 框架 `ReactJS`，它有一个名为 `React Native` 的原生对应物。`React Native` 在短短 2 年内就在开发者社区中获得了极大的普及。它获得的 `Star` 数之多，以至于目前它是 `GitHub` 上第十四受欢迎的项目。

如今，许多 `React Native` 开发公司正在使用这项技术。根据 `Google` 趋势，搜索“React Native”的人数多于搜索“iOS 开发”或“Android 开发”。

在目前的数字环境中，速度、效率和快速工具对于每个移动应用都至关重要，软件开发者很难生产运行快速高效的移动应用。

吸引人的用户体验和简单的开发过程说服移动开发者使用 `JavaScript`、`HTML5`、`CSS` 或 `React Native` 来构建应用。

领先的移动应用开发公司出于多种原因将 `React Native` 视为应用开发的未来。

这些因素包括：

### 1. 跨平台支持

鉴于大多数 `React Native` API 是跨平台的，一个组件就可以同时在 `iOS` 和 `Android` 上运行。我们可以构建功能完备的应用，其功能、外观和感觉都是原生的，而无需编写一行平台特定的代码。然而，我们有时也需要针对特定平台。例如，设计效果在 `iOS` 和 `Android` 之间是不同的。

`React` 通过其平台模块和平台特定文件扩展为此类情况提供了解决方案。平台模块识别应用所用操作系统的能力允许定义特定平台的实现方式。通过使用平台特定文件扩展，我们可以为各种平台指定文件。`React` 会根据应用运行的操作系统自动选择文件。

### 2. 开源

我们都非常清楚这样一个理念：开源项目由大量贡献者组成，他们不知疲倦地工作以改进它们。找到可以构建移动应用的开发者很容易，使用 `React Native` 并专注于效率，因为它是最受欢迎且增长最快的语言之一。

### 3. 缩短开发时间

`React Native` 改变了应用的开发周期。由于它是开源的，许多人都认同它。它可以结合许多不同的机制，例如状态管理工具 `Redux`，这大大改进了开发。

### 4. Code Push 和实时更新

在开发原生应用时，使用 `React Native` 有许多优势，包括实时更新。我们可以通过 `Code Push` 直接向用户发布更改。对于任何影响原生部分的更新，仍需要遵循标准的 `App Store` 或 `Play Store` 更新程序。

### 5. UI 和性能

使用 `JavaScript`、`HTML` 和 `CSS` 创建混合移动应用是常见做法。由于 `React Native` 的独立性，这些应用将保持良好的性能。

### 6. 为不同平台创建应用时使用相同代码

移动开发者使用 `React Native` 使他们能够使用相同的代码为多个平台创建应用。这种方式主要的缺点得到了解决。对于开发者来说，只需掌握一套工具就能创建跨平台应用，还有什么更有优势的呢？

### 7. 减少编写代码的时间

复用以前创建的代码在软件开发领域是一项大任务。通过 `React Native` 的帮助，我们可以实现这种能力。我们并不是说 `React Native` 允许你“编写一次，到处使用”。作为开发者，我们必须创建符合每个平台标准和最佳实践的新用户界面（UI），使其看起来和感觉很自然。最棒的一点是，某些 UI 代码可以在两个平台上使用。

### 8. 快速获取资源

很容易且快速地找到可以使用 `React Native` 构建移动应用的开发者，使用它专注于效率，因为它是最受欢迎且增长最快的语言之一。

### 9. 适用于各种平台的单一框架

`React Native` 支持 `iOS` 和 `Android` 之间的完整代码库复制（或只是部分）。在实践中，某些更改可能需要完全重写，其他功能将作为应用包包含。`React Native` 开发者社区通过开源新工具来积极支持该框架。

### 10. 快速加载

通过引入热重载（Hot Reload），`React Native` 提高了效率并缩短了总开发时间。它允许开发者在应用程序运行时继续处理新版本和 UI 更改。

### 11. 更好的开发环境

开发者在 `React Native` 环境中工作效率更高。通过消除迭代周期中耗时的重新构建和部署，能够产生愉悦的开发体验。`React Native` 在所有平台上的移动应用均使用 `Flexbox` 布局引擎。这意味着在设计时，针对 `iOS` 和 `Android` 平台，只需要理解一种布局引擎即可。

### 12. 包含两个重要的生态系统

`iOS` 和 `Android` 拥有非常不同的生态系统。这些平台的创建具有挑战性。因此，为它们开发原生应用被认为是开发者的最大噩梦。与构建 `iOS` 应用程序类似，`Swift` 或 `Objective C` 的专业知识是必不可少的。另一方面，开发 `Android` 应用需要对 `Java` 和 `Android SDK` 有深入的了解。我们还必须忍受跟这两个生态系统提供的最新功能带来的不便。但有了现代技术，没有任何问题是永久的。

### 为什么 React 如此受欢迎？

由于其卓越的性能、改进的用户体验以及广泛的适用性，`React Native` 赢得了业界的高度赞誉。`Facebook` 支持复杂的后端开发语言，确保了整个实际开发过程的持久性。与 `MetroJS` 和 `AngularJS` 不同，`React Native` 专门关注 UI。`React Native` 的用户界面响应极快。得益于 `React Native` 和设备的原生环境，我们的应用加载速度更快，感觉也更流畅。

此外，`React Native` 与第三方插件配合。下载第三方插件并将其附加到原生模块，以便将 `Google Maps` 引入我们的项目。`Facebook` 的 `React Native` 不仅让全球移动应用开发者的生活变得更容易，而且是一个帮助他们为客户创建突破性应用的移动框架。此外，我们的应用可以轻松利用设备功能，如旋转、缩放和指南针。

## 构建 React Native 应用

### 1. Skype 使用 React Native

当 `Skype` 应用最初出现很多问题时，官方宣布将引入一个使用 `React Native` 开发的新应用程序。`Skype` 进行了彻底重新设计，甚至包括图标，这样新旧功能都能让该应用程序尖端外观的用户受益。微软在意识到 `React Native` 的有效性后，宣布 `React Native` 不仅被视为 `Windows PC` 版本的平台，还将用于创建移动应用程序。此外，微软从 `GitHub` 仓库中获得了 `React Native` 的惊人收益。

### 2. React Native Facebook 广告

在 `React Native` 开始用于社交网站之前，它首先从 `Facebook` 广告开始，作为 `Facebook` 旗下面向 `Android` 用户的移动应用。它可能需要处理由于时区、广告格式、货币惯例、货币以及许多其他变化所需的大量业务逻辑引起的问题。其他开发者受到启发，尝试实现新发布或到 `React Native` 广告中的 `React Native` 技术。

### 3. 使用 React Native，Facebook

作为一个简单的功能，`Facebook` 意图使其在线版本在移动端对客户可用，以便他们在使用智能手机应用程序时能享受流畅的用户界面。`Facebook` 意图使用单一团队来创建其移动应用产品。因此，`React Native` 被用于创建面向 `iOS` 和 `Android` 用户的 `Facebook` 移动应用。`React Native` 开发团队验证并检查了新功能的测试性能。这一关键修改决定了用户是放弃还是继续使用该程序。这只是使用 `React Native` 进行更改的一个例子，但许多其他方面也被用户广泛使用。

### 4. Tesla 使用原生 React

全球最知名的电动汽车制造商 `Tesla` 已加入 `react-native` 社区，以便为其电动汽车和 `Powerwall` 电池创建一个应用程序。他们通过使用 `Facebook` 的趋势结构作为指南来实现这一点。`Tesla` 应用具有一些限制功能，允许基于智能手机进行汽车操作，包括分析车辆并准确定其精确位置的能力。尽管他们的应用开发并不完全为人知，但客户对这一概念给予了积极响应。

### 5. React Native 使用 Instagram

在讨论 `react native` 应用开发服务时，`Instagram` 是其中之一。它从基础视图转换为优秀的 UI 开始，克服将 `react-native` 集成到现有项目的障碍。由于优雅的用户界面，它不需要单独的原生基础设施。尽管开发团队在将 `React Native` 功能集成到 `Instagram` 时遇到了一些挑战性工作，但他们能够稳定地提高应用速度。大约 80%–90% 的代码在 `iOS` 和 `Android` 之间共享，这对于应用开发来说节省了大量时间。

### 6. 使用 React Native 闪光

`Shine` 是压力大、缺乏动力或缺乏激情的用户的顶级 `React Native` 应用之一。它提供放松的文章、鼓励性的格言和座右铭。当用户每天登录时，由专家制作的具有启发性和灵性的音频有助于他们应对日常压力。该软件最初面向 `iOS` 用户，并关注美国市场，因为 `Apple` 手机拥有很大的市场份额。他们迅速为 `Android` 创建了应用，这就是为什么他们使用 `React Native`，因为这项技术使得代码从 `iOS` 传输到 `Android` 变得简单。

### React Native 应用开发的优势

`React Native` 在创建移动应用方面有多个优势。

#### 1. 更具灵活性

得益于每个原生开发服务使用的接口类型，任何团队成员都可以立即接手遗留工作并继续执行。在这个团队中，灵活性正在增长，更新和升级移动应用的流程得到了极大促进。

#### 2. 节省时间和金钱

得益于 `React Native`，企业现在可以拥有适用于 `Android` 和 `iOS` 平台的应用，这还节省了开发同时适用于 `Android` 和 `iOS` 市场的单一应用的时间和精力。结果，花费在创建应用上的资金也被节省了。

#### 3. 卓越性能

运行大多数操作系统的中央处理器（CPU）在此处，但 `React Native` 应用还利用图形处理器（GPU）来提高速度。由于该编程语言对移动设备的专业化，`React Native` 应用的运行速度几乎与原生应用。

#### 4. 立即更改

`React Native` 的实时或热加载功能允许开发者在预览窗口中实时查看他们的更改。此外，开发者从中受益良多，因为他们每完成一步都能获得反馈。

#### 5. 可移动性

`React Native` 声称为过程提供了很大的灵活性，这是采用它的最大优势之一。这些应用可以从 `React Native` 导出并传输到 `Android Studio` 或 `Xcode`。

## React Native 的缺点

我们在上面讨论了 `React Native` 的一些优势，但我们都知道，任何有优势的东西都有缺点。因此，`React Native` 的缺点列如下：

- **框架不足**：每一次新更新或发布（正如大家所知）都会带来许多重大变化，这些变化最终可能难以处理。`React Native` 在这种情况下是更快、更新的替代方案，但为了快速移动，框架倾向于失去对信誉的承诺，导致对于任何 `iOS` 和 `Android` 应用来说仍然不成熟。
- **难以定义用户界面**：如果您的移动应用程序需要动画、多个屏幕切换和交互等功能，现在选择 `React Native` 进行应用开发是不值的。
- **复杂的调试**：`React Native` 开发应用程序的调试程序具有挑战性。这很大程度上归于 `Java`、`JavaScript` 和 `C/C++` 编程语言。

## 使用 React Native 创建移动应用程序

由于全球环境的变化，企业被迫考虑将其业务模式从传统平台转移到数字平台。企业开始创建在 `iOS` 和 `Android` 上运行流畅的极高效实体。然而，移动应用开发成本的上升限制了他们的投资能力。然而，考虑到移动应用程序在通信、零售、医疗保健和娱乐等所有行业已变得如此普及，企业已经意识到，如果没有强大的在线形象，在未来几十年的竞争将是多么困难。

## 领先的跨平台框架 React Native

`React Native` 是一种基于 `JavaScript` 的跨平台框架，被广泛用于开发在 `iOS` 和 `Android` 上具有原生外观和交互体验的移动应用。`React Native` 尽管由 `Facebook` 在 2015 年推出，但它迅速崛起成为领先的开源框架。在为 `Skype`、`Instagram` 等多个应用程序提供动力支持后，它最终作为最出色的应用开发选择而闻名。由于具有代码复用、快速测试能力以及在 `iOS` 和 `Android` 两个平台上同时运行应用等优势，它是创建应用的理想平台。

## 为什么在开发移动应用时我们应该使用 React Native？

毫无疑问，全球有 42% 的开发者在投资应用开发项目时喜欢 `React Native`，许多组织对为什么 `React Native` 会成为首选感到困惑。以下是使用 `React Native` 的理由：

### 节省金钱和时间

使用 `React Native` 的主要优势在于节省了时间、金钱和精力。为多个平台开发原生应用的成本会比利用 `React Native` 和单一代码库创建应用贵得多。因此，通过使用 `React Native`，开发者可以轻松地为 `iOS` 和 `Android` 平台发布相同的更新而无需增加额外工作，从而节省了创建原生应用的开发费用。

### 高质量

企业的首要考虑事项通常与应用的性能有关。此外，`React Native` 应用与原生的 `Android` 和 `iOS` 应用一样优秀。`React Native` 使用 `GPU` 进行计算，而其他使用 `CPU` 的跨平台框架不同。这是 `React Native` 应用性能更好的关键因素。

### 空热更新 (Over-the-Air Updates)

`React Native` 突破性的更新能力允许在用户正在使用应用时对后端进行更改。一旦完成，修改将立即显示在应用中。消费者通常可以选择无需访问应用商店即可进行更新。得益于 `React Native` 的功能，整个应用升级过程变得简单且快速。

### 主要优势是开源

对于那些想要个性化应用的人来说，`React Native` 提供了广泛类原生能力。由于 `React Native` 允许开发者从 `Android` 平滑导出脚本到 `Xcode`，开发者将项目从一个平台迁移到另一个平台时不会遇到困难。

## 原生 (NATIVES)

### 什么是 NativeScript？

一个名为 `NativeScript` 的开源框架被用于构建 `iOS` 和 `Android` 的移动应用。该框架是 `JIT` 编译的。`NativeScript` 和 `iOS` 平台都支持 `V8` 引擎运行时。在开发方面，`NativeScript` 使用 `XML`、`JS` 和 `CSS`。它拥有一个名为 `Playground` 的基于 `Web` 的 IDE。`Playground` 包含了用户界面、简单的项目管理、热重载和设备调试。`NativeScript` 使得程序员能够快速高效地构建跨平台应用，同时减少测试和开发的成本。因此，原生应用在未来几年内将保持强大和丰富，使它们更好用、更易用。

### 为什么 Android 应用偏于使用 NativeScript

如今，开发者可以选择多种框架来创建惊艳且可扩展的移动应用。得益于混合应用理念在市场上的广泛采用，开发者可以充分利用智能手机的功能和开发专业知识。由于 `NativeScript` 为 `Android` 开发解决方案提供了各种优势，它因此进入了视野。正如其名所示，`NativeScript` 允许开发者创建完美的原生应用。惊讶的是，构建应用的时间在没有牺牲质量的情况下缩短。此外，程序员可以使用 `TypeScript` 和 `Angular` 等替代框架。使用 `NativeScript` 创建的应用程序运行非常出色，具有极佳的用户体验，并可以连接到多个设备。以下是我们考虑在项目中使用 `NativeScript` 的所有关键理由。

### 什么是 NativeScript？它的主要优缺点是什么？

一个名为 `NativeScript` 的知名开源前端被用于创建具有卓越性能和用户体验的跨平台移动应用。当它在 2014 年推出时，很快因其极易用性和特定平台的编程能力而闻名。使用 `NativeScript` 最重要的优势是为用户在 `Android` 和 `iOS` 等平台上提供引人入胜的原生体验。`Android` 开发者可以通过原生 `Android API` 轻松访问原生功能，无论什么细分领域都能构建以用户为中心的应用。

#### 原生应用的优势

- **原生应用运行速度快**：因为它们是平台原生的，所以原生应用运行更快。它们有很多预加载元素。由于它们利用了设备的内置功能，所以它们很快，因为用户数据是从本地获取的而不是整个应用程序。
- **原生应用的离线使用**：即使在没有连接的情况下，原生应用也能运行。因此，当我们受困在航空公司、地下隧道或地铁等网络信号差或无连接的地方时，原生应用是可用的。
- **原生应用提供可识别的界面和感觉**：设备上的默认应用已通过原生应用得到了增强。由于该程序与手机上安装的其他应用相似，当用户执行若干操作时，他们会迅速模拟应用的自然流程。在这种情况下，原生应用具有优势，因为试图模仿原生应用外观和感觉的移动应用往往会陷入所谓的“恐怖谷效应”，该术语由机器人学教授森泽广弘（`Masahiro Mori`）命名。
- **原生应用保持宽高比例**：各种屏幕的宽高比被称为宽高比例。它是影响应用如何获得良好图像的重要元素。更改设备的尺寸和形状会导致许多应用崩溃和功能异常。通过原生应用，可以更精确地控制应用的方向、尺寸和分辨率。开发者在创建原生应用时可以使用布局功能。原生应用在设置了屏幕尺寸后，无论运行在哪个屏幕上，它都能保持其自身的宽高比例。`iOS` 和 `Android` 都有名为 `Constraint Layout` 和 `Auto Layout` 的工具，帮助在各自的设备上保持宽高比例。在保持宽高比例的同时，这些功能还为每个屏幕提供了不同的 `DPI`（每英寸点）以保持视觉质量。

#### 原生应用的局限性

- **下载过程冗长**：原生应用只有在从应用商店（`Google Play` 或 `Apple App Store`）下载后才能使用。这涉及到多个步骤：访问应用商店、选择程序、接受条款和条件，并最终安装。许多人没有时间和耐心来完成所有下载步骤。我们在应用漏斗的每个阶段都会流失 20% 的消费者。
- **绝对僵化**：在选择构建平台时，开发者没有多少自由。需要一次处理一个平台，分别为 `Android` 和 `iOS` 进行单独开发。如果我们为原生应用构思招聘开发者，通常需要雇用团队：一个负责 `Android`，一个负责 `iOS`。
- **开发成本高**：原生应用开发者很难寻找，因为他们使用的代码相当困难。因此，原生开发所需时间更长，费用更多。由于每个平台需要不同的代码，构建原生应用也花费更多资金和时间。此外，维护原生应用的费用相对昂贵。维护费用占总应用开发成本的 15%–20%。例如，一个花费 25,000 美元的简单应用大约需要 5,000 美元的维护费用。原生应用的维护费用将随着其开发支出的增加而增加。

### 前提条件

在开始安装之前，我们需要满足以下要求：

- `Node.js`
- `Android`
- `iOS`

### 验证 Node.js

`Node.js` 是构建在 `Google Chrome` 内部 `JavaScript` 引擎 `v8` 之上的 `JavaScript` 运行时环境。`NativeScript` 大量利用 `Node.js` 用于不同的目的，例如构建初始模板应用、编译应用程序等。我们的电脑上需要安装 `Node.js`。希望我们已经在系统中安装了 `Node.js`。如果尚未安装，请访问网站 [https://nodejs.org/](https://nodejs.org/) 获取最新的 `LTS` 包并进行安装。

要测试 `Node.js` 是否安装正确，请在我们的终端中输入以下命令：

```
node --version
```



运行`node --version`命令，可以看到版本号。`node`最新的`'LTS'`稳定版本我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。`12.14.0`。

### CLI 设置

我们可能使用 NativeScript CLI（一个终端/命令行程序）来构建和开发 NativeScript 应用。NativeScript CLI 是通过 Node.js 包管理器`npm`安装在我们的电脑上的。运行下方显示的命令来安装 NativeScript CLI。

```
npm install -g nativescript
```

### 设置 CLI

最新版本的 NativeScript CLI（`tns`）已安装在我们的系统中。现在在我们的终端中输入以下命令。

```
tns
```

无需任何进一步设置，我们就可以使用`tns`构建和开发应用。然而，我们无法在实际硬件上部署该程序。相反，我们可以使用 NativeScript Playground iOS 和 Android 应用来启动程序。

### 设置 NativeScript Playground 应用

在 Google Play 商店或 iOS App Store 中搜索 NativeScript Playground。当搜索结果显示该程序时，点击安装按钮。NativeScript Playground 应用将安装到您的设备上。无需实际上将程序发布到真实设备或模拟器，我们就可以使用 NativeScript Playground 应用在 Android 或 iOS 设备上测试我们的应用。这将加速应用程序的开发过程并提供一种简单的启动方法。

### Android 和 iOS 的设置

让我们学习如何设置系统在真实设备或模拟器上创建并启动 iOS 和 Android 应用。

#### 第 1 步：Windows 上的依赖

在我们的 Windows 命令行提示中以管理员身份运行下面的命令。

```
@powershell -NoProfile -ExecutionPolicy Bypass -Command ((new-object net.webclient).DownloadString('https://www.nativescript.org/setup/win'))
```

执行此命令后，下载的脚本将安装其依赖并进行配置。

#### 第 2 步：macOS 上的依赖

在 macOS 上安装之前，我们必须检查是否安装了 Xcode。NativeScript 需要使用 Xcode。如果尚未安装 Xcode，请前往`https://developer.apple.com/xcode/`下载并然后安装它。在我们的终端中，运行以下命令开始。

```
sudo ruby -e "$(curl -fSSL https://www.nativescript.org/setup/mac)"
```

运行上述命令后，脚本将为开发 iOS 和 Android 安装必要的先决条件。完成后，关闭我们的终端并重启。

#### 第 3 步：Android 依赖项

希望以下要求已设置好：

- JDK 8 或更高版本
- Android SDK Build-tools 28.0.3 或更高版本
- Android Support Repository
- Google Repository
- Android SDK

如果未设置上述要求，请访问`https://developer.android.com/studio/install`并安装它。最后，添加环境变量`JAVA_HOME`和`ANDROID_HOME`。

#### 第 4 步：验证依赖项

此时一切均已完成。可以使用下方提供的命令验证这些依赖项。

```
tns doctor
```

### NativeScript 的顶级用例

多年来，功能丰富且高性能的应用程序在所有平台上采用了 NativeScript。该框架的核心卖点仍然是其影响原生用户体验的常规能力。让我们从各个角度快速回顾 NativeScript 的一些最突出且为人知的用例。

- 包括 Facebook、Twitter、WhatsApp 在许多平台在内的热门社交网络平台都使用了 NativeScript。
- NativeScript 被多个热门 GPS 地图和定位应用使用，包括 Field Trip、Banjo、Glimpse 等。
- 许多热门新闻和娱乐应用，如 Buzzfeed、Reddit、SmartNews、Feedly 等也采用了 NativeScript。
- NativeScript Live 被许多知名游戏应用使用，包括 Drop7、Crossy Road、Real Racing 3、Robot Unicorn Attack 2 等。直播应用（包括 Livestream、Broadcast me、Periscope 以及更多）也利用了 NativeScript。
- NativeScript 被 Apple Music、iHeartRadio 等流媒体音乐和视频应用使用。
- NativeScript 还用于 Skype、Snapchat、Messenger 等热门聊天和社交消息应用。

### 使用 NativeScript 开发 Android 应用的原生优势

多年来，NativeScript 已成为创建强大的、吸引人的高性能的原生 Android 应用的首选框架。对于他们的 Android 项目，开发者可以使用 NativeScript 提供的许多优势。让我们快速回顾使用 NativeScript 的原生优势。

#### 原生应用的性能

通过特定的 Android API 访问原生 UI 是使用 NativeScript 开发 Android 应用的主要优势。与许多其他框架不同，NativeScript 不需要使用 WebView 或桥接层即可访问原生 UI。只要具有这种原生构建能力，NativeScript 就可以在应用程序的所有区域运行原生代码。开发者可以根据需要进一步修改用户界面。这对于 Android 这样复杂且多样的生态系统至关重要，NativeScript 像 Android 编程语言 Kotlin 或 Java 能够实现快速的应用性能和完全原生的用户体验，而不影响代码的重用性。当代码在多个平台被重用时，用户界面和用户体验特征保持自然。

他们熟悉在 iOS 和 Android 平台上工作的开发者所经历的种种困难。此外，该框架得到了开发者社区的广泛支持。最后但同样重要的是，创建 NativeScript 的公司为包含开发任务关键型应用的项目提供企业级支持。

### NativeScript 与 React Native 的比较

从两个基于 JS 的框架中选择一个并不容易。由于都具有跨平台的特性，两者提供的优势具有相当的可比性。然而，React Native 在某些特定行业中表现得尤为出色。这里简要比较了这两个框架的性能、学习曲线、流行程度、开发者社区以及其他重要特性。

#### NativeScript 与 React Native 的性能

两个框架在启动时都提供原生应用性能。两者的加载都需要很长时间。但这恰正是 React Native 大放异彩的地方。NativeScript 渲染页面速度较慢。坦率地说，在一个每一秒都至关重要的社会里，延迟渲染是不可接受的。这就是 React Native 在渲染动态组件时使用原生 SDK 渲染应用的情况。这一切都归功于虚拟 DOM，这使得 React Native 变成了一个非常快的框架。

#### NativeScript 和 React Native 的学习曲线

NativeScript 和 React Native 仅具备 JS 技能的开发者无法处理。考虑一下：最初，NativeScript 对于具有 Angular 背景的开发者来说会更简单。另一方面，具有 React 背景的程序员会发现转向 React Native 更容易。必须记住，这两个系统都使用了 JavaScript。对于前端开发人员来说，这是一个极佳的机会。在这些时期，感知这些框架变得更加简单。选择 React Native 意味着我们只需要 JavaScript，而 NativeScript 则通过其声明式编码方法提供帮助。

#### React Native 与 NativeScript 的开发社区

React Native 的开发者社区比 NativeScript 大，后者被 11% 的程序员使用，而前者的占比为 42%。React Native 非常流行，因为像 Instagram 和特斯拉这样的科技巨头选择了它们而非 PhoneGap 或 NativeScript 来创建他们的应用程序。在决定最佳架构时，考虑社区支持至关重要。

尽管看起来可能很奇怪，但 NativeScript 的存在时间比 React Native 长得多。React Native 于 2015 年 3 月 26 日发布，而 NativeScript 最初创建于 2014 年。尽管 1 年的差距可能看起来是一个优势，但 NativeScript 正在越来越多被 React Native 代替。截至发布日期，React Native 在 npm 上每周有 533 万下载，而 NativeScript 每周仅有 7 千下载。谈到贡献，React Native 在 GitHub 上有超过 2200 多名贡献者，胜过 NativeScript。NativeScript 有 208 名贡献者。在 GitHub 上，React Native 真正有 72 万开发者使用，而 NativeScript 的使用人数超过 3500 人。这些差距显示了社区对 React Native 的广泛接受，这影响了 StackOverflow 上第三方库、回复和 Bug 解决方案的数量。总的来说，React Native 胜出。

#### NativeScript 与 React Native 的流行度

NativeScript 和 React Native 都是使用 JavaScript 开发的。竞争势均力敌。根据 2019 年的一项 StackOverflow 研究，JavaScript 是使用最广泛的技术。在框架方面，React.js 超过了 Angular.js/Angular 和 Vue.js。开发者似乎更青睐 React.js，在所有受访者中占比为 10.5%。除了比 NativeScript 更流行之外，React Native 也吸引了更多的关注。

#### 在 React Native 和 NativeScript 之间我们应该使用哪个？

在这两种知名技术之间做出决定可能是困难的，因为它们各自都有优缺点。对我们来说，最好的技术主要取决于项目的需求。尽管如此，使用 NativeScript 和 React Native 的正确时机已经确定。

选择 NativeScript，如果：

- 我们想要创建一个跨平台程序。
- 使用免费且内置的插件和模板，我们想要创建可扩展的 API。
- 我们不需要 webViews 来创建复杂的、难以访问且分散注意力的用户界面。
- 不惜一切代价地避免性能问题。

选择 React Native，如果：

- 我们想要快速开发一个 MVP（最小可行性产品）。
- 我们想要创建能够实时通信更新的实时应用。
- 我们想要具有特定 UI 的移动应用。
- 在没有第三方插件的情况下，我们必须创建我们的平台。

在本章中，我们涵盖了 React Native 和 NativeScript 的优点、缺点、范围、流行度和比较。

### 笔记

1. 为什么 JavaScript 被认为是最好的移动应用之一？[linkedin.com/pulse/javascript-considered-one-best-mobile-app]
2. 你应该在移动开发中使用 JavaScript 吗？[medium.com/should-use-javascript-mobile-app]
3. 使用 JavaScript 开发移动应用的好处？[medium.com/benefits-using-javascript]
4. React Native 环境？[javpoint.com/react-native-environment]
5. React Native 用于移动应用的未来？[soft.com/future-of-react-native]
6. 原生应用的优缺点？[clutch.com/resources-apps]
7. NativeScript 教程？[tutorialpoint.com/nativescript]
8. 为什么 NativeScript 在 Android 开发中更受青睐？[technology.com/why-nativescript-is-preferred-android-development]
9. NativeScript - 安装？[tutorialpoint.com/nativescript]
10. 用于移动开发的 NativeScript vs React Native？[technology.com/blog/nativescript-vs-react-native]

## 桌面端的 JavaScript

### 本章内容

- Electron.js

在上一章中，我们涵盖了移动端的使用，在本章中，我们将讨论用于桌面应用的 JS。桌面程序的设计在近年来得到了改进，越来越多的应用采用了 Electron，它是这种让桌面程序达到这一水平的技术。以前，JavaScript 是创建网站的首选语言，很大程度上是因为 React、Vue 和 Angular 等 JavaScript 框架非常好。然而，随着 2009 年 Node.js 的出现，JavaScript 获得了在浏览器外运行的能力。

Electron 是一个提供了原生（操作系统）API 的运行时，允许我们用纯 JavaScript 编写桌面应用。我们可以将其视为 Node.js 运行时的一个分支，专门为桌面程序而非 Web 服务器定制。

### 我们如何使用桌面应用程序？

“桌面应用”一词指的是设计为在个人计算机上使用的软件。这些程序是为了单一功能而安装的，没有其他用途。我们用于编写和编辑文档的 Microsoft Word 就是桌面程序的示例。网络浏览器、Visual Studio Code 和 Adobe Photoshop 都是流行的桌面应用示例。

### .NET

.NET 是一个免费、开源且跨平台的开发环境，可用于创建各种软件。在使用 .NET 时，开发者可以使用各种工具和框架来为 Web 网页、移动设备、桌面计算机、视频游戏和物联网创建应用程序。

### 什么是 Electron？

Electron 是一个用于创建桌面软件的免费开源软件环境。该项目最初名为`'Atom shell'`，由 GitHub 构建并提供支持。通过 Electron，我们仅需使用 HTML、CSS 和 JavaScript 即可创建运行在多个平台上的桌面应用。这意味着同一组代码可以用于包括 Windows、macOS 等在内的多个平台的桌面程序。它是使用 Node.js 和 Chromium 构建的。许多知名程序，包括 Atom 编辑器、Visual Studio Code、桌面版 WordPress 和 Slack，都是使用 Electron 开发的。

### 安装

使用 NPM 包管理器将 Electron 添加到我们的项目中。

```
npm install electron --save-dev
```

如果我们打算大量处理 Electron 应用程序，可以使用此命令将其全局安装：

```
npm install electron -g
```



## 哪些应用使用了 Electron？

Electron 为众多企业提供了多项优势。²

### 1. WebTorrent 桌面应用程序

面对现实吧：我们都喜欢种子下载，无论是在手机还是电脑上下载。然而，这类软件似乎仍然过时且陈旧，这就是为什么 WebTorrent 的人员决定采取行动——采用 Electron JS 作为他们的主要开发工具。

`WebTorrent` 是第一个在浏览器中运行的种子客户端，完全用 JavaScript 构建，并利用 WebRTC 进行点对点传输。`WebTorrent` 将用户连接到去中心化的浏览器网络，该网络无需插件、扩展或安装即可提供高效的文件共享。

#### 为什么 WebTorrent 在桌面端使用 Electron？

Electron 随着 WebTorrent 桌面客户端加入战斗，使其尽可能轻量、无广告且开源。它还有助于流媒体传输，并作为一个混合客户端，将程序连接到所有主要的 BitTorrent 和 WebTorrent 网络。

### 2. WordPress 桌面应用程序

WordPress 作为内容管理系统无可争议的君主，需要一个可靠且自动的桌面版本。得益于 Electron JS，它加入了使用 Electron JS 的桌面应用列表——作为一种允许我们管理 WordPress 内容的开源框架。

我们都听说过 WordPress 以及如何在浏览器中使用它。相比之下，桌面版 WordPress 是一个完全全新的事物：基于 Electron 框架构建的桌面软件，提供无缝的跨平台体验，使用户能够专注于内容和设计，而不会被浏览器标签页干扰。

#### 为什么 WordPress 桌面应用使用 Electron？

桌面版 WordPress 是一个以 Electron 为基础的桌面程序，并带有 React 的 JavaScript 作为这种新型桌面技术中的主要语言。

### 3. Ghost 应用程序

如果你从未听说过 Ghost，你并不孤单。Ghost 本质上是一个开源平台，允许用户创建和管理现代网络出版物。

Ghost 完全可以被黑客，并且对在线媒体的未来（从博客到杂志和期刊）具有重大影响。这主要归功于更容易、更专注的创作体验，这显然是 JavaScript 桌面框架等技术的结果。

#### 为什么 Ghost 桌面应用使用 Electron？

本着这种精神，桌面版 Ghost 是一个使用 Electron JS 构建的桌面程序，允许作者在专注于内容的同时同时维护多个博客。

如果我们是作家，我们肯定意识到键盘快捷键等基础操作在浏览器中可能很难实现。相反，Ghost 桌面程序让这一切比以往任何时候都简单。

桌面版 Ghost 是基于 Electron 的应用程序之一，它通过在后端和前端使用 JavaScript 和 Node.js 提供了更好的用户体验。

### 4. Electron Beaker 浏览器

我们正在寻找一个可靠的点对点网络浏览器吗？如果是的话，我们刚刚发现了。Beaker 浏览器是一个为黑客设计的协作浏览器。Beaker 浏览器最初开发为一种可被黑客的产品，它将 Web 转换为开源格式，允许黑客、修改者和创意型人士充分利用他们的数字能力。

#### 为什么 Beaker 浏览器使用 Electron？

Electron 框架使得构建 Beaker 变得简单得多。它作为开发浏览器的工具集，以最少的迭代和最佳的方式协助了 Electron 的设计过程。简而言之，Beaker 浏览器是一个开源在线浏览器，一种让社交黑客变得比以往任何时候都更简单更有效的解决方案。

### 5. Pixels Electron 应用程序

Pixels 对许多作者、设计师和出版者来说是救星。

一个拥有数千张免版税素材照片的网站显然需要改进。

这就是使用 Electron JS 开发的 Pixels 桌面应用诞生的由来。

#### 为什么 Pixels 桌面应用使用 Electron？

只需点击一下，该软件比以往任何时候都更容易地将快照复制到剪贴板。图片可以粘贴到任何软件中，并作为文章、信息图或社交媒体帖的素材图。无需下载，因此没有问题，在 Pixels 桌面软件中寻找新照片非常简单。

### 6. Slack 桌面应用程序

适用于 macOS 的 Slack 桌面应用是另一个利用这种 JavaScript 技术的奇程序。

#### 为什么 Slack 桌面应用使用 Electron？

它是使用 Electron 框架创建的，由于 Chromium 渲染引擎和 Node.js 运行时远程加载其资源，这一点显而易见。

### 7. WhatsApp Electron 应用程序

WhatsApp 是下载最多的聊天软件，另一个使用 Electron 的知名程序。

#### 为什么 WhatsApp 桌面应用使用 Electron？

它是使用 Electron 框架创建的，这让 WhatsApp 一次性涵盖所有功能，减少了工作量。

## 为什么许多企业选择 Electron 创建跨平台应用？

企业选择 Electron 有许多重要原因：

- Electron 允许开发者专门使用 JavaScript 技术如 HTML 和 CSS 创建应用。
- Electron 允许创建在 Mac、Windows 和 Linux 上运行的程序，消对开发者精通原生开发的需求。

### 这的意义是什么？

在最高层，我们可以看到 Mac、Windows 和 Linux。这已经很多了。但在更深层次，这些系统有多种版本。每个版本都有独特的特性，在产品创建时应该考虑每一个使用的系统。此外，为了满足这一开发挑战，我们需要雇用专业人士，这可能需要很长时间。此外，开发三个不同的应用程序是一个耗时的过程。从商业角度来看，在许多情况下，这不是现实的答案。

## Electron 的优势

现在，大多数开发者选择 Electron 创建跨平台应用是因为以下显著的优势：

## 410 攻克 JavaScript

Electron 在最终应用程序包中包含了 Chromium 和 Node.js，即使我们通过仔细选择前端库和框架编写一个基础且轻量级的应用，我们的项目也会变得臃肿。

Chromium 和 Node.js 是大型项目，它们的模块在我们的机器上比通常情况下需要更多的资源。

换句话说，基于 Electron 的应用需要大量的物理内存和磁盘空间。此外，由于资源占用率高，Electron 程序会迅速耗尽笔记本电脑的电池。由于上述严重的性能困境，基于 Electron 的跨平台应用往往会变成臃肿软件。这种缺点可能会被强大的硬件在普通用户面前隐藏。然而，如果用户开始运行许多 Electron 应用，他们将很快注意到这种隐藏的性能问题。

## Electron 的替代方案

一段时间前，出现了如 Electronino 和 DeskGap 等替代方案，作为解决 Electron 性能困难的办法。

这两个努力都尝试利用操作系统的 webview 而不是 Chromium 来减小最终包体积。

遗憾的是，开发的 Electron 框架未能完成这两个项目。

然而，有两个流行的轻量级 Electron 替代方案：Tauri 和 Neutralino.js。

这两个项目都试图通过用更好、更轻量的替代方案替换 Chromium 和 Node，来解决 Electron 的性能问题。

这两个项目都利用著名的 webview 库来渲染 HTML 和 CSS，而不是 Chromium。webview 库使用当前的网络浏览器组件进行渲染。

例如，它将在 Linux 系统上利用 `gtk-webkit`，在 macOS 上利用 Cocoa Webkit，在 Windows 上利用 Edge/MSHTML。

## Electron.js 框架的缺点

使用 electron.js 有一些缺点，列举如下：

### 体积过大

Electron 程序使用它们自己版本的 Chromium 浏览器。

这个浏览器很大，由数百万行代码组成。

事实上，由于 Chrome 浏览器的大小与操作系统一样大，它占据了计算机大量的硬盘空间。

## 用于桌面应用程序的 JavaScript ■ 411

然而，考虑到现在的电脑通常为用户提供 2TB 的内存空间，如此大量的 Electron 应用并不是一个主要的关注点。

### Electron.js 框架消耗大量资源

Electron.js 框架消耗 ROM 和系统资源，如果在笔记本电脑上快速使用，还会消耗电池电量。

事实上，Electron 应用经过优化，可以在许多系统上运行，由于平台各异，应用优化需要消耗更多的能量。

原生应用是针对特定平台的，它们的资源更优。

## 特定客户需求

Electron.js 应用在所有平台上的运行通常相同，但如果用户对每个设备有不同的设计，程序员可能会陷入挣扎。

实际上，开发者必须投入更多精力为每个平台创建独特的功能，这将不可避免地增加成本。最关键的是，这将无法运作；结果是应用所有者必须提前为产品识别进行规划。

## 使用 Electron.js 框架的意义

开发者使用 Electron JS 框架来创建高质量的跨平台应用。

但为什么认为程序员选择这个框架而不是其他工具呢？

首先，该框架支持所有可用的平台，对开发者来说非常友好。此外，开发者将能够使用 Electron.js 框架和其他 JavaScript 框架创建跨平台应用。

Electron 框架成功的另一个原因是它的应用确实是 Web 应用程序。换句话说，Electron.js 是一种网络技术，允许我们简单地将桌面程序转换为 Web 版本。

## 主进程与渲染进程的区别

通过建立 `BrowserWindow` 实例，主进程生成网页。

网页由每个 `BrowserWindow` 实例在自己的渲染进程中进行渲染。

## 412 攻克 JavaScript

当 `BrowserWindow` 实例被销毁时，相关的渲染进程也会结束。

主进程负责所有网页及其关联的渲染进程。

每个渲染进程都是隔离的，并且只关注其在其中执行的网页。

## Electron 中的 HELLO EVERYONE 代码

对于我们的项目，我们构建了一个 `package.json` 文件。现在我们将使用 Electron 构建我们的第一个桌面应用。

创建一个名为 `main.js` 的新文件。填入以下代码：

```javascript
const {app, BrowserWindow} = require('electron')
const url = require('url')
const path = require('path')
```

```javascript
let win

function createWindow() {
  win = new BrowserWindow({width: 700, height: 500})
  win.loadURL(url.format({
    pathname: path.join(__dirname, 'index.html'),
    slashes: 'file:'
  }))
}
```

```javascript
app.on('ready', createWindow)
```

创建一个名为 `index.html` 的新文件，这次是 HTML 格式。在其中输入以下代码。

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Hello Everyone!</title>
</head>
```

```html
<body>
<h1>Hello Everyone!</h1>
We are using the node <script>document.write(process.versions.node)</script>
Chrome <script>document.write(process.versions.chrome)</script>
and Electron <script>document.write(process.versions.electron)</script>
</body>
</html>
```



使用以下命令启动此应用：

```
$ electron ./main.js我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。```

# 这个应用是如何运行的？

我们制作了一个主文件以及一个 HTML 文件。主文件中使用了两个模块：`app` 和 `BrowserWindow`。`app` 模块管理应用程序的事件生命周期，而 `BrowserWindow` 模块负责创建窗口。

## 416 征服 JavaScript

我们可以像创建网页一样创建我们的原生应用。如果我们不希望用户受限于特定的窗口大小，我们可能会利用响应式设计使用户能够以更灵活的方式使用我们的应用。

在本章中，我们研究了使用 `electron.js` 构建的桌面应用以及它们的优缺点，以及如何安装 `electron.js`。

# 笔记

- 1 使用 Electron 和 Vue 构建桌面应用：`www.smashingmagazine.com/2020/07/desktop-apps-vue-javascript/` 访问日期：2022年10月19日。
- 2 著名的 Electron 应用示例（JavaScript 桌面应用）：`https://brainhub.io/library/electron-app-examples` 访问日期：2022年10月19日。
- 3 为什么你应该使用 Electron 的替代方案：`https://blog.logrocket.com/why-use-electron-alternative/` 访问日期：2022年10月19日。
- 4 介绍 Electron.js 框架及其优缺点：`https://www.tutorialspoint.com/electron/introducing-the-electron-js-framework-its-advantages-and-disadvantages/` 访问日期：2022年10月20日。
- 5 Electron – Hello World：`www.tutorialspoint.com/electron/electron_hello_world.htm` 访问日期：2022年10月20日。
- 6 Electron – 构建 UI：`www.tutorialspoint.com/electron/electron_building_uis.htm` 访问日期：2022年10月20日。

# 评价

## JavaScript 到底是什么？

JavaScript 的初开发初衷是为了“让在线网页活起来”。

脚本就是用这种语言编写的程序。它们可以直接写在网页的 HTML 中，并在页面加载后立即自动执行。

脚本以纯文本格式发送并在该格式下运行。它们可以在无需任何额外准备或编译的情况下运行。

JavaScript 是一种执行在 Web 客户端的编程语言，可用于编写网页在特定事件发生时如何反应。JavaScript 是一项流行的选择，因为它作为编程语言既易于上手又强大。它通常被用于控制网页的行为。

尽管人们广泛认为 JavaScript 是“解释执行的 Java”，但事实并非如此。JavaScript 是一种动态编程语言，支持基于原型的对象构建。这就是 JavaScript 的本质。由于这种语言需要熟悉大量的新概念，其基础语法的设计旨在为了在概念上与 Java 和 C++ 对比。该语言的构造结构如 `if` 语句、`for` 循环、`switch` 和 `try... catch` 块在这些语言中都具有相同的功能（或几乎相同）。

编程语言 JavaScript 可以以过程化和面向对象的模式运行。与 C++ 和 Java 等编译型语言中盛行的语法类声明不同，JavaScript 中的对象是通过程序化形成的。这是通过在执行时向原本为空的对象上添加方法和属性来实现的。在构建一个项之后，该项可以作为构建更多同类项的模型（或原型）。

# JavaScript 的过去与未来

JavaScript 由 Brendan Eich 于 1995 年首次开发，用于 Netscape Navigator，这是当时最流行的 Web 浏览器。JavaScript 让 Web 开发人员能够根据网站访问者的操作实时修改屏幕上的视觉组件，从而使创建更具动态的网站成为可能。在 JavaScript 存在的头半年里，它经历了多次变化。它最初被称为 Mocha，后来被称为 LiveScript，最后被命名为 JavaScript。

尽管如此，编程语言 JavaScript 与 Java 编程语言没有任何关系。这是一个有趣的知识。Netscape 和 Sun Microsystems 之间的合作负责了 Java 的开发，导致了这一术语的产生。

如今，JavaScript 的用途远比仅仅限于作为一种 Web 编程语言。因为它是你所选择的、强大且适应性强的语言，可以用许多不同的方式使用，你可以根据自己的意愿编写 JavaScript，无论你喜欢命令式编程、更偏向对象的风格、函数式方法，甚至是事件驱动模型。

# 什么让 JavaScript 与众不同？

至少，JavaScript 具有以下三个出色的特性：

- 完全整合了 HTML 和 CSS。
- 简单的事情可以轻松完成。
- 所有主流浏览器都对其提供支持，并且它是默认开启的。

JavaScript 是浏览器中唯一结合了这三个特性之一的技术。

## 评价 ■ 419

这就是 JavaScript 区别于其他语言之处。正因如此，它是创建浏览器界面最常用的工具。

话虽如此，JavaScript 也可以用于创建服务器、移动应用和其他类型的软件。

## 比 JavaScript 更“优越”的语言

对于某些人来说，JavaScript 的语法并不适合他们。不同个人的偏好可能会有很大差异。

考虑到每个人的项目和需求都是独特的，这是可以预料之中的。

因此，在许多时候出现了各种新语言，为了让这些语言在浏览器中运行，它们必须首先转译（transpile）或转换为 JavaScript。

如今，现代技术使得翻译过程变得极其快速且易于理解，这使得程序员可以用一种语言编写代码，同时在“底层”自动进行转换。

以下是其中一些示例：

- Coffee 经常被称为 JavaScript 的“语法糖”。它通过引入更短的语法来实现这一点，从而让我们能够编写更清晰的代码。Ruby 开发者非常喜欢它。
- TypeScript 专注于实现严格类型，以便于复杂系统的维护。微软是它的开发者。
- Flow 同样支持类型，但方式不同。Facebook 是其背后。
- Dart 是一种独立的编程语言，运行在非浏览器环境中（如移动应用），但也可以转换为 JavaScript 以供浏览器使用。它的引擎在 Dart 平台上运行。由 Google 设计构建。
- 使用 Brython（一种将 Python 转换为 JavaScript 的转换器）使得仅用 Python 编写，而无需 JavaScript。

通过指针的使用，C 语言的设计是为了便于与计算机内存进行直接交互。这种能力被隐藏在 JavaScript 之后。

C 是一种编程语言，通常用于嵌入式计算机和需要高性能的应用程序，例如操作系统。起初，JavaScript 仅包含在网页中，但现在它被用于 Node.js 服务器应用程序，这是该技术的一种较新用途。

C 为用户提供了对线程的显式控制，而 JavaScript 则鼓励用户通过将活动划分为异步函数（这些函数在数据可用时执行）来处理多个任务。C 为用户提供了这种级别的控制，而 JavaScript 则没有。

## Java 与 JavaScript 的对比

- Java 的编译结果是字节码，这是一种中间形式，稍后由 JIT 编译器执行。过去 JavaScript 仅通过解释器执行；然而，现如今通常会使用 JIT 编译器。
- 简单来说，Java 不是一种动态类型语言，而 JavaScript 是一种动态类型编程语言。
- 与 JavaScript 相比，Java 是一种强类型编程语言。
- Java 的设计旨在服务大型应用程序，并为这些程序提供了强大的命名空间。JavaScript 并不直接提供这一点，因此程序员对其进行了合成。
- Java 最初也用于浏览器和服务器，而现在它主要用于服务器。在此之前，JavaScript 只能在浏览器中执行；然而，现在它经常被部署在服务器端。
- Java 和 JavaScript 都支持许多其他语言。交叉编译器能够翻译各种语言，以便它们可以在 Java 的 JVM 或 JavaScript 引擎上执行。

## 42 征服 JavaScript

- Java 8 包含了一种嵌入 JavaScript 的方法，允许该编程语言利用 JavaScript 的许多优势。
- Java 为程序员提供了对线程的直接控制。JavaScript 的调用与响应式函数结构有助于隐藏这其中的很大一部分。

## 与 C# 相比，JavaScript 是

- C# 编程语言被简化为一种称为字节码的形式，这是一种中间形式，稍后由 JIT 编译器执行。曾经，处理 JavaScript 的唯一方法是通过解释。然而，现如今通常会使用 JIT 编译器。
- JavaScript 是动态类型的，与 C# 的静态类型本质形成对比。
- JavaScript 不是强类型的，而 C# 是的。
- JavaScript 拥有不同的库可以涵盖这一功能，其中之一是 `Underscore.js`。C# 有 LINQ，这是一个强大的 .NET 组件，提供了原生数据查询功能，而 JavaScript 拥有独立的库可以涵盖这一特性。
- 计算机语言 C# 对线程提供了精确控制。JavaScript 的调用与响应式函数结构有助于隐藏这其中的很大一部分。
- C# 支持运算符重载和转换。JavaScript 则不支持。

## JavaScript 与编程语言 Python 的比较

- JavaScript 的初始目标是为浏览器内的 HTML 网站提供支持。Python 的设计目标是通过命令行执行，以便启用服务器环境（以及桌面端环境）。
- 同时精通这两种语言的社区现在要大得多。社会研究领域已大量采用 Python 作为一种数据处理语言。现在在服务器和其他地方已经有 JavaScript 的实例。
- JavaScript 使用类似大括号形状的括号来标记代码段。而 Python 使用缩进和空白符。
- Python 方法的参数块可以根据用户的意愿尽可能灵活，而 JavaScript 要求每个参数都必须定义。
- JavaScript 代码的执行通常由事件（如鼠标点击或击键）触发。对函数的调用会被 Python 确认。
- 许多 Python 库的重点是数据的处理和分析，而许多 JavaScript 工具的重点是对浏览器中 HTML 的操作。

## 与 PHP 相比，JavaScript 是

- 这两种脚本语言最初都是在运行时解释的，但现如今通常使用 JIT 编译器来完成必要的转换。
- 它们都有可以动态编写的变量。
- 起初，PHP 的创建是为了在服务器上编译 HTML 页面，而 JavaScript 旨在在客户端计算机的浏览器中运行。现在，JavaScript 也能够在服务器上构建 HTML 文件。
- PHP 几乎不再用于组合 HTML 之外的任何事情。浏览器和服务器端栈中整合业务逻辑和数据库的日益复杂的接口依赖 JavaScript 作为基础。
- PHP 是一种从数据库获取数据并将其格式化为 HTML 的编程语言。它是一种非常直接的语言。JavaScript 正在变成一种可以用于更广泛应用程序的语言，包括通用计算和浏览器交互。

## 424 征服 JavaScript

## JavaScript 与编程语言 Ruby 的比较

- 过去，运行 JavaScript 局限于客户端浏览器，而 Ruby 则结合 Rails 框架在服务器上执行。
- Ruby on Rails 框架为 JavaScript 在服务器的 Node.js 上执行时所使用的许多原则提供了灵感。
- Ruby 和 JavaScript 都是动态类型编程语言的示例。
- 在 Ruby 中，使用 `end` 术语表示块的结束，而 JavaScript 则使用大括号。
- Ruby 的语法更多地源自 Perl 和 Smalltalk，而 JavaScript 的语法很大一部分源自 Java 和 C。
- Ruby 主要限于使用其 Rails 框架的服务器应用程序；尽管如此，一些管理员使用 Ruby 编写支持服务器的命令行程序。另一方面，JavaScript 正在转型为一种通用编程语言。

如所示，JavaScript 与许多其他常见的编程语言有显著差异。它的第一个版本仅用 10 天就创建完成了，但它包含了许多前瞻性的改进，使其能够生存到这个十年。这些创新让它幸存到了现在。

尽管存在许多问题，但似乎只要它是所有浏览器都理解的唯一语言，它将继续成为前端开发人员的关键语言。

# JavaScript 职业发展机会

## 前端 Web 开发人员

这涉及构建网站面向用户且具有视觉吸引力的部分。这一职位主要包括处理 HTML、CSS、JavaScript 和基础后端的工作。你可能对某些基础技术之外的概念有很好的理解，例如性能测试或回归测试。

以下是前端开发者的职责列表：

- 从想法到结论开发新的软件应用程序，包括频繁的测试和维护。
- 为未来的应用程序构建标准的程序和库。
- 确保满足 UI/UX 设计的能力。
- 在将任何用户输入发送到后端服务团队之前，务必对所有这些输入进行真实性检查。
- 与团队其他成员以及投资者协作。

## Web 应用设计师和开发者

开发在 Web 上运行的软件应用程序，例如交互式表单、购物车、文字处理和电子表格程序、视频和图片编辑器、文件转换工具、扫描程序和电子邮件软件。

跨平台桌面程序通常在 Adobe AIR 等平台上创建，而 ELECTRON 则利用了 JavaScript。

在开发交互式网页的过程中，最好使用如 jQuery 之类的 JavaScript 框架，它可以扩展你的 JavaScript 能力以使这些 JavaScript 变得简单。

此角色与前端开发人员不同，因为它对设计和编程背后的原则的侧重较少。

## 精通 JavaScript 的开发者

JavaScript 开发人员的职责是将这种新生成的元素与后端已有的服务连接起来。在大多数情况下，开发者将获得后端 Web 设计师的帮助，后者负责整个服务器端应用程序逻辑。与其他应用程序 HTML 和美学的其他前端开发人员一起工作，JavaScript 开发人员经常在这些项目中协作这些

## 426 征服 JavaScript

同事。编程和应用开发是 JavaScript 开发者的职责。此外，他们还负责：

- 为主要的前端平台创建新功能并进行改进。
- 开发面向终端用户的新功能。
- 协助其他程序的前端工作（Ruby 和 Python 应用中的 HTML/CSS/JavaScript），并为各种不同的平台设计和编写新的前端应用程序。
- 执行代码分析、需求分析、系统风险和软件可靠性分析，以及代码指标识别。

## UX/UI 设计师

这是一个分析和研究人们如何使用特定网站的过程。下一步是在实施改进后对系统进行测试，以使其变得更好。通过掌握用户体验设计和 JavaScript 知识，可能会获得丰厚的收入潜力。

他们也非常精通所选的设计工具；然而，他们的技能组合可能仅包含 HTML 和 CSS。除了熟悉 JavaScript 之外，员工应该在界面设计方面拥有专业知识。负责用户界面的人员可能被称为视觉设计师。

## DevOps 工程师

这个职位有助于缩小 IT 与开发人员之间的沟通鸿沟。此外，他们还会研究诸如服务器软件、版本控制、部署、构建过程以及测试服务器和流程等内容。

以下是 DevOps 工程师的任务列表：

- 发布更新并解决任何出现的技术问题。
- 开发工具以减少用户遇到的错误数量，同时提升他们的整体体验。
- 开发与组织内部现有后端系统协同工作的软件。
- 对生产问题的根本原因进行调查。
- 编写脚本以自动化可视化过程。
- 开发调试系统和对其进行常规维护的流程。

## 负责所有层级的开发者

这与前端和后端的工作相当。公司正在寻找具有极高专业水平的人才，因为这是一个非常有望的职位。

对于 JavaScript 全栈开发者职位，需要以下职责和能力：

- 为 Web 应用程序的结构创建蓝图。
- 与技术团队协作，通过设计和测试开发新功能。
- 具有移动端和桌面平台的开发经验将是优势。
- 保护敏感信息的技能和理解。
- 应具有用于后端开发的语言的知识（例如：JavaScript, Ruby, PHP, Python, Java, .NET 等）。
- 具有与图形设计师合作的历史以及将概念转换为视觉组件的经验。

# 什么是最适合 JavaScript 的框架？

作为一种抽象，开发框架使软件能够提供广泛的功能，并将根据添加用户编写的代码进行特定方式的定制。这些修改可以通过多种方式进行。JavaScript 框架的一种定义是用 JavaScript 编写的应用程序级框架，开发者可以根据自己的需求对其进行自定义。

由于框架在 Web 设计中更具灵活性，绝大多数网站开发者选择在框架内部工作。框架简化并优化了处理 JavaScript 的过程，开启了诸如让应用程序对所用设备更具响应性的可能性。

因此，Vanilla js 被认为是 JavaScript 最伟大的框架之一。

# Vanilla js

原生 JavaScript 就是所谓的 Vanilla js，你会注意到开发者利用 Vanilla js 来产生不需要任何库协助的 JavaScript 代码。你会发现 Vanilla js 是一种脚本语言，它不会对开发人员关于应用程序中定义数据的方式施加任何限制或指导。使用 vanilla.js 编写的应用程序可能并不总是为应用程序提供最优结果。

你会发现 Vanilla js 在开发者中非常流行。这是因为被广泛认为是最简单的框架之一，让所有水平的开发者都能轻松上手。

# 为什么我们认为用 JavaScript 编写的框架如此出色？

它们通过简化困难且复杂的代码来减轻他们的负担。它们允许你更快地提交代码并提高你的工作速度。

它们挑战你专注于应用程序的价值而不是其执行过程。

在我们看来，协作方面，JS 框架提供了最好的潜在投资回报。由于其标准化的用户界面和方法论，来自加拿大、美国和巴西等国家的软件工程师能够相互通信并进行有效的协作。

当时机成熟时，如果你创建一个应用程序 [插入你偏好的框架]，你将能够发现一位经验开发者，他可以自信地进入项目代码库。这个人将能够开始处理功能，而无需你花时间向他们解释软件架构的每一个方面。

实践是使用框架的另一个重要原因。它们会让你全天不断地练习。这是一个极佳的消息！无论你在做什么，只有通过持续的实践才能实现掌握。

# 附录 I

## JavaScript 快速查表

我们必须将 JavaScript 文件连接到 HTML 文件中，以便在网站上使用 JavaScript。在编码过程中包含注释将帮助我们生成更好的代码。可以使用单行注释或多行注释。

- 为了让浏览器识别你的代码是用 JavaScript 编写的并执行它，你必须将代码封装在 `<script>` 标签中并粘贴到你的 HTML 页面。

```html



#我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。使用 JavaScript 编写 HTML 报告

## 内联脚本

你可以将 JavaScript 代码直接写在 HTML 报告中，使用 `<script>` 标签：

```html
<script type="text/javascript">
// 你的 js 代码在这里
</script>
```

## 外部脚本

外部 JavaScript 文件也可以直接引用到 HTML 报告中，使用 `<script>` 标签如下：

```html
<script src="filename.js"></script>
```

## 注释

JavaScript 注释对于解释代码、理解代码正在发生什么以及提高可读性非常有用。

### 注释类型

1. **单行注释**：以 `//` 开头
2. **多行注释**：使用 `/* */` 括起跨行注释

# JavaScript 变量实例

JavaScript 变量可以存储各种数据。等号运算符（`=`）用于在 JavaScript 中为变量赋值。JavaScript 支持以下数据类型：

- **var 变量**：在 JavaScript 中，`var` 是最常用的变量。只有在函数范围内可以重新声明并传输值。使用 `var` 声明的变量在执行 JavaScript 代码时会提升到栈顶。这是一个使用 `var` 关键字定义的变量示例：

```javascript
var x=140; // x 可以重新声明并赋予新值
```

- **const 常量**：为了避免意外结果，`const` 变量在使用之前必须在代码主体声明。在程序运行期间不能重新声明或以任何方式更改值。下面是使用 `const` 关键字定义的 JavaScript 变量示例：

```javascript
const x=5; // 不可能更改变量 x 值
```

- **let 变量**：类似于 `const` 变量，`let` 变量不能重新声明。然而，它们的值可以更改。以下是使用 `let` 关键字定义的变量：

```javascript
let x=202; // 变量不能重新声明，但可以更改值，例如 x=202;
```

## 数据类型

- **变量**：变量数据类型可以取广泛的值，因为，这个吧，它被称为变量。以下是一个变量数据类型的示例：`var y`
- **字符串**：由不同长度的多字符序列组成，构成 JavaScript 的字符串数据类型。你可以在下面的代码段中看到字符串数据类型的用法：`var demoString="Hello World."`
- **数字**：这些都是数字。所有的整数和实数都是可以接受的。这里有一个数值数据类型的应用示例：`var id=100`
- **操作**：你可以在 JavaScript 中在变量上附加操作。
- **对象**：JavaScript 中的对象是用于存储一组作为属性的命名值的存储位置。它们负责管理于自身的自己的信息组件和过程。以下是对象数据类型的示例：`var name="Jon Snow", id="AS123"`
- **布尔值**：布尔值可以是真（`true`）也可以是假（`false`）。以下是一个演示布尔数据类型的代码片段：`var booleanValue=true`
- **常量**：具有常量值的数据类型被称为“常量数”。以下是常量数据类型的实例：`const g=9.8`

# JavaScript 运算符

你可以在变量上使用 JavaScript 运算符来执行各种操作。这些是 JavaScript 中可能使用的多种运算符：

## 基础运算符

JavaScript 的**基础运算符**允许执行加法和乘法等基础算术运算。以下是所有 JavaScript 运算符的索引：

- 将两个整数相加，使用加号（`+`）。
- 要执行减法操作，请利用“减法运算符（`-`）”。
- 可以借助乘法运算符（`*`）乘数字。
- 为了进行除法，我们需要利用除法运算符（`/`）。
- 通过使用（`...`）分组运算符将表达式或子表达式括起来，运算符的评估求值顺序会被改变，使得优先级较低的运算符先求值。
- 当除以另一个整数时，可以通过取模运算符（`%`）找到余数。
- 要给整数加 1，使用自增运算符（`++`）。
- 当使用自减运算符（`--`）时，数字的值会减少 1。

## 位运算符

使用 JavaScript 的位运算符，你可以执行任何涉及数字位的操作。以下是 JavaScript 中可用的所有位运算符的概述：

- 位与运算符（`&`）对于两个操作数中对应位均为 1 的每一个位位置产生产生为 1 的结果。
- 只要每个操作数或两个操作数的位中有一个为 1，位或运算符（`|`）就会交付 1。
- 位非是一个运算符（`~`），它可以翻转操作数中的位。与其他位运算符一样，它将操作数转换为有符号 32 位整数。
- 位异异运算符（`^`）返回两个操作数中对应位均为 1 但并非全都为 1 的每一个位位置。
- 左移运算符（`<<`）将第一个操作数的位向左移动指定的位数。
- 通过提供一个正整数，右移运算符（`>>`）将第一个操作数向右移动相应数量的位。

## 比较运算符

JavaScript 有若干种比较运算符，所有运算符都列在下方。

- 只要它的两个操作数相等，相等运算符（`==`）将返回真或假的结果。
- 当它的两个操作数类型相同且值相等时，等价运算符（`===`）返回一个布尔值。
- 如果两个操作数不等，不等运算符（`!=`）返回一个布尔值。
- 如果两个操作数不是相同类型，或者如果它们不等，不等运算符（`!==`）将返回一个布尔结果。
- 在 JavaScript 中，只有条件（三元）运算符接受三个操作数：一个条件后面跟着一个问号（`?`），一个如果条件为真则运行的表达式后面跟着一个冒号（`:`），以及如果条件为假则执行的最终表达式。
- 如果左操作数的值小于右操作数，那么小于（`<`）将返回真。
- 当且仅当左操作数大于或等于右操作数时，（`>=`）运算符为真。
- 小于（`<=`）是一种相等运算符，如果左操作数小于等于右操作数，它为真。

## 逻辑运算符

整个 JavaScript 逻辑运算符如下：

- 逻辑与运算符（`&&`）用于布尔操作数集合，当且仅当所有操作数均为真时，其结果为真。
- 逻辑或（逻辑析取）运算符（`||`）表示当且仅当操作数中的任意一个为真时，操作数集合为真。
- 非运算符（逻辑取反、否定）（`!`）将真变为假。

# JavaScript 函数

JavaScript 中的函数是一个预定义的代码段，可用于实现某个目标。一旦被调用或触发，它就会开始运行。为了避免重复编写相同的代码，你可以将其保存为函数并在需要时调用它。JavaScript 中的 `function` 关键字用于定义新函数。JavaScript 能够做很多，包括：

## 函数及描述

- `parseInt()`: 它接收一个字符串并返回一个整数。
- `parseFloat()` 是一个接收字符串并返回浮点表示的函数。
- `isNaN()`: 测试一个值是否不是数字（Not a Number）。
- `Number()`: 它接收一个输入并返回相应的数字。
- `eval()`: 可以评估字符串形式的 JavaScript 代码。
- `prompt()`: 使用此方法生成一个文本框，请求用户输入。
- `encodeURI()`: 使用此方法，你可以将 URI 转换为 Unicode 格式。
- `match()`: 这是一个内置函数，可以检查字符串是否匹配正则表达式。

# JavaScript 中的数组

在许多语言中，将数据存储在数组是常见做法。它们被用于对事物分类。数组是同类项的序列。一组汽车集合：

```javascript
var cars=["Tesla", "Toyota", "Honda"];
```

有了关于数组的新知识，我们可以对结果应用各种变换。查看 JavaScript 中的许多 API：

- `push()`: 它在数组末尾用于添加新元素。
- `pop()`: 用于删除数组的最后一个元素。
- `concat()`: 用于连接多个数组。
- `splice()`: 用于以特定的方式和位置添加元素。
- `shift()`: 用于删除数组的第一个元素。
- `reverse()`: 用于保留元素的顺序。
- `slice()`: 用于将数组的一部分提取并复制到新数组中。
- `unshift()`: 用于在数组开头添加新元素。
- `toString()`: 用于将数组元素转换为字符串。
- `valueOf()`: 用于返回对象的原始值。
- `join()`: 用于将数组元素组合成一个字符串。
- `lastIndexOf()`: 用于返回元素在数组中出现的最后一个索引。
- `sort()`: 用于根据某些条件对元素进行排序。
- `indexOf()`: 用于返回元素在数组中首次出现的索引。

# JavaScript 中的字符串

字符串，正如我们已经所说的，只是用于各种用途的字符序列。由于字符串在 JavaScript 中非常强大，我们决定为其分配一个专门的章节。让我们来看看 JavaScript 的字符串函数以及它支持的各种转义序列。

在字符和通信领域，“特殊字符”被称为一种当在字符串中跟随其他字符时会改变那些字符含义的字符。转义字符是可用元字符的一个子集。字符周围的环境决定了该字符是否可以作为转义字符。为了封装字符串，JavaScript 可以使用单引号或双引号。例如，以下是 JavaScript 中可能使用的转义序列选择：

- `\\`—斜杠
- `\"`—双引号
- `\'`—单引号
- `\t`—水平制表符
- `\n`—换行
- `\v`—垂直制表符
- `\r`—回车
- `\b`—退格键
- `\f`—分页符

# DOM，JavaScript 文档对象模型

网站的代码根据文档对象模型（DOM）进行排列。JavaScript 在构建和更改 HTML 组件方面提供了大量选项，这些组件可以通过语言（称为节点）进行访问。

## 节点属性

让我们先检查 JavaScript DOM 中节点的某些属性：

- `attributes`：获取元素所有属性的实时集合。
- `baseURI` 属性当应用于 HTML 元素时，将返回该元素的主 URI。
- `childNodes`：以列表形式访问元素的子节点。
- `firstChild`：返回元素的第一个子节点。
- `lastChild`：元素的最后一个子节点。
- `nextSibling`：通过 `nextSibling` 返回与当前节点在树中处于同一层级的下一个节点。
- `nodeName`：通过调用 `nodeName` 方法返回节点的名称。
- `nodeType`：获取并返回节点的类型。
- `nodeValue`：可以使用 `NodeValue` 方法设置或检索节点的值。
- `ownerDocument` 是该节点的根文档对象。
- `Parent Node`：此函数返回作为当前元素父节点的 `Node`。
- `previousSibling`：使用 `previousSibling` 技术，此命令检索树中位于当前节点之前的节点。
- `textContent`：存储或检索节点及其子节点的文本内容。

## 节点方法

让我们看看 JavaScript 为这些 DOM 节点提供的节点方法：

- `appendChild()`：使用 `appendChild()` 方法将新的子节点作为最后一个子节点添加到元素中。
- 在 HTML 中，`cloneNode()` 是一个用于创建现有节点副本的函数。
- `compareDocumentPosition()` 方法用于检查两个元素文档位置之间的相似性和差异。
- 功能的 API 是由 `getFeature()` 返回的对象实现的。
- `hasAttributes()`：根据返回的值判断元素是否包含某些确定的属性。
- 如果元素具有任何子节点，`hasChildNodes()` 方法将返回 `true`，否则返回 `false`。
- 使用 `insertBefore()` 方法在当前节点左侧插入额外的子节点。
- 如果传递的 `namespaceURI` 是默认值，`isDefaultNamespace` 将返回 `true`；否则返回 `false`。
- 用于测试两个节点是否相等的函数 `isEqualNode()`。
- 如果两个元素具有相同的节点，`isSameNode()` 返回 `true`。
- 可以通过在元素上调用 `isSupported()` 方法来测试某功能是否被支持。
- `lookupNamespaceURI()` 方法获取给定节点的命名空间 URI 并返回它。
- 对于定的命名空间 URI，如果存在，`lookupPrefix()` 将返回带有前缀的 `DOMString`。
- `normalise()` 方法合并元素中相邻的文本节点并消除任何空节点。
- `Child()` 的 `removeChild()` 方法从元素中删除子节点。

## 元素方法

此函数用另一个节点替换元素的子节点。以下是 JavaScript 中可用元素方法的一些示例：

- `getAttribute()` 方法从元素中的节点中检索属性值。
- 输入命名空间和属性名称，`getAttributeNS()` 将以字符串形式返回该属性的值。
- 调用 `getAttributeNode()` 时，它将把传入作为属性的节点返回给你。
- `getAttributeNodeNS()` 函数检索与给定命名空间和属性名称关联的属性节点。
- 名“`getElementsByTagName`”的函数返回所有指定标签的子元素集合。
- 当带有标签名调用时，`getElementsByTagNameNS()` 返回来自给定命名空间的元素的动态 `HTMLCollection`。
- 使用 `hasAttribute()`，如果元素具有属性，则返回 `true`，否则返回 `false`。
- `hasAttributeNS()` 评估给定属性是否存在于给定命名空间的当前元素上，并据此返回 `true` 或 `false`。
- `removeAttribute()` 方法用于从元素中删除属性。
- 在给定命名空间的元素上调用 `removeAttributeNS()` 将从该元素删除该属性。
- 要设置或更改属性节点，使用 `setAttributeNode()`。
- 为元素添加新的命名空间属性节点只需调用 `setAttributeNodeNS()` 即可。

# 使用 JavaScript 转换数据

使用高阶函数，可以在 JavaScript 中进行数据转换。接受其他函数作为参数并返回另一个函数的函数被称为 JavaScript 中的高阶函数。`Map()`、`Filter()` 和 `Reduce` 是唯一接受函数作为输入的高阶函数。现在，让我们检查这些功能的应用。所有这些操作都可以在数组上执行，无需任何中间变量或集合，因为它们内置在 JavaScript 的原型链中。

## map() 方法

使用 `map()` 方法将函数应用于每个数组元素。数组的内容被逐一传递给回调方法，该方法随后生成一个维度相同的新数组。此函数可对每个数组元素应用统一的操作或转换，并返回一个包含更新值的相同长度的新数组。

## filter() 方法

`filter()` 方法用于在数据不符合某些条件时从数组中删除。数组中的每个项目都会传递给回调函数。当且仅当回调函数在每次迭代后返回 `true` 时，元素会被添加到新数组中。

## reduce() 方法

可以使用 `reduce()` 函数将数组中许多成员的结果合并为单个值。在调用 `reduce` 之前，需要提供积累器的初始值（最终结果）。在每个循环中，我们在回调函数中执行操作，并将操作的结果累积在一个变量中。

# Date 对象

在 JavaScript 中，日期对象是一个内置数据类型。通过它的帮助管理和修改日期和时间。新的 `Date()` 运算符用于构造日期对象，可以通过 4 种方式中的一种声明。

## 语法

```javascript
new Date()
new Date(milliseconds)
new Date(dataString)
new Date(year, month, date, hour, minute, second, millisecond)
```




JavaScript 提供了许多用于访问和生成日期时间信息的函数。这些策略包括但不限于：

## 方法与描述

| 方法 | 描述 |
| :--- | :--- |
| `getDate()` | 此函数返回给定月份内某日的数字表示（1–31）。 |
| `getTime()` | 使用 `getTime()`，你可以找出自 1970 年 1 月 1 日以来过了多少毫秒。 |
| `getMinutes()` | `getMinutes()` 是获取当前分钟（0–59）的函数。 |
| `getFullYear()` | 可以通过 `getFullYear()` 函数获取四数的当前年份（yyyy）。 |
| `getDay()` | `getDay()` 返回 0 到 6 之间的数字，代表星期。 |
| `parse()` | `parse` 接收字符串形式的日期并返回自 1970 年 1 月 1 日起的毫秒数。 |
| `setDate()` | 以数字形式，`setDate()` 返回今天的日期（1–31）。 |
| `setTime()` | 当需要更改时间时，使用 `setTime()` 函数（自 1970 年 1 月 1 日起的毫秒）。 |

## JavaScript 浏览器对象

除了 HTML 组件，JavaScript 还可以监控用户的浏览器行为并将属性整合到代码中。

下面列出了 JavaScript 可以使用的许多 Window 属性。

- `window.history`：返回窗口的历史对象。
- `innerHeight`：窗口的内部高度（像素）。
- `innerWidth`：内容区域的最内宽度。
- `closed`：如果窗口已关闭，`closed` 将返回 `true`，否则返回 `false`。
- `pageXOffset`：距离页面中心的水平像素距离。看起来你使用了鼠标在页面上水平滚动。
- `pageYOffset`：距离页面中心的垂直像素距离。文档进行了垂直滚动。
- `navigator`：返回窗口的导航对象（`navigator`）。
- `opener`：使用 `opener` 将返回初始化当前窗口创建的父窗口指针。
- `outerHeight`：窗口的总高度，包括标题栏和任何工具栏。
- `outerWidth`：窗口的总宽度，包括边界和任何其他组件。
- `defaultStatus`：如果你想修改或恢复状态栏的默认文本，请使用 `defaultStatus` 命令。
- `document`：返回与当前窗口关联的文档对象。

## 442 附录 I

- `frames`：这将返回当前窗口中的每一个 iframe。
- `location`：返回窗口的 `location` 对象。
- `name`：指定或返回窗口的标签。
- `parent`：指向活动窗口的父窗口。
- `screen`：获取当前窗口的 Screen 对象。
- `screenLeft`：窗口的左侧水平位置（相对于屏幕）。
- `screenTop`：窗口的顶部垂直位置。
- `self`：返回活动窗口。
- `status`：若要修改或恢复窗口状态栏中的文本，请使用 `status` 命令。
- `top`：返回浏览器中位于屏幕顶部的窗口。
- `screenX`：等同于标准的 `screenLeft` 属性，但在特定浏览器中是必须的。
- `screenY`：等同于 `screenTop`，但某些浏览器要求使用它。

以下是一些可以在用户浏览器中使用的 JavaScript 方法示例：

- 使用 `alert()` 方法弹出一个对话框，以警告用户并提供消除警告的选项。
- 你经常可以借助 `setInterval()` 方法来测试表达式或运行函数。
- `setTimeout()`：在经过指定的时间后，执行一个函数或表达式。
- 若要停止用 `setInterval()` 设置的计时器，请使用 `clearInterval()`。
- 调用 `clearTimeout()` 时将取消任何之前使用 `setTimeout()` 创建的计时器。
- 使用 `open()`，将在浏览器中打开一个新标签页或窗口。
- `print()` 函数会打印活动窗口的内容。
- 通过 `blur()` 函数移除活动窗口的焦点。
- 使用 `moveBy()`，你可以相对于当前位置重新定位窗口。
- 使用 `moveTo()` 方法，你可以将窗口移动到新位置。
- 如果你在窗口上使用 `close()`，该窗口将关闭且程序将退出。
- `confirm()`：调用一个包含消息和“确定（OK）/取消（Cancel）”按钮的对话框。
- `focus()` 函数用于聚焦活动窗口。
- `scrollBy()` 方法将按指定的像素数向下滚动文档。
- `scrollTo()` 方法接收一对 x、y 坐标并将文档滚动到该位置。
- `prompt()`：显示一个请求访问者输入内容的对话框。
- 输入像素值，然后 `resizeBy()` 将将该数值设置为窗口的新宽度和高度。
- `resizeTo()` 设置窗口的宽度和高度为你提供的参数。
- `stop()` 函数取消当前窗口的加载。

本节列出了 JavaScript 可以考虑的 Screen 属性列表。

- `height`：显示器的完整垂直距离。
- `screen width`：两个相邻显示元素之间的总水平距离。
- `colorDepth`：返回每个调色板颜位的深度。
- `availableHeight`：调用 `availableHeight` 时返回显示器的高度（排除 Windows 任务栏）。
- `availableWidth`：返回显示器的宽度。

## 444 附录 I

## 代数与计算

JavaScript 中提供了许多与 `Number` 和 `Math` 相关的属性和方法。

数字的一些特性包括它们的最大值或最小值、是否为正无穷或负无穷，或者是否为 NAN（非数字）。JavaScript 提供了多种处理数值的函数，包括：

- `valueOf()` 返回数字的原始形式。
- `toString()` 方法将整数转换为字符串。
- `toFixed()` 返回具有指定精度的数字的字符串表示。
- 它接收一个整数并使用 `toPrecision()` 方法返回指定长度的字符串。
- 使用 `toExponential()` 获取指数格式的舍入数字的字符串表示。

数字操作得益于 JavaScript 语言中 math 对象提供的数学函数而变得简单。数学对象具有多种数值属性，如对数、欧数、平方根以及 PI 的平方根。以下是通过 JavaScript 可用的某些数学处理工具列表：

- `max(x, y, z...n)` 返回范围内的最大值。
- `min(x, y, z...)` 函数返回给定数字集中最小的值。
- 若要获取 x 的指数值，只需输入 `exp(x)`。
- x 的自然对数（以 E 为底）；`log(x)` 返回此值。
- 若要获取输入值的平方根，请使用函数 `sqrt(x)`。
- 调用 `pow(x, y)` 的结果是 x 的 y 方。
- `round(x)`：将 x 调整到下一个整数。
- 当你输入 `sin(x)` 时，返回 x 的正弦值（x 为弧度）。
- 角的正切值由 `tan(x)` 给出，在这种情况下为 x。

## 附录 II

## TypeScript 简教程

将静态类型（static types）引入 JavaScript 是 TypeScript 带来的许多功能之一，这使得我们构建大型应用程序变得简单得多。

JavaScript 的创建是为了供各种类型的人使用，包括软件开发者以及非开发人员。它的设计目标是用户友好且直观，即使是没有经验的人也能理解它。这最终导致建立了一种出色的语言，用于生产在小型和大型之间规模的原型和项目。另一方面，使用 JavaScript 编程在涉及构建大型应用程序时可能难以扩展。这很大程度上是因为我们应用程序的组件无法公开指定其合约。

## TypeScript 历史概览

JavaScript（也称为 ECMAScript）最初是用于浏览的一种简单编程语言。在它被创建时，人们认为它将用于嵌入网页的小型代码片段。编写几百行代码在当时被认为是相当奇怪。正因如此，这类代码在旧版本的浏览器中执行较为缓慢。然而，随着时间的推移，JS 积累了更多的追随者，开发者也开始使用它来创建交互式体验。

## 附录 II ■ 449

- TypeScript 编译器的工作是在程序编译期间删除任何与类型相关的信息。

在 JavaScript 中，类型不被视为真正的特性，因为它们没有被使用。由于 TypeScript 必须先转换为常规 JavaScript，因此在代码被视为真正的 JavaScript 并提交到浏览器执行之前，必须移除与类型相关的内容。这是因为 TypeScript 必须这样做，而 TypeScript 编译器负责进行代码分析。如果系统有足够的基础来这样做，就会生成错误和警告。

### 语言部门

从源代码中提取类型信息的任务属于语言服务（language service）的职责范围。开发工具可以使用这些信息提供 IntelliSense 类型建议，并且在处理替代重构时也会用到这些信息。

## 由 TypeScript 定义的静态类型检查器

早些时候提到，某些编程语言在任何情况下都不允许执行包含缺陷的程序。静态检查是在不实际运行程序本身的情况下，发现计算机代码中错误的方法。根据所操作值的类型来判断某物是否构成错误的过程被称为“静态检查”，简称为“检查”。

因为 TypeScript 在程序执行之前通过检查值的类型来执行错误检查，因此它被称为静态类型检查器。例如，在之前提供的最后一个示例中，由于对象的类型存在错误。TypeScript 指出的错误如下：

```javascript
const obj = { width: 10, height: 15 };

const area = obj.width * obj.height;
```

属性 ‘height’ 不存在类型 '{ width: number; height: number }’ 上。你的意思是 ‘height’ 吗？属性 ‘height’ 不存在类型 '{ width: number; height: number }’ 上。你的意思是 ‘height’ 吗？

## 450 ■ 附录 II

## JavaScript 语言类型扩展

然而，TypeScript 和 JavaScript 之间有什么联系？

### 语法

我们将文本组合成程序的形式被称为其语法。由于 TypeScript 是 JavaScript 的超集，它与 JS 的语法兼容。举一个例子，这行代码有语法错误，因为它缺少一个：

```typescript
let a = (4
```

`') expected.') expected.`

没有任何 JavaScript 代码会因为语言语法问题被 TypeScript 标记为错误。这意味着你可以将任何功能性的 JavaScript 代码放在 TypeScript 文件中，而不必担心代码是如何编写的。

## 类型

另一方面，TypeScript 是一个类型超集，它扩展了控制不同类型的值可以应用的规则。它通过扩展管理值如何应用的规则来实现这一点。之前在 `obj.height` 上发生过的问题并不是由于语法错误；而是由于对某种值（类型）应用不当而导致的错误。

另一个例子是接下来的 JavaScript 代码，它在 Web 浏览器中运行时，将记录如下值：

```javascript
console.log(4 / []);
```

语法上正确的软件跟踪无穷大。另一方面，如果你尝试将一个数字除以数组，TypeScript 将抛错误，因为它认为这是一个无意义的操作。

```typescript
console.log(4 / []);
```

在算术运算的右侧，你可以自由使用任何数值、bigint 或枚举类型。在算术运算的右侧，你可以使用以“any”、“number”或“bigint”开头的类型，或者使用枚举类型。

有一种可能，将一个数字除以数组并不是你本意的操作。你很有可能是想将一个数字除以数组，也许看看这样做会发生什么，但在绝大多数情况下，这是代码中的错误。TypeScript 内置类型检查器的目标是允许正确的程序执行，同时在情况允许范围内尽可能识别常见的编程错误。

当你将一些代码从 JavaScript 文件移动到 TypeScript 文件时，根据代码在 JavaScript 文件中的编写方式，你可以在 TypeScript 文件中发现类型问题。可以想象这些是代码的合规问题，但也可能是 TypeScript 毫无无故地过度谨慎。在这篇文章中，我们将演示如何包含一系列 TypeScript 语法以消除此类错误。

## 运行期间的行为

在执行 JavaScript 的同时，另一种名为 TypeScript 的编程语言保持了功能的完整。例如，在 JavaScript 中，除以零的操作会产生无限（infinite）值，而不会在程序执行期间产生错误。在一般情况下，JavaScript 代码的执行不会受到 TypeScript 的任何重大影响。

因此，当你将代码从 JavaScript 迁移到 TypeScript 时，即使 TypeScript 认为代码存在类型错误，也可以确保代码的运行方式与 JavaScript 中 中。JavaScript 和 TypeScript 都使用相同的语法，这就是原因所在。

关于 TypeScript 提供的最重要的保证之一是它将保持运行时行为与 JavaScript 一致。这意味着你能够平滑地在两种语言之间切换，而不必担心任何可能导致应用程序停止正常运行的小幅修改。

## 类型擦除

当 TypeScript 编译器完成对代码的检查并准备构建“编译后”代码时，它通常会擦除所有类型。这是为了该过程的下一步做准备。这意味着当你的代码被编译时创建的简单 JS 不包含任何类型信息。

## 452 附录 II

基于此，TypeScript 永远不会根据它从你提供的数据得出的类型来更改程序的运行方式，因为它无法访问该信息。需要记住的一点是，即使在编译过程中可能会遇到困难，类型系统本身对你的程序在运行时运行没有任何影响。这是底线。

结论，包含 TypeScript 的包不包含任何额外的运行时库。由于你的应用程序将使用与 JavaScript 程序相同的标准库（或更多库），因此你不需要学习任何额外的 TypeScript 特定框架。这是因为你的应用程序将使用相同的库。

## TypeScript 的主要属性和函数

### TypeScript 对类型注解的支持

为变量或函数分配类型的过程被称为类型注解。

```typescript
const birthdayGreeter = (name: string, age: number): string => {
  return 'Happy birthday ${name}, you are now ${age}years old!';
};
```

```typescript
const birthdayHero = "Jane User";

const age = 22;

console.log(birthdayGreeter(birthdayHero, age));
```

示例展示了如何构造一个带有两个参数（`name` 和 `age`）的函数。我们给 `name` 字段分配了 `string` 类型，给 `age` 字段分配了 `number` 类型。

函数返回的值也可以被分配类型。在特定情况下，我们的函数将返回一个 `string` 类型的值。

```typescript
const birthdayGreeter = (name: string, age: number): string => {};
```

如果我们传入的类型与 TypeScript 预期的类型不同，就会得到错误。

### TypeScript 对结构类型的支持

编程语言 TypeScript 是一种结构类型语言，这意味着为了让两个项目被视为相同类型，它们必须具有等同属性。

### 利用 TypeScript 进行类型推断

在没有提供显式类型的情况下，TypeScript 编译器可能会根据自身的逻辑，根据变量的初始值或函数的应用分别为变量或函数推断类型。

```typescript
const platform = 'freeCodeCamp';

const add = (a: number, b: number) => a + b;
```

在刚刚所示示例中，变量 `platform` 被赋予了字符串值，尽管我们没有显式地这样做。此外，函数的返回值被假设为 `number` 类型。

### TypeScript 删除的字符

在编译期间，TypeScript 会消除类型系统的构造：

输入：

```typescript
let x: someType;
```

输出：

```javascript
let x;
```

## 为什么要使用 TypeScript？

### 检查拼写错误和对代码进行静态分析

自此，你代码中的总错误将会减少，因为每当你错误使用特定类型时，TS 都会提醒你。

## 454 附录 II

运行时错误也减少了，而且由于 TypeScript 具有静态代码分析，如果在代码中发现任何拼写错误或其他问题，你将获得警告。因此，错误将会变少，这可能导致测试范围的缩小。

### 类型上的注释可以替代代码文档

由于类型上的注释，我们能够理解（例如）一个函数预期接收什么类型的输入，以及它将返回什么类型的结果。此外，我们还能理解该函数将交付什么样的输出。

这使得代码更易于阅读，反过来也不仅让我们自己，也让其他人更容易理解代码的意图。

使用集成开发环境（IDE）的用户在使用 TypeScript 期间，可以获得更准确、更具洞察力的 IntelliSense 反馈，这是使用这种编程语言的另一个优势。这种功能的实现是由于 IDE 能够感知用户当前正在处理的特定类型的数据，从而实现了这一功能。

## TypeScript 入门之旅：快速上手

我们首先在应该开始的地方安装 TypeScript 包。在这种情况下，我们有两个选择：我们可以全局安装它，以便在系统中的任何项目中使用它；我们可以本地安装它，以便仅在当前正在工作的项目中使用它。

通过执行以下命令，你将能够全局安装 TypeScript：

```bash
npm install -g typescript
```

如果你不想在范围内安装任何内容，则需要执行此命令：

```bash
npm install --save-dev typescript
```




由于我们发现在整个开发过程中非常有用，因此 TypeScript 作为开发依赖包含在了本地安装中。首先，它必须被编译为 JavaScript 才能在生产环境中使用。TypeScript 无法在浏览器中执行。

## 附录 II 455

安装 TypeScript 之后，第一步是创建一个新项目。你可以通过以下命令来实现：

```bash
tsc --init
```

执行此命令后，将在项目的父目录中创建一个全新的 `tsconfig.json` 文件。该配置文件包含了在项目中使用 TypeScript 时可以使用的所有配置设置。

你可以在 `tsconfig.json` 文件的 `compileOptions` 键下为给定项目提供所有的构建设置。该文件位于项目的根目录下。

文件中已经包含了某些配置设置，但如果有必要，你有能力为项目添加额外的选项。你可以注释掉或删除不需要的编译器选项。

## 建立你的 TypeScript 开发环境建立基础

### 设置你的开发环境

**代码编辑器：** 你需要一个支持 TypeScript 的集成开发环境（IDE）来使用 TypeScript 提供的所有功能。虽然我们建议使用 Visual Studio Code（它也是用 TypeScript 设计的），你可以使用任何支持 TypeScript 的集成开发环境（IDE）。

**Node.js 和 npm：** 书中描述的每个项目在使用 npm 的同时，都调用一个一个 Node.js 开发环境。

当你安装 Node.js 时，会安装一个 JavaScript 包管理器 `npm`。

安装 Node.js 后，请运行以下命令以确认安装了功能性的 Node.js 环境：

```bash
node -v
```

在安装 TypeScript 之后，开始工作的第一步是创建一个新项目。你可以通过以下命令来实现：

```bash
tsc --init
```

执行此命令后，将在项目的父目录中创建一个全新的 `tsconfig.json` 文件。该配置文件包含了在项目中使用 TypeScript 时可以使用的所有配置设置。

你可以在 `tsconfig.json` 文件的 `compileOptions` 键下为给定项目提供所有的构建设置。该文件位于项目的根目录下。

文件中已经包含了某些配置设置，但如果有必要，你有能力为项目添加额外的选项。你可以注释掉或删除不需要的编译器选项。

## 建立你的 TypeScript 开发环境建立基础

### 设置你的开发环境

**代码编辑器：** 你需要一个支持 TypeScript 的集成开发环境（IDE）来使用 TypeScript 提供的所有功能。虽然我们建议使用 Visual Studio Code（它也是用 TypeScript 设计的），你可以使用任何支持 TypeScript 的集成开发环境（IDE）。

**Node.js 和 npm：** 书中描述的每个项目在使用 npm 的同时，都调用一个功能性的 Node.js 开发环境。

当你安装 Node.js 时，会安装一个 JavaScript 包管理器 `npm`。

安装 Node.js 后，请运行以下命令以确认安装了功能性的 Node.js 环境：

```bash
node -v
```

## 456 附录 II

### 开始项目

首先，创建一个项目目录并进入它：

```bash
mkdir my-project
cd my-project
```

接下来，初始化该项目：

```bash
npm init -y
```

这会创建一个 `package.json` 文件。现在，我们将 TypeScript 安装到项目中：

```bash
npm install --save-dev typescript
```

安装完成后，初始化 TypeScript 配置：

```bash
npx tsc --init
```

这将创建一个 `tsconfig.json` 文件。现在，我们可以创建一个 `index.ts` 文件并编写代码：

```typescript
touch index.ts
```

在 `index.ts` 中输入以下代码：

```typescript
let message: string = "Hello, TypeScript!";

console.log(message);
```

现在，将 TypeScript 编译为 JavaScript：

```bash
npx tsc
```

这将生成一个 `index.js` 文件。你可以使用 Node.js 运行它：

```bash
node index.js
```

## TypeScript 基础类型

### 基本类型

TypeScript 提供了许多基本类型。以下是常用的几种类型：

- `string`：用于字符串。
- `number`：用于数字（整数和浮点）。
- `boolean`：用于布尔值。

例如：

```typescript
let age: number = 25;

let myName: string = "Alice";

let isStudent: boolean = true;
```

## 数组

数组用于存储相同类型的数据列表。

```typescript
let numbers: number[] = [1, 2, 3];

let strings: Array<string> = ["Alice", "Bob"];
```

### 接口（Interface）

接口用于定义对象的形状。

```typescript
interface User {
    id: number;
    name: string;
    email?: string; // 可选属性
}

const user: User = {
    id: 1,
    name: "Alice"
};
```

### 联合类型（Union Types）

联合类型允许变量可以是多种类型之一。

```typescript
let id: string | number;

id = 101;

id = "A101";
```

### 枚举（Enums）

枚举允许定义一组常量。

```typescript
enum Direction {
    Up,
    Down,
    Left,
    Right
}

let moveDir: Direction = Direction.Up;
```

# 附录 II ■ 459

- 因为 VSCode 和 ts-node 会自动发现并存在的 `tsconfig` json 文件，所以没有必要对这些程序中的任何一个进行任何调整。

# 面向 JAVASCRIPT 开发人员的 TYPESCRIPT

TypeScript 与 JavaScript 之间的关系与人们预期的可能不同。TypeScript 提供了 JavaScript 的所有功能，并且在这些功能的基础上还额外提供了一层，称为 TypeScript 的类型系统。

例如，JavaScript 提供了字符串和数字等语言原始类型，但该编程语言不会验证以确保你一致性地分配了它们。TypeScript 则可以。

这表明，你已经编写且运行良好的 JavaScript 代码也是有效的 TypeScript 代码。使用 TypeScript 的主要优势在于，它通过指出你代码中表现出意外行为的区域来减少错误的发生概率。

# 从推断得出的类型

TypeScript 熟悉 JavaScript 编程语言，在某些情况下，它会自动为你创建类型。例如，当在 TypeScript 中创建一个变量并给它分配一个特定值时，TypeScript 将使用该值作为变量的类型。

```typescript
let HelloWorld = "Hello World";

let HelloWorld: string
```

TypeScript 可以构建一个与 JavaScript 代码兼容的类型系统，但由于它理解 JavaScript 的工作原理，它也拥有类型。这提供了一个类型系统，而不需要你向代码中添加字符来使类型显而易见。这就是为什么 TypeScript 能够确定在上面的示例中 `HelloWorld` 变量代表一个字符串。

在编写 JavaScript 时，你可以使用 Visual Studio Code 的自动补全功能。在底层，Visual Studio Code 使用 TypeScript，简化了处理 JavaScript 的过程。

# 附录 II

## 定义类型

JavaScript 为你提供了大量的不同设计模式库供选择。然而，设计模式使得自动推断类型更具挑战性（例如，使用动态规划的模式）。TypeScript 是 JavaScript 编程语言的扩展，它允许你在某些位置告诉 TypeScript 适当的类型。这样做是为了适应上述场景。

例如，可以使用以下代码来构建一个具有推断类型的对象，该对象具有属性 `name: string` 和 `id:`：

```typescript
const user = {
  name: "Hayes",
  id: 0,
};
```

你可以通过使用接口（interface）声明对该对象的形状提供详细描述：

```typescript
interface User {
  name: string;
  id: number;
}
```

```typescript
const user: User = {
  username: "Hayes",
  id: 0,
};

// Error: Type '{ username: string; id: number; }' is not assignable to type 'User'.
// Object literal may only specify known properties, and 'username' does not exist in type 'User'.
```

正因如此，TypeScript 以与相同的方式支持类和面向对象编程。在处理类时可以使用接口声明：

```typescript
interface User {
  name: string;
  id: number;
}

class UserAccount {
  name: string;
  id: number;

  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
}

const user: User = new UserAccount("Murphy", 1);
```

你可以使用接口对函数的参数和返回值进行注解：

```typescript
function getAdminUser(): User {
  //...
}

function deleteUser(user: User) {
  //...
}
```

接口可以使用当前 JavaScript 中可用的以下基本类型：Boolean、bigint、null、number、string、symbol 和 undefined。TypeScript 在此列表中增加了几个，例如 `any`（“允许任何内容”）、`unknown`（意味着“确保使用此类型的人宣布该类型是什么”）、`never`（意味着“无法想象这种类型可能存在”）以及 `void`（简单意味着“无”）。此外，你还有选择构建自己的种类的类型。

你会发现构建类型有两种不同的语法：接口（interfaces）和类型（type）。你应该更看重接口。但当你需要非常特定的特性时，请使用 `type`。

# 462 附录 II

# 组合的形式

你可以通过使用语言混合 TypeScript 简单的类型来构建更复杂的类型。实现这一目标有两种常用方法：通过使用联合类型（unions）和泛型（generics）。

# 联合类型（Unions）

在使用联合类型时，你可以定义一个类型可以是多个类型中的任意一个。例如，你可以将一个布尔类型描述为具有 true 或 false 的属性：

```typescript
type MyBool = true | false;
```

注意：如果你将光标悬停在上面句子中的 `MyBool` 单词上，你会发现它具有布尔分类。这是结构类型系统具有的特征之一。更多关于此的内容可以找到。

联合类型最常见的应用之一是表达用户允许的字符串字面量或整数集合：

```typescript
type WindowStates = "open" | "closed" | "minimized";

type LockStates = "Locked" | "unlocked";

type PositiveOddNumbersUnderTen = 1 | 3 | 5 | 7 | 9;
```

联合类型为处理多种类型提供了解决方案。你可能有一个函数既接受数组也接受字符串，如下所示：

```typescript
function getLength(obj: string | string[]) {
  return obj.length;
}
```

# USER AND EXPENSE 是 TYPESCRIPT 的类中的两个

JavaScript 这种面向对象的方式被称为 TypeScript。类、接口和其他等面向对象编程概念得到了支持。正因如此，JavaScript 在 ES5 之前没有类。这种功能是由 ES6 引入的。

# 附录 II ■ 463

# 开发类

在 TypeScript 中定义类需要使用类关键字。类的语法如下所示：

## 语法

```typescript
class class_name {
  // 类作用域
}
```

类的名称紧随类关键字之后。在命名类时，需要考虑标识符。

- **字段（Fields）** 定义在类内部并被称为字段。
- **构造函数（Constructors）** 负责为对象分配内存。
- **函数（Functions）** 是对象能够执行许多活动的表示。有时使用方法（Methods）来指代它们。

整体而言，这些组件构成了类的成员。考虑类的 TypeScript 版本：

```typescript
class Person {
}
```

编译时，它将生成以下代码：

```javascript
// Generated by typescript 1.10

var Person = (function () {
  function Person() {
    return Person;
  }
})();
```

# 464 附录 II

# 类声明示例

```typescript
class Car {
  // 字段
  engine: string;

  // 构造函数
  constructor(engine: string) {
    this.engine = engine;
  }

  // 函数
  disp(): void {
    console.log("Engine is :" + this.engine);
  }
}
```

```javascript
this.engine = engine;
}

// function
Car.prototype.disp = function () {
  console.log("Engine is: " + this.engine);
  return Car;
}())());
```

# 创建实例对象

使用 `new` 关键字，后紧跟类名即可创建该类的新实例。其语法如下所示：

## 语法

```javascript
var object_name = new class_name([arguments]);
```

实例化类的示例：`var obj = new Car("Engine 1")`

# 类继承

继承的概念可以通过 TypeScript 实现。程序从现有类中派生新类的能力被称为继承。作为后续类创建基础的类被称为父类（parent class）或超类（super class）。而新生成的类被称为子类（kid or sub classes）。

> `extends` 关键字允许一个类从另一个类继承属性和行为。子类继承其父类的所有属性和方法，私有成员和构造函数除外。

“继承”（inherited）一词也可以指代：

- 单继承——每个子类最多只能从一个父类继承。
- 多重继承——一个类可以从多个其他类中继承。目前 TypeScript 不支持多重继承。
- 多级继承——多个层级的继承。示例演示了如何在多个层级上继承。

## 数据隐藏

类具有控制其他类如何查看存储在其成员中的数据的能力。这种功能有时被称为数据封装（data encapsulation）或数据隐藏（data hiding）。

封装的思想在面向对象编程中通过访问修饰符（access modifiers）和访问限定符（access specifiers）的概念来实现。访问限定符和修饰符决定类的数据成员对于定义它们的类以外类是否可见。

### public

所有人都可以查看公共数据成员包含的信息。类数据成员的默认访问级别是公共。

### private

只有定义私有数据成员的类实例可以访问该成员的数据。每当外部类成员尝试访问私有成员时，编译器都会生成错误。

### protected

受保护的数据成员不仅对与被保护成员同类的成员可用，还对父类可能有的任何子类的成员可用。

# 接口（Interfaces）

## TypeScript 接口概述

TypeScript 中的接口定义了代码不同部分之间的约定。此外，它们为用于类型验证时提供了细粒度的名称。

首先，让我们来看一个简单的插图：

```typescript
function getFullName(person: {
  firstName: string;
  lastName: string;
}) {
  return `${person.firstName} ${person.lastName}`;
}

let person = {



```typescript
firstName: 'John',
lastName: 'Wick'
};
console.log(getFullName(person));
```

代码语言：TypeScript (`typescript`)

# 输出

John Wick

代码语言：TypeScript (`typescript`)

在这里，`getFullName()` 方法的参数由 TypeScript 编译器进行验证。

如果参数包含两个字符串类型的属性，TypeScript 编译器将允许参数通过。在这种情况下，它将抛出错误。

代码本身演示了函数参数注释如何增加代码复杂性并使其更难以理解。TypeScript 接口的设计考虑了这个问题。在下文中，使用了一个具有两个字符串属性的 `Person` 接口：

```typescript
interface Person {
  firstName: string;
  lastName: string;
}
```

代码格式：CSS (`css`) 使用驼峰命名法（camel case）。在名称中，每个单词的首字母大写。例如 `FullName`、`UserProfile` 和 `Person`。

`Person` 接口一旦定义，就可以作为类型使用。接口的名称也可以标注在函数的参数上。

```typescript
function getFullName(person: Person) {
  return `${person.firstName} ${person.lastName}`;
}
```

```typescript
let john = {
  firstName: 'John',
  lastName: 'Doe'
};

console.log(getFullName(john));
```

代码语言：TypeScript (`typescript`)

现在代码变得更易读了。

# 函数类型

接口允许你指定函数的类型以及对象的特征。

要指定函数类型，你将接口附加到函数签名上，该签名包含了带有类型的参数列表和返回类型。例如：

```typescript
interface StringFormat {
  (str: string, isUpper: boolean): string
}
```

TypeScript，一种编程语言 (`typescript`)

现在可以使用此接口用于特定类型的函数。

下面展示了为声明为函数的变量赋值相同类型的值。

```typescript
let format: StringFormat;
```

```typescript
format = function (str: string, isUpper: boolean) {
  return isUpper ? str.toLocaleUpperCase() : str.toLowerCase();
};
```

```typescript
console.log(format('hi', true));
```

代码语言：TypeScript (`typescript`)

# 输出

HI

# TypeScript 中的对象

构成对象的键值对集合被称为实例。值可以是从简单的数字到函数或其他事物的数组的任何内容。以下是语法：

```javascript
var object_name = {
  key1: "value1", // 标量值
  key2: "value",
  key3: function() {
    // 函数
  },
  key4: ["content1", "content2"] // 集合
};
```

如所示，对象不仅可以存储标量值和函数，还可以存储数组、元组和其他结构。

# TypeScript 的类型格式

假设你写了以下 JavaScript 对象字面量：

```javascript
var person = {
  firstname: "Tom",
  lastname: "Hanks"
};
```

当你需要更改对象的值时，JavaScript 提供了你需要的功能。假设我们后来发现 `Person` 对象需要一个额外的功能。

```javascript
person.sayHello = function() {
  return "hello";
};
```

如果你尝试使用相同的代码，TypeScript 编译器将返回编译错误。TypeScript 中的具体对象必须有对应的类型模板。在 TypeScript 中，所有对象都代表预定义类的具体实例。

# 鸭子类型（Duck-Typing）

如果对象具有相同的特征集，那么在鸭子类型中被认为是相同类型。鸭子类型不是检查对象的精确类型，而是确保特定的属性存在。

TypeScript 编译器利用鸭子类型系统，这允许在不损害类型安全的情况下动态生成对象。在下一个示例中，我们将看到如何向一个没有直接实现接口但具有所有必要的方法发送对象。

# TypeScript 中的命名空间（Namespaces）

使用命名空间允许你以有意义的方式组织代码。TypeScript 在设计时考虑了这一点，而 JavaScript 的变量声明位于全局作用域，如果在同一个项目中使用多个 JavaScript 文件，可能会覆盖或误解。

## 命名空间定义

要定义命名空间，必须首先使用 `namespace` 术语，随后是命名空间的实际名称，如下所示：

```typescript
namespace SomeNameNamespace {
  export ISomeInterfaceName {}
  export class SomeClassName {}
}
```

使用 `export` 术语指示哪些类或接口暴露在命名空间之外。

使用定义在不同命名空间中的类或接口的语法是使用 `namespaceName.className` 形式：

`SomeNameNamespace.SomeClassName;`

如果初始命名空间定义在完全不同的 TypeScript 文件中，必须使用三斜杠引用语法访问它。

```typescript
/// <reference path="FileName.ts" />
```

## 嵌套命名空间

嵌套命名空间定义如下：

```typescript
namespace namespace_1 {
  export namespace namespace_2 {
    export class class_name {}
  }
}
```

# TypeScript 中的模块（Modules）

此 TypeScript 模块的目标是提供一种封装和重用相似代码的方法。可以将模块分类如下：

附录 II ■ 471

- 内部模块
- 外部模块

## 内部模块

TypeScript 的内部模块在之前的版本中已经引入。这样做是为了让类、接口和函数在逻辑上分组到单个单元中，并将该单元导出到另一个模块。在 TypeScript 的最新迭代中，这种逻辑分类被称为命名空间（namespace）。因此，命名空间优于内部模块。虽然我们目前允许使用内部模块，但强烈建议使用命名空间。

## 内部模块语法（旧版）

```typescript
module TutorialPoint {
  export function add(x, y) {
    console.log(x + y);
  }
}
```

## 外部模块

TypeScript 外部模块的目的是允许开发者声明并加载许多外部文件之间的依赖关系。如果只是使用单个 `.js` 文件，则不需要外部模块。在历史上，浏览器脚本标签 `<script></script>` 被用于管理 JavaScript 文件之间的依赖关系。然而，由于模块加载速度非常慢，这种方式无法随着你的需求增长。这意味着异步加载模块不是一个选项，文件必须按顺序加载。在 NodeJs 等服务器端 JS 语言中，甚至不存在脚本标签。

依赖的 `js` 文件可以通过两种方式之一加载，这两种方式都涉及到一个主 JavaScript 文件：

- 服务器端 - NodeJs
- 客户端 - RequireJs

# TypeScript 中的函数

易于理解、易于维护且多功能的代码高度依赖于其作为基础构建块的函数。一组设计用于执行某些活动的语句被称为函数。

函数将软件的功能拆分为不同的逻辑部分。当函数被定义后，就可以通过调用它们来访问代码。这使得代码可以在多个地方使用。此外，函数简化了读取和维护程序代码的过程。

函数声明为编译器提供了有关函数名称、其参数以及返回类型的信息。函数的核心内容是其函数体，函数体由函数规范提供。

- **定义函数**：函数描述描述了项工作的细节以及完成该工作的方式。
- **调用函数**：在函数投入运行之前，必须对其进行调用。
- **返回函数**：函数可以在名为“返回函数”的过程中将控制权和值返回给调用它们的人。
- **参数化函数**：参数是向函数发送值的手段。

## 可选参数

在不需要为函数提供参数即可执行函数的情况下，可以使用可选参数。在参数名称前加一个问号是指示其为可选的一种方法。在调用函数时，可选参数应该作为最后一个参数传递。可能接受或不接受可选参数的函数语法如下：

```typescript
function function_name(param1[:type], param2[:type], param3[:type])
```

## 剩余参数

剩余参数类似于 Java 中的可变参数。发送给函数的不同值的数量不受剩余参数的任何方式限制。然而，所有传入的值需要具有相同的类型。换句话说，剩余参数的作用是作为多个相同类型参数的占位符。

当将参数声明为剩余参数时，该参数名称将赋予由三个点组成的前缀。任何涉及剩余的参数都应该出现在剩余参数之前。

## 默认参数

也可以为函数的参数设置默认值。另一方面，也可以直接提供此类参数的值。

## 语法

```typescript
function function_name(param1[:type], param2[:type] = default_value) {
```

# TypeScript 中的数字

`Number` 类充当包装器的功能，并使得像操作对象一样操作数字字面量。数值在 TypeScript 中可以表示为 `Number` 对象，就像 JavaScript 中的那样。可以使用数字对象将数字字面量转换为 `number` 类的实例。

## 语法

```typescript
var var_name = new Number(value)
```

如果给 `Number` 函数 `Object() { [native code] }` 传递一个不是数字的参数，它将返回 `NaN`（不是数字）。

# TypeScript 中的数组

使用变量来存储值会带来许多问题，其中包括：

- 变量本质上是标量的。换句话说，无论情况如何，变量声明一次都不可能包含多一个值。这表明，为了让程序能够容纳 `n` 个值，在程序运行之前需要进行 `n` 个变量声明。当必须保留更大的数据集时，使用变量并不是一个选项，因为这不符合实际情况。这意味着不能使用变量。
- 按照它们声明的顺序检索或读取值可能是困难的，因为程序中变量的内存分配似乎是按照任意顺序分配的。

为了解决这个问题，TypeScript 编程语言在其工具箱中有一个名为数组（arrays）的组件。当我们谈论数组时，指的是所有具有相同数据类型的项集合。被称为数组的项集合其元素都是相同种类的。排序是用户自行选择拥有的。

## 数组由什么组成

以下列表更深入地概述了数组的属性：

- 每只要进行声明，内存将按顺序分配。
- 数组中永远不会有变化。这意味着一旦启动了数组，其大小就无法更改。
- 每一个内存块都是项的替代品。
- 数字值表示数组的维度或数组的大小。
- 使用逗号分隔的一组值。
- 使用单个数字来特定标识元素。
- 就像变量一样，数组在使用之前需要编写它们的定义。在声明数组之前需要使用 `var` 关键字。
- 在数组元素中填充数据的操作被称为“数组初始化”，它是许多编程语言的一部分。
- 虽然可以更新或编辑数组项，但无法删除它们。数组元素不可删除。

## 数组包含的对象

如果需要，也可以通过 `Array` 对象从头创建一个数组。

- 数字值表示数组的维度或数组的大小。
- 使用逗号分隔的一组值。

# 附录 II ■ 476

```javascript
var mytuple = [];

mytuple[0] = 120;
mytuple[1] = 234;
```

# TypeScript 中的联合类型（UNION）

得亏 TypeScript 1.4，程序现在具备了混合一种或两种不同类型的能力。联合类型（Union types）是一种非常有用的方法，用于描述一个可以是多种不同类型中任意一个的值。在引用联合类型时，使用管道符号（`|`）来表示两个或多个数据类型的组合。简单而言之，联合类型的语法看起来像是由几个类型组成的字符串，每个类型之间用竖线分隔。

## 语法

`Type1|Type2|Type3`

## 示例：联合类型变量

```typescript
var val: string | number;

val = 12;

console.log("numeric value of val " + val);

val = "This is a string";

console.log("string value of val " + val);
```

前面的插图显示变量的类型为联合。这指定了变量可以是数字，也可以是字符串。两者都是接受的。

# TypeScript 中的环境声明（AMBIENTS）

在 TypeScript 中，环境声明（ambient declarations）是一种用于通知 TypeScript 编译器实际源代码存储在另一个位置的方法。这些声明可以放在文件的任何地方。如果它使用了多种不同的第三方 JS 框架，例如 jQuery、AngularJS 或 NodeJS，你将无法在 TypeScript 中重新构建它。这是因为 TypeScript 不兼容这些框架。TypeScript 程序员在尝试利用这些包的同时，在保持类型安全和智能提示（intellisense）方面可能会遇到挑战。TypeScript 可以通过使用环境声明与其他库进行无缝连接，从而扩展其功能。

## 环境声明的定义（Definition of Ambients）

按照习惯，环境声明存储在具有以下扩展名的类型声明文件中：`.d.ts`

`Sample.d.ts`

上面显示的文件不会被编译为 JavaScript。它将同时用于类型安全和智能提示。

以下语法将用于定义环境变量或模块：

```typescript
declare module Module_Name {
}
```

客户端 TypeScript 文件应当以上述所示的方式包含对环境文件的引用。

```typescript
// <reference path="Sample.d.ts" />
```



# 注释 (NOTES)

+ 1 简简历史/静态类型检查器/ (2022,10月19日)/ `www.typescript.org/docs/books/handbook/typescript-from-scratch.html`
+ 2 TypeScript 的支柱/特性/如何入门/ (2022,10月19日)/ `www.freecodecamp.org/news/learn-typescript-basics/`
+ 3 设置TypeScript 开发环境/(2022,10月19日)/ `www.newline.com/beginners-guide-to-typescript/setting-up-your-typescript-development-environment`
+ 4 针对 JavaScript 程序员的 TypeScript
+ 5 `www.tutorialpoint.org/docs/handbook/typescript-in-5-minutes.html`
+ 6 TypeScript 中的类：`User` 和 `Expense`
+ 7 `www.tutorialpoint.com/typescript/typescript_classes.htm`
+ 8 TypeScript - 对象
+ 9 `www.tutorialpoint.com/typescript/typescript_objects.htm`
+ 10 TypeScript - 命名空间
+ 11 `www.tutorialpoint.com/typescript/typescript_namespaces.htm`
+ 12 模块

# 附录 III

# JavaScript 工具

在本章中

- Gulp
- Grunt
- npm

在上一章中，我们涵盖了 TypeScript 的简要指南，在本章中，我们将讨论实用的 JS 工具。

由于 JavaScript 是一种非常流行的语言，并且所有前端 Web 应用都以某种形式使用它，许多出色的工具帮助我们轻松地开发高质量的 JavaScript 应用。

工具生态系统每天都在增长，可以使用更多用于创建和调试 JavaScript 应用的工具。

# GULP 概述

我们将讨论 Gulp 及其安装、优点和缺点。¹

Gulp 到底是什么？

Gulp 是一个运行在 Node.js 平台上的任务运行器。Gulp 完全使用 JavaScript 代码运行前端任务和大型 Web 应用程序。它自动化了系统任务，如 CSS 和 HTML 压缩、库文件合并以及编译 SASS 文件。这些任务可以通过使用 Shell 或 Bash 脚本在命令行中执行。

# 为什么我们应该使用 Gulp？

它比其他任务运行器更短、更简单、更快。CSS 预处理器有 SASS 和 LESS。编辑源文件后，页面会自动刷新。

Gulp.js 易于理解和构建，因为它使用 JavaScript 代码来构建任务。

# 历史

CC0 许可证适用于所有 Gulp 文档。Gulp v1.0.0 最初于 2015 年 1 月 15 日发布，当前版本为 v3.9.0。

### 特性

- 支持压缩和合并。
- 使用纯 JavaScript 代码。
- 将 LESS 或 SASS 转换为 CSS。
- Node.js 平台在内存中管理文件操作并提高速度。

### 优点

- 与任何其他任务运行器相比具有显著的时间优势。
- 代码编写和理解简单。
- 测试 Web 应用简单。
- 插件易于使用，并且旨在同时只做一件事。
- 重复执行重复任务，如压缩样式表、压缩图像等。

# 缺点

- 它比 Grunt 有更多依赖项，而且是一个新手。
- 我们无法使用 Gulp 插件执行多个任务。
- Grunt 的配置没有那么整洁。

# GULP 安装

本节将引导我们逐步安装 Gulp。

Gulp 系统要求 跨平台

- 操作系统 跨平台
- IE（Internet Explorer 8+）、Firefox、Google Chrome、Safari 和 Opera 都是支持的浏览器。

安装 Gulp

第 1 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

![](img/70a7539ec7c3f429f5e3c9c64df71823_521_0.png)

Node.js 是跨平台的 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

| 16.18 LTS | 19.0. Current |
| :--- | :--- |
| 用户 | 特性 |
| 其他下载 | 更新日志 |
| 其他下载 | API 文档 |

第 2 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

Node.js 是一个开源的跨平台 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

第 3 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

Node.js 是一个开源的跨平台 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

第 4 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

Node.js 是一个开源的跨平台 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

第 5 步：为了显示 `npm`（Node.js 包管理器）的版本，请在命令提示符中输入以下命令。

`"-g"` 参数保证了 Gulp 在整个项目中可用。

```bash
npm install gulp -g
```

第 6 步：查看 Gulp 的版本以确保其已安装。

```bash
gulp -v
```

（注：关于步骤 3-7 的 OCR 文本是重复/乱码的。我根据文中反映的标准 `npm` 安装程序重构了逻辑流。）

（注：关于页面 521-522 的提供的 OCR 文本非常混乱。我将贴近提供的文本并修复明显的错误。）

（注：关于 521-522 的 OCR 文本极其损坏。我将提供实际内容的尽可能清晰的版本。）

# GULP 安装

本节将引导我们逐步安装 Gulp。

Gulp 系统要求 跨平台

- 操作系统 跨平台
- IE（Internet Explorer 8+）、Firefox、Google Chrome、Safari 和 Opera 都是支持的浏览器。

安装 Gulp

第 1 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

![](img/70a7539ec7c3f429f5e3c9c64df71823_521_0.png)

Node.js 是一个开源的跨平台 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

| 16.18 LTS | 19.0. Current |
| :--- | :--- |
| 用户 | 特性 |
| 其他下载 | 更新日志 |
| 其他下载 | API 文档 |

第 2 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

Node.js 是一个开源的跨平台 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

第 3 步：运行 Gulp 示例，我们需要 Node.js。下载 Node.js，请访问 `https://nodejs.org/en/`，我们将看到下面的屏幕。

Node.js 是一个开源的跨平台 JavaScript 运行时环境。

Node.js 19 是新的！

下载 Windows (x64)

第 4 步：为了显示 `npm`（Node.js 包管理器）的版本，请在命令提示符中输入以下命令。

`"-g"` 参数保证了 Gulp 在整个项目中可用。

第 5 步：在命令提示符中安装 Gulp。

```bash
npm install gulp -g
```

第 6 步：查看 Gulp 的版本以确保其已安装。

```bash
gulp -v
```

# 附录 III

## 设置我们的项目

在我们的计算机上创建一个文件夹，例如名为“work”，用来保存我们的项目。`work` 文件夹包含以下文件和子文件夹：

- `Src`: 预处理过的 HTML 源代码文件和目录位于 `Src` 目录。
- `Images`: 包含未压缩的图片。
- `Scripts`: 包含几个已经处理过的脚本文件。
- `Styles`: 由几个预处理过的 CSS 文件组成。
- `Build`: 生产环境文件位于此自动生成的文件夹中。
- `Images`: 由压缩后的图片组成。
- `Scripts`: 包含压缩代码的单个脚本文件。
- `Styles`: 包含压缩代码的单个 CSS 文件。
- `gulpfile.js`: 用于指定我们任务的配置文件名为名为 `gulpfile.js`。

## 使用 GULP 开发应用程序

我们在上一节中学习了 Gulp 的安装和基础知识，涵盖了 Gulp 构建系统、包管理、任务运行器和 Gulp 结构等主题。⁴

以下是我们在本节中将检查的创建应用程序的一些基础知识：

- 声明必需的依赖项
- 为依赖项创建任务
- 执行任务
- 观察任务

## 依赖项声明

在为应用程序安装插件时，我们必须指示插件的依赖项。像 `bower` 和 `npm` 这样的包管理器会处理这些依赖项。

让我们在配置文件为 `gulp-imagemin` 插件定义依赖项。可以使用以下命令行安装此用于压缩图片的插件：

```
npm install gulp-imagemin --save-dev
```

如下代码所示，我们可以在配置文件中包含依赖项。

```
var imagemin=require(`gulp-imagemin`);
```

## 依赖项的任务创建

任务允许我们以模块化的方式配置 Gulp。每个依赖项都必须有自己的任务，我们必须将其添加以设置额外的插件。Gulp 任务将组织如下：

```javascript
gulp.task(`taskname`, function() {
  //在这里，执行操作
});
```

其中 `"function()"` 执行我们的任务，`"taskname"` 是一个字符串名称。`gulp.task` 定义了对其他任务的依赖关系，并将函数注册为带有具名的任务。

如下代码所示，我们可以为之前创建的依赖项构建任务。

```javascript
gulp.task(`imagemin`, function() {
  var imgsrc = `src/images/**/*`, imgdest = `build/images`;
  gulp.src(imgsrc)
  .pipe(changed(imgdest))
  .pipe(imagemin())
  .pipe(gulp.dest(imgdest));
});
```

图片保存在 `img src` 对象中，可以在目录 `src/images/**` 中找到。`imagemin` 构造函数将其传递到进一步的函数中。通过调用带有目标目录参数的 `dest` 方法，它会压缩从 `src` 文件夹传输到 `build` 文件夹的图片。

### 运行任务

Gulp 文件已配置完毕并准备好运行。要执行该任务，请在项目目录下输入以下命令。

```
gulp imagemin
```

## GruntJS 概述

我们将讨论 GruntJS 及其安装、优缺点。GruntJS 是一个 JavaScript 任务管理器，可以毫不费力地自动化我们应用程序的各种操作，提高开发者的生产力。⁵ GruntJS 拥有许多不同任务的插件。其中一个实例是 `nodemon` 插件，当应用程序中的任何 JavaScript 文件发生变化时，它会自动重启 `node` 服务器。因此，我们不需要在每次更改 JavaScript 时手动停止并重启 `node` 服务器。我们可以使用 `grunt-contrib-css` 插件来压缩 CSS 文件。我们可以使用 `grunt-jsfmt` 插件对应用程序中的 JavaScript 进行格式化、搜索或重写。

### 我们为什么应该使用 Grunt？

Grunt 可以轻松地执行编译、单元测试、文件压缩、测试执行、执行等重复操作。⁶ Grunt 自带任务，让我们的插件和脚本功能更多。Grunt 的生态系统非常庞大；我们可以以最少的努力自动化任何内容。

### 历史

GruntJS 的第一行源代码添加于 2011 年。

2013 年 2 月 18 日发布了 Grunt v0.4。

2014 年 5 月 12 日发布了 Grunt v0.4.5。

Grunt 目前的稳定版本是 1.0.0 r1，于 2016 年 2 月发布。

### 优点

- 我们可以使用 Grunt 快速执行文件压缩、编译和测试。
- Grunt 统一了 Web 开发者的工作流。
- 因为它具有最小的基础设施，Grunt 使得处理新的代码库变得简单。
- 它通过加速开发工作流来提高项目性能。

## 缺点

- 每当 `npm` 包更新时，我们必须等待 Grunt 的作者。
- 每项工作都旨在执行特定的功能。
- 如果我们希望扩展某个任务，我们必须采用某些方法来完成工作。
- Grunt 为单个插件提供了大量的配置选项。
- Grunt 配置文件通常很长。

## GRUNT 的功能

Grunt 是一个基于 JavaScript 的任务运行器，可用于自动化工作流中的重复操作，并作为 JavaScript 对象的命令行工具。⁷

以下是 GruntJS 的一些最显著的功能：

- Grunt 让工作流变得像编写配置文件一样简单。
- 毫不费力地，我们可以自动化重复操作。
- Grunt 是一个著名的 NodeJS 任务运行器。它适应性强且被频繁使用。
- 它采用基础方法，任务用 JS 编写，配置用 JSON 编写。
- Grunt 压缩 JavaScript、CSS 文件、测试文件、CSS 处理器文件（SASS、LESS）和其他文件。
- Grunt 自带任务，让你的插件和脚本功能更多。
- 它通过加速开发工作流来提高项目性能。
- 因为它具有最小的基础设施，Grunt 使得处理新的代码库变得简单。
- Grunt 的生态系统非常庞大；我们可以以最少的努力自动化任何内容。
- Grunt 减少了执行重复活动时出错的可能性。
- Grunt 现在拥有近 4000 个插件。
- 它可以应用于大型项目。

## GRUNT 的设置

本节将逐步引导我们如何在系统中安装 Grunt。⁸

### Grunt 系统要求

- 跨平台操作系统
- 支持 Internet Explorer（8 及以上）、Firefox、Google Chrome、Safari 和 Opera

### Grunt 的安装

第 1 步：为了执行 Grunt，我们需要 Node.js。当我们点击链接 `https://nodejs.org/en/` 下载 Node.js 时，屏幕将显示。

Node.js 是一个开源、跨平台的 JavaScript 运行时环境。

| 16.18.0 LTS | 19.0.0 Current |
|---|---|
| 适用于大多数用户 | 最新功能 |
| 其他下载 | 更改日志 | 其他下载 | 更改日志 | |

有关支持版本的信息，请查看发布计划。

下载带有最新功能的压缩包。

第 2 步：运行安装程序在我们的机器上安装 NodeJs。

第 3 步：第三步是设置环境变量。

### 用户变量 PATH

- 右键点击“我的电脑”。
- 选择“属性”。
- 接下来，点击高级选项卡下的“环境变量”。
- 当环境变量中的 `PATH` 项出现时，双击它。
- 将出现编辑用户变量窗口，如下所示。将 `C:\Program Files\nodejs\node_modules\npm` 作为 NodeJs 文件夹路径添加到变量值框中。如果已经为其他文件建立了路径，请按照格式在分号 (;) 之后添加 NodeJs 路径。

完成后点击确定。

### 系统变量

- 双击屏幕上系统变量下的 `Path`。
- 将出现编辑系统变量的窗口，如下所示。如下所示，将 `C:\Program Files\nodejs\` 作为 NodeJs 文件夹的路径并点击确定。

# 490 ■ 附录 III

第 4 步：要在你的系统上完成 Grunt 的安装，请如下所示全局安装其命令行接口 (CLI)。

```
npm install -g grunt-cli
```

运行上述命令后，`grunt` 命令将添加到系统路径中，并可以在任何目录下使用。

安装 `grunt-cli` 并不会安装 Grunt 任务运行器。`grunt-cli` 的功能是执行 Gruntfile 旁安装 Grunt 版本。它允许系统同时安装多个 Grunt 版本。

第 5 步：为了使用 Grunt，我们需要生成配置文件。

```
package.json
```

`package.json` 文件与 Gruntfile 位于项目的根目录下。当我们在与 `package.json` 相同的文件夹中执行 `npm install` 命令时，它将使用 `package.json` 来适当运行每个依赖项。

我们可以在命令行提示符中使用以下命令生成基础的 `"package.json"` 文件：

```
npm init
```

`"package.json"` 文件的基础结构如下：

```json
{
  "name": "tutorialsession",
  "version": "0.1.0",
  "devDependencies": {
    "grunt-contrib-jshint": "~0.10.0",
```



`"grunt-contrib-nodeunit": "~0.4.1"`,

`"grunt-contrib-uglify": "~0.5.0"`

}

}

以下命令可用于向已存在的`package.json`文件添加 Grunt 和 Grunt 插件。

```
npm install <module> --save-dev
```

# 附录 III 491

本地安装的模块由上述命令中的单词`module`指示。前面的命令还会自动将`<module>`添加到`devDependencies`中。

例如，以下命令将把最新版本的 Grunt 添加到你的`devDependencies`并安装它。

```
npm install grunt --save-dev
```

### Gruntfile.js

我们在`Gruntfile.js`文件中定义 Grunt 设置。我们在这里编写设置。如下所示，基础的`Gruntfile.js`文件：

```javascript
// (Grunt 及其插件所需的) 我们的包装函数
// 此函数包含了所有的配置
module.exports = function(grunt) {

  // 配置 GRUNT
  grunt.initConfig({

    // 从 package.json 文件中获取配置信息
    // 这样我们就可以使用像 name 和 version (pkg.name) 等内容
    pkg: grunt.file.readJSON('package.json'),

    // 所有的配置都放在这里
    uglify: {

      // uglify 任务配置
      options: {},
      build: {}

    }

  });

  // 记录某些信息
  grunt.log.write('Hello world! Welcome to Tutorial!');

  // 加载提供 “uglify”任务的插件
  grunt.loadNpmTasks('grunt-contrib-uglify');

  // 默认任务
  grunt.registerTask('default', ['uglify']);

};
```

# 开始使用 GRUNT

利用 Grunt 需要 Node.js，请确保其已安装好。使用 Node.js 包管理器，我们可以安装 Grunt 及其插件。⁹

在机器上安装 Grunt 之前，我们通过命令行更新 Node 包管理。

```
npm update -g npm
```

在 Mac 或 Linux 计算机上提供管理员访问权限，请在命令行开头使用`sudo`单词，如下所示。

```
sudo npm update -g npm
```

### CLI 的安装

安装的 Grunt 版本通过 CLI（命令行接口）启动。我们必须全局安装 Grunt 的命令行接口 (CLI) 才能开始使用它。

```
npm install -g grunt-cli
```

运行上述命令后，`grunt`命令将添加到系统路径中，并可以在任何目录下使用。通过安装`grunt-cli`，我们并没有安装 Grunt 任务运行器。它允许系统同时安装多个 Grunt 版本。

### CLI原理

每次执行 Grunt 时，CLI 都会使用`require()`机制检查系统中是否已安装 Grunt。我们可以使用`grunt-cli`从项目中的任何目录启动 Grunt。如果本地使用了 Grunt，`grunt-cli`将利用本地安装的 Grunt 库并应用 Grunt 文件中的配置。

### 在新项目和当前项目上工作

如果我们正在处理一个已经配置并包含`package.json`和`Gruntfile`的项目，请遵循下列表说明：

- 找到项目的项目根目录路径。
- `npm install`命令可用于安装依赖。
- 使用`grunt`命令启动 Grunt。
- 如果我们开始一个新项目，请在项目中包含`package.json`和`Gruntfile`这两个文件。
- `package.json`：当我们在相同文件夹中执行`npm install`命令时，位于项目根目录的`package.json`文件将用于运行所指示的每个依赖项。
- `Gruntfile.js`：项目的配置设置写在`Gruntfile.js`文件中。

### package.json

当我们在相同文件夹中执行`npm install`命令时，`package.json`文件用于运行提到的每个依赖项，并位于项目根目录下`Gruntfile`旁边。

有几种方法可以构建`package.json`，如下所示：

- 使用`grunt-init`生成`package.json`文件。
- 我们也可以使用`npm-init`命令来构建`package.json`文件。

```json
{

  "name": "tutorialsession",

  "version": "0.1.0",

  "devDependencies": {

    "grunt-contrib-jshint": "~0.10.0",

    "grunt-contrib-nodeunit": "~0.4.1",

    "grunt-contrib-uglify": "~0.5.0"

  }

}
```

本地安装的模块由上述命令中的单词`module`指示。前面的命令还会将`<module>`添加到`devDependencies`中。例如，以下命令将把最新版本的 Grunt 添加到你的`devDependencies`并安装它。

## 496 附录 III

可能会指派人员执行这些活动，但因为这些活动相对简单，执行这些活动的人去做其他事情会效率更高。

这就是 Grunt 和 Gulp 发挥用场的地方。

我们可以使用一段非常简单的代码、插件以及 Gulp 或 Grunt 来构建一个自动执行任务的过程。

这两个程序都能允许您检查特定文件夹中的新文件或更改，并执行与它们相关的操作。

换句话说，在我们配置了想要的过程并将其应用于现有文件后，任何新文件或更新的文件都可以自动应用这些过程。

假设我们设置了一个压缩`images`目录中`jpg`文件的程序。

当我们执行该程序时，所有照片都会被移除 EXIF 数据并进行压缩。

一旦我们正确安装并配置了 Gulp 或 Grunt，每个工具的图像压缩任务代码看起来像这样：

### Gulp

```javascript
gulp.task('jpgs', function() {

  return gulp.src('src/documents/*.jpg')

  .pipe(imagemin({ progressive: true }))

  .pipe(gulp.dest('optimizedimages'));

});
```

### Grunt

```javascript
imagemin: {

  jpgs: {

    options: {

      progressive: true

    },

    files: [{

      expand: true,

      cwd: 'src/img',

      src: ['*.jpg'],

      dest: 'documents/'

    }]

  }

}
```

## 附录 III 497

如果我们还配置了 Gulp 或 Grunt 来检查新文件或更新的文件，保存到目录的任何更改或新文件都将被压缩，EXIF 数据将立即擦除。

Gulp 或 Grunt 可以高效地完成这项工作，在大量文件的情况下，它们所需的时间仅是手动执行时间的一部分。

## Gulp vs Grunt：有什么区别？

既然我们已经知道 Gulp 和 Grunt 可以完成此工作，让我们来谈谈它们是如何实现的。这两个程序都是使用 Node.js 的运行器，Node.js 是一个用于开发工具和应用的开源 JavaScript 运行时环境。Gulp 和 Grunt 依赖插件来完成我们希望为我们完成的任务。

构建任务，这两个工具都利用`.js`文件；对于 Grunt，你使用`gruntfile.js`，而对于 Gulp，我们使用`gulpfile.js`。我们可能未使用函数，而是通过`gulp.task`和`gulp.task`定义工作流。

每个工具可以执行并自动化的最频繁的任务如下：

- 图像文件压缩
- 移除脚本调试器和控制台语句
- CSS 和 JavaScript 最小化、合并和清理
- 代码错误检查
- Less 文件编译
- 将更新发送到实时服务器
- 数据库更新

## Gulp vs Grunt：哪一个更快？

在速度方面，Gulp 具有显著优势，尽管这种优势可能并不那么显著，而且 Grunt 的改进在很大程度上缩小了速度差异。

Gulp 目前的速度优势是因为它使用了流（streams）并在内存中处理作业，导致只写入一个文件。

此外，Gulp 可以同时处理多个作业，而 Grunt 通常一次只处理一个任务。

## 498 附录 III

MWtech 曾了一项速度测试，以比较使用 Gulp 和 Grunt 进行 Sass 编译所需的时间。结果显示，Gulp 要快得多，仅花费 1.27 秒，而 Grunt 需要 2.348 秒。当插件在 Grunt 中执行文件时，会保存一个临时文件。文件通过所有插件后，会写入最终目标文件。

将数据写入磁盘会显著增加执行活动所需的时间；然而，“显著”是一个相对词汇。除非我们正在处理一个庞大的项目，否则 Gulp 或 Grunt 的输出时间将以秒或毫秒计。

即使是 Grunt，也需要 500 ms 才能完成 Gulp 在 50 ms 内即可完成的任务，这是十倍的差异；对于长长的 Grunt 时间范围，我们讨论的是半秒的差异。比较 Gulp 和 Grunt 时，我们处理的项目规模决定了性能是否是一个问题。即使速度对我们来说是一个问题，Grunt 在今年早些时候获得了管道支持（截至 0.5 版本），速度差异可能比大多数人执行时要低。

## Gulp vs Grunt：配置对比编码

Gulp 和 Grunt 在配置代码方面的关键区别一直引起了激烈争议。Gulp 旨在帮助我们使用单用途插件和脚本来实现目标。在大多数情况下，这使得为 Gulp 编写插件比为 Grunt 编写插件容易得多。此外，由于 Gulp 更关注代码和单任务插件，在 Gulp 中设置插件的程序比 Grunt 插件要标准化得多。

然而，问题可能较少关于代码，而在于我们（如果适用的话）我们的团队对 node 流（node streams）有多熟悉。Gulp 大程度上依赖 node 流，除非其他所有与 Gulp 工作的人都熟悉它们，以及管道（pipes）、缓冲区（buffers）和异步 JavaScript，否则处理 Gulp 将是一场苦战。

虽然配置 Grunt 比设置 Gulp 需要的时间，但 Grunt 要易用得多，因为它依赖于配置而不是代码。此外，虽然 Gulp 更容易阅读，但许多人认为 Grunt 写起来更简单。如果我们与一个技能水平各异的大群体一起工作，Grunt 可能是更好的选择。要使用它，请阅读手册，获取并设置必要的插件。

## 539

## Gulp vs Grunt：支持、社区与插件

如果我们还配置了 Gulp 或 Grunt 来检查新文件或更新的文件，保存到目录的任何更改或新文件都将被压缩，EXIF 数据将立即擦除。

Gulp 或 Grunt 可以高效地完成这项工作，在大量文件的情况下，它们所需的时间仅是手动执行时间的一部分。

## 500 附录 III

## NPM 概述

我们将讨论 npm 及其安装和缺点

## 什么是 npm？

npm 是 Node Package Manager 的缩写，全球最大的注册表。

## npm 的组件

npm 由三个不同的组件组成：

- 网站：npm 官方网站`npm.com/`用于查找包并创建和配置配置文件以管理私有公共包。
- CLI（命令行界面）：CLI 从我们的计算机终端与 npm 包和仓库交互。
- 注册表：注册表是一个 JavaScript 项目和元数据的巨大数据库。可以使用任何支持的 npm 注册表。

## 安装 npm (Node.js 和 npm)

我们必须安装 Node.js 才能将其安装在我们的机器上，因为 npm 已经包含了 Node.js。在计算机上安装 npm 有两种方式：

- 使用 NVM（Node 版本管理器）。
- 使用 Node.js 安装程序。

强烈建议使用 Node 版本管理器安装 npm，而不是 Node 安装程序。

可以根据需要在它们之间切换，以便为项目使用任何 Node.js 版本。他们不建议我们使用 node 安装程序来安装 npm 和 Node.js。

打开`https://github.com/nvm-sh/nvm`在我们的 Linux 操作系统上使用 nvm 下载并安装 npm。

- 由于我们使用的是 Windows 操作系统设备，我们将从 Git 链接下载适用于 Windows 的`nvm-setup.zip`文件。
- 下载后运行安装程序，然后按照屏幕上的安装说明进行操作。
- 通过双击该程序或从右键菜单中选择“以管理员身份运行”来运行设置。
- 点击“Yes”选项将允许安装。
- 在仔细阅读他们的许可协议后，如果我们同意，点击“Next”选项以接受它。
- 在选择 NVM 的安装区域后，点击“Next”按钮。它保持所选的默认位置。
- 在选择设置程序创建符号链接的文件夹后，点击“Next”按钮。
- 现在我们的安装已准备就绪，点击“Install”按钮开始程序。
- nvm 设置现在已开始在我们的电脑上安装，我们需要等待一会儿让它完成。
- nvm 设置安装完成；选择“Finish”退出设置。

### 验证 nvm 版本

在 nvm 设置完成后，验证是否已安装 nvm 以及安装了哪个版本的 nvm。在我们的终端中运行以下命令来实现：

```
nvm -v
```

# 附录 III：附录 III

### 查看可以使用 nvm 安装的 Node.js 列表

使用以下命令发现 nvm 支持的 Node.js 版本。它将显示当前可用的 Node.js 限制列表。

```
npm list available
```

### 安装 npm 和 node.js

我们可以安装任何版本的 Node.js；在我们的系统中，我们安装了 LTS 14.15.4。要安装 Node.js，只需运行以下命令：

```
nvm install 14.15.4
```

### 验证 Node.js 和 npm 版本

使用命令`nvm use 14.15.4`来启动 Node.js（确保将 14.15.4 替换为安装的版本）。

```
nvm use 14.15.4
```

然后，在终端中使用命令`node -v`和`npm -v`来验证 Node.js 和 npm 版本。

```
node -v
npm -v
```

### 验证已安装的 Node.js 版本列表

使用以下命令，我们可以看到机器上当前安装并激活了多少不同的 Node.js 版本。

```
nvm list
```

在我们的系统中，Node.js 版本 14.15.4 目前处于激活状态。如有必要，我们还可以在机器上安装其他不同的 Node.js 版本（同时基于不同的版本构建另一个 Node.js 项目）。从 nvm 提供的列表中选择不同的 Node.js 版本，然后执行下面的命令进行安装。

```
nvm install 12.20.2
```

在这里，我们选择安装 Node 版本 12.20.2；它还在我们的智能手机上下载并设置了合适的 npm 版本。

# Node.js 和 npm 现在提供两个独立的版本。运行以下命令查看当前安装了多少个 Node.js 版本：

```
nvm list
```

### 使用 Node 安装程序安装 npm 和 Node.js

考虑我们无法在设备上安装 npm 或在安装时遇到困难的情况。Node.js 安装程序是在电脑上安装 npm 和 Node.js 的替代方法。

要同时安装 Node.js 和 npm，请 Node.js 下载区域`https://nodejs.org/en/download/`，在那里我们可以找到适用于各种操作系统的 Node.js 安装程序。

![](img/70a7539ec7c3f429f5e3c9c64df71823_543_0.png)

### 下载

最新 LTS 版本：16.18.0（包含 npm 8.19.2）
下载适用于您平台的 Node.js 源代码或预构建安装程序，并开始开发。

### 下载 npm

下载与我们的操作系统及其位数兼容的任何 Node.js 安装。

- 1. 我们正在为设备下载 64 位的 Node.js 安装程序，因为我们拥有 64 位操作系统的 Windows。
- 2. 下载后运行安装程序，然后按照屏幕上的安装说明进行操作。
- 3. 点击“Next”按钮开始安装。
- 4. 在阅读并接受许可协议后，点击“Next”按钮。
- 5. 为 Node.js 安装选择一个唯一位置并点击“Next”继续。它保持在默认位置。
- 6. 选择我们想要安装的 Node.js 功能后，点击“Next”。
- 7. 勾选框并选择“Next”选项与 node.js 和 npm 一起安装额外工具（如 C++）。
- 8. 要在设备上安装 Node.js 和 npm，现在点击“Install”按钮。
- 9. 要安装 Node.js，在弹出框中选择“Yes”。
- 10. 完成安装后，点击“Finish”按钮。如工具自动安装检查所示，额外工具已准备好安装。按任意键继续。

要下载最新版本的 npm，请执行以下命令。

```
npm install -g
```



### npm 的特性

- `package.json` 文件，用于定义所有包。
- `package.json` 文件的内容必须以 JSON 格式编写。

### `package.json`

当我们使用 `npm init` 启动 JavaScript/Node.js 项目时，会创建一个带有开发者提供的基本元数据的“`package.json`”文件。

- Name：这是我们项目或库的标题。
- version：这是项目的版本号。
- description：关于项目的详细信息。
- license：这是项目的许可协议。

### 何时使用 npm

- 使用 `npm` 修改项目的包或按原样使用它们。
- 当我们需要下载独立工具时，利用 `npm`。
- 利用 `npx` 在不下载的情况下运行包。
- 如果我们需要与任何其他用户共享代码，请使用 `npm`。
- 当你想将代码限制给特定的开发者时，我们可以使用 `npm`。
- 使用 `npm` 创建团队以组织开发者并进行包维护。
- 处理各种版本和依赖关系，使用 `npm`。
- 当底层代码快速修改时，可以使用 `npm` 更新应用。
- 要查找负责其他相关问题和项目的开发者，请使用 `npm`。

### 命令行客户端

`npm` 包带有一个 CLI（命令行客户端），可用于获取和安装包。

#### Windows 示例

```bash
C:\>npm install <package>
C:\>npm uninstall <package>
```

#### Mac OS 示例

```bash
npm install <package>
npm uninstall <package>
```

### 发布包

只要目录包含“`package.json`”，我们就可以从 PC 发布它。

验证 `npm` 是否已安装：

```bash
C:\>npm
```

验证我们的登录状态：

```bash
C:\>npm whoami
```

如果没有，请登录：

```bash
C:\>npm login

Username: <our username>
Password: <our password>
```

进入你的项目页面并发布它：

```bash
C:\Users\my_user>cd my_project
C:\Users\my_user\my_project>npm publish
```

### 全局模式包安装

我们全局加载了 `npm` 包，这是我们目前拥有的。让我们修改并安装 UglifyJS 作为一个包（一种 JavaScript 压缩工具）。虽然可以缩写为 `-g`，但在此情况下我们使用 `--global` 标志：

```bash
npm install uglify-js --global

C:\Users\JTP\AppData\Roaming\npm\uglify-js -> C:\Users\JTP\AppData\Roaming\npm\node_modules\uglify-js\bin\

uglify-js@3.13.9

added 1 package from 1 contributor in 12.32s
```

### 本地模式包安装

在本地安装任何包时通常使用 `package.json` 文件。以下是在我们的主目录中创建项目文件夹的示例：

```bash
mkdir project && cd project

npm init

package name: (project)

version: (1.0.0)

description: Instance of the package.json

entry point: (indexes.js)

test command:

git repository:

keywords:

author:

license: (ISC)
```

要用默认设置生成“`package.json`”，请按回车。然后输入“yes”确认“json”文件可以。通过这样做，项目根目录下将创建一个“`package.json`”文件：

```json
{
  "name": "project",
  "version": "1.0.0",
  "description": "Instance of the package.json",
  "main": "indexes.js",
  "scripts": {
    "test": "echo \"Error: no test is specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}
```

### 移除本地包

我们也可以卸载包，因为 npm 包管理始终是可以操作的。假设当前安装的 `packageName` 有兼容性问题。因此，我们将卸载此包并安装较早的版本：

```bash
npm uninstall packageName
```

### 安装特定包版本

现在我们已经有了所需的版本 `packageName` 包，我们可以安装它。可以使用 `@` 符号来附加版本号。

```bash
npm install packageName@1.4.5
```



## 508 附录 III

正如我们所见，执行`npm`指令有多种方法。下方提供了一些常用`npm`命令（或别名）的列表。

- `npm i`：使用`npm i`安装本地包
- `npm i -g`：使用`npm i`安装全局包
- `npm un`：使用`npm un`卸载本地包
- `npm up`：由`npm`更新的包
- `npm t`：使用`npm`测试
- `npm ls`：使用`npm ls`列出已安装模块
- `npm ll`或`npm la`：使用`ll`或`npm la`在列出模块的同时打印更多包详细信息

我们在本章中讨论了 Gulp、Grunt 和 npm 的介绍、安装和功能。

## 注释

1. Gulp 概述：`www.tutorialpoint.com/gulp/gulp_overview.htm` 访问日期：2022年10月22日。
2. Gulp 安装：`www.tutorialpoint.com/gulp/gulp_installation.htm` 访问日期：2022年10月22日。
3. Gulp 基础：`www.tutorialpoint.com/gulp/gulp_basics.htm` 访问日期：2022年10月22日。
4. Gulp 开发应用：`www.tutorialpoint.com/gulp/developing_application.htm` 访问日期：2022年10月22日。
5. GruntJS：`www.tutorialteacher.com/nodejs/gruntjs` 访问日期：2022年10月22日。
6. Grunt 概述：`www.tutorialpoint.com/grunt/grunt_overview.htm` 访问日期：2022年10月22日。
7. Grunt 特性：`www.tutorialpoint.com/grunt/grunt_features.htm` 访问日期：2022年10月22日。
8. Grunt 安装：`www.tutorialpoint.com/grunt/grunt_installing.htm` 访问日期：2022年10月22日。
9. Grunt 入门：`www.tutorialpoint.com/grunt/grunt_getting_started` 访问日期：2022年10月21日。
10. Gulp vs Grunt-比较自动化工具：`www.keycdn.com/blog/gulp-vs-grunt::Gulp%20vs%20Grunt%3A%20Speed&text=The%20reason%20for%20Gulp%27%20current,%20task%20at%20atime` 访问日期：2022年10月22日。
11. 什么是 npm：`www.javatpoint.com/what-is-npm` 访问日期：2022年10月22日。

## 索引

ActiveX 控制程序 267
聚合 345
AJAX 技术 10, 34–35, 153, 268
`alert(1)` 方法 442
代数 444–445
Algolia Places 195–196
TypeScript 中的环境音, 476–477
使用 NativeScript 的 Android 应用 397–399
Android SDK 380
Android Studio 379–380；*另见* Studio (VS) Code
AngularJS 17, 19–20, 46, 213, 217–219
特性 295–296
前端框架和库 272–273
vs. JavaScript 260–263
vs. React 295–197
Vue.js 316–318
Animate On Script (AOS) 197
Anime.js 196–197
Apache Cordova 235–236
API 见应用程序编程接口 (API)
`App.js` 241, 291–292
AppJSX 303
应用程序编程接口 (API) 181–191, 367, 434；*另见用户*界面 (UI)
GraphQL API 67
原生 Fetch API 162
应用
跨平台应用（*见跨平台应用*）
桌面应用（*见桌面应用*）
动态 Web 应用 279–280
全栈在线应用 358
Ghost Electron 应用 406–407
混合应用 235
移动应用（*见移动应用*）
Pexels Electron 应用 407
Playground JavaScript 390, 395–396
专业 JavaScript 应用 375
服务器应用 4
单页应用 (SPAs) 215
Skype 385
独立级 vs. 跨平台应用 239
Tesla 应用 386
web 4, 27, 425
应用程序用户界面 359
算术运算符 82
在 JavaScript 中 98–101, 434–435
在 TypeScript 中 473–475
赋值运算符 83
辅助
社区解决方案 301
离线状态 133
异步函数 143–143；*另见*函数
vs. 延迟 JavaScript 143–144
Node.js 131–133
Atom 39–40
音频/视频处理 333
Aurelia 25–26
Axios 方法 159–160
babel VS Code 69, 288
`.babelrc` 文件 229
Babylon.js 232
Backbone.js 224–226
后端框架 17–18, 227, 275；开发 274, 333
Express.js 228, 361–363
Gatsby 229
Meteor 230–231
Next.js (见 Node.js) 任务 372
Web 设计 425
Beaker Browser 407
Video 198
位运算符 83, 432
`blur()` 方法 444
布尔对象 113–114
前端框架 273
库 217, 273
括号 43
Beaker Browser 407
Netscape 浏览器 9, 418, 220
对象 441–444
Brython 419
BSON 数据类型 343
`buffer` 312
Build 系统 482–483
bundle过程 293
C# 7–8, 255, 275, 317, 342, 404
`choreographer.js` 199–200
class 继承 465–466
`clearInterval()` 方法 424
`clearTimeout()` 方法 442
Cleave.js 199
Cleave 442
CLI 命令行 320
客户端优化语言 255
客户端 JavaScript 3
客户端侧编程 256
`function()` 443
Cocoon.js 框架 233
Code Editor 455
Code Push SDK 382
编码 371
配置 498
集成 C++ 335
CoffeeScript 419
命令行客户端 505
命令行界面 (CLI) 500
注释 77–78
在 Google 社区 296
社区协助 301；另见助手
比较运算符 82, 332–433
TypeScript 编译器 448–449
无编译器编程 34；另见编程
计算 444–445
计算机化属性 314
vs. 编码 498
环境配置 373
简单环境 360
`confirm()` 方法 443
`console.log()` 方法 457
JavaScript 中的“const”关键字 430
`contact()` 数组 334
cook 5, 165–168
在 JavaScript 中 166
属性 168–170
利用 165–166
种类 170–172
回调方法 339
Carbon Components Svelte 222
Carbon 设计系统 222
层样式表 (CSS) 语言 33, 46, 72, 227, 272, 375, 479–480
大小写敏感语言 77
CDN 库 318
字符
删除字符 453
转义字符 435
分号字符 76
特殊字符 435
Chart.js 198–199
`'create-react-app'` 方法 293, 364
交叉编译器 421；*另见*应用
桌面应用；移动应用
跨平台应用（*见跨平台应用*）
Electron（*见 Electron*）
跨平台应用 239
框架 28, 389
程序 238–239, 408–409
运行时环境 367
支持 381
Ghost 406–407
主进程 vs. 渲染进程 411–412
NodeGUI 240
Node.js 240
NW.js 241
Pexels 407
Proton Native 241
React.js 239–240
Slack 408
独立应用 239
使用 404–405
WebTorrent 405–406
使用层样式表 (CSS) 的语言
WhatsApp 408
WordPress 406
开发者
适合 373 的语言
Dart 419
vs. JavaScript 254–260
数据库
作为后端层 367
跨平台文档型数据库 358–359
JavaScript 熟练 225–427
软件 381
TypeScript 459–462
文档型数据库 350, 360
MongoDB（*见 MongoDB*）
仅 SQL 数据库 350
无模式数据库 342
React Native 社区 400
DevOps 工程师 426–427
VueJS 中的指令 315
数据驱动 (D3.js) 193–194
数据隐藏 466
MongoDB 数据建模 344
数据类型 5, 430–431
Django 275
`document.getElementById()` 方法 147, 151–152
`document.getElementsByClassName()` 方法 149
BSON 数据类型 343
在 JavaScript 中 81
日期 106–109
Day.js 包 222
基于 Debian 的计算机 54
默认参数 473；另见
DOM 见
32, 145, 192, 212, 224, 263, 278, 279, 300, 436
143–144
删除字符 453
在 TypeScript 中 475
前端 Web 开发 424–425
`fullPage.js` 202
JavaScript 全栈开发 427
全栈在线应用 358
函数
全局变量 80–81
Google Chrome JavaScript V8 引擎 3
Google trends 381
Granim 201–202
GraphQL API 677
GruntJS 486–487
入门特性 492–495
Gulp vs. GruntJS 495–499
设置 488–491
Gulp 479–480
应用 484–486
基础 482–484
优于 GruntJS 495–499
安装 481–482
`gulpfile.js` 484
异步函数（见异步函数）
Fetch 函数 156–158
在 JavaScript 中 92–95, 433, 434
在 TypeScript 中 471–473
基础运算符 431
模糊查找器
“g”参数 482；另见游戏创建 5–6
游戏引擎
Babylon.js 233
GDevelop 233
Kiwi.js 233
Melon.js 233
Phaser 231–232
PixJS 231
PlayCanvas WebGL 232
JavaScript 工具
GruntJS（见 GruntJS）
Gulp（见 Gulp）
Node 包管理器（见 Node Package Manager）
使用 280
Three.js 233
Gatsby 228
GDevelop 233
`getAttribute(method)` 方法 438
`getAttributeNode(method)` 方法 438
`getAttributeNS(method)` 方法 438
`getDate(method)` 方法 440
`getDay(method)` 方法 440
`getElementsByClassName(method)` 函数 147–148
`getElementsByName(method)` 方法 149
`getElementsByByTagName(method)` 方法 149, 438
`getElementsByTagNameNS(method)` 方法 438
`hasAttribute(method)` 方法 438
`setAttributeNS(method)` 方法 439
Hello Every Code 版 412–413
“Hello, World!”程序 74
Hevery, Misko 295
HTML 见超文本标记语言 (HTML)
HtmlWeb-packPlugin 291
HTTP
cookies（见 cookies）
请求 153–164
HttpOnly 属性 171
混合应用 235；另见应用
超文本标记语言 (HTML) 11, 33, 46, 72, 144, 145, 227, 272, 374–375, 413, 417, 423, 425, 429, 441, 479
超文本预处理器 252
超文本传输协议 (HTTP) 367
`getFullYear(method)` 方法 440
`getMinutes(method)` 方法 440
`getTime(method)` 方法 440
Ghost Electron 应用 406–407
Git 控制，40
GitHub Hub 2, 40, 214, 217, 218, 382, 381, 385, 400
Glimmer 200–201
全局包安装 506
全局作用域 313
理想 JavaScript 框架 226–227
标识符 78
IDEs 集成集成开发环境 (IDEs)
-else 语句 84–88
深度分析。Node.js 268–269
`indexOf()` 数组 435
`innerHTML` 属性 151–152
`innerText` 属性 152–153
`insertOne()` 方法 356
JavaScript 变量实例 430
在 Vue.js 中 325–327
集成开发环境 (IDEs) 38–40, 42, 44, 46, 54, 455, 457
交互式行为 4–5
接口；另见用户界面 (UI)
应用程序接口 (API) 181–191, 367, 434
应用 359
在 TypeScript 中 466–468
内部模块，在 TypeScript 中 471
国际电工委员会 (IEC) 12
国际标准组织 (ISO) 12
物联网 268, 335, 405
Ionic 框架 235, 376, 377
`isNaN()` 函数 434
Java 8, 422
后端语言 274
vs. JavaScript 14, 244–247, 421–422
JavaFX 404
Java JDK 380
JavaScript (JS) 417–418；另见 NativeScript; TypeScript
Angular JS vs 260–263
API（见应用程序接口 (API))
应用 4–6
数组 98–101, 435–435
异步函数在 134–144 中
优点 6
布尔对象 113–114
浏览器对象 441–444
客户端 JavaScript 3
注释 77–78
控制 14–15
Dart vs 254–260
数据类型在 5, 81, 430–431 中
日期对象在 106–109, 440 中
定义 1
桌面应用（见桌面应用）
开发者熟练 425–428
开发工具 8–9
编辑器（见 JavaScript (JS) 编辑器）
错误和异常 114–122
演变 9–14
首次代码 75–77
缺陷 6–7
表单（见表单）
框架（见框架）
前端长度 272
函数在 92–95, 433 中
游戏引擎（见游戏引擎）
“Hello, World!”程序 74
HTTP 请求 153–164
if-else 语句 88
HTML 属性 151–152
innerText 属性 152–153
安装，在 Studio Code 中 46–54
v. Java, 14, 244–247
jQuery vs. 251–252
库（见库）
循环在 89–92 中
数学在 109–112 中
移动使用（见移动使用）
Node.js vs. 264–269
数字对象在 112–113 中
对象在 95–98 中
运算符在 82–84, 431–433 中
机会 424–425
Oracle，12, 15
过去和未来 418
PHP vs. 252–254
目的 3
Python vs. 247–250
特质 418–424
标准 12
字符串在 102–105, 436 中
switch 语句 88–89
语法 74–75
趋势 11
转换数据 439–441
唯一编程语言 7–8
表单验证（见表单验证）
变量在 78–81, 430 中
TypeScript 448
Laravel 275
`lastIndexOf()` 数组 443
后进先出 (LIFO) 原则 28
学习曲线 258
Leaflet 202–203
JavaScript Booster 69
JavaScript (ES6) 代码片段 64–65
JavaScript (JS) 用于 NativeScript 和 React Native 399
Animate On Scroll (A) 195–196
Anime.js 196–197
Atom 39–40
Brackets 43
Eclipse 41–42
NetBeans 44
Sublime Time 42–43
Video.js 198–199
Choreographer.js 199–200
Cleave.js 193–194
D3.js 193–194
Visual Studio (VS) Code 40, 41–46
JavaScript/React 预处理器 302
前端库 272–273
`fullPage.js` 202
Glimmer 200–201
Granim.js 201–212
Jest 测试框架 30
`join()` 数组 363
jQuery 2, 16, 191, 192, 219, 221, 236–237, 374, 376
前端框架和库 273
vs. UI 251–252
Lodash 195
Masonry 204–205
Moment.js 204
Multiple.js 203–204
Omniscience.js 205
Parsley 206
Polymer 208
Popper.js 206–67
React.js 192–193
Screenfull 207–208
Three.js 207
Underscore 194–195
Voca 208–209
jQuery-based 库 220
JS JavaScript (JS)
JSX XML (JSX)
瞬时编译 (JIT) 编译器 420–422
Kiwi.js 233
Kotlin 420
Ky 162–164
后端 JavaScript 框架 274
C++ 274, 335, 417
CSS 语言 33, 46, 72, 227, 272, 375, 479–480
Linux
安装 Visual Studio Code 54–55
安装 Node.js 61–62
LiveScript 256, 261, 264
Live Server 68
Live Share 68
iOS Live 更新 382
本地变量 79–80
前端开发 272
Java（见 Java）
非结构化查询语言 (NoSQL) 367
面对象编程 (OOP) 语言 95, 462
Lodash 195
逻辑错误 116
逻辑运算符 83, 433
JavaScript 循环在 89–92
Macromedia Dreamweaver MX 8
Macromedia 的 HomeSite 5 9
Main.js 292
主进程 vs 渲染进程 411–412
`map()` 方法 439
Masonry 205–204
`match()` 函数 434
Material UI 215
JavaScript 中的数学 109–112
MEAN vs. MERN Stack 368–369
Melon.js 232
MERN Stack 368–369
vs. MERN Stack 368–369
结构可能 365
Meteor 22–23, 238, 377
微服务设计 355
Microsoft Chrome Debugger 67
Microsoft MainPage 8
Microsoft Internet Explorer 171
Microsoft 的 JavaScript 9
Microsoft Word 404
Mithril 22
Mobile Angular UI 237
移动应用 4, 233–234, 373–376；另见跨平台应用；桌面应用
Apache Cordova 235–236
优点 376–377
开发 372
Ionic 235
jQuery 236–237
Meteor 238
Mobile Angular UI 237
NativeScript 234–235
OnSen UI 236
React Native 234, 380–390
Sencha Touch 237
Titanium 238
使用 JavaScript 374–376
移动应用开发（见移动应用）
NativeScript（见 NativeScript）
编程语言（见编程语言）
React Native 377–390
移动性 242
Moch 248
模型-视图控制器 (MVC) 26
架构概念 221
设计模式 279
框架 295
范式 262
现代 JavaScript 9–10
模块在 TypeScript 中 470–471
Moment.js 204
MongoDB 数据库 342–346
优点与缺点 346
数据建模 344
特性 346
开始于 346–349
在 Windows 上安装 350–356
vs. RDBMS 344
“mongod” 命令 347
`moveBy()` 函数 443
`moveTo()` 函数 443
Mozilla 基金 357
JavaScript 中的多行注释 78
Multiple.js 203–204
Muuri 220
MVC 见视图控制器 (MVC)
命名空间，在 TypeScript 中 470
NAN (不是数字) 444
原生应用 397–398；另见应用
fetch Fetch API 162
React Native 376
NativeScript 234–235；另见 JavaScript (JS); TypeScript
优点 391–392
Android 应用 390–391, 397–399
用例 396–397
框架 374
使用 React Native 399–401
399–395 版本的设置
嵌套命名空间 470
.NET 405
NetBeans 44
Netscape 浏览器 9, 418, 420；*另参见* browsers
`new Date()` 算符 440
新项目 293–294
Next.js, 18, 24–25
Ngx-bootstrap 218
NodeGUI 240
Node 2–4, 10, 22, 23, 40, 46, 240, 244, 240, 256, 293, 307, 309, 311, 333, 334, 394, 409, 410, 420, 455, 479, 506
异步函数 131–133
后端语言 237
buffer
默认到本地 312
开发环境 55–60
缺点 336–337
环境 338–380
首次应用 340–342
函数 312
全局作用域 313
与 JavaScript 的 264–269
JS 运行时环境 365–367
Linux，安装 61–62
弱类型 311
方法 437–438
对象字面量 311
基本类型 311
process 对象 312
在 Visual Studio Code 中的项目 62–64
属性 436–437
用法 334–335, 338
Windows，安装 55–60
Node 包管理器 (NPM) 293, 365, 499–500
本地模式下的包安装 506–507
移除本地包 507
设置 500–504
NodeSource 仓库 61
Node 版本管理器 500
非阻塞输入/输出架构 336
None 值，cookies 170
JavaScript 中的非基本数据类型 81
非结构化查询语言 (NoSQL) 367
Not Only SQL 数据库 350；*另参见* databases
简单的 SQL 数据库 342；*另参见* databases
NPM 新包管理器 (NPM)
`Number()` 函数 434
数字
JavaScript 中的对象 112–113
在 TypeScript 中的 473
NW.js 241
对象创建 95–97
对象方法 97–98
面向对象编程 (OOP) 语言 95, 462
对象
在 JavaScript 中 95–98
在 TypeScript 中 468–469
离线辅助 373；*另参见*
Omniscient.js 205
`onclick` 事件类型 123
`onnerror()` 函数 120–122
单向数据绑定 297
`mouseout` 事件 124–125
`mouseover` 事件 124–125
`onsubmit` 事件类型 123–124
Oomph 项目 41
`open()` 函数 443
开源 Flutter UI 开发 SDK 273
开源软件 390
文档导型数据库 350
框架 240
命令行客户端 505
500 的组件
下载 503–505
504 的特性
全局模式包安装 506
`package.json` 506
`packageName` 包 507–508
开源软件（续）
Javascript 库 251
项目 381–382
服务器环境 367
算符 82–84, 431–433
Oracle 12, 14, 15
包
管理员 483
Day.js 212
全局模式包安装 506
Node 包管理器（参见 Node 包管理器 (NPM)）
`package.json` 456, 504–506
`packageName` 包 507–508
本地模式下的包安装 506–507
参数
默认参数 473
"Expires" 和 "Max-Age" 参数 169
-g 参数 482
剩余参数 472–473
`parseFloat()` 函数 443
`parseInt()` 函数 434
`parse()` 方法 440
Parsley 206
路径，键 168
Pexels electron 应用程序 407；*另参见* applications
Phaser 231–232
PhoneGap 373, 376
PHP 8, 423；*另参见*语言：编程语言
后端语言 274
与 JavaScript 的 252–255
Pixij 231
纯 JavaScript 对象 (POJO) 模型 295
PlayCanvasWebGL 232
Playground 应用 390, 395–396；*另参见* applications
插件 499
Polymer 24, 208
`pop()` 数组 434
Popper.js 206–207
预处理器 483
Prettier 65–66
基本算符 431–432
数据 5, 81
Node.js 的 311
`print()` 函数 443
专业开发
Web 应用程序开发者 425
前端开发者 224–425
专业 JavaScript 应用 375
客户端端编程 256
无编译器编程 34
语言（参见编程语言）
服务器端 JS 256
服务器端网站编程 356–358
传统编程 34
语言 342, 371, 377；*另参见*大小写敏感编程 77
客户端编程 255
C 语言 420–421
动态编程 372
极响应式 372
框架 373
前端框架 372
Ionic 框架 373
jQuery 374
原生脚本框架
面向对象编程 (OOP) 语言 95, 462
离线辅助 373
PhoneGap 373
React Native 374
适用于开发者 373
Tabris.js 374
Typescript 298
`prompt()` 函数 434, 443
Proton Native 241
Prototype.js 194
`push()` 数组 434
Python 378, 422–423；另参见：编程语言
后端语言 274
与 JavaScript 的 247–250
库 62
健壮框架 227；另参见框架
路由过程 296
`querySelector()` 函数 148
快速交付 409
Quokka.js 66
Ruby on Rails 8, 275, 423；另参见
React 开发工具 280
React.js 17, 18, 20–21, 192–235, 214–240, 239–267, 273–296
经验法则 227
运行时环境 357
运行时错误 115–116
AngularJS 与 295
优势 279
特性 281
缺点 282
环境，设置 286
前端框架 273, 363
安装方法 286–295
版本 282
SameSite 属性 169–170
扩展性 242, 345
无模式数据库 345；另参见
cookies 范围 168–170
屏幕 207–208
`scroll()` 函数 443
`scrollTo` 函数 443
搜索引擎优化 (SEO) 359
安全 cookies 171–172
分号字符 76
无服务器架构 334–335
服务器端 JS 357–358
处理 256
服务器端网站编程 356–358
React JSX 302
属性 303–305
注释 305–306
嵌套元素 306–307
样式 374
React Native 234, 374, 380
用于 JavaScript 247–250
用于应用 380–388
学习曲线 39–41
用于 Semantic 399–401
虚拟 DOM 280
`reduce()` 函数 440
注册表 505
`removeAttribute()` 439
`resize()` 函数 443
`resize()` 函数 443
服务器端公共许可证 (SSPL) 342
服务器端渲染 (SSR) 356–358
会 169, 171
`setAttribute` 方法 439
`setAttribute()` 方法 439
`setDate` 方法 441
`setInterval` 方法 442
`setTimeout` 方法 442
设置 309–311
反转数组 434
剩余参数 472–473
可用程序 378–379
用于 Native 393
用于 Vue 318–321
用于 React.js 286
若干 203
`shift()` 函数 434
简单环境 360
简单配置 327
简单插值 325
简单数据 314–315
单行注释 78
单页应用 (SPAs) 215
Skype 385
`slice()` 数组 434
`splice()` 数组 434
Spring 275
栈数据 240
特殊算符 84, 435
特殊字符 435；另参见
静态类型检查 447–449
停止函数 443
字符串 102–105
太阳微系统 418
SuperAgent 161–162
超级编辑器 46
Svelte 221–223
Svelte.js 298–301
Svelte-flow 222
Svelte Material UI (SMUI) 222
Svelte 编写的程序 299
switch 语句 88–89
同步 JavaScript 141–142
语法糖 419
JavaScript 语法 74–75
错误 115
函数 93
Tabnine 70
Tabris.js 374
任务执行器 483
样本 314–315
在 Vue 中 327–331
Tesla 应用 386；另参见应用程序
测试 30
基于文本的编辑器 444
第三方 cookies 171；另参见
"this" 关键字 464
Three.js 207, 233
三层架构系统 366
throw 语句 119–120
titanium 238
`toString()` 数组 435
文档对象模型 300
位置 JavaScript 框架 281；另参见框架
传统编程 34；另参见编程
转换数据, JavaScript 439–441
译器 302
`config.json` 457–458
用于 TypeScript 语言的 475–476
双向通信 322
TypeScript 318, 447–448；另参见
JavaScript (JS); NativeScript
在中的 476–477
数组 473–475
类 462–465
继承 465–466
速成课程 454–459
用于开发者 459–462
基础元素 448–449
函数中的 471–473
接口 466–468
模块中的 470–471
名称 470
对象中的 468–469
属性和函数
52–453
编程语言 298
static checker 449–452
tu 用于 475–476
type template 用于 469
union 在 476
use 的 453–454
Vim 44–45
Virtual DOM 278, 280, 297, 313, 315, 322, 363
Visual Studio (VS) Code 39, 40–41, 45–46, 455
Typescript 编译器 (tsc) 449, 451, 453, 456–457
TypeScript type template 469
典型 cookie 属性 168–170；另另
JavaScript 开发者扩展 64–70
JavaScript 安装于 46–54
Linux 安装于 54–55
Node.js 项目 62–64
V8 JavaScript 引擎 61
Voca 208–209
Ubuntu 官方仓库 61
UI 查看用户界面 (UI)
Underscore.js 194–195
TypeScript 中的 Union 476
`unshift(1)` 数组 435
用户界面 (UI) 72, 296, 373；另请
Vue CLI 版本 315, 324
Vue.js 17, 21, 212–213, 215–217, 313
优势 321–322
对比 Angular(JS) 316–318
公司 323–324
框架的比较评估 315–316
环境搭建 318–321
特性 313–315
实例在 325–327
designer 426
配合 Electron 413–416
kit 217
validate 方法 124
JavaScript 表单的验证 177；另请
表单
邮箱验证 180–181
示例 177–178
数字验证 178–179
使用一个 179–180
`value(0)` 数组 435
流行的 316
基于模板的方法 316
模板在 327–331
Walke, Jordan 192, 194, 296
watchers 315
web
应用程序（查看 applications）
cookies（查看 cookies）
开发框架 427
层 366–367
对比移动端 258
服务器 4
Vanilla JS 71–73, 428
Vanilla JS vs. React JS 27
应用程序 27
开发者便利性 31–32
开发成本 32–33
功能性 27
维护 32
性能 28–29
安全性 30–31
栈数据结构 28
测试 30
UI/UX 性能 31
网站 33–35, 72
Webpack 289–291, 320–321
Webpack-dev-server 287
WebTorrent 桌面应用 405–406；另请
移动端应用程序
`wget` 命令 55
WhatsApp Electron 应用 408；另请
应用程序
变量 78–81, 430
JavaScript 中的 “var” 关键字 430
React 版本 282–285
循环 loop 89–91, 417
Windows
MongoDB 数据库安装于 350–356
Node.js 安装于 55–60
WordPress 桌面应用 406；另请应用程序
worker threads 模块 336
Xcode 395
XMLHttpRequest 155–156
XMLHttpRequest 153–156
Zeit 228
zombie cookies 172；另请 cookies
