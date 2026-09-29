

# Oracle SQL 入门指南

书籍及封面设计：Mona Setiadi

技术审核员：Budi Kurniawan

索引编制：Chris Mayle

数值函数....................................................................................................85

字符函数..................................................................................................88

日期时间函数..................................................................................91

与NULL相关的函数.........................................................................................92

总结................................................................................................................96

# 第10章：PL/SQL...............................................................................................97

逐行处理.........................................................................................................97

If-Then-Else 决策逻辑..............................................................................101

用户定义函数.............................................................................105

总结................................................................................................................106

字典................................................................................................................107

目录视图......................................................................................108

表视图......................................................................................................108

列视图......................................................................................................109

过程视图......................................................................................110

源码视图......................................................................................110

总结................................................................................................111

Oracle SQL 初学者教程

## 引言

欢迎学习 Oracle SQL 初学者教程。如果你想以简单的方法学习 SQL，这本书非常适合你。SQL 代表结构化查询语言（读作 s-q-l），它是你与关系型数据库管理系统（RDBMS）交互的标准语言。本书使用 Oracle 数据库的免费版本来展示 SQL 是如何工作的。

## SQL 概述

SQL 最初由 IBM 在 20 世纪70 年代开发，1986年由美国国家标准（ANSI）正式制定。从那时起，SQL 标准修订了七次。本书中的示例使用 Oracle 数据库 11g Release 2，它符合 SQL:2008 标准。该标准是 SQL:2011 的早期版本。

SQL 由数据定义语言（DDL）和数据操作语言（DML）组成。DDL 用于创建、删除和修改表和其他对象的结构。DML 用于插入、检索和更新表中的数据。

许多数据库厂商实现的 SQL 版本并非100% 符合标准。他们经常为 SQL 添加独特的特性，导致产生了 SQL 方言。例如，以下是 Oracle 和 MySQL 的一些区别：

- `CREATE TABLE` 语句中的 `AS` 关键字在 Oracle 中是强制的，但在 MySQL 中可选。

- Oracle `INSERT` 语句只能插入一行；MySQL `INSERT` 语句可以插入多行。

- Oracle 支持 `UNION`、`INTERSECT` 和 `MINUS` 运算符，而 MySQL 只支持 `UNION`。

- Oracle 的 `PL/SQL` 在 MySQL 中的等价物是存储过程（MySQL 没有为其过程扩展命名）。`PL/SQL` 的函数比存储过程多。

由于这些方言的存在，为一种 RDBMS 编写的 SQL 语句可能在其他 RDBMS 中运行。

## 关于本书

本书由十一章和三个附录组成。本节提供了每个章节和附录的概述。

第一章“存储和维护数据”开始介绍数据如何在关系型数据库中进行存储和维护。在本章中，你将学习如何使用 SQL `INSERT`、`UPDATE` 和 `DELETE` 语句。

第二章“基础查询”解释了如何使用 `SELECT` 语句构建查询。

第三章“查询输出”展示了如何在显示数据库数据列之外格式化查询输出。

第四章“分组”解释了什么是分组、如何创建分组以及如何对分组应用聚合函数。

第五章“连接”讨论了用于从多个表查询数据的 `JOIN` 子句。

第七章“复合查询”讨论了用于组合多个查询输出的集合运算符。

第八章“视图”讨论了视图，即创建并存储在数据库中的预定义查询。

第九章“内置函数”讨论了 Oracle 数据库中一些常用的内置函数。

第十章“PL/SQL”引入了 Oracle 的 `PL/SQL` 编程语言。`PL/SQL` 扩展了 SQL。

第十一章“数据字典”展示了如何使用数据字典（数据库的元数据）来查找有关数据库的信息。

附录 A“安装 Oracle Database XE”是安装 Oracle 表达式版并准备尝试书中示例的指南。

附录 B“Oracle 内置数据类型”提供了 Oracle 内置数据类型的列表。

最后，附录 C“索引”涵盖了 Oracle 数据库中提供的各种索引技术。

## 编码规范

SQL 不区分大小写。但在书中，诸如 `CREATE` 和 `SELECT` 等 SQL 保留字以及 `COUNT` 和 `MAX` 等关键字使用大写。要查找完整的 SQL 保留字，请参考 Oracle SQL 手册。非保留字（如表名和列名）使用小写。

在本书示例中，单词或表达式之间使用单个空格。允许额外的空格且不影响结果。

## 代码下载

随本书的示例可以从以下网站下载：

```
http://books.brainynsoftware.com/download
```

# 第一章

## 存储和维护数据

关系型数据库（如 Oracle 数据库）中的数据存储在表中。例如，一个非常简单的销售数据库可能有四张表，分别存储产品、客户、供应商和客户订单的数据。

当你向表中添加一条数据记录时，该记录被存储为表的一行。记录包含字段。例如，一个产品记录可能有四个字段：产品代码、名称、价格和发布日期。存储在产品表中的所有记录必须具有相同的字段。每个字段都是表的一列。

本章将向你展示如何使用 SQL 语句来存储和维护数据。本章的主要目标是让你体验使用 SQL 操作。

为了测试示例，你需要一个良好的 Oracle 数据库。附录 A“安装 Oracle Database XE”展示了如何安装 Oracle 数据库表达式版（XE）并为尝试书中示例做好准备。该附录还展示了如何使用 SQL*Plus 执行你的 SQL 语句。如果你没有良好的 Oracle 数据库，应该先阅读此附录。

### 选择要使用的数据库

你需要一个数据库来存储数据。当你安装 Oracle Database XE 时，安装过程中创建一个名为“XE”的数据库。要使用该数据库，请运行 SQL*Plus 并像附录 A“安装 Oracle Database XE”中描述的那样发布 `CONNECT` 命令。

# Oracle SQL: 入学者教程

### 创建表

在向数据库存储数据之前，你必须先为你的数据创建一个表。你通过使用 SQL `CREATE TABLE` 语句来实现这一点。你创建的表将存在于你当前连接的数据库中，在本例中，该数据库是 XE。

`CREATE TABLE` 语句的语法如下。

```
CREATE TABLE table
  column_1 data_type_1,
  column_2 data_type_2,
  ...
  PRIMARY KEY (columns);
```

列表 1.1 显示了一个创建一个包含四列的产品表的 `CREATE TABLE` 语句。

### 列表 1.1：创建一个包含四列的表表

```
CREATE TABLE product
  p_code VARCHAR(6),
  p_name VARCHAR(15),
  price NUMBER(4,2),
  launch_dt DATE,
  PRIMARY KEY (p_code);
```

这四列具有三种不同的数据类型。如下：

- `VARCHAR2(n)` - 变长度字符串，最大 `n` 个字符。

- `NUMBER(p, s)` - 精度为 `p`、标度为 `s` 的数字。`price` 列的类型为 `NUMBER(4,2)`，可以存储 -99.99 到 +99.99 之间的数字。

- `DATE` – 日期

注意

附录 B，“Oracle 内置数据类型”提供了完整的 Oracle 数据类型列表。

在创建表时，你应该始终添加主键，尽管主键是可选的。主键是唯一标识表中每行的列或一组列。在列表 1.1 的 `CREATE TABLE` 语句中，`p_code` 字段将是产品表的主键。

另请注意，SQL 语句必须以分号（号结束；

## 添加数据

一旦你拥有了表，就可以使用 `INSERT` 语句向其添加数据。`INSERT` 语句的语法如下：

```
INSERT INTO table
(column_1,
column_2,
...)
VALUES (value_1,
value_2,
...);
```

例如，列表 1.2 显示了一个向产品表插入一行的 SQL 语句。

列表 1.2：向产品表插入一行

```
INSERT INTO product
( p_code, p_name, price, launch_dt)
VALUES ( 1, 'Nail', 10.0, '31-MAR-2013');
```

执行列表 1.2 中的语句后，你的产品表将有一行数据。你可以使用此语句查询你的表。

# Oracle SQL: 入学者教程

```
SELECT * FROM product;
```

查询结果如下。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |

|---|---|---|---|

| 1 | Nail | 10.00 | 31-MAR-13 |

你可以在一个 `INSERT` 语句中只添加一行。列表 1.3 中的五个 `INSERT` 语句向产品表添加了五行。

### 列表 1.3：向产品表添加五行数据

```
INSERT INTO product (p_code, p_name, price, launch_dt)
VALUES (2, 'Washer', 15.00, '29-MAR-13');
INSERT INTO product (p_code, p_name, price, launch_dt)
VALUES (3, 'Nut', 15.00, '29-MAR-13');
INSERT INTO product (p_code, p_name, price, launch_dt)
VALUES (4, 'Screw', 25.00, '30-MAR-13');
INSERT INTO product (p_code, p_name, price, launch_dt)
VALUES (5, 'Super Nut', 30.00, '30-MAR-13');
INSERT INTO product (p_code, p_name, price, launch_dt)
VALUES (6, 'New Nut', NULL, NULL);
```

执行列表 1.3 中的语句后，你的产品表将包含这些行。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |

|---|---|---|---|

| 1 | Nail | 10.00 | 31-MAR-13 |

| 2 | Washer | 15.00 | 29-MAR-13 |

| 3 | Nut | 15.00 | 29-MAR-13 |

| 4 | Screw | 25.00 | 30-MAR-13 |

| 5 | Super Nut | 30.00 | 30-MAR-13 |

| 6 | New Nut | NULL | NULL |

现在发布 `COMMIT` 命令来持久化（确认存储）额外的五行。

```
COMMIT;
```

## 更新数据

你指定 `UPDATE` 语句来更新现有数据的一个或多个列。你可以更新表中的所有行或某些行。

`UPDATE` 语句的语法如下：

```
UPDATE table_name
SET column_1 = new_value_1,
    column_2 = new_value_2,
    ...
[WHERE condition];
```

你在 `WHERE` 子句中指定要更新的行。如果没有 `WHERE` 子句，所有行都将被更新。如果有 `WHERE` 子句，只有符合条件的行会被更新。如果没有行符合条件，则没有行会被更新。

```
SELECT * FROM table;
```

星号（`*`）表示表中的所有列。例如，列表 2.1 显示了一个从 `product` 表中查询所有数据的 SQL 语句。

### 列表 2.1：查询所有产品数据

```
SELECT * FROM product;
```

执行该查询将得到如下结果。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |

|---|---|---|---|

| 1 | Nail | 10.00 | 31-MAR-13 |

| 2 | Washer | 15.00 | 29-MAR-13 |

| 3 | Nut | 15.00 | 29-MAR-13 |

| 4 | Screw | 25.00 | 30-MAR-13 |

| 5 | Super_Nut | 30.00 | 30-MAR-13 |

| 6 | New Nut | NULL | NULL |

## 选择特定列

要选择特定的列，请在 `SELECT` 子句中列出这些列。按照你希望在输出表中看到的顺序编写这些列。例如，列表 2.2 中的 `SELECT` 语句查询了 `product` 表中的 `p_name` 和 `price` 列。

### 列表 2.2：查询特定列

```
SELECT p_name, price FROM product;
```

查询将返回所有包含 `p_name` 和 `price` 列的行。以下是查询输出。

| P_NAME | PRICE |

|---|---|

| Nail | 10.00 |

| Washer | 15.00 |

| Nut | 15.00 |

| Screw | 25.00 |

| Super_Nut | 30.00 |

## 使用 WHERE 选择行

要查询特定的行，请使用 `WHERE` 子句。回想 SQL `SELECT` 语句具有以下语法。

```
SELECT column_names FROM table_name [WHERE condition];
```

例如，列表 2.3 中的 SQL 语句查询了 `product` 表中 `price = 15` 的 `p_name` 和 `price` 数据。

- 列表 2.3：查询特定行

```
SELECT p_name, price FROM product WHERE price = 15;
```

查询将返回价格为 15 的行，在这种情况下是 Washer 和 Nut。查询输出如下。

```
P_NAME          PRICE
------------ ----------
Washer          15.00
Nut             15.00
```

列表 2.3 中 `WHERE` 条件中的等号（`=`）是比较运算符之一。表 2.1 显示了所有的比较运算符。

| Operator | Description |

| --- | --- |

| = | 等于 |

| < | 小于 |

| > | 大于 |

| <= | 小于等于 |

| >= | 大于等于 |

| != | 不等于 |

表 2.1：比较运算符

作为另一个例子，列表 2.4 显示了一个使用不等于（`!=`）运算符的 `WHERE` 子句。

### 列表 2.4：使用 != 比较运算符

```
SELECT p_name, price FROM product WHERE p_name != 'Nut';
```




查询将返回所有 `p_name` 不为 `Nut` 的行。在这种情况下，查询输出如下。

| P_NAME | PRICE |
| --- | --- |
| Nail | 10.00 |
| Washer | 15.00 |
| Screw | 25.00 |
| Super_Nut | 30.00 |
| New Nut | NULL |

## 复合条件

列表 2.4 中的条件 `p_name != 'Nut'` 被称为谓词。使用 `AND` 和 `OR` 逻辑运算符，你可以将谓词组合起来形成复合条件。查询将只返回满足复合条件的行。

`OR` 逻辑运算符的规则在表 2.2 中。

| Left condition | Logical operator | Right condition | Compound condition |
| --- | --- | --- | --- |
| True | OR | True | True |
| True | OR | False | False |
| False | OR | True | True |
| False | OR | False | False |

表 2.2：OR 规则

原则上，如果两个进行 `OR` 连接的条件中任何一个为真，则 `OR` 条件的结果为真；否则，如果没有一个条件为真，则复合条件为假。`AND` 逻辑运算符的规则在表 2.3 中。

| Left condition | Logical operator | Right condition | Compound condition |
| --- | --- | --- | --- |
| True | AND | True | True |
| True | AND | False | False |
| False | AND | True | False |
| False | AND | False | False |

表 2.3：AND 规则

基本上，只有当两个进行 `AND` 连接的条件都为真时，`AND` 条件的结果才为真；否则结果为假。例如，列表 2.5 中的语句 `WHERE` 子句中包含三个谓词。

