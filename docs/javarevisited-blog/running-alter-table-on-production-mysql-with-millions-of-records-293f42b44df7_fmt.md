
# 在有数百万条记录的生产 MySql 上运行 ALTER TABLE

> 原文：<https://medium.com/javarevisited/running-alter-table-on-production-mysql-with-millions-of-records-293f42b44df7?source=collection_archive---------1----------------------->

有些事情我们不喜欢做，但是我们不得不做！

![](img/159db045d3d7c60fc38bfee090b8cf0b.png)

由[泰勒维克](https://unsplash.com/@tvick?utm_source=medium&utm_medium=referral)在 [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral) 上拍摄的照片

生产数据库上的模式变更一直是一个棘手的问题，当我们谈论数百万条记录时，这个问题就更加严重了，如果您过去在生产服务器上运行过变更，那么您就会知道，`ALTER TABLE`命令基本上是读取整个表的锁，然后短暂地写入锁。如果有数百万条记录，这意味着一个简单的`ADD COLUMN`将需要 20-30 分钟，并将导致生产停工。

> 注意：对于 MySQL 版本 < 5.6 锁是必需的，但是如果你使用的是 5.6+ 和 InnoDB，很多 [ALTER TABLE 操作都可以避免锁。](https://dev.mysql.com/doc/refman/5.6/en/innodb-online-ddl-operations.html)

## Percona 工具包救援助手🚀

![](img/1e8702bb53915ad7ac855b2f510d8aab.png)

[Percona Toolkit Helper](https://www.percona.com/doc/percona-toolkit/3.0) 自带`pt-online-schema-change`，其中的 [文档](https://www.percona.com/doc/percona-toolkit/3.0/pt-online-schema-change.html#name) …

> `pt-online-schema-change`在不阻塞读或写的情况下改变表的结构。在 DSN 中指定数据库和表。在阅读该工具的文档并仔细检查您的备份之前，请勿使用该工具。

基本上，`pt-online-schema-change`的工作方式类似于 MySql ALTER 的内部工作方式，但唯一的区别是它处理的是要更改的表的副本。下面是它在幕后做的事情：

1. 创建要修改的表的空副本，并根据需要修改它。
2. 复制原始表中的内容，并从原始表中创建触发器，以便在发生任何更新时更新新表中的相应行。
3. 数据是以小块的形式复制的，这可以根据用户来控制，我们稍后会谈到这一点。
4. 当复制完成时，它同时对原始表和新表进行原子重命名，并删除原始表 post。

在整个过程中，原始数据库是空闲的，可以为读写流量提供服务。

## 安装指南

请参考 Percona toolkit 网站的[下载部分](https://www.percona.com/doc/percona-toolkit/3.0/pt-online-schema-change.html#downloading)了解更多信息。

```
sudo apt install percona-toolkit
wget percona.com/get/percona-toolkit.tar.gz
wget percona.com/get/percona-toolkit.rpm
wget percona.com/get/percona-toolkit.deb
```

**样本用法：**

```
pt-online-schema-change --host <HOST> --user <DB_USER> --ask-pass  --alter "add column <YOUR_COLUMN_NAME>" D=<DATABASE>,t=<TABLE> --execute
```

**强制选项：**

1. `--host`：在此指定数据库主机
2. `--ask-pass`：在执行时询问密码或使用 `--password`：在命令本身中输入密码
3. `--alter`：要运行的 alter 命令
4. `--D`：您的数据库的名称
5. `--T`：表格名称
6. `--execute`：由于安全原因，这必须被指定

## 其他有用的选项

1. `--dry-run`：顾名思义，它不执行 ALTER TABLE，而是检查所有内容，并检查运行命令时可能出现的问题。您可以将此视为对查询的模拟修改（这不能与 `--execute` 一起使用，两者是互斥的）
2. `--alter-foreign-keys-method`：涉及外键的修改是很棘手的。这里可用的一些选项有：
   - `rebuild_constraints`：该方法删除并重新添加引用新表的外键。这通常是首选，除非子表太大，改变它们需要很长时间。
   - `drop_swap`：该选项将禁用外键检查，然后删除原始表，接着将新表重命名到它的位置。这种重命名操作不是原子的，因此风险更大，因为原始表在很短的时间间隔内不存在，这可能导致查询失败。
   - `auto`：让 Percona 决定什么最适合你的桌子。
3. `--check-alter`：检查更改命令，并在可能出现意外行为时发出警告
4. `--check-slave-lag`：如果副本滞后大于 `--max-lag`，暂停数据复制
5. `--chunk-size`：定义数据块的行数。（数据以块的形式复制）
6. `--critical-load`：复制完每个块后，Percona 会检查状态，如果负载过高，则会中止。您可以添加一个逗号分隔的 MySql 状态变量和阈值列表
7. `--drop-new-table`：控制如果数据复制失败，是否删除新表
8. `--drop-old-table`：控制操作完成后是否要删除旧表
9. `--print`：打印工具触发的 SQL 命令
10. `--max-lag`：如果副本延迟超过设定值，则暂停查询
11. `--max-load`：每个块被复制后，Percona 检查状态，如果负载过高，暂停查询
12. `--new-table-name`：您可以指定新表格的名称
13. `--sleep`：在复制每个块之间暂停多长时间

## 关于用法的一些注意事项

1. 如果表中没有主键或唯一索引，这种改变将不起作用。
2. 除非指定了 foreign key 选项，否则 ALTER 将不适用于带有外键的表。（在选项部分勾选 #2）
3. 如果负载过大或检测到从属滞后，该工具会自动暂停。这些值可以使用命令行选项来控制。
4. 在这里追踪已知的 bugs。
5. 根据文档，它适用于`Percona XtraDB Cluster (PXC) 5.5.28–23.7`，但在我们的测试中，它适用于 MySQL 5.7，查看下一节了解更多信息。

## 测试执行结果

以下是对结果的一些观察：

如果直接在 MySql 上执行 ALTER TABLE，执行时间大致相同，但是对应用程序读/写流量没有影响。

以下是在**测试数据库**和非生产环境下运行的结果。该表有多个外键关系，记录超过 500 万条，总执行时间大约为 10 分钟。

下面是示例执行输出

> （注意：为了保密，隐藏了数据库和表名）：

```
Not checking slave lag because no slaves were found and --check-slave-lag was not specified.
Operation, tries, wait:
  analyze_table, 10, 1
  copy_rows, 10, 0.25
  create_triggers, 10, 1
  drop_triggers, 10, 1
  swap_tables, 10, 1
  update_foreign_keys, 10, 1
Child tables:
  `<DATABASE>`.`<TABLEA>` (approx. 257042 rows)
  `<DATABASE>`.`<TABLEB>` (approx. 1194 rows)
  `<DATABASE>`.`<TABLEC>` (approx. 931229 rows)
Will automatically choose the method to update foreign keys.
Altering `<DATABASE>`.`<TABLE>`...
Creating new table...
Created new table <DATABASE>._<TABLE>_new OK.
Altering new table...
Altered `<DATABASE>`.`_<TABLE>_new` OK.
2021-10-08T19:11:08 Creating triggers...
2021-10-08T19:11:08 Created triggers OK.
2021-10-08T19:11:08 Copying approximately 5564340 rows...
Copying `<DATABASE>`.`<TABLE>`:   6% 06:39 remain
Copying `<DATABASE>`.`<TABLE>`:  15% 05:39 remain
Copying `<DATABASE>`.`<TABLE>`:  23% 04:56 remain
Copying `<DATABASE>`.`<TABLE>`:  31% 04:23 remain
Copying `<DATABASE>`.`<TABLE>`:  37% 04:09 remain
Copying `<DATABASE>`.`<TABLE>`:  45% 03:34 remain
Copying `<DATABASE>`.`<TABLE>`:  53% 03:01 remain
Copying `<DATABASE>`.`<TABLE>`:  60% 02:35 remain
Copying `<DATABASE>`.`<TABLE>`:  65% 02:20 remain
Copying `<DATABASE>`.`<TABLE>`:  72% 01:52 remain
Copying `<DATABASE>`.`<TABLE>`:  80% 01:21 remain
Copying `<DATABASE>`.`<TABLE>`:  86% 00:55 remain
Copying `<DATABASE>`.`<TABLE>`:  92% 00:32 remain
Copying `<DATABASE>`.`<TABLE>`:  99% 00:02 remain
2021-10-08T19:18:19 Copied rows OK.
2021-10-08T19:18:19 Max rows for the rebuild_constraints method: 28380
Determining the method to update foreign keys...
2021-10-08T19:18:19   `<DATABASE>`.`<TABLE>`: too many rows: 257042; must use drop_swap
2021-10-08T19:18:19 Drop-swapping tables...
2021-10-08T19:18:19 Analyzing new table...
2021-10-08T19:18:19 Dropped and swapped tables OK.
Not dropping old table because --no-drop-old-table was specified.
2021-10-08T19:18:19 Dropping triggers...
2021-10-08T19:18:19 Dropped triggers OK.
Successfully altered `<DATABASE>`.`<TABLE>`.
```

## 结论

该工具提供了许多特性，可以安全地在大型生产表上执行变更。但是，在使用这个工具之前，应该注意一些值得注意的事情。此外，文档建议在生产环境中运行该命令之前，在测试环境中进行[生产备份](https://www.percona.com/doc/percona-toolkit/3.0/pt-online-schema-change.html#risks)和测试。

如果你需要更多的帮助，请随时联系我。请务必关注所有新的更新。谢谢你的阅读。干杯🍺
