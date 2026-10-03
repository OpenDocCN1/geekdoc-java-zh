
# OCP Oracle Certified Professional Java SE 17 Developer 实践指南：考试 1Z0-829

提供超过 1,000 道练习题，涵盖所有考试目标。

![](img/e0249ee409e157651f035d8c59357695_0_0.png)

JEANNE BOYARSKY

SCOTT SELIKOFF

## 第 1 章：处理日期、时间、文本、数值和布尔值

## 第 2 章：控制程序流

## 第 3 章：利用 Java 面对象方法

## 第 4 章：处理异常

## 第 5 章：使用数组和集合

## 第 6 章：使用流和 Lambda 表达式

## 第 7 章：打包和部署 Java 代码并使用 Java 平台模块系统

## 第 8 章：管理并发代码执行

## 第 9 章：使用 Java I/O API

## 第 10 章：使用 JDBC 数据库

## 第 11 章：实现本地化

## 第 12 章：模拟考试 1

## 第 13 章：模拟考试 2

## 第 14 章：模拟考试 3

## 引言

表格 1.1：Java 17 专业认证考试

表格 1.2：Oracle 目标及相关学习指南章节

![](img/e0249ee409e157651f035d8c59357695_5_0.png)

Jeanne Boyarsky

Scott Selikoff

![](img/e0249ee409e157651f035d8c59357695_5_1.png)

献给我的母亲 Dalene，她每天都带给我快乐。

——Jeanne

Scott

![](img/e0249ee409e157651f035d8c59357695_7_0.png)

## 致谢

Jeanne 和 Scott 感谢对本书做出贡献的许多个人。感谢 Kezia Endsley 和 Archana Pragash 引导我们完成这一工作过程并让这本书变得更好。感谢 Janeice DelVecchio 在我们创作本书期间担任我们的编辑。感谢 Elena Fender 担任我们的校对员并发现我们漏掉的错误。这本书的出版离不开 Wiley 的许多人员，包括 Kenyon Brown、Pete Gaughan、Christine O’Connor 以及其他人。

Jeanne 个人特别感谢所有为恢复活动付出精力的人，包括 DevNexus 和 KCDC 领导团队、NYC/Hudson FIRST 委员会，以及创造奇的 Joe Bray。Scott 是一位非常出色的合著者，改进了 Jeanne 写的所有内容。非常感谢 CodeRanch.com 的所有人，他们提出并回答了关于我们书籍的问题。最后，Jeanne 感谢所有的新程序员，以及 FRC 和 FTC 的不断提醒。

没有妻子 Patti 和家人的爱与支持，Scott 无法走到这一步。他想感谢他的两个女儿 Olivia 和 Sophia，以及小女儿 Elysia，感谢他们的耐心和理解，并在“爸爸该去办公室工作了”时给爸爸送上冷咖啡！Scott 想对他在本书创作过程中极具耐心的合著者 Jeanne 表达谢意。他不知道她是如何忍受他的，但他很庆幸她这样做，并对我们制作的书籍质量感到兴奋。最后，Scott 感谢他的母亲 Barbara Selikoff（一位退休教师），她教会了他教育的价值；感谢他的父亲 Mark Selikoff，他灌输了努力工作的好处。

Jeanne 和 Scott 都非常感谢书籍的读者。听到你们这些喜欢这本书并通过考试的人的反馈感觉非常好。我们还感谢那些指出错误并对我们的书籍提出建议的人。Radu Pana 和 Vlad Alin 是第一个发现我们《Java 17 学习指南》中错误的人。

## 关于作者

**Jeanne Boyarsky** 于 2019 年被选为 Java 冠军，是 NYJavaSIG 的领导者。她在纽约市的一家银行担任了 20 多年的 Java 开发人员，在那里负责开发、指导和开展培训。在空余时间，她还是 CodeRanch.com 的高级版主，并负责该论坛的代码库维护。Jeanne 还担任一个 FIRST 机器人小组编程部门的导师，指导学生初学者学习 Java。此外，她每年都会在多个会议上进行演讲。

