
# PHP：初学者指南，在 6 小时内学习 PHP 和 MySQL 编程的终极分步指南

## 绪言

你是否被创建自己网站的想法所启发？是否曾想过拥有一个具有登录/退出功能的网站有多酷？你是否需要学会如何在数据库中创建、读取、更新或删除（CRUD）记录？你是否已经忘记了过去的教学练习？在考虑了这些问题后，我将向你展示如何在没有任何外部帮助的情况下制作网站，你将了解 PHP 网站代码函数中的每一个细微元素。如果你是后端 Web 开发的新手，这本教程正是为你准备的。

我将澄清你感兴趣的每一个点，这样你就不需要研究 PHP 中使用的某些特定技术了。为了尽可能保持简单，我们不会使用任何复杂的系统。此外，我不会专注于功能实现后的网站设计。然而，执行这些设计绝非难事。这本书将对整个 PHP 编码过程进行简单而详尽的分析。

那么，什么是 PHP 呢？如果你需要设计一个网站，你可能需要这个问题的答案。回想 1999 年，估计有超过 100,000 个网站使用 PHP 来升级自己的网站。今天，有超过 1,000,000 个网站在使用 PHP。

PHP 是 Web 开发中常用且广泛使用的编程语言。PHP 代表超文本处理器（Hypertext Preprocessor）。在互联网早期，大多数目标都是静态内容页面。随着互联网的发展，人们需要具有更多功能的网站，例如博客和论坛。PHP 是理想的工具，直到今天，PHP 仍然是一门非常强大且成熟的语言。它最初于 1995 年发布，已成为网站开发最受欢迎的语言之一。它运行在服务器端，极其安全。现在它已经开源，大多数机构都提供 PHP 运行包。

如果你需要一个包含博客和表单等组件的交互式网站，你可以自己学习 PHP。许多人没有空间或能力学习编程语言（例如 PHP），并选择购买网站包。然而，这些包提供的基础网站只能供少数人使用，功能有限，且亮点受限。在与它斗争之后，这位客户自己开发了网站。完成之后，他现在拥有了一个精美且具有交互元素的网站，这些元素超出了网站包能提供的任何功能。这就是 PHP 的区别！

## 第一章：设置你的服务器

既然现在你已经准备就绪，从编程的螺丝和螺母来说，我们应该从在服务器上输出一个简单的“hello world”开始。

首先，进入你安装 XAMPP 的目录（通常在 `C:\xampp`）。从那里开始，进入 `htdocs` 文件夹（通常在 `C:\xampp\htdocs`）并创建一个名为“MyFirstWebsite”的文件夹。从现在起，你就为你的网站创建了一个 URL。该文件夹将用于存放所有的网站记录（.html, .php, .css, .js 等）。打开你的内容管理器，我们现在开始吧！

![img/8e0a31fe30a159a13fdfed1340b5ed7_8_0.png](img/8e0a31fe30a159a13fdfed1340b5ed7_8_0.png)

使用 Sublime Text。如果你在使用 Notepad++ 或任何其他编辑器，也可以。它现在还不是一个主要组件，因为这只是人们可能想要使用的偏好。

我们将做的是使用基础 PHP 语言创建一个简单的 HTML 页面，并从服务器展示“hello world”。然后我们将进行以下操作：

### 上述代码：

```html
<html>
<head>
<title>My first Website</title>
</head>
<body>
<?php
echo "<p>Hello World!</p>";
?>
</body>
</html>
```

将文件保存到“MyFirstWebsite”文件夹中，并将其命名为 `index.php`。（如图顶部的地址栏所示）

既然你有了文件，我们现在应该打开 XAMPP 控制面板。如果它没有出现在桌面上，它位于你的 XAMPP 文件夹中，如下：

![img/8e0a31fe30a159a13fdfed1340b5ed7_9_0.png](img/8e0a31fe30a159a13fdfed1340b5ed7_9_0.png)

既然它已经在那里，点击服务部分的“Start”按钮运行 Apache 和 MySQL。你应该看到 PID(s) 和默认端口号。Apache 是我们的 Web 服务器名称，它将处理每一个文件。MySQL 是存储大部分数据的数据库。

打开你的浏览器，并在地址栏输入 `localhost`。你应该能看到 XAMPP 的菜单。

如果是第一次运行，它会询问你倾向于哪种语言，只需选择一个，它将引导你进入菜单。如果你看到索引是 `localhost/xampp`，这是无论你是否输入 `localhost` 都会显示的默认页面。

![img/8e0a31fe30a159a13fdfed1340b5ed7_10_0.png](img/8e0a31fe30a159a13fdfed1340b5ed7_10_0.png)

### 1.1 创建公共 HTML 页面

下一步是我们需要修改网站，并包含一个注册页面，让客户可以在那里注册，并在注册后立即进入一个登录页面。我们还应该使用以下代码调整落地页：

![img/8e0a31fe30a159a13fdfed13405b5ed7_11_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_11_0.png)

#### 上方代码：

```html
<html>
<head>
<title>My first PHP Website</title>
</head>
<body>
<?php
echo "<p>Hello World!</p>";
?>
<a href="login.php"> 点击这里登录</a>
<a href="register.php"> 点击这里注册</a>
</body>
</html>
```

现在已经显而易见了，我们刚刚包含了 2 个连接，分别用于登录和注册。我们应该先制作注册页面。如你所见，它只是一个基础结构，客户可以在其中填写凭据。对于登录页面，插入此代码：

**洞察：** 直接复制相同的代码以让操作更简单更快速。

#### login.php

```html
<html>
<head>
<title>My PHP Website</title>
</head>
<body>
<h2>登录页面</h2>
<a href="index.php">点击这里返回</a><br/><br/><br/>
<form action="checklogin.php" method="POST">
输入用户名： <input type="text" name="username" required="required" /><br>
输入密码： <input type="password" name="password" required="required" /><br>
<input type="submit" value="登录"/>
</form>
</body>
</html>
```

从根本上说，它仍然与 `register.php` 的代码相同，但所做的调整/进展是下划线部分。

尝试再次运行 `localhost/MyFirstWebsite`，你的页面应该显示如下：

#### index.php

![img/8e0a31fe30a159a13fdfed13405b5ed7_13_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_13_0.png)

#### login.php

![img/8e0a31fe30a159a13fdfed13405b5ed7_13_1.png](img/8e0a31fe30a159a13fdfed13405b5ed7_13_1.png)

#### register.php

![img/8e0a31fe30a159a13fdfed13405b5ed7_13_2.png](img/8e0a31fe30a159a13fdfed13405b5ed7_13_2.png)

### 1.2 创建数据库及其表

现在我们已经有了面向所有普通人的最重要的页面，我们继续处理数据库如何？

首先，选择 `localhost/phpmyadmin`。这将带你进入 phpmyadmin 落地页：

Localhost/phpmyadmin

![img/8e0a31fe30a159a13fdfed13405b5ed7_14_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_14_0.png)

从那里开始，点击顶部的“数据库”（Databases）选项卡，然后从中间的内容框选择 `first_db`，然后点击“创建”（make）。将“排序规则”（Collation）留如下所示：

![img/8e0a31fe30a159a13fdfed13405b5ed7_14_1.png](img/8e0a31fe30a159a13fdfed13405b5ed7_14_1.png)

你现在已经成功创建了你的第一个数据库。

从那里开始，我们来创建一个表，可以在其中注册我们的客户并展示数据如何？首先，点击左侧的 `first_db`，创建一个名为 `clients` 的具有 3 个段的表，然后点击“执行”（Go）。

![img/8e0a31fe30a159a13fdfed13405b5ed7_14_2.png](img/8e0a31fe30a159a13fdfed13405b5ed7_14_2.png)

对于表的结构，选择相应的字段然后点击“保存”（recovery）：

| 组 | 列名 | 类型 | 长度 | 空值属性 | 其他属性 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| | Id | INT | N/A | 非空 | 自动增加 |
| | Username | varchar | 50 | 非空 | |
| | Secret key | varchar | 50 | 非空 | |

如果未确定，请全部保持默认值。

![img/8e0a31fe30a159a13fdfed13405b5ed7_15_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_15_0.png)

**注意：** 你需要滚动到该页面的右侧来找到自动递增（`auto_increment`）。我只是修改了字段以适应。

接下来，再创建一个名为 `login` 的表，具有 7 个部分的表结构：

| 组 | 列名 | 类型 | 长度 | 空值属性 | 其他属性 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| | id | INT | N/A | 非空 | 自动增加 |
| | username | varchar | 50 | 非空 | |
| | date_posted | varchar | 30 | 非空 | |
| | time_posted | Time | 30 | 非空 | |
| | date_edited | varchar | 30 | 非空 | |
| | time_edited | Time | 30 | 非空 | |
| | password | varchar | 25 | 非空 | |

![img/8e0a31fe30a159a13fdfed13405b5ed7_15_1.png](img/8e0a31fe30a159a13fdfed13405b5ed7_15_1.png)

### 1.3 向数据库添加用户

既然我们有了表，我们应该进入有趣的部分，让你的注册页面可用。从 `registration.php` 包含以下代码：

register.php

![img/8e0a31fe30a159a13fdfed13405b5ed7_16_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_16_0.png)

这里是代码：

```html
<html>
<head>
<title>My first PHP Website</title>
</head>
<body>
<h2>注册页面</h2>
<a href="index.php">点击这里返回</a><br/><br/>
<form action="checklogin.php" method="POST">
输入用户名： <input type="text" name="username" required="required" /><br>
输入密码： <input type="password" name="password" required="required" /><br>
<input type="submit" value="注册"/>
</form>
</body>
</html>
```

`$_SERVER["REQUEST_METHOD"] == "POST"` - 检查是否在点击提交按钮时获取了 POST 方法。POST 方法是在 html `method="POST"` 中制作的。

`$_POST` 从表单中获取信息。对于我们的例子，是用户名和密码。

`mysql_real_escape_string()` - 将信息转换为字符串以防止 SQL 注入。

之后，进入你的 `register.php` 尝试输入数据然后点击“注册”。对于我的例子，输入了 123456。它应该显示输入。这里是示例：

![img/8e0a31fe30a159a13fdfed13405b5ed7_17_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_17_0.png)

通过部分你已经看到了通过表单获取信息的正确方法以及如何将其添加到数据库。在你的 `register.php` 上，包含补充代码：

![img/8e0a31fe30a159a13fdfed13405b5ed7_17_1.png](img/8e0a31fe30a159a13fdfed13405b5ed7_17_1.png)

以下是代码解释：

```html
<html>
<head>
<title>My first PHP Website</title>
</head>
<body>

<h2>注册页面</h2>
<a href="index.php">点击这里返回</a><br/><br/>
<form action="checklogin.php" method="POST">
输入用户名： <input type="text" name="username" required="required" /><br>
输入密码： <input type="password" name="password" required="required" /><br>
<input type="submit" value="注册"/>
</form>
</body>
</html>

<?php
if($exists > 0) {
    echo '<script>alert("用户名已被占用!");</script>'; // 提示用户
    echo '<script>window.location.assign("register.php");</script>'; // 跳转到 register.php
}
if($bool) {
    mysql_query("INSERT INTO users (username, password) VALUES ('$username', '$password')"); // 向 users 表插入值
    echo '<script>alert("注册成功!");</script>'; // 提示用户
    echo '<script>window.location.assign("register.php");</script>'; // 跳转到 register.php
}
?>
```

`mysql_connect("Server name","Server Username","Server Password")` - 用于连接我们的 XAMPP 服务器的结构。`localhost` 或 `127.0.0.1` 是服务器名称。默认用户名是 `root`，密码为空。`mysql_select_db('database name')` - 选择使用的数据库。
`then die('Message')` - 如果条件不满足，显示错误消息。
`mysql_query('sql question')` - 执行 SQL 查询。
`mysql_fetch_array('query')` - 获取表中的所有列以显示或控制数据。它被放在循环中以便查询所有列。注意，每个循环只查询一行，这就是为什么 `while` 循环至关重要。
`$row['row name']` - 当前查询部分的估值。它表示为一个数组。对于我们的例子，`$row` 是行列的变量名。

尝试你之前的输入并看看发生了什么。它应该显示你已经注册。尝试进入 phpmyadmin 查看你的 `clients` 表：

![img/8e0a31fe30a159a13fdfed13405b5ed7_19_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_19_0.png)

恭喜！现在你知道如何带有数据验证的数据添加到数据库了。

### 1.4 用户登录：认证

随后，对于登录页面，我们需要创建一个名为 `checklogin.php` 的另一个文档。由于回到我们的 `login.php`，我们的表单有一个名为 "checklogin.php" 的 action，特别是 `<form action="checklogin.php" method="POST">`。如果你在 `register.php` 上看到它，它也在 `register.php` 中，因为后端也在同一个文档中完成。

我们现在用以下语言编写 `checklogin.php` 怎么样：

#### checklogin.php

![img/8e0a31fe30a159a13fdfed13405b5ed7_20_0.png](img/8e0a31fe30a159a13fdfed13405b5ed7_20_0.png)

```php
<?php

session_start();

$username = mysql_real_escape_string($_POST['username']);

$password = mysql_real_escape_string($_POST['password']);

$bool = true;

mysql_connect("localhost", "root", "") or die (mysql_error()); // 连接服务器

mysql_select_db("first_db") or die ("无法连接到数据库"); // 连接数据库

$query = mysql_query("Select * from users WHERE username='$username'"); // 查询 users 表

$exists = mysql_num_rows($query); // 用户名是否存在

$table_users = "";

$table_password = "";

if($exists > 0) // 如果没有返回行或没有现有用户名
{
    while($row = mysql_fetch_assoc($query)) // 显示查询中的所有行
    {
        $table_users = $row['username']; // 传递第一个用户名行
        // $table_users, 依此类推直到查询结束
        $table_password = $row['password']; // 传递第一个密码行
        // $table_password, 依此类推直到查询结束
    }

    if(($username == $table_users) && ($password == $table_password)) // 检查是否存在匹配的字段
    {
        if($password == $table_password)
        {
            $_SESSION['user'] = $username; // 在会话中设置用户名。这充当全局变量
        }
    }
}
```



## PHP 登录验证与重定向逻辑

```php
header("location: home.php"); // 将用户重定向到认证后的主页
}
}
else
{
    Print '<script>alert("Incorrect Password!");</script>'; // 提示用户
    Print '<script>window.location.assign("login.php");</script>'; // 重定向到 login.php
}
else
{
    Print '<script>alert("Incorrect username!");</script>'; // 提示用户
    Print '<script>window.location.assign("login.php");</script>'; // 重定向到 login.php
}
?>
```

### 核心函数说明

- `session_start()` - 初始化会话。通常在页面顶部调用，`$_SESSION[""]` 依赖它。
- `mysql_num_rows()` - 返回整数，根据查询结果统计行数。
- `$_SESSION['name']` - 全局会话变量，用于标识客户端是否通过验证。

### 测试建议

1. 使用错误的用户名/密码测试，应返回预期提示。
2. 输入正确值，应跳转至 `home.php`（注意：若 `home.php` 不存在将报 404 错误）。

---

## 第二章：为已登录用户设置主页并注销

### 2.1 创建 `home.php`

**代码结构：**

```html
<html>
<head>
<title>我的第一个 PHP 网站</title>
</head>
<?php
session_start(); // 开启会话
if($_SESSION['user']){ // 检查用户是否登录
}
else{
    header("location: index.php"); // 未登录则重定向
}
$user = $_SESSION['user']; // 获取用户值
?>
<body>
<h2>主页</h2>
<!-- 显示用户名 -->
<a href="logout.php">点击此处注销</a><br><br>
<form action="add.php" method="POST">
向列表添加更多内容： <input type="text" name="details" /><br>
公共帖子？ <input type="checkbox" name="public[]" value="yes" /><br>
<input type="submit" value="加入列表"/>
</form>
<h2 align="center">我的列表</h2>
<table border="1" width="100%">
    <tr>
        <th>Id</th>
        <th>详情</th>
        <th>编辑</th>
        <th>删除</th>
    </tr>
    <!-- PHP 循环输出数据 -->
</table>
</body>
</html>
```

**关键点：**
- `session_start()`：必须在输出任何内容前调用。
- `header()`：用于重定向未授权用户。

### 2.2 创建 `logout.php` 并测试安全性

**测试步骤：**
1. 刷新 `home.php` 并点击注销。
2. 点击浏览器后退按钮，应无法进入 `home.php`。
3. 手动输入 `localhost/MyFirstWebsite/home.php`，同样应被重定向至登录页。

> 实现原理：在 `home.php` 顶部检查 `$_SESSION['user']`，若不存在则 `header("location: index.php")`。

---

## 2.3 向列表添加数据 (`add.php`) - 仅限登录用户

