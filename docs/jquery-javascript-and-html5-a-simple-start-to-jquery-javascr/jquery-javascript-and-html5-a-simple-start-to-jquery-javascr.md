
# jQuery, JavaScript 和 HTML5：jQuery, JavaScript 和 HTML5 入门指南（软件工程师编写）（jQuery 编程、jQuery 基础教程、... Web 开发中的 JavaScript、Java）

作者：Scott Sanderson

# 第 1 章：引言

如果有一个应用开发框架可以被称为全面的，那么 HTML5 毫无疑问地胜出了。尽管 HTML5 的规范尚未完善，但大多数现代网络浏览器都支持在设备上运行这些流行功能，设备范围从智能手机到桌面电脑。这意味着你只需要编写一个应用程序，它就可以在你的设备上运行而不会出现任何互操作性问题。

毫无疑问，HTML5 是 Web 应用开发的未来，如果你想留在这一行列中，你就需要具有前瞻性思维，并装备自己以应对未来即将向你提出的技术挑战。HTML5 的范围显而易见，因为行业的大多数主要参与者都在关注这项技术并给予了全力支持。

如果 HTML5 的多功能性和高阶特性吸引了你，并且你想立即开始编写自己的应用程序，但又不知道如何开始以及从何处开始，那么这本书就是为你准备的。这本书涵盖了你借助 HTML、JavaScript/JQuery 和 CSS 创建运行良好的应用程序的所有内容。然而，它并不是一本参考指南。我们希望为你提供实用的知识，以便你尽早开始开发。

这本书是一份完美的入门指南，涵盖了 HTML5、JavaScript 和 CSS 开发的所有基本方面。它涵盖了从最基础的到你信任该框架时所需的一切内容。前三章向你介绍了这三种技术，为你提供了一个起点基础。

# 第 2 章：HTML5 基础

HTML（超文本标记语言）是一种用于创建网页的语言。事实上，自从第一个网页创建以来，这种语言一直被使用。然而，随着更新、更好版本的引入，其功能也在不断进化。已知该语言起源于 SGML（标准通用标记语言），SGML 早期被用于文档出版。HTML 从 SGML 那里继承了格式功能概念及其语法。

对于浏览器而言，HTML 使用的最有趣且最有益的方面之一是，浏览器同时支持向后兼容和向前兼容。虽然向后兼容通常很容易实现，但向前兼容却很棘手，因为在这种情况下，其问题领域是无限大的。然而，为了实现这一点，浏览器被设计为忽略它们不识别的标签。

多年来，HTML 一直是人们的全部。但随着时间的推移，人们觉得需要更多，这是由于另一种被称为 XML（可扩展标记语言）的技术出现而催化的。尽管 XML 与 HTML 有许多相似之处，但两者之间存在许多根本性的区别。首先，XML 要求标签匹配，这意味着对于每一个起始标签，必须存在一个闭合标签。此外，XML 允许你创建自己的标签，因为它不像 HTML 那样拥有一个固定的标签集。

XML 中使用的标签是元标签，或描述位于起始标签和闭合标签之间数据的标签。为了确保 XML 文档的有效性，使用名为 XSD（XML 架构定义）的技术。然而，这项技术无法用于验证 HTML 文档，因为 HTML 文档缺乏定义良好的结构。

W3C（世界网联盟）引入了 XHTML 来尝试修复 HTML 的缺陷。根据 XHTML 规范，HTML 文档应遵循更严格的规则。

## 语义化标记

HTML5 的基本特性是它为内容提供了意义。HTML5 不仅仅使用 `div` 进行布局，还引入了语义化标签，如 `<header>`、`<footer>`、`<section>`、`<article>` 和 `<nav>`。这有助于浏览器和搜索引擎理解网页内容的结构和目的。

## HTML5 元素

在 HTML 中，一个元素简单来说就是起始标签、内容和一个闭合标签。因此，当你写时：

```html
<div>
<b>This is my world!</b>
</div>
```

在这个示例中，`div` 包含了粗体文本。需要说明的是，HTML5 不区分大小写。因此，无论你写 `<B>` 还是 `<b>`，浏览器都会认为它们是相同的。然而，W3C 建议使用小写标签。

## 元素操作

HTML5 定义了超过 100 个元素。这些元素的定义在附录中提供。

## 如何为元素添加属性？

额外数据可以以属性的形式添加到起始标签中。属性通常表示为 `name="value"`。属性的值包含在引号内。对于向元素添加的属性数量没有限制。例如：

```html
<div id="main" class="mainContent"></div>
```

在这里，`id` 和 `class` 是属性，其中 `id` 唯一标识元素，`class` 指定该 `div` 所属的 CSS 样式。

### 布尔属性

可以使用多种类型的属性。最常用的类型之一是布尔属性。布尔属性可以从允许的值集中取值。一些可能的值包括：

- `Checked`
- `Disabled`
- `Selected`
- `Readonly`

有两种方式来指示布尔属性的值。

```html
<input type="checkbox" name="vegetable" value="Broccoli" checked>
<input type="checkbox" name="vegetable" value="Broccoli" checked="checked">
```

在第一种情况下没有给出值并是假设的。尽管后者看起来是冗余的形式，但它是更优的形式，特别是当你使用 jQuery 时。

### 全局属性引用

HTML5 提供了一组命名属性，可以与任何元素一起使用。这些属性的示例包括 `accesskey`、`spellcheck` 和 `draggable`，以及其他几个。

### 空元素

某些元素在任何情况下都不包含内容。这些元素包括 `<link>`、`<br>` 和 `<img>`，以及许多其他。

### 自闭合标签

如果你使用一个不包含任何内容的元素，那么可以使用自闭合标签。这种标签的示例是 `<br/>`。

`div` 等元素必须写成 `<div></div>`，即使它们没有任何内容。

## 如何添加 Expando 属性

你作为作者定义的任何属性都称为 expando 属性。你可以为这个自定义属性命名，并在需要时为其分配一个值。

## 如何添加注释

可以使用 `!` 和两个连字符 `-` 来添加注释。添加注释的语法如下：

```
<!--text -->
```

你也可以使用以下语法添加条件注释：

```
<!--[if lte IE 7]><html class="no-js ie6" lang="en"><![endif]-->
```

此注释用于判断正在使用的浏览器是否比 IE7 发布更早的版本。

### 如何创建 HTML 文档

HTML 文档可以简单地描述为一个包含元数据、内容和结构的框架。

HTML 文档必须以标签 `<!DOCTYPE html>` 开始。在 HTML5 中，该声明指示浏览器应该以无怪异模式（no-quirks mode）或 HTML5 兼容模式运行。

下一个标签应该是 `<html>`。该元素内部包含了 `<head>` 和 `<body>` 元素。`<head>` 元素可以包含 HTML 文档的元数据，这些元数据是使用 `<meta>` 标签声明和定义的。`<head>` 元素还包含 `<title>` 元素，其具有以下作用：

- 搜索引擎使用
- 此内容显示在浏览器工具栏中
- 为页面提供默认名称

`<body>` 元素包含了任何要显示在 HTML 文档上的其他信息。

