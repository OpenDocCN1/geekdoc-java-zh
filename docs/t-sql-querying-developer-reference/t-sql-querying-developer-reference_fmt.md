
# T-SQL 查询（开发者参考）

![](img/bdc38aa36f6e2987d913ee5381474711_0_0.png)

> 献给 Lilach，赋予我所做一切的意义。

— ITZIK

你觉得这本书怎么样？我们希望听听你的反馈，以便不断改进我们的书籍和学习资源。参与简要在线调查，请访问：

```
microsoft.com/learning/book
```

- 窗口函数. . . . . . . . . . . . . . . . 259
- 结论 ........................................................................................ 371
- 使用 `EXEC` 命令 ................................................................................ .525

你对这本书有什么看法？我们希望听听你的意见！

微软非常重视您的反馈，以便我们不断改进为您提供的书籍和学习资源。如需参与简短的在线调查，请访问：

```
microsoft.com/learning/booksurvey
```

# 前言

自 1993 年以来，我一直任职于微软并在微软 SQL Server 团队工作。见证这款产品成熟到今天这样，真是一段非凡的历程。看到微软 SQL Server 客户群如何使用 SQL Server 来运行他们的关键任务业务，令人兴奋。在所有经历中，能够支持我见过的最有活力、最热情的技术社区，是我的荣幸。

SQL Server 社区充满了真正优秀、聪明的人。他们以与他人分享卓越的知识为荣，这一切都是为了让社区变得更强大。世界上任何人都可以登录 Twitter 并向 `#sqlhelp` 提问任何问题，几秒钟内，世界上最聪明的专家之一就会给出回复。如果你正在寻找性能、存储、查询优化、大规模设计、建模或任何数据相关主题的专业知识，这些专家今天就在社区中分享他们的专长。你不仅能通过他们的专业知识认识他们，还能通过他们独特、友好的性格认识他们。我们 SQL Server 社区将此亲称为我们的家庭。

社区中的每个人都通过主要贡献者在特定领域的专长而认识他们。如果你询问最优秀的数据库性能专家，社区里的人会给你同样的四个或五个名字。如果你询问最优秀的存储专家，人们同样会给你同样的四个或五个专家名字。你总能在社区中找到几位在特定专业领域最顶尖的专家。据我所知，这只有一个例外，那就是 T-SQL 语言。有很多才华横溢的 T-SQL 专家，但如果你问谁是最棒的 T-SQL，每个人都会给你一个名字：Itzak Ben-Gan。

Itzak 请我为他的新书写这篇前言，我深感荣幸。他之前的书籍——《Inside Microsoft SQL Server: T-SQL Querying》(Microsoft Press, 2009)、《Inside Microsoft SQL Server: T-SQL Programming》(Microsoft Press, 2009) 以及《Microsoft SQL Server High-Performance T-SQL Using Window Functions》(Microsoft Press, 2012)——都摆在我认识的每个 DBA 的书架上。这些书籍加起来超过 2000 页关于 Microsoft SQL Server T-SQL 的顶尖知识，它们为高质量数据库内容树立了标准。

我对这本新书《T-SQL Querying》感到非常兴奋。它不仅结合了他之前三本书的材料，还增加了来自 SQL Server 2012 和 2014 的内容，包括窗口函数、新的基数估计器、序列、列存储、内存 OLTP（`In-Memory OLTP`）等。Itzak 还有几位合著者：Kevin Farlee、Adam Machanic 和 Dejan Sarka。Kevin 是微软 SQL Server 工程师团队的一员，我已经合作多年。Adam 是我上面提到的世界上最优秀的数据库性能专家之一，而 Dejan 则因在商业智能（BI）和数据建模方面的专长而闻名。我完全预期这本书将成为 SQL Server 的标准指南。

Mark Souza

云与企业工程总经理

微软

# 引言

更新了《Inside SQL Server 2008: T-SQL Querying》(Microsoft Press, 2009) 以及《Inside Microsoft SQL Server 2008: T-SQL Programming》(Microsoft Press, 2009) 后，本书为数据库开发者和管理员提供了 T-SQL 架构的详细视角。它涵盖了 SQL Server 2012 和 2014 的内容，但在许多情况下处理的是与版本无关且适用于未来 SQL Server 版本的问题。在深度 T-SQL 知识作者的指导下，解决最复杂的集合查询和查询调优问题。深化对架构和原理的理解——学习优化代码性能的实用方法和高级技术。这本书涵盖了作者多年经验中开发、改进和完善的独特技术，为常见挑战提供了高效的解决方案。本书还强调了正确理解语言及其基础的重要性。

# 谁应该读这本书

这本书旨在帮助有经验的 T-SQL 实践者在该领域更加博学和高效。这本书假设你已经掌握了 T-SQL 编码和调优的基础知识，并准备好应对更高级的挑战。如果你在不同的数据库平台及其 SQL 方言上有类似的经验，这本书可能对你仍然有效，但具有实际的 SQL Server 和 T-SQL 知识和经验更为理想。

# 假设

本书假设你至少有一年使用 SQL Server 编写调优 T-SQL 的实战经验。它假设你已经良好掌握了 T-SQL 编码和调优的基础，并准备好应对更复杂的挑战。

# 这本书可能不适合你……

如果你对数据库和 SQL 还非常陌生，那么这本书可能不适合你。

# 本书的结构

本书开头的两个章节奠定了逻辑和物理查询处理的基础，以便你能够从后续的章节中获得最大的收益。

第一章涵盖了逻辑查询处理。它详细描述了处理查询时涉及的逻辑阶段、SQL 查询的独特之处，以及在关系型、集合型环境中进行编程时需要采用的特殊思维。

第二章涵盖了查询调优和物理层。它描述了内部数据结构、衡量查询性能的工具、访问方法、基数估计、索引功能、使用扩展事件进行查询优先级排序、列存储技术、临时表和表变量的使用、与游标的对比、通过修订版进行查询调优，以及并行查询执行。（关于并行查询执行的部分由 Adam Machanic 编写。）

接下来的五章涉及各种数据操作相关主题。这些主题的涵盖范围广泛；除了解释功能外，它们还重点关注代码性能以及如何使用这些功能解决常见任务。第三章涵盖了使用子查询、连接（`joins`）以及 `UNION`、`INTERSECT` 和 `EXCEPT` 关系运算符的多表查询。第四章涵盖了使用分组（`grouping`）、交叉（`pivoting`）和窗口函数的数据分析。第五章涵盖了 `TOP` 和 `OFFSET-FETCH` 过滤器、每组排序前 N 条的任务。第六章涵盖了数据修改任务，如记录操作、高效使用序列对象、合并数据以及 `OUTPUT` 子句。第七章涵盖了日期和时间处理，包括日期时间间隔的处理。

第八章涵盖了面向 BI 从业者的 T-SQL，由 Dejan Sarka 编写。它描述了如何准备分析数据以及如何使用 T-SQL 处理统计数据分析任务。这些任务包括频率、连续变量的描述性统计、线性依赖以及移动平均和熵。

第九章涵盖了 T-SQL 支持的可编程构造结构。这些包括动态 SQL、用户定义函数、存储过程、触发器、SQLCLR 编程（由 Adam Machanic 编写）、事务与并发以及错误处理。

此前，这些主题在《Inside Microsoft SQL Server: T-SQL Programming》一书中曾介绍过。

第十章涵盖了 SQL Server 2014 的主要改进之一——内存 OLTP（`In-Memory OLTP`）引擎。本章由微软的 Kevin Farlee 编写，他参与了该功能的实际开发。

第十一章涵盖了图和递归查询。它展示了如何使用 T-SQL 在 SQL Server 中处理员工层级、物料清单（bill of materials）和地图等结构。它展示了如何实现枚举路径模型（使用自己的自定义解决方案和 `HIERARCHYID` 类型）以及嵌套集合模型。它还展示了如何使用递归查询来操作图中的数据。

# 系统要求

运行本书中的代码示例需要以下软件：

- SQL Server 2014:
    - 版本：64 位企业版（`Enterprise`）、开发版（`Developer`）或评估版（`Evaluation`）；其他版本不支持书中涵盖的内存 OLTP 和列存储技术。你可以在此下载预览版：`http://www.microsoft.com/sql`。
    - 硬件和软件要求请参阅 `http://msdn.microsoft.com/en-us/library/ms14506(v=sql120).aspx`。
    - 在 SQL Server 2014 安装程序的“功能选择”对话框中，选择以下组件：数据库引擎服务（`Database Engine Services`）、客户端工具连接（`Client Tools Connectivity`）、文档组件（`Documentation Components`）、管理工具 - 基本（`Management Tools – Basic`）、管理工具 - 完全（`Management Tools – Complete`）。

- 带有 Microsoft SQL Server Data Tools (SSDT) 的 Visual Studio 2013:
    - 你可以在此处查看 Visual Studio 2013 的系统要求和平台兼容性：`http://www.visualstudio.com/products/visual-studio-2013-compatibility-vs`。
    - 关于安装 SSDT 的信息请参阅 `http://msdn.microsoft.com/en-us/data/tools.aspx`。

根据你的 Windows 配置，你可能需要本地管理员权限来安装或配置 SQL Server 2014 和 Visual Studio 2013。

# 下载：代码示例

本书包含许多代码示例。你可以从作者网站下载本书的源代码：`http://tsql.solidq.com/books/tq3`。

源代码组织在一个名为 `T-SQL Querying - YYYYMMDD.zip` 的压缩文件中，其中 `YYYYMMDD` 代表内容的更新日期。请按照压缩包中 `Readme.txt` 文件中的说明安装代码示例。

# 感谢

许多人直接或间接地为本书的实现做出了贡献，他们理应感谢和认可。我可能无意中遗漏了一些名字，在此提前致歉。

致 Lilach：是你让我想要精通我所长。除了成为我生活的灵感来源外，你在书中也扮演了活跃的非正式角色。你是本书的第一位读者！在我将稿交给编辑之前，我们花费了许多小时阅读文本寻找错误。我觉得你对 T-SQL 的了解甚至比该领域的专业人士还要深。

致我的父母 Mila 和 Gabi，以及我的兄弟姐妹 Mickey 和 Ina，感谢你们如既往的支持以及接受我不在的事实。你们在过去几年里经历了许多动荡，我希望未来几年是健康快乐的。

本书的合作者 Dejan Sarka、Adam Machanic 和 Kevin Farlee。能成为这样一个博学团队的一员是我的荣幸。

致 SQL Server Pro 编辑团队的所有前任及现任成员：Megan Keller, Lavon Peters, Michele Crockett, Mike Otey, Jayleen Heft，我确定还有许多其他人。我为本杂志撰稿了十五多年，非常感激有这个机会与杂志的读者分享我的知识。

致前任及现任的 SQL Server MVP：Paul White, Alejandro Mesa, Erland Sommerskog, Aaron Bertrand, Tibor Karazi, Benjamin Nevarez, Simon Babin, Darren Green, Allen Mitchell, Tony Rogers 以及许多其他人——以及 MVP 负责人 Simon Tien。这是一个伟大的计划，我非常荣幸并自豪能成为一员。这个人的专业水平令人惊叹，每当我们聚在一起、分享想法或只是在喝着啤酒叙叙近况时，我总是感到兴奋。我必须向 Paul White 表以特别感谢。我从你那里学到了很多，我非常喜欢你的作品。谁知道呢，也许有一天我们会合作做一些事情。

最后，我的学生们：教授 T-SQL 是我的动力。这是我的热情。感谢你们让我履行使命，并感谢所有促使我追求更多知识的绝佳问题。

—致敬，Itzik

```
http://aka.ms/mspfree
```

经常回来查看最新动态！

我们知道您很忙，所以我们保持了简短，只有几个问题。您的回答将直接给 Microsoft Press 的编辑。（不会要求任何个人信息）。感谢您的参与！

## 保持联系

让我们继续交流吧！我们在 Twitter 上：`http://twitter.com/MicrosoftPress`。

本页特意留白

# 第 1 章

## 逻辑查询处理

观察不同领域的真正专家，你会发现他们都有一个共同的习惯——精通基础。无论何种，所有职业都涉及解决问题。所有问题的解决方案，无论多么复杂，都涉及到对基础技术的混合应用。如果你想精通某个职业，你需要在坚实的基础之上构建你的知识。投入大量精力完善你的技术，掌握基础知识，你就能解决任何问题。

这本书的主题是 Transact-SQL (T-SQL) 查询——学习关键技术并将其应用于解决问题。我找不到比从“逻辑查询处理”这一章开始更合适的方式来开启这本书了。我发现这一章是书中最重要的——不仅是因为它涵盖了查询处理的核心内容，还因为 SQL 编程在概念上与任何其他编程都非常不同。

> 注意 本书是第三版。上一个版本分为两卷，现已合并为一。关于更改的详情，请查看有关获取源代码和示例数据的信息，请务必访问书籍的引言部分。

T-SQL 是 Microsoft SQL Server 对 ANSI 和 ISO SQL 标准的方言或扩展。在整书中，我将交叉使用 SQL 和 T-SQL 术语。在讨论源自 ANSI/ISO SQL 且与大多数方言相关的语言方面时，我通常使用 SQL 或标准 SQL 术语。在讨论考虑到 SQL Server 实现的语言方面时，我通常使用 T-SQL 术语。请注意正式名称是 Transact-SQL，尽管它通常被称为 T-SQL。大多数程序员（包括我在内）都觉得称其为 T-SQL 很舒服，因此我和其他作者自觉地选择在整书中使用 T-SQL 术语。

### SQL 读音的起源

许多英语母语数据库专业人士将 SQL 读作 "sequel"，尽管该语言的正确读音是 S-Q-L（"ess kyoo ell"）。人们可以对这种错误读音背后的原因做出合理的推测。我的猜测是既有历史原因，也有语言原因。

历史原因方面，20 世纪 70 年代，IBM 开发了一种名为 SEQUEL 的语言，它是 Structured English Query Language（结构化英语查询语言）的缩写。该语言旨在操作名为 R 的数据库系统中的数据，该系统基于 Edgar F. Codd 的关系型数据库管理系统 (RDBMS) 模型。由于商标纠纷，SEQUEL 缩写被缩短为 SQL。ANSI 在 1986 年采纳 SQL 为标准，ISO 在 1987 年也采纳了。ANSI 宣布该语言的官方读音为 "ess kyoo"，但这一事实似乎并非常识。

语言原因方面，"sequel" 的读音简单更流畅，主要是对英语使用者而言。我自己经常也因为这个原因而这样读。

> 更多信息 本章对 SQL 历史的涵盖基于维基百科（自由百科书）的一篇文章，可以在 `http://en.wikipedia.org/wiki/SQL` 找到。



# SQL 编程基础

SQL 编程有许多独特之处，例如集合思维、查询元素的逻辑顺序以及三值逻辑。在没有这些知识的情况下编写 SQL 是一条漫长的道路，低性能的代码难以维护。本章的目的是帮助你理解 SQL 的设计初衷，你需要建立一个坚实的基础，其余部分才能构建。在相关的地方，我将明确指出与 T-SQL 特定的元素。在整书中，我将涵盖复杂问题。在本章中，我将只处理查询的基础方面。在本书中，我还将关注性能。在本章中，我将只处理查询的逻辑方面。你将在书中发现大量性能内容。在本章描述的逻辑查询处理阶段可能并不均匀。但请记住，在实践中，数据库中的查询物理执行与逻辑执行有不同。

逻辑查询处理的每一步都会生成一个虚拟表，作为后续步骤的输入。这些虚拟表对调用者（客户端应用程序或外部查询）是不可见的。只有最后一步生成的表会被返回给调用者。如果查询中没有指定某个子句，则直接跳过相应的步骤。以下节简要描述了不同的逻辑步骤。

## 逻辑查询处理阶段简述

如果目前对步骤的描述看起来并不合理，请不要担心。提供的描述是在参考之后之后。场景示例之后的章节将更详细地涵盖这些步骤。此外，在这里我只描述了连接操作符（`join`），因为它是最常用的，因此容易联系。其他操作符（`APPLY`、`PIVOT` 和 `UNPIVOT`）将在本章节后的“逻辑查询处理的进一步阶”部分中介绍。

图 1 包含一个表示逻辑查询阶段的流程图。在整个章节中，我将引用图中出现的步骤编号。

- **(FROM)** 此阶段识别查询源和表操作符。每个表操作符应用一系列子阶段。连接涉及的阶段有 `(1-J1)` 卡卡尔积、`(1-J2)` ON 谓词、`(1-J3)` 添加外部行。此阶段生成虚拟表 `VT-J1`。

- **(1-J1) 卡卡尔积** 此阶段在表操作符涉及的两个表之间执行笛卡尔积（交叉连接），生成 `VT-J1`。

- **(1-J2) ON 谓词** 此阶段根据 `ON` 子句中出现的谓词（`<<predicate>>`）过滤 `VT-J1` 中的行。只有谓词求值为 `TRUE` 的行会被插入 `VT-J2`。

- **(1-J3) 添加外部行** 如果指定了 `OUTER JOIN`（而不是 `CROSS JOIN` 或 `INNER JOIN`），则将保留的表（或表中）未找到匹配项的行作为外部行添加到来自 `VT-J2` 的行中，生成 `VT-J3`。

- **(2) WHERE** 此阶段根据 `WHERE` 子句中出现的谓词（`<<where_predicate>>`）过滤 `VT-J1` 中的行。只有谓词求值为 `TRUE` 的行会被插入 `VT-2`。

- **(3) GROUP BY** 此阶段根据 `GROUP BY` 子句中指定的表达式集合（又称分组）对 `VT-J2` 中的行进行分组，生成 `VT3`。最终，每个符合条件的组将有一行结果。

- **(4) HAVING** 此阶段根据 `HAVING` 子句中出现的谓词（`<<having_predicate>>`）过滤 `VT-J3` 中的行。只有谓词求值为为 `TRUE` 的组会被插入 `VT4`。

- **(5) SELECT** 此阶段处理 `SELECT` 子句中的元素，生成 `VT5`。

![](img/bdc38aa36f6e2987d913ee5381474711_29_0.png)

图 1-1 逻辑查询处理流程图。

第 1 章 逻辑查询处理 5

- **(5-1) 评估表达式** 此阶段评估 `SELECT` 列表中的表达式，生成 `VT5-1`。

- **(5-2) DISTINCT** 此阶段删除 `VT5-1` 中的重复行，生成 `VT5-2`。

- **(6) ORDER BY** 此阶段使用游标 `VC6` 根据 `ORDER BY` 子句中指定的列表对 `VT5-2` 中的行进行排序。如果没有 `ORDER BY` 子句，`VT5-2` 变为 `VT6`。

- **(7) TOP | OFFSET-FETCH** 此阶段根据 `TOP` 或 `OFFSET-FETCH` 规格从 `VC6` 或 `VT6` 中过滤行，分别生成 `VC7` 或 `VT7`。使用 `TOP` 时，根据 `ORDER BY` 子句的排序过滤指定数量的行，或者在缺少 `ORDER BY` 子句时按任意顺序。使用 `OFFSET-FETCH` 时，根据 `ORDER BY` 子句的排序跳过指定数量的行，然后过滤下一个指定数量的行。`OFFSET FETCH` 过滤器是在 SQL Server 2012 中引入的。

## 基于客户订单场景的示例查询

为了详细描述逻辑处理阶段，我将带你通过一个示例查询。首先运行以下代码创建 `dbo.Customers` 和 `dbo.Orders` 表，填充示例数据，并查询它们以显示内容：

```sql
SET NOCOUNT ON;
USE tempdb;
```

```sql
IF OBJECT_ID(N'dbo.Orders', N'U') IS NOT NULL DROP TABLE dbo.Orders;
```

```sql
IF OBJECT_ID(N'dbo.Customers', N'U') IS NOT NULL DROP TABLE dbo.Customers;
```

```sql
CREATE TABLE dbo.Customers (
  custid CHAR(5) NOT NULL,
  city VARCHAR(10) NOT NULL,
  CONSTRAINT PK_Customers PRIMARY KEY(custid)
);
```

```sql
CREATE TABLE dbo.Orders (
  orderid INT NOT NULL,
  custid CHAR(5) NULL,
  CONSTRAINT PK_Orders PRIMARY KEY(orderid),
  CONSTRAINT FK_Orders_Customers FOREIGN KEY(custid)
  REFERENCES dbo.Customers(custid)
);
GO
```

```sql
INSERT INTO dbo.Customers(custid, city) VALUES
  ('FISSA', 'Madrid'),
  ('FRNDO', 'Madrid'),
  ('KRLOS', 'Madrid'),
  ('MERIS', 'Zion');
```

```sql
INSERT INTO dbo.Orders(orderid, custid) VALUES
(1, 'FISSA'),
(2, 'FRNDO'),
(3, 'KRLOS'),
(4, 'FISSA'),
(5, 'MERIS'),
(6, 'KRLOS'),
(7, 'FRNDO');
```

```sql
SELECT C.custid, C.city, COUNT(O.orderid) AS numorders
FROM dbo.Customers AS C
LEFT JOIN dbo.Orders AS O ON C.custid = O.custid
GROUP BY C.custid, C.city
HAVING COUNT(O.orderid) < 3
ORDER BY numorders;
```

该查询返回：

| custid | city | numorders |
| :--- | :--- | :--- |
| FISSA | Madrid | 2 |
| FRNDO | Madrid | 2 |
| KRLOS | Madrid | 2 |
| MERIS | Zion | 1 |

| C.custid | C.city | O.orderid | O.custid |
| --- | --- | --- | --- |
| FISSA | Madrid | 1 | FRNDO |
| FISSA | Madrid | 2 | FRNDO |
| FISSA | Madrid | 3 | KRLOS |
| FISSA | Madrid | 4 | KRLOS |
| FISSA | Madrid | 5 | KRLOS |
| FISSA | Madrid | 6 | MRPHS |
| FISSA | Madrid | 7 | NULL |
| FRNDO | Madrid | 1 | FRNDO |
| FRNDO | Madrid | 2 | FRNDO |
| FRNDO | Madrid | 3 | KRLOS |
| FRNDO | Madrid | 4 | KRLOS |
| FRNDO | Madrid | 5 | KRLOS |
| FRNDO | Madrid | 6 | MRPHS |
| FRNDO | Madrid | 7 | NULL |
| KRLOS | Madrid | 1 | FRNDO |
| KRLOS | Madrid | 2 | FRNDO |
| KRLOS | Madrid | 3 | KRLOS |
| KRLOS | Madrid | 4 | KRLOS |
| KRLOS | Madrid | 5 | KRLOS |
| KRLOS | Madrid | 6 | MRPHS |
| KRLOS | Madrid | 7 | NULL |
| MRPHS | Zion | 1 | FRNDO |
| MRPHS | Zion | 2 | FRNDO |
| MRPHS | Zion | 3 | KRLOS |
| MRPHS | Zion | 4 | KRLOS |
| MRPHS | Zion | 5 | KRLOS |
| MRPHS | Zion | 6 | MRPHS |
| MRPHS | Zion | 7 | NULL |

表 1-1 从步骤 1-J1 返回的虚拟表 VT1-J1

### 步骤 1-J2: ON 谓词（连接条件）

`ON` 子句是三个查询句（`ON`、`WHERE` 和 `HAVING`）中的第一个，根据谓词过滤行。`ON` 子句中的谓词应用于上一个步骤返回的虚拟表（`VT1-J1`）中的所有行。只有 `<on_predicate>` 为 `TRUE` 的行才会成为此步骤返回的虚拟表（`VT1-J2`）的一部分。

## NULL 与三值逻辑

这里稍微离题一下，介绍与此步骤相关的 SQL 的一些重要方面。关系模型定义了两个表示缺失值的标记：A 标记（缺失且适用）和 I 标记（缺失且不适用）。前者表示某个值通常是有效的，但由于某种原因缺失了。例如，考虑 `People` 关系中的 `birthdate` 属性。对于大多数人来说，这个信息是已知的，但在某些罕情况下并不是的——例如，我妻子的爷爷显然不是，他出生于某一天，但没人知道是哪一天。后者表示某个值是无关的。例如，考虑 `Orders` 关系中的 `custid` 属性。假设你在公司进行库存检查时，如果发现物品的预期水平与库存水平之间不一致，你会向数据库添加一个虚拟订单以进行补偿。在这种事务中，客户 ID 是无关的。

与关系模型不同，SQL 标准没有区分不同类型的值，而是只使用一个通用标记——`NULL` 标记。`NULL` 是 SQL 中很多困惑和问题的根源，应该对其良好的理解以避免错误。首先，人们犯的一个常见错误是使用“NULL 值”这一术语，但 `NULL` 不是一个值；它是一个缺失值的标记。正确的术语是“NULL 标记”（NULL mark）或“NULL”。此外，由于 SQL 对缺失值和缺失且不适用的情况只使用一个标记，当你使用 `NULL` 时，SQL 无法判断它代表的是缺失还是缺失且不适用。例如，在我们的示例数据中，有一个订单的 `custid` 列是 `NULL` 标记。假设这是一个与任何客户都不相关的虚拟订单。所以你使用 `NULL` 记录了值缺失的事，而不是缺失且不适用。

SQL 中关于 `NULL` 的很大困惑与你在查询过滤器、谓词、`CHECK` 约束以及其他地方有关。谓词的可能值为 `TRUE`、`FALSE` 和 `UNKNOWN`。这被称为三值逻辑，并且是 SQL 特有的。大多数编程语言的逻辑表达式只有 `TRUE` 或 `FALSE`。`UNKNOWN` 值在 SQL 中通常涉及一个 `NULL`。（例如，这三个逻辑表达式的逻辑值都是 `UNKNOWN`：`NULL > 1759`；`NULL = NULL`；`NULL + NULL > Y`）。记住，`NULL` 标记表示缺失值。根据 SQL，当将一个值与另一个值（即使是 `NULL`）比较时，逻辑结果始终是 `UNKNOWN`。处理 `UNKNOWN` 结果和 `NULL` 可能非常困惑。当 `NOT TRUE` 是 `FALSE`，且 `NOT FALSE` 是 `TRUE` 时，`UNKNOWN` 的相反（`NOT UNKNOWN`）仍然是 `UNKNOWN`。`UNKNOWN` 结果和 `NULL` 在不同语言元素中的处理方式不一致。例如，所有查询过滤器（`ON`、`WHERE` 和 `HAVING`）将 `UNKNOWN` 视为 `FALSE`。另一方面，`CHECK` 约束将 `UNKNOWN` 视为 `TRUE`。假设有一个 `CHECK` 约束要求 `salary` 列大于 0。一个带有 `NULL` 的行会被接受的，因为 `(NULL > 0)` 是 `UNKNOWN` 且在 `CHECK` 约束中被视为 `TRUE`。两个 `NULL` 之间的比较产生 `UNKNOWN`，正如我提到的，如果一个 `NULL` 不同于另一个。另一方面，对于 `UNIQUE` 约束、某些关系运算符或排序，`NULL` 被视为相等。这些关系运算符隐式使用了 `DISTINCT` 谓词。以下表达式是 true：`NULL NOT DISTINCT FROM NULL`、`IS DISTINCT FROM 1759`。直到 SQL Server 2014，T-SQL 不支持 `DISTINCT` 谓词，但我非常希望未来能添加支持（参见功能请求：https://connect.microsoft.com/SQL/feedback/28642/）。简而言之，为了避免麻烦，你应该意识到 `UNKNOWN` 结果和 `NULL` 在不同语言元素中的处理方式。

```sql
Customers AS C LEFT JOIN Orders AS 0
```

表 1-2 第一列显示了来自 VT1-J 的 ON 子句的值。

| C.custid | C.city | O.orderid | O.custid |
| --- | --- | --- | --- |
| FISSA | Madrid | 1 | FRNDO |
| FISSA | Madrid | 2 | FRNDO |
| FISSA | Madrid | 3 | KRLOS |
| FISSA | Madrid | 4 | KRLOS |
| FISSA | Madrid | 5 | KRLOS |
| FISSA | Madrid | 6 | MRPHS |
| FISSA | Madrid | 7 | NULL |
| FRNDO | Madrid | 1 | FRNDO |
| FRNDO | Madrid | 2 | FRNDO |
| FRNDO | Madrid | 3 | KRLOS |
| FRNDO | Madrid | 4 | KRLOS |
| FRNDO | Madrid | 5 | KRLOS |
| FRNDO | Madrid | 6 | MRPHS |
| FRNDO | Madrid | 7 | NULL |
| KRLOS | Madrid | 1 | FRNDO |
| KRLOS | Madrid | 2 | FRNDO |
| KRLOS | Madrid | 3 | KRLOS |
| KRLOS | Madrid | 4 | KRLOS |
| KRLOS | Madrid | 5 | KRLOS |
| KRLOS | Madrid | 6 | MRPHS |
| KRLOS | Madrid | 7 | NULL |
| MRPHS | Zion | 1 | FRNDO |
| MRPHS | Zion | 2 | FRNDO |
| MRPHS | Zion | 3 | KRLOS |
| MRPHS | Zion | 4 | KRLOS |
| MRPHS | Zion | 5 | KRLOS |
| MRPHS | Zion | 6 | MRPHS |
| MRPHS | Zion | 7 | NULL |



只有 `<on_predicate>` 为 TRUE 的行才被插入 VT1-J2，如表 1-3 所示。

### 表 1-3 从步骤 1-J2 返回的虚拟表 VT1-J2

| 逻辑值 | C.custid | C.city | O.orderid | O.custid |
|---|---|---|---|---|
| TRUE | FRNDO | Madrid | 1 | FRNDO |
| TRUE | FRNDO | Madrid | 2 | FRNDO |
| TRUE | KRLOS | Madrid | 3 | KRLOS |
| TRUE | KRLOS | Madrid | 4 | KRLOS |
| TRUE | KRLOS | Madrid | 5 | KRLOS |
| TRUE | MRPHS | Zion | 6 | MRPHS |

### 步骤 1-J3: 添加外部行

这仅发生在外连接。对于外连接，你通过指定外连接类型（`LEFT`、`RIGHT` 或 `FULL`）将一个或两个输入表标记为**保留**（preserved）。标记的表意味着其所有行都会返回，即使它们被 `<on_predicate>` 过滤掉了。步骤 1-J3 返回 VT1-J2 中的行，加上在步骤 1-J2 中未找到匹配的保留表的行。这些添加的行被称为外部行（outer rows）。`NULL` 被分配给外部行中非保留表的属性。因此生成了虚拟表 VT1-J3。

在我们的示例中，保留表是 Customers：

`Customers AS C LEFT JOIN Orders AS O`

只有客户 FISSA 没有匹配到订单（因此不在 VT1-J2 中）。因此，一条 FISSA 的行被添加到 VT1-J2 中，Orders 属性为 `NULL`。结果是虚拟表 VT1-J3（如表 1-4 所示）。由于示例查询的 FROM 子句没有更多表运算符，虚拟表 VT1-J3 也是 FROM 阶段返回的虚拟表 VT1。

### 表 1-4 从步骤 1-J3 返回的虚拟表 VT1-J3（也是 VT1）

| C.custid | C.city | O.orderid | O.custid |
|---|---|---|---|
| FRNDO | Madrid | 1 | FRNDO |
| FRNDO | Madrid | 2 | FRNDO |
| KRLOS | Madrid | 3 | KRLOS |
| KRLOS | Madrid | 4 | KRLOS |
| KRLOS | Madrid | 5 | KRLOS |
| MRPHS | Zion | 6 | MRPHS |
| FISSA | Madrid | NULL | NULL |

> **注意**：如果 FROM 子句中出现多个表操作符，它们将从左到右进行处理——至少在逻辑查询处理顺序上是这样规定的。每个表操作符的结果都将作为下一个表操作符的左输入。最终的虚拟表将作为下一步的输入。

### 第 2 步：WHERE 阶段

WHERE 过滤器应用于上一步返回的虚拟表中的所有行。满足 `<where_predicate>` 为 TRUE 的行构成了此步骤返回的虚拟表（VT2）。

> **注意**：你不能引用 SELECT 列表中创建的列别名，因为它们还没有被处理——例如，你不能写 `SELECT YEAR(orderdate) AS orderyear ... WHERE orderyear > 2014`。带有讽刺的是，有些人认为这种行为是 SQL Server 的一个 bug，但当你理解了逻辑查询处理时，这很容易解释。此外，由于数据尚未进行分组，你不能使用分组聚合函数——例如，你不能写 `WHERE orderdate = MAX(orderdate)`。

在示例查询中应用过滤器：

```
WHERE C.city = 'Madrid'
```

来自 VT1 的客户 MRPHS 的行被删除了，因为城市不是 Madrid，并生成了表 1-5 所示的虚拟 VT2。

### 表 1-5 从第 2 步返回的虚拟 VT2

| C.custid | C.city | O.orderid | O.custid |
|---|---|---|---|
| FRNDO | Madrid | 1 | FRNDO |
| FRNDO | Madrid | 2 | FRNDO |
| KRLOS | Madrid | 3 | KRLOS |
| KRLOS | Madrid | 4 | KRLOS |
| KRLOS | Madrid | 5 | KRLOS |
| FISSA | NULL | | NULL |

使用外连接查询的一个令人困惑点是在 ON 子句还是 WHERE 子句中指定谓词。两者的主要区别是 ON 在外连接行之前应用（步骤 1-J3），而 WHERE 在此之后应用。通过 ON 子句从服务表中删除某行并不是最终的，因为步骤 1-J3 会将其重新加回来；相比之下，通过 WHERE 子句删除行是最终的。另一种理解方式是，将 ON 谓词视为匹配目的，而将 WHERE 谓词视为更基础的过滤目的。对于连接中保留侧的行，ON 子句不能丢弃这些行；它只决定非保留侧的哪些行与它们匹配。然而，WHERE 子句确实可以丢弃保留侧的行。记住这些将帮助你做出正确的选择。

例如，假设你想从 Customers 和 Orders 表返回某些客户及其订单。你想返回的客户只有 Madrid 客户——包括下过订单的未下订单的。外连接正是为这种请求设计的。你在 Customers 和 Orders 之间执行左外连接，使 Customers 保留表。为了能够返回没有订单的客户，你必须在 ON 子句中指定 Customers 和 Orders 之间的关联（`ON C.custid`）。没有订单的客户在步骤 1-J2 中被消除，但在步骤 1-J3 中作为外行重新添加。然而，由于你只想返回 Madrid 客户，你必须在 WHERE 子句中指定城市谓词（`WHERE C.city = 'Madrid'`）。在 ON 子句中指定城市谓词会导致非 Madrid 客户在步骤 1-J3 中被重新添加到结果集中。

> ON 和 WHERE 子句之间的这种逻辑差异仅在使用外连接时存在。当你使用内连接时，在哪里指定谓词并不重要，因为步骤 1-J3 会被跳过。谓词是一个接一个应用的，它们之间没有中间步骤，都起到基础的过滤作用。

### 第 3 步：GROUP BY 阶段

GROUP BY 阶段根据 GROUP BY 子句中定义的分组集（或多个集合），将上一步返回的表行关联到组。为了简单起见，假设你有一组用于分组的表达式。这被称为分组集。

在这个阶段，从上一步返回的表行被分成若干组。分组集中值的每个唯一组合都标识一个组。上一步的每行都与且仅与一个组关联。虚拟表 VT3 由按分组排列的 VT2 的行（原始信息）和分组标识符（分组信息）组成。

对以下示例查询应用步骤 3：

```
GROUP BY C.custid
```

你得到了表 1-6 所示的虚拟表 VT3。

### 表 1-6 从第 3 步返回的虚拟 VT3

| C.custid | C.custid | C.city | O.order | O.custid |
|---|---|---|---|---|
| FRNDO | FRNDO | Madrid | 1 | FRNDO |
| | | Madrid | 2 | FRNDO |
| KRLOS | KRLOS | Madrid | 3 | KRLOS |
| | | Madrid | 4 | KRLOS |
| | | Madrid | 5 | KRLOS |
| FISSA | FISSA | Madrid | NULL | NULL |

最终，分组查询将为每个组生成一行（除非该组被过滤掉）。因此，当查询中指定了 GROUP BY 时，所有后续步骤（HAVING、SELECT 等）只能指定对每个组产生标量（单一）值的表达式。这些表达式可以包括来自原始部分的列或聚合函数。检查表 1-6 中的结果；SELECT 列表只能包含来自上一步的列，除非它们是 GROUP BY 列表的列。如果你引用原始部分的列，它们必须经过聚合。上一步选择的未处理列应重命名，以便在结果表中具有列名——例如 `YEAR(orderdate) AS orderyear`。

### 第 4 步：HAVING 阶段

HAVING 过滤器应用于上一步的组。只有满足 `<having_predicate>` 为 TRUE 的组才会成为此步骤返回的表（VT4）。将此应用于示例查询：

```
HAVING COUNT(order) < 3
```

KRLOS 的行被删除了。生成了表 1-7 所示的虚拟 VT4，

### 表 1-7 从第 4 步返回的虚拟 VT4

| C.custid | C.custid | C.city | O.order | O.custid |
|---|---|---|---|---|
| FRNDO | FRNDO | Madrid | 1 | FRNDO |
| | | Madrid | 2 | FRNDO |
| FISSA | FISSA | Madrid | NULL | NULL |

> **注意**：聚合函数不接受子查询作为输入——例如 `HAVING SUM(..)) > 10`。

### 第 5 步：SELECT 阶段

尽管在查询中进行了指定，SELECT 子句仅在第五步被处理。SELECT 构建了返回给调用者的表。此阶段涉及两个子阶段：(5-1) 评估表达式和 (5-2) 应用子句。

#### 步骤 5-1：评估表达式

SELECT 列表中的表达式可以返回上一步返回的虚拟表的列及其处理。记住，如果查询是聚合查询，在步骤 3 之后，你只能引用属于分组列表的上一步列。如果你引用原始部分的列，它们必须经过聚合。重要：如前所述，SELECT 列表创建的别名不能用于之前的步骤——例如，在 WHERE 阶段。当你理解了查询子句的逻辑处理时，这完全合理。此外，别名甚至不能在同一个 SELECT 列表的其他表达式中使用。这种限制的背后是 SQL 的另一个独特之处；许多操作都是一次性操作。例如，在以下 SELECT 列表中，表达式评估的逻辑顺序并不重要也不保证：`SELECT c1 + 1 AS e1, c2 + 1 AS e2`。因此，以下 SELECT 列表是不支持的：`SELECT c1 + 1 AS e1, e1 + 1 AS e2`。你允许在定义别名的阶段之后使用列别名。如果你在 SELECT 阶段定义了列别名，你可以在 ORDER BY 阶段中引用它——例如 `SELECT YEAR(orderdate) AS orderyear ... ORDER BY orderyear`。

“一次性操作”的概念可能很难理解。例如，在编程环境中，为了交换变量之间的值，你会使用一个临时变量。然而，在 SQL 中交换表列时，你使用以下语句：

```
UPDATE dbo.T1 SET c1 = c2, c2 = c1;
```

逻辑上，你应该假设整个操作是一次完成的。这就像源表在整个操作完成并结果替换源表之前没有被修改一样。出于类似的原因，下面的 UPDATE 将更新 T1 的所有行，将 T1 中相同的最大 c1 值加到 c1，直到操作更新完成：

```
UPDATE dbo.T1 SET c1 = c1 + (SELECT MAX(c1) FROM dbo.T1);
```

不要担心最大 c1 值可能会操作的进行而不断变化；它不会变化，因为操作是一次性发生的。

将此步骤应用于示例查询：

```
SELECT C.custid, COUNT(O.orderid) AS numorders
```

你得到了虚拟表 VT5-1，如表 1-8 所示。由于 SELECT 阶段的另一个可能的子阶段（DISTINCT）未应用于示例查询，该子阶段返回的虚拟表 VT5-1 就是 SELECT 阶段返回的虚拟表 VT5。

### 表 1-8 从步骤 5 返回的虚拟表 VT5-1（也称为 VT5）

| C.custid | numorders |
|---|---|
| FRNDO | 2 |
| FISSA | 0 |

#### 步骤 5-2：应用 DISTINCT 子句

如果查询指定了 DISTINCT 子句，则从上一步返回的虚拟表中删除重复行，并生成虚拟表 VT5-2。

> **注意**：SQL 偏离了关系模型，它允许表具有重复行（当不强制主键或唯一约束时），并且查询可以在结果中返回重复行。根据关系模型，关系的体是一个元组集合（SQL 称之为行），根据数学集合理论，集合（区别于多重集合）没有重复项。使用 DISTINCT 子句，你可以确保查询返回唯一的行，从这个意义上说，符合关系模型。

你应该意识到，SELECT 阶段首先评估表达式（子阶段 5-1），之后才删除重复行（子阶段 5-2）。如果你没有意识到这一点，可能会对某些查询的结果感到惊讶。例如，下面的查询返回下过订单的客户的唯一 ID：

```
SELECT DISTINCT custid
FROM dbo.Orders
WHERE custid IS NOT NULL;
```

正如你可能预期的那样，该查询在结果集中返回了三行：

```
custid
----
FRNDO
KRLOS
MRPHIS
```

假设你想根据 custid 排序为结果行添加行号。在没有意识到问题的情况下，你会根据 `ROW_NUMBER` 函数向查询表达式添加内容，如下所示（先不要运行查询）：

```
SELECT DISTINCT custid, ROW_NUMBER() OVER(ORDER BY custid) AS rownum
FROM dbo.Orders
WHERE custid IS NOT NULL;
```

在运行查询之前，你预计会在结果中得到多少行？如果你的答案是 3，那么你就错了。这是因为阶段 5-1 在删除重复项之前评估了所有表达式，包括基于 `ROW_NUMBER` 函数的表达式。在这个例中，SELECT 语句在表 VT4 上操作，VT4 有有五行（在应用 WHERE 过滤器之后）。因此，阶段 5-1 生成了一个具有五行的表 VT5。加上行号后，这些行已经是唯一的。当应用阶段 5-2 时，它发现没有重复项需要删除。以下是该查询的结果：

```
custid rownum
----------------------
FRNDO 1
FRNDO 2
KRLOS 3
KRLOS 4
MRPHIS 5
MRPHIS 6
```

如果你想为客户 ID 分配行号，必须先去掉重复的客户 ID。这可以通过表表达式（CTE）来实现，如下：

```
WITH C AS (
  SELECT DISTINCT custid
  FROM dbo.Orders
  WHERE custid IS NOT NULL
)
SELECT custid, ROW_NUMBER() OVER(ORDER BY custid) AS rownum
FROM C;
```

这次你得到了预期的输出：

```
custid rownum
-----------
FRNDO 1
KRLOS 2
MRPHIS 3
```

回到我们的原始示例查询，由于没有指定 DISTINCT，步骤 5-2 被跳过了。在这个查询中，它不会移除行。

### 步骤 6：ORDER BY 阶段

来自上一步的行根据 ORDER BY 子句中指定的列表进行排序，返回游标 V6。ORDER BY 子句是 SELECT 阶段创建的列别名可以重用的步骤。

如果指定了 DISTINCT，ORDER BY 子句中的表达式可以访问 SELECT 阶段返回的虚拟表（VT5）。如果没有指定 DISTINCT，ORDER BY 子句中的表达式可以访问输入和输出表（VT4 和 VT5）。此外，如果没有 DISTINCT，你可以在 ORDER BY 中指定 SELECT 子句中允许的任何表达式。也就是说，你可以对最终返回在结果集中的表达式进行排序。

指定 DISTINCT 时，不允许访问你不返回的表达式是有的。在 SELECT 列表中添加表达式时，DISTINCT 可能会改变返回行数。如果没有 DISTINCT，SELECT 列表的变化不会影响返回行数。

在 ORDER BY 子句中，你还可以指定 SELECT 列表的序号。例如，下面的查询按 custid 然后按顺序排序：

```
SELECT orderid, custid FROM dbo.Orders ORDER BY 2;
```

然而，这种做法是不推荐的，因为你可能会更改 SELECT 列表而忘记相应修改 ORDER BY 列表。此外，当查询字符串很长时，很难看出 ORDER BY 列表中的一项对应 SELECT 列表中的哪一项。

> **重要**：此步骤与其他所有步骤的不同之处在于，它不返回关系结果；而是返回一个游标。记住关系模型是基于理论的，关系的体（SQL 称为表）是元组（行）的集合。集合没有特定的顺序。带有 ORDER BY 子句的查询返回按特定组织的结果。标准 SQL 将这种结果称为游标。理解这是正确理解 SQL 的基本步骤之一。

在描述表的内容时，大多数人（包括我）通常按某种顺序描述行。但因为表是没有特定顺序的集合，这种描述可能会引起误解。图 1-2 显示了正确描述表内容的方法，而不暗示顺序。

![](img/bdc38aa36f6e2987d913ee538147411_45_0.png)

> 客户和订单集。

> **注意**：虽然 SQL 不假设表具有任何给定顺序，但它维护了基于创建顺序的序号。指定 `SELECT *`（尽管由于书中后提到的几个原因这是一个坏习惯）可以保证列按创建顺序返回。在这一方面，SQL 偏离了关系模型。

由于此步骤不返回表（它返回游标），目标尝试消耗表将失败。例如，下面的定义表尝试是无效的：

```
SELECT orderid, custid
FROM dbo.Orders
ORDER BY DESC ) AS
```

同样，下面的定义视图的尝试也是无效的：

```
CREATE VIEW MyOrders
AS
SELECT orderid, custid
FROM dbo.Orders
ORDER BY DESC;
```

有一个异常情况——当 T-SQL 允许根据带有 BY 子句的查询定义表表达式时——即 TOP 或 OFFSET-FETCH 过滤器。将在描述这些过滤器后解释这个异常情况。



ORDER BY 将 NULL 等。也就是说，NULL 排在一起。标准 SQL 将 NULL 排序在低值还是高值取决于实现，且必须保持一致。T-SQL 将 NULL 排序在已知值之前（优先）。将此步骤应用于示例查询：

你得到了表 1-9 所示的游标 V6。

| C.custid | numorders |
|---|---|
| FISSA | 0 |
| FRNDO | 2 |

### 步骤 7：应用 TOP 或 OFFSET-FETCH 过滤器

TOP 和 OFFSET-FETCH 是基于行数和顺序的查询过滤器。这与基于谓词的经典查询过滤器（ON, WHERE, HAVING）形成对比。TOP 是 T-SQL 特有的过滤器，而 OFFSET-FETCH 是标准的。正如提到的，OFFSET-FETCH 是 SQL Server 2012 中引入的。本节在逻辑查询处理的上下文中描述这些过滤器。

过滤器的规范中涉及两个元素。一个是（强制的）要过滤的行数或百分比（向上取整）。另一个（可选的）是定义过滤哪些行的顺序。遗憾的是，TOP 的排序规范（OFFSET-FETCH 相同）是由查询中经典的展示 ORDER 子句定义的，而不是与其脱节并独立于它。我稍后会解释为什么这种设计选择是有问题的并导致了困惑。如果没有指定顺序，你应该假设它是任意的，产生非确定性的结果。这意味着如果你多次运行查询，即使数据保持不变，也无法保证获得可重复的结果。生成了虚拟表 VT7。如果指定了顺序，游标 VC7 返回订单值最高的三个订单：

```sql
SELECT TOP (3) orderid, custid
FROM dbo.Orders
ORDER BY orderid DESC;
```

此查询生成以下输出：

```
orderid    custid
------ -------
7          NULL
6          MRPHOS
5          KRLOS
```

即使指定了 `orderid`，仅凭这一事实并不能保证确定性。如果排序不是唯一的（例如，你将前面的查询中的 `orderid` 更改为 `custid`），则具有相同排序值的行之间的顺序应该被认为是任意的。有两种方法可以让 `TOP` 过滤器变为确定：一种是指定 `ORDER BY` 列表并添加 `WITH TIES` 选项（例如 `custid, orderid`）。另一种是使用非唯一的 `ORDER BY` 列表，这允许过滤器包含底层查询结果中所有与最后返回行具有相同排序值的其他行。使用此选项，返回哪些行的选择将是确定的，且排序不再针对具有相同排序值的行进行。

`OFFSET-FETCH` 过滤器与 `TOP` 类似，但它增加了一个选项，用于指定在指示过滤多少行（`FETCH` 子句）之前跳过多少行（`OFFSET` 子句）。`OFFSET` 和 `FETCH` 子句都指定在强制 `ORDER BY` 子句之后。例如，以下查询根据 `orderid` 降序指定排序，并跳过四行，过滤接下来的两行：

```sql
SELECT orderid, custid
FROM dbo.Orders
ORDER BY orderid DESC
OFFSET 4 FETCH NEXT 2 ROWS ONLY;
```

此查询返回以下输出：

```
orderid    custid
------ -------
3          KRLOS
2          FRNDO
```

从 SQL Server 2014 开始，`OFFSET-FETCH` 的实现不支持 `PERCENT` 和 `WITH TIES` 选项，尽管 SQL 代码支持它们。此步会生成游标 VC7。

在我们的示例中跳过了第 7 步，因为没有指定 `TOP` 和 `OFFSET-FETCH`。

我之前提到过，`TOP` 和 `OFFSET-FETCH` 的排序是由传统定义显示顺序的相同 `ORDER` 子句定义的，这导致了混淆。请考虑以下查询作为示例：

```sql
SELECT TOP (3) orderid, custid
FROM dbo.Orders
ORDER BY orderid DESC;
```

在这里，`ORDER BY` 具有两个不同的用途。一个是传统的显示排序（基于 `orderid` 降序排列的返回行）。另一个是为 `TOP` 过滤器定义选择哪三行（具有最高 `orderid` 值的三行）。但如果你基于查询定义表表达式，情况就会变得复杂。回想“第 6 步：`ORDER BY` 阶段”，通常你不允许基于带有 `ORDER BY` 子句的查询来定义表表达式，因为此类查询会生成游标。我曾尝试定义一个派生表，但当内部查询带有 `ORDER BY` 子句时，该内部查询的尝试是失败的。

这一限制有一个例外，但需要很好地理解以避免产生错误的预期。例外是内部查询允许拥有 `ORDER BY` 子句以支持 `TOP` 或 `OFFSET-FETCH` 过滤器。但在这种情况下，重要的是记住，如果外部查询没有显示的 `ORDER BY` 子句，则结果的显示排序是无法保证的。排序仅对包含 `ORDER BY` 子句的直接查询有效。如果你想保证结果的显示，最外层的查询必须包含 `ORDER BY` 子句。以下是标准中识别此点的准确语言，来自 ISO/IEC 9075-2:2011(E) 第 4.15.3 节 派生表：

> <query expression> 可以包含一个可选的 <order clause>。通过 <query expression> 对表行的排序仅对于包含 <order clause> 的 <query expression> 有保证。

尽管你在实践中观察到了，但在遵循示例时，结果的显示排序是没有保证的，因为最外层的查询没有 `ORDER BY` 子句：

```sql
SELECT orderid, custid
FROM (
    SELECT TOP (3) orderid, custid
    FROM dbo.Orders
    ORDER BY orderid DESC
) AS D;
```

假设你运行上述查询并得到一个似乎按照内部查询排序规范排列的结果。这并不意味着该行为是保证可重复的。它可能是优化方面考虑的结果，而这些方面是不保证可重复的。这是 SQL 从业者经常掉入的最常见陷阱之一——根据观察到的行为得出结论并据此建立预期，而不是正确地理解理论。

此外，人们常犯的一个错误是创建一个“排序视图”。记住，如果你指定了 `TOP` 或 `OFFSET-FETCH` 选项，允许在内部查询中包含 `ORDER BY` 子句。因此，人们可能尝试在不实际过滤行的情况下实现这一点的方法是指定 `TOP (100) PERCENT` 选项，如下：

```sql
-- 尝试创建一个排序视图
IF OBJECT_ID('dbo.MyOrders', 'V') IS NOT NULL DROP VIEW dbo.MyOrders;
GO
```

```sql
-- 注意：这不会创建一个“排序视图”
CREATE VIEW dbo.MyOrders
AS
SELECT TOP (100) PERCENT orderid, custid
FROM dbo.Orders
ORDER BY orderid DESC;
GO
```

考虑针对该视图的以下查询：

```sql
SELECT orderid, custid FROM dbo.MyOrders;
```

根据我刚刚解释的，如果你查询视图且没有在外部查询中指定 `ORDER BY` 子句，你就无法获得任何显示排序保证。当我在我的系统上运行时，我得到按以下顺序的结果：

```
orderid    custid
------ -------
7          NULL
6          MRPHOS
5          KRLOS
4          KRLOS
3          KRLOS
2          FRNDO
1          FRNDO
```

如所示，结果是基于 `orderid` 降序的，但你仍然需要记住这并不是保证的。如果过滤器是根据自己的排序规范设计的，并且与显示的 `ORDER BY` 解离，那么所有的混淆都可以避免。这种分离设计的良好示例是使用窗口函数 `ROW_NUMBER`。你指定排名计算的排序，独立于你为了显示目的可能定义或未定义的排序。但遗憾，对于 `TOP` 和 `OFFSET-FETCH`，木已成舟。因此，责任现在在我们用户身上，要很好地理解设计，并知道从中期待什么，更重要的是，知道不该从中期待什么。

完成后，运行以下代码进行清理：

```sql
IF OBJECT_ID('dbo.MyOrders','V') IS NOT NULL DROP VIEW dbo.MyOrders;
```

注意：APPLY、PIVOT 和 UNPIVOT 不是标准操作符；它们是 T-SQL 特有的扩展。APPLY 在标准中有一个类似的术语叫做 `LATERAL`，但 PIVOT 和 UNPIVOT 则没有。

我之前已经涵盖了连接的逻辑处理阶段。在这里，我将简要描述其他三个操作符以及它们如何融入逻辑查询处理模型。

表操作符接收一个或两个表作为输入。根据它们相对于表操作符关键字（JOIN, APPLY, PIVOT, UNPIVOT）的位置，将它们称为左输入和右输入。输入表不受限制地，可以是以下许多选项之一：普通表、临时表、派生表、CTE 或值值函数。在逻辑查询处理术语中，表操作符从左到右求值，一个操作符返回的虚拟表成为下一个操作符的左输入表。

每个表操作符都执行一组不同的步骤。为了方便和清晰，我将在步骤数字前加上表操作符的首字母（j 代表 JOIN，A 代表 APPLY，P 代表 PIVOT，U 代表 UNPIVOT）。

以下是四个表操作符及其元素：

```
(J) <left_input_table>
{ CROSS | INNER | OUTER } JOIN <right_input_table>
ON <on_predicate>
```

```
(A) <left_input_table>
{ CROSS | OUTER } APPLY <right_input_table>
```

```
(P) <left_input_table>
PIVOT <aggregate_func<aggregation_element>> FOR
<spreading_element> IN(<target_col_list>)
AS <result_table_alias>
```

```
(U) <left_input_table>
UNPIVOT <target_values_col> FOR
<target_names_col> IN(<source_col_list>)
AS <result_table_alias>
```

提醒一下，连接涉及以下步骤的子集（取决于连接类型）：

- J1: 应用卡卡尔积
- J2: 应用 ON 谓词
- J3: 添加外行

## APPLY

APPLY 操作符（取决于应用类型）涉及以下一个或两个步骤：

- A1: 将右表表达式应用到左行
- A2: 添加外行

APPLY 操作符将右表表达式应用于左输入中的每一行。右表表达式可以引用左输入列。右输入会对左输入的每一行进行求值。此步骤通过将每行与右表表达式中的对应行匹配，统一产生的集合，该步骤返回合并后的结果。

步骤 A1 同时适用于 CROSS APPLY 和 OUTER APPLY。步骤 A2 仅适用于 OUTER APPLY。如果内部（右）表表达式对某行返回空集，则 CROSS APPLY 不返回该外（左）行。OUTER APPLY 则将返回一行，并用 NULL 作为内部表表达式属性的占位符。

例如，以下查询返回了每个客户订单 ID 最高的两个订单：

```sql
SELECT C.custid, C.city, A.orderid
FROM dbo.Customers AS C
CROSS APPLY (
    SELECT TOP (2) O.orderid, O.custid
    FROM dbo.Orders AS O
    WHERE O.custid = C.custid
    ORDER BY orderid DESC
) AS A;
```

此查询生成以下输出：

| custid | city | orderid |
|---|---|---|
| FRNDO | Madrid | 2 |
| FRNDO | Madrid | 1 |
| KRLOS | Madrid | 5 |
| KRLOS | Madrid | 4 |
| MKPHS | Zion | 6 |

注意输出中缺少了 FISSA，因为表表达式对其返回了空集。如果您想返回没有下订单的客户，请如下使用 OUTER APPLY：

```sql
SELECT C.custid, C.city, A.orderid
FROM dbo.Customers AS C
OUTER APPLY (
    SELECT TOP (2) O.orderid, O.custid
    FROM dbo.Orders AS O
    WHERE O.custid = C.custid
    ORDER BY orderid DESC
) AS A;
```

此查询生成以下输出：

```
custid  city    orderid
FISSA   Madrid  NULL
FRNDO  Madrid  2
FRNDO  Madrid  1
KRLOS   Madrid  5
KRLOS   Madrid  4
MRPHS  Zion    6
```

## PIVOT

您使用 PIVOT 操作符将数据从行旋转到列（透视），并在过程中执行聚合。

假设您想查询 TSQLV3 示例数据库中的 Sales.OrderValues 查询（示例数据库的详情请参见书籍引言），并返回每个员工处理的每个订单的总值。您希望输出为每个员工占一行，每年一列，并在每个员工和年份的交叉处显示总值。以下 PIVOT 查询允许您实现此目标：

```sql
USE TSQLV;

SELECT empid, [2013], [2014], [2015] AS year, val
FROM (
    SELECT empid, YEAR(orderdate) AS orderyear, val
    FROM Sales.OrderValues
) AS D
PIVOT ( SUM(val) FOR orderyear IN([2013],[2014],[2015]) ) AS P;
```

此查询生成以下输出：

```
empid  2013    2014    2015
9      9894.52   26310.39  41013.17
3      18223.96  108026.17 75652.75
6      16642.61  41326.38  14144.16
7      15232.16  60471.99  48864.89
1      35764.52  93148.11  63195.02
5      49945.12  128809.81  54135.94
5      18383.92  30716.48  19691.90
2      21757.06  70444.11  74336.56
8      22240.12  56032.63  48589.54
```

该查询将每个源行的员工年度值行列转置（拆分）为每个订单年份的单独行，生成如下输出：

| empid | orderyear | val |
| :--- | :--- | :--- |
| 3 | 2013 | 18223.96 |



| 3 | 2014 | 108026.17 |
| 3 | 2015 | 76562.75 |
| 6 | 2013 | 16642.61 |
| 6 | 2014 | 43126.38 |
| 6 | 2015 | 14144.56 |
| 9 | 2013 | 89884.52 |
| 9 | 2014 | 26310.39 |
| 9 | 2015 | 41103.17 |
| 7 | 2013 | 15232.16 |
| 7 | 2014 | 60471.99 |
| 7 | 2015 | 48864.89 |
| 1 | 2014 | 93146.11 |
| 1 | 2015 | 63195.02 |
| 4 | 2013 | 49945.12 |
| 4 | 2014 | 128809.81 |
| 4 | 2015 | 54135.94 |
| 2 | 2014 | 70444.14 |
| 2 | 2015 | 74316.56 |
| 5 | 2013 | 18383.92 |
| 5 | 2014 | 30716.48 |
| 5 | 2015 | 19691.90 |
| 8 | 2013 | 22240.12 |
| 8 | 2014 | 56032.63 |
| 8 | 2015 | 48589.54 |

UNPIVOT 操作涉及三个逻辑处理阶段：

1.  **U1: 生成副本**
2.  **U2: 提取元素**
3.  **U3: 移除包含 NULL 的行**

第一步 (`U1`) 生成从作为 `UNPIVOT` 输入的左表表达式（在本例中为 `EmpYearValues`）生成的行副本。这一步为每个被行列转置的列（在 `UNPIVOT` 算子的子句中）生成一个副本。由于 `IN` 子句中有三个列名，因此每个源行都会产生三份副本。生成的虚拟表将包含一个新列，用源列名作为字符字符串存储。该列的名称将是 `IN` 子句之前指定的名称（在本例中为 `orderyear`）。第一步返回的虚拟表如表 1-10 所示。

### 表 1-10 UNPIVOT 第一步返回的虚拟表

| empid | 2013 | 2014 | 2015 | orderyear |
| :--- | :--- | :--- | :--- | :--- |
| 3 | 18223.96 | 108026.17 | 76562.75 | 2013 |
| 3 | 18223.96 | 108026.17 | 76562.75 | 2014 |
| 3 | 18223.96 | 108026.17 | 76562.75 | 2015 |
| 6 | 16642.61 | 43126.38 | 14144.56 | 2013 |
| 6 | 16642.61 | 43126.38 | 14144.56 | 2014 |
| 6 | 16642.61 | 43126.38 | 14144.56 | 2015 |
| 9 | 89884.52 | 26310.39 | 41103.17 | 2013 |
| 9 | 89884.52 | 26310.39 | 41103.17 | 2014 |
| 9 | 89884.52 | 26310.39 | 41103.17 | 2015 |
| 7 | 15232.16 | 60471.99 | 48864.89 | 2013 |
| 7 | 15232.16 | 60471.99 | 48864.89 | 2014 |
| 7 | 15232.16 | 60471.99 | 48864.89 | 2015 |
| 1 | NULL | 93146.11 | 63195.02 | 2013 |
| 1 | NULL | 93146.11 | 63195.02 | 2014 |
| 1 | NULL | 93146.11 | 63195.02 | 2015 |
| 4 | 49945.12 | 128809.81 | 54135.94 | 2013 |
| 4 | 49945.12 | 128809.81 | 54135.94 | 2014 |
| 4 | 49945.12 | 128809.81 | 54135.94 | 2015 |
| 2 | NULL | 70444.14 | 74316.56 | 2013 |
| 2 | NULL | 70444.14 | 74316.56 | 2014 |
| 2 | NULL | 70444.14 | 74316.56 | 2015 |
| 5 | 18383.92 | 30716.48 | 19691.90 | 2013 |
| 5 | 18383.92 | 30716.48 | 19691.90 | 2014 |
| 5 | 18383.92 | 30716.48 | 19691.90 | 2015 |
| 8 | 22240.12 | 56032.63 | 48589.54 | 2013 |
| 8 | 22240.12 | 56032.63 | 48589.54 | 2014 |
| 8 | 22240.12 | 56032.63 | 48589.54 | 2015 |

第二步 (`U2`) 从当前行的行转置元素对应的源列中提取值。存储值的目标列名称在 `FOR` 子句之前（在本例中为 `val`）。目标列将包含来自虚拟表中当前行对应的源列的值。此步返回的虚拟表如表 1-11 所示。

### 表 1-11 UNPIVOT 第二步返回的虚拟表

| empid | val | orderyear |
| :--- | :--- | :--- |
| 3 | 18223.96 | 2013 |
| 3 | 108026.17 | 2014 |
| 3 | 76562.75 | 2015 |
| 6 | 16642.61 | 2013 |
| 6 | 43126.38 | 2014 |
| 6 | 14144.56 | 2015 |
| 9 | 89884.52 | 2013 |
| 9 | 26310.39 | 2014 |
| 9 | 41103.17 | 2015 |
| 7 | 15232.16 | 2013 |
| 7 | 60471.99 | 2014 |
| 7 | 48864.89 | 2015 |
| 1 | NULL | 2013 |
| 1 | 93146.11 | 2014 |
| 1 | 63195.02 | 2015 |
| 4 | 49945.12 | 2013 |
| 4 | 128809.81 | 2014 |
| 4 | 54135.94 | 2015 |
| 2 | NULL | 2013 |
| 2 | 70444.14 | 2014 |
| 2 | 74316.56 | 2015 |
| 5 | 18383.92 | 2013 |
| 5 | 30716.48 | 2014 |
| 5 | 19691.90 | 2015 |
| 8 | 22240.12 | 2013 |
| 8 | 56032.63 | 2014 |
| 8 | 48589.54 | 2015 |

`UNPIVOT` 的第三也是最后一步 (`U3`) 是移除结果列（在本例中为 `val`）中的 `NULL` 值。此步返回的虚拟表如表 1-12 所示。

### 表 1-12 UNPIVOT 第三步返回的虚拟表

| empid | val | orderyear |
| :--- | :--- | :--- |
| 3 | 18223.96 | 2013 |
| 3 | 108026.17 | 2014 |
| 3 | 76562.75 | 2015 |
| 6 | 16642.61 | 2013 |
| 6 | 43126.38 | 2014 |
| 6 | 14144.56 | 2015 |
| 9 | 89884.52 | 2013 |
| 9 | 26310.39 | 2014 |
| 9 | 41103.17 | 2015 |
| 7 | 15232.16 | 2013 |
| 7 | 60471.99 | 2014 |
| 7 | 48864.89 | 2015 |
| 1 | 93146.11 | 2014 |
| 1 | 63195.02 | 2015 |
| 4 | 49945.12 | 2013 |
| 4 | 128809.81 | 2014 |
| 4 | 54135.94 | 2015 |
| 2 | 70444.14 | 2014 |
| 2 | 74316.56 | 2015 |
| 5 | 18383.92 | 2013 |
| 5 | 30716.48 | 2014 |
| 5 | 19691.90 | 2015 |
| 8 | 22240.12 | 2013 |
| 8 | 56032.63 | 2014 |
| 8 | 48589.54 | 2015 |

完成后，运行以下代码进行清理：

```sql
IF OBJECT_ID('dbo.EmpYearValues') IS NOT NULL DROP TABLE dbo.EmpYearValues;
```

## 窗口函数

你使用窗口函数对源自底层结果集的集合（窗口）逐行进行数据分析。使用名为 `OVER` 子句来定义窗口规格。T-SQL 支持多种窗口函数：聚合、排序、偏移和统计。

与本章中描述的其他功能的做法一样，这里的重点将仅仅是逻辑处理。如所述，窗口函数所作用的集合源自底层结果集。如果你从逻辑处理的角度考虑，只有在进入 `SELECT` 阶段 (5) 时才能获得结果集。在此阶段之前，结果仍处于形成阶段。因此，窗口函数仅限制在 `SELECT` (5) 和 `ORDER BY` (6) 阶段，如列表 1-3 所示。

### 列表 1-3 逻辑处理中的窗口函数

```sql
(5) SELECT (5-2) DISTINCT (7) TOP<top_specification> (5-1) <select_list>
(1) FROM (3) <left> <join_type> JOIN <right> ON <on_predicate>
(1-A) <left> <apply_type> APPLY <right_input_table> AS alias
(1-P) <left> PIVOT(<pivot_specification>) AS alias
(1-U) <left> UNPIVOT(<unpivot_specification>) AS alias
(2) WHERE <where_predicate>
(3) GROUP BY <group_by_specification>
(4) HAVING <having_predicate>
(6) ORDER BY <order_by_list>
(7) OFFSET <offset_specification> ROWS NEXT <fetch_specification> ROWS ONLY;
```

尽管我可能会详细解释窗口函数的工作原理，但我想在允许的这些阶段演示它们的用法。以下示例在 `SELECT` 列表中包含了 `COUNT` 窗口聚合函数：

```sql
USE TSQLV3;
```

```sql
SELECT orderid, custid,
COUNT(*) OVER(PARTITION BY custid) AS numordersforc
FROM Sales.Orders
WHERE shipcountry = 'Spain';
```

该查询产生以下输出：

| orderid | custid | numordersforc |
| :--- | :--- | :--- |
| 10326 | 8 | 3 |
| 10801 | 8 | 3 |
| 10970 | 8 | 3 |
| 10928 | 29 | 5 |
| 10568 | 29 | 5 |
| 10887 | 29 | 5 |
| 10366 | 29 | 5 |
| 10426 | 29 | 5 |
| 10550 | 30 | 10 |
| 10303 | 30 | 10 |
| 10888 | 30 | 10 |
| 10911 | 30 | 10 |
| 10629 | 30 | 10 |
| 10872 | 30 | 10 |
| 10874 | 30 | 10 |

# UNION、EXCEPT 和 INTERSECT 操作符

本节重点关注 `UNION`（包括 `ALL` 和隐式去重版本）、`EXCEPT` 和 `INTERSECT` 的逻辑查询处理方面。这些操作符对应数学集合论中的相似操作符，但在 SQL 的情况下，它们被应用于关系（relations），而关系是一种特殊的集合。列表 1-4 包含了应用这些操作符之一的查询通用形式，并为代码中不同元素的逻辑处理顺序分配了数字。

### 列表 1-4 应用 UNION、EXCEPT 或 INTERSECT 操作符的查询通用形式

```
(1) query1
(2) <operator>
(2) query2
(3) [ORDER BY <order_by_list>]
```

`UNION`、`EXCEPT` 和 `INTERSECT` 操作符比较两个输入之间的完整行。T-SQL 支持两种 `UNION` 操作符。`UNION ALL` 操作符返回一个包含两个输入中所有行的单一结果集。`UNION` 操作符返回一个包含来自两个输入合并后的唯一行的结果集（不包含重复项）。`EXCEPT` 操作符返回出现在第一个输入中但不在第二个输入中的唯一行。`INTERSECT` 操作符返回同时出现在两个输入中的唯一行。

单个查询中不允许使用 `ORDER BY` 子句，因为查询旨在返回集合（无序的）。你可以在查询的末尾指定 `ORDER BY` 子句，它将应用于操作符的结果。

从逻辑处理的角度来看，每个输入查询首先被单独处理，并经过所有相关阶段（不包括不被允许的用于展示的 `ORDER BY`）。然后应用操作符，如果指定了 `ORDER BY` 子句，则将对其应用于结果集。

以以下查询为例：

```sql
USE TSQL;

SELECT region, city
FROM Sales.Customers
WHERE country = 'USA'

INTERSECT

SELECT region, city
FROM HR.Employees
WHERE country = 'USA'

ORDER BY region, city;
```

该查询生成了以下输出：

```
region          city
----------------  ----------
WA              Kirkland
WA              Seattle
```

首先，每个输入查询都按照所有相关的逻辑处理阶段单独处理。第一个查询返回来自美国客户的地点（地区，城市）。第二个查询返回来自美国员工的地点。`INTERSECT` 操作符返回在两个输入中都出现的行——在我们的案例中即既是客户位置又是员工位置的地点。最后，`ORDER BY` 子句按地区和城市对行进行排序。

作为逻辑处理阶段的另一个示例，以下查询使用 `EXCEPT` 操作符返回没有下订单的客户：

```sql
SELECT custid FROM Sales.Customers
EXCEPT
SELECT custid FROM Sales.Orders;
```

第一个查询返回 `Customers` 表中的客户 ID 集合，第二个查询返回来自第二个集合的客户 ID 集合。`EXCEPT` 操作符返回来自第一个集合但不在第二个集合中的行集。请记住，集合没有重复项；`EXCEPT` 操作符返回第一个集合中未出现在第二个集合中的唯一行。

结果集的列名由操作符的第一个输入决定。相应位置的列必须具有兼容的数据类型。最后，在比较行时，`UNION`、`EXCEPT` 和 `INTERSECT` 操作符隐式地使用去重谓词（一个 `NULL` 不等同于另一个 `NULL`；`NULL` 不不同于非 `NULL` 值）。

## 结论

理解逻辑查询处理和 SQL 的独特方面对于 SQL 从业人员至关重要。通过熟悉语言的这些方面，你可以产生正确的解决方案并解释你的选择。记住，核心思想是掌握基础。

# 第 2 章

## 查询调优

第一章“逻辑查询处理”侧重于 SQL 的逻辑设计。本章侧重于 Microsoft SQL Server 平台上的物理实现。由于 SQL 是基于标准的，你会发现不同数据库平台中的核心语言元素看起来是相同的。然而，由于物理层并非标准，你会看到不同平台之间存在更大的差异。因此，要擅长查询调优，你需要非常熟悉你所工作特定平台的物理层。本章涵盖了 SQL Server 物理层的各个方面，为你的查询调优提供基础。

要调优查询，你需要分析查询执行计划并查看不同工具提供的性能衡量指标。此过程的一个关键步骤是找到并识别计划中代表更多工作量的活动，并将性能衡量指标的相关部分与这些活动联系起来。一旦你搞定了这部分，就需要尝试消除代表大部分工作量的活动。

要理解你在查询执行计划中看到的内容，你需要非常熟悉访问方法（`access methods`）。要理解访问方法，你需要非常熟悉 SQL Server 使用的内部数据结构。

本章从介绍内部数据结构开始。然后描述了你将用于查询处理的工具。这些之后是对访问方法的详细讨论，以及涉及这些访问方法的查询执行计划的检查。本章还涵盖了基数估计（`cardinality estimates`）、索引特性、用于调优的查询优先级、索引和查询信息及统计、临时表、基于集合与迭代的解决方案、通过查询修订进行查询调优以及并行查询执行。

本章侧重于传统的磁盘表。内存优化表将在第 10 章“内存 OLTP”中单独介绍。

### 内部结构

本节关注 SQL Server 中的内部数据结构。它从描述页（`pages`）和区（`extents`）开始。然后讨论将表组织为堆（`heap`）相对于 B 树和非聚集索引的组织方式。

### 页和区

页（`page`）是 SQL Server 存储的 8-KB 单元。对于磁盘表，页是 SQL Server 可以读取或写入的最小 I/O 单元。这方面在内存优化表上发生了变化，但正如所述，这些将在第 10 章单独讨论。图 2-1 显示了页结构的图。

![](img/bdc38aa6f6e2987d913ee5381474711_66_0.png)

**图 2-1 页结构图。**



页的 96 字节头包含此类信息，例如该页属于哪个分配单元、如果该页是索引的一部分，则指向链表中前一个页和下一页的指针、页中的空闲量以及内存。根据分配单元，你最终可以确定哪些对象页属于 `views.allocation_units` 和 `sys.partitions`。对于数据页和索引页，页体包含数据或索引记录。在页的末尾有一个行偏移数组（row-offset array），这是一个由双字节指针组成的数组，指向页中的各个记录。页头中前一个和后一个指针与行偏移数组的结合强制了索引顺序。

为了出于读或写目的操作页，SQL Server 需要缓冲池（buffer pool，内存中的数据缓存）中的页。SQL Server 无法直接与磁盘上的页进行交互。如果 SQL Server 需要读取一个页，且该页由于之前的活动已存在于数据缓存中，它将只执行逻辑读取（从内存读取）。如果页不在内存中，SQL Server 将首先执行物理读取，将页从数据文件调入内存。同样，如果 SQL Server 需要写入一个页且该页已在内存中，它将执行逻辑写入。它还会在页头中设置脏标记（dirty flag），以指示内存中的状态比数据文件中的状态更新。

SQL Server 定期运行名为 `lazywriter` 和 `checkpoint` 的进程，将脏页从缓存写入磁盘，有时也会使用其他线程协助完成此任务。

这种方法被称为 LRU-K2，根据最后两次访问（记录在内存中的页头中）来优先从数据缓存中释放页。SQL Server 主要通过懒性写入器（`lazywriter`）进程根据此算法将页标记为可用。

区（extent）是一个包含连续页的单元，如图 2-2 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_67_0.png)

图 2-2 区示意图。

SQL Server 支持两种类型的区，称为混合区（mixed）和统一区（uniform）。对于新对象（表或索引），SQL Server 每次从混合区中分配一个区，直到其达到 8 页的大小。同一个区的不同页可以属于不同的对象。SQL Server 使用称为共享分配映射（SGAMs）的位图页来跟踪哪些区是混合的并且有可分配的页。一旦对象的大小达到 8 页，SQL Server 将以后所有的页分配都从统一区中进行。统一区完全由同一个对象所有。SQL Server 使用称为全局分配映射（GAMs）的位图页来跟踪哪些区是空闲的。

## 表组织

表可以通过两种方式之一进行组织——堆（heap）或 B 树。从技术上讲，当表定义了聚集索引时，它被组织为 B 树；如果没有则组织为堆。你可以直接使用 `CREATE CLUSTERED INDEX` 命令创建聚集索引，或者从 SQL Server 2014 开始，使用内联索引定义 `INDEX <index_name> CLUSTERED`。你也可以通过主键或唯一约束的定义间接地创建聚集索引。当你向表添加主键约束时，SQL Server 将将其强制执行为聚集索引，除非你指定了 `NONCLUSTERED` 或表上已存在聚集索引。当你为表指定唯一约束时，SQL Server 将使用非聚集索引来强制执行，除非你指定 `CLUSTERED` 关键字。无论何种情况，如所述，有聚集索引的表被组织为 B 树，而没有聚集索引的被组织为堆。这种表的组织方式被称为 HOBT。

在 SQL 中，看到组织为 B 树的表要常见得多。主要原因可能是当你定义主键约束时，SQL Server 默认使用聚集索引来强制执行。在人们创建表时没有考虑物理组织并使用默认值定义主键的情况下，他们最终会得到 B 树。因此，SQL Server 中关于 B 树的经验远比堆多。此外，聚集索引对插入模式和读取模式都提供了级别的控制。由于这些原因，在其他条件都相同的情况下，我通常倾向于默认使用 B 树组织。

某些情况下堆可以带来收益。例如，在第 6 章“数据修改”中，我描述了批量工具以及为了以最小日志记录处理导入所需的条件。如果目标表是 B 树，那么在你启动想要获得最小日志的导入时，它必须是空的。如果是堆，即使它已经包含数据，也可以获得最小日志。因此，当目标表已包含数据且你正在添加大量数据时，你可以先删除索引，导入到堆中然后重建索引，从而获得更好的性能。在这个示例中，你将堆用作临时状态。

无论表如何组织，它都对其定义零或多个非聚集索引。非聚集索引始终组织为 B 树。HOB（表对象）以及非聚集索引可以以不同的方式进行分区。每个 HOB 的每个分区以及非聚集索引数据存储在称为分配单元（allocation units）的页集合中。三种类型的分配单元被称为 `ROW_DATA`、`ROW_OVERFLOW_DATA` 和 `L_DATA`。

`ROW_DATA` 存储固定长度列；只要行不超过 8,060 字节限制，它也存储变长度列。`ROW_OVERFLOW_DATA` 存储 `VARCHAR`、`NVARCHAR`、`VARBINARY`、`VARIANT` 或 CLR 定义类型，这些类型不超过 8000 字节，但因为超过 8060 字节的大小限制而被移出原始行。`L_DATA` 存储大对象值——超过 8000 字节的 `VARCHAR(MAX)`、`NVARCHAR(MAX)`、`VARBINARY(MAX)`、XML 或 CLR。系统视图 `sys_internal_allocation_units` 存储在分配单元中的页集合锚。

在接下来的章节中，我将描述堆、聚集索引是非聚集索引。为了简单起见，我假设数据是非分区的；但如果是分区的，该描述适用于单个分区。

### 堆

堆是一个没有聚集索引的表。这种结构之所以被称为堆，是因为数据没有按任何顺序组织；而是作为一组页和区布局的。示例数据库 `PerformanceV`（有关如何安装示例数据库的详情请参见本书引言）中的 `Orders` 实际上被组织为 B 树，但图 2-3 展示了它组织为堆时可能后的样子。

SQL Server 将属于一个或多个称为分配映射（IAMs）的位图页的数据映射。IAM 页的页头具有指向 SQL Server 从混合区为堆分配的前八个页的指针。每个页还指向指向 IAM 页在数据文件中映射的 4 GB 范围起始位置的指针。IAM 页对该范围内的每个区都有一个表示。如果 IAM 页不属于该对象，SQL Server 将维护一个 IAM 页链。当 SQL Server 需要读取堆时，它依赖 IAM 页中的信息来确定它需要哪些页。

我没有解释清楚页拆分（因为页拆分发生在 B 树中），但目前只需证明堆表（heaps）不会产生页拆分。

### B 树（聚集索引）

SQL Server 中基于磁盘的表的所有索引都结构化 B 树，这是平衡树的一种特例。平衡树是指没有任何叶子节点到根节点的距离远多于任何其他叶子节点的树。

聚集索引的结构为 B 树，它在叶子节点层维护整个表的数据。聚集索引并不是数据的副本；它本身就是数据。图 2-4 展示了当 `Orders` 表按照 `order` 列的详细信息组织成 B 树时可能的光景。

![](img/bdc38aa36f6e2987d913ee5381474711_70_0.png)

如图 2-4 所示，`Orders` 表的完整数据存储在索引层级。数据行按键值顺序（在我们的案例中为 `orderdate`）组织。双向链维护了页之间的顺序，页面的行偏移数组维护了页内的顺序。当 SQL Server 需要在索引层级执行有序扫描（范围扫描）操作时，它是通过遵循链表来实现。我将这种扫描称为索引顺序。

注意图 2-4，对于每一行，索引都会维护一个列唯一标识符（在插图中缩写为 `ung`）。该列中的值列举了具有相同键值的行，当索引列不唯一时，它与键值结合使用，以唯一标识这些行。我将在稍后讨论非交换索引（noncommutative indexes）时详细阐述唯一标识符的用途。

当优化器对查询进行优化时，它需要选择算法来处理连接、分组和聚合、去重、窗口函数和显示顺序等操作。某些操作仅可以使用基于顺序的算法处理，例如显示顺序（查询中的 `ORDER BY` 子句）。某些操作可以使用多种算法处理，包括基于顺序的算法或基于哈希的算法。连接可以使用基于顺序、基于哈希或基于循环的算法处理。要使用基于顺序的算法，数据需要是有序的。优化器获取有序数据的一种方法是在计划中添加一个显式的排序操作。然而，显式的排序操作需要内存授予（memory grant），且扩展性较差（N 扩展）。

另一种获取有序数据的方法是执行索引扫描（假设索引存在）。这通常比其他替代方案更高效。此外，它不需要像显式排序和哈希算子那样需要内存授予。当索引不存在时，优化器只剩下剩余选项。对于只能用基于顺序的算法处理的操作（如分组和聚合），对于可以使用多种算法处理的操作，优化器将根据成本估算做出选择。由于排序的扩展性较差，优化器倾向于选择对少量行排序的策略。哈希算法的扩展性通常优于排序，因此优化器倾向于对大量行使用哈希。

关于索引文件层级的数据，文件中页的顺序可能与索引顺序不匹配。如果页 `x` 指向下一页 `y`，而 `y` 在文件中出现在页 `x` 之前，则 `y` 被视为无序页。逻辑扫描碎片（也称为百分比平均碎片）被衡量为无序页占数的百分比。如果索引文件层级中有 25 个页，其中有 5 页是无序的，那么你的逻辑扫描碎片率为 20%。索引逻辑扫描碎片的主要原因是：当数据未缓存时，索引扫描操作会变慢。当数据被缓存时，这种碎片对任何索引扫描的影响往往很小。

当 SQL Server 需要在索引的叶节点级别查找特定的键（key）时，它会执行一种称为寻查找（seek）的访问方法。该访问方法从根页开始，识别出包含所查找键范围的行。它向下遍历级别，每层读取一个页面，直到到达叶层级中包含第一个匹配项的页面。然后，访问方法在叶层级上执行范围扫描（range scan）以找到所有匹配的键。请记住，所有页面距离根页的距离都是相同的。这意味着访问方法将读取与索引层数等数量的页面以到达第一个匹配项。这些读取的 I/O 模式是随机 I/O，而不是顺序 I/O，因为寻查找操作在到达叶层级之前读取的页面将是相邻的。

在性能估算方面，了解索引的层数非常重要，因为这将决定了寻查找操作在页读取上的成本，而且执行计划会反复调用多次寻查找操作（例如，嵌套循环连接算子）。对于已存在的索引，你可以对索引调用 `INDEXPROPERTY` 函数来获取这个数字；对于你尚未创建的索引，你需要熟悉 `IndexDepth` 属性以便使用它来估算索引将包含的层数。

计算索引层数（记为 L）所需的的操作数和步骤如下所示（请记住，除非显式说明，否则这些计算适用于聚集索引和无序索引）：

- 表中的行数（称为 `num_rows`）：在我们的案例中，该值是 1,000。

- 平均总行行大小（称为 `leaf_row_size`）：在聚集索引中，这实际上是数据行的大小。我所说的“总行（gross）”是指你需要考虑行的开销以及行偏移区域中 2 字节指针的开销。行开销通常涉及几个字节。在我们的 `Orders` 表中，平均数据行大小为 200 字节。

- 平均页面填充密度（称为 `page_density`）：这是页面填充情况的百分比值。页面密度受删除、页拆分以及使用低于 100% 的填充因子（fillfactor）值重建索引等因素的影响。我们表中的聚集索引是基于升序键模式的；因此，在我们的案例中，`page_density` 可能接近 100%。

- 容纳在叶页中的行数（称为 `rows_per_leaf_page`）：计算此值的公式为 `FLOOR((page_size - header_size) * page_density / leaf_row_size)`。在我们的案例中，`rows_per_leaf_page` 等于 `FLOOR((192 - 96) * 1 / 200)`。

- 页面总数（称为 `num_leaf_pages`）：这是一个简单的公式：`num_rows / rows_per_leaf_page`。在我们的案例中，它等于 `1,000,000 / 40 = 25,000`。

- 平均非叶节点行大小（称为 `non_leaf_size`）：非叶节点行包含索引的列（在我们的案例中，只有 `orderdate`，为 3 字节）；4 字节的唯一标识符（仅存在于非唯一的聚集索引中）；6 字节的页面指针；几个额外的内部开销（在我们的案例中总计为 7 字节）；在我们的案例中，总非叶节点行大小为 20 字节。

- 容纳在非叶页中的行数（称为 `rows_per_non_leaf_page`）：计算此值的公式与计算 `rows_per_leaf_page` 类似。它是 `FLOOR(page_header_size) / non_leaf_row_size`，在我们的案例中，等于 `FLOOR(8192 – 96) / 20 = 404`。

- 叶节点之上的级别（称为 `L-1`）：该值通过以下公式计算：`CEILING(LOG(num_leaf_pages))`。在我们的案例中，它等于 `CEILING(LOG(25000)) = 5`。

- 索引深度（称为 `L`）：该值通过以下公式计算：`CEILING(LOG(num_leaf_pages)) + 1`。在我们的案例中，它等于 `5 + 1 = 6`。

- 索引能够容纳的行数（称为 `N`）：除非显式说明，否则这些计算适用于聚集索引和无序索引。对于非聚集索引，寻查找操作在 2 层、3 层或 4 层之间的 I/O 模式取决于数据的大小。对于小表，寻查找可能是 2 层，对于中等表是 3 层，对于大表则是 4 层。

### B 树上的非聚集索引

在 B 树上创建的非聚集索引在架构上与堆（heap）不同。区别在于，在 B 树上创建的非聚集索引中，行定位符是一个称为聚集键（clustering key）的值，通常称为 RID。聚集键包含了被指向行中的聚集索引键值以及行唯一标识符（如果存在）。这种思想是从逻辑和物理两个层面上指向某行。这种架构是为 OLTP 系统设计的；然而，当发生数据插入时，聚集索引往往会引发页拆。如果聚集索引使用 RID 作为行定位符，那么所有指向可能移动的数据行的指针都将发生更改以反映它们的新 RID。想象一下这对于表上的多个非聚集索引会对性能产生多大的影响。相反，SQL Server 维护了逻辑指针，当数据在聚集索引的叶页之间移动时，这些指针不会改变。

图 2-6 展示了 PK Orders 非聚集索引可能的样子；该索引以 `order` 为键定义，表显示了以 `order` 为键列定义的聚集索引。

![](img/bdc38aa36f6e2987d913ee5381474711_76_0.png)

**图 2-6 B 树上的非聚集索引。**

对非聚集索引中特定键（或 `order` 值）的查找（seek）操作最终将到达相关的叶行，然后访问行定位符。行定位符是被指向行的聚集键。为了实际到达被指向的行，查找（lookup）操作需要根据获取的聚集键在聚集索引中进行。

这种查找被称为键查找（key lookup），相对于 RID 查找（RID lookup）。我将在本章稍后部分演示这种访问方法。每次查找操作的成本（按页读取次数计算）与聚集索引的层数一样（在我们的案例中为 3 层）。相比之下，当表是堆时，RID 查找只需要单个页。当然，在进行范围查询时，我们使用非聚集索引和一系列查找，堆缓存与聚集表案例在逻辑读取次数上的比例之比将接近于 L，其中 L 是聚集索引的层数。

## 衡量查询性能的工具

SQL Server 提供了许多工具来衡量查询性能，但需要记住的一点是，最终重要的是用户体验。用户主要关心两点：响应时间（第一行返回所需的时间）和吞吐量（查询完成所需的时间）。自然，作为技术人员，我们需要识别不同的性能衡量标准，我们认为这些是影响最终用户体验的主要因素。我们倾向于查看诸如读取次数（主要关注 I/O 密集型活动）以及 CPU 时间和经过时间（elapsed time）。

我在本章中使用的示例将针对示例数据库 PerformanceV3。（有关如何安装它的详细信息，请参阅书的介绍）。运行以下代码连接到示例数据库：

```sql
SET NOCOUNT ON
USE PerformanceV3;
```

我将使用以下查询来演示衡量查询性能的工具：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 10000;
```

当你想在测试环境中衡量查询性能时，你需要考虑预计生产环境对于该查询是热缓存还是冷缓存。如果是前者，你想执行两次查询并衡量第二次执行的性能。第一次执行将导致所有页带入数据缓存，而第二次执行将在热缓存上运行。如果是后者，在运行查询之前，你想运行一个手动检查点（checkpoint）将脏缓冲区写入磁盘并删除缓存中的所有缓冲区，如下：

```sql
CHECKPOINT
DBCC DROPCANBUFFERS;
```

注意，虽然你应该只在隔离的测试环境中手动清除数据缓存，但显然此操作对查询性能有负面影响。这两个命令都需要权限。

我使用三个主要的内置工具来分析和衡量查询性能：图形化执行计划、STATISTICS IO 和 STATISTICS TIME 会话选项，以及带有语句完成事件的扩展会话（Extended Session）。我使用图形化执行计划来分析优化器为查询创建的计划。当需要衡量单个查询或少量查询的性能时，我使用会话选项。我需要衡量大量查询的性能。



# 关于执行计划

你可以在 SQL Server Management Studio (SSMS) 中通过突出显示查询并点击 SQL 编辑器工具栏上的“显示估计执行计划”（`Ctrl+L`）按钮来请求查看估计计划。你可以通过启用“包含实际执行计划”（`Ctrl+M`）并执行查询来查看实际计划。我通常更倾向于分析实际计划，因为它包含了实际返回的行数以及每个算符的实际执行次数。优化器的次优选择通常由于基数估计不准确造成的，这些可以通过比较实际执行计划中的估计值和实际值来检测。

使用以下代码通过会话选项 `STATISTICS IO`（用于 I/O 信息）和 `STATISTICS TIME`（用于时间信息）启用查询性能统计：

```sql
SET STATISTICS IO, TIME ON;
```

当你运行查询时，SSMS 将在“消息”窗中报告性能信息。

要使用扩展事件衡量从 SSMS 提交的临时查询性能，请捕获 `sql_statement_completed` 事件，并过滤提交查询的 SSMS 会话的会话 ID。使用以下代码创建：

```sql
CREATE EVENT SESSION [performance] ON SERVER
ADD EVENT sqlserver.sql_statement_completed
(
    ACTION (sqlserver.sql_text)
)
WHERE ([sqlserver.session_id] = (SELECT SESSION_ID()));
GO
ALTER EVENT SESSION [performance] ON SERVER STATE = START;
```

紧接在 `STATISTICS IO` 行之后出现的行代表了查询的执行。为了在冷缓存中处理我们的查询，SQL Server 使用了 170 ms 的 CPU 时间，查询耗时 765 ms 的时钟时间完成。

图 2-8 显示了扩展事件会话 query_performance 的监视数据（Watch Data）窗口，其中突出显示了针对冷缓存的示例查询的执行。

| name | timestamp |
|---|---|
| sql_statement_completed | 2014-10-25 17:43:46.455859 |
| sql_statement_completed | 2014-10-25 17:43:48.962804 |
| sql_statement_completed | 2014-10-25 17:43:48.913784 |
| sql_statement_completed | 2014-10-25 17:43:51.62405 |

事件: `sql_statement_completed` (2014-10-25 17:43:51.62405)

| Field | Value |
|---|---|
| cpu_time | 170 |
| duration | 765 |
| last_row_count | 10000 |
| line_number | 1 |
| logical_reads | 25339 |
| offset | 0 |
| offset_end | -1 |
| physical_reads | 25146 |
| row_count | 10000 |
| statement | `SELECT orderid, custid, empid, orderdate, filler FROM Orders WHERE orderid <= 10000` |
| writes | 0 |

**图 2-8** 来自扩展事件会话的信息。

现在缓存是热的，再次运行该查询。我从 `STATISTICS IO` 得到了以下输出：`Table 'Orders'. Scan count 9, logical reads 25339, physical reads 0, read-ahead reads 0, 0 logical reads 0, 0 physical reads 0, 0 read-ahead reads 0`。注意代表物理读取的指标均为 0。我从 `STATISTICS TIME` 得到了以下输出：`CPU time = 26 ms, elapsed time = 299 ms`。自然地，有了热缓存，查询完成得更快。

# 访问方法

本节提供了 SQL Server 访问数据的各种方法的描述；它被设计用于书中所有涉及执行计划分析的参考。本节中的示例使用了针对 `Orders` 表的查询。该表被组织为 B 树，并以 `orderid` 为键定义了聚簇索引。我们使用以下代码创建 `Orders` 表的副本 `Orders2`，并将其作为一个堆：

```sql
IF OBJECT_ID('dbo.Orders2', 'U') IS NOT NULL DROP TABLE Orders2;
SELECT * INTO Orders2 FROM Orders;
ALTER TABLE Orders2 ADD CONSTRAINT PK_Orders2 PRIMARY KEY (orderid);
```

当我想展示针对 B 树组织的表的访问方法时，我会查询 `Orders`。当我想展示针对堆组织的表的访问方法时，我会查询 `Orders2`。为了演示，我使用了随机化来生成示例数据。这意味着当你查询此数据库中的对象时，你的结果可能与我的不同。与访问方法相关的成本大部分是 I/O 活动。因此，我提供了逻辑读取次数作为访问方法性能的主要衡量标准。

## 表扫描/非聚簇索引扫描

我描述的第一种方法是在当不需要按特定顺序返回数据时，对表进行全扫描。在两种主要情况下，你会得到全扫描。一种是你确实需要表中的所有行。另一种是你需要行的一个子集，但有一个良好的索引来支持你的过滤。棘手之处在于，全扫描的查询在底层表的组织结构（堆或 B 树）上看起来有所不同。当底层表是堆时，计划将显示一个名为 Table Scan（表扫描）的算子。当底层表是 B 树时，计划将显示一个 `Ordered False` 的 Clustered Index Scan（聚簇索引扫描，无序）算子。我将前者称为表扫描，将后者称为无序聚簇索引扫描。

表扫描或非聚簇索引扫描涉及对属于表的所有数据页进行扫描。针对结构为堆的 `Orders2` 表的查询将被扫描：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders2;
```

图 2-9 显示了关系引擎优化器为该查询生成的图形化执行计划，图 2-10 显示了存储引擎处理这种访问方法的插图。

**Table Scan [Orders2]**

Cost: 100 %

| Physical Operation | Table Scan |
|---|---|
| Logical Operation | Table Scan |

**图 2-9** 堆扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_82_0.png)

**图 2-10** 堆扫描（存储引擎）。

SQL Server 在我们的系统上报告此查询有 24,396 次逻辑读取。如果你发现物理操作和逻辑操作都显示 Table Scan 感到有点困惑，你并不孤单。对我来说，逻辑操作是表扫描，物理操作是堆扫描。

存储引擎唯一的选项是针对 IAM 页进行分配顺序扫描。回想“表”部分，分配顺序扫描是执行的。针对结构为 B 树的表的以下查询将需要扫描：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM Orders;
```

图 2-11 显示了优化器为此查询生成的计划。注意 `Clustered Index Scan` 算子的 `Ordered` 属性为 `False`。图 2-12 显示了存储引擎处理这种方法的插图。

**Clustered Index Scan [idx]**

Cost: 100 %

| Physical Operation | Clustered Index Scan |
|---|---|
| Logical Operation | Clustered Index Scan |
| Ordered | False |

**图 2-11** B 树扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_83_0.png)

**图 2-12** B 树扫描（存储引擎）。

SQL Server 报告此查询 25,073 次逻辑读取。同样，在这里发现两个属性都显示 Clustered Index Scan 有点困惑。这次逻辑操作是表扫描，物理操作是堆扫描。`Clustered Index Scan` 算子的 `Ordered` 属性为 `False` 意味着从关系顺序的角度来看，数据不需要按顺序返回。这为存储引擎留下了操作空间，可以在两种扫描类型之间选择：索引扫描（遵循链表的扫描）和分配顺序扫描（对 IAM 页的扫描）。存储引擎在选择使用哪种扫描类型时考虑的因素包括性能和数据一致性。我在描述有序扫描（`Ordered True` 的 `Clustered Index Scan` 和 `Index Scan`）后会提供更多细节。

无序非聚簇索引扫描与无序聚簇索引类似。覆盖索引的概念意味着非聚簇索引包含了查询指定的所有列。换句话说，覆盖索引并不是具有特殊属性的索引；而是对于特定查询而言是覆盖的。SQL Server 可以通过访问索引数据来获取查询所需的数据，而无需访问完整的数据行。除了这些，该访问方法与无序聚簇索引扫描相同，只是覆盖非聚簇索引的叶级包含页面更少，因为行大小更小，每页可以容纳更多行。

作为这种方法的示例，以下查询从 `Orders` 表所有的 `orderid` 值：

```sql
SELECT orderid
FROM Orders;
```

我们的表在 `orderid` 列上有一个非聚簇索引（`PK_Orders`），这意味着表的顺序 ID 位于索引的叶级。该索引覆盖了我们的查询。图 2-13 显示了你为该查询获得的图形化执行计划，图 2-14 说明了存储引擎处理它的两种方式。

| Physical Operation | Index Scan |
|---|---|
| Logical Operation | Index Scan |
| Ordered | False |

**图 2-13** 无序非聚簇索引扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_84_0.png)

**图 2-14** 无序非聚簇索引扫描（存储引擎）。

![](img/bdc38aa36f6e2987d913ee5381474711_85_0.png)

在我的系统上，SQL Server 对此查询报告了 2,611 次逻辑读取。这是构成 `PK_Orders` 索引层级的页面数。

给你出一个小谜题：在查询中添加 `orderdate` 列，如下所示：

```sql
SELECT orderid, orderdate
FROM dbo.Orders;
```

查看图 2-15 所示的该查询的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_85_1.png)

**图 2-15** 包含聚簇键的索引。

观察发现，对于此查询，`PK_Orders` 索引仍被覆盖索引。问题在于

## 有序聚集索引扫描

有序聚集索引扫描是对聚集索引叶子层的全扫描，它保证数据将按顺序返回给下一个算符。例如，下面的查询请求按 `orderdate` 排序的所有订单，它将在计划中获得这种访问方式：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
ORDER BY orderdate;
```

你可以在图 2-16 中找到该查询的执行计划，并在图 2-17 中看到存储引擎如何执行这种访问方式的插图。

![](img/bdc38aa36f6e2987d913ee5381474711_86_0.png)

**图 2-16** 有序聚集索引扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_86_1.png)

**图 2-17** 有序聚集索引扫描（存储引擎）。

在我的系统上，SQL Server 对此查询报告了 25,073 次逻辑读取。

注意计划中的 `Ordered` 属性 `True`。这表示数据需要按顺序从算符返回。当算符具有属性 `Ordered: True` 时，存储引擎可以通过一种方式执行扫描——使用索引顺序扫描（基于链接索引列表的扫描），如图 2-17 所示。与分配顺序扫描不同，索引顺序扫描的性能取决于索引的碎片程度。在没有任何碎片的情况下，索引顺序扫描的性能应该非常接近分配顺序扫描的性能，因为两者最终都将按文件顺序读取数据。在冷缓存情况下，随着碎片程度的增加，性能差异将显著——倾向于分配顺序扫描（或成本更低）。自然的推论是：如果你不对数据进行排序，就不会请求排序的数据，以便留出分配顺序扫描的可能性；并且，你应该在冷缓存下进行大规模索引顺序扫描的索引中解决碎片问题。我将详细阐述碎片及其处理层。

注意，优化器并不限于有序正向扫描。请记住链表是一个双向链表，每个页面都包含一个后继指针和一个前驱指针。如果你请求了降序排序，你仍然会获得有序索引扫描，只是反向的（从尾部到头部），而不是正向（从头部到尾部）。有趣的是，从 SQL Server 2014 开始，存储引擎将考虑在有序正向扫描中使用并行处理。而它串行处理有序反向扫描。

SQL Server 还支持降序索引。使用它的一个原因是，当并行是查询性能的重要因素时，启用并行扫描。另一个原因是支持多个排序要求方向相反的键列——例如，按 `col1, col2 DESC` 排序。我将在本章稍后的“索引功能”部分演示如何使用降序索引。

## 有序覆盖非聚集索引扫描

有序非聚集索引扫描与有序聚集索引扫描类似，前者在非聚集索引中执行访问方式——通常用于覆盖查询。其成本低于聚集索引扫描，因为涉及的页面较少。我们聚簇表上的 `PK_Orders` 索引覆盖了以下查询，并以所希望的顺序存储了数据：

```sql
SELECT orderid, orderid
FROM dbo.Orders
ORDER BY orderid;
```

图 2-18 显示了查询的执行计划，图 2-19 说明了存储引擎处理该访问方式的方式。

![](img/bdc38aa36f6e2987d913ee5381474711_87_0.png)

**图 2-18** 有序覆盖非聚集索引扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_88_0.png)

**图 2-19** 有序覆盖非聚集索引扫描（存储引擎）。

注意计划中索引扫描的 `Ordered` 属性显示为 `True`。

有序索引扫描不仅发生你显式请求排序数据时，也发生在计划使用可以从排序输入数据中受益的算符时。这可能发生在 `GROUP BY`、`DISTINCT`、连接（joins）和其他请求中。也可能发生在不明显的情况下。例如，查看图 2-18 所示的执行计划：

```sql
SELECT orderid, orderid
FROM dbo.Orders
ORDER BY orderid;
```

![](img/bdc38aa36f6e2987d913ee5381474711_87_0.png)

注意计划中索引扫描的 `Ordered` 属性显示为 `True`。

## 分配顺序扫描

图 2-21 通过三个步骤演示了分配顺序扫描如何返回行的多次出现。

### 分配顺序扫描：获取行的多次出现

**步骤 1：**

| 50 | 10 | 90 |
|---|---|---|
| 60 | 20 | 100 |
| 70 | 30 | 110 |
| 80 | 40 | 120 |

分配顺序扫描 ->

输出: 50, 60, 70, 80, 10, 20, 30, 40

**步骤 2：**

| 50 | 10 | 90 | 30 |
|---|---|---|---|
| 60 | 20 | 100 | 40 |
| 70 | | 110 | |
| 80 | 25 | 120 | |

分配顺序扫描 ->

插入 25

输出: 50, 60, 70, 80, 10, 20, 30, 40

**步骤 3：**

| 50 | 10 | 90 | 30 |
|---|---|---|---|
| 60 | 20 | 100 | 40 |
| 70 | | 110 | |
| 80 | 25 | 120 | |

分配顺序扫描 ->

输出: 50, 60, 70, 80, 10, 20, 30, 40, 90, 100, 110, 120, 30, 40

**图 2-21** 分配顺序扫描：获取行的多次出现。

步骤 1 显示了正在进行的分配顺序扫描，按照文件顺序（而非索引顺序）读取某些索引的叶页。已经读取了两个页（键 50, 60, 70, 80, 10, 20, 30, 40）。此时，在读取索引的第三个页之前，有人向表中插入了一个键为 25 的行。

步骤 2 显示了目标插入页发生了分裂，因为该页已满了。分裂的结果是分配了一个新页——在我们的案例中，它位于文件的后部，是扫描尚未到达的位置。原页的一半行移动到新页（键 30, 20），而键为 25 的新行由于其键值被添加到原页。

步骤 3 显示了扫描的继续：读取剩余的两个页（键 90, 100, 110, 120, 30, 40），包括由于分裂而添加的那个。注意，键为 30 和 40 的行被再次读取了。

当然，类似地，取决于分裂发生时扫描到达了多远以及新页分配的位置，扫描最终可能会跳过某些行。图 2-22 通过三个步骤演示了这种情况是如何发生的。

### 分配顺序扫描：跳过行

![](img/bdc38aa36f6e2987d913ee5381474711_91_0.png)



![](img/bdc38aa36f6e2987d913ee5381474711_91_1.png)

![](img/bdc38aa36f6e2987d913ee5381474711_91_2.png)

图 2-22 分配顺序扫描：跳过行。

步骤 1 显示了正在进行的分配顺序扫描，它在插入发生之前成功读取了一个页（键 50, 60, 70, 80）。

步骤 2 显示了目标页的分裂，但这次新页分配在文件的较前位置，即扫描已经经过的位置。与之前的分裂示例类似，键为 30 和 40 的行移动到新页，键为 25 的新行被添加到原页。

步骤 3 显示了扫描的继续：读取剩余的两个页（键 10, 20, 25, 90, 100, 110, 120）。如你所见，键为 30 和 40 的行被完全跳过了。

简而言之，分配顺序扫描可能会返回行的多次出现，或跳过扫描期间发生分裂的行。分裂的发生可能是因为插入新行、更新索引键导致行移动，或者更新变长列导致行扩展。记住，分裂只发生在索引中；堆（`heap`）不会发生分裂。因此，这种现象不会发生在堆中。

索引顺序扫描更安全，因为它不会读取同一行的多次出现，也不会因为分裂而跳过行。记住，索引顺序扫描按顺序遵循索引链表。如果一个页尚未发生分裂，扫描将读取两个页；因此，它不会跳过行。如果扫描已经过了分裂，扫描将读取新页；因此，它不会返回行的多次出现。

存储引擎非常清楚分配顺序扫描容易产生分裂引起这种不一致结果，而索引扫描则不会。它将在我称为**不安全（`unsafe`）**和**安全（`safe`）**的情况中，使用分配顺序扫描执行 `Ordered: False` 的索引扫描。不安全类别是扫描实际上可能因为分裂返回行的多次出现或跳过行。当索引大小大于 64 页且查询在 `Read Uncommitted`（读取未提交）隔离级别下运行时（例如指定 `NOLOCK`）时，存储引擎会选择这种。大多数人对 `Read Uncommitted` 的感知仅仅是查询不请求共享锁并可以读取未提交的脏读。这种感知是正确的，但遗憾的是，大多数人没有意识到对于存储引擎来说，`Read Uncommitted` 也意味着一致性方面有很多限制。换句话说，它将以返回行的多次出现或跳过行为代价选择更快的选项。当查询在默认的 `Committed`（已提交）或更高的隔离级别运行时，存储引擎将选择索引扫描以防止此类分裂现象的发生。总结，当满足以下所有条件时，存储引擎会使用不安全类别的顺序扫描：

- 索引大小大于 64 页。
- 计划显示 `Index Scan, Ordered: False`。
- 查询在 `Read Uncommitted` 隔离级别下运行。
- 允许对数据进行更改。

在安全类别方面，当存储引擎知道在不牺牲读取一致性（至少在分裂方面）的情况下是安全的，也会使用比 `Read Uncommitted` 更高隔离级别的分配顺序扫描。例如，当你使用 `TABLOCK` 运行查询时，存储引擎知道在读取期间没有人可以更改数据。因此，使用分配顺序扫描是安全的。另一个存储引擎知道安全采用分配顺序扫描的例子是索引位于只读文件组或数据库。总之，当索引大小和数据是只读的（由于 `TABLOCK` 提示、只读文件组或数据库），存储引擎将使用安全类别的分配顺序扫描。请记住，逻辑碎片会影响索引顺序扫描的性能，但不会影响分配顺序扫描。根据前面的信息，你应该意识到存储引擎将使用索引扫描来处理具有 `Ordered: False` 属性的 `Index Scan` 运算符。

下一节将演示不安全和安全的分配顺序扫描。

```sql
SET NOCOUNT ON;
USE tempdb;
GO

-- 创建表 T1
IF OBJECT_ID(N'dbo.T1', N'U') IS NOT NULL DROP TABLE dbo.T1;

CREATE TABLE dbo.T1
(
  clcl UNIQUEIDENTIFIER NOT NULL DEFAULT(NEWID()),
  filler CHAR(2000) NOT NULL DEFAULT('a')
);
GO
CREATE UNIQUE CLUSTERED INDEX idx_clcl ON dbo.T1(clcl);
```

在 `clcl` 上创建了一个唯一索引，它将由默认表达式 `NEWID()` 填充。使用随机 GUID 填充索引键应该会导致大量分裂，这又会导致索引出现高度的逻辑碎片。运行以下代码使用无限循环插入行，并在几秒后停止（例如 5 秒，以便表超过 64 页）：

```sql
SET NOCOUNT ON;
USE tempdb;

TRUNCATE TABLE dbo.T1;

WHILE 1 = 1
INSERT INTO dbo.T1 DEFAULT VALUES;
```

运行以下代码检查索引的碎片程度：

```sql
SELECT avg_fragmentation_in_percent FROM sys.dm_db_index_physical_stats(
  DB_ID(N'tempdb'),
  OBJECT_ID(N'dbo.T1'),
  1,
  NULL,
  NULL
);
```

```sql
SELECT PrevLevel.RowNum + 1,
  CurLevel.PageID, CurLevel.PagePID
FROM LinkedList AS PrevLevel
JOIN #DBCCIND AS CurLevel
ON CurLevel.PrevPageID = PrevLevel.PageID
AND CurLevel.PrevPageID = PrevLevel.PagePID
```

```sql
SELECT
  CAST(PageID AS VARCHAR(MAX)) + ':'
  + CAST(PageID AS VARCHAR(MAX)) + '' AS [text]
FROM LinkedList
ORDER BY RowNum
FOR XML PATH('')
OPTION (MAXRECURSION 0);
```

```sql
DROP TABLE #DBCCIND;
```

该代码将 `DBCC IND` 的输出存储在临时表中，然后使用递归查询从头到尾跟踪链表，最后使用基于 `FOR XML path` 选项的技术将叶页按照链表顺序合并成单个字符串。我在我的系统上得到了以下输出：

`1132098 1111372 1133098 1125591 1137567 1118198 1128938 1117929 1136036 1128595...`

在这里很容易观察到逻辑碎片，例如，页面 132098 指向页面 1111372，而后者在文件中位置靠前。

接下来，运行以下代码查询 T1：

```sql
SELECT SUBSTRING(CAST(clcol AS BINARY(16)), 11, 6) AS segment1
FROM dbo.t1;
```

`UNIQUEIDENT` 的最后 6 个字节是决定顺序的第一个段——因此，我使用 `SUBSTRING` 函数进行提取，以便于查看行是否按索引顺序返回的。此查询的执行计划显示为聚集索引扫描（`Clustered Index Scan`），排序为否（`Ordered False`）。然而，由于环境是只读的，且索引级别为默认读取（`Default Read`），存储引擎使用了索引扫描。此查询按索引顺序返回行。例如，这是我在我的上得到的输出：

| segment1 | clcol | filler |
| :--- | :--- | :--- |
| 00000E83A06E | 5F57CA42-78B6-4176-8BDC-000ED83A06E | |
| 00002627271D | 7B3D64F2-9197-487E-0002677271D | |
| 0002EE4AF130 | 7D4A671D-5BFD-4837-831C-0002E4AF1430 | |
| 000019E53048 | 2A70C6C3-5459-40CE-90A5-0039E30408 | |
| 000048B904D2 | 40C8B1A2-48C7-4095-A5F4B48B90D2 | |
| 00005E12D3C0 | FEF7B3A2-440F-918B-0005E12D3C0 | |
| 000607D63997 | B49C5301-E1E7-4745-B50007D63997 | |
| 0007B8D20817 | 1157F2E9-A27E-4795-B007B8D20817 | |
| 0007B0C102C0 | 9D3E4A5C-3AAD-4868-B4A1-0007B0C102C0 | |
| 00007E73BEF8 | 73207EF8-A267-47A3-B22CF-0007E73BEF8 | |

再次使用 `NOLOCK` 提示查询该表：

```sql
SELECT SUBSTRING(CAST(clcol AS BINARY(16)), 11, 6) AS segment1, *
FROM dbo.T1 WITH (NOLOCK);
```

这一次，存储引擎对该不安全查询采用了分配顺序扫描（`allocation order scan`）。这是我在我的上运行该代码得到的输出：

| segment1 | clcol | filler |
| :--- | :--- | :--- |
| 0x0D35CA4F3BAE | 7E21A82E-8712-47F1-A553-0D35CA4F3BAE | A |
| 0x426DF0DBD03 | 003FE4B-18E0-4A8D-861-C26DADFDB03 | |
| 0x42D6A3FF2C | 9239BF31-94AE-47F0-8B50-4260DA6AFF2C | |
| 0x42AE5E6967AD | 2FA0A9A-2A7E-42C0-A22E-42ES69C73AD | |
| 0x5EEBC29A844 | 374327C-07C2-48BC-A6B5-5EEBC29A844 | |
| 0x97A5286AE1D | 131BDF97-B0F1-488-97A5286AE1D | |
| 0x78D967590DC | 7AA0F5BF-0DB1-4689-B851-78D67590DC | |
| 0x78BA1713227 | 7AF0C88F-FC08-4534-B42C-78BA1713227 | |
| 0x78DACE8A159E | 90EBE771-301F-4A6B-A938-78DACE8A159E | |
| 0x20CC225A810D | 54BD309-7804-4969-8A7F-20CC225A810D | |

注意行并不是按索引顺序返回的。如果正在进行此类读取，可能会返回多次行。作为不安全查询分配顺序扫描的示例，带上 `TABLOCK` 运行查询：

```sql
SELECT SUBSTRING(CAST(clcol AS BINARY(16)), 11, 6) AS segment1
FROM dbo.T1 WITH (TABLOCK);
```

在这里，尽管代码在提交（`Committed`）隔离级别下运行，存储引擎认为使用分配顺序扫描是安全的，因为没有人更改数据。我从此查询中得到了以下输出：

| segment1 | clcol | filler |
| :--- | :--- | :--- |
| 0x0D35CA4F3BAE | 7E21A82E-8712-47F1-A553-0D35CA4F3BAE | A |
| 0x426DF0DBD03 | 003FE4B-18E0-4A8D-861-C26DADFDB03 | |
| 0x42D6A3FF2C | 9239BF31-94AE-47F0-8B50-4260DA6AFF2C | |
| 0x42AE5E6963AD | 2FA0A9A-2A7E-42C0-A22E-42ES69C73AD | |
| 0x5EEBC29A844 | 374327C-07C2-48BC-A6B5-5EEBC29A844 | |
| 0x97A5286AE1D | 131BDF97-B0F1-488-97A5286AE1D | |
| 0x78D967590DC | 7AA0F5BF-0DB1-4689-B851-78D67590DC | |
| 0x78BA1713227 | 7AF0C88F-FC08-4534-B42C-78BA1713227 | |
| 0x78DACE8A159E | 90EBE771-301F-4A6B-A938-78DACE8A159E | |
| 0x20CC225A810D | 54BD309-7804-4969-8A7F-20CC225A810D | |

## 第 2 章：查询调优

接下来我将演示不安全的分配顺序扫描如何返回多次行。打开两个连接（称为连接 1 和连接 2）。在连接 1 中运行以下代码，无限循环地向 T1 插入行，导致频繁的分页：

```sql
SET NOCOUNT ON;
USE tempdb;

TRUNCATE TABLE dbo.T1;

WHILE 1 = 1
INSERT INTO dbo.T1 DEFAULT VALUES;
```

在连接 2 中运行以下代码，在连接 1 插入数据的同时循环读取数据：

```sql
SET NOCOUNT ON;
USE tempdb;

WHILE 1 = 1
BEGIN
    SELECT * INTO #T1 FROM dbo.T1 WITH (NOLOCK)

    IF EXISTS(
        SELECT clcol
        FROM #T1
        GROUP BY clcol
        HAVING COUNT(*) > 1) BREAK;

    DROP TABLE #T1;
END

SELECT clcol, COUNT(*) AS cnt
FROM #T1
GROUP BY clcol
HAVING COUNT(*) > 1;

DROP TABLE #T1;
```

这段代码运行一个无限循环，在每次迭代中通过 `NOLOCK` 读取数据并存入临时表，一旦在 `seqval` 列中发现存在间隔的连续值，就会跳出循环。随后代码会显示具有间隔的连续值对。几秒钟后，我在连接 2 中得到了以下输出（缩略形式）：

| cur | nxt |
| :--- | :--- |
| 8128 | 8130 |
| 12378 | 12380 |
| 13502 | 13504 |
| 17901 | 17903 |
| 25257 | 25259 |
| 27515 | 27517 |
| 29784 | 29784 |
| 32764 | 32766 |
| 32945 | 32947 |



你可以停止连接 1 中的代码。你可以在不带 `NOLOCK` 提示的情况下再次运行测试，在这种情况下存储引擎将使用索引顺序扫描。连接 2 中的代码不应跳出循环，因为没有发现间隔。

## 索引顺序扫描

如果你认为索引顺序扫描可以防止诸如返回行的多次出现或跳过行等现象，请重新考虑。索引顺序扫描确实对页分裂是安全的，但页分裂并不是数据在叶节点中移动的唯一原因。叶节点中移动的另一个原因是索引键的更新。如果索引键在索引顺序扫描读取行后被修改，并且该行移动到了扫描尚未到达的叶节点位置，则扫描将第二次读取该行。同样，如果索引键在索引顺序扫描读取行之前被修改，且该行移动到了扫描已经过的叶节点位置，扫描将永远无法到达该行。例如，假设你有一个 `Employees` 表，目前有四行（员工 A 薪水 2000，员工 B 薪水 4000，员工 C 薪水 3000，员工 D 薪水 1000）。在 `salary` 列上定义了一个聚集索引作为键。图 2-23 通过三个步骤展示了索引顺序扫描如何由于读取期间发生的更新而返回同一行的多次出现。

### 步骤 1
![步骤 1](img/bdc38aa0f6e2987d913ee538147471101_0.png)
输出: D 1000, A 2000, C 3000

### 步骤 2
![步骤 2](img/bdc38aa0f6e2987d913ee538147471101_1.png)
输出: D 1000, A 2000, C 3000

### 步骤 3
![步骤 3](img/bdc38aa0f6e2987d913ee538147471101_2.png)
输出: D 1000, A 2000, C 3000, B 4000, D 5000

**图 2-23** 索引顺序扫描：获取行的多次出现。

你对表执行了一个查询，存储引擎使用了索引顺序扫描。请记住，当计划显示 `Index Scan: True` 时（例如当查询带有 `ORDER BY` 子句时），总是使用索引顺序扫描；但当 `Ordered` 属性为 `False`、环境为读/写且隔离级别不是 `Uncommitted` 时，它也会这样做。

步骤 1 显示扫描已经读取了叶层级中的第一页，并返回了员工 D、A 和 C 的行。如果查询在 `Read Committed` 级别下运行，则会在行上获取共享锁。如果查询在 `Read Committed` 级别下运行（例如某行或某页），即使查询尚未完成，锁也会被释放。这意味着在扫描完成该页的时间点，两种隔离级别对已读取的行都没有锁。

步骤 2 显示了对员工 D 的行的更新，将薪水从 1000 增加到 5000。由于索引键的原因，该行移动到了叶层中的第二页。

步骤 3 显示扫描的继续，读取索引叶层中的第二页，并返回了员工 B 和 D 的行。注意，员工 D 被返回了第二次。第一次返回时行薪水为 1000，第二次返回时薪水为 5000。注意，这种现象不会在比 `Read Committed` 更高的隔离级别下发生，因为这些级别会一直保持共享锁直到事务结束。这种现象也不会发生于基于行版本的两个隔离级别之间：`Read Committed Snapshot` 和 `Snapshot`。

同样，索引顺序扫描可能会跳过行。图 2-24 显示了这如何通过三个步骤发生。

这次员工 D 的起始薪水为 5000，其行位于第二个索引页。步骤 1 显示扫描已经读取了叶层级中的第一页，并返回了员工 A 和 C 的行。

步骤 2 显示了对员工 D 的行的更新，将薪水从 5000 减少到 1000。由于索引键的原因，该行移动到了叶层中的第一页。

步骤 3 显示扫描的继续，读取索引叶层中的第二页，返回了员工 B 的行。注意员工 D 的行完全没有返回——无论是薪水 5000 还是 1000。这种现象可以在 `Read Uncommitted`、`Read Committed` 和 `Repeatable Read` 下发生，因为更新是对一个未被读取的行进行的。这种现象在 `Serializable`、`Read Committed` 和 `Snapshot` 下不会发生。

### 步骤 1
![步骤 1](img/bdc38aa0f6e2987d913ee538147471103_0.png)
输出: A 2000, C 3000

### 步骤 2
![步骤 2](img/bdc38aa0f6e2987d913ee538147471103_1.png)
输出: A 2000, C 3000

### 步骤 3
![步骤 3](img/bdc38aa0f6e2987d913ee538147471103_2.png)
输出: A 2000, C 3000, B 4000

**图 2-24** 索引顺序扫描：跳过行。

为了亲眼观察这两个现象，你可以运行一个简单的测试。首先，执行以下代码填充 `Employees` 表：

```sql
SET NOCOUNT ON;

USE tempdb;

IF OBJECT_ID('dbo.Employees') IS NOT NULL DROP dbo.Employees;

CREATE TABLE dbo.Employees
(
  empid VARCHAR(10) NOT NULL,
  salary MONEY NOT NULL,
  filler CHAR(1) NOT NULL DEFAULT('a')
);

CREATE CLUSTERED INDEX Idx_c1_salary ON dbo.Employees(salary);

ALTER TABLE dbo.Employees
CONSTRAINT PK_Employees PRIMARY KEY (empid);

INSERT INTO dbo.Employees(empid, salary) VALUES
('D', 1000.00),
('A', 2000.00),
('C', 3000.00),
('B', 4000.00);
```

打开两个连接。在连接 1 中运行以下代码，循环将员工 D 的薪水从当前值更新为 6000（在 1000 和 5000 之间切换）：

```sql
SET NOCOUNT ON;

USE tempdb;

WHILE 1=1
UPDATE dbo.Employees
  salary = 6000.00
WHERE empid = 'D';
```

在连接 2 中运行以下代码，该无限循环将 `Employees` 表的内容存入临时表：

```sql
SET NOCOUNT ON;

USE tempdb;

WHILE 1 = 1
BEGIN
  SELECT * INTO #Employees FROM dbo.Employees;
  IF @@rowcount <> 4 BREAK; -- 使用 4 表示跳过，> 4 表示多次
  DROP TABLE #Employees;
END

SELECT * FROM #Employees;

DROP TABLE #Employees;
```

由于代码没有指定 `NOLOCK` 提示且环境为读/写，存储引擎使用了索引顺序扫描。当行数不等于预期值（四）时，代码中断循环。在扫描两次读取同一行的情况下，此代码返回五行输出：

| empid | salary | filler |
|---|---|---|
| D | 1000.00 | a |
| A | 2000.00 | a |
| C | 3000.00 | a |
| B | 4000.00 | a |
| D | 5000.00 | a |

在扫描跳过行的情况下，此代码返回三行输出：

| empid | salary | filler |
|---|---|---|
| A | 2000.00 | a |
| C | 3000.00 | a |
| B | 4000.00 | a |

你可以将过滤器更改为 `< 4` 以等待行被跳过的情况，更改为 `> 4` 以等待行被读取两次的情况。

希望这能让你更好地理解存储引擎如何处理扫描，最重要的是在 `Read Uncommitted` 隔离级别下运行代码的影响。后续章节将继续介绍访问方法。

## 非聚集索引查找 + 范围扫描 + 查找

访问方法“非聚集索引查找 + 范围扫描 + 查找”通常用于小范围查询（使用点查询），且使用了未覆盖查询的索引。例如，假设你想查询订单 ID 落在小订单 ID 范围内的订单，例如 `orderid <= 25`。对于符合条件的订单，你想返回 `orderid`、`custid`、`empid`、`shipperid`、`orderdate` 和 `filler` 列。我们有一个名为 `PK_Orders` 的非聚集索引，定义以 `orderid` 列作为键。该索引可以支持过滤；但由于索引没有覆盖查询，将需要查找从相应的数据行中获取剩余列。如果表是堆（heap），查找将是 RID 查找（RID lookups），每次代价为一次读取。如果底层表是 B 树，查找将是键查找（key lookups），每次代价等同于聚集索引的层数。

为了在堆上演示这种访问方法，我将使用以下查询：

```sql
USE PerformanceV3;

SELECT orderid, custid, empid, shipper, orderdate, filler
FROM dbo.Orders2
WHERE orderid <= 25;
```

图 2-25 显示了查询的执行计划，图 2-26 说明了存储引擎处理访问的方法。

在页面右上角，针对 `PK_Orders2` 索引的索引查找（Index Seek）在索引中执行查找到第一行匹配行，然后执行范围扫描以识别所有符合条件的行（在我们的案例中为 25 行）。此活动的目的是收集目标数据行的行定位符（在堆表情况下为 RID）。寻查找的成本是三行。范围扫描的成本取决于符合条件的行数以及每页可以容纳多少行。该索引每页可以固定容纳到近 400 行。因此，在我们的案例中，这 25 行符合条件的行可能存在于寻查找操作到达的叶节点的第一页中。很可能不需要为范围扫描进行额外的页读取。

访问方法的第三部分是对返回的行定位符执行查找（lookups），以从各自的数据行中收集剩余的列。查找是由 `Index Seek` 算子返回的每一行触发的嵌套循环（Nested Loops）操作激活的。由于此示例涉及堆（heap），查找是 RID 查找，每次花费一次页读取。对于 25 行符合条件的行，查找的总成本为 25。这正是 SQL Server 在我的系统上对该查询执行的读取次数。

![图 2-25](img/bdc38aa36f6e2987d913ee5381474711_106_0.png)

**图 2-25** 非聚集索引寻查找 + 范围扫描 + 针对堆的查找（执行计划）。

![图 2-26](img/bdc38aa36f6e2987d913ee5381474711_107_0.png)

**图 2-26** 非聚集索引寻查找 + 范围扫描 + 针对堆的查找（存储引擎）。

为了演示针对 B 树的访问方法，我将使用以下查询：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 25;
```

图 2-27 显示了查询的执行计划，图 2-28 说明了存储引擎处理访问的方法。

这种访问方法与之前方法的关键区别在于，它不是应用 RID 查找，而是应用了键查找（key lookups）。记住，键查找等同于在聚集索引中的查找（seek），其读取次数等于聚集索引的层数（在我们的案例中为 3 层）。因此，我们的查询执行的总读取次数为 3 + 0 + 25 * 3 = 78。这正是 SQL Server 在我的系统上对该查询报告的读取次数。

| 指标 | 值 |
|---|---|
| 实际行数 | 25 |
| 估计行数 | 25 |

| 算子 | 详情 |
|---|---|
| **SELECT** | Cost: 0 % |
| **Nested Loops (Inner Join)** | Cost: 0 % |
| **Index Seek (NonClustered) [Orders].[PK_Orders]** | Cost: 4 %<br>Output List: Uniq100:[PerformanceV3].dbo.orderid, [PerformanceV3].dbo.[Orders].orderdate<br>Seek Predicates: Seek Keys[1]: End: [PerformanceV3], [Orders].orderid <= ScalarOperator(25) |
| **Key Lookup (Clustered) [Orders].[idx_c1_od]** | Cost: 96 %<br>执行次数: 25<br>估计执行次数: 25<br>估计行数: 1<br>输出列表: [PerformanceV3].dbo.[Orders2].custid, [PerformanceV3].dbo.[Orders2].empid, [PerformanceV3].dbo.[Orders2].shipperid, [PerformanceV3].dbo.[Orders2].orderate, [PerformanceV3].dbo.[Orders2].filler<br>Seek Predicates: Seek Keys[1]: Prefix: [PerformanceV3].dbo, [Orders].orderid, Uniq101 = Scalar Operator [PerformanceV3].dbo.[Orders].[orderdate]), Scalai Operator(Uniq1001) |

**图 2-27** 非聚集索引寻查找 + 范围扫描 + 针对 B 树的查找（执行计划）。

既然已经涵盖了这种访问方法的方面，我们可以转向更有趣的话题，例如基数估计（cardinality estimates）、预取（prefetch）和转折点（tipping points）。

在优化像我们示例中这样的查询时，优化器需要做出许多选择，这些选择取决于过滤器的估计基数（返回的行估计数）。在描述此处要做的具体选择之前，我将首先描述用于此查询的基数估计方法。通常，进行基数估计是一项棘手的工作，我将在本章稍后的“基数估计”部分详细阐述。不过，我们的特定案例非常直接。

![图 2-28](img/bdc38aa36f6e2987d913ee5381474711_109_0.png)

**图 2-28** 非聚集索引寻查找 + 范围扫描 + 针对 B 树的查找（存储引擎）。

当你创建索引时，SQL Server 还会创建关于索引中数据的统计信息。统计信息包含一个带有通用信息的头、关于索引中前导键列向量的密度信息以及索引中前导键列的直方图。直方图表示列中键值的分布。运行以下代码以显示 SQL Server 基于 `orderid` 列为 `Orders` 表上的 `PK_Orders` 索引创建的直方图：

```sql
DBCC SHOW_STATISTICS ('dbo.Orders', 'PK_Orders') WITH HISTOGRAM;
```

该代码在我的系统上生成了以下输出：

| RANGE_HI_KEY | RANGE_ROWS | EQ_ROWS | DISTINCT_RANGE_ROWS | AVG_RANGE_ROWS |
|---|---|---|---|---|
| 1 | 0 | 1 | 0 | 1 |
| 1000000 | 999999 | 1 | 999998 | 1 |

SQL Server 支持多达 200 步的直方图。在我们的案例中，由于表具有 1 到 1,000,000 连续顺序 ID 范围，SQL Server 认为两个步骤就能充分表示这种数据分布。每个步骤表示大于的。

如前所述，如果匹配百分比低于上述临界点，优化器将选择全聚集索引（或堆表）。但此时优化器需要做的另一个选择是采用并行计划还是串行计划。与直觉认为“并行化总能提高扫描性能”相反，串行扫描有时比并行扫描更高效。扫描本身可以由预读机制高效处理。并行化能够获益的是处理过滤器，这是一项需要 CPU 周期的操作。线程越多，带过滤器的扫描就越快。问题在于，如果并行扫描为不同的线程提供行数据，且每个线程都应用过滤器，那么并行化（聚集流，Gather Streams）算符就需要收集来自不同线程返回的符合条件的行。每一行需要收集的行都有固定的成本。过滤后剩余的行越多，Gather Streams 操作就越贵。如果带过滤并行扫描与 Gather Streams 操作的成本之和低于串行扫描的成本，优化器将选择前者；否则将选择后者。

让我说得具体些。为了反映更多线程允许带过滤的扫描更快完成的事实，优化器通过并行度成本计算（call DOPCosting），将并行扫描的 CPU 成本（call CPUParallel）对比于串行扫描的 CPU 成本（call CPUSerial）。你可以通过执行一个不带过滤器的查询并查看串行扫描的属性来获取串行扫描的 CPU 成本。我得到的 CPU 成本是 1。DOPCosting 的计算方式为并行度 DOPForExecution 除以 2。DOPForExecution 是执行计划的一个属性；它代表 SQL Server 用于处理并行计划的最大线程数，它主要基于可用的逻辑 CPU 数量。例如，在我的系统中，我有 8 个逻辑 CPU，在并行计划中通常会获得 8 的并行度。因此，在我的情况下，DOPCosting 是 8 / 2 = 4。所以，CPUParallel 为 1 / 4。Gather 操作涉及一些启动成本（call GatherStreamsStartup）以及每行的额外成本（call GatherStreamsRow）。串行扫描计划的 CPU 部分是 CPUSerial。该计划的成本不受行数影响。并行扫描计划的 CPU 部分是 CPUSerial / (DOPForExecution / 2) + GatherStreamsStartup + GatherStreamsRow。

DOPForExecution 越大，在并行计划的成本高于串行计划成本之前，你就能过滤越多的行。在我的 DOPForExecution 为 8 的系统中，并行计划与串行计划之间的临界点位于 272,000 行到 273,000 行之间。例如，以下查询在我的系统中获取了并行计划：



```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 10000;
```

该查询的执行计划如图 2-29 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_113_0.png)

**图 2-29** 带有扫描的并行查询计划。

对于 272,000 行，我仍然得到了并行计划。对于 273,000 行及更多时，我得到了串行计划。例如，以下查询在我的系统中获得了串行计划：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 300000;
```

该查询的执行计划如图 2-30 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_113_1.png)

**图 2-30** 带有扫描的串行查询计划。

由于并行计划的成本公式取决于你系统中的逻辑 CPU 数量，因此在 CPU 数量与生产系统不同的测试系统上排查查询可能会很困难。你可以使用一些工具让优化器假设一个与实际不同的 CPU 数量，但遗憾的是，这些工具是未记录且不支持的，其行为被认为是不可预测的。我严格将它们用于实验和研究。我觉得这些工具帮助我更好地理解 SQL Server 引擎的工作原理，我建议你不要在生产系统的任何地方中使用它们。

一个工具是 `DBCC OPTIMIZER_WHATIF`。该工具让优化器假设当前会话为了成本计算而具有某些可用资源。要假设 CPU 数量，将 `CPUs` 指定为第一个参数，将数量指定为第二个参数。例如，要假设有 16 个 CPU，运行以下代码：

```sql
DBCC OPTIMIZER_WHATIF(CPUs, 16);
```

检查以下查询的计划，它过滤了 300,000 行：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 300000
OPTION(RECOMPILE);
```

这一次，我得到了并行计划。那是因为 `CPUParallel` 比之前低了，允许在达到并行计划与串行计划之间的临界点之前过滤更多的行。

请注意，这种效果仅影响用于成本计算的 CPU 数量；因此，`DOPForCost` 将计算为该数字除以 2，并采用整数除法。执行的实际并行度仍基于系统中的逻辑 CPU 数量。更准确地说，它将基于 SQL Server 创建的调度器数量；通常 SQL Server 为每个逻辑 CPU 创建一个调度器。

要恢复系统的默认 CPU 数量，将第二个参数指定为 0，如下：

```sql
DBCC OPTIMIZER_WHATIF(CPUs, 0);
```

`DBCC OPTIMIZER_WHATIF` 命令对会话有局部影响。有一个工具对整个系统产生全局影响，但它是未记录且不支持的。如所述，通常 SQL Server 为系统中的每个逻辑 CPU 创建一个调度器，调度器的数量决定了 `DOPForExecution`。最后，第三个影响并行化的未记录且不支持的工具是查询标记 8649。这里有一个使用此跟踪的示例，查看使用并行计划的影响：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 30000
OPTION(QUERYTRACE 8649);
```

记住，在有 8 个逻辑 CPU 的情况下，优化器通常会选择串行计划。但通过此跟踪，优化器选择了并行计划。

### 无序非聚集索引扫描 + 查找

当满足以下条件时，优化器通常使用**无序非聚集索引扫描 + 查找**（unordered nonclustered index scan + lookups）访问方法：

- 查询具有选择性过滤器。
- 存在一个包含过滤列（或列）的非聚集索引，但该索引不是覆盖索引。
- 过滤列不是索引列表中的引导列。

例如，以下查询的计划使用了在键列 `(shipperid, orderdate, custid)` 上创建的访问方法 `idx_nc_sid_od_cid`：

```sql
SELECT orderid, custid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid = 'C000000001';
```

该索引的重要点是，`custid` 列出现在索引叶行中，但不是第一个键。

图 2-31 显示了查询的执行计划，图 2-32 说明了存储引擎如何处理访问方法：

```text
Query 1: Query cost (relative to the batch): 100%
SELECT [orderid],[custid],[empid],[shipperid],[orderdate],[filler] FROM
Missing Index (Impact 99.9012): CREATE NONCLUSTERED INDEX (<Name of Miss
```

```sql
CREATE NONCLUSTERED INDEX ([<Name of Missing Index, sysname>])
ON [dbo]([custid])
INCLUDE ([orderid],[empid],[shipperid],[orderdate],[filler])
```

| 实际行数 | 46 |
|------|---|
| 估计行数 | 742683 |

![](img/bdc38aa36f6e2987d913ee5381474711_115_0.png)

![](img/bdc38aa36f6e2987d913ee5381474711_116_0.png)

**图 2-32** 无序非聚集索引扫描 + 查找（存储引擎）。

在我的系统上，SQL Server 对此查询执行了 4,006 次逻辑读取。

当然，你可以通过创建一个以 `custid` 为前导键列的覆盖索引来获得更高效的计划。不出所料，优化器意识到了这一点并报告了这样一个缺失的索引，如图 2-31 所示。有了这样的索引，你可能总共只需要三或四次读取就能得到所需的结果。然而，也许该查询的频率很低，你宁愿在运行时支付更多费用，也不愿增加创建另一个索引带来的成本。此外，你可能不被允许在目标系统中创建新索引。

**无序非聚集索引扫描 + 查找**访问方法会对索引的叶节点级进行全无序扫描，然后对符合条件的键进行查找。正如我提到的，查询必须选择足够的内容来支撑这种访问方式；否则，由于过多的查找，它将比简单扫描整个表更昂贵。为了确定过滤器的基数，SQL Server 需要对过滤列拥有直方图。通常，当你创建索引时，SQL Server 会创建包含前导键列直方图的统计信息。但在我们的示例中，优化器需要索引中前导键的直方图。如果此类统计信息不存在，SQL Server 会创建它们，前提数据库属性 `AUTO_CREATE_STATISTICS` 是开启的（默认是开启的）。

所以当你第一次运行此查询时，SQL Server 在 `custid` 列上查找分布统计信息并发现不存在。SQL Server 接着检查了 `AUTO_CREATE_STATISTICS` 数据库选项并发现它是开启的。随后，SQL Server 在对列值进行采样后触发了基于 `custid` 列的统计信息的自动创建。优化器随后根据直方图对过滤器进行了基数估计，你可以在查询计划 74.2683 中看到这一点。这与实际匹配数（46 个）并不远。由于过滤器的选择性，使用这种访问方法的优化器比全表扫描更高效。索引叶节点级的扫描花费了 3,868 次读取。46 个键的查找花费了 138 次读取。这就是为什么查询总共执行了 4,006 次读取。在章节后面的部分，我将在“基数估计”部分详细阐述优化器使用的基数估计方法。

### 聚集索引查找 + 范围扫描

正如我解释过的，非聚集索引查找 + 范围扫描 + 查找是非常昂贵的。因此，当你有一个非聚集覆盖索引时，优化器通常会结合查找，仅处理极小比例的符合条件的行。我解释过，这是一个转折点，超过该点后，优化器倾向于对表进行全扫描。如果你有一个过滤器倾向于产生大量匹配项，且获得良好的性能对你来说很重要，那么你的重点应该放在消除对昂贵查找的需求。这可以通过安排覆盖索引来实现——即在叶节点行中包含查询所引的所有列。获取覆盖索引有两种主要方法：一种是使用聚集索引，另一种是使用包含列（included columns）的非聚集索引。本节侧重于前者，下一节重点关注后者。

聚集索引显然是一个覆盖索引，因为叶节点行就是数据行。对于基于聚集索引的第一键（或列）进行过滤的查询，优化器通常使用聚集查找 + 范围扫描方法。这种访问方法在叶节点级执行到第一个符合条件的行的查找操作，然后应用范围扫描直到最后一个符合条件的行。由于避免了昂贵的查找，这种访问方法始终比替代的全表扫描更高效。这使得基于此方法的计划成为一个“微不足道的计划”（trivial plan），意味着无论匹配行数有多少，该查询都只有一个优化计划。

以下查询查找在给定 `orderdate`（聚集索引键）上放置的所有订单，是讨论的重点：

```sql
SELECT orderid, custid, empid, shipperid, orderdate
FROM dbo.Orders
WHERE orderdate = '20140212';
```

图 2-33 显示了查询的执行计划，图 2-34 说明了存储引擎处理访问方法的方式。

![](img/bdc38aa36f6e2987d913ee5381474711_118_0.png)

**图 2-33** 聚集索引查找 + 范围扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_118_1.png)

**图 2-34** 聚集索引查找 + 范围扫描（存储引擎）。

过滤器使用了等号运算符，但由于 `orderdate` 列不是唯一的，过滤器可能有多个匹配行。在我的情况下，我得到了 703 行匹配。SQL Server 报告此查询在我处执行了 22 次逻辑读取。自然地，如果你使用 `>=`、`<=`、`<` 和 `BETWEEN` 运算符，你会得到类似的访问方法。

### 覆盖非聚集索引查找 + 范围扫描

非聚集索引查找 + 范围扫描 + 查找访问方法是非常昂贵的。因此，当你有一个非聚集覆盖索引时，优化器通常会结合查找，仅处理极小比例的符合条件的行。我解释过，这是一个转折点，超过该点后，优化器倾向于对表进行全扫描。如果你有一个过滤器倾向于产生大量匹配项，且获得良好的性能对你来说很重要，那么你的重点应该放在消除对昂贵查找的需求。这可以通过安排覆盖索引来实现——即在叶节点行中包含查询所引的所有列。获取覆盖索引有两种主要方法：一种是使用聚集索引，另一种是使用包含列的非聚集索引。本节侧重于前者，下一节重点关注后者。

聚集索引显然是一个覆盖索引，因为叶节点行就是数据行。对于基于聚集索引的第一键（或列）进行过滤的查询，优化器通常使用聚集查找 + 范围扫描方法。这种访问方法在叶节点级执行到第一个符合条件的行的查找操作，然后应用范围扫描直到最后一个符合条件的行。由于避免了昂贵的查找，这种访问方法始终比替代的全表扫描更高效。这使得基于此方法的计划成为一个微不足道的计划，意味着无论匹配行数有多少，该查询都只有一个优化计划。

过滤器使用了等号运算符，但由于 `orderdate` 列不是唯一的，过滤器可能有多个匹配行。在我的情况下，我得到了 703 行匹配。SQL Server 报告此查询在我处执行了 22 次逻辑读取。自然地，如果你使用 `>=`、`<=`、`<` 和 `BETWEEN` 运算符，你会得到类似的访问方法。（注：原文后续存在大量重复内容，此处已按逻辑去重翻译）

图 2-35 显示了创建此索引后我们示例查询的执行计划，图 2-36 说明了存储引擎如何处理访问方法。

![](img/bdc38aa36f6e2987d913ee5381474711_120_0.png)

**图 2-35** 覆盖非聚集索引查找 + 范围扫描（执行计划）。

![](img/bdc38aa36f6e2987d913ee5381474711_120_1.png)

**图 2-36** 覆盖非聚集索引查找 + 范围扫描（存储引擎）。

观察计划中 Index Seek 算子的 Seek Predicates（寻查找谓词）属性：`Prefix: shipper = 'C'; Start: orderdate >= '2014-01-01'; End: orderdate < '2015-01-01'`。寻查找操作在索引叶节点中找到满足 Prefix 和 Start 谓词的第一行。范围扫描一直持续到满足 Prefix 和 End 谓词的最后一行。当我在系统上运行此查询时，我得到了 49,782 行匹配结果。SQL Server 报告该查询仅有 222 次逻辑读取。范围扫描只读取了包含符合条件的页。如果创建索引时将列放在键列表的前面并将等值列放在后面，情况将完全不同。SQL Server 将不得不扫描所有满足范围谓词（`orderdate >= '20140101' AND '20150101'`）的行作为寻查找谓词，并将等值谓词（`shipperid = 'C'`）作为剩余谓词进行评估。

如果你有多个范围谓词，那么你的运气就不好。在这种情况下，无法创建一个索引来使符合条件的行在叶索引中处于连续的范围内。在范围谓词中，只有在范围谓词中出现的列里涉及前导键列的范围谓词可以用作寻查找谓词；所有剩余的范围谓词将用作剩余谓词，应用于扫描到的行，以决定是否返回它们。出于这个原因，您希望将与选择性最高的范围谓词相关的列放置在与等值谓词相关的列之后。将范围谓词的所有剩余列放在索引键列表的最后。

例如，假设你的过滤器具有谓词 `col1 > 5 AND col2 > 10`。假设第一个谓词有 50% 的匹配行，而第二个谓词有 2%。你想要确保定义索引时的键列表为 `(col2, col1)` 而不是反过来。这样 SQL Server 将只需要扫描索引叶节点中 2% 的页，而不是 50%。你将在书中看到一些与多个范围谓词相关的性能问题示例，以及缓解这些问题的建议方法。你将在第 7 章“处理日期和时间”中关于间隔的讨论中找到此类示例，在第 11 章“图形和递归查询”中关于嵌套集合模型的讨论中找到此类示例。

总结一下，当你有多个等值谓词时，可以按你喜欢的任何顺序将列放置在索引键列表中。当你最多有一个范围谓词时，将等值谓词的列放置在第一个键列表中，并将范围谓词的列放在最后。当你有多个范围谓词时，将来自选择性最高的范围谓词的列放置在其他范围谓词的列之前。

有关优化多个谓词的更多信息，请参阅“多个范围谓词的优化技巧”系列文章。第 1 部分可以在：http://sqlmag.com/database-development/optimization-tips-multiple-range-predicates-part-1 查看。第 2 部分在此：http://sqlmag.com/t-sql/optimization-tips-multiple-range-predicates-part-2。第 3 部分在这里：http://sqlmag.com/t-sql/optimization-tips-multiple-range-predicates-part-3。

完成后，运行以下命令进行清理：

```sql
DROP INDEX idx_nc_sid_od_i_cid_orderid on Orders;
```

# 基数估计 (Cardinality estimates)

SQL Server 关系引擎（也称为查询处理器）内部的主要组件是查询优化器。该组件负责为您提交给 SQL Server 的查询生成物理执行计划。在查询优化期间，优化器会探索替代计划，并从中选择它认为效率最高的一个。优化器需要决定使用何种访问方法访问对象、使用什么连接算法、使用什么聚合算法和去重算法、为排序和哈希活动分配多少内存等。在许多情况下，优化器在计划不同点需要做出的选择取决于基数估计——即从上一个算子返回了多少行。为了进行基数估计，优化器使用了一个名为基数估计器的组件。

当你分析图形化查询执行计划时，可以将鼠标指针悬停在来自算子的箭头上来查看基数估计。如果你查看估计的查询计划，你只会看到估计值。如果你查看实际计划，你将同时看到估计行数和实际数值。即使是优化器做的次优选择也与不准确的基数估计有关，检测这些问题的主要方法是与实际值进行比较。

此查询的执行计划如图 2-37 所示。

| 实际行数 | 50000 |
| --- | --- |
| 预估行数 | 100 |
| SELECT Cost: 0 % | Compute Scalar Cost: 0 % | Stream Aggregate (Aggregate) Cost: 0 % | Sort Cost: 4 % | Nested Loops (Inner Join) Cost: 0 % | Index Seek (NonClustered) [Orders,PK_Orders] Cost: 1 % |
| Memory Grant 1088 | | | | | | |

**图 2-37** 基数被低估的执行计划。



正如指令所示，优化器针对值 999900 对查询进行了优化，而没有考虑运行时的值。优化器使用了 `orderid` 列上的直方图来估计该输入过滤器的基数，并得出了 100 行的估计值。在实践中，该过滤器有 500,000 条匹配项。因此，你看到了优化器选择低估所导致的上述四个影响。它选择在 `PK_Orders` 中进行查找（seek）并回查（lookups），尽管扫描表会更高效。它选择对行进行排序并使用基于顺序的聚合算法（流聚合 Stream Aggregate），尽管哈希聚合（hash aggregate）会更高效。排序操作的内存授予（memory grant）是不必要的，因为它是基于 100 行的估计，因此排序算符（Sort operator）最终溢出到 `tempdb`（溢出级别 2）。它选择了串行计划（serial plan），尽管并行计划（parallel plan）会更高效。

高估倾向往往会产生与低估几乎相反的结果（再次强调，这不是详尽列表）：

- 对于过滤器，倾向于使用扫描而不是索引查找和回查。
- 对于聚合、连接和去重（distinct），倾向于使用基于哈希的算法而不是基于顺序的算法。
- 对于排序和哈希操作，不会发生溢出，但很可能会获得比需要更大的内存授予，导致内存浪费。
- 倾向于使用并行计划而不是串行计划。

为了演示高估，我将在查询中使用一个变量并为其赋值一个会导致产生选择性过滤的值，如下所示：

```sql
DECLARE @i AS INT = 999900;

SELECT empid, COUNT(*) AS asumnbers
FROM dbo.Orders
WHERE orderid > @i
GROUP BY empid;
```

与参数值不同，变量值通常无法被嗅探（sniffed）。这是因为优化器开始工作的初始优化单元是整个批处理（batch）。优化器应该在优化查询之前执行查询之前的代码。换句话说，它在优化查询之前没有执行变量赋值。因此，它根据未知的变量值对预测的 `order >` 进行了基数估计。稍后在“未知项”章节中，我在表 2-1 中提供了一张针对未知输入的广泛估算值表。你会发现，对于具有未知输入的大于（`>`）操作符，优化器使用了 30% 的硬编码估计值。将 30% 应用于表中 1,000,000 行的基数上，你得到了 300,000 行。而实际匹配数仅为 100 行。你可以在图 2-38 中看到这一点。

![](img/bdc38aa36f6e2987d913ee5381474711_125_0.png)

### 图 2-38 基数被高估的执行计划。

你可以看到基数高估对优化器选择所产生的上述影响。它选择扫描某个覆盖索引，而不是索引 `PK_Orders` 查找和回查。它选择在局部聚合上使用基于哈希的算法进行局部/全局聚合，而不是使用基于顺序的聚合。用于哈希操作和排序操作的内存授予被夸大了。它选择了并行计划而不是串行计划。

当然，如果基数估计准确是最好的，但在低估和高估之间，我通常更倾向于后者。这是因为我发现高估对查询性能的影响往往没有低估严重。

## 统计信息

SQL Server 依赖数据的统计信息来进行基数估计。每当你创建一个索引时，SQL Server 会通过对数据进行全扫描来创建统计信息。当需要额外的统计信息时，SQL Server 可能会自动创建它们。SQL Server 创建三种类型的统计信息：头部（header）、密度向量（density vectors）和直方图（histogram）。为了演示这些，运行以下代码将创建一个具有键列 `(custid, empid)` 的索引：

```sql
CREATE INDEX idx_nc_eid ON Orders(custid, empid);
```

SQL Server 创建了上述三种统计信息来支持该索引。你可以通过运行 `DBCC SHOW_STATISTICS('Orders', 'idx_nc_eid')` 来查看它们。

我从此命令获得了以下输出（头部文本已适应显示）：

| Name | Updated | Rows | Rows Sampled | Density | Average key length |
| --- | --- | --- | --- | --- | --- |
| idx_nc_eid | Oct 21 2014 | 100000 | 100000 | 0.0002646 | 18 |
| Filter | | | | | |
| YES | | 100000 | | | |
| 5E-05 | | custid | | | |
| 1.05021E-06 | | custid, empid | | | |
| 0.00042E-06 | | custid, empid, ordinate | | | |
| RANGE_KEY | RANGE_ROWS | AVG_RANGE_ROWS | | | |
| 0000000001 | | | | | |
| 0000000130 | | 37 | 37 | 0.02896 | |
| 0000000252 | | 37 | 37 | 0.03223 | |
| 0000000310 | | 29 | 29 | 0.01928 | |
| 0000000519 | | 1138 | 11 | 0.0662 | |
| 00000019486 | | 63 | 63 | 0.0555 | |
| 00000019704 | | 1034 | 10 | 0.3577 | |
| 00000019783 | | 4045 | 40 | 0.3875 | |
| 00000019904 | | 5906 | 59 | 0.5159 | |
| 00000020000 | | 4733 | 47 | 0.4921 | |

观察直方图的前两步：

| RANGE_HI_KEY | RANGE_ROWS | EQ_ROWS | DISTINCT_RANGE_ROWS | AVG_RANGE_ROWS |
| --- | --- | --- | --- | --- |
| C0000000001 | 46 | 0 | 1 | |
| C0000000130 | 6437 | 37 | 128 | 50.2891 |

输入值属于第 2 步。它小于该步的 `RANGE_HI_KEY` 值，因此 SQL Server 使用 `AVG_RANGE_ROWS` 值 50.2891 作为基数估计。我在我的系统上针对此查询得到的执行计划显示，估计行数为 50.2891，而实际行数为 57。

如你所见，对于已知输入的等值谓词，基数估计非常直观。如果你有范围谓词，估计值将根据直方图中的信息进行插值。如果只涉及一步，估计值将根据该步的信息进行插值。如果涉及多个步骤，SQL Server 将范围划分为与不同步骤相交的子区间，优化器会对每个子区间进行估计，并汇总这些估计值。

下一个示例演示了优化器使用密度向量的情况。请记住，与参数不同，变量值是可以被嗅探（sniffable）的。因为初始优化单元是批处理（batch），优化器在优化查询之前不应该执行赋值。考虑以下代码：

```sql
DECLARE @cid AS VARCHAR(11) = 'C0000000001';

SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid = @cid;
```

优化器在这里无法嗅探变量值。由于 `custid` 列可用密度信息，优化器使用了它。因为该列的密度为 0.00005。将此值乘以表 1,000,000 行的基数，你就会得到 50。我针对此查询得到的执行计划显示，估计行数为 50，实际行数为 46。

## 多个谓词的估计

如所述，SQL Server 只支持单列直方图。当查询过滤涉及多个谓词时，SQL Server 可以根据各自的直方图对每个谓词做出估计，但它需要以某种方式将这些估计合并为一个单一估计。旧版估计器和新的基数估计器处理此的方式不同。

我将分别解释谓词合（由 `AND` 运算符分隔的谓词）和谓词取或（由 `OR` 运算符分隔的谓词）情况下的估计方法。

在描述多个谓词的估计方法之前，我会先说明两个特定谓词的选择性（匹配百分比），以便在示例中使用它们。接下来的查询包含一个基于 `custid` 列的谓词的过滤条件：

```sql
SELECT orderid, custid, empid, shipper, orderdate, filler
FROM dbo.Orders
WHERE custid <= 'C000001000';
```

在我的系统上，查询计划显示估计行数为 52,800。这个数字对应 5.28% 的选择性。

接下来的查询包含一个基于 `empid` 列的谓词的过滤条件：

```sql
SELECT orderid, custid, empid, shipper, orderdate, filler
FROM dbo.Orders
WHERE empid <= 100;
```

如果你在运行此查询之前 `empid` 列上没有统计信息，则执行此查询将触发统计信息的创建。在我的系统上，查询计划显示估计行数为 19,800，对应 19.8% 的选择性。

基数估计器假设当你的查询有多个谓词时，它们之间是相互独立的。基于这一假设，对于谓词合，它计算出的结果选择性是各个单独选择性的乘积。考虑以下查询作为示例（注意跟踪遵循了基数估计器的使用）：

```sql
SELECT orderid, custid, empid, shipper, orderdate, filler
FROM dbo.Orders
WHERE custid <= 'C000001000'
AND empid <= 100
OPTION(QUERYTRACEON 9481);
```

在我的系统上，我得到了如图 2-40 所示的查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_129_0.png)

**2-40** 使用旧版基数估计器对合与进行的估计。

请记住，我系统上的单独估计值为 5.28% 和 19.8%，因此乘积是 5.28% * 19.8% = 10.4%。事实上，计划中的基数估计确实反映了这一点。

在拥有多年 SQL Server 经验后，微软发现实际上，谓词之间存在某种程度的依赖关系。在平均情况下，谓词既不是独立的也不是完全依赖的——而是处于两者之间的中间位置。即使我的样本数据也没有反映这一点，因为我是使用简单的随机化来创建它的；如果你仔细考虑，下单的客户与处理订单的员工之间通常会存在某些依赖关系。如果完全独立，统计学上应该使用单独估计值的乘积。但由于现实中的平均情况介于两者之间，微软选择了一种名为“指数退避”（exponential backoff）的方法，这种方法适用于这种情况。该方法考虑了最具选择性的估计作为基准，然后逐渐减少选择性较低估计的影响。假设 S1 是最具选择性的估计，S2 是下一个，以此类推，指数退避公式为：

```
S1 * S2/2 * S3/4 ...
```

在这种情况下，基数估计会考虑这种选择性的百分比，乘以 1,000,000 行的基数，得到 50。我针对此查询得到的执行计划显示，估计行数为 50，而实际行数为 46。

SQL Server 在创建索引时会为索引创建统计信息；因此，`orderid` 列上的直方图包含了表中的 900,000 行数据。运行以下代码显示索引的统计信息：

```sql
DBCC SHOW_STATISTICS('dbo.Orders2', 'PK_Orders2');
```

我在我的系统上得到了以下输出：

| Name | Updated | Rows | Rows Sampled | Steps | Density | Average key |
| --- | --- | --- | --- | --- | --- | --- |
| PK_Orders2 | Oct 21 2014 | 9:29PM | 900000 | 900000 | 2 | 1 | 4 |
| String Index Filter Expression Unfiltered Rows | | | | | | | |
| NO | NULL | 900000 | | | | | |
| All density Average Length Columns | | | | | | | |
| 1.11111e-06 | 4 | orderid | | | | | |
| RANGE_HI_KEY RANGE_ROWS | EQ_ROWS | DISTINCT_RANGE_ROWS | AVG_RANGE_ROWS | | | | |
| 1 | 1 | 0 | 1 | | | | |
| 900000 | 1 | 899998 | 1 | | | | |

输出的最后部分是 `orderid` 列上的直方图。观察发现最大订单 ID 值为 900,000，这确实是表中目前的最大值。接下来，运行以下代码添加 100,000 行：

```sql
INSERT INTO dbo.orders2
SELECT *
FROM dbo.Orders
WHERE orderid > 900000 AND order <= 100000;
```

现在查询表并过滤订单 ID 大于 900,000 的行，如下所示（跟踪标志确保了使用旧的基数估算）：

```sql
SELECT orderid, custid, emid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid > 900000
ORDER BY orderdate
OPTION(QUERYTRACE9481);
```

由于额外的 100,000 行少于刷新统计信息的阈值，新行没有被直方图建模。你可以看到最大值仍然是 900,000。旧的基数估算器检查直方图，发现过滤器的范围在直方图最大值之后。仅根据此信息，估计的匹配行数为 0，但允许的最小估计值为 1。检查图 2-42 中查询的执行计划。

### Warnings

Operator tempdb to spill during data execution with level 2

Actual Number of Rows: 100000

Estimated Number Rows: 1



# 图 2-42 显示使用旧基数估算器时升序键问题的计划

| SELECT (Cost: 0 %) | Sort (Cost: 63 %) | Nested Loops (Inner Join) (Cost: 0 %) | Compute Scalar (Cost: 0 %) | Index Seek (NonClustered) [Orders2] (Ps_Orders2) (Cost: 18 %) | RID Lookup (Heap) [Orders2] (Cost: 18 %) |

观察发现过滤器的估计基数为 1，而实际上是 100,000。你可以看到优化器根据此不准确估计做出的若干次次优选择。这个问题通常发生在列为升序键且你过滤最新数据时。通常，最新数据没有被直方图建模。

新的基数估算器处理估计的方式不同。如果它识别出过滤区间超过了记录标记，它将通过考虑自上次统计刷新以来的修改次数来插值估计。再次运行示例查询，但这次让 SQL Server 使用新的基数估算器：

```sql
SELECT orderid, custid, emid, shipperid, orderdate, filter
FROM dbo.Orders2
WHERE orderid > 900000
ORDER BY orderid;
```

我得到了图 2-43 所示的执行计划。

Actual Number of Rows: 100000

Estimated Number Rows: 1

| SELECT (Cost: 0 %) | Parallelism (Gather Streams) (Cost: 4 %) | Sort (Cost: 10 %) | Table Scan [Orders2] (Cost: 86 %) | Memory Grant 266304 |

# 图 2-43 显示使用新基数估算器解决升序键问题的计划

这一次，你可以看到估计是准确的。结果是优化器做出的选择更加优化。

另一个你可以用来处理升序键问题的工具是跟踪标志 `2389`。与新的基数估算器不同，该跟踪标志在 SQL 2014 之前可用。如果你启用此跟踪标志，当 SQL Server 刷新统计信息时，它会检查源列值是否持续增加。如果它们连续三次刷新中持续增加，SQL Server 会在直方图中添加一个毫秒以匹配为升序数据。然后，在查询时，SQL Server 会在模型数据中添加一个毫秒 http://blogs.msdn.com/b/janio/archive/2006/04/24/582227.aspx。

对于大表，自动更新统计信息的默认阈值（500 加上更改的 20%）可能是不够的。想想：对于一个拥有 1,000,000 行的表，20% 是 200,000 次更改。如果你更新了 100,000 行，统计信息将不会自动更新。如果你更新了 300,000 行，它们就会更新。

图 2-44 显示了这些查询的计划。

## 查询 1

| 实际行数 | 100 |
| --- | --- |
| 预估行数 | 300000 |

![](img/bdc38aa36f6e2987d913ee5381474711_136_0.png)

```sql
SELECT
Cost: 0 %
Clustered Index Scan (Clustered)
[Orders].[idx_cl_od]
Cost: 100 %
```

## 查询 2

| 实际行数 | 487 |
| --- | --- |
| 预估行数 | 300000 |

![](img/bdc38aa36f6e2987d913ee5381474711_136_1.png)

```sql
SELECT
Cost: 0 %
Clustered Index Scan (Clustered)
[Orders].[idx_cl_od]
Cost: 100 %
```

> **警告**
>
> 无统计信息的列: `[Performancev3].dbo.[Orders].custid`

**图 2-44** 显示预估为 30% 的计划。

第一个查询使用了无法被嗅探（sniffed）的值。第二个使用了常量，且没有统计信息，你禁用了创建新统计信息的选项。

对于 `BETWEEN` 和 `LIKE` 谓词，表 2-1 显示预估值为 9%。该规则的例外是 SQL Server 2014，当你对变量使用 `BETWEEN`，或对禁用嗅探的参数时，预估值为 16.4317%。以下查询演示了这些规则：

```sql
-- Query 1
DECLARE @i AS INT = 99901, @j AS INT = 100000;

SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderdate BETWEEN @i AND @j;
```

```sql
-- Query 2
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderdate BETWEEN @i AND @j
OPTION(QUERYTRACEON 9481);
```

```sql
-- Query 3
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid BETWEEN 'C0000000001' AND 'C00000000010';
```

```sql
-- Query 4
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid LIKE '%9999%';
```

这些查询的执行计划如图 2–45 所示。

| 查询 1 | 实际行数 | 100 |
| --- | --- | --- |
| | 预估行数 | 164317 |
| SELECT Cost: 0 % | Parallelism (Streams) | Clustered Index Scan (Clustered) [Orders].idx_c1_0ld Cost: 95 % |

| 查询 2 | 实际行数 | 100 |
| --- | --- | --- |
| | 预估行数 | 90000 |
| SELECT Cost: 0 % | Parallelism (Streams) | Clustered Index Scan (Clustered) [Orders].idx_c1_0ld Cost: 97 % |

| 查询 3 | 实际行数 | 487 |
| --- | --- | --- |
| | 预估行数 | 90000 |
| SELECT Cost: 0 % | Parallelism (Streams) | Clustered Index Scan (Clustered) [Orders].idx_c1_0ld Cost: 97 % |

| 查询 4 | 实际行数 | 126 |
| --- | --- | --- |
| | 预估行数 | 90000 |
| SELECT Cost: 0 % | Parallelism (Streams) | Clustered Index Scan (Clustered) [Orders].idx_c1_0ld Cost: 97 % |

**图 2–45** 显示针对 BETWEEN 和 LIKE 的预估计划。

第一个查询落在我描述的例外，因此它获得了 16.4317% 的预估值。第二个查询与第一个相同，但因为你强制使用了基数估计器（cardinality estimator），你得到了 9% 的预估值。第三和第四个查询使用了常量，但没有可用的统计信息。顺便提一下，查询 4 通常会使用包含子字符串出现次数信息的统计信息。然而，由于你禁用了数据库的自动创建统计信息，SQL Server 没有创建这些统计信息，而是使用了基于未知输入的预估方法。

对于等号操作符，未知输入的预估方法取决于 SQL Server 中列的唯一性和值的值。当列是唯一的时，预估值为 1 行。当不唯一，在 SQL Server 2014 中预估值为 $C^{1/2}$，其中 C 是输入的基数；在 SQL Server 2014 之前是 $C^{3/4}$。

以下查询演示了所有三种方法：

- 查询 1

```sql
DECLARE @OI AS INT = 100000;

SELECT orderid, custid, empid, shiperid, orderdate, friday
FROM dbo.Orders
WHERE orderid = @oi;
```

- 查询 2

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid = 'C000000001';
```

- 查询 3

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid = 'C000000001'
OPTION(QUERYTRACEON 9481);
```

这些查询的带预估的执行计划如图 2-46 所示。

查询 1: 成本（相对于批处理）:0% ![](img/bdc38aa36f6e2987d913ee5381474711_138_0.png)

查询 2: 成本（相对于批处理）:0% ![](img/bdc38aa36f6e2987d913ee5381474711_138_1.png)

查询 3: 成本（相对于批处理）:0% ![](img/bdc38aa36f6e2987d913ee5381474711_138_2.png)

**图 2-46** 显示等号的预估计划。

当你进行实验时，运行以下代码关闭统计信息的自动创建：

```sql
ALTER DATABASE Performancev3 SET AUTO_CREATE_STATISTICS OFF;
```

可以重新运行查询查看 SQL Server 何时自动创建统计信息。例如，重新运行带有 LIKE 谓词的查询：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE custid LIKE '%9999%';
```

我得到了图 2-47 所示的查询计划。

| | 实际行数 | 126 |
| --- | --- | --- |
| | 预估行数 | 29354 |
| SELECT Cost: 0 % | Nested Loops (Inner Join) Cost: 18 % | |
| Index Scan (NonClustered) [Orders].[idx_nc_sid_od] Cost: 80 % | | |
| Key Lookup (Clustered) [Orders].[idx_cl_od] Cost: 2 % | | |

**图 2-47** 使用 LIKE 字符串的查询计划。

SQL Server 首先创建了 `custid` 列的字符串统计信息并基于统计信息进行了预估。与之前在图 2-45 中获得的该查询预估（查询 4）相比，该预估更准确。

旧版和新基数估计器的另一个区别在于它们如何处理带表达式的过滤。以 `order=0` 为例。旧版基数估计器简单地将该情况视为未知输入。在 orders 中，这被转换为 $1,000,000^{3/4}=31,622$。这可能是低估了。新基数估计器更加智能。在这里，它意识到表达式使用了模运算。从统计上来说，对于 `order=0`，你将获得 50% 的匹配项。因此，该情况的预估值为 500,000 行。这比旧版估计器生成的数值接近得多。

# 索引功能

本节介绍了各种索引功能。包括降序索引、包含列、过滤索引和统计信息、列存储索引以及内联索引定义。这些功能按其添加到 SQL Server 的顺序涵盖。

## 降序索引

在 SQL Server 中，你可以在索引定义中指定列的方向。默认是升序，但使用 `DESC` 关键字可以请求降序，例如 `col1, col2 DESC`。

基于表的索引在叶节点级具有双向链表。SQL Server 可以按正反顺序扫描叶行。顺便提一下，正如你在第 10 章中学到的，内存优化表的 BW-Tree 索引是单向的。回到基于表的索引，起初似乎不需要降序索引，但有一些用例。

事实证明，存储引擎目前能够并行处理正扫描。每当你有一个反扫描时，它都是串行处理的。以以下查询为例：

```sql
-- 查询 1, 并行
SELECT orderid, custid, empid, shipper, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 100000
ORDER BY orderdate;
```

```sql
-- 查询 2, 串行
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 100000
ORDER BY orderdate DESC;
```

图 2-48 显示了这些查询的执行计划。

查询 1: 成本（相对于批处理）:50%
```sql
SELECT * FROM [dbo].[Orders] WHERE [orderid]<=@1 ORDER BY [orderdate] ASC
```
![](img/bdc38aa36f6e2987d913ee5381474711_140_0.png)

查询 2: 成本（相对于批处理）:50%
```sql
SELECT * FROM [dbo].[Orders] WHERE [orderid]<=@1 ORDER BY [orderdate] DESC
```
![](img/bdc38aa36f6e2987d913ee5381474711_140_1.png)

**图 2-48** 显示没有并行反扫描的计划。

当你尝试使用跟踪标志 `8649` 强制第二个查询并行时，观察优化器的行为非常有意思，如下：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 100000
ORDER BY orderid DESC
OPTION(QUERYTRACEON 8649);
```

该查询的计划如图 2-49 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_141_0.png)

**图 2-49** 强制并行计划。

由于无法使用并行反向扫描，优化器选择了一个使用并行无序扫描后进行显式排序操作的计划。显然，这是一个非常低效的计划。如果你发现并行是查询性能的关键因素，可以安排降序索引。当然，如果微软在某时刻引入了对并行反向扫描的支持，你就不再需要降序索引了。

降序索引另一个有用的案例是带有窗口分区句（window partition clause）和窗口排序句（window order clause）的窗口函数。考虑以下查询：

```sql
-- Query 1
SELECT shipperid, orderdate, custid,
ROW_NUMBER() OVER(PARTITION BY shipperid ORDER BY orderdate) AS rownum
FROM dbo.Orders;
```

```sql
-- Query 2
SELECT shipperid, orderdate, custid,
ROW_NUMBER() OVER(PARTITION BY shipperid ORDER BY orderdate DESC) AS rownum
FROM dbo.Orders;
```

```sql
-- Query 3
SELECT shipperid, orderdate, custid,
ROW_NUMBER() OVER(PARTITION BY shipperid ORDER BY orderdate DESC) AS rownum
FROM dbo.Orders
ORDER BY shipperid DESC;
```



目前，表上有一个名为 `idx_nc_sid_od_cid` 的覆盖索引，其键列表定义为 `(shipperid, orderdate, custid)`。查看图 2-50 中这些查询的执行计划。

### 查询 1：查询成本（相对于批处理）：100

```sql
SELECT shipperid, custid, ROW_NUMBER() OVER(PARTITION BY shipperid ORDER BY order) as rownum
```

| SELECT | Sequence Project (Compute Scalar) | Segment | Index Scan (NonClustered) |
| :--- | :--- | :--- | :--- |
| Cost: 0 % | Cost: 2 % | Cost: 0 % | Cost: 98 % |

### 查询 2：查询成本（相对于批处理）：100

```sql
SELECT shipperid, custid, ROW_NUMBER() OVER(PARTITION BY shipperid ORDER BY order DESC) as rownum
```

| SELECT | Sequence Project (Compute Scalar) | Segment | Parallelize (Gather Streams) | Sort | Index Scan (NonClustered) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Cost: 0 % | Cost: 0 % | Cost: 19 % | Cost: 71 % | Cost: 10 % | |

### 查询 3：查询成本（相对于批处理）：100

```sql
SELECT shipperid, custid, ROW_NUMBER() OVER(PARTITION BY shipperid ORDER BY order DESC) as rownum
```

| SELECT | Sequence Project (Compute Scalar) | Segment | Index Scan (NonClustered) |
| :--- | :--- | :--- | :--- |
| Cost: 0 % | Cost: 2 % | Cost: 0 % | Cost: 98 % |

**图 2-50** 带有窗口函数的查询计划。

查询 1 的计划显示，由于有一个覆盖索引，其键按升序排列从分区列开始，并按照窗口函数指定的顺序继续包含排序列，因此优化器选择了有序索引并避免了显式的排序操作。

在查询 2 中，窗口函数的规范与查询 1 类似，但排序列 `orderdate` 使用了降序。从理论上说，优化器本可以选择以降序扫描我们的覆盖索引的计划。毕竟，在缺少显示 `ORDER BY` 子句的情况下，SQL Server 可能会按照所需的顺序返回行。但看起来 SQL Server 必须按窗口分区元素的升序顺序处理行，因此它添加了一个显式的排序操作。

奇怪的是，正如你在查询 3 的计划所示，如果你添加了一个按 `shipperid` 降序排列的显示 `ORDER BY` 子句，优化器突然发现它可以使用反向扫描来计算窗口函数并支持所需的顺序。这是 Brad Shultz 在数百人面前演示扫描时提到的最后一点。

索引的另一个用例是 SQL Server 需要处理方向相反的多个列的行。例如，如果你的查询有一个 `ORDER BY col1, col2 DESC` 的子句，它可以从键列表为 `col1, col2 DESC` 或 `col1 DESC` 的索引中获益。两个列都按升序排列的索引并不是最优的；SQL Server 仍然需要显式对行进行排序。

作为一个趣事，二十年前，在 SQL Server 2000 发布不久后，Mikey Snyder 发现了我见过的 SQL Server 最令人惊讶的 Bug 之一。如果你创建一个以 `col1 DESC` 为键的索引，并执行带有过滤器 `col1 > @n` 的 `DELETE` 语句，SQL Server 会删除所有 `col1 < @n` 的行。这个 Bug 在 SQL Server 2000 RTM 中被修复了，当然是这样。

---

该查询的执行计划如图 2-52 所示。

| 实际行数 | 99 |
|---|---|
| 估计行数 | 678 |

![](img/bdc38aa36f6e2987d913ee5381474711_145_0.png)

```sql
SELECT Cost: 0 %    Index Seek (NonClustered) [idx_USA_orderdate] Cost: 100 %
```

**图 2-52** 使用过滤索引的计划，优化器认为该索引可能有用，但基数估计值不准确。

由于索引匹配了查询过滤器，优化器认为该索引可能有用。顺便提一下，如果查询过滤器是索引过滤器的子区间，该索引仍然可以使用。例如，如果索引过滤器为 `col1 > 10` 而查询过滤器为 `col1 > 20`，则可以使用该索引。回到我们的示例，因为索引键列与查询范围谓词中的列匹配，所以优化器可以使用查找（seek）和范围扫描（range scan）来获取符合条件的行。索引覆盖了查询，因此不需要回表（lookups）。该索引对于此查询是最优的。

奇怪的是，尽管我提到过过滤索引可以提高基数估计的质量，但如果你查看图 2-52 中的查询计划，该估计值似乎并不非常准确。事实上，它反映的是仅基于 `orderdate` 列对过滤器的估计值。问题在于，在这里你并没有对过滤后的行进行任何操作，因此优化器不需要更准确的估计。例如，如果你在查询中添加 `ORDER BY orderdate`，你将看到排序输出的估计行数将会。

我从 Paul White 那里学到的一个有趣点是，如果你将过滤列（在本例中为 `shipcountry`）添加到索引中——例如作为包含列（included column）——估计从一开始将是基于过滤统计结果的。基于此思路，使用 `shipcountry` 作为包含列重新创建索引，如下：

```sql
CREATE NONCLUSTERED INDEX idx__USA_orderdate
ON Sales.Orders(orderdate)
INCLUDE(orderid, custid, requireddate, shipcountry)
WHERE shipcountry = 'USA'
WITH (DROP_EXISTING = ON);
```

重新运行查询：

```sql
SELECT orderid, custid, orderdate, requireddate
FROM Sales.Orders
WHERE shipcountry = 'USA'
AND orderdate >= '20140101';
```

该查询的执行计划如图 2-53 所示。

| 实际行数 | 99 |
|---|---|
| 估计行数 | 99 |

![](img/bdc38aa36f6e2987d913ee5381474711_146_0.png)

图 2-53 使用过滤索引且基数估计准确的计划。

观察发现这个估计值是准确的。

你还可以使用过滤索引来解决与数据完整性常见的请求。SQL Server 支持的 `UNIQUE` 约束在强制唯一性时，从不会将 `NULL` 视为相等。如果你在允许 `NULL` 的列上定义 `UNIQUE` 约束，则只允许该列有一行是 `NULL`。在某些情况下，你可能需要强制非 `NULL` 值的唯一性，但允许多个 `NULL`。标准 SQL 不支持这种功能，但 SQL Server 支持。通过过滤索引，处理这非常简单。创建一个基于 `WHERE <column> IS NOT NULL` 形式谓词的简单过滤索引。例如，运行以下代码创建一个在 `col1` 列上带有过滤索引的表 T1：

```sql
IF OBJECT_ID('dbo.T1', 'U') IS NOT NULL DROP TABLE dbo.T1;

CREATE TABLE dbo.T1(col1 INT, col2 VARCHAR(10));

CREATE NONCLUSTERED INDEX idx_col1_notnull ON T1(col1) WHERE col1 NOT NULL;
```

运行以下代码插入两行具有相同非 `NULL` col1 值的行：

```sql
INSERT INTO dbo.T1(col1, col2) VALUES(1, 'a'), (1, 'b');
```

尝试失败并报错：

```text
Msg 2601, Level 14, State 1, Line 1023
Cannot insert duplicate key row in object 'dbo.T1' with unique index 'idx_col1_notnull'. The duplicate key value is (1).
The statement has terminated.
```

尝试插入两行 col1 为 `NULL` 的行：

```sql
INSERT INTO dbo.T1(col1, col2) VALUES(NULL, 'c'), (NULL, 'd');
```

这次代码成功了。完成后，运行以下代码进行清理：

```sql
USE TSQL3;

DROP INDEX idx_USA_orderdate ON Sales.Orders;

DROP TABLE T1;
```

## 列存储 (Columnstore)

列存储技术是数据库领域的规则改变者。它最初在 SQL Server 2012 中引入，并在 SQL Server 2014 中显著改进。该技术主要针对数据仓库工作负载。考虑如图 2-54 所示的数据仓库的经典星型模型。

![](img/bdc38aa36f6e2987d913ee5381474711_147_0.png)

图 2-54 星型模型。

![](img/bdc38aa36f6e2987d913ee5381474711_150_0.png)

**图 2-56** 应用于事实表（Fact table）的列存储。

SQL Server 将数据分为**行组**（rowgroups）。每个行组包含约 1,000 行（更精确地说，多达 $2^{20}$ 行）。你可以通过查询视图 `sys.column_store_row_groups` 查找有关行组的信息。每个行组被分成单独的列段（column segments），每个列段都以高度压缩格式存储在不同的页面集上。你可以通过视图 `sys.column_store_segments` 查找有关列段的信息，包括列段中的最小值和最大值。SQL Server 使用字典将条目数字映射到较大的实际值来减少存储需求。SQL Server 始终对字符串使用字典，当唯一值足够少时，有时会对其他类型使用。你可以通过视图 `sys.column_store_dictionaries` 查找有关字典的信息。

创建列存储索引后，再次运行我们的查询：

```sql
SELECT D1.attr1 AS x, D2.attr1 AS y, D3.attr1 AS z,
COUNT(*) AS cnt, SUM(F.measure1) AS total
FROM dbo.Fact AS F
INNER JOIN dbo.dbo.DimA1 AS D1
ON F.key1 = D1.key1
INNER JOIN dbo.dbo.DimA2 AS D2
ON F.key2 = D2.key2
INNER JOIN dbo.dbo.DimA3 AS D3
ON F.key3 = D3.key3
WHERE D1.attr1 <= 10
AND D2.attr1 <= 15
AND D3.attr1 <= 10
GROUP BY D1.attr1, D2.attr1, D3.attr1;
```

## 查询优化

此查询的执行计划见 2-57。

![](img/bdc38aa36f6e2987d913ee5381474711_151_0.png)

2-57 针对列存储的星型连接查询计划。

我在我的系统中获取了此查询的性能统计数据：

Table 'Fact'. Scan count 8, logical 13235 CPU time = 172 ms, elapsed time = 185 ms.

如所述，从数据仓库的角度来看，我们的事实表数据非常小。在实践中，你会倾向于处理更大的表，此时行存储（rowstore）和列存储（columnstore）之间的性能差异会大得多。

列存储技术最大的优点之一是它完美消除了对事实表进行索引调优的需求。你只需要创建一个索引。为了满足查询，SQL Server 仅从相关列构建结果集。仔细想想，这非常有深意义；因为它拥有所有的覆盖索引，而无需为每情况创建单独的索引。此外，SQL Server 只从相关列构建结果集的这一事实，与行存储相比往往往往显著降低 I/O 成本。

列存储技术的另外两个方面也往往会降低 I/O 成本。如所述，微软通过列存储实现的压缩级别远高于行存储。此外，请记住 SQL Server 在内部记录了每个列段的最小值和最大值。如果你的查询按特定列进行过滤，且过滤后的值落在列段覆盖的范围之外，则整个行组将被排除。这种能力被称为段消除（segment elimination）。

SQL Server 中列存储技术实现的一个有趣方面是，它是内存优化的，但它不需要整个数据集都装入内存。列存储技术也极大受益于并行处理。

我描述了一些有助于降低 I/O 成本的技术方面。技术中还有一个方面有助于降低 CPU 成本。随着列存储技术，微软在 SQL Server 中引入了批处理执行（batch execution）。一个批处理是一部分行相关列的向量化形式。通常，批大小接近一千行。增强以支持批模式的算子一次处理一个批，而不是一次处理一行。算子执行的内部函数使用批作为行的输入。在我们示例查询的计划中，使用批模式的算子是列存储索引、哈希算子（Hash operators），图 2-57 突出了该计划中使用批模式的另外两个算子。其他算子的迭代次数较少。此外，它们按批评估元数据，而不是按行。这些都意味着更少的 CPU 周期。批模式仅在数据被组织为列存储时使用，但该技术本身并没有什么限制可以阻止它也应用于行存储。也许我们会在未来会看到这种支持。

如前所述，SQL Server 2012 中的列存储在许多方面都存在局限。你只能创建非聚集列存储索引，这意味着你必须在其中创建基于行存储的数据主要表示形式。对于非常大的数据仓库，你必须考虑额外的空间需求以及对数据的两种表示形式的维护。你最大的局限性是，一旦创建了非聚集列存储索引，该表就会变为不可加载的（nondatable）。绕过此限制的方法是维护两个具有相同结构的表：一个是带新表的分区表；另一个是不带列存储索引的增量表（trickle table），它用于吸收实时变化。一旦你准备好将增量表转换为分区表，你就可以创建非聚集列存储索引。

SQL Server 2014 在批处理处理方面做了多项改进。例如，它可以在哈希连接外连接、标量聚合器以及溢起到 tempdb 的算子中使用批模式。它还处理了需要从一种模式到另一种模式的情况。

```sql
CREATE TABLE FactCS
(
key1 NOT NULL,
key2 NOT NULL,
key3 NOT NULL,
measure1 NOT NULL,
measure2 NOT NULL,
measure3 NOT NULL,
measure4 VARCHAR(50) NULL,
Filler BINARY(100) NOT NULL DEFAULT (0x)
);
```

```sql
CREATE CLUSTERED INDEX idx_cl_cs ON FactCS;
INSERT INTO FactCS SELECT * FROM Fact;
```

动态地执行。SQL Server 2014 放宽了某些与数据类型相关的限制。例如，它支持精度超过 18 的 `NUMERIC`、精度超过 2 的 `DATETIMEOFFSET`、`BINARY` 和 `VARCHAR`（尽管不带 MAX 饰符），以及 `UNIQUEIDENTIFIER`。

使用 FactCS 表运行以下查询：

```sql
SELECT D1.attr1 AS x, D2.attr1 AS y, D3.attr1 AS z,
COUNT(*) AS sum, SUM(measure1) AS total
FROM dbo.FactCS AS F
  INNER JOIN dbo.Dim1 AS D1
  ON Fcs.key1 = D1.key1
  INNER JOIN dbo.Dim2 AS D2
  ON Fcs.key2 = D2.key2
  INNER JOIN dbo.Dim3 AS D3
  ON Fcs.key3 = D3.key3
  WHERE D1.attr1 <= 10
  AND D2.attr1 <= 15
  AND D3.attr1 <= 10
GROUP BY D1.attr1, D2.attr1, D3.attr1;
```

第一次运行查询时，SQL Server 可能需要刷新现有的统计信息并创建新的统计，因此解析和编译时间可能会稍长。第二次运行查询以获得更典型的运行时间感受。SQL Server 在我的系统上此查询报告了以下统计信息：

Table 'FactCS'. Scan count 8, logical reads 13556
CPU time = 139 ms, elapsed time = 219 ms.

有关列存储（columnstore）技术和 SQL Server 2014 改进的更多信息，请参考以下白皮书：http://research.microsoft.com/apps/pubs/default.aspx?id=193599。

完成后，运行以下代码进行清理：

```sql
SET STATISTICS IO OFF;
SET STATISTICS TIME OFF;
DROP INDEX idx_nc_cs ON dbo.Fact;
DROP TABLE dbo.FactCS;
```



## 内联索引定义

正如你将在第 10 章中学到的，SQL Server 2014 作为内存 OLTP 框架的一部分引入了对内存优化表的支持。在此实现中，创建后不允许进行 DDL 更改。为了允许你在创建表时像定义表一样定义索引，微软引入了内联索引定义的语法。由于微软已经在主要的解析器组件中做了大量工作，它还将此类语法的支持扩展到了磁盘表（包括表变量）。

请记住，一旦声明表变量，就无法更改其定义，因此你不能在现有表变量上定义索引。以前，你只能通过表定义中的 `PRIMARY KEY` 和 `UNIQUE` 约束在变量上定义索引，因此这些索引必须是唯一的。现在，通过新的内联索引语法，你可以在表变量定义中定义非唯一索引，如下所示：

```sql
DECLARE @T AS TABLE
{
  col1 INT NOT NULL,
  INDEX idx_c1_CLUSTERED, -- 列索引
  col2 INT NOT NULL,
  col3 INT NOT NULL,
  INDEX idx_nc_col2_col3 NONCLUSTERED (col2,col3) -- 表索引
};
```

仅通过约束，你就可以将列级索引作为列定义的一部分，并将基于复合键列表的表级索引作为独立项进行定义。在 SQL Server 2014 的实现中，内联索引不支持 `UNIQUE`、`INCLUDE` 和 `WHERE` 选项。如需唯一性，请像你以前间接通过 `PRIMARY KEY` 或 `UNIQUE` 约束那样定义索引。

## 使用扩展事件对调优查询进行排序

如果你在系统中遇到了通用的性能问题，尝试查找并修复瓶颈，一种常见的方法是优化查询以提高效率。棘手之处在于，系统中有很多查询模式，尝试优化所有查询是不现实的。你希望对需要调优的查询进行排序，以便将更多时间花在那些调优后对整个系统产生影响更大的案例上。

你需要决定使用哪种性能指标来对查询进行排序。可以是持续时间，因为这是用户对性能的感知。也可能是你识别了系统中特定的瓶颈，并依赖相关的指标。例如，如果你识别出 I/O 子系统存在瓶颈，你自然会想要关注 I/O 相关的指标，如读取和写入。

要衡量查询性能，可以使用带有 `statement completed` 事件的扩展事件会话捕捉系统中的典型工作负载。记住，语句带有性能信息。为了演示，我将对来自特定 SSMS 会话的即时查询进行负载采样，因此我将捕获 `sql_statement_completed` 事件并根据相关会话的 SPID 进行过滤。如果查询在你的环境中是从存储过程提交的，则你需要捕获 `sp_statement_completed` 事件并应用任何与你相关的过滤器。

帮助你确定调优哪些查询的关键元素是 `query_hash` 动作。它从 SQL Server 2012 开始在 `statement completed` 事件中可用。这是一个表示查询字符串模板或参数化形式的哈希值。具有相同模板的查询即使输入不同，也会获得相同的查询哈希值。在捕获工作负载后，按 `query_hash` 值对事件分组，并按总相关性能指标（例如，持续时间）降序对组（查询模板）进行排序。然后将更多精力投入到排名前的模板上。

使用以下代码创建一个扩展事件会话，将指定会话的性能负载捕捉到指定的目标文件中（确保将会话 ID 和文件路径替换为实际值），使用 `query_hash` 动作：

```sql
CREATE EVENT SESSION [perf] ON SERVER ADD EVENT sqlserver.sql_statement_completed(ACTION(sqlserver.query_hash)) TARGET package0.event_file(filename=N'C:\Temp\perf.xel')
```

使用以下代码启动会话：

```sql
ALTER EVENT SESSION [perf] ON SERVER = START;
```

假设你从 SSMS 运行以下工作负载，运行几次：

```sql
SELECT * FROM FactCS WHERE D1.attr1 <= 10 AND D2.attr1 <= 15 AND D3.attr1 <= 10
```

完成后，运行以下代码停止会话：

```sql
ALTER EVENT SESSION [perf] ON SERVER = STOP;
```

数据以 XML 格式捕获。使用以下代码将数据复制到临时表：

```sql
SELECT CAST(event_data AS XML) FROM sys.fn_xe_file_target('C:\Temp\', null, null)
```

查询 `#Events` 并提取列到临时表，如下：

```sql
SELECT 
  event_data.value('(@name="query_hash")[1]', 'bigint') AS query_hash,
  event_data.value('(@name="duration")[1]', 'bigint') AS duration,
  event_data.value('(@name="cpu_time")[1]', 'bigint') AS cpu_time,
  event_data.value('(@name="physical_reads")[1]', 'bigint') AS physical_reads,
  event_data.value('(@name="logical_reads")[1]', 'bigint') AS logical_reads,
  event_data.value('(@name="writes")[1]', 'bigint') AS writes,
  event_data.value('(@name="row_count")[1]', 'bigint') AS row_count
FROM #Events;
```

你可以通过查询 `#Queries` 方便地检查查询性能，如下所示：

```sql
SELECT query_hash, duration, cpu_time, physical_reads AS physreads,
logical_reads AS reads, writes, row_count
FROM #Queries;
```

我在我的系统中得到了如下输出（statement 列显示两行以适应页面）：

| Query_hash | duration | cpu_time | physreads | reads | writes | rowcnt |
|---|---|---|---|---|---|---|
| 31951613358041094 | 234514 | 139 | 22 | 13 | 0 | 500 |
| 31951613358041094 | 189375 | 219 | 21 | 12 | 0 | 400 |

请观察，基于相同模板的查询即使输入值不同，也获得了相同的查询哈希值。

最后一步是对 `#Queries` 表执行查询，按查询哈希值对事件进行分组，并按所需性能指标（在本例中为持续时间）之和进行倒序排序，如下：

```sql
SELECT
query_hash, SUM(duration) AS duration,
CAST(100. * SUM(duration) / SUM(SUM(duration)) OVER() AS NUMERIC(5, 2)) AS pct,
(SELECT TOP (1) statement
FROM #Queries AS Q2
WHERE Q2.query_hash = Q1.query_hash) AS queryexample
FROM #Queries AS Q1
GROUP BY query_hash
ORDER BY SUM(duration) DESC;
```

在我的系统上得到了以下输出：

| query_hash | duration | pct | queryexample |
|---|---|---|---|
| 1479172743199462596 | 3159476 | 58.13 | SELECT orderid, custid, empid, shipperid, orderdate<br>FROM dbo.Orders<br>WHERE custid = '0000000001' |
| 3195161633580410970 | 2267599 | 41.72 | SELECT orderid, custid, empid, shipperid, orderdate<br>FROM dbo.Orders<br>WHERE orderid = '20140101' |
| 1502019618400129514 | 7963 | 0.15 | SELECT orderid, custid, empid, shipperid, orderdate<br>FROM dbo.Orders<br>WHERE orderid >= 100001 |

我的示例工作负载中只有三个查询。自然地，在活跃的系统中，你会有很多查询。此时，你已经知道哪些查询在对整个系统的潜在影响方面更重要，需要调优。

完成后，运行以下代码删除临时表和扩展会话：

## 索引和查询信息及统计数据

SQL Server 通过动态管理视图（DMVs）和动态管理函数（DMFs）为你提供了有关索引和查询的丰富性能信息。本节描述我认为特别有用的对象。

在本章较早之前，我讨论了索引碎片。你可以查询 `sys.dm_db_index_physical_stats` 来获取索引的物理统计信息，包括碎片级别。例如，以下代码返回 PerformanceV3 数据库中所有索引的信息（所有表、所有索引和所有分区均为 NULL）：

```sql
SELECT database_id, object_id, index_id, partition_number,
av_fragmentation_in_percent, avg_page_space_used_in_percent
FROM sys.dm_db_index_physical_stats(DB_ID('PerformanceV3'), NULL, NULL, NULL, 'SAMPLED');
```

为了评估碎片情况，我检查两个指标：`avg_fragmentation_in_percent` 是乱序页的百分比（也称为逻辑扫描碎片），`avg_page_space_used_percent` 是百分比表示的平均页面填充率。

在生产环境中运行此查询时要小心，因为这些信息是在你查询此对象时实际收集的。`DETAILED` 模式开销最大，因为它涉及数据的全扫描。`LIMITED` 模式最廉，因为它只检查父索引页（非叶节点），但由于这个原因，它无法报告平均页面填充率。`SAMPLED` 扫描数据的 1%，是两者之间很好的折中。

当你遇到高水平的逻辑扫描碎片并发现它影响了你的查询性能时，解决方法是重建或重新组织索引。同样，如果空间过多或太少（会导致页拆分），请重建索引，并在需要时选择所需的填充因子。

使用 `ALTER INDEX <index_name>` 重建索引，如下：

```sql
ALTER INDEX <index_name> ON <table_name> REBUILD WITH (FILLFACTOR = 70 /*, ONLINE = ON */);
```

使用 `ALTER INDEX` 重新组织索引，如下：

```sql
ALTER INDEX <index_name> ON <table_name> REORGANIZE;
```

`REBUILD` 选项允许指定填充因子，其结果往往比 `REORGANIZE` 选项更有效；前者是离线操作，而后者是在线操作。如果你使用的是 SQL Server 企业版，可以通过添加 `ONLINE = ON` 将索引重建作为一种大部分在线的操作；然而，在线重建是一个耗时且更昂贵的操作，因此如果你可以承受一些停机时间，最好尽可能在线进行。

你需要能够识别哪些索引被使用得更频繁，哪些很少使用或几乎不使用。你不希望保留很少使用的索引，因为它们会对修改操作产生负面影响。SQL Server 在后台收集索引使用信息，并允许你通过名为 `dm_db_index_stats` 和 `dm_db_usage_stats` 的动态管理对象进行查询。`dm_db_index_operational_stats` 函数为你提供底级的 I/O、锁定和访问统计信息。例如，要获取 PerformanceV3 数据库中所有对象和分区的信息：

```sql
SELECT * FROM sys.dm_db_index_operational_stats(DB_ID('PerformanceV3'), NULL, NULL, NULL);
```

```sql
FROM (SELECT
QS.*,
SUBSTRING(ST.text, QS.statement_start_offset/2) + 1,
((CASE statement_end_offset
WHEN -1 THEN DATALENGTH(ST.text)
ELSE QS.statement_end_offset END
- QS.statement_start_offset)/2) + 1) AS query
) AS QS
FROM sys.dm_exec_query_stats AS QS
CROSS APPLY sys.dm_exec_sql_text(QS.sql_handle) AS ST
CROSS APPLY sys.dm_exec_plan_attributes(QS.plan_handle) AS PA
WHERE PA.attribute = 'dbid'
AND PA.value = DB_ID('PerformanceV3') AS DS
GROUP BY QS.query_hash
ORDER BY duration DESC;
```

该查询在以下时间生成了输出：

| sample_query | cnt | cpu | reads | logical_reads | duration |
| --- | --- | --- | --- | --- | --- |
| SELECT ... WHERE custid = 'C000010000' | 10 | 3155513 | 92 | 40305 | 3158897 |
| SELECT ... FROM dbo.Cust AS F | 8 | 2021766 | 1 | 110332 | 2929692 |
| SELECT ... WHERE orderid <= 100000 | 14 | 46365 | 0 | 25339 | 2805217 |
| SELECT ... WHERE orderid = '20140201' | 10 | 115054 | 0 | 215 | 2266620 |
| SELECT ... WHERE custid LIKE '%99999' | 1 | 1828461 | 0 | 4283 | 1887095 |

SQL Server 还为你提供了类似的视图，如 `sys.dm_exec_procedure_stats` 和 `sys.dm_exec_trigger_stats`，用于查询存储过程和触发器的性能统计。运行以下代码来在你的系统中查询这些视图：

- `FROM sys.dm_exec_procedure_stats`
- `FROM sys.dm_exec_trigger_stats`

SQL Server 2014 引入了一个名为 `sys.dm_exec_query_plans` 的新 DMV。此视图提供了实时的查询计划进度。它为活动查询计划中的每个算符返回一行数据，具体来说是为计划中的每个算符和线程返回，带有进度信息。它显示了估算成本以及到为止产生的实际计数、I/O、CPU 和经过时间信息、打开和关闭时间、算符活跃的第一次和最后时间、生成行的第一次和最后时间等。这是一个非常酷的功能。但请注意，你需要启用某种形式的实际查询计划才能查看报告信息。要实现这一点，你可以在 SSMS 中启用“包含实际执行计划”，运行 `STATISTICS PROFILE XML` 选项，或者使用带有 `query_post_execution_showplan` 事件的扩展事件会话，以及带有 `Statistics Profile Plan` 或 `Showplan XML Statistics Profile` 的跟踪。

例如，在 SSMS 中启用“包含实际执行计划”并运行以下查询：

```sql
SELECT 01.orderid, 01.orderdate, MAX(02.orderdate) AS mxdate
FROM dbo.Orders AS 01
INNER JOIN dbo.Orders AS 02
ON 02.orderid <= 01.orderid
GROUP BY 01.orderid, 01.orderdate;
```

要查看实时查询进度，可以在不同的查询窗中查询该视图，如下所示：

```sql
SELECT FROM sys.dm_exec_query_profiles;
```



我一直在等待像 SQL Sentry（他们开发了流行的 Plan Explorer 工具）这样的公司站出来，并根据视图中的信息，提供一个查询计划实时进度的图形化动画视图。谁知道呢，也许当你读到这些文字时，某家公司已经做到了。

# 临时对象

本节涵盖了如何将临时表和表变量作为辅助查询优化的工具使用。这些对象经常被误解，而这种误解往往会导致次优的解决方案。希望通过本节的信息，你将对这些对象有正确的理解，并能有效地使用它们。我将临时表和表变量统称为“临时对象”。

临时对象用于各种目的，而非与性能相关。例如，当你有一个流程需要设置某些中间结果集以供后续处理时，就需要此类对象。因为本章的重点是查询优化，我将主要讨论为了查询优化目的而使用此类对象。

在许多情况下，你会发现从查询优化的角度来看，使用临时对象是有益的。一种情况是你有一个代价昂贵的查询，它生成了一个很小的结果集，而你需要多次引用此结果，这是为了避免重复工作。另一种情况是帮助改进基数估算。SQL Server 使用统计信息对计划叶子节点进行基数估计，数据在计划中流动得越远，基数估计的质量就越可能下降。如果你有一个涉及大量表和大量操作的查询，并且在计划中观察到次优选择（这些选择连接到了不准确的基数估计），你可以提取工作的一部分（例如连接的子集），直到你在计划中看到问题出现的地方以及更多。

关于使用临时对象存在许多常见的误解。最古老的误解之一是人们认为表变量只存在于内存中。但实际上，它们和表一样，会产生磁盘活动。

有趣的是，技术似乎正在跟上这些误解。SQL Server 近期版本的某些改进可以减少或消除磁盘活动。例如，从 SQL Server 2014 开始，你可以将表类型定义为内存优化的（使用 `MEMORY_OPTIMIZED = ON` 选项）。当你声明这种类型的表变量时，它被表示为内存优化表。此功能是内存数据库引擎的一部分，详见第 10 章。

SQL Server 2014 的另一项改进（也回溯到了 SQL Server 2012）与 SQL Server 如何处理类似于 `SELECT INTO` 的激写入有关。通常，激写入会刷新页面以防止内存被新页面冲满。有了这项功能，当你在 tempdb 中执行操作时，激写入行为被放宽了，这在你创建并填充临时对象、对其进行查询然后将其删除时是有益的。

另一个关于表表达式和 CTE 的常见误解是人们直觉上认为当你使用表表达式时，如果有利，SQL Server 会将查询结果持久化到工作表中。理论上存在这种可能性，但事实是，到目前为止微软尚未向引擎引入此类功能。任何对表表达式的引用都会被展开，查询直接与底层对象进行交互。当你有一个昂贵的查询并需要多次与其结果集交互（即使是同一个查询）时，这一事实尤为重要。

在接下来的章节中，我将比较 SQL Server 支持的不同类型的临时对象。

**表 2-2 临时对象**

| 功能/对象类型 | 局部临时表 | 表变量 | 表表达式 (CTE) |
| --- | --- | --- | --- |
| 在 tempdb 中的物理表示 | 是 | 是 | 否 |
| 通常适用于需要查询一次或多次 | 多次 | 多次 | 一次 |
| 统计信息（直方图、密度向量） | 是 | 否 | 否 |
| 通常适用于表大小 | 大 | 小 | 任意 |
| 作用域/可见性 | 当前和内部 | 批 | 语句 |
| 外部事务的一部分/受外部事务影响 | 是 | 否 | 否 |
| 日志记录 | 支持事务回滚 | 支持语句回滚 | 否 |

对表表达式引用将被内联，昂贵的工作将被重复。这种行为很容易演示。通过开始运行以下代码来启用性能统计报告：

```sql
SET STATISTICS IO, TIME ON;
```

考虑以下查询，它计算每年的订单数量：

```sql
SELECT YEAR(orderdate) AS orderyear, COUNT(*) AS numbers
FROM dbo.Orders
GROUP BY YEAR(orderdate);
```

我在我的系统上获得了该查询的性能统计数据：逻辑读取 = 2,641，CPU 时间 = 861 ms，通过时间 = 289 ms。

你需要设计一个解决方案，对于每一年，返回订单数量最接近的年份，以及这两个年份之间订单数量的差异。为了实现这一点，你使用了以下查询（如果你不熟悉 `CROSS APPLY` 算符，可以在第 3 章找到详细信息）：

```sql
WITH C AS (
    SELECT YEAR(orderdate) AS orderyear, COUNT(*) AS numbers
    FROM dbo.Orders
    GROUP BY YEAR(orderdate)
)
SELECT C1.orderyear, C1.numbers,
       A.orderyear AS otheryear, C1.numbers - A.numbers AS diff
FROM C AS C1
CROSS APPLY (
    SELECT TOP (1) C2.orderyear, C2.numbers
    FROM C AS C2
    WHERE C2.orderyear <> C1.orderyear
    ORDER BY ABS(C1.numbers - C2.numbers)
) AS A
ORDER BY C1.orderyear;
```

检查图 2-58 所示的该查询的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_165_0.png)

**图 2-58** 使用 CTE 的执行计划显示昂贵的工作被重复了。

计划中的中间分支（嵌套循环 `Nested Loops` 算符的外部内部）代表了名为 C1 的 CTE 实例，它在外部查询的 `FROM` 子句中被引用。它涉及对 `Orders` 表的数据进行一次扫描、分组和聚合。计划底部的分支（嵌套循环 `Nested Loops` 算符的内部部分）代表了名为 C2 的 CTE 实例，它被 `TOP (1)` 子查询引用。该分支也涉及对 `Orders` 表的数据进行扫描、分组和聚合。由于外部表 C1 目前有五年份，这部分被激活了五次。总之，昂贵的工作被重复了六次。我获得了该查询的性能统计数据：逻辑读取 = 15,696（6 次扫描），CPU 时间 = 4763 ms，通过时间 = 1938 ms。

为了避免重复昂贵的工作，你应该将分组查询的结果持久化到临时表或表变量中。这里有一个使用表变量实现此点的示例：

```sql
DECLARE @T AS TABLE (
    orderyear INT,
    numorders INT
);

INSERT INTO @T(orderyear, numorders)
SELECT YEAR(orderdate) AS orderyear, COUNT(*) AS numorders
FROM dbo.orders
GROUP BY YEAR(orderdate);

SELECT T1.orderyear, T1.numorders,
       A.orderyear AS otheryear, T1.numorders - A.numorders AS diff
FROM @T AS T1
CROSS APPLY (
    SELECT TOP (1) T2.orderyear, T2.numorders
    FROM @T AS T2
    WHERE T2.orderyear <> T1.orderyear
    ORDER BY ABS(T1.numorders - T2.numorders)
) AS A
ORDER BY T1.orderyear;
```

这些语句的执行计划如图 2-59 所示。

第一个执行计划用于计算聚合值并将其写入表变量的代码。观察到，批处理中 100% 的成本（实际上也是 100%）都与此活动相关。第二个执行计划是针对表变量的查询。第二个查询访问了表变量六次，但它非常小，以至于这部分工作可以忽略不计。以下是我为该解决方案获得的性能统计数据：逻辑读取 = 2,622，CPU 时间 = 468 ms，通过时间 = 572 ms。这仅是 CTE 解决方案读取次数的六分之一，运行时间不足其三分之一。简而言之，请记住表表达式没有物理侧面；它们不会被持久化。当你查询它们时，SQL Server 会直接将工作翻译到底层的对象上。如果你需要将结果持久化到某处，你应该使用临时表或表变量。

**查询 1：查询成本（相对于批处理）：100%**

```text
INSERT INTO @T(orderyear, numbers) SELECT YEAR(orderdate) AS orderyear, COUNT(*) AS numbers FROM dbo.
```

| INSERT | Table Insert | Compute Scalar | Hash Match | Compute Scalar | Index Scan (Non-Clustered) |
|---|---|---|---|---|---|
| Cost: 0% | [@T] Cost: 0% | Cost: 0% | (Aggregate) Cost: 68% | Cost: 1% | [Orders].[PK_Orders] Cost: 31% |

**查询 2：查询成本（相对于批处理）：0%**

```text
SELECT T1.orderyear, T1.numbers, A.orderyear AS otheryear, T1.numbers - A.numbers AS diff FROM @T AS T1 CROSS APPLY ...
```

| SELECT | Compute Scalar | Nested Loops | Sort | Table Scan |
|---|---|---|---|---|
| Cost: 0% | Cost: 0% | (Inner Join) Cost: 0% | Cost: 39% | [@T1] Cost: 11% |

| SELECT | Compute Scalar | Nested Loops | Table Scan |
|---|---|---|---|
| Cost: 0% | Cost: 0% | (Top Sort) Cost: 39% | [@T2] Cost: 11% |

**图 2-59** 使用表变量的执行计划显示昂贵的工作没有重复。

第 2 章 查询调优 143

语句，通常优化器无法感知变量值。这同样适用于表变量。如果同一个批处理声明、填充并查询表变量，优化器会在表变量填充之前优化查询。因此，它不知道表的基数。与普通变量一样，如果你添加了 `RECOMPILE` 查询选项，查询将在表变量填充后进行优化；其基数对优化器是可见的。但每次执行代码时都会付出重新编译的成本。另一种让表基数可见的方法是将表变量作为表值参数传递给存储过程，并获取嗅探。

我将使用以下代码和相关的执行计划来演示表变量的基数估计：

```sql
DECLARE @T AS TABLE (
    col1 INT NOT NULL PRIMARY KEY UNCLUSTERED,
    col2 INT NOT NULL,
    filler CHAR(200) NOT NULL
);

INSERT INTO @T(col1, col2, filler)
SELECT n AS col1, n AS col2, 'a' AS filler
FROM TSQLV3.dbo.GetNums(1, 100000) AS Nums;

-- Query 1
SELECT col1, col2, filler
FROM @T
WHERE col1 <= 100
ORDER BY col2;

-- Query 2
SELECT col1, col2, filler
FROM @T
WHERE col1 <= 100
ORDER BY col2
OPTION(RECOMPILE);

-- Query 3
SELECT col1, col2, filler
FROM @T
WHERE col1 >= 100
ORDER BY col2
OPTION(RECOMPILE);
```

这三个查询的执行计划如图 2-60 所示。

**查询 1**

| 实际行数 | 100 |
|---|---|
| 估计行数 | 1 |
| SELECT 成本: 0% | 排序成本: 78% | 表格扫描 [@T] 成本: 22% |

**查询 2**

| 实际行数 | 100 |
|---|---|
| 估计行数 | 30000 |
| SELECT 成本: 0% | 排序成本: 50% | 表格扫描 [@T] 成本: 50% |

**查询 3**

| 实际行数 | 99901 |
|---|---|
| 估计行数 | 30000 |
| SELECT 成本: 0% | 排序成本: 50% | 表格扫描 [@T] 成本: 50% |

> **警告**：运算符在执行期间使用 tempdb 溢出，溢出级别为 1

**图 2-60** 使用表变量的查询计划。

该代码声明了一个名为 `@T` 的表变量，包含 col1、col2 和 filler 三列，并在 col1 上定义了一个名为 `PK_@T` 的非聚集索引。代码向该表变量中填充了 100,000 行数据。随后，该代码执行了三个查询。查询 1 过滤 `col1 <= 100` 的行。查询 2 过滤 `col1 <= 100` 的行并带有 `RECOMPILE` 选项。查询 3 过滤 `col1 >= 100` 的行并带有 `RECOMPILE` 选项。所有查询都按 `col2` 对结果排序。索引 `PK_@T` 可以支持过滤，但由于它不是覆盖索引，如果优化器决定使用它，将涉及回查。前两个查询具有选择性，受益于使用索引和少量查找的计划。最后一个查询是非选择性的，受益于扫描。

查看图 2-60 中的计划，我们看到所有三个计划都存在低效选择。在第一个计划中，优化器拥有表的基数信息，因此假设它非常小。结果是，它使用了扫描。在第二个计划中，得益于 `RECOMPILE` 查询选项，优化器获得了表的基数信息；但由于没有直方图且你使用了 `<=` 运算符，它估计有 30% 的匹配率（记得表 7-2 中神奇的估计值表吗？）。在第三个计划中——同样得益于 `RECOMPILE` 查询——优化器拥有表的基数信息，且由于你使用了 `>=` 运算符，这里也是 30%。然而，在这种情况下，30% 是低估的，导致操作溢出到 `tempdb`。

针对表变量基数的另一种可见方案是使用跟踪标志 `2453`，该跟踪标志在 SQL Server 2014 RTM CU3 以及 SQL Server 2012 SP2 及更高版本中可用。该跟踪标志指示 SQL Server 根据其用于普通表的相同阈值来触发重新编译。然而，它并不是在每次查询执行时显式强制重新编译，而是让你获得进一步的自动重新编译。当自动重新编译发生时，表的基数就会变得可用。你可以在此处关于此跟踪标志的详细信息：http://support.microsoft.com/kb/2952444/en-us。

如下所示代码所示，使用临时表倾向于获得更好的基数估计，从而获得更好的计划：

```sql
CREATE TABLE #T (
    col1 INT NOT NULL PRIMARY KEY UNCLUSTERED,
    col2 INT NOT NULL,
    filler CHAR(200) NOT NULL
);

INSERT #T(col1, col2, filler)
SELECT n as col1, n as col2, 'a' AS filler
FROM SQLV3.dbo.GetNums(1, 100000) AS Nums
OPTION(MAXDOP 1);

GO

-- Query 1
SELECT col1, col2, filler
FROM #T
WHERE col1 <= 100
ORDER BY col2;

-- Query 2
SELECT col1, col2, filler
FROM #T
WHERE col1 >= 100
ORDER BY col2;

GO

-- Cleanup
DROP TABLE #T;
```

两个查询的执行计划如图 2-61 所示。

你可以从计划中看到基数估计是准确的。如预期，第一个查询的计划执行了查找和回查。第二个查询的计划是一个并行计划，执行了扫描，且排序没有溢出到 `tempdb`。

**查询 1**

| 实际行数 | 100 |
|---|---|
| 估计行数 | 100 |

```text
SELECT Cost: 0%
Sort Cost: 4%
Nested Loops (Inner Join) Cost: 0%
Index Seek (NonClustered) [#T].[PK_#T__35700D30F46B9310] Cost: 1%
RID Lookup (Heap) [#T] Cost: 95%
```

**查询 2**

| 实际行数 | 99901 |
|---|---|
| 估计行数 | 99901 |

```text
SELECT Cost: 0%
Parallelism (Gather Streams) Cost: 19%
Sort Cost: 39%
Table Scan [#T] Cost: 41%
```



## 图 2-61 使用临时表的查询计划

我曾提到理论上涉及表的查询应该获得更好的基数估计，但实践中的情况并非总是如此。使用临时表或变量的复杂性在于 SQL Server 使用的某种缓存机制。正如书中之前讨论的，SQL Server 使用 `SG` 页来管理。临时对象是从空开始的，每当你的修改发生时，都需要在相应的 `SG` 上进行分配。你可以意识到，当同时创建许多临时对象时，可能会导致页锁竞争的瓶颈。

SQL Server 拥有一种旨在减少竞争的内部缓存机制。假设你执行一个使用临时表或表变量的存储过程。当存储过程结束时，临时对象通常会被销毁。

我说的就这么多。Paul White 提供了以下两个链接：

- http://sqlblog.com/blogs/paul_white/2012/08/15/temporary-tables-in-procedures.aspx
- http://sqlblog.com/blogs/paul_white/2012/08/17/temporary-object-caching.aspx

同样地，假设你有一个触发器，在某些条件下，你需要从触发器中执行回滚（`rollback`）。但你需要保存来自插入（`inserted`）和删除（`deleted`）表中的信息。如果你执行了回滚，插入和删除表中的所有数据都会消失。如果你先将插入和删除表中的数据复制到目标表，然后执行回滚，那么到目标表的复制操作将被撤销。解决方案是在执行回滚之前，将插入和删除表中的数据复制到表变量（`table variables`）中。然后执行回滚，并在回滚后从表变量中恢复数据。

## 基于集合的方法与迭代方案

人们在需要解决查询任务时面临的共同困境之一，是在解决方案中使用基于集合的方法还是基于迭代的方法。关系模型在某种程度上基于数学集合论。你通过应用基于集合论的原理，使用基于集合的方法来解决任务。以下是集合论创立基格奥尔格·康托尔（Georg Cantor）对“集合”的定义：

> 我们所说的“集合”，是指我们感知或思维中任何由确定的、不同的对象 m（称为 M 的“元素”）构成的整体 M。
> —— Joseph W. Dauben, Georg Cantor (普林顿大学, 1990)

对我来说，以输入表为 a 的基于集合的解决方案在结果的正确性上不对数据的物理顺序做任何假设。你可以使用 T-SQL 查询实现这种方法，而无需迭代。相反，迭代方案一次处理一行，并且可以依赖数据的顺序。你可以使用游标（`cursor`）机制或带有 `TOP (1)` 查询的循环来一次处理一行。

有很多原因导致我通常倾向于将基于集合的方法作为默认，并且仅在特殊情况下考虑迭代方法。其中一个原因是哲学层面的，另一个是实务层面的。哲学维度是，我觉得基于深厚数学基础的方法可能会产生更稳定、更健壮的解决方案。关系模型之所以存在多年，可能因为它基于深厚的数学基础，而不像计算领域的许多其他更侧重于运动且往往较短的。

实务层面的维度是，与其他编程语言中的迭代结构相比，T-SQL 中的迭代结构效率非常低。例如，T-SQL 的 `WHILE` 循环比 C# 中的循环要慢得多。同样，使用 T-SQL 游标的速度比使用 .NET 中的 `SQLDataReader` 对象慢得多。因此，T-SQL 基于集合的解决方案优于 T-SQL 迭代方案。

有趣的是，SQL Server 在执行 T-SQL 基于集合的解决方案的查询计划时，其执行模型终究是迭代的。当 SQL Server 执行查询计划时，操作符执行迭代（因此，它们也被称为迭代器）来一次处理一行，但 SQL Server 用于执行这些迭代的语言并不是 T-SQL；而是某种在应用这些操作时高效的低级语言。

在特殊情况下考虑迭代方案，即当优化器未能很好地优化我的基于集合的解决方案，并且我觉得已经耗尽了所有的调优选项时。这时，通过实现基于 CLR 的迭代方案而不是基于 T-SQL 的方案，我可以获得更好的性能。

为了演示一个 T-SQL 迭代方案相对于基于集合方案有多昂贵，我将使用一个带有分组和聚合的任务作为示例。为了让问题比基础的分组更有趣，我还会添加一个过滤维度。该任务涉及 `PerformanceV3` 数据库中的 `Shippers` 和 `Orders` 表。使用以下代码向示例数据添加一些发货商和订单：

```sql
SET NOCOUNT ON;

USE PerformanceV3;
```

```sql
INSERT INTO dbo.Shippers(shipperid, shipper)
VALUES ('B', 'Shipper_B'),
       ('D', 'Shipper_D'),
       ('F', 'Shipper_F'),
       ('H', 'Shipper_H'),
       ('X', 'Shipper_X'),
       ('Y', 'Shipper_Y'),
       ('Z', 'Shipper_Z');
```

```sql
INSERT INTO dbo.Orders(orderid, custid, empid, shipper, orderdate)
VALUES (1000001, 'C000000001', 1, 'B', '200910101'),
       (1000002, 'C000000001', 1, 'D', '200910101'),
       (1000003, 'C000000001', 1, 'F', '200910101'),
       (1000004, 'C000000001', 1, 'H', '200910101');
```

任务是识别处理过 2010 年之前的订单但此后未处理过任何订单的发货商。该任务的大部分工作是计算每个发货商的最大订单日期。符合条件的发货商是最大订单日期在 2010 年 1 月 1 日之前的那些。对于此，最佳索引是 `Orders` 表上的非聚集索引，键列列表为 `(shipper, orderdate)`。运行以下代码创建索引：

```sql
CREATE NONCLUSTERED INDEX idx_nc_sid_0 ON orders(shipperid);
```

（注：原文后续部分存在大量重复的 OCR 错误，已根据逻辑进行了清理处理。）

以下是针对我们的任务的一个简单基于集的解决方案（我们称之为基于集的解决方案 1）：

```sql
SELECT shipperid
FROM dbo.Orders
GROUP BY shipperid
HAVING MAX(orderdate) < '20100101';
```

该解决方案对 `Orders` 表执行了基本的分组查询。查询根据 `shipper ID` 对行进行分组，并过滤出最大订单日期在 2010 年之前的运货组。该查询的执行计划如图 2-63 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_177_0.png)

**图 2-63** 基于集的解决方案 1 的查询计划。

优化器创建了一个顺序扫描非聚集索引的计划。然后，计划根据订单应用流聚合（`stream aggregate`），而不需要显式对行进行排序。计划过滤了满足 `HAVING` 谓词的行。我在系统中获取了该查询的性能统计数据：逻辑读取 = 2,487，CPU 时间 = 375 ms，经过时间 = 602 ms。

注意，该解决方案的运行时间仅为半秒。而之前的解决方案完成花费了 17 秒。你会发现该解决方案的计划使用了与基于游标的解决方案相同的基于节点的算法。两个解决方案扫描了相同数量的页面。游标解决方案如此缓慢，主要是因为 T-SQL 中昂贵的迭代和游标取值。

## 通过查询修订进行查询调优

基于集的解决方案 1 比基于游标的解决方案高效得多。然而，如果它仍然不够高效呢？也许这只是一个包含 1,000,000 行数据的小规模测试环境，假设生产环境有 100,000,000 行。

图 2-63 计划中承担大部分工作的两个算子是索引扫描（`Index Scan`）和流聚合（`Stream Aggregate`）算子。这两者都具有线性扩展性，因为它们的成本与行数成正比。因此，整个计划具有线性扩展性。为了讨论方便，我们简化一下：如果处理 1,000,000 行时查询需要半秒钟完成，那么它大约需要 50 秒。假设它需要在三秒内完成。这就是使用行存储索引（`row-store indexes`）能做到的极限。现在假设在此使用列存储索引（`columnstore indexing`）对你来说并不可。此时，你应该评估可能产生更优计划的查询修订。

修订背后的想法是，优化器并非完美。不要误会；我并不是想低估它的能力。但现实是，在许多情况下，执行相同逻辑任务的不同查询会获得不同的执行计划。这与多个原因有关。优化器限制了优化过程以防产生适得其反的结果。计算机对涉及表的大小设有基于成本和时间的阈值。一旦达到任何一个阈值，优化过程就会停止，优化器会选择到目前为止生成的最佳计划。对于不同的查询，优化过程的起点是不同的，在每个情况下，其停止点可能位于不同的计划集之后。此外，查询结构的使用可能会在优化选项方面施加某些限制。

简而言之，如前，执行相同逻辑任务的不同查询可能会获得不同的计划。因此，你必须将修订视为一种查询调优工具。如果你想提高查询调优技能，应该在这个领域投入时间。你可以学习优化器倾向于如何处理不同的查询结构，以及什么条件的变化会使优化器改变其选择。这样，当你调优查询并希望对计划产生某种特定效果时，你就知道该尝试什么，而不是盲目摸索。我将在我们的示例任务中演示这种技术，并在全书中展示更多示例。

第一步是识别现有计划中最昂贵的部分。显然，那部分是对非聚集索引的全表扫描。

第二步是尝试识别一种更高效的策略，即使你还不知道如何实现。考虑到 `Shippers` 表有较少的 `shipper ID`，扫描策略并不是最优的。更优的策略是扫描 `Shippers` 表，然后对于每个运货商在 `Orders` 的非聚集索引上执行提取（`seek`）。这种策略的巧妙处在于，它的扩展性取决于运货商的数量，而不是订单的数量。只要运货商的数量很多，索引层级就决定了操作次数。当行数增加时，索引层级不会发生显著变化。例如，对于 1,000,000 行，索引会有三层，而对于 100,000,000 行会有四层。

第三步是设计一个给你所需策略的查询。你可以首先尝试以下查询，看看优化器是否会处理单个运货商的最大订单日期：

```sql
SELECT MAX(orderdate) FROM dbo.Orders WHERE shipperid = 'A';
```

该查询的计划如图 2-64 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_178_0.png)

**图 2-64** 单个运货商的查询计划。

计划在非聚集索引的 `shipper A` 右侧执行提取，然后进行范围扫描。`Top` 算子只请求一行。因此，范围扫描没有理由继续执行。过滤后的行 `order date` 被交给流聚合算子，该算子返回最大订单日期。该查询的执行在系统中涉及逻辑读取。

现在你知道优化器应用了单个运货商的所需策略，下一步是从 `Shippers` 表获取相同的，并调用相关聚合子查询来返回当前运货商的日期，如果该日期在 2010 年之前。这是实现这种方法的完整解决方案（称为基于集的解决方案 2）：

```sql
SELECT shipperid
FROM dbo.Shippers
WHERE (SELECT MAX(orderdate)
       FROM dbo.Orders AS O
       WHERE O.shipperid = Shippers.shipperid) < '20100101';
```

人们希望该查询的计划将通过扫描 `Shippers` 表来获取 ID，然后对于每个运货商执行循环（如图 2-64 所示）。但事实并非如此，如图 2-65 执行计划所示。

![](img/bdc38aa36f6e2987d913ee5381474711_179_0.png)

**图 2-65** 基于集的解决方案 2 的查询计划。

如你所示，优化器选择了一个执行非聚集索引全扫描的计划，这正是你想在该查询中避免的。SQL Server 报告了该查询在我系统上的性能统计数据：逻辑读取 = 8+2487，CPU 时间 = 438 ms，经过时间 = 524 ms。

事实证明，当优化器看到示例中的标量聚合查询时，它首先在内部将其展开（`unnests`），转换为连接形式。这样优化器就可以评估不同顺序访问表的计划。问题是优化器在这里需要做许多决策，例如使用何种访问方法、使用何种连接算法、使用何种聚合算法等。搜索空间变得巨大，如果优化器尝试探索所有计划，优化过程将变得非常长以至于适得其反。看起来优化器没有探索到最优计划。

通常情况下，优化器执行的子查询展开会导致更高效的计划，但在本例中，它导致了低效的计划。因此，在这种情况下你需要防止优化器嵌套查询。如果 SQL Server 支持指示优化器不要嵌套的提示（`hint`）将很有用，遗憾的是没有这样的提示。奇怪的是，有一种间接方法可以达到相同目的。当子查询使用 `TOP` 过滤器时，SQL Server 不会嵌套它，因为在某些情况下，这种展开可能会改变查询的含义。例外是内部查询使用了 `TOP (100 PERCENT)`；在这种情况下，SQL 直接忽略 `TOP` 选项，因为知道无意义。在你的查询中，如果你将子查询改为使用 `TOP (1)` 而不是 `MAX`，你就能防止意外的展开。这是修订后的解决方案（称为基于集的解决方案 3）：

```sql
SELECT shipperid
FROM dbo.Shippers AS S
WHERE (SELECT TOP (1) orderdate
       FROM dbo.Orders AS O
       WHERE O.shipperid = S.shipperid
       ORDER BY orderdate DESC) < '20100101';
```

该查询的计划如图 2-66 所示。

![](img/bdc38aa3f6e2987d913ee5381474711_180_0.png)

**图 2-66** 基于集的解决方案 3 的查询计划。

这一次，计划正是你所需要的。它从扫描 `Shippers` 表开始，这只需要几次读取。这扫描了 12 个 `shipper ID`。然后，对于每个运货商，循环在 `Orders` 的非聚集索引上执行提取，以检索当前运货商的最大订单日期。然后过滤器检查 `shipper ID`，如果相应的日期在 2010 年之前，否则丢弃它。这里是我获取的该查询的性能统计数据：针对 `Shippers` 的逻辑读取 = 2，针对 `Orders` 的访问次数 = 12，逻辑读取 = 36，CPU 时间 = 0 ms，经过时间 = 12 ms。

以下是另一种获取高效计划的解决方案（称为基于集合的解决方案 4）：

```sql
SELECT shipperid
FROM dbo.Shippers AS S
WHERE NOT EXISTS
      (SELECT * FROM dbo.Orders AS O
       WHERE O.shipperid = S.shipperid
         AND O.orderdate >= '20100101')
  AND EXISTS
      (SELECT * FROM dbo.Orders AS O
       WHERE O.shipperid = S.shipperid);
```

你针对 `Shippers` 表执行了该查询。该过滤器使用带有相关子查询的 `NOT EXISTS` 谓词，确保外部的 shipper 没有在 2010 年或之后处理过订单。该过滤器还使用了带有相关子查询的 `EXISTS` 谓词，以确保外部的 shipper 至少处理过一个订单。该查询的计划如图 2-67 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_181_0.png)

**图 2-67** 基于集合的解决方案 4 的查询计划。

基于集合的解决方案 3 的计划，该计划也从扫描 `Shippers` 表开始，返回了 12 个 shipper ID。对于这 12 个 shipper 中的每一个，第一个循环在非聚集索引上应用查找，以检查查询中的 `NOT EXISTS` 谓词。对于每个（顺序可能是 0 到 12 个），第二个循环在非聚集索引上应用查找，以检查查询中的 `EXISTS` 谓词。此计划比基于集合的解决方案 3 的计划稍贵一些，但它仍然非常高效，且扩展性与 shipper 的数量相关。我为该查询获取的性能统计数据如下：对 `Shippers` 的逻辑读取 = 2，对 `Orders` 的逻辑读取 = 19，CPU 时间 = 0 ms，通过时间 = 9 ms。

我为该任务提供了四种解决方案，每种解决方案都生成了不同的执行计划。第一个是最简单且直观的，但不是效率最高的。剩下的——即调整查询的尝试——不仅仅是尝试许多解决方案直到获得高效方案。而是在于理解第一个解决方案中的低效之处，并在思考高效计划应该什么样子的之后，应用修改以对计划产生特定的效果。这个练习的重点是强调开发根据查询修改来调优查询技能的重要性。

完成后，运行以下代码以关闭会话中的 I/O 和时间统计：

```sql
SET STATISTICS IO, TIME OFF;
```



此时，建议你重新运行书籍源码中的 `PerformanceV3.sql` 脚本文件，以重新创建一个干净的示例数据库。

# 并行查询执行

过去几年计算机硬件的几个特征是几乎每个指标的巨大增长：更多、更快的存储器，更多、更快的主内存，最重要的是有更多、更强大的 CPU。数据库也发生了一些变化，数据量正在迅速增长。同时，用户对数据分析的需求日益增长，但他们仍然期望在点击按钮后获得秒级的查询结果和报告。

由于强大的计算能力，处理海量数据自然变得更容易了，但最好的性能改进是通过使用专门利用并行性、查询执行和调度内部的特殊算法来实现的。这些算法的关键是将数据分成较小的块，这些块可以同时分布到任何处理器核心上。此类技术被称为并行查询执行、查询内并行或简称为并行，SQL Server 拥有一套精细且成熟的系统来处理这类工作。

本节深入探讨了 SQL Server 的并行查询能力，重点关注查询优化、查询执行和调度内部的关键方面。理解这些领域将使你不仅能够分析查询和性能特征，还能根据你的查询和工作负载适时地启用或限制并行。

> 注意 本节中的示例使用了 `AdventureWorks2014` 示例数据库。你可以从 CodePlex 获取该数据库：https://msftdbproductions.codeplex.com/releases/view/12550。

## 查询内并行如何工作

并行处理——将工作拆分到多个处理器核心上的行为——可以通过不同的方式实现。最常见的模型如下：

- 流水线模型，其中每个核心负责一个操作，数据从一个核心传递到另一个核心。（想象汽车工厂，一个人负责安装门把手，另一个人安装窗户，依此类推。）
- 流式模型，其中每个核心负责一组数据并执行所需的操作。（这种模型类似于工厂，每辆车都由一个人独立完成。）

尽管流水线模型在直觉上看起来更好，特别是应用于汽车和人类工人时，但 SQL Server 和许多其他数据库产品是基于流式模型的。计算机处理器与人类不同，只要数据已经在处理器的本地缓存中，就能快速高效地切换任务。从主内存（或更糟糕的存储器）获取数据的代价比执行新任务贵几个数量级。这意味着，在将数据移动到其他处理器或内存位置之前，对其进行尽可能的操作几乎是有利的。

流式模型也比流水线模型扩展得好得多，特别是当数据增长时。SQL Server 的流式模型涉及使用各种算法（根据场景选择）将行尽可能均匀地分布到各个核心。考虑一种情况：查询计划只有三个操作，但有数十亿行数据需要应用这些操作。在简单的流水线模型中，查询计划可能只能使用三个处理器，但在流模型计划中，理论上可以扩展到数百万或数十亿处理器核心。自然，服务器配备的处理器核心数量有现实限制，而且在大规模扩展数据集时存在收益递减点。这种灵活性在较小的情况下很有帮助，是数据库系统常用流式模型的关键原因之一。

## 查询计划中并行的基础

并行查询计划的概念有点不准确。查询计划将是完全串行的——使用单个工作线程处理——或者它包含一个或多个并行分支，即计划中使用多个线程处理的区域。这是一个重要的区别，因为查询处理器有能力将多个并行流合并为单个流，或从单个流创建并行流。这些操作可以在给定的查询计划中执行任意次数，这意味着一个计划可以拥有许多并行区域与许多串行区域交织。

计划中的每个并行区域将与计划中的其他并行区域使用相同数量的线程。每个区域的线程数被称为并行度 (DOP)。

确定给定算符是否在并行区域内可以通过查看图形计划中的图标来完成。并行区域中的算符将带有带箭头的圆圈，如图 2-68 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_184_0.png)

**图 2-68** 并行区域中的算符带有带箭头的圆圈。

**重分区流 (Repartition Streams)** 该算子的作用是摄取多个并行流，并将行重新分配到不同的线程，其使用的方案与上游并行区域分配行时的方案不同。因此，无论计划是从数据还是逻辑角度来看，该算子都限制了并行区域的开始和结束。该算子的另一种理解方式是连接两个相邻的并行区域。

图 2-69 显示了一个包含所有类型交换（Exchange）算子的查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_185_0.png)

**图 2-69** 使用所有类型 Exchange 算子的查询计划。

图 2-69 中的计划经过编辑和注释，突出了由各种 Exchange 算子定义的三个并行区域（以及两个串行区域）。并行区域 1 从逻辑角度看从聚集（Gather）算子开始。位图（Bitmap）算子的输入来自一个分布流（Distribute Streams）算子，该算子通过一个包含 Top值（Top）算子的串行区域限制了该区域。并行区域 3 馈送该串行区域，并被聚集流（Gather Streams）算子限制。计划中的最后一个并行区域——区域 2——由重分区流（Repartition Streams）算子限制，并与区域 1 直接相邻，中间没有串行区域。

从线程的角度来看，该计划在其并行区域将使用 DOP * 2 个工作线程，加上串行区域中的一个父线程。它之所以能够使用比 DOP 一倍的工作线程，而不是每个线程一个线程，是因为分配给区域 3 的线程可以被区域 2 重用。

再次，遵循计划的逻辑顺序，如果 DOP 为 4，区域 1 将开始并分配四个工作线程。哈希匹配（Hash Match）算子在它的构建侧（包含并行区域 3 的一侧）上运行。因此，在分配给区域 3 的四个线程完成所有工作之前，该算子将一直运行且不会返回。到此为止，这四个线程将用于用于处理区域 2。

仅看并行查询计划可能很难想象到底发生了什么，但当将其转换为略有不同的图形形式时，情况就变得容易了。考虑图 2-70 所示的计划片段。

![](img/bdc38aa36f6e2987d913ee5381474711_186_0.png)

**图 2-70** 仅包含一个排序（Sort）算子的并行区域。

图中所示的计划片段是一个完整的并行区域，仅包含一个排序算子。如果图形计划视图是根据实际发生的情况渲染的，且计划的 DOP 为 4，那么图像看起来可能类似于图 2-71 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_186_1.png)

**图 2-71** 并行是如何工作的。

对于一个 DOP 为 4 的计划，聚集流（Gather Streams）算子将分配四个工作线程。这些工作线程中的每一个将生成一个排序（Sort）算子，而每个排序算子将向分布流（Distribute Streams）算子请求行。重要的一点是，每个排序算子都是独立运行的，完全不知道其他算子正在做什么。由于这种设计，DOP 可以任意放大或缩小，计划仍然可以以相同的方式运行，只是速度快慢之分。

## Exchange 算子内部

上一节从工作线程和行流的角度关注了 Exchange 算子，但它留下了一个核心问题没有回答：为什么 Exchange 被称为交换（Exchange）？

每个 SQL Server 查询计划算子内部有两个逻辑接口：消费者接口（consumer interface），用于从上游获取行；以及生产者接口（producer interface），用于向下传递行。在大多数算子中，这些接口在同一个线程上处理，但在 Exchange 的情况下，会涉及多个线程。Exchange 算子的任务是从消费者侧的线程获取行，并将这些线程交换为生产者侧不同的线程。这就是名称的由来。

实际的交换过程发生在名为 CXPacket 的数据结构内部，其中 C 代表一个 C++ 类（实现该结构），而 XPacket 代表交换包（exchange packet），这是该结构的实际名称。当算子中消耗行时，它们被存储在交换包中。当包被填充后，它们就会跨越交换传递给生产者侧等待的线程。交换每侧线程的数量取决于交换的类型：聚集流（Gather Streams）算子在消费者侧每侧有一个 DOP 线程，在生产者侧有一个；分布流（Distribute Streams）算子在消费者侧有一个线程，在生产者侧有 DOP 线程；而重分区（Repartition）算子在交换的每侧都有 DOP 线程。

如果你花时间监控 SQL Server 等待统计信息，无疑遇到过 CXPacket 等待类型。这种包之所以这样命名，是因为涉及到多个线程并行等待 CXPacket 数据结构。设置此等待的线程通常在等待交换生产者侧的行。然而，如果例如在线程开始生成行之前需要某些同步操作，消费者侧的线程也可以设置该等待类型。

## 行分布策略

并行查询计划必须涵盖广泛的用例。为了增加查询优化器可用的灵活性，在分布（Distribute）或重分区（Repartition）交换的生产者侧，有五种跨算子分配分配的选项：

- **哈希 (Hash)**：这是最常见的分配方案，它涉及根据哈希函数的结果为每行分配一个接收者（consumer）。该方案通常用于在工作线程上对齐逻辑组中的行。例如，如果哈希函数应用于 `ProductID` 列，所有具有相同产品 ID 的行都将被分配到同一个工作线程。如果查询包含按产品 ID 的聚合分组（group by product ID），每个线程将能够独立处理多个产品的聚合。

- **轮询 (Round Robin)**：在这种方案中，交换消耗的行将分配给生产者侧等待的第一个线程，第二行将分配给第二个等待线程，依此类推，直到所有线程都收到了一行。分配将重新从第一个线程开始。该方案的一个示例通常用于嵌套循环（Nested Loops）算子的外部，其中每行都独立地作为循环的内侧工作。

- **广播 (Broadcast)**：此方案将从消费者侧的所有行发送到生产者侧的所有线程。它仅在估计行数较少且希望整组行都出现在每个线程上时使用——例如，为了构建哈希表。

- **按需 (Demand)**：该方案的独特之处在于，它涉及生产者侧线程根据请求接收行。目前，这仅用于分区表。

- **范围 (Range)**：在这种方案中，每个线程被赋予一个唯一且不重叠的键范围来工作。该方案用于构建索引时。

要查看 Exchange 算子使用的分布方案和相关信息，可以将鼠标悬停在算子上直到工具提示出现；或者最好点击 F4 获取属性窗口，如图 2-72 所示。

此图显示选定的分布流（Distribute Streams）算子使用哈希分区，哈希函数将应用于 `AdventureWorks2014.SalesOrderDetail` 表的 `SalesOrderID` 列。

属性窗口对于读取并行计划还有另一个有用功能：当查看实际（而非估计）查询计划时，它会显示计划中每个算子（包括 Exchange 以及其他）每个工作线程处理的行数。这些信息如图 2-73 所示。

通过展开 Actual Number Of Rows 项下的对话框可以看到每个线程的行数。此处所示计划 DOP 为 6，意味着每个并行区域有 6 个工作线程。每个线程处理了 100 多行，但某些线程处理的比其他线程多；对于只有 1000 行的计划，这可能不是主要问题，但对于更大的计划可能会导致性能问题。

这里的线程 0 代表父线程（也称为分配器线程或协调线程）。这是在串行区域中活动并生成并行工作线程的线程。

这里不是为了处理行，而是为了控制工作线程的生命周期；因此，它没有显示在该特定算符上完成了任何工作。

## 并行排序与合并交换

并行的主要目标显然是将昂贵的工作单元拆分为更小的部分，以便在多个 CPU 上并发运行。人们可能会预期，如果某个给定操作在单个处理器上运行需要 1000 毫秒，那么在四个处理器上运行可能只需要 250 毫秒。这种逻辑有些天真，但它可能是正确的——这取决于最初拆分工作的成本有多高，以及将结果合并回单个流以便调用者消耗的成本有多高。

惊讶的是，在某些情况下，将工作单元拆分为更小部分所带来的性能提升甚至比并发线程数量预期的还要大。换句话说，对于这类操作，1000 毫秒的示例在四个处理器上运行可能只需要 200 毫秒，而不是 250 毫秒。这种方法适用于那些在数学上呈非线性扩展的操作；对于大小为 N 的给定工作负载，这类操作在大小为 N * 10 的工作集上表现会比差 10 倍。

一种操作（也是数据库场景中最常见的）是数据排序。所有排序算法都以 N * LOG(N) 的速度扩展。这不是一个非常陡峭的曲线：包含 100,000,000 个元素的集合排序时间仅比 10,000,000 个元素的集合多 11 倍，与线性扩展相比差异仅为 10%。然而，在数据库性能领域，每一比特都至关重要。因此，在查询处理器中利用这类数学收益可能非常有意义。

如果一组大量行需要根据给定键进行排序，查询计划会将排序放入并行区域。如果对多个列进行排序，数据将使用哈希方案进行分布，以保持所有值聚集。

一旦数据完成排序，需要在随后的串行区域中保留顺序；如果数据无法被使用，那么并行排序的意义不大。查询计划将使用 Gather Streams（汇集流）算符的特殊变体，称为合并交换（merging exchange）。合并交换消耗多个相同顺序的数据流，并输出一个保持相同顺序的数据流。这是通过简单的合并算法实现的：如果数据按 `ProductID` 升序排序，则从每个输入流中读取行并记录最小的 `ProductID`。现在从每个流中读取行，直到该 ID 不再有行，此时将记录下一个最小的 ID。现在读取该 ID 的行，依此类推，从而保持输入顺序。

图 2-74 显示了以下查询的计划片段：

```sql
SELECT TOP(1000)
  UnitPrice
FROM Sales.SalesOrderDetail
ORDER BY
  UnitPrice DESC;
```

| Order By | [AdventureWorks2014].[Sales].[Sa |
|---|---|
| n Ascending | False |
| Column Reference | [AdventureWorks2014].[Sales].[Sa |
| Column | UnitPrice |
| Database | [AdventureWorks2014 |
| Schema | [Sales |
| Table | SalesOrderDetail |
| Output List | [AdventureWorks2014].[Sales].[Sa |

![](img/bdc38aa36f6e2987d913ee5381474711_190_0.png)

图 2-74 使用合并交换的并行排序。

这里的 Gather streams 算符包含一个 Order By 属性，表明它是合并交换。数据将根据 `AdventureWorks2014.SalesOrderDetail` 表中的 `UnitPrice` 列进行顺序输出，在该计划中，该列与上游 Sort 算符使用的列相同。

## 部分聚合

在考虑查询计划时，最考虑的因素通常不是计划中有多少个算符。大多数算符一次只处理一行，而且速度非常快。这实际上是 SQL Server 流式查询处理器的核心意义。

重要的算符的数量（相对于批处理的比例有多少个）：100%

当跨线程移动数据时，早期聚合的优势更加明显。这是因为减少了被移动的行数。性能提升出现在行数很多的计划中，而这是非常昂贵的。或者，考虑一种不提前聚合的情况。因为这需要将行移动到新位置。

并行扫描（Parallel scan）是以数据页为单位而非按行运行的，特别是当查找表较小时，某些情况下数据页的数量少于工作线程的数量。在这种情况下，某些工作线程会被分配，但没有工作可做，这不仅意味着分配这些线程浪费了时间，而且意味着剩余的每个线程执行的工作都比预期的要多。

为了消除这种情况，SQL Server 实现了一种名为“少数外层行”（few outer rows）的特殊优化。当使用并行扫描来填充嵌套循环（Nested Loops）算子的外侧时，就会发生此优化。在这种情况下，每个线程代表了在循环内侧需要执行的工作，理想情况下，这些工作应该尽可能在线程之间均匀分布。此外，如果优化器检测到行数太少，会在并行扫描之后立即在计划中插入一个重分区流（Repartition Stream）运算符。

图 2-77 显示了针对以下查询的该优化结果：

```sql
SELECT
  p.ProductID,
  th0.TransactionID
FROM Production.Product AS p
CROSS APPLY (
  SELECT TOP(1000)
    th.TransactionID
  FROM Production.TransactionHistory AS th
  WHERE
    th.ProductID = p.ProductID
  ORDER BY
    th.TransactionID
) AS th
ORDER BY
  th0.TransactionID;
```



![](img/bdc38aa36f6e2987d913ee5381474711_193_0.png)

图 2-77 如果没有“少数外层行”优化，六个线程中只有两个会工作。

在执行计划中，对 `Product` 表的扫描导致两个工作线程接收到了行。这是因为索引中只有两个数据页；该表只有 504 行。查询优化器预见到了这一点，并在扫描后直接插入了重分区流运算符。该运算符将使用轮询方案对行进行重分区，从而在工作线程之间产生完美的平衡，如图 2-78 所示。

## 并行哈希连接和位图

鉴于并行查询计划倾向于处理大量行集，且哈希匹配设计用于连接大量行集，因此在并行查询计划中使用哈希连接运算符是非常常见的。因此，对这些连接进行尽可能的优化是有意义的。

通常的连接算法涉及对外层（构建侧）键进行哈希处理，对每个内层（探测侧）键进行哈希处理，在哈希表中找到匹配的桶，最后遍历桶的链表以找到匹配的行。

在并行执行计划中，可以发生一种优化，每个线程都会构建一个包含哈希表中桶数量的位图。如果相应的哈希桶中没有行，则位掩码中的位将为 0，如果哈希桶中有行，则为 1。在探测阶段，查询处理器不必直接进入桶，而是可以先通过位图发现哈希表中是否存在潜在的行。这可以极大地减少哈希连接查询的成本和开销，特别是在探测侧行有很大比例的与构建侧行不匹配的情况下。

以下查询在计划中使用位图进行了优化，如图 2-79 所示：

```sql
SELECT *
FROM (
  SELECT sh.*, sd.ProductID
  FROM (
    SELECT TOP(1000) *
    FROM Sales.SalesOrderDetail
    ORDER BY SalesOrderDetailId
  ) AS sd
  INNER JOIN Sales.SalesOrderHeader AS sh ON sh.SalesOrderId = sd.SalesOrderId
) AS s;
```

![](img/bdc38aa36f6e2987d913ee5381474711_194_0.png)
![](img/bdc38aa36f6e2987d913ee5381474711_195_0.png)

### 图 2-7 并行计划中的哈希位图。

此类计划中的位图与后续的哈希匹配运算符基于相同的哈希键。

位图优化的进一步增强可能发生在数据仓库查询中，查询优化器确定这些查询是星型连接（即一个或多个维度连接到事实表）。如果发生了星型连接优化，每个维度都将被扫描，并在内部合并成一个单一位图（和表），该位图可以在探测侧作为单个过滤器使用。这种方法比为每个维度单独探测哈希表要快得多。

## 并行性与分区表

在涉及具有大量分区的表的执行计划中，查询优化器可能会选择分配线程并单独处理每个分区，而不是使用典型的并行扫描机制顺序扫描整个分区集。这种特殊情况涉及需求分布方案；每个线程一次可以处理一个分区，并在第一个分区完成后请求另一个分区来工作。通过这种方式，工作在工作线程之间得到了良好的平衡，即使某些分区的行数少于其他分区。

要看到这一操作，需要一个分区表并需要进行一些设置。以下代码在 `tempdb` 中创建了分区函数、分区方案和一个表：

```sql
USE tempdb;
GO

CREATE PARTITION FUNCTION pf_1 (INT)
RANGE FOR VALUES
(
    25000, 50000, 75000, 100000,
    125000, 150000, 175000, 200000, 225000, 250000, 275000, 300000, 325000, 350000, 375000, 400000, 425000, 450000, 475000, 500000, 525000, 550000, 575000, 600000, 625000, 650000, 675000, 700000, 725000, 750000, 775000, 800000, 825000, 850000, 875000, 900000, 925000, 950000, 975000, 1000000
);

CREATE PARTITION SCHEME ps_1 AS PARTITION pf_1 ALL ([PRIMARY]);

CREATE TABLE partitioned_table (
    col1 INT NOT NULL,
    col2 INT NOT NULL,
    col3 CHAR(200) NOT NULL
) ON ps_1;

CREATE UNIQUE CLUSTERED INDEX ix_col1
ON partitioned_table(col1)
ON ps_1;
GO
```

```sql
WITH
n1 AS (SELECT 1 AS c),
n2 AS (SELECT 1 a FROM n1 b, n1 c),
n3 AS (SELECT 1 a FROM n2 b, n2 c),
n4 AS (SELECT 1 a FROM n3 b, n3 c),
n5 AS (SELECT 1 a FROM n4 b, n4 c),
n6 AS (SELECT 1 a FROM n5 b, n5 c)
INSERT INTO partitioned_table WITH (TABLOCK)
(col1, col2, col3)
SELECT TOP(1000000)
ROW_NUMBER() OVER (ORDER BY (SELECT NULL)) AS col1,
CHECKSUM(NEWID()) AS col2,
'' AS col3
FROM n6;
GO
```

一旦表填充完毕，以下查询将产生该计划：

```sql
SELECT COUNT(*)
FROM partitioned_table AS pt1
INNER JOIN partitioned_table AS pt2 ON pt1.col1 = pt2.col1
WHERE pt1.col1 BETWEEN 25000 AND 500000;
```

![](img/bdc38aa36f6e2987d913ee5381474711_197_0.png)

图 2-80 涉及分区表的计划中基于需求的分布。

## 并行 SELECT INTO

多年来，通过 Bulk Copy API 已经并行批量加载数据到表中。并行批量加载并不涉及查询处理器的并行性，而是允许客户端启动并发的批量加载以共同运行。这是因为最小日志的批量拷贝只处理页分配；多个流同时分配页不会产生冲突风险，除了页分配结构外不需要并发控制，这是一种低开销且简单的吞吐量改进。

在查询引擎内部，T-SQL 开发者长期以来可以使用 `SELECT INTO` 语法执行最小日志的插入（只要目标数据库使用简单或批量日志恢复模型）。然而，这些操作始终使用单个流写入数据，尽管关系型引擎能够处理多个并发流。

考虑以下 `SELECT INTO` 查询：

```sql
WITH
n1 AS (SELECT 1 a UNION ALL SELECT 1),
n2 AS (SELECT 1 a FROM n1 b, n1 c),
n3 AS (SELECT 1 a FROM n2 b, n2 c),
n4 AS (SELECT 1 a FROM n3 b, n3 c),
n5 AS (SELECT 1 a FROM n4 b, n4 c),
n6 AS (SELECT 1 a FROM n5 b, n5 c)
SELECT TOP(100000000)
ROW_NUMBER() OVER (ORDER BY (SELECT NULL)) AS col1,
CHECKSUM(NEWID()) AS col2
INTO #test_table
FROM n6;
```



该查询向名为 `#test_table` 的临时表插入了 10,000,000 行。图 2-8 显示了该查询在 SQL Server 2012 实例上运行时的查询计划片段。

| 表 (insert #test_table) | 计算标量 (Compute Scalar) | 顶部 (Top) | 序列投影 (计算标量) | 分段 (Segment) | 并行性 (聚集流) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 成本: 78% | 成本: 0% | 成本: 0% | 成本: 0% | 成本: 0% | 成本: 1% |

图 2-8：在 SQL Server 2012 中，SELECT INTO 在单线程上写入。

尽管此查询使用了并行处理，但在计算行号之前，并行流会被聚集。计算行号后，数据将通过单串行流写入临时表。

在 SQL Server 2014 实例上运行相同的查询会生成图 2-82 所示的计划片段。

| 并行性 (聚集流) | 表成本 (#test_table) | 计算标量 (Compute Scalar) | 并行性 (分发流) | 顶部 (Top) | 序列投影 (计算标量) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 成本: 3% | 成本: 37% | 成本: 0% | 成本: 19% | 成本: 1% | 成本: 1% |

图 2-82：在 SQL Server 2014 中，SELECT INTO 可以是多线程。

在 SQL Server 2014 中，行号是在串行线程中生成的。然而，一旦计算完成，行就会分发到多个线程（在此例中，使用轮询方案），然后从多个并发流写入目标表。

这种增强带来的性能收益可能是惊人的：在一台同时安装了 SQL Server 2012 和 SQL Server 2014 的测试服务器上，在磁盘系统和内存分配完全相同的情况下，该查询在 SQL Server 2012 中运行了 10 秒，而在 SQL Server 2014 中仅需 4 秒。

# 并行性与查询优化

在查询处理器能够执行并行查询计划之前，查询优化器必须先生成该计划。所使用的过程比串行查询计划的要要复杂且细微，作为一名处理并行查询的开发者，你需要了解其内部机制，以便在问题发生时有效处理。

查询计划中使用或不使用并行处理的决策大部分是在查询处理器执行之前做出的。此决策基于实例级（或资源管理器组级）设置与相关查询的结合。实际实际运行计划的执行引擎对于是否使用并行处理几乎没有发言权，且当 SQL Server 实例处于极端资源压力时，它会否决并行使用。

## 并行性设置

如果不理解影响该过程的实例级和资源管理器设置，就不可能对查询优化过程进行讨论。

有四个可以影响并行性的实例级设置。这些设置可以在 `sys.configurations` 目录视图中查看，并可以使用 `sp_configure` 系统存储存储过程进行配置。设置如下：

- **亲和性映射 (Affinity Map)**：此设置控制服务器的哪些逻辑处理器将映射到 SQL 调度器。并行查询计划需要多个 SQL 调度器，因此，如果亲和性映射设置为仅映射一个处理器，则查询优化器将不会尝试生成并行计划。在当今多核服务器中，单调度器的 SQL Server 实例非常罕见。该设置的默认值为 0，表示所有逻辑处理器都应映射到 SQL 调度器。
- **并行度 (Max Degree of Parallelism)**：并行度是一个默认值，并行查询用它确定每个查询分配多少工作线程。此设置可以使用查询级别的 `MAXDOP` 提示来覆盖（增加或减少）。此设置名称中的“*最大*”和查询提示具有误导性；如果并行查询使用，它将使用查询级别指定的 DOP，或者由后文描述的资源管理器设置。对于给定查询，什么是“正确”的 DOP 既不是查询优化器的决策，也不是运行时查询处理器的决策。
- **并行成本阈值 (Cost Threshold for Parallelism)**：在优化查询时，查询优化器会经过多个阶段，每个阶段都会增加时间开开销。优化器的目标之一是在短时间内生成足够好的计划，如果串行查询计划的成本不足以进一步优化，该设置将帮助实现该目标。该设置的默认值为 5，意味着成本高于 5 的串行计划将进入并行阶段。
- **最大工作线程 (Max Worker Threads)**：SQL Server 维护一个供查询使用的操作系统线程池。线程是有限的资源，必须仔细控制以避免饥饿，此设置控制 Server 实例在任何时间可以创建多少线程。这在以下 URL 有完整记录：`https://msdn.microsoft.com/en-us/library/ms19219.aspx`。

除了这些实例级设置外，资源管理器组可以使用 `max_dop` 设置来覆盖并行度。此设置与实例级设置具有相同的影响，只是与查询级别的 `MAXDOP` 提示的交互方式不同：它可以被查询提示覆盖，或者由资源管理器将 `max_dop` 设置为 10。这是一种控制复杂负载并确保单个查询不会消耗过多资源的有用方法。

## 优化过程

在查询优化的第一阶段，优化器为查询生成一个串行版本的查询计划。查询计划的总成本是计划中每个操作符的成本之和。这些成本进一步按操作符拆分为 CPU 和 I/O 成本，如图 2-83 所示。

![](img/bdc3aa36fe2987d91ee53814741_200_0.png)

图 2-83：串行计划中索引扫描的操作成本。

在计划中，此串行扫描的估计 CPU 成本为 0.133606，估计 I/O 成本为 0.91861，总成本为 1.05229——CPU 和 I/O 成本的总和。一旦生成串行计划，计划中每个操作符的成本相加。如果总和小于并行成本阈值设置的值，则不尝试进一步优化，直接使用该计划。然而，如果超过并行成本阈值，则会对查询进行进一步优化，并考虑并行计划。

一旦为查询生成并行查询计划，将进行额外的计算。每个操作符的成本（但不包括 I/O 成本）除以被称为 DOP 的数量。这是调度器数量的一半或查询提示指定的 MAXD。例如，对于具有 24 个调度器的实例，如果保持并行度设置不变且查询级别的 `MAXDOP` 设置为 8，则计算出的 DOP 为 12。然而，在具有 12 个调度器的实例上，即使 `MAXDOP` 提示设置为 8，计算出的 DOP 也将是 6，因为取了这两个值中的较小者。

图 2-84 显示了与前一个图相同的索引，但是并行计划。

| 估计成本 | 0.033414 |
| :--- | :--- |
| 聚集索引扫描 (Clust.[SalesOrderDetail],FK_Sales... | 行 |
| 估计 I/O 成本 | 0.918681 |
| 估计执行次数 | 1 |
| 估计行数 | 121317 |
| 估计操作成本 | 0.952082 (28%) |

**图 2-84**：CPU 成本除以 DOP。在此例中，查询在具有 8 个 SQL 调度器的实例上进行了优化，但实例级并行度设置为 6。串行 CPU 成本 0.133606 除以 4（调度器数量的一半），得到估计的并行 CPU 成本 0.033414。I/O 成本保持不变，因为 SQL Server 在假设 I/O 通道将完全饱和时采取保守的方法。结果是，即使不接触 I/O 成本，整体操作成本也降低了。

除了为了促进并行处理而添加到计划中的任何交换操作符的成本外，所有新操作符都已添加。如果并行版本计划的总成本小于串行版本计划的总操作符成本，则查询优化器选择并行版本。否则，将使用串行版本。

## 为实例配置并行性

如果没有一些配置的建议，设置讨论就是不。遗憾的是，没有简单的答案，但一些通用指南会有帮助。

在大多数情况下，亲和性映射和最大工作线程设置应保持不变。

亲和性映射主要用于控制许可协议，但较新版本的 SQL Server 必须对特定服务器上的所有可用处理器进行授权。这留下了边缘情况，例如，SQL Server 与一个 IIS 实例共享服务器，而管理员希望为每个进程分配自己的预留 CPU。这种情况是有意义的，但在当今世界，服务器虚拟化技术通常是处理该问题的更好方法。

最大工作线程（Max Workers Threads）的设计旨在自动维护，通常只有在极端情况下（特别是具有沉重的并行工作负载以及线程池耗尽的特定类型时）才需要进行调整。这些情况通常需要联系产品支持，明智之举是让支持人员决定如何解决此类问题。

查询成本（Query cost）是 1998 年在 SQL Server 7.0 中首次引入的指标。多年后的现在，在本文结构编写时，计算机行业已经发生了巨大的变化，但查询成本仍然使用基本结构。查询成本为 5（并行度阈值 Cost Threshold Of Parallelism 的默认值）在 1998 年是非常大的，但在当今的海量数据库中则相对较小。因此，建议对大多数 SQL Server 实例更改此数值。对于如今的典型硬件和数据规模，设置在 30 到 50 之间的值是合理的。如果你发现查询（针对你的环境）正在使用并行线程，可以考虑设置更高的值。

与并行度阈值（Cost Threshold For Parallelism）一样，最大并行度（Max Degree Of Parallelism）也有一个令人遗憾的默认值。应该针对特定实例调整此设置，以平衡查询响应时间与允许许多查询并发运行的目标。如果最大并行度太低，查询将变慢；如果它太高，并发查询将强制竞争处理器时间并并产生负面影响。

最大并行度的通用指南取决于工作负载。对于 OLTP 系统，由于其倾向于具有高比例的小型串行查询计划，外还有许多更轻级的查询，可能建议使用较小的最大并行度——低至 2。

相反，对于 OLAP 工作负载，典型情况是较少但规模更大的查询，较高的最大并行度通常是一个好主意。在四插槽服务器上，明智的做法是设置为每个 NUMA 节点的处理器数量（通常与每个插槽的处理器数量相同），在双插槽服务器上设置为其一半。这使得每个查询都能获得可用 CPU 功率的大部分，同时允许并发查询运行而互不干扰。

如果启用了超线程（Hyper-Threading），建议将最大并行度设置为不超过每个节点物理处理器数量的 50%。换句话说，如果每个节点有 6 个物理处理器和 12 个逻辑处理器（由于超线程），通常建议设置最大并行度不超过 9。这有助于防止查询执行压过超线程提供的额外加速。

## 并行抑制因素

除了核心查询优化和处理决策外，几个查询功能可以通过以下两种方式之一抑制并行：在原本并行的查询计划中强制执行串行区域，或完全为特定查询禁用并行。

以下是导致并行查询计划中出现串行区域的常见因素列表：

- **多语句 T-SQL UDF (Multistatement T-SQL UDF)**：多语句 UDF 通过表变量返回表值。用户定义函数（UDF）中的逻辑将在串行区域中处理，尽管计划的其他部分可能使用并行处理。
- **递归 CTE (Recursive CTEs)**：递归公表表达式在串行区域中处理，尽管下游操作符必须使用并行。
- **反向扫描 (Backward scans)**：SQL Server 中的索引使用双向链表，可以正向或反向方向扫描。只有正向扫描符合前述的并行扫描条件。反向扫描将被拒绝并在串行执行。
- **非分区的 TOP、聚合和窗口函数 (Nonpartition TOP, aggregates, and windowing functions)**：使用 TOP 操作符、聚合和窗口函数涉及创建行组。如果组必须通过分析计划在给定阶段的整个行集来确定，则查询优化器别无使用串行示例。示例包括相关表表达式之外、未分组的聚合（也称为*标量聚合*/scalar aggregate）以及不使用分区的窗口函数。

以下列表包含会完全禁用特定计划并行性的常见功能：

- **标量 T-SQL UDF (Scalar T-SQL UDF)**：在查询中使用任何标量 T-SQL UDF 都会导致该查询无法使用并行。对于任何考虑使用 UDF 的开发者来说，这应该是一个重大的红旗（警告）。内联表达式或 CLR UDF 是更好的选择。
- **修改表变量 (Modification of table variables)**：在大多数情况下，当使用查询向表中插入、更新或删除行时，查询中实际数据修改之前的部分可以在并行区域中处理。（除 SELECT INTO 以外的数据修改外）。表变量将打破这一惯例；如果正在修改表变量中的行，整个计划将串行运行。请注意，如果表仅用于计划中不涉及行修改的某些，则并非如此。）
- **带有 DataAccessKind.Read 的 CLR UDFs**：除非 UDF 标记为 *DataAccessKind.Read*，否则 CLR UDF 不会禁用并行，这意味着它有权在主机数据库中运行查询。
- **内存优化表 (Memory-optimized tables)**：内存优化表不能参与并行查询计划。

要查看这些功能之一的影响，请首先考虑以下查询，其计划如图 2-85 所示：

```sql
SELECT TOP(1000)
OrderQty
FROM Sales.SalesOrderDetail
ORDER BY
OrderQty DESC;
```

![](img/bdc38aa36f6e2987d913ee53814711_204_0)
图 85。一个并行计划。

这生成了一个典型的并行计划；但如果进行了微小的修改会怎样？首先创建 UDF：

```sql
CREATE FUNCTION dbo.ReturnInput(@input INT)
RETURNS INT
AS
BEGIN
RETURN(@input)
END
GO
```

一旦创建了 UDF，就可以在查询中使用：

```sql
SELECT TOP(1000)
dbo.ReturnInput(OrderQty)
FROM Sales.SalesOrderDetail
ORDER BY DESC;
```

尽管这可能是可以编写的最简单的 UDF，但对查询计划的影响是巨大的，如图 2-86 所示。

![](img/bdc38aa36f6e2987d913ee53814711_204_1)
图 86。不再是并行计划。

如果你试图确定计划是否由于抑制因素导致的，请检查 SELECT 算符的属性。图 2-87 高亮了 NonParallelReason 属性，它可以帮助你理解限制并行的因素。

| MemoryGrantInfo | CouldNotGenerateParallel |
|---|---|
| NonParallelReason | FULL |
| Optimization Level | |

**2-87  显示存在抑制因素。**

## 并行 APPLY 模式

考虑到本节之前描述的额外线性属性，加上在线程之间迁移行的开销，大型并行查询计划的扩展性并不理想。

尽管查询优化器能够对任何给定查询执行许多优化和转换，但其范围根据模型是有限的。通过大量的手动重写，你可以创建速度快一个数量级的计划，而无需希望查询优化器能够得出正确的解决方案。

## 示例查询

AdventureWorks2014 示例数据库对于示例查询很有用，但规模不足以说明各种性能技巧的优缺点。为了编写查询，需要一些较大的表。

首先，让我们看一个比标准版本多出五个产品的表：

```sql
SELECT
  p.Name,
  p.ProductID + x.v AS ProductID
INTO #bigger_products
FROM Production.Product AS p
JOIN
(
  VALUES
    (0), (1000), (2000), (3000), (4000))
AS x(v);
CREATE CLUSTERED INDEX i_ProductID
ON #bigger_products (ProductID);
GO
```

接下来，有一个事务次数比标准版本多 504 倍的：

```sql
SELECT
th.ProductID + x.v AS ProductID,
th.ActualCost,
th.TransactionDate
INTO #bigger_transactions
FROM Production.TransactionHistory AS th
CROSS JOIN
(
SELECT
    (NTILE(5) OVER (ORDER BY p.ProductID) - 1) * 1000
FROM Production.Product AS p
) AS x(v);
CREATE CLUSTERED INDEX i_ProductID
ON #bigger_transactions(ProductID);
GO
```

该表通过将 `Production.TransactionHistory` 中的 113,443 条交易与来自 `Production.Product` 的 504 行进行交叉连接而创建。这里使用 `NTILE` 函数来创建五组行，这些行对应于创建 `#bigger_products` 表时使用的五行。结果集包含 57,175,272 行，并且在 `ProductID` 列上创建了聚集索引。之所以选择该列，是因为查询将使用该列来连接这两个表。

场景如下：用户想知道每个产品前 10 个最高价格（包括并列）的销售情况以及交易日期。以下查询回答了这个问题：

```sql
SELECT
p.Name,
x.TransactionDate,
x.ActualCost
FROM
(
SELECT
th.ProductID,
th.TransactionDate,
th.ActualCost,
ROW_NUMBER() OVER
(
    PARTITION BY
th.ProductID
    ORDER BY
th.ActualCost DESC
) AS rn
FROM #bigger_transactions AS th
) AS x
INNER JOIN #bigger_products AS p ON
p.ProductID = x.ProductID
WHERE
x.rn <= 10;
```



该查询的工作原理是在派生表 `x` 中计算行号，按 `ProductID` 分区并按 `ActualCost` 降序排列。在查询的外部，对行进行过滤以只返回每个产品的前 10 记录，并与 `#bigger_products` 进行连接，以获取每个产品的名称。图 2-88 显示了为了适应本书而编辑过的计划版本。

![](img/bdc38aa36f6e2987d913ee5381474711_207_0.png)

**图 2-88** 查找前 10 个最贵交易的查询计划。

此查询计划使用了并行处理，但存在几个潜在的瓶颈，可以在不修改索引或表结构的情况下解决。

第一个瓶颈是 `Hash Join` 算子探针侧（probe side）的排序（`Sort`）。如前所述，`Sort` 并不是线性扩展的，而且在这种情况下，输入行数巨大。由于这是一个并行计划，集合会被拆分，但规模的缩小将受到计划 DOP（并行度）的限制。将集合拆分成更小的工作子集，可能会产生更大的收益。此外，较小的子集需要的内存更少，内存溢出并到 `tempdb` 的概率也较低。

第二个瓶颈是 `Hash Join` 算子探针侧并行扫描下游使用的重分区分区流（`Repartition Streams`）。该算子使用哈希分发方法根据 `ProductID` 将行分发到线程之间。这样做是为了确保每个产品的行能够被正确地排序在一起。遗憾的是，这种分区在计划的极早阶段就是必要的，它必须移动扫描产生的每一行——共 57,175,272 行。这是非常量的数据移动。

## 并行嵌套循环

解决这两个瓶颈的方案是重新思考数据在此类大型计划中的流动方式，并找到一种消除单一操作而执行更多更小操作的方法。可以实现此点的查询计划工具是嵌套循环（`Nested Loops`）算子。

在任何查询计划中（无论是串行的还是并行的），嵌套循环算子都会为每个外部行调用一次其内部算子。嵌套循环通常与相关子查询或表表达式一起使用，用于评估每个必要行的相关性。

从连接性能的角度来看，嵌套循环通常不是大型数据集的最优选择，因为每次内部评估都需要对数据进行另一次查找（seek）或扫描，且这些操作的成本可能会累积。因此，随着数据量的增加，通常使用 `Hash` 连接或 `Merge` 连接。

尽管如此，在许多查询中，连接性能并不是决定整体性能的主要因素。由于 `Sort` 和 `Repartition Streams` 算子的扩展性曲线，图 2-88 所示计划中的连接性能被其他元素大大掩盖了。在这些和类似的示例中，忽略连接性能并关注大局会更好。利用嵌套循环将让你能够妥善处理这种情况。

## 减少并行计划开销

利用嵌套循环的关键是一种被称为“并行 APPLY 模式”的特殊查询技术。该模式如列表 2-1所示。

### 列表 2-1 并行 APPLY 模式

```sql
SELECT
 p.[columns] AS x
FROM [driver_table] AS x
[CROSS | OUTER] APPLY
(
 SELECT
 [columns]
FROM [correlated_table] AS c
WHERE
 c.[key] = x.[key]
) p
```

模式包含两个主要元素：

- **驱动表（Driver table）**：这是一个表，其中每一行代表在内部表表达式要执行的一项唯一工作。例如，此表可以是产品、客户、日期或类似的元素类型集合，你希望对其中的每个项目进行分析。
- **相关表（Correlated table）**：这是为驱动表的每行都进行评估的表。相关性通过键（key）建立，确保内部表为每个外部行返回正确的数据。

在 `WHERE` 子句中进行比较。例如，以下查询返回了组织中所有员工都处理过订单的客户：

```sql
SET NOCOUNT ON;
USE TSQLV3;
```

```sql
SELECT custid
FROM Sales.Orders
GROUP BY custid
HAVING COUNT(DISTINCT emp) = (SELECT COUNT(*) FROM HR.Employees);
```

顺带一提，此查询处理了关系代数中“关系除”的一个简单情况。你将 `Orders` 表（连接客户和员工）中的订单集合除以 `Employees` 表中的员工集合，从而得到符合条件的客户。

子查询返回 `Employees` 表中员工的总数。外部查询按客户 ID (`custid`) 对 `Orders` 表中的订单进行分组，并过滤出那些“员工 ID 去重后计数等于子查询返回的员工人数”的客户组。显然，此查询假设数据库中执行了适当的引用完整性，防止订单中出现未在 `Employees` 表中的员工 ID。子查询返回 9，因为有 9 个不同的员工处理了这 9 个订单。

请注意，如果标量子查询返回空集，它将转换为 `NULL`。如果它返回了多个值，则会在运行时失败。在我们的案例中，这两种情况都不会发生，因为标量子查询保证恰好返回一个值，即使源表为空也是如此。

下一个示例是一个自包含的多值子查询。多值子查询在单列中返回多个值。它可以用于在期望多值结果的地方——例如配合 `IN` 谓词使用。

我们示例中的任务是返回在每个月最后一个活动日期下单的订单。最后一个活动日期并不律是该月的最后一天——例如，如果公司在周末和假日不处理订单。第一步是编写一个分组查询，返回每个年每月分组的最后活动日期，如下：

```sql
SELECT MAX(orderdate) AS lastdate
FROM Sales.Orders
GROUP BY YEAR(orderdate), MONTH(orderdate);
```

此查询返回以下结果：

| lastdate |
| :--- |
| 2014-03-31 |
| 2014-07-31 |
| 2015-05-06 |
| 2014-04-30 |
| 2014-10-31 |
| 2015-02-27 |
| 2013-12-31 |
| 2014-05-30 |
| 2015-03-31 |
| 2013-03-30 |

这个查询对于分组查询来说有点不常。通常情况下，你按某些元素分组并返回分组元素和聚合值。在这里，你按年份和月份分组，仅返回聚合值而不返回分组元素。但如果你仔细考虑，年月的分组中的最大日期保留了年月份的信息，因此分组信息在这里并没有丢失。

第二也是最后一步是查询 `Orders` 表，并过滤出订单日期出现在上一步返回的日期集中的订单。以下是完整的解决方案查询：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
WHERE orderdate IN
(SELECT MAX(orderdate)
FROM Sales.Orders
GROUP BY YEAR(orderdate), MONTH(orderdate));
```

此查询生成以下输出：

| orderid | orderdate | custid | empid |
| :--- | :--- | :--- | :--- |
| 10269 | 2013-07-31 | 89 | 5 |
| 10294 | 2013-08-30 | 65 | 4 |
| 10317 | 2013-09-30 | 48 | 6 |
| 10343 | 2013-10-31 | 44 | 4 |
| 10368 | 2013-11-29 | 20 | 2 |

...

# 相关子查询

相关子查询在发生问题时，内部包含对列的引用，这些引用被称为“相关性”（correlations），因为你无法独立运行它们。如果你将内部查询复制并粘贴到新窗口中（以使其可以运行），你必须用代表数据中样本值的常量来替换这些相关性。但当你完成故障排除并修复所需问题后，你必须将常量替换回相关性。这使得相关子查询的故障排除变得更加复杂且容易出错。

作为相关子查询的第一个示例，考虑一个与上一节最后一个任务类似的任务。之前的任务是返回在每个月最后一个活动日期下单的订单。我们现在的任务是返回在客户最后一个活动日期下单的订单。表面上看，唯一的区别是分组不再是年月份，而是客户。如果你获取上一个查询并将分组集从 `YEAR(orderdate), MONTH(orderdate)` 替换为 `custid`，你将得到以下子查询：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
WHERE orderdate IN
(SELECT MAX(orderdate)
FROM Sales.Orders
GROUP BY custid);
```

然而，现在子查询中有一个错误。上述子查询返回了所有客户的最后订单，但 `IN` 谓词会匹配任何订单日期等于列表中*任何*客户最后日期的订单，这并不是我们想要的（每个客户对应的最后日期）。要修复这个问题，我们需要使用相关子查询，如下：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders AS T1
WHERE orderdate =
(SELECT MAX(orderdate)
FROM Sales.Orders AS T2
WHERE T2.custid = T1.custid);
```

为了获取符合条件的键，子查询对外部客户的订单进行过滤，按 `orderdate DESC`、`orderid DESC` 排序，并返回该行的键。

这类任务通常被称为 Top N 分组任务，在实践中非常常见，并有不同的变体。书中多处讨论了该内容，最完整的覆盖包含在第 5 章“TOP 和 OFFSET-FETCH”。在这里讨论它是为了演示查询。

到此时，你已经有一个使用 `TOP` 过滤的简单直观的解决方案。问题是，它的性能如何？在索引指南方面，Top N 分组任务的解决方案通常受益于特定的索引模式，我喜欢将其称为 **POC 模式**。这是任务中元素的缩写。P 代表分区（partitioning/grouping）元素，在我们的案例中是 `custid`。O 代表索引排序（ordering），在我们的案例中是 `orderdate DESC`、`orderid DESC`。PO 是索引键列表。C 代表覆盖（covered）元素——即你为了获得查询覆盖而想要包含在查询中的所有剩余元素。在我们的案例中，C 元素是 `empid`。如果索引是非聚集索引，你需要在索引的 `INCLUDE` 中指定 C 元素。如果索引是聚集索引，C 元素是隐含的。运行以下代码来创建一个 POC 索引以支持你的解决方案：

```sql
CREATE UNIQUE INDEX idx_poc
ON Sales.Orders(custid, orderdate DESC, orderid DESC) INCLUDE (empid);
```

有了该索引，你将获得 TOP 子查询解决方案的图 3-1 所示的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_216_0.png)

**图 3-1** 每个订单执行一次查找（seek）的计划。

该计划对代表 `Orders` 表实例 O1（查询中的外部实例）的 POC 索引进行全扫描。然后对于每个 O1，计划在代表 `Orders` 表实例 O2（查询中的内部实例）的 POC 索引中执行一次查找（seek）。查找到达索引叶子节点中当前客户区域的开始，并扫描行以收集键。然后，计划仅过滤出 O1 键等于 O2 键的 O1 行。

该计划存在某种可以优化的低效率。考虑 `Index Seek` 算符执行了多少次。你每个订单执行一次查找，但你每个客户只需要一行。因此，更高效的策略是**每个客户执行一次查找**。`custid` 列越密集，数据的查找次数就越少；10,000 个客户平均有 1,000 次查找，总共产生 10,000,000 个订单。现有计划执行了 10,000,000 次查找。在索引 B 树有三层的情况下，这相当于 30,000,000 次随机读取。这是极其低效的。如果你发现如何获得每个客户执行一次查找的计划，你将只需 10,000 次查找。这种计划可以使用 `CROSS APPLY` 算符实现，我将在本章稍后演示。目前，我将解决方案限制为仅使用普通子查询，因为这是本节的重点。

使用子查询获取更高效的计划，你需要分两步实现解决方案。第一步，你查询 `Customers` 表，并使用与之前类似的 `TOP` 子查询为每个客户返回符合条件的订单 ID，如下所示：

```sql
SELECT
(SELECT TOP (1) orderid
FROM Sales.Orders AS O
WHERE O.custid = C.custid
ORDER BY orderdate DESC, orderid DESC) AS orderid
FROM Sales.Customers AS C;
```

此查询生成如下输出，仅显示符合条件的订单 ID：

```
orderid
------
11011
10926
10856
11014
10924
11058
10826
10970
11076
11023
```

此查询的计划见图 3-2。

![](img/bdc38aa36f6e2987d913ee5381474711_217_0.png)

**图 3-2** 每个客户执行一次查找的计划。

此计划与图 3-1 中计划之间的关键区别在于，它是每个客户执行查找，而不是每个订单。此计划执行了 10,000 次查找，花费了 30,000 次随机读取。

第二步是查询 `Orders` 表，返回其键出现在第一步查询返回的键集中的订单信息，如下所示：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
WHERE orderid IN
(SELECT TOP (1) orderid
FROM Sales.Orders AS O
WHERE O.custid = C.custid
ORDER BY orderdate DESC, orderid DESC
FROM Sales.Customers AS C);
```

完整解决方案的查询计划见图 3-3。

![](img/bdc38aa36f6e2987d913ee5381474711_218_0.png)

**图 3-3** 每个客户执行一次查找的完整计划。

此计划与图 3-1 中计划之间的关键区别在于，它是每个客户执行查找，而不是每个订单。此计划执行了 10,000 次查找，花费了 30,000 次随机读取。

## EXISTS 谓词

`EXISTS` 谓词的一个奇特之处在于，与大多数谓词不同，它使用**二值逻辑**。它返回真或假，不会因为 `NULL` 的存在而返回未知。尽管如此，`EXISTS` 谓词总是能确定结果集是否为空。与此相反，例如 `IN` 谓词使用三值逻辑。

从索引的角度来看，优化器忽略 `SELECT` 列表。例如，`Orders` 表有一个由 `custid` 定义且不包含任何列的索引 `idx_nc`。观察图 3-4 所示的 `EXISTS` 查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_219_0.png)

**图 3-4** 带有 SELECT * 的 EXISTS 计划

注意，尽管子查询使用了 `SELECT *`，但唯一使用的 `Orders` 表的是 `idx_nc_cust`。换句话说，对于此子查询而言，该索引被认为是覆盖索引。

接下来我将演示可以使用 `EXISTS` 谓词处理的几个经典任务。我将使用表 `T1`，你通过运行以下代码创建并填充它：

```sql
SET NOCOUNT ON;
USE tempdb;
IF OBJECT_ID('dbo.T1', 'U') IS NOT NULL DROP TABLE dbo.T1;
CREATE TABLE dbo.T1(col1 INT NOT NULL CONSTRAINT PK_T1 PRIMARY KEY);
INSERT INTO dbo.T1(col1) VALUES(1), (2), (3), (7), (8), (9), (11), (15), (16), (17), (27), (28);
```

表中的键列是 `col1`。假设你有一个键生成器，它从 1 开始生成连续键，但删除操作产生了空隙。一个经典挑战是识别最小缺失值。为了测试你解决方案的正确性，你可以使用过程生成的一小部分样本数据。出于性能考虑，你希望填充一个更大的表。使用以下代码填充 10,000,000 行数据：

```sql
TRUNCATE TABLE dbo.T1;
INSERT INTO dbo.T1 WITH (TABLOCK) (col1)
SELECT n FROM TSQLV.dbo.GetNums(1, 10000000) As Nums n % 10000 <> 0
OPTION(MAXDOP 1);
```

你可以使用 `CASE` 表达式，如果 1 已经不存在于表中，则返回 1。更复杂的部分是当 1 已经存在时识别最小值。实现此点的方法是使用以下查询：

```sql
SELECT MIN(A.col) + 1 AS missingval
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col = A.col + 1);
```



这段代码的第一步是过滤 T1（别名为 A）中的行，使得 A 中的值出现在缺失值之前。然后你就知道 A 中的值出现在缺失值之前，因为你无法在 T1（别名为 B）中找到另一个 B 值比 A 值大 1 的值。然后，从 A 的所有剩余值中，你返回最小值加 1。也许你认为该查询会立即完成；毕竟，在 `col1` 上有一个索引（`PK_T1`）。从理论上讲，你应该能够顺序扫描索引，并在发现第一个缺失值之前的点时立即短路操作。但针对大型样本数据集，它需要几秒钟才能完成。在我的系统上，它花费了五秒钟完成。要理解为什么查询缓慢，请查看图 3-5 所示的查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_220_0.png)

图 3-5 查找最小值的第一次尝试。

观察到索引 `col1` 被完整扫描了两次。使用 Merge Join 算子执行右半连接（semi join）来检测不匹配。Stream Aggregate 算子识别最小值。关键问题是该计划由于输入被完整扫描两次导致了效率低下。尽管扫描是有序的，但并没有短路。

优化查询的一种尝试是使用 TOP 过滤器代替 MIN 聚合函数，如下：

```sql
SELECT TOP (1) A.col + 1 AS missingval
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col = A.col + 1)
ORDER BY A.col;
```

但是，查询很慢。检查此查询的执行计划，如图 3-6 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_221_0.png)

**图 3-6** 查找最小值的第二次尝试。

Merge Join 谓词将 A 输入视为 `Expr1003 (A.col1 + 1)`，将 B 输入视为 `col1(T1.col1)`。因为外部查询按 `A.col1` 而不是 `A.col1 + 1` 对行排序，优化器没有意识到行已经排序，并添加了 Sort (Top N Sort) 算子，它消耗了整个输入以确定前 1 行。要修复此，只需将外部查询的 `ORDER BY` 改为 `A.col1 + 1`，如下：

```sql
SELECT TOP (1) A.col1 + 1 AS missing
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col1 = A.col1 + 1);
```

观察图 3-7 所示的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_221_1.png)

**图 3-7** 查找最小值的第三次尝试。

优化器意识到 Merge Join 算子返回行的排序方式与 TOP 过滤器需要的方式相同，因此在找到第一个匹配行时就可以短路。查询在亚秒内完成。

或者，如果内部查询的 WHERE 过滤器从 `B.col1 = A.col1 + 1` 改为 `A.col1 = B.col1 - 1`，且 `ORDER BY` 子句从 `A.col1 + 1` 改为 `A.col1`，你也会获得优化计划，如下：

```sql
SELECT TOP (1) A.col1 + 1 AS missing
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE A.col1 = B.col1 - 1)
ORDER BY A.col1;
```

现在添加 CASE 表达式逻辑，如果不存在则返回 1，否则返回子查询的结果。你得到完整的代码：

```sql
SELECT
CASE
WHEN NOT EXISTS (SELECT * FROM dbo.T1 WHERE col1 = 1) THEN 1
ELSE (SELECT TOP (1) A.col1 + 1 AS missingval
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col1 = A.col1 + 1)
ORDER BY missingval)
END AS missingval;
```

另一个涉及序列值的经典任务是识别所有缺失值的范围。在这种情况下，我们将查找表中存在的最小值和最大值之间的缺失值。这种任务通常被称为识别间隔（gap）。与最小值任务不同，没有短路潜力。作为第一步，你可以使用上一个任务中相同的查询来查找：

```sql
SELECT col1
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col1 = A.col1 + 1);
```

针对样本数据得到以下输出：

| col1 |
|---|
| 3 |
| 9 |
| 11 |
| 17 |

观察到索引 `col1` 被完整扫描了两次。使用 Merge Join 算子执行半连接来检测不匹配。Stream Aggregate 算子识别最小值。关键问题是该计划导致输入被完整扫描两次。尽管扫描是有序的，但没有短路。

优化查询的一种尝试是使用 TOP 过滤器代替 MIN 聚合，如下：

```sql
SELECT TOP (1) A.col + 1 AS missingval
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col = A.col + 1)
ORDER BY A.col;
```

但是，查询很慢。如图 3-6 所示，检查此查询的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_221_0.png)

**图 3-6** 查找最小值的第二次尝试。

Merge Join 谓词将 A 输入视为 `Expr1003 (A.col1 + 1)`，B 输入视为 `col1(T1.col1)`。因为外部查询按 `A.col1` 而不是 `A.col1 + 1` 排序，优化器没有意识到行已经排序，并添加了 Sort (Top N Sort) 算子，它消耗了整个输入以确定前 1 行。要修复此，只需将外部查询的 `ORDER BY` 改为 `A.col1 + 1`，如下：

```sql
SELECT TOP (1) A.col1 + 1 AS missing
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col1 = A.col1 + 1);
```

观察图 3-7 所示的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_221_1.png)

**图 3-7** 查找最小值的第三次尝试。

优化器意识到 Merge Join 算子返回行的排序方式与 TOP 过滤器需要的方式相同，因此在找到第一个匹配行时就可以短路。查询在亚秒内完成。

或者，如果内部查询的 WHERE 过滤器从 `B.col1 = A.col1 + 1` 改为 `A.col1 = B.col1 - 1`，且 `ORDER BY` 子句从 `A.col1 + 1` 改为 `A.col1`，你也会获得优化计划，如下：

```sql
SELECT TOP (1) A.col1 + 1 AS missing
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE A.col1 = B.col1 - 1)
ORDER BY A.col1;
```

现在添加 CASE 表达式逻辑，如果不存在则返回 1，否则返回子查询的结果（使用高效解决方案之一）。你得到以下完整的代码：

```sql
SELECT
CASE
WHEN NOT EXISTS (SELECT * FROM dbo.T1 WHERE col1 = 1) THEN 1
ELSE (SELECT TOP (1) A.col1 + 1 AS missingval
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col1 = A.col1 + 1)
ORDER BY missingval)
END AS missingval;
```

另一个涉及序列值的经典任务是识别所有缺失值的范围。在你的情况下，我们将查找表中存在的最小值和最大值之间的缺失值。这种任务通常被称为识别间隔。与最小值任务不同，没有短路潜力。作为第一步，你可以使用上一个任务中相同的查询来查找：

```sql
SELECT col1
FROM dbo.T1 AS A
WHERE NOT EXISTS
(SELECT *
FROM dbo.T1 AS B
WHERE B.col1 = A.col1 + 1);
```

针对样本数据得到以下输出：

| range_from | range_to |
|---|---|
| 4 | 6 |
| 10 | 10 |
| 12 | 14 |
| 18 | 27 |

T-SQL 查询任务的有趣点之一在于，对于任何给定的问题，通常有多种解决方案。不同的解决方案通常会有不同的执行计划。因此，开发以不同方式解决查询任务的能力，并仔细观察每种情况下优化器如何处理是非常重要的。以后，当你调整查询并需要在计划上实现某些效果时（例如通过比较 SQL Server 处理基于子查询的解决方案与连接解决方案的方式，或者使用聚合结果解决方案与使用 TOP 过滤器的解决方案等），这种技能将非常有帮助。

```sql
SELECT * FROM Sales.Orders AS O
WHERE O.custid = C.custid
AND O.empid = E.empid;
```

也许双重否定的形式起初并不十分直观，但好消息是，这种思维可以通过练习得到提高。

现在，你可以检查并比较正向方案与否定方案的计划，以学习优化器在不同情况下是如何处理这些。需要注意的是，由于 TSQLv3 数据库中的表非常小，你实际上无法对它们进行任何性能测试。你需要更大的表来进行适当的性能分析和调优。我在文章《识别序列中的子序列，部分2》（Identifying a Subsequence in Sequence, Part 2）中演示了一个大数据示例，其中双重否定方法实现了非常高效的解决方案，你可以在这里找到：http://sqlmag.com/t-sql-identifying-subsequence-in-sequence-part-2。

我在许多其他情况下也发现了双重否定方法的用。例如，假设你有一个字符串列 `sn`（序列号），该列应该只允许数字。你想用 `CHECK` 约束来强制执行这条规则。你可以赞美基于正向逻辑的谓词，但我发现在这种情况下，双重否定的形式是最优雅且经济的。正向规则说是列中的每个字符都是数字。双重否定的形式则是列中没有一个字符不是数字。在 T-SQL 中，这条规则翻译为以下谓词：

```sql
sn NOT LIKE '%[^0-9]%'
```

简单明了！

## 行为异常的子查询

有些常见任务通过子查询来处理，如果你不遵循最佳实践，很容易遇到 Bug 带来的困扰。我将描述两个问题：一个涉及子查询列名的替换错误，另一个是子查询中对 NULL 的不直观的处理。我还将提供最佳实践，如果遵循了这些实践，可以帮助你避免此类麻烦。

考虑 T1 和 T2 表以及它们填充的示例数据：

```sql
IF OBJECT_ID(N'dbo.T1', N'U') IS NOT NULL DROP TABLE dbo.T1;
IF OBJECT_ID(N'dbo.T2', N'U') IS NOT NULL DROP TABLE dbo.T2;
GO
CREATE TABLE dbo.T1(col1 INT NOT NULL);
CREATE TABLE dbo.T2(col2 INT NOT NULL);
INSERT INTO dbo.T1(col1) VALUES(1);
INSERT INTO dbo.T1(col1) VALUES(2);
INSERT INTO dbo.T1(col1) VALUES(3);
INSERT INTO dbo.T2(col2) VALUES(2);
```

假设你需要返回 T1 中也出现在 T2 值集中的值。执行以下查询（但先不要运行它）。

```sql
SELECT col1 FROM dbo.T1 WHERE col1 IN(SELECT col1 FROM dbo.T2);
```

在执行此查询之前，检查两个表中的值并回答以下问题：你预期在结果中看到哪些值？自然地，你预期在结果中只看到值 2。执行查询。你得到了以下输出：

```text
col1
-----
1
2
3
```

你能解释为什么你得到了 T1 的所有值，而不仅仅是 2 吗？

仔细检查表定义和查询代码会发现，针对 T2 的子查询错误地引用了 `col1`，而不是 `col2`。现在问题是，为什么代码没有失败？SQL 查询会首先解析立即查询中的表列确定哪个列属于它。如果找不到（就像我们的案例那样），它会在外部查询的表里查找。在我们的案例中，外部表中有一个名为 `col1` 的列；因此，使用了它。无意中，内部对 `col1` 的引用变成了一个相关引用。当外部 `col1` 的值为 1 时，内部查询为 T2 中的每一行选择一个 1。当外部 `col1` 的值为 2 时，内部查询为 T2 中的每一行选择一个 2。你意识到，只要 T2 中存在行数据，且 `col1` 的值不为 NULL，你就会得到匹配。

通常，这种类型的问题发生在你在不同表中为表示相同事物时，命名属性的方式是不一致的。例如，假设在 `Customers` 表中你使用存储客户 ID 的列，而在相关的 `Orders` 表中，你将该列命名为 `customerid`。然后你写了一个类似于示例中查询的查询，寻找下过订单的客户，但错误地对两个表都指定了 `custid`。你将获得所有客户，而不仅仅是真正下过订单的客户。当外部语句是 `SELECT` 时，查询返回包含所有行的错误结果，但当你意识到外部语句是 `DELETE` 时，你最终删除了所有行。

有两种实践可以帮助你避免代码中的此类 Bug：一个是长期的建议，另一个是短期的。长期实践是多注意在不同表表示相同事物时，以相同的方式命名属性。短期建议是简单地在列名前加上表名前缀（或你分配的别名），这样你就不需要依赖隐式解析了。将此实践应用于我们的示例查询：

```sql
SELECT col1 FROM dbo.T1 WHERE col1 IN(SELECT col2 FROM dbo.T2);
```

现在查询由于解析错误失败了，显示 T2 中没有名为 `col1` 的列：

```text
Msg 207, Level 1, State 1, Line 1
```

人们在子查询中遇到问题的另一个经典案例与 NULL 的处理。为了看到问题，重新创建并填充 T1 和 T2 表，使用以下内容：

```sql
IF OBJECT_ID(N'dbo.T1', N'U') IS NOT NULL DROP TABLE dbo.T1;
IF OBJECT_ID(N'dbo.T2', N'U') IS NOT NULL DROP TABLE dbo.T2;
GO
CREATE TABLE dbo.T1(col1 INT NOT NULL);
CREATE TABLE dbo.T2(col2 INT NOT NULL);
INSERT INTO dbo.T1(col1) VALUES(1);
INSERT INTO dbo.T1(col1) VALUES(2);
INSERT INTO dbo.T1(col1) VALUES(NULL);
INSERT INTO dbo.T2(col2) VALUES(3);
```

观察两个表中的值。假设你想返回在 T2 中不在 T1 中的值。你写了以下代码来实现此（但先不要运行）：

```sql
SELECT col1 FROM T2 WHERE col1 NOT IN(SELECT col1 FROM T1);
```

在执行此查询之前，回答问题：你预期在结果中看到什么值？大多数人预期会得到值 3。现在运行查询。你得到了空集：

理解为什么你会得到空集的关键在于记住，对于 `WHERE` 过滤器返回行，谓词需要评估为 `true`；得到 `false` 或 `unknown` 都会导致行被丢弃。很清楚为什么你没有得到 2——因为值 2 出现在 T1 中（谓词返回 `true`），你不想看到它（因为 `IN` 不是 `false`）。更难的部分是搞清楚为什么你没有得到值 3。关于 3 是否出现在 T1 的答案是，`NULL` 可以代表任何值。更技术地说，`IN` 谓词翻译为 `3=1 OR 3=2 OR NULL`，这个逻辑取或的结果是逻辑值 `unknown`。对查询应用 `NOT`。当你得到 `unknown` 时，你依然什么也得。换句话说，就像已知 3 出现在 T1 一样，它也知道 3 不出现在 T1。

来忽略它们。你可以通过几种方式实现这种行为。一种方案是在内部查询中通过添加过滤器 `WHERE col1 IS NOT NULL` 来显式地移除 NULL，如下所示：

```sql
SELECT col1 FROM dbo.T2 WHERE col1 NOT IN(SELECT col1 FROM dbo.T1 WHERE col1 IS NOT NULL);
```

这一次，你得到了最初可能预期的结果：

```text
col1
-----
3
```

另一个方案是使用 `NOT EXISTS` 代替 `NOT IN`，如下：

```sql
SELECT col1
FROM dbo.T2
WHERE NOT EXISTS(SELECT * FROM dbo.T1 T1 WHERE T1.col1 = T2.col1);
```



在这里，当内部查询的过滤器将 `NULL` 与任何内容进行比较时，过滤谓词的结果为未知（unknown），而谓词评估值为未知的行会被丢弃。换句话说，此解决方案中过滤器对 `NULL` 的隐式移除，与之前解决方案中显式移除 `NULL` 的效果相同。

## 表表达式

表表达式是命名的查询，你可以像操作表一样对其进行交互。T-SQL 支持四种表表达式：派生表、通用表表达式（CTEs）、视图和内联表值函数（inline TVFs）。前两种仅在定义它们的语句作用域内可见。对于后两种，表表达式的定义作为永久对象存储在数据库中，只要拥有相应的权限即可对其进行交互。

针对表表达式的查询在代码包含三个部分：内部查询、你分配给表表达式的名称（以及相关的列名）以及外部查询。内部查询用于生成一个表结果。这意味着它需要满足三个要求：

- 内部查询不能包含用于呈现的 `ORDER` 子句。它可以拥有 `ORDER` 子句以支持 `TOP` 或 `OFFSET-FETCH` 过滤器，但除非外部查询有自己的 `ORDER` 子句，否则外部查询无法保证行按特定顺序呈现。
- 所有列必须有名称。因此，如果你有一个通过计算得出的列，必须使用别名为其分配名称。
- 所有列名必须是唯一的。因此，如果你连接了同名的表并且需要返回同名的列，则需要为它们分配不同的别名。在中间逻辑处理阶段用作列名以前缀的表名或别名，在根据查询定义表表达式时会被移除。因此，表表达式中的列名必须是唯一的、独立的、未限定的标识符。

只要查询满足这三个要求，就可以作为表表达式中的内部查询使用。

从物理处理的角度来看，内部查询的结果并不持久化在任何地方；而是内联的。这意味着外部查询和内部查询被合并了。当你为针对表表达式的查询查找计划时，你会看到计划在查询内联化后直接与物理结构交互。换句话说，表表达式没有物理侧面；它们是虚拟的，应该被视为一种逻辑工具。该规则的唯一例外是索引视图——其中视图结果在 B 树中被索引。详情请参阅 <http://msdn.microsoft.com/en-us/library/ms191432.aspx>。

后续章节将描述不同类型的表表达式。

## 派生表

派生表可能是与子查询最相似的表表达式类型。它是定义在外部查询 `FROM` 子句中的子查询。你使用以下形式来定义派生表：

```sql
SELECT <col_list> FROM <inner_query> AS <target_alias>[(<target_col_list>)]
```

记住表表达式的所有列都必须有名称；因此，你必须为所有计算结果的列分配列别名。派生表支持两种不同的语法来对应列别名：内联别名和外部别名。为了演示该语法，使用你创建的表 `T1` 表并通过以下代码填充数据：

```sql
IF OBJECT_ID(N'dbo.T1', N'U') IS NOT NULL DROP TABLE dbo.T1;
GO
CREATE TABLE dbo.T1(col1 INT);
INSERT INTO dbo.T1(col1) VALUES(1);
INSERT INTO dbo.T1(col1) VALUES(2);
```

假设你需要内部查询为计算 `col1+1` 定义一个列别名 `expl1`，并在外部查询的某个表达式中引用 `expr1`。使用内联别名形式，你指定计算式后跟 `AS` 子句和别名，如下：

```sql
SELECT col1, expl1 + 1 AS exp2
FROM (SELECT col1, col1 + 1 AS expl1
      FROM dbo.T1) AS D;
```

使用外部别名形式，你在派生表名后的括号中直接指定目标列别名，如下：

```sql
SELECT col1, expl1 + 1 AS exp2
FROM (SELECT col1, col1 + 1
      FROM dbo.T1) AS D(col1, expl1);
```

通过这种方式，你必须为所有列（包括已有名称的列）指定名称。

两种语法都是标准的，各自有优势。我喜欢内联别名的地方是，在长且复杂的查询中，很容易识别哪个别名代表什么。我喜欢外部形式是因为它很容易在一个地方就能看到哪个别名代表什么。

## 通用表表达式

通用表表达式（CTEs）是另一种表表达式，与派生表一样，它们仅对定义它们的语句可见。不存在会话作用域或批处理作用域的 CTE。CTE 的优点在于它们被设计用于解决派生表具有的两个弱点。以下是一个代表年度订单数量的 CTE 定义示例：

```sql
WITH OrdCount
AS
(
  SELECT
    YEAR(orderdate) AS orderyear,
    COUNT(*) AS numbers
  FROM Sales.Orders
  GROUP BY YEAR(orderdate)
)
SELECT orderyear, numbers
FROM OrdCount;
```

回想嵌套派生表的示例。这里是使用 CTE 的替代方案：

```sql
WITH C1 AS
(
  SELECT YEAR(orderdate) AS orderyear, custid
  FROM Sales.Orders
),
C2 AS
(
  SELECT orderyear, COUNT(DISTINCT custid) AS numcounts
  FROM C1
  GROUP BY orderyear
)
SELECT orderyear, numcounts
FROM C2
WHERE numcounts > 70;
```

如你所示，在同一个 `WITH` 语句中，你可以定义多个用逗号分隔的 CTE。内部查询中的每个引用都指向之前定义的所有 CTE。然后，外部查询可以引用该 `WITH` 语句定义的所有 CTE。这种方法的巧妙之处在于查询不是嵌套的；而是以不间断的方式一个接一个执行。因此，如果你需要理清查询的逻辑，可以从上到下以更自然的顺序进行分析。

在排错带有多个 CTE 的 `WITH` 语句时，我发现有点棘手的地方是：如果你想检查中间 CTE 的结果，不能直接将代码隐藏到该部分并运行。你需要在该 CTE 之后注入一个 `SELECT * FROM <ctename>`，然后运行代码到该部分。派生表在这优势在于，在不更改任何代码的情况下，你可以突出显示针对派生表的查询（包括你想要测试的所有单元）并运行。

从物理处理的角度来看，CTE 的处理方式与派生表相同。内部查询的结果不会持久化在任何地方；而是被内联了。这段代码生成的计划与图 3-9 中之前所示的派生表计划相同。

使用 CTE 替代派生表的另一个优势是，由于你可以在引用 CTE 之前对其进行命名，因此你允许在外部查询中多次引用该 CTE 名称，而无需重复代码。回想之前的示例，它使用了两个相同的派生表副本来返回年度订单数以及上年度订单数的差值。这里是基于 CTE 的替代方案：

```sql
WITH OrderCount AS
(
  SELECT
    YEAR(orderdate) AS orderyear,
    COUNT(*) AS numorders
  FROM Sales.Orders
  GROUP BY YEAR(orderdate)
)
SELECT CUR.orderyear, CUR.numorders,
       CUR.numorders - PRV.numorders diff
FROM OrderCount AS CUR
LEFT OUTER JOIN OrderCount AS PRV
ON CUR.orderyear = PRV.orderyear + 1;
```

显然，这是一种更好的设计。

注意，SQL Server 不会在任何地方持久化表表达式的结果，无论对表名的所有引用是否都会展开为所使用的表或 CTE。这在图 3-10 所示的计划中可以清楚看到。

![](img/bdc38aa36f6e2987d913ee5381474711_233_0.png)

图 3-10 多次引用导致执行两次的工作。

你可以看到工作执行了两次。扫描了 Orders 表上的覆盖索引，然后对行进行了排序和聚合。如果该表很大，且你想避免每次都重复这些操作，应该考虑使用临时表或表变量。

### 递归 CTE

T-SQL 支持带有递归语法的特殊形式 CTE。为了描述和演示递归 CTE，我将使用一个 `Employees` 表，你可以通过运行以下代码创建并填充它：

```sql
SET NOCOUNT ON
USE tempdb;
IF OBJECT_ID(N'dbo.Employees', N'U') IS NOT NULL DROP TABLE dbo.Employees;
CREATE TABLE dbo.Employees
(
  empid INT NOT NULL,
  CONSTRAINT PK_Employees PRIMARY KEY,
  mrid INT NULL,
  CONSTRAINT FK_Employees_Employees FOREIGN KEY REFERENCES dbo.Employees(empid),
  epname VARCHAR(25) NOT NULL,
  salary MONEY NOT NULL
);
INSERT INTO dbo.Employees(empid, mrid, epname, salary)
VALUES(1, NULL, 'David', 10000.00),
(2, 1, 'Eitan', 7000.00),
(3, 1, 'Ina', 7500.00),
(4, 2, 'Seraph', 5000.00),
(5, 2, 'Jiru', 5500.00),
(6, 2, 'Steve', 4500.00),
(7, 3, 'Aaron', 5000.00),
(8, 5, 'Lilach', 3500.00),
(9, 7, 'Rita', 3000.00),
(10, 5, 'Sean', 3000.00),
(11, 7, 'Gabriel', 3000.00),
(12, 9, 'Emilia', 2000.00),
(13, 9, 'Michael', 2000.00),
(14, 9, 'Didi', 1500.00);
```

```sql
CREATE UNIQUE INDEX idx_nc_mgr_emp_i_name_sal
ON dbo.Employees(mrid, empid) INCLUDE (empname, salary);
```

递归 CTE 有一个包含锚点成员和递归成员的主体。锚点成员执行一次，递归成员重复执行直到没有结果为止。以下代码是递归 CTE 的示例：

```sql
WITH RecursiveCTE AS
(
  SELECT empid, mrid, empname, salary
  FROM Employees
  WHERE mrid IS NULL
  UNION ALL
  SELECT e.empid, e.mrid, e.empname, e.salary
  FROM Employees e
  INNER JOIN RecursiveCTE r ON e.mrid = r.empid
)
SELECT * FROM RecursiveCTE;
```

这是该查询的输出：

| empid | mrid | empname | salary |
|---|---|---|---|
| 1 | NULL | David | 10000.00 |
| 2 | 1 | Eitan | 7000.00 |
| 3 | 1 | Ina | 7500.00 |
| 4 | 2 | Seraph | 5000.00 |
| 5 | 2 | Jiru | 5500.00 |
| 6 | 2 | Steve | 4500.00 |
| 7 | 3 | Aaron | 5000.00 |
| 8 | 5 | Lilach | 3500.00 |
| 9 | 7 | Rita | 3000.00 |
| 10 | 5 | Sean | 3000.00 |
| 11 | 7 | Gabriel | 3000.00 |
| 12 | 9 | Emilia | 2000.00 |
| 13 | 9 | Michael | 2000.00 |
| 14 | 9 | Didi | 1500.00 |

该查询的执行计划如图 3-11 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_235_0.png)

图 3-11 递归查询的计划。

计划创建了一个 B 树工作表（索引转储）来存储中间结果。计划在聚集索引上执行搜索以获取下一层的员工，并将其写入转储。计划记录递归成员执行的次数。它通过使用 `Compute Scalar` 算子来实现。第一个初始化变量为 0，第二个将变量加 1。`Assert` 算子在计数器大于 100 时会导致失败。换言之，默认情况下递归成员允许运行 100 次。你可以通过名为 `MAXRECURSION` 的查询选项将默认值更改为你想要设置的限制。要移除限制，将其设置为 0。

这些视图存储在数据库中，因此具有相应权限的用户可以重复使用。存储在数据库中的是查询定义和元数据信息，而不是数据本身（前面提到的索引视图除外）。当对表表达式提交查询或修改时，SQL Server 会内联该表表达式，并将查询或修改应用到底层对象。

例如，假设你的组织有不同的分支。让美国分机构的用户只能与美国的客户进行交互。SQL Server 对行级权限提供了内置支持。因此，你创建了如下视图，它查询 `Customers` 表并仅过滤出来自美国的客户：

```sql
USE TSQLV;
IF OBJECT_ID('Sales.USACusts', 'V') IS NOT NULL DROP VIEW Sales.USACusts;
GO
CREATE VIEW Sales.USACusts WITH SCHEMABINDING
AS
SELECT custid, companyname, contactname, contacttitle, address,
       city, region, country, phone, fax
FROM Sales.Customers
WHERE country = N'USA'
WITH CHECK OPTION;
```

你授予美国分支用户对该视图的权限，而不是对底层表的权限。

`SCHEMABINDING` 选项防止对引用的对象和列进行结构性更改。此选项要求使用架构模式的对象并显式列出列列表（不能使用 `*`）。`CHECK OPTION` 确保对视图的修改如果违反了内部查询的过滤条件将被拒绝。例如，使用此选项后，你将不允许通过视图插入一个来自英国的客户。你也不允许通过视图将国家/地区更新为美国以外的任何地区。

现在你查询该视图，你只与美国的客户进行交互，如下例所示：

```sql
SELECT custid, companyname
FROM Sales.USACusts
ORDER BY region, city;
```

如所述，SQL Server 在幕后会内联内部查询，因此你得到的执行计划与执行以下查询得到的计划是相同的：

```sql
SELECT custid, companyname
FROM Sales.Customers
WHERE country = N'USA'
ORDER BY region, city;
```

注意，尽管视图的内部查询被包含了，但有时即使你直觉上认为可以避免，SQL Server 仍然无法避免某些工作。考虑这样一个例子：你对一个宽表进行垂直分区，在每个较窄的表中存储键以及原始列的不同子集。然后你使用视图来连接这些表，使其看起来像一个关系。使用视图为这种这种安排创建一个基础示例：

```sql
IF OBJECT_ID('dbo.V', 'V') IS NOT NULL DROP VIEW dbo.V;
IF OBJECT_ID('dbo.T3', 'U') IS NOT NULL DROP TABLE dbo.T3;
IF OBJECT_ID('dbo.T2', 'U') IS NOT NULL DROP TABLE dbo.T2;
IF OBJECT_ID('dbo.T1', 'U') IS NOT NULL DROP TABLE dbo.T1;
GO
```

```sql
CREATE TABLE dbo.T1
(
  keycol INT NOT NULL CONSTRAINT PK_T1 PRIMARY KEY,
  col1 INT NOT NULL
);
```

```sql
CREATE TABLE dbo.T2
(
  keycol INT NOT NULL
  CONSTRAINT PK_T2 PRIMARY KEY
  CONSTRAINT FK_T2_T1 REFERENCES dbo.T1,
  col2 INT NOT NULL
);
```

```sql
CREATE TABLE dbo.T3
(
  keycol INT NOT NULL
  CONSTRAINT PK_T3 PRIMARY KEY
  CONSTRAINT FK_T3_T1 REFERENCES dbo.T1,
  col3 INT NOT NULL
);
GO
```

```sql
CREATE VIEW dbo.V WITH SCHEMABINDING
AS
SELECT T1.keycol, T1.col1, T2.col2, T3.col3
FROM dbo.T1
INNER JOIN dbo.T2
ON T1.keycol = T2.keycol
INNER JOIN dbo.T3
```



# 视图与连接优化

注意，我在这里并不讨论这是一种好设计还是坏设计——我只是试图解释针对表表达式的代码优化是如何工作的。假设你知道所有表之间存在一对一的关系。一个表中的每一行在其他每个表中都恰好有一个匹配的行。你对视图执行查询，请求源自其中一个表的列：

```sql
SELECT keycol, col1 FROM dbo.V;
```

有些人直觉上认为优化器应该足够智能，能够知道只需要访问 T1。问题在于 SQL Server 并不知道你所知道的——即表与表之间一对一的关系。对于 SQL Server 而言，T1 中的某些行可能在其他表中没有相关的行，因此不应返回。此外，T1 中的某些行在其他表中可能有多个相关行，因此应该被返回多次。换句话说，优化器必须创建一个连接 T1 与 T2、T3 的计划，如图 3-12 所示。

![图 3-12 显示了对所有表的访问](img/bdc38aa36f6e2987d913ee5381474711_238_0.png)

为了只访问 T1 获取你需要的内容，必须直接查询 T1 而不是通过视图。我使用这个例子是为了强调，有时视图并不是最好的工具。（注意：这里的 OCR 文本是碎片化的，但上下文有助于澄清“不是最好的工具”）。

# 高性能数字生成方案

为了获得高性能的解决方案，我依赖于三个关键点：

- 通过交叉连接（`cross joins`）生成大量行
- 在不排序的情况下高效地生成行号
- 当达到请求行数时，使用 `TOP` 进行短路处理（`short-circuiting`）

第一步是生成大量行。行中包含什么并不重要，因为你最终将使用 `ROW_NUMBER` 函数生成数字。在 T-SQL 中，生成大量行的一种极方法是应用交叉连接。但你需要一个至少包含两行的表作为起点。你可以使用 `VALUES` 子句创建一个这样的虚拟表，如下：

```sql
SELECT c FROM (VALUES(1),(1)) AS D(c);
```

该查询生成了如下输出，显示虚拟表有两行：

```text
c
-------
1
1
```

下一步是基于上一个查询定义一个 CTE（称之为 L0，代表 level 0，即 0），并在两个 L0 实例之间应用自交叉连接以获取四行，如下：

```sql
WITH
L0 AS (SELECT c FROM (VALUES(1),(1)) AS D(c))
SELECT 1 AS c FROM L0 AS A CROSS JOIN L0 AS B;
```

该查询生成了如下输出：

```text
c
-------
1
1
1
1
```

下一步是基于上一个查询定义一个名为 L1 的 CTE，然后连接两个 L1 实例以获取 16 行。重复这种模式，当你到达 L5 时，你可能已经拥有 4,294,967,296 行！以下是计算该数字的表达式：

```sql
SELECT POWER(POWER(2,1),POWER(2, 5));
```

下一步是查询 L5 并计算行号（列命名为 `rownum`），同时不触发排序操作。这是通过指定 `ORDER BY (SELECT NULL)` 实现的。你根据此查询创建一个名为 `Bases` 的 CTE。

最后，下一步是查询 N，并使用 `TOP` 选项过滤 `@high - @low + 1` 行，并按 `rownum` 排序。你计算结果列（命名为 `n`）为 `@low + @rownum - 1`。

以下是应用于示例输入范围 11 到 20 的完整解决方案：

```sql
DECLARE @low AS BIGINT = 11, @high AS BIGINT = 20;

WITH
L0 AS (SELECT c FROM (VALUES(1),(1)) AS D(c)),
L1 AS (SELECT 1 AS c FROM L0 AS A CROSS JOIN L0 AS B),
L2 AS (SELECT 1 AS c FROM L1 AS A CROSS JOIN L1 AS B),
L3 AS (SELECT 1 AS c FROM L2 AS A CROSS JOIN L2 AS B),
L4 AS (SELECT 1 AS c FROM L3 AS A CROSS JOIN L3 AS B),
L5 AS (SELECT 1 AS c FROM L4 AS A CROSS JOIN L4 AS B),
Nums AS (SELECT ROW_NUMBER() OVER(ORDER BY (SELECT NULL)) AS rownum FROM L5)
SELECT TOP(@high - @low + 1) @low + rownum - 1 AS n
FROM Nums
ORDER BY rownum;
```

此代码生成了如下输出：

```text
11
12
13
14
15
16
17
18
19
20
```

为了可复用性，将解决方案封装在一个名为 `GetNums` 的内联 TVF 中，如下：

```sql
IF OBJECT_ID('dbo.GetNums', 'IF') IS NOT NULL DROP FUNCTION dbo.GetNums;
GO

CREATE FUNCTION dbo.GetNums(@low AS BIGINT, @high AS BIGINT) RETURNS TABLE
AS
RETURN
WITH
L0 AS (SELECT c FROM (VALUES(1),(1)) AS D(c)),
L1 AS (SELECT 1 AS c FROM L0 AS A CROSS JOIN L0 AS B),
L2 AS (SELECT 1 AS c FROM L1 AS A CROSS JOIN L1 AS B),
L3 AS (SELECT 1 AS c FROM L2 AS A CROSS JOIN L2 AS B),
L4 AS (SELECT 1 AS c FROM L3 AS A CROSS JOIN L3 AS B),
L5 AS (SELECT 1 AS c FROM L4 AS A CROSS JOIN L4 AS B),
Nums AS (SELECT ROW_NUMBER() OVER(ORDER BY (SELECT NULL)) AS rownum FROM L5)
SELECT TOP(@high - @low + 1) @low + rownum - 1 AS n
FROM Nums
ORDER BY rownum;
GO
```

使用以下代码测试该函数：

```sql
SELECT n FROM dbo.GetNums(11,20);
```

我的朋友 Laurent Martin 将此称为“竖琴函数”（harp function）。这个绰号可能看起来很奇怪，直到你查看图 3-13 所示的查询计划。

![图 3-13 竖琴函数查询计划](img/bdc38aa36f6e2987d913ee5381474711_242_0.png)

该计划的巧妙之处在于，`Top` 运算符会在右侧分支请求行时立即请求行，并且一旦达到请求的行数就会进行短路。分别处理行号计算和交叉连接的 `Sequence Project` 算子和 `Nested Loops` 算子会响应来自 `Top` 算子的行请求。一旦 `Top` 算子停止请求，它们就会停止生成行。换句话说，尽管这个解决方案可以生成超过四亿行，但在实践中它只生成请求的行数。

# OUTER APPLY 操作符

`CROSS APPLY` 运算符与内连接（`inner join`）有一个共同点，它们都会忽略右侧没有匹配的行。因此，在之前的查询中，没有下订单的客户被丢弃了。类似于左外连接（`left outer join`）运算符会保留所有左侧行一样，还有一个 `OUTER APPLY` 运算符也能保留所有左侧行。对于外连接中，它会返回 `NULL` 作为右侧未匹配项的占位符。

例如，为了修改上一个查询以保留所有客户，可以将 `CROSS APPLY` 替换为 `OUTER APPLY`，如下：

```sql
SELECT C.custid, A.orderid, A.orderdate, A.empid
FROM Sales.Customers AS C
OUTER APPLY dbt.GetTopOrders(C.custid, 3) AS A;
```

这样，输出就包含了没有下单的客户：

| custid | orderid | orderdate | empid |
|---|---|---|---|
| 1 | 11011 | 2015-04-09 | 3 |
| 1 | 10952 | 2015-03-16 | 1 |
| 1 | 10835 | 2015-01-15 | 1 |
| 2 | 10926 | 2015-03-04 | 4 |
| 2 | 10759 | 2014-11-28 | 3 |
| 2 | 10625 | 2014-08-08 | 3 |
| ... | ... | ... | ... |
| 22 | NULL | NULL | NULL |
| 57 | NULL | NULL | NULL |
| 58 | 11073 | 2015-05-05 | 2 |
| 58 | 10995 | 2015-04-02 | 1 |
| 58 | 10502 | 2014-04-10 | 2 |

如前所述，SQL 中对应 T-SQL 特有的 `APPLY` 运算符的语法被称为侧向衍生表（`lateral derived table`）。我在上一节中描述了与 `CROSS APPLY` 运算符对应的语法。至于对应 `OUTER APPLY`（在 T-SQL 中表示为 `T1 OUTER APPLY (SELECT ... FROM T2 WHERE T2.col1 = T1.col1) AS Q`），在 SQL 中表示为 `T1 LEFT OUTER JOIN LATERAL (SELECT ... FROM T2 WHERE T2.col1 = T1.col1) AS Q ON 1 = 1`。

# 隐式 APPLY

文档记录的 `APPLY` 运算符变体是上述的 `CROSS APPLY` 和 `OUTER APPLY`。还有另一种变体涉及类似于使用显式 `APPLY` 运算符时的操作，但在代码中未使用 `APPLY` 关键字。我将这种变体称为隐式 `APPLY`。隐式 `APPLY` 涉及使用子查询，并在子查询内部查询表函数，并将外部表的列作为输入传递给它。通过示例来解释最为清楚。

考虑你在之前的章节中使用的 `GetTopOrders` 函数，它为请求的客户返回指定数量的最新订单。假设你想为 `Customers` 表中的每个客户计算处理该客户最近 10 笔订单的员工去重计数。你想复用封装在 `GetTopOrders` 函数中的逻辑，因此你执行了以下操作：查询 `Customers` 表；使用子查询将函数应用于外部客户以返回其最近的 10 笔订单；最后，计算处理这些订单的员工去重计数。以下是该逻辑在 T-SQL 中的实现。

```sql
SELECT C.custid,
  (SELECT COUNT(DISTINCT empid) FROM dbo.GetTopOrders(C.custid, 10)) AS numemps
FROM Sales.Customers AS C;
```

注意，现在没有显式提到 `APPLY` 关键字，但显然子查询中的代码将表函数应用到了每个外部客户。这段代码生成了以下输出：

```text
custid  numemps
----    ------
1       4
2       3
3       4
4       4
5       6
6       5
7       6
8       2
9       7
11      7
```

很容易看出为什么这里使用隐式 `APPLY` 术语是合适的。有趣的是，在显式 `APPLY` 运算符添加到 SQL Server 之前，你也无法使用隐式 `APPLY` 功能。换句话说，隐式功能的添加归功于显式运算符的引入。

# 列别名的复用

正如第 1 章讨论的，SQL 令人烦恼的问题之一是如果你在查询的 `SELECT` 子句中定义了列别名，在大多数查询子句中不允许引用。例外是 `ORDER BY` 子句，因为它是逻辑上在 `SELECT` 子句之后评估的唯一子句。

在使用 `APPLY` 运算符时有一个优雅的技巧可以解决这个问题。记住 `APPLY` 是一个表运算符，而表运算符是在查询的 `FROM` 子句中评估的。因为 `FROM` 子句是逻辑上第一个被评估的子句，你在其中创建的任何别名对查询的其他部分可见。由于每个表运算符都会启动一个新的逻辑查询处理步骤，由一个表运算符定义的别名对后续的表运算符也是可见的。

考虑到这一点，使用 `APPLY` 运算符可以应用一个衍生表，为左侧表的表达式定义别名。该衍生表可以基于...

# 连接语法与优化

作为过滤谓词的角色。前者定义了连接中非保留侧的哪些行与保留侧的行匹配，后者则被用作基本过滤器，并且确实可以丢弃两侧的行。

SQL 标准委员会决定在 SQL-92 标准中添加了外连接；他们认为传统的基于逗号的语法不适用于这种新类型的连接。这是因为这种语法不允许你将匹配谓词作为表操作符的一部分来定义，而前面提到的匹配谓词本应该扮演与你在 `WHERE` 子句中指定的过滤谓词不同的不同的角色。因此，他们最终创建了带有 `JOIN` 关键字的新语法，并带有指定的 `ON` 子句，在其中指定匹配谓词。这种带有 `JOIN` 关键字的新语法通常被称为 SQL-92 语法，而旧的基于逗号的语法被称为 SQL-89 语法。

为了让不同类型的连接具有一致的编码风格，SQL-92 标准还增加了对交叉连接和内连接的 `JOIN` 关键字语法的支持。这段历史解释了为什么我们现在对内连接有两种语法，而对外连接只有一种语法。强烈建议你在范围内坚持使用基于 `JOIN` 关键字的语法。原因之一是它产生了一种一致的风格，比混合风格易于维护得多。此外，基于逗号的语法更容易出错，正如我将在讨论内连接时将演示的那样。

我将演示几个内连接的用例。其中一个是生成示例数据，另一个是规避与子查询相关的优化问题。

假设你需要生成代表订单 ID 的示例数据，这些订单在特定日期、由特定客户下单，并由特定员工处理。随着你进入订单日期范围以及需要支持的客户和员工数量范围。使用数据库中的 `GetNums` 函数，你可以生成日期、客户 ID 和员工 ID 的集合。你对这些集合执行交叉连接，以获取所有可能的组合，并使用 `ROW_NUMBER` 函数计算订单 ID，如下：

```sql
DECLARE @date AS DATE = '20150131', @numemps AS INT = 50;

SELECT ROW_NUMBER() OVER(ORDER BY (SELECT NULL)) AS orderid,
       DATEADD(day, D.n, @date) AS orderdate, C.n AS custid, E.n AS empid
FROM dbo.GetNums(0, DATEDIFF(day, @date, '20151231')) AS D
CROSS JOIN dbo.GetNums(1, @numemps) AS C
CROSS JOIN dbo.GetNums(1, @numemps) AS E;
```

`ROW_NUMBER` 函数中不寻常的 `ORDER BY (SELECT NULL)` 是通过任意顺序计算行数的技巧。当我需要生成唯一值且不在乎它们的生成顺序时，我会使用这种方法。

请注意，当你生成示例数据时，你需要更符合实际的数据分布。在现实中，你通常不会拥有均匀分布的订单日期、客户 ID 和员工 ID。有时你为了某些测试需要非常基础的示例数据，这种简单技术对你来说就足够了。

# 第 3 章 多表查询

交叉连接的另一个用例与 SQL Server 中关于子查询的优化缺陷有关。考虑以下查询：

```sql
SELECT orderid, val,
       val / (SELECT SUM(val) FROM Sales.OrderValues) AS pct,
       val - (SELECT AVG(val) FROM Sales.OrderValues) AS diff
FROM Sales.OrderValues;
```

该查询针对 `OrderValues` 视图发出的。它返回每个订单的总体值占总计的百分比，以及与总平均值的差值。总计和总平均值是通过标量子查询计算的。确实，该查询引用了三次 `OrderValues` 视图，显然两个子查询都需要在完全的值集上进行操作。遗憾的是，优化器中没有逻辑可以避免通过匹配所有子查询到一个相同的值来产生重复工作。在我们情况下，问题被放大了，因为 `OrderValues` 是一个视图。它连接了 `Orders` 和 `Details` 表，并对数据进行聚合以产生订单级信息。所有这些在执行计划中都重复了三次，如图 3 所示：

![执行计划显示重复访问](img/bdc8aa36f6e2987d91ee53814741250.png)

（注：原文后续部分存在大量重复的碎片和错乱的描述，已根据指令剔除冗余。）

```sql
INNER JOIN T3
ON T3.col12 = T2.col12
INNER JOIN T4
ON T4.col13 = T3.col13
```

使用这种语法，你漏掉连接谓词的概率很低，即使漏掉了，解析器也会生成错误，因为在内连接（以及外连接）中，`ON` 子句是强制性的。相反，使用 SQL-89 语法，你在 `FROM` 子句中用逗号指定所有表名，而所有谓词都是 `WHERE` 子句中的合取词，如下所示：

```sql
FROM T1, T2, T3, T4
WHERE T2.col11 = T3.col11 AND T3.col12 = T2.col12 AND T4.col13 = T3.col13
```



显然，你误漏连接的概率更高，如果真的漏了，最终将导致无意的交叉连接。

一个常见的问题是，使用 `INNER JOIN` 关键字和直接使用 `JOIN` 之间是否存在区别。没有区别。标准 SQL 将内连接设为默认值，因为它可能是最常用的连接类型。类似地，标准 SQL 在外连接中使关键字 `OUTER` 变为可选的。例如，`LEFT OUTER JOIN` 和 `LEFT JOIN` 是等价的。关于推荐用法，倾向于使用完整语法以使其表述清晰；其他人则倾向于使用省略语法，因为这样代码更短。我认为，比起使用完整语法还是省略语法更重要的，是开发团队成员之间保持一致。当不同的人使用不同的风格时，维护彼此的代码会变得很困难。一个主意是开会讨论风格（如完整语法与省略语法对比、缩进、大小写等），并制定一份每个人都必须遵守的编码风格文档。有时人们根据个人偏好对某些样式方面有强烈的见解，因此当发生冲突时，可以通过投票来决定哪种方案占优。一旦大家都开始使用一致的风格，维护相同的代码就会变得容易得多。

## 外连接

从逻辑查询处理的角度来看，外连接的起始步骤与内连接相同。但此外，它们有一个第三个逻辑步骤，确保你标记为“保留”的表中的行会被返回，即使根据连接谓词，这些行在另一个表中没有任何匹配。通过使用关键字 `LEFT`（或 `LEFT OUTER`）、`RIGHT` 或 `FULL`，你可以将左表、右表或两个表都标记为保留。输出的匹配行（作为外连接）在非保留侧的列中具有 `NULL`。

例如，以下查询返回了客户及其订单，包括没有订单的客户：

```sql
SELECT C.custid, C.companyname, C.country,
O.orderid, O.shipcountry
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = O.custid;
```

在外连接中，`ON` 子句中谓词的作用与内连接不同。在后者中，它充当简单的过滤工具，而在外连接中，它充当了更复杂的匹配工具。无论保留侧的行是否根据谓词找到了匹配行，所有行都将被返回。如果你需要应用任何简单的过滤，请在 `WHERE` 子句中指定。例如，识别所有非匹配项的经典方法是使用外连接并添加一个 `WHERE` 子句，过滤掉非保留侧某个不允许 `NULL` 的列中为 `NULL` 的行。主键列是此目的的良好选择。例如，以下查询仅返回下过订单的客户：

```sql
SELECT C.custid, C.companyname, O.orderid
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = O.custid
WHERE O.orderid IS NULL;
```

人们使用左外连接比使用右外连接要常见得多。这可能是因为大多数人倾向于在查询中引用之前先看到被引用的表，通常被引用的表是与引用表中没有匹配项的表。在简单情况下（如 `T1 LEFT OUTER JOIN T2`），这是确实的，因为你可以用对称的 `T2 RIGHT OUTER JOIN T1` 相同的内容。然而，在涉及多个连接的更复杂的情况下，你会发现右外连接比使用左外连接能提供更简单的解决方案。我将在“多查询查询”部分很快演示此类情况。

## 自连接

自连接是同一张表的多个实例之间的连接。例如，以下查询将员工与其经理（经理也是员工）进行匹配：

```sql
SELECT E.firstname + ' ' + E.lastname AS emp, M.firstname + ' ' + M.lastname AS Mgr
FROM HR.Employees AS E
LEFT OUTER JOIN HR.Employees AS M
ON E.mgrid = M.empid;
```

自连接的特殊之处在于，必须为表的实例设置不同的别名；否则你将得到重复的列名，包括表前缀。

从优化的角度来看，优化器将这两个实例视为两个不同的表。例如，它可以为每个实例使用不同的索引。在查询计划中，你可以通过分配的表别名来识别每个物理对象代表表上的哪个实例。

## 等值连接与非等值连接

等值连接和非等值连接术指的是你在连接谓词使用的运算符类型。当你使用相等运算符时（如绝大多数查询所示），它被称为等值连接。当你使用相等运算符以外的运算符时，该连接被称为非等值连接。

## 连接顺序

有许多原因可能导致优化器选择次优的连接顺序。与其他次优选择一样，连接顺序可能会受到不准确的基数估计的影响。

此外，即使表的数量较少，可能的连接顺序（或称连接树）的理论数量也可能是巨大的。Benjamin Nevarez 在此处的“优化连接顺序”中解释了这一点：http://www.beninezvarez.com/2010/06/optimizing-join-orders/。对于 N 张表，可能的树的数量为 (2N-2)! / (N-1)!，其中 `!` 是阶乘。在一个例子中，如果我们有 5 张表，则会产生 1,680 种可能的树。对于 N 张表，该数量是 17,643,225,600! 这里的 `!` 表示惊讶，而不是表示阶乘，谢天谢地。正如你可能意识到的，如果优化器真的尝试探索所有可能的连接树，优化过程将花费太长时间，并且适得其反。优化器做了许多工作来缩短优化时间。它根据表的大小使用基于成本和时间的阈值，如果达到其中一个阈值，就会停止优化。优化器通常不考虑丛状连接树（bushy join trees，即连接的结果之间再次进行连接）；此类树代表了大部分等待时间。这就是为什么优化器可能无法得出真正的最优连接顺序的原因。

如果你怀疑情况如此并想强制优化器使用特定顺序，你可以按照你认为最优的顺序输入连接，并使用 `FORCE ORDER` 查询，如下所示：

```sql
SELECT DISTINCT C.companyname AS customer, S.company AS supplier
FROM Sales.Customers AS C
INNER JOIN Sales.Orders AS O
ON O.custid = C.custid
INNER JOIN Sales.OrderDetails AS OD
ON OD.orderid = O.orderid
INNER JOIN Production.Products AS P
ON P.product = OD.product
INNER JOIN Production.Suppliers AS S
ON S.supplierid = P.supplierid
OPTION (FORCE ORDER);
```

这被清楚地提示为一种你可以使用的故障排除工具，用它来测试不同顺序的性能，并在优化器有需要时让它做出次优选择。在生产代码中使用此类提示的问题是，它使优化的这部分变成了静态。通常情况下，更改索引、数据特征和其他因素可能会导致优化器连接顺序选择的改变，但当使用提示时显然不会。该提示很好地作为故障排除工具，有时也可以作为生产环境中关键情况下的短期、临时解决方案。然而，它通常不适合作为长期解决方案。例如，假设导致次优连接顺序选择的原因是糟糕的基数估计。当你有时间对问题进行彻底研究时，我希望你能够找到帮助优化器得出更准确估计的方法，从而自然地产生更优的计划。

## 控制逻辑连接评估顺序

你刚刚学会了如何控制物理连接顺序。在某些情况下，你需要控制逻辑连接顺序，以实现查询含义的特定更改。例如，考虑上一节中返回客户-供应商对的查询：

```sql
SELECT DISTINCT C.companyname AS customer, S.companyname AS supplier
FROM Sales.Customers AS C
INNER JOIN Sales.Orders AS O
ON C.custid = C.custid
INNER JOIN Sales.OrderDetails AS OD
ON OD.orderid = O.orderid
INNER JOIN Production.Products AS P
ON OD.productid = P.productid
INNER JOIN Production.Suppliers AS S
ON S.supplierid = P.supplierid;
```

此查询返回 1,236 行。查询中的所有连接都是内连接。这意味着没有下任何订单的客户不会被返回。在我们的样本数据中有两个这样的客户。假设你需要更改解决方案以包含没有订单的客户。直观的做法是将 `Customers` 和 `Orders` 之间的连接类型改为左外连接，如下所示：

```sql
SELECT DISTINCT C.companyname AS customer, S.companyname AS supplier
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = C.custid
INNER JOIN Sales.OrderDetails AS OD
ON OD.orderid = O.orderid
INNER JOIN Production.Products AS P
ON OD.productid = P.productid
INNER JOIN Production.Suppliers AS S
ON S.supplierid = P.supplierid;
```

然而，如果你运行该查询，你会发现它返回的结果与之前相同。同样，`Customers` 和 `Orders` 之间的左外连接返回了两个没有下订单的客户，其订单属性中为 `NULL`。当使用内连接将结果与 `OrderDetails` 连接时，这些行被消除了。这就是为什么在比较具有任何 `OD.orderid` 值的行中 `Order.order` 列的 `NULL` 标记时，结果值未知未知。你可以将其推广并说，任何随后跟随内连接或右外连接的左外连接都会导致该左外连接变成内连接。这是假设你正在将左外连接保留侧的 `NULL` 元素与另一个表的元素进行比较。事实上，如果你查看查询的执行计划，你会发现优化器确实将左外连接转换为了内连接。

人们尝试解决此问题的常用方法是将所有连接都变为左外连接，如下：

```sql
SELECT DISTINCT C.companyname AS customer, S.companyname AS supplier
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = C.custid
LEFT OUTER JOIN Sales.OrderDetails AS OD
ON OD.orderid = O.orderid
LEFT OUTER JOIN Production.Products AS P
ON OD.productid = P.productid
LEFT OUTER JOIN Production.Suppliers AS S
ON S.supplierid = P.supplierid;
```

![](img/bdc38aa36f6e2987d913ee5381474711_261_0.png)

3-18 丛状计划。

观察到计划中实现了所需的丛状布局。

## 半连接与反半连接

通常情况下，连接会匹配两个表中的行并返回双方的元素。半连接与普通连接的区别在于，它只返回其中一侧的元素。你返回元素的一侧决定了它是左半连接还是右半连接。

例如，考虑一个请求：返回下过订单的客户 ID 和公司名称。只要在 Orders 表中找到了匹配的行，你就只返回 Customers 表中的信息。将 Customers 视为左表，该操作就是左半连接。实现此任务有许多方法。其中一种是使用内连接并应用 `DISTINCT` 子句来删除重复信息，如下：

```sql
SELECT DISTINCT C.custid, C.companyname
FROM Sales.Customers AS C
INNER JOIN Sales.Orders AS O
ON C.custid = C.custid;
```

另一种方法是使用 `EXISTS` 谓词，如下：

```sql
SELECT custid, companyname
FROM Sales.Customers AS C
WHERE EXISTS(SELECT *
    FROM Sales.Orders AS O
    WHERE O.custid = C.custid);
```

这两个查询得到的执行计划是相同的。当然，实现此任务还有其他方法。

反半连接是指：如果在相关表中无法找到匹配的行，则返回其中一个表中的元素。同样，取决于你返回的是左表还是右表的信息，该连接可以是左反半连接或右反半连接。例如，返回未下订单的客户的请求可以通过左反半连接操作来实现。

实现这种反半连接有许多经典方法。一种是在 Customers 和 Orders 之间使用左外连接，并过滤出仅外行，如下：

```sql
SELECT custid, C.companyname
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON O.custid = C.custid
WHERE O.orderid IS NULL;
```

另一种是使用 `NOT EXISTS` 谓词，如下：

```sql
SELECT custid, companyname
FROM Sales.Customers AS C
WHERE NOT EXISTS (
    FROM Sales.Orders AS O
WHERE O.custid = C.custid);
```

奇怪的是，目前优化器似乎没有逻辑来检测外连接正在应用于反半连接，但在使用 `NOT EXISTS` 解决方案时可以。这从图 3-19 所示的这些查询执行计划中可以看出。

查询 1：查询成本（相对于批处理）：52%
SELECT C.custid, C.companyname FROM Sales.Customers AS C LEFT OUTER JOIN Sales.Orders AS O ON O.custid = C.custid

![](img/bdc38aa36f6e2987d913ee5381474711_262_0.png)

查询 2：查询成本（相对于批处理）：48%
SELECT custid, companyname FROM Sales.Customers AS C WHERE NOT EXISTS(SELECT FROM Sales.Orders AS O WHERE ...

![](img/bdc38aa36f6e2987d913ee5381474711_262_1.png)

图 3-19 反半连接解决方案的计划。

当然，实现反半连接还有许多其他方法。我展示的是两种经典方法。

## 连接算法

连接算法是 SQL Server 用于处理连接的物理连接策略。SQL Server 支持三种连接算法：嵌套循环、合并和哈希。嵌套循环是这三种算法中最老的，也是当其他算法无法使用时的备选方案。例如，交叉连接只能通过嵌套循环处理。合并和哈希要求连接是等值连接，更准确地说，至少有一个基于等值运算符的连接谓词。

在图形化查询计划中，每算法连接操作符都有不同的图标。此外，`Physical Operation` 属性标识连接算法（Nested Loops、Hash Map、Merge Join），而 `Logical Operation` 属性标识逻辑连接类型（Inner Join、Left Outer Join、Left Anti Semi Join 等）。此外，物理算法名称出现在操作符正下方，逻辑连接类型出现在算法名称下方的括号中。

接下来的章节将描述各个连接算法、它们倾向于高效的情况以及支持它们的索引指南。

## 嵌套循环

嵌套循环算法非常直观。它只执行外层（顶部）循环一次，并对于外层循环的每一行执行一次内层（底部）输入以识别匹配项。

当外部输入较小且内部输入具有基于连接列（以及任何相关的附加列）的键列表的索引时，嵌套循环性能良好。索引是否为覆盖索引至关重要，取决于总共获得多少匹配项。如果总匹配数很少，几次查找开销不高，索引不需要是覆盖索引。如果匹配数量很大，查找将变得昂贵，此时通过使索引成为覆盖索引来避免查找就至关重要。

例如，考虑以下查询：

```sql
SELECT C.custid, C.custname, O.orderid, O.empid, O.shipperid, O.orderdate
FROM dbo.Customers AS C
INNER JOIN dbo.Orders AS O
ON C.custid = O.custid
WHERE C.companyname LIKE 'Cust_100%'
  AND O.orderdate >= '2014-01-01';
```



目前表没有良好的索引来支持嵌套循环。因为较小的一侧（例中为 `Customers`）通常用外部输入且仅执行一次，所以对其提供良好索引并不十分关键。在最坏的情况下，表会被全扫描。更关键的索引是在较大的一侧（例中为 `Orders`）。然而，如果你想避免全扫描 `Customers` 表，可以为 `lastname` 准备索引并包含 `custid` 列。对于 `Orders` 的理想索引，考虑在单次循环中涉及的工作。由于你有一个等值谓词和一个范围谓词，在这里创建理想索引是简单的：根据 `custid` 和 `orderdate` 定义索引键列表，并包含剩余列（`orderid`, `empid`）。还记得关于多个范围谓词的讨论吗？当你同时拥有等值谓词和范围谓词时，需要先用等值列定义键列表。这样，匹配行将连续出现在索引中。如果你用范围列定义键列表，则不是。运行以下代码为你的查询创建优化索引：

```sql
CREATE INDEX idx_nc_customers ON dbo.Customers(companyname) INCLUDE(custid);

CREATE INDEX idx_nc_orders ON dbo.Orders(custid, orderdate) INCLUDE(orderid, empid, shipperid);
```

现在运行你的查询并检查图 3-20 中的查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_264_0.png)

**图 3-20 嵌套循环算法的计划。**

你可以看到，优化器选择了使用嵌套循环算法，表 `Customers` 作为外部输入，表 `Orders` 作为内部输入。计划在 `Customers` 的覆盖索引上执行搜索和范围扫描以检索匹配的客户（例中为 1 个）。然后，通过循环，计划在 `Orders` 的覆盖索引上执行搜索和范围扫描以检索匹配的订单（总共 3 个）。

接下来，我将讨论查询的不同更改对优化的影响。

如所述，如果总匹配数很少，内部表是否为覆盖索引并非关键。你可以通过在查询的 `SELECT` 列表中添加 `O.filler` 来测试这种情况。计划将仍然使用嵌套循环算法，但会添加查找来检索该列，因为它不是 `idx_nc_orders` 的一部分。测试完成后，在应用下一个更改之前，确保从查询中移除 `O.filler`。

当外部输出返回足够的行时，当优化器估计从外部输出返回几十行时，通常会应用预取。我们当前的查询计划不涉及预取，因为优化器估计 `Customers` 只返回几行。如果你将针对 `Customers` 的过滤从 `C.companyname LIKE 'Cust_1000%'` 更改为 `C.companyname LIKE 'Cust_100%'`，它将使用预取。应用更改后，你会发现嵌套循环操作符有一个属性 `OrderedPrefetch` 为 `True`。它是无序预取的原因是尚未按客户 ID 返回行。如果你在查询中添加 `ORDER BY`，优化器将变为 `OrderedPrefetch`。测试完成后，在应用下一个更改之前确保还原原始查询。

我提到过嵌套循环操作通常用于外部输入较小。将针对 `Customers` 的过滤更改为 `C.companyname LIKE 'Cust_10%'`。现在 `Customers` 的估计匹配数从几行增加到数千，优化器将其连接算法的选择改为哈希。

当计划是并行的但输出只有几行时，优化器可以使用一种有趣的技术。在这种情况下，如果没有优化器的干预，工作将不均匀地分配到不同的线程。因此，当优化器检测到少数行时，它会在从外部输出获取行后添加 `Redistribute Streams` 操作符。该操作在线程之间更均匀地重新分配行。

## 合并

合并算法要求两个输入按连接列排序。它像拉链一样合并两者。如果连接是一对多（大多数查询的情况如此），每个输入只通过一次。如果连接类型是多对多，则一个输入被扫描，而另一个输入回溯。

通常，优化器有两种获取排序输入的方法。如果数据已经在索引中排序好，优化器可以使用索引扫描。另一种方法是在计划中添加显式的排序操作，但这样会有与排序相关的成本。

考虑以下查询作为从索引获取排序数据的示例：

```sql
SELECT C.custid, C.companyname, O.orderid, O.empid, O.shipperid, O.orderdate
FROM dbo.Customers AS C
INNER JOIN dbo.Orders AS O
ON C.custid = O.custid;
```

`Customers` 表上的 `PK_Customers` 索引是以 `custid` 为键定义的聚簇索引。因此，`Customers` 的数据被索引覆盖并为合并连接算法排序。

你为“嵌套循环”部分的示例在 `Orders` 表上创建的非聚聚集索引 `idx_nc_cid_oid_i_eid_sid` 对于合并连接来说是非常好的。它的数据根据前导键 `custid` 进行了排序，并且涵盖了查询中来自 `Orders` 的元素。这些条件对于合并连接算法来说是最优的；优化器使用了这种策略，正如你在图 3-21 所示的查询计划中所看到的。

![](img/bdc38aa36f6e2987d913ee5381474711_266_0.png)

**图 3-21** 使用合并连接算法的计划。

作为一个涉及显式排序的合并连接的示例，考虑以下查询：

```sql
SELECT C.custid, C.custname, O.orderdate, O.empid, O.shipperid, O.orderdate
FROM db.Customers AS C
INNER JOIN db.Orders AS O
ON O.custid = C.custid
WHERE O.orderdate > '20140101'
AND O.orderdate < '20140102';
```

数据可以通过 `Customers` 表上的聚簇索引按 `custid` 获取。然而，由于对 `Orders` 有额外的范围过滤，无法创建一个既主要按 `orderdate` 排序以支持过滤，又按 `custid` 排序以支持合并连接的索引。日期范围过滤具有选择性——只有几百行符合条件的记录。此外，`Orders` 上的聚簇索引是以 `orderdate` 为键定义的。优化器认为它可以使用对 `Orders` 上的聚簇索引进行查找和范围扫描来检索符合条件的订单，然后通过显式排序操作按 `custid` 对行进行排序。由于行数很少，排序成本非常低。我们查询的计划执行了这种策略，正如你在图 3-22 中所示。

![](img/bdc38aa36f6e2987d913ee5381474711_266_1.png)

**图 3-22** 使用排序操作符和合并算法的计划。

观察与排序操作相关的低成本。

请注意，此类计划对导致 `Sort` 算符的活动基数估算的不准确性非常敏感。当估算是少数行而实际是大量行时，情况尤为如此，因为排序的可扩展性并不良好。首先，更准确的估算会导致优化器使用完全不同的连接方式。其次，低估可能导致排序活动内存不足，这可能导致向数据溢出到 `tempdb`。你需要关注此类问题，如果你发现了此类问题，请尝试找到帮助优化器得出更准确估算的方法。

# 哈希

哈希算法涉及根据输入内容之一（通常是规模较小的那一个）创建一个哈希表。选择较小侧作为输入的原因通常是这样内存占用会更小。如果哈希表能够放入内存，那么它是理想的。但如果哈希表可以被分区，分区在内存内和内存外之间的交换会降低算法的效率。输入中的项根据哈希函数排列在哈希桶中。为了说明，假设连接列是一个整数，优化器选择模 50 函数作为哈希函数。将创建多达 50 个哈希桶，所有通过哈希函数得到相同结果的项将组织在同一个桶的链列表中。然后对另一个输入（称为探测输入 `probe input`）进行探测，将哈希函数应用于连接列值，并根据结果，算法扫描哈希桶以查找匹配项。

哈希算法在数据仓库查询中表现出色，这类查询倾向于在事实表中加载大量数据，而在维度表中加载较少的数据。它在查询中扩展性良好，极大受益于并行处理。请注意，哈希表需要内存授予，且该算法对基数估算的不准确性敏感。如果内存授予不足，哈希表将溢出到 `tempdb`，导致处理效率降低。

当使用存储索引时，哈希算法可以使用批量执行模式，这在第 2 章中描述。在 SQL Server 2012 中，只有使用哈希算法的内连接可以使用批量执行。此外，如果优化器溢出到 `tempdb`，则执行模式将切换到行模式。在 SQL Server 2014 中，使用哈希算法的外部连接可以使用批量执行，溢出到 `tempdb` 的算符也是如此。

除了经典的数据仓库查询外，还有另一种优化器倾向于选择哈希算法的案例——当没有良好的索引来支持其他算法时。如果你仔细考虑，哈希表是 B 树的另一种替代搜索结构。当没有良好的索引时，创建一个哈希表、使用它，并在每次查询执行时将其丢弃，通常比在 B 树上执行相同的事情更有效。作为一个示例，运行你之前为支持前面的示例而创建的以下代码：

```sql
DROP INDEX idx_nc_cn_id ON dbo.Customers;

DROP INDEX idx_nc_cid_od_oid_eid_sid ON dbo.Orders;
```

然后运行你之前在“嵌套循环”部分运行的相同查询：

这次，由于缺乏支持嵌套循环算法的高效索引，优化器选择使用基于符合条件的客户的哈希表来执行哈希连接。该查询的计划如图 3-23 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_268_0.png)

**图 3-23** 使用哈希算法的计划。

所以，当你看到优化器在某些不自然的情况下使用哈希连接时，请问问自己是否缺少了索引。

# 强制连接策略

如果你怀疑优化器选择了次优的算法，可以尝试两种方法。一种是在 `JOIN` 关键字之前使用连接提示（`LOOP`、`MERGE` 或 `HASH`）。请注意，使用这种方法，查询中的所有连接都会受到影响。此外，与连接顺序不同，连接提示不会影响连接顺序。如果你想强制连接顺序，需要添加 `FORCE ORDER` 提示。

另一种方法是在 `OPTION` 子句中使用查询提示。这种方法的优点是你可以指定多个算法，例如：

```sql
SELECT C.custid, C.custname, O.orderdate, O.empid, O.shipperid, O.orderdate
FROM db.Customers AS C
  INNER JOIN db.Orders AS O
  ON O.custid = C.custid
WHERE O.orderdate > '20140101'
AND O.orderdate < '20140102'
OPTION(LOOP, HASH);
```

请注意，尽管使用这种方法，你阻止了优化器选择合并算法，但为它留了一些灵活性。

## 分离元素

分离元素是一个经典的 T-SQL 挑战。它涉及一个名为 `Arrays` 的表，其中 `arr` 列包含字符串分隔的值列表。运行以下代码创建 `Arrays` 表并填充示例数据：

```sql
SET NOCOUNT ON;
USE tempdb;
```

```sql
IF OBJECT_ID('dbo.Arrays','N''U') IS NOT NULL DROP TABLE dbo.Arrays;
```

```sql
CREATE TABLE dbo.Arrays
(
  id VARCHAR(10) NOT NULL PRIMARY KEY,
  arr VARCHAR(8000) NOT NULL
);
GO
```

```sql
INSERT INTO dbo.Arrays VALUES('A', '20,223,2544,25567,14');
INSERT INTO dbo.Arrays VALUES('B', '30,-23433,28');
INSERT INTO dbo.Arrays VALUES('C', '12,10,8099,12,1200,13,12,14,10,9');
INSERT INTO dbo.Arrays VALUES('D', '-4,-6,-45678,-2');
```

挑战在于如何给出一个高效的 T-SQL 解决方案，将每个字符串拆分为单个元素，并以单独的行返回，包含 `id`、位置和元素本身。预期的如下所示。

| id | pos | element |
|---|---|---|
| A | 1 | 20 |
| A | 2 | 223 |
| A | 3 | 2544 |
| A | 4 | 25567 |
| A | 5 | 14 |
| B | 1 | 30 |
| B | 2 | -23433 |
| B | 3 | 28 |

注意，使用 .NET 比使用 T-SQL 更高效地完成此任务——可以使用 `System.String.Split` 方法或实现你自己的迭代解决方案。然而，我们的挑战是使用 T-SQL 实现一个高效的解决方案。

一种直观的方法是实现一个迭代解决方案，作为一个表函数，以单个字符串和分隔符作为输入，并返回一个表变量。该函数在每次迭代中提取一个元素并将其插入到结果表中。这种方法的问题在于，T-SQL 中的迭代解决方案通常效率较低。

因此，挑战在于找到一个使用 T-SQL 的高效的基于集合的解决方案。要实现这样的解决方案，你需要将任务分为三个步骤：

1. 生成副本。
2. 提取元素。
3. 计算位置。

第一步是从原始行生成副本——数量与字符串中元素的数量相同。第二步是从每个副本中提取相关元素。第三步是计算元素在字符串中的序数位置。

对于第一步，你将非常方便地使用 `TSQLV3` 数据库中的辅助表 `Nums`。该表有一个名为 `n` 的列，存储了一组从 1 开始的整数。你可以将这些数字看作是字符串中字符的位置。也就是说，`n=1` 代表字符位置，`n=2` 代表字符位置，以此类推。为了生成副本，你连接了 `Arrays` 和 `Nums`。使用以下表达式作为连接谓词，它表示第 `n` 个字符是分隔符：`SUBSTRING(arr, n, 1) = ','`。为了避免提取超出字符串长度的字符，使用谓词 `n <= LEN(arr)` 将数字限制在字符串长度。以下是实现代码：

```sql
SELECT id, arr, n
FROM dbo.Arrays
INNER JOIN TSQLV3.Nums
ON n <= LEN(arr)
AND SUBSTRING(arr, n, 1) = ',';
```



这段代码生成了以下输出：

| id | arr | n |
|---|---|---|
| A | 20,223,2544,2567,14 | 3 |
| A | 20,223,2544,2567,14 | 7 |
| A | 20,223,2544,2567,14 | 12 |
| A | 20,223,2544,2567,14 | 18 |
| B | 30,-24333,28 | 3 |
| B | 30,-24333,28 | 10 |

观察发现输出缺少了每个字符串的副本。对于一个包含 X 个元素的字符串，有 X - 1 个分隔符。如果你考虑元素之前的分隔符，那么漏掉的是第一个元素之前的分隔符。要解决这个问题，只需在字符串开头放置一个分隔符，并将结果作为第一个输入传递给 `SUBSTRING` 函数。此外，确保将提取的字符数量增加一个，以考虑到额外的字符。在这两个修改之后，查询看起来如下：

此查询生成了以下输出：

| id | arr | n |
|---|---|---|
| A | 20,223,2544,2567,14 | 1 |
| A | 20,223,2544,2567,14 | 4 |
| A | 20,223,2544,2567,14 | 8 |
| A | 20,223,2544,2567,14 | 13 |
| A | 20,223,2544,2567,14 | 19 |
| B | 30,-24333,28 | 1 |
| B | 30,-24333,28 | 4 |
| B | 30,-24333,28 | 11 |

这一次，你得到了正确数量的副本。此外，观察到对查询的修改产生了一个副作用；发现分隔符的字符位置增加了，因为字符串向右移动了一位。这个副作用对我们来说非常方便，因为相对于原始字符串（不包含开头的分隔符），`n` 实际上代表了元素的起始位置。任务解决方案的第一步已经完成。

第二步是提取当前副本所报告的元素。为了此，你将使用 `SUBSTRING` 函数。你需要将字符串、起始位置和要提取的长度作为输入。现在元素从位置 `n` 开始。对于长度，你需要找到下一个分隔符的位置，并从中减去 `n`。你可以使用 `CHARINDEX` 函数来实现此目的。前两个输入是你正在查找的分隔符和正在查找的字符串。作为第三个输入，指定 `n` 为分隔符的起始位置。你得到：`CHARINDEX(',', arr, n)`。这里的棘手之处在于最后一个元素之后没有分隔符；在这种情况下，函数返回 0。要解决这个问题，请在字符串末尾添加一个分隔符，例如：`CHARINDEX(',', arr + ',', n)`。任务解决方案的第三个也是最后一步是计算元素在字符串中的序数位置。

后续章节提供了有关这些运算符的更多详细信息。

## UNION ALL 和 UNION 运算符

`UNION` 运算符合并来自两个输入的的行。图 3-24 形象地展示了该运算符的作用。它用较深的背景颜色显示了该操作的结果。

![](img/bdc38aa36f6e2987d913ee5381474711_274_0.png)

图 3-24 `UNION` 运算符。

T-SQL 支持 `UNION` 运算符两种变体：`UNION`（隐含的 `DISTINCT`）和 `UNION ALL`。两者都合并来自两个输入的的行，但只有前者会移除结果中的重复项；后者则不会。标准 SQL 实际上支持前者的显式形式 `UNION DISTINCT`，但 T-SQL 仅支持隐含形式。

作为 `UNION` 的示例，以下代码返回了唯一的合并后的员工和客户位置：

```
USE TSQLV3;

SELECT country, region, city FROM HR.Employees

UNION

SELECT country, region, city FROM Sales.Customers;
```

此查询返回了 71 个不同的位置。

如果你想保留重复项，请使用 `UNION ALL` 变体，如下：

```
SELECT country, region, city FROM HR.Employees

UNION ALL

SELECT country, region, city FROM Sales.Customers;
```

此查询返回了 100 行，因为它合并了 9 行员工数据和 91 行客户数据。通常情况下，返回带有重复项的结果是没有意义的，但你可能需要在结果后应用某些逻辑。例如，你需要统计每个位置有多少个客户。为了实现这一点，你可以基于带有 `UNION ALL` 运算符的代码定义一个表表达式，并允许在外部查询中进行分组和聚合。

从性能角度来看，`UNION` 通常比 `UNION ALL` 耗销更大，因为它包含一个移除重复项的额外步骤。图 3-25 显示了最后一次 `UNION` 和 `UNION ALL` 查询这些内容的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_275_0.png)

![](img/bdc38aa36f6e2987d913ee5381474711_275_1.png)

### 图 3-25 UNION 对比 UNION ALL。

`UNION` 查询的计划使用 `Sort`（唯一排序）来移除重复项。另一个选项是使用哈希算法来实现。无论何种方式，你都可以看到 `UNION ALL` 查询涉及了更多工作。

当你合并不相交的输入时（例如包含日期列的不同年份），`UNION` 和 `UNION ALL` 在逻辑上是等价的。遗憾的是，在这种情况下你可能会使用 `UNION` 运算符，因为代码所需的按键次数更少，而没有意识到正在进行不必要的工作。因此，将 `UNION ALL` 运算符作为默认，并将 `UNION` 运算符仅留给结果存在重复项且你需要移除它们的情况。

有趣的是，如果你使用 `UNION` 合并表中的行，且这些表具有定义不相交区间的约束，优化器可以检测这一点并帮助你避免移除重复项的额外工作。

作为一个示例，以下代码创建了不同的表来存储不同年份的数据，并用 `CHECK` 约束强制执行不相交的年份区间：

```
USE tempdb;

IF OBJECT_ID('N''dbo.T2014', 'N''U') IS NOT NULL DROP TABLE dbo.T2014;

IF OBJECT_ID('N''dbo.T2015', 'N''U') IS NOT NULL DROP TABLE dbo.T2015;

GO

CREATE TABLE dbo.T2014
(
    keycol INT NOT NULL CONSTRAINT PK_T2014 PRIMARY KEY,
    dt DATE NOT NULL CONSTRAINT CHK_T2014_dt CHECK (dt >= '20140101' AND dt < '20150101')
);

CREATE TABLE dbo.T2015
(
    keycol INT NOT NULL CONSTRAINT PK_T2015 PRIMARY KEY,
    dt DATE NOT NULL CONSTRAINT CHK_T2015_dt CHECK (dt >= '20150101' AND dt < '20160101')
);
```

忽略最佳实践，你使用以下代码通过 `UNION` 运算符合并表中的行：

```
SELECT keycol, dt FROM dbo.T2014

UNION

SELECT keycol, dt FROM dbo.T2015;
```

幸运的是，得益于约束的存在，优化器发现结果中不存在重复项，因此像 `UNION ALL` 一样优化了此查询。该查询的计划如图 3-26 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_276_0.png)

图 3-26 `UNION` 和 `CHECK` 约束。

建议遵循最佳实践，坚持使用 `UNION ALL` 作为默认，以防优化器可能识别出输入是不相交的。

当进行测试时，运行以下代码进行清理：

```
IF OBJECT_ID('N''dbo.T2014', 'N''U') IS NOT NULL DROP TABLE dbo.T2014;

IF OBJECT_ID('N''dbo.T2015', 'N''U') IS NOT NULL DROP TABLE dbo.T2015;
```

## INTERSECT 运算符

`INTERSECT` 运算符返回两个输入共同的行。图 3-27 形象地展示了该运算符的作用。

![](img/bdc38aa36f6e2987d913ee5381474711_277_0.png)

图 3-27 `INTERSECT` 运算符。

作为一个示例，以下代码返回了共同的位置：

```
USE TSQLV3;

SELECT country, region, city FROM HR.Employees

INTERSECT

SELECT country, region, city FROM Sales.Customers;
```

此查询生成以下输出：

| country | region | city |
| --- | --- | --- |
| UK | NULL | London |
| USA | WA | Kirkland |
| USA | WA | Seattle |

`INTERSECT` 运算符返回两个输入共同的行。如果你想保留重复项，请使用 `INTERSECT ALL` 变体，如下：

```
SELECT country, region, city FROM HR.Employees

INTERSECT ALL

SELECT country, region, city FROM Sales.Customers;
```

此查询生成以下输出：

| country | region | city |
| --- | --- | --- |
| UK | NULL | London |
| USA | WA | Kirkland |
| USA | WA | Seattle |
| UK | NULL | London |
| UK | NULL | London |

在性能方面，`INTERSECT` 通常比 `INTERSECT ALL` 贵，因为它包含一个移除重复项的额外步骤。图 3-28 显示了最后一次 `INTERSECT` 和 `INTERSECT ALL` 查询的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_278_0.png)

![](img/bdc38aa36f6e2987d913ee5381474711_278_1.png)

### 图 3-28 INTERSECT 对比 INTERSECT ALL。

`INTERSECT` 查询的计划使用 `Sort`（唯一排序）来移除重复项。另一个选项是使用哈希算法。无论如何，你都可以看到 `INTERSECT` 查询涉及了更多工作。

当你合并不相交的输入时（例如包含日期列的不同年份），`INTERSECT` 和 `INTERSECT ALL` 在逻辑上是等价的。遗憾的是，在这种情况下你可能会使用 `INTERSECT` 运算符，因为代码所需的按键次数更少，而没有意识到正在进行不必要的工作。因此，将 `INTERSECT ALL` 运算符作为默认，并将 `INTERSECT` 运算符仅留给结果存在重复项且你需要移除它们的情况。

有趣的是，如果你使用 `INTERSECT` 合并表中的行，且这些表具有定义不相交区间的约束，优化器可以检测这一点并帮助你避免移除重复项的额外工作。

作为一个示例，以下代码创建了不同的表来存储不同年份的数据，并用 `CHECK` 约束强制执行不相交的年份区间：

```
USE tempdb;

IF OBJECT_ID('N''dbo.T2014', 'N''U') IS NOT NULL DROP TABLE dbo.T2014;

IF OBJECT_ID('N''dbo.T2015', 'N''U') IS NOT NULL DROP TABLE dbo.T2015;

GO

CREATE TABLE dbo.T2014
(
    keycol INT NOT NULL CONSTRAINT PK_T2014 PRIMARY KEY,
    dt DATE NOT NULL CONSTRAINT CHK_T2014_dt CHECK (dt >= '20140101' AND dt < '20150101')
);

CREATE TABLE dbo.T2015
(
    keycol INT NOT NULL CONSTRAINT PK_T2015 PRIMARY KEY,
    dt DATE NOT NULL CONSTRAINT CHK_T2015_dt CHECK (dt >= '20150101' AND dt < '20160101')
);
```

忽略最佳实践，你使用以下代码通过 `INTERSECT` 运算符合并表中的行：

```
SELECT keycol, dt FROM dbo.T2014

INTERSECT

SELECT keycol, dt FROM dbo.T2015;
```

幸运的是，得益于约束的存在，优化器发现结果中不存在重复项，因此像 `INTERSECT ALL` 一样优化了此查询。该查询的计划如图 3-29 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_279_0.png)

图 3-29 `INTERSECT` 和 `CHECK` 约束。

建议遵循最佳实践，坚持使用 `INTERSECT ALL` 作为默认，以防优化器可能识别出输入是不相交的。

当进行测试时，运行以下代码进行清理：

```
IF OBJECT_ID('N''dbo.T2014', 'N''U') IS NOT NULL DROP TABLE dbo.T2014;

IF OBJECT_ID('N''dbo.T2015', 'N''U') IS NOT NULL DROP TABLE dbo.T2015;
```

## EXCEPT 运算符

`EXCEPT` 运算符仅返回第一个输入中但不在第二个输入中的唯一行。图 3-30 形象地展示了该运算符的作用。

![](img/bdc38aa36f6e2987d913ee5381474711_280_0.png)

图 3-30 `EXCEPT` 运算符。

作为一个示例，以下代码返回了不是客户位置的唯一员工位置：

```
SELECT country, region, city FROM HR.Employees

EXCEPT

SELECT country, region, city FROM Sales.Customers;
```

此查询生成以下输出：

| country | region | city |
| --- | --- | --- |
| USA | WA | Redmond |
| USA | WA | Tacoma |

如果你想保留重复项，请使用 `EXCEPT ALL` 变体，如下：

```
SELECT country, region, city FROM HR.Employees

EXCEPT ALL

SELECT country, region, city FROM Sales.Customers;
```

此查询生成以下输出：

| country | region | city |
| --- | --- | --- |
| USA | WA | Redmond |
| USA | WA | Tacoma |

在性能方面，`EXCEPT` 通常比 `EXCEPT ALL` 贵，因为它包含一个移除重复项的额外步骤。图 3-31 显示了最后一次 `EXCEPT` 和 `EXCEPT ALL` 查询的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_281_0.png)

![](img/bdc38aa36f6e2987d913ee5381474711_281_1.png)

### 图 3-31 EXCEPT 对比 EXCEPT ALL。

`EXCEPT` 查询的计划使用 `Sort`（唯一排序）来移除重复项。另一个选项是使用哈希算法来实现此目的。无论如何，你都可以看到 `EXCEPT ALL` 查询涉及了更多工作。

当你合并不相交的输入时（例如包含日期列的不同年份），`EXCEPT` 和 `EXCEPT ALL` 在逻辑上是等价的。遗憾的是，在这种情况下你可能会使用 `EXCEPT` 运算符，因为代码所需的按键次数更少，而没有意识到正在进行不必要的工作。因此，将 `EXCEPT ALL` 运算符作为默认，并将 `EXCEPT` 运算符仅留给结果存在重复项且你需要移除它们的情况。

有趣的是，如果你使用 `EXCEPT` 合并表中的行，且这些表具有定义不相交区间的约束，优化器可以检测这一点并帮助你避免移除重复项的额外工作。

作为一个示例，以下代码创建了不同的表来存储不同年份的数据，并用 `CHECK` 约束强制执行不相交的年份区间：

```
USE tempdb;

IF OBJECT_ID('N''dbo.T2014', 'N''U') IS NOT NULL DROP TABLE dbo.T2014;

IF OBJECT_ID('N''dbo.T2015', 'N''U') IS NOT NULL DROP TABLE dbo.T2015;

GO

CREATE TABLE dbo.T2014
(
    keycol INT NOT NULL CONSTRAINT PK_T2014 PRIMARY KEY,
    dt DATE NOT NULL CONSTRAINT CHK_T2014_dt CHECK (dt >= '20140101' AND dt < '20150101')
);

CREATE TABLE dbo.T2015
(
    keycol INT NOT NULL CONSTRAINT PK_T2015 PRIMARY KEY,
    dt DATE NOT NULL CONSTRAINT CHK_T2015_dt CHECK (dt >= '20150101' AND dt < '20160101')
);
```

忽略最佳实践，你使用以下代码通过 `EXCEPT` 运算符合并表中的行：



SELECT `keycol`, `dt` FROM `dbo.T2014`

EXCEPT

SELECT `keycol`, `dt` FROM `dbo.T2015`;

幸运的是，得益于约束的存在，优化器发现结果中不存在重复项，因此像 `EXCEPT ALL` 一样优化了此查询。该查询的计划如图 3-32 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_282_0.png)

图 3-32 EXCEPT 和 CHECK 约束。

建议遵循最佳实践，坚持使用 `EXCEPT ALL` 作为默认，以防优化器可能识别出输入是不相交的。

当进行测试时，运行以下代码进行清理：

```sql
IF OBJECT_ID('N''dbo.T2014', 'N''U') IS NOT NULL DROP TABLE dbo.T2014;

IF OBJECT_ID('N''dbo.T2015', 'N''U') IS NOT NULL DROP TABLE dbo.T2015;
```

然后使用 `EXCEPT` 运算符。仅返回第一个输入中在第二个输入中没有匹配的行。然后你基于使用 `EXCEPT` 运算符的代码定义一个 CTE（公表表达式），并在外部查询中返回不需要行号的属性。这里是完整的解决方案代码：

```sql
WITH EXCEPT_ALL
AS
SELECT
    ROW_NUMBER() OVER(PARTITION BY country, region, city ORDER BY (SELECT 0)) AS rn,
    country, region, city
FROM HR.Employees
EXCEPT
SELECT
    ROW_NUMBER() OVER(PARTITION BY country, region, city ORDER BY (SELECT 0)) AS rn,
    country, region, city
FROM Sales.Customers
SELECT country, region, city
FROM EXCEPT_ALL;
```

此代码生成以下输出：

| country | region | city |
|---|---|---|
| USA | WA | Redmond |
| USA | WA | Tacoma |
| USA | WA | Seattle |

`USA, NULL, Seattle` 在 `Employees` 中出现两次，在 `Customers` 中出现一次；因此，它在输出中返回一次。

提示：请回顾前面“The EXISTS predicate”部分中关于寻找缺失值问题高效解决方案的讨论。这里是使用 `EXCEPT` 运算符完成相同任务的更简单且高效的解决方案：

```sql
SELECT TOP (1) missingval
FROM (SELECT coll + 1 AS missingval FROM dbo.T1
EXCEPT
SELECT coll1 FROM dbo.T1) AS D
ORDER BY missingval;
```

与之前讨论的高效解决方案一样，这里的优化器也使用了 `Top` 运算符，一旦找到第一个缺失值，就会短路扫描。

## 结论

本章涵盖了大量内容，讨论了用于从多个表中合并数据的各种工具。它涵盖了子查询、表表达式、强大的 `APPLY` 运算符、连接（joins）以及关系运算符 `UNION`、`EXCEPT` 和 `INTERSECT`。本章描述了使用这些工具的逻辑考虑因素以及如何优化它们的使用。

# 分组、透视和窗口处理

本章侧重于使用 T-SQL 执行各种目的的数据分析计算，例如报表生成。数据分析计算是你应用于一组行并返回一个值的计算。例如，聚合计算就属于此类类别。

T-SQL 支持许多用于执行数据分析计算的特性和技术，例如窗口函数、透视（pivoting）和行透视（unpivoting）、计算自定义聚合以及处理多个分组集（grouping sets）。本章涵盖了这些功能和技术。

## 窗口函数

使用窗口函数可以优雅地执行数据分析计算，在许多情况下也是高效的。与应用于分组查询定义的行组的聚合函数（group functions）不同，窗口函数应用于窗口查询定义的行。`GROUP BY` 子句确定组，而 `OVER` 子句决定窗口。因此，可以将窗口视为一组行（或上下文），供函数应用于其中。

窗口函数的设计是非常深远的，它允许你比其他工具更优雅、更方便地处理数据分析计算。标准 SQL 承认了窗口函数的重要性，并对其提供了广泛覆盖。T-SQL 实现了该标准的子集，我希望微软未来继续投入。

本章对窗口函数的覆盖按其分类组织：聚合、排名、偏移（offset）和统计。还有一个关于使用窗口函数解决间隙和孤岛（gaps and islands）问题的章节。

> 注意：本节描述的窗口处理功能是在 SQL Server 2012 中引入的。如果你使用的是旧版本的 SQL Server，将无法运行相关的代码示例。这些功能包括聚合窗口函数的框架规范（`ORDER BY` 和 `ROWS` 或窗口单位）、偏移窗口函数（`FIRST_VALUE`、`LAST_VALUE`、`LAG` 和 `LEAD`）以及统计窗口函数（`PERCENT_RANK`、`CUME_DIST`、`PERCENTILE_CONT` 和 `PERCENTILE_DISC`）。

## 聚合窗口函数

聚合窗口函数是你所知的分组函数（`SUM`、`AVG` 等），只不过你将其应用于窗口而不是组。为了演示聚合窗口函数，我将使用两个名为 `OrderValues` 和 `EmpOrders` 的小表和一个大表 `Transactions`。运行以下代码创建表并填充示例数据：

```sql
SET NOCOUNT ON;

USE tempdb;

-- OrderValues 表
IF OBJECT_ID('dbo.OrderValues', 'U') IS NOT NULL DROP TABLE dbo.OrderValues;
SELECT * INTO dbo.OrderValues FROM T_QLV3.Sales.OrderValues;
ALTER TABLE dbo.OrderValues ADD CONSTRAINT PK_OrderValues PRIMARY KEY(orderid);
GO

-- EmpOrders 表
IF OBJECT_ID('dbo.EmpOrders', 'U') IS NOT NULL DROP TABLE dbo.EmpOrders;
SELECT empid, ISNULL(ordermonth, CAST('19000101' AS DATE)) AS ordermonth, qty, val, numders
INTO dbo.EmpOrders
FROM T_QLV3.Sales.EmpOrders;
ALTER TABLE dbo.EmpOrders ADD CONSTRAINT PK_EmpOrders PRIMARY KEY(empid, ordermonth);
GO

-- Transactions 表
IF OBJECT_ID('dbo.Transactions', 'U') IS NOT NULL DROP TABLE dbo.Transactions;
IF OBJECT_ID('dbo.Accounts', 'U') IS NOT NULL DROP TABLE dbo.Accounts;
CREATE TABLE dbo.Accounts
(
    actid INT NOT NULL CONSTRAINT PK_Accounts PRIMARY KEY
);
CREATE TABLE dbo.Transactions
(
    actid INT NOT NULL,
    tranid INT NOT NULL,
    val MONEY NOT NULL,
    CONSTRAINT PK_Transactions PRIMARY KEY(actid, tranid)
);
DECLARE
    @num_partitions AS INT = 100,
    @rows_per_partition AS INT = 20000;
INSERT INTO dbo.Accounts WITH (TABLOCK) (actid)
SELECT NP.n
FROM T_QLV3.dbo.GetNums(1, @num_partitions) AS NP;
```

```sql
INSERT INTO dbo.Transactions WITH (TABLOCK) (actid, tranid, val)
SELECT NP.n, RPP.n, (ABS(CHECKSUM(NEWID())%2) * (1 + CHECKSUM(NEWID())%5))
FROM SQL_V3.dbo.GetNums(1, @num_partitions) AS NP
CROSS JOIN SQL_V3.dbo.GetNums(1, @rows_per_partition) AS RPP;
```

`OrderValues` 表为每个订单值和数量有一行。`EmpOrders` 表跟踪每个员工每月总额。`Transactions` 表有 2,000,000 行银行账户交易（100 个账户，每个账户 20,000 次交易）。

## 无窗口函数的数据分析计算限制

在深入研究窗口函数的细节之前，你应该首先意识到执行数据分析计算的替代工具的局限性。了解这些局限性是欣赏窗口函数巧妙设计的好方法。考虑以下分组查询：

```sql
SELECT custid, SUM(val) AS custtotal
FROM dbo.OrderValues
GROUP BY custid;
```

与分析细节相比，分组查询以聚合的形式提供了数据的新洞察。然而，分组查询隐藏了细节。例如，在分组查询中返回详细元素的尝试会失败：

```sql
SELECT custid, SUM(val) AS custtotal
FROM dbo.OrderValues
GROUP BY custid;
```

你会得到以下错误：

Msg 8120, Level 16, State 1, Line 70
列 'dbo.OrderValues.val' 在选择列表中无效，因为它既不在聚合函数中，也不在 GROUP BY 子句中。

如果你同时需要详细信息和聚合信息，可以使用子查询：

```sql
SELECT custid, val, custtotal
FROM (
    SELECT custid, val, SUM(val) OVER(PARTITION BY custid) AS custtotal
    FROM dbo.OrderValues
) AS t;
```

但如果你只想要每行的聚合值怎么办？可以使用窗口函数：

```sql
SELECT custid, SUM(val) OVER(PARTITION BY custid) AS custtotal
FROM dbo.OrderValues;
```

这种方法的问题是，每行都获得数据的全新视图作为起点。例如，如果你想要计算总和，你需要使用框架：

```sql
SELECT custid, val, SUM(val) OVER(PARTITION BY custid ORDER BY val ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS running_total
FROM dbo.OrderValues;
```

代码中有一个错误。观察到每个客户的百分比总和并没有像预期那样相加等于100%，总额的百分比也是如此。由于子查询在底层查询的结果集上操作，你要么重复代码元素，要么使用表表达式。

窗口函数的设计考虑了分组查询和子查询的局限性，而从其功能性来说，这仅仅是冰山一角！

与分组查询不同，窗口查询不会隐藏细节。在返回细节的同时，还会返回窗口函数的结果。

与子查询中对标量聚合函数暴露出的数据新颖视图不同，`OVER` 子句将底层查询结果作为窗口函数的起始点。更准确地说，从逻辑查询处理的角度来看，窗口函数在 `SELECT` 阶段暴露的行集上操作——在处理完 `FROM`、`WHERE`、`GROUP BY` 和 `HAVING` 之后。因此，窗口函数仅允许在查询的 `SELECT` 和 `ORDER BY` 子句中使用。在 `OVER` 子句中使用空规格定义了一个包含整个查询结果集的窗口。因此，`SUM(val) OVER` 给出总和。添加诸如 `PARTITION BY` 这样的分区句会将窗口限制为当前行具有相同 `customer ID` 的行。`SUM(val) OVER(PARTITION BY custid)` 给出客户总额。

接下来的查询为你提供了细节，以及当前订单值占该客户总额的百分比：

```sql
SELECT orderid, custid, val,
    val / SUM(val) OVER() AS pctall,
    val / SUM(val) OVER(PARTITION BY custid) AS pctcust
FROM dbo.OrderValues;
```

这是一个带有格式化百分比的修订版本：

```sql
SELECT orderid, custid, val,
    CAST(100. * val / SUM(val) OVER() AS NUMERIC(5, 2)) AS pctall,
    CAST(100. * val / SUM(val) OVER(PARTITION BY custid) AS NUMERIC(5, 2)) AS pctcust
FROM dbo.OrderValues
ORDER BY custid;
```

为查询添加一个过滤器：

```sql
SELECT orderid, custid, val,
    CAST(100. * val / SUM(val) OVER() AS NUMERIC(5, 2)) AS pctall,
    CAST(100. * val / SUM(val) OVER(PARTITION BY custid) AS NUMERIC(5, 2)) AS pctcust
FROM dbo.OrderValues
WHERE orderdate >= '20150101'
ORDER BY custid;
```

与子查询不同，窗口函数以过滤后的底层查询作为起始点。观察查询输出：

| orderid | custid | val | pctall | pctcust |
|---|---|---|---|---|
| 10835 | 1 | 845.80 | 0.19 | 37.58 |
| 10952 | 1 | 471.20 | 0.11 | 20.94 |
| 11011 | 1 | 933.50 | 0.21 | 41.48 |
| 10926 | 2 | 514.40 | 0.12 | 100.00 |
| 10856 | 3 | 660.00 | 0.15 | 100.00 |
| 10864 | 4 | 282.00 | 0.06 | 5.03 |
| 10951 | 4 | 441.25 | 1.01 | 79.24 |
| 10920 | 4 | 390.00 | 0.09 | 6.96 |
| 11016 | 4 | 491.50 | 0.11 | 8.77 |
| 10924 | 5 | 1835.70 | 0.42 | 27.18 |

注意这些每个客户的百分比 (pctcust) 相加为 100，总额的百分比也是如此。

## 窗口元素

窗口函数在概念上是按行评估的，窗口规格（specification）显式地或隐式地与底层查询相关。聚合窗口函数支持规格中的行数，如下查询所示，它计算每个员工的运行总和：

```sql
SELECT empid, ordermonth, qty,
    SUM(qty) OVER(PARTITION BY empid
    ORDER BY ordermonth
    ROWS BETWEEN UNBOUNDED PRECEDING
    AND CURRENT ROW) AS rnqty
FROM dbo.EmpOrders;
```

规格可以定义一个窗口分区。`PARTITION BY empid` 将窗口限制为与当前行具有相同 `empid` 值的行。同样，`PARTITION BY custid` 将行限制为具有相同 `custid` 值的行。缺少分区句，底层查询结果集被视为一个大分区。因此，对于任何给定的行，`OVER()` 向函数暴露整个结果集。图 4-1 展示了带有空 `OVER` 子句和包含窗口分区句的符合条件的行。

![](img/bdc38aa36f6e2987d913ee538147411_289_0.png)

图 4-1 窗口分区

例如，以下查询计算每个订单占总额的百分比，以及占客户总额的百分比：

```sql
SELECT orderid, custid, val,
    CAST(100. * val / SUM(val) OVER() AS NUMERIC(5, 2)) AS pctall,
    CAST(100. * val / SUM(val) OVER(PARTITION BY custid) AS NUMERIC(5, 2)) AS pctcust
FROM dbo.OrderValues
ORDER BY custid;
```



此查询生成以下输出：

| orderid | custid | val | pctall | pctcustust |
|---|---|---|---|---|
| 10643 | 1 | 814.50 | 0.06 | 19.06 |
| 10692 | 1 | 878.00 | 0.07 | 20.55 |
| 10702 | 1 | 330.00 | 0.03 | 7.72 |
| 10835 | 1 | 845.80 | 0.07 | 19.79 |
| 10952 | 1 | 471.20 | 0.11 | 20.94 |
| 11011 | 1 | 933.50 | 0.21 | 41.48 |
| 10926 | 2 | 514.40 | 0.12 | 100.00 |
| 10856 | 3 | 660.00 | 0.15 | 100.00 |
| 10864 | 4 | 282.00 | 0.06 | 5.03 |
| 10951 | 4 | 441.25 | 1.01 | 79.24 |
| 10920 | 4 | 390.00 | 0.09 | 6.96 |
| 11016 | 4 | 491.50 | 0.11 | 8.77 |
| 10924 | 5 | 1835.70 | 0.42 | 27.18 |

与子查询不同，窗口函数以过滤后的底层查询作为起始点。观察查询输出：

| orderid | custid | val | pctall | pctcust |
|---|---|---|---|---|
| 10835 | 1 | 845.80 | 0.19 | 37.58 |
| 10952 | 1 | 471.20 | 0.11 | 20.94 |
| 11011 | 1 | 933.50 | 0.21 | 41.48 |
| 10926 | 2 | 514.40 | 0.12 | 100.00 |
| 10856 | 3 | 660.00 | 0.15 | 100.00 |
| 10864 | 4 | 282.00 | 0.06 | 5.03 |
| 10951 | 4 | 441.25 | 1.01 | 79.24 |
| 10920 | 4 | 390.00 | 0.09 | 6.96 |
| 11016 | 4 | 491.50 | 0.11 | 8.77 |
| 10924 | 5 | 1835.70 | 0.42 | 27.18 |

我在我的系统上获得该解决方案的性能统计数据如下：

- 运行时间：2.01 秒
- CPU 时间：4.97 秒
- 逻辑读取：19,368

这是一个相当大的改进。

由于使用窗口函数在语言设计上有巨大的优势，我们希望未来能投入资金对此类函数进行更好的优化。

通常情况下，分组和窗口化被认为是实现任务的不同方法，但也有结合两者的有趣方式。它们并不是互斥的。理解这一点的简单方法是考虑逻辑查询处理。回想第 1 章“逻辑查询处理”，`GROUP BY` 子句在第 3 步进行评估，而 `SELECT` 子句在第 5 步进行评估。因此，如果查询是一个分组查询，`SELECT` 阶段是在数据的分组状态上操作的，而不是详细状态上。如果你在 `SELECT` 或 `ORDER BY` 阶段使用窗口函数，该窗口函数也是在分组状态上操作的。

例如，考虑以下分组查询：

```
SELECT custid, SUM(val) AS custotal
FROM dbo.OrderValues
GROUP BY custid;
```

该查询按 `custid` 对行进行分组，并返回每个客户的总值（custotal）。

在查看下一个查询之前，尝试回答以下问题：你能够直接将 `val` 列添加到前一个查询的 `SELECT` 列表中吗？答案是：“当然不能”。因为该查询是一个分组查询，只有当 `SELECT` 中的列名是 `GROUP BY` 列表的一部分或包含在分组聚合函数中，才允许引用它。

考虑到这一点，假设你需要在查询中添加一个计算，返回当前总额占总额的百分比。`SUM(val)`。通常，为了在详细查询中表示总额，你会使用窗口函数 `SUM(val) OVER()`。然而，要将其中一个除以另一个，如下：

```
SELECT custid, SUM(val) AS custtotal,
SUM(val) / SUM(val) OVER() AS pct
FROM dbo.OrderValues
GROUP BY custid;
```

当你尝试直接将 `val` 列添加到 `SELECT` 列表时，会得到相同的错误：

```
Msg 8120, Level 16, State 1, Line 229
Column 'dbo.OrderValues.val' is invalid in the select list because it is not contained in either an aggregate function or the GROUP BY clause.
```

与分组函数不同

如果窗口不能直接引用 `val` 列，它能引用什么？由于 SQL 的“一次性处理”（all-at-once）概念，尝试引用别名也会失败。答案是窗口化的 `SUM` 应该应用于分组后的 `SUM`，如下：

```
SELECT custid, SUM(val) AS custotal,
SUM(val) / SUM(val) OVER() AS pct
FROM dbo.OrderValues
GROUP BY custid;
```

这个想法需要一点时间适应，但从逻辑查询处理的角度来看，它是完全合理的。

**窗口框（Window frame）** 就像分区（partition）是底层查询结果集的过滤部分一样，窗口框是分区的过滤部分。窗口框需要使用窗口排序子句（window order clause）指定排序规范。根据该顺序，你定义了两个界符来框定行。然后，窗口函数被应用于该行框。你可以使用两种窗口函数之一：`ROWS` 或 `RANGE`。

我将从 `ROWS` 开始。使用此单元，你可以定义两种类型的界符：

- `UNBOUNDED PRECEDING | FOLLOWING`：分别为分区中的第一行或最后一行。
- `CURRENT ROW`：当前行。
- `N ROWS PRECEDING | FOLLOWING`：相对于当前行之前或之后指定行数（N）的偏移量。

第一个界符必须在第二个界符之上或在第二个界符之前。

图 4-4 阐释了窗口框的概念。数字 1 和 2 代表员工 ID；值 201307、201308 等代表订单月份。一个示例行被加粗显示为当前行。

![](img/bdc38aa36f6e2987d913ee5381474711_294_0.png)

图 4-4 窗口框。

例如，假设你想查询 `EmpOrders` 表，并为每个员工和订单月份计算累计数量。换句话说，你想查看员工随时间推移的累积性能。你根据 `empid` 列定义窗口分区子句，根据 `ordermonth` 列定义窗口排序子句，并将窗口框子句定义为 `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW`，如下：

```
SELECT empid, ordermonth, qty,
SUM(qty) OVER(PARTITION BY empid
ORDER BY ordermonth
ROWS BETWEEN UNBOUNDED PRECEDING
AND CURRENT ROW) AS runqty
FROM dbo.EmpOrders;
```

因为这种框规范非常常见，标准定义了等效的短形式 `ROWS UNBOUNDED PRECEDING`。这是我们在查询中使用的较短形式：

```
SELECT empid, ordermonth, qty,
SUM(qty) OVER(PARTITION BY empid
ORDER BY ordermonth
ROWS BETWEEN UNBOUNDED PRECEDING) AS runqty
FROM dbo.EmpOrders;
```

该查询生成了以下内容：

| empid | ordermonth | qty | runqty |
|---|---|---|---|
| 1 | 2013-07-01 | 121 | 121 |
| 1 | 2013-08-01 | 247 | 368 |
| 1 | 2013-09-01 | 255 | 623 |
| 1 | 2013-10-01 | 143 | 766 |
| 1 | 2013-11-01 | 318 | 1084 |
| 1 | 2013-12-02 | 536 | 1620 |
| 1 | 2015-05-01 | 299 | 7812 |
| 2 | 2013-07-01 | 50 | 50 |
| 2 | 2013-08-01 | 94 | 144 |
| 2 | 2013-09-01 | 137 | 281 |
| 2 | 2013-10-01 | 248 | 529 |
| 2 | 2013-11-01 | 237 | 766 |
| 2 | 2013-12-01 | 319 | 1085 |
| 2 | 2015-04-01 | 1126 | 5915 |

使用窗口函数计算累计总和是优雅的，而且很快就会发现是高效的。另一种技术是使用连接和分组的查询：

```
SELECT 01.empid, 01.ordermonth, 01.qty,
SUM(02.qty) AS runqty
FROM dbo.EmpOrders AS 01
INNER JOIN dbo.EmpOrders AS 02
ON 02.empid = 01.empid
AND 02.ordermonth <= 01.ordermonth
GROUP BY 01.empid, 01.ordermonth, 01.qty;
```

这种技术复杂非常低下。为了评估不同技术的优化，我将使用较大的 `Transactions` 表。假设你需要计算每个账户交易后的余额。使用窗口函数，你对 `val` 列应用计算，按 `actid` 列分区，按 `tranid` 列排序，框设为 `ROWS UNBOUNDED PRECEDING`。窗口函数的缩写我认为代表的是分区（actid）、排序（tranid）和覆盖（val）。P 和 O 部分应该是索引键，而 C 部分应该包含在叶节点行中。`Transactions` 表上的聚集索引 `PK_Transactions` 包含在此模式中，因此我们已经有了索引。以下查询使用窗口函数计算上述的余额：

```
SELECT actid, tranid, val,
SUM(val) OVER(PARTITION BY actid
ORDER BY tranid
ROWS UNBOUNDED PRECEDING) AS balance
FROM dbo.Transactions;
```

该查询的计划如图 4-5 所示。

| SELECT | Compute Scalar | Stream Aggregate (Aggregate) | Window Pool | Segment | Sequence Project (Compute Scalar) | Segment | Clustered Index Scan (Clustered) [PK_Transactions] |
|---|---|---|---|---|---|---|---|
| Cost: 9% | Cost: 1% | Cost: 9% | Cost: 1% | Cost: 9% | Cost: 1% | Cost: 0% | Cost: 50% |

图 4-5 运行快速优化窗口函数的计划。

计划从按顺序扫描索引开始。这是一个很好的开始。`Segment` 和 `Sequence Project` 操作符的后续部分负责计算行号。行号指示哪些行符合底层行的框。`Segment` 操作符在新分区开始时标记下一个操作符。`Sequence Project` 分配行号——如果是分区中的第一行则为 1，如果不是则为前一个值加 1。`Next Segment` 操作符同样负责在新分区开始时标记其左侧的操作符。

`Window Pool` 和 `Stream Aggregate` 操作符的后续部分代表需要聚合的行框和添加到框中的聚合值。如果没有特殊优化快速跟踪，优化器对于具有 N 行的分区，池必须求和 1+2+...+N = (N+1)/2 行。例如，对于一个有 20,000 次交易的账户，该数字将是 200,010,000。幸运的是，当框的第一个界符是分区的第一行（`UNBOUNDED PRECEDING`）时，优化器会将该情况识别为“快速跟踪”和特殊优化。对于每一行，它获取行的累加，加上当前行的值，并将其写入池中。

有了这种优化，你期望输出池的行数与进入池的行数相同（在我们的案例中为 2,000,000）；然而，计划显示输出的行数等于进入的行数。的原因在于 `Stream Aggregate` 操作符在窗口函数引入很久之前就已经设计。最初，它仅用于计算查询中的分组函数，这种函数进行了聚合但隐藏了细节。Microsoft 使用该操作符计算窗口聚合的技巧是将其添加到行中以防丢失。通过快速优化，如果 N 行进入 `Window Pool` 操作符，你应该看到 N 行输出。

```
SELECT
Cost: 0 %

Stream Aggregate
(Aggregate)
Cost: 1 %

Nested Loops
(Inner Join)
Cost: 2 %

Clustered Index (Clustered)
[Transactions];[PK_Transactions][T.
Cost: 0 %

Clustered Index (Clustered)
[Transactions];[PK_Transactions][T.
Cost: 95 %

Seek Predicates

Seek Key[T1]: Prefix:[tempdb].[dbo](actid) =
Scalar Operator([tempdb].[dbo]) [Transactions](actid) =
[T1] + * Scalar Operator([tempdb].[dbo]) [Transactions](actid) +=
Scalar Operator([tempdb].[dbo]) [Transactions](transid) = [T1].transid
```

**图 4** 带连接和分组查询的计划。

在这里，优化器没有采用任何特殊的优化。POC 对表 T1 实例进行了一次扫描，然后对于每一行，它在代表实例 T2 的索引中进行搜索，直到到达当前账户部分的开头，然后对所有 `T2.actid = T1.actid` 的行进行范围扫描。除了全扫描的代价和寻址的代价外，每个账户总共处理了 (N + N)/2 行，其中 N 是每个账户的交易数。在我们的示例数据中，N 等于 20,000。在我的系统上，该查询花费了一个半多小时才完成。

虽然带连接和分组的查询计划具有平方级规模 (N²)，但窗口函数的计划具有线性规模。此外，优化器知道在 `ROWS` 模式下，窗口框内的行数不超过 10,000 行，它使用了一个专门的内存池（而不是更昂贵的磁盘溢出）。请记住，当单位为 `ROWS` 且优化器使用快速优化（fast-track optimization）时，它每次排序只向池写入两行——一行包含聚合结果，另一行包含详细信息。在这种情况下，了内存池的条件。

尽管如此，对于像 `ROWS UNBOUNDED PRECEDING` 这样更常用的帧规格，优化器仍有改进空间。从理论上讲，在这些情况下可以避免池化。相反，优化器可以使用流操作符，例如它用于计算 `ROW_NUMBER` 函数的序列项目操作符（Sequence Project operator）。作为一个示例，将计算余额的查询中的窗口 `SUM` 替换为 `ROW_NUMBER` 函数以检查性能，查询在了一秒内完成，而原始查询需要四秒。如果微软未来不在此领域投入研究，这就是运行总计（running totals）的性能提升潜力。

如前面提到的，您可以使用 `ROWS` 选项将分隔符指定为当前行之前（`PRECEDING`）或之后（`FOLLOWING`）的行数偏移量。例如，以下查询计算了每个员工在每个月最后三个记录的月份的移动平均值。

```
SELECT empid, ordermoth,
AVG(qty) OVER(PARTITION BY empid
ORDER BY ordermoth
ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS avgqty
FROM dbo.EmpOrders;
```

此查询生成了以下输出：

```
empid ordermoth avgqty
----------------------
1 2013-07-01 121
1 2013-08-01 184
1 2013-09-01 207
1 2013-10-01 215
1 2013-11-01 238
1 2013-12-01 332
1 2014-01-01 386
1 2014-02-01 336
1 2014-03-01 249
1 2014-04-01 154
```

另一个示例是，以下查询计算了最后 100 次交易的移动平均值：

```
SELECT actid, tranid, val,
AVG(val) OVER(PARTITION BY actid
ORDER BY tranid
ROWS BETWEEN 99 PRECEDING AND CURRENT ROW) AS avg100
FROM dbo.Transactions;
```



# 关于不从分区开始的帧的优化

有趣之处在于，你本认为优化器会创建一个计划，将所有帧行写入窗口并对它们进行聚合。在示例中，这意味着 `100 × 2,000,000 = 2,000,000` 行。然而，优化器有一个可以在某些条件下使用的技巧来避免此类工作。如果帧包含超过四行，且聚合是像 `SUM`、`COUNT` 或 `AVG` 这样的累积值，优化器会创建一个带有两个快速跟踪运行计算的计划：从分区开始并结束于所需帧的最后一行（称为 `CumulativeBottom`），另一个从分区开始并结束于所需帧开始之前的一行（称为 `CumulativeTop`）。然后，它通过这两个之间的计算推导出最终的聚合结果。你可以在图 4-7 所示的最后一个查询的计划中看到这种策略。

该查询在我的系统上花费了 12 秒完成。考虑到替代方案，这并不糟糕。

![](img/bdc38aa36f6e2987d913ee5381474711_299_0.png)

```
CumulativeBottom001 = Count(*)
CumulativeBottom001 = SUM(val)
```

![](img/bdc38aa36f6e2987d913ee5381474711_299_1.png)

```
CumulativeBottom001 = Count(*)
CumulativeBottom001 = SUM(val)
```

![](img/bdc38aa36f6e2987d913ee5381474711_299_2.png)

```
Expr1012 = CumulativeBottom0014
Expr1013 = CumulativeBottom0016
Expr1014 = Count(*)
Expr1015 = SUM(val)
```

图 4-7 移动平均的计划。

如果计算不可推导的（无法通过底部和顶部计算推导），优化器将无法使用任何技巧，所有相关的行都必须写入池并进行聚合。此类聚合的例子是 `MIN` 和 `MAX`。为了演示，以下查询使用 `MAX` 计算最后 100 次交易中的最大值：

```sql
SELECT actid, tranid, val,
       MAX(val) OVER(PARTITION BY actid ORDER BY tranid
                     ROWS BETWEEN 99 PRECEDING AND CURRENT ROW) AS max100
FROM dbo.Transactions;
```

此查询的计划在图 4-8 中。

![](img/bdc38aa36f6e2987d913ee5381474711_299_3.png)

图 4-8 来自池的计划。此查询花费了 64 秒完成。注意即使计划也显示了流出池的行数。

要将此方法应用于我们的示例，请使用以下查询：

```sql
SELECT A.actid, D.tranid, D.val,
       MAX(val) OVER(PARTITION BY actid ORDER BY tranid
                     ROWS BETWEEN 99 PRECEDING AND CURRENT ROW) AS max100
FROM dbo.Accounts AS A
CROSS APPLY (SELECT tranid, val,
                  MAX(val) OVER(ORDER BY tranid
                                ROWS BETWEEN 99 PRECEDING AND CURRENT ROW) D;
```

聚合窗口函数支持另一种帧单位，称为 `RANGE`。遗憾的是在 SQL 中，`RANGE` 选项允许您将分隔符指定为相对于当前行排序值的偏移量。这与 `ROWS` 不同，`ROWS` 是根据行数定义偏移量的。对于 `RANGE`，帧的定义是动态的。

![](img/bdc38aa36f6e2987d913ee5381474711_300_0.png)

图 4-9 使用 `APPLY` 操作符的优化。该查询在我的系统上花费了 30 秒完成——是原始查询时间的一半。

结果是，你应该得到员工 9 的以下输出：

| empid | ordermon | qty | sum3month |
|---|---|---|---|
| 9 | 2013-07-01 | 294 | 294 |
| 9 | 2013-10-01 | 256 | 256 |
| 9 | 2013-12-01 | 25 | 281 |
| 9 | 2014-01-01 | 74 | 99 |
| 9 | 2014-03-01 | 137 | 211 |
| 9 | 2014-04-01 | 52 | 189 |
| 9 | 2014-05-01 | 8 | 197 |
| 9 | 2014-06-01 | 161 | 221 |
| 9 | 2014-07-01 | 4 | 173 |
| 9 | 2014-08-01 | 98 | 263 |

遗憾的是，SQL Server 缺少一些允许查询的功能。第一，SQL Server 缺少 `INTERVAL` 功能。第二，SQL Server 在 `RANGE` 上仅支持 `UNBOUNDED` 和 `CURRENT ROW` 隔符。

要在 SQL Server 中实现此任务，你有几种选择。一种是使用缺失的员工和月份记录填充数据，然后使用 `ROWS` 选项，如下：

```sql
DECLARE @frommonth AS DATE = '20130701';
DECLARE @tommonth AS DATE = '20150501';

WITH M AS (
    SELECT DATEADD(month, N.n, @frommonth) AS ordermon
    FROM TSQL3.dbo.GetNums(0, DATEDIFF(month, @frommonth, @tommonth)) AS N
),
R AS (
    SELECT E.empid, M.ordermon, EO.qty,
           SUM(EO.qty) OVER(PARTITION BY E.empid
                            ORDER BY M.ordermon
                            ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS sum3month
    FROM TSQL3.HR.Employees AS E
    CROSS JOIN M
    LEFT OUTER JOIN dbo.EmpOrders AS EO
        ON E.empid = EO.empid
        AND M.ordermon = EO.ordermon
)
SELECT empid, ordermon, qty, sum3month
FROM R
WHERE qty IS NOT NULL;
```

另一种选项是使用连接和分组的查询，就像我之前展示运行总和那样：

```sql
SELECT O1.empid, O1.ordermonth, O1.qty,
       SUM(O2.qty) AS sum3month
FROM dbo.EmpOrders AS O1
INNER JOIN dbo.EmpOrders AS O2
    ON O2.empid = O1.empid
    AND O2.ordermonth BETWEEN DATEADD(month, -2, O1.ordermonth) AND O1.ordermonth
GROUP BY O1.empid, O1.ordermonth, O1.qty
ORDER BY O1.empid, O1.ordermonth;
```

问题在于，当两者都支持以 `UNBOUNDED` 和 `CURRENT ROW` 为隔符的 `RANGE` 时，`ROWS` 和 `RANGE` 在使用相同的框架规范时存在细微的逻辑差异。这种差异在排序不唯一时会表现出来。`ROWS` 选项不包含等值行（在排序值中），而 `RANGE` 则包含。考虑以下示例：

```sql
SELECT orderid, orderdate,
       SUM(val) OVER(ORDER BY orderdate ROWS UNBOUNDED PRECEDING) AS sumrows,
       SUM(val) OVER(ORDER BY orderdate RANGE UNBOUNDED PRECEDING) AS sumrange
FROM dbo.OrderValues;
```

此查询生成以下输出：

| orderid | orderdate | sumrows | sumrange |
|---|---|---|---|
| 10248 | 2013-07-04 | 440.00 | 440.00 |
| 10249 | 2013-07-05 | 1863.40 | 2303.40 |
| 10250 | 2013-07-05 | 1562.60 | 4510.06 |
| 10251 | 2013-07-08 | 654.06 | 4510.06 |
| 10252 | 2013-07-09 | 3597.90 | 8107.96 |
| 11070 | 2015-05-05 | 1629.98 | 126314.56 |
| 11071 | 2015-05-05 | 484.50 | 125746.56 |
| 11072 | 2015-05-05 | 5218.00 | 126271.56 |
| 11073 | 2015-05-05 | 300.00 | 126304.56 |
| 11074 | 2015-05-06 | 232.09 | 126342.65 |
| 11075 | 2015-05-06 | 2637.44 | 126793.22 |
| 11076 | 2015-05-06 | 792.75 | 126457.50 |
| 11077 | 2015-05-06 | 1255.72 | 126793.22 |

`orderdate` 列是不唯一的。在订单 10250 和 10251 的函数结果之间，注意在 `ROWS` 的情况下排序值没有被包含，导致计算是不确定的。排序决定了哪些值被包含在计算中。在 `RANGE` 中，包含了等值行，因此两行得到相同的结果。

虽然两个选项之间的逻辑差异很细微，但性能差异却完全不同。对于窗口池，优化器可以使用专门的内存池或磁盘池（后者用于临时表，并带有 I/O 和锁存的开销）。内存池的风险是内存消耗。如果优化器知道框架中的底层行不会超过 10000 行，它将使用内存池；如果它知道可能更多或不确定，它将使用磁盘池。在 `ROWS` 中，当检测到快速路径情况时，池中恰好存储了两个行，因此你得到了内存池。你有许多方法可以检查使用了哪种池。一种是使用名为 `window_ondisk_warning` 的扩展事件，它在使用磁盘池时触发。另一种方法是通过 `STATISTICS`。内存池导致针对工作表的 I/O 计数为 0，而磁盘池则显示非零值。

作为示例，在开启 `STATISTICS` 后运行以下查询：

```sql
SELECT actid, tranid,
       SUM(val) OVER(PARTITION BY actid ORDER BY tranid
                     ROWS UNBOUNDED PRECEDING) AS balance
FROM dbo.Transactions;
```

这在我的系统上花费了四秒钟完成。它的计划如图 4-5 所示。注意工作表的 I/O 统计为 0，说明使用了内存池：

```
'Worktable'. 扫描 0，逻辑读取 0，物理读取 0，预读 0，lob 逻辑读取 0，lob 物理读取 0，lob 预读 0。
'Transactions'. 扫描 1，逻辑读取 6208，物理读取 168，预读 6200，lob 0，lob 0，lob 预读 0。
```

记住 `RANGE` 包含等值行，每当你使用 `RANGE` 时，优化器都会选择磁盘池。这里有一个示例：

```sql
SELECT actid, tranid,
       SUM(val) OVER(PARTITION BY actid ORDER BY tranid
                     RANGE UNBOUNDED PRECEDING) AS balance
FROM dbo.Transactions;
```

注意工作表的 I/O 统计显示非零值，说明使用了磁盘池：

```
'Worktable'. 扫描 0，逻辑读取 12345，物理读取 10，预读 0，lob 逻辑读取 0，lob 物理读取 0，lob 预读 0。
'Transactions'. 扫描 1，逻辑读取 6208，物理读取 168，预读 6200，lob 0，lob 0，lob 预读 0。
```

在订单 10250 和 10251 的函数结果之间：注意在 `ROWS` 的情况下排序值没有被包含，导致计算是不确定的。排序决定了哪些值被包含在计算中。在 `RANGE` 中，包含了等值行，因此两行得到相同的结果。

需要注意的重要事项……

观察到客户 10 在 2014 年 1 月 10 日下了两个订单，计算结果在两行中生成了相同的 YTD（年初累计）值，这是符合的。

如果你需要每个唯一的客户和日期仅返回一行，则需要根据这两个字段对行进行分组，然后将窗口函数应用于分组后的 `SUM` 函数。由于分区和排序元素的组合是唯一的，你应该使用 `ROWS` 函数。以下是完整的查询语句：

```sql
SELECT custid, orderdate,
       SUM(SUM(val)) OVER(PARTITION BY custid, YEAR(orderdate)
                          ORDER BY orderdate
                          ROWS UNBOUNDED PRECEDING) AS YTD_val
FROM dbo.OrderValues
GROUP BY custid, orderdate;
```

该查询生成了以下输出：

| custid | orderdate | YTD_val |
|---|---|---|
| 1 | 2014-08-25 | 814.50 |
| 1 | 2014-10-03 | 1692.50 |
| 1 | 2014-11-13 | 2022.50 |
| 1 | 2015-01-15 | 845.80 |
| 1 | 2015-03-16 | 1317.00 |
| 1 | 2015-04-09 | 2250.50 |
| ... | | |
| 10 | 2013-12-20 | 1832.80 |
| 10 | 2014-01-10 | 1768.80 |
| 10 | 2014-01-30 | 3661.05 |
| 10 | 2014-04-01 | 4512.25 |
| 10 | 2014-11-14 | 7630.25 |

观察发现每个唯一的客户和日期只有一行，正如客户 10 在 2014 年 1 月 10 日的情况一样。

# 排名窗口函数

排名计算在 T-SQL 中是通过窗口函数实现的。当你对一个值进行排名时，你并不是单独对其进行排名，而是根据特定的顺序相对于一组值进行排名。窗口概念适用于此类计算。该集合由 `OVER` 子句定义。如果没有窗口分区句，你将当前行的值相对于底层查询结果集中所有行进行排名。如果有窗口分区句，则对相同窗口分区内的行进行排名。强制性的窗口排序句定义了排名的顺序。

为了演示排名窗口函数，我将使用以下表。

```sql
SET NOCOUNT ON;
USE tempdb;

CREATE TABLE dbo.Orders (
    orderid INT NOT NULL,
    orderdate DATE NOT NULL,
    empid INT NOT NULL,
    custid VARCHAR(5) NOT NULL,
    qty INT NOT NULL,
    CONSTRAINT PK_Orders PRIMARY KEY(orderid)
);
GO
```

```sql
INSERT INTO dbo.Orders(orderid, orderdate, empid, custid, qty)
VALUES (30001, '20130802', 3, 'B', 10),
       (10001, '20131224', 1, 'C', 10),
       (10005, '20131224', 1, 'A', 30),
       (40001, '20140109', 4, 'A', 40),
       (10006, '20140118', 1, 'C', 10),
       (20001, '20140212', 2, 'B', 20),
       (40005, '20140212', 4, 'A', 10),
       (20002, '20140216', 2, 'C', 20),
       (30003, '20140418', 3, 'B', 15),
       (30004, '20140418', 3, 'B', 20),
       (30007, '20140907', 3, 'C', 30);
```

T-SQL 支持四种排名函数，称为 `ROW_NUMBER`、`RANK`、`DENSE_RANK` 和 `NTILE`。以下是一个在 `Orders` 表上演示这四种函数的查询，不使用窗口分区句，并按 `qty` 列进行排序：

```sql
SELECT
    ROW_NUMBER() OVER(ORDER BY qty) AS rownum,
    RANK() OVER(ORDER BY qty) AS rank,
    DENSE_RANK() OVER(ORDER BY qty) AS densernk,
    NTILE(4) OVER(ORDER BY qty) AS ntile4
FROM dbo.Orders;
```



该查询生成了以下结果：

| orderid | qty | rownum | rank | densernk | ntile4 |
|---|---|---|---|---|---|
| 10001 | 10 | 1 | 1 | 1 | 1 |
| 10006 | 10 | 2 | 1 | 1 | 1 |
| 30001 | 10 | 3 | 1 | 1 | 1 |
| 40005 | 10 | 4 | 1 | 1 | 2 |
| 30003 | 15 | 5 | 5 | 2 | 2 |
| 30004 | 20 | 6 | 6 | 3 | 3 |
| 20001 | 20 | 7 | 6 | 3 | 3 |
| 20002 | 20 | 8 | 6 | 3 | 3 |
| 10005 | 30 | 9 | 9 | 4 | 3 |
| 30007 | 30 | 10 | 9 | 4 | 4 |
| 40001 | 40 | 11 | 11 | 5 | 4 |

`ROW_NUMBER` 函数是四种中最常用的。它根据分区（整个查询结果）的排序计算递增整数。当排序不唯一时（如我们的示例所示），计算将是非确定的。这意味着，如果你再次运行查询，无法保证获得相同的结果。例如，观察 `quantity` 为 20 的行，它们获得了行号 6、7 和 8。在需要确定性（可重复的结果）的情况下，`OFFSET` 可以用于分页，我将在第 5 章演示。对于每一页，你不希望同一行出现在两个页中（因为在一次查询中它是 5，另一次是 6）。为了强制确定行的计算，可以在排序句中添加决胜因素。在我们的示例中，扩展到 `qty` 使排序变为唯一，因此计算是确定的。

`RANK` 和 `DENSE_RANK` 与 `ROW_NUMBER` 的区别在于它们对相同排序（在本例中为数量）的行产生相同的排名。`RANK` 和 `DENSE_RANK` 的区别在于，前者比小于当前值的行数多 1。例如，行号为 6、7 和 8 的行都获得排名值 6（1 + 5 个小于 20 的行）和密集排名值 3（1 + 2 个小于 20 的数量）。结果是，`rank` 值之间会有间隙（如排名 1 和 5 之间），而 `dense rank` 则没有。

最后，`NTILE` 函数根据指定的桶数和排序为分区内的行分配桶号。在本例中，请求的桶数为 4，排序基于 `qty` 列。根据数量排序，结果中的第一行被分配桶号 1，后续是 2，依此类推。如果行数不能被桶数整除（假设余数为 R），前 R 个桶将额外有一行。在本例中我们有 11 行，导致桶大小为 2，余数为 3。因此前三个桶有三行而不是二。`NTILE` 函数是四种排名计算中最少使用的。它的主要用途是数据的统计分析。

记得可选的窗口分区句适用于所有窗口函数。按 `custid` 分区并按 `orderid` 排序的行计算示例：

```sql
SELECT custid, orderid, qty,
       ROW_NUMBER() OVER(PARTITION BY custid ORDER BY orderid) AS rownum
FROM dbo.orders
ORDER BY custid, orderid;
```

该查询生成以下输出，你可以看到每个客户的行号是独立的：

| custid | orderid | qty | rownum |
|---|---|---|---|
| A | 10005 | 30 | 1 |
| A | 40001 | 40 | 2 |
| A | 40005 | 10 | 3 |
| B | 20001 | 20 | 1 |
| B | 30001 | 10 | 2 |
| B | 30003 | 15 | 3 |
| B | 30004 | 20 | 4 |
| C | 10001 | 10 | 1 |
| C | 10006 | 10 | 2 |
| C | 20002 | 20 | 3 |
| C | 30007 | 30 | 4 |

该查询通过 `custid, orderid` 定义了显示顺序。记住，如果没有显式 `ORDER BY` 子句，显示顺序是不被保证的。

从优化的角度来看，就像窗口聚合函数一样，带有 `ROW_NUMBER` 等排名函数的查询的理想索引是 POC 索引。图 4-10 显示了不存在 POC 索引时的查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_308_0.png)

| Output List |
|---|
| [tempdb].[dbo].orderid, [tempdb].[dbo].rownum [tempdb].[dbo].Orders-custid, [tempdb].[dbo].rownum [tempdb].[dbo].Orders-qty |
| Order By |
| [tempdb].[dbo].custid Ascending, [tempdb].[dbo].rownum [tempdb].[dbo].Orders Ascending |

图 4-10 无 POC 索引的 `ROW_NUMBER` 优化。

由于不存在 POC 索引，优化器选择了带有排序的聚集索引扫描：随后它应用排序算子按 `custid, orderid` 对数据进行排序。这种顺序支持 `ROW_NUMBER` 函数的计算以及显示顺序（后者恰好是一致的）。段（Segment）算子在新段（分区）开始时标记序列投影（Sequence Project）算子。反之，后者在行是分区中的第一行时返回 1，如果不是则在之前值的基础上加 1。

图 4-11 使用 POC 索引对 `ROW_NUMBER` 进行优化。

这一次你获得了一个有序的 POC 索引，排序操作随之消失了。

与之前优化的聚合窗口函数相比，`ROW_NUMBER`、`RANK` 和 `DENSE_RANK` 是使用超快速流操作符进行优化的；没有池化。如果未来在使用如 `ROWS UNBOUNDED PRECEDING` 等常用特殊框架的聚合函数优化中也能看到这种特性就太棒了。

对于 `NTILE` 来说，优化器需要知道查询结果中的行数以计算分桶大小。因此，它使用优化来滑动窗口聚合 `COUNT(*) OVER()`，并使用了在图 4-2 中演示的池化技术。

`ROW_NUMBER` 函数和排序之间有一个奇怪的地方。`ORDER BY` 子句是强制性的，且不能是常量；它并不要求窗口排序是唯一的。这些要求意味着，当你仅为了唯一性目的而计算编号且不在乎顺序时，情况会发生变化。你也不希望支付任何与按要求顺序排列数据相关的不必要成本。如果你尝试创建窗口排序句，将会得到错误。如果你尝试指定一个常量（如 `ORDER BY NULL`），也将得到错误。惊讶的是，当你提供一个返回常量的子查询时（如 `ORDER BY (SELECT NULL)`），SQL Server 是接受的。这里有一个使用此技巧的查询示例：

```sql
SELECT orderid, orderdate, custid, qty,
       ROW_NUMBER() OVER(ORDER BY (SELECT NULL)) AS row
FROM dbo.Orders;
```

优化器意识到所有行都具有相同的排序值，它并不真正需要任何顺序的数据。因此，它仅仅根据访问顺序（数据布局、优化）分配行号。

## 偏移窗口函数

你使用窗口函数来请求位于窗口帧开头、结尾，或相对于当前行有特定偏移的元素。我将首先描述一对偏移函数调用 `FIRST_VALUE` 和 `LAST_VALUE`，然后描述 `LAG` 和 `LEAD` 对。

## FIRST_VALUE 和 LAST_VALUE

你可以使用 `FIRST_VALUE` 和 `LAST_VALUE` 函数分别从窗口帧中的第一行或最后一行返回元素。框架规范与我在“聚合窗口函数”主题的“窗口框架”部分描述的相同。这包含了对 `ROWS` 和 `RANGE` 之间关键性能差异的讨论。

当你需要从分区的第一行或最后行返回内容时，通常会使用 `FIRST_VALUE` 和 `LAST_VALUE` 函数。在这种情况下，你会希望配合 `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW` 框架使用 `FIRST_VALUE`，并配合 `ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING` 框架使用 `LAST_VALUE`。

例如，以下查询获取 `Orders` 表的结果，并返回每个客户第一笔订单的数量（`firstqty`）和最后一笔订单的数量（`lastqty`）：

```sql
SELECT custid, orderid, orderdate, qty,
       FIRST_VALUE(qty) OVER(PARTITION BY custid
         ORDER BY orderdate, orderid
         ROWS BETWEEN UNBOUNDED PRECEDING
         AND CURRENT ROW) AS firstqty,
       LAST_VALUE(qty) OVER(PARTITION BY custid
         ORDER BY orderdate, orderid
         ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING) AS lastqty
FROM dbo.Orders
ORDER BY custid, orderdate, orderid;
```

该查询生成以下内容：

| custid | orderid | orderdate | firstqty | lastqty |
|---|---|---|---|---|
| A | 10005 | 2013-12-24 | 30 | 10 |
| A | 40001 | 2014-01-09 | 40 | 10 |
| A | 40005 | 2014-02-12 | 30 | 10 |
| B | 30001 | 2013-08-12 | 10 | 20 |
| B | 20001 | 2014-12-20 | 15 | 20 |
| B | 30003 | 2014-04-18 | 10 | 20 |
| B | 30004 | 2014-04-18 | 10 | 20 |
| C | 10001 | 2013-12-24 | 10 | 30 |
| C | 10006 | 2014-01-18 | 10 | 30 |
| C | 20002 | 2014-02-16 | 20 | 30 |
| C | 30007 | 2014-09-07 | 10 | 30 |

通常，你会将这些函数与当前排序行以及同一客户第一笔订单的数量结合使用，例如通过 `qty - FIRST_VALUE(qty) OVER(...)` 来计算当前订单行之间的差异。

与窗口函数一样，窗口分区句是可选的。正如你可能猜到的那样，窗口排序句是强制性的。显式窗口框架规范是可选的，但默认框架是 `RANGE UNBOUNDED PRECEDING`。因此，你必须指定你的框架；否则，这两个函数都会出现问题。对于 `FIRST_VALUE` 函数，默认框架将给你分区中第一行的元素。但请记住，`RANGE` 选项比 `ROWS` 贵得多。对于 `LAST_VALUE`，`RANGE` 框架下的最后一行是当前行，而不是分区的最后一行。

`FIRST_VALUE` 和 `LAST_VALUE` 函数的优化方式与聚合函数相同。

## LAG 和 LEAD

你可以使用 `LAG` 和 `LEAD` 函数分别从上一行或下一行返回元素。正如你可能已经知道的，这些函数强制要求窗口排序句。这些函数的典型用途包括趋势分析（当前行与上一行之间的差异）、时效性（当前行与下一行之间的差异）等。例如，以下查询带有同一客户上一笔订单和下一笔订单的信息：

```sql
SELECT custid, orderid, orderdate, qty,
       LAG(qty) OVER(PARTITION BY custid
         ORDER BY orderdate, orderid) AS prevqty,
       LEAD(qty) OVER(PARTITION BY custid
         ORDER BY orderdate, orderid) AS nextqty
FROM dbo.Orders;
```

该查询生成以下内容：

| custid | orderid | orderdate | prevqty | nextqty |
|---|---|---|---|---|
| A | 10005 | 2013-12-24 | NULL | 40 |
| A | 40001 | 2014-01-09 | 30 | 10 |
| A | 40005 | 2014-02-12 | 40 | NULL |
| B | 30001 | 2013-08-12 | NULL | 15 |
| B | 20001 | 2014-12-20 | 10 | 10 |
| B | 30003 | 2014-04-18 | 15 | 10 |
| B | 30004 | 2014-04-18 | 10 | NULL |
| C | 10001 | 2013-12-24 | NULL | 10 |
| C | 10006 | 2014-01-18 | 10 | 20 |
| C | 20002 | 2014-02-16 | 10 | 30 |
| C | 30007 | 2014-09-07 | 30 | NULL |

## 统计窗口函数

T-SQL 支持两类提供分布信息的窗口函数：一组提供排序分布，另一组提供逆分布。

## 排序分布函数

排序分布函数根据指定的顺序，以百分比形式给出位于分区内的相对排名。T-SQL 支持两种此类函数，即 `PERCENT_RANK` 和 `CUME_DIST`。这两种函数的计算方式不同。

公式中涉及的元素：

- `rk` = 行的排名
- `nr` = 分区中的行数
- `np` = 在当前行之前或相同的行数

计算 `PERCENT_RANK` 的公式为 `(rk - 1) / (nr - 1)`。

计算 `CUME_DIST` 的公式为 `np / nr`。

例如，以下查询使用这些函数计算分数的排序分布：

```sql
USE TSQLV3;

SELECT testid, studentid, score,
       CAST(100.00 * PERCENT_RANK() OVER(PARTITION BY testid ORDER BY score) AS NUMERIC(5, 2)) AS percent,
       CAST(100.00 * CUME_DIST() OVER(PARTITION BY testid ORDER BY score) AS NUMERIC(5, 2)) AS cumedist
FROM Stats.Scores;
```

该查询生成以下输出：

| testid | studentid | score | percent | cumedist |
|---|---|---|---|---|
| Test ABC | Student E | 50 | 0.00 | 11.11 |
| Test ABC | Student C | 55 | 14.29 | 33.33 |
| Test ABC | Student D | 55 | 14.29 | 33.33 |
| Test ABC | Student H | 65 | 28.57 | 44.44 |
| Test ABC | Student I | 75 | 57.14 | 55.56 |
| Test ABC | Student B | 80 | 71.43 | 77.78 |
| Test ABC | Student F | 62 | 42.86 | 42.86 |
| Test ABC | Student A | 95 | 100.00 | 100.00 |
| Test ABC | Student G | 87 | 85.71 | 100.00 |
| Test XYZ | Student H | 65 | 33.33 | 40.00 |
| Test XYZ | Student I | 75 | 44.44 | 50.00 |
| Test XYZ | Student B | 80 | 55.56 | 70.00 |
| Test XYZ | Student F | 80 | 55.56 | 70.00 |
| Test XYZ | Student A | 95 | 77.78 | 100.00 |
| Test XYZ | Student G | 95 | 77.78 | 100.00 |
| Test XYZ | Student J | 95 | 77.78 | 100.00 |

## 逆分布函数

逆分布函数用于计算百分位数。第 N 百分位数是 N% 的观测值低于的数值。例如，第 50 百分位数（即中位数）测试分数是百分之五十分数低于数值。

T-SQL 提供了两个窗口函数，分别称为 `PERCENTILE_DISC` 和 `PERCENTILE_CONT`，它们分别实现了离散和连续模型。你可以在 0 到 1 的范围作为输入指定你所需的百分位数。使用 `WITHIN GROUP` 子句指定顺序。按照窗口函数的惯例，你可以对整个查询结果集进行计算，也可以使用 `PARTITION` 子句对限制的分区进行计算。

例如，以下查询使用两种模型计算同一次测试中学生分数的中位数：

```sql
SELECT testid, studentid, score,
       PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY score)
       OVER(PARTITION BY testid) AS median_disc,
       PERCENTILE_CONT(0.5) WITHIN GROUP(ORDER BY score)
       OVER(PARTITION BY testid) AS median_cont
FROM Stats.Scores;
```



由于窗口函数不应该隐藏细节，因此你将沿着行详情获取结果。相同的结果会在同一分区的所有行中重复。以下是该查询的输出：

| testid | studentid | score | medianandicont |
|---|---|---|---|
| Test ABC | Student E | 50 | 75 |
| Test ABC | Student C | 55 | 75 |
| Test ABC | Student D | 55 | 75 |
| Test ABC | Student H | 65 | 75 |
| Test ABC | Student I | 75 | 75 |
| Test ABC | Student B | 80 | 75 |
| Test ABC | Student F | 80 | 75 |
| Test ABC | Student A | 95 | 75 |
| Test ABC | Student G | 95 | 77.5 |
| Test XYZ | Student E | 50 | 75 |
| Test XYZ | Student C | 55 | 75 |
| Test XYZ | Student D | 55 | 75 |
| Test XYZ | Student H | 65 | 75 |
| Test XYZ | Student I | 75 | 75 |
| Test XYZ | Student B | 80 | 75 |
| Test XYZ | Student F | 80 | 75 |
| Test XYZ | Student A | 95 | 75 |
| Test XYZ | Student G | 95 | 77.5 |
| Test XYZ | Student J | 95 | 77.5 |

注意，对于 Test XYZ，函数返回相同的结果是因为行数是奇数。请记住，在中位数的情况下，当元素数为偶数时，两种模型使用不同的计算方法。

标准 SQL 支持作为分组有序集（grouped ordered sets）的逆函数。当你需要按组（在我们的案例中是测试）返回百分位数计算结果而不是在所有详细行中重复时，这非常方便。遗憾的是，SQL 目前还不支持有序集。但为了让你有一个直观感受，以下是如何使用两种模型按测试计算中位数的方法（不要在 SQL Server 中尝试这样做）：

```sql
SELECT testid,
    PERCENTILE_DIS(0.5) WITHIN GROUP(ORDER BY score) AS mediandisc,
    PERCENTILE_CONT(0.5) WITHIN GROUP(ORDER BY score) AS mediancont
FROM Stats.Scores
GROUP BY testid;
```

> 注意：你可以在此处找到关于有序集函数的 SQL 功能增强请求：https://connect.microsoft.com/SQLServer/feedback/details/728969。我们希望未来能看到此功能的实现。该概念不仅适用于逆分布函数，也适用于具有排序相关性的集合。

SQL Server 中的替代方案是使用窗口函数并用 `DISTINCT` 子句消除重复，如下：

```sql
SELECT DISTINCT testid,
    PERCENTILE_DIS(0.5) WITHIN GROUP(ORDER BY score)
    OVER(PARTITION BY testid) AS mediandisc,
    PERCENTILE_CONT(0.5) WITHIN GROUP(ORDER BY score)
    OVER(PARTITION BY testid) AS mediancont
FROM Stats.Scores;
```

此查询生成了以下输出：

| testid | mediandisc | mediancont |
|---|---|---|
| Test ABC | 75 | 75 |
| Test XYZ | 75 | 77.5 |

从优化的角度来看，这些函数的效率很低。查询计划有很多行被溢出（spooled），然后读取一次以计算聚合和细节。

## 空隙与岛屿 (Gaps and Islands)

空隙岛屿是 T-SQL 中的经典问题，涉及值的序列。值的类型通常是日期和时间，有时是整数。空隙任务（gaps）识别缺失值的范围，而岛屿任务（islands）识别现有值的范围。许多空隙岛屿任务可以使用窗口函数解决。使用整数序列解释要简单得多。实际上，空隙岛屿任务涉及日期序列。一旦你发现了使用整数序列的方法，就需要对日期序列进行微调。对于示例数据，我将使用以下表：

```sql
SET NOCOUNT ON;
USE tempdb;
IF OBJECT_ID('dbo.T1') IS NOT NULL DROP TABLE dbo.T1;
CREATE TABLE dbo.T1(col1 INT NOT NULL PRIMARY KEY);
GO
INSERT INTO dbo.T1(col1) VALUES(1),(2),(3),(7),(8),(9),(11),(15),(16),(17),(28);
```

空隙任务是识别序列中的缺失值。最简单的技巧之一涉及两个步骤：第一步是返回当前 `col1`（称为 `cur`）使用 `LEAD` 函数的下一个值（称为 `nxt`）。通过以下查询实现：

```sql
SELECT col1 AS cur, LEAD(col1) OVER(ORDER BY col1) AS nxt
FROM dbo.T1;
```

此查询生成了以下输出：

```
cur  nxt
-------------------
1    2
2    3
3    7
8    9
11   15
15   16
16   17
28   NULL
```

我们在 `col1` 上有索引，该查询的计划扫描一次索引以支持 `LEAD` 计算。检查 `cur-nxt` 值对，观察差异大于 1 代表空隙。第二步是根据上一个查询定义 CTE，然后过滤空隙，给 `cur` 加 1 并从 `nxt` 减 1 以返回实际信息。这里是完整的解决方案：

```sql
WITH C AS (
    SELECT col1 AS cur, LEAD(col1) OVER(ORDER BY col1) AS nxt
    FROM dbo.T1
)
SELECT cur + 1 AS range_from, nxt - 1 AS range_to
FROM C
WHERE nxt - cur > 1;
```

此查询生成了以下输出：

```
range_from  range_to
---------------------
4          6
10         10
12         14
18         27
```

注意 `nxt` 为 `NULL` 的对被自然过滤掉了，因为差异是 `NULL`，`NULL > 1` 是未知的，未知的也会被过滤掉。

## 岛屿 (Islands)

岛屿任务是空隙任务的逆过程。识别连续值的范围。我将首先使用 `T1.col1` 中的整数序列演示解决方案，然后使用更真实的日期序列示例。

识别岛屿的最有效技巧之一是根据序列列的计算行号，并使用这些行号计算岛屿标识符。为了查看如何实现这一点，首先根据列顺序计算行号，如下：

```sql
SELECT col1, ROW_NUMBER() OVER(ORDER BY col1) AS rownum
FROM dbo.T1;
```

此查询生成了以下输出：

| col1 | rownum |
|---|---|
| 1 | 1 |
| 2 | 2 |
| 3 | 3 |
| 7 | 4 |
| 8 | 5 |
| 9 | 6 |
| 11 | 7 |
| 15 | 8 |
| 16 | 9 |
| 17 | 10 |
| 28 | 11 |

仔细观察这两个序列，看看是否能识别出它们之间有助于识别岛屿的有趣关系。对于这一点，关注其中一个岛屿。如果你盯着输出足够久，你会在某一点发现它——在一个岛屿内，两个序列都以 1 个整数的固定间隔增加；因此，岛屿内两者的差异是相同的。此外，当从一个岛屿切换到下一个时，`rownum` 增加了 1，而 `col1` 增加了更多；因此，差异从一个岛屿增长到下一个，因此每个岛屿都是。这意味着可以使用差异作为岛屿或分组标识。运行以下查询根据此逻辑计算分组标识符 (`grp`)：

```sql
SELECT col1, col1 - ROW_NUMBER() OVER(ORDER BY col1) AS grp
FROM dbo.T1;
```

此查询生成了以下输出：

| col1 | grp |
|---|---|
| 1 | 0 |
| 2 | 0 |
| 3 | 0 |
| 7 | 3 |
| 8 | 3 |
| 9 | 3 |
| 11 | 4 |
| 15 | 7 |
| 16 | 7 |
| 17 | 7 |
| 28 | 17 |

由于 `col1` 上有索引，行号的计算不需要显式排序，如图 4-12 中该查询的计划所示。

| SELECT | Compute Scan | Sequence Project (Compute Scan) | Segment | Clustered Index Scan (Clustered) |
|---|---|---|---|---|
| Cost: 0% | Cost: 0% | Cost: 0% | Cost: 0% | [T1]:(PK_T1) Cost: 100% |

## 图 4-12：计算分组标识符的查询计划。

此计划中用的大部分成本在于对索引 `PK_T1` 的有序扫描。其余涉及行号计算和序列之间差值计算的工作量可以忽略不计。

最后，你能够根据查询定义一个 CTE，然后在外部查询中按 `grp` 对行进行分组，返回最小的 `col1` 作为岛的开始，并返回最大值作为结束。这里是完整的解决方案查询：

```sql
WITH C AS (
    SELECT col1, col1 - ROW_NUMBER() OVER(ORDER BY col1) AS grp
    FROM dbo.T1
)
SELECT MIN(col1) AS range_from, MAX(col1) AS range_to
FROM C
GROUP BY grp;
```

这生成了以下输出：

```
range_from   range_to
----------   -------
1           3
7           9
11          11
15          17
28          28
```

`T1` 中的 `col1` 序列具有唯一值，但你应该意识到，如果可能存在重复值，该解决方案将无法准确工作。因为 `ROW_NUMBER` 在目标分区内生成的是唯一值，即使对于具有相同排序值的行也是如此。为了使逻辑正确，你需要一个排名函数，该函数为所有具有相同排序值的行分配相同的排名，且不同的排名值之间没有间隙。幸运的是，存在这样的排名函数——那就是 `DENSE_RANK` 函数。这里是使用 `DENSE_RANK` 修改后的解决方案：

```sql
WITH C AS (
    SELECT col1, col1 - DENSE_RANK() OVER(ORDER BY col1) AS grp
    FROM dbo.T1
)
SELECT MIN(col1) AS range_from, MAX(col1) AS range_to
FROM C
GROUP BY grp;
```

由于 `DENSE_RANK` 函数在序列唯一和非唯一都能正常工作，因此使用 `DENSE_RANK` 和 `ROW_NUMBER` 是有意义的。只是使用 `ROW_NUMBER` 函数通过唯一序列解释逻辑会更容易，然后检查非唯一序列，并解释为什么优先选择 `DENSE_RANK`。

如前所述，在大多数情况下，你需要识别涉及时间和日期序列的“岛”（islands）。例如，假设你要查询 TSQL3 数据库中的 `Sales.Orders` 表，并为每个发货员（shipper）识别发货日期。发货日期记录在 `shippeddate` 列中。显然，该列可能存在重复值。此外，表中记录的所有订单并不都是订单；那些尚未发货的订单其 `shippeddate` 为 `NULL`。为了识别问题，你应该简单地忽略这些 `NULL`。为了支持你的解决方案，你需要在分区列 `shipper`、序列列 `shippeddate` 和决胜列 `orderid` 上建立索引键。由于可能存在 `NULL` 且应该被忽略，你需要一个过滤器从索引定义中排除 `NULL`。运行以下代码以获取建议：

```sql
CREATE UNIQUE INDEX idx_sid_sd_oid
ON Sales.Orders(shipper, shippeddate, orderid)
WHERE shippeddate IS NOT NULL;
```

在计算 `T1` 中 `col1` 值的分组标识符时，`col1` 值和密集排名（dense rank）值是具有相同间隔的整数。对于发货序列，情况要复杂一些，因为发货日期值和密集排名值是不同的类型；一个是时间类型，另一个是整数类型。尽管如此，连续值之间的间隔是固定的，在一种情况下是时间间隔 1 天，在另一种情况下是整数 1。因此，在这种情况下应用该逻辑，你从时间类型的 `shippeddate` 值中减去密集排名值乘以时间间隔（1 天）。该组的分组标识符将是一个时间值，但像之前一样，它对于同一个岛的所有成员来说都是相同的。

这里是实现此逻辑的完整解决方案查询：

```sql
WITH C AS (
    SELECT shipperid, shippeddate,
        DATEDIFF(day,
            -1 * DENSE_RANK() OVER(PARTITION BY shipperid ORDER BY shippeddate),
            shippeddate) AS grp
    FROM Sales.Orders
    WHERE shippeddate IS NOT NULL
)
SELECT shipperid,
    MIN(shippeddate) AS fromdate,
    MAX(shippeddate) AS todate,
    COUNT(*) as numorders
FROM C
GROUP BY shipperid, grp;
```

理解计算分组标识符背后逻辑的一种良好方法是首先运行定义 CTE `C` 的内部查询，并检查结果。你将得到以下输出：

| shipperid | shippeddate | grp |
|---|---|---|
| 1 | 2013-07-10 | 2013-07-09 |
| 1 | 2013-07-15 | 2013-07-13 |
| 1 | 2013-07-23 | 2013-07-20 |
| 1 | 2013-07-29 | 2013-07-25 |
| 1 | 2013-08-02 | 2013-07-28 |
| 1 | 2013-08-06 | 2013-07-31 |
| 1 | 2013-08-09 | 2013-08-02 |
| 1 | 2013-08-09 | 2013-08-02 |
| 1 | 2014-01-10 | 2013-12-07 |
| 1 | 2014-01-13 | 2013-12-09 |
| 1 | 2014-01-14 | 2013-12-09 |
| 1 | 2014-01-22 | 2013-12-16 |

你会注意到属于同一个岛的日期具有相同的分组标识符。定义 CTE `C` 的内部查询可以在图 4-13 中看到 ![](img/bdc38aa6f6e2987d91ee53814711_320.png)。

## 图 4-13：日期分组的内部查询计划

此计划非常高效。它对为该解决方案准备的索引进行有序扫描。计划中的工作成本可以忽略不计。完整解决方案生成的发货日期值输出如下：

| shipperid | fromdate | todate | numorders |
|---|---|---|---|
| 1 | 2013-07-10 | 2013-07-10 | 1 |
| 2 | 2013-07-11 | 2013-07-12 | 2 |
| 1 | 2013-07-15 | 2013-07-15 | 1 |
| 2 | 2013-07-16 | 2013-07-17 | 2 |
| 3 | 2013-07-15 | 2013-07-16 | 2 |

有不同的“岛”挑战。一种常见且有趣的情况是我们需要忽略特定大小间隔的情况下识别岛。例如，在我们按发货员识别发货日期的挑战中，你需要忽略 7 天的间隔。该变体的一种非常优雅的解决方案使用了函数：`LAG` 和 `SUM`。我们使用 `LAG` 为每个当前订单返回同一发货员的上一个订单的发货日期。使用 `CASE` 表达式计算一个名为 `startflag` 的标记，如果上一个日期与当前日期之间的差小于等于 7，则设置为 0，否则设置为 1。

这里是实现这一步骤的代码：

```sql
SELECT shipper, shippeddate, orderid,
    CASE WHEN DATEDIFF(day,
        LAG(shippeddate) OVER(PARTITION BY shipper ORDER BY shippeddate, orderid),
        shippeddate) <= 7 THEN 0 ELSE 1 END AS startflag
FROM Sales.Orders
WHERE shippeddate IS NOT NULL;
```



该查询生成以下输出：

| shipperid | shippeddate | orderid | startflag |
|---|---|---|---|
| 1 | 2013-07-10 | 10249 | 1 |
| 1 | 2013-07-15 | 10251 | 0 |
| 1 | 2013-07-23 | 10258 | 1 |
| 1 | 2013-07-29 | 10260 | 0 |
| 1 | 2013-08-02 | 10270 | 0 |
| 1 | 2013-08-06 | 10267 | 0 |
| 1 | 2013-08-09 | 10269 | 0 |
| 1 | 2013-08-09 | 10275 | 0 |
| 1 | 2013-08-12 | 10265 | 0 |
| 1 | 2013-08-16 | 10274 | 0 |
| 1 | 2013-08-21 | 10281 | 0 |
| 1 | 2013-08-21 | 10282 | 0 |
| 1 | 2013-08-27 | 10284 | 0 |
| 1 | 2013-09-03 | 10288 | 0 |
| 1 | 2013-09-03 | 10290 | 0 |
| 1 | 2013-09-11 | 10296 | 1 |
| 1 | 2013-09-12 | 10280 | 0 |

此查询生成以下输出：

| shipperid | shippdate | orderid | startflag | grp |
|---|---|---|---|---|
| 1 | 2013-07-10 | 10249 | 1 | 1 |
| 1 | 2013-07-15 | 10251 | 0 | 1 |
| 1 | 2013-07-23 | 10258 | 1 | 2 |
| 1 | 2013-07-29 | 10260 | 0 | 2 |
| 1 | 2013-08-02 | 10270 | 0 | 2 |
| 1 | 2013-08-06 | 10267 | 0 | 2 |
| 1 | 2013-08-09 | 10269 | 0 | 2 |
| 1 | 2013-08-09 | 10275 | 0 | 2 |
| 1 | 2013-08-12 | 10265 | 0 | 2 |
| 1 | 2013-08-16 | 10274 | 0 | 2 |
| 1 | 2013-08-21 | 10281 | 0 | 2 |
| 1 | 2013-08-21 | 10282 | 0 | 2 |
| 1 | 2013-08-27 | 10284 | 0 | 2 |
| 1 | 2013-09-03 | 10288 | 0 | 2 |
| 1 | 2013-09-09 | 10290 | 0 | 2 |
| 1 | 2013-09-11 | 10296 | 1 | 3 |
| 1 | 2013-09-12 | 10280 | 0 | 3 |

请注意，按照要求，分组标识对于同一个岛屿的所有成员是相同的，并且每个岛都是唯一的。最后一步是根据 `shipperid` 和 `grp` 对行分组，并返回每个岛的最小和最大日期，如下：

```sql
WITH C1 AS (
  SELECT shipperid, shippdate, orderid,
  CASE WHEN DATEDIFF(day,
    LAG(shippdate) OVER(PARTITION BY shipperid ORDER BY shippdate, orderid),
    shippdate) <= 7 THEN 0 ELSE 1 END AS startflag
  FROM Sales.Orders
  WHERE shippdate IS NOT NULL
),
C2 AS (
  SELECT *,
  SUM(startflag) OVER(PARTITION BY shipperid
    ORDER BY shippdate, orderid
    ROWS UNBOUNDED PRECEDING) AS grp
  FROM C1
)
SELECT shipperid,
  MIN(shippdate) AS fromdate,
  MAX(shippdate) AS todate,
  COUNT(*) as numorders
FROM C2
GROUP BY shipperid, grp;
```

此查询生成以下输出：

| | shipperid | frondate | todate | numders |
|---|---|---|---|---|
| 2 | 2014-12-31 | 2015-05-06 | 118 |
| 3 | 2013-09-11 | 2013-09-11 | 1 |
| 2 | 2013-08-26 | 2013-11-15 | 33 |
| 1 | 2014-04-04 | 2014-05-07 | 11 |
| 3 | 2013-07-15 | 2013-08-02 | 8 |
| 1 | 2013-11-18 | 2014-01-28 | 31 |
| 3 | 2013-12-11 | 2014-01-14 | 12 |
| 1 | 2014-05-12 | 2014-05-27 | 57 |
| 2 | 2014-08-06 | 2014-07-04 | 8 |
| 3 | 2013-08-12 | 2013-08-12 | |

对于每组最适用的值，你可以使用函数 `MAX`（或 `MIN`）。该函数会忽略 `NULL` 并适用于大多数数据类型。因此，在我们的案例中，聚合函数是 `MAX`，它被应用于 `CASE` 表达式的结果（在适用时为值列）。总而言之，我们的聚合元素是 `MAX(val)`。

这三个步骤结合在一起就为你提供了如下的解决方案查询：

```sql
SELECT objectid,
MAX(CASE WHEN attribute = 'attr1' THEN value END) AS attr1,
MAX(CASE WHEN attribute = 'attr2' THEN value END) AS attr2,
MAX(CASE WHEN attribute = 'attr3' THEN value END) AS attr3,
MAX(CASE WHEN attribute = 'attr4' THEN value END) AS attr4,
MAX(CASE WHEN attribute = 'attr5' THEN value END) AS attr5
FROM dbo..OpenSchema
GROUP BY objectid;
```

该查询的执行计划如图 4-15 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_326_0.png)

图 4-15 标准行转换查询的计划。

该计划看起来是一个普通的分组查询，其中 `Extra Scalar` 运算符处理 `CASE` 表达式。索引 `PK_OpenSchema` 定义在键列表 `(objectid, attribute)` 上，因此它按所需的顺序排列行，并且由于它是聚集索引，它涵盖了该查询。计划按顺序扫描索引，然后按该顺序将行提供给 `Stream Aggregate` 操作符。如你所见，这是一个非常高效的计划。

出现的一个问题是如何处理预先不知道具体唯一值是什么的情况？答案是从数据中查询这些唯一值，基于这些值构建一个包含这些值的行转换查询的字符串，然后使用动态 SQL 执行它。我将在本章稍后讨论自定义聚合的专门解决方案时演示如何实现。

上述行转换数据点的技术仅使用 SQL 结构，因此这是一种移植性很强的技术。此外，在接下来的“多对一”行转换方法中，你可以轻松地扩展它以支持多个聚合，而无需花费太大代价。

T-SQL 支持另一种技术，使用一个名为 `PIVOT` 的专用表操作符。像任何表操作符一样，你在查询的 `FROM` 子句中使用它。使用如下语法：

```sql
SELECT <col_list>
FROM <source> PIVOT(<agg_func>(<agg_col>) FOR <spreading_col> IN (<spreading_elements>)) AS P;
```

识别你行转换任务中的元素，解决方案查询如下：

```sql
SELECT objectid, attr1, attr2, attr3, attr4, attr5
FROM dbo..OpenSchema
PIVOT(MAX(value) FOR attribute IN(attr1, attr2, attr3, attr4, attr5)) AS P;
```

注意，展开元素在此语法中已经作为列名的标识符指定的，而不是它们在源中的字面字符串。如果标识符是不规范的（以数字、空格、保留关键字开头），你需要用双引号或方括号将其括起来，例如 `"2015"`。

该查询的计划如图 4-16 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_327_0.png)

图 4-16 使用 PIVOT 操作符的行转换查询计划。

如果你查看 `Stream Aggregate` 的属性，你会发现一个小惊喜：SQL Server 生成了与你在上一个解决方案使用的类似的 `CASE` 表达式。你会从性能角度意识到，这两个解决方案的对待方式几乎完全相同。

关于 `PIVOT` 操作符语法的一个奇特之处在于，你不需要指示展开和聚合部分，它们是隐含的；分组列是查询表中所有未作为展开和聚合列提到的列。在这种情况下，`OpenSchema` 表中唯一的列是 `objectid`。但你会意识到这种语法的危险：如果以后向表中添加列，下次运行查询时，这些列将自动成为分组的一部分。因此，建议直接在 CTE 中定义表表达式，其中仅投影需要在行转换操作符中作用的列。这里使用派生表实现这种方法的示例：

```sql
SELECT objectid, attr1, attr2, attr3, attr4, attr5
FROM (SELECT objectid, attribute, value FROM dbo.OpenSchema) AS D
PIVOT(MAX(value) FOR attribute IN(attr1, attr2, attr3, attr4, attr5)) AS P;
```

这种方法是安全的，你不需要担心以后向表中添加列。这种语法的优点是比之前的解决方案简洁。然而，它也有一些缺点。它是专有的，因此移植性较差。它仅限于一个聚合函数。在处理一对一行转换时，你可能需要多个函数。

# 第 4 章 分组、行转换与窗口处理

行转换，但在多对一行转换中允许作为 `PIVOT` 操作符输入进行展开或聚合列。如果你在疑问，T-SQL 不支持子查询作为输入。正如之前的解决方案中所解释的，如果提前知道展开值，你需要自己构建查询字符串并使用动态 SQL 执行它。我将在本章稍后演示示例。

# 多对一行转换

多对一行转换是一种可以将多个源行表示为单个目标行列的行转换。虽然一对一情况下聚合函数是人为的，但在多对一情况下它是有意义的。这是很大的区别。否则，这种情况下使用的技术是相同的。例如，假设你需要查询 `Sales.OrderValues` 视图。你想对数据进行行转换，以便每个客户返回一行，每个年份返回一列，并在每个客户和年份的交叉点返回适用值的总和。在这种情况下，分组列是 `custid`。展开列是 `orderyear`，目前的展开元素为 2013、2014 和 2015。为了允许在计算中使用 `orderyear` 别名，可以在表表达式中定义它。这是使用分组和 `CASE` 表达式的标准方法的查询：

```sql
SELECT custid,
SUM(CASE WHEN orderyear = 2013 THEN value END) AS [2013],
SUM(CASE WHEN orderyear = 2014 THEN value END) AS [2014],
SUM(CASE WHEN orderyear = 2015 THEN value END) AS [2015]
FROM (SELECT custid, YEAR(orderdate) AS orderyear, value
FROM Sales.OrderValues) AS D
GROUP BY custid;
```

该查询生成以下输出：

| custid | 2013 | 2014 | 2015 |
|---|---|---|---|
| 1 | NULL | 2022.50 | 2250.50 |
| 2 | 88.80 | 799.75 | NULL |
| 3 | NULL | NULL | 5960.00 |
| 4 | NULL | NULL | 5324.00 |
| 5 | NULL | NULL | 13849.00 |
| 6 | NULL | NULL | NULL |
| 7 | NULL | NULL | NULL |
| 8 | NULL | NULL | NULL |
| 9 | NULL | NULL | NULL |
| 10 | NULL | NULL | NULL |

这里使用 `PIVOT` 操作符的解决方案：

```sql
SELECT custid, [2013], [2014], [2015]
FROM (SELECT custid, YEAR(orderdate) AS orderyear, value
FROM Sales.OrderValues) AS D
PIVOT(SUM(value) FOR orderyear IN([2013], [2014], [2015])) AS P;
```

提到的，`PIVOT` 操作符的优点在于代码简洁，而缺点之一是它局限于一个聚合。所以如果你需要使用标准解决方案支持多个聚合，而代码长度对你来说是一个问题？有一种方法可以缩短查询。

你创建一个名为 `Matrix` 的辅助表，包含有一和一列。当行和列代表展开值时，你向表中填充 1。以下是创建和填充 `Matrix` 表的代码，随后是显示其内容的查询：

```sql
IF OBJECT_ID('dbo.Matrix', 'U') IS NOT NULL DROP TABLE dbo.Matrix;
CREATE TABLE dbo.Matrix
(orderyear INT NOT NULL PRIMARY KEY,
y2013 INT NULL,
y2014 INT NULL,
y2015 INT NULL
);
GO
INSERT INTO dbo.Matrix(orderyear, y2013) VALUES (2013, 1);
INSERT INTO dbo.Matrix(orderyear, y2014) VALUES (2014, 1);
INSERT INTO dbo.Matrix(orderyear, y2015) VALUES (2015, 1);
SELECT orderyear, y2013, y2014, y2015 FROM dbo.Matrix;
```

该查询生成以下输出：

| orderyear | y2013 | y2014 | y2015 |
|---|---|---|---|
| 2013 | 1 | NULL | NULL |
| 2014 | NULL | 1 | NULL |
| 2015 | NULL | NULL | 1 |

然后为了缩短解决方案的长度，执行以下操作：

- 将源表（我们的案例中为 `D`）与 `Matrix` 表连接，基于双方 `orderyear` 值的等效性匹配行。
- 代替 `CASE` 表达式形式的 `SUM(CASE WHEN orderyear = 2015 THEN value ELSE END)`，使用 `SUM(val*y2015)`。这在两种情况下都是等价的，当年份为 2015 时，返回 `val` 列的值（`y2015` 为 1），当年份不同时，返回 `NULL`。

以下是完整的解决方案查询：

```sql
SELECT custid,
SUM(val*y2013) AS [2013],
SUM(val*y2014) AS [2014],
SUM(val*y2015) AS [2015]
FROM (SELECT custid, YEAR(orderdate) AS orderyear, val
FROM Sales.OrderValues) AS D
INNER JOIN dbo.Matrix AS M ON D.orderyear = M.orderyear
GROUP BY custid;
```

如果你想计算计数而不是和，在不使用 `Matrix` 表的情况下，可以将 `SUM` 替换为 `COUNT` 或使用以下技术：

```sql
SELECT custid,
SUM(CASE WHEN orderyear = 2013 THEN 1 END) AS [2013],
SUM(CASE WHEN orderyear = 2014 THEN 1 END) AS [2014],
SUM(CASE WHEN orderyear = 2015 THEN 1 END) AS [2015]
FROM (SELECT custid, YEAR(orderdate) AS orderyear
FROM Sales.Orders) AS D
GROUP BY custid;
```

你对每个相应的订单返回 1，因此所有 1 的和就得出了计数。该查询生成以下输出：

| custid | 2013 | 2014 | 2015 |
|---|---|---|---|
| 1 | NULL | 3 | 3 |
| 2 | 1 | 2 | 1 |
| 3 | 1 | 5 | 1 |
| 4 | 2 | 7 | 4 |
| 5 | 3 | 10 | 5 |
| 6 | NULL | 4 | 3 |
| 7 | 3 | 7 | 1 |
| 8 | 1 | 1 | 1 |
| 9 | 3 | 8 | 6 |
| 10 | 1 | 5 | 8 |



# 使用 Matrix 表

使用 Matrix 表，你只需将 `SUM` 函数直接应用于 Matrix 列，如下：

```sql
SELECT custid,
SUM(y2013) AS [2013],
SUM(y2014) AS [2014],
SUM(y2015) AS [2015]
FROM (SELECT custid, YEAR(orderdate) AS ordearyear
FROM Sales.Orders) AS D
INNER JOIN dbo.Matrix AS M ON D.ordearyear = M.ordearyear
GROUP BY custid;
```

因为 Matrix 列仅在订单于该年份下单时才为 1，所以 `SUM` 函数在实践中计算的是计数。

记住，标准方法的用处之一是它可以在不增加显著成本的情况下支持多个聚合函数。以下是一个计算和、平均值和计数的示例：

```sql
SELECT custid,
SUM(val*y2013) AS sum2013,
SUM(val*y2014) AS sum2014,
SUM(val*y2015) AS sum2015,
AVG(val*y2013) AS avg2013,
AVG(val*y2014) AS avg2014,
AVG(val*y2015) AS avg2015,
SUM(y2013) AS cnt2013,
SUM(y2014) AS cnt2014,
SUM(y2015) AS cnt2015
FROM (SELECT custid, YEAR(orderdate) AS orderyear, val
FROM Sales.OrderValues) AS D
INNER JOIN dbo.Matrix AS M ON D.orderyear = M.orderyear
GROUP BY custid;
```

回想使用 Matrix 表缩短查询字符串的动机。当表达式较少时，这种优势可能并不明显，但想象一下你有几十个或数百个表达式；这种优势就会体现出来。

## 行逆转 (Unpivoting)

行逆转（Unpivoting）是一种将数据从列状态旋转到行的操作。行逆转任务的起点是以行转表形式存储的源数据。例如，使用以下代码创建表 `PvtOrders`，为其填充示例数据，然后查询其内容：

```sql
IF OBJECT_ID('dbo.PvtOrders', 'U') IS NOT NULL DROP TABLE dbo.PvtOrders;

SELECT custid, [2013], [2014], [2015]
INTO dbo.PvtOrders
FROM (SELECT custid, YEAR(orderdate) AS orderyear, val
FROM Sales.OrderValues) AS D
PIVOT(SUM(val) FOR orderyear IN([2013], [2014], [2015])) AS P;

SELECT custid, [2013], [2014], [2015] FROM dbo.PvtOrders;
```

该查询生成以下输出：

| custid | 2013 | 2014 | 2015 |
| --- | --- | --- | --- |
| 1 | NULL | 2022.50 | 2250.50 |
| 2 | 88.80 | 799.75 | 514.40 |
| 3 | 403.20 | 5960.75 | 660.00 |
| 4 | 1379.00 | 6406.90 | 5604.75 |
| 5 | 4324.40 | 13849.02 | 6754.16 |
| 6 | NULL | 1073.80 | 2160.00 |
| 7 | 9986.20 | 7817.88 | 730.00 |
| 8 | 982.00 | 3026.85 | 224.00 |
| 9 | 4074.28 | 11208.36 | 6680.61 |
| 10 | 1832.80 | 7630.25 | 11338.56 |

### 使用 CROSS JOIN 进行行逆转

数据存储在电子表格中是很常见的。假设你刚刚将数据从电子表格导入数据库。其当前的形状不便于查询，你需要将其转换为每个客户每年一行的形式。以下是实现此行逆转任务的方法：

你可以将行逆转任务分为三个步骤：

1. 生成副本。
2. 提取元素。
3. 删除 NULL 值。

应用于我们示例的第一个步骤是生成源数据的副本。由于你需要逆转的列很多，可以使用 `VALUES` 子句派出一个持有年份的派生表 `Y`，如下：

```sql
SELECT orderyear FROM (VALUES(2013), (2014), (2015)) AS Y;
```

该查询生成以下输出：

```
orderyear
2013
2014
2015
```

为了生成副本，你需要在源表 `PvtOrders` 和持有年份的表 `Y` 之间执行交叉连接（cross join），如下：

```sql
SELECT orderyear
FROM dbo.PvtOrders
CROSS JOIN (VALUES(2013), (2014), (2015)) AS Y;
```

第二个步骤是从每个副本的右侧列提取值以生成结果 `val` 列。`orderyear` 列决定了返回哪个副本的值。当它为 2013 时，你需要返回 `[2013]` 列的值；当它为 2014 时，你需要返回 `[2014]` 列的值，以此类推。为了实现这一步，你可以使用简单的 `CASE` 语句，如下：

```sql
SELECT custid, orderyear,
CASE orderyear
    WHEN 2013 THEN [2013]
    WHEN 2014 THEN [2014]
    WHEN 2015 THEN [2015]
END AS val
FROM dbo.PvtOrders
CROSS JOIN (VALUES(2013), (2014), (2015)) AS Y(orderyear);
```

该查询生成以下输出：

| custid | orderyear | val |
|---|---|---|
| 1 | 2013 | NULL |
| 1 | 2014 | NULL |
| 1 | 2015 | NULL |
| 2 | 2013 | 88.80 |
| 2 | 2014 | 799.75 |
| 2 | 2015 | 514.40 |
| 3 | 2013 | 403.20 |
| 3 | 2014 | 5960.78 |
| 3 | 2015 | 660.00 |

第三个步骤应该是移除无效的行。你不能在 `WHERE` 子句中引用 `val` 别名，因为它定义在 `SELECT` 列表中。作为替代方案，你可以使用 `CROSS APPLY` 运算符定义 `val` 别名并在查询中引用它，如下：

```sql
SELECT custid, orderyear, val
FROM dbo.PvtOrders
CROSS JOIN (VALUES(2013), (2014), (2015)) AS Y(orderyear)
CROSS APPLY (VALUES(CASE orderyear
    WHEN 2013 THEN [2013]
    WHEN 2014 THEN [2014]
    WHEN 2015 THEN [2015]
END)) AS A(val)
WHERE val IS NOT NULL;
```

该查询生成最终输出，其中 `val` 列中带有 NULL 的行被移除：

| custid | orderyear | val |
| --- | --- | --- |
| 1 | 2014 | 2022.50 |
| 1 | 2015 | 2250.50 |
| 2 | 2013 | 88.80 |
| 2 | 2014 | 799.75 |
| 2 | 2015 | 514.40 |
| 3 | 2013 | 403.20 |
| 3 | 2014 | 5960.78 |
| 3 | 2015 | 660.00 |

```sql
CREATE TABLE dbo.Sales
(
custid VARCHAR(10) NOT NULL,
qty2013 INT NULL,
qty2014 INT NULL,
qty2015 INT NULL,
val2013 MONEY NULL,
val2014 MONEY NULL,
val2015 MONEY NULL,
CONSTRAINT PK_Sales PRIMARY KEY(custid)
);
```

```sql
INSERT INTO dbo.Sales
(custid, qty2013, qty2014, qty2015, val2013, val2014)
VALUES
('A', 606.113, 7862.0, 6877.0, 4815.0),
('B', 243.861, 6321.5, 8413.0, 4476.0),
('C', 932.117, 2202.9, 342.0, 9083.0),
('D', 915.833, 1131.1, 9923.0, 4164.0),
('E', 822.246, 8870.0, 3860.0, 7399.0);
```

在这里你需要转置（pivot）不仅是一组列，而是两组：不同订单年份的数量列。为了实现这一点，我们使用了最后一种解决方案，`VALUES` 子句中的每行由三个元素组成：相似年份的常量、持有该年份数量的列以及持有该年份数值的列。以下是完整的查询：

```sql
SELECT custid, salesyear, qty, val
FROM dbo.Sales
CROSS APPLY
(VALUES(2013, qty2013, val2013),
(2014, qty2014, val2014),
(2015, qty2015, val2015)) AS A(salesyear, qty, val)
WHERE qty IS NOT NULL OR val IS NOT NULL;
```

此查询生成了以下输出：

| custid | salesyear | qty | val |
|---|---|---|---|
| A | 2013 | 606 | 4632.00 |
| A | 2014 | 113 | 6877.00 |
| A | 2015 | 781 | 4815.00 |
| B | 2013 | 243 | 2125.00 |
| B | 2014 | 861 | 8413.00 |
| B | 2015 | 637 | 4476.00 |
| C | 2013 | 932 | 9068.00 |
| C | 2014 | 117 | 342.00 |
| C | 2015 | 202 | 9083.00 |
| D | 2013 | 915 | 1131.00 |
| D | 2014 | 833 | 9923.00 |
| D | 2015 | 138 | 4164.00 |
| E | 2013 | 822 | 1907.00 |
| E | 2014 | 246 | 3860.00 |
| E | 2015 | 870 | 7399.00 |

### 使用 UNPIVOT 运算符

与 PIVOT 类似，T-SQL 支持一种名为 UNPIVOT 的表操作符。它作用于左侧提供的输入表，并生成结果表作为输出。UNPIVOT 操作符的设计非常优雅，要求你在其规范中提供最少的信息。无论你需要反转置（unpivot）多少列，你总是从中生成两个结果列——一个用于存储源列值，另一个用于存储源列名。你需要向 UNPIVOT 操作符提供的三个要素（按顺序指定并应用于 PivotOrders 表作为输入）：

1. **值列（Values column）**：你需要为存储源列值的列指定一个名称。在我们的案例中，我们将此列命名为 `val`。该结果列的类型与你正在反转置的源列类型相同（它们类型都相同）。
2. **名称列（Names column）**：你需要为存储源列名的列指定一个名称。在我们的案例中，我们想此列命名为 `orderyear`。该列的类型为 `NVARCHAR(128)`。
3. **源列（Source columns）**：你需要提供想要反转置的源列名称。在我们的案例中，这些是 `[2013],[2014],[2015]`。

在拥有上述三个要素的基础上，UNPIVOT 的语法如下：

```sql
SELECT <col_list>
FROM <table_source> UNPIVOT(<values_col> FOR <names_col> IN (<source_cols>)) AS U;
```

将其应用于 `PivotOrders` 表作为输入，得到以下查询：

```sql
SELECT custid, orderyear, val
FROM PivotOrders
UNPIVOT(val FOR orderyear IN ([2013],[2014],[2015])) AS U;
```

此查询生成了以下输出：

| custid | orderyear | val |
|---|---|---|
| 1 | 2014 | 25.50 |
| 1 | 2015 | 50.50 |
| 2 | 2013 | 88.80 |
| 2 | 2014 | 79.75 |
| 2 | 2015 | 51.40 |
| 3 | 2013 | 40.20 |
| 3 | 2014 | 59.78 |
| 3 | 2015 | 60.00 |

使用 UNPIVOT 操作符的方法简洁且优雅，但仅限于反转置一组列。从性能角度来看，`CROSS JOIN VALUES` 的方法最慢。`CROSS APPLY VALUES` 和 `UNPIVOT` 的执行计划相似，但在涉及足够数据时，`CROSS APPLY VALUES` 倾向于获得并行计划。

# 自定义聚合（Custom aggregations）

自定义聚合是你需要执行但内置聚合函数未提供的计算。例如，字符串拼接、聚合乘积等。为了演示自定义聚合的解决方案，我将使用以下代码创建并填充名为 `Groups` 的表：

```sql
USE tempdb;

IF OBJECT_ID('dbo.Groups') IS NULL DROP TABLE dbo.Groups;

CREATE TABLE dbo.Groups (
  groupid VARCHAR(10) NOT NULL,
  memberid INT NOT NULL,
  string VARCHAR(10) NOT NULL,
  val INT NOT NULL,
  PRIMARY KEY (groupid, memberid)
);
GO

INSERT INTO dbo.Groups(groupid, memberid, string, val) VALUES
('a', 3, 'str1', 6),
('a', 9, 'str2', 7),
('b', 2, 'strb1', 3),
('b', 4, 'strb2', 7),
('b', 5, 'strb3', 3),
('b', 9, 'strb4', 11),
('c', 3, 'str1', 8),
('c', 7, 'str2', 10),
('c', 9, 'str3', 12);
```

运行以下代码显示表的内容：

```sql
SELECT groupid, memberid, string, val FROM dbo.Groups;
```

此查询生成了以下输出：

| groupid | memberid | string | val |
|---|---|---|---|
| a | 3 | str1 | 6 |
| a | 9 | str2 | 7 |
| b | 2 | strb1 | 3 |
| b | 4 | strb2 | 7 |
| b | 5 | strb3 | 3 |
| b | 9 | strb4 | 11 |
| c | 3 | str1 | 8 |
| c | 7 | str2 | 10 |
| c | 9 | str3 | 12 |

假设你想根据 `memberid` 列中值的顺序，拼接 `string` 列中的组值。期望的输出如下：

| groupid | string |
|---|---|
| a | str1,str2 |
| b | strb1,strb2,strb3,strb4 |
| c | strc1,strc2,strc3 |

你可以使用四种主要的解决方案：

- 使用游标（cursor）
- 使用 CLR 用户定义聚合（UDA）
- 使用转置（pivoting）
- 使用专用解决方案

使用 CLR 用户定义聚合类型在第 9 章“可编程对象”中描述。我在这里描述其他三种类型。

## 使用游标

回想第 2 章“查询调优”中关于迭代和关系型解决方案的讨论。我们演示了基于游标的计算最大聚合的解决方案。以类似的方式，你可以计算字符串拼接聚合。按分组列（示例中的 `groupid` 和 `memberid`）排序并将行输入游标。你在循环中获取游标记录，并将当前值连接到变量中已拼接的内容上。如果组发生变化，你把上一个组的结果写入表变量，并重置持有拼接值的变量。以下是完整的解决方案代码：



```sql
DECLARE @Result AS TABLE(groupid VARCHAR(10), string VARCHAR(8000));

DECLARE
@groupid VARCHAR(10), @prvgroupid AS VARCHAR(10),
@string VARCHAR(10), @aggstring AS VARCHAR(8000);

DECLARE C CURSOR AS FAST_FORWARD FOR
SELECT groupid, string FROM dbo.Orders ORDER BY groupid, memberid;

OPEN C;

FETCH NEXT FROM C INTO @groupid, @string;

WHILE @@FETCH_STATUS = 0
BEGIN
    IF @groupid <> @prvgroupid
    BEGIN
        INSERT INTO @Result VALUES(@prvgroupid, @aggstring);
        SET @aggstring = NULL;
    END

    SELECT
    @aggstring = COALESCE(@aggstring + ', ', '') + @string,
    @prvgroupid = @groupid;

    FETCH NEXT FROM C INTO @groupid, @string;
END

IF @prvgroupid IS NOT NULL
INSERT INTO @Result VALUES(@prvgroupid, @aggstring);

CLOSE C;
DEALLOCATE C;

SELECT groupid, string FROM @Result;
```

## 使用转置

处理自定义聚合的另一种方法是使用转置（pivoting）。这种方法适用于元素数量较少且有固定最大上限的情况。

使用转置的困难之处在于，源表并不包含所有所需的要素。记住，对于转置，你需要识别三个要素：分组列、扩展列和值列。在我们的示例中，分组列是 `groupid`，聚合函数和列应用于字符串的 `MAX`，但缺少扩展列。

你需要扩展列的值在各个组之间是通用的。解决方案是计算按 `groupid` 分区并按 `memberid` 排序的行号。假设每个组有最大数量的元素（例如示例中为四个），你可以将这些行号视为扩展值。以下是使用透视（pivoting）的解决方案查询：

```sql
SELECT groupid,
[1]
+ COALESCE(',',' + [2], ' ')
+ COALESCE(',',' + [3], ' ')
+ COALESCE(',',' + [4], ' ') AS string
FROM (SELECT string,
ROW_NUMBER() OVER(PARTITION BY groupid ORDER BY memberid) AS rn
FROM dbo.Groups) AS D
PIVOT(MAX(string) FOR rn IN([1],[2],[3],[4])) AS P;
```

一个组至少有一个元素，但不能保证这一点；透视查询中的元素越多 NULL 越多。`COALESCE` 函数用于将 `'' + <element>` 替换为该元素不存在时的空字符串。实现相同目的更优雅的方法是使用 `CONCAT` 函数，如下：

```sql
SELECT groupid,
CONCAT([1],','+[2],','+[3],','+[4]) AS string
FROM (SELECT string,
ROW_NUMBER() OVER(PARTITION BY groupid ORDER BY memberid) AS rn
FROM dbo.Groups) AS D
PIVOT(MAX(string) FOR rn IN([1],[2],[3],[4])) AS P;
```

该函数拼接其输入，默认将 NULL 输入替换为空字符串。

使用透视来处理自定义聚合的优势是性能的提升。请记住，透视查询被优化为分组查询，因此你应该预期类似于分组查询的性能。这种方法主要的缺点是它在配合小组使用时最有效。对于大组，查询字符串会变得太长。

## 专门解决方案

自定义聚合的解决方案基于游标、透视，而 CLR UDA 是相当通用的。我的意思是，字符串拼接聚合的解决方案与乘积聚合看起来相似。假设你的首要任务是性能：在追求性能时，你通常会发现自己使用了更专业的工具，因此牺牲了通用性。这在生活中通常是如此的，而不仅仅是在 T-SQL 中。虽然专门工具可以为特定任务提供更好的性能，但它们对其他任务的重用性较低。在自定义聚合的背景下，你用于字符串拼接聚合最快解决方案的技巧可能无法重用于乘积聚合。因此，你获得了性能优势，但丢失了通用性。

我将为聚合字符串拼接、乘法和众数（mode）提供专门解决方案。

## 使用 FOR XML 进行字符串拼接

T-SQL 中应用聚合字符串拼接的最快方法之一基于 XML 能力。我将首先演示 `Groups` 表中单个组的技术，然后将其应用于不同的组。假设你想拼接以下查询返回的字符串：

```sql
SELECT string
FROM dbo.Groups
WHERE groupid = 'b'
ORDER BY memberid;
```

此查询生成以下输出：

```
String
------
strb1
strb2
strb3
strb4
```

使用 `FOR XML` 选项，你可以请求将结果作为单个 XML 实例返回。通过使用 `PATH` 模式并将空字符串作为输入，同时要求返回文本节点，你可以获得基本的字符串拼接，而没有额外的 XML 标签：

```sql
SELECT string AS [text()]
FROM dbo.Groups
WHERE groupid = 'b'
ORDER BY memberid
FOR XML PATH('');
```

此查询生成以下输出：

strb1strb2strb3strb4

这会转义字符串。这意味着某些特殊字符（如 `<`、`>` 等）会被转换为 `&lt;`、`&gt;` 等类似的字符。如果你的数据中存在此类特殊字符且你想返回带有原始字符的字符串，有一个变通方法。你添加 `TYPE` 指令，然后使用 `.value` 方法从 XML 实例中提取字符字符串，如下所示：

```sql
SELECT
(SELECT string AS [text()]
FROM dbo.Groups
WHERE groupid = 'b'
ORDER BY memberid
FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)');
```

要在字符串之间添加逗号等分隔符，请将 SELECT 列表中的表达式更改为 `',' + string`。你最终会在拼接字符串的开头得到额外的分隔符。要删除它，可以使用 `STUFF` 函数，如下：

```sql
SELECT
STUFF((SELECT ',' + string AS [text()]
FROM dbo.Groups
WHERE groupid = 'b'
ORDER BY memberid
FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '');
```

`STUFF` 函数作用于作为第一个输入的字符串。它从第二个输入指定的字符位置删除与第三个输入相同数量的字符。然后它将第四个输入指定的字符串插入到第二个输入指定的位置（在本例中为空字符串）。根据前一个查询提供的输入，`STUFF` 函数删除了第一个字符——即额外的分隔符。

此查询针对单个组有效。如果你想将此逻辑应用于所有组，可以将其实现为针对 `Groups` 的相关子查询，如下：

```sql
SELECT groupid,
STUFF((SELECT ',' + string AS [text()]
FROM dbo.Groups
WHERE groupid = G.groupid
ORDER BY memberid
FOR XML PATH(''), TYPE).value('.', 'VARCHAR(MAX)'), 1, 1, '')
FROM dbo.Groups AS G
GROUP BY groupid;
```

在实践中，如果查询中存在 `ORDER BY` 子句，无法保证在赋值发生之前查询会先处理排序。我见过某些执行计划是在赋值之前处理排序的，而有些是在之后；这纯粹是优化的问题。

尝试执行有序聚合拼接是说明未定义行为如何给你带来麻烦的一个佳例。为了演示这一点，我将使用表 `T1`，你可以通过运行以下代码来创建并填充它：

```sql
USE tempdb;
IF OBJECT_ID(N'dbo.T1', N'U') IS NOT NULL DROP TABLE dbo.T1;

CREATE TABLE dbo.T1
(
  col1 INT NULL IDENTITY,
  col2 VARCHAR(100) NULL,
  filler BINARY(2000) NULL DEFAULT(0x),
  CONSTRAINT PK_T1 PRIMARY KEY(col1)
);

INSERT INTO dbo.T1(col2)
SELECT 'String ' + CAST(n AS VARCHAR(10))
FROM TSQLV3.dbo.GetNums(1,100) AS Nums;
```

这里是一个赋值 `SELECT` 语法的常见用法示例，目的是根据 `col1` 的排序拼接 `col2` 中的值：

```sql
DECLARE @s AS VARCHAR(MAX);
SET @s = '';

SELECT @s = @s + col2 + ';'
FROM dbo.T1
ORDER BY col1;

PRINT @s;
```

当我第一次运行这段代码时，我得到了图 4-17 所示的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_344_0.png)

**图 4-17** 使用赋值 `SELECT` 的测试 1 计划。

观察到该计划按顺序扫描了聚集索引 `PK_T1`（该索引以 `col1` 为键）。然后计划使用 `Compute Scalar` 算子处理赋值。该计划的执行符合某些人的预期，即值将根据指定的顺序进行拼接：

String1:String2:String3:String4:String5:String6:String7:String8:String9
String10:String11:String12:String13:String14:String15:String16:String17:String18
String19:String20:String21:String22:String23:String24:String25:String26:String27
String28:String29:String30:String31:String32:String33:String34:String35:String36
String37:String38:String39:String40:String41:String42:String43:String44:String45
String46:String47:String48:String49:String50:String51:String52:String53:String54
String55:String56:String57:String58:String59:String60:String61:String62:String63
String64:String65:String66:String67:String68:String69:String70:String71:String72
String73:String74:String75:String76:String77:String78:String79:String80:String81
String82:String83:String84:String85:String86:String87:String88:String89:String90
String91:String92:String93:String94:String95:String96:String97:String98:String99:String100

但是并没有文档为你提供这样的保证。这恰好是优化器的选择导致了有序字符串。

接下来，我向表中添加了以下非聚集索引，然后运行了相同的赋值：

```sql
CREATE NONCLUSTERED INDEX idx_nc_col2_col1 ON dbo.T1(col2);
GO
DECLARE @s VARCHAR(MAX);
SET @s = '';

SELECT @s = @s + col2 + ';'
FROM dbo.T1
ORDER BY col1;

PRINT @s;
```

该查询的执行计划如图 4-18 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_345_0.png)

**图 4-18** 使用赋值 `SELECT` 的测试 2 计划。

观察到优化器选择了新索引，因为它比聚集索引窄（仅包含感兴趣列）。它没有像查询要求那样对行排序。因此计划对索引进行无序扫描，并添加了一个 `Sort` 算子。讽刺的是，计划在赋值之后执行了排序！不仅如此，你并没有按照所需的顺序获得拼接值；相反，你得到的是中间状态。当我运行这段代码时，得到了如下输出：

String100;

可以说这种方法依赖于它能工作，而且这导致了优化器改变如何优化代码，像新索引一样，这让你陷入了麻烦。如果你遵循定义良好的技术，可以避免很多这种痛苦。

## 聚合乘积

计算聚合乘积是另一种自定义计算类型。它通常用于财务应用程序——例如，计算利率。对于你的 `Groups` 表，你需要计算每组 `val` 列的乘积。这个任务有一个高效的解决方案——特别是使用对数计算。有两组等式是很有用的：

```
log(y) = x
```

```
log(xy) = log(x) + log(y)
```

在 T-SQL 中，`LOG` 函数计算第一个输入的自然对数（其中 $e$ 是约等于 2.71828 的常数）。`EXP` 函数返回输入的指数。也就是说，$EXP(1)$ 是 $e$。这意味着在下面的等式中，一个意味着另一个：

```
log(y) = x <=> EXP(x) = y
```

在下面的等式中，一个意味着另一个：

```
log(xy) = log(x) + log(y)
```

在 T-SQL 中表示的计算所需乘积的查询需要修正由 `LOG` 和 `EXP` 函数使用的浮点不精确性引起的错误：

```sql
SELECT groupid, ROUND(EXP(SUM(LOG(val))), 0) AS product
FROM Groups
GROUP BY groupid;
```

该查询生成如下：

| groupid | product |
|---|---|
| a | 42 |
| b | 693 |
| c | 96 |

如果你也支持零和负值，情况就会变得更加复杂，因为 `LOG` 函数不支持这些值。为了看到此演示，运行以下代码重新填充 `Groups` 表：

```sql
TRUNCATE TABLE dbo.Groups;

INSERT INTO dbo.Groups(groupid, memberid, string, val) VALUES
('a', 3, 'str1', -6),
('a', 9, 'str2', 7),
('b', 2, 'strb1', -3),
('b', 4, 'strb2', -7),
('b', 5, 'strb3', 3),
('b', 9, 'strb4', -11),
('c', 3, 'strc1', 8),
('c', 7, 'strc2', 0),
('c', 9, 'strc3', -12);
```

尝试用新数据运行查询：

```sql
SELECT groupid, ROUND(EXP(SUM(LOG(val))), 0) AS product
FROM Groups
GROUP BY groupid;
```

查询因以下错误失败：

Msg 623, Level 16, State 1, Line 10 An invalid floating point operation occurred.

正确处理零和负数，你需要几点。使用 `NULLIF` 函数对 `val` 配合 `NULL` 以避免错误。对绝对值应用原始的乘积计算。使用 `MIN` 聚合和 `CASE` 表达式，使用一个标记（称为 *zero*），如果至少有一个零则标记为 1，如果没有则为 0。使用 `COUNT` 聚合和 `CASE` 表达式，你计算一个标记（称为 *negative*），如果你有奇数个负值则标记为 -1，否则为 1。这里是应用这些计算的代码：

```sql
SELECT groupid,
-- 使用 NULLIF 将 0 替换为 NULL，对绝对值应用乘积
ROUND(EXP(SUM(LOG(ABS(NULLIF(val, 0))))), 0) AS product,
CASE WHEN MIN(CASE WHEN val = 0 THEN 1 ELSE 0 END) = 1 THEN 0 ELSE 1 END AS zero,
CASE WHEN COUNT(CASE WHEN val < 0 THEN 1 END) % 2 > 0 THEN -1 ELSE 1 END AS negative
FROM Groups
GROUP BY groupid;
```

这段代码生成如下输出：

| groupid | product | zero | negative |
|---|---|---|---|
| a | 42 | 1 | -1 |
| b | 693 | 1 | 1 |
| c | 96 | 0 | 1 |

然后为了得到正确的乘积，将绝对值的乘积乘以零标记和负标记，如下：



```sql
SELECT groupid,
ROUND(EXP(SUM(ABS(NULLIF(val, 0)))), 0) AS product,
MIN(CASE WHEN val = 0 THEN 0 ELSE 1 END) AS zero,
CASE WHEN COUNT(CASE WHEN val < 0 THEN 1 END) % 2 > 0 THEN -1 ELSE 1 END AS negative
FROM Groups
GROUP BY groupid;
```

这里是完整的解决方案代码：

```
USE TSQLV3;
WITH C AS (
  SELECT custid, empid, COUNT(*) AS cnt,
  ROW_NUMBER() OVER(PARTITION BY custid
  ORDER BY COUNT(*) DESC, empid DESC) AS rn
FROM Sales.Orders
GROUP BY custid, empid
)
SELECT custid, empid, cnt
FROM C
WHERE rn = 1;
```

该查询生成了以下输出：

| custid | empid | cnt |
|---|---|---|
| 1 | 4 | 2 |
| 2 | 3 | 2 |
| 3 | 3 | 3 |
| 4 | 4 | 4 |
| 5 | 3 | 6 |

如果你希望在打破平局时返回所有并列项，则需要对你的解决方案进行两处更改。你需要使用 `RANK` 或 `DENSE_RANK` 函数（任一均可），并从窗口排序类中移除员工 ID。这是修改后的代码：

```
WITH C AS (
  SELECT custid, empid, COUNT(*) AS cnt,
  RANK() OVER(PARTITION BY custid 
  ORDER BY COUNT(*) DESC) AS rn
FROM Sales.Orders
GROUP BY custid, empid
)
SELECT custid, empid, cnt
FROM C
WHERE rn = 1;
```

此代码生成了以下输出：

| custid | empid | cnt |
|---|---|---|
| 1 | 1 | 2 |
| 1 | 4 | 2 |
| 2 | 3 | 2 |
| 3 | 3 | 3 |
| 4 | 4 | 4 |
| 5 | 3 | 6 |

请注意，客户 1 有两个员工 ID 处理了最大数量的订单。

回到涉及平局决定的原始任务，考虑解决方案的优化。由于 `ROW_NUMBER` 函数的排序部分基于计算结果，即使你为 `(custid, empid)` 上创建了索引，在查询计划中也会对整个输入集进行排序。对于大量输入，排序开销将是非常昂贵的。可以通过索引视图避免排序（作为一个挑战，看看你是否能想出来），但如果你无法负担索引视图怎么办？

有一种替代方案，依赖于基于分组和字符串拼接的“进长排序”概念，可以高效地利用索引 `(custid, empid)`。该解决方案包含以下步骤：

1. 编写一个分组查询，计算每个客户和员工的订单计数。
2. 在同一个分组查询中，计算一个由计数转换为 `BINARY(4)` 与转换为 `BINARY(4)` 的员工 ID 拼接成的二进制字符串。将拼接后的值命名为 `binval`。
3. 基于分组查询定义一个表表达式并命名为 D。
4. 对 D 编写一个外部查询，按客户 ID 对行分组。在该查询中，计算结果 `MAX(binval)` 包含了最大计数以及众数员工（最大员工 ID）的 ID。应用 `substring` 逻辑提取这两个部分并将它们转换回原始类型。

以下是完整的解决方案：

```
SELECT custid,
CAST(SUBSTRING(MAX(binval), 5, 4) AS INT) empid,
CAST(SUBSTRING(MAX(binval), 1, 4) AS INT) cnt
FROM (
  SELECT custid,
  CAST(COUNT(*) AS BINARY(4)) + CAST(empid AS BINARY(4)) AS binval
  FROM Sales.Orders
  GROUP BY custid, empid
) D;
```

这种解决方案的巧妙之处在于，分层分组和聚合可以依赖上述索引的顺序。为了比较两种解决方案的性能，我创建了一个包含 10,000,000 行的 `OrdersBig` 表，并在 `(custid, empid)` 上建立了索引 `idx_custid_empid`。图 4-19 显示了针对该表的两种解决方案的计划。顶部计划是基于进长排序概念的解决方案。

注意第一个计划在计算行数之前存在昂贵的 `Sort`（排序），而第二个计划中没有。第一个解决方案在我的机器上花费了 15 秒完成，第二个花费了 5 秒。

在考虑自定义定制章节之前，我想提到标准 SQL 定义了一类名为“有序集函数”（ordered set function）的函数，但在本书写作日期，SQL Server 尚未提供该函数。有序集是一种可以在分组查询中使用的相关函数。标准定义了 `WITHIN GROUP` 子句，你可以在其中指定函数的排序规范。有多个可以实现为有序函数的示例：聚合连接、百分位数、CLR 聚合等。你可以在此处找到关于有序集函数的特性请求：https://connect.microsoft.com/SqlServer/feedback/728969。

```
Query 1: Query cost (relative to the batch): 85%
WITH C AS (SELECT custid, COUNT(*) AS ROW_NUMBER() OVER(PARTITION BY custid ORDER BY COUNT(*) DESC, empid DESC)
```

![](img/bdc38aa36f6e2987d913ee5381474711_351_0.png)

```
Query 2: Query cost (relative to the batch): 126%
SELECT custid, (SUBSTRING(MAX(binval), 1, 4) AS INT) AS custid FROM (SELECT custid,
```

![](img/bdc38aa36f6e2987d913ee5381474711_351_1.png)

图 4-19 解决方案的计划。

## 分组集 (Grouping sets)

T-SQL 支持许多与分组集主题相关的特性，用于数据分析。这些特性包括 `GROUPING SET`、`CUBE`、`ROLLUP` 以及 `GROUPING_ID` 和 `GROUPING` 函数。为了演示这些特性，我将在示例中使用名为 `Orders` 的表。运行以下代码创建 `Orders` 表并填充示例数据：

```
SET NOCOUNT ON;
USE tempdb;

IF OBJECT_ID('dbo.Orders', 'U') IS NULL DROP TABLE dbo.Orders;

CREATE TABLE dbo.Orders (
    orderid INT NOT NULL,
    orderdate DATETIME NOT NULL,
    empid INT NOT NULL,
    custid VARCHAR(5) NOT NULL,
    qty INT NOT NULL,
    CONSTRAINT PK_Orders PRIMARY KEY(orderid)
);
GO

INSERT INTO dbo.Orders(orderid, orderdate, empid, custid, qty)
VALUES
(3001, '2012-08-02', 3, 'A', 10),
(10001, '2012-12-24', 1, 'A', 12),
(10005, '2012-12-24', 1, 'B', 20),
(40001, '2013-01-09', 4, 'A', 40),
(10006, '2013-01-18', 1, 'C', 14),
(20002, '2012-02-12', 2, 'B', 12),
(40005, '2014-02-12', 4, 'A', 10),
(20002, '2014-02-16', 2, 'C', 20),
(30003, '2014-04-18', 3, 'B', 15),
(40004, '2014-04-18', 3, 'C', 22),
(40007, '2012-09-07', 3, 'D', 30);
```

在描述特性和函数之前，我先说明：**分组集**（grouping set）术语简单描述的是分组查询中的表达式集。例如，如果你有一个按 `custid`, `empid`, `YEAR(orderdate)` 分组的查询，你的查询就定义了 `(custid, empid, YEAR(orderdate))`。历史上，T-SQL 支持每个查询定义一个组。通过我即将描述的特性，你可以在一个查询中定义多个集合。问题是，为什么不呢？有两个原因。其中有些报告需要显示多级聚合——你需要显示每日、每月和按年的报告。另一个原因是为了在表中持久不同的集合以便快速检索。这是数据仓库中的经典需求。虽然其他技术可以帮助查看分析查询，但此技术需要 SQL Server 企业版。后续章节将描述上述特性。

## GROUPING SETS 子句

你使用 `GROUPING SETS` 子句在一个查询中定义多个集合。将其作为 `GROUP BY` 子句的一部分。`GROUPING SETS` 子句有自己的括号，每对括号代表一个不同的分组。如果没有逗号，每个表达式被视为一个独立的集合。空括号从整个输入集中只定义一个组；换句话说，用它来计算聚合值。使用 `GROUPING SETS` 子句的示例查询定义了四个集合：

```
SELECT custid, empid, YEAR(orderdate) AS orderyear, SUM(qty) AS qty
FROM dbo.Orders
GROUP BY GROUPING SETS
  (custid, empid, YEAR(orderdate)),
  (custid, YEAR(orderdate)),
  (empid, YEAR(orderdate)),
  ()
```

但是有一个问题：如果不同分组集的结果集结构不同，如何合并它们？解决方案是在结果结果行关联的分集的列中使用 `NULL` 作为占位符。以下是前一个查询的输出：

| custid | empid | orderyear | qty |
|---|---|---|---|
| A | 1 | 2012 | 12 |
| B | 1 | 2012 | 20 |
| NULL | 1 | 2012 | 32 |
| C | 1 | 2013 | 14 |
| NULL | 1 | 2013 | 14 |
| B | 2 | 2013 | 12 |
| NULL | 2 | 2013 | 12 |
| C | 2 | 2014 | 20 |
| NULL | 2 | 2014 | 20 |
| A | 3 | 2012 | 10 |
| C | 3 | 2012 | 22 |
| D | 3 | 2012 | 30 |
| NULL | 3 | 2012 | 62 |
| B | 3 | 2014 | 15 |
| NULL | 3 | 2014 | 15 |
| A | 4 | 2013 | 40 |
| NULL | 4 | 2013 | 40 |
| A | 4 | 2014 | 10 |
| NULL | 4 | 2014 | 10 |
| NULL | NULL | NULL | 25 |
| A | NULL | 2012 | 22 |
| B | NULL | 2012 | 20 |
| C | NULL | 2012 | 22 |
| D | NULL | 2012 | 30 |
| A | NULL | 2013 | 40 |
| B | NULL | 2013 | 12 |
| C | NULL | 2013 | 14 |
| A | NULL | 2014 | 10 |
| B | NULL | 2014 | 15 |
| C | NULL | 2014 | 20 |

如果你想在没有 `GROUPING SETS` 子句的情况下获得相同的结果，你需要编写四个分组查询并统一它们的结果，如下所示：

```
SELECT custid, empid, YEAR(orderdate) AS orderyear, SUM(qty) AS qty
FROM dbo.Orders
GROUP BY custid, empid, YEAR(orderdate)

UNION ALL

SELECT custid, NULL AS empid, YEAR(orderdate) AS orderyear, SUM(qty) AS qty
FROM dbo.Orders
GROUP BY custid, YEAR(orderdate)

UNION ALL

SELECT NULL AS custid, empid, YEAR(orderdate) AS orderyear, SUM(qty) AS qty
FROM dbo.Orders
GROUP BY empid, YEAR(orderdate)

UNION ALL

SELECT NULL AS custid, NULL AS empid, NULL AS orderyear, SUM(qty) AS qty
FROM dbo.Orders;
```

`GROUPING SETS` 子句相比多个查询具有几个优势。显然，代码要短得多。此外，它还可以优化。使用四个查询，数据将被扫描四次。而使用 `GROUPING SETS` 子句，优化器会分析分组集并尝试通过汇总（rolling up）聚合结果来尽量减少扫描次数。查看此优化技术的应用，请检查图 4-20 中带有 `GROUPING SETS` 子句的查询执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_354_0.png)

图 4-20 使用 `GROUPING SETS` 的查询计划。

观察到数据被扫描了两次。计划的顶部分支从左到右扫描聚集索引。它计算了一个名为 `Expr1002` 的标量，代表计算 `YEAR(orderdate)` 的结果。由于我没有准备任何索引来支持分组和聚合，优化器添加了一个 `Sort`（排序）算符，按 `empid`、`YEAR(orderdate)`、`custid` 对行进行排序。你可以通过创建支持索引来避免这一点，我稍后会进行演示。基于此顺序，以汇总（rollup）的方式，可以计算所有代表前导组合的分组集。使用从高到低的零基偏移：

- 第 0 层：`empid`, `YEAR(orderdate)`, `custid`
- 第 1 层：`empid`, `YEAR(orderdate)`
- 第 2 层：`empid`
- 第 3 层：`()`

`Sort` 算符左侧第一个聚合算符表示基础分组集 (0)。第二个聚合算符负责聚合结果的汇总。如果你检查查询，会发现 `GROUPING SETS` 子句定义了上述三个分组集：第 0、1 和 3 层，但没有第 2 层。因此，在查看第二个聚合算符的属性时，`Rollup Levels`（汇总级别）将只报告所需的级别。

查询定义了一个额外的分组集 `(custid, YEAR(orderdate))`，该集无法根据计划的第一个分支计算得出。计划中的第二个分支（底部）扫描数据，按 `YEAR(orderdate)`, `custid` 对其排序，然后计算剩余分组集的聚合结果。不需要第二个聚合算符，因为只剩下一个分组；没有需要进行汇总。

如前所述，你可以通过准备支持索引来避免计划中的显式排序。在我们的案例中，其中一个元素是计算结果，因此你可以根据计算添加一个计算列，并将其作为索引的一部分。你希望索引是覆盖的，所以不要忘记包含聚合列（在案例中为 `qty`）。以下是添加计算列和支持索引的代码：

```
ALTER TABLE dbo.Orders add orderdate AS YEAR(orderdate);
GO
CREATE INDEX idx_eid_oy_cid1_qty ON dbo.Orders(empid, orderdate, custid) INCLUDE(qty);
CREATE INDEX idx_oy_cid1_qty ON dbo.Orders(orderdate, custid) INCLUDE(qty);
```

运行查询，你将得到图 4-21 所示的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_355_0.png)

图 4-21 添加索引后使用 `GROUPING SETS` 的查询计划。

支持索引按顺序扫描的，因此这次不需要进行排序操作。

# CUBE 和 ROLLUP 子句

`CUBE` 和 `ROLLUP` 子句仅仅是 `GROUPING SETS` 子句的简写。当你需要定义大量的分组集（你允许多达 4,096 个）时，如果能实际列出所有项就太好了。

从 `CUBE` 子句开始，假设你有一组表达式，并想从中定义所有可能的分组集。在数学中，这被称为集合的幂集（power set），即由原始集合元素形成的所有子集的集合。对于一个基数为 N 的集合，幂集的基数是 2^N。例如，对于一个包含 10 个元素的集合，你将得到包含 1,024 个子集的幂集，包括原始集合和空集。这基本上就是 `CUBE` 的作用。它提供一组表达式作为输入，你将得到一个等效的包含由输入表达式组成的所有分组集的 `GROUPING SETS` 子句。作为一个简单的示例，这里有一个带有两个输入表达式的 `CUBE` 子句的查询：

```
SELECT empid, SUM(qty) AS qty
FROM dbo.Orders
GROUP BY CUBE(custid, empid);
```

该查询等同于以下查询，后者使用了包含所有可能分组集的 `GROUPING SETS` 子句：



SELECT `custid`, `empid`, SUM(`qty`) AS `qty`
FROM `dbo.Orders`
GROUP BY GROUPING SETS
(
  (`custid`, `empid`),
  (`custid`),
  (`empid`),
  ()
);

对于 CUBE 子句的两个输入元素，幂集包含四个分组集。

至于 ROLLUP 子句，它也是一种简写，但它假设输入形成类似于时间、位置等的层次结构。你只会获得由表达式的前导组合形成的分组。考虑以下查询作为示例：

```sql
SELECT
  YEAR(`orderdate`) AS `orderyear`,
  MONTH(`orderdate`) AS `ordermonth`,
  DAY(`orderdate`) AS `orderday`,
  SUM(`qty`) AS `qty`
FROM `dbo.Orders`
GROUP BY
  ROLLUP(YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`));
```

对于 N 个元素，有 N + 1 个组合（包括空集）。前面的查询有一个带有三个输入的 ROLLUP 子句，因此它等同于以下定义了四个集合的 GROUPING SETS 子句查询：

```sql
SELECT
  YEAR(`orderdate`) AS `orderyear`,
  MONTH(`orderdate`) AS `ordermonth`,
  DAY(`orderdate`) AS `orderday`,
  SUM(`qty`) AS `qty`
FROM `dbo.Orders`
GROUP BY
  GROUPING SETS
  (
    (YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`)),
    (YEAR(`orderdate`), MONTH(`orderdate`)),
    (YEAR(`orderdate`)),
    ()
  );
```

ROLLUP 子句的有趣之处在于它如何处理层次结构。GROUPING SETS 的特性之一是可以定义任何分组。CUBE 的特性之一是它可以生成所有可能的组合。ROLLUP 的特性之一是根据层次结构生成组合。GROUPING SETS 子句的有趣特性在于它允许在单个查询中定义多个集合。这是数据报表的一个强大工具。

| bit value | 16 | 8 | 4 | 2 | 1 |
|---|---|---|---|---|---|
| grp_id | `custid` | `empid` | `orderyear` | `ordermonth` | `orderday` | `qty` |
| 25 | NULL | NULL | 2014 | 4 | NULL | 15 |
| 27 | NULL | NULL | 2014 | NULL | NULL | 45 |
| 31 | NULL | NULL | 2014 | NULL | NULL | 205 |
| 8 | A | NULL | 2012 | 8 | 2 | 10 |

例如，取返回值为 25 的那行。该行与分组集 (YEAR(`orderdate`), MONTH(`orderdate`)) 关联。对应的位是值为 4 和 2 的位，这些是未设置的位。其余元素——`custid`、`empid` 和 DAY(`orderdate`)的位是已设置的。它们位位 16、8 和 1 的位。将这些位的值相加，得到 25。

你通过按特定顺序将元素作为函数的输入，来决定哪个位代表哪个分组元素。因此，当用户请求某个分组集时，你将能够计算出唯一标识该分组的整数位图值。

在持久化聚合数据的查询中，我们包含了整数位图的计算（将结果列命名为 `grp_id`），以唯一标识每个结果关联的分组集。此外，你可以在表上创建一个以 `grp_id` 列为键的聚簇索引，以支持高效检索与单个请求分组相关的聚合数据。

以下代码用于在名为 `MyGroupingSets` 的表中持久化最后一个查询的聚合数据，并创建上述的辅助索引：

```sql
USE `tempdb`;
IF OBJECT_ID('dbo.MyGroupingSets', 'N''U') IS NOT NULL DROP TABLE `dbo.MyGroupingSets`;
GO

SELECT
    GROUPING_ID(
    `custid`,
    `empid`,
    YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`) ) AS `grp_id`,
    `custid`,
    `empid`,
    YEAR(`orderdate`) AS `orderyear`,
    MONTH(`orderdate`) AS `ordermonth`,
    DAY(`orderdate`) AS `orderday`,
    SUM(`qty`) AS `qty`
INTO `dbo.MyGroupingSets`
FROM `dbo.Orders`
GROUP BY
  CUBE(`custid`, `empid`),
  ROLLUP(YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`));
```

```sql
CREATE UNIQUE CLUSTERED INDEX `idx_cl_groupingsets`
ON `dbo.MyGroupingSets`(`grp_id`, `custid`, `empid`, `orderyear`, `ordermonth`, `orderday`);
```

假设用户请求了与分组集 ( `custid`, YEAR(`orderdate`), MONTH(`orderdate`)) 关联的聚合数据。其他分组元素 (`empid` 和 DAY(`orderdate`)) 的位值分别为 8 和 1。因此，你通过过滤 `grp_id` 9 来查询表，如下所示：

```sql
SELECT *
FROM `dbo.MyGroupingSets`
WHERE `grp_id` = 9;
```

由于表上的聚簇索引以 `grp_id` 列为引导键，将产生一个在索引内执行查找（seek）的高效计划，如图 23 所示。

如果你的数据源非常大，且聚合数据的完整处理需要很长时间，你可能想避免每晚都进行完整处理。你可能希望运行一次完整处理，并且每晚运行增量更新过程。当然，这假设聚合指标是可累加的。

![](img/bdc38aa36f6e2987d913ee5381474711_360_0.png)

Clustered Index Seek (Clustered [`MyGroupingSets`].(`id_c1_grouping_se_` : 100 %

```sql
SELECT
Cost: 0 %
```

```sql
Seek Predicates
Seek Key[1]: Prefix [`tempdb`].[`dbo`].
[`MyGroupingSets`].`grp_id`= Scalar Operator
(CONVERT(int,IMPLICIT(int),@1))
```

**图 4-23** 返回单个分组的查询计划。

在夜间处理过程中，假设今天是 2014 年 4 月 19 日。持久化的聚合数据保留到 18 日（包含 18 日）。以下是代表 19 日添加的新订单的代码：

```sql
INSERT INTO `dbo.Orders`
(`orderid`, `orderdate`, `empid`, `custid`, `qty`)
VALUES
(5001, '20140419', 1, 'A', 10),
(5002, '20140419', 1, 'B', 30),
(5003, '20140419', 2, 'A', 20),
(5004, '20140419', 2, 'B', 5),
(5005, '20140419', 3, 'A', 15);
```

在夜间处理过程中，你希望将最后一天的行与现有行合并。如果键已存在，则想要更新该行；如果键不存在，则想要插入新行。为了实现这一点，你提供了一个名为 `LastDay` 的 CTE，并将其作为 MERGE 语句的源。MERGE 语句将使用 EXISTS 谓词配合 INTERSECT 运算符来检查源键是否匹配目标键。不需要为正确处理添加任何特殊逻辑。当 EXISTS 谓词返回假时，MERGE 语句将通过插入新行来更新。以下是此类 MERGE 语句的实现：

### 第 4 章 分组、行转置与窗口

```sql
WITH `LastDay` AS
(
  SELECT
      GROUPING_ID(`custid`, `empid`, YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`)) AS `grp_id`,
      `custid`,
      `empid`,
      YEAR(`orderdate`) AS `orderyear`,
      MONTH(`orderdate`) AS `ordermonth`,
      DAY(`orderdate`) AS `orderday`,
      SUM(`qty`) AS `qty`
  FROM `dbo.orders`
  WHERE `orderdate` = '20140419'
  GROUP BY
      CUBE(`custid`, `empid`),
      ROLLUP(YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`))
)
MERGE INTO `dbo.GroupingSets` AS `TGT`
USING `LastDay` AS `SRC`
ON EXISTS (
    SELECT `SRC`.`grp_id`, `SRC`.`orderyear`, `SRC`.`ordermonth`, `SRC`.`orderday`, `SRC`.`custid`, `SRC`.`empid`
    INTERSECT
    SELECT `TGT`.`grp_id`, `TGT`.`orderyear`, `TGT`.`ordermonth`, `TGT`.`orderday`, `TGT`.`custid`, `TGT`.`empid`
)
WHEN MATCHED THEN
  UPDATE SET `TGT`.`qty` += `SRC`.`qty`
WHEN NOT MATCHED THEN
  INSERT (`grp_id`, `custid`, `empid`, `orderyear`, `ordermonth`, `orderday`)
  VALUES (`SRC`.`grp_id`, `SRC`.`custid`, `SRC`.`empid`, `SRC`.`orderyear`, `SRC`.`ordermonth`, `SRC`.`orderday`);
```

# 排序

记住，如果在查询中没有指定 ORDER BY 子句，对显示顺序没有任何保证。即使行按顺序返回，也不意味着你有任何保证。例如，假设你有一个带有 ROLLUP 子句计算每日、每月和总计的查询。优化器会根据元素的顺序优化 ROLLUP 子句。因此，即使没有 ORDER BY 子句，也会按时间层级获取行。但这并不是你想要的。唯一真正保证输出的方法是显式的 ORDER BY 子句。

如果没有多个聚合层只有天，你将按 `YEAR(orderdate)`, MONTH(`orderdate`) 排序。由于你有每日、每月和总计，基于时间层级的排序更为复杂。可以帮你解决此问题的工具是 GROUPING 函数。它与 GROUPING_ID 函数类似，但仅支持一个输入。当元素是详细元素（分组的一部分）时，GROUPING 函数返回 0，当它是聚合（不是分组的一部分）时返回 1。因此，为了将详细年份放在总计行之前，你需要在 ORDER BY 子句中将 GROUPING(YEAR(`orderdate`)) 放在 YEAR(`orderdate`) 之前。月份和天也是如此。以下查询演示了如何应用此逻辑，使详细数据位于每个级别的聚合之前（月内的天、月总量、年内的月份、年、总计）：

```sql
SELECT
    YEAR(`orderdate`) AS `orderyear`,
    MONTH(`orderdate`) AS `ordermonth`,
    DAY(`orderdate`) AS `orderday`,
    SUM(`qty`) AS `totalqty`
FROM `dbo.Orders`
GROUP BY
    YEAR(`orderdate`), MONTH(`orderdate`), DAY(`orderdate`)
ORDER BY
    GROUPING(YEAR(`orderdate`)), YEAR(`orderdate`),
    GROUPING(MONTH(`orderdate`)), MONTH(`orderdate`),
    GROUPING(DAY(`orderdate`)), DAY(`orderdate`);
```

此查询生成输出：

| `orderyear` | `ordermonth` | `orderday` | `totalqty` |
|---|---|---|---|
| 2012 | 4 | 18 | 22 |
| 2012 | 4 | NULL | NULL |
| 2012 | 8 | 2 | 10 |
| 2012 | 8 | NULL | 10 |
| 2012 | 9 | 7 | 30 |
| 2012 | 9 | NULL | 30 |
| 2012 | 12 | 24 | 32 |
| 2012 | 12 | NULL | 32 |
| 2012 | NULL | NULL | 94 |
| 2013 | 1 | 9 | 40 |
| 2013 | 1 | 18 | 14 |
| 2013 | 1 | NULL | 54 |
| 2013 | 2 | 12 | 12 |
| 2013 | 2 | NULL | 12 |
| 2013 | NULL | NULL | 66 |
| 2014 | 2 | 12 | 10 |
| 2014 | 2 | 16 | 20 |
| 2014 | 2 | NULL | 30 |
| 2014 | 4 | 18 | 15 |
| 2014 | 4 | 19 | 80 |
| 2014 | 4 | NULL | 95 |

## 结论

本章涵盖了大量数据分析方面的内容。它从深层的窗口函数开始，描述了不同类型，以及处理“间隙与孤岛”（gaps and islands）问题的实际用途。接着涵盖了处理透视（pivoting）和逆透视（unpivoting）的技术，展示了基于标准方法的解决方案以及基于专用 PIVOT 和 UNPIVOT 操作符的解决方案。随后，章节介绍了处理自定义聚合计算（如字符串拼接和乘积）的不同方法。最后，本章介绍了了可以在同一查询中为多个分组集计算聚合的若干功能。

# 第 5 章

## TOP 和 OFFSET-FETCH

SQL 中的经典过滤器（如 ON、WHERE 和 HAVING）是基于谓词的。TOP 和 OFFSET-FETCH 是基于不同概念的过滤器：你指定顺序以及根据该顺序过滤多少行。许多过滤任务是基于顺序和所需的行数定义的。在 T-SQL 中拥有这种语言支持，允许你以类似于你思考任务的方式来表述请求，无疑是一件好事。

本章从过滤器的逻辑设计方面开始。然后使用分页场景来演示它们的优化。本章还涵盖了在修改语句中使用 TOP 的情况。最后，章节演示了如何使用 TOP 和 OFFSET-FETCH 解决每组 N 条和中位数等实际问题。

# TOP 和 OFFSET-FETCH 过滤器

你使用 TOP 和 OFFSET-FETCH 过滤器以直观的方式实现查询中的过滤需求。TOP 过滤器是 T-SQL 的专用功能，而 OFFSET-FETCH 过滤器是一个标准功能。T-SQL 从 Microsoft SQL Server 2012 开始支持 OFFSET-FETCH。截至 SQL Server 2014，T-SQL 中 OFFSET-FETCH 的实现仍然缺少几个标准元素——有趣的是，这些元素在 TOP 中是可用的。在目前的实现中，每一者都拥有对方不支持的能力。

我将先开始描述 TOP 的逻辑设计方面，然后介绍 OFFSET-FETCH。

## TOP 过滤器

TOP 过滤器是 T-SQL 中常用的构造结构。它的流行可能归功于其设计与许多过滤需求的表达非常契合——例如，“返回最近的三个订单”。在这个请求中，过滤的顺序是基于 `orderdate` 降序，要过滤的行数是 3。

你在 SELECT 列表中指定 TOP 选项，并提供如 `BIGINT` 的输入值来指示你想过滤多少行。你在经典的 `ORDER BY` 子句中提供排序规范。例如，你使用以下查询获取最近的三个订单。

```sql
USE `TSQLV`;

SELECT TOP (3) `orderid`, `orderdate`, `custid`, `empid`
FROM `Sales.Orders`
ORDER BY `orderdate` DESC;
```

我从此查询中得到了以下输出：

| `orderid` | `orderdate` | `custid` | `empid` |
|---|---|---|---|
| 11077 | 2015-05-06 | 65 | 1 |
| 11076 | 2015-05-06 | 9 | 4 |
| 11075 | 2015-05-06 | 68 | 8 |

与其指定你想要过滤的行数，不如可以使用 TOP 来指定百分比（查询结果总行数）。你通过提供一个 0 到 100 之间的值（类型为 `FLOAT`）并添加 `PERCENT` 关键字来实现这一点。例如，在以下查询中，你请求过滤百分之一的行：

```sql
SELECT TOP (1) PERCENT `orderid`, `orderdate`, `custid`, `empid`
FROM `Sales.Orders`
ORDER BY `orderdate` DESC;
```

SQL Server 会根据输入的百分比对计算出的行数向上取整。例如，对 Orders 表中的 830 行应用 1% 的结果是 8.3。将此数字向上取整得到 9。这是我为该查询得到的输出：

| `orderid` | `orderdate` | `custid` | `empid` |
|---|---|---|---|
| 11074 | 2015-05-06 | 73 | 7 |
| 11075 | 2015-05-06 | 68 | 8 |
| 11076 | 2015-05-06 | 9 | 4 |
| 11077 | 2015-05-06 | 65 | 1 |
| 11070 | 2015-05-05 | 44 | 2 |
| 11071 | 2015-05-05 | 46 | 1 |
| 11072 | 2015-05-05 | 20 | 2 |
| 11073 | 2015-05-05 | 58 | 2 |
| 11067 | 2015-05-04 | 17 | 1 |



要将输入的百分比转换为行数，SQL Server 必须确定查询结果中的行数，这通常需要额外工作。

有趣的是，`TOP` 过滤器的排序规范是可选的。例如，考虑以下查询：

```sql
SELECT TOP (3) orderid, orderdate, custid, empid
FROM Sales.Orders;
```

我从此查询得到以下输出：

```
orderid  orderdate custid empid
---------- --------- -----
10248   2013-07-04 85      5
10249   2013-07-05 79      6
10250   2013-07-08 34      4
```

返回哪三行是非确定的。这意味着如果你再次运行查询，在底层数据不变化的情况下，理论上可能会得到不同的三行。在实践中，行的选择取决于优化选择、存储引擎选择、数据布局等物理条件。如果你实际上运行多次查询，只要这些物理条件不改变，你可能会保持相同的结果。但理解关系模型中的“物理数据独立性”原则以及在逻辑层面你没有可重复的结果至关重要。如果没有排序规范，查询是非确定的。保证结果的确定性的第二种方法是使排序规范唯一。例如，在我们的示例中，你可以使用 `orderid DESC` 作为决胜因素。这意味着，在订单日期相同的情况下，订单 ID 较大的行优于 ID 较小的行。这是应用决胜因素后的查询：

```sql
SELECT TOP (3) orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC, orderid DESC;
```

此查询生成了如下：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 11077 | 2015-05-06 | 65 | 1 |
| 11076 | 2015-05-06 | 9 | 4 |
| 11075 | 2015-05-06 | 68 | 8 |

使用唯一排序使得行选择和显示顺序都是确定的。只要底层数据不变化，结果集以及行的显示顺序都可以保证是确定的。

如果你需要过滤特定数量的行但真的不在乎顺序，指定 `ORDER BY (SELECT NULL)` 可能是一个好主意，如下：

```sql
SELECT TOP (3) orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY (SELECT NULL);
```

通过这种方式，你让每个人知道你的任意顺序是有意的，这有助于避免困惑和怀疑。

提醒一下我在第一章“逻辑查询处理”中关于 `TOP` 和 `OFFSET-FETCH` 过滤器的解释：只有当查询包含 `ORDER BY` 子句时，才能保证显示顺序。例如，在以下查询中，排序是不保证的：

```sql
SELECT orderid, orderdate, custid, empid
FROM ( SELECT TOP (3) orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC, orderid DESC ) AS D;
```

# 快速小题

以下查询在寻找什么？（在看答案之前尝试一下）。

```sql
SELECT TOP (3) WITH TIES orderdate
```

答案：此查询返回每个客户的最近订单。

保证确定性结果的第二种方法是通过添加决胜因素使排序规范唯一。例如，在我们的示例中，你可以使用 `orderid DESC` 作为决胜因素。这意味着，在订单日期相同的情况下，订单 ID 较大的行优于 ID 较小的行。这是应用决胜因素后的查询：

```sql
SELECT TOP (3) orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC, orderid DESC;
```

此查询生成了：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 11077 | 2015-05-06 | 65 | 1 |
| 11076 | 2015-05-06 | 9 | 4 |
| 11075 | 2015-05-06 | 68 | 8 |

为了提供呈现顺序保证，你必须在外部查询中指定 `ORDER BY` 子句，例如：

```sql
SELECT orderid, orderdate, custid, empid
FROM (SELECT TOP (3) orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC, orderid DESC) AS D
ORDER BY orderdate DESC, orderid DESC;
```

## OFFSET-FETCH 过滤器

`OFFSET-FETCH` 过滤器是一种标准功能，设计上类似于 `TOP`，但多了一个元素。你可以在指定要过滤的行数之前，指定要跳过多少行。

正如你所猜到的，此功能在实现分页解决方案时非常有用——即当完整结果过长无法在一个屏幕或网页上显示时，根据请求向用户一次返回一个块的结果。

`OFFSET-FETCH` 过滤器要求存在 `ORDER BY` 子句，并且紧跟在其后指定。你首先通过 `OFFSET` 子句指定要跳过的行数，然后通过 `FETCH` 子句指定要过滤的行数。例如，根据指定的顺序，以下查询跳过了前 50 行，并过滤了接下来的 25 行：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC, orderid DESC
OFFSET 50 ROWS FETCH NEXT 25 ROWS ONLY;
```

换句话说，该查询过滤了第 51 到 75 行。在分页术语中，假设页大小为 25 行，此查询返回了第三页。

为了允许自然的声明式语言，如果你喜欢，可以使用关键字 `FIRST` 代替 `NEXT`，尽管它们的含义是相同的。如果不跳过任何行，使用 `FIRST` 可能会更直观。即使你不想跳过任何行，T-SQL 仍然强制要求指定 `OFFSET` 子句（使用 `0 ROWS`）以避免解析歧义。同样，与其使用关键字的复数形式 `ROWS`，你可以在 `OFFSET` 和 `FETCH` 子句中使用单数形式 `ROW`。如果你只需要跳过或过滤一行，这样会更自然。

如果你对 `ONLY` 关键字的用途好奇，它意味着不包含并列。标准 SQL 定义了替代方案 `WITH TIES`；然而，T-SQL 不支持它。同样，标准 SQL 定义了 `PERCENT` 选项，但 T-SQL 目前还不支持。这两个缺失的选项在 `TOP` 过滤器中可用。

如所述，`OFFSET-FETCH` 过滤器需要 `ORDER BY` 子句。如果你想使用任意顺序且不带 `ORDER BY` 子句的 `TOP`，你可以使用 `ORDER BY (SELECT NULL)` 的技巧，例如：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY (SELECT NULL)
OFFSET 0 ROWS FETCH NEXT 3 ROWS ONLY;
```

`FETCH` 子句是可选的。如果你想跳过特定数量的行但不限制返回的行数，只需不使用 `FETCH` 子句即可。例如，以下查询跳过了 50 行，但不限制返回行数：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC, orderid DESC
OFFSET 50 ROWS;
```

关于呈现顺序，其行为与 `TOP` 过滤器相同；即 `OFFSET-FETCH` 只有在最外层查询具有 `ORDER BY` 子句时，才能保证呈现顺序。

## 通过分页演示过滤器的优化

到目前位置，我描述了 `TOP` 和 `OFFSET-FETCH` 过滤器的逻辑设计方面。在本部分，我将涵盖优化方面。我将通过查看不同的分页解决方案来实现。我将描述两种使用 `TOP` 过滤器的分页解决方案、一个使用 `OFFSET-FETCH` 过滤器的解决方案以及使用 `ROW_NUMBER` 函数的解决方案。

在所有情况下，无论你的分页解决方案使用何种过滤选项，排序元素的索引对于良好的性能都是至关重要的。即使索引不是覆盖索引，你也能获得性能。好奇的是，有时当索引没有覆盖时，性能反而更好。我将在具体的实现中提供细节。

我将在示例中使用来自 `PerformanceV3` 数据库的 `Orders` 表。假设你需要实现一个分页解决方案，根据 `orderid` 键，一次返回一页数据。该表定义了一个名为 `PK_Orders` 的非聚集索引，以 `orderid` 为键。此索引对于我将演示的分页查询来说不是覆盖索引。

## TOP 的优化

你可以使用几种策略通过 `TOP` 实现分页解决方案。一种是基于锚点的策略，另一种是 `TOP` 之上的 `TOP`（嵌套查询）。

基于锚点的策略允许用户逐步访问页面。你定义了一个存储过程，当给定上一页最后一行的排序键时，它返回下一页。以下是此类存储过程的实现：

```sql
USE PerformanceV3;
IF OBJECT_ID('dbo.GetPage', 'P') IS NOT NULL DROP PROC dbo.GetPage;
GO
CREATE PROC dbo.GetPage
    @orderid AS INT = 0, -- anchor sort key
    @pagesize AS BIGINT = 25
AS
SELECT TOP (@pagesize) orderid, orderdate, custid, empid
FROM dbo.Orders
WHERE orderid > @orderid
ORDER BY orderid;
GO
```

在这里我假设只支持 `orderid`。当然，你可以使用 `CHECK` 约束来实现完整性规则。使用以下代码请求第一页订单：

```sql
EXEC dbo.GetPage @orderid = 0, @pagesize = 25;
```

我得到了以下输出（但可能因为随机性而不同）：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 1 | 2023-01-01 | 101 | 500 |
| 2 | 2023-01-02 | 102 | 501 |
| 3 | 2023-01-03 | 103 | 502 |
| 4 | 2023-01-04 | 104 | 503 |
| 5 | 2023-01-05 | 105 | 504 |
| 6 | 2023-01-06 | 106 | 505 |
| 7 | 2023-01-07 | 107 | 506 |
| 8 | 2023-01-08 | 108 | 507 |
| 9 | 2023-01-09 | 109 | 507 |
| 10 | 2023-01-10 | 110 | 509 |
| 11 | 2023-01-11 | 111 | 510 |
| 12 | 2023-01-12 | 112 | 511 |
| 13 | 2023-01-13 | 113 | 512 |
| 14 | 2023-01-14 | 114 | 513 |
| 15 | 2023-01-15 | 115 | 514 |
| 16 | 2023-01-16 | 116 | 515 |
| 17 | 2023-01-17 | 117 | 516 |
| 18 | 2023-01-18 | 118 | 517 |
| 19 | 2023-01-19 | 119 | 518 |
| 20 | 2023-01-20 | 120 | 519 |
| 21 | 2023-01-21 | 121 | 520 |
| 22 | 2023-01-22 | 122 | 521 |
| 23 | 2023-01-23 | 123 | 522 |
| 24 | 2023-01-24 | 124 | 523 |
| 25 | 2023-01-25 | 125 | 524 |

要请求第二页，将最后一个 `orderid` 作为锚点键：

```sql
EXEC dbo.GetPage @orderid = 25, @pagesize = 25;
```

我得到了如下输出：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 26 | 2023-01-26 | 126 | 525 |
| 27 | 2023-01-27 | 127 | 526 |
| 28 | 2023-01-28 | 128 | 527 |
| 29 | 2023-01-29 | 129 | 528 |
| 30 | 2023-01-30 | 130 | 529 |
| 31 | 2023-01-31 | 131 | 530 |
| 32 | 2023-02-01 | 132 | 531 |
| 33 | 2023-02-02 | 133 | 532 |
| 34 | 2023-02-03 | 134 | 533 |
| 35 | 2023-02-04 | 135 | 534 |
| 36 | 2023-02-05 | 136 | 535 |
| 37 | 2023-02-06 | 137 | 536 |
| 38 | 2023-02-07 | 138 | 537 |
| 39 | 2023-02-08 | 139 | 538 |
| 40 | 2023-02-09 | 140 | 539 |
| 41 | 2023-02-10 | 141 | 540 |
| 42 | 2023-02-11 | 142 | 541 |
| 43 | 2023-02-12 | 143 | 542 |
| 44 | 2023-02-13 | 144 | 543 |
| 45 | 2023-02-14 | 145 | 544 |
| 46 | 2023-02-15 | 146 | 545 |
| 47 | 2023-02-16 | 147 | 546 |
| 48 | 2023-02-17 | 148 | 547 |
| 49 | 2023-02-18 | 149 | 548 |
| 50 | 2023-02-19 | 150 | 549 |

要请求第三页，将最后一个 `orderid` 作为锚点键：

```sql
EXEC dbo.GetPage @orderid = 50, @pagesize = 25;
```

我得到了以下输出：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 51 | 2023-02-20 | 151 | 550 |
| 52 | 2023-02-21 | 152 | 551 |
| 53 | 2023-02-22 | 153 | 552 |
| 54 | 2023-02-23 | 154 | 553 |
| 55 | 2023-02-24 | 155 | 554 |
| 56 | 2023-02-25 | 156 | 555 |
| 57 | 2023-02-26 | 157 | 556 |
| 58 | 2023-02-27 | 158 | 557 |
| 59 | 2023-02-28 | 159 | 558 |
| 60 | 2023-03-01 | 160 | 559 |
| 61 | 2023-03-02 | 161 | 560 |
| 62 | 2023-03-03 | 162 | 561 |
| 63 | 2023-03-04 | 163 | 562 |
| 64 | 2023-03-05 | 164 | 563 |
| 65 | 2023-03-06 | 165 | 564 |
| 66 | 2023-03-07 | 166 | 565 |
| 67 | 2023-03-08 | 167 | 566 |
| 68 | 2023-03-09 | 168 | 567 |
| 69 | 2023-03-10 | 169 | 568 |
| 70 | 2023-03-11 | 170 | 569 |
| 71 | 2023-03-12 | 171 | 570 |
| 72 | 2023-03-13 | 172 | 571 |
| 73 | 2023-03-14 | 173 | 572 |
| 74 | 2023-03-15 | 174 | 573 |
| 75 | 2023-03-16 | 175 | 574 |

不仅是因为 `Index Seek` 算子中的范围扫描由于 `TOP` 的行目标而变短，查询优化器还需要根据该行目标调整受影响算子的代价。优化的这一方面在 Paul White 的一个非常优秀的文章中进行了详细描述：“The Optimizer: Row Goals In Depth”。你可以在此处找到这篇文章：http://sqlblog.com/blogs/paul_white/archive/2010/08/18/inside-the-optimizer-row-goals-in-depth.aspx

执行查询计划时涉及的 I/O 成本由以下部分组成：

- 寻到叶节点索引：3 次读取（索引有三层）
- 25 行的范围扫描：0–1 次读取（每页有数百行）
- 用于优化查找的嵌套循环预取：9 次读取（通过跟踪标志 8744 禁用预取来测量）
- 25 次键查找：75 次读取



总而言，该查询的性能报告了 87 次逻辑读取。这并不差。情况会变得更好或更糟吗？两方面都是。你可以通过创建一个包含索引（covering index）来获得更好的性能。这将消除预取和键查找的代价，导致总共只有 3–4 次逻辑读取。如果你没有以排序列作为前导键的良好索引——即使是非包含索引——性能可能会变差。这会导致一个对数据进行全扫描的计划，此外，这是一个非常昂贵的计划，尤其是考虑到你为用户每个页面的请求都要为此付出代价。

在使用单个键时，识别符合范围的 `WHERE` 谓词非常简单：`orderid > @orderid`。如果有多个排序键，情况就会变得有点复杂。例如，假设排序向量为 `(orderdate, orderid)`，你将锚点排序键 `@orderdate` 和 `@orderid` 作为 `GetPage` 过程的输入。标准 SQL 有一种以调用构造函数（也称为向量表达式）形式呈现的优雅解决方案。这一功能已经在 T-SQL 中实现，你可以这样表述 `WHERE` 谓词：`(orderdate, orderid) > (@orderdate, @orderid)`。这还允许通过在排序键上使用支持索引来实现优化，类似于对单个键的优化。T-SQL 不支持这种结构。

在表述谓词时，你有两种选择。其中一种（称之为第一谓词形式）如下：`orderid >= @orderid AND (orderdate > @orderdate)`。另一种（称之为第二谓词形式）看起来像：`(orderdate = @orderdate AND orderid > @orderid) OR orderdate > @orderdate`。两者在逻辑上是等价的，但查询优化器的处理方式不同。在我们的情况下，表上定义了一个包含索引 `idx_od_od_i_cid_eid`，其键列表为 `(orderdate, orderid)`，包含列表为 `(custid, empid)`。

以下是使用第一谓词形式的存储过程实现：

```sql
IF OBJECT_ID(N'dbo.GetPage', N'P') IS NOT NULL DROP PROC dbo.GetPage;
GO
CREATE PROC dbo.GetPage
    @orderdate AS DATE = '0010101', -- 锚点排序键 1 (orderdate)
    @orderid AS INT = 0, -- 锚点排序键 2 (orderid)
    @pagesize AS BIGINT = 25
AS
SELECT TOP (@pagesize) orderid, orderdate, custid, empid
FROM dbo.Orders
WHERE orderdate >= @orderdate
AND (orderdate > @orderdate OR orderid > @orderid)
ORDER BY orderdate, orderid;
```

运行以下代码获取第一页：

```sql
EXEC dbo.GetPage @pagesize = 25;
```

我从该执行中得到了以下输出：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 310 | 2010-12-03 | 0000014672 | 218 |
| 330 | 2010-12-03 | 0000009594 | 10 |
| 90 | 2010-12-04 | 0000012937 | 231 |
| 300 | 2010-12-07 | 0000019961 | 282 |
| 410 | 2010-12-07 | 0000001585 | 342 |

运行以下代码获取第二页：

```sql
EXEC dbo.GetPage @orderdate = '20101207', @orderid = 410, @pagesize = 25;
```

我从该执行中得到了以下输出：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 1190 | 2010-12-07 | 0000004678 | 465 |
| 1270 | 2010-12-07 | 0000001507 | 376 |
| 1760 | 2010-12-07 | 0000009532 | 104 |
| 2470 | 2010-12-09 | 0000008664 | 205 |
| 2830 | 2010-12-09 | 0000010497 | 221 |

运行以下代码获取第三页：

```sql
EXEC dbo.GetPage @orderdate = '20101209', @orderid = 2830, @pagesize = 25;
```

我从该执行中得到了以下输出：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 3120 | 2010-12-09 | 000015659 | 381 |
| 3340 | 2010-12-09 | 000008708 | 272 |
| 3620 | 2010-12-09 | 000009367 | 312 |
| ... | ... | ... | ... |
| 2730 | 2010-12-10 | 000015630 | 317 |
| 3490 | 2010-12-10 | 000002887 | 306 |

作为优化，图 5-2 显示了我使用第一谓词形式时得到的计划。

![img/bdc38aa6f62987d913ee5381741_375_0.png](img/bdc38aa6f62987d913ee5381741_375_0.png)
![img/bdc38aa6f62987d913ee5381741_375_1.png](img/bdc38aa6f62987d913ee5381741_375_1.png)
![img/bdc38aa6f62987d913ee5381741_375_2.png](img/bdc38aa6f62987d913ee5381741_375_2.png)

**图 5-2 多个排序键、第一谓词形式的 TOP 计划。**

注意谓词的 `Start` 属性仅基于谓词 `orderdate >= @orderdate`。剩余谓词是 `orderdate >= @orderdate OR orderid > @orderdate`。这种优化可能会导致不必要的扫描包含第一个符合日期的范围的部分——也就是说，即使 `orderdate = @orderdate AND orderid <= @orderdate` 的行也会被扫描。执行的不必要的页面读取次数取决于前导排序键——`orderdate`，在我们情况下，密度越大，越可能发生不必要的工作。在我们的情况下，`orderdate` 列的密度很低 (~1/50)，以至于代价可以忽略不计。当使用排序键时，你可以使用第二谓词的形式获得明显的改进。以下是第二谓词形式的存储过程实现：

```sql
IF OBJECT_ID('dbo.GetPage', 'P') IS NOT NULL DROP PROC dbo.GetPage;
GO
CREATE PROC dbo.GetPage
    @orderdate DATE = '0010101', -- 锚点排序键 1 (orderdate)
    @orderid AS INT = 0, -- 锚点排序键 2 (orderid)
    @pagesize AS BIGINT = 25
AS
SELECT TOP (@pagesize) orderid, orderdate, custid, empid
FROM dbo.Orders
WHERE (orderdate = @orderdate AND orderid > @orderid)
OR orderdate > @orderdate
ORDER BY orderdate, orderid;
GO
```

运行代码获取第三页：

```sql
EXEC dbo.GetPage @orderdate = '20101209', @orderid = 2830, @pagesize = 25;
```

使用第二形式实现的查询计划如图 5-3 所示。

![img/bdc38aa6f62987d913ee5381741_376_0.png](img/bdc38aa6f62987d913ee5381741_376_0.png)
![img/bdc38aa6f62987d913ee5381741_376_1.png](img/bdc38aa6f62987d913ee5381741_376_1.png)
![img/bdc38aa6f62987d913ee5381741_376_2.png](img/bdc38aa6f62987d913ee5381741_376_2.png)

**图 5-3 多个锚点排序键、第二谓词形式的 TOP 计划。**

注意没有剩余谓词，只有查找谓词。奇怪的是，有两个查找谓词。记住，通常情况下，`Index Seek` 算子扫描的范围从 `Prefix` 的第一个匹配开始，到 `Prefix` 的最后一个匹配结束。在我们情况下，一个谓词（在计划中标记为 `[1] Seek Keys...`）从 `orderdate = @orderdate AND @orderid` 开始，以 `orderdate = @orderdate` 结束。另一个谓词（在计划中标记为 `[2] Seek Keys...`）从 `orderdate = @orderdate` 开始且没有显式的结束。查询执行期间有趣的是，如果第一个查找找到了 `Top Expression` 行，执行器会在到达第二个查找之前短路。但如果第一个查找是不够，第二个将执行。使用 `TOP` 有另一种方法。你可以将其认为是 `TOP` 之上的 `TOP`，使用 `@pagenum` 和 `@pagesize` 作为 `GetPage` 过程的输入进行嵌套。这里没有锚点概念。使用一个带有 `TOP` 的查询根据所需顺序过滤 `@pagenum * @pagesize` 行。你基于该查询定义一个表表达式（调用 `D1`）。你使用第二个查询针对 `D1` 过滤 `@pagesize` 行，但使用反序。你基于第二个查询定义一个表表达式（称为 `D2`）。最后，对 `D2` 运行外部查询以对行按所需顺序进行排序。

```sql
IF OBJECT_ID(N'dbo.GetPage',N'P') IS NOT NULL DROP PROC dbo.GetPage;
GO
CREATE PROC dbo.GetPage
    @pagenum BIGINT = 1,
    @pagesize BIGINT = 25
AS

SELECT orderid, orderdate, custid, empid
FROM (SELECT TOP (@pagesize)
FROM (SELECT TOP (@pagenum) * FROM @pagesize)
FROM dbo.Orders
ORDER BY orderid) AS D1
ORDER BY orderid DESC) AS D2
ORDER BY orderid;
```

以下是连续调用该存储的过程，分别请求第一、第二和第三页：

```sql
EXEC dbo.GetPage @pagenum = 1, @pagesize = 25;
EXEC dbo.GetPage @pagenum = 2, @pagesize = 25;
EXEC dbo.GetPage @pagenum = 3, @pagesize = 25;
```

第三次调用的计划如图 5-4 所示。

![img/bdc38aa36f6e2987d913ee5381474711_377_0.png](img/bdc38aa36f6e2987d913ee5381474711_377_0.png)

**图 5-4 TOP 嵌套 TOP 的计划。**

该计划并不昂贵，但与基于锚点（anchor）概念的实现相比，有三个方面并非最优。首先，计划从索引的左侧开始扫描数据直到最后一条符合条件的行。这意味着工作的重复——重新扫描数据。对于用户请求的第一页，计划将扫描 `1 * @pagesize` 行；对于第二页，将扫描 `2 * @pagesize` 行；对于第 n 页，将扫描 `n * @pagesize` 行。注意，`Key Lookup`（键查找）算符被执行了 5 次，尽管实际上实际上只返回了 2 次查找。第三，计划中应用了两个 `Sort`（排序）算符：一个反转原始顺序以获取最后一部分行，另一个将其反转回原始顺序以便按这种方式呈现。对于第三页请求，该计划的执行执行了 241 次逻辑读取。页数越多，工作量就越大。

与锚点策略相比，这种方法的用处在于你不需要处理如何从最后一页请求中收集结果，而且用户不受限于在相邻页面之间进行导航。例如，用户可以从第 1 页开始请求第 5 页，依此类推。

## OFFSET-FETCH 的优化

`OFFSET-FETCH` 过滤器的优化与 `TOP` 类似。微软并没有通过创建一个全新的计划算符来重造轮子，而是决定增强现有的 `Top` 算符。记住，`Top` 算符有一个属性 `Top Expression`，它指示从右侧算符请求并传递给左侧算符的行数。用于处理 `OFFSET-FETCH` 的增强型 `Top` 算符有一个新属性 `OffsetExpression`，它指示从算符请求但不传递给左侧算符的行数。正如你可能猜到的，`OffsetExpression` 属性在 `Top Expression` 属性之前被处理。

为了向你展示 `OFFSET-FETCH` 过滤器的优化，我将在 `GetPage` 过程的实现中使用它：

```sql
IF OBJECT_ID(N'dbo.GetPage', N'P') IS NOT NULL DROP PROC dbo.GetPage;
GO
CREATE PROC dbo.GetPage
    @pagenum AS BIGINT = 1,
    @pagesize AS BIGINT = 25
AS
SELECT orderid, orderdate, custid, empid
FROM dbo.Orders
ORDER BY orderid
OFFSET (@pagenum - 1) * @pagesize ROWS NEXT @pagesize ROWS ONLY;
GO
```

如你所示，`OFFSET-FETCH` 提供了一个简单且灵活的解决方案，使用了 `@pagenum` 和 `@pagesize` 输入。使用以下代码请求前三页：

```sql
EXEC dbo.GetPage @pagenum = 1, @pagesize = 25;
EXEC dbo.GetPage @pagenum = 2, @pagesize = 25;
EXEC dbo.GetPage @pagenum = 3, @pagesize = 25;
```

> **注意**：记住，默认隔离级别为 Read Committed（已提交），存储过程调用之间的数据更改可能会影响你得到的结果，导致你在不同页面中获得同一行或跳过某些行。例如，假设在 T1 某点，你请求第 1 页。你获取了根据分页顺序位于第 1 到 25 的行。在你请求下一页之前，在 T2 某点，有人添加了一行新数据，其排序键使其成为第 20 行。在 T3 某点，你请求第 2 页。你获取了在 T1 中位于 25 到 49 的行，而不是第 50 行。这种行为可能会很尴尬。如果你希望整个页请求序列都与数据的相同状态交互，你需要从在快照隔离级别（snapshot isolation level）下运行的事务中提交所有请求。

存储第三次执行的计划如图 5-5 所示。

![img/bdc38aa36f6e2987d913ee5381474711_379_0.png](img/bdc38aa36f6e2987d913ee5381474711_379_0.png)

**图 5-5 OFFSET-FETCH 的计划。**

如你在计划所示，`Top` 算符从右侧算符请求 `OffsetExpression` 行（在我们的示例中为 50），并且不传递给左侧算符。`Top` 算符从右侧算符请求行（在我们的示例中为 25）并将其传递给左侧算符。`Key Lookup` 算符被执行了 5 次，尽管实际上只返回了 2 次查找。计划中应用了两个 `Sort`（排序）算符：一个反转原始顺序以获取最后一部分行，另一个将其反转回原始顺序以便按这种方式呈现。对于第三页请求，该计划的执行执行了 241 次逻辑读取。页数越多，工作量就越大。

## ROW_NUMBER 的优化

分页的另一种常用解决方案是使用 `ROW_NUMBER` 函数，根据所需的排序计算行号，并根据输入的 `@pagenum` 和 `@pagesize` 过滤出正确的行号范围。

以下是基于此策略的 `GetPage` 存储过程实现：

```sql
IF OBJECT_ID('dbo.GetPage') IS NOT NULL DROP PROC dbo.GetPage;
GO
CREATE PROC dbo.GetPage
    @pagenum BIGINT = 1,
    @pagesize BIGINT = 25
AS
WITH C AS (
    SELECT orderid, orderdate, custid, empid,
    ROW_NUMBER() OVER(ORDER BY orderid) AS rn
    FROM dbo.Orders
)
SELECT orderid, orderdate, custid, empid
FROM C
WHERE rn BETWEEN (@pagenum - 1) * @pagesize + 1 AND @pagenum * @pagesize
ORDER BY rn; -- if order by get sort in plan
```

运行以下代码请求前三页：

```sql
EXEC dbo.GetPage @pagenum = 1, @pagesize = 25;
EXEC dbo.GetPage @pagenum = 2, @pagesize = 25;
EXEC dbo.GetPage @pagenum = 3, @pagesize = 25;
```

该请求的列表计划如图 5-7 所示：

![img/bdc38aa36f6e2987d913ee5381474711_382_0.png](img/bdc38aa36f6e2987d913ee5381474711_382_0.png)

**图 5-7 ROW_NUMBER 的计划。**

有趣的是，该解决方案的优化与基于 `OFFSET-FETCH` 过滤的解决方案相似。你会发现同样的低效之处，包括不必要的查找。因此，成本几乎相同。对于第三页的请求，逻辑读取次数为 241。在请求 1000 页后运行该存储过程：

```sql
EXEC dbo.GetPage @pagenum = 1000, @pagesize = 25;
```



现在的逻辑读取次数为 76,644。你可以通过应用改进后的 `OFFSET-FETCH` 解决方案中使用的优化原则来避免不必要的查找，如下：

```sql
ALTER PROC dbo.GetPage
@pagenum AS BIGINT = 1
AS
WITH C AS (
  SELECT orderid, ROW_NUMBER() OVER(ORDER BY orderid) AS rn
  FROM dbo.Orders
),
K AS (
  SELECT orderid, rn
  FROM C
  WHERE rn BETWEEN (@pagenum - 1) * @pagesize + 1 AND @pagenum * @pagesize
)
SELECT O.orderid, O.orderdate, O.custid, O.empid
FROM dbo.Orders AS O
INNER JOIN K ON O.orderid = K.orderid
ORDER BY K.rn;
```

运行存储过程请求第三页：

```sql
EXEC dbo.GetPage @pagenum = 3, @pagesize = 25;
```

优化后解决方案的计划如图 5-8 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_383_0.png)

图 5-8 ROW_NUMBER 的计划，最小化了查找。

观察发现 Top 算子过滤了前 75 行，然后 Filter 算子过滤了最后 25 行，最后寻寻（seeks）和查找（lookups）仅执行了 25 次。第三页请求的计划执行涉及 153 次逻辑读取，而之前的解决方案需要 241 次。

再次运行存储过程，这次请求第 1000 页：

```sql
EXEC dbo.GetPage @pagenum = 1000, @pagesize = 25;
```

这次执行需要 223 次逻辑读取，而之前的解决方案需要 76,644 次。

## 使用带修改的 TOP 选项

T-SQL 支持在修改语句中使用 `TOP` 过滤。本节首先描述了这一功能、其局限性以及针对局限性的变通方法。然后描述了在需要删除大量行时使用该功能的实际案例。

在我的示例中，将使用一个名为 `MyOrders` 的表。运行以下代码创建此表作为 `PerformanceV3` 数据库中 `Orders` 表的初始副本：

```sql
USE PerformanceV3;
IF OBJECT_ID('dbo.MyOrders','U') IS NOT NULL DROP TABLE dbo.MyOrders;
GO
SELECT * INTO dbo.MyOrders FROM dbo.Orders;
CREATE UNIQUE CLUSTERED INDEX idx_old_on dbo.MyOrders(orderdate, orderid);
```

## 带修改的 TOP

在 T-SQL 中，你可以配合修改语句使用 `TOP`。这些语句包括 `INSERT TOP`、`DELETE TOP`、`UPDATE TOP` 和 `MERGE TOP`。这意味着一旦影响了请求的行数，语句将停止修改。例如，以下语句从 `MyOrders` 中删除了 50 行：

```sql
DELETE TOP (50) FROM dbo.MyOrders;
```

在 `SELECT` 语句中使用 `TOP` 时，你可以使用 `ORDER` 子句来控制选择哪些行。但修改语句没有 `ORDER` 子句。这意味着你可以指定想要修改的行数，但不是基于顺序——至少，不能直接做到。因此，前述语句删除了 50 行，但你无法控制删除的是哪 50 行。你应该认为该顺序是随机的。在实践中，它取决于优化和数据布局。

这种局限性是设计的结果，但如果你需要控制删除哪些行，可以使用一种常见的变通方法。以下是其工作原理示例：

```sql
WITH C AS (
  SELECT TOP (50) *
  FROM dbo.MyOrders
  ORDER BY orderdate
)
DELETE FROM C;
```

等等，使用 CTE 执行此事的更常见方法是：

```sql
WITH C AS (
  SELECT TOP (50) orderid
  FROM dbo.MyOrders
  ORDER BY orderdate
)
DELETE O FROM dbo.MyOrders O
INNER JOIN C ON O.orderid = C.orderid;
```

锁将会发生冲突）；SQL Server 将在每额外增加 1,250 个锁时继续尝试升级。当升级成功时，事务将锁定整个表（或分区）直到完成。这种行为可能会导致并发问题。

如果你想终止正在进行的此类大范围修改，你将面临回滚的后果。如果事务已经运行了一段时间，回滚也需要一段时间才能完成——通常，与原始工作所需的时间一样长。

为了避免上述问题，推荐的方法是采用分批处理修改逻辑。对于我们的清理过程，你可以运行一个循环，反复执行 `DELETE TOP` 语句，直到所有符合条件的行都被删除。你需要确保分批大小不要太小，以至于过程持续时间过久，但又希望它小到足以触发锁升级。棘手的部分在于确定分批大小。在 SQL Server 尝试升级之前需要 5,000 个锁，但这如何转化为你正在删除的行数呢？SQL Server 最初可能决定使用行锁或页锁，而且当你从表中删除行时，SQL Server 也会从定义在表上的索引中删除相应的行。因此，在没有测试的情况下，很难预测理想的行数是多少。

一种简单的方法是在运行带有锁升级事件的跟踪或扩展会话时测试不同的数字。例如，我在 Live Data 窗口运行了以下扩展会话，同时在 ID 为 53 的会话中使用 `DELETE TOP` 语句：

```sql
CREATE EVENT SESSION [Lock_Escalation] ON SERVER
ADD EVENT sqlserver.lock_escalation
WHERE ([session_id]=(53));
```

我使用以下语句从10,000 行开始：

```sql
DELETE TOP (10000) FROM dbo.MyOrders WHERE orderdate < '201301-01';
```

然后我调整了数字，根据是否发生了升级事件来增加或减少。在我的情况下，发生升级的节点在 6,050 到 6,100 行之间。一旦你找到了它，你就不想使用该点减 1 的值。例如，如果你以后添加了索引，该点将会改变。为了安全起见，我将测试中找到的数字除以二。这应该为未来添加索引留出足够的空间。当然，需要定期重新读取以查看数字是否需要调整。

```sql
SET NOCOUNT ON;
WHILE 1 = 1
BEGIN
    DELETE TOP (3000) FROM dbo.MyOrders WHERE orderdate < '201301-01';
    IF @ROWCOUNT < 3000
        BREAK;
END
```

该代码使用了无限循环。每次执行 `DELETE TOP` 语句都会删除最多 3,000 行并提交。一旦受影响的行数少于 3,000，你就知道到达了最后一批，因此代码将跳出循环。如果此过程正在运行（在高峰时段），你可以中止它，停止它是相当安全的。当前批次将进行回滚。然后你可以在此此任务的下一个窗口中再次运行它，进程将简单地从上次停止的地方继续。

## 每组前 N (Top N per group)

“每组前 N”（*Top N per group*）任务是一项经典任务，在实践中以多种形式出现。示例包括：“返回每种证券的最新价格”、“返回每个地区处理订单最多的员工”、“返回每个客户最近的三个订单”等等。有趣的是，在 T-SQL 的许多其他示例中，并没有一种解决方案在所有情况下都被认为是最优的。不同的解决方案在不同的情况下效果最好。对于 Top N 任务，有两个因素决定了哪种解决方案最高效：支持索引的可用性以及分区（组）列的密度。

我将演示不同解决方案的任务是：从任何“每组前 N”任务中返回每个客户最近的订单，你需要识别涉及的元素：分区、排序和覆盖。分区元素定义了组。排序元素定义了顺序——基于该顺序，你过滤每个组中的前 N 行。覆盖元素仅代表你需要返回的其余列。以下是我们示例任务中的元素：

- 分区 (Partitioning): `custid`
- 排序 (Ordering): `orderdate DESC`, `orderid DESC`
- 覆盖 (Covering): `empid`

如所述，决定哪种解决方案高效的因素因素之一是支持性索引的可用性。如果表很小或没有索引，扫描可能是可以的。但如果表很大，索引就是至关重要的。我将使用以下代码为我们的示例创建索引：

```sql
CREATE UNIQUE INDEX idx_orders_poc ON Sales.Orders(custid, orderdate DESC)
INCLUDE(empid);
```

## TOP 扩展

再次，作为一种思维练习，如果你可以更改或扩展 TOP 过滤的设计，你会做什么？在现有的设计中，TOP 的排序规范是基于底层查询的 `ORDER BY` 子句的。另一种设计是让 TOP 使用独立于底层查询 `ORDER BY` 子句的自己的排序规范。这样就很明确 TOP 排序并不提供任何呈现排序的保证，但它允许你为 TOP 过滤器和呈现目的使用不同的排序规范。此外，TOP 语法可以受益于一个分区元素，使得过滤器可以按分区应用。由于与窗口函数一起使用的 `OVER` 子句已经支持分区和排序规范，因此没有必要重造轮子。TOP 可以使用类似的语法，如下所示：

```
TOP (< expression > ) [ PERCENT ] [ WITH TIES ]
OVER ( PARTITION BY (< partition by list > ) [ ORDER BY ( <order by list > ) ] )
```

然后你可以使用以下查询来请求每个客户最近三个三个订单（但不要运行此查询，因为它依赖于不支持的语法）：

```
SELECT TOP (3) OVER PARTITION BY custid ORDER BY orderdate, orderid
FROM dbo.Orders
ORDER BY orderdate, orderid;
```

你可以在此链接中找到向微软改进 TOP 过滤器的请求：http://connect.microsoft.com/SQLServer/feedback/details/254390/over-clause-enhancement-request-top-order。在 SQL Server 中实现此类设计不应该引起兼容性问题。SQL Server 可以在不存在 `OVER` 子句时假设原始行为，并在存在时采用新行为。

## 使用连接的解决方案（随带排序）

在缺少 POC 索引的情况下，我描述的两种解决方案都会变得低效，并且存在扩展性问题。基于 `ROW_NUMBER` 函数的解决方案将需要排序。排序的扩展性是 n log n，随着行数的增加，每行的成本会变得更高。使用 TOP 过滤器和 `APPLY` 操作符的解决方案可能需要 `Index Spool` 操作符（这涉及在计划期间创建索引）和排序。

有趣的是，当在每组前 N 查询中 N 等于 1 且缺少 POC 索引时，有第三种方法的性能和扩展性都比其他方法更好。

在继续操作之前，请确保已删除了 POC 索引：

```sql
DROP INDEX idx_poc ON Sales.Orders;
```

第三种解决方案基于元素的连接。它实现了一种你可以认为“随带排序”（carry-along sort）的技术。你首先编写一个分组查询，按 P 元素 (`custid`) 对行进行分组。在 `SELECT` 列表中，将 O 元素 (`orderdate DESC`, `order DESC`) 和 C 元素 (`empid`) 转换为字符串并合并为一个。这里的重要的是将原始值转换为保留原始排序行为的字符串。例如，对整数使用前导零，对日期使用 YYYYMMDD 格式，等。保留 O 元素的排序行为以过滤行至关重要。C 元素应该被添加以输出到输出。你对连接后的字符串应用 `MAX` 聚合函数。这将每个客户返回一条，其中连接后的字符串持有最近的订单。最后，你基于分组查询定义一个 CTE，并在外部查询中从连接字符串中提取各个列，并将它们转换回原始类型。以下是完整的解决方案查询：

```sql
WITH C AS (
SELECT
  custid,
  MAX(CONVERT(CHAR(8), orderdate, 112)
    + RIGHT('000000000' + CAST(orderid AS VARCHAR(10)), 10)
    + CAST(empid AS CHAR(10)) COLLATE Latin1_General_BIN2 2) AS Orders
FROM Sales.Orders
GROUP BY custid)
```

```sql
SELECT
CAST(SUBSTRING(s, 1, 8) AS DATE ) AS orderdate,
CAST(SUBSTRING(s, 9, 10) AS INT ) AS orderid,
CAST(SUBSTRING(s, 19, 10) AS CHAR(10)) AS empid
FROM C;
```

这种解决方案的优之处在于它的扩展性比其他方案要好得多。对于小型输入表，优化器通常会对数据排序并使用基于排序的聚合（`Aggregate` 操作符）。但对于大型输入表，优化器会使用并行处理，每个线程使用基于基于哈的聚合来完成大部分工作，并由全局聚合来汇总本地结果。你可以通过对 PerformanceV3 数据库中的 Orders 运行随带排序解决方案来看到这一点：

```sql
Use PerformanceV3;

WITH C AS (
SELECT
  custid,
  MAX(CONVERT(CHAR(8), orderdate, 112)
    + RIGHT('000000000' + CAST(orderid AS VARCHAR(10)), 10)
    + CAST(empid AS CHAR(10)) COLLATE Latin1_General_BIN2 2) AS Orders
FROM dbo.Orders
GROUP BY custid)
```

```sql
SELECT
CAST(SUBSTRING(s, 1, 8) AS DATE ) AS orderdate,
CAST(SUBSTRING(s, 9, 10) AS INT ) AS orderid,
CAST(SUBSTRING(s, 19, 10) AS CHAR(10)) AS empid
FROM C;
```

此查询的执行计划如图 5-11 所示。

| Compute Scalar | Parallel Streams | Hash Match | Parallel Streams | Hash Match | Compute Scalar | Clustered Index |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| SELECT | | | | | | |
| 0% | 0% | 0% | 18% | 18% | 30% | 54% |

通过 `grp` 列进行分组并计算 `val` 列的平均值作为中位数。这里是完整的解决方案：

```sql
WITH Counts AS
(
SELECT grp, COUNT(*) AS cnt
FROM dbo.T1
GROUP BY grp
),
RowNums AS
(
SELECT grp, val,
ROW_NUMBER() OVER (PARTITION BY grp ORDER BY val) AS n
FROM dbo.T1
)
SELECT C.grp, AVG(1 * R.val) AS median
FROM Counts AS C
INNER MERGE RowNums AS R
on C.grp = R.grp
WHERE R.n IN (( C.cnt + 1 ) / 2, ( C.cnt + 2 ) / 2 )
GROUP BY C.grp;
```

该解决方案的计划如图 5-12 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_394_0.png)

**5-12** 使用 ROW_NUMBER 的解决方案计划。

SQL Server 选择了一个串行计划，该计划执行了两次索引扫描、几次基于排序的聚合、一次行号计算以及一个合并连接（merge join）。与之前使用 `PERCENTILE_COUNT` 函数的解决方案相比，新解决方案非常高效。在我的系统中仅花费 8 秒即可完成。尽管如此，还有进一步改进的空间。例如，你可以尝试出一个使用并行计划的解决方案，这可以减少需要扫描的页数，你还可以尝试消除昂贵的合并连接。

## 使用 OFFSET-FETCH AND APPLY 的解决方案

我将提出的第三种解决方案使用了 `APPLY` 运算符和 `OFFSET-FETCH` 过滤器。该解决方案定义了一个名为 C 的 CTE，它基于一个分组查询，为每个组计算 OFFSET 和 FETCH 子句的参数。偏移值（称为 ov）计算方式为 `(count - 1) / 2`，取值值（称为 fv）计算方式为 `2 - count % 2`。例如，如果一个组有 11 行，ov 是 5，fv 是 1。对于一个有 12 行的组，ov 是 5，fv 是 2。外部查询对 C 中的每个组应用 OFFSET-FETCH 查询以检索相对值。最后，外部查询对剩余行进行分组并计算值的平均值作为中位数。

370 第 5 章 TOP AND OFFSET-FETCH



WITH C AS
(
    SELECT grp,
           COUNT(*) AS cnt,
           COUNT(*) - 1 / 2 AS ov,
           2 - COUNT(*) % 2 AS fv
    FROM dbo.T1
    GROUP BY grp
)
SELECT grp, AVG(1.* val) AS median
FROM C
CROSS APPLY (
    SELECT O.val
    FROM dbo.T1 AS O
    WHERE O.grp = C.grp
    ORDER BY O.val
    OFFSET C.ov ROWS FETCH NEXT C.fv ROWS ONLY
) AS A
GROUP BY grp;

该解决方案的计划如图 5-13 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_395_0.png)

图 5-13 使用 OFFSET-FETCH 和 APPLY 的解决方案。

第三种解决方案的计划相比第二种计划有三个优势。首先是它利用了并行效率。其次是在一个节点和半个节点中扫描索引，而不是两个。由于数据是密集组，寻址（seek）的成本可以忽略不计。第三个优势是计划中没有合并连接。该解决方案在我的系统中仅花费了 1 秒。对于 10,000,000 行来说，令人印象深刻。

## 结论

本章涵盖了 TOP 和 OFFSET-FETCH 过滤器。它从过滤器的逻辑描述开始，然后继续通过分页解决方案演示了优化方面。你看到了在排序列上建立索引对于获得良好性能是多么关键。即使有了索引，我对如何修改解决方案以避免不必要的查找提供了建议。

本章还涵盖了使用 TOP 过滤器修改数据。最后，本章通过演示如何使用 TOP 和 OFFSET-FETCH 来解决如每组前 N 和使用中位数等复杂任务。

本页故意留白

## 数据修改

本章涵盖与数据修改相关的话。它并不是为了提供 Microsoft SQL Server 所有数据修改功能的详尽介绍，而是关注某些功能中更务实且可能不那么简单的方面。

本章涵盖了数据插入，主要关注批量导入工具。讨论了序列对象，并将其与 `identity` 列属性进行对比。它涵盖了删除、更新和合并数据的方面。它还讨论了 `OUTPUT` 子句，演示了它的实际用途。

## 插入数据

SQL Server 支持多种你可以向表中插入数据的工具。其中某些工具使用了批量加载优化，而这些工具是本节的重点。

本节从讨论 `SELECT INTO` 命令开始。然后继续讨论额外的批量导入工具以及它们为了最小日志记录进行处理所需的要求。本节随后提供了使用灵活批量行集提供者的示例。

## SELECT INTO

`SELECT INTO` 命令创建一个包含查询结果集的新表。它会复制源定义（列名、类型、排序规则、可空性和 identity 属性）和数据。在演示 `SELECT INTO` 的用法之前，运行以下代码以确保 `MyOrders` 不存在：

```
SET NOCOUNT ON;
USE Performance3;
IF OBJECT_ID(N'MyOrders', N'U') IS NOT NULL DROP TABLE MyOrders;
```

运行以下 SELECT 语句来创建 MyOrders：

```
SELECT orderid, custid, orderdate
INTO MyOrders
FROM Performance3;
```

该查询的执行计划如图 6-1 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_398_0.png)

**6-1** 并行的 SELECT INTO。

`SELECT INTO` 的优点之一是其高效，特别是在满足最小日志记录时。当数据库恢复模式为完全（full）时，操作通过完全日志记录处理。然而，当恢复模式为简单（simple）或批量日志（bulk-logged）且未启用事务复制时，操作通过最小日志记录处理。这意味着只记录出于目的所需的信息：分配位图（GAM, IAM, PFS），但不会记录实际插入的数据。最小日志和完全日志之间的日志记录数量差异可能是巨大的。例如，要向表中填充 1GB 的数据，SQL Server 在最小日志模式下仅需要记录几兆字节，而在完全日志模式下需要记录整个 1GB。详细信息请参见“测量日志量”一节。

如果源列具有 `identity` 属性，通常该属性会被复制到目标。如果你不想复制该属性，请对源列应用处理，例如 `ISNULL(col1, 0) AS col1`。

如果你需要创建一个具有 `identity` 属性的新目标列，请使用 `IDENTITY` 函数。但注意，如果在查询中指定了 `ORDER BY` 子句，无法保证生成的标识值反映该顺序。为了获得保证，请使用 `INSERT SELECT` 语句。

如果你需要目标列的类型与源列不同，请使用 `CAST(col1 AS BIGINT) AS col1`。注意，这种处理将导致结果列为空。你可以使用 `ISNULL` 函数使目标列定义为 `NOT NULL`，即 `ISNULL(CAST(col1 AS BIGINT),0) AS col1`。

我提到 SQL Server 2014 引入了 `SELECT INTO` 的并行处理。SQL Server 2014 (CU 10) 的另一项改进也已回到了 SQL Server 2012 服务包 1 (SP1) 累计更新中，涉及目标表为临时表时处理快速写入的方式。你可以在此处找到该改进的详情：http://blogs.msdn.com/b/psql/archive/2014/04/09/sql-server-2014-tempdb-hidden-performance-gem.aspx。快速写入器迅速将与批量操作相关的脏页刷入磁盘，以便 SQL Server 无需等待整个操作完成即可写入磁盘。这防止了批量操作用新页填充内存，但话说回来，这会导致物理 I/O。改进之处在于在 tempdb 中执行批量操作时，当对临时表执行 `SELECT INTO` 时，激进写入行为被放宽，不再像以前那样强制快速刷新脏页。这在创建临时表、查询它们以及快速删除它们时是有益的。现在，此类工作可以在减少物理 I/O 甚至完全不需要的情况下完成。

与 `INSERT SELECT` 相比，`SELECT INTO` 要简单得多，因为你不需要在复制数据之前创建表。`SELECT INTO` 也有缺点。一个缺点是它不允许你指定目标文件组，它使用目标数据库的默认文件组。另一个缺点是该语句结合了 DDL 和 DML，在事务完成之前，不仅目标表的数据被排他锁定，元数据也是如此。正如我将演示的那样，这会导致与元数据访问相关的阻塞。

首先，运行以下代码，如果 MyOrders 表存在，则删除它：

```
USE PerformanceV3;
IF OBJECT_ID(N'dbo.MyOrders', N'U') IS NOT NULL DROP TABLE dbo.MyOrders;
```

打开两个连接。在连接 1 中运行以下代码以开始用户事务并执行 `SELECT INTO` 语句：

```
USE PerformanceV3;
BEGIN TRAN
SELECT orderid, custid, empid, shipperid, orderdate, filler
INTO dbo.MyOrders
FROM dbo.Orders;
```

假设源表非常大，语句需要一些时间才能完成。我通过保持事务开启来模拟一个长时间运行的 `SELECT INTO` 语句。在事务完成之前，操作产生的数据和元数据都被排他锁定。

在连接 2 中，运行以下 `sys.tables` 查询以获取数据库中的表集：

```
USE PerformanceV3;
SELECT SCHEMA_NAME(schema_id) AS schelename, name AS tablename FROM sys.tables;
```

该查询在默认的 `Read Committed`（已提交）隔离级别下运行时会被阻塞。这是因为会话需要共享锁来读取资源（在本例中为 `sys.tables` 中的行），而当另一个会话持有该资源的排他锁时，请求就会被阻塞。

在连接 1 中运行以下代码以提交事务：

```
COMMIT TRAN
```

现在 `SELECT INTO` 事务已提交，它释放了所有锁，因此连接 2 中的查询在会话成功获取其等待的共享锁后完成。

替代方案是在一个快速的事务中创建目标表，然后在另一个事务中使用 `INSERT SELECT` 语句填充它。这样一来，至少你不会遇到与元数据访问相关的长时间阻塞语句。

## 批量导入

除了 `SELECT INTO`，SQL Server 还支持其他可以向你的表插入数据并从批量优化中受益工具：`bcp.exe` 实用程序、`BULK INSERT` 命令、使用批量行提供程序的 `INSERT SELECT`（详见本文单独章节）以及带有本地查询的 `INSERT SELECT`。这些工具统称为*批量导入*（bulk-import）工具。

与 `INTO` 类似，其余批量导入工具可以使用最少日志进行处理，尽管它们需要满足更长的要求列表。要求如下：

- 数据库的恢复模型必须是 `simple`（简单）或 `bulk-logged`（批量日志）。在 `full`（完全）恢复模式下，将获得完全日志。
- 未启用事务复制。如果启用了事务复制，即使恢复模型不是 `full`，你也会获得完全日志。
- 如果表是堆（heap）：
    - 表不需要为空。
    - 你必须指定 `TABLOCK` 选项。注意，对于 `bcp.exe`、`BULK INSERT` 和行集提供程序，此选项代表批量更新锁，允许多个进程同时向同一个目标表加载数据。对于带有本地查询的 `INSERT SELECT`，此选项代表完全的排他表锁，因此同一时间只能有一个进程向表插入数据。
- 如果表是 B 树（聚集索引），满足以下任一条件均即可：
    - 表是空的，且你指定了 `TABLOCK`，并启用了跟踪标记 610。
    - 表是非空的，启用了跟踪标记 610，并且你插入了一个新的键范围；新页分配将记录最少日志。

最少日志记录的要求用以下逻辑表达式总结：

```
non-FULL recovery model AND transactional replication not enabled
AND ( Heap AND TABLOCK
OR B-tree
AND ( empty AND ( TABLOCK OR TF-610 )
OR nonempty AND TF-610 AND new-key-range )
```

使用 `INSERT` 和 `MERGE` 语句插入数据时，你将获得完全日志。有关调整数据加载操作的更多信息，请参阅“数据加载指南”（http://msn.microsoft.com/en-us/library/425070.aspx）。

# 测量日志量

我描述了你的批量导入操作为了以最少日志处理而需要满足的要求。但如果你想知道涉及多少日志，为了此目的，我使用了未公开的函数 `fn_dblog`。该函数返回当前数据库在日志序列号（LSN）范围内的事务日志。如果你想获取所有事务日志记录，请提供两个 `NULL` 参数。

例如，以下查询返回 `PerformanceV3` 数据库中所有日志记录的计数和总大小：

```
USE PerformanceV3;
SELECT SCHEMA_NAME(schema_id) AS schelename, name AS tablename FROM sys.tables;
```

该查询在默认的 `Read Committed` 隔离级别下运行时会被阻塞。这是因为会话需要共享锁来读取资源（在本例中为 `sys.tables` 中的行），而当另一个会话持有该资源的排他锁时，请求就会被阻塞。

（每批行数、错误文件等）。此功能的奇妙之处在于，`OPENROWSET` 函数可以像表一样被查询调用，并且拥有同等的常规查询操作能力。

为了演示这一功能，我将从放置在 `C:\temp` 文件夹中的文件中进行查询并导入数据。如果你想在自己的环境中运行这些示例，请下载书籍的压缩源码文件（可从 http://tsql.solid.com/books/tq3/ 获取），并将源 temp 文件夹中的文件存到 `C:\temp` 文件夹中。

`shippers.txt` 文件包含我最初从 `TSQLV3` 数据库中的 `Sales.Shippers` 表导出的信息。为了支持未来的导入，我还使用 `bcp.exe` 工具的格式选项创建了一个名为 `Shippers.fmt` 的文件，如下所示（在具有正确服务器和实例名的命令行提示符中执行）：

```
bcp TSQLV3.Sales.Shippers format nul -c -f C:\temp\Shippers.fmt -T -S <server,instance_name>
```

以下是如何使用 `OPENROWSET` 函数配合行集提供程序（rowset provider），根据 `Shippers.fmt` 格式文件查询 `Shippers.txt` 文件：

```
SELECT shipperid, companyname, phone
FROM OPENROWSET(BULK 'C:\temp\Shippers.txt',
FORMATFILE = 'C:\temp\Shippers.fmt') AS F;
```

此代码生成以下输出：

| shipperid | companyname | phone |
|---|---|---|
| 1 | Shipper GVSUA | (S03) 555-9831 |
| 2 | Shipper ETYNR | (S03) 555-3199 |
| 3 | Shipper ZHISN | (S03) 555-9931 |

这简直太棒了！

因为你在 FROM 子句中像使用表一样使用了 `OPENROWSET` 函数，所以你可以应用常规的查询操作能力。例如，假设数据库中有一个名为 `TargetTable` 的表，你想从电话号码以 `(S03) 555-9` 开头的文件导入数据到该表。你可以使用普通的 WHERE 子句对数据进行过滤，如下：

注意使用 `TABLOCK` 选项以启用最小日志记录。

你还可以使用单模式下的批量行集提供程序（bulk rowset provider）查询并返回文件内容，作为一个单行和单个大对象列的行集。你可以指定三个选项之一：用于 Unicode 字符数据的 `SINGLE_NCLOB`，用于普通字符数据的 `SINGLE_CLOB`，以及用于二进制数据的 `SINGLE_BLOB`。将此类查询放在括号中使其成为一个自包含的子查询；因此，它可以作为标量表达式用于 `INSERT` 和 `UPDATE` 语句中。

为了演示单模式下批量行集提供程序的使用，我将从 `C:\temp\` 文件夹中的文件导入到 `tempdb` 数据库中名为 `T1` 的表中。首先运行以下代码创建表 T1：

```
USE tempdb;
IF OBJECT_ID(N'dbo.T1', N'U') IS NOT NULL DROP TABLE dbo.T1;
CREATE TABLE dbo.T1
(
  id      INT NOT NULL PRIMARY KEY,
  xmlval  XML NULL,
  textval VARCHAR(MAX) NULL,
  ntextval NVARCHAR(MAX) NULL,
  binval  BINARY(MAX) NULL
);
```

如你所示，该表有一个键列和四个大对象类型的列。

以下代码向表中插入一个键为 1 的新行，并使用批量行集提供程序从 XML 文件 `xmlfile.xml` 获取 XML 字段 `xmlval` 的值：

```
INSERT INTO dbo.T1(id, xmlval)
VALUES (1,
(SELECT xmlval FROM OPENROWSET(
  BULK 'C:\temp\xmlfile.xml', SINGLE_NCLOB AS F(xmlval))));
```

使用 `SINGLE_NCLOB` 选项是因为 `xmlfile.xml` 是一个 Unicode 格式的文件。

如前所述，你可以使用类似的子查询在 `UPDATE` 语句中设置列的值。作为**例句**，以下 `UPDATE` 语句将新行中其余三列的值设置为从三个文件中获得的值：

```
UPDATE dbo.T1
SET textval = (SELECT textval FROM OPENROWSET(
  BULK 'C:\temp\xmlfile.txt', SINGLE_NCLOB AS F(textval)),
ntextval = (SELECT ntextval FROM OPENROWSET(
  BULK 'C:\temp\xmlfile.txt', SINGLE_NCLOB AS F(ntextval)),
binval = (SELECT binval FROM OPENROWSET(
  BULK 'C:\temp\xmlfile.txt', SINGLE_BLOB AS F(binval)))
WHERE id = 1;
```

查询数据以查看导入了什么：

```
SELECT id, xmlval, textval, binval
FROM dbo.T1
WHERE id = 1;
```



你将得到以下输出（此处简略显示）：

```
id xmlval textval binval
1 ... This fil...
```

## 序列

SQL Server 提供了两个主要的内置工具来帮助生成代理键。一个是标识属性，你可能对其很熟悉；另一个是序列对象，它是在 SQL Server 2012 中引入的。本节的重点是序列对象及其与 `identity` 相比的缺点。微软根据标准 SQL 在 SQL Server 中实现了序列对象。我将首先提醒你 `identity` 属性的特性和不灵活性；接着我将介绍序列对象并与 `identity` 进行对比；最后，我将讨论关于这两个特性的性能考虑量。

### 标识属性的特性和不灵活性

`identity` 属性在许多方面都是不灵活的。它是作为定义的一部分指定的列的属性，例如 `INT NOT NULL`。它不是数据库中的一个独立对象。当你需要跨多个表生成代理键时（例如在自定义分区解决方案中），这可能会成为问题。你不能将 `identity` 属性与现有列关联。该属性必须在创建表或修改表时定义。

`identity` 不能与可空的列一起使用。有时你需要在使用键之前生成一个代理键。`identity` 不支持此功能。你必须向目标表插入一个新行，然后使用 `SCOPE_IDENTITY()` 函数获取新生成的键。

你不能在普通的 `SELECT` 查询中用 `identity` 来生成新键。你可以使用 `IDENTITY` 语句在目标表中生成一个具有 `identity` 属性的列。无法保证 `identity` 值是按照特定顺序生成的，即使查询带有 `ORDER BY` 子句。如果你需要键按特定顺序生成，请使用 `ORDER BY` 子句。关于详细信息请参阅以下知识库文章：http://support.microsoft.com/kb/273586

`identity` 无法循环。达到最大值后，对于具有 `identity` 属性的列，在定义时，可以指定最小值和最大值。

`identity` 无法自动循环。在 SQL Server 2012 之前，`identity` 没有缓存；相反，每个值的生成都会导致记录写入。在 SQL Server 2012 和 2014 中，`identity` 有一个预定义的缓存值，取决于目标列的数据类型。微软保留了根据需要更改它的权利。缓存功能提供了性能优势，但这意味着如果 SQL 进程发生异常终止（例如 AlwaysOn 可用组故障转移），下一个值与上一个值会有间隔。你可以使用跟踪标记 272 禁用缓存以获得 2012 版的行为。

无论是否有缓存，`identity` 都无法保证值之间没有间隔。如果导致更改的 `INSERT` 语句失败或事务回滚，`identity` 更改不会撤销。如果你想保证键之间没有间隔，你必须自己实现解决方案。

`identity` 不支持在请求中获取值范围。当你在应用程序中想要为某些目的分配整个键范围时，这可能是需要的。

### 序列对象

与 `identity` 不同，序列对象是数据库中的一个独立对象。你使用 `CREATE SEQUENCE` 命令创建它，使用 `ALTER SEQUENCE` 命令修改其属性，并从 `NEXT VALUE FOR` 函数检索新值。以下是创建序列的语法：

```sql
CREATE SEQUENCE <schema_name>.<sequence_name> AS <type>
START WITH <constant>
INCREMENT BY <constant>
MINVALUE <constant> | NO MINVALUE
MAXVALUE <constant> | NO MAXVALUE
NO CYCLE | CYCLE
CACHE <constant> | NO CACHE;
```

与其他数据库中的对象一样，你将序列放在模式中。与 `identity` 类似，它支持所有比例为零的数值类型：`TINYINT`、`SMALLINT`、`BIGINT`、`NUMERIC(p,0)/DECIMAL(p,0)`。如果你没有指定类型，默认使用 `BIGINT`。如果你最终存储序列的目标列的类型与 `BIGINT` 不同，你希望确保序列具有正确的类型。否则，你将为类型转换支付额外代价。数据类型是序列一旦后无法更改的方面。要更改类型，你需要删除并重新创建序列。

默认情况下，序列被定义为不循环；然而，如果你需要支持循环，请指定 `CYCLE` 选项。

使用 `START WITH` 属性来定义序列生成的第一个值。如果未指定，当 `INCREMENT BY` 属性为正数时，`START WITH` 属性默认认为 `MINVALUE`；当为负数时，认为 `MAXVALUE`。请注意，如果序列定义为循环，在达到 `MAXVALUE` 属性值后，它将循环到 `MINVALUE` 属性定义的值（假设增量为 1），而不是原始的 `START WITH` 属性。当你需要创建一个仅支持正值范围的循环序列时，指定 `START WITH 1 CYCLE` 是一个常见的错误。因为在达到最大值后，序列将循环到最小值（例如，-2147483648 (`INT`)）。正确的做法是将 `MINVALUE` 设置为 1，而不是设置 `START WITH`；在创建序列时，后者默认会被设置为前者，反之亦然。

使用 `INCREMENT BY` 属性来指定步长值。正如你所猜的，它的默认值为 1。

你可以使用 `CACHE` 属性来控制新值导致磁盘写入和记录的频率，而不是仅使用内存缓存。值越大，性能越好。然而，如果 SQL Server 进程非正常终止，生成的下一个值与上一个值之间可能会产生高达缓存值的间隔。我将在下一节中讨论缓存功能的性能考虑。

例如，以下代码在 `PerformanceV3` 数据库中创建了一个名为 `Segorderis` 的序列用于生成订单 ID：

```sql
USE PerformanceV3;
```

```sql
IF OBJECT_ID('dbo.Segorderis', 'SS') IS NOT NULL DROP SEQUENCE dbo.Segorderis;

CREATE SEQUENCE dbo.Segorderis AS INT
MINVALUE 1
CYCLE
CACHE 1000;
```

该序列定义为 `INT`，仅支持该类型中的正值范围，允许循环，并使用了 1000 的缓存。

要从序列获取新值，请调用 `NEXT VALUE FOR` 函数，如下：

```sql
SELECT NEXT VALUE FOR dbo.Segorderis;
```

你可以在许多地方使用该函数，例如 `DEFAULT` 约束、变量赋值、`UPDATE` 和 `MERGE` 赋值、单行和多行 `SELECT` 语句、单行和多行 `INSERT VALUES` 语句以及 `INSERT SELECT` 语句。你不能在子查询中使用该函数。

你可以使用 `ALTER SEQUENCE` 命令修改数据类型以外的所有序列属性，语法如下：

```sql
ALTER SEQUENCE dbo.Seqderids
RESTART WITH <constant>
INCREMENT BY <constant>
MINVALUE <constant> | NO MINVALUE
MAXVALUE <constant> | NO MAXVALUE
NO CYCLE | CYCLE
CACHE <constant> | NO CACHE;
```

要获取有关现有序列的元数据信息，请查询 `sys.Sequences` 视图。例如，该查询检索了 `Seqderids` 序列的属性：

```sql
SELECT current_value, start_value, increment, minimum_value, maximum_value, is_cycling,
is_cached, cache_size
FROM sys.Sequences
WHERE object_id = OBJECT_ID('dbo.Seqderids', 'S');
```

该查询生成了以下输出：

| current_value | start_value | increment | minimum_value | maximum_value | is_cycling | cached | cache_size |
|---|---|---|---|---|---|---|---|
| 1 | 1 | 1 | 1 | 2147483647 | 1 | 1 | 1000 |

回想 `identity` 属性的不灵活性。相比之下，序列对象要灵活得多。有趣的是，`identity` 和 `sequence` 在内部实现为同一个物理对象，但语言层面的设计使得序列变得灵活得多。两者之间还存在关键的性能差异，需要你注意。我将在下一节中讨论。

由于序列是数据库中的一个独立对象，你可以在任何地方使用生成的键——例如，跨表分区解决方案中的多个表。

请注意，序列和 `identity` 本身并不保证唯一性。请记住，在任何时候你都可以更改当前值，也可以插入你自己的值。你需要使用约束等完整性强制工具来保证某些列的唯一性。

如果你想使用序列自动创建列中的键，可以在 `DEFAULT` 约束中调用 `NEXT VALUE` 函数。这是对标准的扩展。与 `identity` 属性不同，`DEFAULT` 约束可以添加到现有列中，也可以从列中移除。你可能有一张带有 `order` 列的 `Orders` 表，你想使用序列 `Seqderids` 自动创建订单 ID。以下是添加此类约束的代码：

```sql
ALTER TABLE dbo.DFT_orders_orderid
ADD CONSTRAINT (NEXT VALUE FOR dbo.Seqderids) FOR order;
```

如果在任何时候停止订单 ID 的自动生成，可以删除约束，如下：

```sql
ALTER TABLE dbo.Orders DROP CONSTRAINT DFT_orders_id;
```

由于序列对象独立于目标表和存储生成值的列，如果你愿意，没有任何机制阻止目标列允许 `NULL` 值。

如果你需要在使用序列值之前生成它，可以将其临时存储在某并在稍后需要时使用。例如，你可以将其存储在变量中，如下：

```sql
DECLARE @newkey AS INT = NEXT VALUE FOR dbo.Seqderids;
```

### 性能、序列与标识考量

如前所述，序列和标识在内部是基于同一个物理对象实现的。然而，这两个功能的实现上存在重要差异，这可能会导致不同的性能影响。当你将使用一个功能的实现切换到使用另一个功能的实现时，这些差异尤为重要。

影响标识和序列性能的主要方面是缓存。缓存决定了 SQL Server 写入磁盘的频率。例如，如果你为序列对象使用 1000 的缓存值。当你第一次请求一个值时，SQL Server 会将 1000 写入磁盘，并在两个内存成员中存储当前值 1 和剩余值数量 999。在 999 次请求后，持有当前值的成员为 1000，而持有值数量的成员为 0。下一次请求将写入 2000，它写入的内存成员将是 1001 作为当前值，以及 99 作为剩余值数量。以此此类推。如果在 AlwaysOn 可用性组中——在重启后，当前值将设置为磁盘上的上的值。因此，你可能会一次性丢失多达缓存大小的值。在选择缓存值时，你需要决定为了提高性能，你愿意在这种事件中丢失多少值。我很快会提供具体的性能数据。但不要忘记我之前提到并演示过的：无论缓存大小如何，序列或标识都不会保证你不会出现间隙。

关于缓存的第一个有趣点是 SQL Server 默认使用什么。微软没有记录此项信息。更准确地说，文档中有一条注释明确表示公司不希望发布此信息：

> “如果启用了缓存选项但未指定缓存大小，数据库引擎将选择一个大小。然而，用户不应依赖该选择的一致性。微软可能会在不通知的情况下更改计算缓存大小的方法。”

尽管如此，你仍然可以通过测试来确定当前的缓存大小。在 SQL Server 2012 之前，标识没有缓存（已在 SQL Server 2008 R2 SP3 上测试）。在 SQL Server 2012 SP 和 2014 RTM 中，序列的默认缓存为 50（无论数据类型如何），而标识的缓存值取决于类型，如表 6-1 所示。

**表 6-1** 类型与缓存大小之间的关系

| 类型 | 缓存大小 |
|---|---|
| TINY | 10 |
| SMALLINT | 100 |
| INT | 1000 |
| BIGINT, NUMERIC | 10000 |

如果你想禁用标识的缓存，可以使用跟踪标志 272，但除此之外，你无法控制缓存大小。

如果你在与我测试时不同的版本上运行测试，正如文档所示，你系统中的默认缓存值可能会不同。

要确定默认缓存值，请使用以下测试。在准备阶段，创建不同类型的序列，以及带有标识属性的不同类型列的表。生成几个值，然后查询这些值。你可以通过运行以下代码来实现：

```sql
IF DB_ID('testdb') IS NULL CREATE DATABASE testdb;

USE testdb;

IF OBJECT_ID('testdb.dbo.SeqTINYINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqTINYINT;

IF OBJECT_ID('testdb.dbo.SeqSMALLINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqSMALLINT;

IF OBJECT_ID('testdb.dbo.SeqINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqINT;

IF OBJECT_ID('testdb.dbo.SeqBIGINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqBIGINT;

IF OBJECT_ID('testdb.dbo.SeqNUMERIC9') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqNUMERIC9;

IF OBJECT_ID('testdb.dbo.SeqNUMERIC38') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqNUMERIC38;

IF OBJECT_ID('testdb.dbo.TINYINT') = 'U' IS NOT NULL DROP TABLE dbo.TINYINT;

IF OBJECT_ID('testdb.dbo.SMALLINT') = 'U' IS NOT NULL DROP TABLE dbo.SMALLINT;

IF OBJECT_ID('testdb.dbo.TINT') = 'U' IS NOT NULL DROP TABLE dbo.TINT;

IF OBJECT_ID('testdb.dbo.BIGINT') = 'U' IS NOT NULL DROP TABLE dbo.BIGINT;

IF OBJECT_ID('testdb.dbo.NUMERIC9') = 'U' IS NOT NULL DROP TABLE dbo.NUMERIC9;

IF OBJECT_ID('testdb.dbo.NUMERIC38') = 'U' IS NOT NULL DROP TABLE dbo.NUMERIC38;
```

```sql
CREATE sequence dbo.SeqTINYINT AS TINYINT MINVALUE 1;

CREATE sequence dbo.SeqSMALLINT AS SMALLINT MINVALUE 1;

CREATE sequence dbo.SeqINT AS INT MINVALUE 1;

CREATE sequence dbo.SeqBIGINT AS BIGINT MINVALUE 1;

CREATE sequence dbo.SeqNUMERIC9 AS NUMERIC(9, 0) MINVALUE 1;

CREATE sequence dbo.SeqNUMERIC38 AS NUMERIC(38, 0) MINVALUE 1;
```

```sql
CREATE TABLE dbo.TINYINT (key TINYINT IDENTITY);

CREATE TABLE dbo.SMALLINT (key SMALLINT IDENTITY);

CREATE TABLE dbo.TINT (key INT IDENTITY);

CREATE TABLE dbo.BIGINT (key BIGINT IDENTITY);

CREATE TABLE dbo.NUMERIC9 (key NUMERIC(9, 0) IDENTITY);

CREATE TABLE dbo.NUMERIC38 (key NUMERIC(38, 0) IDENTITY);
```

```sql
SELECT NEXT VALUE dbo.SeqTINYINT;

SELECT NEXT VALUE dbo.SeqSMALLINT;

SELECT NEXT VALUE dbo.SeqINT;

SELECT NEXT VALUE dbo.SeqBIGINT;

SELECT NEXT VALUE dbo.SeqNUMERIC9;

SELECT NEXT VALUE dbo.SeqNUMERIC38;
```

```sql
INSERT INTO dbo.TINYINT DEFAULT VALUES;

INSERT INTO dbo.SMALLINT DEFAULT VALUES;

INSERT INTO dbo.TINT DEFAULT VALUES;

INSERT INTO dbo.BIGINT DEFAULT VALUES;
```



## 测试序列与标识的缓存行为

```sql
INSERT INTO dbo.NUMERIC9 DEFAULT VALUES;

INSERT INTO dbo.NUMERIC38 DEFAULT VALUES;
```

```sql
SELECT name, current_value FROM sys.Sequences
WHERE object_id IN
  OBJECT_ID('dbo.SeqTINYINT'),
  OBJECT_ID('dbo.SeqSMALLINT'),
  OBJECT_ID('dbo.SeqINT'),
  OBJECT_ID('dbo.SeqBIGINT'),
  OBJECT_ID('dbo.SeqNUMERIC9'),
  OBJECT_ID('dbo.SeqNUMERIC38');
```

```sql
SELECT
  IDENT_CURRENT('dbo.TINYINT') AS TINYINT,
  IDENT_CURRENT('dbo.SMALLINT') AS SMALLINT,
  IDENT_CURRENT('dbo.TINT') AS TINT,
  IDENT_CURRENT('dbo.BIGINT') AS BIGINT,
  IDENT_CURRENT('dbo.NUMERIC9') AS NUMERIC9,
  IDENT_CURRENT('dbo.NUMERIC38') AS NUMERIC38;
```

生成五个值后，我得到了如下输出：

| name | current_value |
|---|---|
| SeqTINYINT | 5 |
| SeqSMALLINT | 5 |
| SeqINT | 5 |
| SeqBIGINT | 5 |
| SeqNUMERIC9 | 5 |
| SeqNUMERIC38 | 5 |

| TINYINT | SMALLINT | TINT | BIGINT | NUMERIC9 | NUMERIC38 |
|---|---|---|---|---|---|
| 5 | 5 | 5 | 5 | 5 | 5 |

接下来，通过任务管理器结束 SQL Server 服务（使用 `Shift+Esc`），然后运行以下代码查询当前的序列和标识值：

```sql
USE testdb;

SELECT name, current_value FROM sys.Sequences
WHERE object_id IN
  OBJECT_ID('dbo.SeqTINYINT'),
  OBJECT_ID('dbo.SeqSMALLINT'),
  OBJECT_ID('dbo.SeqINT'),
  OBJECT_ID('dbo.SeqBIGINT'),
  OBJECT_ID('dbo.SeqNUMERIC9'),
  OBJECT_ID('dbo.SeqNUMERIC38');
```

```sql
SELECT
  IDENT_CURRENT('dbo.TINYINT') AS TINYINT,
  IDENT_CURRENT('dbo.SMALLINT') AS SMALLINT,
  IDENT_CURRENT('dbo.TINT') AS TINT,
  IDENT_CURRENT('dbo.BIGINT') AS BIGINT,
  IDENT_CURRENT('dbo.NUMERIC9') AS NUMERIC9,
  IDENT_CURRENT('dbo.NUMERIC38') AS NUMERIC38;
```

这是在我系统上得到的输出：

| name | current_value |
|---|---|
| SeqTINYINT | 50 |
| SeqSMALLINT | 50 |
| SeqINT | 50 |
| SeqBIGINT | 50 |
| SeqNUMERIC9 | 50 |
| SeqNUMERIC38 | 50 |

| TINYINT | SMALLINT | TINT | BIGINT | NUMERIC9 | NUMERIC38 |
|---|---|---|---|---|---|
| 11 | 101 | 1001 | 10001 | 10001 | 10001 |

标识和序列的缓存大小存在明显的差异。还有一个神奇的事实是，在标识的情况下恢复的值与缓存大小差 1，而在序列中不是。从序列可以看出，标识将“当前值+缓存大小-1”的值写入磁盘发生在第二次请求之后，而序列则是在第一次请求之后。

当我请求序列 `SeqINT` 的下一个值时，我得到了 5：

```sql
SELECT NEXT VALUE FOR dbo.SeqINT;
```

当我向 `TINT` 插入新行时，生成的标识是 1002：

```sql
INSERT INTO dbo.TINT OUTPUT inserted.$identity DEFAULT VALUES;
```

在进行测试时，运行以下代码进行清理：

```sql
IF OBJECT_ID('dbo.SeqTINYINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqTINYINT;
IF OBJECT_ID('dbo.SeqSMALLINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqSMALLINT;
IF OBJECT_ID('dbo.SeqINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqINT;
IF OBJECT_ID('dbo.SeqBIGINT') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqBIGINT;
IF OBJECT_ID('dbo.SeqNUMERIC9') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqNUMERIC9;
IF OBJECT_ID('dbo.SeqNUMERIC38') = 'S' IS NOT NULL DROP SEQUENCE dbo.SeqNUMERIC38;
IF OBJECT_ID('dbo.TINYINT') = 'U' IS NOT NULL DROP TABLE dbo.TINYINT;
IF OBJECT_ID('dbo.SMALLINT') = 'U' IS NOT NULL DROP TABLE dbo.SMALLINT;
IF OBJECT_ID('dbo.TINT') = 'U' IS NOT NULL DROP TABLE dbo.TINT;
IF OBJECT_ID('dbo.BIGINT') = 'U' IS NOT NULL DROP TABLE dbo.BIGINT;
IF OBJECT_ID('dbo.NUMERIC9') = 'U' IS NOT NULL DROP TABLE dbo.NUMERIC9;
IF OBJECT_ID('dbo.NUMERIC38') = 'U' IS NOT NULL DROP TABLE dbo.NUMERIC38;
```

## 性能测试准备

接下来，我将描述用于衡量不同缓存值下标识和序列性能的测试。结果令人大开眼界，显示了在数据库用户 `tempdb` 中生成值时存在显著的性能差异，同时标识和序列在日志缓冲区问题上也存在非常有趣的差异。

在准备测试期间，你创建了一个名为 `testdb` 的数据库并将恢复模型设置为简单。你在 `testdb` 和 `tempdb` 中都创建了一个名为 `SeqI` 的序列。以下是处理准备部分的代码：

```sql
IF DB_ID(N'testdb') IS NULL CREATE DATABASE testdb;
ALTER DATABASE testdb SET RECOVERY SIMPLE;

USE testdb;
IF OBJECT_ID(N'dbo.Seq1', 'NSO') IS NOT NULL DROP SEQUENCE dbo.Seq1;
CREATE SEQUENCE dbo.Seq1 AS INT MINVALUE 1;

USE tempdb;
IF OBJECT_ID(N'dbo.Seq1', 'NSO') IS NOT NULL DROP SEQUENCE dbo.Seq1;
CREATE SEQUENCE dbo.Seq1 AS INT MINVALUE 1;
```

实际性能测试通过查询 `TSQL3.dbo.GetNums` 生成 10,000,000 个标识/序列值，并收集有关日志的信息（日志记录数、以兆字节为单位的大小、刷新次数）、持续时间（毫秒）以及归一化持续时间（总持续时间减去未生成标识/序列值的查询持续时间）。日志统计信息和实际工作的收集是在事务中完成的，以防止日志在收集统计信息之前被回收。以下是测试代码：

```sql
-- 要启用 TF 272: DBCC TRACEON(272, -1), 要禁用: DBCC TRACEOFF(272, -1)
SET NOCOUNT ON;

-- tempdb; -- 在 tempdb 中测试
USE testdb; -- 在用户数据库 testdb 中测试
```

```sql
DECLARE @numrecords AS INT, @sizemb AS NUMERIC(12, 2), @logflushes AS INT,
@starttime DATETIME2, @endtime DATETIME2;
```

```sql
CHECKPOINT;
BEGIN TRAN
```

```sql
ALTER SEQUENCE dbo.Seq1 CACHE 50; -- 尝试 CACHE 10, 50, 10000, NO CACHE
IF OBJECT_ID(N'dbo.T', 'NU') IS NOT NULL DROP TABLE dbo.T;
```

```sql
-- 统计前
SELECT @numrecords = COUNT(*), @sizemb = CAST([Log Record Length] AS BIGINT) / 1048576,
@logFlushes = (SELECT cntr_value FROM sys.dm_os_performance_counters
WHERE counter_name = 'Log Flushes/sec'
AND instance_name = 'testdb' -- 在 testdb 中测试
-- AND instance_name = 'tempdb' -- 在 tempdb 中测试
)
FROM sys.fn_dblog(null,null);
```

```sql
SET @starttime = SYSDATETIME();
```

```sql
-- 实际工作
SELECT
 n -- 测试不带对象或标识
 -- NEXT VALUE FOR dbo.Seq1 AS n -- 测试序列
 -- IDENTITY(INT, 1, 1) AS n -- 测试标识
INTO dbo.T
FROM TSQLV3.dbo.GetNums(1, 1000000) AS N
OPTION(MAXDOP 1);
```

```sql
-- 统计后
SET @endtime = SYSDATETIME();

SELECT
COUNT(*) - @numrecords AS records,
SUM(CAST([Log Record Length] AS BIGINT)) / 1048576 - @sizemb AS sizem,
(SELECT cntr_value FROM sys.dm_os_performance_counters
WHERE counter_name = 'Log Flushes/sec'
AND instance_name = 'tempdb' -- 在 tempdb 中测试
-- AND instance_name = 'tempdb' -- 在 tempdb 中测试 (原文重复，保留一处注释)
) - @logflushes AS logflushes,
DATEDIFF(ms, @starttime, @endtime) AS durationms
FROM sys.fn_dblog(null, null);
```



COMMIT TRAN

## CHECKPOINT

可以通过注释和取消注释部分来自定义代码，以便使用不同的数据库、缓存大小和功能进行测试。目前，该代码在 `tempdb` 中测试缓存大小为 50 的序列对象。

| 数据库对象 | 缓存 | 记录数 | 大小(MB) | 日志刷新次数 | 持续时间 | 归一化持续时间(ms) |
| --- | --- | --- | --- | --- | --- | --- |
| tempdb | 无 | 8717 | 0.58334350 | 42 | 4468 | |
| tempdb | 标识 | 6563 | 0.43955993 | 13 | 5996 | 1501 |
| tempdb | 标识 | TF2252 | 0.43945693 | 9 | 9933 | 89465 |
| tempdb | 序列 | 10062 | 0.43938868 | 33 | 4710 | 240 |
| tempdb | 序列 | 10000 | 0.43938868 | 34 | 4889 | 421 |
| tempdb | 序列 | DFT - 50 | 6562 | 0.43938868 | 34 | 6177 | 1709 |
| tempdb | 序列 | 10 | 6562 | 0.43938868 | 48 | 11625 | 7157 |
| testdb | 序列 | 无缓存 | 6562 | 0.43938868 | 34 | 70367 | 65899 |
| testdb | 无 | 29688 | 2.02630168 | - | - | - |
| testdb | 标识 | 32751 | 1.75932121 | 32 | 6013 | 1270 |
| testdb | 标识 | TF2272 | 1002862 | 7.256192789 | 13444 | 103541 | 100598 |
| testdb | 序列 | 13801 | 1.41382026 | 1000 | 5254 | 511 |
| testdb | 序列 | 32759 | 2.02628615 | 10040 | 10489 | 6746 |
| testdb | 序列 | DFT - 50 | 222863 | 15.85624124 | 20002 | 63890 | 63467 |
| testdb | 序列 | 1022872 | 73.83788404 | 92110 | 281290 | 287367 |
| testdb | 序列 | 无缓存 | 10031230 | 72.87642504 | 1000050 | 2812090 | 2 |

结果中有一些有趣的现象可以观察并推断出最佳实践。观察标识和序列，目标对象在 `tempdb` 中，因为 `tempdb` 不会随重启而丢失。你需要观察记录数、总大小和日志刷新次数，因为如果需要执行回滚，那么当缓存大小较小时，持续时间会增加，但这并不是日志记录。你可以发现，特别是在缓存较小的情况下，`tempdb` 的性能明显优于 `testdb`。另一个有趣的观察是，在用户数据库 (`testdb`) 中，相同的缓存值下，标识的记录数和总大小比序列小，但日志刷新次数和实际性能却大不相同。这里有一部分性能结果供你轻松查看：

| 数据库对象 | 缓存 | 记录数 | 大小(MB) | 日志刷新次数 | 持续时间 | 归一化持续时间(ms) |
| --- | --- | --- | --- | --- | --- | --- |
| tempdb | 标识 | DFT | 6563 | 0.4395593 | 13 | 5969 | 1501 |
| tempdb | 序列 | 6562 | 0.43933868 | 34 | 4889 | 421 |
| testdb | 标识 | DFT | 32751 | 2.02631689 | 38 | 6013 | 1270 |
| testdb | 序列 | 32759 | 2.02628615 | 10000 | 10489 | 5746 |
| tempdb | 标识 | TF272 | 6563 | 0.43945693 | 9 | 9333 | 89465 |
| tempdb | 序列 | 无缓存 | 6562 | 0.43933868 | 34 | 70367 | 65899 |
| testdb | 标识 | TF272 | 1002862 | 7.261529784 | 13444 | 105341 | 100598 |
| testdb | 序列 | 无缓存 | 10031030 | 72.8764200 | 1000050 | 2812090 | 280734 |

你还可以在图 6-2 中标识和序列在某些缓存大小下的运行时对比。

![](img/bdc3aa3f6e2987d913ee538147411_417_0.png)

图 6-2 序列和标识性能测试。

很清楚，对于相同的缓存大小，标识和序列的日志记录数和总大小应该是相似的——毕竟它们在内部都是通过相同的对象实现的。那么为什么缓冲区会有差异呢？

这是由于标识是特定于表的，而序列不是。你可以在带有标识的表中插入新行。因此，插入触发了缓存相关的写入。日志记录被写入日志缓冲区，但假设缓冲区尚未满。那么在缓冲区刷新之前就会发生失败。如果恢复的标识值较早则没关系，因为恢复过程也会撤销插入。所以重用未提交插入生成的标识值并不是问题。由于这个原因，SQL Server 不需要为每次标识相关的写入刷新日志缓冲区。

对于序列对象，情况不同。应用程序可以请求序列值并用于任何用途——而不一定存储在数据库的行中。如果 SQL Server 崩溃然后应用程序请求新值，什么来保证不会产生旧值？为了保证这一点，SQL Server 为每次序列相关的写入刷新日志缓冲区。

你可以在数据库性能测试结果中看到序列缓存大小与日志刷新次数之间的相关性。例如，在无缓存的情况下生成 10,000,000 个值，序列大约获得 10,000,000 次刷新，而标识仅获得其一部分（约 13,000）。性能差异是非常巨大的：序列需要近一小时，而标识只需要几分钟。

另一个需要记住的重要点是默认缓存大小以及它们并不保证保持不变。在我测试的版本和生成中，对于 `INT` 类型，标识的默认缓存大小为 50，创建 10,000,000 个值大约需要一分钟。序列对象的默认缓存大小为 50，创建 10,000,000 个值也大约需要一分钟。从一个功能切换到另一个功能时，记住这一点尤为重要。首先，要确保你没有进行测试。其次，考虑使用足够大的式缓存大小以获得类似的性能。

# 总结标识与序列的比较

本章上面的部分将序列对象与标识列属性进行了比较和对比。讨论了许多方面。为了方便参考，信息以表 6-2 的摘要形式提供。

表 6-2 标识与序列的比较

| 特性 | 标识 (Identity) | 序列 (Sequence) |
| --- | --- | --- |
| 于表无关 | 否 | 是 |
| 可以与现有列关联/取消关联 | 否 | 是 |
| 与空列使用 | 否 | 是 |
| 使用前获取值 | 否 | 是 |
| 在 SELECT 中使用 | 否 | |
| * IDENTITY() 函数可以在 SELECT INTO 中使用 | 是 | |
| 控制顺序 | SELECT INTO 中不支持<br>在 INSERT SELECT 中支持 | 是 |
| 在 UPDATE 中使用 | 否 | 是 |
| 定义最小值和最大值 | 否 | 是 |
| 是否可以循环 | 否 | 是 |
| 是否可以更改当前值 | 是 | 是 |
| 是否可以更改增量 | 否 | 是 |
| 支持用户定义的缓存值 | 否，可以通过 TF272 禁用缓存 | 是 |
| 默认缓存值（截至 SQL Server 2014 RTM 和 SQL Server 2012 SP2） | 取决于类型（TINYINT – 10, SMALLINT – 100, INT – 1000, BIGINT 和 NUMERIC – 10000） | 50 |
| 是否受回滚影响 | 否 | 否 |
| 写入磁盘时需要刷新日志 | 否 | 是 |
| 获取值的范围 | 否 | 是 |

## 删除数据

本节涵盖了数据删除的两个方面：`TRUNCATE TABLE` 语句和删除重复项。你可以在第 5 章找到更多关于数据删除的介绍。

## TRUNCATE TABLE

`TRUNCATE TABLE` 语句是一种高效的语句，它可以删除表中的所有行，并在存在标识属性（identity property）时重置它，但保留表定义。

> 该语句具有基本的语法。例如，如果你有一个名为 T1 的表，你可以对其进行截断处理：

```sql
TRUNCATE TABLE dbo.T1;
```

无论数据库的恢复模式如何，`TRUNCATE TABLE` 语句涉及的日志记录远少于 `DELETE` 语句；因此，它的速度快得多。前者只需要记录哪些区（extents）或数据页被释放，以支持回滚和向前恢复能力。而后者则需要记录被删除的每一行。

由于性能上的巨大差异，通常倾向于使用 `TRUNCATE TABLE` 语句而不是 `DELETE` 语句。但除了性能之外，你还应该注意一些区别。

`TRUNCATE TABLE` 语句需要更高级的权限。你至少需要目标表的 `ALTER` 权限。如果你不想向执行语句的用户授予权限，可以将该语句包含在一个使用 `EXECUTE AS` 子句定义的存储过程中，并确保被模拟的用户拥有相应的权限。

如前所述，与 `DELETE` 语句不同，`TRUNCATE TABLE` 语句在存在标识属性时会重置它。如果你想清空表但保持当前的标识值不变，你需要自己处理。你可以按照以下步骤操作：

1. 开启一个事务。
2. 锁定表。
3. 在变量中捕获当前标识值加 1。
4. 执行 `TRUNCATE TABLE` 语句。
5. 使用存储在变量中的值重置标识属性。
6. 提交事务。

我将使用以下示例数据来演示此解决方案：

```sql
IF OBJECT_ID('dbo.T1', 'N') IS NOT NULL DROP TABLE dbo.T1;

GO
```

```sql
CREATE TABLE dbo.T1
(
  keycol INT NOT NULL IDENTITY,
  datacol VARCHAR(10) NOT NULL
);
```

```sql
INSERT INTO dbo.T1 (keycol, datacol) VALUES('A','B'),('C');
```

```sql
SELECT keycol, datacol FROM dbo.T1;
```

这里是上一个查询的输出，显示了表 T1 的内容：

```
keycol  datacol
------  -------
1       A
2       B
3       C
```

当前的标识值为 3。

以下代码将截断表并手动将标识属性重置为当前值 1：

```sql
IF EXISTS(SELECT * FROM dbo.T1)
BEGIN
  TRAN
  DECLARE @tmp INT = (SELECT TOP (1) keycol FROM dbo.T1 WITH (LOCKX)); -- 锁定
  DECLARE @reseed AS INT = IDENTITY_CURRENT('dbo.T1') + 1; -- 保存
  TRUNCATE TABLE dbo.T1; -- 截断
  DBCC CHECKIDENT('dbo.T1', RESEED, @reseed); -- 重置
```

*(注：此处根据上下文，原意应是将标识属性重置为 1，但代码中逻辑是将 `reseed` 赋值为当前值+1，此处保留代码逻辑翻译)*

*(修正：原文代码中 `reseed = IDENTITY_CURRENT('dbo.T1') + 1` 逻辑似乎是获取当前值后的下一个值，但根据翻译要求，保持代码不翻译。)*

重新审视逻辑：

```sql
IF EXISTS(SELECT * FROM dbo.T1)
BEGIN
  TRAN
  DECLARE @tmp INT = (SELECT TOP (1) keycol FROM dbo.T1 WITH (LOCKX)); -- lock
  DECLARE @reseed AS INT = IDENTITY_CURRENT('dbo.T1') + 1; -- save
  TRUNCATE TABLE dbo.T1; -- truncate
  DBCC CHECKIDENT('dbo.T1', RESEED, @reseed); -- reseed
```

*(注：原文提供的代码块似乎不完整，我将严格按照提供的文本内容进行翻译，不进行补全。)*

由于原文提供的文本在结尾处截断，我将基于您提供的片段进行完整翻译。

... (此处省略前面已翻译的译文，直接提供最后一段的翻译)

如果需要删除的行数较少...

例如，10,000 行——使用一个完全记录日志的 `DELETE` 语句是完全正确的。在这种情况下，可以使用以下解决方案来实现该任务：

```sql
WITH C AS
(
  SELECT *,
    ROW_NUMBER() OVER(PARTITION BY orderid ORDER BY (SELECT NULL)) AS n
  FROM dbo.orders
)
DELETE FROM C
WHERE n > 1;
```

内部查询查询了行数（称为 n），该行数按逻辑键（在本例中为 `orderid`）进行分区。只要每个唯一的 `order ID` 只保留一个出现，那么保留哪一行并不重要，因此可以像我们的查询那样，在窗口排序子句中使用任意排序——即 `ORDER BY (SELECT NULL)`。如果具有相同 `order ID` 值的不同行彼此不同，且你有决定优先保留某行的属性，请确保在窗口排序子句中指定这些属性。列 `n` 代表重复的次数。假设你有三行 `order ID` 为 10248 的数据；你将获得唯一值 1、2 和 3。代码根据计算出的查询定义了一个 CTE `C`。外部查询通过该 CTE 删除 `n` 大于 1 的行。底层表 `Orders` 实际上受 `DELETE` 语句影响的表。

如果需要删除的行百分比很小，但行数仍然很大——例如 5,000,000 行——那么前面的解决方案可能并不理想。它可能会导致日志显著膨胀，并可能导致锁升级。为了避免这种情况，你可以像第 5 章“分块修改”节中描述的那样，将大删除拆分为多个块。以下是该方法在我们案例中的实现：

```sql
WHILE 1 = 1
BEGIN
  WITH C AS
  (
    SELECT *,
      ROW_NUMBER() OVER(PARTITION BY orderid ORDER BY (SELECT NULL)) AS n
    FROM dbo.orders
  )
  DELETE TOP (3000) FROM C
  WHERE n > 1;

  IF @ROWCOUNT < 3000 BREAK;
END
```

如果需要删除的行百分比和行数都很大——例如 25,000,000 行——第三种解决方案可能是最优的。你使用最小日志记录的批量 `SELECT INTO` 将 `n` 等于 1 的行复制到临时表中。完成后，删除原始表，将临时表重命名为原始表名，然后在表上创建任何所需的对象（约束、索引、触发器、权限）。以下是实现该方法的代码：

40 第6 章 数据修改

```sql
-- 将唯一行复制到临时表
WITH C AS
(
  SELECT *,
    ROW_NUMBER() OVER(PARTITION BY orderid ORDER BY (SELECT NULL)) AS n
  FROM dbo.Orders
)
SELECT orderid, custid, empid, orderdate, requireddate, shippate, shipper,
  freight, shipname, shipaddress, shipcity, shipregion, shippostalcode, shipcountry
INTO dbo.Orders_Stage
FROM C
WHERE n = 1;
```

```sql
-- 删除原始表
DROP table dbo.Orders;
```

```sql
-- 在 Orders 上创建约束、索引、触发器和权限
ALTER TABLE dbo.Orders ADD CONSTRAINT PK_Orders PRIMARY KEY(orderid);
```

## 更新数据

本节涵盖了 T-SQL 中的两种特殊更新能力：通过表表达式更新数据，以及使用变量更新数据。

作为更新数据章节以及随后合并数据章节的示例数据，我使用了 `Customers` 和 `CustomersStage` 表，你可以使用以下代码在 `tempdb` 中创建并填充这些表：

```sql
USE tempdb;
```

```sql
IF OBJECT_ID('dbo.Customers', 'U') IS NOT NULL DROP table dbo.Customers;
```

```sql
CREATE TABLE dbo.Customers
(
  custid INT NOT NULL,
  companyname VARCHAR(25) NOT NULL,
  phone VARCHAR(20) NOT NULL,
  address VARCHAR(50) NOT NULL,
  CONSTRAINT PK_Customers PRIMARY KEY(custid)
);

GO
```

```sql
INSERT INTO dbo.Customers(custid, companyname, phone, address)
VALUES(1, 'cust 1', '(111) 111-1111', 'address 1'),
```



(2, 'cust 2', '(222) 222-2222', 'address 2'),
(3, 'cust 3', '(333) 333-3333', 'address 3'),
(4, 'cust 4', '(444) 444-4444', 'address 4'),
(5, 'cust 5', '(555) 555-5555', 'address 5');

GO

```sql
IF OBJECT_ID('dbo.CustomersStage', 'U') IS NOT NULL DROP TABLE dbo.CustomersStage;

CREATE TABLE dbo.CustomersStage
(
  custid INT NOT NULL,
  companyname VARCHAR(25) NOT NULL,
  phone VARCHAR(20) NULL,
  address VARCHAR(50) NOT NULL,
  CONSTRAINT PK_CustomersStage PRIMARY KEY(custid)
);

GO
```

```sql
INSERT INTO dbo.CustomersStage(custid, companyname, phone, address)
-- (根据之前的模式的示例数据)
```

为了演示这种方法，请打开两个连接。在连接 1 中运行以下代码以启动事务并请求新键，同时保持事务开启：

```sql
BEGIN TRAN

DECLARE @newval AS INT;

UPDATE dbo.MySequence SET @newval = val += 1;

SELECT @newval;
```

你得到了新的键值 4，但该行仍被排他性锁定。在连接 2 中运行以下代码尝试获取一个新键：

```sql
BEGIN TRAN

DECLARE @newval AS INT;

UPDATE dbo.MySequence SET @newval = val += 1;

SELECT @newval;
```

连接 2 被阻塞了。

回到连接 1，运行以下代码来回滚事务：

```sql
ROLLBACK TRAN
```

表中的值恢复到 3，且锁由连接 1 释放。连接 2 成功获取了它一直在等待的排他性锁，将值从 3 更新为 4，并返回。

在连接 2 中运行以下代码以提交事务：

```sql
COMMIT TRAN
```

现在值更改 4 已经提交，连接 2 释放了对该行的排他性锁，另一个事务就可以请求下一个值。

你可以看到这种解决方案如何利用 SQL Server 更新数据时使用的标准锁定和阻塞机制，确保值值之间不会出现间隙。

## 合并数据

你使用 `MERGE` 语句根据某些源表的数据将其合并到某些目标表中。它可以用于数据仓库场景，以便将数据合并到汇总表、处理缓慢变化的维度等。它也可以用于在线事务处理 (OLTP) 场景，当你的系统并非数据的产生源；相反，你定期从外部源获取数据并需要将其合并到数据库中的某张表中。

T-SQL 基于标准 SQL 实现了 `MERGE` 语句，并带有一个名为 `WHEN NOT MATCHED BY SOURCE` 子句的扩展，它可以处理标准语句无法处理的情况。

为了演示 `MERGE` 语句，我将使用你之前在“更新数据”部分创建的相同的 `Customers` 和 `CustomersStage` 表。

## MERGE 示例

我将通过示例来解释 `MERGE` 语句。我将从该语句支持的基础子句开始。

假设你需要合并源表 `CustomersStage` 中的数据。对于与目标客户匹配的源客户，你希望用源行中更新的信息更新目标行。对于未与目标客户匹配的源客户，你希望将源客户作为新客户行插入到目标。最后，对于未与源客户匹配的目标客户，你希望删除目标行。你通过以下 `MERGE` 语句实现此类任务：

```sql
MERGE INTO dbo.Customers AS TGT
USING dbo.CustomersStage AS SRC
ON TGT.custid = SRC.custid
WHEN MATCHED THEN
  UPDATE SET
    TGT.companyname = SRC.companyname,
    TGT.phone = SRC.phone,
    TGT.address = SRC.address
WHEN NOT MATCHED THEN
  INSERT (custid, companyname, phone, address)
  VALUES (SRC.custid, SRC.companyname, SRC.phone, SRC.address)
WHEN NOT MATCHED BY SOURCE THEN
  DELETE;
```

`MERGE` 子句用于定义目标表，并可选地为其指定别名。在我们的案例中，目标是 `Customers` 表，别名为 `TGT`。

`USING` 子句用于定义合并的源并可选地为其指定别名。在我们的案例中，源是 `CustomersStage` 表，别名为 `SRC`。`USING` 子句的一个有趣之处是，它的设计类似于 `SELECT` 语句中的 `FROM` 子句。你并不限于仅查询表作为源；相反，可以使用表操作符、表表达式和表函数等源。稍后我将详细介绍这种能力。

`MERGE` 语句中下一个定义部分是 `ON` 谓词。合并谓词的目的是判断源行是否与目标行匹配，以及目标行是否与源行匹配。对于我们来说，做出这种判断是直观的，但 `MERGE` 语句并不要求源表和目标定义键才能工作。在我们的案例中，合并谓词是 `TGT.custid = SRC.custid`。

确定源并定义合并谓词后，剩余子句定义了在不同情况下对目标执行的操作（INSERT、UPDATE 或 DELETE）。通过使用 `WHEN MATCHED` 子句，你定义了当源行与目标行匹配时做什么。根据我们的示例数据（客户 2、3 和 5），当出现匹配项时，你可以对目标行采取的两种可能操作：`UPDATE` 和 `DELETE`。如果你考虑一下，`INSERT` 操作在这里是没有意义的，因为目标行已经存在。事实上，`MERGE` 语句在这种情况下不支持 `INSERT` 操作。在我们的 `MERGE` 语句中，该子句执行的操作是 `UPDATE`；你用源行中最新的信息更新目标行。

与基于连接的 `UPDATE` 语句不同，如果 `MERGE` 语句检测到多行匹配你的目标，它会生成错误。在这种情况下，`UPDATE` 语句仅执行非确定性更新；即将使用源行之一来更新目标。`MERGE` 语句在这种情况下更为健壮，可以保护你免受 Bug 的影响。你只需要确保只有一个源行匹配目标。你可以通过 `WHEN NOT MATCHED BY SOURCE` 子句实现这一点：

```sql
WHEN NOT MATCHED BY SOURCE
UPDATE SET TGT.isdeleted = 1
```

集合操作符（set operators）的特点是，在比较行时，它们隐式地使用 `distinct` 谓词，而不是不同于 (`<>`) 运算符。当检查一个非 `NULL` 值是否与另一个不同时，结果为 `true`。当检查 `NULL` 是否与非 `NULL` 不同时，结果为 `unknown`。这使得使用集合操作符比较行变得简单得多，你不需要对 `NULL` 进行特殊处理。当然，这里的假设是两张表的结构是相同的。如果结构不同，你可以始终定义视图来获取兼容的结构，并将视图作为 `MERGE` 语句的源。

如果 T-SQL 支持标准的 `distinct` 谓词，那么表达 `NULL` 与非 `NULL` 不同、`NULL` 与 `NULL` 相同的条件将会变得更简单。你可以在这里找到关于 SQL Server 支持 `distinct` 谓词的请求：https://connect.microsoft.com/SqlServer/feedback/details/286422。

## 防止 MERGE 冲突

当多个 `MERGE` 语句处理重叠键并并发执行时，它们可能会遇到导致主键冲突的冲突。这是因为默认的“已提交”（Read Committed）隔离级别，你无法保证在整个事务期间数据的访问是序列化的。可能会出现两个或多个语句同时检查某个键是否存在并得到 `false` 的情况；它们都尝试插入具有相同键的新行。其中一个将成功，而其余的将因主键冲突而失败。

例如，考虑以下名为 `AddCustomer` 的存储过程：

```sql
IF OBJECT_ID(N'dbo.AddCustomer',N'P') IS NOT NULL DROP PROC dbo.AddCustomer;

GO

CREATE PROC dbo.AddCustomer
@custid INT, @companyname VARCHAR(25), @phone VARCHAR(20), @address VARCHAR(50)
AS
MERGE dbo.Customers AS /* WITH (SERIALIZABLE) */ AS TGT
USING VALUES(@custid, @companyname, @phone, @address)
AS SRC(@custid, @companyname, phone, address)
ON TGT.custid = SRC.custid
WHEN MATCHED THEN
    UPDATE SET
        TGT.companyname = SRC.companyname,
        TGT.phone = SRC.phone,
        TGT.address = SRC.address
WHEN NOT MATCHED THEN
    INSERT (custid, companyname, phone, address)
    VALUES (SRC.custid, SRC.companyname, SRC.phone, SRC.address)

GO
```

该存储过程接受客户信息作为输入。如果客户已存在，它用新信息更新现有客户；否则，它添加一个新客户。多个会话使用相同的客户 ID 并执行该存储过程，且该客户不存在，一个将成功，其他将获得主键冲突。为了演示这一点，请从多个会话运行以下代码：

```sql
SET NOCOUNT ON;

USE tempdb;

WHILE 1 = 1
BEGIN
    DECLARE @curcustid INT AS CHECKSUM(CAST(SYSDATETIME AS DATETIME(2)));
    EXEC dbo.AddCustomer @custid = @curid, @companyname = 'A', @phone = 'B', @address = 'C';
END;
```

迭代几次后，你将开始收到如下的主键冲突：

Msg 2627, Level 14, State 1, Procedure AddCustomer, Line 5
Violation of PRIMARY KEY constraint 'PK_Customers'. Cannot insert duplicate key in object dbo.Customers'. The duplicate key value is (177624945).

为了避免冲突，你需要在整个事务期间对数据的访问序列化。为了实现这一点，请使用 `SERIALIZABLE` 隔离级别。在我们的存储过程中，删除 `MERGE INTO` 子句中表名后的块分隔符，以表提示指定 `SERIALIZABLE` 隔离级别。你也可以使用 `HOLDLOCK` 提示，它是等效的。然后你可以再次尝试测试，你会发现你不再遇到任何主键冲突错误了。

## ON 并不是过滤器

将 `MERGE ON` 谓词视为过滤器是一个常见的错误，并会导致 Bug。`ON` 谓词定义了源行是否被目标行匹配，然后根据条件将行引导到右侧子句以执行相应的操作。例如，你只需要将客户 ID 为 2 的源行合并到目标，如果客户存在则更新现有行，如果不存在则插入新行。如果（错误地）将 `ON` 谓词视为过滤器，你将写出以下 `MERGE` 语句：

```sql
MERGE INTO dbo.Customers AS TGT
USING dbo.CustomersStage AS SRC
ON TGT.custid = SRC.custid
AND SRC.custid = 2
WHEN MATCHED THEN
    UPDATE SET
        TGT.companyname = SRC.companyname,
        TGT.phone = SRC.phone,
        TGT.address = SRC.address
WHEN NOT MATCHED
    INSERT (custid, companyname, phone, address)
    VALUES (SRC.custid, SRC.companyname, SRC.phone, SRC.address);
```

实践中发生的情况是，对于所有客户 ID 不为 2 的源行，`ON` 谓词求值为 `false`；在这种情况下，行被引导到 `WHEN NOT MATCHED` 子句，导致插入操作。该语句并没有忽略除 2 之外的所有源客户，而是为它们执行了插入操作。如果这些客户 ID 中的任何一个存在于目标中，你将得到主键冲突。糟糕糟糕，如果已经存在，你仍会将它们插入到目标中，尽管你本不应该这样做。例如，当我运行此语句时，我遇到了与客户 3 相关的主键冲突：

Msg 2627, Level 14, State 1, Line 805
Violation of PRIMARY KEY constraint 'PK_Customers'. Cannot insert duplicate key in object 'dbo.Customers'. The duplicate key value is (3).
The statement has been terminated.

正确的解决方案是提供一个表表达式，其中过滤出客户 ID 为 2 的源行，并将该表表达式作为 `MERGE` 语句的源，如下：

```sql
MERGE INTO dbo.Customers AS TGT
USING (SELECT * FROM dbo.CustomersStage WHERE custid = 2) AS SRC
ON TGT.custid = SRC.custid
WHEN MATCHED THEN
  UPDATE SET
    TGT.companyname = SRC.companyname,
    TGT.phone = SRC.phone,
    TGT.address = SRC.address
WHEN NOT MATCHED THEN
  INSERT (custid, companyname, phone, address)
  VALUES (SRC.custid, SRC.companyname, SRC.phone, SRC.address);
```

## 向表中插入数据的 INSERT 示例

假设你对一个标识列（identity column）进行多行插入，并且需要获取新生成的标识值供后续使用。SQL Server 提供了 `SCOPE_IDENTITY` 函数来获取当前会话中生成的最后一个标识值，但它没有提供用于捕获多个生成的标识值的工具。解决方案是使用 `OUTPUT` 子句。

为了演示这一点，首先运行以下代码，它将创建一个名为 `T1` 带有标识列的表：

```sql
USE tempdb;

IF OBJECT_ID(N'dbo.T1', 'N'U') IS NOT NULL DROP TABLE dbo.T1;

CREATE TABLE dbo.T1
(
  keycol INT NOT NULL IDENTITY(1, 1) CONSTRAINT PK_T1 PRIMARY KEY,
  datacol VARCHAR(40) NOT NULL
);
```

以下 `INSERT` 语句从 `TSQLV3.HR.Employees` 表复制五个值到 `T1` 表，导致生成了五个值：

使用 `OUTPUT` 子句，该语句将返回新生成的标识值以及来自插入行的其他信息。注意使用泛化形式 `identity` 对标识列进行引用。SQL Server 支持这种泛化形式，是因为每个表只允许一个标识列。当然，也可以直接引用插入的原始列名 `inserted.keycol`。

此代码生成以下输出：

| keycol | datacol |
|---|---|
| 1 | Davis |
| 2 | Funk |
| 3 | Lew |
| 4 | Peled |
| 5 | Cameron |

要将输出行重定向到表变量供后续使用，请添加 `INTO` 子句。为了演示这一点，首先截空 `T1` 表：

```sql
TRUNCATE TABLE dbo.T1;
```

并在之前的示例基础上添加表变量的声明和 `INTO` 子句，如下所示：

```sql
DECLARE @NewRows TABLE(keycol INT, datacol VARCHAR(40));

INSERT INTO dbo.T1(datacol)
OUTPUT inserted.identity, inserted.datacol
INTO @NewRows(keycol, datacol)
SELECT keycol, lastname
FROM TSQLV3.HR.Employees
WHERE country = 'USA';

SELECT keycol, datacol FROM @NewRows;
```



你将获得如下输出，显示表变量的内容：

| keycol | datacol |
|---|---|
| 1 | Davis |
| 2 | Funk |
| 3 | Lew |
| 4 | Peled |
| 5 | Cameron |

## 删除数据的示例

为了更好地理解配合 `DELETE` 语句的 `OUTPUT` 子句，考虑一个涉及删除的任务，并要求同时归档你正在删除的行。可以通过 `DELETE` 语句中的 `OUTPUT` 子句来实现删除。

为了演示这一点，首先运行以下代码，它在 `tempdb` 中创建一个带有示例数据的 `Orders` 表，同时在名为 `Archive` 的数据库中创建一个 `Orders` 表以吸收归档的订单：

```sql
IF DB_ID('Archive') IS NULL CREATE DATABASE Archive;

GO

USE Archive;

IF OBJECT_ID(N'dbo.Orders', N'U') IS NOT NULL DROP dbo.Orders;

SELECT ISNULL(orderid, 0) AS orderdate, orderdate, empid, custid
INTO dbo.Orders
FROM TSQLV3.Sales.Orders WHERE 1 = 2;

ALTER TABLE dbo.Orders ADD CONSTRAINT PK_Orders PRIMARY KEY(orderid);

USE tempdb;

IF OBJECT_ID(N'dbo.Orders', N'U') IS NOT NULL DROP dbo.Orders;

SELECT orderid, orderdate, empid, custid INTO dbo.Orders FROM TSQLV3.Sales.Orders;

ALTER TABLE dbo.Orders ADD CONSTRAINT PK_Orders PRIMARY KEY(orderid);

-- Before delete
SELECT orderid, orderdate, empid, custid FROM dbo.Orders;
SELECT orderid, orderdate, empid, custid FROM Archive.dbo.Orders;
```

最后两个查询显示了删除前活动和归档 `Orders` 表的内容。

假设你需要删除 `tempdb` 中活动 `Orders` 表中 2014 年之前的订单，并将删除的订单归档到 `Archive` 数据库的 `Orders` 表中。你可以使用 `OUTPUT` 子句来实现，如下所示：

如果需要删除的行数很多，可以使用早期演示的分批修改技术，只是这次增加了 `OUTPUT INTO` 子句，如下所示：

```sql
WHILE 1 = 1
BEGIN
    DELETE TOP (3000) FROM dbo.Orders
    OUTPUT
        deleted.orderid,
        deleted.orderdate,
        deleted.empid,
        deleted.custid
    INTO Archive.dbo.Orders
    WHERE orderdate < '20140101';
    IF @@ROWCOUNT < 3000 BREAK;
END
```

运行以下查询显示删除后活动和归档 `Orders` 表的内容：

```sql
SELECT orderid, orderdate, empid, custid FROM dbo.Orders;
SELECT orderid, orderdate, empid, custid FROM Archive.dbo.Orders;
```

## MERGE 语句示例

使用 `MERGE` 语句时，你会面临其他语句不具备的复杂性：如何知道哪个操作影响了每个输出行？为此，SQL Server 提供了 `$Action` 函数，它返回包含 'INSERT'、'UPDATE' 或 'DELETE' 操作的字符串。

为了演示使用此函数，首先运行以下代码为 `Customers` 和 `CustomersStage` 表填充新的示例数据：

```sql
TRUNCATE TABLE dbo.Customers;
TRUNCATE TABLE dbo.CustomersStage;
```

```sql
INSERT dbo.Customers(custid, companyname, address)
SELECT custid, lastname, address
FROM TSQLV3.HR.Employees
WHERE country = 'USA';
```

## 可组合 DML

假设你需要修改某些表中的行，并将修改后的行的输出信息写入某些目标表。通常情况下，你简单地使用 `OUTPUT INTO` 子句。但你只需要捕捉输出行的子集——而不是所有行。例如，假设你想删除 `tempdb` 数据库中 `Orders` 表中所有 2014 年之前创建的订单行。你需要将 `Archive` 数据库中 `Orders` 表中的被删除行进行归档，但仅针对客户 11 和 42。你不需要将整组输出行写入临时阶段，然后仅从该阶段复制子集，因为这可能意味着大量不必要的工作。

T-SQL 查询可以在 `INSERT` 语句中嵌套带有 `OUTPUT` 子句的 DML 语句——这种功能在某些平台被称为可组合 DML。通过此功能，你可以在无需中间阶段的情况下完成上述删除任务，如下所示：

```sql
INSERT INTO Archive.dbo.Orders (orderid, orderdate, empid, custid)
SELECT orderid, orderdate, empid, custid
FROM ( DELETE FROM dbo.Orders
       OUTPUT deleted.orderid,
              deleted.orderdate,
              deleted.empid,
              deleted.custid
       WHERE orderdate < '20140101' ) AS D
WHERE custid IN (11, 42);
```

可组合 DML 也适用于处理数据仓库中的缓慢变化维度（SCD）2 型。你可以基于一个 `MERGE` 语句定义派生表，该语句包含一个调用 `$Action` 函数的 `OUTPUT` 子句。然后在查询中，你可以过滤已更新的输出行（操作为 'UPDATE'），并将它们作为行的新版本插入表中。

可组合 DML 目前在 T-SQL 中以有限的形式实现。你只能在 `INSERT SELECT` 语句中使用此功能。你可以指定 `WHERE` 过滤器，但不能应用任何进一步的操作（如连接或其他操作符、分组等）。

最后，该功能具有与 `OUTPUT` 子句相似的限制。该表可以是永久表、临时表或表变量。目标表不能是具有触发器的表表达式（如视图），也不能参与了主键-外键关系的表。

## 结论

本章涵盖了与数据修改相关的多个主题。它描述了 SQL Server 支持的一些批量导入工具，以及它们为了以最小日志进行处理而需要满足的条件。它涵盖了序列对象，并将其与 `identity` 列属性进行了对比分析，这提供了重要的性能考量。本章涵盖了删除和更新任务。还提供了一些关于正确使用 `MERGE` 语句并避免可能陷阱的提示。最后，本章涵盖了 `OUTPUT` 子句，描述了该功能的实际用例。

## 处理日期和时间

处理日期和时间是任何层级接触 T-SQL 的人员都需要熟练掌握的关键主题之一。这是因为你存储在数据库中的几乎每条数据都与某种日期和时间元素有关。你有许多需要注意的陷阱，这些陷阱会导致代码出现错误且性能低下。

本章首先介绍 Microsoft SQL Server 支持的日期和时间类型，然后涵盖了操作这些类型输入的内建函数。接着，在处理日期和时间数据时为你提供最佳实践建议。最后，本章涵盖了日期和时间查询任务、这些任务的某些常用解决方案的低效之处，以及具有创意且高效的解决方案。

## 日期和时间类型

编写此时，最新版本的 SQL Server（SQL Server 2014）支持六种日期和时间类型。`DATETIME` 和 `SMALLDATETIME` 是该产品的长期特性。其余类型——`DATE`、`TIME`、`DATETIME2` 和 `DATETIMEOFFSET` 是 SQL Server 2008 引入的后续新增。表 7-1 提供了支持的日期和时间类型的规范。

选择类型的原则是：在日期范围、精度、功能和 API 支持方面涵盖你需求的最小类型。类型越小，占用的存储越少。对于大表，这种节省会累积，导致处理查询时的读取次数减少，从而加快查询速度。

较老的类型 `DATETIME` 和 `SMALLDATETIME` 仍然被广泛使用，尤其是前者。这主要是由于遗留数据、代码和习惯。除非有充分的理由，否则人们通常不会急于更改列类型以及涉及的复杂性。当你需要同时存储日期和时间且不需要比分钟更细的时间时，`SMALLDATETIME` 仍然是最经济的选择。

在支持的日期范围内，对于 `DATE`、`DATETIME2` 和 `DATETIMEOFFSET` 类型，SQL Server 使用的是推测格列哥历（proleptic Gregorian calendar）。该历法扩展了对 1582 年引入的格列哥历之前的日期的支持。更多详细信息，请参阅 http://en.wikipedia.org/wiki/Proleptic_Gregorian_calendar。

### 表 7-1 日期和时间数据类型

| 数据类型 | 存储（字节） | 日期范围 | 精度 | 推荐的输入格式和示例 |
|---|---|---|---|---|
| DATETIME | 8 | 1753 年1 月 1 日至 9999 年 12 月 31 日 | 3 1/3 毫秒 | YYYYMMDD hh:mm:ss.nnn '20090212 12:00:00.000' |
| SMALLDATETIME | 4 | 1900 年1 月 1 日至 2079 年 6 月 30 日 | 1 分钟 | YYYYMMDD hh:mm '20090212 12:00' |
| DATE | 3 | 0001 年1 月 1 日至 9999 年 12 月 31 日 | 1 天 | YYYYMMDD '20090212' |
| TIME(p) | 3 到 5 | | 100 纳秒 | hh:mm:ss.nnnnnn '12:30:00.000000' |
| DATETIME2(p) | 6 到 8 | 0001 年1 月 1 日至 9999 年 12 月 31 日 | 100 纳秒 | YYYY-MM-DD hh:mm:ss.nnnnnn '2009-02-12 12:30:00.000000' |
| DATETIMEOFFSET(p) | 8 到 10 | 0001 年1 月 1 日至 9999 年 12 月 31 日 | 100 纳秒 | YYYY-MM-DD hh:mm:ss.nnnnnn[+-]hh:mm '2009-02-12 12:30:00.000000+02:00' |

如果你需要分离日期和时间，应该分别使用 `DATE` 和 `TIME`。存储纯日期信息更为常见，如订单日期、发货日期、发票日期等。`DATE` 类型是此类信息的经济选择。如果你需要存储纯时间信息，如营业开结束时间，`TIME` 类型是最经济的选择。

处理 `DATETIME` 类型的一个棘手之处在于其有限且奇怪的 3 1/3 毫秒精度（会舍入到最近的刻度，例如 0、3、7、10、13、17 等）。如果这种精度不能满足你的需求，你将需要使用其他类型。例如，`DATETIME2` 支持高达 100 纳秒的精度。此外，该类型的舍入精度可能会产生问题，我稍后将在“舍入问题”部分描述。

`TIME`、`DATETIME2` 和 `DATETIMEOFFSET` 都支持高达 100 纳秒的精度。如果你不需要如此精细的精度，可以在括号中指定以秒为单位的分数。0 表示秒精度，7（默认）表示 100 纳秒精度。确保显式指定你所需的最低精度，因为这可以每个值节省两个字节的存储。例如，`DATETIME2(3)` 提供毫秒精度和 7 字节存储，而不是最大的 8 字节。

作为 `DATETIMEOFFSET`，它在 100 纳秒精度范围内与 `DATETIME2` 相似。此外，它存储了相对于 UTC 的偏移量。这是唯一能够捕捉值采集时和地的真实含义的类型。对于所有其他类型，为了确定值的真实含义，你需要额外记录作为时区和夏令状态的信息。尽管 `DATETIMEOFFSET` 类型没有存储实际的时间和夏令时间，但存储的值考虑了这些因素。例如，假设你需要存储 2015 年 11 月 1 日凌晨 12:30 的太平洋夏令时间（PDT）。太平洋时区（PTZ）从太平洋夏令时间（PDT）切换到太平洋标准时间 (PST)，此时时钟回拨到上午10:00。2015年11月1日凌晨1:30的 PDT距离UTC偏移量为-7小时，此时对应的UTC时间为2015年11月1日上午8:30。一小时后，2015年11月1日凌晨1:30的 PST距离UTC偏移量为-8小时，此时对应的UTC时间为2015年11月1日上午9:30。通过`DATETIMEOFFSET` 类型，你可以正确地捕获PTZ中的日期和时间值，格式如‘20151101 01:00:00.0000000-07:00’和‘20151101 01:30:00.0000000-08:00’。你还可以使用`SYSDATETIMEOFFSET` 值获取当前的日期和时间（稍后你将读到更多关于日期和时间函数的内容）。假设你在2015年从PDT切换到PST的前几秒和几秒后运行了代码：

```sql
SELECT SYSDATETIMEOFFSET();
```

我实际上将我的电脑时钟改到了切换前的几秒，然后在切换前和后分别运行了代码。切换后，我得到了以下输出：

```
2015-11-01 01:59:43.888709 -07:00
```

如你所见，日期和时间值的真实含义被正确捕获了。

如所述，如果你将值存储在其他类型（如`DATETIME2`）中，你需要额外的信息来捕获该值的真实含义。

有些人希望在产品中看到更多与时区相关的功能，例如捕获时区名称、夏令时间日期等。

SQL Server支持的日期和时间函数不支持闰秒。闰秒是一种偶尔应用于UTC的一秒钟调整，以保持其与平均时间（即根据太阳在空中位置所计算的时间）一致。该调整补偿了由于地球自转不规则导致的平均太阳时与原子时间的漂移。例如，在2012年6月30日，UTC在当天的最后一分钟插入了一个闰秒，因此到午夜，当天的最后一秒是23:59:60。同样，UTC也引入了负闰秒的概念，即当天的最后一秒之后是午夜。SQL Server中的日期和时间函数忽略了闰秒的概念。因此，你无法将日期和时间值表示为‘20120630 23:59:60’，也无法通过`DATEADD`和`DATEDIFF`等函数考虑闰秒。

像`SYSDATETIME`这类返回当前日期和时间的函数基于Microsoft Windows时间返回值，而Windows时间也忽略闰秒。Windows时间服务接收来自时间服务器的包含闰秒的数据包，但如果它检测到闰秒，不会在当天的最后一分钟增加或删除一秒；而是在下一次时间同步中，解决本地电脑时钟与正确时间之间产生的单次差异。这与由于任何其他原因（电脑内部时钟频率不准确）而修正电脑时钟与正确时间之间的差异非常相似。如果时间差很小，本地时钟将逐渐调整以使其趋向于正确时间；如果时间差较大，则立即调整。如果你在计算中需要考虑闰秒（例如，如果你想确定两个UTC日期时间值之间的秒数差），那么你需要在计算时维护一个闰秒表。

假设在 2015 年 5 月 5 日中午在一个配置为太平洋时间（Pacific Time Zone）的系统中运行了此代码。你的输出将如下所示：

```
currentdatetimeoffset          currentrentzoffset currentdst
------------------------------------------------------------
2015-05-05 12:00:00.0000000 -07:00 -420      1
```

如果你正在寻找一种支持的获取当前夏令时状态的方法，可以使用 CLR 函数。将 `IsDaylightSavingTime` 方法应用于 `DateTime` 类的 `Now` 属性并返回其结果。（`DateTime.Now` 返回一个设置为此台计算机当前日期和时间的 `DateTime` 对象。）以下是此类名为 `IsDST` 的函数 CLR 代码：

```csharp
using System;
using System.Data.SqlTypes;
using Microsoft.SqlServer.Server;

public partial class TimeZone
{
    [SqlFunction(IsDeterministic = false, DataAccess = DataAccessKind.None)]
    public static SqlBoolean IsDST()
    {
        return DateTime.Now.IsDaylightSavingTime();
    }
}
```

如果你不熟悉开发和部署 CLR 代码，请参见第 9 章“可编程对象”以获取详情。

假设你有一个名为 `C:\Temp\TimeZone\TimeZone\Debug\TimeZone.dll` 包含该程序集的 dll 文件，使用以下代码在 SQL Server 中部署它：

```sql
USE SQLV3;
EXEC sys.sp_configure 'CLR Enabled', 1;
RECONFIGURE WITH OVERRIDE;
IF OBJECT_ID(N'dbo.IsDST', N'FS') IS NOT NULL DROP FUNCTION dbo.IsDST;
```



## 部署与测试

```sql
IF EXISTS(SELECT * FROM sys.assemblies WHERE name = 'TimeZone') DROP ASSEMBLY TimeZone;

CREATE ASSEMBLY TimeZone FROM 'C:\Temp\TimeZone\Debug\TimeZone.dll';

GO

CREATE FUNCTION dbo.IsDST RETURNS BIT EXTERNAL Name TimeZone.IsDST;
```

一旦部署了函数，运行以下代码进行测试：

```sql
SELECT
    SYSDATETIMEOFFSET() AS datetimeoffset,
    DATEPART(TZoffset, SYSDATETIMEOFFSET()) AS currenttzoffset,
    dbo.IsDST() AS currentdst
```

假设你在 2015 年 5 月 5 日运行代码，且你的系统时区配置为标准时间，你将得到以下输出：

| currentdatetimeoffset | currenttzoffset | currentdst |
|---|---|---|
| 2015-05-05 12:00:00.0000000 | -07:00 | 1 |

> **注意**：如果你手动将系统时区更改为具有不同夏令时状态的时区（例如，从太平洋时间更改为协调世界时），函数可能因为旧值的缓存而不会返回正确的夏令时状态。执行以下任何操作都将刷新缓存值：调用 `System.Globalization.CultureInfo.CurrentCulture.ClearCachedData()` 方法、删除并重建系统，以及重置 SQL Server 实例。

## 日期时间函数

`DAY`、`MONTH` 和 `YEAR` 是 `DATEPART` 函数用于提取输入值正确部分的某些缩写。以下是使用这些函数的示例：

```sql
SELECT
    DAY('201502012') AS tday,
    MONTH('201502012') AS month,
    YEAR('201502012') AS they;
```

`DATENAME` 从输入值中提取部分名称，并以字符字符串的形式返回。对于某些部分，该函数取决于语言。例如，当有效语言为 `us_english` 时，表达式 `DATENAME(month, '201502012')` 返回 `February`；当语言为意大利语时，返回 `febbraio`。

`ISDATE` 接受一个输入字符字符串并指示其是否可以转换为 `DATETIME` 类型。如果由于某种原因，你需要在表的字符列中存储日期和时间值，可以在 `CHECK` 约束中使用 `ISDATE` 函数来仅允许有效值。以下示例验证了两个输入值：

```sql
SELECT
    ISDATE('201502012') AS isdate201502012,
    ISDATE('201502030') AS isdate201502030;
```

此代码生成以下输出，显示第一个表示有效日期，而第二个不是：

```
isdate201502012 isdate201502030
--------------------
0
```

你使用 `SWITCHOFFSET` 函数将输入 `DATETIMEOFFSET` 值的偏移切换到所需的偏移量。例如，该代码返回了 -05:00 和 -08:00 偏移的当前日期和时间值，这些值是根据系统活动偏移对当前日期时间值进行调整的：

```sql
SELECT
    SWITCHOFFSET(SYSDATETIMEOFFSET(), '-05:00') AS [now as -05:00],
    SWITCHOFFSET(SYSDATETIMEOFFSET(), '-08:00') AS [now as -08:00];
```

例如，如果输入值的偏移为 +02:00，返回偏移 –05:00 的值，函数将从本地时间减去小时数。

`DATETIMEOFFSET` 函数帮助你使用本地日期时间值以及你提供的偏移作为输入来构造 `DATETIMEOFFSET` 值。将其想为使用本地日期时间值和作为输入的偏移量来构建 `DATETIMEOFFSET` 值。

## 高精度差值计算

与此同时，你可能不得不求助于你那些笨拙且复杂的替代方案，例如下面的 `DATEDIFF_NS100` 内联表值函数 (TVF)：

```sql
USE TSQL3;
```

```sql
IF OBJECT_ID(N'dbo.DATEDIFF_NS100', N'IF') IS NOT NULL
    DROP FUNCTION dbo.DATEDIFF_NS100;
GO

CREATE FUNCTION dbo.DATEDIFF_NS100(@dt1 AS DATETIME, @dt2 AS DATETIME) RETURNS TABLE
AS
RETURN
SELECT
    CAST(864000000000 AS BIGINT) * (ddiff - subdd) + ns100diff AS ns100
FROM (VALUES(@dt1 AS TIME), @dt2 AS TIME),
    DATEDIFF(dd, @dt1, @dt2) AS D(t1, ddiff)
CROSS APPLY (VALUES(CASE WHEN t1 > t2 THEN 1 ELSE 0 END)) AS A1(subdd)
CROSS APPLY (VALUES(CAST(864000000000 AS BIGINT) * subdd
+ (CAST(1000000000 AS BIGINT) * DATEDIFF(ss, '00', t2) + DATEPART(ns, t2)/100)
+ (CAST(1000000000 AS BIGINT) * DATEDIFF(ss, '00', t1) + DATEPART(ns, t1)/100))) AS A2(ns100diff);
```

该函数将计算分为按天、天内的秒以及纳秒的差值——将每个差值转换为相应的100 纳秒倍数。使用内联 TVF 而不是标量函数是出于性能考虑。我将在第 9 章的“用户定义函数”节中解释这一点。

使用以下代码测试该函数：

```sql
SELECT ns100
FROM dbo.DATEDIFF_NS100('20150212 00:00:00.0000001', '20160212 00:00:00.0000000');
```

你将得到输出 3153599999999999。

有时你需要的不仅仅是计算某一部分的差值，而是从低精度的部分到高精度部分进行汇总。假设你想将'20150212 00:00:00.0000001'和'20160212 00:00:00.0000000'之间的差值表示为 11 个月、30 天、23 小时、59 分钟、59 秒和 999999999 纳秒。你可以使用内联 TVF `DATEDIFFPARTS` 实现这一点：

```sql
IF OBJECT_ID(N'dbo.DATEDIFFPARTS', N'IF') IS NOT NULL DROP FUNCTION dbo.DATEDIFFPARTS;
GO

CREATE FUNCTION dbo.DATEDIFFPARTS(@dt1 AS DATETIME, @dt2 AS DATETIME) RETURNS TABLE
/* 只要 @dt2 > @dt1，该函数即可正常工作 */
AS
RETURN
SELECT
    yydiff - subyy AS yy,
    mmdiff - submm % 12 AS mm,
    DATEDIFF(day, mm, mdiff - submm, dt1, dt2) - subdd AS dd,
    nsdiff / CAST(3600000000000 AS BIGINT) % 60 AS hh,
    nsdiff / CAST(0000000000 AS BIGINT) % 60 AS mi,
    nsdiff / 1000000000 % 60 AS ss,
    sdiff % 1000000000 AS ns
FROM VALUES(@dt1, @dt2),
  CAST(@dt1 TIME), CAST(@dt2 TIME),
  DATEDIFF(yy, @dt1, @dt2),
  DATEDIFF(mm, @dt1, @dt2),
  DATEDIFF(dd, @dt1, @dt2)
)
AS D0(dt1, dt2, ydiff, mdiff, ddiff)
CROSS APPLY (VALUES
  CASE WHEN DATEDIFF(yy, ydiff, dt1) > dt2 THEN 1 ELSE 0 END,
  CASE WHEN DATEDIFF(mm, mdiff, dt1) > dt2 THEN 1 ELSE 0 END,
  CASE WHEN DATEDIFF(dd, ddiff, dt1) > dt2 THEN 1 ELSE 0 END
)
AS A1(subby, sumbm, sumbd)
CROSS APPLY (CAST(0000000000 AS BIGINT) *
  + CAST(1000000000 AS BIGINT) * DATEDIFF(ss, '00:00', t2) + DATEPART(ns, t2))
  - CAST(1000000000 AS BIGINT) * DATEDIFF(ss, '00:00', t1) + DATEPART(ns, t1))
AS A2(nsdiff);
```

你调用的函数返回剩余的月份和天差值，作为 yy、mm 和 dd。这些值考虑了当源部分超过目标值时需要减去的情况，这在计算源与目标之间剩余部分（小时、分钟、秒和纳秒）的差值时是必要的。运行以下代码进行测试：

```sql
SELECT yy, mm, dd, hh, ss, ns
FROM DATEDIFFPARTS('20150212 00:00:00.0000001', '20160212 00:00:00.0000000');
```

你将得到如下输出：

```
mm dd hh ss ns
11 30 23 59 59 999999999
```

> **注意**：`DATEDIFF` 函数忽略了输入中较低的部分。作为一个示例，我之前解释过可以使用 `DATEDIFFPARTS` 函数来计算更精确的差值，这样你就可以假设 `@dt2 >= @dt1` 或者通过其他方式强制执行这一点。

## TRY 转换函数

函数（`TRY_CONVERT`、`TRY_CAST` 和 `TRY_PARSE`）。这些函数在转换失败时仅简单地返回 NULL。

例如，以下代码尝试将一个字符字符串转换为 `DATE`：

```sql
SELECT TRY_CONVERT(DATE, '20150212', 112) AS try1, TRY_CONVERT(DATE, '201502030', 112) AS try2;
```

第一次转换成功了，但第二次没有成功。这段代码不会报错，而是返回以下输出：

```
try1        try2
2015-02-12  NULL
```

`TRY_` 系列函数的行为似乎与它们的原始函数相似。

## FORMAT 函数与性能

你使用 `FORMAT` 函数根据 .NET 格式字符串将输入值转换为字符字符串，可以选择地指定 .NET 区域名称。与 `PARSE` 一样，它也会在后台运行且性能很差，稍后我将对此进行演示。例如，以下代码使用英语和英国文化将当前日期和时间值格式化为短格式（`'d'`）：

```sql
SELECT
    FORMAT(SYSDATETIME(), 'd', 'en-US') AS [US English],
    FORMAT(SYSDATETIME(), 'd', 'en-GB') AS [British];
```

假设你在 2015 年 5 月 8 日运行这段代码，你将得到以下输出：

```
US English  British
5/8/2015    08/05/2015
```

这是一个使用显式格式 `'MM/dd/yyyy'` 格式化当前日期时间的示例：

```sql
SELECT FORMAT(SYSDATETIME(), 'MM/dd/yyyy') AS dt;
```

如所述，`PARSE` 和 `FORMAT` 函数的效率非常低，特别是与更原生的函数相比时，后者内部是使用低级语言而非 .NET 开发的。我将通过性能测试来演示这一点。运行以下代码创建一个临时表 `#T`，并为其填充 1,000,000 行数据：

```sql
SELECT orderdate dt, CONVERT(CHAR(10), orderdate, 101) AS strdt
INTO #T
FROM PerformanceV3.dbo.Orders;
```

表 `#T` 的日期是 `DATE` 类型，而 `strdt` 使用美英语格式将日期存储为 `CHAR(10)` 类型。

第一个测试比较了 `PARSE` 与 `CONVERT` 将 `strdt` 列中的值解析为 `DATE` 的性能。为了排除在 SQL Server Management Studio (SSMS) 中显示值所需的时间，我在运行测试时丢弃了结果（在查询选项对话框的“结果”、“网格”下启用“执行后丢弃结果”选项）。以下是测试 `PARSE` 函数的代码：

```sql
SELECT PARSE(strdt AS DATE USING 'en-US') AS mydt
FROM #T;
```

在我的系统中，这段带有 `PARSE` 函数的代码耗时超过三分钟才完成。

以下是使用 `CONVERT` 函数完成相同任务测试的代码：

```sql
SELECT CONVERT(DATE, strdt, 101) AS mydt
FROM #T;
```

这段带有 `CONVERT` 函数的代码不到一秒就完成了。

第二个测试比较了使用 `FORMAT` 与 `CONVERT` 格式化值的性能，即使用 `'MM/dd/yyyy'` 格式将 `dt` 中的值转换为字符字符串。

以下是使用 `FORMAT` 函数完成任务的代码，耗时 28 秒：

```sql
SELECT FORMAT(dt, 'MM/dd/yyyy') AS mystrdt
FROM #T;
```

以下是使用 `CONVERT` 函数完成任务的代码，耗时不到一秒：

```sql
SELECT CONVERT(CHAR(10), dt, 101) AS mystrdt
FROM #T;
```

有趣的是，通过实现你自己的基于 CLR 的日期和时间格式化函数，你可以获得比提供的 `FORMAT` 函数好多的性能。你只需要对输入的日期和时间值调用 `ToString` 方法，并将输入格式字符串作为方法的输入，如 `(String)dt.Value.ToString(formatstring.Value)`。在我的测试中，使用用户定义 CLR 函数的查询在三秒内完成；它比提供的 `FORMAT` 函数快 10 倍。简而言之，最好远离提供的 `PARSE` 和 `FORMAT` 函数，并使用建议的替代方案。

完成后，运行以下代码进行清理：

```sql
DROP TABLE #T;
```



# SQL Server 2014 没有增加对任何新日期和时间函数的支持

## 处理日期和时间时的挑战

在处理日期和时间数据时，你会遇到许多挑战，这些挑战与编写正确且高效的代码有关。本节涵盖了诸如处理字面量、识别日期的星期几、处理仅日期和仅时间的数据、处理第一个、最后一个、上一个和下一个日期的计算、处理搜索参数以及处理舍入问题等挑战。

## 字面量

处理日期时间和字面量是一个引起很多麻烦的领域，通常会导致代码中的错误。本节描述了处理日期时间字面量涉及的复杂性，并提供了建议和最佳实践，帮助你避免陷入麻烦。

首先请注意，尽管 SQL 定义了日期时间和字面量，但 `T-SQL` 并不支持它们。`T-SQL` 的做法是将它们表示为字符字符串。然后，根据 SQL Server 的隐式转换将字符串转换为相应的日期或时间类型。然而，隐式转换是有风险的，因为它取决于会话设置，例如 `DATEFORMAT` 设置。例如，如果你有一个像 `'01/02/2015'` 这样的字符串，且 `DATEFORMAT` 设置为 `'mdy'`，则该字符串被解释为 1 月 2 日。如果 `DATEFORMAT` 设置为 `'dmy'`，则它被解释为 2 月 1 日。为了避免这种歧义，最好使用不产生歧义的格式（例如 `'YYYYMMDD'`），或使用显式转换函数（如带有指定区域的 `CONVERT` 或 `PARSE`）。

### 表 7-2 日期和时间数据格式

| 数据类型 | 与语言无关格式 | 示例 |
| --- | --- | --- |
| `DATETIME` | `'YYYYMMDD hh:mm:ss.nnn'`<br>`'YYYY-MM-DD hh:mm:ss.nnn'`<br>`'YYYYMMDD'` | `'20090212 12:30:15.123'`<br>`'2009-02-12 12:30:15.123'`<br>`'20090212'` |
| `SMALLDATETIME` | `'YYYYMMDD hh:mm'`<br>`'YYYY-MM-DD hh:mm'`<br>`'YYYYMMDD'` | `'20090212 12:30'`<br>`'2009-02-12 12:30'`<br>`'20090212'` |
| `DATE` | `'YYYYMMDD'`<br>`'YYYY-MM-DD'` | `'20090212'`<br>`'2009-02-12'` |
| `DATETIME2` | `'YYYYMMDD hh:mm:ss.nnnnnn'`<br>`'YYYY-MM-DD hh:mm:ss.nnnnnn'`<br>`'YYYY-MM-DD hh:mm:ss.nnnnnn'`<br>`'YYYYMMDD'`<br>`'YYYY-MM-DD'` | `'20090212 12:30:15.123456'`<br>`'2009-02-12 12:30:15.123456'`<br>`'2009-02-12 12:30:15.123456+02:00'`<br>`'20090212'` |
| `DATETIMEOFFSET` | `'YYYYMMDD hh:mm:ss.nnnnnn[+-]hh:mm'`<br>`'YYYY-MM-DD hh:mm:ss.nnnnnn[+-]hh:mm'`<br>`'YYYY-MM-DD hh:mm:ss.nnnnnn'`<br>`'YYYYMMDD'`<br>`'YYYY-MM-DD'` | `'20090212 12:30:15.123456+02:00'`<br>`'2009-02-12 12:30:15.123456+02:00'`<br>`'2009-02-12 12:30:15.123456'`<br>`'20090212'`<br>`'2009-02-12'` |

> 根据标准，`YYYY-MM-DD` 格式对于 `DATE`、`DATETIME2` 和 `DATETIMEOFFSET` 类型被认为是不歧义的。然而，出于后兼容性考虑，它对于较旧类型和 `SMALLDATETIME` 被认为是有歧义的。例如，对于旧类型，值 `'2015-02-12'` 在英式语言下会被解释为 2015 年 12 月 2 日，而在美式语言下解释为 2015 年 2 月 12 日。对于较新的类型，它始终会被解释为 2015 年 2 月 12 日。如果你在使用其中一种旧类型并假设会得到类似英式的解释，而在某处将列的值更改为其中一种新类型，可能会导致不同的解释。由于这个原因，我倾向于坚持使用 `'YYYYMMDD'` 格式。无论是否添加了时间，它在所有类型中都是无歧义的。通常，建议保持在所有情况下都能提供正确且无歧义解释的编码习惯。

## 识别星期几

假设在应用程序中，你需要识别输入日期的星期几。你需要了解此类计算涉及的一些复杂性，本节提供了详细信息。

要计算给定日期的星期几，请使用带有 `weekday` 部分（或简写 `dw`）的 `DATEPART` 函数，例如使用 `DATEPART(weekday, SYSDATETIME())` 获取今天的星期几。你需要注意这种计算依赖于语言。在上一节中，我解释了你的有效语言与一个名为 `DATEFORMAT` 的相关会话选项有关，而后者又决定了日期字面量的解释方式。同样，语言决定了名为 `DATEFIRST` 的会话选项，该选项又决定了什么被视为每周的第一天（1 周一，2 周二，……，7 周日）。你可以使用 `@@DATEFIRST` 函数查询有效设置，并使用 `SET DATEFIRST` 命令覆盖它。然而，通常不建议更改语言设置，因为会话中可能存在依赖登录视角的计算。此外，使用特定语言设置创建的缓存查询计划无法被不同的语言设置重用。

今天是星期四，你正在使用表达式 `DATEPART(weekday, SYSDATETIME())` 计算星期几。如果你使用美式英语语言连接，SQL Server 将你的 `DATEFIRST` 设置为 7（表示星期日是每周的第一天）；因此，表达式返回星期几 5。如果你使用英式英语连接，SQL Server 将 `DATEFIRST` 设置为 1（表示星期一是每周的第一天）；因此，表达式返回星期几 4。如果你显式将 `DATEFIRST` 设置为 2（表示星期二是每周的第一天），如图 7-1 所示，箭头标记了 `DATEFIRST` 设置，x 代表星期几的从 1 开始的序数。

左侧插图表示 `DATEFIRST` 设置为 1 的环境（通常周一是一周的第一天），右侧插图表示 `DATEFIRST` 设置为 2 的环境（周二是周的第一天）。请观察在两种情况下，如果假设计算时周一为周的第一天，结果均为 4。

### DATEFIRST = 1

### DATEFIRST = 2

![](img/bdc38aa36f6e2987d913ee5381474711_463_0.png)

图 7-2 与语言无关的星期。

## 使用 DATETIME 和 SMALLDATETIME 处理仅日期或仅时间的数据

如前所述，旧版本的 `DATETIME` 和 `SMALLDATETIME` 仍然被广泛使用，特别是出于历史或其他原因考虑。问题在于，考虑到这些类型同时包含日期和时间，你如何处理仅包含日期或仅时间的数据呢？推荐的做法是：当你只需要存储日期时，将日期与午夜时间一起存储；当你只需要存储时间时，将时间与基础日期（1900 年 1 月 1 日）一起存储。

如果你在好奇为什么专门使用午夜和基础日期而不是其他时间，这是有原因的。当 SQL Server 将仅包含日期的字符串转换为日期时间类型时，它会假设午夜为时间。例如，如果你有一个带有过滤器 `WHERE dt = '20150212'` 的查询，且 `dt` 列是 `DATETIME` 类型，SQL Server 将隐式地将字面量字符串转换为 `datetime`，并假设为午夜。如果你在 `dt` 列中存储的所有值都以午夜作为时间，该过滤器将正确返回日期为 2015 年 2 月 12 日的行。

仅时间数据的示例，假设你有一个带有过滤器 `WHERE tm = '12:00:00.000'` 的查询，且 `tm` 列是 `DATETIME` 类型。SQL Server 将隐式地将字面量转换为 `DATETIME`，并假设基础日期为日期。如果你在 `tm` 列中存储的所有值都以基础日期作为日期，该过滤器将正确返回时间为午夜的行。

根据推荐的做法，你需要能够获取输入的日期和时间值（例如 `SYSDATETIME` 函数），将其转换为 `DATETIME` 或 `SMALLDATETIME`，并将时间设置为午夜以获取仅日期数据，或将日期设置为基础日期以获取仅时间数据。要获取仅日期数据，只需将输入转换为 `DATE` 然后转换为 `DATETIME`（或 `SMALLDATETIME`），如下所示：

```sql
SELECT CAST(SYSDATETIME() AS DATE) AS DATETIME;
```

有一种稍微复杂的方法可以将输入的时间部分设置为午夜，但它是值得了解的，因为这个概念可以用于其他计算，正如我将在下一节中演示的那样。该方法涉及使用一个过去日期的作为起点，其时间为午夜。我为此使用 1900 年 1 月 1 日。你计算该起始点与输入值之间的天数差（称为 `diff`）。然后向你计算差值时使用的同一个起始点加上天数，即可得到午夜的目标日期。以下是应用于 `SYSDATETIME` 输入的完整计算过程：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', SYSDATETIME()), '19000101');
```

要获取仅时间数据，将输入转换为 `TIME` 然后转换为 `DATETIME`（或 `SMALLDATETIME`），如下所示：

```sql
SELECT CAST(SYSDATETIME() AS TIME) AS DATETIME;
```

## 第一、最后、上一个和下一个日期的计算

本节涵盖了此类计算，例如寻找某期间的第一天或最后一天、某个特定周几的上一个或下一个等。我涵盖的所有计算将基于某个给定的日期和时间值。我将使用 `SYSDATETIME` 函数作为给定值，但你可以将 `SYSDATETIME` 更改为任何日期时间值。

### 期间的第一天或最后一天

本节涵盖了相对于给定参考日期和时间值，某期间（如月份或年份）的第一天和最后一天的计算。

之前我提供了以下表达式将给定的日期时间值的时间设置为午夜：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', SYSDATETIME()), '19000101');
```

你可以使用类似的逻辑来计算每月第一日的日期。你需要确保使用一个作为每月第一日的锚点日期，并使用月份部分而不是日期部分，如下：

```sql
SELECT DATEADD(month, DATEDIFF(month, '19000101', SYSDATETIME()), '19000101');
```

该表达式计算了某月第一天与参考日期之间的月份数差。将该差称为 `diff`。然后该表达式向锚点日期加上月份，产生与给定参考日期相对应的月第一日的日期。

计算每月第一日的另一种方法是使用 `DATEFROMPARTS` 函数，如下所示：

```sql
SELECT DATEFROMPARTS(YEAR(SYSDATETIME()), MONTH(SYSDATETIME()), 1);
```

要返回月的最后一天，你可以使用 `EOMONTH` 函数，如下所示：

```sql
SELECT EOMONTH(SYSDATETIME());
```

### 上一个或下一个特定周几

要计算给定日期之前（包含当天）的上一个特定周几（例如周一），可以使用以下表达式：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', DATEADD(day, -1, SYSDATETIME()))/7*7 + 7, '19000101');
```

与之前一样，如果你需要处理不同的星期，请替换锚点日期——例如周二：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000102', DATEADD(day, -1, SYSDATETIME()))/7*7 + 7, '19000102');
```

或者周日：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000107', DATEADD(day, -1, SYSDATETIME()))/7*7 + 7, '19000107');
```

要使计算变为排除性的（即返回参考日期之后的下一次目标星期几，而不是在当天或之后），只需跳过从锚点日期减去一天的步骤。例如，以下表达式返回参考日期之后的下一个周一：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', SYSDATETIME())/7*7 + 7, '19000101');
```

此计算是针对下一次星期的排除性计算：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000102', SYSDATETIME())/7*7 + 7, '19000102');
```

此计算是针对下一次周日的排除性计算：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000107', SYSDATETIME())/7*7 + 7, '19000107');
```

### 月份第一个或最后一个星期几

在本节中，我将描述如何计算特定时期（如月份或年份）内某个星期几的第一次和最后一次出现。要计算月份内某个星期几的第一次出现，我需要结合之前开发的两种计算方法。一个是计算月份第一天的公式：

```sql
SELECT DATEADD(month, DATEDIFF(month, '19000101', SYSDATETIME()), '19000101');
```

另一个是计算某个星期几的下一次出现，包含当天——在本例中为周一：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', DATEADD(day, -1, SYSDATETIME()))/7*7 + 7, '19000101');
```

技巧在于将月份的第一天作为“下一次星期几出现”计算中的参考日期。例如，以下表达式返回参考月份内第一个周一日期：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', 
    -- 月份的第一天
    DATEADD(month, DATEDIFF(month, '19000101', SYSDATETIME()), '19000101')
    -1) /7*7 + 7, '19000101');
```

要处理不同的星期几，请替换表达式中计算“下一次星期几出现”部分的锚点日期——而不是计算“月份第一天”的部分。以下表达式返回参考月份内第一个周二的日期：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000102',
    -- 月份的第一天
    DATEADD(month, DATEDIFF(month, '19000101', SYSDATETIME()), '19000101')
    -1)/7*7 + 7, '19000102');
```

要计算参考月份内某个星期几的最后一次出现日期，同样需要结合两种计算。一个是参考月份的最后一天：

```sql
SELECT DATEADD(month, DATEDIFF(month, '18991231', SYSDATETIME()), '18991231');
```

另一个是计算某个星期几的上一次出现，包含当天——在本例中为周一：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101', SYSDATETIME())/7*7, '19000101');
```

只需将月份最后一天的计算作为“最后一次星期几”计算中的参考日期。例如，以下表达式返回参考月份内最后一次周一：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101',
    -- 月份的最后一天
    DATEADD(month, DATEDIFF(month, '18991231', SYSDATETIME()), '18991231')
)/7*7, '19000101');
```

处理不同的星期几时，将最后一次星期几计算中的锚点日期替换为相应的日期。例如，以下表达式返回参考月份内最后一次周二：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000102',
    -- 月份的最后一天
    DATEADD(month, DATEDIFF(month, '18991231', SYSDATETIME()), '18991231')
)/7*7, '19000102');
```

以类似于计算年份内某个星期几的第一次和最后一次出现的方式，你可以计算月份内的第一天或最后一天，以及年份内的第一天或最后一天。以下是一些示例：

参考年份内的第一个周一：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101',
    -- 年份的第一天
    DATEADD(year, DATEDIFF(year, '19000101', SYSDATETIME()), '19000101')
    -1)/7*7 + 7, '19000101');
```

参考年份内的第一个周二：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000102',
    -- 年份的第一天
    DATEADD(year, DATEDIFF(year, '19000101', SYSDATETIME()), '19000101')
    -1)/7*7 + 7, '19000102');
```

参考年份内的最后一次周一：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000101',
    -- 年份的最后一天
    DATEADD(year, DATEDIFF(year, '18991231', SYSDATETIME()), '18991231')
)/7*7, '19000101');
```

参考年份内的最后一次周二：

```sql
SELECT DATEADD(day, DATEDIFF(day, '19000102',
    -- 年份的最后一天
    DATEADD(year, DATEDIFF(year, '18991231', SYSDATETIME()), '18991231')
)/7*7, '19000102');
```



# 搜索参数 (SARG)

查询调优中最基础的概念之一是搜索参数（SARG）。它并不是只适用于日期和时间，但在此类数据中非常常见。假设你有一个形式为 `<列> <运算符> <值>` 过滤条件的查询，并且在该列上有支持的索引。只要你不对过滤列进行任何操作，SQL Server 就可以依赖该索引——例如执行索引查找（seek）然后进行索引范围扫描（scan）。如果索引不是覆盖索引，可能会存在过滤选择性是否足以支持索引的问题，但点在于如果你对列进行了操作，除了少数特殊情况外，SQL Server 可能不会依赖索引而使用效率较低的访问方法（如函数）。

如前所述，SARG 的问题并不是只适用于日期和时间，因为你经常根据日期和时间进行过滤。经典的例子是整天、周、月等时间范围。为了优化索引使用，你应该养成在不操作过滤列的情况下表达范围过滤的习惯。例如，以下两个查询在逻辑上是等同的——都过滤整个 2014 年：

```sql
USE PerformanceV3;

SELECT orderid, orderdate, filler
FROM dbo.Orders
WHERE YEAR(orderdate) = 2014;

SELECT orderid, orderdate, filler
FROM dbo.Orders
WHERE orderdate >= '20140101'
AND orderdate < '20150101';
```

`orderdate` 列上定义了一个聚集索引，显然这里的最佳计划是通过范围扫描索引中的符合条件的行。图 7-3 显示了你获取这些查询的实际计划。

```sql
Query 1: 查询成本（相对于批处理）: 80%
SELECT * FROM dbo.Orders WHERE YEAR(orderdate) = 2014
```
![img/bdc38aa3f6e2987d913ee5381474711_470_0.png)
聚集索引扫描（聚集）
[Orders].[idx_cl_od]
成本: 99 %

```sql
Query 2: 查询成本（相对于批处理）: 20%
SELECT * FROM [dbo].Orders WHERE [orderdate]='20140101' AND [orderdate]<'20150101'
```
![img/bdc38aa6f6e2987d913ee5381474711_470_1.png)
聚集索引查找（聚集）
[Orders].[idx_cl_od]
成本: 100 %

图 7-3 非 SARG 查询。

第一个查询中的谓词不是符合 SARG 的。优化器不会试图变聪明去理解你所做操作的含义，而是诉诸全表扫描。在第二个查询中，谓词是符合 SARG 的，允许在索引中进行高效的查找和部分扫描。

如前所述，在例外情况下，SQL Server 将对过滤列进行操作的谓词视为符合 SARG 的。此类异常的例子是谓词将列转换为 `DATE` 类型，如下查询所示：

```sql
SELECT orderid, orderdate, filler
FROM dbo.Orders
WHERE CAST(orderdate AS DATE) = '20140212'
```

Microsoft 的逻辑是将此类谓词视为 SARG，因此选择执行索引查找和索引范围扫描。在这个问题中，这是例外而非常态。

如果你是一个经验丰富的数据库从业人员，其他人很可能会模仿你的做法而不完全理解它们。由于这个原因，你应该倾向于使用更可能符合 SARG 的不操作过滤列的形式。与其使用前一个查询的谓词形式，建议使用以下形式：

```sql
SELECT orderid, orderdate, filler
FROM dbo.Orders
WHERE orderdate >= '20140212'
AND orderdate < '20140213'
```

## 舍入问题

当你将字符字符串值转换为日期时间类型，或者将一个高精度值转换为低精度值时，你需要意识到 SQL Server 是如何处理这些转换的。SQL Server 的某些处理方式可能会出乎意料。

常见的陷阱之一发生在将字符字符串值转换为 `DATETIME` 类型时。为了演示这一点，我将使用以下示例数据：

```sql
USE SQLV3;
IF OBJECT_ID('Sales.MyOrders', 'U') IS NOT NULL DROP TABLE Sales.MyOrders;
GO

SELECT * INTO Sales.MyOrders FROM Sales.MyOrders;
ALTER TABLE Sales.MyOrders ALTER orderdate DATETIME NOT NULL;
CREATE INDEX idx_cl_od ON Sales.MyOrders(orderdate);
```

假设你需要过滤订单日期落在某个范围内的订单。想象存储值中的时间部分并不一定是午夜，而你想过滤像一整天、一个月、一年之类的范围。例如，仅过滤在 2015 年 1 月 1 日下单的订单。人们表达过滤的一种常见错误方法是使用 `BETWEEN` 谓词，如下：

当使用这种形式时，人们认为 999 是秒的最后一位毫秒部分。然而，`DATETIME` 精度是 1/3 毫秒，并舍入到最近的刻度（tick）。因此，毫秒最后一位数字的有效值只有 0、3 和 7。任何其他值都会被舍入到最接近的支持值。这意味着前一个查询中指定为结束定界符的值会被舍入到下一天的午夜。这导致查询返回以下输出：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 10808 | 2015-01-01 00:00:00.005 | | 2 |
| 10809 | 2015-01-01 00:00:00.008 | | 7 |
| 10810 | 2015-01-01 00:00:00.002 | | 4 |
| 10811 | 2015-01-02 00:00:00.000 | | 8 |
| 10812 | 2015-01-02 00:00:00.006 | | 5 |

注意到，尽管你只想寻找 2015 年 1 月 1 日下单的订单，但你也得到了来自 2 号的订单。为此，推荐的做法是将你的范围表示为大于或等于范围内日期的午夜，并且小于范围内最后一个日期之后日期的午夜。在我们的示例中，你应该这样更改过滤条件：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.MyOrders
WHERE orderdate >= '20150101'
AND orderdate < '20150102';
```

这一次你得到了正确的结果：

| orderid | orderdate | custid | empid |
|---|---|---|---|
| 10808 | 2015-01-01 | 55 | 2 |
| 10809 | 2015-01-01 | 88 | 7 |
| 10810 | 2015-01-01 | 42 | 2 |

如果你遵循这一实践，你的代码在所有日期和时间类型上都能正常工作，无论值是否包含相关的时间部分。始终采用在所有情况下都能正常运行的形式总是好的。回到我们使用 `DATETIME` 函数的示例，为了返回今天午夜和明天午夜下单的订单，操作 `SYSDATETIME` 的结果来计算今天和明天午夜作为左闭右开间的边界，如下：

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.MyOrders
WHERE orderdate >= CAST(SYSDATETIME() AS DATE)
AND orderdate < DATEADD(day, 1, CAST(SYSDATETIME() AS DATE));
```

完成后，运行以下代码进行清理工作：

```sql
IF OBJECT_ID('Sales.MyOrders', 'U') IS NOT NULL DROP TABLE Sales.MyOrders;
```

你可能没有意识到 SQL Server 在从高精度日期时间值转换为低精度时会执行类似的舍入逻辑。例如，当你将 `SYSDATETIME()` 函数的结果（返回 `DATETIME2`）转换为 `SMALLDATETIME`（分钟精度）时，SQL Server 不会将值向下取整到分钟的底部；而是将值舍入到最近的分钟。这意味着该值会被舍入到半点之前的分钟开始，以及在半点或之后舍入到下一分钟。如果你想应用向下取整（flooring）而不是舍入，在转换值之前减去 30 秒。以下代码返回了 `SYSDATETIME()` 函数的结果，演示了舍入和向下取整的：

```sql
SELECT
    SYSDATETIME() AS currentdatetime,
    CAST(SYSDATETIME() AS SMALLDATETIME) AS roundedminute,
    CAST(DATEADD(ss, -30, SYSDATETIME()) AS SMALLDATETIME) AS flooredminute;
```

相同的舍入逻辑也适用于从高精度日期时间值到低精度的转换。例如，当将 `SYSDATETIME()` 函数的结果转换为 `SMALLDATETIME`（分钟精度）时，SQL Server 不会将值向下取整到分钟的底部；而是将值舍入到最近的分钟。这意味着该值会被舍入到半点之前的分钟开始，以及在半点或之后舍入到下一分钟。如果你想应用向下取整（flooring）而不是舍入，在转换值之前减去 30 秒。

（注：由于原文后半部分存在大量重复和逻辑断裂，译文已根据意图进行了整合以确保通顺。）

我们将看到该问题体现的实际示例。幸运的是，有高效的解决方案，尽管它们没有经典方法那么简单。

为了演示如何解决涉及日期和时间间隔的常见任务，我将使用代表手机账户和通话会话的示例数据。运行以下代码在 `tempdb` 中创建并填充 `Accounts` 和 `Sessions` 表，并包含少量数据：

```sql
SET NOCOUNT ON;
USE tempdb;
```

```sql
IF OBJECT_ID('dbo.Sessions') IS NOT NULL DROP TABLE dbo.Sessions;
IF OBJECT_ID('dbo.Accounts') IS NOT NULL DROP TABLE dbo.Accounts;
```

```sql
CREATE TABLE dbo.Accounts
(
    actid INT NOT NULL,
    CONSTRAINT PK_Accounts PRIMARY KEY(actid)
)
GO
```

```sql
INSERT INTO dbo.Accounts VALUES(1), (2), (3);
```

```sql
CREATE TABLE dbo.Sessions
(
    sessionid INT NOT NULL IDENTITY(1, 1),
    actid INT NOT NULL,
    starttime DATETIME(0) NOT NULL,
    endtime DATETIME(0) NOT NULL,
    CONSTRAINT PK_Sessions PRIMARY KEY(sessionid),
    CONSTRAINT CHK_endtime_gteq_starttime CHECK (endtime >= starttime)
)
GO
```

```sql
INSERT INTO dbo.Sessions(actid, starttime, endtime) VALUES
(1, '20151231 08:00:00', '20151231 08:30:00'),
(1, '20151231 08:30:00', '20151231 09:00:00'),
(1, '20151231 09:00:00', '20151231 09:30:00'),
(1, '20151231 10:00:00', '20151231 11:00:00'),
(1, '20151231 10:30:00', '20151231 12:00:00'),
(1, '20151231 11:30:00', '20151231 12:30:00'),
(2, '20151231 08:00:00', '20151231 10:00:00'),
(2, '20151231 08:30:00', '20151231 10:00:00'),
(2, '20151231 09:00:00', '20151231 11:30:00'),
(2, '20151231 11:32:00', '20151231 12:00:00'),
(2, '20151231 12:04:00', '20151231 12:30:00'),
(3, '20151231 08:00:00', '20151231 09:00:00'),
(3, '20151231 08:30:00', '20151231 08:30:00'),
(3, '20151231 09:30:00', '20151231 09:00:00');
```

通话会话是定义在 `starttime` 和 `endtime` 之间的间隔，使用 `DATETIME(0)` 类型，精度为一秒。我将不定义每个差值中哪个方面是开区间（不包含）或闭区间（包含），以便你根据示例数据需要代表的实际应用场景，根据具体情况进行定义。

使用上述代码创建的小量组示例数据来验证解决方案的正确性。对于性能测试，可以使用以下代码，它将创建一个包含 50,000 个和 10,000,000 个间隔的大量示例数据：

```sql
-- 10,000,000 intervals
DECLARE
    @num_accounts INT = 50,
    @sessions_per_account INT = 200000,
    @start_period DATETIME(2) = '20120101',
    @end_period DATETIME(2) = '20160101',
    @max_duration_in_seconds INT = 3600; -- 1 hour

TRUNCATE TABLE dbo.Sessions;
TRUNCATE TABLE dbo.Accounts;

INSERT INTO dbo.Accounts(actid)
SELECT A.n AS actid
FROM TSQLV3.GetNums(1, @num_accounts) AS A;

WITH C AS (
    SELECT A.n AS actid,
    DATEADD(second,
    ABS(CHECKSUM(NEWID())) % 
    DATEDIFF(s, @start_period, @end_period) AS @max_duration_in_seconds,
    @max_duration_in_seconds,
    @start_period) AS starttime
    FROM TSQLV3.GetNums(1, @num_accounts) AS A
    CROSS JOIN TSQLV3.GetNums(1, @sessions_per_account) AS I
)
INSERT INTO dbo.Sessions(actid, starttime, endtime)
SELECT actid, starttime, DATEADD(second, @max_duration_in_seconds, starttime)
FROM C;
```

结论是，最好将选择性更高的列 `endtime` 置于选择性较低的列 `starttime` 之前创建索引，如下：

```sql
CREATE UNIQUE INDEX idx_end_start ON dbo.Sessions(actid, endtime, starttime, sessionid);
```

重新运行查询：

```sql
DECLARE
    @actid AS INT = 1,
    @s AS DATETIME(2) = '20151231 11:00:00',
    @e AS DATETIME(2) = '20151231 12:00:00'
SELECT sessionid, actid, starttime, endtime
FROM dbo.Sessions
WHERE actid = @actid
AND starttime <= @s
AND endtime >= @e
OPTION(RECOMPILE);
```

这一次，你得到了图 7-6 中的计划，显示选择性更高的列被用作查找谓词（seek predicate），而选择性较低的列被用作剩余谓词（residual predicate）。

![](img/bdc38aa36f6e2987d913ee5381474711_479_0.png)

| 谓词 |
| --- |
| [tempdb].[dbo].[Sessions].[starttime] <= '2015-12-31 12:00:00' |
| Seek Predicates |
| SeekKeys[1]: Prefix([tempdb].[dbo].[Sessions].actid = Scalar Operator(1)); Start: [tempdb].[dbo].[Sessions].[endtime] = Scalar Operator('2015-12-31 11:00:00') |

图 7-6 与索引 `idx_end_start` 的交集情况。

当我在我的系统上运行此查询时，它只执行了逻辑读取：

当你在测试交集查询（intersection queries）时，运行以下代码删除索引 `idx_end_start`（保留索引 `idx_start` 以备后续示例）：

```sql
DROP INDEX idx_end_start ON dbo.Sessions;
```



因此，当你幸运地有足够的交集查询应用于数据中的近期时期时，通过创建正确的索引很容易获得良好的性能。然而，如果你的交集查询可以应用于任何时期，无论 `starttime` 在 `endtime` 之前还是反之，平均而言，每次查询都会导致账户行数减半。我的示例数据每个分区（账户）有 200,000 行，因此扫描这半部分并不一定是灾难，但如果每个分区有数百万行呢？

对于交集查询，有一种适用于更通用情况的解决方案。它基于一种名为关系树（Relational Tree, RI-tree）的巧妙模型。它由慕尼黑大学的 Hans-Peter Kriegel、Marco Pötke 和 Thomas Seidl 制定，并由 Laurent Martin 进一步优化。该模型的实现涉及：(1) 在表中添加一列表示模型中所谓的叉叉节点（fork node）；(2) 基于 `(forknode, startTime, key)` 和 `(forknode, endtime, key)` 的 B-tree 索引；以及 (3) 用于统一不相交区间集合的新交集查询，每个查询使用不超过一个范围谓词。这个模型和改进非常精妙，是一项令人印象深刻的成就。如果你在应用程序中有执行交集查询的需求且目前正深受性能问题的困扰，那么熟悉它是值得的。你可以在以下内容找到关于该模型、改进以及 SQL Server 中实现的细节：

- "Interval Queries in SQL Server"，作者 Itzik Ben-Gal (http://sqlmag.com/t-sql/server-interval-queries)
- "Managing Intervals Efficiently in Object-Relational Databases"，作者 Hans-Peter Kriegel

# 最大并发区间

寻找最大并发区间数量是一项经典任务。在我们的 `Sessions` 表中，你需要为每个账户统计并发的会话数量。此类计算通常是为了容量规划的峰值使用分析、计费等目的。

如往常，你需要知道界定的区间是闭区间（不包含边界）还是开区间（包含边界）。你需要知道这一点来判断在任何给定时间点哪些区间被认为是活跃的。对于闭闭区间 `[startTime, endtime]`，区间在 `ts >= startTime AND ts <= endTime` 期间处于活跃状态。对于闭开区间 `[startTime, endtime]`，区间在 `ts >= startTime AND ts < endTime` 期间处于活跃状态。在本例中，我假设后者（闭开区间）。

对于这小部分样本数据，你的解决方案应该生成以下内容：

```
acid  mx
1      2
2      3
3      2
```

我将从一个基于子查询的传统但低效的集合解决方案开始，然后继续基于窗口函数的更高效的解决方案。

传统的基于子查询的解决方案将受益于你之前创建的 `idx_end_end` 索引。如果你的 `Sessions` 表中没有此索引，请运行以下代码创建它：

```sql
CREATE UNIQUE INDEX idx_start_end ON dbo.Sessions(actid, starttime, endtime, sessionid);
```

解决方案的第一步是识别区间数量达到最大值的时间点。如果你遵循时间轴，活跃区间的计数只在区间开始或结束时发生变化。在此期间，计数保持不变。此外，每当一个区间开始时，计数增加；而当一个区间结束时，计数减少。因此，最大计数必须落在其中一个开始事件上。解决方案首先定义一个 CTE `P`，返回最大计数可能发生的开始事件时间戳（列 `ts`）：

```sql
WITH P AS (
  SELECT starttime AS ts FROM dbo.Sessions
)
SELECT actid, ts FROM P;
```

第二步是定义一个 CTE，根据所提供的谓词计算同一账户在 `ts` 时的活跃区间数量。实现此点的代码如下：

```sql
WITH P AS (
  SELECT actid, starttime AS ts FROM dbo.Sessions
),
C AS (
  SELECT COUNT(*)
  FROM dbo.Sessions AS S
  WHERE P.actid = S.actid
    AND P.ts >= S.starttime
    AND P.ts < S.endtime
)
SELECT actid, ts, cnt FROM C;
```

这段代码使用小部分样本数据生成以下输出：

| actid | ts | cnt |
| --- | --- | --- |
| 1 | 2015-12-31 08:00:00 | 1 |
| 1 | 2015-12-31 08:30:00 | 1 |
| 1 | 2015-12-31 09:00:00 | 1 |
| 1 | 2015-12-31 10:00:00 | 1 |
| 1 | 2015-12-31 10:30:00 | 2 |
| 1 | 2015-12-31 11:30:00 | 2 |
| 2 | 2015-12-31 09:00:00 | 3 |
| 2 | 2015-12-31 08:30:00 | 2 |
| 2 | 2015-12-31 08:00:00 | 1 |
| 2 | 2015-12-31 11:00:00 | 1 |
| 2 | 2015-12-31 11:30:00 | 1 |
| 2 | 2015-12-31 12:00:00 | 1 |
| 2 | 2015-12-31 08:00:00 | 2 |
| 3 | 2015-12-31 08:30:00 | 2 |
| 3 | 2015-12-31 09:30:00 | 0 |

> 注意：如果你奇怪为什么账户 3 在最后一个时间戳处有 0 个活跃区间，那是因为样本数据有一个开始时间和结束时间相同的退化区间（degenerate interval）。我想包含这样一个闭闭区间的例子，在上一节中讨论了交集测试。在实践中，如果你的表表示闭开区间且你不想要空区间，你的约束将通过 `endtime >= starttime` 谓词来强制执行。

第三步也是最后一步是通过账户对 `C` 中的行进行分组，并返回每个账户的最大计数，如下：

```sql
WITH P AS (
  SELECT actid, starttime AS ts FROM dbo.Sessions
),
C AS (
  SELECT actid, ts,
    (SELECT COUNT(*)
     FROM dbo.Sessions S
     WHERE P.actid = S.actid
       AND P.ts >= S.starttime
       AND P.ts < S.endtime) AS cnt
  FROM P
)
SELECT actid, MAX(cnt) AS mx
FROM C
GROUP BY actid;
```

这个解决方案非常简单直观，所以从逻辑角度来看它是没问题的。问题在于在没有优化索引 `idx_start_end` 的情况下，它的优化效率非常低。该解决方案的计划如图 7-7 所示。

嵌套循环（Nested Loops）的外层分支将索引与计算计数的时间戳连接起来。当区间数量很多时，时间很多，因为这些时间戳是所有区间的起点。对于每个时间戳，嵌套循环的内部分支根据子查询中的谓词在索引中执行查找和范围扫描：`P.actid = S.actid AND P.ts >= S.starttime AND P.ts < S.endtime`。问题就在于此。从区间边界的角度考虑这些谓词，你有两个范围谓词：`S.starttime < P.pts` 和 `S.endtime > P.pts`。平均每个时间戳，Index Seek 运算符将扫描索引中当前账户的大半部分行。每个账户有 N 行，这意味着要扫描 N/2 行。我们的表每个账户有 200,000 行，这相当于每个账户处理 20,000,000,000 行。在我的系统上，处理一个账户大约需要 11 分 30 秒。对于 50 个账户，查询需要大约 9 小时才能完成。计划中误导你让你无法看到过量工作的是，Index Seek 运算符没有告诉你扫描了多少行；而是告诉了它返回了多少行。

![](img/bdc38aa36f6e2987d913ee5381474711_483_png)

7-7 最大并发区间任务传统解决方案的计划。

当你完成此解决方案后，删除索引 `idx_start_end`：

```sql
DROP INDEX idx_start_end ON dbo.Sessions;
```

最大并发区间任务有更高效的解决方案，基于窗口函数。我将首先提供一个基于带有框架的窗口聚合函数的解决方案，它适用于 SQL Server 2012，然后展示一个基于 `ROW_NUMBER` 函数的解决方案，该函数支持更早的版本。这两个解决方案将受益于以下索引，这些索引包含了开始和结束事件：

```sql
CREATE UNIQUE INDEX idx_start_end ON dbo.Sessions(actid, starttime, endtime, sessionid);
CREATE UNIQUE INDEX idx_end_end ON dbo.Sessions(actid, endtime, sessionid);
```

解决方案的第一步是根据事件发生的顺序生成时间顺序序列。我们将事件标记为 `+1` 事件类型，意味着该事件增加了活跃区间的计数，并将事件标记为 `-1` 以减少计数。由于我们示例中的区间是闭开区间，在结束和开始事件发生在同一时间的情况下，你将结束事件排在开始事件之前，这样计数先下降后增加。你通过在需要事件的 `ts` 之后使用（升序）作为决胜因素来实现这一点。以下代码作为名为 `C1` 的 CTE 实现了第一步。

```sql
WITH C1 AS (
  SELECT actid, starttime ts, +1 AS type
  FROM dbo.Sessions
  UNION ALL
  SELECT actid, endtime ts, -1 AS type
  FROM dbo.Sessions
)
SELECT actid, ts, type
FROM C1
ORDER BY actid, ts, type;
```

此代码生成了以下输出（仅显示账户 2 的事件）：

| actid | ts | type |
|---|---|---|
| 2 | 2015-12-31 08:00:00 | 1 |
| 2 | 2015-12-31 08:30:00 | 1 |
| 2 | 2015-12-31 09:00:00 | 1 |
| 2 | 2015-12-31 09:30:00 | -1 |
| 2 | 2015-12-31 10:00:00 | -1 |
| 2 | 2015-12-31 10:30:00 | -1 |
| 2 | 2015-12-31 11:00:00 | 1 |
| 2 | 2015-12-31 11:30:00 | -1 |
| 2 | 2015-12-31 12:00:00 | -1 |
| 2 | 2015-12-31 12:04:00 | 1 |
| 2 | 2015-12-31 12:30:00 | -1 |

第二步简单地通过随时间变化的 `type` 运行总和来计算每个事件之后活跃区的计数。以下是使用 CTE `C2` 实现第二步的代码：

```sql
WITH C1 AS (
  SELECT actid, starttime ts, +1 AS type
  FROM dbo.Sessions
  UNION ALL
  SELECT actid, endtime ts, -1 AS type
  FROM dbo.Sessions
),
C2 AS (
  SELECT *,
    SUM(type) OVER(PARTITION BY actid
      ORDER BY ts, type
      ROWS UNBOUNDED PRECEDING) AS cnt
  FROM C1
)
SELECT actid, ts, type, cnt FROM C2;
```

此步骤生成了以下输出（针对账户 2）：

| actid | ts | type | cnt |
|---|---|---|---|
| 2 | 2015-12-31 08:00:00 | 1 | 1 |
| 2 | 2015-12-31 08:30:00 | 1 | 2 |
| 2 | 2015-12-31 09:00:00 | 1 | 3 |
| 2 | 2015-12-31 09:30:00 | -1 | 2 |
| 2 | 2015-12-31 10:00:00 | -1 | 1 |
| 2 | 2015-12-31 10:30:00 | -1 | 0 |
| 2 | 2015-12-31 11:00:00 | 1 | 1 |
| 2 | 2015-12-31 11:30:00 | -1 | 0 |
| 2 | 2015-12-31 12:00:00 | -1 | 0 |
| 2 | 2015-12-31 12:04:00 | 1 | 1 |
| 2 | 2015-12-31 12:30:00 | -1 | 0 |

最后一步是按账户对 `C2` 中的行进行分组并返回每个组的最大计数，如下所示：

```sql
WITH C1 AS (
  SELECT actid, starttime AS ts, +1 AS type
  FROM dbo.Sessions
  UNION ALL
  SELECT actid, endtime AS ts, -1 AS type
  FROM dbo.Sessions
),
C2 AS (
  SELECT *,
    SUM(type) OVER(PARTITION BY actid
      ORDER BY ts, type
      ROWS UNBOUNDED PRECEDING) AS cnt
  FROM C1
)
SELECT actid, MAX(cnt) AS mx
FROM C2
GROUP BY actid;
```

该查询的执行计划如图 7-8 所示。

该计划是高效的。索引 `idx_start` 和 `idx_end` 按顺序扫描；行被合并，并保留了顺序。然后根据顺序同时计算了窗口聚合和组聚合。计划中没有应用任何操作。该查询在我的系统上花费了 44 秒完成，并且具有线性扩展性。考虑到使用查询的解决方案花费了 10 小时才完成，这并不算差。

该任务的另一种解决方案基于 `ROW_NUMBER` 函数。它与窗口聚合的解决方案相比有两个优势。请记住，带有框架（frame）选项的窗口聚合仅在 SQL Server 2012 及更高版本中可用，而窗口排名函数在更早的版本就可用。

此外，窗口聚合函数使用存储池（spool）来缓存行帧，这是额外的工作。`ROW_NUMBER` 函数使用流式操作符处理计算，无需存储池。因此，使用 `ROW_NUMBER` 处理任务会获得更好的性能。

| Operation | Cost |
|---|---|
| Sequence (Compute Scalar) | 0 % |
| Merge Join (Concatenation) | 24 % |
| Compute Scalar | 1 % |
| Index Scan (NonClustered) [Sessions].[idx_start] | 16 % |
| Compute Scalar | 1 % |
| Index Scan (NonClustered) [Sessions].[idx_end] | 16 % |

基于 `ROW_NUMBER` 的解决方案起始方式与窗口聚合的解决方案类似。它通过统一开始和结束事件来生成按时间顺序的事件序列。此外，它计算了两个数字：一个是计算到当前开始事件为止发生了多少开始事件（称为 `s`），另一个是计算到当前结束事件为止发生了多少开始和结束事件（称为 `se`）。你在查询中计算返回 `NULL` 作为占位符的序数 `s`。通过定义一个代表包含序数的按时间事件序列的 CTE `C1`，然后你查询 `C1` 并针对统一事件计算序数。你基于此查询定义了一个 CTE `C2`，得到了按时间顺序的事件序列，包括序数和 `s`。以下是实现第一步的代码：

```sql
WITH C1 AS (
  SELECT actid, starttime ts, +1 AS type, sessionid,
    ROW_NUMBER() OVER(PARTITION BY actid ORDER BY starttime, sessionid) AS s
  FROM dbo.Sessions
  UNION ALL
  SELECT actid, endtime ts, -1 AS type, sessionid, NULL AS s
  FROM dbo.Sessions
),
C2 AS (
  SELECT *,
    ROW_NUMBER() OVER(PARTITION BY actid ORDER BY ts, type, sessionid) AS se
  FROM C1
)
SELECT sessionid, actid, ts, type, s, se FROM C2;
```

此代码生成了以下输出（仅显示账户 2 的事件）：

| sessionid | actid | ts | type | s | se |
|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... |
| 7 | 2 | 2015-12-31 08:00:00 | 1 | 1 | 1 |
| 8 | 2 | 2015-12-31 08:30:00 | 1 | 2 | 2 |
| 9 | 2 | 2015-12-31 09:00:00 | 1 | 3 | 3 |
| 9 | 2 | 2015-12-31 09:30:00 | -1 | NULL | 4 |
| 8 | 2 | 2015-12-31 10:00:00 | -1 | NULL | 5 |
| 7 | 2 | 2015-12-31 10:30:00 | -1 | NULL | 6 |



| 10 | 2 | 2015-12-31 11:00:00 | 1 | 7 | 7 |
| 10 | 2 | 2015-12-31 11:30:00 | -1 | NULL | 8 |
| 11 | 2 | 2015-12-31 12:00:00 | -1 | NULL | 9 |
| 12 | 2 | 2015-12-31 12:04:00 | 1 | 10 | 10 |
| 12 | 2 | 2015-12-31 12:30:00 | -1 | NULL | 11 |

记住，最大计数必然落在某一个开始事件上；计算结束事件附近的计数是没有意义的。你现在知道了对于每个开始事件，到目前为止有多少个开始事件（`s`）以及多少个开始和结束事件（`se`）。基于这两个数字，你计算活跃区域的数量为到目前为止的开始事件数减去到为止的结束事件数（`se - s`）。你在针对 CTE `C2` 的查询中计算此值（称为 `cnt`）。最后一步是按账户对行进行分组并计算每个组的最大计数，如下所示：

```sql
SELECT actid, MAX(cnt) AS mx
FROM C2
CROSS APPLY (VALUES(s - (se - s))) AS A(cnt)
GROUP BY actid;
```

该查询的执行计划如图 7-9 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_488_0.png)

**FIGURE 7-9** 使用 `ROW_NUMBER` 函数计算最大并发区的计划。

```sql
C2 AS
(
SELECT *,
ROW_NUMBER() OVER(ORDER BY ts, sessionid) AS se
FROM C1
)
SELECT MAX(cnt) AS mx
FROM C2
CROSS APPLY (VALUES(s - (se - s))) AS A(cnt);
GO
```

查询 `Accounts` 表，并使用 `CROSS APPLY` 运算符应用该账户的内联 TVF（为了演示目的，使用了跟踪标记 8649 来创建并行计划）：

```sql
SELECT A.actid, C.mx
FROM dbo.Accounts AS A
CROSS APPLY dbo.MaxConcurrent(A.actid) AS C
OPTION(QUERYTRACEON 8649);
```

我为此查询得到了图 7-10 所示的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_489_0.png)

**7-10 并行连接处理最大并发间隔的解决方案：通过并行扫描连接 `Accounts` 表，然后使用重分区流（Repartition Streams）使用轮询算法将工作分配到不同的线程。这导致嵌套循环连接的内部分支为每个线程处理一个账户的工作。因此，尽管每个账户由一个线程处理，但多个账户是并行处理的。该计划在我的系统上花费了八秒完成。与第一个解决方案 10 小时的运行时间相比，这非常惊人。**

# 区间打包 (Packing intervals)

打包涉及区间的另一个经典任务。其思想是将所有交叉的区间合并为一个打包区间。根据我们的示例数据，你需要按账户对 `Sessions` 表中的区间进行打包，以便获得每个账户拥有多少小时的连续区间。

例如，假设一个账户有以下区间：[p1, p4], [p2, p3], [p4, p7], [p9, p12] 和 [p12, p14]。打包后的区间为 [p1, p7] 和 [p9, p14]。观察到，如果一个区间在另一个区间结束时开始，这两个就会打包在一起。以下是 `Sessions` 表中样本数据集表示的区间打包的预期结果：

| actid | startTime | endTime |
|---|---|---|
| 1 | 2015-12-31 08:00:00 | 2015-12-31 09:30:00 |
| 2 | 2015-12-31 10:00:00 | 2015-12-31 12:30:00 |
| 2 | 2015-12-31 08:00:00 | 2015-12-31 11:30:00 |
| 2 | 2015-12-31 11:32:00 | 2015-12-31 12:00:00 |
| 2 | 2015-12-31 12:04:00 | 2015-12-31 12:30:00 |
| 3 | 2015-12-31 08:00:00 | 2015-12-31 09:00:00 |

与最大并发间隔任务一样，打包任务也有较旧的传统解决方案，这些解决方案在基于窗口函数的求解器上运行得非常好且速度更快。我将跳过这些传统解决方案，直接跳到相同区间的开始。索引定义是相同的——即为开始事件和结束事件创建单独的索引。如果你目前在 `Sessions` 表上没有 `idx_start` 和 `idx_end` 索引，请运行以下代码创建它们：

```sql
CREATE UNIQUE INDEX idx_start ON dbo.Sessions(actid, startTime, sessionid);
CREATE UNIQUE INDEX idx_end ON dbo.Sessions(actid, endTime, sessionid);
```

你基于与处理最大并发间隔任务相似的概念来处理打包任务，但在此增加了额外的复杂性。此外，在打包时，你正在计算活动区间的计数，可以使用窗口聚合函数或使用 `ROW_NUMBER` 函数来计算计数。我将首先描述使用窗口聚合的解决方案。

第一步是生成一个统一的时间顺序事件序列，其中用 +1 类型标记开始事件，用 -1 类型标记结束事件。使用基于该查询实现的 CTE `C1`。

第二步是通过应用 `type` 列的运行加和（running sum）来计算活动区间的计数。然而，打包任务中的运行计算与最大并发间隔任务相比有两个不同点。其一是在窗口 `ORDER BY` 子句中，你使用 `DESC` 作为同时发生的开始和结束事件的决胜因素。在进行区间打包时，你希望事件属于同一个打包区间，通过将开始事件置于结束事件之前，你可以确保计数在打包区间期间不会降为零。第二个不同点是，当事件为开始事件时，为了打包，你需要从计数中减去 1，以反映在应用事件之前有多少个区间活跃。对于结束事件，你实际上需要计数反映事件应用后的状态，在这种情况下不需要减去任何内容。减法逻辑可以使用 `CASE` 表达式处理。你定义一个 CTE 来处理此逻辑。

```sql
WITH C1 AS
(
SELECT sessionid, actid, starttime, +1 AS type
FROM dbo.Sessions

UNION ALL

SELECT sessionid, actid, endtime, -1 AS type
FROM dbo.Sessions
),
C2 AS
(
SELECT *,
SUM(type) OVER(PARTITION BY actid
ORDER BY ts, type DESC
ROWS UNBOUNDED PRECEDING)
- CASE WHEN type = 1 THEN 1 ELSE 0 END AS cnt
FROM C1
)
```

这段代码生成了账户 2 的以下输出：

| sessionid | actid | type | cnt |
|---|---|---|---|
| ... | ... | ... | ... |

第三步是过滤出代表点，即 `cnt` 为 0 的事件。你需要计算分区标识符（命名为 `p`），以便分组。`p` 的计算方法是 `FLOOR((ROW_NUMBER() OVER(PARTITION BY actid ORDER BY ts) + 1) / 2)`。注意在 SQL Server 中不需要显式对结果进行取整，但在其他平台（如 Oracle）默认得到的是数值除法，因此需要 `FLOOR` 函数。为了让解决方案更具移植性，即使在 SQL Server 中不需要，我也使用了这种形式。

你定义一个基于该查询的 CTE `C3`。

最后，查询 `C3`，按账户和分区标识符分组，然后返回打包区间的起始时间戳和结束时间戳。这是完整的解决方案代码：

```sql
WITH C1 AS
(
SELECT sessionid, actid, starttime, +1 AS type
FROM dbo.Sessions

UNION ALL

SELECT sessionid, actid, endtime, -1 AS type
FROM dbo.Sessions
),
C2 AS
(
SELECT *,
SUM(type) OVER(PARTITION BY actid
ORDER BY ts, type DESC
ROWS UNBOUNDED PRECEDING)
- CASE WHEN type = 1 THEN 1 ELSE 0 END AS cnt
FROM C1
),
C3 AS
(
SELECT *,
FLOOR((ROW_NUMBER() OVER(PARTITION BY actid ORDER BY ts) + 1) / 2) AS p
FROM C2
WHERE cnt = 0
)
SELECT actid, MIN(ts) AS startTime, MAX(ts) AS endtime
FROM C3
GROUP BY actid, p;
```

该查询在我的系统上花费了 54 秒完成。

就像最大并发间隔任务一样，在打包任务中，你可以使用窗口聚合函数通过 `ROW_NUMBER` 函数更高效地计算并发区间计数。为了打包，你需要对之前的计算进行一些调整，但总体思路非常相似。

一个调整是序数 `se` 的计算，它计算开始和结束事件。记住，为了打包，当开始和结束事件同时发生时，它们被视为同一个打包区间。因此，在计数的 `ROW_NUMBER` 函数的窗口子句中，你指定 `type DESC`（与之前的升序相反）作为 `ts` 的决胜因素，以防止计数在打包区间期间降为零。

另一个调整是开始事件计数的计算（之前称为 `cnt`，现在称为 `cs`）。为了打包，你需要计数反映事件应用之前的状态。因此，你需要从之前的计算中减去 1，得到 `s - (se - s) - 1`。

解决方案的计划如图 7-11 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_494_0.png)

### 7-11 针对 Packing 任务基于 ROW_NUMBER 的解决方案计划。

该解决方案在我的系统上耗时 26 秒完成。

与之前的任务类似，在 Packing 任务中，你可以通过将单个账户的工作封装在内联表值函数（inline TVF）中，然后使用 `APPLY` 算符将 TVF 应用于 `Accounts` 表，进一步提高并行处理能力。运行以下代码定义内联 TVF：

```sql
IF OBJECT_ID('dbo.PackedIntervals', 'IF') IS NOT NULL DROP FUNCTION dbo.PackedIntervals;
GO
CREATE FUNCTION dbo.PackedIntervals(@Actid AS INT) RETURNS TABLE
AS
RETURN
WITH C1 AS
(
SELECT sessionid, starttime AS ts, +1 AS type,
ROW_NUMBER() OVER(ORDER BY starttime, sessionid) AS s,
NULL AS e
FROM dbo.Sessions
WHERE actid = @Actid
UNION ALL
SELECT sessionid, endtime AS ts, -1 AS type,
NULL AS s,
ROW_NUMBER() OVER(ORDER BY endtime, sessionid) AS e
FROM dbo.Sessions
WHERE actid = @Actid
),
C2 AS
(
SELECT *,
ROW_NUMBER() OVER(ORDER BY ts, type DESC, sessionid) AS se
FROM C1
),
C3 AS
(
SELECT *,
FLOOR((ROW_NUMBER() OVER(ORDER BY ts) + 1) / 2) AS p
FROM C2
CROSS APPLY (VALUES(s - (se - s) - 1, (se - s))) AS A(cs, ce)
WHERE cs = 0 OR ce = 0
)
SELECT MIN(ts) AS startTime, MAX(ts) AS endtime
FROM C3
GROUP BY p;
```

然后使用以下查询将 TVF 应用到 `Accounts` 表（再次，为了演示目的，使用了 TF 8649 来强制并行）：

```sql
SELECT A.actid, P.starttime, P.endtime
FROM dbo.Accounts AS A
CROSS APPLY dbo.PackedIntervals(A.actid) AS P
OPTION(QUERYTRACEON 8649);
```

图 7-12 显示了我在系统上针对该查询获得的计划。

![](img/bdc38aa36f6e2987d913ee5381474711_495_0.png)

**图 7-12 改进并行处理的 Packing 任务解决方案计划。**

该查询在我的系统上仅需 10 秒即可完成。

## 结论



# 第 8 章 适用于 BI 从业者的 T-SQL

全球的事务型数据库中已经存在海量数据。分析这些数据的需求远未满足。数据库和业务智能（BI）开发者每天需要创建成千上万甚至数百万份报告。其中许多报告包含统计分析。数据的统计分析对于数据概览和数据质量评估很有用，而这是更深层次分析的两个典型初始阶段。然而，Microsoft SQL Server 中的统计函数并不多。此外，T-SQL 从业者中对统计学的良好理解并不常见。

本章解释了统计分析的基础知识。它介绍了许多使用 T-SQL 和公共语言运行时（CLR）代码计算统计数据的多种方法。这些代码基于实战经验。我是为了自己开发这些代码，因为我正在处理 BI 项目，特别是数据挖掘，并且在许多项目的初始阶段需要创建大量的统计查询。当然，市上有许多可以购买的统计包。我的许多客户都不允许在系统上安装任何额外软件。因此，我唯一可以依赖的软件就是 SQL Server。

优化统计查询与优化事务查询不同。为了计算统计数据，查询通常会扫描所有数据。如果查询太慢，你可以准备一份数据的随机样本，然后扫描该样本数据。然而，如果查询盲目地遵循原始逻辑，许多查询会通过对数据进行多次扫描来完成。优化此类查询意味着尽可能减少遍历数据的次数。为了实现这一点，你通常需要开发一种使用加法数学的算法，将公式转换为 SQL Server 中可以优化的等效公式。你还需要深入理解 T-SQL。例如，你需要对窗口函数和计算有非常深入理解。除了教你统计学和统计查询外，本章还将帮助你优化查询，以便高效地编写非统计查询。

## 数据准备

在开始任何统计分析之前，你需要了解你正在分析什么。在统计学中，你通过变量来分析案例（cases）。用 SQL Server 的术语来说，你可以将一个案例看作表中的行，将一个变量看作同一表中的列。对于大多数统计分析，你需要了解你正在分析什么……（注：此处原文内容似乎是重复的，已按要求翻译并保留逻辑）。

## 频率

若要快速概述离散变量，请使用频率表。在频率表中，你可以显示数值、这些数值的绝对频率、绝对百分比、累计频率、累计百分比以及绝对百分比的直方图。

### 不使用窗口函数的频率

计算绝对频率和绝对百分比是一个简单的聚合。然而，计算累计频率和累计百分比意味着计算总和（running totals）。在 SQL Server 2012 增加对带框架（frame）的窗口聚合函数支持之前，完成此任务需要使用相关子查询或非等值自连接。这两种方法都相当低效。

运行以下代码分析类别变量的频率分布，它实现了一种使用相关查询的解决方案：

```sql
WITH FCTE AS (
SELECT category,
COUNT(category) AS absfreq,
ROUND(100. * COUNT(category)) / (SELECT COUNT(*) FROM dbo.SalesAnalysis), 4) AS absperc
FROM dbo.SalesAnalysis
GROUP BY category
)
SELECT C1.category,
C1.absfreq,
(SELECT SUM(C2.absfreq) FROM FCTE AS C2
WHERE C2.category <= C1.category) AS cumfreq,
CAST(ROUND(C1.absperc, 1) AS INT) AS absperc,
CAST(ROUND((SELECT SUM(C2.absperc) FROM FCTE AS C2
WHERE C2.category <= C1.category), AS INT) AS cumperc,
CAST(REPLICATE('*', C1.absPerc) AS VARCHAR(100)) As histogram
FROM FCTE AS C1
ORDER BY C1.category;
```

| categoryname | absfreq | cumfreq | absperc | cumperc | histogram |
|---|---|---|---|---|---|
| Beverages | 404 | 404 | 19 | 19 | ************* |
| Condiments | 216 | 620 | 10 | 29 | ************* |
| Confections | 334 | 954 | 15 | 44 | ************* |
| Dairy Products | 366 | 1320 | 17 | 61 | ************* |
| Grains/Cereal | 196 | 1516 | 9 | 70 | ****** |
| Meat/Poultry | 173 | 1689 | 8 | 78 | ****** |
| Produce | 136 | 1825 | 6 | 84 | ****** |
| Seafood | 330 | 2155 | 15 | 100 | ************* |

### 使用窗口函数的频率

一种高效多的解决方案是使用了 SQL Server 2012 及更高版本中提供的带框架的窗口聚合函数。查询的第一部分（即计算绝对数量的通用表表达式查询）与上一个查询相同。然而，累计值（也称为运行总和）是通过窗口聚合函数计算的。

```sql
WITH CTE AS (
  SELECT categoryname,
  COUNT(categoryname) AS absfreq,
  ROUND(100.0 * COUNT(categoryname)) / 
  (SELECT COUNT(*) FROM dbo.SalesAnalysis), 4) AS absperc
  FROM dbo.SalesAnalysis
  GROUP BY categoryname
)
SELECT categoryname,
absfreq,
SUM(absfreq)
  OVER(ORDER BY categoryname
    ROWS BETWEEN UNBOUNDED PRECEDING
    AND CURRENT ROW) AS cumfreq,
CAST(ROUND(absperc, 0) AS INT) AS absperc,
CAST(ROUND(SUM(absperc))
  OVER(ORDER BY categoryname
    ROWS BETWEEN UNBOUNDED PRECEDING
    AND CURRENT ROW) * 0) AS AS CumPerc,
CAST(REPLICATE('*',absperc) AS VARCHAR(50)) AS histogram
FROM CTE
ORDER BY categoryname;
```

当然，此查询的输出与上一个查询的输出相同。

我发现了另一个使用窗口分析的有趣解决方案。`CUME_DIST` 函数计算值组中某个值的累计分布。也就是说，`CUME_DIST` 计算指定值在一组值中的相对位置。对于行 `r`，在假设排序的情况下，`r` 的 `CUME_DIST` 是值小于或等于 `r` 值的行数，除以分区中的行数。`PERCENT_RANK` 函数计算行在行组内的相对排名。`PERCENT_RANK` 评估一个值在查询集中的地位。

以下查询按 `categoryname` 分区计算行号，并对整个集计算一次。它还计算了完整输入上的百分比排名和累计分布：

```sql
SELECT categoryname,
ROW_NUMBER() OVER(PARTITION BY categoryname) AS rn_absfreq,
ROW_NUMBER() OVER(
  ORDER BY categoryname, orderid, productid) AS rn_cumfreq,
PERCENT_RANK()
  OVER(ORDER BY categoryname) AS pr_absperc,
CUME_DIST()
  OVER(ORDER BY categoryname, orderid, productid) AS cd_cumerc
FROM dbo.SalesAnalysis;
```

带有行的部分输出对于显示计算频率的算法很有意义：

| categoryname | rn_absfreq | rn_cumfreq | pr_absperc | cd_cumerc |
|---|---|---|---|---|
| Beverages | 1 | | 0.0024750312296838 |
| Beverages | 2 | | 0.0049500624593675 |
| Beverages | 404 | 404 | 0.18747099769814 |
| Condiments | | 105 | 0.187558031569174 | 0.187395034802784 |
| Condiments | 216 | 620 | 0.287730316241299 |
| Confections | | 621 | 0.287865383101207 | 0.28817605334629 |

如你所见，类别中的最后一行实际上代表了该类别中值的绝对频率。类别中的行号代表了截至并包括当前值的累计频率。例如，饮料的绝对频率为 404，调料的绝对频率为 216，累计频率为 620。`CUME_DIST` 函数在输出中的 `cd_cumerc` 反映了该类别的累计百分比。如果你从类别的累计频率中减去 `pr_absperc`，就会得到该类别的绝对频率。例如，饮料的绝对频率为 404，调料的绝对频率为 216，累计频率为 620。`CUME_DIST` 函数在输出中的 `cd_cumerc` 反映了该类别的累计百分比。如果你从该类别的累计频率中减去 `pr_absperc`，就会得到该类别的绝对频率。

以下查询使用排序来计算频率分布：

```sql
WITH FreqCTE AS (
SELECT categoryname,
ROW_NUMBER() OVER(PARTITION BY categoryname) AS rn_absfreq,
ROW_NUMBER() OVER(
  ORDER BY categoryname, orderid, productid) AS rn_cumfreq,
PERCENT_RANK()
  OVER(ORDER BY categoryname) AS pr_absperc,
CUME_DIST()
  OVER(ORDER BY categoryname, orderid, productid) AS cd_cumerc
FROM dbo.SalesAnalysis
)
SELECT categoryname,
MAX(rn_absfreq) AS absfreq,
MAX(rn_cumfreq) AS cumfreq,
ROUND(MAX(cd_cumerc) - MAX(pr_absperc), 0) AS absperc,
ROUND(MAX(cd_cumerc), 0) AS cumperc,
CAST(REPLICATE('*',ROUND(MAX(cd_cumerc),0) - MAX(pr_absperc),0) AS VARCHAR(100)) AS histogram
FROM FreqCTE
GROUP BY categoryname
ORDER BY categoryname;
GO
```

虽然上一个查询的概念很有趣，但它的效率不如使用窗口函数的查询。

## 众数

众数是分布中最流行的值——“mode”在法语中正是“时尚”的意思。计算众数简单且直接。在下面的查询中，我使用 `TOP (1) WITH TIES` 表达式来获取 `salesamount` 变量分布中频率最高的值。

```sql
SELECT TOP (1) WITH TIES salesamount, COUNT(*) AS number
FROM dbo.SalesAnalysis
GROUP BY salesamount
ORDER BY COUNT(*) DESC;
```

结果如下：

| salesamount | number |
|---|---|
| 360.00 | 29 |

需要 `WITH TIES` 子句是因为在分布中可能存在多个出现次数相同的值。我们将具有多个众数的分布称为双峰分布、三峰分布等，以此类推。

## 中位数

中位数是将分布一分为等两部分的值。对于所选变量，值小于中位数的行数必须等于大于中位数的行数。如果行数是奇数，则中位数是中间那行。如果行数是偶数，中位数可以定义为中间两行的平均值（财务中位数）、它们较小的一个（低统计中位数）或它们较大的一个（高统计中位数）。

`PERCENTILE_DISC` 函数计算整行或行内不同分区中排序值的特定百分位数。对于给定的百分位数 $P$，`PERCENTILE_DISC` 对 `ORDER BY` 子句中的表达式值进行排序，并返回大于或等于 $P$ 且（相对于相同的排序规格）具有最小 `CUME_DIST` 的值。`PERCENTILE_DISC` 根据列值的离散分布计算百分位数；结果等于列中的某个特定值。因此，`PERCENTILE_DISC (0.5)` 函数计算的是低统计中位数。

`PERCENTILE_CONT` 函数在 SQL Server 中根据列值的连续分布计算百分位数。它是通过插值计算的，可能不等于列中的任何特定值。因此，该函数计算的是财务中位数。财务中位数是目前常用的中位数。

以下代码展示了 `PERCENTILE_DISC` 和 `PERCENTILE_CONT` 函数之间的区别。它创建了一个简单的表，并为表的唯一列插入了值为 1, 2, 3 和 4 的四行。然后它计算了低统计中位数和财务中位数：

```sql
IF OBJECT_ID('N''dbo.TestMedian','N''U') IS NOT NULL
GO
CREATE TABLE dbo.TestMedian
(
val INT NOT NULL
);
INSERT INTO dbo.TestMedian (val)
VALUES (1), (2), (3), (4); -- 也可以使用 TOP (1)
SELECT DISTINCT
PERCENTILE_DISC(0.5) WITHIN GROUP (ORDER BY val) OVER () AS mediandisc,
PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY val) OVER () AS mediancont
FROM dbo.TestMedian
GO
```

代码的结果为：

```
mediandisc          mediancont
--------------------
2                   2.5
```

你可以清楚地看到这两个百分位数函数之间的区别。我在下面的查询中计算了 `SalesAnalysis` 视图中 `salesamount` 列的中位数：

```sql
SELECT DISTINCT
PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY salesamount) OVER () AS median
FROM dbo.SalesAnalysis;
```

查询返回以下结果：

```
median
360
```

在这种情况下，对于 `salesamount` 列，众数和中位数相等。然而，这并不意味着分布是偏态的。在得出关于偏度的任何结论之前，我还需要计算平均值。

## 平均值

平均值是确定分布中心最常用的指标。它也可能是最被滥用的统计指标。在没有标准差（在本章稍后解释）的情况下，平均值没有意义，且绝不应单独使用。让我给你举个例子。假设有两对人。在第一对中，两个人的工资相同——假设每年赚 80,000 美。在第二对中，一个人每年赚 30,000 美，另一个人每年赚 270,000 美。第一对的平均值是 80,000 美，而第二对的平均值是每年 150,000 美。通过仅列出平均值，可能会得出第二对中每个人的收入都高于第一对中的任何一个人。然而，你可以清楚地看到，这是一个严重错误的结论。

平均值的定义非常简单：它是连续变量所有值之和除以案例数量，如下公式所示：

```
\mu = \frac{1}{n} \sum_{i=1}^{n} v_i
```

由于平均值的极大重要性，T-SQL 语言包含了 `AVG` 函数。下面的查询使用它来计算 `salesamount` 变量的平均值：

```sql
SELECT AVG(salesamount) AS mean
FROM dbo.SalesAnalysis;
```

查询结果为：

```
mean
------
628.519067
```

将此值与中位数和众数（360）进行比较。显然，平均值高得多；这意味着分布是右偏的，在右侧有一个由不经常出现的高值构成的长尾巴——即值较大较大的一侧。

财务中位数是目前最常用的中位数。（原文重复段落已合并）

财务中位数是目前最常用的中位数。（原文重复段落已合并）



平均值是目前最常用的中位数。（等等，原文说：“The financial median is by far the most-used median.”我将保留它）。

平均值是目前最常用的中位数。（等等，原文说：“The financial median is by far the most-used median.”我将保留它）。

平均值是目前最常用的中位数。（等等，原文说：“The financial median is by far the most-used median.”我将保留它）。

平均值是目前最常用的中位数。（等等，原文说：“The financial median is by far the most-used median.”）。

平均值是目前最常用的中位数。（等等，原文说：“The financial median is by far the most-used median.”）。我将继续。

平均值是目前最常用的中位数。（等等，原文说：“The financial median is by far the most-used median.”）。

实际上，我将继续计算。

## 分布的离散程度

正如提到的，你需要知道观测值的离散程度。与中心性类似，离散程度可以通过几种方式来衡量。我将讨论最常用的几种：极差、四分位距、方差和标准差。

## 极差

极差是最简单的离散程度衡量方法；它是最大值和最小值之间的绝对距离。（让我们快速回顾：单个观测值表示为表中的行。）极差的公式为：

```
R = v_{max} - v_{min}
```

当然，你使用 `MAX` 和 `MIN` 聚合函数来计算极差。

```sql
SELECT MAX(salesamount) - MIN(salesamount) AS range
FROM dbo.SalesAnalysis;
```

你得到以下输出：

```
range
-------
1580.20
```

### 四分位距

中位数是将分布一分为等两部分的值。你可以进一步划分分布——例如，将每一部分再次二分。让我们泛化这个划分过程。对所选列对行（案例、观测值）进行排序。百分位数排名是一个相对量，它告诉你有百分比的观测值小于该值。通过将观测值划分为分位数，你得到了所有行的三个百分位数（25%、50% 和 75%），并且你可以读取这些位置的值，它们重要到有自己的名字：第二四分位数就是中位数。第一个是低四分位数，第三个是高四分位数。如果你从高四分位数（第三个）减去低四分位数（第一个），就得到了四分位距（IQR）的公式：

```
IQR = Q3 - Q1
```

使用窗口分析函数 `PERCENTILE_CONT` 计算 IQR 非常简单：

```sql
SELECT DISTINCT
PERCENTILE_CONT(0.75) WITHIN GROUP (ORDER BY salesamount) OVER (),
PERCENTILE_CONT(0.25) WITHIN GROUP (ORDER BY salesamount) OVER () AS IQR
FROM dbo.SalesAnalysis;
```

该查询返回以下结果：

```
IQR
-------
568.25
```

四分位距像中位数一样具有抗性。这意味着它对单个观测值的剧烈波动不敏感。（让我们快速回顾：单个观测值是表中的单行。）这种抗性是逻辑上的，因为你只使用了两个观测值。

## 平均绝对偏差

对于四分位距（IQR），你只使用了观测值：下四分位数和上四分位数。是否存在一种同时考虑这两个观测值的标准？你可以测量每个值与平均值之间的距离，并将其称为偏差。所有距离之和给出了总体离散程度的衡量标准。你必须考虑某些距离是正的，而另一些是负的；它们相互抵消，因此总和正好为零。偏差的平均值也是如此，这将是一个无用的离散程度衡量标准。你通过忽略符号，转而使用距离的绝对值来解决这个问题。通过计算偏差的平均值，你得到了平均绝对偏差（MAD）的公式：

```
MAD = \frac{1}{n} \sum_{i=1}^{n} |V_i - \mu|
```

从 MAD 公式可以看出，你需要使用 `AVG` T-SQL 聚合函数计算平均值，并在 `SUM` T-SQL 聚合函数中使用此聚合。然而，SQL Server 无法对包含聚合函数或子查询的表达式执行聚合函数；因此，我将通过将平均值存储到变量中来实现：

```
DECLARE @mean NUMERIC(10,2);
SET @mean = (SELECT AVG(salesamount) FROM dbo.SalesAnalysis);
SELECT SUM(ABS(salesamount - @mean))/COUNT(*) AS MAD
FROM dbo.SalesAnalysis;
```

你得到以下输出：

```
MAD
527.048886
```

## 平方偏差

避免偏差符号问题的另一种方法是每个每个偏差平方。通过对 MAD 公式进行微调——具体来说，计算平方偏差的平均值而不是绝对偏差——你得到了均方偏差（MSD）的公式：

```
MSD = \frac{1}{n} \sum_{i=1}^{n} (V_i - \mu)^2
```

要计算 MSD，你需要稍微修改 MAD 的查询：

```sql
DECLARE @mean AS NUMERIC(10,2);
SET @mean = (SELECT AVG(salesamount) FROM dbo.SalesAnalysis);
SELECT SUM(SQUARE(salesamount - @mean))/COUNT(*) AS MSD
FROM dbo.SalesAnalysis;
```

查询返回了 MSD 的以下结果：

## 自由度与方差

假设你暂时只有一个观测值（n=1）。这个观测值也是你的样本平均值，但完全没有离散性。只有当 n 超过 1 时你才能计算离散性。考虑到第一个观测值是你的平均值，只有 (n-1) 个信息可以帮助你计算离散性。这些信息被称为自由度。你也可以将自由度视为可以信息的数量。例如，想象一个取五个不同离散状态的变量。你需要计算所有状态的频率以知道变量的分布；最后一个状态的频率是由你计算的前四个状态的频率决定的，而且它们不能改变，因为所有状态的累计百分比必须等于 100%。

记住，所有偏差之和在不抵消符号的情况下始终始终为 0。只有 (n-1) 个偏差是自由的；最后一个严格由其他部分决定。方差（Var）的定义与 MSD 的定义相似；你只需要将 n 的数量替换为自由度（n-1）：

```
Var = \frac{1}{n-1} \sum_{i=1}^{n} (v_i - \mu)^2
```

这是样本方差的公式，用作总体方差的估计值。现在假设你的数据代表完整的总体，且平均值未知。那么所有观测值对方差计算的贡献都是等的，自由度也就没有意义了。那么总体方差的定义与 MSD 使用相同的公式：

```
Var = \frac{1}{n} \sum_{i=1}^{n} (v_i - \mu)^2
```

Transact-SQL 包含一个计算样本方差作为总体方差估计值的聚合函数（`VARP` 函数）以及一个计算总体方差的函数（`VAR` 函数）。一个查询计算了这两种方差并通过两种方式比较了它们：通过将它们相除，以及将案例数减 1 除以案例数，以证明这种差异仅仅是计算样本方差作为总体方差估计值时使用的自由度的结果：

```sql
SELECT VAR(salesamount) AS populationvariance,
VAR(salesamount) AS samplevariance,
VAR(salesamount) / VAR(salesamount) AS samplepopulation1,
(1.0 * COUNT(*)) / COUNT(*) AS samplepopulation2
FROM dbo.SalesAnalysis;
```

查询返回以下内容：

| populationvariance | samplevariance | samplepopulation1 | samplepopulation2 |
|---|---|---|---|
| 107463.8010215 | 103765.3018194 | 0.99953596287703 | 0.99953596287703 |

如果你的样本足够大，差异是可以忽略不计的。在我分析销售额的示例中，数据代表完整的销售额——即总体。因此，使用总体方差对于正确的分析更为合适。

## 标准差与变异系数

为了补偿偏差符号的问题，对方差取平方根。通过对 MAD 公式进行微调——具体来说，计算平方偏差的平均值而不是绝对偏差——你可以得到标准差的定义：

$\sigma = \sqrt{Var}$

标准差的定义与正态分布类似。正态分布的参数（σ）是总体方差的平方根。标准差是用来描述变量分布程度的标准差。变异系数（CV）是标准差与平均值的简单比例：

$CV = \frac{\sigma}{\mu}$

Transact-SQL 包含一个计算样本方差作为总体方差估计值的聚合函数（`STDEVP`）以及一个计算总体方差的函数（`STDEV`）。以下查询计算了这两种方差并通过两种方式比较了它们：通过将它们相除，以及将案例数减 1 除以案例数：

```sql
SELECT STDEVP(salesamount) AS populationvariance,
STDEV(salesamount) AS samplevariance,
STDEVP(salesamount) / AVG(salesamount) AS samplepopulation1,
(1.0 * COUNT(*)) / COUNT(*) AS samplepopulation2
FROM dbo.SalesAnalysis;
```

查询返回以下内容：

| populationvariance | samplevariance | samplepopulation1 | samplepopulation2 |
|---|---|---|---|
| 1036.4669794752 | 1036.2264726332 | 1.64906211150028 | 3.2568658182147 |

你可以看到销售额的波动。

## 高阶矩量

通过比较平均值和中，你可以判断你的分布是否偏斜。你也可以衡量这种偏度？当然，答案是定的。然而，在定义和计算这种衡量之前，你需要定义正态分布和标准正态分布。

## 正态分布与标准正态分布

正态分布是一类具有相同形状的分布。正态分布是对称的，得分集中在中间。描述为钟形。钟形曲线也称为高斯曲线，以高斯命名。

正态分布的高度在数学上通过两个参数指定：平均值（μ）和标准差（σ）。公式中的常数有 π（3.14159）和 e（自然对数的底）。正态分布的公式为：

```
f(x,\mu,\sigma) = \frac{1}{\sqrt{2\pi}} * e^{-(x-\mu)^2/2\sigma^2}
```

正态分布是一种常见的连续概率分布。它是真实观测落在任何真实范围内的概率函数，曲线在两侧趋于零。正态分布在分布未知的统计中非常重要。它们经常用于自然科学和社会科学中分布未知的实值随机变量。简单来说，如果你预先不知道连续变量的分布，就假设它遵循正态分布。

标准正态分布（Z分布）是均值为 0、标准差为 1 的正态分布。通过对正态分布的 x 值标准化，你可以轻松地计算标准正态分布的 z 值：

```
z = \frac{x-\mu}{\sigma}
```

图 8-1 显示了距离平均值几个标准差之外的概率下降得很快。图中显示了距离平均值两侧四个标准差的概率函数。在本章的晚些部分，我将向你展示如何计算这种概率。

![](img/bdc38aa36f6e2987d913ee5381474711_512_0.png)

## 偏度 (Skewness)

偏度是描述随机变量概率分布不对称性的参数。偏度刻画了分布围绕其均值的不对称程度。正偏表示分布具有向更正值方向延伸的不对称尾部；负偏表示分布具有向更负值方向延伸的不对称尾部。

偏度告诉我们，你在均值一侧尾部的取值（取决于偏度是正还是负）可能仍然有效，你不希望将它们作为离群值处理。离群值是罕见且超出范围的值，可能是错误值。因此，了解变量的偏度不仅能提供关于变量分布的信息，还能在清洗数据时为你提供帮助。

偏度的公式为：

```
Skew = \frac{n}{(n-1)*(n-2)} * \sum_{i=1}^{n} (\frac{v_i - \mu}{\sigma})^3
```

与平均绝对偏差和平均平方偏差公式类似，偏度公式也使用了均值。此外，公式中还包含标准差。我使用低效的代码计算了 MAD 和 MSD；预先计算了均值以及 MAD 和 MSD。我使用这这两个离散度仅是为了逐渐引入常用的方差和标准差。对于方差和标准差，T-SQL 中包含了聚合函数。但没有偏度的聚合函数；因此，你需要优化代码。我想通过仅扫描数据来计算偏度。

我针对这项优化使用了一些数学方法。首先，我展开了第 $i$ 个立方值减去均值的公式：

```
(v_i - \mu)^3 = v_i^3 - 3v_i^2\mu + 3v_i\mu^2 - \mu^3
```

然后，我利用和对乘积的分配律，如仅针对两个值的公式所示：

$3v_1\mu^2 + 3v_2\mu^2 = 3\mu^2(v_1 + v_2)$

该公式可以推广到所有值：

- $\sum_{i=1}^n (3v_i\mu^2) = 3\mu^2\sum_{i=1}^n (v_i)$

当然，我也可以对展开公式中的剩余元素执行相同的数学运算，并在公表表达式 (CTE) 中通过对数据的单扫描来计算所需的所有聚合值，然后使用这些聚合值计算偏度，如下查询所示：

```
WITH SkewCTE AS (
SELECT SUM(salesamount) AS rx,
SUM(POWER(salesamount,2)) AS rx2,
SUM(POWER(salesamount,3)) AS rx3,
COUNT(salesamount) AS rn,
STDEV(salesamount) AS stdev,
AVG(salesamount) AS av
FROM dbo.SalesAnalysis
)
SELECT
(rx3 - 3*rx2*av + 3*rx*av*av - rn*av*av*av)
/(stdev*stdev) * rn / (rn-1) / (rn-2) AS skewness
FROM SkewCTE;
```

查询返回结果如下：

skewness

6.78219500069942

> **正偏**意味着 salesamount 变量的分布在右侧有更长的尾部，向正值方向延伸更多。

## 峰度 (Kurtosis)

峰度刻画了分布与正态分布相比的相对尖峰程度或平坦程度。正峰度表示均值周围有更高的峰，且任何一侧尾部存在极值。负峰度表示分布相对平坦。对于尖峰分布，可以考虑任何方向上远离均值的值可能是正确的。峰度的公式为：

- $Kurt = \frac{n*(n+1)}{(n-1)*(n-2)*(n-3)} * \sum_{i=1}^n \frac{(v_i-\mu)^4}{\sigma^4}$

与偏度一样，可以看到峰度公式也包含了均值和标准差。为了获得高效的查询，我再次展开减法：

```
$(v_i - \mu)^4 = v_i^4 - 4v_i^3\mu + 6v_i^2\mu^2 - 4v_i\mu^3 + \mu^4$
```

之后，我可以再次利用和对乘积的分配律，通过扫描数据来计算峰度，如下查询所示：

```
With KurtCTE AS (
SELECT SUM(salesamount) AS rx,
SUM(POWER(salesamount,2)) AS rx2,
SUM(POWER(salesamount,3)) AS rx3,
SUM(POWER(salesamount,4)) AS rx4,
COUNT(salesamount) AS rn,
STDEV(salesamount) AS stdv,
AVG(salesamount) AS av
FROM dbo.SalesAnalysis)
SELECT
(rx4 - 4*rx^3*av + 6*rx^2*av*av - 4*rx*av*av*av + rn*av*av*av*av) / (stdv*stdv*stdv) * rn * (rn+1) / (rn-1) / (rn-2) / (rn-3) AS kurtosis
FROM KurtCTE;
```

salesamount 变量的峰度结果为：

kurtosis

68.775694703992

峰值告诉你均值周围有很多 salesamount 值，因为分布中存在高峰；然而，该变量在两个尾部也有一些偏离均值的值。均值、标准差、偏度和峰度也是矩阶。均值在计算中使用一阶；标准差使用平方值，因此是二阶；偏度是三阶，而峰度是四阶。它们共同给出了良好的分布估计。

## 使用 CLR 计算偏度和峰度

计算偏度和峰度的查询比之前的要复杂。现在假设你需要在分组中计算这些这些值。在分组中计算均值和标准差是简单的，因为你有可以配合 `GROUP BY` 使用的 T-SQL 聚合函数。然而，使用 T-SQL 计算偏度和峰度会导致查询变得复杂。在 T-SQL 中无法定义自定义聚合 (UDA)，你需要公共语言运行时 (CLR) 来实现——你可以使用 SQL Server 数据库中的简单类。然后你可以直接复制以下用于偏度和峰度的 C# 代码，与 T-SQL 的单扫描高效计算具有相同的数学方法：

```csharp
using System;
using System.Data;
using System.Data.SqlClient;
using System.Data.SqlTypes;
using Microsoft.SqlServer.Server;
```



```csharp
[Serializable]
[UserDefinedAggregate(
    Format.Native,
    IsInvariantToDuplicates = false,
    IsInvariantToNulls = true,
    IsInvariantToOrder = true,
    IsNotEmpty = false)]
public struct Skew
{
    private double rx; // 当前值的和 (x)
    private double rx2; // 平方值的和 (x^2)
    private double r2x; // 两倍值的和 (2x)
    private double rx3; // 立方值的和 (x^3)
    private double r3x2; // 三倍平方值的和 (3x^2)
    private double r3x; // 三倍值的和 (3x)
    private Int64 rn; // 行数

    public void Init()
    {
        rx = 0;
        rx2 = 0;
        r2x = 0;
        rx3 = 0;
        r3x2 = 0;
        r3x = 0;
        rn = 0;
    }

    public void Accumulate(SqlDouble inVal)
    {
        if (inVal.IsNull)
        {
            return;
        }
        rx += inVal.Value;
        rx2 += Math.Pow(inVal.Value, 2);
        r2x += 2 * inVal.Value;
        rx3 += Math.Pow(inVal.Value, 3);
        r3x2 += 3 * Math.Pow(inVal.Value, 2);
        r3x += 3 * inVal.Value;
        rn += 1;
    }

    public void Merge(Skew Group)
    {
        this.rx += Group.rx;
        this.rx2 += Group.rx2;
        this.r2x += Group.r2x;
        this.rx3 += Group.rx3;
        this.r3x2 += Group.r3x2;
        this.r3x += Group.r3x;
        this.rn += Group.rn;
    }

    public SqlDouble Terminate()
    {
        double myAvg = (rx / rn);
        double myStDev = Math.Pow(rx2 - 2 * myAvg + rn * Math.Pow(myAvg, 2)) / (rn - 1) / 2d;
        double mySkew = (rx3 - r3x2 * myAvg + r3x * Math.Pow(myAvg, 2) / Math.Pow(myStDev, 3) * (rn - 1) / (rn - 2));
        return (SqlDouble)mySkew;
    }
}
```

```csharp
[Serializable]
[SqlUserDefinedAggregate(
    Format.Native,
    IsInvariantToDuplicates = false,
    IsInvariantToNulls = true,
    IsInvariantToOrder = true,
    IsNotEmpty = false)]
public struct Kurt
{
    private double rx; // 当前值的和 (x)
    private double rx2; // 平方值的和 (x^2)
    private double r2x; // 两倍值的和 (2x)
    private double rx4; // 当前值的四方的和 (x^4)
    private double r4x3; // 四倍值的立方的和 (4x^3)
    private double r6x2; // 平方值的六倍的和 (6x^2)
    private double r4x; // 四倍值的和 (4x)
    private Int64 rn; // 行数

    public void Init()
    {
        rx = 0;
        rx2 = 0;
        r2x = 0;
        rx4 = 0;
        r4x3 = 0;
        r6x2 = 0;
        r4x = 0;
        rn = 0;
    }

    public void Accumulate(SqlDouble inVal)
    {
        if (inVal.IsNull)
        {
            return;
        }
        rx += inVal.Value;
        rx2 += Math.Pow(inVal.Value, 2);
        r2x += 2 * inVal.Value;
        rx4 += Math.Pow(inVal.Value, 4);
        r4x3 += 4 * Math.Pow(inVal.Value, 3);
        r6x2 += 6 * Math.Pow(inVal.Value, 2);
        r4x += 4 * inVal.Value;
        rn += 1;
    }

    public void Merge(Kurt Group)
    {
        this.rx += Group.rx;
        this.rx2 += Group.rx2;
        this.r2x += Group.r2x;
        this.rx4 += Group.rx4;
        this.r4x3 += Group.r4x3;
        this.r6x2 += Group.r6x2;
        this.r4x += Group.r4x;
        this.rn += Group.rn;
    }

    public SqlDouble Terminate()
    {
        double myAvg = (rx / rn);
        double myStdDev = Math.Pow((rx2 - r2x * myAvg + rn * Math.Pow(myAvg, 2)) / (rn - 1), 1 / 2d);
        double myKurt = (rx4 - r4x3 * myAvg + r6x2 * Math.Pow(myAvg, 2) - 4 * Math.Pow(myAvg, 3) + rn * Math.Pow(myAvg, 4)) / (Math.Pow(myStdDev, 4) * (rn - 1) / (rn - 2) / (rn - 3)) - 3 * Math.Pow((rn - 1), 2) / (rn - 2) / (rn - 3);
        return (SqlDouble)myKurt;
    }
}
```

然后你就可以构建项目并将程序集（`.dll` 文件）部署到 SQL Server 实例。当然，你也可以使用带有源代码的项目，或者使用随书籍附带代码提供的预编译程序集。

一旦构建了程序集，你就需要对其进行部署。第一步是在你的 SQL Server 实例中启用 CLR：

```sql
EXEC sp_configure 'clr enabled', 1;
RECONFIGURE WITH OVERWRITE;
```

然后你部署程序集。部署程序集意味着将其导入数据库中。SQL Server 并不依赖于磁盘上的 `.dll` 文件。你可以直接从 Visual Studio 部署程序集。

# 第 8 章 适用于 BI 从业人员的 T-SQL

或者你可以使用 T-SQL `CREATE ASSEMBLY` 命令。以下命令假设 `DescriptiveStatistics.dll` 文件存在于 `C:\temp` 文件夹中。

```sql
CREATE ASSEMBLY DescriptiveStatistics
FROM 'C:\temp\DescriptiveStatistics.dll'
WITH PERMISSION_SET = SAFE;
```

将程序集导入你的数据库后，你可以使用 `CREATE AGGREGATE` 命令创建用户定义聚合函数。以下两个命令创建了偏度和峰度函数：

```sql
-- 偏度 UDA
CREATE AGGREGATE dbo.Skew(@skew float)
RETURNS float
EXTERNAL NAME DescriptiveStatistics.Skew;
GO

-- 峰度 UDA
CREATE AGGREGATE dbo.Kurt(@kurt float)
RETURNS float
EXTERNAL NAME DescriptiveStatistics.Kurt;
GO
```

部署 UDA 后，你可以像使用标准 T-SQL 聚合函数一样使用它们。例如，该查询计算了 `salesamount` 变量的偏度和峰度：

```sql
SELECT dbo.Skew(salesamount) AS skewness,
       dbo.Kurt(salesamount) AS kurtosis
FROM dbo.SalesAnalysis;
```

查询结果为：

| skewness | kurtosis |
| :--- | :--- |
| 6.78219499972001 | 68.7756494631014 |

当然，既然你已经有了 UDA，你也可以用它们来按组计算偏度和峰度。以下查询计算了 `employeecountry` 离散变量中 `salesamount` 连续变量的四种分布：

```sql
SELECT employeecountry,
       AVG(salesamount) AS mean,
       STDEV(salesamount) AS standarddeviation,
       dbo.Skew(salesamount) AS skewness,
       dbo.Kurt(salesamount) AS kurtosis
FROM dbo.SalesAnalysis
GROUP BY employeecountry;
```

结果为：

| employeecountry | mean | standarddeviation | skewness | kurtosis |
| :--- | :--- | :--- | :--- | :--- |
| UK | 665.538450 | 1151.18485127003 | 5.25006815618545 | 34.798294559445 |
| USA | 615.269533 | 992.247411594278 | 7.56375323252894 | ... |

# 表 8-4 变量与其自身的交叉表

| Zv/Zh | 1 | 2 | 3 | P(Zv) |
|---|---|---|---|---|
| 1 | 0.33 | 0 | 0 | 0.33 |
| 2 | 0 | 0.33 | 0 | 0.33 |
| 3 | 0 | 0 | 0.33 | 0.33 |
| P(Zh) | 0.33 | 0.33 | 0.33 | 1 |

单个变量方差的公式可以扩展为衡量变量与其自身协方差的公式：

```
Var(Z) = CoVar(Z,Z) = Σ (Z_{hi} - μ(Z_{hi})) * (Z_{vi} - μ(Z_{vi})) * P(Z_{hi}, Z_{vi})
```

这个公式似乎适用于两个变量。当然，我的本意是开发一个衡量两个变量组合概率分布的公式。我只需将其中一个变量——例如，将“水平”的 Z 替换为 X，将另一个（“垂直”的）Z 替换为 Y——即可得到协方差的公式：

```
CoVar(X,Y) = Σ (X_{i} - μ(X)) * (Y_{i} - μ(Y)) * P(X,Y)
```

现在，我从销售分析视图中计算两个变量组合的协方差。我可以将变量组合概率 `P(X,Y)` 替换为 n 行中每一行与其自身的概率——即 `1 / n²`——并将这 n 行的概率之和替换为 `1 / n`，因为每行的概率是相等的。以下是计算变量 `salesamount` 和 `discountamount` 协方差的查询：

```sql
WITH CoVarCTE AS (
    SELECT salesamount AS val1,
           AVG(salesamount) OVER () AS mean1,
           discountamount AS val2,
           AVG(discountamount) OVER() AS mean2
    FROM dbo.SalesAnalysis
)
SELECT SUM((val1-mean1)*(val2-mean2)) / COUNT(*) AS covar
FROM CoVarCTE;
```

该查询的结果是：

```
covar
----------------
7637.501912
```

协方差表示两个变量 X 和 Y 之间的相关性。当两个变量都出现较大值时，偏差都是正的（因为 `Xi - Mean(X) > 0` 且 `Yi - Mean(Y) > 0`），因此它们的乘积为正。同样，当出现较小值时，乘积也是正的。当一个为负而一个为正时，乘积为负。这可能发生在 X 的小值对应 Y 的大值时，反之亦然。如果正积的绝对值大于负积，则协方差为正；否则为负。如果正、负积相互抵消，协方差则为零。它们会相互抵消呢？嗯，你可以想象一下这种情况——当两个变量真正独立时。因此，协方差显然总结了变量之间的关系：

- 如果协方差为正，当一个变量的值较大时，另一个变量的值倾向也较大。
- 如果协方差为负，当一个变量的值较大时，另一个变量的值倾向于较小。
- 如果协方差为零，则变量是独立的。

# 相关系数与判定系数

当我推导出单个变量分布的公式时，我希望能比较两个或多个变量的离散程度。我必须推导出相对测量公式——*变异系数* (CV)：

```
CV = σ / μ
```

现在我想比较为两对变量计算的两个协方差。尝试找到一个类似的公式——将协方差除以某个值。结果证明，完美的分母是两个变量标准差的积。这就是相关系数的公式：

```
Correl(X, Y) = Covar(X, Y) / (σ(X) * σ(Y))
```

相关系数之所以是衡量两个变量关系的有用指标，是因为它是有界的：`-1 <= Corr <= 1`。如果变量是独立的，则相关性为零，因为协方差为零。如果变量之间存在完美的线性关系，相关系数可以取 1（例如，将一个变量与其自身相关）。同样，对于完美的负线性关系，相关系数将为 -1。系数的绝对值越大，变量之间的关系越密切。但显著性取决于样本量的大小。系数超过 0.50 通常被认为是显著的。然而，变量之间也可能存在因果关系。为了修正相关系数过大的值，通常对其进行平方并缩小。平方后的系数是*判定系数* (CD)：

```
CD(X, Y) = Correl(X, Y)^2
```

在统计学中，当判定系数高于 0.20 时，你通常可以拒绝零假设，这意味着两个连续变量不是独立的，而是相关的。以下查询计算了 `salesamount` 和 `discountamount` 变量的协方差、相关系数和判定系数：

```sql
WITH CovarCTE AS (
    SELECT salesamount as val1,
           AVG(salesamount) OVER () AS mean1,
           discountamount AS val2,
           AVG(discountamount) OVER () AS mean2
    FROM dbo.SalesAnalysis
)
SELECT SUM((val1-mean1)*(val2-mean2)) / COUNT(*) AS covar,
       SUM((val1-mean1)*(val2-mean2)) / (SQRT(SUM(SQUARE(val1-mean1))) * SQRT(SUM(SQUARE(val2-mean2)))) AS correlation,
       POWER(SUM((val1-mean1)*(val2-mean2)) / (SQRT(SUM(SQUARE(val1-mean1))) * SQRT(SUM(SQUARE(val2-mean2)))), 2) AS cd
FROM CovarCTE;
```



## 结果

| Slope1 | Intercept1 | Slope2 | Intercept2 |
|---|---|---|---|
| 0.071128953210513 | -3.56166730855091 | 4.25586107754898 | 453.4149144211 |

# 列联表与卡方检验

协方差和相关性衡量两个连续变量之间的依赖性。在计算过程中，它们都使用了涉及两个变量的平均值（相关性还使用了标准差）。对于分类（名义）变量，平均值和其他总体指标没有意义。

如果你在变量操作中将“文职”标记为 1，“专业”标记为 2，那么 1.5 的平均值意味着什么？你必须寻找另一种依赖性测试——一种不依赖数值的测试。你可以使用列联表和卡方检验。

列联表用于检查对象在两个定性或分类变量得分之间的关系。它们显示了两个变量在交叉表（透视）格式下的实际分布和预期分布。表 8-5 是职业列（行）和婚姻状况列（列）案例实际（或观测）与预期分布的示例：

### 表 8-5 列联表示例

| 职业/婚姻状况 | 已婚 | 单身 | 总计 |
|---|---|---|---|
| 文职 | 实际 | 4745 | 4388 | 9133 |
| | 预期 | 4946 | 4187 | 9133 |
| 专业 | 实际 | 5266 | 4085 | 9351 |
| | 预期 | 5065 | 4286 | 9351 |
| 总计 | 实际 | 10011 | 8473 | 18484 |
| | 预期 | 10011 | 8473 | 18484 |

如果列不依赖于行，则行频率和列频率是独立的。检验列是否依赖于行使用的是独立性卡方检验。零假设是行频率和列频率之间没有关系。因此，观测频率（O）和预期频率（E）之间不应该差异。

卡方仅仅是归一化频率平方偏差之和（即观测频率与预期频率之差平方除以预期频率之和）。该公式称为皮尔逊卡方公式。

```
\chi^2 = \frac{1}{n}\sum_{i=1}^{n} (O-E)^2
```

已经准备了带有卡方分布临界点的表格。如果计算出的卡方值在给定的自由度和特定置信水平下大于表格中的临界值，你就可以以该置信度拒绝零假设（即变量是相互依赖的）。自由度是列自由度（C）和行自由度（R）的乘积：

```
$DF = (C - 1) * (R - 1)$
```

表 8-6 是卡方临界点表示例。预期数据与实际数据之间的差异越大，产生的卡方值越大。卡方值越大，存在显著差异的概率越高。表格中的概率（Probability）行显示了当卡方值大于或等于特定自由度下表格中的值时，零假设成立的最大概率。

### 表 8-6 卡方临界点

| DF | 0.004 | 0.02 | 0.06 | 0.15 | 0.46 | 1.07 | 1.64 | 2.71 | 3.84 | 6.64 | 10.83 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 0.004 | 0.02 | 0.06 | 0.15 | 0.46 | 1.07 | 1.64 | 2.71 | 3.84 | 6.64 | 10.83 |
| 2 | 0.10 | 0.21 | 0.45 | 0.71 | 1.39 | 2.41 | 3.22 | 4.60 | 5.99 | 9.21 | 13.82 |
| 3 | 0.35 | 0.58 | 1.01 | 1.42 | 2.37 | 3.66 | 4.64 | 6.25 | 7.82 | 11.34 | 16.27 |
| 4 | 0.71 | 1.06 | 1.65 | 2.20 | 3.36 | 4.88 | 5.99 | 7.78 | 9.49 | 13.28 | 18.47 |
| 5 | 1.14 | 1.61 | 2.34 | 3.00 | 4.35 | 6.06 | 7.29 | 9.24 | 11.07 | 15.09 | 20.52 |
| 6 | 1.63 | 2.20 | 3.07 | 3.83 | 5.35 | 5.35 | 8.56 | 10.64 | 12.59 | 16.81 | 22.46 |
| 7 | 2.17 | 2.83 | 3.82 | 4.67 | 6.35 | 8.38 | 9.80 | 12.02 | 14.07 | 18.48 | 24.32 |
| 8 | 2.73 | 3.94 | 4.59 | 5.53 | 7.34 | 9.52 | 11.03 | 13.56 | 15.51 | 20.09 | 26.12 |
| 9 | 3.32 | 4.17 | 5.38 | 6.39 | 8.34 | 10.66 | 12.24 | 14.68 | 16.92 | 21.67 | 27.88 |
| 10 | 3.94 | 4.86 | 6.18 | 7.27 | 9.34 | 11.78 | 13.44 | 15.99 | 18.31 | 23.21 | 29.59 |
| Probability | 0.90 | 0.80 | 0.70 | 0.50 | 0.30 | 0.20 | 0.10 | 0.05 | 0.01 |

例如，你计算了两个变量的卡方值。值为 16，自由度为 7。查找自由度为 7 的卡方最小和较大值分别为 14.07 和 18.48。检查这两个值对应的概率分别为 0.05 和 0.01。这意味着两个变量独立的概率小于 5%，依赖的概率大于 1%。这是一个显著的百分比，意味着你可以说变量是依赖的概率大于 95%。

在 T-SQL 中计算卡方并不简单。获取实际（观测）频率不是问题；问题在于获取预期频率。例如，以下查询使用 `PIVOT` 获取来自销售分析的 `categoryname` 和 `employeeountry` 组合的实际频率：

```sql
SELECT categoryname, [USA], [UK]
FROM (SELECT categoryname, employeeountry, orderid FROM dbo.SalesAnalysis) AS S
PIVOT(COUNT(orderid) FOR employeeountry ([USA], [UK])) AS P
ORDER BY categoryname;
```

查询产生以下结果：

| categoryname | USA | UK |
|---|---|---|
| Beverages | 294 | 110 |
| Condiments | 158 | 58 |
| Confections | 256 | 78 |
| Dairy Products | 240 | 126 |
| Grains/Cereals | 157 | 39 |
| Meat/Poultry | 131 | 42 |
| Produce | 96 | 40 |
| Seafood | 255 | 75 |

你可以从边缘频率（marginal frequencies）或行列总和中计算预期频率。以下查询分步执行此操作：计算两个变量状态组合的观测频率，然后是第一个和第二个变量的观测频率，接着是观测总频率（案例总数），之后才计算两个变量状态组合的预期频率，最后将观测频率和预期频率连接：

```sql
WITH
ObservedCombination_CTE AS
(
    SELECT categoryname, employeeountry, COUNT(*) AS observed
    FROM dbo.SalesAnalysis
    GROUP BY categoryname, employeeountry
),
ObservedFirst_CTE AS
(
    SELECT categoryname, NULL AS employeeountry, COUNT(*) AS observed
    FROM dbo.SalesAnalysis
    GROUP BY categoryname
),
ObservedSecond_CTE AS
(
    SELECT NULL AS categoryname, employeeountry, COUNT(*) AS observed
    FROM dbo.SalesAnalysis
    GROUP BY employeeountry
),
ObservedTotal_CTE AS
(
    SELECT NULL AS categoryname, NULL AS employeeountry, COUNT(*) AS observed
    FROM dbo.SalesAnalysis
),
ExpectedCombination_CTE AS
(
    SELECT F.categoryname, S.employeeountry,
    CAST(ROUND(1.0 * F.observed * S.observed / T.observed, 0) AS INT) AS expected
    FROM ObservedFirst_CTE AS F
    CROSS JOIN ObservedSecond_CTE AS S
    CROSS JOIN ObservedTotal_CTE AS T
),
ObservedExpected_CTE AS
(
    SELECT O.categoryname, O.employeeountry, O.observed, E.expected
    FROM ObservedCombination_CTE AS O
    INNER JOIN ExpectedCombination_CTE AS E
    ON O.categoryname = E.categoryname
    AND O.employeeountry = E.employeeountry
)
SELECT * FROM ObservedExpected_CTE;
```

（注：上述 SQL 逻辑是根据破碎的 OCR 文本重构的，以提供完整的查询结构）。

```sql
GROUP BY categoryname, employeeecountry
),
ExpectedCombination_CTE AS
(
    SELECT rows, onsols, observedcombination,
    SUM(observedcombination) OVER (PARTITION BY rows) AS observedrows,
    SUM(observedcombination) OVER (PARTITION BY onsols) AS observedconcols,
    SUM(observedcombination) OVER () AS observedtotal,
    CAST(SUM(1.0 * observedcombination) OVER (PARTITION BY rows)
    * SUM(1.0 * observedcombination) OVER (PARTITION BY onsols)
    / SUM(1.0 * observedcombination) OVER () AS INT) AS expectedcombination
    FROM ObservedCombination_CTE
)
SELECT SUM(SQUARE(observedcombination - expectedcombination)) as chisquared,
COUNT(DISTINCT rows - 1) * COUNT(DISTINCT onsols) - 1) AS degreesoffreedom
FROM ExpectedCombination_CTE;
```

这是结果：

| chisquared | degreesfreedom |
|---|---|
| 22.229297748233 | 7 |

现在你可以查看表 8-6，即之前显示的卡方临界点表。对于 7 个自由度，你可以读取第一个和更高的值，这些值可以在最后两列中找到：18.48 和 24.32。读取较小值的概率——它是 0.01。你可以看到，在超过 99% 的概率，`categoryname` 和 `employeeecountry` 变量是相关的。显然，来自美国的员工在产品类别中销售更多商品，而来自英国的员工在其他产品类别中销售更多商品。

# 方差分析

最后，是检查连续变量与离散变量之间的线性依赖关系。你可以通过测量离散变量不同组之间连续变量均值之间的方差来实现。这里的零假设是所有方差都源于组内方差的结果。如果你拒绝它，这意味着组与组之间的均值存在某些显著的方差。这被称为残差或未解释的方差。你分析的是均值的方差，因此这种分析被称为方差分析或 ANOVA。

你计算组间方差 $MS_{A}$ 为组均值与总均值之差平方和除以每组的案例数，自由度等于组数减一。公式为：

```
$MS_{A} = \frac{SS_{A}}{DF_{A}}$, 其中 $SS_{A} = \sum_{i=1}^{n} n_i * (\mu_i - \mu)^2$，且 $DF_{A} = (a-1)$
```

离散变量具有离散状态，$\mu$ 是连续变量的总体均值，$\mu_i$ 是离散变量第 $i$ 组中连续变量的均值。

你计算组内方差 $MS_{SE}$ 为各组离组均值之差平方的总和，自由度等于每组均值的行数：

```
$MS_E = \frac{SS_{E}}{DF_{E}}, where SS_{E} = \sum_{i=1}^{a} n_{i} (v_{ij} - \mu_i)^2, and DF_{E} = \sum_{i=1}^{a} (n_i - 1)$
```

连续变量的个体值为 $v_{ip}$，$\mu_i$ 是离散变量第 $i$ 组中的连续变量，$n_i$ 是离散变量第 $i$ 组中的案例数。

一旦你得到了这两者，就可以计算组间方差与组内方差之间的所谓的 F 比例：

```
$F = \frac{MS_{A}}{MS_{E}}$
```

较大的 F 值意味着你可以拒绝零假设。对于不同自由度下的 F 分布尾部累积分布已经计算完毕。对于具有特定组间自由度和组内自由度的特定 F 值，你可以得到临界点，例如，在 F 分布曲线下在该点为止的 F 分布分布小于 5%。这意味着零假设正确的概率小于 5%（即均值与组之间存在相关性）。如果你在对数据进行划分或采样时得到较大的 F 值，则说明划分或采样不是随机的。

如前所述，你现在可以使用 F 值来计算 F 分布。然而，我想向你展示如何动态计算 F 概率（例如，使用 C# 应用）。遗憾的是，执行此任务的 CLR `FDistribution` 方法是在 SQL Server 内部实现的。但是，你可以创建一个控制台应用程序，然后使用 SQLCMD 模式从 SQL Server Management Studio 调用它。以下是计算 F 分布的控制台程序的 C# 代码：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Windows.Forms.DataVisualization.Charting;

class FDistribution
{
    static void Main(string[] args)
    {
        // 测试参数
        if (args.Length != 3)
        {
            Console.WriteLine("Please use three arguments: double FValue, int DF1, int DF2.");
            Console.ReadLine();
            return;
        }

        // 尝试将输入参数转换为数字。
        // FValue
        double FValue;
        bool test = double.TryParse(args[0], System.Globalization.NumberStyles.Float,
          System.Globalization.InvariantCulture.NumberFormat, out FValue);
        if (!test) { Console.WriteLine("First argument must be a double."); return; }

        // DF1
        int DF1;
        test = int.TryParse(args[1], out DF1);
        if (!test) { Console.WriteLine("Second argument must be an int."); return; }

        // DF2
        int DF2;
        test = int.TryParse(args[2], out DF2);
        if (!test) { Console.WriteLine("Third argument must be an int."); return; }

        // 计算 F 分布
        FDistribution fd = new FDistribution();
        double probability = fd.CalculateFProbability(FValue, DF1, DF2);
        Console.WriteLine($"F probability: {probability:P2}");
    }
}

public class FDistribution
{
    public double CalculateFProbability(double fValue, int df1, int df2)
    {
        // 此处应实现 F 分布概率计算逻辑
        return 0.0; // 占位符
    }
}
```

（注：由于原文提供的 C# 代码片段不完整且存在语法错误，翻译时对代码结构进行了合理的对齐和修正以符合逻辑，但保留了核心逻辑意图）

## 定积分



在检查我是否证明或拒绝了零假设时，我使用了统计表——例如，对于特定自由度的卡方分布。对于 F 分布，我使用了 CLR 应用程序而不是统计表。此外，我任意选择了一个阈值，用以定义两个变量之间的关系是显著的。该阈值设定为 95%（从另一个角度看是 5%），这意味着我可以以 95% 的概率拒绝零假设。问题是，这些表是从哪里来的，或者 CLR 应用程序是如何即时计算这些值的，以及我为什么选择 95% 的阈值。

这些表是根据分布函数计算的。例如，有一组针对卡方值的分布函数：每个自由度对应一个。你可以计算所有可能值在函数下方的面积（即总面积），以及特定取值范围内的面积，该范围的一侧可以是闭合的或开开的——这就是尾部面积。如果你知道分布函数，就可以通过定积分计算函数下方的面积。然后，你可以将特定面积与总面积进行比较，以找到特定区域内情况的百分比。

当然，T-SQL 中没有定积分函数。但是，有许多方法可以进行数值积分并计算定积分的数值。梯形法可以在 T-SQL 代码中以简单且高效的方式实现。你为曲线 `f(x)` 定义一个梯形，然后计算梯形的面积，如图 8-2 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_533_0.png)

图 8-2 定积分的梯形法。

梯形法的公式为：

```
$$\int_{a}^{b}f(x)dx \approx \frac{(b-a)}{2}(f(a) + f(b))$$
```

在公式中，`a` 和 `b` 定义了变量 `x` 的值，从而定义了定积分近似的面积。通过将曲线下的面积分成许多较小的梯形，然后相加这些梯形的面积，你可以得到定积分数值的精确近似值。通过在等距离 `h` 上指定 `n` 个点，从而产生 `n-1` 个梯形，公式变为：

```
$$\int_a^b f(x)dx \approx \frac{h}{2} (f(x_0) + 2 * f(x_1) + 2 * f(x_2) + \dots + 2 * f(x_{n-1}) + f(x_n))$$
```

从这里开始，在 T-SQL 中实现定积分变得简单。我将在一个示例中展示，该示例使用了我已经定义的标准正态分布函数。我正在创建一个临时表，包含两列——`z0` 表示 Z 值，`yz` 表示 `f(z0)`。我向表中填充了从 -4 到 4 之间的 Z 值，间距 `h` 等于 0.01。以下代码创建并填充了该表：

```sql
-- 标准正态分布
CREATE TABLE #StdNormDist (
z0 DECIMAL(3,2) NOT NULL,
yz DECIMAL(10,9) NOT NULL);
GO

-- 插入数据
DECLARE @z0 DECIMAL(3,2), @yz DECIMAL(10,9);
WHILE @z0 <= 4.00
BEGIN
    INSERT INTO #StdNormDist(z0, yz) VALUES (@z0, @yz);
    SET @z0 = @z0 + 0.01;
END
```

这里是表中的几行：

| z0 | yz |
| :--- | :--- |
| -4.00 | 0.000133830 |
| -3.99 | 0.000139285 |
| -3.98 | 0.000144948 |
| -3.97 | 0.000150825 |
| ... | ... |
| -0.03 | 0.398726797 |
| -0.02 | 0.398862500 |
| -0.01 | 0.398922334 |
| 0.00 | 0.398942280 |
| 0.01 | 0.398922334 |
| 0.02 | 0.398862500 |
| 0.03 | 0.398726797 |
| ... | ... |
| 3.97 | 0.000150825 |
| 3.98 | 0.000144948 |
| 3.99 | 0.000139285 |
| 4.00 | 0.000133830 |

以下代码创建并填充了一个简单的表，我将用它解释移动平均值：

```sql
CREATE TABLE dbo.MAvg
(id INT NOT NULL IDENTITY(1,1),
val FLOAT NULL);
GO
INSERT INTO dbo.MAvg(val) VALUES
(1), (2), (3), (4), (1), (2), (3), (4), (1), (2);
GO
```

这是来自该演示表的数据：

| id | val |
|---|---|
| 1 | 1 |
| 2 | 2 |
| 3 | 3 |
| 4 | 4 |
| 5 | 1 |
| 6 | 2 |
| 7 | 3 |
| 8 | 4 |
| 9 | 1 |
| 10 | 2 |

我还使用了这些数据来绘制图 8-3 中的图表。

## 简单移动平均

在金融应用中，简单移动平均（SMA）是前 `n` 个数据的未加权平均值。这就是你在第 4 章中学到的移动平均值。计算最后三个值的简单移动平均的公式为：

> $SMA_i = \frac{\sum_{i-2}^{i} V_i}{3}$

以下查询计算了最后三个值的 SMA：

```sql
SELECT id, val,
ROUND(
AVG(val)
OVER (ORDER BY id)
ROWS BETWEEN 2 PRECEDING
AND CURRENT ROW) AS SMA
FROM dbo.MAvg
ORDER BY id;
```

该查询产生以下结果：

| id | val | SMA |
|---|---|---|
| 1 | 1 | 1 |
| 2 | 2 | 1.5 |
| 3 | 3 | 2 |
| 4 | 4 | 3 |
| 5 | 1 | 2.67 |
| 6 | 2 | 2.33 |
| 7 | 3 | 2 |
| 8 | 4 | 3 |
| 9 | 1 | 2.67 |
| 10 | 2 | 2.33 |

## 加权移动平均

加权移动平均（WMA）是任何带有乘因数的平均值，对样本窗口中不同位置的数据赋予不同的权重。所有权重的和必须等于 1。通过 WMA，你可以给最近的值更大的权重，给较旧的值较小的权重。以下是最后两个值的加权移动平均的公式：

```sql
$WMA_i = \frac{\sum_{t=i-1}^{i}(v_t * w_t)}{\sum_{t=i-1}^{i} w_t}$, where
```

以下查询计算最后两个值的 WMA，给当前值赋予权重 0.7，给上一个值赋予权重 0.3：

```sql
DECLARE @A FLOAT;
SET @A = 0.7;
SELECT id, val,
LAG(val, 1) OVER (ORDER BY id) AS prevval,
@A * val + (1 - @A) * 
LAG(val, 1) OVER (ORDER BY id) AS WMA
FROM dbo.MAvg
```

查询结果为：

| id | val | prevval | WMA |
|---|---|---|---|
| 1 | 1 | 1 | 1 |
| 2 | 2 | 1 | 1.7 |
| 3 | 3 | 2 | 2.7 |
| 4 | 4 | 3 | 3.7 |
| 5 | 1 | 4 | 1.9 |
| 6 | 2 | 1 | 1.7 |
| 7 | 3 | 2 | 2.7 |
| 8 | 4 | 3 | 3.7 |
| 9 | 1 | 4 | 1.9 |
| 10 | 2 | 1 | 1.7 |

## 指数移动平均

指数移动平均（EMA）是一种包含无限列表以前值的移动平均值，意味着包含了所有以前的值。它也是加权的，因此你通常会给最近的值更高的权重。EMA 经常用于经济学中的预测。EMA 的公式为：

$EMA_i = \alpha * v_i + (1 - \alpha) * EMA_{i-1}$, where $EMA_1 = v_1$

计算 EMA 的问题在于，当前 EMA 的计算使用了上一个 EMA。使用窗口函数时，SQL Server 不暴露运行计算结果。除非使用游标，否则你无法在查询中引用它。以下查询了一个使用游标进行 EMA 计算的示例，其中参数 $\alpha$ 等于 0.7。

```sql
DECLARE @CurrentEMA AS FLOAT, @PreviousEMA AS FLOAT,
@Id AS INT, @Val AS FLOAT,
@A AS FLOAT;
DECLARE @Results AS TABLE(id INT, val FLOAT, EMA FLOAT);
SET @A = 0.7;

DECLARE EMACursor CURSOR FOR
SELECT id, val
FROM dbo.MAvg
ORDER BY id;

OPEN EMACursor;

FETCH NEXT FROM EMACursor
INTO @Id, @Val;
SET @CurrentEMA = @Val;
SET @PreviousEMA = @CurrentEMA;

WHILE @@FETCH_STATUS = 0
BEGIN
SET @CurrentEMA = ROUND(@A * @Val + (1-@A) * @PreviousEMA, 2);
INSERT INTO @Results(id, val, EMA)
VALUES(@Id, @Val, @CurrentEMA);
SET @PreviousEMA = @CurrentEMA;
FETCH NEXT FROM EMACursor
INTO @Id, @Val;
END;

CLOSE EMACursor;
DEALLOCATE EMACursor;

SELECT id, val, EMA
FROM @Results;
```

查询产生以下结果：

| id | val | EMA |
|---|---|---|
| 1 | 1 | 1 |
| 2 | 2 | 1.7 |
| 3 | 3 | 2.61 |
| 4 | 4 | 3.58 |
| 5 | 1 | 2.77 |
| 6 | 2 | 1.93 |
| 7 | 3 | 2.68 |
| 8 | 4 | 3. |
| 9 | 1 | 1.78 |

当然，你知道使用游标不会产生最高效的 SQL 代码。可以避免游标吗？一种方法是使用递归表达式，如下：

```sql
DECLARE @A FLOAT;
SET @A = 0.7;
WITH RnCTE AS (
    SELECT id, val,
    ROW_NUMBER() OVER (ORDER BY id) AS rn
    FROM dbo.Mavg
),
EMACTE AS (
    SELECT id, rn, val AS EMA
    FROM RnCTE
    WHERE id = 1
    UNION ALL
    SELECT C.id, C.rn, C.val,
    ROUND(@A * C.val + (1 - @A) * P.EMA, 2) AS EMA
    FROM EMACTE AS P
    INNER JOIN RnCTE AS C
    ON C.rn = P.rn + 1
)
SELECT id, val, EMA
FROM EMACTE;
```

当然，这个查询仍然不是高效的，递归 CTE 意味着循环。用 `WHILE` 循环模拟递归 CTE 对优化计算没有太大帮助。我尝试将 EMA 公式转换为只使用值的等效公式，而不是使用上一个 EMA。我通过替换上一个 EMA 来扩展 EMA 公式。以下是扩展五个值的 EMA 公式的过程：

$EMA_5 = \alpha * v_5 + (1 - \alpha) * EMA_4$

$EMA_5 = \alpha * v_5 + (1 - \alpha) * (\alpha * v_4 + (1 - \alpha) * EMA_3)$

$EMA_5 = \alpha * v_5 + (1 - \alpha) * (\alpha * v_4 + (1 - \alpha) * (\alpha * v_3 + (1 - \alpha) * EMA_2))$

$EMA_5 = \alpha * v_5 + (1 - \alpha) * (\alpha * v_4 + (1 - \alpha) * (\alpha * v_3 + (1 - \alpha) * (\alpha * v_2 + (1 - \alpha) * EMA_1))$

由于 EMA 等于值，公式只使用了值。在重新排列方程后，我找到了一个只使用值的计算 EMA 公式：

$EMA_i = \sum_{j=2}^{i} \alpha * (1 - \alpha)^{i-j} * v_j + (1 - \alpha)^{i-1} * v_1$

我现在正在寻找计算 EMA 的更高效的集合解决方案。我出了以下查询：

```sql
DECLARE @A FLOAT;
SET @A = 0.7;
WITH RnCTE AS (
  SELECT id, val,
  ROW_NUMBER() OVER (ORDER BY id) AS rn,
  FIRST_VALUE(val) OVER (ORDER BY id UNBOUNDED PRECEDING) AS val
  FROM dbo.Mavg
),
MaCTE AS (
  SELECT Rn1.id AS id, Rn1.rn AS rn1, Rn2.rn AS rn2,
  Rn1.val, Rn2.val AS YII,
  MAX(Rn2.rn) OVER (PARTITION BY Rn1.rn) AS TRC
  FROM RnCTE AS Rn1
  INNER JOIN RnCTE AS Rn2
  ON Rn1.rn >= Rn2.rn
)
SELECT id, MAX(Y1) AS val,
ROUND(
  SUM(@A * POWER((1 - @A), (rn1 - rn2)) * YII)
  + MAX(POWER((1 - @A), (TRC - 1))), 2) AS EMA
FROM MaCTE
WHERE rn2 > 1
GROUP BY id
UNION
SELECT 1, 1, 1
ORDER BY Id;
```

遗憾的是，尽管这个查询非常复杂，但它仍然不高效。它在第二个表表达式使用了非等连接，这是二次复杂度。因此，对于较大的数据集，此查询的效率很快就会低于游标。在尝试多次后，我几乎要放弃了，并开始认为计算 EMA 的唯一方法是使用游标。我针对这个问题写了一篇博客。几天后，我的博客上有一条评论。Quentin Duyn，SQL Server 社区的杰出成员，使用修改后的公式发现了一种高效的集合查询 EMA 的解决方案。以下是他的查询：

```sql
DECLARE @A AS FLOAT = 0.7, @B AS FLOAT;
SET @B = 1 - @A;
WITH cte_cnt AS (
  SELECT id, val,
  ROW_NUMBER() OVER (ORDER BY id) - 1 as exponent
  FROM dbo.Mavg
)
SELECT id, val,
ROUND(SUM(CASE WHEN exponent=0 THEN 1
ELSE @A
END * val * POWER(@B, -exponent))
OVER (ORDER BY id) * POWER(@B, exponent), 2) AS EMA
FROM cte_cnt;
```

因此，你永远不要放弃，并且要记住知道的人越多越多。

## 熵

信息论是应用数学、电子工程和计算机科学的一个分支，涉及信息的量化，由克劳德·香农开发。

在数据集中，你有有限的可能系统状态。如果你有一个二进制变量，就有两个可能的状态。

### 熵简介

熵衡量的是“意外性”。在数据集中，惊讶是通过概率（即相对频率）来量化的。如果一个系统的概率越低，它发生时你就越惊讶。因此你获得了更多信息。想象你从发行的10张彩票中买了5张。如果你中了，有多惊讶？如果你只买了一张就中了，有多惊讶？

变量 `x` 的特定状态 `i` 的信息定义为概率乘以以二为对数：

$I(x) = -P(x) * LOG_2(P(x))$

添加一个负号是因为概率取值在 0 到 1 之间的区间，而对数函数在该区间内返回负值。

变量的总信息量是其所有状态的信息之和。这种总信息量被称为*熵*。因此，变量 `x` 的熵公式为：

```
H(x) = -\sum_{i=1}^{n} P(x_i) * LOG_2(P(x_i))
```

特定变量的最大熵是多少？假设你有一个变量，在一种情况下只有两个状态，这两个状态之间的数值分布非常均匀，一个状态的概率为 0.9，另一个状态的概率为 0.1。在另一种情况下，以下查询计算了这两个示例的熵：

```sql
SELECT (-1) * (0.1*LOG(0.1,2) + 0.9*LOG(0.9,2)) AS unequalistribution,
(-1) * (0.5*LOG(0.5,2) + 0.5*LOG(0.5,2)) AS equalistribution;
```

结果是

```
unequalistribution      equalistribution
0.46899559358291          1
```

你可以看到，分布越均匀意味着熵越高。在只代表一个状态的均匀分布中（即所有值都等于一个常数），熵为 0。这种变量对于分析是无用的。当值等等分布时，离散变量的熵最大。

现在让我测试不同状态数量变量的可能最大熵。以下查询使用数值在状态上的均匀分布，计算了具有两个、三个和四个状态的变量的最大可能熵：

```sql
SELECT (-1)*(2)*(1.0/2)*LOG(1.0/2,2) AS TwoStatesMax,
(-1)*(3)*(1.0/3)*LOG(1.0/3,2) AS ThreeStatesMax,
(-1)*(4)*(1.0/4)*LOG(1.0/4,2) AS FourStatesMax;
```

查询结果是



TwoStatesMax | ThreeStatesMax | FourStatesMax
--- | --- | ---
1 | 1.58496235845298 | 2

从数学上，你可以学习到：

```
LOG(x/y) = LOG(x) - LOG(y)
```

因此，前面的查询计算不同状态数量的最大可能熵可以简化为：

```sql
SELECT LOG(2,2) AS TwoStatesMax,
LOG(3,2) AS ThreeStatesMax,
LOG(4,2) AS FourStatesMax;
```

从结果中可以看出，随着状态的增加，最大可能熵也会增加。对于连续变量，你可以通过离散化或分箱（binning）来计算熵。箱越少，最大可能熵越低。离散化为具有相等数量的箱，可以指定的箱数量保留尽可能多的熵。这一事实也可以解释为什么 SQL Server 在列的统计信息时使用这种等区域分布。

## 计算熵

在 T-SQL 中遵循熵公式进行计算非常简单。除了计算变量的熵之外，你还可以计算变量的最大可能熵，以及实际熵占最大可能熵的百分比。以下查询对 `customercountry` 变量执行此计算：

```sql
WITH ProbabilityCTE AS (
SELECT customercountry,
COUNT(customercountry) AS StateFreq
FROM dbo.SalesAnalysis
WHERE customercountry IS NOT NULL
GROUP BY customercountry
),
StateEntropyCTE AS (
SELECT customercountry,
1.0*SUM(StateFreq) OVER ( ) AS StateProbability
FROM ProbabilityCTE
)
SELECT (-1)*SUM(StateProbability * LOG(StateProbability,2)) AS TotalEntropy,
LOG(COUNT(*),2) AS MaxPossibleEntropy,
100 * ((-1)*SUM(StateProbability * LOG(StateProbability,2))) /
(LOG(COUNT(*),2)) AS PctOfMaxPossibleEntropy
FROM StateEntropyCTE;
```

结果是

| TotalEntropy | MaxPossibleEntropy | PctOfMaxPossibleEntropy |
| --- | --- | --- |
| 3.9197758986801 | 4.3923174227876 | 89.2416968464042 |

对 `productcategory` 变量重复相同的查询：

```sql
WITH ProbabilityCTE AS
(
SELECT categoryname,
COUNT(categoryname) AS StateFreq
FROM dbo.SalesAnalysis
WHERE categoryname IS NOT NULL
GROUP BY categoryname
),
StateEntropyCTE AS
(
SELECT categoryname,
1.0*StateFreq / SUM(StateFreq) OVER () AS StateProbability
FROM ProbabilityCTE
)
SELECT (-1)*SUM(StateProbability * LOG(StateProbability,2)) AS TotalEntropy,
LOG(COUNT(*),2) AS MaxPossibleEntropy,
100 * ((-1)*SUM(StateProbability * LOG(StateProbability,2))) /
LOG(COUNT(*),2) AS PctOfMaxPossibleEntropy
FROM StateEntropyCTE;
```

`productcategory` 变量的结果是

| TotalEntropy | MaxPossibleEntropy | PctOfMaxPossibleEntropy |
|---|---|---|
| 2.90951317302341 | 3 | 96.98377234137 |

你可以看到 `customercountry` 变量具有接近最大可能熵的值，而 `productcategory` 变量分布更均匀，且熵接近最大可能熵。

由于这是本章的最后一个查询，我必须清理数据库：

```sql
DROP TABLE #TestMedian;
DROP AGGREGATE Skew;
DROP AGGREGATE Kurt;
DROP ASSEMBLY DescriptiveStatistics;
EXEC sp_configure 'clr enabled', 0;
RECONFIGURE;
DROP TABLE StdnormDist;
DROP TABLE Mavg;
```

## 总结

在本章中，你学习了如何在 T-SQL 中遵循熵公式进行计算。此外，你还学习了如何正确使用查询结果并理解背后的统计学。最后，我希望你学会了优化查询并不总是意味着最好的执行计划。分析型查询通常扫描大量数据，通过传统的非聚集索引进行优化并没有带来改进。然而，你在本章中学到的优化技术是算法优化。

对于本章的查询，我准备了样本分析。在引言部分，我还讨论了离散变量和连续变量之间的区别。然后我展示了如何高效地计算离散变量的频率分布并快速获取该分布的概览。

表 8-7 总结了本章介绍的统计指标及其简短定义。

## 表 8-7 本章介绍的统计测量量总结

| 测量量 | 简要定义 |
|---|--|
| 频率 (Frequencies) | 事件的频率（或绝对频次）是该事件在实验或研究中发生的次数。 |
| 数值 (Mode) | 分布的中心——分布中最常见的值。 |
| 中位数 (Median) | 分布的中心——将分布分成两半的值。 |
| 平均值 (Mean) | 分布的中心——平均值。 |
| 范围 (Range) | 分布的离散程度——最大值与最小值之间的距离。 |
| 四分位距 (Inter-quartile range) | 分布的离散程度——上四位数（第三）与下四位数（第一））之间的距离。 |
| 平均绝对偏差 (Mean absolute deviation) | 分布的离散程度——每个值与平均值之间距离的绝对值和。 |
| 均方差 (Mean squared deviation) | 分布的离散程度——每个值与平均值之间距离的平方和，总体测量量。 |
| 方差 (Variance) | 分布的离散程度——每个值与平均值之间距离的平方和，总体样本量。 |
| 标准差 (Standard deviation) | 分布的离散程度——方差的平方根。 |
| 变异系数 (Coefficient of the variation) | 分布的离散程度——相对标准差。 |
| 自由度 (Degrees of freedom) | 统计量最终计算中可以自由变化的数值个数。 |
| 偏度 (Skewness) | 衡量实值随机变量概率分布关于其平均值的不对称性。 |
| 峰度 (Kurtosis) | 衡量实值随机变量概率分布的尖锐程度。 |
| 协方差 (Covariance) | 线性依赖（连续变量）——衡量两个随机变量如何共同变化的量。 |
| 相关性 (Correlation) | 线性依赖（连续变量）——线性关系的相对强度。 |
| 决定系数 (Coefficient of determination) | 线性依赖（连续变量）——相关性的平方。 |
| 线性回归 (Linear regression) | 标量因变量与一个或多个解释变量之间关系的模型。 |
| 联分类表 (Contingency table) | 线性依赖（离散变量）——以矩阵格式显示变量的（多变量）频率分布的表。 |
| 卡方检验 (Chi-squared test) | 线性依赖（离散变量）——两个离散变量之间依赖性的检验。 |
| 方差分析 (Analysis of variance) | 线性依赖（离散和连续变量）——检验几组均值是否相等。 |
| F 检验 (F-test) | 线性依赖（离散和连续变量）——连续变量与离散变量之间依赖性的检验。 |
| 定积分 (Definite integral) | xy 平面上函数下方区域的符号面积，该区域由函数图像、x 轴以及 x = 下边界和 x = 上界的垂直线界定。 |
| 移动平均 (Moving average) | 通过创建完整数据集不同子集的系列平均值来分析数据点的计算方法。 |
| 熵 (Entropy) | 衡量信息内容不可预测性的指标。 |

# 第 9 章

## 可编程对象

本章关注 T-SQL 中的程序化结构。它涵盖了动态 SQL、用户定义函数、存储过程、触发器、SQLCLR 编程、事务与并发以及异常处理。由于本书的重点是查询，因此大多数相关的程序化结构将倾向于以支持查询为中心，并强调代码的性能。

## 动态 SQL

动态 SQL 本质上是构造并执行 T-SQL 代码的 T-SQL 代码。你通常将代码批构建为字符串存储在变量中，然后使用两个工具之一执行存储在变量中的代码：`EXEC` 命令（`EXECUTE` 的缩写）或 `sp_executesql` 存储过程。后者是更灵活的工具，因此建议使用。

你执行的代码在一个批处理中运行，被认为与调用批是分开的。这一点很重要，因为批处理是 Microsoft SQL Server 中许多内容的单元。它是解析、构建和优化的单元。批处理是变量和参数的作用域。你不能在一个批处理中访问另一个批中声明的变量。这意味着如果你在调用批中有一个变量，动态批中的代码是不可见的，反之亦然。所以，如果你需要在批处理之间传递变量值，并且想避免为此目的读写表，你需要一个输入和输出参数形式的接口。在 `EXEC` 和 `sp_executesql` 工具之间，后者支持这种接口；因此，它是推荐使用的工具。我将演示使用这两个工具。

## 使用 EXEC 命令

如所述，`EXEC` 命令不支持接口。你将持有要运行的代码批的字符字符串作为输入传递，命令将执行其中的代码。如果你在动态批中需要引用调用批中变量或参数的值，由于缺乏对接口的支持，会引入挑战。

例如，假设调用批中有一个名为 `@s` 的变量，存储员工的姓氏。你需要构造一个动态批，该批其他包括查询 `TLSQV3` 数据库中的 `HR.Employees` 表并返回该姓氏的员工。在这种情况下，有些人会将变量的内容（实际姓氏）作为字面量接到代码中，并使用 `EXEC` 执行构造的代码，如下：

```sql
SET NOCOUNT ON;
USE TLSQV3;
```

```sql
DECLARE @s AS NVARCHAR(200);
SET @s = 'N''Davis''; -- 源自用户定义

DECLARE @sql AS NVARCHAR(200);
SET @sql = N'SELECT * FROM HR.Employees WHERE LastName = ' + @s; 
EXEC(@sql);
```

黑客获得了以下输出：

```sql
SELECT empid, firstname, lastname, hiredate
FROM HR.Employees WHERE lastname = 'N''abc' UNION ALL
SELECT NULL, name, NULL, NULL FROM sys.columns WHERE object_id = 48557678; --'
```

| empid | firstname | lastname | hiredate |
| --- | --- | --- | --- |
| NULL | custid | NULL | NULL |
| NULL | companyname | NULL | NULL |
| NULL | contactname | NULL | NULL |
| NULL | contacttitle | NULL | NULL |
| NULL | address | NULL | NULL |
| NULL | city | NULL | NULL |
| NULL | region | NULL | NULL |
| NULL | postcode | NULL | NULL |
| NULL | country | NULL | NULL |
| NULL | phone | NULL | NULL |
| NULL | fax | NULL | NULL |

然后，黑客的下一步是使用以下语句收集客户的电话号码：

```sql
SET @s = 'N''abc' UNION SELECT NULL, companyname, phone, NULL FROM Sales.Customers; --'
```

他获得了以下输出：

```sql
SELECT empid, firstname, lastname, hiredate
FROM HR.Employees WHERE lastname = 'N''abc' UNION ALL
SELECT NULL, companyname, phone, NULL FROM Sales.Customers; --'
```

| empid | firstname | lastname | hiredate |
| --- | --- | --- | --- |
| NULL | Customer NRZZB | 030-3456789 | NULL |
| NULL | Customer MLTON | (S) 789-0123 | NULL |
| NULL | Customer KBUDE | (S) 123-4567 | NULL |
| NULL | Customer HFBZG | (171) 456-7890 | NULL |
| NULL | Customer HGVLZ | 0921-68 01 | NULL |

这一切之所以可能，是因为你直接将用户输入字符串拼接到了注入语句中。如果你认为可以通过通过寻找注入中使用的常用元素来检查输入，那么你需要涵盖所有可能的注入方法。黑客们不断在自我创新。正如我的朋友和同事理查德·维纳（Richard Weiner）曾经说过的：“他们并不一定比你聪明，但他们比你有更多时间。”避免注入的唯一真实方法是不将用户输入拼接到代码中，而是将它们作为参数传递。为了做到这一点，你需要一个支持接口的工具，遗憾的是 `EXEC` 命令。幸运的是，`sp_executesql` 过程支持这种接口，我稍后会演示。

`EXEC` 命令有一个有趣的功能，可以用它在括号内拼接多个变量，如下所示：

```sql
EXEC(@v1 + @v2 + @v22);
```

即使输入是大小有限的字符字符串（例如 `VARCHAR(8000)`），你也被允许组合字符串超过 8,000 个字符。在支持 `VARCHAR(MAX)` 和 `NVARCHAR(MAX)` 之前的旧版 SQL Server 中，这曾是一项重要功能。使用这些类型，你可以传递高达 2 GB 大小的输入批。`EXEC` 支持普通字符字符串和 Unicode 字符串作为输入，而 `sp_executesql` 仅支持后者。

## 使用 EXEC AT

除了支持在本地执行动态批的 `EXEC` 命令外，SQL Server 还支持名为 `EXEC AT` 的命令，用于在链接服务器上执行动态批。有趣的地方在于，如果你用于连接链接服务器的提供程序支持参数，你就可以通过参数将输入传递给动态批。

例如，假设你有访问另一个名为 `YourServer` 的 SQL Server 实例的权限，以下是创建链接服务器的代码：

```sql
EXEC sp_addlinkedserver
@server = N'YourServer',
@srvproduct = N'SQL Server';
```

假设你已经在该实例中安装了示例数据库 `TSQLV3`，运行以下代码来测试 `EXEC` 命令：

```sql
DECLARE @sql AS NVARCHAR(1000), @pid AS INT;

SET @sql = 
'SELECT productid, productname, unitprice
FROM TSQLV3.Production.Products
WHERE productid = ?';

SET @pid = 3;

EXEC(@sql, @pid) AT [YourServer];
```

该代码构建了一个批处理，该批处理查询 `Production.Products` 表，过滤作为参数提供的产品 ID，然后在链接服务器上执行该批，并将值 3 作为输入传递。该代码生成了以下输出：

| productid | productname | unitprice |
|---|---|---|
| 3 | Product IMEHJ | 10.00 |

## 使用 sp_executesql 过程

与 `EXEC` 命令不同，`sp_executesql` 过程支持定义输入和输出参数，类似于存储过程。该工具接受三个部分作为输入：第一部分称为 `@stmt`，是你想要运行的代码输入批（带有对输入和输出参数的引用）。第二部分称为 `@params`，是你提供参数声明的地方。第三部分是你为动态批的输入参数赋值，并将输出参数的值收集到变量中的地方。

回到最初的任务，即根据用户输入的姓氏查询 `Employees` 表，以下是你可以如何使用 `sp_executesql` 通过参数化查询来实现：

```sql
DECLARE @s AS VARCHAR(200);
SET @s = 'N\'Davis';
```



# 动态透视存储过程

```sql
CREATE PROC dbo.sp_pivot
    @query AS NVARCHAR(MAX),
    @on_rows AS NVARCHAR(MAX),
    @on_cols AS NVARCHAR(MAX),
    @agg_func AS NVARCHAR(257) = 'NMAX',
    @agg_col AS NVARCHAR(MAX)
AS
BEGIN
    -- 输入验证
    IF @query IS NULL OR @on_rows IS NULL OR @on_cols IS NULL
        OR @agg_func IS NULL OR @agg_col IS NULL
        THROW 50001, '无效输入参数.', 1;

    -- 此处进行额外的输入验证（SQL 注入尝试等）

    DECLARE
        @sql NVARCHAR(MAX),
        @cols NVARCHAR(MAX),
        @newline NVARCHAR(2) = CHAR(13) + CHAR(10);

    -- 如果输入是有效的表或视图
    -- 则针对其构建 SELECT 语句
    IF COALESCE(OBJECT_ID(@query, N'V'), OBJECT_ID(@query, N'U')) IS NOT NULL
        SET @query = N'SELECT * FROM ' + @query;

    -- 将查询变为派生表
    SET @query = N'(' + @query + N') AS Query';

    -- 处理 @agg_col 中的输入
    IF @agg_col = N'*' SET @agg_col = N'1';

    -- 构建列列表
    SET @sql = N'SELECT @result = ' + @newline +
        N'STUFF(' + @newline +
        N'(SELECT N'', '' + ' + @newline +
        N'CAST(' + @on_cols + N' AS NVARCHAR(MAX))' + @newline +
        N' FROM (' + @query + N') AS DistinctCols' + @newline +
        N' ORDER BY ' + @on_cols + @newline +
        N' FOR XML PATH(''''),' + @newline +
        N'1, 1, N'''');';

    EXEC sp_executesql
        @stmt = @sql,
        @params = N'@result AS NVARCHAR(MAX) OUTPUT',
        @result = @cols OUTPUT;

    -- 创建 PIVOT 查询
    SET @sql = N'SELECT ' + @on_rows + @newline +
        N'FROM (' + @newline +
        N'SELECT ' + @on_rows + N', ' + @on_cols + N' AS pivot_col' + @newline +
        N', ' + @agg_col + N' AS agg_col' + @newline +
        N'FROM ' + @query + N') AS PivotInput' + @newline +
        N'PIVOT(' + @agg_func + N'(agg_col)' + @newline +
        N'FOR pivot_col IN (' + @cols + N')) AS PivotOutput;';

    EXEC sp_executesql @sql;
END;
```

## 存储过程参数说明

该存储过程接受以下输入参数：

- `@query`：一个表、名称或任何你想要对其结果进行透视（pivot）处理的查询——例如，`N'Sales.OrderValues'`。
- `@on_rows`：透视分组元素——例如，`N'custid'`。
- `@on_cols`：透视展开元素——例如，`N'YEAR(orderdate)'`。
- `@agg_func`：透视聚合函数——例如，`N'SUM'`。
- `@agg_col`：用于透视聚合函数的输入表达式——例如，`N'val'`。

> **警告**：从定义上来说，此存储过程支持 SQL 注入。输入参数被直接注入到代码中以形成透视查询。出于此原因，你需要非常谨慎地决定何时以及为何使用它，将此过程的使用限制在构建透视查询的开发者可能是一个好主意。应用程序在收集用户输入后调用此存储过程将使你的环境面临风险。

## 执行上下文

该存储过程创建在 `master` 数据库中并带有 `sp_` 前缀，可以在任何数据库的上下文中执行。这可以通过在连接到目标数据库时不使用数据库前缀来调用它，或者通过使用三部分名称（使用所需的数据库作为数据库前缀）来调用它，例如 `mydb.dbo.sp_pivot`。

## 处理逻辑

存储过程执行了一些基本的输入验证以确保所有输入都已提供。过程检查输入 `@query` 是否包含目标数据库中存在的表或视图名称。如果是，过程会将 `@query` 的内容替换为针对该对象的查询；如果不是，过程假设 `@query` 已经包含一个查询。然后，过程会将 `@query` 的内容替换为基于输入查询的名为 `Query` 的派生表的定义。此派生表将被视为查找两个唯一值和最终透视查询的输入。

过程的下一步是检查输入 `@agg_col` 是否为 `*`。这是为了让人们使用 `*` 作为聚合函数 `COUNT` 的输入来计算行数。`PIVOT` 操作符不支持将 `*` 作为 `COUNT` 的输入，因此代码将 `*` 替换为常量 `1`，稍后将根据 `@agg_col` 中存储的内容定义名为 `agg_col` 的列。此列最终将用作存储 `@agg_func` 中的聚合函数的输入。

接下来的两个步骤代表了存储过程的核心。这些步骤构建了两个不同的批处理。第一个处理创建一个用逗号分隔的唯一展开值列表，这些值最终将出现在 `PIVOT` 操作符的 `IN` 子句中。该批处理使用 `sp_executesql` 执行，并使用输出参数 `@result` 将结果存储在本地变量 `@cols` 中。

第二个动态批处理包含最终的透视查询。代码从存储在 `@query` 中的派生表构建一个派生表 `PivotInput`。所有的透视元素（分组、展开和聚合）都被注入到内部查询的 `SELECT` 列表中。然后，根据应用于 `agg_col` 的聚合函数以及带有存储在 `@cols` 中的逗号分隔的展开值列表 `IN` 子句，构建出 `PIVOT` 操作符的规范。最后使用 `sp_executesql` 执行最终的透视查询。

## 示例 1：按员工和年份透视月份订单计数

作为使用该过程示例，下面的代码计算了按员工和年份按月份进行透视的订单计数：

```sql
EXEC TSQLV.dbo.sp_pivot
    @query = N'Sales.Orders',
    @on_rows = N'empid, YEAR(orderdate) AS orderyear',
    @on_cols = N'MONTH(orderdate)',
    @agg_func = N'COUNT',
    @agg_col = N'*';
```

此代码生成了以下内容：

| empid | orderyear | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 2013 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 2 | 2014 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 3 | 2015 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 4 | 2013 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 5 | 2014 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 6 | 2015 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 7 | 2013 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 8 | 2014 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 9 | 2015 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

## 示例 2：按员工按年份透视销售总额

作为该过程的另一个示例，下面的代码计算了按员工按年份透视的（数量*价格）总和：

```sql
EXEC TSQLV.dbo.sp_pivot
    @query = N'SELECT O.orderid, O.empid, YEAR(O.orderdate) AS orderyear, OD.quantity * OD.unitprice AS val
FROM Sales.Orders AS O
JOIN Sales.OrderDetails AS OD ON O.orderid = OD.orderid',
    @on_rows = N'empid',
    @on_cols = N'YEAR(orderdate)',
    @agg_func = N'SUM',
    @agg_col = N'val';
```

此代码生成以下输出：

| empid | 2013 | 2014 | 2015 |
|---|---|---|---|
| 1 | 11365.70 | 29577.55 | 42020.75 |
| 2 | 19231.80 | 11178.61 | 82030.89 |
| 3 | 17731.10 | 45992.00 | 14475.00 |
| 4 | 38789.00 | 97533.58 | 57594.95 |
| 5 | 21965.20 | 32595.05 | 21007.50 |
| 6 | 22834.70 | 74958.60 | 79955.96 |
| 7 | 23161.40 | 59776.52 | 50363.11 |

# 动态搜索条件

动态搜索条件（也称为动态过滤）是应用程序中的常见需求。其理念是应用程序提供通过各种属性过滤数据的用户界面，用户根据每次请求选择对哪些属性进行过滤。为了演示处理动态搜索条件的技术，我将在示例中使用 `tempdb` 中的 `Orders` 表副本。运行以下代码在 `tempdb` 中创建类似 `TSQLV3.Sales.Orders` 表，并带有一些索引以支持过滤：

```sql
SET NOCOUNT ON;
USE tempdb;
IF OBJECT_ID(N'dbo.GetOrders', N'P') IS NOT NULL DROP PROC dbo.GetOrders;
IF OBJECT_ID(N'dbo.Orders', N'U') IS NOT NULL DROP TABLE dbo.Orders;
```

```sql
SELECT orderid, custid, empid, orderdate,
    CAST('A' AS CHAR(200)) AS filler
INTO dbo.Orders
FROM TSQLV3.Sales.Orders;
```

```sql
CREATE CLUSTERED INDEX idx_orderdate ON dbo.Orders(orderdate);
CREATE UNIQUE INDEX idx_orderid ON dbo.Orders(orderid);
CREATE INDEX idx_custid_empid ON dbo.Orders(custid, empid) INCLUDE(orderid, orderdate, filler);
```

你的任务是创建一个名为 `dbo.GetOrders` 的存储过程，它接受四个输入，分别为 `@orderid`、`@custid`、`@empid` 和 `@orderdate`。该过程应该查询 `Orders` 表并根据具有 `NULL` 值的参数对行进行过滤。

以下存储过程的实现代表处理此任务最常用的技术之一：

```sql
IF OBJECT_ID(N'dbo.GetOrders', N'P') IS NOT NULL DROP PROC dbo.GetOrders;
GO
CREATE PROC dbo.GetOrders
    @orderid INT = NULL,
    @custid INT = NULL,
    @empid INT = NULL,
    @orderdate DATE = NULL
AS
    SELECT orderid, custid, empid, orderdate, filler
    FROM dbo.Orders
    WHERE (orderid = @orderid OR @orderid IS NULL)
      AND (custid = @custid OR @custid IS NULL)
      AND (empid = @empid OR @empid IS NULL)
      AND (orderdate = @orderdate OR @orderdate IS NULL);
GO
```

该过程使用静态查询，对于每个参数，它使用以下谓词的析取（OR 谓词）：`列 = @parameter OR @parameter IS NULL`。如果没有为参数提供值，则右侧谓词为真。在谓词析取中，当一个操作数为真时，整个表达式为真；因此，对列不会发生过滤。如果指定了值，右侧谓词为假；因此，左侧谓词是决定过滤哪些行的唯一有效谓词。

这种解决方案易于维护；然而，由于缺少恒真元素，它往往会导致查询性能并非最优。其原因是，当你第一次执行该过程时，优化器会处理代码的参数化形式，包含查询中的所有谓词。这意味着两个谓词对于当前查询的执行都是相关的，而不相关的谓词也包含在计划中。这种方法用于促进重用行为，以节省与每次执行创建新计划所相关的时间和资源。此主题将在章节稍后的“编译、重新编译和执行计划的重用”部分中详细介绍。这种方法保证了如果再次使用不同的相关参数集调用过程，缓存的计划仍然有效，因此可以重用；但如果计划需要在考虑查询中所有谓词（包括对当前执行不相关的谓词）的情况下保持正确，你会意识到这不太可能是高效的。

例如，运行以下代码以仅为 `@orderdate` 参数提供输入值来执行过程：

```sql
EXEC dbo.GetOrders @orderdate = '20140101';
```

观察图 9-1 所示优化器为查询创建的计划。

![图 9-1 使用静态查询解决方案的计划](img/bdc38aa36f6e2987d913ee5381474711_561_0.png)

计划中有多个不同的地方处理不同的谓词，但要点是所有谓词都得到了处理。对于基于 `orderdate` 列的过滤，最高效的计划将是在聚集索引上执行查找和范围扫描的计划。但你在这里看到的是一个完全不同的计划，对于这次执行来说是非常无效的。

你可以采取许多措施来获取高效计划。如果你愿意强制获得计划重用的优势，可以在查询末尾使用 `OPTION(RECOMPILE)`，这会强制 SQL Server 在每次执行时都创建一个新计划。至关重要的是，要使用语句级别的 `RECOMPILE` 而不是存储过程级别的 `RECOMPILE`。对于前者，解析器执行参数嵌入，它将参数与常量嵌入，并在将其传递给优化器之前删除查询的冗余部分。结果是查询仅对与当前执行相关的谓词进行优化，因此获得高效计划的概率很高。

运行以下代码重新创建 `GetOrders` 过程，并在查询中添加 `RECOMPILE` 选项：

```sql
IF OBJECT_ID(N'dbo.GetOrders', N'P') IS NOT NULL DROP PROC dbo.GetOrders;
GO
CREATE PROC dbo.GetOrders
    @orderid AS INT = NULL,
    @custid AS INT = NULL,
    @empid AS INT = NULL,
    @orderdate AS DATE = NULL
AS
    SELECT orderid, custid, empid, orderdate, filler
    FROM dbo.Orders
    WHERE (orderid = @orderid OR @orderid IS NULL)
      AND (custid = @custid OR @custid IS NULL)
      AND (empid = @empid OR @empid IS NULL)
      AND (orderdate = @orderdate OR @orderdate IS NULL)
    OPTION (RECOMPILE);
GO
```

运行以下代码测试基于 `orderdate` 过滤的过程：

```sql
EXEC dbo.GetOrders @orderdate = '20140101';
```

该执行的计划如图 9-2 所示。

![图 9-2 使用 RECOMPILE 按 orderdate 过滤的查询计划](img/bdc38aa36f6e2987d913ee5381474711_562_0.png)

最优计划是在聚集索引上进行查找，它是根据 `orderdate` 定义的。再次执行过程，这次是基于 `orderid` 的过滤：

```sql
EXEC dbo.GetOrders @orderid = 123;
```

该执行的计划如图 9-3 所示。

![图 9-3 使用 RECOMPILE 按 orderid 过滤的查询计划](img/bdc38aa36f6e2987d913ee5381474711_562_1.png)



由于强制重新编译和参数嵌入，你获得了高效的计划。该解决方案使用静态 SQL，因此不会受到攻击。它简单且易于维护。该解决方案的缺点是，根据定义，它不重用计划。但如果频繁使用许多参数组合调用过程，且你希望同时获得高效计划和计划重用呢？有几种方法可以实现。

你可以为每种唯一的参数组合创建一个单独的存储过程，使用 `IF-ELSE` 语句根据指定的参数调用 `GetOrders` 过程。每个过程都将具有仅相关谓词的唯一查询，无需 `RECOMPILE`。通过这种方法，获得高效计划的概率很高。而且计划可以被缓存和重用。解决方案使用静态 SQL，没有注入风险。然而，正如你可以想象，这可能是一个维护噩梦。对于参数，你需要的过程数量是 `Z²`。例如，对于 8 个参数，你将需要 256 个过程。想象一下当你需要进行更改时，需要将其应用到所有过程中。

另一种策略是使用动态 SQL，但采用代码的参数化形式以促进高效计划重用并避免注入。查询字符串从 `SELECT` 和 `FROM` 子句开始 `WHERE`。这样，你不需要维护一个标记来判断是否需要 `WHERE` 子句，以及在连接谓词之前是否需要 `AND` 运算符。解析器将消除此冗余谓词。然后，对于每个指定了值的过程参数，将一个参数化的谓词连接到 `WHERE` 子句。然后使用 `sp_executesql` 执行参数化查询，将查询字符串传递给 `@stmt` 输入，在 `@params` 输入中声明动态批参数，并将过程参数分配给相应的动态批参数。

这里根据新策略重新创建过程：

```sql
IF OBJECT_ID(N'dbo.GetOrders', N'P') IS NOT NULL DROP PROC dbo.GetOrders;
CREATE PROC dbo.GetOrders
@orderid AS INT = NULL,
@custid AS INT = NULL,
@empid AS INT = NULL,
@orderdate AS DATE = NULL
AS
DECLARE @sql NVARCHAR(1000);
```

```sql
SET @sql =
'SELECT orderid, custid, empid, orderdate, filler'
+ N' /* 27702431-107C-478B-8157-60FECC148DD */'
+ N' FROM dbo.Orders'
+ N' WHERE 1 = 1'
+ CASE WHEN @orderid IS NOT NULL THEN
 N' AND orderid = @oid' ELSE N'' END
+ CASE WHEN @custid IS NOT NULL THEN
 N' AND custid = @ocid' ELSE N'' END
+ CASE WHEN @empid IS NOT NULL THEN
 N' AND empid = @eid' ELSE N'' END
+ CASE WHEN @orderdate IS NOT NULL THEN
 N' AND orderdate = @dt' ELSE N'' END
```

```sql
EXEC sp_executesql
@stmt = @sql,
@params = N'@oid AS INT, @cid AS INT, @eid INT, @dt AS DATE',
@oid = @orderid,
@cid = @custid,
@eid = @empid,
@dt = @orderdate;
```

运行以下代码以测试该过程：

解析后，`ORDER BY` 子句导致了以下结果：

`ORDER BY NULL, NULL, shipper DESC, NULL DESC, NULL DESC`

该执行的计划如图 9-6 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_568_0.png)

**图 9-6** 带有多个 `CASE` 表达式并带了重新编译（`RECOMPILE`）的查询计划。

观察到，该计划对 `shipper` 上的聚集索引执行有序扫描，避免了显式排序的需要。

这种解决方案产生了高效的计划。因为它使用了静态查询，所以它不会受到 SQL 注入攻击的影响。然而，它有两个缺点。首先，根据定义，它不重用查询计划。其次，它不支持将多个列作为输入；你最终会得到许多 `CASE` 表达式。

没有这些缺点的解决方案是基于动态 SQL 的。你通过注入排序列方向来构造带有 `ORDER BY` 子句的查询字符串。这种解决方案显而易见的挑战是容易受到 SQL 注入。不过，表结构通常倾向于非常静态。你可以包含一个测试，以确保输入列名出现在你想要从表中支持的硬编码排序列集中。如果该列没有出现在集中，你就会中止查询，怀疑是尝试进行 SQL 注入。如果支持的排序列集发生变化，你只需修改过程定义。很可能更改的频率足够低，使得这种方法变得可行。

使用以下代码通过此策略重新创建过程：

```sql
IF OBJECT_ID(N'dbo.GetSortedShippers', N'P') IS NOT NULL DROP PROC dbo.GetSortedShippers;
GO
CREATE PROC dbo.GetSortedShippers
@colname AS sysname, @sortdir AS CHAR(1) = 'A'
AS
IF @colname NOT IN(N'shipperid', N'companyname', N'phone')
THROW 50001, 'Column name not supported. Possibly a SQL injection attempt.', 1;
```

```sql
DECLARE @sql AS NVARCHAR(1000);

SET @sql = N'SELECT shipperid, companyname, name
FROM Sales.Shippers
ORDER BY '
+ QUOTENAME(@colname) + CASE @sortdir WHEN 'D' THEN N' DESC' ELSE '' END + ';';

EXEC sys.sp_executesql @stmt = @sql;
GO
```

`QUOTENAME` 函数用于用方括号限定排序列名。在你的特定示例中，不需要分隔符，但万一你需要支持被视为不规则标识符的列名，你将需要这些分隔符。

使用以下代码测试该过程：

```sql
EXEC dbo.GetSortedShippers N'shipperid', N'D';
```

该执行的计划如图 9-7 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_569_0.png)

**图 9-7** 动态查询的计划。

这是一个依赖索引顺序的高效计划。与之前的解决方案相比，如果你需要支持多个输入排序、之前缓存的计划，可以很容易地扩展。这种解决方案可以通过以下代码演示：

```sql
IF OBJECT_ID(N'dbo.GetSortedShippers', N'P') IS NOT NULL DROP PROC dbo.GetSortedShippers;
GO
CREATE PROC dbo.GetSortedShippers
@colname1 AS sysname, @sortdir1 CHAR(1) = 'A',
@colname2 AS sysname = NULL, @sortdir2 AS CHAR(1) = 'A',
@colname3 AS sysname = NULL, @sortdir3 AS CHAR(1) = 'A'
AS
IF @colname1 NOT IN(N'shipperid', N'companyname', N'phone')
OR @colname2 IS NOT NULL AND @colname2 NOT IN(N'shipperid', N'companyname', N'phone')
OR @colname3 IS NOT NULL AND @colname3 NOT IN(N'shipperid', N'companyname', N'phone')
THROW 50001, 'Column name not supported. Possibly a SQL injection attempt.', 1;
```

```sql
DECLARE @sql AS NVARCHAR(1000);

SET @sql = N'SELECT shipperid, companyname, phone
FROM Sales.Shippers
ORDER BY '
+ QUOTENAME(@colname1) + CASE @sortdir1 WHEN 'D' THEN N' DESC' ELSE N' ASC' END
+ ISNULL(N', ' + QUOTENAME(@colname2) + CASE @sortdir2 WHEN 'D' THEN N' DESC' ELSE N' ASC' END, N'')
+ ISNULL(N', ' + QUOTENAME(@colname3) + CASE @sortdir3 WHEN 'D' THEN N' DESC' ELSE N' ASC' END, N'')
+ N';';
EXEC sys.sp_executesql @stmt = @sql;
GO
```

关于安全性，重要的是知道，通常执行存储过程的用户将需要运行动态执行代码的直接权限。如果你不想授予此类权限，可以使用 `EXECUTE AS` 子句来冒充该子句中指定的用户上下文。你可以在 Books Online 中找到有关如何操作此详情：http://msdn.microsoft.com/en-us/library/ms18834.aspx。

作为额外资源，你可以在论文《The Curse of SQL》中找到对动态 SQL 的极佳介绍。

```sql
IF OBJECT_ID(N'dbo.EndYear') IS NOT NULL DROP FUNCTION dbo.EndYear;
GO
CREATE FUNCTION dbo.EndYear(@dt DATE) RETURNS DATE
AS
BEGIN
    RETURN DATEADD(year, DATEDIFF(year, '19001231', @dt), '19001231');
END;
GO
```

现在将直接表达式替换为对 UDF（用户定义函数）的调用并运行查询，例如：

```sql
SELECT orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderdate = dbo.EndYear(orderdate);
```

与不使用 UDF 相比，在这里获得的编程优势是不言而喻的。代码更加清晰、简洁。然而，使用 UDF 对性能的影响非常严重。观察图 9-9 所示的该查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_572_0.png)

| 谓词 |
| :--- |
| `[PerformanceV3].[dbo].[Orders].[orderdate] = [PerformanceV3].[dbo].[EndYear]([PerformanceV3].[dbo].[Orders].[orderdate])` |

图 9-9 使用标量 UDF 的查询计划。

遗憾的是，即使 UDF 是基于单个表达式的，SQL Server 也不会对其进行内联（inline）。这意味着正如计划中 Filter 算子的 Predicate 属性所示，UDF 会针对底层表中的每行调用一次。在我们的案例中，UDF 被调用了 1,000,000 次。每次调用都有开销，而百万次调用积累的开销是巨大的。此外，请注意查询计划是串行的。任何对 T-SQL 标量 UDF 的使用都会阻止并行。

该查询在我的系统上花费了四多秒完成，总 CPU 成本超过四秒。这是没有 UDF（使用默认并行计划）查询的 16 倍，也是强制使用串行计划的 8 倍。无论如何，如你所见，使用 UDF 的代价非常高。

有趣的是，有一种变通方法允许将逻辑封装在函数中而不会产生性能惩罚。不要使用标量 UDF，而是使用内联 TVF（表值函数）。困难之处在于内联 TVF 必须返回一个查询。因此，在 `FROM-SELECT` 查询中指定表达式和列别名，并从函数返回该查询。以下是删除标量 UDF 并创建内联 TVF 的代码。

```sql
IF OBJECT_ID(N'dbo.EndOfYear') IS NOT NULL DROP FUNCTION dbo.EndOfYear;
GO
CREATE FUNCTION dbo.EndOfYear(@dt DATE) RETURNS TABLE
AS
SELECT DATEADD(year, DATEDIFF(year, '19001231', @dt), '19001231') AS endofyear;
GO
```

要在查询中调用表函数并将外部表的列作为输入，您需要使用 `APPLY` 算子或子查询中的内联。以下是隐式形式的示例：

```sql
SELECT orderid, custid, empid, shipper, orderdate, filler
FROM dbo.Orders
WHERE orderdate = (SELECT endofyear FROM dbo.EndOfYear(orderdate));
```

这一次，函数中的表达式被内联了。SQL Server 创建的计划与我在之前 9-8 节中显示的原始无 UDF 查询计划相同。使用内联 TVF 没有惩罚。

作为基于多个语句的标量 UDF，它们通常用于实现迭代逻辑。正如本书前面第 2 章“查询调优：T-SQL 迭代”中讨论的那样，特别是当你需要应用多次迭代时，使用 CLR UDF 而不是 T-SQL UDF 将获得更好的性能。此外，只要 CLR UDF 未标记为应用数据，它就会阻止并行。

一个使用迭代逻辑的 T-SQL UDF 示例，考虑以下 `RemoveChars` UDF 的定义：

```sql
USE TSQLV3;
IF OBJECT_ID(N'dbo.RemoveChars', N'FN') IS NOT NULL DROP FUNCTION dbo.RemoveChars;
GO
CREATE FUNCTION dbo.RemoveChars(@string NVARCHAR(4000), @pattern NVARCHAR(4000))
RETURNS NVARCHAR(4000)
AS
BEGIN
    DECLARE @pos AS INT;
    SET @pos = PATINDEX(@pattern, @string);

    WHILE @pos > 0
    BEGIN
        SET @string = STUFF(@string, @pos, 1, N'');
        SET @pos = PATINDEX(@pattern, @string);
    END
    RETURN @string;
END;
GO
```

此函数接受两个参数。一个是 `@string`，代表输入字符串。另一个是 `@pattern`，代表单个字符的模式。UDF 的目的是返回一个字符串，该字符串是移除所有输入字符出现后的输入字符串。函数代码开始使用 `PATINDEX` 函数找到字符模式在 `@string` 中的第一个位置。然后代码进入循环，只要字符串中仍存在模式的项，循环就会一直运行。在每次迭代中，代码使用 `STUFF` 函数从字符串中删除第一个出现项，并寻找下一个位置。循环完成后，代码返回 `@string` 中剩余的内容。

这是一个在对 `Sales.Customers` 表查询中使用 UDF 清理电话号码（通过删除所有非数字字符）的示例：

```sql
SELECT custid, phone, dbo.RemoveChars(phone, N'[^0-9]') AS cleanphone
FROM Sales.Customers;
```

该函数返回如下：

| custid | phone | cleanphone |
|---|---|---|
| 1 | 030-456789 | 030456789 |
| 2 | (5)789-0123 | 57890123 |
| 3 | (5)123-456 | 5123456 |
| 4 | (171)456-789 | 171456789 |
| 5 | 0921-678901 | 0921678901 |
| 6 | 0621-8990 | 06218990 |
| 7 | 67.89-0123 | 67890123 |
| 8 | (91)345 6789 | 913456789 |
| 9 | 23.45,6789 | 23456789 |
| 10 | (604)901-2345 | 6049012345 |

你将在后面的 *SQL programming* 章节中学习如何创建 CLR UDF。使用基于 CLR 的解决方案而不是 T-SQL 解决方案有两个优势：第一，正则表达式比你可以与 `PATINDEX` 函数使用的原始模式丰富得多；第二，获得更好的性能。我针对一个 1,000,000 行的表进行了测试，T-SQL UDF 运行了 16 秒，而 CLR 的运行了 8 秒。

## 多语句 TVF (Multistatement TVFs)

多语句 TVF 内部包含多个语句，并返回一个表变量作为输出。返回的表定义在函数头部。体的作用是填充表变量。当你查询此类函数时，SQL Server 声明表变量，运行填充，将其交给调用查询。为了演示多语句 TVF，我将使用以下代码创建并填充 `Employees` 表：



```sql
SET NOCOUNT ON;
USE tempdb;
GO
IF OBJECT_ID(N'dbo.Employees', 'N'U') IS NOT NULL DROP dbo.Employees;
GO
CREATE TABLE dbo.Employees
(
  empid INT NOT NULL PRIMARY KEY,
  mgrid INT NOT NULL REFERENCES dbo.Employees(empid),
  empname VARCHAR(25) NOT NULL,
  salary MONEY NOT NULL,
  CHECK (empid <> mgrid)
)
```

```sql
INSERT INTO dbo.Employees(empid, mgrid, empname, salary)
VALUES(1, NULL, 'David', 10000.00),
(2, 1, 'Eitan', 7000.00),
(3, 1, 'Ina', 7500.00),
(4, 2, 'Seraph', 5000.00),
(5, 2, 'Jim', 5000.00),
(6, 2, 'Steve', 4500.00),
(7, 3, 'Aaron', 5000.00),
(8, 5, 'Lilach', 3500.00),
(9, 7, 'Rita', 3000.00),
(10, 5, 'Sean', 3000.00),
(11, 7, 'Gabriel', 3000.00),
(12, 9, 'Emilia', 2000.00),
(13, 9, 'Michael', 2000.00),
(14, 9, 'Didi', 1500.00);
```

以下是 `GetSubtree` 函数的定义：

```sql
IF OBJECT_ID(N'dbo.GetSubtree', 'N'TF') IS NOT NULL DROP function GetSubtree
GO
CREATE FUNCTION dbo.GetSubtree (@mgrid AS INT, @maxlevels AS INT = NULL)
RETURNS @Tree TABLE (
  empid INT NOT NULL PRIMARY KEY,
  mgrid INT NOT NULL,
  empname VARCHAR(25) NOT NULL,
  salary MONEY NOT NULL,
  lvl INT NOT NULL
)
AS
BEGIN
    DECLARE @lvl AS INT = 0;
    -- 将根节点插入到 @Tree
    INSERT INTO @Tree
    SELECT empid, mgrid, empname, salary, @lvl
    FROM dbo.Employees
    WHERE empid = @mgrid;

    WHILE @@ROWCOUNT > 0 AND (@lvl < @maxlevels OR @maxlevels IS NULL)
    BEGIN
        SET @lvl += 1;
        -- 将上一层的子节点插入 @Tree
        INSERT INTO @Tree
        SELECT E.empid, E.mgrid, E.empname, E.salary, @lvl
        FROM dbo.Employees AS E
        INNER JOIN @Tree AS T ON E.mgrid = T.empid
        WHERE T.lvl = @lvl - 1;
    END
    RETURN;
END;
GO
```

在使用多语句表值函数（TVFs）时需要记住一点，它们返回的是表变量。请记住，与临时表不同，SQL Server 不会对表变量维护直方图。因此，优化器需要对表变量进行基数估计，而它可以使用的工具相对局限。直方图的缺失可能导致次优方案的选择。这对于函数体内部针对表变量的查询，以及针对该函数的外部查询都是如此。如果你发现了与缺少直方图相关的性能问题，你将需要重新评估你的解决方案。

另一种方案是使用带有临时表的存储过程。这种方法的缺点是，与存储过程的结果进行交互不像查询表函数的结果那样方便。你需要确定自己的优先事项，并进行一些测试，以查看是否存在性能差异以及这种差异有多大。

# 存储过程

在本节中，我将介绍 T-SQL 存储过程的使用。如所述，由于本书的重点是查询，我将主要介绍如何使用存储过程来执行查询以及代码的调优方面。我将首先描述存储过程优于即兴代码（hoc code）的优势。然后，我将介绍 SQL Server 处理编译、重新编译以及执行计划重用的方式。我还会涵盖表类型和表值参数的使用，以及 `EXEC RESULT SET` 子句。

存储过程是一个重要的编程工具，与使用即兴代码实现解决方案相比，它可以带来许多好处。与其他编程环境一样，将逻辑封装在例程中可以实现重用并允许你隐藏复杂性。

与在应用程序中部署更改相比，在存储过程中部署更改要简单得多。无论你是要修复 Bug 还是有更有效的方法来完成任务，只需发布 `ALTER PROC` 命令，所有人立即开始使用修改后的版本。

通过存储过程，你往往可以减少大量的网络流量。通过网络传输的只是过程名称和输入参数。逻辑在数据库引擎中执行，只需要将最终结果传回调用者。在应用程序中实现逻辑往往会导致应用程序与数据库之间之间的往返，从而产生更多的网络流量。

在存储过程中使用参数化查询促进了高效的缓存和重用行为。这是下一节的重点。不过，我应该指出，这种能力并不是存储过程查询所有的。当使用 `sp_executesql` 参数化查询时，也可以获得类似的收益。

# 编译、重新编译和执行计划的重用

当你需要调优存在性能问题的存储过程时，你应该将精力集中在两个主要领域。一个是根据你目前为止在书中学的知识调优过程内部的查询。为此，查询是否存在于存储过程中并不重要。另一个与计划缓存、重用、参数嗅探、变量嗅探和重新编译有关。

> 本节中的示例假设你有一个示例数据库 `PerformanceV3` 的干净副本。如果没有，请先运行书籍源码中的 `PerformanceV3.sql` 脚本。

## 执行计划的重用和参数嗅探

当你创建一个存储过程时，SQL Server 不会优化其中的查询。它会在你第一次执行该过程时进行优化。初始编译（主要是查询优化）是在整个批处理（过程）级别进行的。SQL Server 会缓存查询计划，以便后续执行该过程。当 SQL Server 触发重新编译时，它是在语句级别执行的。

计划缓存和重用的用是为了节省创建新计划所涉及的时间、CPU 和内存资源。SQL Server 创建新计划需要多长时间？我见过花费几毫秒就能创建的计划，也见过需要几分钟才能创建的计划。SQL Server 根据所涉及表的大小来确定优化过程的时间和成本阈值。你可以在图形化或 XML 查询计划的根节点（即 SELECT 节点）中找到有关编译的细节。你会发现以下属性：`CompileTime`（毫秒）、`CompileCPU`（毫秒）、`CompileMemory`（KB）、`Optimization Level`（TRIAL 或 FULL）、`Reason For Early Termination`（找到了低于阈值的足够计划，或达到时间时的 Timeout）等。

SQL Server 的假设是如果存在有效的缓存计划，通常重用它是有益的。因此，默认情况下会尝试这样做。在某些条件下，SQL Server 将触发重新编译，导致创建新计划。我将在“重新编译”部分讨论这个主题。

我将使用一个名为 `GetOrders` 的存储过程来演示计划缓存和重用。运行以下代码在 `PerformanceV3` 数据库中创建该过程：

```sql
USE PerformanceV3;
IF OBJECT_ID('N''dbo.GetOrders','N') IS NOT NULL DROP PROC dbo.GetOrders;
GO

CREATE PROC dbo.GetOrders(@orderid INT)
AS

SELECT orderid, customer, empid, order
FROM dbo.orders
WHERE orderid >= @orderid;
GO
```

该过程接受订单作为输入，并返回所有订单 ID 大于等于输入 ID 的订单信息。我在代码中放置了一个 GUID 作为注释，以便于跟踪与此相关的缓存中的计划。

在 `orderid` 列上定义了一个名为 `PK_Orders` 的非聚集、非覆盖索引。

正如你所看到的，当过程的不同执行提供了具有相似性质的输入时，计划重用是有益的。但如果情况并非如此呢？例如，使用具有中等选择性的输入参数执行该过程：

```sql
EXEC dbo.GetOrders @orderid = 800001;
```

通常情况下，此查询将受益于一个对聚集索引进行全扫描的计划。但由于缓存中已存在该计划，它被重用了，如图 9-12 所示：

![](img/bdc38aa36f6e2987d913ee5381474711_581_0.png)

**图 9-12** 为该过程的第三次执行所示。

参数的编译值是创建计划时使用的（99999），但运行时的值是 800001。算子的成本和估计的行数与创建计划时的计划相同，因为它们反映的是参数编译值。但箭头比之前要粗得多，因为它们反映了本次执行中的实际行数。Index Seek（索引查找）算子返回了 200,000 行，因此该计划执行了许多键查找（key lookups）。该计划在我的系统上执行了 600,524 次逻辑读取。与聚集索引扫描的成本相比，这太巨大了：

我们存储过程中的查询非常简单；它只是一个过滤器以及一个包含几列的 SELECT 列表。尽管如此，这个简单的示例也说明了估算不准确的概念及其一些可能的影响，例如选择索引查找和键查找而不是索引扫描，以及选择串行计划而不是并行计划。你可以自由尝试更多的查询元素来演示其他影响。例如，如果你正在进行分组和聚合，你还将能够观察到估算不准确对选择聚合算法的影响，以及对所需内存授予（用于排序和哈希算子）的影响。使用以下代码修改该过程，在查询中添加分组和聚合：

```sql
ALTER PROC dbo.GetOrders(@orderid AS INT )
AS

SELECT empid, COUNT(*) AS numbers
/* 703FCFF2-97F0-4777-A8B78BE0A4D *
FROM dbo.Orders
WHERE orderid >= @orderid
GROUP BY empid;
GO
```

通常，具有高选择性（例如，输入 @orderid = 999991）时，最佳计划是带有索引查找、键查找、排序算子和基于顺序的聚合（Aggregate）的串行计划。具有中等选择性（例如，输入 @orderid = 800001）时，最佳计划是带有索引扫描、本地哈希聚合和全局顺序聚合的并行计划。

你获得哪种计划取决于你在第一次执行时提供的输入。例如，首先用高选择性执行该过程。你将获得一个带有索引查找和键查找、排序算子以及基于顺序的聚合的串行计划。此外，查询将为排序操作请求一个较小的内存授予。（请参见实际查询中根 SELECT 节点的属性）此计划将被缓存。然后用中等选择性执行该过程。缓存的计划将被重用。不仅排序操作的内存授予效率低下，而且它将不得不溢出到 tempdb。（实际查询计划中的 Sort 算子将显示警告效果）

在查询中添加分组和聚合只是你如何尝试不同查询以观察基数估算影响的一种想法。当然，还有许多其他可以尝试的方法，如连接、排序等。

## 防止执行计划重用

当面临如上一节所的由于计划重用对你没有益处的情况时，你通常会做几件事。如果你只有一个带有过滤器的查询（没有分组和聚合或其他元素），一种选项是创建一个覆盖索引。由于计划重用是的，优化器会选择一个执行聚集索引扫描的计划。无论聚集索引的输入选择性如何，由于计划重用，它总是该计划的。此外，如果存在分组和聚合操作，由于计划重用，重你是有益的。

另一种选项是通过添加 RECOMPILE 强制查询每次执行都重新编译：

```sql
ALTER PROC dbo.GetOrders(@orderid AS INT )
AS

DECLARE @i AS INT = @orderid - 1;

SELECT orderid, custid, emdate, filler
/*703CCFF2-970F-4777-A8B7-A78BE0A4D */
FROM dbo.Orders
WHERE orderid >= @i
OPTION(RECOMPILE);
```

使用参数嵌入选项与计划重用之间的权衡是由于估算不准确的。对于缓存来说，使用语句级选项时 SQL Server 不会缓存。

为了测试该过程，请用高选择性和中等选择性执行它：

```sql
EXEC dbo.GetOrders @orderid = 999991;
EXEC dbo.GetOrders @orderid = 800001;
```

# 表 9-1 硬编码估算值

| 操作符 | 估算值 |
| --- | --- |
| >, >=, < <= | 30% |
| BETWEEN/LIKE | 9% 异常：在 2014 年，带有变量/参数嗅探的 BETWEEN 禁用估算值为 16.4317 |
| = 唯一列 | 1 行 |
| = 非唯一列（SQL Server 2014 之前） | $C^{3/2}$ (C = 表基数) |
| = SQL Server 2014 中的非唯一列 | $C^{1/2}$ |

该执行的计划如图 9-14 所示。

| 实际行数 | 5 |
| --- | --- |
| 估算行数 | 300000 |

**图 9-14** 使用变量的查询计划。

该计划在我的系统上执行了 25,072 次读取。考虑到匹配的数量较少，这是低效的。在这里，如果采用在非聚集索引 PK_Orders 上进行查找（seek）并进行键查找（key lookups）的计划将高效得多。

解决“缺少嗅探”问题有两个主要的解决方案。你应该使用哪种解决方案取决于是否希望重用计划。通常重用计划是理想的，如果存储在变量中的值具有相同的性质。在这种情况下，你可以使用查询 `OPTIMIZE FOR` 并为变量指定一个值以供优化。在我们的案例中，查询是 `@orderid`，因此你将使用以下格式：`<query>OPTION(OPTIMIZE FOR (@i = <value>)>`。由于优化器无法嗅探变量，你实际上是在告诉它要优化哪个值。优化器将使用该值来做出基数估算。

确定要提供的值有点棘，因为你必须提供一个常量。在我们的案例中，我们希望优化器假设高选择性。如果你提供一个像 1000000 这样的值，对于当前数据状态的估算将是高选择性的，但在添加足够多的数据后，就不再是了。如果 SQL Server 支持指定带有输入集匹配百分比的提示，那太好了，但遗憾的是它不支持。因此，你需要提供一个常量值，即使数据不断变化，该值也能保持高选择性的估算。你可以通过提供该类型支持的最大值来实现这一点。对于 `INT`，该值是 2147483647。在这种情况下，基数估算为 1（优化器能估算的最小值），因此，最优计划是使用非聚集索引 PK_Orders 并应用键查找的计划。

# 第 9 章 可编程对象

通过运行以下代码来修改存储过程以实现此解决方案：

```sql
ALTER PROC dbo.GetOrders (@orderid AS INT )
AS

DECLARE @orderid AS INT = @orderid - 1;

SELECT orderid, custid, empid, orderdate, filler
/* 7D3CFCF2-970F-4777-A8B7-8A8BE0A4D */
FROM dbo.Orders
WHERE orderid >= @orderid
OPTION (OPTIMIZE FOR(@i = 2147483647));
GO
```

运行以下代码测试该存储过程：

```sql
EXEC dbo.GetOrders @orderid = 9999997;
```

该执行的计划如图 9-15 所示。

| 实际行数 | 5 |
| --- | --- |
| 估算行数 | 1 |

![](img/bdc38aa36f6e2987d913ee5381474711_586_0.png)

图 9-15 使用 OPTIMIZE FOR 的查询计划。

如你所示，该计划对于高选择性是最优的。观察到应用过滤器后返回的估算行数为 1，实际为 5。该估算值足够让优化器选择最优计划。该计划的执行在我的系统上执行了 18 次逻辑读取。

如果你系统中的典型情况是过滤器具有低选择性，你可以选择“优化”值 0。然而，如果典型情况是过滤器具有中等选择性，那么通过这个提示你无法根据当前和未来的数据状态获得这样的估算。这个提示确实有其局限性。

如果你不希望重用计划——例如，当存储过程执行时变量中的值具有不同性质时——你就走运了。你指定查询提示 `RECOMPILE`，通过在语句级别上这样做，你获得了一个有趣的副作用。语句在变量值赋值后进行优化。换句话说，你获得了变量嗅探。

修改存储过程以实现此解决方案：

```sql
ALTER dbo.GetOrders(@orderid AS INT )
AS
DECLARE @i INT = @orderid - 1;

SELECT orderid, custid, empid, detail
/* 70JCFCF2-970F-4777-A8B7-8A7BBE0A4D */
FROM dbo.Orders
WHERE orderid >= @i
OPTION (RECOMPILE);
GO
```

运行以下代码以高选择性测试存储过程：

```sql
EXEC dbo.GetOrders @orderid = 999997;
```

该执行的计划如图 9-16 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_586_0.png)

图 9-16 使用 RECOMPILE 的查询计划。

![](img/bdc38aa36f6e2987d913ee5381474711_587_0.png)



# 第 9 章 可编程对象

## 防止参数嗅探

你看到了参数嗅探是一个有用的功能。然而，你可能会遇到该功能适得其反的情况。例如，基数估算的一个经典挑战涉及一个递增列。假设 `GetOrders` 存储过程的典型执行具有中等选择性——比如 10%。在选择性方面，我的系统执行了 8 次逻辑读取，最优计划是形成聚集索引的计划。问题是，优化器能发现这一点吗？

挑战在于直方图通常在发生 50% 的变化后才刷新。在存储过程中，你正在查询顶部范围。如果添加了大量行但不足以触发直方图的刷新，那么新的行范围不在直方图中。如果此时 SQL Server 创建新计划并依赖直方图进行基数估算，可能会导致低估。

微软在 SQL Server 2014 中采取了措施解决这个问题。当谓词的范围超过直方图中的最大值时（如 `>=` 操作符所示），基数估算器会考虑现有的直方图和自上次刷新以来的变化计数。它根据数据的平均分布插值新的范围分布。你可以在第 2 章关于基数估算改进的讨论中找到该技术的介绍。因此，在 SQL Server 2014 中，你很有可能得到合理的估算，并且最优计划。然而，在 SQL Server 2014 之前，默认情况下你可能会得到低估。这是一个你最好禁用参数嗅探并让 SQL Server 使用参数值已知时的估算技术的情况。

目前，Orders 表包含 1,000,000 行，订单 ID 为 1 到 100,000。统计信息是最新的，因为源代码在填充表后创建并填充了数据库的索引。运行以下代码向表添加 100,000 行（10%）：

```sql
INSERT INTO dbo.Orders(orderid, custid, empid, shipperid, orderdate, filler)
SELECT 2000000 + orderid, custid, empid, shipperid, orderdate, filler
FROM dbo.Orders
WHERE orderid <= 100000;
```

运行以下代码显示直方图：

```sql
DBCC SHOW_STATISTICS ('dbo.Orders', 'PK_Orders') WITH HISTOGRAM;
```

此代码生成了以下输出：

| RANGE_HI_KEY | RANGE_ROWS | EQ_ROWS | DISTINCT_RANGE_ROWS | AVG_RANGE_ROWS |
| --- | --- | --- | --- | --- |
| 1 | 0 | 1 | 0 | 1 |
| 100000 | 999998 | 1 | 999998 | 1 |

观察发现，直方图中记录的最大值为 1000000。直方图中没有包含你刚刚添加到表中的行的表示。

接下来，我将演示一种在 SQL Server 2014 之前获取的基数估计低估情况。

由于我在 SQL Server 2014 中运行代码，我将使用查询跟踪标志 9481 来强制 SQL Server 使用旧版基数估计器。执行以下查询：

```sql
SELECT orderid, custid, empid, orderdate, filler
/* 703FCF22-920F-4777-A8B7-8A878BE0A4D */
FROM dbo.Orders
WHERE orderid >= 100001
OPTION(QUERYTRACEON 9481);
```

该查询的执行计划如图 9-8 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_589_0.png)

**图 9-18** 基于 SQL Server 2014 之前的基数估计的查询计划。

旧版基数估计器发现你正在过滤的范围在直方图最大值之后。对于它来说，本应该有 0 个标记，但它能估计的最小值是 1。根据对 1 的估计，优化器选择了一个适用于高选择性的计划。在实践中，实际匹配数量为 100,000。该计划的执行在我们系统上执行了 300,264 次逻辑读取。与理想计划应付给你的成本（聚集索引扫描大约 25,000 次读取）相比，这显然是昂贵的。

在 SQL Server 2014 之前，微软提供了跟踪标志 2388 作为处理升序键查询的可能。当启用跟踪标志时，如果 SQL Server 在直方图的连续刷新中观察到键不断增加，它会将列标记为升序。然后，在查询编译时，SQL Server 更新统计信息并在直方图末尾添加一个时间步以包含最近添加的数据。

但如果你使用的是 2014 之前的 SQL Server 版本且不想启用此标志怎么办？另一个选项是禁用参数嗅探。如果你选择这样做，你是在强制 SQL Server 依赖于假设参数值未知的基数估计方法。你可以在早前的表 9-1 中找到 SQL Server 在这种情况下使用的估计值。

在查询/存储过程级别本地禁用参数嗅探有两种主要方法。不推荐的方法是将参数值存储在变量中，然后在查询中引用该变量，如下：

```sql
ALTER PROC dbo.GetOrders(@orderid INT)
AS

DECLARE @i AS INT = @orderid;

SELECT orderid, custid, empid, orderdate, filler
/* 703CCF22-970F-4777-A8B8BEE0A4D */
FROM dbo.Orders
WHERE orderid >= @i;
GO
```

记住，通常 SQL Server 无法嗅探变量值。

通过运行以下代码测试该存储过程：

此存储过程的执行生成如图 9-19 所示的计划。

| 实际行数 | 100000 |
| --- | --- |
| 估计行数 | 330000 |

![](img/bdc38aa36f6e2987d913ee5381474711_590_0.png)

图 9-19 使用变量防止嗅探的计划。

如果你检查表 9-1 中的硬编码估计值，你会发现使用 `>=` 运算符时，估计比例为 30%。将此百分比应用于表的基数（1,100,000 行），你得到 330,000 行。在查询计划中观察到，估计行数为 330,000，而实际为 100,000。也许这不是一个完美的估计，但它比估计为 1 要好得多。优化器选择了一个聚集索引扫描，尽管是服务器级别的扫描，在我的系统上涉及了 27,871 次逻辑读取。对于中低选择性，这显然比一个在 PK_Orders 索引中应用查找和查找的计划要好。

这种方法可以起作用，但存在一些问题。首先，它很笨拙。其次，如果在语句级别发生重新编译，SQL Server 可能会突然嗅探变量值。禁用参数嗅探推荐的方法是使用指定的查询提示。要禁用对特定参数的嗅探，请使用 `OPTIMIZE FOR (@orderid UNKNOWN)`。要禁用所有参数的嗅探，使用 `OPTIMIZE FOR UNKNOWN`。

将此解决方案应用于我们的存储过程：

```sql
ALTER PROC dbo.GetOrders(@orderid AS INT)
AS
SELECT orderid, custid, empid, orderdate, filler
/* 703FCFF2-920F-4777-A8B7-8A7B8EA4D */
FROM dbo.Orders
WHERE orderid >= @orderid
OPTION(OPTIMIZE FOR (@orderid UNKNOWN));
GO
```

运行以下代码测试存储过程：

```sql
EXEC dbo.GetOrders @orderid = 100001;
```

你将获得与图 9-19 相同的计划。

在 SQL Server 2014 中（得益于基数估计器的改进），你实际上不需要禁用嗅探即可获得良好的估计。运行以下代码修改存储过程，使其使用不带提示的原始代码：

```sql
ALTER PROC dbo.GetOrders(@orderid AS INT)
AS
SELECT orderid, custid, empid, orderdate, filler
/* 703FCFF2-920F-4777-A8B7-8A7B8EA4D */
FROM dbo.Orders
WHERE orderid >= @orderid
GO
```

运行以下代码测试存储过程：

```sql
EXEC dbo.GetOrders @orderid = 100001;
```

该执行的计划位于图 9-20。

![](img/bdc38aa36f6e2987d913ee5381474711_591_0.png)

**图 9-20** 基于 SQL Server 2014 基数估计的查询计划。

新的基数估计器考虑了自上次刷新以来的直方图变化。如计划所示，插值的基数估计是准确的。这为我们的中等选择性得到了优化计划——即聚集索引扫描。

升序键问题只是你可能想要禁用参数嗅探的情况。在这些情况下，使用 `OPTIMIZE FOR (@parameter UNKNOWN)` / `OPTIMIZE FOR UNKNOWN` 提示比使用变量要好。

## 编译

在某些情况下，SQL Server 的升序键问题只是你可能想要禁用参数嗅探的情况。在这些情况下，使用 `OPTIMIZE FOR (@parameter UNKNOWN)` / `OPTIMIZE FOR UNKNOWN` 提示比使用变量要好。

如果 SQL Server 创建了新计划而不是重用旧计划，状态如下：

编译

（此处省略重复的逻辑描述）

观察到查询在缓存中找到的两个计划，其 `set_options` 位图是不同的。正如你可能察觉到的，位图中的位值 8 代表 `CONCAT_NULL_YELDS_NULL` 选项。

基于此行为得出的结论是，你应该努力使用一致的环境连接到 SQL Server，以促进高效的计划行为。

重新编译的另一类被称为计划优化性。当缓存计划的优化性产生疑问（而非正确性）时，SQL Server 会应用此类编译。例如，足够的数据变化就属于计划优化性的重新编译情况。其逻辑是：随着足够的数据变化，现有的缓存计划可能不再是最优的。

SQL Server 在列级别跟踪变化。当 SQL Server 考虑重用缓存计划时，对于优化过程中使用的每个直方图，它都会检查自上次统计信息刷新以来相应列发生了怎样的变化。如果达到重新编译阈值，SQL Server 将更新统计信息并触发重新编译。重新编译阈值根据你添加的行数逐渐变化。普通表和临时表的步骤略有不同，具体如下：添加 1 行后，添加 500 行后，然后每增加 500 行加上 20%。对于临时表，步骤是添加 1 行后，添加 6 行后，添加 500 行后，然后每增加 500 行加上 20%。

对于大表，500% 可能代表大量的行。这可能导致自动统计信息的更新频率不够，不足以支持最优计划。SQL Server 支持标记 2371，该标记可以将百分比降低到表行数。你可以在此处找到有关此跟踪标记的详细信息：http://blogs.microsoft.com/sqlserver/archive/2011/09/07/changes-to-automatic-updates-in-sql-server-traceflag-2371.aspx。

在 SQL Server 2014 中，微软为分区表引入了增量统计信息。SQL Server 在表级别维护统计信息。它在整个表的直方图中使用高达 200%，并对表的基数应用 500 + 200% 的计算。使用增量统计信息时，SQL Server 在分区级别维护统计信息。它每个分区的直方图中使用高达 200%，并对分区的基数应用 500 + 20% 的计算。关于此功能的细节，请参见此处 `CREATE STATISTICS` 命令中的 `INCREMENTAL` 部分：http://ms.microsoft.com/en-us/library/ms18038.aspx。

你可能会遇到此类情况：SQL Server 第一次创建的执行计划在数据发生重大变化后仍能保持最优。例如，`GetOrders` 存储过程的典型用例是查询最后几个订单。在这种情况下，计划优化性的重新编译是没有意义的。每当创建一个新计划时，它都将是同一个计划。为了防止重新编译，你可以添加查询提示 `KEEPFIXED PLAN`。这无法阻止 SQL Server 应用计划稳定性重新编译，因为你不能强制它使用一个被认为无效的计划。对于优化性重新编译，已知缓存计划是有效的。因此，如果你对这种选择的性能影响承担责任，SQL Server 在处理“不编译”请求方面没有问题。

使用以下代码带有 `KEEPFIXED PLAN` 查询提示修改 `GetOrders` 存储过程：

```sql
ALTER PROC dbo.GetOrders(@orderid AS INT )
AS

SELECT orderid, custid, empid, orderdate, filler
/* 703FCFF2-970F-4777-A8B7-8A7B8BE0A4D */
FROM dbo.Orders
WHERE orderid >= @orderid
OPTION(KEEPFIXED PLAN);
GO
```

在测试代码时，请确保重新运行 `PerformanceV3.sql` 脚本以重新创建示例数据库。

## 表类型和表值参数

表类型是存储为数据库中对象的对象的表定义。你可以将其用作表变量以及存储过程和用户定义函数表值参数的类型。

表类型可以包含表变量定义中允许的通常元素。元素包括标识属性、计算列、`CHECK`、`DEFAULT`、`PRIMARY KEY` 和 `UNIQUE` 约束。从 SQL Server 2014 开始，表类型甚至拥有内联索引定义。它可以没有外键约束。

作为表变量的类型，它赋予你可重用性。如果你需要在相同的结构上声明表变量，使用表类型可以避免重复定义。例如，假设你在代码的多个地方使用一个持有 `OrderIds` 的表变量，并为了演示排序的目的进行排序。你使用 `CREATE TYPE` 命令定义名为 `OrderIds` 的表类型，如下：

```sql
USE SQLV;
IF TYPE_ID('dbo.OrderIds') IS NOT NULL DROP TYPE dbo.OrderIds;
GO
CREATE TYPE dbo.OrderIds AS TABLE
(
    pos INT NOT NULL PRIMARY KEY,
    orderID INT NOT NULL UNIQUE
);
```

然后，要声明此类型的表变量，使用 `DECLARE` 语句，并且不是指定表定义，而是指定 `AS dbo.OrderIds`。例如，以下代码根据此类型声明了一个名为 `@T` 的表变量，填充了几行数据并进行了查询：

```sql
DECLARE @T dbo.OrderIds;
INSERT INTO @T(pos,orderid) VALUES(1, 10248),(2, 10250),(3, 10249);
SELECT * FROM @T;
```

这种可重用性非常棒。该功能的真正威力在于你可以根据表类型在存储过程和用户定义函数中定义表值参数。但注意，SQL Server 2014 的 TVP 是只读的，必须标记为 `READONLY` 属性。你不允许在存储过程中对 TVP 执行修改。

要查看使用 TVP 的示例，请运行以下代码创建 `GetOrders` 存储过程：

```sql
IF OBJECT_ID(N'dbo.GetOrders', N'P') IS NOT NULL DROP PROC dbo.GetOrders;
GO
CREATE PROC dbo.GetOrders(@T AS dbo.OrderIds READONLY )
AS

  SELECT O.orderid, O.orderdate, O.custid, O.empid
FROM Sales.Orders AS O
INNER JOIN @T AS K
ON O.orderid = K.orderid
ORDER BY K.pos;
GO
```

该存储过程接受一个表值参数并将其与订单表连接。

## EXECUTE WITH RESULT SETS

你可以使用 `WITH RESULT SETS` 子句来定义存储过程或动态批返回的查询结果集的预期形状。你可以将其视为你与存储过程之间的合同。如果存储过程返回的结果与指定的形状兼容，则存储过程成功运行。如果它返回的结果不兼容，取决于差异之处，存储过程的执行将失败或补偿差异。

该功能非常实用的一个例子是，当你使用一个你不负责维护的存储过程时。你想确保在它返回预期形状时才执行它。如果作者更改了存储过程中的查询，你不希望你的代码执行它。除非差异是你可以认为无关紧要的。

考虑以下 `GetErrorInfo` 存储过程定义：

```sql
IF OBJECT_ID('dbo.GetErrorInfo', N'P') IS NOT NULL DROP PROC dbo.GetErrorInfo;
GO
CREATE PROC dbo.GetErrorInfo(@orderid INT)
AS
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
WHERE orderid = @orderid;

SELECT orderid, productid, qty, unitprice
FROM Sales.OrderDetails
WHERE orderid = @orderid;
```

该存储过程接受订单 ID 作为输入并执行两个查询：一个返回输入订单的头，另一个返回相关的订单行。以下是如何执行存储过程并添加 `WITH RESULT SETS` 子句以定义查询结果集的预期形状：

```sql
EXEC dbo.GetErrorInfo @orderid = 10248
WITH RESULT SETS
(
    (
        orderid INT NOT NULL,
        orderdate DATE NOT NULL,
        custid INT NOT NULL,
        empid INT NULL
    )
);
```



```sql
(orderid INT NOT NULL,
productid INT NOT NULL,
qty SMALLINT NOT NULL,
unitprice NUMERIC(19, 3) NOT NULL
);
```

在这种情况下，指定的形状与返回的形状匹配，因此存储过程执行成功。

如果你想应用一些美观上的更改，例如为列分配自定义名称、更改类型（假设值是可以转换的）或更改 NULL 允许性（假设是可行的），你可以使用 `WITH RESULT SET` 子句来实现。例如，以下执行操作将两个结果集中的 `orderid` 列的名称都更改为 `id`：

```sql
EXEC dbo.GetOrderInfo @orderid = 10248
WITH RESULT SETS
(
id INT NOT NULL,
orderdate DATE NOT NULL,
custid INT NOT NULL,
empid INT NULL
),
(
id INT NOT NULL,
productid INT NOT NULL,
qty SMALLINT NOT NULL,
unitprice NUMERIC(19, 3) NOT NULL
);
```

此执行生成了以下输出：

| id | orderdate | custid | empid |
|---|---|---|---|
| 10248 | 2013-07-04 | 85 | S |

| id | productid | qty | unitprice |
|---|---|---|---|
| 10248 | 11 | 12 | 14.000 |
| 10248 | 42 | 10 | 9.800 |
| 10248 | 72 | 5 | 34.800 |

这类似于分配别名。如果你更改了列的类型，SQL Server 将尝试转换这些值。如果任何一个值无法转换，执行将在运行时报错并停止。同样，如果你将列的 NULL 允许性从 `NULL` 更改为 `NOT NULL`，SQL Server 将在运行时检查值，如果发现 `NULL`，它将停止执行并生成错误。当你不允许更改存储过程的定义时，作为代码执行的一部分应用此类更改的能力是非常实用的。

如果列数存在差异，尝试执行存储过程将立即失败。例如，运行以下代码，表示你期望在第一个查询结果集中有三列：

```sql
EXEC dbo.GetOrderInfo @orderid = 10248
WITH RESULT SETS
(
  orderid INT NOT NULL,
  orderdate DATE NOT NULL,
  custid INT NOT NULL
),
(
  orderid INT NOT NULL,
  productid INT NOT NULL,
  qty SMALLINT NOT NULL,
  unitprice NUMERIC(19,3) NOT NULL
)
);
```

你将得到以下错误，表示你在第一个结果集中期望三列但得到了四列：

Msg 11537, Level 16, State 1, ProcedureGetInfo, Line 1175

EXECUTE statement failed because its RESULT SETS clause specified 3 column(s) for result number 1, but the statement sent 4 column(s) at run time.

完成测试后，运行以下代码进行清理：

```sql
IF OBJECT_ID('N''dbo.GetOrderInfo', N'P') IS NOT NULL DROP proc dbo.GetOrderInfo;
```

## 触发器

触发器是一种特殊的存储过程。它是你附加到事件上的例程，当事件发生时，SQL Server 会执行触发器的代码。本节首先介绍 SQL Server 支持的不同类型的触发器，然后继续对高效触发器编程进行讨论。

### 触发器类型和用途

SQL Server 支持不同类型的触发器，包括 `AFTER DML` 触发器、`INSTEAD OF DML` 触发器和 `AFTER DDL` 触发器。

### AFTER DML 触发器

`AFTER DML` 触发器附加到表上的 `INSERT`、`UPDATE` 和 `DELETE` 操作。SQL Server 不支持视图上的 `AFTER DML` 触发器。当用户对表提交操作时，触发器代码会在操作更改表后、在事务提交前执行。如果你在触发器中发出了 `ROLLBACK TRAN` 命令，将回滚触发器内执行的所有工作以及导致触发器触发的事务中执行的所有工作。

SQL Server 中的 DML 触发器是语句级触发器，而不是行级触发器。这意味着无论影响了多少行（即使为零），每个语句都会触发一次。在触发器内部，你可以访问名为 `inserted` 和 `deleted` 的表，它们保存了被修改行的修改前和修改后的状态。在 `INSERT` 触发器中，只有插入的行。在 `UPDATE` 触发器中，`deleted` 保存了更新行的修改前状态，`inserted` 保存了它们的修改后状态。没有 `MERGE` 触发器。你可以定义 `INSERT`、`UPDATE` 和 `DELETE` 来处理 `MERGE` 语句提交的相应操作。

`AFTER DML` 触发器的典型用途包括审计、维护反规范化数据以及跟踪行的最后修改日期和时间。要查看最后一种用例的演示，首先运行以下代码创建一个名为 `T1` 的表：

```sql
SET NOCOUNT ON;
USE tempdb;
IF OBJECT_ID('dbo.T1', 'U') IS NOT NULL DROP TABLE dbo.T1;

CREATE TABLE dbo.T1
(
    keycol INT NOT NULL IDENTITY
    CONSTRAINT PK_T1 PRIMARY KEY,
    dataco VARCHAR(10) NOT NULL,
    lastmodified DATETIME NOT NULL
    CONSTRAINT DFT_T1_lastmodified DEFAULT(SYSDATETIME())
);
```

你需要创建一个 `AFTER UPDATE` 触发器，写入当前的日期和时间值：

```sql
CREATE TRIGGER trg_update ON T1 AFTER UPDATE
AS
BEGIN
    UPDATE T1 SET lastmodified = SYSDATETIME()
    FROM T1 INNER JOIN inserted i ON T1.keycol = i.keycol
END
```

*(注：此处根据上下文逻辑补全了缺失的触发器代码，原文在此处截断或未提供完整代码，但逻辑为更新 lastmodified 列)*

你可以使用 `COL_UPDATED()` 函数来检查列是否被更新。前者接受一个列名并根据是否被更新返回布尔值，后者则返回一个位图。这在需要检查大量列时非常有用。

### DDL 后触发器

SQL Server 支持 DDL 触发器。根据相关事件的范围，你可以创建数据库级触发器或服务器级触发器。例如，`CREATE_TABLE` 事件显然是一个数据库范围内的事件，而 `CREATE_DATABASE` 事件则是一个服务器范围内的事件。

你可以将 DDL 触发器绑定到单个事件（如 `CREATE_TABLE` 和 `ALTER_TABLE`），也可以绑定到事件组（如 `DDL_TABLE_EVENTS` 针对 `CREATE_TABLE`、`ALTER_TABLE` 和 `DROP TABLE` 以及 `DDL_DATABASE_EVENTS` 针对所有数据库级别的事件）。你可以在此处找到 DDL 触发器支持的事件和组：http://msn.microsoft.com/en-us/library/bb510452.aspx。

DDL 触发器的典型用场景包括审核 DDL 更改、强制策略以及更改管理。

在 DML 触发器中，你通过 `inserted` 和 `deleted` 表访问与事件相关的数据。在 DDL 触发器中，微软做了一个有趣的选择，通过一个名为 `EVENTDATA` 的函数以 XML 格式暴露事件信息。这些信息包含了提交更改的人员登录信息、发布时间、受影响的对象以及 T-SQL 语句。你可能猜到了，不同的事件会有不同的关联事件。使用 XML 允许微软提供一种简单且灵活的解决方案，能够轻松适应这些差异。你需要使用 XML 类型的 `value()` 方法从函数获取的 XML 实例中提取信息。

我将演示如何使用 DDL 触发器审核提交给 `testdb` 数据库的所有 DDL 更改。运行以下代码创建创建数据库：

```sql
USE master;
IF DB_ID('testdb') IS NOT NULL DROP DATABASE testdb;
CREATE DATABASE testdb;
GO
USE testdb;
```

运行以下代码创建 `AuditDDLEvents` 表，触发器将从中存储事件信息：

```sql
IF OBJECT_ID(N'dbo.AuditDDLEvents', N'U') IS NOT NULL
DROP TABLE dbo.AuditDDLEvents;

CREATE TABLE dbo.AuditDDLEvents
(
auditlsn          INT NOT NULL,
posttime         DATETIME NOT NULL,
eventype         sysname NOT NULL,
loglogin         sysname NOT NULL,
schemaname       sysname NOT NULL,
objectname       sysname NOT NULL,
targetobjectname sysname NOT NULL,
eventdata         XML NOT NULL,
                 CONSTRAINT PK_AuditDDLEvents PRIMARY KEY (auditlsn)
);
```

最后，使用以下代码创建审核触发器：

```sql
CREATE TRIGGER trg_audit_ddl_events ON DATABASE FOR DDL_DATABASE_LEVEL_EVENTS
AS
SET NOCOUNT ON;

DECLARE @eventdata AS XML = eventdata();

INSERT INTO dbo.AuditDDLEvents (
postime, eventtype, loginname, schemaname, objectname, targetobjectmaname, eventdata)
VALUES (@eventdata.value('(/EVENT_INSTANCE/PostTime)[1]', 'VARCHAR(23)'),
@eventdata.value('(/EVENT_INSTANCE/EventType)[1]', 'sysname'),
@eventdata.value('(/EVENT_INSTANCE/LoginName)[1]', 'sysname'),
@eventdata.value('(/EVENT_INSTANCE/SchemaName)[1]', 'sysname'),
@eventdata.value('(/EVENT_INSTANCE/ObjectName)[1]', 'sysname'),
@eventdata.value('(/EVENT_INSTANCE/TargetObjectName)[1]', 'sysname'),
@eventdata);
```

观察到第一行将函数返回的 XML 实例存储在变量中。然后触发器向审核表中插入一行。`VALUES` 子句中包含了对 `value()` 方法的调用，用于提取你想以关系形式存储在单独立列中的值。此外，`VALUES` 子句还包含带有目标 XML `eventdata` 完整信息的 XML 变量，以防某些事件需要你未存储在单独列中的某些信息。

运行以下 DDL 语句来测试触发器：

```sql
CREATE TABLE dbo.T1(col1 INT NOT NULL PRIMARY KEY);
ALTER TABLE dbo.T1 ADD col2 INT NULL;
ALTER TABLE dbo.T1 ALTER COLUMN col2 INT NOT NULL;
CREATE NONCLUSTERED index idx1 ON dbo.T1(col2);
```

运行以下代码查询审核表：

```sql
SELECT * FROM dbo.AuditDDLEvents;
```

当我在系统上运行查询时，我得到了以下输出（此处以简略形式显示 XML）：

| postime | eventtype | loginname |
|---|---|---|
| 1 | 2015-02-12 15:23:29.627 | CREATE_TABLE | K2\Gandalf |
| 2 | 2015-02-12 15:23:29.713 | ALTER_TABLE | K2\Gandalf |
| 3 | 2015-02-12 15:23:29.720 | ALTER_TABLE | K2\Gandalf |
| 4 | 2015-02-12 15:23:29.723 | CREATE_INDEX | K2\Gandalf |

| schemaname | objectname | targetobjectname | eventdata |
|---|---|---|---|
| 1 | dbo | T1 | NULL | <EVENT_INSTANCE>... |
| 2 | dbo | T1 | NULL | <EVENT_INSTANCE>... |
| 3 | dbo | T1 | NULL | <EVENT_INSTANCE>... |
| 4 | dbo | T1 | NULL | <EVENT_INSTANCE>... |

```sql
FETCH NEXT FROM @C INTO @keycol, @datacol;
END;
```

```sql
END;
GO
```

对于每插入的一行，触发器都会打印一条包含该行元素的消息。通常情况下，你将根据触发器预期执行的任务对这些元素进行某些操作。

运行以下代码以测试受影响行数为零的触发器：

```sql
INSERT INTO dbo.T1(datacol) SELECT 'A' WHERE 1 = 0;
```

触发器直接返回，未执行任何操作。

运行以下代码以测试受影响行数为一的触发器：

```sql
INSERT INTO dbo.T1(datacol) VALUES('A');
```

触发器使用赋值 `SELECT` 语句处理该行，并生成以下输出：

Handling keycol: 1, datacol: A

运行以下代码以测试受影响行数多行的触发器：

```sql
INSERT INTO dbo.T1(datacol) VALUES('B'), ('C'), ('D');
```

触发器使用游标处理这些行并生成以下输出：

Handling keycol: 4, datacol: D

Handling keycol: 3, datacol: C

Handling keycol: 2, datacol: B

完成后，运行以下代码进行清理：

```sql
IF OBJECT_ID('N''dbo.T1', 'U') IS NOT NULL DROP TABLE dbo.T1;
```

另一个需要考虑的效率问题是如何对在表中插入或更新的数据强制执行完整性规则。通常情况下，如果你可以通过约束强制执行规则，那么其性能往往会比触发器更好。这是因为约束在更改发生之前就拒绝了该更改。然而，在某些情况下，约束无法实现你所需。例如，如果你需要在位于不同数据库的表之间强制执行引用完整性，则无法使用外键约束。在这种情况下，可以使用触发器。我想表达的观点是：确保你应该首先考虑约束，只有在无法通过约束实现完整性强制时，才诉诸触发器。

你可能会遇到这样的情况：你需要应用某种修改，但不想让某个触发器触发。也许触发器会对新数据进行某些进一步处理，但你准备插入的数据已经经过处理了。你不想使用 `ALTER TABLE DISABLE` 命令来禁用触发器，因为该命令会全局禁用它。你只想防止它在你即将发出的特定语句中触发。

人们用于此类目的的工具之一是会话上下文。它是与你的会话关联的 `BINARY(128)` 值。你可以在调用堆栈的任何一点对其进行修改和查询。你使用 `SET CONTEXT_INFO` 命令重写该值，并使用 `CONTEXT_INFO` 函数查询它。为了防止触发器运行常规代码，你可以在发布修改操作之前在会话文中植入一个信号。你在触发器中添加逻辑，查询会话上下文，如果发现信号已设置，则返回。否则，触发器将继续运行其原始代码。这听起来是一个很好的解决方案，但如果你尝试过处理会话上下文，就会知道它可能非常笨拙。每个会话只有一个值。如果不同的开发者使用它，你就需要协调每个开发者将使用该值的哪一个部分。然后，为了写入你的那部分值，你需要查询当前值，合并你想要添加的部分，然后将其写回。可以确定，这种策略存在巨大的问题风险。

我喜欢的解决方案更简单，且出错的可能性较小。它使用一个空临时表作为信号机制。你在调用堆栈某一层创建的本地临时表在这一层以及调用堆栈的所有内部层都是可见的。这意味着如果你在发布语句之前创建临时表，它就位于该语句触发的触发器内部。此外，如果你创建了临时表但没有插入任何行，则不会发生页面分配，使其成为用于此类目的的廉价工具。因此，作为你的信号机制，在发布修改之前创建一个特定名称的临时表，并在修改后将其删除。让触发器检查是否存在该名称的临时表，如果存在，则返回；否则正常继续。

为了展示该策略的演示，首先运行以下代码创建一个名为 T1 的表：



```sql
IF OBJECT_ID('dbo.T1','U') IS NOT NULL DROP TABLE dbo.T1;
CREATE TABLE dbo.T1(col1 INT);
```

然后在该表上创建以下触发器：

```sql
CREATE TRIGGER trg_T1_i ON dbo.T1 AFTER INSERT
AS

IF OBJECT_ID('tempdb..#do_not_fire_trg_T1_i','U') IS NOT NULL RETURN;

PRINT 'trg_T1_i in action...';
GO
```

`PRINT` 语句代表你触发器中的常规代码。我用它来显示常规代码何时被运行。`IF` 语句是信号机制的补充，如果存在名为 `#do_not_fire_trg_T1_i` 的临时表，则返回。注意，表名带有 `tempdb` 数据库的限定符。如果没有这个限定符，`OBJECT_ID` 函数将在当前数据库中查找它，这通常是一个用户数据库。

为了确保在不创建信号时触发器继续照常运行，运行以下代码向 T1 插入新行：

```sql
INSERT INTO dbo.T1(col) VALUES(1);
```

临时表不存在，因此触发器继续运行常规代码。触发器生成以下输出：

trg_T1_i in action...

假设你想插入新行，但这次你不想让触发器运行其常规代码。你创建一个 `#do_not_fire_trg_T1_i` 临时表，发布 `INSERT` 语句，然后删除临时表，如下：

```sql
-- 设置信号
CREATE TABLE #do_not_fire_trg_T1_i(col INT);
INSERT INTO T1(col) VALUES(2);
-- 清除信号
DROP TABLE #do_not_fire_trg_T1_i;
```

这一次触发器执行时发现临时表确实存在，因此没有运行其常规代码。

# SQLCLR 编程

尽管 T-SQL 无疑是 SQL Server 的顶级编程语言，但在面对某些类型的问题时，有时可能会很困难。复杂的算法、排序计算以及与其他系统的互操作性是 T-SQL 并不总是最佳挑战。从 SQL Server 2005 开始，开发者获得了一个新选项：集成运行时 SQLCLR。不要误会，SQLCLR 基于 .NET Framework，并且显然不是一个独立的语言。然而，可以使用它来增强 T-SQL 并带来巨大的灵活性。

你可能会遇到需要应用修改但不想让某个触发器触发的情况。也许触发器会对新数据进行某些进一步处理，但你即将插入的数据已经经过处理。你不想使用 `ALTER TABLE DISABLE` 命令来禁用触发器，因为该命令会全局禁用它。你只想防止它在你即将发出的特定语句中触发。

人们用于此类目的的工具之一是会话上下文。它是与你的会话关联的 `BINARY(128)` 值。你可以在调用堆栈的任何一点对其进行修改和查询。你使用 `SET CONTEXT_INFO` 命令重写该值，并使用 `CONTEXT_INFO` 函数查询它。为了防止触发器运行常规代码，你可以在发布修改操作之前在会话文中植入一个信号。你在触发器中添加逻辑，查询会话上下文，如果发现信号已设置，则返回。否则，触发器将继续运行其原始代码。这听起来是一个很好的解决方案，但如果你尝试过处理会话上下文，就会知道它可能非常笨拙。每个会话只有一个值。如果不同的开发者使用它，你就需要协调每个开发者将使用该值的哪一个部分。然后，为了写入你的那部分值，你需要查询当前值，合并你想要添加的部分，然后将其写回。可以确定，这种策略存在巨大的问题风险。

我喜欢的解决方案更简单，且出错的可能性较小。它使用一个空临时表作为信号机制。你在调用堆栈某一层创建的本地临时表在这一层以及调用堆栈的所有内部层都是可见的。这意味着如果你在发布语句之前创建临时表，它就位于该语句触发的触发器内部。此外，如果你创建了临时表但没有插入任何行，则不会发生页面分配，使其成为用于此类目的的廉价工具。因此，作为你的信号机制，在发布修改之前创建一个特定名称的临时表，并在修改后将其删除。让触发器检查是否存在该名称的临时表，如果存在，则返回；否则正常继续。

为了展示该策略的演示，首先运行以下代码创建一个名为 T1 的表：

```sql
IF OBJECT_ID('dbo.T1','U') IS NOT NULL DROP TABLE dbo.T1;
CREATE TABLE dbo.T1(col1 INT);
```

然后在该表上创建以下触发器：

```sql
CREATE TRIGGER trg_T1_i ON dbo.T1 AFTER INSERT
AS

IF OBJECT_ID('tempdb..#do_not_fire_trg_T1_i','U') IS NOT NULL RETURN;

PRINT 'trg_T1_i in action...';
GO
```

`PRINT` 语句代表你触发器中的常规代码。我用它来显示常规代码何时被运行。`IF` 语句是信号机制的补充，如果存在名为 `#do_not_fire_trg_T1_i` 的临时表，则返回。注意，表名带有 `tempdb` 数据库的限定符。如果没有这个限定符，`OBJECT_ID` 函数将在当前数据库中查找它，这通常是一个用户数据库。

为了确保在不创建信号时触发器继续照常运行，运行以下代码向 T1 插入新行：

```sql
INSERT INTO dbo.T1(col) VALUES(1);
```

临时表不存在，因此触发器继续运行常规代码。触发器生成以下输出：

trg_T1_i in action...

假设你想插入新行，但这次你不想让触发器运行其常规代码。你创建一个 `#do_not_fire_trg_T1_i` 临时表，发布 `INSERT` 语句，然后删除临时表，如下：

```sql
-- 设置信号
CREATE TABLE #do_not_fire_trg_T1_i(col INT);
INSERT INTO T1(col) VALUES(2);
-- 清除信号
DROP TABLE #do_not_fire_trg_T1_i;
```

这一次触发器执行时发现临时表确实存在，因此没有运行其常规代码。

## SQLCLR 架构

尽管 T-SQL 无疑是 SQL Server 的顶级编程语言，但在面对某些类型的问题时，有时可能会很困难。复杂的算法、排序计算以及与其他系统的互操作性是 T-SQL 并不总是最佳挑战。从 SQL Server 2005 开始，开发者获得了一个新选项：集成运行时 SQLCLR。不要误会，SQLCLR 基于 .NET Framework，并且显然不是一个独立的语言。然而，可以使用它来增强 T-SQL 并带来巨大的灵活性。

SQL Server，其核心，是旨在作为企业级数据存储的（注：此处原文逻辑可能有重复或遗漏，此处意译为旨在作为企业级数据存储）。“企业级”一词对不同的人有不同的含义，但其核心思想是可扩展性和可用性。系统必须能够增长以服务最大的公司和应用程序，并且系统必须提供机制以确保在请求时做出响应。

作为一个纯粹的开发平台而不是数据库本身，.NET Framework 对上述任何一点都不特别关注。因此，在将其引入 SQL Server 生态系统时，采取了特别措施以确保运行时能够适应严格的环境，且不会降低 SQL Server 能力。

## 进程内托管模型

SQL Server 通过进程内运行时利用 .NET。这意味着运行时与 SQL Server 内部运行的所有内容共享内存和线程空间。这一关键设计决策有一些优缺点：

- 将数据移动到 .NET 程序或移动到 T-SQL 计算开销很小，因为数据不需要跨进程边界。
- 托管 .NET 代码的资源使用可能会直接干扰 SQL Server 其他元素的资源使用，由于共享资源的原因。
- 运行时确保授予 SQL Server 进程的安全权限，无需额外的管理工作。
- SQL 操作系统管理组件 (SQLOS) 能够完全访问运行时，不需要特殊权限或跨进程边界。

最后一点最重要的，也是进程内模型的关键。SQLCLR 托管在 SQL Server 内部，但它也是一个真正的 SQL 组件，与 SQLOS 完全集成。与所有其他 SQL Server 组件一样，SQLCLR 从 SQLOS 接收内存分配和 CPU 时间，SQLOS 可以根据需要保留或重新分配这些资源，以保持 SQL Server 系统的平衡和响应。

除了控制资源外，SQLOS 还负责对托管运行时进行顶层监控，以确保资源过度分配或过度使用不会威胁 SQL 实例的可用性。运行时面临内存泄漏和调度器独占问题，SQLOS 能够动态卸载 AppDomain（在内存泄漏的情况下）或强制不让的线程从繁忙的调度器中退让，给其他查询提供运行机会（这被称为量子惩罚）。

> **重要提示**：在开始运行自定义 SQLCLR 代码之前，你必须首先在实例级别启用该功能。操作方法是首先运行 `EXEC sp_config 'clr enabled', 1`，然后使用 `REFIGURE` 语句提交更改。使用内置的 SQLCLR 功能（如 `HIERARCHYID` 和地理数据类型）不需要重新配置。

## 托管在数据库中的程序集

尽管运行时本身由 SQL Server 级别进行全局（且自动）管理，但 .NET 程序集——即封装我们自定义 SQLCLR 程序的程序的模块——在单个数据库内部都进行管理和安全保护。在数据库级别，每个程序集通过三个可能的存储桶（buckets）之一获得一组权限。此外，AppDomains 由运行时在全局范围内动态管理和范围化，而不是在托管程序集的每个数据库内部进行管理。

.NET 程序集是编译后的 DLL 或 EXE 文件，应用程序通常依赖于这些编译文件的物理副本，或者是加载到全局程序集缓存 (GAC) 中的版本。另一方面，SQL Server 遵循的是不同的模型。当 SQL Server 数据库需要某个程序集时，它首先通过 `CREATE ASSEMBLY` 语句将其加载到数据库中。该语句会读取 DLL 并复制到数据库中。从现在起，任何 SQL Server 都不再使用或访问该物理文件。这消除了管理开销；因为程序集实际上是数据库的一部分，它会随数据库移动到任何地方——包括复制、备份、日志传送、可用性副本等。

使用 `CREATE ASSEMBLY` 语句将程序集引入 SQL Server 的关键因素之一是 `PERMISSION_SET`。此选项限制了程序集的操作，为数据库管理员 (DBA) 或数据库开发人员提供了一种保障，即即使程序集包含恶意（或仅仅是有 Bug 的）代码，它也无法超出某些限制。共有三种可用的权限集：

- **SAFE**（安全）：此权限的限制性最大，程序集可以使用 .NET Framework 类，包括用于数学运算和字符串操作的类。此外，允许程序集使用一种特殊的 ADO.NET 连接类型（即上下文连接）连接到托管数据库。
- **EXTERNAL ACCESS**（外部访问）：此权限集包含了除 `SAFE` 权限集之外的所有内容，外加上访问托管数据库外部资源的能力。例如，在此权限集中，程序集可以访问同一服务器上的另一个数据库、另一个服务器上的另一个数据库，或者网络上某处的文件。
- **UNSAFE**（不安全）：此权限集包含了除 `EXTERNAL` 权限集之外的所有内容，外加上执行可能导致 SQL Server 实例不稳定的操作的能力。包括线程、同步以及通过代码关闭 SQL Server 的能力。

这三种权限通过两种不同类型的检查来实现。当程序集被即时编译 (JITed) 时，会针对 `HostProtection` 属性进行检查。各种 .NET Framework 类和方法都修饰了此属性，在权限不足的程序集中引用它们将导致在 JIT 过程中抛出异常。另一方面，安全限制是在运行时执行的：即 .NET 的代码安全 (CAS) 接口。通常，授予安全权限是限制 CAS 的执行，而授予 `UNSAFE` 集合则允许执行可能影响可靠性的代码，而这种执行是由 `HostProtection` 检查强制实施的。

在创建程序集时指定的另一个选项是 `AUTHORIZATION`（授权），或指定程序集的所有者。从基本的数据库安全——能够 `ALTER` 或 `DROP` 程序集的能力——来看，所有者对程序集的处理方式具有重要影响。具体来说，给定数据库中由同一个数据库主体所有的所有程序集将加载到同一个 AppDomain 中。这种分离使得每个程序集都拥有自己的内存沙箱，与其他程序集集隔离。

这种设计的主要用处是允许 SQLOS 选择性地启动和销毁 AppDomains，而不影响系统的其他部分。例如，如果你的数据库有两个程序集函数，分别由不同的主体所有，且 SQL Server 检测到你的其中一个程序集具有内存泄漏的代码，那么只有受影响的那个需要回收。另一个 AppDomain 的用户不会受到任何影响。这种设计还意味着，如果你有两个或多个应该相互密切交互的程序集，它们必须由同一个主体所有。开发者应该在考虑这些因素时仔细设计程序集的所有权。

## CLR 标量函数和创建第一个程序集

可以创建多种类型的 SQLCLR 对象和程序，但最简单且流行的类型是标量用户定义函数 (UDF)。标量函数有助于封装复杂的逻辑或操作；数学算法、字符串处理逻辑甚至数据压缩都是 CLR 标量函数的常见用例。

与 T-SQL 标量函数相比，CLR 版本始终会产生更好的性能和更简单的查询计划。这是因为 CLR 函数是编译并封装的代码，它们在查询计划的 `Compute Scalar` 算符中引用，就像任何内置函数一样。图 9-22 显示返回空字符串的简单 CLR 标量函数的查询计划。

```
Query 1: Query cost (relative to the batch): 100%
SELECT dbo.SqlFunction1()
```

![](img/bdc38aa36f6e2987d913ee5381474711_612_0.png)

图 9-22 CLR 标量函数的查询计划。

另一方面，T-SQL 标量函数被视为特殊的存储过程，在每次迭代中都会在逻辑和物理上被访问和重新评估。图 9-23 显示了与 CLR UDF 逻辑相同的 T-SQL 标量 UDF（简单返回空字符串）的查询计划。T-SQL 版本实际上产生了两个查询计划：一个用于 `SELECT` 的外部计划，另一个用于逐行调用 UDF 的内部计划。这就是性能问题出现的地方。

```
Query 1: Query cost (relative to the batch): 100%
SELECT dbo.SqlFunction1()
```

![](img/bdc38aa36f6e2987d913ee5381474711_613_0.png)

```
Query 2: Query cost (relative to the batch): 0%
[t_sql_querying].[dbo].[SqlFunction]
```

![](img/bdc38aa36f6e2987d913ee5381474711_613_1.png)

图 9-23 T-SQL 函数查询计划；注意额外的第二个计划。

CLR 函数的关键之处在于，对于终端用户来说，它们看起来和用起来完全完全一样，因此，如果你有一个在 T-SQL 函数中性能不佳的算法，可以迁移到 CLR 函数而无需更改任何下游代码。同样，如果你认为 CLR 函数作为 T-SQL 函数效果更好，也可以迁移回来。这种灵活性是使 SQLCLR 成为性能调优强大工具的原因之一。

## Visual Studio 和 SQL Server Data Tools

在创建程序集之前，你需要决定一个工作环境。虽然你可以使用任何文本编辑器创建 C# 代码并使用 `cexe`（C 编译器）进行编译，但大多数开发者更倾向于使用集成开发环境 (IDE)。通常的选择是 Microsoft Visual Studio，它包含一个名为 SQL Server Data Tools (SSDT) 的 SQL Server 插件。该插件旨在解决全生命周期数据库开发中的许多痛点，包括有助于重构、部署和调试的各种功能。它还包含了有助于创建 SQLCLR 程序集的特定功能。

## SSDT 项目和创建 CLR 函数

Visual Studio 中的 SSDT 项目嵌套在 SQL Server 模板类别下。一旦你创建了工作项目，就可以可以在解决方案管理器 (Solution Explorer) 中右键点击项目，选择“添加 (Add)”，并点击“新建项 (New Item)”来添加用户定义函数。这将弹出一个带有各种项目类型的对话框。SQLCLR C# 类别包含了创建新项的正确模板。

SQLCLR 对象。选择 SQLCLR C# User Defined Function（用户定义函数）类别将弹出一个如列表 9-1 所示的通用函数定义。

**列表 9-1** 用户定义函数的通用模板

```csharp
public partial class UserDefinedFunctions
{
    [Microsoft.SqlServer.Server.SqlFunction]
    public static SqlString SqlFunction1()
    {
        // 在此处放置你的代码
        return new SqlString(string.Empty);
    }
}
```

关于这段代码需要注意的最重要的一点是它实现了一个完整且可运行的用户定义函数。事实上，SQLCLR 标量 UDF（用户定义函数）只是一个标量方法，通过 `CREATE FUNCTION` 语句 T-SQL 暴露。（在这种情况下，装饰方法的 `SqlFunction` 属性用于告诉 Visual Studio 代表你执行此工作。该属性是完全可选的。）没错；无论你决定在花括号之间放置什么类型的逻辑、算法或 .NET Framework 功能，都是允许的。

![](img/bdc38aa36f6e2987d913ee5381474711_614_0.png)



> 注意：虽然 `SqlFunction` 属性用于标量函数，但它确实拥有重要的选项。如果你想在函数上创建索引（例如通过在计算列中使用该函数），你必须使用并将 `IsDeterministic` 属性设置为 `true`。这是一个罕见的情况，因此在此不再介绍。有关更多信息，请参阅微软开发者网络（http://msdn.microsoft.com）上的 `SqlFunctionAttribute` 文档。

## SqlTypes 命名空间

你可能已经注意到列表 9-1 中的代码，它没有返回标准的 .NET `System.Data.SqlTypes`，而是返回 `SqlString` 类型。该类型与其他几个类型一起位于 `System.Data.SqlTypes` 命名空间中。每个类型都映射一个 SQL Server 内置类型，并实现了 `NULL` 行为（通过一个名为 `Nullable` 的接口）以及与基础 SQL Server 类型类似的行为。

这些行为包括了涵盖 SQL Server 数据规则的值范围，以及模拟 SQL Server 行为的操作。例如，在 .NET 默认情况下，对值为 `2147483647` 的整数变量加 1，结果将变为 `-2147483648`。而在 SQL Server 中，此操作会导致算术溢出异常。`SqlInt32` 类型——设计用于镜像 SQL Server 的 `INTEGER` 类型的行为——在尝试执行此操作时也会抛出异常。

SQLCLR 方法并不要求使用 `SqlTypes` 数据。SQL Server 可以在内部映射相似的类型，例如将 `System.String` 映射到 `NVARCHAR`。然而，强烈建议在方法的输入和输出中使用 `SqlTypes`，因为它保证了适当的行为和能力，并确保你的 CLR 模块以 T-SQL 消费者期望的方式做出响应——无论他们是否知道自己处理的是 CLR 模块而不是 T-SQL 模块。

## 发布程序集

添加函数后，程序集就可以准备好“发布”（部署）到目标数据库了。在发布实际程序集之前，你可能想先访问项目属性——特别是 SQLCLR 部分——并根据喜好配置 `Permission Level`（权限级别）和 `Assembly Owner`（程序集所有者）选项。鉴于此示例的简单性，这可能不是必要的。

要进行发布，在解决方案管理器中右键点击项目并点击“发布”。你需要首先指定一个目标数据库。如果该数据库包含你关心的其他对象，你可能想访问“高级”选项对话框，并确保清除任何可能覆盖你之前工作的选项。一旦配置完成这些，建议保存你的设置（通过点击“保存配置文件”），因为 SSDT 不会为后续发布自动记住这些设置。

点击“发布”按钮将函数部署到数据库。在底层，这是通过一系列 T-SQL 脚本完成的，开头类似于如下所示：

```sql
CREATE ASSEMBLY [t_sql_querying_project]
AUTHORIZATION [dbo]
FROM 0X4D5A9000030000000FFFF0008000000 ... (为了简洁已截断)
```

此代码使用 `CREATE ASSEMBLY` 语句将程序集加载到目标数据库。`FROM` 子句支持编译的动态链接库（DLL）的文件路径。在这种情况下，Visual Studio 编译 DLL（你可以在生成的文件夹中找到它），读取字节并以这种形式表示它们，以便更方便地编写脚本并部署到远程位置，而无需担心网络权限。`AUTHORIZATION` 子句将程序集所有者设置为 `dbo`。此语句缺少 `WITH PERMISSION_SET` 子句，这意味着将使用默认的 `SAFE` 权限集。

此时，程序集已加载到数据库中，但标量函数还无法通过 T-SQL 调用。在此发生之前，必须创建一个指向内部方法的 T-SQL 存根函数。SSDT 发布通过类似这样的脚本执行此操作：

```sql
CREATE FUNCTION [dbo].[SqlFunction]
()
RETURNS NVARCHAR (4000)
AS
EXTERNAL NAME [t_sql_querying_project].[UserDefinedFunctions].[SqlFunction]
```

此 T-SQL 函数与 C# 方法具有相同的输入参数（名称）和相同的输出参数类型。Visual Studio 已自动将 `SqlType` 类型映射到 `NVARCHAR(4000)`。（记住 .NET 字符串始终是 Unicode 的）。除此之外，还有-

```cs
public partial class UserDefinedFunctions
{
    [Microsoft.SqlServer.Server.SqlFunction]
    public static SqlInt32 ReturnLength1(
        SqlString string)
    {
        return new SqlInt32(string.Value.Length);
    }
}
```

此函数阐明了关于 `SqlTypes` 的一个重要点：命名空间中的每种数据类型都实现了一个名为 `Value` 的属性，该属性映射回 .NET 类型。在 C# 代码中，使用该属性是处理该类型的推荐方法，而不是使用静态强制转换。

一旦发布了函数，就可以与内置的 `LEN` 函数进行对比测试：

```sql
DECLARE @bigString NVARCHAR(MAX) = REPLICATE(CONVERT(NVARCHAR(MAX), 'a'), 12345);

SELECT
LEN(@bigString) AS SQL_Length,
dbo.ReturnLength1(@bigString) AS CLR_Length;
```

| Sql_Length | CLR_Length |
|---|---|
| 12345 | 4000 |

(1 row(s) affected)

再次，可以通过使用 `SqlFacet` 属性来缓解该问题——这次将其应用于输入值（因此，没有 "return" 声明）：

```cs
public partial class UserDefinedFunctions
{
    [Microsoft.SqlServer.Server.SqlFunction]
    public static SqlInt32 ReturnLength2(
        [SqlFacet(MaxSize=-1)]
        SqlString string)
    {
        return new SqlInt32(string.Value.Length);
    }
}
```

发布后，之前的脚本现在可以按预期工作了：

```sql
DECLARE @bigString NVARCHAR(MAX) = REPLICATE(CONVERT(NVARCHAR(MAX), 'a'), 12345);

SELECT
LEN(@bigString) AS SQL_Length,
dbo.ReturnLength2(@bigString) AS CLR_Length;
```

| Sql_Length | CLR_Length |
|---|---|
| 12345 | 12345 |

(1 row(s) affected)

主要的 `SqlTypes` 陷阱与 SQL Server 的某些时间数据类型有关。`SqlTypes` 命名空间最初于 2005 年发布，在此期间没有收到更新，尽管它包含一个映射到 `DATETIME` 的 `SqlDateTime` 类型，但它不支持 SQL Server 2008 首次引入的 `DATE`、`TIME`、`DATETIME2` 和 `DATETIMEOFFSET`。在这些情况下，遗憾的是需要手动干预。

Visual Studio 自动映射 `TIME`（`System.TimeSpan`）和 `DATETIMEOFFSET`（`System.DateTimeOffset`），但如果需要对 `NULL` 的支持，你将不得不采用 .NET 的可空类型版本（`System.TimeSpan?` 和 `System.DateTimeOffset?`）。遗憾的是，这些类型虽然完全支持 SQLCLR 程序集，但在本文编写时的 SSDT 所有当前版本中都不支持。

`DATE` 和 `DATETIME2` 类没有对应的 .NET 类，但两者都兼容 `System.DateTime` 且支持 `NULL`。遗憾的是，没有方法让 Visual Studio 使用 `SqlFacet` 编写这些关系的脚本。再次，需要手动步骤。

在这两种情况下，对于标量函数，目前的最佳方法是在函数的 C# 方法定义中省略 `SqlFunction` 属性。这将让 Visual Studio 尝试为函数生成 T-SQL 存根，从而避免脚本错误。你可以创建自己的存根脚本并将其包含在后置的 .SQL 文件中，该文件可以从 User Scripts 类别添加到 SSD 项目。

## 字符串类型与大小写性

在编写 T-SQL 时，大小写性考虑（或缺乏考虑）取决于操作中涉及的字符串的排序规则。排序规则可以从数据库或表的单个列继承，这取决于它们是如何设置的以及你具体在做什么。

在 .NET 中，情况略有不同。默认情况下，对字符串的操作都使用二进制比较——这意味着所有操作都是区分大小写的。可以通过使用 .NET 基础库 (BCL) 中几乎所有字符串方法可用的标记进行逐个更改来启用此行为。然而，在编写 SQLCLR 时，代码选择可能不是一个很好的选项，因为一个程序集可能需要在区分大小写和不区分大小写的上下文中使用，而你可能不想仅通过一个修改的标记来维护两份相同的代码。

解决此问题的方法是利用作为 `SqlString` 类属性暴露的 `SqlCompareOptions` 枚举。该枚举包含关于主机数据库排序规则的信息，可以据此推断 SQLCLR 模块中的字符串比较是否应该使用区分大小写的方式。

访问这些信息为许多用例打开了大门。例如，以下是两个正则表达式函数，它们可以部署到任何 SQL Server 数据库，并自动获取正确的大小写设置。

```csharp
// 主机数据库是否使用区分大小写的排序规则？
var options =
  (0 != (input.SqlCompareOptions & SqlCompareOptions.IgnoreCase))
    ? System.Text.RegularExpressions.RegexOptions.IgnoreCase
    : System.Text.RegularExpressions.RegexOptions.None;
```

```csharp
// 使用选项实例化正则表达式对象
var regEx =
  new System.Text.RegularExpressions.Regex(pattern.Value, options);
```

```csharp
// 我们有匹配吗？
return new SqlBoolean(regEx.IsMatch(input.Value));
```

```csharp
// 主机数据库是否使用区分大小写的排序规则？
var options =
  (0 != (input.SqlCompareOptions & SqlCompareOptions.IgnoreCase))
    ? System.Text.RegularExpressions.RegexOptions.IgnoreCase
    : System.Text.RegularExpressions.RegexOptions.None;
```

```csharp
// 使用选项实例化正则表达式对象
var regEx =
  new System.Text.RegularExpressions.Regex(pattern.Value, options);
```

```csharp
// 我们有匹配吗？
return new SqlBoolean(regEx.IsMatch(input.Value));
```

这些函数说明了各种技术：`SqlFacet` 用于设置，`IsNull` 属性用于检查，而 `SqlCompareOptions` 用于验证。这些最终检查通过二进制操作完成。如果设置了 `IgnoreCase`，则结果为非零。

## SQLCLR 标量函数用例

先前的示例旨在尽可能简单地展示如何工作和开发 SQLCLR 函数。这些用例通常属于以下三类之一（或多类）：

- 与 T-SQL 函数相比，SQLCLR 函数提供了优异的性能。对于复杂算法，SQLCLR 函数相比 T-SQL 获得 1000% 或更多的提升并不罕见。令人惊讶的是，在某些情况下 SQLCLR 函数也能超过内置的 SQL Server 函数。内置 `REPLACE` 函数与一个 SQLCLR 函数的测试表明，对于非常大的字符串（最多 50000 个字符）显示了 700% 的改进。

- 另一个 SQLCLR 标量函数的用例是逻辑太难以用 T-SQL 表示。作为一种数据访问语言，T-SQL 并不是为复杂任务设计的。相反，C# 和 Visual Basic .NET 等语言具有丰富的控制形式、高级类和强大的调试器。

- 最后一个用例是利用 .NET 类库 (BCL)。该库具有许多 SQL Server 无法提供的功能，例如磁盘 I/O、网络操作、数据压缩和高级 XML 处理。

考虑 SQLCLR 的 SQL Server 开发者，必须考虑 SQL Server 中的给定任务是否是好主意。.NET 代码应该始终考虑该任务是否可以卸载到不同的服务器。（记住，从许可角度来看，SQL Server 要贵得多）。

如果逻辑是数据密集型的（而非处理密集型的）、共享（即多个应用程序共享的数据逻辑）、如果逻辑是为了过滤或聚合大量数据并节省网络带宽，或者适用这些场景的组合，在 SQL Server 中执行 SQLCLR 可能是合适的。

## 流式表值函数

与 T-SQL 类似，SQLCLR 函数有两种类型：标量和表值。虽然标量值函数在行为上与其 T-SQL 对应，但 SQLCLR 表值函数（TVFs）与 T-SQL 的内联或多语句版本并不相同。SQLCLR 表值函数虽然在意义上接近 T-SQL 多语句函数，但它们不使用 `tempdb` 存储中间数据。它们基于一种使用 .NET `IEnumerable` 接口的方法，向 SQL Server 逐行发送。

## SQLCLR 表值函数生命周期

表值函数的创建方法与标量函数相同。两者之间的核心区别在于，标量函数返回单个值，而表值函数返回的是一个被强制转换为 `IEnumerable`（可枚举）的值的集合。.NET 中的每个内置集合类型都实现了此接口，你可以通过自定义实现或通过 `yield` 语句在自己的代码中利用它，编译器将代表你生成一个 `IEnumerable` 的实现。

SQLCLR 表值函数包含两个主要部分：返回 `IEnumerable` 值的条目的入口方法，以及一个被称为“填充行方法”的次要方法。当从 SQL Server 调用表值函数时，查询处理器首先调用入口方法。该方法的工作是准备一个代表要发送的行的 `IEnumerable` 实例。一旦查询处理器获取了 `IEnumerable` 实例的引用，它就会创建一个 `IEnumerator`（迭代器）实例并开始执行 `MoveNext`。每当此方法返回 `true` 时，就会将返回的对象传递给“填充行”。第二个方法的作用是将对象（或其属性）映射到输出列，然后这些列将以行的形式被查询处理器消耗。

> `IEnumerable` 接口特意缺乏任何属性来指示在不持有内存中持有引用的情况下，可以从源动态访问多少个元素。例如，如果某些代码逐行读取文件，则内存中只需要保留当前行，连同一个指向文件中下一行的指针即可。这就是为什么 `IEnumerable` 被称为流式接口，这使得它在内存通常非常宝贵的 SQL Server 中变得特别好用。

## 创建 SQLCLR 表值函数

创建表值函数从与标量函数相同的模板开始。然而，必须修改返回类型，因此我们将重新回顾 `SqlFunction` 特性。以下是一个实现对逗号分隔值进行简单拆分的示例要点：

```cs
[Microsoft.SqlServer.Server.SqlFunction(
    TableDefinition = "value NVARCHAR(MAX)",
    FillRowMethodName = "StringSplit_fill")]
public static System.Collections.IEnumerable StringSplit(
    [SqlFacet(MaxSize = -1)]
    SqlChars input)
{
    if (input.IsNull)
        return new string[] { };
    else
        return input.Value.Split(',');
}
```

此方法在内部利用了 `System.String.Split`，它返回一个根据提供的任何分隔符（在本例中为逗号）拆分的字符串集合。（当然，分隔符也可以传递给方法，但为了简单起见，这里是硬编码的。）由于尝试拆分 NULL 字符串没有意义，因此对 `IsNull` 属性进行了检查，该属性在所有 `SqlTypes` 数据类型上都有实现，正是为了这种目的。如果字符串为 NULL，你返回一个空集合，这将导致没有行返回给调用者，这正是人们期望该函数在 T-SQL 中实现时可能的行为。

像标量函数一样，此方法也用 `SqlFunction` 特性装饰，但这次它使用了两个新选项。`TableDefinition` 告诉 Visual Studio 如何编写 T-SQL 存根。在这种情况下，指定了单个输出列，但定义可以包含 TDS 协议支持的任意数量——65535 个，这可能不被推荐。另一个选项是 `FillRowMethodName`，它指定了为枚举器返回的每个元素调用的“填充行”方法的名称。一种常见的约定是将“填充行”方法命名为 `[entry name]_fill`。

下一步是创建“填充行”方法本身，在本例中如下：

```cs
static void StringSplit_fill(
    object o,
    out SqlString value)
{
    value = (string)o;
}
```



“填充行”方法始终是一个返回 `void` 值的静态方法。它的第一个参数必须是 `object` 类型，因为这正是枚举器返回的内容。SQLCLR 目前没有使用泛型迭代器。除此之外，此方法用 `SqlFunction` 特性装饰，但这次它使用了两个新选项。`TableDefinition` 告诉 Visual Studio 如何编写 T-SQL 存根。在这种情况下，指定了单个输出列，但定义可以包含 TDS 协议支持的任意数量——65535 个，这可能不推荐。另一个选项是 `FillRowMethodName`，它指定了为枚举器返回的每个元素调用的“填充行”方法的名称。一种常见的约定是将“填充行”方法命名为 `[entry name]_fill`。

下一步是创建“填充行”方法本身，在本例中将如下：

```csharp
static void StringSplit(
    object o,
    SqlValue value)
{
    value = (string)o;
}
```

# 内存利用与更快速、更可扩展的拆分器

在活动环境中利用 SQLCLR 方案时，至关重要的是记住 SQL Server 内存通常是宝贵的。大多数 DBA 喜欢保留服务器用于中央目的（如缓冲区和过程缓存）的内存，而不是被 CLR 空间的大内存分配占用。

上一节创建的字符串拆分器虽然在功能上是健全，但在最小化内存使用方面表现糟糕。它的行为实际上与理想情况恰相反：使用 `StringSplit` 填充所有可能的子字符串的集合，并在元素返回给调用者之前一直持有该集合。这意味着内存不仅被用于每个子字符串，还用于每个字符串的引用。在拆分大字符串时，这种开销会迅速积累。这些问题并不容易解决。要解决这种情况，你需要停止使用简单且内置的 `StringSplit` 方法，而是要编写自己的字符串拆分算法。以下代码是在几天时间内，在论坛与顶尖 SQL Server 开发人员共同开发的。如果你想查看该线程，请访问 `http://www.sqlserver.com/Forums/Topic695508-338-1.aspx`。

此函数可以像其他表值函数一样被引用，在许多场景下对逗号分隔值（CSV）非常有用。以下是一个用例：

```sql
SELECT
*
FROM dbo.StringSplit('abc,def,ghi');
```

| value |
|---|
| abc |
| def |
| ghi |

（影响 3 行）

```csharp
for (int i = lastPos; i < stringLen; i++)
{
    bool matches = true;

    // 针对单字符分隔符进行优化
    if (isSingleCharDelim != delimiter[0])
    {
        if (theString[i] != delimiter[0])
            matches = false;
    }
    else
    {
        for (byte j = 0; j < delimiterLen; j++)
        {
            if ((i + j) >= stringLen) || (theString[i + j] != delimiter[j]))
            {
                matches = false;
                break;
            }
        }
    }
    if (matches)
    {
        nextPos = i;

        // 处理连续分隔符
        if ((nextPos - lastPos) > 0)
            return true;
        else
        {
            i += (delimiterLen - 1);
            lastPos += delimiterLen;
        }
    }
}
lastPos = nextPos + delimiterLen;
nextPos = stringLen;
if ((nextPos - lastPos) > 0)
    return true;
else
    return false;
}
public void Reset()
{
    lastPos = 0;
    nextPos = delimiterLen * -1;
}
```

```csharp
private int lastPos;
private int nextPos;
private readonly char[] theString;
private readonly char[] delimiter;
private readonly int stringLen;
private readonly byte delimiterChar;
private readonly bool isSingleCharDelim;
```

此代码通过一次查找并流式返回一个子字符串来解决内存问题，而不是一次性完成所有工作。这意味着输入字符串必须保留在内存中，但由于只需要单个引用，因此消耗的内存远少于持有对每个子字符串的引用。此外，此代码中使用的算法实际上比使用 `String.Split` 的算法更快。此字符串分割器性能良好，并将内存利用率降到最低。

# 数据访问与上下文连接

到为止，所有的示例都依赖于调用者通过函数传递传递的数据。然而，表值函数和标量函数——以及 SQLCLR 模块——都可以从托管数据库访问数据，即使该数据被标记为 SAFE。这是通过结合标准的 ADO.NET 访问方法和带有上下文的特殊连接字符串实现的。

上下文连接使运行在 SQLCLR 中的代码能够以与调用者运行的 T-SQL 代码相同的可见性和权限访问数据。这意味着 CLR 代码将能够看到调用者可以看到的相同数据，而不会发生权限提升。可见性包括嵌套作用域级别上可用的任何内容，包括在调用 SQLCLR 过程之前创建的本地临时表。

下面的示例函数从一个具有已知结构的表中选择并返回行：

```csharp
[Microsoft.SqlServer.Server.SqlFunction(DataAccess=DataAccessKind.Read)]
public static IEnumerable GetTempValues()
{
    var conn = new SqlConnection("context connection=true");
    var cmd = new SqlCommand("SELECT col1, col2 FROM #values", conn);
    conn.Open();
    var adapter = new SqlDataAdapter(cmd);
    var dt = new DataTable();
    adapter.Fill(dt);

    return (dt.Rows);
}
```

此函数使用 `SqlConnectionStringBuilder` 创建连接字符串。该连接字符串被传递给 `SqlConnection` 对象，该对象用于调用 `SqlCommand` 以从临时表中查询数据。之后，使用 `SqlDataAdapter` 将查询结果填充到 `DataTable` 中。这些行作为集合的形式返回，该集合自然实现了 `IEnumerable`。除了连接字符串外，所有这些内容都是标准的 ADO.NET，易于迁移到或移出 SQL Server。唯一值得注意的是 `SqlFunction` 特性中指定的 `DataAccess` 选项，为了访问数据必须设置它。

> 注意：`DataAccess` 可用的唯一选项是 `None`（默认值）和 `ReadOnly`。这是一个重要点；与 T-SQL 函数一样，SQLCLR 函数不能产生副作用。这意味着它们的设计初衷是只读取数据，而不修改它。如果你想修改数据，存储过程是推荐的方法。

你可能还需要创建一个“填充（fill）”方法，如下：

```csharp
public static void GetTempValues_fill(
object o,
out SqlInt32 col1,
out SqlDouble col2)
{
    var dr = (DataRow)o;
    col1 = new SqlInt32((int)dr[0]);
    col2 = new SqlDouble((double)dr[1]);
}
```

此方法将对象参数 `o` 强制转换为 `DataRow`，这就是入口返回集合的类型。已知 `DataRow` 包含两列：第一个是整数，第二个是双精度浮点数。这些值被分配给相应的输出参数——它们映射到入口方法 `SqlFunction` 特性中指定的类型——这是一个完整的实现。

在创建了正确结构的临时表后，调用该函数将完全如你预期的那样：行流过 CLR 方法并返回调用者：

```sql
CREATE TABLE #values
(col1 INT, col2 FLOAT);

INSERT #values
(1, 1.123),
(2, 2.234),
(3, 3.345);
```

```sql
SELECT *
FROM dbo.GetTempValues();
```

```text
(3 row(s) affected)
col1    col2
----------------------------
1        1.123
2        2.234
3        3.345
```

(3 row(s) affected)

其他数据——例如到远程服务器——也是可能的，且这种访问使用了可以使用。

# SQL 过程和触发器

与函数类似，存储过程是类内部的静态方法。很大的区别是，存储过程不需要输出类型（事实上，大多数从不设置返回值），模板默认为输出——这在调用存储过程时实际上会设置为 0。如果你想设置显式的返回值，可以使用任何整数类型而不是列表所示的 `void`。

## 创建 SQLCLR 存储过程

与已经讨论的函数一样，SSDT 包含一个可在 C# 中使用的存储过程模板。

### 列表 9-2 SQLCLR 存储过程模板

```csharp
public partial class StoredProcedures
{
    [Microsoft.SqlServer.Server.SqlProcedure]
    public static void SqlProcedure1()
    {
        // 在此处放置你的代码
    }
}
```

大多数存储过程都会处理数据库内部的数据，对于这一点，就像在函数一样，你可以使用带有上下文连接的 ADO.NET。与函数不同，用于标记存储过程的属性中没有 `DataAccess` 选项；你的存储过程可以自由地在调用者有访问权的任何表中进行插入、更新或删除操作。

为了向调用者返回标量值，会在存储过程中添加一个或多个输出参数，如下代码块所示：

```csharp
[Microsoft.SqlServer.Server.SqlProcedure]
public static void AddToInput(
    SqlInt32 input,
    out SqlInt32 inputPlusOne,
    out SqlInt32 inputPlusTwo)
{
    inputPlusOne = input + 1;
    inputPlusTwo = input + 2;
}
```

发布此过程后，可以像 T-SQL 存储过程一样执行它，使用 `OUTPUT` 子句来访问输出变量返回的值：

```sql
DECLARE @out1 INT, @out2 INT;

EXEC dbo.AddToInput
    @input = 123,
    @inputPlusOne = @out1 OUTPUT,
    @inputPlusTwo = @out2 OUTPUT;

SELECT @out1 AS out1, @out2 AS out2;
```

```
out1    out2
-----------------
124     125
```

(1 row(s) affected)



从存储过程中以表格形式（有时作为消息）返回数据也是常见的。为此，你需要一套稍不同的工具。

## SQL 管道

ADO.NET 虽然非常适合读取数据，但没有明显的机制将数据传回调用者。为了这个目的，微软引入了 `SqlPipe` 类，它允许开发者在 SQLCLR 存储过程的主体内创建消息并返回表格结果。

`SqlPipe` 类的关键方法是 `Send`，它被重载以接受 `String`、`SqlDataRecord` 或 `SqlDataReader`——每个者的行为略有不同。在如下方法中发送字符串会向调用者返回一条消息，类似于下面的 T-SQL `PRINT` 语句。

```csharp
[Microsoft.SqlServer.Server.SqlProcedure]
public static void SendMessage(SqlString message)
{
    var pipe = Microsoft.SqlServer.Server.SqlContext.Pipe;
    pipe.Send("The message is: " + message.Value);
}
```

这里是通过另一个类 `SqlContext` 获取的 `SqlPipe` 对象引用，该类通过静态属性访问 `SqlPipe`。该类还提供了其他一些有用属性，可以帮助将你的 SQLCLR 例程序连接回调用上下文。这些将在本节稍后部分介绍。

执行时，存储过程会发送消息而不是结果集。在 SQL Server Management Studio 中，这表现为“消息”（Messages）页中的一条消息，如图 9-24 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_632_0.png)

图 9-24 调用 SqlPipe.Send

其他加载返回表格结果。如果你想返回仅包含单行的表格，可以将一个格式化的 `SqlDataRecord` 传递给 `Send` 方法。在大多数情况下，建议尽可能使用输出参数。如果你有一个 `SqlDataReader` 的引用（例如从远程源读取数据），也可以直接传递给 `Send` 以将数据作为表格返回给 SQL Server。

该主题更有趣的变体是构造一个具有任意行数的自定义表格结果，这可能源于运行时计算。为了实现这一点，需要三个 `SqlPipe` 方法：`SendResultsStart`、`SendResultsRows` 和 `SendResultsEnd`。这些每个方法的目的如下方法所示，该方法返回一个整数序列：

```csharp
[Microsoft.SqlServer.Server.SqlProcedure]
public static void SendRows(SqlInt32 numberOfRows)
{
    // 设置输出形状
    var col = new SqlMetadata("col", SqlDbType.Int);
    var rec = new SqlDataRecord(col);

    var pipe = Microsoft.SqlServer.Server.SqlContext.Pipe;

    // 开始输出流 -- 这实际上并没有发送任何内容
    pipe.SendResultsStart(rec);

    // 发送行
    for (int i = 0; i < numberOfRows.Value; i++)
    {
        // 将字段 0 (col) 设置为值
        rec.SetInt32(0, i);
        pipe.SendResultsRow(rec);
    }

    pipe.SendResultsEnd();
}
```

从方法顶部开始，第一个任务是通过为每个输出列创建一个 `SqlMetadata` 实例来描述输出形状——在这种情况下，是一个名为 "col" 的单个整数。此列被传递给 `SqlDataRecord` 构造函数，创建一个将将在方法的剩余部分使用的记录。

从这里，获取了 `SqlPipe` 的引用，并对记录调用了 `SendResultsStart`。此调用并没有实际发送记录；相反它为记录定义的表格形状设置了输出。通过实际发送某些行，会初始化本地变量并根据请求的行数进行循环。对于每一行，其值被设置在适当的 `SqlDataRecord` 列（在本例中为 0），并使用 `SendResultsRow` 方法返回行。最后，使用 `SendResultsEnd` 终止流。

结果一旦发布，看起来如下：

```sql
EXEC dbo.SendRows @numRows = 3;
```

```text
col
---
0
1
2

(3 row(s) affected)
```

解决方案是？在返回 .NET 异常之前，将格式化良好的（即 T-SQL 风格的）异常返回给客户端。只获取格式化良好的异常意味着要停止 .NET 异常——这意味着要使用 `try-catch`：

```csharp
[Microsoft.SqlServer.Server.SqlProcedure]
public static void ThrowException_v2()
{
    var pipe = Microsoft.SqlServer.Server.SqlContext.Pipe;
    var comm = new SqlCommand("RAISERROR('test exception', 16, 1)");

    try
    {
        pipe.ExecuteAndSend(comm);
    }
    catch
    {
    }
}
```

由于预计 `ExecuteAndSend` 调用会导致异常，因此没有理由在 `catch` 块中处理任何内容；它可以直接返回控制权。此添加的结果是，调用者只会看到简单的 T-SQL 风格错误消息：

```sql
EXEC dbo.ThrowException_v2;
```

```text
Msg 50000, Level 16, State 1, Line 16
test exception
```

将此技术更进一步，通过使用嵌套的 `try-catch` 块，可以将其应用于未知和意外的异常：

```csharp
[Microsoft.SqlServer.Server.SqlProcedure]
public static void DivideByZero_Nicer()
{
    try
    {
        int i = 1;
        int j = 0;
        int k = i / j;
    }
    catch (Exception e)
    {
        var pipe = Microsoft.SqlServer.Server.SqlContext.Pipe;
        var tsqlThrow = String.Format("RAISERROR('{0}', 16, 1)", e.Message);
        var comm = new SqlCommand(tsqlThrow);

        try
        {
            pipe.ExecuteAndSend(comm);
        }
        catch
        {
        }
    }
}
```

在这里，可能发生异常的代码——数学运算被封装在外部块中。在 `catch` 块内部，提取了外部块的错误消息（使用 `System.Exception` 对象的 `Message` 属性），并格式化了一个 `RAISERROR` 调用。结果是非自定义异常提供了一个格式化良好的消息：

```sql
EXEC dbo.DivideByZero_Nicer;
```

```text
Msg 50000, Level 16, State 1, Line 15
Attempted to divide by zero.
```

尽管这种技术在涉及非开发人员时确实提供了更好的用户体验，但存在两个重要的权衡。首先，标准 .NET 异常中让非技术型用户感到困惑的元素是堆栈跟踪。对于知道如何读取它的人来说，这些信息对于调试目的是无价的。因此，在你的 C# 代码中使用预处理器指令来确保格式化良好的异常仅在发布生成中使用，而永远不在调试生成中使用。

第二个权衡要微妙得多，且有些令人震惊：

```sql
BEGIN TRY
    EXEC dbo.DivideByZero_Nicer;
END TRY
BEGIN CATCH
    SELECT 'you will never see this';
END CATCH;
```

```text
Msg 50000, Level 16, State 1, Line 14
Attempted to divide by zero.
```

在这里，存储过程调用在 T-SQL 侧被封装在 `TRY-CATCH` 中，并且抛出了异常，但 `CATCH` 块被完全忽略了。原因是异常已经被捕获——在 .NET 代码中。

遗憾的是，对于这种特定的权衡没有完美的解决方案。注意，`@@ERROR` 函数将在调用存储过程后立即检查并返回非零值，但向 T-SQL 添加 `TRY-CATCH` 是为了消除与 `@@ERROR` 相关的各种痛苦和焦虑。因此，它在这里有效并提供不了太大满足度。最终，最好的想法是仅在不需要外部异常处理时使用这种技术，或者教育用户如何读取堆栈跟踪。

> 注意：本节中的示例使用了 `RAISERROR` 而不是新的 T-SQL `THROW` 语句。这是刻意为之，因为 `THROW` 似乎并不与 SQLCLR 异常处理机制交互，并且无论是否有 C# `try-catch` 块，它都会导致抛出两个异常。

## 身份与身份模拟

当你处理 SQLCLR 例程序时，你可能会遇到方法必须访问 SQL Server 外部的远程资源的情况。在这种情况下——特别是在处理文件级和其他网络权限时——知道请求是使用谁的安全凭据发起的非常重要。

默认情况下，SQL Server 在发送外部请求时将使用其服务帐户的凭据。然而，如果你的用户通过集成身份验证连接，你可能希望使用他们的凭据——因此使用访问权限。这是通过利用从 `SqlContext` 类提供的 `WindowsIdentity` 对象来实现的。该对象代表——当使用身份身份时——调用者的身份（即对 SQL Server 进行身份验证的登录）。`WindowsIdentity` 类实现了一个 `Impersonate` 方法，这使得你的 SQLCLR 代码能够代表调用者的凭据执行操作。

在 SQLCLR 存储过程中这样设置此内容：

```csharp
[Microsoft.SqlServer.Server.SqlProcedure]
public static void Impersonation()
{
    var pipe = Microsoft.SqlServer.Server.SqlContext.Pipe;
    var ident = Microsoft.SqlServer.Server.SqlContext.WindowsIdentity;

    // 如果用户使用 SQL 身份验证登录，对象将为 NULL
    if (ident == null)
    {
        pipe.Send("Could not impersonate");
    }
    else
    {
        // 否则，尝试模拟
        using (var context = ident.Impersonate())
        {
            pipe.Send(String.Format("Successfully impersonated: {0}", ident.Name));
        }
    }
}
```

此存储过程当 `WindowsIdentity` 对象不为空时尝试模拟。该方法返回 `WindowsImpersonationContext` 类的实例，该类实现了 `IDisposable` 以便在执行完成后调用 `Undo`。这保持了操作尽可能安全。

## SQLCLR 触发器

触发器——无论是 T-SQL 还是 SQLCLR——实际上是绑定到 DML 操作的存储过程，并可以访问特殊的插入和删除虚拟表。还有 DDL 触发器，它们是绑定到 DDL 的。除了已经讨论过的存储过程之外，关于 SQLCLR 触发器没有更多可说的；它们提供了与存储过程相同的功能。SQLCLR 触发器的 SSDT 模板如列表 9-3 所示。

### 列表 9-3 SQLCLR 触发器通用模板

```csharp
public partial class Triggers
{
    // 为目标输入现有表并取消属性行
    // [Microsoft.SqlServer.Server.SqlTrigger(Name="SqlTrigger1", Target="Table1",
    // Event="FOR UPDATE")]
    public static void SqlTrigger1()
    {
        // 替换为你自己的代码
        SqlContext.Pipe.Send("Trigger FIRED");
    }
}
```

与存储过程一样，`SqlContext` 类提供了一个 `SqlPipe` 对象，可以向调用上下文发送消息或表值。SQLCLR 触发器与存储过程不同，它不支持任何输入或输出参数；T-SQL 中没有从触发器输入参数或收集返回语法。

SQLCLR 使用名为 `SqlTrigger` 的属性，它指定了目标表以及一个或多个事件。该属性在 SSDT 模板中被注释掉，以便代码通过编译；为了工作，你需要将表添加到 SSDT 项目中。为此，表的 DDL 为：

```sql
CREATE TABLE [dbo].[MyTable]
(
    [i] INT NOT NULL PRIMARY KEY
);
```

一旦表已添加到项目中，创建一个功能的 SQLCLR 触发器是一个简单的练习：

```csharp
[Microsoft.SqlServer.Server.SqlTrigger(
    Name = "SqlTrigger1",
    Target = "MyTable",
    Event = "FOR INSERT, UPDATE")]
public static void SqlTrigger1()
{
    var build = new SqlConnectionStringBuilder();
    build.ContextConnection = true;

    using (var conn = new SqlConnection(build.ConnectionString))
    {
        var comm = conn.CreateCommand();
        comm.CommandText = "SELECT COUNT(*) FROM inserted";
        conn.Open();
        int rowCount = (int)comm.ExecuteScalar();
        SqlContext.Pipe.Send(String.Format("Rows affected: {0}", rowCount));
    }
}
```

这会触发 MyTable 中被插入或更新的行。要访问被插入或删除的值，需要运行查询，就像在存储过程中一样，这是通过 ADO.NET 结合上下文连接完成的。在这里，触发器计算了 `inserted` 虚拟表中的行数，并返回一个包含计数的消息：

```sql
INSERT MyTable VALUES (123), (456);
GO
```

```text
受影响行数：2
（影响 2 行）
```

`SqlContext` 类有一个名为 `TriggerContext` 的属性，它返回一个 `SqlTriggerContext` 类的实例。该类针对各种情况提供了一些有用的属性和方法：

- `TriggerAction` 属性识别导致触发器触发的操作，而无需像 T-SQL 中那样通过查询 `inserted` 和 `deleted` 表来做出判断。
- `IsUpdatedColumn` 方法允许您识别在导致触发器触发的操作中，特定列是否被更新过。
- `EventData` 属性可能是最有用的，因为它返回以 `SqlCommand` 对象格式化的针对 DDL 操作的事件数据 XML。此类可以通过 `XmlReader` 暴露数据，这使得在 T-SQL 中的处理变得更简单、更快速。

SQLCLR 触发器的主要用例是高级日志和数据传输。遗憾的是，每个 SQLCLR 触发器都必须在 `SqlTrigger` 特性中指定一个类型，并且必须为每个目标表创建一个新方法。这意味着很难创建通用的触发器（例如日志记录），而且重用性低于预期水平。因此，如果你在触发器中需要 .NET 功能，通常更好的做法是从 T-SQL 触发器中根据需要调用 SQLCLR 存储过程或用户定义函数。

## SQLCLR 用户定义类型

在各种 SQLCLR 模块类型中，用户定义类型和用户定义聚合提供了许多 T-SQL 无法提供的功能。用户定义类型允许开发者创建复杂的数据类型，该类型可以包含静态或实例方法、属性、数据验证逻辑或所有这些内容。微软已成功使用此功能实现了 T-SQL 的 `HIERARCHYID`、`GEOGRAPHY` 和 `GEOMETRY` 类型，尽管你应该意识到这些类型已集成到查询优化过程中。用户类型的灵活性可能没有那么大，但仍然具有巨大的潜力。

## 创建用户定义类型

类似于函数和存储过程，可以使用 SSDT 创建用户定义类型。列表 9-4 显示了 SQLCLR 用户定义类型的模板。

### 列表 9-4 用户定义类型的通用模板



[Serializable]
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native)]
public struct SqlUserDefinedType1 : INullable
{
    public override string ToString()
    {
        // 替换为您自己的代码
        return string.Empty;
    }

    public bool IsNull
    {
        get
        {
            // 在此处处入您的代码
            return _null;
        }
    }

    public static SqlUserDefinedType Null
    {
        get
        {
            SqlUserDefinedType1 h = new SqlUserDefinedType1();
            h._null = true;
            return h;
        }
    }
}

```c
public static SqlUserDefinedType Parse(SqlString s)
{
    if (s.IsNull)
        return Null;
    SqlUserDefinedType u = new SqlUserDefinedType();
    // 在此处处入您的代码
    return u;
}
```

```c
// 这是一个占位方法
public string Method1()
{
    // 在此处处入您的代码
    return string.Empty;
}
```

```c
// 这是一个占位方法
public static SqlString Method2()
{
    // 在此处处入您的代码
    return new SqlString("");
}
```

```c
// 这是一个占位成员字段
public int _var1;
```

```c
// 私有成员
private bool _null;
```

SQLCLR 用户定义类型可以是结构体也可以是类。它们必须实现 `INullable` 接口，该接口包含了 `IsNull` 属性。与存储过程和函数不同，用户定义类型必须装饰有相应的特性：`SqlUserDefinedType` 控制类型的各种行为，而 `Serializable` 则允许 SQL Server 以二进制格式存储该类型的实例。

用户定义类型除了 `INullable` 定义的属性外，还有必需的方法和属性（这些方法和属性在部署期间会验证）：

- `Null` 是一个必须返回该类型空实例的属性。可空性在模板中使用布尔成员 `_null` 实现，通常修改模板中 `Null` 或 `IsNull` 属性的逻辑是不值得的。
- `Parse` 是一个静态方法，用于从字符串创建类型的实例。该方法被 T-SQL 重写，以便可以使用 `DECLARE @t dbo.Type = 'value'` 语法来初始化类型。
- `ToString` 是一个实例级方法，实际上是 `Parse` 的相反；它的作用是提供一个表示该类型实例的字符串。理想情况下，`ToString` 和 `Parse` 应该是完全兼容的。

## 部署和使用用户定义类型

（此处内容与前文重复，已按要求完成翻译）

要实际获取类型的字符串表示，你必须显式调用 `ToString` 来执行转换工作。操作方法如下：

```sql
DECLARE @t dbo.SqlDefinedType = '123';
SELECT @t.ToString() AS typeValue;
GO
```

```text
typeValue
-------
123
-------
(1 row(s) affected)
```

> 重要：SQLCLR 用户定义类型上的方法和属性名是大小敏感的。未使用正确的大小写会导致令人困惑的“找不到方法”（could not find method）错误。

## 处理更复杂的类型

作为一名处理用户定义类型的开发者，如果不需要引用类型或复杂解析场景等更高级的功能，你将无法进展顺利。字符串、集合和类在 .NET CLR 以及大多数其他库中广泛使用，因为这些类型与原生格式不兼容，因此需要考虑更高级且暴露的选项。此外，`Parse` 方法可能并不是所有场景的最优选择。

为了说明可能需要不同技术的类型，考虑存储在数据库中的地址。通常会看到这些地址建模为——至少在美国——：一列城市、一列州份、一列邮政编码，以及一列或两列地址行。地址行的示例是 "546 Contoso St."。这一行虽然被视为单个值，但实际上由多个部分组成。美国地址由以下组合组成：

- 建筑门号，可能包含也可能不包含数字字符——例如 546 或 546B。
- 街道的前方向词，例如 "W. Contoso" 中的 "W."。并不是所有街道都使用这些词，在定义地址行部分时它们是可选的。
- 街道名称。
- 街道类型，可能是 "street"、"way"、"boulevard" 等。这些通常是缩写。
- 后方向词，与前方向词一样，并不是所有街道都使用。例如 "Contoso ST SW."。

假设你想开发数据库并按通常的方式存储地址行——作为城市、州份和邮政编码之外的列——但你又想根据某些报告需求验证并提取这些组成部分。在这种情况下，用户定义类型可能是一个理想选择。

这种类型将命名为 `SqladdressLine`——它拥有五个不同的字符串，对应前面列表中定义的每一个。这需要以下五个成员变量：

```cs
private SqlString _buildingNumber;
private SqlString _streetName;
private SqlString _streetType;
private SqlString _preDirectional;
private SqlString _postDirectional;
```

该类型旨在用于验证，因为这些成员每个都被定义为私有（private），并配有公共（public）访问器/设置属性（getter/setter）。建筑、街道名称和街道类型不是可选的，并且可以验证它们为非空且不完全由空格组成。这可以使用以下方法完成：

```cs
private SqlString validateNull(SqlString input)
{
    if (input.IsNull || input.Value.Trim() == "")
        throw new Exception("Attempted to use NULL or an empty string in a non-nullable field");
    return (input);
}
```

除了非空外，街道类型还可以被验证为正确且支持的街道类型。为此，使用了以下方法：

```cs
private SqlString validateType(SqlString type)
{
    if (
        type == "ST" ||
        type == "LN" ||
        type == "RD" ||
        type == "WAY" ||
        type == "BLVD" ||
        type == "HWY")
        throw new ArgumentException(String.Format("Invalid type: {0}", type.Value));
    return (type);
}
```

需要的最后一个验证方法是针对前方向词和后方向词值的：

```cs
private SqlString validateDirection(SqlString direction)
{
    if (
        direction.IsNull ||
        direction == "N" ||
        direction == "NE" ||
        direction == "E" ||
        direction == "S" ||
        direction == "SE" ||
        direction == "SW" ||
        direction == "W"
    ) {
        throw new ArgumentException(String.Format("Invalid direction: {0}", direction.Value));
    }
    return (direction);
}
```

一旦定义了这些方法，就可以如下创建公共访问器属性：

```cs
public SqlString BuildingNumber
{
    get { return (_buildingNumber); }
    set { _buildingNumber = validateNull(value); }
}

public SqlString StreetName
{
    get { return (_streetName); }
    set { _streetName = validateNull(value); }
}

public SqlString StreetType
{
    get { return (_streetType); }
    set { _streetType = validateNull(value); }
}

public SqlString PreDirectional
{
    get { return (_preDirectional); }
    set { _preDirectional = validateDirection(value); }
}

public SqlString PostDirectional
{
    get { return (_postDirectional); }
    set { _postDirectional = validateDirection(value); }
}
```

只要这些方法被用于值的公共和内部操作，验证将是内置且保证的。通常，定义成员变量后的第一个任务是实现一个解析程序，在这种情况下这是一项相当困难的任务。确定哪些部分存在——特别是处理具有两个、三个或四个单词的街道名称时——是一个辛苦的任务。与其尝试这样做，你可以通过将 `Parse` 方法标记为已实现来禁用它，而是引入一个或多个返回类型完整实例静态方法：

```cs
public static USAddressLine Parse(String s)
{
    throw new NotImplementedException("Parse not supported.");
}
```

用户定义类型仍然要求该方法，但一旦此代码存在，任何尝试使用字符串初始化类型都会抛出异常。与其这样做，用户可以使用工厂方法之一：

```cs
public static USAddressLine StandardLine(
    String BuildingNumber,
    String StreetName,
    String StreetType)
{
    var addressLine = new USAddressLine();
    addressLine.BuildingNumber = BuildingNumber;
    addressLine.StreetName = StreetName;
    addressLine.StreetType = StreetType;
    return (addressLine);
}
```

```cs
public static USAddressLine PreDirectionLine(
    String BuildingNumber,
    String PreDirectional,
    String StreetName,
    String StreetType)
{
    var addressLine = StandardLine(
        BuildingNumber,
        StreetName,
        StreetType);
    addressLine.PreDirectional = PreDirectional;
    return (addressLine);
}
```

常见的地址没有任何方向词，因此 `StandardLine` 方法仅根据门号、街道名称和街道类型返回地址。使用公共访问以确保所有内容都经过验证。包含前方向词的地址行也很常见，因此实现了第二个方法来处理这种情况。由于后方向词并不常见，没有创建显式方法；用户必须先调用这些方法之一，然后单独设置后方向属性。注意需要两个方法是因为 SQLCLR 不支持方法、属性或类型的继承。

使用这些工厂方法需要一种适用于静态方法的特殊引用语法。以下示例使用工厂方法实例化类型并使用 `SET` 关键字设置后方向词值：

```sql
DECLARE @t dbo.USAddressLine = dbo.USAddressLine.StandardLine('123', 'Contoso', 'ST');
SET @t.PostDirectional = 'SW';
GO
```

在类型实际上在此级别运行之前，它需要能够二进制序列化。因为内部使用了引用类型，必须在 `SqlUserDefinedType` 属性上设置几个选项：

```cs
[Microsoft.SqlServer.Server.SqlUserDefinedType(
    MaxByteSize = 8000,
    IsFixedLength = false,
    IsByteOrdered = true)]
```

格式被设置为 `UserDefined`（自定义），这将需要显式的二进制格式实现。作为该实现的一部分，开发者必须定义类型二进制范围的最大大小（字节为字节），范围从 1 到 8000，或从 -1 到 2 GB。在这种情况下，使用 8 是基于以下假设（记住 .NET 中的所有字符串都是 Unicode 并占用两个字节）：

- 建筑门号最多八个字符。
- 前方向词最多两个字符。
- 街道名称最多 25 个字符。
- 街道类型最多四个字符。
- 后方向词最多两个字符。

该类型不是固定长度的的；换句话说，二进制格式的长度取决于类型的各种实例以及地址行各个部分的值。并且该类型将是字节序的（byte ordered）。

最后一个选项可能对 `USAddressLine` 类型没有用，但对许多其他类型来说是关键的。字节序意味着通过比较类型的二进制格式，可以使用大于或小于操作对类型实例进行比较。如果此属性被设置为 `true`，则类型可以参与——例如在索引或作为 `ORDER BY` 列中。然而，你必须小心实现二进制格式，以便实例能够得到正确的比较，否则会在你的代码中引入微妙的 Bug。

此接口指定了两个方法：`Read` 和 `Write`。`Write` 输出类型的二进制表示形式，而 `Read` 则从二进制数据重构该类型。以下是 `USAddress` 类型的 `Write` 方法：

```cs
public void Write(System.IO.BinaryWriter w)
{
    w.Write(_null);
    if (!_null)
    {
        w.Write(BuildingNumber.Value);
        if (!PreDirectional.IsNull)
        {
            w.Write(PreDirectional.Value);
        }
        else
            // 将 NULL 表示为空字符串
            w.Write("");
        w.Write(StreetName.Value);
        w.Write(StreetType.Value);
        if (!PostDirectional.IsNull)
        {
            w.Write(PostDirectional.Value);
        }
        else
            w.Write("");
    }
}
```

该方法首先写入 `_null` 成员的值，该值控制实例是否为空。如果不为空，则继续处理。写入建筑号，然后是前方向词。每个 `Write` 调用都必须有一个对应的 `Read` 调用。因此，即使某个值是空，也必须写入某些内容——在这里是一个空字符串。同样写入街道名称和街道类型，在后方向词之后进行空检查。正因为所有内容都是按照特定顺序写入的，该类型才能被称为“字节排序的”，无论这在实践中是否有用。

`Read` 遵循 `Read(System.IO.BinaryReader r)`：

```cs
public void Read(System.IO.BinaryReader r)
{
    _null = r.ReadBoolean();
    if (!_null)
    {
        BuildingNumber = new SqlString(r.ReadString());
        var preDir = r.ReadString();
        if (preDir != "")
            PreDirectional = new SqlString(preDir);
        StreetName = r.ReadString();
    }
}
```



## SQLCLR 用户定义类型实现细节

### Read 方法实现

```csharp
StreetType = r.ReadString();
}

var postDir = r.ReadString();

if (postDir != "")
    PostDirectional = new SqlString(postDir);
}
```

与 `Write` 从成员变量读取不同，`Read` 是将它们写回。首先检查空属性，然后是建筑号、前方向词的检查，依此类推——顺序与值写入的顺序完全相同。

### ToString 方法实现

在尝试使用该类型之前的最终实现是 `ToString` 方法。尽管如前所述，理想情况下你希望 `ToString` 和 `Parse` 方法是相互兼容的，但在这里是不可能的。不过，`ToString` 的组装非常简单：

```csharp
public override string ToString()
{
    return (
        BuildingNumber.Value + " " + 
        (PreDirectional.IsNull ? "" : PreDirectional.Value + " " + 
        StreetName.Value + " " + " " + 
        StringType.Value + " " + " " + 
        (PostDirectional.IsNull ? "" : PostDirectional.Value));
}
```

### 类型使用示例

在将所有内容整合并发布后，即可使用该类型：

```sql
DECLARE @dbo.USAAddressline = dbo.USAAddressline::Standardline('123', 'Contoso', 'ST');
SET @t.PostDirectional = 'SW';
SELECT
    @t.ToString() AS AddressLine,
    @t.BuildingNumber AS BuildingNumber,
    @t.StreetName AS StreetName,
    @t.StringType AS StreetType;
GO
```

| AddressLine | BuildingNumber | StreetName | StreetType |
|---|---|---|---|
| 123 Contoso ST SW 123 | | Contoso | ST |

(影响了 1 行)

一旦填充，该类型将以字符串或其组成部分之一的形式暴露基础数据。该类型实现了内置验证，并可以实现其他行为。（例如，它在内部可以连接到地理编码引擎。）尽管较保守的实践者可能认为这是一个不好的主意，但这种设计可以为数据库增加大量的灵活性和功能。

## SQLCLR 用户定义聚合

用户定义聚合（User-defined aggregates）与用户定义类型类似，代表了通过 SQLCLR 可用的功能，这些功能与 T-SQL 中的任何内容都没有相似之处。尽管 SQL Server 自带各种聚合函数——`COUNT`、`SUM`、`AVG` 等，但编写自定义聚合的能力是非常强大的，并为复杂的开发场景创建了极大的程序化灵活性。

### 创建用户定义聚合

用户定义聚合与用户定义类型相似，具有几乎相同的编程模式和注意事项。它们要么是结构体（`structs`），要么是类（`classes`），并且在各个阶段必须进行二进制格式化。SSDT 格式如列表 9-5 所示。

**列表 9-5** 用户定义聚合的通用模板

```csharp
[Serializable]
[Microsoft.SqlServer.Server.SqlUserDefinedAggregate(Format.Native)]
public struct SqlAggregate
{
    public void Init()
    {
        // 在此处放置你的代码
    }

    public void Accumulate(SqlString Value)
    {
        // 在此处放置你的代码
    }

    public void Merge(SqlAggregate Group)
    {
        // 在此处放置你的代码
    }

    public SqlString Terminate()
    {
        // 在此处放置你的代码
        return new SqlString(string.Empty);
    }

    // 这是一个占位成员字段
    public int _var1;
}
```

用户定义聚合必须实现四个强制方法，这些方法与类型的生命周期对应：

- 当聚合即将开始时，为每个组实例化该类型的实例（由 `GROUP BY` 子句或其他因素决定，取决于计划），并调用 `Init`。`Init` 的工作是初始化任何变量到正确的状态。这对于内部使用集合类的聚合最为重要。
- 对于要聚合的每行数据，SQL Server 会调用 `Accumulate` 方法。该方法消耗数据并将其添加到变量。默认输入类型是 `QString`，但 `Accumulate` 可以接受任何可转换类型（作为函数和过程）。
- 如果多个组在单独线程上进行聚合，但属于同一个组，则通过一次或多次调用 `Merge` 方法结合在一起。该方法的作用是消耗另一个组的数据并与本地聚合的数据合并。
- 一旦聚合完成，聚合必须产生标量结果。这是 `Terminate` 方法的工作。

用户定义聚合的实例将在处理期间的若干点进行二进制序列化，二进制数据临时存储在 `tempdb` 中。这主要是为了减少在运行大量行、并发聚合或两者时的内存压力。因此，用户定义聚合必须是可序列化的，并实现原生序列化（如果内部仅值类型）或自定义序列化。

实现并发布后，用户定义聚合可以像内置聚合一样使用，结合 `GROUP BY` 子句或使用 `OVER` 子句进行分区（不排序）。请注意，与用户定义类型不同，聚合绑定到架构；在所有使用聚合的情况下，都需要架构引用。

### Concatenate 聚合实现

SQL Server 开发者的一个常见请求是创建一个内置聚合，允许从存储在行中的字符串创建逗号分隔的字符串。虽然你可以在 T-SQL 中通过多种方式实现，但与标准的 SQL 聚合和 `GROUP BY` 语法相比，你的某些方法相当笨拙。在 C# 中实现此类聚合几乎是轻而易举的，它是使用用户定义聚合的一个良好示例。

首先，聚合需要在累积期间存储字符串的地方。虽然它可以简单地使用内部字符串并在每次累积新行时进行追加，但这种方法的计算开销很大。.NET 中的字符串一旦创建后是不可变的，修改现有的字符串实际上创建创建一个字符串。使用集合类更好：

```csharp
private System.Collections.Generic.List<string> stringList;
```

```csharp
public void Init()
{
    stringList = new System.Collections.Generic.List<string>();
}
```

此处使用 `List` 泛型集合类显示代码，其类型为字符串集合。同时展示了 `Init` 方法的实现，它简单地实例化了局部变量 `stringList` 以便进行读取。完成后，就可以实现 `Accumulate`：

```csharp
public void Accumulate(SqlString Value)
{
    if (Value.IsNull)
        // 在每个字符串前添加一个逗号
        stringList.Add("," + Value.Value);
}
```

该方法接受一个 `SqlString`，并首先进行空值检查；如果传递了 `null`，则会被直接忽略。如果输入不为 `null`，则会在前面添加一个逗号。稍后在生成最终输出字符串时，列表中第一个字符串前面的逗号将被删除，以确保不会出现多余的逗号。

接下来是 `Merge` 方法：

```csharp
public void Merge(Concatenate Group)
{
    foreach (string s in Group.stringList)
        this.stringList.Add(s);
}
```

当调用 `Merge` 时，它会从另一个聚合函数的 `stringList` 中读取值，并将其添加到本地的 `stringList` 中。这实际上等同于一次一次调用 `Accumulate` 处理值，对于更复杂的聚合函数，内部调用 `Accumulate` 方法可能是一个好主意。如果值已经合并，另一个聚合函数将被释放，因此无需担心它或其在内存中的值。

最后一个要实现的代码方法是 `Terminate()`：

```csharp
public SqlString Terminate()
{
    if (stringList.Count == 0)
        return SqlString.Null;
    else
    {
        // 移除第一个字符串上的逗号
        stringList[0] = stringList[0].Substring(1, stringList[0].Length - 1);
        return new SqlString(string.Concat(stringList.ToArray()));
    }
}
```

如果调用了 `Init` 但没有遇到非 `null` 值，则内部集合将包含零元素，聚合函数可以向调用者返回 `null`。另一方面，如果存在某些数据，应该移除任何前置的逗号——这是通过取集合中第一个元素的子集来实现——并使用 `String.Concat` 和 `Array` 方法生成一个连接后的字符串。

由于此聚合函数使用了集合，必须修改定义属性并实现 `IBinarySerialize` 接口：

```csharp
[Serializable]
[Microsoft.SqlServer.Server.SqlUserDefinedAggregate(
    Format = Format.UserDefined,
    MaxByteSize = -1,
    InvariantToDuplicates = false,
    InvariantToNulls = true,
    InvariantToOrder = false
)]
public struct Concatenate : IBinarySerialize
```

与 `SqlUserDefinedAggregate` 属性一样，它包含了 `Format` 设置，已设置为 `UserDefined`。`MaxByteSize` 指定为 -1（用于支持高达 2 GB 的数据），因为字符串数组可以任意增长。

接下来的选项通过限制可以选择的查询来保护聚合过程。`InvariantToDuplicates` 如果置为 `true`，意味着查询可能会聚合源中不存在的重复值，这不会引起任何数据问题——考虑例如 `COUNT(DISTINCT)`。在字符串拼接的情况下，情况并非如此，因此该选项被设置为 `false`。`InvariantToNulls` 如果置为 `true`，则允许优化器生成可能导致聚合额外 `null` 值的计划。对于此聚合函数，因为它处理 `null` 值，所以这不是问题，因此被设置为 `true`。

`InvariantToOrder` 自 SQL Server 2005 起被包含在 `SqlUserDefinedAggregate` 属性中，它引发了许多讨论和推测。事实证明，它在任何方面都没有功能，微软从未对其进行过正式评论，也没有采取移除措施。建议不要在你的聚合函数中设置它，以防它被启用并导致意想不到的结果。

`IBinarySerialize` 的 `Write` 方法如下：

```csharp
public void Write(System.IO.BinaryWriter w)
{
    w.Write(stringList.Count);
    foreach (string s in stringList)
        w.Write(s);
}
```

该方法首先写入字符串列表中的元素数量，然后写入每个字符串。作为自定义类型，`Read` 反向执行该操作：

```csharp
public void Read(System.IO.BinaryReader r)
{
    Init();
    int count = r.ReadInt32();
    while (count > 0)
    {
        stringList.Add(r.ReadString());
        count--;
    }
}
```

`Read` 首先调用 `Init`，因为这在调用 `Read` 方法之前不会自动完成——只有在调用 `Accumulate` 之前才会完成。一旦字符串列表实例化，就会读取写入的字符串数量，并为每个字符串调用一次 `ReadString`。`ReadString` 的调用次数应等于对相同字符串执行 `Write` 的调用次数。

发布后，聚合函数终于可以测试了：

```sql
SELECT dbo.Concatenate(theString) AS CSV
FROM
(
    VALUES
        ('abc'),
        ('def'),
        ('ghi')
) AS x (theString);
GO
```

```
CSV
abc,def,ghi
```

(影响 (s) 行)

如 "x" 的派生使用 `VALUES` 子句在名为 `theString` 的列中创建了三个具有字符串值的行。这些值被传递给 `dbo.Concatenate` 聚合函数，输出结果如预期的逗号分隔字符串。

在实践中，聚合函数在大量的 T-SQL 开发场景中极其有用。它们可以实现从简单任务（如此类操作）到复杂算法的任何功能。

## 事务处理

假设没有发生停电，你通过运行以下代码成功提交了其余更改并提交了事务：

```sql
INSERT INTO dbo.T2(keycol, col1, col12) VALUES(4, 201, 'X');
COMMIT TRAN;
```

一旦你收到 SQL Server 对 `COMMIT TRAN` 命令的确认，即认为该事务在执行上是持久的（durable）的。我稍后会详细阐述持久性属性。

一致性（consistency）属性指的是数据库的状态。在事务开始之前和完成后，数据库被认为处于一致状态。在事务提交事务或回滚之前，数据库状态将处于不一致状态。

在 SQL Server 中，约束被视为即时约束——也就是说，它们在每条语句的结束时都会进行检查，即使该语句是用户事务的一部分。SQL Server 不支持延迟约束（deferred constraints），延迟约束仅在事务提交时才进行检查。

隔离性（isolation）属性意味着 SQL Server 将一个事务产生的数据与其他事务隔离开。但对于你的应用程序来说，一致性数据具体意味着什么，取决于你的应用程序的需求。例如，假设在一个事务中发生了两次相同的查询。你的应用程序是否要求事务是可重复的（repeatable）？如果答案是，那么第二次读取必须返回你之前读取的行。如果答案否，那么第二次读取返回你之前读取的但已更改的行也是可以的。你可以通过将隔离级别设置为你所需的语义的级别来控制隔离的程度。

最后，持久性（durability）属性确保了当你提交事务时，一旦收到数据库的确认，你就可以确保事务已完成，并且在系统崩溃时可以恢复。恢复模型（recovery model）是一个数据库设置，决定了数据库的可恢复性。支持的选项有 `SIMPLE`、`BULK_LOGGED` 和 `FULL`。如果恢复模型为 `FULL`，则 SQL Server 在提交时将更改硬化（harden）到日志文件中。硬化更改意味着将 60-KB 的日志缓冲区（log buffer）刷新到磁盘上的日志文件中。如果你使用的是 `SIMPLE` 或 `BULK_LOGGED` 恢复模型，缓冲区操作仅执行最少日志，以支持需要时的回滚操作。因此，当你提交事务时，为了保证持久性，仅让 SQL Server 刷新日志缓冲区是不够的；它还需要将脏数据页从缓冲区池刷新到数据文件中。结果，在 `SIMPLE` 和 `BULK_LOGGED` 恢复模型下，提交可能花费更长时间。

SQL Server 2014 引入了一项名为延迟持久性（delayed durability）的新功能。我将在本节后面的部分介绍。

SQL Server 不支持嵌套事务。但它允许你嵌套 `BEGIN TRAN`/`COMMIT TRAN` 语句并为事务命名，但实际上最多只有一个事务。`ROLLBACK TRAN <tran_name>` 命令（带有事务名称）仅在引用最外层的事务名称时有效。每执行一次 `BEGIN TRAN` 命令，SQL Server 都会增加一个计数器，可以通过 `@@trancount` 函数查询。每执行一次 `COMMIT TRAN` 命令，只有当计数器降到 0 时，事务才会实际提交。

假设你开启了一个事务并在其中调用了一个存储过程。在存储过程中，你发布了 `BEGIN TRAN` 命令，执行了一些工作，并发布了 `COMMIT` 命令。当过程结束时，你仍然处于一个开启的事务中。如果发生导致事务回滚的故障，事务的所有更改都会撤销——包括存储过程调用之前之后提交的更改，以及存储过程提交的更改。

由于 SQL Server 不支持嵌套事务，在存储过程内部，你无法强制执行实际提交。然而，如果你在某些条件下需要撤销存储过程的工作，可以使用保存点（savepoint）为此目的。在存储过程的开头，你可以检查是否已经处于 `@@trancount` 内部。如果你不在事务中，在一个变量中发布 `BEGIN TRAN`（称之为 `@tranexisted`）。如果你已经在事务中，则发布 `SAVE TRAN <savepoint_name>`。如果你在事务中，当过程执行完成时，你确保了事务已完成。但如果你在某些条件下需要撤销存储过程的工作，可以使用保存点来实现此目的。

以下代码演示了如何实现这种策略（使用事务）：

```sql
```



DECLARE @tranexisted INT = 0, @allisgood INT = 0;

-- 假设这里有逻辑来检查 @trancount

IF @trancount = 0
BEGIN
    BEGIN TRAN;
    SET @tranexisted = 1;
END
ELSE
BEGIN
    SAVE TRAN savepoint1;
END

-- ... 业务逻辑 ...

IF @tranexisted = 1
BEGIN
    ROLLBACK TRANSACTION;
END
ELSE
BEGIN
    ROLLBACK TRANSACTION savepoint1;
END

```
你可以取消 BEGIN TRAN 和 COMMIT TRAN 命令来测试代码。当执行良好时（当 `@allisgood` 设置为 1 时，你不回滚工作）以及执行不佳时（当 `@allisgood` 设置为 0 时，你需要回滚工作）。运行此代码，它代表在过程执行时开启了事务，且过程执行不佳。代码会回滚。代码产生输出：

回滚事务。

取消 BEGIN TRAN 和 COMMIT TRAN 命令并再次运行代码。这代表在过程执行时开启了事务，且过程执行不佳。代码回滚到保存点。代码产生输出：

回滚到保存点。
```

# 锁与阻塞

SQL Server 支持不同的模型来强制执行你所需的隔离语义。旧模型（仍然是磁盘表的 SQL Server 默认值）是基于锁的。在这种模型中，行只有一个版本。你的会话需要获取锁来与数据交互，无论是写入还是读取。如果你的会话请求的资源（行、页或表）与另一个会话持有的锁发生冲突，你的会话将被阻塞。这意味着你需要等待另一个会话释放锁或等待超时过期。

磁盘表的另一种模型是行版本模型，它是 Microsoft Azure Database（或“SQL Database”）的默认值。在这种模型中，当你更新或删除行时，SQL Server 将行的版本复制到 tempdb 中的版本存储区，并创建当前行到旧版本的链接。SQL Server 可以在链列表中维护同一行的多个版本。这是对锁模型的一种增强。写入者使用锁，读者不需要。当会话需要读取资源时，它不请求锁。如果当前版本不是会话在当前隔离级别下的版本，SQL Server 将遵循链列表以检索较早的版本。

表 9-2，排他锁（`X`）与所有类型的锁都不兼容，反之亦然。写入者对于所有类型的修改都需要排他锁。这在锁模型和行版本模型中的磁盘表中都是如此。共享锁（`S`）与共享锁兼容。在锁模型中，大多数隔离级别下，读者都需要获取共享锁来读取资源。例外是 Read Uncommitted 隔离级别，在该级别下读者不获取共享锁。

## 表 9-2 锁兼容性

| 请求模式 | IS | S | U | IX | SIX | X |
|---|---|---|---|---|---|---|
| 意向共享 (IS) | 是 | 是 | 是 | 是 | 是 | 否 |
| 共享 (S) | 是 | 是 | 是 | 否 | 否 | 否 |
| 更新 (U) | 是 | 是 | 否 | 否 | 否 | 否 |
| 意向排他 (IX) | 是 | 否 | 否 | 是 | 否 | 否 |
| 共享且意向排他 (SIX) | 是 | 否 | 否 | 否 | 否 | 否 |
| 排他 (X) | 否 | 否 | 否 | 否 | 否 | 否 |

更新锁 (`U`) 是共享锁和排他锁的一种混合体。与共享锁一样，更新与另一个共享锁兼容。与排他锁一样，更新与另一个更新锁不兼容。这意味着一次只有一个会话可以对资源持有更新锁。SQL Server 在内部使用更新锁来保护索引中的访问路径，以便搜索一个需要修改的行。你也可以在查询中使用表提示显式地请求更新锁，例如：

```sql
SELECT ... FROM Table WITH (UPDLOCK) WHERE ...;
```

这种显式提示的一个经典案例是：当你有一个事务涉及读取数据、应用某些计算并写入数据时。如果你想确保在任何给定时刻只有一个会话运行，可以在启动该过程的 `SELECT` 查询中添加 `UPDLOCK` 提示。这样，先执行查询的人就可以运行该流程。其他人将必须等待。稍后，我将解释这种方法如何帮助防止被称为“更新丢失”的现象。

锁兼容性表中的剩余锁是意向锁。包括意向共享锁 (`IS`)、意向排他锁 (`IX`) 和共享意向排他锁 (`SIX`)。意向共享锁和意向排他锁会阻塞相同粒度级别上的冲突锁请求，但不会阻塞较低层级的请求。共享意向排他锁类似于意向排他锁，但带有共享锁的额外限制会阻塞较低粒度级别上的冲突锁。

例如，SQL Server 内部使用意向锁来保护你所交互的资源层次结构。假设你需要作为事务的一部分更新某行。你的会话需要一个排他锁来更新该行。假设你的会话获取了表锁并应用了更新，但你的事务仍开启着。此时，另一个会话尝试获取整个表的共享锁。这里存在冲突，但 SQL Server 无法直接判断存在冲突，因为资源是不同的——一个是行，另一个表。为了简化冲突检测，当你的会话获取资源锁时，它必须在较高粒度级别上获取相同类型的意向锁。例如，为了更新一行，你的会话在请求行的排他锁之前，必须获取表的排他锁。这样，如果另一个会话尝试获取同一表或页上的冲突锁，SQL Server 将很容易检测到冲突。

当你的会话请求的锁与现有锁不兼容时，就会阻塞。默认情况下，等待时间没有限制。如果你想设置限制，可以在会话或客户端中进行。在会话中，你可以设置一个名为 `LOCK_TIMEOUT` 的毫秒选项。默认值为 -1，意味着无限。如果设置了此选项，一旦超时，你将收到错误 1222。

在依赖锁定模型的系统中，短期阻塞是正常的。然而，如果阻塞持续很长时间，就会变成一个问题。如果用户经常遇到长时间锁定，你需要评估你正在使用的模型。对于阻塞导致异常延迟的特定情况，SQL Server 提供了工具来排查状况。例如，假设你的代码中有一个错误导致事务一直开启。你的会话将一直持有任何通常持续到事务结束的锁（例如排他锁）。在有人终止你的事务之前，其他会话将开始抱怨等待。假设你收到了支持电话并需要排查这种状况。

在我演示这种阻塞情况之前，请运行以下代码以初始化我将在演示中查询的行：

```sql
UPDATE dbo.T1 SET col2 = 'Version 1' WHERE keycol = 2;
```

打开两个连接；将它们命名为 connection 1 和 connection 2。当我在系统中这样操作时，第一个的会话 ID 为 53，第二个为 54。

从 connection 1 执行以下代码以开启事务，并用新值修改 T1 中的行：

```sql
SET NOCOUNT ON;
USE testdb;
GO
BEGIN TRAN;
UPDATE dbo.T1 SET col2 = 'Version 2' WHERE keycol = 2;
```

为了应用更新，会话会获取表上的意向排他锁、页上的意向排他锁以及行的排他锁。

从 connection 2 执行以下代码以查询 T1 中的所有行：

```sql
SET NOCOUNT ON;
USE testdb;
GO
SELECT keycol, col1, col2 FROM dbo.T1;
```

该 `SELECT` 查询在默认的隔离级别 `Read Committed` 下运行。会话获取表上的意向共享锁和页上的意向共享锁。一旦它尝试获取被另一个会话排他锁的行的共享锁，请求就会被阻塞。现在，使用 connection 2 的用户正在等待。

我在这里描述的所有工具都是 SQL Server 的内置工具。Adam Machanic 创建了自己的专属工具，以存储过程 `sp_WhoIsActive` 的形式来排查阻塞。许多人发现它非常有用，并将其作为你系统中的标准工具。你可以在 Adam 的博客中找到该存储过程、其使用方法说明以及许可条款：http://tinyurl.com/WholesActive。

回到我们的排错过程；此时，你已经知道会话 53 是阻塞会话，它的事务处于打开状态并将一直持续到有人终止它。要终止与会话 53 关联的用户进程以及会话中的打开事务，请使用 `KILL` 命令：

```sql
KILL 53;
```

会话 53 中事务应用的更改将被撤销。回到连接 2，会话 54 成功获得了它一直在等待的共享锁并完成了查询。该查询生成了以下输出：

```
keycol col1 col2
--------------------
1 101 A
2 102 Version 1
3 103 C
4 101 C
```

如所述，为了尝试我们的示例，请执行 `LOCK_TIMEOUT` 会话选项以以毫秒为单位设置锁超时。（你需要先重新连接。）然后在连接 2 中执行以下代码设置五秒的锁超时并运行查询：

```sql
SET LOCK_TIMEOUT 5000;
SELECT keycol, col1, col2 FROM dbo.T1;
```

五秒后，你将收到一个提示超时的错误：

```
Msg 1222, Level 16, State 51, Line 2
Request time out period exceeded.
```

运行以下代码恢复到默认的无限等待：

```sql
SET LOCK_TIMEOUT -1;
```

测试完成后，关闭两个连接。

## 锁升级 (Lock escalation)

你的事务获取的每个锁都由内存结构表示，该结构使用细粒度锁（如行锁或页锁），但仅为 100 字节。通常，你的事务从获取细粒度锁开始，在某个时刻，SQL Server 将介入并执行升级过程。如果不这样做，获取大量锁的事务将消耗大量内存，并且需要更长时间才能完成，因为分配这些内存结构需要时间。一旦单个事务针对同一对象获取了 5000 个锁，SQL Server 就会尝试将细粒度锁升级为表锁。如果 SQL Server 未成功升级锁——例如当另一个会话正在锁定同一表中的某行——它将在每增加 1250 个锁后再次尝试。一旦 SQL Server 成功升级，事务将锁定整个表。

锁升级的优点是显而易见的——你用的内存更少，事务完成得更快。缺点是你锁定的范围超过了你的需求，这会影响你系统的并发性。人们在尝试访问本可以访问的资源时可能会被阻塞。

为了演示锁升级，我将使用一个名为 `TestEscalation` 的表，你可以通过运行以下代码创建并填充它：

```sql
USE testdb;
IF OBJECT_ID(N'TestEscalation', 'U') IS NOT NULL DROP TABLE dbo.TestEscalation;
GO
```

```sql
SELECT n AS col, CAST('a' AS CHAR(200)) AS filler
INTO dbo.TestEscalation
FROM TSQLV3.dbo.GetNums(1, 100000) AS Ns;
```

```sql
CREATE UNIQUE CLUSTERED INDEX idx1 ON dbo.TestEscalation(col);
```

运行该事务，它从表中删除 20,000 行，然后检查与当前会话 ID 关联了多少个锁：

```sql
BEGIN TRAN;
DELETE FROM dbo.TestEscalation WHERE col <= 20000;
SELECT COUNT(*)
FROM sys.dm_tran_locks
WHERE request_session_id = @SPID
AND resource_type <> 'DATABASE';
ROLLBACK TRAN;
```

代码报告仅存在锁，表明发生了锁升级。

接下来，禁用锁升级并再次运行事务：

```sql
ALTER TABLE dbo.TestEscalation SET (LOCK_ESCALATION = DISABLE);
```

```sql
BEGIN TRAN;
DELETE FROM dbo.TestEscalation WHERE col <= 20000;
SELECT COUNT(*)
FROM sys.dm_tran_locks
WHERE request_session_id = @SPID;
ROLLBACK TRAN;
```

这一次，代码报告存在超过 20,000 个锁，表明没有发生锁升级。你也可以使用带有 `lock_escalation` 事件的扩展事件会话来捕捉锁升级事件。

完成后，运行以下代码进行清理：

```sql
IF OBJECT_ID(N'dbo.TestEscalation', N'U') IS NOT NULL DROP TABLE dbo.TestEscalation;
```

## 延迟持久性 (Delayed durability)

回想之前关于事务持久性的讨论。SQL Server 使用一种称为“预写日志”（write-ahead logging）的概念来优化日志写入。这意味着它首先在 60-KB 日志缓冲区满时将日志写入缓冲区，当事务提交时，你保证事务的持久性。在负载密集的 OLTP 环境中，你有大量的小事务，每个事务只执行少量工作，导致对事务日志产生少量写入。此类环境往往会有频繁的日志缓冲区刷新。SQL Server 2014 引入了一个名为“延迟持久性”的功能，你可以用它来放宽持久性要求，代价是在如果发生电源故障时可能会丢失数据。这允许事务更快地完成，从而减少瓶颈。

重要提示：理解延迟持久性可能导致数据丢失至关重要。只有当你真的不在乎数据丢失时，才应该使用此功能。你通过将数据库选项设置为三个值之一来控制它：

- Disabled（已禁用）：所有事务都是完全持久的。
- Allowed（允许）：事务可以是完全持久的，也可以是延迟持久的，取决于事务级别的指定。
- Forced（强制）：事务是延迟的。

为了演示此功能及其对性能的影响，我将使用名为 `testdb` 的数据库以及其中名为 `T1` 的表。运行以下代码创建数据库和表，并将数据库中的 `DELAYED_DURABILITY` 选项设置为 `Allowed`（允许）：

```sql
SET NOCOUNT ON;
USE master;
GO
IF DB_ID('testdb') IS NOT NULL DROP DATABASE testdb;
GO
CREATE DATABASE testdb;
ALTER DATABASE testdb SET DELAYED_DURABILITY = Allowed;
GO
USE testdb;
CREATE TABLE dbo.T1(col INT NOT NULL);
```

在运行每个测试之前，清空表以确保它是空的：

```sql
TRUNCATE TABLE dbo.T1;
```

运行以下代码以自动模式向 T1 插入 100,000 行完全持久事务：

```sql
DECLARE @i INT = 1;
WHILE @i <= 100000
BEGIN
    INSERT INTO dbo.T1(col) VALUES(@i);
    SET @i += 1;
END;
```

这段代码在我的系统上花费了 33 秒完成。

在运行下一个测试之前，清空表：

```sql
TRUNCATE TABLE dbo.T1;
```

运行以下代码以延迟事务向 T1 插入 100,000 行数据：

```sql
DECLARE @i INT = 1;
WHILE @i <= 100000
BEGIN
    BEGIN TRAN;
    INSERT INTO dbo.T1(col) VALUES(@i);
    COMMIT TRAN WITH (DELAYED_DURABILITY = ON);
    SET @i += 1;
END;
```

这段代码在我的系统上仅花费了两秒就完成了。

```sql
BEGIN TRAN;
DECLARE @i AS INT = 1;
WHILE @i <= 100000
BEGIN
    INSERT INTO dbo.T1(col1) VALUES(@i);
    SET @i += 1;
END
COMMIT TRAN;
```

这段代码在我的系统上执行了一次。

在最终测试之前清除表：

```sql
TRUNCATE TABLE T1;
```

运行以下代码，在一个大型延迟持久性事务向 T1 中插入 100,000 行数据：

```sql
BEGIN TRAN;
DECLARE @i AS INT = 1;
WHILE @i <= 100000
BEGIN
    INSERT INTO dbo.T1(col1) VALUES(@i);
    SET @i += 1;
END
COMMIT TRAN WITH (DELAYED_DURABILITY = ON);
```



对于这种类型的负载，这段代码仅用一秒钟就完成了。

这些测试证实，主要从延迟持久性功能受益的负载类型是包含许多小事务的负载。

# 隔离级别

你使用隔离级别来控制“一致性数据”对你意味着什么。在与数据库数据交互时，你会遇到许多经典现象；每种现象的出现取决于你所运行的隔离级别。这些现象包括：

- **脏读 (Dirty reads)**：对未提交的数据进行读取。一个事务更改了数据，但在另一个事务读取相同数据之前尚未提交。第二个事务最终读取到了不一致的数据状态。
- **丢失更新 (Lost updates)**：两个事务并行运行以下操作：读取数据、进行某些计算并更新数据。在这种流程下，一个事务可能会覆盖另一个事务的更新。
- **不可重复读（也称为不一致分析）**：在同一事务的两次独立查询中，读取相同行时得到了不同的值。如果第二个更改在第一个会话发出的查询之间更改了数据，就会发生这种情况。
- **幻读 (Phantoms)**：在同一事务的两个使用相同过滤条件的独立查询中，第二个查询返回的行不属于第一个查询的结果。如果第二个事务在其两次查询中插入了符合第一个事务查询条件的新行，就会发生这种情况。这些新行被称为幻读。

表 9-3 总结了隔离级别以及每种级别下可能出现的现象。我很快将提供更多细节并演示在不同隔离级别下的工作。

### 表 9-3 隔离级别总结

| 隔离级别 | 脏读 | 丢失更新 | 不可重复读 | 幻读 | 并发模型 | 更新冲突检测 |
|---|---|---|---|---|---|---|
| 读取未提交的 (Read Uncommitted) | 是 | 是 | 是 | 是 | 悲观 | 否 |
| 读取已提交 (Read Committed) | 否 | 是 | 是 | 是 | 悲观 | 否 |
| 可重复读 (Repeatable Read) | 否 | 否 | 否 | 是 | 悲观 | 否 |
| 可序列化 (Serializable) | 否 | 否 | 否 | 否 | 悲观 | 否 |
| 取快照 (Snapshot) | 否 | 否 | 否 | 否 | 乐观 | 是 |
| 读取已提交快照 (Read Committed Snapshot) | 否 | 是 | 是 | 是 | 乐观 | 否 |

对于基于磁盘的表，你有两种隔离级别可用：锁定，以及锁定与行版本的混合。前者支持四种隔离级别：`READ UNCOMMITTED`、`READ COMMITTED`、`REPEATABLE READ` 和 `SERIALIZABLE`。后者支持两种隔离级别：`READ COMMITTED SNAPSHOT` 和 `SNAPSHOT`。SQL Server 的默认内置视图是 `READ COMMITTED`，而在云平台（SQL Database）上是 `READ COMMITTED SNAPSHOT`。

你可以在会话级别或每个表的查询级别设置隔离级别。你通过执行以下语句在会话级别设置隔离级别：

```sql
SET TRANSACTION ISOLATION LEVEL <isolation>
```

在该语句中，`<isolation level>` 可以是以下之一：`READ UNCOMMITTED`、`READ COMMITTED`、`REPEATABLE READ`、`SERIALIZABLE` 或 `SNAPSHOT`。

你通过使用提示词（`READCOMMITTED`、`READ COMMITTED`、`REPEATABLE READ`、`SERIALIZABLE` 或 `SNAPSHOT`）在每个表的查询级别设置隔离级别。`NOLOCK` 等于 `READCOMMITTED`，`HOLDLOCK` 等于 `SERIALIZABLE`。

会话 1 释放了该行的排他锁，允许连接 2 中的会话获取它一直等待的共享锁并读取数据。你在连接 2 中得到以下输出：

```
col2
------
Version 2
```

在连接 2 中，你之前的等待是为了读取数据的提交状态。

运行以下代码将修改后的行中 `col2` 的值改回 `'Version 1'`。

```sql
UPDATE dbo.T1 SET col2 = 'Version 1' WHERE keycol = 2;
```

关闭两个连接。

`READ COMMITTED` 级别并不尝试防止不可重复读。假设你在事务内两次查询了相同的行。由于你没有在行与行之间持有任何锁，另一个会话可以在此期间修改数据。因此，两个不同的查询可能会获取同一行的不同状态。

`READ COMMITTED` 级别并不尝试防止丢失更新。假设你有两个并行运行的事务，它们都包含读取数据、计算以及稍后更新数据的流程。两个事务都读取数据的相同初始状态。每个事务都根据其计算结果，尝试将自己的值写入数据。其中一个事务将先应用更新并提交。另一个事务将最后应用更新，从而覆盖第一个事务的更新。

## 可重复读（Repeatable Read）隔离级别

可重复读隔离级别保证，一旦事务内的查询读取了某些行，事务中的所有后续查询都将获得行的相同状态。SQL Server 通过让读取器在目标行上获取共享锁并一直保持这些锁直到事务结束来实现这一行为。当你开启一个事务并读取某些行后，另一个尝试更新这些行的会话将被阻塞，直到你的事务完成。因此，你事务内的后续读取保证将获得与第一次读取相同的行状态。

要查看可重复读的演示，打开两个连接。在连接 1 中运行以下代码将会话隔离级别设置为可重复读，开启一个事务并读取一行：

```sql
SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;
BEGIN TRAN;
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
```

你得到以下输出：

```
col2
-----
Version 1
```

尝试从连接 2 更新同一行：

```sql
UPDATE dbo.T1 SET col2 = 'Version 2' WHERE keycol = 2;
```

你被阻塞了，因为你需要该行的排他锁，而在另一个会话持有该行共享锁时，你无法获取该锁。

回到连接 1，运行以下代码再次查询该行并提交事务：

```sql
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
COMMIT TRAN;
```

你得到以下输出，这代表了可重复读：

```
col2
-----
Version 1
```

同时，写入器获取了它一直等待的排他锁，修改了该行并提交了事务。

完成后，运行以下代码进行清理：

```sql
UPDATE dbo.T1 SET col2 = 'Version 1' WHERE keycol = 2;
```

关闭连接。

可重复读隔离级别不处理更新冲突。假设你有两个并行运行的事务，它们都包含读取数据、计算以及稍后更新数据的流程。两个会话在获取共享锁后读取数据的相同状态，并一直保持锁直到事务结束。每个事务都根据计算结果，尝试用自己的值更新数据。为了更新数据，两个会话都请求排他锁，每个都会被对方的共享锁阻塞。这就是死锁。SQL Server 会检测到死锁，通常在几秒内。一旦检测，它会选择一个会话进行回滚并释放所有锁。该会话会收到错误 1205。考虑到此类错误，你编写带有重试逻辑的错误处理代码。如果你的会话被选为死锁受害者，当你通过读取数据的新状态来重试事务时，会在更新数据之前将其用于计算。这样，更新就不会丢失。

如果你遇到了与防止丢失更新相关的死锁，你应该重新评估你的解决方案。另一种方案是使用 `READ COMMITTED` 隔离级别，并在你想防止丢失更新的事务中，在读取数据的查询中添加 `UPDLOCK` 提示。先读取数据的会话获取更新锁，而第二个获取的会话在尝试读取数据时就会阻塞。你实现了事务的队列，而无需带有重试逻辑的错误处理代码。

## 可序列化（Serializable）隔离级别

可序列化隔离级别保证，一旦你在事务内查询了数据，你将一直处理相同状态的数据，只看到你自己的更改，直到事务完成。换句话说，事务以可序列化的方式处理数据。当会话开启事务并访问数据时，就像它是唯一正在与数据交互的人一样。

例如，如果你在同一个事务中多次发出相同的查询，该查询的所有出现都会得到完全相同的结果（假设同一个事务在查询之间没有修改数据）。你不仅保证能获得像可重复读隔离级别那样的重复读，还保证不会出现幻读。在可重复读隔离级别下，幻读是可能的。人们经常对此感到惊讶，但各位，可重复读隔离级别仅保证一旦你读取了行，后续读取将获得行的相同状态。

清理线程每分钟启动一次，并从行尾开始移除不再需要的行版本，直到遇到仍被需要的第一行版本。因此，如果你有长时间运行的事务，会增加产生长链的概率。

在基于行版本的隔离级别下，读取器不需要等待。读取者不使用共享锁，这一事实减少了与锁相关的开销，并倾向于减少阻塞和死锁。权衡是读取器可能需要遍历链表来获取正确的版本，并且读取器需要将行版本写入版本存储器。你需要确保在负载增加时使用了 `tempdb`，并且在生产环境中启用行版本控制之前进行测试。

每种基于行版本的隔离级别都需要你开启相应的数据库选项来启用它。要使用**快照隔离（Snapshot）**隔离级别，你需要开启数据库标记 `ALLOW_SNAPSHOT_ISOLATION`。这会导致 SQL Server 开始对行进行版本处理。要实际使用快照隔离级别，你还需要将会话的隔离级别设置为 `SNAPSHOT`。要配合**已提交快照（Read Committed Snapshot）**隔离级别，你需要开启数据库选项 `READ_COMMITTED_SNAPSHOT`。一旦开启，你将默认的**已提交（Read Committed）**隔离级别的语义从仅锁语义变为锁与行版本混合的语义。由于启用此标志会更改默认的隔离级别，你将排除对数据库的独占访问应用。新连接在你想使用共享锁的情况下将使用此设置，此时你需添加表提示 `READCOMMITTEDLOCK`。

要在 `testdb` 数据库中启用快照隔离级别，请开启数据库选项 `ALLOW_SNAPSHOT_ISOLATION ON`，如下所示：

```sql
ALTER DATABASE testdb SET ALLOW_SNAPSHOT_ISOLATION ON;
```

打开两个连接。在连接 1 中运行以下代码以开启事务、更新一行并读取该行：

```sql
BEGIN TRAN;
UPDATE dbo.T1 SET col2 = 'Version 2' WHERE keycol = 2;
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
```

此代码生成了以下输出：

```
col2
------
Version 2
```

查询 `sys.dm_tran_version_store` 以查看当前位于版本存储器中的行版本。

```sql
SELECT * FROM sys.dm_tran_version_store;
```

你会在输出中得到一个行版本。

在连接 2 中运行以下代码，将会话的隔离级别设置为 `SNAPSHOT`，开启事务并查询被连接 1 修改的行：

```sql
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;
BEGIN TRAN;
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
```

记住，在快照隔离下，你获得的是事务级别一致的数据视图。这意味着在整个事务期间，你获得的是在事务内执行第一条语句时点数据的最后提交状态。你将获得以下输出：

```
col2
------
Version 1
```

然后，在连接 1 中运行以下代码提交事务并读取该行：

```sql
COMMIT TRAN;
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
```

你将获得以下输出：

```
col2
------
Version 2
```

回到连接 2，运行以下代码再次读取该行（此时仍处于开启的事务中）：

```sql
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
```

你得到的行状态与上一个查询得到相同：

```
col2
------
Version 1
```

如果你是在**已提交快照**隔离级别下运行，你得到的将不是 `'Version 1'`，而是新的提交状态 `'Version 2'`。

最后，在连接 2 中运行以下代码提交事务并再次查询该行：

```sql
COMMIT TRAN;
SELECT col2 FROM dbo.T1 WHERE keycol = 2;
```

你将获得以下输出：

```
col2
------
Version 2
```

运行以下代码将该行更新回值 `'Version 1'`：

```sql
UPDATE dbo.T1 SET col2 = 'Version 1' WHERE keycol = 2;
```

如前所述，快照隔离级别通过检测更新冲突来防止丢失更新。例如，连接 1 运行以下代码将隔离级别设置为 `SNAPSHOT`，开启事务并查询某行：

```sql
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;
BEGIN TRAN;
SELECT col2 FROM dbo.T1 where keycol = 2;
```

你将获得以下输出：

```
col2
------
Version 1
```

在连接 2 中，运行以下代码更新同一行：

```sql
UPDATE dbo.T1 SET col2 = 'Version 2' WHERE keycol = 2;
```

回到连接 1，尝试将该行更新为：

```sql
UPDATE dbo.T1 SET col2 = 'Version 3' WHERE keycol = 2;
```

SQL Server 检测到有人修改了正尝试更新的行，并生成了错误 3960，表示检测到更新冲突：

```
Msg 3960, Level 16, State 2, Line 7
Snapshot isolation aborted due to update conflict. You cannot use snapshot isolation to access table 'dbo.T1' directly in database 'tempdb' to update, delete, or insert the row that has been modified or deleted by another transaction. Retry the transaction or
```

## 死锁

死锁是形成循环的阻塞情况组合。它可能涉及两个或多个会话。例如，假设会话 X 阻塞 Y，Y 阻塞 Z，而 Z 阻塞 X。SQL Server 每分钟主动搜索一次。当检测到死锁时，它会将搜索间隔降低到 100 毫秒，具体取决于死锁的频率。在一段时间没有死锁后，它会将间隔增加到五秒。当 SQL Server 检测到死锁时，它会选择涉及的一个会话作为受害者并终止其事务。该会话获取错误 1205；撤销事务内的所有工作并释放所有锁。

SQL Server 根据两个标准选择受害者。你可以在会话中设置名为 `DEADLOCK_PRIORITY` 的选项，值范围为 -10 到 10。SQL Server 选择死锁优先级最低的会话作为受害者。如果优先级相同，SQL Server 将根据事务日志中记录的回滚工作量来选择工作量最少的任务。如果优先级和估计工作量相同，SQL Server 将随机选择受害者。

SQL Server 提供了许多工具来排查死锁。跟踪标记 1222 和 1204 可以将死锁输出到错误日志。跟踪事件死锁图和扩展事件 `event_deadlock_report`（属于 `system_health` 会话）可用于在 Profiler 和 SSMS 中以可视化方式查看死锁图。你还可以运行包含以下事件的跟踪或扩展事件：`sql_statement_starting`、`sp_statement_starting`，或根据需要：`lock_deadlock` 和 `lock_deadlock_chain`。死锁链事件报告了涉及的 ID。你可以分析相关会话的语句开始事件，从其事务开始到死锁事件发生。通过这种方式，你可以识别出导致死锁的语句序列。运行此类跟踪或扩展事件的问题在于，如果运行时间很长，开销可能会。

## 简单死锁示例

为了演示简单死锁，请打开两个连接。在连接 1 中运行以下代码以开启事务并更新 T1 中的一行：

```sql
BEGIN TRAN;
UPDATE dbo.T1 SET coll = coll + 1 WHERE keycol = 2;
```

该会话获取了行的排他锁。

在连接 2 中运行以下代码以开启事务并更新 T2 中的某行：

```sql
BEGIN TRAN;
UPDATE dbo.T2 set coll1 = coll1 + 1 WHERE keycol = 2;
```

该会话获取了该行上的排他锁。

回到连接 1，运行代码来查询 T2 中被另一个会话锁定并提交到事务的行：

```sql
SELECT coll1 FROM dbo.T2 WHERE keycol = 2;
COMMIT TRAN;
```

该会话需要一个共享锁来读取该行，但在另一个会话持有该行的排他锁时，它无法获取该锁。该会话被阻塞。

在连接 2 中运行以下代码，尝试查询 T1 中被另一个会话锁定的行并提交事务：

```sql
SELECT coll1 FROM dbo.T1 WHERE keycol = 2;
COMMIT TRAN;
```



该会话也被阻塞了。此时，你发生了死锁。在几秒钟内，SQL Server 会检测到该任务，根据我之前描述的逻辑选择一个死锁受害者，并终止受害者的事务。在我的案例中，SQL Server 选择连接 2 中的会话作为受害者。我在连接 2 中收到了以下错误：

Msg 1205, Level 13, State 5, Line 5
Transaction (Process ID 54) was deadlocked on lock resources with another process and has been chosen as the deadlock victim. Rerun the transaction.

关闭两个连接。

## 减少死锁发生的措施

当死锁发生频率较低时，你可以使用带有重试逻辑的错误处理代码在获取错误 1205 时重试任务。但当系统中的死锁频繁发生，它们可能会变成性能问题。期望消除系统中所有的死锁发生是不现实的；毕竟，它们是有理由的。但你完全可以采取措施来减少其发生频率。

可以避免的死锁常见原因是缺少重要的索引。如果你没有索引来支持查询筛选，SQL Server 必须扫描整个表来获取符合条件的行。在扫描表时，它会获取你不需要的行锁。结果是，即使涉及的会话之间没有真正的逻辑冲突，你也会遇到导致死锁的冲突。

要查看此类死锁的演示，请打开两个连接。从连接 1 运行以下代码以开启事务并更新 `T1` 中 `col1` 等于 101 的行：

```sql
BEGIN TRAN;

UPDATE dbo.T1 SET col2 = col2 + 'A' WHERE col1 = 101;
```

从连接 2 运行以下代码以开启事务并更新 `T2` 中 `col1` 等于 203 的行：

```sql
BEGIN TRAN;

UPDATE dbo.T2 SET col2 = col2 + 'B' WHERE col1 = 203;
```

从连接 1 运行以下代码查询 `T2` 中 `col1` 等于 201 的行：

```sql
SELECT col2 FROM dbo.T2 WHERE col1 = 201;

COMMIT TRAN;
```

尽管没有真正的逻辑冲突，你被阻塞了。

从连接 2 运行以下代码查询 `T1` 中 `col1` 等于 103 的行：

```sql
SELECT col2 FROM dbo.T1 WHERE col1 = 103;

COMMIT TRAN;
```

你再次被阻塞，尽管没有真正的逻辑冲突。此时，SQL Server 检测到了死锁。在我的测试中，SQL Server 终止了连接 2 中的事务，生成了以下错误：

Msg 1205, Level 13, State 51, Line 1
Transaction (Process ID 54) was deadlocked on lock resources with another process and has been chosen as the deadlock victim. Rerun the transaction.

运行以下代码创建缺失的索引：

```sql
CREATE INDEX idx_col1 ON dbo.T1(idx_col1);

CREATE INDEX idx_col2 ON dbo.T2(idx_col2);
```

重新运行测试，但首先在两个 `SELECT` 查询的表名后添加 `WITH(INDEX(idx_col1))` 以让 SQL Server 使用该索引。通常情况下，你不需要这样做。但是由于我们示例中的表很小，SQL Server 有可能会扫描整个表。这次，测试应该在没有冲突的情况下完成。

除了索引，你还可以采取其他措施来减少系统中死锁的发生。在不同事务中访问物理资源的顺序很重要。例如，考虑之前提出的简单死锁示例。在一个事务中，你先修改 `T1` 然后查询 `T2`，在另一个事务中，你先修改 `T2` 然后查询 `T1`。如果对你的应用程序来说，按特定顺序执行这些活动并非关键，那么通过在两个事务中以相同的顺序访问对象（例如，先 `T1` 后 `T2`），可以防止死锁的发生。

另一个你应该考虑的方面是事务的长度。事务越长，发生阻塞的可能性越大，因此死锁的可能性也越大。你应该尝试通过提取出并非事务真正组成部分的活动来缩短事务的长度。

最后，另一个你应该考虑的措施是更改你正在使用的隔离级别。例如，假设你目前使用的是 Read Committed（已提交）隔离级别。你有大量的并发问题，包括死锁，而且许多是并列发生的。

总结一下，你可以采取的措施有：
- 添加重要的索引
- 按相同顺序访问对象
- 缩短事务长度
- 更改隔离级别（例如更改为 Read Committed Snapshot）

通过这种方式，你避免了在 `SELECT` 语句中进行查找，从而防止了死锁。另一个选项是评估切换到基于行版本的隔离级别。在这样的隔离级别下，读取者不会获取共享锁，这消除了我们用例中发生死锁的可能性。显然，你不会仅仅因为这个原因就考虑切换到基于行版本的隔离级别，但如果你确实在评估这个选项，那么这就是你列表中可以增加的理由之一。

测试完成后，运行以下代码进行清理：

```sql
USE testdb;

IF OBJECT_ID('dbo.T1', 'U') IS NOT NULL DROP TABLE dbo.T1;

IF OBJECT_ID('dbo.T2', 'U') IS NOT NULL DROP TABLE dbo.T2;
```

关闭连接。

## 错误处理

本节介绍了如何使用 `TRY-CATCH` 结构在 T-SQL 中进行错误处理。它比较了使用和不使用该结构的错误处理方式。描述了可用的错误函数和 `THROW` 命令。涵盖了如何在事务中执行错误处理以及如何应用重试逻辑。

在我的示例中，我将使用一个名为 `Employees` 的表，你可以通过运行以下代码创建它：

```sql
USE tempdb;

IF OBJECT_ID('dbo.Employees', N'U') IS NOT NULL DROP TABLE dbo.Employees;

CREATE TABLE dbo.Employees (
    empid INT NOT NULL,
    epname VARCHAR(25) NOT NULL,
    mgrid INT NULL,
    /* other columns */
    CONSTRAINT PK_Employees PRIMARY KEY(empid),
    CONSTRAINT CHK_Employees_upid CHECK(empid > 0),
    CONSTRAINT FK_Employees_Employees
    FOREIGN KEY(mgrid) REFERENCES dbo.Employees(empid)
)
```

## TRY-CATCH 结构

`TRY-CATCH` 结构是大多数现代编程语言使用的经典错误处理结构。SQL Server 中的实现非常基础，但如果你是一个经验丰富的 T-SQL 开发人员，在将其与旧的错误处理循环进行比较时，你会发现它的价值。

在旧版本的 SQL Server 中，引入 `TRY-CATCH` 结构之前，你处理错误的主要工具是 `@@ERROR` 函数。该函数会返回你上一个语句是否已终止。如果语句执行成功，函数返回 0；如果发生错误，函数返回错误号。基于此处理错误存在许多问题。几乎每个语句都会导致函数值被覆盖。因此，你必须在每个可能产生错误的语句之后将函数值捕获到变量中，以防丢失错误号。这迫使你将业务代码与错误处理代码混合在一起，这被认为是一种坏做法；它会损害错误处理代码的可维护性和重用性。此外，当你没有在批处理（例如存储过程）中使用 `TRY-CATCH` 来终止执行时，在这些情况下，如果该批处理中有错误处理代码，它将没有机会运行，你必须在调用者中处理该错误。

`TRY-CATCH` 结构解决了旧版错误处理的许多不完善之处。你在 `TRY` 块中指定常规业务代码，在 `CATCH` 块中指定错误处理代码。如果 `TRY` 块成功完成，则将跳过 `CATCH` 块。如果发生错误，SQL Server 将把控制权交给 `CATCH` 块中的第一行代码。例如，运行以下代码向 `Employees` 表插入一个新行：

```sql
SET COUNT ON;

BEGIN TRY
    INSERT INTO dbo.Employees(empid, empname, mgrid)
    VALUES(1,'Emp1', NULL);
    PRINT 'After INSERT';
END TRY
BEGIN CATCH
    PRINT 'INSERT failed';
    /* handle error */
END CATCH;
```

在第一次执行代码时，`INSERT` 语句成功完成。执行 `TRY` 块中的下一行代码并跳过 `CATCH` 块。你得到以下输出：

After INSERT

再次执行代码。`INSERT` 语句由于主键违反错误而失败。SQL Server 将控制权交给 `CATCH` 块。你得到以下输出：

INSERT failed

如果你对在 `TRY-CATCH` 结构中正确使用分号感兴趣，请注意，你应该只在 `END CATCH` 关键字之后放置分号，如下所示：

```sql
BEGIN TRY
    ...
END TRY
BEGIN CATCH
    ...
END CATCH;
```

如果你在 `BEGIN TRY` 或 `BEGIN CATCH` 子句后指定分号，不会报错。然而在这种情况下，分号并不被视为这些子句的终止符；相反，它是一个空语句的无意义的终止符。如果你在 `END TRY` 之后放置分号，将得到错误。简而言之，正确的语法是只在 `END CATCH` 关键字之后放置分号。

如果错误被 `TRY-CATCH` 结构捕获，则错误不会报告给应用程序。如果错误发生在存储过程内部（或任何其他模块内部）但不在 `TRY` 块内部，错误将向上传播直到找到 `TRY` 块。SQL Server 将控制权交给相应的 `CATCH` 块。如果在整个堆栈中未找到 `TRY` 块，错误将报告给应用程序。SQL Server 支持嵌套的 `TRY-CATCH` 结构，因此如果你预判 `CATCH` 块可能会发生错误，可以将代码放在嵌套的 `TRY-CATCH` 结构中。如果错误在没有嵌套 `TRY-CATCH` 的情况下发生在 `CATCH` 块中，该错误处理方式与不使用 `TRY-CATCH` 时相同。

我使用这段代码是为了说明。我发布了 `PRINT` 语句，以便你可以看到代码的哪些部分被激活了。

当你第一次执行此代码时，`INSERT` 语句成功完成，并跳过了 `CATCH` 块。你得到以下输出：

After INSERT

当你第二次执行该代码时，`INSERT` 语句由于主键违反而失败，SQL Server 将控制权交给了 `CATCH` 块。错误处理代码将该错误识别为主键违反。你得到以下输出：

Handling PK violation...
Error Number : 2627
Error Message : Violation of PRIMARY KEY constraint 'PK_Employees'. Cannot insert duplicate key in object 'dbo.Employees'. The duplicate key value is (2).
Error Severity : 14
Error State : 1
Error Line : 4
Error Proc : Not within proc

在更改传递给以下选项的员工 ID 值后，尝试运行代码几次：0; NULL, 10/0。最后一个会导致“除以零”错误。此错误不是你想要在当前层级处理的错误之一；因此，代码重新抛出了该错误。

## 事务中的错误

当事务中发生错误但不在 `TRY` 块中发生时，就事务而言，有两种可能的结果：要么错误足够小（例如，主键违反），导致 SQL Server 保持事务处于打开且可提交状态；要么错误足够严重（例如，转换错误），导致 SQL Server 终止事务。在这种情况下，你只需要查询 `@@trancount` 函数即可知道事务状态。如果该函数返回零，则表示没有打开的事务；如果它返回大于 0 的值，则事务是打开的且可提交的。在后一种情况下，你可以决定想做什么；你可以回滚事务，也可以提交它。如果你希望所有错误都导致事务终止，请开启会话的 `XACT_ABORT`。

当错误在 `TRY` 块内的事务中发生时，处理方式会有所不同。在 `TRY` 块之外通常会导致事务结束的错误，当它在 `TRY` 块内部发生时，会导致事务进入一个打开的不稳定状态。这也被被称为“失败的、注定的”状态。当事务处于这种状态时，你不允许进行任何更改，但允许你读取数据；相反，你最终必须在开始在新事务中应用更改之前回滚。这种状态与 SQL Server 直接终止你的事务相比的优势是，你可以在回滚事务之前读取事务生成的数据。

回想当你开启会话选项 `XACT_ABORT` 时，所有在 `TRY` 块之外发生的错误都会导致事务终止。然而，开启此选项对在 `TRY` 块内部发生的错误有不同影响；所有错误都会导致事务进入打开且不可提交的状态。

当错误在 `TRY` 块内的事务中发生时，就事务而言，有三种可能的结果。如果错误足够小（例如，主键违反），事务保持打开且可提交。如果错误更严重（例如，转换错误），事务进入打开且不可提交的状态。如果错误非常严重，SQL Server 可能会终止事务。如前所述，某些严重程度为 20 及以上的错误会导致 SQL Server 引擎停止处理该会话并断开连接，因为你将无法使用 `TRY-CATCH` 结构捕获这些错误。但是，某些严重程度为 20 及以上的错误不会中断连接，你将能够捕获它们。

如果你需要在使用 `TRY-CATCH` 结构捕获错误后知道事务状态，仅查询 `@@tran` 函数是不够的。该函数仅告诉你事务是否打开，是打开且可提交还是不可提交。要获取此信息，你必须查询 `XACT_STATE` 函数。该函数有三个可能的返回值：0 表示没有打开的事务，1 表示打开且可提交，-1 表示打开且不可提交。

以下代码演示了你可能想要如何处理事务中的错误：

```sql
SET XACT_ABORT ON

BEGIN TRY
    BEGIN TRAN;
    INSERT INTO dbo.Employees(empid, empname, mrid) VALUES ('Emp3', 1);
    /* other activity */
    COMMIT TRAN;
    PRINT 'Code completed successfully.';
END TRY
BEGIN CATCH
    PRINT 'Error ' + CAST(ERROR_NUMBER() AS VARCHAR(10)) + ' found.';
    IF (XACT_STATE()) = -1
    BEGIN
        PRINT 'Transaction is open but uncommittable.';
        /* ...investigate data... */
        ROLLBACK TRAN; -- can only ROLLBACK
        /* ...handle the error... */
    END
    ELSE IF (XACT_STATE()) = 1
    BEGIN
        PRINT 'Transaction is open and committable.';
        /* ...handle error ... */
        COMMIT TRAN; -- or ROLLBACK
    END;
    ELSE
    BEGIN
        PRINT 'No open transaction.';
        /* ...handle error ... */
    END;
END CATCH;

-- SET XACT_ABORT OFF
```

在 `CATCH` 块中，查询 `XACT_STATE` 函数。如果函数返回 -1，你可以读取数据以调查你需要的内容，然后你必须回滚事务。如果它返回 1，则事务打开且可提交，你可以根据意愿回滚或提交事务。如果它返回 0，则没有打开的事务，尝试提交或回滚事务是没有意义的。这种尝试会导致错误。如果你愿意，可以开启新事务并应用更改。

第一次运行此代码。`INSERT` 语句成功完成，你得到以下输出：

Code completed successfully.

第二次运行此代码。`INSERT` 语句由于主键违反而失败，它保持打开且可提交。你得到输出：

Error 2627 found.
Transaction is open and committable.

将员工 ID 更改为 'abc' 并再次运行代码。`INSERT` 语句由于转换错误而失败，导致事务进入打开且不可提交的状态。你得到输出：

Error 245 found.
Transaction is open but unittable.

将员工 ID 改回 3，取消 `SET XACT_ABORT` 命令并再次运行代码。`INSERT` 语句由于主键违反而失败，导致事务进入打开且不可提交的状态。你得到输出：

Error 2627 found.
Transaction is open but unittable.

## 重试逻辑

对于某些错误，如死锁和更新冲突，经典的处理方法涉及应用重试逻辑。如果你的会话发生了错误，一旦你结束事务，另一个会话就可以继续。如果你重试任务，可能会成功。你可以创建一个实现重试逻辑的包装存储过程，并调用处理原始任务的存储过程。以下代码演示了这样的包装存储过程可能的样子（`MyProc` 是处理原始任务的存储过程）：

```sql
CREATE PROC dbo.MyProcWrapper(<parameters>)
AS
BEGIN
    DECLARE @retry INT = 10;
    WHILE (@retry > 0)
    BEGIN
        BEGIN TRY
            EXEC dbo.MyProc <parameters>;
            SET @retry = 0; -- finished successfully
        END TRY
        BEGIN CATCH
            SET @retry = @retry - 1;
            IF @retry = 0 THROW;
        END CATCH
    END
END
```



BEGIN CATCH

    SET @retry = 1;

    IF (@retry > 0 AND ERROR_NUMBER() IN (1205, 3960)) -- errors for retry

    BEGIN

        IF XACT_STATE() <> 0

            ROLLBACK TRANSACTION;

    END

    ELSE

    BEGIN

        THROW; -- max retries reached or other error

    END

END CATCH

END

END

GO;

```

此示例演示了如何针对基于磁盘表的死锁和更新冲突错误处理重试逻辑。相同的模式也可以用于处理内存优化的

然而，你不需要寻找错误 1205 和 3960，而是要寻找错误代码 41302、41305、41325 和 41301，它们分别代表更新冲突、可重复读验证、可序列化验证以及依赖事务中止错误。

## 结论

本章重点讨论了 SQL Server 支持的一些可编程构建体，主要是涉及查询的那些。它涵盖了动态 SQL、用户定义函数、存储过程、触发器、SQLCLR、事务与并发以及错误处理。在许多情况下，讨论的重点在于如何健壮高效地使用代码。

# 第 10 章
## 内存优化事务 (In-Memory OLTP)

Microsoft SQL Server 2014 引入了内存优化事务（In-Memory OLTP）功能。内存优化事务可以极大提升性能，但你需要理解并理解性能提升并非主要因为数据驻留在内存中。相反，性能的提升源于利用数据在内存中的这一事实，并使用不同的数据结构和方法使数据库操作变得高效得多。本章将帮助你理解这些不同的结构和方法，以及如何使用它们来释放内存优化事务的性能潜力。我将进行简要概述以帮助理解背景，然后讨论在查询和设计系统时如何以不同的方式处理内存优化表。

在本章中，我的示例将主要基于 AdventureWorks 示例数据库，并已扩展包含内存优化表。该数据库可以从 `https://msftdbproducts.codplex.com/releases/view/114491` 下载，并用于任何运行兼容版本 SQL Server（SQL Server 2014 或更高版本的企业版、开发者版或评估版）的服务器。

## 内存优化事务概览

内存优化事务系统最初是一个“蓝天项目”（blue-sky project），当时 SQL Server 开发团队面临挑战，要求清零开始，根据当今的业务和硬件格局，想象如果从零开始设计，数据库引擎会什么样。这个蓝天项目变成了代号为 Hekaton 的开发项目。他们对现代计算环境得出了几点观察：

- 通用系统现在支持足够的内存，可以将一个感兴趣的数据集始终保留在内存中。此前，数据库管理系统一次只能将部分数据调入内存。这些数据会被处理，然后从内存中换出，以为其他数据腾空间。凭借现在可以持有数百 GB 内存内存的通用系统，我们现在可以将感兴趣的数据始终保留在内存中，而无需像以前那样换出数据。
- 处理器速度不再增长。尽管芯片的整体复杂度根据摩尔定律继续增加，但时钟频率在 3 GHz 左右达到平台期，多年来没有变化。
- 另一方面，每个插槽的核心数正在增加。现代 CPU 芯片的额外复杂性和功率正以每个插槽越来越多的核心（物理和虚拟的）的形式呈现。

后两项观察结果意味着，每个执行流的运行速度不会比几年前更快，但你有更多潜在的并行执行流可供使用。

SQL Server 的内存优化事务功能与传统的 SQL Server 实现方式不同。一方面，它是 SQL 引擎的完全集成部分；另一方面，它是一个全新的执行引擎。那么，什么是内存优化事务？是什么让它与 SQL Server 的其他部分与不同？

## 数据始终在内存中

在内存优化事务环境中，数据始终在内存中。没有将数据子集换入或换出内存的概念。当一个表被指定为内存优化时，它的数据行永远不会被换出内存。尽管这是行为上的重大变化，但它只是开始。毕竟，如果你在传统数据库服务器上有足够的内存，你没有理由将页面从内存中换出。然而，你可以利用这些信息来明智地操作。

因为你知道永远不需要将数据换入或换出内存，所以你可以消除引擎的许多结构和功能。例如，页面（Pages）是用于促进数据子集在内存内外之间移动的结构。由于该系统永远不会这样做，你可以完全消除页面。如图 10-1 所示，内存优化表中内存中行的数据结构简单来说就是列本身以原生格式存储的数据，并带有几个用于可见性和隔离性目的时间戳（我将在“隔离性”部分中详细介绍）以及一个用于索引链的指针数组。

| 8 字节 | 8 字节 | 4 字节 | 2 字节 | 2 个索引链指针 |
| :--- | :--- | :--- | :--- | :--- |
| 开始时间戳 | 结束时间戳 | 语句 ID | 索引计数 | 填充 |
| | | | | | 行头 24 字节 + (8 字节 * 索引计数) |

**图 10-1** 内存优化表的行格式。

开始和结束时间戳对于维护事务隔离一致性至关重要。开始时间戳标记了行创建的时间。任何在此时间戳之前启动的事务都不会看到此版本。结束时间戳标记了该行被逻辑删除的时间。在此时间之前但在开始时间戳之后启动的事务将继续看到该行，以提供一致的视图。

你还可以省去大量的大量的基础设施，这些基础设施用于跟踪哪些页面在内存中、哪些页面在缓冲区池中、缓冲区池中的页面可能在哪里、页面的内存副本是否已被修改（使其变为“脏”数据）并需要最终将其刷到磁盘等。所有这些管理都不再发生了，这是一个巨大的节省。

这意味着针对内存优化表的事务永远不会因为等待 IO 将所需的页面调入内存而返回调度器队列。

## 原生编译 (Native compilation)

这是 SQL Server 内存优化事务的另一项创新。考虑到处理器速度的停滞以及尽可能利用每个 CPU 周期的需求，内存优化事务系统提供了一个选项，即对存储过程进行原生编译。那么，这意味着什么？

首先是前提条件：这种功能只有在你创建存储过程且该存储过程不访问传统的基于行或基于列的表时才有效。可以访问的表只有内存优化表。此外请注意，原生编译环境的 T-SQL 功能范围较窄，至少在当前版本中，如果你遇到缺失的功能，可能需要采取一些变通方案。某些变通方案是细微的，对性能没有实际成本。另一些则在实现复杂性或性能影响方面可能是不可接受的。

现在是回报：当你创建一个原生存储过程时，T-SQL 源码通过 SQL 查询优化器被转换为 C 代码，这些 C 代码能够直接访问内存结构。这些 C 代码被编译并构建成动态链接库 (DLL)，并像创建表一样动态加载到 SQL 进程中。

所有这一切的结果是，当你执行原生编译存储过程时，与其查找 T-SQL 源码并执行一系列带有许多上下文切换的解释型 SQL 操作，原生编译存储过程只是引擎上下文的一个简单函数调用。它甚至没有上下文切换。如前所述，永远不会因为等待锁或闩锁而等待 IO。简而言之，当原生编译存储过程开始执行时，它通常会一直运行到完成而不会被阻塞。这使得引擎极其高效。

## 无锁无闩锁架构

该架构的另一个方面是它被设计为完全无锁无闩锁的。记得我之前讨论过吗，现代处理器每个插槽的核心数正在增加，为了利用处理能力，你需要启用越来越多的并行执行线程。

织闩（Latches）用于保护如页之类的物理结构。正如我提到的，你不会对内存优化型数据使用织闩，因此你不需要页织闩。此外，所有的行结构和索引结构都设计为无锁，并使用了乐观并发模型。

大多数数据库系统（包括 SQL Server 在内）都是基于悲观并发模型设计的。从根本上说，该系统假设如果两个线程访问相同的数据结构，可能会发生导致问题的冲突。为了避免这种情况，采用悲观并发设计的系统会加锁：第一个尝试访问的线程将获得该结构的锁，而其他具有冲突请求的线程将会被阻塞，直到第一个线程完成。这种模型在保证一致性方面表现良好，但产生了一个遗憾的副作用，会导致大量的线程在等待织闩释放。SQL Server 开发团队在开发 SQL 引擎时还发现，惊人大量的 CPU 周期仅仅浪费在了获取和释放锁以及织闩上，即使在没有冲突或等待的情况下也是如此。

相反，乐观并发假设在大多数情况下不会发生导致不一致的冲突，因此你无需阻塞线程即可运行。并发性通过检查实际的写-写冲突来保证，如果发现冲突，则让尝试修改数据的第二个线程失败。我将在“提交验证（Commit validation）”部分详细介绍这一点。

结果是，你永远不会有线程因等待锁或织闩释放而阻塞。因此，如果应用程序设计得当，你可以让许多执行线程并行运行，充分利用系统中的所有核心。

## SQL Server 集成

与其他内存数据库产品相比，SQL Server 内存数据库（In-Memory OLTP）最独特的特征可能是它与核心数据库引擎完全集成。你可以以表为单位，决定哪些表应该是内存优化的，哪些应该保留在传统的行存储中，哪些应该放在列存储中。在这个世界里，你拥有完全的控制权，可以根据用途和性能需求将每部分数据放在最合适的存储格式中。

因此，你将拥有一个包含内存优化型表、传统表和聚集列存储表的数据库。你需要考虑跨越这些边界的一些影响，我们将讨论这些问题。从积极的一来说，你拥有相同的工具来辅助你的调优工作。

数据库不仅可以拥有存储类型的混合（传统的行存储、内存优化型表和列存储），而且包含此类混合的表的行为也像任何 SQL 表一样。相同的语法适用，使用相同的连接方法，并使用相同的工具和实用程序。AlwaysOn 集群和可用性组（Availability Groups）可以正常工作。正如我们的早期采用者之一所说：“如果你熟悉 SQL，你就熟悉 Hekaton。”与迁移到不同的平台相比，现有知识是一个巨大的优势，因为你不需要学习一套全新的系统来管理你的数据。

## 创建内存优化型表

要在数据库中创建内存优化型表，数据库必须首先包含一个特殊用途的内存优化数据文件组（Memory Optimized Data filegroup）。该文件组将包含持久化在内存表中的数据。其语法与 FILESTREAM 组类似，区别在于 `CONTAINS MEMORY_OPTIMIZED_DATA` 选项。在 AdventureWorks 数据库中添加内存优化数据文件组的代码如列表 10-1 所示。

### 列表 10-1 创建内存优化数据文件组和容器

```
ALTER DATABASE AdventureWorks2014

ADD FILEGROUP AdventureWorks2014_mod CONTAINS MEMORY_OPTIMIZED_DATA;

GO

ALTER DATABASE CURRENT ADD FILE

(NAME='AdventureWorks2014_mod',

FILENAME='Q:\MOD_DATA\AdventureWorks2014_mod')

TO FILEGROUP AdventureWorks2014_mod);
```

注意，你可以添加多个容器（使用 `ADD FILE` 语法，就像你对 FILESTREAM 容器一样）。内存优化型表中的所有数据必须在数据库恢复并上线之前读取到内存中，因此你需要考虑数据从存储器读取的速度。拥有多个容器将通过允许引擎并行处理所有容器来加快数据库的启动。为了进一步优化启动，你应该将检查点文件（checkpoint files）的 IO 负载分分布到多个存储设备上。

在创建内存优化数据文件组后，你可以继续创建内存优化型表。你会发现，创建此类表的语法（如列表 10-2 所示）与创建任何表没有显著区别，除了某些特定的关键字。

### 列表 10-2 创建内存优化型表

```
USE AdventureWorks2014;

GO

CREATE Table Sales.ShoppingCartItem_inmem

(

ShoppingCartItemID IDENTITY(1,1) NOT NULL,

ShoppingCartID nvarchar(50) NOT NULL,

Quantity INT NOT NULL CONSTRAINT IM_ShoppingCartCartItem_Quantity DEFAULT (1),

ProductID INT NOT NULL,

DateCreated datetime2(7) NOT NULL,

CONSTRAINT IM_ShoppingCartCartItem_DateCreated DEFAULT (sysdatetime()),

ModifiedDate datetime2(7) NOT NULL,

CONSTRAINT IM_ShoppingCartCartItem_ModifiedDate DEFAULT (sysdatetime()),

CONSTRAINT PK_ShoppingCartCartItem_ShoppingCartItem_ShoppingCartItemId PRIMARY KEY NONCLUSTERED CLUSTERED

HASH (ShoppingCartItemId) WITH (BUCKET_COUNT = 1048576),

INDEX IX_DateCreated NOT CLUSTERED (DateCreated ASC),

INDEX IX_ModifiedDate NOT CLUSTERED (ModifiedDate ASC),

INDEX IX_ProductID NOT CLUSTERED (ProductID) WITH (BUCKET_COUNT = 1048576)

) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY);
```

### 在内存优化型表中创建索引

内存优化型表中的索引与你使用的任何其他索引相同。在其他方面，它们的行为有所不同。

### 聚集使用非聚集

传统表使用聚集或非聚集索引。内存优化型表，实际上并没有聚集与非聚集索引的概念，因为内存优化型表上的所有索引都被视为非聚集索引。

### 非聚集索引

内存优化型表主要的索引类型是非聚集索引。这些索引有时被称为范围索引，因为与哈希索引不同，它们可以使用不等式谓词高效地检索行范围，而不是哈希索引所设计的键值查找。当然，对于我们更熟悉的传统的 B 树，非聚集索引也可以用于精确键查找，但在其使用场景下速度不会像哈希索引那样快。

创建非聚集索引的语法简单如下：

```
IX_Date NONCLUSTERED (DateCreated ASC)
```



你可以在之前所示表定义的结尾找到此片段的上下文。

注意，内存优化型表中的所有索引都是作为表的一部分创建的，而不是单独添加。

### 非聚集索引结构

内存优化型表上的非聚集索引与传统的 B 树索引不同，其 BW-Tree 结构赋予了它们无锁无栅门的特性，并具有可变大小且紧凑无空隙的页面。

传统的 B 树索引不仅在插入单个条目时受到大量的锁定，在索引需要重新排列时也是如此。当页面需要拆分或合并时，树的范围会被锁定。BW-Tree 索引能够在不锁定结构的情况下插入页面，因为它们创建新页面并简单地切换指针到使用页面映射表。通过交换页面内容，可以让你无需为未来的插入留出空间而创建大型空页。相反，你只需要创建一个带有额外条目的页面新版本，并替换之前的页面版本。

这些特性使得 BW-Tree 这个名字得以诞生。当发明它的团队在寻找名称时，他们讨论了这些属性：无锁、无栅门、闪存友好等。有人注意到，这听起来就像该设计所体现的当前行业术语列表。BW-Tree（buzzword tree）便由此命名。

页面映射表是使这些索引在不需要锁或栅门的情况下运行的关键。该表在索引内部逻辑页面 ID 与页面的物理位置之间提供了一个间接层。与传统的索引页不同（在传统情况下，页面的标识和物理位置是一一对应的绑定关系），页面映射表让你能够通过交换指向索引页新副本的指针，有效地替换索引页的内容，而不会中断任何引用它的页面。这在图 10-2 中所示。

![](img/bdc38aa36f6e2987d913ee5381474711_702_0.png)

图 10-2 非聚集索引。

BW-Tree 结构本身页面之间的链接全部以逻辑页面 ID 的形式存在。这些通过页面映射表进行查找。如果你需要更新索引中的页面（以处理页面拆分或在叶节点中插入新值），你只需构建页面的新版本，并更改页面映射表中的条目指向该页的新版本。假设你需要修改索引页 101。你只需创建一个页面 101 的新副本并将其命名为 101，并带有新内容。你更改映射表中页面 101 的指针以指向该新副本。所有对页面 101 的引用仍然指向页面 101——你只是原子地将指向逻辑页面编号 101 的物理页面交换为了另一个物理页面。

索引页中的每个条目都有一个键值（在非叶页中，这是索引下一层页面中该范围的高端）和一个有效负载。对于非叶页，有效负载是一个页面 ID。对于叶页，有效负载是一个指向匹配键值的实际行或多行的指针。

叶页之间以升序相互链接，每个页面都将链接到具有更高键值分组的页面。对于降序，索引将链接到具有更低键值分组的叶页。你应该理解，与普通 B 树索引中不同，这些链接不是双向的。这意味着如果索引是按一个方向定义的，在不通过排序的情况下，你无法以相反顺序检索行，这你稍后会看到。同样，这些链接是通过页面 ID 而非指针完成的，因此你可以替换页面内容而不会让更改扩散到整个结构中。叶节点的链接使得扫描变得高效得多——一旦到达扫描起点，你只需沿着叶页向下直到到达扫描结束点。

与大多数 B 树结构一样，这些索引可以根据需要增长和缩小。这与哈希索引的情况不同，哈希索引需要根据表预期的基数预设索引大小，正如我在讨论哈希索引时将会看到的。

### 非聚集索引行为

内存优化表上的非聚集索引的行为与传统的非聚集/B 树索引类似，但正如后续节所述，存在一些关键区别。

#### 索引是无栅门的

与传统的 B 树索引不同，内存优化表的索引结构使用了基于 BW-Tree 的略有不同的结构。这种结构使得这些索引可以在没有任何锁或栅门的情况下运行。因此，线程可以在索引中插入相邻行，即使导致页面拆分，也不会阻塞任何线程。这在很大程度上通过前述的页面映射表实现，它有助于原子化替换索引页的内容。

#### 索引是单向的

传统索引可以在任何方向产生扫描；然而，内存优化表中的非聚集索引只能向一个方向遍历。

### 哈希索引

创建哈希索引（在创建表本身时）的语法与之前讨论的非聚集索引语法相似，并摘自列表 10-2：

```sql
INDEX IX_ProdID NONCLUSTERED HASH (ProductID) WITH (BUCKET_COUNT = 1048576)
```

请注意这里增加了 `HASH` 关键字以及额外的子句 `WITH (BUCKET_COUNT = 1048576)`。这最后一个子句决定了形成哈希索引根的指针数组的大小。需要注意的是，在 SQL Server 2014 中，哈希索引一旦索引和表创建，无法调整大小。与非聚集索引不同，哈希索引无法动态调整大小，且一旦创建，桶数组的大小就无法更改。这种限制可能会产生巨大的性能影响，因此你需要仔细考虑该索引所属表最终将增长到多大。

#### 哈希索引行为

哈希索引有特定的用途，即优化精确查找。如你所见，它们在执行此类操作时极其高效。由于哈希索引的数据结构在内存中，整个查找过程直接转换为跟随内存指针。

然而，如果你正在进行全扫描，系统必须访问每个哈希桶（无论其是否为空），对于每个填充的桶，它将遵循具有相同桶的行的索引链指针。

与 B 树不同，哈希索引内部的数据没有固有的顺序。这产生了几个实际影响。第一是没有方法利用索引结构来高效地找到一个值范围。如果查询谓词没有得到精确值，结果查询将执行全表扫描，过滤出给定值之间的行。

这意味着你无法利用索引结构来返回一个有序集合。考虑以下查询：

```sql
SELECT ProductID, Name FROM Production.Product Order BY ProductID;
```

在对 AdventureWorks Production.Product 表上运行时，此代码将产生图 10-6 所示的执行计划：

![](img/bdc38aa36f6e2987d913ee5381474711_706_0.png)

图 10-6 传统索引的查询计划。

尽管你指定了结果应按 `ProductID` 排序，但并没有排序阶段，因为 B 树索引本身是有序的。相比之下，如图 10-7 所示，当对该表的内存版本（在 ProductID 上有哈希索引）运行相同的查询时，你会看到以下执行计划：

```sql
SELECT ProductID, Name FROM Production.Product_inmem ORDER BY ProductID;
```

![](img/bdc38aa36f6e2987d913ee5381474711_706_0.png)

图 10-7 哈希索引的查询计划。

注意，哈希索引需要进行排序，因为哈希索引的扫描不会自动产生有序结果。

#### 哈希索引的应用

哈希索引在单点查找中表现出色，当你有一个精确的键用于查找。在这种情况下，查找只需将键通过哈希函数，然后跟随指针指向数据。如果多行哈希到同一个桶，初始指针将带你进入第一行，然后跟随每行中的后续指针进入所有哈希到该桶的记录链中的下一行。

大多数 OLTP 系统在其性能最关键的逻辑中使用单行或少数行的精确键查找模式。例如：库存更新、需要查找某个零件号并更改现有数量的计费系统、每天记录数百万手机通话记录，或者在业务过程中，单个订单及其行项目被反复引用的订单系统。在所有这些场景中，你可以看到，如果使用针对这种访问模式优化的索引结构，这些过程将大大加速。

#### 注意事项

尽管哈希索引在使用得当时速度很快，但在某些情况下它们的效率会低得多并导致性能问题。我将介绍几个场景并解释问题产生的原因。

**桶数配置不当**：在创建哈希索引时，你必须指定一个桶数。桶数理想情况下应接近表中预期唯一值数量的 1–2 倍。例如，如果你在 `part_no` 上有一个索引，并预计有 10,000 个唯一零件号，你指定的 `BUCKET_COUNT` 为 10,000–20,000。如果你使用的桶数为 100，那么 10,000 个零件号将分散在所有 100 个桶中。平均而言，每个桶将包含 100 行。这意味着，原本可能只需要一次指针查找的查询，在找到正确行之前需要遍历 50 行。如果差距进一步扩大，性能影响会更加严重。

哈希桶大小过小的另一个影响与插入有关。在哈希桶发生冲突的哈希索引中插入行时，系统必须找到插入点。如果值是重复的，这种影响不大，因为你只需插入链的头部。然而，如果存在大量哈希冲突但没有许多重复值，你就需要遍历重复链以为此新值找到合适的位置。列表按键值排序，因此所有重复键的条目都分组在列表中。新的重复值插入在具有相同键值的组的开头。

以以下两个表为例，如列表 10-3 所示。

##### 列表 10-3

（注：原文此处未提供 Listing 10-3 具体内容，仅为引用）

在此处你可以看到，第一个表没有空桶，平均哈希冲突链长度为 12,500。这意味着当该表填满时，插入操作平均需要扫描 6,000 个条目才能找到合适的插入点。相比之下，第二张表有近 200 万个空桶，平均链长度为 1。通过此查询，你可以看到空桶百分比为 30%，平均链长度为个位数。

如果桶的大小过大，影响并不十分严重，因此倾向于让空间冗余总是更好的。过度冗余会产生两种影响：

- 首先，哈希桶是一个 8 字节的指针，会消耗内存，因为数量过大的哈希桶计数会导致内存浪费。由于每个索引只对应哈希表，这通常不是一个显著因素。
- 第二种影响体现在查询导致表扫描时。表扫描是通过访问正在扫描的索引中的每个桶来实现的。优化器会选择桶数量最低的哈希索引进行扫描，因为这样可以最小化需要访问的桶的数量。如果过大的哈希表中 90% 的桶都是空的，查询仍然需要访问每个桶，这将大幅减慢查询速度。如果你遵循我的建议，在表上至少建立非聚集索引，这将不是问题，因为优化器会选择 BW-Tree 聚集索引进行扫描。

**不包含所有键列的查询谓词**：哈希函数是一个数学函数，它接受所有键列作为输入并在哈希数组中产生偏移量。如果查询谓词没有提供所有列，该函数无法工作，因为缺少所有必要的输入。当这种情况发生时，哈希索引将无法使用。其结果通常是全表扫描，因此此错误会使你从直接指针查找退变为全表扫描，这对性能产生灾难性的影响。

遗憾的是，这种情况很容易掉入，因为传统的 B-tree 索引能够选择索引的前导列，并且可以使用索引寻址的计划。当对哈希索引运行此类查询时，如果查询谓词未提供哈希索引中的所有键，结果将是表扫描。这很容易导致这样的情况：当从传统表直接转换为内存优化表时，如果原始查询仅使用前导列，性能可能会下降。在这种情况下，指定一个列数较少的索引，或者为无法指定原始索引所有键列的查询添加额外索引会是更好的选择。你可以在列表 10-4 中看到这种方法，它产生了图 10-8 所示的查询计划。

##### 列表 10-4 仅指定前导列的查询结果示例

```sql
CREATE TABLE dbo.IndexExample (
    ID INT NOT NULL IDENTITY(1,1) PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1024),
    C1 INT NULL,
    C2 INT NULL,
    C3 INT NULL,
    C4 INT NULL,
    -- 针对列 C1 & C2 的非聚集 HASH 索引
    INDEX IX_HashCount NONCLUSTERED (C1, C2) WITH (BUCKET_COUNT = 1048576),
    -- 针对列 C3 & C4 的非聚集 B-Tree 索引
    INDEX IX_NonClusteredExample NONCLUSTERED (C3, C4)
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);
GO

INSERT INTO dbo.IndexExample (C1, C2, C3, C4) VALUES (1,1,1,1);
INSERT INTO dbo.IndexExample (C1, C2, C3, C4) VALUES (2,2,2,2);
GO

-- 第一个查询使用哈希索引的前导列
SELECT C1, C2 FROM dbo.IndexExample WHERE C1 = 1;

-- 第二个查询使用 B-Tree 索引的前导列
SELECT C1, C2 FROM dbo.IndexExample WHERE C3 = 1;
```

```sql
SELECT * FROM [IndexExample] WHERE [C1]=@1
```

![](img/bdc38aa36f6e2987d913ee5381474711_711_0.png)

这是当你使用一个包含前导列但未包含哈希索引所有键列的谓词查询哈希索引时所得到的计划。请注意，尽管表上有一个包含该列的索引，但你仍然在进行全表扫描和过滤，而不是利用索引。

与图 10-8 中的上一个示例不同，当你仅用前导列（而非所有列）查询 BW-Tree 索引时，仍然可以使用索引进行寻址并避免全扫描。这是我们熟悉的行为，并导致了图 10-9 中的计划。

```sql
SELECT * FROM [IndexExample] WHERE [C3]=$1
```

![](img/bdc38aa36f6e2987d913ee5381474711_712_0.png)

这清楚地说明，仅仅将现有的磁盘表和应用程序直接转换为内存优化表，可能会导致意想不到的负面性能结果。内存的速度通常无法弥补扫描百万行而非直接索引寻址的差异。

##### 列表 10-5 优化器根据查询选择索引的示例

```sql
CREATE TABLE dbo.Table3 (
    C1 int NOT NULL,
    C2 int NOT NULL,
    C3 int NOT NULL,
    C4 int NOT NULL,
    PRIMARY KEY NONCLUSTERED HASH (C4) WITH (BUCKET_COUNT = 2097152),
    INDEX HASH_IDX NONCLUSTERED HASH (C1, C2, C3) WITH (BUCKET_COUNT = 2097152),
    INDEX NC_ID_IDX NONCLUSTERED (C1, C2, C3)
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);
GO

INSERT dbo.Table3 VALUES (1,1,1,1), (1,1,1,2), (1,1,1,3);
GO
```



-- 精确键查找将由哈希索引满足
SELECT C1, C2, C3 FROM dbo.table3 WHERE C1 = 1 AND C2 = 1 AND C3 = 1;

-- 范围谓词查询将由 BW-Tree 索引满足
SELECT C1, C2, C3, C4 FROM dbo.table3 WHERE C1 = 1 AND C2 = 1 AND C3 BETWEEN 0 AND 2;

-- 前导列查询将由 BW-Tree 索引满足
SELECT C1, C2, C3, C4 FROM dbo.table3 WHERE C1 = 1 AND C2 = 1;

图 10-10 展示了第一个查询的查询计划，显示谓词提供了所有键列且没有 `ORDER BY` 子句，优化器选择了 `HASH_IDX`。

![](img/bdc38aa36f6e2987d913ee5381474711_713_0.png)

**FIGURE 10-10** 所有键列精确匹配的查询计划。

下一个计划（可以在图 10-11 中看到）显示，当相同谓词的第三个元素表示为范围（`BETWEEN`）时，优化器将选择 BW-Tree 索引。

![](img/bdc38aa36f6e2987d913ee5381474711_713_1.png)

**FIGURE 10-11** 范围谓词查询的计划。

最后的查询如图 10-12 所示，还将生成一个使用非聚集索引的计划，以查找包含某些前键列的谓词条件的行。

![](img/bdc38aa36f6e2987d913ee5381474711_714_0.png)

**图 10-12** 具有某些前键列的查询计划。

## 执行环境

所有涉及内存优化表的事务至少在部分是在与经典 SQL 事务不同的环境中执行的。正如我讨论过的，内存内 OLTP（In-Memory OLTP）系统是一个独特的“引擎中的引擎”。内存内 OLTP 引擎具有一些独特的属性和语义：

- 内存优化表始终在内存中，这意味着事务不会因为 I/O 而阻塞；优化器的代价估算略有不同，因为它考虑了全内存访问；而且当然，你需要留出足够的内存来存放你的内存优化数据。
- 内存优化表上的事务均使用无锁语义完成。这通常是有优势的；然而，也有一些你需要注意的场景。

根据查询的执行方式，有两种不同的环境可以使用。两者中简单的一种被称为查询互操作（query interop）。在这种情况下，查询处理通过 SQL Server 的层级作为传统查询进行，并使用标准的查询引擎。然而，这些查询并不是使用查询引擎从缓冲区池（或如果页面当前不在缓冲区池中，则从磁盘）检索数据，而是直接访问内存内 OLTP 环境中的数据。

第二种执行环境是通过原生编译存储过程（natively compiled procedures）。该环境具有最高级别的性能提升和执行效率；然而，它带来了更多的限制，无论是在 T-SQL 表面积方面还是在事务语义方面。

## 查询互操作

查询互操作执行环境用于即时性 SQL 查询以及传统的存储过程和其他 T-SQL 模块。你可以从触发器、用户定义函数 (UDFs) 等其他模块引用内存优化表。它无非仅仅是针对一个或多个内存优化表的 T-SQL 查询。在这个环境中，你为了适应内存内 OLTP 环境需要做的工作最少，因为你不需要将存储过程迁移到限制更多的编译表面积上。这意味着没有工作要做，但意味着涉及的迁移工作将显著减少且更简单。

那么，在使用查询互操作时需要考虑哪些因素？

## 隔离

内存内 OLTP 目前提供一组受限的隔离级别。快照（Snapshot）是默认隔离级别，并支持重复读（Repeatable Read）和序列化（Serializable）隔离级别。内存优化表不支持读取未提交（Read Uncommitted）、已提交（Read Committed）和已提交快照（Read Committed Snapshot）隔离级别。由于隔离级别至少在事务级别设置，因此涉及内存优化表的事务不能使用任何不支持的隔离级别。整个事务必须在快照、重复读或序列化隔离级别下运行。

在传统的 SQL Server 事务中，默认且常用的隔离级别是已提交（Read Committed）。已提交隔离级别指定事务将只看到提交的数据，而不会看到任何可能被回滚的数据。如果此类事务遇到一行已修改但尚未提交的行，事务将阻塞，直到更新以某种方式得到解决。这在内存内 OLTP 的无锁环境中是不可能发生的。

## 死锁与阻塞

以下示例演示了传统环境与内存环境之间的区别。

### 表 10-2 传统表死锁示例

| 步骤 | 事务 1 | 事务 2 |
| :--- | :--- | :--- |
| 设置 | --设置表<br>`USE AdventureWorks2014;`<br>`GO`<br>`IF (OBJECT_ID('dbo.T1') IS NOT NULL)`<br>`DROP TABLE dbo.T1;`<br>`CREATE TABLE dbo.T1`<br>`(C1 INT NOT NULL PRIMARY KEY,`<br>`C2 INT NOT NULL);`<br>`GO`<br>`INSERT INTO dbo.T1(C1,C2) VALUES (1,1),(2,1);`<br>`GO` | | |
| 1 | `BEGIN TRANSACTION;` | | |
| 2 | | `BEGIN TRANSACTION;` | |
| 3 | `UPDATE dbo.T1 SET C2 = 2 WHERE C1 = 2;` | | |
| 4 | | `UPDATE dbo.T1 SET C2 = 3 WHERE C1 = 1;` | |
| 5 | `SELECT C2 FROM dbo.T1 WHERE C1 = 1;` | | |
| 6 | | `SELECT C2 FROM dbo.T1 WHERE C1 = 2;` | |
| 7 | `COMMIT;` | | |
| 8 | | `COMMIT;` | |

在这个示例中，你有一个简单的表和两个访问该表的事务：

- 在步骤 1 和 2 中，事务 1 和事务 2 分别开始。
- 在步骤 3 中，事务 1 更新 `C1 = 2` 的行，获取该行的排他 (X) 锁。
- 在步骤 4 中，事务 2 更新 `C1 = 1` 的行，获取该行的 X 锁。
- 在步骤 5 中，事务 1 从 `C1 = 1` 的行进行查询，并在事务 2 的 X 锁后阻塞。
- 在步骤 6 中，事务 2 从 `C1 = 2` 的行进行查询，并在事务 1 的 X 锁后阻塞。

这形成了一个经典的死锁，其中其中一个事务将被选为受害者并被中止。

与此相反，表 10-3 显示了当在内存优化表上运行该序列时发生的情况。

### 表 10-3 内存优化表死锁示例

| 步骤 | 事务 1 | 事务 2 |
| :--- | :--- | :--- |
| 设置 | --设置表<br>`USE AdventureWorks2014;`<br>`GO`<br>`IF (OBJECT_ID('dbo.T1') IS NOT NULL)`<br>`DROP TABLE dbo.T1;`<br>`CREATE TABLE dbo.T1`<br>`(C1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1024),`<br>`C2 INT NOT NULL);`<br>`GO`<br>`INSERT INTO dbo.T1(C1,C2) VALUES (1,1),(2,1);`<br>`GO` | | |
| 1 | `BEGIN TRANSACTION;` | | |
| 2 | | `BEGIN TRANSACTION;` | |
| 3 | `UPDATE dbo.T1 SET C2 = 2 WHERE C1 = 2;` | | |
| 4 | | `UPDATE dbo.T1 SET C2 = 3 WHERE C1 = 1;` | |
| 5 | `SELECT C2 FROM dbo.T1 WHERE C1 = 1;` | | |
| 6 | | `SELECT C2 FROM dbo.T1 WHERE C1 = 2;` | |
| 7 | `COMMIT;` | | |
| 8 | | `COMMIT;` | |

在这个示例中，你有一个简单的表和两个访问该表的事务：

- 在步骤 1 和 2 中，事务 1 和事务 2 分别开始。
- 在步骤 3 中，事务 1 更新 `C1 = 2` 的行。
- 在步骤 4 中，事务 2 更新 `C1 = 1` 的行。
- 在步骤 5 中，事务 1 从 `C1 = 1` 的行进行查询，读取事务 2 修改的版本（无阻塞）。
- 在步骤 6 中，事务 2 从 `C1 = 2` 的行进行查询，读取事务 1 修改的版本（无阻塞）。
- 在步骤 7 中，事务 1 提交成功。
- 在步骤 8 中，事务 2 尝试提交，但会因验证失败而中止（因为它读取的 `C1 = 2` 的行已被事务 1 修改），错误消息类似于：**Msg 41302, Level 16, State 110, Line 8: The current transaction attempted to update a record that has been updated since this transaction started. The transaction was aborted.**

这演示了内存优化表无锁特性：没有死锁，但会有提交时的验证失败。

## 列表 10-6 验证失败的重试逻辑

```sql
DECLARE @retry INT = 10;
WHILE @retry > 0
BEGIN
    BEGIN TRY
        BEGIN TRANSACTION;
            -- 业务逻辑
            UPDATE dbo.T1 SET C2 = 3 WHERE C1 = 1;
        COMMIT TRANSACTION;
        SET @retry = 0; -- 成功则退出循环
    END TRY
    BEGIN CATCH
        IF XACT_STATE() <> 0
            ROLLBACK TRANSACTION;
        
        -- 检查是否为提交依赖失败 (错误号 41302, 41305, 41325, 41301 等)
        IF ERROR_NUMBER() IN (41302, 41305, 41325, 41301)
        BEGIN
            SET @retry -= 1;
            -- 可选：短暂延迟后重试
            -- WAITFOR DELAY '00:00:00.001';
        END
        ELSE
        BEGIN
            THROW; -- 非重试错误，直接抛出
        END
    END CATCH
END
IF @retry = 0 AND XACT_STATE() <> 0
    THROW 50001, '重试次数耗尽，事务失败', 1;
```



# 根据工作负载调整重试次数

```sql
DECLARE @retry INT = 10;

WHILE (@retry > 0)
BEGIN
    BEGIN TRY
        EXEC usp_my_native_proc @param1, @param2, ...;

        -- BEGIN TRANSACTION
        -- COMMIT TRANSACTION

        SET @retry = 0;
    END TRY
    BEGIN CATCH
        SET @retry -= 1;

        IF (@retry > 0 AND ERROR_NUMBER() IN (41302, 41305, 41325, 41301, 12055))
        BEGIN
            -- 这些错误无法恢复并继续。事务必须
            -- 回滚并完全重试。
            -- 原生存储过程在抛出错误时会自动回滚，因此在这种情况下跳过
            -- 回滚。

            IF XACT_STATE() = -1
                ROLLBACK TRANSACTION;

            -- 如果存在高频率的写入冲突 (41302)，则使用延迟
            -- 延迟长度取决于冲突事务
            -- 的典型持续时间

            WAITFOR DELAY '00:00:00.001';
        END
        ELSE
        BEGIN
            -- 在此处为其他错误条件插入自定义错误处理
            -- 如果这不是符合条件的错误条件，则抛出异常

            THROW;
        END
    END CATCH;
END;
```

# 跨数据库查询

在 `SQL Server 2014` 中，你无法执行访问内存优化表以及另一个数据库中任何表的查询，无论该数据库是在同一实例中还是另一个实例中。然而，你可以在跨数据库事务中使用内存优化变量。

# 并行性

任何方式访问内存优化表的事务都不会使用并行计划。这是 `SQL Server 2014` 的一个限制，可能会在未来的版本中移除。这些事务的实际并行度（`MAXDOP`）实际上为 1。这会对查询性能产生严重影响，在某些情况下，这可能会抵消内存优化表的性能优势。例如，如果你正在将内存优化表与具有聚类列索引（`Clustered Column Index`）的表进行连接，你可能会认为这些在各自领域中极快的技术会协作良好。遗憾的是，列存储的性能设计是基于高程度的并行性的。列存储能够利用系统的所有核心在极短时间内对海量数据集进行扫描。当引入内存优化表进行查询时，查询的整体并行性降到 1，列存储索引的性能受到严重影响。

这是内存内存 `OLTP`（`In-Memory OLTP`）查询当前并行性限制对性能影响的一个极端示例，但在许多其他情况下，可能仍然能感觉到这种影响，尽管它可能并不明显。坦率地说，通过查看基于磁盘的查询的计划并与内存优化查询的计划进行比较，很容易检测出何时是性能问题。

你可以从第一个计划中看到并行操作符在整个计划中被一致使用，而在来自内存优化查询的第二个计划中，该计划完全基于串行操作符。

你也可以查看或搜索查询的 `XML` 表示中的 `<RelOp>` 标签并寻找 `Parallel` 属性：

```xml
<RelOp AvgRowSize="121" EstimateCPU="0.27821" EstimateIO="0" EstimateRebind="0" EstimateRewinds="0" EstimatedExecutionMode="Row" EstimateRows="22475.9" LogicalOp="Inner Join" NodeId="4" Parallel="true" PhysicalIO="10" EstimatedTotalSubtreeCost="29.8961">
```

在带有内存优化表的查询中，它如下：

```xml
<RelOp AvgRowSize="90" EstimateCPU="2.51833" EstimateIO="0" EstimateRebind="0" EstimateRewinds="0" EstimatedExecutionMode="Row" EstimateRows="22475.9" LogicalOp="Inner Join" NodeId="4" Parallel="true" PhysicalIO="10" EstimatedTotalSubtreeCost="29.8961">
```

注意，在内存优化表的情况下，由于事务 2 的更新不会完成，`C2` 的值将是事务 1 更新后的值 2。在传统表的情况下，事务 2 最终会成功，因此 `C2` 的最终值将是 3。

为了处理这些提交验证错误，编写事务时应使用与处理死锁重试相同的逻辑，如列表 10-6 所示。

# 基数与统计信息

在 `SQL Server 2014` 中，当对内存优化表进行统计操作时，引擎不会像传统表那样使用采样。相反，它将执行全表扫描。虽然这通常会提供更准确的结果，但耗时更长，可能会导致某些干扰。

# 统计信息与原生存储过程

由于原生存储过程在编译成 `DLL` 之前通过 `SQL Server` 进行优化，因此它们不会随数据而改变。在内存优化 `OLTP` 环境之外，更改统计信息会触发重新编译，但对于原生存储过程则不会。

> **注意**：在设置新的内存优化表时，最好在创建任何原生存储过程之前加载数据。这样优化器就可以处理数据，存储过程也能获得优化计划。

如果被原生存储过程访问的表内容发生了足以导致性能下降的变化，可能需要删除并重新创建存储过程，以强制其根据当前的统计信息进行重新编译。

# ATOMIC 块

原生存储过程要求由恰好一个原子块组成。它必须封装存储过程中所有的 `T-SQL` 逻辑。

`Atomic` 块是 `SQL Server 2014` 引入的新概念。它代表一组保证作为一个单元原子成功或失败的语句。`ATOMIC` 块与 `SQL` 事务的交互方式如下：

- 如果存在当前的 `SQL` 事务，`ATOMIC` 块将创建一个保存点并加入现有事务。
- 如果没有当前事务，`ATOMIC` 块将创建一个范围为块本身的事务。
- 如果块抛出异常，则整个块将进行回滚。
- 如果块成功，它创建的保存点将被提交，如果它创建了自己的事务，则该事务将被提交。

# 原生编译存储过程

如前所述，原生编译的存储过程执行效率极高，因为它们被预编译为 `DLL` 并加载到引擎上下文中。请注意，在用于执行解释器查询的解释器环境（或不访问内存优化表的存储过程）与原生编译环境之间进行转换会产生一些开销。对于极少量的逻辑（例如单语句事务），你可能会发现直接在解释器中执行查询的性能会更好。然而，你越能在原生存储过程的上下文中执行越多的逻辑，你获得的益处就越明显。

为了充分利用原生编译存储过程的性能，你应该尝试在每次调用原生存储过程时尽可能执行更多的业务逻辑。以表值参数（`TVP`）的形式将一组行传递给原生存储过程并在存储过程内部完全处理是一种常用方法。

# TVP（表值参数）

为了在原生编译存储过程内部进行访问，`TVP` 必须是内存优化的。它们具有超越原生编译存储过程的巨大优势。内存优化的 `TVP` 可以被传统的 `T-SQL` 存储过程像表一样进行使用，在许多情况下它们要高效得多，因为它们不需要在 `tempdb` 中实例化。创建内存优化表类型的语法可以参见前面提到的 `AdventureWorks` 示例，如列表 10-7 所示。

## 列表 10-7 内存优化的表类型

```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem AS TABLE(
  OrderQty SMALLINT NULL,
  ProductID INT NULL,
  SpecialOfferID INT NULL,
  LocalID INT NULL,
  INDEX IX_ProductID NONCLUSTERED HASH
  (
    ProductID
  ) WITH ( BUCKET_COUNT = 8),
  INDEX [IX_SpecialOfferID] NONCLUSTERED HASH
  (
    SpecialOfferID
  ) WITH ( BUCKET_COUNT = 8)
)
WITH ( MEMORY_OPTIMIZED = ON );
```

这随后用于原生存储过程的调用，如列表 10-8 所示。

## 列表 10-8 在原生存储过程使用表值参数

```sql
-- Table Valued Parameters
-- 如果对象存在，则删除旧对象

IF (OBJECT_ID('Sales.usp_InsertSalesOrder_inmem') IS NOT NULL)
  DROP PROCEDURE Sales.usp_InsertSalesOrder_inmem;

IF (TYPE_ID('Sales.SalesOrderDetailType_inmem') IS NOT NULL)
  DROP TYPE Sales.SalesOrderDetailType_inmem;

-- Memory Optimized Table Type
CREATE TYPE Sales.SalesOrderDetailType_inmem AS TABLE(
    OrderQty SMALLINT NOT NULL,
    ProductID INT NOT NULL,
    SpecialOfferID INT NOT NULL,
    LocalID INT NOT NULL,
    INDEX IX_ProductID NONCLUSTERED HASH
    (
        ProductID
        WITH (BUCKET_COUNT = 8),
    ),
    INDEX [IX_SpecialOfferID] NONCLUSTERED HASH
    (
        SpecialOfferID
        WITH (BUCKET_COUNT = 8)
    )
)
WITH (MEMORY_OPTIMIZED = ON);

GO

-- 使用原生过程使用表值参数
CREATE PROCEDURE Sales.usp_InsertSalesOrder_inmem
  @SalesOrderID INT OUTPUT,
  @DueDate DATETIME2(7) NOT NULL,
  @CustomerID INT NOT NULL,
  @BillToAddress INT NOT NULL,
  @ShipToAddress INT NOT NULL,
  @ShipMethod INT NOT NULL,
  @SalesOrderDetails Sales.SalesOrderDetailType_inmem READONLY,
  @Status TINYINT NOT NULL = 1,
  @OnlineOrderFlag BIT NOT NULL = 1,
  @PurchaseNumber NVARCHAR(25) = NULL,
  @AccountNumber NVARCHAR(15) = NULL,
  @SalesPersonID INT NOT NULL = -1,
  @TerritoryID INT = NULL,
  @CreditCardID INT = NULL,
  @CreditCardApprovalCode VARCHAR(15) = NULL,
  @CurrencyRateID INT = NULL,
  @Comment NVARCHAR(128) = NULL
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER
AS
BEGIN ATOMIC WITH
(
    TRANSACTION ISOLATION LEVEL = SNAPSHOT,
    LANGUAGE = N'us_english'
)
DECLARE @OrderDate DATETIME2 NULL = SYSDATETIME();
DECLARE @SubTotal MONEY NULL = 0;

SELECT @SubTotal = ISNULL(SUM(p.ListPrice * (1 - so.DiscountPct)), 0)
FROM Sales.SalesOrderDetails od
JOIN Sales.SpecialOffer_inmem so ON od.SpecialOfferID = so.SpecialOfferID
JOIN Sales.Product_inmem p ON od.ProductID = p.ProductID;

INSERT INTO Sales.SalesOrderHeader_inmem
(
    DueDate,
    Status,
    OnlineOrderFlag,
    PurchaseOrderNumber,
    AccountNumber,
    CustomerID,
    SalesPersonID,
    TerritoryID,
    BillToAddress,
    ShipToAddress,
    ShipMethodID,
    CreditCardID,
    CreditCardApprovalCode,
    CurrencyRateID,
    Comment,
    OrderDate,
    SubTotal,
    ModifiedDate
)
VALUES
(
    @DueDate,
    @Status,
    @OnlineOrderFlag,
    @PurchaseNumber,
    @AccountNumber,
    @CustomerID,
    @SalesPersonID,
    @TerritoryID,
    @BillToAddress,
    @ShipToAddress,
    @ShipMethodID,
    @CreditCardID,
    @CreditCardApprovalCode,
    @CurrencyRateID,
    @Comment,
    @OrderDate,
    @SubTotal,
    SYSDATETIME()
);

SET @SalesOrderID = SCOPE_IDENTITY();
END;
```

```sql
SET @SalesOrderID = SCOPE_IDENTITY();

INSERT INTO Sales.SalesOrderHeader_inmem
(
    DueDate,
    Status,
    OnlineOrderFlag,
    PurchaseOrderNumber,
    AccountNumber,
    CustomerID,
    SalesPersonID,
    TerritoryID,
    BillToAddress,
    ShipToAddress,
    ShipMethodID,
    CreditCardID,
    CreditCardApprovalCode,
    CurrencyRateID,
    Comment,
    OrderDate,
    SubTotal,
    ModifiedDate
)
SELECT
    @DueDate,
    @Status,
    @OnlineOrderFlag,
    @PurchaseOrderNumber,
    @AccountNumber,
    @CustomerID,
    @SalesPersonID,
    @TerritoryID,
    @BillToAddress,
    @ShipToAddress,
    @ShipMethodID,
    @CreditCardID,
    @CreditCardApprovalCode,
    @CurrencyRateID,
    @Comment,
    SYSDATETIME(),
    @SubTotal,
    GETDATE()
FROM Sales.SalesOrderDetails od
JOIN Sales.SpecialOffer_inmem so ON od.SpecialOfferID = so.SpecialOfferID
JOIN Sales.Product_inmem p ON od.ProductID = p.ProductID;
```



# 限制

- **外键约束**：由于不支持外键约束，我建议在应用程序逻辑中对与另一个表具有关键关系的表执行任何更新操作（插入、更新或删除），并在应用程序逻辑中进行验证，以避免数据不一致。这种验证可以在封装 `DML` 语句的包装函数中完成以验证一致性，也可以直接内联在应用程序代码中。

- **检查约束**：与外键约束一样，检查约束必须在应用程序代码中模拟，封装可能违反该条件的更新语句。

- **唯一约束**：这些是不直接支持的；然而，所有具有 `SCHEMA AND DATA`（架构和数据）持久性的内存优化表都必须有一个唯一主键索引。在许多情况下，该唯一索引将作为唯一约束。

- **ALTER TABLE**：SQL Server 2014 不支持以任何方式修改表。如果你想更改表或其索引的定义，需要卸载、删除、重新创建并重新加载该表。这包括对索引的任何更改或添加。

- **大对象 (LOB) 数据类型**（例如 `varchar(max)`、`image`、`xml`、`text` 和 `ntext`）：内存优化表所有列的总宽度最大为 8,062 字节。虽然你可以使用 `varchar(8000)`，但你不能使用 `(max)`，这将超过 8,060 字节的限制。当需要较大的 LOB 时，通常将列分成 800 字节的记录并在检索时重新组装，并将数据留在传统表中更快。关于如何操作的示例，你可以查看使用内存优化表的 ASP.NET Session 缓存的实现，该实现发布在 Codeplex 上：https://msftdbamples.codplex.com/releases/view/125282。

- **聚集索引**：与其说是一种限制，不如说是需要理解这些表的工作原理。内存优化表上的索引都是指向实际数据的指针，聚集索引和非聚集索引没有区别。行数据物理上并不存储在索引结构中，内存优化表上的所有索引是非聚集的（`NONCLUSTERED`）。它们可以被认为是覆盖索引，因为索引直接引用了表中的所有列。

# DML

SQL Server 2014 中的原生编译存储过程在可用范围方面存在一些限制，这可能需要变通方法。在某些情况下，这些限制表明存储过程可能最好留存在解释模式（`interp mode`）下运行。在许多情况下，可以将过程拆分为一个解释模式下的包装过程和一个原生编译的内部过程。外部包装器构造那些不支持的原生编译存储过程，而内部过程是原生编译的，用以执行对性能最敏感的逻辑。以下是一些需要考虑的关键点：

- **游标**：原生编译存储过程中不支持游标。相反，作为最佳实践，请使用基于集合的逻辑或 `WHILE`。

- **子查询**：不支持嵌套另一个查询的查询。重写查询或在解释模式下执行。

- **SELECT INTO**：不支持 `SELECT INTO` 语法；但可以将其重写为 `INSERT INTO Table`。

- **跨数据库事务**：在 SQL Server 2014 中，涉及内存优化表的事务无法访问另一个数据库中的数据，无论它是本地还是远程的。

- **EXECUTE, INSERT EXEC**：你不能在原生编译存储过程内部调用存储过程。在某些情况下，为了符合此限制，你必须对已提取的代码进行内联。

- **外部连接、Union**：外部连接或联合必须通过聚合较小的查询来实现，通常使用本地的内存优化表变量。

- **析取 (OR, IN)**：原生编译存储过程中不支持这些操作。你必须为每个情况创建查询，然后汇总结果。

## 结论

你已经看到 SQL Server 2014 中的内存 OLTP 系统具有大幅加速数据库操作的潜力——在某些情况下，它代表了业务的规则改变者。然而，这并不能消除理解你正试图解决的性能问题并找出导致这些问题的瓶颈的需求。通过理解这种新环境与传统数据库表不同的行为方式，你可以获得巨大的收益。

# 图和递归查询

本章涵盖了在 Microsoft SQL Server 中使用 T-SQL 对称为*图*（`graphs`）的特殊数据结构的处理。人们在讨论图时会使用不同的术语，如*层次结构*（`hierarchy`）和*树*（`tree`），但这些术语经常使用不当。因此，本章从描述图及其属性的方法论开始，以消除困惑。

在关系型数据库管理系统 (RDBMS) 中对图的处理并非易事。我将讨论两种主要方法。一种基于迭代或递归逻辑——例如使用递归查询。另一种基于在数据库中物化描述数据结构的额外信息——例如使用 `HIERARCHYID` 数据类型。

# 术语

本章使用了许多术语来讨论图以及如何在 SQL Server 中操作它们。本节提供了重要术语的定义，以确保你理解它们。

> 注意：本节的解释基于美国国家标准技术研究院 (NIST) 的定义。我对原始定义进行了一些修改，并添加了一些原生内容，以使其不那么正式并保持与主题领域（T-SQL）相关。
有关图及相关术语更完整、正式的定义，请参考 http://www.nist.gov/dods/

# 图

图是由*边*（`edges`）连接的项的集合。每个项被称为*顶点*（`vertex`）或*节点*（`node`）。边是图中两个节点之间的连接。

图是数据结构的统称，许多场景都可以表示为图。

# 层级结构

某些场景可以被描述为层次结构并建模为有向无环图（DAG）——例如，面向对象编程中类型和类之间的继承关系，以及员工组织架构图中的汇报关系。在第一种场景中，图的边确定了继承关系。类从其他类继承方法和属性（可能从多个类继承）。在第二种场景中，边代表员工之间的汇报关系。注意这些场景具有有向且无环的特性。例如，公司的管理责任链不能形成循环。

# 场景

在本章中，我将使用三个场景：员工组织架构图（树，层次结构）；物料清单（或 BOM，DAG）；以及道路系统（无向环图）。注意（有向）有根树与 DAG 之间的区别。所有的树都是 DAG，但并非所有的 DAG 都是树。在树中，一个项目最多有一个父节点。

# 员工组织架构图

我将使用的员工组织架构图如图 11-2 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_733_0.png)

图 11-2 员工组织架构图。

要创建 `Employees` 表并填充示例数据，请运行列表 11-1 中的代码。`Employees` 表的内容如表 11-1 所示。

## 列表 11-1 Employees 表的数据定义语言和示例数据

```
SET NOCOUNT ON;

USE tempdb;

IF OBJECT_ID('dbo.Employees', 'U') IS NOT NULL DROP TABLE dbo.Employees;

GO

CREATE TABLE dbo.Employees (

  empid INT NOT NULL CONSTRAINT PK_Employees PRIMARY KEY,

  mgrid INT NOT NULL CONSTRAINT FK_Employees_Employees REFERENCES dbo.Employees,

  empname VARCHAR(25) NOT NULL,

  salary MONEY NOT NULL,

  CHECK (empid > mgrid)

);

INSERT INTO dbo.Employees(empid, mgrid, empname, salary) VALUES

(1, NULL, 'David', 10000.00),

(2, 1, 'Eitan', 7000.00),

(3, 1, 'Ina', 7500.00),

(4, 2, 'Seraph', 5000.00),

(5, 2, 'Jiru', 5500.00),

(6, 2, 'Steve', 4500.00),

(7, 3, 'Aaron', 5000.00),

(8, 5, 'Lilach', 3500.00),

(9, 7, 'Rita', 3000.00),

(10, 5, 'Sean', 3000.00),

(11, 7, 'Gabriel', 3000.00),

(12, 9, 'Emilia', 2000.00),

(13, 9, 'Michael', 2000.00),

(14, 9, 'Didi', 1500.00);

CREATE UNIQUE INDEX idx_unc_mgrid_emp ON dbo.Employees(mgrid, empid);
```

## 表 11-1 Employees 表的内容

| empid | mgrid | empname | salary |
|---|---|---|---|
| 1 | NULL | David | 10000.000 |
| 2 | 1 | Eitan | 7000.000 |
| 3 | 1 | Ina | 7500.000 |
| 4 | 2 | Seraph | 5000.000 |
| 5 | 2 | Jiru | 5500.000 |
| 6 | 2 | Steve | 4500.000 |
| 7 | 3 | Aaron | 5000.000 |
| 8 | 5 | Lilach | 3500.000 |
| 9 | 7 | Rita | 3000.000 |
| 10 | 5 | Sean | 3000.000 |
| 11 | 7 | Gabriel | 3000.0000 |
| 12 | 9 | Emilia | 2000.0000 |
| 13 | 9 | Michael | 2000.0000 |
| 14 | 9 | Didi | 1500.0000 |

`Employees` 表以邻接列表的形式表示管理层级，其中经理和员工分别代表父节点和子节点。

# 物料清单 (BOM)

我使用了咖啡店产品的物料清单，如图 11-3 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_735_0.png)

图 11-3 咖啡店产品的物料清单 (BOM)。

要创建 `Parts` 和 `BOM` 表并填充示例数据，请运行列表 11-2 中的代码。`Parts` 和 `BOM` 表的内容如表 11-2 和 11-3 所示。注意，第一种场景（员工组织架构图）只需要一张表，因为它被建模为树；而边（组件，零件）和节点（零件）都可以同一行来表示。BOM 场景需要两张表，因为它被建模为 DAG，多个路径可以指向同一个节点。边（组件，零件）由 `BOM` 表中的行表示，而节点（零件）由 `Parts` 表中的行表示。

## 列表 11-2 Parts 和 BOM 表的数据定义语言和示例数据

```
IF OBJECT_ID('dbo.BOM', 'U') IS NOT NULL DROP TABLE dbo.BOM;

IF OBJECT_ID('dbo.Parts', 'U') IS NOT NULL DROP TABLE dbo.Parts;

GO

CREATE TABLE dbo.Parts

(

    partid INT NOT NULL CONSTRAINT PK_Parts PRIMARY KEY,

    partname VARCHAR(25) NOT NULL

);

INSERT INTO dbo.Parts(partid, partname) VALUES

(1, 'Black Tea'),

(2, 'White Tea'),

(3, 'Latte'),

(4, 'Espresso'),

(5, 'Double Espresso'),

(6, 'Cup Cover'),

(7, 'Regular Cup'),

(8, 'Stirrer'),

(9, 'Espresso Cup'),

(10, 'Tea Shot'),

(11, 'Milk'),

(12, 'Coffee Shot'),

(13, 'Tea Leaves'),

(14, 'Water'),

(15, 'Sugar Bag'),

(16, 'Ground Coffee'),

(17, 'Coffee Beans');

CREATE TABLE dbo.BOM

(

    partid INT NOT NULL CONSTRAINT FK_BOM_Parts REFERENCES dbo.Parts(partid),

    assemblyid INT NOT NULL CONSTRAINT FK_BOM_Assembly REFERENCES dbo.Parts(partid),

    unit VARCHAR(3) NOT NULL,

    qty DECIMAL(8, 2) NOT NULL,

    CONSTRAINT UK_BOM_part (partid, assemblyid),

    CONSTRAINT CHK_BOM_diff (partid <> assemblyid)

);

INSERT INTO dbo.BOM(partid, assemblyid, unit, qty) VALUES

(11, 2, 'mL', 25.00),

(6, 3, 'EA', 1.00),

(7, 3, 'EA', 1.00),

(11, 3, 'mL', 225.00),

(12, 4, 'EA', 1.00),

(9, 4, 'EA', 1.00),

(9, 5, 'EA', 1.00),

(13, 10, 'g', 5.00),

(14, 10, 'mL', 20.00),

(14, 12, 'mL', 20.00),

(16, 12, 'g', 15.00);
```

## 表 11-2 Parts 表的内容

| partid | partname |
|---|---|
| 1 | Black Tea |
| 2 | White Tea |
| 3 | Latte |
| 4 | Espresso |
| 5 | Double Espresso |
| 6 | Cup Cover |
| 7 | Regular Cup |
| 8 | Stirrer |
| 9 | Espresso Cup |
| 10 | Tea Shot |
| 11 | Milk |
| 12 | Coffee Shot |
| 13 | Tea Leaves |
| 14 | Water |
| 15 | Sugar Bag |
| 16 | Ground Coffee |
| 17 | Coffee Beans |

## 表 11-3 BOM 表的内容

| partid | assemblyid | unit | qty |
|---|---|---|---|
| 1 | NULL | EA | 1.00 |
| 2 | NULL | EA | 1.00 |
| 3 | NULL | EA | 1.00 |
| 4 | NULL | EA | 1.00 |
| 5 | NULL | EA | 1.00 |
| 6 | 1 | EA | 1.00 |
| 7 | 1 | EA | 1.00 |
| 10 | 1 | EA | 1.00 |
| 14 | 1 | mL | 230.00 |
| 6 | 2 | EA | 1.00 |
| 7 | 2 | EA | 1.00 |
| 10 | 2 | EA | 1.00 |
| 14 | 2 | mL | 205.00 |
| 11 | 2 | mL | 25.00 |
| 6 | 3 | EA | 1.00 |
| 7 | 3 | EA | 1.00 |
| 11 | 3 | mL | 225.00 |
| 12 | 3 | EA | 1.00 |
| 9 | 4 | EA | 1.00 |
| 12 | 4 | EA | 1.00 |
| 9 | 5 | EA | 1.00 |
| 13 | 10 | g | 5.00 |
| 14 | 10 | mL | 20.00 |
| 14 | 12 | mL | 20.00 |
| 16 | 12 | g | 15.00 |

# 道路系统

道路系统场景指的是美国几个主要城市的道路系统，如图 11-4 所示。在这个场景中，我选择了国际航空运输协会（IATA）代码来识别每个城市。

![](img/bdc38aa36f6e2987d913ee5381474711_739_0.png)

图 11-4 道路系统场景。

要创建 `Cities` 和 `Roads` 表并填充示例数据，请运行列表 11-3 中的代码。`Cities` 和 `Roads` 表的内容如表 11-4 和 11-5 所示。

## 列表 11-3 Cities 和 Roads 表的数据定义语言和示例数据

```
IF OBJECT_ID('dbo.Roads', 'U') IS NOT NULL DROP TABLE dbo.Roads;

IF OBJECT_ID('dbo.Cities', 'U') IS NOT NULL DROP TABLE dbo.Cities;

GO

CREATE TABLE dbo.Cities

(

  city CHAR(33) NOT NULL CONSTRAINT PK_Cities PRIMARY KEY,

  char VARCHAR(30) NOT NULL,

  region VARCHAR(30) NULL,

  country VARCHAR(30) NOT NULL

);

INSERT INTO dbo.Cities(city, city, region, country) VALUES

('ATL', 'Atlanta', 'GA', 'USA'),

('ORD', 'Chicago', 'IL', 'USA'),

('DEN', 'Denver', 'CO', 'USA'),

('IAH', 'Houston', 'TX', 'USA'),

('MCI', 'Kansas City', 'KS', 'USA'),

('LAX', 'Los Angeles', 'CA', 'USA'),

('MIA', 'Miami', 'FL', 'USA');
```



# CHAPTER 11 图形和递归查询

```sql
('MSP', 'Minneapolis', 'MN', 'USA'),
('JFK', 'New York', 'NY', 'USA'),
('SEA', 'Seattle', 'WA', 'USA'),
('SFO', 'San Francisco', 'CA', 'USA'),
('ANC', 'Anchorage', 'AK', 'USA'),
('FAI', 'Fairbanks', 'AK', 'USA');
```

## 创建 TABLE dbo.Rows

```sql
city1    CHAR(3) NOT NULL CONSTRAINT FK_Rows_city1 REFERENCES dbo.Cities,
city2    CHAR(3) NOT NULL CONSTRAINT FK_Rows_city2 REFERENCES dbo.Cities,
distance  INT     NOT NULL,
        CONSTRAINT PK_Rows PRIMARY KEY(city1,city2),
        CONSTRAINT CHK_Rows_citydiff CHECK(city1 < city2),
        CONSTRAINT CHK_Rows_posdist CHECK(distance > 0);
```

```sql
INSERT INTO dbo.Rows(city1, city2, distance) VALUES
('ANC', 'FAI', 359),
('ATL', 'ORD', 715),
('ATL', 'IAH', 800),
('ATL', 'MCI', 800),
('ATL', 'MIA', 665),
('ATL', 'JFK', 865),
('DEN', 'IAH', 1120),
('DEN', 'MCI', 600),
('DEN', 'LAX', 1025),
('DEN', 'MSP', 915),
('DEN', 'SEA', 1335),
('DEN', 'SFO', 1270),
('IAH', 'MCI', 795),
('IAH', 'LAX', 1550),
('IAH', 'MIA', 1190),
('JFK', 'ORD', 793),
('LAX', 'SFO', 385),
('MCI', 'ORD', 525),
('MCI', 'MSP', 440),
('MSP', 'ORD', 410),
('MSP', 'SEA', 2015),
('SEA', 'SFO', 815);
```

## 表 11-4 Cities 表的内容

| cityid | city | region | country |
|---|---|---|---|
| ANC | Anchorage | AK | USA |
| ATL | Atlanta | GA | USA |
| DEN | Denver | CO | USA |
| FAI | Fairbanks | AK | USA |
| IAH | Houston | TX | USA |
| JFK | New York | NY | USA |
| LAX | Los Angeles | CA | USA |
| MCI | Kansas City | KS | USA |
| MIA | Miami | FL | USA |
| MSP | Minneapolis | MN | USA |
| ORD | Chicago | IL | USA |
| SEA | Seattle | WA | USA |
| SFO | San Francisco | CA | USA |

## 表 11-5 Roads 表的内容

| city1 | city2 | distance |
|---|---|---|
| ANC | FAI | 359 |
| ATL | IAH | 800 |
| ATL | JFK | 865 |
| ATL | MCI | 805 |
| ATL | ORD | 715 |
| DEN | IAH | 1120 |
| DEN | LAX | 1025 |
| DEN | MCI | 600 |
| DEN | SEA | 915 |
| DEN | SFO | 1270 |
| IAH | LAX | 1550 |
| IAH | MCI | 795 |
| IAH | MIA | 1190 |
| JFK | ORD | 795 |
| LAX | SFO | 385 |
| MCI | MSP | 440 |
| MCI | ORD | 525 |
| MSP | ORD | 410 |
| MSP | SEA | 2015 |
| SEA | SFO | 815 |

`Roads` 表表示一个无向加权图。每条边（路）由表中的一行表示。`city1` 和 `city2` 属性代表节点。边的权重是 `distance` 属性，它存储了城市之间的距离（英里）。注意 `Roads` 表有一个 CHECK 约束（`city1 < city2`），以防止重复进入同一条边（例如，SEA, SFO；SFO, SEA）。在有了所有场景和示例数据后，让我们处理图的方法：迭代/递归、物化路径以及嵌套集合。

# 迭代/递归

迭代方法采用某种形式的循环或递归。许多迭代算法遍历图。有些一次遍历一个节点，通常用游标实现，但这些通常非常慢。我将关注使用迭代或递归逻辑结合集合查询来逐层遍历图。节点 `P` 的下一层集合 `C` 由 `P` 中的子节点组成。根据经验，逐层遍历图的迭代算法实现比一次遍历一个节点的实现性能更好。

使用迭代方案具有优势：首先，你不需要物化除节点 ID 以外的任何额外信息。其次，适用于树的大多数方案也适用于单路径通往给定节点的图，以及适用于多条路径通往给定节点的图。最后，大多数方案支持无限的层级。

实现迭代方案的方法有两种：使用循环或递归表表达式（CTEs）。两种情况下核心算法是相似的。循环的使用可以提高性能，因为你对物理侧有更多控制。你可以使用临时表，并在它们上定义索引，当你清楚自己在做什么时，可以获得良好的性能。对于递归 CTE，缺点是它们对物理侧的控制很小；优点是递归 CTE 代码更简洁、更优雅。

如果你想封装基于循环的方案，可以使用表值函数（UDF）或存储过程。从用户的角度来看，UDF 更方便使用，因为像查询表一样查询它们。然而，存储过程的限制少得多，你通常可以通过它们获得更好的性能。例如，使用临时表查询优化器倾向于产生更好的估计，从而导致更高效的计划。如果你想封装递归 CTE 的逻辑，可以使用内联表值 UDF。这种选项没有性能缺点；内联 UDF 使用是透明的。代码通过以下形式内联：

```sql
DECLARE @input AS <data_type>;
<recursive_query>;
```

要在内联 UDF 中封装逻辑，只需使用：

```sql
CREATE FUNCTION <function_name>(@input <data_type>) RETURNS TABLE
AS
RETURN
<recursive_query>;
```

## 子图/后代

让我们从返回图中给定根子图（也称为后代）的经典请求开始，例如返回给定员工的所有下属。当树时，请求被称为子树。迭代算法很简单：

输入：`@root`

算法：
- 设置 `@lvl = 0`；向 `@Subs` 表插入 `@root` 行
- 当上一层员工有行时：
- 设置 `@lvl += 1`；向 `@Subs` 表插入下一层的行
- 返回 `@Subs`

运行以下代码创建实现该算法的 `Descendants` UDF。

```sql
-- 函数：Subordinates1, Descendants
-- 输入：@root INT: 经理 ID
-- 输出：@Subs 表：所有层级经理 (empid = @root) 的下属 ID 和级别
-- 处理：
-- * 向 @Subs 插入经理行
-- * 在循环中，当插入行数大于 0 时，向 @Subs 插入下一层下属

IF OBJECT_ID('dbo.Subordinates1','TF') IS NOT NULL DROP FUNCTION dbo.Subordinates1;
GO

CREATE FUNCTION dbo.Subordinates1(@root AS INT) RETURNS @Subs TABLE
(
    empid INT NOT NULL PRIMARY KEY UNCLUSTERED,
    lvl INT NOT NULL, -- 索引将用于过滤
    UNIQUE CLUSTERED(lvl, empid)
)
BEGIN
    DECLARE @lvl AS INT = 0; -- 初始化级别计数器为 0
    -- 将根节点插入 @Subs
    INSERT INTO @Subs(empid, lvl)
    SELECT empid, @lvl FROM dbo.Employees WHERE empid = @root;
    WHILE @@ROWCOUNT > 0 -- 当上一层存在时
    BEGIN
        SET @lvl += 1;
        -- 将下一层下属插入 @Subs
        INSERT INTO @Subs(empid, lvl)
        SELECT C.empid, @lvl
        FROM @Subs AS P -- P = 父
        INNER JOIN dbo.Employees AS C -- C = 子
        ON P.lvl = @lvl - 1 -- 过滤上一层的父节点
        AND C.mgrid = P.empid;
    END
    RETURN;
END
GO
```

函数接受输入参数 `@root`，它是请求子树根员工的 ID。该函数返回 `@Subs` 表变量，包含所有层级中 ID 为 `@root` 的员工的下属。除了员工属性外，`@Subs` 还有一个名为 `lvl` 的列，用于跟踪子树中的层级（子树根为 0，每次迭代增加 1）。

函数的代码通过局部变量 `@lvl` 跟踪当前处理的级别，该变量初始化为 0。

该函数代码首先将 `Employees` 表中 `empid = @root` 的行插入到 `@Subs` 中。

然后在一个循环中，只要上一次插入影响的行数大于零，代码就会将 `@lvl` 变量的值加 1，并向 `@Subs` 插入下一层级的员工——换句话说，就是上一层插入的经理的直接下属。

为了向 `@Subs` 插入下一层级的员工，循环中的查询将 `@Subs`（代表经理）与 `Employees`（代表下属）进行连接。

`lvl` 列非常重要，因为你可以使用它来隔离上一次迭代中插入到 `@Subs` 中的经理。为了仅返回之前插入的经理的下属，连接（join）仅过滤出 `@Subs` 中 `lvl` 列等于上一个级别（`lvl - 1`）的行。

要测试该函数，运行以下代码，它将返回员工 3 的下属：

```sql
SELECT empid, lvl FROM dbo.Subordinates1(3) AS S;
```

此代码生成了以下输出：

| empid | lvl |
|---|---|
| 3 | 0 |
| 7 | 1 |
| 9 | 2 |
| 11 | 2 |
| 12 | 3 |
| 13 | 3 |
| 14 | 3 |

你可以通过检查图 11-2 并遵循输入根员工（ID = 3）的子树来验证输出是否正确。

除了员工 ID 之外，若要获取员工的其他属性，你可以重写函数并将这些属性添加到 `@Subs` 表中，或者简单地将该函数与 `Employees` 表连接，如下所示：

```sql
SELECT E.empid, E.empname, S.lvl
FROM dbo.Subordinates1(3) AS S
INNER JOIN dbo.Employees AS E
ON E.empid = S.empid;
```

你将得到以下输出：

| empid | empname | lvl |
|---|---|---|
| 3 | Ina | 0 |
| 7 | Aaron | 1 |
| 9 | Rita | 2 |
| 11 | Gabriel | 2 |
| 12 | Emilia | 3 |
| 13 | Michael | 3 |
| 14 | Didi | 3 |

要将结果集限制为给定根节点下的叶子员工，只需添加一个带有 `NOT EXISTS` 谓词的过滤器，仅选择不是其他员工经理的员工：

```sql
SELECT empid
FROM dbo.Subordinates1(3) AS P
WHERE NOT EXISTS
(SELECT * FROM dbo.Employees AS C
WHERE C.mgrid = P.empid);
```

此查询返回员工 ID 11, 12, 13 和 14。

到目前为止，你已经看到了一个针对给定根节点下的子树的 UDF 实现，它包含一个 `WHILE` 循环。以下是 CTE 解决方案，它不包含显式循环：

```sql
DECLARE @root AS INT = 3;
WITH Subs AS
(
  -- 锚点成员返回根节点
  SELECT empid, empname, 0 AS lvl
  FROM dbo.Employees
  WHERE empid = @root
  UNION ALL
  -- 递归成员返回下一层孩子
  SELECT C.empid, C.empname, P.lvl + 1
  FROM Subs AS P
  INNER JOIN dbo.Employees AS C
  ON C.mgrid = P.empid
)
SELECT empid, empname, lvl FROM Subs;
```

此代码生成了以下内容：

| empid | empname | lvl |
|---|---|---|
| 3 | Ina | 0 |
| 7 | Aaron | 1 |
| 9 | Rita | 2 |
| 11 | Gabriel | 2 |
| 12 | Emilia | 3 |
| 13 | Michael | 3 |
| 14 | Didi | 3 |

该解决方案采用了与 UDF 实现类似的逻辑。它的简单之处在于你不需要显式地定义返回的表或上一层级的经理。

CTE 主体中的第一个查询根据给定的根员工从 `Employees` 中返回根节点。它还返回 0 作为根员工的级别。在递归 CTE 中，不包含任何递归引用的查询被称为锚点成员（anchor member）。

CTE 体中的第二个查询（跟在 `UNION ALL` 操作符之后）对 CTE 的名称有递归引用。这使其成为递归成员（recursive member），并被以特殊方式处理。

对 CTE（`Subs`）的递归引用代表之前返回的结果集。递归成员查询将之前的结果集（代表上一层级的经理）与 `Employees` 表连接，以返回下一级的员工。递归查询还计算了级别加 1 的值。当递归成员第一次被调用时，`Subs` 代表由锚点成员（根员工）返回的结果集。递归成员没有显式的终止；相反，它被反复调用，直到返回一个空集。当它第一次被调用时，它返回子树的直接下属。当第二次被调用时，`Subs` 代表递归成员第一次调用的结果集（第一层），因此它返回第二层下属。递归成员被反复调用，直到没有更多下属为止——在这种情况下，它返回一个空集且递归停止。

如前所述，使用迭代逻辑返回具有多条路径的子图与返回子树类似。运行以下代码来创建 `PartsExplosion`：

```sql
IF OBJECT_ID('dbo.PartsExplosion', 'FN') IS NOT NULL DROP FUNCTION dbo.PartsExplosion;
GO

CREATE FUNCTION dbo.PartsExplosion(@root INT)
RETURNS @PartsExplosion TABLE
(
    partid INT NOT NULL,
    qty DECIMAL(8,2) NOT NULL,
    unit VARCHAR(3) NOT NULL,
    lvl INT NOT NULL PRIMARY KEY CLUSTERED (lvl)
)
AS
BEGIN
    DECLARE @lvl INT = 0;
    -- 将根节点插入返回表
    INSERT INTO @PartsExplosion(partid, qty, lvl)
    SELECT empid, 1, @lvl
    FROM dbo.Employees
    WHERE empid = @root;
    WHILE @@ROWCOUNT > 0
    BEGIN
        SET @lvl = @lvl + 1;
        -- 将下一级员工插入返回表
        INSERT INTO @PartsExplosion(partid, qty, lvl)
        SELECT C.empid, C.qty, @lvl
        FROM @PartsExplosion AS P
        INNER JOIN dbo.Employees AS C
        ON C.mgrid = P.empid;
    END
    RETURN;
END
```

运行以下代码来查看零件 ID 为 2 的零件爆炸情况：

```sql
SELECT * FROM dbo.PartsExplosion(2);
```



此代码生成了以下输出：

| partid | qty | unit | lvl |
|---|---|---|---|
| 2 | 1 | EA | 0 |
| 6 | 1 | EA | 1 |
| 7 | 1 | EA | 1 |
| 10 | 1 | EA | 1 |
| 14 | 205 | mL | 1 |
| 11 | 25 | mL | 1 |
| 13 | 5 | g | 2 |
| 14 | 20 | mL | 2 |

作为另一个示例，以下代码分解了部件 ID 5（双倍浓缩）：

```sql
SELECT P.partid, P.partname, unit, SUM(qty) AS qty
FROM (SELECT partid, unit
      FROM dbo.PartsExplosion(S) AS PE
      GROUP BY partid, unit) AS PES
INNER JOIN dbo.Parts AS P
ON P.partid = PES.partid;
```

此代码生成了输出：

| partid | part | qty | unit |
|---|---|---|---|
| 5 | Double Espresso | 1.00 | EA |
| 9 | Espresso Cup | 1.00 | EA |
| 12 | Coffee Shot | 2.00 | EA |
| 16 | Ground Coffee | 30.00 | g |
| 17 | Coffee Beans | 450.00 | g |
| 14 | Water | 40.00 | ml |

## 返回员工子树的层级限制

在某些情况下你可能需要限制返回的层数。为了实现这一点，你需要对原始算法进行微小的修改：

**输入**：`@root`, `@maxlevels`（除 `@root` 之外）

**算法**：

- 设置 `@lvl = 0`；向表 `@Subs` 插入 `@root` 的行
- 当上一层还有行且 `@lvl < @maxlevels` 时：
- 设置 `@lvl += 1`；向表 `@Subs` 插入下一层的行（根据上一层 `empid` 值中的 `mgrid`）
- 返回 `@Subs`

运行以下代码创建 `Subordinates2` 函数，它是 `Subordinates1` 的修订版，同时也支持层级限制：

```sql
-- Function: Subordinates2
-- Desc: 带有可选层级限制的后代
-- Input : @root INT: 经理 id
--         @maxlevels INT: 返回的最大层数
-- Output : @Subs TABLE: 下属的 id 和层级
--          所有层级中的输入经理 <= @maxlevels
-- Process : * 向 @Subs 插入输入经理的行
--           * 在循环中，当上一次插入的行数大于 0
--             且上一层小于 @maxlevels
--             向 @Subs 插入下一层的下属

IF OBJECT_ID('dbo.Subordinates2', 'FT') IS NOT NULL DROP FUNCTION dbo.Subordinates;
CREATE FUNCTION dbo.Subordinates2 (@root AS INT, @maxlevels AS INT) RETURNS @Subs TABLE (
  emid INT NOT NULL PRIMARY KEY NONCLUSTERED,
  lvl INT NOT NULL,
  UNIQUE CLUSTERED(lvl, emid)) -- 索引将用于过滤层级
AS
BEGIN
  DECLARE @lvl AS INT = 0; -- 初始化层级计数器为0
  -- 将根节点插入 @Subs
  INSERT INTO @Subs(emid, lvl)
  SELECT emid, 1 FROM dbo.Employees WHERE emid = @root;

  WHILE @rowcount > 0 -- 当上一层还有行
  AND (@lvl < @maxlevels) -- 且未达到层级限制
  OR @maxlevels IS NULL
  BEGIN
    SET @lvl += 1;
    -- 将下一层的下属插入 @Subs
    INSERT INTO @Subs(emid, lvl)
    SELECT C.emid, @lvl -- P = 父级
    FROM @Subs P
    INNER JOIN dbo.Employees AS C -- C = 子级
    ON P.lvl = @lvl - 1 -- 过滤上一层的父级
    AND C.mgrid = P.emid;
  END
  RETURN;
END
GO
```

除了原始输入外，`Subordinates2` 还接受 `@maxlevels` 输入，该输入指示了 `@root` 下请求的最大层数。如果对层级没有限制，则应在 `@maxlevels` 中指定 `NULL`。

循环条件除了检查上一次插入是否影响了零行外，还检查了是否达到了层级限制（具体来说，`@lvl` 变量小于 `@maxlevels` 或为 `NULL`）。除了这些微调外，该函数的实现与 `Subordinates1` 相同。

要测试该函数，请运行以下代码请求员工 3 在所有层级的下属（`@maxlevels` 为 `NULL`）：

```sql
SELECT emid, lvl
FROM dbo.Subordinates2(3, NULL) AS S;
```

你得到以下输出：

```
emid  lvl
-------
3     0
7     1
9     2
11    2
12    3
14    3
```

要仅获取员工 3 下的两层下属，请运行以下代码：

```sql
SELECT empid, lvl
FROM dbo.Subordinates2(3, 2) AS S;
```

此代码生成以下输出：

```
empid lvl
------ ----
3 0
7 1
9 2
11 2
```

要仅获取员工 3 下的第二层员工，请对层级添加过滤器：

```sql
SELECT empid
FROM dbo.Subordinates2(3, 2) AS S
WHERE lvl = 2;
```

你得到以下输出：

```
empid
------
9
11
```

> **使用 MAXRECURSION 提示时要谨慎**
> 使用 CTE 限制层级时，你可能会想使用 `MAXRECURSION` 提示，当递归成员的调用次数超过输入时，它会引发错误并终止。然而，`MAXRECURSION` 设计为一种安全措施，以在数据存在问题或代码存在 bug 的情况下避免无限递归。指定时，`MAXRECURSION` 默认值为 100。你可以指定 `MAXRECURSION 0` 以不设限制，但请注意。

```sql
DECLARE @empid AS INT = 8;
```

```sql
WITH Mgrs
AS (
  SELECT empid, mgrid, empname, 0 AS lvl
  FROM dbo.Employees
  WHERE empid = @empid
  UNION ALL
  SELECT P.empid, P.mgrid, P.empname, C.lvl + 1
  FROM Mgrs AS C
  INNER JOIN dbo.Employees AS P
  ON C.mgrid = P.empid
)
SELECT empid, mgrid, empname, lvl
FROM Mgrs;
```

此代码生成以下输出：

| empid | mgrid | empname | lvl |
|---|---|---|---|
| 8 | 5 | Lilach | 0 |
| 5 | 2 | Jiru | 1 |
| 2 | 1 | Eitan | 2 |
| 1 | NULL | David | 3 |

使用 `Managers` 函数仅获取员工 8 的前两级经理，请运行以下代码：

```sql
SELECT empid, lvl1
FROM dbo.Managers(8, 2) AS M;
```

你得到以下输出：

| empid | lvl1 |
|---|---|
| 2 | 2 |
| 5 | 1 |
| 8 | 0 |

若要仅返回第二级经理，只需在外部查询中添加过滤器，返回员工 ID 为 2：

```sql
SELECT empid
FROM dbo.Managers(8, 2) AS M
WHERE lvl1 = 2;
```

若要使用 CTE 返回员工 8 的两级经理，只需在递归查询的 `ON` 子句中添加一个谓词，如下例中的加粗部分所示：

```sql
DECLARE @empid AS INT = 8, @maxlevels INT = 2;
WITH Mgrs
AS (
  SELECT empid, mgrid, empname, 0 AS lvl
  FROM dbo.Employees
  WHERE empid = @empid
  UNION ALL
  SELECT P.empid, P.mgrid, P.empname, C.lvl + 1
  FROM Mgrs AS C
  INNER JOIN dbo.Employees AS P
  ON C.mgrid = P.empid
  AND lvl < @maxlevels
)
SELECT empid, mgrid, empname, lvl
FROM Mgrs;
```

**另参** 此处提出的路径（`path`）和路径枚举（`path enumeration`）解决方案都实现了算法中可以被认为是“分治”或“归治”的内容：在[分治哈万圣节](http://sqlmag.com/t-sql/divide-and-conquer-halloween)中，我进一步描述了此类实现的其他优化方面。

## 带有路径枚举的子图/后代

在子图/后代解决方案中，你可能希望为每个节点生成一个枚举路径，该路径由指向该节点的所有节点 ID 组成，并使用某些分隔符（如 `.\`）。例如，在组织架构场景中，员工 8 的枚举路径为 `.1.2.5.8.`，因为员工 5 是员工 8 的经理，员工 2 是员工 5 的经理，员工 1 是员工 2 的经理，而员工 1 是根员工。

- 枚举路径有许多用途——对输出中的节点进行排序、检测循环，以及我在稍后在“物化路径”部分中描述的其他操作。坦率地说，你可以对我提供的返回子图的解决方案进行细微调整，以便在不需要任何额外 I/O 的情况下计算枚举路径。

算法从子树的根节点开始，并在循环或递归调用中返回下一层。对于根节点，路径简单为 `.` + 节点 ID + `.`。对于后续节点，路径为父节点的路径 + 节点 ID + `.`。

运行以下代码创建 `Subordinates3` 函数，它与 `Subordinates2` 相同，仅增加了枚举路径的计算。

- 函数：`Subordinates3`
- 带有可选层级限制的后代枚举
- 输入：`@root INT`：经理 ID
- `@maxlevels INT`：要返回的层级数
- 输出：`@Subs` 表：所有 `@maxlevels` 层级内经理的后代 ID、层级和物化路径
- 处理：将经理的行插入 `@subs`；在循环中，如果上一层插入了多于 0 行且层级小于 `@maxlevels`：
    - 将下一级的后代插入 `@subs`
    - 通过连接当前节点到父节点的路径为每个节点计算物化路径

```sql
IF OBJECT_ID('dbo.Subordinates3', 'FN') IS NOT NULL DROP FUNCTION dbo.Subordinates3;
GO
CREATE FUNCTION dbo.Subordinates3(@root INT, @maxlevels INT = NULL) 
RETURNS @Subs TABLE
(
    empid INT NOT NULL PRIMARY CLUSTERED,
    lvl1 INT NOT NULL,
    path VARCHAR(89) NOT NULL, -- 用于过滤层级
    UNIQUE CLUSTERED(lvl1, empid)
)
AS
BEGIN
    DECLARE @lvl1 INT = 0; -- 初始化层级计数
    -- 将根节点插入 @Subs
    INSERT INTO @Subs(empid, lvl, path)
    SELECT empid, 1, CAST(empid AS VARCHAR(10)) + '.'
    FROM dbo.Employees WHERE empid = @root;

    WHILE @@rowcount > 0 -- 当上一层有行
    AND (@lvl1 < @maxlevels -- 未达到层级) OR (@maxlevels IS NULL)
    BEGIN
        SET @lvl1 += 1; -- 层级增加
        -- 插入下一级的后代
        INSERT INTO @Subs(empid, lvl, path)
        SELECT C.empid, @lvl1, P.path + CAST(C.empid AS VARCHAR(10)) + '.'
        FROM @Subs AS P -- P = 父级
        INNER JOIN dbo.Employees AS C -- C = 子级
        ON P.lvl = @lvl1 - 1 -- 过滤上一层的父级
        AND C.mgrid = P.empid;
    END
    RETURN;
END
GO
```

### 图和递归查询

运行以下代码返回员工 1 的所有后代及其路径：

```sql
SELECT empid, lvl
FROM Subordinates3(1, NULL) AS S;
```

此代码生成以下输出：

| empid | lvl | path |
|---|---|---|
| 1 | 0 | .1 |
| 2 | 1 | .1.2. |
| 3 | 1 | .1.3. |
| 4 | 2 | .1.2.4. |
| 5 | 2 | .1.2.5. |
| 6 | 2 | .1.2.6. |
| 7 | 2 | .1.3.7. |
| 8 | 3 | .1.2.5.8. |
| 9 | 3 | .1.3.7.9. |
| 10 | 3 | .1.2.5.10. |
| 11 | 3 | .1.3.7.11. |
| 12 | 4 | .1.3.7.12. |
| 13 | 4 | .1.3.7.13. |
| 14 | 4 | .1.3.7.14. |

通过 `lvl` 和 `path` 值，你可以轻松地图形化返回子树中员工的层级关系：

```sql
SELECT E.empid, REPLICATE(' ', lvl) + E.empname AS empname
FROM Subordinates3(1, NULL) AS S
INNER JOIN dbo.Employees AS E ON E.empid = S.empid
ORDER BY path;
```

该查询根据员工 ID 将 `Subordinates3` 函数子树与 `Employees` 表连接。从函数中获取 `lvl` 和 `path` 值，从表中获取其他感兴趣的属性（如员工姓名）。通过复制字符串（本例为 `' '`）并拼接员工姓名在员工姓名前生成缩进。通过 `path` 列对员工进行排序可以产生正确的层级排序（拓扑排序），这要求子节点出现在其父节点之后——换句话说，要求子节点的排序值比父节点高。根据定义，子节点的路径大于父节点的路径，因为它以父节点的路径开头。以下是该查询的输出：

| empid | empname |
|---|---|
| 1 | David |
| 2 | Eitan |
| 4 | Seraph |
| 5 | Jiru |
| 10 | Sean |
| 8 | Lilach |
| 6 | Steve |
| 3 | Ina |
| 7 | Aaron |

同样，你也可以在子树 CTE 中添加路径计算，如下例中的加粗部分所示：

```sql
DECLARE @root AS INT = 1;
WITH Subs
AS (
  SELECT empid, empname, 0 AS lvl,
         -- 根节点路径 = '.' + CAST(empid AS VARCHAR(10)) + '.'
         CAST('.' + CAST(empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)) AS path
  FROM dbo.Employees
  WHERE empid = @root
  UNION ALL
  SELECT C.empid, C.empname, P.lvl + 1,
         -- 子节点路径 = 父节点路径 + 子节点 empid + '.'
         CAST(P.path + CAST(C.empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX))
  FROM Subs AS P
  INNER JOIN dbo.Employees AS C
    ON C.mgrid = P.empid
)
SELECT empid, empname, lvl, path
FROM Subs;
```



# 排序

排序是一个通常由客户端提出的请求，而不是服务器。这意味着你可能希望层级排序在客户端进行。然而，在本节中，我将介绍使用 T-SQL 的服务器端排序技术，适用于你倾向于在服务器上处理排序的情况。

DAG 的拓扑排序定义为为子节点提供比父节点更高的排序值。有时我将拓扑排序称为正确的层级排序。对 DAG 中的项进行排序的方法有多种可以认为是正确的。

![](img/bdc38aa36f6e2987d913ee5381474711_760_0.png)

请记住，枚举路径是由通往节点的祖先 ID 组成的字符串；这意味着兄弟节点按其节点 ID 进行排序。由于路径是基于字符的，你获得的是基于字符的 ID 排序，这可能与整数排序有所不同。例如，员工 ID 11 的排序结果低于其兄弟节点 ID 9（`'1.3.7.11.' < '1.3.7.9'`），尽管 9 小于 11。你可以保证通过枚举路径排序会产生拓扑排序，但它不能保证兄弟节点之间的顺序。如果你需要这种保证，则需要不同的解决方案。

为了获得最佳的排序灵活性，你可能希望满足以下条件：

1. 拓扑排序——即，确保子节点的排序大于其父节点的排序。
2. 兄弟节点按照要求的顺序排序（例如，按 `empname` 或 `salary`）。
3. 生成的是整数值而不是长字符串。

在枚举路径排序中，需求 2 无法被满足，因为路径是由节点 ID 组成且基于字符的；对字符进行比较和在字符间进行排序是基于排序规则属性的，这将产生与整数不同的比较和排序行为。需求 3 无法被满足，因为解决方案按路径对结果进行排序，与整数值相比，路径非常长。为了满足所有三个需求，你仍然可以使用每个节点对应的路径，但有几点不同：

- 不使用节点 ID，而是根据要求的顺序从代表节点间位置（行号）（例如，`empname` 或 `salary`）的值来构建路径。
- 不在路径的每层使用长度不定的字符字符串，而是每层使用固定长度的二进制字符串。
- 一旦构建了二进制路径，计算表示路径顺序（行号）的整数值，并最终使用这些值对层级进行排序。

遍历子树的核心算法保持不变，但根据行号的二进制表示以不同的方式构建。实现使用了 CTE 和 `ROW_NUMBER()` 函数。

运行以下代码以返回员工 1 的子树，兄弟节点按 `empname` 排序，并按所示缩进显示：

```sql
DECLARE @root AS INT = 1;

WITH Subs AS (
    SELECT empid, empname, 0 AS lvl,
        -- 根节点的路径为 1 (二进制)
        CAST(CAST(1 AS BINARY(4)) AS VARBINARY(MAX)) AS sort_path
    FROM dbo.Employees
    WHERE empid = @root

    UNION ALL

    SELECT C.empid, C.empname, P.lvl + 1,
        -- 子节点的路径 = 父节点路径 + 行号 (二进制)
        P.sort_path + CAST(ROW_NUMBER() OVER(PARTITION BY C.mgrid ORDER BY C.empname) AS BINARY(4))
    FROM Subs AS P
    INNER JOIN dbo.Employees AS C
        ON C.mgrid = P.empid
)

SELECT empid,
    ROW_NUMBER() OVER(ORDER BY sort_path) AS sortval,
    REPLICATE(' | ', lvl) + empname AS empname
FROM Subs
ORDER BY sortval;
```

此代码生成了以下输出：

| empid | sortval | empname |
| :--- | :--- | :--- |
| 1 | 1 | David |
| 2 | 2 | Eitan |
| 5 | 3 | Jiru |
| 8 | 4 | Lilach |
| 10 | 5 | Sean |
| 6 | 6 | Seraph |
| 7 | 7 | Steve |
| 3 | 8 | Ina |
| 7 | 9 | Aaron |
| 11 | 10 | Gabriel |
| 9 | 11 | Rita |
| 14 | 12 | Didi |
| 12 | 13 | Emilia |
| 13 | 14 | Michael |

锚成员查询返回根节点，将整数 1 转换为 `BINARY(4)`，并返回 `VARBINARY(MAX)` 作为二进制路径。递归成员查询通过 `empname` 排序计算员工在兄弟节点中的行号，并将该数字转换为 `BINARY(4)` 后连接到父节点路径上。

> **提示**：使用 `BINARY(4)` 作为排序路径中每个元素的目标类型；不过，你可以使用较小的尺寸来尽量缩短路径长度。只需记住，你计算的是按经理划分的行号。因此，请询问每个经理有多少个直接下属。例如，如果答案是“永远不超过 100 个”，`BINARY(1)` 就足够了。如果是 1,000 个，`BINARY(2)` 就足够了。

外部查询计算行号以根据二进制路径顺序生成排序值，并根据这些排序值对子树进行排序，同时根据计算的值添加缩进。

如果你希望以不同的方式排序兄弟节点，你只需要更改递归成员查询中 `ROW_NUMBER()` 函数的 `ORDER BY` 列表。以下代码包含了按 `salary` 排序兄弟节点的修订版本（如**粗体**所示）：

```sql
DECLARE @root AS INT = 1;

WITH Subs AS (
    SELECT empid, empname, salary, 0 AS lvl,
        -- 根节点的路径 = 1 (二进制)
        CAST(CAST(1 AS BINARY(4)) AS VARBINARY(MAX)) AS sort_path
    FROM dbo.Employees
    WHERE empid = @root

    UNION ALL

    SELECT C.empid, C.empname, C.salary, P.lvl + 1,
        -- 子节点的路径 = 父节点路径 + 行号 (二进制)
        P.sort_path + CAST(ROW_NUMBER() OVER(PARTITION BY C.mgrid ORDER BY C.salary) AS BINARY(4))
    FROM Subs AS P
    INNER JOIN dbo.Employees AS C
        ON C.mgrid = P.empid
)

SELECT empid,
    ROW_NUMBER() OVER(ORDER BY sort_path) AS sortval,
    REPLICATE(' | ', lvl) + empname AS empname
FROM Subs
ORDER BY sortval;
```

此代码生成以下输出：

| empid | sortval | empname |
| :--- | :--- | :--- |
| 1 | 1 | David |
| 2 | 2 | Eitan |
| 5 | 3 | Jiru |
| 8 | 4 | Lilach |
| 10 | 5 | Sean |
| 6 | 6 | Seraph |
| 7 | 7 | Steve |
| 3 | 8 | Ina |
| 7 | 9 | Aaron |
| 11 | 10 | Gabriel |
| 9 | 11 | Rita |
| 14 | 12 | Didi |
| 12 | 13 | Emilia |
| 13 | 14 | Michael |

锚成员查询返回根节点，将整数 1 转换为 `BINARY(4)`，并返回 `VARBINARY(MAX)` 作为二进制路径。递归成员查询通过 `salary` 排序计算员工在兄弟节点中的行号，并将该数字转换为 `BINARY(4)` 后连接到父节点路径上。

> **提示**：使用 `BINARY(4)` 作为排序路径中每个元素的目标类型；不过，你可以使用较小的尺寸来尽量缩短路径长度。只需记住，你计算的是按经理划分的行号。因此，请询问每个经理有多少个直接下属。例如，如果答案是“永远不超过 100 个”，`BINARY(1)` 就足够了。如果是 1,000 个，`BINARY(2)` 就足够了。

外部查询计算行号以根据二进制路径顺序生成排序值，并根据这些排序值对子树进行排序，同时根据计算的值添加缩进。

如果你希望以不同的方式排序兄弟节点，你只需要更改递归成员查询中 `ROW_NUMBER()` 函数的 `ORDER BY` 列表。以下代码包含了按 `salary` 排序兄弟节点的修订版本（如**粗体**所示）：

## 循环

图中的起点和终点在同一个节点。在某些场景下，循环是自然的（例如，系统）。如果你在应该是无环的图中发现了循环，可能表明数据存在问题。然而，我将向你展示一种性能良好的简单循环检测技术，依赖于排列，这是我之前讨论过的。

假设 Didi（`empid` 14）对她在公司层级中的位置不满。Didi 恰好也是数据库管理员，对 `Employees` 表具有完全访问权限。Didi 运行以下循环，为 CEO 引入了循环：

```sql
UPDATE dbo.Employees SET mgrid = 14 WHERE empid = 1;
```

`Employees` 表包含以下 ID 循环：

```
1 3 7 14
```

作为基准，我将使用之前涵盖过的解决方案之一，它构建枚举路径。在我的示例中，我将使用 CTE 解决方案，但你可以将相同的逻辑应用于循环的 UDF 解决方案。

当你通往给定节点的路径时，如果父节点路径已经包含了子节点 ID，则检测到了循环。你可以通过维护一个循环列来跟踪循环，如果没有检测到循环，该列为 0，如果检测到则为 1。在解决方案的锚成员中，循环列的值简单地为 0，显然，根级别没有循环。在递归成员的查询中，使用 `LIKE` 谓词来检查路径是否包含子节点 ID。如果包含则返回 1，否则返回 0。注意路径和模式开头和结尾处点的重要性——如果没有点，当路径包含员工 ID nm（例如，`m = 15, nm = 315`）时，你会得到员工 ID n（例如，`n = 3`）的意外匹配。以下代码带有枚举路径计算的子树，并增加了循环列的计算，所示：

```sql
DECLARE @root AS INT = 1;

WITH S AS (
    SELECT empid, empname, 0 AS lvl,
        -- 根节点没有循环
        CAST('.' + CAST(empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)) AS path,
        0 AS cycle
    FROM dbo.Employees
    WHERE empid = @root

    UNION ALL

    SELECT C.empid, C.empname, P.lvl + 1,
        CAST(P.path + CAST(C.empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)),
        -- 如果父级路径包含子 ID，则检测到循环
        CASE WHEN P.path LIKE '%.' + CAST(C.empid AS VARCHAR(10)) + '.%' THEN 1 ELSE 0 END
    FROM S AS P
    INNER JOIN dbo.Employees AS C
        ON C.mgrid = P.empid
)

SELECT empid, empname, cycle, path
FROM S;
```

如果你运行这段代码，它会在 100 层（默认的 `MAXRECURSION` 值）后中断，因为它检测到了循环但没有避免循环。你需要避免循环——换句话说，不要继续追踪检测到循环的路径。为了实现这一点，只需在递归成员中添加一个过滤器，当其父级的循环值为 0 时才返回子节点，如下例中的**粗体**所示：

```sql
DECLARE @root AS INT = 1;

WITH Subs AS (
    SELECT empid, empname, 0 AS lvl,
        CAST('.' + CAST(empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)) AS path,
        -- 显然根节点没有循环
        0 AS cycle
    FROM dbo.Employees
    WHERE empid = @root

    UNION ALL

    SELECT C.empid, C.empname, P.lvl + 1,
        CAST(P.path + CAST(C.empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)),
        -- 如果父级路径包含子 ID，则检测到循环
        CASE WHEN P.path LIKE '%.' + CAST(C.empid AS VARCHAR(10)) + '.%' THEN 1 ELSE 0 END
    FROM Subs AS P
    INNER JOIN dbo.Employees AS C
        ON C.mgrid = P.empid
        **AND P.cycle = 0** -- 不要追踪有循环的父级路径
)

SELECT empid, empname, cycle, path
FROM Subs;
```

此代码生成如下输出：

| empid | empname | cycle | path |
|---|---|---|---|
| 1 | David | 0 | .1. |
| 2 | Eitan | 0 | .1.2. |
| 3 | Ina | 0 | .1.3. |
| 7 | Aaron | 0 | .1.3.7. |
| 9 | Rita | 0 | .1.3.7.9. |
| 11 | Gabriel | 0 | .1.3.7.11. |
| 12 | Emilia | 0 | .1.3.7.9.12. |
| 13 | Michael | 0 | .1.3.7.9.13. |
| 14 | Didi | 0 | .1.3.7.9.14. |
| 1 | David | 1 | .1.3.7.9.14.1. |
| 4 | Seraph | 0 | .1.2.4. |
| 5 | Jiru | 0 | .1.2.5. |
| 6 | Steve | 0 | .1.2.6. |
| 8 | Lilach | 0 | .1.2.5.8. |
| 10 | Sean | 0 | .1.2.5.10. |

注意输出中，当员工 1 第二次被到达时，检测到了它的循环，路径没有被进一步追踪。在环形图中，这就是你通常需要添加的全部逻辑。在我们的情况下，循环标识了需要修复的数据问题。为了仅隔离出循环路径（例如 `.1.3.7.9.14.1.`），只需在外部查询中添加过滤器 `cycle = 1`，如此处文中的**粗体**所示：

```sql
DECLARE @root AS INT = 1;

WITH Subs AS (
    SELECT empid, empname, 0 AS lvl,
        CAST('.' + CAST(empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)) AS path,
        -- 显然根节点没有循环
        0 AS cycle
    FROM dbo.Employees
    WHERE empid = @root

    UNION ALL

    SELECT C.empid, C.empname, P.lvl + 1,
        CAST(P.path + '.' + CAST(C.empid AS VARCHAR(10)) + '.' AS VARCHAR(MAX)),
        -- 如果父级路径包含子 ID，则检测到循环
        CASE WHEN P.path LIKE '%.' + CAST(C.empid AS VARCHAR(10)) + '.%' THEN 1 ELSE 0 END
    FROM Subs AS P
    INNER JOIN dbo.Employees AS C
        ON C.mgrid = P.empid
        AND P.cycle = 0
)

**SELECT path FROM Subs WHERE cycle = 1;**
```

现在已经识别了循环路径，你可以运行以下代码来修复数据：

```sql
UPDATE dbo.Employees SET mgrid = NULL WHERE empid = 1;
```

# 物化路径

到此为止，我展示的解决方案是在代码执行时计算路径。在物化路径解决方案中，路径被存储起来，这样就不需要重复计算。你基本上在两个额外的列中为树的每个节点存储一个枚举路径和一个层级。该方案在树和森林中效果最佳。理论上，你可以将此方法用于更通用的、具有多个路径指向每个节点的有向无环图（DAG）。相比于递归方法，这种方法在查询时通常更快，因为它不需要在运行时计算路径。然而，在数据发生变化时维护这些路径会变得复杂。

```sql
EXEC dbo.AddEmp
    @empid = 5, @mgrid = 2, @empname = 'Jiru', @salary = $5500.00;

EXEC dbo.AddEmp
    @empid = 6, @mgrid = 2, @empname = 'Steve', @salary = $4500.00;

EXEC dbo.AddEmp
    @empid = 7, @mgrid = 3, @empname = 'Aaron', @salary = $5000.00;

EXEC dbo.AddEmp
    @empid = 8, @mgrid = 5, @empname = 'Lilach', @salary = $3500.00;

EXEC dbo.AddEmp
    @empid = 9, @mgrid = 7, @empname = 'Rita', @salary = $3000.00;

EXEC dbo.AddEmp
    @empid = 10, @mgrid = 5, @empname = 'Sean', @salary = $3000.00;

EXEC dbo.AddEmp
```



@empid = 11, @mrid = 7, @empname = 'Gabriel', @salary = $3000.00;

EXEC `db.AddEmp`

@empid = 12, @mrid = 9, @empname = 'Emilia', @salary = $2000.00;

EXEC `db.AddEmp`

@empid = 13, @mrid = 9, @empname = 'Michael', @salary = $2000.00;

EXEC `db.AddEmp`

@empid = 14, @mrid = 9, @empname = 'Didi', @salary = $1500.00;

执行查询以检查 `Employees` 表的内容：

```
SELECT empid, mrid, empname, salary, lvl, path
FROM dbo.Employees
```

按 `path` 排序：

你得到以下输出：

| empid | mrid | empname | salary | lvl | path |
|---|---|---|---|---|---|
| 1 | NULL | David | 10000.0 | 0 | .1. |
| 2 | 1 | Eitan | 7000.0 | 1 | .1.2. |
| 4 | 2 | Seraph | 5000.0 | 2 | .1.2.4. |
| 5 | 2 | Jiru | 5500.0 | 2 | .1.2.5. |
| 10 | 5 | Sean | 3000.0 | 3 | .1.2.5.10. |
| 8 | 5 | Lilach | 3500.0 | 3 | .1.2.5.8. |
| 6 | 2 | Steve | 4500.0 | 2 | .1.2.6. |
| 3 | 1 | Ina | 7500.0 | 1 | .1.3. |
| 7 | 3 | Aaron | 5000.0 | 2 | .1.3.7. |
| 11 | 7 | Gabriel | 3000.0 | 3 | .1.3.7.11. |
| 9 | 7 | Rita | 3000.0 | 3 | .1.3.7.9. |
| 12 | 9 | Emilia | 2000.0 | 4 | .1.3.7.9.12. |
| 13 | 9 | Michael | 2000.0 | 4 | .1.3.7.9.13. |
| 14 | 9 | Didi | 1500.0 | 4 | .1.3.7.9.14. |

## 移动子树

移动子树有点棘手。某人的经理变更会影响该员工的行及其所有下属。输入是子树的根以及该根的父节点（经理）。子树中所有员工的 `level` 和 `path` 值都需要更新。因此，你需要能够隔离子树并找出如何修订子树中所有成员的 `level` 和 `path` 值。为了隔离受影响的子树，你根据 `E.path LIKE R.path + '%'` 将根节点 (R) 的行与 `Employees` 表 (E) 进行连接。为了计算 `level` 和 `path` 的修订，你需要访问根节点的旧经理 (OM) 和新经理 (NM) 的行。所有节点的新 `level` 值应为当前 `level` 值加上新经理 `level` 与旧经理 `level` 之间的差值。例如，如果你将一个子树移动到一个新位置，新经理和旧经理之间的层级差为 2，那么你需要为受影响子树中的所有员工的 `level` 值加 2。同样，为了修正子树中所有节点的 `path` 值，你需要从旧经理的路径中删除前缀并替换为新经理的路径。这可以通过 `STUFF` 函数来实现。

运行以下代码以创建 `MoveSubtree` 存储过程，它实现了我描述的逻辑：

```
-- 存储过程: MoveSubtree
-- 将给定根节点的整个子树移动到新位置
-- 在给定的父节点下
---------------------------------------
IF OBJECT_ID('dbo.MoveSubtree', 'P') IS NOT NULL DROP dbo.MoveSubtree;
GO

CREATE PROC dbo.MoveSubtree
@root INT,
@mrid INT
AS
SET NOCOUNT ON;
BEGIN;
-- 更新子树中所有员工 (E) 的 level 和 path
-- 设置 level = 当前 level + 新经理的 level - 旧经理的 level
-- 设置 path = 删除旧经理的路径并替换为新经理的路径
UPDATE E
SET lvl = E.lvl + NM.lvl - OM.lvl,
  path = STUFF(E.path, 1, LEN(OM.path), NM.path)
FROM dbo.Employees AS E -- E = 子树
INNER JOIN dbo.Employees AS R -- R = 根（一行）
ON R.empid = @root
AND E.path LIKE R.path + '%'
INNER JOIN dbo.Employees AS OM -- OM = 旧经理（单行）
ON R.mrid = OM.empid
INNER JOIN dbo.Employees AS NM -- NM = 新经理（一行）
ON NM.empid = @mrid;
-- 更新根的新经理
UPDATE dbo.Employees SET mrid = @mrid WHERE empid = @root;
COMMIT;
GO
```

此存储过程的实现是简单的，用于演示。并不保证输入是有效的。为了使此过程更健壮，你还应该检查输入是否会导致某人成为自己的经理。例如，你可以通过 `EXISTS` 谓词生成一个包含新路径的结果集，并确保员工不会出现在这些路径中。

要测试此过程，首先检查之前的树结构：

```
SELECT empid, REPLICATE(' | ') + empname AS empname, lvl, path
FROM dbo.Employees
ORDER BY path;
```

你得到以下输出：

| empid | empname | lvl | path |
|---|---|---|---|
| 1 | David | 0 | .1. |
| 2 | Eitan | 1 | .1.2. |
| 4 | Seraph | 2 | .1.2.4. |
| 5 | Jiru | 2 | .1.2.5. |
| 10 | Sean | 3 | .1.2.5.10. |
| 6 | Steve | 2 | .1.2.6. |
| 3 | Ina | 1 | .1.3. |
| 7 | Aaron | 2 | .1.3.7. |
| 11 | Gabriel | 3 | .1.3.7.11. |
| 9 | Rita | 3 | .1.3.7.9. |
| 12 | Emilia | 4 | .1.3.7.9.12. |
| 13 | Michael | 4 | .1.3.7.9.13. |
| 14 | Didi | 4 | .1.3.7.9.14. |

然后运行以下代码将 Aaron 的子树移动到 Sean 下：

```
BEGIN TRAN;
EXEC dbo.MoveSubtree
@root = 7,
@mrid = 10;
```

```
-- 移动子树
SELECT empid, REPLICATE(' | ') + empname AS empname, lvl, path
FROM dbo.Employees
ORDER BY path;
ROLLBACK TRAN; -- 使用回滚是为了应用更改
```

> 注意 更改仅用于回滚，因此每个测试脚本开始的数据是相同的。

检查结果树以验证子树是否移动正确。

| empid | empname | lvl | path |
|---|---|---|---|
| 1 | David | 0 | .1. |
| 2 | Eitan | 1 | .1.2. |
| 4 | Seraph | 2 | .1.2.4. |
| 5 | Jiru | 2 | .1.2.5. |
| 10 | Sean | 3 | .1.2.5.10. |
| 7 | Aaron | 4 | .1.2.5.10.7. |
| 11 | Gabriel | 5 | .1.2.5.10.7.9. |
| 9 | Rita | 6 | .1.2.5.10.7.9.12. |
| 13 | Emilia | 6 | .1.2.5.10.7.9.13. |
| 14 | Michael | 6 | .1.2.5.10.7.9.14. |
| 8 | Lilach | 3 | .1.2.5.8. |
| 6 | Steve | 2 | .1.2.6. |
| 3 | Ina | 1 | .1.3. |

# 删除子树

删除子树是一项简单任务。你只需要删除所有 `path` 值以子树根为前缀的员工。

要测试此解决方案，运行以下查询检查树的当前状态：

```
SELECT empid, REPLICATE(' ', lvl) + empname AS empname, lvl, path
FROM dbo.Employees
ORDER BY path;
```

你得到以下输出：

| empid | empname | lvl | path |
|---|---|---|---|
| 1 | David | 0 | .1. |
| 2 | Eitan | 1 | .1.2. |
| 4 | Seraph | 2 | .1.2.4. |
| 5 | Jiru | 2 | .1.2.5. |
| 10 | Sean | 3 | .1.2.5.10. |
| 8 | Lilach | 3 | .1.2.5.8. |
| 6 | Steve | 2 | .1.2.6. |
| 3 | Ina | 1 | .1.3. |
| 7 | Aaron | 2 | .1.3.7. |
| 11 | Gabriel | 3 | .1.3.7.11. |
| 9 | Rita | 3 | .1.3.7.9. |
| 12 | Emilia | 4 | .1.3.7.9.12. |
| 13 | Michael | 4 | .1.3.7.9.13. |
| 14 | Didi | 4 | .1.3.7.9.14. |

发布以下代码，首先删除 Aaron 及其下属：

```
BEGIN TRAN;
DELETE FROM dbo.Employees
WHERE path LIKE
(SELECT M.path + '%'
FROM dbo.Employees as M
WHERE M.empid = 7);
-- 删除子树后
SELECT empid, REPLICATE(' | ') + empname AS empname, lvl, path
FROM dbo.Employees
ORDER BY path;
ROLLBACK TRAN; -- 使用回滚是为了应用更改
```

你得到以下输出：

| empid | empname | lvl | path |
|---|---|---|---|
| 1 | David | 0 | .1. |
| 2 | Eitan | 1 | .1.2. |
| 4 | Seraph | 2 | .1.2.4. |
| 5 | Jiru | 2 | .1.2.5. |
| 10 | Sean | 3 | .1.2.5.10. |
| 8 | Lilach | 3 | .1.2.5.8. |
| 6 | Steve | 2 | .1.2.6. |
| 3 | Ina | 1 | .1.3. |

## 查询

在物化路径解决方案中查询数据既简单又优雅。对于子树相关的请求，优化器始终可以使用你在 `path` 列上创建的聚集或覆盖索引。如果你在 `path` 列上创建非聚集索引，只要查询具有足够的选择性，优化器仍然可以使用它。

让我们查看树中的典型请求。对于每个请求，我将提供示例查询及其输出。

### 返回给定根节点的子树

```
SELECT REPLICATE(' | ', E.lvl - M.lvl) + E.empname
FROM dbo.Employees AS E
INNER JOIN dbo.Employees AS M
ON M.empid = 3 -- root
AND E.path LIKE M.path + '%'
ORDER BY E.path;
```

+   * Ina Aaron
  * Gabriel
    * Rita
      * Emilia
        * Michael
          * Didi

查询连接了两个 `Employees` 实例。一个代表经理 (M)，并给定的根员工进行过滤。另一个代表子树中的员工 (E)。子树是在连接条件中使用以下逻辑表达式 `E.path LIKE M.path + '%'` 来进行识别，该表达式用于判断它是否包含根节点的路径作为前缀。缩进通过多次重复字符串（`'|'`）来表示员工在子树中的层级。输出结果按员工的路径进行排序。

此查询生成了如图 11-5 所示的执行计划。

![](img/bdc38aa36f6e2987d913ee5381474711_774_0.png)

图 11-5 自定义物化路径子树查询的执行计划。

计划中的第一个 `Index Seek`（索引查找）操作以及关联的 `Key Lookup`（键查找）负责检索过滤后的员工（empid 3）的行。计划中的第二个 `Index Seek` 操作符对 `path` 属性进行范围扫描，以检索请求的员工子树。由于 `path` 属性代表拓扑排序，`path` 上的索引确保了同一子树的所有成员都连续存储在树的叶节点上。因此，对于子集，可以通过索引中的简单范围扫描进行处理，仅触及实际上属于请求子树的节点。

若要从输出中排除子树根节点（顶层经理），只需在 `LIKE` 模式的第一个字符前添加一个下划线：

```
SELECT REPLICATE('|', E.lvl1 - 1) + E.empname
FROM dbo.Employees AS E
INNER JOIN dbo.Employees AS M
ON M.empid = 3
AND E.path LIKE M.path + '_%'
ORDER BY E.path;
```

- Aaron
| Gabriel
| Rita
| Emilia
| Michael
| Didi

在 `LIKE` 条件中添加额外的下划线后，只有当员工的路径以根节点路径开头且至少有一个后续字符时，才会返回该员工。

### 返回给定根节点下的叶节点

要返回给定根节点下的叶节点（如果根节点本身是叶节点，则包含它），请添加 `NOT EXISTS` 谓词来识别不是其他员工经理的员工：

```
SELECT E.empid, E.empname
FROM dbo.Employees AS E
INNER JOIN dbo.Employees AS M
ON M.empid = 3
AND E.path LIKE M.path + '%'
WHERE NOT EXISTS
(SELECT *
FROM dbo.Employees AS E2
WHERE E2.mgrid = E.empid);
```

| empid | empname |
|---|---|
| 11 | Gabriel |
| 12 | Emilia |
| 13 | Michael |
| 14 | Didi |

### 限制子树深度

要返回带有给定根节点的子树，并限制根节点下的层数，请添加一个限制员工与根节点之间差异的过滤器：

```
SELECT REPLICATE(' ', E.lvl1 - M.lvl1) + E.empname
FROM dbo.Employees AS E
INNER JOIN dbo.Employees AS M
ON M.empid = 3
AND E.path LIKE M.path + '%'
WHERE E.lvl1 - M.lvl1 <= 2
ORDER BY E.path;
```

- Aaron
  - Gabriel
  - Rita

要仅返回给定根节点下 n 层的节点，请使用等于运算符（`=`）来识别层级差异，而不是小于等于运算符（`<=`）：

```
SELECT E.empid, E.empname
FROM dbo.Employees AS E
INNER JOIN dbo.Employees AS M
ON M.empid = 3
AND E.path LIKE M.path + '%'
WHERE E.lvl1 - M.lvl1 = 2;
```

| empid | empname |
|---|---|
| 11 | Gabriel |
| 9 | Rita |

### 返回管理链

要返回给定节点的管理链，您可以使用一个与子树查询类似的查询，但有一个细小不同：您过滤的是特定的员工 ID，而不是特定的经理 ID：

```
SELECT REPLICATE(' | ', M.lvl) + M.empname
FROM dbo.Employees AS E
  INNER JOIN dbo.Employees AS M
  ON E.empid = 14
  AND E.path LIKE M.path + '%'
ORDER BY E.path;
```



# 使用 HIERARCHYID 类型实现物化路径

SQL Server 支持基于 CLR 的数据类型 `HIERARCHYID`，您可以用它表示图。该类型为物化模型提供了内置实现；与自定义模型一样，它适用于树。对于自定义模型，`HIERARCHYID` 值提供了拓扑排序，确定了节点在树中的特定位置。通过拓扑排序，`HIERARCHYID` 路径以两种方式定位自定义模型节点：首先，自定义路径是由实际 ID 组成的，而 `HIERARCHYID` 路径是由内部生成的值组成的。其次，自定义路径是基于字符的，而 `HIERARCHYID` 路径是二进制的。我发现 `HIERARCHYID` 类型的一个主要优势是它们通常比自定义路径更经济。`HIERARCHYID` 数据类型中的路径编码不能超过 892 字节，但这个限制对于大多数存储来说应该不是问题。

> 注意 `HIERARCHYID` 类型是 SQL Server 的私有功能。如果您关心解决方案的移植性，可能更倾向于使用自定义模型。因为它依赖于几乎所有 SQL 方言都支持的基础语言元素：字符字符串、整数列和 `LIKE` 谓词。尽管如此，熟悉 `HIERARCHYID` 数据类型是有意义的，主要有两个原因：
>
> 1. 您可能需要维护已经使用它的解决方案。
> 2. SQL Server 的某些功能使用了该数据类型，例如身份验证功能。

`HIERARCHYID` 类型提供了以下方法和属性，可以帮助你维护和查询层次结构：`GetLevel()`、`GetRoot()`、`GetAncestor()`、`GetDescendant()`、`GetReparentValue()`、`IsDescendant()`、`ToString()`、`Parse()`、`Read()` 和 `Write()`。我将在它们所需的任务背景下来描述这些方法和属性。

请注意，我需要提到在处理 `HIERARCHYID` 类型时关于大小写敏感的几点：

- 作为一种 T-SQL 类型标识符，`HIERARCHYID` 始终是不区分大小写的，就像任何 T-SQL 关键字一样。
- 与此类型关联的方法名（如 `GetAncestor()`）始终是区分大小写的，无论它们是否为静态方法。
- 当 `HIERARCHYID`/`hierarchyid` 用于识别静态方法的 CLR 类时（例如在 `hierarchyid::GetRoot()` 中），它取决于当前数据库上下文是区分大小写还是不区分大小写。当当前数据库区分大小写敏感时，必须使用小写来识别静态方法的 CLR 类。
- 出于排版考虑，我选择将 T-SQL 类型写为 `HIERARCHYID`，但对于代码而言，小写的 `hierarchyid` 是移植性最好的选择。

我之前在自定义模型中这样做，现在我将使用一个员工组织图来演示如何使用 `HIERARCHYID` 类型。运行以下代码创建 `Employees` 表，以及自定义模型中用于支持典型查询的索引：

```sql
IF OBJECT_ID(N'dbo.Employees', N'U') IS NOT NULL DROP table dbo.Employees;

GO

CREATE TABLE dbo.Employees
(
  empid INT NOT NULL,
  hid   HIERARCHYID NOT NULL,
  lvl   AS hid.GetLevel() PERSISTED,
  empname VARCHAR(25) NOT NULL,
  salary MONEY      NOT NULL
);

CREATE UNIQUE CLUSTERED INDEX idx_depth_first ON dbo.Employees(hid);
CREATE UNIQUE INDEX idx_breadth_first ON dbo.Employees(lvl, hid);
ALTER TABLE dbo.Employees ADD CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED(empid);
```

除了存储路径的 `hid` 列外，该表还有一个基于应用于 `hid` 列的 `GetLevel()` 方法的计算列。正如名称所示，该方法返回节点在树中的级别——也就是说，从根节点开始计算。

提醒一下，除了支持请求特定员工查询的 `empid` 列上的显式索引外，代码还创建了两个索引。其中一个用于深度优先请求，以返回子树并按拓扑排序呈现节点；另一个用于广度优先请求，以返回整个层级。

注意，`Employees` 表不包含经理 ID 属性。使用 `HIERARCHYID` 类型，你可以轻松地处理通常需要此类属性的请求。因此，不需要自引用外键。

## 维护数据

每当你需要对树进行更改时（例如添加新的叶子节点或移动子树），你都希望确保能够正确生成新的 `HIERARCHYID` 值或正确地调整现有的值。`HIERARCHYID` 类型的方法和属性可以帮助你完成此类任务。此外，请注意，该类型本身并不强制执行树的有效性——那是你的责任。例如，如果你不通过约束来强制 `HIERARCHYID` 值的唯一性，该类型本身不会拒绝插入具有相同 `HIERARCHYID` 值的尝试。此外，开发一个过程也是你的责任，以防止并发会话在执行树维护任务时为不同的节点产生冲突（相同）`HIERARCHYID` 值。我将解释如何实现这一点。

## 添加员工

添加一个不管理任何人的新员工（叶子节点）的任务需要你为新节点生成一个 `HIERARCHYID` 值，使其在树中的位置正确，然后将新员工插入到表中。运行以下代码创建一个名为 `AddEmp` 的存储过程来实现此项任务：

```sql
-- 存储过程: AddEmp
-- 向表中插入一个不管理任何人的新员工

IF OBJECT_ID(N'dbo.AddEmp', N'P') IS NOT NULL DROP PROC dbo.AddEmp;

GO

CREATE PROC dbo.AddEmp
  @empid AS INT,
  @mgrid AS INT,
  @empname AS VARCHAR(25),
  @salary AS MONEY
AS
  DECLARE
    @hid AS HIERARCHYID,
    @mgr_hid AS HIERARCHYID,
    @last_child_hid AS HIERARCHYID;

  BEGIN TRAN

  IF @mgrid IS NULL
    SET @hid = hierarchyid::GetRoot();
  ELSE
  BEGIN
    SET @mgr_hid = (SELECT hid FROM dbo.Employees WITH (UPDLOCK) WHERE empid = @mgrid);
    SET @last_child_hid = (SELECT MAX(hid) FROM dbo.Employees WHERE hid.GetAncestor(1) = @mgr_hid);
    SET @hid = @mgr_hid.GetDescendant(@last_child_hid, NULL);
  END

  INSERT INTO dbo.Employees (empid, hid, empname, salary)
  VALUES(@empid, @hid, @empname, @salary);

  COMMIT TRAN

GO
```

该过程接受新员工的所有属性：经理 ID、员工姓名和薪资。它应用逻辑生成新员工的 `HIERARCHYID` 值，并将其存储在变量 `@hid` 中。最后，该过程在插入到 `Employees` 表的新行中使用该 `HIERARCHYID` 值 `@hid`。

该过程的代码首先检查传入的员工是否为根节点（即 `manager_id` 为 `NULL`）。在这种情况下，代码使用静态方法 `hierarchyid::GetRoot()` 来计算员工的路径。你可以想象，此方法的目的是为树生成根节点。存储过程的后续部分（`ELSE` 块）处理不为根节点的员工。为了计算该员工的路径，你可以调用 `GetDescendant()` 方法并将其应用于 `@mgr_hid` 变量上。`GetDescendant()` 方法接受两个输入并返回一个位于节点节点的值。如果两个输入都为 `NULL`，该方法生成一个位于兄弟节点之间的值。如果你两次调用该方法并且两种情况下都相同，它将生成相同的输出。防止冲突是你的责任。实现这一简单技术是在 `AddEmp` 过程中运行并指定 `UPDLOCK` 提示，以检索经理路径。请记住，更新锁只能由一个进程持有同一资源。这允许一个会话请求一个新的 `HIERARCHYID` 值。这种简单技术将确保每个会话生成的不同的 `HIERARCHYID` 值。

运行以下代码填充 `Employees` 表：

```sql
EXEC dbo.AddEmp @empid = 1, @mgrid = NULL, @empname = 'David', @salary = 10000.00;
EXEC dbo.AddEmp @empid = 2, @mgrid = 1, @empname = 'Eitan', @salary = 7000.00;
EXEC dbo.AddEmp @empid = 3, @mgrid = 1, @empname = 'Ina', @salary = 7500.00;
EXEC dbo.AddEmp @empid = 4, @mgrid = 2, @empname = 'Seraph', @salary = 5000.00;
EXEC dbo.AddEmp @empid = 5, @mgrid = 2, @empname = 'Jiru', @salary = 5500.00;
EXEC dbo.AddEmp @empid = 6, @mgrid = 2, @empname = 'Eve', @salary = 4500.00;
EXEC dbo.AddEmp @empid = 7, @mgrid = 3, @empname = 'Aaron', @salary = 5000.00;
EXEC dbo.AddEmp @empid = 8, @mgrid = 5, @empname = 'Lilach', @salary = 3500.00;
EXEC dbo.AddEmp @empid = 9, @mgrid = 7, @empname = 'Rita', @salary = 3000.00;
EXEC dbo.AddEmp @empid = 10, @mgrid = 5, @empname = 'Sean', @salary = 3000.00;
EXEC dbo.AddEmp @empid = 11, @mgrid = 7, @empname = 'Gabriel', @salary = 3000.00;
EXEC dbo.AddEmp @empid = 12, @mgrid = 9, @empname = 'Emilia', @salary = 2000.00;
EXEC dbo.AddEmp @empid = 13, @mgrid = 9, @empname = 'Michael', @salary = 2000.00;
EXEC dbo.AddEmp @empid = 14, @mgrid = 9, @empname = 'Didi', @salary = 1500.00;
```



`ToString` 方法返回路径的规范表示，使用斜杠分隔每个层级的值。此查询生成了以下输出：

| hid | path | lvl | empid | empname | salary |
|---|---|---|---|---|---|
| 0x0 | / | 0 | 1 | David | 10000.00 |
| 0x58 | /1/ | 1 | 2 | Eitan | 7000.00 |
| 0x5AC0 | /1/1/ | 2 | 3 | Seraph | 5000.00 |
| 0x5B40 | /1/2/ | 2 | 5 | Jiru | 5500.00 |
| 0x5B56 | /1/2/3/ | 3 | 4 | Lilach | 3500.00 |
| 0x5B5A | /1/2/3/4 | 3 | 10 | Sean | 3000.00 |
| 0x5BC0 | /1/2/3/5/ | 3 | 6 | Steve | 4500.00 |
| 0x628 | /2/ | 1 | 3 | Ina | 7500.00 |
| 0x6AC0 | /2/1/ | 2 | 7 | Aaron | 7500.00 |
| 0x6AD6 | /2/1/1/ | 3 | 9 | Rita | 3000.00 |
| 0x6AD6B | /2/1/1/1/ | 4 | 12 | Emilia | 2000.00 |
| 0x6AD6D | /2/1/1/2/ | 4 | 13 | Michael | 2000.00 |
| 0x6ADF0 | /2/1/1/2/3/ | 4 | 14 | Ddri | 1500.00 |
| 0x6ADA | /2/1/2/3/4/ | 5 | 11 | Gabriel | 3000.00 |

此输出让你直观 `GetDescendant` 方法用于计算值的逻辑。根节点（空字符串）由规范路径 `/` 表示。节点的第一个子包含其对 `GetDescendant` 的 `HIERARCHYID` 调用，并带有两个 `NULL` 输入。结果是父节点的规范路径加上 `/`。因此，根节点的第一个子节点的路径为 `/1`。

如果你在现有节点及其子节点的右侧添加某些内容，新子节点的 `hid` 是通过调用 `GetDescendant` 获取的，将现有节点的 `hid` 作为左输入，`NULL` 作为右输入。新路径值是现有节点的值在最右侧数字加 1。例如，值 `/1/` 在 `/1/` 右侧的值将是 `/2/`。同样，`/1/1` 下方在 `/1/1` 右侧的值将是 `/1/2`。

如果你在某个父节点下并在现有节点的左侧添加某些内容，`GetDescendant` 的输入为 `NULL`，新路径值将是现有节点的值，但其最右侧的数字比它小。例如，`/1/` 下方在 `/1/1/` 左侧的值将是 `/1/0`。

如果你在某个父节点下并向 `GetDescendant` 提供两个父节点现有子节点的 `hid` 值，生成的路径将与现有节点匹配，但最后一个除外。如果现有节点中的数字不是连续的，则新子节点路径的最后一个数字将比该节点大一。例如，当该方法应用于父节点 `/1/1` 且输入节点为 `/1/1/1` 和 `/1/1/4` 时，你得到 `/1/2`。如果输入的最后一个路径数字是连续的，你将得到节点的最后一个数字，后面跟着 `.1`（读作“dot one”）。例如，当该方法应用于父节点 `/1/1` 且输入节点的路径为 `/1/1/1` 和 `/1/1/2` 时，你得到 `/1/1/1/2`。同样，当该方法应用于父节点 `/1/2/3/4/5/` 且输入节点为 `/1/2/3/4/5/2.1.3.4/` 和 `/1/2/1/3/4/5/2.1.3.5/` 时，你得到 `/1/2/3/4/5/2.1.3.5/`。正如你所看到的，如果你既不在最后一个节点的右侧也不在第一个节点的左侧添加新节点，路径就会变得越来越简单。

在章节稍后的部分，“规范化 HIERARCHID 值”部分，我将解释当路径变得过长时如何对其进行规范化。

## 移动子树

`HIERARCHID` 类型支持 `GetReparentValue` 方法，在需要将子树移动到树中的新位置时有助于计算新路径。该方法应用于想要重绘的节点的 `HIERARCHID` 值，但它不会执行实际的修复。它返回一个新值，你可以用它来覆盖现有路径。该方法接受两个输入（调用 `@old_root` 和 `@new_root`），并返回一个目标路径的新值，其中 `@new_root` 替换了 `@old_root`。操作如下：

> **注意**：当你在 `HIERARCHID` h 上调用 `GetReparentValue` 时，`@old_root` 的路径必须是 h 的路径的前缀。如果不是，你将得到 `HierarchicalException` 异常。

例如，如果对规范路径 `/1/1/2/3` 的 `HIERARCHID` 应用 `GetReparentValue` 方法；提供 `/1/` 作为旧根，`/2/1/` 作为新根，你得到规范路径为 `/2/1/4/2` 的 `HIERARCHID`。你可以使用 `CAST` 函数或静态方法将规范表示转换为 `HIERARCHID`，使用上述示例：

```sql
SELECT CAST('/1/1/2/3/' AS HIERARCHID).GetReparentValue('/1/', '/2/1/');
```

你得到输出 `/2/1/4/2`。

考虑到这一点，考虑创建一个名为 `MoveSubtree` 的存储过程，它接受两个输入 `@empid` 和 `@new_grid`。该存储过程的目的是将 `@empid` 子树移动到 `@new_grid` 下。存储过程可以通过三个步骤实现该任务：

- 将 `@new_grid` 和 `@empid` 代表的现有路径存储在变量中（分别调用 `@new_mgr_hid` 和 `@old_root`）。
- 对 `@new_grid` 应用 `GetDescendant` 方法，提供新经理的下属（如果没有则提供 `NULL`）作为输入，以获取员工 `@empid` 下方的新路径。将其存储在变量中（`@new_root`）。
- 更新 `@empid` 代表的所有后代（包括自身）的 `hid` 值为 `@old_root`。可以通过检查表中每个 `hid` 的 `DescendantOf` 方法来识别后代（该方法返回 1）。

运行以下代码创建 `MoveSubtree` 存储过程：

```sql
-- 存储过程: MoveSubtree，
-- 将指定根的子树移动到指定经理的新位置
-------
IF OBJECT_ID('dbo.MoveSubtree', 'N') IS NOT NULL DROP dbo.MoveSubtree;
GO

CREATE PROC dbo.MoveSubtree
    @empid AS INT,
    @new_grid AS INT
AS
DECLARE
    @old_root AS HIERARCHID,
    @new_root AS HIERARCHID,
    @new_mgr_hid AS HIERARCHID;
BEGIN TRAN
SET @new_mgr_hid = (SELECT hid FROM dbo.Employees WITH (UPDLOCK)
    WHERE empid = @new_grid);
SET @old_root = (SELECT hid FROM dbo.Employees
    WHERE empid = @empid);
-- 第一，获取子树根的新 hid
SET @new_root = @new_mgr_hid.GetDescendant(
    ((SELECT MAX(hid)
    FROM dbo.Employees
    WHERE hid.Ancestor(1) = @new_mgr_hid),
    NULL));
-- 接下来，重新安置所有后代
UPDATE dbo.Employees
SET hid = hid.GetReparentValue(@old_root, @new_root)
WHERE hid.DescendantOf(@old_root) = 1;
COMMIT TRAN
GO
```

注意代码使用了显式事务，并在查询目标经理行的第一步获取该行的更新锁。与之前讨论的 `AddEmp` 过程类似，这种技术保证了一次只有一个子树移动到指定目标，防止新生成的 `HIERARCHID` 值发生冲突。

要测试 `MoveSubtree` 存储过程，运行以下代码，将员工 5 (Jiru) 的子树移动到员工 9 (Rita) 下：

```sql
SELECT empid, REPLICATE(' | ', lvl1) + empname AS empname, hid.ToString() AS path
FROM dbo.Employees
ORDER BY hid;
```

```sql
BEGIN TRAN
EXEC dbo.MoveSubtree
    @empid = 5,
    @new_grid = 9;
SELECT empid, REPLICATE(' | ', lvl1) + empname AS empname, hid.ToString() AS path
FROM dbo.Employees
ORDER BY hid;
```

```sql
ROLLBACK TRAN
```

代码展示了数据的前后的状态，因为只是演示，它在事务中运行，因此更改不会提交。以下是该代码的输出，显示子树已正确移动：

| empid | empname | path |
| --- | --- | --- |
| 1 | David | / |
| 2 | Eitan | /1/ |
| 4 | Seraph | /1/1/ |
| 5 | Jiru | /1/2/ |
| 8 | Lilach | /1/2/1/ |
| 10 | Sean | /1/2/ |
| 6 | Steve | /1/3/ |
| 3 | Ina | /2/ |
| 7 | Aaron | /2/1/ |
| 9 | Rita | /2/1/1/ |
| 12 | Emilia | /2/1/1/1/ |
| 13 | Michael | /2/1/1/2/ |
| 14 | Didi | /2/1/1/3/ |
| 11 | Gabriel | /2/1/2/ |

| empid | empname | path |
| --- | --- | --- |
| 1 | David | / |
| 2 | Eitan | /1/ |
| 4 | Seraph | /1/1/ |
| 5 | Jiru | /1/2/ |
| 8 | Lilach | /1/2/1/ |
| 10 | Sean | /1/2/ |
| 6 | Steve | /1/3/ |
| 3 | Ina | /2/ |
| 7 | Aaron | /2/1/ |
| 9 | Rita | /2/1/1/ |
| 12 | Emilia | /2/1/1/1/ |
| 13 | Michael | /2/1/1/2/ |
| 14 | Didi | /2/1/1/3/ |
| 5 | Jiru | /2/1/1/4/ |
| 8 | Lilach | /2/1/1/4/1/ |
| 10 | Sean | /2/1/1/4/2/ |
| 11 | Gabriel | /2/1/2/ |

## 查询

与自定义物化路径解决方案一样，基于 `HIERARCHID` 数据类型的内置物化路径解决方案中的数据查询既简单又优雅。在深度优先和广度优先索引的情况下，你可以让 SQL Server 优化器高效地处理某些类型的请求。

我在这里不会涵盖针对树的所有可能请求，因为它们太多了。相反，我将展示常见请求的示例。像我之前一样，我将为每个请求提供一个示例查询并附带其输出。

## 子图/后代

返回员工 3 的子树，限制输入员工下方的深度为 3 层：

```sql
SELECT E.empid, E.empname
FROM dbo.Employees AS M
INNER JOIN dbo.Employees AS E
ON M.empid = 3
AND E.hid.IsDescendantOf(M.hid) = 1
WHERE E.lvl1 - M.lvl1 <= 3;
```

该查询使用了 `IsDescendantOf` 方法。请记住，如果应用于方法的节点是输入节点的后代，该方法返回 1，否则返回 0。该查询连接了两个 `Employees` 实例：一个代表输入经理（M），另一个代表下属（E）。`ON` 子句中的谓词只过滤出实例 M 中的一行——以及作为 M 中员工后代的一个 `E` 员工。`WHERE` 子句中的谓词只过滤出位于 M 中员工下方三层内的员工。

此查询生成了以下输出：

| empid | empname |
|---|---|
| 3 | Ina |
| 7 | Aaron |
| 9 | Rita |
| 12 | Emilia |
| 13 | Michael |
| 14 | Didi |
| 11 | Gabriel |

此查询的执行计划如图（顶部的）所示，负责从 `empid` 列的索引中返回员工 3 的行。然后，`Compute Scalar`（第二个）通过调用名为 `DescendantLimit` 的内部方法计算请求子树的 `HIERARCHID` 值的上边界点，并将结果存储在变量 `Expr1002` 中。请记住，由于 `HIERARCHID` 值提供了拓扑排序，因此 `hid` 列上的索引允许访问同一子树的所有成员。计划中的第二个 `Index Seek` 算符（底部的）基于 `E.hid >= M.hid AND E.hid <= Expr1002` 对 `hid` 索引执行范围扫描。此计划对于此类请求来说已经是非常理想的了，因为 SQL Server 最终扫描了适用子树的成员。

![](img/bdc38aa36f6e2987d913ee5381474711_788_0.png)

| SELECT | Nested Loops (Inner Join) | Compute Scalar (Cost: 0 %) | Compute Scalar (Cost: 0 %) | Index Seek (NonClustered) [Employees], [PK_Employees] [M] (Cost: 50 %) |
|---|---|---|---|---|
| Cost: 0 % | Cost: 0 % | | | |

Expr1002 = M.hid.DescendantLimit()

Clustered Index Seek (Clustered) [Employees], [idx_depth_first] [E] (Cost: 50 %)

```

Predicate
[tempdb].dbo [Employees] as [E], [Iv] as [I]-[Expr1004] <= (3)

Object
[tempdb].dbo [Employees].idx_depth_first [E]

Output List
[tempdb].dbo [Employees].empid, [tempdb].dbo.[Employees].empname

Seek Predicate
Seek Keq [1] Start [tempdb].dbo, [Employees].hid >= Scalar Operator([tempdb].dbo, [Employees].hid as [M]), [hid]. End [tempdb].dbo, [Employees].hid < Scalar Operator([Expr1002])

```

**图 11-7** `HIERARCHID` 子树查询的执行计划。

## 祖先/路径

接下来，我将解释如何处理返回指向特定员工路径上的所有经理的请求。你可以实现与处理子树请求相似的解决方案。与其过滤代表单个经理的行（来自 `Employees` 实例 M）并然后返回所有符合条件的下属的属性（来自另一个实例 E），不如过滤掉代表该员工的行，并返回所有符合条件的经理的属性。例如，以下查询返回员工 14 的所有经理（或间接经理）：

```sql
SELECT M.empid, M.empname
FROM dbo.Employees AS M
INNER JOIN dbo.Employees AS E
ON E.empid = 14
AND E.hid.IsDescendantOf(M.hid) = 1;
```

此查询生成了以下输出：

| empid | empname |
|---|---|
| 1 | David |
| 3 | Ina |
| 7 | Aaron |
| 9 | Rita |
| 14 | Didi |

尽管此查询与实现子树请求的查询相似，但它无法被高效地优化。这是因为同一路径的成员并不位于索引的连续范围内。

## 子级/直接下属

接下来，我将描述如何处理获取员工直接下属的请求。为了处理此请求，你可以使用与之前的查询类似的连接形式。从 `Employees` 实例 (M) 中过滤出你想要的员工下属的行，并从另一个实例 E 中返回所有父级为过滤出的员工的员工。一个节点的父级是其祖先，输入值为 1 的 `GetAncestor` 方法返回 `HIERARCHID` 值。作为查找直接下属的示例，以下查询返回员工 2 的直接下属：

```sql
SELECT E.empid, E.empname
FROM dbo.Employees AS M
INNER JOIN dbo.Employees AS E
ON M.empid = 2
AND E.hid.GetAncestor(1) = M.hid;
```



此代码生成了以下输出：

| empid | empname |
|---|---|
| 4 | Seraph |
| 5 | Jiru |
| 6 | Steve |

## 叶子节点

你也可以使用输入值为 1 的 `GetAncestor` 方法来识别叶子节点，即没有管理其他员工的员工。这种逻辑可以使用 `NOT EXISTS` 谓词实现：

```sql
SELECT empid, empname
FROM dbo.Employees AS M
WHERE NOT EXISTS (SELECT * FROM dbo.Employees AS E WHERE E.hid.GetAncestor(1) = M.hid);
```

此代码生成了以下输出：

| empid | empname |
|---|---|
| 4 | Seraph |
| 8 | Lilach |
| 10 | Sean |
| 6 | Steve |
| 12 | Emilia |
| 13 | Michael |
| 14 | Didi |

## 展示

最后，为了展示层级结构使得下属出现在经理的下方右侧，请使用以下查询：

```sql
SELECT REPLICATE(' ', lvl) + empname AS empname, hid.ToString() AS path
FROM dbo.Employees
ORDER BY hid;
```

记住 `HIERARCHID` 数据类型提供了拓扑排序，因此你只需要对 `hid` 属性进行排序。缩进通过重复字符串实现。此查询生成了以下输出：

```
empname             path

David

| Ina             /1/

| Seraph           /1/1/

| Jiru              /1/2/

| | Lilach          /1/2/1/

| | Sean            /1/2/2/

| | | Steve           /1/3/

| Ina               /2/

| | Aaron             /2/1/

| | | Rita              /2/1/1/

| | | | Emilia         /2/1/1/1/

| | | | Michael         /2/1/1/2/

| | | | | Didi             /2/1/1/3/

| | | | Gabriel         /2/1/2/
```

此查询的执行计划如图 11-8 所示。

![](img/bdc38aa36f6e2987d913ee5381474711_790_0.png)

**图 11-8** HIERARCHID 排序查询的执行计划。你可以看到优化器通过索引扫描高效地处理了该请求。

## 处理层次的其他方面

本节介绍了处理层次类型的其他方面。我将解释路径可能变长的情况，并提供一个规范它们的解决方案。我将向你展示如何将邻接列表表示转换为基于 `HIERARCHID` 数据类型的表示。最后，我将向你展示如何使用 `HIERARCHID` 数据类型对值列表进行排序。

## 规范 HIERARCHID

当你使用 `HIERARCHID` 数据类型表示树时，某些路径可能会变得很长。对于深度树，这是自然的，因为 `HIERARCHID` 值代表了从根节点到当前节点的路径。然而，在某些情况下，即使树不深，路径也可能变长。首先，我将解释发生这种情况的情况，然后提供一个规范这些值使其更短的解决方案。注意，在本节中，*规范*（normalizing）一词并非指数据库规范化。

当你不断在路径数字连续的现有节点之间添加新节点时，`HIERARCHID` 值可能会变得很大。例如，假设节点路径为 `/1/` 和 `/2/` 并在它们之间添加一个节点。你得到了一个路径为 `/1.1/` 的新节点。现在在 `/1.1/` 和 `/2/` 之间添加一个 `/1.2/`。现在在 `/1/` 和 `/1.2/` 之间添加一个 `/1.1/`。正如你所见，如果你这样在现有节点之间添加节点，即使树不深，也会得到长路径（代表很长的 `HIERARCHID` 值）。

如果兄弟节点之间的顺序不重要，你可以始终在最后一个现有孩子之后或第一个之前添加新节点；这样路径更高效。当兄弟之间的顺序很重要时，你无法控制这一点。如果你频繁在节点之间添加新节点，可能会得到非常长的 `HIERARCHID` 值。在这种情况下，你可以定期运行一个过程（我在这里提供），该过程会对整个图的 `HIERARCHID` 值进行规范，使其变短。

运行以下代码创建 `AddEmp` 过程的新版本：

```sql
-- 存储过程：AddEmp
-- 向表中插入没有经理的新员工
IF OBJECT_ID('dbo.AddEmp', 'P') IS NOT NULL
    DROP PROC dbo.AddEmp;
GO

CREATE PROC dbo.AddEmp
    @empid INT,
    @mgrid INT,
    @leftempid INT,
    @rightempid INT,
    @empname VARCHAR(25),
    @salary MONEY = 1000
AS
BEGIN
    DECLARE @hid AS HIERARCHY::NULL;

    IF @mgrid IS NULL
        SET @hid = hierarchy::GetRoot();
    ELSE
        SET @hid = (SELECT hid FROM dbo.Employees WHERE empid = @mgrid).GetDescendant(
            (SELECT hid FROM dbo.Employees WHERE empid = @leftempid),
            (SELECT hid FROM dbo.Employees WHERE empid = @rightempid));

    INSERT INTO dbo.Employees(empid, hid, empname, salary)
    VALUES(@empid, @hid, @empname, @salary);
END;
```

此版本接受你想要在其中添加新员工的两个子员工的 ID。

接下来，运行以下代码，它将清空 Employees 表并按如下方式填充数据，产生长度路径：

```sql
TRUNCATE TABLE dbo.Employees;

EXEC dbo.AddEmp @empid = 1, @mgrid = NULL, @leftempid = NULL, @rightempid = NULL, @empname = 'A';
EXEC dbo.AddEmp @empid = 2, @mgrid = 1, @leftempid = NULL, @rightempid = NULL, @empname = 'B';
EXEC dbo.AddEmp @empid = 3, @mgrid = 1, @leftempid = NULL, @rightempid = NULL, @empname = 'C';
EXEC dbo.AddEmp @empid = 4, @mgrid = 1, @leftempid = NULL, @rightempid = 3, @empname = 'D';
EXEC dbo.AddEmp @empid = 5, @mgrid = 1, @leftempid = NULL, @rightempid = 3, @empname = 'E';
EXEC dbo.AddEmp @empid = 6, @mgrid = 1, @leftempid = NULL, @rightempid = 5, @empname = 'F';
EXEC dbo.AddEmp @empid = 7, @mgrid = 1, @leftempid = NULL, @rightempid = 5, @empname = 'G';
EXEC dbo.AddEmp @empid = 8, @mgrid = 1, @leftempid = NULL, @rightempid = 7, @empname = 'H';
EXEC dbo.AddEmp @empid = 9, @mgrid = 8, @leftempid = NULL, @rightempid = NULL, @empname = 'I';
EXEC dbo.AddEmp @empid = 10, @mgrid = 8, @leftempid = 9, @rightempid = NULL, @empname = 'J';
EXEC dbo.AddEmp @empid = 11, @mgrid = 8, @leftempid = 9, @rightempid = 10, @empname = 'K';
EXEC dbo.AddEmp @empid = 12, @mgrid = 8, @leftempid = 11, @rightempid = 10, @empname = 'L';
EXEC dbo.AddEmp @empid = 13, @mgrid = 8, @leftempid = 11, @rightempid = 12, @empname = 'M';
EXEC dbo.AddEmp @empid = 14, @mgrid = 8, @leftempid = 13, @rightempid = 12, @empname = 'N';
EXEC dbo.AddEmp @empid = 15, @mgrid = 8, @leftempid = 13, @rightempid = 14, @empname = 'O';
EXEC dbo.AddEmp @empid = 16, @mgrid = 8, @leftempid = 15, @rightempid = 14, @empname = 'P';
EXEC dbo.AddEmp @empid = 17, @mgrid = 8, @leftempid = 15, @rightempid = 16, @empname = 'Q';
EXEC dbo.AddEmp @empid = 18, @mgrid = 8, @leftempid = 17, @rightempid = 16, @empname = 'Q';
EXEC dbo.AddEmp @empid = 19, @mgrid = 8, @leftempid = 17, @rightempid = 18, @empname = 'E';
EXEC dbo.AddEmp @empid = 20, @mgrid = 8, @leftempid = 19, @rightempid = 18, @empname = 'S';
EXEC dbo.AddEmp @empid = 21, @mgrid = 8, @leftempid = 19, @rightempid = 20, @empname = 'T';
```

然后运行以下代码以显示 `HIERARCHID` 值及其规范化路径：

```sql
SELECT empid, REPLICATE('| ', lvl) + empname AS emp, hid.ToString() AS path
FROM dbo.Employees
ORDER BY hid;
```

你将得到如下输出：

| emid | emp | hid | path |
|---|---|---|---|
| 1 | A | 0x | /1/ |
| 2 | B | 0x58 | /1/ |
| 4 | D | 0x60 | /1/ |
| 6 | F | 0x16 | /1/ |
| 8 | H | 0x80 | /1/ |
| 9 | I | 0x50 | /1/ |
| 11 | K | 0x2C | /1/ |
| 13 | L | 0x60 | /1/ |
| 15 | N | 0x88 | /1/ |
| 17 | P | 0x58 | /1/ |
| 19 | E | 0x20 | /1/ |
| 21 | T | 0x36 | /1/ |
| 20 | S | 0x40 | /1/ |
| 18 | Q | 0x68 | /1/ |
| 16 | O | 0x3D | /1/ |
| 14 | M | 0xA0 | /1/ |
| 12 | J | 0x34 | /1/ |
| 10 | J | 0x80 | /1/ |
| 7 | G | 0x1A | /2/ |
| 5 | E | 0x40 | /2/ |
| 3 | C | 0x68 | /2/ |

如你所示，树的深度为三层，某些 `HIERARCHID` 值因为插入顺序变得很长。

规范化值的解决方案涉及以下步骤：

1. 定义一个 CTE `EmpsRN`，按分区计算每个行号，并按值排序。
2. 定义一个递归 CTE `EmpPath`，遍历树的层级，从根节点开始进入下一层子节点。此 CTE 为每个节点构造规范路径。根应分配 `/`，对于下一层的每个节点，通过拼接父节点路径、当前节点的行号以及一个 `/` 字符获取路径。
3. 将 `Employees` 表与 `EmpPaths` 联接，并使用上一步生成的规范路径更新现有的 `hid` 值。

以下是执行规范化的代码：

```sql
WITH EmpsRN AS
(
    SELECT empid, hid, ROW_NUMBER() OVER(PARTITION BY hid.GetAncestor(1) ORDER BY hid) AS rownum
    FROM dbo.Employees
),
EmpPaths AS
(
    SELECT empid, hid, CAST('/' AS VARCHAR(900)) AS path
    FROM dbo.Employees
    WHERE hid = hierarchyid::GetRoot()

    UNION ALL

    SELECT C.empid, C.hid, CAST(P.path + CAST(C.rownum AS VARCHAR(20)) + '/' AS VARCHAR(900)) AS path
    FROM EmpPaths AS P
    INNER JOIN EmpsRN AS C
    ON C.hid.GetAncestor(1) = P.hid
)
UPDATE E
SET hid = CAST(EP.path AS HIERARCHID)
FROM dbo.Employees E
INNER JOIN EmpPaths AS EP
ON E.empid = EP.empid;
```

现在查询规范化后的数据：

```sql
SELECT empid, REPLICATE('| ', lvl) + empname AS emp, hid, hid.ToString() AS path
FROM dbo.Employees
ORDER BY hid;
```

从输出中可以看到，你获得了紧凑路径：

| emid | emp | hid | path |
|---|---|---|---|
| 1 | A | 0x | /1/ |
| 2 | B | 0x58 | /1/ |
| 4 | D | 0x68 | /2/ |
| 6 | F | 0x78 | /3/ |
| 8 | H | 0x84 | /4/ |
| 9 | I | 0x860 | /4/ |
| 11 | K | 0x5A0 | /4/ |
| 13 | L | 0x5E0 | /4/ |
| 15 | N | 0x610 | /4/ |
| 17 | P | 0x630 | /4/ |
| 19 | E | 0x650 | /6/ |
| 21 | T | 0x670 | /7/ |
| 20 | S | 0x688 | /8/ |
| 18 | O | 0x698 | /9/ |
| 16 | M | 0x8A8 | /10/ |
| 14 | J | 0x8B8 | /11/ |
| 10 | J | 0x8D | /13/ |
| 7 | G | 0x8C | /5/ |
| 5 | E | 0x94 | /6/ |
| 3 | C | 0x9C | /7/ |

## 将父子表示法转换为 HIERARCHID

本节解释了如何将基于邻接列表（父子关系）的现有树表示法转换为基于 `HIERARCHID` 数据类型的表示法。

以下创建并填充 `EmployeesOld` 表的代码实现了员工树的邻接列表表示：

```sql
IF OBJECT_ID('dbo.EmployeesOld') IS NOT NULL DROP TABLE EmployeesOld;
IF OBJECT_ID('dbo.EmployeesNew') IS NOT NULL DROP TABLE EmployeesNew;
GO

CREATE TABLE dbo.EmployeesOld(
    empid INT PRIMARY KEY,
    mgrid INT NULL,
    empname VARCHAR(25),
    salary MONEY
);

CREATE UNIQUE INDEX idx_mgrid_empname ON dbo.EmployeesOld(mgrid, empname);

INSERT INTO dbo.EmployeesOld(empid, mgrid, empname, salary)
VALUES
(1, NULL, 'A', 1000),
(2, 1, 'B', 2000),
(3, NULL, 'C', 3000),
(4, 1, 'D', 4000),
(5, 1, 'E', 5000),
(6, 1, 'F', 6000),
(7, 1, 'G', 7000),
(8, 1, 'H', 8000),
(9, 8, 'I', 9000),
(10, 8, 'J', 10000),
(11, 8, 'K', 11000),
(12, 8, 'L', 12000);
```



(13, 8, 'M', 13000),

(14, 8, 'N', 14000),

(15, 8, 'O', 15000),

(16, 8, 'P', 16000),

(17, 8, 'Q', 17000),

(18, 8, 'Q', 18000),

(19, 8, 'E', 19000),

(20, 8, 'S', 20000),

(21, 8, 'T', 21000);

```

使用 `HIERARCHYID` 数据类型创建 `Employees` 表所需的代码：

```sql
CREATE TABLE dbo.Employees(
  empid INT PRIMARY KEY,
  hid HIERARCHYID NOT NULL,
  lvl AS hid.GetLevel() PERSISTED,
  empname VARCHAR(25),
  salary MONEY
);
```

（注：此处部分 SQL 原文存在逻辑混乱或断句，已根据原文结构进行翻译对齐，以保持格式一致）

运行以下代码以显示转换后 `EmployeesNew` 表的内容：

```sql
SELECT REPLICATE('| ', lvl) + empname AS empname, hid.ToString() AS path
FROM dbo.EmployeesNew
ORDER BY hid;
```

你将如下输出：

| empname | path |
| :--- | :--- |
| David | / |
| | Eitan | /1/ |
| | | Seraph | /1/ |
| | | | Jiru | /1/2/ |
| | | | Lilach | /1/2/1/ |
| | | | Sean | /1/2/2/ |
| | | | Steve | /1/3/ |
| Ina | /2/ |
| | Aaron | /2/1/ |
| | Rita | /2/1/1/ |
| | | Emilia | /2/1/1/1/ |
| | | Michael | /2/1/2/1/ |
| | | | Didi | /2/1/2/3/ |
| | | | Gabriel | /2/1/2/ |

## 排序由分隔符值的列表

某些应用程序以字符字符串的形式通过分离的值列表来存储有关数组和数字列表的信息。我在这里不会讨论这种数据表示形式是否真的合适。相反，我将处理涉及此类表示的特定需求。有时你无法控制字符系统的设计，并且需要使用现有设计为请求提供解决方案。

当前的任务涉及对列表进行排序，但基于元素的数值而不是它们的字符表示。例如，考虑列表 `'13,41,17'` 和 `'13,41,3'`。如果根据元素的字符表示对列表进行排序，前者将排在后者之前，因为字符 `'1'` 被认为比字符 `'3'` 小。你希望第二个字符串排在第一个字符串之前，因为数字 3 比数字 17 小。

这个问题的一个特殊情况是排序表示为字符字符串的 IP 地址。在这种特殊情况下，你可以确信每个字符串始终恰好包含四个元素，且每个元素的长度从未超过三位数字。我将首先涵盖这个特殊情况，然后讨论更通用的情况。

运行以下代码创建 `IPs` 表并填充一些 IP 地址：

```sql
IF OBJECT_ID(N'dbo.IPs', N'U') IS NOT NULL DROP TABLE dbo.IPs;
GO

-- 表 IPs 的创建脚本
CREATE TABLE dbo.IPs
(
  ip varchar(15) NOT NULL,
  CONSTRAINT PK_IPS PRIMARY KEY(ip),
  -- 验证 IPs 的 CHECK 
  CONSTRAINT CHK_IP_valid CHECK (
    -- 3 个点且没有空节
    ip LIKE '%_%._%._%_%'
    AND
    -- 不是 4 个或更多点
    ip NOT LIKE '%_%._%._%._%_%'
    AND
    -- 没有除数字和点以外的字符
    ip NOT LIKE '%[^0-9.-]%'
    AND
    -- 每个节不超过 3 位数字
    ip NOT LIKE '%[0-9][0-9][0-9]%'
    AND
    -- 不是 300 - 999
    ip NOT LIKE '%[3-9][0-9][0-9]%'
    AND
    -- 不是 260 - 299
    ip NOT LIKE '%2[6-9][0-9]%'
    AND
    -- 不是 256 - 259
    ip NOT LIKE '%25[6-9]%'
  );
GO

-- 示例数据
INSERT INTO dbo.IPs(ip) VALUES
('131.107.2.201'),
('131.33.2.201'),
('131.33.2.202'),
('3.107.2.4'),
('3.107.3.169'),
('3.107.104.172'),
('22.20.2.77'),
('22.156.9.91'),
('22.156.89.32');
```

我将描述用于 `HIERARCHY` 类型的一种解决方案。IP 地址必须是 81 种可能模式之一（我们讨论的是 IPv4）。你可以编写一个谓词来产生每个节的所有可能模式。你可以使用一个包含三个节长度的辅助数字表。通过连接 `nums` 表四次，你可以得到四个节的变体。然后使用 `nums` 表构造 IP 地址，计算每个节的起始位置和长度。运行以下代码创建并查询 `IPPatterns`，它实现了此逻辑：

```sql
IF OBJECT_ID('dbo.IPPatterns', 'V') IS NOT NULL DROP VIEW dbo.IPPatterns;
CREATE VIEW dbo.IPPatterns
AS
SELECT
REPLICATE('_', N1) + '.' + REPLICATE('_', N2) + '.' +
REPLICATE('_', N3) + '.' + REPLICATE('_', N4) AS pattern,
N1 AS s1, N2 AS s2, N3 AS s3, N4 AS s4
FROM TSQLV.dbo.Nums AS N1
JOIN TSQLV.dbo.Nums AS N2
JOIN TSQLV.dbo.Nums AS N3
JOIN TSQLV.dbo.Nums AS N4
WHERE N1 <= 3 AND N2 <= 3 AND N3 <= 3 AND N4 <= 3;

SELECT pattern, l1, l2, l3, l4, s1, s2, s3, s4 FROM IPPatterns;
```

当你查询它时，你将得到可能的 IP 模式以及每个模式的起始位置和长度，如下简略格式所示：

| pattern | l1 | l2 | l3 | l4 | s1 | s2 | s3 | s4 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ... | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| ... | 1 | 1 | 1 | 2 | 1 | 1 | 1 | 2 |
| ... | 1 | 1 | 1 | 3 | 1 | 1 | 1 | 3 |
| ... | 1 | 1 | 2 | 1 | 1 | 1 | 2 | 1 |
| ... | 1 | 1 | 2 | 2 | 1 | 1 | 2 | 2 |
| ... | 1 | 1 | 2 | 3 | 1 | 1 | 2 | 3 |
| ... | 1 | 2 | 1 | 1 | 1 | 2 | 1 | 1 |
| ... | 1 | 2 | 1 | 2 | 1 | 2 | 1 | 2 |
| ... | 1 | 2 | 1 | 3 | 1 | 2 | 1 | 3 |
| ... | 1 | 2 | 2 | 1 | 1 | 2 | 2 | 1 |
| ... | 1 | 2 | 2 | 2 | 1 | 2 | 2 | 2 |
| ... | 1 | 2 | 2 | 3 | 1 | 2 | 2 | 3 |
| ... | 2 | 1 | 1 | 1 | 2 | 1 | 1 | 1 |
| ... | 2 | 1 | 1 | 2 | 2 | 1 | 1 | 2 |
| ... | 2 | 1 | 1 | 3 | 2 | 1 | 1 | 3 |
| ... | 2 | 1 | 2 | 1 | 2 | 1 | 2 | 1 |
| ... | 2 | 1 | 2 | 2 | 2 | 1 | 2 | 2 |
| ... | 2 | 1 | 2 | 3 | 2 | 1 | 2 | 3 |
| ... | 2 | 2 | 1 | 1 | 2 | 2 | 1 | 1 |
| ... | 2 | 2 | 1 | 2 | 2 | 2 | 1 | 2 |
| ... | 2 | 2 | 1 | 3 | 2 | 2 | 1 | 3 |
| ... | 2 | 2 | 2 | 1 | 2 | 2 | 2 | 1 |
| ... | 2 | 2 | 2 | 2 | 2 | 2 | 2 | 2 |
| ... | 2 | 2 | 2 | 3 | 2 | 2 | 2 | 3 |

当然，你可以实现类似的逻辑来创建 IPv6 的可能 IP 地址。

现在你可以编写一个查询，将 `IPs` 表与 `IPPatterns` 视图连接起来，基于 IP 地址与 IP 模式之间的匹配。这识别了每个 IP 地址的模式，以及每个节的起始位置和长度。你可以在 `ORDER BY` 子句中指定四个表达式，使用 `SUBSTRING` 函数提取节，并将节的字符表示转换为数值。该查询的形式如下：

```sql
SELECT ip
FROM dbo.IPs
INNER JOIN dbo.IPPatterns
ON ip LIKE pattern
ORDER BY
CAST(SUBSTRING(ip, s1, l1) AS INT),
CAST(SUBSTRING(ip, s2, l2) AS INT),
CAST(SUBSTRING(ip, s3, l3) AS INT),
CAST(SUBSTRING(ip, s4, l4) AS INT);
```

此查询生成如下输出：

```
3.107.2.4
3.107.3.169
3.107.104.172
22.20.2.77
22.107.202.123
22.156.9.91
22.156.89.32
131.107.2.201
131.33.2.201
131.33.2.202
```

## 嵌套集合

嵌套集合解决方案是我过的用于树形建模的最优解决方案之一。

> 更多信息：Joe Celko 在他的著作中对嵌套集合模型进行了详尽介绍。你可以在他的书籍《Joe Celko's Sets and Hierarchies SQL for Smarties, Second Edition》(Morgan Kaufmann, 2012) 中找到他对嵌套集的讲解。

嵌套集合方案的主要优点是查询简单且快速，我稍后会描述；遗憾的是，对于大型数据集，该方案的实用性通常仅限于静态树。对于发生频繁变化的动态环境，该方案适用于小树（或小树的森林）。

该方案没有将树表示为邻接列表（父子关系），而是将树形关系建模为嵌套集合。在嵌套集合模型中，父节点表示为一个容器，子节点表示为被包含的集合。包含关系通过分配给每个集合的两个整数值表示：左（left）和右（right）。对于所有集合，一个集合的左值小于所有被包含集合的左值，该集合的右值大于所有被包含集合的右值。自然地，这种包含关系在 n 级关系（祖先/后代）上是传递的。查询基于这些嵌套集合关系。逻辑上讲，这就像一个集合伸出双臂环住了它所包含的所有集合。

### 分配左值和右值

图 11-9 提供了员工树的图形可视化，并为每个员工分配了左值和右值。

![](img/bdc38aa36f6e2987d913ee5381474711_802_0.png)

图 11-9 作为嵌套集合的员工层级。

遍历树的曲线代表左右值的赋值顺序。请注意，你选择的模型决定了分配兄弟节点值的顺序。在这种情况下，我选择了按照员工名称顺序遍历兄弟节点。

你从根节点开始，逆时针遍历树。每当你进入一个节点时，计数器加1并将其设置为节点的左值。每当你离开一个节点时，计数器加1并将其设置为节点的右值。该算法可以实现为迭代或递归程序，为每个节点分配左值和右值。然而，这种实现方式每次遍历一个节点，速度要快得多。核心算法基于我们在前面讨论的逻辑，即每次遍历一层树并计算二进制路径。要理解此算法，请参见图 11-10。

![](img/bdc38aa36f6e2987d913ee5381474711_803_0.png)

图 11-10 嵌套集合模型。该图说明了员工如何遍历其后属。现在可以通过简单递增计数器来分配左右值。记住这个插图——它是理解该解决方案的关键。再次，基准是每次遍历一个子树的原始算法。

> 注意：为了良好的性能，你应该在列上创建索引（例如，`mgrid`, `empid`）。

与其为每个节点生成一行，不如通过连接带有两个数字的辅助表生成两行：`n=1` 代表左，`n=2` 代表右。二进制路径仍然是从行中构建的，但在这种情况下考虑了数字。查询下一层将返回后属。以下代码是该算法的 CTE 实现，其目的是为每个员工生成两个二进制路径以计算左右值。在运行此代码之前，请确保你已经在 `tempdb` 数据库中有了原始 `Employees` 表。如果没有，请运行列表 11-1 中的代码：按 `mgrid`, `empid` 排序。

```sql
CREATE UNIQUE INDEX idx_mgrid_empid ON dbo.Employees(mgrid, empid);
```

### 第 11 章 图与递归查询

```sql
DECLARE @root INT = 1;

-- CTE 两个数字：1 和 2
WITH TwoNums AS (
    SELECT n FROM (VALUES(1),(2)) AS D(n)
)

-- 每个节点的两个二进制排序路径
-- 小于后代的二进制路径
-- 大于后代的二进制路径
SortPath AS (
    SELECT empid, 0 AS lvl, CAST(CAST(n AS BINARY(4)) AS VARBINARY(MAX)) AS sort_path
    FROM dbo.Employees CROSS JOIN TwoNums
    WHERE empid = @root
    UNION ALL
    SELECT C.empid, P.lvl + 1,
    P.sort_path + CAST(
        -1 + ROW_NUMBER() OVER(PARTITION BY C.mgrid ORDER BY C.empname, C.empid) / 2 * 2 + TN.n
        AS BINARY(4))
    FROM SortPath AS P
    INNER JOIN dbo.Employees AS C
    ON P.n = 1
    AND C.mgrid = P.empid
    CROSS JOIN TwoNums AS TN
)

SELECT empid, lvl, sort_path FROM SortPath;
```

此代码生成以下输出：

| empid | lvl | sort_path |
| :--- | :--- | :--- |
| 1 | 0 | 0x00000001 |
| 2 | 1 | 0x0000000100000001 |
| 5 | 2 | 0x000000010000000100000001 |
| 8 | 3 | 0x00000001000000010000000100000001 |
| 8 | 3 | 0x0000000100000001000000010000000100000001 |
| 10 | 3 | 0x0000000100000001000000010000000100000003 |
| 10 | 3 | 0x000000010000000100000001000000010000000100000003 |
| 5 | 2 | 0x00000001000000010000000100000002 |
| 4 | 2 | 0x00000001000000010000000100000004 |
| 4 | 2 | 0x0000000100000001000000010000000400000004 |
| 6 | 2 | 0x00000001000000010000000100000005 |
| 6 | 2 | 0x00000001000000010000000100000005 |
| 2 | 1 | 0x00000001 |
| 3 | 1 | 0x00000001 |
| 7 | 2 | 0x00000001000000010000000100000003 |
| 11 | 3 | 0x00000001000000010000000100000003 |
| 11 | 3 | 0x0000000100000001000000010000000300000002 |
| 9 | 3 | 0x0000000100000001000000010000000100000003 |
| 14 | 4 | 0x000000010000000100000001000000010000000000000000 |
| 14 | 4 | 0x000000010000000100000001000000030000000100000002 |
| 12 | 4 | 0x000000010000000100000001000000010000000300000003 |
| 12 | 4 | 0x00000001000000010000000100000001000000030000000300000004 |



## CTE with Row Numbers Representing sort_path

```sql
Sort AS
{
  SELECT empid, lvl1, ROW_NUMBER() OVER(ORDER BY sort_path) AS sortval
  FROM SortPath
},
```

## CTE with Left and Right Values Representing Nested Sets Relationships

```sql
NestedSets AS
{
  SELECT empid, lvl1, MIN(sortval) AS lft, MAX(sortval) AS rgt
  FROM Sort
  GROUP BY empid, lvl1
}

SELECT empid, lvl1, lft, rgt FROM NestedSets
ORDER BY lft;
```

| empid | lvl1 | lft | rgt |
|---|---|---|---|
| 1 | 0 | 1 | 28 |
| 2 | 1 | 2 | 13 |
| 5 | 2 | 3 | 8 |
| 8 | 3 | 4 | 5 |
| 10 | 3 | 6 | 7 |
| 4 | 2 | 9 | 10 |
| 6 | 2 | 11 | 12 |
| 1 | 3 | 14 | 27 |
| 7 | 2 | 15 | 26 |
| 11 | 3 | 16 | 17 |
| 9 | 3 | 18 | 25 |
| 14 | 4 | 19 | 20 |
| 12 | 4 | 21 | 22 |
| 13 | 4 | 23 | 24 |

记住我之前提供的关于排序路径中每个元素目标类型的提示，该类型取决于单个父节点可以拥有的最大子节点数量。在我的示例中使用 `BINARY(4)`，但请记住在某些情况下可以使用较小的尺寸。

在“嵌套集合（Nested sets）”的第一段中，我提到该解决方案适用于动态树（频繁变化的树）。假设你在 `Employees` 表的两个额外列中存储了左值和右值。请注意，你不再需要表中的 `mgrid` 列，带有左和右值的两个列就足够回答关于下属、祖先等请求了。考虑向树中添加节点时产生的“震动效应”。例如，查看图 11-9 和 11-10，并尝试找出给 Steve 添加一个新下属的影响。

Steve 的左值和右值分别为 11 和 12。新节点应该获得 12 和 13 的左值和右值。Steve 的右值——实际上是树中所有大于等于 12 的左右值——应该增加 2。平均而言，每当插入新节点时，树中一半的节点必须更新。正如你在这里看到的，这种震动效应是剧烈的。如果树是静态的，或者你需要定期对树的静态快照运行查询，那么嵌套集合解决方案就是足够的的。

嵌套集合对于较小的动态树（小树森林）可以提供相当不错的性能——例如，在维护论坛讨论时，其中每个线程都是森林中一棵独立的树。你可以实现一种随每次更改都同步树的左和右值的解决方案。你可以通过使用存储过程或触发器来实现这一点，只要修改成本足够小到可以承受。我不会涉及维护值之间间隙的嵌套集合模型变体（即留出空间以便无需大量工作即可插入新叶节点），因为它们最终都是受限的。

要生成一个包含员工 ID、员工名称、薪水、级别、左值和右值的员工表 (`EmployeesNS`)，连接 CTE 解决方案的外部查询并使用 `SELECT INTO` 语句。运行以下代码以创建此 `EmployeesNS` 表，并按 `empname` 排序兄弟节点：

```sql
DECLARE @root AS INT = 1;

WITH TwoNums AS
(
  SELECT n FROM (VALUES(1),(2)) AS D(n)
),
SortPath AS
(
  SELECT empid, 0 AS lvl, CAST(n AS BINARY(4)) AS VARBINARY(MAX) AS sort_path
  FROM dbo.Employees CROSS JOIN TwoNums
  WHERE empid = @root
  UNION ALL
  SELECT C.empid, P.lvl + 1, TN.n,
  P.sort_path + CAST(
  (-1 + ROW_NUMBER() OVER(PARTITION BY C.mgrid
  -- 决定兄弟节点的顺序
  ORDER BY C.empname, C.empid)) / 2 = 2 + TN.n
  AS BINARY(4))
  FROM SortPath AS P
  INNER JOIN dbo.Employees AS C
  ON P.n = 1
  AND C.mgrid = P.empid
  CROSS JOIN TwoNums AS TN
),
Sort AS
(
  SELECT empid, lvl, ROW_NUMBER() OVER(ORDER BY sort_path) AS sortval
  FROM SortPath
),
NestedSets AS
(
  SELECT empid, lvl, MIN(sortval) AS lft, MAX(sortval) AS rgt
  FROM Sort
  GROUP BY empid, lvl
)
```

```sql
SELECT E.emid, E.empname, E.salary, NS.lft, NS.lft, NS.rgt
INTO dbo.EmployeesNS
FROM NestedSets AS NS
  INNER JOIN dbo.Employees AS E
  ON E.emid = NS.emid;
```

```sql
CREATE UNIQUE CLUSTERED INDEX idx_uc_lft ON EmployeesNS(lft);
ALTER TABLE EmployeesNS ADD PRIMARY KEY (emid);
```

## 查询

`EmployeesNS` 表将员工模型为嵌套集合。查询是简单、优雅且快速的（假设你在 `lft` 上有索引）。在接下来的章节中，我将针对树的常见请求给出解决方案，然后是查询的输出：

### 返回给定根节点的子树

```sql
SELECT C.emid, REPLICATE(' | ', C.lft - P.lft) + C.empname
FROM EmployeesNS AS P
  INNER JOIN EmployeesNS AS C
  ON P.emid = 3
  AND C.lft BETWEEN P.lft AND P.rgt
ORDER BY C.lft;
```

| empid | empname |
|---|---|
| 3 | Ina |
| 7 | Aaron |
| 11 | Gabriel |
| 9 | Rita |
| 14 | Didi |
| 12 | Emilia |
| 13 | Michael |

查询连接两个 `EmployeesNS` 实例。一个代表父节点 (P)，由给定根节点过滤；另一个代表子节点 (C)。它们根据子节点的左右值进行连接。重要提示：你可能想使用 `C.lft >= P.lft AND C.rgt <= P.rgt` 谓词，因为这比 `C.lft BETWEEN P.lft AND P.rgt` 更直观。在嵌套集合模型中，两者的含义相同。然而，后者在索引访问方面可以得到更好的优化，因为它基于一个范围而不是两个。

输出的缩进是通过子节点级别减去父节点级别并复制 '|' 字符串实现的。输出按子节点的左值排序，即所需的兄弟节点排序。该子树查询是大多数查询的基准。如果你想从输出中排除子树的根节点，只需使用大于 (`>`) 和小于 (`<`) 代替 `BETWEEN`。

### 返回给定根节点、限制层级的子树

```sql
SELECT C.emid, REPLICATE('| | ', C.lvl - P.lvl) + C.empname
FROM EmployeesNS AS P
  INNER JOIN EmployeesNS AS C
  ON P.emid = 3
  AND C.lft BETWEEN P.lft AND P.rgt
WHERE C.lvl - P.lvl <= 2
ORDER BY C.emid;
```

| empid | empname |
|---|---|
| 3 | Ina |
| 7 | Aaron |
| 11 | Gabriel |
| 9 | Rita |

### 返回给定根节点的叶子节点

```sql
SELECT C.emid, C.empname
FROM EmployeesNS AS P
  INNER JOIN EmployeesNS AS C
  ON P.emid = 3
  AND C.lft BETWEEN P.lft AND P.rgt
WHERE C.rgt - C.lft = 1;
```

| empid | empname |
|---|---|
| 11 | Gabriel |
| 14 | Didi |
| 12 | Emilia |
| 13 | Michael |

叶子节点是右值比左值大 1 的节点（没有下属）。将此过滤器添加到子树查询的 `WHERE` 子句中。你可以看到，嵌套集合识别叶子节点的速度比使用 `NOT EXISTS` 谓词的解决方案快得多。

### 返回每个节点的下属数量

```sql
SELECT empid, (rgt - lft - 1) / 2 AS cnt, REPLICATE(' | ', lvl) + empname
FROM EmployeesNS
ORDER BY lft;
```

| empid | cnt | empname |
|---|---|---|
| 1 | 13 | David |
| 2 | 5 | Eitan |
| 5 | 2 | Jiru |
| 8 | 0 | Lilach |
| 10 | 0 | Sean |
| 4 | 0 | Seraph |
| 6 | 0 | Steve |
| 3 | 6 | Ina |
| 7 | 5 | Aaron |
| 11 | 0 | Gabriel |
| 9 | 3 | Rita |
| 14 | 0 | Didi |
| 12 | 0 | Emilia |
| 13 | 0 | Michael |

因为节点正好对应两个 `lft` 和 `rgt` 值，在我们的实现中不存在间隙，你可以通过访问子树的根节点来计算下属数量。数量为 `(rgt - lft - 1) / 2`。

### 返回节点的所有祖先

```sql
SELECT P.emid, P.empname, P.lvl
FROM EmployeesNS AS P
INNER JOIN EmployeesNS AS C
  ON C.emid = 14
  AND C.lft BETWEEN P.lft AND P.rgt;
```

| empid | empname | lvl |
|---|---|---|
| 1 | David | 0 |
| 3 | Ina | 1 |
| 7 | Aaron | 2 |
| 9 | Rita | 3 |
| 14 | Didi | 4 |

## 传递闭包

有向图 G 的传递闭包是一个与 G 具有相同节点的图，并且对于 G 中由路径（不一定包含单条边）连接的每对节点，它们都有一条边连接。传递闭包可以立即回答许多问题，而无需探索图中的路径。例如，David 是 Aaron 的经理（直接或间接）吗？如果员工图的传递闭包包含一条从 David 到 Aaron 的边，那么就是。Espresso 包含水吗？我可以从洛杉矶开车到纽约吗？如果输入图包含边 (a, b) 和 (b, c)，那么 a 和 c 之间存在传递关系。传递闭包连接了边 (a, b)、(b, c) 以及 (a, c)。如果 David 是 Ina 的直接经理，而 In 是 Aaron 的直接经理，那么 David 在传递上是 Aaron 的经理或下属。

与传递闭包相关的问题涉及传递关系的特殊情况。一个例子是“最短路径”问题，你试图确定两个节点之间的最短路径。例如，从洛杉矶到纽约的最短路径是什么？

在本节中，我将描述传递闭包和最短路径问题的迭代/递归解决方案。

![](img/bdc38aa36f6e2987d913ee5381474711_811_0.png)

> **注意** 我将展示的某些解决方案（特别是那些使用递归 CTE 的方案）性能会随着输入图的增长而呈指数级下降。我展示它们是为了演示目的，因为它们非常直观且自然。它们对于小图是足够的。传递闭包相关问题的某些高效算法（例如 Floyd 算法和 Marshall 算法）可以实现为“按层”（广度优先）迭代。关于这的细节，请参考 `http://www.nist.gov/d/`；我将展示可以应用于更大图的有效解决方案。

## 有向无环图

我将讨论第一个问题是生成有向无环图 (DAG) 的传递闭包。稍后，我会向你展示如何处理无向图和循环图。图是有向还是无向都不会显著增加解决方案的复杂度，但处理循环图会。我在示例中使用的输入 DAG 是我在本章之前之前使用的 BOM，你通过运行列表 11-2 中的代码创建它。

生成 BOM 传递闭包的代码与子图问题（即零件展开）的解决方案相似。具体来说，你使用广度优先搜索技术遍历图。然而，这里不是只返回根节点，锚点成员（`anchor member`）返回 BOM 中所有的第一级关系。在这种情况下，这简单意味着所有组件为 NULL 的组配/零件对。递归成员（`recursive members`）将代表上一层或父级 (P) 的 CTE 与代表下一层或组件 (C) 的 BOM 连接。它返回原始产品 ID (P) 作为源，并将子产品 ID (C) 作为目标。外部查询返回去重的组件/零件对。请记住，BOM 中的多条路径可能指向同一个零件，但你只需要返回每个唯一零件一次。

运行以下代码生成 BOM 的传递闭包：

```sql
WITH BOMTC AS (
  -- 返回所有第一级包含关系
  SELECT assemblyid, partid
  FROM dbo.BOM
  WHERE assemblyid IS NOT NULL
  UNION ALL
  -- 返回下一层包含关系
  SELECT P.assemblyid, C.partid
  FROM BOMTC AS P
    INNER JOIN dbo.BOM AS C
    ON C.assemblyid = P.partid
)
-- 返回具有传递包含关系的去重对
SELECT DISTINCT assemblyid, partid
FROM BOMTC;
```

此代码生成以下输出：

| assemblyid | partid |
|---|---|
| 1 | 6 |
| 1 | 7 |
| 1 | 10 |
| 1 | 13 |
| 1 | 14 |
| 2 | 6 |
| 2 | 7 |
| 2 | 10 |
| 2 | 11 |
| 2 | 13 |
| 2 | 14 |
| 3 | 6 |
| 3 | 7 |
| 3 | 11 |
| 3 | 12 |
| 3 | 14 |
| 3 | 16 |
| 3 | 17 |
| 4 | 9 |
| 4 | 12 |
| 4 | 14 |
| 4 | 16 |
| 4 | 17 |
| 5 | 9 |
| 5 | 12 |
| 5 | 14 |
| 5 | 16 |
| 5 | 17 |
| 10 | 13 |
| 10 | 14 |
| 12 | 14 |
| 12 | 16 |

该解决方案通过在外部查询中应用 `DISTINCT` 消除了 BOM 中的重复边。更高效的解决方案是在反复运行的查询中使用 `NOT EXISTS` 谓词来完全避免重复；此类谓词将过滤掉未出现在已发现边集中的新发现边。然而，这种实现无法使用 CTE，因为递归成员只能访问上一层，而不是到目前为止获得的所有层。相反，你可以使用 UDF（用户定义函数）或存储过程，在循环中反复调用查询并将每条边插入工作表。运行以下代码来创建 `BOMTC`，它实现了这种逻辑：

```sql
IF OBJECT_ID('dbo.BOMTC') IS NOT NULL DROP FUNCTION BOMTC;
GO

CREATE FUNCTION BOMTC() RETURNS @BOMTC TABLE (
    assemblyid INT NOT NULL,
    partid INT NOT NULL,
    PRIMARY KEY (assemblyid, partid)
)
AS
BEGIN
    DECLARE @rowcount INT = 1;
    WHILE @rowcount > 0
    BEGIN
        INSERT INTO @BOMTC(assemblyid, partid)
        SELECT P.assemblyid, C.partid
        FROM @BOMTC P
        INNER JOIN dbo.BOM C ON C.assemblyid = P.partid
        WHERE NOT EXISTS (
            SELECT 1 FROM @BOMTC T2
            WHERE T2.assemblyid = P.assemblyid AND T2.partid = C.partid
        );
        SET @rowcount = @@ROWCOUNT;
    END
    RETURN
END
```

查询函数以获取 BOM 的传递闭包：如果你想获取 BOM 之间的最短路径，可以使用类似的算法。在这种情况下，锚点成员分配常数距离 1，递归成员每层增加距离。最后，外部查询返回所有可能的路径：

```sql
WITH BOMPaths AS (
  -- 所有路径
```



## 递归 CTE 示例

```sql
SELECT assemblyid, partid, 1 AS distance, CAST(CAST(assemblyid AS VARCHAR(MAX)) + ' -> ' + CAST(partid AS VARCHAR(MAX)) AS VARCHAR(MAX)) AS path
FROM dbo.BOM
WHERE assemblyid IS NOT NULL
UNION ALL
-- 递归
SELECT P.assemblyid, C.partid, P.distance + 1, CAST(P.path + ' -> ' + CAST(C.partid AS VARCHAR(MAX)) AS VARCHAR(MAX))
FROM BOMPaths P
INNER JOIN dbo.BOM C ON C.assemblyid = P.partid
```

得到以下输出：

| assemblyid | partid | distance | path |
|---|---|---|---|
| 1 | 6 | 1 | 1 -> 6 |
| 1 | 7 | 1 | 1 -> 7 |
| 1 | 10 | 1 | 1 -> 10 |
| 1 | 13 | 2 | 1 -> 10 -> 13 |
| 1 | 14 | 1 | 1 -> 14 |
| 2 | 6 | 1 | 2 -> 6 |
| 2 | 7 | 1 | 2 -> 7 |
| 2 | 10 | 1 | 2 -> 10 |
| 2 | 11 | 1 | 2 -> 11 |
| 2 | 13 | 2 | 2 -> 10 -> 13 |
| 2 | 14 | 1 | 2 -> 14 |
| 3 | 6 | 1 | 3 -> 6 |
| 3 | 7 | 1 | 3 -> 7 |
| 3 | 11 | 1 | 3 -> 11 |
| 3 | 12 | 1 | 3 -> 12 |
| 3 | 14 | 1 | 3 -> 14 |
| 3 | 16 | 1 | 3 -> 16 |
| 3 | 17 | 1 | 3 -> 17 |
| 4 | 9 | 1 | 4 -> 9 |
| 4 | 12 | 1 | 4 -> 12 |
| 4 | 14 | 1 | 4 -> 14 |
| 4 | 16 | 1 | 4 -> 16 |
| 4 | 17 | 1 | 4 -> 17 |
| 5 | 9 | 1 | 5 -> 9 |
| 5 | 12 | 1 | 5 -> 12 |
| 5 | 14 | 1 | 5 -> 14 |
| 5 | 16 | 1 | 5 -> 16 |
| 5 | 17 | 1 | 5 -> 17 |
| 10 | 13 | 1 | 10 -> 13 |
| 10 | 14 | 1 | 10 -> 14 |
| 12 | 14 | 1 | 12 -> 14 |
| 12 | 16 | 1 | 12 -> 16 |

此代码生成如下输出：

| assemblyid | partid | distance | path |
|---|---|---|---|
| 1 | 6 | 1 | .1.6. |
| 1 | 7 | 1 | .1.7. |
| 1 | 10 | 1 | .1.10. |
| 1 | 13 | 2 | .1.10.13. |
| 1 | 14 | 1 | .1.14. |
| 2 | 6 | 1 | .2.6. |
| 2 | 7 | 1 | .2.7. |
| 2 | 10 | 1 | .2.10. |
| 2 | 11 | 1 | .2.11. |
| 2 | 13 | 2 | .2.10.13. |
| 2 | 14 | 1 | .2.14. |
| 3 | 6 | 1 | .3.6. |
| 3 | 7 | 1 | .3.7. |
| 3 | 11 | 1 | .3.11. |
| 3 | 12 | 1 | .3.12. |
| 3 | 14 | 2 | .3.12.14. |
| 3 | 16 | 2 | .3.12.16. |
| 3 | 17 | 3 | .3.12.16.17. |
| 4 | 9 | 1 | .4.9. |
| 4 | 12 | 1 | .4.12. |
| 4 | 14 | 2 | .4.12.14. |
| 4 | 16 | 2 | .4.12.16. |
| 4 | 17 | 3 | .4.12.16.17. |
| 5 | 9 | 1 | .5.9. |
| 5 | 12 | 1 | .5.12. |
| 5 | 14 | 2 | .5.12.14. |
| 5 | 16 | 2 | .5.12.16. |
| 5 | 17 | 3 | .5.12.16.17. |
| 10 | 13 | 1 | .10.13. |
| 10 | 14 | 1 | .10.14. |
| 12 | 14 | 1 | .12.14. |
| 12 | 16 | 1 | .12.16. |
| 12 | 17 | 2 | .12.16.17. |
| 16 | 17 | 1 | .16.17. |

## 无向环图

虽然传递闭包是针对有向图定义的，但你也可以为无向图定义并生成它，其中每条边都代表一种双向关系。在我的示例中，我将使用通过运行列表 11-3 中的代码创建并填充的 `Roads` 图。要查看 `Roads` 的视觉化表示，请检查图 11-4。要将传递闭包和最短路径解决方案应用于 `Roads`，首先需要通过从每条现有的边生成两条有向边来将其转换为有向图：

```sql
SELECT city1 AS FROM_city, city2 AS TO_city FROM dbo.Roads UNION ALL
SELECT city2, city1 FROM dbo.Roads
```

例如，无向图中的边 `(JFK, ATL)` 在有向图中显现为两条边：`(JFK, ATL)` 和 `(ATL, JFK)`。前者代表从纽约到亚特兰大的道路，后者代表从亚特兰大到纽约的道路。

由于 `Roads` 是一个环图，你还需要使用我在本章关于遍历环形路径章节中之前描述的环检测逻辑。掌握了从无向图生成有向图并检测环的技术后，你就拥有了生成 `Roads` 传递闭包的所有工具。

运行以下代码来生成 `Roads` 的传递闭包：

```sql
WITH Roads2 AS -- 每对城市生成两行 (from-->to, to-->from)
(
  SELECT city1 AS from_city, city2 AS to_city FROM dbo.Roads
  UNION ALL
  SELECT city2, city1 FROM dbo.Roads
),
RoadPaths AS
(
  -- 返回所有第一级可达性对
  SELECT from_city, to_city,
  -- path 用于识别环
  CAST('.' + from_city + '.' + to_city + '.' AS VARCHAR(MAX)) AS path
  FROM Roads2
  UNION ALL
  -- 返回下一级可达性对
  SELECT F.from_city, T.to_city, CAST(F.path + '.' + T.to_city + '.' AS VARCHAR(MAX))
  FROM RoadPaths AS F
  INNER JOIN RoadPaths AS T
  -- 如果 to_city 出现在 from_city 的路径中，则检测到环
  ON CASE WHEN F.path LIKE '%.' + T.to_city + '%.' 
           THEN 1 ELSE 0 END = 0
  AND F.to_city = T.from_city
)
-- 返回 Roads 的传递闭包
SELECT from_city, to_city, path FROM RoadPaths;
```

| 出发城市 目的城市 | 距离 | 路径 |
| :--- | :--- | :--- |
| ANC FAI | 359 | .ANC,FAI. |
| 特兰大 IAH | 800 | .ATL,IAH. |
| ATL JFK | 865 | .ATL,JFK. |
| ATL MCI | 805 | .ATL,MCI. |
| ATL MIA | 665 | .ATL,MIA. |
| ATL ORD | 715 | .ATL,ORD. |
| DEN IAH | 1120 | .DEN,IAH. |
| DEN LAX | 1025 | .DEN,LAX. |
| DEN MCI | 600 | .DEN,MCI. |
| DEN MSP | 915 | .DEN,MSP. |
| DEN SEA | 1335 | .DEN,SEA. |
| DEN SFO | 1270 | .DEN,SFO. |
| IAH LAX | 1550 | .IAH,LAX. |
| IAH MCI | 795 | .IAH,MCI. |
| JFK ORD | 795 | .JFK,ORD. |
| LAX SFO | 385 | .LAX,SFO. |
| MCI MSP | 440 | .MCI,MSP. |
| MCI ORD | 525 | .MCI,ORD. |
| MSP ORD | 410 | .MSP,ORD. |
| MSP SEA | 2015 | .MSP,SEA. |
| SEA SFO | 815 | .SEA,SFO. |
| FAI ANC | 359 | .FAI,ANC. |
| IAH ATL | 800 | .IAH,ATL. |
| JFK ATL | 865 | .JFK,ATL. |
| MCI ATL | 805 | .MCI,ATL. |
| MIA ATL | 665 | .MIA,ATL. |
| ORD ATL | 715 | .ORD,ATL. |
| IAH DEN | 1120 | .IAH,DEN. |
| LAX DEN | 1025 | .LAX,DEN. |
| MCI DEN | 600 | .MCI,DEN. |
| MSP DEN | 915 | .MSP,DEN. |
| SEA DEN | 1335 | .SEA,DEN. |
| SFO DEN | 1270 | .SFO,DEN. |
| IAH LAX | 1550 | .IAH,LAX. |
| IAH MCI | 795 | .IAH,MCI. |
| JFK ORD | 795 | .JFK,ORD. |
| LAX SFO | 385 | .LAX,SFO. |
| MCI MSP | 440 | .MCI,MSP. |
| MCI ORD | 525 | .MCI,ORD. |
| MSP ORD | 410 | .MSP,ORD. |
| SEA SEA | 2015 | .SEA,SEA. |
| SFO SEA | 815 | .SFO,SEA. |
| SEA ORD | 2425 | .SEA,ORD. |
| SEA JFK | 3220 | .SEA,JFK. |
| ORD SEA | 2425 | .ORD,SEA. |
| ORD DEN | 1125 | .ORD,DEN. |
| ORD IAH | 1320 | .ORD,IAH. |
| ORD LAX | 2150 | .ORD,LAX. |
| ORD SFO | 2395 | .ORD,SFO. |
| MSP IAH | 1235 | .MSP,IAH. |
| SFO IAH | 1935 | .SFO,IAH. |
| SFO MIA | 3125 | .SFO,MIA. |
| MIA LAX | 2740 | .MIA,LAX. |
| MIA SFO | 3125 | .MIA,SFO. |
| LAX MIA | 2740 | .LAX,MIA. |
| LAX ATL | 2350 | .LAX,ATL. |
| SFO MCI | 1870 | .SFO,MCI. |
| SFO MSP | 2185 | .SFO,MSP. |
| SFO ORD | 2395 | .SFO,ORD. |
| SFO ATL | 2675 | .SFO,ATL. |
| SFO JFK | 3190 | .SFO,JFK. |
| SEA IAH | 2455 | .SEA,IAH. |
| SEA MCI | 1935 | .SEA,MCI. |
| SEA ATL | 2740 | .SEA,ATL. |
| SEA MIA | 3405 | .SEA,MIA. |
| MSP LAX | 1940 | .MSP,LAX. |
| MSP SFO | 2185 | .MSP,SFO. |
| MCI LAX | 1625 | .MCI,LAX. |
| MCI SEA | 1935 | .MCI,SEA. |
| MCI SFO | 1870 | .MCI,SFO. |
| LAX MCI | 1625 | .LAX,MCI. |
| LAX MSP | 1940 | .LAX,MSP. |
| LAX ORD | 2150 | .LAX,ORD. |
| JFK JFK | 2945 | .JFK,JFK. |
| IAH SEA | 2455 | .IAH,SEA. |
| ORD MIA | 1380 | .ORD,MIA. |
| MIA JFK | 1530 | .MIA,JFK. |
| MIA MCI | 1470 | .MIA,MCI. |
| MIA ORD | 1380 | .MIA,ORD. |
| MIA MSP | 1790 | .MIA,MSP. |
| MIA DEN | 2070 | .MIA,DEN. |
| MIA SEA | 3405 | .MIA,SEA. |
| MCI IAH | 1470 | .MCI,IAH. |
| JFK IAH | 1665 | .JFK,IAH. |
| JFK JFK | 1530 | .JFK,JFK. |
| IAH JFK | 1665 | .IAH,JFK. |
| SEA LAX | 1200 | .SEA,LAX. |
| MSP ATL | 1225 | .MSP,ATL. |
| MSP JFK | 2005 | .MSP,JFK. |
| MSP MIA | 1790 | .MSP,MIA. |
| MCI JFK | 1320 | .MCI,JFK. |
| LAX SEA | 1200 | .LAX,SEA. |
| JFK MCI | 1320 | .JFK,MCI. |
| JFK MSP | 2005 | .JFK,MSP. |
| JFK SEA | 3220 | .JFK,SEA. |
| JFK DEN | 1920 | .JFK,DEN. |
| JFK LAX | 2945 | .JFK,LAX. |

为了满足两个城市间最短路径的多次请求，你可能希望将结果存储在表中并对其索引，如下：

```sql
WITH Roads
(
    SELECT city1 AS from_city, city2 AS to_city, distance FROM dbo.Roads
    UNION ALL
    SELECT city2, city1, distance FROM dbo.Roads
),
RoadPaths AS (
    SELECT from_city, to_city,
    CAST('*' + from_city + '.' + to_city + '.' AS VARCHAR(MAX)) AS path
    FROM Roads
    UNION ALL
    SELECT F.from_city, T.to_city, F.distance + T.distance,
    CAST(F.path + T.to_city + '.' AS VARCHAR(MAX)) AS path
    FROM RoadPaths AS F
    INNER JOIN Roads2 AS T
    ON CASE WHEN F.path LIKE '%' + T.to_city + '.*'
    THEN 1 ELSE 0 END
    AND F.to_city = T.from_city
),
RoadsRnk AS (
    SELECT *, RANK() OVER(PARTITION BY from_city, to_city ORDER BY distance) AS rnk
    FROM RoadPaths
)
SELECT from_city, to_city, distance, path
FROM RoadsRnk
WHERE rnk = 1;

CREATE UNIQUE CLUSTERED INDEX idx_from_city_to_city
ON dbo.RoadPaths(from_city, to_city);
```

一旦结果集实例化并建立索引，两个城市之间最短路径的请求就可以立即满足。当信息变化不频繁时，这样做是实用且建议的。与通常一样，数据实时性和速度之间存在权衡。以下查询请求洛杉矶和纽约之间的最短路径：

```sql
SELECT from_city, to_city, distance, path FROM dbo.RoadPaths
WHERE from_city = 'LAX' AND to_city = 'JFK';
```

此查询生成以下输出：

| 出发城市 | 目的城市 | 距离 | 路径 |
| :--- | :--- | :--- | :--- |
| LAX | JFK | 2945 | .LAX,JFK. |

这可能是我提出的这些解决方案中最优雅的一个，而且它允许简单快速的查询。然而，维护物化信息（`materialized information`）的代价很高，因此通常这种解决方案对于静态轨迹或小型动态树来说是实用的。



在最后一节中，我介绍了解决传递闭包和最短路径问题的方案。

由于本章是本书的终结，我想给你们留下一个最后的思考。如果你问我，我希望你们从这本书中学到的最重要的事情是什么，我会说是对特别关注基础知识的重要性。不要低估它们，也不要轻视它们。花时间去识别、关注和完善基础技术。当你面对棘手的问题时，解决方案将自然而然地涌现。

> “大事应当从容处之。”
>
> “小事应当严肃对待。”
>
> —山本尊存元，《叶隐录》（Hagakure, The Book of the Samurai）

这些格言的含义并非表面如此。书中随后解释道：

> “在人的事务中，不应该超过两三件可以被称为‘大事’的事情。如果这些事情在平时经过审慎考虑，是可以理解的。其核心在于预先思考，在事来临时则从容处理。如果你事先没有做好准备，要面对一个事件并从容解决是很困难的，而且命中目标时会有不确定性。然而，如果基础已经事先打好，你可以将‘大事应当从容处之’这句话作为你行动的准则。”

## 索引

## 符号运算符

- `=` (等于) 的基数估计, 110, 113–114, 561
- 等值连接 (equi joins), 230–231
- `>` (大于) 运算符，基数估计, 561
- `<` (小于) 运算符，基数估计, 561

## A

- 绝对频率, 476–479
- 绝对百分比, 476–479
- 绝对值, 323–324
- 访问方法。参见 `scans`（扫描）；`seeks`（寻）
- 分配顺序安全索引, 65–76
- 分配顺序扫描 vs. 索引顺序, 65
- 聚集索引查找 + 范围, 93–94
- 成本关联, 57
- 覆盖非聚集索引查找 + 范围, 94–97
- `dm_db_usage_stats` 函数, 135–136
- 索引顺序扫描 vs. 索引顺序
- 索引查找 (index seeks), 48。参见 `Index Seek operator`（索引查找运算符）
- 逻辑谓词作为性能指标, 57
- 非聚集索引查找 + 范围 - 查找, 81–90
- 有序的聚集索引查找, 62–63
- 有序的覆盖非聚集索引扫描, 63–65
- 未提交隔离级别 (Read Uncommitted isolation level), 68–69, 78
- 表格扫描/聚集索引查找, 57–60
- 未覆盖的非聚集索引扫描, 60–62
- 无序非聚集索引扫描 + 查找, 91–93
- 无环图, 708。参见 `acyclic graphs` (DAGs)
- 添加行逻辑处理阶段, 4–5, 13
- 带有 `SQLCLR` 的 `ADO.NET` 上文连接字符串, 603–605
- 亲和掩码 (Affinity mask), 175, 177
- `AFTER DDL` 触发器, 579–581
- `AFTER DML` 触发器, 575–578, 581–583
- `AFTER UPDATE` 触发器, 575–578
- 聚合计算，自定义
- 排序解决方案 (carry-along-sort solutions), 326–327
- 用于的游标, 314–315
- `FOR XML` 字符串拼接, 317–319
- 聚合的分层叶子节点。参见 `grouping sets`（分组集）
- 产品, 504–327
- 概述, 313–314
- 透视 (pivoting for), 315–316, 318–319
- 产品, 322–324
- `SELECT @` 变量方法, 319–322
- 用户定义。参见 `SQLCLR` 用户定义聚合
- 聚合函数
- `AVG`。参见 `averages`（平均值），`AVG` 函数
- 基数过估计的影响, 99
- `COUNT`。参见 `count`（计数）
- 累积聚合函数计划, 274–275
- 带有预期频率计算, 504–505
- 局限性, 261–262
- 被某些限制并行, 179
- 标量聚合, 179
- 禁止的子查询输入, 17
- `SUM`。参见 `SUM` 函数；`SUM OVER` 窗口
- 窗口函数。参见 `aggregate window aggregate functions`（窗口聚合函数）
- 填充间隔解决方案, 466–468
- 与分组函数的相似性, 260
- 自定义计算的。参见 `aggregate calculations, custom`（自定义聚合计算）
- 用于的函数。参见 聚合函数
- 使用分组集 持久化, 334–337
- 用户定义。参见 `SQLCLR` 用户定义聚合
- 别名，确保查询中的唯一性, 204
- 内联 vs. 外部，用于派生表, 205
- `ORDER BY` 子句中的, 14, 20
- 引用, 8, 17
- 与 `APPLY` 运算符复用, 222–224
- `UNION` 运算符的变变变, 38–350
- 全部操作, 17–18
- Allen 间隔代数 (Allen's interval algebra)
- Allen 间隔代数, 452
- 分配顺序扫描的定义, 44
- 行的多次出现, 65–67
- 跳过行问题, 67–68
- 存储元素, 70–76
- 存储引擎情况, 59
- 表格扫描 (Table Scan) 处理, 58
- 属于的分配单元, 42
- 类型, 44
- `ALTER INDEX REBUILD` 命令, 48
- In-Memory OLTP 不支持 `ALTER TABLE`, 704
- `ALTER TABLE` 事件, 579–580
- 方差分析 (ANOVA), 505–528
- `ANSI_set` 选项, 568
- ANSI SQL 顺序, 1–2
- 反半 (anti semi), 237–238
- `APPLY` 运算符, 219–220
- `CROSS APPLY` 运算符, 221–222
- `CROSS` vs. `OUTER`, 228
- 隐式的, 221–224
- 中位数计算, 370–371
- `OUTER APPLY` 运算符, 221
- 并行索引 (Parallel), 183–186
- 列的复用, 222–224
- 类型, 218
- 算术聚合 (`ARITHORT` set), 568
- 算术平均值。参见 `means`（平均值）
- 数组, 245–249
- 升序键, 48
- 聚集 (`ASSEMBLY`), 587–588
- 赋值, 493
- 字符串拼接, 319–322
- 二进制变量, 374
- 事务的原子性 (atomicity), 633
- In-Memory OLTP, 698
- 自动提交事务, 633
- 统计信息, 102
- 基数估计, 112–113
- `BETWEEN` 运算符
- 智能分析 (bi), 116
- 二进制函数, 326
- 变量嗅探, 560
- 块, 378
- 事务的日志, 634
- 物料清单 (BOM), 711–714
- 树 (B-tree), 46
- 降序模式, 47
- 聚集树, 46
- 批量加载需求, 376
- `BW-Tree` 结构, 677–779
- 聚集索引结构, 50
- 叶子节点, 46
- 非聚集索引扫描 + 查找, 83–90
- 有序非聚集索引, 52–53
- 无序聚集索引的, 57–60
- 缓冲区 (buffers), 42
- 缓冲区池, 53
- 清理缓冲区, 54
- 日志缓冲区, 634
- 批量插入 (`BULK INSERT`) 命令, 376, 378
- 批量语句 (`BULK statements`), 410–411
- 批量导入工具, 376
- 预先写入, 374–375
- 最小日志记录, 376
- 最小日志需求, 377
- 打开置 (`OPENRESET`) 函数, 378–380
- `SELECT INTO`, 173–174, 373–376
- 结果集恢复模型, 634
- 智能分析 (BI), 117
- `BW-Tree` 结构, 677–779
- 未知值, 104
- 查看, 382
- 携带排序解决方案, 326–377
- 卡尔积积。参见 `joins`（连接）
- 逻辑处理阶段, 8–9
- `CASE` 表达式, 315
- 字符串排序规则, 595
- 恒标识属性, 387
- 序列创建, 394
- 临时对象, 147
- 临时表, 448

## C

- 清理, 53
- 默认值, 287
- 页面, 42
- 定义, 708
- 相等, 665
- 基数估计, 117
- 过滤索引创建, 107
- 直方图刷新率, 564
- 直方图来源, 103
- 不准确, 94
- 影响, 557
- 连接顺序问题, 223
- 路径路径导致, 767
- 嵌套集, 778
- 下一级, 718
- 父子关系节点列表，转换为 `HERARCHY`, 771–773
- 唯一列, 46–47
- 无序聚集索引的, 57–60

### `COALESCE` 函数

聚集索引 (clustered indexes)，续

- `CLUSTERED` 关键字, 43
- 覆盖索引, 93–94
- 创建, 43
- `FILLFACTOR` 选项, 48
- 导入时的性能影响, 44
- 索引顺序扫描, 46–47
- 叶节点级, 46–47
- 层级，确定数量, 49–50
- 层级, 46–48
- In-Memory OLTP 不支持, 704
- 有序聚集索引, 62–63
- 根页, 48
- 唯一列, 46
- 无方向聚集索引, 57–60
- 可更新的聚集索引, 128–129

- `COALESCE` 函数, 316
- Codd, Edgar F, 2
- 变异系数 (CV), 486, 523
- 决定系数 (CD), 498–499, 523
- 冷缓存, 53
- 收集方法, 229–630
- 列 (columns)
- 使用 `SELECT` 子句中的别名处理顺序, 14, 20
- 重新编译时的变化, 570–571
- 使用 `RESULT SETS` 子句更改名称和类型, 574–575
- In-Memory OLTP 不支持计算列, 703
- 创建顺序, 21
- 密集分区问题, 150, 154
- 对表表达式进行查询时的名称要求, 204
- 引用, 17
- `SQL_VARIANT` 类型, 300
- 子查询相关性, 189
- 子查询中的替换错误, 201–202
- 交换值, 18
- 变量, 473
- 列存储索引 (columnstore indexes)
- 2012 版对比 2014 版的功能, 125, 128
- 优势, 125–127
- 批执行, 128–130
- 聚集的、可更新的列存储索引, 128–129
- 列段, 126
- `CPU` 成本效益, 128
- 数据组织, 125–126
- 数据类型限制, 130
- 作为数据仓库目标, 123
- 删除位图, 129
- 数据存储器, 129
- 字典, 126
- 执行计划, 127
- 用于连接的哈希算法, 243
- `I/O` 成本降低效益, 127
- 重建建议, 129
- 行组 (rowgroups), 126
- 行存储 vs. 列存储的效率, 123–127
- 段消除 (segmentation elimination), 127
- 示例, 125
- 元组处理, 129
- 更新处理, 129
- 用户视图, 126
- `COLUMNS` 更新函数, 577
- 参见特定命令名称
- `COMMIT TRAN`, 633–634
- 提交验证错误, 693–696
- 公共运行时 (Common Runtime)。请参见 `CLR` (`CLR`) 语言运行时
- 通用表表达式 (common expressions)。带有通用表表达式的 `CTE`)
- 编译（重新编译）, 568–571
- 复合 `XML`, 417
- In-Memory OLTP 不支持计算列, 703
- `CONCAT` 函数, 316
- 连接
- 使用逗号分隔的 `CONCAT`, 629–632
- `CONCAT_NULL_YELDS` null 选项, 568–570
- 使用其进行前 N 组排序, 366–368
- 并发模型 (concurrency models)
- 悲观模型 vs. 并发模型, 674
- 与隔离隔离的对比表, 66
- 事务的一致性属性, 634
- 控制台分析变体, 505–506
- 约束 (constraints)
- `CHECK`。参见检查约束
- `DEFAULT WITH NEXT VALUE FROM`, 384
- 删除, 385
- 事务的独立性, 634
- In-Memory OLTP 不支持索引, 704
- 对于内存优化型表, 676
- `UNIQUE` 约束
- 上下文字符串函数, 603–605, 607
- 带有触发器的 `CONTEXT_INFO`, 584
- 保留策略, 501–505
- 连续变量的统计信息
- 分布中心, 479–481
- 定义的, 474
- 其上的描述性统计, 479
- 高阶总体阶矩, 488–494
- 峰度, 489–495, 523
- 均值位于, 481–482, 484, 523
- 中位数，参见
- 众数, 324–327, 498
- 正态分布, 487–488, 509–512
- 总体阶矩, 479
- 分布范围, 482–483
- 偏度, 478–489, 490–495
- 分布离散度, 482–486
- 标准差, 486–487, 490, 498, 523
- 转换函数，`CAST` 函数。各参见
- 日期和时间转换, 431–432
- 固件, 447–449
- 用于日期和时间的 `CONVERT` 函数, 431, 435
- 协调线程, 164–165
- 相关子查询, 187, 189–194
- 相关表, 184
- 相关系数, 498–499, 523
- 相关性 vs. 因果关系, 499
- 分区边界 (Cost Threshold for Partitioning), 175–176
- `COUNT` 函数
- `GROUP BY`, 16
- `HAVING WITH`, 16–17
- 使用其进行模式计算, 324–327
- 外部连接, 17
- 逻辑处理阶段, 36–37
- 协方差, 495–498
- 覆盖索引
- 优势, 93
- 作为聚集索引, 93–94
- 内存优化型索引总是, 677
- 非聚集索引范围, 94–97
- `CPUs`, 176–177
- 逻辑上的, 89–90
- `CREATE CLUSTERED INDEX`, 43
- `CREATE TYPE`, 371–573
- `CREATE TABLE` 事件，带有触发器, 579–580
- `CROSS APPLY` 运算符
- 使用列别名, 223
- 逻辑处理阶段, 27–28
- 多表查询, 219–220
- 使用其进行透置, 310–311
- 并行索引 (Parallel Index), 183–318
- 交叉连接
- 结果的笛卡尔积, 224
- 逻辑处理阶段, 8–9
- 物理连接顺序, 232–233
- 生成大量行, 216–217
- 使用样本数据生成, 225
- 使用子查询进行优化, 226–227
- 语法, 224
- 使用其进行透置, 308–310
- 与非等值连接, 231
- 交叉计数, 703
- 跨数据库事务，In-Memory OLTP 不支持, 705
- `CTEs` (通用表表达式)
- 祖先, 730–733
- 锚成员, 722
- 存档/递归数据匹配
- 要求, 736
- 图中的循环检测, 740–742
- 后代，返回, 722–723
- 费用，避免重复, 140–143
- `MAXRECURSIVE` 提示, 728–729
- 使用其进行多次计算, 324
- 多个 `WITH` 语句, 208
- 允许多次引用, 208–209
- 嵌套, 208
- 性能问题, 209
- 持久性, 140
- 查询要求, 204–205
- 追溯, 209, 718–719
- 递归子图函数, 718–719, 723, 731–733
- 递归，受并行性限制, 179
- 范围, 204
- 最短路径解 vs. 循环, 792–801
- 子图解, 722, 723
- 带有枚举的子图, 736
- 语法, 207
- 临时对象, 130
- 使用逻辑类型进行排序, 736
- 故障排除方法, 402
- 对数据进行日期, 402–403
- 与派生表, 207–208
- `CUBE` 函数, 331–333
- `CUME_DIST OVER` 窗口函数
- 频率计算, 477
- 与 `PERCENT RANK` 对, 288–289
- 累计 F 分布, 506–508
- 累计频率, 476–479
- 累计百分比, 476–499
- `CURRENT ROW` 窗口, 269–270, 274, 276–
- `CURRENT TIMESTAMP` 函数, 522
- 错误的重复, 521
- 使用自定义聚合进行计算, 314–315
- 使用指数移动平均进行计算, 515–518
- `FAST FORWARD` 选项, 152
- 刻画，`T.S` 不等式, 151–153
- 使用递归性解, 151–152
- In-Memory OLTP 不支持, 704
- 由 `ORDER BY` 子句返回, 21–22
- 使用字符串连接, 314–315
- 语法示例, 151
- 带有触发器, 581–583
- `CV` (变异系数), 486
- 数据包数据结构, 163
- 循环图, 708–715, 740–742, 792–801

## D

- `DAGs`。参见有向无环图 (`DAGs`)
- 数据缓存。参见
- 数据语言。参见 `D` (数据定义语言)
- 数据完整性，使用过滤索引强制, 122
- 数据操纵语言。参见
- 数据结构，包含, 384
- 数据类型优先级, 542
- 数据仓库, 123
- 数据分析计算
- 聚合函数。参见
- 汇装到, 587
- 加或减, 44
- 锚点数据, 440
- `BETWEEN` 谓词之后, 447
- 字符字符串, 447
- 兼容性级别，设置, 98
- 跨数据库事务，In-Memory OLTP 不支持, 705
- 补偿方法, 576
- 当前日期和时间, 422
- `GETDATE` 函数, 422
- `GETUTCD` 函数, 422
- 分组依据, 449–559
- 相交区间, 452–456
- 间隔计算, 450–471
- `ISDATE` 函数, 425
- `IsDayLightSaving` 方法, 424
- 孤岛问题, 295–299
- 语言相关结果, 425–437
- 语言中立格式, 436
- 全年最后一天的计算, 547–549
- 本地跟踪方法, 576



# 索引

## 闰秒
422–423

## 最大当前间隔问题
456–509

## 使用其使用
434–436

## Microsoft Windows 时间
421–422

## 午夜，靠近舍入
447

## MONTH 函数
425

## 偏移量 (utc)，提取
423

## 填充级别
466–471

## 用于 PARSE 函数的
431–433, 435

## 间隔的性能增强
450–451, 458–465, 470–471

## 性能问题
423

## 类型的精度
420

## 上一个或下一个工作日的计算
441–443

## 推测格列利历，使用
419

## 查询调优
445–444

# 偏差

## 舍入问题
447–449

## 搜索参数 (SARGs)
445–446

## SMALDATETIME 类型
419–420, 430–440, 446–449

## DECIMAL 数据类型
592–593

## 去重
399–401

## 带有 NEXT VALUE FOR 的 DEFAULT 约束
384

## 定积分
509–512

## 并行度, DOP (自由度并行度)

## SMALDATETIMFROM 函数
431

## SQLCLR 类型转换问题
595

## 存储需求，其
420

## SWITCHOFFSET 函数
425–426

## SYSDATETIME
422, 436–437, 440–441, 446–449

## 在方差分析中
505–508

## 卡方临界点
502

## 已定义
485, 523

## 延迟持久性
634–645

## 由 DELETE 引起

## SYSDATEOFFSET 函数
421–424

## SYSDATETIME 函数
421–422, 420, 595

## TIME 数据类型
419–420, 422

## 时区问题
420–421

## TIMEOFROM 函数
431

## 带有 AFTER 触发器
575–578

## DELETE FROM 语句
361, 399–400

## DELETE TOP 项
360–363, 400

## INSTEAD OF 触发器，带有
578

## 在 MERGE 语句中
405–406

## 带有 OUTPUT
413–414

## 带有 DATETIME 的仅限时间
439–440

## TOADATETIME 函数
426

## TRY_CAST 函数
431–432

## 表的无歧义格式
436

## 与 UTC 比较
420–421

## 杂草
423–439, 431–445

## 删除数据
413–414

## 归档已删除
413–414

## 去重
399–401

## DELETE 用于，DELETE 子句

## SELECT INTO 另一种方法

## WHERE 子句
445–446

## Windows 时间服务
421–422

## YEAR 函数
425

## YYYYMMDD 格式
435–436

## DAY 函数
425

## 夏令时
420–425

## DBCC 命令
400–401

## TRUNCATE TABLE 语句，用于
395–399

## 按需并行分布方案
163, 171–173

## 密集分区插入函数
150

## DENSE_RANK OVER 窗口函数
282–283, 285, 294–296

## IND–71

## 优化器, WHATIF
89–90

## SHOW_STATISTICS
101–102

## dbo 模式
620

## 密度向量，统计
102–103

## 列别名结果
205

## 列别名计划的 APPLY ORDER
452, 222–224

## 劣势
206

## 其执行计划的
206

## 内联分析
205–206

## 多处引用的使用，带有
207

## 嵌套问题
206

## 维度的持久性
140

## （数据定义语言）

## 内存 OLTP 表面积限制
703–704

## 重新编译
568

## 在 DD_DATABASE_EVENTS 上的触发器
579–581

## 在 DD_TABLE_EVENTS 上的触发器
579

## 死锁

### 查询请求
204–205

### 创建的语法
205

### 其临时对象
139

### 定义中的 DESC 索引键
115–116

### DESC 选项，TOP 过滤器
344–345

### 后代查看子查询

### 子节点。参见代码节点

### CES (通用表表表达式)，返回
722–723

### 选择终止
657

### DEADLOCK_PRIORITY 选项
657

### 由生成的错误消息
657–659

### 生成的示例
657–658

### 为生成的图
657–659

### 索引，关系
660

### 隔离级别，关系
660

### 长度
660

### 减少的措施
658–660

### 机制
657

### 物理资源访问顺序问题
659

### 查询内存环境，内存 OLTP
691–693

### 后的重试逻辑
669–670

### 单表死锁
660–662

### 服务器对的监控
657

### 其跟踪标记
657

### HIERARCHID数据的 GetDescendant 方法
757–759

### 查询 HIERARCHID 数据类型
763–764

### desc 索引
63, 115–118

### 平均绝对偏差 (MAD)
484

### 均方差 (MSD)
484

### 标准
486–487, 490, 498, 511 809

### 二分类变量
474

### 有向无环图 (DAGs)
665

### 无环图 (DAGs)

### 物料清单 (BOM) 场景
711–714

### 已定义
708

### 层级结构
709

### 排序
736–739

### 拓扑排序
736–739

### 传递闭包
787–792

### 双复制
711

### 有向图 (DAGs) 定义
707–708

### 返回子集
719–729

### 传递闭包。参见传递闭包

### 脏页，CHECKPOINT 写入
377

### 积极写入
140, 174–175

### 机制
42–44

### 脏读，已定义
645

### 读取隔离
647

### 与隔离级别的，表
646

### 内存 OLTP 不允许的
705

### DISTINCT 子句，不当使用
231–232

### NULL 的处理，带有 ORDER BY
20–22

### 在本地排序中
6, 18–20

### 分布的
408

### 分布中心
479–481

### 对发生表
501–505

### 自由度
485, 502, 505

### 平均绝对偏差 (MAD)
484

### 均方差 (MSD)
484

### 分布函数
509–512

### 频率范围
476–478

### 高阶矩
487–494

### 四季度范围
483

### 反转函数
289–291

### 均
479, 482, 483

### 中
324–327, 480–592

### 正态分布
487–488, 509–512

### 范围
486–488

### 偏度
479–488, 489–490, 523

### 分布的划分
482–486

### 标准偏差
486–490, 521

### 方差
485, 506–508

### 分发器
164–165

### 分治算法
733

### SQL 中的 DML
589

### dm_db_index_usage_stats
135–136

### dm_db_missing_index_columns
136–137

### dm_db_missing_index 详细视图
136

### dm_db_missing_index 组视图
136

### dm_db_procedure_stats
138

### dm_exec_query_profiles 视图
138–139

### dm_exec_query_stats
137–138

### dm_exec_trigger_stats
138

### 动态管理函数 (DMFs)
134–139

### XML (数据操作语言)

### 可组合 DML
417

### 内存 OLTP 区域限制
704–705

### 动态视图 (DMVs)
134–139

### 并行度 (POP) 已定义
159

### 执行计划
161, 162–164

### 最大并行度设置
175–177

### 分发线程
184

### CLEANBUFFERS
53

### 重复。参见 DISTINCT 子句

### 删除
399–410

### 事务的持久性
634

### 动态过滤，动态管理函数 (DMFs)
134–139

### 动态排序
503–508

### 动态架构
300–301

### 动态 SQL

#### 在在中的代码
525

#### 动态交叉
530–535

#### 动态搜索条件
535–542

#### 动态排序
542–546

#### EXEC AT 命令，动态 SQL
529

#### EXEC 命令，动态 SQL 标识至
525–529

#### 安全风险
526–529

#### 带有 RESULT SET 子句
573–575

#### EXECUTE AS 子句
546

### 执行计划

#### 在 Bitmap 算符中
170–171

#### 缓存集，选项
568–570

#### 基数估计中的
98–100

#### CLR 标量函数对比 T-SQL 标量函数
588–589

#### 聚集索引 + 范围扫描
93–94

#### 列存储索引
127

#### 覆盖非聚集索引 + 范围扫描
96–100

#### CPU 成本，权重
176–177

#### 基于策划的查询
152

#### 派生表表达式
206

#### 派生索引计划
116

#### 分发流 Exchange 算符
160–163

#### dm_db_index_operational_stats
135

#### dm_db_index_physical_stats
810

# 执行计划

### 熵计算
518–521, 523

### ON 函数
431, 441

### 硬编码基数估计
561

### 等值连接
230–231

### 等值谓词访问方法
95–97

### 等值连接
230–231

### 错误函数
662–663

### ERROR_function
664

### 验证顺序
693–696

### RAISERROR 命令列表
664

### RAISERROR 命令
664–665

### 重试逻辑
669–670

### 作为回滚的一部分
666

### 事务错误
666–666

### TRY-CATCH。参见 TRY-CATCH 命令

### ERROR_NUMBER 函数
664

### 锁升级
641–643

### 估计器
512

### EVENT SESSION 子句
132

### EVENTDATA
579–580

### 由触发器触发
569

### EXCEPT 算符

#### EXCEPT 实现
255–256

#### 用于合并中的 NULL
407–408

#### 逻辑查询处理阶段
38–39

#### NULL 的处理
11

#### 关系算符特性
24

#### 返回值
255

### Exchange 算符
160–166

### 排斥锁 (X)
636–637

### EXEC AT 命令，动态 SQL
529

### EXEC 命令，动态 SQL 标识至
525–529

### 安全风险
526–529

# E

### 积极写入
140, 174–175

### EAV (实体，属性，值)
300–301

### 已定义
707

### 有向的
707–708

### 传递闭包去重
789

### 元素，从数组分离
245–249

### EMA (指数移动平均)
515–518

### 员工组织图
709–711

### 年末计算
547–549

## 现有值范围识别

### 执行计划，继续

#### 无序覆盖非聚集扫描
60–61

#### 无序非聚集索引扫描, 查找
91–92

#### 变量，存储过程
561–562

### 现有值范围识别。参见孤岛问题 (island problems)

### EXISTS 存在

#### 带有 NOT 的半连接
238

#### 识别间隙顺序
198–200

#### 查找最小值
195–200

#### 嵌套 EXISTS
201

#### NOT EXISTS 对比 NOT
204

#### 正逻辑与负逻辑对比
200–201

#### 返回真或假
194–195

#### 与半连接连接
237

#### 子查询作为输入，到
194–201

#### 子查询的 SELECT 列表索引被忽略
195

#### 与其进行调优
157

#### 与谓词对比
194–205

#### UNKNOWN 值的处理
11

#### 无序非聚集索引扫描, 查找
91–92

#### 用户定义的，动态
535–542

#### 基于 WHERE。参见 WHERE 过滤器

#### 窗口函数
263–264

#### 第一条回归线
500

#### FIRST, VALUE OVER window
285–286, 511

#### FLOOR 函数
468

#### 逻辑查询处理的流程图
5

#### fn_dbfunction
377–388

#### FOLLOWING 关键字
269–274

#### FOR XML 字符串拼接
317–319

#### 连接的强制顺序提示提示
233–236, 245

#### FORCE EXISTS 选项
368

#### In-Memory OLTP 不支持外键约束
704

#### 森林
708。参见图 (graphs)；树 (trees)

#### FORMAT 函数
432–439

#### EXP 函数
322–324

#### 期望频率
501–505

#### 指数退避
106

#### 指数移动平均值 (EMAs)
515–518

#### 扩展事件 (Extended Events) 会话

##### 创建
132

##### 提取统计信息，从
132–134

##### 性能，代码查看
54

##### 查看时对查询进行排序
131–134

##### query_hash_action
131–134–138

##### query_post_execution showplan 事件
131

##### 语句完成事件
131–134

##### 实时数据查看 (Watch Live Data) 统计信息
56

#### 范围 (extents)
42–463

#### 分配与索引扫描的影响
65

#### 数据页填充
135

#### 用于检查逻辑的代码
70–71

#### 定义
47–48

#### dm_db_index_physical_stats 函数

##### 逻辑扫描统计信息
135

##### 重建作为补救
135

#### 帧 (frames)。参见窗口框 (window frames) 用于

#### 频率计算

##### 定义
523

##### 期望频率
501–505

##### 频率分布分析
476–479

##### 用于卡方计算
502–505

##### 与窗口函数一起
477–479

##### 不使用窗口函数
476

## F

### FALSE 值
10

### 少量外部行优化
168–180

### 文件组内存优化型数据
67

### 来自 HIERARCHY 类型的 FileTable
754

### 过滤索引
120–122

### 过滤器

#### 访问方法。参见访问方法

#### 选择基数估计的影响
100

#### 选择基数低估的影响
99

#### 与数据分析计算结合
262–263

#### 日期与 SARG 性（搜索参数化）
444–456

#### 由于缺少支持索引导致的死锁
658–659

#### 动态过滤
535–542

#### 多个谓词的基基数估计
104–107

#### 多个谓词索引
95–97

#### NULL 值的处理
11

#### 执行计划依赖的选择性方面
555–556

### FROM 子句

#### 别名创建，可见性
222–223

#### 深入查找表的用途
205–207

#### 可查询性保证
634

#### 与 SELECT INTO 操作结合
377–378

### FULL OUTER JOIN 子句
13

### 不需要排序时的全表扫描
57–60

### 全数据恢复模型

#### 来自该模型的持久性保证
634

## G

### GAC (全局程序集缓存)
587

### GAMs (全局分配映射)
42

### 间隙问题
291–292

## hierarchies (层级结构)

### Gather 操作
88, 160–166

### 高斯曲线
487–488

### GETDATE 函数
422

### GETUTDATE 函数
422

### 全局分配映射 (GAMs)
22

### 全局程序集缓存 (GAC)
587

### 图形化执行计划。参见执行计划图。

### MAXRECURION 提示
728–729

### 集合节点
778–786

### 返回路径
730–733

### 递归解
718–719, 722–723

### 排序
736–739

### 返回子图的算法
719–729

### 带有路径枚举的传递闭包
733–736

### 传递闭包。参见传递闭包 (transitive closure)。

- 树
708

### 类型
707–708

### 无向 (undirected)

### 无向无环。参见无向图 (undirected graphs)

### 顶点 (vertexes)

### 权重
714, 818

### 大于基数估计
561

### 硬编码
561

### 格里历历，其
419

### GROUP BY 类

- 与 COUNT
16

#### 日期和时间，分组键
449–459

#### 分组
15

- GROUPING SETS 子句
328–331

#### 逻辑顺序
3–5

#### 逻辑阶段样本
7

#### NULL 值处理
11

#### 逻辑处理阶段
4–5, 15–16

#### 与 PIVOT 运算符结合
30

#### 运行总计算
272–273

#### 与 SELECT
16

#### 分组函数对比
259

#### 分组查询数据限制
261

#### 分组
333–334

#### CUBE 函数
331

#### 执行计划
330, 333

#### 特性列表
327

#### 用于排序的 GROUPING SETS
337–338

#### GROUPING ID 函数
333

#### 支持排序
331

#### 与平均值合并
336–337

#### 多个集合
328

#### 乘法
333

#### 排序问题
337–338

#### 括号定义
328

#### 与持久聚合结合
334

#### 幂集
333

#### ROLLUP 函数
331

#### 集合
333

#### UNION all
329–330

#### 分组，不允许 WHERE
14

## H (哈希)

- 哈希 (hashes)

#### 连接的哈希算法
243–245

#### 并行查询中的哈希连接
170–171

#### Hash Match 运算符
167

#### 哈希并行方案
163–165

### HAVING 过滤器

- 与 COUNT
16

#### 逻辑顺序
3–5

#### 逻辑处理阶段
4–5, 15–16

#### 子查询输入
17

#### UNKNOWN 值的处理
11

### 页头
42

### 头统计信息
102

### 堆表 (heaps)

#### 批量加载要求
376

#### 非聚集索引范围扫描
801–818

#### 非聚集索引建立在
50–51

#### 组织
43–46

#### 表扫描
57–60

### Hekaton 项目。参见 In-Memory OLTP

### 层级结构

#### 定义
709

#### 组织图场景
709–711

## HIERARCHY (层级) 数据类型

### 添加叶子节点
756–759

### 优势
754

### 祖先查询
764–765

### 大小敏感性
755

### 子查询
765

### 与自定义实现对比
754

### 冲突预防
757–758

### 数据维护要求
756

### 后代查询
763–764

### 执行计划
764

### GetAncestor 方法
758, 759

### Descendant 方法
760–762

### GetRoot 方法
757, 762

### 属性
756–767

### 索引创建
755

### IsDescendant 方法
760, 763

### 叶子节点查询
765

### 长路径查询
771

### 提供的方法
754



# 值的归一化, 767–771

# 包含父子邻接列表, 771–773

# 路径查询, 764–765

# 可移植性问题, 754

# 演示查询, 766

# 查询解决方案, 758–759, 763–766

# 分离排序列表, 733–777

# 使用的存储过程, 757–757

# 子查询查询, 764–766

# 子树, 760–762

# 树的有效性，强制, 756

# 直方图 (histograms)

- `AUTO_CREATE_STATISTICS` 选项, 102
- `AVG_RANGE_ROWS`, 102–104
- 来自候选估计, 103
- 创建场景, 102
- `DISTINCT_RANGE_ROWS`, 102–103
- `EQ_ROWS`, 102–122
- 过滤索引, 102–126
- 日期频率, 476–479
- 索引键值, 85–86
- 非索引列, 93
- 表变量不进行维护, 553
- `RANGE_H_KEY`, 102–104
- `RANGE_ROWS`, 102–103
- 刷新率输出, 110, 564–665
- 步骤中的, 103
- 跟踪标志, 2389, 109

# HOB (或 B 树) 操作, 43–44

# `HOLDLOCK` 提示, 409

# 超线程, 178

# IAMs (索引分配映射), 44–47

# 识别间隙问题, 198–200

# 索引列, 412–413

# 索引属性

- 属性方面, 394–395
- 缓存性能, 387–394
- 与缓存结合, 382–383
- `IDENTITY` 函数, 374
- 局限性, 381–382
- 手动值更改, 381
- 隐藏的原因, 387
- 性能考虑量, 389–394
- `SELECT INDEX` 复制, 374
- 序列对象对比, 390–395
- 与代理键生成, 381–382
- 跟踪标志, 272, 387
- `TRUNCATE TABLE`: 指定密集的, 396–397

# 索引值分区, 412–413

- 标记 (Marks), 10

# 隐式运算符, 221–222

# `IMPLICIT_TRANSACTIONS` 选项, 633

# 导入数据。参见批量加载 (bulk loads)

# In-Memory OLTP 不允许 IN 连接, 705

# IN 谓词或 EXISTS, 194–195

# `INCLUDE` 子句, 119

# 包含的非索引列, 119–120

# 不一致分析, 645

# `INDEX <index_name> > CLUSTERED`, 43

# 索引分配映射 (IAMs), 44–47

# 索引顺序扫描

- 定义, 46
- 安全问题, 76–81
- 对比顺序扫描类, 47, 65

# 索引扫描操作, 65–180

# 索引访问方法, 49

# 索引查找运算符。另请查找 (seeks)

- 作为策略的一部分强制执行, 154–155

# 索引查找 + 范围扫描 + 查找

- 方法, 81–82
- 在最大并发间隔任务中效率低下, 459
- 优化子查询, 192–193
- 并行扫描结合, 116
- TOP 各种索引的过滤，优化, 348–352

# 索引

- `ALTER INDEX REBUILD` 命令, 48
- 聚集索引。参见列存储 (columnstore)
- 列存储列存储索引
- 覆盖。参见列存储索引
- 由于缺少支持索引导致的死锁, 658–659

# IN_ROW_DATA 分配单元

- 降序, descending, 63, 115–118
- `dm_db_index_operational_stats` 函数, 135
- `dm_db_usage_stats` 函数, 135–136
- `dm_exec_query_stats` 函数, 137–138
- 过滤, 1122
- 使用频率, 135–136
- 导入对性能的影响, 44
- `INCLUDE` 包含在, 列顺序, 95–
- 在非键列中被排除, 119–120
- `INDEXPROPERTY` 函数, 49
- 内联定义, 130–131
- 嵌套循环连接, 用于, 239–240
- 键更新作为行返回错误的来源, 76–81
- 叶子节点更新作为行返回错误的来源, 76–81
- 层级数量, 49–50
- 内存优化表。参见内存优化表的索引
- 缺失信息对象, 136
- 非聚集。参见非索引索引
- 页数据结构用于, 42
- OC（分区、排序、覆盖）, 模式, 192–271–273, 284–285
- `REBUILD` 命令, 135
- `REORGANIZE` 列表, 123
- 根页, 48
- 统计信息创建于, 85–86, 101
- TOP 过滤器, 对优化的影响, 39
- UDDF 子句, 设置, 90
- WHERE 子句谓词, 120

## 内存优化表的索引

- BW-Tree 结构, 677–679
- 聚集与非聚集无意义, 677
- 覆盖性质, 677, 680
- 哈希索引, 680–690
- 键值, 679
- 无锁性质, 679
- 叶子页, 679
- 必须在 `CREATE TABLE` 语句中指定, 675
- 非聚集索引, 677–680
- 页映射表, 678
- 载荷, 679
- 指针性质, 676
- 单向性质, 679–680
- 创建索引的语法, 677
- 信息论, 318–321
- 并行阻碍因素, 178–181
- 内联索引定义, 130–131
- 内联 TVF（表值函数）
- 年末计算, 548–549
- 输入参数计数, 215
- 整数序列生成器用于, 215–218
- 查询需求, 204–205
- 范围, 204
- 语法, 215

## 内存内存型事务处理 (In-Memory OLTP)

- 2014 实现, 671
- 不支持 `ALTER TABLE`, 704
- `ATOMIC` 块, 698
- 阻塞, 691–693
- 不支持检查约束, 704
- 不支持聚集索引, 704
- 验证错误, 693–696
- 不支持计算列, 703
- 不支持的约束类型, 704
- 跨容器查询, 703
- 数据库查询执行禁止, 696
- 不支持游标, 704
- 内存中的数据, 672–673
- 死锁, 691–693
- `DURABILITY` 选项, 675
- 执行引擎城市, 673
- 执行环境, 690
- 不支持外键约束, 704
- 内存优化表, 2
- 与 SQL Server 的集成, 674
- 查询意图中的隔离级别, 691
- 事务语义, 690
- 不支持 LOB 类型, 704
- 锁与无锁架构, 673–674
- 内存优化数据文件, 675
- `MEMORY_OPTIMIZED` 选项, 675
- 内存优化表, 672
- 现代计算环境, 671–672
- 存储过程的原生编译, 673
- 原生编译存储过程。参见原生编译存储过程环境
- 乐观并发模型, 674
- 页消除, 672–673
- 在不使用并行的情况下, 696–697
- 架构选项, 675
- 统计信息生成, 697–698
- 表面积关系, 703–705
- 内存优化, 675–676
- 时间戳, 672
- 事务隔离与一致性, 672
- 不支持唯一约束, 704
- 内部连接,
- 带 JSON 关键字的默认类型, 229
- 内部的逻辑连接步骤, 228
- 逻辑连接评估顺序, 234–237
- 带有 ON WHERE 子句, 215
- 物理连接评估顺序, 232–233
- 带有运行总计算, 272–273
- 语法, 228
- 带有 WHERE 子句, 228
- 内部查询。参见子查询
- `IN_ROW_DATA` 分配单元, 44

## INSERT 子句

- 带有 AFTER 触发器, 575–578, 581–585
- `EXEC` 语句, 全日志 vs. 其他, 376
- `INSTEAD OF INSERT` 触发器, 578
- 带有 `INTO` 子句, 212–413
- `IN MERGE` 语句, 405–406
- 带有 `OUTPUT` 子句, 212–413
- 强制转换类型, 374
- 保证顺序, 374
- 标识属性, 替代方案, 376
- 最小日志, 291
- 与 `SELECT INTO` 比较, 375
- TOP 表, 插入数据, 140
- `INSTEAD OF DML` 触发器, 578
- 集成, 509–512
- 排除 (IX), 637–639
- 共享 (IS), 495–501

# 内部结构

- 分配单元, 44
- B 树。参见 B 树
- 头部, 42
- 堆。参见堆
- 非聚集堆, 50–51
- IAM（索引分配映射）, 44–45
- 叶子节点, 46–49
- 页, 42
- 行偏移页, 42
- 表组织, 43–53
- 内部节点, 708
- 季度数组, 483, 523

# `INTERSECT` 特性, 291

- 所有 `INTERSECT` 实现, 254
- 逻辑查询处理, 38–39
- NULL 的处理, 11, 249
- 带有 `ORDER BY` 子句, 249
- 日期和时间的交集, 452–456
- 日期和间隔计算, 452–456
- Allen 插入, 452
- `AND` 操作符性能问题, 252–255
- 用于 CTE 计数活动视图, 457
- 分组计数, 458
- 索引优化, 252–255
- 交集, 452–456
- 最大间隔, 456–465
- 间隔填充, 466–471, 816

## 左外连接

- 用于 CTE, 718, 722–723
- 逻辑子句, 718–719
- 内部循环, 718, 723–728, 730–733
- 层级, 718
- 递归 vs. 循环, 718
- 存储过程, 718–719
- 子图算法, 719–729
- 带有路径枚举的子图, 733–736

# 迭代解决方案

- 基于游标的解决方案, 151–152
- SQL Server 的迭代执行方法, 149, 152–153
- 分离效率, 246
- 使用游标的强相关, 314–315
- CLR 函数优越性, 397
- 使用 UDF, 549–550
- vs. 基于集合的方法, 149–153

# K

- `KEEP PLAN` 提示, 570–571
- 使用序列对象自动创建, 384–385
- 定义为 B 树聚集索引的列, 46
- 密度对优化的影响, 351–352
- 内存内存不支持外键约束, 704
- 索引访问方法, 49
- 隐式添加到索引的键, 102
- 键列表限制, 119
- 非聚集索引中的查找, 53
- 非聚集索引查找 + 范围扫描, 81–90
- 主, 408–409
- 值的历史, 85–86
- Kriegel, Hans-Peter, 456
- 峰度, 485–523

# L

- `LAG` 窗口函数, 287–299
- 语言 `SET LANGUAGE`, 443–435
- 年末一天计算, 547–549
- `LAST VALUE` 窗口函数, 285–286, 513

# 叶子节点

- 锁, 673–674

# 侧向派生。SELECT APPLY运算符

# `lazywriter` 进程, 42–43

# `LEAD` 窗口函数, 287–292

- 带有 `DBCC` 命令的 leaf having, 70–71

# 左层级

- 聚集索引中的行顺序, 46–47
- 有序聚集索引扫描, 62–63
- 聚集索引中的行, 93

# 左 HIERARCHID 组, 756–759

# 插入到

- 附加的影响, 743, 782

# 左页

- BW-Tree 结构, 678–679
- 密度, 48–49
- 每行访问方法, 94–95
- 拆分, 46–47
- 跳跃查找, 421–422

# 左外连接。参见外连接

- 带有其他连接, 233–245
- `LEFT JOIN`, 等价, 229
- 逻辑顺序, 3
- 保留表, 817

## 左外连接继续

- 逻辑处理阶段, 8–9
- 小于 (<) 基数估计, 561
- `LIKE` 谓词, 112–115
- 卡方检验, 501–505
- 决定系数 (CD), 498–499
- 相关系数, 498–499
- 协方差, 495–498
- 线性回归, 499–501
- 斜率, 499
- 连续变量, 495–500
- 字面量和时间, 334–436

# LOB (对象) 数据类型

- `LOB_DATA` 分配单元, 44
- 不支持，704

# 局部变量方法, 319–322

# 连接阻塞, 637

# 字符串, 338–640, 657

- 引起死锁：参见死锁
- 延迟持久性, 643–645
- `dm_exec_views` 查错, 638–640
- `dm_os_tasks` 查错, 640
- `dm_tran_locks` 查错, 399
- 升级, 361–363, 641
- 交叉锁 (X), 337
- 内存型 OLTP vs. 传统, 691–693
- 交叉锁 (X), 337
- 共享锁 (IS), 337–639
- 隔离功能, 337
- 隔离级别：参见隔离级别
- `KILL` 命令, 641
- `CLOCK`, `TIMEOUT` 选项, 638, 641
- 内存资源, 641
- `NOLOCK` 提示, 647
- Read Committed 隔离级别, 338
- Read Uncommitted 隔离级别, 336–637
- `READPAST` 提示, 446
- 资源层次结构, 337
- 由 `SELECT INTO` 创建, 375
- 共享锁 (S), 336–639, 648–649
- 意图锁 (SIX), 337
- SQL 警报模型, 336
- TOP 更新, 361–362
- 更新锁 (UI), 337
- `UPDLOCK` 提示, 337, 650–651
- 等待状态, 639
- 预写日志, 443
- 对数日志, 322–324

# 逻辑操作属性, 239

# 逻辑顺序 vs. 类型, 3

# 逻辑处理顺序 vs. 物理顺序, 2–3

# 逻辑查询处理阶段

- 添加外行阶段, 4–5, 13
- `APPLY` 运算符, 26–29
- 卡卡尔积, 4–5–8
- 简要描述, 4, 6
- `DISTINCT` 阶段, 18–20
- 表达式评估阶段, 6
- `EXCEPT` 运算符, 38–39
- 图, 5
- `FROM` 阶段, 4–5–14
- `GROUP BY` 阶段, 4–5–16
- `HAVING`, 4–5–17
- `INTERSECT` 运算符, 38–39
- 逻辑顺序 vs. 类型, 3
- `OFFSET-FETCH` 过滤器, 6, 22
- `ON` 谓词阶段, 4–5, 9–13
- `ORDER BY`, 6–22
- 子句顺序, 3–4
- `PIVOT` 运算符, 29–31
- 示例查询, 6–8
- `SELECT` 阶段, 4–5–20
- 步骤数, 3
- 表运算符, 26–27
- `TOP` 过滤器, 6, 22–26
- `UNION` 运算符, 38–39
- `UNPIVOT` 运算符, 27, 31–35
- 虚拟表生成, 4
- `WHERE` 阶段, 4–5–14
- 窗口函数, 35–37, 268–269

# 逻辑读取作为访问方法的性能指标, 57

- `STATISTICS IO` 输出数据, 55

# 激活阶段, 插入问题, 361

# 刷新缓冲区以完成事务, 634

# 日志密集操作, 361

# 锁测量, 377–378

# `SELECT INTO` 命令日志选项, 374

# 序列创建期间的统计信息, 390–393

# 使用覆盖索引最小化的开销, 93

# 关联嵌套循环，生成自, 229

# 键锁, 533

# 非聚集索引查找 + 范围扫描, 81–90

# `RID` 请求, 551

# 无序索引索引扫描加, 91–93

## 移动平均计算

- 嵌套循环算法的 `LOOP` 提示, 244–245
- `PERCENTILE_DIS` 函数用于, 480–481
- `ROW_NUMBER` 解决方案, 369–370
- 测试用表, 368–369
- 窗口函数用于, 289–291

# 嵌套循环操作符, 98, 183–186, 240–241

# 递归, 17

# 最短路径解决方案对比 CTE, 792–801

## 内存

- SQLOS 的内存泄漏处理, 586, 588
- 见“In-Memory OLTP”中的 OLTP
- 内存优化的数据文件, 675
- `MEMORY_OPTIMIZED` 选项, 140
- 在 `TOP` 键上使用 `WHILE` 循环，无键索引, 581
- 内存优化的表，并行性受限, 179
- 丢失更新, 645–646
- LRU-22 算法

# 合并连接用于, 241–245

# 冲突预防, 408–409

# M

- Mechanic, Adam, 641
- MAD (平均绝对偏差), 484, 523
- 多对多透视, 304–307

- `DELETE` 配合, 405–406, 414–416
- `INSERT` 子句用于, 405–406, 414–416
- `INTO` 产生结果用于, 336–337
- Martin, Laurent, 456

# 物化路径模型

- 优点, 743, 存储过程用于, 744–745
- `MERGE` 子句, 405–410
- `MERGE` 谓词, 409–410
- 多源行到目标行的错误, 406

### HIERARCHY 数据类型

- 先，返回, 751–753
- 定义, 742
- 执行计划用于, 750, 754
- NULL 处理, 407
- `ON` 谓词, 405
- `OPENROW BULK` 子句来自, 410–411
- `OUTPUT` 子句用于, 414–416
- 索引创建用于, 743–744
- 索引大小限制, 743



- 叶子节点返回, 751
- 级别和路径修订, 745–748
- 性能问题, 752
- `SERIALIZABLE` 级别用于, 409
- 数据来源, 410–411
- `UPDATE` 子句配合, 405–406, 414–416
- `USING` 子句, 405–410
- 查询, 749–754
- 抖动效应, 743
- 排序, 752–753
- 拆拆路径, 752–753
- 子树，合并, 748–749
- `WHEN MATCHED` 子句, 405–407, 415
- `WHEN NOT MATCHED` 子句, 404–407
- `MERGE TOP` 表, 360
- 子树，返回, 751
- 子树, 751
- 最大并行度, 175–178
- Microsoft SQL Database 备用锁, 636
- Microsoft SQL Server: SQL Server
- Microsoft 虚拟学院 (MVA), 224
- Microsoft Visual Studio for Code, CBR 589–591
- Microsoft Windows 时间, 421–422
- 窗口函数, 301–302
- 窗口函数 (`OVER`) 用于, 275–276
- 最大工作线程, 176–188
- `dmax_join`, 176, 177
- 最小值查找, 195–199
- 缺失值
  - 查找, 195–200, 291–292
- 最大间隔值问题, 455–466
- `MAXRECURSION` 提示, 728–729
- 平均绝对偏差 (MAD), 484, 523
- 平均平方 (MAD), 484, 523
- 处理, 10
- 混合平均值, 43
- 算术, 729
- 连续变量的, 487–488, 509–512
- MAD (平均绝对偏差), 484, 523
- MSD (平均平方), 484, 523
- 作为分布时, 479, 523
- 自定义聚合计算, 324–327
- `TOP TIES` 计算, 480
- `MONTH` 函数, 425
- 中位数
  - 连续分布模型, 368
  - 定义, 479, 523
  - 配合 `APPLY` 的 `OFFSET-FETCH`, 370–371
  - `PERCENTILE_CONT` 解决方案, 369
  - `PERCENTILE_CONT` 解决方案, 480–481
- 移动平均计算
  - 对其他统计数据的探索, 512–513
  - 定义, 523
  - 指数移动平均, 515–518
  - 简单移动平均, 513–514
  - 加权移动平均, 514
  - 窗口函数用于, 274

## MSD

- MSD (平均偏差), 484, 523
- 多连接查询
  - `DISTINCT` 子句在, 231–232
  - `FORCE ORDER` 选项, 236–237
  - 左外连接接其他连接, 234–235
  - 逻辑评估顺序, 234–237
  - 多个 `ON` 子句在, 236
  - 优化，忙碌, 236–237
  - 括号在, 235–236
  - 物理连接顺序, 232–233
  - 右外连接用于优化, 235
- 多个出现次数, 65–76
- 分配顺序来源, 65–76
- 索引顺序扫描来源, 71–86
- 多语句 TVF (表值函数), 550–553
- 多表查询
  - 基于 `APPLY` 操作符, 218–222
  - 连接在。见 joins
  - 关系顺序在。见 relational orders
  - 查询作为。见 subqueries
  - 表格表达式作为。见 table expressions
  - 多值子查询, 188–199
  - 索引用于, 779
  - 根节点返回, 779
  - 性能问题, 782–783
  - 查询, 784
  - 节点路径用于, 781
  - 节点计数, 786
  - 根的子树, 784–785
  - 值分配, 778–784
  - CTE, 208
  - 派生表，问题来自, 206
  - 循环 嵌套连接算法
  - 顶部, 577–578
  - .NET 基础类, 597
  - .NET Framework, Microsoft。见 SQL

## N

- 名称解析，隐含，错误来自, 201–202
- 美国国家标准技术研究院 (NIST), 707
- 原生编译过程环境，in-Memory OLTP
- 优点, 690
- `ATOMIC` 块, 639
- 交叉计数查询，用于, 703
- 不支持游标, 704
- 性能对比 互操作性, 699
- 重试逻辑, 102
- 统计生成, 698
- 存储过程 (SQL) 可能包含在, 705
- 验证错误, 702
- 负逻辑对比正 逻辑, 200–201
- 嵌套循环连接算法
- `AND` 对比 `In`, 784
- 强制优化策略, 244–245
- 索引性能问题, 239–241
- 嵌套循环操作符
  - 瓶颈，通过 `Parallel APPLY` 消除
  - 模式, 188–186
  - 基数估计问题, 985
  - 并行扫描配合, 169–170
- 嵌套集解决方案
  - 优点, 778
- 节点先祖，返回, 786
- 动态树缺陷, 778, 782
- `NO_BROWSETABLE`, 568
- 节点
  - 添加，长路径来自, 767
  - 先祖。见 ancestors
  - 子节点。见 child nodes
  - 之间的连接。见 edges
  - 定义, 707
  - 后代。见 descendants
  - 有向边对比 无向边, 707–708
  - 下一层 级, 718
  - 父节点。见 parent nodes
  - 子树，返回, 719–720
  - 类型, 708
- `NOLOCK` 提示, 62, 67–648
- 非聚集索引查找 + 扫描 + 查找, 81–90
- 非聚集
  - 聚集键, 52–53
  - 覆盖非聚集索引查找 + 扫描, 6
  - 数据结构配合, 43–44
  - 错误, 122
  - 全扫描的, 153–156
  - 包含的非键列在, 119–120
  - In-Memory OLTP 要求, 704
  - 键列表，限制, 119
  - 键查找, 53
  - 级别, 49–50
  - 内存优化的表, 677–680
  - 非聚集索引查找 + 扫描 + 查找, 81–90
  - 排序覆盖非聚集索引扫描, 63–65
  - 行标识符 (RIDs), 51
  - 查找顺序, 720

## O

- 对象，页面成员在, 42
- `OFFSET BY`, 285–287
- `OFFSET-FETCH` 过滤器
  - 2012 对比 2014 版本, 341
  - `FETCH` 子句, 346
  - `FIRST` 关键字, 345
  - 索引优化, 357
  - 隔离级别对输出的影响, 354
  - 中位数计算配合, 370–371
- `NEXT` 子句, 348
- 偏移要求, 348
- 计划中的 `OffExpression` 属性, 354–355
- `ONLY` 子句, 349
- `ORDER BY (SELECT) NULL`, 346
- `ORDER BY` 子句要求, 345–346
- 排序问题, 23–26, 345
- 分页解决方案配合, 354–357
- 逻辑处理中的阶段, 6, 22–26
- `ROW/ROWS` 关键字, 345
- 与 `TOP` 过滤器的相似性, 345
- 语法用于, 235

## ORDER BY 子句

- 列来自 SELECT 阶段, 17
- 游标返回, 21–22
- 排序的 `DISTINCT` 子句, 542–546
- 配合分组集, 227–338
- 逻辑顺序, 3–5
- 逻辑阶段示例, 7
- NULL 值处理, 11
- 带有排序的 `OFFSET-FETCH` 提示, 22–26, 345–346
- 逻辑处理中的阶段, 6, 20–22
- 在集合操作中禁止, 38–39
- 关系操作符配合, 249
- `SELECT` 子句，变量方法配合, 319
- `SELECT NULL` 技巧, 285, 344
- 带有表内部查询的, 204
- 配合 `TOP` 过滤器, 226–341
- 窗口函数在, 35–37

## 排序非聚集扫描

- 结构在 B-树上, 52
- `OFFSET-FETCH`, 285–287
- 2012 对比 2014 版本, 341
- `FETCH` 子句, 346
- `FIRST` 关键字, 345
- 索引优化, 357
- 隔离级别对输出的影响, 354
- 中位数计算配合, 370–371
- `NEXT` 子句, 348
- 偏移要求, 348
- 计划中的 `OffExpression` 属性, 354–355
- `ONLY` 子句, 349
- `ORDER BY (SELECT) NULL`, 346
- `ORDER BY` 子句要求, 345–346
- 排序问题, 23–26, 345
- 分页解决方案配合, 354–357
- 逻辑处理中的阶段, 6, 22–26
- `ROW/ROWS` 关键字, 345
- 与 `TOP` 过滤器的相似性, 345
- 语法用于, 235

# 有序集函数

- 有序集函数，290, 326–327
- `OUTER` 运算符，27–28, 221
- 外部连接
  - `FULL` 连接，见 229。另见外部连接
  - 逻辑处理阶段，13
  - 不允许由内存优化（In-Memory OPT）允许，705
  - `ON` 子句，230
  - `ON` 与 `WHERE` 子句对比，见 14–15
  - 物理连接评估顺序，232–233
  - 保留的表，13, 229–230
  - `RIGHT` 关键字，见 229
  - 语法问题，见 224–225
  - 类型规格，13
  - `WHERE` 子句，230
- 外部行，13
- 乱序页，47
- `OUTPUT` 子句
  - 冲突函数，414–416
  - 用于分块（chunking），414
  - 列识别，411
  - `DELETE` 子句，见 413
  - 灵活性，411
  - `INSERT` 子句，见 412–416
  - `SELECT` 子句，见 411
  - `INTO` 子句，见 411, 412–413, 414
  - `MERGE` 语句，见 414–416
  - `UPDATE` 语句，见 411–414
- `CXPacket` 数据结构，163
- 并行度 (DOP)，159, 161–162, 164, 175
  - 需求分布方案，163, 171–172
  - 对逻辑 CPU 数量的依赖，89–90
- `Exchange` 算子的分布（Distribute）变，160–163
- `Exchange` 算子，160–166
  - 执行计划索引指示，159
  - 生产线模型，158
  - 减少行优化，168–170
  - 仅前向扫描行，116
- `Exchange` 聚合（Gathers）变，160–163, 165–166
  - 哈希分布方案，163–165
- `Hash Join` 算子，位于 170–171
- `Hash Match` 算子，167
- 并行抑制因素，178–181
  - 实例级策略，175–176
  - 间隔计算，见 464–465
  - 旧版本与 2014 版本对比，74
  - 查询优化器中的手写重写，181–188

## P

- 数据和时间的排序，466–471
- 页面空闲 (GFS)，45
- 页面
  - 由内存优化（In-Memory OPT）消除，672–673
  - 范围（extents），43
  - 乱序，47
  - 分拆，在 47–48
  - 结构，42
  - 表结构，见 44–45
  - 与 `OFFSET-FETCH` 过滤器的分页方案，见 345
  - 对 `OFFSET-FETCH` 的优化，354–357
  - 对 `ROW_Number` 的优化，358–360
  - 对 `TOP` 的优化，346–363
- 并行查询执行
  - 优势，158
  - 亲和性掩码（Affinity Mask）设置，177
  - `APPLY` 模式索引，181–186
  - 广播分布方案，163
  - 批量复制 API (Bulk Copy API)，179
  - 基数高估的影响，100
  - 基数低估的影响，99
  - 配置指南，177–178
  - 并行性成本阈值（Cost Threshold for Parallelism）设置，175–176
  - 成本，与串行执行对比，87–90
  - CPU 视图，见 176–177
  - 最大并行度（Max Degree of Parallelism）设置，175–178
  - 最大工作线程流（Max Worker Threads stream），176–178
  - `dop_max` 设置，176
  - 不与内存优化表一起，696–697
  - `Exchange` 算子的合并变，165–166
  - 嵌套循环解决方案，181–186
  - 非聚簇索引查找 + 扫描 + 查找，87–89
    - `NonParallelPlanReport` 节点，180–181
  - 优化过程，见 470–471
- 并行 `APPLY` 模式，181
- 并行 (`Gather Streams`) 算子，88, 160–163
  - 部分聚合，171–173
  - 分区表，Stop 模式工具，90
  - 窗口特性，164
  - 查询成本度量，178
  - 查询计划，见 159
  - 范围分布方案，163, 169–170
  - 重分区（Repartition）算子，163, 169–170
  - 资源信号量（Semaphore grants），175–176
  - 轮询（round robin）分布方案，163, 169–170
  - 行分布策略，163–165
  - 扫描，见 168–170
  - `SELECT INTO` 批量操作，173–174, 374
  - 排序，165–166
  - SQL Server 使用的流模型，159
  - 每个区域线程，259, 161
  - 跟踪标记，90, 117
  - UDF 抑制，179–180, 548
  - `CXPacket` 数据结构，163
- `PRECEDING` 关键字
  - 编译值，555–558
  - 在存储过程中声明，559
- 父节点
  - 见祖先（ancestors）
  - 嵌套集，778
  - 父级接列表，转换为 `HIERARCHY`，771–773
- 用于日期时间的 `PARSE` 函数，433–435
- 分区，排序，见分区排序（partitioning, ordering）。
- 分配单元，44
- 远程触发的变化，570–571
- 由 `PARTITION BY` 排序的索引，117–118
- 并行查询执行，171–173
  - 窗口函数对比，281–285
- 带 `PARTITION BY` 的窗口函数，263–266
  - 路径，见祖先，730–733
- 循环，确定，740–742
- 循环的 vs 无环的，708
- 长路径，767–777
- 多路节点，711
- 带路径的子图，733–736
- 拓扑排序使用，736–739
- 传递闭包（transitive closure）。见传递
- Pearson 平方公式，501–505
- `PERCEPT` 输入索引，`TOP`, 342
- 解决（solve），476–479
  - 汇总的，476
- 与 `PERCENT_RANK OVER` 的计算，777–438
- 总计的，268–289
- `PERCENT_RANK` 窗口函数，288–289
- 分位数
  - 分位数范围计算，483
  - 用于计算的反向分布函数，289–291
  - 分位数范围，483
- 用于寻找分位数范围的 `PERCENTILE_CONT`, 480–481
  - 用于寻找分位数范围的 `PERCENTILE_CONT`, 483–481
- 用于寻找中位的 `PERCENTILE_CONT`, 369–370
- `PERCENTILE_CONT` 窗口函数，289–291
- `PERCENTILE_DIS` 窗口函数，289–291, 480–481
  - 典型工作负载，见扩展事件（Extended Events）
- 性能
  - DMVs（动态管理视图），134–139
  - 查询调优。见查询执行；
  - 测量工具。见执行计划；
  - 统计，性能相关
- 悲观并发模型，674
- PGS（空页空间），45
- 幻读定义，642–646
- 用于验证的可序列化级别，651–652
- 验证级别的对比表，646
- 查询执行阶段。见查询处理
- 电话号码，549–550
- 物理执行计划，97



- 物理查询依赖，41
- 物理操作属性，239
- 物理处理顺序，2–3
- 物理查询执行计划，2
- 与 `PIVOT` 运算符的实际频率，503
    - `CASE` 示例的隐式使用，30–31
    - 与自定义聚合，315–318, 318–319
    - 动态，530–535
    - 用于 XML，318
- 隐式分组阶段，30
- 多对一 `PIVOT`，304–307
- 一对一 `PIVOT`，300–304
- 逻辑阶段，27–29
- `PIVOT` 运算符元素，27
- `PIVOT` 运算符顺序，302–304
- 带 `PIVOT` 的行，534
- 扩展散属性，301–302
- 用用例，299
- Plan Explorer 工具，139
- 计划最优性，570–571
- 计划稳定性，568–570
- 并行计划。见并行查询执行
- 查询执行计划。见执行计划
- POC（索引，排序）的覆盖模式
    - 关联查询优化，192
    - 与排序优化对比，284–285
- 运行总计优化，271–273
- 每组前 N 任务，请求，363–365
- 人口，479, 490。另见分布
- 正逻辑 vs. 负逻辑，200–201
- Pötke, Marco，456
- 使用 `CUBE` 函数创建幂集，331–333
- `PRECEDING` 关键字，269–274, 277, 280–281

# 多个谓词

- 多个谓词，基数估计的，104–107
- 基数估计的。见基数估计
- 聚簇索引查找 + 扫描，93–94
- 早期收益，166
- 执行计划。见执行计划
- 扩展事件，优先级，131–134
- 扩展事件统计，54, 56
- 并行中的哈希连接，170–171
- 过程统计，138
- 直方图。见直方图
- 索引索引，120–162
- 处理顺序，物理 vs. 逻辑，2
- 查询。见查询处理
- 包含非键列，119–120
- 索引扫描统计，76–81
- 内联索引定义，130–233
- 可编程对象
- 动态 SQL。见动态 SQL
- 链接优化策略和选项，33–368
- SQLCLR。见 SQLCLR 编程
- 触发器。见触发器
- 并行 API 模式，183–188
- 并行优化，176–177
- 用户定义函数，不与，696–697
- 用户定义函数。见 UDFs（用户定义的 `PARTITION BY` 子句，117–118）

# 行标识符

- `RAISERROR`, 664–665
- `RAND`, 未定义的选项的, 546
- 分布范围, 482–483, 523
- 范围并行分布方案, 163
- 范围谓词访问方法, 95–97
- 范围扫描：参见
- `RANK UNBOUNDED PRECEDING`, 279–280
- 窗口帧的 `RANK`, 276–280
- rank，
  - `CUME_DIST`, 228–289
  - `PERCENT_RANK`, 228–289
  - 排名分布窗口函数, 282–283, 285
  - `RANK` 窗口函数, 282–283
  - 用于窗口函数, 281–285
- RDBMS (关系数据库管理系统), 2
- 读提交（Read Committed）级别, 644, 648–660, 650
- 读提交快照（Read Committed Snapshot）级别, 642, 652, 655–660
- 未提交（Read Uncommitted）级别
  - 与与其他级别的比较, 646
  - 无共享锁的 own, 646–648
  - 包含 `NOLOCK`, 68
- 订单上无共享锁, 78–81
- 安全类别选项的使用：参见访问方法
  - `AccessKind.Read`, 179
  - 脏数据, 645–647
  - 隔离级别，用于：参见隔离级别
    - 逻辑上的, 55–72
    - 幻读, 645, 646–652
  - 预读, 55
- `REBUILD`, 133
- 重建索引, 135
- 存储过程的重新编译, 568–571
- `RECOMPILE` 选项
  - 效率益处, 537–539
  - 带有问题, 559
  - 语句级-过程级, 537, 559
  - 存储过程，防止，级别, 558–560, 562–563
  - 表变量，连同, 143–148
- 未知参数嗅探（unknowns sniffing of）, 10
- 数据恢复模型, 376–378
- 事务恢复模型, 624
- 递归
  - 祖先, 730–733
  - 在 `ON` 子句中限制, 729
  - `MAXRECURSION` 提示, 728–729
- 递归 CTE (`RECURSIVE CTEs`), 209–211, 718–722, 723
- 触发器, 577–578
- 分治法算法, 733
- 引用
  - 列，表限定的, 8
  - 关联性, 189
- 回归，关系的, 499–501
- 关系数据库管理系统 (RDBMS), 2
- 关系除法, 188
- 关系引擎，SQL Server, 97
- 关系索引树 (RI-tree) 模型, 456
- 关系模型
  - 针对缺失值的, 10
  - SQL 对重复行的的偏离, 18
- 关系运算符
  - `EXCEPT`, 249, 255–256
    - 输入要求, 249
  - `INTERSECT`, 249, 252–254
  - `NULL` 的处理, 11
  - 带有 `ORDER BY` 子句, 249
    - 优先级, 249
    - 结果列名, 249
    - 语法, 249
  - `UNION`, 249–252
  - 运算符对关系的应用, 38
- 关系标准属性, 286
- `REORGANIZE` 关键字, 135
- 重分区流算符 (`Repartition Streams operator`)
  - 使用导致的瓶颈, 183
  - 流重分布的角色, 161, 169–170
  - 优化器的行分布策略, 163
  - 触发触发器太少, 169–170
- 可重复读（Repeatable Read）级别, 646, 649–651, 691
- `REPLACE` 函数, 597
- 资源管理器 (`Resource Governor`), 173–176
- `RESULTS SET` 子句, 573–575
- 重试逻辑, 669–670
- RIDs (行标识符)
  - 非聚集索引查找 + 范围扫描 + 查找, 81–90
  - 结构, 51
- 右外连接
  - 优化多查询连接, 235
  - `RIGHT` 关键字, 229
  - 与左外连接, 230
  - RI-树（关系索引树）模型, 456
  - 行系统子句, 715–718
- 回滚
  - `ROLLBACK` 命令, 634–635
  - 临时表和变量行为, 148–149
  - 根函数, 331, 337–338
  - 根节点, 708
  - 根页, 458
  - 轮询分布方案, 163, 169–170
  - 舍入日期时间, 447–449
- `ROUND` 函数, 322
- 标准 SQL 特性, 349
- 行标识符 (RIDs), 51, 81–90
- 行数 (row numbers)
  - 计算的, 47–478
  - 生成，确定的对随机的, 283
  - 窗口函数：参见行数
  - `@rowcount`，触发器使用的, 582
  - 行分布数据集, 163–165
  - `ROW_NUMBER` 窗口函数
    - 无的, 292–294
    - 最大并发任务, 461–465
    - 中位数, 369–370
    - 优化, 358–360
    - 间隙解决方案, 466, 471
    - 带有分页的, 398–360
    - 排名函数, 282–285
    - 元素, 248
    - Top N 组解决方案, 306–365
- 行偏移量数组, 42
- `ROW_OVERVIEW_DATA` 分配单元, 44
- 行
  - 访问方法导致的错误, 65–81
  - 通过直方图估计的, 102–103
  - 从密度值估计, 107
  - 执行计划中的估计, 98
  - 生成大量连接, 216–217
  - 外部行, 113
  - 作为行单元, 269–276
  - `ROWS UNBOUNDED PRECEDING` 子句, 270–271, 273, 281
  - 运行总计计算
    - 窗口 `SUM` 示例, 264
    - 用于窗口函数: 271–273, 477
  - 年至今 (YTD) 计算, 280–281
  - 计划的昂贵部分，识别, 154
  - 碎片, 47–48
  - 非索引的全扫描，避免, 153–156
  - 需要排序时的全扫描, 57–60
  - 导致全表, 658
  - 索引扫描, 46–47, 59–81
  - 排序聚集索引扫描, 62–63
  - 排序非索引扫描, 63–65
  - 并行, 188–170
  - RIDs, 使用, 51
  - 扫描计数统计, 55
  - 存储引擎方法, 65–81
  - 表扫描/无序索引扫描方法, 57–60
  - 排序非索引扫描加, 60–62
  - 无序非索引扫描加, 91–93
  - `SCHEMABINDING` 选项，视图, 212
  - 批处理，关系到, 525
- `SCOPE_IDENTITY` 函数, 412
- 表表达式, 204
- 临时对象（表和变量）, 140, 148
- 搜索参数, 445–446
- 第二区域, 500
- 安全问题
  - 动态 SQL `EXEC` 参数, 526–528
  - `EXECUTE AS` 子句, 546
  - SQLCLR 存储过程凭据, 614
- 查找
  - 聚集索引查找 + 范围扫描访问方法, 93–94
  - 索引中的成本, 154
  - 行成本, 49–50
  - 非索引查找 + 范围扫描方法, 94–97
  - 强制作为策略, 154–155
  - POC 策略生成的, 364
  - 索引查找访问方法, 49
  - 在非索引中查找特定键, 52
  - 算符，参见 Seek Index 算符
- Segment 算符, 64
- Seid., Thomas 456
- `SELECT` 子句
  - 一次操作, 18
  - 带有 `AS`, 17
  - 列分析和处理顺序问题, 14
  - 带有列引用, 17
  - 表达式评估阶段, 17–118
  - 评估阶段, 6
  - 带有 `INTO`，参见 `SELECT INTO` 命令
  - 逻辑顺序, 3–5
  - 带有 `ORDER BY` 子句, 20–22

# S

- 使用交叉连接生成样本数据, 225
- SARGS (参数), 445–446
- `SAVE TRAN` 命令, 635
- 标量子数组, 187–188
- 扩展
  - 数据库，查询调整, 153–157
  - 并行流方法, 159–166
  - 排序并行以及窗口结果的连接分组, 273
- 扫描
  - 后向扫描, 116–117, 199
  - 聚集索引查找 + 范围扫描, 93–94
  - 排序的非索引查找 + 范围扫描, 94–97
- 分配顺序。参见分配扫描
- 索引扫描顺序的, 65–76
- 索引扫描顺序带有, 76–81
- `DATETIME` 时间, 419–420
- `DATETIMEFROMPARTS` 函数, 431
- SMAs (移动平均值), 513–514
- 快照隔离级别, 646, 652–655, 691
- 嗅探，禁用, 110
- Sommerkers, Erik, 242, 573, 577
- 标识属性, 384,390–395
- `INCREMENT BY`, 383
- 键，自动, 387–394
- `MAXVALUE` 属性, 382–383
- `MINVALUE` 属性, 382–383
- 缺失值的引起, 387
- 某些 `NEXT FOR` 键, 382–386
- 键允许 `NULL`, 385
- 覆盖现有键, 383
- 性能考虑因素, 387–394
- 回滚事务问题, 386
- `START WITH` 属性, 383
- 基数效应，影响, 100
- 基数理解，影响, 99

# 离散属性

- 离散属性，301–303, 315–316
- 分布的离散程度
- 四分位间距，483
- 均绝对偏差，484
- 均方差，484–485
- 范围，482–483
- 标准差，486–487, 490, 498, 511, 523
- 方差，485, 505–508
- `sp_statement`, 已完成事件，131
- SQL 1–2, 参见 T-SQL (Transact-SQL) 目录

## SQL 数据库

- 备用模型，636
- 默认隔离级别，646
- SQL 注入攻击，526–530, 533
- SQL Sentry，539

## SQL Server

- 数据工具 (SSDT)，589
- Management Studio，参见 SSMS (SQL Server Management)

## Management Studio

- 查询优化。参见查询优化器器
- 与 T-SQL 的关系，1
- SQLOS (操作系统)，586, 588

# SQLCLR 编程

- 标量函数的优势，597
- 优于 UDF（用户函数）的优势，595
- `AppDomain` 管理和范围，587
- 架构，587–588
- 程序集最佳实践，587–588
- `AUTHORIZATION` 选项，588
- 调用 CLR 函数，592, 600
- CAS (代码访问安全)，587
- 大写敏感性问题，595–597
- 上文连接字符串，603–605, 607
- `CREATE ASSEMBLY` 命令，587–591
- `CREATE FUNCTION` 语句，590–591
- 创建表值函数，598–600
- 通过方式访问数据库，603–605
- `DataRow` 类型，604
- 以及日期时间类型，595
- 位于 DLLs 中，571
- 启用代码，587
- `EXTERNAL_ACCESS` 权限，587–588, 605
- fill row 方法，598–599
- `FillMethodName` 选项，599
- 函数创建，590–599
- `HostProtection` 属性，588
- 可枚举值，598
- 函数上的索引，590
- 进程内宿托管模型，586
- `ISNullProperty`，596, 599
- 内存实用程序，600–603
- 数据库数据库的能力。参见 SQLCLR 存储过程
- .NET 基类库，597
- .NET 基础，85–586
- 可空值，595
- `NUMERIC` 类型问题，592–593
- 卸放到应用程序服务器，597
- `ORDER BY` 子句，600
- 程序集的所有权，588
- `PERMISSION_SET` 选项，587–588
- 属性设置，597
- 发布程序集，591–592
- 标量函数的查询计划，588–589
- 只读访问，604
- 远程服务器访问，605
- `SAFE` 权限集，587, 591
- 沙箱，内存，588
- 标量函数使用 case，597
- 的安全权限，586
- `SqlCreateIndex` 枚举，595–597
- `SqlFacet` 属性，593, 596
- `SqlFunction` 属性，590–595
- SQLOS 集成，586
- `SqlString` 类型，590–593
- `SqlQuery` 命名空间，589–590
- SSDT 对象，587–590
- 存储过程。参见 SQLCLR 存储过程
- 字符串问题，598–603
- 字符串类型问题，593–595, 597
- 脚本自定义，自定义，595
- `TableDefinition`，599
- 表值函数，流，598
- `TRUE_WRITEONLY` 模式，605
- T-SQL 函数创建，591–592
- 与 SQL Server 的类型兼容性，590–595
- 类型，在 Visual Studio 中，593
- UDF 类函数，588–596
- `UNSAFE` 权限集，587–588
- 聚合的定义聚合。参见 SQLCLR 用户定义聚合
- 用户定义类型。参见 SQLCLR 用户定义
- `SqlTypes` 属性，594

## SQLCLR 存储过程

- 与其他选项，605
- 上下文连接，607
- 606–607
- `@@SERVER` 函数，613
- `EventData` 属性，616
- 异常处理，609–613
- `ExecuteAnd` 方法，610–612
- 执行，606–607
- 身份冒充，614
- 修改数据库的能力，605
- 公共，606
- `RAISERROR` 问题，511–612
- 返回值，606
- 带安全凭据，614
- 发送方法，607–609
- `SqlContext` 类，608–614
- `SqlPipe` 类，607–609
- 模板，606
- `THROW` 语句，828

# BI 统计

- 触发器，615–616
- try-catch 块，621–613



# SQLCLR 用户定义聚合

- `Accumulate` 方法，629–630
- 二进制格式，628–629
- .NET 中的集合类，629–630
- 用逗号分隔，629–632
- 创建，628–629
- 重复值，631
- 可序列化实现，630–631
- `Invert` 方法，628–630
- 周期，628–629
- `Merge` 方法，629–630
- 合并方法，628–629
- 查询计划限制，631
- `Read` 方法，631–632
- 架构引用，629
- 序列化需求，629
- `SQLString` 类型，`SQLAggregate` 设置，631
- 模板，628
- `terminate` 方法，629–630
- 测试，632
- `Write` 方法，631–632

# SQLCLR 用户定义类型

- 聚合选项，625
- 方法和属性名称的大写敏感性，621
- 复杂类型，621–627
- 转换问题，620
- 创建，617–618
- 工厂方法，624–625
- 功能，617
- 二进制序列化接口，625–626
- 实例化，620
- 原生格式，620
- `Null` 属性，618
- `Parse` 方法，618–619, 623–624
- 公共属性，623–624
- 发布，619–620
- 架构，620
- 可序列化属性，618
- `SQLDefinedType` 属性，628
- 存根，620–621
- 模板，617–618
- `ToString` 方法，618–619, 621, 627
- `UserDefined` 由大小，625
- `Write` 方法，626–627

# SQLFacet 属性，SQLCLR

593, 596

# SQLOS (操作系统)

586, 588

# SQL 外部

175–177

# sql_statement 事件

123

# SQLString 类型，SQLCLR

590, 595–597

# SQLTypes 命名空间，SQLCLR

590–595

# SQL_VARIANT 类型

542–543

# SSMS (SQL Server 数据工具)

589

# 显示估计执行计划

53

# Include Actual Plan 选项

138–139, 151–155

# 查询性能，测量

54

# 标准差

486–487, 490, 511, 523

# 标准正态分布

487–488

# SQL

1

# 星型连接

- 内联性能，130
- 行存储与列存储统计数据，123–127

# 语句完成事件，扩展事件会话

133–134

## BI（商业智能）统计

- 分析，505–508, 523
- 案例，473–474
- 注意中心，481, 483
- 卡方检验，501–505, 523
- 决定系数 (CD)，498–499, 523
- 异系数 (CV)，486, 523
- 离分类表，501–505, 523
- 相关系数，498–499, 523
- 协方差，498–523
- `CUME_DIST` 频率计算，477–478
- 定定积分，509–512, 523
- 自由度，485, 502, 505, 528
- 连续变量的描述统计，479–494
- 离散变量，474
- 熵计算，518–521, 523
- 频率计算，476–479, 523
- 频率分布，477–499
- F 检验，506–508
- 高总体方法，487–499
- 重要性，472
- 间分位间距，483, 495–523
- 线性依赖，495–511
- 线性回归，499–501
- 均绝对偏差，484, 523
- 均方差，484–485, 523
- 均值
- 中位数，324–327, 477
- 均值，524–520
- 离散度，518–520
- `CUME_DIST` 频率计算，477–478
- 准备数据，473–474
- 离散分布，487–488
- SQL，1
- 统计数据（业务智能）
- 周期，498–523
- 离散度，509–512
- 偏度，498–523
- 集中性，478–523
- 离散度，486–487, 490, 511, 523
- 标准差，487–488
- 统计数据（5）
- 55555，428–523
- 统计数据，505–508, 523
- 案例，473–474
- 注意中心，481, 483
- 卡方检验，501–505, 523
- 决定系数 (CD)，498–499, 523
- 异系数 (CV)，486, 523
- 离分类表，501–505, 523
- 相关系数，498–499, 523
- 协方差，498–523
- `CUME_DIST` 频率计算，477–478
- 定定积分，509–512, 523
- 自由度，485, 502, 505, 528
- 连续变量的描述统计，479–494
- 离散变量，474
- 熵计算，518–521, 523
- 频率计算，476–479, 523
- 频率分布，477–499
- F 检验，506–508
- 高总体方法，487–499
- 重要性，472
- 间分位间距，483, 495–523
- 线性依赖，495–511
- 线性回归，499–501
- 均绝对偏差，484, 523
- 均方差，484–485, 523
- 均值
- 中位数，324–327, 477
- 均值，524–520
- 离散度，518–520
- `CUME_DIST` 频率计算，477–478
- 准备数据，473–474
- 离散分布，487–488
- SQL，1
- 统计数据（业务智能）
- 周期，498–523
- 离散度，509–512
- 偏度，498–523
- 集中性，478–523
- 离散度，486–487, 490, 511, 523
- 标准差，487–488

# 表格

- 自定义聚合计算的类型，313–314
- 交换列值，18
- `OFFSET` 函数，425–426
- 字符串
- `sys.allocation_views`，42
- `SYSDATIME` 函数，22
- 清理，549–550
- .NET 中的集合类，629–630
- 逗号分隔的 SQLCLR 示例，598–603
- `SYSDATIMOFFSET` 函数，421–424
- `sys.partitions` 视图，22
- `REPLACE` 函数，`String.Replace` SQLCLR
- 函数性能，597
- 处理元素，245–249
- SQLCLR 类型问题，593–595
- `sys.system_internals_units` 视图，44
- `SYSDETIME` 函数，222

# T

- 结构化查询语言 (SEQUENCE)，2–3
- 结构，数据层级。参见内部数据结构
- `STUFF` 函数，318, 549–550

## 表表达式

- 路径枚举算法，719–723
- 相关查询，187–194
- 用于优化的交叉连接，226–227
- 带有 `EXISTS` 谓词，194–201
- 识别模式，198–200
- 内存优化 (In-Memory OPT)，不支持，700
- 多值，187–189
- 嵌套能力，187
- 返回 `NULL` 值，203–204
- 优化 Index SQL 算符，192–193
- POC（分区、排序、覆盖）模式用于
- 缩进，132–187
- 标量聚合，191
- 自包含，178–189
- 列名中的替换错误，201–202
- 带有表表达式的，204–205
- 基于 `TOP` 的过滤，与相关查询自包含，187, 189
- CTEs。参见 CTEs (公用表表达式)
- 派生表。参见派生表
- 内联 TVFs。参见内联 TVFs (表值函数)
- 种类，204
- 查询要求，205–204
- 使用表更新数据，402–403
- 视图。参见

## 表算符

- 笛卡尔积处理阶段，8–9
- 求值顺序，27
- 连接。参见
- 逻辑查询处理，8–14
- 逻辑查询处理，26–35

## 表扫描

- 表扫描算符 (Table Scan operators)，65
- 表扫描/未聚簇索引扫描方法，57–60
- 优于临时表的优势，143
- 基数估计，143–146
- 声明，144
- 带表的声明，571–572
- 带有内联索引定义的，130–131
- 获取到行的 IO 类，412–443
- 由于修改限制并行性，179
- `RECOMPILE` 选项，143–145
- 回滚滚，148–149
- 范围，140
- 可用的统计信息，143
- 表类型，571–573
- 临时。参见临时表和变量
- `SUBSTRING` 函数，246–248
- 树。另见树
- 移动，745–748
- 返回，748–719
- 调优，719–720
- `SUM` 函数，261–265, 268

## SUM OVER 窗口函数

- 优于 `SUM` 查询的优势，263–264
- 带有框架限制器，267–269
- `GROUP BY`，296–299
- 岛解决方案，296
- 最大并发间隔任务，459–461
- 带有间隔解决方案，466–468
- `PARTITION BY`，263–265
- 性能，266–268
- 支持的窗口元素，264
- 内存优化 (In-Memory OPT) 限制，703–705

## 代理生成

- 标识属性，381–382
- 序列对象，382–386
- 使用变量更新方法，403–404
- 分配表，44
- B-树，43–44, 50
- CTEs。参见 CTEs (公用表表达式)
- 使用 `TRUNCATE TABLE` 删除所有行，395–399
- 表达式。参见表表达式
- 堆数据结构，43–46

## 表值表，SQLCLR

## 表，继续

- HOBT (或 B-树) 组织，43–44
- IAMS (索引分配映射)，44–45, 47
- TVFs。参见 TVFs (表值函数)
- 内部结构，43–53
- 内存优化。参见 OLTP
- 内存优化，定义为，140
- `MEMORY_OPTIMIZED` 选项，572
- 算符。参见表优化的
- 分区的
  - 扫描。参见表
  - 临时。参见表和变量对象
  - 临时，带有触发器的，584–585
  - TVFs (表值参数)，571–573
  - 类型定义，571–573
  - 视图。参见视图

## 表值，SQLCLR

597–605

## 表值函数 (TVFs)

571–573

- `HOBLOCK` 提示，69
- 批溢出，128–129
- 基数估计，99–100
- 对象信息，140
- 缓存机制，147–148
- 基数估计，139
- 用例，179
- 磁盘活动来自，140
- 避免重复，140–143
- 激进写入器，140
- 全局表质量，139–140
- 表的使用，139
- `RECOMPILE` 选项，145–148
- 带有回滚，148–149
- 范围，140
- 基数估计，147
- 表执行计划，147
- 表变量，139
- 表与性能对比，143
- `tempdb` 使用，140
- 临时对象类型，139–140
- 分发器或协调线程，164–165
- `Max Worker Threads` 设置，176–178
- 并行查询执行次数，159, 161, 164
- 量子并行性，586
- 三值逻辑，106
- `NTILE` 瓦片，282–283
- `TIME` 数据类型，419–420, 422, 440, 595
- `TIMEFMPARTS` 函数，411
- `OFFSET` 偏移，426
- 基于锚的分页策略，342–352
- 带有 `DELETE` 修改，361–363
- `DESC` 选项，344–345
- `TOP` 的执行计划，353
- 锚排序的执行计划，348, 351, 352
- 索引选择，优化的影响，349
- 不保证的 `INNER ORDER` 子句，344–345
- `INSERT TOP` 语句，360
- `MERGE TOP` 语句，360
- 带有最小值，196–198
- 计算 `TOP WITH TIES` 模式，480
- 修改语句的，360–363
- 嵌套 `TOP` 分页策略，352–353
- 分页解决方案，346–343
- `ORDER BY (SELECT NULL)`，344
- 排序问题，22–26, 342
- 并行限制限制，177
- `PERCENT` 输入指示器，342
- 逻辑局部性阶段，6, 22–26
- 谓词短句，对性能的影响，349–352
- T-SQL 特有，341
- 建议添加 `OVER`，366
- 使用子查询打破相等，191–194
- Top 算符的 `Top Expression` 属性，348
- 执行计划中的 Top 算符，648
- 避免不必要的子查询，156
- `UPDATE TOP` 语句，360
- 在排序键索引上带有 `TOP` 的 `WHILE` 循环，581
- `WITH TIES` 选项，343–344
- 前 N 组结果，365
- `APPLY WITH TOP` 语句，365–366
- 跟随排序，366–368
- 拼接解决方案，366–368
- `CROSS APPLY` 解决方案，219–220
- 分区影响密度，363–364
- 元素，363
- 影响 T-SQL 解决方案的效率，363–366
- N1 解决方案，366–368
- POC 索引支持，192, 363
- `ROW_NUMBER` 解决方案，364–365
- 拓扑排序，726–739

## TRY_CONVERT 函数

`TRY_CONVERT` 函数，431–432

# T-SQL (事务型 SQL)

- 迭代解决方案的低效性，149–150, 152–153
- 与行业标准的关系，1
- 查询调优。另见 185
- TVFs（表值函数），550–553
- TVPs（表值参数）
  - 用于内存 OLTP（In-Memory OLTP）存储过程，699–702
  - 用于存储过程，571–573
- 类型转换错误，542
- 按逻辑顺序排序的，3

# UNKNOWN 值

10–11

- 基数估算中的未知值，110–115
- 无序聚集扫描，57–60
- 无序非聚集索引扫描，60–62
- 无序非索引扫描 + 查找，91–93
- 另见行转列逆列（pivoting unpivoting）
- 配合 `CROSS APPLY AND VALUES`，310–311
- 配合 `JOIN AND VALUES`，308–310
- 目的，307–308
- 配合 `UNPIVOT` 运算符，312–313

## UNPIVOT 运算符元素

- 逻辑处理中的 `UNPIVOT` 运算符元素，315

# U

- 用于偏态和峰度的 UDAFs（用户定义聚合函数），490–495

## UDFs（用户定义函数）

- 能力，546
- 基于 CLR。另见 SQLCLR 编程
- 封装，719
- 迭代逻辑解决方案，718–719
- 549–550 中的迭代逻辑
- 局限性，546–547
- 其中的多语句，549–550
- 由其引起的并行抑制，179–180，相关的共享性能惩罚，547–549
- 标量值的，546–550
- 子查询解决方案，718–724

- 带有 `AFTER UPDATE` 触发器，575–578
- 带有 `INSTEAD OF UPDATE` 触发器，578
- 在 `OPENROWSET` 语句中，405–406
- 带有 `OUTPUT` 子句，380
- 使用序列对象覆盖键，385
- 交换值，18
- `UPDATE TOP` 过滤器，360
- 使用 CTE 更新表，402–403
- 变量赋值方法，403–404

## 更新数据

- 用于防止冲突的可重复读隔离级别，652–659
- 用于防止冲突的快照隔离级别，652–659

- `UNBOUNDED` 关键字，259–272, 277–281, 286

## 无向环图

- 转换为有向图，792–793
- 道路系统场景，715–718
- 传递传递闭包的，792–801
- 加权的，718
- 无向环图。另见无向环图

## UNION 运算符

- `ALL` 变体，37–38
- 带有 `CHECK` 约束，251–252
- 成本，251
- 隐含 `DISTINCT`，250
- 执行计划，251–252
- 带有分组集（grouping sets），329–330
- 逻辑查询处理，38–39
- `NULL` 的处理，249
- 带有 `ORDER BY`，249
- 优先级，249
- 内存 OLTP 不允许联合，705

## UNIQUE 约束

- 带有过滤索引的，122
- 内存 OLTP 不支持，704
- `NULL` 值，117
- 唯一列，46–47, 52–53

# V

- 验证错误，693–696
- `.value` 方法，317–318

## 变量

- 卡方检验的独立性，501–505
- 列，473
- 之间的相关性，495–501
- 离散的，474
- 关于依赖性，499
- 作为键的来源，76–81
- 表达式，402–403
- 用于更新列的 `UPDATE`，577
- 更新锁（U），637
- 变量赋值方法，403–404
- `UPLOCK` 方法，650–651, 758

## 用户定义类型

- SQLCLR 用户定义类型，410–411

## UTC（协调世界时）

420–421

- 临时表。另见临时表和差异对象
- 窗口聚合函数。另见窗口聚合函数

## 窗口框

- `CURRENT ROW` 界符，269–270, 274, 276–278
- 默认值，286
- 用于界符，269
- 作为窗口函数的元素，264
- 快速优化案例，272
- `FOLLOWING` 关键字，269, 273–274
- `INTERVAL`，不支持，276–277
- 偏移量，用于，286
- 带有 `RANGE` 的偏移，276
- 带有 `ROWS` 的偏移，273–274
- 分区，关系，269
- `PRECEDING` 关键字，269–274, 277, 280–281
- `UNBOUNDED PRECEDING` 短语，213
- 分析，505–508
- 协方差，495–498
- 定义的，523



- `VAR` 和 `VARP` 函数，485–486，顶点，502
- 存储的数据；元数据，212
- 输入参数锁定，215
- `INSTEAD OF DML` 触发器，578
- 链接分区表，212–214
- 性能问题，213
- 查询要求，204–205
- 可属性的，211–212
- `SCHEMABINDING` 选项，212
- ，204
- 虚拟表添加行结果，13
- `APPLY` 运算符生成器，26–29
- 由 `FROM` 子句生成，8–6
- `GROUP BY` 阶段，15
- `PIVOT` 运算符生成器，29–31
- `TOP` 过滤器，22–26
- `UNPIVOT` 运算符的，31–35
- `WHERE` 阶段，14–15
- 用于 Visual Studio，589–591
- 嗅探，缺乏，560–564

## 窗口函数

- 优势，263
- `OVER` 窗口聚合函数，274–275
- `CUME_DIST ORDER`，288–289
- `DENSE_RANK ORDER`，282–283, 285–294
- 用于，259
- 快速优化案例，271
- 带有过滤器，263–264
- `FIRST_VALUE ORDER`，285–286, 511
- 频率计算，476–479
- 之间的间隙。另见窗口间隙，291–292
- `GROUP BY`，267–269
- `INTERNAL` 不支持，276–277
- 逆分布函数，289–291
- 岛屿区域，289–299
- `LAG ORDER`，287–288, 285–281
- `LAST VALUE ORDER`，291–292
- 旧版对比，2015
- 限于 `Select` 和 `ORDER` 子句，263
- 逻辑处理阶段，35–37
- `MAX OVER`，275–276
- 使用 `PERCENTILE` 寻找中位数，309
- 移动平均值计算，274
- `NTILE ORDER`，282–283, 285
- 偏移偏移，283–287
- 带有 `ROWS` 的偏移，273–274
- 优化，266–298
- `OVER` 子句，259, 263
- 间隔填充解决方案，466–471
- 某些并行，179
- 嗅探，缺乏，560–564
- 临时表。另见临时表和差异对象
- 窗口聚合函数。另见窗口聚合函数

### 窗口框

- `CURRENT ROW` 界符，269–270, 274, 276–278
- 默认值，286
- 用于界符，269
- 作为窗口函数的元素，264
- 快速优化案例，272
- `FOLLOWING` 关键字，269, 273–274
- `INTERVAL`，不支持，276–277
- 偏移量，用于，286
- 带有 `RANGE` 的偏移，276
- 带有 `ROWS` 的偏移，273–274
- 分区，关系，269
- `PRECEDING` 关键字，269–274, 277, 280–281
- `UNBOUNDED PRECEDING` 短语，213 分析，505–508，协方差，495–498，定义的，523
- `VAR` 和 `VARP` 函数，485–486，顶点，502
- 存储的数据；元数据，212
- 输入参数锁定，215
- `INSTEAD OF DML` 触发器，578
- 链接分区表，212–214
- 性能问题，213
- 查询要求，204–205
- 可属性的，211–212
- `SCHEMABINDING` 选项，212
- ，204
- 虚拟表添加行结果，13
- `APPLY` 运算符生成器，26–29
- 由 `FROM` 子句生成，8–6
- `GROUP BY` 阶段，15
- `PIVOT` 运算符生成器，29–31
- `TOP` 过滤器，22–26
- `UNPIVOT` 运算符的，31–35
- `WHERE` 阶段，14–15
- 用于 Visual Studio，589–591

## 窗口函数（续）

- `PARTITION BY` 子句，263–266
- 带有排序的分区，281–285
- `PERCENTILE_CONT`，289–291, 369
- `PERCENTILE_DIS`，289–291
- `PERC_RANK OVER`，288–289
- 总计的授予，268–269
- 带有 `POC` 索引的，271
- `RANK ORDER`，282–289
- `ROW_NUMBER`，285–281
- `ROWS` 界符，269
- `ROWS UNBOUNDED PRECEDING` 短语，270–271, 273, 281
- 排序值中的相等，`RANGE` vs，278
- `UNBOUNDED` 关键字，269–272, 277–281, 286
- 年内累计，211–280

# W

Waymire, Richard，528

- 周的计算，423–436, 439–441
- 分组依据，449–450
- 加权图，714, 718
- 移动平均值（WMAS），514
- `WHEN NOT MATCHED BY SOURCE` 子句，404–407

## 窗口框（续）

- 列 `IS NOT NULL`，222
- 由日期和时间过滤，445–446
- 不允许增长其中，14
- 带有内连接，228
- 逻辑顺序，3–5
- 逻辑阶段，7
- 来自子查询的 `NULL`，203–204
- 带有外部连接，200–213

- 逻辑处理中的阶段，4–15–143
- `UNKNOWN` 值的处理，11
- 带有键排序 `TOP` 的 `WHILE` 循环，无键索引，581

White, Paul，148, 349–543

![](img/bdc38aa36f6e2987d913ee5381474711_863_0.png)

从技术概览到特定主题的深入解析，您可以在此处获取 Microsoft Press 的免费电子书：

www.microsoftvirtualacademy.com/ebooks

下载 PDF、EPUB 和/或适用于 Kindle 的 Mobi 格式的免费电子书。

在 Microsoft Virtual Academy 寻找其他优质资源，在那里，您可以通过专家提供的免费 Microsoft 培训学习新技能，并帮助您的职业发展。

# Microsoft Press

![](img/bdc38aa36f6e2987d913ee5381474711_864_0.png)

# 告诉我们您的想法！

它有用吗？

它教给您您想学习的内容吗？

是否还有改进的空间？

请通过 `http://aka.ms/tellpress` 告诉我们。

您的反馈将直接送给 Microsoft Press 的员工，我们会阅读您的每一份回复。提前感谢！

![](img/bdc38aa36f6e2987d913ee5381474711_864_1.png)
