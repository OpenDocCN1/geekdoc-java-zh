
# Jakarta EE、NoSQL 数据库与微服务构建现代 Web 应用指南

轻松使用微服务、JNoSQL、Vaadin、Jmoordb 和 MicroProfile 创建 Jakarta EE Web 应用程序

![](img/cover.jpg)

![image](img/cover.jpg)

![](img/line.jpg)

![](img/line.jpg)

![](img/logo.jpg)

## 献给

**Aristides Villarreal Bravo**

给我的爷爷“Papa del Rio”、父母、兄弟、侄子们、我的家人，以及那些相信某些事物并努力寻找它们的人。

**Geovanny Mendoza Gonzalez**

给“Emiro Mendoza `El Miche`（已故）”

给在天堂上关照我的父亲，给我的母亲 Maria Eugenia，给我的姐妹 Claudia 和 Maria，给我的儿子 Matias。

**Otávio Gonçalves de Santana**

我想感谢在这段旅程中支持我的每一个人。我的妻子、我的朋友，当然，还有整个 Java 社区允许我撰写这本书并获得分享我所知的机会。我希望这本书对每个人都有用。

## 关于作者

**Aristides Villarreal Bravo** 居住在巴拿马，是一名 Java 开发人员，自 2007 年起一直是 NetBeans Dream Teams 的成员、Jug 负责人。他目前致力于开发 Java 应用，并关注 Java 企业版、`Jakarta EE`、`Microprofile` 和 NoSQL 数据库等技术。

他为 `Apache NetBeans IDE` 开发了多个插件，并正在开发他的 `Jmoordb` 项目（一个用于 NoSQL 的 Java API）。他参加过许多国内和国际会议，并担任过多本 Java 及相关技术书籍评审员。JEspañol 成员，2017 年 Duke 选择奖获得者。