下面提供了一个 HTML 文档示例：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>TITLE OF DOC</title>
</head>
<body>
CONTENT
</body>
</html>
```

注意：特殊字符 `>` 或 `<` 是 HTML 语法的一部分，可以使用它们的名称或数字（实体）在 HTML 文档中使用。它们的用法语法为：

`&entity_name` 或 `&entity_number`

附录包含了要使用的实体名称和数字对照表。

- 1. 使用制表符、换行符和空格创建的空白会被 HTML 归一化为单个空格。因此，如果你想使用多个空格，必须使用不换行空格字符。例如，如果你想显示 10 mph 使得 10 和 mph 之间不被换行符分隔，你可以写 `10&nbsp;mph`。

### 如何嵌入内容

现在你已经知道如何用你的内容创建 HTML 文档，你可能想从其他源向文档嵌入内容。这些内容可以是来自另一个 HTML 文档的文本或 Flash 应用。

### 内联框架

内联框架用于在当前 HTML 文档的内容中嵌入 HTML 文档。因此，在某种意义上，该元素创建了嵌套浏览器，因为多个网页加载在同一个窗口中。这些是通过使用 `<iframe>` 元素实现的。可以使用以下方式导航嵌套浏览上下文：

- `window.parent` – 此 `WindowProxy` 对象代表父上下文。
- `window.top` – 此 `WindowProxy` 对象代表顶层浏览上下文。
- `window.frameElement` – 这代表浏览上下文容器，如果没有上下文容器，则返回 `null`。

`<iframe>` 元素的语法如下：

```html
<iframe src="name"></iframe>
```

在这里，属性 `name` 定义了浏览上下文的名称。该名称可以是任何字符串，如 `sample.html`。然而，名称不应以下划线开头，因为以下划线开头的名称被留给特殊键名，如 `_blank`。

### 沙箱

沙箱用于避免在你的 HTML 文档中引入弹出窗口或其他恶意软件。为了实现这一点，使用了属性 `sandbox`。你可以按照以下方式使用该属性：

```html
<iframe sandbox="keywords" src="name"></iframe>
```

当你使用沙箱时，会对被调用的上下文实施若干限制。这些限制包括禁用表单、脚本、插件以及自身以外的任何框架。你可以使用等关键词强制系统覆盖这些限制：

- `allow-same-origin`
- `allow-scripts`
- `allow-forms`
- `allow-top-navigation`

可以使用空格将多个关键字隔开。

### 无缝嵌入

`seamless` 属性可以在 `<iframe>` 元素中用于嵌入内容。

```html
<iframe seamless src="name"></iframe>
<iframe seamless="" src="name"></iframe>
<iframe seamless="name"></iframe>
```

### 超链接

超链接可以链接外部和内部位置。使用 `<a>` 元素来实现此功能。

- 蓝色 - 未访问的链接
- 紫色 - 已访问的链接
- 红色 - 激活链接

外部链接的语法：

```html
<a href="address">Text</a>
```

内部链接的语法：

```html
<a href="#id">Text</a>
```

`target` 属性用于指定链接应该在何处打开：

- `_blank`
- `_parent`
- `_self`
- `_top`
- `_frame`

超链接还可以使用以下语法发送电子邮件：

```html
<a href="mailto:email address">Text</a>
```

### 嵌入图像

`<img>` 元素用于向 HTML 文档添加图像。`<img>` 标签是一个空元素（void element），不需要闭合标签。该元素所需的标签是 `src`，它指定了存储图像的绝对或相对地址。可以与 `<img>` 标签一起使用的另一个属性是 `alt`，它指定了图像不可用时必须显示的文本。

```html
<img src="address" alt="alternative text">
```

需要注意的是，你只提供了图像的引用，而没有将它们嵌入到 HTML 文档中。允许的图像格式有 jpeg、png 和 gif。

### 如何创建图像映射

`<map>` 元素可以创建可点击的图像映射。为了在映射和图像之间建立链接，你必须为映射设置名称，并在 `<img>` 标签的 `usemap` 属性中使用该名称。

映射的区域由 `<area>` 元素定义。这是一个自闭合标签，用于定义映射的区域。映射的区域可以使用 `shape`、`href`、`alt` 和 `coords` 属性来设置。

`shape` 属性可以给出值 `poly`、`circle`、`rect` 或 `default`。默认值将区域设置为图像的大小。`href` 和 `alt` 属性的使用方式与 `<a>` 元素相同。最后，`coords` 属性根据所选形状按以下方式定义：

- `poly` - x₁, y₁, x₂, y₂, ..., xₙ, yₙ
- `circle` - x, y, radius
- `rect` - x₁, y₁, x₂, y₂

对于多边形，起始和结束坐标应该是相同的。如果在此方面存在差异，则添加一个闭合值。

示例：

```html
<img src="worldmap.gif" width="145" height="126" alt="World Map" usemap="#country" />
<map name="country">
<area shape="circle" coords="105,50,30" href="China.html" alt="China" />
<area shape="default" href="InvalidCountry.html" alt="Please Try Again" />
</map>
```

## 插件

插件同样可以使用 `<embed>` 和 `<object>` 元素嵌入 HTML 文档中。虽然这些元素执行的任务相似，但它们是由不同的浏览器创建的。因此，它们在 HTML5 中共存。虽然 `<embed>` 元素提供了易用性，但 `<object>` 元素为用户提供了更多功能。这两个元素的语法下文所示：

### `<embed>` 标签

```html
<embed src="Flash.swf"></embed>
```

`src` 属性指定要嵌入文件的 URL 或地址。`<embed>` 元素接受的其他属性还包括：

- `type` - 用于指定内容的 MIME 类型
- `height` - 用于以像素为单位指定内容的高度
- `width` - 用于以像素为单位指定内容的宽度

如前所述，某些浏览器可能不支持 `<embed>` 元素。因此，如果你在文档中使用它，则必须添加回退内容规范。例如，如果你正在嵌入一个 flash 文件，如果浏览器已经不支持，你必须将用户重定向到 flash player 的下载链接。

你可以通过以下方式实现：

```html
<embed src="Flash.swf">
<a href="link for downloading flash player">
<img src="address of the image for download flash player" alt="Download Adobe Flash player" />
</a>
</embed>
```

### `<object>` 标签

`<object>` 标签允许你嵌入各种媒体文件，如视频、音频、PDF、applets 和 Flash。该元素接受以下属性：

- `type` – 用于指定数据的 MIME 类型
- `form` – 用于指定数据的表单 id 或 ids
- `data` – 用于指定对象使用的资源 URL
- `usemap` – 用于指定对象使用的客户端图像映射的名称
- `name` – 用于指定对象名称
- `height` – 用于以像素为单位指定对象的高度
- `width` – 用于以像素为单位指定对象的宽度

在上述所有属性中，必须提及 `data` 或 `type` 属性之一。

数据可以使用 `<param>` 标签传递到 `<object>` 元素中，该标签是 `name` 和 `value` 属性的组合。可以使用此标签声明多个参数。

```html
<object data="file.wav">
<param name="autoplay" value="false" />
</object>
```

注意：

- 1. `<object>` 元素必须始终在 `<body>` 元素内部。
- 2. HTML5 仅支持上述列出的属性以及 `<object>` 元素的全局属性。

# 第 3 章：JavaScript 基础

交互是任何网站的一个重要方面。为了与观众建立更好的联系，为网站添加行为是至关重要的。这可以是简单的按钮，也可以是复杂的动画。这些任务可以使用 JavaScript 来完成，JavaScript 是一种 Web 和编程语言。本章将介绍 JavaScript，并将帮助你立即开始学习 JavaScript。

## 背景

JavaScript 是客户端脚本编写的首选编程语言。与流行观点不同的是，JavaScript 与 Java 没有任何关系。事实上，它与 ECMAScript 具有相似之处。此外，这种编程语言与 C 和 C++ 等其他编程语言唯一的共同点是它们都使用大括号。JavaScript 的国际标准定义在 ISO/IEC 16262 和 ECMA-262 规范中。

这种编程语言最重要的特征之一是它是无类型的。换句话说，使用变量时没有必要指定类型。例如，如果你给一个变量赋值了一个字符串，稍后可以给同一个变量赋值一个整数。变量使用关键字 `var` 进行声明。

## 数据与表达式

任何程序都会向用户访问、操作和表示数据。数据以不同的类型和形式存在。这些数据可以很容易分解为值。在 JavaScript 中，数据可以表示为原始值、对象或函数。

最底层的数据表示被称为原始类型，包括 `null`、`undefined`、`number`、`string` 和 `Boolean`。



# JavaScript 基础

## 内置对象

JavaScript 定义了几个内置对象。这些包括 `Object` 对象、`Global` 对象、`Array` 对象、`Function` 对象、`Boolean` 对象、`String` 对象、`Math` 对象、`Number` 对象、`RegExp` 对象、`Date` 对象、`Error` 对象。

## 原始类型

最底层的数据表示被称为原始类型，包括 `null`、`undefined`、`number`、`string` 和 `boolean`。

## 字符串

字符串可以被简单描述为字符的集合。当引号内包含字符时，系统将其解释为字符串。

## 逻辑运算

逻辑涉及这些逻辑运算符的结果是布尔值（`true` 或 `false`）。

## 转义序列

JavaScript 还支持其他转义序列，如 `\t` 表示制表符，`\n` 表示换行符。

## 布尔类型

布尔类型是一种二进制数据类型，返回 `true` 或 `false`。这些运算符通常用于指示比较的结果。例如，`10 > 5` 将得到 `true`，而 `5 > 10` 将得到 `false`。

## 数字类型操作

为了进行计算，使用了运算符。JavaScript 支持所有基础运算符，运算符优先级如下：

- 加法和减法的优先级相同。
- 乘法和除法的优先级相同。
- 乘法除法的优先级高于加法和减法。
- 如果表达式包含多个相同优先级的运算符，则从左到右求值。

除了基础运算符，JavaScript 还支持模运算 `%`。该运算符执行除法并返回余数作为结果。例如，`23 % 7` 等于 2。

## 一元运算符

虽然加法等运算符需要操作数，但某些运算符只需要一个。此类运算符的示例是 `typeof`，它返回数据的类型。例如，`typeof 12` 返回 `'number'`。请注意 `+` 和 `-` 可以作为一元运算符使用，当它们被用于指定数字的符号时情况如此。

## 逻辑运算符

JavaScript 提供了三种可用的逻辑运算符，即非 (`!`)、或 (`||`) 和与 (`&&`)。涉及这些运算符的操作结果是布尔值（`true` 或 `false`）。这些操作的结果计算遵循以下准则：

| 运算符 | 类型 | 说明 |
| :--- | :--- | :--- |
| `&&` (与) | 二元运算符 | 两个条件必须为真 |
| `||` (或) | 二元运算符 | 至少有一个条件必须为真 |
| `!` (非) | 一元运算符 | 对确定的条件值进行取反 |

例如：

```
'Red' != 'Blue' && 5 > 1 = 'true'
```

```
'Red' != 'Blue' && 5 < 1 = 'false'
```

```
'Red' == 'Blue' && 5 < 1 = 'false'
```

对于条件运算符，JavaScript 使用短路求值。换句话说，如果第一个条件的值计算为 `'false'`，系统将不会评估其他条件，并直接呈现结果。

## 语句

任何以分号结尾的语句被称为语句（statement）。与表达式不同，语句可能产生也可能不产生值，而表达式必须产生值。

## 变量

数据操作是通过变量的帮助完成的。数据存储在内存中，对该内存位置的命名引用称为变量。任何标识符通过在其前面加上关键字 `var` 来声明为变量。变量的声明示例如下：

```
var result;
```

此语句声明了一个名为 `result` 的变量。你也可以在声明的同时使用如下语句来定义变量：

```
var result = 0;
```

或者

```
var result = 23 * 4 + 6;
```

在命名变量时必须遵循某些规则。这些规则如下：

- 变量名可以是数字和字符的组合。
- 变量名不能以数字开头。
- 变量名中允许的特殊字符是下划线 (`_`) 和美元符号 (`$`)。
- 变量名中不应有空格。例如，`'result value'` 是不允许的。
- JavaScript 关键字是保留的，不能使用。

请注意，JavaScript 与 HTML 不同，它是区分大小写的。因此，`VAL` 和 `val` 是两个不同的变量。此外，建议变量名能够描述其用途。例如，如果我们将变量命名为 `result`，那么显而易见，这个变量将包含代码计算出的结果值。

JavaScript 中使用的另一个约定是命名变量，使其变量名的第一个字母小写。然而，名称中后续每个单词的首字母都大写。这的一个例子是变量名 `arrayResult`。此外，不建议使用下划线和美元符号，但在 jQuery 对象中它们被广泛使用。

## 环境

一组完整的变量及其包含的值构成了所谓的环境（environment）。因此，每当浏览器中加载一个新的网页时，你都在创建一个新的环境。以 Windows 8 为例，它会在应用程序启动时创建一个环境，并在结束时销毁该环境。

## 函数

一组解决特定目的的语句被称为函数（function）。使用函数的目的是代码复用。如果你的程序在程序中多次使用某项功能，则将其实现为函数，可以在需要时调用。由于函数是从代码内部调用的，因此可以从代码向函数发送参数。执行时，函数会将一个值返回给调用函数。函数声明和定义的语法如下：

```
function multiply(a, b) {
  return a * b;
}
```

函数名必须始终以关键字 `function` 前置。变量 `a` 和 `b` 是传递给函数的参数，函数返回计算 `a * b` 得到的值。这是一个简单的函数，但你可以根据所需的功能实现复杂且大型函数。

现在你已经实现了函数，你可能想知道函数是如何调用的。这里有一个示例：

```
var x = 2;
var y = 5;
var c = multiply(x, y);
```

在这里，`x` 和 `y` 是函数 `multiply` 将接收的参数。

JavaScript 是一种弱类型语言。这意味着如果你传递给函数的参数多于它预期的，系统将仅使用所需的第一个 `n` 个参数并丢弃其余部分。这种功能的优势是，你可以使用已经实现的函数，并传递额外的参数来扩展函数并为其添加功能。另一方面，如果你无意中传递了数量错误的参数，将无法获得任何错误提示。

JavaScript 还提供了一些与用户交互内置函数。这些函数如下：

- **alert**
  此函数弹出一个带有消息的警告，系统在用户点击 OK 按钮后恢复操作。示例实现：
  ```
  alert('Alert');
  ```

- **prompt**
  此函数显示一个带有消息和供用户输入的文本框的对话框。示例实现：
  ```
  var result = prompt('Enter some text:');
  ```

- **confirm**
  此函数显示一个带有消息和 OK/取消 按钮的对话框。示例实现：
  ```
  var result = confirm('Are you sure?');
  ```

## 函数作用域

函数可以在任何级别进行嵌套。换句话说，可以在另一个函数内部调用函数。

## 类型转换

之前讨论的 `prompt` 函数返回字符串。然而，在这种情况下，可能需要从字符串到数字的转换。在 JavaScript 中，可以使用以下函数将一种类型转换为另一种：

- **Number**
  此函数将提供的对象转换为数字类型。然而，如果函数无法执行转换，则返回 `NaN`。

- **String**
  此函数转换为字符串类型。

## 条件编程

在编写代码时，你可能会遇到许多情况，在条件为真时需要执行一组指令，而在条件为假时执行另一组指令。

### if-else

为了实现此类场景，你可以使用 `if-else` 结构。

语法：

```
if (condition) {
  // code
} else {
  // code
}
```

考虑一种你使用 `prompt` 函数让用户输入年龄的情况。现在，你必须在提供的值进行任何计算之前验证年龄是否为有效数字。这是实现条件编程的理想场景。该场景的示例实现如下：

```
var userAge = prompt('Enter your age: ', '');

if (isNaN(userAge)) {
  alert('Age entered is invalid!');
} else {
  // code
}
```

在这个示例代码中，`if` 子句检查输入的值是否为数字。如果条件为真（即输入的对象不是数字），则给用户一个警告消息。然而，如果条件为假，则执行 `else` 的代码。

这里需要注意的是，对于单条语句，没有必要使用大括号。上述代码也可以写成：

```
var userAge = prompt('Enter your age: ', '');

if (isNaN(userAge))
  alert('Age entered is invalid!');
else
  // code
```

然而，使用大括号是一个好习惯，因为以后可能有添加额外代码的空间。

### if-else if

另一个条件编程结构是 `if-else if` 结构。该结构允许你声明多个条件以及与之相关的操作。语法为：

```
if (condition) {
  // code
} else if (condition) {
  // code
} else {
  // code
}
```

### switch

可以使用此结构实现多个 `else if`。由于条件是按顺序检查其有效性的，因此这种条件编程结构的执行开销较高。作为一种替代方案，可以使用另一个关键字 `switch`，它以跳转表（jump table）的形式实现多个条件。因此，`switch` 的执行开销小于 `if-else if`。

示例实现：

```
var userChoice = prompt('Choose an alphabet: a, b, c', 'e');