Jeanne 于 2005 年获得了文学学士学位和计算机信息技术硕士学位。她享受在全职工作的同时通过在线课程获得硕士学位，这在在线教育还不流行的时代是非常领先的！Jeanne 还是一名杰出的演讲力会演讲大师和敏捷大师。你可以在 www.jeanneboyarsky.com 了解关于她的信息，或在 Twitter 上关注她 @JeanneBoyarsky。

**Scott Selikoff** 是一位专业软件开发人员和作者，在全栈数据库驱动系统开发方面拥有超过 20 年的经验。他精通多种软件语言和平台，目前在 Google 担任首席软件工程师，专注于架构和云服务。

Scott 出生于新泽西州的汤姆河，他于 2002 年通过三年的学习，从康奈尔大学获得了数学和计算机科学的文学学士学位。2003 年，他同样在康奈尔大学获得了计算机科学工程硕士学位。作为一名深爱教育的人，Scott 一直喜欢教授新概念。Scott 是 Garden State Java 用户组的领导者，帮助促进社区内的讨论和思想交流。他还在多所大学和会议上授过课。

Scott 住在新泽西州，与他亲爱的妻子 Patti、三个出色的女儿（双胞女 Olivia 和 Sophia 以及小女儿 Elysia）、一只非常活泼的狗 Georgette，以及三只调皮的猫（Snow、Sugar 和 Minnie Mouse）。在空闲时间，他在汤姆河多代际交响乐团演奏小提琴。你可以在 www.linkedin.com/in/selikoff 了解更多关于 Scott 的信息，或在 Twitter 上关注他 @ScottSelikoff。

Jeanne 和 Scott 都是 CodeRanch.com 论坛的版主，欢迎就问题和建议联系他们。他们还在 www.selikoff.net 撰写了名为 Down Home Country Coding 的技术博客。

除了这本书之外，Jeanne 和 Scott 还是八本畅销 Java 书籍的作者：

- OCA: Java 8 Programmer I Study Guide (Sybex, 2015)
- OCP: Java 8 Programmer II Study Guide (Sybex, 2016)
- OCA / OCP Java 8 Practice Tests (Sybex, 2017)
- OCP Java 11 Programmer I Study Guide (Sybex, 2019)
- OCP Java 11 Programmer II Study Guide (Sybex, 2020)
- OCP Java 11 Developer Complete Study Guide (Sybex, 2021)
- OCP Java 11 Practice Tests (Sybex, 2021)
- OCP Java 17 Developer Study Guide (Sybex, 2022)

## 关于技术编辑

Janeice DelVecchio 担任专业软件开发人员已有 12 年，她对编程和计算机有着终生的热情。编辑技术书籍对她来说是一项很有趣的任务，因为她喜欢发现并修复各种类型的缺陷。

在日常工作中，她运用了广泛的技术技能，包括云计算、流程自动化、高级单元测试和 DevOps。她还在 CodeRanch.com 担任志愿者，在那里运营名为“Cattle Drive”的 Java 课程。

她是 Java 编程语言的专家。如果你问她哪种语言最好，她会告诉你语言是工具，要根据你的用例选择最合适的一种。她学习的第一门语言是 BASIC，她希望有一天能学习游戏开发。

在空余时间，她喜欢烹饪、解谜、玩视频游戏和养鸡。她非常喜欢吃寿司、喝精酿啤酒和摸狗——她的特殊爱好是 80 年代的流行音乐。她住在康涅狄格州的利奇菲尔县。

## 关于技术校对

**Elena Felder** 在 Java 语言甚至还没有泛型时就开始接触 Java 开发，她对这种语言、其工具及其社区的持续增长和适应，并成功跟上不断变化的世界感到非常高兴。她曾出于兴趣为 Jeanne 和 Scott 的首批 *Java 8 Certification Study Guide* 章节之一进行了校对，从那时就开始专业地从事这项工作。

## 引言

《OCP Oracle Certified Professional Java SE 17 Developer Practice Tests》旨在帮助想要通过 1Z0-829 考试成为 Java 17 Oracle 认证专业人员 (OCP) 的人员，以及想要测试自己 Java 17 知识的人。如果你是 Java 17 的新手，我们强烈建议你先从学习指南开始，学习语言的所有方面，一旦考虑参加考试，再回来这本书。