在他的个人网站 [`avbravo.blogspot.com/`](http://avbravo.blogspot.com/) 上发表过文章。

**Geovanny Mendoza Gonzalez** 是 Java 高级后端开发人员，居住在哥伦比亚，拥有哥伦比亚 Simón Bolívar 大学系统工程学士学位以及哥伦比亚巴兰基拉北方大学软件工程专业学位。拥有 `Vaadin 14` 框架认证的专业人士和开发者。巴兰基拉-哥伦比亚 Java 用户组（[www.jugbaq.org](http://www.jugbaq.org)）的负责人，拥有超过 12 年的软件开发经验。

他在国际 Java 会议上使用行业内最新的实践和框架进行演讲。他还在自己的博客中编写关于 `JVM` 相关主题的文章。

博客链接：[`geovanny0401.blogspot.com.co`](https://geovanny0401.blogspot.com.co)

LinkedIn 个人个人页：[`www.linkedin.com/in/gmendozag/`](https://www.linkedin.com/in/gmendozag/)

**Otávio Gonçalves de Santana** 是一位专注于 Java 技术的激情软件工程师。他在金融、社交媒体和电子商务领域的持久化多语言和高性能应用方面拥有经验。Otavio 是多个 `JSRs` 的专家小组成员，以及 `JCP` 执行委员会的专家领袖。他正在致力于……

## 关于评审员

**Constantin Drabo** 获得法国皮卡第朱尔·维文大学（Université Picardie Jules Verne）计算机科学硕士学位。他目前在塞内加尔的波迪拉索纳齐尼大学（Université Nazi Boni）兼职教学，教授 `Java` 和 `Jakarta EE`。

他通过对 `NoSQL` 和机器学习的贡献参与 Java 社区进程（`JCP`）。Constantin 于 2014 年成为 `NetBeans Dream Team` 成员，并于 2018 年获得 Duke 选择奖。

## 致谢

我想感谢这些年来影响我并为创作这本书提供灵感的人们。

感谢我的好朋友 Geovanny Mendoza，多年来我们合作过多个项目。当然还有 Otavio，他是许多人的学习榜样，也是 Java 伟大的创新者和贡献者。

我想感谢我的朋友 Constantin（@PandaConstantin），他的建议和贡献使这本书尽可能地贴合良好的开发实践和标准。

感谢 BPB Publications 全体团队。

感谢多年来 Java、`NetBeans` 和 `Oracle` 社区的朋友们。

Web 应用在多年来不断演变。Java 自诞生以来就与业务发展紧密相连。为了实现标准化并促进此类应用的开发，Java 企业版（Java Enterprise Edition）应运而生。本书将向你介绍用于在高性能环境中创建解决方案的主要规范。

随着时间的推移，出现了一场实现打破传统模式的新数据库技术的运动，这些数据库被归类为类的 NoSQL。大多数章节都侧重于使用 `Jakarta NoSQL` 和 `Jmoordb` 进行实现，这些工具便于在 Java 中使用。

微服务在现代时代对于创建可扩展的应用程序至关重要。`Microprofile.io` 是 Java 创建微服务的参考标准。

一些框架可以帮助我们创建用户界面。其中，我们将学习 `Java Server Faces`、`Vaadin` 和 `Eclipse Krazo` 作为应用开发的重要替代方案。

我们将以应用跟踪和容器测试等主题结束，以提供使用 Java 开发企业级应用时需要考虑的主要工具概述。

我们开发了十十章，你可以在其中找到以下主题：

- **第 1 章：** Jakarta EE 平台简介。你将通过实际示例了解相关规范。
- **第 2 章：** 我们探索 NoSQL 数据库的基础及其优势。
- **第 3 章：** `Jakarta NoSQL` 是一个 Jakarta EE 规范，简化了 Java 应用与 NoSQL 数据库的集成。
- **第 4 章：** 描述了 `Jmoordb` API 如何与 NoSQL 数据库 `MongoDB` 交互。
- **第 5 章：** `Eclipse MicroProfile` 计划的目标是为微服务架构优化企业 Java。它基于 `Jakarta EE` API 的子集，因此我们可以以构建 `Jakarta EE` 应用的方式构建 `MicroProfile` 应用。
- **第 6 章：** 探索 `Java Server Faces` 及其与微服务以及 `MongoDB` 的集成。
- **第 7 章：** 介绍了 `Vaadin` 框架，它旨在使用 `Vaadin` Web 组件用 Java 或 JavaScript 开发 Web 应用，允许你仅几几行代码构建强大的用户界面。
- **第 8 章：** 描述了如何从零开发 Java Web 应用，设计用户界面代码在服务器上安全运行，紧邻你可以通过原生 `Java API` 访问的业务逻辑。将 `Vaadin` 框架与非关系数据库（如 `MongoDB`）集成。
- **第 9 章：** 这是新的 MVC 框架 `Eclipse Krazo` 的介绍，我们使用 `Java security API` 为应用设置安全性，并展示如何简单地使用 `JWT`。
- **第 10 章：** 解释容器、测试、持续集成、`DevOps` 作为创建稳健安全应用程序的基础部分。

## 下载代码

代码包和彩色图片：

请点击链接下载书籍的 `Code Bundle` 和 `Coloured Images`：

# [`rebrand.ly/qble64n`](https://rebrand.ly/qble64n)

## 勘误表

我们对 `BPB Publications` 的工作感到非常自豪，并遵循最佳实践以确保内容的准确性，为我们的订阅者提供享受的阅读体验。读者是我们的镜子，我们利用他们的反馈来反映并改进出版过程中可能发生的任何人为错误。为了让我们保持质量并帮助我们联系可能因意外错误而遇到困难的读者，请发送邮件给我们：

**errata@bpbonline.com**

`BPB Publications’ Family` 非常感谢你的支持、建议和反馈。

你知道吗，`BPB` 为每本出版书籍提供电子书版本，并提供 `PDF` 和 `ePub` 文件？你可以在 `[www.bpbonline.com](http://www.bpbonline.com)` 升级到电子书版本，作为纸质书客户，你有权获得电子书的折扣。请通过 `business@bpbonline.com` 与我们联系获取更多详情。

在 `[www.bpbonline.com](http://www.bpbonline.com)`，你还可以阅读免费技术文章集，订阅一系列免费时通讯，并接收 `BPB` 书籍和电子书的专属折扣和优惠。

## BPB 正在寻找像你这样的作者

如果你有兴趣成为 `BPB` 的作者，请访问 `[www.bpbonline.com](http://www.bpbonline.com/)` 并于今天申请。我们已经与数千名像你这样的开发者和技术专业人士合作，帮助他们向全球技术社区分享见解。你可以进行通用申请，申请我们正在招募作者的特定热门话题，或提交自己的想法。

书籍的代码包也托管在 `GitHub` 上，地址为 [`github.com/bpbpublications/Building-Modern-Web-Applications-with-Jakarta-EE-No-SQL-Database-and-Microservices`](https://github.com/bpbpublications/Building-Modern-Web-Applications-with-Jakarta-EE-No-SQL-Database-and-Microservices)。如果代码有更新，将在现有的 `GitHub` 仓库中更新。

我们丰富的书籍和视频目录中的其他代码包可在 [`github.com/bpbpublications`](https://github.com/bpbpublications) 获取。

## 盗版

如果你在互联网上发现我们作品任何形式的非法副本，如果向我们提供位置或网站名称，我们将不胜感激。请通过 `business@bpbonline.com` 联系我们。

## 如果你有兴趣成为作者

如果你在某个领域拥有专业知识，并对撰写或贡献书籍感兴趣，请访问 `[www.bpbonline.com](http://www.bpbonline.com/)`。

## 评论

请留下你的评论。当你阅读并使用此书后，为什么不在你购买的网站上留下评论呢？潜在读者可以看到并利用你的无偏意见来做出购买决策，我们 `BPB` 可以了解你对产品的看法，我们的作者也可以看到你对书籍的反馈。谢谢！

欲了解更多 `BPB` 的信息，请访问 `[www.bpbonline.com](http://www.bpbonline.com)`。

这些组件基于来自 JavaEE 平台生态系统的规范（`JSR`），该平台由 Java 社区进程（[`jcp.org`](http://jcp.org)）领导，但在 Eclipse Jakarta EE 和 Eclipse Microprofile 标准（[`microprofile.io/`](https://microprofile.io/)）下被品牌重命名；这些标准由公司、用户组和社区组成，并对它们达成共识，以适应行业的新需求。

作为规范一部分 API 被称为 `Java Specification Request (JSR)`。

# 历史

Java EE 平台在近年来发生了重大变化，使得开发更加简单，通过可重用组件改进了性能，从而产生出更轻量且可扩展的应用程序，以适应云和微服务等环境。

我们将简要回顾该平台过去几年的演变，展示每个版本以及相应的规范。

下表显示了平台的不同版本：

| 版本 | 描述 | 日期 |
| :--- | :--- | :--- |
| JPE Project | 第一版本 | 1998 年 5 月 |
| J2EE 1.2 | Servlet, JSP, EJB, JMS, RMI, IIOP | 1999 年 12 月 12 日 |
| J2EE 1.3 | CMP, Connector Architecture | 2001 年 9 月 24 日 |
| J2EE 1.4 | Web Services, Mgmt, Deployment, Async Connector | 2003 年 11 月 11 日 |
| Java EE 5 | Easy of Development Annotations, EJB 3.0, JPA, JSF, JAXB, JAX-WS, Stax, SAAJ | 2006 年 5 月 11 日 |
| Java EE 6 | Extensibility Profiles, Ease of Dev, EJB 3.1 Lite, RESTFull, CDI, JAX-RS | 2009 年 12 月 20 日 |
| Java EE 7 | JMS 2.0, Batch, Web Socket, JSON | 2013 年 5 月 28 日 |
| Java EE 8 | CDI 2.0, JSON-B 1.0, Java Servlet 4.0, JAX-RS 2.1, JSF 2.3, JSON-P 1.1, Java EE Security API 1.0, Bean Validation 2.0, Common Annotations 1.3, Java Persistence 2.2, Java API for WebSocket 1.1, Java Mail 1.6 | 2017 年 9 月 21 日 |

**表 1.1**

# 从 JavaEE 到 Jakarta EE

随着时间的推移，公司和开发者社区开始关注平台的演进。面对规范演进缓慢的现状，近年来出现了两项重要的倡议；一方面是 Microprofile（[`microprofile.io`](http://microprofile.io)），另一方面是 Java EE Guardian（[`javaee-guardians.io/`](https://javaee-guardians.io/)）。

Microprofile 带来了一种创新的标准化路径，基于大型公司的共识产生新的 API，这些公司旨在优化 Java 业务应用程序以支持微服务。2017 年，Reza Rahman 和 James Gosling 博士创建了由爱好者组成的 Java EE Guardian，以实现一个一个更开放、更敏捷的过程来实施 Java EE 平台的新进展。

这些努力导致 Oracle 放弃了对 Java EE 平台的控制权，将其交给了 Eclipse 基金会。被称为 Jakarta EE（[`jakarta.ee`](https://jakarta.ee)），其目的是专注于社区的积极参与，以更快地取得进展并适应变化的市场需求。

在本书中，我们将开发一系列示例，因此我们规定了一些你必须在计算机上安装的要求。

我们假设读者已经具有 Java 知识以及安装开发工具的流程。

我们将从简要描述一些 JSR 开始，并带有代码段，帮助你理解这些 API。如果你已经具有 Java EE 平台的经验，你会发现它们是非常基础的示例和概念，因为它们针对的是想要了解并使用 Java EE/Jakarta EE 平台进行开发的新开发者。

你将看到许多规范的定义，以引导读者了解通过 JSR 建立的规则。

最重要的是让我们提到根据用法分组的一些 API：Web 应用程序、企业级应用程序、Web 服务和安全管理、微服务应用程序。

下表显示了 Web 应用程序技术的 API：

| APIs | JSR |
| :--- | :--- |
| Java API for WebSocket 1.1 | JSR 356 |
| Java API for JSON Binding 1.0 | JSR 367 |
| Java API for JSON Processing 1.1 | JSR 374 |
| Java Servlet 4.0 | JSR 369 |
| JavaServer Faces 2.3 | JSR 372 |
| Expression Language 3.0 | JSR 341 |
| JavaServer Pages 2.3 | JSR 245 |
| Standard Tag Library for JavaServer Pages (JSTL) 1.2 | JSR 52 |

**表 1.2**

下表显示了企业级应用程序技术的 API 栈：

| APIs | JSR |
| :--- | :--- |
| Batch Applications for the Java Platform 1.0 | JSR 352 |
| Concurrency Utilities for Java EE 1.0 | JSR 236 |
| Contexts and Dependency Injection for Java 2 | JSR 330 |
| Dependency Injection 1.0 | JSR 335 |
| Bean Validation 2.0 | JSR 380 |
| Enterprise JavaBeans 3.2 | JSR 318 |
| Interceptors 1.2 | JSR 348 |
| Java Connector Architecture 1.7 | JSR 365 |
| Java Persistence 2.2 | JSR 335 |
| Common Annotations 1.3 | JSR 250 |
| Java Message Service 2.0 | JSR 343 |
| Java Transaction API (JTA) 1.2 | JSR 67 |
| JavaMail 1.6 | JSR 97 |

**表 1.3**

下表显示了 Web 服务的 API：



| APIs | JSR |
| :--- | :--- |
| Java API for RESTful Web Services 2.1 | JSR 370 |
| Web Services 1.3 | JSR 109 |
| Java Architecture for XML 2.1 | JSR 181 |
| Java API for XML-Based RPC (JAX-RPC) 1.1 | JSR 101 |
| Java API for XML Registries (JAXR) 1.0 | JSR 93 |

**表 1.4**

下表显示了管理和安全的 API：

| APIs | JSR |
| :--- | :--- |
| Java EE Security 1.0 | JSR 375 |
| Java Authentication Service for Containers 1.1 | JSR 196 |
| Java Authorization Contract for Containers 1.5 | JSR 115 |
| Java EE Deployment 1.2 | JSR 88 |
| Java EE Management 1.1 | JSR 77 |

**表 1.5**

下表显示了 Java SE 中 Java EE API：

| APIs | JSR |
| :--- | :--- |
| Java Management Extensions (JMX) 2.0 | JSR 3 |
| SOAP with Attachments API (SAAJ) 1.3 | JSR 67 |
| Streaming API for XML (StAX) 1.0 | JSR 173 |
| Java API for XML Processing (JAXP) 1.6 | JSR 206 |
| Java Database Connectivity 4.0 | JSR 221 |
| Java Architecture for XML Binding (JAXB) 2.2 | JSR 222 |
| Java API for XML-Based Web Services (JAX-WS) 2.2 | JSR 224 |
| JavaBeans Activation Framework (JAF) 1.1 | JSR 92 |

**表 1.6**

# Java EE/Jakarta EE 应用程序开发

在此部分，我们将展示如何开发基于 Jakarta EE 的应用程序。以下是我们为开发示例定义的要求列表：

- Java 开发工具包 (JDK)
  - JDK 8 或更高版本
- 构建工具
  - Maven 或 Gradle
- 集成开发环境 (IDE)
  - Apache NetBeans
    - Payara Micro 插件
  - Eclipse
  - IntelliJ IDEA
- NoSQL 数据库
  - MongoDB
- 应用服务器
  - Payara 或任何 Jakarta EE 应用服务器
- Docker

源代码可以通过以下链接获取：

[`github.com/avbravo/Building-JakartaEE-Applications-Microservices`](https://github.com/avbravo/Building-JakartaEE-Applications-Microservices)

要创建一个支持 Jakarta EE 8 规范的 Web 项目，你只需要包含以下 Maven 项目依赖：

```xml
<dependency>
    <groupId>jakarta.platform</groupId>
    <artifactId>jakarta.jakartaee-api</artifactId>
    <version>8.0.0</version>
</dependency>
```

Jakarta EE 应用程序运行在容器中，容器为 Jakarta EE 平台的组件和 API 提供运行环境。

Java EE 定义了四种主要的容器类型：

- **应用客户端容器**：通常是运行在桌面上的应用程序，具有用户界面并使用平台组件。
- **Applet 容器**：管理 applet 的执行。
- **Web 容器**：`Servlet`、`JSP`、`Java Server Faces` 是使用 HTTP 协议在 Web 容器中运行的应用程序。
- **EJB 容器**：管理企业 Java Beans（Enterprise Java Beans）的执行，运行在 Java EE 服务器内部。

# 上下文与依赖注入 CDI 2.0 (JSR 365)

上下文与依赖注入 (CDI) 从 Java EE 6 开始引入。规范将其定义为一组服务，允许对象与上下文生命周期挂钩、被注入，并与拦截器（Interceptor）和装饰器（Decorator）关联。

它允许与事件交互，提供了与企业 Java Beans 组件、Java Server Faces Managed Beans、Bean Validation（Bean Validation）的集成，并支持异步事件。

依赖注入可以在以下级别执行：

- 属性
- 构造函数
- 方法

允许的作用范围有：

- `RequestScoped`
- `SessionScoped`
- `ApplicationScoped`
- `ConversationScoped`
- `DependentScoped`

规范定义了一些注解，如下表所示：

| 注解 | 说明 |
| :--- | :--- |
| `@Named` | 它是标准限定符，允许我们通过注入其他 bean 的依赖以及使用表达式语言来定义被使用的 bean。 |
| `@Model` | 它帮助定义一个构型，用于识别特定的 bean，该 bean 通常定义 MVC 模型中的层。 |
| `@Inject` | 允许声明 bean 的字段、方法和构造函数以便被注入。 |
| `@Producer` | 生产方法作为被注入对象的源。这些对象不需要实例化，可能在运行时变化，且不能在 bean 的构造函数中初始化。 |
| `@Qualifier` | 通过 `@Qualifier` 注解，我们创建限定符来帮助我们识别一个类或一组其他类的类。其提供的优势之一是我们的代码更具可读性。 |
| `@Interceptor` | 允许应用横切关注点，这些点可以在运行时启用或禁用。它们拦截对方法的调用，我们可以在调用方法之前或之后指定对其他方法的调用。 |
| `@Decorator` | 它们仅应用于特定 Java 接口中的 bean，并且与拦截器非常相似。 |
| `@Delegate` | 标识使用装饰器将方法调用委托给容器的委托者。 |

**表 1.7**

`@Model` 注解帮助我们定义一个可以与其他组件使用的模型：

```java
@Model
public class Dog {
    private Integer id;
    private String name;
    // Setters/Getters
}
```

定义 `@Qualifier` `Domestic`：

```java
@Qualifier
@Retention(RUNTIME)
@Target({METHOD, FIELD, PARAMETER, TYPE})
public @interface Domestic {
}
```

`@Qualifier` 可以应用于类定义级或属性定义级：

```java
@Domestic
public class AnimalProcessor {
}
```

或通过依赖注入：

```java
public class AnimalController {
    @Inject
    @Domestic
    AnimalProcessor animalProcessor;
}
```

要从 bean 中声明一个 Bean，我们使用注解 `@SessionScoped`：

```java
@Named
@SessionScoped
public class MySession implements Serializable {
    private Dog dog;
    // Setters/Getters
}
```

CDI 允许通过表达式语言 (EL) 与 Java Server Faces 组件轻松集成：

```xml
<h:form>
    <h:outputLabel value="Id"/>
    <h:inputText value="#{mySession.dog.id}"/>
</h:form>
```

# `@Interceptor`——拦截器示例

我们将开发一个拦截器示例。当通过拦截器执行 `start()` 方法时，将调用 `ExerciseInterceptor` 中定义的 `authorize()` 方法，然后将控制权返回给 `start()` 方法。

![](img/68-1.jpg)

**图 1.1**

在项目中使用拦截器的步骤如下：

1. 首先，我们将按照所示定义 `Model`：

   ```java
   @Model
   public class Person {
       private Integer id;
       private String name;
       private Boolean walk;

       public Person() {
       }

       // Setter/Getter
   }
   ```

2. 接下来，我们将定义用于配合拦截器的 `Feed` 接口：

   ```java
   @Inherited
   @InterceptorBinding
   @Target({TYPE, METHOD})
   @Retention(RUNTIME)
   public @interface Exercise {
   }
   ```

3. 我们声明 `FeedInterceptor` 来拦截使用 `@Exercise` 注解的方法事件：

   ```java
   @Exercise
   @Interceptor
   public class ExerciseInterceptor {
       @Inject
       Person person;

       @AroundInvoke
       public Object authorize(InvocationContext ic) throws Exception {
           try {
               if (!person.getWalk()) {
                   return ic.proceed();
               } else {
                   throw new Exception();
               }
           } catch (Exception e) {
               throw e;
           }
       }
   }
   ```

4. 在 `WEB-INF` 目录下创建 `beans.xml` 文件，并指定创建的 `Exercise` 类：

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <beans xmlns="http://xmlns.jcp.org/xml/ns/javaee"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/beans_1_1.xsd">
       <interceptors>
           <class>book.interceptor.ExerciseInterceptor</class>
       </interceptors>
   </beans>
   ```

5. 在此方法中使用 `@Exercise` 注解：

   ```java
   @Model
   public class ExerciseController implements Serializable {
       @Inject
       Person person;

       public Person getPerson() {
           return person;
       }

       public void setPerson(Person person) {
           this.person = person;
       }

       @Exercise
       public String start() {
           try {
               System.out.println("The person started");
           } catch (Exception e) {
               System.out.println("error " + e.getMessage());
           }

           return "";
       }
   }
   ```

# Enterprise Java Beans 3.2 (JSR 345)

规范将企业 Java Beans 架构 (EJB) 定义为组件的架构。

EJB 的目标是：

- 标准的组件架构。
- 组件开发和部署。
- Web 服务开发和部署。
- 方便创建应用程序。

EJB 的 Session 类型有：

- `Singleton`
- `Stateful`
- `Stateless`

组件可以简单地使用 `@EJB`：

```java
@EJB
MyResources myResources;
```

此示例实现了一个每 10 分钟发送一次通知的 `@Schedule`：

```java
@Singleton
public class SendCongratulations {
    @Schedule(minute = "*/10", hour = "*", persistent = false)
    public void send() {
        // …
    }
}
```

# `@Producer` 示例

从 NetBeans 创建 Enterprise Java Beans 项目以使用 `@Producer` 管理到 MongoDB 数据库的连接。

将：

```xml
<version>8.0</version>
<scope>provided</scope>
</dependency>
```

替换为 Jakarta EE 依赖：

```xml
<dependency>
    <groupId>jakarta.platform</groupId>
    <artifactId>jakarta.jakartaee-api</artifactId>
    <version>8.0.0</version>
    <scope>provided</scope>
</dependency>
```

添加 MongoDB Java 驱动。请记住，在接下来的章节中，将使用 `JNoSQL` 和 `Jmoordb` 与 Java 和 NoSQL 数据库进行通信：

```xml
<dependency>
    <groupId>org.mongodb</groupId>
    <artifactId>mongodb-driver</artifactId>
    <version>3.6.0</version>
</dependency>
```

在 NetBeans IDE 中，选择项目，然后在包 `com.jakartaeebook.nosqleb` 上右键点击并选择 `New | Session Bean`：

![](img/68-6.jpg)

**图 1.6**

将 EJB 名称输入为 `MyProducer`，并在 `Session Type` 中选择 `Singleton` 选项：

![](img/68-7.jpg)

**图 1.7**

IDE 生成了 `Singleton MyProducer.java`，你可以在其中添加企业组件：

```java
import javax.ejb.Singleton;

@Singleton
@LocalBean
public class MyProducer {
    // 在下方添加业务逻辑。（在编辑器中右键点击并选择
    // “Insert Code > Add Business Method”）
}
```

使用 `@Singleton` 注解来定义 bean 的单实例，这由容器控制。

`@ConcurrencyManagement` 注解将控制权交给 EJB 容器，由它控制对单例方法的访问。

可以使用注解对方法访问进行阻塞控制。通常，对于返回值的读取方法使用 `@Lock(READ)`，对于写入方法使用 `@Lock(WRITE)`，这将阻塞其他客户端对这些方法的访问。

Producer 将作为单实例为所有客户端返回数据库连接，因此只需要注入 `myConnection()` 方法。



```java
@Singleton
@ConcurrencyManagement(ConcurrencyManagementType.CONTAINER)
public class MyProducer {
    private static final Logger LOG = Logger.getLogger(MyProducer.class.getName());

    @Produces
    @ApplicationScoped
    public MongoClient myConnection() {
        MongoClient mongo = new MongoClient(“localhost”, 27017);
        try {
            mongo = new MongoClient();
        } catch (Exception e) {
            LOG.severe(e.getLocalizedMessage());
        }
        return mongo;
    }
}
```

# Java Servlet 4.0（JSR-369）

Java Servlet 规范（[`www.jcp.org/en/jsr/detail?id=369`](https://www.jcp.org/en/jsr/detail?id=369)）定义如下：

- **Servlet**：基于 Web 组件的 Java 技术，运行在容器中并生成动态内容。
- **Servlet Container**：作为应用程序服务器或 Web 服务器的一部分，通过网络服务发送请求/响应。Servlet 容器支持 HTTP、HTTPS 协议。
- **Servlet Context**：定义运行 servlet 的 Web 应用程序 Servlet 视图。
- **Request**：封装客户端请求的所有信息。
- **Response**：封装从服务器返回给客户端的信息。

Servlet 允许我们定义过滤器并管理会话。

`HttpServlet` 类定义了我们将在下表中显示的方法：

| HttpServlet | HTTP |
| :--- | :--- |
| `doGet` | GET 请求 |
| `doPost` | POST 请求 |
| `doPut` | PUT 请求 |
| `doDelete` | DELETE 请求 |
| `doHead` | HEAD 请求 |
| `doOptions` | OPTIONS 请求 |
| `doTrace` | TRACE 请求 |

**表 1.8**

使用 `@WebServlet` 注解可以很容易创建一个 servlet：

```java
@WebServlet(name = “Hello“, urlPatterns = {“/Hello“})
public class Hello extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
    }
}
```

HTTP/2 协议相比 HTTP/1 协议提供了新功能，Jakarta EE 8 支持这些功能：

- 服务器推送（Server push）
- 请求/响应复用
- 多路复流
- 请求头压缩

## 服务器推送

它是 HTTP2 中旨在提高性能最重要的改进之一。由于服务器知道客户端请求的资源并可以在被请求之前发送它们，想象页面包含 CSS、JS、图像，服务器可以开始发送。

`HttpServletRequest` 提供了 `PushBuilder`，允许我们利用 HTTP2 协议的进展从服务器向客户端 `push()` 内容。

下面我们将向你展示如何使用 NetBeans IDE 创建应用程序，你可以使用你喜欢的 IDE：

1. 接下来，将从 NetBeans IDE 开发一个 Web 项目。从菜单选择 `File | New | Project`。在 `Categories` 中选择 `Java With Maven` 选项，在 `Projects` 中选择 `Payara Micro Application` 选项：

   ![](img/68-8.jpg)

   **图 1.8**

2. 输入项目名称为 `myservlet`：

   ![](img/68-9.jpg)

   **图 1.9**

3. 在服务器上选择 `Payara Micro Version` 为 `5.191`（或选择你安装的 Java EE Server）：

   ![](img/68-10.jpg)

   **图 1.10**

   最后，生成了 Web 项目。

4. 现在我们将开始创建一个 servlet，选择包并右键点击，选择 `Categories` 为 `Web`，并在 `File Types` 中选择 `Servlet`：

   ![](img/68-11.jpg)

   **图 1.11**

5. 输入 `Class Name` 为 `Hello`：

   ![](img/68-12.jpg)

   **图 1.12**

6. 在 `Configure Servlet Deployment` 中，我们定义 `Servlet Name` 为 `Hello`，并在 `URL Patterns(s)` 中输入 `/Hello`，这是我们访问 Servlet 的路径：

   ![](img/68-13.jpg)

   **图 1.13**

生成的 servlet 将包含对应于 HTTP 协议 GET/POST 的 `doGet()`/`doPost()` 方法：

- `doGet(HttpServletRequest request, HttpServletResponse response)`
- `doPost(HttpServletRequest request, HttpServletResponse response)`
- `processRequest()` 是我们用于处理请求/响应并向客户端返回 HTML 的方法：

```java
@WebServlet(name = “Hello”, urlPatterns = {“/hello”})
public class Hello extends HttpServlet {
    protected void processRequest(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType(“text/html;charset=UTF-8”);
        try (PrintWriter out = response.getWriter()) {
            /* TODO 在此处输出你的页面。你可以使用以下示例代码。 */
            out.println("<!DOCTYPE html>”);
            out.println(“<html>”);
            out.println(“<head>”);
            out.println(“<title>Servlet Hello</title>”);
            out.println(“</head>”);
            out.println(“<body><body>”);
            out.println“<h1>Servlet Hello at “ + request.getContextPath() + “</h1>”);
            out.println(“</body>”);

out..println(“</html>””);
        }
    }

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        process(request, response);
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        process(request, response);
    }

    @Override
    public String getInfo() {
        return “Short description description”;
    }
}
```

执行项目并打开 Web 浏览器，输入地址：`http://localhost:8080/myservlet/Hello`

你可以看到 Servlet 向我们发送了回复 HTML：

![](img/68-14.jpg)

**图 1.14**

它包含一个 servlet，该 servlet 可与 `MongoDB` 数据库通信，并在 `<table>` 组件中显示人员列表及其照片。

我们将应用从 CDI、EJB 和 Servlet 中中学的概念来注入 `@Producer myConnection()`，它将为我们返回数据库的连接。文档将通过 API JSON-B 进行处理，并将它们转换为 `Person.java` 类的对象。该示例使用了名为 `book` 的 `MongoDB` 数据库和名为 `Person` 的集合。你必须创建它们并输入文档，如下所示：

```json
{
“_id” : ObjectId("5cfbe59606f2be9d8d6c667d”),
“id” : “78-96”,
“name” : “Ann”,
“photo” : “images/ann.png”
}
{
“_id” : ObjectId("5cfbe5b306f2be9d8d6c667e”),
“id” : “4-74”,
“name” : “Jhon”,
“photo” : “images/jhon.jpg”
}
```

在项目中添加依赖项 `nosqlejb`：

```xml
<dependency>
<groupId>com.book</groupId>
<artifactId>nosqlejb</artifactId>
<version>0.1</version>
</dependency>
```

示例中将使用的组件有：

- 普通对象 Java 对象：`Person.java`
- Servlet：`PersonServlet`

接下来，我们将看到下文提供的 `Person` 类：

```java
public class Person {
    private String id;
    private String name;
    private String photo;

    public Person() {}

    //Getters Setters /methods
}
```

在 servlet `PersonServlet` 中：

- 注入 `MongoClient`
- 定义一个返回数据库的方法 `getMongoDatabase()`。
- `processRequest()` 方法将文档转换为 `Person` 类。
- `PushBuilder` 利用了新的 HTTP/2 特性，并提前向客户端发送图像。

完整的代码示例可以在 GitHub 上的存储库中找到。在接下来的代码段中，我们将创建一个名为 `PersonServlet` 的 Servlet：

```java
@WebServlet(name = “PersonServlet”, urlPatterns = {“/PersonServlet”})
public class PersonServlet extends HttpServlet {
    @Inject
    MongoClient myConnection;

    public MongoDatabase getMongoDatabase() {
        try {
            MongoDatabase db = myConnection.getDatabase(“book”);
            return db;
        } catch (Exception ex) {
            Logger.getLogger(PersonServlet.class.getName()).log(Level.SEVERE, null, ex);
        }
        return null;
    }

    protected void processRequest(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        Jsonb jsonb = JsonbBuilder.create();
        PushBuilder pb = request.newPushBuilder();
        response.setContentType(“text/html;charset=UTF-8”);

        try (PrintWriter out = response.getWriter()) {
            /* TODO output your page here. You may use the following sample code. */
            out.println(“<!DOCTYPE html>”);
            out.println(“<html>”);
            out.println(“<head>”);
            out.println(“<title>ServletServlet</title>”);
            out.println(“</head>”);
            out.println(“<body>”);
            out.println(““<h1>List of People</h1>”);
            out.println(“<table style=\"width:100%”>”);
            out.println(“<tr>”);
            out.println(“<th>id</th>”);
            out.println(“<th>name</th>”);
            out.println(“</tr>”);

            for (Document doc : getMongoDatabase().getCollection(“person”).find()) {
                Person person = jsonb.fromJson(doc.toJson(), Person.class);
                out.println(“<tr>”);
                out.println(“<td>” + person.getId() + “</td>”);
                out.println(“<td>” + person.getName() + “</td>”);

                if (pb != null) {
                    pb.path(person.getPhoto())
                        .addHeader(“content-type”, person.getPhoto())
                        .push();
                }

                out.println(“<td><img src=’” + person.getPhoto() + “’></td>”);
                out.println(“</tr>”);
            }

            out.println(“</table>”);
            out.println(“</body>”);
            out.println(“</html>”);
        }
    }

    …
}
```

当我们执行项目时，我们注意到 `Servlet` 连接到数据库并返回人员及其各自照片列表。

`http://localhost:8080/PersonServlet`

# Java API for RESTful Web Services JAX-RS 2.1（JSR-370）

这是一个用于使用表述状态传输（REST）创建 Web 服务的 API。它的主要组件是：

- 资源（Resources）
- 供应商（Suppliers）
- 配置（Configuration）：通过 application 子类来加载资源和供应商。



一些需要记住的重要定义如下：

- `Client` API：用于访问 Web 资源。

  ```java
  Client client = ClientBuilder.newClient();
  Response response = client.target("http://localhost:8080/person").request("text/plain").get();
  ```

- `WebTarget`：用于构建 URL。

  ```java
  WebTarget target = client.target("http://localhost:8080/person");
  ```

- `Invocations`：用于调用。

  ```java
  Response response = client.target("http://localhost:8080/person").request("text/plain").get();
  ```

- `Reactive Clients`：支持异步编程。

  ```java
  CompletionStage<String> stage = client.target("http://localhost:8080/person").request("text/plain").get();
  ```

- `RxJava`：用于响应式编程。

  ```java
  Flowable<String> flowable = client.target("http://localhost:8080/person").request("text/plain").get();
  ```

- `Interceptor`：支持拦截器。

  ```java
  Observable<String> observable = client.target("http://localhost:8080/person").request("text/plain").get();
  ```

- `Filter`：用于过滤器。

  ```java
  Single<String> single = client.target("http://localhost:8080/person").request("text/plain").get();
  ```

- `Validation`：用于验证。
- `Entity`：实体。
- `Repository`：存储库。
- `Application`：应用。
- `Services`：服务。

在接下来的示例中，我们将创建一个名为 `myjaxrs` 的项目，如下所示。

`Person` 类包含以下属性：

```java
public class Person {
    private String id;
    private String name;
    private String photo;

    public Person() {
    }

    // Getters Setters
}
```

`Repository` 类模拟了与 NoSQL 数据库的交互：

```java
@Stateless
public class PersonRepository {
    List<Person> personList = new ArrayList<>();

    public PersonRepository() {
        //Old method
        personList.add(new Person("78-10"Marie"));
        personList.add(new Person("426-3"Stephanie"));
    }

    public List<Person> findAll() {
        return personList;
    }

    public Person findById(String id) {
        Person person = personList.stream()
            .filter(p -> id.equals(p.getId()))
            .findAny()
            .orElse(null);

        return person;
    }
}
```

## 创建应用资源

创建继承自 `Application` 的类，这里是应用资源：

```java
import java.util.Set;
import javax.ws.rs.core.Application;

@javax.ws.rs.ApplicationPath("rest")
public class ApplicationConfig extends Application {
    @Override
    public Set<Class<?>> getClasses() {
        Set<Class<?>> resources = new java.util.HashSet<>();
        resources.add(com.book.myjaxrs.PersonService.class);
        return resources;
    }
}
```

`find()` 方法用于通过 id 查找人员，`findAll()` 方法返回所有人员列表。

要将 `PersonServices` 类转换为 Web 服务，在类级别上添加 `@Path` 注解，并在方法级别也实现它。

`@GET` 注解用于 HTTP 协议的获取方法。通过 `@Produces` 我们指示发送结果的 `MediaType`。`PathParam` 用于设置方法接收的参数名称和类型。

在这种情况下，可以从客户端（Web 浏览器）访问 REST 端点，并可以通过调用 `findAll()` 方法来消费服务。

`http://localhost:8080/myjaxrs/rest/personServices/`

![](img/68-17.jpg)

图 1.17

要通过调用 `find` 方法执行查询，只需 URL 中传递参数即可：

`http://localhost:8080/myjaxrs/rest/personService/426-3`

系统将返回由 `id` 指定的个人信息。

`{"id":"426-3","name":"Stephanie"}`

# Java EE Security API 1.0（JSR-375）

安全性是当今业务应用程序中最重要的方面之一。通过引入 JSR-375，Java EE 平台提供了身份验证机制，以确保 Web 资源的安全性。

规范定义了一些术语：

- **身份验证机制（Authentication mechanism）：** 一种由 `Caller` 调用以获取凭据并将其与 `Identity Store`（身份库）中的现有凭据进行比较的身份验证机制。
- **调用者（Caller）、主调用者（Main Caller）：** 通过其凭据向应用程序发送请求的用户。
- **HAM：** `HttpAuthenticationMechanism` 的缩写。
- **身份库（Identity Store）：** 一个指定如何通过凭据、组、角色和权限访问应用程序的组件。
- **JACC：** JSR-115，“容器 Java 授权合约”（Java Authorization Contract for Containers）。
- **JASPIC：** JSR-196，“容器 Java 身份认证 SPI”（Java Authentication SPI for Containers）。

`HttpAuthenticationMechanism` 定义了我们可以使用的三个方法，如下所示：

- `ValidateRequest()`：在某些 Servlet 或服务的 `doFilter()` 方法之前被调用。
- `SecureResponse()`：在某些 Servlet 或服务的 `doFilter()` 方法之后被调用。
- `CleanSubject()`：调用 `HttpServletRequest logout()` 方法时被调用。

将针对 MongoDB 数据库创建一个身份验证示例，该数据库存储用户及其凭据，并使用 Java Server Faces 创建用户界面。

打开位于 `WEB-INF` 文件夹下的 `web.xml` 文件，并在 `web.xml` 文件中定义角色：

```xml
<security-constraint>
  <web-resource-collection>
    <web-resource-name>Application pages</web-resource-name>
    <url-pattern>/faces/pages/*</url-pattern>
  </web-resource-collection>
  <auth-constraint>
    <role-name>ADMIN</role-name>
    <role-name>TESTING</role-name>
  </auth-constraint>
</security-constraint>
<security-role>
  <role-name>ADMIN</role-name>
</security-role>
<security-role>
  <role-name>TESTING</role-name>
</security-role>
```

在验证用户登录的类方法中，实现凭据验证：

```java
public String login() {
  try {
    Credential credential = new UsernamePasswordCredential(
        username,
        new Password(password)
    );

    AuthenticationStatus status = securityContext.authenticate(
        (HttpServletRequest) externalContext.getRequest(),
        (HttpServletResponse) externalContext.getResponse(),
        withParams().credential(credential)
    );

    switch (status) {
      case SEND_CONTINUE:
        facesContext.responseComplete();
        break;
      case SEND_FAILURE:
        facesContext.addMessage(
            null,
            new FacesMessage(
                FacesMessage.SEVERITY_ERROR,
                "Login failed",
                null
            )
        );
        break;
      case SUCCESS:
        facesContext.addMessage(
            null,
            new FacesMessage(
                FacesMessage.SEVERITY_INFO,
                "Welcome",
                null
            )
        );
        return "/faces/pages/index.xhtml?faces-redirect=true";
      case NOT_DONE:
    }
  } catch (Exception e) {
    JsfUtil.errorMessage(e.getLocalizedMessage());
  }

  return "";
}
```

# Identity Store

创建一个实现 `IdentityStore` 的类来验证凭据：

```java
public class MyIdentityStore implements IdentityStore {
  @Override
  public CredentialValidationResult validate(Credential credential) {
    if (!valid(
        usernamePassword.getCaller(),
        usernamePassword.getPasswordAsString()
    )) {
      return CredentialValidationResult.NOT_VALIDATED_RESULT;
    }

    return new CredentialValidationResult(
        "mygroup",
        new HashSet<>(Arrays.asList("mygroup"))
    );
  }
}
```

在 JavaServer Faces 页面级，我们可以使用通过 CDI 集成到 EL 中的 `ifGranted()` 等方法建立限制：

```xml
<h:form id="form" prependId="false" rendered="#{p:ifGranted('ADMIN')}">
```

约束可以在类级或方法级实现：

```java
@ServletSecurity(@HttpConstraint(rolesAllowed = "myrol"))
```

# Java API for JSON Binding JSON-B 1.0（JSR-367）

规范定义 JSON-B 为一种 API，提供了 JSON 文档序列化和反序列化的机制，这些文档可以映射到 Java 类，反之亦然。

该 API 支持基础 Java 类型：

- Integer（整数）
- String（字符串）
- Byte（字节）
- Short（短整型）
- Date（日期）
- Long（长型）
- Float（浮点型）
- Double（双精度浮点型）
- Character（字符）

JSON-B 还支持：

- Collections（集合）
- Generic（泛型）

**JSON（JavaScript 对象表示）** 是一种数据交换格式。JSON 文档由 `key:value` 对组成。它是大多数面向文档的 NoSQL 数据库最使用的格式。

一个 JSON 文档示例：

```json
{
  "id": "785-2",
  "name": "Dog"
}
```

JSON-B 提供了一个 `JsonBuilder` 构造函数，其中包含 `Jsonb` 类，具有 `toJson()` 和 `fromJson()` 方法，用于将 Java 对象序列化为 JSON 文档反之亦然。

使用 `JsonConfig` 可以对文档输出进行格式化。

规范定义了一系列注解，我们将在下表中展示：

| 注解 | 描述 |
| :--- | :--- |
| `@JsonbProperty` | 修改属性名称。在字段级有效，并设置序列化（serialization）和获取（get serialization）方法。 |
| `@JsonbTransient` | 允许你通过 JSON 引擎忽略某个属性。 |
| `@JsonbDateFormat` | 允许你格式化日期。 |
| `@JsonbNumberFormat` | 数字格式化。 |

表 1.9

使用 JSON-B 序列化和反序列化 JSON 文档及 Java 类的简单示例：

```java
public class Animal {
  private String id;

  @JsonbProperty("nameofanimal")
  private String name;

  //Getters/Setters methods
}

Animal animal = new Animal("785-2", "Dog");
```

使用 `toJson()` 方法将 Java 转换为 JSON：

```java
Jsonb jsonb = JsonBuilder.create();
String jsonString = jsonb.toJson(animal);
```

现在使用 `fromJson()` 方法将 JSON 转换为 Java 类：

```java
Animal animal2 = jsonb.fromJson(jsonString, Animal.class);
```

如果我们想对输出应用格式：

```java
JsonbConfig myconfig = new JsonbConfig();
Jsonb jsonb = JsonbBuilder.create(myconfig);
```

# JavaServer Faces 2.3

**Java Server Faces (JSF)** 是一个用于为 Java 应用程序创建用户界面的框架。它基于模型-视图-控制器（MVC）。它是面向组件的。

主要功能包括：

- 包含大量组件
- 允许以简单的方式扩展这些组件
- 提供请求/响应生命周期管理
- 支持表达式语言（EL）中的 CDI 注入
- 支持 HTML5
- 通过 `<f:websocket>` 支持 WebSocket
- 通过 `<f:validateWholeBean>` 进行验证
- 组件搜索框架
- `<f:converterTime>` 支持 Java 8 时间

参考实现有 Eclipse Mojarra、Oracle Mojarra 和 Apache MyFaces。

常用的框架有：

- Primefaces
- Bootsfaces
- Omnifaces

组件可以轻松集成到 `xhtml` 页面中，并且可以通过 CDI 注入到 EL。

在示例中，我们展示了使用 Java Server Faces、Primefaces 和 Bootsfaces 创建的包含面板、标签、表格和按钮的表单：



```xml
<h:form id="form" prependId="false">
  <b:growl id="growl"/>
  <b:panel title="Country" id="content" look="primary">
    <b:panelGrid colSpans="1,4,1,6" columns="4" size="xs">
      <p:outputLabel value="id"/>
      <p:inputText value="#{countryController.country.id}" required="true"/>
      <p:outputLabel value="name"/>
      <p:inputText value="#{countryController.country.name}" rendered="true"/>
    </b:panelGrid>
  </b:panel>
</h:form>
```

```xml
<p:commandButton value="Save" action="#{countryController.save()}" update="::form"/>
```

```xml
</b:panelGrid>
```

```xml
</b:panel>
```

```xml
<p:dataTable value="#{countryController.listCountry}" id="dat var" var="country">
  <p:column headerText="id">
    <p::Label value...idid
  </p:column>
  <p:column headerText="name">
    <p:outputLabelLabel="#.country.namename
  </p:column>
</:
```

```xml
<h:form>
```

在执行应用程序时，这些内容会被渲染为 HTML，由 Web 浏览器进行解释：

![](img/68-18.jpg)

**图 1.18**

对于我们使用的示例，使用了：

- 实体（Entity）
- 存储库（Repository）
- 控制器（Controller）

使用你喜欢的编辑器并按照下文说明创建类：

1. 让我们使用以下代码创建一个名为 `Country` 的实体：

```java
public class Country {

    private String id;

    private String name;

    public Country() {}

    //Setters/Getters

}
```

2. 现在，我们将创建一个存储库的类来管理 MongoDB 数据库中的集合：

```java
@Stateless
public class CountryRepository {

    Jsonb jsonb = JsonbBuilder.create();

    @Inject
    MongoClient myConnection;

    public MongoDatabase getMongoDatabase() {
        try {
            MongoDatabase db = myConnection.getDatabase("book");
            return db;
        } catch (Exception e) {
            JsfUtil.error(e.getLocalizedMessage());
        }

        return null;
    }

    public List<Country> findAll() {
        List<Country> countryList = new ArrayList<>();

        try {
            for (Document doc : getMongoDatabase().getCollection("user").find()) {
                Country country = jsonb.fromJson(doc.toJson(), Country.class);
                countryList.add(country);
            }
        } catch (Exception e) {
            JsfUtil.error(e.getLocalizedMessage());
        }

        return countryList;
    }

    public Boolean save(Country country) {
        try {
            getMongoDatabase()
                .getCollection("user")
                .insertOne(Document.parse(jsonb.toJson(country)));

            return true;
        } catch (Exception e) {
            JsfUtil.error(e.getLocalizedMessage());
        }

        return false;
    }
}
```

3. 你需要一个带有 `@Named` 和 `@ViewScoped` 注解的控制器：

```java
@Named
@ViewScoped
public class CountryController implements Serializable {

    @Inject
    CountryRepository countryRepository;

    Country country = new Country();

    List<Country> listCountry = new ArrayList<>();

    public Country getCountry() {
        return country;
    }

    public void setCountry(Country country) {
        this.country = country;
    }

    public List<Country> getListCountry() {
        return countryRepository.findAll();
    }

    public void setListCountry(List<Country> listCountry) {
        this.listCountry = listCountry;
    }

    @PostConstruct
    public void init() {}

    public String save() {
        countryRepository.save(country);
        return "";
    }
}
```

# WebSocket

Java Server Faces 2.3 支持通过 `<f:websocket>` 与 WebSocket 集成。它在客户端注册一个来自服务器的推送连接。它对于聊天客户端、向客户端发送通知非常有用。

它的使用相对简单，我们将描述这些步骤：

1. 让我们在 `pom.xml` 文件添加 `javax.websocket-api` 依赖：

```xml
<dependency>
    <groupId>javax.websocket</groupId>
    <artifactId>javax.websocket-api</artifactId>
    <version>1.1</version>
    <scope>provided</scope>
</dependency>
```

2. 通过启用 `ENABLE_CDI_RESOLVER_CHAIN` 和 `ENABLE_WEBSOCKET_ENDPOINT` 来配置 `web.xml` 文件：

```xml
<context-param>
    <param-name>javax.faces.ENABLE_CDI_RESOLVER_CHAIN</param-name>
    <param-value>true</param-value>
</context-param>

<context-param>
    <param-name>javax.faces.ENABLE_WEBSOCKET_ENDPOINT</param-name>
    <param-value>true</param-value>
</context-param>
```

3. 现在，注入 `@Push(channel = "notification")` 来注册 WebSocket：

```java
@Named
@ApplicationScoped
public class MySocket implements Serializable {

    Integer count = 0;

    @Inject
    @Push(channel = "notification")
    private PushContext push;

    public Integer getCount() {
        return count;
    }

    public void setCount(Integer count) {
        this.count = count;
    }

    public void pushAction() {
        try {
            count++;
            push.send(count);
        } catch (Exception e) {
            JsfUtil.error(e.getLocalizedMessage());
        }
    }
}
```

4. 在页面中添加以下行：

```xml
<f:websocket channel="notification" onmessage="webSocketListener" />
```

当调用 JavaScript 函数时，会触发 WebSocket 事件：

```javascript
<script type="text/javascript">
function webSocketListener(message, channel, event) {
    document.getElementById("label").innerHTML += message + "<br/>";
}
</script>
```

5. 使用 `<h:commandButton>` 配合 `<f:ajax>` 来发送消息：

```xml
<h:commandButton value="Socket" action="#{mySocket.pushAction()}">
    <f:ajax />
</h:commandButton>
```

6. 从服务器获取的 HTML 组件：

```xml
<div id="label"></div>
```

Java Faces 界面将如所示通过 WebSocket 更新：

![](img/68-19.jpg)

**图 1.19**

要与 Java Faces 组件使用，可以通过运行 `<p:remoteCommand>` 来实现：

```javascript
<script type="text/javascript">
function webSocketListener(message, channel, event) {
    remoteCommand();
}
</script>
```

```xml
<p:remoteCommand
    name="remoteCommand"
    update=":growl"
    actionListener="#{mySocket.actionWebSocket()}"
    process="@all">
</p:remoteCommand>
```

添加一个 `growl` 来显示通知，它会在一段时间后消失：

```xml
<p:growl id="growl" globalOnly="true" life="5000" showDetail="true" />
```

在类中向 `p:growl` 发送：

```java
public String actionWebSocket() {
    JsfUtil.warningMessage("you have a notification");
    return "";
}
```

当从 WebSocket 接收到推送通知时，它将显示 `growl`，提示用户有新通知，如下：

![](img/68-20.jpg)

**图 1.20**

# Java Persistence API 2.2（JSR-338）

大多数应用程序使用数据库来存储信息。当我们开发 Java 应用程序时，通常需要对象关系映射（ORM）或使用 JDBC API，它是 Java 与数据库管理系统通信的接口。

在 Java 平台上，有一个用于数据持久化的标准，称为 Java Persistence API。

该规范定义了 Java Persistence API 架构，包含：

- `EntityManagerFactory`：用于应用程序创建应用程序管理的实体管理器的接口。
- `EntityManager`：创建并销毁应用程序管理的持久上下文。通过注入或 JNDI 获取。
- `Entity`：轻量级持久化领域对象。
- `EntityTransaction`：用于控制资源本地实体管理器事务的接口。
- `Persistence`：获取 `EntityManagerFactory` 实例。
- `Query`：与厂商 DBMS 交互的接口。

JPA 2.2 新版本支持：

- 重复注解
- 在属性转换器中注入
- 支持 Java 8 日期时间 API
- 作为 Stream 的 `Query` 和 `TypeQuery`

## JPA 提供的一些注解

- `@Entity`：将一个类定义为实体。
- `@Id`：标识主键。
- `@GeneratedValue(strategy = GenerationType.IDENTITY)`
- `@NamedQuery()`：这些是定义在实体中的静态查询。
- `@Table`：用于指定表名。
- `@PersistenceContext`：管理持久化上下文。
- `@Embeddable`：复合键。
- `@OneToOne`：一对一关系。
- `@ManyToOne`：多对一关系。
- `@ManyToMany`：多对多关系。

实体是一个 POJO，我们为其添加了一系列的注解：

```java
@Entity
@NamedQuery(name = "Products.findAll", query = "SELECT p FROM Products p")
@NamedQuery(
    name = "Products.findByProductID",
    query = "SELECT p FROM Products p WHERE p.productID = :productID"
)
public class Product implements Serializable {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Integer productID;

    private String productCode;

    private String name;

    public Products() {}
}
```

让我们使用 `Facade or Repository` 模式来与数据库操作交互：

```java
@Stateless
public class ProductsFacade extends AbstractFacade<Products> {

    @PersistenceContext(unitName = "com.book_myjpa_war_0.1PU")
    private EntityManager em;

    @Override
    protected EntityManager getEntityManager() {
        return em;
    }

    public ProductsFacade() {
        super(Products.class);
    }
}
```

在控制器中注入 `Facade` 或 `Repository` 并创建执行 CRUD 操作的方法：

```java
@EJB
ProductsFacade productFacade;

Product product = new Product();

public void save() {
    productFacade.persist(product);
}

public void update() {
    productFacade.merge(product);
}

public void delete() {
    productFacade.remove(product);
}
```



## 结论

本章介绍了 Java EE 平台并描述了一些最重要的规范。这是对 Jakarta EE、Java Servlet、CDI 和 JSF 的非常基础的介绍。JSON-B 是为了了解平台的结构以及它为现代业务应用程序开发提供的优势。

在下一章中，我们将学习 NoSQL 数据库及其它们对于创建下一代应用程序的重要性。

## 问题

1. 为什么要迁移到 Jakarta EE？
2. 在 JavaEE/Jakarta 中实现 WebSocket 的最佳方法是什么？
3. 什么是 CDI？
4. Java Servlet API 4.0 的新特性有哪些？
5. 列举构建在 Java Server Faces 规范上的框架。

# 第 2 章 NoSQL

NoSQL 数据库是一种提供数据存储和检索机制的数据库，其建模是通过关系型数据库中使用的表格关系以外的方法实现的。这些数据库具有高速度和高扩展性。这种类型的数据库在许多应用程序（包括金融应用）中变得越来越流行。随着数量的，用户和供应商的数量也在增加。在简要介绍了 Jakarta/Java 技术后，本章将讨论这种存储信息的新方法——NoSQL 技术；它包含了一些有助于本书读者的术语。

## 结构

* NoSQL
* 键值对 (Key-value)
* 列族 (Column-family)
* 文档 (Document)
* 图谱 (Graph)
* 多模型 (Multi-model)
* 可扩展性与复杂性
* BASE 对比 ACID
* CAP

## 目标

本章将讨论 NoSQL 数据库、NoSQL 类型以及使用每种数据库的最佳实践。

## NoSQL 类型

大约有二百五十个 NoSQL 数据库供应商，每种都有特定的行为和特征。为了更容易理解这种多样化的持久化技术，NoSQL 数据库根据 NoSQL 存储结构进行了分组：

## 键值对 (Key-value)

以下是键值结构的图示：

![](img/key-value.jpg)

**图 2.1**

该数据库的结构类似于`java.util.Map` API，我们可以根据键存储任何值。例如：

* Amazon Dynamo
* Amazon S3 
* Redis
* Scalaris
* Voldemort

将开发者已有的知识与新知识进行比较是自然的；因此，本章将每种新的 NoSQL 结构与标准的关系型技术进行比较。当开发者将键值存储与关系型数据库比较时，他们发现键值存储比关系型的更平滑。在键值存储中，无法在桶（buckets）之间执行连接操作。

此外，整个信息存储在一个二进制对象（blob）中，而不是像关系型结构那样存储列中的一小部分。

| 关系型结构 | 键值结构 |
| :--- | :--- |
| 表 | 桶 (Bucket) |
| 行 | 键/值对 |
| 列 | ---- |
| 关系 | ---- |

**表 2.1**

## 列族 (Column family)

以下是列族的图示：

![](img/column.jpg)

**图 2.2**

该模型随着 Google 的 Bigtable 论文而流行起来，是一个具有高扩展性的分布式系统。与键值结构相比，其独特之处在于“值”，列操作具有很大的数据量。例如：

* HBase
* Cassandra
* Scylla
* Cloud Data
* SimpleDB

当开发者将列族与关系型数据库比较时，它比关系型的更平滑。在键值存储中，无法在桶之间执行连接操作。此外。

| 关系型结构 | 键值结构 |
| :--- | :--- |
| 表 | 桶 (Bucket) |
| 行 | 键/值对 |
| 列 | ---- |
| 关系 | ---- |

**表 2.1**

## 文档集合 (Document collection)

以下代码代表文档结构：

```json
{
  "name":"Diana",
  "duty": [
    "Hunt",
    "Moon",
    "Nature"
  ],
  "age":1000,
  "siblings": {
    "Apollo":"brother"
  }
}
```

文档 NoSQL 数据库结构类似于 JSON 或 XML 文件。它们拥有大量的字段，并且通常在运行时创建。这种无模式（schema-less）的方法允许开发者持久化任何他们想要的数据库。例如：

* Amazon SimpleDB
* Apache CouchDB
* MongoDB

| 关系型结构 | 文档结构 |
| :--- | :--- |
| 表 | 集合 (Collection) |
| 行 | 文档 (Document) |
| 列 | 键/值对 |
| 关系 | ---- |

**表 2.3**

## 图谱 (Graph)

以下是图谱数据库结构的图示：

![](img/graph.jpg)

**图 2.3**

图谱数据库通过连接工作；这种关系比关系型数据库更深层。图谱数据库通过边（edges）结构连接多个顶点。这种数据库在社交媒体中变得流行，用于制作推荐系统。图谱有三个组成部分：

* **属性 (Property)**：结构中的一个小型组件；一个元组，其中键是名称，值是信息本身。
* **顶点 (Vertex)**：看起来像 SQL 技术中具有无限数量属性的表。
* **边 (Edge)**：表示顶点之间关系的元素；它与 SQL 中的关系有相似之处。然而，边具有属性——因此它是比关系更深层的连接。

以下截图了两个相关的图：

![](img/graph_deep.jpg)

**图 2.4**

图的方向是图结构中另一个非常重要的概念，即你可以认识某个人，尽管这个人并不认识你。例如：

* Neo4j
* InfoGrid
* Sones
* HyperGraphDB

## 可扩展性与复杂性

每种特定的持久化结构都能解决特定的问题。如下方的图所示，模型复杂度之间存在平衡；越复杂的模型扩展性越低。例如，键值型 NoSQL 数据库的可扩展性更高，但一旦所有查询和操作都基于键，它的复杂度就会变得简单。

## BASE 对比 ACID

在关系型持久化技术中，使用`ACID`，它是原子性（Atomicity）、一致性（Consistency）、隔离性（Isolation）和持久性（Durability）的缩写。

* **原子性 (Atomicity)**：事务中的所有操作要么全部完成，要么都不执行。
* **一致性 (Consistency)**：数据库在事务开始和结束时将处于一致状态。
* **隔离性 (Isolation)**：事务的行为将就像它是在数据库上执行的唯一操作一样。
* **持久性 (Durability)**：事务完成后，操作将不会撤销。

在 NoSQL 世界中，他们通常关注`BASE`。与`ACID`一，`BASE`是一个缩写。

* **基本可用性 (Basic availability)**：数据库在大部分时间内看起来运行正常。
* **软状态 (Soft-state)**：存储不需要保持写入一致性，不同的副本之间也不需要时刻保持一致。
* **最终一致性 (Eventual consistency)**：存储在未来的某个时间点表现出一致性（例如，在读取时延迟地保证）。

## CAP 定理

没有灵丹妙药；`CAP`可以根据三种行为来解释它。下面的图说明了这一点：

![](img/cap.jpg)

**图 2.5**

`CAP`定理适用于存储状态分布式系统。Eric Brewer 在 2000 年的`分布式计算原理研讨会 (PODC)`上预测，在任何网络共享数据系统中，一致性、可用性和分区性之间存在根本性的权衡。

容错性 (Tolerance)：2002 年，来自 MIT 的`Seth Gilbert 和 Nancy Lynch`发表了对 Brewer 猜想的正式证明。该定理指出，网络共享数据系统只能保证/强支持以下三个属性中的两个：

* **一致性 (Consistency)**：保证分布式集群中的每个节点都返回相同的、最新的、成功的写入。一致性是指每个客户端对数据都有相同的视图。有多种一致性模型。`CAP`中的一致性（用于证明该定理）指的是线性一致性或顺序一致性——一种非常强的一致性。
* **可用性 (Availability)**：每个非故障节点都能在合理时间内对所有读写请求返回响应。这里的关键词是“每一个 (every)”。要保持可用，每个节点（位于网络分区的两侧）必须能够在合理时间内做出响应。
* **分区容性 (Partition tolerance)**：尽管发生网络分区，系统仍能继续运行并维护其一致性保证。网络分区是现实生活的常态。保证分区容性的分布式系统可以在分区愈合后优雅地恢复。

## NoSQL 的多样性

目前，大约有二百二十五种 NoSQL 数据库。这些数据库通常支持一种或多种类型的结构，并且它们具有特定的行为。这些特殊特征以不同的方式让开发者的生活更加舒适，例如`Cassandra`数据库的`Cassandra Query language`、搜索引擎`Elasticsearch`、`OrientDB`的实时查询、`Couchbase`的`N1QL`等。当涉及 NoSQL 数据库时，这些方面非常重要。

## SQL 的标准

对于使用关系数据库的 Java 应用，在 Java 应用程序和关系数据库之间建立一个桥接层是一种良好的做法：`DAO` - 数据访问对象。更多关于关系型数据库，有如`JPA`和`JDBC`等 API，它们对 Java 开发者具有优势：

* 没有厂商锁定。换句话说，有了标准，数据库的更改将会变得更加容易且透明化，因为我们只需要更改一个简单的驱动程序。
* 一旦有了通用的数据库通信方式，无需为每个新数据库学习新的 API。
* 从一个供应商更改到另一个不会产生影响；在某些时刻，需要使用特定的数据库资源，但在这种情况下，`DAO`层中的所有内容都不会丢失。

目前，在 NoSQL 中数据库没有标准，因此 Java 开发者面临一些问题：

* 厂商锁定
* 对于每个新数据库，都需要学习新的 API。对另一个数据库的任何更改都有很大影响，一旦丢失了所有的通信层，就没有标准的 API。即使在同一种 NoSQL 数据库中也会发生这种情况；例如从一列更改到另一列。

目前人们正努力创建一个通用 API 来让 Java 开发者的生活更轻松，例如`Spring Data`、`Hibernate ORM`和`TopLink`。`JPA`是 Java 世界中流行的 API，这就是为什么所有的解决方案都尝试使用它。

Jakarta NoSQL 是一个 Jakarta EE 规范，旨在简化 Java 应用程序与 NoSQL 数据库的集成。它定义了一组 API，并为大多数 NoSQL 数据库提供了标准实现。这有助于与应用程序中使用的底层 NoSQL 技术之间实现极低耦合。该项目包含两个层：

规范包含两个层：

* **通信层（Communication Layer）：**一组定义了与 NoSQL 数据库通信的 API。与传统的 RDBMS 世界相比，它们类似于`JDBC` API。它包含四个模块，每个对应一种 NoSQL 数据库类型：键值对（Key-Value）、列族（Column Family）、文档（Document）和图（Graph）。
* **映射层（Mapping Layer）：** 这些 API 帮助开发者将 Java 应用程序与 NoSQL 数据库集成。该层是注解驱动的，使用了`CDI`和`Bean Validation`等技术，使得开发者易用。在传统的 RDBMS 世界中，这一层可以与 Java Persistence API (JPA) 或对象关系映射框架（如`Hibernate`）相比。

以下截图显示了规范的层：

![](img/3-1.jpg)

**图 3.1**

## 为什么选择 Jakarta NoSQL？

当开发者询问 Jakarta NoSQL 规范时，第一个问题通常是：为什么？

作为开发者，我们为什么要关注它？作为读者，你为什么不应该跳过关于 Jakarta NoSQL 的这一章节？

第一点是厂商锁定（Vendor-lockin）：

**厂商锁定（Vendor-lockin）** 是任何 Java 项目在选择 NoSQL 数据库时需要考虑的问题之一。如果有切换需求，其他考虑因素包括花费在更改上的时间、使用该数据库的新 API 的学习曲线、将丢失的代码、需要替换的持久化层等。Jakarta NoSQL 通过通信 API 避免了大部分此类问题。它还拥有模板类，将`模板方法（template method）`设计模式应用于数据库操作。而`Repository`接口允许 Java 开发者创建并扩展接口，实现将由 Jakarta NoSQL 自动提供：开发者构建的方法查询将自动为他们实现。

为了清楚起见，让我们创建一个示例代码。你知道作为 Java 开发者，我相信当我看到一段代码时会信任你，并且一定会从中获得乐趣。因此，Java 让任何人都感到快乐：

* ArangoDB
* MongoDB
* Couchbase
* OrientDB

以下是不同数据库的截图：

![](img/3-2.jpg)

**图 3.2**

这些数据库有什么共同点？

是的，它们都是文档型 NoSQL 数据库，并且它们都试图创建一个文档，即一个带有名称和信息本身的元组。它们以相同的行为目标执行着完全相同的操作，但使用了不同的类、方法名等。因此，如果你想将代码迁移到另一个数据库，意味着你需要学习新的 API，并更新整个数据库代码以匹配目标数据库的 API 目标。

下图显示了面向文档的数据库：

![](img/3-3.jpg)

**图 3.3**

通过通信规范，我们只需要使用类似于`JDBC`驱动的数据库驱动，就可以轻松在不同数据库之间切换。因此，从软件架构的角度来看，开发者学习新的 NoSQL 数据库会更加轻松；我们可以平滑地跳转到另一个 NoSQL，而无需花费更多时间。

## 为什么不使用 JPA 作为 NoSQL 规范？

JPA 是一个用于对象关系映射的优秀 API，它已经是 Java 世界中由 JSR 定义的标准。如果能对 SQL 和 NoSQL 使用相同的 API 将是极好的，但 NoSQL 中存在一些 SQL 无法涵盖的行为，例如生存时间（time to live）和异步操作。JPA 根本不是为了处理这些特性设计的。

## 特定行为在 NoSQL 数据库中的性

特定行为很重要。即使在相同类型中，每个 NoSQL 数据库都有独特的特性，这是选择一个数据库而非另一个的相当考虑因素。这些特性可能使开发更容易、从配置角度来看更具扩展性或一致性、具有所需的一致性水平或搜索引擎等。例如 Cassandra 及其`Cassandra Query Language`和一致性水平、具有实时查询的 OrientDB、ArangoDB 及其`Arango Query Language`、带有`N1QL`的 Couchbase 等列出不穷。每个 NoSQL 都有特定的行为，且这种行为至关重要，因此 JNoSQL 具有足够的扩展性来捕捉这些本质不同的特性元素。

让我们在代码中寻找乐趣。在讨论了什么是 Jakarta NoSQL 以及为什么我们作为 Java 开发者应该关注这一规范之后，让我们进入后续展示一些代码。在这个示例中，我们将创建一个流畅的 Java SE 应用程序，存储在这些 NoSQL 数据库中：

* Redis（用于键值对）
* Cassandra（用于列族）
* MongoDB（用于文档）
* Neo4J（用于图）

为了将信息存储到 NoSQL 数据库，让我们创建一个实体类；在示例中，我们将创建一个“神”的类来代表神话。一个神将三个属性：id、name 和 power。

```java
public class God {
    private Long id;
    private String name;
    private String power;

    public God(Long id, String name, String power) {
        this.id = id;
        this.name = name;
        this.power = power;
    }

    public God() {
    }

    @Override
    public String toString() {
        return "God{" + "id=" + id + ", name='" + name + '\'' + power=" + power + '}';
    }
}
```

## 安装数据库

我们的目标是将信息存储到 NoSQL 数据库，在此之前安装每个 NoSQL 数据库。一种方案也是我喜欢的方案是使用`docker`和`docker-compose`。简来说，`docker`是一套通过容器交付软件的平台，而`docker-compose`是一个通过文件运行多个容器的工具。如果你想使用`docker-compose`，可以创建一个`docker-compose.yml`并添加以下信息：

```yaml
version: '3.2'
services:
  key-value:
    image: redis
    networks:
      - nosql
    ports:
      - 6379:6379
  column:
    image: "cassandra"
    networks:
      - nosql
    environment:
      JVM_OPTS: -Xms512m -Xmx512m
    ports:
      - 9042:9042
  document:
    image: "mongo:latest"
    networks:
      - nosql
    ports:
      - 27017:27017
  graph:
    image: "neo4j"
    networks:
      - nosql
```



```yaml
environment:
  NEO4J_dbms_memory_heap_max__size: 512m
  NEO4J_AUTH: neo4j/admin

ports:
  - 7474:7474
  - 7687:7687

volumes:
  - "$HOME/neo4j/data:/data"

networks:
  nosql:
```

启动一个新的环境：

`docker-compose -f docker-compose.yml up -d`

## Maven 项目

该项目是一个 Java SE 项目，以便更容易处理所有依赖及其依赖项；我们将使用 Maven 作为构建自动化过程。此类项目的主要要求是 `pom.xml`，项目对象模型（POM）是 Maven 的基本工作单元。它是一个 XML 文件，包含了项目信息以及 Maven 构建项目所需的配置细节。

我们可以将依赖分为五类：

1. **CDI**：（上下文和依赖注入）是一个标准的依赖注入框架。
2. **JSON Binding**：是一个提供在 Java 类和 JSON 文档之间标准绑定层的 Java 框架。
3. **Eclipse MicroProfile Configuration**：它是一个将配置外部化到 Java 应用程序之外并遵循要素要素等良好实践的解决方案。我们稍后会详细介绍 Eclipse MicroProfile。
4. **Jakarta NoSQL Mapping**：思考像 JPA 一样映射 NoSQL 数据库。
5. **Jakarta NoSQL 通信**：思考像 `JDBC` 一样连接 NoSQL 数据库。

如下所示：

```xml
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>jakarta.nosql</groupId>
  <artifactId>demo</artifactId>
  <version>1.0-SNAPSHOT</version>
  <name>jakarta-nosql-demo</name>
  <url>http://www.example.com</url>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
    <weld.se.core.version>3.1.2.Final</weld.se.core.version>
    <jakarta.nosql.version>1.0.0-b1</jakarta.nosql.version>
  </properties>

  <dependencies>
    <!-- CDI -->
    <dependency>
      <groupId>org.jboss.weld.se</groupId>
      <artifactId>weld-se-shaded</artifactId>
      <version>${weld.se.core.version}</version>
    </dependency>

    <!-- JSON Binding -->
    <dependency>
      <groupId>org.eclipse</groupId>
      <artifactId>yasson</artifactId>
      <version>1.0.5</version>
    </dependency>

    <!-- Eclipse MicroProfile Configuration -->
    <dependency>
      <groupId>io.smallrye</groupId>
      <artifactId>smallrye-config</artifactId>
      <version>1.3.9</version>
    </dependency>

    <!-- 映射依赖 -->
    <dependency>
      <groupId>org.eclipse.jnosql.artemis</groupId>
      <artifactId>artemis-document</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.jnosql.artemis</groupId>
      <artifactId>artemis-key-value</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.jnosql.artemis</groupId>
      <artifactId>artemis-column</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.jnosql.artemis</groupId>
      <artifactId>artemis-graph</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <!-- 通信 -->
    <dependency>
      <groupId>org.eclipse.jnosql.diana</groupId>
      <artifactId>mongodb-driver</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.jnosql.diana</groupId>
      <artifactId>cassandra-driver</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.jnosql..diana</groupId>
      <artifactId>redis-driver</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>

    <!-- 图数据库 -->
    <dependency>
      <groupId>org.apache.tinkerpop</groupId>
      <artifactId>gremlin-groovy</artifactId>
      <version>3.4.4</version>
    </dependency>

    <dependency>
      <groupId>com.steelbridgelabs.oss</groupId>
      <artifactId>neo4j-gremlin-bolt</artifactId>
      <version>0.3.1</version>
    </dependency>

    <dependency>
      <groupId>org.neo4j.driver</groupId>
      <artifactId>neo4j-java-driver</artifactId>
      <version>1.7.5</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.jnosql.artemis</groupId>
      <artifactId>graph-connections</artifactId>
      <version>${jakarta.nosql.version}</version>
    </dependency>
  </dependencies>

  <repositories>
    <repository>
      <id>oss.sonatype.org-snapshot</id>
      <url>http://oss.sonatype.org/content/repositories/snapshots</url>
      <releases>
        <enabled>false</enabled>
      </releases>
      <snapshots>
        <enabled>true</enabled>
      </snapshots>
    </repository>
  </repositories>
</project>
```

## 实体模型

给定实体类后，我们需要创建一个与 NoSQL 数据库之间进行转换的机制。Jakarta NoSQL 是注解驱动的，因此它使用了与 JPA 类似的方法。

在此示例中，我们使用了三个注解：

- `Entity` 注解：用于定义该类允许在数据库中使用。
- `Id` 注解：用于定义标识符。
- `Column` 注解：用于定义字段将存储在 NoSQL 中。

代码所示：

```java
import jakarta.nosql.mapping.Column;
import jakarta.nosql.mapping.Entity;
import jakarta.nosql.mapping.Id;

@Entity
public class God {

    @Id
    private Long id;

    @Column
    private String name;

    @Column
    private String power;

    public God(Long id, String name, String power) {
        this.id = id;
        this.name = name;
        this.power = power;
    }

    public God() {}

    @Override
    public String toString() {
        return "God{id=" + id + ", name='" + name + "', power=" + power + '}';
    }
}
```

## 键值

在本节中，我们将探索键值存储与 NoSQL 之间的关系，例如使用 `Bucket`。

代码所示：

```java
import jakarta.enterprise.context.ApplicationScoped;
import jakarta.enterprise.inject.Disposes;
import jakarta.enterprise.inject.Produces;
import jakarta.inject.Inject;
import org.eclipse.microprofile.config.inject.ConfigProperty;

@ApplicationScoped
class BucketManager {

    @Inject
    @ConfigProperty(name = "keyvalue")
    private Bucket manager;

    @Produces
    public BucketManager getManager() {
        return manager;
    }

    public void destroy(@Disposes BucketManager manager) {
        manager.close();
    }
}
```

为了简化代码，在 `META-INF/microprofile.properties` 中放入这些信息：

```properties
keyvalue=redis
```

让我们创建一个键值数据库 Hello World；这段代码将实现创建、更新、查询和删除：

```java
import jakarta.nosql.mapping.keyvalue.KeyValueTemplate;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.util.Optional;

public class KeyValueApp {

    public static void main(String[] args) throws Exception {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            KeyValueTemplate template = container.select(KeyValueTemplate.class).get();

            template.put(diana);

            final Optional<God> god = template.get(1L, God.class);

            System.out.println("query : " + god);

            template.delete(1L);

            System.out.println("query again: " + template.get(1L, God.class));
        }

        System.exit(0);
    }
}
```

一个重要的特性是 TTL（生存时间），该功能定义了信息在数据库中过期的时间：

```java
import jakarta.nosql.mapping.keyvalue.KeyValueTemplate;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.time.Duration;
import java.util.Optional;

public class KeyValueApp2 {

    public static void main(String[] args) throws Exception {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            KeyValueTemplate template = container.select(KeyValueTemplate.class).get();

            template.put(diana, Duration.ofSeconds(1L));

            final Optional<God> god = template.get(1L, God.class);
        }
    }
}
```

```java
System.out.println("query : " + god);

TimeUnit.SECONDS.sleep(2L);

System.out.println("query again: " + template.get(1L, God.class));

}

System.exit(0);

}

}
```

Jakarta NoSQL 为每个 NoSQL 数据库都提供标准的文本形式查询，因此你可以使用普通查询或 `PrepareStatement` 查询：



```java
import jakarta.nosql.mapping.PreparedStatement;
import jakarta.nosql.mapping.keyvalue.KeyValueTemplate;

import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

import java.time.Duration;
import java.util.Optional;
import java.util.concurrent.TimeUnit;

public class KeyValueApp3 {

    public static void main(String[] args) throws InterruptedException {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            KeyValueTemplate template = container.select(KeyValueTemplate.class).get();

            template.put(diana, Duration.ofSeconds(1L));

            Optional<God> result = template.getSingleResult("get 1", God.class);

            System.out.println("Query by plain text: " + result);

            PreparedStatement prepare = template.prepare("get @id", God.class);

            prepare.bind("id", 1L);

            System.out.println("Query by prepare query");

            prepare.getSingleResult().ifPresent(System.out::println);

        }

        System.exit(0);

    }

}
```

为了简化操作，Spring Data Jakarta NoSQL 还提供了仓库（repository）功能：

```java
import jakarta.nosql.mapping.Repository;

import java.util.List;

public interface GodRepository extends Repository<God, Long> {

}
```

```java
import org.eclipse.jnosql.artemis.DatabaseQualifier;

import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

import java.util.Optional;

public class KeyValueApp4 {

    public static void main(String[] args) throws InterruptedException {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            GodRepository repository = container.select(GodRepository.class, DatabaseQualifier.ofKeyValue()).get();

            repository.save(diana);

            Optional<God> result = repository.findById(1L);

            System.out.println("Find by id: " + result);

        }

        System.exit(0);

    }

}
```

就像 Spring Data 一样，你可以通过查询使用方法，即通过约定创建方法，而 Jakarta NoSQL 实现将为你自动实现。然而，键值存储仅允许通过键进行查询。因此，在我们的 God 实体中无法通过名称进行查找。

## 列族数据库（Column family database）

在本节中，我们将探索 Java 与列族数据库之间的关系。对于列族，我们将使用 Apache Cassandra。与任何数据库一样，我们需要定义连接，对于 Jakarta NoSQL 也不例外。简单而言，我们需要创建一个 `ColumnFamilyManager` 和一个用于列族 NoSQL 的 `EntityManager`，使其可用 CDI：

```java
import jakarta.nosql.column.ColumnFamilyManager;

import org.eclipse.microprofile.config.inject.ConfigProperty;

import javax.enterprise.context.ApplicationScoped;
import javax.enterprise.inject.Disposes;
import javax.enterprise.inject.Produces;
import javax.inject.Inject;

@ApplicationScoped
class ColumnManagerProducer {

    @Inject
    @ConfigProperty(defaultValue = "column")
    private ColumnFamilyManager manager;

    @Produces
    public ColumnFamilyManager getManagerCassandra() {
        return manager;
    }

    public void destroy(@Disposes ColumnFamilyManager manager) {
        manager.close();
    }

}
```

为了简化代码，我们将配置信息分离到代码之外；此外，这比硬编码密码等关键信息更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在 `META-INF/microprofile-config.properties` 中我们将放入这些信息：

```text
column=column
column.database=olympus
column.provider=org.eclipse.jnosql.diana.cassandra.column.CassandraConfiguration
column.settings.jakarta.nosql.host.1=localhost
column.settings.cassandra.query.1=CREATE KEYSPACE IF NOT EXISTS olympus WITH replication = {'class': 'SimpleStrategy', 'replication_factor' : 3};
column.settings.cassandra.query.2=CREATE COLUMNFAMILY IF NOT EXISTS olympus.God ("_id" bigint PRIMARY KEY, name text,
```

为了简化代码，Spring Data Jakarta NoSQL 也提供了仓库（repository）功能：

```java
import jakarta.nosql.mapping.Repository;

import java.util.List;

public interface GodRepository extends Repository<God, Long> {

}
```

```java
import org.eclipse.jnosql.artemis.DatabaseQualifier;

import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

import java.util.Optional;

public class ColumnApp4 {

    public static void main(String[] args) throws InterruptedException {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            GodRepository repository = container.select(GodRepository.class, DatabaseQualifier.ofColumn()).get();

            repository.save(diana);

            Optional<God> god = repository.findById(1L);

            System.out.println("Query by id : " + god);

        }

        System.exit(0);

    }

}
```

与 Redis 的键值存储不同，Apache Cassandra 允许你通过字段进行查询，但你需要创建一个二级索引，这可能会降低查询性能。因此，我们需要添加一个新的设置，使用 Cassandra 查询语言在 `name` 字段上创建索引。

```text
column.settings.cassandra.query.3=CREATE INDEX IF NOT EXISTS nameIndex ON olympus.God (name);
```

```java
import org.eclipse.jnosql.artemis.DatabaseQualifier;

import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

public class ColumnApp5 {

    public static void main(String[] args) {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            GodRepository repository = container.select(GodRepository.class, DatabaseQualifier.ofColumn()).get();

            repository.save(diana);

            System.out.println("Query by name : " + repository.findByName("Diana"));

        }

        System.exit(0);

    }

}
```

## 文档数据库

在本节中，我们将探索 Java 与文档数据库之间的关系。对于文档数据库，我们将使用 MongoDB。与任何数据库一样，我们需要定义连接，对于 Jakarta NoSQL 来说也并不不同。简单而言，我们需要使一个 `DocumentCollectionManager` 以及一个用于 Column-Family NoSQL 的 `EntityManager` 可供 CDI 使用：

```java
import jakarta.nosql.document.DocumentCollectionManager;

import org.eclipse.microprofile.config.inject.ConfigProperty;

import javax.enterprise.context.ApplicationScoped;
import javax.enterprise.inject.Disposes;
import javax.enterprise.inject.Produces;
import javax.inject.Inject;

@ApplicationScoped
class DocumentManagerProducer {

    @Inject
    @ConfigProperty(name = "document")
    private DocumentCollectionManager manager;

    @Produces
    public DocumentCollectionManager getManager() {
        return manager;
    }

    public void destroy(@Disposes DocumentCollectionManager manager) {
        manager.close();
    }

}
```

为了简化代码，我们将配置信息分离到代码之外；同时，这比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在 `META-INF/microprofile-config.properties` 中我们将放入这些信息：

```text
document=document
document.database=olympus
document.settings.jakarta.nosql.host=localhost:27017
document.provider=org.eclipse.jnosql.diana.mongodb.document.MongoDBDocumentConfiguration
```

让我们用文档数据库创建一个 hello world；这第一段代码将实现创建、更新、检索和删除：

```java
import jakarta.nosql.document.DocumentDeleteQuery;
import jakarta.nosql.mapping.document.DocumentTemplate;

import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

import java.util.Optional;

import static jakarta.nosql.document.DocumentDeleteQuery.delete;

public class DocumentApp {

    public static void main(String[] args) {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            God diana = new God(1L, "Diana", "Hunt");

            DocumentTemplate template = container.select(DocumentTemplate.class).get();

            template.insert(diana);

            final Optional<God> god = template.find(God.class, 1L);

            System.out.println("query : " + god);

            DocumentDeleteQuery deleteQuery = delete().from("God").where("_id").eq(1L).build();

            template.delete(diana);

        }

    }

}
```

为了简化代码，我们将配置信息分离到代码之外；同时，这比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在 `META-INF/microprofile-config.properties` 中我们将放入这些信息：

```text
document=document
document.database=olympus
document.settings.jakarta.nosql.host=localhost:27017
document.provider=org.eclipse.jnosql.diana.mongodb.document.MongoDBDocumentConfiguration
```

让我们用文档数据库创建一个 hello world；这段代码将实现创建、更新、检索和删除：

```java
import jakarta.nosql.document.DocumentDeleteQuery;
import jakarta.nosql.mapping.document.DocumentTemplate;
```



```java
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.util.Optional;
import static jakarta.nosql.document.DocumentDeleteQuery.delete;

public class DocumentApp {
    public static void main(String[] args) {
        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {
            God diana = new God(1L, "Diana", "Hunt");
            DocumentTemplate template = container.select(DocumentTemplate.class).get();
            template.insert(diana);

            final Optional<God> god = template.find(God.class, 1L);
            System.out.println("query : " + god);

            DocumentDeleteQuery deleteQuery = delete().from("God").where("_id").eq(1L).build();
            template.delete(diana);
        }
    }
}
```

为了简化代码，我们将配置信息分离到代码之外；同时，这比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在`META-INF/microprofile-config.properties`中我们将放入这些信息：

```text
document=document
document.database=olympus
document.settings.jakarta.nosql.host=localhost:27017
document.provider=org.eclipse.jnosql.diana.mongodb.document.MongoDBDocumentConfiguration
```

为了简化代码，我们将配置信息分离到代码之外；同时，这比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在`META-INF/microprofile-config.properties`中我们将放入这些信息：

```java
import jakarta.nosql.document.DocumentDeleteQuery;
import jakarta.nosql.mapping.document.DocumentTemplate;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.util.Optional;
import static jakarta.nosql.document.DocumentDeleteQuery.delete;

public class DocumentApp {
    public static void main(String[] args) {
        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {
            God diana = new God(1L, "Diana", "Hunt");
            DocumentTemplate template = container.select(DocumentTemplate.class).get();
            template.insert(diana);

            final Optional<God> god = template.find(God.class, 1L);
            System.out.println("query : " + god);

            DocumentDeleteQuery deleteQuery = delete().from("God").where("_id").eq(1L).build();
            template.delete(diana);
        }
    }
}
```

为了简化代码，我们将配置信息分离到代码之外；同时，这比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在`META-INF/microprofile-config.properties`中我们将放入这些信息：

```text
document=document
document.database=olympus
document.settings.jakarta.nosql.host=localhost:27017
document.provider=org.eclipse.jnosql.diana.mongodb.document.MongoDBDocumentConfiguration
```

为了简化代码，Spring Data Jakarta NoSQL 也提供了仓库（repository）功能：

```java
import jakarta.nosql.mapping.Repository;
import java.util.List;

public interface GodRepository extends Repository<God, Long> {
}

import org.eclipse.jnosql.artemis.DatabaseQualifier;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.util.Optional;

public class ColumnApp4 {
    public static void main(String[] args) throws InterruptedException {
        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {
            God diana = new God(1L, "Diana", "Hunt");
            GodRepository repository = container.select(GodRepository.class, DatabaseQualifier.ofColumn()).get();

            repository.save(diana);

            Optional<God> god = repository.findById(1L);
            System.out.println("Query by id : " + god);
        }

        System.exit(0);
    }
}
```

与 Redis 的键值存储不同，Apache Cassandra 允许你通过字段进行查询，但你需要创建一个二级索引，这可能会降低查询性能。因此，我们需要添加一个新的设置，使用 Cassandra 查询语言在`name`字段上创建索引。

```text
column.settings.cassandra.query.3=CREATE INDEX IF NOT EXISTS nameIndex ON olympus.God (name);
```

```java
import org.eclipse.jnosql.artemis.DatabaseQualifier;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

public class ColumnApp5 {
    public static void main(String[] args) {
        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {
            God diana = new God(1L, "Diana", "Hunt");
            GodRepository repository = container.select(GodRepository.class, DatabaseQualifier.ofColumn()).get();

            repository.save(diana);
            System.out.println("Query by name : " + repository.findByName("Diana"));
        }

        System.exit(0);
    }
}
```

## 文档数据库

在本节中，我们将探索 Java 与文档数据库之间的关系。对于文档数据库，我们将使用 MongoDB。与任何数据库一样，我们需要定义连接，对于 Jakarta NoSQL 来说也并不不同。坦率地说，我们需要使一个`DocumentCollectionManager`以及一个用于 Column-Family NoSQL 的`EntityManager`可供 CDI 使用：

```java
import jakarta.nosql.document.DocumentCollectionManager;
import org.eclipse.microprofile.config.inject.ConfigProperty;
import javax.enterprise.context.ApplicationScoped;
import javax.enterprise.inject.Disposes;
import javax.enterprise.inject.Produces;
import javax.inject.Inject;

@ApplicationScoped
class DocumentManagerProducer {
    @Inject
    @ConfigProperty(name = "document")
    private DocumentCollectionManager manager;

    @Produces
    public DocumentCollectionManager getManager() {
        return manager;
    }

    public void destroy(@Disposes DocumentCollectionManager manager) {
        manager.close();
    }
}
```

为了简化代码，我们将配置信息分离到代码之外；同时，这比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在`META-INF/microprofile-config.properties`中我们将放入这些信息：

```text
document=document
document.database=olympus
document.settings.jakarta.nosql.host=localhost:27017
document.provider=org.eclipse.jnosql.diana.mongodb.document.MongoDBDocumentConfiguration
```

让我们用文档数据库创建一个 hello world；这第一段代码将实现创建、更新、检索和删除：

```java
import jakarta.nosql.document.DocumentDeleteQuery;
import jakarta.nosql.mapping.document.DocumentTemplate;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.util.Optional;
import static jakarta.nosql.document.DocumentDeleteQuery.delete;

public class DocumentApp {
    public static void main(String[] args) {
        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {
            God diana = new God(1L, "Diana", "Hunt");
            DocumentTemplate template = container.select(DocumentTemplate.class).get();

            template.insert(diana);

            final Optional<God> god = template.find(God.class, 1L);
            System.out.println("query : " + god);

            DocumentDeleteQuery deleteQuery = delete().from("God").where("_id").eq(1L).build();
            template.delete(diana);
        }
    }
}
```

为了简化代码，我们将配置信息从代码中分离出来；此外，比将密码等关键信息硬编码在代码中更安全；事实上，我们将使用 Eclipse MicroProfile Configuration。

在`META-INF/microprofile-config.properties`中，我们将放入这些信息：

```properties
graph.settings.jakarta.nosql.host=bolt://localhost:7687
graph.settings.jakarta.nosql.user=neo4j
graph.settings.jakarta.nosql.password=admin
graph.provider=org.eclipse.jnosql.artemis.graph.connections.Neo4JRemote
```

让我们用图数据库创建一个“Hello World”；第一段代码将完成创建、更新、检索和删除操作：

```java
import org.eclipse.jnosql.artemis.graph.GraphTemplate;
import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;
import java.util.Optional;

public class GraphApp {
    public static void main(String[] args) {
        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {
            GraphTemplate template = container.select(GraphTemplate.class).get();

            God diana = template.getTraversalVertex()
                .hasLabel(God.class)
                .has("name", "Diana")
                .<God>next()
                .orElseGet(() -> template.insert(new God(null, "Diana", "Hunt")));

            System.out.println("query : " + diana);

            template.delete(diana.getId());

            Optional<God> god = template.getTraversalVertex(diana.getId()).next();
            System.out.println("Query: " + god);
        }
    }
}
```



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。System.exit(0);
```

你可以创建关系并填充边（Edges）。通信层（Communication Layer）定义了三个新的 API：键值对、文档和列族族。它没有新的图图 API，因为已经存在一个非常优秀的框架了。Apache TinkerPop 是一个同时用于图数据库（OLTP）和图分析系统（OLAP）的图计算框架。使用 Apache TinkerPop 作为图数据库的通信 API，映射 API（Mapping API）与其有紧密的集成：

```java
import org.eclipse.jnosql.artemis.graph.GraphTemplate;

import javax.enterprise.inject.se.SeContainer;
import javax.enterprise.inject.se.SeContainerInitializer;

import java.util.Optional;

public class GraphApp2 {

    public static void main(String[] args) {

        try (SeContainer container = SeContainerInitializer.newInstance().initialize()) {

            GraphTemplate template = container.select(GraphTemplate.class).get();

            God diana = template.getTraversalVertex().hasLabel(God.class).has("name", "Diana").<God>next().orElseGet(() -> template.insert(new God(null, "Diana", "Hunt")));

            God apollo = template.getTraversalVertex().hasLabel(God.class).has("name", "Apollo").<God>next().orElseGet(() -> template.insert(new God(null, "Apollo", "Sun")));

            God zeus = template.getTraversalVertex().hasLabel(God.class).has("name", "Zeus").<God>next().orElseGet(() -> template.insert(new God(null, "Zeus", "Thunder")));

            template.edge(diana, "brother", apollo);

            template.edge(apollo, "brother", diana);

            template.edge(zeus, "father", apollo);

            template.edge(zeus, "father", diana);

            template.delete(diana.getId());

            template.delete(zeus.getId());

            template.delete(apollo.getId());

        }

        System.exit(0);

    }

}
```

我们创建的查询将运行如图所示所示：

![](img/3-4.jpg)

**图 3.4**

## 结论

本章介绍了 Jakarta NoSQL、该 API 背后的动机，以及我们 Java 开发者如何参与。一个重要的点是，我们创建了一个简单的 Java SE 程序，它只有一个实体 `God`，被持久化到了四个数据库中，每种对应一种支持的数据库类型。

在下一章中，我们将学习 JMoordb 以及如何在你的 Jakarta EE 应用中使用它。

## 问题

1. 什么是 Jakarta NoSQL？
2. Jakarta NoSQL 有多少层？
3. 通信层和映射层之间有什么区别？
4. 什么是 Apache Tinkerpop？
5. 为什么不使用 JPA 作为 NoSQL 规范？

# 第 4 章：理解 Jmoordb

Jmoordb 是一个用于 Java 对象文档映射器（Object Document Mapper），支持 NoSQL 数据库（MongoDB、OrientDB、Couchbase）。

## 结构

- Jmoordb 简介
- 实体
- 注解
  - `@Id`
  - `@Embedded`
  - `@Referenced`
- 仓库
- 创建
- 更新
- 删除
- 搜索
- 聚合
- 数据库

## 目标

本章将展示 Jmoordb 的基本功能以及如何使用它们。

## Jmoordb 简介

在开始开发使用它的应用程序之前，理解一些基本概念是非常重要的。Jmoordb 是一个用于 Java 对象文档映射器，支持 NoSQL 数据库（MongoDB、OrientDB、Couchbase）。它是一个用于 NoSQL 的框架。它的语法与 JPA 非常相似，侧重于文档数据库。

## 实体

实体是一个表示文档属性的 Java 类。这些 Java 类被序列化和反序列化以存储在 NoSQL 数据库中。

下面的截图显示了数据库中的 JSON 文档：

![](img/4-1.jpg)

**图 4.1**

## 注解

注解允许我们用类型装饰属性，API 使用这些类型与数据库交互。以下是我们拥有的注解列表：

- `@Id`：定义文档的键字段。
- `@Ignore`：该属性将在文档中被忽略。
- `@Embedded`：定义一个嵌入文档，整个内容将存储在文档中。
- `@Referenced`：定义一个引用的文档，仅存储被引用文档键字段的值。
- `@Secondary`：表示该属性是辅助键。

一个表示 `Person` 类的简单实体示例：

```java
public class Person {

    @Id
    private String id;

    private String name;

}
```

### `@Id`

`@Id` 注解标识用主键的属性，记住，像 MongoDB 这样的 NoSQL 数据库使用内部字段来区分不同的文档。每个实体必须有一个 `@Id` 属性。

主键用于识别集合中的唯一文档并避免数据重复。当键字段为 `autoincrementable` 类型时，它们在 MongoDB 等数据库中没有直接表示，我们必须通过编程来建立它们的控制。

当你想要使用 `autoincrementable` 作为主键时，必须记住像 MongoDB 这样的数据库内部会为每个文档生成唯一的字段。在 jmoordb 中，我们提供了一种简单的实现方式，通过 `autoincrementableServices`，它提供了一个 `getContador("")` 方法，允许获取指定参数的集合的文档计数。

```java
Integer idperson = autoincrementableServices.getContador("person");
```

在某些情况下，你在实体中定义了一些属性，但你不希望这些属性被存储在数据库文档中。也就是说，它们会被 API 忽略。对于这些类型的字段，我们使用 `@Ignore` 注解：

```java
public class Person {

    @Id
    private String id;

    private String name;

    @Ignore
    private String comment;

}
```

### `@Embedded`

嵌入式文档（Embedded document）是插入到另一个文档中的文档。它是 NoSQL 数据库的特征之一，使得它非常有用，并允许我们改进在关系型数据库中无法实现的数据模型。API 允许我们定义一个嵌入文档或一个嵌入文档列表。该文档通过使用相应注解定义的另一个实体来定义。

嵌入文档的使用取决于你使用它们的特定场景。例如，如果你将文档嵌入到其他文档中，并且这些文档需要更新，那么你必须检查所有文档以更新嵌入式文档。如果数据库设计不当，这可能会成为限制。

以下是如何定义嵌入文档的示例：

```java
public class Country {

    @Id
    private String id;

    private String country;

}

public class Person {

    @Id
    private String id;

    private String name;

    @Embedded
    private Country country;

}
```

要定义嵌入文档列表，使用类似下面的语法 `List<T>`：

```java
public class Person {

    @Id
    private String idperson;

    private String name;

    @Embedded
    List<Country> country;

}
```

### `@Referenced`

被引用的文档（Referenced document）是存储指向另一个文档键字段引用的文档。Jmoordb 提供了一个简单的机制来管理文档之间的引用关系。使用引用可以避免在使用嵌入式文档时可能出现的文档重复。它们的使用与数据库设计相关，并根据特定需求进行调整，模拟了文档之间的关系。

例如，一个嵌入了国家信息的文档存储在名为 `Person` 集合的 100000 个文档中。你可以发现，在所有居住在巴拿的人的文档中，都能找到巴拿国家的相同信息。

通过这种设计，信息是重复的，消耗了更多的存储空间，而且为了对国家信息进行任何更改，都必须检查所有包含这些信息的文档并进行编辑，这将直接影响应用程序的性能。

下面的截图显示了嵌入和重复的文档：

![](img/4-2.jpg)

**图 4.2**

为了避免此类描述的情况，我们有了 `@Referenced` 注解，它允许我们在文档之间创建引用。这些引用可以通过特定属性或列表来实现。

这与关系型数据库中提供的表之间的关系非常相似。当在引用文档中进行搜索时，此查询会在另一个集合中查找包含相关字段的文档。Jmoordb 提供了指示是否要加载代表被引用文档的实体，即是否在另一个集合中进行搜索：

下面的截图显示了引用 `Country=pa:` 的文档：

![](img/4-3.jpg)

**图 4.3**

`@Referenced` 允许你指定对集合的引用，这些集合不一定存储在同一个数据库或同一个服务器上。下面的截图显示了存储在不同服务器数据库中的引用文档：

![](img/4-4.jpg)

**图 4.4**

`@Referenced` 语法非常简单，如下：

`@Referenced(collection="", field="", javatype="", lazy="", repository="")`

下表显示了 `@Referenced` 的语法：

| 属性 | 说明 |
| :--- | :--- |
| `collection` | 被引用集合的名称 |
| `field` | 标识集合中文档的键字段名称 |
| `javatype` | 指定主键的数据类型。允许的类型为（`String`/`Integer`） |
| `lazy` | 允许你设置是否要通过搜索来加载被引用文档的实体。<br>- **False:** 表示当在主文档中搜索时。<br>- **True:** 表示当在集合中搜索时，不会搜索相关集合，仅返回相关集合的 id。 |
| `repository` | 被引用集合的 `Repository` 名称，我们必须指定它所在的包。 |

**表 4.1**

一个带有被引用文档的实体示例：

```java
public class Person {

    @Id
    private String idperson;

    private String name;

    @Referenced(collection = "Country", field = "idperson", javatype = "String", lazy = false, repository = "com.repository.CountryRepository")
    Country country;

}
```

引用文档列表的示例：

```java
public class Person {

    @Id
    private String idperson;

    private String name;

    @Referenced(collectiont = "Country", field = "idperson", javatype = "String", lazy = false, repository = "com.repository.CountryRepository")
    List<Country> country;

}
```

## Repository

仓库（Repository）是一个类型为 `@Stateless`（无状态）的类，在其中我们可以实现执行对数据库、集合和文档操作的方法。API 与 Java 企业版/Jakarta 集成，因此它使用了许多组件，如 Enterprise Java Beans (EJB)、CDI 等。

Jmoordb 直接实现了 MongoDB 的 java 驱动程序，允许我们直接使用驱动程序提供的所有方法。`Document` 类由 Jmoordb 支持并用于许多操作。API 与 Java 企业版/Jakarta 集成。定义一个简单仓库的示例：

```java
@Stateless
public class EntityRepository extends Repository<Entity> {

    public EntityRepository() {
        super(Entity.class);
    }

}
```

在构造函数中，你可以指定数据库和集合：

```java
@Stateless
public class EntityRepository extends Repository<Entity> {

    public EntityRepository() {
        super(Entity.class, "databases");
    }

}
```

方法已组织成如下组：

- C.R.U.D.
  - 创建
  - 读取
  - 更新
  - 删除
- 数据库操作
  - 无模式的数据库

## C.R.U.D.

在关系型数据库世界中，创建（Create）、读取（Read）、更新（Update）和删除（Delete）的缩写用于最常见的数据库操作。在 NoSQL 数据库中，我们可以处理类似的持久操作。许多此类数据库支持事务，使得它们适用于许多解决方案。下面描述了执行这些操作的常用方法。

### 创建

常用操作之一是在集合中存储一系列文档。从 Java 通过仓库将其转换为 JSON/BSON 并存储在数据库中。Jmoordb 执行序列化和反序列化以确保数据完整性。使用 `save()` 方法可以将实体保存到集合中。

下表显示了 `save()` 方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `Boolean save(T t, Boolean… verifyID)` | 将实体保存到数据库中。 |
| `Boolean save(Document doc, Boolean… verifyID)` | 将文档保存到数据库中 |

**表 4.2**

下表描述了 `save()` 方法的参数：

| 参数 | 说明 |
| :--- | :--- |
| `T t` | 要保存的实体 |
| `Document doc` | 这是一个 MongoDB 文档。 |
| `Boolean… verifyID: true` | 可选的，默认情况下，它表示你必须验证不存在具有该 id 的文档。 |
| `Boolean… verifyID: false` | 告诉 jmoordb 不要搜索是否存在另一个具有 id 的文档。 |

**表 4.3**

以下是在 MongoDB 集合中保存实体的示例：

```java
Planet planet = new Planet("earth", "Earth", new Date());

if (planetRepository.save(planet)) {

}
```

请记住，支持 MongoDB Java 驱动，因此你可以使用文档类存储在集合中：

```java
Document doc = new Document("id", 3)
    .append("planet", "Jupiter")
    .append("date", new Date());

if (planetRepository.save(doc)) {

}
```




### 更新

为了更新一个或多个文档，提供了具有不同变体的`update()`方法。这些方法允许你利用这些方法来执行大多数操作。用于更新的方法描述如下表所示：

| 方法 | 说明 |
| :--- | :--- |
| `Boolean update(T t)` | 使用实体的值更新文档。 |
| `Integer update(Document docSearch, Document docUpdate)` | 根据包含要更新值的文档限制条件更新文档，并根据一个文档执行搜索。 |
| `Integer updateMany(Document docSearch, Document docUpdate)` | 更新多个文档。 |
| `Integer replaceOne(String key, String value, Document docUpdate)` | 根据用于执行搜索的值对替换文档。 |
| `Integer replaceOne(Bson search, Document docUpdate)` | 将一个文档替换为另一个。 |
| `Integer updateMany(Document docSearch, Document docUpdate)` | 更新多个文档。 |

#### 表 4.4

在下面的代码段中，更新了名为`Planet`的实体的`Population`属性，注意这是对`update()`方法的简单调用。

```java
planet.setPopularion(50000);

if (planetRepository.update(planet)) {

}
```

通过 MongoDB`Document`类，你可以更新集合中的文档：

```java
planetRepository.update(
    newDocument("id", "earth"),
    new Document("$set", new Document("planet", "New Earth"))
);
```

可以使用`document.field`以简单的方式更新嵌入式文档。在以下示例中将创建两个实体，其中将实现一个嵌入式文档：

```java
@Getter
@Setter
public class Country {

    @Id
    private String idcountry;

    private String country;

    private Integer population;

    @Embedded
    private Continent continent;
}

@Getter
@Setter
public class Continent {

    @Id
    private String idcontinent;

    private String continent;

    private String active;
}
```

```java
countryRepository.updateOne(
    new Document("continent.idcontinent", "am").append("active", "yes"),
    new Document(
        "$set",
        new Document("country", "Panama").append("population", 860000)
    )
);
```

`update`方法更新单个文档，对于需要更新多个文档的情况，使用`updateMany`方法：

```java
countryRepository.updateMany(
    new Document("country", "Colombia"),
    new Document(
        "$set",
        new Document("country", "Colombia").append("population", 545337)
    )
);
```

### 删除

API 支持删除单个或多个文档，可以使用`delete()`方法以非常简单的方式实现。下表显示了实现`delete`方法的不同方式：

| 方法 | 说明 |
| :--- | :--- |
| `delete(Document)` | 删除文档。 |
| `delete(String sql)` | 支持使用 SQL 创建筛选器以移除符合条件的文档。 |
| `delete(key, value)` | 删除搜索匹配指定条件的文档。 |
| `deleteAll()` | 删除所有文档。 |
| `deleteMany(doc)` | 删除所有符合搜索文档中指定条件的文档。 |
| `deleteMany(sql)` | 删除所有符合 SQL 查询中指示条件的文档。 |
| `deleteMany(key, value)` | 删除所有符合过滤器中指定条件的文档。 |

#### 表 4.5

要删除文档，你应该指定`from`字段和值，该值将用于找到符合该条件的文档，然后将其删除：

```java
if (countryRepository.delete("idcountry", country.getIdcountry())) {

}
```

`deleteAll()`方法允许我们从集合中移除所有文档，这是在使用时必须考虑的操作，以避免出现某些情况：

```java
if (countryRepository.deleteAll() != 0) {

}
```

### 读取

在本节中，你将学习搜索文档的方法。记住，NoSQL 数据库的语法和搜索机制与关系型数据库不同。Jmoordb 提供了一种简单的方法与文档交互以检索它们。

jmoordb 内部搜索分为以下几类：

- 按主键搜索
- 按辅助键搜索
- 按任何属性搜索

#### 按主键搜索

下表显示了通过主键搜索的方法：

| 方法 | 说明 |
| :--- | :--- |
| `Optional<T> findById(T t2)` | 搜索由`@Id`定义的主键的实体。 |
| `Optional<T> findById(Document doc)` | 以主键作为参数搜索集合。 |
| `Optional<T> findById(String sql)` | 支持 SQL。 |

#### 表 4.6

- `findById()`：通过查询集合执行读取操作，可以执行所示的复杂查询：

```java
Planet planet = new Planet();

planet.setIdplanet("earth");

Optional<Planet> p1 = planetRepository.findById(planet);

if (p1.isPresent()) {
    planet = p1.get();
}
```

- 基于文档的搜索：Jmoordb 支持基于 MongoDB 的直接搜索。建议在使用时具有有关 MongoDB 的基础知识。该示例非常简单：它展示了通过想要查找`idplanet`的文档进行搜索。

```java
Document doc = new Document("idplanet", "earth");

Optional<Planet> p1 = planetRepository.findById(doc);

if (p1.isPresent()) {
    planet = p1.get();
}
```

- 直接查询支持：许多开发者熟悉 SQL 语言，API 允许使用这些指令执行许多搜索操作：

```java
Optional<Planet> p1 =
    planetRepository.findById("select * from planet where idplanet='earth'");

if (p1.isPresent()) {
    planet = p1.get();
}
```

#### 按辅助键搜索

你可以直接使用键，或者通过`findBySecondaryKey()`方法以更快的方式，该方法识别实体中声明为`@Secondary`的属性，将在本节中解释。下表显示了通过辅助键搜索的方法：

| 方法 | 说明 |
| :--- | :--- |
| `Optional<T> findBySecondaryKey(T t2)` | 搜索了`@Secondary`属性的实体。 |
| `Optional<T> findBySecondaryKey(Document doc)` | 通过定义辅助键的文档搜索实体。 |

#### 表 4.7

`Client`类是一个包含`@Secondary`属性的实体，该属性将`code`属性定义辅助键：

```java
public class Client {

    @Id
    private Integer id;

    @Secondary
    private String code;

    private String name;
}
```

现在实现`save()`方法，在保存文档之前验证是否存在具有辅助键的文档，以避免数据重复：

```java
public String save() {

    Client client = new Client(25, "av", "avbravo");

    Optional<Client> optional = clientRepository.findBySecondaryKey(client);

    if (!optional.isPresent()) {
        clientRepository.save(cliente);
    }
}
```

#### 按任何属性搜索

Jmoordb 允许通过任何属性进行搜索，同时也支持复杂的搜索，为 NoSQL 数据库的常规操作提供了强大的功能。这使我们能够轻松扩展一系列操作的 API。

下表显示了该方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `public Optional<T> find(String key, Object value);` | 根据键/值对执行搜索 |
| `public Optional<T> find(Document document)` | 根据文档进行搜索 |
| `public Optional<T> find(Bson filter)` | 根据过滤器进行搜索 |
| `public Optional<T> find(String statement)` | 根据 SQL 指令进行搜索 |

**表 4.8**

在以下示例中，对匹配`idplanet="earth"`的文档集合进行搜索：

```java
Planet planet = new Planet();

Optional<Planet> p1 = planetRepository.find("idplanet", "earth");

if (p1.isPresent()) {
    planet = p1.get();
}
```

你可以使用 MongoDB 文档类来扩展 Jmoordb 中的搜索条件。如下所示的代码段所示：

```java
Document doc = new Document("idplanet", "earth");

Planet planet = new Planet();

Optional<Planet> p2 = planetRepository.find(doc);

if (p2.isPresent()) {
    planet = p2.get();
}
```

### 过滤器（Filter）

过滤器简化了复杂查询的构建。jmoordb 直接支持 MongoDB 过滤器。在链接中，你可以找到 MongoDB 中使用的过滤器定义：[`mongodb.github.io/mongo-java-driver/3.0/builders/filters/`](https://mongodb.github.io/mongo-java-driver/3.0/builders/filters/)

使用运算符`eq`的示例，同样地我们可以实现其他运算符。

```java
Planet planet = new Planet();

Optional<Planet> p2 = planetRepository.find(eq("idplanet", "earth"));

if (!p2.isPresent()) {
    planet = p2.get();
}
```

### 搜索嵌入文档

通常情况下，你有嵌入文档，因此查看其内部是一项相当常见的任务。查看以下显示嵌入行星文档的文档：

```json
{
  "_id": ObjectId("5884e4ffb2a08a10f017f673"),
  "idcontinent": "as",
  "continent": "Asia",
  "planet": {
    "idplanet": "mars",
    "planet": "Mars",
    "fecha": ISODate("2019-01-21T21:21:42.044Z")
  }
}
```

要执行搜索，指定嵌入文档的名称以及我们要执行搜索的属性：

```java
Continent continent = new Continent();

Optional<Continent> c =
    continentRepository.find(new Document("planet.idplanet", "mars"));

if (c.isPresent()) {
    continent = c.get();
}
```

结果将类似于：

```java
Continent{
  idcontinent=as,
  continent=Asia,
  planet=Planet{
    idplanet=mars,
    planet=Mars,
    fecha=Sat Jan 21 16:21:42 EST 2019
  }
}
```

### 搜索嵌入文档列表

搜索嵌入文档列表与搜索单个嵌入文档相同。创建一个包含你想要搜索条件的文档类型对象，并通过仓库运行搜索操作。

在以下示例中，我们看到一个包含嵌入文档的文档以及一个实现的 Java 代码段：

```json
db.continent.find().pretty()

{
  "_id": ObjectId("5884f516b2a08a0ceb287e99"),
  "idcontinent": "eu",
  "continent": "Europe",
  "planet": [
    {
      "idplanet": "mars",
      "planet": "Mars",
      "fecha": ISODate("2017-01-21T21:21:42.044Z")
    },
    {
      "idplanet": "earth",
      "planet": "Earth",
      "fecha": ISODate("2017-01-21T21:21:42.044Z")
    }
  ]
}

{
  "_id": ObjectId("5884f585b2a08a0da194491d"),
  "idcontinent": "am",
  "continent": "America",
  "planet": [
    {
      "idplanet": "mars",
      "planet": "Mars",
      "fecha": ISODate("2017-01-21T21:21:42.044Z")
    }
  ]
}
```

随后创建了`Continent`类，其中包含一个嵌入文档列表：

```java
public class Continent {

    @Id
    private String idcontinent;

    private String continent;

    private List<Planet> planet;
}
```

现在我们通过仓库执行搜索：

```java
Continent continent = new Continent();

Optional<Continent> c =
    continentRepository.find(new Document("planet.idplanet", "mars"));
```

### 在仓库中搜索

`findBy`方法允许我们执行各种搜索，并返回`Repository`类中指定的类型实体列表。下表显示了`findBy`方法支持的不同参数：

| 方法 | 说明 |
| :--- | :--- |
| `List<T> findBy(Document doc, Document... docSort)` | 根据文档搜索集合，并可选根据另一个文档进行排序 |
| `List<T> findBy(String key, Object value, Document... docSort)` | 根据键/值对搜索集合，并可选根据另一个文档进行排序 |
| `List<T> findBy(String sql)` | 根据 SQL 条件进行搜索 |
| `List<T> findBy(Bson builder, Document... docSort)` | 根据过滤器进行搜索 |

**表 4.9**

```java
List<Continent> list = continentRepository.findAll();
```

为将返回的文档设置限制，记住 jmoordb 支持分页。通过`setLimitOfAllMethod()`方法我们可以指定文档数量：

```java
continentRepository.setLimitOfAllMethod(125);
```




```java
List<Continent> list = continentRepository.findAll();
```

## 示例

我们将展示一组使用`findBy()`方法的简短示例：

```java
List<Continent> list = continentRepository.findBy(new Document("idcontinent", "am"));
```

查找并排序文档：

```java
List<Continent> list = continentRepository.findBy(
    new Document("idcontinent", "am"),
    new Document("idcontinent", 1)
);
```

不带排序搜索嵌入文档：

```java
List<Country> list = countryRepository.findBy(
    new Document("continent.idcontinent", "5")
);
```

按国家排序搜索嵌入文档：

```java
List<Country> list = countryRepository.findBy(
    new Document("continent.idcontinent", "5"),
    new Document("country", 1)
);
```

```java
List<Country> list = countryRepository.findBy(
    new Document("population", new Document("$gt", 500))
);
```

在文档中搜索人口大于 500 的文档并按`Country`排序：

```java
List<Country> list = countryRepository.findBy(
    new Document("population", new Document("$gt", 500)),
    new Document("country", 1)
);
```

在文档中搜索人口小于 200 的文档：

```java
List<Country> list = countryRepository.findBy(
    new Document("population", new Document("$lt", 200))
);
```

在集合中搜索人口等于 800 的文档：

```java
List<Country> list = countryRepository.findBy(
    new Document("population", new Document("$eq", 800))
);
```

搜索引用文档：

```java
List<Country> list = countryRepository.findBy(
    new Document("idcontinent", "am")
);
```

## 构建器（Builder）

Builder 允许我们通过运算符构建复杂的查询。在 MongoDB 门户中，你可以找到更多参考（[`mongodb.github.io/mongo-java-driver/3.2/builders/`](https://mongodb.github.io/mongo-java-driver/3.2/builders/)）。

其中一些操作符包括：

- `eq`
- `gt`
- `gte`
- `lt`
- `lte`
- `ne`
- `in`
- `nin`

例如复合查询（`active="yes" and mark.idmark=9`）：

```java
List<Article> list = articleRepository.findBy(
    and(eq("active", "yes"), eq("mark.idmark", 9))
);
```

## 分页（Pagination）

分页帮助我们以高效的方式处理大量数据，避免因不必要的文档导致实体负载过重。分页不是加载集合中的所有文档，而是加载一小部分，然后将其移动到各个页面中，这会对应用程序的性能产生有利影响。

下表显示了方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `public List<T> findPagination(Document filter, Integer pageNumber, Integer rowsForPage, Document… docSort)` | 指定过滤器、页码和每页行数。 |
| `public List<T> findPagination(String sql, Integer pageNumber, Integer rowsForPage)` | 指定 SQL 条件、页码和每页行数。 |

**表 4.11**

参数用于：

- `pageNumber`：当前页码。
- `rowsForPage`：每页行数。
- `Document… docSort`：可选的排序文档。

你可以使用`sizePage(Integer rowsForPage, Document …doc)`方法，根据你想要的每页行数来获取集合中的总页数：

```java
Integer size = countryRepository.sizePage(10);
```

获取由集合中前 10 个文档组成的第一页：

```java
List<Country> countryList = countryRepository.findPagination(1, 10);
```

可以使用排序和其他操作来实现分页：

```java
List<Country> countryList = countryRepository.findPagination(
    1,
    10,
    new Document("country", 1)
);
```

按国家名称过滤并排序，并获取每页 10 行的第一页：

```java
List<Country> countryList = countryRepository.findPagination(
    new Document("country", "America"),
    1,
    10,
    new Document("country", 1)
);
```

使用 SQL 查询实现分页：

```java
String sql = "select * from country where idcountry='pa'";

List<Country> countryList = countryRepository.findPagination(sql, 1, 10);
```

### `findFirst`

它返回集合中的第一个文档。下表显示了方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `public Optional<T> findFirst(Document… doc)` | 返回集合中符合`Document`中陈述条件的第一个文档。 |
| `public Optional<T> findFirst(String sql)` | 返回集合中符合 SQL 命令中指出的条件的第一个文档。 |

**表 4.12**

此示例搜索了集合中的第一个文档：

```java
Optional<Country> optional = countryRepository.findFirst(
    new Document("idcountry", "pa")
);

if (optional.isPresent()) {
    Country c = optional.get();
}
```

## SQL 支持

基础 SQL 支持已包含在框架中，通过集成一个有趣的库，该库将 SQL 指令转换为 MongoDB 查询。集成已完成，以便通过仓库类与 jmoordb 使用。API 由 Vincent Russell 开发。你可以在仓库中检查代码：

[`github.com/vincentrussell/sql-to-mongo-db-query-converter`](https://github.com/vincentrussell/sql-to-mongo-db-query-converter)

这些方法在本章的不同章节中已有描述，并在后续章节显示了它们的快速指南。下表显示了方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `public Optional<T> findById(String sql)` | 按主键搜索。 |
| `public List<T> findPagination(String sql, Integer pageNumber, Integer rowsForPage)` | 使用分页进行搜索。 |
| `public List<T> findBy(String sql)` | 查找符合 SQL 条件的文档。 |
| `public Boolean delete(String sql)` | 删除符合 SQL 中指明条件的文档。 |
| `public Boolean deleteMany(String sql)` | 删除多个符合 SQL 中指明条件的文档。 |

**表 4.13**

以下是直接在数据库集合上操作 SQL 指令的示例。

获取集合中人口大于 50 的第一个国家：

```java
String sql = "select * from country where population > 50";

Optional<Country> optional = countryRepository.findFirst(sql);

if (optional.isPresent()) {
    Country c = optional.get();
}
```

执行带有调用排序的 SQL 查询：

```java
List<Invoice> invoice = invoiceRepository.findBy(
    "select * from Invoice where status.idstatus=1 order by invoice"
);
```

使用`findById()`按`idplanet`过滤的示例：

```java
Planet planet = new Planet();

Optional<Planet> p2 = planetRepository.findById(
    "select * from p where idplanet='earth'"
);

if (p2.isPresent()) {
    planetas = p2.get();
}
```

使用 SQL 进行分页：

```java
String sql = "select * from country where idcountry='pa' order by idcountry";

List<Country> countryList = countryRepository.findPagination(sql, 1, 10);
```

对于删除，指令提供了多种方案，如下所示。删除`idcountry`等于 pa 的文档：

```java
String sql = "delete from country where idcountry='pa'";

countryRepository.delete(sql);
```

删除多个文档时使用`deleteMany()`方法：

```java
String sql = "delete from country where idcountry='pa'";

countryRepository.deleteMany(sql);
```

## 聚合（Aggregation）

聚合允许我们执行操作返回结果。这些操作可以对数据集进行分组，便于在文档上执行操作。使用 MongoDB 的 Java 驱动可以获得聚合的支持，并通过 jmoordb 实现以方便使用。

它们的示例可以在 MongoDB 站点看到：

[`docs.mongodb.com/manual/aggregation/`](https://docs.mongodb.com/manual/aggregation/)

- `$match`
- `$group`

Jmoordb 使用`JmoordbResult`类来返回执行的聚合操作的结果。

以下截图显示了 jmoordb 中的聚合实现：

![](img/4-5.jpg)

**图 4.5**

聚合支持的方法列表可以在下表中找到。下表显示了方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `List<JmoordbResult> aggregateFromDocument(List<Document> documentList)` | 根据文档列表执行聚合操作。 |
| `List<JmoordbResult> aggregateFromBuilder(List<Bson> builder)` | 根据`Document`中的过滤器列表执行聚合操作。 |
| `List<T> aggregateToEntity(List<Document> documentList)` | 根据文档列表的聚合结果返回实体列表。 |

**表 4.14**

支持聚合构建器（Aggregation Builder），让构建语句变得更容易。`JmoordbResult`类包含一个`Hashmap`，其中存储聚合结果。可以通过`get("name")`方法获取值。它将返回用于将其添加为`_id`的字段名称。下表显示了该方法的语法：

| Method | Description |
| :--- | :--- |
| `String get("_id")` | 用于分组的字段值。它将始终作为`_id`返回。 |
| `String get("name")` | 为结果定义了什么？ |

**表 4.15**

`get`方法的使用示例：

```java
list.forEach((a) -> {
    System.out.println(a.get("_id") + " " + a.get("idcountry"));
});
```

- `$match`：过滤所有洲份为美洲的国家，注意这是一个嵌入文档：

```java
List<Document> documentList = Arrays.asList(
    new Document(
        "$match",
        new Document("continent.idcontinent", "am")
    )
);

List<Country> list = countryRepository.aggregateToEntity(documentList);

list.forEach((a) -> {
    System.out.println(" " + a.getDescription());
});
```

- `$group`：它允许我们对集合进行分组并对其执行操作。例如，在 MongoDB 中，我们将根据活动字段进行分组，并对每个组进行总计。

示例：按 active 分组统计文章数量。如果我们使用 MongoDB shell，应该执行类似如下所示的指令：

```javascript
db.article.aggregate([
    {
        "$group": {
            "_id": {
                "_active": "$active"
            },
            "total": {
                "$sum": 1
            }
        }
    }
]);
```

将生成如下的输出：

```json
{
    "_id": {
        "_active": "yes"
    },
    "total": 1790
}

{
    "_id": {
        "_active": "no"
    },
    "total": 2
}
```

下面使用 jmoordb 实现的示例。创建了一个`Document`的`ArrayList`，在其中使用聚合，结果将以类型为`JmoordbResult`的`List<>`返回，该列表包含用于获取值的键值对：

```java
List<Document> documentList = Arrays.asList(
    new Document(
        "$group",
        new Document("_id", "$" + "active")
            .append("quantity", new Document("$sum", 1))
    )
);

List<JmoordbResult> list =
    articleRepository.aggregateFromDocument(documentList);

list.forEach((a) -> {
    System.out.println(
        "_id " + a.get("_id") +
        " quantity: " + a.get("quantity")
    );
});
```

### `$match`、`$group`

过滤`brand.idmark=9`的项目，将其按资产分组并统计数量。使用 MongoDB shell 的示例：

```javascript
db.article.aggregate([
    {
        "$match": {
            "trademark.idtrademark": 9
        }
    },
    {
        "$group": {
            "_id": {
                "active": "$active"
            },
            "quantity": {
                "$sum": 1
            }
        }
    }
]);
```

结果将是：

```json
{
    "_id": {
        "active": "yes"
    },
    "quantity": 95
}

{
    "_id": {
        "active": "no"
    },
    "quantity": 2
}
```

我们将遵循以下步骤进行实现：

- 使用`$match`定义过滤器，其中文章将通过`brand.idmark=9`进行过滤。
- 通过 active 字段使用`$group`分组。
- 使用`$sum, 1`统计文档数量。

```java
List<Document> documentList = Arrays.asList(
    new Document(
        "$match",
        new Document("trademark.idtrademark", 9)
    )
);
```



```java
new Document("$group", new Document("_id", "$" + "active")
    .append("quantity", new Document("$sum", 1))));

List<JmoordbResult> list = articleRepository.aggregateFromDocument(documentList);

list.forEach((a) -> {
    System.out.println("_id " + a.get("_id") + " quantity: " + a.get("quantity"));
});
```

### `$match` 配合 `$group` 统计总成本

过滤 `mark.idmark=9` 的文章，将其按资产分组并加上 `$cost`。我们在 MongoDB shell 中运行它：

```javascript
db.article.aggregate([
    {
        "$match": {
            "trademark.idtrademark": 9
        }
    },
    {
        "$group": {
            "_id": {
                "active": "$active"
            },
            "cost_total": {
                "$sum": "$cost"
            }
        }
    }
])
```

结果可能类似所示：

```json
{"_id": {"active": "yes"}, "cost_total": 13844.6}

{"_id": {"active": "no"}, "cost_total": 370}
```

以下是通过 `jmoordb` 在 Java 中实现的代码：

```java
List<Document> documentList = Arrays.asList(
    new Document("$match", new Document("trademark.idtrademark", 9)),
    new Document("$group",
        new Document("_id", "$" + "active")
            .append("totalcost", new Document("$sum", "$cost")))
);

List<JmoordbResult> list = articleRepository.aggregateFromDocument(documentList);

list.forEach((a) -> {
    System.out.println("_id " + a.get("_id") + " totalcost: " + a.get("totalcost"));
});
```

输出可以类似所示：

```json
{"_id": {"active": "yes"}, "cost_total": 13844.6}

{"_id": {"active": "no"}, "cost_total": 370}
```

```java
Integer n = continentRepository.count(new Document("idcontient", "am"));
```

**结果：1**

**计数引用文档：**统计 `continents` 集合中属于 `Earth` 行的文档数量。在引用的文档中：

```java
Integer n = continentRepository.count(
    new Document("planet", new Document("idplanet", "earth"))
);
```

## 页面大小

返回集合中的总页数。它还允许为每个集合分配页数。我将向你展示一些用法示例。每个集合分配 5 页：

```java
Integer size = countryRepository.sizeOfPage(5);
```

浏览该大陆的所有国家，每页 5 行：

```java
Integer size = countryRepository.sizeOfPage(
    5,
    new Document("idcontinent", "am")
);
```

## `createIndex(Documment… doc)`

索引允许你优化数据库查询操作，极大提高应用程序性能。以下是一些用法示例：

- 创建主键索引：

  ```java
  planetRepository.createIndex();
  ```

- 根据行星属性创建索引：

  ```java
  planetRepository.createIndex(new Document("planet", 1));
  ```

- 创建一个复合索引：

  ```java
  planetRepository.createIndex(
      new Document("idplanet", 1).append("planet", 1)
  );
  ```

- 为文本搜索创建文本索引，广泛用于自动补全等组件：

  ```java
  planetRepository.createIndex(new Document("idplanet", "text"));
  ```

## `listCollecctions()`

获取数据库中集合的列表：

```java
List<String> list = countryRepository.listCollecctions();

list.forEach((s) -> {
    System.out.println(s);
});
```

显示数据库中所有的集合。

### `existsCollection(String nameCollection)`

检查数据库中是否存在集合：

```java
if (continentRepository.existsCollection("continent")) {
    // 存在
}
```

### `createCollection(String nameCollection)`

它允许我们在数据库中创建一个集合；请记住，这是可选的。在尝试插入第一个文档时，`jmoordb` 会自动创建集合。

让我们看创建一个集合的示例：

```java
if (planetRepository.createCollection("planet")) {
}
```

### `drop()`

它允许你从数据库中删除集合。一些用法示例：

- 删除存储库中指定的当前集合：

  ```java
  if (planetRepository.drop()) {
  }
  ```

- 删除方法参数中指定的集合：

  ```java
  if (planetRepository.drop("continent")) {
  }
  ```

### `toDocument(Object t)`

将实体转换为文档，适用于我们需要处理文档而非 Java 对象的操作：

```java
Document doc = planetRepository.toDocument(planet);
```

### `dropDatabase()`

删除数据库以及所有集合。在使用此方法时必须小心：

```java
planetRepository.dropDatabase();
```

## `ListOfPage`

返回一个对应于所有可用页数的整数列表。当我们有一个数据表并希望在 `SelectOneMenu` 中显示页列表，让用户从列表中选择一个数字跳转到该页时：

```java
Integer rowPage = 25;

List<Integer> pages = new ArrayList<>();

public List<Integer> getPages() {
    return planetRepository.listOfPage(rowPage);
}
```



## 无模式的数据库我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。NoSQL 数据库允许我们存储非结构化信息，Jmoordb 提供了 `jmoordbResult` 类来管理结果：

- 在框架内部，我们可以对这些数据库进行查询并返回一个包含 `HashMap` 的 `List<JmoordbResult>`，我们可以通过遍历它来处理结果。
- 在局限性方面，嵌入式文档将以 String 形式返回，格式为 `Document{field1:value1, fieldn:valuen}}`。

下表显示了方法的语法：

| 方法 | 说明 |
| :--- | :--- |
| `List<JmoordbResult> unknown(String database,String collection, Document… doc)` | 对非结构化数据库进行查询。 |
| `List<JmoordbResult> unknown Sort(String database,String collection, Document doc,Document… docSort)` | 搜索 `Document` 中进行的查询，并可选支持排序。 |
| `List<JmoordbResult> unknown(String database,String collection, Bson filter,Document… docSort)` | 搜索 `Document` 中实现的过滤器，并可选支持排序。 |
| `List<JmoordbResult> unknownPagination(String database,String collection,Integer pageNumber, Integer rowsForPage, Document… doc)` | 进行分页搜索 |
| `List<JmoordbResult> unknownPaginationSort(String database,String collection,Integer pageNumber, Integer rowsForPage, Document doc,Document… docSort)` | 进行带分页和排序的搜索 |

**表 4.17**

将使用以下 MongoDB 集合来开发示例。如果你查看存储的信息，它：

1. 如何使用 `Jmoordb` 创建实体？
2. 如何对嵌入文档进行搜索？
3. 如何声明引用？
4. 哪些方法可以在没有模式（schemas）的情况下更新集合中的数据？
5. 如何获取集合中的文档总数？

# 第 5 章：探索 Eclipse MicroProfile

本章将探索今天应用开发中最具竞争的领域之一，即使用 `Microprofile` 创建微服务。

## 结构

- Eclipse MicroProfile 骨架
- 示例代码
- 数据库
- 技术的整合
- 层、层、更多的层
- 演讲者服务
- 会话服务
- 会议服务
- 客户端服务

## 目标

Eclipse MicroProfile 计划的目标是`为微服务架构优化企业级 Java`。它基于 `Jakarta EE` API 的子集，因此我们可以像构建 Jakarta EE 应用一样构建 MicroProfile 应用。

分而治之——古罗马人最关键的策略——在多个领域都非常有效。将任何重大问题拆解为小部分的背景，可以使工作更于理解，提高可扩展性和敏捷性，并允许更多人参与工作以更快交付。微服务正诞生于这一原则。微服务架构是面向服务架构（SOA）风格的一种变体，它将应用程序结构化为松耦合服务的集合。在微服务架构中，服务是细粒度的，协议是轻量级的。在 Java 中，有多个框架。在本章中，我们将介绍 Java/Jakarta EE 方面，并讨论 Eclipse MicroProfile。

Eclipse MicroProfile 计划的目标是`为微服务架构优化企业级 Java`。它基于 `Jakarta EE` API 的子集，因此我们可以像构建 Jakarta EE 应用一样构建 MicroProfile 应用。

MicroProfiles 定义了构建微服务的标准 API，并跨多个 MicroProfile 运行时交付可移植的应用程序。

## Eclipse MicroProfile 骨架

微服务是一种软件架构，系统是多个独立服务的集合。每个服务都有特定的业务重点，并使用与语言无关的协议（如 REST）与其他服务进行通信。Eclipse MicroProfile 计划为微服务架构优化企业级 Java。它基于 `Jakarta EE` API 的子集。第一个 MicroProfile 版本基于三个现有的 Jakarta EE 技术：`JAX-RS`、`CDI` 和 `JSON-P`。

新的技术在此基础上创建，以允许 Eclipse MicroProfile 和 Jakarta EE 技术之间轻松集成，这主要归功于 `CDI`，它是所有规范的胶水。来自 Eclipse MicroProfile 的新技术具有将版本作为 Jakarta EE 发布的流程；因此，两者都基于同一个规范以避免供应商锁定，并且在每次发布时，组件必须具有 API 和一个 `TCK`。

除了前面提到的三个基本规范外，Eclipse MicroProfile 在你的开发过程中还创建了以下规范：

![](img/5-1.jpg)

**图 5.1**

Eclipse MicroProfile 有多个组件，如下所示：

- `MicroProfile OpenTracing` 规范定义了在你的 `JAX-RS` 应用中访问符合 OpenTracing 标准的 `Tracer` 对象的行为和 API。这些行为规定了传入和传出的请求如何自动创建 OpenTracing Spans。API 定义了如何显式禁用或启用特定端点的跟踪。
- `Eclipse MicroProfile OpenAPI`：该 MicroProfile 规范旨在为 `OpenAPI v3` 规范提供统一的 Java API，所有应用程序开发者可以使用它来暴露其 API 文档。
- `MicroProfile Rest Client` 提供了一种通过 HTTP 调用 RESTful 服务的类型安全方法。尽可能地，MP Rest Client 尝试使用 `JAX-RS 2.0` API 以保持一致性和易于重用。
- `Eclipse MicroProfile Config`：Eclipse MicroProfile Config 是一个从应用程序中外部化配置解决方案。
- `Eclipse MicroProfile Fault Tolerance` 提供了一个简单灵活的构建容错微服务的解决方案，易于使用且可配置。
- `Eclipse Microprofile Metrics`：该规范旨在为 Microprofile 服务器提供一种统一的方法，向管理代理导出监控数据（遥测数据），并提供一种所有（应用程序）程序员都可以使用的用于暴露遥测数据的统一 Java API。
- `MP-JWT` 特性定义了基于 `JSON Web Token (JWT)` 的令牌身份验证和授权的互操作性和容器集成要求，用于 Java EE 风格的 RBAC 权限。它定义了基于 `java.security.Principal` 的扩展，用于表示 JWT 和关联声明，以及 `CDI` 注入注解类型和要求，以及与 `JAX-RS` 容器安全 API 的集成。
- `MicroProfile Health`：健康检查用于从另一台机器（例如 Kubernetes 服务控制器）探测计算节点的状态，主要目标是云基础设施环境，其中自动化过程维护计算节点的状态。

## 示例代码

我们将基于处理 IT 会议的背景创建一个微服务架构。为了管理会议，我们将拥有三个微服务：

- `Speaker`：演讲者服务，负责处理每个演讲者的姓名、简介和社交媒体链接。
- `Conference`：会议服务，与讲座合作，处理会议行程的名称、城市和年份。
- `Session`：会话服务，处理名称、标题、描述以及会议和演讲者信息。

## 数据库

每个数据库都有自己的提案、结构和特定行为，因此我们将根据每个服务使用不同的数据库。事实上，这就是微服务的优势；每个服务可以使用任何符合其要求的技术，而不会影响其他服务。每个微服务都为其特定用例使用适当的数据库：

|  |  |
| :--- | :--- |
| ![](img/5-1a.jpg) | `PostgreSQL`（也称为 `Postgres`）。免费开源的关系型数据库管理系统，强调扩展性和技术标准兼容性。它设计用于处理从单机到数据仓库或具有并发用户的 Web 服务的各种负载。 |
| ![](img/5-1b.jpg) | `MongoDB`。跨平台文档型数据库程序。被归类为 NoSQL 数据库，MongoDB 使用类 JSON 文档。 |
| ![](img/5-1c.jpg) | `Elasticsearch`。基于 `Lucene` 库的搜索引擎。Elasticsearch 提供了一个分布式的、多租户的全文检索引擎，具有 HTTP Web 界面和无模式 JSON 文档。Elasticsearch 使用 Java 开发。 |

**表 5.1**：Eclipse MicroProfile 实现

相对新的 MicroProfile 社区致力于为微服务架构优化企业级 Java 使命。目标是什么？一个跨多个运行时的可移植微服务应用程序平台。目前，IBM、Red Hat、Tomitribe、Payara、伦敦 Java 社区 (LJC) 和 SouJava 是该小组的领导者。

在此示例中使用这些组件：

|  |  |
| :--- | :--- |
| ![](img/5-1d.jpg) | `Thorntail` 提供了一种创新的打包和运行 Java EE 应用程序的方法，通过将它们与足够的服务器运行时打包，以便可以使用 `java -jar` 运行你的应用程序。 |
| ![](img/5-1e.jpg) | 体积小于 70MB，Payara Micro——容器化 Java EE (Jakarta EE)部署的首选开源轻量级中间件平台——微服务部署无需安装或配置，且无需重写代码。 |
| ![](img/5-1f.jpg) | KumuluzEE 使用 Java EE / Jakarta EE 技术开发微服务，并使用 Node.js、Go 等其他语言进行扩展。它将现有的 Java EE 应用迁移到微服务和云原生架构。 |
| ![](img/5-1g.jpg) | Apache TomEE 是 Eclipse MicroProfile 的变体，使用了多个 Apache 项目实现，包括 Apache Tomcat 和 Apache OpenWebBeans。 |

**表 5.2**

# 将技术整合在一起

![](img/5-2.jpg)

**图 5.2**

我们的项目有四个组件：

- **KumuluzEE** 将处理 Session 微服务。用户将搜索会话详情，例如查找关于 Eclipse Microprofile 或 Jakarta EE 的会。为了满足这一需求，项目将使用一种既是 NoSQL 又是强大搜索引擎的（是的，我们说的是 Elasticsearch）。
- **Thorntail** 将处理 Speaker 微服务，这是最简单的服务，用于管理演讲者信息。该服务将与 PostgreSQL 配合。
- **Payara Micro** 将处理 Conference 微服务。该服务与 KumuluzEE 和 Thorntail 强密相关。要创建一个会议，我们需要会话和演讲者。MongoDB 似乎可以轻松适配该服务，因为我们可以使用子文档（subdocuments）的概念将演示列表和演讲者列表放入 Conference 实体中，而不是像关系型数据库那样建立关联关系。
- **Apache TomEE** 是使用 HTML 5 作为前端的客户端浏览器。

Eclipse MicroProfile 的显著优势是什么？首先，它使用了基于 Jakarta EE 的标准，如 CDI、JAX-RS 和 JSON-P。

为了连接到 PostgreSQL 或任何关系型数据库，有一个 JPA 规范描述了在使用 Java 平台的应用程序中对关系型数据进行管理。为了与 NoSQL 数据库通信，我们将使用 Jakarta NoSQL 规范（目前还没有最终版本，但希望很快就会）。

在客户端，我们将使用带有 HTML 5 扩展的 Eclipse Krazo，并使用 Thymeleaf 作为模板引擎。目前，客户端还没有数据库；它只会与服务通信以组织值，然后在浏览器中显示它们。因此，它将使用 Eclipse MicroProfile Rest Client，该客户端提供了一种类型安全的方法来通过 HTTP 调用 RESTful 服务。

## 层、层、层层多的层

当我们谈论微服务时，应用程序中的层数始终是一个庞大的话题。层对于划分职责和编写整洁的代码至关重要，同时还可以保持遵循这种方法构建的许多模式，例如 MVC。

然而，大量的层也难以保持和维护；我们需要注意“延迟层”。否则，我们创建的不是 MVC，而是“洋葱模式”，你每次穿过一层时都会哭泣。并没有一个魔术公式可以确定你需要的层数。相反，它将取决于业务规则的复杂性，以及基础设施代码如何为我们提供最清晰的架构。

在我们的示例中，我们有三层：

- **实体 (entity)：** 业务的第一个实例，领域存在的地方。根据最佳实践，这些实体应该遵循丰富模型（rich model）。我们可以让这些实体与数据库无关，但这一次，让我们保持简单，使用与数据库高度耦合的实体。
- **数据传输对象 (DTO)：** 仅仅一个用于在控制器和实体之间传输值的空类。它最主要的目标是防止实体变成贫血模型（anemic model），因为某些框架可能需要 getter 和 setter 方法进行序列化，这通常意味着封装封装。
- **控制器 (controller)：** 视图和模型之间的桥梁。

```java
return Optional.ofNullable(entityManager.find(Speaker.class, id));

}

public List<Speaker> findAll() {

    String query = "select e from Speaker e";

    return entityManager.createQuery(query).getResultList();

}

}
```

我们有一个资源可以通过 HTTP 请求来暴露服务。我们在 DTO 上创建了一层，以避免封装性的丧失：

```java
import javax.enterprise.context.RequestScoped;
import javax.inject.Inject;
import javax.validation.Valid;
import javax.ws.rs.Consumes;
import javax.ws.rs.DELETE;
import javax.ws.rs.GET;
import javax.ws.rs.POST;
import javax.ws.rs.PUT;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.Produces;
import javax.ws.rs.WebApplicationException;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;

import java.util.List;
import java.util.Optional;
import java.util.stream.Collectors;

import static javax.ws.rs.core.Response.Status.NO_CONTENT;
import static javax.ws.rs.core.Response.status;

@Path("speakers")
@RequestScoped
@Produces(MediaType.APPLICATION_JSON + "; charset=UTF-8")
@Consumes(MediaType.APPLICATION_JSON + "; charset=UTF-8")
public class SpeakerResource {

    @Inject
    private SpeakerService speakerService;

    @GET
    public List<SpeakerDTO> findAll() {
        return speakerService.findAll().stream()
                .map(SpeakerDTO::of)
                .collect(Collectors.toList());
    }

    @GET
    @Path("{id}")
    public SpeakerDTO findById(@PathParam("id") Integer id) {
        final Optional<Speaker> conference = speakerService.find(id);

        return conference.map(SpeakerDTO::of)
                .orElseThrow(this::notFound);
    }

    @PUT
    @Path("{id}")
    public SpeakerDTO update(
            @PathParam("id") Integer id,
            @Valid SpeakerDTO speakerUpdated) {

        final Optional<Speaker> optional = speakerService.find(id);

        final Speaker speaker = optional.orElseThrow(() -> notFound());

        speaker.update(Speaker.of(speakerUpdated));
```



```java
speakerService.update(speaker);

return SpeakerDTO.of(speaker);

}

@DELETE

@Path("{id}")

public Response remove(@PathParam("id") Integer id) {

speakerService.delete(id);

return status(NO_CONTENT).build();

}

@POST

public SpeakerDTO insert(@Valid SpeakerDTO speaker) {

return SpeakerDTO.of(speakerService.insert(Speaker.of(speaker)));

}

private WebApplicationException notFound() {

return new WebApplicationException(Response.Status.NOT_FOUND);

}

}
```

## 会话服务

Session 服务将处理会议的内容，使用户可以找到与云和 Java 等主题相关的会话。该服务使用了结合 Jakarta NoSQL 和 KumuluzEE 的 Elasticsearch。

第一步是将 Elasticsearch 客户端对 CDI 可，正如我们在 Jakarta NoSQL 章节中提到的。Jakarta NoSQL 的参考实现与 Eclipse MicroProfile Config 有紧密集成。

`config` 属性由 `ConfigSources` 提供。`ConfigSources` 根据它们的序号（ordinal）进行排序，高值优先级高于低值。例如，在 Websphere Liberty 中，这意味着如果在 `server.env`（ordinal=300）和 `microprofile-config.properties`（ordinal=100）中设置了相同的 `config`，则将使用来自 `server.env` 的值。默认情况下有 3 个默认 `ConfigSources`：

- `System.getProperties()`（ordinal=400）
- `System.getenv()`（ordinal=300）
- ClassPath 上的所有 `META-INF/microprofile-config.properties` 文件（默认 ordinal=100，可以通过每个文件内部的 `config_ordinal` 属性单独配置）

默认值可以在应用内的 `microprofile-config.properties` 文件中指定，并且可以在后续每个部署中覆盖该值。较高的序号优于较低的：

```java
import jakarta.nosql.document.DocumentCollectionManager;
import org.eclipse.microprofile.config.inject.ConfigProperty;
import javax.enterprise.context.ApplicationScoped;
import javax.enterprise.inject.Disposes;
import javax.enterprise.inject.Produces;
import javax.inject.Inject;

@ApplicationScoped
public class ManagerConfig {

    @Inject
    @ConfigProperty(name = "document")
    private DocumentCollectionManager manager;

    @Produces
    public DocumentCollectionManager getManager() {
        return manager;
    }

    public void destroy(@Disposes DocumentCollectionManager manager) {
        manager.close();
    }

}
```

我们可以在文件中设置配置以使用实体如下：

```java
import jakarta.nosql.mapping.Column;
import jakarta.nosql.mapping.Entity;
import jakarta.nosql.mapping.Id;
import java.util.Objects;

@Entity
public class Session {

    @Id
    private String id;

    @Column
    private String name;

    @Column
    private String title;

    @Column
    private String description;

    @Column
    private Integer speaker;

}
```

为了定义 `Session` 实体，我们对每个字段使用了 `Column` 和 `Id` 注解。

为了定义 `Session` 仓库，我们有一个 `Repository` 及其特化：

```java
import jakarta.nosql.mapping.Repository;
import java.util.List;

public interface SessionRepository extends Repository<Session, String> {

    List<Session> findAll();

}
```

我们正在应用 Elasticsearch 将其作为搜索引擎。Jakarta NoSQL 的触点：

```java
import org.elasticsearch.index.query.QueryBuilder;
import org.elasticsearch.ElasticsearchTemplate;
import org.jnosql.util.StringUtils;
import javax.enterprise.context.RequestScoped;
import javax.inject.Inject;
import javax.validation.Valid;
import javax.ws.rs.Consumes;
import javax.ws.rs.DELETE;
import javax.ws.rs.GET;
import javax.ws.rs.POST;
import javax.ws.rs.PUT;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.Produces;
import javax.ws.rs.QueryParam;
import javax.ws.rs.WebApplicationException;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;
import java.util.Collections;
import java.util.List;
import java.util.Optional;
import java.util.UUID;
import java.util.logging.Logger;
import java.util.stream.Collectors;

import static javax.ws.rs.core.Response.Status.NO_CONTENT;
import static javax.ws.rs.core.Response.status;
import static org.elasticsearch.index.query.QueryBuilders.boolQuery;
import static org.elasticsearch.index.query.QueryBuilders.termQuery;

@Path("sessions")
@RequestScoped
@Produces(MediaType.APPLICATION_JSON + "; charset=UTF-8")
@Consumes(MediaType.APPLICATION_JSON + "; charset=UTF-8")
public class SessionResource {

    private static Logger LOGGER = Logger.getLogger(SessionResource.class.getName());

    @Inject
    private SessionRepository speakerRepository;

    @Inject
    private ElasticsearchTemplate template;

    @GET
    public List<SessionDTO> findAll(@QueryParam("search") String search) {

        LOGGER.info("searching with the field: " + search);

        if (StringUtils.isNotBlank(search)) {

            QueryBuilder queryBuilder = boolQuery()
                .should(termQuery("name", search))
                .should(termQuery("title", search))
                .should(termQuery("description", search));

            LOGGER.info("the query: " + queryBuilder);
        }

    }

}
```

```java
List<Session> sessions = template.search(queryBuilder, "Session");

LOGGER.info("the result: " + sessions);

return sessions.stream().map(SessionDTO::of).collect(Collectors.toList());

}

return speakerRepository.findAll().stream().map(SessionDTO::of).collect(Collectors.toList());

}

@GET

@Path("{id}")

public Session findById(@PathParam("id") String id) {

    final Optional<Session> conference = speakerRepository.findById(id);

    return conference.orElseThrow(this::notFound);

}

@PUT

@Path("{id}")

public SessionDTO update(@PathParam("id") String id, @Valid SessionDTO sessionUpdated) {

    final Optional<Session> optional = speakerRepository.findById(id);

    final Session session = optional.orElseThrow(() -> notFound());

    session.update(Session.of(sessionUpdated));

    speakerRepository.save(session);

    return SessionDTO.of(session);

}

@DELETE

@Path("{id}")

public Response remove(@PathParam("id") String id) {

    speakerRepository.deleteById(id);

    return status(NO_CONTENT).build();

}

@POST

public SessionDTO insert(@Valid SessionDTO session) {

    session.setId(UUID.randomUUID().toString());

    return SessionDTO.of(speakerRepository.save(Session.of(session)));

}

private WebApplicationException notFound() {

    return new WebApplicationException(Response.Status.NOT_FOUND);

}

}
```

## Conference service

Conference service 服务是所有服务中连接最紧密的一个，因为它需要维护来自演讲者（speaker）和会议（session）服务的信息。它使用了 Payara Micro 和结合 Jakarta NoSQL 的 MongoDB。

作为会议服务，第一步是通过 CDI 提供 MongoDB 连接。正如我们之前做的那样，我们将使用与 Eclipse MicroProfile Config 的集成：

```java
import jakarta.nosql.document.DocumentCollectionManager;
import org.eclipse.microprofile.config.inject.ConfigProperty;
import javax.enterprise.context.ApplicationScoped;
import javax.enterprise.inject.Disposes;
import javax.enterprise.inject.Produces;
import javax.inject.Inject;