### 列表 2.5：带有三个谓词的查询

```sql
SELECT *
FROM product
WHERE (launch_dt >= '30-MAR-13'
OR price > 15)
AND (p_name != 'Nail');
```

第一个条件 `launch_dt >= '30-MAR-13' OR price > 15` 的结果对于 `Nail`、`Screw` 和 `Super_Nut` 行为真。查询将只返回满足复合条件的行，在这种情况下是 `Screw` 和 `Super_Nut`。查询输出如下。

```
P_NAME          PRICE
------------ ----------
Screw          25.00
Super_Nut       30.00
```

例如，列表 2.10 中的查询使用 `IN` 运算符来选择所有价格在列表 (10, 25, 50) 中的列。

### 列表 2.10：使用 IN 运算符

```
SELECT * FROM product WHERE price IN (10, 25, 50);
```

列表 2.10 查询的输出如下。

```
P_CODE P_NAME    PRICE LAUNCH_DT
------ ---------- -----------
1      Nail       10.00 31-MAR-13
4      Screw      25.00 30-MAR-13
```

## LIKE 运算符

`LIKE` 运算符允许你指定一个不精确的相等条件。其语法如下。

通配符字符可以是百分号 (`%`) 用于表示任意数量的字符，也可以是下划线 (`_`) 用于表示任意字符的单个出现。

例如，列表 2.11 中的查询使用 `LIKE` 运算符来查找名称以 `N` 开头并跟两个其他字符的产品，以及名称以 `Sc` 开头且长度任意的产品。

### 列表 2.11：使用 LIKE 运算符

```
SELECT * FROM product WHERE p_name LIKE 'N__' OR p_name LIKE 'Sc%',
```

列表 2.11 查询的输出如下。

```
P_CODE P_NAME    PRICE LAUNCH_DT
------ ---------- -----------
3      Nut        15.00 29-MAR-13
4      Screw      25.00 30-MAR-13
```

尽管你可以在数字列上使用 `LIKE`，但它主要用于字符串字符串的列。

## 转义通配符字符

如果你在 `LIKE` 运算符中指定的字符串包含下划线或百分号，SQL 将其视为通配符字符。例如，如果你想查询名称中包含下划线的产品，你的 SQL 语句将如列表 2.12 所示。

### 列表 2.12：LIKE 字符串中的通配符 _

```
SELECT * FROM product WHERE p_name LIKE '%_';
```

如果你执行列表 2.12 中的查询，该查询将返回所有行，而不仅仅是 `Super_Nut`，因为 `LIKE` 运算符中的下划线被视为通配符字符，即任意一个字符。列表 2.13 通过在通配符前加上 `ESCAPE` 字符来解决这个问题，这意味着 `LIKE` 运算符中转义字符 `\_`（反斜杠）之后的任何字符都将被视为字符，而不是通配符字符。现在，只返回 `p_name` 包含下划线的行。

### 列表 2.13：转义通配符字符 _

```
SELECT * FROM product WHERE p_name LIKE '%\_% ESCAPE '\';
```

列表 2.13 中的查询将产生以下输出。

```
P_CODE P_NAME      PRICE LAUNCH_DT
---------------------------------
5 Super_Nut      30.00 30-MAR-13
```

## 组合 NOT 运算符

你可以将 `NOT` 与 `BETWEEN`、`IN` 或 `LIKE` 组合以反转它们的条件。例如，列表 2.14 中的查询使用了 `NOT` 配合 `BETWEEN`。

### 列表 2.14：在 BETWEEN 中使用 NOT

```
SELECT * FROM product WHERE price NOT BETWEEN 15 AND 25;
```

执行列表 2.14 中的查询将得到此结果。

| P_CODE P_NAME | PRICE | LAUNCH_DT |
| --- | --- | --- |
| 1 Nail | 10.00 31-MAR-13 |
| 5 Super_Nut | 30.00 30-MAR-13 |

处理 `NULL`（一个 SQL 保留字）表示数据的缺失。`NULL` 适用于任何数据类型。它不等同于数字零、空字符串或 0000/00/00 日期。你可以在创建表的 `CREATE TABLE` 语句中指定某列是否可以为 null。

对 `NULL` 应用任何比较运算符的结果**总是** `NULL`。你只能使用 `IS NULL` 或 `NOT NULL` 运算符来测试列是否为 `NULL`。

考虑列表 2.15 中的查询。

### 列表 2.15：在 NULL 上错误使用等号运算符

```
SELECT * FROM product WHERE price = NULL;
```

执行列表 2.15 中的查询没有产生输出。事实上，你会得到以下消息。

```
no rows selected
```

另一个例子是考虑使用 `IS NULL` 的列表 2.16 中的查询。

### 列表 2.16：使用 IS NULL

```
SELECT * FROM product WHERE price IS NULL;
```

查询输出如下。

| P_NO | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 6 | New Nut | NULL | NULL |

> 注意

第 6 章“内置函数”讨论了你可以用于测试列是否为空的函数。

## 总结

在本章中，你学习了使用 `SELECT` 语句的基础查询知识。

在下一章中，你将学习如何格式化查询输出。

# 第 3 章

## 查询输出

第 2 章“基础查询”中的所有查询都返回了包含源表列的行。然而，输出行也可以包含字符串或数字表达式。在本章中，你将学习如何格式化查询输出。

### 列别名

默认情况下，输出列与表列相同。但是，你可以使用不同的名称给它们命名。使用别名的语法如下：

```
SELECT column_name AS alias FROM table;
```

别名可以由一个或多个单词组成。例如，你可以用引号将它们括起来。

### 列表 3.1：使用别名

### 表达式

除了乘法运算符 (`*`) 之外，你还可以在列中使用其他算术运算符。这些包括加法 (`+`)、减法 (`-`) 和除法 (`/`)。例如，列表 3.2 中的查询使用了多种表达式。

### 列表 3.2：各种表达式

```sql
SELECT p_name, price * 1 AS new_price, price - 10 AS discounted_price, price / 2 AS half_price
FROM product;
```

列表 3.2 的查询返回以下行。

| P_CODE | PRICE | LAUNCH_DT |
| --- | --- | --- |
| 1 Nail | 10.00 31-MAR-13 |
| 2 Washer | 15.00 29-MAR-13 |
| 3 Nut | 15.00 29-MAR-13 |
| 4 Screw | 25.00 30-MAR-13 |
| 5 Super_Nut | 30.00 30-MAR-13 |
| 6 New Nut | NULL | NULL |

输出如下。

```
P_NAME          NEW_PRICE  DISCOUNTED_PRICE  HALF_PRICE LAUNCH_DT
---------- -------------------------- ---------- ----------
Nail            11.00     0.00              5.00      31-MAR-13
Washer           16.50     5.00              7.50      29-MAR-13
Nut             16.50     5.00              7.50      29-MAR-13
Screw           27.50     15.00             12.50     30-MAR-13
Super_Nut       33.00     20.00             15.00     30-MAR-13
New Nut         NULL       NULL              NULL
```

### 拼接

你还可以使用连接运算符 (`||`) 来连接字符串。例如，列表 3.3 使用了它。

### 列表 3.3：拼接

```sql
SELECT p_name || ' - ' || p_code AS "product_info" FROM product;
```

列表 3.3 查询的输出如下。

```
PRODUCT_INFO
----------
```

## 限制行数

你可以使用 `ROWNUM` 伪列来限制输出行数。其语法如下。

```
SELECT columns FROM table(s)
WHERE conditions ROWNUM < count;
```

使用 `ROWNUM` 的查询的最大输出行数将是 `count – 1`。

例如，看看列表 3.4 中的查询。

### 列表 3.4：使用 ROWNUM

```
SELECT * FROM product WHERE price > 10 AND ROWNUM < 4;
```

如果没有 `ROWNUM < 4` 表达式，输出行数将是 4。然而，列表 3.4 中的查询返回了这三行。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |

## DISTINCT 关键字

查询可能会返回重复行。如果两行的每一列都包含完全相同的数据，则这两行是重复的。如果你不想看到重复的输出行，请在 `SELECT` 子句中使用 `DISTINCT`。你可以在单列或多列上使用 `DISTINCT`。

### 在单列上使用 DISTINCT

列表 3.4 中的查询对 `price` 列使用了 `DISTINCT`。

- 列表 3.4：在单列上使用 DISTINCT

```
SELECT DISTINCT price FROM product ORDER BY price;
```

如果不使用 `DISTINCT`，列表 3.4 中的查询将返回六行，其中包含第 2 行和第 3 行的两个重复价格（两个重复的价格）。相反，列表 3.4 的查询返回以下输出。

```
PRICE
-----
10
15
25
30
NULL
```

## 在多列上使用 DISTINCT

如果查询返回多个列，当两行的所有列都具有相同值时，这两行被认为是重复的。如果只有一个列具有相同值，则它们不是重复的。

`DISTINCT` 关键字也可以应用于多个列。例如，列表 3.5 中的查询在多列上使用了 `DISTINCT`。

列表 3.5：在多列上使用 DISTINCT

```
SELECT DISTINCT price, launch_dt FROM product ORDER BY price;
```

这是输出。请注意，具有相同 `price` 和 `launch_dt` 的输出行将只显示一次。

```
PRICE LAUNCH_DT
---------- ----------
10 31-MAR-13
15 29-MAR-13
25 30-MAR-13
30 30-MAR-13
NULL NULL
```

## 聚合函数

你可以通过聚合函数进一步处理查询输出。聚合函数列在表 3.1 中。

| 函数 | 描述 |
| --- | --- |
| `MAX(column)` | 列的最大列值 |
| `MIN(column)` | 列的列值 |
| `SUM(column)` | 列值的之和 |
| `AVG(column)` | 列的平均值 |
| `COUNT(column)` | 行数 |
| `COUNT(*)` | 包括 `NULL` 在内的所有行数。 |

表 3.1：内置聚合函数

例如，列表 3.6 中的查询使用了表 3.1 中的聚合函数。

### 列表 3.6：使用聚合函数

```
SELECT MAX(price),
MIN(price),
SUM(price),
AVG(price),
COUNT(price),
COUNT(*)
FROM product;
```

注意，只有 `COUNT(*)` 考虑了 `New Nut` 产品，因为它的价格为 `NULL`。

列表 3.6 查询的输出为。

| MAX(PRICE) | MIN(PRICE) | SUM(PRICE) | AVG(PRICE) | COUNT(PRICE) | COUNT (*) |
|---|---|---|---|---|---|
| 30 | 10 | 95 | 19 | 5 | 6 |

`CASE` 表达式允许你拥有动态查询输出，其中列的值可能会根据列的值而变化。`CASE` 有两种类型：简单（Simple）和搜索（Searched）。将在后续子节中将解释两者。

## 简单 CASE

Simple CASE 的通用语法如下。

```
SELECT columns,
CASE column
WHEN equal_value1
THEN output_value1
WHEN equal_value2
THEN output_value2
WHEN
...
[ELSE else_value]
END AS output_column
FROM table
WHERE ... ;
```

在 Simple CASE 中，`column_name` 与 `WHEN` 子句中的 `equal_values` 进行比较，从第一个 `WHEN` 开始到最后一个 `WHEN`。如果 `column_name` 匹配某个 `WHEN` 值，则返回 `THEN` 之后的值，并停止 `CASE` 过程。如果 `column_name` 不匹配任何 `WHEN` 值，且存在 `ELSE` 子句，则返回 `else_value`。如果 `column_name` 不匹配任何 `WHEN` 值但不存在 `ELSE` 子句，则将返回 `NULL`。

例如，列表 3.7 中的查询对 `price` 列使用了 Simple CASE 表达式，以产生 `price_cat`（价格类别）输出列。

### 列表 3.7：Simple CASE 示例

```
SELECT p_code,
p_name,
CASE price
WHEN 10
THEN 'Cheap'
WHEN 15
THEN 'Medium'
WHEN 25
THEN 'Expensive'
ELSE 'Others'
END AS price_cat
FROM product;
```

假设产品表具有以下数据

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |



# 36 Oracle SQL：入门教程

## 第3章：查询输出

### Searched CASE

Simple CASE 将列与多个值进行比较。相反，Searched CASE 可以是任何条件。以下是 Searched CASE 的语法。

```sql
SELECT columns,
CASE
  WHEN condition1
    THEN output_value1
  WHEN condition2
    THEN output_value2
  WHEN
    ELSE else_value
END AS output_column
FROM table
WHERE;
```

条件从第一个 `WHEN` 到最后一个进行评估。如果满足某个条件，则返回相应的值并停止 `CASE` 过程。如果都不满足且存在 `ELSE` 子句，则返回`else_value`。如果都不满足且不存在 `ELSE` 子句，则将返回 `NULL`。

例如，列表 3.8 中的查询对`price`列使用了 Searched CASE 表达式以产生`price_cat`（价格类别）输出列。

#### 列表 3.8：Searched CASE 示例

```sql
SELECT p_code,
p_name,
CASE
WHEN price <= 10 THEN 'Cheap'
WHEN price BETWEEN 10 AND 25 THEN 'Medium'
WHEN price > 25 THEN 'Expensive'
ELSE 'Others'
END AS price_cat
FROM product;
```

该查询将返回这些行。

| P_CODE | P_NAME | PRICE_CAT |
|---|---|---|
| 1 | Nail | Cheap |
| 2 | Washer | Medium |
| 3 | Nut | Medium |
| 4 | Screw | Expensive |
| 5 | Super_Nut | Others |
| 6 | New Ut | Others |

### 列表 3.11：多列排序

```sql
SELECT * FROM product ORDER BY launch_dt, price;
```

对`product`表执行该查询。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Nut | 30.00 | 30-MAR-13 |
| 6 | Nut | NULL | NULL |

