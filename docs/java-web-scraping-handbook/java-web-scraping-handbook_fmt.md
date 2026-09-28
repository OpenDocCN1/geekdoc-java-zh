
# Java Web 爬虫手册

## 目录
- 结论

# 网络爬取简介

网络爬取（Web scraping）或爬虫（Crawling）是指通过下载和解析 HTML 代码来从第三方网站获取数据的行为。这可以通过手动完成，但通常该术语指的是自动化下载页面的 HTML 内容、解析/提取数据，并将其保存到数据库中以供进一步分析或使用的自动化过程。

## 网络爬取 VS API

当一个网站想要向开发者社区开放数据/功能时，他们通常会构建一个 API（应用程序编程接口¹）。API 由一组 HTTP 请求组成，并通常以 JSON 或 XML 格式响应。例如，假设你想在代码中获取以太坊（Ethereum）加密货币的实时价格。你不需要爬取网站来获取这些信息，因为有很多 API 可以为你提供格式良好的数据：

```
curl https://api.coinmarketcap.com/v1/ticker/ethereum/?convert=EUR
```

以及响应内容：

> ¹https://en.wikipedia.org/wiki/Application_programming_interface

## Coinmarketcap JSON 响应

```
{
  id: "ethereum",
  name: "Ethereum",
  symbol: "ETH",
  rank: "2",
  price_usd: "414.447",
  price_btc: "0.0507206",
  24h_volume_usd: "1679960000.0",
  market_cap_usd: "39748509988.0",
  available_supply: "95907342.0",
  total_supply: "95907342.0",
  max_supply: null,
  percent_change_1h: "0.64",
  percent_change_24h: "13.38",
  percent_change_7d: "25.56",
  last_updated: "1511456952",
  price_eur: "349.84756557",
  24h_volume_eur: "1418106314.76",
  market_cap_eur: "33552949485.0"
}
```

我们也可以想象一个电子商务网站有一个 API，通过此端点列出所有产品：

```
curl https://api.e-commerce.com/products
```

它还可以通过以下方式公开产品详情（id 为“123”）：

```
curl https://api.e-commerce.com/products/123
```

由于并不是每个网站都提供整洁的 API，或者根本不提供 API，因此在提取网站信息时，网络爬取可能是唯一的解决方案。

## 为什么选择网络爬取而非 API

> [!INFO]

API 通常更容易使用，问题是许多网站不提供任何 API。对于公司来说，构建 API 可能是一项巨大的成本，你需要发布它、测试它、处理版本控制、创建文档，还有基础设施成本、工程成本等。API 的第二个问题是有时会有速率限制（你每天/每小时允许调用某个端点 X 次），第三个问题是数据可能是不完整的。

## 网络爬取用例

几乎所有内容都可以从 HTML 中提取，唯一“难以”提取的信息是图片或其他媒体内部的内容。以下是使用网络爬取的一些行业：

- 新闻门户：聚合来自不同数据源的文章：Reddit / 论坛 / Twitter / 特定新闻网站
- 房产中介机构
- 搜索引擎
- 旅游业（机票/酒店价格比较工具）
- 电子商务：监控竞争对手价格
- 银行：银行账户聚合（如 Mint 和其他类似应用）
- 新闻业：也称为“数据新闻”
- SEO（搜索引擎优化）
- 数据分析
- “数据驱动”的在线营销
- 市场研究
- 线索生成……

## 实际案例：Mint.com

如你所见，网络爬取有很多用例。

Mint.com 是一个个人财务管理服务，它允许你以集中的方式跟踪你拥有的账户以及许多其他功能。Mint.com 使用网络爬取为其客户执行账户聚合。这是一个经典问题，有些银行为此提供了 API，而另一些没有。因此当 API 不可用时，Mint.com 仍然能够提取账户操作。客户提供其凭据（用户 ID 和密码），Mint 使用网络爬取完成几件事：

- 进入银行网站
- 使用凭据填写登录表单
- 进入账户概览
- 针对每个账户，提取所有操作并保存到 Mint 后端
- 退出

通过这个过程，Mint 能够支持任何银行，无论是否存在 API，也无论银行使用什么技术。这是网络爬取有多用且强大的良好例子。当然，每当银行更改其网站（即使是 HTML 的微小变化），机器人也必须跟着更改。

## 实际案例：Parsely 仪表板

针对出版者的 Parsely 分析。其平台爬取整个网站以提取所有文章（文本、指标）并进行自然语言处理，让出版者能够了解观众喜欢或不喜欢什么。

## 实际案例：Jobijoba 搜索引擎

Jobijoba.com 是一家法国/欧洲初创公司，运行并聚合来自 Monster、CareerBuilder 等多个搜索引擎的列表。这里的价值主张显而易见：有数百甚至数千个平台，申请者需要在这些网站上创建个人资料进行搜索，而 Jobijoba 提供了一种简单的方法，在一个地方可视化所有内容。这种聚合问题在许多其他行业都很常见，正如我们之前看到的，房产、旅游、新闻、数据分析……

## 你在书中将学到什么

在 2017 年，网络爬取对于处理网络提供的海量数据变得越来越重要。在本书中你将学习如何：

- 使用网络爬取收集数据
- 使用 Chrome 开发者工具检查网站
- 解析 HTML 并存储数据
- 处理重依赖 JavaScript 的网站
- 寻找隐藏的 API
- 如何避免经典的陷阱和反爬虫技术

学习网络爬取可能具有挑战性，这就是为什么我的目标是解释足够的理论，以便理解。

# 基础知识

网络基础变得**非常复杂**，在许多技术中，你为了查看网页数据。HTTP 协议是一种分布、协作的、包含超链接的超媒体系统。

## 超文本传输协议

根据维基百科定义：

超文本传输协议（HTTP）是一种应用程序协议，用于分布、协作的、超媒体系统。[1] HTTP 是万维网的基础。

所以，在许多网络协议中，HTTP 使用**客户端/服务器**模型，HTTP 客户端（浏览器）打开连接。HTTP 被称为**无状态**协议，因为每次事务（请求/响应）都是独立的。FTP 例如，是**有状态**的。服务器响应**消息**（例如“我想看那个页面”）

## HTTP 请求结构

当你在浏览器中输入网站地址时，它会发送类似这样的 HTTP 请求：

### 请求

```
GET /how-to-log-in-to-any-websites/ HTTP/1.1
Host: ksah.in
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/*;q=0.8
Accept-Encoding: gzip, deflate, sdch, br
Connection: keep-alive
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36
```

在请求的第一行中，你可以看到使用的 `GET` 动词或方法，意味着我们从特定路径 `/how-to-log-in-to-any-websites/` 请求数据。还有其他的 HTTP 动词，你可以在这里查看完整列表。你可以看到 HTTP 协议的版本，在本书中关注 HTTP。注意截至 2017 年第四季度，前千万个网站中只有 20% 支持 HTTP/2。最后，这是一个键值列表，称为 Header。这里是重要的头部字段：

- `Host`：服务器的域名，如果没有提供端口号，假设为 80。
- `User-Agent`：包含发起请求的客户端信息，包括操作系统信息。在这种情况下，它是我的网络浏览器（Chrome），或 OSX。这个头部很重要，因为它被用于统计（有多少用户通过移动或桌面访问我的网站）以防止任何违规行为。由于这些头部是由客户端发送的，它可以被修改（这被称为“头部伪造”），这正是我们使用爬虫时所做的，让我们的爬虫看起来像正常的网页浏览器。
- `Accept`：接受作为响应的内容类型。有很多不同的内容类型和子类型：`text/plain`、`text/html`、`image/jpeg`、`application/json` ...

> https://www.w3schools.com/tags/ref_httpmethods.asp

## Web 基础：Cookie 与 Referer

- **Cookie**：`name1=value1;name2=value2...` 此标头字段包含一组键值对列表。它被称为会话 Cookie（session cookies），这些用于存储数据。Cookie 是网站用于验证用户身份和/或在你的浏览器中存储数据的工具。例如，当你填写登录表单时，服务器会检查你输入的凭据是否正确，如果是，它将重定向你并在你的浏览器中注入一个会话 Cookie。你的浏览器将在随后向该服务器发送的每个请求中携带此 Cookie。

- **Referer**：`Referer` 头部包含请求实际 URL 的来源 URL。此标头非常重要，因为网站使用它来根据用户的来源地改变自己的行为。例如，许多网站有付费订阅制，并允许你查看文章的 10% 内容，但如果用户来自 Reddit 这样的新闻聚合器，它们会允许你查看完整内容。它们使用 referer 来检查这一点。有时我们必须伪造此标头以获取内容提取。

列表以此类推……你可以在这里找到完整的标头列表³

> ³https://en.wikipedia.org/wiki/List_of_HTTP_header_fields

服务器响应的消息如下所示：

### HTTP 响应

```
HTTP/1.1 200 OK
Server: nginx/1.4.6 (Ubuntu)
Content-Type: text/html; charset=utf-8
<!DOCTYPE html>
<head>
  <meta charset="utf-8" />
  .. [HTML 代码]
```

在第一行，我们获得了一条新信息，HTTP 代码 `200 OK`。这意味着请求成功了。至于请求标头，有很多 HTTP 代码，分为四类常见的：

- `2XX`：成功、理解并被接受的请求
- `3XX`：这类状态码需要客户端采取操作以满足请求（通常请求新的 URL，位于响应标头的 `Location` 中）
- `4XX`：客户端错误：`400 Bad Request` 是由于请求中的语法不正确，`403 Forbidden` 服务器拒绝执行请求，`404 Not Found` 是最著名的 HTTP 代码，服务器未找到请求的资源。
- `5XX`：服务器错误

然后，如果你使用网络浏览器发送此 HTTP 请求，浏览器将解析 HTML 代码，获取所有的最终资源（JavaScript 文件、CSS 文件、图像...），并将结果渲染到主窗口。

# HTML 和文档对象模型 (DOM)

我假设你已经了解 HTML 了，所以这只是一个小的提醒。

- 超文本标记语言 (HTML) 用于为原始内容添加“意义”。
- 级联样式表 (CSS) 用于格式化这些标记后的内容。
- JavaScript 让这些内容具有交互性。

正如你所知道的，网页是一个包含标签内文本的文档，这些标签通过描述标题、段落、列表、链接等元素来为文档添加意义。让我们来看一个基础的 HTML 页面，以理解什么是文档对象模型。

## HTML 页面

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>DOM 是什么？</title>
</head>
<body>
  <h1>DOM 101 太棒极了！</h1>
  <p>网络爬虫是我的 <a href="https://ksah.in">博客</a></p>
</body>
</html>
```

这段 HTML 代码基本上是封装在其他 HTML 内容内部的 HTML 内容。HTML 的层级结构可以通过 HTML 代码中的缩进视为一棵树。当你的网络浏览器解析此代码时，它会创建一个树，它是 HTML 文档的对象的表示。它被称为文档对象模型（DOM）。

## DOM 101 与 Chrome 检查器

下面是 Chrome 检查器内部的树结构：

```
DOM 101 太棒极了！
网络爬虫是我的博客。