@ApplicationScoped
public class MongoConfig {

    @Inject
    @ConfigProperty(name = "document")
    private DocumentCollectionManager manager;

    @Produces
    public DocumentCollectionManager getManager() {
        return manager;
    }

    public void destroy(@Disposes DocumentCollectionManager manager) {
        manager.close();
    }

}
```

让我们创建一个激活了本地环境的配置：

```properties
document=document
document.database=conferences
document.settings.jakarta.nosql.host=localhost:27017
document.provider=org.eclipse.jnosql.diana.mongodb.document.MongoDBDocumentConfiguration
```

```java
import jakarta.nosql.mapping.Column;
import jakarta.nosql.mapping.Convert;
import jakarta.nosql.mapping.Entity;
import jakarta.nosql.mapping.Id;
import java.time.Year;
import java.util.Collections;
import java.util.List;
import java.util.Objects;
import java.util.Optional;
import java.util.stream.Collectors;

@Entity
public class Conference {

    @Id
    @Convert(ObjectIdConverter.class)
    private String id;

    @Column
    private String name;

    @Column
    private String city;

    @Column
    private String link;

    @Column
    @Convert(YearConverter.class)
    private Year year;

    @Column
    private List<Speaker> speakers;

    @Column
    private List<Session> sessions;

}