输出行将首先按`launch_dt`排序，然后按`price`排序，两者均为升序。对`price`的次级排序在 Screw 和 Super_Nut 行中可见。它们的`launch_dt`相同，都是 30-MAR-13。它们的价格不同，Screw 的价格低于 Super_Nut，因此 Screw 行在 Super_Nut 行之前。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 3 | Nut | 15.00 | 29-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 1 | Nail | 10.00 | 31-MAR-13 |
| 6 | New Nut | NULL | NULL |

### 不同列使用不同的排序方向

你也可以对排序的列应用不同的排序方向。例如，列表 3.12 中的查询在其 `ORDER BY` 子句中对不同列使用了不同的方向。

#### 列表 3.12：使用 ORDER 的多个方向

```sql
SELECT * FROM product ORDER BY launch_dt, price DESC;
```

对`product`表执行该查询，输出行将按`launch_dt`升序排序，然后按`price`降序排序。现在，Super_Nut 排在了 Screw 之前。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 3 | Nut | 15.00 | 29-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 1 | Nail | 10.00 | 31-MAR-13 |
| 6 | New Nut | NULL | NULL |

## 使用 WHERE 子句排序

如果你的 `SELECT` 语句同时包含 `WHERE` 子句和 `ORDER BY` 子句，则 `ORDER BY` 必须出现在 `WHERE` 子句之后。

例如，列表 3.13 中的查询同时包含 `WHERE` 和 `ORDER BY`。该查询将仅返回 Nut 产品。

#### 列表 3.13：同时使用 WHERE 和 ORDER BY

```sql
SELECT * FROM product WHERE p_name = 'Nut'
ORDER BY p_name, p_code DESC;
```

如果你执行该查询，你将在输出窗口中只看到一行，即 Nut。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 3 | Nut | 15.00 | 29-MAR-13 |

## 存储查询输出

你可以将查询输出存储到新表或现有表中。要将查询输出存储在新表中，请使用以下语句：

```sql
CREATE TABLE new_table AS SELECT ...;
```

例如，列表 3.14 中的查询执行了一个 `SELECT` 语句并将结果存储在一个名为`nut_product`的新表中。

#### 列表 3.14：将输出存储到新表

```sql
CREATE TABLE nut_product AS
SELECT * FROM product WHERE p_name LIKE '%Nut%';
```

对`product`表执行时，列表 3.14 中的查询将创建一个包含以下内容的`nut_product`表。

| CODE | NAME | LAUNCH_DT |
|---|---|---|
| 3 | Nut | 15.00 29-MAR-13 |
| 6 | New Nut | NULL |
| 5 | Super_Nut | 30.00 30-MAR-13 |

要将查询输出存储到现有表中，请使用此语法。

```sql
INSERT INTO existing_table AS SELECT ...
```

例如，列表 3.15 中的查询将查询结果存储在现有表中。

#### 列表 3.15：将输出存储到现有表

```sql
INSERT INTO non_nut
SELECT * FROM product WHERE p_name LIKE '%Nut%';
```

在执行列表 3.15 的语句之前，你必须先执行以下操作创建`non_nut`表。

```sql
CREATE TABLE non_nut(
  p_code VARCHAR(6),
  p_name VARCHAR(15),
  price NUMBER(4),
  launch_dt DATE,
  PRIMARY KEY (p_code)
);
```

对此`product`表执行列表 3.15 的查询将得到包含以下行的`non_nut`表。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 6 | New Nut | NULL | NULL |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |

## 总结

SQL 允许从表中检索行并处理输出。在本章中学习了如何创建别名、使用聚合函数并对行排序。

# 第4章：分组

组是在特定列具有相同值的行的集合。在第 3 章“查询输出”中，我们学习了如何对所有输出应用聚合函数。在本章中，我们学习如何创建组并对这些组应用聚合函数。

## GROUP BY 子句

在查询中，`GROUP BY` 子句出现在 `WHERE` 子句之后，`ORDER BY` 子句之前。这是带有 `WHERE`、`GROUP BY` 和 `ORDER BY` 子句的 `SELECT` 语句语法：

```sql
SELECT columns,
  aggregate_function(group_columns)
FROM table(s)
WHERE condition
  GROUP BY group_columns
ORDER BY columns;
```

例如，列表 4.1 的查询按日期从`product`表获取输出。

### 列表 4.1：按列分组

```sql
SELECT launch_dt,
  MAX(price) MAX,
MIN(price) MIN,
SUM(price) SUM,
AVG(price) AVG,
COUNT(price) COUNT,
COUNT(*) AS "COUNT(*)"
FROM product
GROUP BY launch_dt;
```

对具有以下行的`product`表执行，将按日期（29日、30日、31日以及 `NULL`）进行聚合。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | New Nut | NULL | NULL |

查询输出将有四行，每个分组日期一行。注意，`COUNT(price)` 元素统计价格列的值，结果为 0。另一方面，`COUNT(*)` 元素统计 `NULL` 日期，结果为 1。

| LAUNCH_DT | MAX | MIN | AVG | COUNT | COUNT(*) |
|---|---|---|---|---|---|
| 29-MAR-13 | 15 | 15 | 30 | 15 | 2 |
| 30-MAR-13 | 30 | 25 | 55 | 27.5 | 2 |
| 31-MAR-13 | 10 | 10 | 10 | 10 | 1 |
| NULL | NULL | NULL | NULL | 0 | 1 |

你可以按多个列进行分组。如果这样做，在所有列上具有相同值的行将形成一组。例如，列表 4.2 按价格和日期进行分组。

### 列表 4.2：按两列分组

```sql
SELECT price,
launch_dt,
MAX(price) MAX,
MIN(price) MIN,
SUM(price) SUM,
AVG(price) AVG,
COUNT(price) COUNT,
COUNT(*) AS "COUNT(*)"
FROM product
GROUP BY price,
launch_dt
ORDER BY price,
launch_dt;
```

应用于同一个`product`表，输出将有五行。尽管 Screw 和 Super_Nut 的价格相同，但它们的启动日期不同，因此属于不同的组。

| LAUNCH_DT | MAX | MIN | AVG | COUNT | COUNT(*) |
|---|---|---|---|---|---|
| 29-MAR-13 | 15 | 15 | 30 | 15 | 2 | 2 |
| 30-MAR-13 | 30 | 25 | 55 | 27.5 | 2 | 2 |
| 31-MAR-13 | 10 | 10 | 10 | 10 | 1 | 1 |
| NULL | NULL | NULL | NULL | 0 | 1 |

## HAVING 关键字

`WHERE` 条件用于选择行。相反，`HAVING` 条件用于选择组。只有满足 `HAVING` 子句中条件的组才会被查询返回。换句话说，`HAVING` 条件是针对聚合结果的而不是针对列。

如果存在，`HAVING` 子句必须出现在 `GROUP BY` 之后，如下语法所示：

```sql
SELECT columns,
  aggregate_function(group_columns)
FROM table(s)
WHERE condition
GROUP BY group_columns
HAVING aggregate_condition
ORDER BY columns;
```

例如，列表 4.3 中的查询使用了 `HAVING` 条件。

### 列表 4.3：使用 HAVING 条件

```sql
SELECT price,
launch_dt,
MAX(price) MAX,
MIN(price) MIN,
SUM(price) SUM,
AVG(price) AVG,
COUNT(price) COUNT,
COUNT(*) "COUNT(*)"
FROM product
GROUP BY price,
launch_dt
HAVING COUNT(price) > 1
ORDER BY price,
launch_dt;
```

仅返回包含多行（满足 `COUNT(price) > 1` 条件）的组。将只返回一行，即价格 = 15 且发布日期 = 29-MAR-13 的行。

| PRICE LAUNCH DT | MAX | MIN | SUM | AVG | COUNT | COUNT(*) |
|---|---|---|---|---|---|---|
| 15 | 29-MAR-13 | 15 | 15 | 30 | 15 | 2 |

如果存在 `WHERE` 子句，它必须出现在 `GROUP BY` 子句之后。在进行分组之前，单独行将通过 `WHERE` 条件进行选择。例如，列表 4.4 中的查询同时使用了 `WHERE` 和 `GROUP BY`。

### 列表 4.4：使用 WHERE 分组

```sql
SELECT launch_dt,
MAX(price) MAX,
MIN(price) MIN,
SUM(price) SUM,
AVG(price) AVG,
COUNT(price) COUNT,
COUNT(*) "COUNT(*)"
FROM product
WHERE p_name NOT LIKE 'Super%'
GROUP BY launch_dt
HAVING launch_dt > '29-MAR-13'
ORDER BY launch_dt;
```

这里是查询输出。

| LAUNCH_DT | MAX | MIN | SUM | AVG | COUNT | COUNT (*) |
| --- | --- | --- | --- | --- | --- | --- |
| 30-MAR-13 | 25.0 | 25.0 | 25.0 | 25.0 | 1 | 1 |
| 31-MAR-13 | 10.0 | 10.0 | 10.0 | 10.0 | 1 | 1 |

在这种情况下，Nut 不满足 `WHERE` 条件。因此，它没有包含在聚合结果中。

不允许将聚合函数作为 `WHERE` 子句。这在列表 4.5 中所示，该列表包含一个执行时会抛出错误的查询。

### 列表 4.5：在聚合上使用 WHERE 的错误

```sql
SELECT price,
launch_dt,
MAX(price) MAX,
MIN(price) SUM,
SUM(price) AVG,
AVG(price) COUNT,
COUNT(price) COUNT,
COUNT(*) COUNT(*)
FROM product
WHERE COUNT(price) > 1;
```

执行此查询将得到此错误消息：

```
-00934: group function is not allowed here
```

## 总结

在本章中，你学习了如何对行值进行聚合。你还学习了使用应用在聚合上的 `HAVING` 条件。在下一章中，你将学习使用 `JOIN` 子句，它用于“聚合”来自多个表的行。

# 第 5 章：连接 (Joins)

现实世界的数据库通常将数据存储在几十个甚至数百个表中。在这些多表数据库中，一个表通常与一个或多个其他表相关。在这种环境下，你应该能够使用 `JOIN` 子句关联两个或多个表的行。本章将向你展示如何操作。

## 主键和外键



在第 1 章“存储和维护数据”中，你学习了主键。主键是一个列或一组列，它能唯一标识表中的每一行。外键是一个列或一组列，它用于与另一个表的主键建立关联。使用外键/主键关联两个表的行的过程被称为“连接（joining）”。虽然主键是唯一的，但外键不需要是唯一的。你可以在多行中拥有相同的外键。例如，在订单表中，同一个产品可以有多个订单。在这个订单表中，产品由其外键表示，例如产品代码，它是产品表的主键。虽然连接表必须使用主键和外键，但缺失它们会导致错误地连接表。

## 查询多个表

要从多个表查询数据，使用`JOIN`关键字来指定两个表的关联列。`SELECT`语句的`JOIN`子句根据主键/外键关系连接两个或多个表的行。例如，订单表（`c_order`）可能需要一个外键来关联产品表的主键。此外，订单表可能还需要一个外键来关联客户表的主键。`JOIN`的语法如下：

```sql
SELECT columns FROM table_1, table_2, ... table_n
WHERE table_1.primary_key = table_2.foreign_key
AND table_2.primary_key = table_n.foreign_key;
```

为了说明连接的使用，将分别使用表 5.1、5.2 和 5.3 中的订单表、客户表和产品表。订单表的`C_NO`和`P_CODE`是外键；它们对应的主键分别在客户表和产品表中。

| C_NO | P_CODE | QTY | ORDER_DT |
|---|---|---|---|
| 10 | 1 | 100 | 01-APR-13 |
| 10 | 2 | 100 | 01-APR-13 |
| 20 | 1 | 200 | 01-APR-13 |
| 30 | 3 | 300 | 02-APR-13 |
| 40 | 4 | 400 | 02-APR-13 |
| 40 | 5 | 400 | 03-APR-13 |

表 5.1：订单表（`c_order`）

```
C_NO C_NAME
----------
10 Standard Store
20 Quality Store
30 Head Office
40 Super Agent
```

表 5.2：客户表

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | New Nut | NULL | NULL |

表 5.3：产品表

列表 5.1 是`JOIN`查询的示例。它根据订单表的`c_no`外键列和客户表的`c_no`主键列将订单表与客户表连接。该查询返回下了一个或多个订单的客户名称。

### 列表 5.1：双表连接

```sql
SELECT c_name,
p_code,
c_order.qty,
c_order.order_dt
FROM c_order
JOIN customer
ON c_order.c_no = customer.c_no;
```

对`c_order`和`customer`表应用后，结果如下。

| C_NAME | QTY | ORDER_DT |
|---|---|---|
| Standard Store | 2 | 100 01-APR-13 |
| Standard Store | 1 | 100 01-APR-13 |
| Quality Store | 1 | 200 01-APR-13 |
| Head Office | 3 | 300 02-APR-13 |
| Super Agent | 5 | 400 03-APR-13 |
| Super Agent | 4 | 400 02-APR-13 |

### 使用别名 (Aliases)

在`join`查询中，不同的表可能具有相同名的列。为了确保引用的是表的正确列，你需要使用其别名对其进行限定。在上一个示例中，`order.c_no`（`c_order`表的`c_no`列）和`customer.c_no`（`customer`表的`c_no`列）被限定了。表别名是一种更方便（更短）的限定列的方法。

例如，在列表 5.2 的查询中，`o`是`c_order`表的别名，`c`是客户表的别名。这些别名被用于`ON`子句，以通过各自表来限定`c_no`列。

### 列表 5.2：使用表别名

```sql
SELECT c_name,
p_code,
o.qty,
o.order_dt
FROM c_order o
JOIN customer c
ON o.c_no = c.c_no;
```

### 列别名 vs. 表别名

在第 3 章“查询输出”中，我解释了使用`AS`关键字创建列别名。虽然列别名可以不用`AS`关键字创建，但它的存在提高了可读性（使用`p_name AS product name`代替`p_name`）。另一方面，表别名不能使用`AS`。

## 连接多个表

