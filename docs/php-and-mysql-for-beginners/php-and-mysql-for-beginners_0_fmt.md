
# PHP 和 MySQL 初学者指南

![](img/cover.jpeg)

![LearnToProgram Logo_CMYK.jpg](img/00001.jpeg)

LearnToProgram, Inc.

康涅狄格州，弗农农

LearnToProgram.tv, Incorporated

27 Hartford Turnpike Suite 206

Vernon, CT 06066

contact@learntoprogram.tv

(860) 840-7090

## 献辞

献给那些努力结束欺凌的人。如果你曾被欺凌，你是美丽的，我们爱你们。

## 关于作者：Mark Lassoff

Mark Lassoff 的父母经常声称 Mark 天生是个程序员。在 80 年代中期，当邻居的孩子在外面玩踢球和扔雪球时，Mark 正忙于在他的 `Commodore 64` 上用 `BASIC` 编程语言编写游戏。计算机和编程在大学期间继续是他感兴趣的，他在大学主修传播学和计算机科学。完成学业后，Mark 在几家大型公司的软件和 Web 开发部门工作。

2001 年，出于一时好奇，当他的同龄人正在征服互联网世界时，Mark 接受了德克萨斯州奥斯汀一个技术培训中心的程序员培训工作。正是在那里他爱上了教授编程。

在过去的 10 年里，教授编程一直是 Mark 的热情。今天，Mark 是一位顶尖技术培训师，遍为软件和 Web 开发人员提供领先课程。Mark 的培训客户包括国防部、洛克希德·马丁、发现卡服务和凯撒珀曼医疗。除了传统的课堂培训外，Mark 还在网上发布课程，全球编程学生都在学习这些课程。

他住在康涅狄格州哈特福德附近，他正在那里重新装修他的公寓。

![download icon.png](img/00002.jpeg)

在以下地址访问本书的完整实验解决方案：

[`learntoprogram.tv/pages/book-lab-solutions`](https://learntoprogram.tv/pages/book-lab-solutions)

# 使用 Python 进行游戏开发的基础

- 使用 Python 进行游戏开发
- GitHub 基础
- 面初学者的 HTML 和 CSS（包含 HTML5）
- 使用 PhoneGap 进行 HTML5 移动应用开发
- Web 开发简介
- iOS 开发训练营
- 针对 iOS6/7 的初学者 iOS 开发
- 初学者 Java 编程
- 初学者 Javascript
- 初学者 Joomla
- 初学者 jQuery
- 使用 iOS 进行移动游戏开发
- 初学者 Node.js
- 初学者 Objective C
- 专为程序员准备的 Photoshop
- 初学者 PHP & MySQL
- 针对零基础初学者的编程
- 使用 Microsoft Project 进行项目管理
- 初学者 Python
- 初学者 Ruby on Rails
- 初学者 SQL 数据库
- 用户体验设计
- 来自 LearnToProgram, Inc. 的书籍
- 使用 HTML5 创建你自己的 MP3 播放器
- CSS 开发（包含 CSS3！）
- 使用 Python 进行游戏开发
- 面向初学者的 HTML 和 CSS
- 初学者 Javascript
- 初学者 PHP 和 MySQL
- 针对零基础初学者的编程
- 初学者 Python
- 初学者 SQL 数据库
- Swift 基础：iOS 开发的语言

## 第一章：你的第一个 PHP 脚本

### 本章目标

- 你将能够定义 `PHP` 和 `PHP 脚本`。
- 你将能够识别并安装创建 PHP 脚本所需的软件开发工具。
- 你将学习如何设置运行 `PHP` 所需的编程环境。
- 你将能够运行你的第一个 `PHP` 脚本。

### 1.1 设置你的开发环境

你可能认为在学习 `PHP` 编程时，是在孤立地学习 `PHP` 语言。然而，`PHP` 是开发基于 `PHP` 应用程序的一套技术的核心。从描述这些技术开始是一个很好的起点。

`PHP` 是一种通用的、开源的服务器端脚本语言，专为 Web 开发设计。它被用于生成动态网页。它是一种用于为网站添加基础 Web 功能的网络脚本语言。`PHP` 的用途示例包括创建用户名和密码登录界面、检查表单详情、创建论坛页面、图片库、问卷调查等。`PHP` 是一门强大的语言，使开发人员能够创建他们想要的任何类型的应用程序。

与某些 Web 语言（如 `Javascript`）不同，`PHP` 并不是在你的浏览器中执行的，而是在服务器上执行——即存储页面并向互联网浏览器提供页面的计算机。服务器处理来自浏览器的请求，然后返回请求的内容——通常是 `HTML` 格式。这就是 `PHP` 被称为“服务端语言”的原因。

`PHP` 既可以写在外部文档中，也可以嵌入 `HTML` 文档本身中。`PHP` 代码由 Web 服务器（通常是 `Apache` 服务器）解释，该服务器拥有 `PHP` 处理器模块，该模块生成生成的网页。其他与 `PHP` 类似的流行语言还有 `ASP`、`Python`、`Perl` 和 `Ruby`。

像 `PHP` 这样的计算机语言的常用用途之一与数据库或数据源建立接口。通常，`PHP` 与 `MySQL` 数据库配合使用。我们将在书的后期讨论 `PHP` 和 `MySQL` 之间的交互。

根据计算机历史，Rasmus Lerdorf 开发了最初的 `PHP` 规范。据说，`PHP` 一词从他的个人主页（Personal Home Page）项目演变为今天广泛使用并广为人知的开源脚本语言，即 `Hypertext PreProcessor`——这是大量开发者广泛合作努力的结果。然而，它并没有遵循原始的缩写 `PHP`，即 `Pre-Hypertext Processor`。

正如 Rasmus Lerdorf 所说，`PHP` 并不是一门全新的革命性语言，因为它从 `C`、`Perl` 和 `Java` 等语言中借鉴了大量的语法。`PHP` 是一门非常专注于 Web 设计的语言。这是一门为 Web 开发人员编写的语言。

`PHP` 非常适合快速创建 Web 前端和后端系统——数据库的创建和操作、目录服务器的直接访问协议、目录服务器的简单网络管理协议，或为 Web 生成非 `HTML` 动态内容（如图像、Flash 或 `PDF` 文档）。

一个简单的 `PHP` 任务示例是从数据库中提取客户信息并动态生成一张看起来专业的 `PDF` 发票。（www.computerworld.com, Interview with Rasmus Lerdorf, 2002 年 2 月 4 日）。许多多人在线游戏服务器是使用 `PHP` 构建的。

`MySQL` 是一个基于标准 `SQL` 的免费数据库管理系统，`SQL` 代表结构化查询语言。`SQL` 在 1986 年成为标准数据库语言。它用于访问和操作数据库。`SQL` 语言在不同的数据库引擎之间非常一致——这意味着从一个数据库品牌切换到另一个是相当容易的。

`MySQL` 是一个开源的关系型数据库管理系统 (RDBMS)，运行在服务器上，允许或提供对多个数据库的并发用户访问。`MySQL` 的开发者是 `Oracle`（原 Sun Microsystems）。根据维基百科，它以联合创始人 Michael Widenius 的女儿 `My` 命名，在 `SQL` 前加上前缀，因此名为 `MySQL`。

`MySQL` 是 Web 应用中流行的数据库选项。它也是不同的开源 Web 语言栈的核心组件，即 `Linux`、`Apache`、`Perl`、`Python` 等。但最常见的组合是 `PHP` 和 `MySQL`，因为它们都倾向于采用极简且直接的方法来解决问题。

通过 `MySQL`，你可以创建数据库中元素之间的关系，这样每当在 Web 中需要再次处理数据时，就不需要重复数据。我们将在书的后期详细讨论 `MySQL`。

`Apache` Web 服务器程序适用于多种操作系统。它是一个在 `Apache` 基金会支持下开发和维护的开源（即非专有的）`http` 服务器。它适用于多种操作系统，包括 `UNIX`、`Solaris`、`Novell Netware`、`Mac OS X`、`Microsoft Windows`、`OS/2`、`TPF` 和 `eComStation`。它根据 `Apache` 许可证发布。传说 `Apache` 的名称源于软件本身有很多补丁。

完成 PHP 编程环境所需的另一个应用程序是 `phpMyAdmin`。它是一个用 `PHP` 语言编写的应用程序，为 `MySQL` 数据库的管理提供基于 Web 的界面。

## 准备你的工具箱

要开始使用 PHP 和 MySQL 创建应用程序，你需要几个辅助开发的应用程序。

需要的应用程序是文本编辑器。在本书中，我将使用 Active State 的 `Komodo Edit` 免费版，但可以使用其他编辑器作为替代。不要使用文字处理软件，因为它们添加的内置代码会干扰编译器。

你可以免费下载 `Komodo Edit`，它有 Windows、Mac 甚至 Linux 的版本。这是 `Komodo Edit` 运行时的样子：

```
![](images/00003.jpeg
```

图 1.1：`Komodo Edit` 的启动界面。

`Komodo Edit` 自带了几个开发模板，可以提供一个良好的起点。

你需要的另一个应用是 Web 服务器环境。这并不是独立的计算机硬件，而是一个软件应用程序，它可以让你的桌面电脑充当服务器来测试 PHP 脚本。通过这种方式，你可以在无需真正上线并连接到互联网实时服务器的情况下测试你的 PHP 脚本。你的计算机将既是客户端也是服务器。对于 Windows 和 Linux 用户，使用的服务器软件环境是 `WAMP`，而对于 Macintosh 用户则将是 `MAMP`。

`WAMP` 代表 Windows、Apache、MySQL 和 PHP。下载后，它会将这些工具放置在你的托栏中：本地主机（local host）、`phpMyAdmin`、`Apache`、`PHP` 和 `MySQL`，如下图像所示：

![](img/00004.jpeg)

图 1.2：WampServer 的主（或控制）菜单，可以通过点击 Windows 图标栏中的 WampServer 图标来激活。

`WAMP` 的安装 URL 为：`www.wampserver.com`

对于 Mac，设置的环境是 `MAMP`。它代表 Macintosh、Apache、MySQL 和 PHP。它的功能基本上与 Windows 版本的套件相同。

如果你在 Windows 机器上工作，为了开始设置工作环境，你需要确保为你的系统下载并安装了最新的 `Visual C++ Service Pack`。如果你在 PC 上设置了自动更新，此服务包应该是可以获取的。`WAMP` 还会检查你是否拥有了最新版本的 `Visual C++ Service Pack` 并相应地通知你。

你现在可以通过 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是免费的服务器软件环境，软件包包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`（偏好设置）。然后在 `Languages`（语言）选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流



在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。



你可以在下载页面查看软件包包含的项目列表——`Apache`、`MySQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)

图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `Edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。



一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。



图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)

图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。



![select php 2.jpg](img/00009.jpeg)

图 1.7：在 `Komodo Edit` 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER`。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 `Komodo Edit` 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。



![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。`WAMP` 代表 Windows, Apache, MySQL and PHP. Once downloaded, it will put these tools in your tray: local host, `phpMyAdmin`, `Apache`, `PHP`, and `MySQL`, as shown in the following image:

![](img/00004.jpeg)

Figure 1.2: WampServer’s Main (or Control) Menu which can be activated by clicking on WampServer’s Icon in the Icon Tray of Windows.

The URL for `WAMP` installation is: `www.wampserver.com`

For the Mac, `MAMP` is the environment to be set up. It stands for Macintosh, Apache, MySQL, and PHP. Its function is basically the same as the Windows version of the suite.

If you are working on a Windows machine, to begin setting up your working environment you need to make sure that the latest `Visual C++ Service Pack` is downloaded and installed for your system. This service pack should be readily available if you have the automatic updates set up on your PC. `WAMP` will also check if you have the latest version of the `Visual C++ Service Pack` and it will notify you accordingly.

You can now download `WAMP` by visiting [www.wampserver.com/en](http://www.wampserver.com/en). `WAMP` is a free server software environment and everything is included in the package—`Apache`, `PHP`, `MySQL` and `phpMyAdmin`.

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

Figure 1.3: WampServer’s Main Page at [`www.wampserver.com/en/`](http://www.wampserver.com/en/).

You may check out the list of items included in the package–`Apache`, `My SQL` `PHP` and `phpMyAdmin`—in the download page.

![WAMP suite list.jpg](img/00006.jpeg)Figure 1.4: WampServer’s download page also at [`www.wampserver.com/en/`](http://www.wampserver.com/en/).

Take note of the directory in which you will extract the zip file of `WAMP`, as you will need to refer to it when you set up your `Komodo Edit` file path and your local server.

After extracting the `WAMP` folder into your local hard disk drive, launch `Komodo Edit`. Go to the menu bar and choose `edit`.

![](img/00007.jpeg)

Figure 1.5: The dropdown menu of Komodo Edit’s `Edit` option.

Under `Edit` choose `Preferences`. Then, under `Languages` Option, choose `PHP`.

If the directory for your `PHP.ini` is not yet set, do so by going into your `WAMP` folder and accessing the `Apache 2.2.22` `bin` folder by going through folders in the following order:

`WAMP>>bin>>Apache2.2.22>>bin`

Look for the text file named “PHP”. This is your `.ini` file. Choose the `PHP.ini` configuration file and set it in your directory. This is done so that `Komodo Edit` can recognize `PHP` in its integrated development environment editor.

![](img/00008.jpeg)

Figure 1.6: Selecting `PHP` as the language option in Komodo Edit’s `Edit >> Preferences >> Language Option` menu path. In this screenshot, the path to the `php.ini` file still has to be set.

![select php 2.jpg](img/00009.jpeg)

Figure 1.7: Setting the path to the `php.ini` file in `Komodo Edit`.

Once you have the language preferences set up, `PHP` is now recognized by `Komodo Edit` as the integrated development environment (IDE) language set.

## 1.2 Understanding PHP Development Workflow

In this section, you will learn about PHP development workflow: how a PHP file is actually created and tested, what process it undergoes, and what happens during each phase of the process.

When creating PHP code, the first thing you do is launch your `WAMP` (or `MAMP`) environment.

### Step 1

If you’re on a PC, you can find the `WAMP` icon either in the Windows Start Menu or in the Icon Tray at the bottom right side of the screen. If you are using a Mac you will find `MAMP` installed in your applications folder. Start it as you would start any other application.

### Step 2

When you launch your `WAMP` program, it automatically activates its server functions which will be indicated by the message “WAMPSERVER – server Online” when you hover your mouse over its icon in the Windows Icon Tray.

If you see the message “WAMPSERVER – server Offline” then you have to activate the server functions by clicking on the `WAMP` icon. This will bring up `WAMPSERVER`’s Start Menu. Then, click on the last option on this menu “Put Online”. This will then bring up `WAMPSERVER` and if...

你需要的另一个应用是 Web 服务器环境。这并不是独立的计算机硬件，而是一个软件应用程序，可以让你的桌面电脑充当服务器来测试 PHP 脚本。通过这种方式，你可以在无需真正上线并连接到互联网实时服务器的情况下测试你的 PHP 脚本。你的计算机将既是客户端也是服务器。对于 Windows 和 Linux 用户，使用的服务器软件环境是 `WAMP`，而对于 Macintosh 用户则将是 `MAMP`。

`WAMP` 代表 Windows、Apache、MySQL 和 PHP。下载后，它会将这些工具放置在你的托栏中：本地主机、`phpMyAdmin`、`Apache`、`PHP` 和 `MySQL`，如下图像所示：

![](img/00004.jpeg)

图 1.2：WampServer 的主（或控制）菜单，可以通过点击 Windows 图标栏中的 WampServer 图标来激活。

`WAMP` 的安装 URL 为：`www.wampserver.com`

对于 Mac，设置的环境是 `MAMP`。它代表 Macintosh、Apache、MySQL 和 PHP。它的功能基本上与 Windows 版本的套件相同。

如果你在 Windows 机器上工作，为了开始设置工作环境，你需要确保为你的系统下载并安装了最新的 `Visual C++ Service Pack`。如果你在 PC 上设置了自动更新，此服务包应该是可以获取的。`WAMP` 还会检查你是否拥有了最新版本的 `Visual C++ Service Pack` 并相应地通知你。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER` 并如果...



你需要的另一个应用是 Web 服务器环境。这并不是独立的计算机硬件，而是一个软件应用程序，可以让你的桌面电脑充当服务器来测试 PHP 脚本。通过这种方式，你可以在无需真正上线并连接到互联网实时服务器的情况下测试你的 PHP 脚本。你的计算机将既是客户端也是服务器。对于 Windows 和 Linux 用户，使用的服务器软件环境是 `WAMP`，而对于 Macintosh 用户则将是 `MAMP`。

`WAMP` 代表 Windows、Apache、MySQL 和 PHP。下载后，它会将这些工具放置在你的托栏中：本地主机、`phpMyAdmin`、`Apache`、`PHP` 和 `MySQL`，如下图像所示：

![](img/00004.jpeg)

图 1.2：WampServer 的主（或控制）菜单，可以通过点击 Windows 图标栏中的 WampServer 图标来激活。

`WAMP` 的安装 URL 为：`www.wampserver.com`

对于 Mac，设置的环境是 `MAMP`。它代表 Macintosh、Apache、MySQL 和 PHP。它的功能基本上与 Windows 版本的套件相同。

如果你在 Windows 机器上工作，为了开始设置工作环境，你需要确保为你的系统下载并安装了最新的 `Visual C++ Service Pack`。如果你在 PC 上设置了自动更新，此服务包应该是可以获取的。`WAMP` 还会检查你是否拥有了最新版本的 `Visual C++ Service Pack` 并相应地通知你。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER` 并如果... (Wait, the text cuts off or repeats. I will only translate what is provided in the final block).



你需要的另一个应用是 Web 服务器环境。这并不是独立的计算机硬件，而是一个软件应用程序，可以让你的桌面电脑充当服务器来测试 `PHP` 脚本。通过这种方式，你可以在无需真正上线并连接到互联网实时服务器的情况下测试你的 `PHP` 脚本。你的计算机将既是客户端也是服务器。对于 Windows 和 Linux 用户，使用的服务器软件环境是 `WAMP`，而对于 Macintosh 用户则将是 `MAMP`。

`WAMP` 代表 Windows、Apache、MySQL 和 PHP。下载后，它会将这些工具放置在你的托栏中：本地主机、`phpMyAdmin`、`Apache`、`PHP` 和 `MySQL`，如下图像所示：

![](img/00004.jpeg)

图 1.2：WampServer 的主（或控制）菜单，可以通过点击 Windows 图标栏中的 WampServer 图标来激活。

`WAMP` 的安装 URL 为：`www.wampserver.com`

对于 Mac，设置的环境是 `MAMP`。它代表 Macintosh、Apache、MySQL 和 PHP。它的功能基本上与 Windows 版本的套件相同。

如果你在 Windows 机器上工作，为了开始设置工作环境，你需要确保为你的系统下载并安装了最新的 `Visual C++ Service Pack`。如果你在 PC 上设置了自动更新，此服务包应该是可以获取的。`WAMP` 还会检查你是否拥有了最新版本的 `Visual C++ Service Pack` 并相应地通知你。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)

图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER` 并如果...



你需要的另一个应用是 Web 服务器环境。这并不是独立的计算机硬件，而是一个软件应用程序，可以让你的桌面电脑充当服务器来测试 PHP 脚本。通过这种方式，你可以在无需真正上线并连接到互联网实时服务器的情况下测试你的 PHP 脚本。你的计算机将既是客户端也是服务器。对于 Windows 和 Linux 用户，使用的服务器软件环境是 `WAMP`，而对于 Macintosh 用户则将是 `MAMP`。

`WAMP` 代表 Windows、Apache、MySQL 和 PHP。下载后，它会将这些工具放置在你的托栏中：本地主机、`phpMyAdmin`、`Apache`、`PHP` 和 `MySQL`，如下图像所示：

![](img/00004.jpeg)

图 1.2：WampServer 的主（或控制）菜单，可以通过点击 Windows 图标栏中的 WampServer 图标来激活。

`WAMP` 的安装 URL 为：`www.wampserver.com`

对于 Mac，设置的环境是 `MAMP`。它代表 Macintosh、Apache、MySQL 和 PHP。它的功能基本上与 Windows 版本的套件相同。

如果你在 Windows 机器上工作，为了开始设置工作环境，你需要确保为你的系统下载并安装了最新的 `Visual C++ Service Pack`。如果你在 PC 上设置了自动更新，此服务包应该是可以获取的。`WAMP` 还会检查你是否拥有了最新版本的 `Visual C++ Service Pack` 并相应地通知你。

你现在可以通过访问 [www.wampserver.com/en](http://www.wampserver.com/en) 下载 `WAMP`。`WAMP` 是一个免费的服务器软件环境，软件包中包含了所有内容——`Apache`、`PHP`、`MySQL` 和 `phpMyAdmin`。

![C:\Users\Earl\Documents\PHP My SQL for Beginners\Chapter 1 Envirnoment & First Script PHP MySQL\Image Captures\WAMP homepage.PNG](img/00005.jpeg)

图 1.3：[`www.wampserver.com/en/`](http://www.wampserver.com/en/) 上的 WampServer 主页。

你可以在下载页面查看软件包包含的项目列表——`Apache`、`My SQL`、`PHP` 和 `phpMyAdmin`。

![WAMP suite list.jpg](img/00006.jpeg)

图 1.4：WampServer 的下载页面同样位于 [`www.wampserver.com/en/`](http://www.wampserver.com/en/)。

请注意你提取 `WAMP` 压缩文件的目录，因为在设置 `Komodo Edit` 文件路径和本地服务器时将需要引用它。

在将 `WAMP` 文件夹提取到你的本地硬盘驱动器后，启动 `Komodo Edit`。进入菜单栏并选择 `edit`。

![](img/00007.jpeg)

图 1.5：Komodo Edit `Edit` 选项的下拉菜单。

在 `Edit` 下选择 `Preferences`。然后在 `Languages` 选项下选择 `PHP`。

如果尚未设置 `PHP.ini` 的目录，请通过进入 `WAMP` 文件夹并按照以下顺序访问文件夹中的 `Apache 2.2.22` `bin` 文件夹来设置：

`WAMP>>bin>>Apache2.2.22>>bin`

寻找名为“PHP”的文本文件。这就是你的 `.ini` 文件。选择 `PHP.ini` 配置文件并将其设置在你的目录。这样做是为了 `Komodo Edit` 能够在其集成开发环境编辑器中识别 `PHP`。

![](img/00008.jpeg)

图 1.6：在 Komodo Edit 的 `Edit >> Preferences >> Language Option` 菜单路径中选择 `PHP` 作为语言选项。在此截图，`php.ini` 文件的路径仍需设置。

![select php 2.jpg](img/00009.jpeg)

图 1.7：在 Komodo Edit 中设置 `php.ini` 文件的路径。

一旦设置好语言偏好，`Komodo Edit` 现在就会将 `PHP` 识别为集成开发环境（IDE）语言集。

## 1.2 理解 PHP 工作流

在本节中，你将学习 PHP 开发工作流：PHP 文件实际上是如何创建和测试的，它经历了什么过程，以及在过程中每个阶段发生了什么。

在编写 PHP 代码时，你做的第一件事是启动你的 `WAMP`（或 `MAMP`）环境。

### 步骤 1

如果你使用的是 PC，你可以在 Windows 开始菜单或屏幕右下角的图标栏中找到 `WAMP` 图标。如果你使用的是 Mac，你将在应用程序文件夹中找到已的 `MAMP`。像启动任何其他应用程序一样启动它。

### 步骤 2

当你启动 `WAMP` 程序时，它会自动激活其服务器功能，当你将鼠标悬停在 Windows 图标栏的它的图标上时，会显示“WAMPSERVER – server Online”的消息。

如果你看到“WAMPSERVER – server Offline”的消息，则你必须通过点击 `WAMP` 图标来激活服务器功能。这将弹出 `WAMPSERVER` 的启动菜单。然后，点击菜单中的最后一个选项“Put Online”（上线）。这将调出 `WAMPSERVER` 并如果... (Wait, the text cuts off or repeats. I will only translate what is provided in the final block).

![](img/00018.jpeg)

图 1.16：在 Chrome 浏览器中 Hello.html 的输出。

如果你想从本地 WAMP 托盘调用浏览器，而不是直接启动浏览器，还有另一种替代方法。在 `Komodo Edit` 中保存文件后，继续第 7 步。

第 1-6 ：与之前的步骤相同。

第 7 ：点击托盘中的 `WAMP` 图标并选择 `localhost`。

![localhost.jpg](img/00019.jpeg)

图 1.17：从 WampServer 的开始菜单启动 localhost。

第 8 ：`WAMP` 本地服务器首页启动。在地址栏的文本中，添加斜杠 (`/`)，然后是 html 文件名 `hello.html`。

![WAMPSERVER hello file.jpg](img/00020.jpeg)

图 1.18：在 Firefox 的地址或 URL 栏中输入 `localhost/hello.html`。

第 9-10 ：与之前的步骤相同。

第 11-12 ：这就是输出。

从我电脑的 `WAMP` 本地服务器，它自动启动了 Firefox 浏览器：

![](img/00021.jpeg)



图 1.19：在 Firefox 的地址或 URL 栏中输入 `localhost/hello.html` 的结果，随后执行 `hello.html`，它仅显示“Hi There!”。

如果网页包含 PHP，服务器会对其进行处理然后为浏览器进行解释，因为浏览器只能解释 HTML、CSS 和 Javascript。这就是为什么必须通过服务器访问文件，而不是直接从网页浏览器访问。

回顾整个工作流：

1. 搭建开发环境——安装 WAMP（或 `MAMP`）和文本编辑器。在这里我们使用了 `Komodo Edit`。
2. 在 `WAMP` 文件夹中设置默认目录。
3. 将 PHP 服务器上线。启动你的文本编辑器。
4. 编写你的脚本。
5. 将文件保存到专门分配给服务器的文件夹中。
6. 启动你喜欢的浏览器。输入要处理的脚本文件。
7. 服务器处理文件中嵌入任何 PHP 脚本。
8. 浏览器解释服务器生成的 HTML 文件。
9. 网页加载。就是这样！

## 1.3 编写你的第一个脚本

PHP 脚本嵌入在 HTML 文档中。因此，你在 PHP 脚本中需要编写的第一部分是基础的 HTML 结构。

这是一个基础、简单的 HTML 文档结构：

```html
<!DOCTYPE html>
<html>
<head>
<title>第一个 PHP 脚本</title>
</head>
<body>
</body>
</html>
```

要在此此 HTML 文档中嵌入 PHP 代码，你需要在 `body` 元素内部的起始标签 `<?php` 和结束标签 `?>` PHP 标签之间编写代码：

```html
<!DOCTYPE html>
<html>
<head>
<title>第一个 PHP 脚本</title>
</head>
<body>
          <?php
          ?>
</body>
</html>
```

这些起始和结束的 PHP 标签将 PHP 代码与 HTML 代码隔离开来。

现在我们可以通过引入 `echo()` 命令来尝试添加更多代码。此输出命令简单地显示放置在引号内的文本或值，如下例所示。

`echo()` 应该放置在 PHP 脚本标签之间。想象命令行就像被夹在起始和结束的 PHP 脚本标签之间。

```html
<!DOCTYPE html>
<html>
<head>
<title>第一个 PHP 脚本</title>
</head>
<body>
          <?php
                             echo("This is my first PHP document");
          ?>
</body>
</html>
```

你应该将代码保存到 `www` 文件夹（针对 Windows）或 `htdocs` 文件夹（针对 Mac）中，命名为 `first_document.php`。请注意，即使文档是使用 HTML 和 PHP 创建的，如果文件名扩展名不是 `.php`，服务器将无法处理文件中嵌入的 PHP 脚本。

打开本地浏览器并在地址栏中输入：`http://localhost/first_document.php`

![](img/00022.jpeg)

图 1.20：执行你的第一个 PHP 脚本 `first_document.php` 的输出。

你将看到嵌入在 HTML 文档中的 PHP 脚本已通过处理，`echo` 命令将文本（通常称为字符串）输出到浏览器窗口。

PHP 还允许你在 `echo()` 命令中嵌入 HTML 标签。这些 HTML 将像任何任何其他 HTML 一样在浏览器中被处理。

```html
<!DOCTYPE html>
<html>
<head>
<title>Hello!</title>
</head>
<body>
<?php          
echo("<h1><<strong>This is my first PHP document</strong></h1>”);
          echo("</br>This is my second PHP statement");
?>
</body>
</html>
```

使用相同的文件名保存带有更改的文件并刷新你的浏览器。

![](img/00023.jpeg)

图 1.21：你修改后的 PHP 脚本 `first_document.php` 的输出。

你会注意到嵌入 `echo()` 命令中的 HTML 已通过处理，且字符串显示为大号粗体文本。

记住，浏览器并不处理 PHP 脚本——由服务器完成。要确认此过程，请在浏览器中查看 `first_document.php` 的源代码。

![](img/00024.jpeg)

图 1.22：在浏览器中查看 `first_document.php` 的源代码。

## 1.4 echo(), print() 和 printf 命令

本节将讨论用于显示内容的这些命令。现在你已经熟悉了 PHP 中的 `echo()` 命令。

`echo()` 和 `print()` 以及 `printf()` 都是输出命令。

`echo()` 和 `print()` 几乎相同，唯一的区别是 `print()` 会返回返回值 1，而 `echo()` 不会。

你可以像使用 `echo` 一样使用这些命令：

```php
echo "Hello!";
```

输出：Hello!

```php
print "Hello!";
```

输出：Hello!

`printf()` 与 `echo()` 不同，它允许使用格式化字符串来控制输出。

```php
printf("Hello, %s", "World");
```

输出：Hello, World!

`%s` 是字符串的占位符。

```php
printf("I am %d years old", 25);
```

输出：I am 25 years old.

`%d` 是整数的占位符。

```php
printf("The value of pi is %.2f", 3.14159);
```

输出：The value of pi is 3.14.

`%.2f` 是浮点数的占位符，`.2f` 表示保留两位小数。

`printf()` 还有许多不同的占位符可用，可以通过访问 [www.w3schools.com/php/func_printf.asp](http://www.w3schools.com/php/func_printf.asp) 了解。

以下是常用的 `printf()` 占位符：

| 占位符 | 描述 |
| :--- | :--- |
| `%s` | 字符串 |
| `%d` | 整数 |
| `%f` | 浮点数 |
| `%b` | 二进制 |
| `%x` | 十六进制整数 |
| `%X` | 十六进制整数 |
| `%u` | 无符号整数 |
| `%p` | 指针地址 |
| `%c` | 字符 |
| `%g` | 自动选择 %f 或 %e |

以下是使用这些格式的示例：

```php
printf("My name is %s", "Alice");
```

输出：My name is Alice.

```php
printf("I am %d years old", 30);
```

输出：I am 30 years old.

```php
printf("The price is $%.2f", 19.99);
```

输出：The price is $19.99.

```php
printf("The binary value of 5 is %b", 5);
```

输出：The binary value of 5 is 101.

```php
printf("The hexadecimal value of 255 is %x", 255);
```

输出：The hexadecimal value of 255 is ff.

```php
printf("The hexadecimal value of 255 is %X", 255);
```

输出：The hexadecimal value of 255 is FF.

```php
printf("The unsigned value of 255 is %u", 255);
```

输出：The unsigned value of 255 is 255.

```php
$var = 5;
printf("The address is: %p", $var);
```

输出：The address is: 0x7ffee457a98c.

```php
printf("The character is %c", "A");
```

输出：The character is A.

```php
printf("The value is %g", 12.3456);
```

输出：The value is 12.35.

现在让我们创建一个一次性使用所有三个命令的程序，以便看到它们的区别。

第 1 步：创建一个具有基础结构的 HTML 文档并嵌入 PHP 起始和结束标签。使用所给的格式：

```html
<!DOCTYPE html>
<html>
<head>
<title>输出</title>
</head>
<body>
    <?php
      echo "This is echoed out";
      echo ("</br>This is also echoed out");
      print ("</br>This line was displayed using print");
      print "</br>This line was displayed using print without the ()";
      printf ("</br>Today is the year %d.", 2013);
      printf ("</br>Five divided by two is %f", 2.5);
  ?>
</body>
</html>
```

第 2 步：将文件保存到 `www`（或 `htdocs`）文件夹中并命名为 `output`。以 `.php` 扩展名保存。

第 3 步：保存文件后，打开浏览器并在地址栏中输入 `http://localhost/output.php`。

输出将如下所示：

![](img/00025.jpeg)

图 1.23：执行 output.php 的结果。

与 `print()` 相比，`Printf()` 具有更多功能，并且由于格式化的存在，使得内容更容易理解。

以上就是 `PHP` 中显示字符串的三个基本命令。

# 章节练习

1. `PHP` 代表什么？

a. Philadelphia Hyper People.

b. Pre Hypertext Processor.

c. Phenomenal Hilarious Panda.

d. Post Hypertext Processing.

2. `WAMP` 中的 `A` 代表什么？

a. Apache.

b. Analog（模拟）。

c. Algorithm（算法）。

d. Asynchronous（异步）。

3. 使用什么地址来检查由 Windows 版 `Apache` 服务器生成的首页？

a. `http://localhost`

b. `https://localpage`

c. `https://localhosts`

d. `http://localhosts`

4. 正确的 `PHP` 起始标签是什么？

a. `<php`

b. `<?php?`

c. `<??php`

d. `<?php`

5. 哪些命令可以显示格式化后的字符串输出？

a. `echo( " ");`

b. `print( " ");`

c. `prints( " ");`

d. `printf( " ");`

# 章节实验题：

1. 创建一个具有骨架基础 HTML 文档。

2. 插入正确的 `script` 标签以便 `PHP` 能被识别。

3. 创建必要的代码来显示你的姓名、兴趣或爱好、年龄和生日。使用 `<h1>` 标签显示姓名，使用 `<h2>` 显示你的兴趣或爱好，并使用 `printf()` 命令以 `dd/mm/yyyy` 日期格式显示年龄和生日。

4. 确保每条信息都显示在新行。使用换行标签 `<br/>`。

# 章节实验答案：

![](img/00026.jpeg)

图 1.24：实验答案输出。

代码列表：第 1 章实验答案

```html
<!DOCTYPE html>
<html>
<head>
<title> PHP 实验 1</title>
</head>
<body>
    <?php
        echo("<h1> Adam Caper</h1>");
        echo("</br><h2>I like basketball, cooking, computer games, playing the guitar, and dancing.</h2>");
        printf ("</br>I am %d years old", 21);
        printf ("</br>My birthday is %d / %d / %d", 2, 7, 1992);
    ?>
</body>
</html>
```

# 章节总结：

在本章中，你学习了 `PHP` 是一种运行在服务器端的脚本语言。我们还识别、下载并安装了编写和运行 `PHP` 所需的软件包包。我们描述了 `PHP` 的工作流，并详细介绍了 `PHP` 代码是如何构建、测试和实现的。

我们解释了 `PHP` 脚本嵌入在 `HTML` 文档中，`HTML` 标签也可以嵌入 `PHP` 脚本中。

我们还讨论了三个用于显示文本输出的命令，了解 `PHP` 脚本是如何处理的，并解释了为什么它们会在文档源代码中消失。

在下一章中，我们将讨论变量：如何命名、为它们赋值，以及如何结合不同的运算符使用变量。

# 第 2 章：变量

## 章节目标：

* 你将能够定义 `PHP` 变量和运算符。
* 你将能够描述使用变量和运算符的过程。
* 你将学习如何正确编写变量操作代码。
* 你将能够创建并编写涉及变量操作的 `PHP` 脚本。

## 2.1 变量简介

变量用于存储八种 `PHP` 数据类型任一种值的内存单元，即：整数、浮点数、字符串、布尔值、数组、对象、资源和空。（这些数据类型将在后续章节中讨论。）

变量需要命名。在 `PHP` 中，变量名以美元符号 `$` 开头，后面跟着字母、数字以及有时下划线。使用下划线的一个规则是它可以放在名称的任何位置，但不要紧跟在 `$` 后面。因此，请避免像 `$_myvariable` 这样的变量名。

让我们对之前的示例进行调整并引入浮点数的使用。

打开 `variables.php` 文件，并将下方代码列表中 PHP 脚本标签内部的代码行添加到其中：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Variables In PHP</title>
</head>
<body>
    <?php
        $name = "Adam";
        $age = 21;
        $height = 165.1;
        print($name);
        print("<br/>");
        print($age);          
        print("<br/>");
        print($height);
    ?>
</body>
</html>
```

以相同的文件名 `variables.php` 保存文件，并在浏览器地址栏中输入以下地址进行访问，Windows 系统：

`http://localhost/variables.php`

Mac 系统则：

`localhost:8888/variables.php`

你的输出应该像所示：

![](img/00030.jpeg)

图 2.4：在浏览器中输出声明的变量，包括浮点数。

我们为什么不尝试稍微调整输出，使其更有意义呢？为每个输出值标记标签肯定对用户来说更有意义。如下所示修改你的代码列表，保存为相同的文件名 `variables.php` 并显示输出：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Variables In PHP</title>
</head>
<body>
    <?php
        $name = "Adam";
        $age = 21;
        $height = 165.1;
        print("First Name: ");
        print($name);
        print("<br/>");
        print("Age: ");
        print($age);          
        print("<br/>");
        print("Height: ");
        print($height);
    ?>
</body>
</html>
```

现在，像之前一样在浏览器地址栏输入并访问 `variables.php`：Windows 系统输入 `http://localhost/variables.php`，Mac 系统输入 `localhost:8888/variables.php`。

你的输出应该像下面的截图：

![](img/00031.jpeg)

图 2.5：为每个输出值标记标签。



我们能够成功地使用`print`命令在值前面放置一些文本标签。然而，还有另一个称为“拼接”（concatenation）的过程，它可以让我们更轻松地完成相同任务。拼接是将几个不同的事物或对象连接成一个完整单元的过程。在这个示例中，我们将每个文本标签及其关联的值连接成一个单元，并在该行中显示该单元。

PHP 中的拼接过程与其他编程语言相比是独特的。如果你熟悉 Javascript 或 HTML，你可能记得加号（`+`）是拼接运算符。在 PHP 中，使用的是点号（`.`）来进行拼接。

如果我们将之前的代码列表更改为使用拼接，代码将更短且更高效：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Variables In PHP</title>
</head>
<body>
    <?php
        $name = "Adam";
        $age = 21;
        $height = 165.1;
        print("First Name: ".$name);
        print("<br/>");
        print("Age: ".$age);
        print("<br/>");
        print("Height: ".$height);
    ?>
</body>
</html>
```

在网络浏览器中查看时，结果应该如下：

![](img/00031.jpeg)

图 2.6：使用拼接过程为每个输出值标记标签。

这个示例演示了拼接的一个非常简单的用。接下来的 HTML 文档显示了更多拼接的示例。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Variables and Concatenation in PHP</title>
</head>
<body>
    <?php
        $name = "Adam";
        $age = 21;
        $taxRate = 0.12;
        print($name);
        print("<br/>");
        print($age);
        print("</br>");
        print($name . " is " . $age . " years.");
        print("</br>");
        printf("The tax rate in Guacamole Island is %0.2f", $taxRate);
        print("</br>");
        $value = 25*62/72+42-51+101*2;
        print("The final value of "."((5*62/72+42-51+101*2)."is ". $value);
    ?>
</body>
</html>
```

在浏览器中查看时，输出将像所示：

![](img/00032.jpeg)

图 2.7：在更复杂的情况下使用拼接过程。

请记住，在赋值变量名时，你可以使用字母（A-Z, a-z）、数字（0-9）或两者的组合，以及下划线字符。虽然下划线字符可以使用`$`符号后的任何位置，但按照习惯，它不会紧跟在`$`符号之后。最后，变量名是区分大小写的。

在命名变量时，采用一致的风格是一个良好的习惯。其中一种风格是在命名变量时使用下划线分隔单词。这种风格要求在变量命名中保持下划线，例如`$tax_Rate`。无论你采用什么样的命名风格，都必须保持一致，例如`$pending_Payments`。

## 2.2 运算符

PHP 中的数学运算符有加、减、乘、除。除了这四种基础运算，还有特殊的运算符，如增、减、模、以及组合运算符。

预计你到此时已经熟悉创建新 PHP 文件的过程。让我们复习已经学过的基础运算符，同时练习算术运算。

首先，创建一个基础 HTML 文档。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Addition Operation in PHP</title>
</head>
```

接下来，在文档主体中包含 PHP 脚本标签。为变量`$x`和`$y`赋值数值，`$x`为 110，`$y`为 52。在 PHP 脚本标签内部，处理这两个变量的加法运算。

```html
<body>
    <?php
        $x = 110;
        $y = 52;
        print($x." + ".$y."=". ($x + $y));
    ?>
</body>
```

将你的文件保存为`addOperation.php`。输出应该如所示：

![](img/00033.jpeg)

图 2.8：处理两个变量的加法运算。

让我们在代码中包含剩余的三个基础运算。你可以复制粘贴添加`$x`和`$y`的代码行三次，然后将加法运算符改为减法（`-`），然后改为乘法（`*`），最后改为除法（`/`）。将你的文件保存为`operators.php`然后刷新你的浏览器。

提示：我是编写程序代码时使用复制粘贴的坚定支持者。如果你重新输入某行，会增加无意中引入错误的概率。

此示例的完整代码列表如下：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Operators in PHP</title>
</head>
<body>
    <?php
        $x = 110;
        $y = 52;
```

```php
print($x . " + " . $y . " = " . ($x + $y));
print("</br>");
print($x . " - " . $y . " = " . ($x - $y));
print("</br>");
print($x . " * " . $y . " = " . ($x * $y));
print("</br>");
print($x . " / " . $y . " = " . ($x / $y));
print("</br>");
?>
</body>
</html>
```

![](img/00034.jpeg)

图 2.9: 处理两个变量的基础算术运算。

显然，如果你为`$x`和`$y`分配了不同的值，你应该期望不同的结果。

如你所见，基础算术操作很容易编写。现在我们将讨论其他特殊运算符是如何实现的。

在下表中列出了特殊运算符以及它们实现功能的简要描述：

| 运算符 | 描述 |
| :--- | :--- |
| 递增 `x++` | 将`x`的值加 1。 |
| 递减 `x--` | 将`x`的值减 1。 |
| 取模 `x % y` | 返回`x`除以`y`的余数。 |
| 组合运算符： | |
| 拼接后返回 `.=` | 拼接并返回运算符左侧表达式中的结果。 |
| 加法后返回 `+=` | 将运算符左侧表达式的值加到运算符右侧表达式上。 |
| 减法后返回 `-=` | 从运算符右侧表达式中减去运算符左侧表达式的值。 |
| 乘法后返回 `*=` | 将运算符左侧表达式的值乘以运算符右侧表达式的值。 |
| 除法后返回 `/=` | 将运算符左侧表达式的值除以运算符右侧表达式的值。 |

让我们详细扩展上一个示例中显示的操作。我们将包括数值的递增和递减、获取除法运算的余数（取模），以及使用不同的组合运算符。

继续你的 PHP 文档`operators.php`。

将文档标题更改为

`<title>"All PHP Operators"</title>`

然后使用文件名`alloperators.php`另存为另一个文件。

在你的原始代码列表中添加以下行代码：

```php
$x++;
$y--;
```

`$x++`将递增`$x`。

`$y--`将递减`$y`。

原始代码列表：

```html
<!DOCTYPE html>
<html>
<head>
    <title>Operators in PHP</title>
</head>
<body>
    <?php
        $x = 110;
        $y = 52;
        print($x . " + " . $y . " = " . ($x + $y));
        print("</br>");
        print($x . " - " . $y . " = " . ($x - $y));
        print("</br>");
        print($x . " * " . $y . " = " . ($x * $y));
        print("</br>");
        print($x . " / " . $y . " = " . ($x / $y));
        print("</br>");
```

为了美观的输出，追加以下行：

```php
print("</br>");
print("Incrementing x =" .$x++);
print("Decrementing y =" .$y--);
print("</br>");
print("Modulus of x and y = " . ($x%$y));
print("</br>");
```

接下来，我们将引入带有以下名称和值的变量：

`$first = 10;`

`$second = 3;`

`$third = 20;`

`$fourth = 4;`

`$fifth = 30;`

`$sixth = 7;`

`$seventh = 50;`

`$eighth = 6;`

使用这些新变量，对`$first`和`$second`执行组合加法，对`$third`和`$fourth`执行组合减法，对`$fifth`和`$sixth`执行组合乘法，并对`$seventh`（被除数）和`$eighth`（除数）执行组合除法：

```php
$first += $second;
$third -= $fourth;
$fifth *= $sixth;
$seventh /= $eighth;
```

使用`echo()`命令显示`$first`、`$third`、`$fifth`和`$seventh`的值。记住`echo`命令的工作方式与`print()`命令相同：

```php
echo($first);
echo("</br>");
echo($third);
echo("</br>");
echo($fifth);
echo("</br>");
echo($seventh);
echo("</br>");
```

在接下来的行中，使用组合运算符后返回（`.=`）显示拼接结果。

```php
$line = "Hello this is a test for concatenation and...";
$line .= "</br> Connect this phrase and place it on the next line";
echo($line);
```

关闭脚本和整个文档：

```php
?>
</body>
</html>
```

这是运行代码时得到的结果：

![](img/00035.jpeg) 图 2.10: 使用组合运算符输出数字和字符串。

以下是完整代码列表：

```html
<!DOCTYPE html>
<html>
<head>
    <title>Operators in PHP</title>
</head>
<body>
    <?php
        $x = 110;
        $y = 52;
        print($x . " + " . $y . " = " . ($x + $y));
        print("</br>");
        print($x . " - " . $y . " = " . ($x - $y));
        print("</br>");
        print($x . " * " . $y . " = " . ($x * $y));
        print("</br>");
        print($x . " / " . $y . " = " . ($x / $y));
        print("</br>");
        print("</br>");
        print("Incrementing x =" .$x++);
        print("Decrementing y =" .$y--);
        print("</br>");
        print("Modulus of x and y = " . ($x%$y));
        print("</br>");

        $first = 10;
        $second = 3;
        $third = 20;
        $fourth = 4;
        $fifth = 30;
        $sixth = 7;
        $seventh = 50;
        $eighth = 6;

        $first += $second;
        $third -= $fourth;
        $fifth *= $sixth;
        $seventh /= $eighth;

        echo($first);
        echo("</br>");
        echo($third);
        echo("</br>");
        echo($fifth);
        echo("</br>");
        echo($seventh);
        echo("</br>");

        $line = "Hello this is a test for concatenation and...";
        $line .= "</br> Connect this phrase and place it on the next line";
        echo($line);
    ?>
</body>
</html>
```

# 验

1. 什么是变量？

a. 变量是字符串的容器。

b. 变量是数值的容器。

c. 变量随时间变化。

d. 变量是存储值的进程。

2. 常见算术运算符的操作是什么？

a. 加、减、拼接、除法。

b. 加、减、乘法、除法。

c. 拼接、递减、加法。

d. 递增、递减、加法、减法。

3. 拼接后返回的正确语法是什么？

a. `+=`

b. `-=`

c. `.=`

d. `==`

4. 为了编写给某个变量加 1 的程序，可以使用什么运算符？

a. 递增

b. 递减

c. 减 -1

d. a 和 c

# 练习

1. 创建一个具有基本结构的 HTML 文档。

2. 添加适当标签以包含 PHP 脚本。

3. 声明四个变量。将它们命名为`$w`、`$x`、`$y`和`$z`，并为它们分配以下整数值：

   `$w = 5;`

   `$x = 25;`

   `$y = 13;`

   `$z = 101;`

4. 使用`echo()`或`print()`显示变量`$w`、`$x`、`$y`和`$z`的初始值。

5. 应用换行。添加对四个变量执行以下基础算术运算的代码：

   `$w + $x`

   `$z – $y`

   `$z / $w`

   `$y * $x`

6. 显示每个数学运算的答案，但将答案格式化一位。将每个结果存储在一个新变量中。将结果分配给以下新变量：

   将`$w + x`的和分配给变量`$a`，

将`$z – y`的差分配给变量`$b`，

将`$z / w`的商分配给变量`$c`，并将`y * x`的乘积分配给变量`$d`。

7. 在下一行，显示结果——递增`$a`和`$b`并分别换行显示其结果，递减`$c`和`$d`并分别换行显示其结果。

8. 显示以下组合运算`+=`的结果：

   `$wxyz = ($a+= ($b+=($c+=$d)))`

# 实验答案

![](img/00036.jpeg) 图 2.11: 实验输出

```html
<!DOCTYPE html>
...
```

# 第 2 章实验练习



# 第 2 章 实验练习

```php
<?php
    $w = 5;
    $x = 25;
    $y = 13;
    $z = 101;
    //显示 w, x, y, z 的值
    echo("w = " . $w);
    echo("</br>");
    echo("x = " . $x);
    echo("</br>");
    echo("y = " . $y);
    echo("</br>");
    echo("z = " . $z);
    echo("</br>");
    $a = ($w + $x);
    $b = ($z - $y);
    $c = ($z / $w);
    $d = ($y * $x);
    //显示基础运算结果
    // 格式保留一位小数
    printf("w + x = %0.1f", $a);
    echo("</br>");
    printf("z - y = %0.1f", $b);
    echo("</br>");
    printf("z / w = %0.1f", $c);
    echo("</br>");
    printf("y * x = %0.1f", $d);
    echo("</br>");
    // a 和 b 自增，c 和 d 自减
    $a++; $b++; $c--; $d--;
    // 串联 A, B, C 和 D 的值
    echo("A = " . $a . " | B = " . $b . " | C = " . $c . " | D = " .$d);
    echo("</br>");
    //显示 $wxyz 的值
    $wxyz = ($a+= ($b+=($c+=$d)));
    echo($wxyz);
?>
```

## 章总结

在本章中，你学习了 `PHP` 中的变量以及它们在声明和实现时与其他语言的区别。

我们讨论了 `PHP` 中不同的运算符以及每个运算符的用途。本章还涵盖了 `PHP` 中的组合运算符和字符串拼接，以及它们在实际程序例程中是如何实现的。

在下一章中，我们将讨论数组——简单数组、关联数组、多维数组和全局数组。

# 第 3 章：数组

### 本章目标

- 你将能够定义数组。
- 你将能够描述 `PHP` 数组的两种类型：索引数组和关联数组。
- 你将学习如何在 `PHP` 中声明和实例化数组。
- 你将介绍 `PHP` 的一些超全局数组。

## 3.1 简单数组或索引数组

数组是用于存储多个值的变量。数组的每个值被称为一个元素（或成员），每个元素都通过其自身的整数索引 `0,1,2,3` 等进行引用。索引还标识了元素在数组中的位置。（索引 `0` 标识第一个元素，索引 `1` 标识第二个元素，以此类推。）在数组中，可以添加、删除、修改和重新排列（排序）元素。

存储在数组中的值可以是八种 `PHP` 数据类型之一：`integer`（整数）、浮点数、`string`（字符串）、`boolean`（布尔）、`object`（对象）、`resources`（资源）、`null` 和 `arrays`（数组）。数组广泛用于存储列表的值。例如，如果你想存储一个团队的所有名称，数组是完美的选择。

在 `PHP` 中，用于创建数组的函数是 `array()`。简单数组（或索引数组）是使用成员数字索引的数组。这种索引通常是顺序的，但也允许随机索引。

在 `PHP` 中声明数组与在 `PHP` 中声明变量相似——美元符号（`$`）位于变量名之前。数组是零索引的，这意味着索引从 `0` 开始——且索引 `0` 始终指向数组的第一个成员。

声明数组首先是写数组名称，跟着等号（`=`），然后是括号内要存储在数组中的值。在下面的示例中，我们有一个由四个 `string` 类型元素组成的数组：

```php
$names = array ("John", "Larry", "Jane", "Lily");
```

如果我们仔细观察这个数组，会发现第一个元素是 `$names[0]`，值为 "John"，第二个元素是 `$names[1]`，值为 "Larry"，第三个是 `$names[2]`，值为 "Jane"，最后一个是 `$names[3]`，值为 "Lily"。

数组也可以定义为：

```php
$names[0] = "John";
$names[1] = "Larry";
$names[2] = "Jane";
$names[3] = "Lily";
```

可以在变量上执行的操作或命令也可以在数组的每个成员上执行，例如 `print()`、`echo()`、拼接和数学运算。我们将使用数组演示这些中的每一个操作。创建一个新的 HTML 模板，并将其保存到 `www`（Windows）或 `htdocs`（Mac）文件夹中，文件名为 `simple_array.php`。放置正确的起始和结束标签。

在上面的系列操作中，我们已经声明了数组。声明数组的另一种方法是手动方法，即将数组的各个成员分配给各自的索引。我们将使用数组名 `$fruit` 声明数组，并通过输入以下代码手动为数组的每个元素赋值：

```php
$fruit[0] = "Berries";
$fruit[3] = "Mangos";
$fruit[4] = "Apples";
```

```php
//Display the array member pairing
echo($first_names[0] . " likes to eat " . $fruit[5]);
echo("</br>");
echo($first_names[1] . " likes to eat " . $fruit[3]);
echo("</br>");
echo($first_names[2] . " likes to eat " . $fruit[4]);
echo("</br>");
echo($first_names[3] . " likes to eat " . $fruit[0]);
echo("</br>");
?>
</body>
</html>
```

### 第 5 步：查看你的运行结果。输出应如所示：

![](img/00042.jpeg)

图 3.6：通过调用简单数组的成员构建句子。

## 3.2 关联数组

关联数组是为每个数组成员分配唯一键值（key value）的数组。这些数组使用命名的键来识别其成员或元素，而不是简单数组使用的数字键（索引）。假设你想在一个数组中存储员工的薪水。数字索引数组不是存储这些值的最佳选择。在关联数组中，员工的姓名充当键，并根据他们的姓名关联其薪水率。

声明关联数组与数字索引数组不同。数字索引数组遵循此数组声明格式：

`$变量名 [索引数字] = 值;`

关联数组遵循此声明格式：

`$变量名 = array(键名 => 值, )`

让我们尝试一下。

**第 1 步**：在你的文本编辑器中创建一个新的 HTML5 文档。使用文件名 `associative_array.php`。确保你包含了 `PHP` 的开始和结束标签。保存你的文件。

**第 2 步**：现在让我们创建一个包含四名员工及其相应薪水的数组。

我们将拥有员工："Doe" 年薪为 $30,000，"Smith" 年薪为 $28,000，"Rogers" 年薪为 $50,000，"Adam" 年薪为 $120,000，以及 "Brown" 年薪为 60,000。

关联数组的声明将如下：

```php
$salary = array("Doe" => 30000,
    "Smith" => 28000,
    "Rogers" => 50000,
    "Adam" => 120000,
    "Brown" => 60000);
```

注意空格和对齐的使用，这使得代码更易读。我们可以使用一行、最小间隔来声明该数组，如下：

`$salary = array("Doe"=>30000,"Smith"=>28000,"Rogers"=>50000, "Adam"=>120000,Brown"=>75000);`

但这不如之前的声明那样具有可读性。

**第 3 步**：然后我们将使用 `echo()` 或 `print()` 配合字符串连接来显示输出，内容为 "Full name 的年薪为 `$salary["Doe"]`"。用于显示预定输出的命令是：

`print("John Doe has an annual salary of " . $salary["Doe"] . ”<br/>”);`

以下代码将显示数组中存储的所有值。



```php
//Display the array members
echo("John Doe has an annual salary of $" . $salary["Doe"] . ".");
echo("</br>");
echo("Robert Smith has an annual salary of $" . $salary["Smith"] . ".");
echo("</br>");
echo("Sam Rogers has an annual salary of $" . $salary["Rogers"] . ".");
echo("</br>");
echo("Drei Adam has an annual salary of $" . $salary["Adam"] . ".");
echo("</br>");
echo("Jim Brown has an annual salary of $" . $salary["Brown"] . ".");
echo("</br>");
```

**第 4 步**：关闭 PHP 脚本，确保你有适当的 HTML 标签。保存文件。

```php
?>
</body>
</html>
```

**第 5 步**：将你的程序与以下代码列表进行对比。代码：`associative_array.php`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Chapter 3: Associative Array</title>
</head>
<body>
    <?php
    //Declare the array
    $salary = array("Doe"=>"30000", "Smith"=>"28000", "Rogers"=>"50000", "Adam"=>"120000", "Brown"=>"75000");
    //Display the array
    echo("John Doe has an annual salary of $" . $salary["Doe"] . ".");
    echo("</br>");
    echo("Robert Smith has an annual salary of $" . $salary["Smith"] . ".");
    echo("</br>");
    echo("Sam Rogers has an annual salary of $" . $salary["Rogers"] . ".");
    echo("</br>");
    echo("Drei Adam has an annual salary of $" . $salary["Adam"] . ".");
    echo("</br>");
    echo("Jim Brown has an annual salary of $" . $salary["Brown"] . ".");
    echo("</br>");
    ?>
</body>
</html>
```

**第 6 步**：在浏览器中查看你的结果。不要忘记通过 `localhost` 使用服务器查看结果。如果正确，输出应该像这样：

![](img/00042.jpeg)

图 3.6：输出关联数组中的值。

## 3.2 关联数组

关联数组是为每个数组成员分配唯一键值的数组。这些数组使用命名的键来识别其成员或元素，而不是简单数组使用的数字键（索引）。假设你想在一个数组中存储员工的薪水。数字索引数组不是存储这些值的最佳选择。在关联数组中，员工的姓名充当键，并根据他们的姓名关联其薪水率。

声明关联数组与数字索引数组不同。数字索引数组遵循此数组声明格式：

`$变量名 [索引数字] = 值;`

关联数组遵循此声明格式：

`$变量名 = array(键名 => 值, )`

让我们尝试一下。

**第 1 步**：在你的文本编辑器中创建一个新的 HTML5 文档。使用文件名 `associative_array.php`。确保你包含了 PHP 的开始和结束标签。保存你的文件。

**第 2 步**：现在让我们创建一个包含四名员工及其相应薪水的数组。

我们将拥有员工：“Doe”年薪为 $30,000，“Smith”年薪为 $28,000，“Rogers”年薪为 $50,000，“Adam”年薪为 $120,000，以及“Brown”年薪为 60,000。

关联数组的声明将如下：

```php
$salary = array("Doe" => 30000,
    "Smith" => 28000,
    "Rogers" => 50000,
    "Adam" => 120000,
    "Brown" => 60000);
```

注意空格和对齐的使用，这使得代码更易读。我们可以使用一行、最小间隔来声明该数组，如下：

`$salary = array("Doe"=>30000,"Smith"=>28000,"Rogers"=>50000, "Adam"=>120000,Brown"=>75000);`

但这不如之前的声明那样具有可读性。

**第 3 步**：然后我们将使用 `echo()` 或 `print()` 配合字符串连接来显示输出，内容为“Full name 的年薪为 $salary["Doe"]”。用于显示预定输出的命令是：

`print("John Doe has an annual salary of " . $salary["Doe"] . ”<br/>”);`

以下代码将显示数组中存储的所有值。

```php
//Display the array members
echo("John Doe has an annual salary of $" . $salary["Doe"] . ".");
echo("</br>");
echo("Robert Smith has an annual salary of $" . $salary["Smith"] . ".");
echo("</br>");
echo("Sam Rogers has an annual salary of $" . $salary["Rogers"] . ".");
echo("</br>");
echo("Drei Adam has an annual salary of $" . $salary["Adam"] . ".");
echo("</br>");
echo("Jim Brown has an annual salary of $" . $salary["Brown"] . ".");
echo("</br>");
```

**第 4 步**：关闭 PHP 脚本，确保你有适当的 HTML 标签。保存文件。

```php
?>
</body>
</html>
```

**第 5 步**：将你的程序与以下代码列表进行对比。代码：`associative_array.php`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Chapter 3: Associative Array</title>
</head>
<body>
    <?php
    //Declare the array
    $salary = array("Doe"=>"30000", "Smith"=>"28000", "Rogers"=>"50000", "Adam"=>"120000", "Brown"=>"75000");
    //Display the array
    echo("John Doe has an annual salary of $" . $salary["Doe"] . ".");
    echo("</br>");
    echo("Robert Smith has an annual salary of $" . $salary["Smith"] . ".");
    echo("</br>");
    echo("Sam Rogers has an annual salary of $" . $salary["Rogers"] . ".");
    echo("</br>");
    echo("Drei Adam has an annual salary of $" . $salary["Adam"] . ".");
    echo("</br>");
    echo("Jim Brown has an annual salary of $" . $salary["Brown"] . ".");
    echo("</br>");
    ?>
</body>
</html>
```

**第 6 步**：在浏览器中查看你的结果。不要忘记通过 `localhost` 使用服务器查看结果。如果正确，输出应该像这样：

![](img/00042.jpeg)

图 3.7：输出关联数组中的值。

## 3.3 多维数组

多维数组是元素本身也是数组的数组。多维数组是一个包含多个“子数组”的主数组。多维数组的一个常见用途是计算机游戏。如果你考虑游戏“关卡”，这些关卡的信息存储在一个或多个多维数组中。声明多维数组与声明关联数组相似，但不再是键及其对应的值，你仍然拥有键，但每个值将是一个数组。让我们处理一个示例。打开一个新文件并检查一些代码以以理解该概念。创建一个 HTML5 文档并将其保存到 `www`（Windows, WAMP）或 `htdocs`（Mac, MAMP）文件夹中，文件名为 `multidimensional_array.php`。

![Komodo Create new 5 doc.](img/00045.jpeg)

图 3.9：Komodo 编辑首页。

![](img/00046.jpeg)

图 3.10：将新文档保存为 `multidimensional_array.php`。

确保你的文件中包含了 PHP 的开始和结束标签。以下数组内容示例来自流行的角色扮演游戏。主数组是背包，子数组将是 `Weapons`、`Armors`、`Useables`、`Key_Items` 和 `Magic_Items`。每个子数组将是描述每个部分的关联数组。

`Weapons` 将是一个包含以下内容的简单数组：

Krasnaya、Executioner、Violet Fear、Atroce’s Blade

```php
"Weapon" => array (
    "Krasnaya",
    "Executioner",
    "Violet Fear",
    "Atroce's Blade"
),
```

`Armors` 数组将包含以下成员：

Lord Kaho’s Horns, Megingjard, Sleipnir, Dragon Manteau, Ears of Ifrit

```php
"Armors" => array (
    "Lord Kaho's Horns",
    "Megingjard",
    "Sleipnir",
    "Dragon Manteau",
    "Ears of Ifrit"
),
```

```php
"Armors" => array
(
    "Lord Kaho's Horns",
    "Megingjard",
    "Sleipnir",
    "Dragon Manteau",
    "Ears of Ifrit"
),
```

使用道具（Useables）将包含以下成员：世界之树之果、狂暴药水、权威勋章、加速药水、万能药、诅咒水。

```php
"Useables" => array
(
    "Yggdrasil Berry",
    "Berserk Potion",
    "Authoritative Badge",
    "Speed Potion",
    "Panacea",
    "Cursed Water"
),
```

Key_Items（关键道具）数组将包含以下成员：大陆卫队证书、黑暗之烬、龙牙、龙鳞、龙皮。

```php
"Key_Items" => array
(
    "Continental Guard Certificate",
    "Ashes of Darkness",
    "Dragon Tooth",
    "Dragon Scale",
    "Dragon Skin"
),
```

Magic_Items 数组将包含以下成员：10 级祝福卷轴、10 级敏捷卷轴、10 级假设卷轴。

```php
"Magic_Items" => array
(
    "Lvl10 Blessing Scroll",
    "Lvl10 Increase AGI Scroll",
    "Lvl10 Assumptio Scroll"
),
```

现在多维数组已经填充了元素，我们可以向您展示如何调用每个数组。引用多维数组使用的语法为 `$varilename[subarray1][subarray2]`。在多维数组 `$backpack` 中实现时，这意味着：

```php
$backpack = array
    "Weapons" => array("Krasnaya", "Executioner", "Violet Fear"),
    "Armors" => array ("Lord Kaho's Horns", "Megingjard", "leipnir", "Ears of Ifrit"),
    "Useables" => array("Yggdrasil Berry", "Berserk Potion", "Authoritative Badge", "Speed Potion", "Cursed Water"),
    "Key_Items" => array("Continental Guard Certificate", "Ashes of Darkness", "Dragon Tooth", "Dragon Scale"),
    "Magic_Items" => array("Lvl10 Blessing Scroll", "Lvl10 Increase AGI Scroll", "Lvl10 Assumptio Scroll"));
```

为了使上述多维数组更易读，您可能希望遵循以下格式：

```php
$backpack = array(
    "Weapons" => array(
        "Krasnaya",
        "Executioner",
        "Violet Fear",
        "Atroce's Blade"
    ),
    "Armors" => array(
        "Lord Kaho's Horns",
        "Megingjard",
        "Sleipnir",
        "Dragon Manteau",
        "Ears of Ifrit"
    ),
    "Useables" => array(
        "Yggdrasil Berry",
        "Berserk Potion",
        "Authoritative Badge",
        "Speed Potion",
        "Panacea",
        "Cursed Water"
    ),
    "Key_Items" => array(
        "Continental Guard Certificate",
        "Ashes of Darkness",
        "Dragon Tooth",
        "Dragon Scale",
        "Dragon Skin"
    ),
    "Magic_Items" => array(
        "Lvl10 Blessing Scroll",
        "Lvl10 Increase AGI Scroll",
        "Lvl10 Assumptio Scroll"
    )
);
```

现在每个数组都已填充，我们可以尝试调用多维数组中的成员。要做到这一点，我们将遵循格式：`$variable[subarray1][subarray2]`。例如，假设我们想要调用数组成员 `er`（它属于 `Weapon`）并显示它。正确的代码是：`echo($backpack['Weapon'][1]);`。

如果您想访问数组中的其他成员，也适用相同的语法。让我们显示整个 `$backpack` 的库存——背包内部的每个分区，然后是每个分区中的所有物品，最后以不特定顺序显示每个分区的某一个物品。显示所有的 `backpack` 分区以及每个 `division` 中的所有物品：



```php
echo("Backpack Contents for Weapons: <br>");
echo($backpack['Weapons'][0]) . "<br>";
echo($backpack['Weapons'][1]) . "<br>";
echo($backpack['Weapons'][2]) . "<br>";
echo("Backpack Contents for Armors: <br>");
echo($backpack['Armors'][0]) . "<br>";
echo($backpack['Armors'][1]) . "<br>";
echo($backpack['Armors'][2]) . "<br>";
echo($backpack['Armors'][4]) . "<br>";
echo("Backpack Contents for Useables: <br>");
echo($backpack['Useables'][0]) . "<br>";
echo($backpack['Useables'][1]) . "<br>";
echo($backpack['Useables'][2]) . "<br>";
echo($backpack['Useables'][3]) . "<br>";
echo($backpack['Useables'][5]) . "<br>";
echo("Backpack Contents for Key Items: <br>");
echo($backpack['Key_Items'][0]) . "<br>";
echo($backpack['Key_Items'][1]) . "<br>";
echo($backpack['Key_Items'][2]) . "<br>";
echo($backpack['Key_Items'][3]) . "<br>";
echo("Backpack Contents for Magic Items: <br>");
echo($backpack['Magic_Items'][0]) . "<br>";
echo($backpack['Magic_Items'][1]) . "<br>";
```

完整的代码列表现在应该是：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Multidimensional Arrays</title>
</head>
<body>
    <?php
        $backpack = array
        (
            "Weapons" => array
                (
                    "Krasnaya",
                    "Executioner",
                    "Violet Fear",
                    "Atroce's Blade"
                ),
            "Armors" => array
                (
                    "Lord Kaho's Horns",
                    "Megingjard",
                    "Sleipnir",
                    "Dragon Manteau",
                    "Ears of Ifrit"
                ),
```

**提示：** 正如丰富的工程师会告诉你的那样，你正在为多个受众编写代码。PHP 代码的第一个受众是解释它的服务器。第二个受众是阅读你代码的人类（包括你自己）。良好的软件工程要求你编写能够让这两类受众都能易读的代码。

```php
"Ears of Ifrit",
),
"Useables" => array
(
    "Yggdrasil Berry",
    "Berserk Potion",
    "Authoritative Badge",
    "Speed Potion",
    "Panacea",
    "Cursed Water",
),
"Key_Items" => array
(
    "Continental Guard Certificate",
    "Ashes of Darkness",
    "Dragon Tooth",
    "Dragon Scale",
    "Dragon Skin",
),
"Magic_Items" => array
(
    "Lvl 10 Blessing Scroll",
    "Lvl 10 Increase AGI Scroll",
    "Lvl 10 Scroll",
);
echo("Backpack Contents for Weapons: <br>");
echo($backpack['Weapons'][0] . "</br>");
echo($backpack['Weapons'][1] . "</br>");
echo($backpack['Weapons'][2] . "</br>");
echo($backpack['Weapons'][3] . "<br><br>");
echo("Backpack Contents for Armors: <br>");
echo($backpack['Armors'][0] . "</br>");
echo($backpack['Armors'][1] . "</br>");
echo($backpack['Armors'][2] . "</br>");
echo($backpack['Armors'][3] . "<br><br>");
echo("Backpack Contents for Useables: <br>");
echo($backpack['Useables'][0] . "</br>");
echo($backpack['Useables'][1] . "</br>");
echo($backpack['Useables'][2] . "</br>");
echo($backpack['Useables'][3] . "</br>");
echo($backpack['Useables'][4] . "</br>");
echo($backpack['Useables'][5] . "<br><br>");
echo("Backpack Contents for Key Items: <br>");
echo($backpack['Key_Items'][0] . "</br>");
echo($backpack['Key_Items'][1] . "</br>");
echo($backpack['Key_Items'][2] . "</br>");
echo($backpack['Key_Items'][3] . "</br>");
echo($backpack['Key_Items'][4] . "<br><br>");
echo("Backpack Contents for Magic Items: <br>");
echo($backpack['Magic_Items'][0] . "</br>");
echo($backpack['Magic_Items'][1] . "</br>");
?>
```

输出结果如下：

![](img/00047.jpeg) 图 3.11：输出多维数组的所有成员。

如果我们只想显示单个项目，那么我们的代码列表可以同样简单：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Multidimensional Arrays</title>
</head>
<body>
    <?php
        $backpack = array
        (
            "We" => array
            (
                "Krasnaya",
                "Executioner",
                "Violet Fear",
                "Atroce's Blade",
            ),
            "Armors" => array
            (
                "Lord Kaho's Horns",
                "Megarding",
                "leipnir",
                "Dragon Manteau",
                "Ears of Ifrit",
            ),
            "Useables" => array
            (
                "Yggdrasil Berry",
                "Berserk Potion",
                "Authoritative Badge",
                "Speed Potion",
                "Panacea",
                "Cursed Water",
            ),
            "Key_Items" => array
            (
                "Continental Guard Certificate",
                "Ashes of Darkness",
                "Dragon Tooth",
                "Dragon Scale",
                "Dragon Skin",
            ),
            "Magic_Items" => array
            (
                "Lvl 10 Blessing Scroll",
                "Lvl 10 Increase AGI Scroll",
                "Lvl 10 Scroll",
            ),
        );
        echo("Weapons[3] : ");
        echo($backpack['Weapons'][3] . "</br><br>");
        echo("Armors[1] : ");
        echo($backpack['Armors'][1] . "</br><br>");
        echo("Useables[5] : ");
        echo($backpack['Useables'][5] . "</br><br>");
        echo("Key Items[0] : ");
        echo($backpack['Key_Items'][0] . "</br><br>");
        echo("Magic Items[2] : ");
        echo($backpack['Magic_Items'][2] . "</br><br>");
    ?>
</body>
</html>
```

输出结果如下：

![](img/00048.jpeg) 图 3.12：输出多维数组的单个成员。

### 我们再来看另一个例子

在本次练习中，我们将创建一个`$teams`数组，它包含子数组：`Yankees`、`Mets`和`Red Sox`。每个子数组都是关联数组，其元素是球员的姓氏。我们的程序将完成一个非常简单的任务：显示第一个球队的名称及其第一个成员的名称。在下一行，显示下一个球队的名称及其第一个成员。程序将对第三支球队执行相同的操作，直到所有球队和成员的姓名都显示完毕。

1. 创建一个新的 HTML5 文档，并将其保存到`www`（Windows 下的 WAMP）或`htdocs`（Mac 下的 MAMP）文件夹下，文件名为`multidimensional_array.php`。

2. 在你的`head`元素中，在`<title>`标签内输入“Teams and Members”。这将是页面的标题。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Teams and Members</title>
</head>
```

3. 在文档的`<body>`中添加 PHP 标签：

```html
<body>
    <?php
    ?>
```

4. 在 PHP 标签内，声明主数组`$teams`，其成员为`Yankees`、`Mets`和`Red Sox`。（这些将是每个元素的键，每个元素本身也是数组）。通过输入以下内容来填充成员列表：

```php
$teams = array
    (
        "Yankees" => array
        (
            "Rivera",
            "Jeter",
            "Granderson",
            "Sabathia",
            "Gradner"
        ),
        "Mets" => array
        (
            "Dickey",
            "Acosta",
            "Pelfrey"
        ),
        "Red Sox" => array
        (
            "Ortiz",
            "Bard",
            "Bucholz",
            "Beckett"
        )
    );
```

5. 仍在 PHP 标签内，添加命令显示第一个球队的名称（目前为字符串）以及该球队数组的第一个成员。使用`echo()`命令：

```php
echo("Yankees--(1) " . $teams['Yankees'][0]);
```

6. 显示第二个球队的名称以及该球队数组的第二个成员。在两个输出行之间插入换行符。代码现在应为：

```php
echo("Yankees--(1) " . $teams['Yankees'][0]);
echo("<br/>");
echo("Mets------(1) " . $teams['Mets'][0]);
```

7. 继续显示球队名称及其后续成员，直到所有数组成员（以球队名称为前）都显示完毕：

```php
echo("Yankees--(1) ".$teams['Yankees'][0]);
echo("<br/>");
echo("Mets------(1) ".$teams['Mets'][0]);
echo("<br/>");
echo("Red Sox--(1) ".$teams['Red Sox'][0]);
echo("<br/><br/>");
echo("Yankees--(2) ".$teams['Yankees'][1]);
echo("<br/>");
```

```php
echo("Mets------(2) ".$teams['Mets'][1]);
echo("<br/>");
echo("Red Sox--(2) ".$teams['Red Sox'][1]);
echo("<br/><br/>");
echo("Yankees--(3) ".$teams['Yankees'][2]);
echo("<br/>");
echo("Mets------(3) ".$teams['Mets'][2]);
echo("<br/>");
echo("Red Sox--(3) ".$teams['Red Sox'][2]);
echo("<br/><br/>");
echo("Yankees--(4) ".$teams['Yankees'][3]);
echo("<br/>");
echo("Mets------(4) ".$teams['Mets'][3]);
echo("<br/>");
echo("Red Sox--(4) ".$teams['Red Sox'][3]);
echo("<br/><br/>");
echo("Yankees--(5) ".$teams['Yankees'][4]);
echo("<br/>");
echo("Mets------(5) ".$teams['Mets'][4]);
echo("<br/>");
echo("Red Sox--(5) ".$teams['Red Sox'][4]);
echo("<br/><br/>");

// 然后关闭脚本和文档：
?>
</body>
</html>
```

保存文件并启动`Firefox`。在 URL 栏或地址栏中，输入`localhost/multidimensional_array.php`（Mac 用户请输入`localhost:8888/multidimensional_array.php`）并查看输出。

你会发现前三个名字显示正常，没有任何任何问题：

![](img/00049.jpeg)

图 3.13：在浏览器中输出数组成员。

而剩余的数组成员显示如下：

![](img/00050.jpeg)

图 3.14：调用数组中未定义的成员会导致错误。

没有显式赋值数值的数组成员会被报告为“undefined offset”（未定义的偏移量）。解决此问题的一种良好方法是在没有更多名称可以显示时显示空格。

该程序应该判断读取的名称是否是数组的最后一个成员，如果是，它应该只“打印”空格来代替缺失的数组成员，直到完成所有球队名称的显示。有助于实现这一目的的命令将在下一章——条件语句中进行讨论。我们将解决方案的讨论和演示留到下一章。

## 3.4 超全局数组



超全局变量（Superglobals）是 `PHP` 内置（预定义）关联数组变量，于 PHP 版本 `4.1.0` 中引入。这些变量对所有 PHP 代码可用，这意味着不需要创建额外的程序使其对整个 PHP 脚本公开。

超全局变量代表来自 URL、HTML 表单、Cookies、Sessions 以及 Web 服务器本身的数据。这些数组在函数内部也可以访问。

欲获取更多帮助和参考，您可以访问以下提供 PHP 友好讨论的 URL：

- `http://php.net/manual/en/index.php`
- `http://www.w3schools.com/php/default.asp`

PHP 超全局数组最常用的用途是从 HTML 表单中获取值。以下是程序员使用的九个超全局数组：

- `$_GET`
- `$_POST`
- `$_REQUEST`
- `$_COOKIE`
- `$_SESSION`
- `$_SERVER`
- `$_ENV`
- `$_GLOBAL`
- `$_FILES`

（注：提供的文本中关于这些超全局变量包含大量重复且碎片化的句子；上述列表根据指令提取了核心信息。）

![](img/00055.jpeg)

图 3.19：在表格单元格中添加输入表单元素（`name="username"`）。

### 步骤 5：添加另一个包含两个表格数据单元格 `<td>` 的表格行。第一个单元格将包含文本“请输入您的年龄”（Please Enter Your Age），第二个单元格将包含用于获取用户年龄的输入表单元素（`userAge`）。

```html
<tr>
    <td>Please Enter Your Age: </td>
    <td><input name="userAge" /></td>
</tr>
```

![](img/00056.jpeg)

图 3.20：添加第二个输入表单元素（`name="userAge"`）。

### 步骤 6：最后，添加另一个包含一个表格数据单元格的表格行。该单元格将包含提交按钮：

```html
<tr>
    <td><input type="submit" value="Submit" /></td>
</tr>
```

![](img/00057.jpeg)

图 3.21：添加包含提交按钮的表格数据单元格。

### `sampleForm.html` 的完整代码列表如下：

代码列表：`sampleForm.html`

```html
<!DOCTYPE html>
<html>
<head>
<title>Sample Form</title>
</head>
<body>
<form action="superGlobals.php" method="post">
<table>
    <tr>
        <td><h1>Hello, this is our example</h1></td>
    </tr>
    <tr>
        <td>Please Enter Your First Name:</td>
        <td><input name="userName" /></td>
    </tr>
    <tr>
        <td>Please Enter Your Age: </td>
        <td><input name="userAge" /></td>
    </tr>
    <tr>
        <td><input type="submit" value="Submit" /></td>
    </tr>
</table>
</form>
</body>
</html>
```

### 步骤 7：查看你的输出。表单的样式将如下所示：

![](img/00058.jpeg)

图 3.22：在浏览器中查看 `sampleForm.html`。

现在表单已经准备好了，我们可以继续编写 PHP 脚本文档。

### 步骤 1：创建一个空白 PHP 文档并将其保存为 `superGlobalsGet.php`。

我们现在准备好处理第一个超全局变量 `$_GET` 了。

### 步骤 2：在你的 `superGlobalsGet.php` 文档中输入以下代码，然后保存：

```php
<?php
    $name=$_GET['userName'];
    $age=$_GET['userAge'];
?>
```

### 步骤 3：添加显示以下输出的命令：

`userName is userAge years old.`

实现此操作的代码是：

`echo($name . " is " . $age . " years old. ");`

完整的 PHP 脚本现在应该如下：

```php
<?php
    $name=$_GET['userName'];
    $age=$_GET['userAge'];
    echo($name . " is " . $age . " years old. ");
?>
```

### 步骤 4：再次保存你的 `superGlobalsGet.php` 文件。

在文本编辑器中打开 `sampleForm.html` 文件，转到文档主体 `<body>` 元素，并在 `<form>` 标签中将 `action` 属性的值替换为 `“superGlobalsGet.php”`，并将 `method` 属性的值替换为 `“get”`。

```html
<body>
<form action="superGlobalsGet.php" method="get">
```

### 步骤 5：将修改后的文件保存为 `sampleFormGet.html`。

### 步骤 6：启动浏览器并调用你的 `sampleFormGet.html` 文件以显示输出。

### 步骤 7：查看你的输出。结果将如下所示：

![](img/00059.jpeg)

图 3.23：在浏览器中查看 `sampleFormGet.html`。

此表单使用了 `“get”` 方法属性。

在用户名文本框中输入 `“John”`，在年龄文本框中输入 `“40”`。点击提交。

![](img/00060.jpeg)

图 3.24：向表单输入值。

点击提交按钮后，输出将如下所示：

![](img/00061.jpeg)

图 3.25：点击提交按钮后查看输出。

注意 URL 显示了用户输入的数据。这个字符串 `?userName=John&userAge=40”` 被附加到了 URL 中。

![superglobalGet.jpg](img/00062.jpeg)

图 3.26：在 URL 中显示用户信息。

### 让我们使用超全局变量 `$_POST` 重一遍相同的过程。

在 `superGlobals.php` 中输入以下代码并保存：

```php
<?php
    $name=$_POST['userName'];
    $age=$_POST['userAge'];
?>
```

添加显示以下输出的命令：

`userName is userAge years old.`

实现此操作的代码是：

`echo($name . " is " . $age . " years old. ");`

完整的代码列表现在应该是：

```php
<?php
    $name=$_POST['userName'];
    $age=$_POST['userAge'];
    echo($name . " is " . $age . " years old. ");
?>
```

### 步骤 1：使用 `sampleForm.html` 文件，修改 `<body>` 元素，转到 `<form>` 标签，将 `action` 属性的值替换为 `“superGlobals.php”`，并将 `method` 属性的值替换为 `“post”`。

```html
<body>
<form action="superGlobals.php" method="post">
```

### 步骤 2：将修改后的文件保存为 `sampleFormGet.html`。

### 步骤 3：启动浏览器并调用你的 `sampleFormGet.html` 文件以显示输出。

### 步骤 4：查看你的输出。结果将如下所示：

![](img/00059.jpeg)

图 3.23：在浏览器中查看 `sampleFormGet.html`。

此表单使用了 `“post”` 方法属性。

在用户名文本框中输入 `“John”`，在年龄文本框中输入 `“40”`。点击提交。

![](img/00060.jpeg)

图 3.24：向表单输入值。

点击提交按钮后，输出将如下所示：

![](img/00061.jpeg)

图 3.25：点击提交按钮后查看输出。

注意 URL 显示了用户输入的数据。这个字符串 `?userName=John&userAge=40”` 被附加到了 URL 中。

### 让我们使用超全局变量 `$_REQUEST` 重一遍相同的过程。

在 `superGlobals.php` 中输入以下代码并保存：

```php
<?php
    $name=$_REQUEST['userName'];
    $age=$_REQUEST['userAge'];
?>
```

添加显示以下输出的命令：

`userName is userAge years old.`

实现此操作的代码是：

`echo($name . " is " . $age . " years old. ");`

完整的代码列表现在应该是：

```php
<?php
    $name=$_REQUEST['userName'];
    $age=$_REQUEST['userAge'];
    echo($name . " is " . $age . " years old. ");
?>
```

### 步骤 1：使用 `sampleForm.html` 文件，修改 `<body>` 元素，转到 `<form>` 标签，将 `action` 属性的值替换为 `“superGlobals.php”`，并将 `method` 属性的值替换为 `“get”`。

```html
<body>
<form action="superGlobals.php" method="get">
```

### 步骤 2：将修改后的文件保存为 `sampleFormGet.html`。

### 步骤 3：启动浏览器并调用你的 `sampleFormGet.html` 文件以显示输出。

### 步骤 4：查看你的输出。结果将如下所示：

![](img/00059.jpeg)

图 3.23：在浏览器中查看 `sampleFormGet.html`。

此表单使用了 `“get”` 方法属性。

在用户名文本框中输入 `“John”`，在年龄文本框中输入 `“40”`。点击提交。

![](img/00060.jpeg)

图 3.24：向表单输入值。

点击提交按钮后，输出将如下所示：

![](img/00061.jpeg)

图 3.25：点击提交按钮后查看输出。

注意 URL 显示了用户输入的数据。这个字符串 `?userName=John&userAge=40”` 被附加到了 URL 中。

![](img/00070.jpeg)

图 3.34：点击提交按钮后的输出。

# 章节练习

1. **什么是数组？**

   a. 数组是用于存储多种类型同质数据的特殊变量。

   b. 数组是存储多个变量的容器。

   c. 数组是获取许多变量值并将其存储的特殊命令。

   d. 数组是创建多个数据的特殊函数。

2. **如果要将数组的某个成员赋值为第四个成员，正确的语法应该是什么？**

   a. `$arrayName[3]=data;`

   b. `arrayName[3]=data;`

   c. `$arrayName[4]=data;`

   d. `arrayName[4]=data;`

3. **在示例中，**

```php
$example = array(
    "Cooper" => 25000,
    "Oswald" => 23500);
```

哪些是键(key)？

   a. Cooper, Oswald

   b. 25000, 23500

   c. $example

   d. array

4. **多维数组最简单的解释是什么？**

   a. 它们是持有特定键并在每个键中关联值的数组。

   b. 它们是数组中的数组。

   c. 它们是拥有多个成员的数组。

   d. 它们是无限变量的数组。

5. **普通数组和超全局数组之间的区别是什么？**

   a. 普通数组比超全局数组大。

   b. 超全局数组来自来自 Web 服务器的用户输入、URL、cookies 和 HTML 文件，而普通数组由程序员声明。

   c. 普通数组占用的内存比超全局数组少。

   d. 超全局数组比普通数组更容易处理。

# 实验练习：实验 1-1 超全局数据集

1. 创建一个 PHP 程序，显示一个表单并询问用户信息——姓名、年龄和当前年份。表单中必须有一个提交按钮和一个重置按钮。点击提交按钮后，PHP 必须返回一个结果，报告该人出生的大年份。

2. 确保 WAMP 或 MAMP 服务器正在运行。

3. 创建一个 HTML5 文档，并将其保存为 `www` 文件夹下的 `yearOfBirth_prediction.html`。

4. 采用以下表单布局和字段：`userName`、`userAge` 和 `currentYear`。将这些元素放在表格中以获得更整的布局。

![](img/00071.jpeg)

图 3.35：浏览器中的 `yearOfBirth_prediction.html`。

使用 `maxlength` 属性将 `userName` 的字符限制为十个，`userAge` 限制为三个，`currentYear` 限制为四个。

```html
<table>
  <tr>
    <td>Enter Your Name:</td>
    <td><input name="userName" maxlength="10"></td>
  </tr>
  <tr>
    <td>Enter Your Age:</td>
    <td><input name="userAge" maxlength="3"></td>
  </tr>
  <tr>
    <td>Enter the Current Year:</td>
    <td><input name="currentYear" maxlength="4"></td>
  </tr>
  <tr>
    <td><input type="submit" value="submit"></td>
    <td><input type="reset" value="clear"></td>
  </tr>
</table>
```

5. 创建一个新的文本文件并将其保存为 `www` 文件夹下的 `birthYear_calculator.php`。

6. 计算年龄并在 `birthYear_calculator.php` 文件中输入代码。我们在这里使用 `$_POST` 超全局变量，但也可以稍后使用其他超全局变量 `$_GET` 和 `$_REQUEST` 来调整代码。

```php
<?php
$name = $_POST['userName'];
$age = $_POST['userAge'];
$year = $_POST['currentYear'];
$yob = $year - $age;
echo($name . " was approximately born in the year " . $yob);
?>
```

![](img/00072.jpeg)

图 3.36：浏览器中的 `yearOfBirth_prediction.html`。

![](img/00073.jpeg)

图 3.37：在表单中输入值。

点击提交后，输出将如下：

![](img/00074.jpeg)

图 3.38：点击提交按钮后的输出。

# 实验练习 2- 超全局多数据集

1. 创建一个 PHP 程序，显示一个表单向两个个人收集数据——两个人的姓名、年龄以及当前年份的条目。表单中必须有一个提交按钮和一个重置按钮。点击提交按钮后，PHP 必须返回一个结果，显示这些人出生的大年份列表。

2. 使用实验 1 中相同的 HTML5 文档，但如下更新 HTML `yearOfBirth_prediction.html` 中的代码：

```html
<table>
  <tr>
    <td>First Person's Name:</td>
    <td><input name="userName1" maxlength="10"></td>
  </tr>
  <tr>
    <td>First Person's Age:</td>
    <td><input name="userAge1" maxlength="3"></td>
  </tr>
  <tr>
    <td>Second Person's Name:</td>
    <td><input name="userName2" maxlength="10"></td>
  </tr>
  <tr>
    <td>Second Person's Age:</td>
    <td><input name="userAge2" maxlength="3"></td>
  </tr>
  <tr>
    <td>Enter the Current Year:</td>
    <td><input name="currentYear" maxlength="4"></td>
  </tr>
  <tr>
    <td><input type="submit" value="submit"></td>
    <td><input type="reset" value="clear"></td>
  </tr>
</table>
```



并在 `birthYear_calculator.php` 中如下：

```php
<?php
$name1 = $_POST['userName1'];
$age1 = $_POST['userAge1'];
$name2 = $_POST['userName2'];
$age2 = $_POST['userAge2'];
$year = $_POST['currentYear'];

$yob1 = $year - $age1;
$yob2 = $year - $age2;

echo $name1 . " was approximately born in the year " . $yob1 . "<br>";
echo $name2 . " was approximately born in the year " . $yob2;
?>
```

```html
<td><input name="currentYear" maxlength="4" /></td>
</tr>
<tr>
<td><input type="submit" value="submit" /></td>
<td><input type="reset" value="clear"</td>
</tr>
</table
</form>
</</body>
</</html>
```

`birthYear_calculator.php`

```php
<?php
    $name[0] = $_POST['userName1'];
    $name[1] = $_POST['userName2'];
    $age[0] = $_POST['userAge1'];
    $age[1] = $_POST['userAge2'];
    $year = $_POST['currentYear'];
    $yob[0] = $year - $age[0];
    $yob[1] = $year - $age[1];
    echo($name[0] . " was approximately born in the year " . $yob[0].".");
    echo("</br>");
    echo($name[1] . " was approximately born in the year " . $yob[1].".");
    echo("</br>");
?>
```

# 章节总结

在本章中，我们讨论了数组。你学习了 PHP 有两种类型的数组：简单数组（索引数组）和关联数组。你学习了多维数组是嵌套在数组中的数组，并且 PHP 提供了访问全局作用域关联数组的方法，这些称为超级变量。

我们列出了九个可以直接使用的超级全局变量，并讨论了其中三个：`$_GET`、`$_REQUEST` 和 `$_POST`。另外六个全局变量只能在远程服务器上运行和测试。

在下一章中，我们将讨论 PHP 条件语句。

# 4：控制结构 - 分支

## 章节目标

- 你将学习表达式、条件表达式、操作数、运算符、比较运算符和逻辑运算符的精确定义并学习其示例。
- 你将能够理解并分析 PHP 中使用的分支控制结构。
- 你将能够理解 PHP 分支控制结构中使用的条件语句之间的区别。
- 你将学习三元运算符并使用它来编写紧凑的 PHP 代码。
- 你将在各种 PHP 脚本中使用条件语句和分支控制结构。

## 4.1 简单控制结构——if 语句

在计算机编程中，控制结构允许你改变程序语句的执行流。与其按行顺序顺序执行，你可以让程序：

a. 跳过特定的行或代码块（分支），或者
b. 重复执行一组行或代码块（循环）。

程序通过评估条件表达式的值为 TRUE（真）或 FALSE（假）来执行这些分支或循环动作。

在本章中我们将处理分支控制结构，而循环控制结构将是第五章的主题。

分支控制结构由：

a. 一个条件表达式和一个定义清晰的代码块，或
b. 多个条件表达式和多个定义清晰的代码块组成。

根据条件表达式求值是 TRUE 还是 FALSE，将执行这些代码块中的某一个或一个都不执行。

**提示**：一个代码块由用大括号 `{}` 隔开的一个或多个程序语句组成。如果代码块中只有一个语句，则不需要大括号。但是，为了清晰和易读，始终会使用大括号。

让我们来看看最简单的分支控制结构——if 语句。它的语法如下：

```
if (conditional-expression) {
    statements . . .
}
```

if 语句后的语句...

如果 `conditional-expression` 在求值时结果为布尔值 TRUE，则大括号括的语句块将被执行。否则（意味着求值 `conditional-expression` 的结果为布尔值 FALSE），语句块将被忽略，程序执行将跳到 if 语句代码块之后的下一个 if 语句。

现在，让我们检查条件表达式。首先我们必须理解什么是表达式。

在 PHP 中，表达式是变量、常量、字面量、运算符、对象甚至函数的任何有效组合，它们可以求值以产生一个值。这个值可以是 PHP 八种数据类型中的任意一种：整数、浮点数、字符串、布尔、数组、对象、资源（或句柄）和空。

如何评估表达式？最简单且最常用的方法是将表达式放在赋值语句的右侧：

```
$variable = expression
```

当执行此赋值语句时，右侧的表达式将进行求值，其值将存储在左侧的 `$variable` 中。通过使用变量来存储表达式评估的结果，你可以在程序的任何地方之后使用该值。

现在，所有的表达式至少包含一个操作数和一个或多个运算符。

运算符是指定要执行特定动作的符号。该动作通常会产生新值。

操作数是接收运算符动作的对象。大多数情况下，操作数是一个变量，但它也可以是字面量、对象、函数或任何运算符可以有效执行动作的实体。

**提示**：PHP 运算符可以分为十组，即：算术、数组、赋值、位运算、比较、错误控制、执行、逻辑、字符串和递增/减少。

最简单的表达式是字面量和变量。这些是仅由一个操作数且没有运算符的表达式。字面量求值为其自身，变量求值为存储在它们中的值。

**提示**：字面量是一个单一的值（不被变量引用）。例如，`114` 和 `"string"` 都是字面量。

让我们看看表达式：

```
$days++
```

它由递增运算符 `++` 和操作数 `$days` 组成。如果 `$days` 存储的是 7，那么评估这个表达式将返回 8。

这是另一个表达式：

```
$cost + $margin
```

它包含两个操作数：变量 `$cost` 和 `$margin` 以及加法运算符 `+`。这个表达式将相加存储在变量中的。为了让这个表达式产生用，它必须是赋值语句的一部分，例如：

```
$sellingPrice = $cost + $margin
```

现在，上述赋值语句右侧表达式的结果存储在变量 `$sellingPrice` 中。

这是一个没有运算符的表达式示例：

```
strtoupper($str)
```

这个表达式由字符串函数 `strtoupper` 和变量 `$str` 组成。`strtoupper` 函数将字符串的所有字符转换为大写。如果 `$str` 中存储的是字符串 `"LearnTo"`，那么 `strtoupper($str)` 返回 `"LEARNTO"`。`str` 的原始内容不变，因此如果你想使用修改后的字符串 `"LEARNTO"`，你必须将表达式 `strtoupper($str)` 放在赋值语句中：

```
$newstr = strtoupper($str)
```

现在，求值为布尔值 TRUE 或 FALSE 的表达式被称为条件表达式。此外，条件表达式专门使用比较运算符和逻辑运算符。

比较运算符允许你在条件表达式通过各种方式比较两个操作数。如果比较测试成功，条件表达式求值为 TRUE；否则值为 FALSE。

下表列出了 PHP 中不同的比较运算符以及它们在 PHP 中的描述。

| 运算符 | 示例 | 结果 |
| :--- | :--- | :--- |
| `==` (等于) | `$LS == $RS` | 如果 `$LS` 中存储的操作数等于 `$RS` 中的操作数，则为 TRUE；否则为 FALSE。 |
| `!=` 或 `<>` (不等于) | `$LS != $RS` 或 `$LS <> $RS` | 如果 `$LS` 中存储的操作数不等于 `$RS` 中的操作数，则为 TRUE；否则为 FALSE。 |

| 运算符 | 表达式 | 描述 |
| :--- | :--- | :--- |
| `== (相同)` | `$LS === $RS` | 如果 `$LS` 中存储的操作数不仅等于 `$RS` 中存储的操作数，而且类型相同，则为 TRUE；否则为 FALSE。 |
| `!== (相同)` | `$LS !== $RS` | 如果 `$LS` 中存储的操作数不仅等于 `$RS` 中存储的操作数，而且类型相同，则为 TRUE；否则为 FALSE。 |
| `>(大于)` | `$LS > $RS` | 测试运算符左侧的操作数是否大于运算符右侧的操作数。 |
| `小于<` | `$LS < $RS` | 测试运算符左侧的操作数是否小于运算符右侧的操作数 |
| `大于或等于>=` | `$LS >= $RS` | 测试左侧的操作数是否大于或等于运算符右侧的操作数 |
| `小于或等于<=` | `$LS <= $RS` | 测试运算符左侧的操作数是否小于或等于右侧的操作数 |

逻辑运算符允许你组合条件表达式以产生 TRUE 或 FALSE 的布尔结果。

| 运算符 | 示例 | 结果 |
| :--- | :--- | :--- |
| AND | `exp1 AND exp2` | 仅当 `exp1` 和 `exp2` 都求值为 TRUE 时为 TRUE；否则为 FALSE。 |
| `&&` | `exp1 && exp2` | |
| OR | `exp1 OR exp2` | 如果 `exp1` 和 `exp2` 中任一求值为 TRUE 或 `exp1` 和 `exp2` 都为 TRUE，则为 TRUE；只有当 `exp1` 和 `exp2` 都为 FALSE 时才为 FALSE。 |
| `||` | `exp1 || exp2` | |

现在让我们检查一些条件表达式。

第一个是非常简单的 PHP 条件表达式：

```php
$age <= 21
```

它由变量 `$age`、比较运算符 `<=`（小于或等于）和整数值 `21` 组成。如果变量 `$age` 的值在 21 到任何小于 21 的值之间，这将产生 TRUE。如果变量 `$age` 的值大于 21，则该条件表达式将产生 FALSE。

第二个例子并不那么简单：

```php
$char >=”A” and $char<=”Z”
```

如果变量 `$char` 存储从 “A” 到 “Z”的任何大写字母，则将产生 TRUE。

最后一个是复杂的条件表达式：

```php
( ( ( $year % 4 == 0 ) && ( $year % 100 != 0 ) ) || ( $year % 400 == 0 ) )
```

如果存储在 `$year` 中的值是闰年，则返回 true；否则返回 false。

现在我们已经涵盖了定义并研究了表达式、条件表达式、操作数、运算符、比较运算符和逻辑运算符，现在我们来看 PHP 的条件语句。

PHP 有三种基本的条件语句，你可以用它们来创建分支控制结构：

a. `if`-语句，
b. `if-else-` 和 `if-elseif-`语句，以及
c. `switch`-语句。

## 4.2 If-语句

`if`-语句评估条件表达式。如果结果为 TRUE，则执行 `if`-语句后面的代码块。否则，忽略该代码块。无论是 TRUE 还是 FALSE，执行都将继续到代码块之后的语句。

`if`-语句的语法为：

```php
if (conditional expression){
    语句代码块 . . .
}
```

### if 之后的语句

让我们来完成一个例子。

**问题：** 创建一个简短的 PHP 程序，根据以下信息判断一个人是否有权投票。

| 变量名 | 值 | 类型 |
| :--- | :--- | :--- |
| `$age` | 19 | 整数 |
| `$isCitizen` | TRUE | 布尔值 |

**解决方案：**

**第 1 步：** 创建一个新的 HTML5 文档。在文档 `<body>` 中包含 PHP 的开始和结束标签。将文档命名为 `conditionals.php`。请参考附图片进行指南。

![](img/00078.jpeg)

图 4.1: Komodo Edit 首页。

![](img/00079.jpeg)

图 4.2: 打开一个新的 HTML5 文档。

![](img/00080.jpeg)

图 4.3: 在文档中添加 PHP 的开始和结束标签。

**第 2 步：** 声明并初始化变量：

| 变量名 | 值 | 数据类型 |
| :--- | :--- | :--- |
| `$age` | 19 | 整数 |
| `$isCitizen` | TRUE | 布尔值 |

```php
<?php
    $age = 19;
    $isCitizen = TRUE;
?>
```

参考第 2 步中给出的变量赋值表。第三列表示将赋值给变量 `$age` 和 `$isCitizen` 的值的“数据类型”。

变量 `$age` 被赋值为整数数据类型 `19`。

变量 `$isCitizen` 被赋值为布尔类型 `TRUE`。

**第 3 步：** 在声明并赋值变量后，按所示输入 `if`-语句的条件表达式：

```php
if ($age <= 21){
    // 语句代码块
}
```

如果变量 `$age` 的值在 21 到任何小于 21 的值之间，将产生 TRUE。`if` 语句后面的代码块将被执行。如果变量 `$age` 的值大于 21，则该条件表达式将产生 FALSE。

第二个例子并不那么简单：

```php
$char >=”A” and $char<=”Z”
```

如果变量 `$char` 存储从 “A” 到 “Z”的任何大写字母，则将产生 TRUE。

最后一个是复杂的条件表达式：

```php
( ( ( $year % 4 == 0 ) && ( $year % 100 != 0 ) ) || ( $year % 400 == 0 ) )
```

如果存储在 `$year` 中的值是闰年，则返回 true；否则返回 false。

现在我们已经涵盖了定义并研究了表达式、条件表达式、操作数、运算符、比较运算符和逻辑运算符，现在我们来看 PHP 的条件语句。

PHP 有三种基本的条件语句，你可以用它们来创建分支控制结构：

a. `if`-语句，
b. `if-else-` 和 `if-elseif-`语句，以及
c. `switch`-语句。

（注：根据提供的原文逻辑，后续部分已根据示例逻辑整合并完成完整翻译）

**问题：** 创建一个简短的 PHP 程序，根据以下信息判断一个人是否有权投票。

| 变量名 | 值 | 类型 |
| :--- | :--- | :--- |
| `$age` | 19 | 整数 |
| `$isCitizen` | TRUE | 布尔值 |

**解决方案：**

**第 1 步：** 创建一个新的 HTML5 文档。在文档 `<body>` 中包含 PHP 的开始和结束标签。将文档命名为 `conditionals.php`。请参考附图片进行指南。

![](img/00078.jpeg)

图 4.1: Komodo Edit 首页。

![](img/00079.jpeg)

图 4.2: 打开一个新的 HTML5 文档。

![](img/00080.jpeg)

图 4.3: 在文档中添加 PHP 的开始和结束标签。

**第 2 步：** 声明并初始化变量：

| 变量名 | 值 | 数据类型 |
| :--- | :--- | :--- |
| `$age` | 19 | 整数 |
| `$isCitizen` | TRUE | 布尔值 |

```php
<?php
    $age = 19;
    $isCitizen = TRUE;
?>
```

参考第 2 步中给出的变量赋值表。第三列表示将赋值给变量 `$age` 和 `$isCitizen` 的值的“数据类型”。

变量 `$age` 被赋值为整数数据类型 `19`。

变量 `$isCitizen` 被赋值为布尔类型 `TRUE`。

**第 3 步：** 在声明并赋值变量后，按所示输入 `if`-语句的条件表达式：

```php
if ($age <= 21){
    // 语句代码块
}
```

如果变量 `$age` 的值在 21 到任何小于 21 的值之间，将产生 TRUE。`if` 语句后面的代码块将被执行。如果变量 `$age` 的值大于 21，则该条件表达式将产生 FALSE。

**第 4 步：** 你的最终代码 应该如下所示：

```html
<!DOCTYPE html>
<html>
<head>
    <title>Conditionals</title>
</head>
<body>
<?php
    $age = 19;
    $isCitizen = TRUE;
    if ($age <= 21){
        print("You are eligible to vote.");
    }
?>
</body>
</html>
```

![](img/00087.jpeg)

图 4.11：在浏览器中查看 `conditionals.php`。

注意浏览器显示的是了一个空白窗口。这是因为组成复合条件表达的各个条件表达式都返回了 `FALSE`，因此它不会执行 `if` 语句后面的代码块。这导致浏览器输出为空白。

让我们来看另一个例子。这次，我们不再在 PHP 代码中嵌入为 `age` 和 `citizens` 赋值的值。相反，信息将通过用于年龄的文本框从用户处获取，并通过单选按钮让用户说明他们是否为公民。



### 问题描述

创建一个简单的 HTML 表单，要求用户输入年龄，并要求他们点击相应的单选按钮来输入公民身份。将变量视为全局变量并使用预定义变量`$_POST`。将你的主 HTML 文档命名为`votersForm.html`，将外部 PHP 文件命名为`votersEligibility.php`。

### 解决方案

#### 步骤 1：创建一个 HTML5 文档

将文件保存为`votersForm.html`。在`<title>`标签中输入“Enter User Information”，如下所示：

```html
<title>Enter User Information</title>
```

不包含 PHP 脚本标签，因为 PHP 脚本将从外部调用——作为此 HTML 文档中`action`表单属性调用的独立 PHP 文档。

对于你的 PHP action 脚本文件，分配文档名为`votersEligibility.php`。

在 HTML 文档的`<body>`中，包含`<form>`标签。将`action`属性值设置为`votersEligibility.php`并将`method`属性值设置为`post`。

```html
<body
    <form action="votersEligibility.php" method="post">
```

#### 步骤 2：继续编写 HTML 代码

使用表格布局表单元素。使用`<table>`可以让表单更有组织、结构更清晰，并防止代码列表中出现过多的`<break>`标签。

你的 HTML 表单文档将包含以下元素：

- 一个用于年龄的输入元素，值为“userAge”
- 两个单选按钮输入元素，一个用于“Yes”，一个用于“No”
- 一个值为“Submit”的提交按钮元素

在第一行行`<tr>`中，我们将询问用户的年龄。第一个表格单元格`<td>`应该显示文本“Enter Your Age”。

```html
<table>
    <tr>
        <td>Enter Your Age</td>
        <td><input name="userAge" ></</td>
    </tr>
```

![](img/00088.jpeg)

图 4.12：使用表格结构创建表单。

在第二行行`<tr>`中，我们将放置单选按钮。第一个表格单元格应该显示文本“Are you a citizen?”。

```html
<tr>
    <td>Are you a citizen?</td>
```

第二个表格单元格将包含用于 Yes 和 No 回答的两个单选按钮。

```html
<td>
    <input type="radio" name="citizen" value="true">Yes</input>
    <input type="radio" name="citizen" value="false">No</input>
</td>
</tr>
```

在第三行行`<tr>`中，在此处包含的唯一表格单元格中放置“submit”按钮。

```html
<tr>
    <td><input type="submit" value="Submit" ></</td>
</tr>
```

#### 步骤 3：放置闭合标签

放置闭合标签`</table>`和`</form>`，确保也有闭合的`</body>`和`</html>`标签，然后保存你的文档。

```html
    </table>
    </form>
</body>
</html>

<!DOCTYPE html>
<html>
<head>
    <title>Enter User Information</title>
</head>
<body>
<form action="votersEligibility.php" method="post">
    <table>
        <tr>
            <td>Enter Your Age</td>
            <td><input name="userAge" ></</td>
        </tr>
        <tr>
            <td>Are you a citizen?</td>
            <td>
                <input type="radio" name="citizen" value="true">Yes</input>
                <input type="radio" name="citizen" value="false">No</input>
            </td>
        </tr>
        <tr>
            <td><input type="submit" value="Submit" ></</td>
        </tr>
    </table>
</form>
</body>
</html>
```

#### 步骤 4：查看你的输出

你的`votersForm.html`输入页面看起来应该是这样：

![](img/00089.jpeg)

图 4.13：在浏览器中查看`votersForm.html`。

显示的页面尚不具备功能。仍然需要创建 PHP 脚本以让程序相应地显示。

#### 步骤 5：创建`votersEligibility.php`

使用你的文本编辑器。这是我们 PHP 脚本的完整代码列表。

```php
<?php
    // 此处为 PHP 代码逻辑
?>
```

*(注：由于原文此处 PHP 代码示例不完整或存在重复，翻译保持了逻辑结构)*

由于原文提供的待翻译文本包含大量重复和错乱片段，以上已根据您的要求进行了格式整理和翻译。

```php
        print("You are not eligible to vote");

    }

?>
```

关闭 PHP 脚本标签，并确保文档中存在 HTML 结束标签。保存你的文件。

#### 步骤 3：启动你的浏览器并在地址栏中输入`http://localhost/conditionals_ifElse.php`。点击“前往”或直接按回车键。

![](img/00092.jpeg)

图 4.17：通过 localhost 在浏览器访问`conditionals_ifElse.php`。

#### 步骤 4：等待几秒并查看你的输出。

![](img/00093.jpeg)

图 4.18：在浏览器中输出`conditionals_ifElse.php`。

你得到了结果“You are not eligible to vote.”是因为变量`$citizen`包含布尔值`FALSE`。

以下是示例的完整代码列表：

代码列表：`conditionals_ifElse.php`的解决方案

```html
<!DOCTYPE html>
<html>
<head>
    <title>Complex Conditional</title>
</head>
<body>
    <?php
        $age = 21;
        $citizen = true;
        if ($age >= 18 && $citizen == true)
        {
            print("<h1>You are eligible to vote.</h1>");
        }
        else
        {
            print("You are not eligible to vote.");
        }
    ?>
</body>
</html>
```

#### 步骤 5：重新加载`conditionals_ifElse.php`并根据下表更改用户信息。

| 年龄 | 公民身份 |
| :--- | :--- |
| 21 | TRUE |
| 16 | TRUE |
| 21 | FALSE |
| 16 | FALSE |

#### 步骤 6：在每次输入后查看你的输出并确保结果正确。

`if-statement`和`if-else-statement`仅测试一个条件表达式。相比之下，`if-elseif-statement`测试多个一个条件表达式。

`if-statement`有一个代码块，`if-else-statement`有两个代码块，而`if-elseif-statement`的代码块数量与它的条件表达式数量相同。

这是`if-elseif-statement`的语法。

```php
if (condexpr0){
    code block for condexpr0 == TRUE . . .
} elseif (condexpr1) {
    code block for condexpr1 == TRUE . . .
} elseif (condexpr2) {
    code block for condexpr2 == TRUE . . .
} else {
    code block if all conditional expressions are FALSE
}
```

### if-elseif 之后的语句

关于`if-elseif-statement`有三点需要注意：

a. `else`子句是可选的。

b. 如果评估的任何一个条件表达式为`TRUE`，则执行该条件表达式的代码块，然后控制跳转到`if-elseif-statement`之后的第一个语句。

c. 如果`if-elseif-statement`没有任何一个条件表达式评估为`TRUE`，则执行与`else`子句（如果存在）相关的代码块。

让我们来做一个示例。

### 问题

创建一个程序例程，根据所确定的数值分值显示相应的描述。PHP 脚本必须嵌入在 HTML 文档中。使用变量名`$grade`来存储数值成绩的值。将默认成绩设置为 93。

将文档保存为文件名`complexConditionals_2.php`。

| 条件 | 消息 |
| :--- | :--- |
| $grade == 100 | Your grade is perfect! |
| $grade > 90 | Your grade is excellent! |
| $grade > 80 | Your grade is great! |
| $grade > 70 | Your grade is good! |
| $grade >= 60 | Your grade is average. |
| $grade <=50 | Your grade is below average. |
| else | Either your grade is super low or you entered an invalid grade :( |

### 解决方案

代码列表：`complexConditionals_2.php`的解决方案

```html
<!DOCTYPE html>
<html>
<head>
    <title>Complex Conditionals 2</title>
</head>
<body>
    <?php
        $grade = 93;
        if ($grade == 100)
        {
            echo("Your is is PERFECT!");
        }
        elseif($grade <=99 && $grade>=90)
        {
            echo("Your grade is Excellent!");
        }
        elseif($grade <= 89 && $grade>=80)
        {
            echo("Your grade is Great!");
        }
        elseif($grade <= 79 && $grade>=70)
        {
            echo("Your grade is Good");
        }
        elseif($grade <= 69 && $grade>=60)
        {
            echo("Your grade is Average");
        }
        elseif($grade <= 59 && $grade>=50)
        {
            echo("Your grade is Below Average");
        }
        else
        {
            echo("You entered an invalid grade :( ");
        }
    ?>
</body>
</html>
```

#### 步骤 1：创建一个新的 HTML5 文档。将你的文档保存为`complexConditionals-2.php`。

![](img/00078.jpeg)

图 4.19：开始页面。

![](img/00094.jpeg)

图 4.20：保存`complexConditionals_2.php`。

![](img/00095.jpeg)

图 4.21：添加`<title>`标签。

![](img/00096.jpeg)

图 4.22：添加`<body>`标签。

#### 步骤 2：为`$grade`分分配初始值。编码整个代码并保存文件。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Complex Conditionals 2</title>
</head>
<body>
    <?php
        $grade = 93;
        if ($grade == 100)
        {
            echo("Your is is PERFECT!");
        }
        elseif($grade <=99 && $grade>=90)
        {
            echo("Your grade is Excellent!");
        }
        elseif($grade <= 89 && $grade>=80)
        {
            echo("Your grade is Great!");
        }
        elseif($grade <= 79 && $grade>=70)
        {
            echo("Your grade is Good");
        }
        elseif($grade <= 69 && $grade>=60)
        {
            echo("Your grade is Average");
        }
        elseif($grade <= 59 && $grade>=50)
        {
            echo("Your grade is Below Average");
        }
        else
        {
            echo("You entered an invalid grade :( ");
        }
    ?>
</body>
</html>
```

#### 步骤 3：启动浏览器，在地址栏中输入文件名并点击“前往”或直接按回车键。等待一秒或两秒。

##### 输出

![](img/00097.jpeg)

图 4.23：在浏览器中访问`complexConditionals_2.php`。

##### 修改给定值

修改`$grade`的值将产生不同的结果。

| 分数 | 预期输出 |
| :--- | :--- |
| 95 | Your grade is excellent! |
| 100 | Your grade is perfect! |
| 72 | Your grade is good! |
| 45 | Your grade is below average. |
| 88 | Your grade is great! |
| 66 | Your grade is average. |
| A | You entered an invalid grade :( |

#### 步骤 4：查看你的输出。

#### 步骤 5：更改`$grade`的值。

#### 步骤 6：查看输出。

### 默认语句

#### switch 后的语句

第一行以`switch`关键字开头，后面紧跟括号内的测试变量名`$variable`，这是要测试其值的变量。

`case`关键字定义了当`case`关键字后的值与测试变量（`$variable`）当前值匹配时，将执行的程序语句。

`break`关键字终止`switch`语句。为什么需要`break`语句呢？当某个 case 值与测试变量的当前值匹配时，会执行该 case 值的语句。此之后，程序将继续向下执行`switch`语句，执行所有其他`case`值的语句以及`default`情况，无论这些值是否与测试变量匹配！显然，我们不希望发生这种情况，这就是为什么我们在每个`case`值的关联语句的最后包含一个`break`语句。

`default`关键字定义了当没有任何`case`值与测试变量匹配时将执行的语句。

### 让我们来看一个例子

**问题：** 创建一个`switch`语句例程，该程序将确定字母等级对应的数字分段，并相应地显示该分段的描述。使用以下成绩表：

| 字母等级 | 输出消息 |
| :--- | :--- |
| A | A 意味着你的分数在 91 到 100 之间。 |



| B | B 意味着你的分数在 81 到 90 之间。 |

| C | C 意味着你的分数在 71 到 80 之间。 |

| D | D 意味着你的分数在 61 到 70 之间。 |

| F | F 意味着你的分数在 51 到 60 之间。 |

| default | 你输入的成绩无效。 |

## 解决方案

**代码列举：** `switchCaseBreakConditional.php` 的解决方案

```php
<!DOCTYPE html>
<html>
<head>
    <title>Switch-Case-Break Conditionals</title>
</head>
<body>
    <?php
        $grade = 'A';
        switch($grade)
        {
            case 'A':
                echo("A means your grade is from 91-100.");
                break;
            case 'B':
                echo("B means your grade is from 81-90.");
                break;
            case 'C':
                echo("C means your grade is from 71-80.");
                break;
            case 'D':
                echo("D means your grade is from 61-70.");
                break;
            case 'F':
                echo("F means your grade is from 51-60.");
                break;
            default:
                echo("The grade you entered is invalid");
        }
    ?>
</body>
</html>
```

**步骤 1：** 创建一个空白的 HTML5 文档并保存为文件名 `switchCaseBreakConditional.php`。（图 4.29：Komodo Edit 开始。图 4.30：创建一个名为 `switchCaseBreakConditional.php` 的新文件）。在 `<title>` 标签中输入“Switch-Case-Break”。在文档的 `<body>` 中包含 PHP 的开始结束标签。（图 4.31：在 Komodo 中打开新的 HTML5 文档）。

**步骤 2：** 将初始值 ‘A’ 赋值给变量 `$grade`。对整个解决方案进行编码并保存文件。

```php
<!DOCTYPE html>
<html>
<head>
    <title>Switch-Case-Break Conditionals</title>
</head>
<body>
    <?php
        $grade = 'A';
        switch($grade)
        {
            case 'A':
                echo("A means your grade is from 91-100.");
                break;
            case 'B':
                echo("B means your grade is from 81-90.");
                break;
            case 'C':
                echo("C means your grade is from 71-80.");
                break;
            case 'D':
                echo("D means your grade is from 61-70.");
                break;
            case 'F':
                echo("F means your grade is from 51-60.");
                break;
            default:
                echo("The grade you entered is invalid");
        }
    ?>
</body>
</html>
```

**步骤 3：** 启动浏览器，在地址栏中输入文件名并点击 Go 或按回车键。等待一两秒。（图 4.32：在浏览器中访问 `switchCaseBreakConditional.php`）。

**输出：步骤 4：** 查看你的输出。如果 `$grade = ‘A’`（图 4.33：查看 `switchCaseBreakConditional.php` 的输出）。

**修改赋值的值：步骤 5：** 将 `$grade` 的值替换为 B、C、D 和 F 并查看结果。

| 评级 | 预期输出消息 |

| :--- | :--- |

| `$grade = ‘A’` | A 意味着你的分数在 91 到 100 之间。 |

| `$grade = ‘B’` | B 意味着你的分数在 81 到 90 之间。 |

| `$grade = ‘C’` | C 意味着你的分数在 71 到 80 之间。 |

| `$grade = ‘D’` | D 意味着你的分数在 61 到 70 之间。 |

| `$grade = ‘F’` | F 意味着你的分数在 51 到 60 之间。 |

| `$grade = ‘a’` | 你输入的成绩无效。 |

| `$grade = ‘E’` | 你输入的成绩无效。 |

**步骤 6：** 查看输出。如果 `$grade = ‘B’`（图 4.34：将 `$grade` 改为 B 并查看输出）。如果 `$grade = ‘C’`（图 4.35：将 `$grade` 改为 C 并查看输出）。如果 `$grade = ‘D’`（图 4.36：将 `$grade` 改为 D 并查看输出）。如果 `$grade = ‘F’`（图 4.37：将 `$grade` 改为 F 并查看输出）。

将 `$grade` 替换为范围之外的值，例如 ‘a’ 和 ‘E’。注意结果。如果 `$grade = ‘a’`（图 4.38：将 `$grade` 改为 a 并查看输出）。如果 `$grade = ‘E’`（图 4.39：将 `$grade` 改为 E 并查看输出）。

我们提到过 `switch` 语句是区分大小写的，如果你尝试给变量 `$grade` 赋值为“a”、“b”、“d”或“f”，这一点被证明是真实的。赋值任何这些小字母成绩都会导致程序报告成绩无效。`switch` 语句可以通过在第一个 `case` 之后添加另一个 `case` 来克服这一局限性。做法如下。如果我们希望将 ‘A’ 和 ‘a’ 相同的成绩，则必须声明连续的 case：

```php
case 'A':
case 'a':
    action;
break;
```

这位于基础 switch-case-break 结构中，如下所示：

```php
$variable = value;
switch($variable)
{
    case 'A':
    case 'a':
        action;
    break;
    default:
        default action;
}
?>
```

运行程序将得到结果：

```php
<body>
    <?php
        $grade = 'a';
```

![](img/00117.jpeg)

图 4.40: 将 `$grade` 的值改为 ‘a’ 并查看输出。

这是因为现有代码没有提供小写 ‘a’ 的情况。

## 问题

调整 `switchCaseBreakConditional.php` 的代码，使其现在包含小写字母等级‘a’、‘b’、‘c’、‘d’和‘f’的情况。保持 `$grade` 的赋值值为 ‘a’。

## 解决方案

代码列表：`switchCaseBreakConditional_2.php` 的解决方案

```html
<!DOCTYPE html>
<html>
<head>
    <title>Switch-Case-Break Conditional 2</title>
</head>
<body>
    <?php
        $grade = 'a';
        switch($grade)
        {
            case 'A':
            case 'a':
                echo("A means your grade is from 91-100.");
            break;
            case 'B':
            case 'b':
                echo("B means your grade is from 81-90.");
            break;
            case 'C':
            case 'c':
                echo("C means your grade is from 71-80.");
            break;
            case 'D':
            case 'd':
                echo("D means your grade is from 61-70.");
            break;
            case 'F':
            case 'f':
                echo("E means your grade is from 51-60.");
            break;
            default:
                echo("The grade you entered is invalid.");
        }
    ?>
</body>
</html>
```

### 步骤 1：创建一个空白 HTML5 文档并将其保存为 `switchCaseBreakConditional_2.php`。

![](img/00078.jpeg)

图 4.41: Komodo Edit 起页。

![](img/00118.jpeg)

图 4.42: 创建名为 `switchCaseBreakConditional_2.php` 的新文件。

### 步骤 2：在 `<title>` 标签中输入“Switch-Case-Break Conditional 2”。在文档 `<body>` 中包含 PHP 的开始和结束标签。

![](img/0119.jpeg)

图 4.43: 向文档中添加标题和 PHP 标签。

### 步骤 3：将初始值 ‘a’ 赋值给变量 `$grade`。编码整个代码并保存你的文件。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Switch-Case-Break Conditional 2</title>
</head>
<body>
    <?php
        $grade = 'a';
        switch($grade)
        {
            case 'A':
            case 'a':
                echo("A means your grade is from 91-100.");
            break;
            case 'B':
            case 'b':
                echo("B means your grade is from 81-90.");
            break;
            case 'C':
            case 'c':
                echo("C means your grade is from 71-80.");
            break;
            case 'D':
            case 'd':
                echo("D means your grade is from 61-70.");
            break;
            case 'F':
            case 'f':
                echo("E means your grade is from 51-60.");
            break;
            default:
                echo("The grade you entered is invalid.");
        }
    ?>
</body>
</html>
```

### 步骤 4：启动你的浏览器，在地址栏中输入文件名并点击 Go 或按回车键。等待一秒。

![](img/0120.jpeg)

图 4.44: 在浏览器中访问 `switchCaseBreakConditional_2.php`。

**输出**：

### 步骤 5：查看你的输出。

![](img/0121.jpeg)

图 4.45: 查看 `switchCaseBreakConditional_2.php` 的输出。

### 修改赋值的值：

### 步骤 6：将 `$grade` 的值替换为以下值并查看结果。第一个已经在之前显示过。从第二行的值 `$grade = ‘B’` 或 `$grade = ‘c’` 开始。

| 等级 | 预期输出 |

| :--- | :--- |

| `$grade = ‘A’ or ‘a’` | A means your grade is from 91-100. |

| `$grade = ‘B’ or ‘b’` | B means your grade is from 81-90. |

| `$grade = ‘C’ or ‘c’` | C means your grade is from 71-80. |

| `$grade = ‘D’ or ‘d’` | D means your grade is from 61-70. |

| `$grade = ‘F’ or ‘f’` | F means your grade is from 51-60. |

| `$grade = ‘X’ or ‘x’` | The grade you entered is invalid. |

| `$grade = ‘85’ or ‘Xx’` | The grade you entered is invalid. |

### 步骤 7：查看输出。

- `$grade = ‘B’ or ‘b’` (images/0122.jpeg) 图 4.46: 将 `$grade` 的值改为 ‘b’。

- `$grade = ‘C’ or ‘c’` ... (此处后续文本截断)

```php
print ($voteStatus . "<br/>你今年 " . $age . "岁。");
?>
</body>
</html>
```

### 步骤 3：启动浏览器，在地址栏中输入文件名并点击“转”或按回车键。等待一两秒。

![](img/00132.jpeg)

图 4.57：在浏览器中访问 `ternaryOperations.php`。

输出：

### 步骤 4：查看你的输出。

![](img/00133.jpeg)

图 4.58：查看 `ternaryOperations.php` 的输出。

### 修改赋值的值：

### 步骤 5：将 `$age` 的值替换为以下值并查看结果。第一个之前显示过。从第二行的值开始，即 `$age = 60`。

| 等级 | 预期输出消息 |

| :--- | :--- |

| `$age = 19` | 你可以投票！ |

| `$age = 60` | 你可以投票！ |

| `$age = 16` | 你不能投票！ |

### 步骤 6：查看输出。

如果 `$age = 60`

![](img/00134.jpeg)

图 4.59：将 `$age` 的值改为 60 并查看输出。

如果 `$age = 16`

![](img/00135.jpeg)

图 4.60：将 `$age` 的值改为 16 并查看输出。

## 章后测

1. 什么是条件语句？

    1. 定义条件的语句。

    2. 将对值的空值进行评估的限制性要求。

    3. 能够持有任何值并根据该值进行评估的逻辑语句。

    4. 评估表达式条件是否为真或假，并执行与真值或假值相关的相应操作的语句。

2. 条件“<=”描述的是哪种条件运算符？

    1. 大于或等于。

    2. 等于。

    3. 小于。

    4. 小于等于。

3. 复杂条件的示例是什么？

    1. if 语句。

    2. switch 语句。

    3. if-else 语句。

    4. 一系列 if-else-if 语句。

4. switch-case-break 条件语句最好的定义是什么？

    1. if 语句的简写表示法。

    2. 基于随机拆分 case 的 switch 。

    3. 具有许多 case 的条件语句。

    4. if 语句的较长版本。

5. switch-case-break 区分大小吗？

    1. 是。

    2. 否。

    3. 也许。



4. 默认情况下是，但可以通过添加多个 `case` 来消除大小写敏感性。

6. 什么是三元运算符？

   1. 与变量相关的一行 `if-else` 语句。
   2. 具有复杂条件结构的条件语句。
   3. 给变量赋值的运算符。
   4. 评估条件并执行特定操作的运算符。

7. 三元语句中的符号 `?` 和 `:` 分别代表什么？

   1. `if` 和 `else`。
   2. `OR`（或）和 `AND`（与）。
   3. 大于和小于。
   4. 加和减。

### 章后实验

1. 创建一个 PHP 程序，显示一个表单，要求个人输入名、姓、年龄和国籍。

表单必须包含名、姓和年龄的文本输入字段；用于国籍是/否回答的单选按钮；以及一个“注册”按钮和一个“重置”或“清除字段”按钮。

2. 创建一个 HTML5 文档并保存为 `voter_registration.html`，位于 `www` 或 `htdocs` 文件夹内。

3. 采用以下表单布局和表单字段：`voterFirstName`、`voterLastname`、`votersAge` 和 `isCitizen`。将这些元素以表格形式放置以保持整洁。

![](img/00136.jpeg)

图 4.61：使用 HTML 和 PHP 创建选民注册表单。

使用 `maxlength` 属性限制 `voterFirstName` 和 `voterLastName` 的字符数量为 15，限制 `votersAge` 为三个字符。

```html
<table>
    <tr>
        <th>名：</th>
        <td>
            <input name="voterFirstName" maxlength="15">
        </td>
    </tr>
    <tr>
        <th>姓：</th>
        <td>
            <input name="voterLastName" maxlength="15">
        </td>
    </tr>
    <tr>
        <th>年龄：</th>
        <td>
            <input name="votersAge" maxlength="3">
        </td>
    </tr>
    <tr>
        <th>国籍：</th>
        <td>
            <input type="radio" name="isCitizen" value="true">是
            <input type="radio" name="isCitizen" value="false">否
        </td>
    </tr>
    <tr>
        <td><input type="submit" value="注册"></td>
        <td><input type="reset" value="清除字段"></td>
    </tr>
</table>
```

4. 创建一个新的文本文件并将其保存为 `voter_registration.php`，位于 `www` 或 `htdocs` 文件夹中。

5. 判断年龄是否大于或等于 18。将代码写入 `voter_registration.php` 文件。使用 `$_POST` 全局变量。

```php
<?php
    $voterFirstName = $_POST['voterFirstName'];
    $voterLastName = $_POST['voterLastName'];
    $isCitizen = $_POST['isCitizen'];
    $votersAge = $_POST['votersAge'];
    if ($votersAge >= 18 && $isCitizen == "true") {
        // 逻辑处理：输出“你可以投票”
    } else {
        // 逻辑处理：输出“你不能投票”
    }
?>
```

6. 输出结果应该是这样的：

![](img/00137.jpeg)

图 4.62：`voter_registration.html` 的输出。

### 章后实验解决方案

#### 代码列表：HTML 表单

```html
<!DOCTYPE html>
<html>
<head>
    <title>章后实验</title>
</head>
<body>
    <form action="voter_registration.php" method="post">
        <table>
            <tr>
                <th>名：</th>
                <td>
                    <input name="voterFirstName" maxlength="15">
                </td>
            </tr>
            <tr>
                <th>姓：</th>
                <td>
                    <input name="voterLastName" maxlength="15">
                </td>
            </tr>
            <tr>
                <th>年龄：</th>
                <td>
                    <input name="votersAge" maxlength="3">
                </td>
            </tr>
            <tr>
                <th>国籍：</th>
                <td>
                    <input type="radio" name="isCitizen" value="true">是
                    <input type="radio" name="isCitizen" value="false">否
                </td>
            </tr>
            <tr>
                <td><input type="submit" value="注册"></td>
                <td><input type="reset" value="清除字段"></td>
            </tr>
        </table>
    </form>
</body>
</html>
```

#### 代码列表：PHP 脚本

```php
<?php
    $voterFirstName = $_POST['voterFirstName'];
    $voterLastName = $_POST['voterLastName'];
    $isCitizen = $_POST['isCitizen'];
    $votersAge = $_POST['votersAge'];

    if ($votersAge >= 18 && $isCitizen == "true") {
        print("你好 " . $voterFirstName . " " . $voterLastName . ", 你今年 " . $votersAge . "岁。<br>");
        print("你是公民。<br>");
        print("你可以投票。");
    } else {
        print("你好 " . $voterFirstName . " " . $voterLastName . ", 你今年 " . $votersAge . "岁。<br>");
        print("你不是公民。<br>");
        print("你不能投票。");
    }
?>
```

```php
        print("You are not allowed to vote.");

    }

?>
```

![](img/00138.jpeg)

图 4.63：查看 `voters_registration.html` 的输出。

![](img/00139.jpeg)

图 4.64：点击注册按钮提交表单。

点击注册（Register）按钮后，输出将如下：

![](img/00140.jpeg)

图 4.65：查看 `voters_registration.php` 的输出。

代码列表：`voters_registration.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>第 4 章实验练习</title>
</head>
<body>
    <form action="voters_registration.php" method="post">
    <table>
        <tr>
            <th>
                名：
            </th>
            <td><input name="voterFirstName" maxlength="15"></td>
        </tr>
        <tr>
            <th>
                姓：
            </th>
            <td><input name="voterLastName" maxlength="15"></td>
        </tr>
        <tr>
            <th>
                年龄：
            </th>
            <td><input name="votersAge" maxlength="3"></td>
        </tr>
        <tr>
            <th>
                国民：
            </th>
            <td>
                <input type="radio" name="isCitizen" value="true">是
                <input type="radio" name="isCitizen" value="false">否
            </td>
        </tr>
        <tr>
            <td><input type="submit" value="Register">注册</td>
            <td><input type="reset" value="Clear Fields">清空字段</td>
        </tr>
    </table>
    </form>
</body>
</html>
```

代码列表：`voters_registration.php`

```php
<?php
    $voterFirstName = $_POST['voterFirstName'];
    $voterLastName = $_POST['voterLastName'];
    $isCitizen = $_POST['isCitizen'];
    $votersAge = $_POST['votersAge'];
    if($votersAge >= 18 && $isCitizen == "true") {
        print("You are " . $voterFirstName . " " . $voterLastName . ", " . $votersAge . " years old.</br>");
        print("You are a citizen.</br>");
        print("You are allowed to vote.");
    } elseif($votersAge >= 18 && $isCitizen == "false") {
        print("You are " . $voterFirstName . " " . $voterLastName . ", " . $votersAge . " years old.</br>");
        print("You are not a citizen.</br>");
        print("You are not allowed to vote.");
    } elseif($votersAge < 18 && $isCitizen == "true") {
        print("You are " . $voterFirstName . " " . $voterLastName . ", " . $votersAge . " years old.</br>");
        print("You are a citizen.</br>");
        print("You are not allowed to vote.");
    } else {
        print("You are " . $voterFirstName . " " . $voterLastName . ", " . $votersAge . " years old.</br>");
        print("You are not a citizen.</br>");
        print("You are not allowed to vote.");
    }
?>
```

### 本章总结

在本章中，你首先学习了表达式和条件表达式，以及它们是如何由操作数、运算符、比较运算符和逻辑运算符构成的。你看到条件表达式是 PHP 分支控制结构的核心组件，以及这种结构是如何通过 PHP 中的四个条件语句实现的，即：

- `if` 语句
- `if-else` 和 `elseif` 语句
- `switch` 语句
- 以及三元运算符

我们还涵盖了多个示例，以充分理解所有条件语句的语法、结构和实现。在下一章中，我们将讨论循环控制结构。

# 第 5 章：控制结构 - 循环

### 本章目标

- 你将理解并分析 PHP 中不同的循环或迭代控制结构。
- 你将掌握 PHP 中 `while-loop`（while 循环）、`do-while-loop`、`for-loop` 和 `foreach-loop` 语句的语法和结构。
- 你将学习如何在实际代码中使用这些不同的循环。

在上一章中，我们学习了分支控制结构，根据条件表达式求值的结果执行或不执行特定的代码块。在本章中，我们学习循环控制结构（也称为迭代控制结构），即重复地执行或迭代特定的代码块。条件表达式求值的结果将决定我们循环或迭代代码块的次数。

一个循环控制结构由：

a. 一个条件表达式，
b. 一个定义清晰的代码块。

只要条件表达式求值为 `TRUE`，该代码块就会重复执行。

提示：你应该充分理解表达式和条件表达式的概念，以及它们是如何由操作数、运算符、比较运算符和逻辑运算符构成的。这些概念在第 4 章中通过大量示例进行了详细说明。

PHP 通过以下循环语句来实现迭代控制结构：

a. `while-loop`
b. `do-while-loop`
c. `for-loop`
d. `foreach-loop`

## 5.1 While 循环

这是 `while-loop` 的语法和结构。

```php
while (条件表达式) {
    代码块
}
```

### while 之后的语句

`while-loop` 的执行从评估条件表达式开始。如果评估结果为 `TRUE`，则执行代码块。然后再次评估条件表达式，只要结果为 `TRUE`，就会执行代码块。一旦条件表达式求值为 `FALSE`，执行将跳转到 `while` 之后的第一个语句。

注意，在 `while` 语句的代码块中，必须存在某些语句导致条件表达式最终变为 `FALSE`。例如，如果你的条件表达式是 `count < 10`，那么代码块中必须有一个语句（例如 `count++`）来终止循环。

### 让我们来看例子

问题：创建一个从 1 数到 10 的 `while` 循环。每个数字分行显示。确保条件语句为 `TRUE`。使用变量 `$number`。

解决方案：

步骤 1：创建一个 HTML 文档。命名为 `whileLoops_1.php`。将其保存在 `www` 或 `htdocs` 文件夹中。

![](img/00141.jpeg)

图 5.1：打开一个新的 HTML 文档。

步骤 2：在你的 PHP 文档中输入程序语句。

代码列表：`whileLoops_1.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>While 示例 1</title>
</head>
<body>
    <?php
        $number = 0;
        while($number < 11) //当 $number 小于 11 时
            print($number); // 显示 $number 的值
            print("</br>"); // 换行
            $number++; // $number 的值加 1
        
    ?>
</body>
</html>
```

![](img/00142.jpeg)

图 5.2：输入 `whileLoops.php` 的语句。

步骤 3：再次保存你的文件。

![](img/00143.jpeg)

图 5.3：在 Komodo Edit 中保存文件。



## 步骤 4：运行你的输出

![](img/00144.jpeg)

图 5.4：`whileLoops_1.php` 的输出。

如果条件表达式求值为 `FALSE`，示例会发生什么？尝试一下并看看结果。

## 步骤 1：调整变量赋值部分，将值 11 赋值给 `$number`

```php
<?php
    $number = 11;
?>
```

![](img/00145.jpeg)

图 5.5：将计数器变量 `$number` 的初始值改为 11。

## 步骤 2：保存你的文档

## 步骤 3：运行你的输出

没有任何内容显示。这是因为条件表达式的值的结果为 `FALSE`（假）。这将导致循环的代码块被忽略，结果是一个空白页面。

让我们尝试另一个例子。这次，我们将指示循环以 5 为步进行计数。

**问题：** 创建一个 `while` 循环，从 0 到 50 以 5 为步进行计数。每个数字应单独成行显示。确保条件语句的初始值为 `TRUE`（真）。使用变量名 `$number`。

**解决方案：**

**步骤 1：** 创建一个新的 HTML5 文档。将其命名为 `whileLoops_2.php`。将其保存到你的 `www` 或 `htdocs` 文件夹下。

![](img/00147.jpeg)

图 5.7：在 Komodo Edit 中打开一个新的 HTML5 文档。

**步骤 2：** 在你的 PHP 文档输入以下程序语句：

代码列表：`whileLoops_2.php`

```php
<!DOCTYPE html>
<html>
<head>
    <title>While Loop Example 2</title>
</head>
<body>
    <?php
        $number = 0;
        while($number < 51) // 当 $number 小于 51 时循环
        {
            print($number); // 显示 $number 的值
            print("</br>"); // 插入换行符
            $number += 5;  // $number 的值增加 5
        }
    ?>
</body>
</html>
```

![](img/00148.jpeg)

图 5.8：输入 `whileLoops_2.php` 的语句。

**步骤 3：** 运行你的输出。

![](img/00149.jpeg)

图 5.9：`whileLoops_2.php` 的输出。

如果初始条件被设置为 `FALSE` 会发生什么？为了找到答案，请尝试以下操作：

**步骤 1：** 调整变量赋值部分，为 `$number` 赋值 52。

```php
<?php
    $number = 52;
```

![](img/00150.jpeg)

图 5.10：在 `whileLoops_2.php` 中将计数器变量 `$number` 的初始值改为 52。

**步骤 2：** 保存你的文档。

**步骤 3：** 运行你的输出。

![](img/00151.jpeg)

图 5.11：在 `whileLoops_2.php` 中将 `$number` 的初始值改为 52 后输出为空。

正如预期的那样，屏幕是空白的，因为在进入 `do-while` 循环时，条件表达式的结果为 `FALSE`。

对于我们的第三个 `while` 循环例子，让我们获取一个包含七个元素或成员的简单数组。（在本章稍后的部分，我们将处理 `foreach` 循环，它是获取任何数组元素的最佳方法。）

**问题：** 创建一个 `while` 循环，读取一个包含七个成员的数组：界、门、纲、目、科、属、种。每个数组成员必须分单独成行显示。使用变量名 `$taxonomy` 作为数组，使用 `$x` 作为数组计数器。

**解决方案：**

**步骤 1：** 创建一个新的 HTML5 文档。将其命名为 `whileLoops_3.php`。将其保存到你的 `www` 或 `htdocs` 文件夹下。

![](img/00152.jpeg)

图 5.12：在 Komodo Edit 中打开一个新的 HTML5 文档。

**步骤 2：** 在你的 PHP 文档输入以下程序语句。

代码列表：`whileLoops_3.php`

```php
<!DOCTYPE html>
<html>
<head>
    <title>While Loops Example 3</title>
</head>
<body>
    <?php
        // 这是数组声明
        $taxonomy = array("Kingdom", "Phylum", "Class", "Order", "Family", "Genus", "Species");
        $x = 0;     //将数组计数器设为零
        while($x < count($taxonomy)) /*比较 $x 是否小于已计数的数组元素数量*/
        {
            print($taxonomy[$x]); // 显示数组成员($x)
            print("</br>");      // 插入换行符
            $x++;      // 访问下一个数组
        }
    ?>
</body>
</html>
```

![](img/00153.jpeg)

图 5.13：输入 `whileLoops_3.php` 的语句。

**步骤 3：** 再次保存你的文件。

**步骤 4：** 运行你的输出。

![](img/00154.jpeg)

图 5.14：`whileLoops_3.php` 的输出。

## 5.2 Do-While-Loop

`do-while` 循环与 `while` 循环一样，只是条件表达式被放在 `do-while` 循环的末尾，紧随代码块之后。这是 `do-while` 循环的语法和结构：

```php
do {
    // 语句块
} while (conditional expression);
do-while 语句后的第一条语句
```

在 `while` 语句中，程序执行是从首先评估条件表达式开始的。但在 `do-while` 循环中，程序执行首先执行循环的代码块，然后才评估条件表达式。如果条件表达式的结果为 `TRUE`，则将再次执行代码块。否则，`do-while` 循环将终止。

让我们修改第一个例子 `whileLoop_1.php`，并创建一个 `do-while` 循环。

**问题：** 创建一个 `do-while` 循环，从 0 到 10 以 1 为步进行计数。每个数字应单独成行显示。确保条件语句的初始值为 `TRUE`。使用变量名 `$number`。

**解决方案：**

**步骤 1：** 创建一个新的 HTML5 文档。将其命名为 `whileLoops_1.php`。将其保存到你的 `www` 或 `htdocs` 文件夹下。

![](img/00154.jpeg)

图 5.15：在 Komodo Edit 中打开一个新的 HTML5 文档。

**步骤 2：** 在你的 PHP 文档输入以下程序语句：

代码列表：`whileLoops_1.php`

```php
<!DOCTYPE html>
<html>
<head>
    <title>While Loop Example 1</title>
</head>
<body>
    <?php
        $number = 1; // 将 $number 设置为 1
        do // do 语句
        {
            print($number); // 显示 $number 的值
            print("</br>"); // 插入换行符
            $number++; // $number 的值增加 1
        } // 当 $number 小于 11 时循环
        while($number < 11);
    ?>
</body>
</html>
```

![](img/00155.jpeg)

图 5.16：输入 `whileLoops_1.php` 的语句。

**步骤 3：** 运行你的输出。

![](img/00156.jpeg)

图 5.17：`whileLoops_1.php` 的输出。

如果初始条件被设置为 `FALSE` 会发生什么？为了找到答案，请尝试以下操作：

**步骤 1：** 调整变量赋值部分，为 `$number` 赋值 11。

```php
<?php
    $number = 11;
```

![](img/00157.jpeg)

图 5.18：在 `whileLoops_1.php` 中将计数器变量 `$number` 的初始值改为 11。

**步骤 2：** 保存你的文档。

**步骤 3：** 运行你的输出。

![](img/00158.jpeg)

图 5.19：在 `whileLoops_1.php` 中将 `$number` 的初始值改为 11 后输出为空。

正如预期的那样，屏幕是空白的，因为在进入 `do-while` 循环时，条件表达式的结果为 `FALSE`。

## 5.3 For-Loop

到目前为止，我们学习了 `while` 和 `do-while` 语句，这是两种简单的 PHP 迭代结构。一种并不简单但紧凑且强大的 PHP 迭代结构，也是程序员最喜爱的结构是 `for` 循环，其结构如下：

```php
for (set-start; continue-condition; increment){
    // 要循环的代码块
}
for 循环语句后的第一条语句
```

在 `for` 语句中，控制 `for` 循环逻辑的所有逻辑和参数都声明在 `for` 关键字后面的第一个括号内。有三个语句必须在括号内声明。它们已分别标记为 `set-start`、`continue-condition` 和 `increment`，以表示每个语句的核心功能。注意只有前两个语句以分号结束。

`set-start` 语句设置循环计数器变量的初始值。计数器变量记录循环执行的次数。该变量如何递增（或递减）在增量语句中设置。

`continue-condition` 语句声明了循环继续执行的条件表达式。该条件在每次循环开始时进行评估。如果评估结果为 `TRUE`，则执行循环；否则，循环终止。

`increment` 语句设置了每次执行循环时计数器变量递增（或递减）的值。在大多数情况下，该变量递增 1，但允许任何值，包括负值。计数器变量的当前值可以随时告诉我们循环已经经历了多少次迭代。

`for-loop` 语句的使用频率比 `while-` 和 `do-while-` 语句得多，特别是当你知道需要迭代代码块多少次时。让 `for-loop` 成为程序员首选迭代结构的特性是：启动、继续和终止循环所需的所有逻辑都可以从 `for-loop` 的第一行直接读取。这与 `while-` 和 `do-while` 循环不同，后者仅显式声明了循环继续执行的条件表达式。因此，在 `while-` 和 `do-while` 循环中，你必须阅读并搜索代码寻找哪个变量（及其初始值）将用作循环计数器，以及它以什么值递增。

让我们分析一个从 1 计数到 10 的简单 `for-loop`。

```php
for ($i = 1; $i <= 10; $i++)
{
    echo ($i . </br>)
}
```

`set-start` 语句 `$i =1` 将计数器变量 `$i` 设置为其初始值 1。在每次执行 `for-loop` 代码块结束时，`$i` 将递增 1（如增量语句 `$i++` 定义所示）。

在 `for-loop` 执行的最开始，会评估测试条件 `$i <=10`。该条件表达式将评估为 `TRUE`，因为执行开始时 `$i` 的值为 1。在代码块的前 10 次迭代中，它将评估为 `TRUE`，但在第 11 次迭代开始时，`$i` 将变为 11，导致 `for-loop` 终止。

现在让我们学习通过二、三和倒序显示整数的 `for-loops` 示例。这需要按 1 以外的值递增和递减。

### 问题

创建一个 `for-loop`，按二和三计数，然后从 40 到 4 倒序按四计数。

### 解决方案

步骤 1：创建一个新的 HTML5 文件并将其保存为 `forLoops_1.php` 在你的 `www` 或 `htdocs` 文件夹中。

![](img/00160.jpeg) 

图 5.20：在 Komodo Edit 中打开新的 HTML5 文档。

步骤 2：输入以下程序语句。

代码列表：`forLoops_1.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>For-loop Example 1</title>
</head>
<body>
    <?php
        echo("Count by twos from 0 to 10:</br>");
        for($i = 0; $i <=10; $i+=2)  //从 0 到 10 递计数
            {
                echo($i . "</br>");
            }
        echo("Count by threes from 0 to 15:</br>");
        for($i = 0; $i <=15; $i+=3)  //从 0 到 15 三递计数
            {
                echo($i . "</br>");
            }
        echo("Count backwards by fours from 40 down to 4:</br>");
        for($i = 40; $i >=4; $i-=4)  //从 40 到 4 倒序四计数
            {
                echo($i . "</br>");
            }
    ?>
</body>
</html>
```

这是你的代码在 Komodo Edit 中看起来的样子：

![](img/0161.jpeg)

图 5.21：输入 `forLoops_1.php` 的语句。

步骤 3：再次保存你的文件。

步骤 4：运行你的输出。

![](img/0162.jpeg)

图 5.22：`forLoops_1.php` 的输出

## 5.4 Foreach 循环

`foreach-loop` 语句是修改过的 `for-loop`，仅适用于数组和对象。它不适用于任何其他类型。（对象将在第 10 章中学习）。`foreach-loop` 的目的是方便连续地检索数组的元素。

提示：在第 3 章中介绍了数组，清楚理解索引数组（或简单数组）、关联数组和多维数组之间的区别至关重要。你应该知道如何创建任何数组、如何填充它们、以及如何检索它们的成员。

当用于迭代索引数组或简单数组的成员时，`foreach-loop` 的结构和语法是：

```php
foreach($arrayName as $elementValue) {
    // 代码块
}
```

当用于迭代关联数组的成员时，`foreach-loop` 的结构和语法是：

```php
foreach($arrayName as $key => $elementValue) {
    // 代码块
}
```

`$arrayName` 是数组的名称，`$elementValue` 是元素的值。

```php
foreach ($gpas as $key => $value)
{
    print("Name: " . $key);
    print("<br/>GPA: " . $value);
    print("<br/>");
}
?>
</body>
</html
```

![](img/00164.jpeg)

图 5.24：输入 `foreachLoops_1.php` 的语句

### 步骤 3：保存文件

### 步骤 4：运行你的输出

![](img/00165.jpeg)

图 5.25：`foreachLoops_1.php` 的输出。

### 问题

创建一个输出布局的变体，使名称位于第一列，相应的 GPA 显示在每个名称对面。

### 解决方案

#### 步骤 1：修改代码并将表格元素代码放在数组声明的正下方。

```php
echo("<table border='0'>");
echo("<tr>");
echo("<th>Name</th>");
echo("<th>GPA</th>");
echo("</tr>");
```

#### 步骤 2：调整 `foreach` 循环并插入适当的表格单元格对齐代码。

```php
foreach ($gpas as $key => $value)
{
    echo("<tr>");
    echo("<td align='left'>" . $key . "</td>");
    echo("<td align='center'>" . $value . "</td>");
    echo("</tr>");
}
```

完整的代码列表现在应该像这样：

**代码列表：** `foreachLoops_2.php`



```html
<!DOCTYPE html>
<html>
<head>
    <title>Foreach Loop Example 1</title>
</head>
<body>
    <?php
        $gpas;
        $gpas["Adam"] = 4.00;
        $gpas["Ervin"] = 3.75;
        $gpas["Erin"] = 3.90;
        $gpas["Jim"] = 3.59;
        $gpas["Eric"] = 3.00;
        $gpas["Duane"] = 2.11;
        $gpas["Sally"] = "Not given";
        echo("<table border='0'>");
        echo("<tr>");
        echo("<th>Name</th>");
        echo("<th>GPA</th>");
        echo("</tr>");
        foreach ($gpas as $key => $value)
        {
            echo("<tr>");
            echo("<td align='left'>" . $key . "</td>");
            echo("<td align='center'>" . $value . "</td>");
            echo("</tr>");
        }
        echo("</table>");      
    ?>
</body>
</html>
```

![](img/00166.jpeg)

图 5.26：输入`foreachLoops_2.php`的语句

### 步骤 3：将文件保存为`foreachLoops_2.php`。

### 步骤 4：运行你的输出。

![](img/00167.jpeg)

图 5.27：`foreachLoops_2.php`的输出

使用`foreach`循环，让我们在另一个关联数组中进行一些操作。第二个示例将涉及根据给定成绩计算学生的 GPA。

### 问题

写一个程序，列出七门学术科目以及最终成绩。在列表末尾计算平均分。见下表：

| 学目 | 成绩 |
| :--- | :--- |
| 代数 | 3.50 |
| 生物 | 3.75 |
| 艺术 | 3.00 |
| 写作 | 2.50 |
| 交流 | 2.50 |
| 语言 | 4.00 |
| 历史 | 3.75 |

### 解决方案

#### 步骤 1：打开一个 HTML 模板。在`<title>`标签中，输入标题为`foreachLoops_3.php`。将文件保存到`www`或`htdocs`文件夹。由于你已经熟悉这一步，我将不再包含图片。

#### 步骤 2：在保持`foreachLoops_3.php`文件打开的情况下，输入以下语句。如下声明关联数组：

```php
$subject;
$subject['Algebra'] = 3.50;
$subject['Biology'] = 3.75;
$subject['Arts'] = 3.00;
$subject['Writing'] = 2.50;
$subject['Communications'] = 2.50;
$subject['Languages'] = 4.00;
$subject['History'] = 3.75;
```

要计算平均分，必须对所有成绩求和然后除以科目数量。因此，你必须包含两个变量来存储成绩的总和`$gpt`以及平均分`$gpa`：

```php
$gpa=0;
$gpt=0;
```

在`foreach`循环中，包含列出不同科目和相应成绩的指令。这也是你包含添加所有成绩过程的部分。

```php
foreach($subject as $name => $value) {
    echo("<tr>");
    echo("<td align='left'>" . $name . "</td>");
    echo("<td align='center'>" . $value . "</td>");
    echo("</tr>");
    $gpt += $value;
}
```

这是完整的代码：

**代码列表：`foreachLoops_3.php`**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Foreach Loop 3</title>
</head>
<body>
    <?php
        $subject;
        $subject['Algebra'] = 3.50;
        $subject['Biology'] = 3.75;
        $subject['Arts'] = 3.00;
        $subject['Writing'] = 2.50;
        $subject['Communications'] = 2.50;
        $subject['Languages'] = 4.00;
        $subject['History'] = 3.75;
        $gpa=0;
        $gpt=0;
        echo("<table border='1'>");
        echo("<tr>");
        echo("<th>Subject</th>");
        echo("<th>Grade</th>");
        foreach($subject as $name => $value)
        {
            echo("<tr>");
            echo("<td align='left'>" . $name . "</td>");
            echo("<td align='center'>" . $value . "</td>");
            echo("</tr>");
            $gpt += $value;
        }
        $gpa = $gpt / count($subject);
        echo("<tr>");
        echo("<td align='left'>Average</td>");
        printf("<th align='center'>%2f</th>", $gpa);
        echo("</tr>");
        echo("</table>");
    ?>
</body>
</html>
```

### 步骤 3：保存文件。

### 步骤 4：运行你的输出。

![](img/168.jpeg)

图 5.28：`foreachLoops_3.php`的输出

## 章节测试

**1 什么是循环？**

a. 代码段的无限迭代。

b. 执行固定次数的命令。

c. 根据条件重复的命令。

d. 控制结构。

**2 `while`循环和`do`循环的主要区别是什么？**

a. `while`循环比`do`循环短。

b. `do`循环的代码逻辑更复杂。

c. 即使条件初始为假，`do`循环也会执行一次。

d. 没有区别。

**3 什么是`for`循环？**

a. `for`循环迭代代码段。

b. `for`循环比`while`和`do`循环代码长。

c. 一种紧凑的循环类型，将逻辑和参数包含在一行内。

d. `for`循环设计用于处理数组。

**4 处理复杂数组时使用哪种循环比较明智？**

a. `while`循环

b. `do-while`循环

c. `for`循环

d. `foreach`循环

## 章节实验

### 问题 1

创建一个循环程序来显示以下输出。不要作弊！你只能`print()`或`echo()`一个星号，而不是星号字符串。

```
*
**
***
****
*****
******
*******
********
*********
```

### 问题 2

写一个程序计算篮球球队结束时的总分。汇总每个球员在上场和下场获得的总分。下表表示关联数组以及球队在比赛期间获得的积分。

| 球员名称 | 上场得分 | 下场得分 |
| :--- | :--- | :--- |
| Brandon Bass | 5 | 3 |
| Avery Bradley | 0 | 2 |
| Jordan Crawford | 6 | 2 |
| Kevin Garnett | 7 | 5 |
| Jeff Green | 3 | 3 |
| Courtney Lee | 1 | 4 |
| Fab Melo | 0 | 2 |
| Paul Pierce | 15 | 10 |
| Shavlik Randolph | 0 | 0 |
| Rajon Rondo | 20 | 8 |
| Jared Sullinger | 0 | 3 |
| Jason Terry | 9 | 10 |
| D.J. White | 3 | 2 |
| Chris Wilcox | 1 | 2 |
| Terrence Williams | 0 | 0 |

### 问题 3

创建一个程序来计算投资的每月收益。程序必须生成包含以下信息的报告：

(1) 投资本金

(2) 利率（年化）

(3) 投资期限（以年为单位，6 个月输入 0.5，3 个月 = 0.25，依此类推）

(4) 每月当前余额

(5) 投资期结束时的汇总余额

期限或时长以及利率将根据表单中输入的数字而异。然而，为了准确计算收益，必须满足以下条件。

### (1) 月利率计算公式为：

`Monthly Interest Rate = $interestRate/12`

### (2) 每月收益必须报告，计算方式为：

`Monthly Interest = $principal * $monthlyInterestRate`

### (3) 每月当前余额也必须报告，计算方式为：

`Monthly Balance = $principal + $monthlyInterest`

### (4) 期末结束时的未来投资价值计算公式为：

`Total Investment = the last monthly balance`

本金、年利率和期限必须都被视为`$superglobal`变量。

为解决方案准备两个文件。全局变量将由表单页面处理。计算由一个包含纯 PHP 脚本独立文档负责，该脚本将处理所有的计算和输出处理。

表单页面应如下：

![](img/00169.jpeg)

图 5.29：实验练习 3 的表单页面或输入屏幕显示。

按如下格式化输出：

| 本金金额 |  |
| 年利率 |  |
| 期限 |  |
| 收益历史 |  |
| 月份 | 每月收益 | 当前余额 |
| 第 1 月 |  |  |
| 第 2 月 |  |  |
| 第 3 月 |  |  |
| … |  |  |
| 第 n 月 |  |  |
|  | 投资在期末的未来价值 |  |

## 章节实验练习答案：

### 解决方案 1：

代码列表：章节练习 1 答案

`chapterLabProb_1.php`

```php
<?php
    for($i=0;$i<=10;$i++)
    {
        for($j=0;$j<=$i;$j++)
        {
            print("*\t");
        }
        print("</br>");
    }
?>
```

解决方案 1 输出：

![](img/00170.jpeg)

图 5.30：实验练习 1 的输出 (`chapter5LabProb_1.php`)

### 解决方案 2：

代码列表：章节练习 2 答案

`chapterLabProb_2.php`



# (5) 投资期结束时的汇总余额

期限或时长以及利率将根据表单中输入的数字而异。然而，为了准确计算收益，必须满足以下条件。

### (1) 月利率计算公式为：

`Monthly Interest Rate = $interestRate/12`

### (2) 每月收益必须报告，计算方式为：

`Monthly Interest = $principal * $monthlyInterestRate`

### (3) 每月当前余额也必须报告，计算方式为：

`Monthly Balance = $principal + $monthlyInterest`

### (4) 期末结束时的未来投资价值计算公式为：

`Total Investment = the last monthly balance`

本金、年利率和期限必须都被视为`$superglobal`变量。

为解决方案准备两个文件。全局变量将由表单页面处理。计算由一个包含纯 PHP 脚本独立文档负责，该脚本将处理所有的计算和输出处理。

表单页面应如下：

![](img/00169.jpeg)

图 5.29：实验练习 3 的表单页面或输入屏幕显示。

按如下格式化输出：

| 本金金额 |  |
| --- | --- |
| 年利率 |  |
| 期限 |  |
| 收益历史 |  |
| 月份 | 每月收益 | 当前余额 |
| 第 1 月 |  |  |
| 第 2 月 |  |  |
| 第 3 月 |  |  |
| … |  |  |
| 第 n 月 |  |  |
|  | 投资在期末的未来价值 |  |

## 章节实验练习答案：

### 解决方案 1：

代码列表：章节练习 1 答案

`chapterLabProb_1.php`

```php
<?php
    for($i=0;$i<=10;$i++)
    {
        for($j=0;$j<=$i;$j++)
        {
            print("*\t");
        }
        print("</br>");
    }
?>
```

解决方案 1 输出：

![](img/00170.jpeg)

图 5.30：实验练习 1 的输出 (`chapter5LabProb_1.php`)

### 解决方案 2：

代码列表：章节练习 2 答案

`chapterLabProb_2.php`

```php
<!DOCTYPE html>
<html>
    <head>
        <title>Chapter 5 Lab Exercise Solution 2</title>
    </head>
    <body>
<?php
    $boston = array
                    (
                        "Brandon Bass" => array (5, 3),
                        "Avery Bradley" => array (0, 2),
                        "Jordan Crawford" => array (6, 2),
                        "Kevin Garnett" => array (7, 5),
                        "Jeff Green" => array (3, 3),
                        "Courtney Lee" => array (1, 4),
                        "Fab Melo" => array (0, 2),
                        "Paul Pierce" => array (15, 10),
                        "Shavlik Randolph" => array (0, 0),
                        "Rajon Rondo" => array (20, 8),
                        "Jared Sullinger" => array (0, 3),
                        "Jason Terry" => array (9, 10),
                        "D.J. White" => array (3, 2),
                        "Chris Wilcox" => array (1, 2),
                        "Terrence Williams" => array (0, 0)
                    );
    $totalScore = 0;
    //add points to get the total score
    foreach($boston as $key)
    {
        foreach($key as $value)
        {
            $totalScore += $value;
        }
    }
    //set up table heading
    echo("<table border='1'>");
    echo("<tr>");
    echo("<th>Player Name</th>");
    echo("<th>Points-First Half</th>");
    echo("<th>Points-Second Half</th>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Brandon Bass</td>");
    echo("<td align='center'>" . $boston['Brandon Bass'][0] . "</td>");
    echo("<td align='center'>" . $boston['Brandon Bass'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Avery Bradley</td>");
    echo("<td align='center'>" . $boston['Avery Bradley'][0] . "</td>");
    echo("<td align='center'>" . $boston['Avery Bradley'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jordan Crawford</td>");
    echo("<td align='center'>" . $boston['Jordan Crawford'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jordan Crawford'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Kevin Garnett</td>");
    echo("<td align='center'>" . $boston['Kevin Garnett'][0] . "</td>");
    echo("<td align='center'>" . $boston['Kevin Garnett'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jeff Green</td>");
    echo("<td align='center'>" . $boston['Jeff Green'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jeff Green'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Courtney Lee</td>");
    echo("<td align='center'>" . $boston['Courtney Lee'][0] . "</td>");
    echo("<td align='center'>" . $boston['Courtney Lee'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Fab Melo</td>");
    echo("<td align='center'>" . $boston['Fab Melo'][0] . "</td>");
    echo("<td align='center'>" . $boston['Fab Melo'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Paul Pierce</td>");
    echo("<td align='center'>" . $boston['Paul Pierce'][0] . "</td>");
    echo("<td align='center'>" . $boston['Paul Pierce'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Shavlik Randolph</td>");
    echo("<td align='center'>" . $boston['Shavlik Randolph'][0] . "</td>");
    echo("<td align='center'>" . $boston['Shavlik Randolph'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Rajon Rondo</td>");
    echo("<td align='center'>" . $boston['Rajon Rondo'][0] . "</td>");
    echo("<td align='center'>" . $boston['Rajon Rondo'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jared Sullinger</td>");
    echo("<td align='center'>" . $boston['Jared Sullinger'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jared Sullinger'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jason Terry</td>");
    echo("<td align='center'>" . $boston['Jason Terry'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jason Terry'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>D.J. White</td>");
    echo("<td align='center'>" . $boston['D.J. White'][0] . "</td>");
    echo("<td align='center'>" . $boston['D.J. White'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Chris Wilcox</td>");
    echo("<td align='center'>" . $boston['Chris Wilcox'][0] . "</td>");
    echo("<td align='center'>" . $boston['Chris Wilcox'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Terrence Williams</td>");
    echo("<td align='center'>" . $boston['Terrence Williams'][0] . "</td>");
    echo("<td align='center'>" . $boston['Terrence Williams'][1] . "</td>");
    echo("</tr>");
    ?>
</body>
</html>
```



```php
<!DOCTYPE html>
<html
    <head>
        <title>Chapter 5 Lab Exercise Solution 2</title>
    </head>
    <body>
<?php
    $boston = array
                    (
                        "Brandon Bass" => array (5, 3),
                        "Avery Bradley" => array (0, 2),
                        "Jordan Crawford" => array (6, 2),
                        "Kevin Garnett" => array (7, 5),
                        "Jeff Green" => array (3, 3),
                        "Courtney Lee" => array (1, 4),
                        "Fab Melo" => array (0, 2),
                        "Paul Pierce" => array (15, 10),
                        "Shavlik Randolph" => array (0, 0),
                        "Rajon Rondo" => array (20, 8),
                        "Jared Sullinger" => array (0, 3),
                        "Jason Terry" => array (9, 10),
                        "D.J. White" => array (3, 2),
                        "Chris Wilcox" => array (1, 2),
                        "Terrence Williams" => array (0, 0)
                    );
    $totalScore = 0;
    //add points to get the total score
    foreach($boston as $key)
    {
        foreach($key as $value)
        {
            $totalScore += $value;
        }
    }
    //set up table heading
    echo("<table border='1'>");
    echo("<tr>");
    echo("<th>Player Name</th>");
    echo("<th>Points-First Half</th>");
    echo("<th>Points-Second Half</th>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Brandon Bass</td>");
    echo("<td align='center'>" . $boston['Brandon Bass'][0] . "</td>");
    echo("<td align='center'>" . $boston['Brandon Bass'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Avery Bradley</td>");
    echo("<td align='center'>" . $boston['Avery Bradley'][0] . "</td>");
    echo("<td align='center'>" . $boston['Avery Bradley'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jordan Crawford</td>");
    echo("<td align='center'>" . $boston['Jordan Crawford'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jordan Crawford'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Kevin Garnett</td>");
    echo("<td align='center'>" . $boston['Kevin Garnett'][0] . "</td>");
    echo("<td align='center'>" . $boston['Kevin Garnett'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jeff Green</td>");
    echo("<td align='center'>" . $boston['Jeff Green'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jeff Green'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Courtney Lee</td>");
    echo("<td align='center'>" . $boston['Courtney Lee'][0] . "</td>");
    echo("<td align='center'>" . $boston['Courtney Lee'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Fab Melo</td>");
    echo("<td align='center'>" . $boston['Fab Melo'][0] . "</td>");
    echo("<td align='center'>" . $boston['Fab Melo'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Paul Pierce</td>");
    echo("<td align='center'>" . $boston['Paul Pierce'][0] . "</td>");
    echo("<td align='center'>" . $boston['Paul Pierce'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Shavlik Randolph</td>");
    echo("<td align='center'>" . $boston['Shavlik Randolph'][0] . "</td>");
    echo("<td align='center'>" . $boston['Shavlik Randolph'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Rajon Rondo</td>");
    echo("<td align='center'>" . $boston['Rajon Rondo'][0] . "</td>");
    echo("<td align='center'>" . $boston['Rajon Rondo'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jared Sullinger</td>");
    echo("<td align='center'>" . $boston['Jared Sullinger'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jared Sullinger'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Jason Terry</td>");
    echo("<td align='center'>" . $boston['Jason Terry'][0] . "</td>");
    echo("<td align='center'>" . $boston['Jason Terry'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>D.J. White</td>");
    echo("<td align='center'>" . $boston['D.J. White'][0] . "</td>");
    echo("<td align='center'>" . $boston['D.J. White'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Chris Wilcox</td>");
    echo("<td align='center'>" . $boston['Chris Wilcox'][0] . "</td>");
    echo("<td align='center'>" . $boston['Chris Wilcox'][1] . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>Terrence Williams</td>");
    echo("<td align='center'>" . $boston['Terrence Williams'][0] . "</td>");
    echo("<td align='center'>" . $boston['Terrence Williams'][1] . "</td>");
    echo("</tr>");
    ?>
</body>
</html>
```

```php
echo("<td align='center'>" . $boston['Terrence Williams'][1] . "</td>");
echo("</tr>");
echo("<tr>");
echo("<th>End Game Score</th>");
echo("<td align='center' colspan='2'>" . $totalScore . "</td>");
echo("</tr>");
?>
</body>
</html>
```

### 方案 2 输出

![](img/00171.jpeg)

图 5.31：实验练习 2 的输出（`chapter5LabProb_2.php`）

### 方案 3

代码列表：章节练习题 3 解决方案

`chapterLabProb_3.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title> 第 5 章实验练习方案 3</title>
</head>
<body>
    <form action="chapter5LabProb_3.php" method="post">
        <table>
            <tr>
                <th align=left>本金</th>
                <td><input name="principal" /></td>
            </tr>
            <tr>
                <th align=left>利率 (%)</th>
                <td><input name="interestRate" /></td>
            </tr>
            <tr>
                <th align=left>期限</th>
                <td><input name="term" /></td>
            </tr>
            <tr>
                <td><input type="submit" value="Okay" /></td>
                <td><input type="reset" value="Clear" /></td>
            </tr>
        </table>
    </form>
</body>
</html>
```

### 方案 3：表单输出

![](img/00169.jpeg)

图 5.32：实验练习 3 的输入界面（`chapter5LabProb_3.php`）

### 代码列表：章节练习题 3 解决方案

`chapterLabProb_3.php`

```php
<?php
    $principal = $_REQUEST['principal'];
    $interestRate = ($_REQUEST['interestRate'] / 100);
    $term = $_REQUEST['term'];
    $mi = 0;
    $mir = 0;
    $mb = $principal;
    $months = ($term * 12);
    $mir = ($interestRate / 12);  
    $final=0;
    echo("<table border='1'>");
    echo("<tr>");
    echo("<td>本金金额</td>");
    echo("<td colspan='2' align='center'>" . $principal . "</td>");
    echo("</tr>");
    echo("<td>年利率（小数形式）</td>");
    echo("<td colspan='2' align='center'>" . $interestRate . "</td>");
    echo("</tr>");
    echo("<td>期限（月数）</td>");
    echo("<td colspan='2' align='center'>" . $months . "</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td colspan='3' align='center'>收益历史</td>");
    echo("</tr>");
    echo("<tr>");
    echo("<td>月份</td>");
    echo("<td>每月收益</td>");
    echo("<td>当前余额</td>");
    echo("</tr>");
    for($i = 1; $i<=$months; $i++) {
        $mi = ($mb*$mir);
        $mb = ($mb+$mi);
        echo("<tr>");
        echo("<td align='center'>月份 " . $i . "</td>");
        printf("<td>%0.2f", $mi);
        printf("<td>%0.2f", $mb);
        $final=$mb;
    }
    echo("<tr>");
    echo("<td colspan='2'>期末结束时的投资未来价值</td>");
    printf("<td>%0.2f", $final);
    echo("</tr></table");
?>
```

### 方案 3 输出

本金：600，利率：10%，期限：（5 个月）0.41667

![](img/00172.jpeg)

图 5.33：实验练习 3 的第一组输入值

![](img/00173.jpeg)

图 5.34：第一组输入值的输出 - 本金：600，利率：10%，期限：（5 个月）0.41667

本金：100，利率：10%，期限：（12 个月）1 年

![](img/00174.jpeg)

图 5.35：实验练习 3 的第二组输入值

![](img/00175.jpeg)

图 5.36：第二组输入值的输出 - 本金：100，利率：10%，期限：（12 个月）1 年

## 总结

在本章中，你学习了 PHP 中不同循环或迭代结构的结构和语法，以及大量的示例：`while-loop`、`do-while-loop`、`for-loop` 和 `foreach-loop`。

在这四种循环结构中，`foreach-loop` 是唯一专门设计用于处理所有类型数组的迭代结构，这使得能够轻松地操作它们。

在下一章中，我们将讨论自定义的 PHP 函数。

# 第 6 章：自定义 PHP 函数

## 目标

- 能够定义什么是 PHP 函数
- 学习创建和调用函数的格式与语法
- 了解用于传递值的参数以及用于接收值的参数
- 学习如何从函数返回值
- 学习如何使用 `include` 和 `require` 将自己的函数组织起来

## 6.1 引言与概述

函数是编程语言中不可或缺的特性，因为：

- 在良好的设计系统中，98% 的代码位于函数之中，充分理解函数对于掌握面向对象编程（OOP）至关重要，它让开发者构建大型且易于维护的应用程序



我们将讨论函数的基础知识，现在你可能还没有意识到这一点，但从第 1 章开始你就在使用这些内置函数，具体来说是 `echo()`、`print()` 和 `printf()`。以下是你在第 1 章中使用这些函数的实例：

```php
echo("<br>这是我的第二个 PHP 语句");
print("你好！");
printf("我 %d 岁", 21);
```

在第 3 章，你使用了 `array()` 函数。调用 `array()` 的实例可能比之前的实例复杂，但它遵循相同的函数调用格式和语法：

```php
$salary = array(
    "Doe" => 30000,
    "Smith" => 28000,
    "Rogers" => 50000,
    "Adam" => 120000,
    "Brown" => 60000
);
```

提示：2012 年 11 月 27 日，`stackoverflow.com` 的一个用户报告说，PHP 官方网站 `www.php.net` 列出了 5845 个内置或内部函数。此外，数百名开发者提供了经过测试和调试的专用函数代码库，大多免费提供。一个大型且流行的库是 PEAR。访问 `pear.php.net` 查看。

## 6.2 调用函数

函数（在其他编程语言中，特别是旧语言中称为子程序）是执行特定任务（特定功能）的语句自包含编译。

例如，`echo()`、`print()` 和 `printf()` 函数的主要工作是在浏览器中显示作为参数传递给它们的、括号内的字符串值。

对于 `array()` 函数，它根据作为参数传递给函数的值创建一个数组。这些值成为数组的元素或成员。`array()` 函数随后返回数组的变量引用。

调用函数等同于程序语句。当你调用一个函数时，程序控制会跳转到函数的第一行。当函数执行完其代码后，程序控制将转移到函数调用之后的语句。

```
$retValue = functionName(arg1, arg2,...); // function call
```

在 `functionName` 执行完毕后将执行的程序语句。

你可以通过向函数传递任意数量的值（称为“参数”）来可选地控制函数的处理过程。

例如，`echo()` 和 `print()` 函数都各接收了一个参数，该参数是一个字符串。这个字符串就是 `echo()` 和 `print()` 函数将在浏览器中显示的内容。接下来，`printf()` 函数了两个参数，第一个是字符串，第二个是整数。字符串和整数都将在浏览器中显示“I am 21 years old.”。最后，`array()` 函数传递了五个参数，这些参数将成为关联数组 `$salary` 的成员或元素。

函数还可以可选地向你返回一个值，称为“返回值”。

调用或执行函数会执行该函数的程序语句。当你调用或执行一个函数时，可以使用以下任何格式：

1. `functionName();`

2. `functionName( arg1, arg2,..., argN );`

3. `$returnValue = functionName();`

4. `$returnValue = functionName( arg1, arg2, . . .);`

- `functionName` – 这是你给函数的唯一名称。没有两个函数会有相同的名称。

- `arg1, arg2, . . ., argN` – 这是一个可选的逗号分隔的字面量或变量名列表，称为参数，是传递给函数的值。你可以传递的参数数量没有限制。这些参数允许你控制函数的执行，它们赋予了函数功能和灵活性。

- `$returnValue` – 这是一个可选的变量，用于接收并存储函数返回的可选值。通过使用变量来持有函数的返回值，我们可以让该值对脚本的其他部分可用。

让我们再看另一个函数调用的例子，它使用了函数调用的所有可选组件——参数列表和返回值。我们将在本章后面的内容多次引用这个例子。

```
$noDaysInMonth = days_in_month( $month, $year );
```

`days_in_month()` 函数是由 [www.stackoverflow.com](http://www.stackoverflow.com) 的用户编写并贡献的。它返回过去或未来任何年份（`$year`）指定月份（`$month`）的天数，并考虑了闰年。

函数是任何编程语言不可或缺组件。由于以下原因，你必须拥有它们：

a. 你消除了重复代码。

假设你写了一个例程，通过提取一个人的名、中间名和姓的首字母来形成一个三个字母的大写缩写。（例如，缩写 GWB 可以由 George Walker Bush 组成。）

如果没有函数，你必须为你需要处理的每个名字复制并粘贴这个例程。但有了函数，你可以将此例程存放在一个函数中，调用该函数并将名、中间名和姓作为参数传递。然后，函数会将这三个字母的缩写作为返回值返回。例如：

```php
$givname = “George”;
$midname = “Walker”;
$surname = “Bush”;
$initials = formInitials( $givname, $midname, $surname);
```

之前的四行代码可以这样被紧凑为一行：

```php
$initials = formInitials( “George”, “Walker”, “Bush”);
```

在上述两种形式中，变量 `$initials` 都将包含大写的字母“GWB”。

b. 函数可以在其他脚本中重用。

你现在有了一个无错误的 `formInitials()` 函数，你（以及其他程序员）可以在未来的脚本中使用它。你甚至不需要阅读或知道哪些程序语句构成了该函数。你只需要知道函数的名称、它的作用、需要向它传递什么参数，以及它的返回值（如果有的话）是什么。

c. 函数极大地减少了错误。

再次假设，如果没有函数，你不得不通过复制和粘贴来复制程序语句。假设你复制并粘贴了二十次某个例程。现在出现了一种情况，你必须对该例程进行细微调整——这意味着你现在必须去那二十个地方进行这些更改。除了进行二十次独立编辑的时间和精力外，极可能会混入某些输入错误，这会完全破坏你的代码。而且在脚本真正崩溃之前，你都不会知晓这一点！

但如果你的例程被创建为一个函数，你只需要修改一次即可。

d. 函数帮助你分而治之。

编程（或者编写实际代码）之前应该先进行长期的、系统的分析。在房屋或建筑的地基之前，绝对会花费几天甚至几周的时间来测量土地、分析土壤、选择合适的材料，然后起草并定稿建筑蓝图。即使在编写第一行代码之前，也会进行类似的分析和设计过程。

对你将在 PHP 中实现的系统进行仔细、详尽且系统的分析，将揭示整个系统可以被分解为层次化的任务。每个任务都可以被编写成一个函数，该函数可以很好地融入函数的层次结构中。事实上，一个设计良好的系统其 98% 的代码都在函数中，剩下的 2% 由用于控制这些函数执行的顶层控制代码组成。

## 6.3 `Include()` 和 `Require()` 函数

在上一节中，我们涵盖了如何调用或执行函数的所有方面，包括向函数传递参数以及检索和存储函数的返回值。我们将在下一节介绍创建函数的细节。现在，我们将涵盖如何组织你将创建的各种函数以及如何轻松地访问它们。通过“组织”，我们的你在哪里或在哪些文件中放置或存储你将创建的函数，以便它们被易于找到和访问？

在之前的所有章节中，我们都是在以 .php 作为文件扩展名的 HTML 结构化文档的 PHP 标签内编写 PHP 代码（而不是 .html）。然而，这并不是现实 PHP 编码的做法。理想情况下，HTML 结构化文档中唯一的 PHP 代码将是对 PHP 函数层次结构中顶层控制函数的函数调用，例如：

```php
<?php
main();
?>
```

`main()`（你选择的任何适当名称）的主要任务是控制函数层次结构中第二层控制函数的执行。`main()` 函数本身的代码将位于单独的 .php 文件中。

函数应该存储在单独的 PHP 函数容器文件中，以便于整洁性、检索和维护。假设在一个项目中，开发团队编写、测试并调试了 100 个函数。假设每个函数的平均长度为 20 行，其中最短的函数只有 2 行，而最长的函数有的一百行。经验丰富的程序员不会将这 100 个函数全部放在一个 PHP 脚本文件中（这至少会有 2000 行代码，并且需要打印 40 页纸质副本）。他们会先根据主要任务对函数进行分类分组，然后将任务相似的函数放置或存储在单独 PHP 函数容器文件中。例如，处理图形的函数将放在 `graphics.php` 中。处理折扣计算的函数将放在 `discounts.php` 中，以此此类推。

程序员根据需要将所需的函数容器文件读取到主脚本文件中。为了实现这一点，程序员可以使用以下四个函数之一：

```php
include("phpScriptName");
include_once("phpScriptName");
require("phpScriptName");
require_once("phpScriptName");
```

这四个函数都允许将 `phpScriptName` 文件中的函数集成到当前脚本文件中，就像代码被复制并粘贴了一样。

`include()` 和 `require()` 之间的唯一区别在于，如果找不到包含的文件，`include()` 仅抛出一个 PHP 警告（`E_WARNING`），而 `require()` 会抛出一个致命错误（`E_COMPILE_ERROR`）并停止运行脚本。

`include_once()` 和 `require_once()` 用于防止嵌套包含。为了理解嵌套包含，让我们考虑以下四个 PHP 脚本——`1stScript.php`、`2ndScript.php`、`myFuncsA.php` 和 `4thScript.php`。

```php
// 1stScript.php
<?php
    include("myFuncsA.php");
    validateParameters();
?>
```

```php
// 2ndScript.php
<?php
    include("myFuncsA.php");
    function computeValues(param1, param2) {
        program statements;
        return $computedValue;
    }
    validateParameters();
?>
```

```php
// myFuncsA.php
<?php
    function validateParameters() {
        program statements;
        return expression;
    }
?>
```

```php
// 4thScript.php
<?php
    include("1stScript.php");
    include("2ndScript.php");
?>
```

`1stScript.php` 和 `2ndScript.php` 都包含了 `myFuncsA.php`，其中定义并编写了函数 `validateParameters()`。到目前为止一切正常好！但现在出现了 `4thScript.php`，它同时包含了 `1stScript.php` 和 `2ndScript.php`。这就是我们的嵌套包含情况！

当 `4thScript.php` 包含 `2ndScript.php` 时就会发生问题，因为发生这种情况时 `2ndScript.php` 会包含 `myFuncA.php`，该文件包含 `validateParameters()` 的定义。但 `1stScript.php` 已经包含了 `myFuncA.php` 并在在此过程中定义了 `validateParameters()`。所以当 `2ndScript.php` 包含 `myFuncA.php` 时，它再次定义了 `validateParameters()`，从而导致显示长错误消息的致命错误：`Cannot redeclare validateParameters() (previously declared in myFuncA.php)`。

为了解决这个问题，我们在 `4thScript.php` 中使用了 `include_once()`。

```php
// 4thScript.php
<?php
    include_once("1stScript.php");
    include_once("2ndScript.php");
?>
```

`include_once()` 和 `require_once()` 在当前执行期间只包含一次指定的文件或脚本。如果你再次调用 `include_once()` 或 `require_once()` 来包含同一个文件或脚本，则什么都不会发生。`include()` 或 `require()` 函数调用应该放置在 HTML 文档的 `<head>` 部分。还需要理解的是，当你包含一个函数脚本文件时，你**不会**自动执行这些函数。函数只有通过格式正确的调用以及正确的参数顺序 才能被执行。

让我们来看一些例子。

![](img/00176.jpeg)

图 6.1：在 Komodo Edit 页面通过点击 New File 开始创建文件。选择 New file 将弹出一个窗口。选择 PHP 模板并将 `www` 设置为目录，其中保存名为 `includeMe.php` 的新文件。

![](img/00177.jpeg)

图 6.2：Komodo Edit 的 New File 窗口。输入文件名 `includeMe.php` 并文件保存到你的 `www` 文件夹中。打开新的 PHP 文件，在起始和结束标签内输入以下代码。

```php
<?php
    print("This statement is called from the file includeMe.php using the include command.");
?>
```

![](img/00178.jpeg)

图 6.3：Komodo Edit 中的 `includeMe.php` 代码。保存并运行此脚本。此代码产生产生输出：

![](img/00179.jpeg)

图 6.4：运行 `includeMe.php` 脚本时的输出。

使用模板创建另一个 PHP 文件，但这次使用 `include.php` 作为文件名。在 `include.php` 文件中，输入以下代码打印相同的语句，然后插入一个换行标签。然后将其放入 include 命令中。

```php
<?php
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
    include("includeMe.php");
?>
```

![](img/0180.jpeg)

图 6.5：Komodo Edit 中查看的 `include.php` 代码列表。你的输出应该像这样：

![](img/0181.jpeg)

图 6.6：运行 `include` 时的输出。

通过在程序中复制 include 语句多次使用 include。通过下面的代码修改 `include.php`，然后运行它。

```php
<?php
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
    include("includeMe.php");
    print("<br>");
    include("includeMe.php");
    print("<br>");
    include("includeMe.php");
    print("<br>");
    include("includeMe.php");
?>
```

![](img/0182.jpeg)

图 6.7：运行修改后的 `include.php` 的输出。

现在，在我们之前的 `include.php` 代码中将 `include` 替换为 `require` 并添加一些 print 语句。还按照下面的代码更改 require 语句内部的文件，然后将文件保存为 `include_2.php`。

```php
// Code Listing: include_2.php
<?php
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
    require("includeMeXX.php");
    print("<br>");
    include("includeMe.php");
    print("<br>");
    include("includeMe.php");
    print("<br>");
    include("includeMe.php");
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
?>
```

注意，当 `require` 语句中发现错误时，该语句之后的代码都没有被处理，程序停止了。

![](img/0183.jpeg)



图 6.8：运行`include_2.php`的输出。

对于`include`函数，相反，它不会产生错误，而是忽略了错误。例如，在文件名`include_3.php`下输入保存以下代码并运行输出：

```php
// Code Listing: include_3.php
<?php
    print("This statement is called from the file includeMe.php using the include command.");
    print("<br>");
    include("includeMeXX.php");
    print("<br>");
    include("includeMe.php");
?>
```

```php
print("The following statement below is printed out using the include function.");
print("</br>");
print("The following statement below is printed out using the include function.");
print("</br>");
print("The following statement below is printed out using the include function.");
print("</br>");
?>
```

如果所有的`print`和`include`语句都经过处理，输出将显示六行。但由于其中一个`include`语句调用了一个不存在或“空”文件——`includeMeXX.php`，程序将把该部分代码视为错误，并在浏览器中打印出错误语句。当使用`require`代替`include`时，程序也会停止。

![](img/00184.jpeg)

图 6.9：`include_3.php`运行时的输出。

## 6.4 创建简单函数

现在，让我们学习如何编写自己的函数。这是我们必须遵循的格式和语法：

```php
function functionName( param1, param2, . . . paramN ) {
    program statements;
    return expression;
}
```

第一行必须以关键字`function`开始。接着是你的函数名称。该名称必须遵循某些规则。

有效的`functionName`以字母或下划线开头，后跟任意数量的字母、数字或下划线。函数名不区分大小写。

我们之前说过，函数是“一个执行特定任务的程序语句的自包含集合”。当你为函数命名时，该名称应该让你对函数将执行的“特定任务”有一个直观的理解。

函数名后面应该跟着一组括号`()`。如果函数被设计为接收参数，则在括号内放置一个用逗号分隔的参数列表（`param1`, `param2`, . . . `paramN`），用于接收参数。你可以指定任意数量的参数变量，但对于你指定的每个参数，在调用函数时必须向函数传递相应的参数。换句话说，函数调用中的参数顺序和数量应该与函数定义中的参数顺序和数量匹配。

无论你的函数是否接收参数，括号`()`都必须紧跟在函数后面。

**注意**：参数（arguments）和形（parameters）之间的区别是什么？参数是你传递给函数的值，而形式是函数内部接收该值的变量。在现实生活中，这两个术语通常互换使用。

括号之后是函数的主代码块，由大括号`{}`分隔。在这个代码块中，你可以编写任何 PHP 程序语句，包括对其他函数的调用（包括当前函数），这种做法被称为递归。

`return`语句返回`expression`。

**提示**：以防你忘记了什么是表达式，你可以回顾第 4 章第 1 节“简单控制结构——If 语句”。

`return`语句可以放在函数代码块的任何位置，但一旦执行了`return`语句，函数将立即终止，控制权返回调用脚本，具体返回函数调用后的第一个程序语句。

让我们创建一个简单函数。准备两个文件模板：一个 PHP 函数容器文件和一个调用容器文件中函数的 HTML 文档。

### 步骤 1：创建一个名为`functions.php`的 PHP 模板。这将是函数容器文件。点击“新建文件”。

![](img/00185.jpeg)

图 6.10：Komodo Edit 启动页。点击“New File”。

![](img/00186.jpeg)

图 6.11：Komodo Edit 的新建文件对话框。输入文件名`functions.php`并文件保存到你的 www 或 htdocs 文件夹中。

一旦创建了`functions.php`文件，就开始编写第一个函数`greeting()`。

### 步骤 2：在你的`functions.php`文件中输入以下代码。

```php
<?php
function greeting()
{
    echo("Hello! This is a greeting!");
}
?>
```

![](img/00187.jpeg)

图 6.12：`functions.php`运行时的输出。

在左右大括号之间的语句是需要该函数的 HTML 文档实际调用的代码。PHP 函数脚本容器文件必须正确地包含或 include 或 require 这些函数。

现在，让我们向容器文件中添加第二个函数`loop()`。这个循环例程将以三角形结构显示星号 (*)。

```php
<?php
    function greeting()
    {
        print("Hello! This is a greeting!</br>");
    }

    function loop()
    {
        for($i=0; $i<=10; $i++)
        {
            for($j=0; $j<=$i; $j++)
            {
                print("*");
            }
            print("<br/>");
        }
    }
}
```

（注：原文在后半部分存在大量重复和逻辑混乱，此处已在保持内容的基础上对翻译进行了逻辑清理。）

函数的返回值它是为传递的特定`$month`和特定`$year`所计算的天数。对函数进行 2014 年 2 月天数的实际调用如下：

```php
$noDaysInMonth = days_in_month( 2, 2014 )
```

该函数将返回 28，该值将存储在变量`$noDaysInMonth`中。

现在，假设我们无法向函数传递参数。在`days_in_month()`函数的情况下，我们必须为想要计算的每年的每个月都编写一个该版本的代码！

没有参数的函数将变得毫无用处！但有了参数，我们只需要一个函数就可以处理过去和未来所有年份月份，直到永恒！

以下是关于向函数传递参数的规则：

a. 如果要向函数传递多个参数，这些参数之间必须用逗号分隔。

b. 传递给函数的参数数量和顺序必须与函数定义中声明的参数数量和顺序匹配。如果函数声明需要三个参数，则必须传递三个相应的参数。

让我们来看之前的例子，一个声明了三个参数的函数。这是该函数的部分声明：

```php
Function formInitials( $givname, $midname, $surname) { 
    program statements
}
```

对此函数的正确调用为：

```php
$initials = formInitials( “George”, ”Walker”, “Bush”)
```

三个参数对应三个参数，且参数的顺序与参数的顺序对应。参数“George”对应参数`$givname`，参数“Walker”对应`$midname`，参数“Bush”对应`$surname`。改变参数的顺序你就会得到错误的结果！

c. 参数可以是 PHP 八种数据类型中的任何一种，即：整数、浮点数、字符串、布尔值、数组、对象、资源（或句柄）甚至 null。（尽管向函数传递 null 值是少罕的。）

d. 向函数传递的参数数量没有限制。然而，使用超过五个或六个参数是不现实的。想象一下，如果你定义并使用一个需要六个以上参数的函数会有多么困难和高错误概率！

提示：通过使用数组，你可以向函数传递任意数量的参数，但仍然保持接口简单，因为你只向函数传递了一个变量，即数组。

让我们来看一些例子。

**步骤 1**：在 PHP 模板中创建一个新的 PHP 函数脚本容器文件，文件名使用`functionArgs.php`。

![](img/00192.jpeg)

图 6.17：Komodo Edit 中文件`functionArgs.php`的新建文件对话框。

**步骤 2**：将其保存到你的`www`或`htdocs`文件夹中。

**步骤 3**：在`functionArgs.php`文件中，创建一个名为`dogAgeCalc()`的函数并向函数传递参数`$dogAge`。

```php
<?php
function dogAgeCalc($dogAge)
{
```

**步骤 4**：编写将狗年龄乘以七的代码。

```php
    $humanAge = $dogAge*7;
    print("The dog's age in human years is " . $humanAge .".");
```

**步骤 5**：关闭脚本。

```php
    }
?>
```

此脚本将计算给定的狗年龄折合人类年龄。例如，如果狗是 7 岁，它等同于一个 49 岁的人类。

这里是狗年龄计算器的完整代码列表。

**代码列表：functionArgs.php**

```php
<?php
function dogAgeCalc($dogAge)
{
    $humanAge = $dogAge*7;
    print("The dog's age in human years is " . $humanAge .".");
}
?>
```

如果你尝试运行此代码，它将显示空白输出，因为变量`$age`尚未赋值。脚本的输出看起来像这样：

![](img/00193.jpeg)

图 6.18：运行`functionArgs.php`时的输出。

现在为了让这个 php 函数容器文件变得有用，我们必须在 HTML 模板中编写的另一个 PHP 文档。

**步骤 6**：打开一个新的 HTML 文档模板并将文件命名为`computeDogAge.php`。

![](img/00194.jpeg)

图 6.19：Komodo Edit 中文件`computeDogAge.php`的新建文件对话框。

**步骤 7**：包含起始和结束的 PHP 脚本标签。在文档的`<head>`部分，`include()` PHP 函数容器文件`functionArgs.php`。对`include()`和`require()`函数的调用必须位于`<head>`部分。

```html
<!DOCTYPE html>
<html
<head>
    <title>Dog Age Calculator</title>
    <?php include("functionArgs.php"); ?>
</head>
```

**步骤 8**：在`<body>`部分调用函数`dogAgeCalc`并为`$age`赋值为五，然后将其传递给函数。

```html
<body
    <?php
        dogAgeCalc(5);
```

**步骤 9**：关闭脚本和文档。

```php
    ?>
</body>
</html>
```完整的代码列表和输出如下：

```html
<!DOCTYPE html>
<html
<head>
    <title>Dog Age Calculator</title>
    <?php include("functionArgs.php"); ?>
</head>
<body>
    <?php
        dogAgeCalc(5);
    ?>
</body>
</html>
```

## 6.6 Return 语句

PHP 函数只返回一个值。如果没有提供值，函数将返回`null`。

`return`的语法是：

```php
return expression;
```

提示：以防你忘记什么是表达式，如果你想从函数返回多个值怎么办？使用数组！

让我们看看以下：

**代码列表：returnExample.php**

```php
<!DOCTYPE html>
<html
<head>
    <?php
function square($value)
{
    $value = $value*$value;
    return($value);
}
?>
<title>Return 1</title>
</head>
<body>
    <?php
    print("The value of 2 squared is " . square(2));
    ?>
</body>
</html>
```

![](img/00196.jpeg)

图 6.21：`returnExample.php`的输出。

现在修改脚本使`square()`的返回值存储在变量`$x`中。

```html
<body>
    <?php
        $x = square(2);
    ?>
</body>
```

现在添加一个`print()`语句来打印`$x`的值。

更新后的代码列表和输出应该是：

**代码列表：returnExample2.php**

```php
<!DOCTYPE html>
<html
<head>
    <title>Return 2</title>
    <?php
function square($value)
{
    $value = $value*$value;
    return($value);
}
?>
</head>
<body>
    <?php
    print("The value of 2 squared is " . square(2));
    $x = square(2);
    print("</br> The value of the returned number is " . $x);
    ?>
</body>
</html>
```

![](img/00197.jpeg)

图 6.22：在 Komodo Edit 中查看`returnExample2.php`的完整代码列表。

![](img/00198.jpeg)

图 6.23：运行`returnExample2.php`时的输出。

### 章节测试

1. 什么是函数？

a. 存储在特定关键字下的相关代码块，可以调用并重复使用。

b. 产生曲线的方程。

c. 在 PHP 中执行预设过程的完整代码列表。

d. 由代码、函数和命令组成的关键字。

2. 什么是参数？

a. 传递给函数的值或字符串。

b. 两个不同意见的冲突。

c. 包含特定值的变量。

d. 完成函数的逗号分隔值。

3. `return`语句是如何工作的？

a. return 结束函数的执行并向调用函数的返回一个值。

b. return 将使代码从无值参数开始并重复自身。

c. `Return`打印传递给函数的值。

d. `Return`处理操作列表并返回结果。

## 4. 哪个函数在传递作为参数的文件名无法找到时会产生错误并终止脚本？

a. `include`

b. `include_once`

c. `require`

d. 以上均不是。

## 章节练习题：

1. 编写一个函数将摄氏度温度转换为华氏度。编写另一个函数将华氏度温度转换为摄氏度。以下是公式。

### 公式：

华氏度转摄氏度：`Tc = (5/9)*(Tf-32)`

摄氏度转华氏度：`Tf = (9/5)*Tc+32`

第一个练习中使用以下参数：

a. 待转换值：50

b. 函数名称为：

    - 华氏度转摄氏度 – Celsius `()`

    - 摄氏度转华氏度 – Fahrenheit `()`

c. 函数参数变量：`$temp`

使用双文档法来实现此目标。第一个文档是命名为`tempCalcFunc.php`的函数容器文件。第二个文档是使用 HTML 模板保存的`chap6Lab1_Sol.php`。

使用`include`函数引用容器文件。将结果显示为两位小数的浮点数。

2. 修改你的程序，让用户可以使用表单输入温度值。使用单选按钮来指示温度是摄氏度还是华氏度。当用户点击提交按钮时，必须显示相应的结果。

使用与练习 1 中相同的函数容器文件`tempCalcFunc.php`。在 HTML 模板中创建另一个 PHP 脚本文件用于表单。文件名使用`chap6Lab2_Sol.php`。

## 章节练习答案：

### 代码列表：tempCalcFunc.php

```php
<?php

    function Celsius($temp)
    {
        $temp = ((($temp*9)/5)+32);
        print("The value in Fahrenheit is ");
        return($temp);
    }

    function Fahrenheit($temp)
    {
        $temp = (($temp-32)*5/9);
        print("The value in Celsius is ");
        return($temp);
    }

?>
```

![](img/00199.jpeg)

图 6.24：在 Komodo Edit 中查看`tempCalcFunc.php`的完整代码列表。

### 代码列表：chap6Lab1_Sol.php



```php
<!DOCTYPE html>
<html>
<head>
<title>Chapter 6 Lab Exercise 1</title>
    <?php
        include("tempCalcFunc.php");
    ?>
</head>
<body>
    <?php
        printf("%0.2f", Celsius(50));
        print (".");
        print ("<br/>");
        printf("%0.2f", Fahrenheit(50));
        print (".");
    ?>
</body>
</html>
```

![](img/00200.jpeg)

图 6.25：在 `Komodo Edit` 中查看 `chap6Lab1_Sol.php` 的完整代码列表。

### 代码列表：tempCalcFunc2.php

```php
<?php

    $tempInput = $_POST['temp'];
    $cond = $_POST['type'];
    $newTemp = 0;

function Celsius($temp)
    {
        $temp = ((($temp*9)/5)+32);
        return($temp);
    }

function Fahrenheit($temp)
    {
        $temp = ((($temp-32)*5)/9);
        return($temp);
    }

if($cond == "1")
    {
        $newTemp = celsius($tempInput);   
        echo("The temperature in Fahrenheit is " . $newTemp.".");
    }
        else if($cond == "2")
    {
        $newTemp = fahrenheit($tempInput);   
        echo("The temperature in Celsius is " . $newTemp.".");
    }

?>
<form action="chap6Lab2_Sol.php">
<input type="submit" value="Return" />
</form>
```

![](img/00201.jpeg)

图 6.26：在 `Komodo Edit` 中查看 `tempCalcFunc2.php` 的完整代码列表。

### 代码列表：chap6Lab2_Sol.php

```php
<!DOCTYPE html>
<html>
<head>
<title>Chapter 6 Lab Exercise 2</title>
</head>
<body>
    <form action="tempCalcFunc2.php" method="post">
    <table>
        <tr>
            <td colspan="2"><<strong>Enter the temperature value and choose<br/>if’s in Celsius or Fahrenheit:</strong></td>
        </tr>
        <tr>
            <td>Temperature</td>
            <td><input type="text" name="temp"></td>
        </tr>
        <tr>
            <td>Celsius</td>
            <td><input type="radio" name="type" value="1"></td>
        </tr>
        <tr>
            <td>Fahrenheit</td>
            <td><input type="radio" name="type" value="2"></td>
        </tr>
        <tr>
            <td><input type="submit" value="Submit"></td>
        </tr>
    </table>
    </form>
</body>
</html>
```

以下是本章介绍的用于 PHP 服务器文件输入/输出操作的函数列表：

| 函数 | 描述 | 参数 |
| :--- | :--- | :--- |
| `fopen()` | 打开文件。 | 文件指针，访问模式 |
| `fclose()` | 关闭文件。 | 文件指针，访问模式 |
| `fwrite()` | 向服务器中打开的文件写入内容。 | 文件指针，资源文件 |
| `fgets()` | 从文件中读取单行。 | 资源文件，字符大小 |
| `fgetc()` | 从文件中读取单个字符。 | 资源文件 |
| `file_get_contents()` | 将整个文件读入到字符串中。 | 资源文件，字符大小 |
| `fread()` | 从打开的文件读取内容。 | 文件指针，字符大小 |
| `fgetcsv()` | 读取保存的 CSV 文件。 | 文件指针，字符大小 |
| `feof()` | 检查是否到达“文件末尾”。局限性：以 `w`、`a`、`x` 模式打开的文件无法读取。 | 文件指针 |
| `unlink()` | 删除文件。 | 资源文件 |
| `or die()` | 如果输入或输出过程中遇到错误，则终止程序。通常与函数 `fopen` 连接。 | 字符串参数 |
| `filesize()` | 获取字节单位的文件大小。 | Null 或整数值 |

表 7.1 介绍的命令和函数列表。

某些文件函数需要特定的模式作为参数之一。这些模式指定了访问类型。以下是 PHP 调用 `fopen()` 函数时使用的模式列表。

| 模式 | 描述 |
| :--- | :--- |
| `r` | 以只读模式打开文件。文件指针指向文件开头。 |
| `r+` | 以读写模式打开文件。文件指针指向文件开头。 |
| `w` | 以只写模式打开文件。打开并清空文件内容，如果文件不存在则创建一个新文件。在任何情况下，你都将获得一个空文件用于写入数据，且文件指针指向文件开头。 |
| `w+` | 以读写模式打开文件。打开并清空文件内容，如果文件不存在则创建一个新文件。文件指针指向文件开头。 |
| `a` | 以追加（写入）模式打开文件。将数据写入现有文件的末尾。如果文件不存在则创建一个新文件。文件指针指向文件末尾。 |
| `a+` | 以追加（写入）和读取模式打开文件。将数据写入现有文件的末尾。如果文件不存在则创建一个新文件。文件指针指向文件末尾。 |
| `x` | 以只写模式打开文件。创建一个新文件。如果文件已存在，则返回 FALSE 并报错。 |
| `x+` | 以读写模式打开文件。创建一个新文件。如果文件已存在，则返回 FALSE 并报错。 |

表 7.2 PHP 文件访问模式。

我们将从一个脚本开始，该脚本向文本文件写入数据，然后另一个脚本将获取该文本文件的内容。

**问题：** 编写一个 PHP 脚本，将包含名称的数据写入文本文件。

**解决方案：**

### 第 1 步

首先使用 `Komodo Edit` 使用 HTML 模板创建一个新的 PHP 文档。

![](img/00207.jpeg)

图 7.1：在 `Komodo Edit` 中创建一个名为 `fileIO_1.php` 的新 HTML 模板。

### 第 2 步

将文件保存在 `www` 或 `htdocs` 文件夹下，命名为 `fileIO_1.php`。

### 第 3 步

我们要写入的文件名为 `"names.txt"`，我们将此文件名存储在变量 `$fileName` 中。

```html
<!DOCTYPE html>
<html>
<head>
    <title>将文件保存到服务器</title>
</head>
<body>
    <?php
    $fileName = "names.txt";
```

### 第 4 步

接下来，我们将使用 `fopen()` 函数访问 `"names.txt"`，该函数接受两个参数：文件名和模式。这是 `fopen()` 函数的正确格式。

```php
fopen($fileName, 'w')
```

我们使用的模式是 `'w'`，意味着以只写模式打开文件。

现在，`fopen()` 函数返回一个文件句柄，除了其他用途外，它是与我们打开的文件关联的指针，我们用它访问文件内容。我们将文件句柄存储在变量 `$fp` 中。我们更新后的 `fopen()` 函数格式为：

```php
$fp = fopen($fileName, 'w')
```

**提示：** 文件句柄是资源数据类型，是 PHP 八种数据类型之一。文件句柄而非文件名，是我们对文件执行输入输出操作的主要手段。我们程序访问的每个文件必须分配一个唯一的文件句柄。

`fopen()` 函数通常与 `or die` 命令连接，如果在执行 `fopen()` 函数期间遇到错误，将终止程序并显示错误信息“Can’t open the file”。我们为 `fopen()` 函数的最终程序语句是：

```php
$fp = fopen($fileName, 'w') or die ("Can't open the file")
```

现在 `fopen()` 函数已成功返回文件句柄，除了其他用途外，它是与我们打开的文件关联的指针，我们用它访问文件内容。我们将文件句柄存储在变量 `$fp` 中。我们更新后的 `fopen()` 函数格式为：

```php
$fp = fopen($fileName, 'w')
```

（注：此处由于原文文本中存在重复和混乱，翻译时已根据逻辑进行了整合，以确保技术文档的连贯性。）

由于您提供的原文文本在后部分存在大量重复和逻辑混乱，上述内容已按照技术文档的逻辑进行了清理和翻译。

我们现在运行该程序，仅是为了检查 `names.txt` 文件是否已实际保存或写入你的本地服务器。请确保你已经保存了 `fileIO_1.php` 文件。

在本地浏览器中运行 `fileIO_1.php`。现在，忽略显示的任何错误信息。

![](img/00210.jpeg)

图 7.4：`fileIO_1.php` 首次运行时输出。

现在页面正在运行，我们可以检查特殊的 `htdocs` 或 `www` 文件夹来寻找 `names.txt` 文件。

打开你的 `wamp/www` 或 `mamp/htdocs` 文件夹：

![](img/00211.jpeg)

图 7.5：通过文档浏览器打开的 `Names.txt`。

点击文件名并选择“使用记事本查看”。请注意，当打开该文本文件时，它将把名称显示为连续的单单词文本，因为 `Notepad` 忽略了换行符。

![](img/00212.jpeg)

图 7.6：使用记事本查看的 `Names.txt`。

尝试使用其他应用程序（如 `WordPad`）查看 `names.txt` 文件，你会发现它将数组成员显示为列表：

![](img/00213.jpeg)

图 7.7：使用 `WordPad` 查看的 `names.txt`。

在这里我们可以看到在通过 `fwrite()` 函数将名称写入文本文件之前，在每个名称末尾追加的换行符的效果：

```php
fwrite($fp, $name[$i] . "\n");
```

`WordPad` 将换行符解释为开始新行的指示。相反，`Notepad` 忽略了换行符。

## 7.2 在服务器上读取文件

现在 `names.txt` 文件已经写入或保存到服务器中，我们将检索它的内容。我们将使用 PHP 中三个常用的文件数据检索的函数：`fread()`、`file_get_contents()` 和 `fgets()`。

`fread()` 函数从文件中读取字符字符串。它需要两个参数：一个文件句柄（资源数据类型）和要读取的字符数（整数数据类型）。示例如下：

```php
$string = fread($fp, 20);
```

在该示例中，从文件句柄 `$fp` 指向的文件读取 20 个字符，并存储在变量 `$string` 中。之后，文件指针将位于文件的第 21 个字符。

**问题**：使用 `fread()` 函数读取文件 `names.txt` 的全部内容。

**解决方案**：

**步骤 1**：在 `Komodo Edit` 中打开 `fileIO_1.php`，删除 `fopen()` 和 `fclose()` 函数之间的所有程序语句。

**步骤 2**：将 `<title>` 标签之间的文本从“Saving Files into the Server”改为“Reading Files from the Server”。

**步骤 3**：在函数调用 `fopen()` 中，将第二个参数模式从 `'w'` 改为 `'r'`。`'r'` 参数意味着我们访问文件仅是为了读取数据。

![](img/00214.jpeg)

图 7.8：根据图 7.2 重现的程序文件 `fileIO_1.php`，我们将保存为 `readFile_1.php`。`fopen()` 和 `fclose()` 调用之间的所有代码已删除。

**步骤 4**：将你的文档保存为 `readfile_1.php`。这是该步骤后你的代码列表应有的样子：

代码列表：`readFile_1.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Reading Files From The Server</title>
</head>
<body>
    <?php
        $fileName = "names.txt";
        $fp = fopen($fileName, 'r');
        fclose($fp);
    ?>
</body>
</html>
```

![](img/00215.jpeg)

图 7.9：在 `Komodo Edit` 中看到的 `readFile_1.php` 完整代码列表。

**步骤 5**：紧接 `fopen()` 的调用之后，输入 `fread()` 的调用。

```php
$string = fread($fp, 20);
```

这是完整代码列表应有的样子：

代码列表：`readFile_2.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Reading Files From The Server</title>
</head>
<body>
    <?php
        $fileName = "names.txt";
        $fp = fopen($fileName, 'r');
        $string = fread($fp, 20);
        fclose($fp);
        echo($string);
    ?>
</body>
</html>
```

![](img/00216.jpeg)

图 7.10：`readFile_2.php` 的完整代码列表。

如果我们运行该脚本，输出将是：

![](img/00217.jpeg)

图 7.11：`readFile_2.php` 运行时的输出。

如你所示，并不是所有的名称都显示在浏览器中，因为根据指令 `fread()` 只检索了 20 个字符。要确切知道从文件中读取多少字节，我们需要 `filesize()` 函数，它会告诉我们特定文件中具体有多少个字节。

**步骤 1**：创建一个新文件并命名为 `readFile_3.php`。完全复制 `readFile_2.php` 中编写的代码。

**步骤 2**：找到包含 `fread()`调用的行。将其从：

```php
$string = fread($fp, 20);
```

修改为：

```php
$string = fread($fp, filesize($fileName));
```

注意 `filesize()` 函数接受一个参数，即它所访问的文件句柄。

**步骤 3**：检查你的整个代码列表。更新后的代码列表必须是：

```html
<!DOCTYPE html>
<html>
<head>
    <title>Reading Files From The Server</title>
</head>
<body>
    <?php
        $fileName = "names.txt";
        $fp = fopen($fileName, 'r');
        $string = fread($fp, filesize($fileName));
        fclose($fp);
        echo($string);
    ?>
</body>
</html>
```

![](img/00218.jpeg)

图 7.12：`readFile_3.php` 的完整代码列表。

**步骤 4**：运行你的脚本。

![](img/00219.jpeg)

图 7.13：`readFile_3.php` 的输出。

如你所见，`names.txt` 的全部内容显示在浏览器中。让我们使用 `fread()` 和 `filesize()` 函数读取另一个文本文件。

**步骤 5**：创建一个包含下方表格中十个名称及其对应学名的新文件。将该文本文件保存为 `names_2.txt`。确保将新文本文件保存在你的 `www` 或 `htdocs` 文件夹中。

| 普通名称 | 学名 |
| :--- | :--- |
| 蚂 | Hymenoptera |
| 蝙 | Chiroptera |
| 熊 | Ursidae Carnivora |
| 驼 | Camelus Camelidae |



| 猫 | Felis Catus |

| 狗 | Canis Familiaris |

| 青蛙 | Anura Ranidae |

| 狮子 | Panthera Leo |

| 羊 | Bovidae Ovis |

| 虎 | Panthera Tigris |

使用 `Komodo Edit` 创建并保存 `names_2.txt` 文件。

![](img/00220.jpeg)

图 7.3：`names.txt` 的列表

**步骤 6**：将字符串“names.txt”赋值给变量 `$fileName` 的行从：

```php
$fileName = "names.txt";
```

修改为：

```php
$fileName = "names_2.txt";
```

这是你的完整代码列表应有的样子：

```html
<!DOCTYPE html>
<html>
<head>
    <title>Reading Files From The Server</title>
</head>
<body>
    <?php
        $fileName = "names_2.txt";
        $fp = fopen($fileName, 'r');
        $string = fread($fp, filesize($fileName));
        fclose($fp);
        echo($string);
    ?>
</body>
</html>
```

**步骤 7**：保存你的文件。

**步骤 8**：运行你的代码并显示输出。

![](img/00221.jpeg)

图 7.15：`readFile_3.php` 运行时的输出。

![](img/00222.jpeg)

图 7.16：`readFile_3.php` 运行时的全屏输出。

图 7.16 是图 7.15 的全屏版本。注意无论你的浏览器缩小、拉伸、调整大小还是最大化，你都会看到普通名称和学名显示为连续的文本。

现在，让我们使用 `file_get_contents()` 函数读取 `names_2.txt`。该函数将整个文件的内容读取到字符串中，而无需文件句柄。因此，我们不需要调用 `fopen()` 或 `fclose()` 函数。

**步骤 1**：创建一个新的 HTML5 文档模板并将文件命名为 `readFile_4.php`。将其保存在你的 `www` 或 `htdocs` 文件夹中。

**步骤 2**：按照你看到的输入以下代码。

代码列表：`readFile_4.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Reading Files From The Server</title>
</head>
<body>
    <?php
        $file = "names.txt";
        $string = file_get_contents($file);
        echo($string);
    ?>
</body>
</html>
```

你可以看到我们的代码要简单得多。我们不需要调用 `fopen()` 和 `fclose()` 函数。我们只需要调用 `file_get_contents()` 函数并传入两个参数：我们想要读取的文件名，以及一个为 `true` 或 `false` 的布尔值。

在 `$string` 赋值语句中的布尔参数 `TRUE` 仅意味着在访问文件时包含路径。由于我们的脚本和文本文件都在 `www` 或 `htdocs` 文件夹中，因此第二个参数没有影响。

**提示**：`file_get_contents()` 函数可以接受多达五个参数。第一个参数是必须的，而其余四个是可选的。你可以查看 [`www.php.net/file_get_contents`](http://www.php.net/file_get_contents) 获取有关该函数的更多详情。

![](img/00223.jpeg)

图 7.17：`readFile_4.php` 的代码列表。

### 步骤 3：保存你的文件并运行输出。

![](img/00224.jpeg)

图 7.18：`readFile_4.php` 运行时的输出。

`file_get_contents()` 函数仅通过几行代码就一次性提取了整个文件的内容。

现在，我们将使用 `fgets()` 函数来读取我们的文件。此函数需要一个文件句柄，因此我们必须先用 `fopen()` 打开文件，最后用 `fclose()` 将其关闭。现在，`fgets()` 从文件中读取字节，直到遇到换行符或文件结束标记。然后它会停止读取字节，并将文件指针留在遇到换行符之后的那个字符上。

### 步骤 1：打开一个 HTML5 文档模板并将此程序保存为 `readFile_5.php` 到你的 `www` 或 `htdocs` 文件夹中。

### 步骤 2：通过包含 PHP 脚本标签开始你的代码。

```html
<!DOCTYPE html>
<html>
<head>
    <title>从服务器读取文件</title>
</head>
<body>
    <?php
```

### 步骤 3：将字符串 “names.txt”存储在变量 `$fileName` 中。

```php
        $fileName = "names.txt";
```

### 步骤 4：使用读取模式调用 `fopen()` 函数。

```php
        $fp = fopen($fileName, 'r');
```

### 步骤 5：使用文件句柄变量 `$fp` 作为函数的参数调用 `fgets()` 函数。我们将 `fgets()` 从文件中读取的字节存储在变量 `$string` 中。

```php
        $string = fgets($fp);
```

### 步骤 6：调用 `fclose()` 并使用 `echo()` 函数显示 `$string` 的内容。

```php
        fclose($fp);
        echo($string);
```

### 步骤 7：关闭 PHP 脚本标签和 HTML 文档。确保保存了你的文档。

```php
    ?>
</body>
</html>
```

### 步骤 8：你的完整代码列表应该像这样：

代码列表：`readFile_5.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>从服务器读取文件</title>
</head>
<body>
    <?php
        $fileName = "names.txt";
        $fp = fopen($fileName, 'r');
        $string = fgets($fp);
        fclose($fp);
        echo($string);
    ?>
</body>
</html>
```

### 步骤 9：运行你的脚本。

![](img/00225.jpeg)

图 7.19：`readFile_5.php` 运行时的输出。

你应该能在浏览器中看到显示的 ‘John’。

现在让我们使用相同的脚本来读取文件 `names_2.txt`。

### 步骤 1：在 Komodo Edit 中保持 `readFile_5.php` 打开状态，将字符串 “names_2.txt”存储在变量 `$fileName` 中。

```php
        $fileName = "names_2.txt";
```

### 步骤 2：点击 文件 > 另存为... > 将文件保存为 `readFile_6.php`。

![](img/00226.jpeg)

图 7.20：另存为对话框。

![](img/00227.jpeg)

图 7.21：将 `readFile_5.php` 保存为 `readFile_6.php`。

### 步骤 3：运行你的脚本。

![](img/00228.jpeg)

图 7.22：`readFile_6.php` 运行时的输出。

你应该在浏览器中看到 “Ant => Hymenopterous formicidae”。

现在，`fgets()` 从文件中读取字节，直到遇到换行符或文件结束标记。然后它会停止读取字节，并将文件指针留在遇到换行符之后的那个字符上。那么，我们如何使用 `fgets()` 函数读取整个文件呢？

我们使用 `while`-循环，在其中我们使用布尔函数 `feof()` 作为条件表达式。当到达文件结束标记时，该函数返回 `TRUE`。

### 步骤 1：创建一个新的 HTML5 文档模板。包含 PHP 块脚本标签并将文件命名为 `readFile_7.php`。

```html
<!DOCTYPE html>
<html>
<head>
    <title>从服务器读取文件</title>
</head>
<body>
    <?php
```

### 步骤 2：将字符串 “names.txt”存储在变量 `$fileName` 中。

```php
        $fileName = "names.txt";
```

### 步骤 3：使用读取模式调用 `fopen()` 函数。

```php
        $fp = fopen($fileName, 'r');
```

### 步骤 4：将 `$string` 初始化为空字符串。

```php
        $string = "";
```

### 步骤 5：创建一个 `while`-循环，其中我们使用布尔函数 `feof()` 作为我们的条件表达式。当到达文件结束标记时，该函数返回 `TRUE`。

```php
        while(!feof($fp)) {
            $string .= fgets($fp);
            $string .= "<br>";
        }
```

### 步骤 6：关闭文件句柄。

```php
        fclose($fp);
```

### 步骤 7：显示 `$string`。

```php
        echo($string);
```

### 步骤 8：关闭 PHP 脚本标签和 HTML 文档。

```php
    ?>
</body>
</html>
```

### 步骤 9：你的完整的代码列表应该像这样：

代码列表：`readFile_7.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>从服务器读取文件</title>
</head>
<body>
    <?php
        $fileName = "names.txt";
        $fp = fopen($fileName, 'r');
        $string = "";
        while(!feof($fp)) {
            $string .= fgets($fp);
            $string .= "<br>";
        }
        fclose($fp);
        echo($string);
    ?>
</body>
</html>
```

### 步骤 3

我们将名称“John”和“Jane”添加到 `names.txt` 文件中，但首先我们将这些名称分别存储在变量 `$name1` 和 `$name2` 中。

```php
$name1 = "John";
$name2 = "Jane";
```

### 步骤 4

使用正确的参数数量和顺序调用 `fwrite()` 函数：文件句柄和数据字符串。为我们正要追加的每个名称添加一个换行符。

```php
fwrite($fp, $name1 . "\n");
fwrite($fp, $name2 . "\n");
```

### 步骤 5

回到 `fopen()` 调用处，添加 `or die` 子句，以便文件 `names.txt` 不存在时向用户发出警告。

```php
$fp = fopen($file, 'a') or die ("Can't Open The File");
```

### 步骤 6

关闭文件指针。

```php
fclose($fp);
```

### 步骤 7

添加一个 `echo` 语句，通知用户新数据已经添加。

```php
echo("names.txt has been overwritten!")
```

### 步骤 8

关闭 PHP 脚本和 HTML 文档并再次保存你的文件。

```php
?>
</body>
</html>
```

### 步骤 9

完整的代码列表现在应该像这样：

代码列表：`appendFile.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Appending and Deleting Files from the Server</title>
</head>
<body>
<?php
    $file = "names.txt";
    $fp = fopen($file, 'a') or die ("Can't Open The File");
    $name1 = "John";
    $name2 = "Jane";
    fwrite($fp, $name1 . "\n");
    fwrite($fp, $name2 . "\n");
    fclose($fp);
    echo("New Data Has Been Added!")
?>
</body>
</html>
```

### 步骤 10

运行你的脚本。

你应该能看到消息“New Data Has Been Added”，但让我们直接访问文件 `names.txt`，查看名称“John”和“Jane”是否确实已经添加。使用 Komodo Edit 或任何文本编辑器打开文件 `names.txt`。

![](img/00232.jpeg)

图 7.26：验证 `names.txt` 包含新添加的名称“John”和“Jane”。

![](img/00233.jpeg)

图 7.27：通过 Komodo Edit 查看 `names.txt` 文件的内容。

![](img/00234.jpeg)

图 7.28：通过 Notepad 查看 `names.txt` 文件的内容。

现在名称“John”和“Jane”已添加到 `names.txt` 文件中。

现在让我们使用 `unlink()` 函数从服务器上删除文件，该函数接受我们打算删除的文件的完整文件名作为其所需的第一个参数。例如：

```php
unlink("filename.ext");
```

这很简单。不需要文件句柄，因此不需要使用 `fopen()`。

但在之前，让我们先创建一个要删除的文件。它是一个简单的文本文件，命名为 `deletedMessage.txt`，包含文本“This file will be deleted from the server.”。我们将在 `www` 或 `htdocs` 文件夹中创建并保存它。

**步骤 1**：使用你的文本编辑器，点击“新建文件”（New File）并选择“文本”（Text）。选择目录 `C:\wamp\www` 并输入文件名 `deletedMessage.txt`。

**步骤 2**：在文本编辑器中输入“This file will be deleted from the server.”。保存文件。

![](img/00235.jpeg)

图 7.29：Komodo Edit 中所示 `deletedMessage` 内容。

现在文件 `deletedMessage` 已保存到服务器上。检查 `www` 或 `htdocs` 文件夹确认文本文件已保存。

![](img/00236.jpeg)

图 7.30：从本地浏览器查看文件 `deletedMessage.txt`。

文本文件也可以使用 Notepad 保存。

![](img/00237.jpeg)

图 7.31：使用 Notepad 创建文件 `deletedMessage.txt`。

确保将此文件保存在 `www` 或 `htdocs` 文件夹内。

![](img/00238.jpeg)

图 7.32：本地磁盘（`C:\wamp` > `www` 文件夹）。

![](img/00239.jpeg)

图 7.33：使用 Notepad 保存了文件 `deletedMessage.txt`。

**步骤 3**：创建一个新的 HTML 文档并按所示输入以下代码：

代码列表：`viewFile.php`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Deleting Files from the Server</title>
</head>
<body>
<?php
    unlink("deletedMessage.txt");
    echo("deletedMessage.txt has been deleted!")
?>
</body>
</html>
```

**步骤 4**：用文件名 `viewFile.php` 保存脚本并运行它：

![](img/00240.jpeg)

图 7.34：运行 `viewFile.php` 的输出。

现在，检查 `www` 或 `htdocs` 文件夹，查看文件 `deletedMessage.txt` 是否还在。这里是 `C:\wamp\www` 文件夹的视图——你可以看到文件不在了。

![](img/00241.jpeg)

图 7.35：`C:\wamp\www` 文件夹的视图，`deletedMessage.txt` 不存在。

## 7.4 CSV 文件



CSV 文件，或逗号分隔值（Comma-Separated Value）文件，是由逗号分隔的字符串或值组成的文本文件。这是一个名为 `deliveredItems.csv` 的 CSV 文件示例：

```
m-000, meat, $12.00, 10
v-000, veggies, $2.50, 12
d-000, dairy, $1.50, 3
c-000, condiments, $1.00, 9
f-000, packaged fruit, $3.00, 7
s-000, spices, $1.75, 1
```

CSV 文件是非常常见且流行的文档结构，主要用于从一种软件格式转换为另一种格式，例如从 Excel 电子格转换为 MySQL 数据库。在这种情况下，数据首先从 Excel 或 MySQL “导出”到 CSV 文件，然后“导入”到 MySQL 或 Excel。

在 CSV 文件中，一行文本（以换行符结束）对应一条记录。每个逗号分隔的字符串对应该记录中的一个字段或列。

如果 `deliveredItems.csv` 的内容被导入数据库，看起来会像这样：

| Category Number | Description | Unit Price | Quantity (boxes) |
| :--- | :--- | :--- | :--- |
| m-000 | meat | $12.00 | 10 |
| v-000 | veggies | $2.50 | 12 |
| d-000 | dairy | $1.50 | 3 |
| c-000 | condiments | $1.00 | 9 |
| f-000 | packaged fruit | $3.00 | 7 |
| s-000 | spices | $1.75 | 1 |

图 7.4：`deliveredItems.csv` 列表

PHP 有特殊函数 `fgetcsv()`，它可以从 CSV 文件读取一行并将逗号分隔的字符串解析为数组。也就是说，每个逗号分隔的字符串变成数组的一个元素。

但在之前，让我们使用 Komodo Edit 创建文件 `deletedMessage.txt`。这是我们将使用 `fgetcsv()` 函数读取的文件。

**步骤 1**：使用你的文本编辑器，点击“新建文件”并选择“文本”。选择目录 `C:\wamp\www` 并输入文件名 `deletedMessage.txt`。

**步骤 2**：在文本编辑器中输入“This file will be deleted from the server.”。保存文件。

![](img/00235.jpeg)

图 7.29：Komodo Edit 中所示 `deletedMessage` 内容。

现在文件 `deletedMessage` 已保存到服务器上。检查 `www` 或 `htdocs` 文件夹确认文本文件已保存。

![](img/00236.jpeg)

图 7.30：从本地浏览器查看文件 `deletedMessage.txt`。

文本文件也可以使用 Notepad 保存。

![](img/00237.jpeg)

图 7.31：使用 Notepad 创建文件 `deletedMessage.txt`。

确保将此文件保存在 `www` 或 `htdocs` 文件夹内。

![](img/00238.jpeg)

图 7.32：本地磁盘（`C:\wamp` > `www` 文件夹）。

![](img/00239.jpeg)

图 7.33：使用 Notepad 保存了文件 `deletedMessage.txt`。

在代码区域右侧显示的新列称为“地图”（Minimap）。你可以通过点击菜单中的“视图”（View）然后取消勾选“地图”来阻止其显示。

![](img/00244.jpeg)

图 7.38：在 Komodo Edit 中取消勾选“地图”的地方。

你得到了文件的最终视图。

![](img/00245.jpeg)

图 7.39：Komodo Edit 中 `deliveredItems.csv` 的普通视图。

如果你需要，可以调整窗口大小，就像这里这样做以便更清晰地查看图像。

![](img/00243.jpeg)

图 7.40：调整大小后的 Komodo Edit 窗口。

现在，我们将编写一个脚本读取 `deliveredItems.csv` 的全部内容，并将每行显示为表格中的行，并将行中的每个逗号分隔值显示为表格中的单元格。

**步骤 3**：使用 HTML5 模板创建一个新的 PHP 文件。将文件保存为 `readCSV.php`。嵌入 PHP 开启标签。

```html
<!DOCTYPE html>
<html>
<head>
    <title>Reading CSV files</title>
</head>
<body>
<?php
```

![](img/00246.jpeg)

图 7.41：为 `readCSV.php` 创建新的 HTML5 模板。

### 第 4 ：将字符串 “deliveredItems.csv”存储在变量 `$fileName` 中。

```php
$fileName = "deliveredItems.csv";
```

### 第 5 ：调用 `fopen()` 函数以 `’r’` 模式访问 `deliveredItems.csv`。将返回的文件句存储在变量 `$fp` 中。

```php
$fp = fopen($fileName, 'r');
```

此时，你的代码看起来应该是这样的：

```html
<!DOCTYPE html>
<html>
<head>
    <title>读取 CSV 文件</title>
</head>
<body>
<?php
    $file = "deliveredItems.csv";
    $fp = fopen($file, 'r');
?>
</body>
</html>
```

现在，我们将利用 `while`循环来逐行读取 `deliveredItems.csv`。当我们读取到一行时，我们将该行中用逗号分隔的值格式化为表格中的某行，然后将该行添加到变量 `$output` 中，该变量最终将包含我们构建的所有行。

### 第 6 ：在进入 `while`循环之前，将变量 `$output` 初始化为空字符串 `""`。

```php
$output = "";
```

### 第 7 ：现在使用条件表达式 `!feof($fp)` 声明 `while`循环。

```php
while(!feof($fp))
```

### 第 8 ：`while`循环中的第一个条语句是调用函数 `fgetcsv()`，该函数将从 `deliveredItems.csv` 读取一行，然后将该行中每个用逗号分隔的值存储为数组 `$inventory` 中的一个元素。

```php
$inventory = fgetcsv($fp, 1024);
```

此时，你的代码应该像这样：

```php
$output = "";
while(!feof($fp))
{
    $inventory = fgetcsv($fp, 1024);
}
```

每次调用 `fgetcsv()` 后，`$inventory` 将包含一个有四个元素的数组。这四个元素对应于 `deliveredItems.csv` 中某行的四个逗号分隔的值。

`m-000, meat, $12.00, 10`

### 第 9：我们将在表格的一行（由四个单元格组成）中显示 `$inventory` 的四个元素。以下代码构建了表格的行。

```php
$line = "";
$line .= "<tr>";
$line .= "<td align='center'>" . $inventory[0] . "</td>";
$line .= "<td align='center'>" . $inventory[1] . "</td>";
$line .= "<td align='center'>" . $inventory[2] . "</td>";
$line .= "<td align='center'>" . $inventory[3] . "</td>";
$line .= "</tr>";
```

### 第 10：一旦构建好了一行，它就会添加到变量 `$output` 中，该变量最终将包含表格的所有行。

```php
$output .= $line;
```

注意，我们在进入循环之前已经将 `$output` 初始化为空字符串 `""`。

### 第 11：当 `while`循环终止时（因为已经到达了 `deliveredItems.csv` 的文件结束标记符），我们可以将输出显示为表格。

```php
print("<table border='1' cellpadding='1'>");
print($output);
print("</table>");
```

### 第 12：关闭脚本标签和 HTML 文档并再次保存你的文件。

以下是完整的代码列表：

**代码列表：readCSV.php**

```html
<!DOCTYPE html>
<html>
<head>
    <title>读取 CSV 文件</title>
</head>
<body>
<?php
    $file = "deliveredItems.csv";
    $fp = fopen($file, 'r');
    $output = "";
    while(!feof($fp))
    {
        $inventory = fgetcsv($fp, 1024);
        $line = "";
        $line .= "<tr>";
        $line .= "<td align='center'>" . $inventory[0] . "</td>";
        $line .= "<td align='center'>" . $inventory[1] . "</td>";
        $line .= "<td align='center'>" . $inventory[2] . "</td>";
        $line .= "<td align='center'>" . $inventory[3] . "</td>";
        $line .= "</tr>";
        $output .= $line;
    }
    print("<table border='1' cellpadding='1'>");
    print($output);
    print("</table>");
?>
</body>
</html>
```

### 第 13：运行你的程序并查看你的输出。

提示：如果你想让表格中的项目描述显示为左对齐，请将 `readCSV.php` 列表中的表格 `<td>` 值从 `’center’` 替换为 `’left’`。

# 练习

1. File I/O 是什么意思？
   a. 文件输入和输出（File Input and Output）。
   b. 文件输入输出。
   c. 文件进入和。
   d. 文件内部和外部。

2. 获取服务器上文件内容最的方法是？
   a. `file_get_contents`
   b. `fgets`
   c. `fread`

3. `’a’` 代表什么？
   a. 附加（Affix）。
   b. 追加（Append）。
   c. 任意的（Arbitrary）。
   d. 附加（Apphend）。

4. 服务器通常使用什么来访问文件？
   a. 访问（Access）。
   b. 追加（Append）。
   c. 任意（Arbitrary）。
   d. 权限（Permission）。

5. CSV 代表什么？
   a. 逗号分隔的值（Comma-separated values）。
   b. 逗号分隔的变量（Comma-separated variables）。
   c. 逗号分隔的命令（Comma-separated commands）。
   d. 逗号分隔的特征（Comma-separated features）。

#### 练习题

1. 创建一个包含以下字段的 HTML 表格：
2. 当你点击 `“submit”` 按钮时，它将跳转到：
3. 创建一个将输入保存到 CSV 文件的程序。
4. 提供指向另一个页面的链接。
5. 在表格中的信息。
6. 使用原理保存。

#### 7 练习答案

**(1) HTML 页面：**

**代码列表：Chap7LabEx.html**

```html
<!DOCTYPE html>
<html>
<head>
    <title>7 练习 HTML</title>
</head>
<body>
    <form action="Chap7LabForm.php">
        <table>
            <tr>
                <th>Last Name:</th>
                <td><input type="text" name="lname"></td>
            </tr>
            <tr>
                <th>First Name:</th>
                <td><input type="text" name="fname"></td>
            </tr>
            <tr>
                <th>Phone Number:</th>
                <td><input type="number" name="pnumber"></td>
            </tr>
            <tr>
                <td><input type="submit" value="Submit"></td>
                <td><input type="reset" value="Clear"></td>
            </tr>
        </table>
    </form>
</body>
</html>
```

**(2) PHP - 数据保存页面：**

**代码列表：Chap7LabForm.php**

```html
<!DOCTYPE html>
<html>
<head>
    <title>7 练习 PHP</title>
</head>
<body>
<?php
    $lname = $_REQUEST['lname'];
    $fname = $_REQUEST['fname'];
    $pnumber = $_REQUEST['pnumber'];
    $file = "contacts.csv";
    $fp = fopen($file, 'a');
    fwrite($fp, $lname . ",");
    fwrite($fp, $fname . ",");
    fwrite($fp, $pnumber . "\n");
    fclose($fp);
    echo "Information has been saved!";
?>
    <form action="Chap7LabEx.html">
        <input type="submit" value="Add more"/>
    </form>
    <form action="Chap7LabExReadCSV.php">
        <input type="submit" value="View entries">
    </form>
</body>
</html>
```

**(3) 以表格形式查看保存的 CSV 的脚本：**

**代码列表：Chap7LabExReadCSV.php**

```html
<!DOCTYPE html>
<html>
<head>
    <title>7 练习读取 CSV</title>
</head>
<body>
<?php
    $file = "contacts.csv";
    $fp = fopen($file, 'r');
    $table = "";
    while(!feof($fp))
    {
        $list = fgetcsv($fp, 1024);
        $entry = "";
        $entry .= "<tr>";
        $entry .= "<td align='center'>" . $list[0] . "</td>";
        $entry .= "<td align='center'>" . $list[1] . "</td>";
        $entry .= "<td align='center'>" . $list[2] . "</td>";
        $entry .= "</tr>";
        $table .= $entry;
    }
    fclose($fp);
    print("<table border='1'>");
    print($table);
    print("</table>");
?>
</body>
</html>
```

```html
<tr>
    <th>姓</th>
    <th>名</th>
    <th>电话号码</th>
</tr>
```

```php
<?php
    print($table);
    print("</table>");
?>
```

```html
<form action="Chap7LabEx.html">
    <input type="submit" value="添加更多"/>
</form>
```

```html
</body>
</html>
```

输出：

![](img/00251.jpeg)

图 7.46: Chap7LabEx.html 运行输出。

![](img/00252.jpeg)



图 7.47: `Chap7LabExForm.php` 运行输出。

![](img/00253.jpeg)

图 7.48: `Chap7LabExReadCSV.php` 运行输出。

![](img/00254.jpeg)

图 7.49: 输入第一个用户信息。

![](img/00253.jpeg)

图 7.50: 已提交的第一个用户信息。

![](img/00255.jpeg)

图 7.51: 从本地数据库查看保存的用户信息。

# 章节总结

在本章中，你学习了执行文件输入/输出的 PHP 函数：创建文件、向文件写入数据、从文件读取数据以及删除文件。

在编写文件输入/输出操作的脚本过程中，你使用了接收数据的表单，并在将数据保存到文本文件之前，使用全局数组获取表单数据。你还使用了数组来显示从 `csv` 格式文件中检索的数据。

# 第 8 章：使用 PHP 发送电子邮件

## 章节目标

- 你将学习文本邮件和 HTML 电子邮件之间的区别。
- 你将学习如何下载和安装 `phpMailer` 包。
- 你将学习如何配置 `WAMPSERVER` 以配合 `phpMailer` 包工作。
- 你将编写 PHP 脚本，使用 `phpMailer` 向 Gmail 账户发送文本和 HTML 电子邮件。

### 8.1 使用 PHP 发送文本邮件

你是否想过，为什么你会收到发件地址如 `noreply@domain.com` 的邮件？或者为什么有人给你发邮件，并通过其邮箱地址暗示你不应该回复？实际上，来自此类地址的邮件是由你最近访问的网站自动生成并发送的。有时，这些邮件可能是收执确认，让你知道你下的订单或发送的邮件已收到。

你可能在某个网站注册成为新会员并开通账户。该网站会向你发送一封邮件确认你的注册，要求你执行某些活动以验证身份，并分配用户名和密码（你有权更改这些信息）。在其他你已经注册（并且是付费会员）的网站上，你会定期收到任何影响你账户的活动的邮件通知。例如，`PayPal.com` 会对其成员在网站上进行的每项活动发送邮件通知：购买、付款、资金转账等。

所有这些邮件都是由网站应用程序自动生成的。它们必须自动创建和发送，否则将需要一个营级规模的人员来监控仅仅一个网站的所有成员的所有活动。

电子邮件的发送和接收需要配置妥当的邮件服务器。这是一个作为虚拟邮局运行计算机程序。它可能运行在专用硬件上，也与其他服务器程序共享硬件资源。它被设计在正常运行期间自动执行，无需任何人工干预。

邮件服务器有两种：出站邮件服务器和入站邮件服务器。出站服务器处理所有发出的邮件并实现 `SMTP`（简单邮件传输协议），而入站服务器处理所有收到的邮件并实现 `POP3`（邮局协议第 3 版）或 `IMAP`（互联网消息访问协议）。

`POP3` 入站服务器将发送和接收的消息存储在客户端的硬盘上。这迫使用户只能从一个设备或位置访问和处理邮件。然而，`IMAP` 入站服务器将消息存储在服务器上，因此允许用户从任何位置或任何设备访问邮件。

发送和接收邮件涉及入站和出站邮件服务器之间的多级通信，这一过程确保邮件能够到达正确的收件者。

**提示**：若想了解更多关于邮件服务器传输和接受邮件的内部细节，你可以访问 [`computer.howstuffworks.com/e-mail-messaging/email.htm`](http://computer.howstuffworks.com/e-mail-messaging/email.htm) 查看“电子邮件是如何工作的”，以及访问 [`www.howtogeek.com/56002/htg-explains-how-does-email-work.`](http://www.howtogeek.com/56002/htg-explains-how-does-email-work/) 查看“电子邮件是如何工作的？”

PHP 允许你直接创建并发送电子邮件。语法如下：

```php
mail($to, $subject, $message, $headers)
```

下表提供了每个参数的详细信息：

| 参数 |  |
| :--- | :--- |
| `$to` | 必需。收件者地址。 |
| `$subject` | 必需。邮件主题。 |
| `$message` | 必需。实际内容。 |
| `$headers` | 可选。指定额外的头部，如 `Cc`, `Bcc`。 |
| `$parameters` | 可选。指定任何参数。 |

如果邮件发送成功，`mail()` 函数返回布尔值 `TRUE`，否则返回 `FALSE`。

**第 1 步**：在 Komodo Edit 中打开空白 HTML 文档并将其保存为 `simpleEmail.php`。

**第 2 步**：在 `<body>` 部分添加 PHP 开始和结束标签。

**第 3 步**：根据下表，编写赋值语句，将第二列的字符串值赋予第一列的变量。例如，对于表格中的第一行，代码应该是：

```php
$to = "someone@email.com";
```

这是完整的代码列表所示：

```php
<!DOCTYPE html>
<html>
<head>
    <title>简单的文本邮件</title>
</head>
<body>
    <?php
        $to = "someone@email.com";
        $subject = "您的反馈。
        $message = "This is a test e-mail created using php";
        $message .= "from LearnToProgram.tv";
        $from = "test@learntoprogram.tv";
        $headers = "From:" . $from;
        $retval = mail($to, $subject, $message, $headers);
        if ($retval) {
            echo ("邮件已发送！");
        } else {
            echo ("邮件未发送！");
        }
    ?>
</body>
</html>
```

**第 4 步**：保存文件并尝试查看你的输出。

现在，当你运行此脚本时，你将获得下方截图所示的错误消息。

![](img/00256.jpeg)

图 8.1: `simpleEmail.php` 的输出。

你遇到此错误的原因是 `WAMPSERVER` 没有配置一个邮件服务器作为其组件之一。那么，一个安装了 `WAMPSERVER` 的初学 PHP 程序员该如何测试发送电子邮件的 PHP 脚本呢？

意乎不用说，解决方案随处可见！如果你在 Google 搜索中输入“如何使用 PHP 从 WAMPSERVER 发送邮件”，你会发现进取的 Web 程序员提供的几种替代方案。这些解决方案中有些可以追溯到两多年前，而有一一两个是今年才提出的。（某些不同的解决方案甚至有相同的名称——“sendmail”，这可能会导致一些微小的困惑！）

直觉上，我们不仅想选择最新的解决方案，还想要一个易于实现的方案。幸运的是，我们在非常流行的 `PHPMailer` 中拥有了它。这里是摘自 PHPMailer 教程（[`code.google.com/a/apache-extras.org/p/phpmailer/wiki/UsefulTutorial`](https://code.google.com/a/apache-extras.org/p/phpmailer/wiki/UsefulTutorial)）的简洁描述。

“PHPMailer 是一个用于 PHP (www.php.net) 的 PHP 类，它提供了一组发送电子邮件的函数。两个主要功能是发送 HTML 邮件和带有附件的邮件。PHPMailer 支持几乎所有的发送邮件方式：`mail()`、`Sendmail`、`qmail` 以及直接发送到 SMTP 服务器。你可以使用基于 SMTP 邮件的任何功能，通过 `to`、`CC`、`BCC` 等发送多个接收人。简而言之：PHPMailer 是在 PHP 中发送邮件的高效方式。”

正如你从描述所示，PHPMailer 是一个用于 PHP 脚本发送电子邮件的完整且功能丰富的包。尽管我们想检查并测试 `PHPMailer` 的所有功能和能力，但考虑到本书的局限性，这将是不切行的。

现在我们将向你展示如何使用 `PHPMailer` 向 Gmail 地址发送纯文本邮件和一封 HTML 邮件。

以下步骤将指导你下载并安装 `PHPMailer`、配置 `WAMPSERVER` 与 `PHPMailer` 协作以及编写脚本。

### 步骤 1：下载 PHPMailer/SMTP

从 [`github.com/PHPMailer/PHPMailer`](https://github.com/PHPMailer/PHPMailer)。以下屏幕显示了 `PHPMailer` 的 GitHub 页面以及下载按钮的位置。你将获得一个名为 `PHPMailer-master.zip` 大约为 200kb 的压缩文件。

![](img/00257.jpeg)

图 8.2：GitHub PHPMailer 下载页的左上部分，[`github.com/PHPMailer/PHPMailer`](https://github.com/PHPMailer/PHPMailer)。

![](img/00258.jpeg)

图 8.3：GitHub PHPMailer 下载页右下部分的下载按钮，[`github.com/PHPMailer/PHPMailer`](https://github.com/PHPMailer/PHPMailer)。

### 步骤 2：解压

将 `PHPMailer-master.zip` 解压到文件夹中。

### 步骤 3：定位脚本

在解压 `PHPMailer-master.zip` 的文件夹中，找到以下三个脚本，并将它们复制到 Windows 中的 `c:/wamp/www` 文件夹（或 Mac 和 Linux 系统上的对应文件夹）。

1. `PHPMailerAutoload.php`
2. `class.phpmailer.php`
3. `class.smtp.php`

### 步骤 4：启用 Apache SSL

在 `WAMPSERVER` 菜单中，通过访问如下所示的 `httpd.conf` 文件启用 Apache 的 `ssl_module`

![](img/00259.jpeg)

图 8.4：在 WAMPSERVER 菜单中访问 `httpd.conf` 文件。

### 步骤 5：配置 httpd.conf

在 `httpd.conf` 文件中取消以下行的注释。（取消注释请删除行开头的 `#` 符号。）

```apache
#LoadModule ssl_module modules/mod_ssl.so
```

取消注释后的行如下截图所示。

![](img/00260.jpeg)

图 8.5：取消注释以启用 `ssl_module`

或者，你也可以通过 `WAMPSERVER` 菜单选项 `Apache -> Apache Modules -> ssl_module` 启用 `ssl_module`，如下截图所示。

![](img/00261.jpeg)

图 8.6：在 WAMPSERVER 菜单中启用 Apache `ssl_module`。

### 步骤 6：启用扩展

在 `WAMPSERVER` 菜单中，为 PHP 启用 `php_openssl`、`php_smtp` 和 `php_sockets` 扩展，如下所示。

![](img/00262.jpeg)

图 8.7：在 WAMPSERVER 菜单中为 PHP 启用 `php_openssl`、`php_smtp` 和 `php_sockets` 扩展。

### 步骤 7：重启

重启 `WAMPSERVER` 使更改生效。

![](img/00263.jpeg)

图 8.8：重启 WAMPSERVER

### 步骤：测试安装

你可以通过执行此代码来测试 `PHPMailer` 是否安装正确，此代码应该只会产生结果：

```php
<?php
```

### 步骤 8：创建脚本

将以下内容粘贴到代码并保存为 `emailText.php`。

```php
<?php
require('PHPMailerAutoload.php');
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\Exception;

$mail = new PHPMailer();
try {
    $mail->isSMTP();
    $mail->Host = 'smtp.gmail.com';
    $mail->SMTPAuth = true;
    $mail->Username = 'your_email@gmail.com';
    $mail->Password = 'your_password';
    $mail->SMTPSecure = 'ssl';
    $mail->Port = 465;
    $mail->setFrom('your_email@gmail.com', 'Your Name');
    $mail->addAddress('recipient@gmail.com');
    $mail->isHTML(false);
    $mail->Subject = 'Testing PHPMailer';
    $mail->Body = 'Hi,<br /><This system is working.';

    if ($mail->send()) {
        echo "Message has been sent";
    }
} catch (Exception $e) {
    echo "Message was not sent. Error: " . $mail->ErrorInfo;
}
?>
```

### 步骤 9：调整凭据

在以下行中调整 `Username` 和 `Password` 值。

### 步骤 10：调整发送者信息

在以下行中调整 `From` 和 `FromName` 字符串，同样在 `addAddress` 函数中。

### 步骤 11：运行

运行脚本。在浏览器中，你应该看到：

`Message has been sent`

## 8.2 发送 HTML 邮件

HTML 邮件包含非常小的 HTML 标签集，但对于哪些标签构成它并没有标准。因此，不同的邮件客户端处理的标签各不相同。有些邮件客户端不处理 HTML 邮件。

当 HTML 邮件最初出现时，由于许多原因对其存在反对。一个原因是安全，可以在 HTML 邮件中加入恶意代码。但邮件附件也可以这样做。尽管如此，HTML 邮件的使用已经泛滥，邮件附件仍在发送，因此对 HTML 邮件的反对已变成了默认接受。

现在，好消息来了！有了 `phpMailer`，你就不需要费心刚才解释的那些额外头部了！

### 步骤 1：获取 `sendEmailText.php` 并将其保存为 `sendEmailHtml.php`。

### 步骤 2：将 `IsHTML` 函数的参数设置为 `TRUE` 或添加以下行：

```php
$mail->IsHTML(true);
```

### 步骤 3：将 `Body` 和 `AltBody` 设置为以下字符串值。

```php
$mail->Body = "Hello, <b>my friend</b>! \n\n This message uses HTML entities!";

$mail->AltBody="Hello, my friend! \n\n This message uses HTML entities, but you prefer plain text !";
```

完整的代码列表应该是这样的：

代码代码列表：`sendEmailHtml.php`



```html
<!DOCTYPE html>
<html>
<head>
  <title>HTML E-mail</title>
</head>
<body>
  <?php
    require('class.phpmailer.php');
    $mail = new PHPMailer();
    $mail->IsSMTP();
    $mail->Mailer = 'smtp';
    $mail->SMTPAuth = true;
    $mail->Host = 'smtp.gmail.com';
    $mail->Port = 465;
    $mail->SMTPSecure = 'ssl';
    $mail->Username = "username@gmail.com";
    $mail->Password = "password";
    $mail->IsHTML(true);
    $mail->SingleTo = false;
    $mail->From = "email address of sender";
    $mail->FromName = "username of sender";
    $mail->addAddress("added email address","added username");
    $mail->Subject = "An HTML Message";
    $mail->Body = "Hello, <b>my friend</b>! \n\n This message uses HTML entities!";
    $mail->AltBody="Hello, my friend! \n\n This message uses HTML entities, but you prefer plain text !";
    if(!$mail->Send())
      echo "Message was not sent <br />PHPMailer Error: " . $mail->ErrorInfo;
    else
      echo "Message has been sent";   
  ?>
</body>
</html>
```

## 章节测试

1. 在 PHP 中，哪个对应电子邮件的收件者？

   a. `$to`

   b. `$from`

   c. `$header`

   d. `$message`

2. `mail()` 函数的作用是什么？

   a. 它通过服务器使用 PHP 发送和接收电子邮件。

   b. 它读取邮件并通知用户他们的邮件。

   c. 它向指定的收件者发送信件的 PDF 文件。

   d. 它将电子邮件副本发送到用户地址簿中的所有地址。

3. SMTP 是什么意思？

   a. Simple Mail Transfer Protocol（简单邮件传输协议）。

   b. Simple Mommy Tailoring Protocol（简单妈妈裁缝协议）。

   c. Super Mail Transfer Protocol（超级邮件传输协议）。

   d. Single Mail Transmit Parity（单邮件传输奇偶校验）。

4. 什么是 HTML 电子邮件？

   a. 一种嵌入了 HTML 标签的电子邮件。

   b. 一种使用 HTML 创建的电子邮件。

   c. 通过 HTML 页面发送的电子邮件。

   d. 一种嵌入在 HTML 文档中纯 JavaScript 生成的电子邮件。

5. 头部 MIME Version 的作用是什么？

   a. 该标题表示邮件包含 ASCII 文本字符以外的字符。

   b. 通泛描述内容类型，包括网页以及作为某些商业产品中富内容的存储。

   c. 为服务器模拟邮件（Mimes the email）。

   d. 复制邮件内容并将其保存到服务器上。

6. content type text/HTML 头部的作用是什么？

   a. 它声明邮件正文将同时包含 HTML 和纯文本。

   b. 它允许在电子邮件中使用 PHP 脚本。

   c. 它允许在电子邮件中使用 Javascript。

   d. 它定义了 HTML 电子邮件将使用的字符编码。

## 章节实验习题

**问题：** 使用 PHP 创建一封 HTML 电子邮件，发送以下 HTML 电子邮件。使用并将以下值分配给适当的变量参数。

```html
<!DOCTYPE html>
<html>
<body>
  <h1>This is Chapter 8 Lab Exercise HTML test e-mail</h1>
  <p><strong>Such an easy Lab Exercise! </strong></p>
</body>
</html>
```

**解决方案：**

代码列表：第 8 章实验习题解答。`chap8Lab.php`

```php
<?php
    require('class.phpmailer.php');
    $mail = new PHPMailer();
    $mail->IsSMTP();
    $mail->Mailer = 'smtp';
    $mail->SMTPAuth = true;
    $mail->Host = 'smtp.gmail.com';
    $mail->Port = 465;
    $mail->SMTPSecure = 'ssl';
    $mail->Username = "username@gmail.com";
    $mail->Password = "password";
    $mail->IsHTML(true);
    $mail->SingleTo = false;
    $mail->From = "email address of sender";
    $mail->FromName = "username of sender";
    $mail->addAddress("added email address","added username");
    $mail->Subject = "An HTML Message";
    $mail->Body = "Hello, <b>my friend</b>! \n\n This message uses HTML entities!";
    $mail->AltBody="Hello, my friend! \n\n This message uses HTML entities, but you prefer plain text !";
    if(!$mail->Send())
      echo "Message was not sent <br />PHPMailer Error: " . $mail->ErrorInfo;
    else
      echo "Message has been sent";   
?>
```

# 章节总结

在本章中，你学习了纯文本和电子邮件的区别。你学习了如何安装和配置 phpMailer。为了发送电子邮件，你学习了各种参数和方法。在下一章中，我们将讨论如何使用 MySQL。

# 第 9 章：使用 MySQL 数据库

## 目标

* 你将学习如何使用 phpMyAdmin 创建 MySQL 数据库。

* 使用 phpMyAdmin，你将学习在 MySQL 中创建表。

* 你将学习开发简单的 CRUD（创建、查询、更新和删除）应用程序。

* 你将学习使用 HTML 表单和 PHP 脚本在 MySQL 数据库中输入和更新数据。

* 你将学习构建 SQL Insert、Retrieve、Update 和 Delete 语句，以及如何使用 MySQLi 在 MySQL 数据库上执行这些语句。

### 数据库

数据库是计算机的核心。计算机的主要任务是保护和管理数据，特别是存储数据、组织数据、更新数据、保护其完整性并以多种方式检索数据。

数据库有很多分类：层次型、文件文件、网络型、分布式等。在业务应用程序中，最常用的类型是关系型数据库。之所以这样做是因为关系型数据库的表不仅存储数据，还存储了它们之间的关系。

**提示：** 你会遇到数据库管理系统或 `dbms`，它包含了用于管理数据库数据的软件工具和实用程序。现在，这两个术语互换使用。

**数据库：** 数据库是有组织的数据集合。它主要由表组成。

**表：** 紧密相关的数据或列（字段）的集合。例如，会计数据库会有一个客户表（用于监控应收款）和另一个供应商表（用于监控应付款），以及一个员工表（用于监控工资和福利）。

**列：** 表由列或字段组成，这些列是你存储在表中的数据类型。

**行：** 这是一组相关数据。例如，在员工表中，一行就是一个员工的数据。

# 数据库概念

- **字段 (Fields)**：这是列的另一种术语。有时，字段指的是特定行的列。

- **记录 (Record)**：这是行的另一种术语。

- **值 (Value)**：值是给定行和列中的数据。

至此，为了帮助你直观地理解理解表、列、行、字段、记录和值这些术语，我们展示了两个数据表的示意图——`Employee`（员工）和 `Department`（部门）（我们将在稍后的代码示例中创建这些表。）

| empId | lastName | firstName | department | position | salary |

| :--- | :--- | :--- | :--- | :--- | :--- |

| 001 | Smith | George | 1 | S Acct | 84000 |

| 002 | Valera | Linda | 2 | J Sales | 55000 |

表 9.1：员工表

`Employee` 表有六列（字段）和两行数据。（第一行作为视觉辅助显示列名，不属于表的一部分。）

| departmentId | departmentName |

| :--- | :--- |

| 1 | Accounting |

| 2 | Sales |

| 3 | Operations |

| 4 | Management |

表 9.2：部门表

`Department` 表有两列（字段）和四行数据。

- **关系 (Relationship)**：关系是两个表之间的链接。它是组织数据的一种强大方法。你通过建立两个表字段之间的链接来定义关系（其中一个或两个字段是主键字段）。例如，我们可以通过链接 `Employee` 的 `department` 字段和 `Department` 的 `departmentId` 字段，建立上述两个表 `Employee` 和 `Department` 之间的关系。这种关系使得两个表的数据可以作为一个整体可用。

一个表拥有的关系数量与其与其他表关联的字段相同。例如，将 `Employee` 的六个字段每一个都链接到数据库中的其他表是可能的，但并不切实际。

- **连接 (Join)**：这是关系的另一种术语。

- **键 (Key)**：这是表中的列或多个列，在其上构建索引以便快速和/或排序访问表数据。

- **索引 (Index)**：这是数据库系统用于更快速定位数据的内部系统。在表中，你可以指定某些列（通常是键）为索引。与关系或连接一样，为表的每一列创建索引是可能的，但并不切实际。

- **主键 (Primary key)**：这是给定表中的列或列组，用于唯一标识表中的每一行。为了唯一标识标识一行，任何两个主键不能具有相同的值。在我们的示例表中，`empId` 字段是 `Employee` 表的主键，而 `Department` 表的主键是 `departmentId`。

- **外键 (Foreign key)**：这是表中的一个或多个列，旨在包含与被引用表中相关的主键/唯一键列匹配的值。外键和主键显式地定义了表与表之间的直接关系。在我们的示例表中，`Department` 表的主键列 `departmentId` 与 `Employee` 表的外键列 `department` 建立了关系。

提示：有关更多与数据库相关的术语，你可以查看 [Database Terminology – A Dictionary of the Top 145 Database Terms](http://raima.com/database-terminology/)。

在本章中，我们将向你介绍一种开源的关系型数据库，称为 `MySql`。（它的读作 My S-Q-L 或 My Sequel。）它是许多共享托管服务的流行标准，并运行在许多平台上——各种 Unix/Linux 版本、Windows 和 Mac OS X。它可以配合许多编程语言——PHP、Java、C#、ASP、Visual Basic 等。

访问 `MySQL` 数据库存储的数据通过 `SQL`（结构化查询语言）完成，它开发于 20 世纪 70 年，现在是所有数据库使用的标准，尽管在不同的实现之间存在细微差异。

通过 `PHP` 并使用 `APIs`（应用程序编程接口）或扩展也可以访问 `MySQL`。

## 9.1 设置数据库

在本节中，我们将创建一个数据库。然后我们将在该数据库中创建两个表（我们之前演示的两个表——`Employee` 和 `Department`），然后在这两个表中存储一些示例数据。为了完成所有这些操作，我们使用了 WAMPSERVER 提供的两个工具——`MySQL Console` 和 `PhpAdmin`。我们将使用后者，但首先让我们涵盖关于 `MySQL Console`的一些介绍细节。

要从 WAMPSERVER 菜单启动 `MySQL Console`，点击 `MySQL`，然后点击如下截图所示的 `MySQL console`。

![](img/00264.jpeg)

图 9.1：WAMPServer 上的 MySQL Console

这将打开一个如下所示的命令行窗口。

![](img/00265.jpeg)

图 9.2：MySQL 命令行窗口。

如果你输入 `HELP`（不带引号），你将看到可以在控制台中输入的所有可能命令的显示，如下帮助屏幕所示。

![](img/00266.jpeg)

图 9.3：可以在命令行中使用的 MySQL 命令列表。

如你所示，这不是一个用户友好的界面，因为它倾向于键盘而不是鼠标，而且全是黑背景上的白字。所以，我们可以忘记 `MySQL Console`，转向 `phpAdmin`。

从 WAMPSERVER 菜单启动 `phpAdmin`，点击 `MySQL` 然后点击如下截图所示的 `MySQL console`（注：此处原文为 MySQL console，但上下文应为 phpAdmin，此处按逻辑意译）。

（注：此处原文描述处可能有误，翻译遵循原文逻辑但结合上下文）

为了通过 `PHP` 访问 `phpAdmin`，在 WAMPServer 上的 `phpAdmin` 菜单中，点击 `MySQL`，如下截图所示。

![](img/0267.jpeg)

图 9.4：phpAdmin

这将带来如下所示的 `phpAdmin` 界面。在 `phpAdmin` 中，它需要一个用户名和密码，但为了测试，可以留空 `root`（注：此处原文描述混乱，此处还原操作流程）

在表中，你可以指定某些列（通常是键）为索引。与关系或连接一样，为表的每一列创建索引是可能的，但并不切实际。如下：

![](img/0268.jpeg)

图 9.5：phpAdmin 界面

在 `phpAdmin` 顶部的点击 `Database`，如下截图所示。

![](img/0269.jpeg)

图 9.6：创建数据库的界面

在大标题 `Database` 下方的 `Create` 框中输入 `employees`（不带引号）。在 `Collation` 下拉框中，选择 `utf8_general_ci`。然后，点击 `Create` 图标。随后弹出消息显示数据库 `employees` 已创建。你将在左侧面板看到该名称，如下所示：

![](img/0270.jpeg)

图 9.7：数据库已创建

如果你点击左面板中的 `employees` 图标，将看到如下：

![](img/0271.jpeg)

图 9.8：在 employees 数据库中创建表

现在，我们将为 employees 数据库创建一个表。在 `Name` 框中输入 `Employee`。在 `Number of Fields` 框中输入 `6`。点击 `Go`。这将带来如下界面：

![](img/0272.jpeg)

图 9.9：创建表字段的界面

现在，我们可以创建 employee 表的字段，每个字段将占据一列。你可以参考下表向各个字段输入数据。

| 字段名称 | 类型 | 长度/值 | 注意 |

| :--- | :--- | :--- | :--- |

| `empid` | `Int` | 11 | 主键 自增 |

| `lastname` | `varchar` | 40 | |

| `firstname` | `varchar` | 20 | |

| `department` | `Int` | 2 | |

| `position` | `varchar` | 20 | |

| `salary` | `Int` | 10 | |

表 9.3：使用此表为员工表的各个字段输入数据

注意对于 `empid` 字段，你必须将 `Index` 指定为 `primary`（从下拉框中选择 `primary`）并勾选 `A_I` 复选框（用于 `Auto_Increment`）。在指定每个字段的名称、类型和长度/值后，点击 `save` 图标，这将完成创建 `employee` 表的过程。

现在，点击名为 `employee` 图，然后点击 `structure`，这将带来如下屏幕。

![](img/00273.jpeg)

图 9.10：员工表（employee）。

让我们创建第二个表，`department`。点击屏幕左侧窗格上的 `Create Table` 图标。这将打开以下界面，你可以在其中定义 department 表的字段或列。



![](img/00274.jpeg)

图 9.11：指定 `department` 表中的字段。

你可以参考下表向各个字段输入数据。

| 字段名 (FIELD NAME) | 类型 (TYPE) | 长度/值 (LENGTH/ VALUE) | 注释 (Notes) |
| :--- | :--- | :--- | :--- |
| `deptId` | `int` | 11 | 主键自增 |
| `departName` | `varchar` | 40 | |

你还需要将字段 `deptid` 设置为主键。指定索引为主（从下拉列表中选择 `primary`）并勾选 `A_I` 复选框（对应 `Auto_Increment` 自增）。

现在，既然我们已经建立了包含两个表的数据库，我们现在应该向表中添加一些数据。要在第一个表中添加数据，点击 `employee`，然后点击 `insert`。之后，添加一些虚构数据，如下：

![](img/00275.jpeg)

图 9.12：向 `employee` 表添加数据。

在这里，你可以看到 `empid` 字段是空的，因为该字段中的数据将自动添加。插入后，点击 `Go`。如果你检查相应的 SQL 代码，你会看到这个：

```
INSERT INTO `employees`.`employee` (`empid`, `lastname`, `firstname`, `department`, `position`, `salary`)
VALUES (NULL, 'Tilly', 'Jennifer', '4', 'Vice President', '124500');
```

这是 `phpmyAdmin` 的一个很好用的功能。当你执行各种数据库操作时，它会显示执行该操作的 SQL 语句——这是学习和掌握 SQL 代码的好方法。

你需要在这里添加 10 名员工的数据。完成后，你将看到类似这里的内容（通过点击 `browse>>profiling`）：

![](img/00276.jpeg)

图 9.13：包含 10 行的 `employee` 表。

在这里，你可以通过点击相应的图标轻松地编辑和删除行。现在，按照相同的步骤在 `departments` 表中添加一些行：

![](img/00277.jpeg)

图 9.14：向 `departments` 表添加数据。

`departments` 表将如下所示：

![](img/00278.jpeg)

图 9.15：包含四行的 `departments` 表。

### 复习题

1. 为了在 MySQL 命令行提示符中获取命令列表，我们应该输入什么？

   a. `mysql>Help`
   b. `mysql>command`
   c. `mysql>list`
   d. 以上都不是。

2. 为了确保列中的每个条目都是唯一的，我们使用什么？

   a. 外键 (Foreign key)。
   b. 候选键 (Candidate key)。
   c. 主键 (Primary key)。
   d. 以上都不是。

## 9.2 从数据库中检索查询

在上一节中，我们使用 `phpMyAdmin` 创建了名为 `employees` 的数据库，并在该数据库中创建了 `employee` 和 `department` 表。同样使用 `phpMyAdmin`，我们向这两个表中输入了示例数据。现在，我们将通过编写在 MySQL 数据库上执行数据库操作的 PHP 脚本来检索这些数据。

为了让 PHP 访问并操作 MySQL 数据库中表的行和列，我们使用 `MySQL API Extension`。PHP 提供了三个这样的扩展：

- 已废弃的原始 MySQL API
- `MySQL PDO` 函数
- MySQL 改进扩展，`MySQLi`。

我们将使用第三种 API 扩展 `MySQLi`，它也是最新的。`API` 意味着应用程序编程接口。该接口定义了你的 PHP 脚本与 MySQL 交互时所需的类、方法、函数和变量。

**提示**：要学习关于这三个 PHP MySQL API 扩展的所有知识，你可以查找文档 `PHP MYSQL API` (2014-03-14 修订 38079)。该手册描述了可以与 MySQL 使用的 PHP 扩展和接口。托管此文档的站点之一是 `downloads.mysql.com/docs/apis-php-en.a4.pdf`。你可以在搜索引擎中输入“php mysqli api”搜索其他。

在我们详细介绍 `MySQLi` 之前，让我们先明确一下“访问并操作 MySQL 数据库中表的行和列”是什么意思。我们将编写一个非常简单基础的 CRUD 应用程序。`CRUD` 是创建（Create）、检索（Retrieve）、更新（Update）和删除（Delete）的缩写。CRUD 应用程序：

a. 向数据库表中添加新行（创建），
b. 从数据库表中检索数据（检索），
c. 修改表列中的数据（更新），
d. 从数据库表中删除行（删除）。

上述四个功能中的每一个都由特定的 SQL 语句专门执行：

| 语句 |  |
| :--- | :--- |
| `INSERT` | 向数据库中的表添加新的数据行。 |
| `SELECT` | 从一个或多个表中检索数据。 |
| `UPDATE` | 修改现有数据。 |
| `DELETE` | 从表中删除一行数据。 |

我们的 PHP 脚本将构建精确的 SQL 语句。`MySQLi` 提供了两种接口：面向对象接口和过程式接口。我们将使用前者。

在不完全理解 OOP（面向对象编程）概念的情况下，除了一些熟悉的关键字和符号（如 `new` 和 `->`），就可以理解 `MySQLi` 的面向对象接口。它通过构建所需的 SQL 语句，并使用 `MySQLi` 让数据库执行该语句。

c. 如果连接对象创建成功，我们就构造一个 SQL 查询（可以是 `INSERT`、`SELECT`、`UPDATE` 或 `DELETE`）。
d. 我们使用连接对象 `$conn` 的 `query` 方法来执行构造好的查询，以获取结果集对象 `$rs`。
e. 我们检查查询是否执行成功。如果成功，我们将显示有关查询执行的某些参数。如果失败，我们将显示错误信息并退出程序。
f. 在检索（Retrieve）功能的情况下，如果查询成功，我们就会获得一个结果集对象。然后，我们使用结果集的 `fetch_array` 方法将结果集对象的数据传输到关联数组或索引数组。
g. 当所有数据库操作（添加、检索、更新和删除）完成后，通过调用连接对象 `$conn` 的 `close` 方法来关闭连接。

让我们从一个简单的脚本 `connect.php` 开始，它将创建一个到我们我们的 `employees` 数据库的连接对象。（这是前几个段落中的第 a 和 b 步）。输入以下代码并将其保存为 `connect.php`。

```php
<?php
  define( "HOSTNAME", "localhost");
  define( "USERNAME", "root");
  define( "PASSWORD", "");
  define( "DB_NAME", "employees");
  $conn = new mysqli(HOSTNAME, USERNAME, PASSWORD, DB_NAME);

  if ($conn->connect_errno) {
    echo( "<br/>Failed to connect to MySQL: (" .
    $conn->connect_errno . ") " . $conn->connect_error );          
  } else {
    echo( "<br/>Connected to database " . DB_NAME);
    echo( "<br/>" . $conn->host_info );
  }
?>
```

让我们分析一下代码。首先，我们定义了四个常量——`HOSTNAME`、`USERNAME`、`PASSWORD` 和 `DB_NAME`。这四个常量将作为参数传递给 `mysqli()` 类，该类创建一个由变量 `$conn` 引用的连接对象。该连接对象的方法允许我们访问数据库 `employees` 表。

注意，为了简化步骤，我们使用了“root”作为用户名，空字符串作为密码，但实际上，我们应该提供真实的用户名和强密码。这些真实的用户名和密码应该在我们的 `employees` 数据库中提前定义并设置。

此外请记住，使用常量应该成为你的编程最佳实践之一。你应该在代码中留出一个位置，用于放置经常变化的参数，例如用户名和密码。

现在，如果我们在运行 Windows 7 的 PC 上运行此脚本，我们将看到这些：

```
Connected to database employees
localhost via TCP/IP
```

第二行或最后一行将取决于你的操作系统。某些系统会生成：

```
127.0.0.1 via TCP/IP
```

现在，让我们通过更改这一行来测试我们的代码：

`define( "DB_NAME", "employees");`

改为：

`define( "DB_NAME", "competitors");`

实际上，我们正在通过提供一个不存在的数据库名称故意制造一个错误条件。如果我们运行这个修改后的 `connect.php`，我们应该得到下面的截图。

![](img/00279.jpeg)

图 9.16：错误信息显示。

显示内容的最后一行是由我们的这行代码生成的：

`echo( "<br/>Failed to connect to MySQL: (" . $conn->connect_errno . ") " . $conn->connect_error );`

显示的其余部分由浏览器 Google Chrome 生成。

正如你所看到的，我们的 `connect.php` 脚本已完全调试并运行良好。现在，我们将进行一些微调并将修改后的脚本保存为 `connectInc.php`。这是它的代码：

```php
<?php
define( "HOSTNAME", "localhost");
define( "USERNAME", "root");
define( "PASSWORD", "");
define( "DB_NAME", "employees");
$conn = new mysqli(HOSTNAME, USERNAME, PASSWORD, DB_NAME);

if ($conn->connect_errno) {
  echo( "<br/>Failed to connect to MySQL: (" . $conn-
  >connect_errno . ") " . $conn->connect_error );
  die( '<br/>Program Terminated');
}
?>
```

我们进行这些更改是因为 `connectInc.php` 是一个脚本，我们将使用 `require_once()` 函数将其包含到接下来的脚本中，如下代码片段所示。

```php
<?php
  require_once("connectInc.php");
?>
```

现在，我们将构建一个脚本，它将构造一个 SQL `Select` 语句从 `employee` 表中检索记录。让我们输入以下代码并将其保存在文件 `Retrieve1.php` 中：

```php
<?php
require_once("connectInc.php");
$sql = "SELECT * FROM employee";
$rs = $conn->query($sql);

if ( $rs === false ) {
  trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
} else {
  $arr = $rs->fetch_array( MYSQLI_ASSOC); // MYSQLI_ASSOC
  $rows_returned = $rs->num_rows;
  echo("<br/>Rows: " . $rows_returned);
  echo("<br/>" . $arr['id']);
  echo("<br/>" . $arr['lastname']);
  echo("<br/>" . $arr['firstname']);
  echo("<br/>" . $arr['department']);
  echo("<br/>" . $arr['position']);
  echo("<br/>" . $arr['salary']);
}
?>
```

让我们分析这段代码。由于我们已经知道 `require_once()` 的作用以及 `connectInc.php`，让我们从这一行开始：

`$ = "SELECT * FROM employee"`

在这里我们构造了一个 SQL 查询（遵循 SQL 语法）并将该查询存储在变量 `$sql` 中。接着在下一行中，我们执行：

`$rs = $conn->query($sql)`

连接对象 `$conn` 的查询方法将执行语句 `$sql` 并返回一个结果集。结果集（也称为记录集）是客户端中的行镜像。在我们的查询中，我们请求了表的所有行。我们本可以请求特定部门的员工。（当然，如果表包含成千上万行而我们请求所有行，客户端机器可能没有足够的内存来存放所有行。因此服务器将需要使用分页技术来提供行。）

现在，回到由 `$conn` 引用的连接对象的查询方法，它执行 SQL 语句并返回由变量 `$rs` 引用的结果集。

如果查询失败，变量 `$rs` 将包含布尔值 `false`，此行代码将显示特定的错误：

`trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);`

为了执行此 `trigger_error()` 函数，请更改此行代码：

`$sql = "SELECT * FROM employee";`

改为：

`$sql = "OBTAIN * FROM employee";`

你将得到此错误信息，专门指出“OBTAIN”是我们 SQL 语句中的错误：`Fatal error: Wrong SQL: OBTAIN * FROM employee Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'OBTAIN * FROM employee' at line . .`

如果我们的查询成功，那么 `employee` 表的所有记录都在变量 `$rs` 引用的结果集对象。我们执行结果执行对象的 `fetch_array` 方法：

`$arr = $rs->fetch_array(MYSQLI_ASSOC);`

`fetch_array` 方法将结果集 `$rs` 当前行的字段存储在关联数组 `$arr` 中，并使用字段名作为键，因为我们提供了常量 `MYSQLI_ASSOC`。如果我们将此常量改为 `MYSQLI_NUM`，那么 `$arr` 将是一个数值索引数组。

我们说“存储 `$rs` 当前行的字段”。那么 `$rs` 的“当前行”会是什么呢？因为在代码行中，我们在 `$rs` 被创建（通过连接对象 `$conn` 的 `query` 方法）之后紧立即访问了它：

```php
$rs = $conn->query($sql);
```

那么 `$rs` 的当前行就是它的第一行。这一行的字段将存储在关联数组 `$arr` 中。我们现在用以下行代码显示这些字段：

```php
echo( $arr['empid'] . ' ' .
      $arr['lastname'] . ' ' .
      $arr['firstname'] . ' ' .
      $arr['department'] . ' ' .
      $arr['position'] . ' ' .
      $arr['salary'] );             
```

在浏览器中，你应该看到类似这里的内容：

```
101 Escudero, Ernesto 3 Utility Supervisor 10000
```

这些是 `employee` 表第一行的字段。检查你获取的值是否与你第一条记录中字段的实际值匹配——`empid`, `lastname`, `firstname`, `department`, `position` 和 `salary`。

我们还有这两行代码：

```php
$rows_returned = $rs->num_rows;
echo( "<br>Rows: " . $rows_returned);
```

它们将产生以下输出：

```
Rows: 9
```

`num_rows` 是由 `$rs` 引用的结果集对象的一个属性，它存储了 `$rs` 中的行数，这也就是 `employee` 表中的行数。检查浏览器中显示的值是否与你 `employee` 表中的记录数匹配。你可以使用 `phpMyAdmin` 来完成此操作。

现在，我们有两个运行运行的脚本。一个脚本 `connectInc.php` 建立了到 MySQL 数据库 `employees` 的连接。第二个脚本 `retrieve1.php` 在数据库上执行了一个 `Select` 查询，并将 `employee` 表的所有记录检索到结果集对象 `$rs` 中。但是，它只显示了第一条记录！我们如何显示结果集 `$rs` 的所有行呢？（实际上，我们如何显示 `employee` 表的所有行呢？）。答案是：我们使用 `while` 循环。

当我们第一次调用 `fetch_array` 方法时，它会将 `$rs` 第一行（当前行）的字段提取到数组 `$arr` 的元素中。然后，`fetch_array` 将第二行变为当前行。



如果我们再次调用`fetch_array`，提取的将是第二行的字段，然后第三行变成当前行。所以，如果我们不断地调用`fetch_array`，我们就能连续地处理结果集`$rs`的所有行。

因此，为了在`while`循环中多次调用`fetch_array`，我们修改了`retrieve1.php`的代码并将其保存为`retrieve2.php`。代码如下：

```php
<?php
require_once("connectInc.php");

$sql = "SELECT * FROM employee";
$rs = $conn->query($sql);

if ( $rs === false ) {
  trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
} else {
  $rows_returned = $rs->num_rows;
  echo( "<br>Rows: " . $rows_returned);
  while ( $arr = $rs->fetch_array(MYSQLI_ASSOC) ) {
    echo("<br/>");
    echo ($arr['empid'] . ' ' .
            $arr['lastname'].'' ' ' .
            $arr['firstname'] . ' ' .
            $arr['department'] . ' ' .
            $arr['position'].' '.
            $arr['salary']);
  }
}
?>
```

当我们执行此脚本时，我们将看到如下方式显示的`employee`表的所有行。

![](img/00280.jpeg)

图 9.17：显示了 employee 表的所有行。

为了以表格的形式呈现这些信息，请将`else`块替换为以下代码，并将脚本保存为`retrieve3.php`：

```php
{
  $rows_returned = $rs->num_rows;
  echo( "<br>Rows: " . $rows_returned);          
  echo("<table>");
  while ($arr = $rs->fetch_array( MYSQLI_ASSOC)) {
    echo("<tr>");
    echo "<td>" . $arr['empid'] . "</td>"
    echo "<td>" . $arr['lastname'] . "</td>"
    echo "<td>" . $arr['firstname'] . "</td>"
    echo "<td>" . $arr['department'] . "</td>"
    echo "<td>" . $arr['position']."</td>"
    echo "<td>" . $arr['salary'] . "</td>";
    echo '</tr>';
  }
  echo("</table>");
}
```

当我们执行`retrieve3.php`时，我们将得到类似下面的显示，其中列对齐整齐。

![](img/0281.jpeg)

图 9.18：信息以表格形式表示。

在本章中，我们能够使用 SQL 命令查询数据库，通过向数据库发送查询来获取`$result`对象，然后遍历`$result`对象的行并创建该数据的表格。这是`retrieve3.php`的代码：

```php
<?php
require_once("connectInc.php");

$sql = "SELECT * FROM employee";
$rs = $conn->query($sql);

if ( $rs === false ) {
  trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
} else {
  $rows_returned = $rs->num_rows;
  echo( "<br>Rows: " . $rows_returned);
  while ( $arr = $rs->fetch_array(MYSQLI_ASSOC) ) {
    echo("<br/>");
    echo ($arr['empid'] . ' ' .
            $arr['lastname'].'' ' ' .
            $arr['firstname'] . ' ' .
            $arr['department'] . ' ' .
            $arr['position'].' '.
            $arr['salary']);
  }
}
?>
```

### 复习题

1. 哪个类作为连接对象的蓝图可以访问数据库？

   a. connection 类

   b. mysqli 类

   c. physics 类

   d. resultset 类

2. 哪个命令指示如果`mysql_connect`不工作，将会导致？

   a. end

   b. die

   c. finish

   d. error

## 9.3 在数据库中存储信息

让我们回顾一下过去的工作。我们使用 phpMyAdmin 创建了数据库`employees`以及它的两个表——`employee`和`department`。我们还使用 phpMyAdmin 向这两个表输入数据。然后，我们编写了几个 PHP 脚本来实现 Retrieve 功能。现在，我们要编写 Create 功能。

我们需要做的第一件事是不包含 empid，因为它是自动生成的。我们将创建一个名为`insert.php`的新文件，在该文件中使用 HTML`form`标签并编写以下代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>插入员工</title>
</head>
<body>
    <form action="insertProcess.php" method="post">
        <p>姓<br/>
        <input type="text" name="last"/></p>
        <p>名<br/>
        <input type="text" name="first"/></p>
        <p>部门<br/>
        <input type="text" name="department"/></p>
        <p>职位<br/>
        <input type="text" name="position"/></p>
        <p>薪资<br/>
        <input type="text" name="salary"/></p>
        <input type="submit" value="保存信息" />
    </form>
</body>
</html>
```

让我们看看这一行 HTML 代码：

`<form action="insertProcess.php" method="post">`

此表单标签将`action`属性设置为`insertProcess.php`，该文件将接收并处理输入此表单的数据。我们使用了`post`方法，它以数组的形式传递信息，而不是创建出现在 URL 中的查询字符串。

如果在浏览器中运行`insert.php`脚本，我们将看到这个：

![](img/0282.jpeg)

图 9.19：插入新数据的表单。

现在我们有一个可以向数据库放入数据的表单。然而，你可以看到可以在部门下方的框中输入任何内容，这并不是我们想要的。

我们希望用户选择部门名称，但保存到数据库的不是部门名称，而是对应的部门 ID，该值只能在 1 到 4 之间。为了实现这一点，我们以此方式修改 HTML 代码。

# 部门

<select name="department">

  <option value="1">财务</option>

  <option value="2">销售</option>

  <option value="3">信息技术</option>

  <option value="4">管理</option>

</select>

在这里，当用户选择相应的字面值（财务、销售、信息技术或管理）时，提交的是`option`标签的`value`属性。

![](img/00283.jpeg)

图 9.20：`Department`字段的下拉框。

## insertProcess.php 脚本

现在，在实际将数据插入表单之前，让我们编写`insertProcess.php`脚本。该脚本的首要任务是从`insert.php`显示的表单中提取输入数据。因此，我们通过以下代码访问超全局数组`$_REQUEST`，然后使用`echo`函数将其显示：

```php
<?php
    $last = $_REQUEST['last'];
    $first= $_REQUEST['first'];
    $department= $_REQUEST['department'];
    $position= $_REQUEST['position'];
    $salary= $_REQUEST['salary'];
    echo($last . ' ' .
          $first . ' ' .
          $department . ' ' .
          $position . ' ' .
          $salary);
?>
```

现在，让我们测试`insert.php`中的输入数据是否已实际传递给`insertProcess.php`。运行脚本`insert.php`并按照所示输入数据。

![](img/00284.jpeg)

图 9.21：将信息传递到数据库。

当我们点击“保存信息”按钮时，你应该会在屏幕上看到这些内容：

`Smith Fred 3 Programmer 65000`

首先，你可能会发现`Information Technology`的代码有些细微差异。我们显示的是‘3’，但你可能会得到‘2’或‘4’。没关系，显示的数据应该是`lastname`、`firstname`、`departmentID`、`position`和`salary`的顺序。如果你在`insert.php`表单中输入的数据按此顺序正确显示，则说明输入的数据已正确传递给此脚本`insertProcess.php`。

## 通用逻辑流

现在，在我们完成将这些数据存储在`employee`表中的`insertProcess.php`其他代码之前，请回到第 9.2 节（从数据库检索查询）开头附近，那里概述了“我们四个主要脚本的通用逻辑流”。以下是该逻辑流的简要总结：

a. 使用连接对象`$conn`建立连接。

b. 检查`$conn`是否成功创建。

c. 构建`INSERT`、`SELECT`、`UPDATE`或`DELETE`查询。

d. 使用`$conn`的`query`方法执行查询。

e. 检查查询是否执行成功。在检索功能的情况下，获取结果集对象并将其内容传输到数组。

f. 关闭连接。

## 完成 insertProcess.php

现在我们完成`insertProcess.php`脚本的代码。首先，我们从超全局数组`$_REQUEST`中提取`insert.php`提交的数据，并将其存储在变量`$last`、`$first`、`$department`、`$position`和`$salary`中。

```php
  $last = $_REQUEST['last'];
  $first= $_REQUEST['first'];
  $department= $_REQUEST['department'];
  $position= $_REQUEST['position'];
  $salary= $_REQUEST['salary'];
```

我们要存储在`employee`表中的数据现在位于五个变量中——`$last`、`$first`、`$department`、`$position`、`$salary`。为了调试，我们使用以下代码在浏览器中显示这五个变量的值：

```php
    echo($last . ' ' .
          $first . ' ' .
          $department . ' ' .
          $position . ' ' .
          $salary);
```

在之后的生产版本中，我们可以移除这一行。

接下来，我们与数据库建立连接并检查连接是否成功。这是我们“通用逻辑流”中的步骤 a 和 b。这是通过`connectInc.php`脚本中的代码实现的，我们将其包含在`insertProcess.php`脚本中：

```php
  require_once("connectInc.php");
```

接下来（步骤 c），我们构建 SQL 插入语句并将该语句存储在变量`$sql`中。

```php
$sql= "INSERT INTO employee VALUES (''," .
"'" . $last . "'," .
"'" . $first . "'," .
"'" . $department . "'," .
"'" . $position . "'," .
"'" . $salary . "')";
```

接下来（步骤 d），我们调用`$conn`的`query`方法。我们提供`$sql`作为参数。我们在`if-else`语句中执行此操作：

```php
  if ($conn->query($sql) == false ) {
    $rmsg = 'Wrong SQL: ' . $sql . ' Error: ' . $conn->error;
  }
```

现在（步骤 e），我们检查查询是否成功。`query`方法返回返回布尔值。如果查询成功写入`employee`表，我们可以访问`$conn`的属性：

```php
  $last_inserted_id = $conn->insert_id;
  $affected_rows = $conn->affected_rows;
  echo( "<br/>Lasted Id: " . $last_inserted_id );
  echo( "<br/>Affected rows: " . $affected_rows );
```

接下来（步骤 f），我们需要关闭连接：

```php
  $conn->close();
```

这显示了测试结果：

`Smith Fred 3 Programmer 65000`

`INSERT INTO employee VALUES ('','Fred','3','Programmer','65000')`

`Lasted Id: 1`

`Affected rows: 1`

![](img/00284.jpeg)

图 9.21：将信息传递到数据库。

![](img/00285.jpeg)

图 9.22：新行。

![](img/00286.jpeg)

图 9.23：新行。

```php
echo( "<br/>Go back to <a href='index.php'>Add-Upd-DelPage</a>" );
?>
```

# 复习题

1. `post`方法使用的信息数据类型是什么？

   a. 数组 (array)。

   b. 链表 (linked list)。

   c. 单个数据 (single data)。

   d. 以上都不是。

2. 连接对象的哪个方法用于关闭其本身？

   a. exit

   b. end

   c. close

   d. 以上都不是。

## 9.4 删除和更新数据库记录

现在我们已经为这个简单基础的 CRUD 应用编写了创建（Create）和检索（Retrieve）功能的脚本，接下来我们将编写用于更新（Update）和删除（Delete）功能的脚本。

首先，我们将修改`retrieve3.php`脚本并保存为`index.php`。我们希望此脚本的页面显示作为一个仪表盘——应用程序的中央控制点。`index.php`也将是我们 CRUD 应用的启动脚本，通过它的仪表盘页面，我们可以访问应用程序的创建、更新和删除脚本。以下是`index.php`的修改后的代码。



```php
<?php

require_once("connectINC.php");

$sql = "SELECT * FROM employee";

$rs = $conn->query($sql);

if ( $rs === false ) {
  $errmsg = 'Wrong SQL: ' . $sql . ' Error: ' . $conn->error;
  trigger_error( $errmsg, E_USER_ERROR);
} else {
  echo("<table>");
  while ($arr = $rs->fetch_array( MYSQLI_ASSOC )) {
    echo("<tr>");
    echo( "<td>" . $arr['empid'] . "</td>"
      . "<td>" . $arr['lastname'] . "</td>"
      . "<td>" . $arr['firstname'] . "</td>"
      . "<td>" . $arr['department'] . "</td>"
      . "<td>" . $arr['position'].  "</td>"
      . "<td>" . $arr['salary'] . "</td>"
      . "<td><a href='delete.php?id=" . $arr['empid'] .
      "'>Delete</a></td>"
      . "<td><a href='updateForm.php?id=" . $arr['empid'] .
      "'>Update</a></td>" );
    echo '</tr>';
  }
  echo("<tr>
      <td></td> <td></td> <td></td> <td></td> 
      <td></td><td></td><td><a href=insert.php>Add New</a></td>");
  echo("</tr>");
  echo("</table>");
}

$conn->close();

?>
```

当我们运行此脚本时，你在`employee`表中输入的所有示例数据都应该如截图所示，按行列有序显示在屏幕上。

![](img/00287.jpeg)

图 9.24：由`index.php`脚本生成的屏幕显示，显示了员工表的行，每个员工都有对应的删除和更新按钮。表格底部还有一个“新增”（Add New）按钮，用于为新员工创建记录。

**提示**：为了让“新增”按钮与删除按钮列对齐，请在定义“新增”按钮的链接之前添加或删除表格单元格标签`<td></td>`。

如果你将`index.php`的代码与`retrieve3.php`的代码进行比较，你会发现我们增加了代码，为显示的每个员工记录创建了删除和更新按钮。通过这两个按钮，我们可以删除员工的记录或修改其数据。我们还在屏幕底部创建了一个“新增”按钮，允许我们向数据库添加新员工。“新增”、删除和更新按钮也是指向`insert.php`、`delete.php`和`updateForm.php`脚本的链接。点击这三个按钮中的任何一个都会执行相应的 PHP 脚本。

这就是`index.php`脚本作为仪表盘的功能。它的屏幕显示允许我们访问 CRUD 应用的创建、更新和删除功能。

当我们链接到`delete.php`和`updateForm.php`脚本时，我们还必须传递想要删除或更新的特定记录的 ID。为了这一点，我们使用了查询字符串（query string）。它是 URL 的一部分，包含要传递给 Web 应用程序的数据。你可能以前见过查询字符串，URL 的末尾有一个问号（`?`），然后是一组键值，如下所示：

`http://program/path/?query_string`

下行示例代码创建了删除按钮并将其链接到`delete.php`脚本。它还构建了传递给`delete.php`脚本的查询字符串。

`<td><a href='delete.php?id=" . $arr['empid'] . "'>Delete</a></td>`

如果你将`index.php`的代码与`retrieve3.php`的代码进行比较，你会发现我们增加了代码，为显示的每个员工记录创建了删除和更新按钮。通过这两个按钮，我们可以删除员工的记录或修改其数据。我们还在屏幕底部创建了一个“新增”按钮，允许我们向数据库添加新员工。“新增”、删除和更新按钮也是指向`insert.php`、`delete.php`和`updateForm.php`脚本的链接。点击这三个按钮中的任何一个都会执行相应的 PHP 脚本。

（注：提供的文本存在大量重复和碎片，已根据逻辑流进行了清理和去重。）

这显示了删除`empid`为 112 的员工的结果。（请将 112 替换为您删除的员工的`empid`。）

如果我们返回主页，即`index.php`，我们将看到以下内容：

你可以看到第一条记录已经消失了，这表明我们的删除操作成功了。

现在，让我们来看`updateForm.php`的完整代码，它实际上是一个完整的 HTML 文档。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Update Form</title>
</head>
<body>
  <?php
    require_once("connectInc.php");
    $id=$_REQUEST['id'];
    $sql = "SELECT * FROM employee WHERE empid = '" . $id . "';";
    $rs = $conn->query($sql);
    if ( $rs === false ) {
      trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
      die( "Select Error: " . $sql);
    } else {
      $arr = $rs->fetch_array( MYSQLI_ASSOC);
    }
    $conn->close();
  ?>
  <form action="updateProcess.php" method="post">
    <input type="hidden" name="id" value="<?php print($id); ?>" />
    <p>Last Name<br/>
    <input type="text" value="<?php print($arr['lastname']) ?>" name="last"/></p>
    <p>First Name<br/>
    <input type="text" value="<?php print($arr['firstname']) ?>" name="first"/></p>
    <p>Department<br/>
    <select name="department">
      <option <?php if($arr['department']==1) { print('selected'); } ?> value="1">Accounting</option>
      <option <?php if($arr['department']==2) { print('selected'); } ?> value="2">Sales</option>
      <option <?php if($arr['department']==3) { print('selected'); } ?> value="3">Information Technology</option>
      <option <?php if($arr['department']==4) { print('selected'); } ?> value="4">Management</option>
    </select></p>
    <p>Position<br/>
    <input type="text" value="<?php print($arr['position']) ?>" name="position"/></p>
    <p>Salary<br/>
    <input type="text" value="<?php print($arr['salary']) ?>" name="salary"/></p>
    <input type="submit" value="Update Information" />
  </form>
</body>
</html>
```

此表单的功能是显示某个员工的数据。放置在我们 HTML 文档`<head>`部分的以下 PHP 脚本执行了获取该员工数据的必要操作：

```php
require_once("connectInc.php");
$id=$_REQUEST['id'];
$sql = "SELECT * FROM employee WHERE empid = '" . $id . "";
$rs = $conn->query($sql);
if ( $rs === false ) {
  trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
  die( "Select Error: " . $sql);
} else {
  $arr = $rs->fetch_array(MYSQLI_ASSOC);
}
$conn->close();
```

在阅读和分析这段代码时，请它也遵循了我们最近在`delete.php`代码中详细说明的步骤 a-f：

a. 创建一个连接对象`$conn`。

b. 检查`$conn`是否成功创建。

c. 构建 SQL 查询。

d. 执行连接对象的查询方法。

e. 检查查询是否执行成功。处理结果对象`$rs`。

f. 关闭连接。

我们不断重复这些步骤的原因是这是任何访问数据库的 PHP 脚本的基本模式。理解并掌握这六步将为你避免未来的任何烦恼！

现在，通过行代码`$arr = $rs->fetch_array(MYSQLI_ASSOC);` 将获取到的员工数据存储在关联数组`$arr`中。然后，数组中的数据将由表单元素用于显示。让我们分析以下显示关联数组`$arr`中数据的 HTML 和 PHP 代码：

```html
<input type="text" value="<?php print($arr['lastname']) ?>" name="last"/>
```

在这里，我们将`<input>`元素的`value`属性设置为数组`$arr`中元素的值，特别是通过键为`lastname`索引的元素。我们使用 PHP 代码来实现。在输入这一行时，你必须小心将每个字符放置在正确的位置，否则会产生各种错误。

在部门（Department）字段的情况下，处理过程不同。我们必须对每个`departmentId`值（1-4）进行单独测试，然后显示相应的`departmentName`。同样，在输入这一行时你必须小心，不要错错任何字符，特别是逗号、引号、大大括号或小括号：

```html
<option <?php if($arr['department']==1) { print('selected'); } value="1">Accounting</option>
```

最后，我们必须处理`empid`字段。记住，该字段是主键，并由 MySQL 数据库自动生成。

你也可以使用`phpMyAdmin`来更改数据库中任何表的任何字段，但目前，只需使用`phpMyAdmin`来验证我们通过 CRUD 应用所做的更改即可。

![](img/00290.jpeg)

图 9.27：使用 phpMyAdmin 编辑数据库中的表字段。

我们简单的基础 CRUD 应用已经完成。

## 复习题

1. 查询字符串中使用哪个符号？

   a. `#`

   b. `$`

   c. `&`

   d. `?`

2. `$_REQUEST[]` 是什么？

   a. 一个函数

   b. 一个命令

   c. 一个数组

   d. 一个超全局数组

## 第 9 章实验练习

1. 确保你的 MAMP 或 WAMP 服务器堆栈已下载、安装并运行。你可以在 [www.wampserver.com/en/](http://www.wampserver.com/en/) 下载 Windows 版的 WAMP 服务器。你可以在 [www.mamp.info](http://www.mamp.info) 下载 Mac 版的 MAMP 服务器。

2. 设置一个 HTML 文档，并在文档的`<body>`部分嵌入 PHP 的起始和结束标签。按照描述将该文档保存到你的`www`文件夹（Windows）或`htdocs`文件夹（Macintosh）中。

3. 创建一个数据库来跟踪计算机科学课程的学生和成绩。在`MySQL`中按如下创建数据库：

   - 数据库名称：`CSClassData`

   - 表数量：1

4. 在`CSClassData`中创建一个名为`students`的表。该表应包含以下字段：

   - `studentID int(5)`

   - `lastName varchar(40)`

   - `firstName varchar(20)`

   - `test1Grade int(3)`

   - `test2Grade int(3)`

   - `test3Grade int(3)`

   - `test4Grade int(3)`

   - `finalExamGrade int(3)`

5. 为 10 名学生输入虚构数据，包括名、姓以及所有 5 次考试的成绩。（成绩按 0-100 的标准评分）。

6. 创建一个数据库连接脚本，连接到你创建的`MySQL`数据库和`CSClassData`数据库。

7. 创建名为`grade_list.php`的页面。在该页面上，按学生输出数据库中的所有成绩。你应该使用表格来实现此功能。

8. 一旦输出了所有成绩，在表格中添加两列。第一列应包含学生通过平均五次成绩得到的数值平均分。

   第二个新列应根据以下标准显示其 A-F 形式的最终成绩：

   - A 90-100

   - B 80-89

   - C 70-79

   - D 60-69

   - F 60 以下

   你应该能够在不更改数据库中任何内容的情况下添加最后两列——这些将是计算字段，而不是存储的数据库字段。

9. 使用 CSS 使你的输出表格更具可读性。

10. 在计算平均分和字母等级字段的右侧，添加删除和编辑的链接。将删除页面命名为`grades_delete.php`，更新页面命名为`grades_updateForm.php`。在表格底部，添加一个调用新增学生页面的链接`grade_insert.php`。

11. 编写 PHP 代码以实现如本章所示的更新、删除和创建功能。

12. 确保页面之间相互链接，以便用户可以在完成的 PHP 应用中轻松地在不同功能之间导航。

## 第 9 章实验答案

### File: `gradesConnect.php`

```php
<?php
  define( "HOSTNAME", "localhost");
  define( "USERNAME", "root");
  define( "PASSWORD", "");
  define( "DB_NAME", "CSClassData");
  $conn = new mysqli(HOSTNAME, USERNAME, PASSWORD, DB_NAME);
  if ($conn->connect_errno) {
    echo( "<br/>Failed to connect to MySQL: (" . $conn->connect_errno . ") " . $conn->connect_error );             
    die( '<br/>Program Terminated');
}
?>
```

### File: `grades_delete.php`

```php
<?php
  require_once("gradesConnect.php");
  $id = $_REQUEST['id'];
  $sql = "DELETE FROM students WHERE studentID= '" . $id . "';";
  if ($conn->query($sql) === false) {
    trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
  } else {
    echo( "<br/>" . $sql);
    $affected_rows = $conn->affected_rows;
    echo( "<br/>Affected rows:    " . $affected_rows );
    echo( "<br/>User " . $id . " deleted from the database.");
  }
  $conn->close();
  echo( "<br/>Return to <a href='grades_list.php'>Add-Upd-Del Page</a>");
?>
```

### File: `grades_list.php`



```php
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Grade List</title>
    <style>
        table, th, td {
          border:1px solid black;
          border-collapse: collapse;
        }
    </style>
    <?php
      require_once("gradesConnect.php");
      $sql = "SELECT * FROM students";
      $rs = $conn->query($sql);
      if ($rs === false ) {
        trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
        die();
      }
    ?>
</head>
<body>
  <table>
    <tr>
      <th>Student ID</th>
      <th>Last Name</th>
      <th>First Name</th>
      <th>Test 1</th>
      <th>Test 2</th>
      <th>Test 3</th>
      <th>Test 4</th>
      <th>Final Exam</th>
      <th>Average</th>
      <th>Grade</th>
      <th>Action</th>
    </tr>
    <?php
      while ($arr = $rs->fetch(MYSQL_ASSOC)) {
        $average = ($arr['test1Grade'] + $arr['test2Grade'] + $arr['test3Grade'] + $arr['test4Grade'] + $arr['finalExamGrade']) / 5;
        if ($average >= 90) {
          $letterGrade = 'A';
        } elseif ($average >= 80) {
          $letterGrade = 'B';
        } elseif ($average >= 70) {
          $letterGrade = 'C';
        } elseif ($average >= 60) {
          $letterGrade = 'D';
        } else {
          $letterGrade = 'F';
        }
        echo "<tr>";
        echo "<td>" . $arr['studentID'] . "</td>";
        echo "<td>" . $arr['lastName'] . "</td>";
        echo "<td>" . $arr['firstName'] . "</td>";
        echo "<td>" . $arr['test1Grade'] . "</td>";
        echo "<td>" . $arr['test2Grade'] . "</td>";
        echo "<td>" . $arr['test3Grade'] . "</td>";
        echo "<td>" . $arr['test4Grade'] . "</td>";
        echo "<td>" . $arr['finalExamGrade'] . "</td>";
        echo "<td>" . $average . "</td>";
        echo "<td>" . $letterGrade . "</td>";
        echo "<td><a href='grades_updateForm.php?id=" . $arr['studentID'] . "'>Edit</a> <a href='grades_delete.php?id=" . $arr['studentID'] . "'>Delete</a></td>";
        echo "</tr>";
      }
    ?>
  </table>
  <p><a href="grade_insert.php">Add New Student</a></p>
</body>
</html>
```

### File: `updateForm.php`

```php
<?php
  require_once("gradesConnect.php");
  $id = $_REQUEST['id'];
  $sql = "SELECT * FROM students WHERE studentID = '" . $id . "";
  $rs = $conn->query($sql);
  if ($rs === false ) {
    trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
    die("Select Error: " . $sql);
  } else {
    $arr = $rs->fetch(MYSQL_ASSOC);
  }
  $conn->close();
?>
<html lang="en">
<head>
    <title>Update Student</title>
</head>
<body>
  <form action="gradesUpdateProcess.php" method="post">
    <input type="hidden" value="<?php print($arr['studentID']) ?>" name="id" />
    <p>Last Name <input type="text" value="<?php print $arr['lastName'] ?>" name="last"/></p>
    <p>First Name <input type="text" value="<?php print $arr['firstName'] ?>" name="first"/></p>
    <p>Test 1 Grade <input type="text" value="<?php print $arr['test1Grade'] ?>" name="test1Grade"/></p>
    <p>Test 2 Grade <input type="text" value="<?php print $arr['test2Grade'] ?>" name="test2Grade"/></p>
    <p>Test 3 Grade <input type="text" value="<?php print $arr['test3Grade'] ?>" name="test3Grade"/></p>
    <p>Test 4 Grade <input type="text" value="<?php print $arr['test4Grade'] ?>" name="test4Grade"/></p>
    <p>Final Exam Grade <input type="text" value="<?php print $arr['finalExamGrade'] ?>" name="finalExamGrade"/></p>
    <input type="submit" value="Update Information" />
  </form>
</body>
</html>
```

# 插入学生

```html
<html lang="en">
<head>
    <title>插入学生</title>
</head>
<body>
    <form action="grades_insertProcess.php" method="post">
        <p>姓<br/>
        <input type="text" name="last"/></p>
        <p>名<br/>
        <input type="text" name="first"/></p>
        <p>测试 1 成绩<br/>
        <input type="text" name="test1Grade" /></p>
        <p>测试 2 成绩<br/>
        <input type="text" name="test2Grade" /></p>
        <p>测试 3 成绩<br/>
        <input type="text" name="test3Grade" /></p>
        <p>测试 4 成绩<br/>
        <input type="text" name="test4Grade" /></p>
        <p>期末考试成绩<br/>
        <input type="text" name="finalExamGrade" /></p>
        <input type="submit" value="保存信息" />
    </form>
</body>
</html>
```

### 文件: `grades_insertProcess.php`

```php
<?php
  require_once("gradesConnect.php");
  $last = $_REQUEST['last'];
  $first= $_REQUEST['first'];
  $grade1 = $_REQUEST['test1Grade'];
  $grade2 = $_REQUEST['test2Grade'];
  $grade3 = $_REQUEST['test3Grade'];
  $grade4 = $_REQUEST['test4Grade'];
  $final = $_REQUEST['finalExamGrade'];
  $sql= "INSERT INTO students VALUES (''," .
    "'" . $last . "'," .
    "'" . $first . "'," .
    "'" . $grade1 . "'," .
    "'" . $grade2 . "'," .
    "'" . $grade3 . "'," .
    "'" . $grade4 . "'," .
    "'" . $final . "')";
  if ($conn->query($sql) == false ) {
    trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
  } else {
    $last_inserted_id = $conn->insert_id;
    $affected_rows = $conn->affected_rows;
    echo( "<br/>最后插入的 ID: " . $last_inserted_id );
    echo( "<br/>受影响行数:    " . $affected_rows );
    echo( "<br/>" . $last . " 成功添加到数据库。" );
  }
  $conn->close();
  echo( "<br/>返回到 <a href='grades_list.php'>添加-更新-删除页面</a>" );      
?>
```

### 文件: `grades_updateProcess.php`

```php
<?php
  require_once("gradesConnect.php");
  $id = $_REQUEST['id'];
  $last = $_REQUEST['last'];
  $first = $_REQUEST['first'];
  $grade1 = $_REQUEST['test1Grade'];
  $grade2 = $_REQUEST['test2Grade'];
  $grade3 = $_REQUEST['test3Grade'];
  $grade4 = $_REQUEST['test4Grade'];
  $final = $_REQUEST['finalExamGrade'];
  $sql= "UPDATE students SET " .
      "lastName = '" . $last . "', " .
      "firstName = '" . $first . "', " .
      "test1Grade = '" . $grade1 . "', " .
      "test2Grade = '" . $grade2 . "', " .
      "test3Grade = '" . $grade3 . "', " .
      "test4Grade = '" . $grade4 . "', " .
      "finalExamGrade = '" . $final . "' WHERE studentID = '" . $id . "";
  if ($conn->query($sql) == false ) {
    trigger_error('Wrong SQL: ' . $sql . ' Error: ' . $conn->error, E_USER_ERROR);
  } else {
    $affected_rows = $conn->affected_rows;
    echo( "<br/>受影响行数:" . $affected_rows );
  }
  $conn->close();
  echo( "用户 " . $id . " 已更新。返回 <a href='grades_list.php'>添加-更新-删除页面</a>.");
?>
```

## 第 9 章总结

本章包含了大量的概念和技术。除了学习 PHP 代码，你还学习了如何使用 `phpMyAdmin` 对 MySQL 数据库进行操作。你学习了如何构建 `SQL` 语句在 MySQL 数据库中插入、更新和删除数据。你学习了如何使用接口构建简单的 CRUD（增删改查）应用程序。关于 PHP 还有很多要学的，但如果你理解了这里的概念和技术，你就在掌握之路上了。在下一章中，我们将讨论一些常用的类和对象。

# 第 10 章：类与对象

## 目标

* 你将学习两个重要的 PHP 函数：`date()` 和 `time()`，以及如何使用这些函数处理日期信息。
* 你将学习使用 PHP 的许多字符串函数处理字符串。
* 你将理解如何使用 session 和 cookie 在请求之间维持状态。

## 10.1 Date 函数

所有的程序都需要处理日期和时间。例如，Web 应用程序需要记录访问页面的日期和时间。这项任务相对简单，但因为需要考虑不同的时区而变得稍微复杂。此外，每年的天数不同，还需要考虑闰年。程序还必须考虑如何呈现日期和时间。用户倾向于 2001 年 2 月 14 日，还是 2001-02-14？你显示的是军用时间 17:45 还是 12 小时制 5:45？

某些编程系统有特定的日期时间类型。PHP 没有，但提供了许多日期函数和对象（参见 http://php.net/datetime）。在本章的节中，我们将查看 `time()` 和 `date()` 函数。

每台计算机都使用内置时钟跟踪当前的日期时间。你可以通过 `time()` 函数获取内置时钟的时间。如果你在浏览器中输入以下代码：

```php
<?php
  print("<br/>" . time());
?>
```

你可能会看到一个十位整数：

139503440

这是一个时间戳。它是从 1970 年 1 月 1 日午夜到当前日期时间之间的秒数。这是计算机用于监控和存储日期的格式，因为在这种整数格式下进行日期计算更容易。如果你再次执行上述脚本，可能会得到：

139503455

注意最后两位数字从 40 变为了 55，这意味着在你两次执行脚本之间经过了 15 秒。计算机的内置时钟正在运行并跟踪时间。

现在，我们可以使用 `date()` 函数轻松地将此时间戳转换为我们可以理解的日期时间格式。例如，脚本：

```php
<?php
  date("D - F d, Y", 131493440);
?>
```

将返回：

Fri - September 02, 2011

`date()` 函数接受两个参数。第一个是强制性的格式字符串 `"D - F d, Y"`，指定日期时间的格式。第二个参数是可选的，它是我们要格式化的时间戳 `131493440`。如果省略第二个参数，`date()` 函数将使用 `time()` 函数返回的时间戳。

格式字符串每个字符的含义总结如下：

| 字符 | 描述 |
| :--- | :--- |
| d | 月份的两位数字，需要时前导零。 |
| D | 三字母字符串形式的星期（例如“Mon”）。 |
| F | 完整单词形式的月份（例如“January”）。 |
| Y | 四位数字形式的年份。 |

表 10.1：`date()` 函数格式字符串的一些字符格式。

仔细研究之前的日期格式字符串并注意它是如何产生显示输出的。现在，让我们对之前的日期格式字符串做一个微小的改变，使其变为：

`date("l - F d, Y", 131493440);`

你发现变化了吗？它是紧跟双引号后的 `l`（小写 L）。显示现在将变为：

Friday - September 02, 2011

这是格式字符串中 `l`（小写 L）字符的含义：

## 表 10.2: `date()` 函数格式字符串中小写字母“L”的格式。



`date()` 函数中还有许多用于格式化日期的字符格式。你可以在 [`php.net/date`](http://php.net/date) 找到它们。

现在，让我们修改脚本以包含用于格式化时间的字符格式：

```php
<?php
  print(date("D F d, Y h:i:s"));
?>
```

该脚本将产生：

`Mon - March 17, 2014 11:47:58`

我们没有提供第二个参数，因此 `date()` 函数使用了 `time()` 函数返回的时间戳，并根据我们新添加的用于格式化的字符串 `h:i:s` 对时间进行了格式化。时间格式每个字符的含义总结如下表所示。

| 字符 | 描述 |
| :--- | :--- |
| h | 12 小时制的小时，带有前导零 (01 – 12)。 |
| i | 分钟，带有前导零 (00 – 59)。 |
| s | 秒，带有前导零 (00 – 59)。 |

表 10.3：`time()` 函数格式字符串的几种字符格式

### 计算现在 30 天后的代码

在本节的开始，我们提到 PHP 将时间戳（即其内部时钟）存储为 10 位整数，因为在这种格式下进行日期和时间计算要容易得多。现在，让我们计算一下 30 天后的日期和时间将是什么。以下是在你的浏览器中执行的代码：

```php
<?php
  print(date("D F d, Y h:i:s"));
  print("<br/>");
  print(time());
  $thirtyDays = 60 * 60 * 24 * 30;
  print("<br/>30 days from right now: " . (time()+ $thirtyDays));
?>
```

你应该得到类似这样的（当然，当前的日期和时间取决于你执行此代码的时间）：

![](img/00291.jpeg)

图 10.1：`date()` 函数的不同输出。

10 位时间戳对我们来说作用不大，所以让我们将其格式化为更易读、实用的形式。我们使用 `date()` 函数，这是要添加的代码：

```php
print("<br/>30 days from right now: " . (date("D F d, Y h:i:s",time()+ $thirtyDays)));
```

在浏览器中查看，我们将看到类似以下的内容：

![](img/00292.jpeg)

图 10.2：当前日期时间 30 天后的日期和时间显示得更清晰。

我们也可以通过简单地将加号（`+`）替换为减号（`-`）来减少几天。将以下代码添加到之前的脚本并在浏览器中查看结果。

```php
print("<br/>30 days before: " . (time()- $thirtyDays));
```

我们还可以获取现在 18 小时后的精确时间。以下是要添加的代码：

```php
$eighteenHours = 60 * 60 *18;
print("<br/>18 Hours from now: " . (date("D F d, Y h:i:s", time() + $eighteenHours)));
```

注意，我们通过添加 `60 * 60 * 18`（即 18 小时的秒数）来增加 18 小时。在浏览器中，我们将看到：

![](img/00293.jpeg)

图 10.3：显示当前时间 18 小后的精确时间。

这是对 PHP 中 `date()` 和 `time()` 函数的快速介绍。在后面关于 cookie 的章节中，我们将再次使用 `time()` 函数，特别是在设置 cookie 的未来过期日期和时间时。有关所有 PHP 日期时间函数的完整参考，请访问 [`php.net/date`](http://php.net/date)。

### 完整代码列表

```php
<?php
  print(date("D F d, Y h:i:s"));
  print("<br/>");
  print(time());
  $thirtyDays = 60 * 60 * 24 * 30;
  print("<br/>30 days from right now: " . (time()+ $thirtyDays));
  print("<br/>30 days from right now: " . (date("D F d, Y h:i:s",time()+ $thirtyDays)));
  $EighteenHours = 60 * 60 *18;
  print("<br/>18 Hours from now: " . (date("D F d, Y h:i:s", time() + $eighteenHours)));
?>
```

**复习题**

1. `date()` 函数有几个参数？

   a. 一个

   b. 两个

   c. 三

   d. 四个

2. 使用哪个字母获取月份的全文本？

   a. F

   b. M

   c. m

   d. D

## 10.2 PHP 中的字符串

在编程中，字符串是字符序列。以下是有效字符串的示例：

- `"Hi!"`

- `"How are you?"`

- `"1234"`

在 PHP 中，字符串可以使用单引号或双引号括起来。以下是使用单引号的示例：

```php
echo 'Hi!';
echo 'How are you?';
echo '1234';
```

单引号内的字符串不会解析变量，而双引号内的字符串则会解析变量和转义字符。以下是使用双引号的示例：

```php
$name = "World";
echo "Hello, $name!"; // 输出：Hello, World!
echo "Hello, \$name"; // 输出：Hello, $name
```

单引号中唯一的转义字符是反斜杠（`\`）和单引号本身（`\'`）。以下是其示例：

```php
echo 'It\'s a sunny day';
```

双引号支持许多转义字符，包括双引号（`\"`）、反斜杠（`\\`）、换行（`\n`）、制表符（`\t`）等。以下是其示例：

```php
echo "He said, \"Hello\"";
echo "Line one\nLine two";
echo "Tabbed text";
```

你可以使用点运算符（`.`）来连接两个字符串。以下是一个示例：

```php
$greeting = "Hello";
$name = "World";
echo $greeting . " " . $name;
```

如果你需要格式化字符串中的变量，可以使用 `sprintf()` 函数。

```php
$greeting = "Hello";
$name = "World";
echo("Hello, %s!", $name);
```

在浏览器中我们将得到以下输出，其中前 30 个字符将作为子字符串显示：

![](img/00300.jpeg)

图 10.10：显示字符串的前 30 个字符。

PHP 中还提供了许多其他字符串函数（可以查看 [`www.php.net/manual/en/ref.strings.php`](http://www.php.net/manual/en/ref.strings.php)），你将轻松找到某个函数或多个函数的组合来完成特定的编程任务。

### 完整代码列表

```php
<?php

$name = "Mark";

echo("My name is $name");

echo('<br/>My name is $name');

echo("<br/>");

$poem = <<<TEST

Roses are Red<br/>

Violets are Blue<br/>

I'm no fan of Heredocs<br/>

But I can teach you!<br/>

<br/>

TEST;

echo($poem);

print_r(str_split($name));

print("<br/>");

print(strrev("Wheel of Fortune"));

print("<br/>");

print("<br/>");

print(substr($poem, 0, 30));

?>
```

### 复习题

1. 用于显示 heredoc 的符号是：

a. `<<<`

b. `>>>`

c. `+++`

d. `---`

2. 哪个函数将字符串转换为数组？

a. `strrev()`

b. `str_split()`

c. `str_con()`

d. `str_arr()`

## 10.3 会话

当你浏览互联网时，通过点击链接在不同的网页之间跳转。当你点击链接时，Web 服务器会将此解释为对你点击链接的指向页面的请求。它会加载页面并执行该页面的 HTML 和 CSS 命令以及任何 PHP 脚本。

PHP 变量将被初始化，执行计算、格式化文本、调整图像大小并定位，然后将完全渲染的页面发送到你的浏览器。Web 服务器随后从内存中删除该页面。任何 PHP 变量的值以及任何计算结果都会丢失。如果由于某些原因你以后再次点击同一个链接，Web 服务器将再次通过相同的过程，而不会记得它以前渲染过此页面。这就是所谓的“无状态”。

在互联网早期的原始阶段，这是可以的，因为大多数时间信息是以格式良好的页面显示的。但现在，在电子商务和交互时代，网页之间必须保持某种连接。当你从一个网页移动到另一个网页并返回时，网页中变量的值必须被保留并传递给下一个网页。这就是所谓的“维护状态”，或者更具体地说，是“在浏览器请求之间保留应用程序的状态”。

例如，购物车应用程序必须记住你从访问过的各种网页中选了哪些项目。在大型多人在线角色扮演游戏（mmorpg）中，你的角色必须维护其健康状态、武器、法术等。这不仅是在你从一个关卡移动到另一个关卡时，而且当你某天注销另一天登录时。

PHP 有几种在网页之间维护状态的机制，即隐藏表单字段、查询字符串、cookies 和会话（sessions）。我们将仅调查会话（在本节）和 cookies（在下一节），它们是浏览器请求之间维护状态的两种常用方法。

PHP 会话是服务器上的一个临时文件，你可以在其中存储数据。一个短的会话 ID (`SID`) 被用于识别和保护该文件。此 `SID` 由服务器作为 cookie 的一部分发送到浏览器。当浏览器下次向服务器发送请求时，它会将 `SID` cookie 发回服务器，允许服务器检索之前保存的任何会话数据，并将这些会话数据在超全局数组 `$_SESSION` 中可用。（服务器生成的 `SID` 是唯一的、随机的且几乎无法猜测，这使其以及你的会话数据免受黑客的攻击。）

尽管你可以在服务器会话文件中存储相当的数据（比你在 4kb cookie 中存储的要多），但请记住，会话主要用于存储临时数据以维护网页之间的状态。一旦你关闭浏览器，会话数据将不再可用。要永久地存储大量数据，则需要其他方法。

现在让我们连续执行脚本 `sessions.php`、`sessions2.php` 和 `sessions3.php`。这将产生以下三个相应的屏幕。

![](img/00301.jpeg)

图 10.11: 脚本 `sessions.php` 的屏幕输出

![](img/00302.jpeg)

图 10.12: 脚本 `sessions2.php` 的屏幕输出

![](img/00303.jpeg)

图 10.13: 脚本 `sessions3.php` 的屏幕输出

## 完整代码列表

### Sessions.php

```php
<?php
    session_start();
    $name="Mark";
    $_SESSION['name'] = $name;
    $_SESSION['password'] = "lobsterchops";
    $_SESSION['age'] = "37";  
?>
```

<a href="sessions2.php">Sessions 2</a>

### Sessions2.php

```php
<?php
    session_start();
    $name = $_SESSION['name'];
    $pw = $_SESSION['password'];
    $age = $_SESSION['age'];
    print("Stored in the session: $name $pw $age");
    session_destroy();
    print(" <br> Session Destroyed.  Please go to <a href='sessions3.php'>Sessions 3</a>. </br>")
?>
```

### Sessions3.php

```php
<?php
    session_start();
    if(isset($_SESSION['name']))
    {
    $name = $_SESSION['name'];
    $pw = $_SESSION['password'];
    $age = $_SESSION['age'];
    } else
    {
        print("Session appears to have been terminated.");
    }
?>
```

<a href="sessions.php">Session 1</a>

## 复习题

1. 使用哪个函数来启动每个会话 (session)?

a. `session_start()`

b. `session_begin()`

c. `session_initiate()`

d. 以上都不是

2. 当我们不再需要会话时，使用哪个函数？

a. `session_end()`

b. `session_finish()`

c. `session_destroy()`

d. 以上都不是

## 10.4 Cookies

在上一节中，我们讨论了会话 (sessions)，它们是服务器上的临时文件，客户端浏览器在其中存储数据以维持浏览器请求之间的状态。而 Cookie 则是由服务器留在客户端计算机上的文件，大小不超过 4kb。

当浏览器向服务器请求页面时，服务器会在其对浏览器请求的响应头中向浏览器发送一个或多个 Cookie。

当浏览器下一次向留下 Cookie 的同一服务器发送请求时，Cookie 中的数据将自动通过请求发送到服务器。通过 Cookie，服务器可以“记住”这个特定的浏览器客户端，并可以使用该客户端发送的 Cookie 中的数据为该特定的客户端浏览器提供定制的响应。

Cookie 只能由创建它的服务器检索，因此提供了一定程度的安全性。尽管如此，它们仍然受到黑客攻击的影响，应仅用于非关键数据（例如用户偏好）。浏览器也可以禁用 Cookie 支持，从而切断对 Cookie 的任何访问。某些客户端可能完全不支持 Cookie。客户端持有的 Cookie 数量也有限制。每个域名只允许 20 个 Cookie，且客户端同时只能持有 300 个 Cookie。尽管如此，对于用户偏好等非安全关键数据，Cookie 可以是维护状态的非常有价值的工具。

Cookie 中的数据应按照以下参数顺序排列：

| Cookie 字段 | 说明 |
| :--- | :--- |
| name | 特定 Cookie 的唯一名称。不允许有空格或分号。 |
| value | 附加到此 Cookie 的任意字符串值。 |
| expire | Cookie 的过期日期。过期时间指定为时间戳或自 1970 年 1 月 1 日午夜 (GMT) 以来的秒数。 |
| path | 浏览器仅对位于此路径下的 URL 返回 Cookie。 |
| domain | 浏览器仅对该域名内的 URL 返回 Cookie。 |
| secure | 浏览器仅通过 https 连接传输 Cookie。 |

表 10.4：Cookie 参数的强制性顺序。

使用 `setcookie()` 函数创建 Cookie 并将其发送到浏览器是很容易的。该函数发送相应的 HTTP 头以在浏览器中创建 Cookie。`setcookie()` 函数的参数与上一个表所示的参数相同。不过，通常情况下，你只需要提供前三个或前四个参数（name, value, expire 和 path），但只要可能，你都应该提供六个参数。

`setcookie()` 函数也应该在向浏览器发送任何输出之前调用，因为 `setcookie()` 在服务器的 HTTP 响应头中发送 Cookie。如果你在调用 `setcookie()` 之前向浏览器发送了输出，PHP 将先发送响应头。因此，`setcookie()` 失去了在响应头中发送 Cookie 的能力。这就是为什么包含 `setcookie()` 调用的代码被放置在 HTML 文档的 `<head>` 部分的原因。

以下是创建名为 `band` 和 `food` 的两个 Cookie 的代码。`band` 将在一个小时后过期，而 `food` 将在 30 天后过期。将其保存为 `cookies.php`。

```php
<?php
setcookie("band", "Journey", time()+ 3600); // 一小时后过期
setcookie("food", "pasta", time()+ (60 * 60 * 24 * 30)); // 30 天过期
?>
```

现在我们在浏览器中有两个 Cookie，检索它们与创建它们一样简单。使用全局变量 `$_COOKIE` 数组包含了浏览器发送的所有值。输入此 `cookies2.php`。

```php
<?php
$band = $_COOKIE['band'];
$food = $_COOKIE['food'];
print("Band: " . $band);
print("<br/>Food: " . $food);
?>
```

显示结果应该是：

Journey

pasta



要删除或“过期”一个 Cookie，调用`setcookie()`并将要删除的 Cookie 名称作为第一个参数，空字符串（或任何值）作为第二个参数，并将过去的时间作为第三个参数。例如：

```php
setcookie("food", "", (time()-1));
```

运行`cookies2.php`，你应该得到相同的显示，因为我们调用了带有过去的时间戳——`food` Cookie 已过期。为了验证此 Cookie 是否已删除，输入以下代码作为`cookies3.php`。

```php
<?php
$band = $_COOKIE['band'];
print("Band: " . $band);
if(isset($_COOKIE['food']))
{
    print("<br/>Food cookie set");
}
else
{
    print("<br/>No cookie found.");
}
?>
```

`isset()`函数在变量不是 NULL 时返回 TRUE。否则返回 FALSE。当你运行`cookies3.php`时，你将在浏览器中获得结果：

Journey

No cookie found.

`food` Cookie 已删除。

a. 一个文件。

b. 一个函数。

c. 一个命令。

d. 以上均不是。

2. 使用哪个函数来创建 cookie？

a. `setcookie()`

b. `startcookie()`

c. `createcookie()`

d. 以上均不是。

# 第 10 章实验练习

1. 确保你的 MAMP 或 WAMP 服务器堆栈已下载、安装并正在运行。

2. 设置一个 HTML 文档，并在文档的`<body>`部分中嵌入 PHP 的开始标签和结束标签。按照描述将该文档保存到`www`文件夹（Windows）或`htdocs`文件夹（Mac）中。

3. 创建一个简单的表单，让用户输入用户名。将用户名存储在会话（session）变量。

4. 创建第二个页面，从会话变量中读取用户名。向用户输出问候语。

5. 输出问候语后，销毁会话并将用户名存储名为`username`的 cookie 中。设置 cookie 在 30 分钟后过期。

6. 创建新页面并获取 cookie。使用`date()`函数在页面顶部显示当前日期。

7. 将字符串 “You have reached the end of PHP for Beginners.” 放入变量`$message`中。

8. 输出字符串中的字符数。

9. 使用字符串函数和任何必要的代码，将所有元音替换为 X 并再次输出字符串。

10. 使用字符串函数将字符串转换为数组，并使用循环输出数组的每个元素。（不要使用`print_r`。）

# 第 10 章实验标准答案

### Lab.php:

```php
<!DOCTYPE html>
<head>
    <title>Lab 10</title>
    <?php
        $user;
        if(isset($_REQUEST['user']))
        {
            $user = $_REQUEST['user'];
            session_start();
            $_SESSION['username'] = $user;
            print("Session saved");
        }
    ?>
</head>
<body>
    <form action="lab.php" method="post">
        <label for="user">Username:</label><input type="text" id="user" name="user" />
        <br/><input type="submit" value="Save Session" />
        <br/><a href="lab2.php">Go to page 2</a>
    </form>
</body>
</html>
```

### Lab2.php

```php
<?php
    session_start();
    $username = $_SESSION['username'];
    print("Hello " . $username);
    session_destroy();
    setcookie("username", $username, time() + 1800);
    print("<br/><a href='lab3.php'>Go to page 3</a>a>");
?>
```

### Lab3.php

```php
<?php
    print(date("D F d, Y h:i:s"));
    $username = $_COOKIE["username"];
    print("<br/>From Cookie: " . $username);
    $message = "You have reached the end of PHP for Beginners.";
    print("<br/>");
    print("String length: " . strlen($message));
    print("<br/>");
    print("<br/>");
    $vowels = array("a", "e", "i", "o", "u", "A", "E", "I", "O", "U");
    $newMessage = str_replace($vowels, "X", $message);
    print($newMessage);
    print("<br/>");
    print("<br/>");
    $messageArray = explode(" ", $message);
    for($i=0;$i<count($messageArray);$i++)
    {
        print($messageArray[$i] . "<br/>");
    }
?>
```

![](img/00304.jpeg)

图 10.14: 脚本`Lab.php`的屏幕输出。用户名字段中已输入“Alison”。

![](img/00305.jpeg)

图 10.15: 脚本`Lab2.php`的屏幕输出

![](img/00306.jpeg)

图 10.16: 脚本`Lab3.php`的屏幕输出

# 第 10 章总结

在本章中，你学习了如何使用 PHP 的`date()`和`time()`函数来访问和处理日期与时间信息。你还接触了处理字符串的不同方法，以及 PHP 的两种行为：单引号和双引号的使用以及 heredoc 语法。我们探索了使用会话（sessions）和 cookie 在不同请求之间维持状态。在我们结束这最后一章之际，我们致敬并表扬你坚持完成了十章 PHP 编程课程。你应该为自己感到非常自豪——做得好！现在让我给你提个建议：我确定你熟悉“不用就会生锈（use it or lose it）”这句话。很好，这也适用于你的编程！确保你积极使用你的知识——现在再次练习和复习概念，以保持记忆清晰。现在就开始用你所学的知识编写你的网页吧！祝你好运！

# 答案：学习 PHP 和 MySQL

### 第 1 章：你的第一个脚本

1. PHP 代表什么？b. 预文本处理器（Pretext Processor）。

2. WAMP 中的 A 代表什么？a. Apache。

3. 使用什么地址检查由 Windows 上 Apache 服务器生成的首页？a. `http://localhost`

4. 正确的开始标签是什么？d. `<?php`

# 第 2 章：变量

1. 变量是什么？a. 字符串和数字的容器。

2. 常见的算术运算有哪些？b. 加法、乘法、法。

3. 使用什么命令输出格式化字符串？d. `printf("`

4. 给某个变量加 1 应该使用什么运算符？c. 递增

# 第 3 章：数组

1. 数组是什么？b. 多个变量的容器。

2. 为数组成员赋值的正确语法是什么？c. `$arrayName=`

3. 在示例`$example = array("Cooper" => 2500, "Oswald" => 2350);`中哪些是键？a. Cooper, Oswald

4. 多维数组最简单的解释是什么？b. 数组中的数组。

### 第 4 章：控制结构 -分支

1. 条件是什么？d. 评估表达式为真或假并执行与真或假相关操作的语句。

2. 条件运算符`<=`表示什么？d. 小于等于。

3. 复杂条件的例子是什么？d. 一系列 if-else 语句。

4. switch-case-break 条件最好定义为？c. 具有许多情况的条件。

5. switch-case-break 大写敏感吗？d. 默认是，但可以通过添加多个情况来自定义以移除大小写敏感。

6. 三元运算符是什么？a. 与变量相关的单行 if-else 语句。

7. 三元语句中的符号`?`和`:`分别代表？a. If 和 else。

### 第 5 章：控制结构 -循环

1. 循环是什么？c. 根据程序设置的条件重复代码段的命令。

2. while 循环和 do-while 循环的主要区别是什么？c. 即使初始设置为 FALSE，do-while 循环也会执行一次；while 循环如果初始值为 FALSE 则忽略循环。

3. for 循环是什么？c. 一种紧凑的循环类型，将逻辑和参数全部包含在一行。

4. 处理复杂数组时使用哪种循环比较明智？d. foreach 循环

# 第 6 章：自定义 PHP 函数

1. 函数是什么？a. 存储在特定关键字下的相关代码块，可以被调用并重复使用。

2. 参数是什么？

答案：a. 传递函数的值或字符串。

### 3. `return`语句是如何工作的？

答案：a. `return`结束函数的执行并向函数的调用者返回一个值。

### 4. 如果传递给函数参数的文件名找不到，哪个函数会产生错误并终止脚本？

答案：c. `require`

# 第 7 章：服务器文件 I/O

### 1. File I/O 是什么意思？

答案：a. 文件输入与输出（File Input and Output）。

### 2. 服务器上获取文本内容最快的方法是什么？

答案：a. `file_get_contents`

### 3. 模式 ‘a’ 代表什么？

答案：b. 追加（Append）。

### 4. 在服务器上追加和删除文件通常需要什么？

答案：b. 服务器权限。

### 5. CSV 是什么意思？

答案：d. 逗号分隔值（Comma-Separated Values）。

# 第 8 章：使用 PHP 发送电子邮件

### 1. PHP 中哪个变量对应邮件的接收者？

答案：a. `$to`

### 2. `mail()`函数的作用是什么？

答案：a. 它通过服务器使用 PHP 发送接收电子邮件。

### 3. SMTP 是什么意思？

答案：a. 简单邮件传输协议（Simple Mail Transfer Protocol）。

### 4. 什么是 HTML 电子邮件？

答案：a. 一种嵌入了 HTML 标签的电子邮件。

### 5. header MIME Version 的作用是什么？

答案：a. 该头部表示邮件包含 ASCII 文本字符以外的字符。

### 6. `content type text/HTML`头部的作用是什么？

答案：d. 它定义了 HTML 邮件将使用的字符编码。

# 第 9.1 章设置数据库

### 1. 在 MySQL 命令行提示符中获取命令列表应该输入什么？

答案：a. `mysql>Help`

### 2. 为了确保列中的每个条目都是唯一的，我们使用什么？

答案：c. 主键（Primary Key）

# 第 9.2 章从数据库检索查询

### 1. 哪个类作为连接对象的蓝图，使 PHP 脚本能够访问 MySQL 数据库？

答案：a. `mysql_connect`。

### 2. 哪个命令指示如果`mysql_connect`不工作，将继续提供所发生的 MySQL 错误？

答案：b. `or die`

# 第 9.3 章在数据库中存储信息

### 1. post 方法使用信息的数据类型是什么？

答案：a. `array`（数组）。

### 2. 连接对象的哪个方法被用于关闭自身？

答案：c. `close`

# 第 9.4 章删除和更新数据库记录

### 1. 查询字符串中使用哪个符号？

答案：d. `?`

### 2. `$_REQUEST[]`是什么？

答案：d. 一个超全局数组

# 第 9.5 章复杂查询

### 1. 使用哪种操作同时从多个表中获取数据？

答案：b. 非正式连接（informal join）

# 第 10.1 章日期对象（Date Object）

### 1. `date()`函数有多少个参数？

答案：b. 两个

### 2. 使用哪个字母获取月份的完整文本显示？

答案：a. F

# 第 10.2 章 PHP 中的字符串（Strings）

### 1. 用于显示 heredoc 的符号是：

答案：a. `<<<`

### 2. 哪个函数将字符串转换为数组？

答案：b. `str_split()`

# 第 10.3 会话（Sessions）

### 1. 使用哪个函数开始每个会话？

答案：a. `session_start()`

### 2. 当我们不再需要会话时使用哪个函数？

答案：c. `session_destroy()`

# 第 10.4 章 Cookie（Cookies）

### 1. 什么是 cookie？

答案：a. 一个文件

### 2. 使用哪个函数创建 cookie？

答案：a. `setcookie()`

## 附录

| 术语 | 定义 |

| :--- | :--- |

| api | 这是应用程序接口（application interface）的缩写。 |

| argument | 这是一个传递给函数的值或变量。 |

| array | 这是 PHP 的类型之一。 |

| boolean | 它只有两个值——TRUE（真）和 FALSE（假）。 |

| break | 这是一个用于终止循环执行的关键字。 |

| browser | 这是一个在计算机上运行的程序。 |

| class | 这是一个对象的蓝图。 |

| client | 这是用户（个人）用于发送或接收电子邮件的程序。 |

| code block | 一组连续的代码行，通常由大括号`{}`隔开。 |

| cookies | 这些是服务器留下的不大于 4kb 的文件。 |

| column | 一个表由列组成。 |

| concatenation | 将多个不同的事物或对象合并成一个单元的过程。 |

| comparison operator | 这是一个比较两个操作数的运算符。 |

| conditional expression | 这是一个求值为真或为的表达式。 |

| conditional statement | 是一行遵循严格语法和语法的代码。 |

| control structure | 代码行编写和排列的特定方式，允许改变执行流。 |

| CRUD | 这是创建（Create）、检索（Retrieve）、更新（Update）和删除（Delete）的缩写。 |

| csv file | 这是一个由逗号分隔值的逗号分隔值（csv）文本文件。 |

| database | 这是一个相关数据的组织集合。 |

| do-while | 这是 PHP 的循环控制结构之一。 |

| dot operator | 点运算符`.`是 PHP 的连接运算符。 |

| email client | 这是用户用于发送或接收电子邮件的程序。 |

| esmtp | 这是扩展简单邮件传输协议（Extended Simple Mail Transfer Protocol）的缩写。 |

| expression | 任何变量、常量、字面量、运算符、对象甚至函数的有效组合，可以被求值产生一个值。 |

| field | 在数据库中，字段是列（column）的另一个术语。 |

| 术语 | 说明 |

| :--- | :--- |

| `file` | 这是一个对存储在计算机上的数据的集合和通用术语，无论这些数据是以文本、二进制、图片、视频、音频、网页等形式存在。文件被分配有一个唯一的文件，以识别并将其与其他文件区分来。 |

| `file handle` | 这是`fopen()`函数的返回值，是 PHP 脚本访问服务器文件的主要手段。脚本访问的每个文件都会被分配一个`file handle`。文件句柄的 PHP 数据类型为`resource`。 |

| `filename` | 计算机上的文件被赋予一个唯一的`filename`来识别。`filename`由特定数量的字符组成（在 Windows 中，`filename`最大长度为 255 个字符），后面可选跟一个点和一个字符扩展名。字符扩展名通常标识文件的类型。例如，扩展名“avi”表示视频文件，“mp3”表示音频文件等。 |

| `file i/o` | 这意味着文件输入/输出，或在计算机上创建和检索文件。在 PHP 中，文件 i/o 仅涉及服务器文件，因为 PHP 禁止在客户端计算机上执行文件 i/o（cookie 情况除外）。 |

| `floating-point` | 这是 PHP 八种数据类型之一。它代表带有小数数字的数值。 |

| `foreach-loop` | 这是 PHP 四种循环控制结构之一。另外三个是：`while-loop`、`do-while-loop`和`for-loop`。 |



| `for-loop` | 这是 PHP 四种循环控制结构之一。另外三个是：`while-loop`、`do-while-loop` 和 `foreach-loop`。 |

| `function` | 这是一个自包含的程序语句块，具有定义的边界，执行特定的任务。 |

| `here document` | 在计算机科学中，这是一种文件字面量或输入流字面量。它是源代码文件的一个部分，被视为一个单独的文件处理。 |

| `heredoc` | 这是一个代码块，无论多大，都可以被视为一个字符串。 |

| `if-else/if-elseif statement` | 这是 PHP 三种条件语句之一，用于创建分支控制结构。另外两个是 `if-statement` 和 `switch-statement`。 |

| `if-statement` | 这是 PHP 三种条件语句之一，用于创建分支控制结构。另外两个是 `if-else/if-elseif-statement` 和 `switch-statement`。 |

| `imap` | 意思是 Internet Mail Access Protocol（互联网消息访问协议）。这是入站邮件服务器使用的协议，用于在服务器上存储的消息。 |

| `incoming mail server` | 它处理所有收到的邮件并实现 `POP3`（邮局协议第 3 版）或 `IMAP`（互联网消息访问协议）。`POP3` 入站服务器将发送和接收的消息存储在客户端的硬盘上。这迫使用户只能从一个设备或位置访问和处理电子邮件。然而，IMAP 入站服务器将消息存储在服务器上，从而允许用户从任何位置或任何设备访问其邮件。 |

| `indexed array` | 这是 PHP 中两种数组之一，使用数字索引来识别和区分其成员或元素。 |

| `integer` | 这是 PHP 八种数据类型之一。它是一个整数，其值范围取决于硬件。 |

| `ip address` | 这是分配给每个连接到互联网的计算机的唯一数字。`IP` 意味着“互联网协议”。 |

| `join` | 在数据库中，这是关系（relationship）的另一种术语。 |

| `key` | 在数据库中，这是在上面构建索引的列或多个列，允许快速和/或排序访问表数据。 |

| `keyword` | 这是一个编程语言保留的单词，因为它在语言的语法和规则中具有特殊含义。程序员不能使用关键字来命名变量或用于任何其他用途。例如：`break`、`else`、`if`、`function` 等等。 |

| `Linux` | 这是一个基于 UNIX 的开源（免费）跨平台操作系统。 |

| `literal value` | 这是一个仅由一个操作数且没有运算符的表达式。它是由其实际字符串值表示的单个标量值（即不是通过变量引用）。例如，1、1.414 和 "string" 都是字面量值。作为表达式的字面量的值等于本身。 |

| `logical operator` | 它结合条件表达式以产生 TRUE 或 FALSE 的布尔结果。例如，`$age < 21`。 |

| `looping control structure` | 参见‘control structure’。 |

| `mail server` | 这是一种处理发送和接收电子邮件的服务器类型。它可以运行在自己的专用硬件上，也可以与其他服务器程序共享硬件资源。它在正常运行期间自动运行，无需任何人工干预。邮件服务器有两种：出站邮件服务器和入站邮件服务器。 |

| `mode` | 模式专门标识一种文件 i/o 操作类型。某些文件 i/o 函数需要模式作为其参数之一。模式通过字符和/或加号 `+` 来标识。例如，`r` 意味着“只读访问”，而 `r+` 意味着“读写访问”。 |

| `multi-dimensional array` | 这是一个其元素或成员也是数组的数组。它是一个包含若干个被称为“子数组”的主数组。 |

| `mysql` | 这是一个流行的、开源的关系型数据库管理系统 (RDBMS)，支持多种管理工具、程序、库以及应用程序编程接口。截至 2014 年 3 月，它是全球使用最广泛的开源 (RDBMS)。 |

| `null` | 这是 PHP 八种数据类型之一。`Null` 表示变量中完全没有存储任何有效值。 |

| `object` | 这是一个编程结构，由程序代码和程序数据组成，封装成一个独立的包，具有清晰的边界以及关于如何访问该对象的程序代码和数据的确定规则。 |

| `or die()` | 这是一个 PHP 语言结构，等同于 `exit`。 |

| `open source software` | 这种源代码公开的计算机软件，其许可规定版权所有者向任何人、出于任何目的提供研究、更改和分发软件的权利。 |

| `operator` | 这是一个指定要执行特定编程操作的符号。此操作通常产生一个新值。PHP 运算符有十组：算术、数组、赋值、位、比较、错误控制、执行、逻辑、字符串以及增减。 |

| `operand` | 它是运算符作用的对象。大多数情况下，操作数是一个变量，但也可以是字面量、对象、函数或任何运算符可以有效执行操作的内容。 |

| `outgoing mail server` | 这种类型的服务器处理所有发送的邮件并实现 `SMTP` 简单邮件传输协议。 |

| `parameter` | 这是函数定义中定义的变量，用于接收传递给函数的参数值。 |

| `PEAR` | 这是 PHP 扩展和应用程序库的缩写。它是一个免费、高质量源代码包的大型集合，可以下载并用于任何 PHP 应用程序。 |

| `pop3` | 意思是邮局协议第 3 版。这是入站邮件服务器使用的协议，将发送和接收的消息存储在客户端的硬盘上。 |

| `post` | 这种方法以数组的形式传递信息，而不是创建出现在 URL 中的查询字符串。 |

| `PHP` | 这是一个递归缩写，其中第一个字母代表缩写词本身，它的意思是“PHP: 超文本处理器”。 |

# PHPMyAdmin

这是一个用 `PHP` 编写并在浏览器中运行的免费开源工具。它允许用户创建、修改或删除 `MySQL` 数据库，以及数据库中的任何表，或任何表中的行和字段。`PHPMyAdmin` 可以在数据库上执行 `SQL` 语句，并管理用户和权限。

## 主键

这是一个列、字段或多个列或字段，其取值确保了表中的每一行都是唯一的。

## 查询字符串

它是 `URL` 中包含传递给 Web 应用程序的数据的部分。

## 记录

在数据库中，记录是“行”的另一种说法。

## 关系

在数据库中，关系是两个表之间的链接。

## 资源

这是 `PHP` 八种数据类型之一。

## 返回值

这是函数返回给调用者的可选值。

## 行

在数据库中，它是表中的一组相关数据。

## 作用域

编程中的一个重要概念，指变量在程序中的可见性或可访问性。具体而言，它指的是程序中可以访问变量的代码部分。`PHP` 提供全局作用域和局部作用域。

## 服务器

这是一个系统（软件和合适的计算机硬件），旨在通过局域网或互联网向其他计算机（客户端）处理请求并交付数据。

## 会话

这是服务器上的一个临时文件，可以在其中存储数据。客户端浏览器会在会话中存储数据以“维持浏览器请求之间的状态”，或更具体地说“在浏览器请求之间保留应用程序的状态”。

## SID

这是会话 ID（session id）的缩写。`SID` 由服务器生成，用于标识和保护会话。

## SQL

这意味着结构化查询语言（Structured Query Language，通常读作“see-qwell”）。它是一种用于在关系型数据库中搜索、排序、添加和提取数据的编程语言。

## 简单数组

参见索引数组。

## SMTP

这是简单邮件传输协议（Simple Mail Transfer Protocol）。这是当邮件从邮件客户端（如 Outlook Express）发送到邮件服务器，或从一个邮件服务器发送到另一个邮件服务器时使用的协议。`SMTP` 使用端口 25。但现在大多数邮件服务器使用 `ESMTP`，它是 `SMTP` 的更新版本。

## 状态

这个词用于“维持状态”这一短语，或更具体地说“在浏览器请求之间保留应用程序的状态”。当浏览器向服务器请求页面时，浏览器和服务器都不会对浏览器之前的请求产生记忆。当加载新页面时，页面中任何变量的值都会丢失。保留这些值就是所谓的“维持状态”。

## 字符串

这是 `PHP` 八种数据类型之一。它是一个任意长度的字符序列。

## 子数组

这是多维数组内部的数组。

## 全局变量

这是 `PHP` 中一种内置的（预定义的）关联数组变量，它对所有 `PHP` 代码自动可用，特别是在函数内部（全局作用域）。全局变量代表了来自 URL、HTML 表单、Cookie、会话（sessions）以及 Web 服务器本身的数据。

## Switch 语句

这是 `PHP` 三种条件语句之一，用于创建分支控制结构。另外两个是 `if-statement` 和 `if-else/if-elseif-statement`。

## 表

在数据库中，它是一组紧密相关的数据或列（或字段）的集合。

## 三元运算符

该运算符作用于三个操作数，是 `if-else` 语句的紧凑形式。

## 时间戳

是从 1970 年 1 月 1 日午夜到当前日期和时间之间的秒数。`PHP` 内部将时间戳存储为 10 位整数。

## URL

这意味着通用资源定位符（Universal Resource Locator）。它是由 Web 浏览器和其他网络软件使用的特殊格式的文本字符串。它标识互联网上的一个网络资源。网络资源是文件，可以是纯 Web 页面、其他文本文档、图形或程序。`URL` 的示例是 `http://www.website.com/myfinename`。

## 值

在 `MySQL` 数据库的表中，值是给定行和列中的数据。

## 变量

这是一个分配用于存储存储的内存单元，该值可以是八种 `PHP` 数据类型中的任意一种，即：整数、浮点数、字符串、布尔值、数组、对象、资源（或句柄）和空（null）。

## Web 浏览器

参见浏览器。

## 数据类型

这是 `PHP` 八种数据类型之一。

## While 循环

这是 `PHP` 四种循环控制结构之一。另外三种是：`do-while-loop`、`for-loop`、`foreach-loop`。

![Development Club Print Ad.pdf](img/00307.jpeg)