我们建议从畅销的《OCP Oracle Certified Professional Java SE 17 Developer Study Guide: Exam 1Z0-829》(Sybex, 2022)（这本书恰好由我们编写）开始学习。与我们学习指南中设计得比实际更简单的题目不同，这本书中的题目会告诉你正确答案的数量。如果有多个正确答案，题目会显示为“选择两个”或“选择三个”。

无论你使用哪种学习指南进行准备，都可以通过这本书来磨练技能，因为它是基于实际考试题目的。

## 理解考试

归结底，考试就是一份题目列表。你对考试结构越了解，表现就可能越好。例如，知道考试包含多少题可以帮助你管理进度和剩余时间。表 I.1 描述了考试的整体结构。

| 考试代码 | 1Z0-829 |
| :--- | :--- |
| 时间限制 | 90 分钟 |
| 题目数量 | 50 题 |
| 及格分数 | 68% |

对于数学好的人来说，这意味着你需要在 50 道题中正确回答大约 34 道才能通过。我们之所以说“大约”，是因为 Oracle 可能会包含用于测试的题目，这些题目是不计分的。

如果 Oracle 更改此内容或对 1Z0-829 考试有任何调整，我们建议查看我们的博客。

尽管如此，这本书的章节是围绕 Oracle 的目标组织的，以便你可以测试自己的技能。虽然在使用本书中这种基于目标的章节之前，你不需要阅读整本学习指南，但你确实需要学习相关的目标。

表格 L.2 显示了在练习本书中的问题之前，你至少需要在 Java 17 学习指南中阅读的哪些章节。

| 本书章节 | 目标 | 学习指南章节 |
|---|---|---|
| 1 | 处理日期、时间、文本、数值和布尔值 | 1, 2, 4 |
| 2 | 控制程序流 | 3 |
| 3 | 利用 Java 面对象方法 | 1, 3, 5, 6, 8 |
| 4 | 处理异常 | 11 |
| 5 | 使用数组和集合 | 4, 9 |
| 6 | 使用流和 Lambda 表达式 | 10, 13 |
| 7 | Java 代码的打包与部署以及使用 Java 平台模块系统 | 12 |
| 8 | 管理并发代码执行 | 13 |
| 9 | 使用 Java I/O API | 14 |
| 10 | 使用 JDBC 访问数据库 | 15 |
| 11 | 实现本地化 | 11 |

我们的一些章节包含很多问题。例如，第 3 章包含 200 多个问题。这是基于 Oracle 选择组织其目标的方式。我们建议每批完成 30–50 题来处理这些较大的章节。这样，你就可以在做更多题之前强化你的学习效果。这也能让你练习一组更接近考试长度的题集。

## 参加模拟考试

本书的第 12、13 和 14 章包含三份全长度的模拟考试卷。这些章节中的问题与基于目标的章节在许多方面都不同。这些模拟考试题通常更难，因为它们的设计目的是测试你的累积知识，而不是强化现有的技能。换句话说，你可能会遇到一个同时测试两个离散主题的问题。

与目标章节一样，我们在模拟考试章节中明确指出了正确答案的数量，就像在真实考试中那样。两个模拟考试章节都设计为 90 分钟内完成，及格分数为 68%。这意味着你需要至少正确回答 34 个问题。记住，在感到准备就绪之前不要参加模拟考试。模拟考试次数是有限的，所以你不想浪费新鲜的尝试机会。

虽然一个基于目标的章节可以在几天内完成，但每个模拟考试章节都设计为一次性完成。你应该尽力模拟考试的体验。这意味着留出 90 分钟，拿上一块白板或草稿纸，即使你不确定答案，也要回答每一个问题。记住，猜答案没有惩罚，你排除的错误答案越多，就越好。

## 审阅考试变更

Oracle 会经常更改题目数量、及格分和时间限制。Jeanne 和 Scott 维护着博客，跟踪真实考试的更新，速度与 Oracle 更新的速度同步。

www.selikoff.net/ocp17-pt

我们建议你在参加真实考试之前阅读此页面，以防自本书出版以来任何信息发生了变化。虽然不常见，但 Oracle 确实会添加、删除或重做目标。当这种情况发生时，我们会在网站上以博客文章的形式提供免费补充材料。

## 需要更多准备帮助吗？