根据之前提供的`JOIN`语法，你可以连接多个表。要实现这一点，在`SELECT`语句中一次连接两个表。例如，列表 5.3 中的查询将订单表与客户表连接，然后将客户表与产品表连接。订单表的行与客户表的相同`c_no`列连接，这些行再与产品表的相同`p_code`连接。该查询返回客户名称及其订单。

### 列表 5.3：三表连接

```sql
SELECT c_name,
p_name,
o.qty,
o.order_dt
FROM c_order o
JOIN customer c
ON o.c_no = c.c_no
JOIN product p
ON o.p_code = p.p_code;
```

对`c_order`、`customer`和`product`示例表应用后，你将看到以下结果。你也可以在`join`查询中应用`WHERE`条件来选择行。例如，在列表 5.4 中，得益于`WHERE`条件，只有以“Super”开头的产品名称出现在查询输出中。

### 列表 5.4：JOIN AND WHERE

```sql
SELECT c_name,
p_name,
o.qty,
o.order_dt
FROM c_order o
JOIN customer c
ON o.c_no = c.c_no
JOIN product p
ON o.p_code = p.p_code
WHERE p_name NOT LIKE 'Super%';
```

在示例表上执行列表 5.4 中的查询将产生以下输出行。

| C_NAME | P_NAME | QTY | ORDER_DT |
| --- | --- | --- | --- |
| Standard Store | Washer | 100 | 01-APR-13 |
| Standard Store | Nail | 100 | 01-APR-13 |
| Quality Store | Nail | 200 | 01-APR-13 |
| Branch Office | Nut | 300 | 02-APR-13 |
| Super Agent | Screw | 400 | 02-APR-13 |

## 多列连接

之前的连接是基于单列的。表也可以基于多一个列进行连接。

两个表多列连接的语法如下：

```
SELECT columns table_1, table_2
WHERE table_1.column_1 = table_2.column_1
AND table_1.column_2 = table_2.column_2
...
AND table_1.column_n = table_2.column_n;
```

作为一个示例，假设你在`shipment`表中跟踪订单发货。

| C_NO | P_CODE | ORDER_DT | SHIP_QTY | SHIP_DT |
| --- | --- | --- | --- | --- |
| 10 | 1 | 01-APR-13 | 50 | 02-APR-13 |
| 10 | 2 | 01-APR-13 | 100 | 02-APR-13 |
| 20 | 1 | 01-APR-13 | 100 | 02-APR-13 |
| 30 | 3 | 02-APR-13 | 300 | 03-APR-13 |
| 10 | 1 | 01-APR-13 | 50 | 10-APR-13 |

为了获取每次发货的订单数量（`c_order`表中的`qty`），你需要一个查询，将`shipment`表与`order`表通过三个列（`c_no`、`p_no`和`order_dt`）进行连接，如列表 5.5 中的查询所示。

### 列表 5.5：多列连接

```
SELECT o.c_no,
o.p_code,
o.order_dt,
ship_qty,
ship_dt,
qty
FROM shipment s
JOIN c_order o
ON s.c_no = o.c_no
AND s.p_code = o.p_code
AND s.order_dt = o.order_dt;
```

在`c_order`和`shipment`表上执行此查询将得到以下输出行。

| C_NO | P_CODE | ORDER_DT | SHIP_QTY | SHIP_DT | QTY |
|---|---|---|---|---|---|
| 10 | 1 | 01-APR-13 | 50 | 10-APR-13 | 100 |
| 10 | 1 | 01-APR-13 | 50 | 02-APR-13 | 100 |
| 10 | 2 | 01-APR-13 | 100 | 02-APR-13 | 100 |
| 20 | 1 | 01-APR-13 | 100 | 02-APR-13 | 200 |
| 30 | 3 | 02-APR-13 | 300 | 03-APR-13 | 300 |

## 外连接

到目前为止我解释的所有连接都是内连接（inner joins）。另一种连接类型是外连接（outer join）。内连接查询只产生连接表中的相关行，而外连接查询即使在某些行在另一个表中没有匹配行，也会产生其中一个表的所有行。

外连接有三种子类型：LEFT（左）、RIGHT（右）和 FULL（全）。接下来的点描述了这三种类型中的。

外连接左侧表的所有行都将出现在输出中，无论其右侧表是否有匹配行。左外连接的语法如下：

```
SELECT columns
FROM table_1 LEFT OUTER JOIN table_2
ON table_1.column = table_2.column;
```

右外连接右侧表的所有行都将出现在输出中，无论其左侧表是否有匹配行。右外连接的语法如下：

```
SELECT columns FROM table_1 RIGHT OUTER JOIN table_2 ON
table_1.column = table_2.column ... ;
```

全外连接返回所有表的所有行，无论相反表中是否存在匹配行。全外连接的语法如下：

```
SELECT columns
FROM table_1 FULL OUTER JOIN table_2
ON table_1.column = table_2.column ... ;
```

列表 5.6 是一个左外连接查询示例。该查询返回`c_order`表的所有行。

### 列表 5.6：左外连接

```
SELECT o.*,
ship_dt
FROM c_order shipment s
LEFT OUTER JOIN ON o.p_code = s.p_code
AND o.c_no = s.c_no;
```

如果你在我们示例的`c_order`和`shipment`表上运行此查询，你将看到以下输出行。

| C_NO | P_CODE | QTY ORDER_DT | SHIP_DT |
|---|---|---|---|
| 10 | 1 | 100 01-APR-13 | 02-APR-13 |
| 10 | 2 | 100 01-APR-13 | 02-APR-13 |
| 20 | 1 | 200 01-APR-13 | 02-APR-13 |
| 30 | 3 | 300 02-APR-13 | 03-APR-13 |
| 10 | 1 | 100 01-APR-13 | 10-APR-13 |
| 40 | 4 | 400 02-APR-13 | NULL |
| 40 | 5 | 400 03-APR-13 | NULL |

注意最后两行没有`shipment`表的匹配行，因此它们的`ship_dt`列为 NULL。

### 仅 NULL 行

如果你只想查询完全发货的订单，你必须像列表 5.7 那样在查询的`WHERE`子句中放入此“only”条件（`ship_dt IS NULL`）。

### 列表 5.7：NULL 行

```
SELECT o.*,
ship_dt
FROM c_order o
LEFT OUTER JOIN shipment s
ON o.p_code = s.p_code
AND o.c_no = s.c_no
WHERE s.ship_dt IS NULL;
```

列表 5.7 查询的输出输出是尚未发货的订单。

| C_NO | P_CODE | QTY ORDER_DT | SHIP_DT |
|---|---|---|---|
| 40 | 4 | 400 02-APR-13 | NULL |
| 40 | 5 | 400 03-APR-13 | NULL |

## 全外连接

假设`c_order`表中的某个订单被了（在现实应用中，取消的订单可能会移动到另一个表）。这意味着`shipment`表的某些行在`order`表中没有匹配行。为了返回没有发货的订单以及没有订单的发货记录，我们需要编写一个如列表 5.8 所示的全外连接查询。

### 列表 5.8：全外连接

```
SELECT o.*, s.*
FROM c_order o
FULL OUTER JOIN shipment s
ON o.p_code = s.p_code
AND o.c_no = s.c_no;
```

为了测试此查询，你需要删除一个订单，例如客户 30 下的订单。`c_order`表现在如下。删除后，`c_order`表行如下。

| C_NO | P_CODE | QTY ORDER_DT |
|---|---|---|
| 10 | 1 | 100 01-APR-13 |
| 10 | 2 | 100 01-APR-13 |
| 20 | 1 | 200 01-APR-13 |
| 40 | 4 | 400 02-APR-13 |
| 40 | 5 | 400 03-APR-13 |

如果你运行列表 5.8 中的查询，你将得到以下输出行。注意两边都有 NULL。右侧的 NULL 来自`shipment`表，左侧的 NULL（在我们行中）来自`c_order`表。

| C_NO | P_CODE | QTY ORDER_DT | C_NO | P_CODE ORDER_DT | SHIP_QTY SHIP_DT |
|---|---|---|---|---|---|
| 10 | 1 | 100 01-APR-13 | 10 | 1 01-APR-13 | 50 02-APR-13 |
| 10 | 2 | 100 01-APR-10 | 10 | 2 01-APR-13 | 100 02-APR-13 |
| 20 | 1 | 200 01-APR-20 | 20 | 1 01-APR-13 | 100 02-APR-13 |
| 10 | 1 | 100 01-APR-10 | 10 | 1 01-APR-13 | 50 10-APR-13 |
| 40 | 4 | 400 02-APR-13 | NULL | NULL | NULL NULL |
| 40 | 5 | 400 03-APR-13 | NULL | NULL | NULL NULL |
| NULL | NULL | NULL | 30 | 3 02-APR-13 | |

## 自连接

假设你的某些产品有替代品，并且你想在`product`表中记录这些替代品，那么你需要添加一列。`product`表中名为`s_code`的新列包含替代品的产品代码。具有`s_code`为 5 的行的的新产品现在看起来如下。

| P_CODE P_NAME | PRICE DT | S_CODE |
|---|---|---|
| 1 Nail | 10 31-MAR-13 | |
| 2 Washer | 15 29-MAR-13 | |
| 3 Nut | 15 29-MAR-13 | 5 |
| 4 Screw | 25 30-MAR-13 | |

要添加`s_code`列，执行以下语句：

```
ALTER TABLE product ADD (s_code VARCHAR2(6));
```

然后，更新`p_code = 3`，执行以下语句：

```
UPDATE product SET s_code = 5 WHERE p_code = 3;
```

如果你需要知道替代品的名称，你需要列表 5.9 所示的查询。该查询将`product`表与其连接。这种连接被称为自连接（self-join）。

自连接的语法如下：



`SELECT columns FROM table alias_1 JOIN table alias_2 ON alias_1.column_x = alias_2.column_y;`

注意`column_x`和`column_y`是同一张表中的列。

### 列表 5.9：自连接

```
SELECT prod.p_code,
prod.p_name,
subst.p_code subst_p_code,
subst.p_name subst_name
FROM product prod
LEFT OUTER JOIN product subst
ON prod.s_code = subst.p_code
ORDER BY prod.p_code;
```

这里是查询的输出行，在第三行的`subst_name`列中显示“Super_Nut”。

| P_CODE P_NAME | SUBST SUBST_NAME |
|---|---|
| 1 Nail | NULL NULL |
| 2 Washer | NULL NULL |
| 3 Nut | 5 Super_Nut |
| 4 Screw | NULL NULL |
| 5 Super_Nut | NULL NULL |
| 6 New Nut | NULL NULL |

## 表的多种用途

如果一个产品有多个替代品，则你需要一个单独的表来存储产品与替代品的关系。替代品不能记录在产品表中。

要创建一个名为`prod_subst`的存储产品-替代品关系的表，请执行以下语句。

```
CREATE TABLE prod_subst (p_code VARCHAR(6), s_code VARCHAR(6));
```

要移除`s_code`列，请执行以下语句：

```
ALTER TABLE product DROP (s_code);
```

你的产品表现在将包含以下行。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
| --- | --- | --- | --- |
| 1 | Nail | 10 | 31-MAR-13 |
| 2 | Washer | 15 | 29-MAR-13 |
| 3 | Nut | 15 | 29-MAR-13 |
| 4 | Screw | 25 | 30-MAR-13 |
| 5 | Super_Nut | 30 | 30-MAR-13 |
| 6 | New Nut | NULL | NULL |

假设唯一具有替代品的是产品 3，其替代品是产品 5 和 6，则`prod_subst`表将具有如下两行。（你需要使用`INSERT`语句插入这两行）

```
P_NO_S_CODE
------ -------
3     5
3     6
```

要获取一个产品的名称及其替代品的名称，你需要两次使用产品表，如列表 5.10 中的查询所示。

### 列表 5.10：表的多次使用

```
SELECT prod.p_code,
prod.p_name,
ps.s_code,
subst.p_name AS s_name
FROM product prod
INNER JOIN prod_subst ps
ON prod.p_code = ps.p_code
INNER JOIN product subst
ON ps.s_code = subst.p_code
ORDER BY prod.p_code;
```

以下是列表 5.10 中查询的输出行。

| P_CODE P_NAME | S_CODE S_NAME |
|---|---|
| 3 Nut | 6 Newer Nut |
| 3 Nut | 5 Super_Nut |

## 自然连接

如果两个表具有同名的列，你可以根据这些列对两个表进行自然连接。在自然连接中，你不需要指定连接应该使用的列。

自然连接的语法如下。

```
SELECT columns FROM table_1 NATURAL JOIN table_2 ... ;
```

列表 5.11 显示了在`c_order`表和`customer`表上进行自然连接的示例。此自然连接隐式地通过它们的`c_no`列连接表连接。

列表 5.11：自然连接

```
SELECT * FROM c_order NATURAL JOIN customer;
```

运行列表 5.11 中的查询将得到以下输出行。

| C_NO P_CODE | QTY ORDER_DT | C_NAME |
|---|---|---|
| 10 1 | 100 01-APR-13 | Standard Store |
| 10 2 | 100 01-APR-13 | Standard Store |
| 20 1 | 200 01-APR-13 | Quality Store |
| 40 4 | 400 02-APR-13 | Super Agent |
| 40 5 | 400 03-APR-13 | Super Agent |

## 自然外连接

自然连接也适用于外连接。考虑列表 5.12 中的查询。

### 列表 5.12：自然外连接

```
SELECT * FROM c_order NATURAL RIGHT JOIN customer;
```

在`c_order`和`customer`表上应用该查询将得到以下输出行。

| C_NO P_CODE | QTY ORDER_DT | C_NAME |
|---|---|---|
| 10 1 | 100 01-APR-13 | Standard Store |
| 10 2 | 100 01-APR-13 | Standard Store |
| 20 1 | 200 01-APR-13 | Quality Store |
| 40 4 | 400 02-APR-13 | Super Agent |
| 40 5 | 400 03-APR-13 | Super Agent |
| 30 NULL | NULL | Head Office |

