
注意，在第 1 行中，声明了 HTML5 文档对象模型（DOM），指示浏览器在第 2 行使用 HTML5 文档起始标签，使用默认命名空间声明属性 `xmlns`，并将 XHTML 命名空间 URI `http://www.w3.org/1999/xhtml` 声明为默认命名空间，以确保浏览器和其他工具以及所有未限定的元素（如 `html`、`head`、`body` 等）都来自 XHTML 命名空间。

此外，在 `html` 起始标签中，我们同时使用 `xml:lang` 和 HTML 属性为所有元素的文本内容指定（默认）`lang`（这里使用 `"en"` 表示英语）。这种属性重复是为了获得一个可以被 HTML 和 XML 工具处理的混合文档而付出的微小代价。

最后，在第 4 行，使用带有 `charset` 属性的（空）`meta` 元素，将 HTML 文档的字符编码设置为 UTF-8，这也是 XML 文档的默认设置。

### 1.2.6 HTML 表单

对于用户交互应用程序，网络浏览器需要渲染用户界面（UI）。软件应用程序 UI 的传统比喻是表单。用于数据输入、数据输出和用户操作的特殊元素称为表控件或 UI 组件。在 HTML 中，表单元素是网页的一部分，由块级元素组成，包含表控件以及这些控件的标签。

用户通过在输入字段中输入文本来完成表单，包括下拉选择列表、单选按钮组和复选框组。完成后的表单通过提交按钮提交。当用户提交表单时，通常通过 GET 方法或 HTTP POST 方法发送到网络服务器。提交的标准编码称为 URL 编码。它由 HTML 媒体类型 `application/x-www-form-urlencoded` 表示。在这种编码中，空格变成加号，任何其他保留字符变成如 RFC 1738 中定义的百分号和十六进制数字。

## 1.3 Web 应用程序基础快速概览

每个表控件都有一个初始值和一个当前值，两者都是字符串。初始值通过元素的 `value` 属性指定，但 `textarea` 元素的初始值由其初始内容给出。控件的当前值首先设置为初始值。之后，控件的当前值可以通过用户交互或脚本进行修改。当提交表单进行处理时，某些控件将它们的 `name` 与其当前值一起发送，这些键值对随表单一起提交。

标签通过在 `<label>` 中包含子元素（隐式标签）或通过为控件提供 `id`（显式标签）与控件关联。通常情况下，我们只需要四类：

- 使用 `<input />` 的单行字段
- 使用 `<output />` 的单行输出
- 使用 `<button>` 的推送按钮
- 使用 `<select>` 的下拉选择列表

隐式标签的 HTML 示例：

```html
<form id="Book">
  <p>ISBN: <output /></p>
  <p>Title: <input /></p>
  <p>Year: <input /></p>
  <button>Save</button>
</form>
```

在接口中，我们在模型类和表控件之间建立了映射。这种映射也称为数据绑定。通常，模型类的属性始终可以在用户界面中表示。然而，如果选择较少（例如少 8 个），可以使用单选组。可以使用类型的输入（例如 `type="date"`）或组件。

## 1.3 使用 CSS 网页文档和用户界面

虽然 HTML 用于定义网页内容的结构，但级联样式表（CSS）语言用于定义网页的演示样式，这意味着你使用它告诉浏览器你希望如何渲染 HTML（或 XML）：使用什么样的元素布局、字体和文本样式、颜色以及动画。

CSS 的第一个草案由 Håkon W. Lie 在 1994 年提出，他后来成为了浏览器供应商 Opera 的 CTO。官方的 CSS1 标准追溯到 1996 年 12 月，"大部分内容是 Håkon W. Lie 与 Bert Bos 在 1995 年在索菲-安蒂利斯的白板上敲定的"（正如他在一次采访中解释的那样）。

CSS 基于规则的形式，规则由选择器（选择规则适用的文档元素）和属性-值对列表（通过 CSS 属性如 `font` 或 `color` 来定义所选元素的样式）组成。在应用给定的 CSS 规则时，计算页面元素的 CSS 属性值有两个基本机制：继承和级联。