**表单提交目标：** `<form action="add.php" method="POST">`

**`add.php` 核心逻辑：**

```php
<?php
session_start();
if($_SESSION['user']){
    // 允许操作
}
else{
    header("location: index.php");
}

$details = $_POST['details'];
$time = strftime("%X");
$date = strftime("%B");
$day = strftime("%d");
$year = strftime("%Y");
// 后续插入数据库逻辑...
?>
```

---

## 3.1 编辑功能 (`edit.php`)

### URL 参数与安全校验

- 使用 `id` 作为唯一标识符（避免详情重复导致歧义）。
- 通过 `$_GET['id']` 获取参数。
- 校验逻辑：`!empty($_GET['id'])` 检查参数是否存在；`$id_exists` 变量标记记录是否存在。

**关键函数/变量：**
- `!empty()` / `empty()`：检查变量是否非空/为空。
- `$_GET['id']`：从 URL 参数获取 ID。
- `$_SESSION['id']`：将 ID 存入会话供跨页面使用。

### 代码片段示例

```php
<?php
session_start();
if($_SESSION['user']){
    // 登录校验通过
}
else{
    header("location:index.php");
}
$user = $_SESSION['user'];
?>
<body>
<h2>首页</h2>
<!-- 显示用户名 -->
<a href="logout.php">点击此处退出</a><br/><br>
<a href="home.php">返回首页</a>
<h2 align="center">当前选中</h2>
<?php
// 查询数据库
$query = mysql_query("SELECT * FROM table WHERE id = '$_GET[id]'");
if($row = mysql_fetch_array($query)){
    // 显示编辑表单
    echo '<form action="update.php" method="POST">
    输入新详细信息: <input type="text" name="details"><br>
    公开帖子? <input type="checkbox" name="public[]" value="yes"/>
    <input type="submit" value="更新列表"/>
    </form>';
}
else {
    echo "<h2 align='center'>没有可编辑的信息。</h2>";
}
?>
</body>
```

### 测试 URL 参数保护

- 访问 `edit.php?id=1` 正常显示。
- 访问 `edit.php` (无参数) 或无效 ID，显示“无可编辑信息”。

---

## 3.2 删除数据 (`delete.php`)

### 实现逻辑

1. 在 `home.php` 列表中，删除链接绑定 JS 确认框：
   ```html
   <a href='#' onclick="myFunction('$row['id']')">delete</a>
   ```
2. JS 函数 `myFunction(id)` 弹出确认，确认后跳转 `delete.php?id=<id>`。
3. `delete.php` 接收 `$_GET['id']`，执行 `DELETE` SQL 语句。

**`home.php` 关键 JS 代码：**

```html
<script>
function myFunction(id) {
    var r = confirm("你确定要删除这条记录吗？");
    if(r == true) {
        window.location.assign("delete.php?id=" + id);
    }
}
</script>
```

**`delete.php` 核心：**
```php
<?php
session_start();
if($_SESSION['user']){
    $id = $_GET['id'];
    mysql_query("DELETE FROM table WHERE id='$id'");
    header("location: home.php");
}
else{
    header("location: index.php");
}
?>
```

---

## 第四章：Web 开发基础架构

### 4.1 HTTP 与互联网

- **HTTP (Hypertext Transfer Protocol)**：定义 Web 资源交换规范，基于**请求-响应**模型。
- **核心组件**：
  - **User Agent (客户端)**：通常指浏览器。
  - **Origin Server (源服务器)**：存储资源（HTML、图片等）。
  - **Proxies (代理)**：中间节点。
- **传输层**：HTTP 构建于 **TCP** 之上，TCP 构建于 **IP** 之上，统称 **TCP/IP**。
- **连接流程**：客户端在端口 80 建立 TCP 连接 -> 发送请求 -> 服务器响应状态行 (如 `HTTP/1.1 200 OK`) 及内容。

### 4.2 PHP 与 MySQL 在 Web 开发中的地位

| 特性 | 说明 |
| :--- | :--- |
| **PHP 定位** | 服务端脚本语言，嵌入 HTML 生成动态内容。解释执行，非编译型。 |
| **MySQL 定位** | 关系型数据库，负责持久化存储。PHP 通过扩展原生支持。 |
| **协作优势** | 设计之初相互适配，开源免费，社区活跃，跨平台 (Win/Mac/Linux)，性能高效。 |
| **开源价值** | 无授权费用，源码可审计/修改，社区支持强大 (如 php.net)。 |

### 4.3 PHP 程序的三大核心组件

1.  **Web Server (Apache/Nginx)**：处理 HTTP 请求，分发静态资源或转发动态请求给 PHP 解释器。
2.  **Server-side Language (PHP)**：执行业务逻辑，操作数据库，生成 HTML 输出。
3.  **Database (MySQL)**：数据持久化存储与检索。

> **动态网页渲染流程**：浏览器请求 -> Apache 接收 -> 调用 PHP 解析脚本 -> PHP 查询 MySQL -> 组装 HTML/CSS/JS -> 返回响应。

### PHP 简史

- 1998 年 PHP 3.0 发布，确立 Web 开发工具地位，与 ASP、JSP 竞争。
- 核心优势：**简单易学** 与 **功能强大** 的结合；内置丰富 Web 功能，避免重复造轮子。



PHP 无处不在，并且与所有主流操作系统都非常兼容。它也很容易学习，是 Web 编程初者的完美工具。此外，你还可以利用一个让 Web 开发对所有人都更简单的社区。

PHP 的创建者增加了一个基础，允许经验丰富的 C 开发者扩展 PHP 的功能。因此，PHP 现在包含了 XML、XSL 和微软的组件对象模型 (COM) 等领先创新。

### Apache

Apache 是一种 Web 服务器，它可以将程序请求转换为相应的网页，并知道如何处理 PHP 代码。PHP 仅仅是一种编程语言，如果没有像 Apache 这样的 Web 服务器支持，Web 客户端无法访问你包含 PHP 的页面。Apache 并不是唯一的 Web 服务器。另一个著名的 Web 服务器是微软的 Internet 服务 (IIS)，它随 Windows 2000 及后续每个版本提供。Apache 具有几个独特优势：免费、提供完整的源代码以及使用不受限制的许可。Apache 2.0 是你可能会使用的当前版本，尽管 1.3 仍在被使用。

### MySQL

结构化查询语言 (SQL) 是用于从关系型数据库管理框架创建、检索、修改和删除信息最著名的语言。关系数据库遵循关系模型并提及数据库的信息以及模式（schema）。模式是数据库组织信息的一种结构。经常使用“关系型数据库管理系统”这一术语实际上是指代用于创建关系型数据库的程序，例如 Oracle 或 Microsoft SQL Server。关系型数据库是表格的集合，但不同的项目通常被认为是数据库的一部分，因为它们有助于组织和结构化信息，同时强制数据库符合一组预先定义的要求。

### MySQL

MySQL 是一个免费但仍包含全功能的关系型数据库。MySQL 创建于 20 世纪 90 年代，以满足 PC 对大规模数据管理日益增长的需求。MySQL 的第一批核心设计者试图利用 MySQL（一个非常小且基础的数据库）来解决他们对数据库的需求。事实证明，MySQL 无法处理他们需要的大量问题，因此他们制作了一个更健壮的数据库，并将其演变成了 MySQL。

MySQL 支持几个独特的数据库引擎。数据库引擎决定了 MySQL 如何处理信息的实际存储和查询。因此，每个存储引擎都有其特定的能力配置和优势。随着时间的推移，可用的数据库引擎变得越来越先进、越来越快速。

MySQL 的最新生产发行版本是 5.x 版本。MySQL 5.0 提供的执行性能类似于许多昂贵的企业数据库，例如 Oracle、Informix、DB2 (IBM) 和 SQL Server (Microsoft)。开发者通过利用许多开源设计者的才华以及社区测试，实现了这种水平的性能执行。对于一般的 Web 驱动数据库任务，默认的 MyISAM 数据库引擎运行得非常好。不必担心数据库的最新和最主要的功能，因为你可能需要的大部分已经集成在 MySQL 中很久了。

# 兼容性

Web 程序（例如 Safari、Firefox、Netscape 和 Internet Explorer）是为了处理 HTML 而设计的，因此 Web 服务器运行在何种操作系统上并不重要。Apache、PHP 和 MySQL 支持广泛的操作系统 (OS)，因此你在服务器或客户端上都不受限于特定的操作系统。虽然你不需要过多担心软件兼容性，但文件格式的极其多样化以及汇聚的各种语言确实需要一些时间来适应。

## 4.4 集成多种信息源

在 Web 早期，生活很简单。文件包含 HTML 以及二进制文件（例如图片）。随后创建了一些进展来改进网页的外观。例如，层级样式表（CSS）将演示数据从你的 HTML 中提取出来并放到同一个位置，这样你就可以同时对整系列页面进行格式更改；你不需要物理地逐个更改一个 HTML 页面的标记。

你可能同时拥有引用 CSS、PHP 模板和 MySQL 数据库的 HTML 文档数据。PHP 模板使得在包含由数据库查询填充的字段时更改页面 HTML 变得简单。

为了大致了解你的代码样子，最好查看包含 PHP 代码的示例，这些代码从 MySQL 数据库创建 HTML，而该 HTML 本身引用了一个 CSS 样式表。

结果是，虽然你在混合中添加了另一个内容，但你让 HTML 标记更易读，且 PHP 代码没有被琐碎的 HTML 混杂。不擅长 PHP 的 Web 设计师可以调整页面外观而无需担心破坏 PHP 代码。

这里指示的最后一种数据 CSS 同样源于分离样式的愿望，例如将内容和颜色与重要内容分离。

层级样式表（CSS）补充了 HTML，让 Web 设计师和客户端对网页的显示方式有更多的控制。设计师和客户端可以创建样式表，描述不同组件（例如头部和链接）在网站上的显示方式。“层级”（cascading）一词意味着许多不同层级的样式表可以连接到同一个网页上，定义从一个级别传递到下一个级别。要应用 CSS 代码，将指示的示例代码放在你的 HTML 记录的头部（header）中。

```html
<html>
<head>
<title>CSS Example</title>
<style type="text/css">
h4, b {color: #80D92F; font-family: arial; }
p { margin-indent: 2cm; background: yellow; font-family: courier; }
</style>
</head>
<body>
```

### 学习如何在你的网站上使用 CSS！

#### 它很酷，很惊艳，甚至还能为你节省时间！

<p>这个 b 是不 <b>很棒</b> 吗？</p>

```html
</body>
</html>
```

在 CSS 中，你可以通过命名来指定颜色，就像我们在这里对背景命名做的那样，“background: yellow”，或者你可以使用数字颜色代码来指定，就像我们在这里做的一样，“color #80D92F”。以 style 开头的代码就是 CSS 代码。

尽管我们在示例中将 CSS 包含文件中，但它可能源自另一个文档，并在那里作为 `user_admin.css` 被引用。

总而言之，这是一个风格问题。我们在 Web 目标中使用大写字母以便更好地看到 HTML，并在每行标记之间加上换行符。标签通常发生在开始-结束情况中。

这些成对的结构为：`<tag>这个不很棒吗？</tag>`

第一个 `<tag>` 显示标签的开始，最后一个 `<tag>` 显示结束。这一对完整的标签被称为一个`元素`（element）。元素内部的任何内容都与其关联的元素属性。在先前的示例中，文本“Learn how to utilize CSS on your web sites!”包含在一个 h3 组件中：`<h3>Learn how to utilize CSS on your web sites!</h3>`

让你的标签整齐地结束，以产生具有清晰边界的元素也是一种良好的做法（而且 XHTML 也是这样要求的）。当你到达一个元素的末尾时，始终使用结束标签，避免出现覆盖的标签对。

（而不是 `<b>粗体<i>斜体</i></b>` 这种形式的，你应该这样关闭代码：`</b></i>` 是错误的，使用 `</i></b>`。）归根结底，你应该打开并关闭项。根据这些原则，如果你打开了粗体和斜体，你应该先关闭斜体再关闭粗体。

## 4.5 从 Web 页面请求数据

了解这些部分如何相互结合可能是困难的。当服务器识别 PHP 代码时，它会将页面的处理交给 PHP 解释器。服务器处理 PHP 记录并将 HTML 文档发送服务器。如果结果包含外部 CSS 样式表，程序会对该样式表发出另一个请求。

在服务器上处理 PHP 被称为服务器端处理。图表示你的 PC 与 Web 服务器之间的关联。

这是服务器端处理的过程：

- 你在浏览器地址栏输入 Web 页面地址。
- 你的浏览器分离该地址并将页面名称发送给 Web 服务器。例如，`http://www.phone.com/directory.html` 会向 `www.phone.com` 请求页面。
- Web 服务器上的一个程序（Web 服务器进程）获取 `directory.html` 的请求并搜索该特定文件。
- Web 服务器从其硬盘读取 `directory.html`。
- Web 服务器将 `directory.html` 的内容返回给你的浏览器。
- 你的 Web 程序利用从 Web 服务器返回的 HTML 标记来构建页面解释。

名为 `directory.html` 的 HTML 文件被称为静态 Web 页面，因为请求 `directory.html` 页面的人都会得到相同的页面。

为了让 Web 服务器更改返回的页面，PHP 和 MySQL 被加入到混合中。

2. 你的程序分离了该地址并将页面名称发送给主机。例如，`http://www.phone.com/login.php` 向 `www.phone.com` 请求了 `login.php` 页面。
3. 主机上的 Web 服务器进程收到了对 `login.php` 的请求。
4. Web 服务器从主机的硬盘上读取 `login.php` 记录。
5. Web 服务器识别出该 PHP 文件不仅仅是一个纯 HTML 文档，因此它调用了另一个程序——PHP 解释器——来处理该文档。
6. PHP 解释器执行它从 Web 服务器进程获取的内容中找到 PHP 代码。这些代码中包含了对 MySQL 数据库的调用。
7. PHP 请求 MySQL 数据库进程执行数据库调用。
8. MySQL 数据库进程将带有数据库信息的 PHP 代码结果传回，并将结果返回给 Web 服务器。
9. PHP 翻译器结合数据库信息完成 PHP 代码的执行，并将结果返回给 Web 服务器。
10. Web 服务器将结果作为 HTML 内容返回给你的浏览器。
11. 你的网页浏览器利用返回的 HTML 内容在你的屏幕上组装网页。

这看起来步骤非常多，但每当请求带有 PHP 代码的网页时，大部分处理过程都会自然发生。事实上，对于单个网页，此过程可能会发生几次，因为一个网页可能包含大量的图像文件以及 CSS 定义，这些内容都应该从 Web 服务器中获取。

在创建动态网页时，你将与各种和服务器组件打交道，这些组件对于拥有吸引人、易于维护、简单易导航且实行的网站至关重要。

在下一章中，我们将向你演示安装步骤，并介绍实现此工作所需的关键组件，即 PHP。

# 第 5 章：探索 PHP

在引入 PHP、MySQL 和 Apache 之后，你已经准备好开始编写代码了。与许多语言不同，PHP 不需要编译器和调试器等复杂设备。实际上，你会发现你可以直接将 PHP 输入到你当前的 HTML 文档中，只需要进行几处修改，就可以运行了。

在本章中，我们将首先向你演示 PHP 如何处理基础文本，然后进入核心的决策处理。你真正可以包含的内容有很多，包括根据当前客户端浏览器画图，以及如果客户端使用的操作系统让你的网站看起来很糟糕，则打印出警告信息。通过 PHP，这些以及更多操作都是可能的，它让这些陷阱变得易于处理。

## 5.1 PHP 与 HTML 文本

使用 PHP 输出内容非常简单；实际上，处理内容是 PHP 的强项。我们将从详细介绍 PHP 在何处被处理开始，然后查看用于输出文本的核心函数，并直接进入在特定条件有效的情况下打印文本。

### 文本输出