## 混合使用不同列名的自然连接

如果你需要根据一列进行连接，而第二对列没有共同列名，你可以在`WHERE`子句中指定不同的列名。列表 5.13 显示了此类示例。

# 66 Oracle SQL：初学者教程

整体查询输出如下所示。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | Newer Nut | 30.00 | 01-MAY-13 |

## ALL 和 ANY 运算符

除了`IN`和`NOT IN`之外，你还可以在多行子查询中使用`ALL`和`ANY`运算符。在使用`ALL`或`ANY`时，你会使用比较运算符。例如，列表 6.4 中的查询使用`ANY`运算符将价格列与子查询进行比较。

### 列表 6.4：使用 ALL

```
SELECT *
FROM product
WHERE price >= (
  SELECT MAX(price)
  FROM product p
  INNER JOIN c_order o
  ON o.p_code = o.p_code
  GROUP BY p.launch_dt
)
ORDER BY p_code;
```

在相同的`product`和`order`表上运行，列表 6.4 中的子查询（加粗显示）返回了这些结果：

```
MAX(PRICE)
------
15
30
10
```

查询输出将仅包含价格大于或等于子查询返回的所有值的行。

## 此处是查询输出。

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | Newer Nut | 30.00 | 01-MAY-13 |

另一个例子是列表 6.5 中的查询与列表 6.4 中的查询相似，不同之处在于等号运算符来比较价格与子查询的结果。

### 列表 6.5：使用 ALL 进行相等比较

```
SELECT *
FROM product
WHERE price = ALL
(SELECT MAX(price)
FROM product p
INNER JOIN c_order o
ON o.p_code = o.p_code
GROUP BY p.launch_dt
)
ORDER BY p_code;
```

与上一个示例相同，子查询将返回这些值：

```
MAX(PRICE)
----------
15
30
10
```

查询输出随后仅包含价格等于所有这些值的行，这是不可能的，因为每个产品只有一个价格。因此，查询没有返回任何行。如果你运行该查询，将看到如下消息：

```
no rows selected
```

## 返回具有相同值的行的子查询

如果你使用`ALL =`且子查询返回一行或多行具有相同值的行，你将不会得到“no rows selected”的消息。

你也可以使用`ANY`运算符将一列与子查询返回的值进行比较。如果你使用`ALL`，查询会将该列与子查询返回的所有值（每一个值）进行比较。如果你使用`ANY`，查询则会将该列与子查询返回的任一值进行比较。

例如，列表 6.6 中的查询将价格列与子查询返回的任何最大价格进行相等比较，句话说，如果价格等于任何一个最大价格，则`WHERE`条件为真。

### 列表 6.6：对 ANY 值使用相等比较

```
SELECT *
FROM product
WHERE price = ANY
(SELECT MAX(price)
  FROM product p
  INNER JOIN c_order o
  ON p.P_code = o.p_code
  GROUP BY p.launch_dt
)
ORDER BY p_code;
```

子查询将返回这些行：

```
MAX(PRICE)
-------
15
30
10
```

外部查询的输出将包含任何价格等于这些（最大价格）值之一的。。这里是查询输出。

```
P_CODE P_NAME PRICE LAUNCH_DT
```

## 第6 章：子查询 69

| | | | |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | Newer Nut | 30.00 | 01-MAY-13 |

## 多层嵌套子查询

子查询可以包含另一个查询，使其成为具有多个嵌套子查询的查询。例如，列表 6.7 中的查询具有多个嵌套子查询。注意那两个`IN`，分别对应两个嵌套查询。查询仅返回没有订购包含 'Nut' 产品名的客户。

列表 6.7：带有多个嵌套子查询的查询

```
SELECT customer.*
FROM customer
WHERE c_no IN
(SELECT c_order
FROM c_order
WHERE p_code IN
(SELECT p_code FROM product WHERE p_name LIKE '%Nut%'));
```

这是查询结果。

```
C_NO C_NAME
------
40 Super Agent
10 Standard Store
```

## 关联子查询

之前的子查询都是独立于其外部查询的。子查询也可以与其外部查询相关，其中外部表中的一个或多个列与子查询表的列（们）相关。这种子查询被称为关联子查询。

例如，列表 6.8 中的查询包含一个关联子查询，返回订购了任何包含 'Nut' 名称产品的客户。注意外部表的`c_no`列与`c_order`表的`c_no`列相关。

## 使用关联子查询

```
SELECT customer.*
FROM customer
WHERE c_no IN
  (SELECT o.c_no
  FROM c_order o
  JOIN product p
  ON o.p_code = p.p_code
  WHERE p_name LIKE '%Nut%');
```

以下是查询结果。

| C_NO C_NAME |
|---|
| 40 Super Agent |
| 10 Standard Store |

## 总结

在本章中，你学习了各种类型的子查询，例如嵌套子查询和关联子查询。在接下来的章节中，你将应用本章学的内容来合并两个或多个查询的结果。

## 第7 章：复合查询

可以使用`UNION ALL`、`UNION`、`INTERSECT`或`MINUS`运算符合并两个或多个`SELECT`语句的结果。列的数量必须相同，相应的列必须具有相同的数据类型。本章展示了如何合并查询结果。

## UNION ALL

当使用`UNION ALL`运算符合并两个或多个查询时，整体输出将是所有查询的结果。例如，查看列表 7.1 中的查询。

列表 7.1：使用 UNION ALL

```
SELECT p_code, p_name, 'FIRST QUERY'
FROM product p WHERE p_name LIKE '%Nut%'
UNION ALL
SELECT p.p_code,
p_name,
'SECOND_QUERY'
FROM c_order o
INNER JOIN product p
ON o.p_code = p.p_code;
```

注意第一个和第二个`SELECT`语句中的 'FIRST QUERY' 和 'SECOND_QUERY' 字面量仅用于标识行从何来。

## 74 Oracle SQL：初学者教程

假设`product`表具有以下行：

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | New Nut | 30.00 | 01-MAY-13 |

并且`c_order`表包含以下记录：

| C_NO | P_CODE | QTY | ORDER_DT |
|---|---|---|---|
| 10 | 1 | 100 | 01-APR-13 |
| 10 | 2 | 100 | 01-APR-13 |
| 20 | 1 | 200 | 01-APR-13 |
| 40 | 4 | 400 | 02-APR-13 |
| 40 | 5 | 400 | 03-APR-13 |
| 30 | 3 | 300 | 02-APR-13 |

列表 7.1 中的查询将返回以下输出。

| P_CODE | P_NAME | QUERY |
|---|---|---|
| 3 | Nut | FIRST QUERY |
| 5 | Super_Nut | FIRST QUERY |
| 6 | New Nut | FIRST QUERY |
| 1 | Nail | SECOND_QUERY |
| 1 | Nail | SECOND_QUERY |
| 2 | Washer | SECOND_QUERY |
| 3 | Nut | SECOND_QUERY |
| 4 | Screw | SECOND_QUERY |
| 5 | Super_Nut | SECOND_QUERY |

注意列表 7.1 查询的输出汇总了第一个`SELECT`语句的所有记录，紧接着是第二个`SELECT`语句的行。你当然可以使用`ORDER`子句来重新排序。例如，列表 7.2 中的查询通过使用`ORDER BY`子句对`p_code`列进行排序修改了列表 7.1 中的查询。

### 列表 7.2：对复合查询的输出行进行排序

```
SELECT p_code, p_name, 'FIRST QUERY'
FROM product p WHERE p_name LIKE '%Nut%'
UNION ALL
SELECT p.p_code,
p_name,
'SECOND_QUERY'
FROM c_order o
INNER JOIN product p
on o.p_code = p.p_code
ORDER BY p.p_code;
```

列表 7.2 的查询结果如下。

| P_CODE | P_NAME | QUERY |
| --- | --- | --- |
| 1 | Nail | SECOND_QUERY |
| 2 | Nail | SECOND_QUERY |
| 3 | Washer | SECOND_QUERY |
| 4 | Nut | SECOND_QUERY |
| 5 | Nut | FIRST_QUERY |
| 6 | Screw | SECOND_QUERY |
| 7 | Super_Nut | SECOND_QUERY |
| 8 | Super_Nut | FIRST_QUERY |
| 9 | New Nut | FIRST_QUERY |

## UNION

`UNION`与`UNION ALL`相似。但使用`UNION`时，重复行只返回一次。例如，考虑包含两个`SELECT`元素的列表 7.3 中的查询。

### 列表 7.3：使用 UNION



```
SELECT p_code,
p_name
FROM product p
WHERE p_name LIKE '%Nut%'
UNION
SELECT p.p_code,
p_name
```

```sql
FROM c_order o
INNER JOIN product p
ON o.p_code = p.p_code
ORDER BY p_code;
```

这里是查询的输出。

```
P_CODE P_NAME
----- -------
1 Nail
2 Washer
3 Nut
4 Screw
5 Super Nut
6 New Nut
```

## INTERSECT（交集）

当你使用`INTERSECT`运算符结合两个或多个查询时，输出将包含所有参与的`SELECT`语句共同拥有的行。换句话说，只有当某行被所有`SELECT`语句返回时，该行才会被包含在最终结果中。

让我们来看列表 7.4 中的示例。

### 列表 7.4：使用 INTERSECT

```sql
SELECT p.p_code,
p_name
FROM product p
WHERE p_name LIKE '%Nut%'
INTERSECT
SELECT p.p_code,
p_name
FROM c_order o
INNER JOIN product p
ON o.p_code = p.p_code
ORDER BY p_code;
```

在相同的`product`和`c_order`表上运行该查询将返回以下结果。

```
P_CODE P_NAME
----- ------
3 Nut
5 Super_Nut
```

## MINUS（相减）

当你使用`MINUS`运算符结合两个`SELECT`语句时，最终输出将来自第一个查询但未被第二个查询返回的行。查看列表 7.5 中的示例。

### 列表 7.5：使用 MINUS

```sql
SELECT p_code,
p_name
FROM product p
WHERE p_name LIKE '%Nut%'
MINUS
SELECT p.p_code,
p_name
FROM c_order JOIN product p
ON o.p_code = p.p_code
ORDER BY p_code;
```

在相同的`product`和`c_order`表上运行此查询会产生以下输出。

```
P_CODE P_NAME
----- ------
6 New Nut
```

使用`MINUS`时，构成查询的`SELECT`语句的顺序非常重要。如果你交换了列表 7.5 查询中两个`SELECT`语句，输出将完全不同。查看列表 7.6 中的查询，它与列表 7.5 中的查询完全相同，仅是两个`SELECT`语句被交换了。

### 列表 7.6：在结合 MINUS 的查询中交换参与的 SELECT 语句

```sql
SELECT p.p_code,
p_name
FROM c_order o
INNER JOIN product p
ON o.p_code = p.p_code
MINUS
SELECT p.p_code,
p_name
FROM product p
WHERE p_name LIKE '%Nut%%'
ORDER BY p_p_code;
```

列表 7.6 中查询的输出如下：

| P_CODE | P_NAME |
| --- | --- |
| 1 | Nail |
| 2 | Washer |
| 4 | Screw |

## 总结

在本章中，你学习了可以组合两个或多个`SELECT`语句的输出。你有五种运算符可以此目的：`UNION ALL`、`UNION`、`INTERSECT`和`MINUS`。

# 第 8 章

## 视图 (Views)

视图实质上是一个预定义的查询。你最频繁地创建和使用视图是为了出于以下目的：

- 隐藏表列（为了安全保护）
- 展示预计算的列（代替表列）
- 隐藏查询（以便无需运行查询即可获得查询输出）

本章讨论了视图并展示了视图的示例。

## 创建和使用视图

你使用`CREATE VIEW`语句创建视图。其语法如下。

```sql
CREATE VIEW view_name (columns) AS SELECT ...;
```

`CREATE VIEW`语句末尾的`SELECT`语句是预定义的查询。当你使用视图时，会执行其预定义的查询。由于查询结果是一个没有持久化（存储）在数据库中的表，因此视图也被称为虚拟表。视图`SELECT`语句中的表被称为基表。

你使用视图的原因之一是你有一个需要与他人共享的表时。如果你不想让其他人看到某些表列，可以使用视图来隐藏这些列。然后你可以共享该视图，并限制对基表的访问。

例如，列表 8.1 显示了基于`product`表创建名为`product_v`视图的`SQL`语句。该视图隐藏了基表的价格列。

### 列表 8.1：使用 VIEW 隐藏列

```sql
CREATE VIEW product_v
( p_code , p_name
) AS
SELECT p_code, p_name FROM product;
```

现在可以像使用任何数据库表一样使用`product_v`。例如，以下语句显示了`product_v`视图中的所有列。

假设`product`表包含以下行：

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | New Nut | 30.00 | 01-MAY-13 |

从`product_v`视图选择所有列将返回这些行。

| P_CODE | P_NAME |
|---|---|
| 1 | Nail |
| 2 | Washer |
| 4 | Screw |

注意，在数据库中视图名称必须在数据库中所有视图和表之间是唯一的。

视图的另一个用途是派生基表中不可用的计算列。这里有一个示例。

假设`product`表存储了每个产品的利润率如下所示。

| P_CODE | P_NAME | PRICE | LAUNCH_DT | MARGIN |
| --- | --- | --- | --- | --- |
| 1 | Nail | 10.00 | 31-MAR-13 | 1 |
| 2 | Washer | 15.00 | 29-MAR-13 | 2 |
| 3 | Nut | 15.00 | 29-MAR-13 | 3 |
| 4 | Screw | 25.00 | 30-MAR-13 | 4 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 | 5 |
| 6 | New Nut | 30.00 | 01-MAY-13 | 6 |

如果你想在视图中查看每个产品的利润率，可以创建一个计算它的视图。这里是列表 8.2 中的示例。