元素 | 控制台 | 来源 | 网络 | 性能 | 内存 | 应用 | 安全 | 审核 | Adblock Plus | Adblock | 样式 | 计算属性 | 事件监听器 | 属性
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---
<html> | | | | | | | | | | | | | | |
<head> | | | | | | | | | | | | | | |
<body> | | | | | | | | | | | | | | |
<h1> | DOM 101 太棒极了！ | | | | | | | | | | | | | | |
<p> | 网络爬虫是我的 | | | | | | | | | | | | | | |
</body> | | | | | | | | | | | | | | |
</html> | | | | | | | | | | | | | | |
> p | | | | | | | | | | | | | | |
> HTMLElement | | | | | | | | | | | | | | |
> Element | | | | | | | | | | | | | | |
> Node | | | | | | | | | | | | | | |
> EventTarget | | | | | | | | | | | | | | |
> Object | | | | | | | | | | | | | | |
```

在左侧我们可以看到 HTML 树，在右侧有一个代表当前所选元素（在本例中为 `<p>` 标签）的 JavaScript 对象，带有它的所有属性。这是这段 HTML 代码的树结构：

### DOM 图解

这棵树的根节点是 `<html>` 标签。它包含两个节点：`<head>` 和 `<body>`。DOM 规范有很多节点类型，但这里是最重要的一个：

- `ELEMENT_NODE`：重要的一个，如 `<html>`、`<body>`、`<a>`。
- `TEXT_NODE`：像文本内容一样，它没有子节点。

## DOM 操作方法

文档对象模型提供了使用 JavaScript 来添加、删除或附加任何节点的方法。`Node` 对象有很多许多属性和方法来这样做：

- `childNodes`：返回所有子节点的列表。
- `nodeType`：返回一个表示节点类型的短整数（1 代表 `ELEMENT_NODE`，3 代表 `TEXT_NODE`）。
- `appendChild()`：将子节点添加到当前节点。
- `removeChild()`：从当前节点中移除子节点。

需要记住的重要点是，你在浏览器中右键检查时看到的 DOM 可能与实际发送的 HTML 完全不同。也许某些 JavaScript 代码执行并动态更改了 DOM！例如，当你滚动账户时，浏览器会发送一个请求来获取新推文，某些 JavaScript 代码动态地将这些新推文添加到 DOM 中。



这段 HTML 代码基本上是封装在其他 HTML 内容内部的 HTML 内容。HTML 的层级结构可以通过 HTML 代码中的缩进视为一棵树。当你的网络浏览器解析此代码时，它会创建一个树，它是 HTML 文档的对象的表示。它被称为文档对象模型（DOM）。下面是 Chrome 检查器内部的树结构：

## DOM 101

这是我的博客。

| 元素 | 控制台 | 来源 | 网络 | 性能 | 内存 | 应用 | 安全 | 审核 | Adblock Plus | Adblock | 样式 | 计算属性 | 事件监听器 | 属性 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `<html>` | | | | | | | | | | | | | | | | |
| `<head>` | | | | | | | | | | | | | | | | | |
| `<body>` | | | | | | | | | | | | | | | | | |
| `<h1>` | DOM 101 太棒极了！ | | | | | | | | | | | | | | | | |
| `<p>` | 网络爬虫是我的 | | | | | | | | | | | | | | | | | |
| `</body>` | | | | | | | | | | | | | | | | | |
| `</html>` | | | | | | | | | | | | | | | | | |
| `> p` | | | | | | | | | | | | | | | | | |
| `> HTMLElement` | | | | | | | | | | | | | | | | | |
| `> Element` | | | | | | | | | | | | | | | | | |
| `> Node` | | | | | | | | | | | | | | | | | |
| `> EventTarget` | | | | | | | | | | | | | | | | | |
| `> Object` | | | | | | | | | | | | | | | | | |

## Chrome 检查器

在左侧我们可以看到 HTML 树，在右侧有一个代表当前所选元素（在本例中为 `<p>` 标签）的 Javascript 对象，带有它的所有属性。这是这段 HTML 代码的树结构：

需要记住的重要点是，你在浏览器中右键检查时看到的 DOM 可能与实际发送的 HTML 完全不同。也许某些 Javascript 代码执行并动态更改了 DOM！例如，当你滚动账户时，浏览器会发送一个请求来获取新推文，某些 Javascript 代码动态地将这些新推文添加到 DOM 中。

## DOM 图解

这棵树的根节点是 `<html>` 标签。它包含两个节点：`<head>` 和 `<body>`。DOM 规范有很多节点类型，但这里是最重要的一个：

- `ELEMENT_NODE` 重要的一个 `<html>`、`<body>`、`<a>`。
- `TEXT_NODE` 像红色中的那些一样，它没有子节点。

# Web 基础

文档对象模型提供了使用 JavaScript 来添加、删除或附加任何节点的方法。`Node` 对象有很多许多属性和方法来这样做：

- `childNodes` 返回所有子节点的列表。
- `Type` 返回一个表示节点类型的短整数（`1` 代表 `ELEMENT_NODE`，`3` 代表 `TEXT_NODE`）。
- `AppendChild` 将子节点添加到当前节点。
- `RemoveChild` 从当前节点中移除子节点。

然后，如果你使用网络浏览器发送此 HTTP 请求，浏览器将解析 HTML 代码，获取所有的最终资源（Javascript 文件、CSS 文件、图像...），并将结果渲染到主窗口。

# HTML 和文档对象模型

我假设你已经了解 HTML 了，所以这只是一个小的提醒。

- 超文本标记语言 (HTML) 用于为原始内容添加“意义”。
- 级联样式表 (CSS) 用于格式化这些标记后的内容。
- Javascript 让这些内容具有交互性。

正如你所知道的，网页是一个包含标签内文本的文档，这些标签通过描述标题、段落、列表、链接等元素来为文档添加意义。让我们来看一个基础的 HTML 页面，以理解什么是文档对象模型。

## HTML 页面

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>DOM 是什么？</title>
</head>
<body>
  <h1>DOM 101 太棒极了！</h1>
  <p>网络爬虫是我的 <a href="https://ksah.in">博客</a></p>
</body>
</html>
```

这段 HTML 代码基本上是封装在其他 HTML 内容内部的 HTML 内容。HTML 的层级结构可以通过 HTML 代码中的缩进视为一棵树。当你的网络浏览器解析此代码时，它会创建一个树，它是 HTML 文档的对象的表示。它被称为文档对象模型（DOM）。

## Web 提取过程

为了在你的代码中访问一个 URL，获取 HTML 代码并解析它以提取想要的数据，我们可以使用不同的方法：

- 无头浏览器
- “手动”执行操作：使用 HTTP 库执行 GET 请求，然后使用类似 Jsoup 的库解析 HTML 并提取你想要的数据。

每个选项都有优缺点。无头浏览器就像普通的浏览器，但没有图形用户界面。它通常用于 QA 原因，对网站进行自动化测试。

稍后。无头浏览器的好处是它可以处理很多事情：解析 HTML、处理身份 Cookie、填充表单、执行 JavaScript 函数、访问 iFrame……它的缺点是与使用纯 HTTP 库和解析库相比，它会有一些开销。

在接下来的三个章节中，我们将学习如何使用 XPath、CSS 选择器和正则表达式来选择并提取 HTML 内部的数据。

### XPath

XPath 是一种使用路径表达式来选择 XML 文档（或 HTML 文档）中节点或节点集的技术。与文档对象模型（DOM）一样，XPath 自 1999 年以来一直是 W3C 标准。即使 XPath 本身不是一种编程语言，它允许你编写表达式来直接访问特定节点或特定节点集，而无需遍历整个 HTML 树（或 XML 树）。

关于 XPath 有整整的书籍介绍，正如我之前提到的，我并不打算深入浅解释所有内容，这只是 XPath 的介绍，我们将通过真实示例看到如何将其用于你的网络爬虫需求。

我们将使用以下 HTML 文档作为后续示例：

### HTML 示例

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>XPath 101</title>
</head>
<body>
  <div class="product">
    <header>
      <hgroup>
        <h1>Amazing product #1</h1>
        <h3>The best product ever made</h3>
      </hgroup>
    </header>
    <figure>
      <img src="http://lorempixel.com/400/200">
    </figure>
    <section>
      <p>Text text</p>
      <details>
        <summary>Product Features</summary>
        <ul>
        <li>Feature 1</li>
        <li class="best-feature">Feature 2</li>
        <li id="best-id">Feature 3</li>
        </ul>
      </details>
      <button>Buy Now</button>
    </section>
  </div>
</body>
</html>
```

首先让我们来看一些 XPath 词汇：

- 在 XPath 术语中，与 HTML 一样，有不同类型的节点：根节点、元素节点、属性节点以及所谓的原子值（它是 HTML 文档中文本节点的同义词）。
- 每个元素节点有一个父节点。在这个示例中，`section` 元素是 `p`、`details` 和 `button` 的父节点。
- 元素节点可以有任意数量的子节点。在我们的示例中，`li` 元素都是 `ul` 元素的子。
- 兄弟节点是具有相同父节点的节点。`p`、`details` 和 `button` 就是兄弟节点。
- 祖先是节点的父以及父节点的父节点……
- 后代是节点的子及其子节点……

### XPath 语法

有不同类型的表达式来选择 HTML 文档中的节点，这里是最重要的几个：

| XPath 表达式 | 说明 |
|---|---|
| `nodename` | 这是最简单的，它选择所有具有该节点名的节点 |
| `/` | 从根节点开始选择（用于编写绝对路径） |
| `//` | 从当前节点开始选择匹配项的节点 |
| `.` | 选择当前节点 |
| `..` | 选择当前节点的父节点 |

| 表达式 | 说明 |
|---|---|
| `@` | 选择属性 |
| `*` | 匹配任何节点 |
| `//@` | 匹配任何属性节点 |

你也可以使用谓词来查找包含特定值的节点。谓词始终位于方括号中：`[predicate]`。这里是一些示例：

| 表达式 | 说明 |
|---|---|
| `//li[last()]` | 选择最后一个 li 元素 |
| `//div[@class='product']` | 选择所有 class 为 product 的 div 元素 |
| `//li[3]` | 选择第三个 li 元素（索引从 1 开始） |
| `//div[@class='product']` | 选择所有 class 为 product 的 div 元素 |

现在我们将看到一些 XPath 表达式的示例。我们可以在 Chrome 开发者工具中测试 XPath 表达式，所以是时候启动 Chrome 了。方法是：右键点击网页 -> 检查，然后在 Mac 上使用 `cmd + f` 或在其他系统上使用 `ctrl + f`，你可以输入 XPath 表达式，匹配将在开发者工具中高亮显示。

### Amazing product #1

有史以来制造的最好的产品

Text text text

- Product Features
- Feature 1
- Feature 2
- Feature 3

Buy Now

```html
<head>...</head>
<body>
  <div class="product">
    <header>...</header>
    <figure>
      <img src="http://lorempxel.com/400/200">
    </figure>
    <section>
      <p>Text text</p>
      <details>
        <summary>Product Features</summary>
        <ul>
          <li>Feature 1</li>
          <li>Feature 2</li>
          <li>Feature 3</li>
        </ul>
      </details>
      <button>Buy Now</button>
    </section>
  </div>
</body>
</html>
```

Web 基础

稍后。无头浏览器的好处是它可以处理很多事情：解析 HTML、处理身份 Cookie、填充表单、执行 JavaScript 函数、访问 iFrame……它的缺点是与使用纯 HTTP 库和解析库相比，它会有一些开销。

在接下来的三个章节中，我们将学习如何使用 XPath、CSS 选择器和正则表达式来选择并提取 HTML 内部的数据。

### XPath

XPath 是一种使用路径表达式来选择 XML 文档（或 HTML 文档）中节点或节点集的技术。与文档对象模型（DOM）一样，XPath 自 1999 年以来一直是 W3C 标准。即使 XPath 本身不是一种编程语言，它允许你编写表达式来直接访问特定节点或特定节点集，而无需遍历整个 HTML 树（或 XML 树）。

关于 XPath 有整整的书籍介绍，正如我之前提到的，我并不打算深入解释所有内容，这只是 XPath 的介绍，我们将通过真实示例看到如何将其用于你的网络爬虫需求。

我们将使用以下 HTML 文档作为后续示例：

### HTML 示例

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>XPath 101</title>
</head>
<body>
  <div class="product">
    <header>
      <hgroup>
        <h1>Amazing product #1</h1>
        <h3>The best product ever made</h3>
      </hgroup>
    </header>
    <figure>
      <img src="http://lorempixel.com/400/200">
    </figure>
    <section>
      <p>Text text</p>
      <details>
        <summary>Product Features</summary>
        <ul>
        <li>Feature 1</li>
        <li class="best-feature">Feature 2</li>
        <li id="best-id">Feature 3</li>
        </ul>
      </details>
      <button>Buy Now</button>
    </section>
  </div>