CSS 布局的基本元素是一个矩形，也称为"盒"，包含内部内容区域、可选的边框、可选的内边距（内容与边框之间）以及边框周围可选的外边距。这种结构由 CSS 盒模型定义。

我们书中不会深入研究 CSS，因为这里的重点是应用程序的逻辑和功能，而不是它的美观。

## 1.4 JavaScript – "Web 的汇编语言"

JavaScript 由 Brendan Eich13 在 1995 年 5 月于 Netscape14 工作期间仅用 10 天开发，作为其浏览器 Navigator 2 的 HTML 脚本语言（更多关于历史见15）。Brendan Eich 在 2015 年 4 月于旧金山的 O'Reilly Fluent 会议上表示："我写 JavaScript 时非常匆忙，我从未梦想过它会成为 Web 的汇编语言"。

JavaScript 是一种动态函数式面向对象的编程语言，可用于：

- 通过以下方式增强网页：
  - 生成特定浏览器的 HTML 内容或 CSS 样式，
  - 插入动态 HTML 内容，
  - 特殊的视听效果（动画）
- 通过以下方式增强 Web 用户界面：
  - 实现高级用户界面组件，
  - 在客户端验证用户输入，
  - 自动预填表单字段。
- 使用本地或远程数据存储16 实现前端 Web 应用。
- 实现用于分布式 Web 应用的前端组件，其远程数据由后端组件管理；后端组件是传统上用 PHP、Java 或 C# 等服务器语言编写的程序，但现在也可以用 NodeJS JavaScript JavaScript。
- 实现一个完整的分布式 Web 应用，其中前端和后端组件都是 JavaScript 程序。

目前浏览器完全支持的 JavaScript 版本称为 ECMAScript 5.1，或简称为"ES5"，但接下来两个版本"ES6"和"ES7"（或"ES 2015"和"ES 2016"）已经受到当前浏览器和后端 JS 环境部分支持。2017 年 5 月，ES6 在移动浏览器中已获得完全支持，但其重要的新模块概念除外。

### 1.4.1 作为面向对象语言的 JavaScript

JavaScript 是面向对象的，但与 Java 和 C++ 等经典面向对象编程语言不同。在 JavaScript 中，类与对象和函数不同，并不是等公民。相反，类必须通过遵循某些模式以特殊 JS 对象的形式来定义：可以是构造函数（可能使用 ES6 类声明的语法糖）或工厂对象。

13 http://en.wikipedia.org/wiki/Brendan_Eich

14 http://en.wikipedia.org/wiki/Netscape

15 http://www.w3.org/community/webed/wiki/A_Short_History_of_JavaScript

16 http://web-engineering.info/JsAndroidResource-Book

然而，也可以在不实例化类的情况下创建对象，在这种它们是无类型的，并且可以为特定对象定义属性和方法，而不依赖任何类定义。在运行时，可以向任何对象和类添加或删除属性和方法。JavaScript 的这种动态性允许强大的元编程，例如定义你自己的类和枚举（或其他数据类型）概念。

### 1.4.2 关于 JavaScript 的进一步阅读

良好的开放访问 JavaScript 书籍：

- *Speaking JavaScript17*，Axel Rauschmayer 博士著。
- *Eloquent JavaScript18*，Marijn Havereke 著。

## 1.5 Web 应用的访问性

为 Web 应用提供可访问性的推荐方法由可访问富交互应用程序（ARIA）标准定义。正如 Bryan Garaventa19 在其关于访问性特性20的文章中所总结的，交互式 Web 技术的可访问性有 3 个主要方面：1) 键盘可访问性，2) 屏幕阅读器可访问性，以及 3) 认知可访问性。

关于 ARIA 的进一步阅读：