```sql
CREATE VIEW product_margin
( p_code, p_name, margin
) AS
SELECT p_code, p_name, price * 0.1 AS margin
FROM product;
```

现在像使用任何数据库表一样使用`product_margin`视图。例如，以下语句显示了`product_margin`视图中的所有列。

| P_CODE | P_NAME | MARGIN |
|---|---|---|
| 1 | Nail | 1 |
| 2 | Washer | 1.5 |
| 3 | Nut | 1.5 |
| 4 | Screw | 2.5 |
| 5 | Super_Nut | 3 |
| 6 | New Nut | 3 |

视图的另一个用途是连接多个表。这里是列表 8.3 中的示例。

```sql
CREATE VIEW order_details
( o_id, p_name, order_date
) AS
SELECT o.o_id, p.p_name, o.order_date
FROM c_order o
INNER JOIN product p
ON o.p_code = p.p_code;
```

现在可以像使用任何数据库表一样使用`order_details`视图。例如，以下语句显示了`order_details`视图中的所有列。

| O_ID | P_NAME | ORDER_DATE |
|---|---|---|
| 1001 | Nail | 01-JAN-23 |
| 1002 | Washer | 02-JAN-23 |
| 1003 | Nut | 03-JAN-23 |
| 1004 | Screw | 04-JAN-23 |
| 1005 | Super_Nut | 05-JAN-23 |
| 1006 | New Nut | 06-JAN-23 |

视图也可以用于过滤数据。这里是列表 8.4 中的示例。

```sql
CREATE VIEW expensive_products
( p_code, p_name
) AS
SELECT p_code, p_name
FROM product
WHERE price > 20;
```

现在可以像使用任何数据库表一样使用`expensive_products`视图。例如，以下语句显示了`expensive_products`视图中的所有列。

| P_CODE | P_NAME |
|---|---|
| 4 | Screw |
| 5 | Super_Nut |
| 6 | New Nut |

总结，视图是`SQL`中一种强大的工具。它们可用于简化查询、提高安全性并提供数据抽象。

```
PRODUCT_SELL_V
PRODUCT_V
PROD_SUBS_V
PS_NONAME_V
```

要删除视图，请使用`DROP VIEW`语句。`DROP VIEW`语句的语法如下。

```
DROP VIEW view_name;
```

例如，列表 8.5 中的语句将删除`ps_noname_v`视图。

### 列表 8.5：删除 ps_noname_v 视图

```
DROP VIEW ps_noname_v;
```

运行列表 8.5 中的语句后，再次列出数据库中的视图将得到以下结果。

| VIEW_NAME |
| --- |
| PRODUCT_SELL_V |
| PROD_SUBS_V |

## 总结

视图是一个预定义的查询，你可以用它来隐藏列、包含预计算的列等。在本章中，你学习了如何创建和管理视图。

# 第 9 章

## 内置函数

Oracle 数据库提供了你可以在查询中使用的函数。这些内置函数可以分为数值函数、字符函数、日期/时间函数以及处理空值的函数。本章的目的是向你介绍其中的一些函数。

## 数值函数

以下是一些较重要的数值函数。

### ABS

`ABS(n)`返回`n`的绝对值。例如，下列查询将`(price - 20.00)`的绝对值作为第三列返回。

```
SELECT p_code, price, (price - 20), ABS(price - 20.00) FROM product;
```

将该查询应用于此产品表

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
| --- | --- | --- | --- |
| 1 | Nail | 10 | 31-MAR-13 |
| 2 | Washer | 15 | 29-MAR-13 |
| 3 | Nut | 15 | 29-MAR-13 |
| 4 | Screw | 25 | 30-MAR-13 |
| 5 | Super_Nut | 30 | 30-MAR-13 |
| 6 | Newer Nut | 15 | 01-MAY-13 |

你将得到此结果。

| P_CODE | PRICE | PRICE-20.00 | ABS (PRICE-20.00) |
| --- | --- | --- | --- |
| 1 | 10 | -10 | 10 |
| 2 | 15 | -5 | 5 |
| 3 | 15 | -5 | 5 |
| 4 | 25 | 5 | 5 |
| 5 | 30 | 10 | 10 |
| 6 | 15 | -5 | 5 |

### ROUND

`ROUND(n, d)`返回舍入到特定小数位数的数字。参数`n`是要舍入的数字，`d`是小数位数。例如，接下来的查询使用`ROUND`将数字舍入到一位小数。

```
SELECT p_code, ROUND (price, 1) FROM product;
```

假设产品表包含这些行

| P_CODE | P_NAME | PRICE | LAUNCH_DT | S_CODE |
| --- | --- | --- | --- | --- |
| 1 | Nail | 10.15 | 31-MAR-13 | NULL |
| 2 | Washer | 15.99 | 29-MAR-13 | NULL |
| 3 | Nut | 15.5 | 29-MAR-13 | 6 |
| 4 | Screw | 25.25 | 30-MAR-13 | NULL |
| 5 | Super_Nut | 30.33 | 30-MAR-13 | NULL |
| 6 | Newer Nut | 15.55 | 01-MAY-13 | NULL |

该查询的输出为：

| P_CODE | PRICE | ROUND (PRICE,1) |
| --- | --- | --- |
| 1 | 10.15 | 10.2 |
| 2 | 15.99 | 16 |
| 3 | 15.5 | 15.5 |
| 4 | 25.25 | 25.3 |
| 5 | 30.33 | 30.3 |
| 6 | 15.55 | 15.6 |

### SIGN

`SIGN(n)`返回一个表示`n`符号的值。该函数在`n < 0`时返回`-1`，`n = 0`时返回`0`，`n > 0`时返回`1`。例如，接下来的查询使用`SIGN`返回`(price - 15)`的符号。

```
SELECT p_code, price, SIGN(price - 15) FROM product;
```

假设产品表有以下记录

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
| --- | --- | --- | --- |
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super_Nut | 30.00 | 30-MAR-13 |
| 6 | Newer Nut | 15.00 | 01-MAY-13 |

查询的输出如下：

| P_CODE | PRICE | SIGN(PRICE-15) |
| --- | --- | --- |
| 1 | 10.00 | -1 |
| 2 | 15.00 | 0 |
| 3 | 15.00 | 0 |
| 4 | 25.00 | 1 |
| 5 | 30.00 | 1 |
| 6 | 15.00 | 0 |

### TRUNC

`TRUNC(n, d)`将数字截断到指定的小数位数。参数`n`是要截断的数字，`d`是小数位数。例如，接下来的查询返回截断到一位小数的结果。

```
SELECT p_code, TRUNC(price, 1) FROM product;
```

假设产品表包含这些行

| P_CODE | P_NAME | PRICE | LAUNCH_DT | S_CODE |
| --- | --- | --- | --- | --- |
| 1 | Nail | 10.15 | 31-MAR-13 | NULL |
| 2 | Washer | 15.99 | 29-MAR-13 | NULL |
| 3 | Nut | 15.5 | 29-MAR-13 | 6 |
| 4 | Screw | 25.25 | 30-MAR-13 | NULL |
| 5 | Super_Nut | 30.33 | 30-MAR-13 | NULL |
| 6 | Newer Nut | 15.55 | 01-MAY-13 | NULL |

该查询的输出为：

| P_CODE | PRICE | TRUNC(PRICE,1) |
| --- | --- | --- |
| 1 | 10.15 | 10.1 |
| 2 | 15.99 | 15.9 |
| 3 | 15.5 | 15.5 |
| 4 | 25.25 | 25.2 |
| 5 | 30.33 | 30.3 |
| 6 | 15.55 | 15.5 |

## 字符函数

以下是一些重要的字符函数。

### CONCAT



`CONCAT(string1, string2)`连接`string1`和`string2`并返回结果。如果你传递数字作为参数，该数字将首先转换为字符串。在接下来的示例中，三个字符串`p_name`、连字符和`price`被连接在一起。

```
SELECT p_code, CONCAT(CONCAT(p_name, ' - '), price) FROM product;
```

`price`列的值将自动转换为字符串。

产品表包含以下行：

| P_CODE | P_NAME | PRICE | LAUNCH_DT | S_CODE |
| --- | --- | --- | --- | --- |
| 1 | Nail | 10.15 | 31-MAR-13 | NULL |
| 2 | Washer | 15.99 | 29-MAR-13 | NULL |
| 3 | Nut | 15.5 | 29-MAR-13 | 6 |
| 4 | Screw | 25.25 | 30-MAR-13 | NULL |
| 5 | Super_Nut | 30.33 | 30-MAR-13 | NULL |
| 6 | Newer Nut | 15.55 | 01-MAY-13 | NULL |

对该表执行查询将返回以下结果：

```
P_CODE CONCAT (CONCAT(P_NAME,'--'),PRICE)

1 Nail -- 10.15
2 Washer -- 15.99
3 Nut -- 15.5
4 Screw -- 25.25
5 Super_Nut -- 30.33
6 Newer Nut -- 15.55
```

你可以使用`||`运算符来连接字符串。接下来的查询产生与上面相同的输出：

```
SELECT p_code, p_name || ' -- ' || price FROM product;
```

`LOWER`和`UPPER(str)`将`str`转换为小写，`UPPER(str)`将`str`转换为大写。例如，接下来的查询使用了`LOWER`和`UPPER`：

```
SELECT p_name, LOWER(p_name), UPPER(p_name) FROM product;
```

对产品表执行查询将给你此结果：

| | | START_DATE | END_DATE |
|---|---|---|---|
| 3 | 29-MAR-13 | 29-APR-13 |
| 4 | 30-MAR-13 | 29-APR-13 |
| 5 | 30-MAR-13 | 29-APR-13 |
| 6 | 01-MAY-13 | 29-APR-13 |

### TO_CHAR

`TO_CHAR(dt, fmt_specifier)`将日期（`dt`）转换为由`fmt_specifier`指定格式的字符串。在下面的示例中，`launch_dt`列使用的格式指定包含三个部分：

- `DD` - 日
- `MONTH` - 大写的月份
- `YYYY` - 年

```sql
SELECT p_code, TO_CHAR(launch_dt, 'DD MONTH YYYY') reformatted_dt
FROM product;
```

运行该查询将得到如下结果：

```
P_CODE REFORMATTED_DT

31 MARCH 2013
29 MARCH 2013
29 MARCH 2013
30 MARCH 2013
30 MARCH 2013
01 MAY 2013
```

## NULL 相关函数

以下是可用于处理`NULL`值的函数。

### COALESCE

`COALESCE(expr1, expr2, ..., expr-n)`返回列表中第一个非`NULL`的表达式。例如，假设`product`表包含以下行：

| P_CODE | P_NAME | LAUNCH_DT | MIN_PRICE |
|---|---|---|---|
| 1 | Nail | 31-MAR-13 | 10.00 | NULL |
| 2 | Washer | 29-MAR-13 | 15.00 | NULL |
| 3 | Nut | 29-MAR-13 | 15.00 | 12.00 |
| 4 | Screw | 30-MAR-13 | 20.00 | 17.00 |
| 5 | New Nut | 01-APR-13 | NULL | 10.00 |
| 6 | Newer Nut | 01-MAY-13 | NULL | NULL |

并且你想使用以下公式查看产品的`sale_price`列：

- 如果`price`可用（非`NULL`），则打 90% 折
- 如果`price`不可用，则返回`min_price`
- 如果`price`和`min_price`均不可用，返回`5.0`

你可以使用`COALESCE`来产生`sale_price`值：

```sql
SELECT p_name, price, min_price,
COALESCE(price * 0.9, min_price, 5.0) sale_price
FROM product;
```

此是查询结果：

| P_NAME | PRICE | MIN_PRICE | SALE_PRICE |
|---|---|---|---|
| Nail | 10.00 | NULL | 9 |
| Washer | 15.00 | NULL | 13.5 |
| Nut | 15.00 | 12.00 | 13.5 |
| Screw | 20.00 | 17.00 | 18 |
| New Nut | NULL | 10.00 | 10 |
| Newer Nut | NULL | NULL | 5 |

### NULLIF

`NULLIF(expr1, expr2)`比较`expr1`和`expr2`。如果它们相等，函数返回`NULL`。如果不相等，函数返回`expr1`。

假设你将产品价格存储在名为`old_price`的表中。例如，下面的`old_price`表显示`p_code = 3`的 Nut 产品的两个旧价格：

```
P_CODE P_NAME   PRICE LAUNCH_DT
------------------------------------
3      Nut         15.00 01-MAR-10
3      Newer Nut   12.00 01-APR-12
```

假设你想显示旧产品的当前价格。以下采用`NULLIF`函数的查询可以解决你的问题：

```sql
SELECT p_code,
p_name,
NULLIF(p.price, op.price) current_price
FROM product p
JOIN old_product op USING (p_code);
```

对以下`product`表和`old_price`表应用查询：

```
P_CODE P_NAME   PRICE LAUNCH_DT
------------------------------------
1      Nail        10.00 31-MAR-13
2      Washer      15.00 29-MAR-13
3      Better Nut  10.00 01-MAY-13
4      Screw       15.00 01-MAY-13
```

返回的两个旧 Nut 如下：

```
P_CODE P_NAME   CURRENT_PRICE
----------------------------
3      Nut             10
3      Newer Nut       10
```

### NVL

`NVL(expr1, expr2)`如果`expr1`不是`NULL`，则返回`expr1`；否则，返回`expr2`。

例如，假设你想比较旧价格和当前价格。在以下查询中应用`NVL`，如果产品从未被更新，则从`product`表中获取旧价格；否则，如果产品已被更新过，其旧价格将来自`old_product`表。

```sql
SELECT p_code,
p.p_name,
p.price current_price,
NVL(op.price, p.price) old_price
FROM product p
LEFT OUTER JOIN old_product op USING (p_code);
```

这是结果：

| P_CODE | P_NAME | CURRENT_PRICE | OLD_PRICE |
|---|---|---|---|
| 1 | Nail | 10 | 10 |
| 2 | Washer | 15 | 15 |
| 3 | Nut | 10 | 12 |
| 4 | Nut | 10 | 15 |
| 5 | Screw | 15 | 15 |