switch (userChoice) {
  case 'a':
    alert('a chosen\n');
    break;
  case 'b':
    alert('b chosen\n');
    break;
  case 'c':
    alert('c chosen\n');
    break;
  default:
    alert('None of the alphabets chosen\n');
    break;
}
```

`switch` 结构将用户输入的值与 `case` 中呈现的值进行匹配。如果找到匹配的值，则执行该 `case`。然而，在这种情况下，如果没有 `case` 值与输入的输入匹配，则执行 `default` 分支。此外，你还可以在 `case` 值中使用条件，并执行条件成立的 `case`。

如果你在 `case` 代码后没有使用 `break` 语句，则匹配 `case` 之后的所有 `case` 都将被执行。例如，如果用户在上述示例中输入 `'b'`，且在 case 代码后没有 `break` 语句，那么输出将是：

```
b chosen
c chosen
None of the alphabets chosen
```

此外，在 `default` 分支中使用 `break` 语句也是一种良好的习惯。

> **注意：**
> 如果你想确定一个关键字是否被赋值了值，可以使用以下代码：
> ```
> if (c) {
>   // code
> } else {
>   // code
> }
> ```
> 如果变量 `c` 被赋值了一个非空值，则 `if` 条件为真并执行相应的代码。相反，如果变量 `c` 的值为 `undefined` 或 `null`，则执行 `else` 结构中的代码。

> **注意：**
> 以下条件的执行将始终为真：
> ```
> "" == 0
> null == undefined
> '123' == 123
> false == 0
> ```
> 请注意，JavaScript 会转换相关变量的类型以进行兼容性比较。

> 然而，如果你想同时比较两个变量的值和类型，JavaScript 提供了另一组运算符 `===` 和 `!==`。当使用此运算符对上述示例中提到的值进行比较时，结果将始终为 `false`。

## 循环

循环是任何编程语言中重要且常用的结构。当你需要执行给定次数的同一组指令时，会面临几种情况。为了实现这种场景，必须使用循环。JavaScript 中提供的循环结构包括 `for`、`while` 和 `do-while`。

`while` 循环包含一个条件，只要条件保持为真，循环就会继续执行。`do-while` 循环是 `while` 循环的修改版。如果 `while` 中的条件为假，则循环将不会执行。相反，即使 `while` 条件为假，`do-while` 循环至少执行一次。

### while 循环的语法

```
while (condition) {
  // code
}
```

### do-while 循环的语法

```
do {
  // code
} while (condition);
```



# JavaScript 循环与错误处理

## for 循环

JavaScript 中提供的最后一种循环是 `for` 循环。`for` 循环允许你在同一语句中初始化循环变量、检查条件并修改循环变量。

### 语法

```javascript
for (initialize; condition; modify) {
  // code
}
```

### 示例代码

```javascript
for (i = 0; i < 10; i = i + 1) {
  // code
}
```

此循环将运行 10 次。

### 注意事项

1. 如果在任何时间点你希望中断循环，可以使用 `break` 语句。
2. 如果你不指定条件，或者指定了一个始终为真的条件，循环将无限运行。

## 错误处理

异常预计会在你代码的几处发生。因此，最好实现一种可以帮助你处理这些异常并避免崩溃的机制。

异常可以被描述为非法操作或任何意外且不寻常的情况。异常的示例包括未经授权的内存访问。

你可以通过在执行任何操作之前验证变量的值，在自己的层面进行异常处理。例如，在执行除法之前，建议检查分母的值是否为零。任何涉及除以零的操作都会抛出除以零异常。

然而，还有其他无法以这种方式处理的情况。例如，如果网络连接突然中断，你无法采取任何措施预先处理该情况。因此，对于这些情况，使用了 `try`、`catch` 和 `finally` 关键字。

预计抛出异常的代码放在 `try` 块中。此异常一旦发生，会被 `catch` 块捕获，该块执行在捕获异常后应立即执行的代码。`catch` 之后可以是 `finally` 块，该块执行最后的清理。该块在 `try` 和 `catch` 块执行后执行。

### 语法

```javascript
try {
  // code
} catch (exceptionName) {
  // code
} finally {
  // code
}
```

# 使用对象

JavaScript 允许用户访问许多对象。其中一个对象就是数组。本节将讨论与处理对象相关的所有基础。

## 数组

一组连续的相似对象被称为数组。该数组有一个名称，可以使用索引访问每个元素。假设 `arrName[]` 是一个数组。可以使用以下方法创建数组：

### 使用索引插入项

可以使用 `new` 关键字创建数组，然后通过给独立元素赋值来添加元素。`new` 关键字使用构造函数创建实例。

```javascript
var arrName = new Array();
arrName[0] = 'Jack';
arrName[1] = 'Alex';
```

### 压缩数组

第二种实现也使用 `new` 关键字。然而，在这种情况下，值作为参数传递给 `Array` 对象的构造函数。

```javascript
var arrName = new Array('Jack', 'Alex');
```

### 字面量数组

在这种类型定义中，值位于方括号内。

```javascript
var arrName = ['Jack', 'Alex'];
```

第一种定义的优点允许你在代码的任何地方为元素赋值。相反，第二和第三种实现要求你预先拥有元素的精确列表。

### 数组属性

所有对象都有一些属性。对你有用的一个属性是 `length`，它是一个只读值，调用时返回数组中的元素数量。你可以在循环和条件中使用该属性。

### 数组方法

对象也可以有自己的函数。这些函数被称为方法。`Array` 可用的方法包括：

- `concat()`：返回一个两个数组拼接后的数组。
- `indexOf()`：找到相关元素在数组中的位置并返回其索引。
- `join()`：此方法将数组中的所有值拼接。然而，默认情况下这些值用逗号分隔。你也可以指定自定义的分隔符。
- `lastIndexOf()`：此方法的工作与 `indexOf()` 相似。然而，它对数组的最后一个元素进行搜索。因此，它返回匹配标准的最后一个元素的索引。
- `pop()`：删除最后一个元素并返回其值。
- `push()`：将相关元素添加到数组末尾，并返回修改后的长度值。
- `reverse()`：此方法会反转数组元素的顺序。该方法会修改原始数组。
- `shift()`：移除并返回第一个值。如果数组为空，则返回 `undefined`。
- `slice()`：此方法需要两个参数：起始索引和结束索引。将创建一个新数组，其元素与位于索引（起始索引）和（结束索引 – 1）处的元素相同。
- `sort()`：此方法对元素进行排序并修改原始数组。
- `splice()`：此方法在指定的数组中删除并添加元素。该方法接受的参数为：起始索引（系统应从此处开始删除元素的索引）、要删除和添加的元素数量。如果传递的元素数量为 0，则不删除任何元素。相反，如果该值大于数组的大小，则从起始索引到数组结束的所有元素都将被删除。
- `toString()`：此方法会创建一个字符串，它是数组中所有元素用逗号分隔的连接字符串。
- `unshift()`：此方法在数组的第一个位置添加一个元素，并返回修改后的长度值。
- `valueOf()`：此方法返回一个字符串，它是包含数组中所有值的逗号分隔连接字符串。

### 注意事项

1. 在处理函数时，你可以传递整个数组（使用数组名）或数组的特定元素（使用 `arrName[index]`）。
2. 可以通过索引访问元素来修改数组元素。例如，`arrName[1] = 'Danny'`；将值 `'Danny'` 分配给数组的第二个元素。

## DOM 对象

在构建应用程序时，你需要访问的主要对象是与它关联的 DOM 对象。这种访问对于你控制并获取网页上发生的事件通知是必要的。

DOM 是对象层次结构的表示。可以使用内置的 `document` 变量访问这些对象。该变量引用 DOM 并执行搜索，可能会返回一个活跃的或静态的 `NodeList`。活跃 `NodeList` 包含一个不断变化的元素列表，而静态 `NodeList` 包含不随时间变化的元素。由于获取静态 `NodeList` 耗时较长，建议选择适用于活跃 `NodeList` 的搜索方法。

### DOM 搜索方法

- `getElementById()`：此方法返回具有指定 ID 的第一个元素的引用。
- `getElementsByTagName()`：此方法返回具有指定标签名称的活跃 `NodeList`。
- `getElementsByName()`：此方法返回具有指定名称的活跃 `NodeList`。这是单选项按钮的首选方法。
- `getElementsByClassName()`：此方法返回具有指定类名的活跃 `NodeList`。然而，此方法不支持 Internet Explorer 8 及更早版本。
- `querySelector()`：此方法接受 CSS 选择器作为参数并返回第一个匹配元素。然而，此方法不支持 Internet Explorer 7 及更早版本。
- `querySelectorAll()`：此方法接受 CSS 选择器作为参数并返回所有匹配元素。因此，它返回一个静态 `NodeList`。然而，此方法不支持 Internet Explorer 7 及更早版本。

## 事件

如果你将 JavaScript 比作引擎，那么事件就是提供所需的火花。事件发生在两种情况下。第一类事件是在用户交互期间发生的事件。用户可能会点击图像或输入文本。所有这些都被归为事件。此外，系统状态的变化也被视为事件。例如，如果视频开始或停止，就说发生了一个事件。DOM 允许你捕获事件并执行相应的代码。

在 JavaScript 中，事件基于发布-订阅机制。在创建对象时，开发者可以发布与该对象相关的事件。此外，每当使用该对象时，都可以向其添加事件处理器。事件处理器会通知订阅的事件已触发。此通知包含了有关事件的信息，如鼠标位置和按键按下，以及其他与事件相关的多个细节。

### 事件捕获与冒泡

可能会出现某些情况，事件绑定到按钮点击，而该点击可能位于超链接内部。在这种情况下，元素存在嵌套。因此，当事件触发时，它沿着 DOM 层次结构向下传递。这个过程被称为**事件捕获**。然而，一旦事件到达元素，该事件就会沿着层次结构向上冒泡。这个过程被称为**事件冒泡**。事件跨越层次结构的移动为开发者提供了根据需要订阅或取消传播的机会。

### 订阅事件

可以使用函数 `addEventListener()` 进行订阅过程。该函数需要三个参数：事件、为该事件需要调用的函数，以及一个决定函数是否在捕获或冒泡过程中调用的布尔值（`true` – 捕获，`false` – 冒泡）。大多数情况下，此值被设置为 `false`。正如 W3C 标准提到的，这是订阅的首选方法。

#### 示例代码

```javascript
var btn = document.getElementById('btnDownload');
btn.addEventListener('click', initiateDownload, false);
```

然而，也存在其他方法，包括为 HTML 标签提供内联订阅。这会将事件订阅到冒泡过程中。使用这种方法的优点是它是最老且最受接受的方法，无论你使用哪种浏览器。

```html
<button id='btnDownload' onclick='initiateDownload();'>Download</button>
```

你也可以使用 JavaScript 订阅事件的传统订阅过程。

```javascript
var btn = document.getElementById('btnDownload');
btn.onclick = initiateDownload;
```

### 取消订阅

可以使用函数 `removeEventListener()` 取消订阅，它接受与 `addEventListener()` 相同的参数集。对于上一个示例中使用的 `btn` 变量，可以通过以下方式实现：

```javascript
var btn = document.getElementById('btnDownload');
btn.removeEventListener('click', initiateDownload, false);
```

### 如何取消传播？

使用函数 `stopPropagation()` 来执行此操作。可以通过以下方式实现：

```javascript
var btn = document.getElementById('btnDownload');
btn.addEventListener('click', initiateDownload, false);

function initiateDownload(e) {
  // download
  e.stopPropagation();
}
```

### 如何阻止默认操作？

可以通过以下方式使用函数 `preventDefault()` 实现：

```javascript
var hyperlink = document.getElementById('linkSave');
hyperlink.addEventListener('click', saveData, false);

function saveData(e) {
  // save data
  e.preventDefault();
}
```

JavaScript 还提供了 `this` 关键字，如果你希望频繁访问触发事件的元素，可以使用它。

## 窗口事件

当前浏览器窗口由 `window` 变量表示，它是 `Window` 对象的实例。以下事件与该对象关联：

- `afterprint`
- `beforeonload`
- `beforeprint`
- `error`
- `blur`
- `haschange`
- `load`
- `message`
- `focus`
- `online`
- `offline`
- `pageshow`
- `pagehide`
- `redo`
- `popstate`
- `storage`
- `resize`
- `unload`
- `undo`

## 表单事件

在 HTML 表单内部发生的动作会触发以下事件：

- `change`
- `blur`
- `focus`
- `contextmenu`
- `forminput`
- `formchange`
- `invalid`
- `input`
- `submit`
- `select`

## 键盘事件参考

键盘会触发以下事件：

- `keyup`
- `keypress`
- `keydown`

## 鼠标事件参考

鼠标会触发以下事件：

- `click`
- `drag`
- `drop`
- `scroll`
- `dblclick`
- `dragenter`
- `dragstart`
- `dragend`
- `dragover`
- `dragleave`
- `mousemove`
- `mousedown`
- `mouseover`
- `mouseout`
- `mousewheel`
- `mouseup`

## 媒体事件参考

视频、图像和音频等媒体元素也会触发事件，如下：

- `canplay`
- `abort`
- `waiting`
- `durationchange`
- `canplaythrough`
- `ended`
- `emptied`
- `loadeddata`
- `error`
- `loadstart`
- `loadedmetadata`
- `play`
- `pause`
- `progress`
- `playing`
- `readystatechange`
- `ratechange`
- `seeking`
- `seeked`
- `stalled`
- `blocked`
- `volumechange`
- `timeupdate`

# 第 4 章：CSS3 基础

层叠样式表（CSS）提供了网页广为人知的视觉呈现效果。尽管 HTML 能够为网页提供基础结构，但 CSS 为开发者提供了大量的设计选择。此外，它快速且高效，这使其成为一种越来越受欢迎的设计工具。

CSS 演变自 SGML（标准化通用标记语言）。这一方面的努力目标是使网页的呈现方式标准化。该技术的最新版本是 CSS3，它由 50 个模块组成。

CSS 最强大的特性是它的层叠能力。简单来说，它允许网页从多个样式表中获取样式，使得后续读取的表中的样式更改将覆盖从之前一个或多个样式表中已实现的样式。

## 如何定义和应用样式

样式的定义和应用涉及两个方面或部分：选择器和声明。选择器决定了网页中需要样式的区域，而声明块描述了必须实现的样式规范。为了说明其工作原理，让我们来看一下以下示例：

```css
body {
  color: white;
}
```

在这个示例中，选择器选择了网页的 `body` 部分，声明块定义了字体颜色应更改为白色。这是一个简单的示例，声明和选择器可以比这复杂得多。

## 如何添加注释

可以使用以下格式在样式表中添加注释：

```css
/* 在此处编写注释 */
```

## 如何创建内联样式

每个元素都有一个关联的全局属性 `style`。可以在元素标签内操作此全局属性，以修改该元素的外观。这种类型的样式不需要你指定选择器，只需要声明块。以下是这种操作的示例：

```html
<body style='color: white;'></body>
```

此 HTML 标签执行的功能与上一节中指定的 CSS 代码相同。使用这种方法的优点是，通过这种方式提供的样式信息会覆盖任何其他样式信息。因此，如果你需要为一个元素使用不同的样式，而文档的其他部分需要不同的样式，你可以为文档使用样式表，并在标签中为该元素指定样式。

## 如何使用嵌入样式

实现与内联样式相同结果的方法是在相关元素内部使用 `<style>` 元素来定义其样式规范。方法如下：

```html
<!DOCTYPE html>
<html xmlns='http://www.w3.org/1999/xhtml'>
<head>
  <title></title>
  <style>
    body {
      color: white;
    }
  </style>