</body>
</html>
```

首先让我们来看一些 XPath 词汇：

- 在 XPath 术语中，与 HTML 一样，有不同类型的节点：根节点、元素节点、属性节点以及所谓的原子值（它是 HTML 文档中文本节点的同义词）。
- 每个元素节点有一个父节点。在这个示例中，`section` 元素是 `p`、`details` 和 `button` 的父节点。
- 元素节点可以有任意数量的子节点。在我们的示例中，`li` 元素都是 `ul` 元素的子。
- 兄弟节点是具有相同父节点的节点。`p`、`details` 和 `button` 就是兄弟节点。
- 祖先是节点的父以及父节点的父节点……
- 后代是节点的子及其子节点……

### XPath 语法

有不同类型的表达式来选择 HTML 文档中的节点，这里是最重要的几个：

| XPath 表达式 | 说明 |
|---|---|
| `nodename` | 这是最简单的，它选择所有具有该节点名的节点 |
| `/` | 从根节点开始选择（用于编写绝对路径） |
| `//` | 从当前节点开始选择匹配项的节点 |
| `.` | 选择当前节点 |
| `..` | 选择当前节点的父节点 |

| 表达式 | 说明 |
|---|---|
| `@` | 选择属性 |
| `*` | 匹配任何节点 |
| `//@` | 匹配任何属性节点 |

你也可以使用谓词来查找包含特定值的节点。谓词始终位于方括号中：`[predicate]`。这里是一些示例：

| 表达式 | 说明 |
|---|---|
| `//li[last()]` | 选择最后一个 li 元素 |
| `//div[@class='product']` | 选择所有 class 为 product 的 div 元素 |
| `//li[3]` | 选择第三个 li 元素（索引从 1 开始） |
| `//div[@class='product']` | 选择所有 class 为 product 的 div 元素 |

现在我们将看到一些 XPath 表达式的示例。我们可以在 Chrome 开发者工具中测试 XPath 表达式，所以是时候启动 Chrome 了。操作方法是：右键点击网页 -> 检查，然后在 Mac 上使用 `cmd + f` 或在其他系统上使用 `ctrl + f`，你可以输入 XPath 表达式，匹配将在开发者工具中高亮显示。

### Amazing product #1

![](img/cbd5c820756a64b88207a1ea9f1c877b_25_0.png)

Text text text

- Product Features
- Feature 1
- Feature 2
- Feature 3

Buy Now

```html
<head>...</head>
<body>
  <div class="product">
    <header>...</header>
    <figure>
      <img src="http://lorempxel.com/400/200">
    </figure>
    <section>
      <p>Text text</p>
      <details>



# 提取你想要的数据

在第一个示例中，我们将从 Hacker News 获取项目，尽管他们提供了一个很好用的 API，但让我们假装他们没有。

## 工具

你需要 Java 8 配合 `HtmlUnit`¹⁶。`HtmlUnit` 是一个 Java 无头浏览器，这个库允许你对网站执行 HTTP 请求，并解析 HTML 内容。

`pom.xml`

```xml
<dependency>
  <groupId>net.forge.htmlunit</groupId>
  <artifactId>htmlunit</artifactId>
  <version>2.28</version>
</dependency>
```

如果你正在使用 Eclipse，我建议你在详细窗格中（点击 `variables` 选项卡时）配置最大长度，这样你就能看到当前页面的完整 HTML。

> ¹⁶http://htmlunit.sourceforge.net

### 我们来爬取 Hacker News

我们的目标是收集第一页的标题、点赞数和评论数。稍后我们将看到如何处理分页。

基础 URL 是：`https://news.ycombinator.com/`

现在你可以使用你喜欢的 IDE 了，是时候了。`HtmlUnit` 需要 `WebClient` 来发送请求。这里有很多选项（代理设置、浏览器、启用重定向等……）。我们将禁用 JavaScript，因为我们的示例不需要它，而且禁用 JavaScript 通常会让页面加载得更快（在特定情况下，这并不重要）。然后，我们对 hacker news 的 URL 发送 GET 请求，并打印从服务器收到的 HTML 内容。

### 简单的 GET 请求

```java
String baseUrl = "https://news.ycombinator.com/";

HttpClient client = new HttpClient();

client.getOptions().setCssEnabled(false);
client.getOptions().setJavaScriptEnabled(false);

try {
  HtmlPage page = client.getPage(baseUrl);
  System.out.println(page.asXml());
} catch (Exception e) {
  e.printStackTrace();
}
```

`HtmlPage` 对象将包含 HTML 代码，你可以通过 `asXml()` 方法访问它。

现在对于每个项目，我们将提取标题、URL、作者等。首先，让我们看看检查 Hacker news 帖子时会发生什么（在 Chrome 中右键点击元素 + 选择“检查”）。

### 提取数据