两位作者都是 CodeRanch.com 的版主。该网站是一个很大且活跃的编程论坛，对 Java 初学者非常友好。它有一个专门针对此考试的论坛叫做 Programmer Certification。

www.coderanch.com/f/24

在阅读本书时，随时可以在上述任何一个论坛中提问。你可能遇到了编译类的困难，或者只是对某些事情感到困惑。你将获得来自丰富的 Java 程序员的解答。那甚至可能是我们的一员！

在我们的 Telegram 频道获取更多 Java 书籍：https://t.me/javalib

## 额外内容

本书有一个网页，使用 Wiley 的交互式在线测试引擎提供书中所有的问题。

![](img/e0249ee409e157651f035d8c59357695_22_0.png)

与所有考试一样，Oracle 的 Java 17 Oracle 专业人员 (OCP) 认证会定期更新，并最终可能被淘汰或取代。在某个时刻，当 Oracle 不再提供此考试时，我们的书籍和在线工具也将被淘汰。如果你在考试淘汰后购买了本书，或者在考试淘汰后尝试在 Sybex 在线学习环境中注册，请知晓我们不保证一旦考试淘汰，考试的在线 Sybex 工具仍然可用。

如果你认为书中存在错误，请向我们的客户团队反映。我们尽力提供准确的内容，但即使如此也可能出现错误。请邮件至 support

OCP 考试涵盖的主题：

- 处理日期、时间、文本、数值和布尔值
- 使用 Java 平台模块系统
- Java 代码的打包与部署
- 管理并发代码执行
- 使用流和 Lambda 表达式
- 使用数组和集合
- 利用 Java 面对象方法
- 控制程序流
- 处理异常
- 使用 Java I/O API
- 使用 JDBC 访问数据库
- 实现本地化

我们的一些章节包含很多问题。例如，第 3 章包含 200 多个问题。这是基于 Oracle 选择组织其目标的方式。我们建议每批完成 30–50 题来处理这些较大的章节。这样，你就可以在做更多题之前强化你的学习效果。这也能让你练习一组更接近考试长度的题集。

## 1. 哪些不是变量名？

A.

B.

C.

D.

## 2. 哪些是？

A.

B.

C.

D.

## 3. 哪些是有效的？

A.

B.

C.

D.

## 4. 哪个类有 `getSeconds()` 方法？

A.

B.

C.

D.

## 5. 以下代码输出什么？

```java
int meal = 5;
int tip = 2;
var total = meal>6 ? tip++ : tip--;
```

## 6. 执行上述代码后 `tip` 的值是多少？

A. 1

B. 2

C. 3

D. 7

E. 以上均非

## 7. 以下代码输出什么？

```java
int year = 1874;
int month = Month.MARCH;
int day = 24;
LocalDate date = LocalDate.of(year, month, day);
System.out.println(date.isBefore(LocalDate.now()));
```

A. false

B. true

C. 代码无法编译。

D. 代码编译但在运行时抛出异常。

## 8. 以下代码的输出是什么？

```java
var b = "12";
b += "3";
b.reverse();
System.out.println(b.toString());
```

A. 12

B. 21

C. 123

D. 321

E. 代码无法编译。

## 9. 以下代码的输出是什么？

```java
var line = new StringBuilder("-");
```

A. false 1

B. false 2

C. true 1

D. true 2

E. 它无法编译。

## 10. 于夏令时间从 2022 年 3 月 13 日凌晨 2 点开始，时钟从凌晨 1:59 跳到凌晨 03:00，以下哪项可以填充空白使得代码不抛出异常？

```java
var localDate = LocalDate.of(2022, 3, 13);
var localTime = LocalTime.of(_______);
var zone = ZoneId.of("America/New_York");
var z = ZonedDateTime.of(localDate, localTime, zone);
```

A. 2, 0

B. 3, 0

C. 以上任一均可运行而不抛出异常。

D. 这两项都会导致抛出异常。

## 11. 关于此文本块，哪个描述是正确的？

```java
var block = """

green
yellow
"""
```

- A. 只有实质性空白（essential whitespace）。
- B. 只有偶然空白（incidental whitespace）。
- C. 既有实质性空白也有偶然空白。
- D. 代码无法编译。

## 12. `cat`、`moose` 和 `penguin` 的返回类型分别是什么？