</head>
<body></body>
</html>
```

## 如何创建外部样式表

对于希望对整个网页或多个网页使用相同样式的情况，最佳方法是使用外部样式表。

该外部样式表可以通过以下方式链接到 HTML 页面：

```html
<!DOCTYPE html>
<html xmlns='http://www.w3.org/1999/xhtml'>
<head>
  <title></title>
  <link rel='stylesheet' type='text/css' href='style.css'>
</head>
<body></body>
</html>
```

## 优先级与层叠

现在你已经了解了如何为特定元素应用样式，让我们转向为更具体的部分实现样式，例如段落的第一行。对于无法根据名称、内容分类或不是 DOM 树一部分的元素，可以使用伪类进行样式设置。可用的伪类包括：

- `:visited`
- `:link`
- `:hover`
- `:active`
- `:focus`
- `:nth-last-child(n)`
- `:not()`
- `:only-child`
- `:nth-child(formula)`
- `:lang(language)`
- `:first-of-type`
- `:only-of-type`

如果你想访问 DOM 树中其他方式无法访问的信息，可以使用伪元素。伪元素包括：

- `::first-letter`
- `::first-line`
- `::after`
- `::before`

## 使用属性选择器

此选择器选择所有存在指定属性的元素。选择器的写法形式如下：

```css
a[title]
```

此选择器将选择所有指定了 `title` 属性的链接。此外，这种选择器类型可以通过以下方式指定属性值，修改为属性-值选择器：

```css
a[title = value]
```

## 浏览器的内置样式

每个浏览器都有一个内置样式表，该样式表应用于使用该浏览器打开的所有网页。事实上，该样式表在任何其他样式表之前应用。你可以使用“工具”菜单中的“可访问性”选项为浏览器定义自己的样式表。然而，用户样式表是特定于浏览器的。因此，如果你打开不同的浏览器，你定义的样式表可能无法访问。

如果你希望用户定义的样式表覆盖 HTML 页面中指定的任何其他样式，可以使用 `!important` 修饰符。该修饰符为指定的样式语句设置最高优先级。示例实现：

```css
body {
  color: white !important;
}
```

## 样式级联

样式的优先级和顺序是根据以下参数决定的：

- 重要性
- 特异性
- 顺序

## 使用 CSS 属性

既然你已经彻底熟悉了选择器的用法，下一步是查看 CSS 属性。

## 颜色

网页中最关键的属性之一是颜色，可以使用 ARGB、RGB 和颜色名称来定义。

RGB 值通常使用 0-255 之间的数字定义。

- 白色 `white` `#ffffff`
- 红色 `red` `#ff0000`
- 黑色 `black` `#000000`
- 绿色 `green` `#008000`

也可以代替颜色名称。以下是这种用法的示例。



```
body {
  color: #ffffff;
}
```

指定颜色的另一种方法是使用 `RGB` 函数，它使用 0-255 之间的数字或百分比指定参数值。这种类型的声明示例如下：

```
h1 { color: rgb(255,0,0); }
```

其他指定颜色的方法还有 `RGBA`（它接受 4 个值）和 `HSL`（它定义色相、饱和度和亮度的值）。

## 透明度

透明度或不透明度由 0.0（不可见）到 1.0（不透明）之间的值定义。

## 文本

在文本方面，可以指定 `font-face` 和 `font-size`。这些属性可以用以下方式定义：

```
h1 { font-family: arial, verdana, sans-serif; }
```

```
h1 { font-size: 12px; }
```

## CSS 盒模型

CSS 盒模型假设网页可以看作是由盒子组成的。盒子之间的间距由 `margin` 和 `padding` 设置决定。这些属性可以用以下方式赋予值：

```
margin: 15px;
padding: 25px;
border: 10px;
```

# 定位 `<div>` 元素

用于创建页面布局的元素是 `<div>`。虽然 HTML5 建议使用语义化标记代替 div 元素，但它们仍然被用于无法使用语义化标记进行样式的内容。div 元素可以被想象成矩形块，并按以下方式声明：

```html
<div>
<!--其他元素包含在此区域内-->
</div>
```

用于定义 div 元素位置的属性包括：

- 可以使用 `top`、`bottom`、`left` 和 `right` 属性以像素（pixels）定义 div 元素的位置。
- 使用 `position` 属性来定义指定的位置是静态的（static）还是相对的（relative）。
- `float` 属性可以允许元素浮向右侧或左侧，定义为 `float: left` 或 `float: right`。
- `clear` 属性在浮动元素之后放置一个清除元素。
- 如果你希望你的用户定义样式表覆盖 HTML 页面中指定的任何其他样式，那么你可以使用 `box-sizing`。

## 居中内容

可以通过以下方式居中内容：

```css
container {
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}
```

## 网页上的地标

父角色类的子类包括：

- **banner**：这定义了网站特定的内容，这些内容在不同网页之间预计不会改变，例如页眉。
- **application**：这定义了指定区域是一个 Web 应用程序。
- **contentinfo**：这定义了网页中关于网页的信息，例如版权信息。这些信息大部分是页脚内容的一部分。
- **complementary**：这定义了页面的一个部分，该部分在离开页面时也具有意义。
- **main**：使用此子角色类来定义网页的主要内容。
- **form**：这定义了网页中预期接收网页输入的区域。
- **search**：此子角色类用于定义网页上的位置，用于从用户处获取搜索查询并显示搜索结果。
- **navigation**：包含导航链接的区域是该子角色类的一部分。

这些角色可以用于提供语义。然而，HTML5 包含的新元素本身就具有语义。尽管如此，HTML5 中没有提供某些工具，对于这些工具，可以使用 `role` 属性。

## 如何使用 `<div>` 元素控制格式？

如前所述，`<div>` 元素本质上是不可见的，并且不为元素提供任何语义。然而，如果你只想将其用于格式化目的，那么它是此用途的完美选择。

## 如何添加主题分隔符？

空元素 `<hr/>` 可用于添加主题分隔符，用于表示从一组内容到另一组内容的过渡。

## 如何对内容进行注释？

有几个元素可用于注释。这些包括你已经使用了很久的 `<b>` 和 `<i>`。然而，除了它们所表示的样式外，它们现在有了新的含义。例如，`<b>` 元素表示“粗体”（bold）样式。此外，HTML5 增加了“特殊关注的范围，但语气、重要性级别或含义没有变化”的含义。

虽然在这种语境下使用粗体样式更有意义，但你仍然可以使用此元素来表示评论中的产品名称或关键词。同样，`<strong>` 元素表示内容的相对重要性，而 `<i>` 表示所涉及内容的语气或含义的变化。此外，`<em>` 元素用于读者将交替朗读的文本。

## 如何使用 `<abbr>` 处理缩写和略语？

在 HTML 之前的版本中

## 元素 - `<address>`

此元素用于定义网页所有者或作者的联系信息。

## 引用和引用

你可以使用 `<blockquote>` 元素指示特定文本为引用，它用于长引用；使用 `<q>` 则用于行内引用。你可以使用 `cite` 属性或 `<cite>` 元素提到引用的来源。然而，在 `q` 和 `blockquote` 元素内部使用 `<cite>` 元素被认为是更好的方法。请记住，`cite` 元素只能提到作品名称，作者和出版地等其他信息不包含在内。

## 如何在 HTML5 中记录代码？

有两个元素 `<code>` 和 `<samp>` 用于记录代码。`<code>` 元素用于记录源代码，而 `<samp>` 元素用于代码的输出。下面是如何操作的 HTML 示例：

```html
<code class="maintainSpace">
echoContent('Screen');

function echoContent(name)
{
alert('This is is' + name + '.');
}
</code>
```

```html
<samp class="maintainWhiteSpace">
This is Screen.
</samp>
```

## `<pre>` 元素

在这里需要提到，这些元素不会保留空格。因此，需要为此目的实现一个类。该类应该如下：

```css
.maintainWhiteSpace {
    white-space: pre;
}
```

某些浏览器可能不支持此样式规则。因此，对于此类浏览器，建议使用 `<pre>` 元素。因此，`<pre>` 元素可以用于定义预格式规则。

## `<var>` 元素

此元素用于声明内部指定的文本是一个变量。例如：

<p>
变量 `var` 代表循环执行的次数。
</p>

## `<br />` 和 `<wbr>` 元素

`<br/>` 元素实现换行。相反，`<wbr>` 实现单词换行。

## `<dfn>` 元素

有时你可能定义一个术语。可以使用 `<dfn>` 元素来实现，它接受标题作为属性之一。

## 处理图形

图像和插图是任何网页内容的不可或缺的一部分。因此，每个图形也可以被视为一个内容单元，它由标题和指向其所属页面的引用组成。为了定义一个或多个图像，使用了 `<figure>` 元素。`<figcaption>` 元素可以用于定义图形标题。

然而，在这里需要提到，`<figure>` 元素没有赋予图形位置任何重要性，这一点与内容相同在一起。然而，如果图形的位置和位置对你很重要，那么你必须考虑使用 `<div>` 元素。

## `<summary>` 和 `<details>` 元素

`<summary>` 元素包含内容，而 `<details>` 显示。为了定义一个或多个图像，使用了 `<figure>` 元素。

## 其他注释

除了上述元素，还有几个，包括：

- `<s>`：用于删除线
- `<u>`：用于下划线
- `<mark>`：用于高亮文本
- `<ins>`：用于插入
- `<del>`：用于删除
- `<small>`：用于小号字体
- `<sub>`：用于下标
- `<sup>`：用于上标
- `<time>`：用于日期和时间
- `<kbd>`：用于用户输入
- `<b>`：用于粗体文本

## 语言元素

你可能需要在文本中使用中文或韩语字符。为了支持这一点，可以使用 `<ruby>` 元素。在此元素内部，可以使用其他如 `<bdi>` 和 `<bdo>` 的元素来放置标记或方向。

## 表格

- 表格的维护极其困难。
- 表格对于辅助设备难以解析。

示例实现：

```html
<table>
<tr>
<td>Frank</td>
<td>1978</td>
</tr>
<tr>
<td>David</td>
<td>1967</td>
</tr>
<tr>
<td>Alex</td>
<td>1989</td>
</tr>
</table>
```

上述创建的表格如下：

| Frank | 1978 |
| David | 1967 |
| Alex | 1989 |

*(注：原文表格格式缺少表头分隔符在标准 Markdown 中不规范，此处按原样翻译)*

当你观察这个表格时，你可能意识到，除非我们定义了所谓的表头，否则表格是不完整的。这可以通过 `<th>` 元素来实现。你可以同时创建垂直和水平的表头。例如，我们可以在上面使用的代码中定义以下表头：

```html
<table>
<tr>
<th>Name</th>
<th>Year of Birth</th>
</tr>
<tr>
<td>Franky</td>
<td>1978</td>
</tr>
<tr>
<td>David</td>
<td>1967</td>
</tr>
<tr>
<td>Alex</td>
<td>1989</td>
</tr>
</table>
```

该代码生成的表格如下所示：

| Name | Year of Birth |
| Franky | 1978 |
| David | 1967 |
| Alex | 1989 |

在上述情况下，表头只是字体大了一些。然而，你可以通过样式规则对它们进行所需的样式设置。可以通过方式实现：

```css
th {
  background-color: black;
  color: white;
}
```

此样式规则将表格表头的单元格颜色设为黑色，文字设为白色。

大多数浏览器的默认行为自动将所有 `<tr>` 元素放在 `<tbody>` 中，表示这是表格的主体。然而，显式定义 `<tbody>` 是一个良好的习惯。此外，`<thead>` 和 `<tfoot>` 也可以显式定义。表格的头部、主体和页脚可以使用 CSS 进行单独样式化。按照规则，你可以有一个表头元素、一个或多个主体元素和一个页脚元素。