- 1. [Libraft C语言结构化并发 (2016)](https://libraft.org)  
  45 分，由 bynomic 发布，2 小时前 | 18 条评论
- 2. [许多公司正在利用偏见排除年长员工的招聘机会](https://news.ycombinator.com)  
  427 分，由 20 发布，5 小时前 | 154 条评论
- 3. [为现实主义而战](https://prism.com)  
  202 分，由 jasonr 发布，8 小时前 | 66 条评论
- 4. [来自 Nautilus 出版者的信](https://news.ycombinator.com)  
  128 分，由 larsson 发布，9 小时前 | 31 条评论
- 5. [罗马尼亚黑客感染了 65% 的 DC 监控摄像头](https://news.ycombinator.com)  
  55 分，由 j6233 发布，1 天前 | 32 条评论
- 6. [SQL 注入](https://news.ycombinator.com)  
  892 分，由 isid 发布，8 小时前 | 301 条评论
- 7. [柏林必须成为公民的城市](https://news.ycombinator.com)  
  95 分，由 m14 发布，9 小时前 | 123 条评论
- 8. [等待十二天：监控国家如何压抑生活](https://dreamearth.com)  
  129 分，由 benish 发布，8 小时前 | 77 条评论
- 9. [正义尚未得到证明](https://wordpress.com)  
  98 分，由 jid 发布，1 天前 | 45 条评论
- 10. [无服务器架构指南](https://news.ycombinator.com)  
  85 分，由 m_v 发布，1 天前 | 22 条评论
- 11. [地铁如何让纽约变得痛苦](https://news.yator.com)  
  80 分，由 smith 发布，1 天前 | 10 条评论
- 12. [社区行为的后果](https://dreamearth.com)  
  21 分，由 jasonr 发布，1 天前 | 92 条评论

使用 `HtmlUnit` 你有几种选项来选择标签：
- `getById(String id)`
- `getFirstXPath(String XPath)`
- `getByXPath(String XPath)`
- 更多选项

由于没有 ID，我们必须使用 XPath 表达式来选择标签。我们可以看到每个项目两行。第一行是位置、标题、URL 和 ID。第二行是分数、作者和评论。在 DOM 结构中，每一行都在 `<tr class="thing">` 标签内，因此我们需要的是遍历这个列表，并对每个项目使用相对 XPath 选择标题、URL、作者等，然后打印内容。

### HackerNewsraper.java 使用 XPath

```java
HtmlPage page = client.getPage(baseUrl);

List<HtmlElement> itemList = page.getByXPath("tr[class='thing']");

if (itemList.isEmpty()) {
    System.out.println("未找到项目");
} else {
    for (HtmlElement htmlItem : itemList) {
        int id = Integer.parseInt(htmlItem.getAttribute("id"));

        String title = ((HtmlElement) htmlItem.getByXPath("td[not(@align='top')][class='title']")).asText());

        String url = ((HtmlAnchor) htmlItem.getByXPath("td[not(@align='top')][class='title']/a")).getHref();

        String author = ((HtmlElement) htmlItem.getByXPath("following-sibling::tr[class='subtext']/a[@class='hn']")).asText());

        int score = Integer.parseInt(((HtmlElement) htmlItem.getByXPath("following-sibling::tr[class='subtext']/span[@class='score']")).asText().replace(" points", ""));
    }
}
```

### 导出为 JSON

```java
HackerNewsItem hnItem = new HackerNewsItem(title, url, author, score, id);

ObjectMapper mapper = new ObjectMapper();

String jsonString = mapper.writeValueAsString(hnItem);

System.out.println(jsonString);
```

在 IDE 中打印结果很酷，但导出为 JSON 或其他格式良好且可重用的格式更好。我们将使用 Jackson⁷ 库将项目映射为 POJO 格式。

首先，我们需要一个 POJO（普通 Java 对象）来表示 Hacker News 项目：

### HackerItem.java POJO

```java
public class HackerNewsItem {

    private String title;
    private String url;
    private String author;
    private int score;
    private int position;
    private int id;

    public HackerNewsItem(String title, String url, String author, int score, int position, int id) {
        super();
        this.title = title;
        this.url = url;
        this.author = author;
        this.score = score;
        this.position = position;
        this.id = id;
    }

    // getters and setters
}
```

> ⁷https://github.com/FasterXML/jackson

然后将 Jackson 依赖添加到你的 `pom.xml`：

`pom.xml`

```xml
<dependency>
  <groupId>com.fasterxml.jackson.core</groupId>
  <artifactId>jackson-databind</artifactId>
  <version>2.7.0</version>
</dependency>
```

现在我们只需创建一个项目，设置它的属性，并将其转换为 JSON 字符串（或文件……）。将旧的 `System.out.println()` 替换为：

### HackerNewsScraper.java

```java
HackerNewsItem hnItem = new HackerNewsItem(title, url, author, score, position, id);

ObjectMapper mapper = new ObjectMapper();

String jsonString = mapper.writeValueAsString(hnItem);

// 打印或保存到文件
System.out.println(jsonString);
```

就这样。你应该有一个良好的 JSON 格式项目列表。

### 进一步尝试

这个示例并不完美，有很多可以做的事情：

- 将结果保存到数据库。
- 处理分页。
- 使用正则表达式验证提取的数据，而不是进行粗暴的 `replace()`。

你可以在这个 Github 仓库⁸ 中找到完整代码。

> ⁸https://github.com/ksahin/javawebscrapinghandbook_code

---

# 处理表单

Digital Ocean 网站的典型登录表单

在本章中，我们将学习如何处理 Web 上的表单。了解如何提交表单对于提取登录表单背后的信息，或执行需要身份验证的操作至关重要。以下是一些需要提交表单的常见操作示例：

- 创建账户
- 身份验证
- 在博客上发表评论
- 上传图片或文件
- 网站上的搜索与过滤
- 收集用户邮箱
- 从用户处收集支付信息
- 任何用户生成的内容！

## 表单理论

### Form 标签

HTML 表单以 `<form>` 标签开始。最重要的属性是 `action` 和 `method`。

`action` 属性代表 HTTP 请求将发送到的 URL，`method` 属性指定了使用哪种 HTTP 方法。

通常，在创建或修改某些内容时使用 `POST` 方法，例如：

- 登录表单
- 账户创建
- 为博客添加评论

> ^15}https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form

### 表单输入框

为了收集用户输入，使用了 `<input>` 元素。正是这个元素使得文本字段出现。`<input>` 元素具有不同的属性：

- `type`: email, text, radio, file, date...
- `name`: 与将发送的值关联的名称
- 更多属性

让我们来看一个典型的登录表单示例：

> 20https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input

### 登录表单

这是对应的 HTML 代码（不包含 CSS 代码）：

### 表单的 HTML 代码

```html
<form action="login" method="POST">
<div class="container">
  <img src="img_avatar2.png" alt="Avatar" class="avatar">
</div>
<div class="container">
  <label for="uname"><b>Username</b></label>
  <input type="text" placeholder="Enter Username" name="uname" required>
  <label for="psw"><b>Password</b></label>
  <input type="password" placeholder="Enter Password" name="psw" required>
  <button type="submit">Login</button>
</div>
</form>
```

当用户用其凭据（例如用户名 `username` 和 `my_great_password`）填充表单并点击提交按钮时，浏览器发送的请求将如下：

### Http 响应

```http
POST /login HTTP/1.1
Host: example.com
Content-Type: application/x-www-form-urlencoded

uname=username&psw=my_great_password
```

### Cookies

在进行 POST 请求后，如果凭据有效，服务器通常会在响应头中设置 Cookie，允许用户进行导航。

此 Cookie 通常被命名为（名称取决于网站后端使用的技术/框架）：

- `session_id`
- `session`
- `JSESSION_ID`
- `PHPSESSID`

浏览器会在随后的每个请求中发送此 Cookie，网站后端端将检查其存在性和有效性以授权请求。Cookie 不仅用于登录，还用于许多不同的用例：

- 购物车
- 用户偏好
- 跟踪用户行为

Cookie 是存储在浏览器或 HTTP 客户端中的小型键值对，其形式如下：

```
cookie_name=cookie_value
```

设置 Cookie 的 HTTP 响应如下：

### Http 响应

```http
HTTP/1.0 200 OK
Content-type: text/html
Set-Cookie: cookie_name=cookie_value
```

带有 Cookie 的 HTTP 请求如下：

### Http 请求

```http
GET /sample_page.html HTTP/1.1
Host: www.example.com
Cookie: cookie_name=cookie_value
```



## 处理表单

WebRequest[https://www.javawebscrapingsbox.com/account/login", POST, EncodingType[name=application/x-www-form-urlencoded], csf_token=1524752332#6997dd9d5ed448484131add18b41a263541b5c2, email=test@test.com, password=[Origin:https://www.javawebscrapingsbox.com/account/login, Accept:text/html,application/xhtml+application/xml;q=0.9,image/*;q=0.8, Cache-Control:max-age=0, Referrer:https://www.javawebscrapingsbox.com/account/login, Accept-Encoding:gzip, deflate]

我们这里有一个例子。你可以看到，向服务器发送不仅仅两个参数（`email` 和 `password`），我们还有一个 `csrf-token` 参数，它的值每次我们提交表单时都会改变。这个参数是隐藏的，正如你在表单的 HTML 中所示：

```html
<div class="container">
  <div class="eight wide sixteen mobile centered column">
    <h2 class="ui dividing header">Log in</h2>
    <form method="POST" enctype="application/x-www-form-urlencoded">
      <div style="display:none">
        <input id="csrf_token" name="csrf_token" hidden value="1524752332#6997dd9d5ed448484131add18b41a263541b5c2" />
      </div>
      <div class="field">
        <label for="email">Email</label>
        <input id="email" name="email" placeholder="Email" type="email" value />
      </div>
      <div class="field"></div>
      <div class="ui two column grid"></div>
      <div class="field"></div>
    </form>
  </div>
</div>
```

## CSRF token

CSRF 代表跨站请求伪造（Cross Request Forgery）。该令牌由每次表单提交 / POST 请求生成。几乎我们使用的每个网站都为了防止 CSRF 攻击。你可以在这里了解更多关于 CSRF 攻击的知识。现在让我们用 HtmlUnit 创建自己的 POST 请求。

首先我们需要创建一个 `Web` 对象。然后，我们需要设置 URL、HTTP 方法、请求头和参数。向 `WebRequest` 对象添加请求头非常简单，你只需要调用 `setAdditionalHeader` 方法。向你的请求中添加参数必须通过 `setParameters` 方法完成，该方法接受一个 `NameValuePair` 列表。正如之前讨论的那样，我们需要向参数中添加 `csrf_token`，可以使用此 XPath 表达式轻松地选择它：`//input[@name='csrf_token']`

### 手动构建伪造请求输入

```java
Html csrfToken = page.getByXPath("//form[@name='csrf_token']");
WebRequest request = new WebRequest(
    new URL("http://www.javawebscrapingsbox.com/account/login"), method.POST);
List<NameValuePair> params = new ArrayList<NameValuePair>();
params.add(new NameValuePair("csrf_token", csrfToken.getAttribute("value")));
params.add(new NameValuePair("email", email));
params.add(new NameValuePair("password", password));
request.setParameters(params);
request.setAdditionalHeader("Content-Type", "application/x-www-form-urlencoded");
request.setAdditionalHeader("Accept-Encoding", "gzip, deflate");
page = client.getPage(request);
```

> 23 https://en.wikipedia.org/wiki/Cross-site_request_forgery

## 案例研究：Hacker News 身份验证

假设你想创建一个登录网站的机器人（以提交链接或执行需要身份验证的操作）：

这里是登录表单及相关的 DOM：

![](img/cbdc820756a64b8207a1ea9f1c877b_50.png)

现在我们可以实现登录算法

### 登录算法

```java
public static WebClient autoLogin(String loginUrl, String login, String password) throws HttpStatusException, MalformedURLException, IOException {
    WebClient client = new WebClient();
    client.getOptions().setCssEnabled(false);
    client.getOptions().setJavaScriptEnabled(false);
    HtmlPage page = client.getPage(loginUrl);
    HtmlInput inputPassword = page.getByXPath("//input[@type='password']");
    // 第一个隐藏输入
    HtmlInput inputLogin = inputPassword.getByXPath("preceding::input[not(@hidden)]");
    inputLogin.setAttribute(login);
    inputPassword.setAttribute(password);
    // 获取所在的表单
    HtmlForm loginForm = inputPassword.getEnclosingForm();
    // 提交表单
    page = client.getPage(loginForm);
    // 返回 client
    return client;
}
```

然后是 main 方法：

- 使用正确的参数调用 `autoLogin`
- 访问 https://news.combinator.com
- 检查链接是否存在以验证已登录
- 打印 cookie

### Hacker News 登录

```java
public static void main(String[] args) {
    String baseUrl = "https://news.combinator.com";
    String loginUrl = baseUrl + "/login?goto=news";
    String login = "login";
    String password = "password";
    try {
        System.out.println("Starting autoLogin on " + loginUrl);
        WebClient client = autoLogin(loginUrl, login, password);
        HtmlPage page = client.getPage(baseUrl);
        HtmlAnchor logoutLink = page.getByXPath(String.format("//a[href='logout?id=%s']", login));
        if(logoutLink != null) {
            System.out.println("Successfully logged in!");
            // 打印 cookies
            for(Cookie cookie : client.getCookieManager().getCookies()) {
                System.out.println(cookie.toString());
            }
        }else{
            System.err.println("Wrong credentials");
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

## 进一步

有很多方法在 Amazon、Dropbox... 以及所有其他受验证码保护的表单，可以用以下代码改进：

- 在 `autoLogin` 内部处理退出链接检查
- 检查空表单并抛出相应的异常

## 文件上传

文件上传不是爬虫常用的，但了解如何上传文件很有趣，例如你想测试自己的网站或在网站上自动化任务。

这并不复杂，sandbox 网站上有一个表单（需要身份验证）：

![](img/cbd5c820756a64b8207a1ea9f1c877b_53.png)

这里是表单的 HTML 代码：

> 24 https://github.com/ksahin/introWebScrapingsbox/upload_file
> 25 https://www.javawebscrapingssandbox.com/upload_file

### 表单示例

```html
<div class="ui text container">
  <h1>Upload Your Files</h1>
  <form action="/upload_file" method="POST" enctype="multipart/form-data">
    <label for="user_file">Upload Your File</label>
    <br>
    <input type="file" name="user_file">
    <br>
    <button type="submit">Upload</button>
  </form>
</div>
```

通常，这里的目标是选择表单，如果有 name 属性可以使用 `getFormByName()` 方法，但这种情况下没有，我们将使用常用的 XPath 表达式。然后我们必须选择文件输入并将名称设置到该输入。注意，你必须经过验证才能提交此表单。

### 文件上传示例

```java
fileName = "file.png";
page = client.getPage(baseURL + "upload_file");
HtmlInput uploadFileForm = page.getByXPath("//form[action='/upload_file']");
HtmlInput fileInput = uploadFileForm.getInputByName("user_file");
fileInput.setValue(fileName);
fileInput.setContentType("image/png");
HtmlElement button = page.getByXPath("//button");
page = button.click();
if(page.asText().contains("Your file was successful uploaded")) {
    System.out.println("File successfully uploaded");
}else{
    System.out.println("Error uploading the file");
}
```

### 其他表单

### 搜索表单

爬虫的另一个常见需求是提交搜索表单。拥有大型数据库的网站（如市场）通常提供搜索表单来查找特定的项目。搜索表单通常有三种实现方式：

- 提交表单时向服务器发送 POST 请求
- 带有查询参数的 GET 请求
- 向服务器发送 AJAX 调用

例如，我在 sandbox 网站上设置了一个搜索表单：

![](img/cbd5c820756a64b8207a1ea9f1c877b_55_0.png)

## 处理表单

这是一个简单的表单，并没有什么复杂的。照常，我们必须选择输入字段，填入我们想要的值，并提交表单。正如我们在章节开头看到的那样，我们也可以手动模拟 POST 请求。当服务器返回响应时，我选择遍历结果并在控制台中打印它（完整的代码像往常可以在仓库中找到）。

### 搜索示例

```java
HtmlPage page = client.getPage(baseUrl + "product/search");
HtmlInput minPrice = page.getElementByIdById("min_price");
HtmlInput maxSize = page.getElementByIdById("max_price");
// 设置最小/最大值
minPrice.setAttribute(MINPRICE);
maxPrice.setAttribute(MAXPRICE);
HtmlForm form = minPrice.getEnclosingForm();
page = client.getPage(form.getWebRequest(null));
HtmlTable table = page.getFirstXPath("//table");
for(HtmlTableRow row : table.getBodies().get(0).getRows()){
    System.out.println(String.format("Name : %s Price: %s", elem.getCell(0).asText(), elem.getCell(2).getText()));
}
```

这里是结果：

| 名称 | 价格 |
| :--- | :--- |
| ClosetMaid 1937440 SuiteS | 319.89 $ |
| RWS Model 34 .22 Caliber | 314.97 $ |
| Neato Botvac D5 Connected | 549.00 $ |
| Junghans Men's 'Max Bill' | 495.00 $ |

## 输出

在 90 年代，基础认证（basic authentication）随处可见。如今，你仍然可以在企业网站上找到它。它是最简单的认证形式之一。服务器将检查客户端发送的 Authorization 请求头中的凭据，或者在浏览器中弹出提示。如果凭据不正确，服务器将返回 401（未授权）状态。

![](img/5c820756a4b8820a1ea9f1c877b_0.png)

### 基础认证

使用 HtmlUnit 使用基础认证非常简单，你只需要按照这种模式格式化你的 URL：`https://username:password@www.webscraping.com`。

### 基础认证示例

```java
HtmlPage page = client.getPage(String.format("https://%s:%s@www.webscraping.com/auth", username, password));
System.out.println(page.asText());
```

## 处理 Javascript

处理使用大量 Javascript 渲染内容的网站可能是很棘手的。如今，越来越多的网站使用如 Angular、React、Vue.js 等框架作为前端。这些前端框架很难处理，因为它们经常使用最新的 HTML5 特性，而 HtmlUnit 并不支持这些特性。所以，基本上，你遇到的问题问题是：你的无头浏览器（headless browser）会下载 HTML 代码，但 Javascript 代码无法执行完整的代码，导致网页无法被完全渲染。针对这些问题有一些解决方案。第一种是使用更好的无头浏览器。第二种是检查 Javascript 前端发出的 API 调用并重现它们。

### Javascript 入门 (101)

Javascript 是一种解释型脚本语言。它正被越来越多地用于构建“Web 应用”和“单页应用”。本章的目的不是教你 Javascript，而是我想让你理解它是如何在 Web 上被使用的。Javascript 的语法类似于 C 或 Java，支持布尔值、字符串、数组、对象等常见数据类型…… Javascript 是弱类型的，这意味着不需要显式地声明数据类型。这里是一些示例：

#### 加一函数



```javascript
function plusOne(number) {
  return number + 1;
}
var a = 4;
var b = plusOne(a);
console.log(b); // 将在控制台中打印 5
```

正如我们在第 2 章中看到的，Javascript 主要用于 Web 上动态修改 DOM 并执行 HTTP 请求。这里有一段使用股票 API 在点击按钮时获取苹果股票的示例代码：

### 原生 Javascript (Vanilla Javascript)

```html
<!DOCTYPE html>
<html>
<head>
<script>
  function refreshStock(){
    fetch("https://api.example.com/1.0/stock/aapl/batch?types=quote,news,chart&range=1m&last=10")
    .then(function(response) {
      return response.json();
    }).then(function(data) {
      document.getElementById('my_cell').innerHTML = '$' + data.quote.latest;
    });
  }
</script>
</head>
<body>
<div>
<h2>苹果股票价格：</h2>
<div id="my_cell"></div>
<button id="refresh" onclick="refreshStock()">刷新</button>
</div>
</body>
</html>
```

## jQuery

jQuery 是最广泛使用的 Javascript 库之一。它非常老了，第一个版本编写于 2006 年，被用于许多场景，例如：

- DOM 操作
- AJAX 调用
- 事件处理
- 动画
- 插件（日期选择器等）

这是相同代码的 jQuery 版本（你可以注意到 jQuery 版本并不一定比原生版本清晰）：

```html
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/jquery/3.2.1/jquery.min.js"></script>
<script>
function refreshStock() {
  $.get("https://api.example.com/1.0/stock/aapl/batch?types=quote,news,chart&range=1m&last=10", function(data, status) {
    $('#my_cell').html('$' + data.latestPrice);
  });
}

$(document).ready(function(){
  $("#refresh").click(function(){
    refreshStock();
  });
});
</script>
</head>
<body>
<div>
<h2>苹果股票价格：</h2>
<div id="my_cell"></div>
<button id="refresh">刷新</button>
</div>
</body>
</html>
```

如果你想了解 Javascript，我向你推荐这本优秀的书：Eloquent Javascript (https://eloquentjavascript.net/)。

## 现代 Javascript 框架

jQuery 存在几个问题。随着 Javascript 应用程序的增长，用它编写整洁可维护的代码极其困难。大多数情况下，代码库充满了“胶水代码”，你必须对每个 id 或类名的变化保持小心。另一个大问题是，在 Javascript 模型和 DOM 之间实现数据绑定可能是复杂的。

传统的服务器端渲染的另一个问题是它可能效率低下。假设你正在一个老旧网站上浏览一个表格。当你请求下一页时，服务器将渲染整个 HTML 页面以及所有资源并发送回你的浏览器。在单页应用（SPA）中，只会发送一次 HTTP 请求，服务器将返回包含数据的 JSON，而 Javascript 框架将填充 HTML 模型。

# 处理 Javascript

- Chromedriver
- Selenium

在你的 `pom.xml` 中添加最新版本的 Selenium：

`pom.xml`

```xml
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>3.8.1</version>
</dependency>
```

如果你没有安装 Google Chrome，可以[在此处下载](https://www.google.com/chrome/browser/desktop/index.html)。要安装 Chromedriver，你可以在 MacOS 上使用 brew：

```bash
brew install chromedriver
```

你也可以通过 npm 安装 Chrome 驱动：

```bash
npm install chromedriver
```

或者使用下方的链接下载。这里有很多版本，我建议你使用最新版本的 Chrome 和 chromedriver。

## 让我们为真实的 SPA 截屏

我们将对 Coinbase 网站进行截屏，这是一个加密货币交易所，使用 React 框架构建，并且充满了 API 调用和 websocket！

> [33](https://sites.google.com/a/chromium.org/chromedriver/downloads)
> [34](https://www.google.com/chrome/browser/desktop/index.html)
> [35](https://pro.coinbase.com/trade/BTC-USD)

# 处理 Javascript

![](img/cbd5c820756a64b88207a1ea9f1c877b_66_0.png)

Coinbase 截图

我们将使用 Selenium API 在无头模式（`headless mode`）下操作 Chrome。我们必须做的第一件事是创建一个 `WebDriver` 对象，它的角色类似于 HtmlUnit 中的 `WebClient` 对象，并设置 chromedriver 路径和一些参数：

Chrome 驱动驱动

```java
// Init chromedriverPath = "/Path/To/Chromedriver"
System.setProperty("webdriver.chrome.driver", chromedriverPath);
ChromeOptions options = new ChromeOptions();
options.addArguments("--headless", "--disable-gpu", "--window-size=1920,1200", "--ignore-certificate-errors");
WebDriver driver = new ChromeDriver(options);
```

根据文档[36](https://developers.google.com/web/updates/2017/04/headless-chrome)，在 Windows 系统上需要 `--disable-gpu` 选项。Chromedriver 会自动找到 Google Chrome 的执行文件路径，如果你有特殊的安装，或者你想使用不同版本的 Chrome，可以这样操作：

```java
options.setBinary("/Path/to/specific/version/of/Google Chrome");
```

如果你想了解更多关于不同选项，这里是[Chromedriver 文档](https://sites.google.com/a/chromium.org/chromedriver/capabilities)

下一步是对 Coinbase 网站执行 GET 请求，等待页面加载并截屏。

我们已经在之前的文章中做过这个，这里是完整代码：

GDA 截图示例

```java
public class ChromeHeadlessTest {
    private static String userName = "";
    private static String password = "";

    public static void main(String[] args) throws IOException{
        String chromedriverPath = "/path/to/chromedriver";
        System.setProperty("webdriver.chrome.driver", chromedriverPath);
        ChromeOptions options = new ChromeOptions();
        options.addArguments("--headless","--disable-gpu","--window-size=1920,1200","--ignore-certificate-errors","--silent");
        WebDriver driver = new ChromeDriver(options);
    }
}
```

```java
// 获取登录页面
driver.get("https://pro.coinbase.com/trade/BTC-USD");
Thread.sleep(10000);
```

```java
// 为当前页面截屏
File screenshot = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
```

> [36](https://developers.google.com/web/updates/2017/04/headless-chrome)
> [77](https://sites.google.com/a/chromium.org/chromedriver/capabilities)

```java
FileUtils.copyFile(screenshot, new File("screenshot.png"));
driver.close();
driver.quit();
}
```

你现在应该有一个 Coinbase 主页的精美截图了。

这里发生了几件事。`Thread.sleep(10000)` 这一行允许浏览器等待整个页面加载。这不一定是最好的方法，因为我们可能等待了太久，或者取决于多个因素（你自己的网络连接、目标网站的 own等）。

![](img/cbd5c820756a64b88207a1ea9f1c877b_68_0.png)

这是爬取 SPA 时的常见问题，解决方法之一是使用 `WebDriverWait`：

```java
WebDriverWait 使用
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.presenceOfElementLocated(By.xpath("/path/to/element")));
```

这里有很多不同的 `ExpectedConditions`，你可以在这里查看文档[38](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/support/ui/ExpectedConditions.html)。我经常使用 `ExpectedConditions.visibilityOfAllElementsLocatedBy(locator)`，因为元素可能存在，但在异步 HTTP 调用完成之前是隐藏的。

这是对无头 Chrome 和 Selenium 的简要介绍，现在让我们一些常见且实用的对象和方法！

> [38](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/support/ui/ExpectedConditions.html)

## Selenium API

在 Selenium API 中，几乎所有内容都基于两个接口：

- `WebDriver`，它是 HTTP 客户端
- `WebElement`，代表 DOM 对象

`WebDriver`[39](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/WebDriver.html) 可以初始化几乎所有的浏览器并带有各种选项（例如窗口大小）。这里是一些常用方法：

| 方法 | 描述 |
| --- | --- |
| `driver.get(URL)` | 对指定的 URL 执行 GET 请求 |
| `driver.getCurrentUrl()` | 返回当前 URL |
| `driver.getPageSource()` | 返回页面的完整 HTML |
| `driver.navigate().back()` | 后退一步 |
| `driver.switchTo().frame(frame)` | 切换到指定的 Frame |
| `driver.manage().getCookies()` | 获取所有 cookie |
| `driver.quit()` | 退出并关闭所有窗口 |
| `driver.findElement(by)` | 根据定位器找到元素 |

`findElement()` 方法对于我们的需求非常重要。

你可以通过以下方式定位元素：

- `findElement(By.xpath)`
- `findElement(By.className)`
- `findElement(By.cssSelector)`

> [39](https://seleniumhq.github.io/selenium/docs/api/java/org/openqa/selenium/WebDriver.html)

# 处理 Javascript

- `findElement(By.className)`
- `findElement(By.cssSelector)`

一旦你拥有了 `WebElement` 对象，可以使用以下方法：

| 方法 | 描述 |
| --- | --- |
| `click()` | 点击元素 |
| `getText()` | 返回元素内部的文本 |
| `sendKeys('some string')` | 在输入框输入某些文本 |
| `getAttribute('href')` | 返回属性的值 |

## 无限滚动

无限滚动广泛用于社交网站、新闻网站或处理大量信息时。我们将看到三种无限滚动的方法：

> [0](https://www.javascriptbox.com/product/infinite_scroll)

# 处理 Javascript

| 名称 | 价格 |
|---|---|
| Red Wing Men's Round 4 | 348.00 |
| ASICS Men-Go 2000 | 62.95 |
| Nike Air Force '07' Retro | 110.00 |
| Red Wing Men's Round 4 | 348.00 |
| T-Mobile 5G Router MC300 | 79.99 |
| Cole Haan Men's Oxford | 150.00 |
| Dr Martens 1460 8-Eye | 90.00 |
| Converse Chuck Taylor-Star Classic 70 | 65.00 |
| Carhartt WIP-101 Jacket | 219.00 |
| New Balance 574 v2 Suede/Mesh | 89.00 |
| Air Jordan 97 '07-White-Black-White | 130.00 |
| Nike Air Max 270 React-White/Black/Hyper-Infrared | 160.00 |
| Wild West Out-Duty Jeans | 89.00 |
| Adidas Originals Gazelle Sneakers | 90.00 |
| New Balance 574 v2 Grey/White | 110.00 |

## 滚动到底部

爬取此页面的第一种方法是让我们的无头浏览器滚动到页面底部。在 Window 对象上可以使用一个非常好方法，叫做 `ScrollTo`。它非常易用，你给它 X 和 Y 坐标，它就会滚动

为了执行这段 JavaScript 代码，我们将使用一个 JavaScript 执行器。它允许我们在当前网页（更具体地说是当前标签页）的文中执行任何 JavaScript 代码。我们可以访问上下文中定义的每一个 JavaScript 函数和变量。

在这个示例中，我们爬取的网页在首次加载时固定 20 行。因此，如果我们的浏览器太大，我们将无法滚动。这个“错误”是故意留的。为了做到这一点，我们必须使用较小的窗口大小操作 Chrome 实例！

> [1](https://developer.mozilla.org/en-US/docs/Web/API/Window)
> [2](https://developer.mozilla.org/en-US/docs/Web/API/scrollTo)

# 处理 Javascript

使用无头 Chrome 的无限滚动



## 设置 ChromeDriver

```java
String ChromeDriverPath = "/path/to/chromedriver";
System.setProperty("webdriver.chrome.driver", ChromeDriverPath);
ChromeOptions options = new ChromeOptions();
options.addArguments("--headless", "--disable-gpu", "--ignore-certificate-errors", "--silent");
// 此处非常重要的选项，你必须指定一个小的窗口大小以便可见
options.addArguments("window-size=600,400");
```

## 初始化 WebDriver

```java
WebDriver driver = new ChromeDriver(options);
JavascriptExecutor js = (JavascriptExecutor) driver;
int pageNumber = 5;
```

## 无限滚动加载数据

```java
driver.get("https://www.javascriptscrapingsbox.com/product/infinite_scroll");
for(int i = 0; i < pageNumber; i++){
    js.executeScript("window.scrollTo(0, document.body.scrollHeight)");
    // 有更好的等待方式，比如使用 WebDriverWait 对象
    Thread.sleep(1200);
}
List<WebElement> rows = driver.findElements(By.xpath("//tr"));

// 对行列表进行操作
processLines(rows);
```

## 关闭驱动

```java
driver.quit();
```

## 执行 Javascript 函数

这种方法的另一种思路是检查 Javascript 代码以理解无限滚动是如何构建的。如往常，右键点击 + 检查以打开 Chrome 开发者工具，找到包含 Javascript 代码的 `<script>` 标签：

### Javascript 代码分析

```javascript
$(document).ready(function() {
  var win = $(window);
  var page = 1 ;
  var apiUrl = '/product/api/' + page ;

  // 每当用户滚动时
  var updatePage = function(){
    apiUrl = apiUrl.replace(String(page), "");
    page = page + 1;
    apiUrl = apiUrl + page;
  }
  var drawNextLines = function() {
    win.data('ajaxready', false);
    $.ajax({
      url: url,
      dataType: 'json',
      success: function(json) {
        for(var i = 0; i < json.length; i++){
          var tr = document.createElement('tr');
          var tdName = document.createElement('td');
          var tdUrl = document.createElement('td');
          var tdPrice = document.createElement('td');

          tdName.innerText = json[i].name;
          tdUrl.innerText = json[i].url;
          tdPrice.innerText = json[i].price;

          tr.appendChild(tdName);
          tr.appendChild(tdUrl);
          tr.appendChild(tdPrice);
        }
      }
    });
```

```javascript
var table = document.getElementById('table');
table.appendChild(tr);

}
win.data('ajaxready', true);
if(url == '/product/api/1' && url != '/product/api/2')
{
    updatePage();
}
}
$('#loading').hide();
}
drawNextLines('/product/api/1');
drawNextLines('/product/api/2');

page = 3 ;
apiUrl = '/product/api/3';

// 需要更新 "ajaxready" 变量以防触发多次 ajax 调用
// 当在疯狂滚动时
win.data('ajaxready', true).scroll(function() {
  // 到达文档末尾？
  if (win.data('ajaxready') == false) return;

  // 当我们准备“触碰”页面底部时触发 ajax 调用
  // 不超过 20 页
  if (win.scrollTop() + win.height() > $(document).height() - 100 &&
  page < 20) {
      $('#loading').show();
      drawNextLines(apiUrl);
  }
});
```

你不需要理解那里的所有内容，唯一有趣的信息是，每当我们靠近页面底部附近（准确来说是 100 像素）时，`drawNextLines()` 函数就会被调用。它接受一个参数，模式为 `/product/api/id` 的 URL，它将返回额外的 10 行。

假设我们想在表格中再获取 50 行。基本上我们只需要创建一个循环并调用 `drawNextLines()` 五次。如果你仔细观察 Javascript 代码，当 AJAX 调用加载时，我们将变量 `ajaxready` 设置为 false。我们可以检查此变量的状态，并等待它被设置为 true。

## 调用 Javascript 函数

```java
JavascriptExecutor js = (JavascriptExecutor) driver;
int pageNumber = 5;
```

```java
driver.get("https://www.javawebscrapingsandbox.com/product/infinite_scroll");
// 我们从 i=3 开始，因为第一次加载时
```

```java
List<WebElement> rows = driver.findElements(By.xpath("//tr"));
```

```java
// 对 rows 进行操作
processLines(rows);
```

## “最佳”方法：直接调用 API

我喜欢的使用 AJAX 爬取网站的方法是直接对 REST API 端点进行 HTTP 调用。在这种情况下，很容易理解要调用哪个 API，因为 Javascript 代码非常直观，而有时它可能会变得更复杂。一个好的方法是打开 Chrome 开发者工具，查看“网络”标签页中发生了什么。

![](img/cbd5c820756a64b88207a1ea9f1c877b_76_0.png)

我们可以清楚地看到被调用的 API URL 以及响应的内容。我们可以使用 `HtmlUnit` 或其他客户端来执行请求，并使用 `Jackson` 库解析 JSON。

### 直接 HTTP 调用示例

```java
WebClient client = new WebClient();
client.getOptions().setJavaScript(false);
client.getOptions().setCss(false);
client.getOptions().useInsecure(true);
java.util.logging.Logger.getLogger("com.gargles").setLevel(Level.OFF);

for (int i = 1; i < 5; i++) {
    Page json = client.getPage("https://www.javascriptscrapingsbox.com/product/api/" + i);
    parseJSON(json.ResponseBody().getContentAsString());
}
```

API 返回一个 JSON 数组，如下：

```json
{
    "id": 31,
    "name": "Marmot Drop's Jacket, Lightweight Fleece",
    "price": "74.96",
    "url": "https://www.amazon.com/dp/B5LC9R2?tag=thewire"
},
{
    "id": 32,
    "name": "ASUS ZenPad 3S (2048x1536), 4GB RAM, eMMC, 5MP Front Camera, 8MP Rear, Android 6.0, Tablet, Titanium Gray",
    "price": "296.07",
    "url": "https://www.amazon.com/dp/B0MXZV1"
},
{
    "id": 33,
    "name": "LG Electronics OLED65C7P65-Inch 4K Ultra HD Smart TV (2017 Model)",
    "price": "2596.99",
    "url": "https://www.amazon.com/dp/B1NAYM1"
}
```

### 解析 JSON 响应

这是一个解析此数组的方法，遍历每个元素并打印到控制台。通常我们不想这样做，可能你想将其导出为 CSV 文件或保存到数据库中...

```java
public static void parseJson(String jsonString) throws JsonException, IOException {
    ObjectMapper mapper = new ObjectMapper();
    JsonNode rootNode = mapper.read(jsonString);
    Iterator<JsonNode> elements = rootNode.elements();
    while(elements.hasNext()){
        JsonNode node = elements.next();
        Long id = node.get("id").asLong();
        String name = node.get("name").asText();
        String price = node.get("price").asText();
        System.out.println(String.format("Id: %s - Name: %s - Price: %s", id, name, price));
    }
}
```

## 处理 JS 渲染页面的技巧

在处理 JS 渲染页面时，有一些技巧：

- 尝试使用 Chrome 开发者工具的网络面板寻找隐藏的 API
- 尝试在你的网络浏览器中禁用 JavaScript，某些网站在这种情况下切换到服务器端渲染
- 寻找目标网站的移动版本，UI 通常更容易爬取。你可以使用自己的手机进行检查。如果它在没有重定向到移动 URL（如 `https://m.example.com` 或 `https://mobile.example.com`）的情况下运行，尝试在请求头中伪造 `User-Agent`

## 验证码破解、PDF 解析和 OCR

在本章中，我们将看到几种可能会阻止你爬取网站/提取信息的内容，例如验证码、PDF 和图像中的数据。

### 验证码类型

![](img/cbd5c820756a64b88207a1ea9f1c877b_81_0.png)

旧版验证码

还有这一个：

![](img/cbd5c820756a64b88207a1ea9f1c877b_81_1.png)

#### Google ReCaptcha v2

最后一种是使用最广泛的验证码机制 Google ReCaptcha v2。这就是我们要学习如何“破解”这些验证码的原因。

用户唯一需要做的就是点击复选框内部。然后该服务将分析许多因素来判断其是真实用户还是机器人。我们并不清楚具体是如何实现的，由于显而易见的原因，Google 没有公布这一点，但已经有很多推测：

- 点击行为分析：用户点击了哪里？光标加速等。
- 浏览器指纹
- 点击位置（你总是直接点击中心吗，还是随机的，像普通用户一样）
- 浏览器历史记录和 Cookie

像第一个那样的旧验证码，光学字符识别（OCR）以及最近的机器学习框架提供了极高的破解准确率（有时比人类还要高……），但对于 Recaptcha v2，最简单且准确的方法是使用第三方服务。

许多公司都提供验证码破解 API，使用真实的人工操作员来解决验证码。我不特别推荐某一个，但我发现 `2captcha.com`[^43] 易于使用、可靠且廉价（1000 个验证码只需 2.99 美元）。

[^43]: https://2captcha.com?from=6028997

在底层，`2captcha` 和其他类似的 API 需要特定的 `site-key` 和目标网站 URL，有了这些信息，他们能够让人工操作员来解决验证码。

```html
<div class="field">&gt;</div>
<div class="field"> 
<label for="recaptcha">&gt;</label>
<script src="https://www.google.com/recaptcha/api.js"></script>
<div class="g-recaptcha" data-sitekey="6L6degfBUAAAAAAjNA5rk2ZitaXzd0m0ajluYZnXX" -->
  <div style="width:380px; height:78px;">
    <div>
<iframe src="https://www.google.com/recaptcha/api2/anchor7ar?k=6L6degfBUAAAAAAjNA5W5nc2FuZi" role="78" frameborder="0" scrolling="no" sandbox="allow-forms allow-popups all" frameid="1"></iframe>
    </div>
  </</div>
</div>
```

从技术上讲，Recaptcha 挑战是一个包含一些魔法 Javascript 代码和一些隐藏输入的 iframe。当你通过点击或解决图片问题来“解决”挑战时，隐藏输入框会被填充一个有效的 token。

### 使用 2captcha 破解 ReCaptcha

![](img/cbd5c820756a64b88207a1ea9f1c877b_83_0.png)

我们感兴趣的是这个 token，`2captcha` API 将返回它。我们需要用这个 token 填充隐藏输入框并提交表单。

你需要做的第一件事是在 `2captcha.com`[^44] 创建一个账户并充值。

[^44]: https://2captcha.com?from=6028997

然后你将在主仪表上找到你的 API key。

一如既往，我设置了一个示例网页[^55]，包含一个有一个输入框和一个需要解决的 Recaptcha 的简单表单：

[^55]: https://www.javascriptwebscrapingsandbox.com/captcha

#### 表单示例

**输入你的名字**

名字

![](img/cbd5c820756a64b88207a1ea9f1c877b_84_0.png)

表单 + 验证码

我们将使用无头模式下的 Chrome 来提交此表单，并使用 `HtmlUnit` 向 `2captcha` 调用 API（我们可以使用任何其他 HTTP 客户端来完成此操作）。现在来写代码。

#### 实例化 WebDriver 和 WebClient

```java
final String API_KEY = "YOUR_API_KEY";
final String API_BASE_URL = "http://2captcha.com/";
final String BASE_URL = "https://www.javawebscrapingsandsbox.com/captcha/";

WebClient client = new WebClient();
client.getOptions().setJavaScriptEnabled(false);
client.getOptions().setCssEnabled(false);
client.getOptions().setInsecureSSL(true);
java.util.logging.Logger.getLogger("com.gargoylesoft").setLevel(Level.OFF);

// 替换为你自己的 chromedriver 路径
final String chromeDriverPath = "/usr/local/bin/chromedriver";
System.setProperty("webdriver.chrome.driver", chromeDriverPath);
```



```java
ChromeOptions options = new ChromeOptions();
options.addArguments("--headless", "--disable-gpu", "--window-size=1920,1080");
options.addArguments("--user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36");
options.addArguments("--ignore-certificate-errors");
WebDriver driver = new ChromeDriver(options);
```

# 验证码破解、PDF 解析和 OCR

我们感兴趣的是这个 token，`2captcha` API 将返回它。我们需要用这个 token 填充隐藏输入框并提交表单。

你需要做的第一件事是在 `2captcha.com` 创建一个账户并充值。

然后你将在主仪表盘上找到你的 API key。

一如既往，我设置了一个示例网页，包含一个有一个输入框和一个需要解决的 Recaptcha 的简单表单：

> https://2captcha.com?from=6028997
>
> https://www.javascriptwebscrapingsandbox.com/captcha

## 输入你的名字

名字

![](img/cbd5c820756a64b88207a1ea9f1c877b_84_0.png)

表单 + 验证码

我们将使用无头模式下的 Chrome 来提交此表单，并使用 `HtmlUnit` 向 `2captcha` 调用 API（我们可以使用任何其他 HTTP 客户端来完成此操作）。现在来写代码。

### 实例化 WebDriver 和 WebClient

```java
final String API_KEY = "YOUR_API_KEY";
final String API_BASE_URL = "http://2captcha.com/";
final String BASE_URL = "https://www.javawebscrapingsandbox.com/captcha/";

WebClient client = new WebClient();
client.getOptions().setJavaScriptEnabled(false);
client.getOptions().setCssEnabled(false);
client.getOptions().setInsecureSSL(true);
java.util.logging.Logger.getLogger("com.gargoylesoft").setLevel(Level.OFF);

// 替换为你自己的 chromedriver 路径
final String chromeDriverPath = "/usr/local/bin/chromedriver";
System.setProperty("webdriver.chrome.driver", chromeDriverPath);
```

```java
ChromeOptions options = new ChromeOptions();
options.addArguments("--headless", "--disable-gpu", "--window-size=1920,1080");
options.addArguments("--user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36");
options.addArguments("--ignore-certificate-errors");
WebDriver driver = new ChromeDriver(options);
```

![](img/cbd5c820756a64b88207a1ea9f1c877b_83_0.png)

我们感兴趣的是这个 token，`2captcha` API 将返回它。我们需要用这个 token 填充隐藏输入框并提交表单。

你需要做的第一件事是在 `2captcha.com` 创建一个账户并充值。

然后你将在主仪表盘上找到你的 API key。

一如既往，我设置了一个示例网页，包含一个有一个输入框和一个需要解决的 Recaptcha 的简单表单：

> https://2captcha.com?from=6028997
>
> https://www.javascriptwebscrapingsandbox.com/captcha

### 输入你的名字

名字

![](img/cbd5c820756a64b88207a1ea9f1c877b_84_0.png)

表单 + 验证码

我们将使用无头模式下的 Chrome 来提交此表单，并使用 `HtmlUnit` 向 `2captcha` 调用 API（我们可以使用任何其他 HTTP 客户端来完成此操作）。现在来写代码。

### 实例化 WebDriver 和 WebClient

# 验证码破解

## 验证码破解逻辑

```java
String siteID = "";
WebElement elem = driver.findElement(By.className("g-recaptcha"));
try {
  siteID = elem.getAttribute("data-sitekey");
} catch (Exception e) {
  System.out.println("未找到验证码 div");
}

String query = String.format("http://2captcha.com/in?key=%s&method=google&url=%s&site=%s", API_KEY, BASE_URL, siteID);
String response = client.get(query);
String stringResponse;
while (!stringResponse.contains("READY")) {
  Thread.sleep(5000);
  // ... 轮询结果的代码 ...
}

if (stringResponse.contains("OK|")) {
  captchaToken = stringResponse.split("\\|")[1];
} else {
  throw new Exception("2captcha 错误: " + stringResponse);
}
```

## 解决验证码

```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("document.getElementById('g-recaptcha').style.display = 'block';");
WebElement textarea = driver.findElement(By.xpath("textarea[@id='g-recaptcha']"));

textarea.sendKeys(captchaToken);
js.executeScript("document.getElementById('g-recaptcha').style.display = 'none';");
driver.findElement(By.id("name")).sendKeys("Kevin");
driver.findElement(By.id("submit")).click();
```

```java
if (driver.getPageSource().contains("your captcha was successfully submitted")) {
  System.out.println("验证码提交成功！");
} else {
  System.out.println("提交验证码时出错");
}
```

# PDF 解析

Adobe 在 90 年代初创建了便携文档格式（PDF）。直到今天，它仍被广泛用于跨平台文档共享。许多网站使用 PDF 导出用于文档、账单、手册……也许你现在正在以 PDF 格式阅读这本电子书。了解如何从 PDF 文件中提取信息是有用的，这正是我们要看的内容。

我制作了一个简单的页面，其中有一个指向 PDF 发票的链接。发票看起来像这样：

> https://www.javawebscrapingsandbox.com/pdf

## 发票

123-456-7890

no_reply@example.com

1234 Main Street

Anytown, State

邮编

收件人：Trenz Pruca

职位

公司名称

4321 First invoice

Anytown, State 邮编

日期： 22/06/2018

项目标题：项目名称

项目描述：在此处描述

采购订单号：12345

发票编号：67890

条款：30 天内

| 描述 | 数量 | 单价 | 费用 |
| --- | --- | --- | --- |
| 项目 1 | 55 € | 100 € | 5500 |
| 项目 2 | 13 € | 90 € | 1170 |
| 项目 3 | 25 € | 50 € | 1250 |
| | | | 小计 € 7920 |
| | | 税费 8,25 % € 653 |
| | | | 总计 € 8573 |

感谢您的光临。很高兴与您合作这个项目。

您的下次订单将在 30 天后发货。

诚挚地，

Urna Semper

## 发票

我们将介绍如何下载此 PDF 并从其中提取信息。

### 前提条件

我们需要 `HtmlUnit` 来获取网页并下载 PDF，以及 `PDFBox` 库来解析它。

pom.xml

```xml
<dependency>
  <groupId>org.apache.pdfbox</groupId>
  <artifactId>pdfbox</artifactId>
  <version>2.0.4</version>
</dependency>
```

## 下载 PDF

下载 PDF 像往常一样简单：

- 访问目标 URL
- 找到特定的锚点（anchor）
- 从锚点中提取下载 URL
- 使用 `Page` 对象获取 PDF，因为它不是 HTML 页面
- 检查刚刚下载的内容类型，确保它是 `application/pdf`
- 将 `InputStream` 复制到文件中

以下是代码：

### 下载发票

```java
HtmlPage html = client.getPage("https://www.javawebscrapingbox.com\npdf");
```

```java
// 选择第一个包含 "pdf" 的锚点
HtmlAnchor anchor = html.getFirstXPath("//a[contains(@href, 'pdf')");
String pdfUrl = anchor.getHrefAttribute();
```

```java
Page pdf = client.getPage(pdfUrl);
```

```java
if (pdf.getWebResponse().getContentType().equals("application/pdf")) {
  System.out.println("Pdf downloaded");
  IOUtils.copy(pdf.getWebResponse().getContentAsStream(),
    new FileOutputStream("invoice.pdf"));
  System.out.println("Pdf file created");
}
```

## 解析 PDF

现在磁盘上已经有了 PDF 文件，我们可以将其加载到 `PDFBox` 中以将内容提取为字符串。我们将从这张发票中提取价格。

一旦我们获取了 PDF 的文本内容，就可以使用正则表达式轻松地从中提取任何内容。文本内容如下：

## 下载发票

```
Title
Company Name
4321 First Street
Anyytown, State ZIP
Date: 22/06/2018
Project Title: Project Name
Project Description: Description Here
P.O. Number: 12345
Invoice Number: 67890
Terms: 30 Days
Thank you for your business. It's a pleasure to work with you on your project.
Your next order will ship in 30 days.
Sincerely yours,
Urna Semper
Description Quantity Unit Price Cost
Item 1 55 € 100 € 5 500
Item 2 13 € 90 € 1 170
Item 3 25 € 50 € 1 250
Subtotal € 920
Tax 8,25 % € 653
Total € 573
!1
INVOICE
123-456-7890
no_reply@example.com
1234 Main Street
```

Anytown, State

ZIP

我们需要遍历每一行，并使用带有捕获组的正则表达式，例如 `Total\\s+€\\s+()` 来提取总价。我们可以提取所需的任何内容，例如电子邮件地址、邮政地址、发票号码……

以下是完整的代码：

## 提取发票

```java
PDDocument document = null;
try {
    document = PDDocument.load(new File("invoice.pdf"));

    PDFTextStripperByArea stripper = new PDFTextStripperByArea();
    stripper.setSortByPosition(true);

    PDFTextStripper tStripper = new PDFTextStripper();

    String stringPdf = tStripper.getText(document);
    String lines[] = stringPdf.split("\\n");
    String pattern = "Total\\s+€\\s+(+)";
    Pattern p = Pattern.compile(pattern);
    String price = "";
    for (String line : lines) {
        Matcher m = p.matcher(line);
        if (m.find()) {
            price = m.group(1);
        }
    }

    if (!price.isEmpty()) {
        System.out.println("Price found: " + price);
    } else {
        System.out.println("Price not found");
    }
} finally {
  if (document != null) {
    document.close();
  }
}
```

`PDFBox` 库中有许多方法，你可以处理密码保护的 PDF、提取特定区域以及更多，这里是文档 (https://pdfbox.apache.org/docs/2.0.8/javocs/)。

# OCR 识别

现在我们已经知道了如何处理 PDF，我们将学习如何处理图像中的文本。图像中的文本是一种旨在让机器人难以提取的模糊技术。你可以在博客中经常发现这些隐藏电子邮件地址/电话号码的技术。

从图像中提取文本被称为“光学识别”或 OCR。有很多可用库，我们将使用 `Tesseract` (https://github.com/tesseract-ocr/tesseract)，它是最好的开源库之一。

## 安装

安装 `Tesseract` 及其依赖非常简单，在 Linux 上：

```
sudo apt install tesseract-ocr
sudo apt install libtesseract-dev
```

在 macOS 上：

```
brew install tesseract
```

关于带有特定标签的 `Tesseract` 的更多信息可以在这里找到：https://github.com/tesseract-ocr/tesseract/wiki

`Tesseract` 是 C++ 编写的，所以我们需要一些 Java 绑定：http://bytedeco.org/

pom.xml

```xml
<dependency>
  <groupId>org.bytedeco.javacpp-presets</groupId>
  <artifactId>tesseract-platform</artifactId>
  <version>3.0.1</version>
</dependency>
```

## Tesseract 示例

我对之前的 PDF 截了图：

# Project Title: Project Name

Project Description: Description Here

P.O. Number: 12345

Invoice Number: 67890

Terms: 30 Days

## OCR 示例



假设我们想提取发票号码。第一步是定位 `tessdata` 文件夹，它包含了 `tesseract` 识别特定字符所需的所有内容。位置取决于你如何安装 `tesseract`。

```
final static String TESS_DATA_PATH = "/path/to/tessdata";
```

以下是完整的代码：

```
BytePointer outText;
TessBaseAPI api = new TessBaseAPI();

if (api.Init(TESS_DATA_PATH, "ENG") != 0) {
    System.err.println("Could not initialize tesseract.");
    System.exit(1);
}
```

```
PIX image = lept.pixRead("ocr_exemple.jpg");
api.SetImage(image);
```

```
// 获取 OCR 结果
outText = api.getUTF8Text();
String string = outText.getString();
String invoiceNumber = "";
for(String lines : string.split("\n"))
```

// 销毁使用的对象并释放内存

```
api.End();
outText.deallocate();
lept.pixDestroy(image);
```

这只是如何使用 `Tesseract` 进行简单 OCR 的示例，我不是 OCR 和图像处理专家，但这里有一些建议：

- 使用正确的语言初始化 `Tesseract`。图像处理：图像裁剪、不同的对比度、缩放、去除边框……可以显著提高 `Tesseract` 输出的质量。
- 你可以使用像 `api.SetVariable("tess_char_whitelist", "0123456789")` 的选项来仅包含数字。这将避免混淆。
- 关于此的更多信息请查看文档：https://github.com/tesseract-ocr/tesseract/wiki。

# 伪装

在本章中，我们将学习如何让我们的机器人看起来像人类。由于各种原因，网站有时会实现反机器人机制。保护网站免受机器人侵害的最明显理由是防止大量的自动化流量影响网站性能。另一个原因是停止机器人的恶意行为（如垃圾邮件）。

有各种保护机制。有时如果机器人每秒/每小时/每天请求过多，就会被屏蔽。有时会对每个 IP 地址的次数进行限制。最困难的保护是用户行为分析。例如，网站可以分析请求之间的时间间隔，同一个 IP 是否在并发请求。

你不一定需要本章中的所有建议，但如果你的机器人无法工作，或者某些功能在 Java 代码中的运行情况与真实浏览器不同，它们可能会有所帮助。

## 头部

我们在第三章中介绍了 HTTP 头部。你的浏览器系统地包含 6-7 个头部，正如你在浏览器的网络检查器中检查请求时所示。

## 隐藏身份

### 请求头 (Request Headers)

- `authority: www.javascriptwebscrapinghandler.com`
- `method: GET`
- `path: /`
- `scheme: https`
- `accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*;q=0.8`
- `accept-encoding: gzip, deflate, br`
- `accept-language: en-US,q=0.8,fr-FR;q=0.6`
- `cache-control: no-cache`
- `cookie: _ga_1.252764229.153821755-_Ga_1.2.251756985-_ga_gat_ua_UA_108465012-1`
- `pragma: no-cache`
- `upgrade-requests: 1`
- `user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_5) AppleWebKit/537.36 (KHTML, like Gecko) Safari/537.36`

如果你在请求中不发送这些头部，目标服务器可以很容易识别出你的请求不是从普通网络浏览器发送的。如果服务器具有某种反爬机制，可能会发生不同的情况：

* HTTP 响应可能会发生
* 你的 IP 地址可能会被封禁
* 验证码 (Captcha)
* 对你的请求进行频率限制

### HttpClient 提供了一种自定义 HTTP 客户端头部的简单方法

### 使用请求头初始化客户端

```
HttpClient = new HttpClient();

client.addRequestHeader("Accept", "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*;q=0.8");

client.addRequestHeader("Accept-Encoding", "gzip, deflate, br");

client.addRequestHeader("Accept-Language", "en-US,q=0.9,fr-FR;q=0.8,fr;q=0.7,la;q=0.6");

client.addRequestHeader("Connection", "keep-alive");

client.addRequestHeader("Host", "ksah.in");

client.addRequestHeader("User-Agent", "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396/99 Safari/537.36");

client.addRequestHeader("Pragma", "no-cache");
```

我们可以更进一步，为我们的 `HttpClient` 分配随机的 `User-Agent`。随机化 `user-agents` 有助于隐藏你的机器人。一个很好的解决方案是创建一个常见的 `User-Agents` 列表并从中随机选择一个。你可以在这里找到这样一个列表：https://developers.whatismybrowser.com/agents/explore

我们可以创建一个包含许多不同 `user agents` 的文件：

`user-agents.txt`

```
Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.1 (KHTML, like Gecko) Chrome/13.0.782.111 Safari/535.1

Mozilla/5.0 (Windows NT 6.0) AppleWebKit/535.1 (KHTML, like Gecko) Chrome/13.0.782.111 Safari/535.1

Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.31 (KHTML, like Gecko) Chrome/26.0.1410.64 Safari/537.31

Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/27.0.1453.116 Safari/537.36

Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/27.0.1453.116 Safari/537.36

Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.1 (KHTML, like Gecko) Chrome/21.0.1180.89 Safari/537.1

Mozilla/5.0 (Windows; Windows NT 6.1; en-US) AppleWebKit/532.2 (KHTML, like Gecko) Chrome/4.0.221.7 Safari/532.2

Mozilla/5.0 (Windows; Windows NT 5.1; en-US) AppleWebKit/525.13 (KHTML, like Gecko) Chrome/0.2.149.22 Safari/525.13

Mozilla/5.0 (Windows NT 5.1; rv:5.0.1) Gecko/20100101 Firefox/5.0

Mozilla/5.0 (Windows NT 6.1; rv:5.0) Gecko/20100101 Firefox/5.0

Mozilla/5.0 (Windows NT 6.1; WOW64; rv:5.0) Gecko/20100101 Firefox/5.0

Mozilla/5.0 (Windows NT 6.1; rv:2.0b7pre) Gecko/20100921 Firefox/4.0b7p

Mozilla/5.0 (X11; Linux x86; fr-fr) Gecko/20100423 Ubuntu/10.04 Firefox/3.6 AppleWebKit/532.4

Mozilla/5.0 (Windows NT 5.1; rv:9.0.11) Gecko/20090610 Firefox/30.11

Mozilla/5.0 (Windows NT 5.1; en-US; rv:9.1.3) Gecko/20090824 Firefox/35.3
```

然后是一个简单的辅助方法，用于读取此文件并返回随机的 `user agent`：

### 随机 user agent 方法

```
private static String getRandomUseragent() {

    List<String> userAgents = new ArrayList<>();

    Random rand = new Random();

    try (BufferedReader br = new BufferedReader(new FileReader("user-agents.txt"))) {

        String sCurrentLine;

        while ((sCurrentLine = br.readLine()) != null) {

            userAgents.add(sCurrentLine);

        }

    } catch (IOException e) {

        e.printStackTrace();

    }

    return userAgents.get(rand.nextInt(userAgents.size()));

}
```

我们可以在给 `HttpClient` 分配一个随机的 `user agent`：

### 设置 user-agent

```
client.addRequestHeader("User-Agent", getRandomUseragent());
```

## 代理 (Proxies)

隐藏爬虫最简单的方法是使用代理。很多情况下，网站会根据 IP 地址来限制你，因此你应该使用代理。在 `HttpClient` 中配置代理是简单的。我不建议使用免费的代理，因为它们通常很慢且不可靠。你可以通过配置 `HttpClient` 来隐藏你的 IP：

```
Config proxyConfig = new ProxyConfig("host", myPort);

client.getOptions().setProxyConfig(proxyConfig);
```

## TOR: 洋葱路由 (The Onion Router)

`TOR`，也称为洋葱路由，是一个通过多个服务器路由流量以隐藏其来源的全球计算机网络。`TOR` 使用使得网络监控变得非常困难。`TOR` 有很多使用场景，例如隐私、言论自由、独裁国家下的记者，当然还有非法活动。在爬虫上下文中，`TOR` 可以隐藏你的 IP 地址，并每 10 分钟更改一次 IP 地址。`TOR` 出口节点的 IP 是公开的。有些网站使用简单的规则阻止 `TOR` 流量：如果收到来自 `TOR` 出口节点的请求，它将被拦截。这就是为什么在很多情况下，与传统的代理相比，`TOR` 对你没有帮助。使用 `TOR` 非常简单，去下载页面，或者在 macOS 上使用包管理器：

```
brew install tor
```

然后你需要启动 `TOR` 进程，并为 `HttpClient` 设置代理配置：

```
WebClient webClient = new WebClient();

ProxyConfig prc = new ProxyConfig("localhost", 9150, true);

webClient.getOptions().setProxyConfig(prc);
```

## 提示 (Tips)

### Cookie

如，`Cookie` 有很多用途。如果你发现目标网站对你的机器人响应不同，尝试分析由客户端 JavaScript 代码设置的 `Cookie` 并手动注入它们。你也可以使用无头模式的 `Chrome` 来更好地处理 `Cookie`。

### 时机 (Timing)

如果你想隐藏你的爬虫，你必须表现得像人类。人类在到达网页后不会在 0.2 秒内就点击链接。他们也不会每隔 5 秒就点击一次链接。在你的请求之间添加一些随机时间来隐藏你的爬虫。快速爬取不是好的做法。你会被封禁，如果你在小型网站上这样做，会给网站服务器带来巨大压力，在某些情况下甚至可能被视为攻击。

## 不可见元素 (Invisible elements)

不可见元素是一种用于检测机器人访问和爬取网站的技巧。通常，一个或多个元素会用 CSS 隐藏，并且会有代码在发生点击时通知网站服务器在元素下方保持隐蔽状态，或者对一个隐藏链接发送请求。然后服务器将封锁该机器人的 IP 地址。

避免这种陷阱的一个好方法是使用 `Selenium` API 中的 `isDisplayed()` 方法。

### 仅与可见元素交互

```
WebElement elem = driver.findElement(By.xpath("//div[@class='something']"));

if(elem.isDisplayed()) {

    // 执行一些操作

}
```

另一种技术是在表单中包含隐藏输入框（hidden inputs）。如果你在提交包含隐藏隐藏的表单时遇到问题，请确保在请求中包含这些输入框，并且不要修改它们的值。

### 隐藏输入

```html
<form>

  <input type="hidden" name="itsatrap" value="value1"/>

  <input type="text" name="email"/>

  <input type="submit" value="Submit"/>

</form>
```

# 云爬虫

## 无服务器部署

在本章中，我们将为我们的机器人介绍无服务器（serverless）部署。无服务器是指在临时容器（函数即服务，或 FaaS）内部执行代码的术语。在“微服务”热潮之后，它是 2018 年的热门话题，现在“纳级服务”来了！

云函数可以由不同的事件触发，例如：

- 对 REST API 的 HTTP 调用
- 消息队列中的作业
- 日志
- IOT 事件

出于许多原因，云函数非常适合网络爬虫。网络爬虫是 I/O 密集型的，大部分时间都花在等待 HTTP 响应，因此我们不需要高端 CPU 服务器。云函数廉价且易于设置。云函数非常适合并行计算，我们可以同时为大规模爬取同时创建数百或数千个函数。

## 部署 Azure 函数

![](img/cbd5c820756a64b88207a1ea9f1c877b_106_0.png)

我们将把一个爬虫程序部署到 Azure 云函数中。我没有偏好的供应商，`AWS Lambda` 也是一个很棒的平台。`Google Cloud` 目前不支持 Java，只支持 Node.js。

我们将重用在第 3 章中构建的 Hacker news 爬虫，并在其之上实现一个小小的 API，这样我们就可以带上 `page` 参数调用此 API，函数将返回该页码对应的每个 hacker news 项目的 JSON 数组。

### 前提条件

你将需要：

- `JDK 8`
- `Maven 3+`
- `Azure CLI` 54

> 54 https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest

- `Azure 函数工具` 55
- `Azure 账户` 56

每个 Azure 组件的安装都有特定于平台的说明，我建议你仔细阅读这些说明。

一旦在系统中安装了所有内容，请确保使用 `Azure CLI` 登录：

```
az login
```

### 创建、运行和部署项目

我们将使用 `Maven archetype` 57 来创建项目结构：

`Maven archetype`

```bash
mvn archetype:generate \
-DarchetypeGroupId=com.microsoft.azure \
-DarchetypeArtifactId=azure-functions-archetype
```



然后 Maven 将询问你有关项目的详细信息。生成的代码简洁且直观：

> 55 https://docs.microsoft.com/en-us/azure/azure-functions/run-local#v2
> 56 https://azure.microsoft.com/en-us/free/
> 57 https://maven.apache.org/guides/introduction/introduction-to-archetypes.html

# 云爬虫

## 自动生成的函数

```java
public class Function {

  /**
   * 此函数监听端点 "api/hello"。在 bash 中使用 `curl` 命令调用它的两种方式：
   * 1. `curl -d "" {host}/api/hello`
   * 2. `curl {host}/api/hello?name=value`
   */
  @FunctionName("hello")
  public HttpResponseMessage<String> hello(
      @HttpTrigger(name = "req", methods = {"get"}, authLevel = AuthorizationLevel.ANONYMOUS) HttpRequestMessage<Optional<String>> request,
      final ExecutionContext context) {
      context.getLogger().info("Java trigger processed.");
      // 解析参数
      String query = request.getQueryParameters().get("name");
      String name = request.getBody().orElse(query);
      if (name == null) {
          return request.createResponse(400, "Please pass a name on the query");
      } else {
          return request.createResponse(200, "Hello, " + name);
      }
  }
}
```

你可以通过以下命令部署你的函数：

```bash
mvn package
mvn azure-functions:deploy
```

# 云端爬虫

```json
{
  "author": "iafrikan",
  "score": 62,
  "position": 123,
  "id": 17599022
}
```

就是这些了。与其返回 JSON 数组，我们也可以将其存储在 Azure 支持的各种数据库系统中。

我建议你进行一些实验，特别是在消息队列方面。对于你的爬虫项目，一种有趣的架构是将任务发送到消息队列中，让 Azure Function 消费这些任务，并将结果保存到数据库中。你可以在[这里](https://docs.microsoft.com/en-us/azure/functions/functions/create-storage-queue-triggered-function)了解更多关于该主题的内容。

Azure 以及像 Amazon Web Service 等其他云供应商的可能性是无限的且易于实现的，尤其是无服务器架构（`serverless architecture`），我强烈推荐尝试这些工具。

# 结

本指南到此结束。希望你喜欢它。现在你应该能够编写自己的爬虫、检查 DOM 和网络请求、处理 JavaScript、重现 AJAX 调用、破解验证码（`Captcha`）和 `Recaptcha`、使用不同的技术隐藏你的爬虫，并将你的代码部署在云端了！

这本书永远不会完结，因为我从读者那里收到了很多反馈。我想添加很多章节：更多的案例研究、一个关于网络爬虫法律方面的章节、一个关于多线程爬虫的章节等。如果感兴趣的人足够，我可能会创建一个完整的视频课程 ;)

我制作了一个[Google 表单](https://docs.google.com/forms/d/e1FALQlSeis42-NHXeFjFeRLQ6L82-YawEb6AlBrOWsN0F4lzZsPpz6ug/view) 来收集读者的反馈，如果你能填写，我将不胜感激！

59 https://docs.microsoft.com/en-us/azure/functions/functions/create-storage-queue-triggered-function
60 https://docs.google.com/forms/d/e1FALQlSeis42-NHXeFjFeRLQ6L82-YawEb6AlBrOWsN0F4lzZsPpz6ug/view

你可以通过 `hi@ksah.in` 向我发送邮件，也可以在 Twitter 上找到我！
Kevin

61 https://twitter.com/SahinKevin