@Entity
public class Session {

    @Column
    private String id;

    @Column
    private String name;

}

@Entity
public class Speaker {

    @Column
```



```java
private Integer id;

@Column

private String name;

}
```

MongoDB 的优势之一是我们可以使用子文档（subdocument）而不是创建关系。因此，我们可以嵌入 `Speaker` 和 `Session`，而不是执行连接（joins）。注意，`Speaker` 和 `Session` 实体包含了名称和 ID 等简要信息：

```java
import jakarta.nosql.mapping.Repository;

import java.util.List;

public interface ConferenceRepository extends Repository<Conference, String> {

    List<Conference> findAll();

}
```

```java
import javax.enterprise.context.RequestScoped;
import javax.inject.Inject;
import javax.validation.Valid;
import javax.ws.rs.Consumes;
import javax.ws.rs.DELETE;
import javax.ws.rs.GET;
import javax.ws.rs.POST;
import javax.ws.rs.PUT;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.Produces;
import javax.ws.rs.Response;

import java.util.List;
import java.util.Optional;
import java.util.stream.Collectors;

@RequestScoped
@Path("conferences")
public class ConferenceResource {

    @Inject
    ConferenceRepository conferenceRepository;

    @GET
    public List<ConferenceDTO> findAll() {
        return conferenceRepository.findAll().stream().map(ConferenceDTO::of).collect(Collectors.toList());
    }

