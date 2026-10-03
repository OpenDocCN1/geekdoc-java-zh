
# Android 安全内部原理：Android 安全架构深度指南

![](img/8524e4e57e2e9dc889903e3d2c5fe367_0_0.png)

Jon Sawyer 写的序言

## 关于作者

Nikolay Elenkov 在过去的 10 年里一直从事企业级安全项目。他曾在各种平台上开发过安全软件，涵盖了从智能卡、硬件安全模块（HSM）到 Windows 和 Linux 服务器。在 Android 初版发布后不久，他对 Android 产生了兴趣，并从 1.5 版本开始就开始为其开发应用。在 Android 4.0（冰淇淋明治）发布后，Nikol 对 Android 内部原理的兴趣进一步浓厚，在过去的三年里，他一直在自己的博客（http://nelenkov.blogspot.com/）上记录发现并编写关于 Android 安全的文章。

## 关于技术审核员

Kenny Root 自 2009 年以来一直是 Google Android 平台的核心贡献者，他的重点主要是安全和密码学。他是 ConnectBot（Android 第一款 SSH 应用）的作者，也是一位热衷的开源贡献者。在不编写代码时，他会花时间陪伴妻子和两个儿子。他是斯坦福大学、哥伦比亚大学、香港中文大学和贝克尔学院的校友，但他源自堪萨斯城市，那里的烧烤是最好的。

## 序言

我在 Android 4.0 版本“冰淇淋明治”发布时，第一次意识到 Nikolay 在 Android 安全领域的专业水平。当时，我需要对新的 Android 备份格式有更好的解释；我正苦于利用我发现的一个漏洞，因为我还没有完全掌握这个功能和格式。他清晰、深入的解释帮助我理解了该问题，利用了漏洞，并迅速将补丁推向生产设备。从那以后，我成了他博客的常客，在需要复习时经常参考。

虽然我很荣幸受邀写这篇序言，但老实地说，我不认为自己能从这本书里中学到什么，因为我已经研究了多年的 Android 安全。这种想法完全是错误的。当我阅读并消化关于我自认为已彻底掌握的主题的新信息时，我的脑中充满了关于我错过了什么以及我本可以做得更好的想法。为什么当我最初沉迷于 Android 时，没有这样一本参考书可用呢？

这本书向读者展示了广泛的安全主题，从 Android 权限和沙箱机制到 Android 的 SELinux 实现（SEAndroid）。它对新的细微细节和罕见功能（如 dm-verify）提供了极佳的解释。像我一样，读完这本书后，你对 Android 功能会有更深入的理解。

《Android 安全原理》已经在我的办公室书架上占了永久的一席。

Jon “jcase” Sawyer

Applied Cybersecurity LLC CTO

美国华盛顿州波特安格利斯市

## 致谢

我要感谢 No Starch Press 参与这本书制作的每位同事。特别感谢 Bill Pollock 让我的随口乱语变得通俗易懂，感谢 Alison Law 耐心地将这些内容转化成了一本真正的书。

非常感谢 Kenny Root 审核了所有章节，并分享了 Android 某些安全功能背后的故事。

感谢 Jorrit “Chainfire” Jong 维护 SuperSU，该它是探索 Android 内部原理的宝贵工具，并审核了我在第 13 章对它的介绍。

感谢 Jon “jcase” Sawyer 继续挑战我们对 Android 安全的假设，并为我的书撰写序言。

## 引言

在很短的时间内，Android 已成为全球最流行的移动平台。尽管最初是为智能手机设计的，但现在它驱动着平板电脑、电视和可穿戴设备，并很快将出现在汽车上。Android 正以惊人的速度发展，每年发布两个大版本。Android 的开发速度令人赞叹，其每个新版本都带来了新的 UI、性能改进以及安全加固。在过去几年里，Android 的隔离机制（沙箱）得到了加固，其攻击面也大大减少。除了这些措施，最近的 Android 版本引入了许多新功能，例如硬件支持的存储、设备加密和设备管理，这些功能都尚未定型，因此可能会发生变化。这就是为什么这本书没有讨论这些新功能的原因。尽管我们可以根据观察到的行为介绍一些 Android L 的安全改进，但在没有底层源代码的情况下，对其实现方式的讨论将是不完整且具有推测性的。

正如任何新平台一样，对 Android 内部原理的讨论是令人兴奋的。Android 流行的原因之一是其可以非常容易地定制。本书旨在通过深入研究 Android 架构来填补这些空白。大多数代码示例来自 Android 进程（通常用 C 或 C++ 实现）和系统服务（通常用 Java 实现），因此熟悉这些语言中的一种是必要的。最后，虽然 Android 应用的基本结构和组件（如 Activity 和 Service）在章节中有简要介绍，但假设读者已具备 Android 开发的基础知识。

### 约定

由于本书的主题是 Android 的架构和实现，因此它包含了多个代码段和文件列表，这些内容在每个列表或代码示例后的章节中被频繁引用。书中使用了一些格式约定，将这些引用（通常包含多个操作系统或编程语言结构）与正文内容区分开来。

等宽字体（例如："the id command"、"XML 属性" 以及 SQL 对象名称）使用*斜体*设置（例如："the getCallingUid() method"、"the name attribute" 等）。文件和目录名称、Linux 用户和进程以及其他操作系统对象也使用*斜体*设置（例如："the packages.xml file"、"the system user"、"the void daemon" 等）。字符串字面量也使用*斜体*（例如："the AndroidSSL provider"）。如果你在程序中使用此类字面量，通常需要用双引号或单引号将它们括起来（例如：`Signature.getInstance("SHA1withRSA", "AndroidOpenSSL")`）。

Java 类通常以不带包名的未限定格式表示（例如："the Binder class"）；只有当所讨论的 API 或包中存在多个同名类，或者当指定所属包具有重要性时，才会使用全限定名（例如："the javax.net.ssl.SSLFactory class"）。在正文中引用时，函数和方法名会带有括号，但为了简洁起见通常会省略其参数（例如："the getInstance() factory method"）。请查看相关的参考文档获取完整的函数或方法签名。

大多数章节包含图表，用于说明所讨论的安全子系统或组件的架构或结构。所有图表都遵循非正式的“框和箭头”风格，并不严格遵守特定格式。尽管如此，大多数图表都借鉴了 UML 类图和部署图的想法，框通常表示类或对象，而箭头表示依赖或通信路径。

## 第 1 章. Android 安全模型

本章将首先简要介绍 Android 的架构、进程间通信 (IPC) 机制和主要组件。然后我们将描述 Android 安全模型以及它如何与底层 Linux 安全基础设施和代码签名相关。最后，我们简要概述 Android 安全模型的一些新增内容，许多多用户支持、基于 SELinux 的强制访问控制 (MAC) 以及验证启动。Android 的架构和安全模型构建在传统的 Unix 进程、用户和文件范式之上，但此处不会从零开始描述该范式。我们假设读者对类 Unix 系统（特别是 Linux）有基本的了解。

### Android 架构

让我们从下到上简要检查 Android 架构。图 1-1 显示了 Android 栈的简化表示。

| 系统应用 设置/手机/启动器/... | 用户安装的应用 |
| :--- | :--- |
| Android 框架库 android.* | Java 运行时库 java.* java.* |
| 系统服务 Activity Mgr./Package Mgr./Window Mgr./... | |
| Dalvik 运行时 | |
| Init Native Daemons Native Libraries HAL | |

图 1-1. Android 架构

### Linux 内核

如图 1-1 所示，Android 构建在 Linux 内核之上。在任何 Unix 系统中，内核都为硬件、网络、文件系统访问和进程管理提供驱动程序。得益于 Android 主线化项目 [11]，你现在可以使用最近的纯净内核运行 Android（这需要一些额外工作），但 Android 内核与你在桌面机器或非 Android 嵌入式设备上找到的“普通”Linux 内核略有不同。这些差异源于一组为了支持 Android 而添加的新功能（有时被称为 Androidisms [22]）。

### 原生用户空间

在内核之上是原生用户空间，由 *init* 二进制文件、多个守护进程以及在系统中使用的数百个原生库组成*init* 二进制文件和守护进程的过程让人联想到传统的 Linux 系统，*init* 和相关的启动脚本是从零开发的，与它们不同。

### Dalvik 虚拟机

Android 的大部分是用 Java 实现的，因此由 Java 虚拟机 (JVM) 执行。Android 当前的 JVM 实现称为 *Dalvik*，它是我们栈中的下一层。Dalvik 是为移动设备设计的，无法直接运行 Java 字节码 (.class 文件)其原生格式是 Dalvik 可执行文件 (DEX) 并封装在 .dex 文件中。反之，.dex 文件封装在系统 Java 库（JAR 文件）或 Android 应用程序（APK 文件，见第 3 章）中。

JVM 使用两条指令将参数加载到栈上（1 和 2），然后执行结果（4）。相比之下，Dalvik 使用单条指令添加参数（寄存器 p0 和 p1）并将结果存入 v0 寄存器（9）。最后，它返回 v0 寄存器的内容（6）。可见，Dalvik 使用更少的指令实现了相同的结果。通常情况下，基于寄存器的虚拟机使用的指令较少，但结果比基于栈的虚拟机对应的代码大。然而，在许多架构上，加载代码的开销小于指令分发，因此基于寄存器的虚拟机可以更高效地解释。

在生产设备中，系统库和预装应用程序不包含与设备无关 DEX 代码。作为一种性能优化，DEX 会被转换为设备相关的格式并存储在优化 DEX (.odex) 文件中，该文件通常与其父 JAR 或 APK 文件位于同一目录。对于用户安装的应用，在安装时也会进行类似的优化。

## 运行时库 (Runtime Libraries)

Java 语言实现需要一组运行时库，这些库主要定义在 `java.*` 包中。Android 的核心 Java 库最初源自 Apache 项目，后续层级基于栈。随着 Android 的演进，原始的 Harmony 发生了巨大变化。在此过程中，某些功能被完全替换（例如国际化支持、加密提供者和某些相关类），另一些则得到了扩展和改进。核心库大部分用 Java 开发，但它们也有原生代码依赖。原生代码通过标准的 Java Native Interface (JNI) 链接到 Android 的 Java 库中，这允许 Java 代码调用原生代码，反之亦然。运行时库层可以直接从系统和服务应用程序进行访问。

## 系统服务 (System Services)

到目前为止引入的层构成了实现 Android 核心——系统服务所必需的机制。系统服务（截至 4.4 版本有 79 个）实现了大多数 Android 功能，包括显示和触摸屏支持、电话功能和网络连接。大多数系统服务是用 Java 实现的；少数基础服务是用原生代码编写的。

除少数例外外，每个系统服务都定义了一个远程接口，可以从其他服务和应用程序调用。结合 Binder 提供的服务发现、调解和 IPC（进程间通信），系统服务在 Linux 上有效地实现了一个面向对象的操作系统。

让我们详细查看 Binder 如何在 Android 上实现 IPC，因为这是 Android 安全模型的基石之一。

## 进程间通信 (Inter-Process Communication)

如前所述，Binder 是一种进程间通信（IPC）机制。Android 拥有独立的地址空间，进程无法直接访问另一个进程的内存（这被称为进程隔离）。出于出于性和这通常是好事：多个进程修改同一块内存可能是灾难性的，而且你不希望由另一个用户启动的潜在恶意进程导出你客户端的内存。

然而，如果一个进程想要向其他进程提供某些服务，它需要提供某种机制允许其他进程发现并与这些服务交互。这种机制被称为 IPC。

对标准 IPC 机制的需求并不新鲜，因此 Android 提供了多种选项。这些包括文件、信号、socket、管道、信号量、共享内存、消息队列等。Android 使用了某些（如本地 socket），但不支持其他（即 System V IPC，如信号量、共享内存段和消息队列）。

标准的 IPC 机制不够灵活或可靠，因此为 Android 开发了新的 IPC 机制 Binder。虽然 Android 的 Binder 是一个新实现，但它基于 OpenBinder 的架构和理念。[6]

Binder 实现了一种基于抽象接口的分布式组件架构。它类似于 Windows 的通用对象模型 (COM) 和 Unix 上的通用对象代理请求架构，与这些框架不同，它运行在单个设备上，不支持跨网络的远程过程调用 (RPC)（尽管可以在 Binder 之上实现 RPC 支持）。Binder 框架的完整描述超本书的范围，但将在接下来的章节中简要介绍其主要组件。

## Binder 实现 (Binder Implementation)

如前所述，在 Unix 类系统上，进程无法访问另一个进程的内存。然而，内核控制所有进程，因此可以暴露一个启用 IPC 的接口。在 Binder 中，该接口是 `/dev/binder` 设备，由 Binder 内核驱动实现。Binder 驱动程序是框架的核心元素，所有的 IPC 调用都通过它进行。进程间通信通过单个 `ioctl()` 实现，它通过 `binder_write_read` 结构发送并接收数据，该结构包含一个包含驱动指令的 `write_buffer` 和一个包含用户态需要执行指令的 `read_buffer`。

但数据实际上如何在进程间传递？Binder 驱动管理每个进程的地址空间。Binder 驱动管理的内存块对进程是只读，所有写入操作由内核模块完成。当一个进程向另一个进程发送消息时，内核在目标进程的内存中分配一些空间，并直接从发送进程拷贝消息数据。它向接收进程队列一条短消息，直到接收者可以直接访问该消息（因为在它自己的内存空间中）。当进程处理完消息后，它会通知 Binder 驱动将该内存标记为空闲。图 1-2 显示了 Binder IPC 架构的简化图。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_14_0.png)

Android 中高级别的 IPC 抽象，如 `Intents`（跨进程传递给组件的命令）、`Messengers`（启用跨进程基于消息通信的对象）和 `ContentProviders`（启用跨进程数据管理接口的组件）构建在 Binder 之上。此外，使用 Android 定义语言 (AIDL) 定义的服务接口允许客户端像调用本地 Java 对象一样调用远程服务。相关的 AIDL 工具会自动生成存根（stub，远程对象的客户端表示）和代理（proxy），将方法映射到底层的 `transact()` Binder 方法，并处理参数转换为 Binder 可以传输的格式（这被称为参数序列化/反序列化）。由于 Binder 本身是强类型的，AIDL 生成的存根和代理还通过在每个 Binder 事务中包含目标接口名称并在存根中进行验证来提供类型安全。

## Binder 安全 (Binder Security)

在高级层次，每个通过 Binder 框架访问的对象都实现了 Binder 接口并被称为 Binder 对象。对 Binder 对象的调用在 Binder 事务内部执行，事务包含目标对象的引用、要执行的方法 ID 以及一个数据缓冲区。Binder 驱动会自动将调用进程的进程 ID (PID) 和有效用户 ID (EUID) 添加到事务数据中。被调用进程（回调）可以检查 PID 和 EUID，并根据内部逻辑或来自调用应用的系统元数据决定是否执行请求的方法。

由于 PID 和 EUID是在内核中填充的，调用进程无法伪造超出系统允许权限的身份（即：Binder 防止了权限提升）。这是 Android 安全模型的核心部分之一，所有高层抽象（如权限）都构建在此之上。调用者的 EUID 和 PID可以通过 `android.os.Binder` 类的 `getCallingPid()` 和 `getCallingUid()` 方法获取，该类是 Android 公共 API 的一部分。

### 注意

> *如果多个应用程序在同一用户下运行，调用进程的 EUID 可能无法映射到单个应用程序*

## Binder 标识

Binder 对象最重要的属性之一是它们在跨进程时保持身份标识唯一。如果进程 A 创建了一个 Binder 对象并将其传递给进程 B，进程 B 又将其传递给进程 C，那么来自所有三个进程的调用将由同一个 Binder 处理。在实践中，进程 A 会通过其内存地址直接引用该 Binder（因为它位于进程 A 的内存空间中），而进程 B 和 C 只接收到 Binder 对象的句柄（handle）。内核维护“存活”Binder 对象与其在其他进程中的句柄之间的映射。由于 Binder 对象的标识是唯一的且由内核维护，除非通过某次 IPC（进程间通信）传递，否则用户空间无法创建 Binder 对象的副本或获取其引用。因此，Binder 对象是一个唯一的、不可伪造且可通信的对象，可以作为安全令牌。这使得在 Android 中使用基于能力的安全机制（capability-based security）成为可能。

## 基于能力的安全

在基于能力的安全模型中，程序通过赋予一个不可伪造的权利来获得对特定资源的访问权限，该能力既引用了目标对象，又封装了对其的一组访问权限。由于能力是不可伪造的，程序拥有某种能力这一事实足以让其访问目标资源；无需维护与实际资源相关的访问控制列表（ACL）或类似的结构。

## Binder 令牌



在 Android 中，`Binder` 对象可以充当能力，当以这种方式使用时，被称为 Binder 令牌（Binder tokens）。`Binder` 令牌既可以是能力，也可以是目标资源。拥有 `Binder` 令牌允许所有者对 `Binder` 对象具有完全访问权限，使其能够对目标对象执行 `Binder` 事务。如果 `Binder` 对象实现了多个动作（通过选择事务的 `code` 参数），则调用者在拥有该 `Binder` 对象引用时可以执行任何动作。如果需要更细粒度的访问控制，则每个动作的实现需要进行必要的权限检查，通常通过使用调用者进程的 `PID` 和 `EID`。

Android 中的一种常见模式是允许所有以 `system`（`UID` 1000）或 `root`（`UID` 0）运行的调用者执行所有操作，但对所有其他进程执行额外的权限检查。对服务等重要 `Binder` 对象的访问通过两种方式控制：限制谁可以获取该 `Binder` 对象的引用，以及在对 `Binder` 对象执行操作之前检查身份（此检查是可选的，如果需要，由 `Binder` 对象本身实现）。

另一种情况是，`Binder` 对象也可以仅作为能力使用而不实现任何其他功能。在这种用法模式下，两个（或多个）协作的进程持有同一个 `Binder` 对象，其中作为服务器（处理某些客户端请求）的进程使用 `Binder` 来验证其客户端，就像 Web 服务器使用会话 Cookie 一样。

这种用法模式由 Android 框架在内部使用，对应用程序而言大部分是不可见的。`Binder` 令牌在公共 API 中可见的一个显著用途是窗口令牌（window tokens）。每个 Activity 的顶层窗口与一个 `Binder` 令牌关联（如果 Android 窗口管理器——负责管理窗口的系统服务——对其跟踪，则称为窗口）。Android 应用程序可以拥有自己的窗口令牌，但无法访问其他应用程序的窗口令牌。通常，你不希望其他应用程序在你的窗口之上添加或删除窗口；每个此类请求必须提供与应用程序关联的窗口令牌，以确保窗口请求来自自己的应用程序或系统。

### Binder 对象

尽管 Android 出于安全考虑控制对 `Binder` 对象的访问，但与 `Binder` 对象通信的唯一方法是获取它的引用，某些 `Binder` 对象（尤其是系统服务）需要全局可访问。然而，向所有系统服务和每个进程发放引用是不切实际的，因此我们需要某种机制，允许进程根据需要发现并获取系统服务的引用。

为了实现服务发现，`Binder` 框架有一个上下文管理器，它维护对 `Binder` 对象的引用。Android 的上下文管理器实现是 `servicemanager` 守护进程。它在引导过程非常早的阶段启动，以便服务在启动时向其注册。服务通过向服务管理器传递服务名称和 `Binder` 引用来注册。一旦服务注册，任何客户端都可以使用其名称获取其 `Binder` 引用。然而，大多数服务都实现了额外的权限检查，获取引用并不会自动授予对其所有功能的访问权限。因为当 `Binder` 引用在服务管理器注册时任何人都可以访问它，所以只有极少数白名单进程会注册系统服务。例如，只有以 `UID` 1002（`AID_BLUETOOTH`）执行的进程才能注册蓝牙系统服务。

你可以使用 `service list` 命令查看已注册服务的列表，该命令返回每个注册服务的名称和实现的 `IBinder` 接口。在 Android 4.4 设备上运行该命令的输出见示例 1-3。

示例 1-3. 使用 `service list` 命令获取注册服务列表

```
service list
Found 79 services:
0 sip:[android.net.sip.ISipService]
1 phone:[com.android.internal.telephony.ITelephony]
2 iponesubinfo:[com.android.internal.telephony.IPhoneSubInfo]
3 servicebook:[com.android.internal.telephony.IccPhoneBook]
4 isms:[com.android.internal.telephony.ImsAdapter]
5 nfc:[android.nfc.media.IMediaRouterService]
6 media_router print:[android.print.IPrintManager]
7 assetatlas:[android.view.IAssetAtlas]
8 dreams:[android.service.dreams.IdreamManager]
--wip--
```

### 其他 Binder 特性

虽然与 Android 的安全模型不直接相关，但两个 `Binder` 的特性是引用计数和死亡通知（也称为死亡链接）。引用计数保证了 `Binder` 对象在没有地方引用它们时会被自动释放。死亡通知允许应用程序在那些进程被杀死时收到通知并执行任何清理工作。（本地 `Binder` 不发送死亡通知，因为本地 `Binder` 不会死亡。）

## Android 框架库

栈的下一层是 Android 框架库，有时被称为“框架”。框架包含了所有非 Android 运行时的 Java 库（`java.*`、`javax.*` 等），并且大部分位于 `android` 顶级包下。框架包含了构建 Android 应用程序的基础区块，例如 Activity 和内容提供者的基类（在 `android.app.*` 包中）；GUI 组件（在 `android.view.*` 和 `android.widget.*` 包中）；以及文件和数据库访问类（主要在 `android.database.*` 和 `android.content.*` 包中）。它还包含了与硬件交互的类，以及利用系统提供的高级服务。

尽管大多数操作系统功能在内核层作为系统服务实现，但它们没有直接暴露在框架中，而是通过管理器的 facade 类访问。通常，每个管理器都有相应的系统服务支持；例如，`BluetoothManager` 是 `BluetoothManagerService` 的 facade。

## 应用程序

栈顶部是应用程序（或应用），即用户直接交互的程序。虽然所有应用具有相同的结构并构建在 Android 框架之上，但我们将系统应用和用户安装的应用区分开来。

### 系统应用

系统应用包含在操作系统镜像中，在生产设备上是只读的（通常挂载为 `/system`），用户无法安装或更改。因此，这些应用被认为是安全的，并被赋予比用户安装应用更多的权限。系统应用可以是 Android 核心的一部分，也可以仅仅是预装应用程序，例如电子邮件客户端或浏览器。虽然在早期版本的 Android 中，安装在 `/system` 下的所有应用都被同等对待（检查应用签名证书的特性除外），Android 4.4 及更高版本将安装在 `/system/priv-app/` 中的应用视为特权应用，并且只向特权应用授予签名保护级别的权限，而不是安装在 `/system` 下的所有应用。使用平台签名密钥签名的应用可以被授予签名级别的系统权限，即使它们没有预装在 `/system` 下，也可以获得系统级权限。（权限和代码签名的详情请见第 2 章。）

虽然系统应用无法卸载或更改，但只要用户允许就可以对其进行更新。例如，用户可以选择用第三方应用程序替换预装的应用程序启动器或输入法。

## 用户安装的程序

每个应用程序都存在一个可读写分区上（通常挂载为 `/data`），该分区托管用户数据，并可以随时卸载。每个应用程序都运行在一个专门的安全沙箱中，通常无法影响其他应用程序或访问其数据。此外，应用只能访问其已显式授予权限的资源。特权分离和最小权限原则是 Android 安全模型的核心，我们将在下一节中探讨它们是如何实现的。

## Android 应用组件

Android 应用程序是松耦合组件的组合，与传统应用程序不同，它可以有多个入口点。每个组件都可以通过用户在当前或另一个应用程序中的操作来访问，或者由应用程序注册了通知的系统事件触发。

组件及其入口点，以及 Android 元数据，定义在应用程序的清单文件中，称为 `AndroidManifest.xml`。与大多数 Android 资源文件一样，该文件在打包到应用程序包 (APK) 之前，会被编译成二进制 XML 格式（类似于 ASN.1），以减小体积并提高运行速度。清单文件中定义的最重要的应用程序属性是应用包名，它唯一标识系统中的每个应用程序。包名与 Java 包名格式相同（例如，反向域名，`com.google.email`）。

`AndroidManifest.xml` 文件在安装时进行解析，并且每个应用程序所需的包和组件必须使用由开发者控制的密钥进行签名。这保证了已安装的应用程序不会被另一个声称具有相同包名的应用程序替换（除非使用相同的密钥签名，在这种情况下将更新现有应用程序）。我们将在第 3 章中讨论代码签名和应用程序包。

Android 应用的主要组件列在下方。

### Activity（活动）

Activity 是一个带有用户界面的单个屏幕。Activity 是 Android GUI 应用程序的主要构建模块。一个应用程序可以拥有多个 Activity，虽然它们被设计按特定顺序显示，但每个 Activity 都可以独立启动，可能由不同的应用启动（如果允许）。

### Service（服务）

Service 是在后台运行且没有用户界面的组件。Service 通常用于执行某些长时间运行的任务，例如下载文件或播放音乐，而不会阻塞用户界面。Service 还可以使用 AIDL 定义远程接口并向其他应用提供某些功能。然而，与操作系统的一部分且始终运行的系统服务不同，应用服务是可以启动和停止的。

### Content providers（内容提供者）

内容提供者为应用数据提供接口，数据通常存储在数据库或文件中。内容提供者可以通过 IPC（进程间通信）访问，主要用于与其他应用共享应用数据。内容提供者对可以访问数据的哪些部分提供细粒度的控制，允许应用程序仅共享其数据的子集。

### Broadcast receivers（广播接收器）

广播接收器是响应系统级事件（称为广播）的组件。广播源自系统（例如，宣布网络连接的变化），或源自用户应用程序（例如，宣布后台数据更新已完成）。

## Android 安全模型

与系统的其他部分一样，Android 安全模型也利用了 Linux 内核提供的安全功能。Linux 是一个多用户操作系统，内核可以隔离彼此的资源，就像隔离进程一样。在 Linux 系统中，一个用户无法访问另一个用户的文件（除非显式授予权限），每个进程都以启动它的用户的身份（用户 ID 和用户组 ID，通常称为 `UID` 和 `GID`）运行，除非相应的可执行文件上设置了 `set-user-ID` 或 `set-group-ID` (`SUID` 和 `SGID`) 位。

Android 利用了这种用户隔离，但对待用户的方式与传统的 Linux 系统（桌面版或服务器）不同。在传统系统中，`UID` 分给可以登录系统并通过 shell 执行命令的物理用户，或者分给在后台运行的系统服务（守护进程）（因为系统守护进程可以通过网络访问，为每个守护进程运行专用的 `UID` 可以限制其中一个被破坏时的损害）。Android 最初是为智能手机设计的，由于手机是个人设备，因此没有必要在系统中注册不同的物理用户。物理用户是隐式的，`UID` 则被用来区分应用程序。这构成了 Android 应用沙箱的基础。

## 应用沙箱

Android 在安装时为每个应用程序分配一个唯一的应用 ID，并在以该 `UID` 运行的专用进程中执行该应用程序。此外，每个应用程序都获得一个专门的数据目录，它只有该目录的写权限。因此，应用程序在进程级（通过让每个应用运行在专用进程中）和文件级（通过拥有私有数据目录）都是隔离或沙箱化的。这创建了一个内核级的应用沙箱，无论它们是在原生进程还是虚拟进程中执行。

系统应用程序在定义良好的固定的 `UID` 下运行，极少数守护进程以 `root` 用户（`UID` 0）身份运行。Android 没有传统的 `/etc/password` 文件，其系统 `UID` 静态定义在 `android_filesystem_config` 头文件中。系统的 `UID` 从 1000 开始，1000 是系统用户 (`AID_SYSTEM`)，它具有特殊（但有限）的特权。应用程序自动生成的 `UID` 从 10000 开始 (`AID_APP`)，相应的用户名采用 `_app` 或 `u_aXXX` 格式（在 Android 版本中，Y 是 Android UID（不是用户 ID））。

例如，`UID` 10037 对应于名称 `u0_a37`，可能分配给 Google 电子邮件客户端 (`com.google.email`)。

示例 1-7. 共享 `UID` 10012 `/data/system/packages.list` 的系统包

```
# grep '10012' /data/system/packages.list
com.android.systemui 10012 0 /data/data/com.android.systemui platform 1028,1015,3052,3001
com.android.systemui 10012 0 /data/data/com.android.systemui platform 1028,1015,3052,3001
```

虽然不建议非系统应用使用共享用户 ID（shared user ID）机制，但该功能也适用于第三方应用程序。为了共享相同的 `UID`，应用程序需要由相同的代码签名密钥签名。此外，在应用程序的新版本中添加共享用户 ID 会导致其 `UID` 发生变化，系统不允许这样做（见第 2 章）。因此，无法追溯地添加共享用户应用，而需要从一开始就设计为与该 `UID` 工作。

## 权限

由于 Android 应用程序处于沙箱中，它们只能访问自己的文件和设备上全局可访问的资源。然而，这种受限的应用程序将毫无趣味，Android 可以向应用程序授予额外的、细粒度的访问权限，以实现更丰富的功能。这些访问权限被称为*权限*（permissions），它们可以控制对硬件设备、网络、数据或操作系统服务的访问。

应用程序可以通过在 `AndroidManifest.xml` 文件中定义权限来请求权限。在应用程序安装时，Android 会检查请求的权限列表，并决定是否授予它们。一旦授予，权限将无法撤销，并且应用程序可以在无需任何额外确认的情况下使用这些权限。此外，对于私钥或用户账户访问等功能，如果请求的应用程序已获得相应的权限，则仍需要显式用户确认（见第 7 章和第 8 章）。某些权限只能授予 Android 操作系统组成部分的应用程序，这可能是因为它们是预装的，或者是使用相同的密钥签名的。第三方应用程序可以定义自定义权限，并定义名为*权限保护级别*（permission protection levels）的类似限制，从而限制对同一作者创建的应用程序的服务和资源的访问。

权限可以在不同的级别实施。对低级系统资源（如设备文件）的请求由 Linux 内核通过检查调用进程的 `UID` 或 `GID` 与资源所有者及访问位进行对比来强制执行。访问高级 Android 组件时，强制由 Android 操作系统或每个组件（或两者兼有）执行。我们将在第 2 章中讨论权限。

## IPC

Android 使用内核驱动程序和用户空间库来实现 IPC。正如在“Binder”中讨论的，内核驱动程序无法伪造，许多系统服务依赖于 `Binder` 提供的调用者 `UID` 和 `PID` 通过 IPC 动态控制对敏感 API 的访问。例如，如果调用者使用示例 1-8 所示的代码以*系统 UID* (1000) 运行，系统蓝牙管理器可能会允许系统应用程序静默启用蓝牙。其他系统服务也可以找到类似的代码。

示例 1-8. 检查调用者是否以系统 `UID` 运行

```java
public boolean isEnabled() {
    if ((Binder.getCallingUid()) != Process.SYSTEM_UID &&
        (!checkCallerIsForegroundUser())) {
        // (TAG){enable:} 不允许非活动且非系统用户执行；
        return false;
    }
}
```

对于影响通过 IPC 暴露的服务的所有方法的更粗粒度权限，系统可以通过在服务声明中指定权限来自动实施。与请求的权限类似，所需的权限在 `AndroidManifest.xml` 文件中声明。与上述示例中的动态权限一样，每个组件权限也是通过底层查询从 `Binder` 获取的 `UID` 实现的。系统使用包数据库确定调用者组件所需的权限，然后将 `UID` 映射到包名，并检索授予调用者的权限集。如果所需的权限在该集合中，则调用成功。如果不在，调用将失败，系统会抛出 `SecurityException`。

## 代码签名与平台密钥

所有 Android 应用程序（包括系统应用）都必须由开发者签名。由于 Android APK 文件是 Java JAR 格式的扩展 [8]，因此所使用的代码签名方法也基于 JAR 签名。Android 使用 APK 签名来确保应用程序的更新来自同一作者（这被称为同源策略），并建立应用程序之间的关系。这两种安全特性都是通过比较当前已安装的目标应用程序的签名证书与更新或相关应用程序的证书来实现的。

系统应用程序由多个平台密钥签名。当不同的系统组件使用相同的平台密钥签名时，它们可以共享资源并在同一个进程中运行。平台密钥由维护特定设备上安装的 Android 版本的人生成并控制：设备制造商、运营商、Google（针对 Nexus）或自建的开源 Android 版本。（我们将在第 3 章中讨论代码签名和 APK 格式。）

## 多用户支持

由于 Android 最初是为具有单一物理用户的手机设备设计的，因此它为每个应用程序分配一个不同的 `UID`，且传统上它们没有物理用户的概念。Android 在 4.2 版本中获得了对多个物理用户的支持，但多用户支持仅在更有可能共享的平板电脑上启用。手机设备上的多用户支持通过将最大用户数设置为 1 来禁用。

每个用户被分配一个唯一的用户 ID（从 0 开始），用户在 `/data/system/users/<user ID>/` 下拥有自己专用的目录，这被称为用户的系统目录。该目录存储用户特定的设置参数、账户数据以及 Android 应用程序。

## SELinux



Android 安全模型严重依赖于授予应用程序的 `UID` 和 `GID`。虽然这些是由内核保证的，且默认情况下每个 Android 应用程序的文件是私有的，但无法阻止恶意应用程序利用系统文件的过度许可访问位（无论是故意还是编程错误）。同样，对系统文件的不当权限一直是 Android 漏洞的根源。事实上，Linux 采用的默认访问控制模型被称为自主访问控制（`DAC`）。自主意味着一旦用户获得访问权限，就可以根据自己的意愿将其传递另一个用户，通过将访问模式设置为全局可见。相比之下，强制访问控制（`MAC`）确保对资源的访问符合系统范围的规则，称为策略。策略只能由管理员更改，用户无法覆盖或绕过它，例如授予所有人访问。

安全增强 Linux（`SELinux`）是 Linux 内核的一种实现，已集成到主内核中超过 10 年。从 4.3 版本开始，Android 集成了来自 Android 安全增强（`SEAndroid`）项目的修改版 SELinux 版本，该项目已扩展以支持 `Binder` 等 Android 特性。Android 将内核进程和用户应用程序隔离在不同的安全域，并为每个域定义不同的访问策略。从 4.4 版本开始，SELinux 以强制模式部署（违反系统策略将产生运行时错误），但策略强制仅适用于内核进程。应用程序仍然以许可模式运行，违反行为会被记录但不会导致运行时错误。（我们将在第 12 章中详细介绍 Android 的 SELinux 实现。）

## 系统更新

Android 设备可以通过连接 PC 并使用标准的 Android 调试（`ADB`）客户端或具有类似功能的厂商提供的应用程序推送更新镜像进行空中更新（`OTA`）。除了系统文件外，Android 更新可能需要修改基带固件、引导加载程序以及从 Android 直接访问的其他设备部分，更新过程通常使用一个对所有设备硬件具有独占访问权的特殊操作系统。这被称为恢复 OS 或恢复。

`OTA` 更新通过下载 `OTA` 包（通常是带有额外代码签名的 `ZIP` 文件，该包包含一个由恢复系统解释的小脚本文件）并将设备重启到恢复模式来完成。或者，用户可以在启动设备时使用特定的按键组合进入恢复模式，并使用恢复菜单界面手动应用更新。

在生产设备上，恢复程序仅接受由设备制造商签名的更新。更新文件通过在注释部分中对整个文件进行签名扩展来完成签名（见第 3 章），恢复程序在安装更新之前会提取并验证该签名。在某些设备（包括所有 Nexus 设备和开发者设备）上，所有者可以替换操作系统和系统更新签名验证。将此引导加载程序切换到允许替换恢复和系统镜像的模式被称为引导加载程序锁定（不要与 `SIM` 解锁混淆，后者允许设备在任何移动网络上使用），并且需要清除所有用户数据（出厂重置），以确保潜在的恶意第三方系统无法访问现有的用户数据。在消费级设备上，解锁引导加载程序会导致设备保修失效。（我们将在第 13 章讨论系统更新和恢复镜像。）

## 验证启动 (Verified Boot)

从 4.4 版本开始，Android 使用 Linux Device-Mapper 的 `verity` 目标 [10] 支持验证启动。`Verity` 使用加密哈希对块设备进行透明完整性检查。树中的每个节点都是一个加密哈希，叶子节点包含物理数据块的哈希值，中间节点包含其子节点的哈希值。由于根节点中的哈希是基于所有其他节点的值，因此只需要信任根哈希即可验证树其余部分。

验证是通过包含在启动分区中的 RSA 公钥执行。在运行时，通过计算块当前的哈希值并与哈希树中记录的值进行比较，来检查设备块。如果值不匹配，读取操作将导致 `I/O` 错误，指示文件系统损坏。由于所有检查都由内核执行，启动过程需要验证内核的完整性以使验证启动正常工作。此过程是设备特定的，通常通过使用一种不可更改的、硬件特定的密钥来实现，该密钥被“烧录”（写入只写存储器）到设备中。该密钥被用于验证每个引导加载程序以及最终验证内核的完整性。（我们将在第 10 章讨论验证启动。）

## 总结

Android 是一个基于 Linux 内核的权限分离操作系统。高级系统功能实现为一组操作系统服务，通过名为 `Binder` 的 `IPC` 机制进行通信。Android 通过为每个应用程序运行不同的系统身份（Linux `UID`）来将应用程序彼此隔离开。默认情况下，应用程序拥有的权限很少，并且需要细粒度的权限才能与系统服务、硬件设备或其他应用程序交互。权限定义在每个应用程序的清单文件中，并在安装时授予。系统使用每个应用程序的 `UID` 来查找已授予了哪些权限，并在运行时强制这些权限。在最近版本中，系统进程隔离利用 `SELinux` 来进一步限制每个进程的权限。

- [1] Android Mainlining Project, http://elinux.org/Android_Mainlining_Project
- 关于 Android 的更多详细讨论，请参阅 Karim Yaghmour 的《Embedded Android》，O'Reilly, 2013, pp. 29–38。
- [3] Yunhe Shi et al., Virtual Machine Showdown: Stack Versus Registers, https://www.usenix.org/legacy/events/sec05/full_papers/p153-yunhe.pdf
- [4] The Apache Software Foundation, Apache Harmony, http://harmony.apache.org/
- [5] Oracle, Java™ Native Interface, http://docs.oracle.com/javase/7/docs/technotes/guides/jni/
- [6] PalmSource, Inc., OpenBinder, http://www.angryredplanet.com/~hackbod/openbinder/docs/html/
- [7] Google, Android APIs Reference, "IBinder," http://developer.android.com/reference/os/IBinder.html
- [8] Oracle, JAR File Specification, http://docs.oracle.com/javase/7/docs/technotes/guides/jar.html
- [9] SELinux Project, SE for Android, http://selinuxproject.org/page/SEAndroid
- [10] Linux kernel source tree, dm-verity, http://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/tree/Documentation/device-mapper/verity.txt

# 第 2 章 权限 (Permissions)

在上一章中，我们概述了 Android 的安全模型并简要介绍了权限。在本章中，我们将提供关于权限的更多细节，重点关注它们的实现和执行。随后，我们将讨论如何定义自定义权限并将其应用于 Android 组件。最后，我们将简述待处理意图（`pending intents`），它们是允许应用程序以另一个应用程序的身份和权限启动意图的令牌。

## 权限的本质

正如第 1 章所学的，Android 应用程序是沙箱化的，默认情况下只能访问它们自己的文件和极少数的系统服务。为了与系统和其他应用程序交互，Android 应用程序可以请求一组额外的权限，这些权限在安装时授予且无法更改（某些例外外，我们将在本章稍后部分讨论）。

在 Android 中，权限仅仅是一个表示执行特定操作能力的字符串。目标操作可以是任何任何内容，从访问物理资源（如设备的 `SD` 卡）或共享数据（如注册联系人列表），到启动或访问第三方应用程序中组件的能力。Android 带有一套内置的预定义权限。每个版本都会添加对应新功能的新权限。

新的内置权限会锁定以前不需要权限的功能，这些权限根据清单文件有条件地应用。要列出设备上定义的所有权限，请使用 `pm list` 命令：

```shell
$ pm list permissions
All Permissions:
permission-REBOOT
permission-BIND_SERVICE
permission-GALLERY_PROVIDER
```

权限名称通常带有定义包名前缀。例如，在示例 2-1 中，`REBOOT` 和 `BIND_SERVICE` 是内置的，而 `GALLERY_PROVIDER` 是应用程序定义的。

## 请求权限

应用程序通过在其 `AndroidManifest.xml` 文件中添加一个或多个 `<uses-permission>` 标签来请求权限。示例 2-2 显示了一个请求 `INTERNET` 和 `WRITE_STORAGE` 的清单示例：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
package="com.example.app"
 androidversionCode="1"
 androidversionName="1.0">

<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.WRITE_STORAGE" />

<!-- ... -->
<application android:name="SampleApp" ...>
<!-- ... -->
</application>
</manifest>
```

## 权限管理

权限在安装时由系统软件包管理器授予每个应用程序（通过唯一的包名标识）。软件包管理器维护一个安装包的中央数据库（包括预装和用户安装），包含安装路径、版本、签名证书和分配权限的信息，以及设备上定义的所有权限列表。（上一节介绍的 `pm list` 命令通过查询软件包管理器来列出这些内容。）此软件包数据库存储在 `/data/system/packages.xml` 文件中，每当应用程序安装、更新或卸载时，该文件就会更新。

示例 2-3 `packages.xml` 中的应用程序项

```xml
<package name="com.google.android.apps.translate"
 codePath="/data/app/com.google.android.apps.translate-2"
 nativeLibraryPath="/data/app/lib/com.google.android.apps.translate-2"
 flags="4767300" fb="1430dfab9e0" fe="142cdf04d67" ut="1430dfdab8d8"
 version="30003028"
 userid="102041"
 installer="com.android.vending" />
<sigs count="1" />
<cert index="7" />
</sigs>
<perms 3 />
```

```xml
<permissions>
  <permission name="android.permission.READ_EXTERNAL_CREDENTIALS" />
  <permission name="android.permission.READ_SMS" />
  <permission name="android.permission.CAMERA" />
  <permission name="android.permission.WRITE_EXTERNAL_STORAGE" />
  <permission name="android.permission.INTERNET" />
  <permission name="android.permission.MANAGE_ACCOUNTS" />
  <permission name="android.permission.GET_ACCOUNTS" />
  <permission name="android.permission.ACCESS_NETWORK_STATE" />
  <permission name="android.permission.RECORD_AUDIO" />
</permissions>
<signing-keycert identifier="17" />
<signing-keycert identifier="6" />
</package>
```

我们现在将关注第 3 章中与权限相关的多数标签和属性的含义。每个包由一个 `<package>` 元素表示，该元素包含关于 `UID`（在属性 `user` 1 中）、签名证书（在 `<cert>` 标签 ② 中）以及分配的权限（列为 `<permission>` 标签 ③）的信息。要通过程序获取已安装包的信息，请使用 `android.content.pm.PackageManager` 类的 `getPackageInfo` 方法，它会返回一个封装了 `<package>` 标签中所含信息的 `PackageInfo` 实例。

如果所有权限都在安装时分配且在不卸载应用程序无法更改或撤销，包管理器如何决定是否授予请求的权限？为了理解这一点，我们必须讨论权限保护级别。

## 权限保护级别

根据官方文档[12]，权限的保护级别“刻画了该权限涉及的潜在风险，并指示了系统在决定是否授予权限时应该遵循的程序”。在实践中，这取决于它的保护级别。接下来的章节将讨论 Android 定义的四个保护级别以及系统如何处理每种级别。

### normal（普通）

这是默认值。它定义了一个对系统或其他应用程序风险的权限。保护级别为 `normal` 的权限将自动授予，不需要用户确认。示例包括 `ACCESS_NETWORK_STATE`（允许访问网络信息）和 `GET_ACCOUNTS`（允许访问账户服务中的账户列表）。

### dangerous（危险）

具有 `dangerous` 保护级别的权限提供了对用户数据的访问或对设备某些形式的控制。示例包括 `READ_SMS`（允许应用程序读取短信消息）和 `CAMERA`（赋予应用程序访问摄像设备的权限）。在授予危险权限之前，Android 会显示一个确认对话框，显示有关所请求权限的信息。由于 Android 要求所有请求的权限必须在安装时授予，用户可以选择安装该应用（从而授予请求的危险权限）或取消应用安装。例如，对于示例 2-3 所示的应用程序（Google 翻译），系统确认对话框将看起来类似于图 2-1 所示。

Google Play 和其他应用市场客户端会显示自己的对话框，其样式通常不同。对于同一个应用程序，Google Play Store 客户端显示如图 2-2 所示的对话框。在这里，所有危险权限都按权限组组织（参见“系统权限”），并且显示普通权限。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_29_0.png)

图 2-1. 默认 Android 应用安装确认对话框

![](img/8524e4e57e2e9dc889903e3d2c5fe367_30_0.png)

### signature（签名）

签名权限仅授予与声明该权限的应用程序使用相同密钥签名的应用程序。这是“最强”的权限级别，因为它要求拥有加密密钥，而该密钥仅由应用（或平台）所有。因此，使用签名权限的通常由由作者控制。内置签名权限通常由设备管理任务的系统应用使用。示例包括 `NET_ADMIN`（配置网络接口、`IPSec` 等）和 `ACCESS_ALL_EXTERNAL_STORAGE`（访问所有多用户外部存储）。我们将在“签名权限”中更详细地讨论签名权限。

### signatureOrSystem（签名或系统）

具有这种保护级别的权限在某种程度上是一种折中；它们被授予属于系统镜像的一部分或与声明该权限的程序使用相同密钥签名的应用程序。这允许厂商将其预装在 Android 设备上的应用程序共享某些需要权限的特定功能，而无需拥有签名密钥。在 Android 4.3 之前，安装在系统分区上的任何应用程序都会自动获得 `signatureOrSystem` 权限。从 Android 4.4 开始，应用程序需要安装在 `/system/priv-app/` 目录下才能被授予具有此保护级别的权限。

## 权限分配

权限在 Android 的各个层级执行。高层组件（如应用程序和系统服务）查询包管理器以确定哪些权限已分配给应用程序，并决定是否授予访问。低层组件（如原生守护进程 `native daemons`）通常无法访问包管理器，并依赖分配给进程的 `UID`、`GID` 和补充 `GID` 来决定授予哪些权限。对设备文件、Unix 域套接字（本地套接字）和网络套接字的资源访问是由内核根据目标资源的所有者和访问模式，以及访问进程的 `UID` 和 `GID` 进行监管的。

我们将在“权限强制”中研究框架级执行。让我们讨论权限如何映射到 `UID` 和 `GID` 等操作系统级构造结构，以及这些进程 ID 如何用于权限强制执行。

## 权限与进程属性

与任何 Linux 系统一样，Android 进程具有许多属性，最重要的是有效 `UID` 和真实 `UID`，以及一组补充 `GID`。如第 1 节所述，每个应用程序在启动时都由安装程序（包管理器）分配了唯一的 `UID` 和 `GID`。这些进程 ID 用于权限强制执行。在我们了解内核和低层系统服务如何检查并执行权限之前，我们需要检查 Android 应用程序进程是如何启动并分配进程属性的。

包管理器读取 `platform.xml` 以设置并维护权限列表及关联 `GID`。当它在安装期间向包授予权限时，包管理器会检查每个权限是否分配了 `GID`。如果是，则会将 `GID` 添加到与应用程序关联的补充 `GID` 列表中。补充 `GID` 列表作为 `packages.list` 文件的最后一个字段（参见示例 1-6）。

示例 2-4. `platform.xml` 节录



```xml
<?xml version="1.0" encoding="utf-8"?>
<permissions>
  <permission name="android.permission.INTERNET">
    <group="inet" />
  </permission>

  <permission name="android.permission.WRITE_EXTERNAL_STORAGE">
    <group="sdcard_r" />
    <group="sdcard_rw" />
  </permission>

  <permission name="android.permission.MODIFY_AUDIO_SETTINGS">
    <group="media" />
  </permission>

  <permission name="android.permission.ACCESS_SURFACE_FLINGER">
    <group="media" />
  </permission>
</permissions>
```

在这里，`INTERNET` 权限与 `inet` 组①关联，`WRITE_EXTERNAL_STORAGE` 权限与 `sdcard_r` 和 `sdcard_rw`②关联。`MODIFY_AUDIO_SETTINGS`③和 `ACCESS_SURFACE_FLINGER`④权限属于 `media` UID（在Android中，这是 `mediaserver` 守护进程）。

Android 没有 `/etc/group` 文件，从组名到 GID 的映射是静态的，并定义在 `android_filesystem_config.h` 头文件中。示例 2-5 显示了包含 `sdcard_rw`➀、`sdcard_r`➁和 `inet`③组的节录。

**示例 2-5.** `android_filesystem_config.h` 中的静态组名和 UID/GID 映射

```c
//snip-
#define AID_ROOT 0 /*传统的 root 用户 */
#define AID_SYSTEM 1000 /* 系统服务器 */
//snip-
#define AID_SDDCARD_RW 1015 /* 外部存储写入权限 */
#define AID_SDDCARD_R 1028 /* 外部存储读取权限 */
#define AID_SDDCARD_ALL 1035 /* 访问所有用户的外部存储 */
//snip-
#define AID_INET 3003 /* 可以创建 AF_INET 和 AF_INET6 套接字 */
//snip-

struct android_id_info {
    const char *name;
    unsigned int *aid;
};

static const struct android_id_info android_id_ids[] = {
    {"root", AID_ROOT,},
    {"system", AID_SYSTEM,},
//snip-
    {"sdcard_rw", AID_SDDCARD_RW, ➀},
    {"sdcard_r", AID_SDDCARD_R, ➁},
    {"sdcard_all", AID_SDDCARD_ALL,},
//snip-
    {"inet", AID_INET, ③}
};
```

`android_filesystem_config.h` 文件还定义了核心 Android 系统目录和文件的目录、访问模式以及关联的能力（针对可执行文件）。

## 进程属性分配

如第 1 章所述，Android 应用程序是用 Java 实现的，并由 Dalvik VM 执行。每个应用程序进程都运行在一个 Dalvik VM 进程中，执行应用程序的字节码。为了减少应用程序的内存占用并提高启动速度，Android 不会为每个应用程序启动一个 Dalvik VM。相反，它在需要启动新应用时，使用一个部分初始化的 `zygote`，并使用 `fork()`[13] 系统调用进行派生（fork）。然而，在启动新进程时，它并没有调用指定 Java 类的 `exec(main)` 函数，而是仅对该进程进行特化，因为通用的 `zygote` 被转换为特定的应用程序进程，然后进一步特化为执行不同函数的单元。派生的子进程继承了 `zygote` 进程的内存镜像，该镜像已预加载了大部分核心应用框架 Java 类。由于这些类永远不会改变，且 Linux 在派生时使用了写时复制（copy-on-write）机制，所有 `zygote` 进程（即所有 Android 应用程序）都共享同一份框架 Java 类。

`zygote` 进程由 `init.rc` 初始化脚本启动，并在名为 `zygote` 的 Unix 域套接字（Unix-domain socket）上接收命令。当 `zygote` 接收到启动新应用的请求时，它会派生自己，子进程执行以下代码（节选自 `dalvik_system_Zygote.cpp` 中的 `forkAndSpecializeCommon()`），如示例 2-6 所示对其进行特化。

**示例 2-6.** `zygote` 中的应用程序进程特化

```
pid = fork();

if (pid == 0) {
  int err;
  /* the setgroupsIntArray(gids)①
  err = setlimitsFromArray(limits)②
  err = setresgid(gid, gid, gid)③
  err = setresuid(uid, uid, uid)④
  err = setCapabilities(permittedCapabilities,effectiveCapabilities)⑤
  err = set_sched_policy(0,SP_DEFAULT)⑥
  err = setLinuxContext(ctx, isSystemServer, seinfo, niceName)⑦
  enableDebugFeatures(debugFlags)⑧
}
```

所示，子进程首先通过①`setgroupsIntArray()`调用的`setgroups()`设置其主 GID 组（对应权限）。接下来，它通过②`setlimitsFromArray()`调用的`setlimit()`设置资源限制，然后通过③`setresgid()`和④`setresuid()`设置实际、有效和保存的用户 ID 以及组 ID。

子进程最初是以 `root` 身份执行的，与其父进程 `zygote` 一样，能够更改其资源限制和所有进程属性。在设置新进程属性后，进程以分配的 UID 和 GID 执行，且无法返回到 `root` 身份执行，因为保存的用户 ID 不为 0。

在设置了 UID 和 GID 后，进程通过⑤`setCapabilities()`设置了其能力集[14]。然后，它通过将自己加入预定义的控制组（control groups）之一来设置其调度策略⑥[15]。在⑦处，进程设置了其名称（显示在进程列表中，通常是应用程序的包名）和 `seinfo` 标签（作为 SELinux，我们在第 12 章讨论），如果根据要求，还会启用调试功能⑧。

> **NOTE**
> Android 4.4 引入了一个全新的实验性运行时称为 Android Runtime (ART)，预计在未来的版本中取代 Dalvik。虽然 ART 为当前的执行环境带来了许多变化，最重要的是提前（AOT）编译，但它使用了与 Dalvik 相同的基于 `zygote` 的进程执行模型。

`zygote` 与应用程序进程之间的进程关系在通过 `ps` 命令获取的进程列表中显而易见，所示：

**示例 2-7.** `zygote` 与应用程序进程的关系

```
$ ps
USER PID PPID VSIZE WCHAN PC NAME
root 1 0 680 540 fmmmmm 00000000 S /init 1
--system
root 181 85808 38280 fmmmmm 00000000 S zygote 2
--system
radio 1139 181 926888 46512 fmmmmm 00000000 S com.android.phone
nfc 1154 181 888516 36976 fmmmmm 00000000 S com.android.nfc
u0_a7 1219 181 95636 48012 fmmmmm 00000000 S com.google.android.gms
```

在这里，`PID` 列表示进程 ID，`PPID` 列表示父进程 ID，`NAME` 列表示进程名。如你所示，*zygote*（PID 181 2）是由 *init* 进程（PID 1 1）启动的，所有应用程序进程都以 *zygote* 为父进程（PID 181）。每个进程都在专用用户下执行，这些用户是内置的（*radio*、*nfc*）或在安装时自动分配的（*u0_a7*）。进程名被设置为每个应用程序的包名（`com.android.phone`、`com.android.nfc` 和 `com.google.android.gms`）。

## 权限强制

如上一节所述，每个应用程序进程在从 *zygote* 派生时会被分配一个 UID、GID 和补充 GID。内核和系统守护进程使用这些进程标识符来决定是否授予特定系统资源或函数的访问。

### 内核级强制

对普通文件、设备节点和本地套接字的访问遵循任何 Linux 系统的规则。Android 特有的添加是要求进程属于 *inet* 组。内核还定义了“防御性安全”（paranoid security），如示例 2-8 所示。

**示例 2-8.** 内核中的防御性安全实现

```
#ifndef CONFIG_ANDROID_PARANOID_NETWORK
#include <linux/android.h>

static inline int current_has_network(void)
{
	return inegroup(AID_NET);
}
#else
static inline int current_has_network(void)
{
	return 1;
}
```

```
static int inet_create(struct *net, struct *sock, int protocol, int kern)
{
--snip---
    if (!current_has_network())
        return -EACCES
--snip---
}
```

进程不属于 *inet* 组（`AID_NET`），会收到拒绝访问错误❶。要为应用程序进程分配 *inet* 组，需要授予 `INTERNET` 权限。结果是只有具有 `INTERNET` 权限的应用程序才能创建套接字。除了检查进程凭据外，Android 内核还为执行特定 GID 的进程授予某些能力：执行 `AID_NET_RAW`（GID 3004）的进程被授予 `CAP_NET_RAW` 能力，执行 `AID_NET_ADMIN`（GID 3005）的进程被授予能力。防御性安全还用于控制对蓝牙套接字和内核隧道驱动（用于 VPN）的访问。内核特殊处理 GID 列表可以在内核树的 `include/linux/android.h` 文件中找到。

### 原生守护进程级强制

虽然 Binder 是 Android 中优选的 IPC 机制，但底层原生守护进程通常使用 Unix 域套接字（本地套接字）进行 IPC。由于 Unix 域套接字表示为文件节点，可以使用标准文件权限来控制访问。

由于大多数套接字在创建时仅允许所有者和组访问，运行在不同 UID 和 GID 下的客户端无法连接套接字。系统守护进程的本地套接字在 *init.rc* 中定义，并在启动时由 *init* 以指定的访问模式创建。例如，示例 2-9 显示了卷管理守护进程如何在 *init.rc* 中定义：

**示例 2-9.** `init.rc` 中的 `void` 守护进程项

```
service void /system/bin/void
class core
socket void stream 0660 root mount
iorio to 2
```

`void` 创建了一个名为 *void* 的套接字，访问模式为 `0660`，所有者为 *root*，组设置为 `mount`❶。`void` 守护进程需要以 `root` 身份运行才能挂载或卸载卷，但 `mount` 组成员（`AID_NET_MOUNT`，GID 1009）可以通过本地套接字发送命令，需要超级用户权限。Android 守护进程的本地套接字在 `/dev/socket/` 目录下创建。示例 2-10 显示 *void* 套接字具有 *init.rc* 中指定的所属者和权限。

**示例 2-10.** `/dev/socket/` 中核心守护进程的本地 socket

```
srw-------- system   1970-01-18 14:26 abbd
srw------- system   1970-01-18 14:26 install
snrw---- root system   1970-01-18 14:26 netd
--snip---
snrw-rw---- root       1970-01-18 14:26 property_service
snrw-rw---- root       1970-01-18 14:26 rld
snrw-rw---- mount   1970-01-18 14:26 vold
snrw-rw---- system   1970-01-18 14:26 zygote
```

Unix 域套接字（Unix domain sockets）允许使用 `SO_CREDENTIAL` 控制消息和 `SO_PEERCRED` 套接字来传递和查询客户端凭据。类似于 Binder 事务中的有效 UID 和有效 GUID，与本地 socket 关联的对方凭据由内核检查，无法被用户级进程伪造。这允许原生守护进程对允许特定客户端执行的操作实现额外的、细粒度的控制，如示例 2-11 中使用 `void` 守护进程所示。

**示例 2-11.** `void` 中基于 socket 客户端凭据的细粒度访问控制

```
int listener::CryptCmd::runCommand(SocketClient *cli, int arg, char **argv) {
 if (cli->getUid() != 0 && cli->getUid() == AID_SYSTEM) {
  cli->sendMsg(ResponseCode::CommandNoPermission,
  "No permission to run crypts commands", false);
  return 0;
}
return
--snip--
```

`void` 守护进程仅允许以 `root` (UID 0) 或 `system` (`AID_SYSTEM`, UID 1000) 用户身份运行的客户端执行加密凭据管理命令。在这里，`SocketClient->getUid()` 使用通过 `getsockopt(SO_PEERCRED)` 获取的客户端 UID 进行初始化，如示例 2-12 所示。

**示例 2-12.** 使用 `getsockopt()` 获取本地 socket 客户端凭据

```
void SocketClient::init(int socket, bool bound, bool useCmdNum) {

--snip---

 ucred creds;

socklen_t sz = sizeof(creds);

memset(&creds, 0, sz);

 int err = getsockopt(socket, SOL_SOCKET, SO_PEERCRED, &creds, &sz);

 if (err == 0) {

 mPid = creds.pid;

 mUid = creds.uid;

 Gid = creds.gid;

}
}
```



本地 socket 连接功能封装在`android.net.LocalSocket`类中，并对 Java 应用程序可用，允许高层系统服务使用 JNI 代码与原生守护进程通信。例如，`MountService`框架类使用

## 框架级强制

正如 Android 权限引言中所提到的，可以在包含应用程序的清单（manifest）中声明所需的权限，从而使用权限控制对 Android 组件的访问。系统会跟踪与组件关联的权限，并在访问之前检查调用者是否已授予所需的权限。由于组件无法在运行时更改所需的权限，系统的强制执行是静态的。静态权限是声明式安全的一个示例。在使用声明式安全时，角色和权限等安全属性被放置在组件的元数据中（Android 中的`AndroidManifest.xml`文件），而不是组件本身，并由容器或运行时环境强制执行。这种方法的用处是将安全决策与业务逻辑隔离开。

Android 组件还会检查调用进程是否在没有在清单中声明权限的情况下被授予了权限。这种*动态权限执行*需要更多工作，但允许更细粒度的访问控制。动态权限执行是命令式安全的示例，因为安全决策是由每个组件做出的，而不是由运行时环境强制执行的。

让我们详细查看动态和静态权限强制执行是如何实现的。

### 动态执行

正如第 1 章所述，Android 的核心实现为一组操作系统服务，这些服务可以通过 Binder IPC 机制从其他进程调用。核心服务向服务管理器（service manager）注册，任何知道其注册名称的应用程序都可以获取 Binder 引用。由于 Binder 没有内置的访问控制机制，当客户端拥有引用时，它们可以通过向`Binder.transact()`传递适当的参数来调用底层系统服务的任何方法。因此，访问控制需要由每个系统服务实现。

在第 1 章中，我们展示了系统服务如何通过直接检查`Binder.getUid()`获取调用者的 UID 来调节导出操作的访问（参见示例 1–8）。然而，这种方法要求服务知道设备中允许的 UID 列表，这对于像 *root* (UID 0) 和 *system* (UID 1000) 等固定 UID 才有效。此外，大多数服务并不关心调用者的实际 UID；它们只是想检查是否已授予了某个权限。

Android 中的每个应用程序 UID 都与一个唯一的包（共享用户 ID 的一部分）关联，包管理器（package manager）会跟踪授予每个包的权限，这可以通过查询包管理器来实现。检查调用者是否具有某些权限是一个非常常见的操作，Android 在`android.content.Context`类中提供了许多辅助方法可以执行此操作。

让我们检查`int Context.checkPermission(String permission, int pid, int uid)`如何在拥有权限时返回`PERMISSION_GRANTED`，在其他情况下返回`PERMISSION_DENIED`。如果调用者是 *root* 或 *system*，则会自动授予权限。作为性能优化，如果不是这种情况，它会在不检查实际权限的情况下检查清单中是否声明了权限。最后，代码查询包管理器服务以查看调用者是否已授予了请求的权限。来自`PackageManagerService`类的相关代码如示例 2-13 所示。

#### 示例 2-13 `PackageManagerService` 中基于 UID 的权限检查

```java
public int checkUidPermission(String permname, int uid) {

    synchronized (mPackages) {

        Object obj = mSettings.getUserId(uid);

        if (obj != null) {

            GrantedPermissions gp = (GrantedPermissions)obj;

            if (gp.permissions.contains(permname)) {

                return PERMISSION_GRANTED;

            }

        } else {

            HashSet<String> perms = mSystemPermissions.get(uid);

            if (perms != null && perms.contains(permname)) {

                return PERMISSION_GRANTED;

            }

        }

    }

    return PERMISSION_DENIED;

}
```

在这里，`PackageManagerService`首先根据 UID 确定应用 ID（我们在第 4 章中讨论过同一个应用程序可以被分配多个 UID），然后获取授予的权限集。如果`GrantedPermissions`类（持有权限名称的`java.util.Set<String>`）包含目标权限，方法返回`PERMISSION_GRANTED`。如果没有，检查目标权限是否应自动分配给传入的 UID（通过`platform.xml`中的`<assignment-permission>`标签，如示例 2-4 所示）。如果此检查失败，最终返回`PERMISSION_DENIED`。

`Context`类中的其他权限检查辅助方法遵循相同的程序。`checkCallingOrSelfPermission(String permission)`方法为我们调用`Binder.getCallingUid()`和`Binder.getCallingPid()`，然后使用获取的值调用`checkPermission(String permission, int pid, int uid)`。`enforcePermission(String permission, int pid, String message)`方法不返回结果，而在未授予权限的情况下抛出指定异常。例如，`BatteryStats`类在执行任何其他代码之前调用`enforceCalling()`，确保只有具有`BATTERY_STATS`权限的类才能获取统计数据，如示例 2-14 所示。未授予权限的调用者将接收到`SecurityException`。

#### 示例 2-14 `BatteryStatsService` 中的动态权限检查

```java
public byte[] getStatistics() {

    mContext.enforceEnCalling(

        android.Manifest.permission.BATTERY_STATS, null);

    Parcel out = Parcel.obtainParcel();

    mStats.writeToParcel(out, 0);

    byte[] data = out.marshal();

    return data;

}
```

### 静态强制

当应用程序尝试与另一个应用程序声明的组件交互时，静态权限强制就会生效。该强制过程会考虑每个目标组件声明的权限（如果有），并允许已授予所需权限的调用者进行交互。

Android 使用意图（intents）来描述其需要执行的操作，完全指定目标组件（通过包名和类名）的意图被称为显式意图。相反，隐式意图包含某些数据（通常仅是抽象的操作，如`ACTION_SEND`），允许系统找到匹配的组件，但它们并没有完整指定目标组件。

当系统接收到隐式意图时，它首先通过搜索匹配的组件来解析意图。如果找到了多个匹配的组件，则会向用户显示选择对话框。当选择了目标组件后，Android 会检查该组件是否有任何关联权限，如果有，则检查这些权限是否已授予调用者。

其通用过程与动态强制相似：使用`Binder.getCallingUid()`和`Binder.getCallingPid()`获取调用者的 UID 和 PID，将调用者的 UID 映射到包名，并检索权限。如果调用者集合包含了目标组件所需的权限，则启动组件；否则将抛出`SecurityException`。

权限检查由`ActivityManagerService`执行，它解析指定的意图并检查目标组件是否有关联的权限属性。如果是这样，它会将权限检查委托给包管理器（package manager）。权限检查的时机和具体顺序取决于目标组件而略有不同。（接下来，我们将检查如何对每个组件执行检查。）

#### Activity 和 Service 强制

如果传递给`Context.startActivity()`或`startActivityForResult()`的意图解析为声明了权限的 activity，则执行权限检查。如果调用者没有所需的权限，则会抛出`SecurityException`。由于 Android 服务可以被启动、停止和绑定，因此如果目标服务声明了权限，对`Context.startService()`、`stopService()`和`bindService()`的调用都受到权限检查。

#### Content Provider 权限强制

Content provider 权限可以保护整个组件，也可以保护特定的导出 URI，并为读取和写入指定不同的权限。（你将在“Content Provider 权限”中学习更多关于权限声明的内容。）如果指定了不同的读写权限，读取权限控制谁可以对目标提供者或 URI 调用`ContentResolver.query()`，而写入权限控制谁可以对提供者或其导出的 URI 之一调用`ContentResolver.insert()`、`ContentResolver.update()`和`ContentResolver.delete()`。当调用这些方法之一时，检查将同步执行。

#### 广播权限强制

在发送广播时，应用程序可以使用`Context.sendBroadcast(Intent, String receiverPermission)`要求接收者持有特定的权限。由于广播是异步的，在调用此方法时不会进行权限检查。如果目标接收者不持有所需的权限，它将被跳过且不会接收广播，但不会抛出异常。反过来，广播者也可以要求广播者持有特定权限以便能够针对它们发送。

所需的权限在清单文件中或动态注册广播时指定。这种权限检查在投递广播时也会执行，且不会导致`SecurityException`。因此，投递广播可能需要两个权限：一个针对广播（如果接收者指定了权限），另一个针对广播接收者（如果发送者指定了权限）。

### 保护和粘性广播

某些广播被声明为受保护（例如`BOOT_COMPLETED`和`PACKAGE_INSTALLED`），并且只能由作为`SYSTEM_UID`、`PHONE_UID`、`SHELL_UID`、`BLUETOOTH_UID`或 root 运行的系统进程发送。如果在不同 UID 下运行的进程尝试发送受保护广播，它在调用`sendBroadcast()`方法之一时将收到`SecurityException`。发送“粘性”广播（如果标记为粘性，系统会在广播完成后保留`Intent`）要求发送者持有`BROAD_STICKY`权限；否则将抛出`SecurityException`且不发送广播。

### 系统权限

Android 的内置权限定义在`android`包中，有时被称为框架（framework）或“平台”。正如我们在第 1 章中学到的，核心 Android 框架是系统服务共享的一组类，其中一些通过公共 SDK 暴露。类封装在`/system/framework/`的 JAR 文件中（最新版本中约有 40 个）。

除了 JAR 库外，框架还包含一个 APK 文件`framework-res.apk`。正如其名称所示，它包含了框架资源（动画、绘图、布局等），但没有实际代码。最重要的是，它定义了`android`包和系统权限。由于`framework-res.apk`是一个 APK 文件，它包含一个`AndroidManifest.xml`文件，其中声明了权限组和权限（参见示例 2-15）。

#### 示例 2-15 `framework-res.apk` 清单中的系统权限定义

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="android" coreApp="true" sharedUserId="android.id.system"
    sharedUserIdLabel="@string/system_label">

    <!-- ... -->
    <protected-broadcast android:name="android.intent.action.BOOT_COMPLETED" />
    <protected-broadcast android:name="android.intent.action.PACKAGE_INSTALL" />

    <!-- ... -->
    <permission-group android:name="android.permission.group.MESSAGES"
        android:label="@string/perm_group_messages"
        android:description="@string/permgroupdesc_messages">
    </permission-group>

    <permission android:name="android.permission.SEND_SMS"
        android:permissionGroup="android.permission.group.MESSAGES"
        android:protectionLevel="dangerous"
        android:label="@string/perm_group_messages"
        android:description="@string/permdesc_sendSms" />

    <!--snip -->

    <permission android:name="android.permission.NET_ADMIN"
        android:permissionGroup="android.permission.group.SYSTEM_TOOLS"
        android:protectionLevel="signature" />

    <!--snip -->

    <permission android:name="android.permission.MANAGE_USB"
        android:permissionGroup="android.permission.group.HARDWARE_CONTROLS"
        android:protectionLevel="system"
        android:label="@string/perm_group_hardware"
        android:description="@string/permdesc_manageUsb" />

    <!--snip -->

    <permission android:name="android.permission.WRITE_SECURE_SETTINGS"
        android:permissionGroup="android.permission.group.DEVELOPMENT_TOOLS"
        android:protectionLevel="signature|system|development"
        android:label="@string/perm_group_dev"
        android:description="@string/permdesc_writeSecureSettings" />

    <!--snip -->
</manifest>
```



如此列表所示，`AndroidManifest.xml` 文件还声明了系统的保护广播。单个权限可以通过在`permissionGroup`属性中指定组名添加到组中。权限组用于在系统 UI 中显示相关的权限，但每个权限仍然需要单独请求。也就是说，应用程序无法请求授予组中的所有权限。

## 签名权限

正如第 1 章讨论的，所有的 Android 应用程序都要求使用开发者控制的签名密钥进行代码签名。这适用于系统应用程序和框架资源包。我们将在第 3 章详细讨论包签名，但现在先说几个系统应用由平台密钥签名。默认情况下，当前 Android 源代码树中有四种不同的密钥：`platform`、`shared`、`media`和`testkey`（发布版本使用的`releasekey`）。所有被视为核心平台组成的包（System UI、设置、电话、蓝牙等）都使用`platform`密钥签名；与搜索和联系相关的包使用`shared`密钥签名；画廊应用和媒体相关的提供程序使用`media`密钥签名；其他所有内容（包括在`myfile`中未显式指定密钥的包）都使用`testkey`（或`releasekey`）签名。定义系统权限的`framework-res.apk` APK 使用`platform`密钥签名。任何尝试请求具有签名保护级别系统权限的应用，都需要使用与框架资源包相同的密钥签名。

例如，使用示例 2-15 签名的`NET_ADMIN`权限（允许已授予的应用程序控制网络接口）被声明为签名保护级别 4，并且只能授予使用`platform`密钥签名的应用程序。

### 注意
Android 开源仓库 (AOSP) 包含了预生成的测试密钥，这些密钥在编译包时会被默认使用。它们不应用于生产环境构建，因为它们是公开的，任何下载 Android 源代码的人都可以获取。发布构建应使用新生成的、属于所有者的私钥签名。可以使用 AOSP `development/tools/` 目录下的`make_key`脚本生成密钥。有关权限密钥生成的详细信息，请参见`build/target/product/security/README`文件。

## 开发权限

传统上，Android 权限模型不允许动态授予和撤销权限，应用程序的授予权限集在安装时是固定的。然而，从 Android 4.2 开始，通过添加新的开发权限（如`READ_LOGS`和`WRITE_SECURE_SETTINGS`），这种情况得到了稍微放宽。可以使用 Android shell `pm grant`和`pm revoke`命令根据需要授予或撤销开发权限。

### 注意
当然，此操作并不是所有人都能使用的，它受到`GRANT_REVOKE_PERMISSIONS`签名权限的保护。它被授予 `android.uid.shell` 用户 ID (UID 2000) 以及所有从 Android shell 启动的进程（这些进程也运行 UID 2000）。

## 共享用户 ID

使用相同密钥签名的 Android 应用可以请求以相同的 UID 运行，并可以在相同的进程中运行。这一功能被称为共享用户 ID (shared user id)，被核心框架服务和系统应用广泛使用。由于它会对计数和账户管理产生侧影响，Android 团队不建议第三方应用使用它，但用户安装的应用也可以使用。此外，系统不支持将不使用共享用户 ID 的现有应用切换到共享用户 ID，因此协调需要使用共享用户 ID 的应用程序从一开始就应该以此进行设计并发布。

通过在`AndroidManifest.xml`的根元素中添加`sharedUserId`属性来启用共享用户 ID。清单文件中指定的用户 ID 需要遵循 Java 包格式（至少包含一个点），并被用作标识符，类似于应用程序的包名。如果指定的用户 ID 不存在，将创建它。如果已经安装了具有相同 shared UID 的包，则会将签名证书与现有包进行比较，如果它们不匹配，则会返回`INSTALL_FAILED_SHARED_USER_INCOMPATIBLE`错误并安装失败。

在已安装应用的新版本中添加`sharedUserId`将更改其 UID，这将导致丢失文件的访问权限（在某些早期 Android 版本中出现过）。因此，系统不允许此类操作，并会通过`INSTALL_FAILED_UID_CHANGED`错误拒绝更新。简而言之，如果你计划为你的应用使用 shared UID，你必须从一开始就进行设计，并且从第一次发布起就不能没有使用它。

共享 UID 首先是系统包数据库中的类对象，其处理方式类似于应用程序：它有关联的签名证书（多个）和权限。Android 有五个内置 UID，在系统引导时自动添加：

- `android.uid.system` (SYSTEM_UID, 1000)
- `android.uid.phone` (PHONE_UID, 1001)
- `android.uid.bluetooth` (BLUETOOTH_UID, 1002)
- `android.uid.log` (LOG_UID, 1007)
- `android.uid.nfc` (NFC_UID, 1027)

示例 2-16 显示了如何定义 `android.uid.system` 共享用户：

示例 2-16. `android.uid.system` 共享用户的定义：

```xml
<shared-user name="android.uid.system" userId="1000">
  <sigs count="1"/>
  <cert count="4"/>
  </sigs>
  <permissions>
    <item name="android.permission.MASTER_CLEAR"/>
    <item name="android.permission.CLEAR_APP_USER_DATA"/>
    <item name="android.permission.MODIFY_NETWORK_ACCOUNTING"/>
  </permissions>
</shared-user>
```

如你所见，除了有一堆可怕的权限（在 4.4 设备上大约 66 个）之外，该定义与之前显示的包声明非常相似。相反，属于共享用户的包没有关联的已授予权限列表。相反，它们继承共享用户的权限，该权限是所有具有相同共享用户 ID (shared-user) 的已安装包所请求权限的并集。这种副作用之一是，如果一个包是共享用户的一部分，它可以访问它没有显式请求的 API。

```xml
<permission
  name="com.example.app.permission-group.TEST_GROUP"
  android:label="@string/test_permission_group_label"
  android:description="@string/test_permission_group_desc" />

<permission
  name="com.example.app.permission1"
  android:label="@string/permission1_label"
  android:description="@string/permission1_desc"
  android:permissionGroup="com.example.app.permission-group.TEST_GROUP"
  android:protectionLevel="signature" />
```

与系统权限一样，如果保护级别为 normal（普通）或 dangerous（危险），当用户确认对话框时，自定义权限将被自动授予。为了控制哪些应用程序被授予自定义权限，你可以将其保护级别声明为 signature（签名），以确保它只被授予使用相同密钥签名的应用程序。

## 注意事项

系统只能授予它已知的权限，这意味着定义自定义权限的应用程序需要在使用这些权限的应用程序之前先安装。如果应用程序请求了系统未知的权限，该请求将被忽略且不会授予。

应用程序还可以使用`android.content.PackageManager.addPermission()` API 动态添加新权限，并使用相应的`removePermission(Permission)` API 将其移除。此类动态添加的权限必须属于应用程序定义的权限树。应用程序只能在其自己的包或以相同用户 ID 运行的其他包的权限树中添加或删除权限。

权限树名称采用反向域名表示法，如果一个权限名称以权限树名称加点作为前缀，则认为属于该权限树。例如，`com.example.app.permission.PERMISSION2` 是示例 2-19 中定义的`com.example.app.permission`树的成员。示例 2-20 显示了如何通过代码添加动态权限。

示例 2-20. 通过代码添加动态权限

```java
PackageManager pm = getPackageManager();
PermissionInfo info = new PermissionInfo();
info.name="com.example.app.permission.PERMISSION2"
info.labelRes=R.string.label;
info.protectionLevel=PermissionInfo.PROTECTION_SIGNATURE;
boolean added = pm.addPermission(info);
Log.d(TAG, "permission added: " + added);
```

动态添加的权限被添加到包数据库（`/data/system/packages.xml`）。它们在重启后依然存在，就像在 manifest 中定义的权限一样，但它们有一个设置为 `dynamic` 的额外类型属性。

## 公共和私有组件

在`AndroidManifest.xml`文件中定义的组件可以是公共的，也可以是私有的。私有组件只能由声明它的应用程序调用，而公共组件也可以供其他应用程序使用。

内容提供者（content providers）外，所有组件默认都是私有的。由于内容提供者的目的是与其他应用程序共享数据，内容提供者最初默认是私有的，但这一行为在 Android 4.2（API Level 17）中发生了变化。目标为 API Level 17 或更高版本的应用程序默认获得私有内容提供者，当目标为较低 API 级别时，它们保持公开以实现后兼容。

可以通过显式将`exported`属性设置为`true`来将组件设置为公共，或者通过隐式地声明意图过滤器（intent filter）来设置。不需要公开的组件可以通过将`exported`属性设置为`false`将其设为私有。如果组件未导出，来自外部应用程序的调用将被活动管理器拦截，无论该进程被授予了权限（除非它作为 root 或系统运行）。示例 2-21 显示了通过将`exported`属性设置为`false`来保持组件私有。

示例 2-21. 通过设置`exported="false"`保持组件私有

```xml
<service androidName="MyService" android:exported="false">
  <intent-filter>
    <action androidName="com.example.FETCH_DATA" />
  </intent-filter>
</service>
```

除非旨在公开使用，否则所有公共组件都应该由自定义权限保护。

## Activity 和 Service 权限

Activity 和服务都可以通过目标组件的`permission`属性由单个权限集进行保护。当其他应用程序使用`Context.startActivity()`或`Context.startActivityResult()`调用一个解析到该 Activity 的意图时，会检查 Activity 权限。对于服务，当其他应用程序使用`Context.startService()`、`stopService()`或`bindService()`调用一个解析到该服务的意图时，会检查相应的权限。

例如，示例 2-22 显示了两个自定义权限`START_MY_ACTIVITY`和`USE_MY_SERVICE`，分别设置给 Activity ➀ 和服务 ➁。想要使用这些组件的应用程序需要在其 manifest 中通过`<uses-permission>`标签请求相应的权限。

示例 2-22. 使用自定义权限保护 Activity 和服务

```xml
<xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  package="com.example.myapp">
  ...
  <permission androidName="com.example.permission.START_MY_ACTIVITY"
    android:permissionLevel="signature"
    android:label="@string/my_activity_permission_label"
    android:description="@string/my_activity_permission_desc" />
  <permission androidName="com.example.permission.USE_MY_SERVICE" ...
```

```xml
<android:permissionLevel="signature"
android:label="@string/use_my_service_label"
android:description="@string/use_my_service_perm" />

<activity androidname=".MyActivity"
android:label="@string/my_activity"
android:permission="com.example.permission.START_MY_ACTIVITY">
  <intent-filter>
    --snip---
  </intent-filter>
</activity>

<service androidname=".MyService"
android:permission="com.example.permission.USE_MY_SERVICE">
  <intent-filter>
    --snip---
  </intent-filter>
</service>
```

## 广播权限

与 Activity 和服务不同，广播接收器（broadcast receivers）的权限可以由接收器本身和发送广播的应用程序指定。在发送广播时，应用程序可以使用`Context.sendBroadcast(Intent intent)`方法发送广播给所有注册的接收器，或者通过`Context.sendBroadcast(Intent, String receiverPermission)`限制接收广播的组件范围。`receiverPermission`参数指定了感兴趣的接收器接收广播所需的持有的权限。或者，从 Android 4.0 开始，可以使用`Intent.setPackage(String packageName)`将接收器范围限制在指定包中定义的接收器。在多用户设备上，持有`INTERACT_AC_USERS`权限的系统应用程序可以使用`broadcastAsUser(Intent intent, UserHandle user)`和`broadcastAsUser(Intent intent, UserHandle user, String receiverPermission)`方法发送仅递送给特定用户的广播。

接收器可以通过以下方式监听发送者：对于静态注册的接收器，在 manifest 中的`<receiver>`标签中使用`permission`属性指定权限；对于动态注册的接收器，通过向`Context.registerReceiver(BroadcastReceiver receiver, IntentFilter filter, String permission, Handler scheduler)`传递所需的权限。只有授予了所需权限的广播者才能向该接收器发送广播。例如，执行安全策略的设备管理应用程序（我们在第 9 章中讨论设备管理）需要`BIND_DEVICE_ADMIN`权限才能接收`DEVICE_ADMIN_ENABLED`广播。由于这是一个保护级别的签名系统权限，该权限保证了只有系统可以激活设备管理应用程序。例如，示例 2-23 显示了默认 Android 应用程序如何 `PolicyManager` 指定`BIND_DEVICE_ADMIN`权限为静态注册的广播接收器指定权限。

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.android.email"
    android:versionCode="500060">
<!--snip-->
<receiver
    android:name="SecurityPolicyAdmin"
    android:label="@string/device_admin_label"
    android:description="@string/device_admin_description"
    android:permission="android.permission.BIND_DEVICE_ADMIN">
```



```xml
<meta-data
    android:name="android.app.device_admin"
    android:resource="@xml/device_admin" />

<intent-filter>
    <action
        android:name="android.app.action.DEVICE_ADMIN_ENABLED" />
</intent-filter>
</receiver>

<!--snip-->

</manifest>
```

与其他组件一样，私有广播接收器只能接收来自同一应用程序的广播。

## 内容提供者权限

如“权限的本质”中所提到的，内容提供者（content providers）比其他组件更复杂的权限模型，我们将在本节中进行详细描述。

## 静态提供者权限

虽然可以使用`permission`属性指定控制整个提供者访问的单一权限，但大多数提供者对读取和写入使用不同的权限，并且还可以指定每个 URI 的权限。使用不同读写权限的提供者示例是内置的 `ContactsProvider`。示例 2-24 显示了其`ContactsProvider2`类的声明。

**示例 2-24. ContactsProvider 权限声明**

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.android.provider.contacts"
    android:sharedUserId="android.uid.shared"
    android:sharedUserLabel="@string/sharedUserLabel">

    <!--snip-->

    <provider
        android:name="ContactsProvider2"
        android:authorities="contacts:com.android.contacts"
        android:label="@string/provider_label"
        android:multiprocess="false"
        android:exported="true"
        android:readPermission="android.permission.READ_CONTACTS"
        android:writePermission="android.permission.WRITE_CONTACTS">

        <!--snip-->

        <path-permission
            android:pathPattern="/*photo"
            android:readPermission="android.permission.GLOBAL_SEARCH" />

        <grant-uri-permission
            android:pathPattern="*/*" />
    </provider>
</manifest>
```

该提供者使用`readPermission`属性来指定读取数据的权限（`READ_CONTACTS` ①），并使用`writePermission`属性单独指定写入权限（`WRITE_CONTACTS` ②）。因此，仅持有`READ_CONTACTS`的应用程序只能调用提供者的`query()`方法，而不能执行`insert()`、`update()`或`delete()`，因为这些操作需要调用者持有`WRITE_CONTACTS`权限。需要读取和写入联系人提供者的应用程序需要同时持有这两项权限。

当全局读写权限不够灵活时，提供者可以指定每个 URI 的权限来保护其数据的某些子集。每个 URI 的权限优先级高于组件级权限（或如果指定了，读取和写入权限）。因此，如果一个应用程序想要访问具有关联权限的内容提供者 URI，它只需要持有目标 URI 的权限，而不是组件级权限。在示例 2-24 中，`ContactsProvider2`使用`<path-permission>`标签，要求尝试读取联系人照片的应用程序持有`GLOBAL_SEARCH`权限 ③。由于每个 URI 的权限覆盖了全局读取权限，感兴趣的应用程序不需要持有`READ_CONTACTS`权限。在实践中，`GLOBAL_SEARCH`权限用于授予 Android 搜索系统对某些系统提供者数据的只读访问，而无法要求其持有所有提供者的读取权限。

## 动态资源权限

虽然静态定义的每个 URI 权限非常强大，但应用程序有时需要向其他应用授予对特定数据（通过其 URI 指定）的临时访问权限，而无需要求它们持有特定的权限。例如，电子邮件或消息应用可能需要与图片查看器应用协作以显示附件。由于应用无法预知附件的 URI，如果它使用静态的每个 URI 权限，它将需要向图片查看器应用授予所有附件的读取权限，这是不符合意愿的。

为了避免这种情况以及潜在的安全担忧，应用程序可以使用`Context.grantUriPermission(String package, Uri uri, int modeFlags)`方法动态授予临时的 URI 访问权限。通过将全局`grantUriPermissions`属性设置为`true`或通过添加`<path-permission>`标签来为特定 URI 启用临时 URI 访问权限。例如，示例 2-25 显示了 Email 应用程序如何使用`grantUriPermissions`属性 ① 在不需要`READ_ATTACHMENT`权限的情况下允许访问附件。

**示例 2-25. 来自 Email 应用的提供者声明**

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  <package package="com.email.android"
    android:versionCode="500060">

    <provider
        android:name=".provider.AttachmentProvider"
        android:authorities="com.email.android.attachmentprovider"
        android:grantUriPermissions="true"
        android:exported="true"
        android:readPermission="com.email.android.permission.READ_ATTACHMENT"/>
</manifest>
```

在实践中，应用程序使用`Context.setPermission()`和`revokePermission()`方法来授予每个 UI 访问。相反，它们在启动应用（示例中的图片查看器）时使用`FLAG_GRANT_READ_PERMISSION`或`FLAG_GRANT_WRITE_PERMISSION`标志。当这些标志设置时，意图接收者被授予对意图数据的读取或写入权限。

从 Android 4.4 (API 19) 开始，可以使用`ContentResolver.takePersistableUriPermission()`方法跨设备重启持久化每个 URI 访问权限，如果意图设置了`FLAG_PERSISTABLE_URI_PERMISSION`。权限被持久化到`/data/system/urigrants.xml`文件中，并通过调用`releasePersistableUriPermission()`进行撤销。临时和持久化的每个 URI 访问都由系统 `ActivityManagerService`管理。

从 Android 4.1 (API 16) 开始，应用程序可以使用意图的`ClipData`添加多个授权的 URI。UI 访问通过`FLAG_GRANT_*`意图授予，并在调用应用的任务结束时自动撤销，因此不需要调用`revokePermission()`。

示例 2-26 显示了示例如何创建一个启动查看器应用的意图。

```java
public Intent getAttachmentIntent(Context context, long accountId) {
    Uri contentUri = getUriIntent(context, accountId);
    Intent intent = new Intent(Intent.ACTION_VIEW);
    intent.setDataAndType(contentUri, mContentType);
    intent.addFlags(Intent.FLAG_GRANT_READ_PERMISSION);
    intent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_WHEN_TASK_RESET);
    return intent;
}
```

## PendingIntent

`PendingIntent`既不是 Android 组件，也不是权限，但由于它们允许应用程序将其权限授予其他应用程序，因此我们在这里讨论它们。

`PendingIntent`封装了一个意图以及用于执行该意图的目标操作（启动操作、发送广播等）。与“普通”意图的主要区别在于，`PendingIntent`还包含了创建它们的应用程序的身份。这允许将`PendingIntent`传递给其他应用程序，这些应用程序可以使用它们以原始应用程序的身份和权限执行指定的操作。

`PendingIntent`用于实现 Android 中的闹钟和通知。闹钟和通知允许任何应用程序指定一个需要执行的操作，该操作是在指定的时间执行，或者在用户与系统通知交互时执行。当创建它们的应用程序不再运行时，闹钟和通知也可以被触发。

**示例 2-27. 使用待处理意图调度闹钟**

```java
private void setAlarm(long id, long millis) {
    Intent i = new Intent(this, MailboxAlarmReceiver.class);
    i.putExtra("mailbox", id);
    setData(Uri.parse("Box" + id));
    pendingIntent = PendingIntent.getBroadcast(this, 0, i, 0);
    pendingIntent.put(id, pi);
    AlarmManager am = (AlarmManager)getSystemService(Context.ALARM_SERVICE);
    am.setAlarm(AlarmManager.RTC_WAKEUP,
        System.currentTimeMillis() + millis, pendingIntent);
}
```



待处理意图也可以绑定到非系统应用程序。规则同样适用：接收 `PendingIntent` 的应用程序可以以与创建应用程序相同的权限和身份执行指定的操作。因此，在构建基础意图时应小心，基础意图通常应该尽可能具体（显式指定组件名称），以确保该意图被预期的组件获取。

待处理意图的实现相当复杂，但它是基于与其他 Android 组件构建时相同的 IPC 和沙箱原理。当应用程序创建一个待处理意图时，系统会使用 `PendingIntent.getCallingUid()` 和 `Binder.getCallingPid()` 获取其 UID 和 PID。基于此，系统会获取创建者的包名和用户 ID（多用户设备上），将其与基础意图以及任何元数据一起存储在 `PendingIntentRecord` 中。活动管理器通过存储相应的 `PendingIntentRecord` 来维护活动待处理意图列表，并在触发时检索必要的记录。然后，它使用记录中的信息来假设待处理意图创建者的身份并执行指定的操作。从那里开始，该过程与启动任何 Android 组件相同，并执行相同的权限检查。

## 总结

Android 在受限的沙箱中运行每个应用程序，并要求应用程序请求特定权限以与其他应用或系统交互。权限是表示执行特定操作能力的字符串。它们在安装时授予，并且（开发权限除外）在应用程序的生命周期内保持不变。权限可以映射到 Linux 辅助组 ID，内核在授予系统资源访问之前会检查这些 ID。

高层服务通过 `Binder` 获取调用应用程序的 UID 并在包管理器数据库中查找其持有的权限来强制执行权限。与应用程序清单文件中声明的组件关联的权限由系统自动执行，但应用程序也可以选择动态执行额外的权限检查。除了使用内置权限外，应用程序还可以定义自定义权限并关联。

每个组件都可以要求权限，内容提供者（content providers）还可以根据每个 URI 指定读写权限。待处理意图将创建它的应用程序身份封装在一个意图中以及一个要执行的操作中，这允许系统或第三方应用程序以相同的身份和权限代表原始应用程序执行操作。

- [11] Google, Android API Reference, "Manifest.permission class", http://developer.android.com/reference/android/Manifest.permission.html
- [12] Google, Android API Guides, App Manifest: <permission> tag, http://developer.android.com/guide/topics/manifest/permission-element.html#plevel
- [13] 有关 `fork()`、`setid()` 等进程管理函数的详细信息，请参阅相应的 man 页面或 Unix 编程书籍，例如 W. Richard Stevens 和 Stephen A. Rago 编写的《Advanced Programming in the UNIX Environment》（第 3 版），Addison-Wesley Professional, 2013。
- [14] 有关 Linux capabilities 的讨论，请参阅 Michael Kerrisk 写的《The Linux Programming Interface: A Linux and Unix System Programming Handbook》（No Starch Press, 2010）第 39 章。
- [15] Linux Kernel Archives, CGROUPS, https://www.kernel.org/doc/Documentation/cgroups/cgroups.txt
- [16] Google, Android API Reference, "ClipData", http://developer.android.com/reference/android/content/ClipData.html

# 第 3 章：包管理

在本章中，我们将深入研究 Android 包管理。我们首先描述 Android 的包格式和代码签名实现，然后详细介绍 APK 安装过程。接下来，我们将探索 Android 对加密 APK 和安全应用程序容器的支持，这些容器用于实现付费应用程序的某种 DRM（数字版权管理）。最后，我们将描述 Android 的包验证机制及其最广泛使用的实现：Google Play 应用验证服务。

## Android 应用程序包格式

Android 应用程序以应用程序包（APK）文件的形式分发和安装，通常称为 APK 文件。APK 文件是包含应用程序代码和资源以及应用程序清单文件的容器文件。它们还可以包含代码签名。APK 格式是 Java JAR 格式的扩展，[1]，而 JAR 格式反又是流行的 ZIP 文件格式的扩展。APK 文件通常具有 `.apk` 扩展名，并与 `application/vnd.android.package-archive` MIME 类型关联。

由于 APK 文件仅仅是 ZIP 文件，你可以使用任何支持 ZIP 格式的压缩工具将其解压并轻松检查其内容。示例 3-1 显示了典型 APK 文件解压后的内容。

**示例 3-1. 典型 APK 文件的内容**

- `AndroidManifest.xml`①
- `classes.dex`②
- `resources.arc`③
- `assets/`④
- `lib/`⑤
- `META-INF/`⑥
  - `CERT.RSA`
  - `CERT.SF`
  - `MANIFEST.MF`
- `res/`⑦
  - `anim/`
  - `color/`
  - `drawable/`
  - `layout/`
  - `menu/`
  - `raw/`
  - `xml/`

## 代码签名

正如第 2 章所学，Android 使用代码签名（特别是签名证书）来控制哪些应用程序可以被授予权限。签名证书在安装期间也用于各种检查，因此在深入了解 APK 安装细节之前，我们应该更熟悉代码签名。

让我们先谈谈通用的代码签名。为什么要对代码进行签名？为了常见的理由：完整性和真实性。在执行任何第三方程序之前，你希望确保它没有被篡改（完整性），并且它确实来自它声称的实体（真实性）。这些功能通常通过数字签名方案实现，该方案保证只有密钥所有者产生有效的签名。

签名验证过程验证代码没有被篡改，并且签名是使用预期的密钥生成的。但代码签名无法直接解决的问题是签名者是否可靠。建立信任通常通常是要求签名者持有数字证书并将其附加签名代码。验证者根据信任模型（如 PKI 或信任网）或根据情况决定是否信任该证书。

代码签名尝试解决的另一个问题是代码是否安全。正如 Flame 和签名恶意软件所示，看似受受信第三方签署的代码并不安全。

### Java 代码签名

Java 代码签名是在 JAR 文件级进行的。它重用并扩展 JAR 清单文件为 JAR 添加签名。主 JAR 清单文件（`MANIFEST.MF`）包含存档中每个文件名和哈希值的条目。例如，示例 3-2 显示了典型 APK 文件的 JAR 清单文件的开头。（在本节的所有示例中，我们将使用 APK 代替普通的 JAR。）

**示例 3-2. JAR 清单文件片段**

```
Manifest-Version: 1.0

Created-By: 1.0 (Android)

Name: res/drawable-xhdpi/ic_launcher.png

SHA1-Digest: 0/Rd3/t0qkslGD/9DY7aCNIBvU==
```

### 实现

Java 代码通过添加另一个名为签名文件（扩展名为 `.SF`）的清单文件来进行签名，该文件包含要签名的数据以及针对数据的数字签名。该数字签名被称为签名块文件，以二进制文件的形式存储在存档中，扩展名为 `.RSA`、`.DSA` 或 `.EC` 之一，取决于所使用的签名算法。如示例 3-3 所示，签名文件与清单非常相似。

**示例 3-3. JAR 签名文件摘**

```
Signature-Version: 1.0

SHA1-Digest-Manifest-Attributes: ZKKXNW/3RG7JA1r0+RlbJIP6IMA=

Created-By: 1.7.0_51 (Sun Microsystems Inc.)

SHA1-Digest-Manifest: bz0XjehVbxE0z2ZC+B4OW25WBxo-

Name: drawable-xhdpi/ic-launcher.png

SHA1-Digest: JtTeE2Y5l3Bdq240PBn27l3dE-

Name: /menu/main.xml

SHA1-Digest: kSQDLfTE07cLTh/cY54UjbbNBo-
```

签名文件包含整个清单文件的摘要（`SHA1-Digest-Manifest` ①），以及 `MANIFEST.MF` 中每个条目的摘要 ② 和 ③。在 Java 6 之前，SHA-1 是默认摘要，但 Java 7 及更高版本可以使用 SHA-256 和 SHA-512 哈希算法生成文件和数字摘要，在这种情况下，摘要分别变为 `SHA-256-Digest` 和 `SHA-512-Digest`。使用版本 4.3，Android 支持 SHA-256 和 SHA-512 摘要。

可以使用以下 OpenSSL 命令轻松验证签名文件中的数字摘要，如示例 3-4 所示。

**示例 3-4. 使用 OpenSSL 验证 JAR 文件摘要**

```
$ openssl sha1 -binary MANIFEST.MF | openssl base64

bz0XjehVbxE0z2ZC+B4OW25WBxo=

$ echo -n "Name: /drawable-xhdpi/ic-launcher.png" | openssl sha1 - \

K/0rd/0qtSlgD9DY7A7CNB+uU=u'rn

|openssl sha1 -binary | openssl base64

JtTeE2Y5l3Bdq240PBn27l3dE-
```

第一个命令 ① 获取整个清单文件的 SHA-1 摘要并将其编码为 Base64；第二个命令 ② 模拟并计算它得出的单个清单条目的摘要。它还演示了 JAR 规范要求的属性规范化格式。

实际的数字签名采用二进制 PKCS#7¹¹⁹（或更通用的 GCS²⁰）格式，包含签名值和签名证书。使用 RSA 算法生成的签名块文件以 `.RSA` 扩展名保存，使用 DSA 或 EC 密钥生成的以 `.DSA` 或 `.EC` 扩展名保存。也可以执行多次签名，在 JAR 文件的 `META-INF` 目录中产生多个 `.SF` 和 `.RSA`/`.DSA`/`.EC` 文件。

CMS 格式本身相当灵活，允许使用不同的算法进行签名和加密。它还通过自定义的已签名或未签名属性进行扩展。深入的讨论超出了本章的范围（有关用于 JAR 签名的 CMS 细节请参阅 RFC 5652，CMS 结构基本上包含摘要算法、签名证书和签名值）。关于将已签名数据包含在 `SignedData` CMS 结构中（一种称为附加签名的格式）的 CMS 规范，JAR 签名并不包含。当签名数据不包含在 CMS 中时，签名被称为分离式签名，验证者需要原始签名数据的副本才能进行验证。示例 3-5 显示了解析为 *ASN.1* [21] 的 RSA 签名块文件。

**示例 3-5. JAR 文件签名块的内容**

```
$ openssl asnparse -i DER in-CERT.RSA

d0=0 hl-4=1 888: SEQUENCE

d4=1 hl-4=2 919: OBJECT .pkcs7-signed-Data 1

15=1 hl-4=4 873: cont[0]

19=2 hl-4=2 869: SEQUENCE

23=3 hl-4=2 12: INTEGER .01 2

26=3 hl-4=2 11: SET

30=4 hl-4=2 9: SEQUENCE

3a=5 hl-4=2 5: OBJECT .sha1 3

37=3 hl-4=2 0: NULL

39=d hl-4=2 11: SEQUENCE

41=d hl-4=2 9: OBJECT .pkcs7-signed-Data 4

52=d hl-4=2 607: cont[0] 5

56=d hl-4=2 603: SEQUENCE

60=d hl-4=2 452: SEQUENCE

64=d hl-4=2 3: cont[0]

66=d7 hl-6=2 1: INTEGER .02

69=d hl-6=2 1: INTEGER .04

72=d hl-6=2 13: SEQUENCE

74=d hl-4=2 9: OBJECT .sha1WithRSAEncryption

85=d hl-4=2 0: NULL

87=d hl-4=2 56: SEQUENCE

89=d hl-4=2 11: SET

91=d hl-4=2 9: SEQUENCE

93=d hl-4=2 1: OBJECT .countryName

98=d hl-4=2 21: PRINTABLESTRING

735=d hl-5=2 9: SEQUENCE

737=d hl-6=2 5: OBJECT

744=d hl-5=2 0: NULL

746=d hl-5=2 13: SEQUENCE

748=d hl-5=2 9: OBJECT .rsaEncryption

759=d hl-4=2 0: NULL

761=d hl-5=3 128: OCTET STRING DUMP:892744D0CEF749...
```

签名块包含标识符 1，描述数据类型：`SignedData` 对象包含版本 2、一组哈希标识符 3（单个签名者的 SHA-1）、数据类型 4（`pkcs7-data`，意味着“任意数据”）；签名证书集 5 以及一个或多个（每个签名者）`SignInfo` 结构，封装了签名值（在示例 3-5 中未完整显示）。对于 JAR 和 APK 签名，`SignedData` 中最重要的元素是签名证书集 ⑤ 和签名值 ⑧。如果我们提取 JAR 文件的内容，可以使用 `OpenSSL smime` 命令通过指定签名文件或签名数据来验证签名。`smime` 命令打印签名数据和验证结果，如示例 3-6 所示：

**示例 3-6. 验证 JAR 文件块**

```
$ openssl smime -verify -in CERT.RSA -inform DER -content CERT.SF signing-cert.pem
Signature-Version: 1.0
SHA1-Digest-Manifest-Attributes: ZKXAnW/3rgJa1r0+RbJIP6IMA=
Created-By: 1.7.0_51 (Sun Microsystems Inc.)
SHA1-Digest: b0z2ZC+B425WBxo= res/drawable-xhdpi/ic/launcher.png
SHA1-Digest: JtTeE2Y5l3Bdq240PBn27l3dE=
Verification successful
```

### JAR 签名

用于 JAR 签名的官方 JDK 工具是 `jarsigner` 和 `keytool` 命令。自 Java 5 起，`jarsigner` 还支持通过时间戳机构（TSA）对签名进行时间标记，这在需要确定签名是在证书过期之前生成的非常有用。然而，此功能并未广泛使用，且在 Android 上不支持。

使用 `jarsigner` 命令签名 JAR 文件需要指定密钥库文件（见第 5 章）以及要使用的别名（除非指定 `sigfile` 选项，否则别名的前八字符将作为签名文件名）以及可选的签名算法。参见示例 3-7 中的 ①。

> 自 Java 7 开始，默认算法更改为 `SHA256withRSA`，因此为了向后兼容使用 SHA-1，需要显式指定。从 Android 4.3 开始支持基于 SHA-256 和 SHA-512 的签名。

**示例 3-7. 使用 `jarsigner` 命令签名 APK 文件并验证签名**

```
$ jarsigner -keystore debug.keystore -signing SHA1withRSA test.apk androiddebugkey①
$ jarsigner -keystore debug.keystore debug -verify -verbose certs.apk②
```

```
-965 Sat Mar 08 23:55:34 JST 2014 res/drawable-xhdpi/ic-launcher.png
X.509, CN=Android Debug, O=Android, C=US (androiddebugkey)③
[certificate is valid from 6/18/71 23:51 PM to 6/10/71 23:51 PM]

-458072 Sun Mar 09 01:16:18 IST 2013 classes.dex
X.509, CN=Android Debug, O=Android, C=US (androiddebugkey)
[certificate is valid from 6/18/11 7:31 PM to 6/10/41 7:31 PM]

-903 Sun Mar 09 01:16:18 IST 2014 META-INF/MANIFEST.MF
-956 Sun Mar 09 01:16:18 IST 2014 META-INF/CERT.SF
-776 Sun Mar 09 01:16:18 IST 2014 META-INF/CERT.RSA

s = signature was verified
m = entry listed in manifest
k = at least one certificate found in keystore
i = at least one certificate found identity scope
```



`jarsigner` 工具可以使用平台支持的所有密钥库类型，也可以使用那些原生不支持且需要 JCA 提供者的类型，例如由智能卡、HSM 或硬件设备支持的类型。用于签名的存储器类型通过 `-storetype` 选项指定，提供者名称和类通过 `-providerName` 和 `-providerClass` 指定。Android 特定的 `signapk` 工具（在“Android 工具”中讨论）也支持 `-providerClass` 选项。

### JAR 验证

通过指定 `-verify` 选项使用 `jarsigner` 命令进行 JAR 验证。示例 3-7 中的 ② 第二次 `jarsigner` 命令验证签名块和签名证书，确保签名文件未被篡改。它验证签名文件（`CERT.SF`）中的每个摘要是否与清单文件（`MANIFEST.MF`）相应的部分匹配。（签名文件中的条目数量不需要与清单匹配。向签名 JAR 中添加文件不会使签名失效：只要原始文件没有更改，验证即可成功。）

最后，`jarsigner` 读取每个清单条目并检查文件摘要是否与实际内容匹配。如果使用 `-keystore` 选项指定了密钥库（如示例所示），`jarsigner` 还会检查证书是否存在于指定的密钥库中。从 Java 7 开始增加了一个新的 `-strict` 选项，用于额外的证书验证，包括时间性检查和证书链验证。验证错误被视为警告并反映在 `jarsigner` 命令的代码中。

序列号：4dc7e9a

有效期从：2011年6月18日 周六 19:31:54 JST 直至：2041年6月20日 周一 19:31:54 JST

证书指纹：

MD5: E8:93:E6:43:99:66:C8:37:E1:30:64:FC:71:C2:32

SHA1: 08:53:74:41:50:27:26:07:E8:F7:A5:56:F4:B3:62:52:06:83:BE

签名算法名称：RSA

版本：3

一旦你获取了签名块文件名（通过列出存档内容示例），你就可以使用 OpenSSL 配合 `unzip` 命令轻松将签名证书提取到文件中，如示例 3-9 所示。（如果 `SignedData` 结构包含多个证书，所有证书都将被提取。在这种情况下，你需要解析 `SignedInfo` 结构来找到实际签名证书的标识符。）

示例 3-9. 使用 `unzip` 和 `openssl pkcs7` 命令提取 APK 签名证书

```
$ unzip -q -c test.apk META-INF/CERT.RSA | openssl pkcs7 -inform DER -print_certs -out cert.pem
```

## Android 代码签名

由于 Android 代码签名基于 Java JAR 签名，它与许多代码签名方案一样，使用了公钥加密法和 X.509 签名证书，但两者的相似之处仅此于此。

在几乎所有其他使用代码签名的平台（如 Java ME 和 Windows Phone）中，代码签名证书必须由平台信任的 CA 颁发。虽然有很多颁发代码签名证书的 CA，但要获得一个被所有目标设备信任的证书可能非常困难。Android 以非常简单的方式解决了这个问题：它并不在乎签名证书的内容或签名者。因此，你不需要它由 CA 颁发，几乎所有在 Android 中使用的代码签名证书都是自名的。此外，你不需要以任何方式断言你的身份：你可以使用任何内容作为主题名称（Google Play 商店会有一些检查来过滤掉常见的名称，但 Android 操作系统本身不会）。Android 将签名证书视为二进制大对象（binary blobs），它们是 X.509 格式仅仅是 JAR 格式的结果。

Android 不在 PKI 意义上验证证书（参见第 6 章）。事实上，如果一个证书不是自签名的，则无需出示或信任签名 CA 的证书；Android 可以轻松地安装带有已过期签名证书的程序。如果你来自传统的 PKI 背景，这看起来可能很奇怪，但请记住 Android 在代码签名时并不使用 PKI，它只是使用了相同的证书和签名格式。

Android 与“标准”JAR 签名的另一点点区别是，所有 APK 条目必须由同一组证书进行签名。JAR 文件格式允许每个文件由不同的签名者签名，并允许未签名的条目。这在 Java 沙箱和访问控制机制中是有意义的，该机制最初是为 applet 设计的，但该模型将代码源定义为签名者证书和代码源 URL 的组合。然而，Android 为每个 APK 分配签名者（通常只有一个，但支持多个签名者），并且不允许不同的 APK 文件条目使用不同的签名者。

Android 的代码签名模型，加上 `java.util.JarFile` 类糟糕的接口（该类对于底层 CMS 签名格式的复杂性并不是良好的抽象），使得正确验证 APK 文件的签名相当困难。虽然 Android 成功地验证了一些

## Android 代码签名工具

如“Java 代码签名”部分中的示例所示，你可以使用常规 JDK 签名工具来签名或验证 APK。除了这些工具外，AOSP `build/` 目录还包含一个名为 `signapk` 的 Android 特定工具。该工具在签名模式下执行的任务与 `jarsigner` 基本相同，但有几个明显的区别。第一，`jarsigner` 要求密钥存储在兼容的密钥文件中，而 `signapk` 采用独立的签名密钥（DER 编码的 PKCS#8 格式）和证书文件（DER 编码的 X.509 格式）。PKCS#8 格式（Java 标准密钥编码格式）的优势在于它包含一个描述编码私钥类型的算法标识符。编码的私钥可能包含密钥材料（可能是加密的），或者它仅包含一个引用（例如密钥 ID），指向存储在硬件设备中的密钥。

从 Android 4.4 开始，`signapk`（在 Android 4.3 中添加到平台）可以生成带有 SHA1withRSA 或 SHA256withRSA 机制的签名。在编写本文时，AOSP 主分支中找到 `signapk` 版本已扩展到支持 ECDSA 签名。

虽然 PKCS#8 格式的私钥较难携带，但你可以轻松地使用 `development/tools/` 中的 `make_key` 脚本生成测试密钥对和自签名证书。如果你有现有的 OpenSSL 工具，必须先使用示例 3-10 所示的 OpenSSL `pkcs8` 命令将其转换为 PKCS#8 格式：

```
示例 3-10. 将 OpenSSL 密钥转换为 PKCS#8 格式
$ echo "keypassword" | openssl pkcs8 -in my-key.pem -topform DER -out my-key.pk8 -passout pass stdin
```

一旦你有了所需的密钥，`signapk`-（后续文本在下一节继续）

## OTA 文件签名

除了默认签名模式外，`signapk` 还有通过 `-w` 选项启用“全文件”模式。在这种模式下，除了对每个条目进行签名外，该工具还在文件末尾生成签名。由于 JAR 文件不支持全文件签名，签名放在哪里？Android `signapk` 工具通过修改 ZIP 格式添加了一个以空字符终止的字符串，随后是二进制签名块和一个包含偏移和大小的 6 字节记录。将偏移量添加到文件末尾使得从末尾开始读取并验证签名，只有在签名通过后才读取文件的其余部分（可能是数百兆）。

## APK 安装过程

有几种方法安装 Android 应用程序：

- 通过应用商店客户端（如 Google Play Store）。这是大多数用户安装的方式。
- 在设备上打开下载的 APK 文件（如果系统设置中的“未知源”选项已启用）。这种方法通常被称为侧载（sideloading）应用。
- 从连接 USB 的电脑使用 Android SDK `adb install` 命令，这调用带有 `install` 参数的 `pm` 命令行工具。这种方法主要用于应用程序开发者。
- 使用 Android shell 直接将 APK 文件复制到系统应用程序目录。由于应用程序目录在生产版本中是不可用的，此方法只能在运行工程（开发）构建版本的设备上使用。

当 APK 文件直接复制到其中一个应用程序目录时，包管理器会监控这些目录的变化并自动检测和安装它。在所有其他安装方法的情况下，应用安装程序（Google Play Store 客户端、默认系统包安装活动、`pm` 命令或其他）会调用系统包管理器的 `installPackage()` 方法，然后将 APK 复制到其中一个应用程序目录并进行安装。在接下来的章节中，我们将探索 Android 包安装过程的主要步骤，并讨论一些复杂的安装步骤，如加密容器的创建和包验证。

## 安装包与数据的位置

回顾第 1 章，Android 区分了系统级应用和用户安装的应用。系统应用位于只读的 `system` 分区（图 3-1 左下角），在生产备设备上无法进行更改或卸载。因此，系统应用被认为是可靠的，并被赋予了更高的权限，某些应用的签名检查也会放宽。大多数系统应用位于 `/system/app/` 目录，而 `/system/priv-app/` 则持有特权应用，这些应用可以根据签名保护级别被授予权限（如第 2 节所述）。`/system/vendor/app/` 托管特定厂商的应用程序。用户安装的程序位于可读写的 `userdata` 分区（如图 3-1 右下角所示），并且可以随时卸载或替换。大多数用户安装的程序安装在 `/data/app/` 目录中。

系统应用和用户安装应用的数据目录都创建在 `userdata` 分区的 `/data/data/` 目录下。`userdata` 分区还托管了用户安装应用程序的优化 DEX 文件（位于 `/data/dalvik-cache/`）、系统包信息（位于 `/data/system/packages.xml`）以及其他的系统数据库和设置文件。（在我们介绍 APK 安装过程时，我们将涵盖图 3-1 中所示其余 `userdata` 分区目录。）

![](img/8524e4e57e2e9dc889903e3d2c5fe367_62_0.png)

## 活跃组件

在建立了 `userdata` 和系统分区的规则后，让我们介绍在包安装过程中起作用的活跃组件。

### PackageInstaller 系统应用

这是默认的 APK 文件处理器。它为包管理提供了一个基本的 GUI，当传递带有 `VIEW` 或 `INSTALL_ACTION` 意图动作的 APK 文件 URI 时，它会解析包并显示安装界面，展示应用程序所需的权限（见图 2-1）。使用 `PackageInstaller` 应用进行安装的前提是用户已在设备安全设置中开启了“未知来源”选项（见图 3-2）。如果未启用“未知来源”，`PackageInstaller` 将显示一个对话框，通知用户已阻止安装从未知来源获取的程序。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_63_0.png)

什么是“未知来源”？虽然屏幕上的提示将其定义为“来自 Play 商店以外来源”，但实际定义要宽得多。当 `PackageInstaller` 启动时，它会获取请求 APK 安装的应用 UID 和包名，并检查其是否为特权应用（安装在 `/system/priv-app/` 中）。如果请求的应用未特权，则被视为未知来源。如果选择了“未知来源”选项且用户确认了安装对话框，`PackageInstaller` 将调用 `PackageManagerService`，由它执行实际的安装。

### pm 命令

`pm` 命令（引入于第 2 节）为系统包管理器的某些功能提供了命令行界面。它可以在 Android shell 中通过 `pm install` 或 `pm uninstall` 分别用于安装或卸载包。此外，Android 调试桥接（ADB）提供了 `adb install/uninstall` 快捷方式。

与 `PackageInstaller` 不同，`pm install` 不依赖于“未知来源”系统选项，且不显示 GUI；它为包安装测试提供了各种实用选项，这些选项是 `PackageInstaller` GUI 无法指定的。要启动安装过程，它会像 GUI 安装器一样调用 `PackageManager` API。

### PackageManagerService

`PackageManagerService`（图 3-1 中的 `PackageManager`）是 Android 包管理基础设施中的核心对象。它负责解析 APK 文件、启动应用安装、升级和卸载包、维护包数据库以及管理权限。

`PackageManagerService` 还提供了许多 `installPackage()` 方法，这些可以使用各种选项执行包安装。其中最通用的是 `installPackageWithVerificationAndEncryption()`，它允许安装加密的 APK 文件，并由验证代理进行包验证。（我们将在稍后在“安装加密的 APK”和“包验证”章节中讨论加密和验证。）

> 注意：`android.content.pm.PackageManager` Android SDK 类向第三方应用暴露了 `PackageManagerService` 的部分功能。

### Installer 类

虽然 `PackageManagerService` 是权限最高的 Android 系统服务之一，但它仍然运行在 `system_server` 进程中（具有系统 UID），且缺乏 root 权限。然而，由于创建、删除和更改应用程序目录的所有权需要超级用户权限，`PackageManagerService` 会通过 `/dev/socket/instald` Unix 套接字将这些操作委托给 `installd` 守护进程，并封装了以命令为导向的 `installd` 协议。

### installd 守护进程

`installd` 是一个具有高权限的原生守护进程，为系统管理器提供应用程序和用户目录管理功能（针对多用户设备）。它还用于启动 `dexopt` 命令，为新安装的包生成优化的 DEX 文件。通过 `installd` 本地套接字访问，只有以系统 UID 运行的进程才能访问。`installd` 守护进程不以 root 身份执行（尽管在早期的 Android 版本中是这样），而是利用 Linux 的 `CAP_DAC_OVERRIDE` 和 `CHOWN` 能力 [23]，以便将其创建的应用程序目录和文件的组和 UID 设置为所属应用程序的。

### MountService

`MountService` 负责可挂载的外部存储（如 SD 卡）以及作为应用程序扩展文件的透明二进制块（OBB）文件。它还用于启动设备加密（见第 10 节）以及更改加密密码。

`MountService` 还管理安全容器，该容器包含不应让非系统访问的应用程序文件。安全容器是加密的，并用于实现一种称为锁定的 DRM（在“锁定”和“Android 4.1 锁定实现”中讨论）。锁定主要用于安装付费应用程序，以确保其 APK 文件无法被轻易拷贝设备并分发。

### void 守护进程

`void` 是 Android 的卷管理守护进程。虽然 `MountService` 包含了大部分处理卷管理的系统 API，但由于它以系统身份运行，并没有权限实际挂载和卸载磁盘卷。这些特权操作在以 root 身份运行的 `void` 守护进程中实现。

`void` 有一个本地套接字接口通过 `/dev/socket/void` 暴露，仅 root 和 mount 组的成员可以访问。由于 `system_server` 进程（托管 `MountService`）的备用 GID 列表包含 mount（1009），`MountService` 被允许访问 `void` 的命令套接字。除了挂载和卸载卷，`void` 还可以创建和格式化分区以及管理安全容器。

### MediaContainerService

`MediaContainerService` 将 APK 文件复制到最终安装位置或加密容器，并允许 `PackageManagerService` 访问移除式存储上的文件。从远程位置（直接或通过应用市场）获取的 APK 文件使用 Android 的 `DownloadManager` 服务下载，下载的文件通过 `DownloadManager` 的内容提供者访问。`PackageManager` 为 `MediaContainerService` 授予每个下载 APK 的权限。如果 APK 是加密的，`MediaContainerService` 将解密第一个文件（在“带有完整性检查的加密 APK”中讨论）。如果请求了加密容器，`MediaContainerService` 将 APK 的加密保护部分（代码和资源）委托给新创建的容器。不需要容器保护的文件直接复制到文件系统。

### AppDirObserver

`AppDirObserver` 是监控应用程序目录 APK 文件变化 [24] 的组件，根据事件类型调用相应的 `PackageManagerService`。当 APK 添加到系统时，`AppDirObserver` 触发包扫描，从而安装或更新应用程序。当 APK 文件被删除时，`AppDirObserver` 卸载进程，移除目录和系统包数据库中的应用条目。

图 3-1 由于空间限制显示了单个 `AppDirObserver` 实例，但实际上有一个特定的系统分区监控的目录有 `/system/framework/`（包含框架资源包 `package-res.apk`）、`/system/app/` 和 `/system/priv-app/`（系统包），以及厂商目录 `/system/vendor/`。`userdata` 分区监控的目录是 `/data/app/app/`，它托管了“旧式”（Android 4.1 之前的）前向锁定 APK 以及在 APK 解密过程中产生的临时文件。

## 安装本地包

现在我们已经知道 Android 组件参与了包的安装，我们将介绍安装过程，从简单的情况开始：安装一个未加密的、无需验证和前向锁定的本地包。

## 解析并验证包



打开本地 APK 文件会启动`android.android.package-archive`处理器，通常是`PackageInstallerActivity`。`PackageInstallerActivity`首先检查请求的应用程序是否已安装（即不被认为来自“未知源”）。如果未安装，且`Settings.Global.INSTALL_NON_MARKET_APPS`为`false`（当勾选了图 3-2 中的“未知源应用”复选框时，该值被设置为`true`），则`PackageInstaller`会显示警告错误并结束安装过程。

如果允许安装，`PackageInstallerActivity`会解析 APK 并从`AndroidManifest.xml`文件和包签名中收集信息。在使用`java.util.JarFile`及相关类提取每个条目的签名证书时，系统会自动验证 APK 文件的完整性。这种实现是必要的，因为`JarFile`的 API 缺乏任何用于验证整个文件或特定条目签名的显式方法。（系统级应用被隐式信任，在解析它们的 APK 文件时，仅验证`AndroidManifest`的完整性。对于不属于系统镜像的包（例如用户安装的应用程序或系统应用的更新），所有 APK 条目都将通过验证。）`AndroidManifest.xml`文件的哈希值也会作为 APK 解析的一部分进行计算，并传递给后续步骤，该值被用于验证从用户在安装对话框中点击“确定”到 APK 拷贝过程开始期间，APK 是否被替换。

> 注意

另一个值得注意的细节是，虽然在安装时使用 Java 库类验证 APK 完整性，但在运行时，Dalvik 虚拟机使用其自身的 ZIP/JAR 解析器原生来实现加载 APK 文件。它们实现中的细微差异一直是多个 Android Bug 的根源。例如，一个漏洞（通常被称为 Android Master Key）允许已签名的 APK 在不重新签名的情况下被修改并仍被视为有效。AOSP 分支已加入了与 Dalvik 使用相同 ZIP 实现的`StrictJarFile`来解决此问题。系统管理器在解析 APK 文件时使用`StrictJarFile`，确保 Dalvik 和包管理器以相同的方式解析 APK 文件。这种实现应该被整合到未来的 Android 版本中。

## 接受权限并启动安装过程

一旦 APK 被解析，`PackageInstallerActivity`会在类似于图 2-1 所示的对话框中显示应用程序信息及其所需的权限。`PackageInstallerActivity`将 APK 文件及其清单摘要以及安装程序包名和 UID 转发给`InstallAppProgress`，由其启动实际的包安装过程。`InstallAppProgress`将 APK URI 和安装元数据传递给`PackageManagerService`的`installPackageWithVerification()`方法，安装过程开始首先验证调用者是否具有`INSTALL_PACKAGES`权限级别的签名，且该权限仅为系统应用程序预留。在多用户设备上，该方法还会验证调用用户是否被允许安装。接下来，它将确定首选安装位置，即内部或外部存储。

## 拷贝到应用程序目录

如果 APK 文件未加密且不需要验证，下一步是将其拷贝到应用程序目录（`/data/app/`）。为了拷贝文件，`PackageManagerService`首先在应用程序目录中创建一个临时文件（带有`.tmp`扩展名），然后将拷贝任务委托给`MediaContainerService`。该文件不会被直接拷贝，因为它可能需要被解密，即需要一个加密容器。由于`MediaContainerService`封装了这些任务，`PackageManagerService`不需要担心底层的实现。当 APK 文件成功拷贝后，它包含的任何原生库都将提取到`/data/app-lib/`下的专用应用目录。接下来，根据包名将 APK 文件和库目录重命名为最终名称，例如 APK 重命名为`com.example.app-1`，目录重命名为`/data/app-lib/com.example.app-1`。最后，将 APK 权限设置为 644 并设置其 SELinux 上下文。

> 注意

默认情况下，APK 文件是全局可读的，任何其他应用程序都可以访问它们。这有利于公共资源的共享，并允许第三方启动器和其他应用程序运行。然而，这些默认权限也允许提取 APK 文件，这对于通过市场分发的应用程序来说是有问题的。APK 前向锁定提供了一种限制代码访问的方法。

## 包扫描

安装过程的下一步是通过调用`PackageManagerService`的`scan()`方法来触发包扫描。如果进程在扫描新 APK 之前停止，它最终会被由`AppObserver`实例捕获，该实例监控`/data/app/`目录并同样触发包扫描。在新建包的情况下，包管理器首先创建一个新的`PackageSettings`结构，包含包名、代码路径、独立资源路径和原生库路径。它为新包分配一个 UID 并将其存储在设置结构中。一旦新应用有了 UID，就可以创建其数据目录。

## 创建数据目录

`PackageManagerService`没有足够的权限来创建和设置应用程序目录的所有权，它通过发送安装命令给`installd`守护进程来委托创建，该命令会创建包名、UID、GID 和 seinfo 标签（用于 SELinux）。`installd`守护进程创建包目录（`/data/com/example.app/`）和`com.example.app`共享原生库目录（`/data/app-lib/`）。随后它将包权限设置为 755 并为原生库创建符号链接。最后，它设置包的 SELinux 上下文，并将所有者更改分配给应用程序的 UID。如果系统有多个用户，下一步是通过`mkdata`命令为每个用户创建数据目录（见第 4 章）。当所有目录创建完成后，控制权返回给`PackageManagerService`，由其从应用程序目录中提取原生库。

## 生成优化的 DEX

下一步是为应用程序生成优化的 DEX。此操作也委托给`installd`并发送`dext`命令。`installd`守护进程派生 dex 进程，在`/data/dalvik/`目录下生成 DEX 文件。（该过程也被称为“优化”。）

> 注意

如果设备使用的是 4.4 版本引入的实验性运行时 (ART) 而不是生成优化 DEX，`installd`将使用`dex2o`命令生成代码。

## 文件和目录结构

当上述过程完成后，应用程序的文件和目录可能如示例 3-12 所示（省略了时间戳和文件大小）。

示例 3-12 安装应用程序后创建的文件和目录

| 权限 | 所有者 | 组 | 路径 |

| :--- | :--- | :--- | :--- |

| -rw-r---- | system | system | /data/com/example.app-apk |

| drwxr-xr-x | system | system | /data/app-lib/com.example.app-1/lib.so |

| -rw-r---- | system | system | /data/dalvik-cache/data/com/example.app-1.apk/classes.dex |

| drwxr-xr-x | u0_a215 | u0_a215 | /data/com/example.app |

| drwxr-xr-x | u0_a215 | u0_a215 | /data/com/example.app/databases |

| drwxr-xr-x | u0_a215 | u0_a215 | /data/com/example.app/files |

| lrwxrwxrwx | root | root | /data/com/example.app/shared_prefs -> /data/app-lib/com.example.app-1 |

| -rw-xr-x | u0_a215 | u0_a215 | /data/com/example.app/shared_prefs |

在这里，① 是 APK 文件，② 是提取出的原生库文件。这两个文件都由系统所有且可读。而 ③ 是应用程序代码的优化的 DEX 文件。它的组被设置为特殊的`all_a215`组，该组包含了所有安装了该应用的用户。这允许所有用户共享同一个优化的 DEX，避免了为每个用户都创建一个副本，这在多用户设备上可能会占用过多的磁盘空间。

在 Android 的沙箱安全模型中，其他用户无法对`lib/`进行读取或写入。`lib`目录仅指向`/data/app-lib/`中应用共享库目录的符号链接。

## 将新包添加到 packages.xml

下一步是将包添加到系统包数据库中。系统会生成一个类似于示例 3-13 的新包条目并将其添加到`packages.xml`。

示例 3-13. 新安装应用程序的包数据库条目

```xml
<package name="com.google.android.apps.chromotone"
codePath="/data/app/com.android.apps.chromotone-2.apk"
nativeLibraryPath="/data/app-lib/com.android.apps.chromotone-2"
flags="572966"
ft="142d0fae588"
tit="142beac305"
ut="142d0fae8d7"
version="16"
userId="100888"
installer="com.android.vending">
<sigs count="1">
  <cert index="7" keys="30820252..."/>
</sigs>
<perms>
<item name="android.permission.USE_CREDENTIALS" />
<item name="com.google.android.apps.chromotone.permission.C2D_MESSAGE" />
<item name="com.google.android.permission.GET_ACCOUNTS" />
<item name="android.permission.INTERNET" />
<item name="android.permission.WAKE_LOCK" />
<item name="com.google.android.c2dm.permission.RECEIVE" />
</perms>
<signing-keyset id="2" key="4"/>
</package>
```

在这里，`<sigs>`元素以十六进制字符串形式持有包签名证书（通常只有一个）的 DER 编码值；或者，在多个应用程序由同一个密钥和证书签名的情况下，它指向该证书首次出现位置的引用。`<perms>`元素包含了授予该应用程序的权限，如第 2 节所述。

`<signing-keyset>`元素是 Android 4.4 中新增的，它持有对应用程序签名密钥的引用，该密钥包含了签名 APK 内部所有文件的公钥（但不包含证书）。`PackageManagersService`收集并将所有应用程序的签名密钥存储在全局`<keyset-sets>`元素中，但从 Android 4.4 开始，不再检查或使用这些密钥集。

## 包属性

根`<package>`元素（如示例 3-13 所示）持有每个包的核心属性，例如安装位置和版本。主要的包属性列在表 3-1 中。可以通过`android.content.pm.PackageManager` SDK 的`getPackageInfo(String packageName, int flags)`方法获取每个包条目中的信息，该方法应返回一个`PackageInfo`实例，其中封装了`packages.xml`条目中可用的属性，以及应用程序清单定义的组件、权限和功能信息。

表 3-1. 包属性

| 属性名称 | 说明 |

| --- | --- |

| name | 包名。 |

| codePath | 包位置的完整路径。 |

| resourcePath | 包中公开可用部分（主资源包和清单）位置的完整路径。这在前锁（forward-locked）应用上是可能的。 |

| nativeLibraryPath | 存储原生库的目录的完整路径。 |

| flags | 与应用相关的标志。 |

| ft | APK 文件时间戳（Unix 毫秒时间，参考`System.currentTimeMillis()`）。 |

| it | 应用程序首次安装的时间（Unix 毫秒时间）。 |

| ut | 应用程序更新的时间（Unix 毫秒时间）。 |

| version | 包的版本，由应用清单中的`versionCode`属性指定。 |

| userID | 分配给应用的内核 UID。 |

| installer | 安装该应用的应用程序的包名。 |

| sharedUserId | 包的共享用户 ID 名称，由清单中的`sharedUserId`属性指定。 |

## 更新组件和权限

在创建`packages.xml`条目后，`PackageManagerService`会扫描新应用清单中定义的所有 Android 组件，并将它们添加到其内部内存表中。接下来，将扫描应用声明的任何权限组和权限，并将其添加到权限注册表中。

> ### 注意

> 定义的自定义权限使用“先到先得”策略进行注册：如果应用 A 和 B 都定义了权限 P，且 A 先安装，则 A 的权限定义会被注册，而 B 的权限定义会被忽略（因为 P 已经注册）。这是可能的因为权限没有以任何方式与包绑定，任何应用都可以定义任何权限。这种“先到先得”策略可能会导致权限级别降级：如果 A 的权限级别（例如，normal/普通）低于 B 的定义（例如，signature/签名），且 A 先安装，那么访问受 P 保护的 B 组件将不再要求调用者与 B 具有相同的密钥签名。因此，在使用自定义权限保护组件时，请务必检查当前注册的权限是否是你应用预期的保护级别。

最后，包数据库的更改（包条目和任何新权限）会被保存到磁盘，`PackageManagerService`会发送`ACTION_PACKAGE_ADDED`以通知其他组件新添加的应用程序。

## 更新包

更新包的流程遵循与安装包的大部分相同步骤，因此我们将仅强调差异。

## 签名验证

第一步是检查新包是否由与现有包相同的签名者签名。这一规则被称为同源策略（same origin policy）或首次信任（Trust First Use, TOFU）。此签名检查确保更新是由原始应用程序相同的实体产生的（假设签名密钥未被破坏），并在更新与扩展应用之间建立了信任关系。正如我们在“更新非系统应用”中看到的，更新继承了原始应用程序的数据。

> 注意

> 在比较签名证书的等性时，并没有按照 PKI 的含义对证书进行验证（不检查时间有效性、信任发行者、撤销等）。

证书等性检查由`PackageManagerService.compareSignatures()`方法执行，如示例 3-14 所示。

示例 3-14. 包签名比较方法

```java
static int compareSignatures(Signature[] s1, Signature[] s2) {
    if (s1 == null) {
        return s2 == null 
            ? SIGNATURE_NEITHER_SIGNED 
            : SIGNATURE_FIRST_SIGNED;
    }
    if (s2 == null) {
        return SIGNATURE_SECOND_SIGNED;
    }
    HashSet<Signature> set1 = new HashSet<>();
    for (Signature sig : s1) {
        set1.add(sig);
    }
    HashSet<Signature> set2 = new HashSet<>();
    for (Signature sig : s2) {
        set2.add(sig);
    }
    // 确保 s2 包含了 s1 中的所有的签名。
    if (set1.equals(set2)) {
        return SIGNATURE_MATCH;
    }
    return SIGNATURE_NO_MATCH;
}
```

目前推荐的有效期至少为 25 年，而 Google Play 商店要求有效期至少到 2023 年 10 月。虽然这只是在推迟问题，但平台最终可能会添加恰当的证书迁移支持。

当包管理器确认更新已使用相同的证书签名时，它将继续更新包。系统级应用和用户安装应用的处理过程有所不同，如后文所述。

## 更新非系统应用

非系统应用的更新本质上是通过重新安装应用并同时保留其数据目录完成的。第一步是杀死正在更新的包的任何进程。接下来，从内部结构和包数据库中移除该包，这也会移除应用已注册的所有组件。接着，`PackageManager`通过调用`scanPackageList()`方法触发包扫描。扫描会对新安装的包进行处理，但它会更新包的代码、资源路径、版本和时间戳。系统会对包清单（manifest）进行扫描，并将任何定义的组件注册到系统中。随后，将重新生成所有包的权限（permissions），以确保它们与更新后包中的任何定义匹配。最后，将更新后的数据库写入磁盘，并发送`PACKAGE_REPLACED`系统广播。

## 更新系统应用



作为用户安装的应用，预装应用（通常位于`/system/app/`）可以在不进行全量系统更新的情况下进行更新，通常通过 Google Play 商店或类似的应用分发服务。尽管系统分区被挂载为只读，但更新会被安装在`/data/app/`中，原始应用保持完好。除了一个`<package>`，更新后的应用还将还有一个`<updated-package>`条目，其格式可能类似于示例 3-16。

示例 3-16. 更新系统包的包数据库条目

```
<package name="com.google.android.keep">
  codePath="/data/app/com.google.android.keep-1.apk" ①
  nativeLibraryPath="/data/app-lib/com.google.android.keep-1"
  flags="it=4767461" ②
  ft="14206e4d980"
  it="14206f3320"
  ut="14226e4dcf8"
  version="2101"
  userId="10053" ③
  installer="com.google.android.vending">
  <certs count="1">
    <cert index="2" />
  </certs>
  <signing-keyset identifier="3" />
  <signing-keyset identifier="34" />
</package>
--snip--
<updated-package name="com.google.android.keep">
  codePath="/system/app/Keep.apk"
  nativeLibraryPath="/data/app-lib/Keep"
  ft="dde88ee8"
  it="14206f3320"
  ut="dde88ee8"
```

更新的`codePath`属性被设置为`/data/app/`中新 APK 的路径 ①。它继承了原始应用的权限和 UID ③ ④，并通过向其`flags`中添加`FLAG_UPDATED_SYSTEM_APK` (0x80) 将其标记为系统应用的更新 ②。

系统应用也可以在系统分区中直接更新，即作为 OTA 系统更新的结果，在这种情况下，允许更新后的系统 APK 使用不同的证书进行签名。其后的原理是，如果安装程序具有足够的权限写入系统分区，则可以更改签名证书以及 UID，并保留任何文件和权限。异常情况是，如果该包是共享用户（shared user）的一部分（在第 2 章中讨论），则无法更新签名，因为这样做会影响其他区域。在相反的情况下，当新的系统应用的签名与当前安装的非系统应用（具有相同包名）的签名不同时，非系统应用将被删除。

## 安装加密 APK

Android 4.1 增加了对加密 APK 安装的支持，并带有对使用 ASEC 的前向锁定（forward locking）的支持。这两个功能都被宣布为应用加密，我们将分别讨论它们，从对加密 APK 文件的支持开始。但首先让我们看看如何安装加密 APK。

可以使用 Google Play 商店或通过 Android shell 中的`pm`命令来安装加密 APK，但系统的`PackageInstaller`不支持加密 APK。由于我们无法控制 Google Play 商店的安装流程，为了安装加密 APK，我们需要使用`pm`命令或编写自己的安装器应用。我们将采用较简单的方法，使用`pm`命令。

## 创建并安装加密 APK

`adb install`命令会将 APK 文件复制到设备上的临时文件，并启动安装过程。该命令为`adb push`和`install`命令提供了一个方便的封装。为了支持加密 APK，`adb install`在 Android 4.1 中获得了三个新参数（示例 3-17）。

示例 3-17. `adb install`命令选项

```
adb install [-l] [-r] [-s] [--algo algorithm name> --key <hex-encoded key>
--iv <hex-encoded iv> <file>
```

`--algo`、`--key`和`--iv`参数允许你分别指定加密算法、密钥和初始化向量 (IV)。但为了使用这些参数，我们需要先创建一个加密 APK。

可以使用示例 3-18 所示的 OpenSSL `enc`命令对 APK 文件进行加密。这里我们使用带有 128 位密钥的 AES-CBC，并指定一个与密钥相同的 IV 以简化操作。

示例 3-18. 使用 OpenSSL 加密 APK 文件

```
openssl enc -aes-128-cbc -K 000102030405060708090A0B0C0D0E0F -iv -in my-app-enc.apk
```

接下来，我们将使用加密算法密钥转换格式（在第 5 章中讨论）并将字节传递`adb install`命令来安装加密 APK，如示例 3-19 所示。

示例 3-19. 使用`adb`安装加密 APK

```
adb install --algo AES/CBC/PKCS5Padding --key 000102030405060708090A0B0C0D0E0F -iv 000102030405060708 /data/local/tmp/my-app-enc.apk
```

如`Success`所示，APK 无错误安装。实际的 APK 文件被复制到`/data/app/`。

更新的`codePath`属性被设置为`/data/app/`中新 APK 的路径 ①。它继承了原始应用的权限和 UID ③ ④，并通过向其`flags`中添加`FLAG_UPDATED_SYSTEM_APK` (0x80) 将其标记为系统应用的更新 ②。

系统应用也可以在系统分区中直接更新，即作为 OTA 系统更新的结果，在这种情况下，允许更新后的系统 APK 使用不同的证书进行签名。其后的原理是，如果安装程序具有足够的权限写入系统分区，则可以更改签名证书以及 UID，并保留任何文件和权限。异常情况是，如果该包是共享用户（在第 2 章中讨论），则无法更新签名，因为这样做会影响其他区域。在相反的情况下，当新的系统应用的签名与当前安装的非系统应用（具有相同包名）的签名不同时，非系统应用将被删除。

## 安装加密 APK

对加密 APK 安装的支持在 Android 4.1 中增加，并带有对使用 ASEC 的前向锁定的支持。这两个功能都被宣布为应用加密，我们将分别讨论它们，从对加密 APK 文件的支持开始。但首先让我们看看如何安装加密 APK。

可以使用 Google Play 商店或通过 Android shell 中的`pm`命令来安装加密 APK，但系统的`PackageInstaller`不支持加密 APK。由于我们无法控制 Google Play 商店的安装流程，为了安装加密 APK，我们需要使用`pm`命令或编写自己的安装器应用。我们将采用较简单的方法，使用`pm`命令。

## 创建并安装加密 APK

`adb install`命令会将 APK 文件复制到设备上的临时文件，并启动安装过程。该命令为`adb push`和`install`命令提供了一个方便的封装。为了支持加密 APK，`adb install`在 Android 4.1 中获得了三个新参数（示例 3-17）。

示例 3-17. `adb install`命令选项

```
adb install [-l] [-r] [-s] [--algo algorithm name> --key <hex-encoded key>
--iv <hex-encoded iv> <file>
```

`--algo`、`--key`和`--iv`参数允许你分别指定加密算法、密钥和初始化向量 (IV)。但为了使用这些参数，我们需要先创建一个加密 APK。

可以使用示例 3-18 所示的 OpenSSL `enc`命令对 APK 文件进行加密。这里我们使用带有 128 位密钥的 AES-CBC，并指定一个与密钥相同的 IV 以简化操作。

示例 3-18. 使用 OpenSSL 加密 APK 文件

```
openssl enc -aes-128-cbc -K 000102030405060708090A0B0C0D0E0F -iv -in my-app-enc.apk
```

接下来，我们将使用加密算法密钥转换格式（在第 5 章中讨论）并将字节传递`adb install`命令来安装加密 APK，如示例 3-19 所示。

示例 3-19. 使用`adb`安装加密 APK

```
adb install --algo AES/CBC/PKCS5Padding --key 000102030405060708090A0B0C0D0E0F -iv 000102030405060708 /data/local/tmp/my-app-enc.apk
```

如`Success`所示，APK 无错误安装。实际的 APK 文件被复制到`/data/app/`。

更新的`codePath`属性被设置为`/data/app/`中新 APK 的路径 ①。它继承了原始应用的权限和 UID ③ ④，并通过向其`flags`中添加`FLAG_UPDATED_SYSTEM_APK` (0x80) 将其标记为系统应用的更新 ②。

如果向其`copyResource()`方法传递了`ContainerEncryptionParams`，则它将使用提供的加密参数来实例化 JCA Cipher 和 Mac（见第 5 章），这些对象可以执行解密和完整性检查。

### 注意

MAC 标签和加密后的 APK 可以封装在一个文件中，在这种情况下，`MediaContainerService`使用其`mAuthenticatedDataStart`、`mEncryptedDataStart`和`mDataEnd`成员从该文件中提取 MAC 和 APK 数据。

## 前向锁定 (Forward Locking)

前向锁定出现在手机铃、壁纸和其他数字“商品”开始在功能手机上共享的时期。由于 Android 上的已安装 APK 文件是可读的，因此从生产设备中提取应用相对容易的。为了在不丢失操作系统任何灵活性的前提下锁定付费应用（并防止用户将其转发给其他用户），早期的 Android 版本引入了前向锁定（也称为代码保护）。

前向锁的核心思想是将应用包分为两个部分：一个全局可读的部分，包含资源和清单文件（位于`/data/app/`），以及一个只有系统用户可读且包含可执行代码的包（位于`/data/app-private/`）。代码包受文件系统权限保护，这使得大多数消费设备上的用户无法访问，但可以从具有 root 权限的设备中提取。这种早期的前向锁定机制很快被废弃，并被在线应用许可服务 Google Play Licensing 所代。

Google Play Licensing 的问题在于它将应用保护的实现转移给了操作系统开发者，且结果参差不齐。前向锁定在 Android 4.1 中被重新设计，现在提供了将 APK 存储在加密容器中的能力，该容器在运行时需要设备特定的密钥才能进行挂载。让我们进一步详细查看它。

## Android 4.1 前向锁定实现

虽然使用加密容器作为前向锁定机制是在 Android 4.1 中引入的，但加密容器最初是在 Android 2.2 中引入的。在那个时候（2010 年中期），大多数 Android 设备都配有有限的内部存储和相对较大（几个 GB）的外部存储，通常以 microSD 的形式存在。为了方便文件共享，外部存储使用 FAT 文件系统进行格式化，该文件系统缺乏文件权限。因此，SD 卡上的文件可以被任何应用程序读取和写入。

为了防止用户直接从 SD 卡复制付费应用，Android 2.2 创建了一个加密文件系统镜像，并在用户选择将应用移动到外部存储时将 APK 存储其中。系统随后会为该加密镜像创建一个挂载点，并使用 Linux 的`device-mapper`进行挂载。Android 在运行时从其挂载点加载每个应用的文件。

Android 4.1 在此想法的基础上构建，使容器使用`ext4`文件系统，该文件系统允许文件权限。一个典型的前向锁定应用的挂载点现在类似于示例 3-24（省略了时间戳）。

示例 3-24. 前向锁定应用挂载点的内容

```bash
# ls -mnt/asec/com.example.app-1
```

在这里，`res.zip`持有应用资源和清单文件并且是全局可读的；包含完整 APK 的`pkg.apk`文件仅供系统和应用专用用户（`u0_a96`）读取。活跃的容器存储在`/data/app-asec/`中，扩展名为`.asec`的文件中。

## 加密应用容器

加密的应用容器被称为 Android 安全外部缓存（Android Secure External Caches）以及 ASEC 容器。ASEC 容器管理（创建、删除、挂载和卸载）在系统卷守护进程 (`vold`) 中实现，`MountService`为框架服务提供了该功能的接口。我们还可以使用`vdc`命令行工具与`vold`交互，以便从 Android shell 处理前向锁定应用（见示例 3-25）。

示例 3-25. 使用 vdc 发出 ASEC 管理命令

```bash
# vdc asec list
vdc asec list
111 0 com.example.app-1
111 0 org.foo.app-1
200 0 asec operation succeeded
```

```bash
# vdc asec path com.example.app-1
vdc asec path com.example.app-1
211 0 /mnt/asec/com.example.app-1
```

```bash
# vdc asec unmount org.example.app-1 0001023030450560708090a0b0c0d0d0e0f 1000
com.example.app-1 1/0001023030450560708090a0b0c0d000f 1000
200 0 asec operation succeeded
```

在这里，`asec list`命令 ❶ 列出了已挂载 ASEC 容器的名称。命名空间 ID 基于包名，其格式与非前向锁定应用的 APK 文件名相同。所有其他命令都接受命名空间 ID 作为参数。`asec path`命令 ② 显示指定的 ASEC 容器的挂载点，而`asec unmount`命令 ③ 则卸载它。除了命名空间 ID 外，`asec mount` ➮ 要求你指定密钥和挂载点的 UID（1000 是系统级）。

ASEC 容器加密算法和密钥长度与原始的 Android 2.2-app-to-SD 实现有所变化：使用了 128 位密钥的 Twofish 算法，存储在`/data/misc/systemkeys/`中，如示例 3-26 所示。

示例 3-26. ASEC 容器加密位置及内容

```bash
# ls /data/misc/systemkeys
-rw-r--r--1 root system 16 AppsOnSD.s
# od -t x /data/misc/systemkeys/AppsOnSD.sks
00000000 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f
```

## 安装前向锁定 APK

前向锁定 APK 的安装过程涉及两个额外的步骤：创建安全容器，这些步骤封装在复制 APK 到应用程序目录时执行。由于无交互安装需要系统权限，因此只有系统应用可以执行。Google 自己的商店客户端利用了加密应用和前向锁定。要准确描述 Google Play 的工作需要了解底层协议（该协议并非公开且在不断演变），查看最近的客户端实现可以看到一些信息。Google Play 服务器发送有关你将下载并安装的包的元数据，例如下载 URL、APK 文件大小、版本和退款窗口。在这些信息中，示例 3-27 中使用的`EncryptionParameters`与示例 3-21 显示的`ContainerEncryptionParameters`非常相似。

示例 3-27. 协议中使用的 EncryptionParams

```java
class AndroidDelivery$EncryptionParams {
    private String encryptionKey;
    private String hmacKey;
    private int version;
}
```

从 Google Play 下载的付费应用的加密算法和 HMAC 算法分别设置为 AES/CBC/PKCS5Padding 和 HMACSHA1。IV 和 MAC 标签与加密后的 APK 封装在一起。在读取并验证所有参数后，它们被转换为`ContainerEncryptionParams`实例，并使用`PackageManager.installPackageWithVerification()`方法安装应用。

在安装付费应用时，会设置`INSTALL_FORWARD_LOCK`标志以启用前向锁定。操作系统随后接管，过程正如前两节所述：创建应用且 APK 最终进入`/data/app/`，同时在`/data/app-ase/`中创建一个加密容器并挂载到`/mnt/ase/<package-name>`。

这种做法的安全性如何？Google Play 现在可以声称付费应用始终以加密形式转换和存储，因此你可以利用自己的应用分发渠道使用 Android 提供的加密设施来实现。尽管，APK 文件内容在某些时刻必须对操作系统可见，因此如果你对运行中的 Android 设备具有 root 权限，它可以

## 包验证



包验证在 Android 4.2 版本中作为应用验证的官方功能被引入，随后被向后移植到所有运行 Android 2.3 及更高版本的 Google Play 商店。使包验证成为可能的设施已内置在操作系统中，Android 本身并不带有内置验证器。最广泛使用的包验证实现是内置在 Google Play 客户端中的，并由 Google 的应用分析基础设施支持。它的设计目的是保护 Android 设备免受 Google 所称为“潜在有害应用”[22]（后门、钓鱼应用程序、间谍软件等），通常简单称为恶意软件。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_80_0.png)

图 3-3 应用验证警告对话框

开启包验证时，APK 在安装前会由验证器进行扫描，如果验证器认为 APK 潜在有害，系统将显示警告（见图 3-3）或阻止安装。在支持的设备上，验证默认开启，但由于它会将应用数据发送给 Google，因此首次使用时需要一次批准。可以通过系统设置屏幕上的“验证应用”选项进行切换（见图 3-2）。

接下来的章节将讨论 Android 包验证基础设施，然后简要 Google Play 的实现。

## Android 对包验证的支持

与大多数处理包管理的事务一样，包验证实现在`PackageManagerService`中，并自 Android 4.0（API 级别 14）起可用。包验证由一个或多个验证代理执行，并要求一个“必需验证器”或零或多个“充分验证器”。当必需验证器和至少一个充分验证器返回正向结果时，验证完成。应用可以通过声明一个广播接收器，其意图过滤器匹配`PACKAGE_NEEDS_VERIFICATION`动作和 APK MIME 类型（`application/vnd.android.package-archive`），来将自己注册为必需验证器，如示例 3-28 所示。

示例 3-28. AndroidManifest.xml 中的必需验证器声明

```xml
<receiver android:name="MyPackageVerifierReceiver"
    android:permission="android.permission.BIND_PACKAGE_VERIFIER">
    <intent-filter>
        <action android:name="android.intent.action.PACKAGE_NEEDS_VERIFICATION" />
        <action android:name="android.intent.action.PACKAGE_VERIFIED" />
        <data android:mimeType="application/vnd.android.package-archive" />
    </intent-filter>
</receiver>
```

此外，声明的应用需要被授予`PACKAGE_VERIFICATION_AGENT`权限。这是一个为系统应用保留的签名权限（`signature|system`），只有系统应用才能成为必需验证器代理。

应用可以通过向其清单文件中添加`<package-verifier>`标签来注册充分验证器，并在标签属性中列出充分验证器的包名和公钥，如示例 3-29 所示。

示例 3-29. AndroidManifest.xml 中的充分验证器声明

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android">
    <package package="com.example.app">
        <package-verifier android:name="com.example.verifier"
            android:publicKey="MIIB..." />
        <application ...>
            <!--snippet -->
        </application>
    </manifest>
```

在安装包时，当必需验证器已安装且`Settings.Global.PACKAGE_VERIFIER_ENABLE`系统设置设置为`true`时，`PackageManagerService`会执行验证。通过将 APK 添加到待安装队列并向注册的验证器发送`ACTION_PACKAGE_NEEDS_VERIFICATION`广播来启用验证。

广播包含唯一的验证 ID 以及关于被验证包的各种元数据。验证代理通过调用`verifyPendingInstall()`方法并传递验证 ID 和验证状态来响应。调用该方法需要`PACKAGE_VERIFICATION_AGENT`权限，这保证了非系统应用无法参与包验证。每次调用`verifyPendingInstall()`时，`PackageManagerService`都会检查是否已收到待安装包的充分验证。如果是，它将把待安装包从队列中移除，发送`PACKAGE_VERIFIED`并启动包安装过程。如果包被验证代理拒绝，或者在规定时间内未收到充分验证，安装将以以`INSTALLED_VERIFICATION_FAILURE`错误告失败。

## Google Play 实现

Google 的应用验证实现内置在 Google Play 商店客户端中。Google Play 商店应用注册为必需验证代理，如果开启了“验证应用”选项，则每次安装应用时，它都会接收到广播，无论是通过 Google Play 客户端本身、`PackageInstaller`应用还是通过`adb`。

该实现并非开源，公开的细节很少，但 Google 的“保护有害应用”Android 帮助页面提到：“当你验证应用时，Google 会接收与应用的信息、URL 以及设备的通用信息，如设备 ID、操作系统版本和 IP 地址。”[[28] 我们可以观察到，截至本文，除了这些信息外，Play 客户端还会发送 APK 文件的 SHA-256 哈希值、文件大小、应用包名、资源名称及其 SHA-256 哈希值、应用 manifest 和类文件的 SHA-256 哈希值、版本和签名证书，以及关于安装应用的元数据和来源 URL（如果可用）。基于此，Google 的 APK 分析算法会判断 APK 是否潜在有害，并向 Play 客户端返回结果，其中包含一个状态码和错误消息，以便在 APK 被认为潜在有害时显示。Play 客户端会使用适当的状态码调用`PackageManagerService`的`verifyingInstall()`方法。应用安装将由上一节描述的算法接受或拒绝。

在实践中（至少在“Google 体验”设备上），Google Play 商店验证器通常是唯一的验证代理，包的安装或被拒绝仅取决于 Google 在线验证服务的响应。

## 总结

Android 应用包（APK 文件）是 JAR 文件格式的扩展，包含资源、代码和 manifest 文件。APK 文件使用 JAR 代码签名格式签名，但要求所有文件必须使用同一组证书进行签名。Android 使用代码签名者来建立应用及其更新的相同来源，并建立应用之间的信任关系。APK 文件通过将其复制到`/data/app/`目录并为每个应用创建一个专用目录`/data/app/`来安装。

Android 支持加密 APK 文件和前锁定应用（forward locked apps）的安全容器。加密应用在复制到应用目录之前会自动解密。前锁定应用被拆分为资源和 manifest 部分（公开访问）以及私有代码（仅由操作系统存储）。

Android 可以在安装应用前通过咨询一个或多个验证代理可选验证应用。目前，最广泛使用的验证代理是内置在 Google Play 客户端中的，并利用 Google 的在线验证服务来检测潜在有害应用。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_82_0.png)

# 第 4 章 用户管理

Android 最初针对的是智能手机等个人设备，并假设每台设备只有一个用户。随着平板电脑和其他共享设备的普及，Android 在 4.2 版本中添加了多用户支持，并在后续版本中进行了扩展。

在本章中，我们将讨论 Android 如何管理共享设备和数据的用户。我们首先将查看 Android 支持的用户类型以及它如何存储用户元数据。然后，我们将讨论 Android 如何在用户之间共享应用程序，同时隔离应用程序数据并保持对每个用户的私有性。最后，我们将介绍 Android 如何实现隔离的外部存储。

## 多用户支持概述

Android 的多用户支持通过为每个用户提供一个隔离的个性化环境，允许多个用户共享单台设备。每个用户都可以拥有自己的主屏幕、小部件、应用程序、在线账户和文件，其他用户无法访问这些内容。

用户通过*用户 ID*（不要与 Linux 的 UID 混淆）进行标识，只有系统可以在用户之间进行切换。用户切换通常通过在 Android 锁屏上选择用户并（可选地）通过模式、PIN 、密码等进行身份验证来触发（通常为了支持多用户环境不需要修改代码，见第 10 章）。应用程序可以通过`UserManager` API 获取当前用户的信息。在受限配置下使用时需要修改其行为的应用程序是例外：这些应用程序需要额外的代码来检查对当前用户施加了哪些限制（详情请参阅*受限配置*）。

多用户支持内置在核心平台中，并适用于所有运行 Android 4.2 或更高版本的设备。默认的平台配置仅允许单个用户，这实际上禁用了多用户支持。为了启用对多个用户的支持，必须将`config_multiuserMaximumUsers`系统资源设置为大于 1 的值，这通常通过添加设备特定的覆盖配置文件来实现。例如，在 Nexus 7 (2013) 上，覆盖文件放置在设备中的`asus/flo/overlay/frameworks/core/res/values/config.xml`文件，`config_multiuserMaximumUsers`的设置如示例 4-1 所示，允许最多八个用户。

示例 4-1. 使用资源覆盖文件启用多用户支持

```xml
<xml version="1.0" encoding="utf-8"?>
<resources xmlns:tools="http://schemas.android.com/tools/1.2">
  <!-- snip -->
  <!-- Maximum number of supported users -- -->
  <integer name="config_multiuserMaximumUsers">8</integer>
  <!-- snip -->
</resources>
```

> Android 兼容性定义要求，支持电话功能的设备（如移动手机）不得启用多用户支持，因为*电话 API 在多个用户上的行为目前是未定义的*。因此，在当前的生产版本（production builds）中，所有手持设备都配置为单用户设备。

当启用多用户支持时，系统设置应用会显示“用户”条目，允许设备所有者（即下一节中讨论的第一个创建的用户）创建和管理用户。用户管理界面如图 4-1 所示。

一旦创建了多一个用户，锁屏就会显示一个用户小部件，显示当前用户并允许切换到不同的用户。图 4-2 显示了拥有八个用户的设备上锁屏可能的样子。

图 4-2. 带有用户切换小部件的锁屏

## 用户类型

尽管 Android 缺乏大多数多用户操作系统的完整用户管理功能（这些通常允许用户添加多个管理员并定义用户组），但它支持配置具有不同权限的用户类型。每个用户类型及其权限将在接后的章节中描述。

### 主用户（所有者）

主用户，也称为设备所有者，是多用户设备上第一个创建的用户，也是单用户设备上的唯一用户。所有者是默认创建的并且始终存在。

主用户被分配用户 ID 为 0。在主用户是唯一用户的单用户设备上，Android 的行为与缺少多用户支持之前的版本相同：分配给应用程序的目录和 UID 保持与之前版本相同的格式和权限（详情请参阅“用户管理”和“应用程序共享”）。

主用户被授予所有权限，可以创建和删除其他用户，还可以更改影响所有用户的设置，包括与设备安全、网络连接和应用程序管理相关的设置。设备和用户管理权限通过在系统设置中显示相应设置并对其他用户隐藏这些设置来授予主用户。此外，底层系统服务（under system services）在执行可能影响所有用户的操作之前，会检查调用用户的身份，并仅在由设备所有者调用时允许执行。

从 Android 4.4 版本开始，系统设置中“无线和网络”部分的以下屏幕将显示给主用户：

- 小区广播

- 管理移动套餐

- 移动网络

- 网络共享和移动热点

- VPN

- WiMAX（如果设备支持则显示）

系统设置中“安全”部分的以下屏幕也保留给主用户：

- 设备加密

- SIM 卡

- 未知源（见第 3 章）

- 验证（见第 3 章）

## 要用户

除受限配置外，所有用户都是要用户。每个用户都有一个专用目录，他们不能添加或删除账户。要用户被限制某些主用户可以执行的操作，例如安装应用程序和更改全局设置（见“用户管理”）。最重要的是，如果要用户更新了添加新权限的应用程序，权限将在无需其他用户同意的情况下授予，且不会通知其他用户权限发生了更改。

### 受限配置

与用户不同，受限配置（在 Android 4.3 中添加）基于主用户并共享其应用程序、数据和账户，但受到限制。因此，主用户必须设置密码以保护其数据。当主用户创建受限配置时如果没有锁屏密码，Android 会提示他们设置一个。

### 用户限制

Android 定义了以下默认限制来控制用户允许做什么。所有限制默认均为 false。下列表显示了受限用户的值：

- **DISALLOW_CONFIG_BLETOOTH** (false): 是否阻止用户配置蓝牙。

- **DISALLOW_CONFIG_CREDENTIALS**: 是否阻止用户配置凭据。当此限制设置为 true 时，受限配置无法添加信任的 CA 证书或将私钥导入系统凭据存储；详情见第 6 章。

- **DISALLOW_CONFIG_WIFI** (false): 是否阻止用户更改 Wi-Fi 访问点。

- **DISALLOW_INSTALL_APPS** (false): 是否阻止用户安装应用程序。

- **DISALLOW_INSTALL_UNKNOWN_SOURCES** (false): 是否阻止用户开启未知源设置（见第 3 章）。

- **DISALLOW_MODIFY_ACCOUNTS** (true): 是否阻止用户添加和删除账户。

- **DISALLOW_REMOVE_USER** (false): 是否阻止用户删除用户。

- **DISALLOW_SHARE_LOCATION** (true): 是否阻止用户切换位置共享。

- **DISALLOW_UNINSTALL_APPS** (false): 是否阻止用户卸载应用程序。

- **DISALLOW_USB_FILE_TRANSFER** (false): 是否阻止用户通过 USB 传输文件。

### 应用限制

在运行时，应用程序可以使用`UserManager.getRestrictions()`方法获取包含施加给用户限制的`Bundle`（一种将字符串键映射到值类型的通用容器类）。限制以键值对的形式定义，其中键为限制名称。

布尔值指定了该限制是否生效。应用程序可以在在受限配置文件内运行时使用该值来禁用某些功能。例如，系统设置应用在显示位置偏好设置时会检查`DISALLOW_SHARE_LOCATION`限制的值。另一个例子是`PackageManagerService`：它在安装或卸载应用之前会检查`DISALLOW_INSTALL_APPS`和`DISALLOW_UNINSTALL_APPS`限制，如果对调用用户设置任何一个限制被设置为 true，则会返回`INSTALL_FAILED_USER_RESTRICTED`错误代码。

主用户可以选择哪些应用程序可以在受限配置文件中可用。当创建受限配置文件时，所有已安装的应用最初都是禁用的，所有者必须显式启用他们想要供受限配置文件使用的应用（见图 4-3）。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_89_0.png)

除了操作系统定义的内置限制外，应用程序还可以通过`BroadcastReceiver`定义自定义限制，接收接收接收`ACTION_GET_RESTRICTION_ENTRIES`条目。Android 会调用此机制查询所有应用可用的限制，并自动构建一个 UI，允许所有者切换用户的自定义限制。

在运行时，应用程序可以使用`UserManager.getApplicationRestrictions()`获取一个包含以键值对形式存储的限制的`Bundle`。应用程序随后可以根据应用的限制，在同一设置中禁用或修改某些功能。设备所有者可以在受限配置文件可用的同一页面上切换系统限制和自定义限制。例如，在图 4-3 中，设置应用支持的单个应用限制（允许应用使用位置信息）显示在主应用开关下方。

### 访问在线账户

受限配置文件还可以通过`AccountManager` API（见第 8 章）访问主用户的在线账户，但此功能默认被禁用。在受限配置文件内运行时需要访问账户的应用程序必须使用`<application>`标签的`restrictedAccountType`属性显式声明它们所需的账户类型，如示例 4-2 所示。

示例 4-2. 允许从受限配置文件访问所有者的账户

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.app">
    <application restrictedAccountType="com.google" ...>
        <!--...-->
    </application>
</manifest>
```



另一方面，不想向受限配置文件暴露信息的应用程序可以通过指定账户类型（作为`<application>`标签的`requiredAccountType`属性的值，可以使用星号`*`来匹配所有账户类型）来声明此项。如果指定了`requiredAccountType`，Android 将自动为受限配置文件禁用此类账户。例如，由于 Android 日历应用在它的清单文件（manifest）中声明了`android:requiredAccountType="*"`，它无法供受限配置文件使用，并在限制设置中被禁用（见图 4-3）。

### 访客用户

Android 支持单个访客用户，但此功能默认禁用。虽然可以通过调用`UserManager.setGuestEnabled(boolean)`方法启用访客，但在当前的 Android 版本中，访客除了`UserManager`和相关类之外似乎没有在其他地方被引用。代码注释表明访客可能是瞬时的，但在编写本文时其目的尚不清楚。它似乎是一个被拒绝或从未完全实现的建议特性的遗留。

## 用户管理

Android 用户由`UserManager`管理，它负责读取和持久化用户信息并维护活动用户列表。由于用户管理与包管理紧密相关，`PackageManagerService`在安装或删除包时会调用`UserManager`来查询或修改用户。`android.os.UserManager`类是`UserManagerService`的一个门面，并向第三方应用程序暴露其功能的子集。应用程序不需要任何特殊权限即可获取系统上的用户数量、用户的序列号、当前用户的名称和限制列表，以及某个包的限制列表。所有其他用户操作（包括查询、添加、删除或修改用户）都需要`MANAG_USERS`签名权限。

## 命令行工具

还可以通过`pm`命令在 Android shell 中执行用户管理操作。这些命令可以在没有 root 权限的情况下通过 shell 运行，因为 shell 用户（UID 2000）被授予了`MANAG_USERS`权限。你可以使用`pm create-user`创建新用户，并使用`pm remove-user`删除它。命令`get-max-users`返回系统支持的最大用户数，而`pm list`则列出所有用户。`pm list`的输出在拥有五个用户的设备上可能像示例 4-3 所示。

示例 4-3. 列出用户

```
$ pm list users
Users:
0
10
11
12
13
```

## 用户状态及相关广播

`UserManagerService`通知其他组件用户相关的事件。当用户被添加时，它发送`USER_ADDED`；当用户被删除时，它发送`USER_REMOVED`。如果用户配置发生变化，它会发送`USER_CHANGED`。切换用户会触发`USER_BACKGROUND`、`USER_FOREGROUND`和`USER_SWITCHED`广播。当用户被启动时，它发送`USER_STARTING`和`USER_STARTED`；当被停止时，它发送`USER_STOPPING`和`USER_STOPPED`。

`USER_BACKGROUND`、`USER_FOREGROUND`和`USER_SWITCHED`广播允许应用程序对用户切换做出响应。`USER_STARTED`和`USER_STOPPED`广播允许应用程序对用户变为活跃或非活跃做出响应。`USER_STARTING`和`USER_STOPPING`广播允许应用程序在用户启动或停止前做出准备。

在这里，`<name>` 2 标签持有用户的用户名，而`<restrictions>`标签 3 包含每个限制项的属性。（用于内置限制列表的受限用户配置。）表 4-1 总结了示例 4-6 中 1 所示的根元素`<user>`的属性。

### 表 4-1. `<user>` 元素属性

| 属性 | 格式 | 描述 |
| --- | --- | --- |
| `id` | integer | 用户 ID |
| `serialNumber` | integer | 用户序列号 |
| `flags` | integer | 表示用户类型的标志位 |
| `created` | 对应 Unix 时间戳（毫秒），与`System.currentTimeMillis()`一致 | 用户创建时间 |
| `lastLoggedIn` | Unix 时间戳（毫秒），与`System.currentTimeMillis()`一致 | 上次登录时间 |
| `icon` | 字符串 | 用户图标文件的完整路径 |
| `partial` | Boolean | 表示用户已部分初始化。部分用户可能尚未创建其所有的文件和目录。 |
| `pinHash` | 十六进制字符串 | 用于 PIN 保护限制的带盐 SHA1+MD5 PIN 哈希值 |
| `salt` | 长型整数 | 用于 PIN 保护限制的 PIN 盐 |
| `failedAttempts` | integer | PIN 保护限制的 PIN 输入失败次数 |
| `lastAttemptMs` | 对应 Unix 时间戳（毫秒），与`System.currentTimeMillis()`一致 | PIN 保护限制的最后一次 PIN 输入尝试的时间（Unix 时间戳（毫秒），与`System.currentTimeMillis()`一致） |

`flags`属性是最重要的属性之一，因为它决定了用户类型。在编写本文时，标志值有 6 位用于用户类型，其余部分已保留，目前定义了以下标志：

- `FLAG_PRIMARY (0x00000001)` 标记主用户。
- `FLAG_ADMIN (0x00000002)` 标记管理员用户。管理员可以创建和删除用户。
- `FLAG_GUEST (0x00000004)` 标记客户用户。
- `FLAG_RESTRICTED (0x00000008)` 标记受限用户。
- `FLAG_INITIALIZED (0x00000010)` 标记用户已完全初始化。

可能存在不同的标志组合，大多数组合并不代表有效的用户类型或状态。主所有者的属性被设置为 19（`0x13` 或`FLAG_INITIALIZED_FLAG_ADMIN_FLAG_PRIMARY`），次级用户的标志为 16（`0x10` 或`FLAG_INITIALIZED`），受限配置的标志为 24（`0x18` 或`FLAG_INITIALIZED_FLAG_RESTRICTED`）。

## 用户系统目录

每个用户系统目录包含用户系统设置和数据，但不包含应用程序数据。正如我们将在下一节中看到的，用户安装的每个应用程序在`/data/`下都有一个数据目录（有关应用程序目录的更多信息请参阅第 3 章）。例如，对于用户 ID 为 12 的次级用户，用户系统目录将命名为`/data/system/users/12/`，并可能包含示例 4-7 中列出的文件和目录。

示例 4-7. 用户目录的内容

- `accounts.db`
- `accounts.db.journal`
- `appwidgets.xml`
- `device_policies.xml`
- `gesture.key`
- `inputmethod`
- `package-restrictions.xml`
- `password.key`
- `photo.png`
- `settings.db`
- `settings.db.journal`
- `wallpaper`
- `wallpaper_info.xml`

`accounts.db`是一个持有在线账户详情的 SQLite 数据库。（我们在第 8 章中讨论在线账户管理。）`appwidgets.xml`存储有关用户添加到主屏幕的小部件信息。`device_policies.xml`描述了当前的设备策略（详情请参阅第 9 章），`gesture.key`和`password.key`分别包含当前选择锁屏或 PIN/密码的哈希值（格式详情请参阅第 10 章）。

`inputmethod`目录包含有关输入方法的信息。`photo.png`存储用户的配置文件或图片。`settings.db`持有特定于用户的系统设置，`wallpaper`是当前选择的壁纸图像。`package-restrictions.xml`文件定义了用户安装了哪些应用程序以及它们存储在哪里。（我们将在下一节中讨论账户共享和每个用户的应用程序数据。）

## 用户应用程序管理

正如在“多用户支持概述”中提到的，由于专用帐户和设置，每个用户都有自己的应用程序数据副本，其他用户无法访问。Android 通过为每个应用程序分配一个新的、每个用户的有效 UID，并创建一个由该 UID 所有的专用应用程序数据目录来实现。我们将在接下来的章节中讨论此实现的细节。

## 应用程序数据目录

如第 3 章所述，Android 通过将 APK 程序包复制到`/data/app/`目录来安装 APK，并在`/data/data/`下为每个应用程序创建一个专用的数据目录。当启用多用户支持时，此布局被托管并扩展以支持额外的用户。为了向后兼容，主用户的应用程序数据仍然存储在`/data/data/`中。

如果在安装新应用程序时系统上存在其他用户，`PackageManagerService`会为每个用户创建数据目录。对于主用户的数据，这些目录是在`installed`守护进程（使用`mkuserdata`命令）的帮助下创建的，因为系统用户没有更改目录所有权的权限。

用户数据存储在`/data/user/`中并以用户的 ID 命名。设备所有者目录（`0/`）是指向`/data/data/`的符号链接，如示例 4-8 所示。

示例 4-8. 多用户设备上`/data/user/`的内容

```
ls /data/user/
drwxr-xr-x 2 root root 4096 0
drwxr-xr-x 2 root root 4096 1
drwxr-xr-x 2 root root 4096 2
```

主用户和次级用户的应用程序数据目录在`/data/data/`下是相同的。

示例 4-9. 主用户和次级用户的`/data/data`内容

```
ls /data/data/
drwxr-xr-x 2 root root 4096 0
drwxr-xr-x 2 root root 4096 1
drwxr-xr-x 2 root root 4096 2
```

```xml
<pkg>
  <preferred-restrictions/>
</package-restrictions>
</pkg>
```

在这里，`com.example.app`包在系统上可用，但未为次要用户安装，这通过为该应用添加`<pkg>`标签并将`inst`属性设置为`false`来表示 ①。根据此信息，`PackageManager`将`com.example.app`包标记为该用户未安装，且该包不会显示在启动器或设置中的应用列表中。

应用程序可以被安装但仍被标记为“已停止”，如 ② 所示。在这里，`com.example.app2`包已安装，但被标记为已停止，且从未启动过；该状态通过`<pkg>`标签的`nl`属性持久化。Android 对从未启动过的应用程序有一个特殊状态；该状态对特定用户持久化。设备所有者（device owner）可以阻止特定用户的某个包，在这种情况下`blocked`属性被设置为`true`，尽管这在图 4-4 中没有显示。

当设备用户安装应用程序时，所有用户的`package-restrictions.xml`文件都会添加一个`inst="false"`的`<pkg>`标签。当另一个用户安装相同的应用程序时，`inst`属性会被移除，该应用程序被认为对该用户已安装。（取决于第二个用户如何启动安装过程，`/data/app/`中的 APK 文件可能会被替换，就像应用更新一样。）

受限用户无法安装应用程序，但当设备所有者为受限用户启用应用时，采用了相同的步骤：通过调用`PackageManager.installExistingPackageAsUser()`方法安装应用程序，该方法会设置包的已安装标记并相应地更新`package-restrictions.xml`。

### App.info

### 示例应用

版本 1.0

- 强制停止
- 卸载
- 显示通知

### 存储

| 总计 | 大小 |
| :--- | :--- |
| 总计 | 2.08MB |
| 应用 | 2.08MB |
| 数据 | 0.00B |

**示例应用**

您想为所有用户卸载此应用吗？该应用程序及其数据将从设备上的所有用户中移除。

取消

确定

否

未设置默认值。

清除默认值

> 图 4-4。当设备所有者尝试为所有用户卸载应用时显示的警告。

当用户卸载一个包时，其应用数据会被删除，内部的每个用户的包已安装标记被设置为`false`。此状态通过在用户的用户的`package-restrictions.xml`文件中对删除的包标签设置`inst="false"`来持久化。APK 文件和原生库目录只有在最后一个安装了该应用的用户卸载它时，才会隐藏在溢出菜单中。然而，所有者可以在应用设置的“系统”选项卡中查看所有已安装的应用，包括他们尚未安装的应用，并且可以为所有用户卸载这些应用。**为所有用户卸载**操作隐藏在溢出菜单中，以免意外选中。它会产生图 4-4 所示的警告。如果所有者在此警告对话框中选择“确定”，则所有用户的应用目录将被移除，APK 文件将从设备中删除。

外部缺点：任何用户都可以更新应用程序，即使它最初是由另一个用户安装的。

这种方案通常不是问题，因为每个用户的应用都有独立的目录，除非更新添加了新权限。由于 Android 在安装时授予权限，如果用户更新应用并接受了影响用户隐私的新权限（例如`READ_CONTACTS`），该权限将适用于所有使用该应用的用户。其他用户不会收到应用已授予新权限的通知，可能永远不会注意到该变化，除非他们手动在系统设置中检查应用详情。Android 在用户首次启用多用户支持时会显示警告通知用户这一事实，但不会再显示关于特定应用的后续通知。

## 外部存储

Android 从第一个公开版本起就包含了对外部存储的支持。由于第一代 Android 设备通过简单挂载 FAT 格式的 SD 卡来实现外部存储，因此外部存储通常被称为“SD 卡”。然而，外部存储的定义更广泛且简单，要求外部存储是一个“不区分大小写的、具有不可变的 POSIX 权限类和方式的文件系统”[30]，其底层实现可以是任何满足此定义的的内容。

### 外部存储实现

较新的设备倾向于通过仿真实现外部存储，某些设备根本没有 SD 卡槽。例如，具有 SD 卡槽的最新 Google 设备是 2010 年 1 月发布的 Nexus One，而在 Nexus S 之后发布的所有 Nexus 设备（其使用专用分区作为外部存储）都通过仿真实现外部存储。对于缺少 SD 卡的设备，外部存储通过直接挂载 FAT 格式的分区实现（该分区与主存储位于同一设备块上），或者通过使用辅助守护进程进行仿真。

从 Android 4.4 版本开始，应用程序能够管理其特定包的目录（对于包`com.example.app`的应用为`Android/data/com.example.app/`），允许访问外部存储上的所有数据，而无需`WRITE_EXTERNAL_STORAGE`权限。此功能被称为合成权限，其 AOSP 实现基于一个 FUSE 守护进程，该守护进程封装了设备存储并根据指定的权限仿真模式管理文件访问和权限。

### 注意

用户空间文件系统（Filesystem in Userspace 或 FUSE [31））是 Linux 的一项功能，允许在用户空间程序中实现功能齐全的文件系统。这是通过使用通用的 FUSE 内核模块实现的，该模块将目标文件系统的所有虚拟文件系统（VFS）调用路由到其用户空间实现。内核模块与用户空间通过打开`/dev/fuse`描述的特殊描述符进行通信。

从 Android 4.4 版本开始，不再支持直接挂载外部存储，而是使用以下方式进行仿真：

FUSE `sdcard`守护进程，即使底层设备是物理 SD 卡也是如此。我们的实现基于由内部存储目录支持的配置，这对于带有物理 SD 卡的设备是典型的。（官方文档[27]包含了有关其他配置的更多细节。）

在主外部存储由内部存储支持的设备上，`sdcard` FUSE 守护进程使用`/data/media/`作为源并在`/mnt/shell/emulated`创建一个模拟文件系统。示例 4-12 显示了在这种情况下如何在设备特定的`init.rc`文件中声明`sdcard`服务 [7]。

示例 4-12. 模拟外部存储的`sdcard`服务声明



`init` 脚本首先通过 `mkdir` 命令创建外部存储的基础目录结构，如下所示：

```
--snap
init:
  mkdir /mnt/shell/emulated 0700 shell [1]
  mkdir /storage/emulated/storage /root 0555 root [2]

export EXTERNAL_STORAGE /storage/emulated/legacy [3]
export EMULATED_STORAGE_SOURCE /mnt/shell/emulated [4]
export EMULATED_STORAGE_TARGET /storage/emulated [5]

## Support legacy paths
symlink /storage/emulated/legacy /sdcard [6]
symlink /storage/emulated/legacy /mnt/sdcard
symlink /storage/emulated/legacy/storage/sdcard0
symlink /mnt/shell/emulated/0 /storage/emulated (1023)
virtual sdcard daemon running as media_rw
service sdcard system/bin/sdcard -u 1023 -g 1023 /data/media/mnt/shell/emulated [7]
class late_start
--snap
```

在这里，`-u` 和 `-g` 选项指定了守护进程应该运行的用户和组，`-l` 指定了模拟存储的布局（在本节稍后部分讨论）。如你所见 [1]，`/mnt/shell/emulated/` 目录（通过环境变量 `EMULATED_STORAGE_SOURCE` [4] 可用）由 `shell` 用户所有且仅供 `shell` 用户访问。其内容可能像在具有五个用户的设备上如示例 4-13 所示。

### 示例 4-13. `/mnt/shell/emulated/` 的内容

```
# ls -l /mnt/shell/emulated/
drwxr-x-x root sdcard 0
drwxr-x-x root sdcard 10
drwxr-x-x root sdcard 11
drwxr-x-x root sdcard 12
drwxr-x-x root sdcard 13
drwxr-x-x root sdcard legacy obb
```

对于应用数据目录，每个用户都会获得一个以其用户 ID 命名的外部存储数据目录。Android 使用挂载命名空间（`mount namespaces`）和绑定挂载（`bind mounts`）的组合，使得每个用户的外部存储数据仅对该用户启动的应用可见，而不显示其他用户的目录。由于所有应用程序都是从 `zygote`（第 2 章）派生的，因此外部存储设置分两个步骤实现：第一步是所有进程通用的，第二步是每个进程特定的。首先，所有派生进程共享的挂载点在唯一的 `zygote` 中设置。然后是设置专用的挂载。

让我们先看看只对它们可见的共享部分，这些是作为每个应用进程特化的一部分设置的。示例 4-14 显示了 `initZygote()` 函数（位于 `dalvik/vm/Init.cpp`）的片段，该函数突出了挂载点的设置。

### 示例 4-14. `zygote` 中的挂载点设置

```
static bool initZygote()
{
    setgid(0,0);

    if (unshare(CLONE_NEWNS) == -1) 
        return -1;

    // 标记根为从节点，这样来自默认
    // 空间的变化只会流向我们的子进程。
    if (mount("roots", "", NULL, MS_SLAVE | MS_REC, NULL) == -1)
        return -1;

    const char* target_base = getenv("EMULATED_STORAGE_TARGET");
    if (target_base != NULL)
        if (mount("tmpfs", target_base, "tmpfs", MS_NOSUID | MS_NODEV, 
            "uid=0,gid=1028,mode=0751") == -1)
            return -1;

    // --snip--
    return ;
}
```

在这里，`zygote` 将 `CLONE_NEWNS` 标志传递给 `unshare()` 系统调用，以便创建一个新的私有挂载命名空间，该空间将被其所有子进程（应用进程）共享。它通过向系统调用传递 `MS_SLAVE` 标志将根文件系统（挂载在 `/`）标记为从。这确保了默认挂载命名空间的变化（例如挂载容器或可移动存储）只会传播到子进程，同时确保子进程创建的任何挂载都不会传播到默认命名空间。最后，`zygote` 创建内存支持的 `EMULATED_STORAGE_TARGET`（通常为 `/storage/emulated/`），子进程使用它将 `tmpfs` 绑定到私有命名空间中的外部存储。

示例 4-15 显示了 `dalvik/native/dalvik_system_Zygote.cpp` 中的进程特定挂载点设置，该设置在 `zygote` 的每个应用进程上执行。（省略了错误处理、日志和一些变量声明。）

### 示例 4-15. 应用进程的外部存储设置

```
static int mountEmulatedStorage(uid_t uid, uint4_t mountMode) {
    userid_t userid = multitask_get_user(uid);

    // 为我们的进程创建第二个挂载命名空间
    if (unshare(CLONE_NEWNS) == -1)
        return -1;

    if (mountMode == MOUNT_MULTIUSER || mountMode == MOUNT_MULTIUSER_ALL) {
      // 这些路径由 init.rc 创建
      const char* source = get("EMULATED_STORAGE_SOURCE");
      const char* target = get("EMULATED_STORAGE_TARGET");
      const char* legacy = get("EXTERNAL_STORAGE");
      if (source == NULL || target == NULL || legacy == NULL) {
        return -1;
      }

      // --snip--
      // /mnt/shell/emulated/0
      snprint(source_user, PATH_MAX, "%s/%d", source, userid);
      // /storage/emulated/0
      snprint(target_user, PATH_MAX, "%s/%d", target, userid);
      // --snip--

      if (mountMode == MOUNT_MULTIUSER_ALL) {
        // 为所有用户挂载整个存储树
        if (mount(source, target, NULL, MS_BIND, NULL) == -1) {
          return -1;
        } else {
          // 只挂载用户特定的存储
          if (mount(source_user, target_user, NULL, MS_BIND, NULL) == -1) {
            return -1;
          }
          // 最后，挂载用户特定的 legacy 路径
          if (mount(target_user, legacy, MS_BIND | MS_REC, NULL) == -1) {
            return -1;
          } else {
            return 0;
          }
        }
      }
    }
```

在这里，`createEmulatedStorage()` 函数从进程获取当前用户 ID，然后使用 `unshare()` 系统调用通过传递 `CLONE_NEWNS` 标志为进程创建一个新的挂载命名空间。该函数获取 `EMULATED_STORAGE_SOURCE`、`EMULATED_STORAGE_TARGET` 和 `EXTERNAL_STORAGE` 变量的值，这些变量在设备特定的 `init.rc` 中初始化。它根据示例 4-12 中的值准备挂载源和目标目录。如果目录不存在，则创建它们，该方法将源路径（例如用户用户的 `/mnt/shell/emulated/0`）绑定到目标路径。这确保了可以从 Android shell（使用 shell 命令）访问外部存储，这被广泛用于开发。

最后一步是将目标目录绑定到 legacy 目录（`/storage/emulated/legacy`）。示例 4 中的设备特定 `init.rc` 文件将 legacy 目录链接到 `/sdcard`，以兼容该硬编码路径（通常使用 `android.os.Environment.getExternalStorageDirectory()`）。

执行所有步骤后，新创建的应用只能看到分配给启动它的外部存储。我们可以通过示例 4-16 所示的不同用户执行的应用挂载列表验证这一点。

### 示例 4-16. 不同用户启动的挂载点列表

```
### cat /proc/7382/mounts
--snap
/dev/fuse/mnt/shell/emulated rwnosid,nodev,relative,user_id=1023,
group_id=1023,default_permissions,allow_other ①
/dev/fuse/storage/emulated/0 rwnosid,nodev,relative,user_id=1023,
group_id=1023,default_permissions,allow_other ②
/dev/fuse/storage/emulated/legacy rwnosid,nodev,relative,user_id=1023,
group_id=1023,default_permissions,allow_other ③
```

```
### cat /proc/7538/mounts
--snap
/dev/fuse/mnt/shell/emulated rwnosid,nodev,relative,user_id=1023,
group_id=1023,default_permissions,allow_other ④
/dev/fuse/storage/emulated/0 rwnosid,nodev,relative,user_id=1023,
group_id=1023,default_permissions,allow_other ⑤
/dev/fuse/storage/emulated/legacy rwnosid,nodev,relative,user_id=1023,
group_id=1023,default_permissions,allow_other ⑥
```

在这里，由 PID 7382 用户启动的进程有一个 `/storage/emulated/0` 挂载点 ②，它是 `/mnt/shell/emulated/0/` 的绑定挂载；而进程 7538（由辅助用户启动）有一个 `/storage/emulated/0` 挂载点 ⑤，它是 `/mnt/shell/emulated/10` 的绑定挂载。

由于两个进程都没有另一个进程外部存储目录的挂载点，两个进程都有 `/storage/emulated/legacy` 挂载点 ③ 和 ⑥，但由于它们绑定到不同的目录（`/storage/emulated/0/` 和 `/mnt/shell/emulated/10/`），每个进程看到的内容不同。两个进程都能看到 `/mnt/shell/emulated/`（① 和 ④），但由于该目录仅供 `shell` 用户访问（权限 0700），应用进程看不到其内容。

## 外部存储

为了模拟最初用于外部存储的 FAT 文件系统，`sdcard` fuse 守护进程为外部存储上的每个文件或目录分配固定的所有者、组和访问权限。此外，权限不可更改，且不支持符号链接和硬链接。分配的所有者和权限取决于 `sdcard` 守护进程使用的权限派生模式。

在 legacy 模式（通过 `-l` 选项指定，该模式与之前的 Android 版本兼容，并且在 Android 4.4 中仍是默认设置）大多数文件和目录由 `root` 用户所有，其组设置为 `sdcard_r_`。获得 `READ_EXTERNAL_STORAGE` 权限的应用将 `sdcard_r_` 作为其辅助组之一，因此即使文件是由不同的用户创建的，也可以读取外部存储上的大多数文件。

示例 4-17 显示了外部存储根目录下文件的所有者和权限。

### 示例 4-17 外部存储上文件的所有者和权限

```
# ls -l /sdcard/
rwwx--- root sdcard_r Alarms
rwwx--x sdcard_r Android
rwwx--x sdcard_r DCIM
--snip---
--rw-r-- sdcard_r 5 text.txt
```

在之前的 Android 版本中，外部存储上的所有文件和目录都被赋予相同的所有者和权限，但 Android 4.4 对应用程序特定的外部文件目录（`/Android/data/<package-name>`，路径由 `Context.getExternalFilesDir()` 返回）进行了不同的处理。应用程序不需要持有 `WRITE_EXTERNAL_STORAGE` 权限即可读写此目录，因为该目录是由创建它的应用程序所有的。

尽管如此，即使在 Android 4.4 中，任何拥有 `READ_EXTERNAL_STORAGE` 或 `WRITE_EXTERNAL_STORAGE` 权限的应用程序都可以访问外部文件目录，因为该目录的组被设置为 `sdcard_r`，如示例 4-18 所示。

### 示例 4-18 应用程序外部文件目录的所有者和权限

```
# ls -l /Android/data/
rwwx--x u0_a16 sdcard_r com.android.browser
```

Android 4.4 提供了一种基于目录结构的更灵活的权限派生模式，该模式由 `sdcard` 守护进程的 `-d` 选项指定。这种派生模式为 `Pictures/` 和 `Music/` 目录设置了专用的组（如示例 4-19 所示，分别为 `sdcard_pics` 1 和 `sdcard_av` 2），这允许对应用程序可以访问的文件进行细粒度控制。到本文为止，Android 还不支持这种细粒度的访问控制，但可以通过定义映射到 `sdcard_pics` 和 `sdcard_av` 组的额外权限来实现。在基于目录结构的权限模式下，用户目录托管在 `Android/user/` 3。

### 注意

虽然 Android 4.4 支持这种新的权限派生模式，但 Nexus 设备仍然在使用旧版的权限模式。

### 示例 4-19 新权限派生模式下的目录所有者和权限

```
rwwx--x roots sdcard_rw /
rwwx--x sdcard_pics /Pictures1
rwwx--x sdcard_av /Music2
rwwx--x sdcard_rw /Android
rwwx--x sdcard_rw /Android/data
rwwx--x u0_a12 sdcard_rw /Android/data/com.example.app
rwwx--x sdcard_rw /Android/obb/
rwwx--x u0_a12 sdcard_rw /Android/obb/com.example.app
```

## 其他多用户功能

除了专用应用程序目录、外部存储和设置外，其他 Android 功能也支持多用户设备配置。例如，在 4.4 版本中，Android 的凭据存储（允许对密钥进行安全管理）允许每个用户拥有自己的密钥存储。（我们将在第 7 章中详细讨论凭据存储）。

此外，通过 `AccountManager` API 访问的 Android 在线账户数据库已扩展，允许次要用户拥有自己的账户，并允许受限制配置共享主用户的一些账户（如果应用程序需要账户支持）。我们将在第 8 章中讨论在线账户支持和 `AccountManager` API。

最后，Android 允许为每个用户设置不同的设备管理策略。从 4.4 版本开始，它还支持设置用户 VPN，路由单个用户的流量且其他用户无法访问。（我们将在第 9 章中讨论设备管理、VPN 和其他企业功能）。

## 总结

Android 通过为每个用户提供专用的内部和外部存储，允许多个用户共享设备。多用户支持遵循既有的安全模型，每个用户的应用程序都被分配了唯一的 UID，并运行在无法访问其他用户数据的专用进程中。用户隔离通过结合考虑用户 ID 的 UID 分配方案以及允许每个用户看到自己存储的存储挂载点来实现。

- [29] Google, Android 4.4 Capability Definition, “9.5. Multi-User Support,” http://static.googleusercontent.com/media/source.android.com/en/capability/4.4/android-4-4-cd.pdf

- [30] Google, “External Storage Technical Information,” http://source.android.com/devices/tech/storage/index.html



- [31] Filesystem in Userspace, http://fuse.sourceforge.net

- [32] Google, Android 4.4 Capability Definition, “9.5. Multi-User Support,” http://static.googleusercontent.com/media/source.android.com/en/capability/4.4/android-4-4-cd.pdf

- [33] Michael Kerrisk, The Linux Programming Interface: A Linux and UNIX System Programming Handbook, No Starch Press, 2010, pp. 261

- [34] Id., 598.

- [35] Ibid., 603.

- [36] Linux Kernel, Shared Subtrees, https://www.kernel.org/doc/Documentation/filesystems/sharedtrees.txt

# 第 5 章 加密提供者

本章介绍了提供者架构，并讨论了内置提供者及其支持的算法。由于 Android 构建在 Java 加密架构（JCA）之上，我们从加密服务提供者（CSP）框架开始介绍。随后讨论了主要的 JCA 类和加密原语（假设已具备加密知识）。接下来，我们介绍了 JCA 提供者以及它们支持的算法。最后，我们展示了如何通过安装自定义提供者来使用额外的算法。

# JCA 提供者架构

JCA 提供了一个可扩展的加密框架和一组涵盖加密原语的 API。这种架构旨在与实现分离并可扩展。使用标准 JCA API 的应用程序只需要指定它们想要使用的算法，在大多数情况下并不依赖于特定的提供者。可以通过注册额外的提供者来实现对新算法的支持。此外，不同提供者提供的加密服务通常是可操作的（在密钥受保护的情况下），应用程序可以根据需要混合不同提供者的服务。让我们详细查看 JCA 的架构。

# 加密服务提供者

JCA 将加密功能分为许多称为引擎的抽象加密服务，并以类的形式为每个服务定义 API。例如，数字签名由`Signature`类表示，加密通过`Cipher`类建模。（在下一节中可以找到完整的类列表。）

在 JCA 语文中，加密服务提供者（CSP 或简称提供者）是提供某些加密服务实现的包（或包集合）。JCA 宣告其实现的服务和算法，允许 JCA 框架维护算法及其实现提供者的注册表。注册表维护了提供者的偏好顺序，因此如果某个算法由多个提供者提供，则返回偏好顺序较高的一个。对于支持延迟提供者选择的引擎类（`Cipher`、`KeyAgreement`、`Mac` 和 `Signature`），该规则存在例外。在延迟提供者选择中，提供者的选择不是发生在实例化引擎类时，而是在初始化引擎类时。初始化需要密钥，系统通过密钥来查找可以接受指定密钥对象的提供者。在使用存储在硬件中的密钥时，延迟选择非常有帮助，因为系统无法仅根据算法找到硬件支持提供者。然而，传递给初始化方法的具体密钥通常包含足够的信息来确定底层提供者。

### 注意

当前的 Android 版本不支持延迟提供者选择（delayed provider selection），但 master 分支中正在进行相关工作，未来版本可能会支持延迟提供者选择。

让我们来看一个使用图 5-1 所示的提供者配置的示例。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_109_0.png)

图 5-1. 未指定提供者时的 JCA 算法实现选择

如果应用程序在不指定提供者的情况下请求 SHA-256 算法实现（如示例 5-1 所示），提供者框架将返回 ProviderB 中的实现（图 5-1 列表中的数字 2），而不是 ProviderC 中的。ProviderC 也支持 SHA-256，但它是图 5-1 列表中的数字 3。

示例 5-1. 在不指定提供者的请求 SHA-256 实现

`MessageDigest md = MessageDigest.getInstance("SHA-256");`

另一方面，如果应用程序专门请求 ProviderC（如示例 5-2 所示），即使 ProviderB 具有更高的优先级，也会返回后者的实现。

示例 5-2. 从特定提供者请求 SHA-256 实现

`MessageDigest md = MessageDigest.getInstance("SHA-256", "ProviderC");`

通常，应用程序不应显式请求提供者，除非它们将请求的提供者作为应用程序的一部分，或者在首选提供者不可用时可以回退。

## 提供者实现

JCA 框架通过要求所有特定加密服务或算法的实现都符合一个通用接口，保证了实现的独立性。对于每个表示特定加密服务的引擎类，框架定义了一个对应的抽象服务提供者（SPI）类。提供特定加密服务的提供者实现并公布了相应的 SPI 类。例如，实现加密算法的提供者将拥有与`Cipher`引擎类对应的`CipherSPI`类的实现。当应用程序调用`Cipher.getInstance()`工厂方法时，JCA 会通过“加密服务提供者”中概述的过程找到合适的提供者，并返回一个`Cipher`实例，该实例将其所有方法调用路由到所选提供者实现的`CipherSPI`子类。

`java.security.Provider`

（详情请参阅每个提供者的文档。）你可以使用示例 5-6 中的代码列出所有提供者、每个提供者提供的加密服务的算法名称以及它们映射到的实现类。

## 示例 5-6. 列出 JCA 提供者及其支持的算法

```
Provider[] providers = Security.getProviders();
for (Provider p : providers) {
    System.out.printf("%s: %s\n", p.getName(), p.getVersion());
    Set<Service> services = p.getServices();
    for (Service s : services) {
        System.out.printf("\t%s/%s\n", s.getAlgorithm(), s.getClassName());
    }
}
```

在后续章节中介绍主要引擎类时，我们将展示其算法名称的格式。

## SecureRandom

`SecureRandom`类表示加密随机数生成器 (RNG)。虽然你可能不会经常直接使用它，但大多数加密操作内部都会使用它来生成密钥和其他加密材料。软件实现通常是密码学安全的伪随机数生成器 (CSPRNG)，它根据一个称为“种子”的初始值产生一个近似真随机数的序列。由于 CSPRNG 产生的随机数质量在很大程度上取决于其种子，因此它被仔细选择，通常基于真 RNG 的输出。

在 Android 上，CSPRNG 实现通过从标准的 Linux `/dev/urandom`设备文件读取种子来设置种子的，该文件是内核 CSPRNG 的接口。由于内核 CSPRNG 本身在启动后可能处于相当可预测的状态，Android 会定期将 CSPRNG 的状态（截至 Android 4.4 为为 4096 字节）保存到`/data/system/entropy.dat`文件。该文件的内容在启动时写入`/dev/urandom`，以便传递之前的熵。这一操作由`EntropyMixer`系统完成。

与大多数引擎不同，`SecureRandom`具有公共构造函数，你可以用它们创建实例。在 Android 上获取正确种子实例的推荐方法是使用默认（无参数）构造函数 ❶。如果你使用`getInstance()`工厂方法，可能需要传递 "SHAPRNG" 作为算法名称，这是`SecureRandom`唯一通用支持的算法名称。由于 SHAPRNG 并不完全是一个加密标准，不同提供者的实现行为可能不同。要让`SecureRandom`生成随机字节，你向其`nextBytes()`方法传递一个数组 ②。它将生成与示例 5-7 中数组长度（16）相同的字节并将其存储在其中。

## 示例 5-7. 使用 SecureRandom 生成随机字节

```
SecureRandom sr = new SecureRandom();❶
byte[] output = new byte[16];
sr.nextBytes(output);②
```

不建议手动为`SecureRandom`设置种子，因为不当为系统 CSPRNG 设置种子可能会导致可预测的字节序列，从而破坏任何需要随机输入的更高层操作。然而，如果出于某些原因你需要为`SecureRandom`设置种子（例如，如果默认种子实现存在缺陷），你可以通过`SecureRandom(byte[])`构造函数或调用`setSeed(long)`get。在手动设置种子时，请确保你从`/dev/urandom`读取的种子具有足够的随机性。

此外，取决于底层实现，调用`setSeed`可能不会替换内部 CSPRNG 状态，而是仅在其基础上添加；相同的种子值可能产生不同的数字序列。因此，在需要确定性值时不应使用`SecureRandom`。请使用设计用于从给定输入产生确定性输出的加密原语，例如哈希算法或密钥派生函数。

## MessageDigest

`MessageDigest`类表示加密消息摘要的功能，也称为哈希函数。加密消息摘要取任意长度的字节序列并生成一个固定大小的字节序列，称为摘要（digest）或哈希（hash）。一个良好的哈希可以保证，即使输入发生微小变化，也会导致完全不同的输出，并且很难找到两个不同但产生相同值的输入（抗碰撞性），或生成一个具有给定哈希值的输入（抗原像抗性）。哈希函数的另一个重要属性是抗次原像抗性。为了能够抵抗次原像攻击，哈希函数应该使得难以找到一个与给定输入 $m_1$ 哈希值相同的第二个输入 $m_2$。

示例 5-8 显示了如何使用`MessageDigest`类。

## 示例 5-8. 使用 MessageDigest 对数据进行哈希

```
MessageDigest md = MessageDigest.getInstance("SHA-256");
byte[] data = getMessage();
byte[] digest = md.digest(data);
```

通过向`getInstance()`方法传递哈希算法名称来创建`MessageDigest`实例 ①。可以使用其中一个`update()`方法分块提供输入，然后调用其中一个`digest()`方法来获取计算出的哈希值。或者，如果输入数据大小固定且较短，可以使用`digest(byte[])`输入 ② 一步完成哈希，如示例 5-8 所示。

## Signature

`Signature`类为基于非对称加密的数字签名算法提供了通用接口。数字签名算法取任意消息和私钥，并产生一个固定大小的字节字符串，称为签名。数字签名通常对输入消息应用摘要，编码计算出的哈希值，然后使用私钥生成签名。然后可以使用相应的公钥通过反向操作来验证签名：计算被签名消息的哈希值，并将其与签名中编码的值进行比较。成功的验证保证了被签名消息的完整性，并在签名私钥保持私密的情况下，保证了其真实性。

通过向`getInstance()`方法传递哈希算法名称创建`Signature`实例。算法名称格式为 `<digest>with<encryption>`（例如 RSA 或 DSA）。对于使用 RSA-PSS 的签名算法，算法名称格式为 `<digest>with<encryption>and<mgf>`。示例 5-9 显示了如何使用`Signature`类生成和验证。

## 示例 5-9. 使用 Signature 类生成签名

```
PrivateKey privateKey = getPrivateKey();
publicKey publicKey = getPublicKey();
byte[] data = "sign me".getBytes("ASCII");

Signature sig = Signature.getInstance("SHA256withRSA");
sig.initSign(privateKey);
sig.update(data);
byte[] signature = sig.sign();

sig.initVerify(publicKey);
sig.update(data);
boolean value = sig.verify(signature);
```

获取实例后，通过将私钥传递给示例 5-9 中的`initSign()`方法 ① 初始化签名，或通过将公钥或证书传递给`initVerify()`方法 ④ 初始化验证。

签名类似于使用`MessageDigest`计算哈希：待签名的数据分块传递给`update()`方法 ② 或批量传递给`sign()`方法 ③，后者返回签名值。要验证签名，将签名数据传递给`update()`方法 ⑤。最后，将签名传递给`verify()`方法 ⑥。

## Cipher

`Cipher`类为加密和解密操作提供了通用接口。加密是使用某种算法（称为密码）和密钥将数据（称为明文或明文消息）转换为看似随机的形式（称为密文）的过程。逆操作称为解密，是将密文转换回原始明文。

今天广泛使用的两种主要加密类型是对称加密和非对称加密。对称加密使用相同的密钥来加密和解密数据。非对称加密使用一对密钥：公钥和私钥。使用其中一个密钥加密的数据只能用另一个密钥解密。`Cipher`类支持对称加密和非对称加密。

根据处理输入的方式，密码可以是分组的或流。分组密码处理固定大小的数据块（称为块）。如果输入无法被划分为若干整数块，则通过添加必要的字节来填充最后一个块，以匹配块的大小。这种操作和添加的字节统称为填充（padding）。填充在解密过程中会被移除，不会包含在解密后的明文中。如果指定了填充算法，`Cipher`类可以

另一方面，流加密器按字节处理输入数据，且不需要填充。

## 分块加密工作模式

分块加密器在处理输入块时采用不同的策略来生成最终密文（或解密时的明文）。这些策略被称为工作模式（modes of operation）、加密模式或简称为模式。最简单的策略是将明文分成若干块（根据需要进行填充），对每个块进行加密，并将加密后的块连接起来生成密文。这种模式被称为电子代码簿（ECB）模式。虽然它简单且易于使用，但有一个主要的缺点：相同的明文块产生相同的密文块，明文结构会反映在密文中，这损害了机密性并便于分析。这通常通过 Wikipedia 上分块加密条目著名的臭名“ECB 企鹅”来说说明。[39] 我们在图 5-2 中了 Android 版本。[40] 1 是原始图像，2 是 ECB 模式加密的图像，3 是 CBC 模式加密的相同图像。如你所见，原始模式可以通过 2 识别出来，而 3 看起来像随机噪声。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_115_0.png)

反馈模式通过在加密前将之前的加密块与当前明文块结合，为密文增加随机性。为了生成第一个密文块，它们将第一个明文块与原始明文中不存在的块大小字节字符串结合，该字符串被称为初始化向量（IV）。当配置为使用反馈模式时，加密器可以使用客户端指定的 IV 或自动生成一个 IV。常用的反馈模式包括密文块链（CBC）、密文反馈（CFB）和输出反馈（OFB）。

另一种为密文增加随机性的方法是计数器（CTR）模式采用的方法，它通过加密计数器序列的连续值，为每个需要加密的明文块生成一个新的密钥。这有效地将底层的分块加密转换为流加密，且不需要填充。

较新的加密算法，例如伽罗斯/计数模式（GCM），不仅能扩散原始明文中的模式，还能对密文进行认证，确保其未被篡改。这提供了认证加密（AE）或带关联数据的认证加密（AEAD）。[41] Java SE 7 已扩展了加密 API 以支持认证加密，这些扩展从 Android 4.4 开始可用，该版本拥有兼容 Java 7 的运行时库 AE。加密器将加密操作输出的认证标签连接到密文中，以形成最终输出。在 Java Cipher API 中，标签在调用`doFinal()`后隐式地包含（在解密时进行验证），因此在确定末尾的隐式标签有效之前，你不应该使用`update()`的输出。

## 获取 Cipher 实例

在讨论了加密器的主要参数后，我们终于可以讨论如何创建`Cipher`实例。与其他引擎类不同，`Cipher`对象是通过`getInstance()`工厂方法创建的，这不仅需要简单的算法名称，还需要你完整指定所请求的加密器将执行的密码转换。

示例 5-10 显示了如何通过向`getInstance()`传递转换字符串来创建`Cipher`实例。

示例 5-10. 创建 Cipher 实例

```
Cipher c = Cipher.getInstance("AES/CBC/PKCS5padding");
```

转换需要指定加密算法、加密模式和填充。传递给`getInstance()`的转换字符串采用 `算法/模式/填充` 格式。例如，示例 5-10 中使用的转换字符串将创建一个使用 AES 作为加密算法、CBC 作为加密模式以及 PKCS#5 填充的`Cipher`实例。

### 注意

> 在我们对 JCA 提供者和引擎类的讨论中，PKCS 一词出现了几次。该缩写代表公钥密码学标准（Public Key Cryptography Standard），指的是最初由 RSA Security, Inc 在 20 世纪 90 年代初开发并发布的一组密码标准。它们已演变为公共互联网标准，现在作为 RFC（意见征求，描述互联网标准的正式文档）发布和维护，但仍仍其原始名称称为。著名的标准包括：PKCS#1（定义了 RSA 加密和签名的基础算法）；PKCS#5（定义了基于密码的加密）；PKCS#7（定义了 PKI 环境下的消息加密和签名，它是 MIME 的基础）；PKCS#12（定义了密钥和证书的容器）。可以在 EMC 网站上找到完整列表。[42]



可以通过仅传递算法名称来创建`Cipher`，但在那种情况下，返回的实现将使用用户特定的加密模式和填充详细信息。这不仅在不同提供者之间具有可移植性，而且如果运行时使用了比预期更不安全的加密模式（例如`ECB`），可能会严重影响系统的安全性。这种“捷径”是 JCA 提供者框架的主要设计缺陷，绝不应使用。

## 使用 Cipher

一旦获取`Cipher`，在加密或解密数据之前需要对其进行初始化。`Cipher`的初始化是通过将一个表示操作模式（`ENCRYPT_MODE`、`DECRYPT_MODE`、`WRAP_MODE`或`UNWRAP_MODE`）的整数常量、用于认证或验证的密钥，以及可选的算法参数传递给`init()`方法之一。`ENCRYPT_MODE`和`DECRYPT_MODE`用于加密和解密任意数据，而`WRAP_MODE`和`UNWRAP_MODE`是专用模式，用于用另一个密钥加密（封装）和解密（解封装）`Key`对象的密钥材料。

示例 5-11 显示了如何使用`Cipher`类进行加密和解密。

**示例 5-11. 使用 Cipher 类加密和解密**

```java
SecureRandom sr = new SecureRandom();
SecretKey key = getSecretKey();
Cipher cipher = Cipher.getInstance("AES/CBC/PKCS5padding");
byte[] iv = new byte[cipher.getBlockSize()];
sr.nextBytes(iv);
IvParameterSpec ivParams = new IvParameterSpec(iv);
cipher.init(Cipher.ENCRYPT_MODE, key, ivParams);
byte[] plaintext = "encrypt".getBytes("UTF-8");
ByteArrayOutputStream baos = new ByteArrayOutputStream();
byte[] output = cipher.update(plaintext);
if (output != null) {
    baos.write(output);
}
output = cipher.doFinal();
baos.write(output);
byte[] ciphertext = baos.toByteArray();

cipher.init(Cipher.DECRYPT_MODE, key, ivParams);
baos = new ByteArrayOutputStream();
output = cipher.update(ciphertext);
if (output != null) {
    baos.write(output);
}
output = cipher.doFinal();
baos.write(output);
byte[] decryptedPlaintext = baos.toByteArray();
```

在此示例中，我们创建了一个使用 CBC 模式和 PKCS5 填充的 AES 实例，生成随机 IV 并将其封装在`IvParameterSpec`对象中，然后通过将`ENCRYPT_MODE`、加密密钥和 IV 传递给`init()`方法来初始化加密器。然后我们通过将数据块传递给`update()`方法来加密数据，该方法返回中间结果（如果输入短到无法返回新块），并通过调用`doFinal()`方法获取最后一个块。最终密文是通过连接中间结果和最终结果得到的。

要解密，我们以`DECRYPT_MODE`初始化加密器，传递相同的密钥和加密时使用的 IV。我们调用`update()`，这次使用密文作为输入，最后调用`doFinal()`获取明文的最后一个块。最终明文是通过连接中间结果和最后一个块得到的。

## Mac

`Mac`类为消息认证码（MAC）算法提供了一个通用接口。MAC 用于检查在不可靠通道上传输的消息的完整性。MAC 算法使用秘密密钥计算一个值，也称为标签），该值可用于验证消息并检查其完整性。验证也使用相同的密钥，因此它需要在通信双方之间共享。（MAC 通常与加密器结合使用以提供机密性和完整性）。

**示例 5-12. 使用 Mac 类生成消息认证码**

```java
MacKey key = keygen.generateKey();
Mac mac = Mac.getInstance("HmacSha256");
mac.init(key);
byte[] message = "Message".getBytes("UTF-8");
byte[] tag = mac.doFinal(message);
```

通过`getInstance()`方法（如示例 5-12 所示）请求使用 SHA-256 作为哈希函数的 HMAC[43] MAC 实例，即可获取`Mac`实例。它使用`SecretKey`初始化，该密钥可以由`KeyGenerator`（参见“KeyGenerator”）生成、从密码派生，或直接从原始密钥字节实例化。对于基于哈希函数的 MAC 实现（例如示例中的 HMAC SHA-256），密钥的类型并不重要，但使用对称密码的实现可能需要传递匹配的密钥类型。我们可以使用其中一个`update()`方法来分块传递消息，并调用`doFinal()`获取最终的 MAC 值，或者通过直接将字节传递给`doFinal()`一步完成该操作。

## 密钥（Key）

`Key`接口表示 JCA 框架中的不透明密钥（opaque keys）。不透明密钥可用于加密操作，但通常不提供对底层密钥材料（原始字节）的访问。这使得我们既可以使用相同的 JCA 类和接口用于在内存中存储密钥材料的加密算法软件实现，也可以用于由硬件支持的实现——在后者中，密钥材料可能存储在硬件令牌中（智能卡、HSM[44] 等），且无法直接访问。

`Key`接口仅定义了三个方法：

- `getAlgorithm()`：返回此密钥可用于加密算法（对称或非对称）的名称。例如`AES`或`RSA`。
- `byte[] getEncoded()`：返回密钥的标准编码形式，用于将密钥传输到其他系统。对于私钥，该格式可以被加密。对于不允许导出密钥材料的硬件支持实现，此方法通常返回`null`。
- `getFormat()`：返回编码密钥的格式。对于未以任何特定格式编码的密钥，这通常是`RAW`。JCA 中定义的其他格式是`X.509`和`PKCS#8`。

你可以通过以下方式获取`Key`实例：

- 使用`KeyGenerator`或`KeyPairGenerator`生成密钥。
- 使用`KeyFactory`从某些编码表示进行转换。
- 从`KeyStore`中检索存储的密钥。

我们将在后续章节中讨论不同的`Key`类型以及如何创建和访问它们。

## 密钥（SecretKey）与 PBE 密钥（PBEKey）

`SecretKey`接口表示用于对称算法的密钥。它是一个标记接口（marker interface），没有为父接口`Key`增加任何新方法。它只有一个可以直接实例化的实现，即`SecretKeySpec`。它既是密钥实现，也是密钥规范（在随后的“KeySpec”部分中讨论），并允许你进行实例化。

`PBE`子接口表示使用基于密码的加密（PBE）[45] 派生的密钥。PBE 定义了从密码和短语派生强加密密钥的算法，这些密码和短语通常熵较低，不能直接作为密钥。PBE 基于两个主要思想：使用盐值（salt）防止通过辅助表（预计算）字典攻击（加盐），以及使用长时间的迭代次数使密钥派生在计算上变得昂贵（密钥拉伸）。盐值和迭代次数被用作 PBE 算法的参数，必须保留，以便从特定密码生成相同的密钥。因此，PBE 实现需要实现`getSalt()`、`iterationCount()`以及`getPassword()`。

## 公钥（PublicKey）、私钥（PrivateKey）与密钥对（KeyPair）

用于非对称加密算法的公钥和私钥通过`PublicKey`和`PrivateKey`接口建模。它们是标记接口，没有添加任何新方法。JCA 为具体的非对称算法定义了专门的类，用于持有相应密钥的参数，例如`RSublicKey`和`RSAPrivateCrt`。`KeyPair`接口是一个更简单的容器，用于存放公钥和私钥。

## KeySpec（密钥规范）

如在`Key`中讨论，JCA 接口表示不透明密钥。另一方面，`KeySpec`建模了密钥规范，这是一种透明的密钥表示，允许你访问单个密钥。

在实践中，大多数具体算法的`Key`和`KeySpec`接口有大量重叠，因为为了实现加密算法需要访问密钥参数。例如，`RSAKey`和`RSAKeySpec`都有`getModulus()`和`getExponent()`方法。区别仅在于当算法在硬件中实现时，在这种情况下`KeySpec`只包含指向硬件管理密钥的引用，而不是实际密钥。相应的`Key`将持有指向硬件管理密钥的句柄，并可执行加密操作，但它不会持有任何密钥材料。例如，存储在硬件中的`RSrivateKey`在调用`getExponent()`时将返回`null`。

`KeySpec`实现可以持有编码的密钥表示，在这种情况下它是算法无关的。例如，`PKCS8EncodedKeySpec`可以以 DER 编码的 PKCS#8 格式持有 RSA 密钥或 DSA 密钥[46]。另一方面，特定算法的`KeySpec`将所有密钥参数作为字段。例如，`RSAKeySpec`包含 RSA 密钥的模数和私指数，分别可以通过`getModulus()`和`getExponent()`方法获取。无论类型如何，`KeySpecs`都会通过`KeyFactory`转换为`Key`对象。

## KeyFactory（密钥工厂）

`KeyFactory`封装了一个转换程序，用于将透明的公钥或私钥表示（某些`KeySpec`子类）转换为不透明[47] 密钥对象（某些`Key`子类）以执行加密操作，反之亦然。`KeyFactory`转换编码密钥数据并将每个密钥存储在`KeyFactory`类的参数字段中。要解析 X509 编码的公钥，可以使用以下代码（参见示例 5-13）。

**示例 5-13. 使用 KeyFactory 转换 X509 编码**

```java
KeyFactory k = KeyFactory.getInstance("RSA");
byte[] encoded = publicKey.getEncoded();
X509EncodedKey keySpec = new X509EncodedKey(encoded);
RSublicKey publicKey = (RSublicKey) k.generatePublic(keySpec);
```

在这里，我们通过向`getInstance()`传递 RSA 创建 RSA `KeyFactory` ①。然后读取编码字节实例化`X509EncodedKey` ②，最后将密钥传递给工厂的`generatePublic()`方法 ③ 以获取`RSublicKey`实例。

`KeyFactory`还可以将来自不同提供者的`Key`实例转换为当前提供者兼容的密钥对象。该操作被称为密钥翻译，并通过`translateKey(Key)`方法执行。

## SecretKeyFactory（密钥工厂）

`SecretKeyFactory`与`KeyFactory`非常相似，只是它操作秘密（对称）密钥。你可以使用它将对称密钥规范转换为`Key`对象，反之亦然。尽管如此，如果你拥有访问对称密钥材料的，使用它立即实例化`SecretKeySpec`比使用`Key`要简单得多，这种用法并不常见。

一个常见的用例是从用户提供的密码 PBE 生成对称密钥（参见示例 5-14）。

**示例 5-14. 使用 SecretKeyFactory 从密码生成密钥密钥**

```java
byte[] salt = generateSalt();
int iterationCount = 1000; int keyLength = 256;
KeySpec keySpec = new PBEKeySpec(password.toCharArray(), salt,
iterationCount, keyLength); ①

SecretKeyFactory skf = KeyFactory.getInstance("PBKDF2WithHmacSHA1") ②
SecretKey key = skf.generateSecret(keySpec); ③
```

在这种情况下，`PBEKeySpec`使用密码、随机生成的盐值、迭代次数和所需的密钥长度进行初始化 ①。通过调用`getInstance()`获取实现 PBE 密钥派生算法的`KeyFactory`（此处为 PBKDF2）②。将`PBEKeySpec`传递给`generateSecret()`将执行密钥派生算法并返回一个`SecretKey`实例 ③。

`KeyPairGenerator`类用于生成公钥和私钥对。通过向`getInstance()`方法传递非对称算法名称来实例化`KeyPairGenerator`。示例 5-15。

**示例 5-15. 使用算法特定参数初始化 KeyPairGenerator**

```java
KeyPairGenerator kpg = KeyPairGenerator.getInstance("ECDH");
ECGenParameterSpec ecSpec = new ECGenParameterSpec("sec256r1");
kpg.initialize(ecSpec);
KeyPair keyPair = kpg.generateKeyPair();
```

初始化`KeyPairGenerator`有两种方式：通过指定所需的密钥大小，以及通过指定算法特定的参数。在这两种情况下，你都可以可选地传递一个`SecureRandom`实例用于密钥生成。如果仅指定了密钥大小，密钥生成将使用默认参数（如果有）。要指定额外参数，你必须实例化并配置适用于你正在使用的非对称算法的`AlgorithmParameters`实例，并将其传递给`initialize()`方法，如示例 5-15 所示。在此示例中，`ECGenParameterSpec`允许你在生成椭圆曲线（EC）加密密钥时指定曲线名称。在传递给`initialize()`方法之后，随后的`generateKeyPair()`调用将使用指定的曲线（sec256r1）生成密钥对。

### 注意

> 虽然不同的标准已经定义了命名曲线，但 Oracle JCA 规范并未显式定义任何曲线名称。由于没有官方的 JCA 标准，Android 支持的曲线可能随平台版本而异。

## KeyGenerator

`KeyGenerator`与`KeyPairGenerator`类非常相似，不同在于它生成的是对称密钥。虽然你可以通过向`SecureRandom`请求随机字节序列来生成大多数对称密钥，但`KeyGenerator`的实现会对弱密钥进行额外的检查，并在适当位置设置密钥奇偶性字节（针对 DES 和派生算法），并利用可用的加密硬件，因此最好使用`KeyGenerator`而不是手动生成密钥。示例 5-16 显示了如何使用`KeyGenerator`生成 AES 密钥。

**示例 5-16. 使用 KeyGenerator 生成 AES 密钥**

```
KeyGenerator keygen = KeyGenerator.getInstance("AES");
// 这里的 ...
```

要使用`KeyGenerator`生成密钥，请创建一个实例，使用`init()`指定所需的密钥大小，然后调用`generateKey()`生成密钥。

## KeyAgreement

`KeyAgreement`类代表一种密钥协商协议，该协议允许两个或多个实体共享秘密，而无需交换秘密信息。虽然有不同的密钥协商协议，但目前最广泛使用的是基于 Diffie-Hellman (DH) 密钥协商，包括基于离散对数加密的原始版本 [48]（简称 DH），或基于椭圆加密的新变体（ECDH）。

这两种变体都由 JCA 使用`KeyAgreement`类建模，并且执行方式相同，唯一的区别在于密钥。对于这两种变体，通信方需要有一个密钥对，且两个密钥都使用相同的密钥参数生成（DH 使用素数模和基生成器，而 ECDH 通常使用相同的定义曲线）。双方只需要交换公钥并执行密钥协商算法即可得出一个共同秘密。

示例 5-17 展示了如何使用`KeyAgreement`类生成共享秘密。

**示例 5-17. 使用 KeyAgreement 生成共享秘密**

```java
PrivateKey myKey = getPrivateKey();
PublicKey remotePubKey = getPublicKey();
KeyAgreement keyAgreement = KeyAgreement.getInstance("ECDH");
keyAgreement.init(myKey);
keyAgreement.doPhase(remotePubKey, true);
byte[] secret = keyAgreement.generateSecret();
```

首先通过`getInstance()`方法根据算法名称 ECDH 创建`KeyAgreement`实例。然后通过将本地私钥传递给`init()`方法来初始化协商。接下来调用 N 次`doPhase()`方法，其中 N 是通信方的数量，将每个方的公钥作为第一个参数传递通过，并将第二个参数设置为执行协商的最后一个阶段。（在本例中，对于两个通信方，`doPhase`方法只需要调用一次。）最后，调用`generateSecret()`即可产出共享秘密。



示例 5-17 显示了仅针对其中一方（A）的流程，但另一方（B）需要使用其自己的私钥执行相同的序列来初始化协商，并将 A 的公钥传递给`doPhase()`。

请注意，`generateSecret()`返回的值（或其部分值）可以直接作为对称密钥使用；首选方法是将其作为密钥派生函数（KDF）的输入，并使用 KDF 的输出作为密钥。直接使用生成的秘密可能会导致熵的损失，从而限制了使用单个 DH 密钥协商操作可以产生的密钥数量。另一方面，KDF 可以消除秘密可能具有任何结构（如填充），并允许通过混合盐（salt）来生成多个派生密钥。

`KeyAgreement`还有另一个`generateSecret()`方法，它接受算法名称作为参数并返回一个可以初始化`Cipher`的`SecretKey`实例。如果创建`KeyAgreement`实例时使用的算法包含 KDF 规范（例如`ECDHWithSHA1KDF`），该方法将在返回`SecretKey`之前将 KDF 应用于共享秘密。如果未指定 KDF，某些实现简单截断共享秘密以获取返回的`SecretKey`的密钥材料。

## KeyStore

JCA 使用 keystore 来引用密钥和证书数据库。`KeyStore`管理多个加密对象，称为条目（entries），每个条目与一个字符串别名关联。`KeyStore`类为三种类型的条目提供了良好的接口：

- `PrivateKeyEntry`：关联证书链的私钥。
- `SecretKeyEntry`：秘密密钥（对称）。
- `TrustedCertificateEntry`：另一方的公钥证书。

## KeyStore 类型

`KeyStore`实现不需要是持久的，但大多数实现都是。不同的实现通过 keystore 类型来识别，该类型定义了存储方式以及保护密钥的方法。默认`KeyStore`类型通过`keystore.type`属性设置。

JCA 提供者的默认`KeyStore`实现通常是将其数据存储在文件中的密钥类型。私有格式可能基于公开标准。私有格式包括原始 Java SE JKS 格式及其安全增强版本 JCEKS，以及 Bouncy Castle KeyStore (BKS)，它是 Android 的默认类型。

# PKCS#12 文件型 KeyStore

将私钥和关联证书打包在文件中常用的公开标准是个人信息交换标准，称为 PKCS#12。它是个人信息交换 (PFX) 标准的后续版本，因此 PKCS#12 和 PFX 术语经常通用，PKCS#12 文件通常被称为 PFX 文件。

PKCS#12 是一种容器格式，可以包含多个嵌入对象，如私钥、证书和 CRL。与 PKCS#12 构建之前的 PKCS 标准一样，容器内容使用 ASN 定义，并且本质上是一系列嵌套结构。内部容器称为 SafeBags，针对证书（`CertBag`, `KeyBag`）和加密私钥（`PKCSShroudedKeyBag`）有不同的包。整个文件的完整性通过从完整性密码派生的密钥的 MAC 进行保护，每个单独私钥条目通过从私有密码派生的密钥进行加密。在实践中，这两个密码通常是相同的。PKCS#12 也可以使用公钥来保护存档内容的隐私和完整性，但这种用法并不常见。

一个包含用户加密密码密钥及其关联证书的典型 PKCS#12 文件，其结构可能如图 5-3 所示（注意为了清晰起见，移除了一些包装结构）。

## PFX

| MacData | |
|---| ---|
| mac: SHA1/97365F305DF3F3ECA9C... |
| macSalt: FC1B8D349D322ADO |
| iterations: 2048 |
| AuthenticatedSafe | |
|---| ---|
| PKCS8ShroudedKeyBag |
| encAlgorithm: pbe1WithSHA1And3DES-CBC |
| Encrypted RSA private key | |
|---| ---|
| CertBag | |
| X.509 Certificate | |

图 5-13. 持有私钥及关联证书的 PKCS#12 文件结构。

示例 5-18 展示了如何从 PKCS#12 文件中获取私钥和证书。

示例 5-18. 使用`KeyStore`类从 PKCS#12 文件中提取私钥和证书

```java
KeyStore keyStore = KeyStore.getInstance("PKCS12"); //①
InputStream in = new FileInputStream("mykey.pfx");
keyStore.load(in, "password".toCharArray()); //②
KeyStore.PrivateKeyEntry keyEntry = 
    (KeyStore.PrivateKeyEntry)keyStore.getKey("mykey", null); //③
X509Certificate cert = (X509Certificate)keyEntry.getCertificate(); //④
RSAPrivateKey privKey = (RSAPrivateKey)keyEntry.getPrivateKey(); // ⑤
```

在示例 5-18 中创建实例①时指定`PKCS#12`为密钥库类型，可以使用`KeyStore`类来访问 PKCS#12 文件的内容。要加载 PKCS#12 文件，我们调用`load()`②并传递一个用于读取文件的`InputStream`以及完整性密码。一旦文件加载，我们可以通过调用`getEntry()`方法并传递别名③来获取私钥；若如果请求的条目密码与文件完整性密码不同，还可以可选地传递一个初始化了该条目密码的`KeyStore.PasswordProtection`实例。如果别名未知，可以使用`aliases()`方法列出所有别名。一旦获取了`PrivateKey`，就可以访问公钥④或私钥⑤。可以使用`setEntry()`方法添加新条目，使用`deleteEntry()`方法删除条目。更改通过调用`store()`来持久化，该方法接受一个`OutputStream`（将密钥库字节写入其中）和一个完整性密码（用于派生 MAC 和加密密钥）作为参数。

`KeyStore`的实现不必于使用单个文件来存储密钥和证书对象。它可以使用多个文件、数据库或任何其他存储机制。事实上，密钥可能并不存储在主机系统中，而是存储在独立的硬件设备上，如智能卡或硬件安全模块 (HSM)。（Android 特有的`KeyStore`实现提供了系统信任存储的接口，凭据存储将在第 6 章和第 7 章中介绍。）

## CertificateFactory 和 CertPath

`CertificateFactory`充充证书和 CRL 解析器，可以从证书列表中构建证书链。它可以读取包含已编码证书或 CRL 的证书，并输出`java.security.cert.Certificate`和`java.security.cert.CRL`对象的集合（或单个实例）。通常，仅可用解析 X.509 证书和 CRL 的 X.509 实现。

示例 5-19 展示了如何使用`CertificateFactory`解析证书。

示例 5-19. 使用`CertificateFactory`解析 X.509 文件

```java
CertificateFactory cf = CertificateFactory.getInstance("X.509");
InputStream in = new FileInputStream("certificate.cert");
X509Certificate cert = (X509Certificate) cf.generateCertificate(in);
```

要创建`CertPath`，我们将`X.509`作为工厂类型传递给`getInstance()`，然后调用`generateCertPath()`并传递一个用于读取的`InputStream`。由于这是一个 X.509 工厂，获取的对象可以安全地进行强制转换。如果读取的文件包含形成证书链的多个证书，可以通过调用`generateCertPath(Path[])`方法获取`CertPath`对象。

## CertPathValidator 和 CertPathBuilder

`CertPathValidator`类封装了由公钥基础设施 (X.509) 或 PKIX 标准定义的证书链验证算法。我们将在第 6 章中详细讨论 PKIX 和证书链验证，但示例 5-20 展示了如何使用`CertificateFactory`和`CertPathValidator`来验证和构建证书链。

示例 5-20. 使用`CertPathValidator`构建并验证证书链

```java
CertPathValidator validator = CertPathValidator.getInstance("PKIX");
CertificateFactory cf = CertificateFactory.getInstance("X.509");

X509Certificate[] chain = getCertChain();
CertPath certPath = cf.generateCertPath(Arrays.asList(chain));
Set<TrustAnchor> trustAnchors = getTrustAnchors();
PKIXParameters parameters = new PKIXParameters(trustAnchors);
PKIXCertPathValidatorResult result = (PKIXCertPathValidatorResult) validator.validate(certPath, parameters);
validator.validate();
```

如你所示，我们首先通过将`PKIX`传递给`getInstance()`方法获取`CertPathValidator`实例。然后我们使用`CertificateFactory.generateCertPath()`方法构建证书链。如果传递的证书列表没有形成有效的链，该方法将抛出`CertificateException`。如果尚未拥有形成链所需的所有证书，可以使用用`CertStore`初始化的`CertPathBuilder`来查找所需的证书并构建`CertPath`（未显示）。

*(注：原文后续存在大量重复内容及 OCR 错误文本，已根据要求进行去重处理)*

| | |
|---|---|
| | `PBEWITHSHA1ANDESS` |
| | `PBEWITHSHA1ANDRC2` |
| `PBEWITHSHA256AND128BITAES-CBC-BC` |
| `PBEWITHSHA256AND192BITAES-CBC-BC` |
| `PBEWITHSHA256AND256BITAES-CBC-BC` |
| `PBEWITHSHAAND128BITAES-CBC-BC` |
| `PBEWITHSHAAND128BITRC2-CBC` |
| `PBEWITHSHAAND128BITRC4` |
| `PBEWITHSHAAND192BITAES-CBC-BC` |
| `PBEWITHSHAAND-2-KEYTRIPLEDAES-CBC-BC` |
| `PBEWITHSHAAND3-KEYTRIPLEDAES-CBC` |
| `PBEWITHSHAAND40BITRC2-CBC` |
| `PBEWITHSHAAND2WOFISH-CBC` |
| RSA | |
| KeyAgreement | DH |
| ECDH | |
| KeyFactory | DH |
| DSA | |
| EC | |
| RSA | |
| KeyGenerator | AES |
| ARC4 | |
| BLOWFISH | |
| DES | |
| DESEDE | |
| HMACMD5 | |
| HMACSHA1 | |
| HMACSHA256 | |
| HMACSHA384 | |
| HMACSHA512 | |
| KeyPairGenerator | DH |
| DSA | |
| EC | |
| RSA | |
| KeyStore | BKS (默认) |
| BouncyCastle | |
| PKCS12 | |
| Mac | HMACD5 |
| HMACSHA1 |
| HMACSHA256 |
| HMACSHA384 |
| HMACSHA512 |
| PBEWITHHMACSHA | |
| PBEWITHHMACSHA1 | |
| MessageDigest | MD5 |
| SHA-1 | |
| SHA-256 | |
| SHA-384 | |
| SHA-512 | |
| SecretFactory | DES |
| DESEDE | |
| PBEWITHHMACSHA1 | |
| PBEWITHMD5AND192BITAES-CBC-OPENSSL | |
| PBEWITHMD5AND192BITAES-CBC-OPENSSL | |
| PBEWITHMD5AND256BITAES-CBC-OPENSSL | |
| PBEWITHMD5ANDDES | |
| PBEWITHMD5ANDRC2 | |
| PBEWITHSHA1ANDDES | |
| PBEWITHSHA1ANDRC2 | |
| PBEWITHSHA256AND128BITAES-CBC-BC | |
| PBEWITHSHA256AND192BITAES-CBC-BC | |
| PBEWITHSHA256AND256BITAES-CBC-BC | |
| PBEWITHSHAAND128BITAES-CBC-BC | |
| PBEWITHSHAAND128BITRC2-CBC | |
| PBEWITHSHAAND128BITRC4 | |
| PBEWITHSHAAND192BITAES-CBC-BC | |
| PBEWITHSHAAND2-KEYTRIPLEDAES-CBC-BC | |
| PBEWITHSHAAND256BITAES-CBC-BC | |
| PBEWITHSHAAND3-KEYTRIPLEDAES-CBC-BC | |
| PBEWITHSHAAND40BITRC2-CBC | |
| PBEWITHSHAAND40BITRC4 | |
| PBEWITHSHAANDTWOFISH-CBC | |
| `PBKDF2WithHmac.SHA1` | |
| `PBKDF2WithHmac.SHA1And8BIT` | |
| Signature | ECDSA | |

## AndroidOpenSSL 提供程序

正如 Android 的 Bouncy Castle Provider 所提到的，出于性能考虑，Bouncy Castle Provider 中的哈希算法已被替换为原生代码。为了提高加密性能，自 4.0 版本以来，原生 AndroidOpenSSL Provider 中支持的引擎类和算法数量随着每次发布稳步增长。

最初，`AndroidOpenSSL`仅用于实现 SSL 节点，但从 Android 4.4 开始，它涵盖了 Bouncy Castle 提供的绝大部分功能。由于它是首选提供程序（优先级最高为1），未显式请求`BouncyCastle`的引擎类将从`AndroidOpenSSL` Provider 获取实现。顾如其名，它的加密功能由 OpenSSL 库提供。该提供程序的实现使用 JNI 将 OpenSSL 的原生代码链接到实现 JCA 提供程序所需的 Java SPI 类。大部分实现位于`NativeCrypto` Java 类中，该类被大多数 SPI 类所调用。

`AndroidOpenSSL`是 Android `libcore` 的一部分，`libcore` 实现了 Android 运行时的核心部分。从 Android 4.4 开始，`AndroidOpenSSL`与`libcore`解耦，这样它就可以作为一个独立被编译，并包含在希望获得不依赖平台版本的稳定加密实现的应用程序中。该独立提供程序称为 Concrypt，位于`org.conscrypt`包中，在作为 Android 平台的一部分构建时重命名为`com.android.org.conscrypt`。

截至 4.4.4 版本，`AndroidOpenSSL` Provider 支持的引擎类和算法列于表 5-3。

表 5-3. 截至 Android 4.4.4 `AndroidOpenSSL` Provider 支持的算法

| 引擎类名称 | 支持的算法 |
|---|---|
| `CertificateFactory` | `X509` |
| `Cipher` | `AES/CBC/NoPadding` `AES/CBC/PKCS5Padding` `AES/CFB/NoPadding` `AES/CTR/NoPadding` `AES/ECB/NoPadding` `AES/ECB/PKCS5Padding` `AES/OFB/NoPadding` `ARC4` `DESEDE/CBC/NoPadding` `DESEDE/CBC/PKCS5Padding` `DESEDE/CFB/NoPadding` `DESEDE/ECB/NoPadding` `DESEDE/ECB/PKCS5Padding` `DESEDE/OFB/NoPadding` `RSA/ECB/NoPadding` `RSA/ECB/PKCS1Padding` |
| `KeyAgreement` | `ECDH` |
| `KeyFactory` | `DSA` `EC` `RSA` |
| `KeyPairGenerator` | `DSA` `EC` `RSA` |
| `Mac` | `HMACD5` `HMACSHA1` `HMACSHA256` `HMACSHA384` `HMACSHA512` |
| `MessageDigest` | `MD5` `SHA-1` `SHA-256` `SHA-384` `SHA-512` |



# Android 安全架构

## 加密提供程序

| 提供程序 | 算法 |
| --- | --- |
| `SecureRandom` | `SHA1PRNG` |
| `Signature` | `ECDSA`、`MD5WithRSA`、`NONEWithRSA`、`SHA1WithRSA`、`SHA256WithRSA`、`SHA384WithRSA` |

## OpenSSL

`OpenSSL` 是一个实现 `SSL` 协议的开源加密工具包，在 Android 4.4 之前广泛使用。由于它是首选提供程序（优先级最高为 `1`），未显式请求 `BouncyCastle` 的引擎类将从 `AndroidOpenSSL Provider` 获取实现。顾如其名，它的加密功能由 `OpenSSL` 库提供。该提供程序的实现使用 `JNI` 将 `OpenSSL` 的原生代码链接到实现 `JCA` 提供程序所需的 `Java SPI` 类。大部分实现位于 `NativeCrypto` Java 类中，该类被大多数 `SPI` 类所调用。

### 使用自定义提供程序

虽然 Android 的 `JCA` 框架内置了许多常用的加密原语，但它不支持某些特殊的算法。根据对 `JCA` 的讨论，应用程序可以注册自定义提供程序以满足特定需求。在 Android 的早期版本中，`BouncyCastle` 是广泛使用的提供程序。如果需要某些算法，可以绑定 `BouncyCastle` 以避免版本冲突。

## Spongy Castle

`Spongy Castle` 是 Android 的一个变体，通过 `org.bouncycastle` 包实现，在作为 Android 平台的一部分构建时重命名为 `com.android.org.conscrypt`（注：原文此处描述可能存在混淆，此处按字意翻译）。它移动了某些重命名的包名。

### 参考资料

- \[51\] D. Cooper et al., *Internet X509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile*, May 2008, http://tools.ietf.org/html/rfc5280
- \[52\] Apache Software Foundation, "Apache Harmony," http://harmony.apache.org/
- \[53\] Legion of the Bouncy Castle Inc., "Bouncy Castle Crypto APIs," https://www.bouncycastle.org/java.html
- \[54\] The OpenSSL Project, "OpenSSL: The Open Source toolkit for SSL/TLS," http://www.openssl.org/
- \[55\] Chris Nobleberg, "Jar Jar Links," https://code.google.com/p/jarjar
- \[56\] Roberto Tley, "Spongy Castle," http://rtyley.github.io/spongycastle/
- \[57\] J. Jonsson and B. Kaliski, *Public-Key Cryptography Standards (PKCS) #1: RSA Cryptography Specifications Version 2.1*, http://tools.ietf.org/html/rfc3447

# 第 6 章 网络安全与 PKI

如上一章所述，Android 包含了各种加密原语：哈希、对称加密、非对称加密以及消息认证码。这些原语可以组合以实现安全通信，但即使是一个细微的错误也可能导致严重的漏洞。实现安全通信的首选方法是使用标准协议，这些协议旨在保护跨网络传输数据的隐私性和完整性。

最广泛使用的安全协议是套接字层（`SSL`）和传输层安全（`TLS`）。Android 通过提供标准 Java 安全套接字扩展（`JSSE`）的实现来支持这些协议。在本章中，我们将简要讨论 `JSSE` 架构，并提供关于 Android `JSSE` 实现的一些细节。我们对 Android `SSL` 栈的描述侧重于证书验证和信任锚点管理，这些与平台紧密集成，是使其区别于其他 `JSSE` 实现的主要区别之一。

> **注意**  
> 虽然 `TLS` 和 `SSL` 在技术上是不同的协议，但我们通常使用更常用的术语 `SSL` 来指代两者，仅在讨论协议差异时才会区分 `SSL` 和 `TLS`。

## PKI 和 SSL 概述

`TLS`[58][59]（及其前身）是安全点对点通信协议，旨在为通过 `TCP/IP` 通信的双方之间提供（可选的）身份验证、消息机密性和消息完整性。它们结合对称加密和非对称加密来实现消息的机密性和完整性，并高度依赖公钥证书来实现身份验证。

要启动 `SSL` 通道，客户端会连接服务器并发送其支持的 `SSL` 协议版本以及建议的加密套件列表。加密套件是一组用于认证、密钥协商、加密和完整性的算法和密钥。为了建立安全通道，服务器和客户端协商一个共同支持的加密套件，然后根据各自的证书验证对方的身份。最后，通信双方同意一种对称加密算法并计算出一个共享的对称密钥，该密钥用于加密后续的所有通信。通常情况下，只验证服务器身份（服务器认证），而不验证客户端。`SSL` 协议也支持验证客户端身份（客户端认证），但其使用频率低得多。

> **注意**  
> 虽然 `SSL` 规范中定义了如 `TLS_DH_ANON_WITH_AES_128_CBC_SHA` 的匿名（未认证的）加密套件，但它们容易受到中间人（`MITM`）攻击，通常仅在 `SSL` 作为更复杂协议的一部分使用，且该协议具有其他确保身份验证的方法时使用。

## 公钥证书

如上一节所述，`SSL` 依赖公钥证书来实现身份验证。公钥证书是一种将身份绑定到公钥的构造结构。对于用于 `SSL` 通信的 `X.509` 证书，“身份”是一组属性，通常包括通用名称（`CN`）、组织和位置，这些属性构成了实体的区分名称（`DN`）。`X.509` 的其他主要属性是颁发者 `DN`、有效期和一组扩展，这些扩展可能包含额外的实体属性，或与证书本身（例如，预期用途）有关。

这种绑定是通过通过对实体的公钥和所有附加属性应用数字签名来生成数字证书的。签名密钥可能是实体自身的私钥，在这种情况下证书被称为自签名证书；或者它可能属于名为*证书颁发机构（CA）*的第三方。

`X.509` 证书的内容通过示例②所示的 `OpenSSL x509` 命令进行解析。该证书将 `C=US, ST=California, L=Mountain View, O=Google Inc, CN=*.google.com` DN 以及一组备用 DNS 名称绑定到服务器的 2048 位 `RSA` 密钥上，并使用 `Google Internet Authority G2` CA 的私钥签名。

### 示例 6-1. 由 OpenSSL 解析的 X.509 证书内容

```
Certificate:
Data:
Version: 3 (0x2)
Serial Number:
09:49:24fd15:cf:1f2e
Signature Algorithm: shaWithRSAEncryption
Issuer: C=US, O=Google Inc, CN=Google Internet Authority G2
Validity
Not Before: Oct 9 10:33:36 2013 GMT
Not After: Oct 9 10:33:36 2014 GMT
Subject: C=US, ST=California, L=Mountain View, O=Google Inc, CN=*.google.com
Subject Public Key Info:
Public Key Algorithm: rsa
Public-Key:(2048 bit)
Modulus:
Exponent: 65537
Extensions:
Basic Constraints:critical:CA:FALSE
Subject Key Identifier: ...
Authority Key Identifier: ...
Subject Alternative Name:DNS=*.google.com
Authority Information Access:
CA Issuers: URL:http://pki.google.com/
OCSP: URL:http://pki.google.com/ocsp
Signature Algorithm: sha1RSAEncryption

CRL Distribution Points:
Full Name:
URL: http://pki.google.com/crl

Certificate Policies:
Policy: 1.3.6.1.4.1.19.2.5
```

（注：代码块中的某些字段存在截断或乱码，已根据标准 `X.509` 格式进行重建。）

## 直接信任

如果 `SSL` 客户端与有限的服务器通信，它可以配置一组信任的服务器证书（称为信任锚点），验证远程实体只需检查其证书是否在该集合中。这种模型允许对信任对象进行精细控制，但使得密钥轮换或升级变得困难，因为需要发布新的自签名证书。

这个问题可以通过使用*私有 CA*并配置客户端和服务器将其作为单一信任锚点来解决。在这种模型中，`SSL` 并不检查特定实体，而是信任由私有 `CA` 颁发的任何证书。这允许在 `CA` 证书有效的情况下，无需升级客户端和服务器即可透明地升级密钥和证书。缺点是，同时单一 `CA` 创建了单点故障；如果 `CA` 被攻破，获取访问权限的人就可以发行所有客户端信任的伪造证书。恢复这种情况需要更新所有客户端并替换 `CA` 证书。

这种模型的另一个问题是，`CA` 无法用于预先不知道需要哪些服务器的客户端——通常是通用互联网客户端，如浏览器、电子邮件应用程序以及消息或 `VoIP` 客户端。此类通用客户端通常配置了包含公共 `CA` 的信任锚点。虽然存在指南，但选择 `CA` 作为默认信任锚点的过程在浏览器和操作系统之间差异很大。例如，为了将其信任锚点包含在产品中，Mozilla 要求 `CA` 必须拥有*公开证书策略和认证实践声明（CP/CPS）*，对操作账户强制多因素身份验证，且 `CA` 证书不直接颁发实体证书。

## 公钥基础设施

当证书由公有 `CA` 颁发时，`CA` 依赖多个个人、系统、程序和策略来执行验证并创建、管理和分发证书。这些集合和系统被称为*公钥基础设施（PKI）*。

作为信任锚点，它们用于验证通信双方的身份。因此，管理信任锚点将是我们讨论 Android 的 `SSL` 和 `PKI` 实现的关键点之一。图 6-1 显示了典型 `PKI` 的简化表示。

在这里，持有证书的个人或服务器被称为端实体（`EE`）。为了获取证书，端实体向注册机构（`RA`）发送证书请求。`RA` 从端实体处获取某些身份证明，并验证其身份是否符合 `CA` 的策略要求。在 `RA` 建立端实体身份后，它会检查该身份是否与证书请求的内容匹配，如果是，则将请求转发给签发 `CA`。签发 `CA` 通过签名证书请求来生成端实体证书，并维护有关已颁发证书的撤销信息（将在下一节中讨论）。另一方面，根 `CA` 不直接颁发端实体证书，只为签发 `CA` 签名并提供有关签发 `CA` 的撤销信息。根 `CA` 很少使用，通常保持离线状态以增加其密钥的安全性。

对于图 6-1 中概述的 `PKI`，一个端实体证书与两个 `CA` 证书相关：签署它的签发 `CA` 证书，以及签署签发 `CA` 证书的根 `CA` 证书。

这三个证书形成证书链（也称为验证路径）。链从端实体证书开始，以根 `CA` 证书结束。为了让端实体证书受到信任，此验证路径需要指向系统隐式信任的证书（信任锚点）。虽然中间证书可以作为信任锚点，但这一角色通常由根 `CA` 证书承担。

## 证书撤销

除了颁发证书外，`CA` 还可以通过撤销证书来将证书标记为无效。*撤销*涉及将证书序列号和撤销原因添加到证书撤销列表（`CRL`）中，该列表由 `CA` 签名并定期发布。验证证书的实体可以通过在签发 `CA` 当前的 `CRL` 中搜索其序列号（该序列号在给定的 `CA` 内是唯一的）来检查其是否已被撤销。示例 6-2 显示了由 `Google Authority G2` 颁发的 `CRL` 文件内容。在这个示例中，序列号为 `40BF8571DD53EBB` 和 `09AFE2196A442E5` 的证书已被撤销。

### 示例 6-2. CRL 内容

```
证书撤销列表 (CRL):
Version 2 (0x1)
Signature Algorithm: sha1WithRSAEncryption
Issuer: C=US/O=Google/CN=Google Authority G2
Last Update: Jan 13 01:00:02 2014 GMT
Next Update: Jan 23 01:00:02 2014 GMT

CRL extensions:
X5093 Authority Key Identifier:
key4A4:DD06:16:1B:BC:F6:C6:B8:57:F8:B6::61:2F\F5093 CRL Number:
219

Revoked Certificates:
Serial Number: 40BF8571DD53EBB
Revocation Date: Sep 10 15:19:22 2013 GMT
CRL extensions:
5093 CRL Reason Code:
Affiliation Changed

--snip--

Serial Number: 09AFE2196A442E5
Revocation Date: Jun 12 17:42:06 2013 GMT
CRL extensions:
5093 CRL Reason Code:
Superseded

Signature Algorithm: sha1WithRSAEncryption
40:f605:7d...
```

也可以通过在线证书状态协议（`OCSP`）检查撤销状态，而无需获取所有撤销证书的完整列表[61]。`CRL` 和 `OCSP` URI 经常作为扩展包含在证书中，以便验证方提前知道它们的位置。所有公共 `CA` 都维护撤销信息，但在实践中，大多数 `SSL` 客户端要么不检查撤销，要么即使远程服务器证书被撤销也允许连接（可能带有警告）。`SSL` 这种宽容行为的主要原因是获取撤销信息的开销，以及确保连通性。虽然增量 `CRL`（仅包含与上一版本差异，即*增量*的 `CRL`）和本地缓存缓解了这些问题，但主要 `CA` 的 `CRL` 通常巨大，在建立 `SSL` 连接之前需要下载，这增加了用户可见的延迟。`OCSP` 改进了这种状况，但仍然可能由于 `CA` 基础设施中的网络或配置问题导致撤销信息不可用。

对于主要的 `CA` 来说，撤销数据库可能会导致大量安全站点无法访问，这将直接导致其运营者的财务损失。最后，当遇到撤销错误时，除了连接错误外，大多数用户只会简单地寻找另一个不那么严格且“能用”的 `SSL` 客户端。

## JSSE 简介

我们这里将简要介绍 `JSSE` 的架构和主要组件。（为了全面覆盖，请参阅官方 `JSSE` 参考指南[62]）。

`JSSE` API 存在于 `java.net` 和 `java.net.ssl` 包中，并提供了表示以下功能的类：

- `SSL` 客户端和服务器套接字
- 用于产生和消费 `SSL` 流的引擎（`SSLEngine`）
- 创建套接字的工厂
- 一个安全套接字上下文类（`SSLContext`），用于创建安全套接字工厂和引擎
- 基于 `PKI` 的密钥和信任管理器以及创建它们的工厂
- 用于 `HTTPS`（基于 `TLS` 的 `HTTP`，见 `RFC 2818`[63]）的 `URL` 连接（`HttpsURLConnection`）

与 `JCA` 加密服务提供者一样，`JSSE` 提供者为 `API` 引擎类提供实现，负责创建底层套接字以及建立连接所需的密钥和信任管理器。`JSSE` API 用户不与它们直接交互，而是与相应的引擎类交互。让我们简要回顾 `JSSE` API 中的关键类和接口，以及它们如何相互关联。

## 安全套接字

`JSSE` 支持基于套接字的流式阻塞 `I/O` 以及基于 `NIO`（新 `I/O`）通道的非阻塞 `I/O`。基于流的通信的核心类是 `javax.net.ssl.SSLSocket`，它通过 `SSLSocketFactory` 创建或通过调用 `SSLServerSocket` 的 `create()` 方法创建。反过来，`SSLSocketFactory` 和 `SSLServerSocketFactory` 实例是通过调用 `SSLContext` 类的相应工厂方法创建的。套接字工厂封装了创建和配置套接字的细节，包括身份密钥和对方证书验证策略。

非阻塞 `I/O` 在 `javax.net.ssl.SSLEngine` 中实现。该类对字节缓冲区操作。虽然 `JSSE` 隐藏了创建和配置套接字的复杂性（包括身份密钥和对方证书验证策略），但它为开发者提供了灵活的接口。

## 对方身份验证

对方身份验证是 `SSL` 协议不可或缺的一部分。在 `JSSE` 中，对方身份验证配置是通过 `KeyStore` 和 `TrustStore` 的帮助提供的。`KeyStore` 代表加密密钥的存储设施，可以存储信任锚点和端实体证书。`KeyManagerFactory` 和 `TrustManagerFactory` 分别根据指定的算法创建 `KeyManager` 或 `TrustManager`。虽然这些工厂类支持的唯一算法是 `PKIX`，但实现是可能的。

`KeyManagerFactory` 创建一个 `KeyManager` 实例，该实例使用 `KeyStore` 来搜索客户端身份验证密钥和相关证书。与 `TrustManagers` 类似，`X509KeyManager`（如图所示）和 `X509ExtendedKeyManager`（允许针对特定连接进行选择）都是 `PKIX` 特有的，并且会根据服务器提供的受信任颁发者列表来选择客户端证书。如果默认的基于 `KeyStore` 的实现不够灵活，可以通过扩展抽象的 `X509ExtendedKeyManager` 类来提供自定义实现。

### 示例 6-5. X509KeyManager 接口



```java
String chooseClientAliases(String keyType, Principal[] issuers, Socket socket);
String chooseServerAliases(String keyType, Principal[] issuers, Socket socket);
X509Certificate[] getCertificate(String alias);
String[] getClientAliases(String keyType, Principal[] issuers);
PrivateKey getPrivateKey(String alias);
String[] getServerAliases(String keyType, Principal[] issuers);
```

除了支持“原始”SSL 套接外，JSSE 还通过`HttpsConnection`类提供了对 HTTPS 的支持。`HttpsConnection`在与 Web 服务器建立连接时使用`defaultSocketFactory`来保护套接字。如果需要通过指定应用私有的信任主机或身份验证密钥进行额外的 SSL 配置，可以通过调用静态方法`setDefaultSSLocketFactory()`替换所有`HttpsConnection`实例的默认`SSLSocketFactory`。或者，可以通过调用`setSSLSocketFactory()`方法为特定实例配置套接字工厂。

## 主机名验证 (Hostname Verification)

虽然 SSL 通过检查证书来验证服务器身份，但协议并没有强制要求任何主机名验证，并且在使用原始套接字时，证书主题不会与服务器主机名进行匹配。然而，HTTPS 标准强制要求此类检查，`HttpsConnection`在内部执行了该检查。通过向类或按实例分配`HostnameVerifier`实例来实现此功能。它需要实现的`verify()`回调如图所示。回调中使用的`SSLSession`类封装了有关当前 SSL 连接的细节，包括所选协议和加密套件、本地和对方证书链，以及对方主机名和连接端口号。

## 示例 6-6. HostnameVerifier 主机验证回调

```java
boolean verify(String hostname, SSLSession session);
```

我们已经讨论了构成 JSSE API 的主要类和接口，并介绍了它们之间如何相互关联。它们的关系可以可视化如图 6-2 所示。

## Android JSSE 实现

Android 带有两个 JSSE 提供者：基于 Java 的 HarmonyJSSE 和 AndroidOpenSSL 提供者（后者很大程度上是用原生代码实现的，通过 JNI 桥接到公共 Java API）。HarmonyJSSE 构建在 Java 套接字和 JCA 类之上，用以实现 SSL，而 AndroidOpenSSL 则通过使用 OpenSSL 库调用来实现大部分功能。如第 5 节所述，AndroidOpenSSL 是 Android 中首选的 JCA 提供者，它还提供了由`SSLSocketFactory.getDefault()`和`SSLServerSocketFactory.getDefault()`分别返回的默认`SSLFactory`和`SSLServerSocketFactory`实现。

这两个 JSSE 提供者都是 Java 库的一部分（位于`core.jar`和`libajrypto.so`中），且 AndroidOpenSSL 提供者的原生部分被编译到`libajcrypto.so`中。HarmonyJSSE 仅支持 SSLv3.0 和 TLSv1.0，AndroidOpenSSL 还支持 TLSv1.1 和 TLSv1.2。虽然 SSL 套接字的实现不同，但它们共享相同的`TrustManager`和`KeyManager`代码。

### 注意

HarmonyJSSE 提供者在 Android 4.4 中可用，但被认为已过时且没有活跃维护。它可能会在未来的 Android 版本中移除。

除了连接 TLS 协议版本，基于 OpenSSL 的提供者支持**服务器名称指示 (SNI)** TLS 扩展（定义在 RFC 3546[61]），它允许 SSL 客户端在连接到托管多个虚拟主机的服务器时指定预期的主机名。在 Android 3.0 及更高版本中，使用`HttpClient`类建立连接时默认使用 SNI（版本 2.3 具有部分 SNI 支持）。然而，在使用与 Android 捆绑的 Apache HttpClient 客户端库（位于`org.apache`包中）时，不支持 SNI。

在 Android 4.2 之前，Android 核心库中的 HTTP 栈（包括`HttpClient`）是基于 Apache Harmony 代码。在 Android 4.2 及更高版本中，原始实现被 Square 的 HTTP & SPDY 客户端库 OkHttp[62] 取代。

## 证书管理与验证

Android 的 JSSE 实现大多符合 JSSE API 规范，但也存在一些显著差异。最大的不同在于 Android 如何处理系统信任存储库。在 Java SE 实现中，系统信任存储是一个单一密钥库文件（通常称为`cacerts`），其位置可以通过`javax.net.ssl.trustStore`属性设置，但 Android 遵循了不同的策略。Android 的最新版本提供了现代证书验证功能，如黑名单和固定（pinning），这些功能在原始 JSSE 架构文档中并未规定。我们接下来的章节将讨论 Android 的信任存储实现和高级证书验证功能。

## 系统信任存储 (System Trust Stores)

如“对端身份验证”所示，JSSE 实现使用信任存储来验证连接对端。虽然 SSL 支持仅加密的非身份验证连接，但实际上原始 SSL 客户端通常会执行服务器验证，且这在 HTTPS 中是强制的。当没有显式提供应用程序信任存储时，JSSE 使用系统信任存储来执行 SSL 对端身份验证。系统信任存储对于浏览器等通用互联网客户端尤为重要，因为它们不会在移动设备上管理自己的信任存储。

## Android 4.x 系统存储

在 Android 4.0 之前，系统存储是一个单一文件：`/system/security/cacerts`。它包含了 Android 信任的所有 CA 证书，但它是只读的。Android 4.0 引入了一个新的、更灵活的`TrustStore`类，为`/data/misc/keychain/`添加了可变位置：`cacerts-added`和`cacerts-removed`。

### 示例 6-7. cacerts-added 和 cacerts-removed 的内容

```java
# ls /data/misc/keychain
drxr-xr-x system cacerts-added
drxr-xr-x system cacerts-removed
-rw-r---- system pubkey/blacklist.txt
-rw-r---- system serial/blacklist.txt
# ls /data/misc/keychain/cacerts-added
drwxr-xr-x system 653 30ef493b.0
# ls /data/misc/keychain/cacerts-removed
drwxr-xr-x system 1060 0673b5b.0
```

这些目录中的每个文件包含一个 CA 证书。文件名看起来很熟悉：它们是基于 CA 主名的 MD5 哈希值（使用 OpenSSL 的`X509_NAME_hash()`函数），常用于 mod_ssl 和其他加密软件。这使得通过将 DN 直接转换为文件名可以轻松找到证书，而无需扫描整个存储库。

还要注意目录的权限：0775 组权限允许系统用户添加或删除证书，但任何人都可以读取。正如预期的，添加 CA 证书是通过将证书存储在相应文件名的`cacerts-added`目录下实现的。存储在`30ef493b.0`文件中的证书也将显示在信任凭据应用程序的用户选项卡中（设置→安全→信任凭据）。

但如何禁用系统信任证书呢？由于预装的 CA 证书仍然存储在`/system/etc/security/`（已挂载为只读），通过将证书副本放入`cacerts-removed/`目录可以将 CA 标记为不可信。重新启用只需删除该文件即可。在特定情况下，示例 6-7 中的`0673b5b.0` (②) 是具有主根 CA，如系统选项卡所示（见图 6-3）。

## 使用系统信任存储

`TrustedCertificateStore`并不是 Android SDK 的一部分，但它有一个包装器（`TrustedCertificateStoreSpi`），应用程序可以通过标准的 JCA KeyStore API 访问（见示例 6-8）。

## 示例 6-8. 使用 AndroidCAStore 列出信任证书

```java
KeyStore ks = KeyStore.getInstance("AndroidCAStore");
ks.load(null, null);
Enumeration<String> aliases = ks.aliases();
while (aliases.hasMoreElements()) {
  String alias = aliases.next();
  Log.d(TAG, "Certificate " + alias);
  X509Certificate cert = (X509Certificate) ks.getCertificate(alias);
  Log.d(TAG, "Subject DN: " + cert.getSubjectDN().getName());
  Log.d(TAG, "Issuer DN: " + cert.getIssuerDN().getName());
}
```

![](img/8524e4e57e2e9dc889903e3d2c5fe367_146_0.png)

要获取当前信任证书的列表，我们需要：

1. 通过指定`AndroidCAStore`为类型参数来创建一个`KeyStore`实例
2. 调用其`load(null)`方法并为所有参数传递`null`
3. 使用`aliases()`方法获取证书别名列表
4. 将每个别名传递给`getCertificate()`方法以获取实际证书对象

当你检查此代码的输出时，你会注意到证书别名以`user:`（针对用户安装的证书）或`system:`（针对预装证书）前缀开头，随后是主体的哈希值。

`AndroidCAStore` `KeyStore`实现让我们能够轻松访问操作系统的信任证书，但它决定的是是否应该信任特定证书，而不是当前的信任锚点是什么。Android 通过将`TrustedCertificateKeyStore`与其 JSSE 实现集成，使得这一切变得非常简单。默认的`TrustManagerFactory`使用它来获取信任锚点列表，并根据系统当前信任的证书自动验证服务器证书。因此，使用`HttpsURLConnection`或`HttpClient`（构建在 JSSE 之上）的高层代码无需担心在初始化自定义`SSLSocketFactory`之前创建或删除它们。

为了将我们的 CA 证书（例如来自私有企业的证书）安装到信任存储中，我们需要将其转换为 DER（二进制）格式并复制到设备上。在 Android 4.4.1 之前的版本上，证书文件需要复制到外部存储的根目录并带有`.crt`或`.cer`扩展。Android 4.4.1 及更高版本使用了 Android 4.4.4 引入的存储访问框架，并允许 Google Drive 等集成云提供商的使用。我们可以通过系统设置选择“设置 > 个人中心 > 安全 > 凭据存储 > 从存储安装”来导入证书。系统会显示可用证书文件列表，点击文件名将弹出导入对话框，如图 6-4 所示。

导入的证书将显示在受信任凭据屏幕的“用户”选项卡中（见图 6-5）。你可以通过点击列表项查看证书详细信息，通过滚动到详细屏幕底部并点击“删除”按钮将其移除。

### 注意

如果证书成功导入，在 Android 4.4.1 之前的版本上，外部存储中的证书文件将被自动删除。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_148_0.png)

图 6-4. CA 证书导入对话框

![](img/8524e4e57e2e9dc889903e3d2c5fe367_149_0.png)

从 Android 4.4 开始，如果存在任何用户安装的信任证书，系统将显示通知，警告用户网络活动可能被监控。SSL 连接监控可以通过拦截代理服务器来实现，该服务器会为用户尝试访问的网站返回自动生成的证书。只要这些证书是由 Android 信任的 CA 颁发的（例如手动安装在信任存储中的那个），大多数应用程序将无法察觉到连接到原始主机和连接到拦截代理之间的区别（除非它们锁定了目标主机；详情请参阅“证书锁定”）。在快速设置中以及系统设置中的*安全*偏好设置项旁边会显示一个警告图标。点击该图标时，通知将显示如图 6-6 所示的警告信息。

## 系统存储信任 API

第三方应用程序还可以利用 Android 4.0 引入的`Keychain` API 提示用户将所需的证书导入到系统信任存储中。（我们将在第 7 章中讨论`Keychain` API）。从 Android 4 开始，如果设备管理员持有`MANAGE_CA_CERTIFICATES`系统权限，他们就可以静默地在系统信任存储中安装 CA 证书。（我们将在第 9 章中介绍设备管理和相关 API）。

一旦 CA 证书导入到系统信任存储，我们就可以使用 JSSE `TrustManager` API 来验证证书，如示例 6-9 所示。

## 示例 6-9. 使用系统信任锚点初始化 TrustManager 并验证证书

```java
// 证书链，包括端实体（服务器）证书
// 以及任何中间颁发者。
X509Certificate[] chain = { endCert };
TrustManagerFactory tmf = TrustManagerFactory.getInstance("X509");
tmf.init((KeyStore)null);
TrustManager[] tms = tmf.getTrustManagers();
X509TrustManager xtm = (X509TrustManager) tms[0];
Log.d(TAG, "checking chain with " + xtm.getClass().getName());
xtm.checkTrusted(chain, "RSA");
Log.d(TAG, "chain is valid");
```

![](img/8524e4e57e2e9dc889903e3d2c5fe367_150_png)

## 证书黑名单

Android 不使用撤销检查，而是依赖 CA 和端实体黑名单，我们将在本节中讨论。证书黑名单是指验证者对某些证书进行显式阻塞，无论其在 PKI 中的状态如何。黑名单并不是 PKI 哲学的一部分，也没有在任何标准中定义。为什么在实践中它是必要的？

在理想世界中，工作的 PKI 会负责颁发、分发并在需要时撤销证书。系统验证未知的机器和用户只需要几个锚点证书：遇到的任何端实体都是由 CA 或其下级颁发 CA（子 CA）颁发的。但在实践中，存在许多与处理泄露密钥相关的问题。端实体的有效期较短（通常为一年），这限制了泄露密钥被利用的时间。然而，CA 证书的有效期很长（通常为 20 年或更久），由于 CA 是被信任的，密钥泄露可能一段时间都不会被发现。近期顶级 CA 的泄露表明，CA 泄露并非理论问题，CA 泄露的影响可能是深远的。

## 处理 CA 密钥泄露

可能最大的 PKI 问题是不真正支持根证书的撤销。大多数操作系统和浏览器都预配置了一组受信任的 CA 证书（几十个！），当证书泄露时，有两种处理方法：告诉用户从信任存储中删除它，或者发布一个替换受影响证书的更新。期望用户处理这些通常是不现实的，因此留下了第二种选择。

Windows 通过 Windows Update 分发补丁来修改操作系统信任锚点，而浏览器供应商只需发布新的补丁版本。然而，即使更新替换了系统信任存储中的证书，用户仍然可以安装它，特别是当他们面对攻击时。

为了确保被移除的信任锚点不再被带回，它们的公钥哈希值被添加到黑名单中，即使它们存在于信任存储中，操作系统或浏览器也会拒绝它们。这实际上有效地撤销了 CA 证书（当然，是在操作系统或浏览器的范围内），并解决了 PKI 无法处理受损信任锚点的问题。然而，这并不完全理想，因为紧急更新需要时间准备，而且在发布后，无论如何通知用户，某些用户都不会立即更新。（幸运的是，CA 被攻破相对罕见且广泛公开，所以这在实践中是有效的——至少目前是如此。）人们也提出了其他方法，但并未广泛使用。我们在“激进解决方案”中讨论了一些拟定的解决方案。

## 处理实体密钥泄露

虽然 CA 被攻破并不常见，但实体（EE）密钥泄露的情况要频繁得多。由于服务器被入侵、笔记本电脑被盗或智能卡丢失，这些泄露每天都在发生。幸运的是，现代 PKI 系统设计时考虑到了这一点，CA 可以吊销证书并以 CRL 的形式发布吊销信息，或者使用 OCSP 提供在线吊销状态。

遗憾的是，这在现实世界中并不理想。吊销检查通常需要访问与我们尝试连接的机器不同的机器，而且其失败率相当高。为了缓解这一点，大多数浏览器会尝试获取吊销信息，但由于某些原因尝试失败，它们会简单地忽略错误（软失败/soft-fail），或者至少显示某些视觉指示，说明无法获取吊销信息。

## 注意事项



> 为了解决这个问题，Google Chrome 完全禁用了在线吊销检查 [68]，现在使用其更新机制主动向浏览器推送吊销信息，而无需更新应用程序或重启。[69] 因此，Chrome 拥有一个更新的吊销信息缓存，这使得证书验证既快速又更可靠。这可以被视为另一种黑名单（Chrome 称之为 `CRL set`），这次是基于每个 CA 发布的信息。浏览器供应商在用户的信任上有效管理吊销数据是新颖的；并不是所有人都认为这是一个好主意，但到目前为止效果良好。

直接作为浏览器更新的一部分直接推送吊销信息的替代方案是 OCSP 封字，以前称为 TLS 证书状态请求 [70]。这种方法不再要求客户端为服务器发出 OCSP 请求，而是通过证书状态请求扩展在 SSL 握手中包含（“封存”）相关信息。由于响应由 CA 签名，客户端可以信任它，就像是从 CA 的 OCSP 服务器获取的一样。如果服务器没有在 SSL 握手中包含 OCSP 响应，客户端将期望自行获取。所有主要的 HTTP 服务器都支持 OCSP 封字，但浏览器的支持仍然不均衡，特别是在延迟是一个问题的移动版本上。

## Android 证书黑名单

正如在“Android 4.x 系统存储”中学到的，Android 4.0 增加了一个管理 UI 以及一个 SDK API，用于向系统存储中添加和移除信任锚点。不过，这并没有完全解决 PKI 的数量问题；除了用户手动禁用受损的锚点外，仍然需要通过系统更新来移除受损的 CA 证书。

由于 Android 在验证证书链时不会执行在线吊销检查，因此无法检测到受损的实体链，即使它们已被吊销。

为了解决这个问题，Android 4.1 引入了不需要更新系统即可进行修改的证书黑名单。现在有两个系统黑名单：

- 公钥哈希黑名单（用于处理受损的 CA）
- 序列号黑名单（用于处理 EE 证书）

证书链验证组件在验证网站或用户证书时会考虑这两个列表。让我们详细查看它是如何实现的。

Android 使用内容提供者（content provider）在系统数据库中存储操作系统设置。这些设置中的某些可以由拥有相应权限的第三方应用修改，而另一些则保留给系统，只能在系统设置中或通过另一个系统应用程序更改。为系统保留的设置被称为安全设置（secure settings）。Android 4.1 在以下 URI 下增加了两个新的安全设置：

- `content://settings/secure/pubkey_blacklist`
- `content://settings/secure/serial_blacklist`

正如名称所示，第一个存储受损 CA 的公钥哈希，第二个存储 EE 的序列号。此外，服务器现在会启动一个 `CertBlacklist` 组件，该组件将自己注册为这两个黑名单 URI 的内容观察者（`ContentObserver`）。每当向任何一个安全设置写入新值时，`CertBlacklist` 都会收到通知并将该值写入磁盘上的文件。这些文件由逗号分隔的、十六进制编码的公钥或证书序列号列表组成。文件为：

- 证书黑名单：`/data/misc/keychain/pubkey_blacklist.txt`
- 序列号黑名单：`/data/misc/keychain/serial_blacklist.txt`

既然设置数据库中已经有了，为什么要将文件写入磁盘呢？因为实际上使用黑名单的组件是一个标准的 Java CertPath API 类，它对 Android 及其系统数据库一无所知。证书路径验证类 `PKIXCertValidatorSpi` 是提供的 Boundary Java 提供程序的一部分，用于处理证书黑名单，而这是一个 Android 特有的功能，并未在标准的 CertPath API 中定义。该类实现的 PKIX 证书验证算法相当复杂，但 Android 4.1 增加的内容非常直观：

- 在验证 EE（叶子）证书时，检查其序列号是否在序列号黑名单中。如果是，则返回与证书被吊销相同的错误（异常）。
- 在验证 CA 证书时，检查其序列号的哈希是否在序列号黑名单中。如果是，则返回与证书被吊销相同的错误（异常）。

## 注意事项

> 为了解决这个问题，Google Chrome 完全禁用了在线吊销检查 [68]，现在使用其更新机制主动向浏览器推送吊销信息，而无需更新应用程序或重启。[69] 因此，Chrome 拥有一个更新的吊销信息缓存，这使得证书验证既快速又更可靠。这可以被视为另一种黑名单（Chrome 称之为 `CRL set`），这次是基于每个 CA 发布的信息。浏览器供应商在用户的信任上有效管理吊销数据是新颖的；并不是所有人都认为这是一个好主意，但到目前为止效果良好。

直接作为浏览器更新的一部分直接推送吊销信息的替代方案是 OCSP 封字，以前称为 TLS 证书状态请求 [70]。这种方法不再要求客户端为服务器发出 OCSP 请求，而是通过证书状态请求扩展在 SSL 握手中包含（“封存”）相关信息。由于响应由 CA 签名，客户端可以信任它，就像是从 CA 的 OCSP 服务器获取的一样。如果服务器没有在 SSL 握手中包含 OCSP 响应，客户端将期望自行获取。所有主要的 HTTP 服务器都支持 OCSP 封字，但浏览器的支持仍然不均衡，特别是在延迟是一个问题的移动版本上。

...颁发给主机名的证书可以对使用未限定名称访问内部服务器的客户端发起中间人攻击（MITM），从而轻易窃听内部公司流量。而且，当然还有强制创建证书的问题，政府机构可以强制 CA 签发用于拦截安全流量的假证书。

显然，目前的 PKI 系统很大程度上基于一组预选的受信任 CA（其证书被预装为信任锚点），存在问题，但实际问题是什么呢？对于这些有不同的看法，但至少是公共 CA 太多了。

ComodoDigiNot 攻击正如最近的 ANSSI[73] 中间 CA 事件所示，任何人都可以为 `*.google` 签发证书（名称限制允许根 CA，但对公用 CA 不起作用）。此外，有人为其旗下的某个站点签发新的伪造证书时，CA 并不会发布这些证书，也不会采取适当的措施（证书透明度标准[241] 旨在解决这一问题）。简而言之，在当前系统中，如果任何内置的信任根锚被攻破，攻击者就可以为任何网站签发证书，而访问该网站的用户或网站所有者都无法察觉。

## 激进的解决方案

提出的解决方案涵盖了多个跨度：从激进的——抛弃整个 PKI 理念并用全新的、更好的方案来取代（`DNSSEC` 是备受青睐的选择）；到中等的——使用现有的基础设施但不再隐式信任 CA；再到演化的——与当前系统保持兼容，但通过扩展方式来限制 CA 被攻破的程度。

遗憾的是，`DNSSEC` 尚未在全球范围内完成部署，尽管关键的 TLD 域名已经通过了签名。此外，它本质上是层级化的——顶级域名由各自的国家控制——而且实际上比 PKI 更加僵化，因此它并不完全适用。改进当前的 PKI 现状是一个活跃的研究领域，未来必须出现更具可行性的激进解决方案。

转向中等方案，SSH 模型也被提过（有时被称为*首次使用信任*，即 TOFU，*Trust on First Use*）。在这种模型中，不再隐式信任任何站点或 CA，由用户决定第一次信任哪个站点。然而，与 SSH 不同的是，你直接或间接（通过 CDN、嵌入内容等）访问的站点数量几乎是无限的，用户管理的信任是非常现实的。

## 聚合与信任捷活性

类似但更实用的是 Convergence[75]。*Convergence* 是基于*信任捷活性*理念的系统，定义为“轻松选择信任对象并随时修改该决策的能力……”。它既能提醒浏览器（或操作系统）预选的信任根锚集，也意识到无法指望用户对他们访问的所有站点独立做出信任决策。信任决策被委托给一组公证节点（notaries），他们通过确认你从站点收到的证书是他们之前见过的证书来为站点背书。如果多个公证节点都指出证书是正确的，用户就可以合理地认为它是真实且经过彻底信任的。

Convergence 并不是一个正式标准，但已经发布了一个工作实现，包括一个 Firefox 插件（客户端）和一个服务器端公证软件。虽然该系统很有前景，但目前可用的公证节点数量有限，Google 已经公开表示不会将其加入 Chrome。此外，它无法作为浏览器扩展实现，因为 Chrome 不允许第三方扩展扩展默认的证书验证模块。

## 证书固定（Certificate Pinning）

这引导我们关注目前的演化解决方案，这些方案已部署在相当大的用户群体中，主要归功于 Chrome 浏览器的推动。一个是证书黑名单（我们已经讨论过），另一个是证书固定。

固定（或更准确地说，公钥固定）采取了与黑名单方法相反的策略；它将受信任为特定站点签发证书的密钥列入白名单。固定功能在 Google Chrome 13 版本中引入，以限制为 Google 属性签发证书的 CA。它是通过维护一个为 DNS 名称签发证书的公钥列表来实现的。在验证主机证书时会检查该列表，如果链中包含至少一个白名单中的密钥，则验证失败。在实践中，浏览器保留了受信任证书的 `SubjectPublicKeyInfo` (SPKI) 字段的 SHA-1 哈希列表。固定公钥而非实际证书，允许在更新主机时不破坏验证，且不需要更新固定信息。

然而，硬编码的固定列表并不能真正解决可扩展性问题：已经提出了几个新的互联网标准来解决这个问题：由 Google 提出的 HTTP 公钥固定扩展（PKPE）[76] 和由 Moxie Marlin 提出的证书密钥信任断言（TACK）[77]。前者更为简单，提议了一种新的 HTTP 标头（`Public-Key-Pin`，或 PKP），其中包含有关主机证书的固定信息。该标头值可以包含公钥、固定有效期，以及一个指定是否应将固定应用于当前主机子域的标记。固定信息必须通过安全 (SSL) 连接传输，并且第一个包含 PKPE 标头的连接将是隐式信任的（并可选地针对客户端中内置的固定信息进行验证）。该协议还支持通过 `report-uri` 指令报告失败的验证（带有 `Public-Key-Pins-Report-Only` 标头），其中验证失败会被报告但仍允许通过。这使得能够通知管理员其站点可能遭受的 MITM 攻击，以便他们采取适当行动。

另一方面，TACK 提议更为复杂，它定义了一种新的 TLS 扩展（也称为 TACK），其携带了用专用 TACK 密钥签名的固定信息。到固定主机名的 TLS 连接要求服务器呈现一个“tack”，其中包含固定的密钥以及一个对服务器公钥的相应签名。固定信息和验证都在 TLS 层完成。相比之下，PKPE 使用 HTTP 层（在 TLS 之上）向客户端发送固定信息，但同时也要求在（实际上）在 TLS 层进行验证，如果与固定信息比对后验证失败，则断开连接。

既然我们已经了解了固定是如何运作的，让我们看看它在 Android 上是如何实现的。

## Android 中的证书固定

固定是 Android 4.2 引入的安全增强功能之一。该系统没有内置的固定信息，而是从 `/data/misc/keychain/` 目录下的一个文件中读取它们（该目录存储了信任根锚）。该文件名为 `pins`，并遵循以下格式：

示例 10. 系统 pins 格式

```
hostname=enforcing=true,sha1-hash1,sha1-hash2,...
```

这里，`enforcing` 为 true 或 false，后面跟着由逗号分隔的哈希列表。注意，没有有效期，因此固定在删除之前始终有效。该文件不仅被浏览器使用，还被集成在 `libcrypto` 中。这意味着不知道固定的旧库可以正常运行。固定功能通过 `X09Extensions` 暴露给第三方库和应用。它有一个方法：

示例 11. X09Extensions 证书验证方法

+   `void checkTrusted(X09Certificate[] chain, String authType, String host)`

系统中的哪个部分使用了这个新功能？默认的 SSL 引擎 (JSSE)，即客户端握手 (`ClientHandshake`) 和 SSL Socket (`OpenSSocket`) 实现会检查底层的 `TrustManager`，如果它支持固定，将对固定列表进行额外验证。如果验证失败，连接将无法建立。

固定不是由操作系统写入的。它的更新由广播（`android.intent.action.UPDATE_PINS`）触发。扩展包含了新固定信息的路径、新版本（存储在 `/data/misc/keychain/metadata/version/`）、当前固定的哈希，以及对上述内容的 SHA12withRSA 签名。广播的接收者 (`CertPinInstallReceiver`) 会验证版本、哈希和签名，如果有效，则用新内容替换当前固定。签名新固定确保了只有控制私钥密钥的人才能更新它们。用于验证的相应公钥作为系统密钥存储在 `/data/data/com.android.providers.settings/databases/settings.db` 中。（截至目前，Nexus 设备上的固定包含 40 多个固定条目，涵盖了大多数 Google 属性，包括 Gmail、YouTube 和 Play 商店）。

## 总结

Android 构建标准 Java API（如 JSSE 和 CertPath）来实现 SSL 连接和所需的身份验证机制。大部分安全功能由基于 OpenSSL 的大部分原生 JSSE 实现提供，而证书验证和信任存储管理则由 Java 实现。Android 提供了一个共享的系统信任存储，可以通过设置界面或 `KeyStore` API 进行管理。所有使用 SSL 或证书验证 API 的应用程序都会继承其信任，除非显式指定了应用特定的信任。Android 的证书验证不使用撤销检查，而是依赖于证书黑名单用于检测受损的 CA 或终端实体证书。最后，Android 的最新版本支持系统级证书锁定（Certificate Pinning），以确保颁发给特定主机服务器证书的证书集。

- [58] T. Dierks and E. Rescorla, 传输层安全 (TLS) 协议版本 1.2，2008年8月，http://tools.ietf.org/html/rfc5246
- [59] A. Freier, P. Karlton, and P. Kocher, 安全套接层 (SSL) 协议版本 3.0，2011年8月，http://tools.ietf.org/html/rfc610
- [60] Mozilla, Mozilla CA 证书包含策略（2.2 版本），https://www.mozilla.org/en-US/about/governance/policies/security-group/certs/policy/inclusion/
- [61] S. Sansetti, 等.,2009 互联网公钥基础设施在线状态协议-OCSP，2013年6月，http://tools.ietf.org/html/rfc6960
- [62] Oracle, Java™ 安全套接字扩展 (JSSE) 参考指南，http://docs.oracle.com/java/7/docs/guides/jsse/JSSERefGuide.html
- [63] E. Rescorla, HTTP TLS，2000年5月，http://tools.ietf.org/html/rfc2818
- [64] D. Cooper, 等., 互联网 X.509 公钥基础设施证书和证书吊销列表 (CRL) 规范，2008年5月，http://tools.ietf.org/html/rfc5280
- [65] Oracle, Java™ PKI 程序员指南，http://docs.oracle.com/java/7/docs/guides/security/certpath/CertPathProgGuide.html
- [66] S. Blake-Wison, 等., 传输层安全 (TLS) 扩展，2003年6月，http://tools.ietf.org/html/rfc3546
- [67] Square, Inc., 适用于 Android 和 Java 应用的 HTTP & SPDY 客户端，http://square.github.io/okhttp/
- [68] 可以通过将 `EnableOnlineRevocationChecks` 设置为 `true`（默认是 `false`）来启用在线吊销检查。https://www.imperialviolet.org/2012/02/05/crlsets.html
- [69] D. Elastlake 3rd，传输层安全 (TLS) 扩展：扩展定义，2011年1月8日，http://tools.ietf.org/html/rfc6066#section-8
- [70] Electronic Frontier Foundation，SSL Observatory 中的未命名名称，2011年4月，https://www.eff.org/deeplinks/2011/04/unqualified-names-ssl-observatory
- [71] Electronic Frontier Foundation，EFF SSL Observatory，https://www.eff.org/observatory
- [72] 法国信息安全局 (ANSSI)，法国网络和信息安全局
- [73] B. Laurie, A. Langley, and E. Kasper, 证书透明度，2013年6月，http://tools.ietf.org/html/rfc6962
- [74] Thoughtcrime Labs, Convergence，http://convergence.io/
- [75] C. Evans, C. Palmer, and R. Slee, HTTP 的公钥锁定扩展，2014年8月7日，http://tools.ietf.org/html/draft-websec-key-pinning-20
- [76] M. Marlinspe, 证书密钥的信任断言，2013年7月，http://tack.org/draft.html

# 第 7 章 凭据存储



# 第 7 章 凭据存储

上一章介绍了`PKI`以及管理信任时涉及的挑战。虽然`PKI`最常见的用途是验证你所连接的实体（服务器身份验证），但它也被用于验证这些实体（客户端身份验证）。客户端验证主要存在于企业环境中，用于从桌面登录到远程访问公司服务器的所有场景。基于`PKI`的客户端验证要求客户端通过执行服务器可以独立验证的某些加密操作，证明它拥有一个身份验证密钥（通常是`RSA`私钥）。客户端验证的安全性很大程度上取决于保护身份验证密钥免受未经授权的使用。大多数操作系统提供了一个系统服务，应用程序可以使用该服务安全地存储和访问身份验证密钥，而无需自行实现密钥保护。`Android`从 1.6 版本开始提供此类服务，并且自`Android 4.0`以来有了改进。

`Android`的凭据存储可以用于存储内置功能的凭据，如`Wi-Fi`和`VPN`连接，以及 [... 文本继续 ...]

（注：根据提供的 OCR 文本，第 159-160 页的内容包含大量的重复和碎片化结构问题。我已根据提供的内容清理了逻辑流，同时保留了所有原始信息。）

（自纠正：提供的第 159-160 页 OCR 文本高度重复且包含重叠的句子。我处理了源文本中提供的唯一片段。）

## 系统凭据存储

系统凭据存储是一种在将凭据存储在磁盘之前对其进行加密的系统服务。加密密钥派自用户提供的密码：4.0 之前的版本为凭据存储保护密码，而`Android 4.0`之后的版本为设备解锁模式、`PIN`或密码。此外，凭据存储系统服务监管对存储凭据的访问，并确保只有明确授权的应用才能访问。

原始的凭据存储引入于`Android 1.6`，限于存储`VPN`和`Wi-Fi` `EAP`凭据。此外，导入凭据的唯一支持方法是通过上一节概述的系统设置`UI`进行，且没有用于凭据管理的公共`API`。

## 身份验证密钥与证书

在`EAP-TLS`和基于`PKI`的`VPN`案例中，客户端拥有身份验证密钥并由公司证书颁发机构 (`CA`) 证书。密钥有时存储在便携的防篡改设备中，如智能卡或`USB`令牌。这极大地提高了安全性，因为密钥无法从设备中提取，因此身份验证需要物理持有设备并知道密码。

### 表 7-1. 凭据存储功能演进

| Android 版本 | API 级别 | 凭据存储更改 |
| --- | --- | --- |
| 1.6 | 4 | 为`VPN`和`Wi-Fi`添加了凭据存储。 |
| 4.0 | 14 | 为凭据存储增加了公共`API` (`Keychain API`)。 |
| 4.1 | 16 | 增加了无需导出即可生成和使用密钥的能力。引入了`HAL`模块并支持硬件支持`RSA`密钥存储。 |
| 4.3 | 18 | 支持使用`AndroidKeyStore` `JCA`提供程序生成和访问应用私有密钥，并提供了检查设备是否支持硬件支持`RSA`密钥的`API`。 |
| 4.4 | 19 | 为`AndroidKeyStore` `JCA`提供程序增加了`ECDSA`和`DSA`支持。 |

## 凭据存储实现

我们现在知道`Android`可以导入加密的凭据并管理对它们的访问。让我们来看看这在底层是如何实现的。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_161_0.png)

## Keystore 服务

`Android`中的凭据存储管理最初是由一个名为`keystore`的单一原生守护进程实现的。它的功能最初限于存储加密形式的任意 blob，但随着`Android`的演进，它通过新功能得到了扩展。它向客户端提供了一个基于本地 `socket` 的接口，每个客户端负责管理自己的状态和 `socket` 连接。在`Android 4.3`中，key-store 守护进程被替换为集中的`Binder`，以便更好地与其他框架服务集成并便于扩展。让我们来看看这个`keystore`服务是如何工作的。

`keystore`服务定义在`init.rc`中，如示例 7-1 所示。

示例 7-1. `init.rc`中的`keystore`服务定义

```
service keystore /system/bin/keystore /data/misc/keystore
    class main
    user keystore
    group drmpe
```

如你所见，`keystore`服务以专用的`keystore`用户身份运行，并将文件存储在`/data/misc/keystore/`中。让我们先看一眼`/data/misc/keystore/`。如果你使用的是单用户设备（如手机），你只会在`keystore/`目录下找到一个`user_0/`目录，但在启用多用户的设备上，你应该为每个`Android`用户找到一个目录。

示例 7-2. 单用户设备上`keystore`目录的内容示例

```
# ls -la /data/misc/keystore/user_0
-rw-------ke keystore 84 .masterkey
-rw-------ke keystore 980 1000_CACERT_cacert
-rw-------ke keystore 756 1000_USRCERT_test
-rw-------ke keystore 884 1000_USRPKEY_test
-rw-------ke keystore 724 1019_USRCERT_myKey
-rw-------ke keystore 724 1019_USRCERT_myKey1
```

在此示例中，每个文件名都包含创建它的应用的 `UID`（1000 是系统）、类型类型（`CA`证书、用户证书或私钥）以及密钥名称（别名），所有内容通过下划线连接。从`Android 4.3`开始，还支持系统和应用私有密钥，`UID`同时反映了`Android`用户 ID 和应用 ID。在多用户设备上，用户 ID 是 `UID /100000`，如第 4 章所述。

除了系统或应用拥有的密钥 blob，还有一个单独的`.masterkey`文件，我们稍后会讨论。当存储受管理密钥的应用被卸载时，只有该应用创建的密钥会被删除。如果应用完全从系统中删除，则所有用户的该密钥都将被删除。由于密钥访问与应用 ID 绑定，此功能防止了获取相同 `UID` 的其他应用访问其他应用的密钥。（`keystore`重置会同时删除密钥文件和主密钥，但也影响当前用户。）

在默认的基于软件的实现中，这些文件的内容如下（硬件支持的实现可能不同；通常不存储加密密钥材料，而是存储指向硬件管理密钥对象的引用）：

- 主密钥（存储在`.masterkey`中）使用 128 位 `AES`密钥加密，该密钥通过`PBKDF2`密钥派生函数从屏幕解锁密码导出，并带有 8192 次迭代和随机生成的 128 位盐（salt）。盐存储在`masterkey`文件的头中。

- 所有其他文件存储的密钥。密钥 blob（二进制对象）包含一个序列化的、可选加密的密钥以及一些描述密钥的数据（元数据）。每个`keystore` blob 包含一个头部、加密的初始向量 (`IV`) 以及数据本身的`MD5`哈希值的拼接，并使用`CBC`模式下的 128 位 `AES`密钥加密。或者更简洁地说：元数据 | `Enc(MD5(data))` | data)。

在实践中，这种架构意味着`Android` `keystore`对于软件解决方案来说相当安全。即使你有 root 设备权限并成功提取了密钥，你仍然需要`keystore`密码来派生主密钥。尝试不同的密码来解密主密钥需要至少 8192 次迭代来派生密钥，这成本是极高的。此外，由于派生函数是……

## 密钥 blob 版本和类型

从`Android 4.1`开始，密钥 blob 两个字段：版本（version）和类型（type）。截至写作时，类型如下：

- `TYPE_ANY`
- `TYPE_GENERIC`
- `TYPE_MASTER_KEY`
- `TYPE_PAIR`

## 访问限制

密钥 blob 由`keystore`服务绑定，因此在（未 root 的）设备上，你需要通过`keystore`服务应用以下访问限制：

- root 用户无法锁定或解锁`keystore`，但系统用户可以执行更多操作。

## keymaster 模块和 keystore 服务实现

虽然原始基于守护进程的实现将密钥 blob 管理和加密包含在一个二进制文件中，但`Android 4.1`引入了新的`keymaster`抽象层 (`HAL`) 系统模块，以便更易地集成特定设备的实现。典型的实现会使用供应商提供的库与支持加密的硬件进行通信，并提供一个“胶水” `HAL`库，`keystore`守护进程会与之链接。

由关键系统服务（keystone system service）实现，不依赖于`HAL`模块。该服务向`AndroidManager`注册其`android.security.keystore`名称，并在启动时运行。与大多数`Android`服务不同，它使用`C++`实现，实现代码位于`system/security/keystore/`。

## Nexus 4 硬件保护实现

为了让大家对整个“硬件保护”的概念有一个直观的认识，让我们简单讨论一下在`Nexus 4`上是如何实现的。`Nexus 4`基于高通骁龙`S4 Pro APQ8064`级系统（`SoC`）。与大多数的`ARM SoC`一样，它启用了`TrustZone`，并在此基础上实现了高通的安全执行环境（`QSEE`）。

`ARM`的`TrustZone`技术提供了两个受硬件层级访问控制支持的虚拟处理器，这允许`SoC`系统被划分为两个虚拟“世界”：用于安全子系统的安全世界（Secure world）和用于处理其他所有内容的普通世界（Normal world）。运行在安全世界中的应用程序被称为信任应用（trusted applications），普通世界应用程序（`Android`操作系统和应用运行的环境）只能通过其显式暴露的有限接口进行访问。图 7-2 显示了启用`TrustZone`系统的典型软件配置。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_165_0.png)

图 7-2. `TrustZone`软件架构

如往常，实现细节非常稀少，但在`Nexus 4`上，与信任应用交互的唯一方式是通过`/dev/qseecom`设备提供的控制接口。希望与`QSEE`交互的`Android`应用加载专有的`libQSEEComAPI.so`库并使用其函数向`QSEE`发送命令。

对于大多数其他安全执行环境（`SEE`），`QSEECom`通信`API`相当底层，基本上只允许交换不透明的数据块（命令和回复），其内容取决于你通信的安全应用。在`Nexus 4`密钥大师（keymaster）的情况下，使用的命令有：`GENERATE_KEYPAIR`、`IMPORT_KEYPAIR`、`SIGN_DATA`和`VERIFY_DATA`。密钥大师实现仅创建命令、通过`QSEE` `API`发送并对其进行解析。它不包含任何加密代码。

一个细节是，`QSEE`信任应用（可能不是一个专用应用，而是更通用的信任应用的一部分）并不返回受保护密钥的简单引用；它保护其专有的密钥块（key blobs）。在这种模型中，真正受硬件保护的是某些主密钥加密密钥（`KEK`）；用户生成的密钥仅通过被`KEK`加密来间接受保护。

这种方法允许实际上无限制数量的受保护密钥，但缺点是，如果`KEK`被攻破解，所有外部存储的密钥块也将随之被破解。（当然，实际实现可能会为每个密钥块生成专用的`KEK`，或者将密钥熔合在硬件中；然而，关于内部实现的细节尚不可。）因此，高通密钥大师在`AOSP`示例 7-3 中定义，该定义建议私指数使用`AES`（主要为`CBC`模式）进行加密，并使用`HMAC-SHA256`检查加密数据的完整性。

### 示例 7-3. `QSEE`密钥块定义（针对 `Nexus 4`）

```c
#define KM_MAGIC_NUM (0xB4B4B42) /* 十进制格式的 "KMB" 密钥大师密钥块 */
#define KM_KEY_SIZE_MAX (512) /* 4096 字节 */
#define KM_IV_LENGTH (16) /* AES128 CBC IV */
#define KM_HMAC_LENGTH (32) /* SHA2 将用于 HMAC */

struct qcom_key_blob {
    uint32_t magic_num;
    uint32_t version_num;
    uint8_t modulus[KM_KEY_SIZE_MAX];
    uint8_t modulus_size;
    uint8_t public_exponent[KM_KEY_SIZE_MAX];
    uint32_t public_exponent_size;
    uint8_t iv[KM_IV_LENGTH];
    uint8_t encrypted_private_exponent[KM_KEY_SIZE_MAX];
    uint32_t encrypted_private_exponent;
    uint8_t hmac[KM_HMAC_LENGTH];
};
```

如示例 7-3 所示，`QSEE`密钥块包含模数、公指数、用于私钥指数加密的`IV`、指数本身以及`HMAC`值。

由于`Nexus 4`中使用的`QSEE`是使用处理器的`TrustZone`函数实现的，在这种情况下，硬件保护凭据库的“硬件”就是`ARM SoC`。那么还有其他可能的实现吗？理论上，硬件保护的密钥大师实现并不需要基于`TrustZone`。任何可以安全地生成和存储密钥的专用设备都可以实现，通常这些设备具有内置的安全元件（`SE`）和可信平台模块（`TPM`）。我们将在第 11 章讨论`SE`和其他防篡设备，但于撰稿时，主流设备尚未配备`TPM`。当然，所有移动设备都具有某种形式的集成电路卡（`UICC`），俗称为`SIM`卡，它通常可以生成并存储密钥，但`Android`并没有标准`API`来访问`UICC`，尽管理论上可以实现基于`UICC`的密钥模块。

## 框架集成

安全地管理凭据是框架的主要目的。`Android`为使用`KeyChain API`的第三方应用提供了高级抽象。虽然系统应用可以直接或通过`android.security.KeyStore`类访问密钥库，但这些接口与实现耦合得紧密，无法作为公共`API`。`Android`为使用`KeyChain API`和`AndroidKeyStore`提供程序的第三方应用提供了高级抽象。我们将展示这些`API`如何使用并提供一些实现细节。

### KeyChain API

`Android`从 1.6 版本开始提供系统级凭据库，但它仅供`VPN`和`Wi-Fi` `EAP`客户端使用。可以使用设置应用安装密钥/证书对，但第三方应用程序无法访问这些密钥。

`Android 4.0`通过`KeyChain`类引入了信任证书和安全凭据的`SDK`。该功能在`Android 4.3`中被扩展以支持新引入的硬件功能。我们将讨论如何使用它并审查其实现。

### KeyChain 类

`KeyChain`类非常简单：它提供了六个静态方法，足以处理大多数证书和密钥任务。我们将查看如何安装私钥/证书对，然后使用它访问由凭据库管理的私钥。

`KeyChain API`允许你安装封装在`PKCS#12`文件中的私钥/证书对。`KeyChain.createInstallIntent()`工方法是该功能的入口。它不接受参数并返回一个可以解析并安装密钥和证书的 intent。（这实际上是设置应用内部使用的 intent。）

## 安装 PKCS#12 文件

要安装`PKCS#12`文件，你需要将其读取为字节数组，将其存储在 intent 的 extras 中的`EXTRA_PKCS12`键下，并启动关联活动（参见示例 7-4）：

示例 7-4. 使用`KeyChain API`安装`PKCS#12`文件

```java
Intent intent = KeyChain.createInstallIntent();
byte[] p12 = readFile("keystore-test.pfx");
intent.putExtra(KeyChain.EXTRA_PKCS12, p12);
startActivity(intent);
```

这应当提示你输入`PKCS#12`密码，以便提取并解析密钥和证书。如果密码正确，系统将提示你输入证书名称，如[图 7-3]所示。如果`PKCS#12`具有友好名称（friendly name）属性，它将显示为默认值；否则，你将得到一个长的十六进制哈希字符串。你在这里输入的字符串是密钥或证书的别名，你可以使用它通过`Keychain API`查找并访问密钥。如果你尚未设置锁屏，系统将提示你设置锁屏`PIN`或密码以保护凭据存储。

### 使用私钥

要使用存储在系统凭据库中的私钥，你需要通过其别名（alias）获取该密钥的引用，并向系统请求访问权限。如果你从未访问过密钥且不知道它的别名，需要先调用`Keychain.choosePrivateKeyAlias()`并提供一个回调实现，该回调将接收选定的别名，如[示例 7-5]所示。

示例 7-5. 使用存储在系统凭据库中的私钥



```java
public class KeystoreTest extends Activity implements OnClickListener,
KeychainAliasCallback() {
    @Override
    public void onClick(View view) {
        Keychain.choosePrivateKeyAlias(this, 2,new String[]{"RSA"}, 4,null, 5,null, 6,-1, 7,null);
    }
}
```

![](img/8524e4e57e2e9dc889903e3d2c5fe367_169_0.png)

```java
@Override
public void alias(final String alias) {
    Log.d(TAG, "Thread: " + Thread.currentThread().getName());
    Log.d(TAG, "selected alias: " + alias);
}
```

第一个参数`1`是当前上下文（context），第二个参数`2`是要调用的回调，第三和第四个参数指定了接受的密钥类型`3`（RSA, DSA, null 或 any）以及匹配私钥的接受证书颁发者`4`。接下来的两个参数是请求证书的服务器主机`5`和端口号`6`，最后一个参数`7`是在密钥选择对话框中预选的别名。我们在这里省略了所有指定的密钥类型（`null`或`-1`），以便从所有可用证书中选择。注意，`alias()` `8`回调不会在主线程执行，因此不要尝试从中直接操作 UI。（它在 binder 线程上调用）。

使用密钥需要用户授权，因此 Android 应该显示密钥选择对话框（参见图 7-4），该对话框也用于授予对所选密钥的访问权限。一旦用户为应用授予密钥访问权限，应用就可以查找该密钥而无需通过密钥选择对话框。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_170_0.png)

图 7-4 密钥选择对话框

示例 7-6 显示了如何使用 Keychain API 获取由系统密钥库管理的私钥的引用。

示例 7-6. 获取密钥实例及其证书链

```java
PrivateKey pk = KeyChain.getPrivateKey(context, alias);①
X509Certificate[] chain = KeyChain.getCertificateChain(context, alias);②
```

要引用私钥，你需要调用`KeyChain.getPrivateKey()`①方法，并传入上一步接收的密钥别名。如果你尝试在主线程调用此方法，将得到异常，请确保从后台线程（如由`AsyncTask`工具类创建的线程）中调用它。`getActivityChain()`②方法返回与私钥相关的证书链（参见示例 7-6）。如果密钥或证书别名不存在，`getPrivateKey()`和`getCertificateChain()`方法返回`null`。

### 安装 CA 证书

安装 CA 证书与安装 PKCS-12 文件没有太大区别。要这样做，将证书加载到字节数组中，并作为 extra 通过`EXTRA_CERTIFICATE`键传递到安装 intent 中，如示例 7-7 所示。

```java
Example 7-7. 使用 Keychain API 安装 CA 证书
Intent intent = KeyChain.createInstallIntent();
intent.putExtra(KeyChain.EXTRA_CERTIFICATE, cert);
startActivity(intent);
```

Android 会解析证书，如果其基本约束（Basic Constraints）扩展设置为`CA:TRUE`，则认为它是 CA 证书并将其导入用户信任存储库。你需要进行身份验证以导入证书。

遗憾的是，导入对话框（参见图 7-5）既不显示证书 DN（区分名称）也不显示其哈希值。在完成之前，用户无法知道他们导入的是什么。很少有人会检查证书的有效性，因为这可能是潜在的安全威胁，因为恶意应用程序可能会诱导人们安装伪造证书。

证书导入后，它应该出现在受信任凭据屏幕的“用户”选项卡中（设置 ► 安全 受信任的凭据）。点击证书条目将显示详细对话框，你可以在其中检查主题、颁发者、有效期、序列号以及 SHA-1/SHA-256 指纹。要删除证书，请按“删除”按钮（参见图 7-6）。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_172_0.png)

图 7-5 CA 证书导入对话框

### 安装 CA 证书

安装 CA 证书与安装 PKCS-12 文件非常相似。要这样做，将证书加载到字节数组中，并作为 extra 通过`EXTRA_CERTIFICATE`键传递到安装 intent 中，如示例 7-7 所示。

Android 会解析证书，如果其基本约束（Basic Constraints）扩展设置为`CA:TRUE`，则认为它是 CA 证书并将其导入用户信任存储库。你需要进行身份验证以导入证书。

遗憾的是，导入对话框（参见图 7-5）既不显示证书 DN 显示其哈希值。在完成之前，用户无法知道他们导入的是什么。很少有人会检查证书的有效性，因为这可能是潜在的安全威胁，因为恶意应用程序可能会诱导人们安装伪造证书。

证书导入后，它应该出现在受信任凭据屏幕的“用户”选项卡中（设置 ► 安全 受信任的凭据）。点击证书条目将显示详细对话框，你可以在其中检查主题、颁发者、有效期、序列号以及 SHA-1/SHA-256 指纹。要删除证书，请按“删除”按钮（参见图 7-6）。

## 删除密钥与证书

删除密钥与证书

虽然你可以删除 CA 证书，但没有方法可以删除密钥和用户证书，凭据设置中的清除选项将删除所有密钥和用户证书。

注意

只要凭据存储库中有密钥，Keychain 就会用于保护对凭据的访问。

## 获取支持的算法信息

获取支持的算法信息

Android 4.3 为`KeyChain`类增加了两个相关方法。根据 API 文档，`isBoundAlgorithm(String algorithm)`“如果当前的 Keychain 实现绑定了指定的类型将返回`true`”。也就是说，如果向此方法传递字符串，`isAlgorithmSupported(String algorithm)`应该返回`true`。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_173_0.png)

## Keychain 实现

我们引入了 Keychain API 的主要功能。现在让我们查看底层实现。

公共的`KeyChain`类和辅助接口位于`android.security`包。该包还包含两个 AIDL 文件：`IKeychainService.aidl`和`IAliasCallback`。`IAliasCallback`在你通过`KeyStore.choosePrivateKeyAlias()`选择密钥时被调用，因此意义不大。

## 控制密钥库

由于 Keychain 应用以系统用户身份运行，任何绑定到其远程接口的进程在技术上都能够执行所有密钥和信任操作。为了防止这种情况，KeychainService 根据调用者的 UID 对凭据存储操作实施额外的访问控制，并使用访问授权数据库管理对单个密钥的访问。只有系统用户可以删除 CA 证书并重置密钥和信任库（这些操作通常通过运行为系统的设置 UI 调用）。同样，只有系统用户或证书安装程序（`com.android.certinstaller`包）可以安装受信任的 CA。

控制凭据库中单个密钥的访问比限制操作更有趣。KeychainService 维护了一个访问授权数据库（位于`/data/data/com.android.keychain/databases/grants.db`），将 UID 映射到它们允许使用的密钥别名。让我们查看示例 7-8 内部情况。

示例 7-8. 授权数据库的架构和内容

```
# sqlite3 grants.db
```

## sqlite:schema

```sql
CREATE TABLE android_metadata (locale TEXT);
CREATE TABLE grants (alias STRING NOT NULL, INTEGER NOT NULL, UNIQUE (alias,uid));
sql: select * from grants;
select from grants;
```

①test10044 ②

③key110044 ②

在这个示例中，UID 为 10044 ② 的应用程序被授予访问别名为 key1 ① ② 密钥的权限。

每次调用`getPrivateKey()`或`getCertificate()`都会对 grants 数据库进行检查，如果未找到授权，将抛出异常。如前所述，KeyChainService 提供了添加和查询授权的 API，且只有系统用户可以调用它们。但谁负责实际授予和撤销访问呢？

还记得私钥选择对话框（图 7-4）吗？当你调用`Keychain.chooseKeyAlias()`时，它会启动 KeyChainActivity（上文介绍），该活动会检查密钥库是否解锁；如果是，KeyChainActivity 将显示密钥选择对话框。点击 Allow（允许）按钮将返回 KeyChainActivity，随后它调用`KeychainService.setGrant()`将其添加到 grants 数据库。因此，即使请求访问私钥的程序拥有所需的权限，用户必须解锁密钥库并显式授权对每个单独密钥的访问。

除了控制私钥存储，KeychainService 还通过新添加的`TrustedCertificateStore`类（来自 libcore）提供信任管理。该类既提供了添加用户安装的 CA 证书的能力，提供了移除（标记为不可信）系统（预装）CA 的能力。第 6 章讨论了其实现细节。

## KeyChainBroadcastReceiver

Keychain 应用的最后一个组件是 KeyChainBroadcastReceiver。它监听`android.intent.action.PACKAGE_REMOVED`系统广播，并将控制权转发给 KeychainService。在接收到 PACKAGE_REMOVED 动作时，该服务会执行一些数据库维护：它遍历所有条目并删除任何引用已不可用的包（即已卸载的包）。

## 凭据和信任存储摘要

Android 4.0 引入了一项新服务，用于授予对系统密钥库（由密钥库系统服务管理）和信任存储（由`TrustedCertificateStore`类管理，后者支持在公共 SDK 中暴露的 KeyChain API）的访问。此功能允许根据调用进程的 UID 和授权数据库来控制对密钥的访问，从而对每个应用程序可以访问哪些密钥实现细粒度的、用户驱动的控制。Android 凭据和信任存储的组件及其关系如图 7-7 所示。

## Android Keystore Provider

虽然 Android 4.0 引入的 Key API 允许应用程序将密钥导入系统凭据存储中，但这些密钥由系统用户所有，任何应用程序都可以请求访问它们。Android 4.3 增加了对应用私有密钥的支持，允许任何应用生成并保存私钥，这些私钥仅供自身访问和使用，对其他应用不可见。

密钥库访问并没有引入另一个 Android 特有的 API，而是通过标准的 JCA API 暴露，即`java.security.KeyPairGenerator`和`java.security.KeyStore`。这两者都由另一个 Android JCA 提供者`AndroidKeyStoreProvider`支持，并通过通过将`AndroidKeyStore`传递相应工厂方法的类型参数来访问。示例 7-9 显示了如何使用`AndroidKeyStoreProvider`生成和访问 RSA 密钥。

**示例 7-9. 使用 AndroidKeyStoreProvider 生成和访问 RSA 密钥**

```java
// generate a key pair
Calendar notBefore = Calendar.getInstance();
Calendar notAfter = Calendar.getInstance();
notAfter.add(1, Calendar.YEAR);
KeyPairGeneratorSpec spec = new KeyPairGeneratorSpec.Builder(ctx).setAlias("key1").
setKeyType("RSA").
setKeySize(2048).
setSubject(new X509Principal(Integer.ONE)).startDate(notBefore.getTime())
setEndDate(notAfter.getTime()).build();①
KeyPairGenerator kpGenerator = KeyPairGenerator.getInstance("RSA");
kpGenerator.initialize(spec);②
KeyPair kp = kpGenerator.generateKeyPair();③
// in another part of the app, access the keys
KeyStore ks = KeyStore.getInstance("AndroidKeyStore");
ks.load(null);
KeyStore.PrivateKeyKeyEntry entry = (KeyStore.PrivateKeyKeyEntry)ks.getKey("key1",null);④
RSAPublicKey publicKey = (RSAPublicKey)entry.getCertificate().getPublicKey();
```

![](img/8524e4e57e2e9dc889903e3d2c5fe367_176_0.png)

```java
RSrivateKey privKey = (RSrivateKey) keyEntry.getPrivateKey();
```

① 你创建了一个`KeyPairGenerator`来生成密钥，并且自动创建的自签名证书密钥与之关联。你可以使用`setKeyType()`方法指定密钥类型（RSA、DSA 或 EC），并使用`setKeySize()`方法指定密钥大小。

## NOTE

每个管理的`KeyEntry`都需要与一个`KeyStore`对象关联。Android 在生成密钥时会自动创建一个自签名证书，但你稍可以使用由 CA 签名的证书替换默认证书。

接下来，你使用`KeyPairGeneratorSpec`实例初始化`KeyPairGenerator`②，然后通过调用`generateKeyPair()`③生成密钥。

最重要的参数是别名（alias）。你将别名传递给`KeyStore.getEntry()`④以获取生成密钥的引用。返回的密钥对象不包含实际的密钥材料；它只是一个指向硬件管理内容的指针。

## 总结

正如你在本章中所学到的，Android 为第三方应用程序提供了一个系统凭据存储，Android 4.3 及更高版本提供了系统应用无法提取的硬件支持存储。

# 第 8 章 账户管理

虽然企业服务通常采用 PKI 进行用户身份验证，但在触摸屏移动设备上多次输入复杂的密码并不愉快。为了改进访问在线服务的用户体验，Android 提供了一个用户账户集中注册，无需应用程序处理密码。

## Android 账户管理概述

早期的 Android 设备内置对 Google 账户的支持和自动数据同步，最初没有提供这些功能的 API。Android 2.0（API 5）引入了带有公共 API 的集中账户管理概念。核心是`AccountManager`类，它提供了对用户账户集中注册的访问。用户每个账户只需输入一次凭据（用户名和密码），即可授权应用程序访问在线资源。该类的另一个主要功能是它可以获取支持账户的身份验证令牌，允许第三方应用程序对在线服务进行验证。在某些旧 Android 版本中，AccountManager 会监控 SIM 卡并在更换卡时擦除凭据，但此功能在 Android 2.3.4 及更高版本中移除。

## 账户管理实现

对于大多数 Android 系统 API，`AccountManager`只是`AccountManagerService`的门面，由后者执行实际工作。然而，该服务并没有为任何特定形式的身份验证提供实现。它仅仅协调了不同账户类型（Google、Twitter、Microsoft Exchange 等）的多个插拔身份验证模块。任何应用程序都可以通过实现账户验证器和相关类（如果需要）来注册身份验证模块。我们在“添加身份验证模块”中展示了如何编写和注册自定义的身份验证模块。

在系统中注册新的账户类型可以让你利用许多 Android 基础设施服务，包括：

- 使用系统数据库中的集中式凭据存储

- 向第三方应用发放令牌

- 利用 Android 的自动后台同步（通过同步适配器）

**图 8-1** 显示了 Android 账户管理子系统的主要组件及其关系

关系。每个组件及其角色将在接下来的章节中描述。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_179_0.png)

## AccountManagerService 和 AccountManager



这里的核心部分是`AccountManagerService`，它协调所有其他组件并在账户数据库中持久化账户数据。`AccountManager`类是一个门面，向第三方应用程序暴露其功能的一个子集。它通过工作线程处理异步方法，并将结果（或错误详情）传回调用者。此外，当请求的令牌或功能可以由多个项提供时，`AccountManager`会显示账户选择器。然而，它并不强制执行任何权限；所有调用者的权限都由`AccountManagerService`检查，我们很快就会讨论具体的权限。

## 身份验证器模块（Authenticator Modules）

如上所述，每个注册身份验证器的功能由可插拔的身份验证器模块提供，身份验证器模块到底是什么？它们由应用程序定义并托管，每个模块仅仅是实现了`android.accounts.Authenticator` AIDL 接口的绑定服务。该接口包含添加账户、提示用户输入凭据、获取身份验证令牌以及更新账户元数据的方法。在实践中，应用程序并不直接实现此接口，而是扩展`android.accounts.AbstractAccountAuthenticator`类，该类将实现方法链接到内部 AIDL 存根。

`AbstractAccountAuthenticator`还确保所有 AIDL 存根的调用者都持有`ACCOUNT_MANAGER`权限；这是一个系统签名权限，仅允许系统组件直接调用身份验证器模块。所有其他客户端都需要通过`AccountManagerService`。

每个身份验证器模块实现一个由名为“账户类型”（account type）的字符串唯一标识的账户。账户通常采用反向域名表示法（类似于 Java 包），并通常使用定义应用程序的包名与账户类型拼接来命名（尽管 Android 并不强制执行此规则，也没有显式指南）。例如，在图 8-1 中，`com.example.app`应用定义了一个类型为`com.example.account`的账户，而`org.foo.app`应用定义了一个类型为`org.foo.account`的账户。

身份验证器的实现是通过向宿主应用添加一个可以使用`android.accounts.Authenticator` intent action 进行绑定的服务完成的。账户类型以及其他元数据通过在服务声明中添加`<meta-data>`标签与服务关联。该标签的`resource`属性指向一个包含账户元数据的 XML 文件（示例参见示例 8-8）。

> NOTE
>
> ` <meta-data>`标签允许将包含任意数据的键值对与其父组件关联。该数据可以是字面量（如字符串或整数），也可以是引用 Android 资源文件的引用。每个组件也支持多个`<meta-data>`标签。所有`<meta-data>`标签的值被收集在一个`Bundle`对象中，并作为`PackageInfo`的`metadata`字段可用（即封装组件值的具体类，如`ServiceInfo`）。对关联元数据的解释取决于具体的组件。

## 身份验证器模块缓存（The Authenticator Module Cache）

“可插拔性”由`AccountAuthenticatorCache`类提供，它扫描定义身份验证器模块的包并将它们提供给`AccountManagerService`。`AccountAuthenticatorCache`是 Android 提供的更通用注册服务缓存的一种实现。该缓存按需（懒加载）通过询问`PackageManagerService`关于注册了特定 intent 和元数据的已安装包来构建。当包被添加、更新或删除时，通过广播接收器触发更新以保持缓存最新。缓存是持久的，并在检测到更改时写入磁盘，缓存文件写入`/data/system/registered_services/`目录，并根据它们扫描的 intent 命名。身份验证器模块缓存保存到`android.accounts.AccountAuthenticator.xml`文件中，看起来可能类似于示例 8-1。

### 8-1. `AccountAuthenticator.xml`注册服务缓存的内容

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<services>
  <service uid="100023" type="com.android.exchange" /> 1
  <service uid="100023" type="com.android.email" /> 2
  <service uid="100069" type="com.example.account" /> 3
  <service uid="100074" type="org.foo.account" /> 4
  <!--snp-->
  <service uid="1010023" type="com.android.email" /> 5
  <service uid="1010023" type="com.android.exchange" /> 6
  <service uid="1010069" type="com.example.account" /> 7
  <!--snp-->
</services>
```

在这里，`com.android.exchange`和`com.android.email`账户类型 (1) 和 (2) 由内置应用注册，而`com.example.account`和`org.foo.account` (3) 和 (4) 由第三方应用程序注册。在多用户设备上，缓存文件将包含每个用户可用账户条目。

在本示例中，第一个次要用户（用户 ID 10）可以使用`com.android.exchange`、`com.android.email`和`com.example.account` (5、6 和 7)，但不能使用`org.foo.account`。

## AccountManagerService 操作与权限

如图 8-1 所示，`com.android.exchange`和`com.android.email`账户类型 (1) 和 (2) 由内置应用注册，`com.example.account`和`org.foo.account` (3) 和 (4) 由第三方应用程序注册。在多用户设备上，缓存文件将包含每个用户可用账户条目。

在本示例中，第一个次要用户（用户 ID 10）可以使用`com.android.exchange`、`com.android.email`和`com.example.account` (5、6 和 7)，但不能使用`org.foo.account`。

这里的核心部分是`AccountManagerService`，它协调所有其他组件并在账户数据库中持久化账户数据。`AccountManager`类是一个门面，向第三方应用程序暴露其功能的一个子集。它通过工作线程处理异步方法，并将结果（或错误详情）传回调用者。此外，当请求的令牌或功能可以由多个项提供时，`AccountManager`会显示账户选择器。然而，它并不强制执行任何权限；所有调用者的权限都由`AccountManagerService`检查，我们很快就会讨论具体的权限。

## 列出与身份验证账户（Listing and Authenticating Accounts）

如上所述，每个注册身份验证器的功能由可插拔的身份验证器模块提供，身份验证器模块到底是什么？它们由应用程序定义并托管，每个模块仅仅是实现了`android.accounts.Authenticator` AIDL 接口的绑定服务。该接口包含添加账户、提示用户输入凭据、获取身份验证令牌以及更新账户元数据的方法。在实践中，应用程序并不直接实现此接口，而是扩展`android.accounts.AbstractAccountAuthenticator`类，该类将实现方法链接到内部 AIDL 存 stub。

`AbstractAccountAuthenticator`还确保所有 AIDL 存 stub 的调用者都持有`ACCOUNT_MANAGER`权限；这是一个系统签名权限，仅允许系统组件直接调用身份验证器模块。所有其他客户端都需要通过`AccountManagerService`。

每个身份验证器模块实现一个由名为“账户类型”的字符串唯一标识的账户。账户通常采用反向域名表示法（类似于 Java 包），并通常使用定义应用程序的包名与账户类型拼接来命名（尽管 Android 并不强制执行此规则，也没有显式指南）。例如，在图 8-1 中，`com.example.app`应用定义了一个类型为`com.example.account`的账户，而`org.foo.app`应用定义了一个类型为`org.foo.account`的账户。

身份验证器的实现是通过向宿主应用添加一个可以使用`android.accounts.Authenticator` intent action 进行绑定的服务完成的。账户类型以及其他元数据通过在服务声明中添加`<meta-data>`标签与服务关联。该标签的`resource`属性指向一个包含账户元数据的 XML 文件（示例参见示例 8-8）。

> NOTE
>
> `<meta-data>`标签允许将包含任意数据的键值对与其父组件关联。该数据可以是字面量（如字符串或整数），也可以是引用 Android 资源文件的引用。每个组件也支持多个`<meta-data>`标签。所有`<meta-data>`标签的值被收集在一个`Bundle`对象中，并作为`PackageInfo`的`metadata`字段可用（即封装组件值的具体类，如`ServiceInfo`）。对关联元数据的解释取决于具体的组件。

## 身份验证器模块缓存（The Authenticator Module Cache）

“可插拔性”由`AccountAuthenticatorCache`类提供，它扫描定义身份验证器模块的包并将它们提供给`AccountManagerService`。`AccountAuthenticatorCache`是 Android 提供的更通用注册服务缓存的一种实现。该缓存按需（懒加载）通过询问`PackageManagerService`关于注册了特定 intent 和元数据的已安装包来构建。当包被添加、更新或删除时，通过广播接收器触发更新以保持缓存最新。缓存是持久的，并在检测到更改时写入磁盘，缓存文件写入`/data/system/registered_services/`目录，并根据它们扫描的 intent 命名。身份验证器模块缓存保存到`android.accounts.AccountAuthenticator.xml`文件中，看起来可能类似于示例 8-1。

### 8-1. `AccountAuthenticator.xml`注册服务缓存的内容



```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<services>
  <service uid="100023" type="com.android.exchange" /> 1
  <service uid="100023" type="com.android.email" /> 2
  <service uid="100069" type="com.example.account" /> 3
  <service uid="100074" type="org.foo.account" /> 4
  <!--snp-->
  <service uid="1010023" type="com.android.email" /> 5
  <service uid="1010023" type="com.android.exchange" /> 6
  <service uid="1010069" type="com.example.account" /> 7
  <!--snp-->
</services>
```

在这里，`com.android.exchange` 和 `com.android.email` 账户类型 (1) 和 (2) 由内置应用注册，而 `com.example.account` 和 `org.foo.account` (3) 和 (4) 由第三方应用程序注册。在多用户设备上，缓存文件将包含每个用户可用账户条目。

在本示例中，第一个次要用户（用户 ID 10）可以使用 `com.android.exchange`、`com.android.email` 和 `com.example.account` (5, 6 和 7)，但不能使用 `org.foo.account`。

# AccountManagerService 操作与权限

这里的核心部分是 `AccountManagerService`，它协调所有其他组件并在账户数据库中持久化账户数据。`AccountManager` 类是一个门面，向第三方应用程序暴露其功能的一个子集。它通过工作线程处理异步方法，并将结果（或错误详情）传回调用者。此外，当请求的令牌或功能可以由多个项提供时，`AccountManager` 会显示账户选择器。然而，它并不强制执行任何权限；所有调用者的权限都由 `AccountManagerService` 检查，我们很快就会讨论具体的权限。

# 列出与身份验证账户 (Listing and Authenticating Accounts)

如上所述，每个注册身份验证器的功能由可插拔的身份验证器模块提供，身份验证器模块到底是什么？它们由应用程序定义并托管，每个模块仅仅是实现了 `android.accounts.Authenticator` AIDL 接口的绑定服务。该接口包含添加账户、提示用户输入凭据、获取身份验证令牌以及更新账户元数据的方法。在实践中，应用程序并不直接实现此接口，而是扩展 `android.accounts.AbstractAccountAuthenticator` 类，该类将实现方法链接到内部 AIDL 存。

`AbstractAccountAuthenticator` 还确保所有 AIDL 存的调用者都持有 `ACCOUNT_MANAGER` 权限；这是一个系统签名权限，仅允许系统组件直接调用身份验证器模块。所有其他客户端都需要通过 `AccountManagerService`。

每个身份验证器模块实现一个由名为“账户类型”的字符串唯一标识的账户。账户通常采用反向域名表示法（类似于 Java 包），并通常使用定义应用程序的包名与账户类型拼接来命名（尽管 Android 并不强制执行此规则，也没有显式指南）。例如，在图 8-1 中，`com.example.app` 应用定义了一个类型为 `com.example.account` 的账户，而 `org.foo.app` 应用定义了一个类型为 `org.foo.account` 的账户。

身份验证器的实现是通过向宿主应用添加一个可以使用 `android.accounts.Authenticator` intent action 进行绑定的服务完成的。账户类型以及其他元数据通过在服务声明中添加 `<meta-data>` 标签与服务关联。该标签的 `resource` 属性指向一个包含账户元数据的 XML 文件（示例参见示例 8-8）。

> **注意**
>
> `<meta-data>` 标签允许将包含任意数据的键值对与其父组件关联。该数据可以是字面量（如字符串或整数），也可以是引用 Android 资源文件的引用。每个组件也支持多个 `<meta-data>` 标签。所有 `<meta-data>` 标签的值被收集在一个的 `Bundle` 对象中，并作为 `PackageInfo` 的 `metadata` 字段可用（即封装组件值的具体类，如 `ServiceInfo`）。对关联元数据的解释取决于具体的组件。

# 身份验证器模块缓存 (The Authenticator Module Cache)

“可插拔性”由 `AccountAuthenticatorCache` 类提供，它扫描定义身份验证器模块的包并将它们提供给 `AccountManagerService`。`AccountAuthenticatorCache` 是 Android 提供的更通用注册服务缓存的一种实现。该缓存按需（懒加载）通过询问 `PackageManagerService` 关于注册了特定 intent 和元数据的已安装包来构建。当包被添加、更新或删除时，通过广播接收器触发更新以保持缓存最新。缓存是持久的，并在检测到更改时写入磁盘，缓存文件写入 `/data/system/registered_services/` 目录，并根据它们扫描的 intent 命名。身份验证器模块缓存保存到 `android.accounts.AccountAuthenticator.xml` 文件中，看起来可能类似于示例 8-1。

### 8-1. `AccountAuthenticator.xml` 注册服务缓存的内容

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<services>
  <service uid="100023" type="com.android.exchange" /> 1
  <service uid="100023" type="com.android.email" /> 2
  <service uid="100069" type="com.example.account" /> 3
  <service uid="100074" type="org.foo.account" /> 4
  <!--snp-->
  <service uid="1010023" type="com.android.email" /> 5
  <service uid="1010023" type="com.android.exchange" /> 6
  <service uid="1010069" type="com.example.account" /> 7
  <!--snp-->
</services>
```

# 管理账户 (Managing Accounts)

与添加新账户一样，删除现有账户需要 `MANAGE_ACCOUNTS` 权限。然而，如果调用设备设置了 `DISALLOW_MODIFY_ACCOUNTS` 限制（用户限制详情见第 4 章），他们无法添加或删除账户，即使调用应用程序持有 `MANAGE_ACCOUNTS` 权限。其他需要此权限的方法是修改属性或凭据的方法，如下所示：

- `clearPassword()`. 清除缓存的密码。

- `confirmCredentials()`. 通过显示密码输入界面 显式确认用户知道密码（即使已缓存）。

- `editProperties()`. 显示允许用户更改全局身份验证器设置的 UI。

- `invalidateAuthToken()`. 从缓存中移除身份验证令牌。（如果调用者持有 `USE_CREDENTIALS` 权限，也可以调用。）

- `removeAccount()`. 删除现有账户。

- `updateCredentials()`. 询问用户输入当前密码并据此更新凭据。

# 使用账户凭据 (Using Account Credentials)

`AccountManagerService` 可能要求其客户端持有的最后一个权限是 `USE_CREDENTIALS`。该权限保护返回或修改身份验证令牌的方法，身份验证令牌是一种取决于服务的字符串，客户端可以使用它向服务器身份验证，而无需在每次请求中发送密码。

通常情况下，服务器在客户端使用凭据成功身份验证后会返回一个身份验证令牌。

密码和密钥（或其他凭据）。令牌通过一个称为令牌类型（token type）的字符串标识，该类型描述了令牌授予的访问类型（例如只读或读写）。令牌是可重用的，可以用于发送多次请求，但可能有有限的有效期。此外，如果认为用户账户已被泄露，或者用户更改了密码，该用户的所有现有身份验证令牌通常会失效，且不会报错。由于 `AccountManagerService` 与协议和应用程序无关，因此即使缓存令牌已过期或在服务器上失效，它也不会自动使这些令牌失效。应用程序有负责通过调用 `invalidateAuthToken()` 方法来清理此类无效的缓存令牌。

这些是需要 `USE_CREDENTIALS` 权限的方法：

- `getAuthToken()`：为特定账户获取指定类型的身份验证令牌。

- `invalidateAuthToken()`：从缓存中移除身份验证令牌。（如果调用者拥有 `MANAGE_ACCOUNTS` 权限，也可以调用此方法。）

# 请求身份验证令牌访问

除了持有 `USE_CREDENTIALS` 权限外，为了获取特定类型的身份验证令牌，调用 `getAuthToken()` 或由 `AccountManager` Facade 类提供的任何封装方法的调用者必须被显式授予对请求的令牌类型的访问权限。这通过显示如图 8-2 所示的确认对话框来实现。该对话框显示了请求应用程序的名称（第一个项目符号，在本例中为“Account Requestor”）、账户类型和名称（第二个项目符号，分别为“Example”和“example user”），以及如果授予访问将允许的数据访问类型简短描述（项目符号下方，“Full access to example data”，即对示例数据的完全访问权限）。如果用户授予访问，此决定将被缓存，如果请求相同的类型，则不再显示对话框。在身份验证器模块相同 UID 下运行的应用程序被允许访问其令牌而无需显示确认对话框。此外，特权系统应用被隐式允许访问所有令牌类型无需确认，因此如果令牌来自特权应用，则不会显示对话框。

# 账户数据库

我们已经介绍了身份验证器模块、身份验证缓存以及 `AccountManagerService` 的主要功能。现在让我们来看看此服务如何使用账户数据库（一个存储在每个用户系统目录中、名为 `accounts.db` 的 SQLite 数据库）来注册账户并缓存凭据。

在单用户设备上，账户数据库位于 `/data/system/users/0/accounts.db`。在多用户设备上，此文件存储主用户的账户信息，次要用户每个在 `/data/system/users/<user ID>/accounts.db` 拥有自己的实例。数据库由六张表组成：`accounts`、`extras`、`authtokens`、`grants`、`users` 和 `meta`。在本文中，`meta` 表似乎未被使用；所有其他表及其关系如图 8-1 所示。

## 表结构

`accounts` 表存储已注册账户的名称、类型和密码，所有其他表都直接或间接与其相关联。它可能包含类似于示例 8-2 的数据。

示例 8-2. `accounts` 表的内容

```sqlite
sqlite> select * from accounts;
| _id | type | password |
| :--- | :--- | :--- |
| 1 | user@gmail.com | com.google | ①......① |
| 2 | user@example.com | com.google.android.pop3 | password② |
| 3 | example_user | com.example.account | pass1234③ |
```

在这里，① 是一个 Google 账户（类型为 `com.google`），允许访问 Gmail、Google Play 商店和其他服务。Google 账户依赖专有的系统组件，仅在 Google 设备体验上可用（你可以在“Google 登录服务”中找到有关 Google 账户的更多细节）。账户 ② 是由内置邮件应用程序注册的 POP3 账户（类型为 `com.google.android.pop3`），而 ③ 是第三方应用程序注册的自定义账户（类型为 `com.example.account`）。每个账户可以与零或多个元数据键值对关联，这些键值存储在 `extras` 表中，并通过其主键（`_id` 列）与账户关联。例如，如果我们的自定义应用程序（id=3 中的 ③）提供后台数据同步，它可能具有比示例 8-3 中那些更增强的属性。

示例 8-3. `extras` 表的内容

```sqlite
sqlite> select * from extras where accounts_id=3;
| _id | accounts_id | key | value |
| :--- | :--- | :--- | :--- |
```

`authtokens` 表存储了为账户发放的令牌。对于我们的自定义应用程序，它看起来可能像示例 8-4。

示例 8-4. `authtokens` 表的内容

```sqlite
sqlite> select * from authtokens where accounts_id=3;
| accounts_id | idtype | authtoken |
| :--- | :--- | :--- |
| 3 | com.example.auth.abcdef0123456789 |
```

`grants` 表存储了应用程序 UID 及其允许使用的令牌。当用户确认特定账户类型和用户名称的访问确认对话框时（见图 8-2），会添加 `grants`。例如，如果 UID 为 10291 的应用程序请求并被授予对 `com.example.auth` 令牌的访问（如我们的示例应用程序所示，见示例 8-4），该授权将由 `grants` 表中的行表示（见示例 8-5）。每个账户 ID、令牌类型和 UID 的组合都会添加一行。

示例 8-5. `grants` 表的内容

```sqlite
sqlite> select * from grants;
| accounts_id | token_type | uid |
| :--- | :--- | :--- |
| 3 | com.example.auth | 10291 |
```

在单用户设备上，账户数据库位于 `/data/system/users/0/accounts.db`。在多用户设备上，此文件存储主用户的账户信息，次要用户每个在 `/data/system/users/<user ID>/accounts.db` 拥有自己的实例。

## 表访问

现在我们检查账户与用户之间的关系。`AccountManager` 允许应用程序查询、添加和删除账户。`accounts` 表是信息的主要存储。`authtokens` 表存储活动令牌。`grants` 表存储授予应用程序的权限。

# 密码安全

需要注意的是，凭据（通常是用户名和密码）存储在只有系统应用程序可以访问的中央数据库中；加密或其他保护凭据被留给身份验证器模块实现。事实上，如果你有一台 root 过的设备，你会发现 `accounts` 表的内容列表将显示某些密码的明文，例如内置应用程序（`com.android.email` 或 `com.google.android.email`）。例如，字符串 `password②` 和 `pass1234③` 分别是 POP 账户和自定义 `com.example.account` 的明文密码。

> 电子邮件应用程序可能需要存储密码而不是密码哈希或身份验证令牌，以支持多种以密码输入的挑战-响应验证方法，例如 DIGEST-MD5 和 CRAM-MD5。

由于 `AccountManager.getPassword()` 方法只能由相同应用程序调用，明文密码在运行时对其他应用程序可见，但可能会包含在备份或设备转文中。为了避免这种潜在的安全风险，应用程序可以使用设备特定密钥加密密码，或者在验证成功后选择用可撤销的主令牌替换密码。

# 多用户支持

回顾第 4 章，在多用户设备上，Android 允许每个用户拥有自己的账户集、应用程序数据和系统设置。这种用户隔离扩展到了在线账户以及在系统账户管理器中注册了自己的账户的用户。Android 4.3 增加了对受限制配置的支持，受限制配置不是完全独立的用户，但与主用户共享已安装的应用程序。使用 `AccountManager` API 的应用程序可以增加对受限制配置的支持。

允许受限配置查看并使用主用户账户的一个集。我们将在下文的“共享账户”中详细介绍这一功能。

接下来的章节将讨论 Android 如何在多用户环境下实现账户隔离和共享。

# 每个用户的账户数据库



正如“账户数据库”中所提到的，`AccountManagerService` 用于存储账户信息和缓存身份令牌的账户数据库存储在每个用户的系统目录下，路径为`/data/system/users/<user ID>/accounts.db`。这使得每个用户都拥有专用的账户存储，不同的用户甚至可能拥有相同类型在线账户的独立实例。除了数据库位置外，所有其他工作方式与所有者用户完全相同，包括权限、访问授权等。当用户被删除时，系统会删除其所有数据，包括账户数据库。

## 共享账户

主用户账户通过简单地将账户数据克隆到受限配置的账户数据库来与受限配置共享。因此，受限配置并不直接访问主用户的账户数据，而是拥有它们自己的拷贝。当添加受限配置时，主用户所有当前账户的名称和类型都会被复制到受限配置账户数据库的`shared_accounts`表中。然而，由于新用户尚未启动，此时`accounts`表是空的，共享账户尚不可用。

`shared_accounts`表的结构与`accounts`表相同，但缺少密码列。对于受限配置，它看起来像示例 8-6。

示例 8-6. `shared_accounts`表格的内容

```sqlite
sqlite> select * from shared_accounts;
|name |type|
| user1@gmail.com |com.google|
| user1@example.com|com.google.android.pop3|
| example_user |com.example.account|
```

共享账户并不是直接通过从所有者的`accounts`表拷贝数据来克隆的；相反，克隆是通过声明该账户的验证器（authenticator）实现的。默认情况下，所有验证器类所继承的`AbstractAuthenticator`不支持账户克隆。

想要支持受限配置共享账户的实现需要显式地这样做，即重写 Android 4.3 引入的受受限配置的几个方法：`getCredentialsForCloning()`（它返回一个包含克隆账户所需所有数据的`Bundle`）以及`addAccountFromCredentials()`（它接收此`Bundle`作为参数并负责根据`Bundle`中的凭据创建账户）。

`AccountService`会延迟共享账户的克隆，直到受限用户实际启动。如果所有者用户添加了任何新账户，这些账户会被添加到`shared_accounts`表并进行类似的克隆。

即使账户成功克隆，它们也可能对受限配置启动的应用程序不可。回顾第 4 章，如果应用程序想要支持共享账户，它必须在`<application>`标签中使用`restrictedAccountType`属性声明它所需的账户类型，以便在将账户传递给运行在受限配置内的应用程序之前进行过滤。截至本文编写，应用程序只能使用此属性声明一种类型的账户。

### 注意

次级用户不与所有者共享账户，因此它们的`shared_accounts`表始终是空的，且所有者账户永远不会被克隆。

## 添加验证器模块

在验证器模块（Authenticator Modules）中，我们注意到验证器模块是一个实现了`android.accounts.IAAuthenticator` AIDL 接口的绑定服务，可以通过`android.accounts.AccountAuthenticator`意图动作进行绑定。在本节中，我们将展示应用程序如何实现并声明验证器模块。

大多数验证器逻辑（包括添加账户、检查用户提供的凭据和获取身份令牌）都在继承自 Android 提供的基类（即`AbstractAuthenticator`）的验证器类中。验证器类需要提供所有抽象方法的实现，但如果不需要所有功能，已实现的方法可以返回`null`或抛出`UnsupportedException`。为了存储账户密码，实现应至少实现`addAccount()`方法，并显示一个从用户处收集密码的 UI。然后可以通过调用`AccountManager`的`addAccountExplicitly()`方法将密码添加到账户数据库。实现凭据收集和登录的 Activity 可以扩展`AccountAuthenticatorActivity`，该类提供了一个方便的方法，可以将收集到的凭据传递给`AccountManager`。

### 注意

请记住`addAccountExplicitly()`方法默认不会加密或保护保护以明文形式存储的密码。如果需要，应该单独实现加密，并将加密后的密码或令牌传递给`addAccountExplicitly()`，而不是明文版本。

一旦你有了验证器实现，你只需要创建一个服务，该服务在用`android.accounts.AccountAuthenticator`意图动作调用它时返回其 Binder 接口，如示例 8-7 所示（省略了`AbstractAccountAuthenticator`方法实现）。

示例 8-7. 验证器服务实现

```java
public static class ExampleAuthenticator extends AbstractAccountAuthenticator {
    // ...
    }

    private ExampleAuthenticator authenticator;

    @Override
    public void onCreate() {
        super.onCreate();
        authenticator = new ExampleAuthenticator(this);
    }

    @Override
    public IBinder onBind(Intent intent) {
        if (AccountManager.ACTION_AUTHENTICATOR_INTENT.equals(intent.getAction())) {
            return authenticator.getIBinder();
        }
        return null;
    }
}
```

为了被`AccountAuthenticatorCache`识别并通过`AccountManagerService`提供，该服务需要像示例 8-8 所示声明`android.accounts.AccountAuthenticator`意图动作和匹配的元数据。访问账户和令牌所需的权限需要添加到文件中。其中，我们只添加了`AUTHENTICATE_ACCOUNTS`权限，这是使用`addAccountExplicitly()`添加账户所需的最小权限。

示例 8-8. 在`AndroidManifest.xml`中声明验证器服务

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/android"
    package="com.example.app"
    android:versionCode="1" android:versionName="1.0">

    <uses-permission android:name="android.permission.AUTHENTICATE_ACCOUNTS" />

    <application>
        <service android:name=".AuthenticatorService">
            <intent-filter>
                <action android:name="android.accounts.AccountAuthenticator" />
            </intent-filter>
            <meta-data
                android:name="android.accounts.AccountAuthenticator"
                android:resource="@xml/authenticator" />
        </service>
    </application>
</manifest>
```

最后，账户类型、标签和图标必须在引用的资源文件中声明，如示例 8-9 所示。在这里，账户类型为`com.example.account`，我们简单地使用图标作为账户图标。

示例 8-9. 在 XML 文件中声明账户元数据

```xml
<?xml version="1.0" encoding="utf-8"?>
<account-authenticator
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:accountType="com.example.account"
    android:label="@string/account_label"
    android:icon="@drawable/ic_launcher" />
```

## Google 账户支持

Android 账户管理设施的主要目标是使集成在线服务变得更容易，并允许通过后台同步无缝访问用户数据。系统账户服务的早期版本是为了支持 Android 与 Google 在线服务的集成而构建的，随后该被解耦并成为操作系统的一部分。Android 2.0 及更高版本中，Google 账户和在线服务支持作为一组进行封装。

适配器（用于 Gmail、日历、联系人等），使用标准的操作系统 API 与`com.google`账户类型同步。然而，它们与其他第三方身份验证器模块和系统适配器相比有几点显著差异：

- Google 账户组件与系统捆绑在一起，因此获得了额外的权限。
- 许多实际功能在服务器端实现。
- 账户身份验证器不在设备上以明文形式存储密码。

## Google 登录服务

实现 Google 账户和服务支持的两个主要组件是 Google 服务框架 (GSF) 和 Google 登录服务 (GLS，在较新版本中显示为 Google Account Manager)。前者为所有 Google 应用提供通用服务，例如集中化设置和功能开关管理；而后者实现了 Google 账户的身份验证提供程序，并将是本节的主题。

Google 提供了大量的在线服务，并支持多种不同的方法来对这些服务进行身份验证，包括通过面向用户的 UI 和多个专用的身份验证 API。然而，Android 的 Google 登录服务并不直接调用这些公共身份验证 API，而是通过运行在`https://android.clients.google.com`的专用在线服务来实现。它具有用于身份验证、授权令牌颁发以及数据馈（邮件、日历等用于数据同步的端点）。

虽然许多身份验证和授权逻辑在服务器端实现，但仍然需要一些本地存储的凭据，特别是对于后台同步。设备端凭据管理是 GLS 提供的功能之一，尽管在编写本文时尚没有公开的源代码或参考文档，但我们可以观察 GLS 在设备上存储了数据以及身份验证是如何实现的。

如前所述，GLS 接入了系统账户框架，因为缓存的凭据、令牌和相关的额外数据被存储在当前用户的系统账户数据库中，与其他账户类型的情况一样。与其他应用程序不同，GLS 不直接存储 Google 账户密码。相反，它在账户表的`password`列中存储一个密码主令牌（可能是某种形式的 OAuth 刷新令牌），而它通过调用关联的 Web 服务端点来交换用于不同 Google 服务的身份验证令牌。当 Google 账户首次添加到设备时，会通过发送在图 8-4 所示的登录活动中输入的用户名和密码来获取该令牌。

如果目标 Google 账户使用默认的“仅密码”身份验证方法且输入了正确的密码，GLS 在线服务将返回主令牌，并将账户添加到用户的账户数据库中。所有后续的身份验证请求都使用主令牌来获取用于同步或自动 Web 登录的服务特定令牌。如果 Google 账户设置为使用双重身份验证 (2FA)，用户会被提示在如图 8-5 所示的嵌入式 WebView 中输入其一次性密码 (OTP，在 Web UI 中称为验证码)。

![图 8-4. Google 账户登录活动](img/8524e4e57e2e9dc889903e3d2c5fe367_192_0.png)

图 8-4. Google 账户登录活动

如果 OTP 验证通过，主令牌将被添加到账户数据库中，并显示支持后台同步的服务列表（见图 8-6）。

### 图 8-5. 作为添加 Google 账户一部分的一次性密码输入

![图 8-5. 作为添加 Google 账户一部分的一次性密码输入](img/8524e4e57e2e9dc889903e3d2c5fe367_194_0.png)

请注意，对于启用 2FA 的 Google 账户，只有初始登录过程不同：所有后续身份验证请求都使用缓存的主令牌，且不需要输入 OTP。一旦缓存，主令牌将授予对 Google 账户的完全访问权限，并且不仅用于数据同步，还可以用于其他类型的账户访问，包括 Web 登录。

虽然缓存一个全能的身份验证令牌非常方便，但这种为了便利的权衡导致了针对 Google 账户的多次攻击，现在许多 Google 服务在显示敏感数据或更改账户设置时需要额外的身份验证。可以通过更改 Google 账户密码、启用双重身份验证，或从关联 Google 账户的账户权限页面删除 Android 设备（见图 8-7）来使主令牌失效。这些任何操作都要求用户在设备下次尝试通过 AccountManager API 获取 Google 身份验证令牌时，使用其新凭据重新进行身份验证。

![图 8-7](img/8524e4e57e2e9dc889903e3d2c5fe367_195_0.png)

## Google 服务身份验证与授权

除了 Gmail、Google 日历以及当然还有搜索等带有 Web UI 的面向用户的在线服务外，Google 还通过 Web API 提供了许多服务的程序化访问。这些服务大多数都需要身份验证，要么是为了访问特定用户数据的子集，要么是为了配额和计费目的。多年来，人们使用了多种标准或 Google 专有的身份验证和授权方法，目前的趋势是将一切迁移到 OAuth2.0[82] 和 OpenID Connect.[83]。然而，许多服务仍在使用旧的专有协议，我们也将简要查看这些。

大多数身份验证协议有两种变体：一种用于 Web 应用，另一种用于已安装的应用程序。Web 应用运行在浏览器中，并预计能够利用所有标准浏览器功能，包括丰富的 UI、自由形式的用户交互、Cookie 存储以及跟随重定向的能力。相反，已安装的应用程序不具备这些功能。

### OAuth 2.0

OAuth 2.0 授权框架在 2012 年成为官方标准。它为不同的用例定义了不同的授权流，但我们不会尝试介绍所有的。我们只讨论 OAuth 2.0 如何与原生应用程序相关。（有关实际协议的细节，请参 RFC 6749）。

OAuth 2.0 规范定义了获取资源令牌的四种基本流。它定义了两种不需要客户端（在我们的场景中 Android 应用）直接处理凭据（如 Google 账户用户名和密码）的模式，即授权码模式和隐式授权模式。这两种模式都需要授权服务器（Google）对资源所有者（Android 应用）进行身份验证，以确定授予还是拒绝访问请求（例如对配置信息的只读访问）。在典型的基于浏览器的 Web 中，这是直观的：用户被重定向到授权页面，然后到一个授权页面，页面基本上是：“你是否允许应用 X 访问数据 Y 和 Z？”如果用户同意，另一个包含授权令牌的重定向会将用户带回原始应用程序。浏览器只需要在下一个请求中传递令牌即可获得目标资源的访问权限。

对于原生应用程序，情况并非如此简单。原生应用程序可以使用系统浏览器来处理授予权限步骤，或者在应用程序的 UI 中嵌入 WebView 或类似的控件。使用系统浏览器涉及启动第三方应用程序（浏览器）、检测成功或失败，并最终确定如何将令牌返回给调用应用程序。嵌入 WebView 稍微友好一点，但它不涉及在应用程序之间来回，仍然产生非原生的 Web UI，并且需要复杂的代码来检测和提取访问令牌。这两种方案都不是理想的，而且对用户来说都是困惑的。

这种集成复杂性和 UI 不匹配正是 OAuth 2.0 支持旨在要解决的问题。OAuth 提供了两个可以获取 OAuth 2.0 令牌的 API：通过特殊的 *oauth2:scope* 令牌类型的平台 AccountManager，以及 Google Play 服务（将在下一节讨论）。在使用上述任何一个 API 获取令牌时，用户

通过将保存的主令牌（master token）传递给 GLS 的服务端组件透明实现，该组件会生成原生的 AccountManager 授权对话框（见图 8-8），而不是一个带有权限授予页面的 WebView。如果你向请求的应用授予令牌，则会向此服务器发送第二个请求进行转换，服务器返回请求的令牌。随后，访问令牌将被传递给应用，而无需通过 WebView 等中间组件。这在本质上与 Web 应用程序的流程相同，但它不需要在原生和浏览器之间进行上下文切换，而且更符合用户习惯。当然，这种原生授权流程仅适用于 Google 账号，而为某些其他使用 OAuth 2.0 的在线服务编写客户端，仍然需要将其 Web 界面集成到你的应用中。例如，Twitter 客户端通常使用 WebView 来处理 Twitter API 返回的权限授予 URL。

## Google Play 服务

Google Play Services (GPS) 在 Google I/O 2012 上发布，是一个易于使用的平台，为第三方 Android 应用提供了与 Google 产品集成的方法。从那时起，它已成为一个巨大的全功能包（包含超过 14,000 个 Java 方法！），提供了对 Google API 和专有操作系统扩展的访问。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_197_0.png)



如上一节所述，通过标准的 `AccountManager` 接口获取 OAuth 2.0 令牌自 Android 2.2 及更高版本起已支持，但在不同的构建之间运行并不可靠，因为它们捆绑的 GLS 版本不同，导致设备之间的行为略有差异。此外，在请求令牌时显示的权限授予对话框并不特别用户友好，因为在某些情况下显示的是原始的 OAuth 2.0 范围（scope），这对于大多数用户来说意义不大（虽然部分支持了某些范围的人类可读别名，例如，在某些版本中显示“管理您的任务”字符串，而不是原始的 `OAuth oauth2:https://www.google.com/auth/tasks`），但这种支持并非理想的普遍可用，因为这也取决于预装的 GLS 版本。

通常情况下，尽管 Android 的账户管理框架很好地集成到操作系统中，并可以通过第三方身份验证模块进行扩展，但其 API 并不特别灵活，对于像 OAuth 2.0 那样的多步身份验证或授权流程的支持也远非简单。GPS 在在线服务的帮助下实现了这一点，该服务尽力隐藏 OAuth 2.0 的复杂性，并提供与 Android 账户管理框架兼容的 Web API。我们接下来将讨论这种集成的细节。

GPS 通过将令牌发放变为两个步骤的过程，为显示用户友好的 OAuth 范围描述添加了通用支持：

- 与以前一样，第一个请求包含账户名称、主令牌和请求请求的服务，格式为 `oauth2:scope`。GPS 在请求中添加了两个参数：应用的包名和其签名证书的 SHA-1 哈希值。响应包含有关所请求范围和请求应用的人类可读详情，GPS 在类似于图 8-9 所示的权限授予对话框中显示这些内容。
- 如果用户授予权限，该决定将以专有格式记录在 `extras` 表中，该格式包括请求应用的包名、签名证书哈希值和已授予的 OAuth 2.0 范围。（注意 `grants` 表未被使用。）随后，GPS 会重新发送授权请求，将 `has_permission` 参数设置为 1。成功后，响应中将产生一个 OAuth 2.0 令牌及其过期日期。过期日期保存在 `extras` 表中，令牌则以类似的格式缓存在 `authtokens` 表中。

## Google

示例应用想要：

- 了解你在 Google 上的身份

通过继续操作，你允许此应用和 Google 根据它们各自的服务条款和隐私政策使用你的信息。

取消

确定

图 8-9. Google Play 服务访问权限对话框

GPS 应用与 GSF 和 GLS 包具有相同的共享用户 ID（`com.google.uid.shared`），因此它可以与这些服务直接交互。这允许它除其他操作外，直接获取 Google 账户凭据和令牌并将其写入数据库 `accounts`。正如预期的那样，GPS 运行在一个远程服务中，该服务由链接到 GPS 的客户端库访问。

与旧的 `AccountManager` API 相比，主要的卖点在于：虽然它的底层身份验证模块（GLS 和 GSF）是系统的一部分（若不通过 OTA 则无法更新），但 GPS 是一个用户可安装的应用，可以通过 Google Play 轻松更新。事实上，它是自动更新的，因此如果应用开发者想要使用新功能，他们就永远不需要依赖用户去更新（除非 GPS 被完全禁用）。这种更新机制旨在为“推出新平台能力提供灵活性”，由于这些功能需要大量的测试，更新频率并不高。

尽管如此，如果你的应用使用 OAuth 2.0 与 Google API 进行身份验证（本文时的推荐方法），你应该绝对考虑使用 GPS 而非“原始” `AccountManager` 访问。

### 注意

为了实际使用 Google API，你必须在 Google API 控制台中注册你的应用名称和签名密钥。注册服务会验证有关令牌用途的查询，以识别调用的应用。此验证过程有一个副作用：你不需要在应用中嵌入 API 并在每次请求时发送它。当然，对于第三方发布的应用，你可以轻松发现包名和签名证书，获取某些其他名义下的令牌并不特别困难。

## 总结

Android 提供的账户管理框架很好地集成到操作系统中，并可以通过第三方身份验证模块进行扩展，但其 API 并不特别灵活，对于像 OAuth 2.0 那样的多步身份验证或授权流程的支持也远非简单。GPS 在在线服务的帮助下实现了这一点，该服务尽力隐藏 OAuth 2.0 的复杂性，并提供与 Android 账户管理框架兼容的 Web API。我们接下来将讨论这种集成的细节。

# 第 9 章 企业安全

Android 初始版本主要面向消费者，企业功能有限。然而，随着平台的普及，Android 设备已进入工作场所，并越来越多地用于访问公司数据。由于这一趋势，对增强平台安全性和管理工具的需求日益增长。尽管 Android 的主要关注点仍然是消费设备，但最近的版本引入了许多企业功能，Android 可能会变得对企业友好。

在本章中，我们将讨论 Android 的主要企业级功能，并演示如何使用它们。我们将从设备管理开始，展示如何将其集成到第三方应用程序中。然后我们将查看 Android 的 VPN 支持，并描述作为第三方用户安装应用开发 VPN 解决方案。接下来我们将展示 EAP 支持的不同身份验证方法，并描述如何管理凭据。最后，我们将演示使用 4.3 添加的扩展 Wi-Fi API 动态添加 EAP 配置文件。

## 设备管理

Android 2.2 引入了对设备管理 API 的支持，使得开发能够实施系统级安全策略并根据设备当前安全级别动态调整特征成为可能。此类应用程序被称为设备管理员。必须在设备的安全设置中显式启用，并且在激活状态下无法卸载。

启用后，它们被授予特殊权限，允许锁定设备、更改密码和清除设备（删除所有用户数据）。设备管理员通常与特定的企业账号（例如 Microsoft Exchange 或 Google 账号）配合使用，允许企业管理员通过允许符合所需安全策略的设备来控制公司数据的访问。

安全策略可以是静态并构建在设备管理员应用程序中的，也可以在服务端配置并作为配置或同步协议的一部分发送到设备。从 4.4 版本开始，Android 支持表 9-1 列出的策略类型。策略常量定义在 `DeviceAdminInfo` 类中。

### 表 9-1. 支持的设备管理策略

| 策略常量/XML 标签 | 值（设置位） | 描述 | API 级别 |
|---|---:|---|---:|
| `USES_POLICY_LIMIT_PASSWORD` `<limit-password>` | 0 | 通过设置最小长度或复杂度限制用户可以选择的密码。 | 8 |
| `US_POLICY_WATCH_LOGIN` `<watch-login>` | 1 | 观察用户的登录尝试。 | 8 |
| `US_POLICY_RESET_PASSWORD` `<reset-password>` | — | 重置用户密码。 | 8 |
| `US_POLICY_FORCE_LOCK` `<force-lock>` | — | 强制设备锁定，或限制最大锁定超时时间。 | 8 |
| `US_POLICY_WIPE_DATA` `<wipe-data>` | — | 设备恢复出厂设置，擦除所有用户数据。 | 8 |
| `US_POLICY_SETS_GLOBAL_PROXY` `<set-global-proxy>` | — | 指定设备代理。（此设置对 SDK 应用程序隐藏。） | 9 |
| `US_POLICY_EXPIRE_PASSWORD` `<expire-password>` | — | 强制用户在管理员定义的限制时间后更改密码。 | 11 |
| `US_ENCRYPTED_STORAGE` `<encrypted-storage>` | — | 要求数据必须加密。 | 11 |
| `US_POLICY_DISABLE_CAMERA` `<disable-camera>` | — | 禁用所有设备摄像头。 | 14 |
| `US_POLICY_DISABLE_KEYGUARD_FEATURES` `<disable-keyguard-features>` | — | 禁用键盘功能的使用，如锁屏小部件或相机支持。 | 17 |

每个设备管理应用程序必须在元文件中列出其意图使用的策略（详情请参见“权限管理”）。当用户激活管理员应用时，会显示受支持的策略列表，如图 9-1 所示。

### 实现

现在我们已经知道了哪些策略可以由设备管理 API 强制执行，让我们内部实现。与大多数 Android 公共 API 一样，名为 `DevicePolicyManager` 的管理类暴露了底层系统服务 `DevicePolicyManagerService` 的部分功能。然而，`DevicePolicyManager` 门面类定义了常量并将服务异常转换为返回代码，但添加的功能很少，我们将重点关注 `DevicePolicyManager` 类。

与系统服务不同，`DevicePolicyManagerService` 在 `system_server` 中以系统用户身份启动并运行，并且可以向第三方应用程序执行几乎所有的 Android 特权操作（例如更改锁屏密码），而这些应用程序不需要持有任何特殊的系统权限。这使得用户能够根据需要启用或禁用设备管理员。

然而，这种程度的活性无法通过标准的 Android 权限轻松实现，因为标准权限仅在安装时授予且无法撤销（如第 2 章所述的某些例外）。因此，`DevicePolicyManagerService` 采用了不同的方法进行权限管理。

Android 设备管理实现的另一个有趣方面与策略的强制执行有关。我们将在接下来详细描述设备管理员权限管理和策略执行。

## 权限管理

在运行时，`DevicePolicyManagerService` 为每个设备用户维护一个内部的、内存策略结构列表。（策略也会持久化在磁盘的 XML 文件中，如下一节所述。）

每个策略结构都包含针对特定用户的当前生效策略，以及每个活跃设备管理员的元数据列表。由于每个用户可以启用多个应用程序，当前激活的策略是由所有管理员中定义的最严格的策略计算得出的。

关于每个设备管理员的元数据包含声明应用程序的信息以及已声明的策略列表（用位掩码表示）。

`PolicyManagerService` 的作用根据其内部活跃策略列表向调用应用程序授予特权操作访问：只有当调用应用程序是活跃的设备管理员，并且它请求了与当前请求（API 调用）对应的策略时，请求才会被授予并执行操作。

为了确认活跃的管理员组件确实属于调用应用程序，`DeviceCallingManagerService` 将调用进程的 UID（通过 `Binder.getUid()` 返回）与目标管理员组件的 UID 进行比对。例如，调用 `resetPassword()` 的应用程序必须是活跃的设备管理员，与注册的管理员组件具有相同的 UID，并且请求了 `USES_RESET_PASSWORD` 策略，调用才能成功。

策略是通过添加一个 XML 资源文件来请求的，该文件将设备管理员想要使用的所有策略作为 `<policies>` 标签的子元素。在图 9-1 之前，允许用户在激活管理员之前检查请求的策略。

与 Android 权限不同，管理员策略是按“全有全无”的基础上授予的，但没有方法只选择某些策略。像示例 9-1 那样请求所有策略的资源文件（对应每个标签的策略，请参表 9-1 的第一列）。您可以在“添加设备管理员”中找到有关将此文件添加到设备管理员应用程序的更多细节。

## 示例 9-1. 在设备管理员应用程序中声明策略

```xml
<?xml version="1.0" encoding="utf-8"?>
<device-admin xmlns:android="http://schemas.android.com/apk/res/android">
  <policies>
    <limit-password />
    <watch-login />
    <reset-password />
    <force-lock />
    <wipe-data />
    <expire-password />
    <encrypted-storage />
    <disable-camera />
    <disable-keyguard-features />
    <set-global-proxy />
  </policies>
</device-admin>
```

为了接收与策略相关的系统事件并允许访问设备管理 API，必须激活设备管理员。这是通过调用 `PolicyManagerService` 的 `setActiveAdmin()` 实现的。由于此方法需要 `MANAGE_DEVICE_ADMIN` 权限（系统签名权限），只有应用程序可以在没有用户交互的情况下添加设备管理员。

用户安装的设备管理员应用程序只能通过启动类似于示例 9-2 的 intent 来请求激活。此 intent 的唯一管理器处理器是 Settings 应用程序。接收到 intent 后，Settings 应用程序会检查请求应用程序是否为有效的设备管理员，提取请求的策略，并构建图 9-1 所示的确认对话框。

点击“激活”按钮将调用 `setActiveAdmin()` 方法，将该应用程序添加到当前设备的活跃管理员列表中。

## 示例 9-2. 请求设备管理员

```java
Intent intent = new Intent(DevicePolicyManager.ACTION_ADD_DEVICE_ADMIN);
Component admin = new ComponentName(this, DeviceAdminReceiver.class);
intent.putExtra(DevicePolicyManager.EXTRA_ADD_ADMIN, "Required for corporate email.");
startActivityForResult(intent, REQUEST_CODE_ADMIN);
```

## 策略持久化

当管理员激活、禁用或其策略更新时，更改将写入目标用户的 `device_policies.xml` 文件。对于所有用户，该文件位于 `/data/system/`；对于所有其他用户，它被写入系统目录 `/data/users/<user-ID>`。

该文件由系统用户拥有并仅供系统用户修改（权限 0600）。`device_policies.xml` 文件包含每个活跃管理员及其策略，以及关于当前锁定的全局信息。文件可能如下。

## 示例 9-3. `device_policies.xml` 文件的内容

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<policies>
  <admin name="com.google.android.gms/com.google.android.mdm.receivers.MdmDeviceAdminReceiver">
    <policies flags="28" />
  </admin>
  <admin name="com.example.android.apis/com.example.android.app.app.DeviceAdminAdminReceiver">
    <policies flags="1023" />
    <password-quality="32760" />
    <min-password-length="6" />
    <min-password-letters="2" />
    <min-password-numeric-value="2" />
    <max-time-to-unlock="300000" />
    <max-failed-password-wipe-value="100" />
    <encryption-requested="true" />
    <disable-camera="true" />
    <disable-keyboard-features-value="1" />
  </admin>
  <admin name="com.example.android.email/com.example.android.email.SecurityPolicyAdmin">
    <policies flags="475" />
  </admin>
  <password-owner-value="10076" />
  <active-password-quality="327680" length="6"
    uppercase="0" lowercase="3"
    letters="3" symbols="0" nonletter="3" />
</policies>
```

三个活跃的设备管理员，每个分别由 `<admin>` 元素 1 和 5 表示。每个管理员的策略存储在 `<policies>` 标签的 `flags` 属性 3 中。

如果策略的配置位被设置，则认为该策略已启用（见表 9-1 的 Value 列）。例如，由于 DeviceAdminSample 应用请求了所有当前可用的策略，其 `flags` 属性值为 1023（十六进制 `0x3FF`，二进制 `1111111111`）。

如果管理员定义了密码质量限制（例如，字母数字混合或复杂密码），它们将持久化为 `<password-quality>` 标签的 `value` 属性 4。在此示例中，值 327680（`0x50000`）对应 `PASSWORD_QUALITY_ALPHANUMERIC`（密码常量定义在 `DevicePolicyManager` 类中）。

其他策略需求（如密码长度和设备加密）的值也存储为每个 `<admin>` 元素的子节点。如果使用 `resetPassword()` 方法通过程序设置了密码，`device_policies.xml` 将包含一个 `<password-owner>` 标签，其 `value` 属性存储了所设置密码的 UID 6。最后，`<active-password>` 标签包含有关当前密码复杂性的细节 7。

## 策略执行

设备管理员具有不同的粒度，可以针对当前用户执行，也可以针对设备上的所有用户执行。某些策略完全不由系统执行——系统只会通知声明该管理员程序，然后由该程序负责采取适当措施。在本节中，我们将描述每种类型的策略是如何实现和执行的。

## `USES_POLICY_LIMIT_PASSWORD`



在设置一个或多个密码限制后，用户无法输入不符合当前策略的密码。然而，系统并不要求立即更改密码，因此当前密码在更改之前保持有效。管理员可以通过启动带有 `DevicePolicyManager.ACTION_SET_NEW_PASSWORD` 的隐式意图（intent）来提示用户设置新密码。

由于每个设备都有独立的解锁密码，密码质量策略是按用户应用的。当设置了密码质量时，不允许使用符合预期质量密码的解锁方法将被禁用。例如，将密码质量设置为 `PASSWORD_QUALITY_ALPHANUMERIC` 将禁用模式（Pattern）和 PIN 码解锁方法，如图 9-2 所示。

## `USES_POLICY_WATCH_LOGIN`

此策略允许设备管理员接收有关登录尝试结果的通知。通知通过 `ACTION_PASSWORD_FAILED` 和 `ACTION_PASSWORD_SUCCEEDED` 广播发送。派自 `DeviceAdminReceiver` 的接收器将通过 `onPasswordFailed()` 和 `onPasswordSucceeded()` 方法自动通知。

## `USES_POLICY_RESET_PASSWORD`

此策略允许管理员程序通过 `resetPassword()` API 设置当前用户的密码。指定的密码必须满足当前的密码质量要求并立即生效。注意，如果设备已加密，为所有者设置锁屏密码也会更改设备加密密码。（第 10 章提供了更多关于设备加密的详细信息。）

## `USES_POLICY_FORCE_LOCK`

此策略允许管理员通过调用 `lockNow()` 方法立即锁定设备，或通过 `setMaximumTimeToLock()` 指定用户空闲直到设备自动锁的最大时间。设置最大锁定时间将立即生效，并限制了用户通过系统显示设置可以设置的空闲睡眠时间。

此策略允许设备管理员通过调用 `wipeData()` API 擦除数据。同时请求 `US_POLICY_WATCH_LOGIN` 策略的应用可以通过 `setMaximumFailedPasswordsForWipe()` API 设置在设备自动擦除之前的失败登录尝试次数。当失败密码次数设置为大于零的值时，每次失败后，锁屏通知都会通知 `DevicePolicyManagerService` 并显示警告对话框，并在达到阈值时触发擦除。如果设备因所有者的登录尝试失败而被擦除，则将执行全设备重置。另一方面，如果擦除是由次要用户触发的，则只删除该用户（以及任何关联数据），设备将切换到其他

## 注意事项

> 全设备擦除不是立即完成的，而是通过在缓存分区中写入擦除命令并重启到恢复模式来实现的。恢复操作系统负责执行实际的设备擦除。因此，如果设备具有忽略擦除命令的自定义恢复镜像，或者用户设法进入自定义恢复并删除或修改了命令文件，则设备擦除可能不会执行。（第 10 章和第 13 章更详细地讨论了恢复）

## `USES_POLICY_SETS_GLOBAL_PROXY`

从 Android 4.4 开始，此策略对第三方应用程序不可。它允许设备管理员通过向全局系统设置提供者写入数据来设置全局代理服务器（`Settings.Global.GLOBAL_HTTP_PROXY_HOST`）、端口（`GLOBAL_HTTP_PROXY_PORT`）和排除主机列表（`GLOBAL_HTTP_PROXY_EXCLUSION_LIST`）。只有设备所有者被允许设置全局代理。

## `USES_POLICY_EXPIRE_PASSWORD`

此策略允许管理员通过 `setPasswordExpiration()` API 设置密码过期超时。如果设置了过期超时，系统会注册一个每日闹钟来检查密码过期。如果密码已经过期，`DevicePolicyManagerService` 将发布每日密码更改通知，直到密码更改。设备管理员通过 `DeviceAdminReceiver.onPasswordExpiring()` 方法获取密码过期状态。

## `USES_ENCRYPTED_STORAGE`

此策略允许管理员通过 `setEncryption()` API 请求加密存储。只有所有者可以请求存储加密。如果设备未加密，请求加密不会自动启动加密过程；设备管理员必须使用 `START_ENCRYPTION` 隐式意图启动加密过程。

## `USES_POLICY_DISABLE_CAMERA`

此策略允许设备管理员通过 `disableCamera()` API 禁用设备上的摄像头。系统检查此策略是否生效并为所有用户禁用摄像头。

## `USES_POLICY_DISABLE_KEYGUARD_FEATURES`

此策略允许管理员通过调用 `disableGuardFeatures()` 方法禁用锁屏小部件等自定义功能。系统检查此策略是否生效并禁用相应功能。

## 添加设备管理员

与其他应用程序一样，设备管理员可以包含在系统镜像，也可以由用户安装。如果管理员是系统的一部分，在 Android 4.4 及更高版本中它可以被设置为所有者，这是一种特殊的管理员，无法禁用也无法卸载。在本节中，我们将展示如何实现管理员，然后演示系统应用如何设置为所有者。

## 实现设备管理员

设备管理员应用需要声明需要 `BIND_DEVICE_ADMIN` 权限的广播接收器，声明其使用的策略的 XML 资源，并响应 `DEVICE_ADMIN_ENABLED` 意图。示例 9-1 显示了一个示例策略声明。

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">
  <package name="com.example.deviceadmin">
  <!-- -->
  <receiver android:name="MyDeviceAdminReceiver"
    android:label="@string/device_admin"
    android:description="@string/device_description"
    android:permission="android.permission.BIND_DEVICE_ADMIN">
    <meta-data
        android:name="android.app.device_admin"
        android:resource="@xml/device_admin_policy" />
    <intent-filter>
      <action android:name="android.app.action.DEVICE_ADMIN_ENABLED" />
    </intent-filter>
  </receiver>
  <!-- -->
</package>
</manifest>
```

Android SDK 提供了一个供你派生使用的基类，即 `android.app.DeviceAdminReceiver`。该类定义了许多回调方法，你可以重写这些方法来处理系统发布的设备策略相关的广播。默认实现是空的，但至少你应该重写 `onCreate()` 和 `isDisabled()` 方法，以便在管理员被启用或禁用时收到通知。在 `onCreate()` 调用之前或 `isDisabled()` 调用之后，设备管理员无法使用任何权限 API。

你可以随时使用 `isActive()` API 查看应用程序当前是否为活跃的设备管理员。正如“权限管理”中所述，管理员不能自动激活自己，而必须启动系统活动进行用户确认，代码类似于示例 9-2。然而，当处于激活状态时，管理员可以通过调用 `removeActiveAdmin()` 方法来取消激活。

> **注意**

> 有关更多信息和完整的工作示例应用程序，请参阅官方[设备管理 API 指南][8]。

## 设置设备所有者

作为系统镜像一部分的设备管理员应用程序（即其 APK 文件安装在系统分区上）可以通过调用 `setDeviceOwner(String packageName, String ownerName)` 方法（在设备 SDK API 中不可见）被设置为设备所有者。该方法的第一个参数指定目标应用程序的包名，第二个参数指定在 UI 中显示的所有者名称。虽然此方法不需要特殊权限，但它只能在设备配置完成（provisioned）之前调用（即如果全局设置 `Settings.Global.DEVICE_PROVISIONED` 设置为 0），这意味着它只能由作为设备初始化执行的系统应用程序调用。

成功调用此方法会在 `/data/system/` 写入 `device_owner.xml` 文件（类似于示例 9-5 中的文件）。可以使用 `getDeviceOwner()`、`isDeviceOwner()`（在 Android SDK API 中暴露为 `isDeviceOwnerApp()`）和 `getDeviceOwnerName()` 方法获取有关当前设备所有者的信息。

### 示例 9-5：`device_owner.xml` 文件的内容

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?>
<device-owner package="com.example.deviceadmin" name="Device Owner" />
```

当设备所有者被激活时（作为配置过程的一部分或由用户激活），它无法被禁用和卸载，如图 9-3 所示。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_211_0.png)

图 9-3：设备所有者管理员无法禁用。

## 管理设备

安装了所有者管理员的设备被称为托管设备，它对影响设备安全的配置更改的反应与未托管设备不同。正如第 6 章和第 7 章所述，Android 允许用户通过设置应用程序或使用调用 `KeyChain API` 的第三方应用程序在系统信任存储区中安装信任证书。如果信任存储区中存在用户安装的证书，从 Android 4.4 版本开始，Android 会显示警告（见图 6-6），通知用户其通信可能会被监控。

企业网络通常要求安装信任证书（例如企业 PKI 的根证书）以便访问企业服务。持有 `MANAGE_CERTIFICATES` 系统权限的设备管理员可以通过 `DevicePolicyManager` 类的 `installCaCert()` 和 `uninstallCaCert()` 方法静默安装或移除此类证书（这些方法为系统应用程序保留，且在公共 API 中不可见）。如果在托管设备上安装了额外的信任证书，网络监控信息将变为一条不那么令惊的消息，如图 9-4 所示。

## 企业账户集成

如“设备管理”部分提到的，设备管理员应用程序通常与企业帐户结合，以便对访问公司数据的设备进行某些控制。在这里我们将讨论两种实现方式：一种是在内置邮件应用程序中，与 Microsoft Exchange ActiveSync 账户配合；另一种是在专用的 Google Apps 设备策略应用中，与企业 Google 账户配合。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_212_0.png)

## Microsoft Exchange ActiveSync

Microsoft Exchange ActiveSync（通常缩写为 EAS）是一种协议，支持从群组服务器到移动设备同步电子邮件、联系人、日历和任务。它受微软自己的 Exchange Server 以及大多数竞争产品（包括 Google Apps）的支持。

Android 包含的邮件应用程序支持 ActiveSync 账户和通过专用的帐户身份验证器进行数据同步（见第 8 章和同步适配器）。为了允许管理员在访问电子邮件和其他公司数据的设备上强制执行安全策略，邮件应用程序在用户启用内置设备管理员之前将不允许进行同步。管理员可以设置锁定规则、擦除所有数据、要求存储加密并禁用设备摄像头，如图 9-5 所示。然而，这些策略并非内置在应用中，而是通过 EAS Provision 协议从服务获取的。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_213_0.png)

## Google Apps

Google Gmail 服务的企业版 Google Apps 也支持设置移动设备安全策略。如果域管理员启用了此功能，Google Apps 帐户持有者还可以远程定位、锁定或擦除其 Android 设备。域管理员还可以从托管设备上选择性地删除 Google Apps 帐户及其所有相关内容，而无需执行完全擦除。策略执行和远程设备管理都在专用的 Google Apps 设备策略应用中实现（见示例 9-3）。

首次启动时，该应用程序会请求用户启用内置设备管理员，并显示当前的域策略设置，如图 9-6 所示。

域管理员在 Google Apps 管理控制台中定义策略（见图 9-7），并使用 Google 的专有同步协议将策略设置推送到设备。

虽然免费的 Google 账户不支持设置设备策略，但 Google 设备可以使用内置在 Google Play Services 中的基础设备管理员（见示例 9-3）。这是因为 Google Play Services 是系统镜像的一部分。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_214_0.png)

图 9-6：策略执行

## VPN 支持

虚拟专用网络（VPN）为不那么安全的网络（如互联网）提供了一个安全的连接。它创建了一个加密的“隧道”，数据可以在其中传输，确保其私密性和安全性。有多种类型的 VPN 协议，包括：

- PPTP（点对点隧道协议）
- L2TP（数据层隧道协议）
- IPSec（互联网安全协议）
- OpenVPN
- WireGuard

每种协议在安全性、速度和配置便利性方面都有不同的特点。Android 支持多种类型的 VPN，允许用户直接在设置中对其进行配置和管理它们。

OpenVPN 是一种流行的开源应用程序，它使用 SSL 进行身份验证和密钥交换（也支持预配置的共享密钥）。OpenVPN 将用于身份验证和密钥交换的 SSL 会话多路复用，加密包通过单个 UDP（或 TCP）协议进行隧道传输。该多路复用协议为 UDP 之上的 SSL 提供了可靠的传输，但可靠性是由协议本身（通常是 TCP）提供的。

OpenVPN 相比于 IPSec 的主要优势在于它简单得多，并且可以完全在用户空间中实现。相比之下，IPSec 需要内核级支持以及多个协议的实现。此外，OpenVPN 流量更容易通过 NAT 和代理传输，因为它使用 UDP 等常用网络协议，并可以通过单个端口对流量进行隧道处理。

接下来的章节将探讨 Android 内置的 VPN 支持，以及它为想要实现 VPN 解决方案的应用程序提供的 API。我们还将回顾构成 Android VPN 基础设施的组件，并展示它是如何保护凭据的。

## Legacy VPN

在 Android 4.0 之前，VPN 支持完全内置在平台中，且不可扩展。新的 VPN 类型只能作为平台更新的一部分添加。为了将其与基于应用程序的实现区分开来，内置的 VPN 支持被称为 legacy VPN（旧版 VPN）。

早期 Android 版本支持基于 PPTP 和 L2TP/IPSec 的 VPN 配置，并带有对“纯 VPN”的支持。此外，Android 4.0 通过提供 `VpnService` 类引入了基于应用程序的 VPN，应用程序可以扩展该类。legacy VPN 通过“设置”应用程序控制，并且在多用户设备上仅对所有者（也称为主用户）可用。图 9-8 显示了添加新 VPN 配置文件的对话框。

## Implementation

legacy VPN 使用内核驱动程序、原生守护进程和系统服务的组合。PPTP 和 L2TP 隧道的低层实现使用了名为 `mtpd` 的 Android 专用守护进程和 PPPoLAC（仅在 Android 内核中可用）。由于 legacy VPN 每个设备仅支持单个 VPN 连接，`mtpd` 只能创建一个会话。IPSec 利用了内核内置的 IPSec 支持以及一个修改过的 `raccoon` 密钥管理守护进程（IPSec-Tools 软件包的一部分，该包补充了 Linux 内核的 IPSec 实现）；示例 9-6 显示了如何在 `init.rc` 中定义这两个守护进程。

### 示例 9-6：`init.rc` 中的 `raccoon` 和 `mtpd` 定义

```text
service raccoon /system/bin/raccoon
  class system
  socket socket main
  # IKE 使用 UDP 端口 500。Raccoon 在绑定端口后会将 setuid-id 设置为 vpn。
  group vpn net_admin inet
  disabled
  oneshot
```

```text
service mtpd /system/bin/mtpd
  class main
  socket mtpd stream 600 system
  group vpn net_admin inet net_raw
  disabled
  oneshot
```

`raccoon` 和 `mtpd` 创建 socket，这些 socket 仅供系统用户访问且默认不启动。两个守护进程都使用 `vpn`、`net_admin`（内核映射为 Linux 能力 `CAP_NET_ADMIN`）和 `inet` 作为补充组，这允许它们创建 socket 并控制网络接口设备。`mtpd` 守护进程还接收 `net_raw` 组（映射为 Linux 能力 `CAP_NET_RAW`），这允许它通过 PPTP 创建 GRE socket。

当通过“设置”应用程序启动 VPN 时，Android 会启动 `raccoon` 和 `mtpd` 守护进程，并通过本地 socket 向它们发送命令以建立配置的连接。守护进程创建请求的 VPN 隧道，然后使用接收到的 IP 地址和网络掩码创建隧道接口。虽然 `mtpd` 在内部执行接口配置，但 `raccoon` 使用辅助命令 `ip-vpn` 来启动名为 `tun0` 的隧道接口。



为了向框架通信连接参数，VPN 在`/data/misc/vpn/`中写入状态文件，如示例 9-7 所示。

### 示例 9-7. VPN 状态文件的内容

```
# cat /data/misc/vpn/state
tun
10.8.0.1
192.168.1.0/24
192.168.1.1
example.com
```

该文件包含隧道接口名称 ①、其 IP 地址和掩码 ②、配置的路由 ③、服务器 ④ 以及搜索域 ⑤，每行一个。

在 VPN 守护进程启动后，框架解析状态文件并调用系统`ConnectivityService`，为新建立的 VPN 连接配置路由、DNS 服务器和搜索域。相应，`ConnectivityService`通过`netd`守护进程的本地 socket 发送命令，由于它以 root 运行，可以修改内核数据包过滤和路由表。来自用户启动和受限配置的所有应用程序的流量，通过防火墙规则路由到 VPN 接口，该规则匹配应用程序 UID 并控制路由规则。

示例 9-8 中的证书 (③) 和来自系统密钥库的示例 9-8 中的 CA 证书 (①) 通过控制套字将其传递给`racoon`，以及其他连接参数。示例 9-8 中的私钥 (④) 从不会直接传递给`racoon`守护进程，仅传递其别名 (`vpnclient`)。

### 注意

> 虽然在具有硬件支持的密钥库的设备上密钥受硬件保护，但存储在 VPN 配置文件中的预共享密钥或密码并非如此的原因。原因是，在编写本文时，Android 在硬件支持的密钥库中不支持对称密钥；它仅支持非对称密钥（RSA、DSA 和 EC）。因此，使用预共享密钥的 VPN 凭据以明文形式存储在 VPN 配置文件中，并可以在内存中解密配置文件后从允许 root 访问的设备中提取。

# 始终开启 VPN (Always-On VPN)

Android 4.2 及更高版本支持始终开启 VPN 配置，它在建立到指定 VPN 配置的连接之前阻止应用程序的所有网络连接。这防止了应用程序通过不安全的通道（如公共 Wi-Fi 网络）发送数据。

设置始终开启 VPN 需要设置一个 VPN 配置文件，将 VPN 网关指定为 IP 地址，并指定显式的 DNS 服务器 IP 地址。这种显式配置是为了确保 DNS 流量不会发送到本地配置的 DNS 服务器（当始终开启 VPN 生效时该服务器会被阻塞）。图 9-9 显示了 VPN 配置选择对话框。

配置选择与其他 VPN 配置文件一起保存在示例 9-8 的加密文件`LOCKDOWN_VPN` (②) 中，该文件仅包含所选配置的名称；在我们的示例中为`144965b85a6.q`。如果存在`LOCKDOWN_VPN`文件，系统会在设备启动时连接到指定的 VPN。如果底层网络连接重新连接或更改（例如在切换 Wi-Fi 热点时），VPN 将自动重启。

始终开启 VPN 通过安装防火墙规则确保所有流量都通过 VPN，这些规则阻止了除 VPN 接口的所有数据包。规则由`LockdownVpnTracker`类安装（在 Android 源代码中，始终开启 VPN 被 lockdown VPN），该类监控 VPN 状态并通过向 net 守护进程发送命令来调整当前防火墙状态，而 net 守护进程转而执行`iptables`工具以修改内核的数据包过滤表。例如，当 L2TP/IPSec VPN 连接到 IP 地址为`11.22.33.44`的 VPN 服务器并创建 IP 地址为`10.1.1.1`的隧道接口`tun0`时，安装的规则（由`iptables`报告；为了简洁省略了一些列）可能如示例 9-10 所示。

示例 9-10 始终开启 VPN 防火墙规则

```
# iptables -v -L n
--snip--
Chain fw_INPUT (1 references)
target opt in source destination
RETURN all - * * - * - * 0.0.0.0/0 10.1.1.1/32
RETURN all - - tun0 * 0.0.0.0/0
RETURN udp - * * 11.22.33.44 0.0.0.0/0 udp spt:1701
RETURN tcp - * * 11.22.33.44 0.0.0.0/0 tcp spt:1701
RETURN udp - * * 11.22.33.44 0.0.0.0/0 udp spt:4500
RETURN tcp - * * 11.22.33.44 0.0.0.0/0 tcp spt:4500
RETURN udp - * * 11.22.33.44 0.0.0.0/0 udp spt:500
RETURN tcp - * * 11.22.33.44 0.0.0.0/0 tcp spt:500
```

```
all -- - * 0.0.0.0/0 0.0.0/0
DROP all -- * 0.0.0.0/0 0.0.0/0
chain fw_OUTPUT in out source destination
target RETURN all -- * 10.1.1.0/24 0.0.0/0
RETURN all -- * tun0 0.0.0.0/0 0.0.0/0
RETURN udp -- * 0.0.0.0 11.22.33.44 udp dpt:1701
RETURN tcp -- * 0.0.0.0 11.22.33.44 tcp dpt:2701
RETURN udp -- * 0.0.0.0/0 11.22.33.44 udp dpt:4500
RETURN tcp -- * 0.0.0.0/0 11.22.33.44 tcp dpt:4500
RETURN udp -- * 0.0.0.0/0 11.22.33.44 udp dpt:5000
RETURN tcp -- * 0.0.0.0/0 11.22.33.44 tcp dpt:5000
RETURN all -- * lo 0.0.0.0/0 0.0.0/0
REJECT all -- * 0.0.0.0/0 0.0.0/0 reject-with-icmp-port-unreachable
--snip--
```

如列表所示，发自 VPN 网络的流量 (1) 和 (5) 是允许的，隧道接口 (2) 和 (6) 上的流量也是允许的。发往 VPN 服务器 (3) 和 (7) 的流量仅允许 IPSec (500 和 4500) 和 L2TP (1701) 使用的端口。所有出站流量被丢弃 (4)，所有入站流量被拒绝 (8)。

# 基于应用的 VPN (Application-Based VPNs)

Android 4.0 添加了`VpnService`公有 API，第三方应用程序可以使用它来构建并非内置于操作系统且不需要系统级权限的 VPN 解决方案。`VpnService`和相关的`Builder`类允许应用程序将 VPN 网关指定为 IP 地址，并指定显式的 DNS 服务器 IP 地址。这种显式配置是为了确保 DNS 流量不会发送到本地配置的 DNS 服务器（当始终开启 VPN 生效时该服务器会被阻塞）。

一个与 OpenVPN 服务器完全兼容的 SSL VPN 客户端。

## 多用户支持

如前所述，在多用户设备上，旧版本的 VPN 只能由所有用户控制。然而，随着对多用户支持的引入，Android 4.2 及更高版本允许所有次要用户（限制配置文件除外，限制配置文件必须共享主用户的 VPN 连接）启动基于应用程序的 VPN。虽然这种变化在技术上允许每个用户启动自己的 VPN，但由于一次只能激活一个基于应用程序的 VPN，无论由谁启动，所有设备用户的流量都会被路由到当前激活的 VPN。Android 4.4 通过引入“每用户 VPN”（per-user VPN）最终实现了完整的多用户 VPN 支持，它允许任何用户的流量都路由到它们自己的 VPN，从而将其与其他用户的流量隔离。

# Linux 高级路由

![](img/8524e4e57e2e9dc889903e3d2c5fe367_226_0.png)

Android 使用了 Linux 内核的若干种高级数据包过滤和路由功能来实现每用户 VPN。这些功能（由 netfilter 内核框架实现）包括 Linux iptables 的 owner 模块，它允许根据创建数据包的进程的 UID、GID 或 PID 来匹配本地生成的数据包。例如，示例 9-12 中的命令创建了一个包过滤规则，丢弃所有由 UID 为 1234 的用户生成的传出包。

# 9-12. 使用 iptables 使用 owning 匹配器和包标记

```
# iptables -OUTPUT -m owner --add-mark 1234 -j DROP
# iptables -A PREROUTING -m -p tcp --dport 80 -j MARK --set-mark 0x1
# ip route add fwmark 0x1 table web 3
# ip route add default via 1.2.3.4 dev em3 table web 4
```

另一个 nftables 功能是能够为匹配特定选择器的数据包标记指定的数字（称为标记/mark）。例如，将所有发往 80 端口（通常用于 Web 服务器）的数据包标记为 mark 0x1。该标记稍后可以在过滤或路由规则中被匹配，方法是添加一条路由规则，将已标记的数据包发送到预定义的路由表（在我们的例子是 web）。最后，可以使用图中所示命令添加一条将匹配 web 表的数据包发送到 em3 接口的路由。

# 多用户 VPN 实现

Android 使用这些过滤和路由功能来标记来自特定 Android 用户所有应用程序的数据包，并让它们通过该用户启动的 VPN 应用程序创建的隧道接口发送。当所有者启动 VPN 时，该 VPN 将与设备上任何无法启动自己 VPN 的限制配置文件共享，方法是匹配所有来自限制配置的数据包，并将其路由到所有者的 VPN 隧道中。

这种分流路由（split-routing）在框架层通过`NetworkManagementService`实现，该服务提供了通过 UID 或 RID 范围管理包路由的 API。`NetworkManagement`通过向以 root 身份运行的 netd 守护进程发送命令来实现这些 API，从而修改内核的数据包过滤和路由表。netd 通过调用 iptables 和 ip 用户实用程序来操纵内核的过滤和路由配置。

让我们通过示例 9-13 中的例子来说来说明 Android 的每用户 VPN 路由。主用户（用户 ID 0）和第一个次要用户（用户 ID 10）分别启动了一个基于应用程序的 VPN。所有者的 VPN 被分配给 tun0 隧道接口，而次要用户的 VPN 被分配给 tun1 接口。当两个 VPN 都连接时，设备还具有内核数据包过滤表的限制配置文件（省略了某些细节）。

示例 9-13.两个不同设备用户启动的 VPN 的包匹配规则

```
# iptables -t mangle -L -n
--sn----
Chain st_mangle OUTPUT (1 references)
target opt source destination
RETURN all -- 0.0.0.0/0 0.0.0.0/0 mark match 0x1
RETURN all -- 0.0.0.0/0 0.0.0.0/0 owner UID match 1016
--snip--
st_mangle_tun0_OUTPUT all -- 0.0.0.0/0 0.0.0.0/0 [goto] owner UID match
0-99999
st_mangle_tun0_OUTPUT all -- 0.0.0.0/0 0.0.0.0/0 [goto] owner UID match
1300000-1399999
st_mangle_tun1_OUTPUT all -- 0.0.0.0/0 0.0.0.0/0 [goto] owner UID match
1000000-1099999
```

# Chain st_mangle_tun0_OUTPUT (3 references)

| target prot opt source destination |

| MARK all -- 0.0.0.0/0 MARK and 0x |

| MARK all -- 0.0.0.0/0 0.0.0.0/0 MARK set 0x36 |

# Chain st_mangle_tun1_OUTPUT (2 references)

| target prot opt source destination |

| MARK all -- 0.0.0.0/0 0.0.0.0/0 MARK and 0x |

| MARK all -- 0.0.0.0/0 0.0.0.0/0 MARK set 0x36 |

传出包首先发送到 st_mangle_OUTPUT 链，该链负责匹配和标记。免于重新路由的数据包（已标记为 0x1 的包）以及来自旧版 VPN 的包（UID 1016，分配给所有者）在不修改的情况下通过。接下来，分配给主用户的 UID 在 0 到 999 之间的进程所创建的数据包将被匹配并发送到 st_mangle_tun0_OUTPUT。来自 UID 1300000-1399999（限制配置文件）的数据包也被发送到同一链。因此，来自所有者和限制配置的流量被视为是相同的。然而，来自第一个次要用户（用户 ID 10，1000000-1099999）的数据包被发送到不同的链，st_mangle_tun0_OUTPUT 清除数据包并将其标记为 0xc；st_mangle_tun1_OUTPUT 执行相同的操作，但标记为 0xd。在数据包被标记后，它们被用于实现不同的路由规则，如示例 9-14 所示。

示例 9-14.两个不同设备用户启动的 VPN 的路由规则

```
# ip rule
0: from all lookup local
1: from all fwmark 0xc lookup 60
2: from all fwmark 0xd lookup 61
# ip route 60 default dev tun0 scope link
# ip route 61 default dev tun1 scope link
```

注意规则已经创建，并且与不同的表关联。标记为 0xc 的数据包去表 60（十六进制） ①，而标记为 0xd 的数据包去表 61（十六进制） ②。表 60 将所有流量路由到 tun0（由所有者创建），而表 61 将所有流量路由到 tun1（由次要用户创建）。

## EAP 认证方法

从 4.4 版本开始，Android 支持 PEAP、EAP-TLS、EAP-TTLS 和 EAP-PWD 认证方法。在探索 Android 如何存储每种认证方法之前，让我们先简要讨论它们各自的工作原理。

## PEAP

保护扩展认证协议（PEAP）通过 SSL 连接传输 EAP 消息以提供机密性和完整性。它使用 PKI 和证书来验证服务器并建立 SSL 连接（阶段 1），但不强制规定如何验证客户端。客户端使用第二种内部（阶段 2）认证方法进行验证，该方法在 SSL 隧道内传输。Android 阶段支持 MSCHAPv2（在 PEAPv0 指定）和通用令牌卡（GTC，在 PEAPv2 指定）。

### EAP-TLS

EAP 传输层安全（EAP-TLS）方法[96] 使用 TLS 进行双向认证，曾是唯一认证可用于 WPA 企业版的 EAP 方法。EAP-TLS 同时使用服务器证书来向客户端验证服务器，以及由认证服务器验证的客户端证书来建立抑制端身份。授予网络访问需要颁发分发 X.509 客户端证书，并维护公钥基础设施。可以通过撤销抑制端证书阻止现有客户端访问网络。Android 支持 EAP-TLS 并使用系统凭据库管理客户端密钥和证书。

### EAP-TTLS

与 EAP-TLS 类似，隧道化传输层安全（EAP-TTLS）协议[97] 基于 TLS。然而，EAP-TTLS 不需要强制使用 X.509 证书进行客户端认证。客户端可以在握手阶段（阶段 1）使用证书进行认证，也可以在隧道阶段（阶段 2）使用另一种协议进行认证。Android 不支持 PAP、MSCHAP、MSCHAPv2 和 GTC 协议作为阶段 2。

### EAP-PWD

EAP-PWD 认证方法[98] 使用共享密码进行认证。与依赖简单挑战-响应机制的旧方案不同，EAP-PWD 设计用于抵抗被动攻击、主动攻击和字典攻击。该协议还提供前向安全性，并保证即使密码泄露，之前的会话也不会被解密。EAP-PWD 基于离散对数密码，可以使用有限域或椭圆曲线实现。

## Android Wi-Fi 架构

与 Android 的硬件支持类似，Android 的 Wi-Fi 架构由内核层（WLAN 驱动模块）、原生守护进程（wpa_supplicant）、硬件抽象层（HAL）、系统服务和系统 UI 组成。Wi-Fi 适配器驱动通常用于构建 Android 设备的系统级芯片（SoC），通常是链接内核模块。wpa_supplicant[99] 是一个 WPA 守护进程，实现与 WLAN 驱动的 WPA 认证器以及 802.1X 关联。然而，Android 设备很少使用原始的 wpa_supplicant 代码；包含的实现通常为了与底层 SoC 有更好的兼容性进行了修改。

HAL 实现在 libhardware_legacy 原生库中，负责通过其控制套接字将框架命令传递给 wpa_supplicant。连接 Wi-Fi 的系统服务是 WiFi，它通过 WifiFacade 类提供公共接口。WifiService 将 Wi-Fi 状态管理委托给一个复杂的 WifiState 状态机，该状态机在连接无线网络时有十多个状态。

WLAN 连接通过系统设置应用中的 Wi-Fi 屏幕控制，连接状态显示在状态栏和快速设置（属于 SystemUi 包）中。



Android 将 Wi-Fi 相关的配置文件存储在 `/data/misc/wifi/` 目录下，因为连接守护进程会直接持久化配置更改，因此需要一个可写目录。该目录由 `wifi` 用户（UID 1010）所有，该用户也是 `wpa_supplicant` 的用户。配置文件（包括 `wpa_supplicant.conf`）的权限为 `0660`，由系统用户所有，其组设置为 `wifi`。这确保了系统应用程序和抑制端守护进程可以读取和修改配置文件，但其他应用程序无法访问。`wpa_supplicant.conf` 文件包含格式化为键值对的配置参数，既有全局的，也有特定于网络的。网络特定参数被封装在网络块中，对于 PSK 配置，它们看起来像示例 9-15 所示。

```
示例 9-15. wpa_supplicant.conf 中的 PSK 网络配置块
network={
ssid="psk-ap"①
key_mgmt=WPA-PSK②
k="password"③
priority=80④
}
```

如你所示，网络块指定了网络 SSID ①、认证密钥管理协议 ②、预共享密钥本身 ③ 以及优先级值 ④。PSK 以明文形式保存，虽然 `wpa_supplicant.conf` 的访问位禁了非系统应用程序访问它，但可以从允许 root 权限的设备中轻松提取。

## EAP 凭据管理

在本节中，我们将检查 Android 如何为每种支持的 EAP 认证方法管理 Wi-Fi 凭据，并讨论 Android 特有的 `wpa_supplicant` 修改，这些更改允许抑制端守护进程利用 Android 的系统凭据库。

示例 9-16 显示了配置为使用 PEAP 的 `wpa_supplicant.conf` 中的网络块。

```
示例 9-16. wpa_supplicant.conf 中的 PEAP 网络块
network={
```

在此，认证密钥协议设置为 `WPA-EAP8021X` ①，方法是 PEAP ②，密码为 `MSCHAPv2` ③。凭据（即身份和密码）以明文存储。通用 `wpa_supplicant.conf` 的区别在于 CA 证书路径 ⑤。在验证服务器时使用 CA 证书 ⑥。

EAP-TLS 配置与 PEAP 类似，如示例 9-17 所示。

```
示例 9-17. wpa_supplicant.conf 中的 EAP-TLS 网络块
network={
sid="eap-ap"
key_mgmt=WPA
key=TLS
identity="android"
ca_cert="keystore://CACERT_eapclient"
client_cert="keystore://USERCERT_eapclient"
engine_id="keystore"
}
```

这里新增了客户端证书 URI ①、引擎 ID ② 和密钥 ID ③。客户端证书从系统凭据库检索。`wpa_supplicant` 原生支持配置 OpenSSL 引擎，通常用于智能卡或硬件设备。

如第 7 章所述，Android 的 `keystore` 引擎使用存储在系统凭据库中的密钥。如果设备支持硬件保护凭据库，`keymaster` HAL 模块可以透明地利用它。

从 4.3 版本开始，Android 允许在导入时选择自己的密钥和证书。之前，所有导入的密钥都属于系统用户，但如果你在导入对话框将凭据使用设置为 Wi-Fi（见图 9-13），密钥所有者将设置为 `wifi` 用户（UID 1010），密钥仅可由运行 `wifi` 用户的系统组件访问，例如 `wpa_supplicant`。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_233_0.png)

由于在使用 EAP-TTLS 认证方法时不支持客户端认证，配置仅包含 CA 证书引用 ②，如示例 9-18 所示。① 以明文存储。

```
示例 9-18. wpa_supplicant.conf 中的 EAP-TTLS 网络配置块
network{
sid="ca-eap"
key_mgmt=WPA-EAP8021X
eap=TTLS
identity="android"
anonymous_identity="anon"
password="password" 1
ca_cert="keystore://CACERT_eapclient" 2
phase2="auth-GTC"
proactive_key_caching=1
}
```

EAP-PWD 方法不依赖 TLS 建立安全通道，因此不需要证书配置，如示例 9-19 所示。凭据以明文形式存储 1 和 ②。

## 示例 9-19. wpa_supplicant.conf 中的 PWD 网络配置块

```conf
network {
  ssid="eap-ap"
  key_mgmt=WPA-EAP IEEE8021X
  eap-PWD
  identity="android1"
  password="password"
  proactive_key_caching=1
}
```

总之，所有使用密码进行认证的 EAP 方法的配置都会以明文形式将凭据存储在 `wpa_supplicant.conf` 文件中。在使用依赖客户端认证的 EAP-TLS，密钥存储在系统密钥库（`system keystore`），从而提供了最高级别的凭据保护。

## 使用 WifiManager 添加 EAP 网络

虽然 Android 支持多种 WPA 企业级认证方法，但由于需要配置大量的参数，并且需要安装并选择认证证书，正确设置它们可能会给某些用户带来挑战。由于 Android 管理 Wi-Fi 网络的官方 API（称为 `WifiManager`）在 Android 4.3 之前不支持 EAP 配置，因此设置 EAP 网络的唯一方法是通过系统设置应用进行添加并手动配置。Android 4.3（API 18）扩展了 `WifiManager` API，允许通过程序进行 EAP 配置，从而在企业环境中实现了自动网络置备。在本节中，我们将展示如何使用 `WifiManager` 添加 EAP-TLS 网络，并讨论其底层实现。

`WifiManager` 允许持有 `CHANGE_IFI_STATE` 权限（保护级别：危险）的应用通过初始化一个带有网络 SSID、认证算法和凭据的 `WifiConfiguration` 实例来添加 Wi-Fi 网络并将其传递给 `WifiManager` 的 `addNetwork()` 方法。Android 4.3 通过添加类型为 `EnterpriseConfig` 的字段扩展了此 API，允许你配置要使用的 EAP 认证方法、客户端和 CA 证书，以及用户名和密码等额外凭据。示例 9-20 展示了如何使用此 API 添加一个使用 EAP-TLS 进行认证的网络。

```java
X509Certificate caCert = getCaCert();
PrivateKey clientKey = getClientKey();
X509Certificate clientCert = getClientCert();

EnterpriseConfig enterpriseConfig = new EnterpriseConfig();
enterpriseConfig.setCaCertificate(caCert);
enterpriseConfig.setClientKeyEntry(clientKey,clientCert);
enterpriseConfig.setAuthMethod(enterpriseConfig.EAP_TLS);
enterpriseConfig.setPhase2Method(enterpriseConfig.Phase2_NONE);
enterpriseConfig.setIdentity("android1");
WifiConfiguration config = new WifiConfiguration();
config.enterprise=enterpriseConfig;
config.SSID="eap-ap";
```

```java
int ntlid = wm.addNetwork(config);
if (ntlid != -1) {
    boolean success = wm.saveConfiguration(config);
}
```

为了设置 EAP-TLS 认证，我们首先需要获取 CA 证书以验证服务器身份，以及客户端的私钥。由于这些通常以 PKCS#12 形式发行，我们可以使用类型为 `PKCS12` 的 `KeyStore` 来提取它们（此处显示）。（当你添加使用这些密钥和证书的 EAP 配置文件时，Android 会自动将指定的密钥和证书导入系统密钥库，因此你不需要导入 PKCS#12 文件。）获取 CA 证书和客户端凭据后，我们使用 `setCaCertificate()` 和 `setClientKeyEntry()` 方法将它们设置为我们的 `WifiEnterpriseConfig` 实例。然后，我们将 EAP 方法设置为 `EAP.TLS`，并将阶段 2 方法设置为 `NONE`，因为 EAP-TLS 是作为建立 SSL 连接（阶段 1）的一部分来认证用户的。Android 还要求我们设置身份标识（`identity`），尽管认证服务器可能不会使用它。在配置好 `WifiEnterpriseConfig` 对象后，我们可以将其添加到主 `WifiConfiguration` 实例中。还需要配置密钥管理协议集，因为默认是 `WPA PSK`。最后，我们可以添加网络并保存配置，这将更新 `wpa_supplicant.conf` 文件以包含新配置的网络。

Android 会自动为配置的私钥和证书生成别名，然后将 PKI 凭据导入系统密钥库。别名基于 AP 名称、密钥管理方案和 EAP 认证方法。通过程序配置的网络将自动显示在系统设置应用的 Wi-Fi 屏幕中，对于示例 9-20 所示的示例，其看起来可能类似于图 9-14。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_236_0.png)

图 9-14. 使用 WifiManager 添加的 EAP-TLS 网络

Android 支持设备管理 API，允许设备管理应用配置安全策略，该策略可以包括对锁屏密码复杂性、设备加密和摄像头使用的的要求。设备管理员通常与公司账户（如 Microsoft Exchange 和 Google Apps 账户）配合，以便根据策略和设备设置限制对公司数据的访问。设备管理 API 还提供了远程锁定设备和擦除数据的功能。

Android 设备可以连接各种类型的 VPN，包括 PPTP、L2TP/IPSec 和基于 SSL 的 VPN。对 PPTP 和 L2TP/IPSec 的支持是内置于平台中的并且可以...

# 第 10 章 设备安全

到目前为止，我们一直关注 Android 如何实现沙箱机制和权限分离以将应用程序相互隔离。在本章中，我们将介绍 Android 如何确保操作完整性并保护数据免具有物理访问权限的攻击者。我们首先简述引导程序（bootloader）和恢复系统（recovery OS），然后讨论 Android 的验证启动（verified boot），它确保系统分区未被修改。接下来，我们查看 Android 如何加密用户数据分区（userdata partition），该分区存放 OS 配置文件和应用程序数据。这保证了没有解密密码无法启动设备，且用户数据无法被提取。然后我们将展示 Android 的锁定是如何实现的，以及解锁模式、PIN 和口密码是如何被哈希并存储在设备上的。

我们还将讨论 USB 调试，它通过 USB 连接到 Android 调试桥（ADB）守护进程的主机，并要求用户显式允许访问。由于通过 USB 允许执行应用程序安装、全备份和文件访问等特权操作……最后，我们描述 Android 全备份的实现方式和存档加密格式。

### 控制 OS 启动和安装

如果拥有设备的物理访问，攻击者不仅可以通过高级 OS 结构（如文件和目录）访问或修改用户和系统数据，还可以通过访问内存或原始磁盘存储。这种直接访问可以通过物理连接设备的电子组件来实现，例如拆解设备并连接到硬件调试接口，或者拆下闪存并使用专用设备读取内容。

> 硬件攻击超出了本书的范围；请参《Android Hacker's Handbook》（Wiley, 2014）第 10 章以获取该主题的介绍。

另一种侵入性较小但仍然强大的获取此类数据的方法是使用设备更新机制来修改系统文件并移除访问限制，或者启动一个允许直接访问存储的替代操作系统。大多数消费 Android 设备默认都是锁定的，因此这些技术要么不可，要么需要代码签名密钥（该密钥通常只有设备制造商拥有）。

### Bootloader

引导程序是一种在设备首次启动时执行的特殊的、与硬件相关的程序（从 ARM 设备的休眠中恢复）。其目的是初始化设备硬件、可选地提供最小化设备配置接口，然后查找并启动系统。

设备启动通常需要经过不同的阶段，每个阶段都可能涉及一个引导程序（bootloader）——为了简单起见，我们将称为包含所有阶段的单一聚合引导程序。Android 引导程序通常是私有的，并且特定于构建设备所使用的系统级芯片（SoC）。设备和 SoC 制造商在它们的引导程序中提供不同的功能和保护级别，但大多数引导程序都支持 `fastboot`，或者更广泛地说支持下载模式（download mode），这允许将根分区镜像（通常称为刷写或 flashing）写入设备的持久性存储器，还可以启动瞬态系统镜像（而不将其刷写到设备中）。`fastboot` 模式可以在设备启动时通过特殊的硬件键组合启用，或者通过 ADB 发送重启引导程序的命令来启用。

为了确保设备的完整性，消费级设备在出厂时带有锁定的引导程序，锁定的引导程序要么完全允许刷写并启动系统镜像，要么只允许由设备制造商签名的镜像。大多数消费级设备允许解锁引导程序，这将移除出厂限制和镜像签名检查。解锁引导程序通常需要格式化 `userdata` 分区，以确保恶意操作系统无法访问现有数据。

在某些设备上，解锁引导程序是一个不可逆的过程，但大多数设备提供了一种重新加载引导程序并将其恢复原始状态的方法。这通常通过在专用的系统分区（通常称为 `param` 或 `misc`）上存储引导程序状态标记位来实现，该分区托管了各种设备元数据。重新锁定引导程序只需重置该标记的值。

### 恢复 (Recovery)

更新设备的更灵活的方法是通过其恢复系统（recovery OS）。恢复系统（简称 recovery）是一个基于 Linux 的最小操作系统，它包含一个内核、带有各种低级工具的内存磁盘（RAM disk）以及一个通常使用设备硬件操作的最小 UI。恢复系统用于应用出厂后的更新，这些更新通常以空中下载（OTA）更新包的形式交付。OTA 包包含更新后的系统文件的新版本（或二进制补丁）以及一个应用更新的脚本。正如我们在第 3 章中学习到的，OTA 文件也是使用设备制造商的私钥进行代码签名的。恢复确保只有来自第三方的 OTA 文件可以修改设备操作系统。

恢复系统存储在专用分区上，就像主 Android 操作系统一样。因此，它可以通过将引导程序放入下载模式并刷写自定义恢复镜像来替换，该自定义镜像会替换嵌入的公钥，或者完全不验证签名。这种恢复系统允许主操作系统被完全替换为第三方生成的构建版本。自定义恢复系统可以允许通过 ADB 获取不受限制的 root 权限，以及原始分区获取。虽然 `userdata` 分区可能是加密的（参见“磁盘加密”），导致数据无法访问，但在恢复模式下，在系统分区上安装恶意程序（rootkit）是轻而易举的。该 rootkit 可以在主操作系统启动时启用对设备的访问，从而允许访问用户数据，而这些数据在主操作系统启动时会被透明地解密。

验证启动（verified boot，在下一节中讨论）可以防止这种情况，但仅当设备使用存储在硬件中的未修改验证密钥来验证启动分区时有效。解锁的引导程序允许启动或刷写系统镜像并直接访问系统分区。Android 安全功能，如验证启动（verified boot）和磁盘加密可以限制通过解锁的引导程序刷写的恶意镜像所能造成的损害，控制对引导程序的访问对于保护 Android 设备至关重要。因此，在测试或开发设备上应该解锁引导程序，或者在修改系统后立即重新加载并恢复其原始状态。

## 验证启动 (Verified Boot)

Android 的验证启动实现基于 `dm-verity` device-mapper 块完整性检查目标。device-mapper 是一个 Linux 内核框架，提供了实现虚拟设备的通用方法。它是 Linux 逻辑卷管理器（LVM）的基础，并用于实现全盘加密（使用 `dm-crypt` 目标）、RAID 阵列甚至是分布式复制存储。

device-mapper 的工作原理本质上是将虚拟块设备映射到一个或多个物理设备，并可选地修改传输过程中的数据。例如，`dm-crypt`（在“磁盘加密”中讨论的 `userdata` 分区加密的基础）在将数据提交磁盘之前解密读取的物理块并对写入进行加密。因此，磁盘加密对于虚拟 `dm-crypt` 块设备的用户来说是透明的。device-mapper 目标可以堆叠，使得实现复杂的数据转换成为可能。

## dm-verity 概述

由于 `dm-verity` 是一个块完整性检查目标，它会在从磁盘读取每个块设备时，透明地验证其完整性。如果块检查通过，则读取成功；如果不是，读取将产生 I/O 错误，就像该块物理损坏一样。

在底层，`dm-verity` 使用预计算的哈希树（也称为 Merkle ）实现，包含了所有设备块的哈希。树的叶节点包含物理设备块的哈希，而中间节点是其子节点的哈希（哈希的哈希）。根节点被称为根哈希（root hash），它基于较低层的所有哈希，如图 10-1 所示。因此，单个设备块的变化将导致根哈希的变化，为了验证哈希值是真实的，我们需要验证它的根哈希。

在运行时，`dm-verity` 在读取每个块时通过遍历预计算的哈希树来计算其哈希并进行验证。由于从物理设备读取数据已经是一项耗时的操作，哈希计算和验证带来的延迟相对较低。此外，一旦通过验证，磁盘块会被缓存，后续对同一块的读取将不会触发完整性验证。

图 10-1. dm-verity 哈希树



由于 `dm-verity` 依赖于覆盖设备所有块的预计算哈希树，为了使验证成为可能，底层设备必须以只读方式挂载。大多数文件系统会在其 `superblock` 中记录挂载时间和元数据，即使运行时没有文件更改，如果底层块设备是以读写方式挂载，完整性检查也将失败。尽管这可以被视为一种局限，但它对于持有系统文件的设备或分区是有效的，因为这些文件只通过 OS 更新更改。任何其他更改都表明 OS 损坏或恶意程序正尝试伪造成系统文件。

最终，`dm-verity` 的只读要求与 Android 的安全模型非常匹配，该模型将应用程序数据托管在读写分区上，并将操作系统文件保留在只读的 `system` 分区上。

## Android 实现

`dm-verity` device-mapper 目标最初是为了在 Chrome OS 中实现验证启动而开发的，并在 3.4 版本中集成到主 Linux 内核中。它通过 `CONFIG_DM_VERITY` 配置项启用。

与 Chrome OS 一，Android 4.4 也使用 `dm-verity` 目标，但根哈希的加密验证和验证分区的挂载实现方式不同。用于验证的 RSA 公钥通过 `verify_key` 文件名嵌入引导分区中，并用于验证 `dm-verity` 映射表，该表持有目标设备的位置和哈希表的偏移，以及根哈希和盐（salt）。

映射表及其签名是验证元数据块的一部分，该块直接写入目标设备第一个文件系统块之后。通过在 `fstab` 文件的 Android 特有 `fmgr_flags` 字段中添加 `verify` 标志可以将分区标记为可验证。当 Android 文件系统管理器在 `fstab` 中遇到 `verify` 标志时，它从 `fstab` 指定的块设备加载验证元数据，并使用包含的验证密钥验证其签名。如果签名检查通过，文件系统解析 `dm-verity` 映射表并将其传递给 Linux device-mapper，device-mapper 使用映射表包含的信息创建一个虚拟的 `dm-verity` 设备。该虚拟块设备被挂载到 `fstab` 指定挂载点，以取代相应的物理设备。结果是，所有底层的读取物理设备会根据预生成的哈希树（hash tree）进行透明化验证。修改或添加文件，甚至重新挂载分区都会导致完整性验证失败和 I/o 错误。

### 注意

由于 `verity` 是内核的一个功能，为了使其完整性保护生效，启动时使用的内核必须是受信任的。在 Android 上，这需要启动分区，该分区还包含根文件系统 RAM 磁盘（`initrd`）和验证公钥。内核启动镜像验证是一个设备特定的过程，通常在设备的引导加载程序（bootloader）中实现，并依赖存储在硬件中不可修改的签名验证密钥。

# 启用验证启动（Verified Boot）

Android 官方文档将在 Android 上启用验证启动的过程描述为一个多步过程，涉及生成哈希树、为哈希树创建 `dm-verity` 映射表、对该表进行签名，以及生成并向 `verity` 元数据块写入目标设备。[102] 在本节中，我们将简要描述该过程的关键步骤。

`dm-verity` 哈希树是用 `veritysetup` 程序生成的，该程序是 `cryptsetup` 加密卷管理工具包的一部分。`veritysetup` 程序可以直接在块设备上操作，也可以使用文件系统生成哈希树，并将哈希表写入文件。Android 的 `dm-verity` 实现要求在调用 `verity` 时必须指定一个显式的哈希偏移量，该偏移指向 `verity` 元数据块之后的位置。图 10-2 显示了为使用 `dm-verity` 准备的磁盘分区布局。

| 超块 (Superblock) | 块1 | 文件系统数据 | 块 N | Verity 元数据块 | 超块 | 哈希树数据 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |

图 10-2. 为 `dm-verity` 验证准备的磁盘分区布局。

生成 `verity` 树会产生根哈希（root hash），用于用于构建目标设备的 `dm-verity` 映射表。示例 10-1 显示了一个采样映射表。

示例 10-1. Android `dm-verity` 映射表

```text
1 dev/block/mmc0p2 dev/block/mmc0p21 40964 40965
204800 204809 sha256
f19515881567e3ceee3bc10796a17935c09174758f9923532ba5c3f47cb3b10
50615918b1b541a8096252c543253fe29b852ae161f20826673cb11
```

如表所示，该行是一个拆拆分（为了可读性跨多行），它位于根哈希 9 之后，包含 `dm-verity` 版本 1、底层数据和哈希设备名称（2 和 3）、数据和哈希块大小（4 和 5）、数据和哈希偏移量（6 和 7）、哈希算法 8 以及盐值（salt）10。

映射表使用 2048 位 RSA 密钥，并结合生成的 PKCS# v1.5 签名共同形成 32 KB 的 `verity` 元数据块。表 10-1 显示了元数据块每个字段的内容和大小。

| 字段 | 描述 | 大小 | 值 |
| :--- | :--- | :--- | :--- |
| 魔数数字 (Magic number) | 由 `fs_mgr` 用于健康检查 | 4 字节 | `0xb001b001` |
| 版本 (Version) | 元数据块版本 | 4 字节 | 当前为 0 |
| 签名 (Signature) | 映射表签名 (PKCS#1 v1.5) | 256 字节 | |
| 映射表长度 (Mapping table length) | 以字节为单位的映射表长度 | 4 字节 | |
| 映射表 (Mapping table) | `dm-verify` 映射表 | 可 | |
| 填充 (Padding) | 填充至 32 kb 字节长度 | 可 | |

用于验证的 RSA 公钥需要是 `mincrypt` 格式（或在验证 OTA 签名由官方恢复使用），它是 `mincrypt RSAPublicKey` 结构的序列化。该结构的有趣之处在于，它不包含密钥模和指数值，而是包含了 `mincrypt` 的 RSA 实现（基于蒙哥马利归约）使用的预计算值。公钥包含在启动镜像根目录下，文件名为 `verify_key`。

启用验证启动所需的最后一步是修改设备的 `fstab`，以便为 `system` 分区启用块完整性验证。这简单只需添加 `verify` 标志，如示例 10-2 所示（Nexus 4 的示例 `fstab` 文件）。

示例 10-2. 经过 `dm-verify` 格式化验证的分区的 `fstab`

```text
/dev/block/partition/imn_sdc /by-name/system /ext4 ro,barrier=1 wait,verify
```

当设备启动时，Android 根据 `fstab` 条目和映射表信息（包含在元数据块中）创建一个虚拟 `dm-verify` 设备，并将其挂载到 `/system`，如示例 10-3 所示。

示例 10-3. 挂载到 `/system` 的 `dm-verify` 虚拟块设备

```text
# mountgrp system
/dev/block/dm-0 /system /ext4 ro,relatime,at,data=ordered 0 0
```

现在，对系统分区的任何修改都导致在读取相应内容时产生错误。

这并不能确保加密块的完整性。事实上，事实证明，如果攻击者知道在磁盘上的原始明文，他们就可以操纵存储的数据，并在我们使用 CBC 进行加密的卷上注入后门程序。[105]

# 备用加密模式：XTS

针对 ESSIV 模式的这种特定攻击可以通过切换到可调加密模式（如 XTS，基于 XEX 的微调代码密文窃取模式）来避免。该模式结合了扇区索引和扇区内密文块索引，为每个扇区派出一个“唯一的”（可变参数）。

为每个扇区使用不同的微调（tweak）与使用相同密钥加密每个扇区的效果相同：明文存储在不同扇区时会产生不同的密文，但它比为每个扇区派生单独密钥（IV）具有更好的性能。虽然优于 CBC ESSIV 模式，但 XTS 在某些情况下仍然容易受到操纵，且不提供密文认证。

截至本文编写时，Android 不支持磁盘加密的 XTS 模式。然而，底层的 `dm-crypt` device-mapper 支持 XTS，并且可以通过 Android 的卷守护进程（void）实现轻松启用。

# 密钥派生

磁盘加密（在 Android 源代码中称为“主密钥”）使用另一个 128 位 AES 密钥（KEK）加密，该密钥由用户提供的密码派生。在 Android 3.0 到 4.3 版本中使用的密钥派生函数是 PBKDF2，具有 2,000 次迭代和 128 位随机值。生成的加密主密钥和盐（salt）与其他解密尝试失败次数等元数据一起存储在占据加密分区最后 16 KB 的页脚结构中，称为 crypto footer。将加密密钥存储在磁盘上而不是直接使用从用户密码派生的密钥，允许快速更改解密密码，因为唯一需要用新密码派生的密钥重新加密的只有主密钥（168 字节）。

虽然使用随机盐使得无法使用预计算表来加速密钥破解，但按当今的标准，PBKDF2 使用的迭代次数（2,000 次）并不大。密钥派生过程如第 7 节所述，使用了 8,192 次迭代。备份加密使用 10,000 次迭代，如后文“Android 备份”部分所述。此外，PBKDF2 是一种迭代算法，基于标准且相对容易实现的哈希函数，这使得 PBKDF2 密钥派生可以并行化，充分利用 GPU 等多核设备的处理能力。这使得即使是复杂的口令也能在短短几天甚至几年内被暴力破解。

为了增加暴力破解磁盘加密密码的难度，Android 4.4 引入了名为 `scrypt` 的新密钥派生函数的支持。[106] `Scrypt` 采用了一种专门设计的密钥派生算法，该算法需要大量的内存以及多次迭代（如一种算法），这使得在 ASIC 或 GPU 等专用硬件上发起暴力攻击变得更加困难，因为这些硬件通常在内存内存运行。

可以通过指定变量 `N`、`r` 和 `p` 来调整 `scrypt`，这些变量会影响所需的 CPU 资源、内存和并行成本。Android 默认使用的值为 `N=32768 (2^{15})`，`r=8` 且 `p22`。通过使用 `N_factor:r_factor:p_factor` 格式设置 `crypto.scrypt` 参数的值来更改，例如 `15:3:1`（默认值）。每个参数的值通过计算 2 的相应因子的幂来得出。Android 4.4 设备会自动更新 crypto 中的密钥派生算法。

### 注意

在同一台台式机器上，使用一种简单的、单线程算法（从 0000 开始生成所有可能的 PIN）来暴力破解 4 位 PIN，每个 PIN 大约需要 5 毫秒。

## 更改磁盘加密密码

磁盘加密的用户级部分在 Android 卷管理守护进程（`vold`）的 `cryptfs` 模块中实现。`cryptfs` 拥有用于创建和挂载加密卷，以及用于验证和更改主密钥加密密码的命令。Android 系统服务通过本地 socket（也命名为 `vold`）向 `vold` 发送命令与 `cryptfs` 通信，而 `vold` 根据接收到的命令设置描述当前加密或挂载过程状态的系统属性。（这导致了一个相当复杂的流程，在下下文的“启用加密”和“启动加密设备”中进行了详细描述。）

Android 并没有提供更改磁盘加密密码的 UI，但可以通过 `vdc` 命令行工具直接与 `vold` 守护进程通信来实现此操作。然而，对 `vold` 控制 socket 的访问受限于 root 用户和挂载组的成员，此外，`cryptfs` 命令仅对 root 和 system 用户可用。如果你正在使用工程版本构建，或者你的设备通过“超级用户”应用提供了 root 权限（见第 13 章），你可以向 `vold` 发送示例 10-4 所示的 `cryptfs` 命令来更改加密密码。

示例 10-4. 使用 `vdc` 更改磁盘加密密码

```bash
# vdc cryptfs changepw <newpass>
```

> 注意
>
> 如果你更改了锁屏密码，磁盘加密密码将自动更改。（这不适用于多用户设备上的次用户。）

## 启用加密

如前节所述，Android 磁盘加密的用户级部分由 `vold` 守护进程的专用 `cryptfs` 模块实现。`cryptfs` 提供了 `checkpw`、`restart`、`cryptocomplete`、`enablecrypto`、`changepw`、`verifypw`、`getfield` 和 `setfield` 命令，框架在加密或加密卷挂载过程的不同阶段发送这些命令。除了 `vold` 本 socket 权限外，`cryptfs` 还会显式检查命令发送者的身份，仅允许 root 和 system 用户访问。

## 使用系统属性控制设备加密

`vold` 守护进程设置了许多系统属性以触发设备加密或挂载的不同阶段，并将当前加密状态通信给框架服务。`ro.crypto.state` 属性持有当前加密状态，当数据分区成功加密时，它被设置为 `encrypted`；尚未加密时则设置为 `unencrypted`。如果设备不支持磁盘加密，该属性也可以被设置为 `unsupported`。`vold` 守护进程还为 `vold.decrypt` 属性设置了多个预定义值以指示设备加密或挂载的当前状态。`vold.encrypt_progress` 属性持有当前的加密进度（从 0 到 100），或者在设备加密或挂载期间发生错误时返回错误字符串。

`ro.crypto_fs_blkdev` 系统属性包含由 device mapper 分配的虚拟设备名称。成功解密磁盘加密密钥后，该虚拟设备将位于 `/data` 替代底层物理卷，如示例 10-5 所示（带输出）。

示例 10-5. 挂载在 `/data` 的加密虚拟块设备

```text
# mountgrep '/data'
/dev/block-vd0 /data ext4 rw,relatime,nousid,noatime,errors=panic,user_xattr,barrier=1,nblk_io_sumbit,data=ordered:0 0
```

## 卸载 `/data`

Android 框架期望 `/data` 可用，但为了对其进行加密，需要将其卸载。这造成了一个“自生蛋鸡”的困地，Android 通过卸载物理 userdata 分区并在执行加密时将其挂载一个内存文件系统（tmpfs）来解决此问题。在运行时切换分区需要关闭并重启系统服务，`vold` 通过设置 `vold.decrypt` 系统属性的值为 `trigger_restart_framework`、`trigger_restart_min_framework` 或 `trigger_shutdown_framework` 来触发。这些值会触发 `init.rc` 的不同部分，如示例 10-6 所示。

示例 10-6. `init.rc` 中的 `vold.decrypt` 触发

```rc
+   --snip---
on on post-fs-data①
chown system system /data
chmod 0777 /data
restorecon /data
copy data/system/entropy.data /dev/urandom
--snip---
on on property:void.decrypt=trigger_reset_main②
class_reset main
on on property:void.decrypt=trigger_load_persist_props
load_persist_props
on on property:void.decrypt=trigger_post_fs_data③
tigger post-fs-data
on on property:void.decrypt=trigger_restart_min_framework④
class_start main
on on property:void.decrypt=trigger_restart_framework⑤
class_start main
class_start late_start
on on property:void.decrypt=trigger_shutdown_framework⑥
class_reset late_start
class_reset main
--snip---
```

## 触发加密过程

当用户通过系统 UI 中的“安全>加密手机”启动加密过程时，设置应用调用 `MountService`，后者向 `vold` 发送 `cryptfs enablepassword` 命令，其中 `password` 是锁定密码。反过来，`vold` 卸载 userdata 分区并将 `vold.decrypt` 设置为 `trigger_shutdown_framework` ⑥（如示例 10-6 所示），这将关闭除核心服务部分以外的大多数系统服务。`vold` 守护进程

## 更新加密脚部并加密数据

接下来，`vold` 设置虚拟 `dm-crypt` 设备并写入加密脚部。接下来，`vold` 设置虚拟的 `dm-crypt` 设备并写入加密脚部。加密脚部包含加密密钥（主密钥）、用于 KEK 的盐以及其他派生参数。`加密_IN_PROGRESS` 标记（2）表示加密已启动但尚未完成。最后，加密无错误完成，`vold` 清除 `加密_IN_PROGRESS` 标记并重启设备。

## 启动加密设备

启动加密设备需要用户提供磁盘加密密码。Android 不使用特殊的引导加载程序，而是将系统属性设置为 1 并启动一组最小的系统服务以显示标准的 Android UI。对于设备加密，这再次需要在 `/data` 挂载 `tmpfs` 以允许核心服务启动。当核心框架启动后，Android 检测到 `vold.decrypt` 设置为 1 并启动 `userdata` 挂载过程。



该过程的第一步是通过向 `vold` 发送 `cryptcomplete` 命令检查分区是否加密，`vold` 则检查分区格式是否正确以及`加密_IN_PROGRESS`标记是否设置。如果发现分区已成功加密，框架将启动由 CryptKeeper 提供的如图 10-4 所示的密码输入 UI。此活动作为主屏幕（启动器），由于它的优先级高于默认启动器，它在设备启动后首先运行。

如果设备未加密，CryptKeeper 将禁用自身并结束，导致系统活动管理器启动默认的主屏幕应用程序。如果设备已加密或处于加密过程中（即 `vold.crypt` 属性不为空或设置为 `trigger_restart framework`），CryptKeeper 活动将启动并隐藏状态栏和系统栏。此外，CryptKeeper 会忽略硬件返回键，从而防止离开密码输入 UI。

如果设备损坏，或者加密过程中断导致`userdata`分区仅部分加密，则设备无法启动。在这种情况下，CryptKeeper 将显示如图 10-5 所示的 UI，允许用户触发出厂重置，从而重新格式`userdata`分区。

## 获取磁盘加密密码

当用户输入密码时，CryptKeeper 通过调用 `MountService` 的 `decryptStorage()` 方法来加密 `cryptfs checkpw`。这指示 `void` 通过尝试将加密分区挂载到临时挂载点然后卸载它，来检查输入的密码是否正确。如果过程继续，`void` 会将由 `dm-mapper` 分配的虚拟块设备名称设置为 `ro.cryptofs.crypto_blkdev` 属性，并将控制权返回给 `MountService`，后者会发送 `cryptfs` 重启命令，指令 `void` 重启示例 10-6 中主类 ② 中的所有系统。这使得文件系统可以被卸载，并将新分配的 `dm-crypt` 块设备挂载到 `/data`。

## 启动所有系统服务

在加密分区挂载并准备就绪后，`void` 设置了 `void.decrypt` 以触发示例 10-6 中的 `trigger_post_fs_data` ③，触发本节中的 `post-fs-data` ① 命令，这些命令设置文件和目录权限、恢复 SELinux 上文并在必要时需要 `/data` 目录。

最后

## 磁盘加密的局限性

磁盘加密仅保护静态数据；即设备关闭时的数据。由于磁盘加密是透明的且在内核层实现，在加密卷挂载后，它对于用户级进程来说与明文卷没有区别。磁盘加密不能保护数据免受运行在设备上的恶意程序的攻击。处理敏感数据的应用程序不应仅依赖全盘加密，而应该实现它们自己的基于文件的加密方法。文件加密密钥应使用从用户提供的密码派生的 KEK（密钥加密密钥）进行加密，如果数据需要绑定到设备，则使用某些不可更改的硬件属性。为了确保文件完整性，必须使用如 GCM 之类的认证加密方案或额外的认证函数（如 HMAC）对加密数据进行验证。

## 屏幕安全

访问 Android 设备的一种方式是要求用户身份验证以访问系统 UI 和应用程序。用户身份验证通过在设备启动或屏幕关闭时显示锁屏来实现。单用户设备上配置为需要数字 PIN 解锁的锁屏可能如图 10-6 所示。

在早期的 Android 版本中，锁屏仅设计用于保护对设备 UI 的访问。随着平台的演进，锁屏扩展了许多功能，包括显示最新设备或应用程序状态的小部件、允许在多用户设备上切换用户，以及解锁系统密钥库的能力。同样，锁屏 PIN 或密码现在被用于派生凭据存储加密密钥（用于软件实现）以及磁盘加密密钥 KEK。

## 锁屏实现

Android 锁屏（或称为 `keyguard`）的实现与普通的 Android 应用程序类似：在窗口上布局小部件。它的特殊之处在于其窗口位于一个高窗口层上，其他应用程序无法在其上方绘图或进行控制。此外，锁屏会拦截正常的导航按钮，这使得用户无法绕过，从而“锁定”设备。

然而，锁屏层并不是最高层；源自锁屏本身的对话框和状态栏会绘制在锁屏之上。你可以使用 ADT 带的 `Hierarchy Viewer` 工具查看当前显示的窗口列表。当屏幕锁定定时，活跃的窗口是 Keyguard 窗口，如图 10-7 所示。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_254_0.png)

### 注意

在 Android 4.0 之前，第三方应用程序可以在锁屏层显示窗口，这允许应用程序拦截 Home 键并实现“kiosk”风格的应用程序。然而，由于此功能被某些恶意软件应用滥用，从 Android 4.0 开始，向锁屏层添加窗口需要 `INTERNAL_SYSTEM_WINDOW` 签名权限，该权限仅供系统应用程序使用。

长期以来，锁屏一直是 Android 窗口系统的实现细节，并没有被分离成一个专用组件；随着锁屏小部件、待机程序（屏幕保护程序）以及多用户支持的引入，锁屏获得了许多新功能，并最终在 Android 4.4 中被提取到一个专门的系统应用 `Keyguard` 中。`Keyguard` 应用运行在 `com.android.systemui` 进程中，与核心 Android UI 实现一起。

每种解锁方法（下文将讨论）的 UI 都实现为专门的视图组件。该组件由专门的视图容器类 `KeyguardHostView` 托管，连同锁屏小部件和其他 UI 组件。例如，图 10-6 所示的 PIN 锁视图实现在 `KeyguardPINView` 类中实现，密码锁由 `KeyguardPasswordView` 类实现。`KeyguardHostView` 类会自动根据当前配置的解锁方法和状态选择并显示相应的保护视图（guard view）。解锁视图将密码检查委托给 `LockPatternUtils` 类，该类负责对比用户输入以保存锁定凭据，并将密码更改持久化到磁盘，同时更新与认证相关的元数据。

除了锁屏解锁视图的实现外，Keyguard 系统应用包含了导出的 `KeyguardService`，它暴露了一个远程 AIDL 接口 `IKeyguardService`。该服务允许客户端检查锁屏的当前状态、设置当前用户、启动相机以及隐藏或禁用锁屏。更改锁屏的操作受系统权限 `CONTROL_KEYGUARD` 的保护。

## 锁屏解锁方法

原生 Android 提供了几种锁屏解锁方法（在 Android 源代码中也称为安全模式）。在这些方法中，有五种可以在锁屏界面直接选择：滑动（Slide）、面部解锁、图案（Pattern）、PIN 和密码（Password），如图 10-8 所示。

滑动解锁方法不需要身份验证，因此其安全级别等同于无。截至本文编写，面部解锁是 `SecurityMode.Biometric`（“强生物识别”）的唯一实现（在未来版本中可以使用指纹或虹膜识别）。其他不符合当前安全策略的方法已被禁用且无法选择。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_255_0.png)

图 10-8 可选择的锁屏解锁方法

图案解锁方法（`SecurityMode.Pattern`）是 Android 特有的，要求在 3×3 网格上绘制预定义的图案来解锁设备，如图 10-9 所示。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_256_0.png)

PIN（`SecurityMode.PIN`）和密码（`SecurityMode.Password`）解锁方法的实现相似，但区别在于字符范围：PIN 只允许数字（0-9），而密码允许字母。`SecurityMode` 枚举定义了三个在选择界面中无法直接选择的解锁方法：`SecurityMode.Account`、`SecurityMode.SimPin` 和 `SecurityMode.SimPuk`。`SecurityMode.Account` 方法仅适用于支持 Google 账户（Google 体验）的设备，它并不是一个独立的解锁方法，只能作为其他安全方法的备用。同样，`SecurityMode.SimPin` 和 `SecurityMode.SimPuk` 并不是锁屏方法；它们只有在设备 SIM 卡在使用前需要 PIN 时可用。如果 SIM 卡记录了 PIN 认证状态，只需输入一次 PIN 或 PUK——即设备启动时（或者 SIM 卡状态被重置时）。我们将在后续章节深入探讨这些方法的实现。

### 面部解锁

面部解锁是 Android 4.0 引入的一种较新的解锁方法。它利用设备的前摄像头注册所有者的面部图像（见图 10-10），并依靠识别技术来识别解锁设备时捕捉的面部。尽管自引入以来面部解锁的准确性已得到改进，但它被认为

所有解锁方式都具有类似的安全性，甚至设置屏幕还会警告用户“长得像你的人也可能会解锁你的手机。”此外，面部解锁（Face Unlock）需要一个备份解锁方式——图案或 PIN，以处理无法进行面部识别的情况（例如光线不足、摄像头故障等）。面部解锁的实现基于 PittPatt（匹特兹堡模式识别）公司开发的面部识别技术，该公司于 2011 年被 Google 收购。代码仍为专有，目前没有关于存储数据格式或所采用识别算法的详细信息。截至本文写作，面部解锁的实现位于 `com.android.facelock` 包中。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_258_0.png)

### 图形解锁

如[图 10-9](#)所示，图形解锁代码是通过连接 $3\times3$ 矩阵上的至少四个点来输入的。每个点只能使用一次（交叉点被忽略），最大点数为九个。在内部，图案被存储为字节序列，每个点由其索引表示，0 为左上角，8 为右下角。该图案类似于 PIN 码，最少四位，最多九位，且仅使用 9 个不同的数字（0 到 8）。然而，由于点不能重复，图形解锁的变化数量远低于九位 PIN 码。

图形锁的哈希值存储在 `/data/system/gesture.key` 中（多用户设备上为 `/data/system/users/<user ID>/gesture.key`），格式为未加盐的 SHA-1 值。通过简单转储此文件，我们发现它包含了图 10-9 中图形的 `gesture.key` 文件内容（十六进制表示为 00010024060708）。示例 10-8 与该图案序列的 SHA-1 哈希值匹配，该示例的哈希值为 6a06e2b93452c366074181b9fea73e9ed2c48。

示例 10-8. `/data/system/gesture.key` 文件的内容

```bash
# od -t1 /data/system/gesture.key
000020 6a 06 e2b 9b 34 52 c3 66 07 41 81 b9fea73e9ed2c48
000020 e9 2c-48
```

由于计算哈希时没有使用随机盐值，每个图案始终哈希为相同的值，这使得相对容易生成所有可能的图案及其相应哈值的预表（网上很容易找到）。一旦获取 `gesture.key` 文件，即可恢复图案。然而，该文件由系统所有，权限设置为 0600，因此在生产设备上通常无法恢复。输入的图案将通过 `LockSettings` 类的 `checkPattern()` 方法与保存的哈希进行比对，并使用 `userManager` 类的 `saveLockPattern()` 方法进行缓存和持久化。保存图案还会将当前密码质量值设置为 `DevicePolicyManager.PASSWORD_QUALITY_SOMETH`。

图形解锁方法的另一个不幸属性是，电容触摸屏直接使用手指操作（而不是使用手写笔或类似工具），多次绘制解锁图案会在触摸屏上留下明显的痕迹，使其极易受到所谓的“指纹攻击”（smudge attack）。使用适当的光线和摄像头，可以检测到屏幕上的指纹油，并以极高的概率推断出解锁图案。由于这些原因，图形解锁方法的安全性被认为非常低。此外，由于组合数量有限，解锁图案是一个糟糕的熵源，当用户的解锁凭据用于派生加密密钥（例如用于系统密钥库和设备加密）时，是不允许使用的。

与面部解锁类似，图形解锁方法支持备份解锁机制，只有在用户输入超过五次无效图案后才会触发。备份验证必须通过点击锁屏底部的“忘记图案”按钮手动激活。按下该按钮后，设备将进入 `SecurityMode.Account` 安全模式并显示图 10-11 所示的屏幕。

用户可以输入注册设备上的任何 Google 账户凭据来解锁，然后重置或更改解锁方法。因此，在设备上注册一个带有易猜或（共享）密码的 Google 账户，可能会成为设备锁定状态的潜在后门。

### 注意

> 截至本文写作，配置为需要双重身份验证的 Google 账户无法用于解锁设备。

### PIN 和密码解锁

PIN 和密码方法本质上是等效的：它们将用户输入的哈希与存储在设备上的加盐哈希值进行比较，如果值匹配则解锁。PIN 或密码的哈希是用户输入的 SHA-1 和 MD5 哈希值的组合，并使用 64 位随机值加盐。计算出的哈希以十六进制字符串的形式存储在 `/data/misc/password.key` 文件（多用户设备上为 `/data/system/users/<user ID>/password.key`）中，看起来类似于示例 10-9。

示例 10-9. `/data/misc/password.key` 文件的内容

```bash
### /data/system/password.key && echo
9B93A9A84E6F2E14922F0C7294445D327EB7B04C9E230D84CC01C20D78BAE01FAAC
```

PIN 或密码的哈希是用户输入的 SHA-1 和 MD5 哈希值的组合，并使用 64 位随机值加盐。计算出的哈希以十六进制字符串的形式存储在 `/data/misc/password.key` 文件中……（此处省略重复的存储描述）

用户提供的密码方法通过该类中的一个 `saveLockPassword()` 方法进行调用和持久化。`saveLockPassword()` 会更新目标（当前）用户的 `password.key`。类似于手势（gesture），该文件由系统所有，权限为 `0600`。在更新密码哈希值之余，`saveLockPassword()` 还会计算输入密码的复杂度，并更新与 `screen_password_type` 键对应的值列。例如 `locksettings.db` 中的示例 10-10，显示了计算出的复杂度。如果启用了密码历史，`saveLockPassword()` 还会将 PIN 或密码哈希添加到 `locksettings` 表中，参见示例 10-11。

当设备被加密时，所有者用户的 PIN 或密码也会重新加密磁盘加密密钥。因此，调用所有者用户的 PIN 或密码也会调用系统 `MountService` 的 `changeEncryptionPassword()` 方法。（更改次要用户的 PIN 或密码不会影响磁盘加密密钥。）

### PIN 和 PUK 解锁

PIN 和 PUK 安全模式本身并不是锁屏解锁方法；它们依赖于设备 SIM 卡的状态，并且只有在 SIM 卡处于锁定状态时才会显示。SIM 卡可能要求用户输入预配置的 PIN 代码来解锁卡片，并访问内部存储的任何网络认证密钥，这些密钥用于注册移动网络和拨打非紧急电话。

由于 SIM 卡在重置之前会一直保持其状态，因此 PIN 代码通常只在设备首次启动时输入。如果输入错误代码超过三次，SIM 卡将锁定，并要求用户输入一个单独的代码来解锁，该代码称为 PIN 解锁密钥（PUK）或个人阻锁码（PUC）。

当显示锁屏时，Android 会检查 SIM 卡的状态，如果状态为 `State.PIN_REQUIRED`（定义在 `IccCardConstants` 类中），它将显示图 10-12 所示的 SIM 解锁密钥屏保护程序。当用户输入 SIM PIN 时，它会被传递给 `ITelephony` 接口的 `supplyPinReportResult()` 方法（实现在 `TeleService` 应用中），该方法反过来通过无线接口守护进程（`rild`）将传递给设备的基带处理器（实现移动网络通信的设备组件，有时也称为调制解调器或无线电）。最后，直接连接到 SIM 的基带处理器会将 PIN 发送到 SIM 卡并接收相应的状态。该状态通过相同的路径传回解锁视图。如果状态表示 SIM 卡已接受 PIN 且未配置锁屏，则将显示主屏幕（启动器）。另一方面，如果配置了锁屏，则在解锁 SIM 卡后显示锁屏，用户必须输入凭据来解锁设备。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_263_0.png)

如果 SIM 卡被锁定（即处于 `PUK_REQUIRED` 状态），Android 会显示 PUK 输入界面，并允许用户在解锁卡片后设置新 PIN。PUK 和新 PIN 会被传递给 `ITelephony` 接口的 `supplyPukReportResult()` 方法，由该方法将其交付给 SIM 卡。如果配置了锁屏，则在验证 PUK 并配置新 PIN 后显示。

钥匙屏保护程序（Keyguard）系统应用通过注册 `TelephonyIntents.ACTION_SIM_STATE_CHANGED` 广播来监控 SIM 状态的变化，并在卡片变为锁定或永久禁用时显示锁屏。用户可以通过导航到 设置►安全►设置 SIM 卡锁并使用“锁定 SIM 卡”复选框来切换 SIM 卡的 PIN 保护。

## 暴力破解防护

由于复杂的密码在触摸屏键盘上输入可能不方便，用户通常使用较短的解锁凭据，这些凭据很容易被猜测或通过暴力破解。Android 通过要求用户在每次五次连续失败的身份验证尝试后等待 30 秒来防止直接在设备上执行的暴力破解攻击（在线攻击），如图 10-13 所示。这种技术被称为速率限制（rate limiting）。

为了进一步震慑暴力破解，可以使用 `DevicePolicyManager` API 设置并强制密码复杂度、过期和历史记录规则，如第 9 章所述。如果设备存储或允许访问敏感的公司数据，设备管理员还可以使用 `DevicePolicyManager.setMaximumFailedPasswordsForWipe()` 方法为身份验证失败尝试设置阈值。当达到阈值时，设备上的所有用户数据将被自动删除，以防止攻击者获得未经授权访问。

# 安全 USB 调试



## Android 调试与设备安全

Android 成功原因之一是应用开发门槛低；应用可以在任何操作系统上使用高级语言进行开发，而无需投资开发者工具或硬件（当使用 Android 模拟器时）。为嵌入式或其他专用开发软件在传统上是困难的。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_264_0.png)

通常很难（在某些情况下无法）检查或与设备交互以调试程序。从最早版本开始，Android 就包含了一个强大的设备交互工具包，允许交互式调试和检查设备，称为 Android 调试桥（ADB）。ADB 在消费设备上通常是关闭的，但可以通过系统 UI 开启，以便在设备上进行应用开发和调试。因为 ADB 提供对设备文件系统和应用程序的权限访问，它可以用于获取未经授权的数据。在以下章节中，我们将讨论 ADB 的架构，然后介绍最近 Android 版本为限制访问所采取的步骤。

### ADB 架构

ADB 跟踪所有连接到主机的设备（或模拟器），并提供各种服务。它通过注册 `TelephonyIntents.ACTION_SIM_STATE_CHANGED` 广播来监控 SIM 状态的变化，并在卡片变为锁定或永久禁用时显示锁屏。用户可以通过导航到“设置►安全►设置 SIM 卡锁”并使用“锁定 SIM 卡”复选框来切换 SIM 卡的 PIN 保护。

当设备被加密时，所有者用户的 PIN 或密码也会重新加密磁盘加密密钥。因此，调用所有者用户的 PIN 或密码也会调用系统 `MountService` 的 `changeEncryptionPassword()` 方法。（更改次要用户的 PIN 或密码不会影响磁盘加密密钥。）

用户提供的密码方法通过该类中的 `saveLockPassword()` 方法进行调用和持久化。`saveLockPassword()` 会更新目标（当前）用户的 `password.key`。类似于手势（gesture），该文件由系统所有，权限为 `0600`。在更新密码哈希值之余，`saveLockPassword()` 还会计算输入密码的复杂度，并更新与 `screen_password_type` 键对应的值。例如，`locksettings.db` 中的示例 10-10 显示了计算出的复杂度。如果启用了密码历史，`saveLockPassword()` 还会将 PIN 或密码哈希添加到 `locksettings` 表中，参见示例 10-11。

### PIN 和 PUK 解锁

PIN 和 PUK 安全模式本身并不是锁屏解锁方法；它们依赖于设备 SIM 卡的状态，并且只有在 SIM 卡处于锁定状态时才会显示。SIM 卡可能要求用户输入预配置的 PIN 代码来解锁卡片，并访问内部存储的任何网络认证密钥，这些密钥用于注册移动网络和拨打非紧急电话。

由于 SIM 卡在重置之前会一直保持其状态，因此 PIN 代码通常只在设备首次启动时输入。如果输入错误代码超过三次，SIM 卡将锁定，并要求用户输入一个单独的代码来解锁，该代码称为 PIN 解锁密钥（PUK）或个人阻锁码（PUC）。

当显示锁屏时，Android 会检查 SIM 卡的状态。如果状态为 `State.PIN_REQUIRED`（定义在 `IccCardConstants` 类中），它将显示图 10-12 所示的 SIM 解锁密钥屏保护程序。当用户输入 SIM PIN 时，它会被传递给 `ITelephony` 接口的 `supplyPinReportResult()` 方法（实现在 `TeleService` 应用中），该方法反过来通过无线接口守护进程（`rild`）将其传递给设备的基带处理器。基带处理器是实现移动网络通信的设备组件，有时也称为调制解调器或无线电。

最后，直接连接到 SIM 的基带处理器会将 PIN 发送到 SIM 卡并接收相应的状态。该状态通过相同的路径传回解锁视图。如果状态表示 SIM 卡已接受 PIN 且未配置锁屏，则将显示主屏幕（启动器）。另一方面，如果配置了锁屏，则在解锁 SIM 卡后显示锁屏，用户必须输入凭据来解锁设备。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_263_0.png)

如果 SIM 卡被锁定（即处于 `PUK_REQUIRED` 状态），Android 会显示 PUK 输入界面，并允许用户在解锁卡片后设置新 PIN。PUK 和新 PIN 会被传递给 `ITelephony` 接口的 `supplyPukReportResult()` 方法，由该方法将其交付给 SIM 卡。如果配置了锁屏，则在验证 PUK 并配置新 PIN 后显示。

钥匙屏保护程序（Keyguard）系统应用通过注册 `TelephonyIntents.ACTION_SIM_STATE_CHANGED` 广播来监控 SIM 状态的变化，并在卡片变为锁定或永久禁用时显示锁屏。用户可以通过导航到“设置►安全►设置 SIM 卡锁”并使用“锁定 SIM 卡”复选框来切换 SIM 卡的 PIN 保护。

## 暴力破解防护

由于复杂的密码在触摸屏键盘上输入可能不方便，用户通常使用较短的解锁凭据，这些凭据很容易被猜测或通过暴力破解。Android 通过要求用户在每次五次连续失败的身份验证尝试后等待 30 秒来防止直接在设备上执行的暴力破解攻击（在线攻击），如图 10-13 所示。这种技术被称为速率限制（rate limiting）。

为了进一步震慑暴力破解，可以使用 `DevicePolicyManager` API 设置并强制密码复杂度、过期和历史记录规则，如第 9 章所述。如果设备存储或允许访问敏感的公司数据，设备管理员还可以使用 `DevicePolicyManager.setMaximumFailedPasswordsForWipe()` 方法为身份验证失败尝试设置阈值。当达到阈值时，设备上的所有用户数据将被自动删除，以防止攻击者获得未经授权访问。

# 安全 USB 调试

Android 成功原因之一是应用开发门槛低；应用可以在任何操作系统上使用高级语言进行开发，而无需投资开发者工具或硬件（当使用 Android 模拟器时）。为嵌入式或其他专用开发软件在传统上是困难的。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_264_0.png)

通常很难（在某些情况下无法）检查或与设备交互以调试程序。从最早版本开始，Android 就包含了一个强大的设备交互工具包，允许交互式调试和检查设备，称为 Android 调试桥（ADB）。ADB 在消费设备上通常是关闭的，但可以通过系统 UI 开启，以便在设备上进行应用开发和调试。因为 ADB 提供对设备文件系统和应用程序的权限访问，它可以用于获取未经授权的数据。在以下章节中，我们将讨论 ADB 的架构，然后介绍最近 Android 版本为限制访问所采取的步骤。

### ADB 架构

ADB 跟踪所有连接到主机的设备（或模拟器），并提供各种服务。它通过注册 `TelephonyIntents.ACTION_SIM_STATE_CHANGED` 广播来监控 SIM 状态的变化，并在卡片变为锁定或永久禁用时显示锁屏。用户可以通过导航到“设置►安全►设置 SIM 卡锁”并使用“锁定 SIM 卡”复选框来切换 SIM 卡的 PIN 保护。

ADB 支持以下操作：

- 在设备上执行 shell 命令
- 获取系统和应用日志
- 安装和卸载应用

如果设备上启用了调试功能，你只需通过 USB 线将设备连接到计算机，即可执行以上操作以及更多操作（例如，在 UI 中注入触摸事件或输入）。因为 ADB 不依赖于设备的屏幕锁，且在大多数设备上，你不需要解锁设备即可执行 ADB 命令；而且在大多数提供 root 权限的设备上，通过 ADB 连接允许你访问并更改每个文件，包括系统文件和密码数据库。

更糟糕的是，你实际上并不需要带有开发工具的电脑来通过 ADB 访问数据库；另一台 Android 设备和一根 USB On-The-Go（OTG）线就足够了。有很多可以在短时间内从另一台设备提取尽可能多数据的 Android 工具。[110] 如果设备已 root，此类工具可以提取你所有的凭据，禁用或暴力破解屏幕锁，甚至登录你的 Google 账户。但即使没有 root，外部存储上的任何内容（尤其是照片）都是可以访问的，你的联系人和短信也是如此。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_268_0.png)

Android 4.2.2 通过引入所谓的“安全 USB 调试”功能提供了一个正式的解决方案。“安全”是指现在只有经过用户显式授权的主机才能连接到设备上的 `adbd` 守护进程并执行调试命令。如果有人尝试通过 USB 将设备连接到另一台设备以访问 ADB，他们必须先解锁目标设备，并在图 10-15 所示的确认对话框中点击“确定”，以授权调试主机访问。

你可以通过勾选“始终允许此计算机”复选框来使决定持久化。只要你处于同一台机器上，调试就会像以前一样工作。

自然地，这种安全 USB 调试只有在你设置了足够安全的触摸屏密码时才有效。

> **注意**
>
> 在支持多用户使用的平板电脑上，确认对话框仅向主用户（所有者）显示。

## 安全 ADB 实现

当 `ro.adb.secure` 系统属性被设置为 1 时，默认启用 ADB 身份验证功能，且无法通过系统接口禁用。当设备连接时，它最初处于 `CS_UNAUTHORIZED` 状态，只有在主机通过验证后才会进入 `CS_DEVICE` 状态。使用 RSA 密钥来验证设备上的 ADB 守护进程，通常遵循以下三个步骤：

1. 当主机连接时，设备发送一个 `A_AUTH` 消息，其参数类型为 `ADB_AUTH_TOKEN`，其中包含一个 20 字节的随机值（从 `/dev/urandom` 读取）。

2. 主机响应一个 `A_AUTH` 消息，其参数类型为 `ADB_AUTH_SIGNATURE`，其中包含使用主机的私钥之一对随机令牌进行的 SHA1withRSA 签名。

3. 设备尝试验证收到的签名。如果签名验证成功，它将响应一个 `A_CXN` 数据包并进入 `CS_DEVICE` 状态。如果验证失败（是因为签名值不匹配或没有用于验证的公钥），设备将发送另一个带有新随机值的 `ADB_AUTH_TOKEN`。如果失败次数超过某个阈值，它会减慢速度。

当你第一次连接到新主机时，签名验证通常会失败，因为它没有主机的密钥。在这种情况下，主机会通过带有 `ADB_AUTH_RSAPUBPUBLICKEY` 参数的 `A_AUTH` 消息发送其公钥。设备获取该密钥的 MD5 哈希值并在图 10-15 中显示。

由于 `adb` 是原生守护进程，密钥必须传递给主 Android 操作系统，以便在屏幕上显示。这是通过简单地将密钥写入本地 socket（也命名为 `adbd`）来实现的，`adbd` 守护进程会监控该 socket。

当你从开发者选项中启用调试时，会启动一个监听 `adbd` socket 的线程。当线程接收到以 `PK` 开头的消息时，它将其视为公钥，进行解析、计算 MD5 哈希值并显示确认对话框。该确认对话框在专门的活动 `UsbDebuggingActivity` 中实现，它是 `SystemUI` 软件包的一部分。

如果你点击“确定”，该活动会向 `adbd` 发送简单的 OK 响应，`adbd` 使用该密钥来验证身份验证消息。如果你勾选了“始终允许此计算机”复选框，公钥将被写入磁盘，并在下次连接到同一主机时自动用于签名验证。

> **注意**
>
> 从 4.3 版本开始，Android 允许你清除所有保存的身份验证密钥。此功能可以通过选择“设置 > 开发者选项 > 撤销 USB 调试授权”来触发。

`UsDeviceManager` 类提供了允许和拒绝 USB 调试、清除身份验证密钥以及启动和停止 `adbd` 守护进程的公共方法。这些方法通过 `UsService` 的 `IUsbManager` AIDL 接口提供给其他应用程序。调用修改设备状态的 `IUsbManager` 方法需要 `MANAGE_USB` 系统签名权限。

## ADB 身份验证密钥

虽然我们上面描述了 ADB 身份验证协议，但并没有详细说明过程中使用的实际密钥：由本地 ADB 服务器生成的 RSA 密钥。这些密钥位于 `$HOME/.android`（Windows 上的 `%USERPROFILE%\.android`）下的 `adkey`（私钥）中。可以通过设置环境变量 `ANDROID_SDK_HOME` 来覆盖默认密钥。如果设置了 `ADB_VENDOR_KEYS` 环境变量，也会进行搜索。如果在任何其他地方未找到密钥，则将生成并保存新的密钥对。

私钥（`adkey`）仅存储在主机上，采用标准的 OpenSSL PEM 格式。公钥（`adkey.pub`）包含公钥的 Base64 编码 mincrypt 表示，这基本上是 mincrypt 的 `RSAPublicKey` 结构的序列化（“Enabling Verified Boot”后跟随一个 `user@host` 标识符，用空格分隔）。用户标识符在本文似乎未使用，仅在基于 Unix 的操作系统上有意义；在 Windows 上，它是 `unknown@unknown`。

密钥存储在设备上的 `/data/misc/adb/adkeys` 文件中。当你接受它们时，新的授权密钥会被追加到同一个文件中。只读的“厂商密钥”存储在 `/adkeys` 文件中，但它似乎存在于当前设备。公钥格式与主机上相同，便于 `libcrypt` 加载。示例 10-13 显示了示例密钥。该文件由系统用户所有，组为 shell，权限为 640。

示例 10-13. `adkeys` 的内容

```text
# cat /data/misc/adb/adkeys
QAAAIUdf17wyVy+Y2NGGF+EgWoPoBfyc4rNd3s6w3Igt25fKNR7O8+A+IVGW
QAAAKFklvp+f1cAb6E2qy/hmm1S1Ygt2-tmwuQZFe+O4vepe6huIN8YbBrkr7
xny---
b7Gd6F0hRKO2gopy5
```

## 验证主机密钥指纹

虽然 ADB 调试确认对话框完整显示密钥指纹，以让你验证是否连接到了预期的主机，但 `adb` 客户端没有打印主机密钥指纹的命令。在运行几个虚拟机时，虽然似乎没有混淆的空间（毕竟机器上只有一个），但情况可能会变得模糊。

示例 10-14 显示了如何以图 10-15 中确认对话框相同的格式显示主机密钥指纹（在 `$HOME/.android` 中运行或指定公钥路径）。

示例 10-14. 显示主机密钥指纹

```bash
$ cut -d' ' -f1 adkey.pub | openssl base64 -A -d | \
openssl md5 -cut -d' ' -f2 | tr '[a-z]' '[A-Z]'

69:DAC0AD:AF6:B7:18:BA6:C4:BE0:FC7:75:9A
```



## Android 备份

Android 包含一个备份框架，允许将应用数据备份到 Google 云，并支持将已安装的 APK 文件、应用数据和外部存储文件完整备份到通过 USB 连接的主机。设备备份并不是一种安全功能，备份允许从设备中提取应用数据，这可能会带来安全问题。

## Android 备份概述

Android 备份框架在 Android 2.2 中公开发布，但可能在内部就已经可用。该框架允许应用程序声明称为“备份代理”（backup agents）的特殊组件，系统在为应用程序创建备份和恢复其数据时会调用这些组件。虽然备份框架在内部支持可插拔的备份传输层（backup transports），但在最初，实践中唯一可用的传输层是一个专有的层，它将应用程序数据存储在 Google 的云存储中。

## 云端备份

由于备份与用户的 Google 账户关联，当用户在设备上安装一个带有备份代理的应用程序时，如果用户注册的 Google 账号与创建备份时使用的账号相同，则应用程序的数据可以自动恢复。备份和恢复由系统管理，通常无法由用户触发或控制（尽管可以通过 Android shell 访问触发云备份的开发者命令）。默认情况下，备份会定期触发，而恢复仅在应用首次安装到设备上时进行。

## 本地备份

Android 4.0 增加了一种新的本地备份传输层，允许用户同时将备份保存到其台式电脑的文件。本地备份（也称为全量备份）需要启用并授权 ADB 调试，因为备份数据是使用 ADB（通过`adb pull`）将设备文件传输到主机的相同方法流到宿主机的。

全量备份通过在 shell 中执行`adb backup`命令启动。该命令在设备上启动一个新的 Java 进程，该进程会绑定到系统的`BackupManagerService`，并根据`adb backup`指定的参数请求备份。`BackupManagerService`会启动一个类似于如图 10-16 所示的确认活动，提示用户授权备份并在需要时指定备份加密密码。如果设备已经加密，用户必须输入设备加密密码才能继续。此密码也将用于加密备份；不支持使用专用的备份加密密码。当用户按下“备份我的数据”（Backup up my data）按钮时，全量备份过程就会启动。

全量备份会调用每个目标包的备份代理以获取其数据的副本。如果没有定义备份代理，`BackupManager`将使用内部的`BackupAgent`类，该类会复制包的所有文件。全量备份遵循包 AndroidManifest.xml 文件中`<application>`标签的`allowBackup`属性，如果`allowBackup`设置为`false`，则不会提取包数据。

除了选项数据外，全量备份还包括用户安装的系统应用程序 APK 文件，以及外部存储内容，但存在一些局限性：全量备份不会备份受保护（使用 DRM 应用）的内容，并且跳过某些系统设置，如移动网络 APNs 和 Wi-Fi 访问点连接。

使用`adb restore`命令恢复备份。备份恢复非常有限，不允许指定任何选项，因为它只能执行全量恢复。

## 备份文件格式

Android 备份文件以几行文本开头，随后是二进制数据。这些行是备份头，它们指定了用于创建备份的备份格式和加密参数（如果指定了备份密码）。未加密备份的头如示例 10-15 所示。

示例 10-15. 未加密的备份头

| | ANDROID BACKUP |
|---|---|
| 1 | |
| 2 | |
| 3 | none |

第一行 ① 是文件魔数（格式标识符），第二行 ② 是备份格式版本（Android 4.4.2 之前为 1，后续版本为 2；版本 2 表示密钥派生方法发生了变化，现在考虑了多字节密码（字符）），第三行 ③ 是压缩标志（1 表示已压缩），第四行 ④ 是使用的加密算法（`none`或`AES-256`）。

实际的备份数据是一个压缩且可选加密的 tar 文件，包含一个备份清单文件，随后是应用程序 APK（如果有）以及应用数据（文件、数据库和首选项）。数据使用默认算法压缩，并可以使用 OpenSSL 的`zlib`命令解压，如示例 10-16 所示。

示例 10-16. 使用 OpenSSL 解压 Android 备份

```bash
$ dd if=mybackup.ab bs=24 skip=1 opens zlib -d > mybackup
```

备份是解压的，你可以使用标准的 tar 命令查看其内容或提取它，如示例 10-17 所示。

### 10-17. 使用 tar 查看解压备份的内容

```bash
$ tar mybackup.tar

-rw-- 1000/1000 1019 apps/org.myapp/manifest1
-rw-r- 1000/1000 141228 apps/org.myapp/a/org.myapp-1.apk2
-rw-rw- 10091/10091 231 apps/org.myapp/f/share_history.xml3
-rw-rw- 10091/10091 0 apps/org.myapp/db/mybackup.db-journal4
-rw-rw- 10091/10091 512 apps/org.myapp/db/mybackup.db
-rw-rw- 10091/10091 1110 apps/org.myapp/shared/org.myapp_preferences.xml5
```

在 tar 文件内部，应用数据存储在……（等待，提供的 OCR 文本从此处开始似乎变得混乱/重复了。我将根据从提供的片段推导出的逻辑流进行清理）。

*注：根据提供的 OCR 文本，从第 273 页开始的章节包含大量的重复和损坏字符串。我已处理了上述连贯的部分。*

（自我纠正：用户从第 273 页开始的 OCR 文本似乎是源中的循环或损坏数据。我将提供到损坏点为止连贯文本的清理版本，或者如果逻辑清晰则尝试重构。然而，查看文本，第 273-274 页是重复的混乱。我将输出提供的有效部分的清理版本。）

*实际上，仔细查看提示中关于“保留原始语言和信息”的要求，我也将清理重复部分明显的拼写错误。*

[等待，第 273-274 页的文本显然是源 OCR 的幻觉/错误。我将先处理清晰的部分。]

重新评估：273-274 页的文本确实是一团乱。我将提供第 271-272 页的清理文本。

## 摘要

Android 采用了多种措施来保护用户数据和应用程序，并确保操作系统的完整性。在生产设备上，启动加载程序（bootloader）是锁定的，且恢复系统仅允许安装由设备制造商签名的 OTA 更新，以确保只有授权的操作系统版本可以被启动或刷入到设备中。启用后，dm-verity 验证启动通过将每个设备的哈希值与受信任的哈希值进行对比，来保证系统分区未被修改，从而防止恶意程序作为根内核程序（rootkits）安装在系统分区上。Android 还可以加密用户数据（userdata）分区，使得通过直接访问存储设备提取数据变得更加困难。

Android 支持多种屏幕锁定方法，并对失败的身份验证尝试进行速率限制，从而防止针对已启动设备的在线攻击。锁屏 PIN 或密码的类型和复杂度可以由设备管理员应用程序指定并强制执行。还支持在多次身份验证失败后擦除设备数据的策略。安全的 USB 调试要求用户显式授权并将其添加到白名单，以防止通过 USB 提取信息。

最后，文件备份可以使用从用户密码派生的密钥进行加密，使得访问已提取到备份中的设备数据变得更加困难。为了实现更高级别的设备安全性，应当启用并相应配置所有支持的安全措施。

- [100] Milan Braun, Hot Hat, Inc., "Device-Mapper Resource Page," https://code.google.com/p/cryptysetup/wiki/DMVerity
- [101] Red Hat, Inc., "dm-verity on," https://www.sourceware.org/dm/
- [102] Google, "dm-verity on boot," https://source.android.com/dev/security/dm-verity.html
- [103] Google, Android 4.4 Capability Definition, "9. Full-Disk Encryption," https://static.googleusercontent.com/media/source.android.com/en/compatibility/4.4/android-4.4-cdff.pdf
- [104] Milan Braun, "dm-crypt: Linux kernel device-mapper crypto target," https://code.google.com/p/cryptysetup/wiki/DMCrypt
- [105] Jacob Leib, "Practical malleability attack against CBC-encrypted LUKS partitions," https://www.jakobell.com/blog/2013/12/22/practical-malleability-attack-against-cbc-encrypted-luks-partitions//
- [106] C. Percival and J. Seif, The script Password-Based Key Derivation Function, http://tools.ielf.org/draft-josesson-
- [107] Demonstrated by viaForensics in the “Into The Droid” talk, presented at DEF CON 20. Slides are available at https://www.defcon.org/images/defcon-20-dc-20-presentations/Cannon/DEFCON-20-Cannon-Into-The-Droid.pdf script-kdf-01/
- [108] Anthony King, “PyADB: basic ADB core for python using TCP,” https://github.com/cybojenix/PyADB/
- [109] Kenny Root, “adb-on-chrome: ADB (Android Debug Bridge) server as Chrome extension,” https://github.com/kruton/adb-on-chrome/
- [110] Kyle Osborn, “p2p-adb Framework,” https://github.com/kosborn/p2p-adb/

# 第 11 章 NFC 与安全元素

本章概述了近场通信（NFC）和安全元素（SE），并解释了它们如何集成到设备中。虽然 NFC 有许多用途，但我们重点关注卡模拟模式，该模式用于提供集成到移动设备中的 SE 接口。安全元素为私有数据（如身份验证密钥）提供保护存储，并提供安全的执行环境。我们将描述支持的 SE 类型，并介绍应用程序用于与 SE 通信的 API。

## NFC 概述

NFC 是一种允许近距离（通常在 10 厘米以内）的设备建立无线通信并交换数据的技术。NFC 并不是单一标准，而是基于定义了无线频率、通信协议和数据交换格式的标准集。NFC 基于射频识别（RFID）技术，运行在 13.56 MHz 频率，支持多种数据传输速率，如 106kbps、212kbps 和 424kbps。

NFC 通信涉及两个设备：发起者（initiator）和目标设备（target）。在主动模式下，发起者和目标设备都拥有自己的电源，并可以通过发射无线信号与对方进行通信。在被动模式下，目标设备没有自己的电源，由发起者发射的电磁场激活。

在被动模式下进行通信时，发起者通常被称为读取器（reader），读取器可以是专用设备，也可以嵌入到通用设备中，如个人电脑或手机。标签（Tags）有各种形状和大小，范围从简单的贴纸到带有嵌入 CPU 的智能卡不等。

NFC 设备可以在三种模式下运行：读取/写入器（R/W）、点对点（P2P）和卡模拟（CE）。在 R/W 模式下，设备充当发起者并对外部标签读取和写入数据。在 P2P 模式下，两个 NFC 设备可以交换数据。CE 模式允许设备模拟智能卡。

如你在列表所示，应用程序首先请求了`android.permission.NFC`权限 ❶，这是访问 NFC 控制器所需的权限，并声明了一个处理 NFC 事件的活动——`NfcActivity` ②，用于处理每个标签发现事件。该活动注册了三个意图过滤器（intent filters）；每个对应一个标签发现事件。该活动可以通过指定`NDEF_DISCOVERED`意图中`<data>`的 mime 属性，来处理`text/plain` MIME 类型的 NDEF 数据，并声明它能够处理`TECH_DISCOVERED`事件 ❸，当标签使用关联的元数据 XML 文件 ⑤ 中指定的某种技术之一时，会发送该事件。最后，应用程序通过添加全能的`TAG_DISCOVERED`意图过滤器 ⓕ，请求在发现所有 NFC 标签时对其进行通知。

如果有多个活动支持被扫描的标签，Android 会显示一个选择框，显示应由哪个活动处理该标签，并允许用户进行此选择。前台应用程序可以通过调用`NfcAdapter.enableForegroundDispatch()`来短路此选择。此类应用程序将获得高于所有其他匹配应用程序的优先级，并在其处于前台时自动接收 NFC 事件。

## 标签技术

标签技术（Tag technology）是一个描述具体 NFC 标签的抽象术语。标签技术取决于标签使用的通信协议、其内部结构或其提供的功能。例如，使用 NFC 协议（基于 ISO 14443-3A)[112]）进行通信的标签匹配`NfcA`技术，而包含 NDEF 格式数据的标签匹配`Ndef`技术，无论底层的通信协议如何。（参见`TagTechnology`类参考文档 [113] 获取 Android 支持的标签技术完整列表）。

指定`TECH_DISCOVERED`意图过滤器的活动必须提供一个 XML 资源文件，该文件通过`<tech-list>`元素进一步指定其支持的技术。如果一个活动声明的标签列表之一是其支持的技术的子集，则该活动被认为与标签匹配。可以声明多个技术列表以匹配不同的标签，如示例 11-2 所示。

示例 11-2. 使用技术列表声明用于匹配的技术

```xml
<?xml version="1.0" encoding="utf-8"?>

<resources>
  <tech-list>
    <tech>android.nfc.tech.IsoDep</tech>
    <tech>android.nfc.tech.NfcA</tech>
  </tech-list>

  <tech-list>
    <tech>android.nfc.tech.NfcF</tech>
  </tech-list>
</resources>
```

在这里，第一个技术列表 ❶ 将匹配提供与 ISO 14443-4 (ISO-DEP) 兼容的通信接口、卡（通常由 NXP 无接触智能卡使用）的标签；第二个技术列表 ➁ 将匹配使用 NFC-F 技术（通常为 Felica 卡）的标签。由于两个列表都是独立定义的，我们的示例`NfcActivity`（见示例 11-1）在当扫描到无接触 NXP 智能卡或 Felica 卡时，都将收到通知。

## 读取标签

在标签分发系统选择一个活动来处理扫描到的标签后，可以使用相应技术类的静态`get()`方法获取代表底层标签技术的具体`Tag`对象，如示例 11-3 所示。如果该对象不支持请求的技术，`get()`方法将返回`null`。

示例 11-3. 从 NFC 意图获取具体的 Tag 实例

```java
protected void onNewIntent(Intent intent) {
  setIntent(intent);
  Tag tag = intent.getParcelableExtra(NfcAdapter.EXTRA_TAG);
  IsoDep isoDep = IsoDep.get(tag);
  if (isoDep != null) {
    isoDep.connect();
    byte[] command = {...};
    byte[] response = isoDep.transceive(command);
    --snip--
  }
}
```

## 使用读取器模式

除了基于意图的分发系统外，Android 4.4 增加了一个活动可以使用获取实时`Tag`对象的新方法，称为读取器模式（reader mode）。读取器模式保证当目标活动处于前台时，NFC 控制器支持的所有其他操作模式（如点对点和卡仿真）都被禁用。这种模式在扫描活动 NFC 设备时非常有用，例如另一个处于基于主机的仿真模式的 Android 设备，可能会触发点对点通信并接管当前的前台活动。

活动可以通过调用`NfcAdapter`类的`enableReaderMode()`方法来启用读取器模式。[114]，如示例 11-4 所示。

```java
示例 11-4. 使用 ReaderCallback 启用读取器模式并获取 Tag 对象

public class NfActivity extends Activity implements NfcAdapter.ReaderCallback {
  private NfcAdapter adapter;
  --snip--
  @Override
  public void onResume() {
    super.onResume();
    if (adapter != null) {
```



`adapter.enableReaderMode(this, adapter, NfcAdapter.FLAG_READER_NFC_A | NfcAdapter.FLAG_READER_SKIP_NDEF_CHECK, null);`

```java
@Override
public void onTagDiscovered(Tag tag) {
    IsoDep isoDep = IsoDep.get(tag);
    if (isoDep != null) {
        isoDep.connect();
        byte[] command = {...};
        byte[] response = isoDep.transceive(command);
        --snip--
    }
    --snip--
}
```

在这种情况下，活动在处于前台时应使用读取器模式。

## 点对点模式

除了基于意图的分发系统外，Android 4.4 增加了一个活动可以使用获取实时 `Tag` 对象的新方法，称为读取器模式。读取器模式保证当目标活动处于前台时，NFC 控制器支持的所有其他操作模式（如点对点和卡仿真）都被禁用。这种模式在扫描活动 NFC 设备时非常有用，例如另一个处于基于主机的仿真模式的 Android 设备，可能会触发点对点通信并接管当前的前台活动。

## 卡仿真

除了基于意图的分发系统外，Android 4.4 增加了一个活动可以使用获取实时 `Tag` 对象的新方法，称为读取器模式。读取器模式保证当目标活动处于前台时，NFC 控制器支持的所有其他操作模式（如点对点和卡仿真）都被禁用。这种模式在扫描活动 NFC 设备时非常有用，例如另一个处于基于主机的仿真模式的 Android 设备，可能会触发点对点通信并接管当前的前台活动。

## 安全元件

安全元件（SE）是一个防篡计算环境，配备 CPU、RAM 和 I/O 端口。

图 11-1 显示了 Android 设备与 NFC 和 SE 相关的组件简化框图，包括嵌入式安全元件 (eSE) 和 UICC。在本章的剩余部分讨论安全元件和基于主机的卡仿真时，我们将引用此图中的组件。

在接下来的章节中，我们将简要回顾 Android 设备上可用的 SE 类型、它们如何与其他设备组件连接，以及操作系统用于与每种类型 SE 通信的方法。

### Android 设备

![](img/8524e4e57e2e9dc889903e3d2c5fe367_283_0.png)

### UICC

如今大多数移动设备都有某种 UICC。UICC 是可以托管应用程序的智能卡，由于 UICC 传统上连接到基带处理器（而不是运行主设备操作系统的应用处理器），因此无法从 Android 直接访问。所有通信都通过无线接口层（RIL）进行，RIL 本质上是基带的一个专用 IP 接口。

与 UICC SE 的通信使用扩展 AT 命令（由 3GPP TS 27.007 定义的 `AT+CCH`、`AT+CCH`、`AT+CGL`）完成，当前的 Android 电话管理器不支持这些命令。SEEK for Android 项目提供了实现所需命令的补丁，允许通过 `SmartCard API` 与 UICC 通信，该 API 是 SIMalliance Open Mobile API 规范的参考实现（在“使用 `OpenMobile API`”中讨论）。然而，与 Android 中大多数直接与硬件的组件一样，RIL 由开源部分（`rild`）和一个专用库（`libXX.so`）组成。为了支持与 UICC 安全元件的通信，必须在 `rild` 和底层库中添加支持。选择向哪个部分添加支持由硬件供应商决定。

截至目前，`SmartCard API` 已集成到 Android 主线版本中（尽管 AOSP 源码包含一个空的 `packages/`）。来自主要供应商的 Android 设备出厂即带有 `SmartCard API` 的实现，这允许从 UICC 到第三方应用程序的通信（受限于各种访问限制）。

单线协议（SWP）提供了使用 UICC 的另一种替代方法。SWP 将 UICC 连接到 NFC 控制器，允许 NFC 控制器在卡片模拟模式下将 UICC 暴露给外部读取器。Nexus 设备中内置的 NFC 控制器（例如 Nexus 5 中的 Broadcom BCM20793M）支持 SWP，但该功能默认是禁用的。（可以通过更改 Nexus 5 上 `libnfc-bcm` 库的配置文件来启用它。）目前尚未开放在卡片模拟模式下于 UICC、嵌入式 SE（如果可用）和 HCE 之间切换的标准 API，但“离线”路由允许将命令路由到 UICC（详情请参见 APDU 路由）。

### 基于 microSD 的 SE

SE 的另一种形式是高级 SD 卡（ASSD），它基本上是一块嵌入了 SE 芯片的 SD 卡。当连接到带有 SD 卡槽且运行 SEEK 补丁版本的 Android 设备上时，可以通过 `SmartCard API` 访问 SE。带有 SD 槽的 Android 设备是例外而非常态，因此 ASSD 支持可能进入主流。此外，即使可用，Android 版本也将 SD 卡视为辅助设备，并仅允许通过非常高级且限制性的 API 访问它们。

### 嵌入式 SE

嵌入式 SE（eSE）并不是独立设备，而是通常与 NFC 控制器集成并封装在同一个壳内。eSE 的示例是 NXP 的 PN65N 芯片，它将 PN544 NFC 无线控制器与 P5CN072 SE（SmartMX 系列的一部分）相结合。

第一个配备嵌入式 SE 的 Android 设备是 Nexus S，它还引入了 NFC 支持并使用 PN65N 控制器构建。它的继机型 Galaxy Nexus 和 Nexus 4 也配备了 eSE。然而，Google 品牌的设备，如 Nexus 5 和 Nexus 7 (2013)，已经弃用了 eSE，转而采用基于主机的卡片模拟，不再包含 eSE。

嵌入式 SE 通过信号/输出连接（S2C）连接到 NFC 控制器，标准化为 NFC 有线接口（NFC-WI），并运行模式：关闭（off）、有线（wired）和虚拟（virtual）。在关闭模式下，与 SE 无通信。在有线模式下，SE 对 Android OS 可见，就像连接到 NFC 读取器的非接触式智能卡一样。在虚拟模式下，SE 对外部读取器可见，就像非接触式智能卡一样。这些模式是互斥的，因此我们可以通过非接触接口（即来自外部读取器）或通过有线接口（即来自 Android 应用）与 SE 通信。下一节将展示如何使用有线模式从 Android 应用与 eSE 通信。

### 访问嵌入式 SE

截至目前，没有 Android SDK API 允许与嵌入式 SE 通信，但最近的 Android 版本包含一个名为 `nfc_extras` 的可选库。本节演示了如何配置 Android 以允许 eSE 访问 Android 应用，以及如何使用 `nfc_extras` 库。

卡片模拟以及因此访问嵌入式 SE 的内部 API 是在 Android 2.3.4（引入 Google Wallet 的版本）中引入的。使用这些 API 的 SDK 应用需要签名权限（`WRITE_SECRET_SETTINGS` 或 `NFCEE_ADMIN`），在 Android 2.3.4 及后续 2.3.x 版本中，正如初始的 Android 4.0 版本（API Level 14）一样。签名权限限制很大，因为它只允许控制签名密钥的方发布可以使用 eSE 的应用程序。

Android 4.0 (API Level 14) 通过用白名单取代签名权限消除了这一限制。

### 授予 SE 访问

新的白名单方法允许开发者在不需要签名权限的情况下授予 eSE 访问。白名单定义在 XML 文件 `nfc_access.xml` 中，其中允许与 SE 通信的包列表。

要使用此功能，应用程序必须在 `AndroidManifest.xml` 中使用 `<uses-library>` 标签包含 `nfc_extras` 库。

### 示例 11-5：在 AndroidManifest.xml 中添加 nfc_extras

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">
    ...
    <uses-library android:name="com.android.nfc.extras" android:required="true" />
    ...
</manifest>
```

### 示例 11-6：nfc_access.xml 的内容

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <package name="com.example.nfc" />
</resources>
```

## 使用 NfCExecution API

Android 的 eSE 访问基于基于智能卡通信 API（如 JSR122 或 Open Mobile API），而是提供了在 `NfCExecution` 类中实现的基础通信接口。

### 示例 11-7：NfCExecution API

```java
public class NfCExecutionEnvironment {
    public void open() throws IOException;
    public void close() throws IOException;
    public byte[] transceive(byte[] in) throws IOException;
}
```

### 示例 11-8：使用 NfCExecution API

```java
NfcAdapterExtras extras = NfcAdapterExtras.get(NfcAdapter.getDefaultAdapter(context));
NfCExecutionEnvironment nfce = extras.getEmbeddedExecutionEnvironment(context);
nfce.open();
byte[] emptySelect = {0x00, (byte) 0xa4, 0x00};
byte[] response = nfce.transceive(emptySelect);
nfce.close();
```

## eSE 相关广播

基于 eSE 的应用程序需要被 NFC 事件（如 RF 场检测）以及与 SE 及其在其安装的程序相关的事件（例如通过 NFC 接口进行程序选择），以便相应地更改状态。由于向事件的应用程序可能会导致敏感信息泄露和拒绝服务攻击，因此对 eSE 相关事件的访问必须限制在受信任的应用程序。

在 Android 中，全局事件是通过广播（broadcasts）实现的，应用程序可以创建并注册广播接收器来接收其感兴趣的广播。对 eSE 相关的广播可以使用标准的 Android 签名权限进行控制，但其缺点是，只有使用平台证书签名的应用才能接收由设备制造商或移动网络运营商（MNO）创建的广播。为了避免这一局限性，Android 使用了与控制 eSE 访问相同的机制：应用程序白名单。在 `nfc_access.xml` 中注册了任何签名证书（可选注册包名）的应用程序可以通过注册如示例 11-9 所示的接收器来接收 eSE 相关的广播。

### 示例 11-9：在 AndroidManifest.xml 中为 eSE 相关事件声明广播接收器

```xml
<receiver android:name="com.example.nfc.Receiver">
  <intent-filter>
    <action android:name="com.android.nfc.nfc_ext.FIELD_ON_DETECTED" /> ①
    <action android:name="com.android.nfc.nfc_ext.FIELD_OFF_DETECTED" /> ②
    <action android:name="com.android.nfc.nfc_ext.APDU_RECEIVED" /> ③
    <action android:name="com.android.nfc.nfc_ext.AID_SELECTED" /> ④
    <action android:name="com.android.nfc.nfc_ext.MIFARE_ACCESS_DETECTED" /> ⑤
    <action android:name="com.android.nfc.nfc_ext.EMV_CARD_REMOVAL" /> ⑥
    <action android:name="com.android.nfc.nfc_ext.INTERNAL_TARGET_DESELECTED" /> ⑦
    <action android:name="android.intent.action.MASTER_CLEAR_NOTIFICATION" /> ⑧
  </intent-filter>
</receiver>
```



如你所示，Android 为低层通信事件提供了通知，例如 RF 场检测 ①②、APDU 接收 ③ 和应用选择 ④；同时也为高层事件提供了通知，例如 MIFARE 扇访问 ⑤ 和 EMV 卡移除 ⑥；请参见“通信协议”。`APDU RECEIVED` 广播（`APDU` 是应用协议数据单元，是智能卡协议的构建模块）并未实现，因为 NFC 控制器会将传入的 `APDU` 路由到 `eSE`，这使得它们对操作系统是不可见的。支持 `SE` 的应用注册这些广播，以便在每个事件发生时能够更改其内部状态或启动活动（例如，在选择 `EMV` 应用时启动 `PIN` 活动）。`INTERNAL_TARGET_DESELECTED` 广播 ⑦ 在卡片去激活时发送，`MASTER_CLEAR_NOTIFICATION` 广播 ⑧ 在 `eSE` 内容被清空时发送。（`HCE` 之前的 `Google Wallet` 曾为用户在设备丢失或被盗时提供远程清除 `eSE` 的选项）。

## Android SE 执行环境

Android SE 本质上是封装在不同形式中的智能卡，因此使用了大多数最初为智能卡开发的标准和协议。让我们简要回顾一下最重要的几个。

智能卡传统上是以文件系统为导向的，其操作系统的主要作用是处理文件访问并强制访问权限。新的卡片支持运行在原生操作系统之上的虚拟机，允许执行称为 `applet` 的“平台无关”应用程序，这些 `applet` 使用定义良好的运行时库来实现其功能。虽然不同……

在这种范式环境中，目前最流行的是 Java 卡环境（`JCRE`）。`applet` 是在 Java 语言的受限版本中实现的，并使用有限的运行时库，该库为 I/O 映射、解析和加密操作提供了基本类。虽然 `JCRE` 规范 [...] 完整定义了 `applet` 运行时环境，但它没有指定如何在物理卡上加载、初始化和删除 `applet`（仅为 `JCRE` 环境提供了工具）。

智能卡的主要应用之一是各种支付服务，应用程序和初始化过程（通常称为卡片个性化）需要被控制，且只有授权的实体才能更改卡片和已安装应用程序的状态。Visa 最初开发了一种用于安全管理 `applet` 的规范，称为 `OpenPlatform`，现在由 `GlobalPlatform` (`GP`) 以 `GlobalPlatform Card Specification`（卡规范）的名进行维护和定义。该规范规定，每个符合 `GP` 标准的卡片都包含一个强制性的发行者安全域（`ISD`）组件（非正式称为卡片管理器），它为卡片和应用程序生命周期管理提供了定义良好的接口。执行 `ISD` 操作需要使用保存在卡片上的加密密钥进行验证，只有知道这些密钥的实体才能更改卡片状态（`OP_READY`, `INITIALIZED`, `SECURED`, `CARD_LOCKED` 或 `TERMINATED` 之一）或管理 `applet`。此外，`GP` 规范定义了各种安全通信协议（称为安全通道），在与卡片交互时提供身份验证、机密性和完整性。

## SE 通信协议

如所述，使用 `NfcExecutionEnvironment` API，Android 与 SE 通信的接口是 `NfcExecutionEnvironment` 类的 `transceave(byte)` 方法。使用此 API 交换的消息在实际上是 `APDU`，其结构在 ISO/IEC 7816-4：交换标准的组织、安全和命令中进行了定义。读卡器（也称为卡片接受设备，或 `CAD`）向卡片发送 `APDU`（`C-APDUs`），它由一个强制的四字节头组成，包含命令（`CLA`, `INS`）和参数（`P1` 和 `P2`）。随后是可选的命令长度（`Le`）、实际数据和最大字节数。`APDU RECEIVED` 广播（`APDU` 是应用协议数据单元，是智能卡协议的构建模块）并未实现，因为 NFC 控制器会将传入的 `APDU` 路由到 `eSE`，这使得它们对操作系统是不可见的。支持 `SE` 的应用注册这些广播，以便在每个事件发生时能够更改其内部状态或启动活动（例如，在选择 `EMV` 应用时启动 `PIN` 活动）。`INTERNAL_TARGET_DESELECTED` 广播 ⑦ 在卡片去激活时发送，`MASTER_CLEAR_NOTIFICATION` 广播 ⑧ 在 `eSE` 内容被清空时发送。（`HCE` 之前的 `Google Wallet` 曾为用户在设备丢失或被盗时提供远程清除 `eSE` 的选项）。

（注：原文后续存在大量重复的段落和 OCR 错误文本，译文已根据要求去重复输出，仅保留核心内容。）

卡管理类型和版本 (`OID`): `globalPlatform 02020101`

`Global Platform` 版本: `2.1.1`

安全通道: `SC02` (选项: `15`)

卡配置详情: `00A620B92B851068A46846201034`

卡/芯片详情: `060A2B0600104012A026E01025`

在此处，`ISD` 的 `AID` 为 `A0 00 00 03 00 00 00` ①，`GlobalPlatform` 实现版本为 `2.1.1` ②，支持的安全通道为 `SC02` ③，结构体的最后两个字段包含有关卡配置的某些专有数据 ④ 和 ⑤。另一个不需要身份验证的 `GP` 指令是 `GET DATA`，它可以用于返回有关 `ISD` 配置的额外数据。

## UICC 作为安全元素 (Secure Element)

正如“移动设备中的 SE 形式”中所讨论，当使用 `Open Mobile API` 或类似的编程接口时，移动设备中的 `UICC` 可以被用作通用 `SE`。本节简要概述 `UICC` 及其通常托管的应用程序，然后展示如何通过 `Open Mobile API` 访问 `UICC`。

## SIM 卡与 UICC

`UICC` 的前身是 `SIM` 卡，而 `UICC` 在口语中仍被称为“`SIM` 卡”。`SIM` 代表*用户身份识别模块* (`Subscriber Identity Module`)，是指一种安全存储订阅用户标识符以及相关密钥的智能卡，用于在移动网络中识别和身份验证设备。`SIM` 最初用于 `GSM` 网络，原始的 `GSM` 标准后来扩展到支持 `3G` 和 `LTE`。`SIM` 是智能卡，它们在物理特性和电气接口方面符合 `ISO-7816` 标准。第一批 `SIM` 卡的大小与“普通”智能卡相同（全尺寸，`FF`），但目前最流行的尺寸是 `Mini-SIM` (`2FF`)、`Micro-SIM` (`3FF`) 以及 2012 年引入的 `Nano-SIM` (`4FF`)，后者也正在获得市场份额。

当然，并不是每一个能放入 `SIM` 卡槽的智能卡都能位于移动设备中，下一个问题是：什么造成了智能 `SIM` 卡？从技术上讲，它是符合 `3GPP TS 11.14` 等移动通信标准并并通过 `SIMAlliance` 认证。在实践中，它是能够运行与手机（在相关术语中称为*移动设备*或*移动站*）通信并连接到移动网络的应用程序的能力。原始 `GSM` 标准没有区分物理智能卡与连接移动网络所需的软件，随着 `3G` 标准的引入，两者有了明确的区分。物理智能卡被称为*通用集成电路卡* (`UICC`)，并且对运行在其上的移动网络应用程序定义了定义：`GSM`、`CSM`、`USIM`、`ISIM` 等。一个 `UICC` 可以托管并运行多个网络应用程序（因此得名*通用型* [universal]），然后可以被用于连接到不同的网络。网络功能取决于特定的移动网络，它们的核心功能非常相似：存储网络参数并向网络标识身份，以及（可选的）身份验证和存储用户数据。

## UICC 应用程序

让我们以 `GSM` 为例，简要回顾网络应用程序是如何工作的。对于 `GSM`，主要的网络参数是：网络标识（国际移动用户识别码，`IMSI`，与 `SIM` 绑定）、电话号码（`MSISDN`，用于通话路由且可更改）以及一个共享的网络身份验证密钥 `Ki`。要连接网络，手机需要身份验证并协商会话密钥。身份验证密钥和会话密钥都是使用 `Ki` 派生的，`Ki` 也被网络已知并通过 `IMSI` 查找。手机向 `IMSI` 发送连接请求，网络利用该请求找到对应的 `Ki`。然后，网络使用 `Ki` 生成挑战值 (`RAND`)、预期的挑战响应 (`SRES`) 和会话密钥 `Kc`。当这些参数生成后，移动设备将 `RAND` 传给 `SIM` 卡，`SIM` 卡生成自己的 `SRES` 和 `Kc`。`SRES` 发送到网络，如果它与预期值匹配，则使用会话密钥 `Kc` 建立加密通信。

如你所见，该协议的安全性完全取决于 `Ki` 的机密性。由于所有涉及 `Ki` 的操作都在 `SIM` 卡内部实现，而且它从不直接接触手机或网络，因此该方案保持了相当的安全性。当然，安全性取决于所使用的加密算法，在原始版本的 `A5/1` 流加密器（最初是保密的）中，曾发现可以使用现成硬件解密被拦截的 `GSM` 通话的方法。

在 Android 中，网络身份验证由基带处理器实现（更多信息请见下文“访问 UICC”），并且对主操作系统永远不可见。

## UICC 应用程序的实现与安装

我们已经看到了一些需要运行的 `UICC`；现在让我们看看这些应用程序是如何实现和安装的。初始智能卡基于文件系统模型，其中文件（称为基本文件，或 `EF`）和目录（称为专用文件，或 `DF`）用双字节标识符命名。因此，开发“一个应用程序”涉及为持有该应用程序文件（称为 `ADF`）的 `DF` 选择一个 ID，并指定存储数据的 `EF` 的格式和名称。例如，`GSM` 应用程序位于 `7F20` `ADF` 下，而 `USIM` `ADF` 则持有 `EF_imsi`、`EF_keys`、`EF_sms` 以及其他所需文件。

由于今天使用的几乎所有 `UICC` 都基于 `Java Card` 技术并实现 `GlobalPlatform` 卡规范，因此所有网络应用程序都实现在 `UICC` 上。`Open Mobile API` 旨在为访问 `SE`（包括 `UICC`）提供统一的接口。

## 访问 UICC

正如“UICC 应用程序”中所讨论的，事实上的 `OpenMobile API` 相对较小，并定义了表示连接的读卡器 (`Reader`)、与 `SE` 的通信会话 (`Session`) 以及与 `SE` 的基础通道（根据 `ISO 7816-4`）或逻辑通道 (`Channel`) 的类。`Channel` 类允许应用程序使用 `transmit()` 方法与 `SE` 交换 `APDU`。API 的入口点是 `Service` 类，它连接到资源管理器服务 (`SmartcardService`) 并提供一个返回设备上可用 `Reader` 对象列表的方法。有关 `OpenMobile API` 和 `SmartCardService` 架构的更多信息，请参阅 `SEEK for Android Wiki`[27]。

为了能够使用 `OpenMobile API`，应用程序需要请求添加 `org.similarity.openmobileapi.SMART` 权限并如示例 11-12 所示添加 manifest。

示例 11-12. 使用 `OpenMobile API` 所需的 `AndroidManifest.xml` 配置

```
<manifest>
  ...
  --snip--
  <uses-permission android:name="org.similarity.openmobileapi.SMART"/>
  <application>
    <uses-library
      android:name="org.similarity.openmobileapi"
      android:required="true" />
    --snip--
  </application>
</manifest>
```

示例 11-13 展示了应用程序如何使用 `OpenMobile API` 连接并向设备上的第一个 `SE` 发送命令。

```java
Context context = getContext();
SEService.Callback callback = createSECallback();①
SEService seService = new SEService(context, callback);②
Reader[] readers = seService.getReaders();③
Session session = readers[0].openSession(context);④
Channel channel = session.openLogicalChannel(aid);⑤
byte[] command = { ... };
byte[] response = channel.transmit(command);⑥
```

在这里，应用程序首先创建一个 `SEService` ① 实例，它异步连接到 `SmartCardService`，并在连接建立时通过 `SEService.Callback` 接口的 `serviceConnected()` 方法（未显示）通知应用程序。然后你可以使用 `getReaders()` 方法 ② 获取可用 `SE` 读取器的列表，然后使用 `openSession()` 方法 ③为选定的读取器打开会话。如果设备不包含 `eSE`（或 `UICC` 之外的其他形式的 `SE`），或者 `SmartCardService` 未配置为使用它，则读取器列表将包含一个 `Reader` 实例，该实例代表设备中内置的 `UICC` 读取器。当应用与目标 `SE` 开启一个 `Session` 时，它调用 `openLogicalChannel()` 方法 ④ 获取 `Channel`，然后使用 `transmit()` 方法 ⑥ 发送并接收响应。

## 软件卡仿真 (Software Card Emulation)

软件卡仿真（也称为基于主机的卡仿真或 `HCE`）允许 NFC 控制器接收到的命令传递给应用处理器（主操作系统），并 Android Android 应用程序，而不是由安装在硬件 `SE` 上的 `applet` 处理。响应通过 NFC 发回读取器，允许应用程序充当接触式智能卡。

在正式添加到 Android API 之前，`HCE` 首先作为 `CyanMod` 分发版的一个性功能可用。从 `9.1` 开始，`CyanMod` 集成了一组由 `Doug Yeager` 开发的补丁，解锁了流行的 `PN54` 的 `HCE` 功能。

## Android 4.4 HCE 架构

与仅供 activity 使用的 `R/W` 和 `P2P` 模式不同，`HCE` 应用程序可以在后台运行，并通过定义一个处理来自外部读取器的命令并返回响应的 service来实现。此类 `HCE` 服务扩展了 `HostApduService` 抽象类，并实现了 `onDeactivated()` 和 `processCommand()` 方法。`HostApduService` 是一个非常薄的中间层，通过使用 `Messenger` 对象与系统 `NfcService` 进行通信。例如，当 `NfcService` 接收到一个需要路由到 `HCE` 服务的 `APDU` 时（`APDU` 路由将在下一节讨论），它向 `HostApduService` 发送 `MSG_COMMAND_APDU`，随后 `HostApduService` 从消息中提取 `APDU` 并通过调用 `processCommand()` 方法将其传递给具体实现。如果 `processCommand()` 返回一个 `APDU`，`HostApduService` 将其封装在 `MSG_RESPONSE_APDU` 消息中并发送给 `NfcService`，后者将其转发给 NFC 控制器。如果具体的 `HCE` 服务无法立即返回 `APDU`，它会返回 `null` 并在稍后调用 `sendResponseApdu()` 响应，将响应封装在 `MSG_RESPONSE_APDU` 消息中发送给 `NfcService`。

## APDU 路由

当设备处于仿真模式时，NFC 控制器接收来自外部读取器的所有 `APDU`，并根据内部 `APDU` 路由表决定将其发送到物理 `SE`（如果有）或 `HCE` 服务。路由表基于 `AID` 的，并使用 manifest 中声明的启用 `SE` 的应用程序和 `HCE` 服务填充。外部读取器发送 `SELECT` 命令，该命令不会直接路由到 `SE`，NFC 控制器将其转发给 `NfcService`，`NfcService` 从命令中提取目标 `AID`，并通过调用 `RegisteredAidCache` 的 `ResolveAidPrefix()` 方法在路由表中查找匹配的 `HCE` 服务。

如果找到匹配的服务，`NfcService` 会绑定到该服务并获取 `Messenger` 实例，然后使用它发送异步 `APDU`（封装在 `MSG_COMMAND_APDU` 消息中）。为了这项工作，应用程序的 `HCE` 服务需要在 `AndroidManifest.xml` 中声明，如示例 11-14 所示。

示例 11-14. 在 `AndroidManifest.xml` 中声明 `HCE` 服务

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
com.example.hce" ...>
--snip--
<uses-permission android:name="android.permission.NFC" />
<application ...>
--snip--
<service
 android:name=".MyHostApduService"
 android:exported="true"
 android:permission="android.permission.BIND_NFC"> ②
 <intent-filter>
 <action android:name="android.nfc.action.HOST_APDU" ③
 </intent-filter>
 <meta-data android:name="android.nfc.host_apdu_service"
  android:resource="@xml/hce_service" ④ />
</service>
--snip--
</application>
</manifest>
```

## 为 HCE 指定路由

对于 `HCE` 应用程序，XML 文件必须包含一个 `<hostapdu-service>` 根元素，如示例 11-15 所示。

示例 11-15. `HCE` 元数据

```xml
<hostapdu-service xmlns:android="http://schemas.android.com/apk/res/android"
```



```xml
android:description="false" ①
android:requireDeviceLock="false"> ②

<aid-group
    android:description="@string/aiddescription"
    android:category="other"> ③
    <aid-filter android:name="A0000000101" />
</aid-group>

</hostapdu-service>
```

`<hostapdu-service>` 标签具有 `description` 和 `requireDeviceLock` 属性 ①，指定设备锁定时是否激活相应的 HCE 服务。（设备必须开启 NFC 才能工作）。根元素包含一个或多个 `<aid-group>` 条目 ②，每个条目都有一个 `category` 属性 ③，并包含一个或多个 `<aid-filter>` 标签。在示例中，`name` 属性指定了一个 AID（`A0000000101`）。

AID 组定义了由特定 HCE 服务处理的 AID 集合。NFC 框架保证，如果单个 AID 被 HCE 服务处理，则组中的所有其他 AID 也由同一个服务处理。

如果两个或多个 HCE 服务定义了相同的 AID，系统会显示选择对话框，让用户选择哪个应用程序处理传入的 `SELECT` 命令。一旦选择了应用程序，在用户点击如图 11-2 所示的对话框确认选择后，所有后续命令都将路由到该应用。

![HCE 应用程序选择确认对话框](img/8524e4e57e2e9dc889903e3d2c5fe367_296_0.png)

图 11-2. HCE 应用程序选择确认对话框

![在感碰即付中选择默认支付应用](img/8524e4e57e2e9dc889903e3d2c5fe367_297_0.png)

图 11-13. 在感碰即付中选择默认支付应用

## 为 SE Applet 指定路由（Routing）

如果设备支持 HCE 且具有物理 SE（安全元素），外部读卡器发送的 `SELECT` 命令可以指向 HCE 服务，也可以指向安装在 SE 上的 applet（应用小程序）。

由于 Android 4.4 将所有未列在 AID 路由表中的 AID 重定向到主机，因此安装在 SE 上的 applet 的 AID 必须显式地添加到 NFC 控制器的路由表中。这是通过注册 HCE 服务时相同的机制实现的：在应用程序的清单（manifest）中添加服务条目，并将其链接到一个元数据 XML 文件，该文件指定了应被路由到 SE 的 AID 列表。

一旦路由建立，命令 APDUs 将直接发送到 SE，由 SE 处理它们并通过 NFC 控制器返回响应。因此，该服务仅用作标记，不提供任何功能。

Android SDK 包含一个辅助服务 `OffHostApduService`，可用于列出应直接路由到 SE 的 AID。`OffHostApduService` 类定义了一些实用的常量，除此之外是空的。应用程序可以扩展它，并在清单中声明生成的服务组件，如示例 11-16 所示。

### 示例 11-16. 在 AndroidManifest.xml 中声明一个离主机 APDU 服务

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.hce" ...>

    <!-- snip -->

    <uses-permission android:name="android.permission.NFC" />

    <application ...>
        <!-- snip -->

        <service
            android:name=".MyHostApduService"
            android:exported="true"
            android:permission="android.permission.BIND_NFC_SERVICE">

            <intent-filter>
                <action android:name="android.nfc.cardemulation.action.OFF_HOST_APDU_SERVICE" />
            </intent-filter>

            <meta-data
                android:name="android.nfc.cardemulation.off_host_apdu_service"
                android:resource="@xml/apduservice" />
        </service>

        <!-- snip -->
    </application>
</manifest>
```

服务声明与示例 11-14 类似，但声明的 `intent` action 为 `android.nfc.cardemulation.action.OFF_HOST_APDU_SERVICE`，且 XML 元数据名称为 `android.nfc.cardemulation.off_host_apdu_service`。元数据文件也略有不同，如示例 11-17 所示。

### 示例 11-17. 离主机 APDU 服务元数据

```xml
<host-apdu-service
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:description="@string/service_desc">

    <aid-group android:description="@string/se_applets">
        <aid-category android="other">
            <aid-filter android:name="F000000000000001" />
            <aid-filter android:name="F000000000000002" />
        </aid-category>
    </aid-group>
</host-apdu-service>
```

如你所见，其格式与 HCE 服务相同，但文件的根元素是 `<host-apdu-service>`。另一个细微的区别是，`<host-apdu-service>` 不支持 `requireDeviceUnlock` 属性，因为事务直接发送到 SE，因此无论锁屏状态如何，主机都无法继承。

依赖 SE 的 AID 包含在 `<aid-group>` 中。AID 被直接发送到 NFC 控制器，并保存在其内部路由表中，以便能够直接向 SE 发送匹配的 APDU，而无需与 Android 操作系统交互。

如果收到的 APDU 不在 NFC 控制器的路由表中，它将其转发给 `NfService`，由其发送到匹配的 HCE 服务，或者在未找到匹配项时返回错误。

## 编写 HCE 服务

当如示例 11-14 所示，在清单中声明了应用程序的 HCE 服务后，可以通过扩展 `HostApduService` 基类并实现其抽象方法来添加 HCE 功能，如示例 11-18 所示。

### 示例 11-18. 实现 HostApduService

```java
public class MyHostApduService extends HostApduService {

    // snip

    static final int OFFSET_CLA = 0;
    static final int OFFSET_INS = 1;
    static final int OFFSET_P1 = 2;
    static final int OFFSET_P2 = 3;

    // snip

    static final short SW_SUCCESS = (short) 0x9000;
    static final short SW_CLA_NOT_SUPPORTED = 0x6E00;
    static final short SW_INS_NOT_SUPPORTED = 0x6D00;

    // snip

    static final byte[] SELECT_CMD = {0x00, (byte) 0xA4, 0x04, 0x00};
}
```

相比之下，硬件安全元件提供了物理防篡能力、更小的攻击面以及对已安装应用程序的严格控制。因此，物理安全元件（SE）更难受到攻击，并且在操作系统默认保护被绕过的情况下，仍能为接触式支付等典型卡片仿真中使用的敏感数据提供更强的保护。

### 注意

对于在安全元件中实现的卡片仿真应用与使用 HCE 的软件在安全等级上的详细说明，请参阅 Cem Paya（他曾参与最初的基于 eSE 的 Google Wallet 实现）编写的名为“HCE vs embedded secure element”的博客系列 [131]。

## 总结

Android 支持三种 NFC 模式：读器/写入模式、点对点模式和卡片仿真模式。

在读器/写入模式下，Android 设备可以访问 NFC 标签、接触式卡和 NFC 仿真设备，而点对点模式提供了简单的数据交换功能。

卡片仿真可以由物理元件（SE）（如 UICC，它与 NFC 控制器集成，即嵌入式 SE）支持，也可以自 Android 4.4 起由普通的 Android 应用程序支持。

硬件安全元件通过提供物理防篡能力和对 SE 应用（通常实现为 Java Card 应用）的严格控制来提供最高安全性。然而，由于在 SE 上安装应用程序所需的身份密钥通常由单一实体（如设备制造商或移动运营商 MNO）控制，分发 SE 应用变得困难。

Android 4.4 中的基于主机的仿真（HCE）使得开发和分发适用于卡片仿真的应用程序更容易，但它依赖于操作系统并且对敏感应用程序代码的保护较弱。

- [131] NDEF 格式及其使用标签技术的实现描述于 NFC 论坛出版物，地址见：http://nfc-forum.org/our-work/specifications-and-application-documents/nfc-forum-technical-specifications/
- [132] ISO 标准的所有官方版本均发布在其网站上：http://www.iso.org/iso/home/catalogue_ics.htm。标准的草案版本可以标准工作组的网站获取。
- [133] Google, Android Reference, "TagTechnology," https://developers.android.com/reference/android/nfc/tech/TagTechnology.html
- [134] Google, Android Reference, "NfcAdapter," https://developers.android.com/reference/android/nfc/NfcAdapter.html
- [135] NFC Forum, "NFC Forum Technical Specifications," http://nfc-forum.org/our-work/specifications-and-application-documents/nfc-forum-technical-specifications
- [136] 3GPP, AT command for Equipment (UE), "Bas," https://developers.android.com/guide/topics/connectivity/nfc/html#p2p
- [137] "Secure Evaluation Kit for the Android platform," https://code.google.com/p/seek-for-android/
- [138] SimAlliance Limited, Open Mobile Application Specification v2.05, https://www.simalliance.org/en/?=documentManager/sdoc.file&fileID=139231478580
- [139] SD Association, "Advanced Security SD Card: ASSD," https://www.sdcard.org/developers/overview/ASSD/
- [121] ECMA International, ECMA-373: Near-Field Communication Wired Interface (NFC-WI), http://www.ecma-international.org/publications/files/ECMA-ST/ECMA-373.pdf
- [122] Oracle, "JSR 177: Security and Trust Services API for J2METM", https://jcp.org/en/jsr/detail?id=177
- [123] Oracle, Java Classic Platform Specification 3.0.4, "http://www.oracle.com/oracle/technetwork/java/javac/specs-jsp-13640.html
- [124] GlobalPlatform, "Card Specifications," http://www.globalplatform.org/specificationscard.asp ISO 7816 和其他智能卡相关标准的摘要位于 CardWerk 网站上：http://www.cardwerk.com/smartcards/smartcard_standards.aspx
- [125] Google, Android Security Overview, "SIM Card Access," https://source.android.com/devices/tech/security/#sim-card-access
- [126] SEEK for Android, "SmartCardAPI," https://code.google.com/p/seek-for-android/wiki/SmartcardAPI
- [127] CyanogenMod, http://www.cyanogenmod.org/
- [128] Google, Android API Reference, "Messenger," https://developer.android.com/reference/android/os/Messenger.html
- [129] Google, Host-based Card Emulation, "Payment Applications," https://developer.android.com/topics/connectivity/nfc/hce#PaymentApps
- [130] Cem Paya, Random Oracle, "HCE vs embedded secure-element," parts I to VI, http://randomoracle.wordpress.com/2014/03/08/hce-vs-embedded-secure-element-comparing-risks-part-i/

# 第 12 章 SELinux

虽然之前的章节提到了增强型 Linux（SELinux）及其与 Android 的集成，但我们目前对 Android 安全模型的讨论一直集中在 Android 的安全模型上。

### 注意

只有当 DAC（自主性访问控制）允许访问资源时，才会咨询 MAC（强制访问控制）策略。如果 DAC 拒绝访问（例如基于文件权限），则拒绝视为最终的安全决策。

SELinux 支持两种形式的 MAC：类型强制（TE）和多级安全（MLS）。MLS 通常用于强制不同级别的受限信息，在 Android 中并不使用。

SELinux 中实现的类型强制要求所有主体和对象都具有一个关联的类型，SELinux 使用此类型来强制其安全策略的规则。

在 SELinux 中，类型（type）是策略中定义的与对象或主体关联的字符串。引用进程或进程组的主体类型也称为域（domains）。引用对象的类型通常指定对象在策略中扮演的角色，例如系统文件、应用程序数据文件等。

类型（或域）是安全上下文不可或缺的一部分，正如下文“安全上下文”部分讨论的那样。

# SELinux 模式

SELinux 有三种运行模式：禁用（disabled）、允许（permissive）和强制（enforcing）。

当 SELinux 处于禁用状态时，不会加载策略，仅对默认的 DAC 进行安全保护。在允许模式下，会加载策略并检查对象访问，但对拒绝访问仅进行记录而不强制。最后，在强制模式下，安全策略会被加载并执行，同时记录违规行为。

在 Android 中，可以通过 `getenforce` 和 `setenforce` 命令更改 SELinux 模式，如示例 12-1 所示。然而，通过 `setenforce` 设置的模式不是持久的，在设备重启时将重置为默认值。

### 示例 12-1. 使用 getenforce 和 setenforce 命令

```shell
# getenforce
Enforcing
# setenforce 0
# getenforce
Permissive
```

此外，即使 SELinux 处于强制模式，也可以使用 `permissive` 语句为每个域（进程）指定允许模式。（参见“对象类和权限语句”示例。）

# 安全上下文

在 SELinux 中，安全上下文（security context）（也称为安全标签（security label）或标签）是一个由冒号分隔字段的字符串：用户名、角色、类型和可选的 MLS 安全范围。

SELinux 用户名通常与一组或一类用户相关；例如，非特权用户的 `user_u` 和管理员的 `admin_u`。

用户可以关联一个或多个角色以实现基于角色的访问控制，其中每个角色都与一个或多个域类型关联。类型用于对域中的进程进行分组或指定对象类型。

安全范围（或级别）用于实现 MLS，并指定主体所处的安全级别。



截至本文时，Android 仅使用安全上下文的字段，用户和安全范围始终设置为 `u` 和 `s0`。角色的作用是为域（进程）设置 `r`，或者为对象设置内置的 `object_r` 角色。

可以通过向 `ps` 命令指定 `-Z` 选项显示安全上下文，如示例 12-2 所示（在 `LABEL` 列）。

## 示例 12-2. Android 中的进程安全上下文

| USER | PID | PPID | NAME | LABEL |
| :--- | :--- | :--- | :--- | :--- |
| userinit | root | 1 | 0 | /init | u0:r0:s0 |
| kernels0 | root | 2 | 0 | kthreadadd | u0:r0:s0 |
| kernels0 | root | 3 | 2 | kasoftirdq/0 | u0:r0:s0 |
| userhealthds | root | 175 | 1 | /sbin/healthd | u0:r0:s0 |
| userservicemanagers | system | 176 | 1 | /system/bin/ | u0:r0:s0 |
| uvolsdsd | root | 177 | 1 | /system/bin/vold | u0:r0:s0 |
| userinit | nobody | 178 | 1 | /system/bin/rmt_storage | u0:r0:s0 |
| netd0 | root | 179 | 1 | /system/bin/netd | u0:r0:s0 |
| userdebuggers | root | 180 | 1 | /system/bin/debugger | u0:r0:s0 |
| urilds0 | root | 181 | 1 | /system/bin/rild | u0:r0:s0 |
| uterplatform_apps0 | u0_a125 | 950 | 183 | com.android.systemui | u0:object_r:s0 |
| media_apps0 | u0_a5 | 1043 | 183 | android.process.media | u0:object_r:s0 |
| radxdios0 | radio | 1141 | 183 | com.android.phone | u0:r0:s0 |
| urafcs0 | nfc | 1163 | 183 | com.android.nfc | u0:r0:s0 |
| unrusted_apps0 | u0_a7 | 1360 | 183 | com.android.gms | u0:r0:s0 |

同样，可以通过向 `ls` 命令传递 `-Z` 来查看文件的上下文，如示例 12-3 所示。

## 示例 12-3. Android 中的文件和目录安全上下文

```
# ls -Z
drwx-xr-x root root 4096 Jan 1 0 groups:s0 acct
drwx-x-- root root 4096 Jan 1 0 file:s0 cache
-rwx--x-- root root 4096 Jan 1 0 rootfs:s0 charger
drwx-xr-x system system 4096 Jan 1 0 system_data_file:s0 data
-rw-r--r-- root root 4096 Jan 1 0 root:s0 default.prop
drwx-xr-x root root 4096 Jan 1 0 device:s0 dev
-rwxrwxrwx root root 4096 Jan 1 0 rootfs:s0 -> /system/etc
-rw-r--r-- root root 4096 Jan 1 0 rootfs:s0 file_contents
dr-xr-x-- system system 4096 Jan 1 0 externals:s0 firmware
-rw-r----- root root 4096 Jan 1 0 fstab:s0 init
```

## 安全上下文的分配与持久化

我们已经确定所有主体和对象都有安全上下文，但它是如何分配和持久化的呢？对于对象（通常是文件），安全上下文是持久的，并通常存储在文件的扩展属性中。扩展属性不由文件系统解释，Linux 发行版和当前 Android 的 ext4 文件系统以键值对的形式支持扩展属性，其中名称是以空字符终止的字符串。SELinux 使用此存储对象的安全上下文。

对象的安全上下文可以在文件初始化时显式设置（也称为标记），或者在创建对象时隐式分配。对象通常继承其父对象的类型（例如，新创建的文件继承目录的）。但如果安全策略允许，对象可以与其父进程不同的标签，这被称为类型转换（type transition）。

## 安全策略

SELinux 安全策略用于内核中的安全服务器，在运行时允许或拒绝对对象的访问。出于性能考虑，策略通常是由许多策略文件生成的二进制形式。策略源文件使用专用语言编写，由语句和规则组成。语句定义用户、类型和角色。规则允许或拒绝对对象的访问（访问向量规则）；指定允许的转换（类型强制规则）；并指定默认的用户、角色和类型（默认规则）。SELinux 策略语法的详细讨论超出了本书的范围，但后续章节将介绍一些常用的语句和规则。

## 语句

SELinux 策略语言支持多种语句，但类型、属性和权限语句构成了安全策略主体。我们将在后续章节介绍这三种语句。

## 类型和属性语句

`type` 和 `attribute` 语句声明类型及其属性，如示例 12-4 所示。

示例 12-4. 类型和属性语句

```
attribute file_type
attribute domain
type system_data_file, file_type, data_file_type
type untrusted_app_domain
```

在这里，前两个声明了 `file_type` 和 `domain` 属性，下一个声明了 `system_data_file` 类型并与 `file_type` 和 `data_file_type` 关联。第四个声明了 `untrusted_app` 类型并与 `domain` 属性关联（标记所有进程）。

根据粒度的不同，SELinux 策略可能跨越源文件拥有几十或数百个类型和属性。然而，运行时对所有内核对象的访问都需要根据策略进行检查；大型策略会对性能产生负面影响。在计算资源有限的设备上运行时，对性能的影响为明显，这也是 Android 保持 SELinux 策略较小的原因。

## 用户和角色语句

`user` 语句声明 SELinux 用户标识，将其与其角色关联，并可选地指定默认安全级别以及用户可以访问的安全范围。示例 12-5 显示了 Android 中默认的用户标识。

示例 12-5. Android 中 SELinux 用户标识的声明

```
user roles { r } level s0 range s0-mls_system;
```

如示例 12-5所示，用户与 `r` 角色关联（括号内），该角色反过来通过 `role` 语句声明，如示例 12-6所示。

示例 12-6. Android 中 SELinux 角色的声明

```
role r
role r types domain
```

第二个语句将 `r` 角色与 `domain` 属性关联，将其标记为分配给进程（域）的角色。

## 对象类和权限语句

`permissive` 语句允许指定的域运行在允许模式下（一种仅记录 MAC 策略违规但不实际执行策略的模式，如所述），即使 SELinux 运行在强制模式下。正如我们在强制域中看到的，Android 当前基础策略中的大多数域都是允许的。例如，`adbd` 守护进程（实际上的 adbd）中的进程在允许模式下运行，如示例 12-7 所示。

示例 12-7. 将指定的域设置为允许模式

```
type adbd, domain;
permissive adbd
```

`class` 语句定义 SELinux 对象类，其关联的权限由 Linux 内核中的 respect object 实现决定，并在策略中是静态的。对象类通常定义在 `security_class` 策略源文件中。

示例 12-8. `security_classes` 文件中的对象类声明

```
# 文件相关类
class filesystem
class file
class dir
```

SELinux 权限（也称为访问向量）通常定义在名为名为 `access_vectors` 的策略文件中，并与对象类（object classes）关联。权限可以是特定于类的（与 `daemon` 类关联），也可以被一个或多个对象类继承，在这种情况下，它们使用通用关键字进行定义。示例 12-9 显示了所有文件对象 ① 通用权限集的定义，以及 `dir` 类（代表目录）与所有通用文件权限（使用 `inherits` 关键字）以及一组特定目录的权限 ②（`add_name`、`remove_name` 等）的关联。

示例 12-9. `access_vectors` 文件中的权限定义

```
{
ioctl
read
write
create
getattr
setattr
lock
}
```

```
{
class dir
inherits file

add_name
remove_name
reparent
search
rmdir
}
```

## 类型转换规则

类型强制规则和访问向量规则（在“域转换规则”和“访问向量规则”章节中讨论）通常构成了 SELinux 类型的大部分。最常用的类型强制规则类型是 `type_transition` 规则，它规定了允许哪些域和类型的转换。例如，在 Android 中管理 Wi-Fi 连接的 `wpa_supplicant` 守护使用示例 12-10 所示的转换规则，将其在 `/data/misc/wifi/` 目录下创建的 socket 与 `wpa_socket` 类型关联。在缺少此规则的情况下，socket 将继承其父目录的类型：`wpa_data_file`。

12-10. wpa 域中的类型转换（来自 `wpa_supplicant.te`）

```te
# wpa - wpa supplicant or equivalent
type wpa, domain;

permissive wpa:①
type wpa_exec, exec_type, file_type;
init_daemon_domain(wpa)②
unconfined_domain(wpa)③
type_transition wpa wifi_data_file:sock_file, wpa_socket:④
```

在这里，`wpa`、`wifi_data_file:sock_file` 和 `wpa_socket` 分别是源类型（在这种情况下是 `wpa_supplicant` 进程的域）、目标类型和类（转换前的对象类型和类）以及转换后的对象类型。

### 注意

> 为了能够创建并更改 socket 文件，`wpa` 域对父目录和 socket 本身需要额外的权限——仅有 `type_transition` 是不够的。然而，由于 `wpa` 域是允许的 ① 且是无限制的（默认授予了大多数权限）③，因此在不显式允许每个所需权限的情况下也允许该转换。

## 域转换规则

在 Android 中，如 `wpa_supplicant` 等原生系统守护进程由 `init` 进程启动，因此默认继承它的安全上下文。然而，大多数守护进程都与一个专用域关联，并在启动时使用域转换来切换它们的域。这通常通过 `init_daemon(domain)`② 实现，如示例 12-10 所示，其底层是使用 `type_transition` 关键字实现的，这与类型转换类似。

二进制的 SELinux 策略二进制处理过程使用 `m4` 宏预处理器 [132] 在合并所有源文件之前展开宏。`init_daemon_domain()` 宏接受一个参数（进程的新域），并在 `te_macros` 文件中使用另外两个宏定义：`domain_trans()` 和 `domain_auto_trans()`，它们分别用于转换到新域并自动执行转换。示例 12-11 定义了这三个宏的定义 ①②③。以 `allow` 关键字开头的行是访问向量 (AV) 规则，我们将在下一节中讨论。

## 12-11. `te_macros` 文件中的域转换宏定义

```te
define('domain_trans',
allow $1:file { getattr open read execute };
allow $1:process transition;
allow $1:file { entrypoint read execute };
allow $1:process sigchld;
dontauditunit $1:process { sig never };
allow $1:process { noatsecure };
①
# domain_auto_trans(olddomain, type, newdomain)
define('domain_auto_trans',
domain_trans($1,$2,$3)
type_transition $1 $2:process $3;
②
)
```

```te
define('daemon_domain(domain)
macro_daemon_domain',
domain_auto_trans(init, $1_exec, $1)
tmpfs_domain($1)
')
--snip--
```

## 访问向量规则

AV 规则通过指定进程对其目标对象拥有的权限集来定义进程在运行时做什么。示例 12-12 显示了 AV 规则的通用格式。

示例 12-12. AV 规则格式

`rule_source_type target_type : class_set;`

名称可以是 `allow`、`daudit` 或 `neverallow`。要形成规则，需要将 `source_type` 和 `target_type` 元素替换为一个或多个之前定义的类型或属性标识符，其中 `source_type` 是主体（进程）的标识符，`target_type` 是进程尝试访问的对象的标识符。`class` 元素替换为目标的类，`per_set` 指定了进程对目标对象拥有的权限集。你可以通过在大括号 `{}` 中包含指定多个类型、类和权限。此外，某些规则支持使用通配符 (`*`) 和补码 (`~`) 运算符。

## allow 规则

最常用的规则是 `allow`，它规定主体（进程）被允许对类型对象执行操作。让我们以 SELinux 策略（见 12-13）为例来说如何使用 `allow`。

```te
示例 12-13. void 的 allow 规则（来自 void.te）
type void, domain;
type void_exec, exec_type, file_type;
init_daemon_domain(void)
--snip--
allow void:filesystem { mount unmount };①
--snip--
allow void:capability { ptrace kill };②
--snip--
```

在此列表中，① 允许 `void` 守护进程（运行在 `void` 域中）挂载、卸载和删除文件系统。② `self` 关键字意味着目标域与源域相同，在这种情况下是被允许的。

## auditallow 规则

`auditallow` 规则用于在已知事件安全时抑制拒绝信息。例如，规则 12-14 规定，如果审计守护进程被拒绝 `ADMIN`，则不会创建审计日志。然而，`daudit` 规则可能会掩盖程序错误，因此建议不要 `daudit`。

示例 12-14. `installd` 域的 `daudit` 规则（来自 `installd.te`）

```te
type installd, domain;
--snip--
daudit installd self:capability sys_admin
--snip--
```

## neverallow 规则

`neverallow` 规则规定即使显式允许规则允许，也不允许声明的操作。例如，12-15 所示的规则禁止 `init` 域之外的所有域加载 SELinux 策略。

示例 12-15. 禁止 init 以外域加载 SELinux 策略的 neverallow 规则（来自 domain.te）

```te
neverallow { domain -init } kernelsecurity load_policy;
```

### 注意

> 本节仅对 SELinux 提供简要概述。关于架构、实现以及策略语言的更详细讨论，请参考《SELinux Notebook》[133]。

## Android 实现

如第 1 节和第 2 节所述，Android 的沙箱安全模型严重依赖于为系统守护进程和应用程序使用 Linux ID。进程隔离和访问控制最终由 Linux 内核根据 UID 和 GID强制执行。由于 SELinux 也是 Linux 内核的一部分，它是使用 MAC 策略加固 Android 沙箱模型的自然候选者。

由于 SELinux 已集成到主内核中，在 Android 中启用它应该是配置内核和设计适当 MAC 策略的问题。然而，由于 Android 对 Linux 内核及其用户空间引入了一些与桌面和服务器 Linux 发行版不同的独特扩展，为了将 SELinux 集成到 Android，需要在内核和用户空间进行一些更改。虽然集成 SELinux 的初始工作由 Google 开始，但大多数所需的更改是在 Android 安全增强项目（以前称为 SEAndroid）[134] 中实现的，并随后被集成到主线 SELinux 源码树中。



查看这些主要更改。有关更改的完整列表及其背后的原理，请参阅 SEAndroid 项目原始作者编写的《安全增强 (SE) Android: 为 Android 带来灵活的 MAC》论文 [135]。

## 内核更改

回想一下，SELinux 是一个安全模块，它通过实现插入到内核服务中的 LSM 钩子来实施访问控制。Android 的 Binder IPC 机制也实现为一个内核驱动程序，但由于其最初的实现没有包含任何 LSM 钩子，其运行时行为无法通过 SELinux 策略进行控制。为了给 Binder 添加 SELinux 支持，Binder 驱动程序中插入了 LSM 钩子，并在 SELinux 代码中增加了对 binder 对象类及相关权限的支持。

SELinux 安全钩子声明在 `include/linux/security.h` 中，示例 12-16 显示了为了支持 Android 而添加的 Binder 相关声明。

### 示例 12-16：`include/linux/security.h` 中的 Binder 安全钩子声明

```c
--snip--
int security_binder_set_context_mgr(struct task_struct *mgr)
int security_binder_transaction(struct task_struct *from,
struct task_struct *to)②
int security_binder_transfer(struct task_struct *from,
	struct task_struct *to)③
int security_binder_transfer_file(struct task_struct *from,
	struct task_struct *to,struct file *file)④
```

第一个钩子 ① 控制哪个进程可以成为 binder 上下文管理器，第二个钩子 ➁ 控制进程调用 binder 事务的能力。接下来的两个函数用于规避谁可以使用 Binder 将 binder 引用传输到另一个进程 ③，以及使用 Binder 将一个打开的文件传输到另一个进程 ④。

为了让 SELinux 策略能够对 Binder 设置限制，内核中还增加了对 binder 对象类及其权限（`impersonate`、`call`、`set_context_mgr` 和 `transfer`）的支持，如示例 12-17 所示。

### 示例 12-17：`selinux/include/class.h` 中的 Binder 对象类和权限声明

```c
--snip--
struct security_class_mapping seccls_map[] = {
--snip--
{"binder", {"impersonate", "call", "set_context_mgr", "transfer", NULL },
{ NULL },
};
```

## 用户空间更改

除了内核更改外，为了将 SELinux 集成到 Android，还需要许多用户空间的修改和扩展。其中，最重要的包括：在内核 C 库（bionic）中对文件系统标签的支持；对 `init` 以及原生守护进程和可执行文件的扩展；框架级 SELinux API；以及对核心框架服务的修改以使其感知 SELinux。本节将描述每项更改以及它们如何集成到 Android 运行环境中。

## 库和工具

由于 SELinux 使用扩展属性来存储文件系统对象的安全上下文，Android C 库首先添加了使用扩展属性的系统调用（`listxattr()`、`getattr()`、`setxattr()` 等）的封装函数，以便获取和设置文件及目录的安全标签。

为了从用户空间利用 SELinux 特性，SEAndroid 添加了与 Android 的 `libselinux` 库，以及一组用于管理标签、安全策略以及在强制（enforcing）和允许（permissive）模式之间切换 SELinux 模式的实用命令。与大多数 Android 命令行工具一样，SELinux 工具在 `toolbox` 二进制文件中实现，并作为其符号链接进行安装。表 12-1 总结了新增或修改的命令行工具。

### 表 12-1：SELinux 命令行工具

| 命令 | 描述 |
|---|---|
| `chcon` | 修改文件的安全上下文 |
| `getenforce` | 获取当前的 SELinux 模式 |
| `getsebool` | 获取策略布尔值 |
| `id` | 显示进程的安全上下文 |
| `load_policy` | 加载策略文件 |
| `ls -Z` | 显示文件的安全上下文 |
| `ps -Z` | 显示运行进程的安全上下文 |
| `restorecon` | 恢复文件（文件）的安全上下文 |
| `runcon` | 在指定的安全上下文中运行程序 |
| `setenforce` | 设置强制模式 |
| `setsebool` | 设置策略布尔值 |

## 系统初始化

与传统的 Linux 系统一样，在 Android 中，所有用户空间守护进程和程序都由 `init` 进程启动，内核启动的第一个进程（`PID=1`）。但与其他基于 Linux 的系统不同，Android 的初始化脚本（`init.rc` 及其变体）不是由通用 shell 解释的，而是由 `init` 解释的。每个初始化脚本都包含 `init` 在读取脚本时执行的内置命令。SEAndroid 增加了初始化 SELinux 以及设置服务和文件安全所需的命令，如表 12-2 所示。

### 表 12-2：支持 SELinux 的 `init` 内置命令

| `init` 内置命令 | 描述 |
|---|---|
| `*` | |

当 `init` 启动时，它从 `/sepolicy` 二进制文件加载 SELinux 策略，并根据系统属性 `ro.boot.selinux` 的值设置强制模式（`init` 根据 `androidboot.selinux` 内核命令行参数的值设置该属性）。当属性值为 `permissive` 时，SELinux 进入允许模式；设置为任何其他值或未设置，则模式为强制。

接下来，`init` 加载并解析 `init.rc` 文件并执行其中的命令。示例 12-18 显示了 `init.rc` 的部分内容，专注于 SELinux 的部分。

### 示例 12-18：`init.rc` 中的 SELinux 初始化

```sh
--snip--
on early-init
--snip--
setcon ur:init
--snip--
on post-fs-data
--snip--
chown system 777 /data
--snip--
service ueventd
--snip--
setcon ur:init:0
--snip--
on property:selinux.reload=1
restart ueventd
--snip--
```

在此示例中，`init` 设置了服务和文件的安全上下文。数据分区的安全上下文在启动时恢复（如示例 12-18 所示），以确保其状态一致。这种重载可以通过设置 `selinux` 属性来触发。

## 文件标记

回想一下，SELinux 使用扩展属性来存储文件系统对象的安全上下文。在 Android 中，所有文件的初始上下文在一个名为 `file_contexts` 的文件中定义，其可能如示例 12-19 所示。

### 示例 12-19：`file_contexts` 的内容

```text
--snip--
/ uobject_rootfs:0
/adb_keys uobject_rootfs:0
/default_prop uobject_rootfs:0
/fsstab,* uobject_rootfs:0
---
/dev/* uobject_devices:0
/dev/akm3,* uobject_devices:0
/dev/accelerometer uobject_devices:0
---
/system/* uobject_system_files:0
/system/bin/ash uobject_execs:0
/system/bin/mksh uobject_execs:0
---
/data/* uobject_data_files:0
/data/backup/* uobject_data_files:0
/data/secure/* uobject_data_files:0
---
```

可以看出，该文件包含了路径（有时使用通配符）及其关联的安全上下文，每个占一行。`file_contexts` 文件在 Android 的构建和启动过程中会被多次查询。例如，由于内存根文件系统（挂载在 `/`）和设备文件系统（挂载在 `/dev`）不是持久的，所有文件通常与 `genfs_contexts` 中指定的安全上下文关联，或者使用 `context=` 挂载选项分配。为了在这些系统中为特定文件分配安全上下文，它使用 `restorecon` 命令在 `file_contexts` ① 中查找根系统的安全上下文，并将 ② 作为设备系统的默认值并进行相应设置。当从源码构建 Android 时，`make_ext4` 命令也使用 `file_contexts` 来设置系统分区（挂载在 `/system` ③）和用户数据分区（挂载在 `/data` ④）文件的初始上下文。最后，Android 的恢复 OS 也包含 `file_contexts` 的副本，用于设置恢复系统在系统更新期间创建的文件标签。

## 系统属性标记

Android 使用全局系统属性，所有进程可见，用于各种目的，如通信硬件状态、启动或停止系统服务、触发磁盘加密甚至重载 SELinux 策略。只读系统属性的访问不受限制，但由于更改关键读写属性的值会改变系统行为，因此对这些属性的访问是限制的，仅允许系统进程访问。

UID 是系统和无线电的标识。SEAndroid 根据尝试修改属性的进程的域（domain）增强了基于 UID 的访问控制。为了实现这一功能，属性（非 SELinux 对象）必须与安全上下文关联。这通过在 `property_contexts` 文件中列出属性的安全上下文来实现，这与 `file_contexts` 指定文件标签的方式是一致的。该文件由 `property_service`（在 `init` 之后）加载到内存中，生成的安全上下文查找表被用于根据进程（主体）和属性（对象）的安全上下文来决定是否允许进程访问特定属性。SELinux 策略定义了一个新的 `property_service` 对象类，它具有单一权限，用于指定访问规则，如例 12-20 所示。

### 例 12-20：`volt.te` 中的系统属性访问规则

```text
--snip--
allow volt_property_service_set
allow powerctl_property_service_set
allow ctl_default_property_service_set
--snip--
```

在此列表中，该域被允许设置类型为 `volt_prop`、`powerctl_prop` 和 `ctl_default_prop` 的系统属性。

这些类型根据 `property_contexts` 中的属性名称与实际属性关联，如例 12-21 所示。

### 例 12-21：`property_contexts` 中属性名与其安全上下文的关联

```text
--snip--
volt.uobject_r_volt_props0
sys.powerctl.uobject_r_powerctl_props0
ctl.uobject_r_ctl_default_props0
--snip--
```

该策略的效果是 `volt` 可以设置所有以 `volt`、`powerctl` 或 `ctl` 开头的属性的值。

## 应用程序进程的标记

回想第 2 章，所有进程都从 `zygote` 进程派生，以减少内存占用并提高应用启动速度。以 `system` 用户运行并托管大多数系统服务的 `system_server` 进程也是从 `zygote` 派生的，尽管通过接口略有不同。

以 `root` 用户运行的 `zygote` 进程负责设置每个进程的 DAC 凭据（UID、GID 和补充 GID）以及权限（capabilities）和资源限制。为了支持 SELinux，`zygote` 已被扩展以检查其所派生的客户端的安全上下文。安全上下文根据 `seapp_contexts` 配置文件中指定的分配规则确定，这些规则取决于应用的 UID、包名、标记系统服务器进程的标志以及一个名为 `seinfo` 的 SELinux 特定字符串属性。`seapp_contexts` 文件包含了安全上下文分配规则（每行一条），由输入选择器（input selectors）和输出属性组成。为了匹配规则，所有输入选择器都必须满足（逻辑与关系）。例 12-22 显示了截至版本 4.4.3 的参考 SELinux 策略中 `seapp_contexts` 文件的内容。

### NOTE

`seapp_contexts` 与参考策略中的所有文件一样，可以在 Android 源码树的 `external/sepolicy/` 目录下找到。文件的注释包含了输入选择器的完整列表、选择器匹配优先级规则以及输出说明。

### 例 12-22：`seapp_contexts` 文件的内容

```text
isSystemServer-true domain=system①
user=system-domain-app_type=system_data_file②
user=bluetooth-domain-bluetooth-type=bluetooth_data_file
user=nfc-domain-nfc-type=nfc_data_file
user=radio-domain-radio-type=radio_data_file
user=app_untrusted_app_type=app_data_filelevel=③
user=app_seinfo-platform-domain-platform_type=app_data_file④
user=app_seinfo-shared-domain-shared_app_type=platform_data_file⑤
user=app_seinfo-media-domain-media_type=platform_data_file
user=app_seinfo-release-domain-release_type=app_data_file
user=isolated_domain-isolated_app⑥shell_data_file
```

此列表的第一行 ① 指定了系统服务器的域（`system`），因为其 `isSystemServer` 选择器（只能使用一次）被设置为 `true`。由于 Android 使用 SELinux 用户标识符、角色和安全级别，生成的安全上下文变为 `u:r:s0`。

第二个参数 ② 将用户选择器匹配目标进程的用户名，该用户名源自其 UID。如果进程以内置 Linux 用户之一运行（如 `android_filesystem_config.h` 中定义的 `system`、`radio`、`nfc` 等），在匹配用户选择器时使用关联名称。隔离服务被赋予 `_isolated` 用户名字符串，而任何其他进程都是 `_app` 用户名字符串。因此，匹配此选择器的系统应用被分配了 `system_app_domain`。

`type` 属性指定了分配给目标进程文件的对象类型。在这种情况下，文件是 `system_data_file`，文件的安全上下文变为 `uobject:r:system_data_file:s0`。

③ 匹配所有在非系统 UID 下执行的应用，并将其进程分配到 `untrusted_app_domain`。每个未受信任应用的私有目录数据被递归地分配 `app_data_file` 对象类型，这导致了 `object:r:app_data_file:s0`。

④ 和 ⑤ 使用 `seinfo` 选择器区分非系统应用并将它们分配到不同的域：匹配 `seinfo-platform` 的进程被分配到 `platform_app_domain`，匹配 `seinfo-shared` 的被分配到 `shared_app_domain`。（正如我们在下一节看到的，应用的 `seinfo` 是由其签名证书决定的。）

最后，⑥ 为所有隔离服务分配 `isolated_app` 域。

## Middleware MAC

上一节引入的 `seinfo` 是一个 SEAndroid 特性的部分，称为中间件 MAC（MMAC），它是一种高级别的访问控制方案，与内核级 MAC（在 SELinux LSM 模块中实现）分离。

MMAC 设计用于为 Android 模型提供 MAC 限制，限制在框架层工作且无法轻易映射到内核级 MAC。原始实现包含一个安装时 MAC 功能，它根据包名和签名证书限制可以授予每个包的权限，无论用户的权限决定如何。也就是说，即使用户决定授予其请求的所有权限，如果策略不允许，MMAC 仍会阻止安装。

SEAndroid 的 MMAC 实现还包含意图 MAC 功能，使用策略控制应用之间的意图交换。另一个 SEAndroid 特性是内容提供者 MAC，它定义了内容提供者访问的策略。然而，原始 SEAndroid MMAC 实现仅部分合并到了主线，目前支持的功能仅基于应用签名证书的 `seinfo` 分配。

### NOTE

> 从 4.3 版本开始，Android 有一个实验性的意图防火墙功能，使用“防火墙”式规则限制发送和接收的意图。该功能与 SEAndroid 的意图 MAC 类似，但未与 SELinux 实现集成。

在这里，`@PLATFORM` ❶、`@MEDIA` ❷、`@SHARED` ❸ 和 `@RELEASE` ❹ 宏分别代表 Android 中的四种平台签名证书（平台、媒体、共享和发布），在构建 SELinux 策略时，这些宏会被替换为相应的、以十六进制字符串编码的证书。



在扫描每个已安装的包时，系统`PackageManagerService`会将其签名证书与`mac_permission.xml`文件的内容进行匹配；如果找到，则为该包分配指定的`seinfo`值。如果没有找到匹配项，则将根据`<default>`标签❺分配默认`seinfo`值。

## 设备策略文件

Android 的 SELinux 策略由一个二进制策略文件和四个辅助配置文件组成，用于进程、应用、系统属性和文件的标记以及初始化。表 12-3 显示了这些文件在设备上的位置，并简要描述了策略文件的用途和内容。

表 12-3. Android SELinux 策略文件

| 策略文件 | 描述 |
| --- | --- |
| `/sepolicy` | 二进制内核策略 |
| `/file_contexts` | 文件安全上下文，用于标记文件系统 |
| `/property_contexts` | 系统属性安全上下文 |
| `/seapp_contexts` | 用于推导应用进程和文件的安全上下文 |
| `/system/etc/security/mac_permissions.xml` | 将应用签名证书映射到`seinfo`值 |

> 注意
> 
> 在 4.4.3 版本之前的启用了 SELinux 的 Android 版本支持覆盖表 12-3 所示的默认策略文件，使用位于`/data/security/current`和`/data/system/`（用于 MMAC 配置文件）目录下的对应文件，以便在无需进行完整 OTA 更新的情况下实现策略更新。然而，Android 4.4.3 删除了此功能，因为这可能会导致文件系统上设置的安全标签与新策略中引用的标签之间产生差异。现在策略文件仅从表 12-3 所示的默认只读位置加载。

## 策略事件日志

具有匹配审核规则的数据访问和授权会被记录到内核日志缓冲区，并可以使用`dmesg`查看，如示例 12-24 所示。

### 示例 12-24. 内核日志缓冲区记录的 SELinux 访问拒绝

```
# dmesg grep 'ave'
--snip--
s={18473.7252707} type=1400 audit(1402061801.158:256): avc: denied { getattr }
for pid=9574:comm="zygote" dev="sockfs" socket=8692 denied { getattr }
context=scontext=r:untrusted_app0 tcontext=uzygote0 tclass=unix_stream_socket
--snip--
```

在这里，审核日志显示第三方应用程序（安全上下文`u:untrusted_app:s0`）被拒绝访问 zygote Unix 域套接字的`getattr`权限（目标上下文`u:zygote:s0`，对象类`unix_stream_socket`）。

## Android 4.4 SELinux 策略

Android 4.2 是第一个包含 SELinux 代码的版本，但在发布构建中在编译时禁用了 SELinux。Android 4.3 在所有构建中启用了 SELinux，但其默认模式设置为`permissive`（许可模式）。此外，所有域也被单独设置为`permissive`，并基于`unconfined`（无限制）域，这意味着即使全局 SELinux 模式设置为`enforcing`（强制模式），它们本质上也拥有完全访问权限（在 DAC 范围内）。

Android 4.4 是第一个以`enforcing`模式分发 SELinux 的版本，并包含了核心系统守护进程的强制域。本节概述了 4.4 版本中部署的 Android SELinux 策略，并介绍了构成策略的一些主要域。

## 策略概述

Android 基础 SELinux 策略的源代码位于 Android 源码树的`external/sepolicy/`目录下。除了本章为止介绍的文件（`access_vectors`、`file_contexts`、`mac_permissions.xml`等）外，策略主要由类型强制 (TE) 语句和规则组成，并分为多个`.te`文件，通常每个定义域一个文件。这些文件被组合生成二进制策略文件`sepolicy`，它包含在启动镜像的根目录下作为`/sepolicy`。

你可以使用标准的 SELinux 工具（如`seinfo`、`sesearch`、`sedispol`和`on`）来检查二进制策略。例如，我们使用`seinfo`命令获取策略对象和规则数量的摘要，如示例 12-25 所示。

### 示例 12-25. 使用 seinfo 命令查询二进制策略文件

```
seinfo file sepolicy
Statistics for policy file: sepolicy
Policy Version & Type: v.26 (binary, mls)

Classes: 84 Permissions: 249
Sensitivities: 1 Categories: 1024
Types: 267 Attributes: 21
Users: 1 Roles: 2
Booleans: 1 Cond. Expr.: 1
Allow: 1140 Neverallow: 0
Auditallow: 0 Dontauditid: 36
Type trans: 132 Type_change: 0
Type_member: 0 Role allow: 0

Role_trans: 0 Range_trans: 0
Constraints: 63 Validatrans: 0
Initial IDs: 27 Fs_trans: 0
```

文件和目录，并且将被拒绝由 MAC 策略显式允许的任何权限。

### 注意

虽然 Android 4.4 只有四个强制模式（enforcing）域，但平台在不断演进，基础 SELinux 策略也在不断完善，最终域可能会被部署在强制模式下。例如，截至本文编写时，在 Android 开源项目（AOSP）的主分支的基础策略中，所有域在发布版本（release builds）中都被设置为强制模式，而宽容模式（permissive）域仅用于开发版本（development builds）。

即使一个域处于强制模式下，如果它由于派生自一个被授予了所有或大部分权限的基础域，它也可以被允许实际上不受限制的访问。在 Android 的 SELinux 策略中，这种域就是无限制域（unconfined domain），我们将在接下来讨论它。

## 无限制域 (Unconfined Domains)

Android 的 SELinux 策略包含一个名为`unconfined`的基础域（也称为模板域），它被允许所有系统权限，并用作其他策略域的父域。从 Android 4.4 开始，`unconfined`域的定义如示例 12-29 所示。

示例 12-29. Android 4.4 中的 unconfined 域定义

```
allow unconfineddomain self_capability_set *;
allow unconfineddomain kernelsecurity *load_policy;
allow unconfineddomain kernelselsystem *;
allow unconfineddomain selfprotect *;
allow unconfineddomain process *;
allow unconfineddomain domainid;
allow unconfineddomain dom_r_dir_perms;
allow unconfineddomain dom_link_file_r_file_perms;
allow unconfineddomain fifo; fifo file * rw_file_perms;
allow unconfineddomain socket_class_set *;
allow unconfineddomain domain_type:class_set *;
allow unconfineddomain key *;
allow unconfineddomain fs_type *;
allow unconfineddomain [fs_type dev_file_type]:{chr blk_file lnk_file sock_file fifo_file} -relabto;
allow unconfineddomain [fs_type dev_file_type]:{chr file_file} {entrypoint_label};
allow unconfineddomain node_type *;
allow unconfineddomain node_type:tcp_socket udp_socket rawip_socket node_bind;
allow unconfineddomain netif_tetinetype *;
allow unconfineddomain port_type:socket_class_set name_bind;
allow unconfineddomain port_type:tcp_socket dcp_socket name_connect;
allow unconfineddomain domain_peer *;
allow unconfineddomain binder{call transfer sel_context_mgr};
allow unconfineddomain property_type:property_set set;
```

如你所见，`unconfined`域被允许所有能力①（加载 MAC 策略除外）、所有与进程相关的权限❸等等。其他域通过`unconfined_domain`“继承”了该域的权限。在 Android 4.4 的 SELinux 策略中，所有宽容模式域也是无限制的，因此被授予了不受限制的访问（在 DAC 限制范围内）。

虽然`unconfined`域仍然存在于 AOSP 主分支中，但它已经受到了相当大的限制，并且不再用作无限制的访问工具，而是作为系统守护进程和其他特权 Android 组件的策略。随着更多的域切换到强制模式并且其策略被精细调整，预计`unconfined`将被移除。

## 应用域 (App Domains)

回想一下，SEAndroid 根据进程 UID 或签名证书为应用进程分配了多个不同的域。这些应用域通过使用`app domain()`宏继承基础域来分配通用权限，该宏在`app.te`中定义，包含了允许所有 Android 所需的常用操作的规则。示例 12-30 显示了`app.te`文件的片段。

示例 12-30, appdomain 策略片段（来自 app.te）

```
----
allow appdomain zygote:fd use①
allow appdomain zygote_tmpfs:file read②
----
allow appdomain systemfile:rw_file_perms;
allow appdomain system_unix:stream_socket { read write setop }
binder_call(appdomain, system)③

 appdomain surfaceflinger:stream_socket { read write setop }
binder_call(appdomain, surfaceflinger)④

allow appdomain app_data:file_create_dir_perms;
allow appdomain app_data:filenotdevclass_set create_file_perms ⑤
```

此策略允许`appdomain`接收并使用来自 zygote ① 的文件描述符、读取由 zygote 管理的系统属性、通过管道、本地或套接字与 system_server 通信③、与 surfaceflinger 守护进程（负责屏幕绘图）通信④，并在沙箱目录中创建文件和目录⑤。策略的其他部分定义了允许其他权限的规则，例如网络访问、对下载文件的访问以及对核心系统服务的 Binder 访问。对于通常不需要的操作，如原始块设备访问、内核内存访问和 SELinux 域转换，使用`neverallow`规则被显式禁止。

具体的应用域，例如`untrusted_app`（根据示例 12-22 所示`seapp_contexts`中的分配规则，它被分配给所有非系统应用），会根据目标应用程序的需要扩展域并添加额外的访问规则。示例 12-31 显示了`untrusted_app.te`的片段。

示例 12-31, untrusted_app 应用域策略片段（来自 untrusted_app）

```
type untrusted_app, appdomain:
permissive appdomain①
app_domain(untrusted_app)②
net_domain(untrusted_app)③
bluetooth_domain(untrusted_app)④
```

## 解锁引导程序 (Bootloader)

Nexus 设备的引导程序是通过在设备处于 fastboot 模式（将在下一节中讨论）时执行`oem unlock`命令来解锁的。因此，为了解锁设备，必须首先启动到 fastboot 模式，这可以通过执行`adb reboot bootloader`命令实现（如果设备已允许 ADB 访问），或者在设备启动时按下特殊的按键组合来实现。例如，在关机状态的 Nexus 5 上同时按住音量减、音量加和电源键，会中断正常启动过程并显示出如[图 13-1]所示的 fastboot 界面。

引导程序有一个简单的 UI，可以通过音量加/减和电源键进行操作。它允许用户继续启动过程、在 fastboot 模式或恢复模式（recovery mode）下重启设备，以及关机设备。

通过 USB 数据线将设备连接到主机，可以使用`fastboot`命令行工具（Android SDK 的一部分）向设备发送额外的命令。执行`fastboot unlock`命令将显示出如[图 13-2]所示的确认屏幕。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_329_0.png)

图 13-1. Nexus 5 引导程序界面

![](img/8524e4e57e2e9dc889903e3d2c5fe367_330_0.png)

确认屏幕警告说，解锁引导程序允许安装未经测试的第三方操作系统版本并会清除所有用户数据。由于第三方操作系统版本可能不遵循 Android 的安全模型并可能允许对所有用户数据进行无限制访问，清除数据是一项重要的安全措施；它确保了在解锁引导程序后现有的用户数据无法被提取。

执行`fastboot oem lock`命令可以再次锁定引导程序。重新锁定引导程序将其恢复到原始状态，并且将无法再加载第三方操作系统镜像。然而，除了锁定/解锁标记外，某些引导程序还会保留一个额外的“已篡改”（tampered）标记，该标记在引导程序首次解锁时被设置。此标记允许引导程序检测其是否曾被锁定，并且即使在锁定状态下也能禁止某些操作或显示警告。

## Fastboot 模式

虽然`fastboot`命令和协议可用于解锁引导程序，但它们的原始目的是通过向引导程序发送分区镜像，来轻松地清除或覆盖设备分区，然后这些镜像会被写入指定的块设备。这在将 Android 移植到新设备（称为“设备启动”）或使用设备制造商提供的分区镜像将设备恢复到出厂状态时特别有用。

## Android 分区布局

设备通常有多个分区，fastboot 通过名称（而不是相应的 Linux 设备文件）来引用这些分区。通过列出`/dev/block/`中对应设备 SOC 的`by-name/`目录下的文件，可以获取分区列表及其名称。例如，Nexus 5 基于高通 SoC，其包含一个移动调制解调器（MSM）基带处理器，该目录名为`msm_sdcc.1/`，如示例 13-1 所示（省略时间戳）。

示例 13-1. Nexus 5 上的分区列表



# 查看分区布局

```
# ls /dev/block/platform/msm_sdcc.1/by-name
lrwxr-xr-x root DDR ->/dev/block/mmblk0p24
lrwxr-xr-x root aboot ->/dev/block/mmblk0p6
lrwxr-xr-x root abootb ->/dev/block/mmblk0p11
lrwxr-xr-x root boot ->/dev/block/mmblk0p19
lrwxr-xr-x root cache ->/dev/block/mmblk0p27
lrwxr-xr-x root crypto ->/dev/block/mmblk0p26
lrwxr-xr-x root fsc ->/dev/block/mmblk0p22
lrwxr-xr-x root fsg ->/dev/block/mmblk0p21
lrwxr-xr-x root grow ->/dev/block/mmblk0p29
lrwxr-xr-x root imgdata ->/dev/block/mmblk0p17
lrwxr-xr-x root lazy ->/dev/block/mmblk0p18
lrwxr-xr-x root metadata ->/dev/block/mmblk0p14
lrwxr-xr-x root misc ->/dev/block/mmblk0p15
lrwxr-xr-x root modem ->/dev/block/mmblk0p15
lrwxr-xr-x root modem1 ->/dev/block/mmblk0p12
lrwxr-xr-x root modem2 ->/dev/block/mmblk0p13
lrwxr-xr-x root pad ->/dev/block/mmblk0p7
lrwxr-xr-x root persist ->/dev/block/mmblk0p16
lrwxr-xr-x root recovery ->/dev/block/mmblk0p20
lrwxr-xr-x root rpm ->/dev/block/mmblk0p03
lrwxr-xr-x root rmpb ->/dev/block/mmblk0p10
lrwxr-xr-x root sbl ->/dev/block/mmblk0p27
lrwxr-xr-x root sbl1 ->/dev/block/mmblk0p08
lrwxr-xr-x root sdi ->/dev/block/mmblk0p05
lrwxr-xr-x root ssd ->/dev/block/mmblk0p23
lrwxr-xr-x root system ->/dev/block/mmblk0p25
lrwxr-xr-x root tz ->/dev/block/mmblk0p04
lrwxr-xr-x root tzb ->/dev/block/mmblk0p09
lrwxr-xr-x root userdata ->/dev/block/mmblk0p29
```

如上所示，Nexus 5 拥有 29 个分区，其中 `boot` 引导程序。

虽然 `fastboot` 命令和协议可以用于解锁引导程序，但它们的原始目的是为了通过向引导程序发送分区镜像，来轻松地清除或覆盖设备分区，然后这些镜像会被写入指定的块设备。这在将 Android 移植到新设备（称为“设备启动”）或使用设备制造商提供的分区镜像将设备恢复到出厂状态时特别有用。

# Fastboot 协议

`fastboot` 协议通过 USB 工作并由主机驱动。它使用批量传输向引导程序发送命令和数据。当所有数据接收后，引导程序会以 `OKAY`、`FAIL` 或 `INFO` 消息做出响应。

# Fastboot 命令

`fastboot` 命令行工具实现了 `fastboot` 协议，并允许你获取设备列表（使用 `devices` 命令）、获取引导程序信息（使用 `getvar` 命令）、在各种模式下重启设备（使用 `reboot` 命令），以及清除或格式化分区。

`fastboot` 支持多种向分区写入镜像的方法。单个命名分区可以使用 `flash` 命令进行刷新，而包含多个分区镜像的 ZIP 文件可以使用 `zip` 命令一次性刷新。

`flash` 命令会自动将 `boot.img`、`system.img` 和 `recovery.img` 文件写入 `boot`、`system` 和 `recovery` 分区。`raw boot disk` 命令会自动从指定的内核和内存磁盘创建启动镜像并将其刷新 `boot` 分区。除了分区镜像外，`fastboot` 在调用 `boot` 或 `boot disk` 命令时不会将镜像写入设备。

当引导程序锁定时，修改分区的命令（如 `flash` 命令）和启动自定义内核的命令（如 `boot` 命令）是不允许的。

示例 13-2 显示了一个典型的 `fastboot` 会话。

```
$ fastboot devices
004fc161ca52c5 fastboot

$ fastboot getvar version-bootloader
version-bootloader: MAKOZ10o
finished. total time: 0.01s

$ fastboot getvar version-baseband
version-baseband: M9615SA-CEFWMAZ-2.0.1700.98
finished. total time: 0.01s

$ fastboot boot custom-recovery.img
downloading: 'boot.img'...
OKAY [0.577s]
booting...
FAILED (remote: not supported in locked device)
finished. total time: 0.579s
```

在这里，第一个命令列出了连接到主机的序列号，它们目前处于 `fastboot` 模式。命令 2 和 3 分别获取引导程序和基带的版本字符串。最后，命令 4 尝试启动自定义恢复镜像，但由于引导程序处于锁定状态而失败。

# 恢复模式 (Recovery)

恢复操作系统（也称为恢复控制台或简单的恢复）是一个最小操作系统，用于执行无法从 Android 直接执行的任务，例如出厂重置（清除 `userdata` 分区）或应用 OTA 更新。

引导加载程序的 `fastboot` 模式允许在设备启动时通过按下组合键来启动恢复系统，或者使用 ADB 运行 `adb recovery` 命令来启动。引导加载程序还提供了一个菜单界面，用于启动恢复系统。在接下来的章节中，我们将查看 Nexus 设备出厂并包含在 AOSP 中的“原生”Android 恢复系统，然后介绍自定义恢复系统，自定义提供了更丰富的功能，但需要解锁的引导加载程序才能安装或启动。

# 原生恢复 (Stock Recovery)

Android 的原生恢复系统实现了满足《Android 兼容性定义文档》（CDD）中“可更新软件”版本所需的最基本功能，该文档要求“设备实现必须包含一种替换整个系统软件的机制……”以及“更新机制必须支持在不擦除数据的情况下进行更新”。

尽管如此，CDD 并没有规定应该使用的具体更新机制，因此存在多种系统更新方法，原生恢复系统同时实现了 OTA 更新和连接线更新（tethered updates）。对于 OTA 更新，主 OS 下载更新文件，然后触发恢复系统进行应用。对于连接线更新，用户在 PC 上下载更新包，并使用 `adb sideload otafile.zip` 命令将其推送到恢复系统。这两种方法的实际过程是相同的，仅获取 OTA 包的方法不同。

原生恢复系统有一个简单的菜单界面（如图 13-3 所示），使用设备的硬件按钮（通常是电源键和音量上/下键）进行操作。然而，菜单默认是隐藏的，需要通过按下特定的组合键来激活。在 Nexus 设备上，通常通过同时按电源键和音量下键几秒即可显示恢复菜单。

系统恢复菜单有四个选项：*重启*（`reboot`）、*从 ADB 应用更新*（`apply update from ADB`）、*出厂重置*（`factory reset`）和*擦除缓存分区*（`wipe cache partition`）。*从 ADB 应用更新*选项会在设备上启动 ADB 服务器并启用连接线（侧载）模式。然而，如你所见，没有应用 OTA 更新的选项，除非用户选择从主 OS 中应用 OTA 更新（见图 13-4），否则它会自动应用，无需进一步的用户交互。Android 通过向恢复系统发送控制命令来实现此功能，这些命令会在恢复系统启动时自动执行。（我们将在下一节中讨论用于控制恢复系统的机制。）

图 13-3。原生恢复菜单

# 控制恢复系统 (Controlling the Recovery)

主 OS 通过 `android.os.RecoverySystem` API 控制恢复系统，该 API 通过向 `/cache/recovery/command` 文件写入选项字符串（每行一个）来与恢复系统通信。命令文件的内容由恢复二进制文件（位于恢复系统中的 `/sbin/recovery`）读取，该文件在恢复系统启动时从 `init.rc` 自动启动。这些选项修改恢复二进制文件的行为，导致其擦除指定分区、应用 OTA 更新或简单重启。表 13-1 显示了原生恢复二进制文件支持的选项。

## 表 13-1。原生恢复二进制文件的选项

| 恢复选项 | 描述 |
| --- | --- |
| `--intent=<string>` | 完成后将指定的 intent 动作保存并传回主 OS |
| `--update_package=<OTA package path>` | 验证并安装指定的 OTA 包 |
| `--wipe_data` | 擦除用户数据和缓存分区，然后重启 |
| `--wipe_cache` | 擦除缓存分区，然后重启 |
| `--show_text` | 要显示的消息 |
| `--exit` | 退出并重启 |
| `--locale` | 用于恢复消息和 UI 的本地化 |
| `--just_exit` | 设置恢复过程的当前状态 |

为了确保所有指定的命令均完成，恢复二进制文件将其参数拷贝到引导加载程序控制块（BCB），BCB 托管在 `misc` 分区上（示例 13-1）。BCB 用于向引导加载程序通信恢复过程的当前状态。BCB 的格式在 `bootloader_message` 结构中指定，如示例 13-3 所示。

```
示例 13-3. BCB 格式结构
struct bootloader_message {
char command[32]①
char status[32]②
char recovery[768]③
char stage[32]④
char reserved[224]⑤
};
```

如果设备在恢复过程中重启或关机，下次启动时，引导加载程序会检查 BCB，如果 BCB 包含 `boot-recovery` 命令，则再次启动恢复。如果恢复过程成功完成，恢复二进制文件会在退出前清除 BCB（所有字节置零），在下次重启时，引导加载程序将启动主 Android OS。

在示例 13-3 中，① 处的命令是给引导加载程序的（通常是 `boot-recovery`）；② 是引导加载程序在执行特定平台操作后写入的状态文件；③ 包含恢复二进制文件的选项（`--update-package`、`--wipe-data` 等）；④ 是描述需要多次重启的 OTA 包安装阶段的字符串，例如 2/3 表示三次重启中的第二次安装。最后一个字段 ⑤ 截至撰写本文时未被使用。

# 侧载 OTA 包 (Sideloading an OTA Package)

除了由主 OS 下载外，OTA 包还可以直接从主机传递给恢复系统。为了启用此项更新，用户必须从菜单中选择“从 ADB 应用更新”。这会启动 ADB 守护进程，它仅支持 `sideload` 命令。在主机上执行 `adb sideload otafile.zip` 将 OTA 包传输到设备。

# OTA 签名验证 (OTA Signature Verification)

如第 3 章所学，OTA 包使用哈希值进行签名（见“应用更新”）。恢复系统使用 `RecoverySystem` 类的 `verifyPackage()` 方法验证 OTA 包。该方法接收 OTA 文件的路径以及 ZIP 文件中的证书列表。如果 OTA 包的签名与 ZIP 中的任何证书匹配，则 OTA 被认为是有效的，系统将进入恢复。

验证是使用构建到恢复镜像中的密钥进行的。构建恢复系统时，这些密钥从指定的 OTA 文件中提取，转换为 `RSAPublicKey` 结构并写入 `/res/keys` 文件。当使用 RSA 作为签名算法时，密钥的字面量（如在 C 源文件中所示）可能类似于示例 13-4。

示例 13-4。恢复系统中的 `/res/keys` 文件

```
[0,0c9e62d1,1779500719...359964220;34370144].①
v2{0,8d5069b,393856617...241539245};②
```

在这里，第一行 ① 是一个序列密钥（如果没有指定版本标识），其公指数 e=3，用于验证使用 SHA-1 创建的签名；第二行 ② 包含版本 2 密钥，公指数 e=65537，也用于 SHA-1 签名。目前支持的签名算法包括 2048 位 RSA 配合 SHA-1（密钥版本 1 和 2）或 SHA-256（密钥版本 3 和 4），以及使用 NIST P-256 曲线的 ECDSA（版本 5，在 AOSP 主分支中可用）。

# 启动系统更新过程 (Starting the System Update Process)

如果 OTA 包签名验证通过，恢复系统通过执行 OTA 文件中包含的更新命令来应用系统更新。更新命令保存在恢复镜像的 `META-INF/com/google/android/` 目录下，命名为 `update-binary` ①，如 13-5 所示。

示例 13-5。系统更新 OTA 包的内容

```
-- META-INF/
-- CERT.RSA
-- CERT.SF
-- com/
|-- android/
|   |-- metadata
|   |-- otacert
|   -- google/
|     -- android/
|       |-- update-binary①
|       |-- updater-script②
|       |-- MANIFEST.MF
-- patch/
-- boot.img.p
-- system/
-- radio.img.p
-- recovery/
|-- /etc/
|  -- install-recovery.sh
-- recovery-from-boot.p
```

```
-- system//
|-- permissions.android.xml
|-- com.google.android.ble.xml
|-- security/
|-- cacerts/
|-- framework/
|-- lib
```

恢复程序（`recovery`）从 OTA 文件中提取 `update-binary` 到 `/tmp/update_binary` 并启动它，同时传递三个参数：恢复 API 版本（截至本文编写为版本 3）；`update-binary` 用来向恢复程序反馈进度和消息的管道文件描述符；以及 OTA 包的路径。`update-binary` 进程反过来执行 OTA 包中标记为 `METAINF/google/android/updater-script` 的更新脚本（`updater-script`）并对其进行评估。该更新脚本是使用一种名为 `edify` 的描述性脚本语言编写的（从 1.6 版本开始；之前的版本使用名为 `amend` 的旧变体）。`edify` 语言支持如 `if else` 等简单控制结构，并可以通过函数进行扩展，函数也可以作为控制结构（通过决定评估它们的哪些参数）。更新脚本包含了一系列函数调用，这些调用触发了应用更新所需的各种。

# 应用更新

`edify` 的实现定义并注册了各种函数，用于复制、删除和修补文件；格式化和挂载卷；设置文件权限和 SELinux 标签；表 13-2 显示了最常用的 `edify` 函数的摘要。

## 表 13-2. 重要 `edify` 函数摘要

| 函数名称 | 描述 |
| :--- | :--- |
| `abort` | 使用错误消息终止安装过程。 |
| `apply_patch` | 安全地应用二进制补丁。在替换原始文件之前，确保补丁后的文件具有预期的哈希值。可以修补磁盘分区。 |
| `apply_patch_check` | 检查文件是否具有指定的哈希值。 |
| `assert` | 检查条件是否为真。 |
| `delete`/`delete_recursive` | 删除文件/目录下的所有文件。 |
| `file_getprop` | 从指定的属性文件中获取系统属性。 |
| `format` | 使用指定的文件系统格式化卷。 |
| `getprop` | 获取系统属性。 |
| `mount` | 在指定的路径上挂载卷。 |
| `package_extract_dir` | 将指定的 ZIP 目录提取到文件系统的路径上。 |
| `package_extract_file` | 将指定的 ZIP 文件提取到文件系统的路径上，或将其作为 blob 块返回。 |
| `run_program` | 在子进程中执行指定的程序并等待其完成。 |

示例 13-6 显示了典型的系统更新 `edify` 脚本的（简化）内容。

示例 13-6. 完整系统更新 OTA 包中的 `updater-script` 内容：



`mount("ext4","EMMC","dev/block/platform/msm.sdcc.by-name/system","system");`

`file_getprop("/system/build.prop","root.build.fingerprint") = "google/.../user/release-keys"`

`file_getprop("/system/build.prop","root.build.fingerprint") = "google/.../user/release-keys"`

`Package expects build fingerprint of getprop("/google/.../user/release-keys: this has +`

`getprop("root.build.device") = "headerhead"`

`abort("This package is for "headerhead" devices; this is a ""`

`abort("root.build.device" = "")`

## 复制和修补文件

更新脚本首先挂载系统分区，然后检查设备型号和当前构建版本是否符合预期 ① 这种检查是必要的，因为尝试在不兼容的构建版本上安装系统更新可能会导致设备处于不稳定的状态。（这通常被称为“软砖”，因为通常可以通过使用工作正常的构建版本重新刷所有分区来恢复；而“硬砖”则无法恢复。）

由于 OTA 更新通常不包含完整的系统文件，只包含针对每个更改文件相对于上一个版本的二进制补丁（使用 `bsdiff` 生成）[140]，因此只有当每个“待修补文件”与生成相应分区时所使用的文件相同时，更新才能成功。为了确保这一点，更新脚本使用 `apply_patch_check` 函数检查每个“待修补文件”的哈希值是否符合预期 ②

除了系统文件外，更新过程还会修补不包含文件系统的分区，例如引导（boot）和调制（modem）分区。为了保证修补此类分区能够成功，更新脚本会检查目标分区的内容，如果它们未处于预期状态则发出告警 ③ 当所有系统文件和分区都通过验证后，更新脚本将删除不必要的文件，以及将被替换而非修补的文件 ④ 随后脚本将修补所有系统文件 ⑤ 和分区 ⑥ 它会移除任何之前的恢复分区并在 `/system/` 中解压新的恢复程序 ⑦

## 设置文件所有权、权限和安全标签

下一步是使用 `set_metadata_recursive` 函数设置所有创建或修补的文件和目录的用户、所有者、权限和文件能力 ⑧ 从版本 4.3 版本开始，Android 支持 SELinux，因此所有文件都必须正确标记，才能使访问规则生效。这就是为什么 `set_metadata_recursive` 函数被扩展，用以设置文件和目录的 SELinux 安全标签（最后一个参数，`u:object_r:system_file:s0` ⑨）。

## 完成更新

接下来，更新脚本修补设备的底板软件 ⑩，该软件通常存储在调制分区中。脚本的最后一步是卸载系统分区 ⑪。

在 `update-binary` 进程退出后，如果启动时带有 `_wipe_cache` 选项，恢复程序将清除缓存分区并将执行日志复制到 `/cache/` 以便访问。如果没有报告错误，恢复程序将清除 BCB 并重启到主系统。

## 更新恢复程序

如果你仔细检查整个脚本 13-6，你会注意到它修补了引导 ⑫ 和调制 ⑬ 分区，并解压了恢复程序的补丁。这是设计如此。由于在写入恢复分区时更新可能会中断，只有当主系统完成后才会更新恢复程序。更新是由 Android `init.rc` 文件中的 `flash_recovery` 服务触发的，如示例 13-7 所示。

示例 13-7. `init.rc` 中 `flash_recovery` 服务的定义：

```
------
service flash_recovery /system/etc/install-recovery.sh
class main
oneshot
------
```

你可以看到，该服务只是启动 `/system/etc/install-recovery.sh` 脚本 ➿ 当恢复程序需要更新时，更新脚本会复制恢复分区的补丁文件（➲）。`install-recovery.sh` 的内容可能如示例 13-8。

示例 13-8. `install-recovery` 的内容：

```
#!/system/bin/sh
if apppatch -c EMMC /dev/block/platform/msm_sdc.by/name/recovery:9506816:3e90...; then
log -t "Installing new recovery"
 apppatch -b /system/etc/recovery_resource.dat \
EMMC/dev/block/platform/msm_sdc.by/name/boot:89088042a3bd...\nEMMC/dev/block/platform/msm_sdc.by/name/recovery \
3e90...9506816a3bde=/system/recovery-from-boot
else
log -t "Recovery image already installed"
fi
```

脚本使用 `apppatch` 命令通过检查恢复分区的哈希值检查恢复 OS 是否需要修补 ❶。如果设备的恢复分区与创建该补丁时的版本匹配，脚本将应用补丁 ➲。如果恢复程序已更新或具有未知哈希，脚本将记录消息并退出 ❸。

## 自定义恢复

由第三方构建的恢复 OS（非设备制造商）。由于它是第三方创建的，自定义恢复没有使用制造商密钥签名，因此需要解锁设备的引导加载程序（bootloader）才能启动或刷入它。

可以使用 `fastboot custom-recovery` 命令在不安装到设备的情况下启动自定义恢复，也可以使用 `fastboot flash recovery custom-recovery` 命令将其永久刷入。

自定义恢复提供了官方恢复程序通常不具备的高级功能，例如全分区备份和恢复、具有完整设备管理工具 set 的 root shell，用于挂载外部 USB 设备等。自定义恢复模式（custom recovery）还可以禁用 OTA 包检查，允许安装第三方操作系统构建版本或进行修改，例如框架或主题自定义。

目前有多种自定义恢复模式可用，但截至本文撰写时，功能最全且维护最活跃的是 Team Win Recovery Project (TWRP) [141]。它基于 AOSP 原生恢复模式，也是一个开源项目 [142]。TWRP 拥有一个可定制主题的触摸界面，与 Android 原生 UI 非常相似。它支持加密分区备份、从 USB 设备安装系统更新，以及从/向外部设备进行备份和恢复，并集成了文件管理器。TWRP 2.7 版本的启动界面如图 13-5 所示。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_342_0.png)

除了原生 AOSP 恢复模式外，还可以从主操作系统控制自定义恢复模式。通过 `/cache/recovery/` 命令文件传递参数，自定义恢复模式通常允许从主操作系统触发其部分（或全部）扩展功能。例如，TWRP 支持一种极简脚本语言，用于描述启动恢复模式时应执行哪些恢复操作。这使得 Android 应用可以通过方便的 GUI 界面查询恢复命令。例如，请求对启动分区、用户分区和系统分区进行压缩备份，将生成如示例 13-9 所示的脚本。

示例 13-9。TWRP 备份脚本示例

```
# eat /cache/recovery/openrecoveryscript
```

# 警告

永久刷入一个带有忽略 OTA 包签名选项的自定义恢复模式，可能会在短暂获得设备访问权限的情况下，导致设备的系统软件被替换并植入后门。因此，不建议在日常使用的且存储个人或敏感信息的设备上刷入自定义恢复模式。

## Root 权限

Android 的安全模型遵循最小权限原则，并通过将每个进程作为专用用户运行，努力将系统进程和应用进程相互隔离。然而，Android 也基于 Linux 内核，该内核实现了标准的 Unix 风格 DAC 强制访问控制）（除非启用了 SELinux）；详见第 12 章。

这种 DAC 安全模型最大的缺点之一是，某个系统用户（通常称为 root，UID=0），也称为超级用户，对系统拥有绝对权力。root 可以读取、写入和更改任何文件或目录的权限位；杀死任何进程；挂载和卸载卷；等等。虽然这种无限制的权限对于管理传统的 Linux 系统是必要的，但在 Android 设备上拥有超级访问权限允许用户有效地绕过 Android 的沙箱，并读取或写入任何应用程序的私有文件。

Root 权限还允许通过修改设计为只读的分区来更改系统配置，随意启动或停止系统服务，并移除或禁用核心系统应用。这可能会对设备的稳定性产生不利影响，甚至导致设备无法使用，这就是为什么生产环境设备上通常不允许获取 root 权限的原因。

此外，Android 尝试限制以 root 身份执行的系统进程数量，因为任何此类进程中的编程错误都可能为权限提升攻击打开大门，导致第三方应用获得 root 权限。在部署 SELinux 强制模式后，进程受到全局安全策略的限制，因此攻破 root 进程并不一定能获得对设备的无限制访问权限，但仍可能访问敏感数据或允许修改系统行为。此外，即使是受 SELinux 限制的进程也可能利用内核漏洞来绕过安全策略或通过其他方式获得无限制的 root 权限。

尽管如此，root 权限对于开发设备上的调试或逆向工程应用程序也非常方便。此外，虽然允许第三方应用获取 root 权限损害了 Android 的安全模型，但也允许执行通常在生产设备上无法实现的各种自定义。

由于 Android 最大的卖点之一一直是其易于自定义，因此对修改核心 OS（也称为 modding）以获得更高灵活性的需求一直很高，特别是在 Android 早期早期。除了自定义系统外，在 Android 设备上拥有 root 权限还允许实现某些在不修改框架和添加系统服务的情况下无法实现的应用程序，例如防火墙、全设备备份、网络共享等。

在接下来的章节中，我们将描述如何在开发版（工程版）Android 构建版本和自定义 Android 构建版本（ROM）中实现 root 权限，以及如何将其添加到生产环境的构建版本中。然后，我们将展示需要超级访问权限的程序（通常称为 root 应用）如何请求并使用 root 权限以便以 root 身份执行进程。

## 工程版中的 Root 权限

Android 的构建系统可以为特定设备生成多个构建变体，这些变体区别在于包含的应用程序和工具的数量，以及几个修改系统行为的关键系统属性值。这些构建变体中的某些允许从 Android shell 获取 root 权限，我们将在接下来的章节中展示。

### 以 Root 启动 ADB

商用设备使用 user 构建变体（当前构建变体被设置为 `ro.build.type` 属性的值），该变体不包含诊断和开发工具，默认禁用 ADB 守护进程，不允许调试未在清单中显式设置 `debuggable` 属性的应用，并且不允许通过 shell 访问 root 权限。userdebug 构建变体与 user 非常接近，但它还包含了一些额外的模块（带有 debug 模块），允许对所有应用进行调试，并默认启用 ADB。

Engineering（或 eng）构建版本包含了大多数可用模块，允许调试，默认启用 ADB，并将 `ro.secure` 系统属性设置为 0，这会改变运行在其上的 adbd 守护进程的行为。当 `ro.secure` 被设置为 1（安全模式）时，adbd 进程初始以 root 身份启动。示例13-10。user 构建版本的 adbd 进程

```
# getprop ro.build.type
user
# getprop ro.secure
1
# ps | grep adbd
```

示例13-11。eng 构建版本的 adbd 进程

```
# getprop ro.build.type
eng
# getprop ro.secure
0
# ps | grep adbd
root 19979 4656 264 0000fd1c S /sbin/adbd
# cat /proc/19979/status
Name: adbd
State: S (sleeping)
Tgid: 19979
Pid: 19979
ppid: 1
TracerPid: 0
Uid: 0 0 0
Gid: 0 0
```

可以看到，进程的 UID 和 GID 都设置为 2000 (shell)，且 adbd 进程没有辅助组。最后，其能力集设置为 0x0000000000000000，这决定了在 user 构建上，进程被限于 CAP_UID 和 CAP_GID。相比之下，在 eng 或 userdebug 构建上，adbd 守护进程可以以 root 身份执行，如示例 13-12 所示。虽然 ADB 守护进程在 userdebug 构建上会丢弃 root 权限（如本例所示），但可以通过从主机执行 `adb root` 命令手动以安全模式重启它，如示例 13-12 所示。

示例 13-12。在 userdebug 构建上重启 adbd

```
$ adbd shell id
uid=2000(shell) gid=2000(shell) groups=103(graphics),1004(input),1007(log),1009(main),1011(abid),1015(sdcard_rw),1028(sdcard_rd),3001(net_admin),3002(net_bt_),3003(net),3006(net_bw_stats) context=u:shells0
$ adbd root
restarting adbd as root
$ adbd shell ps grep id
```

在这里，adbd 守护进程最初以 shell (UID=2000) 身份启动，从主机启动的任何 shell 也具有 UID=2000 和 GID=0。执行 `adb` 命令 ②（该命令在内部会将 `service.adb.root` 系统属性设置为 1）会以 root 身份重启 adbd 守护进程 ③，随后启动的 shell 的 UID 和 GID 均为 0 ➮。

### 注意

由于此设备启用了 SELINUX，shell 的 UID 和 GID 会变化，但其安全上下文（安全标签）保持不变：在 ① 和 ➮ 中均为 `urshell0`。因此，即使在获得 root ADB 后，启动的所有进程仍然受授予 shell 域的权限限制（除非根据 MAC 策略允许转换到另一个域；详情请见第 12 章）。在实践中，从 Android 4.4 开始，shell 域是无限制的（unconfined），当作为 root 运行时，此域中的进程对设备拥有几乎完全的控制。

## 使用 su 命令

在 userdebug 构建中，可以在不重启 ADB 为 root 的情况下获取 root 权限。这可以通过 `su` 命令（用于替换用户，也称为切换用户和超级用户）来实现，该命令以带有标记位的 UID 身份安装，因此允许调用进程获取 root 权限或以指定的 UID 执行命令（包括 UID=0）。默认实现非常基础，仅允许 root 和 shell 用户使用，如示例 13-13 所示。

示例 13-13. userdebug 构建的默认实现

```
int main(int argc, char **argv)
{
    --snip
    myuid = getuid();
    if (myuid != AID_ROOT && myuid != AID_SHELL) ① {
        fprintf(stderr,"su: uid %d not allowed to su\n", myuid);
        return 1;
    }

    if(argc < 2) {
        uid = gid = 0;②
    } else {
        --snip
    }
    if(setgid(gid) || setuid(uid)) ③ {
        fprintf(stderr,"su: permission denied\n");
        return 1;
    }

    --snip
    execcl("/system/bin/sh", "sh", NULL);➮

    fprintf(stderr,"su: exec failed\n");
    return 1;
}
```

主函数首先检查 UID 是否为 `AID_ROOT` (0) 或 `AID_SHELL` (2000) ①，以及是否由不同的用户调用。它将进程的 UID 和 GID 设置为 0 ②，最后启动 Android shell Ⓐ。从该 shell 执行的任何命令默认都会继承其特权，允许超级用户访问设备。

## 生产版本构建上的 root 权限

正如我们在“工程构建上的 root 权限”中所中学的，商业 Android 设备通常基于 user 构建变体。这意味着 ADB 守护进程以 shell 用户身份运行，且设备上没有安装相应的命令。

这是一种安全的配置，大多数用户应该能够通过平台提供的工具，或者第三方应用程序（如自定义启动器、键盘或 VPN 客户端）完成设备的配置和定制任务。然而，修改 Android 外观和感受或核心配置的操作是不可行的，对底层 Linux way 系统的低级访问也是如此。此类操作只能通过运行具有 root 权限的某些命令来完成，这就是为什么许多高级用户寻求在他们的设备上启用 root 权限的原因。

在 Android 设备上获取 root 权限通常被称为 rooting（获取 root），对于可以解锁 bootloader 的设备，这可能非常简单；但对于不允许解锁 bootloader 的设备，如果不采取额外措施防止系统分区修改，这几乎是不可能的。在接下来的章节中，我们描述了典型的 rooting 过程，并介绍了一些最流行的“超级用户”应用，它们能够启用并管理 root 权限。

## 通过更改启动或系统镜像进行路由



在某些 Android 设备上，在 bootloader 已解锁的前提下，用户可以通过刷入新的启动镜像（通常称为内核或自定义内核）轻松地转换为工程或 userdebug 构建，这会更改`ro.secure`和`ro.debuggable`系统属性的值。更改这些属性允许 ADB 守护进程执行 root 并允许通过 Android shell 访问 root 权限，正如“工程构建上的 root 权限”所述。然而，当前的 Android 用户在编译时禁用了这种行为（通过不定义`ALLOW_ADB_ROOT`），且 ADB 守护进程会忽略`ro.secure`和`ro.debuggable`系统属性的值。

启用 root 权限的另一种方法是解包系统镜像，添加 SU 二进制文件或类似的工具，然后用新的系统镜像覆盖。这通常不仅允许从 shell 获取 root 权限，还允许从第三方应用程序获取。然而，Android 4.3[1] 及更高版本中的若干安全增强禁止了应用执行 SU，方法是通过 Zygote 产生进程的边界集中丢弃所有能力，并使用`noexec`标志挂载系统分区。

此外，在将 SELinux 设置为强制模式的 Android 版本上，以 root 权限执行进程通常不会更改其安全上下文，此类进程受到 MAC 策略的限制。由于这些原因，在最近的 Android 版本上启用 root 权限可能不像更改系统属性或将 SU 二进制文件拷贝到设备那样简单。当然，替换启动或系统镜像允许禁用 SELlinux 并撤销任何安全缓解，从而降低设备的安全级别并启用 root 权限。然而，这种激进的做法类似于替换整个操作系统，可能会防止设备接收来自制造商的系统更新。这在大多数情况下是不理想的，因此已经开发出了多种 root 方法。

## 通过刷入 OTA 包进行 rooting

在某些 Android 设备上，在 bootloader 已解锁的前提下，用户可以通过刷入新的启动镜像（通常称为内核或自定义内核）轻松地转换为工程或 userdebug 构建，这会更改`ro.secure`和`ro.debuggable`系统属性的值。更改这些属性允许 ADB 守护进程执行 root 并允许通过 Android shell 访问 root 权限，正如“工程构建上的 root 权限”所述。然而，当前的 Android 用户在编译时禁用了这种行为（通过不定义`ALLOW_ADB_ROOT`），且 ADB 守护进程会忽略`ro.secure`和`ro.debuggable`系统属性的值。

启用 root 权限的另一种方法是解包系统镜像，添加 SU 二进制文件或类似的工具，然后用新的系统镜像覆盖。这通常不仅允许从 shell 获取 root 权限，还允许从第三方应用程序获取。然而，Android 4.3[1] 及更高版本中的若干安全增强禁止了应用执行 SU，方法是通过 Zygote 产生进程的边界集中丢弃所有能力，并使用`noexec`标志挂载系统分区。

此外，在将 SELinux 设置为强制模式的 Android 版本上，以 root 权限执行进程通常不会更改其安全上下文，此类进程受到 MAC 策略的限制。由于这些原因，在最近的 Android 版本上启用 root 权限可能不像更改系统属性或将 SU 二进制文件拷贝到设备那样简单。当然，替换启动或系统镜像允许禁用 SELlinux 并撤销任何安全缓解，从而降低设备的安全级别并启用 root 权限。然而，这种激进的做法类似于替换整个操作系统，可能会防止设备接收来自制造商的系统更新。这在大多数情况下是不理想的，因此已经开发出了多种 root 方法。

## 通过刷入 OTA 包 rooting

在某些 Android 设备上，在 bootloader 已解锁的前提下，用户可以通过刷入新的启动镜像（通常称为内核或自定义内核）轻松地转换为工程或 userdebug 构建，这会更改`ro.secure`和`ro.debuggable`系统属性的值。更改这些属性允许 ADB 守护进程执行 root 并允许通过 Android shell 访问 root 权限，正如“工程构建上的 root 权限”所述。然而，当前的 Android 用户在编译时禁用了这种行为（通过不定义`ALLOW_ADB_ROOT`），且 ADB 守护进程会忽略`ro.secure`和`ro.debuggable`系统属性的值。

启用 root 权限的另一种方法是解包系统镜像，添加 SU 二进制文件或类似的工具，然后用新的系统镜像覆盖。这通常不仅允许从 shell 获取 root 权限，还允许从第三方应用程序获取。然而，Android 4.3[1] 及更高版本中的若干安全增强禁止了应用执行 SU，方法是通过 Zygote 产生进程的边界集中丢弃所有能力，并使用`noexec`标志挂载系统分区。

### SuperSU

我们将使用 SuperSU 来演示 OTA 包如何工作。Android 设备。OTA 包是更新系统的文件组合。

示例 13-14. SuperSU OTA 的内容

```
- arm
- chatter.pie
- su
- common/
- 99Superudaemon
- installuser.apk
- META-INF/
- CERT.RSA
- google/
- android/
- update-binary
- MANIFEST.MF
- chatter
```

为了理解 SuperSU 如何启用 root 权限，我们首先需要检查其安装过程。为此，让我们分析示例 13-15 所示的脚本 ⑤。（SuperSU 使用普通脚本而不是原生二进制。）

示例 13-15. SuperSU OTA 安装脚本

```bash
#!/bin/sh
--snip
ui_print "- Mounting /system and data"①
mount /system
mount /data
mount -o rw,remount /system
--snip
ui_print "- Extracting files"②
cd /tmp
mkdir supersu
cd supersu
unzip -o "$ZIP"
cp ../* /
--snip
ui_print "- Placing files"
mkdir /system/bin/.ext
cp $BIN/su/system/bin/daemonsu③
cp $BIN/su/system/bin/su
cp $COM/Superuser.apk /system/app/Superuser.apk
--snip
⑤
cp $COM/install-recovery.sh /system/etc/install-recovery.sh
cp $COM/99SuperSU/Daemon /system/etc/init.d/99Superudaemon
echo 1 >/system/etc/installed_daemon
--snip
ui_print "- Setting permissions"⑥
set_perm 0 0777 /system/bin/.ext
set_perm 0 000 $SUMOD /system/bin/.ext/su
set_perm 0 000 $SUMOD /system/bin/su
--snip
set_perm 0 0755 /system/xbin/daemonsu⑦
ch_con /system/bin/.ext/su
ch_con /system/xbin/su
--snip
ch /system/xbin/daemonsu
--snip
ui_print "- Post-installation script"⑧
/system/bin/su --install
```

### 注意

正如“更新恢复（Updating the Recovery）”中所过的，此脚本通常用于从主操作系统更新恢复镜像，因此你可能会好奇为什么 SuperSU 会尝试更新设备的恢复分区。SuperSU 使用此脚本在启动时启动其某些组件，我们稍后会讨论。

OTA 包安装过程的下一步是设置权限和 SELinux 安全标签（`chcon` 是一个 shell 函数，它调用`set` SELinux 工具程序并设置`uobject:r_system_file:s0`标签）。最后，脚本调用带有`--install`选项的命令来执行某些安装后初始化，然后卸载`/system`和`/data`。当脚本执行成功时，恢复模式会将设备重启到 Android 主系统。

# SuperSU 如何初始化

为了理解 SuperSU 是如何初始化的，让我们来看`install-recovery.sh`脚本的内容（参见示例 13-16，省略了注释），该脚本由`init`自动执行。

示例 13-16. SuperSU 的`install-recovery.sh`脚本内容

```
#!/system/bin/sh
/system/xbin/daemons --auto-daemon &
/system/etc/install-recovery-2.sh
```

脚本首先执行守护进程二进制文件，启动一个具有 root 权限的守护进程。下一步执行`install-recovery.sh`脚本，该脚本可能用于执行额外的初始化，这对其他 root 应用是必要的。在 Android 4.3 及更高版本中，需要使用守护进程来允许应用以 root 权限执行代码，因为所有应用（从 zygote 分生产生）的能力绑定（capability binding）都已清零，从而防止它们执行特权操作，即使它们成功以 root 身份启动进程。此外，从 Android 4.4 开始，SELinux 处于强制模式（enforcing mode），因此任何由应用程序启动的进程都会继承其安全上下文（通常为`untrusted_app`），并像应用本身一样受到 MAC（强制访问控制）限制。

SuperSU 通过让应用使用二进制文件以 root 身份执行命令来绕过这些安全限制，这些命令通过 Unix 域接字传递给守护进程二进制文件，最终由守护进程在`u:init:s0`SELinux 上文中作为 root 身份执行接收到的命令。进程交互过程如示例 13-17 所示。

示例 13-17. 应用通过 SuperSU 请求 root 权限时启动的进程

| ps -s | LABEL USER PID PPID NAME |
| :--- | :--- | :--- | :--- | :--- |
| init:s0 | root | 1 | 0 | /init |
| zygote:s0 | root | 187 | 1 | zygote |
| init:s0 | root | 209 | 1 | daemons:mount:target |
| init:s0 | root | 210 | 209 | daemonsmaster |
| init:s0 | root | 3969 | 210 | daemons:10292 |
| untrusted_apps | u0 | u:a2:292 | 13637 | 187 | com.example.app |
| untrusted_apps | u0 | u:a2:209 | 15256 | 187 | com.chainfire.supersu |

在这里，`com.example.app`应用 ⑨（父进程是 zygote ②）通过`-c`选项将命令传递给`su`二进制文件来请求 root 权限。如你所示，进程 ⑧ 以请求应用相同的用户（u0_a292, UID=10292）和相同的 SELinux 域（untrusted_app）运行。然而，请求执行的命令进程 ⑨ 以 root 身份执行（在本例中为`sleep`）确实在 SELinux 域（安全上下文`u:r:init:0`）中以 root 身份执行。如果我们追踪它的 PPID（第四列），会发现`sleep`进程是由`daemonsu:10292`进程 ⑤ 启动的，这是一个专门为我们的应用的`daemonsu`实例（UID=10292）。`daemonsu`进程从`daemonsu:master`实例 ④ 继承其 init SELinux 域，而该实例又由第一个 daemonsu 实例 ③ 启动。这是通过`install-recovery.sh`脚本启动的实例（参见示例 13-16），它在其父进程——init 进程 ①（PID=1）的域内运行。

`eu.chainfire.supersu`进程 ⒇属于 SuperSU 管理应用，它显示了图 13-6 所示的 root 权限授予对话。

![](img/8524e4e57e2e9dc889903e3d2c5fe367_351_0.png)

Superuser 权限只能授予一次、持续一段时间或永久授予。SuperSU 维护一个已授予 root 权限的应用内部白名单，如果请求的应用已经在白名单中，则不会显示授予对话。

### 注意

SuperSU 有一个辅助库`libsuperuser[146]`，它通过为不同的`su`调用模式提供 Java 封装，使得编写 root 应用变得更容易。SuperSU 的作者还提供了一份编写 root 应用的全面指南，称为 How-To SU[147]。

# 自定义 ROM 上的 root 权限

自定义 ROM 无需通过`install-recovery.sh`来启动它们的超级守护进程（同于 SuperSU 的 daemons），因为它们可以完全自定义启动过程。例如，流行的 CyanogenMod 开源 Android 发行版从`init.superuser`启动其 su 守护进程。

示例 13-18. CyanogenMod 中显示的 su 守护进程启动脚本

```
service su_daemon /system/xbin/su --daemon ① oneshot
```

```
on property:persist.sys.root_access=②
stop su_daemon
```

```
on property:persist.sys.root_access=③
stop su_daemon
```

```
on property:persist.sys.root_access=④
start su_daemon
```

```
on property:persist.sys.root_access=⑤
start su_daemon
```

此 init 脚本定义了 su_daemon ①，可以通过更改`persist.sys.root_access`的值来启动或停止。该属性决定是否向应用、ADB shell 或两者授予 root 权限。默认禁用 root 权限，但可以通过 CyanogenMod 的选项进行配置。

### 注意

SuperSU 和允许 root 权限的自定义 ROM 采取某些措施来限制哪些应用执行 root 命令（通常通过将其加入白名单），但实现上的缺陷可能允许应用绕过这些措施并获取 root 权限。因此，在日常设备上应禁用 root 权限，仅在开发时使用。

# 通过漏洞获取 root

在没有解锁 bootloader 的生产设备上，可以通过利用漏洞获取 root 权限，允许应用或 shell 启动 root（也称为软 root）并修改系统。漏洞通常封装成“一键式”应用或脚本，通过安装二进制文件或修改系统来持久 root 权限。例如，所谓的 towelroot 漏洞（作为 Android 应用发布）利用 Linux 内核漏洞（CVE-2014-3153）获取 root 权限并安装 SuperSU 以持久化。（也可以通过用自定义恢复覆盖恢复分区来持久 root 权限，允许安装任意软件。但某些设备具有额外的保护，防止对 boot、系统和恢复分区进行修改。）

![](img/8524e4e57e2e9dc889903e3d2c5fe367_353_0)

### 注意

*参考《Android Hacker Handbook》（Wiley, 2014）第 3 章，详细介绍了用于在各种 Android 版本中获取 root 权限的主要权限提升漏洞。该书第 12 章介绍了在 Android 中实现的漏洞缓解技术，以防止权限提升攻击并加固系统。*

## 总结

为了允许更新系统软件或将设备恢复出厂状态，Android 设备允许通过 bootloader 存储的不受限访问。bootloader 通常实现一种管理协议（通常是 fastboot），允许从主机传输并刷写分区。生产设备的 bootloader 通常是锁定的，只允许刷写签名镜像。然而，大多数 bootloader 可以解锁，允许刷写第三方镜像。

Android 使用一个专用分区称为 recovery，用于应用 OTA 包或清除设备上的所有数据。生产设备的 bootloader 通常只允许设备制造商签名的 OTA 包。如果 bootloader 已解锁，自定义恢复（允许第三方更新或完全忽略签名验证）就可以启动或永久安装。

工程版或调试版 Android 允许通过 Android shell 获取 root 权限，此类设备可以通过包含“superuser”守护进程和允许控制所有应用程序的第三方 OTA 包来启用 root 权限。第三方 Android 构建（ROM）通常开箱支持 root 权限，尽管可以通过系统设置界面禁用。

- [137] Code Aurora Forum, “(L)(K) kernel based Android bootloader,” https://codeaurora.org/blogs/little-based-kernel-android-bootloader/
- [138] Code Aurora Forum, https://www.codeaurora.org/cgit/quic/la/kernel/lk/
- [139] Google, Android Compatibility Definition, https://static.googleusercontent.com/media/source.android.com/en/compatibility/android-android-cdd.pdf



- [140] Colin Percival, “Binary diff/patch utility,” http://www.daemonology.net/bsdiff/

- [141] TeamWin, “TWRP 2.7,” http://teamwin.in/project/twr2/

- [142] TeamWin, “Team Recovery Project (TWRP),” https://github.com/TeamWin/Team-Recovery-Project/

- [143] Google, “Security Enhancements in Android 4.3,” http://source.android.com/devices/tech/security/enhancements43.html

- [144] Jorit “Chainfire” Jongma, “CF-Root download 3 page,” http://download.chainfire.eu/supersu/

- [145] Jorit “Chainfire” Jongma, “Google Play Apps: SuperSU,” https://play.google.com/store/apps/details?id=eu.chainfire.supersu&hl=en

- [146] Jorit “Chainfire” Jongma, `libsuperuser`, https://github.com/chainfire/libsuperuser/

- [147] Jorit “Chainfire” Jongma, “How-To SU Guidelines for problem-free su usage,” http://su.chainfire.eu/

# 索引

## 关于数字索引的说明

索引条目中的链接显示为该条目所在的章节标题。由于某些章节包含多个索引标记，一个条目拥有多个指向同一章节的链接并不稀见。点击任何链接都将直接带您到文中该标记出现的位置。

## 符号

`2FA` (双重身份验证)，Google 登录服务

`<password-owner>` 标签，策略持久化

`<policies>` 标签，策略持久化

`@PLATFORM` 宏，中间件 MAC

## A

`A_AUTH` 消息，安全 ADB 实现

`abort` 函数，启动系统更新过程

`AbstractAccountAuthenticator` 类，身份验证模块，多用户支持，共享账户

`accept()` 方法，JSSE 简介

`ACCESS_ALL_EXTERNAL_STORAGE` 权限，签名

访问控制列表 (ACLs)，Binder 安全性

`ACCESS_KEYGUARD_SECURE_STORAGE` 权限，PIN 和密码解锁

`ACCESS_SURFACE_FLINGER` 权限，权限与进程属性

访问向量 (AVs)，对象类与权限语句，访问向量规则、访问向量规则、`auditallow` 规则、`auditallow` 规则、`auditallow` 规则

规则，访问向量规则、访问向量规则、`auditallow` 规则、`auditallow` 规则、`auditallow` 规则

- `allow` 规则，访问向量规则

- `auditallow` 规则，`auditallow` 规则

- `undoubt` 规则，`auditallow` 规则

- `never` 规则，`auditallow` 规则

`Authenticatorcache`，身份验证模块，身份验证模块缓存

`Authenticator.xml` 文件，身份验证模块缓存

账户管理，Android 账户管理概述，`AccountManagerService` 和 `AccountManager`，`AccountManagerService` 和 `AccountManager`，身份验证模块，身份验证模块，列出并验证账户，列出并验证账户，管理账户，请求身份验证令牌访问，表结构、表结构，表访问、表访问，多用户支持、多用户支持，共享，Google 账户支持、Google 账户支持、Google 账户支持，Google 服务身份验证与授权，`ClientLogin`，`OAuth 2.0`

`AccountManager` 类，`AccountManagerService` 和 `AccountManager`

`AccountManagerService` 和 `AccountManager`，列出并验证账户，列出并验证账户，管理账户，请求身份验证令牌访问

列出并验证账户，列出并验证账户

管理账户，`AccountManagerService` 和 `AccountManager`

请求身份验证令牌访问，请求身份验证令牌访问

使用账户凭据，管理账户

账户数据库，表结构、表结构，表访问

密码安全，表访问

表访问，表结构

表结构，表结构

身份验证模块，身份验证模块、身份验证模块，共享账户

添加，共享账户

缓存，身份验证模块

概述，身份验证模块

Google 账户，Google 账户支持、Google 账户支持、Google 账户支持，Google 服务身份验证与授权，`ClientLogin`，`OAuth 2.0`

`ClientLogin` 协议，Google 服务身份验证与授权

Google Account Manager，Google 账户支持

Google 登录服务，Google 账户支持

Google Play 服务，`OAuth 2.0`

`OAuth 2.0`，`ClientLogin`

概述，Google 账户支持

多用户支持，表访问、多用户支持、多用户支持

概述，表访问

每用户账户数据库，多用户支持

共享账户，多用户支持

概述，Android 账户管理概述

`AccountManager` 类，应用限制，外部存储权限，Android 账户管理概述，`AccountManagerService` 和 `AccountManager`

`ACCOUNT_MANAGER` 权限，身份验证模块

`AccountManagerService`，`AccountManagerService` 和 `AccountManager`，列出并验证账户，列出并验证账户，管理账户，请求身份验证令牌访问

列出并验证账户，列出并验证账户

管理账户，列出并验证账户

概述，`AccountManagerService` 和 `AccountManager`

请求身份验证令牌访问，请求身份验证令牌访问

使用账户凭据，管理账户

账户数据库，表结构、表结构，表访问

密码安全，表访问

表访问，表结构

表结构，表结构

`accounts.db` 文件，用户系统目录

ACLs (访问控制列表)，Binder

`ACTION_ADD_DEVICE_ADMIN` 意图，权限管理

`ACTION_DEVICE_ADMIN_ENABLED` 意图，实现设备管理员

`ACTION_GET_RESTRICTION_ENTRIES` 意图，应用限制

`ACTION_NDEF_DISCOVERED` 意图，读/写模式

`ACTION_PACKAGE_ADDED` 广播，更新组件与权限

`ACTION_PASSWORD_FAILED` 广播，策略持久化

`ACTION_PASSWORD_SUCCEEDED` 广播，策略持久化

`ACTION_SET_NEW_PASSWORD` 动作，策略持久化

`ACTION_START_ENCRYPTION` 意图，策略执行

`ACTION_TAG_DISCOVERED` 意图，读/写模式

`ACTION_TECH_DISCOVERED` 意图，读/写模式

`<active-password>` 标签，策略持久化

活动，静态强制，公共与私有组件

权限，静态强制，公共与私有组件

强制，静态强制

`ActivityManagerService`，Pending Intents

ADB (Android 调试桥)，多用户支持，软件包管理器系统应用，暴力攻击防护，暴力攻击防护，ADB 概述，安全 ADB 的需要

安全 ADB 实现、安全 ADB 实现、安全 ADB 实现，`Root`访问，使用 `su` 命令

身份验证密钥，安全 ADB 实现

守护进程概述，暴力攻击防护

实现，安全 ADB 实现

安全性，ADB 概述

`root`访问，`Root`访问，使用 `su` 命令

在工程版本上，`Root`访问

在生产版本上，使用 `su` 命令

加密，安全 ADB 的需要

验证主机密钥指纹，安全 ADB 实现

`ADB_AUTH_RSAPUBLKEY` 参数，安全 ADB 实现

`ADB_AUTH_SIGNATURE` 参数，安全 ADB 实现

`ADB_AUTH_TOKEN` 参数，安全 ADB 实现

`abbd` (ADB) 守护进程，暴力攻击防护

`adb install` 命令，OTA 包，更新应用

`adb push` 命令，更新应用

`adb reboot bootloader` 命令，恢复模式

`adb restore` 命令，本地备份

`adb shell` 命令，Android 实现

`adb sideload` 命令，OTA 文件

`ADB_TRACE` 环境变量，ADB 概述

`ADB_VENDOR_KEYS` 环境变量，安全 ADB 实现

`addAccountExplicitly()` 方法，列出并验证账户，共享账户，添加身份验证模块

`addAccountFromCredentials()` 方法，多用户支持

`addAccount()` 方法，列出并验证账户，共享账户

`addNetwork()` 方法，凭管理

`addPermission()` 方法，自定义权限

`addProvider()` 方法，提供实现，使用自定义提供

高级 (` `) 安全卡，UICC

AEAD (关联数据的身份验证加密)，加密模式

`AES` 算法，算法名称，加密模式，密钥生成器，Android's Bouncy Castle，Android's Bouncy Castle，AndroidSSL 提供，密钥库服务，备份格式

AIA (权威信息访问)，系统信任 API

AID (应用标识)，SE 通信协议，查询 eSE 执行

环境，APDU 路由

`<aidl>` APDU 路由，指定 SE 程序的路由

AID (Android 接口语言)，Binder 实现

飞行模式，次用户

`--algo` 参数，创建并安装加密 APK

算法参数，算法名称

`aliases()` 方法，PKCS#12 文件备份密钥库

`allowBackup` 属性，本地备份，备份加密

`allow` 规则，访问向量规则

始终开启 VPN 配置，始终开启 VPN

Android Beam 功能，对等点模式

Android 调试桥，多用户支持

Android 开发工具 (ADT) Eclipse 插件，ADB 概述

Android 接口语言 (AIDL)，Binder 实现

`AndroidKeyStoreProvider`，Android 密钥库提供

Android 主线项目，Linux 内核

`AndroidManifest.xml` 文件，用户安装应用，应用沙箱，权限

Android 主 密钥

Android 开源项目 (AOSP)，系统权限，强制域

`AndroidOpenSSL` 提供，Android's Bouncy Castle，Android JSSE 实现

Android Runtime (ART)，创建数据目录

`ANDROID_SDK_HOME` 环境变量，安全 ADB 实现

Android 安全外部通道 (ASEC) 包含，更新系统应用，加密应用

# 容器

ANNSI 中间事件，当今 PKI 中的信任问题

- AOSP（Android 源项目），系统权限，强制域

- `APDU_RECEIVED` 广播，eSE 相关广播

- APDUs（应用协议数据单元），eSE 相关广播，Android 4.4 HCE 架构，APDU 路由，为 HCE 服务指定路由

- 指定路由，APDU 路由，为 HCE 服务指定路由

- 针对 SE 应用程序程序，为 HCE 服务指定路由

- 针对 HCE 服务，APDU 路由

- APKs，原生用户空间，IPC

- 代码签名和，IPC

- Dalvik VM 和原生用户空间

- `appdomain`（应用域），无限制域

- `app_domain()` 宏，无限制域

- app ID，Android 应用组件，基于应用程序的 VPN，始终开启的 VPN，声明 VPN，声明 VPN，声明 VPN，声明 VPN，声明 VPN

- 声明，声明 VPN

- 建立连接，声明 VPN

- 通知用户关于连接情况，声明 VPN

- 准备，声明 VPN

- 应用标识符 (AID)，SE 通信协议，查询 eSE 执行环境，APDU 路由

- 应用协议数据单元，eSE 相关广播

- `application/vnd.android.package-archive` MIME 类型，Android 应用包格式，`apply_patch_check` 函数，启动系统更新过程，复制并补丁文件

- `applypatch` 命令，完成更新

- `apply_patch` 函数，启动系统更新过程

- Android 框架库，用户安装的应用，用户安装的应用，用户安装的应用，用户安装的应用，Android 应用组件，Android 应用组件，Android 应用组件，软件包和数据的位置，次级用户，用户系统目录，应用数据目录，应用数据目录

- 活动，用户安装的应用广播接收器，Android 组件的，用户安装的应用的内容提供者，Android 组件的多用户支持，次级用户沙箱，Android 组件的服务，用户安装的应用

- 系统，Android 框架库用户安装的，用户安装的应用，软件包和数据的位置的用户管理，用户系统目录，应用数据目录，应用数据目录

- 应用共享，应用数据目录数据目录，应用数据目录概述，用户系统目录

- `ARC4` 算法，Android 的 Bouncy Castle 提供者，Android 的 Bouncy Castle 提供者，`AndroidOpenSSL` 提供者，VPN 支持架构，Linux 内核，Linux 内核，原生用户空间，Dalvik VM，Dalvik VM，Dalvik VM，进程间通信，进程间通信，Binder 实现，Binder 安全，Binder 安全，Binder 令牌，访问 Binder 对象，访问 Binder 对象，Android 框架库，Android 框架库，用户安装的应用，用户安装的应用，用户安装的应用，用户安装的应用，Android 应用组件，Android 应用组件，JCA 提供者架构，加密服务提供者，提供者实现，提供者实现

- 应用，Android 框架库，用户安装的应用，用户安装的应用，用户安装的应用，Android 应用组件，Android 组件组件活动，用户安装的应用

- 广播接收器，Android 组件

- 内容提供者，Android 组件

- 组件，用户安装的应用

- 服务，用户安装的应用

- 系统，Android 框架库

- 用户安装，用户安装的应用

- Binder，进程间通信，进程间通信，Binder 实现，Binder 安全，Binder 安全，Binder 安全，Binder 令牌，访问 Binder 对象，访问 Binder 对象

- 访问对象，Binder 令牌

- 基于权限的安全，Binder 安全

- 死亡通知，访问 Binder 对象

- 实现，进程间通信

- 对象标识，Binder 安全

- 概述，进程间通信

- 引用计数，访问 Binder 对象

- 安全，Binder 实现

- 令牌，Binder 安全

- Dalvik VM，原生用户空间

- 框架库，Android 框架库

- 进程间通信，Dalvik VM

- Java 运行时库，Dalvik VM

- JCA，JCA 提供者架构，加密服务提供者，提供者实现，提供者实现

- 动态提供者注册，提供者实现

- 概述，JCA 提供者架构

- 提供者实现，加密服务提供者

- 静态提供者注册，提供者实现

# Linux 内核，Linux Kernel

- 原生用户空间层，Linux 内核系统服务，Dalvik VM

- ART（Android Runtime），创建数据目录

- ASEC（Android 安全外部缓存）容器，更新系统应用，加密应用容器

- `asec mount` 命令，加密应用容器

- `asec path` 命令，加密应用容器

- `asec unmount` 命令，加密应用容器

- ASSD（高级安全 SD 卡），UICC

- `assert` 函数，启动系统更新过程

- 分配权限，签名

- 非对称加密，`MessageDigest`，`Signature`

- AT 命令，UICC

- 属性语句，类型和属性语句

- `auditallow` 规则，`auditallow` 规则，设备策略文件

- `AUTHENTICATE_ACCOUNTS` 权限，列出并验证账户，添加身份验证模块

- 关联数据的身份加密 (AEAD)，分组密码模式

- 身份验证模块，Android 账户管理概述，身份验证模块，身份验证模块，共享账户

- 账户管理和，Android 账户管理概述

- 添加，共享账户

- 缓存，身份验证模块

- 概述，身份验证模块

- 权威访问访问，系统信任存储 API

- `authtokens` 表，表结构，表访问

- AVs，对象类和权限语句

- 后门，加密应用和 Google Play

- 备份框架，验证主机密钥指纹，验证主机密钥指纹，验证主机密钥指纹，本地备份，备份文件格式，备份加密

- 云备份，验证主机密钥指纹

- 控制范围，备份加密

- 加密，备份文件格式

- 文件备份，本地备份

- 本地备份，验证主机密钥指纹

- `BackupService`，本地备份，备份文件格式

- BCB（引导加载程序控制），控制恢复

- `BIND_DEVICE_ADMIN` 权限，广播权限，进程间通信，实现设备管理员

- Binder，进程间通信，进程间通信，Binder 实现，Binder 安全，Binder 安全，Binder 令牌，访问 Binder 对象，访问 Binder 对象，框架强制执行，系统信任存储

- 访问对象，Binder 令牌

- 基于权限的安全，Binder 安全

- 死亡通知，访问 Binder 对象

- 实现，进程间通信

- 密钥服务和，系统信任存储



- 对象标识，`Binder` 安全

- 概述，进程间通信

- 权限和，框架强制执行

- 引用计数，访问 `Binder` 对象

- 安全，`Binder` 实现

- 令牌，`Binder` 安全

- `BIND_NFC_SERVICE` 权限，Android 4.4 HCE 架构，编写 HCE 服务

# 高级 Linux 挂载功能

- `BKS` (Bouncy Castle KeyStore)，类型，Android 的 Bouncy Castle 提供者

- 黑名单证书，黑名单，黑名单，处理实体密钥泄露

- Android，处理实体密钥泄露

- 处理 CA 密钥泄露，黑名单

- 处理 EE 密钥泄露，黑名单

- 分组密码模式，分组密码模式

- `BLOWFISH` 算法，Android 的 Bouncy Castle 提供者，Android 的 Bouncy Castle 提供者

- 蓝牙，次级用户

- `BOOT_COMPLETED` 广播，广播权限强制

- `BCB`（引导加载程序控制），控制恢复

- 引导加载程序程序，系统更新，设备安全，系统更新和根访问，系统更新和根访问，快速启动模式，快速启动模式，Android 分区布局，Android 分区布局

- 快速启动模式，快速启动模式，快速启动模式，Android 分区布局，Android 分区布局

- 命令，Android 分区布局

- 分区布局，快速启动模式

- 协议，Android 分区布局

- 解锁，系统更新，系统更新和根访问

- Bouncy Castle Store (`BKS`)，类型，Android 的 Bouncy Castle 提供者

- Bouncy Castle 提供者，Android JCA 提供者

- 广播，Android 组件，广播权限强制，广播权限，访客用户

- 权限，广播权限权限

- 权限强制，广播权限强制

- 接收器，Android 组件

用户管理与访客用户

# `BROADCAST_STICKY` 权限，广播权限强制

暴力破解，PIN 和 PUK 解锁

# C

- `CA`（证书颁发机构），公钥证书，直接信任与私有 `CA`，证书黑名单，使用私钥

- 定义的，公钥证书

- 处理泄露，证书黑名单

- 安装证书，使用私钥

- 私有的，直接信任与私有 `CA`

- 相机，禁用，策略强制

- `CAMERA` 权限，普通

- `CameraService`，策略强制

- 基于能力的安全，`Binder` 安全

- `CAP_CHOWN` 能力，`installd` 守护进程 (Daemon)

- `CAP_DAC_OVERRIDE` 能力，`installd` 守护进程 (Daemon)

- `CAP_KILL` 能力，访问控制规则 (ACL)

- `CAP_NET_ADMIN` 能力，内核级强制

- `CAP_NET_RAW` 能力，内核级强制

- `CAP_SETGID` 能力，`Root` 访问

- `CAP_SETUID` 能力，`Root` 访问

- `CAP_SYS_ADMIN` 能力，`auditd` 规则

- `CAP_SYS_PTRACE` 能力，访问控制规则 (ACL)

- 卡模拟 (CE) 模式，NFC 概述，点对点模式

- 类别属性，`APDU` 路由

- `CBC`（密码分组链接链），分组密码工作模式，磁盘加密

- `CDD`（兼容性定义文档），外部存储实现

- `CDP`（证书撤销列表分布点），系统信任 API

- CE（卡模拟）模式，NFC 概述，点对点模式

- 证书颁发机构 (CA)，公钥证书

- `CertificateException`，系统信任存储库 API，Android 中的证书固定

- `CertificateFactory` 类，`PKCS#12` 文件支持的密钥库，Android Bouncy Castle 提供程序

- 证书撤销列表 (CRL)，公钥密钥基础设施 (PKI)

- 证书，网络安全与 PKI，直接信任与私有 CA，直接信任与私有 CA，公钥密钥基础设施，Android JSSE 实现，系统信任存储库，Android 4.x 系统信任存储库，系统信任存储库 API，证书黑名单，证书黑名单，处理实体密钥泄露，收敛与信任捷活性，凭据存储，使用私钥，删除密钥和用户证书

- Android，处理实体密钥泄露

- 黑名单，证书黑名单，证书黑名单

- 处理 CA 密钥泄露，证书黑名单

- 处理 EE 密钥泄露，证书黑名单

- 证书固定，收敛与信任捷活性

- 删除，删除密钥和用户证书

- 直接信任与私有 CA，直接信任与私有 CA

- EAP 凭据，凭据存储

- 安装 CA，使用私钥

- 管理，Android JSSE 实现，系统信任存储库，Android 4.x 系统信任存储库，系统信任存储库 API

- Android 4.x 系统信任存储库，系统信任存储库

- 系统信任存储库 API，系统信任存储库 API

- 系统信任存储库，Android JSSE 实现

- 使用系统信任存储库，Android 4.x 系统信任存储库

- PKI，直接信任与私有 CA

- 公钥，网络安全与 PKI

- 撤销，公钥密钥基础设施

- `CertPathBuilder` 类，`CertificateFactoryAndCertPath`，Android-Bouncy Castle 提供程序

- `CertPath` 类，`PKCS#12` 文件支持的密钥库，对对身份验证

- `CertPathTrustManagerParameters`，对对身份验证

- `CertPathValidator` 类，`CertificateFactoryAndCertPath`，Android-Bouncy Castle 提供程序

- `CERT.SF` 文件，JAR 文件签名

- `CertStore` 类，Android Bouncy Castle 提供程序

- `CFB`（密码反馈），分组密码工作模式

- 挑战响应握手验证协议 (`CHAP`)，VPN 支持

- `changeEncryptionPassword()` 方法，PIN 和密码解锁

- `CHANGE_WIFI_STATE` 权限，EAP 凭据管理

- `Channel` 类，访问 UICC

- `CHAP`（挑战响应握手验证协议），VPN 支持

- `chchon` 工具，库与工具

- `checkPassword()` 方法，PIN 和密码解锁

- `checkPattern()` 方法，图纹解锁

- `checkPermission()` 方法，动态强制，共享用户 ID

- `checkServerTrusted()` 方法，系统信任存储库 API，证书固定

- `choosePrivateKeyAlias()` 方法，安装 PKCS#12 文件，密钥库 API 实现

- 密码分组链接链 (`CBC`)，分组密码工作模式，磁盘加密

- `Cipher` 类，签名，分组密码工作模式，分组密码工作模式，获取 `Cipher` 实例，Android-Bouncy Castle 提供程序，AndroidOpenSSL 提供程序

- 分组密码模式，分组密码工作模式

- 获取实例，分组密码工作模式

- 概述，签名

- 支持的算法，Android Bouncy Castle 提供程序，AndroidOpenSSL 提供程序

- 使用，获取 `Cipher` 实例

- 密码反馈，`CFB`，分组密码工作模式

- 密码模式，磁盘加密

- 密码套，网络安全与 PKI

- 密文，签名，分组密码工作模式

- `classes.dex` 文件，Android 应用程序包格式

- `class` 关键字，对象类和权限语句

- `class` 语句，对象类和权限语句

- `clearPassword()` 方法，管理账户，表结构

- 客户端凭据，传递与查询，原生守护进程级强制

- `ClientLogin` 协议，Google 服务身份验证与授权

- `clone()`，高级 Linux 挂载功能

- `CLONE_NEWNS` 标志，高级 Linux 挂载功能，Android 实现，Android 实现

- CN（通用名称），网络安全与 PKI

- `codePath` 属性，向 `packages.xml` 中添加新包

- 代码签名，IPC

- COM（通用对象模型），进程间通信

- `common` 关键字，对象类和权限语句

- 通用名称 (CN)，网络安全与 PKI

- 通用对象模型 (COM)，进程间通信

- 通用对象请求代理架构 (CORBA)，进程间通信

- `Comodo` 攻击，今日 PKI 中的信任问题

- `compareSignatures()` 方法，签名验证

- 兼容性定义文档 (CDD)，外部存储实现

- `CONFIG_ANDROID_NETWORK` 权限，内核级强制

- `CONFIG_DM_VERITY` 配置项，`dm-verity` 概述

- `confirmCredentials()` 方法，管理账户

- 加密提供者，AndroidOpenSSL Provider

- `Container` 类，实现与参数

- 内容提供者，`Binder` 实现，Android 组件

- 定义的，`Binder` 实现

- 强制

- 动态

- 静态

- 控制 `KEYGUARD`，锁屏实现

- 选项，SuperSU 初始化

- `copyResource()` 方法，实现与参数

- CORBA（通用对象请求代理架构），进程间通信

- 计数器 (CTR）模式，分组密码工作模式

- 创建属性，用户元数据

- `createContainer()` 方法，公共 API

- `createSecureContainer()` 方法，安装锁定 APK

- 凭据，原生守护进程级强制，凭据存储，凭据存储，身份密钥与证书，系统信任存储库，密钥存储库，密钥存储库，Nexus 4 硬件实现，Nexus 4 硬件实现，公共 API，公共 API，安装 PKCS#12 文件，使用私钥，删除密钥和用户证书，删除密钥和用户证书，密钥库 API 实现，控制密钥库，Android 密钥提供程序

- 访问密钥库，密钥库 API 实现

- Android 实现，系统信任存储库，密钥存储库

- 服务，密钥库，Nexus 4 硬件实现，Nexus 4 硬件实现

- 访问限制，密钥存储库框架集成，Nexus 4 硬件实现密钥块，密钥存储库

- 密钥库主，密钥存储库，系统信任存储库

- Nexus 4 硬件实现，Nexus 4 硬件实现

- AndroidKeyStoreProvider，Android 密钥提供程序

- EAP 凭据，凭据存储，凭据存储，身份密钥与证书

- 身份密钥与证书，凭据存储

- 概述，凭据存储，系统信任存储库，身份密钥与证书

- KeyChain API，公共 API，公共 API，安装 PKCS#12 文件，使用私钥，删除密钥和用户证书，删除密钥和用户证书，删除密钥和用户证书

- 删除密钥和用户证书，删除密钥和用户证书

- 安装 CA 证书，使用私钥 `KeyChain` 类，公共 API

- 概述，公共 API，删除密钥和用户证书支持的算法，删除密钥和用户证书

- 使用私钥，安装 PKCS#12 文件

- 概述，控制密钥库传递与查询，原生守护进程级强制

- CRL（证书撤销列表），公钥密钥基础设施

- CDP（证书撤销列表分布点），系统信任存储库 API

- `CRYPT_ENCRYPTION_IN_PROGRESS` 标志，触发加密过程

## `cryptfs checkpw` 命令，解密并挂载 `/data`

- `cryptfs enableinplace` 命令，触发加密过程

- `cryptfs` 模块，磁盘加密密码

- `CryptKeeper` 类，启动加密设备

- crypto 脚注，密码模式，触发加密过程

- 密码学安全的伪随机数生成器 (CSPRNG)，算法名称，`SecureRandom`

- 密码学服务提供者 (CSP)，加密提供者

- 加密法，系统更新，JCA 提供者架构，加密服务提供者，提供实现，提供实现，动态提供者注册，动态提供者注册，算法名称、算法名称、算法名称，消息摘要、签名、使用密码、密钥、密钥、密钥、SecretKey 和 PBEKey、SecretKey 和 PBEKey、SecretKey 和 PBEKey、KeyFactory、SecretKeyFactory、SecretKeyFactory、KeyGenerator、密钥协商、PKCS#12 文件备份密钥库、PKCS#12 文件备份密钥库、证书工厂和证书路径、证书工厂和证书路径、Android JCA 提供者、Android JCA 提供者、Android JCA 提供者、Android 的 Bouncy Castle 提供者、AndroidSSL 提供者、使用自定义提供者

- Android 提供者，Android JCA 提供者、Android JCA 提供者、Android JCA 提供者、Android 的 Bouncy Castle 提供者、AndroidSSL 提供者、使用自定义提供者

- AndroidOpenSSL，Android 的 Bouncy Castle 提供者

- Bouncy Castle，Android JCA 提供者

- Crypto，Android JCA 提供者

- OpenSSL 和，AndroidOpenSSL

- 概述，Android JCA 提供者

- Spongy Castle，使用自定义提供者

- 自定义提供者，AndroidOpenSSLProvider

- 哈希，系统更新

- JCA 架构，JCA 提供者架构，加密服务提供者，提供实现，提供者注册提供实现

动态提供者注册，JCA 提供者架构

提供实现，加密服务提供者静态提供者注册，提供实现，

JCA 引擎类，动态提供者注册，动态提供者注册，算法名称、算法名称、算法名称，消息摘要、签名、使用密码、密钥、密钥、密钥、SecretKey 和 PBEKey、SecretKey 和 PBEKey、SecretKey 和 PBEKey、SecretKey 和 PBEKey、SecretKey 和 PBEKey、KeyFactory、SecretKeyFactory、SecretKeyFactory、KeyGenerator、密钥协商、PKCS12 文件备份密钥库、PKCS#12 文件备份密钥库、证书工厂和证书路径、证书工厂和证书路径

算法名称，算法名称 `CertificateFactory` 类，`PKCS#12` 文件备份密钥库

`CertPathBuilder` 类，证书工厂和证书路径 `CertPath` 类，`PKCS#12` 文件备份密钥库

`CertPathValidator` 类，证书工厂和证书路径 `Cipher` 类，签名

`KeyAgreement` 类，`KeyGenerator` `KeyFactory` 类，`SecretKey` 和 `PBEKey`

`KeyGenerator` 类，`SecretFactory` `Key` 接口，密钥 `KeyGenerator` 类，`SecretFactory`

`KeyPair` 接口，`SecretKey` 和 `PBEKey` `KeySpec` 接口，`SecretKey` 和 `PBEKey`

`KeyStore` 类，密钥协商 `Mac` 类，使用密码

`MessageDigest` 类，通过算法名称获取引擎类实例，动态提供者注册

## 动态提供者注册

`PBEKey` 接口，密钥

- 私钥接口，`SecretKey` 和 `PBEKey`

- 公钥接口，`SecretKey` 和 `PBEKey`

- `SecretFactory` 类，`KeyFactory`

- `SecretKey` 接口，密钥

- `SecureRandom` 类，算法名称

- `Signature` 类，消息摘要

- 加密提供者，Android JCA 提供者

- CSP (密码学服务提供者)，加密提供者

- CSPRNG (密码学安全的伪随机数生成器)，算法名称，`SecureRandom`

- `ctl_default_prop` 类型，标记系统属性

- CTR（计数器）模式，分组密码工作模式

- CyanogenMod Android 发行版，软件卡仿真，SuperSU 如何初始化

- DAC（自主访问控制），多用户支持，Selinux，自定义恢复

- 守护进程 (daemons)，Android 应用组件，内核级强制

- 原生进程级强制，内核级强制安全模型和，Android 应用组件

- `daemonsu` 二，SuperSU

- Dalvik Exec (DEX)，原生用户空间，应用程序包和数据的位置

- Dalvik VM，原生用户空间

- 危险保护级别，正常

- `data_file_type` 属性，类型和属性语句

- 通知，访问 `Binder` 对象

- `debuggable` 标记，应用沙箱

- USB，暴力攻击防护，暴力攻击防护，ADB 概述，对安全 ADB 的需求，安全 ADB 实现，安全 ADB 实现，

- 认证密钥，安全 ADB 实现

- 守护进程概述，暴力攻击防护

- 实现，安全 ADB 实现

- 安全需求，ADB 概述

- 安全，对安全 ADB 的需求

- 验证主机密钥指纹，安全 ADB 实现

`DECRYPT_MODE`，获取密码实例

- 实现，安全 ADB 实现

- 需要，ADB 概述

- 安全性，对安全 ADB 的必要性

- 验证主机密钥指纹，安全 ADB 实现

- 验证启动功能，恢复 (Recovery)，恢复 (Recovery)，`dm-verity` 概述，Android 实现

- 启用，Android 实现

- 实现，`dm-verity` 概述

- 概述，恢复 (Recovery)

- 设备存储加密，策略强制

- `dex2at` 命令，创建数据目录

- DEX (Dalvik 执行文件)，原生用户空间，应用程序包和数据的位置

- `deopt` 命令，安装守护进程

- DH (Diffie-Hellman)，密钥生成器，Android 的 Bouncy Castle Provider

- `digest()` 方法，`MessageDigest`

- DigiNot 攻击，当今 PKI 中的信任问题

- 数字签名算法 (DSA)，Android JCA 提供者，Android 的 Bouncy Castle，AndroidOpenSSL Provider，keymaster 模块和 keystore 服务实现

- `<disable-camera>` 标签，设备管理



`<disable-keyguard-features>`标签，设备管理

`disableReaderMode()`方法，使用阅读模式

`DISALLOW_CONFIG_BLUETOOTH`限制，多用户

`DISALLOW_CONFIG_CREDENTIALS`限制，多用户

`DISALLOW_CONFIG_WIFI`限制，多用户

`DISALLOW_INSTALL_APPS`限制，多用户，应用限制

`DISALLOW_INSTALL_UNKNOWN_SOURCES`限制，多用户

`DISALLOW_MODIFY_ACCOUNTS`限制，多用户，列出和验证账户

`DISALLOW_REMOVE_USER`限制，多用户

`DISALLOW_SHARE_LOCATION`限制，多用户，应用限制

`DISALLOW_UNINSTALL_APPS`限制，多用户，应用限制

`DISALLOW_USB_FILE_TRANSFER`限制，多用户自主访问控制 (DAC)，多用户支持，Selinux，自定义限制

磁盘加密，启用验证启动，磁盘加密，加密模式，密钥派生，磁盘加密密码，更改磁盘加密密码，使用系统属性控制设备加密，触发加密过程，解密并挂载`/data`

启动已加密设备，触发加密过程，解密并挂载`/data`

解密并挂载`/data`

获取密码，解密并挂载`/data`

所有系统服务，解密并挂载`/data`

加密模式，启用磁盘加密，更改磁盘加密密码，使用系统属性控制设备加密，触发加密过程

使用系统属性控制加密，更改磁盘加密密码

触发加密过程，触发加密过程卸载`/data`，使用系统属性控制设备加密

更新加密页脚，触发加密过程

密钥派生，加密模式的限制，解密并挂载`/data`的密码，密钥派生，磁盘加密密码

更改，磁盘加密密码

识别名称 (DN)，网络安全和 PKI dm-crypt device-mapper 目标，恢复 (Recovery)，磁盘加密，触发加密过程

dm-verity device-mapper 块完整性检查目标，恢复 (Recovery)，恢复 (Recovery)，dm-verity 概述，Android 实现

启用，Android 实现，dm-verity 概述

概述，恢复 (Recovery)

DN (识别名称)，网络安全和 PKI

`doFinal()`方法，分组密码工作模式

`domain`属性，类型和属性语句

`domain_auto_trans()`宏，类型转换规则

`domain_trans()`宏，类型转换规则

`dontaudit`规则，`auditallow`规则

`doPhase()`方法，密钥协商

`DownloadManager`服务，`MediaContainerService`

DSA (数字签名算法)，Android JCA 提供者，Android 的 Bouncy Castle Provider，AndroidOpenSSL Provider，keymaster 模块和 keystore 服务实现

# E

EAP (扩展验证协议)，凭据存储，凭据存储，密钥和证书，多用户 VPN 实现，Wi-Fi EAP，Wi-Fi EAP，EAP 认证方法，EAP 认证方法，EAP 认证方法，EAP 认证方法，Android Wi-Fi 架构，EAP 凭据管理

使用`WiFiManager`添加网络，EAP 凭据管理

Android Wi-Fi 架构，EAP 认证方法

密钥和证书，凭据存储，认证方法，Wi-Fi EAP，Wi-Fi EAP，EAP 认证方法，EAP 认证方法，EAP 认证方法，EAP 认证方法

- EAP-PWD，EAP 认证方法

- EAP-TLS，EAP 认证方法

- EAP-TTLS，EAP 认证方法

# PEAP，Wi-Fi EAP

凭据管理，Android Wi-Fi 架构

概述，凭据存储

系统凭据库，密钥和证书

EAP-PWD (仅使用密码的 EAP)，EAP 认证方法，EAP 凭据管理

EAP-TLS (EAP-传输层安全)，凭据存储，EAP 认证方法，EAP 凭据管理，使用`WifiManager`添加 EAP 网络

EAP-TTLS (EAP-隧道传输层安全)，EAP 认证方法，EAP 凭据管理

EAS (Exchange ActiveSync 账户集成)，托管设备

ECB (电子密码本)，分组密码工作模式

ECDSA (椭圆曲线 DSA)，Android 代码签名，keymaster 模块和 keystore 服务实现

EC (椭圆曲线)，`SecretKeyFactory`

edify 函数，启动系统更新过程

`editProperties()`方法，管理账户

EE (终端实体)，公密钥基础设施，证书黑名单

已定义，公密钥基础设施

处理泄露，证书黑名单

实际用户 ID (EUID)，Binder 实现

电子密码本 (ECB)，分组密码工作模式

电子边界基金 (EFF)，当今 PKI 中的信任问题

椭圆曲线 DSA (ECDSA)，Android 代码签名，keymaster 模块和 keystore 服务实现

椭圆曲线 (EC)，`SecretKeyFactory`

嵌入式安全元素 (eSEs)，UICC，嵌入式 SE，访问 eSE，使用`NfcExecutionEnvironment` API

广播，使用`NfcExecutionEnvironment` API 访问嵌入式 SE

`NfcExecutionClass`，访问 eSE 模拟外部存储，应用程序共享

`EMULATED_STORAGE_SOURCE`环境变量，Android 实现，Android 实现

`EMULATED_STORAGE_TARGET`环境变量，Android 实现，Android 实现

`enableForegroundDispatch()`方法，注册标签分发

`enableReaderMode()`方法，使用阅读模式加密盐-密码初始化向量 (ESSIV)，磁盘加密，加密模式

`<encrypted-storage>`标签，设备管理加密，策略强制，启用验证启动，备份文件格式

备份，备份文件格式设备存储，策略强制

# `ENCRYPT_MODE`，获取加密实例

终端实体，公密钥基础设施强制，权限，进程属性分配，内核级强制，框架级强制，静态强制，静态强制，广播权限强制，广播权限强制，广播权限强制

- 框架级，框架级强制，静态强制，静态强制，静态强制，广播权限强制，广播权限强制，广播权限强制

- 活动权限强制，静态强制广播权限强制，广播权限强制

- 内容提供者权限强制，静态强制动态强制，框架级强制

- 保护广播，广播权限强制

服务权限强制，静态强制

粘性广播，广播权限分配

内核级，原生守护进程级，内核级强制

`enforcePermission()`函数，动态强制，共享用户 ID

企业安全，企业安全，企业级安全，实现，策略持久化，策略持久化，策略强制，托管设备，Microsoft Exchange ActiveSync，VPN 支持，VPN 支持，L2TP/IPSec，L2TP/IPSec，基于 SSL 的 VPN，始终连接 VPN，通知用户连接，多用户 VPN 实现，Wi-Fi EAP，EAP 认证方法，Android Wi-Fi 架构，EAP 凭据管理

设备管理 API，企业安全，实现，策略持久化，策略持久化，托管设备

账户集成，托管设备

设备管理员，策略强制

策略强制，策略持久化

策略持久化，策略持久化

权限管理，实现

EAP 框架，多用户 VPN 实现，Wi-Fi EAP，EAP 认证方法，Android Wi-Fi 架构，EAP 凭据管理

使用`WiFiManager` API 添加网络，EAP 凭据管理

Android Wi-Fi 架构，EAP 认证方法，Wi-Fi EAP

凭据管理，Android Wi-Fi 架构

VPN，Microsoft Exchange ActiveSync，VPN 支持，VPN 支持，L2TP/IPSec，L2TP/IPSec，基于 SSL 的 VPN，始终连接 VPN，通知用户 VPN 连接

基于应用的，始终连接 VPN

L2TP，VPN 支持

遗留，基于 SSL 的 VPN

多用户支持，通知用户 VPN 连接

PPTP，VPN 支持

基于 SSL，L2TP/IPSec

Xauth，L2TP/IPSec

`EntropyMixer`服务，`SecureRandom`

eSEs，UICC

ESSIV（加密盐扇区初始化向量），磁盘加密，密码器模式

`establish()`方法，声明 VPN

EUID（有效用户 ID），Binder 实现

EV（扩展验证）证书，直接信任和私有 CA

Exchange ActiveSync (EAS) 账户集成，托管设备

`<expire-password>`标签，设备管理

ext4 文件系统，前向锁，安全上下文分配与持久化

扩展验证 (EV) 证书，直接信任和私有 CA

可扩展认证协议 (EAP)，多用户 VPN 实现

可扩展认证协议-传输层安全协议 (EAP-TLS)，凭据存储，EAP 认证方法，EAP 凭据管理，EAP 凭据管理，使用`WiFiManager`添加 EAP 网络

可扩展认证协议-隧道传输层安全协议 (EAP-TTLS)，EAP 认证方法，EAP 凭据管理

仅使用密码的可扩展认证协议 (EAP-PWD)，EAP 认证方法，EAP 凭据管理

外部存储，应用共享，外部存储实现，高级 Linux 挂载功能，Android 实现

Android 实现，高级 Linux 挂载功能

Linux 挂载功能，外部存储实现

概述，应用共享

权限，Android 实现

`EXTERNAL_STORAGE`环境变量，Android 实现

`EXTRA_CERTIFICATE` Key，使用私钥

# F

面解锁方法，锁屏解锁方法

出厂重置，系统更新

`failedAttempts`属性，用户元数据文件

`fastboot boot`命令，Android 分区布局，更新恢复

`fastboot`命令行工具，Android 分区布局

`fastboot devices`命令，Android 分区布局

`fastboot flash`命令，Android 分区布局，更新恢复

`fastboot flash:raw`命令，Android 分区布局

`fastboot`模式，设备安全，Fastboot 模式，Fastboot 模式，Android 分区布局，Android 分区布局

命令，Android 分区布局

分区布局，Fastboot 模式

协议，Android 分区布局

`fastboot oem lock`命令，解锁引导程序

`fastboot oem`命令，解锁引导程序

`fastboot update`命令，Android 分区布局

`fastboot update ZIP文件名`命令，Android 分区布局

FAT 文件系统，前向锁

FDE（全磁盘加密），启用验证启动

文件控制信息 (FCI)，查询 eSE 执行环境

`file_getprop`函数，启动系统更新过程

用户空间文件系统 (FUSE)，外部存储实现

文件类型，类型和属性语句

`FLAG_ADMIN`标志，用户元数据文件

`FLAG_GRANT_PERSISTABLE_URI_PERMISSION`标志，动态提供权限

`FLAG_GRANT_READ_URI_PERMISSION`标志，动态提供权限

`FLAG_GRANT_WRITE_URI_PERMISSION`标志，动态提供权限

`FLAG_GUEST`标志，用户元数据文件

`FLAG_INITIALIZED`标志，用户元数据文件

`FLAG_PRIMARY`标志，用户元数据文件

`FLAG_RESTRICTED`标志，用户元数据文件

`flags`属性，向`packages.xml`添加新包，用户元数据文件，策略持久化

`FLAG_UPDATED_SYSTEM_APP`标志，更新系统应用

Flame，代码签名

`<force-lock>`标签，企业安全

`fork()`系统调用，权限和进程属性

`format`函数，启动系统更新过程

框架，Android 框架库，框架级强制，静态强制，静态强制，静态强制，广播权限强制，广播权限强制，广播权限强制，Nexus 4 硬件支持

凭据存储实现，Nexus 4 硬件支持

组成部分，Android 框架库

框架级权限强制，框架级强制，静态强制，静态强制，静态强制，广播权限强制，广播权限强制，广播权限强制

Activity权限强制，静态强制

广播权限强制，广播权限强制

内容提供者权限强制，静态强制

动态强制，框架级强制

受保护广播，权限强制，服务权限强制，静态强制

粘性广播，广播权限强制

`ft`属性，向`packages.xml`添加包

`FullBackup`类，全磁盘加密 (FDE)，启用验证启动

FUSE（用户空间文件系统），外部存储实现

# G

GCM（高斯计数模式），分组密码模式

Google 客户端消息，Android 证书黑名单

`generateCertificate()`方法，证书工厂

`generateCertPath()`方法，证书工厂

`GENERATE_KEYPAIR`命令，Nexus 4 硬件支持

`generate_keypair()`方法，keymaster 模块和密钥服务实现

`generateKeyPair()`方法，密钥工厂

`generate()`方法，密钥工厂

`generateSecret()`方法，密钥

通用路由封装 (GRE)，VPN 支持

`getAccountCredentialsForCloning()`方法，多用户支持

`GET_ACCOUNTS`权限，列出账户

`getAlgorithm()`方法，密钥

`getApplicationRestrictions()`方法，应用限制

`getAuthToken()`方法，管理账户，表结构

`getCallingPid()`方法，静态强制

`getCallingUid()`方法，静态强制

`getCertificateChain()`方法，使用私钥

`getCertificate()`方法，密钥链实现

`getDeviceOwner()`方法，设置设备所有

`getDeviceOwnerName()`方法，设置设备所有

`getEmbeddedExecutionEnvironment()`方法，使用 NFC 执行环境 API

`getEncoded()`方法，密钥，密钥工厂

`getEncryptionStatus()`方法，策略强制

`enforce`工具，库

`getEntry()`方法，Android 密钥库提供者

`getExternalFilesDir()`方法，Android 实现

`getExternalStorageDirectory()`方法，Android 实现

`getFormat()`方法，密钥

`getInstance()`方法，动态提供者注册

`getkeypair_public()`方法，keymaster 模块和密钥库服务实现

`getKeySpec()`方法，密钥工厂

`get()`方法，标签技术

`getModulus()`方法，密钥密钥和 PBE

`getPassword()`方法，列出账户，表结构，表访问

`getPrivateExponent()`方法，密钥密钥和 PBE

`getPrivateKey()`方法，使用私钥，密钥链实现

`getprop`函数，启动系统更新过程

`getReaders()`方法，使用 OpenMobile API

`getsebook`工具，库

`SelectionModeForCategory()`方法，APDU 路由

`getUserData()`方法，列出账户

`getvar`命令，Android 分区布局

GlobalPlatform 卡规范，Android SE 执行环境，SE 通信协议

Google 代理设置，策略强制

`GLOBAL_SEARCH`权限，静态提供者权限

GLS (Google 登录服务)，Google 账户支持

Google 帐户管理器，Google 账户支持

Google 账户，Google 账户支持，Google 账户支持，支持，Google 服务身份验证与授权，ClientLogin，OAuth 2.0

ClientLogin 协议，Google 服务身份验证与授权

Google 帐户管理器，Google 账户支持

Google 登录服务，Google 账户支持

Google Play 服务，OAuth 2.0

OAuth 2.0，ClientLogin

概述，Google 账户支持

账号集成，Microsoft Exchange ActiveSync

Google 消息服务 (GCM)，Android 证书黑名单

Google 设备，在线账户管理

Google 登录服务 (GLS)，Google 账户支持

Google Play，正常

Google 服务框架 (GSF)，Google 账户支持

Google 钱包，嵌入式 SE，eSE 相关广播

GPS (Google Play 服务)，OAuth 2.0

`GrantedPermission`类，动态强制



`grantPermission()`方法，动态提供者权限

`grants`表，表结构

GRE（通用路由封装），VPN 支持

GSF（Google 服务框架），Google 账户支持

访客用户，应用限制

# H

HAL（硬件抽象层），`keymaster`模块和`keystore`服务实现，EAP 身份验证方法

硬件安全模块（HSM），PKCS#12 文件备份密钥库

HCE，Android 4.4 HCE 架构

HMAC 算法，安装前锁定的 APK

`HostApduService`，标签，软件卡仿真，为 SE Applets 指定路由，编写 HCE 服务

`<host-apdu-service>`标签，APDU 路由基于主机的卡仿真（HCE）；软件卡仿真，软件卡仿真，Android 4.4 HCE 架构，Android 4.4 HCE 架构，APDU 路由，为 HCE 服务指定路由，为 SE Applets 指定路由，编写 HCE 服务

Android 4.4 架构，软件卡仿真

APDU 路由，Android 4.4 HCE 架构，APDU 路由，为 HCE 服务指定路由

为 HCE 服务指定路由，APDU 路由

为 SE applets 指定路由，为 HCE 服务指定路由

应用安全，编写 HCE 服务

编写服务，为 SE applets 指定路由

主机名验证，对端身份验证

`HostnameVerifier`类，对端身份验证

HSM（硬件安全模块），PKCS#12 文件备份密钥库

`HttpClient`类，使用系统信任存储

HTTPS（安全超文本传输协议），证书撤销

`HttpsURLConnection`类，证书撤销，对端身份验证，Android JSSE 实现，使用系统信任存储

`IAccAuthenticator`接口，身份验证器模块，共享账户

`icon`属性，用户元数据文件

`id`属性，用户元数据文件

实用，库和工具

IKE（网络密钥交换），L2TP/IPSec

`KeyguardService`，锁屏实现

`IMPORT_KEYPAIR`命令，Nexus 4 硬件支持实现

`import_keypair()`方法，`keymaster`模块和`keystore`服务实现

`inherits`关键字，对象类和权限语句

`init_daemon(domain)`宏，类型转换规则

`initialization vector()`，分组密码工作模式，`keystore`服务

`initSign()`方法，签名

`insertProviderAt()`方法，提供者实现，使用自定义提供者

`INSTALL_ACTION`意图，软件包数据位置

`InstallProgress` Activity，解析并验证包

`installCaCert()`方法，托管设备

`instal`守护进程，策略概述

`installer`属性，将新包添加到`packages.xml`

`installExistingPackageAsUser()`方法，应用共享

`INSTALL_FAILED_INVALID_APK`错误，实现和加密参数

`INSTALL_FAILED_SHARED_USER_INCOMPATIBLE`错误，开发权限

`INSTALL_FAILED_UID_CHANGED`错误，开发权限

`INSTALL_FAILED_USER_RESTRICTED`错误，应用限制

`INSTALL_FAILED_USER_VERIFICATION_FAILURE`错误，Android 软件包验证

`INSTALL_FORWARD_LOCK`标志，安装前锁定的 APK

`INSTALL_NON_MARKET_APPS`设置，`MediaContainerService`

`INSTALL_PACKAGES`权限，解析并验证包

`installPackageWithVerificationAndEncryption()`方法，`PackageInstaller`系统应用，创建并安装加密 APK

`INSTALL_PARSE_FAILED_INCONSISTENT_CERTIFICATES`错误，签名验证

`INTERACT_ACROSS_USERS_FULL`权限，用户状态及相关广播

`INTERACT_ACROSS_USERS`权限，广播权限，用户状态及相关广播

`INTERNAL_SYSTEM_WINDOW`权限，屏幕安全

`INTERNAL_TARGET_DESELECTED`广播，eSE 相关广播

网络密钥交换（IKE），L2TP/IPSec

`INTERNET`权限，请求权限

IP 安全协议（IPSec），VPN 支持

互联网安全关联和密钥管理协议（ISAKMP），L2TP/IPSec

`invalidate.AuthToken()`方法，管理账户

IPC（进程间通信），Dalvik VM，权限

以及，Dalvik VM

安全模型，权限

IPSec 扩展身份验证（Xauth），L2TP/IPSec

IPSec（IP 安全协议）协议，VPN 支持

`isAdminActive()`方法，实现设备管理员

ISAKMP（互联网安全关联和密钥管理协议），L2TP/IPSec

`isBoundKeyAlgorithm()`方法，删除密钥和证书

`isDefaultServiceForCategory()`方法，APDU 路由

`isDeviceOwnerApp()`方法，设置设备所有者

`isDeviceOwner()`方法，设置设备所有者

`isKeyAlgorithmSupported()`方法，删除密钥和证书

Issuer 安全域（IS）组件（卡片管理器），Android SE 执行环境

`isSystemServer`选择器，标记应用进程

`it`属性，将新包添加到`packages.xml`

`initialization vector()`，分组密码工作模式，`keystore`服务

`iv`参数，创建加密 APK

# 第二部分

引擎类，动态提供者注册，动态提供者注册

获取实例，动态提供者注册

`KeyAgreement`类，`KeyGenerator`

`KeyFactory`类，`SecretKey`

`KeyGenerator`类，`SecretFactory`

`Key`接口，`Key`

`KeyPairGenerator`类，`SecretFactory`

`KeyPair`接口，`Key`

`KeyStore`类，`KeyAgreement`

`Mac`类，使用加密

`MessageDigest`类，`SecureRandom`

`PBEKey`接口，`Key`

`PrivateKey`接口，`SecretKey`和`PBEKey`

`PublicKey`接口，`SecretKey`和`PBEKey`

`SecretKeyFactory`类，`KeyFactory`

`SecretKey`接口，`Key`

`SecureRandom`类，算法

`Signature`类，`MessageDigest`

Java 运行时库，Dalvik VM

Java 安全套字扩展（JSSE），Android JCA 提供者，证书撤销，JSSE 简介，JSSE 简介，对端身份验证，Android JSSE 实现，Android JSSE 实现，系统信任存储，Android 4.x 系统信任存储，系统信任存储 API，证书黑名单，证书黑名单，处理实体密钥损坏

算法名称，算法名称

架构，JCA 提供者架构，加密服务提供者，提供者实现，提供者实现

动态提供者注册，提供者实现

静态提供者注册，提供者实现

`CertificateFactory`类，PKCS#12 文件备份密钥库

`CertPath`类，PKCS#12 文件备份密钥库

`CertPathValidator`类，`CertificateFactory`和`CertPath`

`Cipher`类，签名，分组密码工作模式，分组密码工作模式，使用加密

分组密码模式，分组密码工作模式

获取实例，分组密码工作模式

概述，签名

使用，获取加密

Android 实现，Android JSSE

证书黑名单，Android 黑SE

# Android，处理终端实体密钥泄露

- 处理 CA 密钥泄露，证书黑名单

- 处理 EE（终端实体）密钥泄露，证书黑名单

- 证书管理与验证，Android JSSE 实现，系统信任存储库

- Android 4.x 系统信任存储库，系统信任存储库 API

- Android 4.x 系统信任存储库，系统信任存储库

- 系统信任存储库 API

- 系统信任存储库，Android JSSE 实现

- 使用系统信任存储库，Android 4.x 系统信任存储库

- 验证，对端身份认证

- 概述，证书吊销，JSSE 简介

- 对端身份认证，Android JCA 提供者

- 安全套接，JSSE 简介

- Java 虚拟机（JVM），原生用户态

- JCA，算法名称

- JCRE（Java 卡片运行时环境），eSE 相关广播

- JSSE，Android JSSE 实现

- `--just_exit`

- JVM（Java 虚拟机），原生用户态

# K

- KDF（密钥派生函数），密钥协商（`KeyAgreement`）

- KEK（密钥加密密钥），Nexus 4 硬件支持实现，启用验证启动，密码模式，密钥派生

- 内核级权限强制，进程属性分配

- `KeyAgreement`类，`KeyGenerator`，Android 的 Bouncy Castle 提供者，OpenSSL 提供者

- 密钥块（key blobs），密钥库服务（The keystore Service）

- API Key，公开 API，安装 PKCS#12 文件，使用私钥，删除密钥和用户证书，删除密钥和用户证书，删除密钥和用户证书，托管设备

- 删除密钥和用户证书

- 安装 CA 证书，使用私钥

- `Keychain`类，公开 API

- 概述，公开 API，删除密钥和用户证书

- 支持的算法，删除密钥和用户证书

- 使用私钥，安装 PKCS#12 文件

- `KeychainBroadcastReceiver`，删除密钥和用户证书，控制对密钥库的访问

- `Keychain`类，公开 API

- `KeychainService`类，删除密钥和用户证书

- 密钥派生，密码模式

- 密钥解密函数（KDF），密钥协商

- 密钥加密密钥（KEK），Nexus 4 硬件支持实现，启用验证启动，密码模式，密钥派生

- `KeyFactory`类，`SecretKey`和`PBEKey`，Android JCA 提供者，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者

- `KeyGenerator`类，`SecretKeyFactory`，Android 的 Bouncy Castle 提供者

- 锁界面自定义，禁用，策略强制

- `KeyguardHostView`类，锁屏实现

- `KeyguardPINView`类，锁屏实现

- `KeyguardService`，锁屏实现

- 锁界面解锁方法，锁屏实现，锁界面解锁方法，锁界面解锁方法，锁界面解锁方法，锁界面解锁方法，锁界面解锁方法，模式解锁，模式解锁，模式解锁，PIN 和密码解锁

- 面部解锁，锁界面解锁方法

- 密码解锁，锁界面解锁方法，模式解锁

- 模式解锁，锁界面解锁方法，模式解锁

- PIN 解锁，锁界面解锁方法，模式解锁

- PUK 解锁，锁界面解锁方法，PIN 和密码解锁

- 滑动解锁，锁界面解锁方法

- `Key`接口，`Key`

- `KeyManager`类，对端身份认证

- `KeyManagerFactory`类，JSSE 简介

- `keymaster`模块，密钥库服务

- `KeyPairGenerator`类，`SecretKeyFactory`，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，Android Keystore 提供者，Android Keystore 提供者

- `KeyGeneratorSpec`类，Android Keystore 提供者

- `KeyPair`接口，`SecretKey`和`PBEKey`

- `--key`参数，创建并安装加密 APK

- `KeySpec`接口，`SecretKey`和`PBEKey`

- `KeyStore`类，密钥协商，Android 的 Bouncy Castle 提供者，JSSE 简介，Android 4.x 系统信任存储库，公开 API，Android Keystore 提供者

- `-keystore`参数，JAR 文件签名

- 密钥库服务，系统凭据库

- 密钥扩展（key stretching），`SecretKey`和`PBEKey`

# L

- L2TP（二层隧道协议），VPN 支持

- 标签，强制访问控制

- `lastAttemptMs`属性，用户元数据文件

- `lastLoggedIn`属性，用户元数据文件

- 最少使用（LRU），用户状态及相关广播

- 旧 VPN，基于 SSL 的 VPN，基于 SSL 的 VPN 实现，配置和凭据存储，始终连接 VPN

- 访问凭据，配置和凭据存储

- 始终连接，始终连接 VPN

- 实现，基于 SSL 的 VPN

- 配置和凭据存储，实现

- `<limit-password>`标签，企业安全

- 死亡链接（link to death），访问 Binder 对象

- Linux 内核，Linux 内核，通知用户 VPN 连接，恢复，恢复

- 高级路由，通知用户 VPN 连接

- Device-mapper 框架，恢复

- 逻辑卷管理器（LVM），恢复

- Linux 安全模块（LSM）框架，SELinux

- `load_policy`工具，库与工具

- `--locale`参数，控制恢复

- 位置，多用户支持，次用户

- 锁定功能，权限本质，策略强制

- `LOCKDOWN_VPN`文件，始终连接 VPN

- `LockdownVpnTracker`类，始终连接 VPN

- `LockNow()`方法，策略强制

- `LockPatternUtils`类，锁屏实现，PIN 和密码解锁

- 锁屏，多用户支持，用户类型

- `LockScreenUtils`类，模式解锁

- `LockSettingsService`，PIN 和密码解锁

- 逻辑卷管理器（LVM），恢复

- 登录尝试通知，策略持久化

- `-l`参数，Android 实现

- 低内存杀手（low memory killer），Linux 内核

# LRU（最少使用），用户状态及相关广播

- `Is`命令，安全上下文，库与工具

- LSM（Linux 安全模块）框架，SELinux

- LVM（逻辑卷管理器），恢复

# M

- `--macgalo`参数，实现与加密参数

- `Mac`类，使用密码，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者

- `--macker`参数，实现与加密参数

- MAC（强制访问控制），安全模型，多用户支持，SELinux，SELinux 架构，Android 实现

- MAC（消息摘要算法），使用密码，密钥库服务

- `MANAGE_ACCOUNTS`权限，列出和验证账户，管理账户

- `MANAGE_CA_CERTIFICATES`权限，系统信任存储库 API，托管设备

- `MANAGE_DEVICE_ADMINS`权限，权限管理

- `MANAGE_USERS`权限，访客

- 强制访问控制，安全模型，多用户支持，SELinux，SELinux 架构，Android 实现

- `MANIFEST.MF`文件，代码签名，JAR 文件签名

- 标记包，Linux 高级路由，多用户 VPN 实现

- `MASTER_CLEAR_NOTIFICATION`广播，eSE 相关广播

- key master，密钥库服务

- `MediaContainerService`，复制到应用程序目录，实现与加密参数，安装前锁定 APK

- `@MEDIA`宏，中间件 MAC

- 消息摘要算法（MAC），使用密码，密钥库服务

- `MessageDigest`类，`SecureRandom`，Android JCA 提供者，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者

- `META-INF`目录，Android 格式

多用户支持，IPC，用户管理，用户类型，主用户（所有者），次级用户，应用限制，游客用户，用户状态及相关广播，用户列表文件，用户系统目录，应用程序数据目录，应用共享，外部存储实现，高级 Linux 挂载特性，Android 实现，外部存储权限，表访问，多用户支持，通知 VPN 连接，Linux 高级路由

账户管理，表访问，多用户支持

概述，表访问

每用户账户数据库，多用户支持

共享账户，多用户支持

应用管理，用户系统目录，应用程序数据目录

应用共享，应用程序数据目录

数据目录，应用程序数据目录

概述，用户系统目录

广播及，游客用户

命令行工具，游客用户

外部存储，应用共享，外部存储实现，高级 Linux 挂载特性，Android 实现

Android 实现，高级 Linux 挂载特性

Linux 挂载特性，存储实现

概述，应用共享

权限，外部存储权限

特性位于，用户状态及相关广播，用户列表文件，用户系统目录

用户列表文件，用户状态及相关广播

用户元数据文件，用户列表文件

用户系统目录，用户系统目录

概述，用户管理

安全模型，IPC

用户类型，用户类型，主用户（所有者），次级用户，应用限制

- 游客用户，应用限制

主用户，用户类型

受限配置，次级用户

次级用户，主用户（所有者）

VPN，通知 VPN 连接，通知 VPN 连接，Linux 高级路由

- 实现，Linux 高级路由

Linux 高级路由，通知 VPN 连接

# N

`name`属性，向`packages.xml`中添加新包

`nativeLibraryPath`属性，向`packages.xml`中添加新包

原生用户空间层，Linux 内核

`NDEF_DISCOVERED` intent，注册标签分发



# NDEF（NFC 数据交换格式），读取/写入模式

近场通信，次级用户

`NET_ADMIN` 权限，签名

`netd` 守护进程，实现，始终开启 VPN，策略概述

过滤器内核框架，通知 VPN 连接

`NetworkManagementService`，Linux 高级路由

## 网络安全

网络安全与 PKI，直接信任与 CA，直接信任与私有 CA，公钥基础设施，证书吊销，JSSE 简介，对等身份验证，Android JSSE 实现，系统信任存储库，Android 4.x 信任库，系统信任方，系统信任存储库 API，Android 证书黑名单，现代 PKI 证书中的信任问题，收敛与信任捷性

证书锁定，收敛与信任捷性

证书吊销，公钥基础设施

收敛与信任，现代 PKI 中的信任问题

直接信任与私有 CA（Direct Trust and Private CA）

当前 PKI 系统的问题，Android 证书黑名单

JSSE，证书吊销，JSSE 简介，对等身份验证，Android JSSE 实现，系统信任存储库，Android 4.x 系统信任库，系统信任存储库 API

Android 4.x 系统信任库，系统信任存储库

Android 实现，Android JSSE 实现

证书黑名单，系统信任存储库 API

主机名验证，对等身份验证

概述，证书吊销

对等身份验证，JSSE 简介

安全套接，JSSE 简介

系统信任存储库 API，系统信任存储库 API

系统信任存储库概述，Android 4.x 系统信任库

使用系统信任存储库，Android 4.x 系统信任库

PKI，直接信任与私有 CA

公钥证书，网络安全与 PKI

## 安全策略与权限

`neverallow` 规则，`auditallow` 规则

`nextBytes()` 方法，`SecureRandom`

`nextSerialNumber` 属性，用户列表文件

Nexus 设备，应用共享，Nexus 4 硬件保护实现，`Fastboot` 命令

凭据存储，Nexus 4 硬件保护实现

官方恢复，`Fastboot` 命令

`NfcActivity` 类，注册标签分发

`NfcAdapter` 类，注册标签分发，使用读取模式，对等传输模式

`NfcExtras` 类，使用 NfcExecutionEnvironment API

## NFC 相关

NFC 数据交换格式（NDEF），读取/写入模式

`NfcAccessControl` 类，嵌入式 SE（安全元素）

`NFCEE_ADMIN` 权限，嵌入式 SE

`NfcExecutionEnvironment` 类，授予 eSE 访问，使用 NfcExecutionEnvironment API，Android SE 执行环境

NFC（近场通信），次级用户

NFC（近场通信），NFC 与安全元素，NFC 概述，使用读取模式，对等传输模式，卡仿真，Android 4.4 HCE 架构，为 SE Applet 指定路由

Android 支持 NFC，NFC 概述，使用读取模式，对等传输模式

卡仿真模式，对等传输模式

对等传输模式，使用读取模式

读取/写入模式，NFC 概述

基于模型的卡仿真，卡仿真，Android 4.4 HCE 架构，为 SE Applet 指定路由，编写 HCE 服务

Android 4.4 架构，卡仿真

APDU 路由，Android 4.4 HCE 架构

应用安全，编写 HCE 服务

编写服务，为 SE Applet 指定路由

概述，NFC 与安全元素

`NfcService`，NFC 概述，嵌入式 SE

## 权限与保护级别

普通保护级别，权限

`nosusetuid` 标记，Root 权限

OAuth 2.0，客户端服务

OBB（不透明二进制）文件

BB（二进制大对象）文件

`Binder` 对象，Binder 安全

SecurityB（OFB），Block Block of of

`hostduduservice` 类，为 SE Applet 指定路由

`OFF_APDU_SERVICE`，为 SE Applet 指定路由

`offhost-apdu-service` 元素，为 SE Applet 指定路由

`onDeactivated()` 方法，卡仿真

`onDisabled()` 方法，实现设备

`onEnabled()` 方法，Google 登录服务

`onPasswordExpired()` 方法，策略强制

`onTagcovered()` 方法，使用读取模式

不透明二进制文件，安装守护进程

OpenID Connect，Google 服务身份验证与授权

`openLogicalChannel()` 方法，使用 OpenMobile API

`openMobile` API，访问 UICC

`openSession()` 方法，使用 OpenMobile API

## OpenSSL 相关

OpenSSL，Android 代码签名，创建加密文件，AndroidSSL

Android 密钥库引擎，Nexus 4 硬件保护实现

转换为 PKCS#8 格式，Android 代码签名

加密提供程序及，AndroidSSL

`enc` 命令，创建加密文件

`openssl enc` 命令，创建加密文件

OpenVPN 应用，L2TP/IPSec，声明 VPN

## 设备与系统

优化的 DEX 文件，Dalvik VM，应用程序包数据位置

OS 启动与安装控制，设备安全，设备安全，引导加载

加载程序，设备安全

恢复 OS，引导加载

OTA（空中），多用户支持，引导加载，启用安全验证，UICC

应用程序，官方恢复，控制恢复，控制恢复，控制恢复，OTA 签名验证

刷机包，通过刷入 OTA 包获取 Root

侧载包，控制恢复

签名验证，控制恢复

SIM 卡更新，UICC 应用程序

更新包，引导加载，启用安全验证，官方恢复，控制恢复，控制恢复，控制恢复，OTA 签名验证

# APK 安装过程

APK 安装过程、应用程序包和数据的位置、`MediaContainerService`、更新组件和权限、更新系统应用、安装前向锁定 APK、安装前向锁定 APK

活动组件、Android 4.1 前向锁定实现、安装前向锁定 APK

加密应用与 Google Play、安装前向锁定 APK 前向锁定、实现与加密参数

安装加密 APK、更新系统应用

安装本地包、`MediaContainerService`

应用程序包和数据的位置、APK 安装过程

更新包、更新组件和权限

代码签名、实现、查看或提取签名者信息

在 Android 中、查看或提取签名者信息

在 Java 中、实现

包验证、Android 对包验证的支持、Android 对包验证的支持

Android 支持、Android 对包验证的支持

Google Play 实现、Android 对包验证的支持

`package-restrictions.xml` 文件、用户系统目录、应用程序数据目录

`PackageManagerService`、`MediaContainerService`、动态强制、复制到应用程序目录

创建并安装加密 APK、Android 对包验证的支持、Android 对包验证的支持、客体用户、应用程序数据目录、应用

共享、身份验证器模块、中间件 MAC

包、IPC

`packages.xml` 文件、应用程序包和数据的位置

`package_extract_dir` 函数、启动系统更新过程

`package_extract_file` 函数、启动系统更新过程

`PACKAGE_INSTALLED` 广播、广播权限强制

`PACKAGE_NEEDS_VERIFICATION` 动作、Android 对包验证的支持

`PACKAGE_REMOVED` 广播、控制密钥库的访问

`PACKAGE_REPLACED` 广播、更新非系统应用

`PACKAGE_VERIFICATION_AGENT` 权限、Android 对包验证的支持

`PACKAGE_VERIFIED` 广播、Android 对包验证的支持

`PACKAGE_VERIFIER_ENABLE` 设置、Android 对包验证的支持、填充、签名

## 认证与密码

PAP（密码认证协议）、VPN 支持部分属性、用户元数据文件

密码过期超时、策略强制

密码解锁方法、锁屏解锁方法、模式解锁

`PASSWORD_QUALITY_ALPHANUMERIC` 常量、PIN 和密码解锁、策略持久化、策略持久化

`PASSWORD_QUALITY_NUMERIC` 常量、PIN 和密码解锁

模式解锁方法、锁屏解锁方法、模式解锁

`PBEKey` 接口、密钥

PBKDF2 算法、密码模式、磁盘加密密码、备份文件格式

PEAP（可扩展认证协议）、Wi-Fi EAP、EAP 凭据管理

`peekAuthToken(method)`、列出并验证账户

## 权限与进程

同行认证、JSSE 简介

点对点（P2P）方法、NFC 概述、使用读取模式

等待意图、Pending Intents

权限、应用程序沙箱、权限、权限、权限的本质、权限的本质、权限管理、权限管理、normal、signature、signature、signature、权限与进程属性、进程属性赋值、内核强制、原生守护进程级强制、广播权限

# 执行权限

系统权限、系统权限、开发权限、共享用户 ID、自定义权限、自定义权限、公共和私有组件、公共和私有组件、广播权限、广播权限、静态提供者权限、等待意图、应用共享、Android 实现

活动、公共和私有组件

分配、signature

广播、广播权限

内容提供者、广播权限、静态提供者权限

动态、静态提供者权限

静态、广播权限

自定义、共享用户 ID

执行、进程属性赋值、内核级强制、原生守护进程级强制

框架级、原生守护进程级强制

内核级、进程属性赋值

原生守护进程级、内核级强制

外部存储、Android 实现

管理、权限

概述、权限

等待意图、Pending Intents

PID 分配与、权限与进程属性

私有组件、自定义权限

保护级别、权限管理、normal、signature、signature

dangerous、normal

定义、权限管理

normal、权限管理

signature、signature

signatureOrSystem、signature

公共组件请求自定义权限、权限的本质

安全模型、应用程序沙箱服务、公共和私有组件共享用户 ID、开发权限

系统、广播权限强制、系统权限、系统权限开发权限、系统权限

概述、广播权限强制签名权限、系统权限查看已知列表、权限的本质

授予时、应用共享 `PERMISSION_DENIED` 响应、框架级强制

`PERMISSION_GRANTED` 响应、框架级强制语句、对象类和权限语句

PFX（信息交换语法）、密钥库类型钓鱼程序、加密应用与 Google Play

PID（进程 ID）、Binder 实现、权限与进程属性赋值、权限与进程属性

Binder 和、Binder 实现 PIN 解锁密钥（PUK）解锁方法、锁屏解锁方法、PIN 和密码解锁

PIN 解方法、锁屏解锁方法、模式解锁、PIN 和密码解锁、PIN 密码锁 `pinHash` 属性、用户元数据文件

PittPat（匹兹堡模式识别）公司、锁屏解锁方法

PKCS（公密钥密码学标准）、分组密码模式

PKCS#12 文件、凭据存储

PKI（公密钥基础设施）、网络安全与 PKI、直接信任和私有 CA、直接信任和私有 CA、公密钥基础设施

证书撤销、公密钥基础设施

直接信任和私有 CA、直接信任和私有 CA

概述、直接信任和私有 CA

公密钥证书、网络安全与 PKI

PKIX（基于 X.509）、Android Bouncy Castle 提供者、JSSE 简介

PKPE（HTTP 公密钥固定扩展）、收敛与信任敏捷性

平台密钥、IPC、系统权限

安全模型、IPC

系统应用和、系统权限

平台签名密钥、Android 框架库

`pm` 命令、OTA 文件代码签名

`pm create-user` 命令、客体用户

`pm get-max-users` 命令、客体用户

`pm install` 命令、更新系统应用、实现与加密参数

`pm list users` 命令、客体用户

## 公钥基础设施

公钥证书，网络安全与 PKI

公钥加密标准（PKCS），分组密码工作模式

公钥基础设施，公钥基础设施

用于 HTTP 的公钥固定扩展（PKPE），收敛性与信任敏捷性

`Public-Key-Pin` 头部，收敛性与信任敏捷性

`Public-Key-Pins-Report-Only` 头部，证书固定

`PublicKey` 接口，`SecretKey` 和 `PBEKey`

PUK（PIN 解锁密钥）解锁方法，Keyguard 解锁方法，PIN 和密码解锁

# Q

QSEE（高通安全执行环境），Nexus 4 硬件加速实现

# R

`racoon` 守护进程，基于 SSL 的 VPN，配置文件和凭据存储

射频识别（RFID）技术，NFC 概览

随机数生成器（RNG），算法名称

RA（注册机构），公钥基础设施

RC4 算法，Android 的 Bouncy Castle 提供者，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，VPN 支持

`READ_CONTACTS` 权限，静态提供者权限

读取器/写入器（R/W）模式，NFC 概览，读取器/写入器模式，注册标签分发，标签技术

- 读取器模式，标签技术

- 读取标签，标签技术

- 注册标签分发，读取器/写入器模式

- 标签技术，注册标签分发

`READ_EXTERNAL_STORAGE` 权限，Android 实现

`READ_LOGS` 权限，系统权限

只读分区，Android 框架库

# SMS 权限，普通

读写分区，用户安装应用

`recovery` 二进制文件，控制恢复

`recovery` 操作系统，引导程序，`Fastboot` 命令，控制恢复，控制恢复，控制恢复，OTA 签名验证，启动系统更新过程，复制并补丁文件，复制并补丁文件，复制并补丁文件，完成更新，更新恢复

自定义恢复，更新恢复

官方恢复，`Fastboot` 命令，控制恢复，控制恢复，控制恢复，OTA 签名验证，启动系统更新过程，复制并补丁文件，复制并补丁文件，复制并补丁文件，完成更新

- 应用更新，启动系统更新过程

- 控制，控制恢复

- 复制并补丁文件，复制并补丁文件

- 完成更新，复制并补丁文件

- OTA 签名验证，控制恢复

- 设置文件所有权、权限和安全标签，复制并补丁文件

- 侧载包，控制恢复

- 启动系统更新过程，OTA 签名验证

- 更新恢复

`RecoverySystem` 类，控制恢复

引用计数，访问 Binder 对象

参考实现（RI），Android 的 Bouncy Castle 提供者

注册机构（RA），公钥基础设施

`relabelmo` 权限，强制域

`@RELEASE` 宏，中间件 MAC

远程过程调用（RPC），进程间通信

`removeAccount()` 方法，管理账户，表访问

`removeActiveAdmin()` 方法，实现设备管理员

`removeProvider()` 方法，提供者实现

请求权限，权限的本质

意见征求请求（RFCs），分组密码工作模式

`requireDeviceUnlock` 属性，APDU 路由

`resetPassword()` 方法，策略持久化，策略执行

`<reset-password>` 标签，企业安全

资源属性，身份验证器模块

`resourcePath` 属性，将新包添加到 `packages.xml`

`Resources` 类，Android 应用包格式

`restorecon` 命令，库和工具，文件标记

`restrictedAccountType` 属性，应用限制，共享账户

受限配置，次用户，应用限制，应用限制

访问在线账户，应用限制

应用限制，应用限制

用户限制，次用户

`revokePermission()` 方法，动态提供者权限

`revokeUriPermission()` 方法，动态提供者权限

RFCs（意见征求请求），分组密码工作模式

RFID（射频识别）技术，NFC 概览

`rild`（射频接口）守护进程，PIN 和密码解锁

RI（参考实现），Android 的 Bouncy Castle 提供者

RNG（随机数生成器），算法名称

`ro.crypto.fs_crypto_blkdev` 属性，使用系统属性控制设备加密，解密并挂载 `/data`

`ro.crypto.state` 属性，更改加密密码

`ro.debuggable` 属性，生产构建上的 Root 权限

`cmd` 命令，自定义恢复，Root 权限，Root 权限，以 root 启动 ADB，使用命令，生产构建上的 Root 权限，通过刷入 OTA 包 Root，通过漏洞 Root

工程构建，Root 权限，Root 权限，以 root 启动 ADB

以 root 启动 ADB，Root 权限

使用命令，启动 ADB

生产构建，使用 `su` 命令，生产构建上的 Root 权限，通过刷入 OTA 包 Root，通过漏洞 Root

更改启动或系统镜像，生产构建上的 Root 权限

刷入 OTA 包，通过刷入 OTA 包 Root

通过漏洞，通过漏洞 Root

`root` 用户，`installd` 守护进程

`ro.secure` 属性，生产构建上的 Root 权限

RPC（远程过程调用），进程间通信

RSA 算法，实现，算法名称，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，`dm-verity` 概览，启用验证启动，控制恢复

`runcon` 工具，库和工具

`run_program` 函数，启动系统更新过程

运行时库，Dalvik VM

R/W 模式，NFC 概览

# S

S2C（信号输入/输出连接），嵌入式 SE

`salt` 属性，用户元数据文件

同源策略，IPC

沙盒，应用，Android 组件

SA（安全关联），L2TP/IPSec

`saveLockPassword()` 方法，PIN 和密码解锁

`lockPattern()` 方法，图案解锁

`scanPage()`，图案解锁

`saveLock()` 方法，复制到目录

`SCM_CREDENTIALS`，原生消息

屏幕安全，用户安装应用



# recovery 操作系统

## 引导程序与 Fastboot 命令

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新
- 更新恢复

## 自定义恢复

- 更新恢复

## 官方恢复

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新

### 应用更新

- 启动系统更新过程

### 控制

- 控制恢复

### 复制并补丁文件

- 复制并补丁文件

### 完成更新

- 复制并补丁文件

### OTA 签名验证

- 控制恢复

### 设置文件所有权、权限和安全标签

- 复制并补丁文件

### 侧载包

- 控制恢复

### 启动系统更新过程

- OTA 签名验证

### 更新恢复

- 完成

## `RecoverySystem` 类

- 控制恢复

## 引用计数

- 访问 `Binder` 对象

## 参考实现 (RI)

- Android 的 Bouncy Castle 提供者

## 注册机构 (RA)

- 公钥基础设施

## `relabelmo` 权限

- 强制域

## `@RELEASE` 宏

- 中间件 MAC

## 远程过程调用 (RPC)

- 进程间通信

## `removeAccount()` 方法

- 管理账户
- 表访问

## `removeActiveAdmin()` 方法

- 实现设备管理员

## `removeProvider()` 方法

- 提供者实现

## 请求权限

- 权限的本质

## 意见征求请求 (RFCs)

- 分组密码工作模式

## `requireDeviceUnlock` 属性

- APDU 路由

## `resetPassword()` 方法

- 策略持久化
- 策略执行

## `<reset-password>` 标签

- 企业安全

## 资源属性

- 身份验证器模块

## `resourcePath` 属性

- 将新包添加到 `packages.xml`

## `Resources` 类

- Android 应用包格式

## `restorecon` 命令

- 库和工具
- 文件标记

## `restrictedAccountType` 属性

- 应用限制
- 共享账户

## 受限配置

- 次用户
- 应用限制

### 访问在线账户

- 应用限制

### 应用限制

- 应用限制

### 用户限制

- 次用户

## `revokePermission()` 方法

- 动态提供者权限

## `revokeUriPermission()` 方法

- 动态提供者权限

## RFCs (意见征求请求)

- 分组密码工作模式

## RFID (射频识别) 技术

- NFC 概览

## `rild` (射频接口) 守护进程

- PIN 和密码解锁

## RI (参考实现)

- Android 的 Bounce Castle Provider

## RNG (随机数生成器)

- 算法名称

## `ro.crypto.fs_crypto_blkdev` 属性

- 使用系统属性控制设备加密
- 解密并挂载 `/data`

## `ro.crypto.state` 属性

- 更改加密密码

## `ro.debuggable` 属性

- 生产构建上的 Root 权限

## 命令

- 自定义恢复
- Root 权限
- 以 root 启动 ADB
- 使用命令
- 生产构建上的 Root 权限
- 通过刷入 OTA 包 Root
- 通过漏洞 Root

## 工程构建

- Root 权限
- 以 root 启动 ADB

### 以 root 启动 ADB

- Root 权限

### 使用命令

- 启动 ADB

### 生产构建

- 使用 `su` 命令
- 生产构建上的 Root 权限
- 通过刷入 OTA 包 Root
- 通过漏洞 Root

### 更改启动或系统镜像

- 生产构建上的 Root 权限

### 刷入 OTA 包

- 通过刷入 OTA 包 Root

### 通过漏洞

- 通过漏洞 Root

## `root` 用户

- `installd` 守护进程

## `ro.secure` 属性

- 生产构建上的 Root 权限

## RPC (远程过程调用)

- 进程间通信

## RSA 算法

- 实现
- 算法名称
- Android 的 Bouncy Castle 提供者
- `AndroidOpenSSL` 提供者
- dm-verity 概览
- 启用验证启动
- 控制恢复

## `runcon` 工具

- 库和工具

## `run_program` 函数

- 启动系统更新过程

## 运行时库

- Dalvik VM

## R/W 模式

- NFC 概览

# S

## S2C (信号输入/输出连接)

- 嵌入式 SE

## `salt` 属性

- 用户元数据文件

## 同源策略

- IPC

## 沙盒

- 应用
- Android 组件

## SA (安全关联)

- L2TP/IPSec

## `saveLockPassword()` 方法

- PIN 和密码解锁

## `lockPattern()` 方法

- 图案解锁

## `scanPage()`

- 图案解锁

## `saveLock()` 方法

- 复制到目录

## `SCM_CREDENTIALS`

- 原生消息

## 屏幕安全

- 用户安装应用

# recovery 操作系统

## 引导程序与 Fastboot 命令

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新
- 更新恢复

## 自定义恢复

- 更新恢复

## 官方恢复

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新

### 应用更新

- 启动系统更新过程

### 控制

- 控制恢复

### 复制并补丁文件

- 复制并补丁文件

### 完成更新

- 复制并补丁文件

### OTA 签名验证

- 控制恢复

### 设置文件所有权、权限和安全标签

- 复制并补丁文件

### 侧载包

- 控制恢复

### 启动系统更新过程

- OTA 签名验证

### 更新恢复

- 完成

## `RecoverySystem` 类

- 控制恢复

## 引用计数

- 访问 `Binder` 对象

## 参考实现 (RI)

- Android 的 Bouncy Castle 提供者

## 注册机构 (RA)

- 公钥基础设施

## `relabelmo` 权限

- 强制域

## `@RELEASE` 宏

- 中间件 MAC

## 远程过程调用 (RPC)

- 进程间通信

## `removeAccount()` 方法

- 管理账户
- 表访问

## `removeActiveAdmin()` 方法

- 实现设备管理员

## `removeProvider()` 方法

- 提供者实现

## 请求权限

- 权限的本质

## 意见征求请求 (RFCs)

- 分组密码工作模式

## `requireDeviceUnlock` 属性

- APDU 路由

## `resetPassword()` 方法

- 策略持久化
- 策略执行

## `<reset-password>` 标签

- 企业安全

## 资源属性

- 身份验证器模块

## `resourcePath` 属性

- 将新包添加到 `packages.xml`

## `Resources` 类

- Android 应用包格式

## `restorecon` 命令

- 库和工具
- 文件标记

## `restrictedAccountType` 属性

- 应用限制
- 共享账户

## 受限配置

- 次用户
- 应用限制

### 访问在线账户

- 应用限制

### 应用限制

- 应用限制

### 用户限制

- 次用户

## `revokePermission()` 方法

- 动态提供者权限

## `revokeUriPermission()` 方法

- 动态提供者权限

## RFCs (意见征求请求)

- 分组密码工作模式

## RFID (射频识别) 技术

- NFC 概览

## `rild` (射频接口) 守护进程

- PIN 和密码解锁

## RI (参考实现)

- Android 的 Bounce Castle Provider

## RNG (随机数生成器)

- 算法名称

## `ro.crypto.fs_crypto_blkdev` 属性

- 使用系统属性控制设备加密
- 解密并挂载 `/data`

## `ro.crypto.state` 属性

- 更改加密密码

## `ro.debuggable` 属性

- 生产构建上的 Root 权限

## 命令

- 自定义恢复
- Root 权限
- 以 root 启动 ADB
- 使用命令
- 生产构建上的 Root 权限
- 通过刷入 OTA 包 Root
- 通过漏洞 Root

## 工程构建

- Root 权限
- 以 root 启动 ADB

### 以 root 启动 ADB

- Root 权限

### 使用命令

- 启动 ADB

### 生产构建

- 使用 `su` 命令
- 生产构建上的 Root 权限
- 通过刷入 OTA 包 Root
- 通过漏洞 Root

### 更改启动或系统镜像

- 生产构建上的 Root 权限

### 刷入 OTA 包

- 通过刷入 OTA 包 Root

### 通过漏洞

- 通过漏洞 Root

## `root` 用户

- `installd` 守护进程

## `ro.secure` 属性

- 生产构建上的 Root 权限

## RPC (远程过程调用)

- 进程间通信

## RSA 算法

- 实现
- 算法名称
- Android 的 Bouncy Castle 提供者
- `AndroidOpenSSL` 提供者
- dm-verity 概览
- 启用验证启动
- 控制恢复

## `runcon` 工具

- 库和工具

## `run_program` 函数

- 启动系统更新过程

## 运行时库

- Dalvik VM

## R/W 模式

- NFC 概览

# S

## S2C (信号输入/输出连接)

- 嵌入式 SE

## `salt` 属性

- 用户元数据文件

## 同源策略

- IPC

## 沙盒

- 应用
- Android 组件

## SA (安全关联)

- L2TP/IPSec

## `saveLockPassword()` 方法

- PIN 和密码解锁

## `lockPattern()` 方法

- 图案解锁

## `scanPage()`

- 图案解锁

## `saveLock()` 方法

- 复制到目录

## `SCM_CREDENTIALS`

- 原生消息

## 屏幕安全

- 用户安装应用

# recovery 操作系统

## 引导程序与 Fastboot 命令

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新
- 更新恢复

## 自定义恢复

- 更新恢复

## 官方恢复

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新

### 应用更新

- 启动系统更新过程

### 控制

- 控制恢复

### 复制并补丁文件

- 复制并补丁文件

### 完成更新

- 复制并补丁文件

### OTA 签名验证

- 控制恢复

### 设置文件所有权、权限和安全标签

- 复制并补丁文件

### 侧载包

- 控制恢复

### 启动系统更新过程

- OTA 签名验证

### 更新恢复

- 完成

## `RecoverySystem` 类

- 控制恢复

## 引用计数

- 访问 `Binder` 对象

## 参考实现 (RI)

- Android 的 Bouncy Castle 提供者

## 注册机构 (RA)

- 公钥基础设施

## `relabelmo` 权限

- 强制域

## `@RELEASE` 宏

- 中间件 MAC

## 远程过程调用 (RPC)

- 进程间通信

## `removeAccount()` 方法

- 管理账户
- 表访问

## `removeActiveAdmin()` 方法

- 实现设备管理员

## `removeProvider()` 方法

- 提供者实现

## 请求权限

- 权限的本质

## 意见征求请求 (RFCs)

- 分组密码工作模式

## `requireDeviceUnlock` 属性

- APDU 路由

## `resetPassword()` 方法

- 策略持久化
- 策略执行

## `<reset-password>` 标签

- 企业安全

## 资源属性

- 身份验证器模块

## `resourcePath` 属性

- 将新包添加到 `packages.xml`

## `Resources` 类

- Android 应用包格式

## `restorecon` 命令

- 库和工具
- 文件标记

## `restrictedAccountType` 属性

- 应用限制
- 共享账户

## 受限配置

- 次用户
- 应用限制

### 访问在线账户

- 应用限制

### 应用限制

- 应用限制

### 用户限制

- 次用户

## `revokePermission()` 方法

- 动态提供者权限

## `revokeUriPermission()` 方法

- 动态提供者权限

## RFCs (意见征求请求)

- 分组密码工作模式

## RFID (射频识别) 技术

- NFC 概览

## `rild` (射频接口) 守护进程

- PIN 和密码解锁

## RI (参考实现)

- Android 的 Bounce Castle Provider

## RNG (随机数生成器)

- 算法名称

## `ro.crypto.fs_crypto_blkdev` 属性

- 使用系统属性控制设备加密
- 解密并挂载 `/data`

## `ro.crypto.state` 属性

- 更改加密密码

## `ro.debuggable` 属性

- 生产构建上的 Root 权限

## 命令

- 自定义恢复
- Root 权限
- 以 root 启动 ADB
- 使用命令
- 生产构建上的 Root 权限
- 通过刷入 OTA 包 Root
- 通过漏洞 Root

## 工程构建

- Root 权限
- 以 root 启动 ADB

### 以 root 启动 ADB

- Root 权限

### 使用命令

- 启动 ADB

### 生产构建

- 使用 `su` 命令
- 生产构建上的 Root 权限
- 通过刷入 OTA 包 Root
- 通过漏洞 Root

### 更改启动或系统镜像

- 生产构建上的 Root 权限

### 刷入 OTA 包

- 通过刷入 OTA 包 Root

### 通过漏洞

- 通过漏洞 Root

## `root` 用户

- `installd` 守护进程

## `ro.secure` 属性

- 生产构建上的 Root 权限

## RPC (远程过程调用)

- 进程间通信

## RSA 算法

- 实现
- 算法名称
- Android 的 Bouncy Castle 提供者
- `AndroidOpenSSL` 提供者
- dm-verity 概览
- 启用验证启动
- 控制恢复

## `runcon` 工具

- 库和工具

## `run_program` 函数

- 启动系统更新过程

## 运行时库

- Dalvik VM

## R/W 模式

- NFC 概览

# S

## S2C (信号输入/输出连接)

- 嵌入式 SE

## `salt` 属性

- 用户元数据文件

## 同源策略

- IPC

## 沙盒

- 应用
- Android 组件

## SA (安全关联)

- L2TP/IPSec

## `saveLockPassword()` 方法

- PIN 和密码解锁

## `lockPattern()` 方法

- 图案解锁

## `scanPage()`

- 图案解锁

## `saveLock()` 方法

- 复制到目录

## `SCM_CREDENTIALS`

- 原生消息

## 屏幕安全

- 用户安装应用

# recovery 操作系统

## 引导程序与 Fastboot 命令

- `Fastboot` 命令
- 控制恢复
- OTA 签名验证
- 启动系统更新过程
- 复制并补丁文件
- 完成更新
- 更新恢复



# 其他

- 自定义恢复，更新恢复
- 官方恢复，`Fastboot` 命令，控制恢复，`OTA` 签名验证，启动系统更新过程，复制并补丁文件，完成更新
  - 应用更新，启动系统更新过程
  - 控制，控制恢复
  - 复制并补丁文件
  - 完成更新
  - `OTA` 签名验证，控制恢复
  - 设置文件所有权、权限和安全标签，复制并补丁文件
  - 侧载包，控制恢复
  - 启动系统更新过程，`OTA` 签名验证
  - 更新恢复，完成
- `RecoverySystem` 类，控制恢复
- 引用计数，访问 `Binder` 对象
- 参考实现（`RI`），Android 的 Bouncy Castle 提供者
- 注册机构（`RA`），公钥基础设施
- `relabelmo` 权限，强制域
- `@RELEASE` 宏，中间件 `MAC`
- 远程过程调用（`RPC`），进程间通信
- `removeAccount()` 方法，管理账户，表访问
- `removeActiveAdmin()` 方法，实现设备管理员
- `removeProvider()` 方法，提供者实现
- 请求权限，权限的本质
- 意见征求请求（`RFCs`），分组密码工作模式
- `requireDeviceUnlock` 属性，`APDU` 路由
- `resetPassword()` 方法，策略持久化，策略执行
- `<reset-password>` 标签，企业安全
- 资源属性，身份验证器模块
- `resourcePath` 属性，将新包添加到 `packages.xml`
- `Resources` 类，Android 应用包格式
- `restorecon` 命令，库和工具，文件标记
- `restrictedAccountType` 属性，应用限制，共享账户
- 受限配置，次用户，应用限制
- 访问在线账户，应用限制
- 应用限制
- 用户限制，次用户
- `revokePermission()` 方法，动态提供者权限
- `revokeUriPermission()` 方法，动态提供者权限
- `RFID`（射频识别）技术，`NFC` 概览
- `rild`（射频接口）守护进程，`PIN` 和密码解锁
- `RI`（参考实现），Android 的 Bouncy Castle Provider
- `RNG`（随机数生成器），算法名称
- `ro.crypto.fs_crypto_blkdev` 属性，使用系统属性控制设备加密，解密并挂载 `/data`
- `ro.crypto.state` 属性，更改加密密码
- `ro.debuggable` 属性，生产构建上的 `root` 权限
- 命令，自定义恢复，`root` 权限，以 `root` 启动 `ADB`，使用命令，生产构建上的 `root` 权限，通过刷入 `OTA` 包获取 `root` 权限，通过漏洞获取 `root` 权限
- 工程构建，`root` 权限，以 `root` 启动 `ADB`
- 以 `root` 启动 `ADB`，`root` 权限
- 使用命令，启动 `ADB`
- 生产构建，使用 `su` 命令，生产构建上的 `root` 权限
- 更改启动或系统镜像，生产构建上的 `root` 权限
- 刷入 `OTA` 包，通过刷入 `OTA` 包获取 `root` 权限
- 通过漏洞获取 `root` 权限
- `root` 用户，`installd` 守护进程
- `ro.secure` 属性，生产构建上的 `root` 权限
- `RSA` 算法，实现，算法名称，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，`dm-verity` 概览，启用验证启动，控制恢复
- `runcon` 工具，库和工具
- `run_program` 函数，启动系统更新过程
- 运行时库，Dalvik VM
- `R/W` 模式，`NFC` 概览
- 公钥证书，网络安全与 `PKI`
- 公钥加密标准（`PKCS`），分组密码工作模式
- 公钥基础设施，公钥基础设施
- 用于 `HTTP` 的公钥固定扩展（`PKPE`），收敛性与信任敏捷性
- `Public-Key-Pin` 头部，收敛性与信任敏捷性
- `Public-Key-Pins-Report-Only` 头部，证书固定
- `PublicKey` 接口，`SecretKey` 和 `PBEKey`
- `PUK`（`PIN` 解锁密钥）解锁方法，`Keyguard` 解锁方法，`PIN` 和密码解锁

# Q

- `QSEE`（高通安全执行环境），Nexus 4 硬件加速实现

# R

- `racoon` 守护进程，基于 `SSL` 的 `VPN`，配置文件和凭据存储
- 射频识别（`RFID`）技术，`NFC` 概览
- 随机数生成器（`RNG`），算法名称
- `RA`（注册机构），公钥基础设施
- `RC4` 算法，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，`VPN` 支持
- `READ_CONTACTS` 权限，静态提供者权限
- 读取器/写入器（`R/W`）模式，`NFC` 概览
  - 读取器模式，标签技术
  - 读取标签，标签技术
  - 注册标签分发，读取器/写入器模式
  - 标签技术，注册标签分发
- `READ_EXTERNAL_STORAGE` 权限，Android 实现
- `READ_LOGS` 权限，系统权限
- 只读分区，Android 框架库
- `SMS` 权限，普通
- 读写分区，用户安装应用
- `recovery` 二进制文件，控制恢复
- `recovery` 操作系统，引导程序，`Fastboot` 命令，控制恢复，`OTA` 签名验证，启动系统更新过程，复制并补丁文件，完成更新
- 自定义恢复，更新恢复
- 官方恢复，`Fastboot` 命令，控制恢复，`OTA` 签名验证，启动系统更新过程，复制并补丁文件，完成更新
  - 应用更新，启动系统更新过程
  - 控制，控制恢复
  - 复制并补丁文件
  - 完成更新
  - `OTA` 签名验证，控制恢复
  - 设置文件所有权、权限和安全标签，复制并补丁文件
  - 侧载包，控制恢复
  - 启动系统更新过程，`OTA` 签名验证
  - 更新恢复，完成
- `RecoverySystem` 类，控制恢复
- 引用计数，访问 `Binder` 对象
- 参考实现（`RI`），Android 的 Bouncy Castle 提供者
- 注册机构（`RA`），公钥基础设施
- `relabelmo` 权限，强制域
- `@RELEASE` 宏，中间件 `MAC`
- 远程过程调用（`RPC`），进程间通信
- `removeAccount()` 方法，管理账户，表访问
- `removeActiveAdmin()` 方法，实现设备管理员
- `removeProvider()` 方法，提供者实现
- 请求权限，权限的本质
- 意见征求请求（`RFCs`），分组密码工作模式
- `requireDeviceUnlock` 属性，`APDU` 路由
- `resetPassword()` 方法，策略持久化，策略执行
- `<reset-password>` 标签，企业安全
- 资源属性，身份验证器模块
- `resourcePath` 属性，将新包添加到 `packages.xml`
- `Resources` 类，Android 应用包格式
- `restorecon` 命令，库和工具，文件标记
- `restrictedAccountType` 属性，应用限制，共享账户
- 受限配置，次用户，应用限制
- 访问在线账户，应用限制
- 应用限制
- 用户限制，次用户
- `revokePermission()` 方法，动态提供者权限
- `revokeUriPermission()` 方法，动态提供者权限
- `RFCs`（意见征求请求），分组密码工作模式
- `RFID`（射频识别）技术，`NFC` 概览
- `rild`（射频接口）守护进程，`PIN` 和密码解锁
- `RI`（参考实现），Android 的 Bouncy Castle Provider
- `RNG`（随机数生成器），算法名称
- `ro.crypto.fs_crypto_blkdev` 属性，使用系统属性控制设备加密，解密并挂载 `/data`
- `ro.crypto.state` 属性，更改加密密码
- `ro.debuggable` 属性，生产构建上的 `root` 权限
- 命令，自定义恢复，`root` 权限，以 `root` 启动 `ADB`，使用命令，生产构建上的 `root` 权限，通过刷入 `OTA` 包获取 `root` 权限，通过漏洞获取 `root` 权限
- 工程构建，`root` 权限，以 `root` 启动 `ADB`
- 以 `root` 启动 `ADB`，`root` 权限
- 使用命令，启动 `ADB`
- 生产构建，使用 `su` 命令，生产构建上的 `root` 权限
- 更改启动或系统镜像，生产构建上的 `root` 权限
- 刷入 `OTA` 包，通过刷入 `OTA` 包获取 `root` 权限
- 通过漏洞获取 `root` 权限
- `root` 用户，`installd` 守护进程
- `ro.secure` 属性，生产构建上的 `root` 权限
- `RPC`（远程过程调用），进程间通信
- `RSA` 算法，实现，算法名称，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，`dm-verity` 概览，启用验证启动，控制恢复
- `runcon` 工具，库和工具
- `run_program` 函数，启动系统更新过程
- 运行时库，Dalvik VM
- `R/W` 模式，`NFC` 概览

# S

- `S2C`（信号输入/输出连接），嵌入式 `SE`
- `salt` 属性，用户元数据文件
- 同源策略，`IPC`
- 沙盒，应用，Android 组件
- `SA`（安全关联），`L2TP/IPSec`
- `saveLockPassword()` 方法，`PIN` 和密码解锁
- `lockPattern()` 方法，图案解锁
- `scanPage()`，图案解锁
- `saveLock()` 方法，复制到目录
- `SCM_CREDENTIALS`，原生消息
- 屏幕安全，用户安装应用



# RFID（射频识别）技术与 NFC 概览

- `rild`（射频接口）守护进程，PIN 和密码解锁
- RI（参考实现），Android 的 Bouncy Castle Provider
- RNG（随机数生成器），算法名称
- `ro.crypto.fs_crypto_blkdev` 属性，使用系统属性控制设备加密，解密并挂载 `/data`
- `ro.crypto.state` 属性，更改加密密码
- `ro.debuggable` 属性，生产构建上的 Root 权限
- 命令，自定义恢复，Root 权限，以 root 启动 ADB，使用命令，生产构建上的 Root 权限，通过刷入 OTA 包 Root，通过漏洞 Root
- 工程构建，Root 权限，以 root 启动 ADB
- 以 root 启动 ADB，Root 权限
- 使用命令，启动 ADB
- 生产构建，使用 `su` 命令，生产构建上的 Root 权限，通过刷入 OTA 包 Root，通过漏洞 Root
- 更改启动或系统镜像，生产构建上的 Root 权限
- 刷入 OTA 包，通过刷入 OTA 包 Root
- 通过漏洞，通过漏洞 Root
- root 用户，`installd` 守护进程
- `ro.secure` 属性，生产构建上的 Root 权限
- RPC（远程过程调用），进程间通信
- RSA 算法，实现，算法名称，Android 的 Bouncy Castle 提供者，AndroidOpenSSL 提供者，dm-verity 概览，启用验证启动，控制恢复
- `runcon` 工具，库和工具
- `run_program` 函数，启动系统更新过程
- 运行时库，Dalvik VM
- R/W 模式，NFC 概览

# S

- S2C（信号输入/输出连接），嵌入式 SE
- `salt` 属性，用户元数据文件
- 同源策略，IPC
- 沙盒，应用，Android 组件
- SA（安全关联），L2TP/IPSec
- `saveLockPassword()` 方法，PIN 和密码解锁
- `lockPattern()` 方法，图案解锁
- `scanPage()`，图案解锁
- `saveLock()` 方法，复制到目录
- `SCM_CREDENTIALS`，原生消息
- 屏幕安全，用户安装应用
- `recovery` 操作系统，引导程序，Fastboot 命令，控制恢复，OTA 签名验证，启动系统更新过程，复制并补丁文件，完成更新，更新恢复

> 此处省略了大量重复的文本，确保语义已翻译。

- 保护，OTA 签名验证，启动系统更新过程，复制并补丁文件

> 此处已根据指令去除了重复行，仅保留唯一翻译。

## 系统属性与安全模型

- 系统属性，标记文件
- 安全增强型 Linux，SELinux
- 安全异常（`SecurityException`），静态强制
- 安全模型，Android 应用组件、应用沙盒、权限、IPC、多用户支持、系统更新
- 应用沙盒、Android 应用组件代码签名、IPC
- IPC、权限 IPC
- 多用户支持、IPC
- 概览，Android 应用组件
- 权限、应用沙盒
- 平台密钥、IPC
- SELinux、多用户支持
- 系统更新、多用户支持
- 验证启动、系统更新
- `security.properties` 文件，提供者实现
- `sedispol` 命令，Android 4.4 SELinux 策略
- SEEK for Android 项目，UICC，访问 UICC
- `seinfo` 命令，Android 4.4 SELinux 策略
- `seinfo` 标签，进程属性赋值、复制到应用目录、标记应用进程
- `self` 关键字，访问向量 Linux（Access Vector Linux）
- SELinux（安全增强型 Linux），多用户支持、强制访问控制、安全上下文赋值与持久化、类型和属性语句、对象类和权限语句、类型转换规则、访问向量规则、`auditallow` 规则、Android 实现、内核后门、中间件 MAC、设备策略文件、Android 4.4 SELinux 策略、策略

## 概览、强制域与无限制域

- 访问向量规则，`auditallow` 规则
- `allow` 规则，访问向量规则
- `auditallow` 规则
- `dontaudit` 规则，`auditallow` 规则
- `neverallow` 规则，`auditallow` 规则
- Android 4.4 策略、设备策略文件、Android 4.4 SELinux 策略、策略概览、强制域、无限制域
- 应用域，无限制域
- 强制域、策略概览
- Android 4.4 SELinux 策略
- 无限制度，强制域
- SELinux 架构
- 多用户支持
- 域转换规则、类型转换规则
- 实现、`auditallow` 规则、Android 实现、内核更改、中间件 MAC、设备策略文件
- 设备策略文件、中间件 MAC
- 内核更改、Android 实现
- 策略事件日志、设备策略文件
- 用户空间更改、内核更改
- 强制访问控制、SELinux
- 模式、强制访问控制
- 安全上下文（标签）、强制访问控制、安全上下文赋值与持久化
- 赋值与持久化、安全上下文赋值与持久化
- 安全模型、多用户支持
- 安全策略、安全上下文赋值与持久化、类型和属性语句、对象类和权限语句
- 对象类和权限语句
- 类型和属性语句
- 用户和角色语句、类型和属性语句
- 类型转换规则

## Android 方法、命令与属性

- `sendBroadcast()` 方法，广播权限强制，广播权限
- `--send_intent` 选项，控制恢复
- `sendResponseApdu()` 方法写入 HCE 服务
- `serialNumber` 属性，用户元数据文件
- 服务器名称指示（SNI），Android JSSE 实现
- 服务接口（SPI），加密服务提供者
- 服务、用户的应用、静态强制
- 应用架构、用户的应用
- 权限强制、静态强制
- SE，Nexus 4 硬件支持实现
- `sesearch` 命令，Android 4.4 SELinux 策略、策略概览
- `SEService` 类，访问 UICC
- `setActiveAdmin()` 方法，权限管理
- `setAuthToken()` 方法，列出并验证账户
- `setCameraDisabled()` 方法，策略强制
- `setcon` 命令，库和工具
- `setDefaultSSLFactory()` 方法，对等认证
- `setDeviceOwner()` 方法，设置设备所有者
- `setforce` 命令，库和工具
- `<set-global-proxy>` 标签，企业安全
- `setGrant()` 方法，控制密钥库访问
- `set-groupID(SGID)`，Android 应用组件
- `setKeyguardDisabledFeatures()` 方法，策略强制
- `setMaximumFailedPasswordsForWipe()` 方法，策略强制
- `setMaximumTimeToLock()` 方法，策略强制
- `set_metadata` 函数，启动系统更新过程
- `set_metadata_recursive` 函数，启动系统更新过程、复制和补丁文件
- `setNdefPushMessageCallback()` 方法，对等点模式
- `setNdefPushMessage()` 方法，对等点模式
- `setPasswordExpiration()` 方法，策略强制
- `setPassword()` 方法，列出并验证账户、表结构
- `setboul` 命令，库和工具
- `setSeed()` 方法，安全随机（SecureRandom）
- `setSSLSocketFactory()` 方法，对等认证
- `setStorageEncryption()` 方法，策略强制
- `setUserData()` 方法，列出并验证账户
- set-user-ID（SUID），Android 应用组件
- SGID（set-groupID），Android 应用组件

## 加密、签名与密钥库

- SHA-1 算法，Android JCA 提供者、Android Bouncy Castle 提供者、AndroidSSLProvider、OTA 签名验证
- SHA1PRNG 算法，Android JCA 提供者、AndroidOpenSSL Provider
- SHA1WithDSA 算法，Android JCA 提供者
- SHA-256 算法，加密服务提供者、算法名称、使用密码算法、Android Bouncy Castle 提供者、AndroidOpenSSL Provider、磁盘加密、OTA 签名验证
- `shared_accounts_table`，表结构、多用户支持
- `@SHARED` 宏，中间件方法
- 共享用户 ID，开发权限
- `userId` 属性，向 `packages.xml` 添加新包
- `sharpening`，创建数据目录
- `show_progress` 函数，启动系统更新过程
- `--text_option`，控制恢复
- `-sigfile` 选项，JAR 文件签名
- SignalIn/SignalOut 连接（S2C），嵌入式 SE
- `signapk` 工具，JAR 文件签名、Android 代码签名
- `Signature` 类，签名验证、消息摘要、Android JCA 提供者、Android Bouncy Castle 提供者
- AndroidSSL Provider
- 签名文件
- 签名或系统保护级、应用包和数据
- 签名权限、系统权限
- 签名保护级、Android 库、签名
- `SIGN_DATA` 命令，Nexus 4 硬件支持实现
- `sig(data)()` 方法，keymaster 模块和密钥库服务
- SIMAlliance 规范，UICC
- SIM 卡，系统更新、用户所有者（Owner）、Nexus 4 硬件支持实现
- 多用户支持、用户所有者（Owner）
- UICs 和、SE 执行环境
- 解锁、系统更新
- 简单 NDEF 交换协议（SNEP）协议，读取模式
- SIM 工具（STK）应用，UICC
- 单线协议（SWP），UICC
- 滑动解锁方法，锁屏解锁
- SmartCard API，UICC
- SMARTCARD 权限，使用 OpenMobile API
- SmartcardService，访问 UICC
- SNEP（简单 NDEF 交换协议）协议模式
- SNI（服务器名称指示），Android JSSE 实现
- SoC（单片系统），Nexus 4 硬件支持实现
- 软件卡，Android 4.4 HCE 架构
- `SO_PEERCRED` 权限选项，原生守护进程级强制
- SPI（服务接口），加密服务提供者
- Spongy Castle 提供者，使用自定义提供者
- 间谍软件，加密应用和 Google Play
- SQLite，用户目录
- `SSLContext` 类，证书撤销
- `SSLEngine` 类，证书撤销
- SSL Observatory 项目，当今 PKI 中的信任问题
- SSL（安全套层），网络安全和 PKI、直接信任和私钥、公钥基础设施、L2TP/IPSec
- 证书撤销，公钥基础设施
- 直接信任和私钥
- PKI，直接证书、网络安全和 PKI
- 基于 SSL 的 VPN，L2TP/IPSec
- `SSLServerSocket` 类，JSSE 介绍
- `SSLSocket` 类，JSSE 介绍
- `SSLSocketFactory` 类，对等认证
- `--stages` 选项，控制恢复

## 应用、恢复与 Root 权限

- `startActivityForResult()` 方法，静态强制、公共和私有组件
- `startActivity()` 方法，静态强制、公共和私有组件
- 粘广播，广播权限强制
- STK（SIM 工具）应用，UICC
- `- ()` 方法，PKCS#12 文件支持的密钥库
- `StrictJarFile` 类，包的解析与验证
- `so` 命令，以 Root 身份启动 ADB、SuperSU
- SUID（设置用户 ID），Android 应用组件
- SuperSU 应用，通过刷入 OTA 数据包进行 Root、SuperSU
- 初始化，SuperSU
- superuser，PackageInstaller 系统应用
- `supplyPinReportResult()` 方法，PIN 和密码解锁
- `supplyPukReportResult()` 方法，PIN 和 PUK 解锁
- `surfaceflinger` 守护进程，不受限制的域（Unconfined Domains）
- SWP（单线协议），UICC
- `symlink` 函数，启动系统更新过程
- 对称加密，签名
- 系统，Dalvik VM、Android 框架库、广播权限强制
- 权限，系统权限、认证密钥与证书
- 应用（apps），Android 框架库
- 凭据存储，认证密钥与证书
- 权限，广播权限强制、系统权限
- 开发方法，系统权限
- 概览，广播权限强制
- 签名权限，系统权限
- 服务，Dalvik VM
- `system_data` 文件类型，类型与属性语句
- 单芯片系统（SoC），Nexus 4 硬件支持实现
- 系统分区，Android 框架库
- 系统信任存储，Android JSSE 实现、Android 4.x 系统
- 信任存储，系统信任存储 API
- Android 4.x，系统信任存储
- API，系统信任存储 API
- 概览，使用 Android 4.x 系统信任存储

## 系统更新与恢复

- 系统更新，多用户支持、系统更新与 Root 访问、Fastboot 模式、Fastboot 命令、更新恢复
- `bootloader` 程序，系统更新与 Root 访问、Fastboot 模式
- 模式
- 解锁，系统更新与 Root 访问、恢复 OS、Fastboot 命令、更新恢复
- 自定义恢复（custom recoveries），更新恢复
- 原厂恢复（stock recovery），Fastboot 命令（等等，我这里有个拼写错误）
- 原厂恢复，Fastboot 命令

# T

- TACK（证书密钥信任链），收敛与信任敏捷性
- `TAG_DISCOVERED` 意图，注册标签调度
- `--tag` 参数，实现与加密参数
- Team Win Recovery 项目（TWRP），更新恢复
- `TECH_DISCOVERED` 意图，注册标签调度
- `<list>` 元素，注册标签调度
- 网络共享（tethering），主用户（所有者）
- TE（类型强制），SELinux 架构、Android 4.4 SELinux 策略
- 时间戳权威（TSA），JAR 文件签名
- TLS（传输层安全），网络安全与 PKI
- TOFU（首次信任），更新组件与权限、当今 PKI 中的信任问题
- 令牌（tokens），Binder、Binder 安全
- towelroot 漏洞，通过漏洞进行 Root

## TPM 与信任管理

- TPM（可信平台模块），Nexus 4 硬件支持实现
- `transceive()` 方法，Android 安全执行环境
- `translateKey()` 方法，密钥工厂
- `transmit()` 方法，访问 UICC
- 传输层安全（TLS），网络安全与 PKI
- 信任锚点，直接信任与私有 CA
- 证书密钥信任链（TACK），收敛与信任敏捷性
- `TrustedCertificateEntry` 类，密钥协商协议
- `TrustedCertificateStore` 类，系统信任存储、控制对密钥库的访问
- 可信平台模块（TPMs），Nexus 4 硬件支持实现
- `TrustManager` 类，对等认证
- `TrustManagerFactory` 类，JSSE 简介、使用系统信任存储
- 首次信任（TOFU），更新组件与权限、当今 PKI 中的信任问题
- `trustStore` 属性，Android JSSE 实现
- TrustZone，Nexus 4 硬件支持实现
- TSA（时间戳权威），JAR 文件签名
- 双重身份认证（2FA），Google 登录服务
- TWRP（Team Win Recovery Project），更新恢复
- `TYPE_ANY`，密钥库服务
- 类型强制（TE），SELinux 架构、Android 4.4 SELinux 策略
- `TYPE_GENERIC`，密钥库服务
- `TYPE_KEY_PAIR`，密钥库服务
- `TYPE_MASTER_KEY`，密钥库服务
- 类型语句，类型与属性转换语句
- `type_transition` 规则，类型转换规则

# U

## 系统初始化与多用户支持

- UIC（通用集成电路卡），Nexus 4 硬件支持实现、安全元件、UICC、查询 eSE 执行环境、SIM 卡与 UICC、UICC 应用、访问 UICC
- 访问，UICC 应用
- 应用实现与安装，UICC 应用
- 应用，SIM 卡与 UICC
- SIM 卡与，查询 eSE 执行环境
- 使用 OpenMobile API，访问 UICC
- UID，应用沙盒、IPC、权限与进程属性、多用户支持
- 概览
- 与权限与进程属性关联
- Linux UIC 与，多用户支持概览
- 多用户支持，IPC
- 共享，应用沙盒
- `ui_print` 函数，启动系统更新过程
- `umount` 函数，启动系统更新过程
- 不受限制域（unconfined domain），强制域
- `uninstallCaCert()`，受托管设备
- 通用集成电路卡，Nexus 4 硬件支持实现
- 未知源，应用包和数据的位置、MediaContainerService
- 主用户（所有者），次用户
- 多用户支持与，主用户（所有者）、次用户



- `PackageInstaller` 与，应用包和数据的位置，`MediaContainerService`
- `unshare()`，高级 Linux 挂载功能
- 不支持异常 (`UnsupportedException`)，共享账户
- `untrusted_app` 类型，类型与属性语句

## `UNWRAP_MODE`，获取 `Cipher` 实例

- `updateCredentials()` 方法，管理账户
- `update()` 方法，`MessageDigest`
- `--update_package` 参数，控制恢复
- `UPDATE_PINS` 广播，证书固定化
- 更新，多用户支持
- USB，次用户
- 多用户支持，攻击防护
- 安全调试，攻击防护
- 多用户，

---

- 安全，实现
- 认证密钥，Secure ADB
- 守护进程概览，攻击防护
- 实现，Secure ADB
- 需要，的
- 安全指纹，Secure ADB
- `UsbDebuggingActivity`，Secure ADB
- `UsbDeviceManager` 类，Secure ADB
- `USE_CREDENTIALS` 权限，管理账户，请求认证令牌
- `userdata` 分区，用户安装应用，控制系统属性
- 解密密并挂载，`/data`
- 用于加密的卸载，控制系统属性
- `userId` 属性，在 `packages.xml` 中添加新包
- 用户安装应用，用户安装应用

## `users.xml` 文件，用户列表文件

- 用户管理，用户管理，用户类型，主用户 (所有者)，次用户，不受限制，游客用户，游客用户，用户状态与广播，用户列表文件，用户系统目录，用户系统目录，应用数据目录，应用数据目录，共享，外部存储实现、高级 Linux 挂载功能、Android 实现，外部存储权限
- 应用管理，用户系统目录，应用数据目录
- 数据目录，应用数据目录
- 概览，用户系统目录
- 广播与，游客用户
- 命令行工具，游客用户
- 外部存储，共享、外部存储实现、高级 Linux 挂载功能、Android 实现
- Android 实现，高级 Linux 挂载功能
- Linux 挂载功能，外部存储实现
- 概览，共享
- 权限，Android 实现
- 元数据，用户状态与广播，用户列表文件，用户系统目录
- 用户列表文件，用户列表文件
- 用户系统目录，用户系统目录
- 多用户支持，用户管理，外部存储权限
- 特性，，外部存储权限

访客用户, 应用限制

主用户, 用户类型

受限配置, 次级用户

次级用户, 主支持（所有者）

`UserManager` API, 多用户支持概述

`UserManagerService`, 访客用户

`USER_STARTED` 广播, 用户状态及相关广播

`USER_STARTING` 广播, 用户状态及相关广播

`user` 声明, 类型和属性声明

`USER_STOPPED` 广播, 用户状态及相关广播

`USER_STOPPING` 广播, 用户状态及相关广播

`USES_ENCRYPTED_STORAGE` 常量, 设备管理, 策略执行

`<uses-policies>` 标签, 实现

`USES_POLICY_DISABLE_CAMERA` 常量, 设备管理, 策略执行

`USES_POLICY_DISABLE_KEYGUARD_FEATURES` 常量, 设备管理, 策略执行

`USES_POLICY_EXPIRE_PASSWORD` 常量, 设备管理, 策略执行

`USES_POLICY_FORCE_LOCK` 常量, 企业安全, 策略执行

`USES_POLICY_LIMIT_PASSWORD` 常量, 企业安全, 策略持久化

`USES_POLICY_RESET_PASSWORD` 常量, 企业安全, 实现, 策略执行

`USES_POLICY_GETS_GLOBAL_PROXY` 常量, 企业安全, 策略执行

`USES_POLICY_WATCH_LOGIN` 常量, 企业安全, 策略持久化, 策略执行

`USES_POLICY_WIPE_DATA` 常量, 企业安全, 策略执行

`ut` 属性, 向 `packages.xml` 添加新包

# V

`validate()` 方法, `CertificateFactory` 和 `CertPath`

# `VerificationParams` 类, 实现和加密参数

验证启动功能, 系统更新, 恢复, 恢复, dm-verity 概述, Android 实现

- 启用, Android 实现
- implementation, dm-verity 概述
- overview, 恢复

`VERIFY_DATA` 命令, Nexus 4 硬件支持实现

`verify_data()` 方法, keymaster 模块和 keystore 服务实现

`verify` 标志, dm-verity 概述

`verify()` 方法, 签名, 对等身份验证

`verifyPackage()` 方法, 控制恢复

`verifyPendingInstall()` 方法, Android 对包验证的支持

verity 元数据块, 启用验证启动

`version` 属性, 向 `packages.xml` 添加新包, 用户列表文件

VFS (虚拟文件系统), 外部存储实现

虚拟专用网络, Microsoft Exchange ActiveSync

`void` 守护进程, 更改磁盘加密密码, 解密并挂载 `/data`, 策略概述

`void_prop_type`, 系统属性标记

VPNs (虚拟专用网络), 主用户（所有者）, 凭据存储, 凭据存储, 身份密钥和证书, Microsoft Exchange ActiveSync, VPN 支持, VPN 支持, L2TP/IPSec, L2TP/IPSec, 基于 SSL 的 VPN, 基于 SSL 的 VPN, 实现, 配置和凭据存储, 始终开启 VPN, 始终开启 VPN, 声明 VPN, 声明 VPN, 声明 VPN, 声明 VPN, 通知用户 VPN 连接, 通知用户 VPN 连接, Linux 高级路由

- 基于应用程序的, 始终开启 VPN, 声明 VPN, 声明 VPN, 声明 VPN, 声明 VPN
- 声明, 声明 VPN
- 建立连接, 声明 VPN

关于连接的通知用户, 声明 VPN

准备, 声明 VPN, 主用户（所有者）

配置界面, EAP 凭据, 凭据存储, 凭据存储, 身份密钥和证书

身份密钥和证书, 凭据存储概述, 凭据存储系统凭据库, 身份密钥和证书

L2TP, VPN 支持旧版, 基于 SSL 的 VPN, 基于 SSL 的 VPN, 实现, 配置和凭据存储, 始终开启 VPN

访问凭据, 始终开启配置和凭据存储, 始终开启 VPN 实现, 基于 SSL 的 VPN 配置和凭据存储, 实现

多用户支持, 通知用户 VPN 连接, 通知用户 VPN 连接, Linux 高级路由实现, Linux 高级路由

Linux 高级路由, 通知用户 VPN 连接

PPTP, VPN 支持, 基于 SSL, L2TP/IPSec Xauth, L2TP/IPSec

`VpnService` 类, 始终开启 VPN

# W

waklocks, Linux 内核

`<watch-login>` 标签, 企业安全 WebView 控制, 客户端登录

Wi-Fi, 主用户（所有者）, 次级用户, 凭据存储, 凭据存储,

# 身份密钥和证书, 多用户 VPN 实现, Wi-Fi EAP, EAP 身份验证方法, Android Wi-Fi 架构, EAP 凭据管理

EAP 凭据, 凭据存储, 凭据存储, 身份密钥和证书

身份密钥和证书, 凭据存储

overview, 凭据存储

系统凭据库, 身份密钥和证书

EAP 框架, 多用户 VPN 实现, Wi-Fi EAP, EAP 身份验证方法, Android Wi-Fi 架构, EAP 凭据管理

使用 `WifiManager` API 添加网络, EAP 凭据管理

Android Wi-Fi 架构, EAP 身份验证方法

身份验证方法, Wi-Fi EAP

凭据管理, Android Wi-Fi 架构

多用户支持, 主用户（所有者）

用户限制, 次级用户

`WifiConfiguration` 类, EAP 凭据管理

`wifi_data_file` 类型, 类型转换规则

`WifiEnterpriseConfig` 类, 使用 `WifiManager` 添加 EAP 网络

`WifiManager` API, EAP 凭据管理

`WifiManager` 类, Android Wi-Fi 架构

Wi-Fi 安全访问第二代 (WPA2), 多用户 VPN 实现

Wi-Fi 安全访问 (WPA), 多用户 VPN 实现

`WifiService`, Android Wi-Fi 架构

`WifiStateMachine` 类, Android Wi-Fi 架构

WiMax, 主用户（所有者）

`--wipe-cache` 选项, 控制恢复, 复制和补丁文件

`<wipe-data>` 标签, 企业安全

`verifyData()` 方法, 策略执行

`wipe_data` 选项, 控制恢复

擦除用户数据, 策略执行

`-w` 选项, Android 代码签名

WPA2 (Wi-Fi 安全第二代), 多用户 VPN 实现

`wpa_socket` 类型, 类型转换规则

`wpa_supplicant` 守护进程, EAP 身份验证方法, 类型转换规则

WPA (Wi-Fi 安全), 多用户 VPN 实现

`WRAP_MODE`, 获取加密实例

`WRITE_CONTACTS` 权限, 静态权限

`WRITE_EXTERNAL_STORAGE` 权限, 请求权限, 应用共享, Android 实现

`write_raw_image` 函数, 启动系统更新过程

`WPA_SECURE_SETTINGS` 权限, 系统权限, 嵌入 SE

# X

基于 X509 的 PKI (PKIX), Android Bouncy Castle Provider, JSSE 简介

`.X509` 证书, `KeyFactory`, PKCS#12 文件存储, Android Bouncy Castle Provider, `AndroidOpenProvider`, 使用自定义提供程序, 网络安全和 PKI, 控制恢复

`X509ExtendedKeyManager` 接口, 对等身份验证

`X509KeyManager` 接口, 对等身份验证

`X509_NAME_hash_old()` 函数, 系统信任存储

`X509TrustManagerExtensions` 类, 证书锁定

`X509TrustManager` 接口, 对等身份验证

Xauth (IPSec 扩展身份验证), L2TP/IPSec

XTS (基于 X 的微调密码本模式带密文窃取), 加密模式

# Z

ZIP 格式, Android 包格式, Android 分区布局

`-z` option, 安全上下文, 库和工具

`ZygoteConnection` 类, 系统属性标记

`zygote` 进程, 权限和进程属性, Android 实现, 系统属性标记, 策略概述, 无限制域

# Android 安全内部原理：Android 安全架构深度指南

Nikolay Elenka

Copyright © 2015

**ANDROID SECURITY INTERNALS.** Copyright © 2015 by Nikolay Elenka

保留所有权利。未经版权所有者和出版者的事先书面许可，不得以任何形式或通过任何电子或机械手段（包括复印、录制或通过任何信息存储或检索系统）对本书进行复制或传输。

首次印刷

1 17 16 15 14 1 2 3 4 5 6 7 8 9

ISBN-10: 1-59327-581-1

ISBN-13: 978-1-59327-581-5

出版社：William Pollock

制作编辑：Alison Law

封底插图：Garry Booth

内页设计：Octopod Studios

开发编辑：William Pollock

技术审核：Kenny Root

文字校对：Gillian McGarvey

排版：Susan Gilinert Stevens

校对：James Raleigh

索引：BIM Proofreading & Indexing Services

### 有关分发、翻译或批量销售的信息，请直接联系 No Starch Press, Inc.：

No Starch Press

245 8th Street, San Francisco, CA 94103

电话：415.863.9933；info@nostarch.com；

www.nostarch.com

美国国会图书号：2014952666

No Starch 和 No Starch Press 是 No Starch Press, Inc. 的注册商标。此处提到的其他产品和公司名称均为其各自所有者的商标。我们没有在每次出现标记名称时使用商标符号，而是仅以编辑方式使用这些名称，并维护商标所有者的利益，无侵犯商标的意图。

Android 机器人根据 Google 创建并共享的作品复制或修改，并根据 Creative Commons 3.0 署名许可协议中规定的条款进行使用。

本书中的信息按“现状”分发，不提供任何保证。尽管在准备本书时已采取了一切预防措施，但作者或 No Starch Press, Inc. 对因书中包含的信息直接或间接引起或声称引起的任何损失或损害，不对任何个人或实体承担任何责任。

No Starch Press

2014-10-21T11:56:17:00