显示只有 Nut 被更新了，并且更新了两次。因此，它的旧价格来自`old_price`表。其他产品从未被更新，所以它们的当前和旧价格相同。它们的旧价格来自`product`表，因为`op.price`列的参数是`NULL`。

## 总结

你学习了一些可以在 Oracle 数据库中使用的内置函数。如果你想了解更多内置函数，请查阅 Oracle 手册。

## PL/SQL

`PL/SQL`是 Procedural Language（过程语言）的缩写，它补充了 SQL。本章的目标是介绍常用的`PL/SQL`特性，例如：

- 行处理查询输出
- if-then-else 逻辑
- 异常处理
- 用户自定义函数

## 行处理

在之前的章节中，你已经了解到查询的输出可以有多行。你可以编写一个`PL/SQL`程序来处理查询输出。行处理的`PL/SQL`程序结构如下：

```sql
BEGIN
FOR output_row IN (
  SELECT ...)
LOOP
...
END LOOP;
END;
```

### 示例 10.1: 行处理

示例中的程序使用了连接查询，其输出存储在名为`inv`的变量中。在循环中，`inv`的每行都被插入到`invoice`表中：

```sql
BEGIN
  FOR inv IN
    (SELECT c_no,
      c_name,
      p_name,
      qty,
      price * prc, total_prc,
      sysdate as invoice_dt,
      launch_dt
    FROM c_order
    JOIN product
    JOIN customer)
  LOOP
    INSERT INTO invoice
    (
      inv.c_no,
      inv.c_name,
      inv.p_name,
      inv.qty,
      inv.unit_prc,
      inv.total_prc,
      inv.invoice_dt
    );
  END LOOP;
```

假设你有`c_order`、`customer`和`product`表，分别如表 10.1、10.2 和 10.3，并且你还有一个空的`invoice`表。

### 表 10.1: c_order 表

| C_NO | Store | C_DATE |
|---|---|---|
| 10 | Standard Store | 25-JUL-13 |
| 20 | Quality Store | 27-JUL-13 |
| 30 | Head Office | 19-JUL-13 |
| 40 | Super Agent | 14-JUL-13 |

### 表 10.2: customer 表

| P_CODE | P_NAME | PRICE | LAUNCH_DT |
|---|---|---|---|
| 1 | Nail | 10.00 | 31-MAR-13 |
| 2 | Washer | 15.00 | 29-MAR-13 |
| 3 | Nut | 15.00 | 29-MAR-13 |
| 4 | Screw | 25.00 | 30-MAR-13 |
| 5 | Super Nut | 30.00 | 30-MAR-13 |
| 6 | New Nut | NULL | NULL |

### 表 10.3: product 表

如果你在 SQL*Plus 中输入并执行示例 10.1 中的`PL/SQL`程序，你的 SQL*Plus 屏幕将如图 10.1 所示。注意，执行`PL/SQL`程序需要在最后一个`END;`之后输入斜杠`/`。

![](img/45d34be9f5c11ea49c07c6bf553ed6_105_0.png)

```sql
SQL> BEGIN
  FOR inv IN
    (SELECT c_no,
      c_name,
      p_name,
      qty,
      price * prc, total_prc,
      sysdate as invoice_dt,
      launch_dt
    FROM c_order
    JOIN product NATURAL
    JOIN customer)
  LOOP
    INSERT INTO invoice
    (
      inv.c_no,
      inv.c_name,
      inv.p_name,
      inv.qty,
      inv.unit_prc,
      inv.total_prc,
      inv.invoice_dt
    );
  END LOOP;
END;
SQL> |
```

`PL/SQL`过程成功完成。

图 10.1：在 SQL*Plus 中执行`PL/SQL`程序

执行程序后，`invoice`表将填充以下行：

| C_NO C_NAME | P_NAME | QTY UNIT_PRC TOTAL_PRC | INVOICE_DT |
|---|---|---|---|---|
| 10 Standard Store | Washer | 100 | 15 | 1500 | 12-SEP-13 |
| 10 Standard Store | Nail | 100 | 10 | 1000 | 12-SEP-13 |

## If-Then-Else 决策逻辑

你可以使用`if`语句在程序中进行分支。例如，列表 10.2 中的 if-then-else 决策逻辑根据产品发布日期（`launch_dt`）对输出行进行不同的处理。

### 列表 10.2: If-then-else 决策逻辑

```
BEGIN
FOR invc IN
(SELECT c_no,
  c_name,
  p_name,
  qty,
  price unit_prc,
  (qty * price) total_prc,
  sysdate invoice_dt,
  launch_dt
FROM c_order NATURAL
JOIN product NATURAL
JOIN customer
)
LOOP
  IF invc.launch_dt IS NOT NULL THEN
    INSERT
    INTO invoice VALUES
    (
      invc.c_no,
      invc.c_name,
      invc.p_name,
      invc.qty,
      invc.unit_prc,
      invc.total_prc,
      invc.invoice_dt
    );
  ELSE
    NULL;
  END IF;
END LOOP;
END;
```

# 102 Oracle SQL: 初学者教程

对于此示例，我使用了一个包含以下行的`c_order`表。这个`c_order`表与上一个示例中使用的表的区别在于多了第六行，该行记录了某个产品（`p_co = 6`）的销售，且其`launch_dt`为空。

| C_NO | P_CO | QTY | ORDER_DT |
| :--- | :--- | :--- | :--- |
| 10 | 1 | 100 | 01-APR-13 |
| 10 | 2 | 100 | 01-APR-13 |
| 20 | 1 | 200 | 01-APR-13 |
| 40 | 4 | 400 | 02-APR-13 |
| 40 | 5 | 400 | 03-APR-13 |
| 40 | 6 | 600 | 01-MAY-13 |

由于产品的`launch_dt`为空，处理过程不会为这个额外的订单插入发票行。如果你执行列表 10.2 中的程序，则会将与上一个示例相同的行插入到`invoice`表中。`PL/SQL`中的异常处理允许你使用`EXCEPTION`语句来处理程序中的错误（或异常）。其语法如下：

```
EXCEPTION
  WHEN exception_name
  THEN exception_handling_statement;
```

例如，假设你想使用列表 10.3 中的`PL/SQL`程序从`invoice`表中查询特定的发票。列表 10.3 中的`SELECT`查询将其输出行存储在`invoc`变量中，该变量被定义为`ROWTYPE`数据类型。

### 列表 10.3: 不带异常处理的 PL/SQL 程序



```sql
DECLARE
  invc invoice%ROWTYPE;
BEGIN
  SELECT *
  INTO invoc
  FROM invoice
  WHERE c_no = '&c_no_prompt'
  AND p_name = '&p_name_prompt'
  AND TO_CHAR(invoice_dt, 'DD-MON-YY') = '&invoice_dt_prompt';
  dbms_output.put_line(invoc.c_name || ' - ' || invoc.p_name || ' - - ' || invoc.total_prc);
END;
```

# 第 10 章：PL/SQL 103

假设 `invoice` 表包含以下行。

| C_NO | C_NAME | P_NAME | QTY | UNIT_PRC | TOTAL_PRC | INVOICE_DT |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 10 | Standard Store | Washer | 100 | 15 | 1500 | 12-SEP-13 |
| 10 | Standard Store | Nail | 100 | 10 | 1000 | 12-SEP-13 |
| 20 | Quality Store | Nail | 200 | 10 | 2000 | 12-SEP-13 |
| 40 | Super Agent | Screw | 400 | 25 | 10000 | 12-SEP-13 |
| 40 | Super Agent | Super_Nut | 400 | 30 | 12000 | 12-SEP-13 |

如果你执行列表 10.3 中的程序，系统会提示你三次，输入要查询的发票 `c_no`、`p_name` 和 `invoice_dt`。如果 `invoice` 表中不存在该发票，程序将终止，并且你会看到“no data found”错误消息。你的 SQL*Plus 看起来如下所示。

```sql
SQL> DECLARE
2 invoc invoice%ROWTYPE;
3 BEGIN
4 SELECT *
5 INTO invoc
6 FROM invoc
7 WHERE c_no = '&c_no_prompt'
8 AND p_name = '&p_name_prompt'
9 AND TO_CHAR(invoice_dt, 'DD-MON-YY') = '&invoice_dt_prompt';
10 dbms_output.put_line(invoc.c_name || ' - ' || invoc.p_name || ' - - ' || invoc.total_prc);
11 END;
12 /\
Enter value for c_no_prompt: 10
old 7: WHERE c_no = '&c_no_prompt'
new 7: WHERE c_no = '10'
Enter value for p_name_prompt: Nail
old 8: AND p_name = '&p_name_prompt'
new 8: AND p_name = 'Nail'
Enter value for invoice_dt_prompt: 11-SEP-13
```

# 104 Oracle SQL: 初学者教程

```sql
old 9: AND TO_CHAR(invoice_dt, 'DD-MON-YY') =
  '&invoice_dt_prompt';
new 9: AND TO_CHAR(invoice_dt, 'DD-MON-YY') = '11-SEP-13';
```

```sql
DECLARE
*
ERROR at line 1:
ORA-01403: no data found
ORA-06512: at line 4
SQL>
```

为了处理错误（异常），你可以为列表 10.3 中的程序添加异常处理语句。列表 10.4 显示了列表 10.3 程序的修改版本。

### 列表 10.4: 带异常处理程序

```sql
DECLARE
  invc invoice%ROWTYPE;
BEGIN
  SELECT *
  INTO invoc
  FROM invoice
  WHERE c_no = '&c_no_prompt'
  AND p_name = '&p_name_prompt'
  AND TO_CHAR(invoice_dt, 'DD-MON-YY') = '&invoice_dt_prompt';
  dbms_output.put_line(invoc.c_name || ' - ' || invoc.p_name || ' - - ' || invoc.total_prc);
EXCEPTION
  WHEN NO_DATA_FOUND THEN
    dbms_output.put_line('Error: data not found');
END;
```

# 108 Oracle SQL：初学者教程

| TABLE_NAME | COMMENTS |
| --- | --- |
| ALL_XML_SCHEMAS | 用户有权引用的所有 XML Schema 描述 |
| ALL_XML_SCHEMAS2 | ALL_XML_SCHEMAS 的虚拟版本，不包含 XMLTYPE 列 |
| USER_RESOURCE_LIMITS | 显示用户的资源限制 |
| USER_PASSWORD_LIMITS | 显示用户的密码限制 |

`USER_CATALOG` 用户拥有的表、视图、同义名和序列

`ALL_CATALOG` 用户可以访问的所有表、视图、同义名、序列

`USER_CLUSTERS` 用户自己的簇的描述

`ALL_CLUSTERS` 用户可以访问的簇描述

`USER_CLU_COLUMNS` 表列到簇列的映射

`USER_COL_COMMENTS` 用户表和视图中列的注释

在上述列出的某些视图将在后续章节中进行解释。

### User_Catalog 视图

`user_catalog` 视图存储了你的表和视图的名称。使用列表 11.2 中的查询语句可以查看数据库中存在的表和视图。这些表和视图被称为用户表和视图（与系统表和视图相对）。

列表 11.2：使用 `user_catalog` 视图

```sql
SELECT * FROM user_catalog;
```

在你的数据库中运行列表 11.2 中的查询得到的输出可能与我在这里得到的完全不同。以下是我的输出。

| TABLE_NAME | TABLE_TYPE |
| --- | --- |
| CUSTOMER | TABLE |
| C_ORDER | TABLE |
| PRODUCT | TABLE |
| C_SHIP | TABLE |
| OLD_PRODUCT | TABLE |
| PRICE_LOG | TABLE |

### User_Tab_Cols 视图

你可以从 `User_Catalog` 视图获取表和视图名称。要查看每个表和视图的详细信息，你可以查询 `user_tab_cols` 视图。例如，列表 11.3 中的查询显示了 `product` 表的列名及其数据类型、长度、精度和度。

### 列表 11.4：查找 `product` 表的列元数据

这里是查询输出。

| COLUMN_NAME | DATA_TYPE | DATA_LENGTH | DATA_PRECISION | DATA_SCALE |
|---|---|---|---|---|
| P_CODE | VARCHAR2 | 6 | | |
| P_NAME | VARCHAR2 | 14 | | |
| PRICE | NUMBER | 22 | 4 | 2 |
| LAUNCH_DT | DATE | 7 | | |

除了这五列之外，`USER_TAB_COLS` 视图还有许多其他列，例如显示所有者和默认值的列。

### User_Procedures 视图

`user_procedures` 视图包含关于你的存储程序的信息，包括函数、过程和触发器。使用列表 11.5 中的查询显示你的存储过程。注意，该视图还有其他一些列，提供了更多关于存储程序的信息。

列表 11.5：揭示存储过程和函数的元数据

```sql
SELECT object_name, object_type FROM user_procedures;
```

在你的数据库上执行该查询将给你类似下方的输出行。

```sql
OBJECT_NAME        OBJECT_TYPE
-----------        -----------
CALC_NEW_PRICE      FUNCTION
UPD_PRICE           PROCEDURE
PRICE_UPD_LOGGING TRIGGER
```

### User_Source 视图

我解释的最后一个视图是 `user_source` 视图。该视图包含你的存储函数的源代码。例如，列表 11.6 中的查询返回了 `CALC_NEW_PRICE` 函数的源码。

列表 11.6：读取函数的源代码

```sql
SELECT line, text FROM user_source WHERE name = 'CALC_NEW_PRICE';
```

执行该查询将向你显示所示的函数代码行。

# 第 11 章：数据字典