在上述创建的表格中，必须添加的下一个重要特性是表格标题（caption）。为了定义表格标题，使用了 `<caption>` 元素。

在某些情况下，你可能觉得需要对单独列进行样式设置。考虑到表格在 HTML 中本质上是以行为中心的，这似乎是一项艰巨的任务。虽然你有 `<tr>` 元素来识别行，但没有用于识别列的 `<td>` 元素。`<td>` 元素识别的是单元格。然而，你仍然可以使用 `<colgroup>` 或 `<col>` 元素对单独列进行样式设置。`<table>` 元素可以包含 `<colgroup>` 元素，它包含作为组元素一部分的 `<col>` 元素。此外 `<col>` 元素还有一个 `span` 属性用于定义该组中的列。下面提供了解释其工作原理的示例实现：

```html
<colgroup>
  <col span="2" class="vHeader" />
</colgroup>
```

用于设置此组列的 CSS 样式规则可能如下：

```css
.vHeader {
  color: red;
}
```

到目前为止讨论的表格都是普通表格，HTML5 还支持不规则表格，可以描述为每行的列数可能不同的表格。`rowspan` 和 `colspan` 属性可用于管理表格布局。

# 第 6 章：JavaScript 和 jQuery

你可能已经习惯了 JavaScript 的强大。在 JavaScript 章节中，你已经学习了如何创建和添加 JavaScript 来使网页变为动态。Web 开发最大的挑战是设计能够在任何浏览器上运行良好的的网页元素，因为不同的浏览器对元素的支持不同，这使得寻找共同点变得困难。

本章将带你在 JavaScript 开发上更进一步，教你如何创建对象并使用它们。此外，它还向你介绍了 jQuery 的概念，它试图创建浏览器兼容的代码。虽然它不能保证 100% 的浏览器兼容性，但它确实解决了相关的日常问题。

## 如何创建 JavaScript 对象

JavaScript 中从数字到字符串的任何内容都是对象。因此，知道如何有效地创建和处理这些内容非常重要。在 JavaScript 中创建对象简单的方法是使用对象字面量语法。下面的示例说明了如何操作。

```javascript
var customer1 = {
  yearOfBirth: 2000,
  name: 'Alex',
  getCustomerInfo: function () {
    return 'Customer: ' + this.name + ' ' + this.yearOfBirth;
  }
};
```

这段代码创建了一个对象 `customer1`，带有数据成员 `name` 和 `yearOfBirth` 以及成员函数 `getCustomerInfo`。注意此 `this` 关键字的使用也很重要，它能够正确访问相关对象所正在使用或引用的值。

此外，你还可以使用 `new` 关键字动态地创建对象。继承的方法包括：

- `constructor`
- `isPrototypeOf`
- `hasOwnProperty`
- `toString`
- `propertyIsEnumerable`
- `valueOf`

一旦创建了对象，可以通过以下方式添加属性：

```javascript
function getCustomer(myName, myYearBirth) {
  var newCust = new Object();
  newCust.name = myName;
  newCust.yearOfBirth = myYearBirth;
  newCust.getCustomerInfo = function () {
    return 'Customer: ' + this.name + ' ' + this.yearOfBirth;
  };
  return newCust;
}
```

这段代码创建了对象 `newCust`。可以通过创建若干实例：

```javascript
var cust1 = getCustomer('Alex', 1978);
var cust2 = getCustomer('David', 1986);
```

到目前为止讨论的表格都是普通表格，JavaScript 不支持特定的类，但你可以使用上述方法模拟类。

## 命名空间

没有特定的关键字来实现命名空间。然而，可以使用对象的概念来实现命名空间。如果你将变量和方法分类为对象并作为这些实例进行访问，那么只需将这些对象的名称放在全局命名空间，即可减少变量的作用域。

## 实现继承

你可以通过创建对象并根据共同特征对其分类，在 JavaScript 中定义对象之间的“是”关系。例如，如果你正在为公司实现一个对象。你可以创建特定类型的对象，如 `managerTechnical`、`managerGeneral`、`technicalStaff`、`recruitmentStaff` 和 `officeStaff`，并将它们分类为 `technicalStaff`（包含 `managerTechnical` 和 `technicalStaff`）以及 `adminStaff`（包含 `managerGeneral`、`recruitmentStaff` 和 `officeStaff`）。同样，也可以定义新的函数。

## 使用 jQuery

jQuery 是一个浏览器兼容的辅助函数库，你可以在代码中使用它来减少输入、实现和测试的工作。这些函数本质上是用 JavaScript 编写的。因此，你也可以调用 jQuery，一个 JavaScript 库。

jQuery 可用的功能列表包括：

- **Attributes**：一组用于获取和设置 DOM 元素属性的方法。
- **Ajax**：一组提供同步和异步服务器调用支持的方法。
- **Core Methods**：jQuery 的基础函数。
- **Callbacks**：一个用于管理回调的对象。
- **Data Methods**：促进 DOM 元素与任意数据之间关联的方法。
- **CSS Methods**：用于获取和设置 CSS 相关属性的方法。
- **Dimensions**：用于访问和操作 DOM 元素尺寸的方法。
- **Deferred object**：一个能够注册多个回调，同时维护状态更改数据并将其从一个回调传递到下一个回调的对象。
- **Forms**：用于控制表单控件的方法。
- **Traversing**：一组提供用于遍历 DOM 支持的方法。
- **Effects**：用于为网页创建动画的方法。
- **Events**：用于基于事件执行的方法。
- **Selectors**：用于在 CSS 选择器中访问 DOM 元素的方法。
- **Offset**：用于定位 DOM 元素的方法。
- **Utilities**：一组工具方法。

在开始学习 jQuery 之前，你需要将它引入你的项目中。一旦你安装了它并准备好在项目中使用它，下一步就是学习如何使用它。

首先，你需要按照以下方式在需要使用 jQuery 的网页上引用 jQuery 库：

```html
<script type="text/javascript" src="Scripts/qunit.js"></script>
<script src="Scripts/jquery-1.8.2.js"></script>
```

接下来需要知道，你希望在 HTML 页面使用的 jQuery 代码位于 jQuery 命名空间中，该命名空间有一个别名 `$`。因此，在引用 jQuery 的功能时，你可以编写 `jQuery.jFeature` 或 `$.jFeature`。

在开始在网页中使用它之前，你还需要按照如下方式修改 `default.js` 文件：



```javascript
function initialize() {
  txtInput = $('#txtInput');
  txtResult = $('#txtResult');
  clear();
}
```

这允许你通过 ID 匹配来使用 jQuery 和 CSS 选择器。

此外，当你继续使用 jQuery 进行编码时，请在做出任何更改后使用 `Ctrl+F5` 刷新屏幕，因为浏览器可能无法立即捕获 JavaScript 的修改。此外，要尽可能使用 jQuery 对象，因为它们提供了良好的跨浏览器兼容性。

可以通过以下方式从 jQuery 包装器引用 DOM 对象：

```javascript
var domElement = $('#txtInput')[0];
```

这是一个简单的代码，在引用元素之前检查该元素是否存在。

```javascript
var domElement;

if ($('#txtInput').length > 0) {
  domElement = $('#txtInput')[0];
}
```

## 如何创建 jQuery 包装来引用 DOM 元素

可以通过以下方式从 DOM 元素引用创建 jQuery 包装：

```javascript
var myDoc = $(document);
var inText = $(this).text();
```

第一个语句将包装的对象赋值给变量。而第二个语句则包装了使用 `this` 引用的对象。

## 如何添加事件监听器

jQuery 提供了 `.on` 方法来订阅事件。此外，你可以使用 `.off` 方法取消订阅。这些方法可以使用以下方式使用：

```javascript
$('#btnSubmitInfo').on('click', onSubmit);
$('#btnSubmitInfo').off('click', onSubmit);
```

## 如何触发事件处理器

jQuery 提供了 `trigger` 或 `triggerHandler` 方法来触发事件处理器或处理器代码的执行。可以通过以下方式实现：

```javascript
$('#btnSubmitInfo').triggerHandler('click');
```

## 初始化代码

你经常会面临加载 HTML 文档时运行初始化代码的需求。你可以通过以下方式使用 jQuery 实现：

```html
<script>
$(document).ready(function () {
  initializationFunction();
});
</script>
```

这可以放在 HTML 文档的底部。它将调用 `initializationFunction`。

# 第 7 章：表单

在之前的章节中，你已经学习了如何创建和操作 HTML 文档。借鉴这些，我们现在开始理解表单，它是网页开发中最关键和常用的内容单元之一。

简单来说，表单是一种收集数据并将其发送到可以处理的地方（大多数情况下是服务器）的方法。然而，由于我们还没有讨论服务器脚本，我们将重点关注将数据发送到电子邮件地址。但是，请注意，我们不建议这种做法，它仅用于理解目的。

## 网络通信

在进入表单的工作之前，了解 HTTP 的基础知识非常重要。典型的网络通信由以下活动组成：

1. 当用户浏览网页时，通过发送 `GET` HTTP 请求来启动对 Web 服务器资源的访问请求。
2. 经由服务器处理请求，并使用 HTTP 协议向浏览器发送响应。
3. 浏览器处理服务器响应，并以“表单”的形式呈现给用户。
4. 用户向表单输入内容，并在点击提交或回车键后，数据再次使用 HTTP 协议发送到服务器。
5. 这些数据再次由服务器处理，服务器将其响应发布到浏览器，并显示在网页上。

## Web 服务器

最初，Web 服务器的设计目的是为了接收和处理请求，并使用 HTTP 将结果传回浏览器。最初，当网页非常简单时，此类 Web 服务器能够在单位时间内处理大量请求。当时不涉及状态，因为发送和接收请求就像打开连接、传输数据和关闭连接一样简单。

新时代的 Web 服务器比这些简单的 Web 服务器强大得多。现在的 Web 服务器实现了所谓的“保持连接”（`keep alive`）功能，这确保了连接在一定时间内保持开放，以便同一个浏览器向服务器发送后续请求。

## Web 浏览器

Web 浏览器是一个桌面应用程序，用于显示网页并管理网页与服务器之间的用户交互。Web 服务器与页面之间的通信是通过 `AJAX` 等技术建立的。

## 数据如何提交到 Web 服务器

可以使用以下代码创建 HTML 表单：

```html
<form method="post">
  <input type="text" name="Customer">
  <input type="submit" value="Get Information" />
</form>
```

允许的元素有：

- `<textarea>` - 多行输入
- `<button>` - 按钮
- `<select>` - 下拉列表，允许多选
- `<input type="checkbox">` - 复选框。选中复选框的 jQuery 选择器为 `$('input[type=checkbox]:checked')`
- `<input type="button">` - 可点击按钮
- `<input type="datetime">` - 日期时间（UTC）
- `<input type="date">` - 仅日期
- `<input type="email">` - 邮箱字段
- `<input type="color">` - 颜色选择器
- `<input type="hidden">` - 隐藏输入字段
- `<input type="datetime-local">` - 日期时间（任何时区）
- `<input type="month">` - 月份年份
- `<input type="image">` - 图像提交按钮
- `<input type="password">` - 密码字段，带有掩码
- `<input type="number">` - 数字字段
- `<input type="range">` - 范围控件，接受数值并定义允许的值范围
- `<input type="radio">` - 单选按钮，具有 `value` 属性用于设置和读取状态。识别标记单选按钮的 jQuery 选择器为 `$('input[type=radio]:checked')`
- `<input type="search">` - 搜索字段，用于输入搜索字符串
- `<input type="reset">` - 用于重置表单字段的按钮
- `<input type="url">` - URL 字段
- `<input type="tel">` - 电话号码字段
- `<input type="submit">` - 提交按钮
- `<input type="time">` - 时间控件，接受时间值
- `<input type="text">` - 单行文本字段
- `<input type="week">` - 周年份控件

## `<label>` 元素

它是用于向用户传达元素含义的元素。该元素中的文本显示在文本框内，当用户点击时会自动移除。你还可以指定 label 的样式。

## 指定父表单

可能会出现表单的提交元素并不位于同一个结构中的情况。因此，在这种情况下，收集数据可能是一个巨大的挑战。为了针对此问题，HTML5 提供了一个 `id` 属性，可以为多个表单元素设置。这允许一次性地从不同的表单元素中收集数据。

## 如何触发表单提交

触发后，从表单提交元素或具有相同 `id` 的表单收集的所有数据将通过 HTTP 方法发送到服务器。`<input>` 元素可以触发表单提交。此外，你也可以使用 JavaScript 实现此目的。为了实现这一点，你必须给相关的表单指定一个 `id`，例如 `myFirstForm`。链接到 HTML 文档的 `default.js` 文件必须包含以下代码：

```javascript
$(document).ready(function () {
  $('#myFirstButton').on('click', submitMyFirstForm);
});

function submitMyFirstForm() {
  $('#myFirstForm').submit();
}
```