    @GET
    @Path("{id}")
    public ConferenceDTO findById(@PathParam("id") String id) {
        final Optional<Conference> conference = conferenceRepository.findById(id);
        return conference.orElseThrow(this::notFound);
    }

    @PUT
    @Path("{id}")
    public ConferenceDTO update(@PathParam("id") String id, @Valid ConferenceDTO sessionUpdated) {
        final Optional<Conference> optional = conferenceRepository.findById(id);
        final Conference session = optional.orElseThrow(() -> notFound());

        session.update(Conference.of(sessionUpdated));
        conferenceRepository.save(session);

        return ConferenceDTO.of(session);
    }

    @DELETE
    @Path("{id}")
    public Response remove(@PathParam("id") String id) {
        conferenceRepository.deleteById(id);
        return status(NO_CONTENT).build();
    }

    @POST
    public ConferenceDTO insert(@Valid ConferenceDTO session) {
        session.setId(UUID.randomUUID().toString());
        return ConferenceDTO.of(conferenceRepository.save(Conference.of(session)));
    }

    private WebApplicationException notFound() {
        return new WebApplicationException(Response.Status.NOT_FOUND);
    }

}
```

为了确保服务已运行，我们执行了 Eclipse Microprofile 健康检查，这样我们就可以评估 HTTP 状态和以毫秒为单位的响应时间：

```java
import org.eclipse.microprofile.health.HealthCheck;
import org.eclipse.microprofile.health.HealthCheckResponse;

import javax.ws.rs.client.Client;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;

abstract class AbstractHealthCheck implements HealthCheck {

    abstract Client getClient();

    abstract String getUrl();

    abstract String getServiceName();

    @Override
    public HealthCheckResponse call() {
        try {
            long start = System.currentTimeMillis();

            Response response = getClient()
                .target(getUrl())
                .request(MediaType.TEXT_PLAIN_TYPE)
                .get();

            long end = System.currentTimeMillis() - start;

            return HealthCheckResponse.named(getServiceName())
                .withData("service", "available")
                .withData("time millis", end)
                .withData("status", response.getStatus())
                .withData("status", response.getStatusInfo().toEnum().toString())
                .up()
                .build();

        } catch (Exception exp) {
            return HealthCheckResponse.named(getServiceName())
                .withData("services", "not available")
                .down()
                .build();
        }
    }

}

@Health
@ApplicationScoped
class ConferenceHealthCheck extends AbstractHealthCheck {

    @Inject
    @ConfigProperty(name = "org.client.ConferenceService/rest/url")
    private String url;

    private Client client;

    @PostConstruct
    public void init() {
        this.client = ClientBuilder.newClient();
    }

    @Override
    Client getClient() {
        return client;
    }

    @Override
    String getUrl() {
        return url;
    }

    @Override
    String getServiceName() {
        return "Conference Service";
    }

}

@Health
@ApplicationScoped
class SessionHealthCheck extends AbstractHealthCheck {

    @Inject
    @ConfigProperty(name = "org.client.SessionService/rest/url")
    private String url;

    private Client client;

    @PostConstruct
    public void init() {
        this.client = ClientBuilder.newClient();
    }

    @Override
    Client getClient() {
        return client;
    }

    @Override
    String getUrl() {
        return url;
    }

    @Override
    String getServiceName() {
        return "Session Service";
    }

}

@Health
@ApplicationScoped
class SpeakerHealthCheck extends AbstractHealthCheck {

    @Inject
    @ConfigProperty(name = "org.client.SpeakerService/rest/url")
    private String url;

    private Client client;

    @PostConstruct
    public void init() {
        this.client = ClientBuilder.newClient();
    }

    @Override
    Client getClient() {
        return client;
    }

    @Override
    String getUrl() {
        return url;
    }

    @Override
    String getServiceName() {
        return "Speaker Service";
    }

}
```

我们可以在 `https://server_ip/health` 状态：

```json
{
  "checks": [
    {
      "data": {
        "time millis": 11,
        "service": "available",
        "status": "200"
      },
      "name": "Speaker Service",
      "state": "UP"
    },
    {
      "data": {
        "time millis": 11,
        "service": "available",
        "status": "200"
      },
      "name": "Conference Service",
      "state": "UP"
    },
    {
      "data": {
        "time millis": 10,
        "service": "available",
        "status": "200"
      },
      "name": "Session Service",
      "state": "UP"
    }
  ],
  "outcome": "UP",
  "status": "UP"
}
```

一旦服务和健康检查就绪，让我们进入控制器。Krazo 是基于 JAX-RS 构建的 API。因此，任何 Jakarta EE 开发者在创建 `Controller` 类时都会感到如鱼得水：

```java
import org.eclipse.microprofile.rest.client.inject.RestClient;
import org.client.session.SessionService;
import org.client.speaker.SpeakerService;

import javax.inject.Inject;
import javax.mvc.Controller;
import javax.mvc.Models;
import javax.mvc.View;
import javax.ws.rs.BeanParam;
import javax.ws.rs.GET;
import javax.ws.rs.POST;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;

import java.util.Optional;

@Controller
@Path("conference")
public class ConferenceController {

    @Inject
    private Models models;

    @Inject
    @RestClient
    private SessionService sessionService;

    @Inject
    @RestClient
    private ConferenceService conferenceService;

    @Inject
    @RestClient
    private SpeakerService speakerService;

    @GET
    @View("conference.html")
    public void home() {
        this.models.put("conferences", conferenceService.findAll());
    }

    @Path("add")
    @GET
    @View("conference-add.html")
    public void add() {
        this.models.put("conference", new Conference());
        this.models.put("speakers", speakerService.findAll());
        this.models.put("presentations", sessionService.findAll());
    }

    @Path("delete/{id}")
    @GET
    @View("conference.html")
    public void delete(@PathParam("id") String id) {
        conferenceService.remove(id);
        this.models.put("conferences", conferenceService.findAll());
    }

    @Path("edit/{id}")
    @GET
    @View("conference-add.html")
    public void edit(@PathParam("id") String id) {
        final Conference conference = Optional.ofNullable(conferenceService.findById(id))
            .orElse(new Conference());

        this.models.put("conference", conference);
    }

}
```

```java
this.models.put("speakers", speakerService.findAll());
```



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。this.models.put("presentations", sessionService.findAll());

}

@Path("add")

@POST

@View("conference.html")

public void add(@BeanParam Conference conference) {

    conference.update(speakerService, sessionService);

    if (conference.isIdEmpty()) {

        conferenceService.insert(conference);

    } else {

        conferenceService.update(conference.getId(), conference);

    }

    this.models.put("conferences", conferenceService.findAll());

}

}
```

HTML5 资源和替换在 Thymeleaf 中实现：

```html
<!DOCTYPE html>

<html xmlns:th="http://www.thymeleaf.org">

<head>

<title>拉丁美洲会议 (会议)</title>

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link rel="stylesheet" href="/css/bootstrap.min.css">

<meta charset="UTF-8">

</head>

<body>

<div class="container">

<h1>会议</h1>

<form th:action="@{/conference/add}" method="post" accept-charset="UTF-8">

<input id="id" name="id" type="hidden" th:value="${conference.id}">

<div class="form-group">

<label for="conferenceName">名称</label>

<input type="text" class="form-control" th:value="${conference.name}" name="name" id="conferenceName" placeholder="输入会议名称" required>

</div>

<div class="form-group">

<label for="conferenceCity">城市</label>

<input type="text" class="form-control" th:value="${conference.city}" name="city" id="conferenceCity" placeholder="输入会议城市" required>

</div>

<div class="form-group">

<label for="conferenceLink">链接</label>

<input type="url" class="form-control" th:value="${conference.link}" name="link" id="conferenceLink" placeholder="输入会议链接" required>

</div>

<div class="form-group">

<label for="conferenceYear">年份</label>

<input type="number" class="form-control" th:value="${conference.year}" name="year" id="conferenceYear" placeholder="输入会议年份" required>

</div>

<div class="form-group">

<label for="conferenceSpeakers">演讲者</label>

<select class="form-control" id="conferenceSpeakers" th:value="${conference.speakersIds}" name="speakers" multiple>

<tr th:each="speaker : ${speakers}">

<option th:value="${speaker.id}" th:text="${speaker.name}" th:selected="${conference.speakersIds.contains(speaker.id)}"></option>

</tr

</select>

</div>

<div class="form-group">

<label for="conferenceSessions">课程</label>

<select class="form-control" id="conferenceSessions" th:value="${conference.sessionsIds}" name="presentations" multiple>

<tr th:each="presentation : ${presentations}">

<option th:value="${presentation.id}" th:text="${presentation.name}" th:selected="${conference.sessionsIds.contains(presentation.id)}"></option>

</tr

</select>

</div>

<button type="submit" class="btn">保存</button>

</form>

</div>

<script src="https://code.jquery.com/jquery.js"></script>

<script src="/js/bootstrap.min.js"></script>

</body>

</html>
```

## 结论

通过 `Eclipse MicroProfile`，可以使现代应用程序准备好用于微服务架构。它具有许多功能，可以缓解此类结构中可能发生的大问题。一个重要的一点是它们与 `Jakarta EE` 技术的集成，也就是说，可以快速且安静地使用 `JPA` 或 `Jakarta NoSQL` 等规范。在不遥远的未来可能还会推出几个功能，例如与 `GraphQL` 的集成以及响应式编程 API。优秀的一点是，所有这些功能都是开源的，并为社区透明实现，亲爱的读者，你可以在其中做出贡献。

## 问题

1. 什么是 `Eclipse MicroProfile`？
2. 什么是 `DTO`？

# 第 6 章：Java Server Faces

## 引言

本章将介绍 Java Server Faces 规范以及如 `Primefaces` 等框架的使用，这些框架有助于在 Java 企业版/Jakarta EE 应用中使用组件。

## 结构

* Java Server Faces 简介
* Java Server Faces 2.3
* 框架
  * Primefaces
  * Bootsfaces
  * Omnifaces
  * Jmoordbjsf
* 演示示例
  * 模型 (Model)
  * 视图 (View)
  * 控制器 (Controller)
* Jmoordbjsf 示例
  * Docker
  * nbmongo 插件
  * 仓库 (Repository)
  * 资源 (Resources)
* JsfClient
  * 实体 (Entity)
  * 服务 (Services)
  * 转换器 (Converter)
  * 数据模型 (Datamodel)
  * 国际化 (Internalization)
  * 登录 (Login)
  * 自动完成 (Autocomplete)
* Primefaces Selenium
* 结论

## 目标

本章是 Java Server Faces 的介绍，它是今天最流行的 Java Web 框架之一。目标是让你能够使用该规范轻松地开发 Web 应用。

## Java Server Faces 简介

Java Web 应用的发展始于 `Servlets`。这些 API 是许多 Java Web 技术的核心。多年来，创建了 `Java Server Pages`，允许 HTML 代码与 Java 代码混合以与 `HTTP` 协议交互。随后诞生了 `Java Server Faces` 规范，它提供了一个面向组件的 MVC 框架。

JSF 提供的某些功能包括：

* 大量的组件
* 与规范集成
* 支持 HTML5
* 转换器 (Converters)
* 事件与监听器 (Listeners)
* 验证器 (Validators)
* Facelets
* 支持 Ajax

几年前，`Mojarra` 还是参考规范。现在它是 `Jakarta EE` 的一部分，已重命名为 `Jakarta Faces`。新规范的官方网站为 [`jakarta.ee/specifications/faces/2.3/`](https://jakarta.ee/specifications/faces/2.3/)，将在后续介绍。

## Java Server Faces 2.3

Java Server Faces 的最新版本 ([`javaserverfaces.github.io/`](https://javaserverfaces.github.io/)) 提供了许多上面提到的功能：

* CDI 对齐
  * JSF 产品的注入和 EL 解析
  * 更多 JSF 产品的注入
* WebSocket 集成
  * Ajax 方法调用
* 转换/验证
  * 类级验证
  * `f:convertDateTime` 对 JDK 8 时间的支持
* Java API
  * `UIData` 和 `UIRepeat` 对 `Iterable` 接口的支持
  * `UIData` 和 `UIRepeat` 对 `Map` 接口的支持
* 组件
  * 组件搜索表达式框架
  * 可自由放置的单选按钮
* 视图与资源
  * 对精确映射的基本支持（无扩展名 URL）
  * 获取视图资源列表

## 框架

Java Server Faces 优势之一是可以创建一个扩展组件或创建新组件的框架。常用的框架有：

* Primefaces
* Bootsfaces
* Omnifaces

还将展示一个与 `jmoordb` 集成的框架。

* Jmoordbjsf

### Primefaces

它提供了超过 100 个即插用的组件。它极大地简化了用户界面的开发：

![](img/6-1.jpg)

**图 6.1**

### Bootsfaces

它支持许多组件，可以与 Primefaces 的组件混合，最重要的是与 Bootstrap 集成得非常好。

### Omnifaces

它是一个非视觉实用工具库，有助于 Java Server Faces 的复杂任务。

### Jmoordbjsf

它是一个 Java Server Face 库，实现了许多适配于 `jmoordb` 使用的 Primefaces 和 Bootsfaces 组件。

在接下来的章节中，将开发两个示例来演示 Java Server Faces 组件的最常见特性。

## 示例示例

在此示例中，你将创建一个 Java EE/Jakarta EE 应用，该应用使用某些组件来演示基于 `MVC (模型视图控制器)` Web 应用开发的便利性。

按照上述描述的步骤创建项目：

1. 打开 NetBeans IDE 并运行 `File | New Project`。

   然后在 Categories（类别）中选择 `Java With Maven`，并在 Projects（项目）中选择 `Web Application`，如下所示：

   ![](img/6-2.jpg)

   **图 6.2**

2. 输入项目名称 `demo`。在 `Server` 选项中保留 `<Not Server Selected>`，并在 `Java EE Version` 中选择 `Java EE 8 Web`，如下截图所示：

   ![](img/6-3.jpg)

   **图 6.3**

3. 在 `Project Properties`（项目属性）中选择 `Java Server Faces` 框架，并在 `Components`（组件）中选择 `Primefaces`。如下截图所示，还要检查 Java 版本和其他项目属性：

   ![](img/6-4.jpg)

   **图 6.4**

4. 编辑 `pom.xml` 文件并将 primefaces 版本更新为 `8.0`，同时添加 `jmoordbutils`。在代码仓库中，你可以看到整个项目：

```xml
<dependency>

  <groupId>org.primefaces</groupId>

  <artifactId>primefaces</artifactId>

  <version>8.0</version>

</dependency>

<dependency>

  <groupId>org.projectlombok</groupId>

  <artifactId>lombok</artifactId>

  <version>1.18.6</version>

</dependency>

<dependency>

  <groupId>com.github.avbravo</groupId>

  <artifactId>jmoordbutils</artifactId>

  <version>0.84</version>

</dependency>
```

## 模型

实体将定义通过控制器与视图关联的模型。在我们的示例中，这些是简单的 Java 类。让我们创建一个包含以下数据的 `Person` 类：

```java
public class Person {

  private String name;

  public Person() {

  }

  //Setters/Gettters

}
```

## 视图

视图由 Java Server Faces 组件表示，这些组件在 Web 浏览器中渲染为 HTML 页面。Primefaces 有超过 100 个组件，例如，你将使用这些：

* InputText
* Label
* CommandButton
* Panel grid
* Datatable
* Calendar

Primefaces 不需要配置，只需在项目中添加依赖项即可使用：

```xml
<dependency>

  <groupId>org.primefaces</groupId>

  <artifactId>primefaces</artifactId>

  <version>8.0</version>

</dependency>
```

在每个页面的命名空间中添加以通过 `<p>` 使用组件：

`xmlns:p="http://primefaces.org/ui"`

要绘制日历，只需添加组件 `<p:calendar/>`：

```xml
<p:calendar id="inline" mode="inline" />
```

这将在客户端渲染，如下截图所示：

![](img/6-5.jpg)

**图 6.5**

将使用一些组件，例如带有标签的面板、文本框和按钮，该按钮将名称插入到显示在 datatable 中的列表中。将使用双列的 panelGrid：

```xml
<p:panelGrid columns="2">

  <p:outputLabel value="name"/>

  <p:inputText value="#{personController.name}"/>

  <f:facet name="footer">

    <p:commandButton value="Insert" action="#{personController.save()}" update=":form:growl, :form:datatable"/>

  </f:facet>

</p:panelGrid>
```

`datatable` 将有一个按钮，用于显示带有所选元素的对话框。如你所见，它与 `List<Person>` 关联，该列表将在控制器中定义：

```xml
<p:dataTable var="item" value="#{personController.personList}" id="datatable">

  <p:column headerText="name">

    <p:outputLabel value="#{item.name}"/>

  </p:column>

  <p:column headerText="">

    <p:commandButton action="#{personController.show}" update=":form:outputPanelPerson, :form:growl" oncomplete="PF('personDialog').show()" icon="fa fa-print" >

      <f:setPropertyActionListener value="#{item}" target="#{personController.personSelected}" />

    </p:commandButton>

  </p:column>

</p:dataTable>
```



它将生成一个如下所示的视图：

![](img/6-6.jpg)

**图 6.6**

要生成对话框，请使用`<p:dialog>`组件并在内部添加你需要的组件：

```xml
<p:dialog header="Person" widgetVar="personDialog" modal="true" showEffect="fade" hideEffect="fade">

  <!-- components go here -->

</p:dialog>
```

# 恢复 MongoDB 数据库

恢复 MongoDB 数据库，我们有多种方法，包括：

1. 使用 MongoDB 客户端提供的`mongorestore`进行恢复。
2. 在`docker-compose`文件中指定。

使用适用于 Apache NetBeans IDE 的某些插件，例如：

- 使用`nbmongo`插件。
- 使用`jmoordbbackup`（[`plugins.netbeans.org/plugin/75520/jmoordbbackup`](http://plugins.netbeans.org/plugin/75520/jmoordbbackup)）。

作为一个示例，我们将使用适用于 Apache NetBeans IDE 的`nbmongo`插件。

## nbmongo 插件

如果你使用 NetBeans IDE，可以使用`nbmongo`插件，下载地址见以下链接：[`plugins.netbeans.org/plugin/52638/nbmongo`](http://plugins.netbeans.org/plugin/52638/nbmongo)。下载后你将获得一个`.nbm`文件：

![](img/6-12.jpg)

**图 6.12**

这通过`Tools | Plugins | Download`菜单进行安装：

![](img/6-13.jpg)

**图 6.13**

然后点击`Add Plugins…`按钮，找到`.nbm`文件并继续安装过程。最后，你可以在`Services MongoDB`标签页中找到已安装的插件。

右键点击选择`New Connection`，并在描述中输入`docker connection`：

![](img/6-14.jpg)

**图 6.14**

一旦建立了连接，右键点击连接并选择`Create database`，我们输入名称`jsfdata`：

![](img/6-15.jpg)

**图 6.15**

项目在仓库中有两个 JSON 文件，即`profiles.json`和`user.json`。以下是`user.json`文件：

```json
{"_id" : {"$oid" : "5e8d4700bbb26a0d745d890e"}, "username" : "demo", "password" : "3gmNUqygQ/aVZ3HK0qIi1A==", "name" : "Demo User", "userInfo" : [{"iduserinfo" : "9f8f3db8-3fe8-43be-a372-898c1d99d02a", "username" : "avbravo", "datetime" : {"$date" : 1571756460834}, "description" : "update"}], "active" : "yes", "profile" : [{"idprofile" : "ADMIN"}]}
```

以下是`profile.json`文件：

```json
{"_id" : {"$oid" : "5e8d45d8bbb26a0d745d890d"}, "idprofile" : "ADMIN", "profile" : "Admin", "userInfo" : [{"iduserinfo" : "e9f251e9-169c-460d-8121-29a4315dde35", "username" : "demo", "datetime" : {"$date" : 1583615123746}, "description" : "update"}, {"iduserinfo" : "63c7156c-a8c8-41f5-bab4-0f92665d6220", "username" : "demo", "datetime" : {"$date" : 1583615123747}, "description" : "update"}], "active" : "si"}
```

我们将执行数据导入，此过程可以通过多种方式完成，示例展示了如何通过插件进行。

要执行此操作，右键点击`jsfdata`数据库并从下拉菜单中选择`Import`：

![](img/6-16.jpg)

**图 6.16**

选择`profile.json`文件并根据提示操作：

![](img/6-17.jpg)

**图 6.17**

对`user.json`文件重复相同的过程，最后数据库中将显示两个集合：

![](img/6-18.jpg)

**图 6.18**

下一步你将需要从你喜爱的 IDE 创建 Web 应用程序，我们将使用 NetBeans IDE。按照上述步骤创建项目：

1. 打开 NetBeans IDE 并运行`File | New Project`。然后从`Categories`中选择`Java With Maven`，并在`Projects`中选择`Web Application`，如下截图所示：

   ![](img/6-19.jpg)

   **图 6.19**

2. 输入项目名称`jsfmicroservices`并按下`Next`按钮，如下截图所示：

   ![](img/6-20.jpg)

   **图 6.20**

3. 在`Server`选项中保留`<Not Server Selected>`，在`Java EE Version`中选择`Java EE 8 Web`，如下截图所示：

   ![](img/6-21.jpg)

   **图 6.21**

4. IDE 生成 Web 项目，然后在 NetBeans 菜单中选择`File | New`，在`Categories`中选择`Payara`，选择`Maven Project`：

   ![](img/6-22.jpg)

   **图 6.22**

5. 在下一个屏幕上，选择你需要的`Payara`版本：

   ![](img/6-23.jpg)

   **图 6.23**

6. 完成后，在`pom.xml`文件中添加依赖：

```xml
<dependencies>
    <dependency>
      <groupId>org.payara</groupId>
      <artifactId>payara-micro-api</artifactId>
      <version>5.0</version>
    </dependency>

    <dependency>
      <groupId>org.payara</groupId>
      <artifactId>payara-flatfile-server</artifactId>
      <version>5.0</version>
    </dependency>

    <dependency>
      <groupId>org.eclipse.platform</groupId>
      <artifactId>javaee-api</artifactId>
      <scope>provided</scope>
    </dependency>

    <dependency>
      <groupId>org.eclipse.platform</groupId>
      <artifactId>glassfish-embedded</artifactId>
      <version>5.1.9</version>
      <scope>provided</scope>
    </dependency>
</dependencies>
```

```java
private List<Profile> profile;

private String active;

@Embedded

List<UserInfo> userInfo;

//Setters/Getters

}
```

## 仓库（Repository）

仓库模式（Repository pattern）定义了类如何与数据库进行交互。它的定义非常简单，是`jmoordb`中定义的仓库接口的扩展。在构造函数中，它通过两种方式被调用：

- 仅通过类名，将假设集合（collection）与类名相同。
- 通过定义数据库名称和集合。

创建类`ProfileRepository.java`：

```java
@Stateless
public class ProfileRepository extends Repository<Profile> {

    public ProfileRepository(){

        super(Profile.class,"jsfdata","profile");

    }

}
```

创建类`UserRepository.java`：

```java
@Stateless
public class UserRepository extends Repository<User> {