在学习 PHP 的过程中，你需要能够简单且规律地显示消息的能力。PHP 给了你实现这一机会，但在编写代码时你必须使用合法的 PHP 语法。或者让 HTML 专门为浏览器产生 PHP 代码。一切看起来都像是内容和代码的混合。这无疑给你网站的客户带来困惑！你可以使用任何你喜欢的文本编辑器来编写 PHP 代码，包括记事本或 Dev-PHP (http://sourceforge.net/ventures/devphp/)。

我们的示例展示了对比 HTML 标记和 PHP 代码看起来像什么样，以及你可以做什么来开始注意到它们之间的差异。

## 5.1 PHP 与 HTML 文本

尽管大多数代码看起来非常基础，但就其本身是无法运行的，因此存在一些问题。目前没有真正的方法可以判断文件中哪些部分是标准 HTML，哪些部分是 PHP。因此，`echo()` 的顺序必须以不同的方式处理。修复方法是将你的 PHP 代码封装在 `<?php ?>` 标签中。

当你开始编写 PHP 代码时，你将处理包含 PHP 和 HTML 代码的简单文本文件。HTML 是一种基础标记语言，用于指定页面在浏览器中的外观；然而，它仅仅是文本。服务器在将 HTML 文档发送到客户端浏览器之前不需要进行转换。与 HTML 代码相反，PHP 代码在结果页面发送到浏览器之前必须经过解析。

为了分离 PHP 代码以告知 Web 服务器应该处理什么，PHP 代码被放在 `<?php` 和 `?>` 标签之间。

## 5.2 模块

要在 PHP 中创建程序，你需要了解一些元素。变量可以存储数据，我们使用美元符号 (`$`) 来标识它们。变量可以是字符串、数字等。

### 变量

- 变量可以由字母、数字和下划线组成；例如 a-z, A-Z, 0-9 和 `_`。
- 美元符号后的第一个字符必须是字母或下划线。
- PHP 中的变量对大小写敏感。这意味着 `$variable_name` 和 `$Variable_Name` 是不同的。
- 使用等号 (`=`) 为变量赋值。
- 始终以分号 (`;`) 结束赋值。

### 读取变量

若要获取已赋值变量的值，只需指定美元符号 (`$`) 后跟变量名，并在代码中像往常一样使用它。程序结束时你不需要移除变量，因为 PHP 会自然地清理它们。

### 变量类型

变量都存储特定类型的信息。PHP 会自然选择数据类型。这些信息类型包括字符串、数字以及如数组之类的复杂组件。我们稍后会讨论数组。需要知道的是，除非你有动力去关心数据类型，否则 PHP 会处理所有点。在需要特定类型信息的情况下（例如数值除法运算），PHP 会尝试自然地转换数据类型。如果你有一个包含单个数字“2”的字符串，它将被转换为整数 2。

### 变量作用域

PHP 帮助保持你的代码整洁，因为它确保了即使你使用了他人的代码（你很可能会这样做），你代码中的变量名也不会与先先定义的变量名冲突。例如，如果你使用一个名为 `$name` 的取值为 Bill 的变量，而你使用了另一个人的代码，其中也包含名为 `$name` 的变量，那么你的值可能会被覆盖。你代码中 `$name` 的值 Bill 将被 Hello 替换，你的代码将输出 Hello 而不是 Hello Bill，这将是一个严重的问题。

为了防止这种情况发生，PHP 将代码划分为函数。为了将你代码中的变量与函数中的变量隔离开，PHP 在每个函数内部提供了独立的变量存储空间。这种不同的存储区域意味着作用域，即变量值可以被访问的地方，是该值的就近存储。

### 全局变量

全局变量允许你跨越不同功能之间的限制来获取变量的值。全局声明表示你需要该变量在所有被视为全局的地方都是相同的。

全局变量应尽量少使用，因为这很容易在不清楚结果的情况下无意中调整了变量。这类错误可能极难发现。此外，当我们详细检查函数时，你会发现，调用函数时可以向它们传递值，并在执行完成后获取返回的值。你不需要使用全局变量。

然而，万一你需要在特定函数中使用变量，且不想在每次函数结束时丢失该值，那么你可能倾向于不使用全局变量，而是使用静态变量。

#### 静态变量

静态变量使得变量在函数结束时不会被销毁。每当你调用该函数时，都可以再次使用该静态变量的值，它的值将与最后一次作为函数的一部分使用时相同。考虑这一点简单方法是将该变量视为仅对该函数开放的全局变量。`$age` 的估计值在每次调用函数时都会保持不变，直到程序结束。该值是根据赋值的。通过这种方式，我们已经讨论了两种变量，但还有一种需要检查：全局变量。

#### 超全局变量

超全局变量是 PHP 使用特殊变量来提供脚本环境的信息。这些变量不需要声明。它们通常处处可用，并提供脚本的数据，例如用户输入。

从 PHP 4.0 开始，超全局变量被称为数组。数组是值的集合，我们将在后面的章节中讨论。更多定义的超全局变量（如以 `$HTTP_*` 开头的）仍然存在，但绝对不建议使用它们。

# 第 6 章：PHP 选择

在上一部分，我们开始学习 PHP 编程和基础知识。现在是增加对 PHP 的熟悉度和知识。我们将从表达式和语句开始。

## 6.1 表达式

编程中有几个需要理解的构建块：语句、表达式和运算符。语句是执行任务的代码。语句由表达式和运算符组成。表达式是评估值的代码。值可以是数字、字符串或布尔值。

运算符是某种作用于表达式的代码组件。例如，递减符号（`--`）可以用于递减其之前的表达式的值。例如：

```php
$account_balance = $credits - $debits;
```

关于表达式最重要的点就是使用运算符将其合并为复合表达式和声明。通过这种方式，我们将查看将表达式转换为更复杂的表达式和语句的运算符。

表达式简单的类型是字面量或变量。字面量评估自身。字面量的例子包括数字、字符串和常量。变量评估分配它的值。

尽管字面量或变量可能是合法的表达式，但它们本身什么都不做。你可以通过运算符将表达式连接起来来实现操作。运算符通过在基本表达式之间建立连接将表达式转换为更复杂的表达式。例如，如果你需要连接两个数值属性，你会组合成 `3 + 4`。数字 3 和 4 分都是基本表达式。包括 `3 + 4` 在内也是合法的表达式，其值在此为 7。加号（`+`）是一个运算符。操作数是运算符作用的对象；例如，操作数可以是你的变量，运算符处理该操作数。

不同的运算符有不同的类型和操作数数量。运算符还可以被重载，这意味着它们在不同的上下文中执行不同的操作。

通过运算符关联的两个或多个表达式被称为表达式。你是正确的，运算符创建复杂的表达式。你拥有的子表达式和运算符越多，表达式就越复杂。无论赋值了什么值，它仍然是一个表达式。

当表达式和运算符组合以产生真正执行操作的代码时，你就有一个语句。

运算符位于 http://www.php.net/manual/en/language.operators.php。我们将讨论一些运算符，以便你尽可能快地上手 PHP。目前我们将简要介绍。每个运算符除了主要功能外，还有四个基本属性：

- 运算符结合性
- 操作数数量
- 优先级顺序
- 操作数类型

关于表达式，真的没有更多需要了，除了如何使用运算符将其合并为复合表达式和语句。接下来，我们将讨论用于将表达式转换为更复杂的表达式和语句的运算符。

## 6.2 运算符概念

PHP 有许多种的运算符，包括：

- 算术运算符
- 数组运算符
- 赋值运算符



- 位运算符
- 比较运算符
- 执行运算符
- 增/减运算符
- 逻辑运算符
- 字符串运算符

运算符位于 `http://www.php.net/manual/en/language.operators.php`。我们将讨论一些运算符，以便你尽可能快地上手 PHP。目前我们将简要介绍。每个运算符除了主要功能外，还有四个基本属性：

- 运算符结合性
- 操作数数量
- 优先级顺序
- 操作数类型

最简单的入门方法是从操作数开始。

## 1. 操作数数量

不同的运算符接受不同数量的操作数。许多运算符用于将两个表达式连接为一个复杂的单一表达式；这些被称为二元运算符。二元运算符包括乘、减、加、除。

某些运算符接受一个操作数；这些被称为一元运算符。考虑负运算符（`-`），它将数值乘以 -1。在第 3 章描述的预增、预递减运算符也是一元运算符。

三元运算符接受三个操作数。`if` 语句的简写（我们稍后在检查条件时会讨论）接受三个操作数。

## 2. 操作数类型

你应该意识到运算符旨在工作的操作数类型，因为运算符预期其操作数是特定的数据类型。

PHP 尝试在这些情况下通过自动转换为运算符预期的数据类型来简化你的生活。然而，在某些情况下，自动转换是不可能的。

- `(float)`, `(double)`, `(real)`：转换为 float，即可能包含小数部分的数字。
- `(string)`：转换为字符串。
- `(array)`：转换为数组。
- `(object)`：转换为对象。

要使用类型转换，请将其放在要转换的变量之前，如示例 6.2 所示，变量 `$test_string` 具有字符串 1234。

### 示例 6.2. 转换变量

```php
$test = 1234;
$test_string = (string)$test;
```

请记住，在特定类型之间进行转换时，发生什么并不显而易见。如果你在控制变量类型时不加留心，可能会反复遇到困难。

某些二元运算符（例如赋值运算符）对左操作数有进一步的限制。由于赋值运算符是在为左侧的操作数分配值，它必须是一个可以接收值的类型，例如变量。

### 示例 6.3. 左值表达式

```php
3 = $locations; // awful - 无法将值分配给精确的 3
$a + $b = $c; // awful - 左侧表达式不是一个变量
$c = $a + $b; // OK
$stores = "Becker." . "Furniture"; // OK
```

有一种较简单的方法可以记住这一点。赋值操作中的左侧表达式被称为左值（L-value）。PHP 中的左值是变量、数组组件和对象属性。

## 优先级

运算符的优先级决定了表达式中哪个运算符先被处理。例如，乘法和除法在加法和减法之前处理。你可以在 `http://www.zend.com/manual/language.operators.php#language.operators.pr` 查看一个简化的表格。

如果运算符的优先级相同，按照它们在表达式中出现的顺序进行处理。例如，乘法和除法在表达式中出现的顺序就是它们处理的顺序，因为它们的优先级相同。相同优先级的运算符可以在任何请求中出现而不影响结果。

另一方面，大多数表达式没有多个一个相同优先级的运算符，而且它们处理的顺序不会改变结果。如示例 6.4 所示，在加减连续的一组数字时，先加法还是后减法没有区别——结果都是 1。

PHP 有几个优先级级别，多到如果不查阅参考资料很难记忆。表 4-2 是按优先级从高到低排序的 PHP 运算符列表。相同级别的运算符优先级完全相同。

### 示例 6.4. 优先级

```php
2 + 4 - 5 == 1;
4 - 5 + 2 == 1;
4 * 5 / 2 == 10;
5 / 2 * 4 == 10;
2 + 4 - 5 == 1;
4 - 5 + 2 == 1;
```

当使用不同优先级级别运算符的表达式时，顺序可能会改变表达式的值。你可以利用括号 `(` 和 `)` 来覆盖优先级级别，或者为了让表达式更易读。

图 6.5 展示了如何更改默认优先级。

### 图 6.5. 使用括号更改默认优先级

```php
echo 2 * 3 + 4 + 1;
```

```php
echo 2 * (3 + 4 + 1);
```

结果是：

11

16

在第二个表达式中，由于括号覆盖了默认优先级，乘法最后执行。

PHP 有几个优先级级别，多到如果不查阅参考资料很难记录。

## 结合性

所有运算符按照特定的方向处理其运算符。这种方向被称为结合性（associativity），它取决于运算符的类型。大多数运算符从左到右处理，这被称为左结合。例如，在表达式 `3 + 5 - 2` 中，先处理 3 和 5，然后从结果中减去 2，得到 8。虽然左结合意味着表达式从左到右评估，而右结合则意味着相反。

由于赋值运算符具有右结合性，它是例外之一，因为右结合性并不常见。表达式 `a = $b = $c` 的形成是因为 `$b` 被赋值为 `$c`，然后 `$a` 被赋值为 `$b`。这为大多数变量分配了相同的值。如果赋值运算符是右结合的，变量可能没有值。

如果你认为这不可理解，请不要担心。这些原则在你无法理清指令时才会发挥作用。请记住，你应该始终在表达式中使用括号来使你的真实含义更清晰。这既有助于 PHP，也有助于其他想要阅读你代码的人。

如果你不小心使用了 `&` 而不是 `&&` 或 `|` 而不是 `||`，你将误解运算符。`&` 和 `|` 一次只查看二位信息。

PHP 将把你的操作数转换为二进制并应用运算符。

## 关系运算符

在第 3 章中我们查看了赋值和数学运算符。关系运算符提供了查看两个操作数并根据检查返回 TRUE 或 FALSE 的能力。评估为 TRUE 或 FALSE 的表达式被称为布尔表达式，我们在上一个节中讨论过。这些检查包含了对相等、小于或大于的测试。这些比较运算符允许你决定何时执行某事。

### 等于

相等运算符双等号 (`==`) 被经常使用。使用单等号 `=` 是程序中的典型错误。

如果操作数相等，则返回 TRUE；否则返回 FALSE。

你经常可能需要验证两个事物是否不同。不等运算符（等号前的感叹号 `!`）检查相等的反面。

- `"1" != "A"` / 有效
- `"1" != "1"` / 虚假

### 比较运算符

你可能需要检查的不仅仅是相等。比较运算符测试两个值之间的关系。你可能在中学数学中接触过这些。它们包含了小于 (`<`)、小于等于 (`<=`)、大于 (`>`) 和大于等于 (`>=`)。

例如，`3 < 4` 是 TRUE，而 `3 < 3` 是 FALSE，且 `3 <= 3` 是 TRUE。

### 逻辑运算符

逻辑运算符与逻辑运算符的布尔结果配合，以构建更多的逻辑表达式；有四个逻辑运算符也是布尔运算符。

要测试两个操作数是否都为真，使用 AND 运算符，也写为双 ampersand (`&&`)。双 ampersand 和 AND 都是逻辑运算符；主要区别是双 ampersand 在 AND 运算符之前被评估。如果两个操作数都是 TRUE，则返回 TRUE；通常情况下，返回 FALSE。

要测试是否其中一个操作数为 TRUE，使用 OR 运算符，它也被写为双竖线或管道符 (`||`)。如果两个操作数中的一个或都为 TRUE，则返回 TRUE。

要测试是否仅有一个操作数为 TRUE，请利用 XOR（异或）。当仅有一个操作数为 TRUE 时，XOR 返回 TRUE。如果两个操作数都是 TRUE，它返回 FALSE。

要使布尔值无效，使用 NOT 运算符，写为感叹号 (`!`)。如果操作值为 FALSE，它返回 TRUE。如果操作值为 TRUE，它返回 FALSE。

## 条件语句

条件语句与变量一样，是我们构建 PHP 开发体系的基石。

它们会根据代码中设定的标准改变脚本的执行流程。PHP 中有三种基本的条件语句：

- `if`
- `? :` (`if` 语句的简写)
- `switch`

当你有许多任务需要处理，并且需要根据变量的内容采取不同的活动时，`switch` 语句非常有帮助。本节将在稍后部分将详细阐述 `switch` 语句。

### if 语句

`if` 语句提供了在提供的条件为 TRUE（真）时执行某段代码的能力；通常情况下，该代码块不会执行。条件可以是任何表达式，包括对非零、等值、空、变量以及函数返回属性的测试。

无论如何，你编写的每一个条件语句都包含一个限制子。如果条件为 TRUE（真），则大括号 `{}` 中的代码块将被执行。如果不是，PHP 将忽略它并移动到第二个条件，继续遍历所有组合，直到 PHP 遇到 `else`。此时，只有当 IF 条件结果为 FALSE（假）时，才会执行该代码块；否则，如果块中只有一行代码要执行，则不需要大括号。同样不需要 `else` 解释。

`else` 块必须可靠地放在最后，并被视为默认活动处理。这类似于分号 (`;`)。

普通的真条件有：

- `$var`，如果 `$var` 具有除空集 (0)、空字符串或 NULL 以外的属性
- `isset($var)`，如果 `$var` 具有除 NULL 以外的属性，包括空集或空字符串
- TRUE 或任何变体

我们还没有讨论过第二一点。`isset()` 是一个检查变量是否已设置的函数。已设置的变量具有 NULL 以外的值。

`if` 语句的语法如下：

```php
if (conditional expression) {
    piece of code;
}
```

如果条件块中的 `if` 表达式评估为 TRUE（真），则执行紧随其后的代码块。在这种情况下，如果变量 `$username` 被设置为 `'Administrator'`，则会打印欢迎消息。如果不是，则什么都不会发生。

```php
if ($username == "Administrator") {
    echo('Welcome to the administrator page.');
}
```

如果你只需要执行单独语句，则不需要大括号，但习惯性使用它们是一个良好的做法，因为它可以使代码更易读且更难被误改。

### else 语句

可选的 `else` 语句在条件返回为 FALSE（假）时提供一段执行的默认代码。在没有 `if` 语句的情况下无法 `else`，因为它本身不接受条件。因此，`else` 和 `if` 在你的代码中始终成对出现。

当你使用属性开始你的代码段时，记得完成来自 `if` 条件的代码块结束。和 `if` 块一样，`else` 块也应该使用大括号来开始和结束代码。

### elseif 语句

上述大部分内容都非常出色，但需要同时测试几个条件除外。

要实现这一点，你可以利用 `elseif` 语句。它会考虑测试扩展条件直到发现其中一个为真或遇到 `else` 块。每个 `else` 都有自己的障碍，专门紧跟在 `elseif` 条件之后。`elseif` 必须位于 `if` 语句之后，以及如果存在的 `else` 语句之前。

```php
if ($username == "Admin") {
    echo('Welcome to the administrator page.');
} else if ($username == "Guest") {
    echo('Please investigate around.');
} else {
    echo("Welcome back, $username.");
}
```

在这里，你可以检查两个条件，并根据 `$username` 的属性采取不同的活动。此时，你还有另一种选择，如果 `$username` 不是前两个之一，则执行其他操作。

下一个构造结构建立在 `if/else` 语句的概念之上，但它允许你有效地检查表达式结果的多个属性，而无需为每个值都编写一个不同的 `if/else`。

### ? 运算符

`?` 运算符是一个三元运算符，这意味着它接受三个操作数。它的预期行为像语句一样，但它从两个表达式中的一个返回一个值。条件表达式决定了表达式的值。使用冒号 (`:`) 来分隔表达式，如下所示：

```php
{expression} ? return_when_expression_true : return_when_expression_false;
```

案例 4.8. 利用 `?` 运算符生成消息

```php
<?php
$logged_in = TRUE;
$user = "Administrator";
$banner = ($logged_in == TRUE) ? "Welcome back, $user!" : "Please login.";
echo "$banner";
?>
```

上述示例 4.8 产生：

Welcome back, Admin!

这对于检查错误非常有帮助。然而，我们应该看看一种语句，它允许你将表达式与可能值的列表进行对比，以选择执行代码。

### switch 语句

`switch` 语句将表达式与多个值进行比较。通常会有一个像变量这样的表达式，你需要为变量中存储的每个值执行不同的代码。例如，你可能有一个名为 `$action` 的变量，它可能具有 `adds`、`modify` 和 `delete` 的值。`switch` 语句使得根据这些值中的每一个来描述要执行的代码块变得简单。为了展示使用 `if` 语句和 `switch` 语句测试变量的几个属性的区别，我们将向你展示 `if` 语句的代码（见图 6.9）和 `switch` 语句的示例（图 6.10）。

图 6.9. 利用 `if` 测试各种属性

```php
if ($action == "Include") {
    echo "Perform activities for including.";
    echo "The greatest number of statements as you like can be in every square.";
} else if ($action == "MODIFY") {
    echo "Perform activities for modifying.";
} else if ($action == "Erase") {
    echo "Perform activities for erasing.";
}
```

案例 6.10. 利用 `switch` 测试各种属性

```php
switch ($action) {
    case "Include":
        echo "Perform activities for including.";
        echo "The greatest number of statements as you like can be in every square.";
        break;
    case "MODIFY":
        echo "Perform activities for modifying.";
        break;
    case "Erase":
        echo "Perform activities for erasing.";
        break;
}
```

`switch` 语句通过获取 `switch` 关键字后的值并按照排列顺序与 `case` 进行比较来符合预期。如果没有匹配，则不执行代码。当一个匹配时，则执行代码。随后的 `case` 继续执行，直到 `switch` 语句结束或遇到 `break` 关键字。这对于具有顺序步骤的过程非常有帮助。如果客户已经完成了几个步骤，他可以从离开的地方继续。

`switch` 语句后的表达式必须是一个简单类型，例如整数、字符串或数字。如果引用数组中的特定元素作为简单类型，则可以使用数组。

有多种方法引导 PHP 不执行匹配项之外的其他情况。

## 6.3 跳出

如果你只需要执行匹配块中的代码，请在该块的末尾放置 `break` 关键字。当 PHP 跳过 `break` 关键字时，处理将跳转到 `switch` 语句之后的行。案例 6.11 概述了没有 `break` 语句时的处理工作方式。

案例 6.11. 没有 `break` 关键字时的情况

```php
$action = "ASSEMBLE ORDER";
switch ($action) {
    case "ASSE ORDER":
        echo "Perform activities for order assembly.<br/>";
    case "PACKAGE":
        echo "Perform activities for packing.<br/>";
    case "SHIP":
        echo "Perform activities for shipping.<br/>";
}
```

如果 `$action` 的值是 “ASSEMBLE ORDER”，结果是：

Perform activities for order assembly.

Perform activities for packing.

Perform activities for shipping.

另一方面，如果客户已经装配了订单，“PACKAGE”的估计产生这些：

Perform activities for packaging.

Perform activities for shipping.

### 默认值

`switch` 语句同样提供了一种在没有任何替代情况都不匹配时执行某些操作的方法，这与 `if`、`elseif` 或 `else` 块中的 `else` 语句相同。

使用 `default` 语句作为 `switch` 的最后一个 `case` 语句（参见示例

示例 4-12. 使用 `default:` 语句产生错误的 `switch` 语句

```php
switch ($action) {
    case "ADD":
        echo "Perform activities for adding.";
        break;
    case "MODIFY":
        echo "Perform activities for modifying.";
        break;
    case "DELETE":
        echo "Perform activities for deleting.";
        break;
    default:
        echo "Error: Action must be either ADD, MODIFY, or DELETE.";
}
```

`switch` 语句还增强了替代语法，在该语法中，`switch` 和 `endswitch` 关键字用于标记 `switch` 的开始和结束，而不是使用大括号 `{}`，如示例 6.13 所示。



# 示例 6.13. 利用 `endswitch` 结束 switch

定义 `switch ($action)`:

```php
case "ADD":
    echo "Perform actions for adding.";
    break;
case "MODIFY":
    echo "Perform actions for modifying.";
    break;
case "DELETE":
    echo "Perform actions for deleting.";
    break;
default:
    echo "Error: Action must be either ADD, MODIFY, or DELETE.";
endswitch;
```

你已经发现，可以根据你的程序根据被称为“表达式”的条件来执行不同的代码。`switch` 语句为将表达式的值与各种可能的值进行匹配提供了一种合适的格式。

## 6.4 循环

由于你已经根据检查改变了 PHP 程序的执行流，你需要意识到需要反复执行赋值，直到检查结果为 FALSE（假），这需要使用循环（LOOPING）。代码循环每执行一次，就称为一次 *iteration*（迭代/循环）。这对于某些基础任务非常有价值，例如：通过返回的列长期地显示查询结果。PHP 提供了 `while`、`for` 和 `do ... while` 结构来执行循环。

每个循环结构都需要两个基础数据部分。首先，停止循环的条件描述方式与 `if` 语句中的比较一样简单。其次，要执行的代码同样被指定在单行内或大括号内。一种逻辑错误是将那些依赖于代码的执行以导致循环停止的代码排除在循环之外，从而导致死循环。

你已经发现，可以根据条件让项目执行不同的代码。`switch` 语句为将表达式的评估与各种可能的属性进行匹配提供了一个有利的安排。

只要表达式评估为 TRUE（真），代码就会执行。为了避免永远循环的死循环，你的代码应当使表达式在最后变为 FALSE。当这种情况发生时，循环停止，执行继续到下一行代码，遵循逻辑循环。

### while 循环

`while` 循环接收一个表达式，后跟要执行的代码。

`while` 循环的语法为：

```php
while (expression)
{
    code to execute;
}
```

示例 6.14 展示了一个示例。

### 示例 6.14. 一个检查到 10 的 while 循环示例

```php
<?php
$num = 1;
while ($num <= 10){
    print "Number is $num<br/>";
    $num++;
}
print 'Done.';
?>
```

示例 6.14 输出这些：

- Number is 1
- Number is 2
- Number is 3
- Number is 4
- Number is 5
- Number is 6
- Number is 7
- Number is 8
- Number is 9
- Number is 10

Done.

在循环开始之前，变量 `$num` 被设置为 1。这被称为实例化计数器变量。代码块每执行一次，都会通过语句 `$num++;` 将 `$num` 的值加1。在 10 次迭代后，评估 `$num <= 10` 得到 FALSE，然后循环停止并打印 Done。记住增加 `$num` 变量，因为 `while` 循环依赖于它。小心不要导致死循环。不返回页面并在 Web 服务器上花费大量处理时间会导致负面影响。

### do ... while 循环

`do ... while` 循环接收一个类似于 `while` 语句的表达式，但它将其放在末尾。其语法是：

```php
do {
    code to execute;
} while (expression);
```

当你需要无论表达式值如何至少执行一次代码时，这种循环很有用。例如，如示例 6.15 所示，用这个循环检查 10。

### 示例 6.15. do ... while 循环示例

```php
<?php
$num = 1;
do {
    echo "Number is $num<br/>";
    $num++;
} while ($num <= 10);
echo 'Done.';
?>
```

### for 循环

`for` 循环提供了与 `while` 循环相同的功能，尽管它们需要一个定义的区域。语法为：

```php
for (initialization; condition; modification) {
    code to execute;
}
```

一个 `for` 循环示例：

```php
<?php
for ($num = 1; $num <= 10; $num++) {
    echo "Number is $num<br/>";
}
?>
```

### 跳出循环

通常情况下，退出循环的主要方法是满足决定停止点的表达式。如果循环中的代码发现了导致继续执行没有意义的错误，你可以使用 `break` 语句跳出循环。这类似于鞋带被卡在电梯上。

你在循环中可能遇到的可能问题包括在除以零时出错。如果你的客户端是恶意的或只是粗率的，她可能会在你预期正值的地方输入负值（尽管这应该在你的表单验证中获得）。在作为循环一部分执行的代码中，代码检查 `$counter` 是否等于零。如果是，代码调用 `break`。

### 示例 6.16. 使用 `break` 避免除以零

```php
<?php
$counter = -10;
for ($counter < 10; $counter++){
    if ($counter == 0) {
        echo "Stopping to avoid division by zero.";
        break;
    }
    echo "100/$counter<br/>";
}
?>
```

这产生了：

100/-3

100/-2

100/-1

Stopping to avoid division by zero.

### continue 语句

有时你可能希望直接跳过循环代码的执行。`continue` 语句为你完成了这一点。你本质上是跳到了下一次循环。确保在 `continue` 语句之前修改你的测试变量，否则可能会出现死循环。示例 6.17 展示了前面的示例使用 `continue` 代替 `break`。

### 示例 6.17. 使用 `continue` 代替 `break`

```php
<?php
$counter = -3;
for (; $counter < 10; $counter++){
    if ($counter == 0) {
        continue;
    }
    echo "100/$counter<br/>";
}
?>
```

```php
<?php
for($counter=0;$counter<10;$counter++) {
    //检查是否除以零
    if ($counter==0){
        echo "Skipping to avoid division by zero.<br>";
        continue;
    }
    echo "100/$counter ",100/$counter,"<br />";
}
?>
```

新的输出如下序列所示：

- 100/ - 3 - 33.3333333333
- 100/ - 2 - 50
- 100/ - 1 - 100
- 跳过以与除零保持策略性距离
- 100/1 100
- 100/2 50
- 100/3 33.33333333333
- 100/4 25
- 100/5 20
- 100/6 16.66666666667
- 100/7 14.2857142857
- 100/8 12.5
- 100/9 11.11111111111

注意，循环跳过了 `$counter` 值为零的情况，并且它无论如何都继续处理下一个值。

我们现在已经过的大部分主要的程序流语言结构。我们讨论了在你的程序中控制程序流的构建模块。表达式可以像简单的 `TRUE` 或 `FALSE`，也可以像使用本地运算符进行关系比较那样令人费解。与程序流构造结构（如 `if` 语句和 `switch`）相结合的表达式使得决策变得简单。

我们还检查了 `while`、`do ... while` 和 `for` 循环。循环对于基础元素网页任务非常有帮助，例如在 HTML 表格中显示查询结果。

# 第 7 章：函数

为了编写不仅包含几行代码且具有良好组织以产生价值的 PHP 程序，你必须对函数有深入的理解。函数可以让你避免在程序中反复编写相同的代码行。函数的工作原理为一段代码分配一个名为“函数名”的名称。随后，你通过调用该名称来执行代码。PHP 中有许多内置函数。例如，`print_r` 是一个函数，它用简单的英语而不是代码来打印变量周围的连贯数据。如果给出字符串、数字或浮点数，`print_r` 函数将打印属性本身。如果给出一个数组，属性将以键和组件的形式展示。在 PHP 5.0 中，`print_r` 和 `var_export` 可以显示对象的受保护和私有属性。

运行你的数组从 `aggregate_info` 到 `imap_ping` 经过 `pdf_open_image`。由于这些（函数）非常多，我们在本章中只需要涵盖几个基础知识，尽管我们会提供足够的数据，以便你使用函数去查看 http://www.php.net 获取完整的函数列表。

你可以查看 http://www.php.net 获取完整的函数列表。具体来说，我们将介绍以下内容：

- 如何创建一个函数、给它命名并执行该函数
- 如何向函数传递值并在函数中使用它们
- 如何从函数返回值并将其应用到你的代码中
- 如何在尝试使用函数之前验证该函数是否存在

在何时可能将代码拆分为函数时，这在某种程度上取决于主观的判断。毫无疑问，如果你发现自己自己在反复编写几行代码，那么将这些代码提取到自己的函数中是非常明智的。这会让你的代码更易读，并保护你免于在你对该段代码进行其他操作时进行多次改进，因为此时它只位于一个地方，而不是在你需要替换和更改它的多个地方。

函数是一个代码块，它允许值通过、形成它们，然后执行操作。将制作蛋糕并放入烤箱烘烤想象成一个函数。你将生团放入烤箱，面团混合物就是输入。烤箱接收面团混合物；这就是函数。函数烤蛋糕的结果是可食的烤蛋糕。函数甚至可以接受其他输入，例如温度和烘烤时间。这些不同的输入被称为参数。

参数将数据发送到函数，随后函数执行代码。函数可以使用从零到整个列表范围内的内容。在图 7.1 中，你将利用 `echo` 函数来显示某些文本。`echo` 显示你作为参数发送它的消息。大多数函数需要你将参数放在括号内，但 `echo` 是此情况的一个特例。变量的 `echo` 是万无一失的！图 7.1 显示了脚本结果如何显示。

```php
<?php
echo ("Hello world!");
?>
```

![](img/8e0a31fe30a159a13fdfed3405b5ed7_88_png)



![](img/8e0a31fe30a159a13fdfed3405b5ed7_88_png)

`echo` 显示你作为参数发送它的消息。大多数函数需要你将参数放在括号内，但 `echo` 是此情况的一个特例。图 7.1 显示了脚本结果如何显示。

```php
<?php
echo ("Hello world!");
?>
```

![](img/8e0a31fe30a159a13fdfed3405b5ed7_88_png)

`echo` 显示你作为参数发送它的消息。大多数函数需要你将参数放在括号内，但 `echo` 是此情况的一个特例。图 7.1 显示了脚本结果如何显示。

这显示为：

Hello from function-land!

`hi` 函数不接受任何参数，因此你不需要在括号之间列出任何内容。既然你已经定义了一个基础函数，我们来尝试加入几个参数怎么样？

## 参数

在调用函数时，参数提供了一种将数据传递给函数的有效方法，而无需费心考虑变量的作用域。在 PHP 中，你不需要描述参数包含什么类型的信息——只需要指定参数的名称即可。

一个接收参数的函数示例是 `strtolower`，它能将你的字符串“Hi world!”转换为小写。它接收一个 `string` 类型的参数，该数据类型在第 3 章中描述。此外，还有另一个名为 `strtoupper` 的函数，它可以将你字符串中的所有字符转换为大写字母，如示例 7.4 所示。

### 示例 7.4. 在另一个接收参数的函数内部利用字符串大小写函数

```php
<?php
// 字符串大写函数 function capitalize($str)
{
// 首先，将所有字符转换为小写
$str = strtolower($str);
// 第二，将第一个字符转换为大写
$str[0] = strtoupper($str[0]); // $str[0] 获取字符串中的第一个字符
echo $str;
}
capitalize("hEl WoRl!");
?>
```

Case 7.4 产生如下结果：

# Hi world!

`$str` 的值在函数内部被 `echo` 出来，是因为你没有指定任何从函数获取该值的方法。如上所述，`$str[0]` 获取字符串中的第一个字符。

PHP 不需要你描述一个函数是否真的返回一个值，或者它返回什么类型的数据类型。

参数同样可以包含默认值。有了默认值，你确实不需要为函数传递任何信息，它就会设置默认值。我们把你的大写函数改为具有一个默认值怎么样，允许你将每个单词的首字母大写，或者简化整个句子？我们将在示例 7.5 中实现这一点。

### 图 7.5. 创建一个带有默认参数的大写函数

```php
<?php
// 字符串或仅每个单词首字母大写函数 function capitalize($str,$each=TRUE) {
// 首先，将所有字符转换为小写，非第一个单词的字母可能保持大写
$str = strtolower($str);
if ($each === TRUE) {
$str = ucwords($str);
} else {
$str = strtoupper($str);
}
echo("$str <br>");
}
capitalize("hEllo WoRl!");
echo("Now do the same with the echo parameter set to FALSE.<br>");
capitalize("hEllo WoRl!",FALSE);
?>
```

结果如下：

Hello World!

Now do the same with the echo parameter set to FALSE

HELLO WORLD!

## 参数引用

当你向函数传递一个查询值时，函数内部会创建一个本地副本来存储该值。对该值进行的任何更改只会影响函数中变量的本地副本，而不会影响参数的源。你可以通过定义引用参数来定义修改源变量的参数。

引用参数通过在函数定义中的参数前加上符号符号 `&` 来定义引用。我们应该修改示例 7.5 中的 `capitalize` 函数，使其接收一个用于大写的字符串的引用变量，如示例 7.6 所示。

### 图 7.6 修改 `capitalize()` 以接收引用参数

```php
<?php
function capitalize (&$str,$each=TRUE ) {
// 首先，将所有字符转换为小写
$str = strtolower($str);
if ($each === TRUE) {
$str = ucwords($str);
} else {
$str[0] = strtoupper($str[0]);
}
}
$str = "Hi WoRld!";
capitalize( $str );
echo $str;
```

示例 7.8 产生如下结果：

Hello World!

由于 `capitalize` 将 `$str` 参数定义为引用参数，因此在执行时向函数发送了指向源变量的连接。函数基本上访问并修改了源变量。如果该变量没有被声明为引用，则会显示第一次估计的结果“hEllo World!”

## 包含和引入 PHP 文件

为了让你的代码更易读，你可以将函数放在不同的文件中。从互联网下载的许多 PHP 扩展都包含了函数，这些函数现在已经被记录下来，你基本上可以将它们包含在你的 PHP 程序中。另一方面，PHP 提供了四个函数，允许你从不同的文件中嵌入代码：

- `include`
- `require`
- `include_once`
- `require_once`

每一个 `include` 和 `require` 函数在功能上都非常相似，无论它们处理无法检索的资源的方式如何。例如，`include` 和 `include_once` 在资源不可检索时会发出通知并尝试继续执行程序。`require` 和 `require_once` 函数在无法恢复资源时会停止特定页面的准备。

你已经学会了如何定义函数及其参数，以及如何在它们之间正向传递数据；此外，我们还为你提供了一些极佳的示例，展示了调查潜在函数问题的有效方法。

接下来，我们将介绍一种编程风格，称为面向对象（OO）编程。PHP 5.0 拥有完善的 OO接口。关于哪种编码方式更好一直存在争论，事实上，并没有哪种绝对更好或更差；这基本上是一个风格问题，取决于个人经验。

## 7.3 面向对象编程

面向对象的目标与我们在讨论函数时考察的目标相同，基本上是为了让代码重用变得简单。它使用类将函数和变量组合在一起形成对象。你可以将对象看作是一个小秘密盒子，它们可以在不需要知道具体运作方式的情况下工作。

尽管如此，它们仍然利用函数；不过，它们在类中被赋予了另一个名称。这些被称为*方法*（methods）。类作为创建所定义对象的蓝图。变量也可以定义在方法中；但它们获得了可以被表征为类本身主要特征的新能力。

当从类创建另一个对象时，它被称为该类的*实例*（instance）。在类中定义的任何变量在每次出现时都会获得独立的存储空间。变量的存储空间使得对象具有记忆方法执行信息的能力。

如果你对面向对象编程的想法还不熟悉，不要因为不能立即理解一切而恐慌。我们将在第 8 章中处理类，所以只需要知道如何调用这些技术就足够了。实际上，任何对象可以实现的功能通过普通函数也可以实现。这仅仅是风格和个人喜好的的问题

### 创建类

类通常存储在独立的文档中以便重用。让我们构建一个名为 `Cat`（猫）的对象，它有三个方法：`meow`（喵叫）、`eat`（吃）和 `purr`（呼噜）。类定义了类本身及其名称。类名遵循与变量和函数相同的命名原则。构成类的代码放在大括号之间。以下示例创建了没有数据或定义任何方法变量的 `Cat` 类。你可以像示例 7.10 所示，快速验证类是否已定义。

### 示例 7.10. 从 `Cat` 类创建一个对象

```php
<?php
class Cat {
}

$fluffy = new Cat();
echo "Cushy is another " . gettype($fluffy) . ".";
?>
```

上述代码显示如下：

Fluffy is a new object!

### 创建实例

示例 7.10 描述了类并创建了它的实例。`new` 关键字告诉 PHP 返回 `Cat` 类的另一个实例。尽管该类什么都没做，但你可以看出它被表征为一个对象。类是构建实例的蓝图。类规定了该类的每个新实例中包含的内容。每个实例都可以在实例的上下文中执行类内部定义的任何操作。

### 方法和构造函数

方法是定义在类内部的函数。它们在类的范围内运行，包括它的变量。对于类来说，有一种特殊的方法被称为*构造函数*（constructor），它在创建类的另一个实例时被调用，以执行初始化类的工作，例如设置类中变量的初始值。构造函数通过创建一个与类名同名的方法来表征，如示例 7.11 所示。

### 图 7.11. 创建 `Cat` 构造函数

```php
<?php
class Cat {
    // 构造函数
    function Cat() {
}
}
?>
```

PHP 5.0 支持利用 `__constructor` 创建构造方法的语法，如示例 7.12 所示。如果 PHP 5.0 中的类没有此系统，则使用使用类名作为系统名的旧样式。

### 图 7.12. 使用类名的构造函数

```php
<?php
class Cat {
    // 构造函数
    function __constructor() {
    }
}
?>
```

构造函数也可以像方法一样包含参数。此外，类可以包含用户定义的方法。对于 `Cat` 类，你可以定义 `meow`、`eat` 和 `purr`，如示例 7.13 所示。

### 示例 7.13. 为 `Cat` 定义成员函数

```php
<?php
class Cat {
    // 构造函数
    function __constructor() {
    }
    // 猫喵叫
    function meow() {
        echo "Meow...";
    }
    // 猫吃
    function eat() {
        echo "*eats**";
    }
    // 猫呼噜
    function murmur() { 
        echo "*Purr...*";
    }
}
?>
```

当你创建一个类的实例时，构造函数会被调用（前提是它存在）。正如你可能知道的，类提供了对象的蓝图。你从类中创建一个对象。如果你看到“实例化类”这个表达式，这与创建对象的意思相同；因此你可以认为它们是同义的。当你创建一个对象时，你正在创建一个类的实例，这意味着你正在实例化类。

`new` 构建通过为新对象分配内存来实例化类，这意味着它需要一个唯一的后缀调用，即对构造函数的调用。

构造函数的名称与类名相同，它引入了新对象。

### 图 7.14. 从 `Cat` 类创建一个对象

```php
<?php
class Cat {
    // 构造函数
    function __constructor() {
    }
}

$myCat = new Cat;?>

// 猫喵叫
function meow() {
```

```php
function Birthday(){
  $this->age++;
}
```

```php
class Domestic_Cat extends Cat {
  /Constructor
  function Domestic_Cat() {
  }
  /Sleep like a domestic cat
  function sleep() {
    echo("Zzzzzz.<br/>");
  }
}
```

```php
$fluffy=new Domestic_Cat();
$fluffy->Birthday();
$fluffy->sleep();
echo "Age is $fluffy->age <br/>";
?>
```

Case 7.17 输出如下：

Zzzzzz.

Age is 1

注意，你可以从 `Cat` 类中访问 `Birthday` 函数以及最近定义的 `sleep` 方法，无论该方法定义在对象的哪个级别。

## 父类运算符 (parent)

从所有方面来说，`Domestic_Cat` 都是 `Cat`。然而，它包含了 `Cat` 的基础方法。同样，你可以重写父类的现有功能来编写自己的新代码。你只需要在新类中重新分类该函数即可。

在扩展类以重写现在定义在父类中的函数时，你仍然可以执行父类的代码，并在之后包含你自己的特定功能。要在你的代码之前调用父类技术，请使用：

`parent::method_from_parent`

这会调用父类中的父系统。然后你可以将其添加到代码中，如示例 7.18 所示。

### 图 7.18. 利用 `parent` 构造

```php
<?php
class Cat {
  /How old the cat is
  var $age;
  function Cat($new_age){
    /Set the age of this cat to the new age
    $this->age = $new_age;
  }
  function Birthday(){
    $this->age++;
  }
  function Eat(){
    echo "chomp chomp.";
  }
  function Meow(){
    echo "meow.";
  }
}
class Domestic_Cat extends Cat {
  /Constructor
  function Domestic_Cat() {
  }
}
```

### 静态方法与变量 (Static Methods and Variables)

如果方法和变量在类中被定义为静态，它们同样同样被利用和访问。正如第 3 章概述的，静态意味着系统或变量通过对象本身是唯一的。在 PHP 4.0 中，没有真正的方法可以判断一个变量是静态的；尽管如此，在 PHP 5.0 中可以使用 `static` 修饰符。

`::` 运算符允许你引用没有任何实例或对象的类中的变量和系统。示例 7.20 显示了如何使用 `::` 调用静态系统，以及普通的 `->` 调用语法如何不起作用，即使在创建了类的实例也是如此。（PHP 不报告错误——它只是不起。）

### 示例 7.20. 利用 `->` 和 `::` 运算符调用

```php
<?php
class Cat {
}
class Hypnotic_Cat extends Cat {
  /Constructor
  function Hypnotic_Cat() {
  }
  /This function must be called statically
  public static function hypnotize() {
    echo ("The cat was hypnotized.");
    return;
  }
}
/Hypnotize all cats
Hypnotic_Cat::hypnotize();
```

```php
$hypnotic_cat = new Hypnotic_Cat();
/Does nothing
$hypnotic_cat->hypnotize();
```

输出如下：

The feline was hypnotized.

当使用作用域解析符 (`::`) 调用策略时，你无法利用 `$this` 对象来引用该对象，因为根本没有对象。

### 变量引用 (Variable References)

在 PHP 中，变量名指向内存中存储存储的区域。可以有多个变量名指向内存中的同一个位置。取地址符运算符 (`&`) 用于表示你关注的是变量指向的内存区域，而不是它的值。

PHP 引用允许让两个变量引用相同的内容。通过这种方式，更改一个变量的值可以改变另一个变量的值。这可能会让发现代码中的错误变得异常困难，因为改变一个变量会改变另一个。

相同的符号也可以用于接收引用的函数。Case 5-21 利用了此来引用 `$some` 变量。

### 示例 7.21. 引用 `$some_variable`

```php
<?php
$some_variable = "Hello World!";
$some_reference = &$some_variable;
$some_reference = "Guten Tag World!";
echo $some_variable;
echo $some_reference;
?>
```

输出如下：

Guten Tag World!Guten Tag World!

示例 7.21 说明引用是使用 `&` 运算符定义的，并位于当前变量的 `$` 之前。变量 `$some_reference` 随后引用 `$some_variable`（放置“Hi World!”的内存区域）。

正如在本部分检查过的，变量引用有助于将变量作为引用传递给函数。这允许函数修改你基础代码中的变量，而不是修改一个在函数结束时丢失的本地副本/拷贝。

在不使用引用运算符的情况下将变量赋值给另一个变量会导致变量的副本被设置到内存中的另一个位置。可以更改新变量而不修改第一个变量。虽然这会占用更多内存，但如果你不想更改第一个变量的值，这是最好的方法。

既然你现在已经全面学习了函数和类，你已经准备好处理更多的对象了。

![](img/8e0a31fe30a159a13fdfed13405b5ed7_116_0.png)

图 9.1. Windows 运行对话

当你进入命令行时，输入 `mysql` 并按回车。`mysql` 命令的语法如下：

```
mysql -h hostname -u client -p
```

如果你在所有 PC 上都安装了 MySQL，默认用户名为 root。你可以忽略主机名 (hostname) 标志和值。当 MySQL 显示“Enter password”提示时，输入你的密码。如果密码、用户名和主机名正确，你将看到一个如图中所示的横幅显示。

![](img/8e0a31fe30a159a13fdfed13405b5ed7_116_1.png)



# 安装后可用的默认数据库

安装后可用的默认数据库名为 `mysql`。`mysql` 数据库同样存储了数据库客户端的验证信息。尝试不要删除它！当你启动 `mysql` 时，并没有指定与特定数据库的关联。`USE` 命令可以帮助你完成这一点。

要与 `mysql` 数据库关联，请在 MySQL 提示符下输入相应的命令：

```sql
USE mysql;
```

系统返回：

```
Database changed
```

如果你的 ISP 提供了不同的数据库名称，请使用该名称而不是 `mysql`。

# 9.2 管理数据库

现在你已经与数据库关联，可以创建用户、数据库和表了。如果你在托管环境中使用 MySQL 服务器，你将不需要创建数据库或客户端账户，因为他们已经为你提供了用户名和数据库名。

## 创建用户

要创建除默认首选 `root` 客户端之外的用户，请执行 `grant` 命令。`grant` 命令的语法如下：

```sql
GRANT PRIVILEGES ON DATABASE.OBJECTS TO username@'hostname' IDENTIFIED BY 'password';
```

例如：

```sql
GRANT ALL PRIVILEGES ON *.* TO "michele@localhost" IDENTIFIED BY 'secret';
```

这创建了一个名为 `michele` 的客户端，它可以访问本地的任何内容。要切换到 `michele` 客户端，在 `mysql` 命令提示符下输入：

```sql
exit
```

此时，从命令行使用新的用户名和密码启动 MySQL。在启动 MySQL 时，用户名和密码的语法标点符号为：

```bash
mysql -h hostname -u username -p password
```

注意 `-p` 和密码字之间没有空格。如果你只指定 `-p` 标志而不带密码，MySQL 会提示你输入密码字。如果你不需要客户端获取除其自身表以外的表，可以将 `GRANT PRIVILEGES ON *.* TO "michele"` 中的 `*` 替换为客户端数据库的代码，如下所示：

```sql
GRANT ALL PRIVILEGES ON store.* TO "michele@localhost" IDENTIFIED BY 'mystery';
```

你必须以 `root` 或具有授权的用户身份运行此行代码。在这段代码中，单词 `store` 关联到分配权限的数据库名，你将在后续部分创建它。

## 创建 MySQL 数据库

你将创建一个名为 `store` 的数据库。`CREATE DATABASE` 命令的功能如下：

```sql
CREATE DATABASE store;
```

如果执行成功，你将得到如下输出：

```
Query OK, 1 row affected (0.03 sec)
```

数据库名称不能包含任何空格。在 Linux 和 Mac OS X 等 Unix 服务器上，数据库名称也是区分大小写的。

要开始使用此数据库，输入：

```sql
USE store;
```

你将得到结果：

```
Database changed.
```

相信你已经准确完成了所有操作，新信息已经设置好并将被选中。创建表来存储信息是一个至关重要的想法，这正是我们要去的地方！

# 9.3 使用 phpMyAdmin

`phpMyAdmin` 工具可以通过 http://www.phpmy.net/ 访问，允许你通过 Web 程序控制 MySQL 数据库。只需要一个安装了 PHP 的 Web 服务器和一个用于控制它的 MySQL 数据库。

要引入 `phpMyAdmin`，请按照以下步骤操作：

1. 点击主页上的“Downloads”。
2. 下载存档文件，例如 `all-languages.tar.gz`（Unix 归包）或 `all-languages.zip`（Windows ZIP 设计）。
3. 解压存档（包含子目录）到 PC 上的一个目录。
4. 将它们发送到可以执行 PHP 记录的 ISP 账户。或者，如果你本地安装了 Web 服务器，将它们移动到文档根目录下具有一致名称的目录，例如 `myadmin`。
5. 为了建立 `phpMyAdmin`，在 `myadmin` 目录内创建一个名为 `config` 的目录。在 Linux 框架上，执行以下命令来创建目录并设置系统允许设置程序修改配置文件：

```bash
cd myadmin
mkdir config
chmod o+w config
cp config.inc.php config/
chmod o+w config/config.inc.php
```

6. 在你的 Web 程序中，访问 http://localhost/myadmin/scripts/setup.php。

你将看到一个如图中所示的屏幕。

![](img/8e0a31fe30a159a13fdfed13405b5ed7_120_0.png)

图 9.3. phpMyAdmin 设置为 phpMyAdmin 创建了配置文件

7. 在“Servers”段落，点击“Add”按钮。服务器设置页面如所示所示。

*(注：由于原文中存在大量重复且混乱的 OCR 描述，译文已根据逻辑进行了精简处理)*

```sql
SELECT *
FROM 'authors'
LIMIT 0, 30
```

authors 表中的数据以及用于生成该数据的查询

# 9.4 数据库概念

数据库是数据的存储库。它们在监督和控制组织化数据方面脱颖而出。结构化信息是一种安排相关数据片段的方法，我们之前已经在第 3-6 章中检查过它。结构化数据的基本类型（也可以称为数据结构）包括：

- 文件
- 列表
- 数组
- 记录
- 树
- 表格

这些每种基本结构都有许多变体，并考虑了在信息上要执行的不同操作。理解这一主概念的一种简单方法是考虑电话目录（电话簿）。它是最常见的数据库，包含了几项数据内容——姓名、地址和电话号码，此外还有特定范围内的每个电话用户。电话簿已经演进，少数人的名字可能是**加粗**的，但通常情况下，电话目录中的每个条目都具有相同的结构。

如果你将电话目录的纸质版比作数据库来看，那么电话目录就是一张表，其中包含每个订阅者的记录。每个订阅者的记录包含三个字段（也称为属性或列）：姓名、地址、电话号码。这些记录通过姓名字段标识，该字段被称为键字段。电话目录按字母顺序排列，按姓氏在先；请查看图 9.9 以了解基于电话目录类比的你数据库中的独特记录和独特字段。虽然 MySQL 数据库中的信息不是以任何特定顺序存储，但可以按顺序进行查询。

| 姓名 | 地址 | 电话号码 |
| :--- | :--- | :--- |
| Davis, Michele | 7505 N. Linway Fpt 53217 | 414-352-4818 |
| Meyer, Simon | 5802 Beard Avenue S 55419 | 612-925-6897 |
| Phillips, Jon | 4204 Zenith Avenue S 55416 | 612-924-8020 |
| Phillips, Peter | 6200 Bayou Avenue HPk 55411 | 651-668-2251 |

## 图 9.9 电话簿记录和字段

如果你从电话簿中提取相同的信息并将其放入数据库，你就可以组合问题，例如：谁的电话号码是 651-668-2251，或者特定邮政分区或邮政编码中所有姓 Davis 的人。这种数据库类似于大型电子表格；它可以被称为平文件数据库，这意味着每个数据库都自包含在一张表中。自 20 世纪 70 年代以来，处理信息的关系型数据库已经取代了平文件。它们维护各种表，并根据需要连接在一起。

# 9.5 结构化查询语言

既然你已经定义了表，就可以向其中添加信息。MySQL 将跟踪所有细节。要管理信息，请使用结构化查询语言 (SQL) 命令。

由于其设计目的是为了轻松地描述行与表之间的关系，数据库使用 SQL 来修改表中的信息。

SQL 是一种用于大多数数据库（例如 MySQL、Oracle 或 Microsoft SQL Server）的标准语言。它被专门创建为一种用于检索、包含和管理存储在数据库中的信息的语言。我们将在下一章介绍 MySQL 的细节，但我们将从一些易于使用的简单命令开始。我们将从创建表开始。

## 创建表

利用表命令来指定新数据库表的结构。当你创建一个数据库表时，每个段落都有几个选择以及数据类型和列名。在向表中添加信息时必须提供的值通过 `NOT NULL` 关键字指定。`PRIMARY KEY` 关键字用于指定。虽然 MySQL 数据库中的信息不是以任何特定顺序存储，但可以按顺序进行查询。

### 示例：

```sql
CREATE TABLE books (
    id INT NOT NULL AUTO_INCREMENT,
    title VARCHAR(255) NOT NULL,
    pages INT,
    PRIMARY KEY (id)
);
```

### 示例：

```sql
CREATE TABLE authors (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    age INT,
    PRIMARY KEY (id)
);
```

## 插入数据

```sql
INSERT INTO books (title, pages) VALUES ('The Great Gatsby', 180);
INSERT INTO books (title, pages) VALUES ('1984', 328);

INSERT INTO authors (name, age) VALUES ('F. Scott Fitzgerald', 44);
INSERT INTO authors (name, age) VALUES ('George Orwell', 46);
```

## 查询数据

```sql
SELECT * FROM books;
SELECT name FROM authors WHERE age > 40;
```

`WHERE` 子句以另一种方式限制了选择哪些行。`WHERE` 为查询返回的结果设置了截断点。例如，如果某个字段不符合精确的值，或者作为某项属性并不精确或显著，则该行可能会被忽略。`ORDER BY` 子句允许你以期望的方式对返回的数据进行排序。多个表中的字段可以被强制要求对等。如果在 `SELECT` 语句中整合了多个表而没有 `WHERE` 子句，随后的结果将变成笛卡尔积（Cartesian product），其中第一个表中的每一行都与第二个表中的所有列一起返回，然后对第一表中的第二行执行同样的操作。换句话说，这意味着会产生大量的的结果！

# 修改数据库数据

如果你犯了错误，例如输入了某本书的错误页数，你可以利用 `UPDATE` 命令来更改信息。升级表有许多不同的动机，例如客户更改密码。

`UPDATE` 使用与 `SELECT` 语句相同的 `WHERE` 子句，但它包含一个指定部分段值的 `SET` 命令。

# 删除数据库数据

`DELETE` 命令用于删除表中的列或记录。它采用与 `UPDATE` 相同的 `WHERE` 子句，但会删除任何匹配的列。如果没有 `WHERE` 子句，你将面临“噢糟糕！”的时刻，因为表中的每条记录都将被删除。

# 第 10 章：数据库最佳实践

既然你已经运行了 MySQL 并创建了数据库，我们应该谈谈数据库设计和保护你的数据库。正如你很可能意识到的那样，对数据进行备份至关重要。将 MySQL 添加到 PHP 并为你的动态网站整合应用程序是一个极不起的开始。然而，准确结构化你的数据库将极大帮助。如果你拥有安全性、信息完整性和备份，你就拥有了数据库最重要的部分。我们将在稍后的章节中讨论安全性。

## 10.1 数据库设计

正确设计你的数据库对于你应用程序的卓越性能至关重要。就像把打印机放在你办公室之外是无效的一样，在糟糕的连接中设置信息会降低工作效率，因为你的数据库服务器将浪费时间搜索信息。在考虑你的数据库时，请考虑当数据库被使用时我们会遇到哪些类型的查询。例如，可购买物品的详情是什么？或者，这是否是一个合法的用户名和密码？

### 关系型数据库

MySQL 是一个关系型数据库。关系型框架的一个关键要素是信息可以分布在几个表中，而不是像我们的电话目录示例那样。相关信息存储在孤立的表中，并允许你通过两个两个表的键（`key`）将它们结合。键是表之间的连接。主键（`primary key`）的选择是在设计另一个数据库时你做出的最基础的选择之一。

你必须理解的最重要的概念是，必须保证键是唯一的。如果可能两条记录（过去、现在或未来）在某个属性上具有相同的特征，请不要使用该特征作为基本键。从另一个表中计算键字段计数以形成表与表之间的连接被称为外键关系（`foreign key relationship`），类似于主管与工人或客户与买家之间的关系。

由于你有存储相关信息的独立表，你必须考虑每个表中与不同表中项目相对应的项目数量。

### 关系类型

数据库连接通过以下分类进行量化：

- 一对一连接
- 一对多连接
- 多对多连接

我们将讨论这些每种连接并提供示例。如果你在考虑关系时考虑到家庭结构，那么你的思路就清晰了。当你只和其中一个父母相处时，这是一种特定的关系；当你和父母双方在一起时，那是另一种关系。当你获得一个重要的伙伴，并且你们每一个人——父母、你和你的伙伴——一起做某事时，那是另一种关系。这与池化相似性没有区别。所有这些不同类型的连接类似于盛放你关系流的特定容器。在数据库世界中，这就是你创建的信息。

### 一对一关系

在一对一关系中，每个项目与一个且仅一个另一个项目标识。在在线书店的实例中，客户与他们的配送地址之间存在对应关系。每个客户必须精确有一个配送地址。

### 标准化



# 数据库标准化与设计

## 标准化概述

思考你的信息如何连接以及组织它们的最有效方法被称为**标准化**（standardization）。信息的标准化是根据连贯的连接将其拆分，以尽可能地减少信息的重复。大多数情况下，复制的信息浪费空间并使维护成为一个问题。如果你更改了复制的数据，可能会漏掉某部分并导致数据库中出现不一致的风险。然而，有很多东西是可以感激的；但是，数据库将每条信息都设置在自己的表中将花费过多的处理时间，而且查询会变得复杂。在其中发现平衡是目标。

虽然电话目录示例极其简单，但你通过网站页面准备的信息类型可以从智能收集相关信息中极大受益。我们继续以在线书店为例。网站需要了解客户信息，包括登录、地址和电话号码，以及关于书籍的数据，包括标题、作者、页数以及每个标题何时获取的。从将这些大部分数据放在一个表中开始可能看起来是一个明智主意，但它浪费了数据库空间并使信息更新变得重复。每次购买都会重复所有客户信息。一本书被限制为两个作者。在这种情况下，我们使用的是具有两个作者的书，而不是仅仅一个。

位置的组成部分可以被认为并非直接与客户端等同。道路地址取决于邮政分区，邮政分区取决于城市，最后，城市取决于州。**第三型范式**（Third Normal Form）强制将这些内容拆分为孤立的表。

正如你可能已经看到的，第三型范式从根源上消除了很多信息重复，尽管这可能是以操作的便利性和执行效率为代价的。在这个示例中，你真的期望城市和道路名称会频繁更改吗？在这种情况下，第三型范式仍然可以防止城市和道路名称的拼写错误。由于这是你的数据库，你可以在标准化与数据库的运行速度或易用性之间决定你想要的和谐平衡点。

既然我们已经确定了信息布局的要点，我们就可以深入探讨如何描述分段的细微元素。

## 列数据类型

尽管数据库存储的是与你在 PHP 中收集和处理的相同的数据，但在创建数据库时，数据库需要将字段设置为特定类型的信息。

请记住，PHP 不是强类型语言，但大多数数据库都是！

## 数据类型详解

数据类型是对特定种类数据的分类。当你阅读时，你习惯于传统的分类，例如字母和数字。因此，由于你使用了图像、数字和字母，识别不同类型的信息就变得简单。你可以初步判断一个数字是比率、时期还是货币单位。帮助你理解比率、时间或货币单位的图像（符号）就是该信息的类型。数据库使用内部代码来记录它所创建的各种类型信息的状态。

许多编程语言要求软件设计人员宣布每个信息对象的数据类型，大多数数据库框架也要求客户端指定每个信息字段的类型。可用的信息类型随不同的编程语言以及不同的数据库应用而变化。尽管，无论如何，三种基本信息类型——数字、日期/时间和字符串——都以某种形式存在。

数字型 ID 结合一组特殊的数字，提供了一种确保**主键字段**（`key field`）唯一性的方法。在创建字段时指定 `auto_increment` 值是为分段产生唯一 ID 的极佳方法。例如，如果有两个名为 John Smith 的创建者，而你使用他们的名字作为键，那么你在识别使用的是哪一个 John Smith 时就会遇到问题。保持键的唯一性是确保数据库中拥有正确信息的关键部分。

# 数据的备份与恢复

## 备份与恢复数据

事实上，即使是维护得最好的数据库偶尔也会出现问题。工具故障，特别是工具故障，真的会破坏你的网站页面。仅仅下载 Web 服务器上的文档（HTML、PHP 和图片）是不够的。没有比告诉 Web 客户端他们需要返回数据（例如他们的记录）或需要重新制作你的列表项更糟糕的事情了。拥有一个完整的备份可以在 60 分钟的停机时间与需要重新哈希数据之间产生质的区别。

## 复制数据库文件

你也可以对 MySQL 数据库的数据文件进行简单的文档备份，就像你下载 HTML 和 PHP 文档一样。如果你可以下载文档，就可以下载 MySQL 数据库文档。

我们不建议使用这种策略将数据库从一台机器迁移到另一台服务器，因为不同的 MySQL 版本可能预期这些文档具有不同的结构。MySQL 将数据文件存储在一个特殊的信息注册表中，在 Windows 上通常位于 `C:\Program Files\MySQL\MySQL Server 4.1\data\[database_name\]`，在 Unix 变体（例如 Linux 和 Mac OS X）上位于 `/var/lib/mysql`。执行复制备份之前关闭 MySQL 服务，以确保在备份时所有文档都来自同一时间点。

要使用当前的数据文件完全下载并恢复 MySQL 数据库，所有文档必须在下载时的相同注册表中进行替换。然后必须重启数据库。

## mysqldump 命令

使用 MySQL 命令行创建完整的数据库备份是理想的。你用于更改阶段或将数据库从一台服务器迁移到另一台服务器的工具相同；`mysqldump` 会创建一个包含重建数据库对象和填充信息的 SQL 语句文本文件。`mysqldump` 命令从命令行运行，接受下载单个表、单个数据库或所有内容的参数。命令的语法为：

```
mysqldump -u client -p objects_to_backup
```

`mysqldump` 命令创建备份输出到标准输出（默认仅打印到屏幕）。指定一个对你需要下载的对象权限的客户端。你将被要求输入该客户端的相关密码。

使用大于（`>`）符号将此输出重定向到一个文件名的文档。

### 备份示例

我们将为你演示如何在命令行中备份名为 `store` 的数据库。

```
mysqldump -u root -p store > my_backup_of_store.sql
```

这告诉 `mysqldump` 以 `root` 客户端身份登录数据库并备份 `store` 数据库。你将被要求输入安装时指定的 `root` 密码。命令的输出通过重定向字符（也称为大于符号 `>`）放在一个名为 `my_backup_of_store.sql` 的文件中。

## 恢复 MySQL 备份

好消息是从 `mysqldump` 恢复你的数据库并不困难。备份文件的内容基本上是 SQL 语句，因此可以由 MySQL 命令行客户端恢复下载的信息。

如果你使用 `mysqldump --all-databases` 将数据库备份到名为 `my_backup.sql` 的文件，你可以恢复数据库：

```
mysql -u root -p < my_backup.sql
```

如果你是对单个数据库进行特定备份，情况会复杂一些。要恢复那种备份文件，请使用 `-D` 命令行开关：

```
mysql -u root -p -D store < my_backup.sql
```

既然你已经知道如何恢复默认转储记录，我们可以继续学习有关导出和导入信息的其他应用。

## 与其他格式一起

尽管处理基于 SQL 的文档是有益的，但有时你可能需要以不同的格式保存信息。例如，处理数据列表的一种常用方法是 CSV（逗号分隔值）格式。`mysqldump` 支持这种格式。你只需要指定 `-no-create-info`、`-tab` 以及 `-fields-terminated-by` 参数：

```
mysqldump -u root -p -no-create-info -tab=/home/jon -fields-terminated-by=','
```

## mysqlimport 命令

当你设置数据库时，可能需要从另一个数据库或 CSV 格式的表格获取信息。例如，如果你正在处理书籍，你可能获取当前的书籍索引。示例 8-2 显示了书籍数据。

要导入示例中的信息，使用 `mysqlimport`：

```
mysqlimport -u root -p -fields-terminated-by=',' books.txt
```

文件的基本部分（不包括扩展名）决定表名。在上例中，表名为 `books`。表必须已经存在，否则会报错。另一个重要的关键字是 `ENCLOSED BY`；允许你指定字符（例如双引号 `"`）来包裹文件中的每个字段。这对于避免处理如《Exemplary Shell Script, Second Edition》这样的书名出现问题很有用，否则会导致 `mysqldump` 将标题的 Second Edition 部分误认为是下一个字段的开始。

## 最佳备份实践

取决于你的基本信息以及它更改的频率，你可以决定备份的频率。通常情况下，每周、每两周和每月是最常见的。如果你的业务完全依赖你的数据库，你应该制定每周甚至每天的备份计划。此外，在不同的位置保留信息的副本对于防止大规模范围灾难（例如火灾）是一个明智之举。我们的一个客户每月在工作场所的防火燃安全箱中进行每月的每月备份，尽管另一位客户会将信息发送到备份管理部门。备份部门可以使用物理硬盘、磁带或 CD，也可以登录您的服务器执行电子化备份。

# 进级 SQL

在本节中，我们将介绍一些数据库思想，虽然这些对于构建您的网站并非完全基础，但可以增强执行并让您的查询更具适应性。

## 索引

记录的工作方式就像书籍目录符合预期一样。如果你在没有目录的情况下搜索“Make TABLE”这个单词，你将不得不花费大量精力浏览书页，寻找可能相关的区域。然后你需要检查整个段落。这绝对对你或数据库引擎的时间来说都不是有效的利用。这种安排就是一个列表。

列表中的信息经过排序和组合，使得发现特定值变得明智。如果属性是经过排序的，如果你正在搜索某个特定内容，当数据库在发现一个比你正在查找的项目更大的值时，就可以停止查找。

然而，你面临着与书籍相同的问题。如果一条记录如此特殊，为什么不记录所有内容呢？有多种原因：

- 可用空间有限。
- 在编写书籍时，生成和维护一个巨大的、广泛的索引是低效的。
- 文件中的信息过多意味着在选择信息时需要更多时间查阅文件。

通过这种方式，可以对在表中归档哪些字段做出一些明智的选择。每个文件都因为容量需要对应其特定的数据文件，当数据库中排序字段的内容更改时，这可能会包含一些准备时间。

### 索引的使用场景

如果你执行不带 `WHERE` 子句的简单 `SELECT` 语句，将不会使用索引。

列表可以在三个值得关注的区域发挥作用：

#### 在 WHERE 子句中

例如，查询 `SELECT * FROM creators WHERE creator = 'Ellen Siever';` 如果可用，将利用 `creator` 字段的索引。

#### 在 ORDER BY 子句中

例如，查询 `SELECT * FROM contacts ORDER BY creator;` 如果可用，将利用 `creator` 字段的索引。

#### 在 MIN 和 MAX 子句中

例如，如果 `MIN` 或 `MAX` 函数中指定的段具有索引，则查询将利用索引。

只需记住，索引必须在使用之前定义好。

## 在何处指定索引

数据库记录可以指定为 `CREATE TABLE` 命令的一部分，也可以通过特殊的 SQL 语句添加到现有表中。如果索引是作为 `CREATE TABLE` 命令的主要部分创建的，它指定在代码段的末尾：

```
UNIQUE index(creator)
```

`UNIQUE` 命令在 `creator` 字段上创建一个索引。同样，并不是所有索引都是唯一的。

## 多列索引

同样可以创建使用多个字段的 MySQL 索引。多列唯一索引保证了字段组合的唯一性。

最适合的字段是那些经常作为 `WHERE` 语句一部分使用的字段，特别是当你意识到将使用包含复合键时。这些是添加到多列列表的极佳字段。在多列记录中请求字段的目标是让经常使用的字段在前。MySQL 使用多列索引来加速查询，即使只使用了列表的第一部分估计。

主索引也是特殊的。每个表允许一个主索引。尽管如此，你可以拥有你想要的数量的特殊索引。

我们将执行一个带有特定 `WHERE` 条件的查询，然后使用 `EXPLAIN` 获取关于 MySQL 如何处理该查询的见解：

`EXPLAIN` 输出关于 MySQL 如何处理查询的大量数据。

它告诉您：

- 正在使用 `creators` 表。
- 查询类型为 `ALL`，因此每条记录都经过过滤以检查正确的值。
- 由于没有匹配的记录，`possible_keys` 为 `NULL`。
- 此查询使用的 `key` 目前为 `NULL`。
- `key_len` 是键的长度；目前为 `NULL`，因为没有使用键。
- `ref` 部分显示了与键使用的字段或常量；目前为 `NULL`。
- 必须遍历的列数。

注意，许多属性相对于索引发生了变化：

- `ref` 意味着从此表中读取具有协调索引列表属性的行以进行匹配。
- `possible_keys` 显示一个可能的键 `authind`。
- `key` 显示使用了 `authind` 键。对应的 `key_len` 显示键的长度为 126。
- `ref` 告诉您正在使用一致的键。
- `columns` 显示搜索了一行，这在最近并不多见。

相关性表明，添加索引即使对于小表也节省了大量的处理时间。

## 使用 LEFT JOIN ON 子句进行选择

我们讨论过在 `SELECT` 语句中使用 `WHERE` 子句执行连接，尽管还有另一种连接表的方法。

与其使用 `WHERE` 关键字，可以使用 `LEFT JOIN` 执行左连接或外部连接。左连接本质上允许你查询两个通过关系连接在一起的表，但允许即使另一个表中没有协调行，其中一个也能返回行。使用书店表作为示例，你可能需要执行一个获取客户和购买信息的查询，此外记录尚未购买过任何东西的客户。

使用该表：

```sql
SELECT * FROM clients LEFT JOIN buys ON clients.user_id = buys.user_id;
```

如果你想尝试此查询，你需要创建 `clients` 表并包含一些信息：

```sql
CREATE TABLE clients (
    user_id int(100) NOT NULL AUTO_INCREMENT,
    first_name varchar(100) DEFAULT NULL,
    last_name varchar(100) DEFAULT NULL,
    username varchar(45) DEFAULT NULL,
    secret_key varchar(32) DEFAULT NULL,
    PRIMARY KEY (user_id)
);

INSERT INTO clients VALUES (1,'Michele','Davis','mdavis),(2,'Jon','Phillips','jphillips');
```

## 使用数据库函数

就像 PHP 中有函数一样；你可以在 MySQL 查询内部使用函数。我们将讨论几类函数，从字符串函数开始。

你将发现的其他实际类型是日期和时间修改函数。

### 字符串函数

由于你经常需要处理字符串，MySQL 提供了许多函数来完成一系列任务。你主要会在从查询返回的信息上使用字符串函数。然而，在不引用表的情况下使用它们也是可能的。

**拼接**。与使用 PHP 后置运算符（`.`）组合字符串的方法类似，MySQL 可以通过 `CONCAT` 函数将数据字段的字符串粘在一起。

例如，如果你需要返回一个连接标题和页数的单一字段，你可以使用 `CONCAT`。

## 事务

事务强制对数据库的不同更改作为单个工作单元进行处理。要么所有进展被提交，要么全部被丢弃。当你开启事务对该表实施改进时，其他会话无法访问该表。在你的会话中，如果在升级后选择相同的信息，你可以迅速看到任何进展。

两个命令控制你的事务。`COMMIT` 命令将进展保存到数据库。`ROLLBACK` 命令放弃进展。

```sql
SELECT * FROM books_innodb WHERE (title_id = 1 OR title_id = 2);
```

此操作产生了结果：

```
+----------+-----------------------+-------+
| title_id | title                 | pages |
+----------+-----------------------+-------+
| 1        | Linux in a Nutshell   | 476   |
| 2        | Classic Shell Scripting | 558 |
+----------+-----------------------+-------+
```

示例：使用事务

```sql
CREATE TABLE `books_innodb` (
    `title_id` int(11) NOT NULL auto_increment,
    `title` varchar(150) default NULL,
    `pages` int(11) default NULL,
    PRIMARY KEY (`title_id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

INSERT INTO `books_innodb` (`title_id`, `title`, `pages`) VALUES
(1, 'Linux in a Nutshell', 476),
(2, 'Exemplary Shell Scripting', 558);

START TRANSACTION;
DELETE FROM books_innodb WHERE title_id = 1;
DELETE FROM books_innodb WHERE title_id = 2;
```

# 第 11 章：让 PHP 与 MySQL 通信

现在你已经可以使用 MySQL 客户端工具来控制数据库中的信息，你可以开始使用 PHP 来显示和修改数据库中的信息。

PHP 提供了用于处理数据库的标准函数。

首先，我们将讨论 PHP 内置的数据库函数。我们还将向你演示使用 PHP 扩展与应用程序仓库（PEAR）数据库函数的最有效方法，这些函数让你能够使用相同的函数来访问任何支持的数据库。这种灵活性源于一种被称为“抽象”的方法。在编程接口中，反射简化了复杂的连接。它通过消除协作中的任何无关紧要的部分来符合预期，让你能够专注于核心部分。PEAR 的 DB 类就是这样一种数据库接口反射。

## 11.1 流程

登录数据库所需的数据被减少到了最低。这种标准配置允许你与 MySQL 以及其他使用相同函数的数据库进行协作。同样，其他 MySQL 特有的函数被通用的、能够与多个数据库通信的通用函数所取代。例如：

MySQL 特有的接口函数是：

```php
mysql_connect($db_host, $db_username, $db_password);
```

对比 PEAR 的 DB 接口函数：



```php
$connection = DB::connect("mysql://$db_username:$db_password@$db_host/$db_database");
```

在两种情况下，基本数据都是可用的，但 PEAR 函数额外指定了要连接的数据库类型。你可以连接 MySQL 以及其他支持的数据库。我们将在感兴趣的地方检查这两种连接技术。

在本节中，你将了解如何从 PHP 连接到 MySQL 服务器，如何使用 PHP 获取和检索存储的信息，以及如何准确地向客户端显示数据。

### 流程

无论使用 `mysql` 命令行界面还是 PHP，执行查询的本质步骤都是相同的：

- 连接到数据库。
- 选择要使用的数据库。
- 构建 `SELECT` 语句。
- 执行查询。
- 显示结果。

我们将针对原生 PHP 和 PEAR 函数逐一介绍这些进展步骤。

### 资源

在连接到 MySQL 数据库时，你将使用两个新资源。主资源是连接标识符，它持有与数据库建立动态连接所需的大部分重要数据。另一个资源是结果集。它包含了从动态数据库查询结果集中检索结果所需的所有数据。

你将在本部分创建并分配这两个资源。

# 使用 PHP 函数查询数据库

在这一部分，我们介绍如何用 PHP 连接到 MySQL 数据库。这非常简单，我们将直接从示例开始，但我们应该快速说明实际发生了什么。当你尝试连接到 MySQL 数据库时，MySQL 服务器会根据你的用户名和密码验证身份。PHP 会为你处理数据库连接，并允许快速开始执行查询并收集信息。

与第 8 章一样，我们需要相同的数据来连接数据库：

- 数据库服务器的 IP 地址
- 数据库名称
- 用户名
- 密码

在继续之前，请验证你可以使用 MySQL 命令行客户端登录你的数据库。

图 9-1 显示了数据库协作流程如何识别这两种类资源的。构建 `SELECT` 语句发生在第三次函数调用之前，但并未标出。它是通过原生 PHP 代码完成的，而不是 MySQL MySQL PHP 函数。

# 11.2 使用 PHP 函数查询数据库

你需要做的主要工作是连接到数据库并检查是否存在连接。通过设置存储连接数据的文档，允许你在调用 `mysql_connect` 函数时使用变量而不是硬编码属性，如示例 9-4 所示。我们通过包含这些代码片段正在创建一个文档 `db_test.php`。

`mysql_connect` 函数接受数据库、用户名和密码作为参数。如果连接成功，则返回一个数据库连接。如果无法建立连接，则返回 `FALSE`。

## 引入 PEAR

PEAR 使用一个管理你引入的 PEAR 的管理器。取决于你引入的 PHP 版本。如果你运行的是 PHP 4.3 或更高版本，它现在已经引入了。如果你运行的是 PHP 5.0，PEAR 被拆分成不同的包。你感兴趣的 `DB` 包是可选的，但已经引入了。

### Unix

你可以通过在 shell 中执行以下命令在 Unix 系统上引入包管理器：

```bash
curl -L http://get.pear.org/installer | php
```

这会将 get-pear.org 网站的输出（实际上是源 PHP）用于引入 PEAR 并将其传递给 `php`。

### Windows

PEAR 安装程序会创建一个名为 `C:\php\PEAR_ENV.reg` 的文件。你必须双击它以在注册表中设置 PEAR 路径。当对话框显示验证你的数据时，你将其添加到注册表并点击确定。

在运行此 `.bat` 文件后，你可能需要修改 `php.ini` 文件将 PEAR 索引包含包含路径中。`php.ini` 的第 447 行现在类似于：

```ini
include_path = "c:\php\includes;c:\php\PEAR"
```

在使用 `DB` 包之前必须重启 Apache。

### 便捷的 ISP

大多数 ISP 都引入了 PEAR DB。如果你的 ISP 还没有引入，请请求他们引入。你可以通过尝试运行示例 9-8 中的 PHP 代码来判断 PEAR DB 是否已引入，查看 `require_once('DB.php');` 是否会导致错误。

### 引入附加包

完成后，你可以在命令行中输入 `pear` 来访问 PEAR 包管理器。引入新模块只需执行 `pear package`。

### 创建一个连接实例

`DB.php` 文档描述了一个 `DB` 类。有关处理类和对象的更多信息，请参阅第 5 章。我们基本上是在调用类中的方法。`DB` 类有一个 `connect` 方法，我们将使用它而不是我们旧的接口函数。双冒号 (`::`) 表示我们正在从第 4 行的类中调用该函数：

```php
$connection = DB::connect('mysql://$db_username:$db_password@$db_host/$db_database');
```

当你调用 `join` 函数时，它会创建另一个数据库关联并存储在变量 `$connection` 中。`join` 函数尝试根据你提供的连接字符串与数据库建立关联。

#### 连接字符串

连接字符串使用这种新格式来连接在孤立字段中提供的登录数据：

`dbtype://username:password@host/database`

这种结构你可能觉得很眼熟，因为它从根本上说与 Windows 记录顺序的连接字符串是相同的。字符串的第一部分是让 PEAR 函数区别于原生 PHP 的关键点。`phptype` 字段指定了要连接的数据库类型。

支持的数据库包括 `ibase`、`msq`、`mssql`、`mysql`、`oci8`、`odbc`、`pg` 和 `sybase`。你的 PHP 页面要与不同类型的数据库协同工作，只需要更改 `phptype`！

用户名、密码和数据库应该与原生 PHP 接口是一致的。只需要指定关联类型即可。尽管如此，你通常需要指定所有字段。

在包含了 `db_login.php` 的属性后，接口字符串看起来如下：

```
mysql://test:test@localhost/test
```

如果第 6 行的连接策略成功，则会创建一个 `DB` 对象。它包含了访问数据库的程序以及关于该数据库关联状态的大部分数据。

#### 查询

它包含的技术之一称为 `query`。`query` 方法的预期与 PHP 的 `query` 函数相似，因为它接收一个 SQL 语句。

# 第 12 章：处理表单

HTML 结构提供了一种从客户端向服务器发送重要信息的方法，可以在服务器对其进行处理。你将大量利用在书的第一部分中学到的 PHP 语言来处理和验证表单信息。

我们将从构建一个基础表单开始，并弄如何在客户端提交后获取字段中的数据。我们将检查可以设置在表单以及隐藏属性上的基本元素类型。显然，PHP 代码将与这些组件结合。

表单运行于两个阶段的过程。表单必须展示给客户端。然后用户输入数据并提交表单。每个表单都有一个 `action` 属性，指定当客户端提交时加载哪个页面来处理信息。通常，这就是最初创建表单的同一个文档。PHP 代码只需验证是否有客户端数据提交该页面的请求，以确定该文档是被用来生成表单的还是生成其信息的。

在各种应用程序中，查询数据库是至关重要的。无论是查找帖子、客户端还是博客，它都能让用户的生活变得简单得多。在数据库级别，还有许多方法可以处理查询并返回结果。

## 12.1 构建表单

由于你需要一个让客户端输入查询问题的地方，我们应该从构建一个用于处理客户端信息的表单开始。每个表单都必须包含这些基本部分：

- 带有 `method` 关键字属性的表单类型
- 一个或多个带有 `name` 标签属性的数据组件
- 带有 `action` 关键字属性的提交去向

我们应该构建一个基础的表单，其中包含一个名为 `hunt` 的内容信息字段和一个简单的按钮，如示例 10-1 所示。

将示例 10-1 中的代码放在 Web 服务器上 Web 可访问目录（例如，根目录）中的一个名为 `simple.php` 的文件中。严格来说，表单只是简单地由 HTML 表征的，但我们在第 6 行使用了一些 PHP 代码来引用全局变量数组 `$_SERVER` 中的 `"PHP_SELF"` 组件。这为处理表单信息所需的当前 PHP 文档名称提供了另一种路径。

示例 10-1 中的表单允许你从客户端获取用于搜索的查询字符串。注意我们在内容所在的地方包裹了一个 `name` 标签；这使得表单更易用。点击“Search:”消息会将光标移动到 `hunt` 字段。在第 6 行，我们将表单的提交方法设置为 `GET`。

这样做是为了确保客户端可以收藏他们的搜索结果，而不需要返回页面并重新输入他们的信息。第 8 行通过定义内容字段完成了大部分工作。

从你的程序中访问 `simple.php` 文档将创建与图 10-1 类似的表单。这并不特别有用，因为你提交的任何值都会再次返回相同的表单，但我们将处理这个问题。

![](img/8e0a31fe30a159a13fdfed13405b5ed_156_0.png)

示例表单在浏览器中的显示方式

### 默认值

在对数据库执行查询时，你可能可能需要在表单中确实设置一些默认值。这是非常有用的，例如在价格范围内进行查找时。客户端通常不喜欢输入所有属性，这在搜索时会让操作变得简单得多。通常，表单元素的默认值位于 `value` 属性中；另一方面，复选框有一个使用 `checked` 关键字的特殊情况。

### 输入类型

有各种类型的数据，你认为使用哪种对你好呢？单选按钮、复选框、内容、数据、文本区域、按钮……噢天哪！我们将描述每一个信息选项。

#### 文本框

在管理来自客户端的信息时，你可能需要一个内容字符串。使用 `text` 类型组件从客户端获取这些字符串。`name` 属性对于表单提交后处理信息是必要的，因为它指定了如何引用该属性。当它出现在程序中时，`size` 参数决定了内容框的长度。`maxlength` 参数决定了可以在字段中输入的最大字符数。结构如下：

```html
<input type="text" name="name" size="显示大小" maxlength="允许的最大字符数"/>
```

#### 复选框

当你需要给客户端提供几个不同的选项时，复选框很有帮助，特别是当他们被允许单独选择每个决定时。只有当你有几个选项提供给客户端时才使用复选框；通常，你需要使用另一种类型的数据。这被称为 `select`（选择框），我们稍后会讨论。对于复选框，将信息类型设置为 `checked`。`name` 和 `value` 属性也是必须的。如果 `value` 设置为 `checked`，则复选框理所当然是被选中的。

## 12.2 模板

每当你从客户端获取客户端信息时，你都应该对其进行处理。如果你不处理客户端信息，可能会导致许多问题——包括潜在的安全风险。

处理数据并不复杂。我们将概述最广泛使用的用于清理客户端信息的 PHP 函数。

```php
$connection =
DB::connect("mysql://$db_username:$db_password@$db_host/$database");

if (DB::isError($connection)){ // check for join mistakes
    die("Could not interface with the database: <br>" . DB::errorMessage($connection));
}
}
```

### 模板

模板将负责页面呈现或外观的 HTML 代码与负责业务逻辑信息的 PHP 代码分离。一旦完成分离，对于正在学习 HTML 可能还有 CSS 的人来说，修改布局将变得不再困难，而无必苦苦担心弄坏 PHP 代码。此外，PHP 代码可以专注于信息本身，而不是参与到展示细微元素中。

使用模板有许多不同的关注点。例如，如果你在模板中编写了错误，错误将直接从模板中返回。模板本身大部分可以堆叠到 Web 程序或图形化 Web 开发工具中（例如 Dreamweaver），因为它们在处理后看起来就像页面的最终状态。模板为用于展示的核心编程元素提供了支持，例如能够判断页面的某个区域是否可见。

显而易见，没有什么是是完美的；模板也有两三个缺点。模板增加了需要维护的文件数量。它们会带来少量的额外处理时间。它们还强制要求引入模板引擎并设置注册表。要使用 Smarty（一个著名的模板引擎），你至少需要运行 PHP 4.0.6 版本。

### 模板引擎

网上有很多模板包可用。每个包都有自己的模板引擎来准备模板，并在各种情况下尽可能使其高效。无论你使用哪种模板引擎，通常都会遵循相同的步骤步骤：

1. 获取你的数据。
2. 对模板中使用的每个属性调用模板函数。
3. 使用模板函数显示模板。

我们将通过几个示例快速过一遍这一过程。可用的模板引擎之一是 Smarty，稍后图 10-16 所示。Smarty 有许多元素；但我们最关注的是基本的模板引擎功能。

### 安装

虽然引入 Smarty 并不像引入和设计 Apache、PHP 或 MySQL 那样令人惑，但它值得某些关注：

#### 应用级索引

对于每个你想要使用 Smarty 的应用程序，你必须设置一组四个索引。这四个索引分别用于格式、编译后的模板、保留模板和设计记录。尽管你可能不会使用这些特性，但你应该设置这些索引以防万一：

1. 在你的归档根目录下创建一个名为 `myapp/` 的索引。（你可以根据需要命名，但在本文后续内容中，我们将统称为 `myapp/`。）
2. 在刚创建的目录内创建一个名为 `smarty` 的注册表（`myapp/smarty`）。
3. 在刚创建的 `smarty` 注册表中，再创建四个注册表：`formats`、`templates_c`、`store` 和 `config`。确保 Web 服务器对你在上一步创建的 `templates_c` 和 `store` 索引具有访问权限。

你只需要创建一个和一个 PHP 文件来尝试一下。

# 第 13 章：实战 PHP

在本章中，我们将开始尝试编写 PHP 程序时执行的更常见的任务，例如处理字符串，以及显示字符串、日期和时间的不同格式。我们还将向你演示处理 PHP 程序创建或读取的文档的行业标准。此外，我们还会提供一个案例，说明如何让客户端传输文件并在将其打开之前接受其内容。传输文件很有帮助，但如果文件没有经过合法接收，可能会成为安全隐患。

在构建页面的 HTML 输出时，我们在字符串处理上花费了大量精力。PHP 有一系列丰富的函数，可以完成你可能更改字符串实例的任何任务。你还应该能够处理日期和时间。对日期进行任何形式的加或减法（例如，根据属性跳过很长时间），如果没有专门用于处理日期的函数提供帮助，很快就会变得复杂。

## 13.1 字符串函数

由于你本质上在使用两种都能帮助操作字符串的语言，因此你需要了解 PHP 和 MySQL 中的字符串函数。你可能会认为，根据具体情况，在查询中或 PHP 中修改字符串更为合适。你将学习到以下字符串操作：

- 格式化字符串以便显示
- 计算字符串长度
- 将字符串的大小更改为大写或小写
- 在字符串内部搜索字符串并返回匹配的位置
- 只返回字符串的一部分，即子字符串

我们将从格式化字符串开始，因为这将帮助你完成剩余的所有主题。

### 用于显示的字符串格式化

在这一方法中，你一直在使用 `echo` 和 `print` 来显示字符串而无需做太大修改。

你会发现名为 `sprintf` 和 `printf` 的函数。如果你熟悉其他编程语言（例如 C），你会发现这些函数的工作方式与其他地方相同。如果你以前没有使用过它们，请不要担心。

#### 使用 printf

`printf` 函数通过将其第一个参数作为一个特殊字符串来符合预期。它的主要区别是 `sprintf` 返回一个字符串，而 `printf` 显示输出。

#### 填充

你还可以为每个字段指定填充。要在字段左侧填充零，可以在转换符号后跟一个零，然后是要填充排序器的零的数量，如示例 11-4 所示。如果参数输出使用的空间少于你指定的数字，则会在左侧填充零。

PHP 提供了几个函数让你了解不同的记录属性。PHP 能够从你的框架记录中读取信息，并向记录中写入信息。另一方面，它的功能并不止于此。它还配备了一套完整的、高亮的文档和目录控制 API，允许你：

- 查看和修改文档特征
- 读取并列出目录内容
- 修改文档权限
- 将文档内容检索到各种本地信息结构中
- 根据特定示例搜索文档

这种通过 API 进行的大部分文档控制功能都是强大且灵活的。PHP 拥有大量的特有命令，包括所有的文档控制命令。

## 13.3 文件操作

既然你知道一个文件存在，你可能认为你已经完成了，但实际上并非如此。仅仅文件在那里并不意味着你可以读取、写入或执行它。要检查这些属性，请使用 `is_readable` 检查读取权限，使用 `is_writable` 检查写入权限，并使用 `is_executable` 检查执行文件的能力。每个函数都接受一个文件名作为参数。除非你确定文件与你的脚本在同一个目录中，否则你必须在文件名中指定文件的完整路径。你可以使用连接符将路径和文件名结合在一起，例如：

```php
$file_name = $path_to_file . $file_name_only;
```

### URL 包装器

PHP 构建了两个用于文件系统函数的 URL 约定，包括 `open` 和 `duplicate`。除了这两个包装器外，从 PHP 4.3.0 开始，你可以利用 PHP 脚本和 `stream_wrapper_register` 创建自己的包装器。默认包装器是 `file://`，用于 PHP，并且它是本地文件系统。如果你指定一个相对路径（即不以 `/`、`\` 或 Windows 驱动器号如 `C://` 开头的路径），则该路径相对于当前工作目录。

通常情况下，这是脚本所在的地方，除非显然它被更改了。通过一些函数，例如 `fopen` 和 `file_get_contents`，`include_path` 也可以用来查找相对路径。

## 13.4 调用系统调用



对于一个基于 PHP 的网站来说，允许文件传输是一个非常基本的要求。例如，在一个网络博客页面上，客户端可能需要传输一张图片来配合他的帖子。

由于你将在第 17 节中计划一个网站，我们将逐步介绍传输文件的步骤。PHP 允许你通过数据结构来实现此。

当你使用文件传输表单字段时，客户端程序会弹出一个文件选择对话框，所以你不需要担心处理这一点。在文件传输字段中包含的代码是 `<input type="file" name="file">`。你应该在结构标签中包含 `enctype="multipart/form-data"`。这允许随表单提交发送文件。

## 第 14 章：XHTML

既然你已经学习使用 PHP 和 MySQL 构建动态页面的基础，早点研究构建你网站页面基础的 HTML 标记的变化。你将了解到 XHTML、它的要求以及为什么它值得投入额外的精力来创建。请记住，为了从你的 PHP 脚本创建高质量的 Web 内容，标记必须符合标准。将 XHTML 输出视为在 PHP 和数据库函数处理后请求页面时的完成品。我们还将检查你的脚本生成的 XHTML 输出以捕获任何错误。

XHTML 代表可扩展超文本标记语言（Extensible Hyper-Text Markup Language）。XHTML 是一种类似于 HTML 的标记语言，但根据 XML 的要求，它具有更严格的语法。HTML 是基于 SGML 的，SGML 虽然灵活但处理起来复杂，而 XML 简化了 SGML，使其在稍微灵活的情况下更容易转换。XHTML 语言结构看起来非常像 HTML 语言，使用更明显且较少的符号（`<`、`>`）来描述标签，但对标签如何传递有更严格的要求。满足这些语法要求的 XHTML 文被称为良好的（well-formed），而满足语言结构以及 DTD 中包含的辅助规则 HTML 文被称为有效的。可以使用任何标准 XML 库自然处理 XHTML，而大多数 HTML 使用通常使用为 HTML 处理修改的宽松解析器。你可以从许多方面将 XHTML 视为 HTML 和 XML 的交汇，因为它是两者的重构。展示变化的最简单方法是显示一个 HTML 文档及其对应的 XHTML 文档。首先，这是一个简单的 HTML 4.0 文档：

这里发生了什么变化？

- 在开头有另一个 XML 声明，标识文档为 XML 1.0，使用 UTF-8 字符编码。如果你的文档使用 UTF-8 编码（或 ASCII，它是其子集），你可以完全跳过它。
- `DOCTYPE` 呈现发生了细微变化。
- 所有的 HTML 标记现在都是小写的。（XHTML 规范要求小写。）
- `html` 元素包含一个 `xmlns` 属性（描述本文后面描述的 XHTML 命名空间），以及一个 `xml:lang` 属性，补充了用于 XML 处理器的 `lang` 属性。
- `<BR>` 标签现在是 `<br/>` 标签，结尾的斜杠（`/`）表示它是一个“空元素”且不会有结束标签。
- 有另一个结束标签 `</p>`，它结束了 `body` 内部第一行的 `<p>`。XHTML 不允许你在没有结束标签的情况下拥有开始标签，除非使用用于 `<br/>` 的空元素文档。尽管这太短了无法展示很多，但打开和关闭标签的要求也需要是对称的；`<b>` 是正确的，而 `<i>` 是错误的。

交付更稳定的记录。虽然更严格的错误检查听起来像是一种负担，但该提案建议程序发布错误，而不是试图渲染形状错误的内容，从而通过促使创建者纠正其错误来解决问题。

## 14.2 XHTML 和 XML 命名空间

XML 具有极强的非排他性。它描述了标点符号和基本结构，但对查询没有过多规定，例如哪些组件和属性应该命名。任何需要创建 XML 词汇表的人都可以这样做，而无需联系 W3C 或标准机构。这产生了一个问题：一个连接中的 `Title` 含义可能与另一个连接中的 `Title` 完全不同。[XML 命名空间]规范（可以在 http://www.w3.org/TR/REC-xml-names/ 处找到）提供了一套设计人员可以使用的系统，利用统一资源标识符（URIs）来识别特定的词汇表。URIs 是著名的统一资源定位符（URLs）和统一资源名称（URNs）的结合。从 XML 命名空间的角度来看，URIs 非常有用，因为它们将一种易用的语法与所有权的概念结合在一起。W3C 声称以 `http://www.w3.org/` 开头的名称，因此使用它们作为标识符是非常合适的。在没有混合其他词汇表的纯净 XHTML 中，通过使用 `xmlns` 属性在 `html` 元素上声明命名空间。例如：

```html
<html xmlns="http://www.w3.org/1999/xhtml" >
```

命名空间 URI `http://www.w3.org/1999/xhtml` 现在适用于 `html` 组件本身以及任何子组件，只要它们没有自己的特定的 `xmlns` 属性或或以前缀和冒号开头的名称。

## 14.3 XHTML 版本

自诞生以来，XHTML 标准一直在演进。目前正在使用的有三种值得关注的形式：

### XHTML 1.0

XHTML 1.0 的内容与 HTML 4.01 相同，但它要求使用 XML 语法。

### XHTML 1.1

XHTML 1.1 是 1.0 版本基于模块的重新格式化形式。它是严格的，因为它使用了模块化安排，这些模块是从《XHTML 模块化》中描述的更大部分集中选出的。这是 W3C 的建议，提供了一个模块化结构，模块有一组标准集合和需要符合 XHTML 环境的各种定义。任何部署的 HTML 元素，例如演示组件和框架集，已从此变体中移除。所有基于程序的演示都由层叠样式表（CSS）控制。此外，1.1 包含了 Ruby 标记支持，这是东亚语言所必需的。

## 14.4 使用 PHP 创建 XHTML

从你的 PHP 代码生成 XHTML 并不比制作普通的 HTML 困难（参见示例 14.4）。

示例 14.4. 从 PHP 创建 XHTML 记录

```php
<?php
// 询问程序是否接受 application/xhtml+xml MIME 类型
// 这是由于 IE 的考虑
if(strstr($_SERVER["HTTP_ACCEPT"],"application/xhtml+xml")) {
    header('Content-Type: application/xhtml+xml; charset=utf-8');
}
else {
    header('Content-Type: text/html; charset=utf-8');
}
// 创建文档类型定义
$doctype = '<?xml version="1.0" encoding="UTF-8"?>';
$doctype .= '<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN">';
$doctype .= ' <html SYSTEM "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">';
// 创建头部
$head = '<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">';
$head .= "<head>";
$head .= "<title>Document Declaration Example</title>";
$head .= "</head>";
// 创建正文内容
$body = "<body>";
$body .= " <p>The substance of the page goes here.</p>";
$body .= "</body>";
// 创建页脚
$footer = '</html>';
// 全部输出
echo $doctype;
echo $head;
echo $body;
echo $footer;
?>
```

由于我们掌握了 XHTML（它增强了标准 HTML 和你网站的兼容性），我们准备好进入将 PHP 和 MySQL 过程相结合的概念。在接下来的章节中，我们将讨论如何从 PHP 内部修改 MySQL 中的数据库对象和信息。我们还将学习创建动态 HTML 连接，以对数据库中的特定数据执行操作。

## 第 15 章：修改 MySQL 对象和 PHP 数据

## 15.1 从 PHP 修改数据库对象

SQL 查询字符串仍然提供数据库命令的基本工具。你可以简单地使用标准 SQL 以与执行查询相同的方式来创建和修改数据库对象。有时，你需要在 PHP 内部创建数据库对象。我们将从创建表开始，这是一个创建对象的示例。

## 15.2 操作表数据

我们之前创建了 `books` 和 `authors` 表，但还没有创建 `buyers` 表。我们将使用示例 15.1 所示的 PHP 创建它。

示例 15.1. 从 PHP 创建表

```php
<?php
include('db_login.php');
// ... (连接逻辑)
$query = "CREATE TABLE buyers (
    buyer_id int NOT NULL AUTO_INCREMENT, 
    username varchar(50) NOT NULL,
    email varchar(50) NOT NULL,
    PRIMARY KEY (buyer_id)
)";
$result = $connection->query($query);
if (DB::isError($result)) {
    die("Could not create table: <br/>". $result->error->message);
}
echo "Table created successfully!";
?>
```

### 删除表

要删除表，你将使用 `DROP` 命令。

示例 15.2. 从 PHP 删除表

```php
<?php
include('db_login.php');
// ... (连接逻辑)
$query = "DROP TABLE buyers";
$result = $connection->query($query);
if (DB::isError($result)) {
    die("Could not drop table: <br/>". $result->error->message);
}
echo "Table dropped effectively!";
?>
```

```php
$connection->disconnect();
?>
```

# 使用嵌入链接显示结果

您可能需要让网页浏览器具备点击超链接的能力，以便启动与查询结果中当前行相关的活动。您可以通过查询结果显示在屏幕上时，包含指向查询结果的 URL 链接来实现。这些链接包含一个指向该行的唯一标识符以及处理该活动的脚本。

链接指向的 PHP 脚本主要根据传递给它的唯一标识符对数据库进行查询。您可以执行的活动类型范围广泛，从格式化或删除某行，到从相关表中获取详细信息（例如，书籍标题的作者）。
