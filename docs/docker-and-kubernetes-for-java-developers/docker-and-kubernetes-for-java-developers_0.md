

# Java 开发者 Docker 与 Kubernetes 指南

![](img/Image00130.jpg)

**伯明翰 - 孟买买**

## 制作致谢

| 作者 | 文字编辑 |
| :--- | :--- |
| Jaroslaw Krochmalski | Safis Editing |
| 审稿员 | Pierre Mavro |
| 项目协调员 | Kinjal Bari |
| 策划编辑 | Vijin Boricha |
| 校对 | Safis Editing |
| 采购编辑 | Prachi Bisht |
| 索引员 | Mariammal Chettiyar |
| 内容开发编辑 | Trusha Shriyan |
| 视觉设计 | Kirk D'Penha |
| 技术编辑 | Varsha Shivhare |
| 制作协调 | Shantanu Zagade |

## 关于作者

**Jaroslaw Krochmalski** 是一位热情的软件设计者和开发者，专攻金融领域。他在软件开发领域拥有超过 12 年的经验。他是整洁代码和软件工艺的热爱好者。他是一位认证 Scrum 大师，也是敏捷开发的粉丝。他的专业兴趣包括 Web 应用开发的新技术、设计模式、企业架构和集成模式。

他自 2000 年以来一直从事专业的软件设计和开发，并从 2002 年起使用 Java 作为主要编程语言。过去，他曾在 **Kredyt Bank**（**KBC**）和 Bank BPS 等公司工作过许多大型项目，例如国际汇款、快速支付和收收系统。他目前在丹麦公司 7N 顾问，担任 Nykredit 银行的基础设施架构师。你可以通过 Twitter `@jkroch` 或通过邮箱 `jarek@finsys.pl` 与他联系。

## 关于审稿员

**Pierre Mavro** 住在巴黎郊区。他是一个开源软件爱好者，使用 Linux 已超过 10 年。目前，他在 Criteo 担任首席 SRE，管理分布式系统和 NoSQL 技术。在过去的几年里，他一直设计高可用性基础设施、公有云和私有云基础设施，并在一家高频交易公司工作过。他还写了一本关于 MariaDB 的书，名为 *MariaDB High Performance*。他也是骑行者应用程序 Nousmotards 的创始人之一。

## www.PacktPub.com

如需与书籍相关的支持文件和下载，请访问 [www.packtPub.com](http://www.packtpub.com)。你知道 Packt 为出版的每本书都提供 eBook 版本，并提供 PDF 和 ePub 文件吗？你可以在 [www.packtPub.com](http://www.packtpub.com) 升级到 eBook 版本，作为纸质书客户，你有权获得 eBook 版的折扣。请联系我们 `service@packtpub.com` 了解更多详情。在 [www.packtPub.com](http://www.packtpub.com)，你还可以阅读免费技术文章合集，订阅一系列免费新闻邮件，并接收 Packt 书籍和 eBook 的独家折扣和优惠。

![](img/Image00003.jpg)

[`www.packtpub.com/mapt`](https://www.packtpub.com/mapt)

通过 Mapt 获取最需求的软件技能。Mapt 让你完全访问所有 Packt 图书和视频课程，以及行业领先的工具，帮助你规划个人发展并职业职业。

## 为什么要订阅？

- 可在 Packt 出版的每本书中全文搜索
- 复制、粘贴、打印和书签内容
- 按需提供并可通过网络浏览器访问

## 客户反馈

感谢购买 Packt 的此书。在 Packt，质量是我们编辑流程的核心。为了帮助我们改进，请在亚马逊的亚马逊页面上这本书留下诚实的评论：[`www.amazon.com/dp/1786468395`](https://www.amazon.com/dp/1786468395)。

如果你想加入我们的定期审稿员团队，可以发送电子邮件至 `customerreviews@packt.com` 联系我们。

## 目录

### 1. 前言

- 本书涵盖的内容
- 本本书需要的知识
- 本本书的读者
- 惯例
- 支持
- 下载代码
- 下载图片
- 错误说明
- 盗版问题
- 问题

### 2. Docker 简介

- Docker 背后的思想
- 虚拟化与容器化
- Docker 概念——镜像与容器
- Docker 注册表、仓库
- 其他工具
- 安装 Docker
  - 在 macOS 上安装
  - 在 Linux 上安装
  - 在 Windows 上安装

### 3. 网络与持久化存储

- 网络
  - Docker 网络类型
    - 桥（`bridge`）
    - 主机（`host`）
    - 无（`none`）
- 网络命令
- 创建并检查网络
- 将容器连接到网络
- 端口暴露与端口映射
- 持久化存储
- 卷相关命令
- 创建卷
- 删除卷
- 卷驱动程序

### 4. 微服务实战

- 微服务简介
- 单体架构与微服务的对比
  - 单体架构
  - 微服务架构
- 维护数据一致性
- Docker 的作用
- Kubernetes 的作用
- 何时使用微服务架构

### 5. 创建 Java 微服务

- REST 简介

#### 5.1 HTTP 方法

#### 5.2 Java 中的 REST

##### 5.2.1 Java EE7 - 使用 Jersey 的 JAX-RS

###### JAX-RS 注解

##### 5.2.2 Spring Boot

#### 5.3 编写 Spring Boot 微服务

##### 5.3.1 Maven 构建文件

###### 应用入口点

###### 领域模型和仓库

###### REST 控制器

###### API 文档化

#### 5.4 运行应用程序

#### 5.5 发起调用

##### Spring RestTemplate

##### HTTPie

##### Postman

##### Paw for Mac

#### 5.6 Spring Initializr

#### 5.7 总结

### 6. 使用 Java 应用创建镜像

#### 6.1 Dockerfile

#### 6.2 Dockerfile 指令

##### FROM

##### MAINTAINER

##### WORKDIR

##### ADD

##### COPY

##### RUN

##### CMD

##### The ENTRYPOINT

##### EXPOSE

##### VOLUME

##### LABEL

##### ENV

##### USER

##### ARG

##### ONBUILD

##### STOPSIGNAL

##### HEALTHCHECK

##### 使用 Maven 创建镜像

##### 构建镜像

##### 创建和删除卷

#### 6.3 总结

### 7. 使用 Java 应用运行容器

#### 7.1 启动和停止容器

##### 启动

##### 停止

##### 列出运行中的容器

##### 移除容器

#### 7.2 容器运行模式

##### 前台模式

##### 后台模式

##### 连接到运行中的容器

#### 7.3 监控容器

##### 查看日志

##### 检查容器

##### 统计信息

##### 容器事件

#### 7.4 重启策略

##### `no`

##### `always`

##### `on-failure`

##### `unless-stopped`

##### 更新运行中容器的重启策略

#### 7.5 资源运行时约束

##### 内存

##### 处理器

##### 更新运行中容器的约束

#### 7.6 使用 Maven 运行

##### 插件配置

##### 启动和停止容器

#### 7.7 总结

### 8. Kubernetes Intro

#### 8.1 为什么我们需要它

#### 8.2 Kubernetes 基础概念

##### Pods

##### ReplicaSets

##### Deployment

##### Services

##### kube-dns

##### Namespace

##### Nodes

###### Kubelet

###### Proxy

###### Docker

##### Master node

###### etcd

###### API server

###### scheduler

##### 可用工具

###### kubectl

###### Dashboard

###### Minikube

#### 8.3 总结

### 9. 使用 Java 使用 Kubernetes

#### 9.1 安装 Minikube

##### 在 Mac 上安装

##### 在 Windows 上安装

##### 在 Linux 上安装

##### 启动本地集群

#### 9.2 安装 kubectl

##### 在 Mac 上安装

##### 在 Windows 上安装

##### 在 Linux 上安装

#### 9.3 在 Kubernetes 集群上部署

##### 创建服务

##### 创建 deployment

##### 与容器交互并查看日志

##### 手动扩缩

##### 自动扩缩容

##### 查看集群事件

##### 使用 Kubernetes dashboard

#### 9.4 Minikube addons

#### 9.5 清理

#### 9.6 总结

### 10. 与 Kubernetes API 工作

#### 10.1 API 版本控制

##### Alpha

##### Beta

##### Stable

#### 10.2 身份验证

##### HTTP 基础认证

##### 静态令牌文件

##### 客户端证书

##### OpenID

#### 10.3 授权

##### 基于属性的访问控制

##### 基于角色的访问控制（RBAC）

##### WebHook

##### AlwaysDeny

##### AlwaysAllow

#### 10.4 Admission 控制

#### 10.5 使用 API

##### API 操作

##### 示例调用

###### 创建服务

###### 创建 deployment

###### 删除服务和 deployment

#### 10.6 Swagger 文档

#### 10.7 总结

### 11. 在云端部署 Java

#### 11.1 使用云、Docker 和 Kubernetes 的优势

#### 11.2 安装工具

##### Python 和 PIP

##### AWS 命令行工具

##### Kops

##### jq

#### 11.3 配置 Amazon AWS

#### 11.4 创建管理用户

##### 为 kops 创建用户

#### 11.5 创建集群

##### DNS 设置

###### AWS 托管的根域名

###### AWS 托管的子域名

###### 在其他注册处购买的域名的 Route 53

###### AWS Route 53 中的子域名，域名在别

##### 检查区域可用性

##### 创建存储

##### 创建集群

##### 启动集群

#### 11.6 更新集群

#### 11.7 安装仪表板

#### 11.8 总结

### 12. 更多资源

#### 12.1 Docker

##### Awesome Docker

##### 博客

##### 交互教程

#### 12.2 Kubernetes

##### Awesome Kubernetes

##### 教程

##### 博客

##### 扩展

##### 工具

###### Rancher

###### Helm 和 charts

###### Kompose

###### Kubetop

###### Kube-applier

# 前言

想象一下在几分钟内就能 Apache Tomcat 或 Wildfly 上创建并测试 Java EE 应用程序，并快速部署和管理 Java 应用程序。听起来好得不可真实？你有理由欢呼了，因为通过利用 Docker 和 Kubernetes，这些场景都是可能的。

本书将从介绍 Docker 开始，深入探讨其网络和持久化存储概念。随后，你将接触微服务的概念，并学习如何将 Java 微服务作为 Docker 容器部署和运行。接着，本书将重点关注 Kubernetes 及其特性。你将从使用 `Minikube` 运行本地集群开始。下一步是将你的 Java 服务部署到真实的云端，运行在 Amazon AWS 之上的 Kubernetes 上。在书结束时，你将获得一些高级主题的实战经验，进一步扩展你对 Docker 和 Kubernetes 的知识。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

# 本书内容

第 1 章，*Docker 简介*，介绍了 Docker 背后的设计原理，并展示了 Docker 与传统虚拟化之间的区别。本章还解释了 Docker 基本概念，如镜像、容器和 `Dockerfiles`。

第 2 章，*网络与持久化存储*，解释了 Docker 容器中的网络和持久化存储是如何工作的。

第 3 章，*微服务实*，概述了微服务的定义，并解释了它们与单体架构相比的优势。

第 4 章，*创建 Java 微服务*，探索了如何利用 Java EE7 或 `Spring Boot` 快速构建 Java 微服务的配方。

第 5 章，*使用 Java 应用创建镜像*，教授了如何手动或通过 `Maven` 构建文件将 Java 微服务打包成 Docker 镜像。

第 6 章，*使用 Java 应用运行容器*，展示了如何使用 Docker 运行容器化的 Java 应用程序。

第 7 章，*Kubernetes 简介*，介绍了 Kubernetes 的核心概念，如 Pod、节点、服务和部署。

第 8 章，*在 Java 中使用 Kubernetes*，展示了如何在本地 Kubernetes 集群上部署已封装为 Docker 镜像的 Java 微服务。

第 9 章，*使用 Kubernetes API*，展示了如何使用 Kubernetes API 自动化创建 Kubernetes 对象（如服务或部署）。本章提供了如何使用 API 获取集群状态信息的示例。

第 10 章，*在云端 Kubernetes 上部署 Java*，向读者展示了如何配置 Amazon AWS EC2 实例使其适用于运行 Kubernetes 集群。本章还提供了如何在 Amazon AWS 云上创建 Kubernetes 集群的精确指令。

第 11 章，*更多资源*，探索了 Java 和 Kubernetes 如何引导读者参考互联网上的优质资源，以进一步扩展关于 Docker 和 Kubernetes 的知识。

# 本书所需的条件

对于本书，你需要任何一台不错的 PC 或 Mac，并且能够运行现代版本的 Linux、Windows 10 64 位或 macOS。

# 本书的读者

本书面向想要进入容器化世界的 Java 开发者。读者将学习 Docker 和 Kubernetes 如何帮助在自己的基础设施或云端上部署和管理 Java 应用程序。

# 写作规范

在书中，你会发现许多用于区分不同类型信息的样式。以下是一些示例：

- **新术语**以粗体显示。
- **重要词汇**以粗体显示。
- **重要备注**显示在框内。
- **提示与技巧**如本所示。
- **警告**显示在框内。
- 代码输入或输出写法如下：

```json
{
  "apiVersion": "v1",
  "kind": "Pod",
  "metadata": {
    "name": "rest_service",
    "labels": {}
  },
  "spec": {
    "containers": [
      {
        "name": "rest_service",
        "image": "rest_service",
        "ports": [
          {
            "containerPort": 8080
          }
        ]
      }
    ]
  }
}
```

- 命令行输入：

```bash
rm $(docker ps -a -f status=exited)
```

- 命令显示为：`docker build`
- 文件名显示为：`Dockerfile`
- 路径显示为：`/path/to.xxx`
- 网址显示为：`https://www.chenjin5.com`
- Twitter 账号显示为：`@handle`
- 菜单项显示为：`Click`

# 读者反馈

我们随时欢迎读者的反馈。请告诉我们对这本书的看法，无论喜欢还是不喜欢。反馈对我们非常重要，有助于我们开发读者感兴趣的内容。反馈请邮件至 `feedback@packt.com` 并注明书名。如果你对某个主题专业并兴趣编写书籍，请查看我们的作者指南 [www.packt.com/authors](http://www.packt.com/authors)。

# 客户支持

现在你是 Packt 书的所有者，我们有很多方法帮助你充分利用。

# 下载示例代码




你可以从你的账户[`www.packt.com`](http://www.packt.com)下载本书的示例代码。如果你是在其他地方购买的，可以访问[`www.packt.com/support`](http://www.packt.com/support)并注册让文件通过电子邮件发送。你可以按照以下步骤下载：

1. 使用你的邮箱和密码登录或注册网站。
2. 将鼠标悬停在顶部的`SUPPORT`标签上。
3. 点击`Code Downloads & Errata`。
4. 在`Search`框中输入书名。
5. 选择你需要下载代码的书。
6. 从你购买书籍的下拉菜单中选择。
7. 点击`Code Download`。

文件下载后，请确保使用最新版本的软件解压或提取文件夹：

- Windows：WinRAR / 7-Zip
- Mac：Zipeg / iZip / UnRarX
- Linux：7-Zip / PeaZip

本书的代码包也托管在 GitHub 上，地址为[`github.com/PacktPublishing/Docker-and-Kubernetes-for-Java-Developers`](https://github.com/PacktPublishing/Docker-and-Kubernetes-for-Java-Developers)。我们还有其他来自丰富书籍和视频目录的代码包可以在[`github.com/PacktPublishing/`](https://github.com/PacktPublishing/)找到。去看看吧！

# 下载本书的彩色图片

我们还为您提供了一个 PDF 文件，其中包含了书中使用的截图/图表的彩色版本。这些彩色图片将帮助您更好地理解输出的变化。您可以从此处下载该文件：[`http://www.packtpub.com/sites/default/files/downloads/Bookname_ColorImages.pdf`](http://www.packtpub.com/sites/default/files/downloads/Bookname_ColorImages.pdf)、[`DockerandKubernetesforJavaDevelopers`](https://github.com/PacktPublishing/DockerandKubernetesforJavaDevelopers)、[`ColorImages.pdf`](http://www.packtpub.com/sites/default/files/downloads/Bookname_ColorImages.pdf)。

# 勘误

尽管我们尽力确保内容的准确性，但错误仍然不可所避免。如果您在我们的某本书书中发现了错误——可能是文本或代码中的错误——如果您能告诉我们，我们将不胜感激。通过这样做，您可以避免其他读者产生困扰，并帮助我们改进这本书的后续版本。

如果您发现任何错误，请访问[`www.packtpub.com/submit-errata`](http://www.packtpub.com/submit-errata)，选择您的书籍，点击“错误提交表”（Errata Submission Form）链接，并输入错误的详细信息。一旦错误通过验证，您的提交将被接受，错误将上传到我们的网站，或添加到该书“错误”部分下的现有错误列表中。

要查看之前提交的错误，请访问[`www.packtpub.com/books/content/support`](https://www.packtpub.com/books/content/support)，在搜索框中输入书名。所需信息将显示在“错误”部分。

# 盗版

互联网上受版权材料的盗版是所有媒体中持续存在的问题。在 Packt，我们非常重视对版权和许可的保护。如果您在互联网上发现任何形式的我们作品非法副本，请立即向我们提供地址或网站名称，以便我们采取补救措施。

请通过`copyright@packtpub.com`与我们联系，并附上疑似盗版材料的链接。感谢您帮助保护我们的作者以及保护我们为您提供价值内容的能力。

# 问题

如果您对本书的任何方面有任何问题，可以通过`questions@packtpub.com`与我们联系，我们将尽力解决这些问题。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

# Docker 简介

在本章中，我们要做的第一件事是解释 Docker 背后的原理及其架构。我们将涵盖镜像、层和容器等 Docker 概念。接下来，我们将安装 Docker 并学习如何从`remote`注册表拉取示例基础 Java 应用镜像并在本地机器上运行它。

Docker 最初作为平台即服务公司 dotCloud 的内部工具创建的。2013 年 3 月，它作为开源项目公开发。其源代码在 GitHub 上供所有人免费获取，地址为[`https://github.com/docker/docker`](https://github.com/docker/docker)。不仅是 Docker Inc. 的核心团队在开发 Docker，还有许多知名机构也投入时间和精力来增强和贡献 Docker，例如 Google、Microsoft、IBM、Red Hat、Cisco systems 等。

Kubernetes 是 Google 开发的一种种工具，根据其在 Borg（Google 自建的容器系统）上学到的最佳实践，用于在计算机集群中部署容器。在编排、自动化部署、管理和伸缩容器方面，Kubernetes 补充了 Docker；它通过保持跨集群的容器部署平衡来管理 Docker 节点的负载负载。Kubernetes 还提供了容器之间通信的方法，无需开放端口。

# Docker 背后的原理

Docker 背后的原理是将应用程序及其所需的所有项打包成一个单一的标准化单元。这些依赖项可以是二进制文件、库、JAR 文件、配置文件、脚本等。

Docker 将所有这些封装成一个完整的文件系统，包含运行 Java 应用程序所需的虚拟机本身、应用服务器（如 Wildfly 或 Tomcat）、应用程序代码以及`runtime`库，基本上就是您在服务器上安装和部署以运行应用程序的所有内容。

有了 Docker，您可以在无需在主机上安装 Java 环境的情况下运行 Java 应用程序。所有不兼容 JDK 或 JRE、应用服务器版本错误等问题都消失了。升级也变得简单易行，只需在主机上运行新版本的容器即可。

如果你需要进行一些清理，只需销毁 Docker 镜像即可，就像什么都没有发生过一样。不要将 Docker 视为一种编程语言或框架，而应将其视为一个帮助解决安装、分发和管理软件等常见问题的工具。

它允许开发者和 DevOps 在任何地方构建、交付和运行代码。任何地方也意味着多台机器，而这正是 Kubernetes 派上用场的地方；我们稍后会回到这一点。

将所有的应用程序代码和运行时依赖封装成一个单一且完整的软件单元似乎与虚拟化引擎相同，但事实远如此，正如我们现在解释的那样。为了充分了解 Docker 到底是什么，首先我们需要理解传统虚拟化和容器化之间的区别。让我们现在对比这两种技术。

# 虚拟化与容器化的对比

传统的虚拟机代表了硬件级别的虚拟化。本质上，它是一个安装了 BIOS 和操作系统的完整虚拟化物理机。它运行在宿主机操作系统之上。你的 Java 应用程序在虚拟化环境中的运行方式就像它在你自己的机器上正常运行一样。

为你的应用程序使用虚拟机有很多优势。每台虚拟机都可以拥有完全不同的操作系统；例如，可以是不同的 Linux 发行版、Solaris 或 Windows。从定义上说，虚拟机也是非常安全的；它们是箱子里完全隔离的完整操作系统。

然而，任何东西都是没有免费的。虚拟机包含了操作系统运行所需的所有功能：核心系统库、设备驱动程序等。有时它们会非常消耗资源且笨重。虚拟机需要完整安装，这有时可能非常繁琐且不于设置。

最后，但同样重要的是，在虚拟机中执行应用程序你需要更多的计算能力和资源，因为管理程序需要首先导入虚拟机，然后启动它，这需要时间。然而，我相信，在运行 Java 应用程序时，拥有完整的虚拟化环境并不是我们经常需要的。

Docker 带着容器化的概念来解于之急。Java 应用程序（当然，不仅限于 Java）运行在 Docker 上，运行在一个名为“容器”的隔离环境中。容器并不是流行意义上的虚拟机。它的行为类似于某种操作系统虚拟化，但完全没有仿真。

主要的区别在于，虽然每个传统的虚拟机镜像都运行在独立的客体操作系统上，但 Docker 容器运行在宿主机上运行的同一个内核中。容器是自给自足的，它不仅与底层操作系统隔离，还与其他容器隔离。它有自己独立的文件系统和环境变量。

自然地，容器之间可以相互通信（例如应用程序容器和数据库容器），也可以共享磁盘上的文件。这就是与传统虚拟化对比时的主要区别，因为容器运行在它们相同的内核中，它们利用了更少的系统资源。

所有的操作系统核心软件都从 Docker 镜像中移除了。基础容器可以是、且通常是非常轻级的。它没有与经典虚拟化管理程序和客体操作系统相关的开销。通过这种方式，你可以为 Java 应用程序实现几乎是裸机的核心性能。

此外，由于容器开销极小，容器化 Java 应用程序的启动时间通常很短。你还可以在几秒钟部署数百个应用程序容器，以缩短供应软件所需的时间。我们将在后续章节中通过 Kubernetes 实现这一点。

尽管 Docker 与传统的虚拟化引擎非常不同。请注意，容器并不能在所有用例下替代虚拟机；仍然需要经过深思熟虑来确定什么对你的应用程序最好。两种解决方案都有它们自己的优势。

一方面，我们拥有性能中等但完全隔离安全的虚拟机；另一方面，我们拥有缺少某些关键功能但具备高性能、且可以快速部署的容器。让我们看看使用 Docker 容器化还能获得哪些其他好处。

# 使用 Docker 的优势

正如我们之前提到的，使用 Docker 的主要可见收益将是极快的性能和很短的供应时间。你可以快速轻松地创建或销毁容器。

容器与其他 Docker 容器高效地共享操作系统内核和所需的库。正因为如此，运行在容器中的多个版本的应用程序将非常轻量级。结果是更快的部署、更容易的迁移和启动时间。

在部署 Java 微服务时，Docker 特别有用。我们将在后续章节中详细介绍微服务。微服务应用程序由一系列分离的服务组成，通过 API 与其他通信。微服务将应用拆分为许多小进程。它们是单体应用的对立面，单体应用将所有操作作为一个单个进程或一组大型进程运行。

使用 Docker 容器允许你部署现成的软件，这些软件具有可移植性且极易分发。你的容器化应用程序只需运行在它的容器内部；不需要安装。

缺乏安装过程是一个巨大的优势；它消除了软件和库冲突、甚至是驱动兼容性问题等问题。Docker 容器是可移植的；它们可以在任何地方运行：你的本地机器、远程服务器以及私有云或公共云。

所有主要的云计算提供商，如`Amazon Web Services`（`AWS`）和 Google 的计算平台现在都支持 Docker。运行在（比如）Amazon EC2 实例上的容器可以很容易转移到其他环境，实现完全相同的一性和功能。

Docker 在你的基础设施层之上提供的额外抽象层是一个不可或缺的功能。开发者可以创建软件，而无需担心它以后运行在什么平台上。

Docker 拥有 Java 同样的承诺：编写一次，随处运行；只不过不是配置代码，而是按照你想要的方式配置服务器（通过选择操作系统、调整配置文件、安装依赖项），并且你可以确定你的服务器模板在任何运行 Docker 的宿主机上运行方式都完全相同。

由于 Docker 可重复的构建环境，它特别适用于测试，尤其是在你的持续集成或持续交付流中。你可以快速启动相同的环境来运行测试。由于容器镜像每次都是相同的，你可以分发工作负载并并行运行测试，而没有任何问题。

Docker 容器的使用加速了持续集成。不再有无休止的构建-测试-部署循环；Docker 容器确保了应用程序在开发、测试和生产环境中的运行方式完全一致。

代码随着时间的推移而增长变得越来越棘手。这就是为什么“不可变基础设施”的思想现在越来越流行，容器化概念也变得如此广泛。

通过将 Java 应用程序放入容器中，你可以简化部署和扩展的过程。通过拥有一个几乎不需要配置管理的轻量级 Docker 主机，你只需要通过向主机部署和重新部署容器来简单地管理应用程序。而且，由于容器非常轻量，这只需要几秒钟。

我们之前已经讨论了很多镜像和容器，但还没有进入细节。现在让我们深入探讨，看看 Docker 镜像和容器到底是什么。

# Docker 概念——镜像与容器

在处理 Kubernetes 时，我们将使用 Docker 容器；它是一个开源容器集群管理器。为了运行自己的 Java 应用程序，我们需要先创建一个镜像。让我们从 Docker 镜像的概念开始。

## 镜像

将镜像想象成一个只读模板，它是创建容器的基础基础。它就像一份配方，包含了应用程序运行所需的所有内容的定义。

它可以是一个带有应用服务器（例如`Tomcat`或`Wildfly`）的 Linux 以及你的 Java 应用程序本身。每个镜像都从基础镜像开始；例如`Ubuntu`（一个 Linux 镜像）。

虽然你可以从一个简单的镜像开始并在上方构建应用程序技术栈，你也可以从互联网上成百上千的镜像中挑选一个已经准备好的。有很多对 Java 开发者非常有用的镜像：`openjdk`、`tomcat`、`wildfly`等。我们稍后将使用它们作为自己镜像的基础。

拥有一个已经安装并正确配置好的 Wildfly 作为你自己镜像的起点要容易得多。这样你就可以专注于你的 Java 应用程序了。如果你是构建镜像的新手，与自己开发相比，下载一个专门的基础镜像是获得速度提升的绝佳方法。

镜像是通过一系列被称为“指令”的命令创建的。指令放置在`Dockerfile`中。`Dockerfile`只是一个纯文本文件，包含了一系列有序的`root`文件系统更改（同于运行启动应用服务器的命令、添加文件或目录、创建环境变量等）以及稍后在容器运行时使用的相应执行参数。

当你启动构建镜像的过程时，Docker 会读取`Dockerfile`并逐条执行指令。结果将是最终镜像。每条指令都会为镜像创建一个新层。该镜像层随后将成为下一条指令所创建层的父层。

Docker 镜像跨主机和操作系统具有高度的可移植性；镜像可以在任何运行 Docker 的主机上的 Docker 容器中运行。Linux 原生支持 Docker，但在 Windows 和 macOS 上必须在虚拟机中运行。

重要的是 Docker 使用镜像来运行你的代码，而不是`Dockerfile`。`Dockerfile`是在你运行`docker build`命令时用于创建镜像的。此外，如果你将镜像发布到 Docker Hub，你发布的是带有层的生成镜像，而不是源`Dockerfile`本。

我们之前提到过`Dockerfile`中的每条指令都会创建一个新层。层是镜像的内部本质；Docker 镜像由它们组成。现在让我们解释一下它们是什么以及它们的特性。

## 层

每个镜像都由一系列堆叠在一起的层组成。事实上，每一层都是一个中间镜像。通过使用`union filesystem`（联合文件系统），Docker 将所有这些层合并为一个单一的镜像实体。

联合文件系统允许透明地叠加不同文件系统的文件和目录，从而产生一个单一、一致的文件系统，如下所示：

![](img/Image00004.jpg)



在这些独立文件系统中具有相同路径的目录内容和结构将在新的类虚拟文件系统中的单个合并目录中共同显示。换句话说，顶层的文件系统结构将与下方层的结构合并。与前一层具有相同路径的文件和目录将覆盖下方的内容。删除上层将再次显示并暴露之前的目录内容。

正如我们之前提到的，层是堆叠放置的，一个在另一个之上。为了保持层的顺序，Docker 利用了层 ID（Layer IDs）和指针的概念。每层都包含 ID 和指向父层的指针。没有引用父层指针的层是栈中的第一层，即基础层。你可以从下面的图中看到这种关系：

![](img/Image00005.jpg)

层具有一些有趣的特性。首先，它们是可重用和可缓存的。你在上图中看到的指向父层的指针非常重要。当 Docker 处理你的 `Dockerfile` 时，它会查看两点：正在执行的 `Dockerfile` 指令和父镜像。

Docker 将扫描父层的所有子层，并寻找命令与当前指令匹配的层。如果找到匹配项，Docker 将跳到下一条 `Dockerfile` 指令并重复该过程。如果缓存中没有找到匹配的层，则会创建一个新的。

对于向镜像中添加文件的指令（我们稍后会详细介绍），Docker 会为每个文件内容创建一个校验和（checksum）。在构建过程中，会将此校验和与现有镜像的校验和进行对比，以检查该层是否可以从缓存中重用。

如果两个不同的镜像具有共同部分，例如 Linux Shell 或 Java 运行时，跟踪所有拉取层的 Docker 将在两个镜像中重用该 Shell 层。这是一个安全的操作；如你所知，层是只读的。在下载另一个镜像时，该层将被重用，仅从 Docker Hub 拉取差异部分。

这无疑节省了时间、带宽和磁盘空间，但它还有另一个巨大的优势。如果你修改了你的镜像（例如修改了容器化的 Java 应用程序），只有应用程序层会被修改。

当你从 `Dockerfile` 成功构建一个镜像后，你会发现后续相同 `Dockerfile` 的构建速度会快得多。一旦 Docker 为某个指令缓存了镜像层，就不需要重新构建。之后，你不再分发整个镜像，而是推送更新的部分。这使得过程变得更加简单快速。

可重用层的概念也是 Docker 与不共享任何内容的完整虚拟机相比如此轻量级的原因之一。正亏了这些层，当你拉取一个镜像时，最终不需要下载它的整个文件系统。如果你已经有了另一个包含了你要拉取的镜像某些层的镜像，那么实际上只会下载缺失的层。

不过，有一点警告，这与层的另一个特性有关：除了是可重用的外，层还是**累加的**。如果你在容器中创建一个大文件，然后进行一次 `commit`（我们稍后会介绍这一点），然后删除该文件并再次进行 `commit`；那么这个文件将仍然存在于层历史中。

想象这样一个场景：你拉取了基础 Ubuntu 镜像并安装了 Wildfly 应用服务器。然后你改变了主意，卸载了 Wildfly 并改安装 Tomcat。所有从 Wildfly 安装中删除的文件仍然存在于镜像中，尽管它们已被删除。镜像大小会迅速增长。

理解 Docker 的分层文件系统会对你的镜像大小产生巨大影响。当你将镜像发布到注册表时，大小可能会变成问题；它需要更多请求且传输时间更长。

例如，当需要在集群中部署成千上万个容器时，大镜像就会成为一个问题。你应该始终意识到层的累加性，并尝试在 Dockerfile 的每一步中优化镜像，就像使用命令链（command chaining）一样。我们稍后在创建 Java 应用镜像时将使用命令链技术。

由于层是累加的，它们提供了特定镜像是如何构建的完整历史。这带带了你另一个很棒的功能：回滚到镜像历史中某个点的可能性。由于每个镜像都包含了其所有的构建步骤，如果我们需要，可以很容易地返回之前的步骤。这可以通过标记（tagging）某个层来实现。我们将在书的后面部分介绍镜像标记。

层和镜像彼此紧密相关。正如我们之前所说的，Docker 镜像存储为一系列只读层。这意味着一旦容器镜像被创建，它就不会改变。

但如果所有文件系统都设为只读，将毫无意义。那么修改镜像呢？或者将你的软件添加到基础 Web 服务器镜像中？嗯，当我们启动一个容器时，Docker 实际上会获取只读镜像（带有其所有的只读层），并在层栈的顶部添加一个可写层。现在让我们关注容器。

# 容器（Containers）

镜像的运行实例被称为容器。Docker 使用 Docker 镜像作为只读模板来启动它们。如果你启动一个镜像，你就拥有该镜像的运行容器。自然地，你可以拥有许多相同镜像的运行容器。事实上，稍后在学习 Kubernetes 时，我们将会经常这样做。

要运行一个容器，我们使用 `docker run` 命令：

```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

有很多 `run` 命令的选项和开关可以使用；我们稍后会了解它们。某些选项包括网络配置，例如（我们将在第 2 章，`网络与持久化存储`）中解释 Docker 的网络概念）。

其他的与 `-it`（来自 interactive，交互式）相同的选项告诉 Docker 引擎以不同的方式运行；在这种情况下，让容器具有交互性，并将其输出和输入附加到终端上。让我们只关注容器的概念，以便更好地理解大局。我们稍后将使用 `docker run` 命令来测试我们的设置。

那么，当我们运行 `docker run` 命令时，底层发生了什么？Docker 将检查你想要运行的镜像是否在本地机器上可用。如果没有，它将从远程（remote）仓库拉取。

Docker 引擎获取镜像，并在镜像层栈顶部添加一个可写层。接下来，它初始化镜像的名称、ID 和资源限制（如 CPU 和内存）。在这一阶段，Docker 还将通过从池中查找并附加可用 IP 地址来设置容器的 IP 地址。

执行的最后一步是实际命令，它作为 `docker run` 命令的最后一个参数传递。如果使用了 `it` 选项，Docker 将捕获并提供容器输出，它将显示在控制台上。

你现在可以执行通常在准备操作系统运行你的应用程序时会做的事情。这包括安装软件包（例如通过 `apt-get`）、使用 Git 拉取源代码、使用 Maven 构建你的 Java 应用等。所有这些操作都将修改顶部可写层中的文件系统。

如果你执行 `commit` 命令，将创建一个包含你所有更改的新镜像，它就像是被“冻结”了一样，并准备好在稍后运行。要停止容器，使用 `docker stop` 命令：

```
docker stop
```

容器停止后将保留所有的设置和文件系统更改（在顶部的可写层中）。容器中运行的所有进程都将停止，你将丢失内存中的所有内容。这就是停止的容器与 Docker 镜像的区别。

要列出系统中所有的容器（无论运行中还是停止的），执行 `docker ps` 命令：

```
docker ps -a
```

结果 Docker 客户端将列出一个表格，包含容器 ID（你可以在其他命令中引用容器的唯一标识符）、创建日期、启动容器使用的命令、状态、暴露端口和名称（由你分配或 Docker 为你选的趣味名称）。

要删除容器，你可以直接使用 `docker rm` 命令。如果你想一次删除几个，可以使用容器列表（由 `docker ps` 命令提供）和过滤器：

```
docker rm $(docker ps -a -q -f status=exited)
```

我们说过 Docker 镜像总是只读且不可变的。如果它没有更改镜像的可能性，它将非常没用。那么，除了修改 Dockerfile 并重新构建之外，镜像修改是如何可能的呢？

当容器启动时，层栈顶部的可写层供我们使用。我们实际上可以对运行容器进行更改；这可以是添加或修改文件，例如安装软件包、配置操作系统等。

如果你在运行容器中修改文件，该文件将从底层（父级）只读层取出并放置在顶部可写层中。我们的更改仅在顶部层中可行。联合文件系统将覆盖底层文件。原始的底层文件不会被修改；它仍然安全地存在于底层只读层中。

通过发布 `docker commit` 命令，你从运行容器创建一个新的只读镜像（以及其中所有的更改）：

```
docker commit <container-id> <image-name>
```

`docker commit` 命令保存了你对容器所做的所有更改。为了避免数据损坏或不一致，Docker 将暂停你正在提交更改的容器。`docker commit` 命令的结果是一个全新的只读镜像，你可以从它创建新的容器：

![](img/Image00006.jpg)

在成功执行 `commit` 后，Docker 将输出新生成镜像的完整 ID。如果你在没有先发布 `commit` 的情况下删除了容器，然后重新启动相同的镜像，Docker 将启动一个全新的容器，其中不会包含之前运行容器中所做的任何更改。

无论是否执行了 `commit`，你对文件系统的更改都不会影响基础镜像。通过修改容器中的顶层可写层来创建镜像在调试和实验时非常有用，但通常最好使用 Dockerfile 以一种文档化且易于维护的方式管理你的镜像。

我们现在已经学习了容器化世界中的构建（Dockerfile 和镜像）和运行（容器）部分。我们仍然缺少最后一个元素：分发组件。Docker 的分发组件由 Docker registry（注册库）、index（索引）和 repository（仓库）组成。让我们现在关注它们，获得一个完整的图景。

# Docker registry、repository 和 index

Docker 分发系统的第一个组件是 registry。Docker 利用分级系统来存储镜像，如下截图所示：

![](img/Image00007.jpg)

你构建的镜像可以存储在 `remote` registry 中供他人使用。`Docker` registry 是一个服务（实际上是一个应用程序），用于存储你的 Docker 镜像。Docker Hub 是可用 registry 的示例；它是免费的，并服务于巨大且不断增长的现有镜像集合。

另一方面，repository 是相关镜像的集合（命名空间），通常提供同一个应用程序或服务的不同版本。它是具有相同名称和不同标签的不同 Docker 镜像的集合。

如果你的应用命名为 `hello-world-java`，且你用于 Registry 的用户名（或命名空间）为 `dockerJavaDeveloper`，那么你的镜像将被放置在 `dockerJavaDeveloper/hello-world-java` 仓库中。

你可以为镜像打标签，并在单个命名仓库中存储具有不同 ID 的多个版本镜像，并使用如 `username/image_name:tag` 的特殊语法访问镜像的不同标签版本。

`Docker` repository 与 Git 仓库非常相似。例如，类似于 `Git`，`Docker` 仓库通过 URI 识别，可以是公开的也可以是私有的。URI 的格式如下所示：

```
{registryAddress}/{namespace}/{repositoryName}:{tag}
```

Docker Hub 是默认的 registry，如果你不指定 registry 地址，Docker 将从 Docker Hub 拉取镜像。若要在 registry 中搜索镜像，请执行 `docker search` 命令；例如：

```
$ docker search hello-java-world
```

在不指定 `remote` registry 的情况下，Docker 将在 Docker Hub 上搜索并输出符合搜索标准的镜像列表：

![](img/Image00008.jpg)

起初 registry 和 repository 之间的区别可能会让人困惑，让我们描述执行以下命令时会发生什么：

```
$ docker pull ubuntu:16.04
```

该命令从 Docker Hub registry 下载 `ubuntu` 仓库中标签为 `16.04` 的镜像。官方的 `ubuntu` 仓库不使用用户名，因此在此示例中省略了命名空间部分。

尽管 Docker Hub 是公开的，但你可以通过你的 Docker Hub 用户账户免费获得一个私有仓库。

最后，同样重要的一点是你应该注意的组件是 index。index 管理搜索、打标签以及用户账户和权限。事实上，registry 将身份验证委托给 index。

在执行如 `push` 或 `pull` 等远程命令时，index 首先查看镜像的名称，然后检查是否有相应的仓库。如果是，index 将验证你是否允许访问或修改该镜像。如果是，操作将获得批准，并由 registry 接收或发送镜像。

让我们总结一下目前为止学到的：

- Dockerfile 是构建镜像的配方。它是一个包含有序指令的文本文件。每个 Dockerfile 都有一个你在此基础上构建的基础。
- 镜像是文件系统的特定状态：运行中容器只读、冻结且不可变的快照。
- 镜像由层组成，代表文件系统在不同时间点的更改；层类似于 Git 仓库的 commit 历史。Docker 使用层缓存。
- 容器是镜像的运行实例。它们可以是运行状态或停止状态。你可以运行多个相同镜像的容器。
- 你可以对容器的文件系统进行更改并对其进行 `commit` 以使其持久化。
- 只有文件系统的更改可以 `commit`，内存更改将丢失。
- registry 持有一个命名仓库的集合，而仓库本身又是由其 ID 跟踪的镜像集合。registry 与 Git 仓库相同：你可以 `push` 和 `pull` 镜像。

你现在应该理解了镜像及其层和容器的本质。但 Docker 不仅仅是一个 Dockerfile 处理器和运行引擎。让我们看看还有哪些可用工具。

# Additional tools

它是一个完整的软件包，包含了广泛的工具和 API，这些工具对开发者和 DevOps 的日常工作非常有帮助。例如，有一个 Kinematic，这是一个用于在 Windows 和 macOS X 上使用 Docker 的桌面开发者环境。

从 Java 开发者的角度来看，有很多可用工具，这些工具在程序员的日常工作中特别有用，例如 IntelliJ IDEA Docker 集成插件（我们将在接下来的章节中大量使用此插件）。Eclipse 粉丝可以使用适用于 Eclipse 的 Docker 工具，该工具从 Eclipse Mars 版本开始提供。NetBeans 也支持 Docker 命令。

无论你选择哪种开发环境，这些插件都能让你直接从喜爱的 IDE 中下载和构建 Docker 镜像、创建并启动容器，以及执行其他相关任务。

Docker 现在如此流行，难怪有数百种第三方工具被开发出来以使 Docker 更加实用。其中最著名的是 Kubernetes，我们将在书中重点关注它。但 Kubernetes 之外，还有许多其他工具。

它们将支持与 Docker 相关的操作，例如持续集成/持续交付、部署和基础设施或镜像优化。数十个托管服务现在都支持运行和管理 Docker 容器。

随着 Docker 受到越来越多的关注，几乎每个月都有与 Docker 相关的工具涌现。你可以在 GitHub 的 awesome Docker 列表中找到一个非常精良的 Docker 相关工具和服务列表，地址为：https://github.com/veggiemonk/awesome-docker。

但可用的不仅仅是工具。此外，Docker 还提供了一系列非常实用的 API。其中之一用于管理镜像和容器的远程 API。使用此 API，你能够将镜像分发到运行时 Docker 引擎中。

还有 Stats API，它可以暴露容器的实时资源使用信息（如 CPU、内存、网络 I/O 和块磁盘 I/O）。该 API 端点可用于创建工具来展示你容器的运行情况；例如在生产系统中。

既然我们现在已经了解了 Docker 背后的理念、虚拟化与容器化的区别，以及使用 Docker 的益处，让我们开始采取行动吧。我们将首先安装 Docker。

# 安装 Docker

在本节中，我们将介绍如何在 Windows、macOS 和 Linux 操作系统上安装 Docker。接下来，我们将运行一个示例 `hello-world` 镜像来验证安装，并检查在安装完成后一切是否都运行正常。

Docker 的安装非常简单，但有一些点你需要关注以确保其运行顺畅。我们将指出这些点，以使安装过程变得轻松。

你应该知道，Linux 是 Docker 的原生环境。如果你运行容器，它将在 Linux 内核上运行。如果你在运行于 Linux 的 Docker 上运行容器，它将使用你自己机器的内核。

在 macOS 和 Windows 上情况并非如此；这就是为什么如果你要在这些操作系统上运行 Docker 容器，就需要对 Linux 内核进行虚拟化。

Docker 引擎在 macOS 或 MS Windows 上运行时，将使用专门为运行 Docker 容器设计的轻量级 Linux 发行版。它完全从内存中运行，仅占用几兆内存，并在几秒内启动。

在 macOS 和 Windows 上安装主 Docker 软件包后，将默认使用操作系统内置的虚拟化引擎。因此，对你的机器有一些特殊要求。

对于最新的原生 Docker 设置（它深度集成到操作系统内置的原生虚拟化引擎中），你需要 64 位的 Windows 10 专业版或企业版。

对于 macOS，最新的 Docker for Mac 是一个从零开发的原生 Mac 应用程序，具有原生用户界面，并与 OS X 原生虚拟化、虚拟机管理程序框架、网络和文件系统集成。强制性要求是 Yosemite 10.1。

# 在 macOS 上安装

要获取 Docker macOS，只需将 `Docker.app` 移动到你的 `Applications`（应用程序）文件夹中即可。如果你运行 Docker，它将以鲸鱼图标的形式出现在 macOS 菜单栏中。图标在启动过程中会播放动画并在完成后恢复稳定：

![](img/Image0000.jpg)

如果你现在点击图标，它将为你提供一个实用的菜单，显示 Docker 状态和其他额外选项：

![](img/Image0001.jpg)

Docker for Mac 具有自动更新功能，这对于保持安装版本最新非常有帮助。第一个 Preferences...（设置）面板提供了自动检查更新的可能性；默认是勾选的：

![](img/Image0002.jpg)



如果你是一个勇敢的人，也可以切换到 beta 通道（测试版）来获取更新。这样你始终可以获得最新强大的 Docker 特性，但带有稳定性下降的风险，这也是测试软件的常态。另外注意，切换到 beta 通道将卸载你当前的稳定版 Docker 并破坏你所有的设置和容器。Docker 会对此发出警告，以确保你真的想这样做：

![](img/Image0003.jpg)

`Preferences ...` 中的 `File Sharing`（文件共享）面板将提供一个选项，用于标记机器上的 macOS 目录，挂载到稍后运行的 Docker 容器中。我们将在书中后面详细解释挂载目录。目前，让我们保持默认的选中目录集即可：

![](img/Image0004.jpg)

`Advanced`（高级）面板具有一些调整可供 Docker 使用的计算机资源的选项，包括处理器数量和内存大小。如果你从以下设备开始使用 Docker，默认设置通常是一个不错的起点：

![](img/Image0005.jpg)

`Proxies`（代理）面板提供了设置代理的可能性，如果你的机器上需要它的话。你可以选择使用系统设置或手动设置，如下截图所示：

![](img/Image0006.jpg)

在下一页，你可以编辑一些 Docker 进程设置。这包括添加注册仓库和镜像仓库。Docker 在拉取镜像时将使用它们。`Advanced` 标签包含一个文本字段，你可以在其中输入包含进程配置的 JSON 文本：

![](img/Image0007.jpg)

## 介绍

- 电子搜索
- 书下载
- 学习分享

## 网站：

- 电子搜索
- 书下载
- 学习分享

## 德猫

- 电子搜索
- 书下载
- 学习分享

## 网站：

- 电子搜索
- 书下载
- 学习分享

- 在 `Daemon` 面板中，你也可以关闭 `Docker Experimental features`。长期以来，`Experimental features` 默认都是开启的。每隔一段时间，新版本的 `Docker` 就会带来新的 `Experimental features`。在编写本书时，它们将包含，例如：`Checkpoint & Restore`（一个允许通过创建检查点来冻结运行中容器的功能）、`Docker graph driver plugins`（用于使用外部/进程外图形驱动程序供 `Docker` 引擎使用，作为内置存储驱动程序的替代方案）以及其他。查看 `Docker` 新版本包含哪些新功能总是很有趣的。点击 `Daemon` 页面上的链接将带你进入 GitHub 页面，该页面列出了解释了所有新的实验性功能。

- 最后一个 `Preferences...` 窗格是 `Reset`（重置）。如果你发现 `Docker` 无法启动或运行异常，可以尝试将 `Docker` 安装重置为出厂默认：

![](img/Image00017.jpg)

但需要提醒你，将 `Docker` 重置为出厂状态也将删除你机器上可能下载的所有镜像和容器。如果你有尚未推送到任何地方的镜像，先进行备份始终是个好主意。

`Docker` 菜单中的 `Open Kitematic` 是打开我们之前提到的 `Kitematic` 程序的方便快捷方式。它是一个在 Windows 和 Mac OS X 上使用 `Docker` 的桌面实用程序。如果你还没有安装 `Kitematic`，`Docker` 将为你提供一个带有安装包的链接：

![](img/Image00018.jpg)

- 如果你运行 `Kitematic`，它会首先向你展示 `Docker Hub` 登录界面。你现在可以注册 `Docker Hub`（`Sign up`），然后提供你的用户名和密码登录：

![](img/Image00019.jpg)

点击 `Skip For Now`（以后跳过）将让你不登录 `Docker Hub` 直接进入镜像列表。让我们通过拉取并运行镜像来测试我们的安装。如下截图所示，搜索 `hello-java-world`：

![](img/Image00020.jpg)

从注册库拉取镜像后，启动它。`Kitematic` 将展示运行中的容器日志，这将是来自容器化 Java 应用程序著名的 `hello world` 信息：

![](img/Image00021.jpg)

在 `Kitematic` 中运行容器就到这里。让我们尝试在 shell 中执行相同的操作。在终端中执行以下命令：

```bash
$ docker run milkyway/java-hello-world
```

结果，你将看到同样的问候，来自一个容器化的 Java 应用程序，这次是在 macOS 终端中：

![](img/Image00022.jpg)

好了，我们已经在 macOS 上启动并运行了原生的 `Docker`。让我们在 Linux 上也安装它。

# 在 Linux 上安装

世界上有很多不同的 Linux 发行版，安装过程对于每个 Linux 发行版可能略有不同。我将在最新的 16.04 Ubuntu 桌面版上安装 `Docker`：

1. 首先，我们需要允许 `apt` 软件包管理器通过 HTTPS 协议使用仓库。在 shell 中执行：

   ```bash
   $ sudo apt-get install -y --no-install-recommends apt-transport-https ca-certificates curl software-properties-common
   ```

2. 接下来我们要做的是将 `Docker` 的 `apt` 仓库 `gpg` 密钥添加到我们的 `apt` 源列表中：

   ```bash
   $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add –
   ```

3. 如果成功，响应将是简单的 `OK`。使用以下命令设置稳定仓库：

   ```bash
   $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   ```

4. 接下来，我们需要更新 `apt` 软件包索引：

   ```bash
   $ sudo apt-get update
   ```

5. 现在，我们需要确保 `apt` 安装程序将使用官方的 `Docker` 仓库而不是默认的 Ubuntu 仓库（后者可能包含旧版本的 `Docker`）：

   ```bash
   $ apt-cache policy docker-ce
   ```

6. 使用此命令安装最新版本的 `Docker`：

   ```bash
   $ sudo apt-get install -y docker-ce
   ```

7. `apt` 软件包管理器将下载许多软件包；这些是所需的依赖项以及 `docker-engine` 本身：

   ![](img/Image00023.jpg)

8. 好了，你应该准备就绪了。让我们验证一下 `Docker` 是否在我们的 Linux 节点工作：

   ```bash
   $ sudo docker run milkyway/java-hello-world
   ```

9. 如你所示，`Docker` 引擎将从 `Docker Hub` 拉取 `milkyway/java-hello-world` 镜像及其所有层，并返回问候：

   ![](img/Image00024.jpg)

但我们需要用 `sudo` 运行 `Docker` 命令吗？原因是 `Docker` 守护进程始终以 `root` 用户身份运行，并且从 `Docker` 0.5.2 版本开始，`Docker` 守护进程绑定到 Unix socket 而不是 TCP 端口。默认情况下，该 Unix socket 属于 `root` 用户，因此默认你可以通过 `sudo` 访问它。让我们修复它，以便能够作为普通用户运行 `Docker` 命令：

1. 首先，如果 `Docker` 组不存在，则添加它：

   ```bash
   $ sudo groupadd docker
   ```

2. 然后，将你自己的用户添加到 `Docker` 组。将用户名更改为你偏好的的用户：

   ```bash
   $ sudo gpasswd -a jarek docker
   ```

3. 重启 Docker 守护进程：

   ```bash
   $ sudo service restart
   ```

4. 现在让我们注销并重新登录，执行一次无需 `sudo` 的 `docker run` 命令。如你所见，你现在可以作为非 `root` 用户工作：

   ![](img/Image00025.jpg)

5. 好了。我们的 Linux 安装已准备好可以使用。

# 在 Windows 上安装

原生 Docker 软件包可以在 64 位的 Windows 专业版或企业版上运行。它使用 Windows 10 虚拟化引擎来虚拟化 Linux 内核。这就是为什么安装包不再包含像之前的 `Docker` 版本那样的 VirtualBox 设置。原生应用程序采用典型的 `.msi` 安装包。如果你运行它，它将用一条友好的消息问候你，说它将位于任务栏中，小鲸图标下方：

![](img/Image00026.jpg)

托盘上的 `Docker` 图标会告知 `Docker` 引擎的状态。它还包含一个小但实用的菜单：

![](img/Image00027.jpg)

让我们探索偏好设置看看哪些可用选项。第一个标签 `General` 允许设置 `Docker` 在登录时自动运行。如果你每天使用 `Docker`，这可能是建议的设置。你还可以标记自动检查更新并发送使用统计。发送使用统计将帮助 Docker 团队在未来版本中改进工具；除非你有某些关键的安全任务，否则我建议开启此选项。这是对这一伟大工具未来版本贡献的好方法：

![](img/Image00028.jpg)

第二个标签 `Shared Drives` 允许你选择 `Docker` 容器将使用的本地 Windows 硬盘：

![](img/Image00029.jpg)

我们将在第二章 网络与持久化存储]中介绍 Docker 数据卷。下一个设置页面 `Advanced` 允许我们对在 Windows PC 上的 `Docker` 引擎进行一些限制，并选择 Linux 内核虚拟机镜像的位置：

![](img/Image00030.jpg)

`Network` 允许你配置 `Docker` 与网络的方式，例如子网地址和掩码或 DNS 服务器。我们将在第二章 网络与持久化存储]中介绍 Docker 网络：

![](img/Image00031.jpg)

如果你所在的网络处于代理之后，并希望 Docker 能够访问互联网，你可以在 `Proxies` 标签页中设置代理配置：

![](img/Image00032.jpg)

该对话框与你在其他应用程序中看到的设置类似，在其中你可以定义代理设置。它可以接受不使用代理、系统代理设置或手动设置（为 HTTP 和 HTTPS 通信使用不同的代理）。下一个面板对于配置 Docker 守护进程非常有用：

![](img/Image00033.jpg)

`Basic` 关意味着 Docker 使用基本配置。你可以将其切换到 `Advanced` 并以 JSON 结构体的形式提供自定义设置。`Experimental`（实验性）功能与我们在 macOS 上安装 Docker 时已经提到的相同，这将是 `Checkpoint & Restore`（检查点与恢复）或启用 Docker 图形驱动插件等。你还可以指定一个远程仓库列表。Docker 将直接使用纯文本 HTTP 而非 HTTPS 从不安全的仓库中拉取镜像。

使用最后一个面板上的 `Reset` 选项可以让你重启 Docker 或将其重置为出厂设置：

![](img/Image00034.jpg)

但请注意，将 Docker 重置为初始设置也将删除机器上当前的所有镜像和容器。

`Open Kitematic...` 选项也出现在 Docker 栏图标右键菜单中，它是启动 Kitematic 的快速快捷方式。如果你第一次执行且没有安装 Kitematic，Docker 将询问你是否想先下载它：

![](img/Image00035.jpg)

Windows 版 Docker 安装就此结束。这是一个非常无痛的过程。作为安装过程的最后一步，让我们检查 Docker 是否可以从命令命令行运行，因为这可能是你未来启动它的方式。在命令提示符或 PowerShell 中执行以下命令：

```bash
docker run milkyway/java-hello-world
```

![](img/Image00036.jpg)

如你在上一个截图所示，我们收到了一条来自作为 Docker 容器启动的 Java 程序的 Hello World 消息。

### 总结

就是这样。我们的 Windows 版 Docker 安装已完全功能正常。在本章中，我们学习了 Docker 背后的理念以及传统虚拟化与容器化之间的主要区别。我们了解了许多 Docker 核心概念，如镜像、层、容器和仓库。我们应该已经在本地机器上安装了 Docker；现在是时候继续学习更高级的 Docker 特性，例如网络和持久存储了。

# 网络与持久存储

在上一章中，我们学习了许多 Docker 概念。我们知道容器是镜像的运行时。它将包含你的 Java 程序以及所有必要的依赖项，例如 JRE 或应用程序服务器。但在某些情况下，Java 程序是自给自足的。它始终与其他服务器（如数据库）通信，或者暴露给他人（如运行在应用服务器上的 Web ，它需要接受来自用户或其他应用程序的请求）。现在是描述如何向外部开放 Docker 容器的方法、网络和持久存储了。在本章中，你将学习如何配置网络、暴露和映射网络端口。通过这样做，你可以让你的 Java 程序与其他容器通信。想象以下场景：你可以有一个运行带有你 Java 程序的 Tomcat 应用程序服务器容器，与另一个运行数据库（例如 `PostgreSQL`）的容器通信。虽然 Kubernetes 的网络方法与 Docker 默认提供的有所不同，但现在让我们简要关注 Docker 本身。稍后我们将介绍 Kubernetes 特定的网络。容器与外部世界的通信不仅关乎网络；在本章中，我们还将关注数据卷，作为一种在容器运行和停止周期之间持久化数据的方法。

本章涵盖以下主题：

- Docker 网络类型
- 网络命令
- 创建网络
- 端口映射与暴露
- 卷命令
- 创建和删除卷

让我们从 Docker 网络开始。

# 网络

为了让你的容器能够与外部世界通信（无论是另一个服务器还是另一个 Docker 容器），Docker 提供了不同的网络配置方法。让我们从容器可用的网络类型开始。

# Docker 网络类型

Docker 开箱即用提供了不同的网络类型。要列出它们，请执行 `docker network ls` 命令：

```bash
$ docker network ls
```

Docker 将输出可用列表，包含唯一网络标识符、名称以及在背后支持它的驱动程序：

![](img/Image00037.jpg)

为了概览各种网络类型之间的差异，我们现在逐一描述它们。

# Bridge（桥接）

这是 Docker 的默认网络类型。当 Docker 服务守护进程启动时，它会配置一个名为 `docker0` 的虚拟桥接。如果你没有使用 `docker run -net=<NETWORK>` 选项指定网络，Docker 守护进程将默认将容器连接到桥接网络。此外，如果你创建一个新容器，它也将连接到桥接网络。对于 Docker 创建的每个容器，它都会分配一个虚拟以太网设备并附加到桥接上。使用 Linux 命名空间，虚拟以太网设备在容器中映射为 `eth0`，如下图所示：

![](img/Image00038.jpg)

`in-container eth0` 接口从桥接地址范围获得 IP 地址。换句话说，Docker 将从桥接可用范围内找到一个空闲 IP 地址，并用该 IP 地址配置容器的 `eth0` 接口。从现在起，如果新容器需要（例如连接互联网），它将使用桥接；即主机的 IP 地址。桥接会自动在任何连接到它的网络接口之间转发数据包，并允许容器与主机以及同一主机上的其他容器进行通信。桥接网络可能是最频繁使用的。

# Host（主机模式）

这种网络类型直接将容器放在主机的网络栈中。也就是说，主机上定义的所有网络接口容器都是可用的，如下图所示：

![](img/Image00039.jpg)

如果你使用 `-net=host` 选项启动容器，那么容器将使用主机网络。它将像普通网络一样快：没有桥接，没有转换，什么都没有。这就是为什么当你需要获得最佳网络性能时，它非常有用。与运行在桥接网络上的容器相比，运行在主机网络栈中的容器速度更快，不需要遍历 `docker0` 桥接和 `iptables` 端口映射。在主机模式下，容器共享主机的网络空间（例如你的本地机器），直接将其暴露给外部。通过使用 `-net=host` 命令开关，你的容器可以通过主机的 IP 地址访问。但是，你需要意识到这可能是危险的。如果你以 root 身份运行应用程序且存在某些漏洞，将面临安全风险，因为有人可以通过 Docker 容器远程控制主机网络。使用主机网络类型还意味着你需要使用端口映射来访问容器内部的服务。我们将在本章稍后部分介绍端口映射。

简单来说，`none` 网络完全没有配置网络。这种网络类型不使用任何驱动程序。当你不需要容器具备网络访问时，它非常有用；`docker run -net=none` 命令会完全禁用网络。

Docker 提供了一系列简短的命令来处理网络。你可以从 shell（Linux 或 macOS）或 Windows 的命令提示符和 PowerShell 中运行它们。让我们现在了解它们。

# 网络命令

在 Docker 中管理网络的父命令是 `docker network`。你可以使用 `docker network help` 命令列出整个命令集，如下截图所示：

![](img/Image00040.jpg)



若要获取特定命令每个选项的详细语法和描述，请对每个命令使用 `-help` 选项。例如，要获取 `docker network create` 可用参数的描述，请执行 `docker network create -help`。

让我们简要描述每个可用命令：

- `docker network ls`：这是我们之前一直在使用的命令，它只是列出容器可用的网络。它将输出网络标识符、名称、使用的驱动程序以及网络范围。
- `docker network create`：创建新网络。该命令的完整语法是 `docker network create [OPTIONS] NETWORK`。我们稍后会使用该命令。
- `docker network rm`：`dockercnetworkcrm` 命令简单地删除网络。
- `docker network connect`：将容器连接到特定网络。
- `docker network disconnect`：如名称所示，它会将容器从网络中断开。
- `docker network inspect`：`docker network inspect` 命令显示关于网络的详细信息。如果你遇到网络问题，它非常有用。我们现在将创建并检查我们的网络。

`docker network inspect inspect` 命令显示关于网络的详细信息。如果你遇到网络问题，它非常有用。我们现在将创建并检查我们的网络。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

## 创建并检查网络

让我们创建一个网络。我们将该网络命名为 `myNetwork`。在 shell 或命令行中执行以下命令：

```bash
$ docker network create myNetwork
```

这是该命令最简单的形式，但可能是使用最频繁的。它采用默认驱动程序（我们没有使用任何选项来指定驱动程序，将使用默认的 `bridge`）。作为输出，Docker 将打印出新创建网络的标识符：

![](img/Image00041.jpg)

你稍后将使用此标识符在将容器连接到该网络或检查网络属性时引用它。命令的最后一个参数是网络名称，这比 ID 方便且容易记忆。在我们的案例中，网络名称是 `myNetwork`。`docker network create` 命令接受更多参数，如下表所示：

|  | 描述 |
| :--- | :--- |
| `-d, -driver="bridge"` | 用于管理网络的驱动程序 |
| `-aux-address=map[]` | 网络驱动程序使用的辅助 IPv4 或 IPv6 地址 |
| `-gateway=[]` | 主子网的 IPv4 或 IPv6 网关 |
| `-ip-range=[]` | 从子范围分配容器 IP |
| `-ipam-driver=default` | IP 地址管理驱动程序 |
| `-o`, `-opt=map[]` | 设置驱动程序的特定选项 |
| `-subnet=[]` | 表示网络段的 CIDR 格式子网 |

最重要的参数之一是 `-d`（`--driver`）选项，默认值为 `bridge`。驱动程序允许你指定网络类型。记得 Docker 默认提供了几个驱动程序：`host`、`bridge` 和 `none`。

创建网络后，我们可以使用 `docker network inspect` 命令检查其属性。在 shell 或命令行执行以下操作：

```bash
$ docker network inspect myNetwork
```

作为响应，你将获得许多关于网络的详细信息。如截图所示，我们新创建的网络使用了 `bridge` 驱动程序，即使我们没有显式请求它：

![](img/Image00042.jpg)

如你所见，容器列表是空的，原因是我们还没有将任何容器连接到此网络。让我们现在就这样做。

## 将容器连接到网络

现在我们已经准备好了 `myNetwork`，可以运行 Docker 容器并将其附加到网络。要启动容器，我们将使用 `docker run --net=<NETWORK>` 选项，其中 `<NETWORK>` 是默认网络之一或你创建的网络名称。让我们以 Apache Tomcat 为例，它是 Java Servlet 和 JavaServer Pages 技术的开源实现：

```bash
docker run -it --net=myNetwork tomcat
```

这需要一些时间。Docker 引擎将从 Docker Hub 拉取所有 Tomcat 的镜像层，然后运行容器。还有另一种附加网络的选项，你可以告知 Docker 你想容器连接到哪个网络，使用 `container:` 前缀，如下例所示：

```bash
docker run -it --net=myNetwork tomcat own
```

在上一个示例中，我们使用 `bridge` 网络运行了 `myNetwork` 镜像。下一个命令将使用相同的网络运行 `myNetwork` 镜像，如下：

```bash
docker run -it --net=myNetwork tomcat
```

```bash
docker run -it --name myTomcat --net=myNetwork tomcat
```

为了检查同一网络上的容器是否可以通信，我们将使用另一个镜像，`busybox`。BusyBox 是一个在单个可执行文件中提供多个精简 Unix 工具的软件。让我们在单独的 shell 或命令提示符窗口中运行以下命令：

```bash
docker run -it --net container:myTomcat busybox
```

如你所见，我们已经指示 Docker 想要让 `busybox` 容器使用与 Tomcat 相同的网络。作为替代方案，我们当然也可以通过 `--net myNetwork` 选项来显式地指定网络名称。

让我们检查它们是否真的可以通信。在运行着 `busybox` 的 shell 窗口中执行以下命令：

```bash
$ wget localhost:8080
```

上一个指令将在 `8080` 端口上执行 `HTTP GET` 请求，而 Tomcat 正在另一个容器中监听该端口。在成功下载 Tomcat 的 `index.html` 之后，我们就有证明，两个容器都是可以通信的：

![](img/Image00044.jpg)

到目前为止良好，运行在同一宿主机和同一网络上的容器可以相互通信。但从外部与我们的容器通信呢？端口映射（Mapping ports）派上了用场。我们可以将 Docker 容器暴露的端口映射到宿主机的端口，在我们的情况下这就是 localhost。通用思路是，我们希望宿主机上的端口映射到运行容器中的特定端口，相当于 Tomcat 容器的 `8080` 端口。

要从宿主机将端口（或一组端口）绑定到容器，我们使用 `docker run` 命令的 `-p` 标志，如下例：

```bash
$ docker run -it --name myTomcat2 --net=myNetwork -p 8080:8080 tomcat
```

上一个命令运行了另一个 Tomcat 实例，它也连接到 `myNetwork` 网络。然而，这次我们将容器的 `8080` 端口映射到宿主机相同的数字端口。`-p` 选项的语法非常直观：你只需要输入主机端口号、一个冒号，然后是你想要映射的容器内的端口号：

```bash
$ docker run -p <hostPort>:<containerPort> <image ID or name>
```

Docker 镜像可以使用 Dockerfile 中的 `EXPOSE` 指令（例如 `EXPOSE 7000-8000`）或 `docker run` 命令（例如所示）向其他容器暴露整个范围的端口：

```bash
$ docker run --expose=7000-8000 <container ID or name>
```

然后，你可以使用 `docker run` 命令从宿主机到容器映射整个范围的端口：

```bash
$ docker run -p 7000-8000:7000-8000 <container ID or name>
```

让我们验证一下是否可以从 Docker 外部访问 Tomcat 容器。为了做到这一点，让我们在映射端口的情况下运行 Tomcat：

```bash
$ docker run -it --name myTomcat2 --net=myNetwork -p 8080:8080 tomcat
```

然后，我们只需要在喜爱的浏览器中输入以下地址：`http://localhost:8080`。

结果，我们可以看到 Tomcat 的默认欢迎页面，它直接从运行中的 Docker 容器提供服务，如下屏所示：

![](img/Image00045.jpg)

很好，我们可以从 Docker 外部与我们的容器通信。顺便说一下，我们现在宿主机上运行着两个隔离的 Tomcat，而没有任何端口冲突、资源冲突等。这就是容器化的力量。

你可能会问，暴露（exposing）和映射（mapping）端口之间的区别是什么，即 `--expose` 切换和 `-p` 参数的区别？嗯，`--expose` 将运行时暴露端口，但不会创建到主机的任何映射。暴露的端口仅对运行在同一网络、同一 Docker 宿主机上的另一个容器可用。而 `-p` 选项等同于 `publish`：它会创建一个端口映射规则，将容器上的端口映射到宿主机系统的端口。映射的端口从 Docker 外部可用。请注意，如果你使用了 `-p` 但 Dockerfile 中没有 `EXPOSE`，Docker 将会执行一个隐式的 `EXPOSE`。这是因为，如果一个端口对公众开放，它也会自动对其他 Docker 容器开放。

在 Dockerfile 中无法创建端口映射。映射一个或多个端口仅仅是一个运行时选项。这是因为端口映射配置依赖于宿主机。Dockerfile 需要与宿主机无关且具有可移植性。

你只能在运行时使用 `-p` 绑定端口。

还有一个选项，它允许在容器启动期间自动一次性映射镜像中（即 Dockerfile 中）暴露的所有端口。`-P` 切换（这次是大写的 `P`）会将动态分配的随机宿主机端口映射到 Dockerfile 中通过 `EXPOSE` 指令暴露的所有容器端口。

在映射端口时，`-p` 选项比 `-P` 给你提供更多控制。Docker 不会自动选取任何随机端口；宿主机上的哪些端口应该被映射，取决于你。

如果你运行以下命令，Docker 将宿主机上的随机端口映射到 Tomcat 的 `8080` 端口：

```bash
$ docker run -it --name myTomcat --net=myNetwork -P
```

要检查具体映射了哪些端口，可以使用 `docker ps` 命令。在独立的 shell 中执行：

```bash
$ docker ps
```

在输出中，Docker 将列出运行的容器，并在 `PORTS` 列显示映射的端口：

![](img/Image00046.jpg)

如之前的屏幕所示，`myTom3` 将 `8080` 端口映射到了 `3272`。再次，对 `http://localhost:3272` 执行 `HTTP GET` 方法将我们的欢迎页面。`docker ps` 命令的替代方案是 `docker port` 命令，配合容器 ID 或名称使用（这将提供有关映射端口的信息）。在我们的情况下，这是：

```bash
$ docker port myTom3
```

结果，Docker 将输出映射关系，说明容器的 `8080` 端口映射到了主机的 `3272` 端口：

![](img/Image00047.jpg)

所有映射的信息也可以在 `docker inspect` 命令的结果中获得。例如执行以下命令：

```bash
$ docker inspect myTom2
```

在 `docker inspect` 命令的输出中，你会发现 `Ports` 部分包含以下信息：

![](img/Image00048.jpg)

让我们用表格简单总结一下与暴露和映射相关的选项：

| 指令 | 含义 |
| :--- | :--- |
| `EXPOSE` | 明确指定端口上有可用服务。用于 Dockerfile，并使暴露的端口对其他容器开放。 |
| `--expose` | 等同于 `EXPOSE`，但用于运行时，在容器启动期间。 |
| `-p hostPort:containerPort` | 指定端口映射规则，将容器上的端口映射到宿主机系统的端口。使端口从 Docker 外部开放。 |
| `-P` | 将动态分配的随机宿主机端口（或端口）映射到使用 `EXPOSE` 或 `--expose` 暴露的所有端口。 |

端口映射是一个非常棒的功能。它提供了灵活的配置可能性，让你的容器开放到外部世界。事实上，如果你希望你的容器化 Web 服务器、数据库或消息服务器能够与其他通信，这个功能是不可或缺的。如果默认的网络驱动程序不够用，你始终可以尝试在互联网上寻找特定的驱动程序或自己开发一个。Docker Engine 网络插件扩展了 Docker，以支持广泛的网络技术，例如 `IPVLAN`、`MACVLAN` 或其他完全不同且奇特的技术。Docker 中的网络可能性几乎是无尽的。现在，让我们关注 Docker 容器扩展性的另一个非常重要的方面：卷。

## 持久化存储

正如你在第 1 章 *Docker 简介*中所记忆的那样，Docker 容器文件系统默认情况下是临时的。如果你启动一个 Docker 镜像（即运行容器），你将在层级堆栈之上获得一个读写层。你可以随所欲地创建、修改和删除文件；如果你将更改提交回镜像，它们将变为持久化。如果你想在镜像中创建应用程序的完整设置以及所有环境，这是一个非常棒的功能。但在存储和检索数据时，这并不十分方便。最好的选择是将容器生命周期和你的应用程序与数据分离。理想情况下，你可能希望保持这些分离，这样你的应用程序生成（或正在使用）的数据就不会被破坏或绑定到容器的生命周期，从而可以重复使用。

一个完美的例子是 Web 应用程序服务器：Docker 镜像包含了 Web 服务器软件（例如 Tomcat），并部署、配置了你的 Java 应用程序，准备好就绪。但服务器将使用的数据应该与镜像分离。这是通过卷（volumes）实现的，我们将在本章的这关注卷。卷不是联合文件系统的一部分，因此写入操作是瞬时的且尽可能快速，不需要提交任何更改。

卷位于联合文件系统之外，作为宿主机文件系统上的普通目录和文件存在。

Docker 数据卷有三个主要的用例：

- 在宿主机文件系统和 Docker 容器之间共享数据
- 在容器被删除时保留数据
- 与其它 Docker 容器共享数据

让我们从列出可用的卷相关命令开始。

## 卷相关命令

卷相关命令的基础是 `docker volume`。命令如下：

- `docker volume create`：创建卷
- `docker volume inspect`：显示一个或多个卷的详细信息
- `docker volume ls`：列出卷
- `docker volume rm`：删除一个或多个卷
- `docker volume prune`：删除所有未使用的卷，即所有不再映射到任何容器的卷

与网络相关命令类似，如果你在执行命令时使用 `-help` 开关，可以获取每个命令的详细说明和所有可能的选项，例如：`docker volume create -help`。让我们从创建一个卷开始。

## 创建卷

正如你在第 1 章 *Docker 简介*中所记忆的那样，Docker for Windows 或 Docker for Mac 中有一个设置屏幕，允许我们指定 Docker 可以访问哪些驱动器。首先，让我们在我们的 Docker for Windows 中标记 `D` 驱动器，以便 Docker 容器可以使用：

![](img/Image00049.jpg)

为了我们的卷示例，我在我的 `D` 盘上创建了一个 `docker_volumes/volume1` 目录，并在里面创建了一个空的 `data.txt` 文件：

![](img/Image00050.jpg)

创建卷有两种方法。第一种是在运行镜像时指定 `-v` 选项。让我们运行我们已知的 `busybox` 镜像，并为我们的数据创建一个卷：

```bash
$ docker run -v d:/docker_volumes/volume1:/volume -it busybox
```

在上一个命令中，我们使用 `-v` 开关创建了一个卷，并指令 Docker 将 `host` 目录 `d:/docker_volumes/volume1` 映射到运行容器中的 `/volume` 目录。如果我们现在列出运行中的 `busybox` 容器中 `/volume` 目录的内容，我们可以看到我们的空 `data1.txt` 文件，如下截图所示：

![](img/Image00051.jpg)

`-v` 选项中的参数是宿主机上的目录（在这种情况下是你自己的操作系统，在我们的示例中是 `d:/docker_volumes/volume1`）、一个冒号，以及它在容器中可用的路径（我们的示例中是 `/volume`）。创建的卷是一种映射目录。它将对容器可用，也可以从宿主机操作系统访问。映射目录中已存在的任何文件（宿主机的 `d:/docker_volumes/volume1`）将在容器内部可用；它们在映射期间不会被删除。

`-v` 选项不仅可以用于目录，还可以用于单个文件。如果你想在容器中可以使用配置文件，这将非常有用。关于此点的最佳示例是 Docker 官方文档中的示例：



```
$ docker run -it -v ~/.bash_history:/root/.bash_history ubuntu
```

执行上一个命令将让你在本地机器和运行的容器之间拥有相同的 bash 历史。最棒的是，如果你退出容器，本地机器上的 bash 历史将包含你在容器内部执行的命令。从宿主机映射单个文件允许你暴露你的配置。对于开发者来说，映射单个文件在调试或尝试你的应用程序时可能非常有用。

除了在启动容器时创建卷之外，还有一个命令可以在启动容器之前创建一个卷。我们现在将使用它。

创建无名卷的最简单形式将是：

```
$ docker volume create
```

作为输出，Docker 将给你一个卷标识符，你稍后可以引用该卷。最好给卷起一个有意义的名字。要创建一个独立的命名卷，请执行以下命令：

```
$ docker volume create --name myVolume
```

要列出我们现在拥有的卷，请执行`docker volume ls`命令：

```
$ docker volume ls
```

输出将是我们到目前创建的卷列表：

![](img/Image00052.jpg)

通过这种方式创建的卷不会显式映射宿主机上的路径。如果容器的基础镜像在指定的挂载点包含数据（作为 Docker 处理的结果），这些数据将在卷初始化时复制到新卷中。这与显式指定`host`目录不同。其后的理念是在创建镜像时，你不应该关心卷在宿主机系统上的位置，使镜像可以在不同主机之间迁移。让我们再次运行另一个容器并将命名卷映射到它：

```
$ docker run -it -v myVolume:/volume --name myBusybox3 busybox
```

注意，这次我们没有指定宿主机上的路径。相反，我们指令 Docker 使用我们在上一步创建的命名卷。命名卷将在容器的`/volume`路径可用。让我们在卷上创建一个文本文件：

![](img/Image00053.jpg)

如果我们现在运行另一个容器并指定相同的命名卷，我们将能够访问之前创建的`myBusybox3`容器中可用的数据：

```
$ docker run -it -v myVolume:/volume --name myBusybox4 busybox
```

我们的两个容器现在共享同一个卷，如下截图所示：

![](img/Image00054.jpg)

Docker 命名卷（named volumes）是实现容器之间共享卷的一种简单方式。它们也是过去 Docker 早期常用的“纯数据容器”（data-only containers）的绝佳替代方案。现在已经不同了——命名卷要好得多。值得注意的是，每个容器并不限于只能使用一个卷，否则将是一个严重的限制。

你可以多次使用`-v`参数来挂载多个数据卷。

在容器之间共享卷的另一种选项是`-volumes-from`开关。如果你的其中一个容器已经挂载了卷，通过此选项，我们可以指示 Docker 使用其他容器中映射的卷，而不是提供卷的名称。考虑这个示例：

```
$ docker run -it -volumes-from myBusybox4 --name myBusybox5 busybox
```

以后这种方式运行`myBusybox5`容器，如果你再次进入运行中的`myBusybox5`容器的`/volume`目录，你将看到相同的`data.txt`文件。

`docker volume ls`命令可以接受一些过滤参数，这非常有用。例如，你可以列出没有被任何容器使用的卷：

```
docker volume ls -f dangling=true
```

不再被任何容器使用的卷可以使用`docker volumes prune`命令轻松删除：

```
docker volume prune
```

要列出使用特定驱动程序（driver）创建的卷（我们稍后会介绍驱动程序），你可以使用驱动过滤器对列表进行过滤，如下例：

```
docker volume ls -f driver=local
```

最后但同样重要的是，创建卷的另一种方法是 Dockerfile 中的`VOLUME CREATE`指令。我们稍后将在书中从 Dockerfile 创建镜像时使用它。使用`VOLUME CREATE`指令创建卷与在容器启动时使用`-v`选项相比，有一个非常重要的区别：在使用`VOLUME CREATE`时，无法指定`host`（主机）目录。这类比于暴露和映射端口。你不能在 Dockerfile 中映射端口。Dockerfile 的设计目的是可移植、可共享且独立于主机的。`host`目录是 100% 依赖主机的，在任何其他机器上都会失效，这略微偏离了 Docker 的设计理念。因此，在 Dockerfile 中只能使用可移植的指令。

如果你在创建卷时需要指定`host`目录，你需要在运行时指定它。

## 删除卷

与创建卷一样，在 Docker 中删除卷有两种方法。首先，你可以引用容器名称并执行`docker rm -v`命令来删除卷：

```
$ docker rm -v <containerName or ID>
```

在不提供`-v`选项的情况下删除容器时，Docker 不会警告你删除它的卷。结果，你将拥有“悬空”（dangling）的卷——即不再被任何容器引用的卷。如你记得，它们可以使用`docker volume prune`命令轻松删掉。

删除卷的另一种选项是使用`docker volume rm`命令：

```
$ docker volume rm <volumeName or ID>
```

如果该卷恰好被容器使用，Docker Engine 将不允许你删除它，并给你一条警告消息：

![](img/Image00055.jpg)

如你所见，在 Docker 中创建、共享和删除卷并不复杂。它非常灵活，允许你为应用程序创建所需的设置。但这种灵活性还有更多内容。在创建卷时，你可以指定`--driver`选项（简写`-d`），如果你需要映射某些外部的、非标准的存储，这可能很有用。我们目前创建的卷都是使用本地文件系统驱动程序的（文件存储在宿主系统的本地驱动上）；当你使用`volume inspect`命令检查卷时可以看到驱动程序的名称。不过还有其他选项——让我们现在来看看它们。

## 卷驱动程序 (Volume drivers)

与网络驱动插件一样，卷插件扩展了 Docker 引擎的能力，并实现了与其他类型的存储集成。互联网上有大量免费的可用插件；你可以在 Docker 的 GitHub 页面找到列表。其中一些包括：

- **Azure 文件存储 Docker 卷驱动程序 (Docker volume driver for Azure file storage)**：这是一个 Docker 卷驱动程序，使用 Azure 文件存储将云端文件共享挂载到 Docker 容器卷。它利用 Azure 文件存储的网络文件共享（SMB/CIFS 协议）功能。你可以创建可以从一个主机无缝迁移到另一个主机的容器，或者在运行不同主机的多个容器之间共享卷。

- **IPFS**：开源卷插件，允许将 IPFS 文件系统作为卷。IPFS 是一个非常有趣且充满前景的存储系统；它使得高效分发海量数据成为可能。它提供了去重、高性能和集群持久化，提供了安全的 P2P 内容交付、快速性能和去中心化存档。IPFS 提供了对数据的弹性访问，不受低延迟或骨干网络连接的影响。

- **Keywhiz**：你可以使用此驱动程序让你的容器与远程 Keywhiz 服务器通信。Keywhiz 是一个用于管理和分发秘密数据的系统，例如 TLS 证书/密钥、GPG 密钥、API 令牌和数据库凭据。与其将这些数据放在配置文件中或拷贝（这类似于会导致泄露或难以追踪），Keywhiz 让其管理更加简单和安全：集群中的 Keywhiz 服务器在数据库中中心化存储加密的密钥。客户端使用双向认证 TLS（`mTLS`）获取它们有权访问的密钥。

正如你从之前的示例中看到的，它们非常有趣，有时甚至奇特。由于 Docker 的可扩展性，你可以创建非常灵活的设置。但第三方驱动程序并不总是引入全新的存储类型；它们有时只是扩展现有驱动。一个例子可以是 Local Persist 插件，它通过允许在主机任何位置指定挂载点来扩展默认驱动的功能，即使通过`docker volume rm`命令删除卷，文件依然存在。

如果你需要一个尚未提供的卷插件，可以自己编写。该过程在 Docker 的 GitHub 页面上有很好的文档说明，并附带扩展示例。

我们现在涵盖了如何将容器开放给外部世界。我们可以使用网络和挂载卷来实现容器与其他主机之间的数据共享。让我们总结一下到本章为止我们学到的内容：

- 我们可以使用网络插件进一步扩展网络数据交换

- 卷持久化数据，即使容器重启也是如此

- 对卷文件的修改是直接进行的，但在更新镜像时不会包含

- 即使容器本身被删除，数据卷仍然存在

- 卷允许主机文件系统与 Docker 容器之间或其他容器之间共享数据

- 我们可以使用卷驱动程序进一步扩展文件交换

### 总结

在本章中，我们学习了 Docker 网络和存储卷功能。我们了解如何区分不同的网络类型，如何创建网络以及暴露和映射网络端口。

我们已经过过卷相关的命令，现在可以创建或删除卷。在第 3 章《处理微服务》中，我们将专注于使用 Docker 和 Kubernetes 部署的软件。

在读完前两个章节后，你现在应该对 Docker 架构及其概念有了了解。在我们继续后续 Java、Docker 和 Kubernetes 旅程之前，让我们先了解微服务的概念。

通过阅读这一章，你会发现为什么向微服务和云开发转型是必要的，以及为什么单体架构不再是一个选择。微服务架构也是 Docker 和 Kubernetes 发挥特别用处的地方。

本章将涵盖以下主题：

* 微服务简介以及与单体架构的比较

* Docker 和 Kubernetes 如何融入微服务世界

* 何时使用微服务架构

在实际创建 Java 微服务并使用 Docker 和 Kubernetes 部署它之前，让我们先解释微服务的理念，并将其与单体架构进行比较。

## 微服务简介

根据定义，微服务也称为`微服务架构`（`MSA`），是一种架构风格和设计模式，它认为应用程序应该由一组松耦合的服务组成。这种架构将业务领域模型分解为更小的、一致的部分，并由服务来实现这些。换句话说，每个服务都将有自己的职责，且与彼此相互独立，每个服务都提供某个特定的功能。

这些服务应该是隔离且自治的。然而，它们自然需要通过通信来提供某些业务功能。它们通常使用`REST`暴露或通过发布/订阅模式发布和订阅事件来 get 通信。

解释微服务理念背后逻辑的最佳方法是将其与构建大型应用程序的传统方法——单体设计进行比较。

请看下面的图，它展示了单体应用程序和由微服务组成的分布式应用程序：

![](img/Image00056.jpg)

正如你在上一个图中所示，单体应用程序与使用微服务架构创建的应用程序完全不同。让我们比较这两种方法，并指出它们的优缺点。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

* 电子书搜索下载

* 书单分享

* 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

* 电子书搜索下载

* 电子书打包资源分享

* 学习资源分享

## 单体架构与微服务

我们首先从描述单体架构开始比较，以介绍它的特征。

### 单体架构

在过去，我们通常将应用程序创建为完整、巨大且统一的代码块。以一个 Web MVC 应用程序为例。此类应用程序的简化架构如如下所示：

![](img/Image00057.jpg)

如你所见，该图展示了一个典型的 Web 应用程序，在本例中是银行系统的一个片段。它是`模型-视图控制器`（`MVC`）应用程序，由模型、视图和控制器组成，用于向客户端浏览器提供 HTML 内容。它可能还可以通过`REST`端点接收和发送 JSON 内容。这种应用程序是作为一个单元构建的。如你所见，这里有几层。企业级应用程序通常由三部分组成：客户端用户界面（包括在浏览器中运行的 HTML 页面和 JavaScript）、处理`HTTP`请求的服务端部分（可能是使用某些类似 Spring 的控制器构建的），然后是服务层，它可能可以使用 EJBs 或 Spring 服务实现。服务层执行特定领域的业务逻辑，并最终检索/更新数据库中的数据。这是一个非常典型的 Web 应用程序，我们每个人可能都偶尔创建过一次。整个应用程序是一个单体，一个单一逻辑的可执行文件。若要对系统进行任何更改，我们必须构建并部署整个服务器端应用程序的更新版本；此类应用程序被封装成单个`WAR`或`EAR`归档，连同所有 HTML 和 JavaScript 文件等静态内容。部署时，所有应用程序代码都运行在同一台机器上。扩展此类应用程序通常需要将完全相同的应用程序代码的多副本部署到集群中的多台机器上，可能在某些负载均衡器之后。

这种设计并不坏，毕竟我们的应用程序可以正常运行。但世界变化得很快，特别是在使用敏捷开发方法时。企业已开始要求以比以往任何时候都快的速度发布软件。ASAP（尽快快）已成为 IT 开发语言词典中一个非常常见的词汇。规范不断变动，因此代码频繁变化并随时间不断增长。如果开发应用程序的团队很大（对于复杂、巨大的应用程序来说，很可能是这样），每个人必须非常小心，不要破坏彼此的工作。随着每个新功能的添加，我们的应用程序变得越来越复杂。编译和构建时间变得越来越长，早晚使用单元测试或集成测试来测试整个部分将变得棘手。此外，新加入团队成员的切入点可能是令人生畏的，他们将需要从源码仓库中检出整个项目。然后他们需要在 IDE 中构建它（对于大型应用程序来说，这并不总是那么容易），并分析和理解组件结构以完成工作。此外，负责用户界面部分的人员需要与中间层的开发人员、数据库建模的人员、DBA 等进行通信。团队结构随着时间推移往往会模仿应用程序架构。存在一种风险：负责特定层的开发者倾向于向他控制的层中放入尽可能多的逻辑。结果是，代码随着时间推移可能变得不可维护。我们都经历过并做过这些，不是吗？

此外，单体系统的扩展并不像将一个`WAR`或`EAR`放入另一个应用程序服务器并启动它那么简单。由于所有应用程序代码都运行在服务器的同一个进程中，通常扩展应用程序的各个部分几乎是不可能的。以这个例子为例：我们有一个集成了 VOIP 外部服务的应用程序。我们的应用程序用户不多，但有大量来自 VOIP 服务的事件需要我们处理。为了处理日益增长的负载，我们需要扩展应用程序，在单体系统的情况下，我们需要扩展整个系统。这是因为应用程序是一个单一的、巨大的工作单元。如果应用程序的某一个服务非常消耗 CPU 或资源，则整个服务器都必须配置足够的内存和 CPU 来处理负载。这可能是昂贵的。每台服务器都需要快速的 CPU 和足够的内存，以便运行我们应用程序中最需求的部分。

所有单体应用程序都具有以下特征：

* 它们规模庞大，通常涉及许多人员共同工作。尽管拥有强大的机器和优秀的开发环境（例如`IntelliJ IDEA`），在将项目加载到 IDE 时，这可能会成为一个问题。但这不仅仅关乎成百、上万甚至数百万行代码，还关乎解决方案的复杂性，例如团队成员之间的通信问题。通信问题可能导致同一个问题在应用程序的不同部分有多个解决方案。这会让系统变得更大，并很容易演变成一个无人也无法理解整个系统的“大泥球”（big ball of mud）。此外，人们可能由于害怕对系统引入重大更改，因为另一端的某个功能可能会突然停止工作。如果这在生产系统中被用户报告，那就太糟糕了。

* 它们的发布周期很长，我们都了解发布管理、权限、回归测试等流程。对于一个庞大的单体应用，几乎不可能创建出持续交付流。

* 它们很难扩展；运维团队在集群中部署一个新应用程序实例通常需要投入大量工作。要扩展特定功能是不可能的，你唯一的选择是增加集群中整个系统的实例数量。这使得扩扩缩容变成了一项巨大的挑战。

* 一旦部署失败，整个系统将不可用。

* 你被锁定在特定的编程语言或技术栈中。当然，使用`Java`时，部分可以使用运行在`JVM`上的一种或多种语言开发，如`Scala`、`Kotlin`或`Groovy`，但如果你需要与`.net`库集成，麻烦就来了。这意味着你并不总是能够使用合适的工具来完成工作。想象一种场景：你想在数据库中存储大量复杂的文档，它们通常具有不同的结构。作为文档数据库的`MongoDB`应该是合适的对吧？是的，但我们的系统运行在`Oracle`上。

* 它并不非常适用于敏捷开发流程，在那种流程中，我们需要不断实现更改，几乎立即发布到生产环境，并为下一次迭代做好准备。

如你所见，单体应用适用于小团队和小项目。如果你需要规模更大且涉及许多团队的东西，最好考虑替代方案。但对于你可能正在处理的现有单体系统该怎么办？你可能会发现将系统的某些部分外包并拆分为小型服务是很有帮助的。这将加速开发过程并提高可测试性，还会让你的应用程序更容易扩展。在单体应用仍保留核心功能的同时，许多部分可以外包为支持核心模块的小侧服务。这种方法如如下所示：

![](img/Image00058.jpg)

在这种（所谓的）过渡方案中，主业务逻辑将留在你的单体应用中。诸如集成、后台作业或其他由消息触发的其他型子系统，可以移动到它们自己的服务中。你甚至可以将这些服务放入云端，以进一步减少对周围基础设施管理的需求。这种方法允许你将现有的单体应用逐渐迁移到完全面向服务的架构。让我们来看看微服务方法。

### 微服务架构

微服务架构旨在解决我们在单体应用中提到的问题。主要区别在于，单体应用中定义的服务被拆分为各个独立的服务。最棒的是，它们在不同的宿主机上独立部署。请看下图：

![](img/Image00059.jpg)



使用微服务架构创建应用程序时，每个微服务都负责一个特定的业务功能，并且仅包含执行该特定业务逻辑所需的实现。这等同于使用“分而治之”（divide and conquer）的方式来构建系统。这似乎与面向面向的架构（SOA）相似。事实上，传统的 SOA 和微服务架构具有一些共同特征。它们都将应用程序的碎片组织成服务，并都定义了服务可以从其他服务解耦的清晰边界。

然而，SOA 的根源在于将单体应用与另一个应用集成的需求。这通常是通过 API（通常基于 SOAP，使用沉重的 XML 消息）来实现的。在 SOA 中，这种集成高度依赖于中间的中间件，通常是企业服务总线（`ESB`）。微服务架构也可以利用消息总线，但有显著差异。在微服务架构中，消息层完全没有逻辑，仅用作从一个服务到另一个服务的消息传输。

这与 `ESB` 形成了鲜明对比，后者需要大量的逻辑来进行消息路由、模式验证、消息翻译等。因此，微服务架构比传统的 SOA 不复杂。

在扩展方面，微服务与单体应用相比有巨大差异。微服务的关键优势在于单个服务可以根据资源需求单独扩展。这是因为它们自给自足且独立。由于微服务通常部署在资源较小的宿主机上，宿主机只需要包含服务正常运行所需的资源。随着资源需求的增长，无论是水平扩展还是垂直扩展都变得简单。要进行水平扩展，你只需要部署足够的实例来处理特定组件的负载即可。

我们将在接下来的章节中回到这个概念，届时我们将学习 `Kubernetes`。与单体系统相比，垂直扩展也容易得多且便宜得多，你只需要升级部署微服务的宿主机即可。此外，引入服务的新版本也很容易，你不需要为了升级某个功能而停止整个系统。事实上，你可以在运行时完成它。

部署后，微服务提高了整个应用程序的容错能力。例如，如果某个服务中出现内存泄漏或其他问题，只有该服务会受到影响，然后可以进行修复和升级，而不会干扰系统的其他部分。这在单体架构中是不可能的，因为其中一个故障组件就会导致整个应用程序崩溃。

从开发者的角度来看，将应用程序拆分为单独的部分并独立部署具有巨大的优势。精通服务器端 JavaScript 的开发者可以开发其负责的 `node.js` 部分，而系统的其他部分将使用 `Java` 进行开发。这都与每个微服务暴露的 API 有关；除了这个 API 之外，每个微服务都不需要了解其他服务的任何信息。这使得开发过程变得简单得多。

独立的微服务可以进行独立的开发和测试。基本上，微服务方法规定，与其让所有开发者都在一个上维护一个往往变得难以管理的巨型代码库，不如由小型且敏捷的团队管理几个较小的代码库。服务之间唯一的依赖就是它们暴露的 API。

数据存储方面也存在差异。正如我们之前提到的，每个微服务都应该负责存储自己的数据，因为同样，它应该是独立的。这导致了微服务架构的另一个特性：实现多异构持久化（polyglot persistence）的可能性。微服务应该拥有自己的数据。

虽然微服务通过 `REST` 端点或事件与其他微服务进行通信和数据交换，但它们可以使用最适合任务的形式存储自己的数据。如果数据是关系型的，服务将使用传统的关系型数据库，如 `MySQL` 或 `PostgreSQL`。如果文档数据库更适合任务，微服务可以使用 `MongoDB` 等，或者如果数据是图结构，可以使用 `Neo4j`。

这得出了另一个结论：通过实现微服务架构，我们现在只需要选择最适合任务的编程语言或框架，这也适用于数据存储。当然，在微服务架构中，拥有自己的数据可能会带来一个挑战，即数据一致性。我们将在本章的稍后部分讨论这个主题。

让我们从开发过程的角度总结一下使用微服务架构的优势：

- 服务可以使用各种语言、框架及其版本进行编写。
- 每个微服务相对较小，开发者更容易理解（这导致了更少的 bug）、易于开发且可测试。
- 部署和启动时间很快，这提高了开发者的生产力。
- 每个服务可以由多个服务实例组成，以增加吞吐量和可用性。
- 每个服务都可以独立于其他服务进行部署，更容易频繁地发布服务的新版本。
- 更容易组织开发过程；每个团队拥有并负责一个或多个服务，并可以独立于所有其他团队开发、发布或扩展其服务。
- 你可以选择你认为最适合任务的任何编程语言或框架。对于技术栈没有长期的承诺。如果需要，可以使用新的技术栈重写服务，如果 API 没有发生变化，这对于系统的其他部分来说是透明的。
- 更利于持续交付，因为小单元更容易管理、测试和部署。只要每个团队保持向后和向前的 API 兼容性，它就可以在与其他团队解耦的发布周期中工作。在某些情况下，这些发布周期是耦合的，但这不是常见情况。

### 维护数据一致性

服务之间必须是松耦合，以便它们能够独立地开发、部署和扩展。它们当然需要通信，但它们是相互独立的。它们具有定义良好的接口，并封装了实现细节。但数据呢？

在现实世界和非复杂的应用程序中（微服务应用很可能是复杂的）中，业务事务往往必须跨越多个服务。例如，如果你创建一个银行应用程序，在执行客户的资金转账订单之前，你需要确保它不会超过其账户余额。单体应用随附的单一数据库为我们提供了很多便利：原子事务、单一数据查找点等。

另一方面，在微服务世界中，不同的服务需要保持独立。这意味着它们可以有不同的数据存储需求。对于某些服务，将是一个关系型数据库，而其他可能需要文档数据库，如 `MongoDB`，它擅长存储非结构化数据。

因此，当我们构建微服务并将数据库拆分为多个较小的数据库时，我们如何管理这些挑战？我们也提到服务应该拥有它们的数据。也就是说，每个微服务只依赖于自己的数据库。数据库实际上是服务实现的一部分。这在设计微服务架构时带来了一个非常有趣的挑战。

正如 Martin Fowler 在他的 `Microservice trade-offs` 专中所说的：分布式系统中维护强一致性是非常困难的，这意味着每个人必须管理最终一致性。我们如何处理这个问题？嗯，这一切取决于边界。

### 微服务的边界

微服务应该具有定义的职责和边界。微服务需要根据业务领域进行分组。此外，在实践中，你需要这样设计微服务，使其无法直接连接到其他服务的数据库。

松耦合意味着微服务应该暴露建模数据相关访问模式的清晰 API 接口。它们必须遵守这些接口，当需要更改时，你可能会引入版本机制并创建另一个版本。你可以使用发布/订阅模式从一个微服务分发事件供其他服务处理，如下图所示：

![](img/Image0060.jpg)

正如你所看到的，使用微服务架构面临许多挑战，但也具有许多优势。不过，必须提醒你，我们还有更多需要解决的挑战。由于服务之间是相互独立的，它们可以使用不同的编程语言来实现。这意味着每个服务的部署过程可能各不相同：Java Web 应用和 `node.js` 应用的部署过程将完全不同。

这可能会使服务器的部署变得复杂。而这正是 `Docker` 大显身手的地方。

### Docker 的角色

正如你在前面的章节中所记忆的，`Docker` 利用了容器化概念。你只需要将你的应用程序（在此背景下，应用程序是一个微服务），无论它使用什么语言和技术，放入单一的可部署且可运行软件单元中，称为镜像。

我们将在第 4 章 *创建 Java 微服务* 中详细介绍将 Java 应用打包成镜像的过程。`Docker` 镜像将包含服务运行所需的所有内容，它可以是一个带有所有所需库和应用程序服务器的 Java 虚拟机，也可以是一个与 `node.js` 运行时一起打包的 `node.js` 应用以及所有需要的 `node.js` 模块（例如 `express.js` 或任何 `node.js` 服务运行所需的模块）。

一个微服务可能由两个容器组成：一个运行服务代码，另一个运行数据库以保存服务自己的数据。

`Docker` 将容器隔离到单个进程或服务。实际上，我们应用程序的所有部分都将是一组打包好的、准备就用的 `Docker` 镜像。容器作为完全隔离的沙箱运行，每个容器只存在操作系统的最简内核。

`Docker` 使用 Linux 内核并利用了如 `cnames` 和 `namespaces` 等内核接口，这允许多个容器在相互完全隔离运行的同时共享同一个内核。

由于底层系统的系统资源是共享的，你可以以最优性能运行服务，与传统的虚拟机相比，它的资源占用要小得多。由于容器是可移植的，正如我们在第 2 章 *网络与持久化存储* 中提到的，它们可以在任何可以运行 `Docker` 引擎的地方运行。

这使得微服务的部署过程变得简单。若要部署运行在特定主机上的服务新版本，只需停止正在运行的容器，并启动一个基于最新版本服务代码的 `Docker` 镜像的新容器。我们将在本书的后部分介绍创建镜像新版本的过程。当然，主机上运行的所有其他容器都不会受到此更改的影响。

由于微服务需要使用 `REST` 协议进行通信，我们的 `Docker` 容器（更准确地说，你打包并运行在 `Docker` 容器内部的 Java 微服务）也需要通过网络进行通信。正如你在第 2 章 *网络与持久化存储* 中记忆的网络知识，为 `Docker` 容器暴露和映射网络端口非常简单。

`Docker` 容器化似乎非常适合微服务架构。你可以将微服务封装成一个便携的盒子并暴露所需的网络端口，使其能够与外界通信。需要时，你可以运行任意数量这样的盒子。

让我们总结一下处理微服务时实用的 `Docker` 特性：

- 易于伸缩服务，只需更改运行的容器实例数量。
- 容器隐藏了每个服务背后的技术细节。无论使用什么技术栈，所有带有服务的容器启动和停止方式完全相同。
- 每个服务实例都是隔离的。
- 你可以限制容器消耗的 CPU 和内存的运行时约束。
- 容器的构建和启动非常快。正如你在第 1 章 *Docker 简介* 中记忆的，与传统的虚拟化相比，开销极小。
- `Docker` 镜像层会被缓存，这在创建服务新版本时为你提供了额外的速度提升。

这难道不完美符合微服务架构的定义吗？确实如此，但存在一个问题。由于我们的微服务分布在多个主机上，很难追踪哪些主机正在运行某些服务，也无法监控哪些服务需要更多资源，或者在最坏的情况下，它们已经挂掉且无法正常运行。

此外，我们需要将属于特定应用程序或功能的服务进行分组。这是我们谜图中缺失的元素：容器管理和编排。许多框架的出现完全是为了处理更复杂的场景：管理集群中的单项服务或跨主机的服务的多个实例，或者在部署和管理层面如何在多个服务之间进行协调。这些工具之一就是 `Kubernetes`。

### Kubernetes 的角色

虽然 `Docker` 提供了容器的生命周期管理，但 `Kubernetes` 通过提供编排和管理容器集群将其推推高度。如你所知，使用微服务架构创建的应用程序将包含一些分离且独立的服务。我们如何对它们进行编排和管理呢？

`Kubernetes` 是一个非常适合这种场景的开源工具。它定义了一组构建块，提供了部署、维护和扩展应用程序的机制。`Kubernetes` 中的基本调度单元被称为 `pod`。

`pod` 中的容器运行在同一主机上，共享相同的 IP 地址，并通过 `localhost` 找到彼此。它们还可以使用标准的进程间通信（如共享内存或信号量）进行相互通信。`pod` 为容器化组件增加了另一层抽象。

一个 `pod` 由一个或多个容器组成，这些容器保证位于同一台主机上并可以共享资源。这等同于属于某个应用程序的容器逻辑集合。

对于传统服务，例如带有相应数据库的 `REST` 端点（实际上是整个微服务），`Kubernetes` 提供了一个 `service` 概念。`service` 定义了 pod 的逻辑组，并强制执行从外部访问此类逻辑组的规则。

`Kubernetes` 使用标签（Labels）概念来标记 pod 和其他资源（服务、部署等）。这些是简单的键值对，可以在创建时附加到资源上，并在任何时间添加和修改。我们之后将使用标签来组织并选择资源子集（例如 pod），并将它们作为一个实体进行管理。

`Kubernetes` 可以自动将你的容器或一组容器放置在特定的主机上。为了找到合适的主机（负载最小的主机），它将分析主机的当前负载以及不同的位置和可用性约束。当然，你可以手动指定主机，但拥有此自动功能可以充分利用可用的处理能力和资源。

`Kubernetes` 可以在容器、pod 和集群级别监控资源使用情况（CPU 和内存）。资源使用和性能分析代理在每个节点运行，自动发现节点上的容器，并收集 CPU、内存、文件系统和网络使用统计数据。

`Kubernetes` 还管理你容器实例的生命周期。如果实例过多，其中一些将被停止。如果工作负载增加，新的容器将自动启动。这一功能被称为容器自动伸缩。它会根据你为服务定义的内存、CPU 占用率或其他指标（例如每秒查询数）自动更改运行中容器的数量。

正如你在第 2 章中回顾的——`网络和持久化存储`中所介绍的，`Docker` 通过操作卷（volumes）来持久化你的应用程序数据。`Kubernetes` 也支持两种类型的卷：与 pod 具有相同周期的普通卷（regular），以及生命周期独立于任何 pod 的持久化卷（persistent）。

卷的类型实现方式与 `Docker` 相同，以插件的形式存在。这种可扩展的设计允许你拥有几乎任何你需要的卷。它目前包含了存储插件，如 Google Cloud 平台卷、AWS 弹性块存储卷等。

`Kubernetes` 可以监控你服务的健康状况，它可以通过对指定的 URL 执行指定的 `HTTP` 方法（例如 `GET`）并分析响应中返回的 `HTTP` 状态码来实现。此外，TCP 探测可以检查指定的端口是否开放，这也可以用于监控服务的健康状况。

最后，但同样重要的是，你可以指定可以在容器中执行的命令，以及根据命令响应可以采取的某些操作。如果指定的探测方法信号表明容器出现问题，它可以被自动重启。

当你需要更新软件时，`Kubernetes` 支持滚动更新（rolling updates）。这一功能允许你以最小的停机时间更新已部署的容器化应用程序。滚动更新功能允许你指定在更新期间允许停止的旧副本数量。

正如你所知道的，使用 `Docker` 升级容器化软件特别简单，它只是容器的一个新镜像版本。我猜你现在已经有了全貌。部署（Deployments）可以进行更新、发布或回滚。负载均衡、服务发现等你在编排和管理运行在 `Docker` 容器中的微服务集群时可能需要的所有功能，在 `Kubernetes` 中都是可用的。

`Kubernetes` 最初由 Google 为大规模应用而设计，如今已被各种规模的组织广泛用于生产环境中的容器。

### 何时使用微服务架构

微服务架构是组织应用程序的一种新方式。在开始阶段，当你开始创建一个系统且其规模较小时，可能不需要使用微服务方法。当然，基础 Web 应用程序也没有问题。当你为办公室的人编写基础 Web 应用程序时，采用微服务架构可能大材小用了。

另一方面，如果你计划开发一种供数百万移动客户端使用的全新超级互联网服务，我会考虑从一开始就采用微服务。开个玩笑说，你懂的，始终要尝试为工作选择最合适的工具。归结到底，目标是提供业务价值。

然而，在一段时间之后，你应该记住系统的整体状况。如果你的应用程序在功能和特性上的增长超出了你的预期，或者你从一开始就知道这一点，你可能想要开始将功能拆分为微服务。

你应该尝试进行功能拆分，并指出你系统中具有清晰边界且未来需要扩展和独立部署的碎片部分。如果一个项目有很多人参与，让他们开发应用程序中各个相互分离、独立的部分，将极大地推动开发进程。

每个服务可以采用混合的技术栈，每个服务可以使用不同的编程语言或框架实现，并在最合适的数据存储中存储自己的数据。这关键在于 API 以及服务之间通信的方式。

拥有这种架构将带来更短的上市时间，与单体架构相比，其构建、测试和部署时间被大大缩短。如果你只需要扩展需要处理更高负载的服务。既然有了 `Docker` 和 `Kubernetes`，没有理由不采用微服务架构；它在未来肯定会有回报。

微服务架构不仅仅是一个新的流行词汇，它在今天被广泛认为是构建应用程序的更优方式。微服务理念的诞生源于对更好地利用计算资源的需求，以及维护日益复杂的 Web 应用程序的需求。

Java 是构建微服务的极佳选择。你可以将微服务创建为单个可执行的 JAR 包、自包含的 Spring Boot 应用程序，或者部署在 `Wildfly` 或 `Tomcat` 等应用服务器上的全功能 Web 应用程序。根据你的用例以及微服务的职责和功能，上述任何一种方法都可以胜任。

Docker 仓库（Repository）包含了许多实用的镜像，你可以自由地将它们作为微服务的基础。Docker Hub 中提供的许多镜像是由个人创建的，有些扩展了官方镜像并根据需求进行了定制，而另一些则是从基础镜像开始定制的整个平台配置。

基础镜像可以是简单的纯 `JDK`，也可以是准备好运行的完全配置的 `Wildfly`。这极大地提升了开发性能。

### 总结

在本章中，我们比较了单体架构和微服务架构。我希望你能看到后者的优势。我们还学习了在部署容器化应用程序时，`Docker` 和 `Kubernetes` 如何融入整体布局，这使得这一过程变得更加简单愉快。

Java 是一个实现微服务经过验证的生态系统。你将创建的软件将由小的、高度可测试且高效的模块组成。事实上，在第 4 章`创建 Java 微服务`中，我们将亲手操作创建一个这样的微服务。

## 创建 Java 微服务

在第 3 章`处理微服务`中，我们学习了微服务架构背后的很多理论。现在是时候进行实践操作了；我们将实现自己的微服务。这将是一个简单的 REST 服务，接受 `HTTP` 方法（如 `GET` 和 `POST`）来检索和更新实体。

在 Java 中开发微服务有几种选择。在本章中，我们将概述两种主要方法，最流行的可能是 JEE7 和 Spring Boot。我们将简要查看如何使用 JEE `JAX-RS` 编写微服务。我们还将创建一个在 Spring Boot 之上的微服务。

事实上，在第 5 章`为 Java 应用创建镜像`中，我们将 Docker 容器运行我们的 Spring Boot 微服务。

在本章结束时，我们将熟悉一些实用的工具——我们将使用诸如 `Spring Initial` 等代码生成工具来快速启动一个 Spring Boot 服务项目。在开始编写自己的微服务之前，让我们简要解释一下什么是 REST。

### REST 简介

REST 缩写代表表述层状态转移（Representational State Transfer）。它是一种基于网络的软件架构风格和设计。它描述了一个系统如何与另一个系统通信状态。这与微服务世界完美契合。

正如你在第 3 章《处理微服务》中所记得，基于微服务架构的软件应用程序是一系列相互通信的、分离且独立的服务。

在继续深入之前，我们需要理解 REST 中的一些概念：



- `resource`（资源）：这是 REST 架构中的核心概念。任何信息都可以是一个资源，例如银行账户、一个人、一张图片或一本书。资源的表示必须是“无状态的”（stateless）。

- `representation`（表示）：资源的特定表示方式。例如，银行账户资源可以使用 `JSON`、`XML` 或 `HTML` 来表示。不同的客户端可能会请求资源的不同表示，一个可以接受 `JSON`，而其他则期望 `XML`。

- `server`（服务器）：服务提供者。它暴露可以被客户端消费的服务。

- `client`（客户端）：服务消费者。这可以是另一个微服务、应用程序，或者只是运行 Angular 应用程序的用户浏览器等。

正如定义所示，REST 用于在网络上传输这些资源的表示。表示本身是通过某些媒体类型创建的。媒体类型可以不相同。媒体类型的示例包括 `JSON`、`XML` 或 `RDF`。`JSON` 媒体类型被广泛接受，可能是最常用的。在我们的示例中，我们也将使用 `JSON` 与服务通信。当然，REST 不是微服务通信的唯一选择；还有其他选择，例如 Google 非常优秀的 `gRPC`，它带来了诸如 `HTTP/2` 和 `protobuff` 等优势。

在 REST 架构中，资源通过组件进行操纵。事实上，这些组件就是我们的微服务。组件通过标准的统一接口请求并操作资源。REST 并不绑定任何特定协议；然而，REST 调用通常使用最流行的 `HTTP` 或 `HTTPS` 协议进行。在 `HTTP` 的情况下，这种统一接口由标准的 HTTP 方法组成，如 `GET`、`PUT`、`POST` 和 `DELETE`。

REST 并不绑定任何特定协议。

在我们开始实现响应 `HTTP` 调用的服务之前，了解我们将要使用的 HTTP 方法是值得的。现在我们将更仔细地关注一下它们。

### HTTP 方法

基于 REST 的架构使用标准的 HTTP 方法：`PUT`、`GET`、`POST` 和 `DELETE`。以下列表给出了这些操作的解释：

- `GET` 提供对资源的读取访问权限。调用 `GET` 不应产生任何副作用。这意味着 `GET` 操作是幂等的（idempotent）。资源绝不会通过 `GET` 请求被更改；例如，请求没有副作用。这意味着它是幂等的。

- `PUT` 创建一个新资源。与 `GET` 类似，它也应该是幂等的。

- `DELETE` 移除一个或多个资源。`DELETE` 操作在被重复调用时不应产生不同的结果。

- `POST` 将更新现有的资源或创建一个新资源。

RESTful Web 服务简单来说基于 `REST` 资源概念和 HTTP 方法使用的 Web 服务。它应该定义暴露方法的基 URI、支持的 MIME 类型（如 `XML`、文本或 `JSON`）以及服务处理的操作（`POST`、`GET`、`PUT` 和 `DELETE`）。

根据 RESTful 原则，HTTP 对于 REST 来说简单且自然。这些原则是一组约束，确保客户端（例如服务消费者、其他服务或浏览器）能够以灵活的方式与服务器通信。让我们来看它们。

在 REST 原则的客户端-服务器通信中，所有以 RESTful 风格构建的应用在原则上必须也是客户端-服务器。应该有一个服务器（服务提供者）和一个客户端（服务消费者）。这使得服务器和客户端能够松耦合并独立进化。这非常符合微服务的概念。正如你在第 3 章《处理微服务》中所记得，它们必须是独立的：

- `Stateless`（无状态）：每个 `client` 请求都需要完全表示其状态。服务器必须完全理解 `client` 请求，而无需使用任何服务器上下文或服务器会话状态。也就是说，所有状态必须在客户端侧管理。每个 REST 服务都应该是无状态的。随后的请求不应依赖于临时存储的先一个请求的数据。消息应该是自描述的。

- `Cacheable`（可缓存）：响应数据可以被标记为可缓存或不可缓存。任何标记为可缓存的数据都可以重用作为对相同后续请求的响应。每个响应都应该指示其是否可缓存。

- `Uniform interface`（统一接口）：所有组件必须通过单一统一接口进行交互。由于所有组件交互都通过此接口发生，与不同服务的交互非常简单。

- `Layered system`（分层系统）：服务的消费者不应假设直接连接到服务提供者。也就是说，客户端在任何时候都无法判断自己是连接到终端服务器还是中间层。中间层有助于实施安全策略，并通过启用负载均衡提高系统的可扩展性。由于请求可以被缓存，客户端可能会从中间层获取缓存响应。

- `Manipulation of resources through representations`（通过表示操作资源）：一个资源可以有多种表示。可以通过这些表示的任何消息来修改资源。

- `Hypermedia As The Engine Of Application State (HATEAS)`（超媒体作为应用状态引擎）：RESTful 应用的消费者只需要知道一个固定的服务 URL。后续资源都应该从资源表示中的链接被发现。

上述概念代表了 REST 的定义特征，并将 REST 架构与其他架构（如 Web 服务）区分开来。需要注意的是 REST 服务是一种 Web 服务，但 Web 服务不一定是 REST 服务。

REST 微服务应该表示实体的状态。例如，我们的实体是一本书（以及它的属性如 ID、标题和作者），用 `XML`、`JSON` 或纯文本表示。对 REST 最基本的思考方式是将其视为格式化服务 URL 的方式。例如，有了 `book` 资源，我们可以想象服务中定义了以下操作：

- `/books` 允许访问所有书籍。

- `/books/:id` 是查看单个书籍的操作，根据其唯一 ID 检索。

- 向 `/books` 发送 `POST` 请求是创建新书籍并将其存储在数据库中的方法。

- 向 `/books/:id` 发送 `PUT` 请求是更新给定书籍的方法，再次通过唯一 ID 标识。

- 向 `/books/:id` 发送 `DELETE` 请求是删除特定书籍的方法，再次通过唯一 ID 标识。

值得理解的是 REST 并不是 HTTP。它经常使用 HTTP 是因为在最通用的形式下，REST 是关于将动词概念与任意名词集合进行映射，并且与 HTTP 方法非常契合。HTTP 包含一组有用的通用动词（`GET`、`POST`、`PUT`、`PATCH` 等）。

在 REST 中，我们传输的不是实际对象，而是它的一种特定形式表示，例如 XML、文本或 JSON。作为一种架构风格，REST 意味着它只是一个概念。如何实现它取决于你。Java 非常适合开发 REST 服务。让我们来看看如何实现。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

### Java 中的 REST 实现

在 Java 中开发 REST 服务时，我们至少有几种框架可以使用。最流行的将是带有 JAX-RS 的纯 JEE7，以及带有 Spring Boot 的 Spring Framework。你可以使用其中任何一种，也可以将它们混合使用。让我们现在详细查看这两个框架，从 JAX-RS 开始。

### Java EE7 - 使用 Jersey 的 JAX-RS

JAX-RS 是由于 `Java Specification Request`（`JSR`）311 而诞生的。正如官方定义所示，JAX-RS 是用于 RESTful Web 服务的 Java API。它是一个根据 REST 架构模式创建 Web 服务的规范。JAX-RS 使用 Java SE 5 中引入的 Java 注解来简化 Web 服务客户端和节点（endpoints）的开发和部署。从 1.1 版本开始，JAX-RS 是 Java EE 的官方组成部分。作为 Java EE 官方部分的一个显著特点是，使用 JAX-RS 无需任何配置。

带有 JAX-RS 2.0 的 Java EE 7 带来了几个实用的功能，进一步简化了微服务的开发。JAX-RS 2.0 最重要的新功能之一是支持遵循 REST 的 HATEOAS 原则的超媒体驱动控制（hypermedia following）。来自 Oracle 的库 `Jersey` 可能是实现此规范最广为人知的库。

Jersey 是 `JSR 311` 规范的参考实现。

Jersey 实现提供了一个在 Java Servlet 容器中实现 RESTful Web 服务的库。在服务端，Jersey 提供了一个 servlet 实现，它通过扫描预定义的类来识别 RESTful 资源。Jersey 让编写 RESTful 服务变得简单得多。它抽象了许多你原本需要自己完成的低级代码工作。使用 Jersey，你可以以声明式的方式进行操作。

注册在你的 `web.xml` 文件中的 servlet 会分析入站的 `HTTP` 请求，并选择正确的类和方法来响应该请求。它通过查看类级和方法级别的注解来找到要执行的方法。带有注解的类可以位于不同的包中，但你可以通过 `web.xml` 指示 Jersey servlet 扫描某些包中的带注解类。

JAX-RS 支持通过 `Java Architecture for XML Binding`（`JAXB`）创建 XML 和 JSON。Jersey 实现还提供了一个 `client` 库用于与 RESTful Web 服务通信。

正如我们之前所说的，我们使用 Java 注解开发 JAX-RS 应用程序。这种工作既简单又愉快。现在让我们描述这些注解。

### JAX-RS 注解

JAX-RS 中最重要的注解如表所示：

| 注解 | 含义 |
| :--- | :--- |
| `@PATH` | 设置路径为基础 `URL + /your_path`。基础 URL 基于你的应用程序名称、servlet 以及来自 `web.xml` 配置文件的 URL 模式。 |
| `@POST` | 表示接下来的方法将响应 `HTTP POST` 请求。 |
| `@GET` | 表示接下来的方法将响应 `HTTP GET` 请求。 |
| `@PUT` | 表示接下来的方法将响应 `HTTP PUT` 请求。 |
| `@DELETE` | 表示接下来的方法将响应 `HTTP DELETE` 请求。 |
| `@Produces` | 定义由带有 `@GET` 注解的方法交付的 MIME 类型。例如，可以是 `"text/plain"`、`"application/xml"` 或 `"application/json"`。 |
| `@Consumes` | 定义由此方法消耗的 MIME 类型。 |
| `@PathParam` | 从 URL 中提取（注入）值到方法参数中。通过这种方式，你可以将资源的 ID 注入到方法中获取正确的对象。 |
| `@QueryParam` | 用于提取（注入）随请求而来的 URI 查询参数。`Uniform Resource Identifier`（`URI`）是用于在互联网上标识名称或资源的字符字符串。 |
| `@DefaultValue` | 指定默认值。对可选参数有用。 |
| `@CookieParam` | 允许你将客户端请求发送的 cookie 注入到你的 JAX-RS 资源方法中的注解。 |
| `@Provider` | `@Provider` 注解用于任何 JAX-RS 运行时感兴趣的内容，例如 `MessageBodyReader` 和 `MessageBodyWriter`。对于 `HTTP` 请求，`MessageBodyReader` 用于将 `HTTP` 请求实体映射到方法参数。在响应端，返回值由 `MessageBodyWriter` 映射到 `HTTP` 实体。如果应用程序需要额外的元数据，例如 `HTTP` 头或不同的状态码，方法可以返回一个使用 `Response` 构建的 `response`。 |
| `@ApplicationPath` | `@ApplicationPath` 注解用于定义应用程序的 URL 映射。由 `@ApplicationPath` 指定路径是资源类中 `@Path` 指定的所有资源 URI 的基础。你可以在 `javax.ws.rs.Application` 的子类上应用 `@ApplicationPath`。 |

这些注解名称初看可能并不清晰直观。让我们看看示例 REST 端点的实现，它将会变得清晰许多。

应用程序本身标记了 `@ApplicationPath` 注解。默认情况下，在符合 JEE 的服务器启动期间，JAX-RS 将扫描 Java 应用程序存档中的所有资源以发现暴露的节点。我们可以重写 `getClasses()` 方法手动将资源类注册到 JAX-RS 运行时。可以通过下面的示例：

```java
package pl.finsys.jaxrs_example 
@ApplicationPath("/myApp") 
public class MyApplication extends Application { 
   @Override 
   public Set<Class<?>> getClasses() { 
      final Set<Class<?>> classes = new HashSet<>(); 
      classes.add(MyBeansExposure.class); 
      return classes; 
   } 
} 
```

在上一个示例中，我们只是注册了一个 REST 应用程序，赋予它 `/myApp` 基础路径。只有一个 `REST` 方法处理器（节点），即 `MyBeansExposure` 类，我们在 REST 应用程序中注册了它。在独立 Java 类中实现的简化 REST 端点看起来如下：

```java
package pl.finsys.jaxrs_example 
import javax.annotation.PostConstruct; 
import javax.enterprise.context.ApplicationScoped; 
import javax.ws.rs.DELETE; 
import javax.ws.rs.GET; 
import javax.ws.rs.POST; 
import javax.ws.rs.Path; 
import javax.ws.rs.PathParam; 
import javax.ws.rs.container.ResourceContext; 
import javax.ws.rs.core.Context; 
import javax.ws.rs.core.Response; 

@ApplicationScoped 
@Path("beans") 
public class MyBeansExposure { 
    @Context ResourceContext rc; 
    private Map<String, Bean> myBeans; 

    @GET 
    @Produces("application/json") 
    public Collection<Bean> allBeans() { 
        return Response.status(200).entity(myBeans.values()).build(); 
    } 

    @GET 
    @Produces("application/json") 
    @Path("{id}") 
    public Bean singleBean(@PathParam("id") String id) { 
        return Response.status(200).entity(myBeans.get(id)).build(); 
    } 

    @POST 
    @Consumes("application/json") 
    public Response add(Bean bean) { 
        if (bean != null) { 
            myBeans.put(bean.getName(), bean); 
        } 
        final URI id = URI.create(bean.getName()); 
        return Response.created(id).build(); 
    } 

    @DELETE 
    @Path("{id}") 
    public void remove(@PathParam("id") String id) { 
        myBeans.remove(id); 
    } 

} 
```

正如上一个示例所示，我们使用了类级别的 `@Path` 注解。每个标记有 `@GET`、`@PUT`、`@DELETE` 或 `@POST` 注解的方法都会响应以基础 `@Path` 开头的 URI 调用。此外，我们可以在方法级别使用 `@Path` 注解；它会在某种程度上扩展特定方法所响应的 URI 路径。

在我们的示例中，使用 URI 路径 `myApp/beans` 执行的 `HTTP GET` 将调用 `allBeans()` 方法，返回 JSON 格式的 bean 集合。使用 `myApp/beans/12` URI 路径执行的 `GET` 方法将调用 `singleBean()` 方法，由于 `@PathParam` 注解的作用，`{id}` 参数将传递到方法。在 `myApp|beans|12` URI 上调用 `HTTP DELETE` 方法将执行参数值为 `12` 的 `remove()` 方法。

为了给你提供近乎无限的活性，`@Path` 注解支持正则表达式。考虑以下示例：



```java
package pl.finsys.jaxrs_example
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.core.Response;

@Stateless
@Path("/books")
public class BookResource {

   @GET
   @Path("{title : [a-zA-Z][a-zA-Z_0-9]}")
   public Response getBookByTitle(@PathParam("title") String title) {
      return Response.status(200).entity("getBookByTitle is called, title : " + title).build();
   }

   @GET
   @Path("{isbn : \\d+}")
   public Response getBookByISBN(@PathParam("isbn") String isbn) {
      return Response.status(200).entity("getBookByISBN is called, isbn : " + isbn).build();
   }
}
```

在上一个示例中，我们有两个 `@GET` 映射，它们都映射到了相同的 `/books/` 路径。第一个带有 `/{title : [a-zA-Z][a-zA-Z_0-9]}` 参数只会对字母和数字做出响应。第二个带有 `/{isbn : \\d+}` 参数的仅在你调用 URI 时提供数字时才会执行。如你所见，我们映射了两个相同的路径，但每个路径会对不同类型的传入路径参数做出响应。

除了使用 `@PathParam` 外，我们还可以使用 `@QueryParams` 通过请求参数提供参数。请看以下示例：

```java
package pl.finsys.jaxrs_example
import java.util.List;
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.core.Context;
import javax.ws.rs.core.Response;
import javax.ws.rs.core.UriInfo;

@Stateless
@Path("/users")
public class UserResource {
   @EJB private UserService userService;

   @GET
   @Path("/query")
   @Produces("application/json")
   public Response getUsers(
      @QueryParam("from") int from,
      @QueryParam("to") int to,
      @QueryParam("orderBy") List<String> orderBy)) {
      List<User> users = userService.getUsers(from, to, orderBy);
      return Response.status(200).entity(users).build();
   }
}
```

创建 JEE7 REST 服务非常简单，不是吗？通过构建项目并部署到符合 JEE 标准的应用程序服务器，我们已经有了几个可以通过 `HTTP` 调用的端点。但有一种更简单更快速的方法。在微服务时代，我们毕竟希望以最小的开销更快地创建单个组件。Spring Boot 就出现了。让我们现在来看看。

## Spring Boot

Spring 本身是一个非常流行的基于 Java 的框架，用于构建 Web 和企业级应用程序。它不仅关注依赖注入的 Spring Core，Spring Framework 还提供了许多开箱即用的功能，让开发者的工作更容易，并更快交付所需的功能。列表很长；这里只是几个例子：

- **Spring data**：简化了从关系型和 NoSQL 数据存储中进行数据访问
- **Spring batch**：提供了一个强大的批处理框架
- **Spring security**：提供了许多保护应用程序安全的方法
- **Spring social**：支持与 Twitter、Facebook、GitHub 等社交网络网站集成
- **Spring integration**：企业级集成模式的实现，用于通过轻量级消息传递和声明式适配器促进与其他企业应用程序的集成

但是，为什么 Spring 会变得如此流行？有几个原因：

- 它使用了依赖注入方法，这鼓励编写可测试的低耦合代码
- 可以很容易地包含数据库事务管理功能
- 可以与其他流行的 Java 框架集成，例如 JPA/Hibernate 等
- 它包含一个先进的 MVC 框架，用于更快地构建 Web 应用程序，将视图与业务逻辑分离

在 Spring 框架中，配置 bean 有多种方式，例如 XML 定义文件、Java 注解和代码配置。这可能是一个繁琐的过程。此外，我们经常需要为不同的应用程序编写大量的样板配置。Spring Boot 的诞生是为了解决配置的复杂性。我们可以使用 Spring Boot 来满足自己的需求，开发出可以直接运行的小型、独立微服务。它可以是一个单一的可运行 fat JAR 文件，其中包含了运行应用程序所需的所有 Java 依赖。你不需要应用程序服务器或复杂的部署描述符配置。事实上，在后台，Spring Boot 会为你启动一个嵌入式服务器。当然，你并不强制要求使用嵌入式应用程序服务器。你始终可以构建一个 WAR 文件将其部署到自己的 Tomcat 或 Wildfly 上。值得注意的是，尽管在运行 Spring Boot 应用时大部分工作会自动完成，但它并不是一个代码生成框架。

这一切是否让你想起了 Docker 容器的简单性和可移植性？是的，但它是在应用层面。正如我们在第 3 章《处理微服务》中所讨论的那样，我们正在向更小、可独立部署的微服务架构发展。这意味着我们需要能够快速启动并运行新组件。使用 Spring Boot 时，我们可以获得许多开箱即用的功能。这些功能以 Maven 对象的形式提供，你只需要将它们包含在 Maven `pom.xml` 文件中。

下表显示我们将使用的 Spring Boot 提供的一些重要启动项目（starter projects）：

| 项目 | 描述 |
| :--- | :--- |
| `spring-boot-starter` | Spring Boot 应用的基础启动器。提供对自动配置和日志的支持。 |
| `spring-boot-starter-web` | 用于构建基于 Spring MVC 的 Web 应用或 RESTful 应用的启动项目。使用 Tomcat 作为默认嵌入式 servlet 容器。 |
| `spring-boot-starter-data-jpa` | 提供对 Spring Data JPA 支持。默认实现是 Hibernate。 |
| `spring-boot-starter-validation` | 提供对 Java Bean Validation API 支持。默认实现是 Hibernate Validator。 |
| `spring-boot-starter-test` | 提供对各种单元测试框架的支持，如 JUnit、Mockito 和 Hamcrest 匹配器 |

还有许多对你可能很有用的项目。我们不会使用它们，但让我们来看看还有哪些可用资源：

| 项目 | 描述 |
| :--- | :--- |
| `spring-boot-starter-web-services` | 用于开发基于 XML 的 Web 服务启动项目 |
| `spring-boot-starter-activemq` | 支持使用 JMS 在 ActiveMQ 上进行基于消息通信 |
| `spring-boot-starter-integration` | 支持 Spring Integration，该框架提供了企业集成模式的实现 |
| `spring-boot-starter-jdbc` | 提供对 Spring JDBC 的支持。默认配置 Tomcat JDBC 连接池 |
| `spring-boot-starter-hateoas` | HATEOAS 代表“超媒体作为应用状态的引擎”。使用 `HATEOAS` 的 RESTful 服务除了数据外，还会返回与当前上下文相关的附加资源链接 |
| `spring-boot-starter-jersey` | JAX-RS 是开发 REST API 的 Java EE 标准。Jersey 是默认实现。该启动项目提供对构建基于 JAX-RS 的 REST API 的支持 |
| `spring-boot-starter-websocket` | `HTTP` 是无状态的。Web sockets 允许服务器和浏览器之间维持连接。该启动项目提供对 Spring WebSockets 的支持 |
| `spring-boot-starter-aop` | 提供对面向切面编程的支持。还提供对 AspectJ 的支持用于高级面向切面编程 |
| `spring-boot-starter-amqp` | 默认值为 `RabbitMQ`，该启动项目提供基于 AMQP 的消息传递 |
| `spring-boot-starter-security` | 该启动项目启用 Spring Security 的自动配置 |
| `spring-boot-starter-batch` | 提供使用 Spring Batch 开发批应用的支持 |
| `spring-boot-starter-cache` | 使用 Spring Framework 进行缓存的基础支持 |
| `spring-boot-starter-data-rest` | 使用 Spring Data REST 暴露 REST 服务的支持 |

让我们使用这些优秀工具来编写自己的 Spring Boot 微服务。

## 编写 Spring Boot 微服务

我们知道可以使用可用启动器，所以让我们利用它们来节省一些时间。我们将创建的服务将是一个简单的 REST 微服务，用于从数据库中存储和检索实体：在我们的案例中是书籍（books）。为了让它尽可能整洁简单，我们不打算实现身份验证和安全功能。书籍将存储在内存中的关系型数据库 H2 中。我们将使用 Maven 构建并运行我们的书店，因此让我们先从 `pom.xml` 构建文件开始。

## Maven 构建文件

如你所见，我们自己服务的父项目是 `spring-boot-starter-parent`。Spring 这是为基于 Spring Boot 应用提供依赖和插件管理的父项目。这为我们提供了许多可用功能。我们还包含了两个启动器：

- `spring-boot-starter-web`：这是因为我们要创建请求映射，类似于我们之前使用 JEE7 JAX-RS 通过 `@Path` 注解实现的 `@GET` 或 `@POST` 映射
- `spring-boot-starter-data-jpa`：因为我们要将书籍存储在内存 H2 数据库中

启动器（starters）是为不同目的定制的简化依赖描述符。例如，`spring-boot-starter-web` 是用于构建 Spring MVC Web 应用的启动器。它使用 Tomcat 作为默认嵌入式容器。我们还包含了 Spring Boot Maven 插件，它允许我们在不构建 JAR 或 WAR 的情况下直接运行应用程序，或者为未来的部署准备 JAR 或 WAR 文件。我们完整的 `pom.xml` 应该如下所示：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>pl.finsys</groupId>
    <artifactId>rest-example</artifactId>
    <version>0.1.0</version>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.2.RELEASE</version>
    </parent>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-validator</artifactId>
        </dependency>
        <dependency>
            <groupId>org.hsqldb</groupId>
            <artifactId>hsqldb</artifactId>
            <scope>runtime</scope>
        </dependency>

        <!--test dependencies-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>com.jayway.jsonpath</groupId>
            <artifactId>json-path</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <properties>
        <java.version>1.8</java.version>
    </properties>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

    <repositories>
        <repository>
            <id>spring-releases</id>
            <url>https://repo.spring.io/libs-release</url>
        </repository>
    </repositories>

    <pluginRepositories>
        <pluginRepository>
            <id>spring-releases</id>
            <url>https://repo.spring.io/libs-release</url>
        </pluginRepository>
    </pluginRepositories>
</project>
```



首先，在`pom.xml`文件中，我们定义了父 Maven 依赖。由于我们的应用程序是一个 Spring Boot 应用，因此我们从`spring-boot-starter-parent`依赖继承`pom.xml`。这让我们开箱即用地获得所有 Spring Boot 的优秀特性，例如启动机制、依赖注入等。通过添加`spring-boot-starter-data-jpa`作为依赖，我们将能够使用所有与数据库相关的功能，例如 JDBC 事务管理、用于实体类的 JPA 注解等。准备好`pom.xml`后，让我们继续定义微服务的入口点。

### 应用入口点

我们的应用程序入口点将命名为`BookStoreApplication`，文件名为`BookstoreApplication.java`：

```java
package pl.finsys.example; 

import org.springframework.boot.SpringApplication; 
import org.springframework.boot.autoconfigure.SpringBootApplication; 

@SpringBootApplication 
public class BookstoreApplication { 

    public static void main(final String[] args) { 
        SpringApplication.run(BookstoreApplication.class, args); 
    } 
} 
```

就这些。总共九行代码（不计空行）。没有更简洁的了。`@SpringBootApplication`是一种快捷注解，非常方便。它替换了以下所有的注解：

- `@Configuration`：标记有此注解的类将成为应用程序上下文 Bean 定义的源。
- `@EnableAutoConfiguration`：此注解让 Spring Boot 根据类路径设置、其他 Bean 以及各种属性设置添加 Bean。
- `@EnableWebMvc`：通常你会在 Spring MVC 应用中添加这一个，但 Spring Boot 在类路径上看到`spring-webmvc`时会自动添加它。它将应用程序标记为 Web 应用程序，从而会激活诸如设置`DispatcherServlet`等关键行为。
- `@ComponentScan`：告诉 Spring 去寻找其他组件、配置和服务，允许它找到控制器。

到目前为止一切顺利。我们需要为我们的服务准备一些模型。我们将在数据库中保存一些实体；这正是`spring-boot-starter-data-jpa`启动器大派上用场的地方。我们将能够使用 JPA（用 Hibernate 实现）和`javax.api`。

### 领域模型和存储库

我们服务中的领域模型将是`Book`类，定义在`Book.java`中：

```java
package pl.finsys.domain;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Id;
import javax.validation.constraints.NotNull;
import javax.validation.constraints.Size;

@Entity
public class Book {

    @Id
    @NotNull
    @Column(name = "id")
    private Long id;

    @NotNull
    @Size(max = 64)
    @Column(name = "author")
    private String author;

    @Size(max = 64)
    @Column(name = "title")
    private String title;

    public Book() {
    }

    public Book(Long id, String author, String title) {
        this.id = id;
        this.title = title;
        this.author = author;
    }

    public Long getId() {
        return id;
    }

    public String getAuthor() {
        return author;
    }

    public String getTitle() {
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    @Override
    public String toString() {
        return "Book{" +
                "id=" + id +
                ", author='" + author + '\'' +
                ", title='" + title + '\'' +
                '}';
    }
}
```

如上一个列表所示，`Book`类是一个简单的 POJO，带有一些注解、属性、getter 和 setter。`@Entity`注解来自`javax.persistence`包，并将 POJO 标记为数据库实体，以便 JPA 从 H2 数据库存储或检索它。`@Column`注解指定了存储对应属性的列名。`@NotNull`和`@Size`注解确保我们的实体进入数据库之前具有正确的值。

我们已经定义了实体；现在需要一种在数据库中读取和存储它的机制。我们将使用 Spring 的`JpaRepository`来实现。我们的存储库命名为`BookRepository`，位于`BookRepository.java`文件中：

```java
package pl.finsys.example.repository; 

import pl.finsys.example.domain.Book; 
import org.springframework.data.jpa.repository.JpaRepository; 

public interface BookRepository extends JpaRepository<Book, Long> { 
}
```

Spring Data JPA 提供了一种存储库编程模型，从每个托管领域对象的接口开始。

定义此接口有两个目的。首先，通过扩展`JpaRepository`接口，我们为类型获得了一系列通用的 CRUD 方法，允许我们保存实体、删除实体等。例如，以下方法是可用（在我们扩展的`JPARepository`接口中声明）：

- `findAll()`
- `findAll(Sort sort)`
- `findAll(Iterable<ID> ids)`
- `<S extends T> List<S> save(Iterable<S> entities)`
- `getOne(ID id)`
- `<S extends T> S save(S entity)`
- `<S extends T> Iterable<S> save(Iterable<S> entities);`
- `T findOne(ID id);`
- `boolean exists(ID id);`
- `Iterable<T> findAll();`
- `Iterable<T> findAll(Iterable<ID> ids);`
- `long count();`
- `void delete(ID id);`
- `void delete(T entity);`
- `void delete(Iterable<? extends T> entities);`
- `void deleteAll();`

不需要 SQL 编码，不需要 JPA-QL 查询，什么都不需要。只需扩展 Spring`JPARepository`接口，所有这些方法都可以使用。当然，我们不仅限于这些方法。我们可以在接口中声明自己的方法，例如`findByTitle(String title)`。Spring 会在运行时识别它，并根据标题为我们找到书籍。我强烈建议阅读 Spring Data 项目文档并进行更多实验；它非常方便使用。

直接在控制器中使用`entity`仓库通常不是一种好的做法，因此是时候创建一个书籍服务了。它将是一个定义在`BookService.java`中的`BookService`接口：

```java
package pl.finsys.example.service; 

import pl.finsys.example.domain.Book; 
import javax.validation.Valid; 
import javax.validation.constraints.NotNull; 
import java.util.List; 

public interface BookService { 
    Book saveBook(@NotNull @Valid final Book book); 
    List<Book> getList(); 
    Book getBook(Long bookId); 
    void deleteBook(final Long bookId); 
} 
```

实现部分在`BookServiceImpl.java`中可以如下所示：

```java
package pl.finsys.example.service; 

import org.springframework.beans.factory.annotation.Autowired; 
import pl.finsys.example.domain.Book; 
import pl.finsys.example.repository.BookRepository; 
import pl.finsys.example.service.exception.BookAlreadyExistsException; 
import org.slf4j.Logger; 
import org.slf4j.LoggerFactory; 
import org.springframework.stereotype.Service; 
import org.springframework.transaction.annotation.Transactional; 
import org.springframework.validation.annotation.Validated; 

import javax.validation.Valid; 
import javax.validation.constraints.NotNull; 
import java.util.List; 

@Service 
@Validated 
public class BookServiceImpl implements BookService { 

    private static final Logger LOGGER = LoggerFactory.getLogger(BookServiceImpl.class); 
    private final BookRepository repository; 

    @Autowired 
    public BookServiceImpl(final BookRepository repository) { 
        this.repository = repository; 
    } 

    @Override 
    @Transactional 
    public Book saveBook(@NotNull @Valid final Book book) { 
        LOGGER.debug("Creating {}", book); 
        Book existing = repository.findOne(book.getId()); 
        if (existing != null) { 
            throw new BookAlreadyExistsException( 
                    String.format("There already exists a book with id=%s", book.getId())); 
        }
        return repository.save(book);
    }

    @Override 
    @Transactional(readOnly = true)
    public List<Book> getList() { 
        LOGGER.debug("Retrieving all books"); 
        return repository.findAll(); 
    }

    @Override 
    @Transactional(readOnly = true)
    public Book getBook(Long bookId) { 
        return repository.findById(bookId).orElse(null);
    }

    @Override 
    @Transactional 
    public void deleteBook(final Long bookId) { 
        LOGGER.debug("Deleting book with id {}", bookId);
        repository.deleteById(bookId);
    } 
}
```

与 JAX-RS 类似，使用`@PathParam`和`@QueryParam`来指定控制器方法的输入参数，现在在 Spring 中我们有了`@PathVariable`和`@RequestParam`。如果你需要让方法参数从请求体中获取（作为一个你想要保存的整个 JSON 对象，与我们的`saveBook()`方法相同），将需要使用`@RequestBody`注解对参数进行映射。至于输出，`@ResponseBody`注解可以告诉我们的控制器，方法的返回值应该绑定到 Web 响应体中。

在真实世界的服务中，你可能会有很多控制器映射了许多路径。当向世界开放此类服务时，记录该服务的 API 文档通常是一项良好的做法。此 API 文档就是服务契约。手动执行这些可能是一个繁琐的过程。此外，如果你进行了更改，保持 API 文档同步是很有用的。有一个工具可以让这变得简单得多，那就是 Swagger。

### 文档 API

在客户端使用服务之前，它需要一个服务契约。服务契约定义了服务的所有细节；例如，如何调用服务、服务的 URI 以及请求和响应的格式是什么。你的客户端需要知道如何与你的 API 交互。在过去的几年里，在主要供应商的支持下，Swagger 正在获得大量的关注。Swagger 规范以 JSON 格式呈现了你服务资源和操作的所有细节。该规范的格式被称为 OpenAPI 规范（Swagger RESTful API 文档规范）。它是人类和机器可读的，易于解析、传输和在集成中使用。可以使用`SpringFox`库从 RESTful 服务代码生成 Swagger 文档。此外，还有一个名为 Swagger UI 的优秀工具，集成到应用程序中，它可以提供人类可读的文档。在本节中，我们将为服务生成 Swagger 文档。`SpringFox`库可以在 GitHub 的`http://springfox.github.io/springfox/`以及 Maven 中央仓库获取，它是一个为使用 Spring 构建的 API 自动构建 JSON API 文档的工具。更棒的是，该库提供了 Swagger UI 工具。该工具将与你的服务一起部署，并可以使用方便的方式浏览生成的 API 文档。让我们把 Swagger 引入我们的服务。我们首先向服务的`pom.xml`文件中添加必要的依赖：

```xml
<dependency> 
   <groupId>io.springfox</groupId> 
   <artifactId>springfox-swagger2</artifactId> 
   <version>2.6.1</version> 
</dependency>

<dependency> 
   <groupId>io.springfox</groupId> 
   <artifactId>springfox-swagger-ui</artifactId> 
   <version>2.5.0</version> 
</dependency> 
```

在应用程序的类路径中拥有该库后，我们需要开启它。下一步是添加配置类来启用并生成 Swagger 文档。我们通过创建一个带有 Spring`@Configuration`注解的类来实现，如下例所示：



```java
package pl.finsys.example.configuration;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import springfox.documentation.builders.PathSelectors;
import springfox.documentation.builders.RequestHandlerSelectors;
import springfox.documentation.spi.DocumentationType;
import springfox.documentation.spring.web.plugins.Docket;
import springfox.documentation.swagger2.annotations.EnableSwagger2;

@Configuration
@EnableSwagger2
public class SwaggerConfig {
    @Bean
    public Docket api() {
        return new Docket(DocumentationType.SWAGGER_2)
                .select()
                .apis(RequestHandlerSelectors.any())
                .paths(PathSelectors.any()).build();
    }
}
```

这里有几点说明。`@Configuration` 被注解的类定义了一个 Spring 配置，`@EnableSwagger2` 开启 Swagger 支持。`Docket` 是一个用于配置生成 Swagger 文档的构建器，配置为 `DocumentationType.SWAGGER_2` 以生成 Swagger 2 兼容的 API 文档。在 `Docket` 实例上调用的 `select()` 方法返回一个 `ApiSelectorBuilder`，它提供了 `apis()` 和 `paths()` 方法，使用字符串谓词过滤被记录的控制器和方法。在我们的示例中，我们希望所有的控制器和所有映射路径都被记录；这就是为什么我们使用 `.apis(RequestHandlerSelectors.any()).paths(PathSelectors.any())`。

你也可以使用传递给 `paths()` 的 `regex` 参数来提供额外的过滤器，仅为匹配正则表达式的路径生成文档。

就这些；这是为你的 API 生成文档最简单的形式。如果你现在运行服务（我们稍后会这样做），将有两个端点可用：

- `http://localhost:8080/v2/api-docs`
- `http://localhost:8080/swagger-ui.html`

第一个包含 Swagger 2 兼容的文档，采用 JSON 格式，如下面的截图所示：

![](img/Image00061.jpg)

要以更有用的形式浏览 API 文档，请将浏览器指向第二个 URL。你将看到 Swagger UI 工具界面：

![](img/Image00062.jpg)

Swagger UI 是 HTML、JavaScript 和 CSS 资源的集合，可以从符合 Swagger 规范的 API 动态生成精美的文档。它列出了你的服务操作以及请求和响应格式。最棒的是，你可以使用这个工具通过执行特定请求来测试服务。事实上，它是快速测试服务的极佳工具。我们的文档目前并不详细。当然，我们可以通过一些细节来增强文档。我们可以这样做，有很多 Java 注解可以在服务代码中使用来增强生成的文档。这些注解来自 `swagger-annotation` 包，如果你使用了 `springfox-swagger2` 库就可以可以使用它们。例如，考虑以下代码段：

```java
@ApiOperation(value = "Retrieve a list of books.",
responseContainer = "List")
@RequestMapping(value = "/books", method = RequestMethod.GET, produces = {"application/json"})
public List<Book> listBooks() {
    LOGGER.debug("Received request to list all books");
    return bookService.getList();
}
```

在前面的代码中，我们使用 `@ApiOperation` 注解对该操作提供了更详细的描述。还有很多：用于描述参数的 `@ApiImplicitParam`，提供在此资源/操作使用的授权方案名称的 `@Authorization`，提供许可证信息的 `@License` 等。所有这些注解都会被 `springfox-swagger2` 识别并用于增强生成的文档。我强烈建议查看 `swagger-annotations` 的 JavaDoc；你将能够以详细、专业的方式记录你的 API。

我想我们的小服务已经准备好了；现在是让它运行起来了。

### 运行应用程序

由于我们在 `pom.xml` 构建文件中定义了 Spring Boot 插件，我们现在可以使用 Maven 启动应用程序。你只需要在系统路径中有 Maven，但作为一名 Java 开发者，你可能已经拥有它了。要运行应用程序，请在命令行（macOS 终端或 Windows 上的 `cmd.exe`）中执行以下命令：

```bash
$ mvn spring-boot:run
```

过了一会儿，Spring 的启动日志将出现在控制台中，你的微服务就准备好接受 `HTTP` 请求了。很快，在第 5 章《使用 Java 应用创建镜像》中，我们的目标是从 Docker 容器中看到同样的结果：

![](img/Image00063.jpg)

如果你愿意，也可以直接从 IDE 运行应用程序，无论是 IntelliJ IDEA、Eclipse 还是 Netbeans。我们的 `BookstoreApplication` 类有一个 `main()` 方法；你只需要在你的 IDE 中创建一个运行时配置并运行它即可。这与 JEE7 JAX-RS 服务不同。在那种情况下，你将将服务部署到符合 JEE 标准的应用程序服务器中才能运行它。在调试你的服务时，拥有 `main()` 方法非常方便。只需以 `BookstoreApplication` 为入口点启动调试会话即可。不需要创建远程调试会话。等我们的服务运行起来，是时候对其暴露的端点进行一些调用了。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

### Making calls

可以使用任何可以执行 `HTTP` 请求的工具或库对服务暴露的操作进行调用。第一个显而易见的选择就是 Web 浏览器。但浏览器仅适用于执行 `GET` 请求（例如从我们的书店服务获取书籍列表）。如果你需要执行其他方法（如 `POST` 或 `PUT`）或提供额外的请求参数、头部值等，你将需要使用一些替代方案。首选可能是 `cURL`，这是一种使用各种协议传输数据的命令行工具。让我们看看我们拥有的其他选项。

### Spring RestTemplate

如果你需要从另一个服务调用服务，你需要一个 `HTTP` 客户端。Spring 提供了非常有用的 `RestTemplate` 类。它为你提供了同步的客户端 `HTTP` 访问，简化了与 HTTP 服务器的通信，并强制执行 RESTful 原则。它处理 HTTP 连接，让应用程序代码提供 URL（带有可能的模板变量）并提取结果。默认情况下，`RestTemplate` 依赖标准的 JDK 设施来建立 HTTP 连接。你可以通过 `setRequestFactory()` 方法切换到你喜欢的其他 HTTP 库，例如 Apache `HttpComponents`、`Netty` 和 `OkHttp`。调用 `REST` 资源获取 `ID = 1` 的书籍可以如下：

```java
package pl.finsys.example.client;

import org.springframework.http.ResponseEntity;
import org.springframework.web.client.RestTemplate;
import pl.finsys.example.domain.Book;

public class ExampleClient {
    public static void main(String[] args) {
        try {
            RestTemplate restTemplate = new RestTemplate();
            ResponseEntity<Book> response = restTemplate.getForEntity("http://localhost:8080/books/1", Book.class);
            System.out.println(response.getBody());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

当然，这只是一个简化的客户端示例，用于向你展示思路。你可以使用 `RestTemplate` 为 REST 资源创建更复杂的客户端调用。

### HTTPie

`cURL` 的一个很好的命令行替代方案是 `HTTPie`，可以在 [`httpie.org`](https://httpie.org)。它是一个命令行 `HTTP` 客户端。幸运的是，名字中的 `ie` 并不是来自 Internet Explorer。如果你喜欢在 shell 或命令行中工作，`HTTPie` 是一个单一命令，为 cURL 增加了以下功能：合理的默认值、表达性且直观的命令语法、彩色且格式化的终端输出、内置 JSON 支持、持久会话、表单和文件上传、代理和认证支持，以及对任意请求数据和头的支持。它用 Python 编写，适用于 Linux、macOSX 和 Windows。

### Postman

Postman 是许多开发者的首选工具。它可以作为 Chrome 插件或 [`www.getpostman.com`](https://www.getpostman.com) 独立程序可用。Postman 使用非常方便。它是一个强大的 GUI 平台，可以让你的 API 开发更快、更简单，从构建 API 请求到测试、文档和共享。你可以保存 `HTTP` 请求以备后用，并将它们组织在集合（collections）中。如果你在多个环境中工作（例如在开发服务时使用 localhost，之后使用生产环境），Postman 引入了环境（environments）的概念。环境允许你使用变量来定制请求。这样，你就可以在不更改请求的情况下轻松切换不同的设置。每个环境都表示为一组键值对。这使得在多个环境之间工作变得简单。它还有一个非常实用的 UI 来编辑你的 `HTTP` 请求：

![](img/Image00064.jpg)

你可以定义请求头、cookies 和正体。如果你的服务支持认证，Postman 包含了许多认证助手：它可以支持 basic Auth、digest Auth 和 OAuth。响应体可以在三种视图之一中查看：pretty（美化）、raw（原始）和 preview（预览）。pretty 模式对 JSON 或 XML 响应进行格式化，使其更容易查看，且头会在头部标签页中以键/值对的形式显示。它是一个非常强大且易用的工具。如果你在 macOS 上工作，还有更更好的选择。

### Paw for Mac

**Paw** 是一个功能齐全的 `HTTP` 客户端，让你测试你构建或使用的 API。它拥有精美的原生 OS X 界面，用于组合请求、检查服务器响应并直接生成客户端代码。正如接下来的截图所示，它还包含一个强大的编辑器来组合你的请求：

![](img/Image00065.jpg)

它还支持许多认证方案，包括 OAuth 1 和 2、Basic Auth、Digest Auth、Hawk、AWS Signature Version 4 和 Amazon S3。与 Postman 类似，Paw 也允许你通过文件夹组织请求。你还可以快速定义和切换不同的环境。有趣的功能是，Paw 可以生成执行你请求的客户端代码。它可以为 `cURL`、`HTTPie`、Objective-C、Python、JavaScript、Ruby、PHP、Java、Go 等许多语言生成代码。你猜怎么着？Paw 还可以导入我们一直在讨论的 Swagger 文档。你可以使用此功能来测试你收到的服务。

如果你需要快速启动新服务，有一些工具可能会很有帮助。其中之一是 **Initializr**。

### Spring Initializr

Spring Initializr 是一个基于 Web 的工具，可以在 [`start.spring.io`](https://start.spring.io) 获取。它是 Spring 项目的快速启动器。Spring Initializr 可以以下方式使用：

- 从浏览器 [`start.spring.io`](https://start.spring.io)
- 在你的 IDE 中（IntelliJ IDEA Ultimate 或 NetBeans，使用插件）
- 从命令行使用 Spring Boot CLI 或简单的使用 `cURL` 或 `HTTPie`

使用 Web 应用非常方便；你只需要提供关于应用程序的 Maven 模板详细信息，例如组、制品名称、描述等：

![](img/Image00066.jpg)

在依赖（Dependencies）部分中，你可以输入想要包含的功能关键词，例如 JPA、web 等。你还可以将 UI 切换到高级视图，以便列出所有功能并等待选择：

![](img/Image00067.jpg)

作为输出，Spring Initializr 将创建一个包含你想要启动的基础 Maven 项目的 ZIP 压缩包。由 Spring Initializr 创建的是 Maven 项目，并遵循标准的 `Maven` 目录布局。这在创建新的 Spring 项目时确实节省了大量时间。你不再需要搜索特定的 Maven 模板（archetypes）并查找它们的版本。Initializr 会自动为你生成 `pom.xml`。`pom.xml` 中依赖的存在非常重要，因为 Spring Boot 会在类路径上发现某些内容时，自动做出创建内容的决策。例如，如果应用程序运行时存在 H2 数据库的依赖且位于类路径中，Spring Boot 将自动创建一个数据连接和一个嵌入式 H2 数据库。

### 总结

如你所见，开发 Java 微服务并没有听起来有那么复杂。你可以在 JEE7 JAX-RS 或 Spring Boot 之间进行选择，连接一些类，一个基础服务就准备好了。你并不局限于使用 Spring MVC 来创建 REST 端点。如果你更熟悉 Java EE JAX-RS 规范，可以轻松地将 JAX-RS 集成到 Spring 应用中，特别是 Spring Boot 应用。然后你可以从两者中各取所长。

当然，在现实世界中，你可能还会包含一些更高级的功能，如身份验证和安全性。可以使用 Spring Initializr 在开发自己的服务时提供显著的速度提升。在第 5 章《使用 Java 应用创建镜像》中，我们将把书店服务打包成 Docker 镜像并使用 Docker Engine 运行它。

## 使用 Java 应用创建镜像

现在我们已经有了一个基于 Spring Boot 的简单但功能完整的 Java 微服务，我们可以更进一步。在用 Kubernetes 部署它之前，让我们将其打包为 Docker 镜像。在本章中，我们将创建一个包含应用程序的 Docker 镜像，并将 Spring Boot 应用 Docker 化，以运行在隔离的环境（即容器）中。

本章涵盖的主题有：

- 创建 `Dockerfile`
- `Dockerfile` 指令
- 构建镜像
- 创建和删除镜像

让我们从 `Dockerfile` 的定义开始，它将是我们容器的定义。

### Dockerfile

正如你在第 1 章《Docker 简介》中所记得的，`Dockerfile` 某种程度上是一个构建镜像的配方。它是一个纯文本文件，包含由 Docker 按其放置顺序执行的指令。每个 `Dockerfile` 都有一个基础镜像，Docker 引擎将在此基础上进行构建。生成的镜像是文件系统的特定状态：它是运行中容器的只读、冻结且不可变的快照，由多个代表文件系统在不同时间点变化的层组成。

Docker 中的镜像创建流程非常简单，基本上由两个步骤组成：

1. 首先，你准备一个名为 `Dockerfile` 的文本文件，其中包含了一系列关于如何构建镜像的。在 `Dockerfile` 中可以使用的指令范围并不广，但足以完全指示 Docker 如何创建镜像。
2. 接下来，你执行 `docker build` 命令，根据刚刚创建的 `Dockerfile` 创建一个 Docker 镜像。`docker build` 命令在上下文（context）中运行。构建上下文是指定位置的文件，可以是 `PATH` 或 URL。`PATH` 是你本地文件系统上的目录，而 URL 是 Git 仓库地址。上下文是进行递归处理的。`PATH` 将包含任何子目录。URL 将包含仓库及其子模块。



如果你创建一个包含 Java 应用的镜像，你也可以跳过第二步，并利用可用的 Docker Maven 插件之一。在我们学习了如何使用`docker build`命令构建镜像后，我们还将使用 Maven 创建镜像。当使用 Maven 构建时，提供给`docker build`命令的上下文（在这种情况下为构建过程）将由 Maven 自动提供。实际上，完全不需要`Dockerfile`，它会在构建过程中自动创建。我们稍后会介绍这一点。

`Dockerfile`的标准名称就是`Dockerfile`。它只是一个纯文本文件。取决于你使用的 IDE，有插件可以提供 Dockerfile 语法高亮和自动补全，这使得编辑变得非常轻松。`file`指令使用简单清晰的语法，使得它们非常易于理解、创建和使用。它们被设计为自解释的，特别是因为它们允许像编写良好的应用程序源码一样进行注释。现在让我们认识`Dockerfile`指令。

## Dockerfile 指令

我们将从每个 Dockerfile 必须位于顶部的指令开始，即`FROM`指令。

### FROM

这是`Dockerfile`中的第一条指令。它为文件中接后的每一个指令设置基础镜像。`FROM`指令的语法非常简单，只需：

`FROM <image>`，或`FROM <image>:<tag>`，或`FROM <image>@<digest>`。

`FROM`指令接受`tag`或`digest`作为参数。如果你决定跳过它们，Docker 将假设你想要从`latest`标签构建镜像。请注意，`latest`并不总是你想要构建的基础镜像的最新版本。`latest`标签是一种特殊的标签。此外，它的作用可能不像你预期的那样工作。简而言之，除非镜像创建者（例如`openjdk`或`fabric8`）有特定的`build`、`tag`和`push`模式，否则`latest`标签并没有任何特殊含义。分配给镜像的`latest`标签仅意味着它是最后一次在指定标签的情况下构建并执行的镜像。这可能会引起误解，拉取标记为`latest`的镜像不会获取软件的最新版本。

Docker 不会在拉取标记为`latest`的镜像时检查是否为最新版本。如果找不到提供的标签或摘要，Docker 将在构建期间报错。你应该明智地选择基础镜像。我的建议是始终优先选择 Docker Hub 官方仓库。通过选择官方镜像，你可以确保它是高质量、经过测试、支持且维护的。

对于 Java 应用的容器化，我们有两种选择。第一种是使用基础 Linux 镜像并使用`RUN`指令安装 Java（稍后我们将介绍`RUN`）。第二种选择将拉取一个已经安装了 Java 运行时的镜像。在这里你有更多选择。例如：

- `openjdk`：包含 Java 平台标准版开源实现的官方仓库。`latest`标签（未指定任何标签时将使用的标签）在本书编写时指向`8u121-alpine` OpenJDK 版本。

- `fabric8/java-alpine-openjdk8-jdk`：该基础镜像实际上也被 fabric8 Maven 插件使用。

- `frolvlad/alpine-oraclejdk8`：三个标签可以选择：`full`（仅删除了源码 tar 包）、`cleaned`（清理了桌面部分）、`slim`（删除了编译器和 JVM 外的所有内容）。`latest`标签指向`cleaned`版本。

- `jeanblanchard/java`：基于 Alpine Linux 的镜像，以保持最小体积（约为 Ubuntu 镜像的 25%）。`latest`标签指向 Oracle Java 8 (Server JRE)。

通过在[`hub.docker.com`](https://hub.docker.com)的 Docker Hub 上注册并创建账户，你可以访问 Docker Store。它可以在[`store.docker.com`](https://store.docker.com)访问。尝试在 Docker Store 中搜索与 Java 相关的镜像。你会发现有很多非常有用的镜像可以选择，其中之一就是官方的 Oracle Java 8 SE (Server JRE) 镜像。该 Docker 镜像提供了 Server JRE，这是一个专门针对在服务器环境中部署 Java 的运行时环境。Server JRE 包含了 JVM 监控工具以及服务器应用程序通常所需的工具。你可以通过 Docker Store 购买此官方 Java Docker 镜像。点击 Get Content，它的价格为 $0.00，因此它可以免费供你的开发目的之用。

请注意，来自 Docker Store 的镜像与你的 Docker Hub 账户绑定。在拉取这些镜像或使用它们作为基础镜像构建自己的镜像之前，你需要使用`docker login`命令和你的 Docker Hub 凭据对 Docker Store 进行身份验证。

为了我们的目的，让我们选择`jeanblanchard/java`。它是运行在 Alpine Linux 发行版之上的官方 Oracle Java。基础镜像很小且下载速度快。我们的`FROM`指令看起来如下：

```
FROM jeanblanchard/java:8 
```

如果在你的 Docker 宿主机（例如在你的本地机器）上没有找到`FROM`镜像，Docker 将尝试从 Docker Hub（或你设置的私有仓库）中查找并拉取它。`Dockerfile`中的所有后续指令将使用`FROM`中指定的镜像作为起始起点。这就是为什么它是强制性的；一个有效的`Dockerfile`必须在顶部包含它。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载

- 书单分享

- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载

- 电子书打包资源分享

- 学习资源分享

### MAINTAINER

通过使用`MAINTAINER`指令，你设置了生成镜像的`Author`（作者）字段。可以是你的名字、用户名，或任何你想作为通过你编写的`Dockerfile`创建的镜像的作者的内容。此命令可以放在`Dockerfile`的任何位置，但良好的做法是将其放在文件顶部，紧接`FROM`指令之后。这是一个所谓的“非执行命令”，意味着它不会对生成的镜像产生任何更改。语法再次非常简单：

```
MAINTAINER authors_name 
```

### WORKDIR

`WORKDIR`指令为 Dockerfile 中之后的任何`CMD`、`RUN`、`ENTRYPOINT`、`COPY`和`ADD`指令添加工作目录。该指令的语法为`WORKDIR /PATH.`。如果提供了相对路径，可以在一个 Dockerfile 中使用多个`WORKDIR`指令；它将相对于上一个`WORKDIR`指令的路径。

### ADD

`ADD`基本上的作用是将文件从源复制到容器自身的文件系统中所需的目标位置。它接受两个参数：源（`<source path or URL>`）和目标位置（`<destination path>`）：

```
ADD <source path or URL> <destination path > 
```

源可以有两种形式：它可以是文件路径、目录路径或 URL。该路径相对于构建过程启动的目录（即我们之前提到的构建上下文）。这意味着例如，你不能将`"../../config.json"`放在`ADD`指令的源路径参数中。

源路径目标路径可以包含通配符。这些与传统文件系统相同：`*`表示任何文本字符串，或`?`表示任何单个字符。

例如，`ADD target/*.jar /`将所有以`.jar`结尾的文件添加到镜像文件系统的根目录中。

如果需要，你可以指定多个源路径，并用逗号分隔它们。它们都必须相对于构建上下文，就像你只有一个源路径一样。如果你的源路径或目标路径包含空格，你需要使用一种特殊的语法，在周围添加方括号：

`ADD ["<source path or URL>" "<destination path>"]`

如果源路径不以斜杠结尾，它将被视为单个文件并直接复制到目标位置。如果源路径以斜杠结尾，它将被视为一个目录：它的所有内容将被复制到目标路径中，但目录本身不会在目标路径处创建。所以，如你所见，在向镜像添加文件或目录时，尾部斜杠`/`非常重要。如果源路径指向常用格式（如 ZIP、TAR 等）的压缩存档，它将被解压到目标路径。Docker 不会通过文件名识别存档，它会检查文件的内容。

如果存档损坏或以任何其他方式被 Docker 读取，它将不会被提取，你也不会收到错误消息。文件将直接复制到目标路径。

相同的尾部斜杠规则适用于目标路径；如果它以斜杠结尾，意味着它是一个目录。否则，它将被视为单个文件。这在构建镜像的文件系统内容时为你提供了极大的灵活性；你可以将文件添加到目录，将文件作为单个文件添加（使用相同或不同的名称），或直接添加整个目录。

`ADD`命令不仅用于从本地文件系统复制文件，你还可以用它从网络获取文件。如果源是一个 URL，则 URL 的内容将自动下载并放在目标位置。请注意，从网络下载的文件存档不会被解压。再次，在下载文件时尾部斜杠非常重要；如果目标路径以斜杠结尾，文件将下载到该目录中。否则，下载的文件将以你提供的目标路径作为名称保存。

`<destination directory>`可能是绝对路径或相对于`WORKDIR`指令指定目录的相对路径（我们稍后会介绍）。源（或多个源）将直接复制到指定的目标位置。例如：

- `ADD config.json projectRoot/`将将`config.json`文件添加到`<WORKDIR>/projectRoot/`

- `ADD config.json /absoluteDirectory/`将将`config.json`文件添加到`/absoluteDirectory/`

关于镜像中创建的文件的所有权，它们将始终以用户 ID (`UID`) `0`和组 ID (`GID`) `0`创建。权限将与源文件相同，除非是从远程 URL 下载的文件：在这种情况下，它将获得`600`权限（仅所有者可以读写文件）。如果你需要更改这些值（所有权或权限），你需要在 Dockerfile 中`ADD`指令之后提供更多指令。

如果需要添加到镜像的文件位于需要身份验证的 URL 上，`ADD`指令将无法工作。你需要使用 shell 命令下载文件，例如`wget`或`curl`。

注意，如果不需要`ADD`的特殊功能（如解压存档），则不应使用`ADD`，而应该使用`COPY`。

### COPY

`COPY`指令将新文件或目录从`<source path>`复制添加到容器的文件系统的`<destination path>`路径中。

它与`ADD`指令非常相似，甚至语法也一样：

```
COPY <source path or URL> <destination path > 
```

`ADD`的相同规则也适用于`COPY`：所有源路径必须相对于构建上下文。再次强调，源路径和目标路径末尾斜杠（/）的存在非常重要：如果存在斜杠，则该路径被视为文件；否则，它将被视为目录。

当然，与`ADD`一样，你可以有多个源路径。如果源路径或目标路径包含空格，你需要将它们封装在方括号中：

```
COPY ["<source path or URL>" "<destination path>"] 
```

`<destination path>`是一个绝对路径（如果以斜杠开头），或者相对于`WORKDIR`指令指定的路径的相对路径。

如你所见，`COPY`的功能与`ADD`指令几乎相同，只有一个区别。`COPY`仅支持将本地文件基本复制到容器中。另一方面，`ADD`提供了更多功能，例如解压归档文件、通过 URL 下载文件等。Docker 的最佳实践建议是，如果你不需要`ADD`的这些额外功能，应该优先使用`COPY`。得益于`COPY`命令的透明性，`Dockerfile`将更加简洁且易于理解。

`ADD`和`COPY`指令都有一个共同且重要的方面，即缓存。基本上，Docker 会缓存构建过程中进入镜像的文件。它会检查镜像中一个或多个文件的内容，并为每个文件计算校验和。在缓存查找期间，会将该校验和与现有镜像中的校验和进行比较。如果文件发生了任何变化（如内容和元数据），则缓存将失效。否则，如果源文件没有更改，则将重用现有的镜像层。

如果你有多个 Dockerfile 步骤使用上下文中的不同文件，请逐一`COPY`，而不是一次性全部复制。这将确保只有当特定需要的文件更改时，每个步骤的构建缓存才会失效（强制重新运行该步骤）。

如你所示，`COPY`指令的语法和行为与`ADD`指令几乎相同，但它们的功能集又有所不同。对于不需要`ADD`归档解压或从 URL 获取功能的文件和目录，你应该始终使用`COPY`。

### RUN

`RUN`指令是`Dockerfile`的核心执行指令。本质上，`RUN`指将在当前镜像之上的新层中执行命令（或多个命令），然后提交结果。生成的提交镜像将作为`Dockerfile`中下一条指令的基础。正如你从第一章 *Docker 简介* 中记得的，分层是 Docker 的核心概念。`RUN`以命令为参数并运行它以创建新层。

这意味着`COPY`和`ENTRYPOINT`设置的参数可以在运行时被覆盖，因此如果你在启动容器后没有更改任何内容，结果将始终相同。然而，`RUN`将在构建时执行，无论你在运行时做什么，它的影响都会存在。

为了让你的 Dockerfile 具具可读性并易于维护，你可以使用反斜杠将长或复杂的`RUN`语句拆分为多行。

`Dockerfile`中的`RUN`命令将按照它们在文件中出现的顺序执行。

每个`RUN`指令都会在镜像中创建一个新层。

正如你从第一章 *Docker 简介* 中熟悉的，层会被 Docker 缓存和重用。`RUN`指令的缓存在此下次构建期间不会自动失效。例如，与`RUN apt-get upgrade -y`相同的指令缓存将在下次构建期间被重用。为什么缓存很重要？在大多数情况下，缓存是非常有利的，可以在构建镜像时为你节省大量时间。它让构建新容器变得真的、非常快。然而，有一个警告。有时缓存可能是危险的，并产生意之外的结果。缓存在构建过程中被大量使用，当你想要`RUN`命令的更新输出进入新容器时，这可能会导致问题。如果`RUN`命令在两次构建之间没有变化，Docker 的缓存就不会失效。实际上，Docker 将重用缓存中之前的结果。这显然是有害的。想象一种情况：你使用`RUN`命令从 Git 仓库拉取源代码，将`git clone`作为构建镜像的第一步。

请注意 Docker 缓存何时需要失效，否则你的镜像构建将得到意之外的结果。

这就是为什么了解如何选择性地失效缓存是很好的。在 Docker 世界中，这被称为缓存破解（cache busting）。

考虑以下示例。`RUN`最常见的用例可能是应用`apt-get`，这是 Ubuntu 上用于下载软件包的包管理器命令。假设我们有如下 Dockerfile，用于安装 Java 运行时：

```
FROM ubuntu 
RUN apt-get update 
RUN apt-get install -y openjdk-8-jre 
```

如果从此`Dockerfile`构建镜像，两个`RUN`指令的所有层都将被放入层缓存中。但过段时间后你决定在镜像中需要`node.js`包，现在 Dockerfile 看起来像这样：

```
FROM ubuntu 
RUN apt-get update 
RUN apt-get install -y openjdk-8-jre 
RUN apt-get install -y nodejs 
```

如果你第二次运行`docker build`，Docker 将重用缓存中的层。结果是`apt-get update`将不会执行，新创建的镜像可能包含过版本的`java`和`node.js`软件包。在创建`RUN`指令时，你应该始终牢记缓存的概念。在我们的示例中，我们应该始终将`RUN apt-get update`与`apt-get install`结合在同一个`RUN`语句中这将只创建一个层；例如：

```
RUN apt-get update \
&& apt-get install -y openjdk-8-jre \
&& apt-get install -y nodejs \
&& apt-get clean 
```

不仅如此，你还可以使用一种称为“版本锁定”（version pinning）的技巧来避免缓存问题。这仅仅是为你想要安装的包提供一个特定的、具体的版本。

### CMD

`CMD`指令的目的是为执行的容器提供默认值。你可以将`CMD`指令视为你镜像的起点，当容器稍后运行时。这可以是一个可执行文件，或者，如果你指定了`ENTRYPOINT`指令（我们将在下文介绍），你可以省略可执行文件并仅提供默认参数。`CMD`指令的语法有两种形式：

- `CMD ["executable","parameter1","parameter2"]`：这是所谓的`exec`形式。这也是首选且推荐的形式。参数是 JSON 数组，需要封装在方括号中。重要的注释是`exec`形式在运行容器时不调用命令 shell。它只运行作为第一个参数提供的可执行文件。如果`Dockerfile`中存在`ENTRYPOINT`指令，`CMD`为`ENTRYPOINT`指令提供一组默认参数。



- `CMD command parameter1 parameter2`：这是指令的 shell 形式。这一次，shell（如果镜像中存在）将处理提供的命令。指定的二进制文件将通过调用 `/bin/sh -c` shell 来执行。这意味着如果你显示容器的主机名，例如使用指令的 shell 形式 `CMD echo $HOSTNAME`，你应该使用 shell 形式。

我们之前提到过，推荐的 `CMD` 指令形式是 `exec` 形式。原因如下：通过 shell 启动的一切都将作为 `/bin/sh -c` 的子命令运行，而它不会传递信号。这意味着可执行文件将不会是容器的 PID 1，且不会接收 Unix 信号，因此你的可执行文件无法接收来自 `docker stop <container>` 的 `SIGTERM` 信号。另一个缺点是：你需要在容器中包含一个 shell。如果你正在构建一个最小化镜像，它不需要包含 shell 二进制文件。使用 shell 形式的 `CMD` 指令将直接失败。

当 Docker 执行命令时，它不会检查容器内部是否存在 shell。如果镜像中没有 `/bin/sh`，容器将无法启动。

另一方面，如果我们将 `CMD` 更改为 `exec` 形式，Docker 将尝试寻找一个名为 `echo` 的可执行文件，这显然会失败，因为 `echo` 是一个 shell 命令。

由于 `CMD` 等于 Docker 引擎运行容器时启动的起点，因此一个 Dockerfile 中只能有一个 `CMD` 指令。

如果 Dockerfile 中有多个 `CMD` 指令，只有最后一个会生效。

你可能注意到 `CMD` 指令与 `RUN` 非常相似。它们都可以运行任何命令（或应用程序）。但存在一个关键的区别：执行时机。通过 `RUN` 指令提供的命令在构建期间执行，而通过 `CMD` 指令指定的命令是在通过 `docker run` 启动新创建的镜像时执行的。与 `CMD` 不同，`RUN` 指令实际上是用于构建镜像的，通过在之前提交的层之上创建一个新层来实现。

`RUN` 是一个构建时指令，而 `CMD` 是一个运行时指令。

信不信由，我们现在可以将我们的 REST 示例微服务容器化了。让我们通过对第 4 章“创建 Java 微服务”中创建的 `pom.xml` 文件执行 `mvn clean install` 来检查它是否构建成功。构建成功后，我们应该得到一个包含 `rest-example-0.1.0.jar` 文件的 `target` 目录。`target` 目录下的 Spring Boot 应用 JAR 是一个可执行的胖 JAR。我们将从 Docker 容器内部运行它。让我们使用已经熟悉的命令编写基础 `Dockerfile` 并将其放在项目根目录下（这将是我们 `docker build` 命令的上下文）：

```dockerfile
FROM jeanblanchard/java:8
COPY target/rest-example-0.1.0.jar rest-example-0.1.0.jar
CMD java -jar rest-example-0.1.0.jar
```

我们现在可以运行 `docker build` 命令，使用 `rest-example` 作为镜像名称，并省略标签（你可能记得，构建镜像时省略标签将创建 `latest` 标签）：

```bash
$ docker build . -t rest-example
```

第一个参数 `.` 指定了 `docker build` 命令的上下文。在我们的案例中，它就是我们这个小微服务的根目录。在构建过程中，Docker 将输出所有的步骤和层 ID。注意，几乎每一个 `Dockerfile` 指令都会创建一个新层。如果你还记得第 1 章“Docker 简介”，Docker 利用了层缓存。如果某个层可以重用，它将从缓存中提取。这极大地提升了构建过程的性能。最后，Docker 将输出新创建镜像的 ID，如后续截图所示：

![](img/Image00068.jpg)

镜像已经创建，因此它应该出现在可运行的镜像列表中。要列出镜像，请执行以下 Docker 命令：

```bash
$ docker image ls
```

如后续截图所示，我们的 `rest-example` 镜像已经存在并准备就绪了：

![](img/Image00069.jpg)

到目前为止一切顺利。我们已经构建了一个基础形式的镜像。虽然运行镜像的过程是第 6 章“使用 Java 应用程序运行容器”的主题，但让我们现在快速运行它以证明它是可以运行的。运行镜像请执行以下操作：

```bash
$ docker run -it rest-example
```

过了一会儿，你应该能看到熟悉的 Spring Boot Banner，这表明我们的服务正在 Docker 容器内部运行：

![](img/Image00070.jpg)

这并不复杂，对吧？基础的 `Dockerfile` 只包含三行：使用 `FROM` 定义基础镜像、使用 `COPY` 将可执行 jar 包传输到镜像的文件系统中，以及一个用于运行服务的 `CMD` 指令。

使用 Maven 构建应用程序 jar 归档然后使用 Dockerfile 的 `COPY` 指令将其拷贝过去简单可行。那么将构建过程委托给 Docker 守护进程本身呢？我们可以做到，使用我们已经熟悉的 `Dockerfile` 指令。使用 Docker 守护进程构建 Java 应用的缺点是镜像将包含所有的 JDK（包括 Java 编译器）、Maven 二进制文件以及我们的应用程序源码。我建议构建单个制品物（JAR 或 WAR 文件），进行彻底测试（使用面向发布的 QA 周期），并将该制品物（当然还有它的依赖项）部署到目标机器上。

```dockerfile
FROM java:8
RUN apt-get update
RUN apt-get install -y maven
WORKDIR /app
COPY pom.xml /app
COPY src /app
ENTRYPOINT ["/usr/lib/jvm/java-8-openjdk-64/bin/java", "-jar", "target/rest-example-0.1.0.jar"]
```

还有一个与 `CMD` 类似的 Dockerfile 指令：`ENTRYPOINT`。让我们现在来看看。

### ENTRYPOINT

#### ENTRYPOINT 指令

Docker 官方文档说明 `ENTRYPOINT` 指令允许你配置一个作为可执行文件运行的容器。这并不非常清晰，至少初次看是如此。`ENTRYPOINT` 指令与 `CMD` 指令相关。事实上，开始可能会让人困惑。原因很简单：`CMD` 先开发，然后为了更多的自定义开发了 `ENTRYPOINT`，两者之间存在功能重叠。让我们解释一下。`ENTRYPOINT` 指定了容器启动时始终执行的命令。而 `CMD` 指定了传递给 `ENTRYPOINT` 的参数。Docker 有默认的 `ENTRYPOINT` 为 `/bin/sh -c` 但没有默认的 `CMD`。例如，考虑这个 Docker 命令：

```bash
docker run ubuntu "echo" "hello world"
```

在这种情况下，镜像将是 `ubuntu`，`ENTRYPOINT` 为默认的 `/bin/sh -c`，传递给 `ENTRYPOINT` 的命令将是 `echo "hello world"`。

#### 语法

`ENTRYPOINT` 指令的语法有两种形式，类似于 `CMD`。

`ENTRYPOINT ["executable", "parameter1", "parameter2"]` 是 `exec` 形式，推荐使用。与 `CMD` 指令的 `exec` 形式相同，不会调用命令 shell。这意味着正常的 shell 处理将不会发生。例如，`ENTRYPOINT ["echo", "$HOSTNAME"]` 不会对比 `$HOSTNAME` 变量进行变量替换。如果你需要 shell 处理，则需要使用 shell 形式或直接执行 shell。例如：

```dockerfile
ENTRYPOINT ["sh", "-c", "echo $HOSTNAME"]
```

在 Dockerfile 中使用 `ENV` 定义的变量（我们稍后会讨论这个）会被 Dockerfile 解析器替换。

`ENTRYPOINT command parameter1 parameter2` 是一种 shell 形式。它会发生正常的 shell 处理。这种形式还会忽略任何 `CMD` 或 `docker run` 命令行参数。此外，你的命令将不会是 PID 1，因为将由 shell 执行。结果，如果你随后运行 `docker stop <container>`，容器将无法正常退出，停止命令将在超时后被强制发送 `SIGKILL`。

与 `CMD` 指令完全相同，Dockerfile 中最后一个 `ENTRYPOINT` 指令将生效。在 Dockerfile 中覆盖 `ENTRYPOINT` 允许你在运行容器时使用一个不同的命令来处理你的参数。如果你需要更改镜像中的默认 shell，可以通过更改 `ENTRYPOINT` 来实现：

```dockerfile
FROM ubuntu

ENTRYPOINT ["/bin/bash"]
```

从现在起，所有来自 `CMD` 的参数，或者在使用 `docker run` 启动容器时提供的参数，将由 Bash shell（此处原文 Bash shell 应为 Bash shell）处理，而不是默认的 `/bin/sh -c`。

考虑下面这个基于 BusyBox 的简单 `Dockerfile`。BusyBox 是一个在单个可执行文件中提供多个精简 Unix 工具的软件。为了演示 `ENTRYPOINT`，我们将使用 BusyBox 中的 `ping` 命令：

```dockerfile
FROM busybox

ENTRYPOINT ["/bin/ping"]

CMD ["localhost"]
```

让我们使用上一个 Dockerfile 构建镜像，执行以下命令：

```bash
$ docker build -t ping-example .
```

如果你现在使用 `ping` 镜像运行容器，`ENTRYPOINT` 指令将处理来自提供的 `CMD` 参数的参数：在我们的情况下，默认情况下将是 `localhost`。让我们使用以下命令运行它：

```bash
$ docker run ping-example
```

结果，你将得到一个 `/bin/ping localhost` 的命令行响应，如下面的截图所示：

![](img/Image0007.jpg)

`CMD` 指令（正如你可能从它的描述中记得那样）设置了默认命令和/或参数，这些参数可以在运行容器时从命令行进行覆盖。`ENTRYPOINT` 不同，它的命令和参数不能通过命令行覆盖。相反，所有的命令行参数都将附加在 `ENTRYPOINT` 参数之后。通过这种方式，你可以从某种程度上锁定容器启动期间始终执行的命令。

与 `CMD` 参数不同，当 Docker 容器带有命令行参数运行时，`ENTRYPOINT` 命令和参数不会被忽略。

由于命令行参数将附加到 `ENTRYPOINT` 参数之后，我们可以通过传递不同的参数给 `ENTRYPOINT` 来运行我们的 `ping` 镜像。让我们尝试一下，通过不同的输入运行我们的 ping 示例：

```bash
$ docker run ping-example www.google.com
```

这次它的行为会有不同。提供的参数值 `www.google.com` 将附加到 `ENTRYPOINT`，而不是在 Dockerfile 中提供的默认 `CMD` 值。将执行的完整命令行将是 `/bin/ping www.google.com`，如下面的截图所示：

![](img/Image00072.jpg)

你可以使用 `ENTRYPOINT` 的 `exec` 形式来设置相当稳定的默认命令和参数，然后使用 `CMD` 的任一形式来设置更可能更改的额外默认值。

`ENTRYPOINT` 指令给了我们很大的灵活性。最后，也是重要的一点是，在启动容器时，可以使用 `docker run` 命令的 `--entrypoint` 参数来覆盖 `ENTRYPOINT`。注意，你可以使用 `--entrypoint` 覆盖 `ENTRYPOINT` 设置，但这只能设置要执行的二进制文件（将不会使用 `sh -c`）。如你所示，`CMD` 和 `ENTRYPOINT` 指令都定义了运行容器时执行什么命令。让我们总结一下我们学到的差异及其协作关系：

- Dockerfile 应该至少指定一个 `CMD` 或 `ENTRYPOINT` 指令。
- Dockerfile 中的最后一个 `CMD` 和 `ENTRYPOINT` 将被使用。
- 当将容器作为可执行文件使用时，应该定义 `ENTRYPOINT`。
- 你应该使用 `CMD` 指令作为为 `ENTRYPOINT` 定义的命令定义默认参数的方法，或者在容器中执行 `ad-hoc` 命令。
- 当使用备性参数运行容器时，`CMD` 将被覆盖。
- `ENTRYPOINT` 设置了每次使用该镜像创建容器时所使用的具体默认应用程序。
- 如果你将 `ENTRYPOINT` 与 `CMD` 结合，你可以从 `CMD` 中移除可执行文件，只留下它的参数，这些参数将传递给 `ENTRYPOINT`。
- `ENTRYPOINT` 的最佳用法是设置镜像的主命令，允许该镜像像执行该命令一样运行（然后使用 `CMD` 作为默认标记）。

好了，我们的服务运行良好，但它并不好用。首先，让它运行涉及很多手动步骤，这就是为什么我们将在本章稍些时候使用 Maven 来实现自动化。其次，正如你记得的，我们的服务监听进入端口 `8080` 的 `HTTP` 请求。我们的基础镜像运行了，但没有暴露任何网络端口，因此没有或任何东西可以访问该服务。让我们继续学习剩下的 Dockerfile 指令来修复它。

### EXPOSE

`EXPOSE` 指令通知 Docker 容器在运行时监听指定的端口。我们已经在第 2 章“网络与存储”中提到过 `EXPOSE`。`EXPOSE` 不会自动使端口在主机上可用。为了实现这一点，你必须使用 `-p` 标志发布端口范围或使用 `-P` 标志一次性发布所有端口。

回到我们的 `Dockerfile` 并暴露一个端口：

```dockerfile
FROM jeanblanchard/java:8

COPY target/rest-example-0.1.jar rest-example.1.jar

CMD java -jar rest-example.1.jar

EXPOSE 8080
```

如果你现在使用相同的命令 `docker build -t rest-example` 构建镜像，你会注意到 Docker 输出第四层，说明端口 `8080` 已暴露。暴露的端口对于主机上的其他容器可用，如果你在运行时映射了它们，对于外部世界可用。好了，让我们使用以下 `docker run` 命令尝试一下：

```bash
$ docker run -p 8080:8080 -it rest-example
```

如果你现在调用 localhost，例如 `POST`（保存我们的书籍实体）或 `GET`（获取书籍列表或书籍），正如我们在第 4 章“创建 Java 微服务”中所做的那样，使用任何 HTTP 工具（如 HTTPie 或 Postman），它的响应与之前相同。然而，这次是通过 Docker 容器。现在，这很有趣。让我们了解剩下的重要的 Dockerfile 指令。

### VOLUME

正如你可能从第 1 章“Docker 简介”中记得，容器文件系统默认是临时的。如果你启动一个 Docker 镜像（即运行容器），你将在层栈之上获得一个读写层。你可以随心所欲地创建、修改和删除文件，然后提交层以持久化更改。在第 2 章“网络与存储”中，我们学习了如何创建卷，这是从 Docker 容器存储和检索数据的极方法。我们可以在 `Dockerfile` 中使用 `VOLUME` 指令来实现。

语法不能更简单了：它只是 `VOLUME ["/volumeName"]`。

`VOLUME` 参数可以是 JSON 数组，带有多个参数的纯字符串。例如：

```dockerfile
VOLUME ["/var/lib/tomcat8/webapps/"]

VOLUME /var/log/mongodb /var/log/tomcat
```

`VOLUME` 指令创建一个带有指定名称的挂载点，并将其标记为持有来自原生宿主机或其他容器的外部挂载卷。

`VOLUME` 命令将挂载容器内部的目录，并将该目录内创建或编辑的任何文件存储在宿主机文件结构之外的磁盘上。在 `Dockerfile` 中使用 `VOLUME` 让 Docker 知道某个目录包含持久数据。Docker 会为这些数据创建一个卷并且永远不会删除它，即使你删除了所有使用它的容器。它还会绕过联合文件系统（union file system），因此该卷实际上是一个实际目录，它会以读写或只读的形式挂载到所有共享它的容器的正确位置（如果它们是通过 `--volumes-from` 选项启动的）。为了理解 `VOLUME`，让我们来看这个简单的 Dockerfile：

```dockerfile
FROM ubuntu

VOLUME /var/myVolume
```

如果你现在运行容器并在 `/var/myVolume` 中保存一些文件，这些文件将可以供其他容器共享。

基本上，`VOLUME` 和 `-v` 几乎是等同的。`VOLUME` 和 `-v` 的区别在于，你可以动态地使用 `-v` 并在通过执行 `docker run` 启动时将你的 `host` 目录挂载到容器上。这是因为 Dockerfile 的目的是为了移植性和共享性。宿主机目录卷 100% 取决于宿主机，在任何其他机器上都会失效，这与 Docker 的理念有些偏差。因此，在 Dockerfile 中仅可以使用移植的指令。



`VOLUME`和`-v`的根本区别在于：`-v`会将你操作系统中的现有文件挂载到 Docker 容器内部，而`VOLUME`会在宿主机上创建一个新的空卷并将其挂载到容器内部。

### LABEL

为了给我们的镜像添加元数据，我们使用`LABEL`指令。单个标签是一个键值对。如果你需要在标签值中包含空格，则需要用一对引号将其括起来。标签是累加的，它们包含了从作为你镜像基础的基础镜像（即来自`FROM`指令的镜像）中获取的所有标签。如果 Docker 遇到已存在的标签，它将用新值覆盖具有相同键的标签。定义标签时，你必须遵守一些规则：键只能由小写字母、数字、点和连字符组成，并且必须以字母或数字开头和结尾。为了防止命名冲突，Docker 推荐使用反向域名表示法使用命名空间来标记键。另一方面，没有命名空间（点）的键预留给命令行使用。

`LABEL`指令的语法非常直观：

```
LABEL "key"="value" 
```

若要有一个多行值，请用反斜符分隔行；例如：

```
LABEL description="This is my \

multiline description of the software." 
```

你可以在单个镜像中拥有多个标签。用空格或反斜符分隔它们，例如：

```
LABEL key1="value1" key2="value2" key3="value3"

LABEL key1="value1" \

key2="value2" \

key3="value3" 
```

实际上，如果你需要在镜像中包含多个标签，建议使用`LABEL`指令的多标签形式，因为这只会在镜像中产生一个额外的额外的层。

每个`LABEL`指令都会创建一个新层。如果你的镜象有许多标签，请使用单个`LABEL`指令的多标签形式。

如果你想检查镜像拥有哪些标签，请使用你在前面的章节中已经熟悉的`docker inspect`命令。

### ENV

`ENV`是一个`Dockerfile`指令，用于将环境变量`<key>`设置为值`<value>`。你使用`ENV`有两种选择：

* 第一种`ENV <key> <value>`，它将单个变量设置成一个值。第一个空格后的整个字符串将被视为`<value>`。这包括任何字符，以及空格和引号。例如：

```
ENV JAVA_HOME /var/lib/java8 
```

* 第二种是带有等号的形式，即`ENV <key>=<value>`。这种形式允许一次性设置多个环境变量。如果你需要在值中提供空格，则需要使用引号。如果你需要在值中提供引号，请使用反斜符：

```
ENV CONFIG_TYPE=file CONFIG_LOCATION="home/Jarek/my \
app/config.json" 
```

请注意，你可以使用`ENV`来更新`PATH`环境变量，然后`CMD`参数将感知到该设置。这将使得`Dockerfile`中的`CMD`参数形式更加整洁。例如，设置以下内容：

```
ENV PATH /var/lib/tomcat8/bin:$PATH 
```

这将确保`CMD ["startup.sh"]`能够正常工作，因为它会在系统`PATH`中找到`startup.sh`文件。你也可以使用`ENV`来设置经常修改的版本号，以便更容易处理升级，如下例所示：

```
ENV TOMCAT_VERSION_MAJOR 8

ENV TOMCAT_VERSION 8.5.4

RUN curl -SL http://apache.uib.no/tomcat/tomcat-$TOMCAT_VERSION_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz | tar zxvf apache-tomcat-$TOMCAT_VERSION.tar.gz -c /usr/Jarek

ENV PATH /var/lib/tomcat8/bin:$PATH 
``` 

这将确保`CMD ["startup.sh"]`能够正常工作，因为它会在系统`PATH`中找到`startup.sh`文件。你也可以使用`ENV`设置经常修改的版本号，以便更容易处理升级，如下例所示：

```
ENV TOMCAT_VERSION_MAJOR 8

ENV TOMCAT_VERSION 8.5.4

RUN curl -SL http://apache.uib.no/tomcat/tomcat-$TOMCAT_VERSION_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz | tar zxvf apache-tomcat-$TOMCAT_VERSION.tar.gz -c /usr/Jarek
```

（注：原文中此处存在内容重复，译文已按要求去重）

`ONBUILD`指令指定了一个额外的指令，当其他镜像使用此镜像作为基础镜像进行构建时，该指令会被触发。换句话之，`ONBUILD`指令是父`Dockerfile`给子`Dockerfile`（下游构建）的指令。任何构建指令都可以被注册为触发器，这些指令将在`Dockerfile`中的`FROM`指令之后立即触发。

#### ONBUILD 语法

`ONBUILD`指令的语法如下：

```
ONBUILD <INSTRUCTION> 
```

其中，`<INSTRUCTION>`是另一个 Dockerfile 构建指令，它将在稍后构建子镜像时被触发。这里有一些限制：`ONBUILD`指令不允许链接另一个`ONBUILD`指令，并且不允许将`FROM`和`MAINTAINER`指令作为`ONBUILD`触发器。

如果你正在构建一个将作为其他镜像构建基础的镜像，那么它是非常有用的。例如，一个应用程序构建环境，或者可以使用用户特定配置进行自定义的守护进程。`ONBUILD`指令对于自动化构建你选择的软件栈非常有用（[`docs.docker.com/engine/reference/builder/#onbuild`](https://docs.docker.com/engine/reference/builder/#onbuild) 和 [`docs.docker.com/engine/reference/builder/#maintainer-deprecated`](https://docs.docker.com/engine/reference/builder/#maintainer-deprecated)）。考虑以下这个使用 Maven 构建 Java 应用程序的示例（是的，Maven 也可以作为 Docker 容器可用）。基本上，你项目的所有 Dockerfile 只需要引用包含包含`ONBUILD`指令的基础容器即可：

```
FROM maven:3.3-jdk-8-onbuild
CMD ["java","-jar","/usr/src/app/target/app-1.0-SNAPSHOT-jar-with-dependencies.jar"] 
```

这没有什么魔力，如果你查看父镜像的 Dockerfile，一切都会变得显而易见。在我们的情况下，它将是 GitHub 上可用的`docker-maven` Dockerfile：

```
FROM maven:3-jdk-8
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD ADD . /usr/src/app
ONBUILD RUN mvn install 
```

有一个基础镜像同时安装了 Java 和 Maven，并有一系列复制文件和运行 Maven 的指令。

`ONBUILD`指令向镜像添加了一个触发指令，该指令将在稍后镜像被用另一个构建的基础时执行。触发器将在子构建的范围内执行，就像它被立即插入到子`Dockerfile`的`FROM`指令之后一样。

当 Docker 在构建过程中遇到`ONBUILD`指令时，构建器会在正在构建的镜像的元数据中添加一种触发器。但这是该镜像唯一的影响方式。构建结束时，所有触发器的列表将存储在镜像清单的键`OnBuild`下。你可以使用熟悉的`docker inspect`命令查看它们。

稍后，镜像可能会通过`FROM`指令作为新构建的基础。在处理`FROM`指令时，Docker 构建器会查找并执行`ONBUILD`触发器。

#### STOPSIGNAL

要指定应发送到容器的信号，请使用`STOPSIGNAL`。该信号可以是名称，例如`9`。

#### HEALTHCHECK

`HEALTHCHECK`指令可以用于测试应用程序是否存活。容器可以有几种状态：`created`（已创建）、`restarting`（重启中）、`running`（运行中）、`paused`（已暂停）、`exited`（已退出）或`dead`（已死亡）。`HEALTHCHECK`的实现可以是对此端点的`GET`请求，返回`200`。

Dockerfile 中只能有一个`HEALTHCHECK`指令。如果你列出了多个，最后一个生效。`HEALTHCHECK`的语法如下：

```
HEALTHCHECK --interval=5m --timeout=2s --retries=3 curl -f http/ping || exit 1
```

在上一个示例中，命令`curl -f http/ping`将每 5 分钟执行一次，最大超时时间为 2 秒。如果单次检查运行时间超过 2 秒，则认为检查失败。如果连续三次重试失败，容器将变为`unhealthy`（不健康）状态。

### 使用 Maven 创建镜像

自然，我们可以使用 Docker 本身来构建 Docker 镜像。但这不是 Spring 开发者的典型用例。对于我们来说，典型的用例是使用 Maven。如果你设置了持续集成流（例如使用 Jenkins），这会特别有用。将镜像构建过程委托给 Maven 可以给你带来很大的灵活性，并节省大量时间。GitHub 上至少有几个 Docker Maven 插件是可以免费提供的，例如：

*   [`github.com/spotify/docker-maven-plugin`](https://github.com/spotify/docker-maven-plugin) : Spotify 的用于构建和推送 Docker 镜像的 Maven 插件。

*   [`github.com/alexec/docker-maven-plugin`](https://github.com/alexec/docker-maven-plugin) 。

*   [`github.com/fabric8io/docker-maven-plugin`](https://github.com/fabric8io/docker-maven-plugin) : 我认为这是最有用且可配置的一个。

我们的用例将使用`Maven`打包 Spring Boot 可执行`JAR`，然后将该构建产物复制到 Docker 镜像中。使用 Maven 插件主要关注两个方面：

* 构建并推送包含构建产物的 Docker 镜像

* 为集成测试和开发启动和停止 Docker 容器。这是我们在第 6 章 中重点关注的内容，*使用 Java 应用程序运行容器*

现在让我们关注创建镜像，从插件目标和可能的配置选项开始。

fabric8 Docker 插件提供了几个 Maven 目标：

* `docker:build` : 这使用来自`maven-assembly-plugin`的程序集描述符格式来指定从镜像子目录（默认为`/maven`）中添加的内容

* `docker:push` : 使用此插件构建的镜像可以推送到公共或私有的 Docker 仓库

* `docker:start`和`docker:stop` : 用于启动和停止容器

* `docker:watch` : 这将按顺序执行`docker:build`和`docker:run`。它可以在后台（独立控制台）无限运行，除非你用`CTRL+C`停止它。它可以监控程序集文件的变化并重新运行构建。这节省了大量时间

* `docker:remove` : 用于清理镜像和容器

* `docker:logs` : 打印运行容器的输出

* `docker:volume-create`和`docker:volume-remove` : 分别用于创建和删除卷。我们将在本章稍后回到这些内容

在运行这些目标之前，我们需要指示插件它应该如何行为。我们在项目的`pom.xml`文件的插件配置中进行设置：

* Maven Docker 插件配置

插件定义中的重要部分是`<configuration>`元素。这是你设置插件行为的地方。`<configuration>`中有两个主要元素：

* 一个`<build>`配置，指定如何构建镜像

* 一个`<run>`配置，描述应该如何创建和启动容器

以下是用于 Docker 的`fabric8` Maven 插件的最简单配置示例：

```
 <plugin>
  <groupId>io.fabric8</groupId>
  <artifactId>docker-maven-plugin</artifactId>
  <version>0.20.1</version>
  <configuration>
   <dockerHost>http://127.0.0.1:2375</dockerHost>
   <verbose>true</verbose>
   <images>
     <image>
      <name>rest-example:${project.version}</name>
      <build>
      <dockerFile>Dockerfile</dockerFile>
      <assembly>
        <descriptorRef>artifact</descriptorRef>
      </assembly>
      </build>
     </image>
   </images>
  </configuration>
</plugin> 
```

`<dockerHost>`指定运行中的 Docker 引擎的 IP 地址和端口，因此，为了让它构建，你需要先运行 Docker。在前面的情况下，如果你从 shell 中运行`mvn clean package docker:build`命令，Fabric8 Docker 插件将使用你提供的`Dockerfile`构建镜像。但还有另一种构建镜像的方法，完全不需要`Dockerfile`，至少不需要显式定义。要做到这一点，我们需要稍微更改插件配置。看看修改后的配置：

```
 <configuration>
  <images>
    <image>
      <name>rest-example:${project.version}</name>
      <alias>rest-example</alias>
      <build>
       <from>jeanblanchard/java:8</from>
       <assembly>
         <descriptorRef>artifact</descriptorRef>
       </assembly>
       <cmd>java -jar      
        maven/${project.name}-${project.version}.jar</cmd>
      </build>
     </image>
   </images>
</configuration>
```

你可以看到，我们不再交付`Dockerfile`。相反，我们只是将`Dockerfile`指令作为插件配置元素。这非常方便，因为我们不再需要硬编码可执行 jar 名称、版本等。它将从 Maven 构建作用域获取。例如，jar 的名称将提供给`<cmd>`元素。这将自动在`Dockerfile`中生成有效的`CMD`指令。如果我们现在使用`mvn clean package docker:build`命令构建项目，Docker 将使用我们的应用程序构建镜像。让我们按字母顺序列出可用的配置元素：

| 元素 | 描述 |

| :--- | :--- |

| `assembly` | `<assembly>`元素定义了如何构建进入 Docker 镜像的产物和其他文件。你可以使用`targetDir`元素提供一个目录，程序集中的文件和产物将复制到该目录。默认值为`/maven`。在我们的示例中，我们将使用`<descriptorRef>`提供预定义的程序集描述符之一。`<descriptorRef>`是一种方便的快捷方式，可以接受以下值： <br>* `artifact-with-dependencies` : 附加项目产物及其所有依赖项。当目标目录存在类路径文件时，将被添加到其中。<br>* `artifact` : 仅附加项目产物但不包含依赖项。<br>* `project` : 附加整个 Maven 项目但不包含`target/` |

| `buildArgs` | 一个指定构建参数的映射。 |

| `build` | 等同于 Dockerfile 中的`FROM`，用于指定基础镜像。 |

| `cleanup` | 用于在构建后清理未标记镜像。 |

| `nocache` | 用于禁用 Docker 的构建缓存。在运行 Maven 命令时，可以通过设置系统属性`docker.nocache`来覆盖它。 |

| `compression` | 可以接受`none`（默认）、`gzip`或`bzip2`值。它指定压缩模式以及构建存档如何传输到 Docker 守护进程。 |

| `cmd` | 这等同于我们已经熟悉的`CMD`指令，提供默认执行的命令。 |



| `dockerHost` | 指定运行的 Docker 引擎的 IP 地址和端口。 |
|---|---|
| `healthCheck` | 等同于 Dockerfile 中的 `HEALTHCHECK`。 |
| `entryPoint` | 等同于 Dockerfile 中的 `ENTRYPOINT`。 |
| `env` | 等同于 Dockerfile 中的 `ENV`。 |
| `from` | 等同于 Dockerfile 中的 `FROM`。 |
| `labels` | 定义标签，同于 Dockerfile 中的 `LABEL`。 |
| `maintainer` | 等同于 Dockerfile 中的 `MAINTAINER`。 |
| `optimize` | 如果设置为 `true`，则将所有 `runCmds` 压缩为单个 `RUN` 指令。强烈建议这样做以减少创建的镜像层数。 |
| `ports` | Dockerfile 中的 `EXPOSE`。这是一个 `<port>` 元素列表，每个暴露的端口一个。格式可以是纯数字 `"8080"` 或带有协议的 `"8080/tcp"`。 |
| `runCmds` | 等同于 `RUN`，构建过程中要运行的命令。它包含传递给 shell 的 `<run>` 元素。 |
| `tags` | 可以包含 `<tag>` 元素列表，为构建的镜像提供额外的标签。 |
| `user` | 等同于 Dockerfile 中的 `USER`，指定 Dockerfile 应该切换的用户。 |
| `volumes` | 包含 `VOLUME` 等效项列表，用于创建容器卷的 `<volume>` 元素列表。 |
| `workdir` | 等同于 Dockerfile 中的 `WORKDIR`，启动容器时进入的目录。 |

如你所见，插件配置非常灵活，它包含了一套完整的 Dockerfile 指令等效选项。让我们看看在配置配置的情况下，我们的 `pom.xml` 应该是什么样。

## 完整的 `pom.xml`

如果你从一开始就开始关注我们的项目，那么完整的 Maven POM 如下所示：

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">

  <modelVersion>4.0.0</modelVersion>

  <groupId>pl.finsys</groupId>
  <artifactId>rest-example</artifactId>

  <version>0.1.0</version>

  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>1.5.2.RELEASE</version>
  </parent>

  <dependencies>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
      <groupId>org.hibernate</groupId>
      <artifactId>hibernate-validator</artifactId>
    </dependency>
    <dependency>
      <groupId>org.hsqldb</groupId>
      <artifactId>hsqldb</artifactId>
      <scope>runtime</scope>
    </dependency>
    <dependency>
      <groupId>io.springfox</groupId>
      <artifactId>springfox-swagger2</artifactId>
      <version>2.6.1</version>
    </dependency>
    <dependency>
      <groupId>io.springfox</groupId>
      <artifactId>springfox-swagger-ui</artifactId>
      <version>2.5.0</version>
    </dependency>
    <!--test dependencies-->
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-test</artifactId>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-test</artifactId>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>com.jayway.jsonpath</groupId>
      <artifactId>json-path</artifactId>
      <scope>test</scope>
    </dependency>
  </dependencies>

  <properties>
    <java.version>1.8</java.version>
  </properties>

  <build>
    <plugins>
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
      </plugin>
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
      </plugin>
      <plugin>
        <groupId>io.fabric8</groupId>
        <artifactId>docker-maven-plugin</artifactId>
        <version>0.20.1</version>
        <configuration>
          <images>
            <image>
              <name>rest-example:${project.version}</name>
              <alias>rest-example</alias>
              <build>
                <from>openjdk:latest</from>
                <assembly>
                  <descriptorRef>artifact</descriptorRef>
                </assembly>
                <cmd>java -jar maven/${project.name}-${project.version}.jar</cmd>
              </build>
              <run>
                <wait>
                  <log>Hello World!</log>
                </wait>
              </run>
            </image>
          </images>
        </configuration>
      </plugin>
    </plugins>
  </build>

  <repositories>
    <repository>
      <id>spring-releases</id>
      <url>https://repo.spring.io/libs-release</url>
    </repository>
  </repositories>
  <pluginRepositories>
    <pluginRepository>
      <id>spring-releases</id>
      <url>https://repo.spring.io/libs-release</url>
    </pluginRepository>
  </pluginRepositories>
</project>
```

## 构建镜像

使用我们的 Spring Boot 制品构建 Docker 镜像，请运行此命令：

```bash
mvn clean package docker:build
```

`clean` 告诉 Maven 删除 `target` 目录。Maven 总是通过 `package` 命令编译你的类。在运行 `docker:build` 命令时运行 `package` 命令是非常重要的。如果你尝试分步运行这些命令，将会遇到错误。在 Docker 镜像构建时，你将在控制台中看到以下输出：

![](img/Image00073.jpg)

控制输出将显示新镜像的 ID。如果你好奇自动生成的 Dockerfile 长什么样，可以在项目的 `target/docker/rest-example/0.1.0/build` 目录下找到它。第一次构建此 Docker 镜像将花费更长时间，因为所有层都需要下载。但得益于层缓存，每次构建都将快得多。

## 创建和删除卷

如果没有管理卷的功能，Fabric8 Maven Docker 插件将不是完整的解决方案。事实上，它提供了两种处理卷的方法：`docker:volume-create` 和 `docker:volume-remove`。你可能还记得第 2 章，网络和持久化存储，Docker 在处理卷及其驱动程序时使用了插件式架构。`fabric8` 插件可以配置为将特定的卷驱动程序及其参数传递给 Docker 进程。考虑以下插件配置的片段：

```xml
<plugin>
  <configuration>
    [...]
    <volumes>
      <volume>
        <name>myVolume</name>
        <driver>local</driver>
        <opts>
          <type>tmpfs</type>
          <device>tmpfs</device>
          <o>size=100m,uid=1000</o>
        </opts>
        <labels>
          <volatileData>true</volatileData>
        </labels>
      </volume>
    </volumes>
  </configuration>
</plugin>
```

在前面的示例中，我们使用本地文件系统驱动程序创建一个命名卷。它可以在容器启动时挂载，如 `pom.xml` 文件中的 `<run>` 部分所示。

## 总结

在本章中，我们学习了如何开始使用 Docker 容器打包 Java 应用程序。我们可以通过 `docker build` 命令和 `Dockerfile` 手动操作，也可以使用 Maven 来。对于 Java 开发者来说，Docker 帮助我们将应用程序隔离在干净环境中。隔离是非常重要的，因为它减少了我们使用的软件环境的复杂性。Fabric8 Maven Docker 插件是一个很好的工具，我们可以用它通过 Maven 自动化镜像构建，特别是在处理 Java 应用程序时。不再需要手动编写 Dockerfile，只需配置插件丰富的选项即可。此外，将其与 Maven 工作允许我们轻松地将 Docker 构建集成到现有的开发流中，例如使用 Jenkins 进行持续交付。在第 6 章，使用容器运行 Java 应用程序中，我们将更详细地讨论如何在容器内运行我们的 Java 应用程序。当然，我们也将使用 Maven。

在第 5 章 `使用 Java 应用程序创建镜像` 中，我们学习了 Dockerfile 的结构以及如何构建镜像。到此时，你应该能够创建自己的 Docker 镜像并开始使用它了。实际上，我们已经运行了多次容器，但没有深入细节。我们使用 Dockerfile 手动构建了镜像，然后执行了 `docker build` 命令。我们还一直在使用 Maven 来自动化构建过程。我们创建的镜像包含了我们简单的 REST Java 服务。我们已经运行了它，以检查它是否真的可以正常工作。然而，这一次，我们将详细介绍如何从我们的镜像运行容器。本章将包含以下概念：

- 启动和停止容器
- 容器运行模式
- 监控容器
- 容器重启策略
- 资源的运行时限制
- 使用 Maven 运行容器

## 启动和停止容器

让我们回到起点，从基础知识开始：如何从 shell 或命令行手动运行和停止 Docker 容器。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

### 启动

正如你在之前的几个章节中看到的，为了从镜像启动容器，我们使用 `docker run` 命令。运行中的容器将拥有自己的文件系统、网络栈和与宿主机隔离的进程树。正如你从第 5 章 `使用 Java 应用程序创建镜像` 中记得的，每一个 `docker run` 命令都会创建一个新容器并执行 Dockerfile 中指定的命令 `CMD` 或 `ENTRYPOINT`。

`docker run` 命令的语法如下：

```bash
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
```

该命令接受镜像名称，并带有可选的 `TAG` 或 `DIGEST`。如果你跳过了 `TAG` 和 `DIGEST` 命令参数，Docker 将根据标签为 `latest` 的镜像运行容器。`docker run` 命令还接受一组你可能觉得有用的选项，例如运行模式（分离或前台）、网络设置，或对 CPU 和内存的运行时限制。我们将在本章稍后介绍这些内容。当然，你可以在除了镜像名称外不需要任何参数的情况下执行 `docker run` 命令。它将运行并采用镜像中定义的默认选项。指定选项让你有机会覆盖由镜像作者指定的选项以及 Docker 引擎的运行时默认值。



`COMMAND`参数不是强制的，镜像作者可能已经通过`Dockerfile`中的`CMD`指令提供了默认的`COMMAND`。`CMD`在`Dockerfile`中只出现一次，并且通常是最后一条指令。当从镜像启动容器时，我们可以通过简单地为`docker run`提供自己的命令或参数作为`COMMAND`参数来覆盖`CMD`指令。`docker run`命令中镜像名称之后出现的任何内容都将传递给容器并视为`CMD`参数。如果镜像还指定了`ENTRYPOINT`，那么`CMD`或`COMMAND`将作为参数追加到`ENTRYPOINT`之后。但你猜怎么着，我们也可以使用`docker run`命令的`--entrypoint`选项来覆盖`ENTRYPOINT`。

### 停止

要停止一个或多个正在运行的 Docker 容器，我们使用`docker stop`命令。语法非常简单：

```
$ docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

你可以指定一个或多个容器进行停止。`docker stop`的唯一选项是`-t`（`--time`），它允许我们在停止容器之前指定一个等待时间。默认值为 10 秒，这应该足够让容器优雅地停止。若要以更粗暴的方式停止容器，你可以执行以下命令：

```
$ docker kill CONTAINER [CONTAINER...]
```

`docker stop`和`docker kill`之间有什么区别？它们都会停止运行中的容器。但存在一个重要的区别：

* `docker stop`：容器内的主进程首先接收`SIGTERM`，在经过宽限期后接收`SIGKILL`。
* `docker kill`：容器内的主进程将被发送`SIGKILL`（默认）或通过选项`--signal`指定的任何信号。

换句话说，`docker stop`尝试通过发送标准 POSIX 信号`SIGTERM`来触发优雅关闭，而`docker kill`只是粗暴地杀死进程，从而关闭容器。

### 列出运行中的容器

要列出运行中的容器，只需执行`docker ps`命令：

```
$ docker ps
```

要包含 Docker 宿主机上的所有容器，请包含`-a`选项：

```
$ docker ps -a
```

你还可以使用`-f`选项通过指定过滤器来过滤列表。过滤器需要以`key=value`格式提供。目前可用的过滤器包括：

* `id`: 按容器的 ID 过滤
* `label`: 按标签过滤
* `name`: 按容器名称过滤
* `exited`: 按退出码过滤
* `status`: 按状态过滤，状态可以是创建 (created)、重启中 (restarting)、运行 (running)、移除 (removing)、退出 (exited) 或死亡 (dead)
* `volume`: 当指定卷名称或挂载点时，将包含卷的容器
* `network`: 当指定网络 ID 或名称时，将包含连接到网络的容器

考虑以下示例，它将获取宿主机上的所有容器并过滤：

```
$ docker ps -a -f status=running
```

### 容器

要从宿主机删除容器，我们使用`docker rm`命令。语法如下：

```
$ docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

你可以一次指定一个或多个容器。如果你反复运行临时的前台进程，这些文件系统会迅速膨胀。对此有一个解决方法：与其手动清理，不如告诉 Docker 在容器退出时自动清理并删除文件系统。你通过添加`--rm`标志来实现，这样在进程结束后就会删除容器。

`--rm`标志会让 Docker 在容器关闭后删除它。

例如，像示例所示使用`run`命令：

```
$ docker run --rm -it Ubuntu /bin/bash
```

上述命令告诉 Docker 在容器关闭后删除。

在启动 Docker 容器时，你可以决定是以默认模式、前台还是后台（即所谓的分离模式）运行容器。让我们解释一下它们的区别。

### 容器运行模式

Docker 有两种容器运行模式：前台和分离。让我们从默认的模式开始。

### 前台

在前台模式下，你执行`docker run`的控制台将附加到标准输入、输出和错误流。这是默认设置；Docker 会将`STDIN`、`STDOUT`和`STDERR`流附加到你的 Shell 控制台。如果你有需要，可以更改这种行为并为`docker run`命令使用`-a`切换。作为`-a`切换的参数，你使用要附加到控制台的流的名称。例如：

```
$ docker run -a stdin -a stdout -i -t centos /bin/bash
```

上述命令将同时`stdin`和`stdout`流附加到你的控制台。

实用的`docker run`选项包括`-i`或`--interactive`（用于保持`STDIN`流打开，即使未附加）以及`-t`或`--tty`（用于附加`pseudo-tty`伪终端）切换器。它们通常结合使用`-it`，你需要使用它为容器中运行的进程分配一个`pseudo-tty`控制台。实际上，我们在第 5 章 *使用 Java 应用创建镜像* 中，运行 REST 服务时，已经使用了这个选项：

```
$ docker run -it rest-example
```

简单来说，`-it`用于结合使用，在容器启动后将命令行附加到容器上。这样你就可以在 shell 控制台中查看运行中容器的状况，并在需要时与容器进行交互。

### 离线模式 (Detached)

你可以使用`-d`选项以离线模式启动 Docker 容器。它是前台模式的相反操作。容器启动并在后台运行，类似于守护进程或服务。让我们尝试在后台运行我们的`rest-example`，执行以下命令：

```
$ docker run -d -p 8080:8080 rest-example
```

容器启动后，你将获得控制权，并可以使用 shell 或命令行执行其他命令。Docker 只会输出容器 ID，如后续截图所示：

![](img/Image00074.jpg)

你可以使用容器 ID 在其他 docker 命令中引用该容器，例如，当你需要停止容器或附加到它时。当我们的服务在后台运行时，它仍然在工作：Spring Boot 监听在`8080`端口以接收`HTTP` `GET`或`POST`请求。请注意，在离线模式启动的容器在用于运行容器的根进程退出时会停止。理解这一点很重要，即使你在后台运行了某些进程（从`Dockerfile`中的指令启动），如果启动容器的命令结束，Docker 也会停止容器。在我们的案例中，Spring Boot 正在运行并监听，同时防止了 Docker 关闭容器。要将容器从后台带回你控制台的前台，你需要`attach`（附加）到它上。

### 附加到运行中的容器 (Attaching to running containers)

为了保持对离线容器的控制，请使用`docker attach`命令。`docker attach`的语法非常简单：

```
$ docker attach [OPTIONS] <container ID or name>
```

在我们案例中，这就是我们在容器启动时获得的 ID：

```
$ docker attach 5687bd611f84b53716424fd826984f551251bc95f3db49715fc7211a6bb23840
```

此时，如果有任何内容输出（例如来自我们运行的 REST 服务的另一行日志），你将在控制台上看到它。如你所见，如果你需要实时查看写入`stdout`流的内容，`docker attach`命令会非常有用。它本质上是让你的控制台*重新附加*（reattach）到容器中运行的进程上。换句话说，它会将`stdout`流式传输到你的屏幕，并将`stdin`映射到你的键盘，允许你输入命令并查看输出。注意，在附加到容器时按下`CTRL + C`组合键会杀死容器正在运行的进程，而不是从控制台分离。要从进程分离，请使用默认的`CTRL+P`和`CTRL+Q`组合键。如果`CTRL + P`和`CTRL + Q`序列与现有的快捷键冲突，可以通过为`docker attach`命令设置`--detach-keys`选项来提供自己的分离序列。如果你希望能够使用`CTRL + C`进行分离，可以通过将`sig-proxy`参数设置为`false`来告诉 Docker 不要向容器中运行的进程发送`sig-term`：

```
$ docker attach --sig-proxy=false [container-name or ID]
```

如果容器在后台运行，能够监控它的行为将很不错。Docker 提供了一系列功能来实现这一目标。让我们看看如何监控运行中的容器。

### 监控容器 (Monitoring containers)

有一些方法可以监控运行中的 Docker 容器。可以是查看日志文件、查看容器事件和统计信息，以及检查容器属性。让我们从 Docker 拥强大日志功能开始。访问日志记录至关重要，特别是当你的容器以离线运行时运行。让我们看看 Docker 在日志机制方面能提供什么。

### 查看日志 (Viewing logs)

大多数应用程序将其日志记录输出到标准`stdout`流。如果容器在前台模式下运行，你将会在控制台中看到它。然而，当以离线模式运行容器时，你将在控制台上只看到容器 ID。但是，Docker 引擎会将运行中容器的所有`stdout`输出收集在宿主机上的历史文件中。你可以通过`docker logs`命令来显示它。该命令的语法如下：

```
$ docker logs -f <container name or ID>
```

`docker logs`命令会将日志的最后几行输出到控制台。由于容器仍在后台（离线模式）运行，你将立即获得提示符，如后续截图所示，它显示了我们 REST 服务的日志文件片段：

![](img/Image0075.jpg)

`-f`标志的作用类似于 Linux 中的`tail`，它会持续显示新的日志记录。当你完成时，`CTRL + C`将停止显示日志。默认情况下，日志记录存储在`/var/lib/docker`中的文件文件中。你可以使用`docker inspect`并使用模板提取`LogPath`。

我们已经提到过，默认情况下日志会被写入 JSON 文件。但这可以很容易更改，因为 Docker 利用了日志驱动器的概念。通过使用不同的驱动器，你可以为容器选择其他存储方式。默认驱动器是`json-file`驱动器，它只需将记录写入 JSON 文件。每个驱动器都可以接受额外的参数。JSON 驱动器接受，例如：

```
--log-opt max-size=[0-9+][k|m|g]
--log-opt max-file=[0-9+]
```

正如你可能猜的，这类似于 Java 应用中的滚动文件。`max-size`指定了可以创建的最大文件大小，Docker 将创建一个新文件。可以使用大小后缀`k`、`m`或`g`，其中`k`代表字节，`m`代表兆字节，`g`代表字节。将日志拆分成单独的文件便于传输、存档等。此外，如果文件较小，搜索日志文件会方便得多。

`docker logs`命令仅显示最新日志文件的记录。

还有其他可用的日志驱动器列表包括：

* `none`: 它将完全关闭日志记录
* `syslog`: 这是 Docker 的`syslog`日志驱动器。它会将日志消息写入系统`syslog`
* `journald`: 将日志消息写入`journald`。`systemd-journald`是一个负责事件日志的守护进程，以追加的二进制文件作为其日志文件
* `splunk`: 提供使用`Event Http`收集将日志消息写入 Splunk。Splunk 可以作为企业级日志分析器使用。
* `gelf` : 将日志记录写入 GELF 终端，例如 Graylog 或 Logstash。Graylog 可以在[`www.graylog.org`](https://www.graylog.org)获取，是一个开源日志管理工具，支持对所有日志文件进行搜索、分析和告警。Logstash 可以在[`www.elastic.co/products/logstash`](https://www.elastic.co/products/logstash)找到，它是一个用于处理来自任何源的数据（包括日志数据）的流水线。
* `fluentd` : 将日志消息写入`fluentd`。Fluentd 是一个用于统一日志层的开源数据收集器。Fluentd 的主要功能是通过在中间提供统一的日志层，将数据源与后端系统分离。它体积小、运行快，并拥有数百个插件，使其成为非常灵活的解决方案。你可以在它的网站[`www.fluentd.org`](https://www.fluentd.org)上阅读更多关于`fluentd`的信息。
* `gcplogs` : 将日志记录发送到 Google Cloud logging。
* `awslogs` : 此驱动程序将日志消息写入 Amazon CloudWatch logs。

如你所见，Docker 的可扩展架构在运行容器时再次提供了几乎无限的灵活性。要切换到其他日志驱动程序，使用`docker run`命令的`--log-driver`选项。例如，要将日志记录存储在`syslog`中，执行以下命令：

```bash
$ docker run --log-driver=syslog rest-example
```

注意，`docker logs`命令仅对`json-file`和`journald`驱动有效。要访问写入另一个日志引擎的日志，你需要使用与所选驱动程序匹配的工具。使用专用工具来浏览日志记录通常会更方便；实际上，这往往是你选择其他日志驱动程序的原因。例如，在 Logstash 或 Splunk 中搜索和浏览日志比翻阅满是 JSON 条目的文本文件快得多。

查看日志记录是监控我们应用程序在宿主机上运行情况的方便方法。有时，查看运行容器的属性也会很有用，例如映射的网络端口或映射的卷等。要显示容器属性，我们使用`docker inspect`命令，它是非常有用的。

### 检查容器 (Inspecting a container)

我们一直用来列出运行容器的`docker ps`命令为我们提供了许多容器的信息，例如它们的 ID、运行时间、映射端口等。要显示有关运行容器的更多细节，我们可以使用`docker inspect`。命令的语法如下：

```bash
$ docker inspect [OPTIONS] CONTAINER|IMAGE|TASK [CONTAINER|IMAGE|TASK...]
```

默认情况下，`docker inspect`命令将以 JSON 数组格式输出容器或镜像的信息。由于有许多属性，它可能不非常易读。如果我们知道在寻找什么，可以提供一个模板来处理输出，使用`-f`（或`--format`）选项。该模板使用来自 Go 语言的模板格式（顺便说一下，Docker 本身是用 Go 编写的）。`docker inspect`命令最简单且常用的模板只是一个短模板，用于精确提取你所需要的信息，例如：

```bash
$ docker inspect -f '{{.State.ExitCode}}' jboss/wildfly
```

由于`inspect`命令接受 Go 模板来形成容器或镜像元数据的输出，此功能为处理和转换结果提供了几乎无限的可能性。Go 模板引擎非常强大，因此，你可以使用模板引擎进一步处理结果，而不是通过`grep`管道输出（虽然后者很快但很乱）。

`--format`的参数只是我们想要应用到容器元数据的模板。在这个模板中，我们可以使用条件语句、循环和其他 Go 语言特征。例如，以下命令将找到所有退出码非零容器的名称：

```bash
$ docker inspect -f '{{if ne 0.0 .State.ExitCode }}{{.Name}} {{.State.ExitCode}}{{ end }}' $(docker ps -aq)
```

注意，我们提供了`$(docker ps -aq)`而不是容器 ID 或名称。结果是，所有运行容器的 ID 将被传递到`docker inspect`命令中，这是一种非常方便的快捷方式。大括号`{{}}`表示 Go 模板指令，它们之外的任何内容都将字面打印。Go 模板中的点（`. `）表示上下文（context）。大多数情况下，当前上下文是元数据的整个数据结构，但在需要时可以重新绑定，包括使用`with`动作。例如，这两个`inspect`命令将打印完全相同的结果：

```bash
$ docker inspect -f '{{.State.ExitCode}}' wildfly
$ docker inspect -f '{{with .State}} {{.ExitCode}} {{end}}' wildfly
```

如果你在绑定的上下文内部，美元符号（`$`）将始终让你获取`root`上下文。我们可以执行此命令：

```bash
$ docker inspect -f '{{with .State}} {{$.Name}} exited with {{.ExitCode}} exit code \ {{end}}' wildfly
```

它将输出：

```
/wildfly exited with 0 exit code.
```



模板引擎支持逻辑函数，如 `and`、`or` 和 `not`；它们将返回布尔结果。还支持比较函数：`eq`、`ne`、`lt`、`le`、`gt` 和 `ge`。它们可以比较字符串、浮点数或整数。配合 `if` 等条件函数，这些都可以非常有用：

```bash
docker inspect -f '{{if eq .State.ExitCode 0}}Normal Exit{{else if eq .State.ExitCode 1}}Not a Exit{{end}}' wildfly
```

有时，`docker inspect` 的巨大输出可能会非常困惑。由于输出是 JSON 格式，可以使用 `jq` 工具来获取概述并挑选出感兴趣的部分。`jq` 工具可以在 [`stedolan.github.io/`](https://stedolan.github.io/) 免费获取。它是一个轻量且灵活的 JSON 处理器，类似于用于 JSON 数据的 `sed` 命令。例如，让我们从元数据提取容器 IP：

```bash
$ docker inspect <containerID> | jq -r '.[0].NetworkSettings.IPAddress'
```

如你所见，`docker inspect` 命令提供了关于容器有用信息。结合模板功能以及可选的 `jq` 工具，它为你提供了强大的工具来获取容器信息并用于脚本编写。但除了元数据之外，还有另一个价值来源。它是运行时统计，我们现在关注它。

### 统计（Statistics）

要查看容器的 CPU、内存、磁盘 I/O 和网络 I/O 统计数据，请使用 `docker stats` 命令。你可以通过指定用空格分隔的容器 ID 或名称将统计测量限制在一个或多个特定容器。默认情况下，如果没有指定容器，命令将显示所有运行容器的统计数据，如下截图所示：

![](img/Image00076.jpg)

`docker stats` 命令接受选项，包括：

- `--no-stream`：这将禁用流式统计并仅获取第一个结果。
- `-a`（`--all`）：这将显示所有容器（而不仅仅是运行中的容器）的统计数据。

统计数据可以用来查看我们的容器在运行时的表现是否良好。这些信息对于检查我们是否需要对容器应用某些限制非常有用，我们将在本章稍后部分介绍运行时限制。

查看日志、容器元数据和运行统计数据，这为你监控运行中的容器提供了近乎无限的可能性。此外，我们还可以全局地查看 Docker 宿主机上发生了什么。当宿主机上的 Docker 引擎接收到命令时，它会发布一个我们可以观察的事件。让我们现在来看这种机制。

### 容器事件

为了实时观察进入 Docker 引擎的事件，我们使用 `docker events` 命令。如果容器已经启动、停止、暂停等，该事件就会被发布。如果你想知道容器运行期间发生了什么，这非常有用。这是一项强大的监控功能。Docker 容器会报告大量的事件，你可以通过 `docker events` 命令列出这些事件。该列表包括：

```text
attach, commit, copy, create, destroy, detach, die, exec_create, exec_detach, exec_start, export, health_status, kill, oom, pause, rename, resize, restart, start, stop, top, unpause, update
```

`docker events` 命令可以接受 `-f` 选项，如果你在寻找特定的内容，它可以过滤输出结果。如果没有提供过滤器，则所有事件都将被报告。目前可能的过滤器列表包括：

- `container (container=<name or id>)`
- `event (event=<event action>)`
- `image (image=<tag or id>)`
- `plugin (experimental) (plugin=<name or id>)`
- `label (label=<key> or label=<key>=<value>)`
- `type (type=<container or image or volume or network or daemon>)`
- `volume (volume=<name or id>)`
- `network (network=<name or id>)`
- `daemon (daemon=<name or id>)`

看看下面的示例。在一个控制台窗口中运行了 `docker events` 命令，而在另一个独立的控制台中执行了 `docker run rest-example`。如如下截图所示，`docker events` 将为我们的 `rest-example` 容器报告 `create`、`attach`、`connect` 和 `start` 事件：

![](img/Image00077.jpg)

结果你将获得一个时间戳和事件名称，以及触发事件的容器 ID。`docker events` 命令可以接受额外的选项，如 `--since` 和 `--until`，用于指定你想要获取事件的时间范围。监控容器事件是查看 Docker 宿主机运行情况的极佳工具。然而，还有更多功能。例如，你还可以影响容器在崩溃情况下的行为。我们使用容器重启策略来实现这一点。

### 重启策略

通过在 `docker run` 命令中使用 `--restart` 选项，你可以指定重启策略。这告诉 Docker 在容器关闭时如何反应。然后容器可以重启以最大限度地减少停机时间，例如运行在生产服务器上时。然而，在我们解释 Docker 重启策略之前，让我们先关注一下退出码（exit codes）。退出码是至关重要的信息，它告诉容器运行失败或退出的原因。有时它与你传递给 `docker run` 作为参数的内部命令有关。当 `docker run` 命令以非零代码结束时，退出码遵循 `chroot` 标准，如下所示：

- 退出码 `125`：`docker run` 命令本身失败。
- 退出码 `126`：提供的命令无法被调用。
- 退出码 `127`：找不到提供的命令。
- 其他非零的、取决于应用程序的退出码。

如你可能记得，在之前的章节中，我们一直使用 `docker ps` 命令来列出运行中的容器。为了列出未运行的容器，我们可以为 `docker ps` 命令添加 `-a` 选项。容器完成后，可以在 `docker ps -a` 命令的输出的 `Status` 列中找到退出码。通过在启动容器时指定重启策略，可以自动重启崩溃的容器。指定所需的重启策略是通过 `docker run` 命令的 `--restart` 选项完成的，例如所示：

```bash
$ docker run --restart=always rest-example
```

目前 Docker 有四种重启策略。让我们现在一个一个了解它们，从最简单的 `no` 开始。

### `no`

`no` 策略是默认的重启策略，它简单地在任何情况下都不会重启容器。实际上，你不需要指定此策略，因为这是默认行为。除非你有某些用于运行 Docker 容器的可配置设置，否则 `no` 策略可以作为一个关闭开关。

### `always`

如果我们希望容器无论命令具有什么退出码都重启，则可以使用 `always` 重启策略。基本上，它顾言其实行；Docker 在每种情况下都会重启容器。重启策略将始终重启容器。即使容器在重启之前已经停止，情况也是如此。每当 Docker 服务重启时，使用 `always` 策略的容器也将被重启，无论它们之前是否正在执行任务。

使用 `always` 重启策略，Docker 守护进程将尝试无限地重启容器。

### `on-failure`

这是一种特殊的重启策略，可能也是常用的一种。通过使用 `on-failure` 重启策略，你指示 Docker 每当容器以非零退出状态退出时重启你的容器，否则不重启。这就是我们从退出码开始解释重启策略的原因。你可以可选地为 Docker 提供尝试重启的次数。这种重启策略的语法也不同，因为使用此策略时，你还可以指定自动重启的最大次数。

考虑这个示例：

```bash
$ docker run --restart=on-failure:5 rest-example
```

上述命令将运行我们的 REST 服务，并在失败时尝试重启 5 次。`on-failure` 重启策略的主要优势是，当应用程序以成功退出码退出（这意味着应用程序没有错误；它只是执行完毕），容器将不会重启。容器的重启次数可以通过我们已经知道的 `docker inspect` 命令获取。例如，获取特定 ID 或名称容器的重启次数：

```bash
$ docker inspect -f "{{ .RestartCount }}" <ContainerID>
```

你也可以发现容器再次启动的时间：

```bash
$ docker inspect -f "{{ .State.StartedAt }}" <ContainerID>
```

你应该知道 Docker 在重启容器之间使用延迟，以防止洪水式攻击保护。这是一个不断增加的延迟；它从 100 毫秒开始，然后 Docker 将之前的延迟翻倍。实际上，守护进程将等待 100 ms，然后是 200 ms、400、800 等，直到达到 `on-failure` 限制，或者你使用 `docker stop` 停止容器，或者执行 `docker rm -f` 命令强制删除。

如果容器成功重启，延迟将重置为默认值 100 毫秒。

### `unless-stopped`

同样，与 `always` 类似，如果我们希望容器无论退出码如何都重启，我们可以使用 `unless-stopped`。`unless-stopped` 重启策略的作用与 `always` 相同，但有一个例外：它会无论退出状态如何重启容器，但如果容器在此之前处于停止状态，则不会在守护进程启动时启动它。这意味着通过使用 `unless-stopped` 重启策略，如果容器在重启之前处于运行状态，则容器将在系统重启后重新启动。当 Docker 容器内的应用程序退出时，该容器也将停止。如果容器内运行的应用程序崩溃，容器将停止，并且该容器将保持停止状态，直到有人或某物重启它。

在对容器应用重启策略之前，最好先思考一下容器将用于执行什么种的工作。这取决于取决于运行在容器上的软件类型。例如，数据库可能应该应用 `always` 或 `unless-stopped` 策略。如果你的容器应用了某些重启策略，当你使用 `docker ps` 命令列出容器时，它将显示为 `Restarting` 或 `Up` 状态。

### 更新正在运行的容器的重启策略

有时，在容器启动后有必要实时（on the fly）更新 Docker 运行时参数。例如，你想防止容器在 Docker 主机上消耗过多资源。要在运行时设置策略，我们可以使用 `docker update` 命令。除了其他运行时参数（例如内存或 CPU 限制，我们将在本章稍后部分讨论）之外，`docker update` 命令还提供了更新正在运行容器重启策略的选项。语法非常直观，你只需要提供希望让容器拥有的新重启策略以及容器的 ID 或名称即可：

```bash
$ docker update --restart=always <CONTAINER_ID or NAME>
```

在容器上运行 `docker update` 命令后，新的重启策略将立即生效。另一方面，如果你在一个已停止的容器上执行 `update` 命令，该策略将在你以后启动容器时生效。可能的选项与你启动容器时可以指定的选项完全相同：

- `no`（默认值）
- `always`
- `on-failure`
- `unless-stopped`

如果你在 Docker 主机上运行了多个容器，并想一次性为所有容器指定新的重启策略，只需提供它们所有的 ID 或名称，并用空格隔开即可。

你还可以使用 `docker events` 命令查看应用了什么重启策略，你已经在上一节中了解了。`docker events` 可用于观察容器报告的运行时事件历史，它也会报告 `docker update` 事件，为你提供有关更改的详细信息。如果容器应用了重启策略，该事件将被发布。如果你想检查正在运行容器的重启策略，请使用 `docker inspect` 配合容器 ID 或名称，并将 `--format` 参数设置为值的路径：

```bash
$ docker inspect --format '{{ .HostConfig.RestartPolicy.Name }}' <ContainerID>
```

这种以单个容器为单位设置重启策略的能力，对于那些镜像是自包含的且不需要执行更复杂的编排任务的情况非常有用。重启策略并不是你可以在运行的容器上更改的唯一参数。

### 资源的运行时限制

在运行时限制 Docker 容器对资源的使用可能是很有用的。Docker 提供了许多可能性来对内存、CPU 使用或磁盘访问使用设置限制。让我们从设置内存限制开始。

### 内存

值得性，默认情况下（即如果你使用默认设置且不带任何限制），运行的容器可以使用所有的主机内存。要更改此行为，我们可以使用 `docker run` 命令的 `--memory`（或简写为 `-m`）开关。它接受常用的后缀 `k`、`m` 或 `g` 分别表示千字节、兆字节和吉字节。

设置了内存限制的 `docker run` 命令语法如下：

```bash
$ docker run -it -m 512m ubuntu
```

前面的命令将执行 `ubuntu` 镜像，容器可以使用的最大内存为半个千字节。

如果你不设置容器可以分配的内存限制，可能会导致随机问题，即单个容器很容易让整个主机系统变得不稳定和或不可用。因此，始终在容器上使用内存限制是一个明智的决定。

除了用户内存限制外，还有内存预留（memory reservation）和内核内存限制。让我们解释一下什么是内存预留限制。在正常工作条件下，运行的容器可以并且可能会使用需要的所有内存，直到达到你使用 `docker run` 命令的 `--memory`（`-m`）开关设置的限制为止。当应用内存预留时，Docker 将检测到低内存情况，并尝试强制容器将其消耗限制在预留限制范围内。如果你不设置内存预留限制，它将与 `-m` 开关设置的硬内存限制完全相同。

内存预留并不是一个硬限制功能。无法保证限制不会被超过。内存预留功能将尝试根据预留设置确保内存被分配。

考虑以下示例：

```bash
$ docker run -it -m 1G --memory-reservation 500M ubuntu /bin/bash
```

前面的命令将硬内存限制设置为 `1G`，并将内存预留设置为 `500M`。在设置了限制的情况下，当容器消耗内存超过 `500M` 但少于 `1G` 时，Docker 将尝试将内存缩小到 `500M`。

在下一个示例中，我们不在设置硬内存限制的情况下设置内存预留：

```bash
$ docker run -it --memory-reservation 1G ubuntu /bin/bash
```

在前面的示例中，当容器启动时，它可以根据需要获取大量内存。`--memory-reservation` 开关设置将防止容器长时间消耗内存。

内核内存与用户内存完全不同，主要区别是内核内存无法交换到磁盘。它包括栈页（stack pages）、内存页（slab pages）、套字内存压力和 TCP 内存压力。你使用 `--kernel-memory` 开关来设置内核内存限制以约束这些内存。与设置用户内存限制一样，只需提供带有后缀的数字，如 `k`、`m` 和 `g` 分别表示千字节、兆字节或吉字节，尽管设置千字节的情况很少见。

例如，每个进程都会消耗一些栈页。通过限制内核内存，你可以在内核内存使用过高时防止启动新进程。由于由于由于无法将内核内存交换到磁盘，容器可能会通过消耗过多内核内存阻塞整个主机服务。

设置内核内存限制非常直观。我们可以单独设置 `--kernel-memory` 而不通过 `-m` 限制总内存，如下所示：

```bash
$ docker run -it --kernel-memory 100M ubuntu /bin/bash
```

在前面的示例中，容器中的进程可以根据需要获取内存，但它只能消耗 `100M` 的内核内存。我们也可以设置硬内存限制，如下命令所示：

```bash
$ docker run -it -m 1G --kernel-memory 100M ubuntu /bin/bash
```

在前面的命令中，我们同时设置了内存和内核内存，因此容器中的进程总共可以使用 `1G` 内存，而这 `1G` 包含了 `100M` 的内核内存。

运行容器时，另一个非常有用的内存相关限制是交换倾向（swappiness）限制。我们通过在 `docker run` 命令中使用 `--memory-swappiness` 参数来应用该限制。当你想要避免与内存交换相关的性能下降时，这非常有帮助。`--memory-swappiness` 参数的参数是允许交换出的匿名内存页的百分比，因此取值范围从 `0` 到 `100`。将该值设置为零将根据你的内核版本禁用交换或使用最小的交换。相比之下，将值设置为 `100` 则将所有匿名页设置为交换出的候选对象。例如：

```bash
$ docker run -it --memory-swappiness=0 ubuntu /bin/bash
```

在前面的命令中，我们为我们的 `ubuntu` 容器完全关闭了交换。

除了设置内存使用限制外，你还可以指示 Docker 如何将处理器功率分配给它将运行的容器。

### 处理器

通过使用 `docker run` 命令的 `-c`（或等等的 `--cpu-shares`）开关，可以指定容器可以分配的 CPU 份额值。默认情况下，每个新容器都有 1024 个 CPU 份额，所有容器都获得相同部分的 CPU 周期。此百分比可以通过调整容器 CPU 份额权重相对于所有其他运行容器的权重来更改。但请注意，你无法设置容器可以使用的精确处理器速度。这是一个相对权重，与实际处理器速度无关。事实上，没有办法可以精确地表示容器有权仅使用主机处理器的 2 GHz。

CPU 份额只是一个数字，它与 CPU 速度完全无关。



如果我们启动两个容器且它们都使用 100% 的 CPU，则处理器时间将在两个容器之间平分。这是因为两个容器将相同数量的处理器份额。但如果我们将一个容器的处理器份额限制为 512，它将只获得一半的 CPU 时间。这并不意味着它只能使用一半的 CPU；该比例仅在 CPU 密集型进程运行时生效。如果另一个容器（具有 `1024` 份额）处于空闲状态，我们的容器将允许使用 100% 的处理器时间。实际的 CPU 时间将取决于系统上运行容器的数量。通过一个具体的例子更容易理解。

考虑三个容器，其中一个（我们称之为 `Container1`）的 `--cpu-shares` 设置为 `1024`，另外两个（`Container2` 和 `Container3`）的 `--cpu-shares` 设置为 `512`。当三个容器中的进程都尝试使用所有 CPU 功率时，`Container1` 将获得总 CPU 时间的 50%，因为与所有其他运行容器（`Container2` 和 `Container3`）之和相比，它允许的 CPU 使用率为一半。如果我们添加第四个具有 `--cpu-share` 为 `1024` 的容器 `Container4`，我们的第一个 `Container1` 将仅获得 33% 的 CPU，因为它现在相对分配了总三分之一的 CPU 功率。`Container2` 将获得 16.5%，`Container3` 也是 16.5%，而最后一个 `Container4` 再次被允许使用 33% 的 CPU。

虽然 `docker run` 命令的 `-c` 或 `--cpu_shares` 标志修改了容器相对于所有其他运行容器的 CPU 份额权重，但它并没有限制容器对主机的 CPU 使用。但还有另一个限制容器 CPU 使用的标志：`--cpu-quota`。它的默认值为 `100000`，意味着允许 100% 的 CPU 使用配额。我们可以使用 `--cpu-quota` 来限制 CPU 使用，例如：

```
$ docker run -it --cpu-quota=50000 ubuntu /bin/bash
```

在前面的命令中，容器的限制将是 CPU 资源的一个 50%。`--cpu-quota` 通常与 `docker run` 的 `--cpu-period` 标志配合使用。这是 CPU CFS（完全公平调度器）周期的设置。默认周期值为 100000，即 100 毫秒。请看这个示例：

```
$ docker run -it --cpu-quota=25000 --cpu-period=50000 ubuntu /bin/bash
```

这意味着容器每 50 ms 就可以获得 50% 的 CPU 使用率。

限制 CPU 份额和使用并不是我们可以在容器上设置的唯一处理器相关限制。我们还可以将容器的进程分配到特定的处理器或处理器核心。当我们想要时，`docker run` 命令的 `--cpuset` 开关就非常有用。考虑以下示例：

```
$ docker run -it --cpuset 4 ubuntu
```

前面的命令将运行 `ubuntu` 镜像并允许容器使用所有四个处理器核心。要启动容器并仅允许一个处理器核心，你可以将 `--cpuset` 值改为 `1`：

```
$ docker run -it --cpuset 1 ubuntu
```

务必注意 `Docker` 在容器启动期间或动态更新约束时输出的警告，可能会出现你的约束未生效的情况！

我们已经知道如何使用命令行命令来运行和观察容器。然而，如果你需要在开发流程中启动容器（例如用于集成测试），这就会非常不利。我们在第 5 章 *使用 Java 应用创建镜像* 中一直使用的用于构建镜像的 Fabric8 Docker Maven 插件，在我们需要运行容器时也大大派用用场。让我们现在就开始操作吧。

## 使用 Maven 运行

该插件提供了两个与启动和停止容器相关的 Maven 目标（goals）。它们是 `docker:start` 和 `docker:stop`。容器通过 `docker:start` 创建并启动，通过 `docker:stop` 停止并销毁。如果你在集成测试期间需要运行容器，典型的用例是将这些目标包含在 Maven 构建阶段中：将 `docker:start` 绑定到 `pre-integration-test` 阶段，并将 `docker:stop` 绑定到 `post-integration-test` 阶段。

### 插件配置

插件使用 `pom.xml` 文件中 `<configuration>` 下的 `<run>` 子元素的配置。最重要的配置元素列表如下：

| 配置元素 | 说明 |
|---|---|
| `cmd` | 在容器启动结束时应执行的命令。如果没有给出，则使用镜像的默认命令。 |
| `entrypoint` | 容器的入口点。 |
| `log` | 日志配置，决定是否以及如何打印来自运行容器的日志消息。这也可以配置使用的日志驱动程序。 |
| `memory` | 以字节为单位的内存限制。 |
| `namingStrategy` | 创建容器名称的命名策略。`none`：使用 Docker 随机分配的名称（默认）；`alias`：使用镜像配置中指定的别名。如果已存在同名容器，则抛出异常。 |
| `network` | `<network>` 元素可用于配置容器的网络模式。它包含以下子元素：`<mode>`：网络模式，可以是以下值之一；`bridge`：与默认 Docker 桥接的桥接模式（默认）；`host`：共享 Docker 宿主机网络接口；`container`：连接到指定容器的网络。容器的名称取自 `<name>` 元素；`custom`：使用自定义网络，必须在使用 `Docker network create` 之前创建；`none`：不设置网络。 |
| `ports` | `<ports>` 配置包含端口映射列表。每个映射包含多个部分，每个部分之间用冒号分隔。这等同于使用 `docker run` 命令配合 `-p` 选项时的端口映射。 |
| `restartPolicy` | 提供我们在本章稍后讨论过的重启策略。 |
| `volumes` | 用于绑定到宿主机的 `volumes` 配置。 |

`ports` 配置的示例条目如下：

```xml
<ports>
  <port>8080:8080</port>
</ports>
```

`restartPolicy` 配置的示例条目如下：

```xml
<restartPolicy>on-failure</restartPolicy>
```

`volumes` 配置的示例条目如下：

```xml
<volumes>
  <volume source="/host/path" target="/container/path"/>
</volumes>
```

## 总结

在本章中，我们学习了如何管理容器的周期，使用不同的运行模式（前台和后台）启动它，停止或删除它。我们还知道如何通过执行以下命令停止它：

```
$ mvn docker:stop
```

10 秒后（正如你记得容器那样），Maven 将输出容器已停止：

```
[INFO] DOCKER> "rest-example":0.1.0] Stop and removed container 51660084f0d after 0 ms
```

让我们再次运行容器，这次使用 Maven `docker:run` 目标：

```
$ mvn clean package docker:run
```

这次 Maven 插件将运行容器，我们在控制台上看到了 Spring Boot 的横幅，如下：

我猜你现在可以识别 `docker:start` 和 `docker:run` 之间的差异了。没错，`docker:run` 等于 `docker run` 命令的 `-i` 选项。`docker:run` 还会自动开启 `showLogs` 选项，让你能看到容器内部发生了什么。作为替代方案，你可以通过系统属性提供 `docker.follow`，这样 `docker:start` 将永远不会返回，直到按下 `CTRL + C` 为止，这与你执行 `docker:run` Maven 目标完全相同。

正如你所见，Fabric8 Docker Maven 插件提供了与你在 Shell 或命令行中运行和停止容器时相同的控制力。但 Maven 过程本身的优势在于此：你可以实现自动化。Docker 容器现在可以用于构建、集成测试以及你可能拥有的持续交付流程；随你怎么命名。

## Kubernetes 简介

在阅读了第 6 章，*使用 Java 应用程序运行容器*之后，你已经掌握了许多关于使用 Docker 打包 Java 应用程序的知识。现在是时候更进一步，关注我们所缺失的——容器管理和编排了。市场上有一些合适的工具，例如 `Nomad`、`Docker Swarm`、`Apache Mesos` 或 `AZK`。在本章中，我们将关注可能最流行的一个：Kubernetes。

Kubernetes（有时称为 `k8s`）是由 Google 在 2015 年创建的用于 Docker 容器的开源编排系统。Google 开发的第一个统一容器管理系统是内部称为 `Borg` 的系统；Kubernetes 是它的后代。

本章涵盖的主题如下：

- 我们为什么以及何时需要容器管理
- Kubernetes 简介
- Kubernetes 基础概念

让我们从回答这个问题开始：我们为什么需要 Kubernetes？我们将看看容器管理和编排背后的原理。

### 为什么我们需要 Kubernetes？

如你所知，Docker 容器为运行封装成微小、独立软件单元的 Java 服务提供了极大的灵活性。Docker 容器使得应用程序的组件具有可移植性——你可以在不同的环境之间移动单个服务，而无需担心依赖项或底层操作系统。只要操作系统能够运行 `Docker engine`，你的 Java 容器就可以运行在该系统上。

此外，正如你在第 1 章，*Docker 简介*中所记忆的，Docker 的容器隔离概念与传统的虚拟化完全不同。区别在于 Docker 容器利用宿主机操作系统的资源——它们轻量、快速且易于启动。

这一切都很好，但存在一些风险。你的应用程序由多个独立的微服务组成。服务的数量会随着时间的推移并且很可能会增长。此外，如果你的应用程序开始承受更高的负载，增加相同服务的容器数量以分担负载是非常好的。

这并不意味着你只需要使用自己的服务器基础设施——你的容器可以进入云端。今天我们有很多云供应商，例如 `Google` 或 `Amazon`。拥有在云端运行容器的可能性带给你很多优势。首先，你不需要管理自己的服务器。其次，在大多数云中，你只需为实际使用付费。

如果负载出现峰值，云服务的成本会增加，因为你使用了更多的计算能力。但如果没有负载，你无需支付任何费用。这很容易说，但监控你的服务器使用情况，尤其是当运行带有大量组件的应用程序时，可能是棘手的。你需要仔细查看云厂商的账单，确保你没有容器在云端空转且无所事事。

如果某个特定服务对你的应用程序并不重要且不需要快速响应，你可以将其移动到最便宜的机器上。另一方面，如果另一个服务经历了更高的负载且至关重要，你将希望将其移动到更强大的机器上或启动它的更多实例。

最好的是，通过使用 Kubernetes，这一切是可以自动化的。通过拥有管理 Docker 容器的正确工具，可以动态完成。你的应用程序可以以非常敏捷的方式进行自适应——终端用户可能甚至不知道他们正在使用的应用程序位于何处。

容器管理和监控软件可以通过更好地利用你所付费的硬件来大幅降低硬件成本。Kubernetes 处理在计算集群节点上的调度，并积极管理工作负载，以确保它们状态与用户声明的意图相匹配。通过 `labels`（标签）和 `Pods`（我们将在本章稍后介绍）的概念，Kubernetes 将组成应用程序的容器分组为逻辑单元，以便管理和发现。

将你的应用程序以运行在托管环境中容器集的形式存在，也改变了软件开发的视角。你可以开发新版本的服务，并在其准备就绪时动态地进行滚动更新。这意味着关注应用程序本身而非运行它的机器，结果这允许开发团队以更加灵活、更小且更模块化的方式运行。它让软件开发变得真正敏捷，这正是我们一直追求的。

微服务是小且独立的，构建和部署时间大大缩短。此外，发布风险更小，因此你可以更频繁地发布更小的更改，最大限度地减少一次性发布所有内容时可能发生的巨大失败风险。

在我们开始 Kubernetes 基础概念之前，让我们列一下 Kubernetes 为我们提供的功能：

- 快速且可预测地部署应用程序
- 动态扩展
- 无缝发布新功能
- 容错能力
- 仅将硬件使用限制在所需的资源上
- 敏捷应用程序开发
- 操作系统、主机和云供应商之间的可移植性

这是一个无法轻易超越的特性列表。要理解如何实现这一点，我们需要理解 Kubernetes 的核心概念。到目前，我们只知道一个来自 Docker 的单一概念——容器——它是可移植、独立的软件单元。容器可以包含我们想要的任何内容，无论是数据库还是 `Java REST microservice`。让我们来了解剩余的部分。

### Kubernetes 基础概念

集群是一组节点；它们可以是物理服务器或安装了 Kubernetes 平台的虚拟机。基础 Kubernetes 架构如图所示：

![基础 Kubernetes 架构](img/Image00080.jpg)

如你所见，Kubernetes 集群由一个 `Master node`（主节点）和若干带有某些组件的 `worker nodes`（工作节点）组成。虽然乍看之下可怕且复杂，但如果我们从 Pod 开始逐一描述概念将会更容易理解。

### Pod

Pod 由一个或多个 Docker 容器组成。它是 Kubernetes 平台的基本单元以及 Kubernetes 工作的基础执行单元。Pod 的图如下：

![Pod 架构](img/Image0081.jpg)

运行在同一个 Pod 中的容器共享相同的公共网络命名空间、磁盘和安全上下文。事实上，建议在同一个 Pod 的容器之间通过 `localhost` 进行通信。每个容器也可以与集群内的任何其他 Pod 或服务通信。

正如你在第 2 章，*网络与持久化存储*中所记忆的，你可以在 Docker 容器中挂载卷。Kubernetes 也支持卷的概念。附加到 `Pod` 的卷可以挂载到该 Pod 上的一个或多个容器内部。Kubernetes 支持许多不同的卷类型，原生支持挂载 GitHub 仓库、网络磁盘、本地硬盘等。

如果你的应用程序需要分布式存储并需要处理大量数据，你并不局限于本地硬盘。Kubernetes 还支持 `Volume Providers`（卷提供者）。目前，可用的持久化卷提供者列表包括：

- `GCE`：即 Google 云平台。
- `AWS`：Amazon 云服务。
- `GlusterFS`：一种可扩展的网络文件系统。使用免费且开源的 `GlusterFS`，你可以利用现有的存储硬件创建大型的分布式存储解决方案。
- `OpenStack Cinder`：为 OpenStack Nova 计算平台用户提供的块存储服务。
- `CephRBD`：一个**可靠的自治分布式对象存储系统**（`RADOS`），它为你的应用程序提供单一统一存储集群中的对象、块和文件系统存储。
- `QuoByte`
- `Kube-Aliyun`



网络命名空间和卷并不是 `Pod` 的唯一属性。正如你在 `Pod` 结构图中所示，`Pod` 可以附带标签（labels）和注解（annotations）。

标签在 Kubernetes 中非常重要。它们是附加到对象（在本例中是 `Pods`）上的键值对。标签背后的理念是它们可以被用于标识对象——标签对用户来说是有意义且相关的。标签的一个示例可能是：

```
app=my-rest-service
layer=backend
```

之后，我们将使用标签选择器（label selectors）来选择具有指定标签的对象（如 `Pod`）。通过标签选择器（它是 Kubernetes 中的核心分组原语），客户端或用户可以识别一个对象或一组对象。选择器与标签类似，也是一种键值表达式，用于通过使用匹配的标签来识别资源。例如，选择器表达式 `app = my-rest-service` 将选择所有标签为 `app = my-rest-service` 的 `Pod`。

另一方面，注解是可以附加到 `Pod` 上的某种元数据。它们并不是用于标识的属性；而是可以被工具或库读取的属性。关于注解应该包含什么没有任何规定——这取决于你。注解可以包含信息，如构建或发布版本、时间戳、Git 分支名称、Git `pull` 请求数，或任何内容，如手机号。

标签旨在标识有关 Kubernetes 对象（如 `Pods`）的信息。而注解仅仅是附加到对象上的元数据。

我们之前提到过，`Pod` 是 Kubernetes 中基本的执行单元。它可以包含多个容器。一个包含多个 Docker 容器的 `Pod` 的现实示例可以是我们的 Java REST 微服务 `Pod`。

在之前的章节的示例目的中，我们的微服务一直将它的数据库数据存储在内存中。在现实生活中，数据可能应该存入真实的数据库中。我们的 `Pod` 可能会有一个包含 Java JRE 和 Spring Boot 应用程序本身的容器，以及另一个带有 PostgreSQL 数据库的容器，微服务使用该数据库来存储数据。这两个容器共同构成一个 `Pod`——一个单一、解耦的执行单元，包含了我们 REST 服务运行所需的所有内容。

`Pod` 的定义是一个称为 `Pod` 清单的 JSON 或 YAML 文件。看这个包含一个容器的简单示例：

```
apiVersion: v1
kind: Pod
metadata:
   name: rest_service
spec:
   containers:
      name: rest_service
      image: rest_service
         ports:
  - containerPort: 8080
```

JSON 文件中的相同 `pod` 清单看起来如下所示：

```json
{
  "apiVersion": "v1",
  "kind": "Pod",
  "metadata": {
    "name": "rest_service",
    "labels": {
      "name": "rest_service"
    }
  },
  "spec": {
    "containers": [{
      "name": "rest_service",
      "image": "rest_service",
      "ports": [{"containerPort": 8080}]
    }]
  }
}
```

容器的 `image` 是 Docker 镜像名称。`containerPort` 暴露了该 REST 服务容器的端口，以便我们可以通过 `Pod` 的 IP 连接到服务。默认情况下，正如你从第 1 章 *Docker 简介* 中记忆的那样，`image` 中定义的入口点将是运行的内容。

意识到 `Pod` 的生命是脆弱的非常重要。因为 `Pod` 被视为无状态的、独立的单元，如果其中一个 `Pod` 不健康或正被替换为新版本，Kubernetes Master 不会对其留情面——它会直接杀死并丢弃它。

事实上，`Pod` 具有严格定义的生命周期。以下列表描述了 `Pod` 生命的阶段：

- `pending`（等待）：此阶段意味着 `Pod` 已被 Kubernetes 系统接收，但一个或多个 Docker 容器镜像尚未创建。`Pod` 可能会在此阶段持续一段时间——例如，镜像需要从互联网下载。
- `running`（运行）：`Pod` 已放置在节点上，并且所有的 Docker 容器都已创建。
- `succeeded`（成功）：`Pod` 中的所有 Docker 容器都已以成功状态终止。
- `failed`（失败）：`Pod` 中的所有 Docker 容器都已终止，但至少有一个容器以失败状态终止，或被系统终止。
- `unknown`（未知）：这通常表示与 `Pod` 宿主的通信存在问题；由于某种原因，无法获取 `Pod` 的状态。

当一个 `Pod` 被关闭时，并不仅仅是因为它失败了。更多情况下，如果我们的应用程序需要处理增加的负载，我们需要运行更多的 `Pod`。另一方面，如果负载降低或完全没有负载，那么运行许多 `Pod` 就没有意义了——我们可以丢弃它们。当然，我们可以手动启动和停止 `Pod`，但自动化总是更好的。这引入了 `ReplicaSets`（副本集）的概念。

### ReplicaSets

`ReplicaSets` 是通过复制来扩展应用程序的概念。Kubernetes 有什么用？通常，你可能想要复制你的应用程序（事实上），出于以下几个原因，包括：

- **扩展性**：当负载增加并对于现有实例数量来说过重时，Kubernetes 允许你扩展应用程序，根据需要创建额外的实例。
- **负载均衡**：我们可以轻松地将流量分配到不同的实例，以防止单个实例或节点过载。负载均衡由于 Kubernetes 的架构是开箱即用的，非常方便。
- **可靠性与容错性**：通过拥有应用程序的多个版本，你可以防止其中一个或多个实例失败时出现问题。如果系统能够替换任何失败的实例，这一点尤为真实。

复制适用于许多用场景，包括基于微服务的应用程序（其中多个独立服务提供特定功能），或基于“任何组件都可能在随时失败”理论的云原生应用程序。复制是实现它们的完美解决方案，因为多个实例自然地符合该架构。

`ReplicaSet` 确保在任何时刻都有指定数量的 `Pod` 副本（称为 `replicas`）在运行。如果数量太多，它们将被关闭。如果需要更多（例如某些副本因为错误或崩溃而死亡，或者负载更高），则会启动更多的 `Pod`。`ReplicaSets` 被 `Deployment` 使用。让我们来看看 `Deployment` 是什么。

### Deployment

`Deployment` 负责创建和更新应用程序实例。一旦创建了 `Deployment`，Kubernetes Master 会将应用程序实例调度到集群中的各个节点。`Deployment` 是一个更高层次抽象；它在进行 `Pod` 编排、创建、删除和更新时管理 `ReplicaSets`。`Deployment` 为 `Pod` 和 `ReplicaSets` 提供了声明式更新。`Deployment` 允许轻松更新 `ReplicaSet`，并能够回滚到之前的部署。

你只需要指定所需的副本数量以及每个 `Pod` 中运行的容器，`Deployment` 控制器就会启动它们。YAML 文件中的 `Deployment` 清单定义如下：

```yaml
apiVersion: 1.0
kind: Deployment
metadata:
  name: rest_service-deployment
spec:
  replicas: 3
  template:
    metadata:
      labels:
        app: rest_service
    spec:
      containers:
      - name: rest_service
        image: rest_service
        ports:
        - containerPort: 8080
```

在上一个示例中，`Deployment Controller` 将创建一个包含三个 `Pod` 的 `ReplicaSet`，这些 `Pod` 运行我们的 Java REST 服务。

`Deployment` 是一种控制结构，负责 `Pod` 的启动和销毁。`Deployment` 通过创建或关闭副本来管理单个 `Pod` 或一组 `Pod` 的状态。`Deployments` 同时也管理 `Pod` 的更新。`Deployments` 是一种高级别的抽象，它们创建 `ReplicaSets` 资源。`ReplicaSets` 监控 `Pod` 并确保始终运行正确数量的副本。

当你想要更新一个 `Pod` 时，你需要修改 `Deployment` 的清单文件。这种修改将创建一个新的 `ReplicaSet`，该集合将会扩容，而之前的 `ReplicaSet` 将收缩，从而为你的应用程序提供无停机部署。

`Deployments` 的主要目的是执行滚动更新（rolling updates）和回滚（rollbacks）。滚动更新是以顺序、逐个的方式将应用程序更新到新版本的过程。通过一次更新一个实例，你可以保持应用程序的运行。如果你同时更新所有实例，你的应用程序可能会经历停机。此外，执行滚动更新允许你在过程中捕获错误，以便在影响所有用户之前进行回滚。

`Deployment` 还允许我们进行轻松的回滚。要进行回滚，我们只需将想要回滚的版本设置为目标版本即可。Kubernetes 会扩容对应的 `ReplicaSet` 并收缩当前的，这将导致回滚到服务的指定版本。事实上，我们将在第 8 章 *使用 Java 使用 Kubernetes* 中大量使用 `Deployments` 来向集群发布服务的更新。

复制（Replication）是 Kubernetes 功能的大部分。正如你所看到的，`Pod` 的生命是脆弱且短暂的。因为 `Pods` 及其克隆体一直在来去，我们需要某种持久且具体的东西，某种永远存在的东西，以便我们应用程序的用户（或其他 `Pods`）可以发现并调用。这引出了我们 Kubernetes 服务（services）的概念。让我们现在关注它们。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

### Services

Kubernetes `services` 将一个或多个 `Pods` 分到一个需要长时间运行且外部可的内部或外部过程中，例如我们的 Java REST API 端点或数据库主机。这就是我们给 `Pods` 赋予标签（labels）变得非常重要的地方；服务通过查找特定标签来寻找并分组 `Pods`。我们使用标签选择器来选择具有特定标签的 `Pods`，并将服务或 `ReplicaSets` 应用于它们。其他应用程序可以通过 Kubernetes 服务发现找到我们的服务。

服务是 Kubernetes 用于向一个或多个 `Pods` 提供网络连接的抽象。虽然（正如你从 Docker 网络章节中所记忆的），Docker 默认使用主机私有网络，容器只有在它们位于同一台主机上时才能相互通信。在 Kubernetes 中，集群中的 `Pods` 可以与其他 `Pods` 通信，无论它们落在哪个主机上。这是通过服务实现的。

每个服务都有其自己的 IP 地址和端口，该地址和端口在服务的整个生命周期内保持不变。服务具有集成的负载均衡器，可以将网络流量分发到所有 `Pods`。虽然 `Pod` 的生命由于根据应用程序需求被启动或销毁而可能是脆弱的，但服务是一个更持久的概念。

每个 `Pod` 都有自己的 IP 地址，但当它死亡而另一个被创建时，IP 地址可能会有所不同。这可能会成为一个问题——如果一组 `Pods` 为 Kubernetes 集群内部的其他 `Pods` 提供功能，人们可能会丢失另一个的 IP 地址。服务通过分配生命周期的 IP 地址解决了这个问题。

服务抽象实现了解耦。假设我们在 Spring Boot 应用程序之上运行我们的 Java REST 服务。我们需要一种方法从互联网将 HTTP 请求（如 `GET` 或 `POST`）路由到我们的 Docker 容器。我们将通过设置一个 Kubernetes 服务来实现这一点，该服务使用负载均衡器将来自公共 IP 地址的请求路由到其中一个容器。

我们将带有 REST 服务的容器分组到一个 `Pod` 中并命名，例如命名为 `Our little REST service`。然后我们将定义一个 Kubernetes 服务，为 `Our little REST service` `Pod` 中的任何容器提供 `8080` 端口的服务。Kubernetes 然后将使用负载均衡器在指定的容器之间分配流量。

让我们总结一下 Kubernetes 服务的功能：

- 服务是持久且永久的。
- 它们提供发现。
- 它们提供负载均衡。
- 它们暴露稳定的网络 IP 地址。
- 它们通过标签的使用查找并分组 `Pods`。

我们已经提到内置了服务发现机制。Kubernetes 支持两种查找服务的主要模式：环境变量和 DNS。服务发现是确定如何连接到服务的进程。Kubernetes 包含一个内置的 DNS 服务器用于此目的：`kube-dns`。

### kube-dns

Kubernetes 提供了一个 DNS 集群插件，每次集群启动时都会自动启动。DNS 服务本身作为集群服务运行——它就是 `SkyDNS`——这是一种构建在 `etcd` 之上的用于发布和发现分布式服务（你将在本章中了解什么是 `etcd`）。它利用 DNS 查询来发现可用的服务。它支持正向查询（A 记录）、服务查询（SRV 记录）和反向 IP 地址查询（PTR 记录）。

实际上，服务是 Kubernetes 分配 DNS 名称的唯一类型；Kubernetes 生成内部 DNS 条目，格式为 `service-name.namespace-name.svc.cluster.local`。这解析到服务的集群 IP。例如，对于名为 `my-rest-service` 的服务，DNS 插件将确保该服务对于集群中的其他 `Pods`（或其他服务）通过 `my-rest-service.default.svc.cluster.local` 主机可用。基于 DNS 的发现为跨集群连接服务提供了灵活且通的方法。

注意，当使用 `hostNetwork=true` 时，Kubernetes 将使用主机的 DNS 服务器，而不使用集群的 DNS 服务器。

### Namespace

`namespace`（命名空间）在 Kubernetes 内部作为一种分组机制。`Pods`、`volumes`、`ReplicaSets` 和 `services` 在命名空间内轻松协作，但命名空间提供了与集群其他部分的隔离。

这种隔离的可能用例是什么？嗯，命名空间允许你在同一个集群中管理不同的环境。例如，你可以在同一机器集群上拥有不同的测试环境和阶段环境。

这可能会节省你基础设施的一些资源，但可能是危险的；如果没有命名空间，在集群上发布软件新版本以测试环境是有风险的，因为预发布版本运行在同一个集群上。有了命名空间，你可以对集群中的不同环境进行操作而不必影响其他环境。

由于 Kubernetes 使用 `default` 命名空间，使用命名空间是可选的，但是推荐的。

我们已经解释了所有的 Kubernetes 抽象——我们知道有 `Pods`、`ReplicaSets`、`Deployments` 和服务。现在是时候进入 Kubernetes 架构的物理执行层了。所有微小而脆弱的 `Pods` 都需要运行的地方。它们运行在 `nodes`（节点）中，我们现在就要学习它们。

### Nodes（节点）

`node` 是 Kubernetes 架构中的干力。根据你的基础设施，它可以是虚拟机或物理机。工作节点（worker node）根据主节点（Master node）的指令运行任务，我们很快就会解释主节点。节点（在 Kubernetes 早期，它们被称为 `Minions`）可以运行一个或多个 `Pods`。它们在容器化环境中提供了特定应用的虚拟主机。

当工作节点崩溃时，运行在该节点上的 `Pods` 也会之崩溃。

下图显示了 `node` 的内容：

![](img/Image00082.jpg)

如你在上一个图中所示，Kubernetes 中的 `node` 内部运行着一些进程，每个进程都非常重要。让我们逐一解释它们的用途。

### Kubelet

`Kubelet` 可能是 Kubernetes 中最重要的控制器。它是一个响应来自主节点命令的进程（我们稍后会解释什么是主节点）。每个节点都有这个进程在监听。主节点调用它来管理 `Pods` 及其容器。

`Kubelet` 运行 `Pods`（如你所知，`Pods` 是共享 IP 和卷的容器集合）。`Kubelet`（[`kubernetes.io/v1.0/docs/admin/kubelet/`](https://kubernetes.io/v1.0/docs/admin/kubelet/)）负责单台机器上运行的内容，它有一个任务：给定一组要运行的容器，确保它们都在运行。

换句话说，`Kubelet` 是代理（agent）的名称，而 `node` 是我们对代理运行机器的称呼。值得知道，每个 `Kubelet` 还有一个内部的 `HTTP` 服务器，它监听 HTTP 请求并响应简单的 API 调用以提交新的清单文件（manifest）。

### Proxy（代理）



`proxy` 是一种网络代理，它创建一个客户端可以访问的虚拟 IP 地址。网络调用将透明地代理到 Kubernetes 服务中的 `Pods`。如你所知，服务提供了一种将 `Pods` 分组为单一业务进程的方法，可以通过公共访问策略进行访问。通过在 `node` 上运行 `proxy`，我们可以调用服务的 IP 地址。从技术上讲，节点的代理是一个 `kube-proxy` ([`kubernetes.io/docs/admin/kube-proxy/`](https://kubernetes.io/docs/admin/kube-proxy/)) 进程，通过编写 `iptables` 规则来拦截对服务 IP 地址的访问。Kubernetes 网络代理运行在每个节点上。没有它，我们就无法访问服务。

`kube-proxy` 只认识 UDP 和 TCP，不理解 HTTP，提供负载均衡，并仅用于访问服务。

### Docker

最后，每个节点都需要一些运行的东西。它将是一个 Docker 容器运行时，负责拉取镜像和运行容器。

所有节点像现实世界中的任何其他工作组一样，都需要一个管理器。在 Kubernetes 中，节点器的角色由一个特殊的节点承担：主节点。

### The Master node（主节点）

主节点不运行任何容器——它只处理和管理集群。主节点是中央控制点，提供了集群的统一视图。有一个主节点控制多个工作节点，这些工作节点实际上运行着我们的容器。主节点会自动处理 `Pods` 跨集群中工作节点的调度——通过考虑每个节点上的可用资源。主节点的结构如图所示：

![](img/Image00083.jpg)

让我们逐个解析主节点，从 `etcd` 开始。

### etcd

Kubernetes 将所有的集群状态存储在 [`etcd`](https://github.com/coreos/etcd) 中，这是一个具有强一致性模型的分布式数据存储。`etcd` 是一个分布式、可靠的键值存储，用于分布式系统最关键的数据，重点在于：

- **简单**：定义良好的、面向用户的 API
- **安全**：自动 TLS 带有可选的客户端证书认证
- **快速**：基准测试为每秒 10,000 次写入
- **可靠**：使用 Raft 进行分布

这些状态包括集群中存在哪些节点、哪些 `Pods` 应该运行、它们运行在哪些节点上以及大量其他。整个集群状态存储在 `etcd` 实例中。这提供了一种可靠存储配置数据的方法。运行主节点上的另一个关键组件是 API server。

### The API server（API 服务器）

主节点上的主要组件之一是 API server。它非常重要，以至于有时你会发现主节点被泛称为 API server。从技术上讲，它是一个名为 `kube-apiserver` 的进程，它使用 JSON 接收并响应 `HTTP` `REST` 请求。它的主要目的是为 API 对象（如 `Pods`、服务、`ReplicaSets` 等）对数据进行验证和配置。API server 提供了访问集群共享状态的前端，所有其他组件都通过它进行交互。API server 是中央管理实体，也是唯一连接到 `etcd` 的 Kubernetes 组件。所有其他组件都必须通过 API server 与集群状态交互。我们将在第 9 章 *Working With Kubernetes API* 中详细介绍 Kubernetes API。

主节点不运行任何容器——它只处理和管理集群。运行容器的节点是工作节点。

### The scheduler（调度器）

正如我们之前提到的，如果你创建一个 Deployment，主节点会将应用程序实例调度到各个节点。一旦应用程序实例运行，Deployment Controller 就会持续监控这些实例。这是一种自愈机制——如果某个节点宕机或删除，Deployment Controller 将替换它。

现在我们已经知道了构成 Kubernetes 架构的 Kubernetes 特定组件，让我们看看我们有哪些可用工具。

### Available tools（可用工具）

在本书的剩余部分，我们将使用几个工具。让我们从最重要的开始：`kubectl`。

### kubectl

`kubectl` 是用于对 Kubernetes 集群运行命令的命令行界面。事实上，这是与 Kubernetes 工作时最常用的命令。在第 8 章 *Using Kubernetes with Java* 中，我们将遍历命令的语法和可能的用法。通过 `kubectl`，你将与集群进行交互。

### Dashboard

Kubernetes Dashboard 是一个美观、简洁的 Kubernetes 集群 Web 端 UI。通过 Dashboard，你可以管理和排查集群本身以及运行在其中的应用程序。你可以说它是 Kubernetes 的用户界面。对于那些偏好使用图形化 UI 的人，Dashboard 是部署容器化应用程序和获取集群上运行应用程序概述的实用工具，还可以用于创建或修改单个资源，如 Deployments、Pods 和 services。例如，你可以缩放 Deployment 规模、启动滚动更新、重启 Pod，或使用部署向导（deploy wizard）部署新应用程序。我们将在第 8 章 *使用 Java 使用 Kubernetes* 中也会使用该 Dashboard。

### Minikube

运行集群似乎是一个需要大量设置的复杂过程。事实并非完全如此。实际上，在本地机器上启动并运行 Kubernetes 集群用于学习、测试和开发是非常容易的。可以在 GitHub 上的 [`github.com/kubernetes/minikube`](https://github.com/kubernetes/minikube) 找到 `minikube` 工具，它允许你自己在自己的机器上设置本地集群。它支持所有主流平台，包括 Linux、macOS 和 Windows。启动的集群将是一个单节点集群，但对于开始进行真实的 Kubernetes 示例绰绰有余。事实上，在第 8 章 *使用 Java 使用 Kubernetes* 中，在我们开始将 `REST` 服务部署到集群之前，我们将将在本地运行 Kubernetes。

除了之前提到的那些工具，你可能在互联网上发现许多与 Kubernetes 配合得很好的其他工具和程序。

### 总结

本章引入了许多新概念。让我们简要总结一下我们学到的 Kubernetes 架构。

Kubernetes (k8s) 是一个开源平台，用于自动化跨节点集群的容器操作，如部署、调度和伸缩性。使用 Kubernetes，你可以：

- 自动化容器的部署和复制
- 动态扩展和缩小容器的规模
- 将容器组织成组并在它们之间提供负载均衡
- 轻松发布新版本的应用程序容器
- 为你的应用程序提供容错机制——如果某个容器挂了，它会被替换
- Kubernetes 由以下部分组成：
  - **集群 (Cluster)**：一组节点。
  - **节点 (Nodes)**：作为工作节点的物理机或虚拟机。每个节点运行 `kubelet`、`proxy` 和 `Docker` 引擎进程。
  - **主节点 (Master node)**：提供集群的统一视图。它交付 Kubernetes API 服务器。API 服务器提供一个可以与集群交互的 `REST` 端点。主节点还包括用于创建和复制 Pods 的控制器。
  - **Pods**：调度到节点上。每个 Pod 运行单个容器或一组容器和卷。同一个 Pod 中的容器共享相同的网络命名空间和卷，并可以使用 `localhost` 相互相互通信。它们的生命是脆弱的；它们会不断出生和死亡。
  - **标签 (Labels)**：Pods 带有附加的键/值对标签。标签用于精确选择 Pods。
  - **服务 (Services)**：一种定义一组 Pods 及其访问策略的抽象。服务通过使用标签选择器（label selectors）找到它们的 Pod 组。因为单个 Pod 的 IP 可能会变化，服务为其客户端提供一个持久的 IP 地址供其使用。

这些理论内容可能让人感到有些无从下手。别担心，在第 8 章 *使用 Java 使用 Kubernetes* 中，我们将运行本地 Kubernetes 集群。我们的计划将包括使用 `minikube` 创建本地 Kubernetes 集群。然后我们将使用 Java REST 微服务部署并管理 Docker 容器。通过一些实际的、上手的操作，Kubernetes 架构将变得清晰得多。运行本地 Kubernetes 并不是我们要做的全部。之后在第 10 章 *在云端 Kubernetes 上部署 Java* 中，我们将把应用程序放在真实的云中——那是 Kubernetes 真正大放异彩的地方。

## 使用 Java 使用 Kubernetes

在第 7 章 *Kubernetes 简介* 中，我们学习了 Kubernetes 架构和概念。我们了解节点、Pods 和服务。在本章，我们将进行实操，并将我们的 Java REST 服务部署到本地 Kubernetes 集群中。为了学习目的，我们将使用 Minikube 工具在本地机器上创建一个集群。在本地机器上学习 Kubernetes 比一开始就去云端要简单。因为 Minikube 是在本地运行而不是通过云提供商运行，某些特定提供商的功能（如负载均衡器和持久化卷）将无法开箱即用。然而，你可以使用 `NodePort`、`HostPath`、持久化卷以及若干插件（如 DNS 或 dashboard）在推送到真实的生产级集群之前，先在本地测试你的应用。在第 10 章 *在云端 Kubernetes 上部署 Java* 中，我们将使用 `Amazon Web Services` (`AWS`) 和 Google 容器引擎托管的 Kubernetes。

为了跟随学习，我们需要准备好以下工具：

- `Docker`：用于构建我们想要部署的 Docker 镜像
- `minikube`：一个本地 Kubernetes 环境
- `kubectl`：Kubernetes 命令行界面

本章将涵盖以下主题：

- 在 macOS、Windows 和 Linux 上安装 Minikube
- 使用 Minikube 启动本地集群
- 在本地集群上部署 Java 应用程序
- 与容器交互：缩放、自动伸缩和查看集群事件
- 使用 Kubernetes dashboard

我们在第 7 章 *Kubernetes 简介* 中提到过 `minikube`；现在我们将深入了解一些细节，从安装开始。

### 安装 Minikube

Minikube 工具的源码可以在 GitHub 的 [`github.com/kubernetes/minikube`](https://github.com/kubernetes/minikube) 找到。

#### 在 macOS 安装

以下命令序列将下载 `minikube` 二进制文件，设置执行权限并将其移动到 `/usr/local/bin` 文件夹，使其在 macOS 中可用：

```bash
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.12.2/minikube-darwin-amd64
$ chmod +x minikube
$ sudo mv minikube /usr/local/bin/
```

或者，如果你使用 Homebrew 包管理器（免费访问 [`brew.sh`](https://brew.sh)，非常方便且推荐），你可以通过输入安装 minikube：

```bash
$ brew install minikube
```

#### 在 Windows 安装

Windows 版 Minikube 同样是一个可执行文件。你可以在 Minikube 站点 [`github.com/kubernetes/minikube`](https://github.com/kubernetes/minikube) 找到最新版本。你只需要下载最新的可执行文件，将其重命名为 `minikube.exe`，并将其放置在系统路径中以便从命令行调用。

#### 在 Linux 安装

Linux 的安装过程与 macOS 相同。区别在于可执行文件的名称。以下命令将下载最新的 Minikube 发布版本，设置执行位并移动到 `/usr/local/bin` 目录：

```bash
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

我们正在使用由 `minikube` 提供的本地 Kubernetes 集群。运行命令启动集群：

```bash
$ minikube start
```

Minikube 运行在自己的虚拟机上。根据你的宿主机操作系统，你可以选择几种虚拟化驱动。目前支持的是 `virtualbox`、`vmwarefusion`、`xhyve`、`hyperv` 和 `kvm`（基于内核的虚拟机）。默认的 VM 驱动是 virtual box。你可以覆盖此选项。以下是使用 `xhyve` 的 macOS 启动命令示例：

```bash
$ minikube start --vm-driver=xhyve
```

第一次启动 Minikube 时，你会看到它正在下载 Minikube ISO，因此过程会稍微长一点。不过，这是一次性的操作。Minikube 配置将保存在你 `home` 目录下的 `.minikube` 文件夹中，例如 Linux 或 macOS 上的 `~/.minikube`。在首次运行时，Minikube 还会配置 `kubectl` 命令行工具（我们稍后会回到这里）以使用本地的 `minikube` 集群。此设置被称为 `kubectl` 上下文（context）。它决定了 `kubectl` 与哪个集群交互。所有可用的上下文都存在 `~/.kube/config` 文件中。

由于集群现在正在运行，并且我们默认启用了 `dashboard` 插件，你可以通过以下命令查看（仍然为空的）Kubernetes 面板：

```bash
$ minikube dashboard
```

它将会在默认浏览器中打开集群面板的 URL：

![](img/Image00084.jpg)

如你所见，面板现在是空的。如果你浏览到 Namespaces 菜单，你会发现 Minikube 创建了一些命名空间，其中供我们使用的命名空间简单命名为 default。Minikube 安装的部分（例如 DNS 或 Dashboard）也运行在集群本身上，具有独立的命名空间，如 `kube-public` 和 `kube-system`。

请随意浏览菜单和部分；到目前为止，没有任何危险，因为它只是一个没有运行任何内容的本地开发集群。我们将在本章的最后一部分回到面板，看看如何使用漂亮的 UI 来部署我们的服务（如果你愿意这样做），而不是使用命令行 shell。

当然，让集群空运行是毫无意义的，因此我们需要一个工具来管理它。虽然我们可以通过面板完成几乎所有工作，但拥有一个命令行工具会方便得多。`kubectl` 控制 Kubernetes 集群。我们将大量使用 `kubectl` 命令行工具来部署、调度和扩展我们的应用程序及微服务。该工具作为适用于 Mac、Linux 和 Windows 的独立二进制文件提供。在下一节中，你将找到不同平台的安装说明。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源

### 安装 kubectl

`kubectl` 适用于主流平台。让我们从这里开始：

#### 在 macOS 安装

以下序列将下载 `kubectl`，设置可执行标记并将其复制到 `/usr/local/bin`：

```bash
$ minikube start --vm-driver=xhyve
```

Homebrew 提供了最方便的安装方法。要进行安装，请使用：

```bash
$ brew install kubectl
```

要更新，请使用：

```bash
$ brew upgrade kubectl
```

#### 在 Windows 安装

`kubectl` 适用于 Windows。与 macOS 类似，我们需要处理 `.exe` 文件。要进行安装，请使用：

```bash
$ brew install kubectl
```

#### 在 Linux 安装

`kubectl` 适用于 Linux。以下命令将下载 `kubectl`，设置可执行标记，然后移动到 `/local/bin`：

```bash
$ chmod +x kubectl
sudo cp kubectl
```

要验证集群是否启动，执行：

```bash
$ kubectl cluster-info
```

要列出我们拥有的节点，执行：

```bash
$ kubectl get nodes
```

### 在集群上部署

我们通过定义服务开始在集群上部署软件的过程。正如你从第 7 章 *Kubernetes 简介* 中记忆的那样，服务将一组 Pod 抽象为单一 IP。

### 创建服务

默认情况下，每个 Pod 只能在 Kubernetes 网络内通过其 IP 地址访问。为了能够从外部访问容器，我们需要将 Pod 暴露为服务（Service）。要创建一个服务，我们将使用简单的 `.yaml` 文件。YAML 是一种人类可读的序列化语言，通常用于配置文件。我们 `rest-example` 的示例服务清单如下：



```yaml
apiVersion: v1
kind: Service
metadata:
  name: rest-example
  labels:
    app: rest-example
    tier: backend
spec:
  type: NodePort
  ports:
  - port: 8080
  selector:
    app: rest-example
    tier: backend
```

注意，服务的清单并不引用 Docker 镜像。这是因为正如你从第 7 章《Kubernetes 简介》中记忆的那样，Kubernetes 中的服务只是一个抽象，为一个或多个 Pod 提供网络连接。每个服务都将获得自己独立的 IP 地址和端口，该地址在服务的生命周期内保持不变。每个 Pod 都需要特定的标签才能被服务发现；服务使用标签选择器（selectors）通过标签来查找分组 Pod。在我们之前的示例中，`selector` 将选取所有具有 `app` 标签值为 `rest-example` 且具有 `tier` 标签值为 `backend` 的 Pod：

```yaml
selector:
  app: rest-example
  tier: backend
```

- `Proxy-mode: userspace`：在用户空间模式下，`iptables` 规则将数据包转发到本地端口，`kube-proxy` 在该端口监听连接。运行在用户空间的 `kube-proxy` 会终止连接，为服务建立后端建立新连接，然后将请求转发到后端并将响应传回给本地进程。用户空间模式的优势是，由于连接是从应用程序创建的，如果连接被拒绝，应用程序可以重试到不同的后端。
- `Proxy-mode: iptables`：在此模式下，安装 `iptables` 规则直接将目标为服务的数据包转发到该服务的后端。这比将数据包从内核移动到 `kube-proxy` 再传回内核更高效，因此会产生更高的吞吐量和更好的尾延迟。然而，与用户空间模式不同，使用 `iptables` 模式使得在初始选择的 Pod 无响应时无法自动重试到另一个 Pod，因此它依赖于工作正常的就绪探针（readiness probes）。

如你所见，在两种情况下，节点上都会运行一个 `kube-proxy` 二进制文件。在用户空间模式下，它将自己插入作为代理；在 `iptables` 模式下，它将配置 `iptables` 而不是亲自代理连接。

服务类型可以取以下值：

- `NodePort`：通过指定服务类型为 `NodePort`，我们声明在集群外部暴露服务。Kubernetes 主节点将从标记配置的范围（默认：`30000-32767`）中分配一个端口，集群的每个节点都将该端口（每个节点上的端口号相同）代理到您的服务。
- `Load balancer`：这将在支持外部负载均衡器的云提供商上创建一个负载均衡器（例如，在 Amazon AWS 云上）。使用 Minikube 时无法使用此功能。
- `Cluster IP`：这将仅在集群内部暴露服务。如果你不提供其他类型，将使用此默认值。

准备好`service.yml`文件后，我们可以通过执行以下`kubectl`命令来创建第一个 Kubernetes 服务：

```bash
$ kubectl create -f service.yml
```

要查看我们的服务是否创建正确，可以执行`kubectl get services`命令：

![](img/Image00087.jpg)

我们还可以通过添加`--all-namespaces`来列出其他服务（包括`minikube`集群本身提供的服务，如果你感兴趣的话）：

```bash
$ kubectl get services --all-namespaces
```

要查看特定服务的详情，我们使用`describe`命令。执行以下命令查看我们的`rest-example` Java 详情：

```bash
$ kubectl describe service rest-example
```

在输出中，我们看到了最有用的服务属性，特别是端点（endpoints，我们的内部容器 IP 和端口，在本例中只有一个，因为我们在服务中运行了一个 Pod）、服务内部端口以及代理的 NodePort：

![](img/Image00088.jpg)

在`.yaml`文件中拥有所有设置非常方便。但是，有时需要以更具动态的方式创建服务；例如在某些自动化流程中。在这种情况下，我们不是先创建一个`.yaml`文件，而是通过向`kubectl`命令本身提供所有参数和选项来手动创建服务。但在此之前，你将先创建部署（deployment），因为手动创建服务只是使用`kubectl`命令暴露部署。毕竟，服务是一个暴露的部署，实际上，它只是一组`Podss`。这种由于服务创建而产生的暴露示例看起来如下：

```bash
$ kubectl expose deployment rest-example --type="NodePort"
```

## 创建部署

在创建部署之前，我们需要准备好 Docker 镜像并将其发布到存储库中，例如 Docker Hub。当然，它也可以托管在您组织中的私有仓库。正如你从第 7 章《Kubernetes 简介》中记忆的那样，Pod 中的每个 Docker 容器都有它自己的镜像。默认情况下，Pod 中的`kubectl`进程将尝试从指定的存储库拉取每个镜像。你可以通过指定部署描述符中`imagePullPolicy`属性的值来更改此行为。它可以具有以下值：

- `IfNotPresent`：使用此设置，只有当本地主机上不存在镜像时，才会从存储库拉取。
- `Never`：使用此设置，`kubelet`将仅使用本地镜像。

在创建部署时将`imagePullPolicy`设置为`IfNotPresent`是很有用的；否则，Minikube 将在查找本地主机上的镜像之前尝试下载镜像。

Kubernetes 使用与 Docker 本身相同的镜像语法，包括私有仓库和标签（tags）。

在镜像名称中提供标签非常重要。否则，Kubernetes 在仓库中查找你的镜像时将使用最新标签，就像 Docker 执行的那样。

当与本地 Kubernetes 集群协作时，使用本地构建的镜像有点棘手。Minikube 运行在一个独立的虚拟机中，因此它看不到你在本地机器上使用 Docker 本地构建的镜像。这有一个解决方法。你可以执行以下命令：

```bash
$ eval $(minikube docker-env)
```

之前的命令实际上将利用运行在`minikube`上的 Docker 守护进程并在 Minikube 的 Docker 上构建你的镜像。这样，本地构建的镜像就可以被 Minikube 使用，而无需从外部存储库拉取。为了这一点，我们需要将镜像推送到远程仓库。

1. 首先，我们需要登录：

   ```bash
   $ docker login
   ```

2. 然后，我们将使用`docker tag`命令为我们的镜像标记（注意你需要提供 DockerHub 用户名）：

   ```bash
   $ docker tag 5452c0ed7 $DOCKER_HUB_USER/rest-example
   ```

3. 最后一步是使用`docker push`命令将镜像推送到 Docker Hub：

   ```bash
   $ docker push $DOCKER_HUB_USER/rest-example
   ```

4. 现在既然存储库中有了镜像，我们需要一个部署清单。再次是一个`.yaml`文件，如下所示：

   ```yaml
   apiVersion: extensions/beta1
   kind: Deployment
   metadata:
     name: rest-example
   spec:
     replicas: 1
     template:
       metadata:
         labels:
           app: rest-example
           tier: backend
       spec:
         containers:
         - name: rest-example
           image:却是 rest-example
           imagePullPolicy: IfNotPresent
           resources:
             requests:
               cpu: 100m
               memory: 100Mi
           env:
           - name: GET_HOSTS_FROM
             value: dns
           ports:
           - containerPort: 8080
   ```

使用`kubectl`在集群上创建此部署，你需要执行以下命令，这与创建服务完全相同，区别在于文件名：

```bash
$ kubectl create -f deployment.yml
```

![](img/Image00089.jpg)

你可以通过以下命令查看部署属性：

```bash
$ kubectl describe deployment rest-service
```

![](img/Image00090.jpg)

如你所见，除了 ReplicaSet 和默认滚动更新策略外，还创建了一个 Pod。你还可以通过以下命令查看 Pods：

```bash
$ kubectl get pods
```

`get pods`命令的输出将给你部署中运行的 Pod 的名称。这在以后很重要，因为如果你想与特定的 Pod 交互，你需要知道它的名称：

![](img/Image00091.jpg)

```bash
$ kubectl run rest-example --image=jotka/rest-example --replicas=1 --port=8080 --labels="app:rest-example;tier:backend" --expose
```

让我们通过表格总结与创建资源及获取其信息相关的`kubectl`命令，并提供一些示例：

| 示例命令 | 含义 |
| :--- | :--- |
| `kubectl create -f ./service.yaml` | 创建资源 |
| `kubectl create -f ./service.yaml -f ./deployment.yaml` | 从多个文件创建资源 |
| `kubectl create -f ./dir` | 在指定目录的所有清单文件中创建资源 |
| `kubectl create -f https://sampleUrl` | 从 URL 创建资源 |
| `kubectl run nginx --image=nginx` | 启动一个 nginx 实例实例 |
| `kubectl get pods` | 获取`pod`的文档 |
| `kubectl get pods --selector=app=rest-example` | 列出所有匹配指定标签`selector`的 Pod |
| `kubectl explain pods` | 显示所有 Pod 的详情 |
| `kubectl get services` | 列出所有创建的服务 |
| `kubectl explain service` | 显示特定服务的详情 |
| `kubectl explain services` | 显示所有创建服务的详情 |
| `kubectl get deployments` | 列出所有创建的部署 |
| `kubectl get deployment` | 显示特定部署详情 |
| `kubectl explain deployment` | 显示特定部署的详情 |
| `kubectl explain deployments` | 显示所有创建部署的详情 |
| `kubectl get nodes` | 列出所有集群节点 |
| `kubectl explain node` | 显示特定节点的详情 |

### 调用服务

正如我们在`kubectl describe service rest-example`命令输出所示，我们的`rest-example service`可以通过端口`8080`和域名`rest-example`在集群内部访问。在我们的情况下，端点的完整 URL 将是`http://rest-example:8080`。然而，为了能够从外部执行该服务，我们使用了`NodePort`映射，并且知道它被分配了端口`31141`。我们只需要调用集群的 IP。可以使用以下命令获取它：

```bash
$ minikube ip
```

获取外部可访问的服务 URL 和端口号有一个快捷方法。我们可以使用`minikube service`命令来告知准确的服务地址：

```bash
$ minikube service rest-example --url
```

上一个命令的输出将是带有映射端口号的服务 URL。如果你跳过`--url`选项，`minikube`将使用你的默认网络浏览器打开服务的 URL。这有时非常方便。

有了端点的完整 URL，我们可以使用任何`HTTP`客户端（例如`curl`）来访问服务：

![](img/Image00092.jpg)

当服务运行时，应用程序日志通常可以帮助你理解集群内部正在发生什么。日志对于调试问题和监控集群活动特别有用。让我们看看如何访问容器日志。

## 与容器交互并查看日志

大多数现代应用程序都有某种日志记录机制。例如，我们的 Java REST 服务使用`slf4j`从 REST 控制器输出日志。对于容器化应用程序来说，最简单直接的日志记录方法就是直接写入标准输出和标准错误流。Kubernetes 原生支持这种功能。

假设我们已经使用浏览器或`curl`向新的 Web 服务发送了请求，现在我们应该能够看到一些日志。在此之前，我们需要一个 Pod 的名称，它是在部署过程中自动创建的。要获取 Pod 名称，请使用`kubectl get pods`命令。之后，你可以显示指定 Pod 的日志：

```bash
$ kubectl logs rest-example-3660361385-gkzb8
```

如接下来的截图所示，我们将获得来自运行在 Pod 中的服务的知名 Spring Boot 横幅：

![](img/Image00093.jpg)

查看日志并不是我们对特定 Pod 可以做的唯一事情。与 Docker 类似（实际上 Pod 正在运行 Docker），我们可以使用`kubectl exec`命令与容器进行交互。例如，为运行中的容器获取一个 shell：

```bash
$ kubectl exec -it rest-example-3660361385-gkzb8 -- /bin/bash
```

上一个命令会将你的 shell 控制台挂载到运行中容器的 shell 中，你可以在其中对其进行交互，例如列出进程，如下幅截图所示：

![](img/Image00094.jpg)

`kubectl exec`命令的语法与 Docker 中的`exec`命令非常相似，只有一个微小的区别，正如你在第 7 章《Kubernetes 简介》中记忆的那样，一个 Pod 可以运行多个容器。在这种情况下，我们可以使用`--container`或`-c`参数开关在`kubectl exec`命令中指定一个容器。例如，假设我们有一个名为`rest-example-3660361385-gkzb8`的 Pod。该 Pod 有两个名为`service`和`database`的容器。接下来的命令将为 service 容器打开一个 shell：

```bash
$ kubectl exec -it rest-example-3660361385-gkzb8 --container service -- /bin/bash
```

当然，我们的 Java`rest-example`服务将数据保存在内存中，因此它不是无状态的，这可能不是扩缩的最佳示例；如果启动另一个实例，它将拥有自己的数据。然而，它是一个 Kubernetes 服务，所以我们仍然可以使用它来演示扩缩。要将我们的`rest-example`部署从一个 Pod 扩展到三个，请执行以下`kubectl scale`命令：

```bash
$ kubectl scale deployment rest-example --replicas=3
```

过了一会儿，为了检查结果，请执行以下命令，你会发现现在部署中运行了三个 Pod：

```bash
$ kubectl get deployments
$ kubectl get pods
```

在下表中，你可以看到更多一些与手动扩缩相关的`kubectl`命令的示例：

| 示例命令 | 含义 |
| :--- | :--- |
| `kubectl scale deployment rest-example --replicas=3` | 将名为`rest-example`的部署扩展到`3`个 Pod |
| `kubectl scale --replicas=3 -f deployment.yaml` | 将`deployment.yaml`文件中指定的资源扩展到`3` |
| `kubectl scale deployment rest-example --current-replicas=2 --replicas=3` | 如果名为`rest-example`的部署当前大小为`2`，则将其扩展到`3`个 Pod |
| `kubectl scale --replicas=5 deployment/foo deployment/bar` | 同时扩展多个部署 |

扩缩可以由 Kubernetes 自动完成，例如当服务负载增加时。

## 自动扩缩



通过水平 Pod 自动扩缩（horizontal Pod auto scaling），`Kubernetes` 会根据观察到的 CPU 利用率自动调整部署或 `ReplicaSet` 中 Pod 的数量。`Kubernetes` 控制器定期调整部署中 `replicas` 的数量，以使观察到的平均 CPU 利用率匹配你指定的节点。

水平自动扩缩器（Horizontal Auto Scaler）只是 `Kubernetes` 中的另一种资源，因此我们可以像创建其他资源一样，使用 `kubectl` 命令创建它：

- `kubectl get hpa`：列出自动扩缩器
- `kubectl describe hpa`：获取详细描述
- `kubectl delete hpa`：删除自动扩缩器

此外，还有一个特殊的 `kubectl autoscale` 命令可以方便地创建水平 Pod 自动扩缩器。例如：

```bash
$ kubectl autoscale deployment rest-example --cpu-percent=50 --min=1 --max=10 
```

上一个命令将为我们的 `rest-example` 部署创建一个自动扩缩器，目标 CPU 利用率设置为 `50`%，`replicas` 数量在 `1` 到 `10` 之间。

所有的集群事件都会被注册，包括由于手动或自动扩缩产生的事件。在监控集群上具体执行了什么操作时，查看集群事件很有帮助。

### 查看集群事件

要查看集群事件，输入以下命令：

```bash
$ kubectl get events 
```

它将呈现一个巨大的表格，列出集群上注册的所有事件：

![](img/Image00095.jpg)

表格将包括节点状态的变化、拉取 Docker 镜像、容器启动和停止事件等。查看整个集群的状况会非常有用。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

### 使用 Kubernetes dashboard

`Kubernetes dashboard` 是一个通用的、基于 Web 的 `Kubernetes` 集群 UI。它允许用户管理在集群中的应用程序并进行故障排除，还可以管理集群本身。我们还可以编辑部署、服务或 Pod 的清单文件（manifest）。更改将由 `Kubernetes` 立即获取，因此它赋予了我们扩展或缩小部署的能力，例如。

如果你使用 `minikube dashboard` 命令打开 dashboard，它将在你的默认浏览器中打开 dashboard URL。从这里，你可以列出集群上的所有资源，如部署、服务、Pod 等。我们的 dashboard 不再是空的，如接下来的截图所示；我们有一个名为 `rest-example` 的部署：

![](img/Image00096.jpg)

如果你点击它的名称，你将进入部署详情页，该页面将显示通过 `kubectl describe deployment` 命令获得的相同信息，但具有美观的 UI：

![](img/Image00097.jpg)

dashboard 不仅仅是只读工具。每个资源都有一个方便的菜单，你可以用它删除资源或编辑其清单：

![](img/Image00098.jpg)

如果你选择 view/edit YAML 菜单选项，你将能够使用方便的编辑器编辑清单：

![](img/Image00099.jpg)

注意，如果你更改了一个值（例如 `replicas` 的数量）并点击 `Update`，更改将发送到 `Kubernetes` 并执行。通过这种方式你也可以扩展你的部署。

由于部署自动创建了 `ReplicaSet`，`ReplicaSet` 也会在 dashboard 中可见：

![](img/Image00100.jpg)

服务也是如此。如果你浏览到 Services 菜单，它将列出集群上创建的所有服务列表：

![](img/Image00101.jpg)

点击服务的名称将带你进入详情页：

![](img/Image00102.jpg)

所有的集群事件都会被注册，包括由于手动或自动扩缩产生的事件。在监控集群上具体执行了什么操作时，查看集群事件很有帮助。

### Minikube addons

`Minikube` 带有了一些插件（addons），例如 `Kubernetes dashboard`、`Kubernetes DNS` 等。我们可以执行以下命令列出可用插件：

```bash
$ minikube addons list
```

上一个命令的输出将列出可用插件及其当前状态，例如：

![](img/Image00105.jpg)

要启用或禁用插件，我们分别使用 `minikube addons disable` 或 `minikube addons enable`，例如：

```bash
$ minikube addons disable dashboard

$ minikube addons enable heapster
```

如果插件已启用，我们可以通过 `addon open` 命令打开相应的 Web，例如：

```bash
$ minikube addons open heapster
```

### 清理

如果你完成了对部署和服务的操作或想重新开始，可以通过删除部署或服务来进行集群清理：

```bash
$ kubectl delete deployment rest-example

$ kubectl delete service rest-example 
```

这些代码也可以合并成一条命令，例如：

```bash
$ kubectl delete service,deployment rest-example
```

要停止 `minikube` 集群，只需执行：

```bash
$ minikube stop
```

如果你想删除当前的 `minikube` 集群，可以执行以下命令来删除：

```bash
$ minikube delete 
```

### 总结

如你所见，`Minikube` 是尝试 `Kubernetes` 并将其用于本地开发的简单方法。运行本地集群并没有像最初看起来那样可怕。最棒的是，本地 `minikube` 集群是一个有效的 `Kubernetes` 集群。如果你能通过在本地玩玩来熟悉 `Kubernetes`，那么你就能毫无问题地在真实的云环境中部署你的应用程序。让我们总结一下让 Java 应用程序在 `Kubernetes` 集群上运行需要执行的步骤。

首先，我们需要为微服务编写一些代码。这可以基于你的任何意愿，可以是运行在 Tomcat、JBoss 或 Spring Bootstrap 上的微服务。这没关系，你只需要选择你希望软件运行的技术：

- 接下来，将代码放入 Docker 镜像中。你可以通过创建 `Dockerfile` 手动完成，也可以使用 Docker Maven 插件来自动化此过程
- 创建 `Kubernetes` 元数据，例如部署清单（deployment manifest）和服务部署清单（service manifest）
- 通过滚动部署和创建服务来应用元数据
- 根据你的需求伸缩你的应用程序
- 从命令行或仪表板管理你的集群

在第 9 章 `使用 Kubernetes API` 中，我们将查看 `Kubernetes API`。这是与 `Kubernetes` 集群交互的一种极佳方式。由于 API 的存在，可能性几乎是无限的，你可以创建自己的开发工作流，例如使用 Jenkins 进行持续交付。有了 API，你不再局限于使用现有工具将软件部署到 `Kubernetes`。事情会变得更有趣。

## 使用 Kubernetes API

在第 7 章 `Kubernetes 简介` 和第 8 章 `在 Java 中使用 Kubernetes` 中，我们学习了 `Kubernetes` 概念，并通过通过 `minikube` 安装本地 `Kubernetes` 集群在实践中使用了它们。我们了解 `Kubernetes` 架构的所有部分，例如 pods、nodes、deployment 和 services。我们还提到了位于 Master 节点上的主要组件之一，即 API server。正如你从第 7 章 `Kubernetes 简介` 中回记得的那样，API server 在技术上是一个名为 `kube-apiserver` 的进程，它使用 JSON 接收并响应 `HTTP REST` 请求。API server 的主要目的是验证和处理集群资源（如 Pods、services 或 deployments）的数据。API Server 是中心管理实体。它也是直接连接到 `etcd` 的 `Kubernetes` 组件，`etcd` 是 `Kubernetes` 存储所有集群状态的分布式键值数据存储。

在之前的章节中，我们一直使用 `kubectl` 命令行工具来管理集群。`kubectl` 是一个实用的工具，每我们需要对集群执行命令时（无论是创建、编辑还是删除资源）。事实上，`kubectl` 也与 API server 通信；你可能已经注意到 `Kubernetes` 中几乎每个更改内容的操作基本上都是编辑资源。如果你想扩展或缩小你的应用程序，将通过修改 deployment 资源来实现。`Kubernetes` 会实时捕获变化并将其应用到资源上。此外，只读操作（如列出 Pod 或 deployments）将执行相应的 `GET` 请求。

事实上，如果你以更高的详细级别运行 `kubectl` 命令（使用 `--v=6` 或 `--v=9` 选项），就可以看到 `kubectl` 命令执行了哪些 `REST` 调用，我们将在本章稍后回到这个问题。我们可以通过 `kubectl`、`client` 库或通过发送 `REST` 请求来访问 API。`REST` API 什么时候有用呢？嗯，你可以在每种编程或脚本语言中创建 `REST` 调用。这创建了一个全新的灵活性层面，你可以从你自己的 Java 应用程序、从 Jenkins 中的持续交付流中，或从你正在使用的构建工具（例如 Maven）中管理 `Kubernetes`。可能性几乎是无限的。在本章中，我们将了解 API 概述、其结构和示例请求。我们将使用命令行工具 `curl` 通过 `REST` 调用来完成这些。本章将涵盖以下主题：

- 关于 API 版本的说明
- 身份验证（确定身份是谁）
- 授权（确定谁可以做什么）
- 通过一些示例调用使用 API
- OpenAPI Swagger 文档

让我们从 API 概述开始。

### API 版本控制

`Kubernetes` 在不断增长。它的功能在变化，这导致 API 也随之变化。为了处理这些变化并在长时间内保持与现有客户端的兼容性，`Kubernetes` 支持多个 API 版本，每个版本都有不同的 API 路径，例如 `/api/v1` 或 `/apis/extensions/v1beta1`。`Kubernetes API` 规范中有三个 API 级别：alpha、beta 和 stable。让我们了解它们的区别。

### Alpha

alpha 版本级别默认禁用，与其他软件一样，alpha 版本应该被认为是有缺陷的且未准备好绪。此外，你应该注意，alpha 版本中引入的任何功能在稍后的稳定版本中并不总是可用的。此外，API 中的更改在下一个版本中可能是不兼容的。你不应该使用 `alpha` 版本，除非你非常渴望测试新功能或进行一些实验。

### Beta

beta 级与 API 的 `alpha` 级完全不同，代码经过测试（仍然可能有一些错误，因为尚未发布）。此外，与 `alpha` 级相比，`beta` 中的功能未来不会删除。如果 API 发生破坏性的、不兼容的更改，`Kubernetes` 团队将提供迁移指南。在生产环境中使用 `beta` 不是好主意，但你可以在非业务关键集群上安全地使用 `beta`。我们也鼓励在使用 `beta` 时提供反馈，这将使 `Kubernetes` 对我们所有人都变得更好。`beta` 级别的版本名称将包含 `beta` 词，例如 `v1beta1`。

### Stable

API 的稳定级别是经过测试的生产就绪的软件。稳定 API 中的版本名称将是 `vX`，其中 `X` 是一个整数，例如 `v1`。

`Kubernetes API` 利用了 API 组的概念。引入 API 组是为了将来更容易地扩展 `Kubernetes API`。API 组在 `REST` 路径以及调用的 JSON 载负载的 `apiVersion` 字段中指定。目前有几个正在使用的 API 组：core、batch 和 extensions。组名是 API 调用 `REST` 路径的一部分：`/apis/$GROUP_NAME/$VERSION`。core 组是一个异常，它不会出现在 `REST` 路径中，例如：`/api/v1`。你可以在 `Kubernetes API` 参考中找到支持的 API 组的完整列表。

### 身份验证

默认情况下，`Kubernetes API` 服务器在两个端口上提供 `HTTP` 请求：

- **Localhost，不安全端口**：默认情况下，IP 地址为 `localhost`，端口号为 `8080`。此处没有 TLS 通信，该端口上的所有请求都将跳过身份验证和授权插件。这用于测试和引导，以及主节点的其他组件。它也用于其他 `Kubernetes` 组件（如 `scheduler` 或 `controller-manager`）执行 API 调用。你可以通过 `--insecure-port` 切换更改端口号，并使用 `--insecure-bind-address` 命令行切换更改默认 IP。
- **安全端口**：默认端口号为 `6443`（可以通过 `--secure-port` 切换更改），在云服务提供商上通常为 `443`。它使用 TLS 通信。可以通过 `--tls-cert-file` 切换设置证书。可以通过 `--tls-private-key-file` 切换提供私有 SSL 密钥。通过此端口的所有请求都将由身份验证、授权模块和准控制模块处理。你应该尽可能使用安全端口。通过让你的 API 客户端验证 `api-server` 提供的 TLS 证书，它们可以验证连接是加密的，且不受中间人攻击的影响。你还应该运行 `api-server`，使得不安全端口仅对 localhost 可，这样跨网络的连接将使用 `HTTPS`。
- 使用 `minikube`，要直接访问 API 服务器，你需要使用 `minikube` 生成的自定义 SSL 证书。客户端证书和密钥通常存储在 `~/.minikube/apiserver.crt` 和 `~/.minikube/apiserver.key` 中。在进行 `HTTP` 请求时，你需要将它们加载到你的 `HTTPS` 客户端。如果你使用 `curl`，使用 `--cert` 和 `--key` 选项来使用 `cert` 和 `key` 文件。

可以通过代理简化访问 API 服务器，我们将在本章后面介绍。

如果你想从不同的域名向 `Kubernetes API` 发送请求，需要在 `api-server` 上启用 `cors`。通过向 `kube-apiserver` 配置中添加 `--cors-allowed-origins=["http://*"]` 参数来实现，通常在 `/etc/default/kube-apiserver` 文件中，并重启 `kube-apiserver`。

注意，`Kubernetes` 集群本身并不管理用户。相反，假设用户是由外部独立服务管理的。`Kubernetes` 集群中没有资源代表普通用户账户。这就是为什么无法通过 API 调用将用户添加到集群中。

`Kubernetes` 本身并不管理用户账户。

`Kubernetes API` 支持多种形式的身份验证：`HTTP` 基础认证、令牌（bearer token）和客户端证书。它们被称为身份验证策略。启动 `api-server` 时，你可以通过命令行标志启用或禁用这些身份验证策略。让我们看看哪些可能性，从最简单的基础认证策略开始。

### HTTP 基础认证

要使用此身份验证策略，你需要使用 `--basic-auth-file=<path_to_auth_file>` 切换启动 `api-server`。它应该是一个 `csv` 文件，其中每个用户都有如下条目：

```
password, user name, userid 
```

你还可以指定一个可选的第四列，包含组名并用逗号分隔。如果一个用户有多个组，则整个列的内容必须用双引号括起来，例如：

```
password, user, userid,"group1,group2,group3" 
```

如果 `api-server` 利用基础认证策略，它将期望所有的 `REST` 调用都带有包含用 `BASE64` 编码的用户名和密码的 `Authorization` 头（类似于普通的基础认证保护的 Web 调用），例如：

```
BASE64ENCODED(USER:PASSWORD) 
```

要生成授权头的值，你可以在 shell 中使用以下命令，它将为密码为 secret 的用户生成值：

```bash
echo -n "user:secret" | base64
```

注意，对基础 `auth` 文件的任何更改都需要重启 `api-server` 才能生效。

`HTTP` 基础认证通常在云端运行 `Kubernetes` 时作为默认选项。例如，一旦你在 Google Container Engine 上启动了容器集群，你将有一个运行在 GCP 项目虚拟机上的运行 `api-server` 的主节点。如果你运行 `gcloud preview container clusters list`，你将看到 `api-server` 监听请求的端点以及访问它所需的凭据。关于在云端运行 `Kubernetes` 的更多信息，请参考第 10 章，*在云端 Kubernetes 上部署 Java*。

### 读累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载



- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享

### 静态令牌文件

要让`api-server`使用此方案，需要使用`--token-auth-file=<PATH_TO_TOKEN_FILE>`切换启动。与`HTTP`基础认证策略类似，提供的文件是一个`csv`文件，每个用户有一条记录。记录需要符合以下格式：

```
token, user, group 
```

再次，组名是可选的，如果一个用户有多个组，你需要用逗号分隔它们并用双引号括。令牌只是一个`base64`编码字符串。在 Linux 上生成令牌的示例命令如下：

```bash
echo `dd if=/dev/urandom bs=128 count=1 2>/dev/null | base64 | tr -d "+/" | dd bs=32 count=1 2>/dev/null`
```

输出将是一个令牌，然后将其输入`token`文件，例如：

```
3XQ8W6IAourkOLH2py,default,default
```

使用此策略时，`api-server`将预期值为`Bearer <TOKEN>`的`Authorization`头。在我们的示例中，它看起来像：

```
Authorization: Bearer 3XQ8W6IAourkOLH2py... 
```

令牌永久有效，不重启 API 服务器无法更改令牌列表。

### 客户端证书

为了使用此方案，启动`api-server`时需要以下切换：

```bash
--client-ca-file=<PATH_TO_CA_CERTIFICATE_FILE>
```

`CA_CERTIFICATE_FILE`必须包含一个或多个用于验证提交给`api-server`的客户端证书的证书颁发机构。客户端证书的`/CN`（通用名称）被用户名。客户端证书还可以指示用户的组关系。要为一个用户包含多个组关系，你需要在证书中包含多个组织字段。例如，使用`openssl`命令行工具生成签名请求：

```bash
openssl req -new -key user.pem -out user-csr.pem -subj "/CN=user/O=group1/O=group2"
```

这将为名为`user`属于两个组`group1`和`group2`的用户创建一个签名请求。

### OpenID

OpenID connect 1.0 是 OAuth 2.0 协议之上的简单身份层。你可以在互联网上的`https://openid.net/connect`更多关于 OpenID connect 的信息。它允许客户端根据授权服务器执行的验证验证终端用户的身份，并以一种互操作且类`REST`的方式获取终端用户的概要信息。所有云提供商（包括 Azure、Amazon 和 Google）都支持 OpenID。它与`OAuth2`的主要区别在于访问令牌中返回了一个名为`id_token`的额外字段。该令牌是一个`JSON Web Token`（`JWT`），具有许多已知字段（例如用户的电子邮件），并由服务器签名。为了识别用户，身份验证器使用`OAuth2token`响应中的`id_token`作为者令牌（bearer token）。要使用 OpenID 身份验证，你需要登录你的身份提供者，它将为你提供一个`id_token`（以及标准的 OAuth 2.0 `access_token`和`refresh_token`）。

由于执行身份验证所需数据都包含在`id_token`中，因此 Kubernetes 不需要身份提供者进行额外的调用。这对于扩展性来说非常重要，因为每个请求都是无状态的。

要向`kubectl`命令提供令牌值，你需要使用`--token`标记。或者，你也可以将其直接添加到`kubeconfig`文件中。

当你是对你的`api-server`执行`HTTP`调用时将发生的简化流程：

- `kubectl`将将你的`id_token`通过`authorization`头部发送到 API 服务器
- API 服务器将通过检查配置中指定的证书来验证 JWT 签名
- API 服务器将检查`id_token`是否过期
- API 服务器将确保用户已获得授权，如果是，则向`kubectl`返回响应

默认情况下，任何拥有`api-server`访问凭据的人都对集群具有完全访问。你还可以配置更细粒度的授权策略，让我们现在来看授权。

### 授权

成功身份验证后的下一步是检查允许已验证用户执行哪些操作。截至目前，Kubernetes 支持四种授权策略方案。要利用特定的授权方案，在启动`api-server`时使用`--authorization-mode`开关。语法如下：

```
$ kube-apiserver --authorization-mode <mode> 
```

`<mode>`参数包含一个有序的授权插件列表，Kubernetes 用这些插件验证用户。当启用多个身份验证插件时，第一个成功验证请求的插件将让 Kubernetes 跳过执行剩余的所有插件。

默认授权模式为`AlwaysAllow`，允许所有请求。

支持以下授权方案：

- 基于属性的控制
- 基于角色的控制
- Webhook
- `AlwaysDeny`
- `AlwaysAllow`

让我们逐一简要描述它们。

### 基于属性的访问控制

如果你使用`--authorization-mode=ABAC`启动`api-server`，将使用基于属性的访问控制（`ABAC`）策略。该策略使用本地文件，你可以在文件中灵活地定义每个用户应该拥有的权限。有一个额外的选项提供策略文件：`--authorization-policy-file`，因此使用此策略的完整语法为：

```
$ kube-apiserver --authorization-mode=ABAC \
--authorization-policy-file=<PATH_TO_POLICY_FILE> 
```

注意，对策略文件的任何更改都需要重启`api-server`。

正如你从第 7 章 *Kubernetes 简介* 中记得的，Kubernetes 集群使用命名空间（namespaces）的概念对分组分组，例如 Pod、部署或服务。`api-server`中的授权方案利用了这些命名空间。`ABAC`策略文件的语法非常清晰易读。每个条目都是描述授权规则的 JSON 对象。考虑策略文件中的以下条目，它赋予用户`john`对`myApp`命名空间的完全访问权限：

```json
{
   "apiVersion": "abac.authorization.kubernetes.io/v1beta1",
   "kind": "Policy",
   "spec": {
      "user":"john",
      "namespace": "myApp",
      "resource": "*",
      "apiGroup": "*",
      "nonResourcePath": "*"
   }
}
```

下一个示例将赋予用户`admin`对所有命名空间的完全访问权限：

```json
{
   "apiVersion": "abac.authorization.kubernetes.io/v1beta1",
   "kind": "Policy",
   "spec":{
      "user":"admin",
      "namespace": "*",
      "resource": "*",
      "apiGroup": "*",
      "nonResourcePath": "*"
   }
}
```

最后，一个赋予所有用户对整个集群只读访问权限的示例：

```json
{
   "apiVersion": "abac.authorization.kubernetes.io/v1beta1",
   "kind": "Policy",
   "spec": {
      "user":"*",
      "namespace": "*",
      "resource": "*",
      "apiGroup": "*",
      "nonResourcePath": "*",
      "readonly":true
   }
}
```

### 基于角色的访问控制 (RBAC)

基于角色的访问控制（`RBAC`）策略实现深度集成到 Kubernetes 中。事实上，Kubernetes 内部使用它为系统组件授予运行所需的权限。`RBAC`是 100% API 驱动的，角色和绑定是可以在集群上创建的资源，例如 Pod、部署或服务。启用`RBAC`模式只需向`apiserver`传递标记：

```
--authorization-mode=RBAC
```

这种模式允许你使用 Kubernetes API 创建并存储策略。在`RBAC`API 中，一组权限由角色概念表示。命名空间角色（由`Role`资源表示）与集群角色（由`ClusterRole`资源表示）之间存在区别。`ClusterRole`可以定义与`Role`相同的权限，还可以定义某些集群权限，例如跨命名空间管理资源。注意一旦启用`RBAC`，API 的每个方面都允许访问。

权限是累加的；没有拒绝规则。

这是一个赋予对所有资源的所有操作的完整权限的角色示例：

```yaml
apiVersion: rbac.authorization.k8s.io/v1beta1
metadata:
  name: cluster-writer
rules:
  - apiGroups: ["*"]
    resources: ["*"]
    verbs: ["*"]
    nonResourceURLs: ["*"]
```

正如你从第 8 章 *使用 Java 使用 Kubernetes* 中记得，`Role`是一个资源，使用文件创建资源时执行`kubectl create`命令，例如：

```
$ kubectl create -f cluster-writer.yml
```

`Role`和`ClusterRole`定义权限集，但不会直接将其分配给用户或组。Kubernetes API 中另一个资源用于此，即`RoleBinding`或`ClusterRoleBinding`。它们将`Role`或`ClusterRole`绑定到特定的主体，主体可以是用户、组或服务用户。要绑定`Role`或`ClusterRole`，你需要执行`kubectl create rolebinding`命令。查看以下示例。为`myApp`命名空间中的用户`john`授予`adminClusterRole`：

```bash
$ kubectl create rolebinding john-admin-binding \
--clusterrole=admin --user=john --namespace=myApp
```

下一个将为跨整个集群的用户`admin`授予`cluster-admin ClusterRole`：

```bash
$ kubectl create clusterrolebinding admin-cluster-admin-binding \
--clusterrole=cluster-admin --user=admin
```

用于`kubectl create -f`的等效 YAML 文件如下：

```
apiVersion: rbac.authorization.k8s.io/v1beta1
kind: ClusterRoleBinding
metadata:
  name: admin-cluster-admin-binding
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- kind: User
  name: admin 
```

### WebHook

当`api-server`使用`--authorization-mode=Webhook`选项启动时，它将调用外部`HTTP`服务器来对用户进行授权。这使你拥有了创建自定义授权服务器的能力。换句话说，WebHook 是一种`HTTP`回调模式，允许你使用一个远程`REST`器来管理授权，该服务器可以是你自己开发的，也可以是第三方授权服务器。

在进行授权检查时，`api-server`会执行一个`HTTP POST`请求，负载为 JSON 数据，其中包含一个序列化的`api.authorization.v1beta1.SubjectAccessReview`对象。该对象描述了向`api-server`发起请求的用户、该用户想要执行的操作，以及作为该操作主体资源的详细信息。一个请求负载示例如下例所示：

```
 {
  "apiVersion": "authorization.k8s.io/v1beta1",
  "kind": "SubjectAccessReview",
  "spec": {
    "resourceAttributes": {
      "namespace": "rest-example",
      "verb": "get",
      "resource": "pods"
    },
    "user": "john",
    "group": [
      "group1",
      "group2"
    ]
  }
}
```

远程授权服务器应该提供响应，说明该用户是否有权在指定的资源上执行指定的操作。响应应包含`SubjectAccessReviewStatus`字段，指定`api-server`应该允许还是拒绝访问。一个允许的 JSON 响应如下：

```
 {
  "apiVersion": "authorization.k8s.io/v1beta1",
  "kind": "SubjectAccessReview",
  "status": {
    "allowed": true
  }
}
```

拒绝的响应将如下例所示：

```
 {
  "apiVersion": "authorization.k8s.io/v1beta1",
  "kind": "SubjectAccessReview",
  "status": {
    "allowed": false,
    "reason": "user does not have read access to the namespace"
  }
}
```

将授权委托给另一个服务的可能性使得授权过程变得非常灵活。想象你自己的软件，可以根据用户在企业`LDAP`目录中的角色，授权用户在你的集群中执行某些操作。

### AlwaysDeny

此策略拒绝所有请求。如果你在启动`api-server`时使用`--authorization-mode=AlwaysDeny`参数，则将使用它。如果你正在进行某些测试或希望在不实际停止`api-server`的情况下阻止传入的请求，这非常有用。

### AlwaysAllow

如果你在启动`api-server`时使用`--authorization-mode=AlwaysAllow`，所有请求将被接受，而不使用任何授权方案。只有当你不需要对 API 请求进行授权时才使用此标志。

如你所见，Kubernetes 中的身份验证和授权功能非常灵活。在本章开始的图表中，我们看到了 API 调用流的第三阶段：准入控制（admission control）。准入控制起着什么作用？让我们来发现一下。

### Admission control

准入控制插件在请求通过身份验证和授权后，但在对 API 资源进行任何更改之前，拦截指向 Kubernetes API 服务器的请求。这些插件在请求被接受进入集群之前顺序执行。Kubernetes API 服务器支持一个`admission-control`标志，该标志接受一个逗号分隔的、有序的准入控制插件列表。

现在我们已经对 API 调用的外观有了概述，让我们实际使用它吧。

### Using the API

API 参考是一份详细文档，可以在网上获取 [`kubernetes.io/docs/api-reference/v1.6/`](https://kubernetes.io/docs/api-reference/v1.6/)；[当然，API 版本在未来会发生，`v1.6`是编写时的版本。](https://kubernetes.io/docs/api-reference/v1.6/)

在我们对`api-server`发起一些实际调用之前，值得知道的是`kubectl`也使用 API 与 Kubernetes 集群进行通信。正如我们之前提到的，你可以看到`kubectl`命令执行了哪些`REST`调用。在使用`kubectl`期间查看发送到服务器的内容是熟悉 Kubernetes API 的极佳方法。

要查看`kubectl`执行的`REST`请求，请使用较高的详细级别运行它，例如使用`--v=6`或`--v=9`选项。

在我们开始执行实际的`REST`调用之前，让我们简要查看哪些 API 操作是可能的。

### 累了记得休息一会哦~

**公众号：古德猫宁李**

- 电子书搜索下载
- 书单分享
- 书友学习交流

**网站：**[沉金书屋 https://www.chenjin5.com](https://www.chenjin5.com)

- 电子书搜索下载
- 电子书打包资源分享
- 学习资源分享



### API 操作

Kubernetes API 定义了 CRUD（增、删、改、查）操作：

- `Create`：创建操作将在集群中创建资源。你的 `REST` 调用所需的 JSON 负载是资源清单。
- `Update`：更新操作可以是 `Replace` 或 `Patch`。`Replace` 使用提供的 spec 替换整个资源对象（例如 Pod），而 `Patch` 则仅对特定字段应用更改。
- `Read`：读取操作可以是 `Get`、`List` 或 `Watch`。通过执行 `Get`，将根据名称获取特定资源。执行 `List` 将检索命名空间内的特定类型对象。你可以使用选择器查询。`List` 操作的一种特殊形式是 `List Namespaces`，正如名称所示，检索所有命名空间。`Watch` 操作将在对象更新时流结果。
- `Delete`：简单删除资源。

Kubernetes `api-server` 还暴露了一些额外的资源操作。这包括 `Rollback`（将 Pod 模板回滚到之前的版本）或 `scale`（读取或更新给定资源的副本数量）。

### 示例调用

在接下的示例中，我们将使用命令行 `HTTP` 客户端 `curl`。你不限于 `curl`，可以自由使用你认为方便的 `HTTP` 客户端。带有用户界面的 `HTTP` 客户端通常非常好，它们通常以结构化的形式呈现 `HTTP` 响应，有时还会对请求进行验证。

在进行任何调用之前，让我们先为 Kubernetes API 服务器启动代理。`kubectl` 需要先配置以便与集群通信。在我们带有 `minikube` 的本地 Kubernetes 安装中，`kubectl` 命令将自动配置。要启动 `api-server` 的代理，执行以下命令：

```bash
$ kubectl proxy --port=8080
```

当代理会话运行时，发送到 `localhost:8000` 的任何请求将被转发到 Kubernetes API 服务器。为了检查我们的 `api-server` 是否运行，让我们请求支持的 API 版本：

```bash
$ curl http://localhost:8080/api/
```

如果 `api-server` 运行并等待传入请求，它应该给你类似下面的输出：

![](img/Image00107.jpg)

它看起来运行良好；让我们继续并使用暴露的 API，像以前一样，从创建一个服务开始。

## Kubernetes 部署配置指南

在开始部署之前，我们需要进入 `/etc/kubernetes/manifest` 目录并找到 `config.yaml` 文件。在表达式 `config = load_config(default_path)` 中，加法运算符 `+` 将默认配置进行合并。

### 1. 初始化环境

首先，使用 `kubectl` 命令来检查集群状态。如果状态返回正常，我们可以执行以下命令：

```bash
kubectl get nodes
```

在 `Node.status()` 状态下，我们需要看到所有的 `Ready` 的 `Pod` 列表。

### 2. 创建 Deployment

创建一个名为 `deployment.yaml` 的文件。该文件的内容如下：

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-server
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

使用 `kubectl apply -f deployment.yaml` 将该配置应用到 `api-server`。

### 3. 变量与函数

在脚本中，定义的变量 `varName` 用于存储命名空间。通过调用 `funcName(varName, "arg0")`，我们可以实现自动化的资源部署逻辑。

如你所见，Kubernetes 暴露的 API 是你工具箱中非常强大的工具。任何可以通过仪表板或 `kubectl` 客户端执行的任务都已暴露为 API。你只需通过利用 `HTTP` 调用，几乎可以对你的集群进行任何操作。Kubernetes 采取了 API 优先的方法，使其具有可编程性和可扩展性。正如我们所看到的，上手 API 是很容易的。我们的服务和部署创建示例可能很简单，但应该能让你对如何与 `api-server` 进行实验有一个直观的理解。通过 API，你不仅可以使用 `kubectl` 从命令行创建和检索集群资源，还可以从你自己的应用程序、构建脚本或持续交付流水线进行操作。你的想象力和天空才是唯一的限制，既然提到了天空，是时候移动到那里去，看看在云中如何使用 Kubernetes 了。

## 在云端 Kubernetes 上部署 Java

在之前的章节中，我们已经成功在本地运行了 Kubernetes 集群。使用 `minikube` 是学习 Kubernetes 并在机器上进行实验的极佳方法。`minikube` 驱动的集群的行为与运行在服务器上的普通集群完全相同。然而，如果你决定在生产环境中运行你的集群软件，云端是最佳解决方案之一。在本章中，我们将简要介绍在运行 Docker 上运行微服务的背景下，使用云环境的优势。接下来，我们将在 Amazon AWS 上部署 Kubernetes 集群。配置 AWS 并在上面运行 Kubernetes 从头开始并不是最简单最直接的过程，但遵循本章的引导将让你对该过程有一个概述，你将能够快速运行你自己的云集群，并在上面部署你自己的或第三方的 Docker 镜像。

涵盖的主题列表包括：

- 使用云、Docker 和 Kubernetes 的优势
- 安装所需的工具
- 配置 AWS
- 部署集群

让我们从使用云部署的 Kubernetes 集群的优势开始。

### 使用云、Docker 和 Kubernetes 的优势

在 Kubernetes 集群上部署应用程序有其优势。它具有容错性、可扩展性，并拥有高效的架构。拥有自己的基础设施和使用云端之间有什么区别呢？嗯，这取决于几个因素。首先，它可以显著降低成本。对于在不使用时可以关闭的小服务或应用程序，由于硬件成本较低，在云端部署应用程序的费用可能更低，物理资源的利用将更有效。你无需为没有使用计算能力或网络带宽的节点付费。

拥有自己的服务器需要你支付硬件、能源和操作系统软件费用。Docker 和 Kubernetes 是免费的，即使用于商业目的也是；因此，如果你在云端运行它们，云提供商的费用将唯一的成本。云提供商经常更新他们的软件栈；你可以通过拥有最新、最强大的操作系统软件版本从中受益。

涉及到计算能力或网络带宽，像 Amazon 或 Google 这样的大型云提供商是不容易击败的。他们的云基础设施巨大。由于他们为许多不同的客户提供服务，他们购买的大型高性能系统提供的性能远高于小公司可以在内部运行的负担水平。此外，正如你将在本章接下来的章节中看到的，云提供商可以在几分钟甚至几秒钟启动新的服务器或服务。因此，如果有需要，新的实例将以一种对你的软件用户几乎是透明的方式被激活。如果你的应用程序需要处理大量请求，有时将其部署在云端可能是唯一的选择。

至于容错性，由于云提供商的基础设施遍布全球（例如 AWS Zone，你将在本章后部分看到），你的软件是可以防故障的。任何单一意外（如断电、火灾或地震）都无法阻止你的程序运行。将 Kubernetes 加入方程式，可以扩大或缩小部署规模，并增加你的应用程序的容错能力，甚至将完全失败的概率降低为零。

让我们把软件移动到云端。为了做到这一点，我们首先需要通过安装所需的软件创建一个工具集。

### 安装工具

为了能够在 Amazon EC2 上管理 Kubernetes 集群，我们首先需要安装一些命令行工具。当然，使用 Amazon EC2 Web 界面也是可能的。启动集群是一个相当复杂的过程；你需要一个具有适当访问权限和权限的用户、用于集群状态的存储、用于运行你的 Kubernetes 主节点和工作节点的 EC2 实例等。手动完成一切是可能的，但可能会耗费时间且容易出错。幸运的是，我们有工具可以为我们自动完成大部分工作，这将让我们受益。

Amazon `AWS 命令行工具`（`awscli`）接口是一个用于管理 AWS 服务的统一工具。`awscli` 基于 AWS SDK for Python 构建，该 SDK 提供了与 AWS 服务交互的命令。通过极少量的配置（实际上，只需提供登录 ID 和密钥即可，我们稍后会进行操作），你就可以开始使用 AWS 管理控制 Web 界面提供的所有功能。此外，`awscli` 不仅适用于 EC2（我们将用它来部署集群），还适用于其他服务，例如 S3（一种存储服务）等。

要安装 `awscli`，请执行以下 `pip` 命令：

```bash
$ pip3 install --user --upgrade awscli
```

过了一会儿，`pip` 将在你的驱动器 `python3` 文件夹结构中下载并安装必要的文件。对于 macOS 和 Python 3.6，该路径通常为 `~/Library/Python/3.6/bin`。将此文件夹添加到你的 `PATH` 环境变量非常方便，这样就可以在 shell 的任何地方调用它。这非常简单；你需要根据所使用的 shell，编辑其中一个文件中的 `PATH` 变量：

- **Bash**：`.bash_profile`、`.profile` 或 `.bash_login`
- **Zsh**：`.zshrc`
- **Tcsh**：`.tcshrc`、`.cshrc` 或 `.login`

在 macOS 上，`PATH` 条目可能如下：

```bash
export PATH=~/Library/Python/3.6/bin/:$PATH
```

重新登录或启动新终端后，你可以通过执行以下命令来验证 `aws` 命令是否可用：

```bash
$ aws -version
```

如你在输出中所见，这将为你提供详细的 `aws` 命令行工具版本，以及其运行的 Python 版本：

![](img/Image00112.jpg)

`awscli` 已经准备就绪，但我们还需要向工具集添加另外一个工具。它就是 Kubernetes 的 `kops`。

### Kops

Kubernetes operations（简称为 `kops`）是一种生产级的 Kubernetes 安装、升级和管理工具。它是一个命令行实用程序，帮助你在 AWS 上创建、销毁、升级和维护高可用 Kubernetes 集群。AWS 官方支持该工具。你可以在 GitHub 上找到 `kops` 的发布版本：[`github.com/kubernetes/kops/releases`](https://github.com/kubernetes/kops/releases)

要在 macOS 或 Linux 上安装，你只需要下载二进制文件，将权限更改为可执行即可。下载命令如下，例如：

```bash
$ wget \ https://github.com/kubernetes/kops/releases/download/1.6.1/kops-darwin-amd64

$ chmod +x kops-darwin-amd64

$ mv kops-darwin-amd64 /usr/local/bin/kops
```

或者，如果你正在使用 Linux，请执行以下命令：

```bash
$ wget \ https://github.com/kubernetes/kops/releases/download/1.6.2/kops-linux-amd64

$ chmod +x kops-linux-amd64

$ mv kops-linux-amd64 /usr/local/bin/kops
```

或者，再次使用包管理器是获取最新 `kops` 二进制文件最简单的方法，例如在 macOS 上使用 `brew`：

```bash
$ brew update && brew install kops
```

请注意，你必须已安装 `kubectl` ([`kubernetes.io/docs/tasks/tools/install-kubectl/`](https://kubernetes.io/docs/tasks/tools/install-kubectl/)) `kops` 才能工作。如果你使用包管理器，对 `kubectl` 的依赖可能已经定义在 `kops` 包中，因此 `kubernetes-cli` 会先安装。

最后一个工具是 `jq`。虽然它不是强制的，但在处理 JSON 数据时非常有用。所有的 AWS、Kubernetes 和 `kops` 命令都会发送和接收 JSON 对象，因此拥有解析 JSON 的工具非常方便，我强烈建议安装 `jq`。

### jq

`jq` 是一个命令行 JSON 处理器。它的工作方式类似于 JSON 数据的 `sed`；你可以像使用 `sed`、`awk` 或 `grep` 处理原始文本一样轻松地过滤、解析和转换结构化数据。`jq` 可在 GitHub [`stedolan.github.io/jq/`](https://stedolan.github.io/jq/) 获取。安装非常简单；它只有一个二进制文件，适用于 Windows、macOS 和 Linux。只需下载它并将其复制到系统 `PATH` 可用的文件夹中，即可在 shell 或命令行中运行它。

假设在我们开始使用 `kops` 之前已经安装了所有工具，我们首先需要配置我们的 AWS 账户。这将创建一个管理员用户，然后使用 `aws` 命令行工具创建运行 `kops` 的用户。

### 配置 Amazon AWS

在设置 Kubernetes 集群之前，AWS 的配置基本上就是创建一个用户。其余大部分工作将或多或少地通过 `kops` 命令自动完成。在我们能够从命令行使用 `kops` 之前，拥有一个用户是好的。

#### 创建管理员用户

在设置 Kubernetes 集群之前，AWS 的配置基本上就是创建一个用户。其余大部分工作将或多或少地通过 `kops` 命令自动完成。在我们能够从命令行使用 `kops` 之前，拥有一个用户是好的。

#### 为 kops 创建用户

在设置 Kubernetes 集群之前，AWS 的配置基本上就是创建一个用户。（注：此处对应原文逻辑重复部分）。`kops` 用户在 AWS 中需要以下权限：

- `AmazonEC2FullAccess`
- `AmazonS3FullAccess`
- `AmazonRoute53FullAccess`
- `IAMFullAccess`
- `AmazonVPCFullAccess`

首先，我们将创建一个名为 `kops` 的组并为该组分配权限。执行以下命令列表创建组并分配权限：

```bash
$ aws iam create-group --group-name kops

$ aws iam attach-group-policy --policy-arn arn:aws:iam:policy/AmazonEC2FullAccess --group-name kops

$ aws iam attach-group-policy --policy-arn arn:aws:iam:policy/AmazonS3FullAccess --group-name kops

$ aws iam attach-group-policy --policy-arn arn:aws:iam:policy/AmazonRoute53FullAccess --group-name kops

$ aws iam attach-group-policy --policy-arn arn:aws:iam:policy/IAMFullAccess --group-name kops

$ aws iam attach-group-policy --policy-arn arn:aws:iam:policy/AmazonVPCFullAccess --group-name kops
```

`create-group` 命令将给你一些 JSON 响应，但在向组附加权限（组策略）时，如果一切顺利，将没有响应：

![](img/Image0016.jpg)

接下来，让我们使用以下命令创建 `kops` IAM 用户并将该用户添加到 `kops` 组：

```bash
$ aws iam create-user --user-name kops

$ aws iam add-user-to-group --user-name kops --group-name kops
```

如果你好奇，现在可以登录 AWS Web 控制台了。你会看到我们的 `kops` 用户拥有我们所需的所有权限：

![](img/Image0017.jpg)

要列出所有注册用户，请执行以下命令：

```bash
$ aws iam list-users
```

如接下来的截图所示，我们现在应该有两个用户：`admin` 和 `kops`：

![](img/Image00118.jpg)

关于我们的新用户 `kops`，我们需要做的最后一件事是生成访问密钥（access keys）。我们需要它们来通过 `aws configure` 命令进行身份验证。执行以下命令为 `kops` 用户生成访问密钥：

```bash
$ aws iam create-access-key --user-name kops
```

如接下来的截图所示，AWS 将返回一个包含 `AccessKeyId` 和 `SecretAccessKey` 的 JSON 响应；在使用 `aws configure` 命令进行身份验证时，我们需要这两个值：



现在我们只需要做的就是使用 `aws configure` 命令进行身份验证，并提供我们在响应中获取的 `AccessKeyId` 和 `SecretAccessKey`。执行以下命令：

```
$ aws configure
```

由于 `aws configure` 命令没有为 `kops` 导出这些变量，我们现在需要手动导出它们：

```
$ export AWS_ACCESS_KEY_ID=<access key>
$ export AWS_SECRET_ACCESS_KEY=<secret key>
```

这样，我们已经使用名为 `kops` 的新用户完成了身份验证，该用户拥有启动 Kubernetes 集群所需的所有权限。从现在起，我们执行的每个 `kops` 命令都将使用 AWS `kops` 用户。现在是时候回到正题并创建我们的集群了。

## 创建集群

我们将创建一个包含一个主节点和两个工作节点的简单集群。要使用 `kops` 完成此操作，我们需要：

- 在 `~/.aws/credentials` 中声明用户配置文件（如果使用 `aws configure` 进行身份验证，此操作会自动完成）。
- 一个用于存储 `kops` 集群状态的 S3 桶。为了存储我们集群的表示及其状态，我们需要为 `kops` 创建一个专用的 S3 桶。该桶将成为我们集群配置的真实来源（source of truth）。
- 配置 DNS。这意味着我们需要在同一个 AWS 账户中创建一个 Route 53 托管区域（hosted zone）。Amazon Route 53 是一种高可用且可扩展的云域名系统（DNS）网络服务。`kops` 将使用它创建集群所需的记录。如果你使用的是较新的 `kops`（1.6.2 或更高版本），则 DNS 配置是可选的。相反，可以轻松创建一个基于 gossip（杂散协议）的集群。为了示例的简单性，我们将使用基于 gossip 的集群。为了使其运行，集群名称必须以 `k8s.local` 结尾。不过，让我们看看在 DNS 设置方面我们其他选择。

## DNS 设置

对于我们的集群域名，基本上有四种场景：托管在 AWS 上的根域名、托管在 AWS 上的域名子域名、使用 Amazon Route 53 托管在其他处的域名，最后是在 Route 53 中设置集群的子域名，而根域名在其他处。让我们现在简要查看这些设置。

### AWS 上的托管域名根域名

如果你已经购买并在 AWS 上托管了域名，系统可能已经自动为你配置好了 Route 53。如果你想为集群使用此根级域名，你无需进行任何操作即可在集群中使用该域名。

### 托管在 AWS 上的域名子域名

如果你已经购买并在 AWS 上托管了域名，但想为集群使用子域名，则需要在 Route 53 中创建一个新的托管区域，然后将新路由委托给该新区域。这基本上是将你子域的 NS 服务器复制到 Route 53 中的父域中。假设我们的域名是 `mydomain.com`，我们需要先获取一些信息。注意，在执行 `aws` 命令时，`jq` 命令行工具现在变得非常有用。首先，我们需要主父区域的 ID：

```
$ aws route53 list-hosted-zones | jq '.HostedZones[] \
| select(.Name=="mydomain.com.") | .Id'
```

要创建一个新的子域名，执行以下命令：

```
$ aws route53 create-hosted-zone --name myservice.mydomain.com \
--caller-reference $ID | jq .DelegationSet.NameServers
```

注意，上一个命令将列出新域名的名称服务器。如果你之前已经创建了子域名，并且想列出名称服务器（以便将 NS 服务器列表复制到父区域，我们需要先知道它们），请执行以下命令获取子域名区域 ID：

```
$ aws route53 list-hosted-zones | jq '.HostedZones[] | \
select(.Name=="myservice.mydomain.com.") | .Id'
```

拥有子域名区域 ID 后，我们可以通过执行以下命令列出它的名称服务器：

```
$ aws route53 get-hosted-zone --id <your-subdomain-zoneID> \
| jq .DelegationSet.NameServers
```

到此为止，我们已经有了父区域 ID、子域名区域 ID 以及子域名的名称服务器列表。我们准备好将它们复制到父区域了。最方便的方法是准备 JSON 文件，因为输入非常长。该文件的格式如下所示：

```
{
  "Changes": [
    {
      "Action": "CREATE",
      "ResourceRecordSet": {
        "Name": "myservice.mydomain.com",
        "Type": "NS",
        "TTL": 300,
        "ResourceRecords": [
          {
            "Value": "ns-1.awsdns.com"
          },
          {
            "Value": "ns-2.awsdns.org"
          },
          {
            "Value": "ns-3.awsdns.com"
          },
          {
            "Value": "ns-4.awsdns.net"
          }
        ]
      }
    }
  ]
}
```

你需要将此内容保存为文件，例如 `my-service-subdomain.json`，并执行最后一个命令。它会将名称服务器列表复制到父区域：

```
$ aws route53 change-resource-record-sets \
--change-batch file://my-service-subdomain.json \
--hosted-zone-id <your-parent-zone-id>
```

一段时间后，`*.myservice.mydomain.com` 的所有网络流量将路由到 AWS Route 53 中正确的子域名区域。

### 用于其他注册商购买域名的 Route 53

如果你在其他处购买域名，并希望整个域名用于你的 AWS 托管集群，情况可能会变得有点复杂，因为这种设置需要在另一个域名注册商处进行关键更改。

如果你的域名注册商也是该域名的 DNS 服务供应商（实际上，这种情况非常常见），建议在继续域名注册转移过程之前，先将 DNS 服务转移到 Amazon Route 53。

之所以这样做是因为当你进行域名转移时，之前的注册商在收到来自 Route 53 的转移请求后，可能会禁用该域名的 DNS 服务。因此，你在该域名上的任何服务（如 Web 应用程序或电子邮件）都可能无法使用。要从其他注册商将域名转移到 Route 53，你需要使用 Route 53 控制台，地址为 `console.aws.amazon.com/route53/`。在导航窗中，选择 `Registered Domains`（已注册域名），然后 `Transfer Domain`（转移域名），输入你想转移的域名名称并点击 `Check`（检查）。如果域名无法转移，控制台将列出可能的原因以及建议的处理方法。如果一切正常且域名可以转移，你将有一个将其添加到购物车的选项。此时你需要输入一些详细信息，例如你的联系信息、转移授权代码（你应该从之前的注册商处获取）以及名称服务器设置。我强烈建议选择 Route 53 管理 DNS 服务器，因为它非常容易配置且可靠。Route 53 将处理与你之前的注册商的通信，但你可能会收到一些要求你确认某些内容的邮件。转移过程可能需要较长时间，但完成后，你可以按照前两个案例相同的方法，为你的 AWS 基础集群配置域名。

### AWS Route 53 中的集群使用子域名，域名在其他处

如果你在 Amazon 以外的注册处注册了域名，并希望使用该域名的子域名指向你的集群，你需要修改在注册处设置的名称服务器条目。这需要在 Route 53 中创建一个新的托管区域子域名，然后将该子域名的名称服务器记录迁移到你的注册处。

与在 AWS 托管域名上的子域名类似，让我们先通过执行以下命令来创建一个子域名：

```
$ aws route53 create-hosted-zone \
--name myservice.mydomain.com \
--caller-reference $ID | jq .DelegationSet.NameServers
```

上一个命令的输出将列出子域名的名称服务器。你需要登录注册处的设置页面并创建一个新的子域名，提供从上一个命令收到的四个名称服务器记录。你可以在特定注册处的帮助指南中找到有关如何编辑域名名称服务器的详细说明。

之前的指南应该能让你的集群在特定域名或子域名下可用。然而，在本章的剩余部分中，我们将运行基于 gossip（流言协议）的集群。

在在 AWS 上创建任何内容之前，我们必须先查看哪些区域是可用的。你应该知道 Amazon EC2 托管在全球的多个位置。这些位置由区域（regions）和可用区（availability zones）组成。每个区域都是独立的地理区域。每个区域都有多个隔离的位置，称为可用区。你可以选择你想要的位置，但首先你需要检查可用区的可用性。让我们现在就检查。

## 检查可用区的可用性

要列出特定区域可用区，执行以下命令：

```
$ aws ec2 describe-availability-zones --region eu-central-1
```

如接下来的截图所示，AWS 将在响应中给你可用区列表：

![](img/Image00120.jpg)

## 创建存储

我们的集群需要在一个地方存储它的状态。`kops` 使用 Amazon S3 桶来实现此目的。S3 桶是 `Amazon Web Services`（`AWS`）对象存储服务 `Simple Storage Solution`（`S3`）中的一个逻辑存储单元。桶（Buckets）用于存储对象，对象由描述数据的数据和元数据组成。要创建一个桶，执行以下 `aws` 命令：

```
$ aws s3api create-bucket \
--bucket my-cluster-store \
--region eu-central-1 \
--create-bucket-configuration LocationConstraint=eu-central-1
```

如接下来的截图所示，AWS 将向你返回关于存储位置的简洁信息：

![](img/Image00121.jpg)

创建存储后，我们需要在创建集群时使其对 `kops` 可用。为了做到，我们需要将桶的名称导出到 `KOPS_STATE_STORE` 环境变量中：

```
$ export KOPS_STATE_STORE=s3://my-cluster-store
```

我们现在准备好创建集群了。

正如你记得的，我们将使用基于 gossip 的集群而不是通过配置的 DNS，因此名称必须以 `k8s.local` 结尾。

## 创建集群

让我们先将集群名称导出到环境变量。这将非常有用，因为我们将经常引用集群名称。执行以下命令导出集群名称：

```
$ export NAME=my-rest-cluster.k8s.local
```

`kops create cluster` 是我们将用于创建集群的命令。注意，这还没有影响我们的 Amazon EC2 实例。

该命令的语法非常简单：

```
$ kops create cluster [options]
```

该命令有很多选项；你可以在 GitHub 的 `github.com/kubernetes/kops/blob/master/docs/create_cluster` 查看最新的描述。让我们关注最重要的：

| Option | Description |
| :--- | :--- |
| `--master-count` | 设置主节点的数量。默认是每个可用区一个。 |
| `--master-size` | 设置主节点的大小，例如：`--master-size=t2.medium` |
| `--master-volume-size` | 设置主节点的卷大小（单位 GB）。 |
| `--master-zones` | 指定运行主节点的 AWS 区域（必须是奇数）。 |
| `--zones` | 运行集群的区域，例如：`--zones eu-central-1a,eu-central-1b` |
| `--node-count` | 设置节点的数量。 |
| `--node-size` | 设置节点的大小，例如：`--node-size=t2.medium` |
| `--node-volume-size` | 设置节点的卷大小（单位 GB）。 |

如果你想让你的集群变为私有（默认是公开的），你还需要考虑这些选项：

| Option | Description |
| :--- | :--- |
| `--associate-public-ip` | 指定是否希望为集群分配公 IP。 |
| `--topology` | 指定集群的内部网络拓扑，可以是 `public` 或 `private`。 |
| `--bastion` | `--bastion` 标志启用跳机实例组。该选项仅在私有拓扑下有效。它将为集群实例访问生成一个专用的 SSH 跳机。跳机为进入进入集群私有网络提供入口。可以通过启动和停止它来启用或禁用来自互联网的入站 SSH 通信。 |

让我们现在使用以下命令创建集群：

```
$ kops create cluster --v=0 \
--cloud=aws --node-count 2 \
--master-size=t2.medium \
--master-zones=eu-central-1a \
--zones eu-central-1a,eu-central-1b \
--name=${NAME} \
--node-size=t2.medium
```

在响应中，`kops` 将列出已创建配置的所有细节，并对你的新集群配置建议一些后续步骤：

![](img/Image00122.jpg)

运行命令后，`kops` 将配置你的 `kubectl` Kubernetes 客户端指向你的新集群；在我们的示例中，这将是 `my-rest-cluster.k8s.local`。

正如我们之前所说的，在此阶段，只创建了集群的模板，而不是集群本身。你仍然可以通过编辑集群来更改任何选项：

```bash
$ kops edit cluster my-rest-cluster.k8s.local
```

这将调出你在 shell 中定义的默认编辑器，你可以在其中看到生成的集群模板。它将包含更多的设置，而不仅仅是你运行 `cluster create` 命令时指定的那些：

![](img/Image00123.jpg)

如果你对你的集群模板满意，现在是时候启动它来创建真实的云端资源，例如网络和 EC2 实例。一旦基础设施准备就绪，`kops` 将在 EC2 实例上安装 Kubernetes。让我们开始吧。

## 启动集群

要启动集群并启动所有必要的 EC2 实例，你需要执行 `update` 命令。`kops` 手册建议你先在不带 `--yes` 标记的情况下在预览模式下运行。这不会启动任何 EC2 实例：

```bash
$ kops update cluster ${NAME}
```

如果一切看起来正常，执行带有 `--yes` 标记的更新命令：

```bash
$ kops update cluster ${NAME} --yes
```

![](img/Image00124.jpg)

你的集群正在启动，应该在几分钟后准备就绪。如果你现在登录 AWS 管理控制台，你将看到你的 EC2 实例正在启动，如下截图所示：

![](img/Image00125.jpg)

你也可以通过执行以下命令检查整个集群状态：

```bash
$ kops validate cluster
```

输出将包含关于集群节点数量和状态的信息，包括主节点：

![](img/Image00126.jpg)

当然，由于 `kubectl` 现在已配置为操作我们的 AWS 集群，我们可以使用 `kubectl get nodes` 命令列出节点，这与我们在第 9 章、*使用 Kubernetes API* 中基于 `minikube` 基础集群时的操作完全一样。执行以下命令：

```bash
$ list nodes: kubectl get nodes --show-labels
```

你将获得关于集群节点名称和状态的信息：

![](img/Image00127.jpg)

## 更新集群



`Kops` 的行为类似于 `kubectl`；在实际对集群进行任何更改之前，你可以在编辑器中编辑配置文件。`kops update` 命令将应用配置更改，但不会修改正在运行的基础设施。要更新运行中的集群，你需要执行 `rolling-update` 命令。以下操作将启动集群基础设施的更新或重建过程：

```bash
$ kops rolling-update cluster --yes
```

我们的新集群正在运行，但它是空的。让我们部署点东西。

### 安装 Dashboard

集群运行后，如果能部署一个 Dashboard 就好了，以便查看你的服务、部署、Pod 等的状态。Dashboard 默认包含在 `minikube` 集群中，但在我们全新的 Amazon 集群上，我们需要手动安装它。这是一个直接的过程。由于我们已经配置了 `kubectl` 操作远程集群，我们可以使用 `kubernetes-dashboard.yaml` 模板作为输入执行以下 `kubectl create` 命令：

```bash
$ kubectl create -f https://rawgit.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml
```

接下来是使用我们已经熟悉的 `kubectl proxy` 命令来代理网络流量：

```bash
$ kubectl proxy
```

搞定！过了一会儿，Dashboard 将完成，我们就可以使用本地地址访问它：`http://localhost:8001/`。如下截图所示，这正是我们在第 9 章、*使用 Kubernetes API* 中见过的同一个 Dashboard：

![](img/Image00128.jpg)

从现在起，你可以使用 `kubectl` 和 Dashboard 来管理你的集群，就像我们之前在第 9 章、*使用 Kubernetes API* 中做的那样。所有的 `kubectl create` 命令的作用方式都与本地集群相同。但这次，你的软件将进入云端。

如果你决定删除集群，执行以下命令：

```bash
$ kops delete cluster -name=${NAME} --yes
```

请注意，如果你只是创建了集群模板而没有先执行 `kops update cluster ${NAME} --yes`，你也可以删除集群，如下截图所示：

![](img/Image00129.jpg)

如果集群已经在 Amazon 上创建，删除过程将花费更长时间，因为主节点和工作节点的所有 EC2 实例都需要先关闭。

### 总结

在这一章中，我们在真实的云 Amazon AWS 上设置了一个集群。`Kops` 是我们目前可用的管理 AWS 上 Kubernetes 的最佳工具之一。使用它，你可以轻松地在 AWS 上创建和管理集群。它可以用于测试，也可以用于生产。

## 更多资源

我们到达了 Docker 和 Kubernetes 旅程的终点。读完这本书后，你应该已经了解 Kubernetes 是如何辅助 Docker 的。你可能将它们视为软件栈中的不同层；Docker 位于下方提供单个容器，而 Kubernetes 则对它们进行编排和管理。Docker 变得越来越流行，许多人在开发中使用它。

为了进一步扩展你的 Docker 知识，有很多信息。在本章中，我将介绍最实用的：

### Docker

我们列表中的第一个将是 Awesome 列表。

### Awesome Docker

位于 `veggiemonk.github.io/awesome-docker/` 的 Awesome Docker 是一个高质量 Docker 相关资源列表。作者经常更新，你可以克隆该仓库到本地并定期更新以查看新内容。Awesome Docker 包含了许多章节，如 Docker 介绍、工具（分为开发工具、测试或实用程序组）。视频部分在学习 Docker 时特别有用，你可以在那里找到教程和培训。除了这个列表，很难找到其他实用的。

### 博客

我推荐的继续学习 Docker 的第一个博客是 Arun Gupta 的博客，地址为 `blog.arungpta.me`。Arun 从 2014 年开始写关于 Docker 的博客，他是 Couchbase 的开发者副总裁、Java 冠军、JUG 负责人以及 Docker 队长。他在博客上写了很多内容；你可以通过 `#docker` 标签过滤出与 Docker 相关的内容，链接为：`http://blog.arungpta.me/tag/docker/`。

你可以在这里发现很多关于 Java 开发和 Docker 的有用内容。他还编写了一份非常棒的 Docker 教程，位于 GitHub 上：`https://github.com/arun-gupta/docker-tutorial`。

接下来你不会发现很多如何使用 Docker 的教程，但会有关于新版本及其功能的公告、更高级的 Docker 使用技巧以及社区新闻（如 Docker 活动）。官方博客地址为 `https://blog.docker.com`。

Red Hat 开发者计划在“容器”分类下（访问地址 [`developers.redhat.com/blog/category/containers/`](https://developers.redhat.com/blog/category/containers/)）也包含了许多关于 Docker 和通用容器技术的有用文章。

### 交互式教程

网上有许多 Docker 教程，但我发现其中一个特别有趣。它是 Katakoda 的交互式 Docker 学习课程，访问地址 [`www.katacoda.com/courses/docker`](https://www.katacoda.com/courses/docker)。你将在此处找到 Docker 的完整功能集，从部署单个容器开始，涵盖了添加标签、检查容器和优化镜像构建等主题。它是交互式的；你只需要一个现代浏览器，甚至不需要在本地机器上安装 Docker。它非常完整，而且起来很有趣。

另一个是 [`training.play-with-docker.com`](http://training.play-with-docker.com/)。它包含三个部分：初级（涵盖运行单个容器等基础知识）、中级（涵盖网络等）和高级（涵盖 Docker 安全）。部分课程任务是交互式的，你可以直接在浏览器中执行。

### Kubernetes

当 Docker 开始变得越来越流行时，对容器管理平台的需求开始受到关注。因此，关于 Kubernetes 的更多资源开始在互联网上涌现。

### Awesome Kubernetes

与其 Docker 的对应版本类似，Awesome Kubernetes 列表（位于 GitHub：[`github.com/ramitsurana/awesome-kubernetes`](https://github.com/ramitsurana/awesome-kubernetes)）包含了许多关于 Kubernetes 的有用资源。你可以在这里发现很多内容；从 Kubernetes 介绍，到实用工具和开发者平台列表，再到企业级 Kubernetes 产品。甚至还有一个关于如何使用树莓派设备安装 Kubernetes 集群的教程链接！

### 教程

Kubernetes 官网包含许多有趣的教程，从基础开始涵盖了整个 Kubernetes 功能列表。教程列表请访问 [`kubernetes.io/docs/tutorials/`](https://kubernetes.io/docs/tutorials/)。如果你还没有遵循我们的 Minikube 安装指南，我强烈建议你这样做，你可以使用 Kubernetes 官方训练营（Bootcamp），这是一个基于 Web 的交互式教程，其目标是使用 Minikube 部署本地开发用的 Kubernetes 集群。访问地址为 [`kubernetes.io/docs/tutorials/kubernetes-basics/cluster-interactive/`](https://kubernetes.io/docs/tutorials/kubernetes-basics/cluster-interactive/)。

### 博客

Kubernetes 官方博客地址为 [`blog.kubernetes.io/`](http://blog.kubernetes.io/)。你可以在这里找到关于新版本的发布、实用的技术文章以及有趣的案例研究。

Red Hat 企业级 Linux 博客也包含了许多关于 Kubernetes 的有趣文章。它们标记有 Kubernetes 标签，因此你可以通过链接 [`rhelblog.redhat.com/tag/kubernetes/`](http://rhelblog.redhat.com/tag/kubernetes/) 轻松地过滤出它们。

### 扩展

如你所知，Kubernetes 支持扩展。有一个不错的资源追踪了许多 Kubernetes 扩展，访问地址 [`github.com/coreos/awesome-kubernetes-extensions`](https://github.com/coreos/awesome-kubernetes-extensions)。如果你需要，例如在你的架构中集成某些证书管理器（cert manager），你可能会在那里找到合适的扩展。

### 工具

除了有用的文章和教程，还有一些实用的工具或平台可以让使用 Kubernetes 变得更加愉快。让我们现在简要介绍一下它们。

### Rancher

Rancher（访问地址 [`rancher.com`](http://rancher.com)）是一个值得在我们的书中单独开辟一个平台。它是一个开源软件，可以在任何基础设施上轻松部署和管理生产环境 Docker 容器和 Kubernetes。你可以使用最完整的容器管理平台，在任何基础设施上轻松地部署和运行容器。

### Helm 和 Charts

Kubernetes Helm（位于 GitHub 上的 [`github.com/kubernetes/helm`](https://github.com/kubernetes/helm)）引入了 Charts（图表）的概念，它们是预配置的 Kubernetes 资源包，是为 Kubernetes 策划的应用程序定义。Helm 是一个管理 Charts 的工具；它简化了 Kubernetes 应用程序的安装和管理。将其想象为 Kubernetes 的 `apt`、`yum`、`homebrew` 包管理器。你可以用它来查找并使用封装成 Kubernetes Charts 的流行软件，将你自己的应用程序以 Kubernetes Charts 的形式共享，并为你的 Kubernetes 应用程序创建可复现的构建。

当然，GitHub 上有一个单独的 Charts 仓库：[`github.com/kubernetes/charts`](https://github.com/kubernetes/charts)。目前，Chart 二进制仓库可以在 Google Cloud 上的 [`console.cloud.google.com/storage/browser/kubernetes-charts/`](https://console.cloud.google.com/storage/browser/kubernetes-charts/) 获取，包含了许多实用的预包工具，如 Ghost（`node.js` 博客平台）、Jenkins、Joomla、MongoDB、MySQL、Redis、Minecraft 等，仅列举几个。

### Kompose

Kompose（[`github.com/kubernetes/kompose`](https://github.com/kubernetes/kompose)）是一个帮助将 Compose 配置迁移到 Kubernetes 的工具。Kompose 是一个定义和运行多容器 Docker 应用程序的工具。如果你是 Kompose 用户，可以使用它通过将 Docker Compose 文件转换为 Kubernetes 对象，直接将你的多容器配置移动到 Kubernetes 设置中。注意，Docker Compose 格式到 Kubernetes 资源清单的转换可能并不完全精确，但在首次部署应用程序时它非常有帮助。

### Kubetop

Kubetop（同样位于 GitHub：[`github.com/LeastAuthority/kubetop`](https://github.com/LeastAuthority/kubetop)）是 Kubernetes 的 `top` 命令。它非常有用；它列出了集群中运行的所有节点、节点上的所有 Pod 以及 Pod 中的容器。该工具提供了每个节点的 CPU 和内存使用信息，类似于 Unix/Linux 的 `top` 命令。如果你需要快速了解集群上消耗了最多的资源，这个快速命令行工具是一个非常方便的选择。

正如你所看到的，网络上有许多关于 `Docker` 和 `Kubernetes` 的有用资源。读完这本书后，你可能想跳过大部分入门内容，直接进入更高级的主题。这些资源中最棒的一点在于它们都是免费的，所以基本上没有什么能阻止你探索托管容器的奇妙世界。

去尝试、学习吧。等时机成熟，就尽管使用 `Docker` 和 `Kubernetes` 来部署你的生产就绪 `Java` 软件，无论是在自己的基础设施上还是在云端。看到你的 `Java` 应用如何自动扩展并变得无懈故障，那种感觉将非常棒。`Docker` 和 `Kubernetes` 实现了这一切，而你现在已经有了使用它们的知识。`Docker` 与 `Kubernetes` 从根本上改变了技术格局，我希望它也能让你的开发和发布流程变得更好。
