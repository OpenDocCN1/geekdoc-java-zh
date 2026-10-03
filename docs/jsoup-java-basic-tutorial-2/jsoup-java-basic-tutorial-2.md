
# jsoup-java 入门教程

# 致谢

# 关于

你可以将此 PDF 分享给任何你认为能从中受益的人，最新版本可以从此处下载：jsoup

这是一本为了教学目的而创建的非官方免费的 Jsoup 电子书。所有内容均提取自 Stack Overflow 文档，这些文档由 Stack Overflow 的许多辛勤工作的人士编写。它既不属于 Stack Overflow 附属，也不是 Jsoup 的官方出品。

使用书中呈现的内容风险需自负；我们不保证其正确或准确，请将您的反馈和修正发送至 `info@zzzprojects.com`

# 第 1 章：Jsoup 入门

## 备注

Jsoup 是一个用于 Java 的 HTML 解析和数据提取库，侧重于灵活性和易用性。它可以从 HTML 页面中提取特定数据（通常被称为“网络爬虫”），还可以修改 HTML 页面的内容，并使用允许的标签和属性白名单来“清理”不可信的 HTML。

## JavaScript 支持

**Jsoup 不支持 JavaScript**，正因如此，任何动态生成的内容或添加到页面的内容都无法被提取。如果你需要提取通过 JavaScript 添加到页面的内容，有几种替代方案：

- 使用支持 JavaScript 的库，例如 `Selenium` 或 `HtmUnit`，它们使用真实的浏览器来加载页面。
- 反向工程通过 AJAX 加载页面，因此你可以查看浏览器的网络标签查看数据来自哪里。

## 官方网站与文档

你可以在 `jsoup.org` 找到各种 Jsoup 相关资源，包括 Javadoc、Jsoup 食谱以及 JAR 下载。

## 下载

Jsoup 可以在 Maven 上作为 `org.jsoup` 获取。如果你在 Android Studio 中使用 Gradle，可以通过在 `build.gradle` 中添加以下内容加入项目：

```gradle
compile 'org.jsoup:jsoup:1.8.3'
```

如果你在使用 Ant (Eclipse)，请在 POM 部分添加以下内容：

```xml
<dependency>
  <groupId>org.jsoup</groupId>
  <artifactId>jsoup</artifactId>
  <version>1.8.3</version>
</dependency>
```

Jsoup 也可以作为下载的 JAR 用于其他环境。

## 版本

| 版本 | 发布日期 |
| --- | --- |
| 1.9.2 | 2016-05-17 |
| 1.8.3 | 2015-08-02 |

## 示例

### 提取链接的 URL 和标题

Jsoup 可以轻松从网页提取所有链接。在这种情况下，我们可以使用 Jsoup 提取我们需要的特定链接，位于页面上的 h3 Header。我们还可以获取链接的文本。

```java
Document doc = Jsoup.connect("http://stackoverflow.com").userAgent("Mozilla").get();
for (Element e : doc.select(".question-hyperlink")) {
  System.out.println(e.attr("abs:href"));
  System.out.println(e.text());
  System.out.println();
}
```

这得到了以下输出：

```
http://stackoverflow.com/questions/12920296/past-5-week-calculation-in-webi-bo-4-0
Past 5 week calculation in WEBI (BO 4-0)?

http://stackoverflow.com/questions/3603701/how-to-get-information-about-the-visualized-elements-in-listview
How to get information about the visualized elements in listview?
```

发生了什么：

- 首先，我们从指定的 URL 获取 HTML 文档。这段代码还将请求的 User Agent Header 设置为“Mozilla”，这样网站就会像往常向浏览器那样提供内容。
- 然后，使用 `select(...)` 和 `for` 循环获取所有 Stack Overflow 问题的链接，在本例中具有 `question-hyperlink` 类的链接。
- 使用 `.text()` 输出每个链接的文本，并使用 `.attr("abs:href")` 输出链接的 href。

在这种情况下，我们使用 `abs:` 来获取绝对 URL，即包含域名和协议的 URL。

### 从部分 HTML 中提取完整 URL

仅选择链接的 `href` 属性值将返回相对 URL。

```java
String bodyFragment = "<div><a href=\"/documentation\">Stack Overflow Documentation</a></div>";

Document doc = Jsoup.parseBodyFragment(bodyFragment);
String link = doc
  .select("div > a")
  .first()
  .attr("href");

System.out.println(link);
```

## 输出

```
/documentation
```

通过将基础 URI 传递给 `parse` 方法并使用 `absUrl` 方法代替 `attr`，我们可以提取完整的 URL。

```java
Document doc = Jsoup.parseBodyFragment(bodyFragment, "http://stackoverflow.com");

String link = doc
  .select("div > a")
  .first()
  .absUrl("href");

System.out.println(link);
```