如果没有给表单 `method` 属性赋值，它将被设置为默认 `GET`。此外，`action` 属性也将有一个默认值。因此，点击按钮将引用到相同的页面。然而，现在 URL 将包含一个 `QueryString`，它是用户选择或输入的值的组合。例如，如果表单要求用户输入客户 ID，且用户输入了 1245，那么 `QueryString` 将是：

`customerID=1245`

该 `QueryString` 将按以下方式附加到 URL：

`Mywebpage.asp? customerID=1245`

这里还需要提到的一点是 `QueryString` 是经过 URI 编码的。因此，特殊字符由特定的值表示。例如，空格表示为 `+`，感叹号 (`!`) 表示为 `%21`。键值对表示为 `name=value`，且多个键-值对之间用 `&` 分隔。

## 如何序列化表单

你可以使用 jQuery 的 `serialize` 方法对表单进行序列化。可以通过以下方式实现：

```javascript
var myFormData = $('#myFirstForm').serialize();
```

你可以使用以下代码解码经过 URI 编码的字符串：

```javascript
var data = decodeURIComponent(myFormData);
```

## 使用 `autofocus` 属性

默认情况下，焦点不会设置在表单的任何元素上。但是，你可以使用 `focus` 方法设置焦点，其实现方式如下：

```javascript
$('input[name="firstName"]').focus();
```

然而，你也可以通过以下方式设置 `autofocus`：

```html
<input type="text" name="firstName" autofocus="autofocus"/>
```

## 如何使用数据提交约束

表单只有满足以下约束时才能发送数据：

- 必须设置 `name` 属性。
- 你必须设置表单提交元素的值。
- `<form>` 元素必须定义了其表单提交元素，且提交元素不应被禁用。
- 如果实现了多个提交按钮，值只有在点击激活的提交按钮时才会提交。
- 选择复选框。
- 选择单选按钮。
- `<option>` 元素必须设置 `<option>` 元素。
- 如果有文件选择字段，必须选择其中一个字段。
- `object` 元素的 `declare` 属性必须被设置。

始终记住，重置按钮不会发送任何数据，且表单不需要 `ID` 即可发送数据。

## 如何使用 POST 或 GET

有两种 HTTP 方法可用于向服务器提交数据。这些方法是 `GET` 和 `POST`。在一种情况下，URL 会附加 `QueryString`；而在另一种情况下，信息是在消息正文中发送的。

## 表单验证

了解应用程序所有安全问题的根源在于用户数据是有益的。当你决定向用户数据和交互开放应用程序时，你就让你的应用程序容易受到安全威胁。因此，你需要在处理接收到的任何数据之前对其验证，以防止任何问题的出现。验证可以在浏览器端或服务器端进行。但是推荐使用服务器端验证，因为浏览器级别的验证很容易被操纵。

你可以实现的简单验证形式是使用 `<select>` 元素中的 `required` 属性。你可以按照以下方式设置此属性：

```html
<select name="dateBirth" required="required">
```

生成的验证错误取决于浏览器，每个浏览器都有不同的用户通信方式来告知某个字段是必填的。

此外，`placeholder` 属性也是可用的，它会在未填写的字段上保持固定的提示，直到用户提供该字段的值。它可以通过以下方式实现：

```html
<input type="text" name="Date of birth" required="required" placeholder="enter the date of birth">
```

HTML5 中增加了时间、日期和基于类型的输入使得验证变得简单得多，因为它们可以直接进行匹配以检查它们是否具有有效的输入值。此外，电子邮件、数字和范围也可以被轻松地验证。

HTML5 执行验证并将其与 `:valid` 或 `:invalid` 伪类进行匹配。如果验证成功，值将匹配 `:valid`，否则匹配 `:invalid`。然而，如果一个值不是“required”，它将匹配到 `:optional` 伪类。

# 第 8 章：WEB 服务

到目前为止的所有章节都处理浏览器级别的编码和脚本。然而现在是时候转向服务器端脚本了。本章重点关注通过 Node.js 如何在服务器级别使用 JavaScript，以及你如何处理 Web 服务。

## Node.js 基础

Node.js 是一个允许你在服务器上运行 JavaScript 的平台。它是基于 Google 的 V8 引擎构建的。它高度可扩展且运行速度快，是构建实时应用的理想选择。

## 编写基础代码

要开始使用 Node.js，你需要创建一个 `.js` 扩展的文件并在其中编写代码。

```javascript
var http = require('http');

var server = http.createServer(function(request, response) {
  response.setHeader('Content-Type', 'text/plain');
  response.end('Hello World');
});

server.listen(8080, function() {
  console.log('Server is running at http://localhost:8080/');
});
```

你可以通过在终端中使用命令 `node filename.js` 来运行此代码。然后打开浏览器并导航到 `http://localhost:8080` 来查看输出。

```javascript
exports.start = start;
```

当你将这段代码保存到文件中时，就会创建一个模块。其他函数可以通过 `require` 函数来使用该模块。例如，如果文件被保存为 `sample1.js`，则可以在另一个函数中通过以下方式使用 `start()`：

```javascript
var samplex = require('./sample1.js');
sample1.start();
```

## 如何创建 Node.js 包 (package)

模块的集合被称为应用程序。一旦你发布了你的包，它就可以被安装和使用。例如，考虑一个包含不同数学模块的包。

根文件夹必须包含以下内容：

- `README.md` / 名称
- `/lib`
  - `main.js`
- `/bin`
  - `mod1.js`
  - `mod2.js`

## 创建聚合模块

你可能希望只为用户提供一个访问对象。用户应该能够通过该对象访问包中的所有模块。为了实现这一点，必须在 `bin` 文件夹中创建一个 `main.js` 模块，该模块必须定义包含在 `module.exports` 中的模块。

## 如何创建 README.md 文件

`README.md` 文件是一个帮助文件，开发者可以将其作为使用你的包的启动指南。该文件的扩展名为 `.md`，是 markdown 的缩写。这种格式为该文件中编写的文本提供了可读性。

下面是此类类型的示例文件：

```
samplePackage package
=============
```

在 `samplePackage` 中，可以使用以下函数：

- `add` 执行两个数字的相加并显示结果。
- `sub` 执行一个数字减去另一个数字并显示结果。

## 如何创建 package.json 文件

此文件包含包的元数据，可以使用命令手动创建：

```bash
npm init
```

该命令会创建该文件，稍后可以对其编辑。下面是一个示例文件：

```json
{
  "name": "sampleFile",
  "version": "0.0.0",
  "description": "This is a sample file ",
  "main": "bin/main.js",
  "scripts": {
    "test": "echo \"This is a test file\" && exit 1"
  },
  "repository": "",
  "keywords": [
    "sample",
    "example",
    "add",
    "sub"
  ],
  "author": "XYZ",
  "license": "ABC"
}
```

除了测试脚本外，你还可以提供 git 脚本，它们是目前可用的源码控制管理器。

## 如何发布包

如之前所述，包可以根据文件夹结构来定义。当你发布你的包时，你让所有用户都能访问它。为了执行此操作，你必须使用 `npm` 命令，这也是用于搜索和安装包的命令。然而，在使用命令 `npm adduser` 发布任何包之前，你将需要为自己创建一个账户。在输入所需信息后，你的账户就会被创建。但是，这意味着不需要任何验证。因此，任何人都可以向仓库添加代码。因此，在从注册表下载和安装包时，你应该小心。

要发布一个包，你只需要进入包的根目录并在命令提示符中输入命令 `npm publish`。

## 如何安装和使用包



已发布的包可以被任何用户下载和安装。你只需要进入文件夹并输入命令 `npm install samplePackage`。这会将包安装到本地。另一方面，如果你想全局安装该包，可以输入命令 `npm install -g samplePackage`。对于全局安装，你将需要使用命令 `npm link samplePackage` 创建每个应用程序到全局安装的链接。

```javascript
var samplePackage = require('samplePackage');
```

```javascript
app.use('/forms', express.static(__dirname + '/public'));

app.post('/SubmitHeyPost', function (request, response) {
  if (request.method.toLowerCase() == 'post') {
    var form = new formidable.IncomingForm();

    form.parse(request, function (err, fields) {
      response.write(200, { 'Content-Type': 'text/html' });

      response.write('Hey ' + fields.userName + '!<br/>');

      response.end('Enjoy this POST.');

      console.log('Handled request from ' + fields.userName);
    });
  }
});

app.get('/SubmitHey', function (request, response) {
  response.write(200, { 'Content-Type': 'text/html' });

  response.write('Hey ' + request.query.userName + '!<br/>');

  response.end('Enjoy.');

  console.log('Handled request from ' + request.query.userName);
});

var port = 8080;

app.listen(port);

console.log('Listening on: ' + port + 'port');
```

6. 你现在可以像之前的示例中一样运行该应用程序了。

## 使用 Web 服务

典型网站场景最大的缺点之一是，即使新页面与之前的页面相同，HTML 页面也会重绘。这会导致你浪费带宽和资源。这一缺点可以通过 Web 服务来解决，Web 服务用于发送和接收数据，其优点是 HTML 页面不需要重绘。用于发送请求的技术是 AJAX（异步 JavaScript 和 XML）。这种技术允许你异步执行数据发送操作。

在继续之前，了解 Web 服务的基础知识以及如何使用它们至关重要。客户端需要定期与 Web 服务器进行通信，这种通信通过 Web 服务来实现。在这种情况下，客户端可以是任何使用 Web 服务的机器，也可以是 Web 服务本身。因此，无论客户端是什么，都需要创建并向 Web 服务发送请求，并接收和解析响应。

你一定听过“集结合”（mashups）这个词，它用于描述将多个 Web 服务组合在一起的应用程序。存在两大类 Web 服务：任意 Web 服务（arbitrary web services）和 REST（表述状态转移）。在第一种情况下，操作集是任意的，而在第二种情况下，存在一个统一的操作集。

## 表述状态转移 (REST)

该框架使用标准的 HTTP 操作，这些操作映射到它的创建、删除、更新和检索操作。此外，REST 不关注与消息的交互。相反，它的交互关注于无状态资源。这可能就是 REST 用于用于创建整洁 URL 的原因。REST URL 的示例包括 `httplocalhost:8080/Customers/2`（用于删除客户）和 `http://localhost:8080/Vehicles?VIN=XYZ12`（用于通过 GET 方法传递参数来检索特定车辆的信息）。

某些防火墙可能不允许使用 POST 和 GET 方法。因此，建议在 QueryString 中使用“动”（verb）。URL 的示例如下：

`http://localhost:8080/Vehicles?verb=DELETE&VIN=XYZ987`

HTTP 协议还允许你使用 HTTPS 实现安全。REST 提供了许多优势，如连接简单、操作快速和资源消耗少。然而，许多开发者倾向于使用 JSON（JavaScript 对象表示），因为其体积紧凑。此外，REST 只支持 GET 和 POST，这限制了它的功能，因此，一些开发者切换到了 RESTFUL。

## 任意 Web 服务

这类 Web 服务也被称为“大型 Web 服务”。此类服务的示例是 WCF（Windows 通信框架）。任意 Web 服务通过不将操作仅映射到协议的某些方面来扩展其操作领域。结果是，它们提供了更多功能，包括许多安全机制和消息路由。

这类 Web 服务具有一种典型的接口格式，客户端可以使用它来读取和解析信息。因此，客户端可以立即调用服务。常见的 API 格式是 Web 服务描述语言（WSDL）。对于任意 Web 服务，客户端必须借助 SOAP（简单对象访问协议）消息来组装其请求。这种 Web 服务不使用 HTTP 协议，而是使用 TCP。

## 如何使用 Node.js 创建 RESTful Web 服务

在之前提到的示例中，`samplePackage` 可以暴露为 Web 服务。可以在该包上使用 GET 方法，并将操作作为参数传递。该包良好的 RESTful 实现可能像这样：

```
http://localhost:8080/samplePackage?operation=add&x=1&y=5
```

## 如何使用 AJAX 调用 Web 服务

可以使用 AJAX 异步调用 Web 服务，AJAX 实际上是 JavaScript。AJAX 不是向服务器发送调用并重绘 HTML 文档，而是直接回调服务器。在这种情况下，屏幕不会重绘。下面给出了示例实现：