| NAME | TYPE | LINE TEXT |
|---|---|---|
| CALC_NEW_PRICE | FUNCTION | 1 FUNCTION calc_new_price( |
| CALC_NEW_PRICE | FUNCTION | 2 exist_price NUMBER, |
| CALC_NEW_PRICE | FUNCTION | 3 inc NUMBER) |
| CALC_NEW_PRICE | FUNCTION | 4 RETURN NUMBER |
| CALC_NEW_PRICE | FUNCTION | 5 IS |
| CALC_NEW_PRICE | FUNCTION | 6 BEGIN |
| CALC_NEW_PRICE | FUNCTION | 7 RETURN exist_price + (exist_price * inc); |
| CALC_NEW_PRICE | FUNCTION | 8 END; |

## 总结

数据字典包含了你数据库的元数据。在本章中，你学习了使用数据字典中的某些视图。

# 附录 A

安装 Oracle Database XE

为了尝试书中的示例，你需要一个 Oracle 数据库。因为你需要创建表和其他对象，并存储和更新数据，最好拥有自己的数据库。幸运的是，你可以从 Oracle 网站下载 Oracle Database Express Edition（也称为 Oracle Database XE）。正如你将在本附录中学习到的，Oracle Database XE 自带了一个名为 SQL*Plus 的工具，你可以用它来运行 SQL 语句。

## 下载 Oracle Database XE

可以从此网页下载此数据库软件。

`http://www.oracle.com/technetwork/indexes/downloads/index.html`

向下滚动直到在列表中看到 Database 11g Express Edition 并点击链接。然后，选择适用于你版本的版本。正如你将在附录中学习到的，Oracle Database XE 自带了一个名为 SQL*Plus 的工具，你可以用它来运行 SQL 语句。

> **注意**：下文示例在 Windows 下测试。

## 安装 Oracle Database

解压下载的文件到本地驱动器中的文件夹，然后双击 `setup.exe` 文件。你会看到如图 A.1 所示的安装向导。

点击“下一步”，在如图 A.2 所示的许可窗口中接受协议。选择适用于你平台的版本（Windows 或 Unix）并按照说明操作。如果提示输入密码，你可能需要更改，例如默认密码。

点击“下一步”，在如图 A.3 所示的“选择目录”窗口中选择路径。点击“下一步”，你会看到如图 A.4 所示的摘要窗口。点击“安装”，在“安装完成”窗口中点击“完成”。

## 使用 SQL*Plus 创建用户

要运行 SQL*Plus，从 Windows 开始菜单中选择“Run SQL”，如图 A.5 所示。

SQL*Plus 将打开，如图 A.6 所示。SQL*Plus 是 Oracle 数据库的命令行客户端。你用它来输入和执行 SQL 语句以及 PL/SQL 程序。

通过输入以下命令并按回车连接 SYSTEM：

```sql
CONNECT SYSTEM/password AS SYSDBA;
```

这里，`password` 是你在期间输入的 SYSTEM 用户密码。要创建一个用户，输入并执行以下命令。

```sql
CREATE USER name IDENTIFIED BY password;
```

将 `name` 替换为你想要创建的用户名，将 `password` 替换为密码。例如，以下命令创建一个名为 `john` 密码为 `secret` 的用户。

```sql
CREATE USER john IDENTIFIED BY secret;
```

接下来，输入并执行以下命令，将 `name` 替换为上一个命令中的用户名：

```sql
GRANT ALL PRIVILEGES TO name;
```

`GRANT ALL` 命令赋予指定用户所有权限。在真实系统中，赋予用户所有权限可能不是明智之举。

该用户现在有权限测试书中的示例。要登录，在 SQL*Plus 中输入此命令：

```sql
CONNECT name/password;
```

例如

```sql
CONNECT john/secret;
```

安装过程中创建了一个名为“XE”的数据库。上面的 `CONNECT` 命令将你连接到此数据库。

你现在已准备好测试书中的示例。

# 附录 B

Oracle 内置数据类型

Oracle 数据库有 18 种内置数据类型，如表 B.1 所示。

| 数据类型 | 说明 |
| --- | --- |
| VARCHAR2(ml) | 最大长度为 ml 的变长度字符字符串 |
| NVARCHAR2(ml) | VARCHAR2 的 Unicode 版本 |
| NUMBER(p, s) | 精度为 p、标度为 s 的数字 |
| DATE | 有效范围从公元前 4712 年 1 月 1 日到公元 9999 年 12 月 31 日 |
| BINARY FLOAT | 32 位浮点数 |
| BINARY DOUBLE | 64 位浮点数 |
| TIMESTAMP | 日期的年、月、日值以及时间的时、分、秒值 |
| INTERVAL YEAR | 存储以年和月计算的时间段 |
| INTERVAL DAY | 存储以天、小时、分、秒计算的时间段 |
| RAW(size) | 长度为 size 字节的原始二进制数据 |
| LONG RAW | RAW 的更大版本 |
| ROWID | 表示表中行唯一地址的 Base-64 字符串 |
| CHAR(l) | 长度为 l 的固定长度字符 |
| NCHAR(l) | CHAR 的 Unicode 版本 |
| CLOB | 单字节或多字节字符的字符大对象 |
| NCLOB | CLOB 的 Unicode 版本 |
| BLOB | 二进制大对象 |
| BFILE | 包含存储在数据库外部的大文件的定位符 |

表 B.1：Oracle 内置数据类型

## 附录 C

索引

书籍索引部分的条目指向该词/短语的位置。索引条目帮助找到包含该词/短语的页。同样，列索引可以加快你在数据库中查找数据的速度。如果你的查询条件针对未索引的列（或列），将进行全表扫描，查询速度会比有索引时慢。

本附录展示了如何创建各种索引。涵盖的主题如下：

- 创建索引
- 多列索引
- 位图索引和连接位图索引
- 函数索引
- 删除索引

## 创建索引

要对表的某一列或若干列创建索引，请使用此语句。

```sql
CREATE INDEX index_on ON table (columns);
```

例如，列表 C.1 中的语句在 `product` 表的 `p_name` 列上创建一个名为 `p_name_ix` 的索引。

**列表 C.1：在 `product` 表的 `p_name` 上创建索引**

```sql
CREATE INDEX p_name_ix ON product (p_name);
```

## 唯一索引名称和列

你不能拥有重复的索引。此外，你不能对同一列（或列）进行多次索引。

## 多列索引

索引可以基于多个列。当你需要搜索在索引列上具有相同值的行时，多列索引非常有用。例如，如果你的查询必须搜索 `product` 表的 `p_name` 列，且可能有多个行具有相同的 `p_name` 但不同的发布日期，那么在 `p_name` 和 `launch_dt` 上都创建索引将会有帮助。

例如，列表 C.2 中的语句在 `product` 表的 `p_name` 和 `launch_dt` 列上创建了一个多列索引。

列表 C.2：在多个列上创建索引

```sql
CREATE INDEX p_name_launch_ix ON product (p_name, launch_dt);
```

## 位图索引

列表 C.1 和 C.2 中创建的索引是普通索引，技术上称为 B-tree 索引。对于行不会并发更改的表（例如低量数据输入环境），位图索引可能是更好的选择。`product` 表是这种低数据维护表的示例，因此适用于位图索引。相比之下，客户订单表的插入更频繁，不是位图索引的良好候选。

例如，列表 C.3 中的语句在 `c_order` 表上创建一个名为 `order_bix` 的位图索引。

列表 C.3：创建位图索引

```sql
CREATE BITMAP INDEX order_bix ON c_order (p_code, c_no);
```

## 连接位图索引



连接位图索引是位图索引的变体。连接位图索引专门用于加速从连接查询中从连接表中检索列。

例如，列表 C.4 中的语句在`c_name`列上创建了一个连接位图索引。注意，创建连接位图索引需要额外的子句：`FROM`和`WHERE`。这些子句定义了表之间的连接关系。

### 列表 C.4：在 c_name 列上创建连接位图索引

```
CREATE BITMAP INDEX c_name_bji ON c_order(c.c_name)
FROM c_order o, customer c
WHERE o.c_no = c.c_no;
```

如果`c_name`必须从`c_order`表扫描，现在可以使用索引更快地检索它。

虽然连接位图索引的目的是加速特定列的检索（列表 C.4 语句中的`c_name`），但连接表通常利用表的主键索引，因为它们大多基于这些键进行连接。如果你经常需要对其他列进行连接，你可能也想对这些列创建索引。

## 函数索引

在表中输入数据时，经常会出现大小写使用不一致的情况。有时列值全大写输入，有时全小写，有时是混合大小写。

例如，下面的客户表显示`c_name`列使用了不一致的大小写。

| C_NO | C_NAME | PHONE |
|---|---|---|
| 10 | Standard Store | 1-416-223-4455 |
| 20 | Quality store | 1-647-333-5566 |
| 30 | Branch Office | 1-416-111-2222 |
| 40 | Super Agent | 1-416-111-2222 |
| 50 | New Brand | 1-905-777-8888 |
| 60 | NEW STORE | 1-905-000-9999 |

这产生了一个问题，因为查询可能无法返回所有预期数据。例如，在客户表中，搜索“new”将找不到“STORE”。为了解决这个问题，你可以在查询中使用`c_name`列的`UPPER`版本，如 C.5 所示。

### 列表 C.5：在查询中使用 UPPER 函数

```
SELECT * FROM customer WHERE UPPER(c_name) LIKE '%STORE';
```

为了让此查询运行得更快，你还应该创建一个基于转换为大写的`c_name`列的索引。列表 C.6 展示了如何操作。

### 列表 C.6：一个函数索引

```
CREATE INDEX func_name_ix ON customer
(UPPER(c_name))
```

## 删除索引

要删除任何类型的索引，请使用`DROP INDEX`语句。例如，列表 C.7 中的语句删除了`s_name_bji`。

### 列表 C.7：删除连接位图索引

```
DROP INDEX s_name_bji;
```

# 128 Oracle SQL：初学者教程

- 字典视图...............................................................................................107
- `DISTINCT`关键字.............................................................................28
- 表达式...........................................................................................26
- 外键...............................................................................................47
- `FROM`子句................................................................................13
- 全外连接（`FULL outer join`）...........................................................53
- `GRANT ALL`命令............................................................................119
- 分组（group）................................................................................41
- `GROUP BY`子句...............................................................................41, 44
- `HAVING`子句...............................................................................43
- `HAVING`条件............................................................................43
- IBM..................................................................................................100
- if-then-else................................................................................20, 65
- `IN`运算符......................................................................................123
- 索引项.......................................................................................53
- 内连接（inner join）.......................................................................................7
- `INSERT`语句....................................................................................
- `INTERSECT`运算符................................................................................76
- `INTERVAL DAY`数据类型...............................................................................121
- `INTERVAL YEAR`数据类型...............................................................................121
- `IS NOT NULL`运算符......................................................................23
- `IS NULL`运算符.............................................................................23
- 连接（join）..................................................................................47
- `JOIN`子句...............................................................................47, 48
- `JOIN`关键字................................................................................48
- 左外连接（`LEFT outer join`）...............................................................................53
- `LENGTH`函数..............................................................................90
- `LIKE`运算符...............................................................................21, 22
- `LONG RAW`数据类型......................................................................121
- 元数据（metadata）...........................................................................................107
- `MINUS`运算符...............................................................................77
- MySQL..................................................................................................1
- `NATURAL`关键字............................................................................61
- `NCHAR`数据类型............................................................................121
- `NCLOB`数据类型............................................................................123
- `NOT IN`运算符...............................................................................65
- `NOT`运算符...............................................................................19, 23
- NULL..........................................................................................11, 42, 55
- `NULLIF`函数.............................................................................94
- `NUMBER`数据类型...........................................................................121
- `VARCHAR2`数据类型......................................................................121
- `NVL`函数..................................................................................95
- 运算符（operator）.............................................................................................16
- Oracle 数据库..................................................................................1, 5
- Oracle Database XE...........................................................................5
- 下载（downloading）..................................................................................113
- 安装（installation）.......................................................................................114
- `ORDER BY`子句...............................................................................74

# 索引 129

- `ORDER`子句.................................................................................... 41
- 外连接（out join）....................................................................................... 53
- PL/SQL........................................................................................................... 2, 97
- 谓词（predicate）..................................................................................... 16
- 主键（primary key）................................................................................................ 7, 47
- 查询（query）............................................................................................... 13
- 查询输出（query output）............................................................................................... 37
- `RAW`数据类型............................................................................................... 121
- RDBMS......................................................................................................... 1
- 关系型数据库（relational database）............................................................................... 5
- 右外连接（`RIGHT outer join`）.................................................................................. 53
- `ROLLBACK`命令............................................................................................. 10, 11
- `ROUND`函数.................................................................................. 36
- `ROWID`数据类型.................................................................................. 121
- `ROWNUM`....................................................................................................... 27
- `SELECT`子句.................................................................................. 13, 14, 26
- `SELECT`语句..............................................................................................



# 索引

- `SIGN` 函数：13, 15, 18, 48, 74, 79
- `SQL`：87
  - 2008 标准：1
  - 2011 标准：1
  - `SQL` 留字
- `SQL*Plus`：5
- 结构化查询语言（`Structured Query Language`）
- 子查询（`subquery`）：63, 66
  - 比较运算符（`comparison operator`）：65
  - 多行（`multiple-row`）：65
  - 嵌套（`nested`）：69
  - 单行（`single-row`）：63
- `SUBSTR` 函数：90
- 表别名（`table alias`）：50
- `TIMESTAMAP` 数据类型：121
- `TO.CHAR` 函数：92
- `TRUNC` 函数：87
- `UNION ALL` 运算符：73
- `UPDATE` 语句：9, 11
- `UPPER` 函数：89
- `user_catalog` 视图：108
- `user_procedures` 视图：110
- `user_source` 视图：110
- `user_tab_cols` 视图：109
- `USING` 关键字：61
- `VARCHAR2` 数据类型：121
- 视图（`view`）：79
  - 嵌套（`nested`）：83
  - 视图管理（`view management`）：83
- `WHERE` 子句：9, 10, 13, 44, 65
- `WHERE` 条件（`WHERE condition`）：11, 43, 68
- 通配符：22