## 输出

```
http://stackoverflow.com/documentation
```

### 从 HTML 文档文件中提取数据

Jsoup 可用于操作或从本地包含 HTML 的文件中提取数据。`filePath` 是磁盘上的路径。`ENCODING` 是期望的字符集名称，例如 "Windows-31J"。它是可选的。

```java
// 加载文件
File inputFile = new File(filePath);
// 将文件解析为 HTML 文档
Document doc = Jsoup.parse(filePath, ENCODING);
// 通过 "a" 选择元素
Elements elements = doc.select("a");
```

在线开始使用 Jsoup: [https://rtptutorial.com/jsoup/topic/297/getting-started-with-jsoup](https://rtptutorial.com/jsoup/topic/297/getting-started-with-jsoup)

# 第 2 章：格式化 HTML 输出

## 参数

| 参数 | 详情 |
| --- | --- |
| `boolean outline()` | 获取是否启用了大纲模式。默认是 false。如果启用，HTML 输出方法将认为所有标签均为块级元素。 |
| `Document.OutputSettings outline(boolean)` | 启用或禁用 HTML 大纲模式。 |

## 备注

- Jsoup 1.9.2 API

## 示例

### 将所有元素显示为块级元素

默认情况下，Jsoup 将仅显示带有尾部换行符的块级元素。内联元素在不换行的情况下不会显示。

给定一个包含内联元素的体片段：

```html
<select name="menu">
  <option value="foo">foo</option>
  <option value="bar">bar</option>
</select>
```

使用 Jsoup 打印：

```java
Document doc = Jsoup.parse(html);
System.out.println(doc.html());
```

结果为：

```html
<html>
<head></head>
<body>
  <select name="menu">
    <option value="foo">foo</option>
    <option value="bar">bar</option>
  </select>
</body>
</html>
```

要以将每个元素都视为块级元素的方式显示输出，必须在文档的 `OutputSettings` 上启用 `outline` 选项。

```java
Document doc = Jsoup.parse(html);
doc.outputSettings().outline(true);
System.out.println(doc.html());
```

## 输出

```html
<html>
<head></head>
<body>
<select name="menu">
<option value="foo">foo</option>
<option value="bar">bar</option>
</select>
</body>
</html>
```

来源：Jsoup - 格式化 `<option>` 元素

在线阅读格式化 HTML 输出：[https://riptutorial.com/jsoup/topic/5954/formatting-html-output](https://riptutorial.com/jsoup/topic/5954/formatting-html-output)

# 第 3 章：使用 Jsoup 登录网站

## 示例

### 使用 Jsoup 进行简单的身份验证 POST 请求

下面演示了一个带有身份验证数据的简单 POST 请求，注意此请求取决于网站：

```java
final String USERAGENT = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36";
String LOGIN_URL = "https://example.com/login";
String body = "username=password=password";
Document doc = Jsoup.parse(body); // 此处仅为演示
// 实际应使用：
// Connection res = Jsoup.post(LOGIN_URL, body);
```

### 带有身份验证数据的简单 POST 请求

下面演示了一个带有身份验证数据的简单 POST 请求，注意此请求取决于网站：

```java
// 示例：使用 Jsoup 发送身份验证 POST 请求
String login_URL = "https://example.com/login";
Map<String, String> formData = new HashMap<>();
formData.put("username", "myuser");
formData.put("password", "mypass");

Connection res = Jsoup.post(login_URL, formData);
Document doc = res.parse();
```

### 使用 Jsoup 复杂的 POST 请求

大多数网站的身份验证过程比上述的要复杂。

登录网站的常见步骤：

1. 获取初始请求的 cookie
2. 检查表单
3. 解析表单以查看需要随请求发送的安全 token
4. 发送请求。

下面是一个使用 Jsoup 处理 cookie 的示例：

```java
Map<String, String> cookies = new HashMap<>();
Connection conn = Jsoup.connect(LOGIN_URL);
response = conn.execute();
cookies = response.cookies();

Map<String, String> formData = new HashMap<>();
formData.put("username", "myuser");
formData.put("password", "mypass");
formData.put("authenticity_token", authToken);

Connection res = Jsoup.connect(ACTION_URL)
    .cookies(cookies)
    .data(formData)
    .method(Method.POST)
    .execute();
```

### 登录 FormElement

在本示例中，我们将使用 `FormElement` 类登录网站。

```java
public static void checkElement(String name, Element elem) {
    if (elem == null) {
        throw new RuntimeException("无法找到 " + name);
    }
}
```

在线阅读登录网站：[https://riptutorial.com/jsoup/topic/4631/logging-into-websites](https://riptutorial.com/jsoup/topic/4631/logging-into-websites)

# 第 4 章：解析 JavaScript 生成的页面

## 示例

### 使用 Jsoup 和 HtmUnit 解析 JavaScript 生成的页面

**page.html**

```html
<html>
<head>
  <script src="loadData.js"></script>
</head>
<body onload="loadData()">
  <div class="container">
    <table id="data" border="1">
      <tr>
        <th>col1</th>
        <th>col2</th>
      </tr>
    </table>
  </div>
</body>
</html>
```

**loadData.js**

```javascript
// 向 page.html 中的 table.data 添加行和列
function loadData() {
  var data = document.getElementById("data");
  for (var row = 0; row < 2; row++) {
    var tr = document.createElement("tr");
    for (var col = 0; col < 2; col++) {
      var td = document.createElement("td");
      td.appendChild(document.createTextNode("." + col));
      tr.appendChild(td);
    }
    data.appendChild(tr);
  }
}
```

**page.html 加载到浏览器时**

| Col1 | Col2 |
| --- | --- |
| 0.0 | 0.1 |
| 1.0 | 1.1 |

### 发生了什么？

Jsoup 解析从服务器交付的源码（在本例中为从文件加载的源码）。它不会调用客户端操作，例如 JavaScript 或 CSS DOM 操作。在这个示例中，行和列从未被附加到数据表中。

### 如何解析在浏览器中渲染的页面？

```java
// 使用 HTML Unit 加载页面并触发脚本
WebClient webClient = new WebClient();
HtmlPage myWeb = webClient.getPage(new File("page.html").toURI().toURL());

// 将页面转换为生成的 HTML 并转换为文档
doc = Jsoup.parse(myWeb.asXml());

// 遍历行和列
for (Element row : doc.select("table#data > tr")) {
  for (Element col : row.select("td")) {
    // 打印结果
    System.out.println(col.ownText());
  }
}

// 清理资源
webClient.close();
```

## 输出

```
0.0
0.1
1.0
1.1
```

在线解析 Javascript 生成的页面：[https://riptutorial.com/jsoup/topic/4632/parsing-javascript-generated-pages](https://riptutorial.com/jsoup/topic/4632/parsing-javascript-generated-pages)

# 第 5 章：选择器

## 备注

选择器是由组合符分隔的简单选择器链。选择器是不区分大小写的（包括针对元素、属性和属性值）。

当未提供元素选择器时，通用选择器 (`*`) 是隐式的（即 `*.header` 与 `.header` 是等价）。

| 模式 | 匹配 | 示例 |
| --- | --- | --- |
| `*` | 任何元素 | `*` |
| `tag` | 具有给定标签名的元素 | `div` |
| `ns:E` | 命名空间 ns 中类型为 E 的元素 | `fb:name` 查找 `<fb:name>` 元素 |
| `#id` | ID 为 "id" 的元素 | `div#wrap`, `#logo` |
| `.class` | 类名为 "class" 的元素 | `div.left`, `.result` |



# 选择器完整引用

| 模式 | 匹配 | 示例 |
| --- | --- | --- |
| `[attr]` | 属性名为 `attr` 的元素（值任意可） | `a[href]`, `[title]` |
| `[attrPrefix]` | 属性名以 `attrPrefix` 开头的元素。用于查找带有 HTML5 数据集的元素 | `[^data]`, `div[^data-]` |
| `[attr=val]` | 属性名为 `attr` 且值等于 `val` 的元素 | `img[width=500]`, `a[rel=nofollow]` |
| `[attr="val"]` | 属性名为 `attr` 且值等于 `val` 的元素 | `span[hello="Cleveland"][goodbye="Columbus"]`, `a[rel="nofollow"]` |
| `[attr^=valPrefix]` | 属性名为 `attr` 且值以 `valPrefix` 开头的元素 | `a[href^=http:]` |
| `[attr$=valSuffix]` | 属性名为 `attr` 且值以 `valSuffix` 结尾的元素 | `img[src$=.png]` |
| `[attr*=valContaining]` | 属性名为 `attr` 且值包含 `valContaining` 的元素 | `a[href*=/search/]` |
| `[attr~=regex]` | 属性名为 `attr` 且值匹配正则表达式的元素 | `img[src~=(?i)\.(png|jpe?)]` |
| | 以上内容可以任意顺序组合 | `div.header[title]` |

# 示例

## 使用 CSS 选择器选择元素

```java
String html = "<!DOCTYPE html>" +
  "<html>" +
  "<head>" +
    "<title>Hello world!</title>" +
  "</head>" +
  "<body>" +
    "<h1>Hello there!</h1>" +
    "<p>First paragraph</p>" +
    "<p class=\"not-first\">Second paragraph</p>" +
    "<p class=\"not-first third\">Third <a href=\"page.html\">paragraph</a></p>" +
  "</body>" +
  "</html>";
```

```java
// 解析文档
Document doc = Jsoup.parse(html);
```

```java
// 获取文档标题
String title = doc.select("head title").first().text();
System.out.println(title); // Hello world!
```

```java
// 获取除第一个之外以外的所有段落
Elements otherParagraphs = doc.select("p.not-first");
// 等同于
otherParagraphs = doc.select("p");
otherParagraphs.remove(0);
```

```java
// 获取第三个段（在 otherParagraphs 列表中的第二个）
// 排除第一个段
Element thirdParagraph = otherParagraphs.get(1);
// 替代方案：
thirdParagraph = doc.select("p.third");
```

```java
// 你也可以在元素内部进行选择，例如第三个段内带有 href 属性的锚点
Element link = thirdParagraph.select("a[href]");
// 或者文档正体中的第一个 <h1> 元素
Element headline = doc.select("body").first().select("h1").first();
```

你可以在此处找到受支持选择器的详细概述。

## 提取 Twitter 标记

```java
// Twitter 标记文档：
// https://dev.twitter.com/cards/markup
String[] twitterTags = {
  "twitter:site",
  "twitter:site:id",
  "twitter:creator",
  "twitter:creator:id",
  "twitter:description",
  "twitter:title",
  "twitter:image:alt",
  "twitter:player",
  "twitter:player:width",
  "twitter:player:height",
  "twitter:player:stream",
  "twitter:app:name:iphone",
  "twitter:app:id:iphone",
  "twitter:app:url:iphone",
  "twitter:app:name:ipad",
  "twitter:app:id:ipad",
  "twitter:app:url:ipad",
  "twitter:app:name:googleplay",
  "twitter:app:id:googleplay",
  "twitter:app:url:googleplay"
};
```

```java
// 连接到 URL 并提取源码
Document doc = Jsoup.connect("http://stackoverflow.com/").get();
```

```java
for (String twitterTag : twitterTags) {

  // 查找匹配的 meta 标签
  Element meta = doc.select("meta[name=" + twitterTag + "]").first();

  // 如果找到，获取 content 属性的值
  String content = meta != null ? meta.attr("content") : "";

  // 显示结果
  System.out.printf("%s = %s%n", twitterTag, content);
}
```

## 输出

```
twitter:site =
twitter:site:id =
twitter:creator =
twitter:creator:id =
twitter:description = Q&A for professional and enthusiast programmers
twitter:title = Stack Overflow
twitter:image =
twitter:image:alt =
twitter:player =
twitter:player:width =
twitter:player:height =
twitter:player:stream =
twitter:app:name:iphone =
twitter:app:id:iphone =
twitter:app:url:iphone =
twitter:app:name:ipad =
twitter:app:id:ipad =
twitter:app:url:ipad =
twitter:app:name:googleplay =
twitter:app:id:googleplay =
twitter:app:url:googleplay
```

```java
public static void main(String[] args) {

    readAllLinks obj = new readAllLinks();
    my_site = "stackoverflow.com";
    obj.get_links("http://stackoverflow.com/");
}

private void get_links(String url) {
    try {
        Document doc = Jsoup.connect(url).userAgent("Mozilla").get();
        Elements links = doc.select("a");
        
        if (links.isEmpty()) {
            return;
        }

        links.stream().map(link -> link.attr("href")).forEachOrdered((this_url) -> {
            boolean add = uniqueURL.add(this_url);
            if (add && this_url.contains(my_site)) {
                System.out.println(this_url);
                get_links(this_url);
            }
        });
    } catch (IOException ex) {
    }
}
```

该程序的执行时间取决于你的网站，可能会花费长时间。上述代码可以扩展，用于从特定网站提取数据（如页面标题、文本或图像）。我建议在抓取链接之前，先阅读公司的使用条款。

示例使用了 Jsoup 库来获取链接，你也可以通过 `your_url/sitemap.xml` 获取链接。

在线阅读使用 Jsoup 进行网络爬虫教程：https://riptutorial.com/jsoup/topic/319/web-crawling-jsoup

# 鸣谢

| 序号 | 章节 | 贡献者 |
| --- | --- | --- |
| 1 | Jsoup 入门 | Alice, Community, Jeffrey Bosboom, JonasCz, Zack Teater |
| 2 | HTML 输出格式化 | Zack Teater |
| 3 | 使用 Jsoup 登录网站 | Joel Min, JonasCz, Stephan |
| 4 | 解析 JavaScript 生成的页面 | Zack Teater |
| 5 | 选择器 | JonasCz, Stephan, still_learning, Zack Teater |
| 6 | 使用 Jsoup 进行网络爬虫 | Alice, JonasCz, r_D, RamenChef |