    public UserRepository(){

        super(User.class,"jsfdata","user");

    }

}
```

## 资源（Resources）

接下来，你将为资源`UserResources`和`ProfileResources`创建类，数据将通过 JAX-RS API 暴露，这一主题将在后续章节中扩展。

接下来的章节将解释安全策略，现在请编辑`web.xml`文件并添加将在应用程序中使用的角色。将使用 Jakarta Security API 进行验证：

```xml
<security-constraint>
  <web-resource-collection>
    <web-resource-name>Application pages</web-resource-name>
    <url-pattern>/faces/pages/*</url-pattern>
  </web-resource-collection>

  <auth-constraint>
    <role-name>admin</role-name>
    <role-name>testing</role-name>
  </auth-constraint>
</security-constraint>

<security-role>
  <role-name>admin</role-name>
</security-role>

<security-role>
  <role-name>testing</role-name>
</security-role>
```

然后创建类`UserResources.java`，注入仓库并设置安全措施，通过`@RolesAllowed({" "})`授权，通过`@Path("/")`指明`Path`。在接下来的章节中，我们将扩展关于使用微服务的主题。参考以下示例：

```java
@Path("user")
public class UserResources {

    @Inject
    UserRepository userRepository;

    @GET
    @RolesAllowed({"admin"})
    @Produces({MediaType.APPLICATION_XML, MediaType.APPLICATION_JSON})
    public List<User> get() {

        return userRepository.findAll();

    }

    @GET
    @Path("/findall")
    @RolesAllowed({"admin"})
    @Produces({MediaType.APPLICATION_XML, MediaType.APPLICATION_JSON})
    public List<User> findAll() {

        return userRepository.findAll();

    }

    @POST
    @Path("/add")
    @RolesAllowed({"admin"})
    @Consumes(MediaType.APPLICATION_JSON)
    public Response create(User user) {

        try {

            if (userRepository.update(user)) {

                return Response.status(201).entity("User saved").build();

            }

            return Response.status(400).entity("User could not be saved").build();

        } catch (Exception e) {

            return Response.status(400).entity("Error!!" + e.getLocalizedMessage()).build();

        }

    }

    @PUT
    @Path("/update")
    @RolesAllowed({"admin"})
    @Consumes(MediaType.APPLICATION_JSON)
    public Response update(User user) {

        try {

            if (userRepository.update(user)) {

                return Response.status(201).entity("Updated user").build();

            }

            return Response.status(400).entity("User was not updated").build();

        } catch (Exception e) {

            return Response.status(400).entity("Error!!" + e.getLocalizedMessage()).build();

        }

    }

    @GET
    @Path("/search/{username}")
    @RolesAllowed({"admin"})
    @Produces(MediaType.APPLICATION_JSON)
    public User findByUsername(@PathParam("username") String username) {

        User user = new User();

        try {

            user.setUsername(username);

            Optional<User> optional = userRepository.findById(user);

            if (!optional.isPresent()) {

                user = optional.get();

            }

        } catch (Exception e) {

            System.out.println("findByUsername() " + e.getLocalizedMessage());

        }

        return user;

    }

}
```

执行项目，你将得到类似下面的输出：

![](img/6-28.jpg)

**图 6.28**

如你所示，安全性是使用 Java EE Security API / Jakarta EE Security API 设置的。然后执行 Postman 查询以验证结果。将显示你没有权限访问微服务：

![](img/6-29.jpg)

**图 6.29**

我一直在开发一个名为`jmoordbjsf`的库，它集成了 Primefaces 组件以简化其使用。这些组件已经打包并准备好备用，且与`jmoordb`、`jmoordbutils`完美集成。将依赖添加到你的项目中：

```xml
<dependency>
  <groupId>com.github.avbravo</groupId>
  <artifactId>jmoordbjsf</artifactId>
  <version>0.47</version>
</dependency>
```

按照以下方式添加 JAX-RS 客户端以消费微服务：

```xml
<dependency>



```xml
<groupId>org.glassfish.jersey.core</groupId>
<artifactId>jersey-client</artifactId>
<version>2.25.1</version>
</dependency>

<dependency>
  <groupId>org.glassfish.jersey.media</groupId>
  <artifactId>jersey-media-json-jackson</artifactId>
  <version>2.25</version>
</dependency>
```

在`<repositories>`部分中，你需要包含以下仓库：

```xml
<repository>
  <id>jitpack.io</id>
  <url>https://jitpack.io</url>
</repository>
```

记得添加`<finalName>`来指定项目的根路径。

```xml
<finalName>jsfclient</finalName>
```

检查仓库中可用的代码，你可以在那里看到完整的`pom.xml`文件。Primefaces 提供了几个免费主题，有助于改善应用程序的外观，这些在下面的截图所示：

![](img/6-35.jpg)

**图 6.35**

## `web.xml`文件的配置

编辑`web.xml`文件并添加`omega`主题：

```xml
<context-param>
  <param-name>primefaces.THEME</param-name>
  <param-value>omega</param-value>
</context-param>
```

在源代码仓库中，你可以看到完整的内容。我们还使用 Java Security API 添加了安全设置，将在后续章节中进行解释。

## 实体（Entity）

完全按照另一个项目中的创建`User`和`Profile`两个类：

```java
public class User {

    @Id
    private String username;

    @Size(min = 10, max = 250)
    private String password;

    @Size(min = 8, max = 250)
    private String name;

    @Referenced(collection = "Profiles",
        field = "idprofile", javatype = "String", lazy = false,
        repository = "com.jsfmicroservices.repository.ProfileRepository")
    private List<Profile> profile;

    private String active;

    @Embedded
    List<UserInfo> userInfo;

    public User() {
    }
}
```

## 服务（Services）

为了与微服务通信，我们使用了多个客户端，Java 中常用的实现之一是 Jersey（JAX-RS）。因此，你将创建服务来消费上一个项目中提供的微服务。下面的图显示了应用程序通信的总方案：

![](img/6-36.jpg)

**图 6.36**

创建包含 JAX-RS 客户端的`UserServices`类。注意在示例中，使用了一个方法来消费所有可用资源。使用`Client`类来创建一个与微服务通信的客户端。同时注册`HttpAuthenticationFeature`，以指示你用于安全性的用户名和密码。通过`Webtarget`指定资源的路径。使用`GenericType<List<T>>`转换为指定的数据类型：

```java
@Stateless
public class UserServices implements Serializable {

    private static final String PASS = "pass";

    private static final String FAIL = "fail";

    private static final String SUCCESS_RESULT = "<result>success</result>";

    @Inject
    AuthentificationProducer authentificationProducer;

    // <editor-fold 适配="collapsed" desc="List<User> findAll()">
    public List<User> findAll() {

        List<User> userList = new ArrayList<>();

        try {
            Client client = ClientBuilder.newClient();

            client.register(authentificationProducer.httpAuthenticationFeature());

            WebTarget target = client.target("http://localhost:8080" + "/jsfmicroservices/resources/user/findall");

            GenericType<List<User>> data = new GenericType<List<User>>() {
            };

            userList = target.request(MediaType.APPLICATION_JSON).get(data);

        } catch (Exception e) {
            System.out.println("findAll()" + e.getLocalizedMessage());
        }

        return userList;
    }
    // </editor-fold>

    // <editor-fold 适配="collapsed" desc="Boolean add(User user)">
    public Boolean add(User user) {

        try {
            Client client = ClientBuilder.newClient();

            client.register(authentificationProducer.httpAuthenticationFeature());

            WebTarget webTarget = client.target("http://localhost:8080" + "/jsfmicroservices/resources/user/add");

            Invocation.Builder invocationBuilder = webTarget.request(MediaType.APPLICATION_JSON);

            // ... 添加逻辑

            return true;

        } catch (Exception e) {
            System.out.println("add()" + e.getLocalizedMessage());

            return false;
        }
    }
    // </editor-fold>

    // <editor-fold 适配="collapsed" desc="User findByUsername(String username)">
    public User findByUsername(String username) {

        User user = new User();

        try {
            Client client = ClientBuilder.newClient();

            client.register(authentificationProducer.httpAuthenticationFeature());

            user = client.target("http://localhost:8080" + "/jsfmicroservices/resources/user/search/")
                .path("/{username}")
                .resolveTemplate("username", username)
                .request(MediaType.APPLICATION_JSON)
                .get(User.class);

        } catch (Exception e) {
            System.out.println("findByUsername() " + e.getLocalizedMessage());
        }

        return user;
    }
}
```

## 转换器（Converter）

转换器的功能是将`String`转换为对象，反之亦然。Java Server Faces 没有直接的转换器，因此你必须自己制作。你可以使用`@FacesConverter("name")`注解并且类必须实现`Converter`接口。它们将用于某些组件，例如 autocomplete 和`selectOneMenu`。例如：

```java
@FacesConverter("userConverter")
public class UserConverter implements Converter {

    // ...
}
```

或者通过类声明以及以下代码行：

```java
@Named
@RequestScoped
public class UserConverter implements Converter {

    // ...
}
```

下面是`UserConverter.java`的代码，其中`getAsObject()`方法返回选中的对象，`getAsString()`方法返回键属性的`String`：

```java
@Named
@RequestScoped
public class UserConverter implements Converter {

    @Inject
    UserServices userServices;

    @Override
    public Object getAsObject(FacesContext facesContext, UIComponent uiComponent, String s) {

        User user = new User();

        try {
            if (!s.equals("null")) {
                user = userServices.findByUsername(s);
            }
        } catch (Exception e) {
            System.out.println("getAsObject() " + e.getLocalizedMessage());
        }

        return user;
    }

    @Override
    public String getAsString(FacesContext facesContext, UIComponent uiComponent, Object o) {

        String r = "";

        try {
            if (o instanceof User) {
                User user = (User) o;
                r = String.valueOf(user.getUsername());
            }
        }

        return r;
    }
}
```

```java
} else if (o instanceof String) {

    r = (String) o;

} catch (Exception e) {

    System.out.println("getAsString() " + e.getLocalizedMessage());

}

return r;

}

}
```

## 数据模型（Datamodel）

在使用`<p:datatable>`时，你可以有多种方式使用：直接使用`List<>`，或者通过`LazyDataModel`，或者我们在示例中使用的`DataModel`来更有效地管理对象列表。

`DataModel`允许我们与数据建立绑定，并允许我们处理选中的行。

让我们定义`getRowData(String rowkey)`方法，它将返回从对象列表中选中的对象。公共方法`getRowKey(Role role)`返回主键。如下方的代码所示：

```java
public class UserDataModel extends ListDataModel<User> implements SelectableDataModel<User> {

    public User Data Model() {
    }

    public UserDataModel(List<User> data) {
        super(data);
    }

    @Override
    public User getRowData(String rowKey) {

        List<User> list = (List<User>) getWrappedData();

        for (User user : list) {
            if (user.getUsername().equals(rowKey)) {
                return user;
            }
        }

        return null;
    }

    @Override
    public Object getRowKey(User user) {
        return user.getUsername();
    }
}
```

创建一个 JSF CDI Bean，注入`UserServices`并定义一个`List<User>`，在`init()`方法中调用`findAll()`方法，如下代码所示：

```java
@Named
@ViewScoped
@Getter
@Setter
public class UserController implements Serializable {

    private static final long serialVersionUID = 1L;

    @Inject
    UserServices userServices;

    List<User> userList = new ArrayList<>();

    public UserController() {
    }

    @PostConstruct
    public void init() {

        userList = userServices.findAll();

        for (User u : userList) {
            System.out.println("---> " + u.getName() + " profile " + u.getProfile().get(0));
        }
    }
}
```

编辑`index.xhtml`文件并添加与`userList`关联的面板和`datatable`。记住`Profiles`在 User 内部定义为`List<>`，因此将使用`repeat`来遍历每一条记录并显示`profile`属性的值：

```xml
<p:panel header="User">
    <p:dataTable value="#{userController.userList}" var="item">
        <p:column headerText="Username">
            <p:outputLabel value="#{item.username}"/>
        </p:column>

        <p:column headerText="Name">
            <p:outputLabel value="#{item.name}"/>
        </p:column>

        <p:column headerText="Profile">
            <p:repeat value="#{item.profile}" var="var">
```



```xml
<p:outputLabel value="#{var.profile}"/>
```

```xml
</p:repeat>
```

```xml
</p:column>
```

```xml
</p:dataTable>
```

```xml
</p:panel>
```

执行项目，将显示带有用户数据的`datatable`。这些数据是从微服务中消耗的：

![](img/6-37.jpg)

**图 6.37**

## 国际化（Internationalization）

多语言支持对于应用程序至关重要。Jmoordbutils 包含了项目中最常用标签的属性文件，例如消息、按钮和警告。

Jmoordbjsf 已经过优化，使用存储在`com.properties`包中的`messages.properties`文件。创建`com.properties`包并在其中生成`messages.properties`文件，如下截图所示：

![](img/6-38.jpg)

**图 6.38**

为了方便起见，按类别对标签进行分组，这样更容易使用，例如：

- 标签（label）
- 字段（field）
- 按钮（button）
- 警告（warning）
- 信息（info）
- 错误（error）
- 栏（menubar）
- 菜单（menu）
- 对话框（dialog）

你可以为属性文件添加新语言的支持。

![](img/6-39.jpg)

**图 6.39**

如下截图所示，选择你想要支持的语言：

![](img/6-40.jpg)

**图 6.40**

在存储库的项目中，你可以看到属性文件。然后选择或打开文件并选择`Add properties`选项，添加你需要的属性：

![](img/6-41.jpg)

**图 6.41**

在`xhtml`页面的`h:head`部分，添加以下行代码：

```xml
<h:head>
    <f:facet name="first">
        <f:view locale="#{jmoordbLanguajes.locale !=null?jmoordbLanguajes.locale:'es'}"></f:view>
        <f:loadBundle basename="com.properties.messages" var="messages" />
    </f:facet>
</h:head>
```

```java
public List<Profile> complete(@PathParam("query") String query) {
    List<Profile> suggestions = new ArrayList<>();

    try {
        query = query.trim();

        suggestions = profileRepository.findRegex("profile", query, true, new Document("profile", 1));
    } catch (Exception e) {
        System.out.println("complete() " + e.getLocalizedMessage());
    }

    return suggestions;
}
```

运行项目时，可用的端点为`GET /jsfmicroservices/resources/profile/autocomplete/{query}`。现在编辑`Jsfclient`项目中的`ProfileServices.java`文件并添加`complete`方法：

```java
public List<Profile> complete(String query) {
    List<Profile> suggestions = new ArrayList<>();

    try {
        Client client = ClientBuilder.newClient();

        client.register(authentificationProducer.httpAuthenticationFeature());

        suggestions = client
            .target("http://localhost:8080" + "/jsfmicroservices/resources/profile/autocomplete/")
            .path("/{query}")
            .resolveTemplate("query", query)
            .request(MediaType.APPLICATION_JSON)
            .get(new GenericType<List<Profile>>() {});
    } catch (Exception e) {
        System.out.println("complete() " + e.getLocalizedMessage());
    }

    return suggestions;
}
```

在我们的`.xhtml`页面定义自动补全时使用组件`<jmoordbjsf:autocomplete>`，你可以看到属性`completeMethod`指向`Service`中定义的`complete`方法，即执行搜索的字段。指定转换器、补全方法、`labeltips`的值、监听器和其他属性：

```xml
<jmoordbjsf:autocomplete converter="#{profileConverter}"
    completeMethod="#{userController.profileServices.complete}"
    labeltip1="#{msg['field.idprofile']} #{p.idprofile}"
    labeltip2="#{msg['field.profile']} #{p.profile}"
    listener="#{userController.handleAutocompleteOfListXhtml}"
    value="#{userController.profileSearch}"
    itemLabel="#{p.idprofile}"
    field="idprofile"
    dropdown="true"
    minQueryLength="0"
    update=":form"/>
```



执行它，我们将得到一个如下图所示的视图，用户输入一个术语，并显示满足该条件的 Profiles 列表：

![](img/6-45.jpg)

**图我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。6.45**

## Primefaces Selenium

为了测试组件，我们使用 `Selenium`、`Arquillian` 等框架。

`Primefaces Selenium` 项目是基于 `Primefaces Arquillian` 项目创建的。在此之前，Primefaces 组件很难用该框架进行测试。有关示例和文档，你可以访问他们的网站：

[`github.com/primefaces-extensions/primefaces-selenium/`](https://github.com/primefaces-extensions/primefaces-selenium/)

## 结论

本章通过非常简单的示例对 Java Server Faces 进行了非常基础的介绍。我们将基于 `Jmoordb Stack`、`Primefaces` 或 `BootsFaces` 的项目也拆分为微服务架构，这是一种以友好且快速的方式从 Java 创建 Web 应用程序的极佳工具。我们建议访问官方（`http://www.primefaces.org`）网站，在那里你可以找到许多组件使用的示例。

PrimeFaces 是创建 Web 应用程序的优秀工具。它是 JSF 规范最复杂的实现之一。我们还演示了下一代 JSF 框架 `Jmoorb jsf` 的使用。它结合了两个主要 JSF 实现（`PrimeFaces` 和 `OmniFaces`）的力量，并具有与 NoSQL 数据库通信的灵活性。

## 问题

1. 如何将 Primefaces 添加到你的项目中？
2. 如何将其与 Controller 关联？
3. 提到最常用的？

# 第 7 章：Vaadin

## 引言

Vaadin 是一个开源 Web 框架，帮助 Java 开发者以最小努力构建极佳的用户体验。本章将介绍其丰富的用户界面组件集。

## 结构

- Vaadin 简介
- Vaadin 架构
- Web 组件
- 表单输入
  - Label
  - 按钮
  - 复选框
  - 组合框
  - 文本字段
  - 文本区域
  - 日期选择器
  - 邮箱字段
  - 选择框
  - 数字字段
  - 密码字段
  - 单选按钮
  - 对话框
  - 网格
  - 表单布局
  - 应用布局
  - 折叠面板
  - 通知
  - 登录
  - 上传
  - 标签页
  - Lumo

## 目标

本章涵盖了这种创新的、现代且具有良好性能和适应性的 Java 框架。

## Vaadin 简介

什么是 Vaadin？它是一家拥有多年免费软件经验的芬兰公司，开发中心位于芬兰，并在德国和美国设有办事处，传统上一直是开发 Web 应用的框架。今天我们讨论的是 Vaadin14，它不仅仅是一个框架，更是一个完整的平台，通过组合完美简化 Web 应用的开发。所有这些组件都设计为适用于任何设备（即响应式），Vaadin 也为 PWA 等新技术做好了准备。

## Vaadin 架构

Vaadin 架构专注于改进用户界面与服务器之间的通信，让 Java 开发者更轻松地使用 `HTML`、`CSS` 和 `JavaScript` 等 Web 技术，以安全的服务端方式使用 Web 组件。让 Java 开发者完全访问所有现代 Web 增强功能。对于后端使用 `JavaScript` 的前端开发者来说，他们可以创建一个服务端 Java 应用程序并更轻松地访问后端，同时可以在那里实现客户端 TypeScript 视图。

根据我的工作经验，当我使用基于减法的服务时，总是面临维护复杂性或恢复应用程序通用状态以及在需要时网络通信协议的问题。通过健壮的 Java 后端将用户界面连接到数据，这是一个巨大的优势。

- **主题**：这些是可以通过 CSS 或 HTML 模板定义的默认主题选项。
- **应用服务器**：在此部分，你可以将用户界面逻辑中生成的相同主题、HTML 模板、组件和后端服务集成，并在通信中实现强大的响应能力。
- **后端**：它允许你使用来自虚拟机（也就是说后端）的组件。我们拥有彼此独立的 Web 组件，但通过后端，我们能够使用这些相同的组件，这使得 Vaadin 在这种架构中是独特的。换句话说，Vaadin 指的是虚拟机的服务器，因此从理论上讲，你能够使用任何执行在 JVM 上的语言（如 `Scala`、`groovy` 等）来构建 Web 应用。

另一方面，业务逻辑可以在与 UI 代码相同的 servlet 中执行，在某些情况下，数据存储分布在数据库管理系统或平面文件中。对于数据库，它是通过如 `JPA` 等持久化解决方案进行访问的，`JPA` 是一种将数据从面向对象语言的类型系统转换为数据库关系模型的技术，这被称为对象关系映射（`ORM`）。因此，你可以像部署任何其他 Java Web 应用程序一样部署 Vaadin 应用。例如，你可以将此类封装为标准 Java Web 应用程序的 WAR 文件的一部分，并部署到 Web 服务器（更准确地说是 `Servlet` 容器）如 `Tomcat`：

![](img/7-1.jpg)

**图 7.1**

## 表单输入

### 标签（Label）

`Label` 是与 Vaadin 相关的最简单的组件。通过 `Label`，你可以根据内容的模式在不同的格式或场景下显示文本，例如不可编辑文本、纯文本和 HTML 文本。

我们有一个默认占据 100% 宽度的容器，而标签将占据它所需的空间。正如图 7.2 所示：

![](img/7-2.jpg)

**图 7.2**

现在，我们可以从下方的截图看到 `Label` 示例的结果：

![](img/7-3.jpg)

**图 7.3**

### 按钮（Button）

我们将讨论另一个重要的组件——按钮。基本上，创建按钮非常简单，它的主要功能是启动某些操作，例如完成表单中的输入。`Button` 有一个方法允许你添加点击监听器，可以通过 `addClickListener()` 或 `onClick()` 方法添加点击监听器来处理。

如下方的截图所示，这是一个 `Button` 的示例：

![](img/7-4.jpg)

**图 7.4**

现在，我们可以从下方的截图看到 `Button` 示例的结果：

![](img/7-5.jpg)

**图 7.5**

### 复选框（CheckBox）

选项按钮（Option Button）与复选框（Checkbox）之间的唯一区别在于，同一个容器内可以选择多个选项。当复选框被激活时，可以通过 `setValue()` 方法确定写入 `Boolean` 属性的验证值，并通过 `getValue()` 方法获取。修改复选框的值会产生 `ValueChangeEvent`，它可以被 `ValueChangeListener` 使用。

如下方的截图所示，这是一个 `CheckBox` 的示例：

![](img/7-6.jpg)

**图 7.6**

现在，我们可以从下方的截图看到 `Checkbox` 示例的结果：

![](img/7-7.jpg)

**图 7.7**

### 组合框（ComboBox）

`ComboBox` 是一种选择组件，允许你从下拉列表中选择项目。这是最常见的下拉框，它显示项目列表。`ComboBox` 也会在你点击箭头之前隐藏列表。

![](img/7-8.jpg)

**图 7.8**

现在，我们可以从下方的截图看到 `ComboBox` 示例的结果：

![](img/7-9.jpg)

**图 7.9**

### 文本字段（Text Field）

`TextField` 是允许用户输入数据的组件。它广泛用于输入员工、客户、产品等数据。如下方的截图所示，这是一个 `TextField` 的示例：

![](img/7-10.jpg)

**图 7.10**

现在，我们可以从下方的截图看到 `TextField` 示例的结果：

![](img/7-11.jpg)

**图 7.11**

### 文本区域（TextArea）

`TextArea` 组件与 `TextField` 类似，区别在于它代表多行文本输入。它用于请求大量数据，如注释、备注、解释等。如下方的截图所示，这是一个示例：

![](img/7-12.jpg)

**图 7.12**

现在，我们可以从下方的截图看到 `TextArea` 示例的结果：

![](img/7-13.jpg)

**图 7.13**

### 日期选择器（Date Picker）

`Date Picker` 提供了一个带有可滚动日历的日期选择字段。它也可以自定义位置输入日期。如下方的截图所示，这是一个 `Date Picker` 的示例：

![](img/7-14.jpg)

**图 7.14**

现在，我们可以从下方的截图看到 `Date Picker` 示例的结果：

![](img/7-15.jpg)

**图 7.15**

### 邮箱字段（Email Field）

`Email Field` 提供了一种以简单方式在文本框中建立邮箱验证。如下方的截图所示，这是一个 `Email Field` 的示例：

![](img/7-16.jpg)

**图 7.16**

现在，我们可以从下方的截图看到 `Email Field` 示例的结果，观察到当输入正确的邮箱地址时，它是正常的；反之则会显示错误消息：

![](img/7-17.jpg)

**图 7.17**

### 选择框（Select）

`Select` 提供了一个带有自定义项的下拉选择框，该组件可以禁用或进入只读模式。如下方的截图所示，这是一个 `Select` 的示例：

![](img/7-18.jpg)

**图 7.18**

现在，我们可以从下方的截图看到 `Select` 示例的结果：

![](img/7-19.jpg)

**图 7.19**

### 数字字段（Number Field）

`Number Field` 提供了一种以简单方式在仅数字文本框中建立自动验证。如下方的截图所示，这是一个 `Number Field` 的示例：

![](img/7-20.jpg)

**图 7.20**

现在，我们可以从下面的截图看到 `Number Field` 示例的结果：

![](img/7-21.jpg)

**图 7.21**

### 密码字段（Password Field）

此 Web 组件仅支持单个字符。它用于隐藏在文本框中输入的数据。例如，如果你在应用程序中指定了一个文本框来输入密码，它将用星号（`**`）显示；如果应用程序要求不显示密码，你可以在属性 `setRevealButtonVisible(false)` 中进行指定。

如下所示是密码字段的一个示例：

![](img/7-23.jpg)

**图 7.23**

现在，我们可以从下面的截图看到密码字段示例的结果：

![](img/7-24.jpg)

**图 7.24**

### 单选按钮（Radio Button）

用于自定义单选按钮的 Web 组件，单选按钮显示了一个可以开启或关闭的选项。通常，单选按钮用于一组选项，显示用户只能从中选择一个的选项。选择组内带有标签的选项之一会通过一个黑点来激活该选项，表示该选项已被选中。

如下所示是单选按钮的一个示例：

![](img/7-25.jpg)

**图 7.25**

现在，我们可以从下面的截图看到单选按钮示例的结果：

![](img/7-26.jpg)

**图 7.26**

### 对话框（Dialog）

用于对话框的 Web 组件告知用户有关的任务，并可能包含信息，防止用户与底层页面进行交互。它是可访问的，并与屏幕阅读器配合，以确保所有用户都能使用你的应用程序。

如下所示是对话框的一个示例：

![](img/7-27.jpg)

**图 7.27**

现在，我们可以从下面的截图看到对话框示例的结果：

![](img/7-28.jpg)

**图 7.28**

我们点击“打开对话框（Open Dialog）”按钮来显示以下表单，如你在下面的截图所示，我们将有两个选项来确认或取消，此示例用于用户需要从购物篮中移除产品，或更新个人信息记录的应用程序中：

![](img/7-29.jpg)

**图 7.29**

对于此示例，点击确认按钮，它将显示如下所示的消息，如截图所示：

![](img/7-30.jpg)

**图 7.30**

### 网格（Grid）

网格的 Web 组件可以从任何数据源懒性加载数据、显示数据，并允许对对应记录和字段的一系列行列进行数据操作。此组件能够维护文本和/或图形。另一方面，它们可以处理存在的大数据，并在用户界面的单个组件中轻松滚动 10 万行数据。

如下所示是网格的一个示例：

![](img/7-31.jpg)

**图 7.31**

现在，我们可以从下面的截图看到网格示例的结果：

![](img/7-32.jpg)

**图 7.32**

### 表单布局（Form Layout）

表单布局的 Web 组件为表单元素提供了可配置的响应式设计。其主要功能之一是能够保护表单内容，使其在所有设备上都保持易读。另一方面，它能帮助程序员以最短的时间开发应用程序。

如下所示是表单布局的一个示例：

![](img/7-33.jpg)

**图 7.33**

现在，我们可以从下面的截图看到表单布局示例的结果：

![](img/7-34.jpg)

**图 7.34**

在接下来的图中，我们可以看到表单布局在移动设备上的显示方式：

![](img/7-35.jpg)

**图 7.35**

### 应用布局（App Layout）

应用布局提供了一种快速简便的方法来实现常见的应用程序设计结构。它允许对应用程序的设计，例如一个可以在顶部水平配置的菜单，反之，可以在侧边有一个垂直抽屉。这两个组件可以组合，形成一个带有应用标题栏的侧边菜单。另一方面，你还可以配置页面内容、图标、Logo 等。

优点之一是菜单会根据屏幕尺寸进行调整，因此在所有设备上使用都非常直观，就像原生应用程序一样。

如下所示是应用布局的一个示例：

![](img/7-36.jpg)

**图 7.36**

现在，我们可以从下面的截图看到应用布局示例的结果：

![](img/7-37.jpg)

**图 7.37**

### 菜单栏（Menu Bar）

向用户展示并在屏幕特定区域供选择的一组选项，这些被称为菜单。市场上开发的大多数应用程序都包含菜单，菜单中包含了实现应用程序实用性的所有必要工具。

正如图 7.39 所示，它类似于 Word、Excel、PowerPoint，包含了菜单，在这些栏中包含销售（Sales）、账单（Billing）等选项。菜单相对于其他控件的优势是它们占据的屏幕空间较少，但在某些情况下在菜单完全显示之前会受到限制。

如下所示是菜单栏的一个示例：

![](img/7-38.jpg)

**图 7.38**

现在，我们可以从下面的截图看到菜单栏示例的结果：

![](img/7-39.jpg)

**图 7.39**

### 折叠面板（Accordion）

折叠面板 Web 组件是一组可展开的面板，用于用户显示和隐藏内容，以便用户界面不那么拥挤。该组件在其他意义上由节点（nodes）和子节点（secondary nodes）组成。你可以显示主节点或包含子节点的展开或折叠节点。它与 Vaadin 家族中的另一个组件 `TreeGrid` 类似。

另一方面，折叠面板组件的优点之一可以在移动和桌面环境中良好地显示。因此，它支持键盘和屏幕阅读器。它还支持将在章节末解释的 `Lumo` 和 `Material` 主题。

如下所示是折叠面板的一个示例：

![](img/7-40.jpg)

**图 7.40**

现在，我们可以从下面的截图看到折叠面板示例的结果，如截图所示，我们看到此示例的折叠面板组件包含用户的个人信息和健康信息。在这张图中，你可以看到姓名和文档：

![](img/7-41.jpg)

**图 7.41**

继续相同的示例，在接下来的图中我们展开了用户的健康信息并向我们展示了 EPS 和提供服务的城市的数据：

![](img/7-42.jpg)

**图 7.42**

### 通知（Notification）

通知的 Web 组件用于显示一个出现在屏幕上的小面板，因此你可以自定义通知显示的位置和时间。通常，它总是设置为较短的时间并显示消息。

此示例使用了 `setDuration`，它指示了通知自动关闭需要多久。正如你在下面的截图所示，你必须以毫秒为单位指定时间，例如，如果你希望通知打开 5 秒，则传递值 `5000`。

现在，我们可以从下面的截图看到通知示例的结果。正如我们观察到的图，当我们点击 `Example Notification` 按钮时，它会自动向我们发送一条持续时间为 5 秒的消息：

![](img/7-44.jpg)

**图 7.44**

### 登录（Login）

有了一套用于登录表单的 Web 组件，并支持密码管理器。它包含对实体（如人员、车辆、计算机等）请求访问资源时的验证。该组件可以添加事件监听器，以便你为用户提供密码找回指令。另一方面，它可以在无需修改代码的情况下适应不同的语言和地区，换句话说，你可以通过 `i18n` 对应用程序进行国际化。

下面的截图是登录的一个示例：

![](img/7-45.jpg)

**图 7.45**

现在，我们可以从下面的截图看到登录示例的结果。在这里你可以看到两种场景，第一种情况是想要进入应用程序的人正确输入了用户名和密码。

在第二种情况下，如果输入的数据不正确，该组件将负责显示和隐藏错误消息，以便在登录尝试失败时向用户提供信息：

![](img/7-46.jpg)

**图 7.46**

### 上传（Upload）

Web 上传组件提供了许多专门功能，例如通过指示进度来上传多个文件、通过拖放方法上传文件。它允许你显示计算机中拥有的任何驱动器，此控件包括硬硬盘、软磁盘、CD-ROM 等。另一方面，它最有趣的属性是 `setAcceptedFileTypes`，它允许我们指定在该组件中显示什么类型的文件。如果你将属性 `setAcceptedFileTypes` 设置为字符串 `*.txt`，则表示只显示具有此扩展名的文件。可以通过正斜杠（`/`）分隔来显示多种文件类型。

如你所见，下面的截图是上传示例。我们将尝试上传一个 JPG 格式的文件：

![](img/67-47.jpg)

**图 7.47**

接下来，例如如下面的截图所示，使用了上传组件，我们点击 `Upload File…` 按钮来浏览系统驱动器并显示图像格式的文件：

![](img/7-48.jpg)

**图 7.48**

如你所见，在下面的截图中我们添加了一个 `JPG` 图像文件：

![](img/7-49.jpg)

**图 7.49**

### 标签页（Tabs）

标签页 Web 组件对于你了解一个经常困扰程序员的标签组件特性非常。那就是，标签页将内容组织成独立的视图，你每次只能看到一个视图。它不是一个容器，也就是说，它并不包含一个可以为每个选项放置元素的区域，而是是一组必须与网格和表单布局等组件关联的视图。因此，标签页可以同时进行水平和垂直配置，最后是标签。

如你所见，下面的截图是标签页的示例：

![](img/7-40.jpg)

**图 7.40**

现在，我们可以从下面的截图看到登录示例的结果。在这里你可以看到两种场景，第一种情况是想要进入应用程序的人正确输入了用户名和密码。

在第二种情况下，如果输入的数据不正确，该组件将负责显示和隐藏错误消息，以便在登录尝试失败时向用户提供信息：

![](img/7-41.jpg)

**图 7.41**

- **数据库：** `MongoDB` ([`www.mongodb.com/download-center`](https://www.mongodb.com/download-center), [`mongodb.github.io/mongo-java-driver/`](https://mongodb.github.io/mongo-java-driver/))
- **组件 Vaadin：** `Crud UI Add-on`

你对 Project Base 做了什么？这是一个现备用的项目，包含了配置、依赖和示例代码。要生成新的 Vaadin 项目，请访问以下链接：[`vaadin.com/start/v14`](https://vaadin.com/start/v14) 并如屏所示选择 Project Base 的技术栈选项：

![](img/8-2.jpg)

**图 8.2**

在 `Get Started` 中，我们选择了 `CDI` 和 `Java EE`，将 `Maven Group ID` 输入为 `com.book.bpb`，`Project Name` 为 `demo`。

点击 `Download` 并解压 `demo.zip` 文件。如果它未激活，你可能需要登录 Vaadin 平台。

## 打开项目

在喜好的 IDE 中导入生成的项目，在本次工作中，我们将使用如下屏所示的 IntelliJ IDEA：

![](img/8-3.jpg)

**图 8.3**

但可以使用任何其他 Java IDE。如果你更倾向于 Eclipse 或 NetBeans，请访问：

- [`vaadin.com/tutorials/import-maven-project-eclipse`](https://vaadin.com/tutorials/import-maven-project-eclipse)
- [`vaadin.com/learn/tutorials/import-maven-project-netbeans`](https://vaadin.com/learn/tutorials/import-maven-project-netbeans)

## 什么是 Maven？

Apache Maven 是一个软件项目管理工具。Maven 的基础是 `pom` 项目的对象模型。Maven 的目标是促进和统一软件开发过程。

`pom.xml` 文件的最小版本必须包含项目根、`modelVersion`、`groupId`、`artifactId` 和 `version`。

现在我们将可视化 `pom.xml` 文件的结构，我们必须为此项目添加哪些依赖，Jmoordbutils、Lombok、JDK 的配置以及 Vaadin 框架的版本，我们可以查看 `pom.xml` 文件。

以下代码源自 `pom.xml` 文件：

```xml



```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">

  <modelVersion>4.0.0</modelVersion>

  <groupId>com.book.bpb</groupId>
  <artifactId>demo</artifactId>
  <name>Demo</name>
  <version>1.0-SNAPSHOT</version>
  <packaging>war</packaging>

  <properties>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
    <failOnMissingWebXml>false</failOnMissingWebXml>

    <!-- Dependencies -->
    <vaadin.version>14.1.20</vaadin.version>
    <drivers.dir>${project.basedir}/drivers</drivers.dir>
    <drivers.downloader.phase>pre-integration-test</drivers.downloader.phase>
  </properties>

  <dependencies>
    <dependency>
      <groupId>com.vaadin</groupId>
      <artifactId>vaadin-cdi</artifactId>
    </dependency>

    <dependency>
      <groupId>javax</groupId>
      <artifactId>javaee-api</artifactId>
      <version>7.0</version>
      <scope>provided</scope>
    </dependency>

    <dependency>
      <groupId>org.mongodb</groupId>
      <artifactId>mongo-java-driver</artifactId>
      <version>3.4.2</version>
    </dependency>

    <dependency>
      <groupId>com.github.avbravo</groupId>
      <artifactId>jmoordbutils</artifactId>
      <version>0.84</version>
    </dependency>

    <!-- Added to provide logging output as Flow uses -->
    <!-- the unbound SLF4J no-operation (NOP) logger implementation -->
    <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-simple</artifactId>
    </dependency>

    <dependency>
      <groupId>com.vaadin</groupId>
      <artifactId>vaadin-testbench</artifactId>
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
```

## 项目结构

项目的结构包含了后端的包，以及子包 `Models`、`Repositories`、`Services` 和 `Implementations`；另一方面，我们还创建了 `UI` 包，其中包含 `application` 子包，如下屏所示：

![](img/figure_4.jpg)

**图 8.4**

我们添加了 `Web | frontend | styles` 文件夹来创建 `shared-styles.html` 文件，如下屏所示：

![](img/figure_5.jpg)

**图 8.5**

我们在 `shared-styles.html` 中添加了以下代码：

```html
<link rel="import" hrefbower_components/lumo-styles/color">
<link rel="import" hrefbower_components/lumo-styles/typography">

<dom-module id="view-styles">
  <template>
    <style>
      .view-toolbar {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      .view-container {
        display: flex;
        justify-content: center;
      }

      .view-nav {
        display: inline-flex;
        flex-direction: column;
        align-items: center;
        padding: 4px;
      }
    </style>
  </template>
</dom-module>
```

```css
<style>
  line-height: var(--lumo-line-height-s);
}

.confirm-text > * {
  margin-bottom: 0.6em;
}

.confirm-text div:not(:first-child) {
  color: var(--lumo-secondary-text-color);
  font-size: var(--lumo-font-size-s);
}
</style>
```

```html
<template>
</template>
</dom-module>
```

```html
<custom-style>
```

## 配置数据库连接

对于本项目，我将提到两种连接到 NoSQL 数据库的方法，第一种如《第 6 章：Java Server Faces》中描述的，即安装并配置 `docker` 并创建一个镜像；第二种是创建一个 `Class` 并配置到 `MongoDB` 的连接。如下所示所示：

![](img/8-6.jpg)

**图 8.6**

## 模型

对将在项目或演示中使用的 `Classes` 或接口进行汇总说明。这种类型的模型代表一个 `Role`（角色）。它包含一个 `idRole`、一个名称、两个布尔字段（第一个用于模块授权，第二个用于访问应用程序）。

对于 `Class` `user`（用户），它包含了用于标识用户的 `idUser` 字段、用于用户全名的 `firstName` 和 `lastName`，此外还有其他基本信息，如邮箱、密码、国家等。

## 类 Role

以下代码是 `Role` 类：

```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import java.util.List;

public class Role {
  @Id
  private String idRole;

  @Secondary
  private String name;

  private Boolean authorizedModule1;
  private Boolean accessModule2;

  public Role() {
  }

  public Role(String idRole, String name, Boolean authorizedModule1, Boolean accessModule2) {
    this.idRole = idRole;
    this.name = name;
    this.authorizedModule1 = authorizedModule1;
    this.accessModule2 = accessModule2;
  }

  public String getIdRole() {
    return idRole;
  }

  public void setIdRole(String idRole) {
    this.idRole = idRole;
  }

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public Boolean getAuthorizedModule1() {
    return authorizedModule1;
  }

  public void setAuthorizedModule1(Boolean authorizedModule1) {
    this.authorizedModule1 = authorizedModule1;
  }

  public Boolean getAccessModule2() {
    return accessModule2;
  }

  public void setAccessModule2(Boolean accessModule2) {
    this.accessModule2 = accessModule2;
  }

  @Override
  public String toString() {
    return "Role{" +
        "idRole=" + idRole +
        ", name='" + name + '\'' +
        ", authorizedModule1=" + authorizedModule1 +
        ", accessModule2=" + accessModule2 +
        '}';
  }
}
```

## 类 User

以下展示了 `User` 类：

```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import javax.validation.constraints.Email;
import java.util.List;

public class User {
  @Id
  private String idUser;

  @Secondary
  private String firstName;

  private String lastName;

  @Email
  private String contactEmail;

  private String password;
  private Boolean blocked;
  private String country;
  private Role mainRole;

  public User() {
  }

  public User(String idUser, String firstName, String lastName, @Email String contactEmail,
              String password, Boolean blocked, String country, Role mainRole) {
    this.idUser = idUser;
    this.firstName = firstName;
    this.lastName = lastName;
    this.contactEmail = contactEmail;
    this.password = password;
    this.blocked = blocked;
    this.country = country;
    this.mainRole = mainRole;
  }

  public String getIdUser() {
    return idUser;
  }

  public void setIdUser(String idUser) {
    this.idUser = idUser;
  }

  public String getFirstName() {
    return firstName;
  }

  public void setFirstName(String firstName) {
    this.firstName = firstName;
  }

  public String getLastName() {
    return lastName;
  }

  public void setLastName(String lastName) {
    this.lastName = lastName;
  }

  public String getContactEmail() {
    return contactEmail;
  }

  public void setContactEmail(String contactEmail) {
    this.contactEmail = contactEmail;
  }

  public String getPassword() {
    return password;
  }

  public void setPassword(String password) {
    this.password = password;
  }

  public Boolean getBlocked() {
    return blocked;
  }

  public void setBlocked(Boolean blocked) {
    this.blocked = blocked;
  }

  public String getCountry() {
    return country;
  }

  public void setCountry(String country) {
    this.country = country;
  }

  public Role getMainRole() {
    return mainRole;
  }

  public void setMainRole(Role mainRole) {
    this.mainRole = mainRole;
  }

  @Override
  public String toString() {
    return "User{" +
        "idUser=" + idUser +
        ", firstName='" + firstName + '\'' +
        ", lastName='" + lastName + '\'' +
        ", contactEmail='" + contactEmail + '\'' +
        ", password='" + password + '\'' +
        ", blocked=" + blocked +
        ", country='" + country + '\'' +
        ", mainRole=" + mainRole +
        '}';
  }
}
```

## 管理

`line-height: var(--lumo-line-height-s);`

`}`

`.confirm-text > * {`

`margin-bottom: 0.6em;`

`}`

`.confirm-text div:not(:first-child) {`

`color: var(--lumo-secondary-text-color);`

`font-size: var(--lumo-font-size-s);`

`}`

`</style>`

`</template>`

`</dom-module>`

`</custom-style>`

## 配置数据库连接

对于本项目，我将提到两种连接到 NoSQL 数据库的方法，第一种如《第 6 章：Java Server Faces》中描述的，即安装并配置 `docker` 并创建一个镜像；第二种是创建一个 `Class` 并配置到 `MongoDB` 的连接。如下所示：

![](img/8-6.jpg)

**图.6**

## 模型

对将在项目或演示中使用的 `Classes` 或接口进行汇总说明。这种类型的模型代表一个 `Role`（角色）。它包含一个 `idRole`、一个名称、两个布尔字段（第一个用于模块授权，第二个用于访问应用程序）。

对于 `Class` `user`（用户），它包含了用于标识用户的 `idUser` 字段、用于用户全名的 `firstName` 和 `lastName`，此外还有其他基本信息，如邮箱、密码、国家等。

## 类 Role

以下代码是 `Role` 类：



```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import java.util.List;

public class Role {
  @Id
  private String idRole;

  @Secondary
  private String name;

  private Boolean authorizedModule1;
  private Boolean accessModule2;

  public Role() {}

  public Role(String idRole, String name, Boolean authorizedModule1, Boolean accessModule2) {
    this.idRole = idRole;
    this.name = name;
    this.authorizedModule1 = authorizedModule1;
    this.accessModule2 = accessModule2;
  }

  public String getIdRole() {
    return idRole;
  }

  public void setIdRole(String idRole) {
    this.idRole = idRole;
  }

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public Boolean getAuthorizedModule1() {
    return authorizedModule1;
  }

  public void setAuthorizedModule1(Boolean authorizedModule1) {
    this.authorizedModule1 = authorizedModule1;
  }

  public Boolean getAccessModule2() {
    return accessModule2;
  }

  public void setAccessModule2(Boolean accessModule2) {
    this.accessModule2 = accessModule2;
  }

  @Override
  public String toString() {
    return "Role{" +
        "idRole=" + idRole +
        ", name='" + name + '\'' +
        ", authorizedModule1=" + authorizedModule1 +
        ", accessModule2=" + accessModule2 +
        '}';
  }
}
```

## 类 User

以下展示了 `User` 类：

```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import javax.validation.constraints.Email;
import java.util.List;

public class User {
  @Id
  private String idUser;

  @Secondary
  private String firstName;

  private String lastName;

  @Email
  private String contactEmail;

  private String password;
  private Boolean blocked;
  private String country;
  private Role mainRole;

  public User() {}

  public User(String idUser, String firstName, String lastName, @Email String contactEmail,
      String password, Boolean blocked, String country, Role mainRole) {
    this.idUser = idUser;
    this.firstName = firstName;
    this.lastName = lastName;
    this.contactEmail = contactEmail;
    this.password = password;
    this.blocked = blocked;
    this.country = country;
    this.mainRole = mainRole;
  }

  public String getIdUser() {
    return idUser;
  }

  public void setIdUser(String idUser) {
    this.idUser = idUser;
  }

  public String getFirstName() {
    return firstName;
  }

  public void setFirstName(String firstName) {
    this.firstName = firstName;
  }

  public String getLastName() {
    return lastName;
  }

  public void setLastName(String lastName) {
    this.lastName = lastName;
  }

  public String getContactEmail() {
    return contactEmail;
  }

  public void setContactEmail(String contactEmail) {
    this.contactEmail = contactEmail;
  }

  public String getPassword() {
    return password;
  }

  public void setPassword(String password) {
    this.password = password;
  }

  public Boolean getBlocked() {
    return blocked;
  }

  public void setBlocked(Boolean blocked) {
    this.blocked = blocked;
  }

  public String getCountry() {
    return country;
  }

  public void setCountry(String country) {
    this.country = country;
  }

  public Role getMainRole() {
    return mainRole;
  }

  public void setMainRole(Role mainRole) {
    this.mainRole = mainRole;
  }

  @Override
  public String toString() {
    return "User{" +
        "idUser=" + idUser +
        ", firstName='" + firstName + '\'' +
        ", lastName='" + lastName + '\'' +
        ", contactEmail='" + contactEmail + '\'' +
        ", password='" + password + '\'' +
        ", blocked=" + blocked +
        ", country='" + country + '\'' +
        ", mainRole=" + mainRole +
        '}';
  }
}
```

## 管理

`line-height: var(--lumo-line-height-s);`

`}`

`.confirm-text > * {`

`margin-bottom: 0.6em;`

`}`

`.confirm-text div:not(:first-child) {`

`color: var(--lumo-secondary-text-color);`

`font-size: var(--lumo-font-size-s);`

`}`

`</style>`

`</template>`

`</dom-module>`

`</custom-style>`

## 配置数据库连接

对于本项目，我将提到两种连接到 NoSQL 数据库的方法，第一种如 `第 6 章：Java Server Faces` 中描述的，即安装并配置 docker 并创建一个镜像；第二种是创建一个 `Class` 并配置到 `MongoDB` 的连接。如下所示：

![](img/8-6.jpg)

**图 8.6**

## 模型

对将在项目或演示中使用的 `Classes` 或接口进行汇总说明。这种类型的模型代表一个 `Role`（角色）。它包含一个 `idRole`、一个名称、两个布尔字段（第一个用于模块授权，第二个用于访问应用程序）。

对于 `Class` user（用户），它包含了用于标识用户的 `idUser` 字段、用于用户全名的 `firstName` 和 `lastName`，此外还有其他基本信息，如邮箱、密码、国家等。

## 类 Role

以下代码是 `Role` 类：

```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import java.util.List;

public class Role {
  @Id
  private String idRole;

  @Secondary
  private String name;

  private Boolean authorizedModule1;
  private Boolean accessModule2;

  public Role() {}

  public Role(String idRole, String name, Boolean authorizedModule1, Boolean accessModule2) {
    this.idRole = idRole;
    this.name = name;
    this.authorizedModule1 = authorizedModule1;
    this.accessModule2 = accessModule2;
  }

  public String getIdRole() {
    return idRole;
  }

  public void setIdRole(String idRole) {
    this.idRole = idRole;
  }

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public Boolean getAuthorizedModule1() {
    return authorizedModule1;
  }

  public void setAuthorizedModule1(Boolean authorizedModule1) {
    this.authorizedModule1 = authorizedModule1;
  }

  public Boolean getAccessModule2() {
    return accessModule2;
  }

  public void setAccessModule2(Boolean accessModule2) {
    this.accessModule2 = accessModule2;
  }

  @Override
  public String toString() {
    return "Role{" +
        "idRole=" + idRole +
        ", name='" + name + '\'' +
        ", authorizedModule1=" + authorizedModule1 +
        ", accessModule2=" + accessModule2 +
        '}';
  }
}
```

## 类 User

以下展示了 `User` 类：




```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import javax.validation.constraints.Email;
import java.util.List;

public class User {
  @Id
  private String idUser;
  @Secondary
  private String firstName;
  private String lastName;
  @Email
  private String contactEmail;
  private String password;
  private Boolean blocked;
  private String country;
  private Role mainRole;

  public User(){}

  public User(String idUser, String firstName, String lastName, @Email String contactEmail, String password, Boolean blocked, String country, Role mainRole) {
    this.idUser = idUser;
    this.firstName = firstName;
    this.lastName = lastName;
    this.contactEmail = contactEmail;
    this.password = password;
    this.blocked = blocked;
    this.country = country;
    this.mainRole = mainRole;
  }

  public String getIdUser() {
    return idUser;
  }

  public void setIdUser(String idUser) {
    this.idUser = idUser;
  }

  public String getFirstName() {
    return firstName;
  }

  public void setFirstName(String firstName) {
    this.firstName = firstName;
  }

  public String getLastName() {
    return lastName;
  }

  public void setLastName(String lastName) {
    this.lastName = lastName;
  }

  public String getContactEmail() {
    return contactEmail;
  }

  public void setContactEmail(String contactEmail) {
    this.contactEmail = contactEmail;
  }

  public String getPassword() {
    return password;
  }

  public void setPassword(String password) {
    this.password = password;
  }

  public Boolean getBlocked() {
    return blocked;
  }

  public void setBlocked(Boolean blocked) {
    this.blocked = blocked;
  }

  public String getCountry() {
    return country;
  }

  public void setCountry(String country) {
    this.country = country;
  }

  public Role getMainRole() {
    return mainRole;
  }

  public void setMainRole(Role mainRole) {
    this.mainRole = mainRole;
  }

  @Override
  public String toString() {
    return "User{" +
    "idUser=" + idUser +
    ", firstName='" + firstName + '\'' +
    ", lastName='" + lastName + '\'' +
    ", contactEmail='" + contactEmail + '\'' +
    ", password='" + password + '\'' +
    ", blocked=" + blocked +
    ", country='" + country + '\'' +
    ", mainRole=" + mainRole +
    '}';
  }
}
```

## 管理

`line-height: var(--lumo-line-height-s);`

`}`

`.confirm-text > * {`

`margin-bottom: 0.6em;`

`}`

`.confirm-text div:not(:first-child) {`

`color: var(--lumo-secondary-text-color);`

`font-size: var(--lumo-font-size-s);`

`}`

`</style>`

`</template>`

`</dom-module>`

`</custom-style>`

## 配置数据库连接

对于本项目，我将提到两种连接到 NoSQL 数据库的方法，第一种如`第 6 章：Java Server Faces`中描述的，即安装并配置`docker`并创建一个镜像；第二种是创建一个`Class`并配置到`MongoDB`的连接。如下所示：

![](img/8-6.jpg)

**图 8.6**

## 模型

对将在项目或演示中使用的`Classes`或接口进行汇总说明。这种类型的模型代表一个`Role`（角色）。它包含一个`idRole`、一个名称、两个布尔字段（第一个用于模块授权，第二个用于访问应用程序）。

对于`Class` user（用户），它包含了用于标识用户的`idUser`字段、用于用户全名的`firstName`和`lastName`，此外还有其他基本信息，如邮箱、密码、国家等。

## 类 Role

以下代码是`Role`类：

```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import java.util.List;

public class Role {
  @Id
  private String idRole;
  @Secondary
  private String name;
  private Boolean authorizedModule1;
  private Boolean accessModule2;

  public Role(){}

  public Role(String idRole, String name, Boolean authorizedModule1, Boolean accessModule2) {
    this.idRole = idRole;
    this.name = name;
    this.authorizedModule1 = authorizedModule1;
    this.accessModule2 = accessModule2;
  }

  public String getIdRole() {
    return idRole;
  }

  public void setIdRole(String idRole) {
    this.idRole = idRole;
  }

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public Boolean getAuthorizedModule1() {
    return authorizedModule1;
  }

  public void setAuthorizedModule1(Boolean authorizedModule1) {
    this.authorizedModule1 = authorizedModule1;
  }

  public Boolean getAccessModule2() {
    return accessModule2;
  }

  public void setAccessModule2(Boolean accessModule2) {
    this.accessModule2 = accessModule2;
  }

  @Override
  public String toString() {
    return "Role{" +
    "idRole=" + idRole +
    ", name='" + name + '\'' +
    ", authorizedModule1=" + authorizedModule1 +
    ", accessModule2=" + accessModule2 +
    '}';
  }
}
```

## 类 User

以下展示了`User`类：

```java
import com.avbravo.jmoordb.anotations.Embedded;
import com.avbravo.jmoordb.anotations.Id;
import com.avbravo.jmoordb.anotations.Secondary;
import com.avbravo.jmoordb.pojos.UserInfo;
import javax.validation.constraints.Email;
import java.util.List;

public class User {
  @Id
  private String idUser;
  @Secondary
  private String firstName;
  private String lastName;
  @Email
  private String contactEmail;
  private String password;
  private Boolean blocked;
  private String country;
  private Role mainRole;

  public User(){}

  public User(String idUser, String firstName, String lastName, @Email String contactEmail, String password, Boolean blocked, String country, Role mainRole) {
    this.idUser = idUser;
    this.firstName = firstName;
    this.lastName = lastName;
    this.contactEmail = contactEmail;
    this.password = password;
    this.blocked = blocked;
    this.country = country;
    this.mainRole = mainRole;
  }

  public String getIdUser() {
    return idUser;
  }

  public void setIdUser(String idUser) {
    this.idUser = idUser;
  }

  public String getFirstName() {
    return firstName;
  }

  public void setFirstName(String firstName) {
    this.firstName = firstName;
  }

  public String getLastName() {
    return lastName;
  }

  public void setLastName(String lastName) {
    this.lastName = lastName;
  }

  public String getContactEmail() {
    return contactEmail;
  }

  public void setContactEmail(String contactEmail) {
    this.contactEmail = contactEmail;
  }

  public String getPassword() {
    return password;
  }

  public void setPassword(String password) {
    this.password = password;
  }

  public Boolean getBlocked() {
    return blocked;
  }

  public void setBlocked(Boolean blocked) {
    this.blocked = blocked;
  }

  public String getCountry() {
    return country;
  }

  public void setCountry(String country) {
    this.country = country;
  }

  public Role getMainRole() {
    return mainRole;
  }

  public void setMainRole(Role mainRole) {
    this.mainRole = mainRole;
  }

  @Override
  public String toString() {
    return "User{" +
    "idUser=" + idUser +
    ", firstName='" + firstName + '\'' +
    ", lastName='" + lastName + '\'' +
    ", contactEmail='" + contactEmail + '\'' +
    ", password='" + password + '\'' +
    ", blocked=" + blocked +
    ", country='" + country + '\'' +
    ", mainRole=" + mainRole +
    '}';
  }
}
```

## 管理

提供一个`EJB`类来支持实体类的基本操作。Jmoordb 为 CRUD 操作提供了`Repository`接口。

现在我们创建一个`UserManagement`类。在下一步中，我们将添加一个 (1) 方法，第一个参数是模型类，第二个参数是数据库名称，最后一个参数是表名。

## UserManagement

```java
import com.avbravo.jmoordb.repository;
import com.book.bpb.backend.entity.User;
import javax.ejb.Stateless;

@Stateless
public class UserManagement extends Repository<User> {
  public UserManagement(){
    super(User.class,"demo");
  }
}
```

在此步骤中我们创建一个`RoleManagement`类。在下一步中，我们将添加一个 (1) 方法，第一个参数是实体类，第二个参数是数据库名称，最后一个参数是表名。

## RoleManagement 类

```java
import com.avbravo.jmoordb.repository;
import com.book.bpb.backend.entity.Role;
import javax.ejb.Stateless;

@Stateless
public class RoleManagement extends Repository<Role>{
  public RoleManagement(){
    super(Role.class,"demo");
  }
}
```




```java
import java.util.List;
import javax.inject.Inject;
import javax.ws.rs.Consumes;
import javax.ws.rs.DELETE;
import javax.ws.rs.GET;
import javax.ws.rs.POST;
import javax.ws.rs.PUT;
import javax.ws.rs.Path;
import javax.ws.rs.PathParam;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;

@Path("users")
public class UserResource {
    String directoryLogger = JsfUtil.isLinux() ? JsfUtil.userHome() + JsfUtil.fileSeparator() + "demo" + JsfUtil.fileSeparator() + "logs" + JsfUtil.fileSeparator() + "logger.json" : "C:\\demo\\logs\\logger.json";

    @Inject
    UserManagement userManagement;

    @GET
    public List<User> findAll() {
        return this.userManagement.findAll();
    }

    @GET
    @Path("{name}")
    public List<User> findByName(@PathParam("name") String name) {
        return this.userManagement.findRegex("name", name, true, new Document("name", 1));
    }

    @POST
    public Response createUser(User user) {
        try {
            if (userManagement.update(user)) {
                return Response.status(201).entity("User saved").build();
            }
            return Response.status(400).entity("User could not be saved").build();
        } catch (Exception e) {
            JsfUtil.appendTextToLogErrorFile(this.directoryLogger, JsfUtil.nameOfClass(), JsfUtil.nameOfMethod(), e.getLocalizedMessage(), e);
            return Response.status(400).entity("Error!!" + e.getLocalizedMessage()).build();
        }
    }

    @PUT
    @Path("/update")
    @Consumes(MediaType.APPLICATION_JSON)
    public Response update(User user) {
        try {
            if (userManagement.update(user)) {
                return Response.status(201).entity("Updated User").build();
            }
            return Response.status(400).entity("User was not updated").build();
        } catch (Exception e) {
            JsfUtil.appendTextToLogErrorFile(this.directoryLogger, JsfUtil.nameOfClass(), JsfUtil.nameOfMethod(), e.getLocalizedMessage(), e);
            return Response.status(400).entity("Error!!" + e.getLocalizedMessage()).build();
        }
    }

    @DELETE
    @Path("/delete")
    @Consumes(MediaType.APPLICATION_JSON)
    public Response delete(User user) {
        try {
            if (userManagement.delete(user)) {
                return Response.status(201).entity("delete user").build();
            }
            return Response.status(400).entity("Not update of user").build();
        } catch (Exception e) {
            JsfUtil.appendTextToLogErrorFile(this.directoryLogger, JsfUtil.nameOfClass(), JsfUtil.nameOfMethod(), e.getLocalizedMessage(), e);
            return Response.status(400).entity("error!!" + e.getLocalizedMessage()).build();
        }
    }
}
```

## `RoleResource` 类

`RoleResource` 类促进了存储库与保存、更新、删除以及通过 `findByName` 和 `findAll` 角色操作的通信，如 `RoleResource` 类代码所示：

```java
import com.avbravo.jmoordbutils.JsfUtil;
import com.book.bpb.backend.dao.RoleManagement;
import com.book.bpb.backend.entity.Role;
import com.mongodb.client.result.DeleteResult;
import org.bson.Document;
import javax.inject.Inject;
import javax.ws.rs.*;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;
import java.util.List;

@Path("roles")
public class RoleResource {
    String directoryLogger = JsfUtil.isLinux() ? JsfUtil.userHome() + JsfUtil.fileSeparator() + "demo" + JsfUtil.fileSeparator() + "logs" + JsfUtil.fileSeparator() + "logger.json" : "C:\\demo\\logs\\logger.json";

    @Inject
    RoleManagement roleManagement;

    @GET
    public List<Role> findAll() {
        return this.roleManagement.findAll();
    }

    @GET
    @Path("{name}")
    public List<Role> findByName(@PathParam("name") String name) {
        return this.roleManagement.findRegex("name", name, true, new Document("name", 1));
    }

    @POST
    public Response createRole(Role role) {
        try {
            if (roleManagement.update(role)) {
                return Response.status(201).entity("Role saved").build();
            }
            return Response.status(400).entity("Role could not be saved").build();
        } catch (Exception e) {
            JsfUtil.appendTextToLogErrorFile(this.directoryLogger, JsfUtil.nameOfClass(), JsfUtil.nameOfMethod(), e.getLocalizedMessage(), e);
            return Response.status(400).entity("Error!!" + e.getLocalizedMessage()).build();
        }
    }

    @PUT
    @Path("/update")
    @Consumes(MediaType.APPLICATION_JSON)
    public Response update(Role role) {
        try {
            if (roleManagement.update(role)) {
                return Response.status(201).entity("Updated role").build();
            }
            return Response.status(400).entity("Role was not updated").build();
        } catch (Exception e) {
            JsfUtil.appendTextToLogErrorFile(this.directoryLogger, JsfUtil.nameOfClass(), JsfUtil.nameOfMethod(), e.getLocalizedMessage(), e);
            // 注意：原文在此处大大括号问题
        }
    }

    // ... 剩余方法遵循相同的模式

    @DELETE
    @Path("/delete")
    @Consumes(MediaType.APPLICATION_JSON)
    public Response delete(User user) {
        try {
            if (userManagement.delete(user)) {
                return Response.status(201).entity("delete user").build();
            }
            return Response.status(400).entity("Not update of user").build();
        } catch (Exception e) {
            JsfUtil.appendTextToLogErrorFile(this.directoryLogger, JsfUtil.nameOfClass(), JsfUtil.nameOfMethod(), e.getLocalizedMessage(), e);
            return Response.status(400).entity("error!!" + e.getLocalizedMessage()).build();
        }
    }
}
```

## `MainView`

我们修改了 `MainView` 类，为了良好的设计，我们使用 `GRID` 组件来列出数据。这些名称声明如下：

```java
@HtmlImport("frontend://shared-styles.html")
@Viewport("width=device-width, minimum-scale=1.0, initial-scale=1.0, user=yes")
@PWA(name = "Project Base", shortName = "Project Base")
@Theme(value = Lumo.Class, variant = Lumo.LIGHT)
public class MainView extends Div implements RouterLayout, PageConfigurator {
    public MainView() {
        H2 title = new H2("es");
        title.addClassName("main-layout__title");

        RouterLink users = new RouterLink(null, userList.Class);
        users.add(new Icon(VaadinIcon.LIST), new Text("Users"));
        users.addClassName("main-layout__nav-item");
        users.setHighlightCondition(HighlightConditions.sameLocation());

        RouterLink roles = new RouterLink(null, roleList.Class);
        roles.add(new Icon(VaadinIcon.ARCHIVES), new Text("Roles"));
        roles.addClassName("main-layout__nav-item");

        Div navigation = new Div(users, roles);
        navigation.addClassName("main-layout__nav");

        Div header = new Div(title, navigation);
        header.addClassName("main-layout__header");

        add(header);
        addClassName("main-layout");
    }

    @Override
    public void conFigurePage(InitialPageSettings settings) {
        settings.addMetaTag("apple-mobile-web-app-capable", "yes");
        settings.addMetaTag("apple-mobile-web-app-status-bar-style", "black");
    }
}
```

在下一步中，我们创建 `userList` 类，此表单将包含与新 `User`、更新或删除相关的所有：

```java
@Route(value = "users", layout = MainView.Class)
@PageTitle("Users List")
public class userList extends Composite<VerticalLayout> {
    private Button refresh = new Button("", VaadinIcon.REFRESH.create());
    private Button add = new Button("", VaadinIcon.PLUS.create());
    private Button edit = new Button("", VaadinIcon.PENCIL.create());
    private Grid<User> grid = new Grid<>(User.Class);
    private final IUserService repo;
    private final IRoleService role;

    private TextField firstName = new TextField("First name");
    private TextField lastName = new TextField("Last name");
}
```



```java
private EmailField contactEmail = new EmailField("Contact Email");
private PasswordField password = new PasswordField("Password");
private CheckboxGroup<Role> roles = new CheckboxGroup<>();
private ComboBox<Role> mainRole = new ComboBox<>("Main Role", role.listar());
private Checkbox blocked = new Checkbox("Blocked");
private ComboBox<String> country = new ComboBox<>("Country");
private Button cancel = new Button("Cancel");
private Button save = new Button("Save", VaadinIcon.CHECK.create());
```

当点击任何按钮时，都会显示 `UserFormDialog`。对于添加按钮，我们传递了一个新的用户实例。对于更新按钮，我们传递在 `GRID` 中选中的 `User` 实例。我们可以将 `UserFormDialog` 实现为 `Crud` 中的内部类：

```java
public UserFormDialog(String caption, User user) {
    initLayout(caption);
    initBehavior(user);
}
```

表单中的所有输入字段都是 `UserFormWindow` 类的成员，并添加到 `initLayout` 方法中的某种设计中。

`initBehaviour` 方法必须建立用户实例与输入字段之间的数据链接。

我们需要数据绑定。在 Vaadin 框架中，这通常意味着使用一个 binder：

```java
private void initLayout(String caption) {
    roles.setItems(role.listar());
    save.getElement().setAttribute("theme", "primary");
    HorizontalLayout buttons = new HorizontalLayout(cancel, save);
    buttons.setSpacing(true);
    FormLayout formLayout = new FormLayout(new H2(caption), firstName, lastName, contactEmail, password, country, roles, mainRole, blocked);
    VerticalLayout layout = new VerticalLayout(formLayout, buttons);
    layout.setAlignSelf(FlexComponent.Alignment.END, buttons);
    add(layout);
}
```

```java
private List<String> getCountriesList() {
    return Stream.of(Locale.getISOCountries())
        .map(iso -> new Locale("",iso).getDisplayCountry()).sorted()
        .collect(Collectors.toList());
}
```

`initBehavior` 方法中发生了一些重要的事情：

- 所有在 `UserFormWindow` 类中也是输入字段的 Java 字段都链接到 `Student` 类中的 Java 字段（通过调用 `bindIntanceFields`）。
- User 类 Java 字段中的所有值都设置在 `UserFormWindow` 类对应的输入字段中（通过 `readBean`）。

```java
private void initBehavior(User user) {
    BeanValidationBinder<User> binder = new BeanValidationBinder<>(User.Class);
    binder.bindInstanceFields(this);
    binder.readBean(user);
    cancel.addClickListener(e -> close());
    save.addClickListener(e -> {
        try {
            binder.validate();
            binder.writeBean(user);
            repo.registrar(user);
            close();
            refresh();
            Notification.show("User saved");
        } catch (ValidationException ex) {
            Notification.show("Please fix the errors and try again");
        }
    });
}
```

当你点击取消按钮时，只需调用 `Window.close()`（旧版）。监听保存按钮会调用 `writeBean` 将输入字段中的值写入 `User` 实例中：

```java
cancel.addClickListener(e -> close());
```

**注意：`writeBean` 会触发 `ValidationException`。因此，此时还没有进行验证。添加我们在 User 类中拥有的 JavaBean 验证限制只需更改 Binder 的实现即可：**

```java
BeanValidationBinder<User> binder = new BeanValidationBinder<>(User.Class);
```

## 实现删除操作

让我们用不同的方法来实现基于删除按钮的 CRUD 操作。与其简单地为该操作添加单个按钮，我们将在 `GRID` 的每一行中添加一个删除按钮。在 `GRID` 内部添加 UI 组件最简单的方法是使用 `addComponentColumn` 方法：

```java
private class RemoveDialog extends Dialog {
    private Button cancel = new Button("Cancel");
    private Button delete = new Button("Delete", VaadinIcon.TRASH.create());

    public RemoveDialog(User user) {
        initLayout(user);
        initBehavior(user);
    }
```

我们创建 `initLayout()` 方法，在其中配置页面的整个部分，添加列名并使用 `setColumns` 方法配置 Grid，以显示 `idUser`、`firstName` 和 `lastName` 属性。最后是尺寸和位置：

```java
private void initLayout(User user) {
    Span span = new Span("Do you really want to delete the user " + user.getFirstName() + " " + user.getLastName() + "?");
    delete.getElement().setAttribute("theme", "error");
    HorizontalLayout buttons = new HorizontalLayout(cancel, delete);
    VerticalLayout layout = new VerticalLayout(new H2("Confirm"), span, buttons);
    layout.setAlignSelf(FlexComponent.Alignment.END, buttons);
}
```



```java
private class RemoveDialog extends Dialog {
    private Button cancel = new Button("Cancel");
    private Button delete = new Button("Delete", VaadinIcon.TRASH.create());
    public RemoveDialog(User user) {
        initLayout(user);
        initBehavior(user);
    }
```

我们创建 `initLayout()` 方法，在其中配置页面的整个部分，添加列名并使用 `setColumns` 方法配置 `Grid`，以显示 `idUser`、`firstName` 和 `lastName` 属性。最后是尺寸和位置：

```java
private void initLayout(User user) {
    Span span = new Span("Do you really want to delete the user " + user.getFirstName() + " " + user.getLastName() + "?");
    delete.getElement().setAttribute("theme", "error");
    HorizontalLayout buttons = new HorizontalLayout(cancel, delete);
    VerticalLayout layout = new VerticalLayout(new H2("Confirm"), span, buttons);
    layout.setAlignSelf(FlexComponent.Alignment.END, buttons);
}
```

```java
return this.roleManagement.findAllRole();
}

@GET
@Path("{name}")
public Role findByName(@PathParam("name") String name) {
    return this.roleManagement.findBYName(name);
}

@POST
public void createRole(Role role) {
    this.roleManagement.createRole(role);
}

@PUT
@Path("{name}")
public void updateAccount(@PathParam("name") String name, Role role) {
    this.roleManagement.updateRoleByName(name, role);
}

@DELETE
@Path("{name}")
public Response deleteRole(@PathParam("name") String name) {
    DeleteResult result = this.roleManagement.removeByName(name);
    System.out.println(result.getDeletedCount());
    return Response.ok().build();
}
```

## 项目执行

我们在`mvn clean package tomee:run`终端中执行以下命令。现在，我们准备好运行应用程序并导航到`localhost:8080`。如如下截图所示：

![](img/8-7.jpg)

**图 8.7**

我们点击`User`（用户）菜单，如下截图所示可视化`User View`（用户视图）的数据：

![](img/8-8.jpg)

**图 8.8**

接下来，我们按下`Add`按钮并添加，如下截图所示：

![](img/8-9.jpg)

**图 8.9**

接下来，我们按下`Edit`按钮进行编辑，如下面的截图所示：

![](img/8-10.jpg)

**图 8.10**

接下来，我们按下`Delete`按钮进行删除，如下截图所示：

![](img/8-11.jpg)

**图 8.11**

我们点击`User`菜单，如下截图所示可视化`Role View`（角色视图）的数据：

![](img/8-12.jpg)

**图 8.12**

接下来，我们按下`Add`按钮并添加，如下截图所示：

![](img/8-13.jpg)

**图 8.13**

接下来，我们按下`Edit`按钮进行编辑，如下面的截图所示：

![](img/8-14.jpg)

**图 8.14**

接下来，我们按下`Delete`按钮进行删除，如下截图所示：

![](img/8-15.jpg)

**图 8.15**

## 使用 PWA 运行

正如在前一章关于`渐进式 Web 应用 (PWA)`中提到的，PWA 是一种结合了网页和原生移动应用程序的应用程序软件。由于它提供了与原生应用相似的体验，因此 Vaadin 为 PWA 应用提供了非常方便的配置，只需在项目的主类（在本例中为`MainView`类）中添加`@PWA`注解即可，如下代码所示：

```java
@PWA(name = "Project Base for Vaadin Flow with CDI", shortName = "Project Base")
```

这将提供一个`offline.html`页面，因此它可以看起来像传统的桌面应用程序，也可以通过结合现代浏览器的特性看起来像现代原生移动应用程序。

运行应用程序时，你可以在页面底部的栏中看到它是一个 PWA 应用，如下截图所示：

![](img/8-16.jpg)

**图 8.16**

通过点击，应用程序将安装在移动设备、平板电脑或桌面上。

## 响应式设计

如下截图所示，我们将从移动或桌面设备模拟应用程序。Vaadin Responsive 是一个可以添加到任何组件或 UI 的扩展。它是一种 Web 设计方法，旨在创建在各种设备（从桌面电脑显示器到手机手机）上通过最少的缩放和滚动即可提供最佳、易于阅读和导航的查看体验的站点。

![](img/8-17.jpg)

**图 8.17**

## 总结

在本章中，读者学习了如何使用最佳实践从零开始连接到`MongoDB`等 NoSQL 数据库的 Web 应用。我们从开始解释了如何从 Vaadin 页面创建项目，为项目添加必要的依赖项，以及应用程序样式以便在网页和移动场景下进行可视化。

## 问题

1. 如何在桌面和移动上安装 Vaadin 应用？

## 参考文献

* **[`developer.mozilla.org/en-US/docs/Web/Web_Components`](https://developer.mozilla.org/en-US/docs/Web/Web_Components)**

* **[`vaadin.com/docs/v14/index.html`](https://vaadin.com/docs/v14/index.html)**

# 第 9 章

# Eclipse Krazo 与微服务的安全性

## 引言

本章将演示如何使用`Eclipse Krazo`创建应用程序，Eclipse Krazo 是一种用于为符合 Microprofile 标准的应用程序构建用户界面的新框架。你还将学习如何使用`Jakarta EE`和`JSON Web Token (JWT)`在应用程序中实现安全措施。

## 结构

* Eclipse Krazo 简介

* MvcContext

* Eclipse Krazo

* Controller (控制器)

* Model (模型)

* CDI

* VIEW (视图)

* Databinding (数据绑定)

* Validation (验证)

* Security (安全)

* Jakarta EE Security API Specification

* Eclipse MicroProfile Interoperable JWT RBAC

* JSON Web Tokens (JWT)

* Realm (领域)

* MP LEMON BUILDER

## 目标

学习 Eclipse Krazo 的基本概念以及如何使用`IdentityStore`和`JWT`实现安全。

## Eclipse Krazo 简介

多年来，Java EE 平台引入动作导向的框架一直受到期待。首次尝试是在 JSR 371 中进行的，可以在[`jcp.org/en/jsr/detail/371`](https://jcp.org/en/jsr/detail/371)找到。该规范从 Java EE 8 平台中排除，因此被更改为 Eclipse Krazo 以避免版权问题。该项目目前在 Eclipse Foundation 的名下，其名称可以在网站[`www.mvc-spec.org/2019/10/28/eclipse-krazo-beta1.html`](https://www.mvc-spec.org/2019/10/28/eclipse-krazo-beta1.html)找到。

Java Web 框架分为两类：

* 组件导型框架在框架内部处理 HTTP 请求，因此在应用程序代码中所需的交互很少。而在动作导向框架中，所有 HTTP 请求都路由到应用程序，由开发者负责在控制器中进行相应的实现。

Eclipse Krazo 构建在 JAX-RS API 之上，并支持 CDI 和 Bean Validation 等 Jakarta EE API。第五章“探索 MicroProfile”中展示了 JSQL 的示例。在本章中，我们将关注通用方面。

现在将使用 maven 模板创建一个名为`krazosguide`的项目。进入控制台并命令：

```bash
mvn archetype:generate -DarchetypeGroupId=de.erdlet.archetypes -DarchetypeArtifactId=jakartaee8-mvc-archetype -DarchetypeVersion=1.0.1-Beta1 -DgroupId=com.bpb.book -DartifactId=krazosguide
```

模板生成了应用程序的多个组件、视图文件`hello.jsp`、主类`App.java`以及控制器`AppController.java`，将在后续章节中描述：

![](img/9-1.jpg)

**图 9.1**

`App.java`类定义了`ApplicationPath("/mvc")`，如下代码所示：

```java
@ApplicationPath("/mvc")
public class App extends Application {
}
```

`AppController.java`拥有`@Controller`注解，`sayHello()`方法拥有`@GET`注解，客户端将通过`/mvc/app`路径访问，从而调用`hello.jsp`页面。以下是`AppController.java`的代码：

```java
@Path("app")
@Controller
```

```java
public class AppController {

  @GET
  public String sayHello() {
    return "hello.jsp";
  }
}
```

`hello.jsp`代表应用程序的视图，并显示`Hello MVC`消息。如下面的代码所示：

```html
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hello!</title>
</head>
<body>
  <h1>Hello MVC!</h1>
</body>
</html>
```

当你运行应用程序并进入浏览器时，你将看到像下面图片所示的视图。`http://localhost:8080/krazosguide/mvc/app:`

![](img/9-2.jpg)

**图 9.2**

## MVCContext

`MvcContext`被规范定义为一个对象，允许我们访问应用程序的配置、安全和路径。它通过注入方式在控制器中使用，并通过表达式语言 (EL) 在视图中使用。例如：

`<form action="${mvc.basePath}/mvc/update" method="post">`

## Controller

控制器是一个 java 类，我们对其添加`@Controller`注解，这是一个 JAX-RS API 装饰器。请记住，根据 MVC 模式，`Controller`是一个接口，允许处理业务逻辑以及发生在模型和视图之间的请求。

在 Controller 方法中定义的返回值类型有：

*   `String`：这被解释为`Path`。

*   `void`：与`@View`装饰器配合使用。

*   `Response`：它是 JAX-RS 风格的`Response`。

*   `Viewable`：包括对视图引擎模型或对象的引用。

## Models

Models 允许我们通过 map 将数据传递到视图。例如：

```java
@Inject
private Models models;

@GET
public String sayHello() {
  models.put("message","Welcome !");
  return "hello.jsp";
}
```

## CDI

Eclipse Krazo 支持通过`@Named`注解使用 CDI 实现，该注解定义了 beans 和 models，后者是一个定义了视图和控制器之间 map 的接口。这些被定义为`@RequestScoped`。

按照下面的代码创建`Greeting.java`类：

```java
@Named("greeting")
@RequestScoped
public class Greeting {
  private String message;
  public String getMessage() {
    return message;
  }
  public void setMessage(String message) {
    this.message = message;
  }
}
```

然后我们将将其注入到`AppController.java`类中，并创建`Cdi()`方法来分配`Welcome from CDI message:`：

```java
@Inject
Greeting greeting;

@GET
@Path("cdi")
public String Cdi() {
  greeting.setMessage("Welcome from CDI");
  return "hello.jsp";
}
```

## View

它负责数据的显示，在编写本书时，Eclipse Krazo 支持 12 种视图引擎：

*   JSP

*   Facelets

*   Asciidoc

*   Freemarker

*   Handlebars

*   Jade

*   Jetbrick

*   JSR-223

*   Mustache

*   Pebble

*   Stringtemplate

*   Thymeleaf

*   Velocity

*   Jtwig

为了显示通过 Models 和 CDI 分配的数据，我们编辑页面`hello.jsp`并添加以下代码行：

`<h2>${message}</h2>`

`<h3>${greeting.message}</h3>`

`hello.jsp`页面看起来类似于以下：

```html
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Hello!</title>
</head>
<body>
  <h1>Hello MVC!</h1>
  <h2>${message}</h2>
  <h3>${greeting.message}</h3>
</body>
</html>
```

（注：此处省略重复内容）

以下是`AppController`类的完整代码，包含了 Models、CDI 等等的实现：



```java
@Path("app")
@Controller
public class AppController {
  @Inject
  Models models;
  @Inject
  Greeting greeting;

  @GET
  public String sayHello() {
    return "hello.jsp";
  }

  @GET
  @Path("view")
  @View("hello.jsp")
  public void view() {
    this.models.put("message", "Welcome from view");
  }

  @GET
  @Path("response")
  public Response response() {
    this.models.put("message", "Welcome from response");
    return Response.status(Response.Status.OK)
      .entity("hello.jsp")
      .build();
  }

  @GET
  @Path("viewable")
  public Viewable viewable() {
    this.models.put("message", "Welcome from viewable");
    return "viewable";
  }

  @GET
  @Path("cdi")
  public String Cdi() {
    greeting.setMessage("Welcome from CDI");
    return "hello.jsp";
  }
}
```

`IdentityStoreHandler` 接口允许你调用身份存储（Identity Store）并验证用户的凭据。

它包含两个方法：

* `validate(Credential)`：验证凭据并返回有关用户的信息。
* `getCallerGroups(CredentialValidationResult)`：它返回与调用者关联的所有组。

使用 NetBeans IDE 创建一个项目，其中一个返回国家列表的微服务将在 PayaraMicro 中运行。（你可以使用支持 Microprofile 的其他服务器）。我们将使用的角色 `web` 和 `mobile` 将在 `web.xml` 文件中指定。以下为示例设置了安全限制的 `web.xml` 文件：

```xml
<security-constraint>
  <web-resource-collection>
    <web-resource-name>Application pages</web-resource-name>
    <url-pattern>/faces/pages/*</url-pattern>
  </web-resource-collection>
  <auth-constraint>
    <role-name>web</role-name>
    <role-name>mobile</role-name>
  </auth-constraint>
</security-constraint>
<security-role>
  <role-name>web</role-name>
</security-role>
<security-role>
  <role-name>mobile</role-name>
</security-role>
```

在 `JAXRSConfiguration` 类中，我们通过 `@DeclaredRoles` 建立了 `web` 和 `mobile` 角色的权限。确保只有拥有这些角色的用户才能访问。以下是 `JAXRSConfiguration.java` 的代码：

```java
@ApplicationScoped
@ApplicationPath("resources")
@DeclareRoles({"web", "mobile"})
@BasicAuthenticationMechanismDefinition(realmName = "jnosqlrealm")
public class JAXRSConfiguration extends Application {
    @Override
    public Set<Class<?>> getClasses() {
        Set<Class<?>> resources = new java.util.HashSet<>();
        resources.add(com.bpb.jakarta.nosql.securityidentitystore.resources.CountryResources.class);
        return resources;
    }
}
```

实体类 `Country` 代表国家的信息：

```java
public Class Country {
    private String id;
    private String name;
    //get/set
}
```

`CountryResources` 类包含了 `getCountry()` 方法，该方法将返回某些国家列表。使用 `@RolesAllowed({"web"})` 将访问限制为具有 `web` 角色的用户：

```java
@Stateless
@Path("/country")
public class CountryResources {
    @GET
    @Produces(MediaType.APPLICATION_JSON)
    @RolesAllowed({"web"})
    public List<Country> getCountry() {
        List<Country> country = new ArrayList<Country>();
        country.add(new Country("pa", "Panama"));
        country.add(new Country("co", "Colombia"));
        country.add(new Country("br", "Brasil"));
        return country;
    }
}
```

实现 `IdentityStore` 的 `CountrySecurity` 类包含 `CredentialValidationResult` 的 `validate` 方法（`UsernamePasswordCredential` `usernamePasswordCredential`），其中对调用者提供的用户凭据（用户名、密码）进行验证。这些需要验证的凭据可以存储在仓库、文件、数据库等。

该方法将返回用户及其拥有的角色，这些角色将用于验证实现 `@DeclareRoles({"web", "mobile"})` 和 `@RolesAllowed({"web"})` 的类中的访问。

显示凭据验证的 `CountrySecurity` 类代码与所示，请注意这只是一个示例，用户和密码数据放置在你的应用程序中，请使用 `IdentityStore` 的源：

```java
@ApplicationScoped
public class ContrySecurity implements IdentityStore {
    public CredentialValidationResult validate(UsernamePasswordCredential usernamePasswordCredential) {
        if (usernamePasswordCredential.compareTo("userjnosql", "userjnosql")) {
            return new CredentialValidationResult("userjnosql", new HashSet<>(asList("web", "mobile")));
        }
        return INVALID_RESULT;
    }
}
```

根据你的考虑，从 IDE 运行应用程序或通过 docker 或将其转换为 Uber jar，并在浏览器中输入 `http://localhost:8080/resources/country`，将显示一个对话框，请求用户凭据：

![](img/figure_9.5.jpg)

**图 9.5**

输入用户名凭据：`userjnosql` 和密码：`userjnosql`。记住这些仅用于教学目的，永远不要使用与用户名类似的密码，并且不要在代码中直接暴露它们。它生成 JSON 格式的国家列表：

![](img/9-5.jpg)

**图 9.6**

Postman 是与微服务交互极极工具。要建立身份验证，你必须为 `BasicAuth` 设置参数，如用户名和密码。

下图显示了通过 `IdentityStore` 认证消费微服务：

![](img/9-6.jpg)

**图 9.7**

## Eclipse MicroProfile 互操作 JWT RBAC

这是一个 Microprofile 规范，它规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

该规范规定了如何在微服务中实现 `JSON Web Token (JWT)`。它使用 `OpenID Connect (OIDC)` 和 `JWT (JSON Web Tokens)` 进行基于角色的控制。

## JSON Web Tokens (JWT)

RFC-7519 标准将 JSON Web Tokens 定义为安全地表示双方之间声明的机制。JWT 包含：

* `Header`：包含用于签名令牌的算法类型、令牌类型。
* `Claims`：存储在令牌上的信息。
* `Signature`：签名。

对于下面开发的示例，将使用 Payara Server。你可以使用你喜欢的服务器。将执行的基本步骤：

* 在 Payara Server 上创建 Realm
* 生成两个测试用户
* 使用 `mplemon` 生成应用程序
* 部署两个应用程序
* 从控制台和 PostMan 测试

使用以下命令运行 Payara Server：

```bash
cd ~/payara-5.194/payara5/bin
./asadmin start-domain domain1
```

## Realm

Realm 是一种用于用户验证的机制。将创建一个 Realm 并添加用户进行验证。步骤如下：

1. 从浏览器访问 Payara Server 的管理界面，通常启用在端口 `4848` http://localhost:4848：
2. 然后，选择 `Configurations | Server-configure | Security | Realm`：

![](img/9-7.jpg)

**图 9.8**

3. 点击 `New` 按钮。为属性输入以下值：

   * `Name`：`jnosql-realm`
   * `Class Name`：`com.sun.enterprise.security.auth.realm.file.FileRealm`
   * `Key File`：`jnosql-realm`

![](img/9-8.jpg)

**图 9.9**

4. 点击 `Ok` 按钮保存更改，创建的 realm 显示在列表中：

![](img/9-9.jpg)

**图 9.10**

现在点击 `jnosql-realm` 并点击 `Manage Users` 按钮来创建用户：

![](img/9-10.jpg)

**图 9.11**

点击 `Manager User` 按钮将显示输入用户信息的表单。使用以下值：

`User Id`：`userjnosql`

`Group List`：`web`

输入你认为合适的密码并点击 `Ok` 按钮。

![](img/9-11.jpg)

**图 9.12**

重复此过程并创建一个具有以下详细信息的新用户：

`User Id`：`userjmoordb`

`Group List`：`mobile`

最后，它将显示将由 Payara Server 验证的两个用户。

![](img/9-12.jpg)

**图 9.13**

# MP Lemon Builder

MP Lemon Builder 是由 Diego Enrique Silva Límaco（`@apuntesdejava`）开发的一个工具，它允许我们为 Microprofile 生成带有 JWT 身份验证的项目。它非常易用，并且自动化了生成项目的整个过程，包括生成令牌以及消耗令牌的应用程序。

第一步是从以下网站下载 `.jar` 文件：

[`github.com/apuntesdejava/mp-lemon-builder`](https://github.com/apuntesdejava/mp-lemon-builder)

下载完成后，从控制台使用 `--help` 参数执行以获取关于生成项目所需的不同参数的帮助：

```
java -jar mplemonbuilder.jar --help
```

要创建项目，运行带有以下参数的 `mplemonbuilder`：

```
java -jar mplemonbuilder.jar --group-id=com.jnosqlmvc --project-name=jnosqlmvc-jwt --realm-name=jnosql-realm --header-key=my-header-key --issuer=http://www.jnosql.org/spec/ --roles=web,mobile
```

将要求提供版本号、Web 应用程序名称、生成 `jwt` 的应用程序名称以及项目生成的路径。在下面的图中，我们看到了 MP Lemon Builder 控制台：

![](img/9-13.jpg)

**图 9.14**

创建了 `jnosqlmvc-jwt` 目录，并在其中两个两个项目：`jnosqljwt` 和 `jnosqlweb`。

## 分析项目：jnosqljwt

从我们喜爱的编辑器中打开项目，示例使用了 NetBeans IDE：

![](img/9-14.jpg)

**图 9.15**

该项目有两个类，其中 `CypherService.java` 被用于创建令牌。以下是 `CypherService.java` 类的代码：



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

```java
@javax.enterprise.context.ApplicationScoped
public class CypherService {
    private static final Logger LOG = Logger.getLogger(CypherService.class.getName());
    private String issuer;
    private int tokenValid;
    private String audience;
    private String headerKey;
    private final Collection<String> roles = new LinkedHashSet<>();
    @javax.annotation.PostConstruct
    public void init() {
        Security.addProvider(new BouncyCastleProvider());
        LOG.info("Credentials loaded");
    }

    public String createToken(PrivateKey key, String username, Collection<String> groups) {
        LocalDateTime now = LocalDateTime.now();
        LocalDateTime expiration = now.plus(tokenValid, ChronoUnit.SECONDS);
        return Jwts.builder()
            .setHeaderParam("typ", "JWT")
            .setIssuedAt(Date.from(now.atZone(ZoneId.systemDefault()).toInstant()))
            .setExpiration(Date.from(expiration.atZone(ZoneId.systemDefault()).toInstant()))
            .signWith(SignatureAlgorithm.RS256, key)
            .setSubject(username)
            .setAudience(audience)
            .setHeaderParam("kid", headerKey)
            .claim("groups", groups)
            .setId(UUID.randomUUID().toString())
            .setIssuer(issuer).compact();
    }

    public PrivateKey readPrivateKey() throws IOException, NoSuchAlgorithmException, InvalidKeySpecException {
        try (InputStream is = CypherService.class.getResourceAsStream("/jwt-config.json")) {
            JsonObject json = Json.createReader(is).readObject();
            String keyString = json.getString("private-key");
            this.issuer = json.getString("issuer");
            this.audience = json.getString("audience", "audience");
            json.getJsonArray("roles").stream()
                .map((v) -> (JsonString) v).forEachOrdered((s)
                -> roles.add(s.getString()));
            this.tokenValid = json.getInt("token-valid");
            this.headerKey = json.getString("header-key");
            byte[] encoded = Base64.getDecoder().decode(keyString);
            return KeyFactory.getInstance("RSA").generatePrivate(new PKCS8EncodedKeySpec(encoded));
        }
    }

    public Collection<String> getRoles() {
        return roles;
    }
}
```

`http --form :8080/jnosqljwt/auth username=userjnosql password=userjnosql`

它生成了必须复制并用于我们应用程序的令牌：

![](img/9-16.jpg)

**图 9.17**

要验证 JWT 令牌，请访问 `https://jwt.io/` 并粘贴生成的代码。它将向我们显示解码后的令牌：

![](img/9-17.jpg)

**图 9.18**

## jnosqlweb

如下截图所示，从 NetBeans IDE 或你最喜欢的编辑器打开该项目：

![](img/9-18.jpg)

**图 9.19**

该项目包含以下文件：

*   `JAXRSConfiguration.java`：定义微服务的路径并建立身份验证将通过 MP-JWT 进行。MicroProfile JWT RBAC 规范定义了 `LoginConfig` 注解，以提供与 `web.xml` 文件中的 `login-config` 元素相同的信息，这需要一个继承自 JAX-RS Application 的类：

    ```
    @ApplicationPath("resources")
    @LoginConfig(authMethod = "MP-JWT")
    @DeclareRoles({"web","mobile"})
    public class JAXRSConfiguration extends Application {
    }
    ```

*   规范定义了：

    *   `java.security.Main` 标识 JWT 的主体 (`Main`)。

    *   一个 MP-JWT 实现，用于支持作为 `JsonWebToken` 身份验证的调用者注入，并需要 `@RequestScoped` 范围。

`PingResource.java` 类是一个可以通过路径 `/ping` 访问的微服务。`all` 路径使用了 `@PermitAll` 注解允许所有角色访问，而 `secure` 路径仅允许具有 `{"web", "mobile"}` 角色的用户访问。以下代码为 `PingResource.java` 类：

```java
@Path("ping")
@Produces(TEXT_PLAIN)
public class PingResource {
    @Inject
    private Principal principal;
    @Inject
    private JsonWebToken jwt;
    @GET
    @PermitAll
    @Path("all")
    public String ping() {
        return principal.getName() + jwt.getGroups();
    }
    @GET
    @RolesAllowed({"web","mobile"})
    @Path("secure")
    public String pingSecure() {
        return principal.getName() + jwt.getGroups();
    }
}
```

然后从 IDE 或通过控制台命令生成应用程序的 `.war` 文件：

```bash
cd jnosqlweb/
mvn clean install
```

在 Payara Server 上执行部署应用程序，这样你就可以运行两个应用程序了：

![](img/9-20.jpg)

**图 9.20**

从控制台执行以下命令访问 `all` 路径：

`http :8080/jnosqlweb/resources/ping/all`

![](img/9-21.jpg)

**图 9.21**

现在尝试使用以下命令访问 secure：

`http :8080/jnosqlweb/resources/ping/secure`

如图像所示，没有授权的访问。你必须指定为该用户生成的令牌：

![](img/9-22.jpg)

**图 9.22**

使用之前为 `userjnosql` 创建的令牌，或为另一个 `userjmoordb` 创建一个。使用以下命令：

`http --form :8080/jnosqljwt/auth username=userjmoordb password=userjmoordb`

复制生成的令牌：

![](img/9-23.jpg)

**图 9.23**

通过复制末尾的令牌并在前后添加引号再次运行它。如下所示：

![](img/9-24.jpg)

**图 9.24**

将生成类似下方的输出，显示用户以及该令牌拥有的角色：

```http
HTTP/1.1 200 OK
Content-Length: 19
Content-Type: text/plain
Server: Payara Server 5.194 #badassfish
X-Frame-Options: SAMEORIGIN
X-Powered-By: Servlet/4.0 JSP/2.3 (Payara Server 5.194 #badassfish Java/AdoptOpenJDK/1.8)
userjmoordb[mobile]
```

## 结论

本章展示了 Eclipse Krazo 的一些特性以及使用 Microprofile JWT 的 `IdentityStore` 实现身份验证机制。我们包含了 MP Lemon Builder 应用程序的使用，它自动化了令牌创建和身份验证的整个过程。这些是构建 Web 应用程序特别是微服务时至关重要的特性。

在下一章中，我们将观察如何使用针对容器（如 Docker）优化的工具来执行应用程序测试。

## 问题

1. Eclipse Krazo 会取代 Java Server Faces 吗？

2. 你在应用程序中使用了哪些安全机制？

3. 你在应用程序中使用了 JWT 吗？

# 第 10 章

## 测试与持续集成

## 引言

如今，应用程序的质量需要测试。在本章中，我们将展示一些方法。

## 结构

*   Testcontainers

    *   WebDriver Containers

    *   Selenium

    *   创建容器

    *   支持的运行时

    *   共享容器

    *   持续集成与持续交付

    *   Jenkins

    *   Microsoft Azure

    *   Tekton

## 目标

本章的目标是展示如何使用容器。

## Testcontainers 简介

Testcontainers 是一个 Java 库，支持 JUnit 测试，提供常用数据库、Selenium Web 浏览器或任何可以在 Docker 容器中运行的丢弃实例。你可以从 `https://www.testcontainers.org/` 获取更多信息。

## 测试 Eclipse Krazo

为了测试我们应用程序的视图，我们可以使用 Selenium。Testcontainers 为我们提供了容器的集成支持，将在将在文中描述。

## WebDriverContainers

我们的许多应用程序需要测试视图并与按钮、表格、表单等各种组件交互，并了解我们应用程序的行为。在 Java 应用程序测试框架中，Selenium 是一个值得考虑的替代方案。你可以访问他们的网站 `https://selenium.dev/` 查看。

Testcontainers 支持 WebDriver 容器，这允许我们通过 Selenium 等项目实例化包含 Web 浏览器的容器。

主站 `https://www.testcontainers.org/modules/webdriver_containers/` 描述了一些优势，例如：

*   兼容 Selenium 2/Webdriver 测试。

*   测试容器单元与 Docker 安装配合工作。你不需要指定任何浏览器。

*   浏览器始终从纯镜像启动。

*   保证了浏览器与 Selenium 之间的兼容性。

## Selenium

它提供了一套自动化 Web 浏览器测试工具，可以模拟用户与应用程序的交互。

*   **Web Driver:** 这是一个允许我们控制网络浏览器的 API。每个网络浏览器都有其 `WebDriver` 的实现。

*   **WebElement:** 代表页面内的 DOM 树元素（标签、按钮、文本框等）。

我们可以通过以下方式定位元素：

*   `name`

*   `id`

*   `tag name`

*   `xpath`

*   `xss selector`

*   `class name`

以下是元素选择器的示例：

*   `driver.findElement(By.name("name"))`

*   `driver.findElement(By.id("name"))`

*   `driver.findElement(By.cssSelector("input[type='submit']")).click();`

## ChromeDriver

为了运行测试，我们需要在计算机上安装 `ChromeDriver`。你可以从 `https://sites.google.com/a/chromium.org/chromedriver/downloads` 下载它。

请按照以下步骤操作：

*   解压 `chromedriver_linux64 file.zip`

*   将 `chromedriver` 文件复制到 `/usr/bin` 目录

    *   `cp chromedriver /usr /bin`

*   赋予执行权限

    *   `sudo chmod + x/usr/bin /chromedriver`

*   如果你使用的是其他浏览器，请查阅相关要求的的文档。

如你所见，我们可以访问网站的任何元素，甚至可以在按钮和其他元素上模拟事件。该示例基于上一章节中开发的 `krazosguide` 项目。编辑 `AppController.java` 类并添加模型资源，完整代码所示：

```java
@Path("app")
@Controller
public class AppController {
  @Inject
  Models models;
  @Inject
  Greeting greeting;
  @GET
  public String sayHello() {
    return "hello.jsp";
  }
  @GET
  @Path("view")
  @View("hello.jsp")
  public void view() {
    this.models.put("message", "Welcome from view");
    this.models.put("resource", "view");
  }
  @GET
  @Path("response")
  public Response response() {
    this.models.put("message", "Welcome from response");
    this.models.put("resource", "response");
    return Response.status(Response.Status.OK)
    .entity("hello.jsp")
    .build();
  }
  @GET
  @Path("viewable")
  public Viewable viewable() {
    this.models.put("message", "Welcome from viewable");
    this.models.put("resource", "viewable");
    return new Viewable("hello.jsp");
  }
  @GET
  @Path("cdi")
  public String cdi() {
    this.models.put("message", "Welcome from CDI");
    this.models.put("resource", "cdi");
    greeting.setMessage("Welcome from CDI/Greeting");
    return "hello.jsp";
  }
}
```

修改 `hello.jsp` 页面并添加一个输入元素以在网站上显示文本框：



```xml
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html lang="en">
<head>
<title>Hello!</title>
</head>
<body>
<form>
<h2 id="message">${message}</h2>
<input name="textfield" size="45" type="text" value=${resource} />
</form>
</body>
</html>
```

你想验证当从浏览器访问 URL `http://localhost:8080/krazosguide/mvc/app/view` 时，是否会产生类似于后续页面所示输出：

![](img/10-1.jpg)

**图 10.1**

让我们创建一个测试，检查 `<h2>` 和文本框的值，以确保它们显示了预期的结果。记住，方法 `view()` 被调用并将赋值给 `Models`，这些值将在 `hello.jsp` 页面中显示：

```java
@GET
@Path("view")
@View("hello.jsp")
public void view() {
  this.models.put("message", "Welcome from view");
  this.models.put("resource", "view");
}
```

在 Google Chrome 或 Firefox 浏览器中，我们可以安装 Xpath Finder 扩展，它可以生成组件的 `xpath`。

在激活扩展的情况下，我们将光标置于文本上，它会告诉我们元素 `<h2>` 的路径为 `/html/body/h2`，如下截图所示：

![](img/10-2.jpg)

**图 10.2**

编辑 `pom.xml` 文件并添加以下依赖：

```xml
<properties>
  <testcontainers.version>1.12.4</testcontainers.version>
  <selenium-remote-driver.version>3.141.59</selenium-remote-driver.version>
</properties>
<!--Test Containers -->
<dependency>
  <groupId>org.testcontainers</groupId>
  <artifactId>testcontainers</artifactId>
  <version>${testcontainers.version}</version>
</dependency>
<dependency>
  <groupId>org.testcontainers</groupId>
  <artifactId>selenium</artifactId>
  <version>${testcontainers.version}</version>
</dependency>
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-remote-driver</artifactId>
  <version>${selenium-remote-driver.version}</version>
</dependency>
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-chrome-driver</artifactId>
  <version>${selenium-remote-driver.version}</version>
</dependency>
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-support</artifactId>
  <version>3.141.59</version>
</dependency>
<dependency>
  <groupId>org.slf4j</groupId>
  <artifactId>slf4j-jdk14</artifactId>
  <version>1.7.29</version>
</dependency>
```

以下将是结果。

我们将遵循的步骤是：

1. 执行 Web 项目。
2. 从 NetBeans IDE 运行测试。
3. 选择 `AppControllerTest` `.java` 文件，右键点击并点击 **Test File**（测试文件）选项。以下截图显示了运行测试的过程。

![](img/10-3.jpg)

**图 10.3**

以下截图显示了测试如何在指定的容器上运行：

![](img/10-4.jpg)

**图 10.4**

执行结束时发送了一条错误消息，其中一个测试失败了。具体来说是 `viewTest()`，因为期望 `view1` 的值但它返回的是一个视图。如下所示：

![](img/10-5.jpg)

**图 10.5**

显示了如下更详尽的消息：

`viewTest(com.bpb.book.AppControllerTest) Time elapsed: 10.097 s <<< FAILURE!`

`org.junit.ComparisonFailure: expected:<view[1]> but was:<view[]>`

`at com.bpb.book.AppControllerTest.viewTest(AppControllerTest.java:37)`

以下将是结果：

`Failures:`

```text
AppControllerTest.viewTest:37 expected:<view[1]> but was:<view[]>
```

`Tests run: 3, Failures: 1, Errors: 0, Skipped: 0`

`------------------------------------------------------------------------`

`BUILD FAILURE`

我们自动执行的操作就像是打开浏览器并输入地址然后获取消息。文本框包含的值是 `view` 而不是测试中指示的 `view1`，这就是生成错误的原因：

![](img/10-6.jpg)

**图 10.6**

我们修改了测试，指示我们应该将 `view` 的值返回到文本框的内容。它看起来像这样：

```java
@Test
public void viewTest() {
    RemoteWebDriver driver = chrome.getWebDriver();
    driver.get(url + "/mvc/app/view");
    WebElement element = driver.findElement(By.name("textfield"));
    String resource = element.getAttribute("value");
    assertEquals("view", resource);
    driver.close();
}
```

再次运行测试，在最后你将得到以下结果：

`Tests run: 3, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 74.31 s - in com.bpb.book.AppControllerTest`

`Results:`

`Tests run: 3, Failures: 0, Errors: 0, Skipped: 0`

由于 NetBeans IDE 显示为绿色，表示所有测试已成功通过：

![](img/10-7.jpg)

**图 10.7**

使用命令通过 Maven 运行测试：

```bash
mvn test
```

在 Selenium 门户中有一个如何测试其他组件的完整示例，这是对它们使用的简单介绍。例如，我们可以为输入文本赋值：

```java
WebElement element = driver.findElement(By.name("textfield"));
element.sendKeys("From test");
```

控制页面元素事件始终始终以一种方式进行，例如，点击事件：

```java
WebElement button = driver.findElement(By.name("buttonHello"));
button.click();
```

## 测试容器

`TestContainer` API 提供了一个 `GenericContainers` 的类，它可以帮助在没有特殊设置的情况下运行容器。注解 `@ClassRule` 在测试之前触发被标记注解的方法。

此方法可以用于初始化与 NoSQL 数据库的连接，如 `MongoDB`、`OrientDB` 以及许多其他。通过 `GenericContainers` 可以建立：

- `withExposedPorts`：暴露端口；
- `withEnv`：建立环境变量；
- `withCommand`：允许你执行命令；
- `withLogConsumer`：注册日志的 API；
- `withNetwork`：允许你自定义网络。

它还为我们提供了方法：

- `getMappedPort()`：映射端口；
- `getFirstMappedPort()`：第一个暴露的端口；
- `getContainerIpAddress()`：IP 地址；
- `execInContainer`：执行类似于 `docker exec` 的命令。

在接下来的示例中，我们使用 `MongoDB` 数据库并暴露端口 `27017`：

```java
@ClassRules
public GenericContainer container = new GenericContainer("mongodb:latest")
    .withExposedPorts(27017,27017);
Integer firstMappedPort = container.getFirstMappedPort();
```

你可以在以下链接中找到进一步的参考：[`www.testcontainers.org/features/creating_container`](https://www.testcontainers.org/features/creating_container)

## MicroShed 测试

MicroShed 是一个非常有用的工具，让我们以简单且快速的方式使用 Docker 镜像创建并执行测试。它的特殊之处在于帮助测试准备好生产的容器。MicroShed 允许你使用容器编写和测试 Microprofile 和 Jakarta EE。

它已在以下环境进行过测试：

- OpenLiberty
- Wildfly
- Payara Micro
- Apache TomEE

Microshed 方便为使用 JAX-RS 创建的端点创建测试。你可以用于创建测试的注解有：

- `@MicroShedTest`：创建集成测试，允许注入 JAX-RS。
- `@Container`：注解在仓库中查找 Dockerfile 并启动容器，测试将在容器加载后运行。如果 Docker 容器镜像上的标签未指定，你可以指定要使用的特定适配器。你可以使用 `ApplicationContainer`，或者如果指定了容器依赖（例如 `PayaraMicro`），通过 `MicroprofileApplication` 使用。

```java
@Container
public static ApplicationContainer app = new ApplicationContainer()
    .withAppContextRoot("/myservice");
```

或：

```java
@Container
public static MicroProfileApplication app = new MicroProfileApplication();
```

- `@RESTClient`：它允许注入 Rest 客户端并调用 HTTP 请求。

## 支持的运行时

### Open Liberty

**Maven 依赖：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**等待：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**等待 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**



```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 file：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

## Payara Micro

**Maven 依赖：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-micro</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 Dockerfile：**

```dockerfile
FROM payara/micro:593
```

**main/config：**

```dockerfile
COPY src/config
CMD ["--deployment", "/opt/payara"]
```

## Payara Server

**Maven 依赖：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-payara-server</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 Dockerfile：**

```dockerfile
FROM payara/server-full:593
```

**target/myservice.war：**

```dockerfile
ADD target/myservice.war /opt/payara
```

## Wildfly

**通用 Maven 依赖：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-testcontainers</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

**示例 Dockerfile：**

```dockerfile
FROM jboss/wildfly
```

**build/libs/myservice.war：**

```dockerfile
ADD build/libs/myservice.war /opt/jboss/wildfly/deployments/
```

## 共享容器

我们通常对应用程序进行多次测试，通过使用共享容器可以避免在每个测试开始时加载容器。使用`@SharedContainerConfig`注解在第一个测试运行之前启动容器。如下代码所示：

```java
public class AppContainerConfig implements SharedContainerConfiguration {
    @Container
    public static ApplicationContainer app = new ApplicationContainer()
        .withAppContextRoot("/openliberty");
}

@MicroShedTest
@SharedContainerConfig(AppContainerConfig.class)
public class TestPeople {
    // ...
}

@MicroShedTest
@SharedContainerConfig(AppContainerConfig.class)
public class TestCountry{
    // ...
}
```

## 使用 OpenLiberty 的示例

我们将使用 OpenLiberty 创建容器测试示例。对于这一点，我们需要一组要求：

- Docker
- Apache Maven 或 Gradle
- Apache NetBeans IDE

创建一个 Maven（在本例中）或 Gradle 应用程序。从 Apache NetBeans 执行以下步骤：`File | New Project | Categories,`选择`Java With Maven`和`Web Application.`

向向框填充以下信息：

- `Project Name:` `openlibertytest`
- `Group id`: `com.bpb.jakarta.nosql`
- `Version`: `1.0-SNAPSHOT`
- `Package`: `com.bpb.jakarta.nosql.openlibertytest`

不要提供任何服务器，但在下拉框`JavaEE Version`中选择`JavaEE 8` web 并点击`Finish`。

1. 添加测试依赖项。在你创建的项目中，进入`pom.xml`文件，并在下方添加 Microshed 和 JUnit 依赖项：

```xml
<dependency>
    <groupId>org.microshed</groupId>
</dependency>
```

```xml
<dependency>
    <artifactId>microshed-testing-testcontainers</artifactId>
    <version>0.6.1.1</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.4.2</version>
    <scope>test</scope>
</dependency>
```

### 2. 配置项目以发现 OpenLiberty

在项目的`/src/main/liberty/config`文件夹下创建`server.xml`文件，并添加以下内容：

```xml
<server>
    <featureManager>
        <feature>jaxrs-2.1</feature>
        <feature>jsonb-1.0</feature>
        <feature>mpHealth-2.0</feature>
        <feature>mpConfig-1.3</feature>
        <feature>mpRestClient-1.1</feature>
        <feature>beanValidation-2.0</feature>
        <feature>cdi-2.0</feature>
    </featureManager>
</server>
```

### 3. 创建并配置 Docker 文件

通过菜单`File | New File | DockerFile.`创建`DockerFile`。

以下是`DockerFile`的内容：

```dockerfile
FROM openliberty/open-liberty:full-java8-openj9-ubi
COPY src/main/liberty/config /config/
ADD target/openlibertytest.war /config/dropins
```

### 4. 使用日志和执行插件增强项目

在`pom.xml`中添加额外的依赖：

- **通过 SLF4J 处理日志：**

```xml
<dependency>
    <groupId>org.slf4j</groupId>
    <artifactId>slf4j-log4j12</artifactId>
    <version>1.7.29</version>
    <scope>test</scope>
</dependency>
```

- **用于 OpenLiberty 容器测试：**

```xml
<dependency>
    <groupId>org.microshed</groupId>
    <artifactId>microshed-testing-liberty</artifactId>
    <version>0.6.1.1</version>
</dependency>
```

通过包含构建后的最终文件名来修改构建（build）部分。`finalName`部分如下：

```xml
<finalName>openlibertytest</finalName>
```

在插件（plugin）部分，按如下所示配置`maven-failsafe-plugin`：

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-failsafe-plugin</artifactId>
    <version>3.0.0-M3</version>
    <executions>
        <execution>
            <phase>integration-test</phase>
            <id>integration-test</id>
            <goals>
                <goal>integration-test</goal>
            </goals>
            <configuration>
                <trimStackTrace>false</trimStackTrace>
            </configuration>
        </execution>
    </executions>
</plugin>
```

在`/src/test/resources`文件夹下创建带有基础配置的`log4j.properties`文件。内容类似于于：

```properties
log4j.rootLogger=INFO, stdout
log4j.appender=org.apache.log4j.ConsoleAppender
log4j.appender.layout=org.apache.log4j.PatternLayout
log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout
log4j.appender.stdout.layout.ConversionPattern=%r %p %c %x - %m%n
log4j.logger.org.microshed.testing=DEBUG
```

我们使用了官方门户 microshed 提供的示例作为基础，并适配到我们之前的示例，在该示例中使用了`Country`类：

```java
public class Country {
    @NotNull
    private String id;
    @NotNull
    @Size(min = 5, max = 50)
    private String name;
    @JsonbCreator
    public Country(@JsonbProperty("name") String name, @JsonbProperty("id") String id) {
        this.name = name;
        this.id = id;
    }
    @Override
    public boolean equals(Object obj) {
        if (obj == null || !(obj instanceof Country))
            return false;
        Country other = (Country) obj;
        return Objects.equals(id, other.id) && Objects.equals(name, other.name);
    }
    @Override
    public int hashCode() {
        return Objects.hash(id, name);
    }
    //Getters /Setters
}
```

将创建一个类来模拟仓库（repository），它可以可以是数据源（例如 MongoDB）。这是一个模拟数据库操作的简单类：

```java
@ApplicationScoped
public class CountryRepository {
    private final Map<String, Country> countryRepo = new HashMap<>();
    public String save(String name, String id) {
        Country country = new Country();
        // ... logic
        return id;
    }
}
```

如下所示的`CountryService`类：

```java
@ApplicationScoped
@Path("/country")
public class CountryService {
    @Inject
    CountryRepository countryRepository;

    @GET
    @Produces(MediaType.APPLICATION_JSON)
    public List<Country> findAll() {
        return countryRepository.findAll();
    }

    @GET
    @Path("/{id}")
    public Country getCountry(@PathParam("id") String id) {
        Country country = countryRepository.findById(id);
        if (country == null) {
            throw new NotFoundException("Country with id " + id + " found.");
        }
        return country;
    }

    @POST
    public String create(@QueryParam String name, @QueryParam String id) {
        return countryRepository.save(name, id);
    }

    @PUT
    @Path("/{id}")
    public void updateCountry(@PathParam("id") String id, Country p) {
        countryRepository.update(id, p);
    }

    @DELETE
    @Path("/{id}")
    public void deleteCountry(@PathParam("id") String id) {
        countryRepository.delete(id);
    }
}
```

要运行它，请在终端输入以下 Maven 命令：

```bash
mvn clean install.
```



以下截图显示了执行结果：

![](img/10-8.jpg)

**图 10.8**

## GenericContainer

使用公共静态的 `GenericContainer<?>` 可以定义泛型容器，例如 MongoDB。通过 `dependOn()` 方法，你可以指定主容器在泛型容器启动之前不启动。如下代码段所示：

```java
@Container
public static GenericContainer<?> mongo = new GenericContainer<>("mongo:3.4")
    .withExposedPorts(27017)
    .withNetworkAliases("testmongo");

@Container
public static ApplicationContainer app = new ApplicationContainer()
    .withAppContextRoot("/openlibertytest")
    .withReadinessPath("/health/ready")
    .dependsOn(mongo);
```

某些容器方法允许获取 IP、端口等信息：

```java
@Test
public void testMongoDB() {
    mongo.start();
    String connection = "mongodb://" + mongo.getContainerIpAddress() + ":" + mongo.getMappedPort(27017);
    MongoClient mongoClient = MongoClients.create(connection);
    MongoDatabase database = mongoClient.getDatabase("test");
    MongoCollection<Document> collection = database.getCollection("country");
    Document document = new Document("name", "Panama").append("id", "pa");
    collection.insertOne(document);
    Country country = convert(collection.find(eq("name", "Panama")));
    assertEquals("Panama", country.getName());
}
```

你可以在 GitHub 仓库中参考本书中的示例。可以看到微服务测试是以非常简单的方式实现的。`Microshed` 为我们提供了一系列额外设施，如 JWT 测试、可以在主 Microshed 站点进行扩展的 `ApplicationEnvironment`。

## 持续集成与持续交付（CI/CD）

几年前，Martin Fowler 将[持续集成](https://martinfowler.com/articles/continuousIntegration.html)定义为：持续集成是一种软件开发实践，其中团队成员频繁地集成他们的工作，通常每个人每天至少集成一次——导致每天有多次集成。每次集成都通过自动化构建（包括测试）进行验证，以便尽快检测到集成错误。许多团队发现这种方法显著减少了集成问题，并允许团队更快速地开发出凝聚性的软件。本文是对持续集成的简要概述，总结了该技术及其当前用法。

## Jenkins

多年来 Jenkins（[`www.jenkins.io/`](https://www.jenkins.io/)）一直是用于持续集成的主要自动化服务器之一。正如其网站上解释的，Jenkins 允许你自动化构建、测试和交付或部署软件的任务。

它可以原生安装在操作系统上，可以使用 WAR 文件运行，也可以像目前大多数方式那样使用 Docker 镜像运行。许多平台集成了 Jenkins 流水线，例如 CloudBees、Red Hat OpenShift 等。

我们将关注一个使用流水线的小应用程序。Jenkins 流水线由一组插件组成，允许 Jenkins 在 Jenkins 内部集成持续流水线。它是通过一个名为 `Jenkinsfile` 的简单文本文件完成的。你可以在站点找到官方信息（[`www.jenkins.io/doc/book/pipeline/`](https://www.jenkins.io/doc/book/pipeline/)）。

## 创建简单的 Pipeline

以下是创建非常简单的流水线的方法。你必须使用 Docker、原生安装或 Jenkins `file.war` 运行 Jenkins 实例。

以下截图显示了 Jenkins 的初始界面，我们必须输入图像出现的提示中指定的密码：

![](img/10-9.jpg)

**图 10.9**

Jenkins 拥有大量的插件，其中我们可以提到 JUnit、Sonar、PMD、CheckStyle、Maven、Gradle。你可以在门户搜索适合你需求的插件列表。在我们的情况下，继续选择“安装建议的插件”（Install suggested plugins）选项，如下所示：

![](img/10-10.jpg)

**图 10.10**

我们必须等待插件安装完成，记住你可以在任何时候添加或删除插件。下面的截图显示了安装进度：

![](img/10-11.jpg)

**图 10.11**

下一步是创建 Jenkins 管理员凭据。下面的截图显示了创建它所需的数据：

![](img/10-12.jpg)

**图 10.12**

然后我们配置将用于 Jenkins 的服务器 URL。以下截图显示了配置界面：

![](img/10-13.jpg)

**图 10.13**

通过这些步骤，我们的 Jenkins 服务器已准备好为我们的项目工作，如下图所示：

![](img/10-14.jpg)

**图 10.14**

下一步是创建一个使用简单示例 Pipeline 的任务。有几种方法可以使用 Jenkins 提供的模板使用 Pipeline，其中包括连接代码仓库、运行测试、创建可分发包等许多任务。记住，对于 Jakarta EE 和 MicroProfile 应用，以下截图向我们展示了创建简单任务的过程：

![](img/10-15.jpg)

**图 10.15**

点击 `Create new task`（创建新任务）并输入名称 `hellipeline`，如下所示选择 `Pipeline`：

![](img/10-16.jpg)

**图 10.16**

在 `Pipeline` 部分，我们选择 GitHub YAML：

![](img/10-17.jpg)

**图 10.17**

你可以为你的设置触发器，它将执行指定的作业。下面的截图显示了如何配置：

![](img/10-18.jpg)

**图 10.18**

下图显示了流水线的执行结果：

![](img/10-19.jpg)

**图 10.19**

我们也可以创建一个 `jenfile` 文件并将其放入代码仓库。你可以在官方网站查看更多信息（[`www.jenkins.io/doc/pipeline/tour/hello-world/`](https://www.jenkins.io/doc/pipeline/tour/hello-world/)）。

## 持续交付

这是一项在许多工具帮助下演变巨大的实践，主要通过测试确保项目的开发。[`continuousdelivery.com/`](https://continuousdelivery.com/) 门户为我们提供了以下定义：持续交付是将所有类型的更改（包括新功能、配置更改、错误修复和实验）安全、快速且以可持续的方式交付到生产环境或用户手中的实践。

CI/CD 是 DevOps 的重要组成部分，容器编排是当今应用程序开发中使用越来越多的实践之一。许多云平台为我们提供 CI/CD 流水线环境。例如，Microsoft Azure 允许我们非常方便地使用 Azure Pipeline。

访问主页 [`github.com/marketplace/azure-pipelines`](https://github.com/marketplace/azure-pipelines) 并使用可用的选项：

![](img/10-20.jpg)

**图 10.20**

你可以创建组织、授权访问仓库并创建 Pipeline：

![](img/10-21.jpg)

**图 10.21**

然后选择 GitHub YAML：

![](img/10-22.jpg)

**图 10.22**

你必须编辑 `azure-pipelines.yml` 文件，并根据你的需求对其进行调整：

```yaml
## Starter pipeline
### 从一个最小流水线开始，你可以自定义它来构建和部署你的代码。
### 添加构建、运行测试、部署等操作的步骤：
### https://aka.ms/yaml
trigger:
  - master
pool:
  vmImage: 'ubuntu-latest'
steps:
  - script: echo Hello, world!
    displayName: 'Run a one-line script'
  - script: |
      echo Add other tasks to build, test, and deploy your project.
      echo See https://aka.ms/yaml
    displayName: 'Run a multi-line script'
```

建立适当的计划并执行流水线：

![](img/10-24.jpg)

**图 10.24**

下图显示了可以跟踪的各种执行情况：

![](img/10-25.jpg)

**图 10.25**

你可以选择创建环境（Environment）：

- 无（None）
- Kubernetes
- 虚拟机（Virtual Machines）

如下截图所示，配置你需要的发布类型：

![](img/10-26.jpg)

**图 10.26**

## Tekton 框架

Tekton 是一个基于 Kubernetes 的框架，使得 CI/CD 系统的创建更加灵活。通过抽象实现细节，可以使用它测试不同的云供应商（<https://cloud.google.com/tekton/>）。

组件包括：

- **Task**：这些是必须执行的任务。它们类似于 Kubernetes 集群中的 Pod。
- **TaskRunner**：执行定义的任务。
- **PipelineResources**：它定义了任务使用的制品。
- **PipelineRun**：定义要执行的任务列表。

要求非常基础：

- **安装 Kubernetes：**

```bash
snap install kubectl --classic
kubectl version
```

要安装它，我们遵循以下步骤：

```bash
kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml
```

通过以下命令完成执行：

```bash
kubectl get pods --namespace tekton-pipelines
```

以下示例是官方文档的一部分，你可以在 [`github.com/tektoncd/pipeline/blob/master/docs/tutorial.md`](https://github.com/tektoncd/pipeline/blob/master/docs/tutorial.md) 中找到。

- **创建一个 Task：**

```yaml
apiVersion: tekton.dev/v1alpha1
kind: Task
metadata:
  name: echo-hello-world
spec:
  steps:
  - name: echo
    image: ubuntu
    command:
    - echo
    args:
    - "hello world"
```

- **创建一个 TaskRunner：**

```yaml
apiVersion: tekton.dev/v1alpha1
kind: TaskRun
metadata:
  name: echo-hello-world-task-run
spec:
  taskRef:
    name: echo-hello-world
```

- **现在创建一个 PipelineResources：**

```yaml
apiVersion: tekton.dev/v1alpha1
kind: PipelineResource
metadata:
  name: skaffold-git
spec:
  type: git
  params:
    - name: revision
      value: master
    - name: url
      value: https://github.com/GoogleContainerTools/skaffold
```

- **创建 Pipeline：**

```yaml
apiVersion: tekton.dev/v1alpha1
kind: Pipeline
metadata:
  name: tutorial-pipeline
spec:
  resources:
    - name: source-repo
      type: git
    - name: web-image
      type: image
  tasks:
    - name: build-skaffold-web
      taskRef:
        name: build-docker-image-from-git-source
      params:
        - name: pathToDockerFile
          value: Dockerfile
        - name: pathToContext
          value: /workspace/docker-source/examples/microservices/leeroy-web # 配置：可能根据你的源代码更改
      resources:
        inputs:
          - name: docker-source
            resource: source-repo
        outputs:
          - name: builtImage
            resource: web-image
    - name: deploy-web
      taskRef:
        name: deploy-using-kubectl
      resources:
        inputs:
          - name: source
            resource: source-repo
          - name: image
            resource: web-image
      from:
        - build-skaffold-web
      params:
        - name: path
          value: /workspace/source/examples/microservices/leeroy-web/kubernetes/deployment.yaml # 配置：可能根据你的源代码更改
        - name: yamlPathToImage
          value: "spec.template.spec.containers[0].image"
```

如这些示例所示，使用 Tekton 非常简单。

## 结论

本章展示了如何使用 `TestContainers` 和 `Microshed` 创建测试，并展示了使用 Azure Pipeline 进行 CI/CD 的示例。此外，简要介绍了用于创建 CI/CD 流水线的 Tekton 框架。

在整本书中，介绍了用于 Jakarta Enterprise 应用程序开发的各种技术、API 和框架。

## 问题

1. 什么是 `TestContainers`？
2. 什么是 `Selenium`？