1. 浏览器如何与屏幕阅读器交互，以及 ARIA 在其中的位置21，Bryan Garaventa 著
2. 可访问性树训练指南22，whatsock.com 著
3. ARIA 角色一致性矩阵23，whatsock.com 著
4. Mozilla 的 ARIA 概述文章26
5. W3C 的 ARIA 概述页面25

> 17 https://speakingjs.com/es5/index.html
> 18 https://elojavascript.net/
> 19 https://www.linkedin.com/profile/view?id=26751364&trk=groups-post-post-b
> 20 https://www.linkedin.com/grp/post/4512178-134539009
> 21 http://linkedin.in/que-Q08
> 22 https://whatsock.com/training
> 23 https://whatsock.com/training/matrices
> 24 https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA
> 25 https://www.w3.org/WAI/intro/aria.php

## 1.6 测验题

如果你想查找以下测验题的答案，可以查看我们的讨论论坛26。如果你在论坛中没有找到答案，可以发帖询问特定问题的答案。

### 1.6.1 问题 1：格式良好的 XML

下列片段中哪一个代表格式良好的 XML？选择一个或多个：

1. ▢`<em><<strong>>This is some text <b>and this is more text. Here is even more.</b></text></STRONG></em>`
2. ▢`<strong>This text is bold. <em>And this is italicized and bold.</em></<em></strong><em>emph`
3. ▢`<STRONG>This text is bold. <em>And this is italicized and bold.</em></STRONG> And this is just italics.em`
4. ▢`<strong>This text is bold. <em>and is italicized and bold.</em></EM>and is just italics.`

### 1.6.2 问题 2：HTML 表单

记住 HTML 表单是由包含控件和标签的块元素组成的 HTML 文档部分。下列元素代表正确的表单？选择一个或多个：

1.
```html
<form>
  <div><label>ISBN:</label><input name="isbn" /></div>
  <div><label>title:</label><input name="title" /></div>
</form>
```

2.
```html
<form>
  <div><label for="isbn">ISBN:</label><input id="isbn" name="isbn" />
  <label for="title">title:</label><input id="title" name="title" /></div>
</form>
```

3.
```html
<form>
  <label>ISBN:</label><input name="isbn" /></label>
  <label>Title:</label><input name="title" /></label>
</form>
```

4.
```html
<form>
  <div><label for="isbn">ISBN:</label><input name="isbn" /></div>
  <div><label>title:</label><input name="title" /></div>
</form>
```

5.
```html
<form>
  <div><label>ISBN:</label><input name="isbn" /></div>
  <div><label>Title:</label><input name="title" /></div>
</form>
```

# 2 关于 JavaScript 的更多

## 2.1 JavaScript 基础

在总结中，我们尝试考虑 Douglas Crockford² 关于 JavaScript 的重要点¹

### 2.1.1 类型和字面量

JavaScript 有三种原始类型：字符串、数字和布尔，我们可以借助 `typeof` 运算符测试变量是否持有此类类型的值，例如 `typeof === "number"`。

有五种引用类型：`Object`、`Array`、`Function`、`Date` 和 `RegExp`。数组、函数和正则表达式是特殊类型，但从概念上讲，日期和正则表达式是原始值。

变量、数组元素、函数参数和返回值的类型通常由 JavaScript 引擎检查。类型转换（强制转换）是自动的。

变量的值可能是：

- 数据值：字符串、数字或布尔；
- 对象引用：普通对象、数组、函数或正则表达式；
- 特殊值 `null`，通常用于初始化对象的默认值；
- 特殊值 `undefined`，所有已声明但未初始化的变量。

字符串是 Unicode 字符序列。字符串字面量如 `"Hello world"`、`...'` 或空字符串 `""` 被单引号或双引号包裹。两个字符串可以使用 `+` 运算符拼接，并使用三等运算符检查相等性：

```javascript
if (firstName + lastName === "JamesBond") ...
```

字符串的字符数可以通过对字符串应用 `length` 属性获得：

```javascript
console.log("Hello world!".length); // 12
```