可以使用以下代码创建一个 `MyPage.html`：

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<title></title>
<script type="text/javascript" src="scripts/jquery-1.8.2.min.js"></script>
</head>
<body>
<form id="myForm">
输入 X 的值:<input type="text" id="x" /><br />
输入 Y 的值:<input type="text" id="y" /><br />
结果: <span id="finalResult"></span><br />
<button id="btnAdd">数字相加</button>
</form>
<script type="text/javascript" src="scripts/default.js"></script>
</body>
</html>
```

## 如何使用 XMLHttpRequest

实际执行 AJAX 用的对象是 `XMLHttpRequest`，它可以用于发送/接收 XML 和其他类型的数据。该对象可以使用以下方式使用：

```javascript
var xmlhttp=new XMLHttpRequest();
xmlhttp.open("GET","add?x=50&y=1",false);
xmlhttp.send();
var xmlDoc=xmlhttp.response;
```

第一行创建对象，第二行设置使用带有 QueryString 的 GET 方法，使用“false”表示操作必须异步执行。下一行发送请求，最后一行将响应设置给变量，稍后可以进行读取和解析。

然而，生成的输出是 JSON 而不是默认的（XML），因此，`default.js` 文件必须更改为：

```javascript
$(document).ready(function () {
  $('#btnAdd').on('click', addTwoNum);
});

function addTwoNum() {
  var x = document.getElementById('x').value;
  var y = document.getElementById('y').value;
  var result = document.getElementById('finalResult');
  var xmlhttp = new XMLHttpRequest();
  xmlhttp.open("GET", "add?x=" + x + "&y=" + y, false);
  xmlhttp.send();
  var jsonObject = JSON.parse(xmlhttp.response);
  result.innerHTML = jsonObject.result;
}
```

该代码从 `<input>` 元素提取 x 和 y 的值。随后，创建一个 `XMLHttpRequest` 对象并使用 QueryString 调用 `open` 方法。执行 `send` 函数后，解析响应字符串。为了测试页面，你可以输入命令：

`node app`

该命令启动 Web 服务，之后你就可以用浏览器窗口打开链接：

`http://localhost:8080/SamplePage.html`

该代码现在可以运行了。然而，你可能希望在异步中执行 AJAX 调用

异步方式。为此，你必须找到 `open` 方法并将‘false’ 参数更改为‘true’。此外，你还需要订阅 `onreadystatechange` 来管理异步调用。这可以通过以下方式实现：

```javascript
function addTwoNum () {
  var a = document.getElementById('a').value;
  var b = document.getElementById('b').value;
  var result = document.getElementById('finalResult');
  var xmlhttp = new XMLHttpRequest();

  xmlhttp.readyState = function () {
    if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
      var jsonObject = JSON.parse(xmlhttp.response);
      result.innerHTML = jsonObject.result;
    }
  }

  xmlhttp.open("GET", "/add?a=" + a + "&b=" + b , true);
  xmlhttp.send();
}
```

状态对应的代码如下：

- 0 - 未初始化
- 1 - 加载中
- 2 - 已加载
- 3 - 交互中
- 4 - 已完成

如果服务器提供了进度事件，你可以订阅浏览器的进度事件。然后，可以添加一个事件监听器，在事件触发时启动代码执行。这可以通过以下方式实现：

```javascript
function addTwoNum () {
  var a = document.getElementById('a').value;
  var b = document.getElementById('b').value;
  var finalResult = document.getElementById('finalResult');
  var xmlhttp = new XMLHttpRequest();

  xmlhttp.onreadystatechange = function () {
    if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
      var json = JSON.parse(xmlhttp.response);
      result.innerHTML = json.result;
    }
  }

  xmlhttp.addEventListener("progress", updateProgress, false);
  xmlhttp.open("GET", "/add?a=" + a + "&b=" + b , true);
  xmlhttp.send();
}

function updateProgress(evt) {
  if (evt.lengthComputable) {
    var percentComplete = evt.loaded / evt.total;
    //通过输出 percentComplete 来显示进度
  } else {
    // 你需要知道总大小来计算进度
  }
}
```

你还可以通过订阅错误事件和中止（abort）事件来执行错误处理。

这可以通过以下方式实现：

```javascript
function addTwoNum () {
  var a = document.getElementById('a').value;
  var b = document.getElementById('b').value;
  var finalResult = document.getElementById('finalResult');
  var xmlhttp = new XMLHttpRequest();

  xmlhttp.onreadystatechange = function () {
    if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
      var jsonObject = JSON.parse(xmlhttp.response);
      result.innerHTML = jsonObject.result;
    }
  }

  xmlhttp.addEventListener("progress", updateProgress, false);
  xmlhttp.addEventListener("error", failed, false);
  xmlhttp.addEventListener("abort", canceled, false);

  xmlhttp.open("GET", "/addition?x=" + x + "&y=" + y, true);
  xmlhttp.send();
}

function transferFailed(evt) {
  alert("发生了一个错误");
}

function canceled(evt) {
  alert("被用户取消");
}
```

了解不同浏览器以不同的方式实现和响应对象对你也有益。因此，建议你必须使用 `XMLHttpRequest` 的 jQuery 封装。使用 jQuery 可以使代码独立于浏览器。用于 AJAX 调用的 jQuery 封装是 `$ajax()`，它接受一个对象作为参数。上面的代码可以通过以下方式重新实现：

```javascript
function addTwoNum() {
  var a = $('#a').val();
  var b = $('#b').val();
  var data = { "a": a, "b": b };

  $.ajax({
    url: '/add',
    data: data,
    type: 'GET',
    cache: false,
    dataType: 'json',
    success: function (data) {
      $('#result').html(data.result);
    }
  });
}
```

变量值被获取并提供给 ajax 调用。其他属性对象的设置所示。另一个关注的话题是 CORS，或跨源资源共享，这是允许跨站 AJAX 调用的一种方法。

# 第 9 章：WebSocket 通信

在某些场景下，可能需要在客户端和服务器之间建立双向通信。需要这种通信形式的示例应用程序是聊天应用程序。本章详细研究了如何建立和使用 WebSocket 通信。

## 使用 WebSocket 进行通信

WebSocket 通信是通过 WebSocket 协议建立的，该协议使用 TCP 连接建立全双工通信通道。该协议已由 IETF 标准化（RFC 6455），WebSocket API 的工作草案在 W3C 中。

这项技术已经取代了长轮询（long polling）的概念。在这种情况下，客户端发送请求并一直等待响应，直到收到响应为止。这种方法的好处是连接保持开启状态，当数据可用时，会立即发送。然而，连接可能会超时并需要重新建立。

## 理解 WebSocket 协议

WebSocket 协议允许客户端与服务器之间的双向通信。当创建一个 WebSocket 对象时，会触发事件。如果发生错误，会调用 `onError` 函数。在发送任何消息之前，会检查对象的 `readyState` 属性。其属性值如下：

- 3 - CLOSED
- 2 - CLOSING
- 1 - OPEN
- 0 - CONNECTING

## 定义 WebSocket API

WebSocket API 有以下成员：

- `close`
- `binaryType`
- `bufferedAmount`
- `extensions`
- `hostname`
- `onclose`
- `onerror`
- `onmessage`
- `onopen`
- `readyState`
- `send`

## 如何实现 WebSocket

WebSocket 对象可以通过以下方式实现：



```javascript
// <reference path="_references.js" />

var WebSocket;

function connect() {
  WebSocket = new WebSocket(wsUri);

  WebSocket.onopen = function (evt) {
    onOpen(evt);
  };

  WebSocket.onclose = function (evt) {
    onClose(evt);
  };

  WebSocket.onmessage = function (evt) {
    onMessage(evt);
  };

  WebSocket.onerror = function (evt) {
    onError(evt);
  };
}

function doSend() {
  if (WebSocket.readyState != 1) { // 1 是 OPEN
    writeOutput("NOT OPEN");
    return;
  }
  WebSocket.send($('#txtMessage').val());
}

function onOpen(evt) {
  writeOutput("CONNECTED");
}

function onClose(evt) {
  writeOutput("DISCONNECTED");
}

function onMessage(evt) {
  writeOutput('RESPONSE: ' + evt.data);
}

function onError(evt) {
  writeOutput('ERROR: ' + evt.data);
}

function checkSupported() {
  if (window.WebSocket) {
    writeOutput('WebSocket is supported!');
    return true;
  } else {
    writeOutput('WebSockets is not supported');
    $('#btnSend').prop('disabled', true);
    return false;
  }
}

function writeOutput(message) {
  $('#div').append(message + '<br>');
}
```

## 如何处理超时

当没有活动持续 20 分钟时，就会识别为超时。处理超时有效的方法之一是定期向服务器发送空消息。可以通过以下方式实现。

```javascript
var timerId = 0;

function resetTimer() {
  clearInterval(timerId);
  timerId = setInterval(function() {
    WebSocket.send("");
  }, 20 * 60 * 1000); // 20 分钟
}
```

```javascript
function writeOutput(message) {
  var output = $("#divOutput");
  output.html(output.html()) + '<br />' + message;
}
```

```javascript
function checkSupported() {
  if (window.WebSocket) {
    writeOutput('WebSockets supported!');
    return true;
  }
}
```

```javascript
else {
  writeOutput('WebSockets NOT supported');
  $('#btnSend').attr('disabled', 'disabled');
  return false;
}
```

```javascript
function connect() {
  WebSocket = new WebSocket(wsUri);
  WebSocket.onopen = function(evt) { onOpen(evt) };
  WebSocket.onclose = function(evt) { onClose(evt) };
  WebSocket.onmessage = function(evt) { onMessage(evt) };
  WebSocket.onerror = function(evt) { onError(evt) };
}
```

```javascript
function keepAlive() {
  var timeout = 15000;
  if (WebSocket.readyState == WebSocket.OPEN) {
    WebSocket.send('');
  }
  timerId = setTimeout(keepAlive, timeout);
}

function cancelKeepAlive() {
  if (timerId) {
    cancelTimeout(timerId);
  }
}

function doSend() {
  if (WebSocket.readyState != WebSocket.OPEN) {
    writeOutput('NOT OPEN: ' + ($('#txtMessage').val()));
    return;
  }
  writeOutput('SENT: ' + ($('#txtMessage').val()));
  WebSocket.send($('#txtMessage').val());
}
```

```javascript
function onOpen(evt) {
  writeOutput("CONNECTED");
  keepAlive();
}
```

```javascript
function onClose(evt) {
  cancelKeepAlive();
  writeOutput("DISCONNECTED");
}
```

```javascript
function onMessage(evt) {
  writeOutput('RESPONSE: ' + evt.data);
}
```

```javascript
function onError(evt) {
  writeOutput('ERROR: ' + evt.data);
}
```

## 如何处理断开

连接有时会因为网络错误而关闭。因此，你可能需要在 `onClose` 函数的结构内部调用 `connect` 函数。这可能会导致问题。在这方面面临的一个常见问题是，服务器无法识别这个新连接请求属于一个已存在的客户端。你可以通过向服务器发送身份标识消息来处理此问题。

## 如何处理 Web 集群

你可能需要在 Web 集群中运行你的应用程序，在这种情况下，传入的请求可能由许多服务器处理。使用多个服务器来进行负载均衡和性能优化。在这种情况下，你可以实现“会话保持”（sticky servers），确保客户端仅由一台服务器提供服务。换句话说，一个客户端的所有请求都由同一台服务器处理。这有助于你解决由于打开连接可能出现的问题。这些问题也可以使用 Microsoft App Fabric Caching Service 和 Redis 等产品来处理。

## 如何使用 WebSocket 库

处理上述所有问题可能具有挑战性。因此，处理这种情况的最佳方法是使用服务器和客户端库。目前有如 SignalR 和 Socket.IO 等库供你探索。

# 第 10 章：借助 Web 存储管理本地数据

上一节讨论的大部分主题侧重于提高网站及其向客户提供的服务的性能。因此，信息或数据处理被限制在客户端和服务器之间传输的数据。在这种情况下，服务器需要等待整个往返过程完成。这涉及到成本开销。

为了解决这个问题，大多数现代浏览器已开始支持 Web 或 DOM 存储，这允许在客户端级别存储某些数据。本章提供了所用存储机制的概述，以及如何使用它们在这方面提高系统性能。

## Web 存储简介

在大多数 Web 应用程序中，会实现类似 SQL Server 的服务器端存储解决方案。这可能是“用剑杀蚊子”。你不需要如此巨大的解决方案，因为在浏览器级别存储少量信息就可以达到你的目的。

Http Cookie 一直是浏览器级别最常用且常用的数据存储形式。事实上，大多数浏览器都使用它来存储用户信息。Cookie 值可以按以下方式设置：

```javascript
function setCookieValue(cName, cValue, daysToExpire) {
  var daysToExpire = new Date();
  daysToExpire.setDate(daysToExpire.getDate() + daysToExpire);
  cValue = cValue + " expires=" + daysToExpire.UTCString();
  document.cookie = cName + "=" + cValue;
}
```

可以使用以下代码获取 Cookie 值：

```javascript
function getCookieValue(cName) {
  var cookie = document.cookie.split(";");

  for (var i = 0; i < cookie.length; i++) {
    var cookies = cookie[i];

    var indexVal = cookies.indexOf("=");

    var keyVal = cookies.substr(0, indexVal);
    var actualVal = cookies.substr(indexVal + 1);

    if (keyVal == cName) {
      return actualVal;
    }
  }
}
```

