

# Cassandra 查询备忘单

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/cassandra-query-cheat-sheet>

## 1. 介绍

有时，我们需要快速参考指南来开始我们的学习之路。特别是，备忘单是包含所有关键信息的文档。

在本教程中，我们将学习 Cassandra 查询语言（CQL）的基本概念，以及如何使用我们一路构建的备忘单来应用它们。

## 2. Cassandra 一瞥

[Apache Cassandra](/web/20220528143413/https://www.baeldung.com/cassandra-with-java) 是一个开源的、NoSQL 和[分布式数据存储系统](/web/20220528143413/https://www.baeldung.com/cs/distributed-systems-guide)。这意味着它不是只能在一台服务器上运行，而是可以在多台服务器上传播。它还以其高可用性和分区容忍度而闻名。

换句话说，Cassandra 数据库的设计灵感来自于 [CAP 定理](/web/20220528143413/https://www.baeldung.com/cs/brewers-cap-theorem)的“AP”。

此外，**Cassandra 是一种无主架构，可大规模扩展，最重要的是，它提供了简单的故障检测和恢复**。

## 3. 数据类型

通常，Cassandra 支持丰富的数据类型。这些类型包括本机类型、集合类型、用户定义的类型和元组，以及自定义类型。

### 3.1. 本地类型

原生类型是内置类型，为 Cassandra 中的一系列常量提供支持。

首先，字符串是编程世界中非常流行的数据类型。

CQL 为字符串提供了四种不同的数据类型：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `ASCII` | `string` | ASCII 字符串 |
| `inet` | `string` | IPv4 或 IPv6 地址字符串 |
| `text` | `string` | UTF8 编码字符串 |
| `varchar` | `string` | UTF8 编码字符串 |

布尔值有两个可能的值，要么是`true`要么是`false`：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `boolean` | `boolean` | `true`或`false` |

使用 `blob` 数据类型，我们可以将图像或多媒体数据作为二进制流存储在数据库中：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `blob` | `blob` | 任意字节 |

持续时间是一个三符号整数，表示月、日和纳秒：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `duration` | `duration` | 持续时间值 |

Cassandra 为整数数据提供了广泛的数据类型：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `tinyint` | `integer` | 8 位有符号整数 |
| `smallint` | `integer` | 16 位有符号整数 |
| `int` | `integer` | 32 位有符号整数 |
| `bigint` | `integer` | 64 位有符号长整型 |
| `varint` | `integer` | 任意精度整数 |
| `counter` | `integer` | 计数器列（64 位有符号） |

对于整型和浮点型，我们有三种数据类型：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `decimal` | `integer, float` | 可变精度小数 |
| `double` | `integer, float` | 64 位浮点 |
| `float` | `integer, float` | 32 位浮点 |

对于与日期和时间相关的需求，Cassandra 提供了三种数据类型：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `date` | `integer, string` | 日期值（不带时间） |
| `time` | `integer, string` | 时间值（无日期） |
| `timestamp` | `integer, string` | 时间戳（带有日期和时间） |

通常，在使用插入或更新命令时，我们必须避免冲突：

| **数据类型** | **支持的常量** | **描述** |
| --- | --- | --- |
| `uuid` | `uuid` | UUID（任何版本） |
| `timeuuid` | `uuid` | 第一版 UUID |

### 3.2. 集合类型

当用户对关系数据库中的一个字段有多个值时，通常将它们存储在一个单独的表中。例如，用户有许多银行帐户、联系信息或电子邮件地址。因此，在这种情况下，我们需要在两个表之间应用连接来检索所有数据。

Cassandra 提供了一种使用集合类型将数据分组并存储在一列中的方法。

让我们快速看一下这些类型：

*   `set` – 独特的价值观；存储为未订购
*   `list` – 可以包含重复值；秩序至关重要
*   `map` – 键值对形式的数据存储

### 3.3. 用户定义的类型

用户定义的类型允许我们在一列中附加多个数据字段：

```java
CREATE TYPE student.basic_info (
  birthday timestamp,
  race text,
  weight text,
  height text
);
```

### 3.4. 元组类型

元组是用户定义类型的替代形式。它使用尖括号和逗号分隔符来分隔它包含的元素类型。

下面是一个简单元组的命令：

```java
-- create a tuple
CREATE TABLE subjects (
  k int PRIMARY KEY,
  v tuple<int, text, float>
);

-- insert values
INSERT INTO subjects  (k, v) VALUES(0, (3, 'cs', 2.1));

-- retrieve values
SELECT * FROM subjects;
```

## 4. Cassandra CQL 命令

让我们来看几类 CQL 命令。

### 4.1. 键盘命令

首先要记住的是，Cassandra 中的键空间很像 RDBMS 中的数据库。它是数据的最外层容器，定义复制策略和其他选项，特别是对于所有的键空间表。记住这一点，一个好的通用规则是每个应用程序一个键空间。

让我们看看相关的命令：

| **命令** | **例子** | **描述** |
| --- | --- | --- |
| `CREATE KEYSPACE` | `CREATE KEYSPACE keyspace_name` WITH replication = { 'class' : 'SimpleStrategy', 'replication_factor' : 2}; | 创建一个密钥空间。 |
| `DESCRIBE KEYSPACE` | `DESCRIBE KEYSPACE;` | 它会列出所有的关键空间。 |
| `USE KEYSPACE` | `USE keyspace_name;` | 这个命令将客户端会话连接到一个密钥空间。 |
| `ALTER KEYSPACE` | `ALTER KEYSPACE keyspace_name WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 3 } AND DURABLE_WRITES = false;` | 改变一个键区。 |
| `DROP KEYSPACE` | `DROP KEYSPACE keyspace_name;` | 删除一个键空间。 |

### 4.2. 表格命令

在 Cassandra 中，表也被称为列族。我们已经知道了主键的重要性。但是，在创建表时必须定义主键。

让我们回顾一下这些命令：

| **命令** | **例子** | **描述** |
| --- | --- | --- |
| `CREATE TABLE` | `CREATE TABLE table_name ( column_name UUID PRIMARY KEY, column_name text, column_name text, column_name timestamp);` | 创建一个表。 |
| `ALTER TABLE` | `ALTER TABLE table_name ADD column_name int;` | 它将向表中添加一个新列。 |
| `ALTER TABLE` | `ALTER TABLE table_name ALTER column_name TYPE datatype;` | 我们可以更改现有列的数据类型。 |
| `ALTER TABLE` | `ALTER TABLE table_name WITH caching = {'keys' : 'NONE', 'rows_per_partition' : '1'};` | 该命令有助于改变表的属性。 |
| `DROP TABLE` | `DROP TABLE table_name;` | 放下一张桌子。 |
| `TRUNCATE TABLE` | `TRUNCATE table_name;` | 利用这一点，我们可以永久删除所有数据。 |

### 4.3. 索引命令

我们可以使用索引来加速查询，而不是扫描整个表并等待结果。然而，我们必须记住，Cassandra 中的主键已经被索引了。因此，它不能再次用于相同的目的。

让我们来看看这些命令：

| **命令** | **例子** | **描述** |
| --- | --- | --- |
| `CREATE INDEX` | `CREATE INDEX index_name ON table_name ( column_name);` | 创建索引。 |
| `DROP INDEX` | `DROP INDEX IF EXISTS index_name;` | 删除索引。 |

### 4.4. 基本命令

这些命令用于读取和操作表值：

| **命令** | **例子** | **描述** |
| --- | --- | --- |
| `INSERT` | `INSERT INTO table_name ( column_name1, column_name2) VALUES ( value1, value2);` | 在表中插入记录。 |
| `SELECT` | `SELECT * FROM table_name;` | 命令用于从特定的表中提取数据。 |
| `WHERE` | `SELECT * FROM table_name WHERE column_name = value;` | 它过滤掉谓词上的记录。 |
| `UPDATE` | `UPDATE table_name SET column_name2 = value2 WHERE column_name1 = value1;` | 它用于编辑记录。 |
| `DELETE` | `DELETE FROM table_name WHERE identifier = condition;` | 该语句从表中删除值。 |

### 4.5. 其他命令

Cassandra 有两种不同类型的键：分区键和聚集键。分区键指示存储数据的节点。

相比之下，聚集键决定了分区键中数据的顺序：

| **命令** | **例子** | **描述** |
| --- | --- | --- |
| `ORDER BY` | `SELECT * FROM table_name WHERE column_name1 = value ORDER BY column_name2 ASC;` | 为此，分区键必须在 WHERE 子句中定义。此外，ORDER BY 子句表示用于排序的聚类列。 |
| `GROUP BY` | `SELECT column_name FROM table_name GROUP BY condition1, condition2;` | 该子句仅支持 with Partition Key 或 Partition Key and Clustering Key。 |
| `LIMIT` | `SELECT * FROM table_name LIMIT 3;` | 对于大型表，限制检索的行数。 |

## 5. 运算符

Cassandra 支持算术运算符和条件运算符。在算术运算符下，我们有 `+`、`-`、`*`、`/`、`%`。

WHERE 子句在 Cassandra 中很重要。条件运算符在该子句中与[某些场景和限制](https://web.archive.org/web/20220528143413/https://www.datastax.com/blog/deep-look-cql-where-clause)一起使用。这些运算符是`CONTAINS`、`CONTAINS KEY`、`IN`、`=`、`>`、`>=`、`<`和`<=`。

## 6. 常见函数

毫无疑问，函数，无论是聚合函数还是标量函数，在将值从一个值转换到另一个值时都起着重要的作用。因此，Cassandra 在这两个类别中都提供了几个本地函数。

让我们来看看这些函数：

*   Blob 转换函数
*   UUID 和 Timeuuid 函数
*   令牌函数
*   WRITETIME 函数
*   TTL 功能
*   令牌函数
*   `MIN()`，`MAX()`，`SUM()`，`AVG()`

除了这些本地函数，它还允许用户定义函数和集合。

## 7. 结论

在这篇短文中，我们已经看到了 Cassandra 查询语言的构建模块。首先，我们研究了它支持的数据类型以及如何定义它们。然后，我们看了执行数据库操作的常见命令。最后，我们讨论了该语言的运算符和函数。