下面显示的最后一段代码描述了如何使用 Cookie。

```javascript
setCookie('fName', 'Clark', 1);
var fName = getCookieValue('fName');
```

你也可以为此目的使用给出的结构：

```javascript
setCookie('fName', 'Clark');
var fName = getCookieValue('fName');
```

## HTML5 存储

- Web Storage
- Web SQL 数据库
- IndexedDB
- 文件系统 API

## 探索 localStorage

LocalStorage 是用于存储数据的两种机制之一。它本质上是一个存储对象，作为全局变量存储。使用这种机制最大的优势是提供的读写 API 简单易用。

## 如何使用 localStorage 对象引用

属性和方法包括：

- `setItem(key, value)`
- `getItem(key)`
- `removeItem(key)`
- `clear()`
- `length`
- `key(index)`

```javascript
function isWSSupported() {
  return 'localStorage' in window;
}

if (isWSSupported()) {
  localStorage.setItem('fName', ('#fName').val());
}
```

除此之外，你还可以使用 Modernizr JavaScript 库进行检测。值得提到，这种类型的 Web 存储允许 5MB 的存储空间，而 cookie 仅允许 4KB 的存储空间。当超过存储空间时，系统会抛出相应的异常。

虽然 Web 存储只允许存储字符串，但你也可以借助 JSON 工具方法来存储复杂对象。

## 如何使用 sessionStorage 进行短期持久化

sessionStorage 也是一个存储对象，具有与 localStorage 相同的属性和方法。两种存储机制之间的唯一区别在于 sessionStorage 仅为当前会话存储数据。如果浏览器窗口关闭，数据将无法再次使用。

## 与 sessionStorage 和 localStorage 的相关问题

与这两个存储机制的一些问题包括：

1. 硬盘的并发读写。
2. 搜索能力较慢。
3. 不支持事务。

## 如何处理存储事件

同步是在 Web 存储实现中面临的最大挑战。为了解决这个问题，你可以订阅存储事件，它可以通知你可能发生的任何更改。当你订阅 `StorageEvent` 时，可以访问以下属性：

- `newValue`（新值）
- `oldValue`（旧值）
- `url`
- `storageArea`（存储区域）

与其他事件不同，`StorageEvent` 不允许取消或冒泡。你可以使用以下构造结构来订阅事件：

```javascript
function respond (exc) {
  alert(exc.newValue);
}

window.addEventListener('storage', respond, false);
```

该事件可以通过以下操作触发：

`localStorage.setItem('name', 'Clark');`

你也可以借助 jQuery 绑定到这些事件上。

# 第 11 章：离线 Web 应用

上一章讨论了存储，这是最常用的离线应用之一。然而在某些场景下，你可能需要更好的工具和高级功能，如索引、异步支持和事务处理。这些功能是许多其他可用离线应用的一部分。

本章讨论了 Web SQL 和 IndexedDB，它们是用于数据存储的关系型结构。然而，它们不能用于存储文件。因此，FileSystem API 用于此目的。本章最后讨论了如何使用 HTTP 缓存让你的网站支持离线。

## Web SQL

Web SQL 是一个关系型数据库，其最新的实现是基于 SQLite 的。然而，需要提到，该数据库规范不再被 W3C 支持，但许多浏览器仍然支持它。

## 如何创建和打开数据库

```javascript
var dbase = openDatabase('Lib', '1.0', 'Sample library', 5 * 1024 * 1024);
```

参数如下：

- `name`（名称）
- `version`（版本）
- `displayName`（显示名称）
- `estimatedSize`（估计大小）
- `creationCallback`（创建回调）

## 如何操作数据库

SQL 中的操作脚本可以作为参数传递给 `transaction.executeSql` 函数以操作数据库。下面是一个创建表的示例：

```javascript
transaction.executeSql("CREATE TABLE IF NOT EXISTS employees(" + 
  "id INTEGER PRIMARY KEY AUTOINCREMENT, " + 
  "fName TEXT, " + 
  "lName TEXT" + 
  ")");
```

## IndexedDB

到目前为止，你已经处理了 Web 存储数据的两种极端情况。Web 存储机制遵循简单的键值对模型，而 Web SQL 基于关系型数据库模型。IndexedDB 是一个介于这两种模型之间的替代模型。它能够处理从字符串到复杂对象的一切。然而，在使用这种存储机制时，请使用与浏览器无关的方法。

可以通过以下方式打开或创建数据库：

```javascript
var indexedDB = window.indexedDB;
var openRequest = indexedDB.open('Lib', 1);
```

IndexedDB 对象的一个重要方面是 `keypath` 属性，它用于定义必须用作键的属性。如果指定的属性不存在，可以创建一个自动递增或自动递减的属性。

可以使用以下代码添加索引：

```javascript
var openRequest = indexedDB.open('Lib', 2);

openRequest.onupgradeneeded = function(response) {
  var store = response.currentTarget.transaction.objectStore("employees");
  store.createIndex('lName', 'lName', { unique: false });
};
```

所需的参数是：`Name`（名称）、`keypath`（键路径）和可选参数。类似地，可以使用以下代码删除索引：

```javascript
store.deleteIndex('lastName');
```

你可以使用以下代码添加和删除存储对象：

```javascript
var openRequest = indexedDB.open('Lib', 3);

openRequest.onupgradeneeded = function(response) {
  response.currentTarget.result.deleteObjectStore("employees");
};
```

同样，可以以以下方式添加对象：

`response.currentTarget.result.createObjectStore("employees", { keypath: 'email' });`

下一组操作包括事务，它们以以下方式执行：

1. 必须以以下方式打开事务：



# IndexedDB 操作示例

## 1. 添加新记录

```javascript
var openRequest = indexedDB.open('Lib', 1);
var dbase;

openRequest.onsuccess = function(response) {
  dbase = openRequest.result;
  addEmployee();
}

function addEmployee() {
  var myTrans = dbase.transaction('employees', 'readwrite');
  var employees = myTrans.objectStore("employees");
  var request = employees.add({fName: 'Sammy', lName: 'Clark'});

  request.onsuccess = function(response) {
    alert('New Record ID: ' + request.result);
  }
}
```

## 2. 更新记录

```javascript
var openRequest = indexedDB.open('Lib', 1);
var dbase;

openRequest.onsuccess = function(response) {
  dbase = openRequest.result;
  updateEmployee();
}

function updateEmployee() {
  var myTrans = dbase.transaction('employees', 'readwrite');
  var employees = myTrans.objectStore("employees");
  var request = employees.put({fName: 'Sammy', lName: 'Clarkie'});

  request.onsuccess = function(response) {
    alert('Updated Record ID: ' + request.result);
  }
}
```

## 3. 删除记录

```javascript
var openRequest = indexedDB.open('Lib', 1);
var dbase;

openRequest.onsuccess = function(response) {
  dbase = openRequest.result;
  deleteEmployee();
}

function deleteEmployee() {
  var myTrans = dbase.transaction('employees', 'readwrite');
  var employees = myTrans.objectStore("employees");
  var request = employees.delete(1);

  request.onsuccess = function(response) {
    alert('Deleted Record ID: ' + request.result);
  }
}
```

# 如何使用 FileSystem API

上述存储机制可以用于存储字符串形式的数据。然而，复杂数据结构如文件和图像也可以通过 URI 存储。但是，这是一个成本极高的选项。HTML5 为此目的提供了一个低成本且更简单的 File API。使用这种格式，你可以在用户文件系统的沙盒位置创建文件和目录。

## 可用功能

### 1. 打开并创建文件系统

```javascript
window.requestFileSystem(TEMPORARY, 5 * 1024 * 1024, getFile, handleError);

function getFile(FileSystem) {
  FileSystem.root.getFile("sample.txt", { create: true }, fileOpened, handleError);
}

function fileOpened(fileEntry) {
  alert("File opened!");
}

function handleError(error) {
  alert(error.code);
}
```

### 2. 写入文件

```javascript
function writeFile(fileWriter) {
  fileWriter.onwrite = function() { alert('Success'); };
  fileWriter.onerror = function() { alert('Failed'); };

  fileWriter.write(new Blob(['Hello world'], {type: 'text/plain'})));
}
```

### 3. 向文件追加内容

```javascript
function writeToFile(fileWriter) {
  fileWriter.onloadend = function() { alert('Success'); };
  fileWriter.onerror = function() { alert('Failed'); };
  fileWriter.seek(fileWriter.length);
  fileWriter.write(new Blob(['Hello world'], {type: 'text/plain}));
}
```

### 4. 读取文件

```javascript
function readFile(file) {
  var fileReader = new FileReader();
  fileReader.onloadend = function() { alert(this.result); };
  fileReader.onerror = function() { alert('Failed'); };
  fileReader.readAsText(file);
}
```

### 5. 删除文件

```javascript
fileEntry.remove(fileRemoved, handleError);
```

目录也存在类似的函数。

# 附录：HTML 元素参考

- `<a>` 超链接
- `<abbr>` 缩写
- `<address>` 联系信息
- `<area>` 图像映射区域
- `<article>` 独立章节
- `<aside>` 辅助部分
- `<audio>` 音频流
- `<b>` 粗体文本
- `<base>` 文档基础 URI
- `<bb>` 浏览器按钮
- `<bdo>` 双向文本覆盖
- `<blockquote>` 长引用
- `<body>` 主体内容
- `<br>` 换行
- `<button>` 推送按钮
- `<canvas>` 位图画布
- `<caption>` 表格标题
- `<cite>` 引用
- `<code>` 代码片段
- `<col>` 表列
- `<colgroup>` 表列组
- `<command>` 用户可以调用的命令
- `<datagrid>` 交互式树、列表或表格数据
- `<datalist>` 预定义控制值
- `<dd>` 定义描述
- `<del>` 删除
- `<details>` 更多信息（详情）
- `<dfn>` 术语的定义实例
- `<dialog>` 对话
- `<div>` 通用分区块
- `<dl>` 描述列表
- `<dt>` 描述术语
- `<em>` 强调
- `<embed>` 嵌入应用
- `<fieldset>` 表单控制组
- `<figure>` 带有标题的插图
- `<footer>` 节页脚
- `<form>` 表单
- `<h1>` 一级标题
- `<h2>` 二级标题
- `<h3>` 三级标题
- `<h4>` 四级标题
- `<h5>` 五级标题
- `<h6>` 六级标题
- `<head>` 文档头部
- `<header>` 节页眉
- `<hr>` 分隔线
- `<html>` 文档根元素
- `<i>` 斜体文本
- `<iframe>` 内联框架
- `<img>` 图像
- `<input>` 表单控制项
- `<ins>` 插入
- `<kbd>` 用户输入
- `<label>` 表单控制标签
- `<legend>` 解释性标题或图例
- `<li>` 列表项
- `<link>` 指向资源的链接
- `<map>` 客户端图像映射
- `<mark>` 标记或高亮显示文本
- `<menu>` 命令菜单
- `<meta>` 元数据
- `<meter>` 标量测量
- `<nav>` 导航
- `<noscript>` 不支持脚本时的备用内容
- `<object>` 通用嵌入资源
- `<ol>` 有序列表
- `<optgroup>` 选项组
- `<option>` 选择控制
- `<output>` 输出控制
- `<p>` 段落
- `<param>` 插件参数
- `<pre>` 预格式文本
- `<progress>` 任务进度
- `<q>` 内联引用
- `<rp>` Ruby 注释括号
- `<rt>` Ruby 注释文本
- `<ruby>` Ruby 注释
- `<samp>` 示例输出
- `<script>` 链接或嵌入脚本
- `<section>` 文档章节
- `<select>` 选择控制
- `<small>` 小字号
- `<source>` 媒体资源
- `<span>` 通用内联容器
- `<strong>` 强强调
- `<style>` 嵌入样式表
- `<sub>` 下标
- `<sup>` 上标
- `<table>` 表格
- `<tbody>` 表格主体
- `<td>` 表格单元格
- `<textarea>` 多行文本控制
- `<tfoot>` 表格页脚
- `<th>` 表头单元格
- `<thead>` 表格头部
- `<time>` 日期和/或时间
- `<title>` 文档标题
- `<tr>` 表格行
- `<ul>` 无序列表
- `<var>` 变量
- `<video>` 视频或电影
- `<wbr>` 可选在此处断开大单词

# 赠品：免费书籍与特别优惠

再次感谢你下载这本书！我想向你提供一项很棒的服务，当有免费书籍可用时，它会通过电子邮件向你发送通知。你可以在这些书籍被标上正常零售价之前，免费获得一些优秀书目。这是一个为了感谢你作为优秀客户而提供的优惠，没有任何附带条件。只需点击下方链接即可开始。

![赠品图片](img/5b2f768a50799763f7f92e5b907a924b_142_0.png)

版权所有 2015 Globalized Healing, LLC - 保留所有权利。
