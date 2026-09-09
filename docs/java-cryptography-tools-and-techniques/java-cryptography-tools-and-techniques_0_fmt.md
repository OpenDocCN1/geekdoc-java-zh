
# Java 加密：工具与技术

本书可在 [`leanpub.com/javacryptotoolsandtech`](http://leanpub.com/javacryptotoolsandtech) 购买

此版本出版于 2023-06-13

![出版者标志](img/leanpub-logo.png)

这是一本来自 [Leanpub](https://leanpub.com) 的书籍。Leanpub 通过精益出版流程为作者和出版者赋能。[精益出版](https://leanpub.com/manifesto) 是使用轻量级工具和多次迭代来出版正在开发中的电子书，以获取读者反馈，不断调整直到获得正确的书籍，并在一旦成功后建立影响力。

© 2017 - 2023 David Hook 和 Jon Eaves

## 目录

## 指南

1. 开始阅读

## 致谢

作者感谢 Peter Grant、Stephen Farrugia 和 Megan Woods 审阅了本书内容。

作者还感谢 Christoffer Sawicki、Sree Harsha Totakura 和 Alexander Railean 报告了出版书中错误和歧义之处。这些反馈帮助为所有人完善了这本书。

David 还想感谢他的妻子 Janine 和儿子 Lewis 的支持，并感谢猫 Hamlet（那只披着皮毛的原生小密码学家）和狗 Ophelia 的持续关注（也许可能不是密码学家，但对她自己认为在做的事情非常有热情）。你们一直是灵感和支持的源源泉，谢谢！

Jon 想要感谢他的妻子 Jo 的支持，她不仅支持这本书，还支持他在所有事务上的工作。此外，Jon 还想感谢 David 卓越的友谊、支持和指导，因为如果没有他对 `Bouncy Castle` 的勤勉管理，加密社区将因此贫乏许多。

## 引言

*“在知道如何遵守规则之前，违反规则是不够明智的。”*

– T. S. Eliot

我们之前编写关于 Java、`Bouncy Castle` 以及它如何触及加密世界的书籍尝试现在已经过去十多年了。

从那时起，发生了许多变化，Java 的 `Bouncy Castle` API 版本经过了两次 `FIPS 140-2` 认证，该项目已从一个兼业爱好转变为现在有一个小组在全职工作并支持的项目。API set 已经扩展，增加了如 `Time Stamp Protocol`（时间戳协议）、`TLS` 甚至最近的 `JSSE` 提供者。当时处于尖端的 `Java 1.5` 已经结束了生命，而像 `SHA-1` 这样的骨干算法在研究和技术上都已被超越。甚至是许多我们目前认为是安全的算法，现在其密钥大小也急剧增加，即便如此，在量子计算机出现后它们仍然可能变得过时。

因此，我们有些工作需要追赶，而这本书正是尝试做到这一点。除了处理 `Bouncy Castle` API 的更新和增强外，我们还尝试提供这些 API 所基于的一些原始材料和标准。我们这样做是因为，掌握实现背后的背景材料也是重要的。我们大多数人在“实一线”面临的最大问题是生成消息并与其他已经部署的系统进行通信；鉴于此，了解他们应该实现什么，以及有哪些选项或差异，当你面对需要找出你处理的某个黑盒系统到底期待什么时，将会有很大帮助。

### 关于书的一些话

如果你是这个领域的新手，并从这本书开始，请先花时间阅读附录 A。它描述了一种名为 `ASN.1` 的数据描述语言，其起源追溯到 20 世纪 80 年代——那是计算史上一个有趣的时代，因为过去如果消息比需要的多一个字节我们就会陷入恐慌。`ASN.1` 也反映了这种“恐慌”，并被用于定义加密协议中使用的各种结构的编码。因此，书中随处都有对 `ASN.1` 的引用，了解它究竟是什么的会让内容变得更容易理解。

### 关于软件本身的几句话

`Bouncy Castle` 项目自 1999 年以来一直运行，并于 2000 年发布了正式版本。虽然 `Bouncy Castle` 慈善机构和加密研讨会的成立意味着人们终于可以全职投入 API 工作，但尽管如此，我们的经验教给我们的一点是：错误是不可避免的。这些可能是我们工作中的错误、描述算法的文档中的错误、协议规范中的错误，以及我们或其他用户解释上的错误。在某些情况下，“错误”可能是完全无法预见的，因为对攻击的发现可能会使之前被认为是安全的算法或协议，下降到仅类似于你在飞艇侧面喷涂秘密并让其飞越国家体育赛场时所能预期的安全水平。这类事情需要持续的警惕。

所有这些事情都会影响我们所提供的库的安全性和兼容性。如果你打算在这个领域工作，请在至少了解你将如何升级的情况下不要部署东西，因为你很可能需要这样做！虽然指责 `NIST`、`IETF`、某些公司或互联网上的“老家伙”对某个安全问题可以提供暂时的缓解，但如果你无法部署补丁，这对你、你的用户或他们的数据没有任何帮助。

最后，请考虑通过 `Keyfactor` (https://www.keyfactor.com/platform/bouncy-castle-support/) 获取支持合同。了解你的补丁来源是有益的，请支持我们，我们将一直在这里为你提供支持！

本章将介绍 Java 中使用的加密 API 架构，以及构建在加密 API 之上的用于 CMS/SMIME/OpenPGP 的 Bouncy Castle API 架构。文中将提供基础安装说明，并讨论了 `BC FIPS` 认证版 API 与普通发行版之间的差异。此外，还将提供适用于所有 API 的随机数使用注意事项，并探讨“安全位”（bits of security）对应用程序和算法的意义。

# Java 提供者架构

与 Java 加密体系（`JCA`）相关的提供者架构（Provider Architecture）为 JVM 中的一系列安全服务提供了基础。这些服务现在包括 Java 安全套接扩展（`JSSE`），它提供了对安全套接层（SSL）和传输层安全（TLS）实现的访问；Java 通用安全服务（`JGSS`）API 以及简单身份验证和安全层（SASL）API。你还会看到对 Java 加密扩展（`JCE`）的引用，虽然最初（Java 1.4 之前）它是与 `JCA` 分开捆绑的，但除了少数例外外，现在大多数情况下将其视为 `JCA` 的一部分会更好。`JCA` 与 `JCE` 之间这种区分具有意义的情况之一是提供者签名（provider signing），我们稍后会详细介绍。

基础层在提供者架构中通过一组服务类来指定，这些类暴露给开发者，以便提供与已安装的服务提供者交互的统一接口。服务类通过调用在各种服务提供者接口（`SPI`）中定义的方法来提供功能，这些方法是由实际提供者中定义的对象实现的，这些提供者要么随 JVM 一带，要么由 Bouncy Castle 等其他供应商提供。

![通过 Java 加密架构调用的提供者块视图](img/chapter1----JCADiag.png)

通过 Java 加密架构调用的提供者块视图

提供者架构提供的第一点是，将应用程序开发者通常调用的内容（例如属于 `java.security.Signature` 或 `javax.crypto.Cipher` 的方法）与加密服务提供者（如 Bouncy Castle）实际实现的内容进行分离。例如，从开发者的角度来看，创建一个加密器看起来如下：

```
Cipher c = Cipher.getInstance("Blowfish/CBC/PKCS5Padding");
```

但 Blowfish 加密服务的实现者实际上会扩展 `javax.crypto.CipherSpi` 类，正是这个服务提供者接口（`SPI`）对象被封装在 `Cipher` 对象内部，并提供加密器相关的实际工作部分。

提供者架构提供的第二点是允许应用程序部署者决定使用特定算法的哪种供应商实现。这可以通过依赖提供者优先级（provider precedence）来实现，当像示例中调用特定服务的 `getInstance()` 方法时就是如此。你也可以通过指定提供者名称来要求使用 `getInstance()` 创建的加密服务对象所包含的 SPI 必须来自特定的提供者：

```
Cipher c = Cipher.getInstance("Blowfish/CBC/PKCS5Padding", "BC");
```

或者对于 Java 1.5 及更高版本，通过传递实际的提供者对象：

```
Cipher c = Cipher.getInstance(
                "Blowfish/CBC/PKCS5Padding", new BouncyCastleProvider());
```

## 提供者优先级的工作原理

在没有显式指定提供者的情况下，`JCA` 依赖提供者优先级来确定创建 SPI。

你可以通过以下示例看到这种用法：

```
 1 /**
 2  * 一个简单的应用程序，演示了提供者优先级对
 3  * JVM 返回内容的影响。
 4  */
 5 public class PrecedenceDemo
 6 {
 7     public static void main(String[] args)
 8         throws Exception
 9     {
10         // 将 BC 添加到优先级列表的末尾
11         Security.addProvider(new BouncyCastleProvider());
12 
13         System.out.println(MessageDigest.getInstance("SHA1")
14                                         .getProvider().getName());
15 
16         System.out.println(MessageDigest.getInstance("SHA1", "BC")
17                                         .getProvider().getName());
18     }
19 }
```

如果你编译并运行该示例（假设是标准的 Java 安装），你应该看到如下输出：

```
SUN
BC
```

正如代码注释所示，`addProvider()` 方法将提供者添加到优先级列表的末尾，因此默认的 SHA-1 实现来自 `SUN` 提供者，而不是 Bouncy Castle。

当 JVM 启动时，已安装提供者的优先级由 JVM JDK `java.security` 文件中的优先级表决定。如果你查看的是 Java 1.8 及之前的版本，可以在 `$JAVA_HOME/jre/lib/security` 中找到 `java.security` 文件；对于 Java 1.9 及更高版本，文件位于 `$JAVA_HOME/conf/security`。

## 提供者签名意味着什么？

你可能也见过关于签名提供者（signed providers）的引用。许多 JVM 要求任何加密或密钥交换服务的提供者必须经过 JCE 签名证书的签名。某些（如 OpenJDK 项目产生的）不需要，但由 Oracle 和 IBM 等机构产生的仍然需要。

如果提供者没有被正确签名，在要求提供者签名的 JVM 中将拒绝使用该提供者的任何 JCE 功能（注意，这不包括签名和消息摘要）。在大多数情况下，这并不需要担心，因为构建自己的提供者是不常的，但如果你确实要这样做，就需要申请 JCE 签名证书。在我们 Bouncy Castle 的情况下，我们已经申请了签名证书，并使用 Oracle 颁发的证书，这使得普通的 Bouncy Castle 提供者和 Bouncy Castle FIPS 提供者都能与标准 JVM 工作。

注意：JCE 签名证书与普通的代码签名证书完全不同。在需要的情况下，你需要按照随 Java 发行版附带的文档《如何在 Java 加密架构中实现提供者》中“获取代码签名证书”部分的描述进行操作。

## 管辖策略文件（Jurisdiction Policy Files）

与需要签名提供者一样，某些 JVM（例如 Oracle 和 IBM 的）的 JCE 实现对算法和密钥大小也有限制。这些限制是由管辖策略文件（Jurisdiction Policy files）强制的。假设你需要比这些限制更大的密钥，如果你在 Java 1.9 之前的 JVM 上运行，可能需要安装无限制策略文件（从 Java 1.9 开始，管辖策略文件的默认变为无限制）。

你通常可以在下载 JDK/JRE 的同一个地方找到无限制策略文件。通常位于名为“Unlimited Strength Jurisdiction Policy Files”的链接处。下载通常是一个 ZIP 文件，如果合法可以下载，你应该下载并解压它。你会在 ZIP 中看到几个 jar 文件和一个 README。按照说明操作即可准备就绪。如果你使用包管理器（如 `apt`）安装 JDK/JRE，你通常会发现也有一个包含无限制策略文件的包可以安装。

在你的开发 `JVM` 以及与生产环境中操作相关的任何 `JVM` 中都安装无限制策略文件（unrestricted policy files）是非常重要的。在 Linux 或其他 Unix 变体上，这通常意味着你需要 root 权限，或者需要拥有 root 权限的人员来安装这些策略文件。这在 Windows 上尤为重要，因为常规的 JDK 安装通常会安装两个独立的 JVM —— 一个用于 JDK，另一个用于通用的 Java 运行时。在这种情况下，你需要确保这两个 JVM 中都安装了策略文件。

在 Java 1.5 之后，测试策略文件是否存在的最简单方法是使用 Java 工具 `$JAVA_HOME/bin/jrunscript`：

```
jrunscript -e 'print (javax.crypto.Cipher.getMaxAllowedKeyLength("AES") >= 256);'
```

如果你尝试在 Java 1.5 或更早版本上执行此操作，你需要编写一个小型应用程序。以下代码通常可以完成任务：

```
 1 /**
 2  * 一个用于检查无限制策略文件的简单应用程序。
 3  */
 4 public class PolicyFileCheck
 5 {
 6     public static void main(String[] args)
 7         throws NoSuchAlgorithmException
 8     {
 9         try
10         {
11             Cipher cipher = Cipher.getInstance("Blowfish/ECB/NoPadding", "BC");
12 
13             cipher.init(Cipher.ENCRYPT_MODE,
14                     new SecretKeySpec(new byte[32], "Blowfish"));
15 
16             System.out.print("true");
17         }
18         catch (NoSuchAlgorithmException e)
19         {
20             throw e;
21         }
22         catch (Exception e)
23         {
24             System.out.print("false");
25         }
26     }
 27 }
```

上述两种方法都旨在根据是否存在无限制策略文件来显示单个“true”或“false”，尽管如果不存在 `Blowfish` 算法，第二种方法也会抛出 `NoSuchAlgorithmException`。在 Blowfish 不存在的极少数情况下，你需要将算法选择更改为其他可用且代表你实际计划使用的算法。

### 标准提供者集合

Java 1.4 默认有五个提供者：标准的 JCA 提供者、一个 JSSE 提供者、一个 RSA 签名提供者、一个 JCE SPI 提供者（用于加密算法、MAC 和密钥协商算法）以及一个 JGSS 的提供者。

从 Java 1.9 开始，现在有十二个。所有以前的提供者，加上椭圆曲线（Elliptic Curve）、XML 签名、LDAP、简单身份验证和安全层（SASL - 有两个）、用于智能卡的 PC/SC 提供者，以及用于硬件安全模块（HSMs）的 PKCS11 提供者。

你可能看到的具体将取决于你查看的是哪个版本的 `JVM` 以及哪个发行版。我们将在下一节中看到，通过少量的代码，就可以更清晰地了解默认可用的内容。

### 检查提供者及其能力

可用的提供者也可以标准的 Java API 访问。以下程序显示了 Java 运行时安装的提供者列表，并将它们的名称和“info”字符串作为输出。

```
 1 /**
 2  * 用于列出已安装提供者及其可用信息的简单应用程序。
 3  */
 4 public class ListProviders
 5 {
 6     public static void main(String[] args)
 7     {
 8         Provider[] installedProvs = Security.getProviders();
 9 
10         for (int i = 0; i != installedProvs.length; i++)
11         {
12             System.out.print(installedProvs[i].getName());
13             System.out.print(": ");
14             System.out.print(installedProvs[i].getInfo());
15             System.out.println();
16         }
17     }
 18 }
```

通过显示每个提供者携带的查找表，也可以获取提供者所实现的算法的“人类可读”列表。以下程序将打印出可用算法，以及可能存在的别名以及这些别名解析到的算法。



```
/**
 * 用于列出提供者能力（包括别名名称）
 * 的简单应用程序。
 * <pre>
 *     usage: chapter1.ListProviderCapabilities provider_name
 * </pre>
 */
public class ListProviderCapabilities
{
    public static void main(String[] args)
    {
        if (args.length != 1)
        {
            System.err.println(
                "usage: chapter1.ListProviderCapabilities provider_name");
            System.exit(1);
        }

        Provider provider = Security.getProvider(args[0]);

        if (provider != null)
        {
            for (Iterator it = provider.keySet().iterator(); it.hasNext();)
            {
                String entry = (String)it.next();
                boolean isAlias = false;

                // 别名项引用另一个条目
                if (entry.startsWith("Alg.Alias"))
                {
                    isAlias = true;
                    entry = entry.substring("Alg.Alias".length() + 1);
                }

                String serviceName = entry.substring(0, entry.indexOf('.'));
                String name = entry.substring(serviceName.length() + 1);

                if (isAlias)
                {
                    System.out.print(serviceName + ": " + name);
                    System.out.println(" (alias for " + provider.get("Alg.Alias." + entry) + ")");
                }
                else
                {
                    System.out.println(serviceName + ": " + name);
                }
            }
        }
        else
        {
            System.err.println("provider " + args[0] + " not found");
            System.exit(1);
        }
    }
}
```

## Bouncy Castle API 架构

Bouncy Castle 最初作为一个支持 J2ME 平台加密的项目开发的。在整合基础 API 后，显然可以使用这些组件构建一个支持 JCA 和 JCE 描述的提供者架构的高级 API。

随着项目的进展，显然还需要支持如 CMS、S/MIME 和 X.509 证书生成等更高级别的 API。

对于高级 API 有两种尝试。第一次尝试与 BC 提供者和 JCA 密耦合。第二次尝试（从 BC 1.46 开始）引入了提供不同 API 所需“粗粒操作”的接口。与基础提供者/底层划分相结合，使得不同 API 的布局如下所示。

![Bouncy Castle API 的高层布局 (FIPS 和通用)](img/chapter1----BCArchDiag.png)

Bouncy Castle API 的高层布局 (FIPS 和通用)

分层方法使得两种情况成为可能：程序可以使用轻量级 API 编写，因此 BC 提供者不再是强制性的；而且虽然图没有没有这一点，但可以使用来自不同供应商的其他 JCA/JCE 提供者，在必要时甚至可以使用多个提供者。因此，在许多情况下，BC API 在 HSM 中的运行效果与使用 BC Provider 一样良好。

### BC Core API

BC 核心 API 的主体位于 `org.bouncycastle.crypto` 包中，传统上这被描述为轻量级（light-weight）API。在今天将其描述为轻量级库可能看起来很奇怪（坦白地说，在 17 年之后，虽然它并不算臃肿，但已经变得相当大），该库最初的设计初衷是作为一种可以轻松子集并在小型设备上运行的。在早期，大多数情况下，甚至方法参数都没有经过校验。在大多数设备上，并没有足够的空间来实现此类“奢侈”功能。

轻量级库旨在提供一种“代数”，允许不同的加密算法和摘要与不同的编码、模式、MAC 和签名算法进行混合组合。需要指出的是，这种可以进行混合的方式其灵活性比防止产生不安全组合的实际需求要高得多。如果你打算使用轻量级 API，最好对你正在做什么有非常清楚的了解，或者实现一种源自可靠人员之手的算法/模式组合。

BC 核心 API 还包括一个 ASN.1 库，它提供了一系列支持不同协议元素的低级类，涵盖了从密钥编码到时间戳和数字签名的所有内容。ASN.1 库中的类被设计为可以在任何 BC 轻量级加密 API 可使用的平台上运行。

## BC Provider

BC 轻量级 API 提供了一个足够构建 JCA/JCE 提供者的足够构建块，因此，BC Provider 是由轻量级类构建的。这导致了轻量级 API 的某些部分向 JCA 的世界观倾斜，但它意味着 Bouncy Castle 的实际算法支持仍然集中在少数包中，BC Provider 的大部分部分实际上只是提供基础设施，以便让轻量级类通过核心 JCA 和 JCE 中定义的服务提供者接口（SPI）接口呈现出来，并使用 BC ASN.1 库来描述任何协议组件，例如需要为 JCA 生成的密钥编码和算法参数。

## 支持的 APIs

BC 加密 API 包含了对处理 CMS、PKCS#10、PKCS#12、S/MIME、OpenPGP、DTLS、TLS、OCSP、TSP、CMP、CRMF、DVCS、DANE、EST、PEM/OpenSSL、X.509 证书以及 X.509 属性证书的支持。除了 OpenPGP 的 API 外，这些 API 都是基于 ASN.1 构建的协议，并且它们提供了 BC 核心 ASN.1 库提供的包级对象无法满足的高级功能。

这些 API 构建在一组操作符接口之上，并设计为与 JCA/JCE 无关（agnostic），这意味着可以与任何提供者一起工作，并且也可以与不使用 JCE 或 JCA 的 Java 加密 API 使用。API 自带了针对 JCA/JCE 以及 BC 轻量级 API 实现的操作符。不同的操作符包可以通过与其相关的包名来区分，JCA/JCE 操作符都在以 `.jcajce` 结尾命名的包中，而 BC 轻量级包都在以 `.bc` 结尾命名的包中。

支持的 APIs 分为 4 个 jar 文件：

- `bcpkix` 集，包含所有与证书、CMS 和 TSP 相关的内容
- `bcpg` 集，包含 OpenPGP API
- `bcmail` 集，包含 S/MIME API
- `bctls` 集，包含 TLS API 和 BCJSSE 提供者

## Bouncy Castle FIPS 发行版

Bouncy Castle FIPS 发行版完全基于通过 FIPS 140-2 1 级认证的代码构建，其提供是为了允许人们为需要使用 FIPS 合规性或实际 FIPS 合规的环境开发应用程序。它们还被用作其他 FIPS 认证的基础，并为如通用标准（Common Criteria）之类的认证提供了基础。

### FIPS 发行版的区别

FIPS 发行版与常规 BC 发行版之间有两个主要区别。

第一个区别是常规 BC 库中等同于轻量级 API 的被隐藏了。这是因为 FIPS 标准要求底层支持被锁定，以便开发者的访问只能通过已知的路径进行，因此提供可以任意组装的轻量级 API 以执行高级功能的通用 BC 方法过于开放了。仍然存在一个低级 API，它与 BC FIPS 提供者具有类似的关系，但它比通用 BC API 中提供的要僵硬得多。

第二个区别是该发行版能够在两种模式下运行：仅批准模式（approved-only mode），即只有 FIPS 批准的算法可用；以及非批准模式（non-approved mode），可以使用提供者实现的完整算法集。

还有第三个较小的区别：并不是 Bouncy Castle 常规发行版中实现的所有内容在 FIPS 发行版中都是可用的。部分原因是由于最初的设计决策，在 FIPS 发行版中仅尝试支持在至少一个当前 IETF 标准中提到的算法。另一个考虑因素是，由于认证要求，向 FIPS 发行版中添加任何内容都要困难得多且昂贵。无论如何，如果你发现任何你认为应该包含的缺失内容，请务必告诉我们，但请理解需要耐心！

### BC FIPS 提供者

BCFIPS 提供者有 3 个变体，其中两个是因为 Android。主发行版是 BCFIPS，它位于 `org.bouncycastle` 包下，并针对特定的 JVM 版本进行了认证。下一个发行版位于 `org.stripycastle` 包下，并通常预装在 Android 设备上 —— 这一个通过 SCFIPS 名称访问。最后是一个可以作为应用程序 DEX 文件的 Android 版本。最后一个版本遵循 Roberto Tyley 的 `org.spongycastle` 约定。

目前，在使用 SCFDEX 提供者时，DEX 应用需要针对特定平台进行明确认证才能符合 FIPS 标准。SCFDEX 主要被那些需要证明自己运行在 FIPS 认证代码库上的开发者使用，而不是需要证明结果代码通过了 FIPS 认证。

Bouncy Castle FIPS 提供者名称和提供者类

| 名称 | 提供者类 | 平台 |
| --- | --- | --- |
| BCFIPS | `org.bouncycastle.jcajce.provider.BouncyCastleFipsProvider` | 通用 JVM |
| SCFIPS | `org.stripycastle.jcajce.provider.StripyCastleFipsProvider` | Android |
| SCFDEX | `org.spongycastle.jcajce.provider.SpongyCastleFipsProvider` | Android |

### BC FIPS 支持的 APIs

支持的 APIs 同样可用，尽管在编写时它们大部分依赖于提供者的使用。虽然 API 中不同操作接口的实现遵循通常的 `jcajce` 包约定，但并没有像常规 API 集那样的使用低级 API 的对应 `bc` 包实现。

对于 BCFIPS，4 个 jar 文件以 `bcpkix-fips`（PKIX API 集）、`bcmail-fips`（基于 PKIX 的 S/MIME API 集）、`bcpg-fips`（OpenPGP API 集）和 `bctls-fips`（TLS API 集）开头。

对于 SCFIPS，4 个 jar 文件以 `scpkix-fips`（PKIX API 集）、`scmail-fips`（基于 PKIX 的 S/MIME API 集）、`scpg-fips`（OpenPGP API 集）和 `sctls-fips`（TLS API 集）开头。

对于 SCFDEX，4 个 jar 包分别为 `scpkix-fipsdx`（PKIX API 集）、`scmail-fipsdx`（基于 PKIX 构建的 S/MIME API 集）、`scpg-fips`（OpenPGP API 集）和 `sctls-fipsdx`（TLS API 集）。

值得注意的是，这种情况与通用 API 的另一个不同之处在于，当 FIPS 提供者被配置为“仅批准（approved-only）”模式时，并非所有支持的 API 支持的算法都是可用的。

# 安装 Bouncy Castle

向 JVM 中安装加密提供者有两种方法。你可以在运行时手动添加它，方法是通过实际添加提供者，也可以通过将提供者对象传递给尝试创建的服务的 `getInstance()` 方法来基于“按需”的方式调用它。选择哪种方法取决于你的具体情况，但如果通过配置 Java 运行时来安装提供者，出现问题的概率会较低。

请注意，虽然以下说明在涉及特定提供者时是基于 BC 提供者的背景给出的，相同的说明（除提供者配置相关的说明外）同样适用于 BC FIPS 提供者以及大多数其他提供者。

## 静态安装

静态安装提供者的方法取决于你处理的是否 Java 1.9 之前的 JVM。

对于 Java 1.4 到 Java 1.8，你可以通过将其类名插入 `$JAVA_HOME/jre/lib/security` 中 `java.security` 文件的列表中来添加提供者。提供者列表是一系列格式为“security.provider.n”的条目，其中 n 是提供者的优先级数字，1 表示该提供者的优先级最高。在这种情况下，添加 Bouncy Castle 需要添加一行如下格式的配置：

```
security.provider.N=org.bouncycastle.jce.provider.BouncyCastleProvider
```

其中 N 代表你希望 BC 提供者拥有的优先级。如果你没有将 BC 提供者添加到列表末尾，请确保调整了其他提供者的值。此之后，你需要确保提供者在类路径上，最好放在 `$JAVA_HOME/jre/lib/ext` 目录下，这样它将始终由 JCA 信任的类加载器加载。

对于 Java 1.9 及更高版本，列表位于 `$JAVA_HOME/conf/security` 文件中。目前 BC 提供者不支持 jar 包的 `META-INF/service` 功能，因此需要按照之前的方式添加提供者，但要使用提供者的名称“BC”或“BCFIPS”添加到提供者列表中。

Java 1.9 不再支持 `$JAVA_HOME/jre/lib/ext`。在 Java 1.9 的情况下，你只需要确保 BC 包含在类路径中。

## 运行时安装

运行时使用提供者有两种方法。

第一方法是使用 `java.security.Security` —— 对于 BC 提供者，如下所示：

```
java.security.Security.addProvider(
             new org.bouncycastle.jce.provider.BouncyCastleProvider());
```

执行上述语句后，JVM 中的情况几乎与静态安装提供者发生的情况等效。消息摘要等服务可以通过使用提供者名称的 `getInstance()` 方法来访问。

使用第二种方法，将提供者对象传递到所请求的服务中，例如，要使用 BC 提供者为 Blowfish 创建 Cipher，你可以这样写：

```
Cipher c = Cipher.getInstance("Blowfish/ECB/NoPadding",
                                            new BouncyCastleProvider());
```

## 提供者配置

配置提供者有三种方法：

* 使用系统属性
* 向提供者的构造函数传递字符串
* 调用某些配置对象

不同的 Bouncy Castle 提供者（BC、BCFIPS 和 BCJSSE）都使用了这些方法。

### 配置 BC Provider

BC Provider 支持三个系统属性：

* `org.bouncycastle.asn1.allow_unsafe_integer`
  允许接受扩展的 ASN.1 整数。在这种情况下，扩展意味着符号位已通过整个字节进行编码。
* `org.bouncycastle.ec.disable_mqv`
  从提供者和轻量级 API 中移除 EC MQV 实现。
* `org.bouncycastle.dsa.FIPS186-2for1024bits`
  这是一个旧属性，允许使用 FIPS 186-2 中的算法生成 1024 位 DSA 密钥。

### 配置 BCFIPS Provider

BCFIPS Provider 支持通过字符串构造函数参数以及系统属性进行配置。

该提供者可以配置为创建特定形式的 DRBG，和/或在构造时为 DRBG 提供熵池。例如，要使用 `java.security` 文件条目为 BCFIPS 配置熵池，你需要如下所示写入条目：

```
org.bouncycastle.jcajce.provider.BouncyCastleFipsProvider C:HYBRID;ENABLE{All};
```

`HYBRID` 命令是导致熵池构建的关键字。该配置字符串也可以在运行时通过调用 `BouncyCastleFipsProvider` 构造函数并将配置字符串作为参数来传递，如下：

```
new BouncyCastleFipsProvider("C:HYBRID;ENABLE{All};")
```



BCFIPS Provider 还支持许多系统属性，包括 `org.bouncycastle.ec.disable_mqv` 和 `org.bouncycastle.dsa.FIPS186-2for1024bits`。

### 配置 BCJSSE Provider

类似于 BCFIPS Provider，BCJSSE Provider 也支持使用参数和系统属性进行配置。要将 BCJSSE 置于 FIPS 模式，也是通过构造函数的字符串参数实现的，因此对于静态安装的情况，`java.security` 中的赋值如下：

```
org.bouncycastle.jsse.provider.BouncyCastlesProvider fips:BCFIPS
```

注意在这种情况下使用了两个独立的设置。第一个 `fips` 开启了 BCJSSE 的 FIPS 模式，这意味着将使用符合 FIPS 标准的密码套和参数。第二个 `BCFIPS` 表示使用 BCFIPS Provider 提供加密服务。当你寻求 BCFIPS Provider 的 FIPS 合规性时，可以使用此配置。

## 基础故障排除

在配置了提供者、设置了策略文件并选择了安装提供者的方法后，你应该准备好使用 Bouncy Castle 提供者。然而，下节提供了一些常见问题的解决方案。

### 提供者未正确安装

如果你通过名称访问服务，可能会看到类似的内容（在此情况下提供者名称为“BC”）：

```
java.security.NoSuchProviderException: No such provider: BC
	at javax.crypto.Cipher.getInstance(Cipher.java:593)
```

在这种情况下，提供者没有被正确安装。如果你预期它是静态安装的，你需要检查 `java.security` 文件；否则，你需要确保执行预期的运行时安装代码在尝试调用提供者服务之前执行。

### 提供者未正确签名

如前所述，如果包含提供者的 jar 包没有正确签名，当尝试使用 JCE 功能时，JCE 将拒绝它。如果你看到：

```
java.lang.SecurityException: JCE cannot authenticate the provider BC
	at javax.crypto.Cipher.getInstance(Cipher.java:657)
	at javax.crypto.Cipher.getInstance(Cipher.java:596)
```

提供者 jar 包未签名，或者由于某种原因加载到了 JCE 不信任的类加载器中。如果发生这种情况，你需要检查提供者 jar 包已签名，并且可能需要检查类路径，以确保提供者 jar 包出现在系统类加载器可能信任的位置。

## JCE 策略文件问题

如果你看到类似下面的错误：

```
java.security.InvalidKeyException: Illegal key size or default parameters
	at javax.crypto.Cipher.checkCryptoPerm(Cipher.java:1026)
	at javax.crypto.Cipher.implInit(Cipher.java:801)
	at javax.crypto.Cipher.chooseProvider(Cipher.java:864)
	at javax.crypto.Cipher.init(Cipher.java:1249)
	at javax.crypto.Cipher.init(Cipher.java:1186)
```

或者以以下内容开头的异常堆栈：

```
java.lang.SecurityException: Unsupported keysize or algorithm parameters
```

如果你在 Java 1.8 之前的 JVM 上运行，这通常意味着为运行应用程序的 JVM 正确安装 JCE 的无限制管辖区策略文件，你应该下载并安装这些策略文件。如果你使用的是 Java 1.8 或更高版本，问题将由于 `lib/security/java.security` 文件中 `crypto.policy` 属性的值。如果你希望充分利用 BC 提供者，需要将该值设置为“unlimited”。从 Java 1.8 Update 161 开始，`crypto.policy` 的默认值为“unlimited”，之前的版本为“limited”。在 Java 1.9 及更高版本中，需要检查的文件是 `conf/security/java.security`，且 `crypto.policy` 的默认值为“unlimited”。

## 提供者似乎挂起

如果发生这种情况，你可能遇到了熵耗尽（entropy exhaustion）的情况，详情请参见下一节“关于熵的几点”。

### 关于熵的几点

对于像 Bouncy Castle 这样的纯软件提供者来说，熵生成是一个问题，主要原因是提供者无法自行生成熵，因此必须依赖外部熵源。

对于 Bouncy Castle，BC 和 BCFIPS 提供者都会使用 JVM 的熵源，除非提供了另一个源。数据随后将通过 DRBG（确定性随机数生成器）进行过滤。

JVM 使用的熵源会有所不同，例如在 Linux 上，它通常被设置为 `/dev/random`，这可能会导致阻塞。通常安装 `rng-tools` 或类似的等效工具可以解决这个问题，因为它还会暴露任何支持 RNG 生成的底层硬件，以用于为 `/dev/random` 提供种子。在某些虚拟环境中，硬件 RNG 可能永远不可用，在这种情况下，找到其他方法为你的 JVM 提供熵是非常重要的。这些方法取决于你所使用的环境。

### 从提供者获取 SecureRandom

BC 和 BCFIPS 提供者包含两个 SecureRandom 服务。

可以通过以下方式访问 `DEFAULT` 服务：

```
SecureRandom random = SecureRandom.getInstance("DEFAULT", "BC");
```

`DEFAULT` 服务适用于生成密钥、IV（初始化向量）和随机 nonce（随机数）。在内部，它处于预测抗性模式（prediction resistant mode），在处理每个请求之前都会重新种子。这确保了底层的 DRBG（默认基于 SHA-512）能够产生尽可能噪声的输出。

第二个服务是 `NonceAndIV` 服务。可以使用以下方式创建 `NonceAndIV` 服务：

```
SecureRandom random = SecureRandom.getInstance("NonceAndIV", "BC");
```

`NonceAndIV` 服务与 `DEFAULT` 服务的区别在于它只定期重新种子。这减轻了对熵源的压力，目前被认为用于 IV 和随机 nonce 是合适的，但它不满足生成密钥的种子要求。

### 手动构建 SecureRandom

你也可以在普通的 BC API 和 BCFIPS API 中手动构建符合 SP 800-90A [33] 风格 DRBG 的 SecureRandom。这允许对 nonce、类型、个性化数据甚至熵源进行自定义。

由于 FIPS 的要求，BC 和 BCFIPS API 的构建细节略有不同。在普通的 BC API 中，你可以如下所示构造基于哈希算法的 SecureRandom 对象：

```
SP800SecureRandom random =
        new SP800SecureRandom(new SecureRandom(), true)
                 .setPersonalizationString(
                       Strings.toByteArray("My Bouncy Castle SecureRandom"))
                 .buildHash(new SHA512Digest(), null, false);
```

注意在上述情况下，nonce 为 `null`，且预测抗性被设置为 `false`。最后一点意味着通常这会使 DRBG 不利于生成密钥，因为它在请求之间不会进行重新种子。对于密钥和私钥的生成，你通常希望将预测抗性设置为 `true`。

BC FIPS API 中的等效代码如下：

```
FipsDRBG.Builder rBuild =
       FipsDRBG.SHA512.fromEntropySource(new SecureRandom(), true)
                      .setPersonalizationString(
                           Strings.toByteArray("My Bouncy Castle SecureRandom"));

FipsSecureRandom random = rBuild.build(null, tv.predictionResistance());
```

在两种情况下，传递用于初始化的 SecureRandom 都不被直接使用，只使用了其 `generateSeed()` 方法。

## 为什么这很重要

拥有良好的熵源很重要，因为归根结底，它影响你创建的任何密钥的安全性，以及任何参数（如初始化向量）的真实随机性。

尽管如此，Unix 风格操作系统上的 JVM 通常配置 `/dev/random` 为默认值，当系统耗尽熵时，它通常会阻塞。还有一个额外的随机源 `/dev/urandom`（注意名称不同），它在熵耗尽时不会阻塞。

有些领域认为 `/dev/urandom` 可能足够了——但在本文写作时的事实是，如果你在使用 FIPS，`/dev/urandom` 至少不是。原因有两个：对大多数系统上已经进行的熵评估使用的是 `/dev/random`，以及一个简单的事实：生成糟糕的密钥实际上比没有密钥更没用——你最好等一下。是的，在加密私密信息时服务器阻塞的威胁是痛苦的，但与你开始使用低质量密钥加密内容导致客户端数据泄露可能发生的情况相比，那感觉就像是天堂里的永恒。

要做的第一件事是在可能的情况下安装硬件 RNG 支持，或者如果你使用的是暴露硬件 RNG 的虚拟环境，安装最接近硬件 RNG 支持的工具。

你可以做的第二件事是使用基于有效 DRBG 的熵池——普通的 BC 提供者默认使用此类，BC FIPS 提供者实际上期望熵源能跟上随机性请求，但允许配置熵池（详情见提供者配置部分）。

最后，如果你尝试从其他系统为你的 DRBG 提取熵，请记住 RFC 4086“安全随机性要求”[86]、SP 800-90B“用于随机位生成的熵源建议”[34] 的内容以及“黄金法则”：即使你从某处获取的值有 64 位，它也可能只代表几位的实际熵。

#### 安全位数

你将在不同的章节以及互联网上的其他文档中看到关于安全强度位数（bits of security strength）的引用。目前你看到的数值将来自 80、112、128、192 和 256 位。正如你可能想的那样，数字越大越好。

对于大多数算法而言，这些数字试图提供一种计算难度的衡量，或者对于理想的对称加密算法，提供暴力破解攻击的复杂度。如果某个算法的评级为 `2^80`，那么假设是执行对其的有效攻击需要 `2^80` 次操作。

随着计算机变得越来越快，像 `2^80` 这样的数字已不再代表它们曾经面临的挑战。如今，人们普遍认为应该使用安全强度至少为 112 位算法；如果预计应用程序处理的数据在 6 年后仍需要安全，则应使用更高的强度（128 位更高）。`SP 800-57 Part 1 (Revision 4)` 的第 5.6.2 节 [32] 讨论了选择用于应用程序算法时应考虑的因素。对于决策的另一种不同但相似的观点，还有欧盟网络和信息安全局（ENISA）发布的报告 [50]

### 总结

在本章中，我们查看了 `JCA/JCE` 的架构以及提供者优先级的工作原理。我们还查看了 `JCA/JCE` 的不同 `Bouncy Castle` 提供者的架构，以及如何安装和配置它们。此外，还查看了针对 `JSSE` 的 Bouncy Castle 提供者的 FIPS 和非 FIPS 配置。

我们还查看了一份可能发生的常见问题列表及其指示。希望这些内容足够让你上手并运行，以便你完成书中其余部分的示例。

最后，我们还查看了影响 Java 中加密提供者使用的一个细微的配置/设置问题。即用于密钥和私钥生成的可用随机数的质量。虽然高质量的随机数源是一个很大且显而易见的益处，但它非常重要。在 `FIPS` 提供者的情况下，由于最佳 RNG（随机数生成器）源可能会导致性能问题，请不要忘记检查硬件 RNG 支持。在不支持的情况下，不要忘记也可以配置 `BCFIPS` 提供者来使用熵池。

## 第 2 章：分组密码与流密码

本章介绍了用于通过对称密码进行加密的 `Java APIs`。你会看到使用对称密码加密数据的两种不同方法：一种基于“电子密码”（virtual code-books），另一种基于将消息与密码的密钥流混合。我们还将讨论基本模式的密码配置，以及密钥和其他参数的输入和生成。最后，我们将查看哪些内容可以方便在输入/输出流上使用密码。

### 基础知识

对称密码依赖于使用秘密密钥来加密数据。将密钥泄露给不应该拥有它的人，游戏就结束了。我们将在书的后面部分讨论交换密钥的方法，但由于对称密码为我们提供了处理大量数据加密所需的手段，在担心其他任何问题之前，先查看它们是值得的。

### 算法安全强度

经过适当分析，对称密码的安全强度以安全位（bits）来描述。

如今，如果你想确保安全，通常认为你的密码至少应该具有 112 位安全强度。`NIST` 目前推荐的两种对称密码 `AES` 和 `Triple-DES` 的估计安全强度所示在 `NIST SP 800-57` 的表 2 中 [32]。你可以从下方看到。

NIST 对称密码安全强度

| 算法 | 密钥大小 | 安全强度（位） |
| --- | --- | --- |
| 2 密钥 Triple-DES | 112 | <= 80 |
| 3 密钥 Triple-DES | 168 | 112 |
| AES | 128 | 128 |
| AES | 192 | 192 |
| AES | 256 | 256 |

理想情况下，对称密码对于给定密钥大小的安全强度应由所使用的密钥大小反映。从上表可以看出 `AES` 就是这样一种密码，但你从 `Triple-DES` 看出并非总是如此。如果你打算使用其他算法，值得检查文献，以确保你构思的密钥大小/算法组合准确反映了你认为应用程序所需的安全位。

#### 如何保住秘密

在进行任何涉及对称秘密密钥的操作之前，重要的是意识到“不告知”秘密密钥只是影响密钥有效寿命的因素之一。至少还有其他三个考虑因素需要留心中。

##### 密钥是如何生成的

密钥的质量取决于用于生成密钥的随机数据的熵。虽然找到一个能产生（例如）64 位的随机值生成器很棒，但如果这些位全为 1 或全为 0，那么就只有 1 位熵。猜一个这种方式生成的秘密密钥将非常容易。

##### 数据量和密钥的使用次数

尽管有其他考虑因素，通用的规则是最大块数约为 `2^32`。至少你应该计划在处理完总块数之前更换密钥。

##### 与密钥和密码模式相关的参数

大多数密码模式都涉及 nonce（随机数）和初始化向量（IV）的使用。在某些模式中（如 `GCM`），重用 IV 对安全可能是致命的。请明智地生成任何参数！这一切意味着什么？答案是确保在生成密钥时使用高质量的熵。

可能会返回任何内容。它将是 `AES`，但是否需要参数、一个 `IV`，甚至于某种模式对于你正在尝试的操作是安全的，无人能预知。

在流加密的情况下，你通常只会看到 `cipher_name`，因为流加密不包含关联的模式（modes）或填充（paddings）。

### 块加密

在“过去的好时光”，人们经常使用密码本（code-books）来加密消息，其中一个字符串会被替换为密码本指定的某些字符串。

从根本上说，块加密提供了一种动态生成此类密码本条目的机制，其替换是根据代表所用块加密位大小的位字符串完成的。

![加密模式下的基础块加密](img/chapter2----BasicBlockCipher.png)

加密模式下的基础块加密

显然，生成随机条目并没有什么用，因此块加密使用其初始化时的密钥来确保其生成的密码本条目是确定性的。我的意思是，一个代表加密器输入块的 b 位字符串始终将映射到虚拟密码本中相同（但可能不同的）对应的 b 位字符串。加密器的输入通过虚拟密码本进行映射，产生相应的输出。

附录 C 中有 Bouncy Castle 支持的块加密列表。

### 块模式

块加密的模式分为四类：基于块的模式、可用于流的模式、认证模式以及密钥封装（key wrapping）模式。我们将在本章剩余部分介绍基于块的模式和流模式。认证模式和密钥封装基于这些模式之上，我们将在第三章查看这些模式。

#### ECB 模式

电子密码本（ECB）模式是最简单的对称加密形式，正如该模式的名字所示，加密器简单是将一个位块映射到由密钥表示的虚拟密码本中的一个位块。加密器的加密/解密设置决定了操作产生的是密文还是明文。

这是一个在 ECB 模式下使用 `AES` 的基本示例。这可能是你在 JCE 中能做的最简单的事情，但它展示了 `Cipher` 类和 `SecretKeySpec` 类的使用。



## ECB 模式示例

```java
 1 /**
 2  * ECB 模式下 AES 的简单示例。
 3  */
 4 public class ECBShortExample
 5 {
 6     public static void main(String[] args)
 7         throws Exception
 8     {
 9         byte[] keyBytes = Hex.decode("000102030405060708090a0b0c0d0e0f");
10 
11         SecretKeySpec key = new SecretKeySpec(keyBytes, "AES");
12 
13         Cipher cipher = Cipher.getInstance("AES/ECB/NoPadding", "BC");
14 
15         byte[] input = Hex.decode("a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7");
16 
17         System.out.println("input    : " + Hex.toHexString(input));
18 
19         cipher.init(Cipher.ENCRYPT_MODE, key);
20 
21         byte[] output = cipher.doFinal(input);
22 
23         System.out.println("encrypted: " + Hex.toHexString(output));
24 
25         cipher.init(Cipher.DECRYPT_MODE, key);
26 
27         System.out.println("decrypted: "
28                             + Hex.toHexString(cipher.doFinal(output)));
29     }
 30 }
```

运行该示例应该产生以下输出：

```
input    : a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7
encrypted: c600a21491fbcfec368b5adf31c50881
decrypted: a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7
```

你可以看到消息非常短，尝试将赋值给 `input` 的消息替换为这里更长的消息：

```java
 byte[] input = Hex.decode("a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7"
                              + "a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7");
```

在这种情况下，你将看到此输出：

```
input    : a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7
encrypted: c600a21491fbcfec368b5adf31c50881c600a21491fbcfec368b5adf31c50881
```

## CBC 模式自动生成 IV 示例

下一个示例展示了如何为 CBC 模式自动生成 IV（初始化向量）。你会发现，任何需要使用 IV 的加密算法都支持类似的功能。

```java
 /**
 * A simple example of AES in CBC mode, with the Cipher generating IV.
 */
 public class CBCGenExample
 {
    public static void main(String[] args)
        throws Exception
    {
        byte[] keyBytes = Hex.decode("000102030405060708090a0b0c0d0e0f");

        SecretKeySpec key = new SecretKeySpec(keyBytes, "AES");

        Cipher cipher = Cipher.getInstance("AES/CBC/NoPadding", "BC");

        byte[] input = Hex.decode("a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7"
                                 + "a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7");

        System.out.println("input    : " + Hex.toHexString(input));

        cipher.init(Cipher.ENCRYPT_MODE, key);

        byte[] iv = cipher.getIV();

        byte[] output = cipher.doFinal(input);

        System.out.println("encrypted: " + Hex.toHexString(output));

        cipher.init(Cipher.DECRYPT_MODE, key, new IvParameterSpec(iv));

        System.out.println("decrypted: "
                            + Hex.toHexString(cipher.doFinal(output)));
    }
 }
```

如果你运行这个示例几次，你应该会看到加密输出在随机变化。

使用 `Cipher.getIV()` 返回的生成字节数组的替代方案是使用 `Cipher.getParameters()`，它返回一个 `AlgorithmParameters` 对象。你可以像上一个示例中使用 `IvParameterSpec` 一样使用它，通过参考以下代码片段来修改示例。这段代码替换了上述示例中第 20 行到第 28 行的内容：

```java
 cipher.init(Cipher.ENCRYPT_MODE, key);

 AlgorithmParameters ivParams = cipher.getParameters();

 byte[] output = cipher.doFinal(input);

 System.out.println("encrypted: " + Hex.toHexString(output));

 cipher.init(Cipher.DECRYPT_MODE, key, ivParams);
```

在两个自动生成 IV 的示例中，我们使用了提供程序默认的内部 `SecureRandom` 来生成 IV。在需要时，也可以在调用 `init()` 方法时向 `Cipher` 传递一个 `SecureRandom`，以便使用你自己的随机数源。例如，你可能会写：

```java
SecureRandom myRandom = ...

Cipher.init(Cipher.ENCRYPT_MODE, key, myRandom);
```

其中 `myRandom` 是你专门从 DRBG 构造函数构建的 `SecureRandom`。

## 填充

分组加密的基本形式（当仍以密码簿形式使用如 ECB 或作为 CBC 加密的基础）只能处理与块大小对齐的数据。显然，你想要加密的数据并不总是恰好是块大小的倍数，因此提出了一些用于向数据中添加填充的程序。

所有的填充机制（偶尔的零填充除外）在原始明文块对齐时都会添加一个额外的填充块。在这种情况下，填充的额外块将是一个字节长度等于加密器块大小的字节字符串（例如 AES 为 16，Triple-DES 为 8）。

除了 BC FIPS 提供程序不支持的零字节填充外，Bouncy Castle 提供程序支持以下填充机制。

### ISO7816-4 填充

这种填充定义在 `ISO7816-4` 中。第一个填充字节的值为 0x80，其余填充由零字节组成。通过填充字符串“ISO7816-4Padding”设置。

### ISO10126-2 填充

这种填充定义在 `ISO10126-2` 中。填充的最后一个字节是填充字节的数量，其余的填充字节由随机数据组成。通过填充字符串“ISO10126-2Padding”设置。

### PKCS#5/PKCS#7 填充

PKCS#5/PKCS#7 填充最初定义在 PKCS #5 [129] 中，并在 PKCS #7 [76] 中进行了进一步修订。明文用一个表示为了填充一个块所需的字节数的字节字符串进行填充。例如，对于像 AES 这种 16 字节块的加密器，比下一个块边界短 5 字节的明文将用值为‘5’的字节填充。通过填充字符串“PKCS5Padding”或“PKCS7Padding”设置。

### TBC 填充

尾位取反（TBC）填充根据最后一位的值添加。如果位为 0，则添加一串 1；如果位为 1，则添加一串 0。通过填充字符串“TBCPadding”设置。

### X9.23 填充

这种填充定义在 `X9.3` 中。由于与 PKCS#5/PKCS#7 类似，填充的最后一个字节是填充字节的数量，但与 PKCS#5/PKCS#7 不同，其他字节是零或由随机数据组成。通过填充字符串“X923Padding”设置。

### 零字节填充

永远不要在这种情况下使用它，因为 BC FIPS 提供程序不支持。当明文以零结尾时会添加零字节填充。通过填充字符串“ZeroBytePadding”设置。

在提供程序方面，PKCS#5/PKCS#7 是最常见的，通常被称为“PKCS5”，有时被称为“PKCS7”。

你可以从加密数据中看到填充的存在，因为它比原始输入长并且是块对齐。

## 密文窃取

如果你有处理任意长度数据的需求（有一个限制），可以使用密文窃取，或 `CTS`。`CTS` 操作首次在 `RFC 2040` [74] 中作为 RFC 发布，并在 `SP 800-38A` 的附录 [25] 中进行了进一步扩展。它被视为 `CBC` 模式的一种特殊情况，对于 Java 而言，我们将其视为填充机制。虽然 `CTS` 仅适用于大于一个块的消息，但它确实提供了一种使用 `CBC` 模式生成密文的方便方法，生成的密文长度与原始明文完全一致。

`SP 800-38A` 的附录定义了三种方法，其中 `CS3` 与 `RFC 2040` 中定义的相同。以下示例是该模式的，在提供程序中可以引用为 `CS3Padding` 或 `CTSPadding`。

```java
 1 /**
 2  * 一个使用 CBC 模式并配合密文窃取的 AES 简单示例。
 3  */
 4 public class CTSExample
 5 {
 6     public static void main(String[] args)
 7         throws Exception
 8     {
 9         byte[] keyBytes = Hex.decode("000102030405060708090a0b0c0d0e0f");
10 
11         SecretKeySpec key = new SecretKeySpec(keyBytes, "AES");
12 
13         Cipher cipher = Cipher.getInstance("AES/CBC/CTSPadding", "BC");
14 
15         byte[] input = Hex.decode("a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7"
16                                 + "a0a1a2a3a4a5a6a7a0");
17 
18         System.out.println("input    : " + Hex.toHexString(input));
19 
20         byte[] iv = Hex.decode("9f741fdb5d8845bdb48a94394e84f8a3");
21 
22         cipher.init(Cipher.ENCRYPT_MODE, key, new IvParameterSpec(iv));
23 
24         byte[] output = cipher.doFinal(input);
25 
26         System.out.println("encrypted: " + Hex.toHexString(output));
27 
28         cipher.init(Cipher.DECRYPT_MODE, key, new IvParameterSpec(iv));
29 
30         System.out.println("decrypted: "
31                             + Hex.toHexString(cipher.doFinal(output)));
32     }
 33 }
```

运行该示例将产生以下输出：

```
input    : a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0
encrypted: caa168f23f888234125f2e6bd9c1934eefd8d07f7b4d2cd46f
decrypted: a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0
```

如你所示，加密输出的长度与原始明文相同。

## 流式块模式

![在流式加密模式中使用块密码](img/chapter2----StreamBlockCipher.png)

在流式加密模式中使用块密码

流式模式之所以被称为此名，是因为它们能够在不使用填充的情况下加密任意大小的数据。在这种情况下，块密码被用于生成一个密钥流，然后将其与待加密的数据进行异或。这些模式还有另一个有用特性：虽然块密码的核心仍然在使用其虚拟密码本，但这些模式仅要求密码加密算法的实现，因为密码本现在仅用于生成一个加密流，以便与用于加密的数据或用于解密的密文进行异或。

### CTR 模式

计数器模式（`CTR`），也称为分段计数器模式（`SIC`），由 NIST 在 `SP 800-38a` [24] 中由 IETF 在 `RFC 3686` [85] 中标准化。在块流式模式中，这是最有用的。

该模式非常简单，密钥流通过加密一个块生成，该块是随机值（nonce）和计数器的混合。计数器的可用空间决定了密码可以安全地处理多少个块——例如，8 位计数器只允许 256 个块。不同的 nonce 结合相同的初始计数器应该产生唯一的密钥流，因此 nonce 的大小决定了这一点。

以下是该模式的示例：

与 CBC 模式一样，如果解密的数据出现错误，该错误将在流重新同步之前传播到整个一个字大小的字节。

### OFB 模式

OFB（输出反馈）模式与 CFB 模式的不同之处在于，初始 IV 被视为加密器的原始状态，并仅对其进行加密，以产生每个新的密钥流块，该块用于与密钥流进行异或运算。待加密的明文永远不会被底层加密器直接处理。该模式定义在 SP 800-38a 中 [24]。

要在 JCE 中使用 OFB 模式，只需在模式中包含 OFB 字符串，例如：

```java
Cipher cipher = Cipher.getInstance("AES/OFB/NoPadding", "BC");
```

OFB 模式确实具有位错误不会传播的优点，这在某些情况下（例如在处理视频或音频时）非常有用。OFB 模式的缺点是，如果密钥流中存在循环（例如对于给定的密钥和给定的输入值，索引时代码本返回的输出是原始值），流可能会开始意外地重复。正如你可以想象的，这种情况发生的概率非常小，但你在这个领域工作得越久，就越会发现变得“幸运”是多么容易。因此，虽然我们列出了 OFB 模式，但这实际上是为了兼容性考虑，我们不会将其用于任何新项目。CTR 模式也具有 OFB 模式的所有优点且没有缺点，因此，在抛开兼容性不考虑的情况下，使用 CTR 模式更好。

## 流加密

流加密器是设计用于生成密钥流的加密器。

![加密模式下的基本流加密](img/chapter2----StreamCipher.png)

加密模式下的基本流加密

与块加密器的流式模式一样，密钥流随后与输入明文进行异或，以产生密文。同样，与块加密器一样，流加密使用对称密钥初始化，有时还会使用其他参数（如 IV）。与块加密器不同，流加密没有模式，因此你通常只需通过名称调用它们。

附录 C 列出了 Bouncy Castle 支持的流加密器列表。

以下示例展示了 RFC 7539 定义的 ChaCha20 版本 [124] 的用法。



```java
/**
 * 使用 RFC 7539 ChaCha 流加密器的示例。
 */
public class StreamExample
{
    public static void main(String[] args)
        throws Exception
    {
        byte[] keyBytes = Hex.decode("000102030405060708090a0b0c0d0e0f"
                                    + "000102030405060708090a0b0c0d0e0f");

        SecretKeySpec key = new SecretKeySpec(keyBytes, "ChaCha7539");

        Cipher cipher = Cipher.getInstance("ChaCha7539", "BC");

        byte[] input = Hex.decode("a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7"
                                 + "a0a1a2a3a4a5a6a7a0");

        System.out.println("input    : " + Hex.toHexString(input));

        byte[] iv = Hex.decode("010203040506070809101112");

        cipher.init(Cipher.ENCRYPT_MODE, key, new IvParameterSpec(iv));
        byte[] output = cipher.doFinal(input);
        System.out.println("encrypted: " + Hex.toHexString(output));

        cipher.init(Cipher.DECRYPT_MODE, key, new IvParameterSpec(iv));
        System.out.println("decrypted: "
                            + Hex.toHexString(cipher.doFinal(output)));
    }
}
```

如你在示例代码中所示，`Cipher` 定义中缺少了模式和填充标识符，因为它们不是必需。此示例的输出为：

```
input: a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7
encrypted: 3a77592ab77c8fb1dca9e467e56dca5d3c2e623e7a59c73
decrypted: a0a1a2a3a4a5a6a7a0
```

我们可以看到加密器产生的密文长度与原始明文相同。

### 基于加密器的输入/输出

JCE 提供了 `javax.crypto.CipherInputStream` 和 `javax.crypto.CipherOutputStream` 类，它们提供了一种将加密器作为过滤器的方法。遗憾的是，如果对封装的加密器的 `doFinal()` 方法调用出现问题，这些类会静默失败。这对你来说是否是一个问题主要取决于你的决定，但请注意，这种副作用是静默失败意味着 AEAD 加密器抛出的异常也会被忽略（我们将在本章讨论这意味着什么）。

考虑到这一点，下面的示例是使用 Bouncy Castle 版本的 `CipherInputStream` 和 `CipherOutputStream`，你可以在 `javax.crypto` 中找到它们。

```java
/**
 * 使用 BC CipherInputStream/CipherOutputStream 类的示例。
 */
public class CipherIO
{
    public static void main(String[] args)
        throws Exception
    {
        KeyGenerator kGen = KeyGenerator.getInstance("AES", "BC");

        SecretKey key = kGen.generateKey();

        Cipher cipher = Cipher.getInstance("AES/CBC/PKCS5Padding", "BC");

        byte[] input = Hex.decode("a0a1a2a3a4a5a6a7a0a1a2a3a4a5a6a7"
                                 + "a0a1a2a3a4a5a6a7a0");

        System.out.println("input    : " + Hex.toHexString(input));

        cipher.init(Cipher.ENCRYPT_MODE, key);

        AlgorithmParameters ivParams = cipher.getParameters();

        // 加密明文
        ByteArrayOutputStream bOut = new ByteArrayOutputStream();
        CipherOutputStream cOut = new CipherOutputStream(bOut, cipher);

        cOut.write(input);
        cOut.close();

        byte[] output = bOut.toByteArray();

        System.out.println("encrypted: " + Hex.toHexString(output));

        cipher.init(Cipher.DECRYPT_MODE, key, ivParams);

        // 解密密文
        ByteArrayInputStream bIn = new ByteArrayInputStream(output);

        CipherInputStream cIn = new CipherInputStream(bIn, cipher);

        byte[] decrypted = Streams.readAll(cIn);

        System.out.println("decrypted: "
                            + Hex.toHexString(decrypted));
    }
}
```

你会注意到这里使用的加密器是采用 CBC 模式和 PKCS #7 填充的 AES。如果你运行示例，你应该看到加密输出如预期的比输入长，并且填充在解密步骤中被干净地删除了。

### 总结

在本章中，我们查看了块加密和流加密。我们涵盖了加密器使用的密钥生成、块加密器运行的不同模式以及填充加密数据的方法。我们还涵盖了如何使用 CTR 和 CFB 模式使用块加密进行流。

最后，我们还查看了 JCE 如何通过 `CipherInputStream` 和 `CipherOutputStream` 类通过加密器提供输入和输出。这是 Java 中读取和写入加密数据的常用方法之一。我们还指出，如果你在使用 AEAD 加密器，应该使用 `org.bouncycastle.jcajce.io` 包中的 `CipherInputStream` 和 `CipherOutputStream`，因为如果 AEAD 标签验证失败，JCE 提供的类将静默失败。

本章介绍了用于验证数据未被篡改的方法——无论是经过加密解密还是直接以明文形式发送。这涉及到使用称为消息摘要（message digests）的函数对一组输入计算加密哈希值。除了识别篡改外，通过计算消息摘要并包含共享密钥，还可以对输入的来源提供某些保证。在第二种情况下，这种加密校验和意味着可以断定消息具有特定的发送者，并可用于避免重放攻击风险。提供这种额外保证的函数被称为 `MACs`。这些函数有效的主要原因是它们是不可逆的。这种不可逆性也使得摘要和 `MACs` 适用于随机数生成和密钥派生，在这两个领域中，都希望隐藏输入到生成器的原始种子材料。

## 消息摘要

消息摘要用于为特定消息计算加密校验和（或哈希）。消息摘要与类似 `CRC` 的东西之间的区别在于：消息摘要输入的输入的任何微小变化都会对构成消息摘要函数结果的位值产生不可预测且可能是巨大的影响。虽然在不先进行计算的情况下无法猜测某个特定消息的明摘要输出，但消息摘要的大小和函数本身也反映了两个不同的消息产生相同摘要结果（也称为 `collision`，碰撞）的概率。

### MessageDigest 类

JCA 通过 `MessageDigest` 类提供了对支持消息摘要计算对象的访问，该类可以在 `java.security` 包中找到。由于它属于 JCA，此类对象不是直接创建的，而是通过 `getInstance()` 方法创建的。

`MessageDigest` 不需要任何设置。创建后，使用不同的 `update()` 方法将数据添加到计算中，并通过其中一个 `digest()` 方法返回结果，如下例所示：

```java
/**
 * 使用传入的算法 
 * digestName 返回基于数据计算的摘要。
 *
 * @param digestName 摘要算法的名称。
 * @param data 摘要函数的输入。
 * @return 计算的消息摘要。
 */
public static byte[] computeDigest(String digestName, byte[] data)
    throws NoSuchProviderException, NoSuchAlgorithmException
{
    MessageDigest digest = MessageDigest.getInstance(digestName, "BC");

    digest.update(data);

    return digest.digest();
}
```

以下是 `computeDigest()` 函数的简单用法：

```java
/**
 * 使用 MessageDigest 的简单示例。
 */
public class DigestExample
{
    public static void main(String[] args)
        throws Exception
    {
        System.out.println(
            Hex.toHexString(
                computeDigest("SHA-256", Strings.toByteArray("Hello World!"))));
    }
}
```

如果你运行该示例且一切顺利，你将看到以下输出。

```
7f83b1657ff1fc53b92dc18148a1d65dfc2d4b1fa3d677284addd200126d9069
```

如果你尝试微调 `DigestExample` 中的输入字符串，你会发现生成的摘要以一种显而随机的方式发生变化，即使字符串保持当前的 12 个字符（或 96 位）长度，这远低于消息摘要生成的 256 位。

`MessageDigest` 还支持一种“一键式”计算方法，也称为 `digest()`，如示例中的所示，它接受单个字节数组作为输入。该类中还有一个静态的 `MessageDigest.isEqual()` 方法，接受两个字节数组。`isEqual()` 方法提供了恒定时间的相等性检查，尽管如果你真的在寻找更安全的恒定时间比较，Bouncy Castle API 中也有 `org.bouncycastle.util.Arrays.constantTimeAreEqual()`。

## MACs

`MACs` 用于需要对加密校验和的计算方式提供保证的情况。它们涉及到创建 `MAC` 的方与使用 `MAC` 的方之间使用共享密钥。它们比消息摘要进一步，因为可以用于将计算 `MAC` 的消息与特定的发送者关联，并作为消除重放消息的手段。`MACs` 可以使用密码或消息摘要生成。与消息摘要不同，`MAC` 函数假设存在密钥以及输入数据。在固定密钥的情况下，`MACs` 可以执行与消息摘要类似的功能，但它们仍然优于简单的 `CRC`，因为对 `MAC` 输入的更改会导致 `MAC` 结果产生不可预测的位变化。当用于初始化 `MAC` 的密钥密钥时，`MAC` 还能对被 MAC 处理的数据的来源提供某些保证。

截断 `MACs` 也相当常见，大多数情况下这是相当安全的，但要注意：`MAC` 越小，发生 `collision` 的概率就越高，因此截断 `MAC` 会同时影响初始化它的密钥的寿命以及 `MAC` 本身的可靠性。在开始丢弃位之前，最好考虑这些影响。

### Mac 类

JCE 通过 `javax.crypto.Mac` 类提供了对 MAC 函数的访问。与 `Cipher` 类一样，此类对象不是直接创建的，而是使用 `getInstance()` 工厂模式。

这是一个计算 `MAC`。

```java
/**
 * 使用传入的算法
 * type 返回基于数据计算的 MAC。
 *
 * @param algorithm 算法的名称。
 * @param key 用于 MAC 的适当密钥。
 * @param data MAC 函数的输入。
 * @return 计算的 MAC。
 */
public static byte[] computeMac(String algorithm, SecretKey key, byte[] data)
    throws NoSuchProviderException, NoSuchAlgorithmException,
           InvalidKeyException
{
    Mac mac = Mac.getInstance(algorithm, "BC");

    mac.init(key);

    mac.update(data);

    return mac.doFinal();
}
```

你可以看到 `MAC` 和 `MessageDigest` 的主要区别在于存在 `init()` 方法以及对 `SecretKey` 的使用。如前所述，由于使用了密钥，`MACs` 常用于验证消息内容的来源。

`MAC` 类的另一个区别是我们现在使用 `Mac.doFinal()` 作为获取最终校验和的方法，使得该类的用法类似于 `Cipher` 类。`MAC` 类上的 `init()` 方法很大程度上遵循 `Cipher` 类，某些 MAC 算法可以接受额外的参数（如 IV），其用途与相应加密类的参数类似。还有一个接受字节数组的 `doFinal()` 版本，可以作为一键式方法计算 `MAC`，就像 `MessageDigest` 的一键式 `digest()` 方法一样。

以下示例提供了使用 `computeMac()` 方法使用 AES 和 CMAC 算法计算 `MAC` 的示例：

```java
/**
 * 使用 AES CMAC 的简单示例。
 */
public class MacExample
{
    public static void main(String[] args)
        throws Exception
    {
        SecretKey macKey = new SecretKeySpec(
            Hex.decode("dfa66747de9ae63030ca32611497c827"), "AES");

        System.out.println(
            Hex.toHexString(
                computeMac("AESCMAC", macKey,
                                 Strings.toByteArray("Hello World!"))));
    }
}
```

如果你运行此代码且一切顺利，你应该得到：

```
24331a9b3a21f382e41c8a485fababf0
```

这与底层加密器的块大小相同，是一个 128 位的值。请注意，使用给定的加密算法计算 MAC 有多种不同的方法，例如 `CBC-MAC` 和 `GMAC`（仅两个）。完整列表可以在附录 C 中找到。

#### HMAC

如所述，也可以使用消息摘要来计算 MAC。以这种方式计算的 MAC 被称为哈希 MAC，简称为 `HMACs`。

下面的示例展示了如何通过 JCE 的 `Mac` 类使用 HMAC。如你所见，除了 `macKey` 设置和算法名称外，我们之前看到的 `computeMac()` 方法也可以用于 HMAC。



## 使用 HMAC SHA-256 的简单示例

```java
 1 /**
 2  * 使用 HMAC SHA-256 的简单示例。
 3  */
 4 public class HMacExample
 5 {
 6     public static void main(String[] args)
 7         throws Exception
 8     {     Security.addProvider(new BouncyCastleProvider());
 9         SecretKey macKey = new SecretKeySpec(
10                 Hex.decode(
 11                     "2ccd85dfc8d18cb5d84fef4b19855469" +
 12                     "9fece6e8692c9147b0da983f5b7bd413"), "HmacSHA256");
 13 
 14         System.out.println(
 15             Hex.toHexString(
 16                 computeMac("HmacSHA256", macKey,
 17                                  Strings.toByteArray("Hello World!));));
 18     }
 19 }
```

运行此示例将产生一个 256 位的字符串：

```
8e079dd2d9b271a17a4d3dfa3a808b41d2105fee7aabe7ceccfdf66e8339e5d7
```

在这种情况下，它反映了用于支持 `HMAC` 函数的消息摘要的大小。

## 密钥派生函数

密钥派生函数（`KDFs`）利用消息摘要和/或 MAC 获取一组输入（在某些情况下这些需要保密），然后产生适用于不同长度密钥的数据流。某些 KDF 会会将密钥的大小限制为输出摘要的最大大小。德国标准 `BSI TR-03111` [40] 的第 4.3.3 节就有这样一个示例，其中摘要的输出（`SHA-1` 或 `SHA-256`）被用于生成对称加密会话密钥。更常见的是，KDF 对产生的输出大小是灵活的。

最常见的灵活 KDF 定义在 `X9.63` [68] 中，并在其他地方被广泛引用，包括 `BSI TR-03111` 和 NIST 标准。其次常见的是最初被称为 `NIST Concatenation KDF` 的，现在描述在 `SP 800-56C` [31] 第 4 节中。我们在这里查看这两个函数。

### X9.63 KDF

KDF 需要的输入包括：

*   `Z` 它通常是一个生成的秘密值，通常来自密钥协商方案。
*   `SharedInfo` 这是一个可选的字节字符串，它与 `Z` 结合。
*   `keyLen` 要生成的密钥的长度。
*   一个函数 `H()`，它是我们用于构建 KDF 的消息摘要。
*   `hLen` `H()` 的输出大小。

`SharedInfo` 是 KDF 计算中使用的可选字节字符串。它的命名法源于这样一个事实：当多个实体尝试使用相同的 `Z` 值生成相同的密钥材料时，在使用 KDF 之前必须以某种方式共享该字节字符串。其目的是提供一些额外数据，以确保无论 Z 值是否冲突，KDF 的输出与其他 KDF 相比都是唯一的。

在验证输入后，执行以下算法来计算密钥材料：

1.  设置 `R = ceil(keyLen / hLen)`
2.  设置 `C = 1`
3.  从 `I = 1` 到 `R`：
    1.  设置 `K = H(Z || SharedInfo)`
    2.  设置 `C = C + 1`
    3.  设置 `Result = Result || K`
4.  返回 `keyLen` 字节。

其中 `ItoB()` 是将 `C` 转换为 4 位整数的函数。

### 拼接 KDF (Concatenation KDF)

最初描述于早期版本的 `SP 800-56`，该算法现在描述在 `SP 800-56C` [31]，标题为“单步密钥派生”。KDF 需要的：

*   `Z` 它通常是一个生成的秘密值，通常来自密钥协商方案。
*   `SharedInfo` 与 `Z` 结合的可选字节字符串。
*   `keyLen` 要生成的密钥的长度。
*   一个函数 `H()`，它是我们用于构建 KDF 的消息摘要。
*   `hLen` `H()` 的输出大小。

`SharedInfo` 是 KDF 计算中使用的可选字节字符串。它的命名法源于这样一个事实：当多个实体尝试使用相同的 `Z` 值生成相同的密钥材料时，在使用 KDF 之前必须以某种方式共享该字节字符串。其目的是提供一些额外数据，以确保无论 Z 值是否冲突，KDF 的输出与其他 KDF 相比都是唯一的。`SP 800-56A` [29] 提供了关于可以放入 `SharedInfo` 的表格。

在验证输入后，执行以下算法来计算密钥材料：

1.  设置 `R = ceil(keyLen / hLen)`
2.  设置 `C = 0`
3.  从 `I = 1` 到 `R`：
    1.  设置 `C = C + 1`
    2.  设置 `K = H(ItoB(C) || SharedInfo)`
    3.  设置 `Result = Result || K`
4.  返回 `keyLen` 字节的 `Result`。

其中 `ItoB()` 也是将 `C` 转换为 4 位大端整数的函数。正如你预期的那样，你不能从我们过的任何一个函数中生成无限的密钥字符串。NIST 函数的限制和安全强度在 `SP 800-56C` [31] 中有所记录。对于我们的目的而言，你永远不会遇到产生密钥材料数量的限制，但你应该确保 KDF 中使用的哈希/MAC 函数对于你生成的密钥大小具有适当的安全强度。

随着 SHA-3 的问世，两个额外的函数：`SHAKE128` 和 `SHAKE256`。虽然它们都基于海绵结构（sponge），但它们与 SHA-3 摘要本身不同，因为它们在设计上能够适应不同的输出大小。这类新型哈希算法被称为可扩展输出函数（XOF），`SHAKE128` 和 `SHAKE256` 已被用于一系列可以产生变量输出的哈希和 MAC 算法。

在 Bouncy Castle 的底层 API 中，XOF 函数实现了 `org.bouncycastle.crypto.Xof`，其定义如下：

```java
 1 public interface Xof
 2     extends ExtendedDigest
 3 {
 4     /**
 5      * 将此摘要的最终计算结果输出到
 6      * outLen 个字节中。
 7      *
 8      * @param out 用于写入输出字节的输出数组。
 9      * @param outOff 开始写入字节的偏移量。
10      * @param outLen 请求的输出字节数。
11      * @return 写入的字节数
12      */
13     int doFinal(byte[] out, int outOff, int outLen);
 14 
 15     /**
116      * 开始输出此摘要的最终计算结果。
17      * 结果。与 doFinal 不同，此方法将持续产生
18      * 输出，直到 Xof 被显式重置或发出其他信号。
19      *
20      * @param out 用于写入输出字节的输出数组。
21      * @param outOff 开始写入字节的偏移量。
22      * @param outLen 请求的输出字节数。
23      * @return 写入的字节数
24      */
25     int doOutput(byte[] out, int outOff, int outLen);
26 }
```

如你所示，这些额外的方法允许在 `doFinal()` 上指定变量大小的输出，并且具有持续输出的潜力——`doOutput()` 方法——直到调用 `doFinal()` 为止。正是这种挤出额外数据的能力赋予了可扩展函数名称。

## SHAKE 函数

`Xof` 的主要实现者是 `SHAKE128` 和 `SHAKE256`。`SHAKE128` 中的 128 和 `SHAKE256` 中的 256 源于与算法相关的最大安全位数，且两者的默认输出大小分别为 256 位和 512 位。如果你使用 `MessageDigest.getInstance()` 方法创建其中任何一个，返回将是最小大小。在这些最小大小之下，输出的实际强度为 `d/2`，其中 `d` 是输出的位（bits）长度。

## cSHAKE, KMAC, TupleHash 和 ParallelHash

2016 年，在 SHA-3 标准发布一多年前后，NIST 发布了 SP 800-185 [36]，该标准定义了一个基于 SHAKE 构建的函数 `cSHAKE`，以及另外三个额外的函数 `KMAC`、`TupleHash` 和 `ParallelHash`，它们都都是基于 `cSHAKE` 构建的。

### cSHAKE

cSHAKE 引入了两个配置参数：`N` 和 `S`。`N` 是函数名称字符串，`S` 是自定义字符串。`N` 应该仅作为 NIST 标准的一部分设置——我们稍后会看到一些示例。另一方面，`S` 用于本地使用——我们以及你可以根据意愿设置它。如果 `N` 和 `S` 均为空字符串，则 cSHAKE 的输出与相应的 SHAKE 函数的输出相同。

在编写本文时，cSHAKE 只能从 Bouncy Castle 的底层 API 正确使用。对于通用提供程序，`N` 和 `S` 是通过引擎的构造函数设置的。例如：

```java
CSHAKEDigest cshake = new CSHAKEDigest(
              128, new byte[0], Strings.toByteArray("Email Signature"));
```

这创建一个基于 SHAKE128 的 `CSHAKEDigest`，其中 `N` 为空，`S` 由从字符串“Email Signature”的 ASCII 编码创建的字节串表示。另一方面：

```java
CSHAKEDigest cshake = new CSHAKEDigest(256, new byte[0], new byte[0]);
```

是 SHAKE256 的直接等效物。

### KMAC, TupleHash 和 ParallelHash

KMAC、TupleHash 和 ParallelHash 都是 cSHAKE 的示例， NIST 标准化了输出。

KMAC 在底层 API 中表示，使用基于字符串“KMAC”的 ASCII 编码的字节串作为其 `N` 值。如其名称所示，它是一个 MAC，底层版本位于 `org.bouncycastle.crypto.macs` 包中，并且可以使用密钥初始化。在 JCA 中提供 `KMAC128` 和 `KMAC256`。

TupleHash 在底层 API 中表示，使用基于字符串“TupleHash”的 ASCII 编码的字节串作为其 `N` 值。如其名称所示，它是一个摘要函数，底层版本位于 `org.bouncycastle.crypto.digests`。例如，向 `TupleHash` 输入“abc”、“def”、“ghi”将产生结果。在 JCA 中提供 `TupleHash128` 和 `TupleHash256`。

ParallelHash 在底层 API 中表示，使用基于字符串“ParallelHash”的 ASCII 编码的字节串作为其 `N` 值。如其名称所示，它是一个摘要函数，底层版本位于 `org.bouncycastle.crypto.digests`。它设计用于多线程执行并接受一个阻塞大小。在 JCA 中提供 `ParallelHash128` 和 `ParallelHash256`。

## Bouncy Castle 摘要和 MAC 计算接口

Bouncy Castle 的 PKIX 包提供了用于摘要和 MAC 计算器的通用接口。这些接口基于流，并提供与算法相关的 ASN.1 `AlgorithmParameters`、用于写入数据的输出流，以及在流关闭后获取计算摘要/MAC 方法。

这些接口贯穿 PKIX API 用于引入摘要和 MAC 操作。JCA 和 BC 底层 API 都存在该接口的实现。如果你需要，也可以由其他加密 API 编写。

### DigestCalculator 接口

`DigestCalculator` 接口所示：

```java
 1 /**
 2  * 通用接口，能够从输出流中
 3  * 计算摘要。
 4  */
 5 public interface DigestCalculator
 6 {
 7     /**
 8      * 返回表示由计算器实现的摘要的算法标识符。
 9      *
10      *
11      * @return 算法 ID 和参数。
12      */
13     AlgorithmIdentifier getAlgorithmIdentifier();
14 
15     /**
16      * 返回一个用于计算摘要的接收数据的流。如果你想
17      * 在运行过程中也累积数据，请使用
18      * org.bouncycastle.util.io.TeeOutputStream。
19      *
20      * @return 一个 OutputStream
21      */
22     OutputStream getOutputStream();
23 
24     /**
25      * 返回对写入计算器输出流的数据计算出的
26      * 摘要。
27      *
28      *
29      * @return 摘要。
30      */
31     byte[] getDigest();
32 }
```



通常情况下，你会通过 `DigestCalculatorProvider` 创建这些对象之一。在高级别 PKIX 类需要创建 `DigestCalculator` 的情况下，你通常会找到一个接受 `DigestCalculatorProvider` 作为参数的方法。如果你使用的是 Bouncy Castle 不直接支持的加密 API（例如特定于 HSM 硬件安全模块的 API），并且你需要在使用 Bouncy Castle PKIX API 的过程中利用它来计算消息摘要，你通常需要实现 `DigestCalculatorProvider` 接口，以为你的消息摘要计算器实现创建一个提供者。

`DigestCalculatorProvider` 接口也基于 `AlgorithmIdentifier` 类，并包含一个方法。

```java
/**
 * DigestCalculator 实现的提供者的基础接口。
 */
public interface DigestCalculatorProvider
{
    DigestCalculator get(AlgorithmIdentifier digestAlgorithmIdentifier)
    throws OperatorCreationException;
}
```

假设你不需要为这些对象中的一个提供自己的实现，如果你正在与 JCA 提供者工作，通常会使用 `JcaDigestCalculatorProviderBuilder` 来创建一个 `DigestCalculatorProvider`。你也可以使用 `DefaultDigestAlgorithmIdentifierFinder` 来解析大多数常见的消息摘要名称及其关联的 `AlgorithmIdentifier` 结构。例如，在使用 BC 提供者创建 SHA-256 消息摘要计算器时，它看起来如下：

```java
/**
 * 为传入的算法摘要名称返回一个 DigestCalculator。
 *
 * @param digestName 摘要算法的名称。
 * @return 用于 digestName 的 DigestCalculator。
 */
public static DigestCalculator createDigestCalculator(String digestName)
    throws OperatorCreationException
{
    DigestAlgorithmIdentifierFinder algFinder =
                              new DefaultDigestAlgorithmIdentifierFinder();
    DigestCalculatorProvider        digCalcProv =
        new JcaDigestCalculatorProviderBuilder().setProvider("BC").build();

    return digCalcProv.get(algFinder.find(digestName));
}
```

`createDigestCalculator` 的参数 `digestName` 以 “SHA-256” 的形式传入。对于像像这样的人为构造的示例，它看起来比 `MessageDigest.getInstance("SHA-256")` 更复杂，但在 BC PKIX API 需求的语境下，这种方法实际上让工作变得简单许多。

使用 `DigestCalculator` 关在于获取输出流并将待摘要的信息写入输出流中。例如，对我们原始的 SHA-256 摘要示例进行重构如下：

```java
/**
 * SHA-256 DigestCalculator 的创建和使用。
 */
public class DigestCalculatorExample
{
    public static void main(String[] args)
        throws Exception
    {
        DigestCalculator digCalc = createDigestCalculator("SHA-256");

        OutputStream dOut = digCalc.getOutputStream();

        dOut.write(Strings.toByteArray("Hello World!"));

        dOut.close();

        System.out.println(Hex.toHexString(digCalc.getDigest()));
    }
}
```

如果你运行上面的示例，你会发现它产生的结果与我们之前过的使用 `MessageDigest` 的原始 SHA-256 示例相同。

你可以在 `org.bouncycastle.operator.bc` 包中找到 `DigestCalculatorProvider` 接口和 `DigestCalculator` 接口实现的更多示例。这些实现没有使用 JCA，可以作为实现你自己的接口版本的指南。

## MacCalculator 接口

下面给出了 `MacCalculator` 接口：

```java
/**
 * 用于密钥初始化操作的通用接口，该操作能够从输出流中
 * 计算 MAC。
 */
public interface MacCalculator
{
    AlgorithmIdentifier getAlgorithmIdentifier();

    /**
     * 返回一个接受数据的流，用于计算以供后续验证的
     * MAC。如果你还想在处理过程中累积数据，请使用
     * org.bouncycastle.util.io.TeeOutputStream。
     *
     * @return 一个 OutputStream
     */
    OutputStream getOutputStream();

    /**
     * 根据写入流的内容返回计算出的 MAC。
     *
     * @return 计算出的 MAC。
     */
    byte[] getMac();


    /**
     * 返回用于计算 MAC 的密钥。
     *
     * @return MAC 密钥。
     */
    GenericKey getKey();
}
```

`MacCalculator` 的使用在 PKIX API 中往往更具专门性，因此并不是为它们有一个提供者类，而是为每个领域都有专门的构建器和提供者，例如 CMS（由 `JceCMSMacCalculatorBuilder` 表示）和 PKCS #12（由 `JcePKCS12MacCalculatorBuilderProvider` 表示）。

创建完成后，`MacCalculator` 的用法与 `DigestCalculator` 相同。你也可以在与不同 PKIX 协议相关的 `.bc` 包中找到更多 `MacCalculator` 实现。这些实现没有使用 JCA，可以作为实现你自己的接口版本的指南。

## 摘要的应用：默尔树

一个说明摘要有多么强大的良好例子是[默尔树](https://en.wikipedia.org/wiki/Merkle_tree)。默尔树是 Ralph Merkle 在 1979 年左右提出的构想。它们最近由于比特币而变得广为人知，但在其他应用中也经常使用，例如出现在 RFC 6962 和 RFC 7574。

### 什么是默尔树？

默尔树是摘要的树，叶节点摘要代表某些数据，分支节点摘要代表从下方节点摘要构建的摘要。

![基础默尔树 - 数据用于生成叶节点哈希](img/chapter3----Merkle1.png)

从图中可以看出，根哈希在意义上代表树的哈希，因此代表存储在树中的所有数据的哈希。这是默尔树有用之处之一，无论有多少个数据值，你都可以使用默尔树将其减少为一个哈希，如果以后需要添加另一个数据值，不需要重新计算所有的哈希。你只需要计算新数据的哈希，然后重新计算受数据插入影响的分支节点直到根哈希。

这引导我们进入默尔树的另一个有用功能：你可以生成所谓的 `审计路径`（audit path），作为数据值已添加到树中的证明。我们可以在下面的图中看到审计路径是如何生成的。

![生成证明值 D2 存在的审计路径所涉及的步骤](img/chapter3----Merkle2.png)

如所示，这关乎收集与数据路径相关的分支哈希。之所以这样做的原因是，一旦你计算了这些哈希以及你要证明在树中的数据的哈希，你就可以重新计算根哈希值。如果根哈希值计算出的哈希与树的实际根哈希相同，你就确认了审计路径显示你感兴趣的值确实在树中。

实现 Merkle 树的最佳方法是使用平衡树算法——其主要原因是它能保持审计路径最短，从而提供评估成本最低的证明。关于 Merkle 树的另外一个点是，它还提供了一个反警示，说明了如果你简单地拼接哈希值并输入哈希函数，会发生什么，因为你可能会发现自己容易受到二阶前像攻击（second preimage attack）。虽然我们在这里不讨论细节，但从 Merkle 树的角度来看，这表现就像是你仅使用普通哈希函数对数据进行哈希，而有人欺骗你接受一个实际哈希值到树中，此时该树的根节点可能会被证明某个文档已插入其中，而实际上并没有插入。

幸运的是，这种情况通过在哈希处理之前为数据添加前缀，并对分支节点哈希使用不同的前缀是很容易避免的——这是 RFC 6962 中采用的方法。

### MerkleTree 类

以下代码使用 AVL+ 树实现了 `MerkleTree`，它是平衡 AVL 树的一种变体，将插入的数据存储在叶子节点中。你会注意到，该树的实现通过在哈希计算中使用前缀提供了二阶前像抗性，这与 RFC 6962 的相同。为了利用围绕 Merkle 树的一些更高级的安全证明，你还需要修改此实现以限制树的大小。

以下是代码：



```java
/**
 * 基于 AVL+ 树的 Merkle Tree 实现（其中数据始终
 * 存储叶子节点中）。
 */
public class MerkleTree
{
    // 树节点的基类。
    private class Node
    {
        byte[] keyValue;
        byte[] hash;

        // 如果此节点的 keyValue 大于
        // 其他节点的 keyValue，返回 true。
        boolean isGreaterThan(Node other)
        {
            for (int i = 0; i != keyValue.length; i++)
            {
                int thisB = this.keyValue[i] & 0xff;
                int otherB = other.keyValue[i] & 0xff;
                if (thisB > otherB)
                {
                    return true;
                }
                else if (thisB < otherB)
                {
                    return false;
                }
            }

            return false;
        }
    }

    // 叶子节点。
    private class LeafNode
        extends Node
    {
        final byte[] nodeValue;

        LeafNode(byte[] nodeHash, byte[] nodeValue)
        {
            this.keyValue = nodeHash;
            this.nodeValue = nodeValue;
            this.hash = nodeHash;
        }
    }

    // 分支节点。
    private class BranchNode
        extends Node
    {
        Node left, right;

        BranchNode(Node left, Node right)
        {
            this.left = left;
            this.right = right;
            this.recalculateHash();
            this.recalculateKeyValue();
        }

        void recalculateKeyValue()
        {
            this.keyValue = findMaxValue(left);
        }

        void recalculateHash()
        {
            this.hash = calculateBranchHash(left, right);
        }

        int getBalance()
        {
            return getHeight(this.left) - getHeight(this.right);
        }

        private int getHeight(Node root)
        {
            if (root instanceof BranchNode)
            {
                return 1 + Math.max(
                    getHeight(((BranchNode)root).left),
                    getHeight(((BranchNode)root).right));
            }

            return 0;
        }

        private byte[] findMaxValue(Node root)
        {
            if (root instanceof BranchNode)
            {
                return findMaxValue(((BranchNode)root).right);
            }
            else
            {
                return ((LeafNode)root).keyValue;
            }
        }
    }

    private final MessageDigest digest;
    private final byte[] emptyHash;

    Node root;

    /**
     * 构造函数
     * @param digest 用于生成树哈希的摘要算法。
     */
    public MerkleTree(MessageDigest digest)
    {
        this.digest = digest;
        this.emptyHash = digest.digest();
    }

    /**
     * 将值插入 Merkle 树。
     * @param value 要插入的值。
     */
    public void insert(byte[] value)
    {
        LeafNode leafNode = createLeafNode(Arrays.clone(value));

        if (root == null)
        {
            root = leafNode;
        }
        else
        {
            root = insertLeaf(root, leafNode);
        }
    }

    /**
     * 如果值在树中，则返回指向该值的 AuditPath（审计路径）。否则返回 null。
     * @param value 我们想要审计路径的值。
     * @return 一个 AuditPath，如果值不存在则返回 null。
     */
    public AuditPath generateAuditPath(byte[] value)
    {
        LeafNode leafNode = createLeafNode(Arrays.clone(value));

        if (root == null)
        {
            return null;
        }
        else
        {
            List pathElements = new ArrayList();

            boolean found = buildAuditPath(pathElements, root, leafNode);

            if (found)
            {
                return new AuditPath(root.hash, pathElements);
            }

            return null;
        }
    }

    private LeafNode createLeafNode(byte[] nodeValue)
    {
        // 使用零前缀是为了确保我们使用的计算方法与
        // 节点不同。详情请参见 RFC 6962 的第 2.1 节。
        return new LeafNode(hash((byte)0x00, nodeValue), nodeValue);
    }

    private boolean buildAuditPath(
        List<AuditPath.Element> proof, Node treeNode, LeafNode newNode)
    {
        if (newNode.isGreaterThan(treeNode))
        {
            if (treeNode instanceof BranchNode)
            {
                BranchNode branch = (BranchNode)treeNode;

                if (buildAuditPath(proof, branch.right, newNode)) // 找到
                {
                    proof.add(new AuditPath.Element(true, getHash(branch.left)));

                    return true;
                }
            }

            return false;
        }
        else
        {
            if (treeNode instanceof BranchNode)
            {
                BranchNode branch = (BranchNode)treeNode;

                if (buildAuditPath(proof, branch.left, newNode)) // 找到
                {
                    proof.add(new AuditPath.Element(false, getHash(branch.right)));

                    return true;
                }
                return false;
            }
            else
            {
                return Arrays.constantAreEqual(treeNode.hash, newNode.hash);
            }
        }
    }

    private byte[] getHash(Node node)
    {
        if (node == null)
        {
            return emptyHash;
        }
        else
        {
            return node.hash;
        }
    }

    private byte[] calculateBranchHash(Node left, Node right)
    {
        // 前缀是为了确保计算方法与        // 叶子节点不同。详情参见 RFC 6962 的第 2.1 节。
        byte[] leftHash = (left != null) ? left.hash : emptyHash;
        byte[] rightHash = (right != null) ? right.hash : emptyHash;

        return hash((byte)0x01, Arrays.concatenate(leftHash, rightHash));
    }

    private byte[] hash(byte preFix, byte[] value)
    {
        digest.update(preFix);
        digest.update(value);

        return digest.digest();
    }

    // 平衡操作 - 左旋
    private BranchNode rotateLeft(BranchNode n)
    {
        n.left = new BranchNode(n.left, ((BranchNode)n.right).left);
        n.right = ((BranchNode)n.right).right;

        balance((BranchNode)n.left);

        n.recalculateKeyValue();
        n.recalculateHash();

        return n;
    }

    // 平衡操作 - 右旋
    private BranchNode rotateRight(BranchNode n)
    {
        n.right = new BranchNode(((BranchNode)n.left).right, n.right);
        n.left = ((BranchNode)n.left).left;

        balance((BranchNode)n.right);

        n.recalculateKeyValue();
        n.recalculateHash();

        return n;
    }

    private Node insertLeaf(Node treeNode, LeafNode newNode)
    {
        if (treeNode == null)
        {
            return newNode;
        }
        else if (treeNode.isGreaterThan(newNode))
        {
            if (treeNode instanceof BranchNode)
            {
                BranchNode branch = (BranchNode)treeNode;

                branch.left = insertLeaf(branch.left, newNode);

                branch.recalculateKeyValue();
                branch.recalculateHash();

                return balance(branch);
            }
            else
            {
                return new BranchNode(newNode, treeNode);
            }
        }
        else
        {
            if (treeNode instanceof BranchNode)
            {
                BranchNode branch = (BranchNode)treeNode;

                branch.right = insertLeaf(branch.right, newNode);

                branch.recalculateKeyValue();
                branch.recalculateHash();

                return balance(branch);
            }
            else
            {
                return new BranchNode(treeNode, newNode);
            }
        }
    }

    // 检查 BranchNode 是否达到平衡。
    private BranchNode balance(BranchNode node)
    {
        int balance = node.getBalance();

        // 左侧高
        if (balance == 1)
        {
            return rotateRight(node);
        }

        // 右侧高
        if (balance == -1)
        {
            return rotateLeft(node);
        }

        // 左右重
        if (balance >= 2)
        {
            if (((BranchNode)node.left).right instanceof LeafNode)
            {
                node.left = rotateRight((BranchNode)node.left);
                return node;
            }
            else
            {
                node.left = rotateLeft((BranchNode)node.left);
                return rotateRight(node);
            }
        }

        // 右左重
        if (balance <= -2)
        {
            if (((BranchNode)node.right).left instanceof LeafNode)
            {
                node.right = rotateLeft((BranchNode)node.right);
                return node;
            }
            else
            {
                node.right = rotateRight((BranchNode)node.right);
                return rotateLeft(node);
            }
        }

        return node;
    }

    /**
     * 返回树的转储 - 中序遍历。
     * @return 树的字符串转储。
     */
    public String toString()
    {
        StringBuilder sBld = new StringBuilder();

        toString(sBld, root);

        return sBld.toString();
    }

    private void toString(StringBuilder sBld, Node root)
    {
        if (root instanceof BranchNode)
        {
            sBld.append("(N[");
            sBld.append(new BigInteger(1, root.keyValue).toString(16));
            sBld.append("]: ");
            toString(sBld, ((BranchNode)root).left);
            sBld.append(", ");
            toString(sBld, ((BranchNode)root).right);
            sBld.append(")");
        }
        else
        {
            sBld.append("(L[");
            sBld.append(new BigInteger(1, root.keyValue).toString(16));
            sBld.append("]: ");
            sBld.append(new BigInteger(1, ((LeafNode)root).nodeValue).toString());
            sBld.append(")");
        }
    }
}
```



# AuditPath 类

希望你已经注意到了 `MerkleTree` 中的 `generateAuditPath()` 方法，它返回一个 `AuditPath`。`AuditPath` 类为哈希值提供了载体，这些哈希值构成了特定值已存储在树中的证明。对路径进行完整评估以检查是否与某些可能的数据匹配是在 `isMatched()` 方法中完成的。

```java
 1 /**
 2  * MerkleTree 类创建的 AuditPath 载体，用于提供树中值的 3  * 存在证明。
 4  */
 5 public class AuditPath
 6 {
 7     /**
 8      * 节点哈希的载体，combine() 方法确保在评估时
 9      * 将哈希正确添加到与其合并的哈希值中。
10      */
11     public static class Element
12     {
13         byte[] value;
14         boolean isLeft;
15 
16         Element(boolean isLeft, byte[] value)
17         {
18             this.isLeft = isLeft;
19             this.value = value;
20         }
 
21         /**
22          * 将此元素的哈希与传入的哈希合并，
23          * 的格式适用于传递给摘要函数。
24          *
25          * @param hash 要与此元素合并的哈希。
26          * @return 元素哈希与传入哈希的拼接。
27          */
28         public byte[] combine(byte[] hash)
29         {
30             if (isLeft)
31             {
32                 return Arrays.concatenate(new byte[]{1}, value, hash);
33             }
34             else
35             {
36                 return Arrays.concatenate(new byte[]{1}, hash, value);
37             }
38         }
39     }
 
40     private final byte[] rootHash;
41     private final List<Element> elements;
 
42     AuditPath(byte[] rootHash, List<Element> elements)
43     {
44         this.rootHash = rootHash;
45         this.elements = Collections.unmodifiableList(elements);
46     }
 
47     /**
48      * 返回该审计路径所在树的根哈希。
49      *
50      * @return 树的根哈希。
51      */
52     public byte[] getRootHash()
53     {
54         return Arrays.clone(rootHash);
55     }
 
56     /**
57      * 返回代表通往树根的审计路径
58      * 元素的列表。
59      *
60      * @return 哈希元素哈希 元素列表。
61      */
62     public List<Element> getElements()
63     {
64         return elements;
65     }
 
66     /**
67      * 如果传入的数据值是审计路径 
68      * 匹配的值，则返回 true。
69      *
70      * @param digest 用于哈希计算的摘要
71      * @param data 正在检查的值
72      * @return 如果审计路径对应该数据，则返回 true，否则返回 false。
73      */
74     public boolean isMatched(MessageDigest digest, byte[] data)
75     {
76         digest.update((byte)0x00);
77         digest.update(data, 0, data.length);
 
78         byte[] dig = digest.digest();
 
79         for (AuditPath.Element element : elements)
80         {
81             dig = digest.digest(element.combine(dig));
82         }
 
83         return Arrays.constantTimeAreEqual(getRootHash(), dig);
84     }
85 }
```

你可以从 `isMatched()` 方法中看到，尽管原始 `Merkle tree` 的规模很大，但审计路径只包含几个哈希值。这几个哈希值足以允许你确认某个值已添加到树中，因为它们在与感兴趣值的哈希值合并时，提供了足够的数据来重新计算树的根哈希。

## 尝试使用 Merkle Tree

既然到了这里，如果能实际尝试使用这个类就太好了。以下代码段将向树填充 2000 多个数字，然后通过为特定值生成审计路径，查看其是否能找到该值已添加到树中的证明。

```java
 1       MessageDigest sha256 = MessageDigest.getInstance("SHA-256");
 2 
 3       MerkleTree tree = new MerkleTree(sha256);
 4 
 5       // 用数据填充树。
 6       for (int i = 0; i != 1000; i += 2)
 7       {
 8           tree.insert(BigIntegers.asUnsignedByteArray(BigInteger.valueOf(i)));
 9       }
 
10       for (int i = 1001; i > 0; i -= 2)
11       {
12           tree.insert(BigIntegers.asUnsignedByteArray(BigInteger.valueOf(i)));
13       }
 
14       // 为感兴趣的值生成审计路径。
15       byte[] value = BigIntegers.asUnsignedByteArray(BigInteger.valueOf(239));
 
16       AuditPath path = tree.generateAuditPath(value);
 
17       System.out.println("Value on path: " + path.isMatched(sha256, value));
 
18       // 尝试使用路径匹配不同的值。
19       value = BigIntegers.asUnsignedByteArray(BigInteger.valueOf(100));
 
20       System.out.println("Value on path: " + path.isMatched(sha256, value));
```

如果一切运行正常，示例代码将输出：

```
Value on path: true
Value on path: false
```

证明第一个数字 239 同时在树中，并且是生成审计路径针对的值。

# 第 4 章：认证模式、密钥封装与 SealedObject

本章介绍了认证模式，这是对称加密的一种变体，它在数据流中包含密码校验和，以便解密方可以判断数据的正确性。我们还将查看密钥封装模式，即加密对称密钥和私钥。最后，我们将查看使用 Java 提供的 `SealedObject` 类来加密序列化对象的简单方法。

### 示例设置

示例使用了以下方法生成一个固定值的 128 位 AES 密钥：

```java
 1   /**
 2    * 创建固定值的 AES 密钥。
 3    *
 4    * @return 固定的 AES 密钥。
 5    */
 6   static SecretKey createConstantKey()
 7   {
 8       return new SecretKeySpec(
 9                      Hex.decode("000102030405060708090a0b0c0d0e0f"), "AES");
10   }
```

我们避免使用 `KeyGenerator` 类，是因为我们希望下面示例的输出和行为易于预测。

### 认证加密模式

认证加密模式提供了一种允许对加密数据流进行验证的模式，这种验证可以在解密之前或解密之后进行，验证其可能是原始加密数据的准确表示。数据的检查是通过使用 MAC（消息认证码）完成的，由解密密文的方进行验证。MAC 不限于与加密后的明文相关，任何认证数据模式都可以扩展为将“关联数据”（associated data）纳入计算中，此时 MAC 也会包含这些“关联数据”。正因为这种可扩展性，你会看到这些模式既被称为 AE（认证加密）模式，也被称为 AEAD（带关联数据的认证加密）模式。

![认证加密模式的基本类型](img/chapter4----AEADTypes.png)

## 认证加密模式的基本类型

Bellare 和 Namprempre [42] 定义了三种基本的认证加密模式。基本类型简述如下。

### `Encrypt-and-MAC`（加密认证）

在这种情况下，MAC 是在明文上计算的，并且对明文进行加密。生成的密文和 MAC 然后发送给接收者。如前所述，可能还会涉及关联数据。这种方法与 `Encrypt-then-MAC`（加密后认证）的区别在于，接收者必须在检查 MAC 之前先解密密文。

### `MAC-then-Encrypt`（认证后加密）

在这里，在明文上计算 MAC，明文和 MAC 都被加密，并将生成的密文发送给接收者（带有任何关联数据）。这种方法也需要解密密文来验证 MAC。

### `Encrypt-then-MAC`（加密后认证）

在最后一种情况下，数据先被加密，然后在关联密文以及（如果存在）任何关联数据上计算 MAC。然后将密文、关联数据和 MAC 发送给接收者，接收者通常可以在不需要恢复任何原始明文的情况下验证前两项。

在记住这些定义的同时，我们现在来看一些实际实现。

### GCM

Galois/Counter Mode（伽罗斯计数模式）定义在 NIST SP 800-38D [27] 中，并使用了 `Encrypt-then-MAC` 方法。它可以与关联数据一起使用，`GMAC` 实际上是 GCM 的仅针对关联数据的版本。

下面的示例展示了如何使用 GCM 进行加密。

```java
 1   /**
 2    * 使用传入的参数通过 GCM 加密传入的数据 pText。
 3    *
 4    * @param key 要使用的密钥密钥。
 5    * @param iv 要与 GCM 一起使用的 IV（初始化向量）。
 6    * @param tagLen 要由 GCM 生成的 MAC 长度。
 7    * @param pText 传给密文算法的明文输入。
 8    * @return 密文。
 9    */
10   static byte[] gcmEncrypt(SecretKey key,
11                             byte[] iv,
12                             int    tagLen,
13                             byte[] pText)
14       throws Exception
15   {
16       Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");
17 
18       GCMParameterSpec spec = new GCMParameterSpec(tagLen, iv);
19 
20       cipher.init(Cipher.ENCRYPT_MODE, key, spec);
21 
22       return cipher.doFinal(pText);
23   }
```

如你在代码示例所示，GCM 也有它自己的参数规范 - `GCMParameterSpec` - 它包含一个 IV 和一个标签长度。对于 GCM，IV 可以是任意长度，但对于给定的密钥，它是唯一的是非常重要的，因为 GCM 底层的加密模式是 `CTR`，因此重用 IV 将导致加密时生成相同的密钥流。标签长度用于指定使用的 MAC 大小——NIST SP 800-38D 的附录 C 中包含了关于 MAC 大小的指导，但正如 Niels Ferguson 在“GCM 中的认证漏洞”[45] 中表达的，通用规则是对于用于计算 MAC 的底层 `GHASH` 算法，应使用最大标签尺寸。

在示例中，我们也没有使用关联数据。因此，除了存在 `GCMParameterSpec` 之外，下方的加密步骤和解密步骤看起来与我们在第 2 章中看到的对称加密非常相似。

```java
 1   /**
 2    * 使用传入的密钥和其他参数解密密文 cText。
 3    *
 4    *
 5    * @param key 要使用的密钥密钥。
 6    * @param iv 要与 GCM 一起使用的 IV。
 7    * @param tagLen 之前由 GCM 生成的 MAC 长度。
 8    * @param cText 加密后的密文。
 9    * @return 原始明文。
10    */
11   static byte[] gcmDecrypt(SecretKey key,
12                             byte[] iv,
13                             int    tagLen,
14                             byte[] cText)
15       throws Exception
16   {
17       Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");
18 
19       GCMParameterSpec spec = new GCMParameterSpec(tagLen, iv);
20 
21       cipher.init(Cipher.DECRYPT_MODE, key, spec);
22 
23       return cipher.doFinal(cText);
24   }
```

如代码示例所示，GCM 也有它自己的参数规范 - `GCMParameterSpec` - 它包含一个 IV 和一个标签长度。对于 GCM，IV 可以是任意长度，但对于给定的密钥，它是唯一的是非常重要的，因为 GCM 底层的加密模式是 `CTR`，因此重用 IV 将导致加密时生成相同的密钥流。标签长度用于指定使用的 MAC 大小——NIST SP 800-38D 的附录 C 中包含了关于 MAC 大小的指导，但正如 Niels Ferguson 在“GCM 中的认证漏洞”[45] 中表达的，通用规则是对于用于计算 MAC 的底层 `GHASH` 算法，应使用最大标签尺寸。

在示例中，我们也没有使用关联数据。因此，除了存在 `GCMParameterSpec` 之外，下方的加密步骤和解密步骤看起来与我们在第 2 章中看到的对称加密非常相似。



# 认证加密模式

认证加密模式提供了一种允许对加密数据流进行验证的模式，这种验证可以在解密之前或解密之后进行，验证其可能是原始加密数据的准确表示。数据的检查是通过使用一个 MAC（消息认证码）完成的，由解密密文的方进行验证。MAC 不限于与加密后的明文相关，任何认证数据模式都可以扩展为将“关联数据”（associated data）纳入计算中，此时 MAC 也会包含这些“关联数据”。正因为这种可扩展性，你会看到这些模式既被称为 AE（认证加密）模式，也被称为 AEAD（带关联数据的认证加密）模式。

![认证加密模式的基本类型](img/chapter4----AEADTypes.png)

## 认证加密模式的基本类型

Bellare 和 Namprempre [42] 定义了三种基本的认证加密模式。基本类型简述如下。

### `Encrypt-and-MAC`（加密认证）

在这种情况下，MAC 是在明文上计算的，并且只对明文加密。生成的密文和 MAC 然后发送给接收者。如前所述，可能还会涉及关联数据。这种方法与 `Encrypt-then-MAC`（加密后认证）的区别在于，接收者必须在检查 MAC 之前先解密密文。

### `MAC-then-Encrypt`（认证后加密）

在这里，在明文上计算 MAC，明文和 MAC 都被加密，并将生成的密文发送给接收者（带有任何关联数据）。这种方法也需要解密密文来验证 MAC。

### `Encrypt-then-MAC`（加密后认证）

在最后一种情况下，数据先被加密，然后在密文以及（如果存在）任何关联数据上计算 MAC。然后将密文、关联数据和 MAC 发送给接收者，接收者通常可以在不需要恢复任何原始明文的情况下验证前两项。

在记住这些定义的同时，我们现在来看一些实际实现。

## GCM

Galois/Counter Mode（伽罗斯计数模式）定义在 NIST SP 800-38D [27] 中，并使用了 `Encrypt-then-MAC` 方法。它可以与关联数据一起使用，`GMAC` 实际上是 GCM 的仅针对关联数据的版本。

下面的示例展示了如何使用 GCM 进行加密。

```java
/**
 * 使用传入的参数通过 GCM 加密传入的数据 pText。
 *
 * @param key 要使用的密钥密钥。
 * @param iv 要与 GCM 一起使用的 IV。
 * @param tagLen 要由 GCM 生成的 MAC 长度。
 * @param pText 传给密文算法的明文输入。
 * @return 密文。
 */
static byte[] gcmEncrypt(SecretKey key,
                         byte[] iv,
                         int    tagLen,
                         byte[] pText)
      throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");

    GCMParameterSpec spec = new GCMParameterSpec(tagLen, iv);

    cipher.init(Cipher.ENCRYPT_MODE, key, spec);

    return cipher.doFinal(pText);
}
```

如你在代码示例所示，GCM 也有它自己的参数规范 - `GCMParameterSpec` - 它包含一个 IV 和一个标签长度。对于 GCM，IV 可以是任意长度，但对于给定的密钥，它是唯一的是非常重要的，因为 GCM 底层的加密模式是 `CTR`，因此重用 IV 将导致加密时生成相同的密钥流。标签长度用于指定使用的 MAC 大小——NIST SP 800-38D 的附录 C 中包含了关于 MAC 大小的指导，但正如 Niels Ferguson 在“GCM 中的认证漏洞”[45] 中表达的，通用规则是对于用于计算 MAC 的底层 `GHASH` 算法，应使用最大标签尺寸。

在示例中，我们也没有使用关联数据。因此，除了存在 `GCMParameterSpec` 之外，下方的加密步骤和解密步骤看起来与我们在第 2 章中看到的对称加密非常相似。

```java
/**
 * 使用传入的密钥和其他参数解密密文 cText。
 *
 *
 * @param key 要使用的密钥密钥。
 * @param iv 要与 GCM 一起使用的 IV。
 * @param tagLen 之前由 GCM 生成的 MAC 长度。
 * @param cText 加密后的密文。
 * @return 原始明文。
 */
static byte[] gcmDecrypt(SecretKey key,
                         byte[] iv,
                         int    tagLen,
                         byte[] cText)
      throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");

    GCMParameterSpec spec = new GCMParameterSpec(tagLen, iv);

    cipher.init(Cipher.DECRYPT_MODE, key, spec);

    return cipher.doFinal(cText);
}
```

同时也请记住，如果标签计算未能验证消息（排除配置错误的情况下），那么极有可能是消息本身存在问题。确保任何使用你所验证的数据的人都知这一点是非常重要的。

## 参数生成

与需要 `IVs` 的 `CBC` 等模式一样，Bouncy Castle 中也提供了适用于 `GCM` 的 `AlgorithmParameterGenerator` 和 `AlgorithmParameters` 的实现，可以使用这两个类提供的 `getInstance()` 方法来创建。

以下示例展示了如何使用 `AlgorithmParameterGenerator` 为 GCM 密码算法创建一个 `AlgorithmParameters` 对象。

```java
/**
 * 一个使用 AlgorithmParameterGenerator 的 GCM 示例
 */
public class GCMWithParamGenExample
{
    public static void main(String[] args)
        throws Exception
    {
        SecretKey aesKey = createConstantKey();

        AlgorithmParameterGenerator pGen =
            AlgorithmParameterGenerator.getInstance("GCM","BC");

        byte[] msg = Strings.toByteArray("hello, world!");

        System.out.println("msg  : " + Hex.toHexString(msg));

        AlgorithmParameters pGCM = pGen.generateParameters();

        Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");

        cipher.init(Cipher.ENCRYPT_MODE, aesKey, pGCM);

        byte[] cText = cipher.doFinal(msg);

        System.out.println("cText: " + Hex.toHexString(cText));

        GCMParameterSpec gcmSpec = pGCM.getParameterSpec(GCMParameterSpec.class);

        byte[] pText = gcmDecrypt(
                            aesKey, gcmSpec.getIV(), gcmSpec.getTLen(), cText);

        System.out.println("pText: " + Hex.toHexString(pText));
    }
}
```

与之前的示例不同，`GCM` 使用的 `IV` 现在是随机的，因此运行该样本将产生不同的输出。

GCM 参数还有一个 ASN.1 定义，定义在 RFC 5084 [95] 中，如下：

```
GCMParameters ::= SEQUENCE {
  aes-nonce        OCTET STRING, -- recommended size is 12 octets
  aes-ICVlen       AES-GCM-ICVlen DEFAULT 12 }

AES-GCM-ICVlen ::= INTEGER (12 | 13 | 14 | 15 | 16)
```

注意 `ICVlen` 的单位是字节（octets），而不是 `GCMParameterSpec` 中的位（bits），而且请记住在此语境下，`DEFAULT` 指的是当值不应在 DER 中编码时，而不是实际的默认值是什么。正如我们已经提到的，最好使用 128 位的 GCM 标签长度（从 ASN.1 的角度来看是 16 个字节）。虽然该结构是专门为 `AES` 使用而定义的，但 JCE 提供程序通常允许将相同格式用于具有 128 位块大小的其他密码算法。

你可以通过 `pGCM.getEncoded()` 创建 ASN.1 结构的副本，它默认将返回一个 ASN.1 编码，或者你可以完整指定它，并将生成的字节数组传递给 `GCMParameters.getInstance()`，如下所示：

```java
GCMParameters asn1Params = GCMParameters.getInstance(pGCM.getEncoded("ASN.1"));
```

同样，可以通过调用 `AlgorithmParameters.init()` 方法使用 ASN.1 结构 `asn1Params` 的编码来初始化 `AlgorithmParameters` 实现，如下：

```java
AlgorithmParameters pGCM = AlgorithmParameters.getInstance("GCM", "BC");

pGCM.init(asn1Params.getEncoded());
```

## 使用关联数据

到目前为止，我们的示例还没有包含任何关联数据（associated data）。关联数据是不经加密的数据，但它仍用于 MAC 的计算，MAC 提供了出现在加密数据末尾的标签。从 Java 7 开始，`Cipher` 类还包含了为 AEAD 密码算法添加关联数据的方法。

接下来的加密示例展示了如何使用 Java 7 提供的 `Cipher.updateAAD()` 方法包含关联数据。

```java
/**
 * 使用传入的参数通过 GCM 加密传入的数据 pText，
 * 并将 aData 整合到 GCM MAC 计算中。
 *
 * @param key 要使用的密钥密钥。
 * @param iv 用于 GCM 的 IV。
 * @param pText 传入密码算法的明文输入。
 * @param aData 要包含在 GCM MAC 中的关联数据。
 * @return 密文。
 */
static byte[] gcmEncryptWithAAD(SecretKey key,
                         byte[] iv,
                         byte[] pText,
                         byte[] aData)
      throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");

    GCMParameterSpec spec = new GCMParameterSpec(128, iv);

    cipher.init(Cipher.ENCRYPT_MODE, key, spec);

    cipher.updateAAD(aData);

    return cipher.doFinal(pText);
}
```

Bouncy Castle 还提供了一个允许传递关联数据的算法规范：`AEADParameterSpec`。虽然它不像 Java 7 采用的方法灵活，但下面的代码展示了等效写法。



## GCM 解密示例

```java
/**
 * 使用传入的参数通过 GCM 解密传入的数据 cText，
 * 并将 aData 整合到 GCM MAC 计算中。
 *
 * @param key 要使用的密钥密钥。
 * @param iv 用于 GCM 的 IV。
 * @param cText 传入密码算法的密文输入。
 * @param aData 要包含在 GCM MAC 中的关联数据。
 * @return 明文。
 */
static byte[] gcmDecryptWithAAD(SecretKey key,
                                byte[] iv,
                                byte[] cText,
                                byte[] aData)
    throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/GCM/NoPadding", "BC");

    GCMParameterSpec spec = new GCMParameterSpec(128, iv);

    cipher.init(Cipher.DECRYPT_MODE, key, spec);

    cipher.updateAAD(aData);

    return cipher.doFinal(cText);
}
```

考虑到兼容性要求，在可以使用 `updateAAD()` 方法的情况下，最好使用它们。你可以使用以下示例查看两种方法的协同工作。

```java
/**
 * 带有附加数据 (AAD) 的简单 GCM 示例
 */
public class GCMWithAADExample
{
    public static void main(String[] args)
        throws Exception
    {
        SecretKey aesKey = createConstantKey();

        byte[] iv = Hex.decode("bbaa99887766554433221100");
        byte[] msg = Strings.toByteArray("hello, world!");
        byte[] aad = Strings.toByteArray("now is the time!");

        System.out.println("msg: " + Hex.toHexString(msg));

        byte[] cText = gcmEncryptWithAAD(aesKey, iv, msg, aad);

        System.out.println("cText: " + Hex.toHexString(cText));

        byte[] pText = gcmDecryptWithAAD(aesKey, iv, cText, aad);

        System.out.println("pText: " + Hex.toHexString(pText));
    }
}
```

如果你运行该示例，你将看到以下输出：

```
msg: 68656c6c6f2c20776f726c6421
cText: 4024f07c59c758d2d0c7d09934dfe5a6760d5c1f6d778efc3e48e9d073
pText: 68656c6c6f2c20776f726c6421
```

# CCM

计数器结合 CBC/MAC (CCM) 的标准定义在 NIST SP 800-38C [26] 中。它使用了*先加密后加密*（MAC-then-Encrypt）的方法，使用明文计算 CBC-MAC，然后使用 CTR 模式加密算法对明文对其进行加密。它也可以与关联数据配合，尽管它的 MAC “等效”算法 CMAC 与没有明文的 CCM 不同。

与 GCM 一样，CCM 需要一个 `IV`（在这种情况下实际上是 `nonce` 随机数）和一个标签长度来指定要包含的 MAC 大小。以下代码展示了如何使用 `CCM` 加密，除了加密规范外，它看起来与 GCM 的用法相同，因为 JCE API 并没有实际定义 `CCMParameterSpec` 类，因此许多包括 `Bouncy Castle` 在内的供应商都直接接受 `GCMParameterSpec` 用于相同的用途，如下文所示：

```java
/**
 * 使用所传入的参数通过 CCM 加密传入的数据 pText，
 * 并将 aData 纳入 CCM MAC 计算中。
 *
 * @param key 使用的秘密密钥。
 * @param nonce 与 CCM 使用的随机数。
 * @param pText 传入加密器的明文输入。
 * @param aData 与明文一起处理的关联数据。
 * @return 密文。
 */
static byte[] ccmEncryptWithAAD(SecretKey key,
                                byte[] nonce,
                                byte[] pText,
                                byte[] aData)
    throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/CCM/NoPadding", "BC");

    GCMParameterSpec spec = new GCMParameterSpec(128, nonce);

    cipher.init(Cipher.ENCRYPT_MODE, key, spec);

    cipher.updateAAD(aData);

    return cipher.doFinal(pText);
}
```

在这种情况下，我们同样使用了 128 位的标签长度。虽然这与之前的 GCM 示例相同，但与 GCM（标签基于 GHASH 函数）不同，CCM 使用加密算法来计算 MAC，因此标签长度仅限于所使用的底层加密算法的块大小。

Bouncy Castle 中的 CCM 还支持 `AEADParameterSpec` 类，正如我们在下面的解密方法示例所示：

```java
/**
 * 使用所传入的参数通过 CCM 解密传入的密文 cText，
 * 并将 aData 纳入 CCM MAC 计算中。
 *
 * @param key 使用的秘密密钥。
 * @param nonce 原本与 CCM 使用的随机数。
 * @param cText 被加密的密文。
 * @param aData 包含在 CCM MAC 中的关联数据。
 * @return 明文。
 */
static byte[] ccmDecryptWithAAD(SecretKey key,
                                byte[] nonce,
                                byte[] cText,
                                byte[] aData)
    throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/CCM/NoPadding", "BC");

    AEADParameterSpec spec = new AEADParameterSpec(nonce, 128, aData);

    cipher.init(Cipher.DECRYPT_MODE, key, spec);

    return cipher.doFinal(cText);
}
```

我们可以使用下面的示例程序将这两个方法结合在一起。

```java
/**
 * 一个带有带有附加关联数据 (AAD) 的简单 CCM 示例
 */
public class CCMWithAADExample
{
    public static void main(String[] args)
        throws Exception
    {
        SecretKey aesKey = createConstantKey();

        byte[] iv = Hex.decode("bbaa99887766554433221100");
        byte[] msg = Strings.toByteArray("hello, world!");
        byte[] aad = Strings.toByteArray("now is the time!");

        System.out.println("msg  : " + Hex.toHexString(msg));

        byte[] cText = ccmEncryptWithAAD(aesKey, iv, msg, aad);

        System.out.println("cText: " + Hex.toHexString(cText));

        byte[] pText = ccmDecryptWithAAD(aesKey, iv, cText, aad);

        System.out.println("pText: " + Hex.toHexString(pText));
    }
}
```

它应该产生以下输出：

```
msg  : 68656c6c6f2c20776f726c6421
cText: f659bc8216422ed3a6ae7cf3401b5b4ea1e93ae0a7c01d401b3cb25315
pText: 68656c6c6f2c20776f726c6421
```

这也显示了密文长度比明文增加了标签的长度。与 GCM 一样，在评估标签时的错误将导致符合 Java 7 或更高版本的 JVM 抛出 `AEADBadTagException`，或者在较早的 JVM 上抛出 `BadPaddingException` 异常。

CCM 的算法参数生成方式与我们在 GCM 中看到的相同。RFC 5084 [95] 也定义了 CCM 参数的 ASN.1 定义如下：

```asn
CCMParameters ::= SEQUENCE {
    aes-nonce         OCTET STRING,
    aes-IClen        INTEGER DEFAULT 128,
    aes-taglen         INTEGER (4..16),
    aData              OCTET STRING OPTIONAL
}
```

Bouncy Castle 提供了 `CCMParameters` 类，其 ASN.1 定义与 `GCMParameters` 类似。

## EAX

另一种常见的 AEAD 模式是 EAX，它由 Bellare, Rogaway 和 Wagner 在“EAX Mode of Operation”[41] 中提出，作为一种更高效的方法。与 CCM 不同，它使用了*先加密后 MAC*（Encrypt-then-MAC）方法，但它仍然基于 CTR，且其 MAC 实际上是随机数、密文以及关联数据的复合。

在这种情况下，Bouncy Castle 仅支持 `AEADParameterSpec` 类，如如下示例所示：

```java
/**
 * 使用所传入的参数通过 EAX 模式加密传入的数据 pText。
 *
 * @param key 使用的秘密密钥。
 * @param nonce 与 EAX 模式使用的随机数。
 * @param pText 传入加密器的明文输入。
 * @return 密文。
 */
static byte[] eaxEncrypt(SecretKey key,
                         byte[] nonce,
                         byte[] pText)
    throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/EAX/NoPadding", "BC");

    AEADParameterSpec spec = new AEADParameterSpec(nonce, 128);

    cipher.init(Cipher.ENCRYPT_MODE, key, spec);

    return cipher.doFinal(pText);
}
```

解密遵循与之前相同的模式：

```java
/**
 * 使用所传入的密钥和其他参数通过 EAX 模式解密密文 cText。
 *
 * @param key 使用的秘密密钥。
 * @param nonce 与 EAX 模式使用的随机数。
 * @param cText 被加密的密文。
 * @return 原始明文。
 */
static byte[] eaxDecrypt(SecretKey key,
                         byte[] nonce,
                         byte[] cText)
    throws Exception
{
    Cipher cipher = Cipher.getInstance("AES/EAX/NoPadding", "BC");

    AEADParameterSpec spec = new AEADParameterSpec(nonce, 128);

    cipher.init(Cipher.DECRYPT_MODE, key, spec);

    return cipher.doFinal(cText);
}
```

在这种情况下，由于标签长度指向 CMAC 的输出大小，128 位的值与底层加密算法的最大标签大小相关。EAX 也支持基于其他加密算法的使用。

```java
/**
 * A simple main for using the EAX methods.
 */
public class EAXExample
{
    public static void main(String[] args)
        throws Exception
    {
        SecretKey aesKey = createConstantKey();

        byte[] iv = Hex.decode("bbaa99887766554433221100");
        byte[] msg = Strings.toByteArray("hello, world!");

        System.out.println("msg  : " + Hex.toHexString(msg));

        byte[] cText = eaxEncrypt(aesKey, iv, msg);

        System.out.println("cText: " + Hex.toHexString(cText));

        byte[] pText = eaxDecrypt(aesKey, iv, cText);

        System.out.println("pText: " + Hex.toHexString(pText));
    }
}
```

如果一切运行正常，该示例应产生以下输出。

```
msg  : 68656c6c6f2c20776f726c6421
cText: 9153fdf091f0d023ab18645fd2eaa916f0b27f3b1eddf6afac6d950bc4
pText: 68656c6c6f2c20776f726c6421
```

虽然这两个示例都没有显示关联数据（associated data），但可以通过 `AEADParameterSpec` 或 `Cipher.updateAAD()` 方法添加关联数据。

与 GCM 和 CCM 一样，评估标签时的错误会导致在符合 Java 7 或更高版本的 JVM 中抛出 `AEADBadTagException`，或者在较早的 JVM 中抛出 `BadPaddingException` 异常。

### 其他 AEAD 模式

Bouncy Castle 还提供了在 [122] 中定义的 OCB 模式。OCB 模式最初被提出作为 CCM 更高效的替代方案，因为在产生相同效果的情况下，OCB 模式密码所需的块加密操作次数仅为 CCM 模式密码的一半。从编程的角度来看，你可以像处理 EAX 一样处理这种模式，尽管 Bouncy Castle 的实现固定用于 128 位块加密。

### 密钥封装算法 (Key Wrapping Algorithms)

密钥封装（Key wrapping）主要关于使用对称密钥来封装其他密钥。我们稍后看到使用非对称密钥加密对称密钥的示例，但此类操作实际上是为了密钥传输，而不是任何长期密钥存储(2。



在本节中，我们主要查看 NIST SP 800-38F 中定义的 NIST 标准密钥封装算法 [28]，这些算法围绕对称加密器的使用——具体到 NIST SP 800-38F 中，是 AES 和 Triple-DES。NIST SP 800-38F 中定义的密钥封装算法包含一些校验和信息，有助于确保解封后的密钥是实际封装的那个密钥，并且它们足够健壮，可以用于保护普通数据，这使得它们对于封装非对称密钥也有用——这些通常呈现为 ASN.1 DER 编码的二进制块（blobs）。健壮性源于算法的一个特性，这意味着最终封装编码中的每一个位都依赖于输入编码的每一个位。

### KW 模式

KW 模式是不带填充的基本封装模式。请注意，在这种情况下，数据必须按照所用加密器块大小的一半进行对齐。因此，在下面使用 AES 的情况下，我们需要确保输入密钥的编码是 8 字节的倍数，因为 AES 的块大小为 16 字节。

以下示例使用 JCE API 封装了一个 16 字节的 Blowfish 密钥。

```
 1 /**
 2  * KW 风格密钥封装示例 - 注意在这种情况下，输入必须
 3  * 按 8 字节边界对齐（对于 AES）。
 4  */
 5 public class KWExample
 6 {
 7     public static void main(String[] args)
 8         throws Exception
 9     {
10         SecretKey aesKey = createConstantKey();
11 
12         SecretKeySpec keyToWrap = new SecretKeySpec(
13             Hex.decode("00010203040506070706050403020100"), "Blowfish");
14 
15         // 封装密钥
16         Cipher wrapCipher = Cipher.getInstance("AESKW", "BC");
17 
18         wrapCipher.init(Cipher.WRAP_MODE, aesKey);
19 
20         byte[] cText = wrapCipher.wrap(keyToWrap);
21 
22         // 解封密钥
23         Cipher unwrapCipher = Cipher.getInstance("AESKW", "BC");
24 
25         unwrapCipher.init(Cipher.UNWRAP_MODE, aesKey);
26 
27         byte[] cText = wrapCipher.wrap(keyToWrap);
```

（注：KW 示例的输入包含大量重复的 `byte[] cText = wrapCipher.wrap(keyToWrap);`，已为了可读性进行了清理。）

### KWP 模式

KWP 模式定义了一种填充机制，允许我们在保持算法健壮性的同时规避块对齐。

这个示例的顺序稍微有点后，因为我们直到第 6 章才会查看 `KeyPairGenerator`、`KeyPair` 和 `PrivateKey` 类，但使用私密钥可以为示例提供可以使用的内容(3）。

Bouncy Castle 还支持 `RFC 3370` [83] 中定义的 IETF 密钥封装算法，这些算法最初源于 `RFC 3217` [82] 和 `RFC 3211` [81]。前两个适用于 `RC2` 和 `Triple-DES`。后者是一种基于 CBC 的更通用算法，适用于任何块加密器。

### SealedObject 类

除了提供调用密钥封装的 API 之外，JCE 还提供了一个简单的类，允许加密对象的传输和恢复。实现此项的类是 `javax.crypto.SealedObject`。

在创建 `SealedObject` 时，我们需要传入想要封装的序列化对象，以及我们希望用于执行封装的 `Cipher` 实例。该 `Cipher` 实例需要初始化为加密模式。请看下面的示例，它配置为在 `CCM` 模式下使用 `AES`：

```
 1 /**
 2  * An example of use of a SealedObject to protect a serializable object. In this
 3  * case we use a private key, but any serializable will do.
 4  */
 5 public class SealedObjectExample
 6 {
 7     public static void main(String[] args)
 8         throws Exception
 9     {
10         SecretKey aesKey = createConstantKey();
11 
12         // create our interesting serializable
13         KeyPairGenerator kpGen = KeyPairGenerator.getInstance("RSA", "BC");
14 
15         kpGen.initialize(2048);
16 
17         KeyPair kp = kpGen.generateKeyPair();
18 
19         // initialize the "sealing cipher"
20         Cipher wrapCipher = Cipher.getInstance("AES/CCM/NoPadding", "BC");
21 
22         wrapCipher.init(Cipher.ENCRYPT_MODE, aesKey);
23 
24         // create the sealed object from the serializable
25         SealedObject sealed = new SealedObject(kp.getPrivate(), wrapCipher);
26 
27         // simulate a "wire transfer" of the sealed object.
28         ByteArrayOutputStream bOut = new ByteArrayOutputStream();
29         ObjectOutputStream    oOut = new ObjectOutputStream(bOut);
31 
32         oOut.writeObject(sealed);
33 
34         oOut.close();
35 
36         SealedObject transmitted = (SealedObject)new ObjectInputStream(
37             new ByteArrayInputStream(bOut.toByteArray())).readObject();
38 
39         // unseal transmitted, extracting the private key
40         PrivateKey unwrappedKey =
41                        (PrivateKey)transmitted.getObject(aesKey, "BC");
42 
43         System.out.println("key: " + unwrappedKey.getAlgorithm());
44         System.out.println("   : " + Arrays.areEqual(
45                 kp.getPrivate().getEncoded(), unwrappedKey.getEncoded()));
46     }
47 }
```

注意，要调用 `SealedObject.getObject()`，我们只需要传入要使用的密钥以及我们所需的服务提供者名称。在内部，`SealedObject` 还通过 `Cipher.getParameters()` 存储算法规范以及 `Cipher` 返回的 `AlgorithmParameters` 对象的编码版本。然后它可以使用提供的提供者重新创建算法参数，并创建且初始化适用于恢复原始存储对象的 `Cipher` 实例。

运行此示例产生的输出应与之前的 KWP 封装示例相同：

```
key: RSA
   : true
```

这确认了 RSA 私钥已从 `SealedObject` 实例中成功提取。

### 总结

在本章中，我们查看了对称密钥加密中的一个新概念——“身份验证模式”。这允许在解密时验证数据流的正确性，并且在需要时允许对非加密文本（如标头）进行验证。

我们还学会了如何使用密钥封装和 `SealedObject` 类安全地传输密钥。

## 第 5 章：基于密码的密钥生成与密钥划分

基于密码的密钥生成和密钥划分代表了从一组输入最终获得单一秘密的两种方法。它们有不同的目的。在第一种情况下，我们获取用户知道的东西并用它来推导出我们想要使用的秘密。在第二种情况下，我们从想要使用的秘密开始，但通过将其部分分给不同的用户来隐藏它——其核心思想是必须有人数的人同时协作才能揭示原始秘密。这种实现方法需要追溯历史，使用拉格朗日在 1771 年提出的结果，该结果最终在 1861 年被证明适用于通用情况，并在 1979 年引起了密码学的关注。

我们将从第一种情况开始。

### 基于密码的密钥生成

在“获取易于记忆的内容并产生有效的对称密钥”的情况下，有一系列算法利用消息摘要和随机盐值来产生密钥。实现这一目标有多种技术，但大多数它们都是围绕消息摘要构建的。这些函数统称为基于密码的密钥派生函数，简称 `PBKDFs`。使用通过 `PBKDFs` 生成的密钥进行的加密简单被称为基于密码的加密，或 `PBE`。

#### PBKDF 的输入

除了密码外，`PBKDFs` 还需要盐和迭代次数，以及一个伪随机函数（`PRF`）。`PRF` 作为混合器将密码、盐和迭代次数结合在一起，并产生的字节流随后用于创建加密。通常 `PRF` 是消息摘要或 `HMAC`。

##### 密码

在 PBKDF 的输入中，只有密码是秘密的。重要的是密码是密钥熵的来源。正如常一样，密钥的熵是决定任何加密安全因素之一。换句话说，你可以使用 PBKDF 轻松生成 256 位流。然而，如果密码在 'a' 到 'z' 的范围内，不需要费费精力就能意识到只有 26 位流是可能的——实际上安全强度低于 5 位。

所以，非常短的密码不是好主意。

另一个考虑因素是密码总是被转换为字节数组以供给 `PRF` 并与其他组件混合。了解这种转换是如何发生的是有的。虽然某些算法将字符视为 16 位，而其他算法在处理之前会将字符转换为 `UTF-8`，但也有某些算法会将收到的任何输入按 7 位 `ASCII` 处理。这很重要，因为如果你试图利用非英语字符集，甚至是扩展字符集，你希望确保所有的努力都不会被 PBKDF 使用的转换器丢弃。

##### 盐

盐是一个公开值。盐始终是一个随机字节字符串，允许我们隐藏无意或故意的密码重复使用，因为使用盐会改变从 PBKDF 生成的密钥流。

盐可以是任何长度，但最好至少与 `PRF` 输出单个块时产生的大小一样。通常，这与支持 `PRF` 本身的关联 `HMAC` 或消息摘要的长度相同。这意味着任何可能用于攻击 PBKDF 的预计算哈希“彩虹表”都需要与 `PRF` 输出位长度处于数量级。这将创建足够的表来执行有意义的字典攻击变得极其困难甚至不可能。

##### 迭代次数

迭代次数也是一个公开值。迭代次数的唯一目的是增加将密码转换为密钥所需的计算时间，其核心思想是，如果使用 100 次迭代而不是 1 次，那么执行该计算的成本将增加 100 倍。

在 2000 年，1024 次的迭代次数似乎足够大了。而现在，你希望找到一个足够大的数字，既能让你对由于增加带来的延迟感到接受，又能增加攻击者在尝试猜测密码时面临的计算成本。

## 其他输入考量

最初，仅由迭代次数决定的 CPU 消耗量就足以对你的密码哈希算法的保护程度提供某种程度的确定性，前提是你的服务器是该区域内最强大的计算机。对于通用计算机来说，这可能仍然成立。然而，随着可编程 GPU 的出现以及对定制超大规模集成集成电路（VLSI）的便捷获取，已经不能简单地说，对于特种哈希计算机而言，你的服务器不再是该区域内最强大的计算机。事实上，对于传统的 PBKDFs，基于 VLSI 和 GPU 的自定义方法能够运行的迭代次数远高于普通服务器能够处理的任何水平。

如今，内存使用和其他难以扩展的因素也被纳入考量中，以保护密码哈希算法的结果。2013 年到 2015 年间，互联网上举办了一场密码哈希竞赛 [38]。获胜的是名为 `Argon2` 的算法，并对四位决赛者 `Catena`、`Lyra2`、`Makwa` 和 `yescrypt` 予以表扬。`Argon2` 尚未被加入 Bouncy Castle APIs，但 `yescrypt` 表扬的原因之一是它与名为 `scrypt` 的算法的关系，它是原始“额外成本”PBKDFs 之一之一且已存在于 BC APIs 中。我们稍后将介绍 `scrypt`。

## PKCS5 方案 2

在编写本文时，创建 PBKDF 最常用的技术是 PKCS #5 中描述的第二种方案，即 `PBKDF2`。其受欢迎的部分原因是由于该方案也被 NIST 推荐用于 SP 800-132 [35]。`PBKDF2` 使用 `HMAC` 作为 `PRF`。默认情况下，为 `HMAC` 提供底层摘要的消息摘要是 `SHA-1`，这表明了该算法的年代感。现在你至少会使用 `SHA-256` 或 `SHA-512`。

该算法遵循派生算法的经典模式，将密码、`salt` 和迭代次数作为输入，然后根据迭代次数反复应用特定的 `HMAC`。

### 使用 JCE 进行 PBKDF2

以下示例显示了如何创建一个 JCE `SecretKeyFactory`，该工厂支持 `PBKDF2` 并使用 `SHA-256` 作为 `PRF`。

```
 1   /**
 2    * 使用 BC JCE 提供者基于 SHA-256 使用 PBKDF2 计算派生密钥。
 3    *
 4    *
 5    * @param password 密码输入。
 6    * @param salt 盐参数。
 7    * @param iterationCount 迭代次数参数。
 8    * @return 派生密钥。
 9    */
10   public static byte[] jcePKCS5Scheme2(char[] password, byte[] salt,
11                                        int iterationCount)
12           throws GeneralSecurityException
13   {
14       SecretKeyFactory fact = SecretKeyFactory.getInstance(
15                               "PBKDF2WITHHMACSHA256","BC");
16 
17       return fact.generateSecret(
18               new PBEKeySpec(password, salt, iterationCount, 256))
19                                                                   .getEncoded();
20   }
```

### 使用 BC 低级 API 的 PBKDF2

`scrypt` 算法也可以通过 BC 低级 API 直接调用，使用 `PKCS5S2ParametersGenerator` 类。

```
 1   /**
 2    * 使用 BC 低级 API 基于 SHA-256 使用 PBKDF2 计算派生密钥。
 3    *
 4    *
 5    * @param password 密码输入。
 6    * @param salt 盐参数。
 7    * @param iterationCount 迭代次数参数。
 8    * @return 派生密钥。
 9    */
10   public static byte[] bcPKCS5Scheme2(char[] password, byte[] salt,
11                                       int iterationCount)
12   {
13       PBEParametersGenerator generator = new PKCS5S2ParametersGenerator(
14                                                           new SHA256Digest());
15 
16       generator.init(
17               PBEParametersGenerator.PKCS5PasswordToUTF8Bytes(password),
18               salt,
19               iterationCount);
20 
21       return ((KeyParameter)generator
22                               .generateDerivedParameters(256)).getKey();
23   }
```

注意该类接受消息摘要作为构造函数参数。该消息摘要用于确定在使用 `PBKDF2` 函数时使用哪种 `HMAC`。

## SCRYPT



# scrypt 算法

`scrypt` 算法最初由 Colin Percival 在 2009 年提出 [39]，随后由 RFC 7914 [126] 跟进。`scrypt` 算法内部使用 `PBKDF2`，但与 `PBKDF2` 的不同在于它增加了内存消耗。你可以看到，基于 GPU 的自定义方法 `scrypt` 能够运行远高于普通服务器能够处理的迭代次数。

如今，内存使用和其他难以扩展的因素也被纳入考量中，以保护密码哈希算法的结果。2013 年到 2015 年间，互联网上举办了一场密码哈希竞赛。获胜的是名为 `Argon2` 的算法，并对四位决赛者 `Catena`、`Lyra2`、`Makwa` 和 `yescrypt` 予以表扬。`Argon2` 尚未被加入 Bouncy Castle APIs，但 `yescrypt` 表扬的原因之一是它与名为 `scrypt` 的算法的关系，它是原始“额外成本” PBKDFs 之一且已存在于 BC APIs 中。我们稍后将介绍 `scrypt`。

## scrypt 算法流程

并不是简单的单轮哈希加盐，`scrypt` 算法被分为三步，第一步是使用密码生成一个长度为 ![(128 * r)](img/leanpub_equation_66) 字节的数组。

中间步骤对 `B` 数组中的每个块应用 `ROMIX` 函数。`ROMIX` 函数在 RFC 7914 中定义为基于 `Salsa20` 核心函数。

最后，再次将 `PBKDF2` 应用 `B` 数组。

你可以看到 `B` 数组的使用使得 `scrypt` 变成了“内存密集型”。选择参数时需要小心，因为算法会消耗内存，但这使得攻击者从生成的派生密钥猜测密码变得困难得多。

![scrypt - 派生密钥长度显示](img/ScryptDiag.png)

## 代码示例：使用 BC 低级 API 计算 SCRYPT 派生密钥

```java
/**
 * 使用 BC 低级 API 通过 SCRYPT 计算派生密钥。
 *
 * @param password 输入的密码。
 * @param salt 盐值参数。
 * @param costParameter 成本参数。
 * @param blocksize 块大小参数。
 * @param parallelizationParam 并发参数。
 * @return 派生密钥。
 */
public static byte[] bcSCRYPT(char[] password, byte[] salt,
                              int costParameter, int blocksize,
                              int parallelizationParam)
{
    return SCrypt.generate(
            PBEParametersGenerator.PKCS5PasswordToUTF8Bytes(password),
            salt, costParameter, blocksize, parallelizationParam,
            256 / 8);
}
```

# 其他 PBKDFs

Bouncy Castle 提供程序支持许多其他 PBKDF，包括 PKCS #12、PKCS #5 中指定的原始方案、原始的 OpenSSL PBKDF，以及 OpenPGP 中的方案。

# 密钥分割 Implementation (Key Splitting)

用于秘密共享的算法有很多，但在这里我们将介绍 Adi Shamir 在 1979 年 ACM 论文《如何共享秘密》（How to Share a Secret）中提出的秘密共享算法 [137]。

该算法涉及将秘密分成份额，其有趣之处在于：首先，当使用该算法分割秘密时，任何单独的份额都无法恢复秘密。其次，份额可以基于阈值进行分配，这意味着可以创建份额，使得只需要所有者中一定比例的人聚集在一起即可恢复秘密。因此，你经常看到该算法被称为 Shamir 门限方案（Shamir’s Threshold Scheme）。

## 基础算法

Shamir 算法的初始设置需要受信方持有某个秘密整数 ![S](img/leanpub_equation_67.png)，该秘密将分给 ![n](img/leanpub_equation_68.png) 个用户。我们还需要一个阈值 ![t](img/leanpub_equation_69.png)，这意味着从我们的共 ![n](img/leanpub_equation_71.png) 个用户组中选出的任意一组 ![t](img/leanpub_equation_70.png) 用户，都能够恢复秘密整数 ![S](img/leanpub_equation_72.png)。

接下来，受信方选择一个大于 `S` 和 `n` 的质数 `p`，并定义一个多项式 `{$$}f(x){$$}`，其系数 ![a_0](img/leanpub_equation_73.png) 到 ![a_{t-1}](img/leanpub_equation_74.png)，对于 ![i = 1](img/leanpub_equation_76.png) 到 ![t - 1](img/leanpub_equation_77.png)，满足 ![0 < a_i <= p - 1](img/leanpub_equation_75.png)，且 ![a_0 = S](img/leanpub_equation_78.png)。

最后，利用生成的多项式，受信方计算出 `n` 个份额 ![S_i = f(i) \mod p](img/leanpub_equation_79.png)，其中 ![i](img/leanpub_equation_80.png) 是份额的索引。然后将 ![S_i](img/leanpub_equation_81.png) 给用户 ![i](img/leanpub_equation_82.png)。

恢复份额则需要 ![t](img/leanpub_equation_83.png) 个用户聚集，并使用拉格朗日插值法（Lagrange Interpolation）计算秘密多项式的 ![a0](img/leanpub_equation_84.png)。`a0` 就是被恢复的秘密 ![S](img/leanpub_equation_85.png)。

除了将拉格朗日插值表示为质域上的运算外，该算法的实现相当直接。如果你对后续数学原理感兴趣，可以在 [1] 和 [2] 中找到更详细的解释，后者还包含了一个计算示例。

## 密钥分割的实现

以下代码提供了密钥分割的实现。在这里完整展示代码，部分是为了证明它并不极端复杂，另一方面是因为尽管它很有用，但我们尚未完全确定应该将其存放在 Bouncy Castle 的哪个位置。

该实现分为三个部分：用于存储分割秘密的载体类、实际的分割器，以及辅助插值计算的拉格朗日权重计算器。在实现代码之后，有一个短示例展示了如何将这三个例程结合在一起以分割和恢复秘密。这是组合实现的唯一方法吗？不是，但我们希望它能提供足够的解释，让你在需要时进行调整。

### 秘密分割载体

`SplitSecret` 类用于携带份额值，以便分发给被托有恢复秘密能力的各。正如你预期的，这些仅仅是用于多项式构建的选定质域上的大整数。

```java
/**
 * 用于存储分割秘密的 BigInteger 值的份额容器。
 */
public class SplitSecret
{
    private final BigInteger[] shares;

    /**
     * 构造函数。
     *
     * @param shares 初始秘密分割后的份额。
     */
    public SplitSecret(BigInteger[] shares)
    {
        this.shares = shares.clone();
    }

    /**
     * 返回与分割秘密关联的份额副本。
     *
     * @return 秘密份额数组。
     */
    public BigInteger[] getShares()
    {
        return shares.clone();
    }
}
```

### 秘密分割器

`ShamirSecretSplitter` 类提供了构建代表分割秘密的份额的核心逻辑。在配置了对等数量、阈值以及代表我们所工作域的质数阶后，我们可以使用 `split()` 方法划分传入的秘密，以创建相应数量的份额。

```java
/**
 * 一个基于 Shamir 方法的秘密分器。
 * <p>
 * 参考：Shamir, Adi (1979), "How to share a secret",
 * Communications of the ACM, 22 (11): 612-613.
 * </p>
 */
public class ShamirSecretSplitter
{
    private final int numberOfPeers;
    private final int k;
    private final BigInteger order;
    private final SecureRandom random;
    private final BigInteger[] alphas;
    private final BigInteger[][] alphasPow;

    /**
     * 在指定的域上创建一个 ShamirSecretSplitter 实例，
     * 以在指定数量的节点之间共享秘密。
     *
     * @param numberOfPeers 共享秘密的节点数量。
     * @param threshold 重构秘密时必须存在的节点数量。
     * @param field 代表我们所操作群的质数域。
     * @param random 随机源。
     */
    public ShamirSecretSplitter(
            int numberOfPeers, int threshold, BigInteger field,
            SecureRandom random)
    {
        this.numberOfPeers = numberOfPeers;
        this.k = threshold;
        this.order = field;
        this.random = random;

        // 预计算每个节点的幂。
        alphas = new BigInteger[numberOfPeers];
        alphasPow = new BigInteger[numberOfPeers][k];

        if (k > 1)
        {
            for (int i = 0; i < numberOfPeers; i++)
            {
                alphas[i] = alphasPow[i][1] = BigInteger.valueOf(i + 1);
                for (int degree = 2; degree < k; degree++)
                {
                    alphasPow[i][degree] = alphasPow[i][degree - 1]
                                      .multiply(alphas[i]);
                }
            }
        }
        else
        {
            for (int i = 0; i < numberOfPeers; i++)
            {
                alphas[i] = BigInteger.valueOf(i + 1);
            }
        }
    }

    /**
     * 给定秘密，生成随机系数（除了作为秘密的 a<sub>0</sub>
     * 并为每个隐私节点计算函数（每个节点被分配了专用的 `alpha`）。
     * 系数从 `(0, fieldSize)` 中随机选取。
     *
     * @param secret 要共享的秘密
     * @return 每个隐私节点的秘密份额
     */
    public SplitSecret split(BigInteger secret)
    {
        BigInteger[] shares = new BigInteger[numberOfPeers];
        BigInteger[] coefficients = new BigInteger[k];

        // D0: 对于每个份额
        for (int peerIndex = 0; peerIndex < numberOfPeers; peerIndex++)
        {
            shares[peerIndex] = secret;
        }

        coefficients[0] = secret;

        // D1 到 DT: 对于每个份额
        for (int degree = 1; degree < k; degree++)
        {
            BigInteger coefficient = generateCoeff(order, random);

            coefficients[degree] = coefficient;

            for (int peerIndex = 0; peerIndex < numberOfPeers; peerIndex++)
            {
                shares[peerIndex] = shares[peerIndex].add(
                                      coefficient
                                          .multiply(alphasPow[peerIndex][degree])
                                          .mod(order)
                                     ).mod(order);
            }
        }

        return new SplitSecret(shares);
    }

    // Shamir 的原始论文实际上将 [0, fieldSize) 作为系数可以
    // 取的范围，但这对于最高阶项是不正确的，因为这会产生降低
    // 该项阶数的效果。我们通过使用 (0, fieldSize) 等集合来防止这种情况。
    private static BigInteger generateCoeff(BigInteger n, SecureRandom random)
    {
        int nBitLength = n.bitLength();
        BigInteger k = new BigInteger(nBitLength, random);
        while (k.equals(BigInteger.ZERO) || k.compareTo(n) >= 0)
        {
            k = new BigInteger(nBitLength, random);
        }
        return k;
    }
}
```

### 拉格朗日权重计算器

`LagrangeWeightCalculator` 是用于重组秘密的工具类。注意在 `computeWeights()` 方法中，对 `activePeers` 的元素进行了空检查，因为某些节点可能缺失。

```java
/**
 * 用于给定域内给定数量节点计算拉格朗日权重的基础计算器。
 *
 * @param numberOfPeers 共享秘密的节点数量
 * @param field 群的域。
 */
public class LagrangeWeightCalculator {

    private final int numberOfPeers;
    private final BigInteger field;
    private final BigInteger[] alphas;

    /**
     * 在指定的域上构建计算器，以计算处理
     * 在指定数量节点之间秘密的权重。
     *
     * @param numberOfPeers 共享秘密的节点数量
     * @param field 群的域。
     */
    public LagrangeWeightCalculator(int numberOfPeers, BigInteger field)
    {
        this.numberOfPeers = numberOfPeers;
        this.field = field;
    }
}
```



this.alphas = new BigInteger[numberOfPeers];

for (int i = 0; i < numberOfPeers; i++)
{
    alphas[i] = BigInteger.valueOf(i + 1);
}

/**
 * 计算用于插值重构秘密的拉格朗日权重。
 *
 * @param activePeers 可用的节点数组，如果节点不存在则为 null。
 * @return 拉格朗日权重
 */
public BigInteger[] computeWeights(Object[] activePeers)
{
    BigInteger[] weights = new BigInteger[numberOfPeers];
    for (int i = 0; i < numberOfPeers; i++)
    {
        if (activePeers[i] != null)
        {
            BigInteger numerator = BigInteger.ONE;
            BigInteger denominator = BigInteger.ONE;
            for (int peerIndex = 0; peerIndex < numberOfPeers; peerIndex++)
            {
                if (peerIndex != i && activePeers[peerIndex] != null)
                {
                    numerator = numerator.multiply(alphas[peerIndex]).mod(field);
                    denominator = denominator.multiply(alphas[peerIndex].subtract(alphas[i]).mod(field)).mod(field);
                }
            }
            weights[i] = numerator.multiply(denominator.modInverse(field)).mod(field);
        }
    }
    return weights;
}

#### 整合在一起

最后我们将它们整合在一起。

以下代码展示了如何使用拉格朗日权重计算器期望的方法重组秘密，并给了一个生成秘密的简单用法示例。运行此代码应该会在输出中产生 `matched: true` 字样。

```java
/**
 * 使用 ShamirSecretSplitter 和
 * LagrangeWeightCalculator 对 BigInteger 密钥进行分割和恢复的简单示例。
 */
public class ShamirExample
{
    // 恢复共享密钥。
    // 注意：我们使用 activeShares 数组中份额的位置来
    // 确定其在 f(i) 函数中的索引值。
    static BigInteger recoverSecret(BigInteger field, BigInteger[] activeShares)
    {
        LagrangeWeightCalculator lagrangeWeightCalculator = new LagrangeWeightCalculator(activeShares.length, field);
        BigInteger[] weights = lagrangeWeightCalculator.computeWeights(activeShares);

        // 加权
        int index = 0;
        while (weights[index] == null)
        {
            index++;
        }
        BigInteger weightedValue = activeShares[index].multiply(weights[index]).mod(field);
        for (int i = index + 1; i < weights.length; i++)
        {
            if (weights[i] != null)
            {
                weightedValue = weightedValue.add(activeShares[i].multiply(weights[i]).mod(field)).mod(field);
            }
        }
        return weightedValue;
    }

    // 创建一个新的份额数组，仅包含索引列出的份额，其他条目为 null。
    private static BigInteger[] copyShares(int[] indexes, BigInteger[] shares)
    {
        // 注意：activeShares 数组的大小需要与 shares 数组相同。
        // 份额的顺序是重要的。
        BigInteger[] activeShares = new BigInteger[shares.length];
        for (int i = 0; i != indexes.length; i++)
        {
            activeShares[indexes[i]] = shares[indexes[i]];
        }
        return activeShares;
    }

    /**
     * 创建共享密钥并为素数域 p 生成一个多项式以进行分割，然后展示密钥的恢复。
     */
    public static void main(String[] args)
    {
        SecureRandom random = new SecureRandom();
        BigInteger p = new BigInteger(384, 256, random);
        int numberOfPeers = 10;
        int threshold = 4;
        byte[] secretKey = new byte[32];
        random.nextBytes(secretKey);
        BigInteger secretValue = new BigInteger(1, secretKey);
        ShamirSecretSplitter splitter = new ShamirSecretSplitter(numberOfPeers, threshold, p, random);
        SplitSecret secret = splitter.split(secretValue);
        BigInteger[] s = secret.getShares();
        BigInteger recoveredSecret = recoverSecret(p, copyShares(new int[] { 1, 2, 3, 7 }, s));
        System.err.println(Hex.toHexString(BigIntegers.asUnsignedByteArray(secretValue)));
        System.err.println(Hex.toHexString(BigIntegers.asUnsignedByteArray(recoveredSecret)) + ", matched: " + secretValue.equals(recoveredSecret));
    }
}
```

值得注意的是，权重计算器是使用 `active` 份额数组的长度配置的，但该值仅用于确定跨份额数组的计算。如果活动份额数组长度短于原始分发的实际份额数量，你仍然会获得相同的计算权重，因此权重计算器实际上只需要知道正在处理的活动节点集中的最大索引，而不是原始的最大索引。

### 总结

在本章中，我们查看了从多个输入源获取并创建密钥的两种基本方法。基于密码的密钥生成允许使用用户创建的数据派生密钥。密钥分割从密钥开始，然后将其分成碎片分给多个方。

我们详细检查了如何使用 `JCE` 和 `BouncyCastle` 底层 API 通过 `PKCS5` 和 `SCRYPT` 从用户输入数据创建密钥。

最后，我们详细介绍了使用 `Shamir’s` 门限方案的密钥分割算法。

## 第 6 章：签名

本章介绍了公钥加密的使用，以及它如何应用于数字签名的创建和验证。我们还将查看密钥对的生成和密钥导入。

### 密钥对的生成与导入

在 Java 中任何关于公钥或非对称加密的讨论都必须从生成和构建公钥的基础类的讨论开始。

`JCA` 为非对称密钥提供了两个基础接口：

- `java.security.PublicKey`
- `java.security.PrivateKey`

非对称密钥对使用 `java.security.KeyPairGenerator` 类生成。在查看每个算法时，我们将看到密钥对生成的示例。另一个需要了解的类是 `java.security.KeyFactory`。该类用于从外部源导入密钥并进行转换，以便与特定的提供程序配合。

下面的短方法展示了如何根据给定算法和密钥规范从密钥规范生成公钥：

```java
/**
 * 根据 keySpec 中的细节返回用于算法构建的公钥。
 * @param algorithm 密钥规范所属的算法。
 * @param keySpec 持有公钥细节的密钥规范。
 * @return 用于算法的 PublicKey
 */
public static PublicKey createPublicKey(String algorithm, KeySpec keySpec) throws GeneralSecurityException
{
    KeyFactory keyFact = KeyFactory.getInstance(algorithm, "BC");
    return keyFact.generatePublic(keySpec);
}
```

你也可以执行等任务来创建私钥：

```java
/**
 * 根据 keySpec 中的细节返回用于算法构建的私钥。
 * @param algorithm 密钥规范所属的算法。
 * @param keySpec 持有私钥细节的密钥规范。
 * @return 用于算法的 PrivateKey
 */
public static PrivateKey createPrivateKey(String algorithm, KeySpec keySpec) throws GeneralSecurityException
{
    KeyFactory keyFact = KeyFactory.getInstance(algorithm, "BC");
    return keyFact.generatePrivate(keySpec);
}
```



`KeyFactory` 方法能够处理 ASN.1 编码，例如你可能在证书编码或 PKCS #12 文件中找到它们。我们稍后会看到这些编码的规范。目前只需了解公钥编码可以通过 `PublicKey.getEncoded()` 产生，并使用 `X509EncodedKeySpec` 对象传递给 `KeyFactory.generatePublic()` 方法；私钥编码可以通过 `PrivateKey.getEncoded()` 产生，并使用 `PKCS8EncodedKeySpec` 对象传递给 `KeyFactory.generatePrivate()`。

除了携带 ASN.1 编码的规范外，我们看到某些算法具有特定的规范类型，用于携带构建其公钥和私钥所需的值。

## 数字签名

数字签名方案通常是混合方案，它们使用私钥创建签名，其中签名的计算过程包含了签名所应用的数据的哈希，或者持有该数据哈希的某种编码表示。数字签名的核心思想是将一段公共信息（在本例中为被签名的文档/消息）与一段私有信息（签名者的私钥）绑定，以便他人能够通过使用签名者的公钥来确认私有信息的持有者对该绑定负责。

数字签名分为两种类型：确定性和非确定性。包括 `DSA` 在内的若干种算法依赖于使用随机值来保护签名者的私钥，导致同一方对同一份文档生成的任何两个签名都不相同。而其他算法（包括基于 `RSA` 的算法）则产生确定性签名，当签名密钥和被签名的文档相同时，生成的签名总是看起来是一样的。

## 签名安全强度

在选择数字签名的密钥大小和哈希算法时，考虑因素之一是各个组件部分的安全强度。在查看 Bouncy Castle 和 `JCA` 支持的算法之前，值得短暂停一下，看看涉及算法的相对安全强度。在我们的案例中，我们将仅查看 `SP 800-57` [32] 中发布的 NIST 算法，因为这些数据易于获取。签名的安全性取决于使用的公钥算法、公/私钥对的密钥大小以及使用的消息摘要。

`SP 800-57` 中的表 3 给出了不同摘要算法的安全强度如下：

### 摘要算法安全强度

| 摘要算法 | 安全强度（位 bits） |
| --- | --- |
| `SHA-1` | <= 80 |
| `SHA-224`, `SHA-512/224`, `SHA3-224` | 112 |
| `SHA-256`, `SHA-512/256`, `SHA3-256` | 128 |
| `SHA-384`, `SHA3-384` | 192 |
| `SHA-512`, `SHA3-512` | 256 |

对于表中未描述的摘要算法，你可以将其作为一个起点，但尝试从此表推断到其他摘要算法时应保持谨慎。首先要意识到，摘要的强度既与其输出大小有关，也与其压缩函数中使用的内部缓冲区有关。其次要意识到的是，对算法的研究和分析可能还会显示其他因素也适用，并且在使用算法时需要考虑在内。例如，在用于签名的情况下，虽然 `SHA-1` 明显低于当前 `FIPS` 要求的 112 位安全级别，但 `SHA-1` 与公钥算法结合使用时的安全性仍存在争议，因此验证基于 `SHA-1` 的签名具有潜在风险，但可能可以接受。另一方面，在 `FIPS` 下不再允许生成新的 `SHA-1` 签名，因为现在有了许多更优且易于使用的算法。

适用于 NIST 标准的公钥算法在 `SP 800-57` 的表 2 中描述如下：

### 公钥算法安全强度

| 公钥算法 | 密钥大小 | 安全强度（位 bits） |
| --- | --- | --- |
| `DSA` | 1024 | <= 80 |
| `DSA` | 2048 | 112 |
| `DSA` | 3072 | 128 |
| `DSA` | 7680^(4) | 192 |
| `DSA` | 15360⁴ | 256 |
| `RSA` | 1024 | <= 80 |
| `RSA` | 2048 | 112 |
| `RSA` | 3072 | 128 |
| `RSA` | 7680^(5) | 192 |
| `RSA` | 15360⁵ | 256 |
| `ECDSA` | 160-223 | <= 80 |
| `ECDSA` | 224-255 | 112 |
| `ECDSA` | 256-383 | 128 |
| `ECDSA` | 384-511 | 192 |
| `ECDSA` | 512+ | 256 |

在使用公钥加密时，通用规则是尽量让公钥算法成为最弱的一环，因此要尝试始终使用至少与所用公钥同强的摘要算法。同样，如果签名生成过程中涉及某些函数（如掩码生成函数），你也希望用于掩码生成函数的摘要其安全性至少与签名中的摘要相同。某项特性的安全性“存在争议”引入了未来某个日期可能需要道歉并在匆忙中重新进行工程设计的可能性——这真的应该尽量避免。

## 签名类

`JCA` 中与签名创建和验证相关的服务通过 `Signature` 类提供，该类位于 `java.security` 包中。与其他 `JCA` 类一样，`Signature` 类型的对象不是直接创建的，而是通过 `getInstance()` 方法创建的。由于签名算法通常涉及消息摘要，标准的格式已演变为：

`<摘要>with<算法>`

例如，`SHA256withDSA` 是使用 `DSA` 的 `SHA256`，而 `SHA512withRSA` 是使用 `RSA` 的 `SHA512`。`Signature` 对象的初始化部分取决于该对象是用于创建签名还是验证。在创建签名的情况下（即私钥操作），使用 `initSign()` 方法。在签名验证的情况下（即公钥操作），调用 `initVerify()` 方法并传入公钥或 `Certificate` 对象。有时签名算法还需要参数，如果是这样，还需要调用带有 `AlgorithmParameterSpec` 的 `setParameter()` 方法。

一旦 `Signature` 对象初始化，与生成或验证签名的数据将传递给相应的 `update()` 方法。一旦所有数据都传递给 `Signature` 对象，如果对象是用于签名生成的，则使用 `sign()` 方法。如果对象是用于签名验证的，则调用 `verify()` 方法并传入原始使用源者私钥生成的签名字节数组。

本质上三个步骤：初始化、更新，然后签名或验证。

## 数字签名算法

数字签名算法 (`DSA`) 追溯到 1991 年，是 NIST 发布 `FIPS 186` [21] 时第一个签名算法，该标准描述了一个围绕 `DSA` 算法构建的标准，被称为数字签名标准或 `DSS`。DSS 现在由 `FIPS 186-4` [22] 描述，涵盖了更广泛的签名算法，但原始的 `DSA` 仍在，尽管密钥比最初规定的大得多。

![签名验证和生成的示意图](img/chapter6----RegDSA.png)

签名验证和生成的示意图

DSA 类型的签名始终由两个整数 ![R](img/leanpub_equation_86.png) 和 ![S](img/leanpub_equation_87.png) 组成，它们通常由被签数据的哈希、私钥和一个随机值生成。生成 DSA 签名时使用秘密随机值意味着 DSA 算法的行为通常是非确定性的。

### 基于大整数的 DSA

`DSA` 密钥对基于一组参数 (P, Q, G)，这些参数具有以下特征：

*   ![P](img/leanpub_equation_88.png): 位长度属于集合 (1024, 2048, 3072) 的素数。
*   ![Q](img/leanpub_equation_89.png): ![(P - 1)](img/leanpub_equation_90.png) 的一个质因子，其位长度属于 (160, 224, 256) 集合。选择哪种位长度取决于 ![P](img/leanpub_equation_91.png) 的位长度。160 仅在 ![P](img/leanpub_equation_92.png) 位长度为 1024 时使用；当 ![P](img/leanpub_equation_93.png) 长度为 2048 时，可以使用 224 或 256；而对于 ![P](img/leanpub_equation_94.png) 长度为 3072 时，只能使用 256。
*   ![G](img/leanpub_equation_95.png): 伽罗瓦域 ![GF(P)](img/leanpub_equation_97.png) 乘群中阶为 ![Q](img/leanpub_equation_96.png) 的子群的生成元，使得 ![1 < G < P](img/leanpub_equation_98.png)。

在 Java 中，这些参数封装在 `java.security.spec.DSAParameterSpec` 对象中，并用于生成密钥。这些参数可以在密钥对生成器内部生成，或者你可以传入预定义的参数，或者是使用 `java.security.AlgorithmParameterGenerator` 生成的参数。以下是一个生成适用于 2048 位密钥参数 set 的简单示例。

```java
/**

 * 返回一组生成的、适用于创建 2048

 * 位密钥的 DSA 参数。

 *

 * @return 持有生成参数的 DSAParameterSpec。

 */

public static DSAParameterSpec generateDSAParams()

    throws GeneralSecurityException

{

    AlgorithmParameterGenerator paramGen =

        AlgorithmParameterGenerator.getInstance("DSA", "BC");

    paramGen.init(2048);

    AlgorithmParameters params = paramGen.generateParameters();

    return params.getParameterSpec(DSAParameterSpec.class);

}
```

生成 DSA 参数的算法描述在 FIPS PUB 186-4 中。它是有效的，但如果你尝试使用上述方法，你会发现它并不快。

### 密钥对生成

密钥对生成涉及创建一个公值（称为 ![Y](img/leanpub_equation_99.png)）和一个私值（称为 ![X](img/leanpub_equation_100.png)）。私有值 ![X](img/leanpub_equation_101.png) 是随机生成的，满足 ![0 < X < Q](img/leanpub_equation_102.png)，而 ![Y](img/leanpub_equation_103.png) 计算为 ![Y = G^{X} \mod P](img/leanpub_equation_104.png)。私有值 ![X](img/leanpub_equation_105.png) 然后被配合密钥参数用于创建签名，而 ![Y](img/leanpub_equation_106.png) 值则配合参数用于验证签名。

在 Java 中，生成密钥对最基本的方法是直接指定大小。

```java
/**

 * 使用基于提供者的参数生成一个 2048 位 DSA 密钥对。

 *

 * @return 一个 DSA KeyPair

 */

public static KeyPair generateDSAKeyPair()

    throws GeneralSecurityException

{

    KeyPairGenerator keyPair = KeyPairGenerator.getInstance("DSA", "BC");

    keyPair.initialize(2048);

    return keyPair.generateKeyPair();

}
```

在这种情况下，生成密钥对的服务将选择或生成一组支持生成 2048 位密钥的参数集。如果它正在生成参数集，可能会有明显的时间延迟。创建 DSA 参数是非常耗销的。如果你愿意，也可以通过 `DSAParameterSpec` 指定自己的参数生成密钥，利用接收 `AlgorithmParameterSpec` 的 `KeyPairGenerator.initialize()` 方法。我们可以通过将代码修改为如下形式，调整上一个示例中的 `generateDSAKeyPair()` 方法来实现此点：

```java
/**

 * 使用我们自定义的参数生成 DSA 密钥对。

 *

 * @param dsaSpec 用于密钥生成的 DSA 参数。

 * @return 一个 DSA KeyPair

 */

public static KeyPair generateDSAKeyPair(DSAParameterSpec dsaSpec)

    throws GeneralSecurityException

{

    KeyPairGenerator keyPair = KeyPairGenerator.getInstance("DSA", "BC");

    keyPair.initialize(dsaSpec);

    return keyPair.generateKeyPair();

}
```

然后传入从 `generateDSAParams()` 方法返回的 `DSAParameterSpec`。在这两种情况下，`KeyPair` 都由来自 `java.security` 包的 `DPublicKey` 和 `DSrivateKey` 组成。

### 签名生成

DSA 的安全性来源于离散对数问题，但略有不同。DSA 签名由 ![R](img/leanpub_equation_10.png) 和 ![S] 组成，它们是通过以下步骤随机随机值

1. 生成一个随机的 ![K](img/leanpub_equation_11.png)，满足 ![0 < K < Q](img/leanpub_equation_12.png)
2. 计算 ![R = G^{K} \mod P](img/leanpub_equation_13.png)
3. 计算 ![S = k^{-1}(H(m) + xr) \mod Q](img/leanpub_equation_14.png)

其中 ![H(m)] 是消息的哈希值。考虑到所有这些，创建 DSA 名的 Java 代码非常简单。以下示例使用 SHA-256 消息摘要创建 DSA 签名。

```java
/**

 * 使用传入的私钥和输入数据生成编码后的签名。

 * @param dsaPrivate 用于生成签名的私钥。

 * @param input 需要签名的输入数据。

 * @return 编码后的签名。

 */

public static byte[] generateDSASignature(PrivateKey dsaPrivate, byte[] input)

    throws GeneralSecurityException

{

    Signature signature = Signature.getInstance("SHA256withDSA", "BC");

    signature.initSign(dsaPrivate);

    signature.update(input);

    return signature.sign();

}
```

你会注意到 `signature.sign()` 返回一个 `byte[]`，你可能在好奇 ![R] 和 ![S] 发生了什么。在这种情况下 ![R] 和 ![S] 以 ASN.1 INTEGER 对象的形式位于 ASN.1 SEQUENCE 中。请记住 ASN.1 INTEGER 是符号符号，因此 DSA 签名的长度可能会略有不同，取决于一个或两个分量整数中是否存在符号位。

### 签名验证

DSA 的验证稍微复杂一些，在假设输入通过验证的情况下，需要以下步骤：

1. 计算 ![W = s^{-1} \mod Q]
2. 计算 ![U_1 = (W * H(m)) \mod Q]
3. 计算 ![U_2 = (RW) \mod Q]
4. 计算 ![V = ((G^{U_1}Y^{U_2}) \mod P) \mod Q]
5. 验证 = (V == R)

再次，在 Java 中，这一切都“在内部”完成，验证由我们的签名生成示例生成的 DSA 签名的过程如下：

```java
/**

 * Return true if the passed in signature verifies against

 * the passed in DSA public key and input.

 *

 * @param dsaPublic the public key of the signature creator.

 * @param input the input that was supposed to have been signed.

 * @param encSignature the encoded signature.

 * @return true if the signature verifies, false otherwise.

 */

public static boolean verifyDSASignature(

    PublicKey dsaPublic, byte[] input, byte[] encSignature)

    throws GeneralSecurityException

{

    Signature signature = Signature.getInstance("SHA256withDSA", "BC");

    signature.initVerify(dsaPublic);

    signature.update(input);

    return signature.verify(encSignature);

}
```



虽然这应该是显而易见的，但生成 DSA 签名的第三方库中一个常见错误是忘记签名中的组件整数是有符号的。如果你有一个本应可以通过验证的签名但却没有通过，最可能的原因是该 DSA 签名在最初创建时假设整数是无符号的，并且其中一个整数的最高位被置位，导致它变成了一个负数。对上述验证数值步骤的审查表明，如果 `R` 或 `S` 任何一个为负值，结果将不会理想。如果你面临这种情况且无法修复第三方库，可以使用 Bouncy Castle ASN.1 库对签名进行预处理，使用正确的 ASN.1 INTEGER 值将其重新编码为 ASN.1 SEQUENCE，然后将结果的字节数组传递给 `Signature` 类进行验证。

下面的实用方法展示了使用 Bouncy Castle ASN.1 库进行这种重编码的其中一种方法。

```java
/**
 * Fix a faulty DSA signature that has been encoded using
 * unsigned integers.
 *
 * @param encSignature the encoded signature.
 * @return the corrected signature with signed integer components.
 */
public static byte[] patchDSASignature(byte[] encSignature)
    throws IOException
{
    ASN1Sequence sigSeq = ASN1Sequence.getInstance(encSignature);

    ASN1EncodableVector sigV = new ASN1EncodableVector();

    // fix R
    sigV.add(new ASN1Integer(
        ASN1Integer.getInstance(sigSeq.getObjectAt(0)).getPositiveValue()));

    // fix S
    sigV.add(new ASN1Integer(
        ASN1Integer.getInstance(sigSeq.getObjectAt(1)).getPositiveValue()));

    return new DERSequence(sigV).getEncoded();
}
```

当然，如果能让产生错误编码的机构改进他们的做法，总是更好的。在某些情况下这并不总是可能的，在这种情况下重新编码是必要的。

## 基于椭圆曲线的 DSA

椭圆曲线上的 DSA，简称为 ECDSA，最初描述于 X.962 [67]，现在也涵盖于 FIPS PUB 186-4 [22]。

ECDSA 定义在两个有限域上：域 `GF_p` 和域 `GF_{2^m}`。这两个域的区别在于操作的方式。在 `GF_p` 的情况下，操作是对奇质数取模的；在 `GF_{2^m}` 的情况下，操作是对不可约多项式取模。对于我们，我们通过选择特定的曲线来生成密钥，决定使用哪种公式。在 FIPS PUB 186-4 中，所有的 `GF_p` 曲线都以“P-” 开头，而 `GF_{2^m}` 字段以“B-” 或 “K-” 开头。在这种情况下，“K-” 表示 Koblitz 曲线，它是 `GF_{2^m}` 的一个特例。

在 Java 中，不同曲线的域参数可以通过名称定义（使用 `java.security.spec.ECGenParameterSpec` 类），也可以通过组件值定义（使用 `java.security.spec.ECParameterSpec` 参数规范类）。

### 密钥对生成

选择特定曲线的域参数后，生成密钥对涉及生成秘密值 `d`，然后计算出一个作为公钥的点 `Q`。`Q` 作为公钥。

## 4 计算 `S = (K^{-1} (H(m) + dR) \mod N)`

其中 `H(m)` 再次是我们要签名的消息哈希，而 `N` 是 EC 曲线的阶。下面的示例展示了之前见过的 `SHA-256` 的用法，你可以看到 JCA 的步骤与普通的 DSA 相同。

```java
/**
 * 使用传入的 EC 私钥和输入数据生成编码的 ECDSA 签名。
 *
 *
 * @param ecPrivate 用于生成签名的私钥。
 * @param input 要签名的输入。
 * @return 编码后的签名。
 */
public static byte[] generateECDSASignature(
    PrivateKey ecPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withECDSA", "BC");

    signature.initSign(ecPrivate);

    signature.update(input);

    return signature.sign();
}
```

同样的方法也用于签名的编码。由于由于的步骤返回的是整数 `R` 和 `S`，`signature.sign()` 调用也返回了一个包含两个 ASN.1 INTEGER 对象的 ASN.1 SEQUENCE 编码。

### 签名验证

使用 ECDSA 进行验证比使用 DSA 稍微复杂，因为过程中的某个中间步骤可能会产生无效的 EC 点。对于 ECDSA，在假设输入有效的情况下，验证签名需要以下步骤：

1. 计算 `W = s^{-1} \mod N`
2. 计算 `U_1 = (W * H(m)) \mod N`
3. 计算 `U_2 = (RW) \mod N`
4. 计算 `(x, y) = {U_1}G + {U_2}Q`。如果 `((x, y)` 位于 `\infty)`，则返回无效。
5. `verified = (x == R)`

以下是上述生成方法的签名验证示例。

```java
/**
 * 如果传入的 ECDSA 签名通过传入的 EC 公钥和输入的验证，则返回 true。
 *
 *
 * 6    * @param ecPublic 签名创建者的公钥。
 * @param input 原本应该签名的输入。
 * @param encSignature 编码后的签名。
 * @return 如果签名通过验证，则返回 true，否则返回 false。
 */
public static boolean verifyECDSASignature(
    PublicKey ecPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withECDSA", "BC");

    signature.initVerify(ecPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

请注意，针对 DSA 的关于第三方库错误编码签名的警告也同样适用于 ECDSA。

### 确定性 DSA (DDSA/ECDDSA)

正如我们之前所见，DSA 依赖于使用随机数 `K`，该数也必须保密。它的缺点之一是用相同的密钥对同一文档重新签名会产生不同的签名，因为签名是非确定的。这种不确定性由于使用了随机的 `K` 值。RFC 6979 [118] 中描述了创建确定性 DSA 签名的方法。使用的“技巧”是计算 `K` 而不是使用随机数，而是以一种与私钥一样保密的方式计算 `K`。由于 `K` 仅在生成 DSA 签名时需要，这意味着使用 DSA 确定性公式生成的签名可以被任何其他 DSA 实现所验证。在 Bouncy Castle 中，确定性 DSA 的两种公式分别名为 DDSA 和 ECDDSA。

下面的方法生成一个 ECDDSA 签名，而不是 ECDSA 签名。

```java
/**
 * 使用传入的 EC 密钥和输入生成编码的确定性 ECDSA (ECDDSA) 签名。
 *
 *
 * @param ecPrivate 用于生成签名的私钥。
 * @param input 要签名的输入。
 * @return 编码后的签名。
 */
public static byte[] generateECDSASignature(
    PrivateKey ecPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withECDSA", "BC");

    signature.initSign(ecPrivate);

    signature.update(input);

    return signature.sign();
}
```

Edwards 曲线已经出现了一段时间，IETF 在发布 `RFC 8032` 时发布了正式标准 [130]。在 DSA 中使用 Edwards 曲线与常规的 ECDSA 在两个层面上有所不同。第一，每条曲线只能使用一种摘要算法，而且除了要签名的消息外，还需要一些额外的输入在摘要中对其进行哈希处理。第二，签名的安全性不依赖于为每个生成的签名使用唯一的随机数——签名是确定性的。曲线的公式还应该使涉及它们的计算对侧信道攻击具有更强的韧性。

EdDSA 指定了两种不同签名强度的曲线。第一条曲线 `Ed25519` 旨在提供 128 位的安全性，第二条曲线 `Ed448` 提供约 224 位的安全性。`Ed448` 是为那些愿意牺牲部分性能以更好地防御针对曲线结构的分析攻击的应用提供的。`Ed25519` 使用 `SHA-512` 作为摘要算法，而 `SHA-3` 算法 `SHAKE-256` 被用作 `Ed448` 的摘要算法。

### 密钥对生成

可以通过为感兴趣的特定曲线创建 `KeyPairGenerator`（使用字符串“Ed25519”或字符串“Ed448”）来生成 EdDSA 的密钥对。

以下示例显示了 `Ed448` 的密钥对生成：

```java
/**
 * Generate a EdDSA key pair for Ed448.
 *
 * @return a EdDSA KeyPair
 */
public static KeyPair generateEd448KeyPair()
    throws GeneralSecurityException
{
    KeyPairGenerator keyPair = KeyPairGenerator.getInstance("Ed448", "BC");

    return keyPair.generateKeyPair();
}
```



携带 EdDSA 密钥的 `KeyPair` 将由 `org.bouncycastle.jcajce.interfaces` 包中的 `EdDSAKey` 接口实现组成。

### 签名生成

除了要签名的消息外，签名生成过程还会接收一个上下文 `C`。上下文 `C` 旨在将正在生成的签名锁定到特定的用途，并且签名者和验证者都需要知道它。它可以是空的，但如果不为空，则长度不能超过 255 字节。由于之前有 `Ed25519` 的定义，`RFC 8032` 规定了 3 个版本的 `Ed25519` 以及 2 个版本的 `Ed448`。与 `RFC 8032` 最相关的两种签名方案的两个版本引入了上下文，并专门处理对待签名消息的预哈希，以允许这些方案用于非常大的消息。由于很快就会介绍的原因，`RFC 8032` 建议仅在严格必要时才使用预哈希。

我们不会详细介绍 `RFC 8032` 中签名生成算法的具体细节，因为它们随每种曲线而异，但下面的概述指示了签名生成的实际工作原理。给定一个特定曲线的哈希方案 `Hash()`、一个 0 到 255 字节的上下文 `C` 以及以字节为单位的上下文长度 `CLen`，过程大致如下：

1.  对于预哈希版本的算法，将 `F` 设置为 `0`；如果直接使用消息，则将 `F` 设置为 `1`。
2.  将 `DOM` 设置为 `classifier \parallel OCTET(F) \parallel OCTET(CLen) \parallel C`，其中对于 `Ed448` 分类为“SigEd448”，对于 `Ed25519` 分类为“SigEd25519 no Ed25519 collisions”，这两个字符串均以 ASCII 编码。`OCTET()` 函数简单地将其参数转换为单个字节。
3.  对私钥进行哈希，将结果分为两部分，`H1` 和 `H2`。
4.  设置 `S = (H1 \parallel A)`，其中 `A` 是字节数组形式的公钥。
5.  将前缀值 `P` 设置为 `H2`。
6.  将 `r` 设置为 `Hash(DOM(F, C) \parallel P \parallel M)` 得到的小端整数，其中如果直接使用消息，则将 `F` 设置为 `1`。
7.  将前缀值 `P` 设置为 `H2`。
8.  将 `r` 设置为 `Hash(DOM(F, C) \parallel P \parallel M)` 得到的小端整数，其中如果直接使用消息，则将 `F` 设置为 `1`。

### 签名验证

3. 检查 `S * B = R + k * A'`，其中 `B` 是曲线的基点，而 `A'` 是作为点的公钥。

在 JCA 中，密钥类型再次被用于确定正在处理的是哪类型的 EdDSA 签名，你可以看到下面的示例代码遵循了通常的模式：

```java
/**
 * 如果传入的 EdDSA 签名通过传入的
 * EdDSA 公钥和输入的验证，则返回 true。
 *
 * @param edPublic 签名创建者的公钥。
 * @param input 应该签名的输入。
 * @param encSignature 编码后的签名。
 * @return 如果签名通过验证，否则返回 false。
 */
public static boolean verifyEdDSASignature(
    PublicKey edPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("EdDSA", "BC");

    signature.initVerify(edPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

当你需要将使用的签名锁定到特定的曲线时，可以使用“Ed25519”和“Ed448”作为传递给 `Signature.getInstance()` 的签名算法名称。

### DSTU 4145

DSTU 4145 [46] 发布 2002 年，是一种基于椭圆曲线的乌克兰标准。目前该标准尚未发布 RFC，但据报道已用于 PDF 签名和 CMS 消息。

### 密钥对生成

DSTU 4145 提供了 10 组曲线参数集，编号从 0 到 9，它们基于基础分支“1.2.804.2.1.1.1.1.3.1.1.2”。以下代码将为其中一组参数集设置并初始化 `KeyPairGenerator`。内部密钥对的生成涉及生成私有值 `d` 和公点 `Q`，它是该密钥对公钥的依据。

```java
/**
 * 为传入的命名参数集生成一个 DSTU 4145-2002 密钥对。
 *
 * @param curveNo 要使用的曲线编号（范围 [0-9]）
 * @return 一个 EC KeyPair
 */
public static KeyPair generateDSTU4145KeyPair(int curveNo)
    throws GeneralSecurityException
{
    KeyPairGenerator keyPair = KeyPairGenerator.getInstance(
                                "DSTU4145", "BC");

    keyPair.initialize(
        new ECGenParameterSpec("1.2.804.2.1.1.1.1.3.1.1.2." + curveNo));

    return keyPair.generateKeyPair();
}
```

我们应该通过这个例子指出，如果有更友好的命名方式，我们很乐意听到，但我们至少确定使用 OBJECT IDENTIFIER（对象标识符）弧是正确的。

在 Bouncy Castle 中，DSTU 4145 公钥和私钥实现了 `DSTU4145PublicKey` 和 `DSTU4145PrivateKey` 接口。这些接口仅在 Bouncy Castle API 中定义。

### 签名生成

签名生成算法像 ECDSA 一样使用随机值，但该算法使用的是所用曲线的 EC 字段元素，并且在将消息哈希 `H(m)` 转换为整数也是小端序。函数 `FE()` 和 `INT()` 用于将整数转换为字段元素并反之。私有值仍由 `d` 表示，基点由 `G` 表示。

1. 计算 `h = FE(H(m))`。如果 `h == 0` 则 `h = 1`。
2. 生成一个随机的 `K`，使得 `0 < K < N`。
3. 计算 `(x, y) = KG`。如果 `x == 0` 不存在 [注：源文本存在重叠部分，已维护逻辑流]。
4. 计算 `R = hx`。
5. 计算 `S = (K + d) mod N`。

`R` 和 `S` 值被用于签名。以下代码提供了签名的生成示例：

```java
/**
 * 为传入的命名参数集生成一个 DSTU 4145-2002 密钥对。
 *
 * @param ecPrivate 用于生成的私钥。
 * @param input 待签名的输入。
 * @return 编码后的签名。
 */
public static byte[] generateDSTU4145Signature(
    PrivateKey ecPrivate, byte[] input)
   throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("DSTU4145", "BC");

    signature.initSign(ecPrivate);

    signature.update(input);

    return signature.sign();
}
```

与 ECDSA 不同，编码后的签名不是以 SEQUENCE 中的 ASN.1 对象形式返回。在这种情况下，仍然使用 ASN.1 编码，但签名被编码在 OCTET STRING 中，其中包含签名值，可能会添加前导零以便分割字符串，从而轻松提取 `R` 和 `S` 值。

### 签名验证

输入验证后，验证 DSTU 4145 签名需要一个三步过程。

1. 计算 `h = FE(H(m))`。如果 `h == 0` 则 `h = 1`。
2. 计算 `(x, y) = GS + QR`。如果 `(x, y)` 位于 `∞` 则返回无效。
3. `verified = INT(hx) == R`。

从 JCA 的高层来看，此实现最终看起来如下：

```java
/**
 * 如果传入的 DSTU 4145 签名通过传入的
 * EC 公钥和输入的验证，则返回 true。
 *
 * @param ecPublic 签名创建者的公钥。
 * @param input 应该签名的输入。
 * @param encSignature 编码后的签名。
 * @return 如果签名通过验证，否则返回 false。
 */
public static boolean verifyDSTU4145Signature(
    PublicKey ecPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("DSTU4145", "BC");

    signature.initVerify(ecPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

#### 将一切整合

下面的示例展示了我们为密钥对生成、签名生成和签名验证而定义的方法。

```java
/**
 * 使用 DSTU 4145-2002 对数据进行签名并
 * 验证生成的签名的示例。
 */
public class DSTU4145Example
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        KeyPair ecKp = generateDSTU4145KeyPair(0);
        byte[] dstuSig = generateDSTU4145Signature(
            ecKp.getPrivate(), Strings.toByteArray("hello, world!"));
        System.out.println("DSTU 4145-2002 verified: " +
                    verifyDSTU4145Signature(
                        ecKp.getPublic(), Strings.toByteArray("hello, world!"),
                          dstuSig));
    }
}
```

假设一切顺利，运行该示例你将看到以下输出：

```
DSTU 4145-2002 verified: true
```



### GOST

GOST 算法遵循了与 DSA 类似的演变过程，最初从大整数域开始，后来演变为椭圆曲线。初始标准 `GOST R 34.10-94` 和相关的消息摘要 `GOST R 34.11-94` 于 1994 年发布，并包含在 RFC 4491 [91] 中。2001 年，`GOST R 34.10-2001` 增加了一种 EC 算法，该算法也包含在 RFC 5832 [108] 中。2012 年，发布了签名算法和消息摘要的更新版本，即 `GOST R 34.10-2012`（也包含在 RFC 7091 [121] 中）和摘要 `GOST R 34.11-2012` “Streebog”（也包含在 RFC 6986 [119] 中）。除了 Bouncy Castle 的实现，WebCrypto GOST Library 网站上还发布了一个 JavaScript 实现 [43]。

不同 GOST 签名算法的基本细节见下表。

| 标准 | 算法名称 | 使用的摘要 | 签名算法名称 |
| --- | --- | --- | --- |
| GOST R 34.10-94 | “GOST3410” | GOST R 34.11-94 | “GOST3410” |
| GOST R 34.10-2001 | “ECGOST3410” | GOST R 34.11-94 | “ECGOST3410” |
| GOST R 34.10-2012 | “ECGOST3410-2012” | GOST R 34.11-2012 (256) | “ECGOST3410-2012-256” |
| GOST R 34.10-2012 | “ECGOST3410-2012” | GOST R 34.11-2012 (512) | “ECGOST3410-2012-512” |

正如你可能猜到的那样，除了增加更大的曲线参数外，`GOST 34.10-2012` 还设计用于支持 256 位和 512 位的消息摘要。

进一步说明：像 DSA/ECDSA 一样，所有的 GOST 签名算法都需要将签名消息的哈希转换为 `BigInteger`，但与 DSA/ECDSA 不同，这种转换是小端序（little-endian）的。如果你在调试一个运行得不正常的自定义 GOST 签名算法实现时，这是一个非常值得检查的点。记住这一点，我们现在将更详细地查看这些算法。

### 基本签名算法

现在我们查看不同 GOST 签名算法涉及的基本操作。

#### GOST R 34.10-94

原始的 GOST 签名算法使用域参数组成，由一个素数 $P$、值 $Q$（它是 $P-1$ 的一个 254-256 位素因子）以及另一个值 $A$（任何小于 $P-1$ 且满足 $A^Q \mod P = 1$ 的数字）组成。一旦确定了一组域参数，就会生成一个私值 $X$，然后计算公值 $Y = A^X \mod P$。

与 DSA 签名一样，由 `GOST R 34.10-94` 生成的签名由一个 $R$ 值和一个 $S$ 值组成。这些值通过以下步骤计算：

1. 生成一个随机的 $K$，使得 $0 < K < Q$。
2. 计算 $R = (A^{K} \mod P) \mod Q$。
3. 计算 $S = (XR + K * H(m)) \mod Q$。

其中 $H(m)$ 是我们要生成签名的消息 $m$ 的哈希。在 `GOST R 34.10-94` 的情况下，验证步骤与 DSA 不同，反映了对 $S$ 计算的差异：

1. 计算 $V = H(m) \mod Q$。
2. 计算 $Z_1 = (SV) \mod Q$。
3. 计算 $Z_2 = ((Q - R) * V) \mod Q$。
4. 计算 $U = ((A^{Z_1} * Y^{Z_2}) \mod Q$。
5. `verified = (U == R)`。

注意，与 DSA 不同，`GOST R 34.10-94` 输出包含两个 256 位数的编码（根据需要填充导零）。没有 ASN.1 编码，签名固定为 64 字节。在 Bouncy Castle 中，`GOST R 34.10-94` 的公私钥分别实现了 `GOST3410PublicKey` 和 `GOST3410PrivateKey` 接口。

#### GOST R 34.10-2001

`GOST R 34.10-2001` 是基于椭圆曲线的。类似于 ECDSA，算法使用了基点 $G$、阶 $N$、私值 $d$ 和公点 $Q$。与 ECDSA 相比，可以看到步骤 4 是不同的：

1. 生成一个随机的 $K$，使得 $0 < K < N$。
2. 计算 $(x, y) = KG$。
3. 计算 $R = x \mod N$。如果 $R == 0$，则返回步骤 1。
4. 计算 $S = (K * H(m) + d) \mod N$。如果 $S == 0$，则返回步骤 1。

与 `GOST R 34.10-94` 一样，`GOST R 34.10-2001` 输出包含两个 256 位数的编码（根据需要填充导零）。没有 ASN.1 编码，签名固定为 64 字节。输入验证后，签名验证包含以下步骤：

1. 计算 $V = H(m)^{-1} \mod N$。
2. 计算 $Z_1 = (SV) \mod N$。
3. 计算 $Z_2 = ((N - R) * V) \mod N$。
4. 计算 $(x, y) = G\{Z_1\} + Q\{Z_2\}$。如果 $(x, y)$ 为无穷点 $\infty$，则返回无效。
5. `verified = (x == R)`。

在 Bouncy Castle 中，`GOST R 34.10-2001` 的公私钥实现了 `ECPublicKey` 和 `ECPrivateKey` 接口。

#### GOST R 34.10-2012

`GOST R 34.10-2012` 用于签名和验证的算法与 `GOST R 34.10-2001` 相同。新标准的区别在于增加了新的曲线和新的消息摘要。这两个新的消息摘要基于 RFC 6986 中定义的“Streebog”哈希函数，它可以产生 256 位和 512 位的摘要。以类似的方式，一些新曲线也更大，使其与 512 位 GOST 版本提供的安全水平保持一致。

GOST R 34.10-2012 签名长度可以是 512 位或 1024 位。与早期的 GOST R 34.10 标准一样，签名由两个无符号值组成，分别代表 $R$ 值和 $S$ 值。

在 Bouncy Castle 中，GOST R 34.10-2012 公钥和私钥也带有 `ECPublicKey` 和 `ECPrivateKey` 接口的实现。

### 示例代码 - GOST R 34.10-2012

在本节中，我们选择只查看 GOST R 34.10-2012 是出于两个原因。第一个除了某些名称更改外，从 JCA（Java 加密体系）的角度来看，密钥的生成和算法的使用基本上都是相同的。第二个原因是 GOST R 34.10-94、GOST R 34.11-94 和 GOST R 34.10-2001 将于 2018 年正式淘汰，因此专注于 GOST R 34.10-2012 更好。

#### 密钥对生成

有 4 组可用于生成 GOST 密钥的主要参数集：
- `Tc26-Gost-3410-12-256-paramSetA`
- `Tc26-Gost-3410-12-512-paramSetA`
- `Tc26-Gost-3410-12-512-paramSetB`
- `Tc26-Gost-3410-12-512-paramSetC`

正如你所猜的的，256 和 512 指的是用于特定参数集的 GOST R 34.11-2012 版本。

在 JCA 中，我们利用 `ECGenParameterSpec` 类来传递参数集名称。以下示例代码将使用列出的参数名称之一生成一个 GOST R 34.11-2012 密钥对。

```java
 1   /**

 2    * 为传入的命名参数集生成一个 GOST 3410-2012 密钥对。

 3    *

 4    * @param paramSetName 用于生成密钥对基础的参数集名称。

 5    * @return 一个 EC KeyPair

 6    */

 7   public static KeyPair generateGOST3410_2012KeyPair(String paramSetName)

 8       throws GeneralSecurityException

 9   {

10       KeyPairGenerator keyPair = KeyPairGenerator.getInstance(

11                                   "ECGOST3410-2012", "BC");

12 

13       keyPair.initialize(new ECGenParameterSpec(paramSetName));

14 

15       return keyPair.generateKeyPair();

16   }
```

#### 签名生成

GOST R 34.11-2012 的签名生成同样围绕 256 位或 512 位的摘要展开。可用的两种签名算法为：
- `ECGOST3410-2012-256`
- `ECGOST3410-2012-512`

以下方法编写用于接受上述两个算法名称之一作为参数并生成签名。

```java
 1   /**

 2    * 使用传入的 GOST 3410-2012 私钥和输入数据生成

 3    * 编码的 GOST 3410-2012 签名。

 4    *

 5    * @param ecPrivate 用于生成签名的私钥。

 6    * @param input 待签名的输入数据。

 7    * @param sigName 要使用的签名算法名称。

 8    * @return 编码后的签名。

 9    */

10   public static byte[] generateGOST3410_2012Signature(

11       PrivateKey ecPrivate, byte[] input, String sigName)

12       throws GeneralSecurityException

13   {

 14       Signature signature = Signature.getInstance(sigName, "BC");

15 

16       signature.initSign(ecPrivate);

17 

18       signature.update(input);

19 

20       return signature.sign();

21   }
```

这两种签名类型产生不同大小的签名，并取决于是否使用了适当曲线。对于基于 256 位摘要的签名，产生 512 位的签名，由 $R$ 和 $S$ 值组成。对于基于 512 位摘要的签名，则产生 1024 位的签名。

#### 签名验证

我们的验证示例方法也编写为接受所使用的算法名称。代码如下所示。

```java
 1   /**

 2    * 如果传入的 GOST 3410-2012 签名相对于传入的

 3    * GOST 3410-2012 公钥通过，则返回 true。

 4    *

 5    * @param ecPublic 公钥。

 6    * @param input 被签名的输入数据。

 7    * @param sigName 签名算法名称。

 8    * @param encSignature 编码后的签名。

 9    * @return 如果签名通过，否则返回 false。

10   */

11   public static boolean verifyGOST3410_2012Signature(

12       PublicKey ecPublic, byte[] input,

13       String sigName, byte[] encSignature)

14       throws GeneralSecurityException

15   {

16       Signature signature = Signature.getInstance(sigName, "BC");

17 

18       signature.initVerify(ecPublic);

19 

20       signature.update(input);

21

22       return signature.verify(encSignature);

23   }
```

#### 整合使用

最后，值得将所有方法结合起来。以下示例代码使用其中一种 512 位参数集生成签名。

```java
 1  /**

 2   * 使用 GOST 3410-2012 生成并验证

 3   * 签名的示例。

 4   */

 5 class GostR3410_2012Example {

 6     public static void main(String[] args)

 7         throws GeneralSecurityException {

 8         KeyPair keyPair = generateGOST3410_2012KeyPair("Tc26-Gost-3410-12-512-paramSetA");

 9 

10        byte[] signature = generateGOST3410_2012Signature(keyPair.getPrivate(),

11                             "hello!".getBytes(),

12                             "ECGOST3410-2012-512");

13 

14        System.out.println("ECGOST3410-2012-512 verified: " +

15                             verifyGOST3410_2012Signature(keyPair.getPublic(),

16                             "hello!".getBytes(),

17                             "ECGOST3410-2012-512",

18                             signature));

19     }

20    }
```

如果一切正常，你将看到以下输出：

```
ECGOST3410-2012-512 verified: true
```

### RSA 算法

在许多方面，将 RSA 算法描述为过去 30 年公钥加密的主力工具会忽略重点。该算法最初是由 Clifford Cocks 在 1973 年在英国的 GCHQ 发现的，但直到 1997 年才解密。在此期间，算法在 1977 年被 Ronald Rivest、Adi Shamir 和 Leonard Adleman 独立发现，这就是 RSA 名称的由来。RSA 被广泛用于签名生成，也用于密钥传输——我们将稍后讨论。

这种选择之所以有效，与使用 RSA 时执行基础签名和验证操作的方式有关。与 DSA/ECDSA 一样，我们计算被签名消息的哈希值；在这种情况下，由于我们处理的是简单的大整数幂运算，因此引入了某种形式的填充，以确保签名得到适当的安全，使其成为一个接近 $N$（模数）的数字。我们将填充函数称为 $PAD()$，哈希函数称为 $H()$。在查看基于 RSA 的各种签名方法时，我们会发现改变的是填充函数；而创建签名的基础算术操作保持不变。

![RSA 签名生成与验证的示意图](img/chapter6----RegRSA.png)

RSA 的基本签名操作可以描述为 $S = PAD(H(M))^{D} \mod N$，验证操作描述为 $PAD(H(M)) == S^{E} \mod N$。当你读到第 7 章时可能会发现，这与 RSA 的加密操作是相反的。如果你试图理解收到的签名内容（可能是出于调试目的），这会很有用。使用公钥解密 RSA 签名将恢复出 $PAD(H(M))$，在签名莫名其妙失败的情况下，这可能有助于找到问题出在哪里。

#### 密钥对生成

在 JCA 中，可以通过仅指定模数的位长度来创建 RSA 密钥，也可以提供所需的位长度和一个要使用的公指数。在最后一种情况下，使用的算法参数规范是 `RSAKeyGenParameterSpec`。在下方的示例中，公指数已被设置为费马数 `F4`（十六进制值为 `0x10001`）。该十六进制值解释了为什么从二进制计算机的角度来看，这个数字是如此友好且高效的。

```java
 1   /**

 2    * 使用用户指定的参数生成 2048 位 RSA 密钥对。

 3    *

 4    * @return 返回一个 RSA KeyPair

 5    */

 6   public static KeyPair generateRSAKeyPair()

 7       throws GeneralSecurityException

 8   {
```



```java
KeyPairGenerator keyPair = KeyPairGenerator.getInstance("RSA", "BC");

keyPair.initialize(
    new RSAKeyGenParameterSpec(2048, RSAKeyGenParameterSpec.F4));

return keyPair.generateKeyPair();
}
```

带有 RSA 密钥的 `KeyPair` 将由来自 `java.security.interfaces` 包的 `RSAPublicKey` 和 `RSAPrivateKey` 的实现类组成。对于大多数提供者，你会发现私钥也实现了 `RSAPrivateCrtKey`，这意味着它具有必要的组件，使得可以使用中国剩余定理进行优化。

如果你检查运行此方法生成的私钥，你会发现为私指数 `D` 生成的数字比我们选择的公指数大得多，而且从大整数数学的角度来看，完全没有那么友好。

### PKCS #1 Version 1.5 签名

RSA 签名的原始填充机制在 PKCS #1 中描述，直到 PKCS #1 Version 1.5 之后，它仍然标准中描述的唯一方法。标准的最新版本可以在 RFC 8017 中找到 [128]。

### 签名生成

给定代表待签名消息 `M` 摘要的值 `h`。PKCS #1 Version 1.5 使用的填充函数定义为：

`PAD(h) = 0x00 || 0x01 || F || 0x00 || DigInfo(h)`

其中 `F` 是一个至少 8 字节长的字节字符串，且每个字节的值均为 0xFF。`F` 必须足够长，以确保 `PAD(h)` 生成的字符串长度与所用 RSA 密钥的模长度相同。`DigInfo()` 函数定义为通过 DER 编码以下 ASN.1 结构产生的字节字符串：

```
DigestInfo ::= SEQUENCE {
    digestAlgorithm DigestAlgorithm,
    digest OCTET STRING
}

DigestAlgorithm ::= AlgorithmIdentifier

AlgorithmIdentifier  ::=  SEQUENCE  {
    algorithm               OBJECT IDENTIFIER,
    parameters              ANY DEFINED BY algorithm OPTIONAL  }
```

由于相关的 ASN.1 标准早期版本中的类型错误，可选参数字段被定义为 ASN.1 NULL 值^(7)。

```
SEQUENCE
    algorithm               OBJECT IDENTIFIER,
    parameters              ANY DEFINED BY algorithm OPTIONAL  }
```

其中 `M` 代表 SHA-256。这种填充机制被称为类型 1 填充，其特性是产生常量字符串，这使得如果两个签名是用相同的密钥生成的，就可以看出它们与同一个文档相关，这与普通的 DSA/ECDSA 不同。从 JCA 的角度来看，算法的使用遵循了我们预期的模式：

```java
/**
 * 使用传入的私钥和
 * 输入数据生成 RSA 签名。
 *
 * @param rsaPrivate 用于生成签名的私钥。
 * @param input 要签名的输入数据。
 * @return 编码后的签名。
 */
public static byte[] generatePKCS15Signature(
    PrivateKey rsaPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withRSA", "BC");

    signature.initSign(rsaPrivate);

    signature.update(input);

    return signature.sign();
}
```

在这种情况下，返回 RSA 操作返回整数的字节编码，被视为无符号值并在必要时填充零以达到模的大小。

### 签名验证

假设匹配公钥和相同的输入，验证上一个示例中生成的签名的代码如下：

```java
/**
 * 如果传入的签名相对于传入的 RSA
 * 公钥和输入验证通过，则返回 true。
 *
 * @param rsaPublic 签名创建者的公钥。
 * @param input 应该被签名的输入。
 * @param encSignature 编码后的签名。
 * @return 如果签名有效则返回 true，否则返回 false。
 */
public static boolean verifyPKCS15Signature(
    PublicKey rsaPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withRSA", "BC");

    signature.initVerify(rsaPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

在底层，该过程将在对我们待验证签名的消息进行重构 `PAD(h)` 之后，应用 RSA 验证操作。

## PSS 签名

虽然目前似乎还没有任何针对格式正确且实现正确的 PKCS #1 Version 1.5 签名的成功攻击，但密码分析学的进展表明，在实现 RSA 所使用的 `PAD(h)` 函数时，在签名中包含一定程度的随机性更好。这就是概率签名方案（Probabilistic Signature Scheme，简称 PSS）。该方案最初由 Bellare 和 Rogaway 在“PSS: Provably Secure Encoding Method for Digital Signatures”中提出 [48]，该方案在理论上是可证明安全的，并已被适配到 PKCS #1 Version 2，在 RFC 8017 [128] 中以 RSA-PSS 的形式出现。

### 签名生成

与 PKCS #1 Version 1.5 使用的填充机制不同，RSA-PSS 方案还包括一个可选的 `salt`，长度为 `sLen`，以及一个掩码生成函数 `MGF()`。给定使用摘要函数 `Digest()` 生成的消息摘要值 `h`，其输出长度为 `hLen`，以及长度为 `modBits` 的 RSA 模数，我们可以描述新填充函数 `PAD()` 的步骤如下：

1. 设置 `maxLen = ceil((modBits - 1) / 8)`
2. 生成一个长度为 `sLen` 的随机字节字符串 `salt`；如果 `sLen == 0`，则 `salt` 为空字符串。
3. 设置 `M' = Z || h || salt`，其中 Z 为八零字节。
4. 设置 `H = Digest(M')`。
5. 设置 `DB = PS || 0x01 || salt`，其中 PS 是一个零字节字符串，使 DB 的长度达到 `maxLen - hLen - 1`。
6. 设置 `dbMask = MGF(H, maxLen - hLen - 1)`。
7. 设置 `maskedDB = DB XOR dbMask`。
8. 设置 `EM = maskedDB || H || 0xBC`。
9. 将 EM 中最左侧字节的最左 `8 * maxLen - (modBits - 1)` 位置零。
10. 返回 `EM`。

你可以在 RFC 8017 的 B.2.1 节找到标准掩码生成函数（MGF1）的定义。MGF1 的实现源码在 Bouncy Castle 中可用。

正如你可能猜到的那样，如果盐长度为零，那么生成的签名将是确定性的。否则，即使密钥和输入数据相同，签名也会改变。正如 Coron 在 [49] 中讨论的那样，减小盐长度会降低算法的安全性，虽然目前认为这样做不会产生太大风险。RFC 8017 提供了一个粗略的法则：如果盐的位长度与哈希函数输出的位长度相同，则盐长度对于给定的哈希算法是最优的。以下示例展示了 JCA 中 RSA-PSS 的基本用法：

```java
/**
 * 使用传入的私钥和输入数据生成编码的 RSA 签名。
 * 
 * 
 * @param rsaPrivate 用于生成签名的私钥。
 * @param input 待签名的输入。
 * @return 编码的签名。
 */
public static byte[] generateRSAPSSSignature(
    PrivateKey rsaPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withRSAandMGF1", "BC");

    signature.initSign(rsaPrivate);

    signature.update(input);

    return signature.sign();
}
```

在上面的示例中，将使用内部默认值来选择种子大小。稍后我们将看到，有一种方法使用 `SignatureSpec` 来配置 `Signature` 类。

### 签名验证

签名验证涉及恢复填充字符串，然后通过检查长度、确认字符串开头的零位以及末尾 0xBC 字节来反转填充步骤。在 JCA 中，验证步骤如下：

```java
/**
 * 如果传入的签名通过公钥和输入验证，则返回 true。
 * 
 * 
 * @param rsaPublic 公钥。
 * @param input 应该被签名的输入。
 * @param encSignature 编码的签名。
 * @return 如果签名有效返回 true，否则返回 false。
 */
public static boolean verifyRSAPSSSignature(
    PublicKey rsaPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SHA256withRSAandMGF1", "BC");

    signature.initVerify(rsaPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

在底层，情况更为复杂。取恢复的字节字符串 `EM`，算法处理如下：

1. 设置 `maskedDB` 为 `EM` 最左侧的 `maxLen - hLen - 1` 字节，令 `H` 为下一个字节。
2. 设置 `dbMask = MGF(H, maxLen - hLen - 1)`。
3. 设置 `DB = DB XOR dbMask`。
4. 将 DB 中最左侧字节的最左 `8 * maxLen - (modBits - 1)` 位置零。
5. 如果 DB 的前 `maxLen - hLen - sLen - 2` 字节不是零，或者位置在 `maxLen - hLen - sLen - 1` 的字节不是 0x01，则返回无效。
6. 令 `salt` 为 DB 的最后 `sLen` 字节。
7. 设置 `M' = Z || h || salt`，其中 Z 为八零字节。
8. 设置 `H = Digest(M')`。
9. `verified = (H == H')`。

### 使用 PSSParameterSpec

JCA 提供了 `java.security.spec.PSSParameterSpec` 类作为配置 `Signature` 对象的机制，用于设置消息摘要、盐、掩码生成函数和轨迹的细节。

使用 `PSSParameterSpec` 生成签名只需调用 `Signature.setParameter()` 并传入一个 `PSSParameterSpec` 对象即可。

```java
/**
 * 使用传入的私钥和输入数据生成编码的 RSA 签名。
 * 
 * @param rsaPrivate 用于生成签名的私钥。
 * @param input 要签名的输入数据。
 * @return 编码后的签名。
 */
public static byte[] generateRSAPSSSignature(
    PrivateKey rsaPrivate, PSSParameterSpec pssSpec, byte[] input)
    throws GeneralSecurityException
{
```



## RSA PSS 签名

```java
Signature signature = Signature.getInstance("RSAPSS", "BC");

signature.setParameter(pssSpec);

signature.initSign(rsaPrivate);

signature.update(input);

return signature.sign();
```

如下所示，验证过程也是类似的。

```java
/**
 * 如果传入的签名通过传入的 RSA 公钥和输入的验证，则返回 true。
 *
 * @param rsaPublic 签名创建者的公钥。
 * @param input 原本被签名的输入数据。
 * @param encSignature 编码后的签名。
 * @return 如果签名验证通过则返回 true，否则返回 false。
 */
public static boolean verifyRSAPSSSignature(
    PublicKey rsaPublic, PSSParameterSpec pssSpec,
    byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("RSAPSS", "BC");

    signature.setParameter(pssSpec);

    signature.initVerify(rsaPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

注意，在两种情况下，`setParameter()` 方法都在 `init()` 方法之前调用的。

以下示例使用了我们的两个示例方法来创建和验证签名，该签名在其他情况下会被指定为“SHA256withRSAandMGF1”。`PSSParameterSpec` 构造函数的第一个参数提供签名消息摘要，下一个参数提供掩码生成函数的名称，而紧随其后的参数提供用于该函数的消息摘要。最后是一个用于指定尾部（trailer）的参数——在此情况下，1 表示应该使用尾部值 `0xBC`。

```java
/**
 * 一个使用基于 SHA-256 的 PSSParameterSpec 的 RSA PSS 示例。
 */
public class RSAPSSParamsExample
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        KeyPair rsaKp = generateRSAKeyPair();

        PSSParameterSpec pssSpec = new PSSParameterSpec(
            "SHA-256",
            "MGF1", new MGF1ParameterSpec("SHA-256"), 32,
            1);

        byte[] pssSignature = generateRSAPSSSignature(
            rsaKp.getPrivate(), pssSpec, Strings.toByteArray("hello, world!"));

        System.out.println("RSA PSS verified: "
                                 + verifyRSAPSSSignature(
                                             rsaKp.getPublic(), pssSpec,
                                             Strings.toByteArray("hello, world!"),
                                             pssSignature));
    }
}
```

你可以看到，参数规范提供了所需的一切，因为 `verify` 和 `generate` 方法中的签名算法仅简单称为 `RSAPSS`。

假设一切进展正常，如果你运行该示例，你应该看到以下输出：

```
RSA PSS verified: true
```

## 其他 RSA 签名算法

Bouncy Castle 还支持另外三种 RSA 签名类型：两种基于 ISO9796-2，一个来自 X9.31——它也列在 FIPS PUB 186-4 中并最初定义在 X9.31 中。

| 标准 | 算法名称模板 |
| --- | --- |
| ISO9796-2 | `<digest>withRSA/ISO9796-2` |
| ISO9796-2 | `<digest>withRSAandMGF1/ISO9796-2` |
| X9.31 | `<digest>withRSA/X9.31` |

如你所示，除了引号之后的类型名称外，名称模板遵循通常的 Java 约定。例如，使用 ISO9796-2 PSS 变体的 SHA-256 签名是“SHA256withRSAandMGF1/ISO9796-2”。同样，使用 SHA-256 和 X9.31 创建 `Signature` 类的实例使用的是名称“SHA256withRSA/X9.31”。

同时请注意，目前尚不支持在 ISO9796-2 PSS 变体中使用 `PSSParameterSpec`。

## SM2

SM2 是一种基于椭圆曲线密码学的签名算法，由中国密码管理局发布。目前仅有关于 SM2 及其使用的消息摘要 SM3 的草案 RFC 可用。关于 SM2 和 SM3 的另一个信息来源是托管在 `http://gmssl.org` 的北京大学项目。草案 RFC 和北京大学网站都包含了对原始中国标准的引用。

SM2 签名算法指定使用 SM3 消息摘要。SM2 在许多方面与其它基于椭圆曲线（EC）的签名算法不同。最根本的区别在于该算法通过根据签名者的身份和签名者的公钥附加常量字符串对消息进行预处理。我们先来看预处理步骤。

### 消息预处理步骤

签名或验证消息的第一步是计算消息前缀。消息前缀基于用户的身份字符串、所用曲线 EC 参数的域元素 `A` 和 `B` 的编码，以及构成签名者公钥 `Q` 的元素编码。

1. 计算 `ZA = H(bitLength(ID) || ID || A || B || xG || yG || xQ || yQ)`
2. 计算 `m' = ZA || m`，其中 `bitLength(ID)` 是表示 ID 位长度的双字节整数，`H()` 代表 SM3 摘要。

在未指定 ID 的情况下，SM2 使用默认 ID 字符串，由十六进制字符串“31323334353637383132333435363738”中的字节值表示。

### 签名生成

一旦消息 `m` 被预处理为 `m'`，我们就可以使用以下四个步骤计算签名。

1. 生成一个随机 `K`，使得 `0 < K < N`。
2. 计算 `(x, y) = KG`。
3. 计算 `R = (H(m') + x) mod N`，如果 `R == 0` 或 `R + K == N` 则返回第一步。
4. 计算 `S = ((1 + d)^-1 * (K - dR)) mod N`，如果 `S == 0` 则返回第一步。

通常，尽管算法不同，但在使用 JCA 执行时，SM2 签名算法看起来非常熟悉。

```java
/**
 * 根据传入的 EC 私钥和输入数据，基于 SM3 摘要生成
 * 编码的 SM2 签名。
 *
 * @param ecPrivate 用于生成签名的私钥。
 * @param input 待签名的输入数据。
 * @return 编码的签名。
 */
public static byte[] generateSM2Signature(
    PrivateKey ecPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SM3withSM2", "BC");

    signature.initSign(ecPrivate);

    signature.update(input);

    return signature.sign();
}
```

与 `ECDSA` 一样，`SM2` 通过将 `R` 和 `S` 编码为 `ASN.1 SEQUENCE` 中的两个 `ASN.1 INTEGER` 类型，生成一个代表签名的字节数组。尽管我们尚未遇到过该算法的签名签名，但关于 `INTEGER` 是有符号类型这一常规警告仍然适用。

### 签名验证

在对 `R` 和 `S` 进行边界检查以及对消息 `m` 进行预处理以产生 `m'` 后，我们有 3 个步骤来确定签名是否与提供的消息和公钥匹配。

1. 计算 `T = (R + S) mod N`。如果 `T == 0` 则返回无效。
2. 计算 `(x, y) = SG + TQ`。
3. `verified = (R == ((H(m') + x) mod N))`

```java
/**
 * 如果传入的 SM3withSM2 签名相对于传入的
 * EC 公钥和输入验证通过，则返回 true。
 *
 * @param ecPublic 签名创建者的公钥。
 * @param input 原本应被签名的输入数据。
 * @param encSignature 编码的签名。
 * @return 如果签名验证通过，则返回 true，否则返回 false。
 */
public static boolean verifySM2Signature(
    PublicKey ecPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SM3withSM2", "BC");

    signature.initVerify(ecPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

### 使用 SM2ParameterSpec

在我们之前看过的示例中，`Signature` 对象内部使用了默认的 SM2 `ID` 值。Bouncy Castle 同时也支持参数规范——`SM2ParameterSpec`，允许显式设置用于签名计算的 ID 字符串。

下面的方法展示了如何在第 18 行设置签名生成所需的 ID。

```java
/**
 * 根据传入的 EC 私钥和输入数据，基于 SM3 摘要生成
 * 编码的 SM2 签名。
 *
 * @param ecPrivate 用于生成签名的私钥。
 * @param sm2Spec 携带有签名签署者 ID 的 SM2 规范。
 * @param input 待签名的输入数据。
 * @return 编码的签名。
 */
public static byte[] generateSM2Signature(
    PrivateKey ecPrivate, SM2ParameterSpec sm2Spec, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SM3withSM2", "BC");

    signature.setParameter(sm2Spec);

    signature.initSign(ecPrivate);

    signature.update(input);

    return signature.sign();
}
```

下一个方法展示了为签名验证设置 ID 的过程。

```java
/**
 * 如果传入的 SM3withSM2 签名相对于传入的
 * EC 公钥和输入验证通过，则返回 true。
 *
 * @param ecPublic 签名创建者的公钥。
 * @param sm2Spec 携带有预期签署者预期 ID 的 SM2 规范。
 * @param input 原本应被签名的输入数据。
 * @param encSignature 编码的签名。
 * @return 如果签名验证通过，则返回 true，否则返回 false。
 */
public static boolean verifySM2Signature(
    PublicKey ecPublic, SM2ParameterSpec sm2Spec,
    byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SM3withSM2", "BC");

    signature.setParameter(sm2Spec);

    signature.initVerify(ecPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

最后这是一个将两个方法结合并设置 ID 的示例。

```java
/**
 * 使用 SM2ParameterSpec 设置 ID 的示例。
 */
public class SM2Example
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        KeyPair ecKp = generateKeyPair("sm2v1");

        SM2ParameterSpec sm2Spec = new SM2ParameterSpec("Signer");

        byte[] sm2Signature = generateSM2Signature(
            ecKp.getPrivate(),
            sm2Spec,
            "hello, world!");

        System.out.println("SM2 verified: " +
            verifySM2Signature(ecKp.getPublic(),
                sm2Spec,
                "hello, world!"));
    }
}
```

如果你运行此示例且一切顺利，将看到输出：

```
SM2 verified: true
```

正如你预期的，如果你尝试更改一侧的 ID 而不更改另一侧，签名验证步骤将失败。

## Bouncy Castle 签名接口



# Bouncy Castle 的 PKIX 包为签名的生成和验证提供了通用接口

这些接口都是基于流的，并提供了获取算法相关的 ASN.1 `AlgorithmParameters`、写入数据的输出流，以及在流关闭时检索签名的方法。

这些接口贯穿 PKIX API 用于引入签名和验证操作，并且针对 JCA 和 BC 底层 API 都提供了实现。如果你需要，你也可以编写自己的实现。

## ContentSigner 和 ContentVerifier 接口

`ContentSigner` 接口所示：

```java
 1 /**
 2  * 一个能够从输出流创建签名的操作者的通用
 3  * 接口。
 4  */
 5 public interface ContentSigner
 6 {
 7     /**
 8      * 返回描述该签署器生成的签名算法
 9      * 参数的标识符。
10      *
11      * @return 算法 OID 和参数。
12      */
13     AlgorithmIdentifier getAlgorithmIdentifier();
14 
15     /**
16      * 返回一个接收数据以用于计算签名的
17      * 流。如果你也想在过程中累积数据，
18      * 请使用 TeeOutputStream。
19      *
20      * @return 一个 OutputStream
21      */
22     OutputStream getOutputStream();
23 
24     /**
25      * 根据写入流的当前数据返回一个签名，
26      * 自从开始或上一次调用 getSignature() 以来写入的数据。
27      *
28      * @return 代表签名的字节数组。
29      */
30     byte[] getSignature();
31 }
```

`ContentVerifier` 遵循类似的模式。

```java
 /**
 * 操作符的通用接口，能够根据输出流中的数据
 * 验证签名。
 */
public interface ContentVerifier
{
    /**
     * 返回描述此验证器支持的签名算法
     * 和参数的算法标识符。
     *
     * @return 算法 oid 和参数。
     */
     AlgorithmIdentifier getAlgorithmIdentifier();

    /**
     * 返回一个流，用于接收数据以便供后续验证
     * 计算签名。如果你想在生成的同时累积数据，
     * 请使用 TeeOutputStream。
     *
     * @return 一个 OutputStream
     */
     OutputStream getOutputStream();

    /**
     * 如果签名的预期值与传入流的数据相
     * 匹配，则返回 true。
     *
     * @param expected 数据上签名的预期值。
     * @return 如果签名通过验证则返回 true，否则返回 false
     */
    boolean verify(byte[] expected);
}
```

由于正在处理的签名类型在分析其签名的 `AlgorithmIdentifier` 之前是未知的，因此通常会通过 `ContentVerifierProvider` 创建此类验证器。在高级层 PKIX 类需要创建 `ContentVerifierProvider` 的情况下，通常会发现一个接受 `ContentVerifierProvider` 作为参数的方法。因此，如果你由于需要与其他软件或硬件接口以执行实际的签名验证工作，而需要提供这些接口之一的自定义实现，你通常也会实现 `ContentVerifierProvider`。

`ContentVerifierProvider` 接口也基于 `AlgorithmIdentifier` 类，并有三个方法。

```java
 /**
 * ContentVerifier 对象提供者的通用接口。
 */
public interface ContentVerifierProvider
{
    /**
     * 返回此验证器是否关联了一个证书。
     *
     * @return 如果存在关联的证书则返回 true，否则返回 false。
     */
    boolean hasAssociatedCertificate();

    /**
     * 如果存在关联证书，则返回该证书。
     *
     * @return 包含关联证书的持有者（如果存在），
     * 如果不存在则返回 null。
     */
    X509CertificateHolder getAssociatedCertificate();

    /**
     * 返回一个与传入的算法标识符匹配的 ContentVerifier，
     *
     * @param verifierAlgorithmIdentifier 所需的算法和参数。
     * @return 匹配的 ContentVerifier
     * @throws OperatorCreationException 如果无法创建所需的 ContentVerifier
     */
    ContentVerifier get(AlgorithmIdentifier verifierAlgorithmIdentifier)
        throws OperatorCreationException;
}
```

## 总结

在本章中，我们查看了与公钥签名相关的安全级别和基础知识。这涵盖了使用各种方案（如 DSA、DSTU 4145、GOST 以及最著名的 RSA）对数字签名进行创建和验证。

最后，我们查看了用于 Bouncy Castle PKIX 包的操作符接口。这些接口包含了 `ContentSigner` 和 `ContentVerifier`，允许进行与提供者无关签名操作。

# 第 7 章：密钥传输、密钥协商和密钥交换

本章展示了如何将公钥加密应用于密钥传输、密钥协商和密钥交换。我们将使用在第 2 章中看到的用于对称加密的相同 API 来查看密钥传输。之后，我们将查看密钥协商和密钥交换。

## 算法安全强度

支持密钥传输、密钥协商和密钥交换算法的通用安全强度遵循与第 6 章中签名算法相同的指南。对于 RSA 和椭圆曲线，你可以遵循第 6 章中为 RSA 签名和 ECDSA 给出的相同值。

这里有一个我们在签名章节中未涵盖过的新算法：基于素数的 Diffie-Hellman，它主要使用与 DSA 相同类型的参数。适用于 NIST 标准的 Diffie-Hellman 密钥协商的安全强度描述在 NIST SP 800-57 的表 2 中。对于我们感兴趣的安全强度范围，密钥大小表所示：

### 密钥协商安全强度

| 公钥算法 | 密钥大小 | 安全强度（位） |
| --- | --- | --- |
| DH | 1024 | <= 80 |
| DH | 2048 | 112 |
| DH | 3072 | 128 |
| DH | 7680⁹ | 192 |
| DH | 15360⁹ | 256 |

我们还将看到在本章描述的许多技术中使用了摘要函数。第 6 章中关于摘要相对于公钥算法的相对安全强度的规则也适用于此处。

## 密钥传输

在本文中，密钥传输是一个术语，用于描述在本地生成对称密钥后将其安全地发送给另一方的过程。在不考虑后量子算法的情况下，RSA 和 ElGamal 是仅直接提供这种能力的算法，因为它们的结构允许在末端加密单个文本块，并在另一端恢复原始文本。

### RSA-OAEP

RSA 加密/解密步骤执行的是与 RSA 签名/验证相反的操作。给定一个明文消息 `M`，RSA 的加密操作可以描述为 `Enc = PAD(M)^E mod N`，解密操作为 `PAD(M)^D mod N`，其中 `N` 是 RSA 模数，`E` 是公指数，`D` 是私指数。

![RSA-OAEP 加密和解密的原理图](img/chapter7----OAEP.png)

RSA-OAEP 加密和解密的图

OAEP 填充函数由 Bellare 和 Rogaway 在《Optimal Asymmetric Encryption - How to Encrypt with RSA》中引入，随后从 PKCS #1 2.0 开始采用。理想情况下，对于像 RSA 这样的算法，加密值应该是一个小于模数的随机数——此时任何基于已知密文的攻击（通过已知填充前的消息，或对填充本身的某些了解）都会失效。OAEP 并没有完全做到这一点，但它非常接近，并且为加密消息提供了一种不可变的方法，并允许根据需要对加密进行标记。

#### OAEP 密钥封装

使用 OAEP 对对称密钥进行封装是将对称密钥字节作为 `M`，使用 OAEP 编码构造填充块，然后应用 RSA 加密操作生成密文。该编码的构造与我们之前查看的 PSS 机制相似。除了消息 `M` 之外，OAEP 填充还接受一个标签 `L`，用于标记加密，或者在未使用时为零长度。给定这两个输入以及输出长度为 `hLen` 的摘要函数 `Digest()` 和长度为 `modBits` 的 RSA 模数，OAEP 填充的编码算法描述如下：

1. 设置 `maxLen = \lceil(modBits - 1) / 8\rceil`
2. 设置 `lHash = Digest(L)`
3. 设置 `DB = lHash \parallel PS \parallel 0x01 \parallel M`，其中 `PS` 是一个长度足够的零字符串，可能为空，以使 `DB` 的长度达到 `maxLen - hLen`。
4. 生成一个长度为 `hLen` 的随机字节字符串 `seed`。
5. 设置 `dbMask = MGF(seed, maxLen - hLen)`。
6. 设置 `maskedDB = DB \oplus dbMask`。
7. 设置 `seedMask = MGF(maskedDB, hLen)`。
8. 设置 `maskedSeed = seed \oplus seedMask`。
9. 设置 `EM = 0x00 \parallel maskSeed \parallel maskedDB`。
10. 返回 `EM`。

从 JCE 的角度来看，使用的数字摘要函数名称和 MGF 函数名称被包含在加密算法名称的填充字段中。由于我们处理的是 RSA，模式被指定为 `NONE`。在接下来的示例中，我们的数字摘要函数是 `SHA-256`，使用 `MGF1` 掩码生成函数。掩码生成函数将使用相同的摘要算法。

```java
 1   /**
 2    * 使用 RSA OAEP 算法生成封装的密钥，
 3    * 返回生成的加密结果。
 4    *
 5    * @param rsaPublic 用于封装的公钥。
 6    * @param secretKey 要加密/封装的密钥密钥。
 7    * @return 如果签名验证通过则返回 true，否则返回 false。
 8    */
 9   public static byte[] keyWrapOAEP(
10       PublicKey rsaPublic, SecretKey secretKey)
11       throws GeneralSecurityException
12   {
13       Cipher cipher = Cipher.getInstance(
14           "RSA/NONE/OAEPwithSHA256andMGF1Padding", "BC");
15 
16       cipher.init(Cipher.WRAP_MODE, rsaPublic);
17 
18       return cipher.wrap(secretKey);
19   }
```

由于示例中的 `Cipher` 对象已经在封装模式下初始化，因此仅用了 `Cipher.wrap()` 方法。使用 `Cipher.update()` 或 `Cipher.doFinal()` 将导致异常。

### OAEP 密钥解封装

封装过程涉及对密文应用 RSA 解密操作，然后反转 OAEP 填充函数以产生原始消息 `M`，该消息提供了构成对称密钥的字节。

1. 设置 `maxLen = \left\lceil(modBits - 1) / 8\right\rceil`
2. 设置 `lHash = Digest(L)`
3. 将 EM 分为 `Y \parallel maskSeed \parallel maskedDB`，其中 `Y` 是单个字节，`maskSeed` 长度为 `hLen` 字节，`maskedDB` 是剩余的字节。
4. 设置 `seedMask = MGF(maskedDB, hLen)`。
5. 设置 `seed = maskedSeed \oplus seedMask`。
6. 设置 `dbMask = MGF(seed, maxLen - hLen)`。
7. 设置 `DB = maskedDB \oplus dbMask`。
8. 将 DB 分为 `lHash^{\prime} \parallel PS \parallel Z \parallel M`，其中 `lHash^{\prime}` 长度为 `hLen` 字节，`PS` 是一个值为 0x00 的零或多个字节字符串，`Z` 是单个字节，`M` 是剩余的字节。
9. 如果 `lHash \neq lHash^{\prime}` 或 `Y \neq 0x00`
10. 返回 `M`。

从 JCE 的角度来看，使用的数字摘要函数名称和 MGF 函数名称被包含在加密算法名称的填充字段中。由于我们处理的是 RSA，模式被指定为 `NONE`。在接下来的示例中，我们的数字摘要函数是 `SHA-256`，使用 `MGF1` 掩码生成函数。掩码生成函数将使用相同的摘要算法。

```java
 1   /**
 2    * 使用 RSA OAEP 算法生成封装的密钥，
 3    * 返回生成的加密结果。
 4    *
 5    * @param rsaPublic 用于封装的公钥。
 6    * @param secretKey 要加密/封装的密钥密钥。
 7    * @return 如果签名验证通过则返回 true，否则返回 false。
 8    */
 9   public static byte[] keyWrapOAEP(
10       PublicKey rsaPublic, SecretKey secretKey)
11       throws GeneralSecurityException
12   {
13       Cipher cipher = Cipher.getInstance(
14           "RSA/NONE/OAEPwithSHA256andMGF1Padding", "BC");
15 
16       cipher.init(Cipher.WRAP_MODE, rsaPublic);
17 
18       return cipher.wrap(secretKey);
19   }
```



由于示例中的 `Cipher` 对象已经在封装模式下初始化，因此仅用了 `Cipher.wrap()` 方法。使用 `Cipher.update()` 或 `Cipher.doFinal()` 将导致异常。

### OAEP 密钥解封装

解封装过程涉及对密文应用 RSA 解密操作，然后反转 OAEP 填充函数产生原始消息 `M`（images/leanpub_equation_410.png），它提供了构成对称密钥的字节。

1. 设置 `maxLen = \left\lceil(modBits - 1) / 8\right\rceil`（images/leanpub_equation_411.png）
2. 设置 `lHash = Digest(L)`（images/leanpub_equation_412.png）
3. 将 EM 分为 `Y \parallel maskSeed \parallel maskedDB`（images/leanpub_equation_413.png），其中 `Y`（images/leanpub_equation_414.png）是单个字节，`maskSeed`（images/leanpub_equation_415.png）长度为 `hLen`（images/leanpub_equation_416.png）字节，`maskedDB`（images/leanpub_equation_417.png）是剩余的字节。
4. 设置 `seedMask = MGF(maskedDB, hLen)`（images/leanpub_equation_418.png）
5. 设置 `seed = maskedSeed \oplus seedMask`（images/leanpub_equation_419.png）
6. 设置 `dbMask = MGF(seed, maxLen - hLen)`（images/leanpub_equation_420.png）
7. 设置 `DB = maskedDB \oplus dbMask`（images/leanpub_equation_421.png）
8. 将 DB 分为 `lHash^{\prime} \parallel PS \parallel Z \parallel M`（images/leanpub_equation_422.png），其中 `lHash^{\prime}`（images/leanpub_equation_423.png）长度为 `hLen`（images/leanpub_equation_424.png）字节，`PS`（images/leanpub_equation_425.png）是一个值为 0x00 的零或多个字节字符串，`Z`（images/leanpub_equation_426.png）是单个字节，`M`（images/leanpub_equation_427.png）是剩余的字节。
9. 如果 `lHash \neq lHash^{\prime}`（images/leanpub_equation_428.png）或 `Y \neq 0x00`（images/leanpub_equation_429.png）
10. 返回 `M`（images/leanpub_equation_430.png）

对于 JCE 而言，数字摘要函数名称和使用的 MGF 函数名称被包含在加密算法名称的填充字段中。由于我们处理的是 RSA，模式被指定为 `NONE^(10)`。在接下来的示例中，我们的数字摘要函数是 `SHA-256`，使用 `MGF1` 掩码生成函数。掩码生成函数将使用相同的摘要算法。

```java
/**
 * 使用 RSA OAEP 算法生成封装的密钥，
 * 返回生成的加密结果。
 *
 * @param rsaPublic 用于封装的公钥。
 * @param secretKey 要加密/封装的密钥密钥。
 * @return 如果签名验证通过则返回 true，否则返回 false。
 */
public static byte[] keyWrapOAEP(
    PublicKey rsaPublic, SecretKey secretKey)
    throws GeneralSecurityException
{
    Cipher cipher = Cipher.getInstance(
        "RSA/NONE/OAEPwithSHA256andMGF1Padding", "BC");

    cipher.init(Cipher.WRAP_MODE, rsaPublic);

    return cipher.wrap(secretKey);
}
```

由于示例中的 `Cipher` 对象已经在封装模式下初始化，因此仅用了 `Cipher.wrap()` 方法。使用 `Cipher.update()` 或 `Cipher.doFinal()` 将导致异常。

### 整合整体

以下示例展示了如何使用我们定义的方法来封装和解封装 AES 密钥。

```java
/**
 * 基于 OAEP 的简单密钥封装和解封装示例。
 */
public class OAEPExample
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        SecretKey aesKey = createAESKey();

        KeyPair kp = generateRSAKeyPair();

        byte[] wrappedKey = keyWrapOAEP(kp.getPublic(), aesKey);

        SecretKey recoveredKey = keywrapOAEP(kp.getPrivate(),
                                    wrappedKey, aesKey.getAlgorithm());

        System.out.println(Arrays.areEqual(aesKey.getEncoded(), recoveredKey.getEncoded()));
    }
}
```

### 使用 OAEPParameterSpec

正如你在 OAEP 编码算法中所看到的，标签 `L`（images/leanpub_equation_432.png）可以包含在加密中。JCE 允许你设置此值，还可以通过 `javax.crypto.spec.OAEPParameterSpec` 和 `javax.crypto.spec.PSource.PSpecified` 类通用的配置 OAEP 填充。

允许使用 `OAEPParameterSpec` 需要我们将算法参数规范传递给 `Cipher.init()` 方法。我们可以通过如下调整封装方法来实现：

```java
/**
 * 根据传入的 OAEPParameterSpec，使用 RSA OAEP 算法生成封装的密钥，
 * 并返回生成的加密结果。
 *
 * @param rsaPublic 用于封装的公钥。
 * @param oaepSpec OAEP 操作的参数规范。
 * @param secretKey 要加密/封装的密钥密钥。
 * @return 如果签名验证通过则返回 true，否则返回 false。
 */
public static byte[] keyWrapOAEP(
    PublicKey rsaPublic, OAEPParameterSpec oaepSpec, SecretKey secretKey)
    throws GeneralSecurityException
{
    Cipher cipher = Cipher.getInstance("RSA", "BC");

    cipher.init(Cipher.WRAP_MODE, rsaPublic, oaepSpec);

    return cipher.wrap(secretKey);
}
```

并对解封装方法进行相应的更改，如下：

```java
/**
 * 返回在 wrappedKey 中被加密的密钥。
 *
 * @param rsaPrivate 用于解封（un own）的私钥。
 * @param oaepSpec OAEP 操作的参数规范。
 * @param wrappedKey 被加密的密钥。
 * @param keyAlgorithm 加密密钥所属的算法。
 * @return 解封后的 SecretKey。
 */
public static SecretKey keyUnwrapOAEP(
    PrivateKey rsaPrivate, OAEPParameterSpec oaepSpec,
    byte[] wrappedKey, String keyAlgorithm)
    throws GeneralSecurityException
{
    Cipher cipher = Cipher.getInstance("RSA", "BC");

    cipher.init(Cipher.UNWRAP_MODE, rsaPrivate, oaepSpec);

    return (SecretKey)cipher.unwrap(
                        wrappedKey, keyAlgorithm, Cipher.SECRET_KEY);
}
```

请注意，在上述两种情况下，由于 `OAEPParameterSpec` 提供了使用 RSA-OAEP 所需的所有配置，我们只需要向 `Cipher.getInstance()` 方法指定基础算法名称“RSA”。将 `oaepSpec` 传递给 `Cipher.init()` 方法即可完成其余。

下面的示例代码展示了如何使用 `OAEPParameterSpec` 配置 RSA 解密器使用基于 SHA-256 的 RSA-OAEP，并使用基于 SHA-256 的 MGF1 作为掩码生成函数。这个 RSA-OAEP 示例与之前未使用 `OAEPParameterSpec` 的示例之间的唯一区别在于，包含了由字符串“My Label”的字节定义的标签（label）。

```java
/**
 * 展示了基于 OAEP 的密钥封装和解封的简单示例
 * 并使用 OAEPParameterSpec 类配置加密。
 */
public class OAEPParamsExample
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        SecretKey aesKey = createTestAESKey();

        KeyPair kp = generateRSAKeyPair();
        OAEPParameterSpec oaepSpec = new OAEPParameterSpec(
                                        "SHA-256",
                                        "MGF1", MGF1ParameterSpec.SHA256,
                                            new PSource.PSpecified(
                                              Strings.toByteArray("My Label")));

        byte[] wrappedKey = keyWrapOAEP(kp.getPublic(), aesKey);

        SecretKey recoveredKey = keyUnwrapOAEP(
                                    kp.getPrivate(), oaepSpec,
                                    wrappedKey, aesKey.getAlgorithm());

        System.out.println(
            Arrays.areEqual(aesKey.getEncoded(), recoveredKey.getEncoded()));
    }
}
```

与之前的 RSA-OAEP 示例一样，运行该示例应该产生以下输出：

```
true
```

这表明原始密钥字节已正确恢复。

如果你感兴趣，可以在封装和解封之间更改 `oaepSpec` 的值，你会发现解封将抛出异常并失败。最后，如果你想在不使用 `OAEPParameterSpec` 的情况下，将 `oeapSpec` 值恢复到产生加密时所需的精确值，可以使用 `PSource.PSpecified.DEFAULT` 作为标签——该常量提供了一个等同于空字符串的标签源。

### ElGamal-OAEP

与 RSA 一样，ElGamal 算法也提供了处理单块数据的能力。基于 Diffie-Hellman 算法，它产生一个大小是密钥两倍的区块，包含加密数据。

ElGamal 使用常规 Diffie-Hellman 密钥。Diffie-Hellman 域参数与我们在第 6 章中为 DSA 的参数相同——在这种情况下，`P`（img/leanpub_equation_433.png）和 `G`（img/leanpub_equation_434.png）参数是最感兴趣的。一旦选定一组域参数，就会生成一个私值 `X`（img/leanpub_equation_435.png），其中 `0 < X < P`（img/leanpub_equation_436.png），以及公值 `Y`（img/leanpub_equation_437.png），后者通过计算 `G^{X}`（img/leanpub_equation_438.png）生成。

给定一个消息 `M`（img/leanpub_equation_439.png）和包含 `Y`（img/leanpub_equation_440.png）、`P`（img/leanpub_equation_441.png）和 `G`（img/leanpub_equation_442.png）的公钥，加密步骤取一对常规 Diffie-Hellman 密钥对并经过以下步骤：

1. 生成一个随机 `K`（img/leanpub_equation_443.png），使得 `0 < K < P - 1`（img/leanpub_equation_444.png）
2. 计算 `Gamma = G^{K} \mod P`（img/leanpub_equation_445.png）
3. 计算 `Phi = (PAD(M) * Y^{K}) \mod P`（img/leanpub_equation_446.png）
4. 返回 `(Gamma, Phi)`（img/leanpub_equation_447.png）

其中，`(Gamma, Phi)`（img/leanpub_equation_448.png）元组作为无符号整数返回，必要时会在导位补零，以使每个整数的编码长度与密钥相同。`PAD()`（img/leanpub_equation_449.png）函数就是我们之前看到的 OAEP 函数。

在解密时，一旦从编码中恢复了 `Gamma`（img/leanpub_equation_450.png）和 `Phi`（img/leanpub_equation_451.png），就可以通过单个步骤使用私值 `X`（img/leanpub_equation_453.png）和域参数 `P`（img/leanpub_equation_454.png）来恢复 `M`（img/leanpub_equation_452.png）：

1. 计算 `PAD(M) = (Gamma^{P - 1 - X} * Phi) \mod P`（img/leanpub_equation_455.png）

在兼容性方面，该算法通常没有问题，尽管你偶尔会遇到没有正确扩展 `(Gamma, Phi)`（img/leanpub_equation_456.png）元组编码的实现。

下面的示例展示了如何基于 SHA-256 摘要使用 ElGamal 进行 OAEP。使用了我们之前与 RSA 相同的 OAEP 参数。除了主要的算法名称（用于密钥对生成的 DH，以及加密名称开头的 ElGamal），你可以发现它与我们看到的 RSA 代码几乎完全相同。



```java
 /**
 * 示例展示了基于 ElGamal OAEP 的
 * 密钥封装与解封操作。
 */
 public class OAEPExampleWithElGamal
{
    /**
     * 使用基于提供者的参数生成一个 2048 位 DH 密钥对。
     *
     * @return 一个 DH KeyPair
     */
    public static KeyPair generateDHKeyPair()
        throws GeneralSecurityException
    {
        KeyPairGenerator keyPair = KeyPairGenerator.getInstance("DH", "BC");

        keyPair.initialize(2048);

        return keyPair.generateKeyPair();
    }

    /**
     * 使用 OAEP 算法生成封装的密钥，
     * 返回加密结果。
     *
     * @param dhPublic 用于封装的基础的公钥。
     * @param secretKey 要加密/封装的密钥密钥。
     * @return 如果签名验证通过则返回 true，否则返回 false。
     */
    public static byte[] keyWrapOAEP(
        PublicKey dhPublic, SecretKey secretKey)
        throws GeneralSecurityException
    {
        Cipher cipher = Cipher.getInstance(
            "ElGamal/NONE/OAEPwithSHA256andMGF1Padding", "BC");

        cipher.init(Cipher.WRAP_MODE, dhPublic);

        return cipher.wrap(secretKey);
    }

    /**
     * 返回在 wrappedKey 中加密的密钥密钥。
     *
     * @param dhPrivate 用于解封的私钥。
     * @param wrappedKey 加密的密钥密钥密钥。
     * @param keyAlgorithm 加密密钥所属的算法。
     * @return 解封后的 SecretKey。
     */
    public static SecretKey keyUnwrapOAEP(
        PrivateKey dhPrivate, byte[] wrappedKey, String keyAlgorithm)
        throws GeneralSecurityException
    {
        Cipher cipher = Cipher.getInstance(
            "ElGamal/NONE/OAEPwithSHA256andMGF1Padding", "BC");

        cipher.init(Cipher.UNWRAP_MODE, dhPrivate);

        return (SecretKey)cipher.unwrap(
                           wrappedKey, keyAlgorithm, Cipher.SECRET_KEY);
    }

    public static void main(String[] args)
        throws GeneralSecurityException
    {
        SecretKey aesKey = createTestAESKey();

        KeyPair kp = generateDHKeyPair();

        byte[] wrappedKey = keyWrapOAEP(kp.getPublic(), aesKey);

        SecretKey recoveredKey = keyUnwrapOAEP(
                                    kp.getPrivate(),
                                    wrappedKey, aesKey.getAlgorithm());

        System.out.println(
            Arrays.areEqual(aesKey.getEncoded(), recoveredKey.getEncoded()));
    }
 }
```

注意该代码使用了 2048 位的密钥。如果你尝试在此情况下转储密文，你会发现密文的长度是当你使用 RSA 时长度的两倍。

假设一切顺利，运行该示例应该产生以下输出，证明原始密钥字节已正确正确恢复：

```
true
```

## RSA-KEM

![RSA-KEM 用于加密和解密的原理图 - 注意它与 OAEP 的不同之处](img/chapter7----RSAKem.png)

RSA-KEM 用于加密和解密的原理图 - 注意它与 OAEP 的不同之处

RSA-KEM 密钥传输算法在 NIST SP 800-56B [30] 和 RFC 5990 [111] 中都有描述，后者详细说明了其在加密消息语法 (CMS) 中的用法。这是你在 RSA 算法最高安全级别上最理想的用法，这一点通过 RSA-KEM 拥有比 RSA-OAEP 更严密的安全证明得到了证实。该算法的唯一缺点是它产生的加密比相应的 RSA-OAEP 加密稍长。这是因为用于组成 RSA-KEM 消息的 RSA 块负载用于创建一个对称密钥，然后该对称密钥用于封装正在传输的密钥。

目前，RSA-KEM 仅在 BCFIPS API 中实现。

### RSA-KEM 密钥封装

密钥封装是一个两个阶段的过程。我们加密一个用于派生密钥密钥 (KEK) 的随机值，然后使用 KEK 封装我们想要保护的密钥密钥。给定我们的模 `N`，我们的公指数 `E` 以及长度 `kekLen`，我们执行以下操作：

1. 生成一个随机 `Z` 使得 `Z < N`
2. 计算 `Z^E mod N`
3. 派生 `KEK = KDF(Z, kekLen)`
4. 计算 `EK = Wrap(KEK)`
5. 设置 `EK = C || WK`
6. 返回 `EK`。

`KDF()` 函数通常是一个基于消息的密钥函数。`Wrap()` 函数我们在第 3 章中看到的封装函数之一。在基础级别，Bouncy Castle 的 RSA-KEM 使用 `Cipher` 类，其简单示例如下：

```java
 /**
  * 使用 KTS-KEM-KWS 算法生成封装的密钥，
  * 返回加密结果。
  *
  * @param rsaPublic 用于封装的基础的公钥。
  * @param ktsSpec 密钥参数。
  * @param secretKey 要加密/封装的密钥。
  * @return 如果签名验证通过则返回 true，否则返回 false。
  */
  public static byte[] keyWrapKEMS(
      PublicKey rsaPublic, KTSParameterSpec ktsSpec, SecretKey secretKey)
      throws GeneralSecurityException
  {
      Cipher cipher = Cipher.getInstance("RSA-KTS-KEM-KWS", "BCFIPS");

      cipher.init(Cipher.WRAP_MODE, rsaPublic, ktsSpec);

      return cipher.wrap(secretKey);
  }
```

从 方法的参数可以看出，封装密钥时需要考虑两个因素。一个是使用的 RSA 密钥的整体安全性，另一个是所选参数的整体安全性，对称算法的选择和 KDF 都有助于安全性。我们稍后将对参数进行更详细的查看。

### RSA-KEM 密钥解封

与 RSA-KEM 密钥封装一样，RSA-KEM 密钥解封也是两个阶段的过程。我们需要首先解密密钥密钥的材料，然后解密封装密钥以恢复我们发送的原始密钥。

给定我们的 RSA-KEM 输出 `WK`，模 `N` 和我们的私指数 `D`，执行以下操作：

1. 分解 `EK = C || WK`，其中 `C` 是 RSA 加密块，`WK` 是封装密钥。
2. 计算 `Z = C^D mod N`
3. 派生 `KEK = KDF(Z, kekLen)`
4. 计算 `K = Unwrap(KEK, WK)`
5. 返回 `K`。

在 JCE 级别，这再次转化为对 `Cipher` 类的使用：

```java
   /**
   * 返回封装在 wrappedKey 中的加密秘密密钥。
   *
   * @param rsaPrivate 用于解封装的私钥。
   * @param ktsSpec 密钥传输参数。
   * @param wrappedKey 加密后的秘密密钥。
   * @param keyAlgorithm 加密密钥对应的算法。
   * @return 解封装的 SecretKey。
   */
  public static SecretKey keyUnwrapKEMS(
      PrivateKey rsaPrivate, KTSParameterSpec ktsSpec,
      byte[] wrappedKey, String keyAlgorithm)
      throws GeneralSecurityException
  {
      Cipher cipher = Cipher.getInstance("RSA-KTS-KEM-KWS", "BCFIPS");

      cipher.init(Cipher.UNWRAP_MODE, rsaPrivate, ktsSpec);

      return (SecretKey)cipher.unwrap(
                                 wrappedKey, keyAlgorithm, Cipher.SECRET_KEY);
  }
```

注意：如代码所所示，为了使 RSA-KEM 运行，双方必须约定相同的参数。

## 整合一切

`KTSParameterSpec` 提供了常量 `KDF2`（它指向 X9.63 KDF）和 `KDF3`（它指向以前称为 NIST Concatenation KDF 的算法）。

以下示例使用了默认 KDF 的 RSA-KEM 方法，该方法基于使用 SHA-256 的 NIST 拼接 KDF。在这种情况下，参数还指定了 KEK（密钥加密密钥）为 256 位，并使用 `AESKWP` 作为密钥封装函数。

```java
 /**
  * 显示基于 RSA-KEMS 的秘密密钥封装和解封装的简单示例。
  */
 public class KEMSExample
 {
     public static void main(String[] args)
         throws GeneralSecurityException
     {
         SecretKey aesKey = new SecretKeySpec(
                                 Hex.decode("000102030405060708090a0b0c0d0e0f"),
                                 "AES");

         KeyPairGenerator keyPair = KeyPairGenerator.getInstance("RSA", "BCFIPS");

         keyPair.initialize(2048);

         KeyPair kp = keyPair.generateKeyPair();

         KTSParameterSpec ktsSpec =
                             new KTSParameterSpec.Builder(
                                 "AESKWP", 256,
                                 Strings.toByteArray("OtherInfo Data")).build();

         byte[] wrappedKey = keyWrapKEMS(kp.getPublic(), ktsSpec, aesKey);

         SecretKey recoveredKey = keyUnwrapKEMS(
                                     kp.getPrivate(), ktsSpec,
                                     wrappedKey, aesKey.getAlgorithm());

         System.out.println(
             Arrays.areEqual(aesKey.getEncoded(), recoveredKey.getEncoded()));
     }
 }
```

正如我们在第 3 章中所看到的，OtherInfo 数据为产生 KEK 的 `KDF` 函数提供了额外的材料。我们稍后还会看到 OtherInfo 也可以将其他算法的输出引入混合中。Bouncy Castle 还提供了一个用于从 ASN.1 编码构建 OtherInfo 的辅助类——`org.bouncycastle.crypto.util` 包中的 `DEROtherInfo` 类。

运行该示例应该产生以下输出，表明组成 `aesKey` 的字节已成功通过了封装和解封装过程：

```
true
```

通常，以 RSA-OAEP 为例，你会预期 `wrappedKey` 长度为 256 字节。如果你检查示例代码生成的 `wrappedKey` 长度，你会发现字节数组长度为 280 字节。在这种情况下，额外的 24 字节数据代表了秘密密钥的 AESKWP 封装。

## 密钥协商与密钥交换

![双方之间基本密钥协商的操作](img/chapter7----KeyAgree.png)

双方之间基本密钥协商的操作

我们现在要查看的算法其基础是 Diffie-Hellman-Merkle^(13) 密钥交换。它更为人知的是 Diffie-Hellman，基于 Whitfield Diffie 和 Martin Hellman 1976 年的原始论文，被视为第一个实用公钥密码学方案之一。有趣的是，与 RSA 一样，事实证明该方案是 1969 年在英国 GCHQ 由 James Ellis、Clifford Cocks 和 Malcolm Williamson 独立开发的。密钥协商的主要 NIST 标准是 NIST SP 800-56A“使用离散对数密码学的成对密钥建立方案” [29]，但我们过的许多 EC 签名方案（如来自俄罗斯、中国和乌克兰的）也有相关的密钥协商算法。Diffie-Hellman 首次出现在 IETF RFC 中可能是 1999 年的 RFC 2631 [75]，这与开发变为 X9.42 的工作有关 [66]。从那时以后围绕素域和椭圆曲线出现了多次更新和替代提案。

### 有限域上的 Diffie-Hellman

Diffie-Hellman 基于一组参数 (P, Q, G)，其中参数具有以下特征：

*   P：一个素数。
*   Q：(P-1) 的一个素数因子。
*   G：有限域 GF(P) 中阶为 Q 的子群的生成元。

通常 Q 参数会被忽略，并且在 PKCS #5 中有这种验证公钥的示例。密钥协商操作非常简单。考虑仅双方的情况，协议如下：

1.  A 选择一个随机秘密 x，其中 1 ≤ x ≤ P-2。
2.  B 选择一个随机秘密 y，其中 1 ≤ y ≤ P-2。
3.  A 向 B 发送 G^x，B 向 A 发送 G^y。
4.  A 计算 Z = (G^y)^x，如果 Z ≤ 1 或 Z = P-1，则报错。
5.  B 计算 Z = (G^x)^y，如果 Z ≤ 1 或 Z = P-1，则报错。



## 6. A 返回 Z

## 7. B 返回 Z

共享值 Z 然后可以用某种方式用于促进 A 和 B 之间的加密通信。了解任何一方的随机秘密被称为私钥 `X`，而公有值 `G^X` 被称为公钥 `Y`。我们将在后的讨论中看到它的用法。

关于该协议需要识别的一点是，它并不局限于双方。其结果是，当协议在远程双方之间执行时，必须明确：如果双方都没有采取任何步骤来验证对方公钥的来源，就可能发生中间人攻击。

IETF 标准（如 `RFC 5114` [96]）中描述了若干组用于 Diffie-Hellman 的推荐参数集。你也可以在 `JCE` 中使用 `AlgorithmParameterGenerator` 生成自己的参数集。与 `DSA` 一样，生成 Diffie-Hellman 参数的过程非常缓慢。这不是你会希望频繁执行的操作。以下方法展示了如何为创建 2048 位密钥生成参数的示例：

```java
 1   /**
 2    * Return a generated set of DH parameters suitable for creating 2048
 3    * bit keys.
 4    *
 5    * @return a DHParameterSpec holding the generated parameters.
 6    */
 7   public static DHParameterSpec generateDHParams()
 8       throws GeneralSecurityException
 9   {
10       AlgorithmParameterGenerator paramGen =
11           AlgorithmParameterGenerator.getInstance("DH", "BC");
12 
13       paramGen.init(2048);
14 
15       AlgorithmParameters params = paramGen.generateParameters();
16 
17       return params.getParameterSpec(DHParameterSpec.class);
18   }
```

该示例方法返回一个 `DHParameterSpec`，它是 `JCE` 类，支持 `PKCS #3` 中描述的 Diffie-Hellman 参数。由于如此，`DHParameterSpec` 仅支持 `P`、`G` 以及一个额外的值 `L`。`L` 值用于指定 Diffie-Hellman 操作中私有值的位长度。`L` 的目的是为了使计算更高效——例如，对于 2048 位的私有值，计算（如果仅由私有值描述）被认为安全强度为 1024 位，即 `2^2048` 的平方根。考虑到目前 2048 位的 Diffie-Hellman 密钥认为提供 112 位安全性，私有值可以小至 224 位。这在 `RFC 5114` 第 4 节 [96] 以及 `RFC 4419` [90] 第 6.2 节中进一步讨论，后者建议私有值至少是协商生成的对称密钥大小的两倍。完全听凭运气，最可能的私有值可能达 2047 位，这在这种情况下显然是过度的。

`JCE` 还支持 `DHGenParameterSpec` 类，该类同时接受基质数的大小和建议的私有值大小。例如，为了生成 2048 位参数并额外指定 256 位的私有值大小，你可以将 `paramGen` 的初始化更改为如下：

```java
 paramGen.init(new DHGenParameterSpec(2048, 256));
```

Bouncy Castle API 还支持 `DHDomainParameterSpec`。它可以用于检索 `DHParameterSpec` 的扩展，该扩展包含 `Q` 值以及验证参数（在 `BCFIPS` 的情况下）。

### 密钥对生成

密钥对生成涉及创建一个公有值（称为 `Y`）和一个私有值（称为 `X`）。私有值 `X` 是随机生成的，其中 `1 <= X <= P - 2`，而 `Y` 的计算方式为 `Y = G^X mod P`。然后使用私有值 `X` 初始化密钥协商操作，并将 `Y` 发送给我们尝试与之计算共享密钥的对方。

与其他算法一样，在 Java 中生成密钥对的最基本方法是创建一个 `KeyPairGenerator` 并简单地指定大小，如下：

```java
 1   /**
 2    * Generate a 2048 bit DH key pair using provider based parameters.
 3    *
 4    * @return a DH KeyPair
 5    */
 6   public static KeyPair generateDHKeyPair()
 7       throws GeneralSecurityException
 8   {
 9       KeyPairGenerator keyPairGen = KeyPairGenerator.getInstance("DH", "BC");
10       keyPairGen.initialize(2048);
11       return keyPairGen.generateKeyPair();
12   }
```

在上述两种情况下，示例返回的 `KeyPair` 都包含该包中的 `DHPublicKey` 和 `DHPrivateKey`。

### 密钥协商

Java 的 `KeyAgreement` 类将协议分为三个部分：

* `init()` 接收调用者的私钥以及可选的任何其他参数。
* `doPhase()` 接收另一个的公钥和一个布尔值 `lastPhase`——当 `lastPhase` 为 `true` 时，意味着协议已完成。
* `generate()` 在完成后被调用。这些方法以不同的形式生成密钥。

获取共享密钥的最基本方法是作为字节数组。以下方法演示了双方之间的 Diffie-Hellman 协商，共享密钥以字节数组的形式返回。为了演示，该方法还提取了 `KeyAgreement` 实例返回的密钥的前 32 字节并将其作为返回值。

```java
 1   /**
 2    * Generate an agreed secret byte value of 32 bytes in length.
 3    *
 4    * @param aPriv 节点 A 的私钥。
 5    * @param bPub 节点 B 的公钥。
 6    * @return 生成密钥的前 32 字节。
 7    */
 8   public static byte[] generateSecret(PrivateKey aPriv, PublicKey bPub)
 9       throws GeneralSecurityException
10   {
11       KeyAgreement agreement = KeyAgreement.getInstance("DH", "BC");
12 
13       agreement.init(aPriv);
14 
15       agreement.doPhase(bPub, true);
16 
17       return Arrays.copyOfRange(agreement.generateSecret(), 0, 32);
18   }
```

如果你移除对 `Arrays.copyOfRange()` 的调用，你会发现返回值比 256 位大得多。

```java
 1   /**
    * 生成一个长度为 256 位的约定 AES 密钥值。
    *
    * @param aPriv A 方的私钥。
    * @param bPub B 对方的公钥。
    * @return 生成的 AES 密钥 (256 位)。
    */
   public static SecretKey generateAESKey(PrivateKey aPriv, PublicKey bPub)
       throws GeneralSecurityException
   {
       KeyAgreement agreement = KeyAgreement.getInstance("DH", "BC");

      agreement.init(aPriv);

      agreement.doPhase(bPub, true);

      return agreement.generateSecret("AES");
   }
```

这个示例方法仍然在使用原始的 Diffie-Hellman 计算。当我们查看下面示例的输出时，我们将看到这意味着什么。

### 初始示例

在查看示例之前，为了演示 Diffie-Hellman 使用的几点，我们需要定义一些实用方法，这些方法将允许我们对 JCE 生成的公钥和私钥的值进行控制。

如果你查看以下类，你会发现它通过 Bouncy Castle 的 `FixedSecureRandom` 类提供了一组硬编码的私有值，并将其与提供者的默认 Diffie-Hellman 参数相结合，以生成具有 256 位私钥值的密钥。`FixedSecureRandom` 的两个参数意味着 `insecureRandom` 字段可以用于生成两个密钥。

```java
 1 public class InsecureDHUtils
 2 {
 3     // 设置常量安全随机数以产生常量私钥，
 4     private static SecureRandom insecureRandom = new FixedSecureRandom(
 5         new FixedSecureRandom.Source[] {
 6         new FixedSecureRandom.BigInteger(256,
 7             Hex.decode(
 8                 "914bb9b3d677c4ce87e5f671a88c85c0" +
 9                     "615228c6f7d6fbfdee89092f69609128")),
10         new FixedSecureRandom.BigInteger(256,
11             Hex.decode(
12                 "837028bb0ccdaf1cf9a390b1f84bf916" +
 13                     "999ba4760d4297124ca991a1e616b676")) });
14 
15 
16     private static DHParameterSpec dhSpec;
17 
18     /**
19      * 初始化用于密钥对生成的的 Diffie-Hellman 参数
20      */
21     static void insecureUtilsInit()
22         throws GeneralSecurityException
23     {
24         // 获取一个常规参数集并为具有 256 位
25         // 私钥值的密钥进行定制。
26         KeyPair kp = generateDHKeyPair();
27         dhSpec = ((DHPublicKey)kp.getPublic()).getParams();
28         dhSpec = new DHParameterSpec(dhSpec.getP(), dhSpec.getG(), 256);
29     }
30 
31     /**
32      * 使用我们的常量随机源生成密钥对。
33      * @return 一个 Diffie-Hellman 密钥对。
34      */
35     static KeyPair insecureGenerateDHKeyPair()
36         throws GeneralSecurityException
37     {
38         KeyPairGenerator keyPairGen = KeyPairGenerator.getInstance("DH", "BC");
39 
40         keyPairGen.initialize(dhSpec, insecureRandom);
41 
42         return keyPairGen.generateKeyPair();
43     }
44 }
```

结合我们之前过的 `generateSecret()` 和 `generateAESKey()` 方法，这些实用方法可以用于生成一个双方之间使用 Diffie-Hellman 的示例，通过密钥协商同时生成共享密钥和 AES 密钥，如下：



```java
 1 /**
 2  * 基础 Diffie-Hellman 示例，展示了使用 KeyAgreement 类
 3  * 生成字节数组和密钥密钥。
 4  * <b>注意</b>：此示例正在生成常量密钥，除非你确实打算这样做，否则
 5  * 不要在现实中使用该密钥生成代码！
 6  */
 7 public class BasicDHExample
 8 {
 9     // 使用 A 和 B 方的密钥对生成并打印共享密钥。
10     private static byte[] generateSecretValue(KeyPair aKp, KeyPair bKp)
11         throws GeneralSecurityException
12     {
13         byte[] aValue = generateSecret(aKp.getPrivate(), bKp.getPublic());
14         byte[] bValue = generateSecret(bKp.getPrivate(), aKp.getPublic());
15 
16         System.out.println("aS: " + Hex.toHexString(aValue));
17         System.out.println("bS: " + Hex.toHexString(bValue));
18 
19         return aValue;
20     }
 21     // 使用 A 和 B 方的密钥对生成并打印 AES 密钥。
 22     private static SecretKey generateAESKey(KeyPair aKp, KeyPair bKp)
 23         throws GeneralSecurityException
 24     {
 25         byte[] aValue = generateSecret(aKp.getPrivate(), bKp.getPublic());
 26         byte[] bValue = generateSecret(bKp.getPrivate(), aKp.getPublic());
 27 
 28         System.out.println("aS: " + Hex.toHexString(aValue));
 29         System.out.println("bS: " + Hex.toHexString(bValue));
 30 
 31         return aValue;
 32     }
 33 
 34     public static void main(String[] args)
 35         throws Exception
 36     {
 37         insecureUtilsInit();
 38 
 39         // 为 A 生成密钥对。
 40         KeyPairGenerator keyPairGenA = KeyPairGenerator.getInstance("DH", "BC");
 41         keyPairGenA.initialize(dhSpec, insecureRandom);
 42         KeyPair aKp = keyPairGenA.generateKeyPair();
 43 
 44         // 为 B 生成密钥对。
 45         KeyPairGenerator keyPairGenB = KeyPairGenerator.getInstance("DH", "BC");
 46         keyPairGenB.initialize(dhSpec, insecureRandom);
 47         KeyPair bKp = keyPairGenB.generateKeyPair();
 48 
 49         // 使用 A 和 B 方的密钥对生成并打印共享密钥。
 50         byte[] aValue = generateSecret(aKp.getPrivate(), bKp.getPublic());
 51         byte[] bValue = generateSecret(bKp.getPrivate(), aKp.getPublic());
 52 
 53         System.out.println("aS: " + Hex.toHexString(aValue));
 54         System.out.println("bS: " + Hex.toHexString(bValue));
 55 
 56         return aValue;
 57     }
 58 }
```

当你运行此示例时，它将打印 4 行内容：

```
aS: 914bb9b3d677c4ce87e5f671a88c85c0615228c6f7d6fbfdee89092f69609128
bS: 837028bb0ccdaf1cf9a390b1f84bf916999ba4760d4297124ca991a1e616b676
aS: 914bb9b3d677c4ce87e5f671a88c85c0615228c6f7d6fbfdee89092f69609128
bS: 837028bb0ccdaf1cf9a390b1f84bf916999ba4760d4297124ca991a1e616b676
```

关键材料通常会根据每次调用而有所不同，它通过使用 Bouncy Castle 特有的 `AlgorithmParameterSpec` 来管理，即 `org.bouncycastle.jcajce.spec.UserKeyingMaterialSpec` 类。该类的名称源于 RFC 5652 [10] 中用于加密消息语法 (CMS) 密钥协商接收者的参数名称。

`UserKeyingMaterialSpec` 仅接收一个字节数组作为内容。

```java
 1   /**
 2    * 生成一个长度为 256 位的约定 AES 密钥值。
 3    *
 4    * @param aPriv Party A 的私钥。
 5    * @param bPub Party B 的公钥。
 6    * @return 生成的 AES 密钥 (256 bits)。
 7    */
 8   public static SecretKey generateAESKey(
 9       PrivateKey aPriv, PublicKey bPub, byte[] keyMaterial)
10       throws GeneralSecurityException
11   {
12       KeyAgreement agreement = KeyAgreement.getInstance("DHwithSHA256KDF", "BC");
 13 
14       agreement.init(aPriv, new UserKeyingMaterialSpec(keyMaterial));
 15 
16       agreement.doPhase(bPub, true);
 17 
18       return agreement.generateSecret("AES");
19   }
```

如何格式化用于构建 `UserKeyingMaterialSpec` 的字节数组由你决定。例如，NIST SP 800-56A [29] 和 NIST SP 800-56B [30] 都对如何构建用户密钥材料提供了详细建议，你也可以利用 Bouncy Castle 包含的 `DEROtherInfo` 类。

下一个示例使用了我们新的 `generateAESKey()` 方法，通过 KDF 结合额外的密钥材料。为了对比，它仍然使用了与之前相同的方法从共享密钥生成字节数组。

```java
 1 /**
 2  * 基础 Diffie-Hellman 示例，展示了如何使用 KeyAgreement 类
 3  * 通过额外的密钥材料生成字节数组和密钥密钥。
 4  * <b>注意</b>：此示例正在生成常量密钥，除非你确实打算这样做，否则
 5  * 不要在实际生活中使用此密钥生成代码！
 6  */
 7 public class UKMDHExample
 8 {
 9     // 使用 A 和 B 密钥对生成并打印共享密钥。
 10     private static byte[] generateSecretValue(KeyPair aKp, KeyPair bKp)
 11         throws GeneralSecurityException
 12     {
 13         byte[] aValue = generateSecret(aKp.getPrivate(), bKp.getPublic());
 14         byte[] bValue = generateSecret(bKp.getPrivate(), aKp.getPublic());
 15 
 16         System.out.println("aS: " + Hex.toHexString(aValue));
 17         System.out.println("bS: " + Hex.toHexString(bValue));
 18 
 19         return aValue;
 20     }
 21 
 22     // 使用 A 和 B 密钥对生成并打印 AES 密钥。
 23     // 注意：这次我们引入了一些字节的密钥材料。
 24     private static SecretKey generateAESKeyValue(KeyPair aKp, KeyPair bKp)
 25         throws GeneralSecurityException
 26     {
 27         byte[] keyMaterial = Strings.toByteArray("For an AES key");
 28 
 29         SecretKey aKey = generateAESKey(
 30             aKp.getPrivate(), bKp.getPublic(), keyMaterial);
 31         SecretKey bKey = generateAESKey(
 32             bKp.getPrivate(), aKp.getPublic(), keyMaterial);
 33 
 34         System.out.println("aK: " + Hex.toHexString(aKey.getEncoded()));
 35         System.out.println("bK: " + Hex.toHexString(bKey.getEncoded()));
 36 
 37         return aKey;
 38     }
 39 
 40     public static void main(String[] args)
 41         throws Exception
 42     {
 43         // 设置用于密钥对生成的参数规范
 44         insecureUtilsInit();
 45 
 46         // 为 A 部分和 B 部分生成密钥对
 47         KeyPair aKp = insecureGenerateDHKeyPair();
 48         KeyPair bKp = insecureGenerateDHKeyPair();
 49 
 50         // 密钥协商生成共享密钥
 51         byte[] retGenSec = generateSecretValue(aKp, bKp);
 52         // 密钥协商生成 AES 密钥
 53         SecretKey retAESKey = generateAESKeyValue(aKp, bKp);
 54 
 55         // 比较两个返回值。
 56         System.err.println(Arrays.areEqual(retGenSec, retAESKey.getEncoded()));
 57     }
 58 }
```

尝试运行该示例，你应该能看到它产生以下输出：

```
aS: 8412f73f3e704cdf
```

### 使用 KeyAgreement 类

接下来要查看的是如何使用 `KeyAgreement` 类利用统一 Diffie-Hellman（Unified Diffie-Hellman）模型。在该协议中，临时密钥被视为协商的参数。在 Bouncy Castle 中，这些额外密钥和密钥通过 `DHUParameterSpec` 进行配置，该类可以在 `org.bouncycastle.jcajce.spec` 包中找到。

下面的 Java 方法展示了使用统一 Diffie-Hellman 模型和基于 SHA-256 的 X9.63 KDF 生成基本 AES 密钥所需的代码。

```java
 1   /**
 2    * 使用 Unified Diffie-Hellman 模型生成长度为 256 位的约定的 AES 密钥值
 3    *
 4    *
 5    * @param aPriv Party A 的私钥。
 6    * @param aPubEph Party A 的临时公钥。
 7    * @param aPrivEph Party A 的临时私钥。
 8    * @param bPub Party B 的公钥。
 9    * @param bPubEph Party B 的临时公钥。
 10    * @return 生成的 AES 密钥 (256 位)。
 11    */
 12   public static SecretKey dhuGenerateAESKey(
 13       PrivateKey aPriv, PublicKey aPubEph, PrivateKey aPrivEph,
 14       PublicKey bPub, PublicKey bPubEph, byte[] keyMaterial)
 15       throws GeneralSecurityException
 16   {
 17       KeyAgreement agreement =
 18           KeyAgreement.getInstance("DHUwithSHA256KDF", "BC");
 19 
 20       agreement.init(aPriv,
 21           new DHUParameterSpec(aPubEph, aPrivEph, bPubEph, keyMaterial));
 22 
 23       agreement.doPhase(bPub, true);
 24 
 25       return agreement.generateSecret("AES");
 26   }
```

如你所见，统一模型通过将算法名称以“DHU”而不是简单的“DH”来指定。

以下示例展示了如何使用 `dhuGenerateAESKey()` 方法在两个双方之间生成共享的 AES 密钥。

```java
 1 /**
 2  * 基础统一 Diffie-Hellman 示例，展示了协议中每个双方使用两个密钥对
 3  *，其中一组被视为临时的。
 4  */
 5 public class UnifiedDHExample
 6 {
 7     public static void main(String[] args)
 8         throws Exception
 9     {
 10         // 为方 A 和方 B 生成密钥对
 11         KeyPair aKpS = generateDHKeyPair();
 12         KeyPair aKpE = generateDHKeyPair();    // A 的临时密钥对
 13         KeyPair bKpS = generateDHKeyPair();
 14         KeyPair bKpE = generateDHKeyPair();    // B 的临时密钥对
 15 
 16         // 密钥协商生成 AES 密钥
 17         byte[] keyMaterial = Strings.toByteArray("For an AES key");
 18 
 19         SecretKey aKey = dhuGenerateAESKey(
 20             aKpS.getPrivate(),
 21             aKpE.getPublic(), aKpE.getPrivate(),
 22             bKpS.getPublic(), bKpE.getPublic(), keyMaterial);
 23         SecretKey bKey = dhuGenerateAESKey(
 24             bKpS.getPrivate(),
 25             bKpE.getPublic(), bKpE.getPrivate(),
 26             aKpS.getPublic(), aKpE.getPublic(), keyMaterial);
 27 
 28         // 比较两个返回值。
 29         System.out.println(
 30             Arrays.areEqual(aKey.getEncoded(), bKey.getEncoded()));
 31     }
 32 }
```



在这种情况下，由于使用了随机密钥，我们判断其正常运行的最好标志是最后的密钥比较。假设一切顺利，该示例将产生以下结果，表明两个密钥计算出的值相同：

```
true
```

通过查看示例你可以发现，任何一方的静态密钥对也可以用于协议中，以弥补缺少一组临时密钥对的情况。这意味着作为替代的静态密钥也将被传递并作为 `dhuGenerateAESKey()` 方法的配置参数使用。这就是我们之前提到的单次协议。

### MQV

MQV 是另一种同样利用临时密钥对的密钥协商协议。它以其发明者 Alfred Menezes、Minghua Qu 和 Scott Vanstone 的姓氏命名，该协议首次在 1995 年的论文《Some New Key Agreement Protocols Providing Mutual Implicit Authentication》[4] 中描述。MQV 与统一模型的不同在于，它还结合了基于双方静态私钥的“隐式签名”。这意味着任何对协议进行中间人攻击的尝试都会失败，因为会被检测到。这种“隐式签名”意味着 MQV 在开箱即用性方面比统一模型提供了更强的验证基础。

```java
  /**
   * 使用 MQV 生成一个长度为 256 位的约定的 AES 密钥。
   *
   * @param aPriv A 方的私钥。
   * @param aPubEph A 方的临时公钥。
   * @param aPrivEph A 方的临时私钥。
   * @param bPub B 方的公钥。
   * @param bPubEph B 方的临时公钥。
   * @return 生成的 AES 密钥 (256 位)。
   */
  public static SecretKey mqvGenerateAESKey(
      PrivateKey aPriv, PublicKey aPubEph, PrivateKey aPrivEph,
      PublicKey bPub, PublicKey bPubEph, byte[] keyMaterial)
      throws GeneralSecurityException
  {
      KeyAgreement agreement =
          KeyAgreement.getInstance("MQVwithSHA256KDF", "BC");

      agreement.init(aPriv,
          new MQVParameterSpec(aPubEph, aPrivEph, bPubEph, keyMaterial));

      agreement.doPhase(bPub, true);

      return agreement.generateSecret("AES");
  }
```

将示例放入简单的用例中，我们得到如下代码：

```java
/**
 * 基础 Diffie-Hellman MQV 示例，展示了协议中每个方使用两对密钥，
 * 其中一组被视为临时密钥。
 */
public class MQVDHExample
{
    public static void main(String[] args)
        throws Exception
    {
        // 为 A 方和 B 方生成密钥对
        KeyPair aKpS = generateDHKeyPair();
        KeyPair aKpE = generateDHKeyPair();    // A 的临时密钥对
        KeyPair bKpS = generateDHKeyPair();
        KeyPair bKpE = generateDHKeyPair();    // B 的临时密钥对

        // 密钥协商生成 AES 密钥
        byte[] keyMaterial = Strings.toByteArray("For an AES key");

        SecretKey aKey = mqvGenerateAESKey(
            aKpS.getPrivate(),
            aKpE.getPublic(), aKpE.getPrivate(),
            bKpS.getPublic(), bKpE.getPublic(), keyMaterial);
        SecretKey bKey = mqvGenerateAESKey(
            bKpS.getPrivate(),
            bKpE.getPublic(), bKpE.getPrivate(),
            aKpS.getPublic(), aKpE.getPublic(), keyMaterial);

        // 比较两个返回值。
        System.out.println(
            Arrays.areEqual(aKey.getEncoded(), bKey.getEncoded()));
    }
}
```

运行该示例应产生以下输出，表明两个密钥计算出的值相同：

```
true
```

希望你也能看到示例中的任何一个临时密钥如何被替换为同方的静态密钥，从而产生单次通过版本的 MQV 协议。

### 椭圆曲线 Diffie-Hellman

我们目前为止关于 Diffie-Hellman 的大部分内容同样适用于使用椭圆曲线密码学 (ECC) 执行该协议。椭圆曲线 (EC) 提供了类似的性能优势，但在同等安全水平下密钥尺寸小得多。

虽然现在某些标准中有了针对 EC 密钥协商的特定参数集，但通常情况下，EC Diffie-Hellman 可以使用 ECDSA 相同的 EC 参数集生成的密钥来执行。在后续章节的示例代码中，我们假设你有权访问第 6 章中为 ECDSA 定义的密钥对生成方法。

### 基础密钥协商

假设阶因子 1，EC 的基本步骤如下：

1. ![A](img/leanpub_equation_574.png) 将其公钥 ![W_a](img/leanpub_equation_575.png) 发给 ![B](img/leanpub_equation_576.png)

2. ![B](img/leanpub_equation_577.png) 将其公钥 ![W_b](img/leanpub_equation_578.png) 发给 ![A](img/leanpub_equation_579.png)

3. ![A](img/leanpub_equation_580.png) 计算 `(x, y) = d_aW_b`。如果 `((x, y)](images/leanpub_equation_582.png)` 位于 `\infty](images/leanpub_equation_583.png)` 则返回无效

4. ![B](img/leanpub_equation_584.png) 计算 `(x, y) = d_bW_a`。如果 `((x, y)](images/leanpub_equation_586.png)` 位于 `\infty](images/leanpub_equation_587.png)`则返回无效

5. ![A](img/leanpub_equation_588.png) 返回 `x](images/leanpub_equation_589.png)` 

6. ![B](img/leanpub_equation_590.png) 返回 `x](images/leanpub_equation_591.png)`

这个直接过程中的唯一陷阱在于，所涉及的阶因子并不总是 1。如果不考虑阶因子，人员可能会使用特殊构造的公钥，从而导致对方密钥的某些泄露。为了防止这种情况，接收公钥的方需要确保其被强制进入曲线的子群中。处理这种阶因子的方法有两种。第一种（NIST 推荐）是直接乘以阶因子，因此步骤 4 和 5 替换为：

1. ![A](img/leanpub_equation_592.png) 计算 `(x, y) = d_aW_b`。如果 `((x, y)](images/leanpub_equation_594.png)` 位于 `\infty](images/leanpub_equation_595.png)`则返回无效

2. ![B](img/leanpub_equation_596.png) 计算 `(x, y) = d_bW_a`。如果 `((x, y)](images/leanpub_equation_598.png)` 位于 `\infty](images/leanpub_equation_599.png)`则返回无效

第二方法是乘以阶因子，然后乘以其逆。在这种情况下，步骤 4 和 5 需要扩展为下面的步骤：

1. 设置 `l = h^{-1} \mod N](images/leanpub_equation_600.png)

2. ![A](img/leanpub_equation_601.png) 计算 `P_b = hW_b](images/leanpub_equation_602.png)

3. ![B](img/leanpub_equation_603.png) 计算 `P_a = hW_a](images/leanpub_equation_604.png)

4. ![A](img/leanpub_equation_605.png) 计算 `(x, y) = (d_al)P_b`。如果 `((x, y)](images/leanpub_equation_607.png)` 位于 `\infty](images/leanpub_equation_608.png)`则返回无效

5. ![B](img/leanpub_equation_609.png) 计算 `(x, y) = (d_bl)P_a`。如果 `((x, y)](images/leanpub_equation_611.png)` 位于 `\infty](images/leanpub_equation_612.png)`则返回无效

其中 `N](images/leanpub_equation_613.png)` 是与所使用的 EC 参数集相关的曲线的阶。

```java
 1   /**
 2    * 生成长度为 256 位的约定的 AES 密钥值。
 3    *
 4    * @param aPriv A 方的私钥。
 5    * @param bPub B 方的公钥。
 6    * @param keyMaterial 与密钥混合的用户密钥材料。
 7    * @return 生成 AES 密钥 (256 位)。
 8    */
 9   public static SecretKey ecGenerateAESKey(
10       PrivateKey aPriv, PublicKey bPub, byte[] keyMaterial)
11       throws GeneralSecurityException
12   {
13       KeyAgreement agreement =
14           KeyAgreement.getInstance("ECCDHwithSHA256KDF", "BC");
15 
16       agreement.init(aPriv, new UserKeyingMaterialSpec(keyMaterial));
17 
18       agreement.doPhase(bPub, true);
19 
20       return agreement.generateSecret("AES");
21   }
```

这是一个简单的示例，展示了双方之间如何使用 `ecGenerateAESKey()` 方法生成共享的 AES 密钥：

```java
 1 public class ECCDHExample
 2 {
 3     public static void main(String[] args)
 4         throws Exception
 5     {
 6         //为 A 和 B 方生成密钥对
 7         KeyPair aKp = generateECKeyPair();
 8         KeyPair bKp = generateECKeyPair();
 9 
10         // 密钥协商生成共享密钥
11         byte[] keyMaterial = Strings.toByteArray("For an AES key");
12 
13         SecretKey aKey = ecGenerateAESKey(
14             aKp.getPrivate(), bKp.getPublic(), keyMaterial);
15         SecretKey bKey = ecGenerateAESKey(
16             bKp.getPrivate(), aKp.getPublic(), keyMaterial);
17 
18         // 比较两个返回值。
19         System.out.println(
20             Arrays.areEqual(aKey.getEncoded(), bKey.getEncoded()));
21     }
 22 }
```

你可以看到，这种模式与我们在有限域上 Diffie-Hellman 中看到的完全相同。唯一的区别在于密钥的生成方式。根据现有的惯例，运行此示例应该显示生成的两个密钥是相同的，并产生以下输出：

```
true
```

### 添加临时密钥

基于椭圆曲线的协商也支持统一模型（Unified Model）和 MQV。这两种方法都记录在 NIST SP 800-56A [29] 中。此外基于椭圆曲线的 MQV 也在 RFC 5753 [105] 中定义用于 CMS。

需要注意的是，执行 ECMQV 的某些方法目前受专利保护，如 RFC 5753 相关的 IPR 披露 [70] 所示。

### ECDH - 统一模型

在 ECC 下，统一模型遵循我们之前看到的相同过程。从 A 方的角度来看，该过程遵循以下步骤：

1. ![A](img/leanpub_equation_615.png) 向 ![B](img/leanpub_equation_617.png) 发送他们的公钥 ![(W_sa, W_ea)](img/leanpub_equation_616.png)

2. ![B](img/leanpub_equation_618.png) 向 ![A](img/leanpub_equation_620.png) 发送他们的公钥 ![(W_sb, W_eb)](img/leanpub_equation_619.png)

3. ![A](img/leanpub_equation_621.png) 计算 ![(x_s, y_s) = d_saW_sb](img/leanpub_equation_622.png)。如果 ![((x_s, y_s)](img/leanpub_equation_623.png) 位于 ![\infty)](img/leanpub_equation_624.png) 则返回无效。

4. ![A](img/leanpub_equation_625.png) 计算 ![(x_e, y_e) = d_eaW_eb](img/leanpub_equation_626.png)。如果 ![((x_e, y_e)](img/leanpub_equation_627.png) 位于 ![\infty)](img/leanpub_equation_628.png) 则返回无效。

5. ![A](img/leanpub_equation_629.png) 返回 ![x_e \parallel x_s](img/leanpub_equation_630.png)

在 NIST SP 80-56A 中，上述过程被调整为包含与我们之前相同的因子的乘法。也可以通过*清除*因子来达到相同的效果。

下面的示例方法展示了在统一模型下使用因子 ECDH 的情况，假设传入了完整的密钥。与之前的统一模型示例一样，它的密钥派生也是基于 SHA-256 的 X9.63 KDF。

```java
 1   /**
 2    * 使用 EC 统一 Diffie-Hellman 模型生成长度为 256 位的约定的 AES 密钥值。
 3    *
 4    * @param aPriv A 方的私钥。
 5    * @param aPubEph A 方的临时公钥。
 6    * @param aPrivEph A 方的临时私钥。
 7    * @param bPub B 方的公钥。
 8    * @param bPubEph B 方的临时公钥。
 10   * @return 生成的 AES 密钥 (256 位)。
 11   */
 12   public static SecretKey ecGenerateAESKey(
13       PrivateKey aPriv, PublicKey aPubEph, PrivateKey aPrivEph,
14       PublicKey bPub, byte[] keyMaterial)
15       throws GeneralSecurityException
16   {
17       KeyAgreement agreement =
18           KeyAgreement.getInstance("ECCDHwithSHA256KDF", "BC");
19 
20       agreement.init(aPriv, new UserKeyingMaterialSpec(keyMaterial));
21 
22       agreement.doPhase(bPub, true);
23 
24       return agreement.generateSecret("AES");
25   }
```



密钥确认在 NIST SP 800-56A [29] 第 5.9 节中描述。它提供了另一种引入或加强与密钥协商机制配合使用的身份验证机制。基本技术并不难理解——用于生成共享密钥的 `KDF` 也用于生成共享的 MAC 密钥。通过将 `KDF` 生成的派生密钥材料分为两部分来实现：

![Mac \parallel SecretKey = DerivedKeyMaterial](img/leanpub_equation_647.png)

NIST SP 800-56A 第 5.9.1 至 5.9.3 节对哪些数据适合包含在 MAC 处理的数据中进行了详细讨论。可能的数据包括诸如公钥、参与者的身份标识符（IDs）和/或之前约定的秘密值（secret）。我们不会在此处重复完整的讨论，但有两点值得注意。第一，所选 MAC 的强度在位安全强度上，至少应与预期生成的共享密钥的强度相当。第二，正如你所预期的那样，MAC 密钥在使用后应立即丢弃，不应用于任何其他用途。

目前，只有 BCFIPS API 直接支持密钥确认。在 `org.bouncycastle.crypto.util` 中提供了一个 `ByteMacData` 类，以防你想遵循 NIST SP 800-56A 中使用的 MAC 数据构造。在使用密钥确认时，`KeyAgreement` 类返回一个 `AgreedKeyWithMacKey`，该对象提供了同时访问派生的共享密钥和 MAC 密钥的方法。

## 生成 AgreedKeyWithMacKey

BCFIPS API 通过扩展传递给 `KeyAgreement.generateSecret()` 的算法字符串中允许的语法，支持从 `KeyAgreement` 类返回两个密钥。基本语法遵循以下格式：

`macAlgorithm[macKeySizeInBits]/cipherAlgorithm[cipherKeySizeInBits]`

以下方法按照我们之前看过的的方法，生成一个 256 位的 AES 密钥。在这种情况下，`generateSecret()` 方法传递了一个内容为“HmacSHA512[256]/AES[256]”的字符串，因此该方法返回的不是简单的 `SecretKey`，而是返回一个 `AgreedKeyWithMacKey`，其中包含一个长度为 256 位的 SHA-512 HMAC 密钥。

```java
 1   /**
 2    * 使用 ECMQV 生成一个 256 位的约定 AES 密钥以及关联的 
 3    * 256 位 SHA-512 MAC 密钥。
 4    * 
 5    * @param aPriv A 方的私钥。
 6    * @param aPubEph A 方的临时公钥。
 7    * @param aPrivEph A 方的临时私钥。
 8    * @param bPub B 方的公钥。
 9    * @param bPubEph B 方的临时公钥。
10    * @return 包含两个密钥的 AgreedKeyWithMacKey。
11    */
12   public static AgreedKeyWithMacKey keyConfGenerateAESKey(
13      PrivateKey aPriv, PublicKey aPubEph, PrivateKey aPrivEph,
14      PublicKey bPub, PublicKey bPubEph, byte[] keyMaterial)
15      throws GeneralSecurityException
16   {
17       KeyAgreement agreement =
18           KeyAgreement.getInstance("ECMQVwithSHA256KDF", "BCFIPS");
19 
20       agreement.init(aPriv,
21           new MQVParameterSpec(aPubEph, aPrivEph, bPubEph, keyMaterial));
22 
23       agreement.doPhase(bPub, true);
24 
25       return (AgreedKeyWithMacKey)
26                   agreement.generateSecret("HmacSHA512[256]/AES[256]");
27   }
```

两个密钥的顺序反映了它们从派生密钥材料中提取的顺序。派生密钥材料的前 256 位被用作 HMAC 密钥源，接下来的 256 位派生密钥材料被用于 AES 密钥。

## 计算 MAC

一旦返回 `AgreedKeyWithMacKey`，我们应该在继续后续之前检查 MAC。在 FIPS 环境中，我们还应该在使用 MAC 密钥后立即将其擦除。MAC 密钥实现了 `ZeroizableSecretKey` 接口以实现这一点。

以下方法将验证为 SHA-512 HMAC 计算的 MAC，即我们在生成方法中指定的相同 MAC 算法。你可以看到第 19 行对 `zeroize()` 方法的调用。

```java
 1   /**
 2    * 为传入的 MAC 数据计算 MAC 标签值。
 3    * 注意：我们在返回标签值之前会将 MAC 密钥置零。
 4    * 
 5    * @param macKey 用于初始化 MAC 的密钥。
 6    * @param macData 用于计算 MAC 标签的数据。
 7    * @return MAC 标签值
 8    */
 9   public static byte[] calculateMAC(
10      ZeroizableSecretKey macKey, byte[] macData)
11      throws GeneralSecurityException
12   {
13      Mac mac = Mac.getInstance("HmacSHA512", "BCFIPS");
14 
15      mac.init(macKey);
16 
17      byte[] tag = mac.doFinal(macData);
18 
19      macKey.zeroize();
20 
21      return tag;
22   }
```

正如你所料，一旦 MAC 密钥被擦除，它就不再使用了。

## 整合

以下示例展示了使用 `ByteMacData` 类使用 `KeyAgreement` 和 MAC 方法。

```java
1 /**
2  * 显示使用 KeyAgreement 和临时
3  * 的密钥对示例。
4  */
5 public class KeyConfExample {
6     public static void main(String[] args)
7         throws Exception {
8         // 为 A 方和 B 方生成密钥对
9         byte[] keyMaterial = Strings.toByteArray("AES key");
10        // A 方。
11        AgreedKeyWithMacKey aKey = keyConfGenerateAESKey(
12             aPriv, aPubEph, aPrivEph,
13             bPub, bPubEph, keyMaterial);
14 
15        // B 方。
16        AgreedKeyWithMacKey bKey = keyConfGenerateAESKey(
17             bPriv, bPubEph, bPrivEph,
18             aPub, aPubEph, keyMaterial);
19        );
20 
21        // builder 设置
22        ByteMacData byteMacData = new ByteMacData.Builder(
23                ByteMacData.Type.BILATERALU, // 常量
24                Strings.toByteArray("Party A"), // A 方 ID
25                Strings.toByteArray("Party B"), // B 方 ID
26                aPubEph.getPublic().getEncoded(), // 临时数据 A
27                bPubEph.getPublic().getEncoded()) // 临时数据 B
28            .withText(Strings.toByteArray("hello, world!")) // 可选
29            .build();
30 
31        // 为 MAC 构建输入
32        byte[] aTag = calculateMAC(aKey.getMacKey(), byteMacData.getMacData());
33        byte[] bTag = calculateMAC(bKey.getMacKey(), byteMacData.getMacData());
34 
35        // 比较两个返回值。
36        System.err.println("keys equal: "
37            + Arrays.areEqual(aKey.getEncoded(), bKey.getEncoded()));
38        System.err.println("tags equal: "
39            + Arrays.areEqual(aTag, bTag));
40    }
41 }
```

构建器设置符合 NIST SP 800-56A 第 5.9.1 至 5.9.3 节的讨论。你也将那里找到诸如 `BILATERALU` 等常量的定义。从根本上说，常量被用作区分符，以帮助在不同情况计算 MAC 标签值时避免意外冲突。如果一切顺利，在示例结束时，你将获得相同的约定密钥和 MAC 标签值，并应该看到以下输出：

```
keys equal: true
tags equal: true
```

如果你尝试更改几个输入值，你会发现其实不需要费太大精力就能检测到协议协商中的失败或干扰。

## 总结

在本章中，我们研究了如何使用公钥加密来传输密钥、执行密钥协商以及交换密钥。这涵盖了算法选择的广泛范围，包括每种协议的 `Elliptic Curve`（椭圆曲线）、`Diffie-Hellman` 以及它们的派生变。本章还涵盖了许多协议的扩展，以提高它们的可靠性。

我们查看了使用如 `RSA-OAEP`、`ElGamal-OAEP` 和 `RSA-KEM` 等算法进行密钥封装和解封装的各种选项，并为每个算法提供了实例示例。

对于密钥协商和密钥交换，`Diffie-Hellman` 在 `NIST` 中非常重要，因此我们在本章中使用了这些算法演示了完整的示例。

最后，我们还查看了使用瞬态密钥（ephemeral keys）对密钥协商协议的一系列改进。本章涵盖了两种主要方法：`Unified Model`（统一模型）和 `MQV`。此外，`NIST SP 800-56A` 中定义的密钥确认协议为加强密钥协商机制提供了额外选项。

# 第 8 章：X.509 证书与属性证书

虽然公钥算法解决了与安全传输密钥或为人们提供验证其数字签名的机制相关的“数值”问题，但现实情况是，一组数字看起来看起来非常相似，因此需要一种方法将实体与特定的公钥关联起来。

将公钥与身份关联并断言该关联有效性的常用方法之一是使用 `X.509` [57] 证书结构。`X.509 Certificates` 用于将密钥与身份关联。该身份是证书的主体（subject）。另一个身份是证书的签名者，他也被视为认证颁发机构（CA），也称为证书颁发者，它也存储在证书中，以便（如果可能的话）追溯证书的来源。

在本章中，我们将研究公钥证书是如何创建的，以及在创建后如何将额外的属性与它们关联起来。在处理这个问题时，我们首先需要查看证书最初是如何与身份关联的。

## X.500 区分名称 (Distinguished Name)

证书身份的基本单位是 `X.500` 区分名称。`X.500` 中的主要 `ASN.1` 结构是 `Name`，我们将看到它被用于填充 `X.509` 证书中的身份字段，并提供在扩展和其他字段中表示身份的方法。

```
Name ::= CHOICE {
                RDNSequence }

RDNSequence ::= SEQUENCE OF RelativeDistinguishedName

RelativeDistinguishedName ::= SET SIZE (1..MAX) OF AttributeTypeAndValue

AttributeTypeAndValue ::= SEQUENCE {
                               type  OBJECT IDENTIFIER,
                               value ANY }
```

在 `Bouncy Castle` 中，`X.500` 名称由 `X500Name` 类表示，该类定义在 `org.bouncycastle.asn1.x500` 层次结构下。你可能会奇怪，为什么整个包层次结构要专门用于这样一个简单的结构。现实情况是，虽然结构简单，但它的用途和应用非常多样——以至于正如 Peter Gutmann 出色的《X.509 风格指南》[69] 所指出的，你甚至可以轻松包含一段显示某人玩猫的 MPEG 电影！

目前 `X500` 包层次结构由两个包组成：核心 `x500` 包和子包 `x500.style`。核心包包含 `X500Name` 类以及 `X500NameBuilder` 类，以及代表构成 `Name` 的 `SEQUENCE` 项的组件类：`RDN` 代表相对区分名称 (`RelativeDistinguishedName`)，`AttributeTypeAndValue` 代表属性类型和值 (`AttributeTypeAndValue`) 结构。`style` 包包含了模板类，提供了配置 `X500Name` 对象以符合不同标准的方法。当你发现自己正尝试符合某个区分名称的规范（profile for Distinguished Names），而 `BC` 类并不完全适用时，可以扩展样式类，或者复制并编辑这些类，以产生合适的内容。

`JCA` 依赖 `X500Principal` 来支持 `X.500` 名称结构。与 `BC` 的 `X500Name` 类不同，`X500Principal` 只能从字符串或字节编码创建——没有构建器类。因此，即使你限制自己使用 `X500Principal`，有时使用 `X500NameBuilder` 来构造名称，然后使用 `X500Name.getEncoded()` 从字节编码创建新的 `X500Principal` 可能会更好，如下所示：

```java
X500NameBuilder x500Bldr = new X500NameBuilder();

x500Bldr.addRDN(BCStyle.CN, "Example X.500 Name");

X500Principal x500Principal = new X500Principal(x500Bldr.build().getEncoded())
```

这特别适用于向单个 `RDN` 添加多个 `ATVs` 的情况。

你可以通过使用 `X500Name` 的 `getInstance()` 方法将 `X500Principal` 转换为 `X500Name`：

```java
X500Name x500Name = X500Name.getInstance(x500Principal.getEncoded())
```

在向单个 `RDN` 添加多个 `ATVs` 的情况下，尽量避免使用字符串表示，如果必须使用，请谨慎使用。`X500Name` 和 `X500Principal` 类都支持字符串的转换，但结果取决于这些类如何解释输入。我们现在来看其中的一些问题。

## X.500 遇到字符串

在使用 X500 名称时注意到的第一个问题是有多种方法生成其字符串表示。其中之一是使用 `ASN.1 OBJECT IDENTIFIER` (`OIDs`) 的简写来表示属性类型（例如，“CN”实际上是 OID “2.5.4.3”的简写）。第二个问题是构成 `Name` 的 `SEQUENCE` 实际上有两种排序方式，取决于使用哪种约定。第一种 ISO 约定按照顺序转换，因此字符串表示 RDN 的部分是第一个 RDN，依此类推。第二种 IETF 和 `RFC 4519` [92] 使用的约定通过反序转换，因此字符串表示 RDN 的部分实际上是序列中的最后一个 RDN。

如何选择？如今 IETF 排序可能是最常见的，尽管如此，如果你正在生成或处理字符串格式的 X500 名称，检查工作所在的规范是否选择了特定的排序可能会避免未来的尴尬。

在 `Bouncy Castle` 的情况下，默认排序是 ISO 排序。`JCA` 的 `X500Principal` 类遵循 IETF 排序。

Bouncy Castle 的 `X500Name` 类允许定义本地样式，因此，你可以使用以下方法指定使用 `RFC 4519` 中的方法将 `X500Name` 转换为字符串：

```java
   /**
   * 将 X500Name 转换为 IETF 样式。
   */
  public static X500Name toIETFName(X500Name name)
  {
      return X500Name.getInstance(RFC4519Style.INSTANCE, name);
  }
```



Bouncy Castle 的 `X500Name` 类默认使用这种方法。JCA 的 `X500Principal` 类会将待比较的名称转换为规范字符串表示，然后在内部进行比较。

## 公钥证书

与 X.500 一样，X.509 本身在提供功能方面非常慷慨，因此人们通常会采用特定的配置来创建和评估证书。对于互联网而言，最流行的是 RFC-5280 [101]。虽然不同的配置在解释方式可能有所不同，但格式始终是 X.509 中描述的。

## Certificate 和 TBSCertificate

在我们开始查看证书之前，快速查看涉及的 ASN.1 结构，以了解 API 底层到底发生了什么。虽然在这个世界上，很少东西能让开发者像面对 ASN.1 模块那样感到畏惧，但理解这些概念是值得的，因为如果你对“盒子内部”到底发生了什么有所了解，那么调试出错的情况就会变得容易得多。

下方的 ASN.1 片段提供了 X.509 证书的核心定义。如果你需要，可以在附录 A 的讨论中找到关于其含义的更多详细信息。

```
Certificate  ::=  SEQUENCE  {
     tbsCertificate       TBSCertificate,
     signatureAlgorithm   AlgorithmIdentifier,
     signature            BIT STRING  }

TBSCertificate  ::=  SEQUENCE  {
     version         [0]  Version DEFAULT v1,
     serialNumber         CertificateSerialNumber,
     signature            AlgorithmIdentifier,
     issuer               Name,
     validity             Validity,
     subject              Name,
     subjectPublicKeyInfo SubjectPublicKeyInfo,
     issuerUniqueID  [1]  IMPLICIT UniqueIdentifier OPTIONAL,
                          -- If present, version MUST be v2 or v3
     subjectUniqueID [2]  IMPLICIT UniqueIdentifier OPTIONAL,
                          -- If present, version MUST be v2 or v3
     extensions      [3]  Extensions OPTIONAL
                          -- If present, version MUST be v3 --  }

Version  ::=  INTEGER  {  v1(0), v2(1), v3(2)  }

CertificateSerialNumber  ::=  INTEGER

Validity ::= SEQUENCE {
     notBefore      Time,
     notAfter       Time  }

Time ::= CHOICE {
     utcTime        UTCTime,
     generalTime    GeneralizedTime }

UniqueIdentifier  ::=  BIT STRING

SubjectPublicKeyInfo  ::=  SEQUENCE  {
     algorithm            AlgorithmIdentifier,
     subjectPublicKey     BIT STRING  }

Extensions  ::=  SEQUENCE SIZE (1..MAX) OF Extension

Extension  ::=  SEQUENCE  {
     extnID      OBJECT IDENTIFIER,
     critical    BOOLEAN DEFAULT FALSE,
     extnValue   OCTET STRING
                 -- contains the DER encoding of an ASN.1 value
                 -- corresponding to the extension type identified
                 -- by extnID
     }
```

首先也是最重要的一点是 `TBSCertificate` 结构包含了证书的主体，包括公钥（编码在 `SubjectPublicKeyInfo` 中）。第二点是存储在 `Certificate` 中的签名是基于 `TBSCertificate` 的 DER 编码计算的（在此情况下，`TBS` 实际上代表“To Be Signed”，即待签名）。使用 DER（区分编码规则）在这里非常重要，这意味着在计算签名哈希值时，证书的评估结果始终保持一致。

第二个需要注意的是有效期，证书的颁发是为了在特定时期内有效。这一决定由 CA（颁发机构）做出，并反映了多种考虑，包括签名算法的强度、证书主体（`subject`）最初应该持有证书多长时间，以及公钥的强度以及它或其关联私钥可能的使用次数。

最后是版本。极少看到 `v2` 证书——`issuerUniqueID` 和 `subjectUniqueID` 是为了 `v2` 添加的，事实证明这也许是那些最好留在图纸上的主意之一。通常情况下你只会遇到 `v1` 和 `v3` 证书，如果你看到 `v1` 证书，它通常是自签名的并用信任锚点。版本 `v3` 的证书通常带有扩展，在日常使用中，我们最经常处理这类证书，例如验证文档或时间戳，或加密密钥。我们将在后面详细查看证书中常见的扩展。

如你所见，`TBSCertificate` 还包含了我们需要身份信息，既可以帮助我们识别颁发者主体（`subject`），以及序列号，以便我们判断该证书来自我们正在查看的颁发者。除了有用之外，这使得颁发者撤销证书成为可能，我们将在本章稍后讨论这一主题。

## 创建基础公钥证书

在我们查看生成证书之前，定义几个实用方法会很有用。其中一个提供合适的日期：

```java
  /**
   * 计算一个以秒为单位日期（适用于 PKIX 配置 - RFC 5280）
   *
   * @param hoursInFuture 现在之后的小时数，可以为负数。
   * @return 设置为现在 + (hoursInFuture * 60 * 60) 秒的 Date
   */
  public static Date calculateDate(int hoursInFuture)
  {
       long secs = System.currentTimeMillis() / 1000;

       return new Date((secs + (hoursInFuture * 60 * 60)) * 1000);
  }
```

另一个是为提供序列号：

```java
  private static long serialNumberBase = System.currentTimeMillis();

  /**
   * 使用单调递增的值计算序列号。
   *
   * @return 表示序列中下一个序列号的 BigInteger。
   */
  public static synchronized BigInteger calculateSerialNumber()
  {
      return BigInteger.valueOf(serialNumberBase++);
  }
```

你将看到 Bouncy Castle 的 API 会生成 `X509CertificateHolder` 类。这些类的优点是独立于提供者的，因为它们仅仅作为证书的载体。在我们查看如何构建基础证书之后，我们将查看如何将 `X509CertificateHolder` 转换为 Java 的 `X509Certificate` 对象之一。

以下示例显示了如何生成自签名的版本 1 证书。版本 1 证书仍然被广泛使用，但仅作为信任锚点，否则无法限制其用途。当我们查看带有扩展的证书时，将看到限制证书用途的示例。

```java
  /**
   * 构建一个示例自签名 V1 证书，作为信任锚点或
   * 根证书。
   *
   * @param keyPair 用于签名和提供公钥的密钥对。
   * @param sigAlg 用于签名证书的签名算法。
   * @return 包含 V1 证书的 X509CertificateHolder。
   */
  public static X509CertificateHolder createTrustAnchor(
          KeyPair keyPair, String sigAlg)
          throws OperatorCreationException
  {
      X500NameBuilder x500NameBld = new X500NameBuilder(BCStyle.INSTANCE)
              .addRDN(BCStyle.C, "AU")
              .addRDN(BCStyle.ST, "Victoria")
              .addRDN(BCStyle.L, "Melbourne")
              .addRDN(BCStyle.O, "The Legion of the Bouncy Castle")
              .addRDN(BCStyle.CN, "Demo Root Certificate");

      X500Name name = x500NameBld.build();

      X509v1CertificateBuilder certBldr = new JcaX509v1CertificateBuilder(
                                                  name,
                                                  calculateSerialNumber(),
                                                  calculateDate(0),
                                                  calculateDate(24 * 31),
                                                  name,
                                                  keyPair.getPublic());

      ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
                               .setProvider("BC").build(keyPair.getPrivate());

      return certBldr.build(signer);
  }
```

在第 14 到 19 行中，我们可以看到使用 `X500NameBuilder` 来创建一个 `X.500` 名称，以提供与证书关联的身份详细信息。证书的内容在第 23 到 29 行进行构建，并使用传入方法的私钥和签名算法名称创建一个签名者。

由于该证书是自签名的，因此证书体中的主体（subject）和颁发者（issuer）被设置为同一个名称。如果你收到了其中一个，你真的得听信出示者的话。

要调用该方法，我们只需要决定使用哪种公钥算法以及使用哪种签名算法来签署证书。在下面的代码段中，我们可以看到如何调用该方法创建一个使用 `ECDSA` 通过 `SHA-256` 签名的自签名证书。

```java
KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
KeyPair trustKp = kpGen.generateKeyPair();

X509CertificateHolder trustCert =
                          createTrustAnchor(trustKp, "SHA256withECDSA");
```

## 将 X509CertificateHolder 转换为 X509Certificate

提供了 `org.bouncycastle.cert.jcajce.JcaX509CertificateConverter` 类用于将 `X509CertificateHolder` 对象转换为普通的 JCA `X509Certificate` 对象。

`JcaX509CertificateConverter` 类可以根据 JVM 中当前的提供者优先级来生成证书，或者你可以指定一个特定的提供者。在示例中，我们通过使用其名称指定了 Bouncy Castle 提供者。

```java
X509CertificateHolder certHldr = ...

X509Certificate cert = new JcaX509CertificateConverter()
                                                   .setProvider("BC")
                                                   .getCertificate(certHldr);
```

要反向转换，只需将 `X509Certificate` 的编码传递给 `X509CertificateHolder`，或者将 `X509Certificate` 传递给 `JcaX509CertificateHolder`，它会为你完成编码步骤。

```java
X509Certificate cert = ...
X509CertificateHolder certHldr = new JcaX509CertificateHolder(cert);
```

正如我们接下来看到的，你也可以使用 `CertificateFactory` 类来转换 `X509CertificateHolder`。

## CertificateFactory 类

`java.security.cert` 包中的 `CertificateFactory` 类也可以用于将 `X509CertificateHolder` 或其他形式的 `X.509` 证书转换为 Java 的 `X509Certificate` 对象之一。我们将在下一章中看到该类的进一步用法，因为 `CertificateFactory` 也用于证书撤销列表 (`CRLs`)、以及证书路径的构建与验证。

`CertificateFactory` 类同样是基于提供者的，需要使用 `getInstance()` 方法来实例化。它有两个与生成公钥证书相关的方法：`generateCertificate()` 和 `generateCertificates()`。这些方法可以用于读取各种编码的证书（通常包括 `PEM` 和 `BER/DER`），然后生成单个证书（`generateCertificate()` 的情况）或证书集合（`generateCertificates()` 的情况）。

`X509CertificateHolder` 的 `getEncoded()` 方法会生成封装在类类中的 `X.509` 证书的 BER 编码。你可以使用该方法以如下方式为 `generateCertificate()` 提供输入：

```java
  /**
   * 使用 CertificateFactory 将 X509CertificateHolder 转换为 X509Certificate 的简单方法。
   */
  public static X509Certificate convertX509CertificateHolder(
                                      X509CertificateHolder certHolder)
          throws GeneralSecurityException, IOException {
      CertificateFactory cFact = CertificateFactory.getInstance("X.509", "BC");

      return (X509Certificate)cFact.generateCertificate(
                          new ByteArrayInputStream(certHolder.getEncoded()));
  }
```

## 创建带有扩展的 CA 证书

X.509 版本 3 主要创新是引入了证书扩展。在继续之前，最好先回顾一下扩展是如何使用 ASN.1 结构定义的。

```
Extension ::= SEQUENCE {
    extnID      OBJECT IDENTIFIER,
    critical    BOOLEAN DEFAULT FALSE,
    extnValue   OCTET STRING -- 包含对应 extnID 标识的扩展类型的 ASN.1 值的编码
}
```



OBJECT IDENTIFIER `extnID` 用于标识 `extnValue` 的内容，`critical` 用于指示 CA 是否认为此扩展重要到需要任何想要使用该证书的人都理解它，然后 `extnValue` 是一个 `OCTET STRING`，持有扩展值的实际 DER 编码。注意，由于 `critical` 的默认值为 `false`，如果它为 `false`，则在扩展结构进行 DER 编码时该值将不存在。

扩展提供了两个好处：它们允许添加关于证书主体的额外信息，例如它可能可能被认知的其他名称；它们还使得 CA 能够对证书的用途放置某些限制。在我们稍后查看证书请求（CertificationRequests）时，这是一个重要的点：虽然可以请求添加扩展，但证书中添加哪些扩展是由签名证书的 CA 决定的。

这也允许 CA 安全地创建其他 CA 来代表它们行动。不能用于 CA 的证书终止了从路径顶部信任锚点领先证书链（或证书路径）。终止链的证书被称为端实体证书（end-entity certificate）。端实体证书通常与特定服务、组织或个人的身份直接绑定。

当 `X509CertificateHolder` 以对象形式呈现扩展项时，如果你正在使用 JCA

对于 `X509Certificate`，要么有一个与该扩展相关的特定方法，要么你需要使用 `X509Certificate.getExtensionValue()` 来获取扩展值。请注意，返回的扩展值将是包含扩展值的 DER 编码 `OCTET STRING`，而不是扩展值本身。你可以使用以下方法解开扩展值，并获取代表该扩展值的内容字节：

```java
/**
 * 从 JCA X509Certificate 中提取扩展的 DER 编码值字节。
 *
 * @param cert 感兴趣的证书。
 * @param extensionOID 与感兴趣的扩展相关的 OID。
 * @return 扩展内部的 DER 编码，如果缺少扩展，则返回 null。
 */
public static byte[] extractExtensionValue(
        X509Certificate cert,
        ASN1ObjectIdentifier extensionOID)
{
    byte[] octString = cert.getExtensionValue(extensionOID.getId());

    if (octString == null)
    {
        return null;
    }

    return ASN1OctetString.getInstance(octString).getOctets();
}
```

其中 `extensionOID` 是与该扩展相关的 `OBJECT IDENTIFIER`。

考虑以下示例，它创建了一个可以用于签署其他证书的中间证书。该方法使用了 `JcaX509ExtensionUtils` 类并创建了多个扩展，以提供关于发行者的额外信息、证书公钥的通用标识符，以及签署该证书的 CA 期望该证书用途的细节。

```java
/**
 * 构建一个可以作为 CA 证书的示例 V3 中间证书。
 *
 * @param signerCert 带有公钥的证书，该公钥以后将用于验证此证书的签名。
 * @param signerKey 用于在证书中签名的私钥。
 * @param sigAlg 用于签名证书的签名算法。
 * @param certKey 要安装在证书中的公钥。
 * @param followingCACerts
 * @return 包含 V3 证书的 X509CertificateHolder。
 */
public static X509CertificateHolder createIntermediateCertificate(
        X509CertificateHolder signerCert, PrivateKey signerKey,
        String sigAlg, PublicKey certKey, int followingCACerts)
        throws CertIOException, GeneralSecurityException,
               OperatorCreationException
{
    X500NameBuilder x500NameBld = new X500NameBuilder(BCStyle.INSTANCE)
            .addRDN(BCStyle.C, "AU")
            .addRDN(BCStyle.ST, "Victoria")
            .addRDN(BCStyle.L, "Melbourne")
            .addRDN(BCStyle.O, "The Legion of the Bouncy Castle")
            .addRDN(BCStyle.CN, "Demo Intermediate Certificate");

    X500Name subject = x500NameBld.build();

    X509v3CertificateBuilder certBldr = new JcaX509v3CertificateBuilder(
            signerCert.getSubject(),
            calculateSerialNumber(),
            calculateDate(0),
            calculateDate(24 * 31),
            subject,
            certKey);

    JcaX509ExtensionUtils extUtils = new JcaX509ExtensionUtils();

    certBldr.addExtension(Extension.authorityKeyIdentifier,
            false, extUtils.createAuthorityKeyIdentifier(signerCert))
            .addExtension(Extension.subjectKeyIdentifier,
                    false, extUtils.createSubjectKeyIdentifier(certKey))
            .addExtension(Extension.basicConstraints,
                    true, new BasicConstraints(followingCACerts))
            .addExtension(Extension.keyUsage,
                    true, new KeyUsage(
                                            KeyUsage.digitalSignature
                                          | KeyUsage.keyCertSign
                                          | KeyUsage.cRLSign));

    ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
            .setProvider("BC").build(signerKey);

    return certBldr.build(signer);
}
```

给定信任锚点 `trustAnchorKey` 的 `PrivateKey` 及其关联证书 `trustCert`，我们可以调用上述方法创建一个如下单级 CA 证书：

```java
KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
KeyPair caKp = kpGen.generateKeyPair();

X509CertificateHolder caCert =
        createIntermediateCertificate(trustCert,
                trustAnchorKey,
                "SHA256withECDSA", caKp.getPublic(), 0);
```

注意调用时传递了 0 作为 `followingCACerts`。我们将在查看 `BasicConstraints` 时看到它的含义。

## 常见扩展

在了解了所添加的扩展后，值得花一点时间理解它们的实际含义。这里涵盖的扩展应仅作为指南，如果你需要解释它们，应该检查 RFC 5280 的相关章节。

### 基本约束 (Basic Constraints)

`basicConstraints` 扩展由常量 `Extension.basicConstraints` 标识，其 OID 值为 `2.5.29.19` (`id-ce-basicConstraints`)。它的 ASN.1 定义如下：

```asn
BasicConstraints ::= SEQUENCE {
    cA                BOOLEAN DEFAULT FALSE,
    pathLenConstraint INTEGER (0..MAX) OPTIONAL }
```

例如，如果 `BasicConstraints` 扩展中的 `cA` 为 `TRUE` 且 `pathLenConstraint` 为 `0`，那么从扩展的角度来看，该证书允许签署其他证书，但被签署的证书不能用于签署其他证书并延长链。

在第一个示例中，`BasicConstraints` 扩展通过以下行添加：

```java
.addExtension(Extension.basicConstraints,
             true, new BasicConstraints(followingCACerts))
```

由于以 `followingCACerts` 变量的形式提供了 `pathLenConstraint`，这告诉我们该证书是作为 CA 发行的，前提是后续不能超过 `followingCACerts` 个 CA，值为 0 意味着只有实体证书可以随其后。

使用 `X509CertificateHolder` 类恢复 `BasicConstraints` 时可以使用：

```java
BasicConstraints basicConstraints = BasicConstraints.fromExtensions(
                                                  certHldr.getExtensions());
```

来获取对象。

在 Java 的 `X509Certificate` 类中，提供了方法 `X509Certificate.getBasicConstraints()`，它返回一个 `int`。该 `int` 值代表 `pathLenConstraint`，除非 `cA` 为 `FALSE`，此时 `getBasicConstraints()` 返回 `-1`。

### 机构密钥标识 (Authority Key Identifier)

`authorityKeyIdentifier` 扩展由常量 `Extension.authorityKeyIdentifier` 标识，其 OID 值为 `2.5.29.35` (`id-ce-authorityKeyIdentifier`)。它的 ASN.1 定义如下：

```asn
AuthorityKeyIdentifier ::= SEQUENCE {
    keyIdentifier [0] KeyIdentifier OPTIONAL,
    authorityCertIssuer [1] GeneralNames OPTIONAL,
    authorityCertSerialNumber [2] CertificateSerialNumber OPTIONAL }

KeyIdentifier ::= OCTET STRING
```

此扩展的目的是识别用于验证证书签名的公钥，或者换句话说，是验证证书上的签名，该签名将证书上的公钥与证书的主体（subject）以及任何相关的扩展绑定在一起。因此，如果你愿意接受此扩展所识别的公钥具有权威性，那么你接受存储在证书中关联属性的公钥也是有效的，这是合逻辑的。另一方面，如果你无法理解此扩展或无法验证证书的签署者，那么接受证书中的任何内容更多是出于盲目信任，而不是基于对所用签名算法有效性的考量。

#### AuthorityKeyIdentifier（权威机构密钥标识符）

使用 `X509CertificateHolder` 类恢复 `AuthorityKeyIdentifier` 时，可以使用以下代码：

```java
AuthorityKeyIdentifier authorityKeyIdentifier = 
                AuthorityKeyIdentifier.fromExtensions(certHldr.getExtensions());
```

来获取该对象。

在 Java 的 `X509Certificate` 类中，没有直接以对象形式检索 `AuthorityKeyIdentifier` 方法。如果你想从这些内容创建一个 `AuthorityKeyIdentifier` 对象，可以利用我们之前定义的 `extractExtensionValue` 方法，如下所示：

```java
X509Certificate cert = ...

AuthorityKeyIdentifier authorityKeyIdentifier =
     AuthorityKeyIdentifier.getInstance(
                 extractExtensionValue(cert, Extension.authorityKeyIdentifier));
```

#### Subject Key Identifier（主体密钥标识符）

`subjectKeyIdentifier` 扩展由常量 `Extension.subjectKeyIdentifer` 标识，其 OID 值为“2.5.29.14” (id-ce-subjectKeyIdentifier)。它的 ASN.1 定义如下：

```asn
SubjectKeyIdentifier ::= KeyIdentifier
```

`subjectKeyIdentifier` 仅仅是一个字节串，用于为证书中包含的公钥提供标识符。例如，如果你正在寻找某个特定证书的颁发证书，且该证书的 `AuthorityKeyIdentifier` 设置了 `keyIdentifier` 字段，你预期会在颁发证书的 `SubjectKeyIdentifier` 扩展中找到存储在 `keyIdentifier` 中的值。RFC 5280 第 4.2.1.2 节提供了计算密钥标识符值的两种常用方法。

使用 `X509CertificateHolder` 类恢复 `SubjectKeyIdentifier` 时，可以使用以下代码：

```java
SubjectKeyIdentifier subjectKeyIdentifier = SubjectKeyIdentifier.fromExtensions(
                                                     certHldr.getExtensions());
```

来获取该对象。

在 Java 的 `X509Certificate` 类中，没有直接以对象形式检索 `SubjectKeyIdentifier` 方法。如果你想从这些内容创建一个 `SubjectKeyIdentifier` 对象，可以利用我们之前定义的 `extractExtensionValue` 方法，如下所示：

```java
X509Certificate cert = ...

SubjectKeyIdentifier subjectKeyIdentifier =
     SubjectKeyIdentifier.getInstance(
                 extractExtensionValue(cert, Extension.subjectKeyIdentifier));
```

#### Subject Alternative Name（主体备用名称）

`subjectAltName` 扩展由常量 `Extension.subjectAlternativeName` 标识，其 OID 值为“2.5.29.17” (id-ce-subjectAltName)。它的 ASN.1 定义如下：

```asn
SubjectAltName ::= GeneralNames

GeneralNames ::= SEQUENCE SIZE (1..MAX) OF GeneralName
```

`subjectAltName` 用于存储与证书关联的备用（或别名）主体名称。如果你想将电子邮件地址与证书关联，严格来说，这是放置它的最佳位置。

使用 `X509CertificateHolder` 类恢复 `subjectAltName` 扩展的 `GeneralNames` 对象，可以使用以下代码：

```java
GeneralNames subjectAltName = GeneralNames.fromExtensions(
                   certHldr.getExtensions(), Extension.subjectAlternativeName);
```

来获取该对象。



在 Java 的 `X509Certificate` 类中，提供了 `X509Certificate.getSubjectAlternativeNames()` 方法，它返回一个不可变的 `List` 对象集合，代表在该扩展中可以找到的各种对象。每个 `List` 有两个元素，第一个是与 `GeneralName` 关联的标签，第二个元素是 `GeneralName` 值的解释，无论是 `String` 还是 DER 编码的字节数组。取决于你计划如何处理这些内容，直接使用我们之前使用的 `extractExtensionValue()` 方法创建一个 `GeneralNames` 对象可能会更简单一些。

## Issuer Alternative Name（颁发者备用名称）

`issuerAltName` 扩展由常量 `Extension.issuerAlternativeName` 标识，其 OID 值为“2.5.29.18” (id-ce-issuerAltName)。它的 ASN.1 定义如下：

```
IssuerAltName ::= GeneralNames
```

与 `subjectAltName` 类似，`issuerAltName` 用于存储与证书颁发者关联的备用名称。与 `subjectAltName` 扩展不同，此扩展不能替代 `TBSCertificate` 结构中 `issuer` 字段的内容。使用 `X509CertificateHolder` 类恢复 `issuerAltName` 扩展的 `GeneralNames` 对象，可以使用以下代码：

```
GeneralNames issuerAltName = GeneralNames.fromExtensions(
                     certHldr.getExtensions(), Extension.issuerAlternativeName);
```

来获取该对象。

在 Java 的 `X509Certificate` 类中，此扩展的处理方式与 `SubjectAltName` 扩展相同，提供了 `X509Certificate.getIssuerAlternativeNames()` 方法，它返回一个不可变的 `List` 对象集合，描述扩展中找到的各种对象。对于 `SubjectAltName` 扩展，你可能发现直接将此扩展作为 `GeneralNames` 对象处理更好。

## Distribution Point（CRL 分布点）

CRL 分布扩展提供了获取 CRL 信息的方法。该扩展应该是非关键的，并由 OID 值“2.5.29.31” (id-ce-CRLDistributionPoints) 标识。

该扩展的语法在 RFC 5280 中描述如下：

```
id-ce-CRLDistributionPoints OBJECT IDENTIFIER ::= { id-ce 31 }

CRLDistributionPoints ::= SEQUENCE SIZE (1..MAX) OF DistributionPoint

DistributionPoint ::= SEQUENCE {
    distributionPoint       [0]     DistributionPointName OPTIONAL,
    reasons                 [1]     ReasonFlags OPTIONAL,
    cRLIssuer               [2]     GeneralNames OPTIONAL }

DistributionPointName ::= CHOICE {
    fullName                [0]     GeneralNames,
    nameRelativeToCRLIssuer [1]     RelativeDistinguishedName }

ReasonFlags ::= BIT STRING {
    unused                  (0),
    keyCompromise           (1),
    cACompromise            (2),
    affiliationChanged      (3),
    superseded              (4),
    cessationOfOperation    (5),
    certificateHold         (6),
    privilegeWithdrawn      (7),
    aACompromise            (8) }
```

`CRLDistributionPoints` 结构在 BC 库中由 `CRLDistPoint` 类表示。你可以使用以下代码从 `X509CertificateHolder` 恢复 CRL 分布扩展值：

```
CRLDistPoint crlDistPoints =
                    CRLDistPoint.getInstance(
                        certHldr.getExtensions().getExtension(
                            Extension.cRLDistributionPoints).getParsedValue());
```

如你所见，该扩展可以包含关于何时获取 CRL（证书吊销列表的信息，以及 CRL 将涵盖的原因。`RFC 5280` 中对该扩展有非常详尽的讨论，我们在此不再重复，但我们将指出以下一点：在盲目处理此扩展时需要格外谨慎——接受一个跳转到任意 URL 的指令并可能下载一个未知大小的巨型文件，这绝不是可以轻率对待的事情。对于任何面向互联网的业务，你确实希望以某种方式对此过程进行抽象，这样你就可以免受收到的所有证书可能并非善意的这一事实的影响。

## 密钥用法 (Key Usage)

`keyUsage` 扩展由常量 `Extension.keyUsage` 标识，其 OID 值为“2.5.29.15” (`id-ce-keyUsage`)。它的 ASN.1 定义如下：

```
KeyUsage ::= BIT STRING {
    digitalSignature      (0),
    nonRepudiation        (1),
    keyEncipherment       (2),
    dataEncipherment      (3),
    keyAgreement          (4),
    keyCertSign           (5),
    cRLSign               (6),
    encipherOnly          (7),
    decipherOnly          (8) }
```

`keyUsage` 扩展是限制证书中密钥用途最通用的方法。哪些位必须设置或不能设置，很大程度上取决于证书所使用的配置文件（profile）及其用途。例如，用于客户端本地 SSL 的证书可能只设置了 `digitalSignature` 位，因为证书中的公钥应仅用于签名验证操作。`RFC 5280` 第 `4.2.1.3` 节讨论了各种可能性，并对其他对 `keyUsage` 存有特定解释的 RFC 给出了一些线索。

要使用 `X509CertificateHolder` 类恢复 `KeyUsage`，你可以使用：

```
KeyUsage keyUsage = KeyUsage.fromExtensions(certHldr.getExtensions());
```

来获取该对象。

Java 的 `X509Certificate` 类为此扩展提供了特定的处理方法，即特定方法 `X509Certificate.getKeyUsage()`，该方法返回一个布尔数组，表示 `KeyUsage` 位字符串中的每一位。请注意，在这种情况下，布尔值的顺序反映了它们在 ASN.1 定义中的编号，而不是位在 `BIT STRING` 中设置的实际顺序。

## 扩展密钥用法 (Extended Key Usage)

`extKeyUsage` 扩展由常量 `Extension.extendedKeyUsage` 标识，其 OID 值为“2.5.29.37” (`id-ce-extKeyUsage`)。它的 ASN.1 定义如下：

```
ExtKeyUsageSyntax ::= SEQUENCE SIZE (1..MAX) OF KeyPurposeId
KeyPurposeId ::= OBJECT IDENTIFIER
```

如果存在此扩展，则该证书旨在仅用于其所列出的用途之一，除非在 `ExtKeyUsageSyntax` 序列中包含了特殊的 `KeyPurposeId` `anyExtendedKeyUsage`。在弧线 `id-kp` (“1.3.6.1.5.5.7.3”）上分配了一系列密钥用途 ID。

通常，此扩展与实体证书（end entity certificates）配合使用，以比密钥用法扩展允许更严格的方式将证书锁定在特定用途上。例如，用于验证时间戳的证书必须包含 `ExtendedKeyUsage` `id-kp-timeStamping`，其定义为：

```
 id-kp-timeStamping OBJECT IDENTIFIER ::= {iso(1)
                     identified-organization(3) dod(6)
                     internet(1) security(5) mechanisms(5) pkix(7)
                     kp (3) timestamping (8)}
```

表明该证书公钥只能用于验证时间戳。在这种情况下，`ExtendedKeyUsage` 扩展还应该被标记为关键的（critical），且 `ExtendedKeyUsage` 扩展的存在显然比仅在 `KeyUsage` 扩展中设置 `digitalSignature` 位具有更强的约束。

要使用 `X509CertificateHolder` 类恢复 `ExtendedKeyUsage`，你可以使用：

```
ExtendedKeyUsage extKeyUsage = ExtendedKeyUsage.fromExtensions(
                                                     certHldr.getExtensions());
```

在 Java `X509Certificate` 类中，此扩展也由特定方法 `X509Certificate.getExtendedKeyUsage()` 表示，该方法返回一个字符串列表，表示扩展中已设置的 OBJECT IDENTIFIER 值。

另请注意，如果你需要使用 `anyExtendedKeyUsage`（例如，因为你正在开发的应用程序需要它），则该扩展不应被标记为关键。

## 创建实体证书 (Creating End-Entity Certificates)

正如我们之前提到的，实体证书代表证书链的末端。如果你想要一个关联到特定用户或特定用户活动的证书，通常将是一个与他们关联的实体证书。

下面的示例创建了一个授权用于验证数字签名的实体证书。请注意，示例包含一个 `BasicConstraints` 扩展，但这次扩展的值不是带路径长度的创建的，而是带有布尔值 `false`。

```
 /**
   * 创建一个用于验证数字签名的通用实体证书。
   * 
   * @param signerCert 带有公钥的证书，该公钥稍后将用于
   *                   验证此证书的签名。
   * @param signerKey 用于生成签名的私钥
   * @param sigAlg 用于签名证书的签名算法。
   * @param certKey 安装在证书中的公钥。
   * @return 包含 V3 的 X509CertificateHolder。
   */
  public static X509CertificateHolder createEndEntity(
          X509CertificateHolder signerCert, PrivateKey signerKey,
          String sigAlg, PublicKey certKey)
          throws CertIOException, GeneralSecurityException,
                 OperatorCreationException
  {
      X500NameBuilder x500NameBld = new X500NameBuilder(BCStyle.INSTANCE)
              .addRDN(BCStyle.C, "AU")
              .addRDN(BCStyle.ST, "Victoria")
              .addRDN(BCStyle.L, "Melbourne")
              .addRDN(BCStyle.O, "The Legion of Bouncy Castle")
              .addRDN(BCStyle.CN, "Demo End-Entity Certificate");

      X500Name subject = x500NameBld.build();

      X509v3CertificateBuilder   certBldr = new JcaX509v3CertificateBuilder(
              signerCert.getSubject(),
              calculateSerialNumber(),
              calculateDate(0),
              calculateDate(24 * 31),
              subject,
              certKey);

      JcaX509ExtensionUtils extUtils = new JcaX509ExtensionUtils();

      certBldr.addExtension(Extension.authorityKeyIdentifier,
              false, extUtils.createAuthorityKeyIdentifier(signerCert))
              .addExtension(Extension.subjectKeyIdentifier,
              false, extUtils.createSubjectKeyIdentifier(certKey))
              .addExtension(Extension.basicConstraints,
                      true, new BasicConstraints(false))
              .addExtension(Extension.keyUsage,
                      true, new KeyUsage(KeyUsage.digitalSignature));

      ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
                                     .setProvider("BC").build(signerKey);

      return certBldr.build(signer);
  }
```

请注意，在这种情况下 `BasicConstraints` 的构造函数只是传递了布尔值 `false`。这是为了指示该证书不能作为 CA 证书，尽管它可能用于验证签名。如果我们收到由上述示例所示配置的证书签名的证书，我们应该直接拒绝它，因为很明显签名证书在创建时从未打算让证书路径变得更长。

### 使用扩展密钥用法 (Using ExtendedKeyUsage)

在第二个示例中，我们正在创建一个包含 `ExtendedKeyUsage` 扩展的实体实体证书。正如我们之前从 ASN.1 定义中看到的，`ExtendedKeyUsage` 被定义为一个或多个 `KeyPurposeIds`，其中 `KeyPurposeId` 是一个 `OBJECT IDENTIFIER`（对象标识符）。`RFC 5280` 目前为 `KeyPurposeId` 如下定义：



## OID 定义

```
anyExtendedKeyUsage OBJECT IDENTIFIER ::= { id-ce-extKeyUsage 0 }

id-pkix  OBJECT IDENTIFIER  ::=
           { iso(1) identified-organization(3) dod(6) internet(1)
                   security(5) mechanisms(5) pkix(7) }

id-kp OBJECT IDENTIFIER ::= { id-pkix 3 }

id-kp-serverAuth             OBJECT IDENTIFIER ::= { id-kp 1 }

id-kp-clientAuth             OBJECT IDENTIFIER ::= { id-kp 2 }

id-kp-codeSigning            OBJECT IDENTIFIER ::= { id-kp 3 }

id-kp-emailProtection        OBJECT IDENTIFIER ::= { id-kp 4 }

id-kp-timeStamping           OBJECT IDENTIFIER ::= { id-kp 8 }

id-kp-OCSPSigning            OBJECT IDENTIFIER ::= { id-kp 9 }
```

你也会发现 `RFC 5280` 之外也存在 `KeyPurposeIds`，甚至可能会在你正在处理的应用程序中发现具有特定含义的私有定义。

## 创建包含 ExtendedKeyUsage 扩展的实体证书

以下示例创建了一个包含 `ExtendedKeyUsage` 扩展的实体证书。

```
 1   /**
 2    * 创建一个特殊用途的实体证书，该证书与特定的
 3    * 密钥用途相关。
 4    * 
 5    * @param signerCert 带有公钥的证书，该公钥稍将用于
 6                        验证此证书的签名。
 7    * @param signerKey 用于生成证书签名的私钥。
 8    *                  certificate。
 9    * @param sigAlg 用于签名证书的签名算法。
10    * @param certKey 要安装在证书中的公钥。
11    * @param keyPurpose 与此证书公钥关联的特定 KeyPurposeId。
12    *                   certificate.
13    * @return 一个包含 V3 证书的 X509CertificateHolder。
14    */
15   public static X509CertificateHolder createSpecialPurposeEndEntity(
16           X509CertificateHolder signerCert, PrivateKey signerKey,
17           String sigAlg, PublicKey certKey, KeyPurposeId keyPurpose)
18           throws OperatorCreationException, CertIOException,
19                  GeneralSecurityException
20   {
21       X500NameBuilder x500NameBld = new X500NameBuilder(BCStyle.INSTANCE)
22               .addRDN(BCStyle.C, "AU")
23               .addRDN(BCStyle.ST, "Victoria")
24               .addRDN(BCStyle.L, "Melbourne")
25               .addRDN(BCStyle.O, "The Legion of the Bouncy Castle")
26               .addRDN(BCStyle.CN, "Demo End-Entity Certificate");
26 
28       X500Name subject = x500NameBld.build();
29 
30       X509v3CertificateBuilder   certBldr = new JcaX509v3CertificateBuilder(
31               signerCert.getSubject(),
32               calculateSerialNumber(),
33               calculateDate(0),
34               calculateDate(24 * 31),
35               subject,
36               certKey);
37 
38       JcaX509ExtensionUtils extUtils = new JcaX509ExtensionUtils();
39 
40       certBldr.addExtension(Extension.authorityKeyIdentifier,
41               false, extUtils.createAuthorityKeyIdentifier(signerCert))
42               .addExtension(Extension.subjectKeyIdentifier,
43                       false, extUtils.createSubjectKeyIdentifier(certKey))
44               .addExtension(Extension.basicConstraints,
45                       true, new BasicConstraints(false))
46               .addExtension(Extension.extendedKeyUsage,
47                             true, new ExtendedKeyUsage(keyPurpose));
48 
49       ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
50                                      .setProvider("BC").build(signerKey);
51 
52       return certBldr.build(signer);
53   }
```

如我们所示，该证书通过提供的 `BasicConstraints` 扩展被定义为实体证书，并且包含了 `ExtendedKeyUsage` 扩展。

给定 CA 的私钥 `caPrivKey` 及其关联证书 `caCert`，我们可以如下调用上述方法创建一个专门用于签名时间戳的证书：

```
1       KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
2       KeyPair specEEKp = kpGen.generateKeyPair();
3 

4       X509CertificateHolder specEECert =
5               createSpecialPurposeEndEntity(caCert, caPrivKey,
6                                              "SHA256withECDSA",
7                                              specEEKp.getPublic(),
8                                              KeyPurposeId.id_kp_timeStamping);
```

注意，示例中将 `ExtendedKeyUsage` 扩展的关键性（critical）设置了 `true`。如果上面的代码片段使用 `KeyPurposeId.anyExtendedKeyUsage` 作为密钥用途，则该值需要设置为 `false`。

## 属性证书

X509 属性证书最常见的配置描述在 `RFC 5755` 中。它们与我们之前看到的证书的区别在于它们没有附加公钥。相反，它们允许将组组成、角色、安全许可等属性与实体（可能是公钥证书）关联。在这里，可以将属性证书比作签证，而将原始公钥证书比作护照。

属性证书的这种特性使其非常有用，与其每个人都有自己的 CA 来发行 X509 证书，各个小组可以发布与现有身份关联的属性证书。此外，授予某人短期访问权限是可能的，访问过期时不会影响公钥证书。

### 属性证书结构

属性证书的结构如下：

```
AttributeCertificate ::= SEQUENCE {
  acinfo               AttributeCertificateInfo,
  signatureAlgorithm   AlgorithmIdentifier,
  signatureValue       BIT STRING
}

AttributeCertificateInfo ::= SEQUENCE {
  version                 AttCertVersion, -- version is v2
  holder                  Holder,
  issuer                  AttCertIssuer,
  signature               AlgorithmIdentifier,
  serialNumber            CertificateSerialNumber,
  attrCertValidityPeriod  AttCertValidityPeriod,
  attributes              SEQUENCE OF Attribute,
  issuerUniqueID          UniqueIdentifier OPTIONAL,
  extensions              Extensions OPTIONAL
}

AttCertVersion ::= INTEGER { v2(1) }

AttCertValidityPeriod  ::= SEQUENCE {
  notBeforeTime  GeneralizedTime,
  notAfterTime   GeneralizedTime
}
```

### Holder 结构

通过查看其在 `RFC 5755` 中的定义，你可以看到 `Holder` 结构允许使用公钥证书以外的内容。

```
Holder ::= SEQUENCE {
  baseCertificateID   [0] IssuerSerial OPTIONAL,
      -- 持有公钥证书的
      -- 发布者和序列号
  entityName          [1] GeneralNames OPTIONAL,
      -- 申请者的名称或角色
  objectDigestInfo    [2] ObjectDigestInfo OPTIONAL
      -- 用于直接验证持有者，
      -- 例如，一个可执行文件
}

ObjectDigestInfo ::= SEQUENCE {
  digestedObjectType  ENUMERATED {
    publicKey            (0),
    publicKeyCert        (1),
    otherObjectTypes     (2) },
  -- otherObjectTypes 不得
  -- 在此配置中未使用
  otherObjectTypeID   OBJECT IDENTIFIER OPTIONAL,
  digestAlgorithm     AlgorithmIdentifier,
  objectDigest        BIT STRING
}
```

值得注意的是，标准允许定义三种匹配持有者的方法，你可以从 `ObjectDigestInfo` 结构可以看出，它既可以用于公钥证书，也可以用于其他对象。最初，预计该结构会为 `Holder` 结构的解释器提供额外的灵活性，但事实证明这种灵活性也为歧义创造了机会。为了消除混淆风险，RFC 5755 规定 `Holder` 序列中**只能存在一个** 选项。

### AttCertIssuer 结构

`AttCertIssuer` 结构在设计时也考虑了灵活性。查看 RFC 5755 提供的定义也可以发现，与 `Holder` 一样，出于该 RFC 的目的，在结构中填充定义良好的字段子集会更好。

```
AttCertIssuer ::= CHOICE {
  v1Form   GeneralNames,  -- 不得在此配置
                          -- 中中使用
  v2Form   [0] V2Form     -- 仅限 v2
}

V2Form ::= SEQUENCE {
  issuerName            GeneralNames  OPTIONAL,
  baseCertificateID     [0] IssuerSerial  OPTIONAL,
  objectDigestInfo      [1] ObjectDigestInfo  OPTIONAL
    -- issuerName 必须在此配置中出现
    -- baseCertificateID 和 objectDigestInfo 不得
    -- 在此配置中出现
}

IssuerSerial  ::=  SEQUENCE {
  issuer         GeneralNames,
  serial         CertificateSerialNumber,
  issuerUID      UniqueIdentifier OPTIONAL
}
```

由于 `UniqueIdentifier` 在 RFC 5280 提供的 X.509 配置中已弃用，你不太会在 `IssuerSerial` 结构中看到填充该值。

### Attribute 结构

我们将查看属性证书结构中的最后一个元素：`Attribute` 结构，它构成了证书所携带的属性序列。

```
Attribute ::= SEQUENCE {
  type      AttributeType,
  values    SET OF AttributeValue
    -- 至少需要一个值
}

AttributeType ::= OBJECT IDENTIFIER

AttributeValue ::= ANY DEFINED BY AttributeType
```

如你所示，Attribute 结构在它可以包含的内容方面非常通用。

## 构建属性证书

以下示例展示了如何使用 RFC 5755 中定义的 `RoleSyntax` 构建一个简单的属性证书，该证书仅包含一个用户角色的 URI。

```
 1   public static X509AttributeCertificateHolder createAttributeCertificate(
 2           X509CertificateHolder issuerCert, PrivateKey issuerKey, String sigAlg,
 3           X509CertificateHolder holderCert, String holderRoleUri)
 4           throws OperatorCreationException
 5   {
 6       X509v2AttributeCertificateBuilder acBldr =
 7               new X509v2AttributeCertificateBuilder(
 8                     new AttributeCertificateHolder(holderCert),
 9                     new AttCertIssuer(issuerCert.getSubject()),
10                     calculateSerialNumber(),
11                     calculateDate(0),
12                     calculateDate(24 * 7));
13 
14       GeneralName roleName = new GeneralName(
 15                        GeneralName.uniformResourceIdentifier, holderRoleUri);
16 
17       acBldr.addAttribute(
 18                X509AttributeIdentifiers.id_at_role, new RoleSyntax(roleName));
19 
20       ContentSigner signer = new JcaContentSigner(sigAlg)
21               setProvider("BC").build(issuerKey);
 22       
23       return acBldr.build();
24   }
```

构建器的模式与证书类似，唯一的区别在于证书要携带的属性的构建和分配。在实践中，属性甚至可能包含私有的 OID 以及私有的 ASN.1 结构。

调用示例方法如下：



```
X509AttributeCertificateHolder attrCert =
    createAttributeCertificate(issuerCert,
        issuerKey,
        "SHA256withECDSA", holderCert, "id://DAU123456789");
```

我们只需要确保签名算法适用于密钥以及我们尝试构建的属性证书。

### 总结

在本章中，我们查看了安全和认证通信的基础构建块之一：X.509 证书。

我们介绍了如何使用 X.509 结构附加公钥和身份，以及如何创建证书链。

最后，本章考虑了如何将属性证书与现有公钥证书结合。

## 第章：证书吊销与路径

有时发布者需要撤回对证书的签名。这一过程称为证书吊销，既有静态也有在线的方法支持此。

此外，持有证书的方可能会将其用于不应使用的地方。为了防止这种情况，已经有了标准的算法来进行证书验证。这些算法可以检查用于签发实体证书的所有证书的来源，并确认实体证书“符合用途”。

我们将首先查看“改变主意”的过程。

### 证书吊销列表 (CRLs)

在理想的世界中，证书一旦签发，将一直有效到过期日期。然而，情况并非总是如此，因此存在一种机制用于确定发布者是否改变了对特定证书有效性的判断。

证书吊销列表，简称 `CRLs`，是最初提出的解决方案，用于证书发布者能够让用户了解已发布证书的状态。与证书一样，CRL 的定义在 RFC 5280 中，顶层结构 `CertificateList` 定义如下：

```
CertificateList  ::=  SEQUENCE  {
      tbsCertList          TBSCertList,
      signatureAlgorithm   AlgorithmIdentifier,
      signatureValue       BIT STRING  }

 TBSCertList  ::=  SEQUENCE  {
      version                 Version OPTIONAL,
                                   -- 如果存在，必须为 v2
      signatureAlgorithm               AlgorithmIdentifier,
      issuer                  Name,
      thisUpdate              Time,
      nextUpdate              Time OPTIONAL,
      revokedCertificates     SEQUENCE OF SEQUENCE  {
           userCertificate         CertificateSerialNumber,
           revocationDate          Time,
           crlEntryExtensions      Extensions OPTIONAL
                                    -- 如果存在，必须为 v2
                                }  OPTIONAL,
      crlExtensions           [0]  EXPLICIT Extensions OPTIONAL
                                    -- 如果存在，必须为 v2
                                }
```

从结构上可以看出，其意图是 CRL 的权威性源于签署它们的人。它包含了一些颁发者详情、一个撤销列表、关于 CRL 发行时间的详细信息（`thisUpdate`）、可能需要请求更新的时间（`nextUpdate`）以及一些扩展。

### 常见 CRL 扩展

与证书一样，CRL 也可以具有扩展，用于传递有关如何解释 CRL 的额外信息。接下来的列表并不是详尽的，仅应作为指南。如果你需要深入理解这些扩展，最好确保你已经阅读了 RFC 5280 的相关章节 [101]。

### 权威密钥标识符 (Authority Key Identifier)

权威密钥标识符扩展提供了一种识别用于验证 CRL 签名的公钥的方法。符合 RFC 5280 [101] 的 CRL 颁发者 get 包含权威密钥标识符扩展。

该扩展的语法与证书对应的扩展相同。

### 颁发者别名 (Issuer Alternative Name)

颁发者别名扩展是一个非关键扩展，允许将额外的身份与 CRL 关联。该扩展的语法与证书对应的扩展相同。

### CRL 号 (CRL Number)

CRL 号也是非关键的，用于提供一个指示此 CRL 是否取代了另一个 CRL 的唯一标识符。符合 RFC 5280 [101] 的 CRL 颁发者被要求包含 CRL 号扩展。

CRL 号扩展由常量 `Extension.basicConstraints` 标识，其 OID 值为“2.5.29.20”，并由单个整数组成。实际定义看起来如下：

```
id-ce-cRLNumber OBJECT IDENTIFIER ::= { id-ce 20 }

CRLNumber ::= INTEGER (0..MAX)
```

合规的 CRL 颁发者应该在每次发布新 CRL 时增加 `CRLNumber` 的值，这样编号更高的 CRL 总是代表 CRL 更新的修订版本。需要注意的是，当 CRL 是增量 CRL（delta CRL）时，`CRLNumber` 值必须与其所对应的 CRL 共享相同的编号序列。

### 增量 CRL 指示器 (Delta CRL Indicator)

增量 CRL 指示器显示该 CRL 应被视为较早 CRL 的更改列表，其理念是：如果将增量 CRL 和早的完整 CRL 结合，结果将代表在增量 CRL 发行时应有的完整 CRL。

增量 CRL 指示器的 OID 值为“2.5.29.27”，该扩展具有以下语法：

```
id-ce-deltaCRLIndicator OBJECT IDENTIFIER ::= { id-ce 27 }

BaseCRLNumber ::= CRLNumber
```

其中 `BaseCRLNumber` 是增量 CRL 所显示更改的那个较早完整 CRL 的 CRL 号。

增量 CRL 指示器应被标记为关键扩展。

### 常见 CRL 条目扩展

从 `TBSCertList` 的定义中可以看出，`revokedCertificates` 字段也留有可选扩展的空间。RFC 5280 目前为 CRL 条目定义了三个扩展。需要注意的是，在 RFC 5280 之前也存在 `HoldInstructionCode`（OID 值为“2.5.29.23”），但它已被移除。

### CRL 撤销原因 (CRLReason)

`CRLReason` 扩展的 OID 值为“2.5.29.21”，该扩展具有以下语法：

```
id-ce-cRLReasons OBJECT IDENTIFIER ::= { id-ce 21 }

-- reasonCode ::= { CRLReason }

CRLReason ::= ENUMERATED {
    unspecified             (0),
    keyCompromise           (1),
    cACompromise            (2),
    affiliationChanged      (3),
    superseded              (4),
    cessationOfOperation    (5),
    certificateHold         (6),
         -- value 7 is not used
    removeFromCRL           (8),
    privilegeWithdrawn      (9),
    aACompromise           (10) }
```

如名称所示，`CRLReason` 扩展指示证书最初进入 CRL 的原因。如果不存在 `CRLReason` 扩展，你应该假设原因代码为 0，即 `unspecified`。RFC 5280 还规定，如果原因是 `unspecified`，则不应包含该扩展，只有在需要指示其他原因时才使用它。

### 无效日期 (InvalidityDate)

`InvalidityDate` 扩展用于提供一个确切日期，已知或怀疑证书在该日期变为无效。该扩展使得当实际失效时间早于撤销日期时，不再需要回溯填写 CRL 条目日期。RFC 5280 建议在任何此类信息可用的情况下都包含此扩展。

`InvalidityDate` 扩展的 OID 值为“2.5.29.24”，该扩展具有以下语法：

```
id-ce-invalidityDate OBJECT IDENTIFIER ::= { id-ce 24 }

InvalidityDate ::=  GeneralizedTime
```

关于 `GeneralizedTime` 如何构建的细节可以在附录 A：“ASN.1 and Bouncy Castle”。

### 证书颁发者 (CertificateIssuer)

`CertificateIssuer` 扩展用于指示证书的真实颁发者是谁。不过，当你发现它时，情况有点不同。RFC 5280 第 5.3.3 节规定，当不存在此扩展时，证书颁发者默认为之前的颁发者。换句话说，一旦出现 `CertificateIssuer`，每个 CRL 条目都应被认为与新的颁发者关联。

`CertificateIssuer` 扩展的 OID 值为“2.5.29.29”，该扩展具有以下语法：

```
id-ce-certificateIssuer OBJECT IDENTIFIER ::= { id-ce 29 }

CertificateIssuer ::=     GeneralNames
```

考虑到解释 CRL 的影响，RFC 5280 规定在使用时必须标记为关键。

## 创建新 CRL

以下代码创建一个包含单个撤销的 CRL。

```
/**

创建一个包含单个撤销的 CRL。

   * @param caKey 签署 CRL 的私钥。

   * @param sigAlg 用于签署 CRL 的签名算法。

   * @param caCert 与签署 CRL 的密钥相关的证书。

   * @param certToRevoke 要撤销的证书。

   * @return 代表 CA 撤销列表的 X509CRLHolder。

   */

   public X509CRLHolder createCRL(

           PrivateKey caKey,

           String sigAlg,

           X509CertificateHolder caCert,

           X509CertificateHolder certToRevoke)

           throws IOException, GeneralSecurityException, OperatorCreationException

   {

       X509v2CRLBuilder crlGen = new X509v2CRLBuilder(caCert.getSubject(),

                                           new Date(0));

       crlGen.setNextUpdate(calculateDate(24 * 7));

       // 添加撤销

       ExtensionsGenerator extGen = new ExtensionsGenerator();

       CRLReason crlReason = CRLReason.lookup(CRLReason.privilegeWithdrawn);

       extGen.addExtension(Extension.reasonCode, false, crlReason);

       crlGen.addCRLEntry(certToRevoke.getSerialNumber(),

                                           new Date(), extGen.generate());

       // 为 CRL 添加扩展

       JcaX509ExtensionUtils extUtils = new JcaX509ExtensionUtils();

       crlGen.addExtension(Extension.authorityKeyIdentifier, false,

               extUtils.createAuthorityKeyIdentifier(caCert));

       ContentSigner signer = new JcaContentSignerBuilder(sigAlg)

                                   .setProvider("BC").build(caKey);

       return crlGen.build(signer);

   }
```

我们的第一步是为 CRL 创建构建器，即 `X509v2CRLBuilder` 类，在这种情况下调用了 `setNextUpdate()` 方法。

### 将 X509CRLHolder 转换为 X509CRL

`org.bouncycastle.cert.jcajce.JcaX509CRLConverter` 类用于将 `X509CRLHolder` 对象转换为标准的 JCA `X509CRL` 对象。`JcaX509CRLConverter` 类可以根据 JVM 中当前的提供者优先级生成 `X509CRL`，你也可以指定特定的提供者。在示例中，我们通过名称指定了 Bouncy Castle 提供者。

```
X509CRLHolder crlHldr = ...

X509CRL crl = new JcaX509CRLConverter()
                                      .setProvider("BC")
                                      .getCRL(crlHldr);
```

若要反转换，只需将 `X509CRL` 的编码传递给 `X509CRLHolder`，或者将 `X509CRL` 传递给 `JcaX509CRLHolder`，后者将为你完成编码步骤。

```
X509CRL crl = ...

X509CRLHolder crlHldr = new JcaX509CRLHolder(crl);
```

`CertificateFactory` 类有两个与生成公钥证书相关的方法：`generateCRL()` 和 `generateCRLs()`。这些方法可以用于读取各种编码的证书（通常包括 PEM 和 BER/DER），然后生成单个证书（在 `generateCRL()` 情况下）或证书集合（在 `generateCRLs()` 情况下）。

`X509CertificateHolder` 的 `getEncoded()` 方法生成封装在该类中的 X.509 证书的 BER 编码。你可以如下方式使用该方法为 `CertificateFactory` 的 `generateCertificate()` 方法提供输入：

```
 1   /**

 2    * 使用 java.security.cert.CertificateFactory 类将 X509CRLHolder 转换为 X509CRL 的简单方法。

 4    */

 5   public static X509CRL convertX509CRLHolder(

 6                                            X509CertificateHolder crlHolder)

 7           throws GeneralSecurityException, IOException

 8   {

 9       CertificateFactory cFact = CertificateFactory.getInstance("X.509", "BC");

10 

11       return (X509CRL)cFact.generateCRL(

12                                          new ByteArrayInputStream(

13                                                  crlHolder.getEncoded()));

14   }
```

### 创建更新的 CRL

你可能已经意识到，CRL 会随着时间的推移而变得越来越。如果没有 API 的帮助，创建一个更新的 CRL 可能会非常痛苦下面的示例展示了如何获取现有的 CRL 并对其进行更新。

```
 1   /**

 2    * 从之前的 CRL 创建更新的 CRL 并添加新的撤销项。

 3    *

 4    * @param caKey 签名 CRL 的私钥。

 5    * @param sigAlg 用于签名 CRL 的签名算法。

 6    * @param caCert 与用于签名 CRL 的密钥相关的证书。

 7    * @param previousCaCRL 此 CA 之前的 CRL。

 8    * @param certToRevoke 要撤销的证书。
```



```java
9    * @return 表示该 CA 更新后撤销列表的 X509CRLHolder。
11    */
12   public X509CRLHolder updateCRL(
13           PrivateKey caKey,
14           String sigAlg,
15           X509CertificateHolder caCert,
16           X509CRLHolder previousCaCRL,
17           X509CertificateHolder certToRevoke)
18           throws IOException, GeneralSecurityException, OperatorCreationException
19   {
20       X509v2CRLBuilder crlGen = new X509v2CRLBuilder(caCert.getIssuer(),
21               calculateDate(0));
22 
23       crlGen.setNextUpdate(calculateDate(24 * 7));
24 
25       // 添加新的撤销项
26       ExtensionsGenerator extGen = new ExtensionsGenerator();
27 
28       CRLReason crlReason = CRLReason.lookup(CRLReason.privilegeWithdrawn);
29 
30       extGen.addExtension(Extension.reasonCode, false, crlReason);
31 
32       crlGen.addCRLEntry(certToRevoke.getSerialNumber(),
33            new Date(), extGen.generate());
34 
35       // 添加之前的撤销项
36       crlGen.addCRL(previousCaCRL);
37 
38       // 将扩展项添加到 CRL
39       JcaX509ExtensionUtils extUtils = new JcaX509ExtensionUtils();
40 
41       crlGen.addExtension(Extension.authorityKeyIdentifier, false,
42               extUtils.createAuthorityKeyIdentifier(caCert));
43 
44       ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
45                                   .setProvider("BC").build(caKey);
46 
47       return crlGen.build(signer);
48   }
```

你可以看到这与从头创建 CRL 非常相似，唯一的区别是这一行代码：

```java
crlGen.addCRL(previousCaCRL);
```

### 请求结构

```
Request ::=     SEQUENCE {
    reqCert                    CertID,
    singleRequestExtensions    [0] EXPLICIT Extensions
                                       { {re-ocsp-service-locator,
                                              ...}} OPTIONAL }

CertID ::= SEQUENCE {
    hashAlgorithm            AlgorithmIdentifier
                                 {DIGEST-ALGORITHM, {...}},
    issuerNameHash     OCTET STRING, -- Hash of issuer's DN
    issuerKeyHash      OCTET STRING, -- Hash of issuer's public key
    serialNumber       CertificateSerialNumber }
```

BC API 使用 `Req` 类来表示 `Request` 序列，并使用 `CertificateID` 来表示 `CertID`。`Req` 类正如你预期的那样工作，尽管你通常不会直接创建它，因为你会使用 `OCSPReqBuilder` 来构建一个完整的请求对象，而构建器会为你完成创建工作。

另一方面，`CertificateID` 需要一些操作，因为它需要能够计算哈希值。SHA-1 仍被广泛用于此目的，除非另有说明，否则创建一个 `CertificateID` 来检查由颁发者证书 `issuerCert` 签发的序列号为 `serialNumber` 的证书状态，看起来如下：

```java
DigestCalculatorProvider digCalcProv =
    new JcaDigestCalculatorProviderBuilder().setProvider("BC").build();

CertificateID   id = new CertificateID(
    digCalcProv.get(CertificateID.HASH_SHA1), issuerCert, serialNumber);
```

其中传递给 `CertificateID` 构造函数的 `DigestCalculator` 如所示，是用于 SHA-1 的。

请求信息的载体结构是 `OCSPRequest`，在 BC API 中由 `OCSPReq` 类表示。如果需要，OCSPRequest 可以被签名，因此其 ASN.1 定义遵循与我们在证书中看到的类似模式。

完整 `OCSPRequest` 的 ASN.1 定义如下：

```
OCSPRequest     ::=     SEQUENCE {
    tbsRequest                  TBSRequest,
    optionalSignature   [0]     EXPLICIT Signature OPTIONAL }

TBSRequest      ::=     SEQUENCE {
    version             [0] EXPLICIT Version DEFAULT v1,
    requestorName       [1] EXPLICIT GeneralName OPTIONAL,
    requestList             SEQUENCE OF Request,
    requestExtensions   [2] EXPLICIT Extensions {{re-ocsp-nonce |
                     re-ocsp-response, ...,
                     re-ocsp-preferred-signature-algorithms}} OPTIONAL }

Signature       ::=     SEQUENCE {
    signatureAlgorithm   AlgorithmIdentifier
                             { SIGNATURE-ALGORITHM, {...}},
    signature            BIT STRING,
    certs            [0] EXPLICIT SEQUENCE OF Certificate OPTIONAL }

Version  ::=  INTEGER  {  v1(0) }
```

你唯一可能直接创建 BC `OCSPReq` 对象的时刻是作为响应者，此时你从某人发送给你的编码 `OCSPRequest` 结构中创建它。在客户端，你可以使用 `OCSPReqBuilder` 类构建 `OCSPReq`。

### 响应

响应者用 `OCSPResponse` 结构进行回复。在 Bouncy Castle OCSP API 中，`OCSPResponse` 结构由 `OCSPResp` 类表示。其 ASN.1 描述如下：

```
OCSPResponse ::= SEQUENCE {
  responseStatus         OCSPResponseStatus,
  responseBytes          [0] EXPLICIT ResponseBytes OPTIONAL }

OCSPResponseStatus ::= ENUMERATED {
   successful            (0),  -- 响应具有有效确认
   malformedRequest      (1),  -- 非法确认请求
   internalError         (2),  -- 颁发者内部错误
   tryLater              (3),  -- 稍后重试
                               -- (4) 未使用
   sigRequired           (5),  -- 必须签名请求
   unauthorized          (6)   -- 请求未授权
}
```

上述结构需要注意的重要点是，响应状态并没有说明你所查询的任何证书的有效性！你需要进一步深入挖掘以获取相关信息。

如你所见，该结构的设计考虑了灵活性，`ResponseBytes` 结构遵循了你在许多 ASN.1 结构中看到的模式，其中包含一个 `OBJECT IDENTIFIER` 以允许识别其承载的负载——在这种情况下，嵌入在 `OCTET STRING` 中。

```
ResponseBytes ::= SEQUENCE {
   responseType            OBJECT IDENTIFIER,
   response                OCTET STRING }
```

RFC 6960 定义的标准响应是 `BasicOCSPResponse`，它由一个名为 `id-pkix-ocsp-basic` 的对象标识符定义，值为 `{ id-pkix-ocsp 1 }`。

```
BasicOCSPResponse ::= SEQUENCE {
  tbsResponseData          ResponseData,
  signatureAlgorithm       AlgorithmIdentifier,
  signature                BIT STRING,
  certs                [0] EXPLICIT SEQUENCE OF Certificate OPTIONAL }

ResponseData ::= SEQUENCE {
   version             [0] EXPLICIT Version DEFAULT v1,
   responderID             ResponderID,
   producedAt              GeneralizedTime,
   responses               SEQUENCE OF SingleResponse,
   responseExtensions  [1] EXPLICIT Extensions OPTIONAL }
```

你可以通过调用 `getResponseObject()` 方法访问 `OCSPResp` 对象中的负载。如果内部结构标识自身携带了与 `id-pkix-ocsp-basic` 关联的 `OCTET STRING`，则 `getResponseObject()` 将创建一个 `BasicOCSPResp`。

在 Bouncy Castle OCSP API 中，`OCSPResponse` 结构由 `OCSPResp` 类表示。`BasicOCSPResp` 允许你通过 `getResponseObject()` 方法获取 `BasicOCSPResp` 对象。

如你所见，`BasicOCSPResponse` 允许签名，由于 `responses` 字段是一个 `SEQUENCE`，它可以携带一组要包含在单个响应中的响应。还有一个 `certs` 字段，可以用于携带帮助验证与 `BasicOCSPResponse` 相关签名的证书。

`SingleResp` 类作为 `SingleResponse` 结构的封装。`SingleResponse` 结构的语法如下：

```
SingleResponse ::= SEQUENCE {
   certID                  CertID,
   certStatus              CertStatus,
   thisUpdate              GeneralizedTime,
   nextUpdate          [0] EXPLICIT GeneralizedTime OPTIONAL,
   singleExtensions    [1] EXPLICIT Extensions OPTIONAL }
```

如你所见，这有点像单个证书的“微型 CRL”。`SingleResp` 对象上的 `getCertStatus()` 方法返回的 `certStatus` 字段是实际证书状态，它会告诉证书是良好的（用 null 表示）还是存在问题。`nextUpdate` 字段通过 `getNextUpdate()` 方法访问，并在 OCSP 响应需要缓存时（因此用于 OCSP 装）可以使用。注意：由于 `nextUpdate` 是可选的，它可能不存在，此时 `getNextUpdate()` 方法将返回 null。

通常你只会在客户端直接构建 `OCSPResp`，此时你正在转换一个编码响应。在响应者中，你通常使用 `OCSPRespBuilder` 构建 `OCSPResp`。

### 扩展

查看 ASN.1，OCSP 请求和响应都可以携带扩展。RFC 6960 中列出了若干种扩展，但这里详细介绍了最常见的两种。

#### Nonce

`nonce` 扩展用于将响应与请求匹配，并防止重放攻击^(16)。正如该扩展的名称所示，`nonce` 扩展的值应该是客户端在合理期限内仅使用一次的内容。其 ASN.1 定义和标记如下：

```
id-pkix-ocsp-nonce     OBJECT IDENTIFIER ::= { id-pkix-ocsp 2 }

Nonce ::= OCTET STRING
```

由于该值被指定为 `OCTET STRING`，因此它可以是客户端希望使用的任何符合“重用风险”标准的的内容。使用时，客户端会将该扩展添加到请求中，然后由响应者在响应中将其原样返回。

### 可接受的响应类型

除了 `BasicOCSPResponse` 之外，OCSP 允许允许多种响应类型。当响应者能够响应多种响应类型时，客户端限制响应者可能选择的响应类型是一个明智的主意。

实现这一点的扩展是 `AcceptableResponses` 扩展，其定义和标记如下：

```
id-pkix-ocsp-response  OBJECT IDENTIFIER ::= { id-pkix-ocsp 4 }

AcceptableResponses ::= SEQUENCE OF OBJECT IDENTIFIER
```

RFC 6960 规定响应者必须能够提供包含 `BasicOCSPResponse` 的响应。如果你需要告诉响应者你的客户端只能处理 `BasicOCSPResponse`，你可以按照如下创建扩展：

```java
Extension ext =
    new Extension(OCSPObjectIdentifiers.id_pkix_ocsp_response, true,
       new DERSequence(OCSPObjectIdentifiers.id_pkix_ocsp_basic).getEncoded());
```



然后使用 `OCSPReqBuilder` 类将其添加到你的请求中，我们将在下文中介绍该类。

## OCSP Stapling：解决 OCSP 的问题

在查看 Bouncy Castle API 如何支持 OCSP 之前，值得注意的是，虽然 OCSP 解决了大部分关于使用 CRL 的问题，但它也带来了一些自己的问题。提供 OCSP 响应者并签发大量高级证书的 CA 将面临大量的请求；此外，还会创建一个“侧信道”，因为执行 OCSP 检查的连接端会向签发证书的 CA 广播它正在与该证书的持有方通信。对于像 TLS 这样的协议来说，这可能是一个特别严重的问题，因为客户端浏览器会发现自己正在向 CA 广播其流量习惯——这可能不是所有人认为积极的特性。

![OCSP Stapling - 服务器发送短寿命 OCSP 响应以及其证书](img/chapter9----OCSPStapling.png)

OCSP Stapling - 服务器发送短寿命 OCSP 响应以及其证书

这个问题可以通过名为 OCSP stapling（OCSP 封字）的程序来解决，在这一概念起源的 TLS 中，它被称为多证书状态请求扩展，并在 RFC 6961 [116] 中描述。在这种情况下，TLS 服务器收集 OCSP 响应并将其与其证书路径一起发送。客户端随后验证 OCSP 响应上的签名（必须由证书签发者签名），然后就可以确认证书是有效的——至少在 OCSP 响应的有效期范围内。

OCSP stapling 的原理是服务器负责收集响应，因此客户端的身份得到了保护。此外，虽然 OCSP 响应的寿命很短，但它们不是一次性的，因此服务器可以重用响应直到需要新的响应——从而减轻 CA OCSP 响应者的负载。如果你在自己设计的系统中使用 OCSP，你可能需要考虑这一点。

## 生成 OCSP 请求

此示例展示了一个生成 OCSP 请求的方法，用于查询签发者为 `issuerCert` 序列号为 `serialNumber` 的证书的有效性。该请求还生成包含一个 nonce 扩展。

```java
/**
 * 生成一个关于证书 serialNumber 的 OCSP 请求，
 * 由 issuerCert 表示，并包含一个 nonce 扩展。
 *
 * @param issuerCert 我们想要检查的证书的签发者证书。
 * @param serialNumber 我们想要检查的证书的序列号。
 * @return 一个 OCSP 请求。
 */
public static OCSPReq generateOCSPRequest(
        X509CertificateHolder issuerCert, BigInteger serialNumber)
    throws OCSPException, OperatorCreationException
{
    DigestCalculatorProvider digCalcProv =
        new JcaDigestCalculatorProviderBuilder().setProvider("BC").build();

    // 生成我们正在查找的证书的 ID
    CertificateID id = new CertificateID(
        digCalcProv.get(CertificateID.HASH_SHA1), issuerCert, serialNumber);

    // 带有 nonce 的基础请求
    OCSPReqBuilder bldr = new OCSPReqBuilder();

    bldr.addRequest(id);

    // 创建 nonce 扩展的细节 - 仅供示例！
    BigInteger nonce = BigInteger.valueOf(System.currentTimeMillis());

    bldr.setRequestExtensions(new Extensions(
        new Extension(OCSPObjectIdentifiers.id_pkix_ocsp_nonce,
                     true, new DEROctetString(nonce.toByteArray()))));

    return bldr.build();
}
```

代码遵循三个步骤：首先构建 `CertificateID`，以便我们在请求中包含要检查的证书的正确信息。接下来，我们创建一个 `OCSPReqBuilder` 并将 `CertificateID` 添加其中。最后，我们向构建器添加 nonce 扩展，然后生成完成请求。

## 生成 OCSP 响应

组合一个 OCSP 响应需要使用 `BasicOCSPRespBuilder` 和 `OCSPRespBuilder` 类。我们需要这两个构建器，因为 OCSP 允许在 `OCSPResponse` 中包含 `BasicOCSPResponse` 以外的响应类型。

接下来的示例方法编写目的是允许根据最后一个参数——`revokedSerialNumber` 为传递给它的证书生成通过或失败的响应。

```java
/**
 * 根据单个撤吊的证书生成 OCSP 响应。
 *
 * @param request 我们被要求检查的 OCSP 请求。
 * @param responderKey 响应者的签名密钥。
 * @param pubKey 响应者的公钥。
 * @param revokedSerialNumber 我们视作已撤销的序列号。
 * @return 一个 OCSP 响应。
 */
public static OCSPResp generateOCSPResponse(
    OCSPReq request,
    PrivateKey responderKey, SubjectPublicKeyInfo pubKey,
    BigInteger revokedSerialNumber)
    throws OCSPException, OperatorCreationException
{
    DigestCalculatorProvider digCalcProv =
        new JcaDigestCalculatorProviderBuilder().setProvider("BC").build();
   BasicOCSPRespBuilder basicRespBldr = new BasicOCSPRespBuilder(
                                pubKey,
                                digCalcProv.get(CertificateID.HASH_SHA1));
   Extension ext = request.getExtension(
                            OCSPObjectIdentifiers.id_pkix_ocsp_nonce);
   if (ext != null)
   {
       basicRespBldr.setResponseExtensions(new Extensions(ext));
   }
   Req[] requests = request.getRequestList();
   for (int i = 0; i != requests.length; i++)
   {
       CertificateID certID = requests[i].getCertID();
       // 这通常会更通用得多！
       if (certID.getSerialNumber().equals(revokedSerialNumber))
       {
            basicRespBldr.addResponse(certID,
                new RevokedStatus(new Date(), CRLReason.privilegeWithdrawn));
        }
       else
       {
            basicRespBldr.addResponse(certID, CertificateStatus.GOOD);
        }
   }
   ContentSigner signer = new JcaContentSigner("SHA256WithECDSA")
                                   .setProvider("BC").build(responderKey);
   BasicOCSPResp basicResp = basicRespBldr.build(signer, null, new Date());
   OCSPRespBuilder respBldr = new OCSPRespBuilder();
   return respBldr.build(OCSPRespBuilder.SUCCESSFUL, basicResp);
}
```

通过代码可以看到，我们需要先设置 `BasicOCSPRespBuilder`，如果请求中存在 nonce，则将其添加。处理步骤是检查请求中的任何 `CertificateID` 对象是否与我们给出的撤销序列号匹配。接下来，我们构建并签名 `BasicOCSPResp`（我们假设客户端知道如何验证证书链）。最后创建一个 `OCSPResp` 对象，由于我们能够完整处理请求，指示成功状态。

### 将请求生成器与响应结合

接两个代码示例是一个通用的状态报告器，用于说明你可能如何解释响应。在下面的代码片段中，我们使用之前定义的 `generateOCSPRequest()` 生成请求，然后使用上一节定义的 `generateOCSPResponse()` 方法处理结果。

```java
/**
 * 使用 OCSP 请求和响应检查证书是否为撤销序列号。
 * @param caPrivKey 签发者私钥。
 * @param caCert 签发者证书。
 * @param revokedSerialNumber 响应者视为撤销的序列号。
 * @param certToCheck 要生成 OCSP 请求的证书。
 * @return 用于 certToCheck 的状态消息。
 */
public static String getStatusMessage(
    PrivateKey caPrivKey, X509CertificateHolder caCert,
          BigInteger revokedSerialNumber, X509CertificateHolder certToCheck)
    throws Exception
{
    OCSPReq request = generateOCSPRequest(
                                    caCert, certToCheck.getSerialNumber());
    OCSPResp response = generateOCSPResponse(
        request,
        caPrivKey, caCert.getSubjectPublicKeyInfo(),
        revokedSerialNumber);
    BasicOCSPResp basicResponse =
                        (BasicOCSPResp)response.getResponseObject();
    ContentVerifierProvider verifier =
          new JcaContentVerifierBuilder()
                .setProvider("BC").build(caCert.getSubjectPublicKeyInfo());
    // 验证响应
    if (basicResponse.isSignatureValid(verifier))
    {
        SingleResp[] responses = basicResponse.getResponses();
        Extension reqExt = request.getExtension(
                            OCSPObjectIdentifiers.id_pkix_ocsp_nonce);
        byte[] reqNonce = reqExt.getEncoded();
        Extension respExt = basicResponse.getExtension(
                            OCSPObjectIdentifiers.id_pkix_ocsp_nonce);
        // 如果 nonce 存在则进行验证
        if (respExt != null
            && Arrays.equals(reqNonce, respExt.getEncoded()))
        {
            String message = "";
            for (int i = 0; i != responses.length; i++)
            {
                message += " certificate number "
                    + responses[i].getCertID().getSerialNumber();
                if (responses[i].getCertStatus()
                    == CertificateStatus.GOOD)
                {
                    return message + " status: good";
                }
                else
                {
                    return message + " status: revoked";
                }
            }
            return message;
        }
        else
        {
            return "response nonce failed to validate";
        }
    }
    else
    {
        return "response failed to verify";
    }
}
```

此代码片段仅执行一些初始设置以创建 `getStatusMessage()` 方法所需的密钥和证书，然后调用了它。

```java
public static void main(
    String[] args)
    throws Exception
{
    KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
    KeyPair caKp = kpGen.generateKeyPair();
    X509CertificateHolder caCert = createTrustAnchor(caKp, "SHA256WithECDSA");
    KeyPair certKp = kpGen.generateKeyPair();
    X509CertificateHolder certOfInterest = createIntermediateCertificate(
                                    caCert,
                                    caKp.getPrivate(),"SHA256WithECDSA",
                                    certKp.getPublic(), 0);
    System.out.println(
```



如果你按原运行 `main()`，你应该得到证书的序列号，后面跟着“status: good”。你也可以将 `certOfInterest.getSerialNumber().add(BigInteger.ONE)` 修改为 `certOfInterest.getSerialNumber()`，从而让 `getStatusMessage()` 返回“status: revoked”。

注意，虽然示例集中于 API 中最通用的 OCSP 类，但在 `org.bouncycastle.ocsp.jcajce` 中还有 JCA 特有的 OCSP 类，如 `JcaCertificateID`、`JcaBasicOCSPRespBuilder` 和 `JcaRespID`，它们允许使用 `PublicKey` 和 `X509Certificate` 类。

## 证书路径验证

当我们谈论证书路径（certificate path）时，我们指的是为了从某个特定的信任锚点（trust anchor，即我们直接信任的证书）到我们尝试验证的证书（通常是终端实体证书）而涉及的证书。这条路径实际上是一系列较短路径的集合，代表了完整证书路径从信任锚点不断延伸的各个子集。有时，证书路径也被称为证书链（certificate chain）。

我们已经触及了证书有效性的两个方面：证书是否由我们信任的证书颁发机构签名，以及我们是否确定该机构没有通过颁发 `CRL` 来撤销其签名。除了信任锚点（通常是自签名的）外，路径中的所有证书都需要满足这些标准。我们需要检查的另一点是，从信任锚点开始，路径上签发证书的每一个人，是否都意图让他们签发的特定证书按照该证书目前使用的方式被使用。

例如，我们已经看到 `Basic Constraints`（基本约束）扩展可以用于判断证书是否可以作为 `CA` 证书使用，或者是一个终端实体证书并代表路径的终点。现在想象，你面对的是一个证书路径，其中终端实体证书由一个证书签名，而该证书的 `Basic Constraints` 扩展并未断言签名证书是 `CA` 证书。在这种情况下，路径显然是无效的，因为签署我们所看到的终端实体证书的颁发者在签署该签名证书时，并没有考虑到将其用于签署其他证书。

除了上述示例外，路径验证可能极其复杂，或者至少看起来极其复杂。路径验证最常用的算法是 `RFC 5280` [101] 中介绍的 IETF 算法，但重要的是记住，政府和企业都对 `RFC` 中给出的算法指定了不同的变体。这些变体被称为配置方案（profiles），在开始为特定组织验证证书之前，确保你意识到自己正在针对哪种配置进行验证至关重要。

## JCA 中的证书路径验证

Java 拥有自己的用于验证证书路径的 API，即 `CertPath` API。这涉及到几个通过 `getInstance()` 方法创建的类，因为它们的内部实现可能会随提供者（provider）的不同而异。还有一些用于配置证书路径分析器的参数类，以及用于携带分析结果的类和用于携带证书路径本身的类。

### CertPath API

以下所有类都封装在 `java.security.cert` 包中。我们将在示例中展示如何使用这些类，但以下内容可以让你对阅读代码时看到的内容有一个大致的了解。

#### CertPath
`CertPath` 是证书链或路径的载体类。该类的对象是通过 `CertificateFactory.generateCertPath()` 方法之一创建的，而不是直接创建的。

#### CertStore
`CertStore` 是证书和 `CRLs` 的通用存储区。它们通过 `CertStore.getInstance()` 创建，并要求作为 `getInstance()` 方法一部分 `CertStoreParameters` 对象。

#### CertStoreParameters
`CertStoreParameters` 有两个子类：`CollectionCertStoreParameters` 和 `LDAPCertStoreParameters`。这些类的存在是为了让 `CertStores` 能够获取证书和 `CRLs`。如果你想实现底层的 `CertStore`，也可以指定自己的类。

#### CertSelector
`CertSelector` 是一个提供证书匹配机制的通用接口。当你需要这些选择之一时，通常会使用 `X509CertSelector` 类。

#### CertPathBuilder
`CertPathBuilder` 是用于构建已验证证书路径的支持类。这些也是基于提供者的，并使用 `getInstance()` 工厂模式。

#### CertPathValidator
`CertPathValidator` 是用于验证现有证书路径的支持类。`CertPathValidator` 也是基于提供者的，并使用 `getInstance()` 工厂模式创建。

#### CRLSelector
`CRLSelector` 是一个提供 `CRLs` 匹配机制的通用接口。通常在你需要这些之一时使用它。

#### PKIXParameters
`PKIXParameters` 是将配置传递给证书路径验证器或通过其子类 `PKIXBuilderParameters` 传递给证书路径构建器的主要类。

#### PKIXBuilderParameters
`PKIXBuilderParameters` 是 `PKIXParameters` 类的扩展。该类允许定义允许的最大路径长度，并提供关于你希望验证或构建路径的终端实体证书的详细信息。

#### PKIXCertPathValidatorResult
如果证书路径验证失败，你将遇到异常。在验证通过的情况下，结果将以 `PKIXCertPathValidatorResult` 返回。

#### PKIXCertPathChecker
`PKIXCertPathChecker` 类提供了自定义证书路径验证的方法，允许开发者引入自己的检查项。

#### PKIXRevocationChecker
`PKIXRevocationChecker` 类是 `PKIXCertPathChecker` 的扩展类，于 Java 8 中出现。该类为自定义 `CRLs` 和 `OCSP` 的使用提供了超出通常允许范围的支持。

#### TrustAnchor
`TrustAnchor` 提供了一种机制，为证书路径构建器或验证器提供公钥或包含该公钥的证书，你愿意直接信任该证书以形成证书路径的基础。

#### X509CertSelector
`X509CertSelector` 是一个可变的类，可以配置为匹配特定的证书。在证书路径构建器类中，它被用于指定代表终端实体的证书。

#### X509CRLSelector
`X509CRLSelector` 也是一个可变的类，可以配置为匹配特定的 `CRLs`。

### 基础示例

下面的示例展示了使用 Java `CertPath` API 对基于信任锚点、终端实体证书上方有一个 CA 证书的简单证书路径进行验证的过程。

```java
/**
 * 使用 CertPathValidator 验证证书路径的基本示例。
 */
public class JcaCertPathExample {
    public static void main(String[] args) throws Exception {
        //
        // 设置我们的示例数据
        //
        KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
        JcaX509CertificateConverter certConverter = new JcaX509CertificateConverter().setProvider("BC");
        JcaX509CRLConverter crlConverter = new JcaX509CRLConverter().setProvider("BC");
        KeyPair trustKp = kpGen.generateKeyPair();
        X509CertificateHolder trustHldr = createTrustAnchor(trustKp, "SHA256withECDSA");
        X509Certificate trustCert = certConverter.getCertificate(trustHldr);
        KeyPair caKp = kpGen.generateKeyPair();
        X509CertificateHolder caHldr = createIntermediateCertificate(trustHldr, trustKp.getPrivate(), "SHA256withECDSA", caKp.getPublic(), 0);
        X509Certificate caCert = certConverter.getCertificate(caHldr);
        KeyPair eeKp = kpGen.generateKeyPair();
        X509Certificate eeCert = certConverter.getCertificate(createEndEntity(caHldr, caKp.getPrivate(), "SHA256withECDSA", eeKp.getPublic()));
        X509CRL trustCRL = crlConverter.getCRL(createEmptyCRL(trustKp.getPrivate(), "SHA256withECDSA", trustHldr));
        X509CRL caCRL = crlConverter.getCRL(createEmptyCRL(caKp.getPrivate(), "SHA256withECDSA", caHldr));
        //
        // 创建我们的示例证书路径
        //
        CertificateFactory certFact = CertificateFactory.getInstance("X.509", "BC");
        List<X509Certificate> chain = new ArrayList<X509Certificate>();
        chain.add(caCert);
        chain.add(eeCert);
        CertPath certPath = certFact.generateCertPath(chain);
        //
        // 构建包含我们证书集的 CertStore。
        //
        List certStoreList = new ArrayList();
        certStoreList.add(trustCRL);
        certStoreList.add(caCert);
        certStoreList.add(caCRL);
        certStoreList.add(eeCert);
        CertStoreParameters params = new CollectionCertStoreParameters(certStoreList);
        CertStore certStore = CertStore.getInstance("Collection", params, "BC");
        //
        // 创建有效信任锚点的集合
        //
        Set<TrustAnchor> trust = new HashSet<TrustAnchor>();
        trust.add(new TrustAnchor(trustCert, null));
        //
        // 设置路径验证的参数
        //
        PKIXParameters param = new PKIXParameters(trust);
        X509CertSelector certSelector = new X509CertSelector();
        certSelector.setCertificate(eeCert);
        param.setTargetCertConstraints(certSelector);
        param.addCertStore(certStore);
        param.setRevocationEnabled(true);
        try {
            //
            // 创建验证器并执行验证。
            //
            CertPathValidator validator = CertPathValidator.getInstance("PKIX", "BC");
            PKIXCertPathValidatorResult result = (PKIXCertPathValidatorResult) validator.validate(certPath, param);
            System.out.println("validated: " + result.getPublicKey());
        } catch (CertPathValidatorException e) {
            System.out.println("validation failed: index (" + e.getIndex() + "), reason \"" + e.getMessage() + "\"");
        }
    }
}
```

### 自定义证书验证

`PKIXCertPathChecker` 类提供了在验证过程中引入您自己的处理逻辑的能力。这些类需要在配置时添加，并通过 `PKIXParameters.addCertPathChecker()` 方法添加到验证过程中。

您可能出于以下几个原因想要使用此类。例如，您可能正在处理一个引入了自定义关键扩展的验证配置（profile），在这种情况下您将需要基于 `PKIXCertPathChecker` 的实现以确保这些扩展得到正确处理。或者，您可能正在使用依赖 CRL 进行吊销检查的路径验证器，而您希望以不同的方式处理吊销，例如使用 OCSP。

### PKIXCertPathChecker 类

`PKIXCertPathChecker` 是一个抽象类，它包含四个需要由子类实现的方法。需要注意的是，提交给检查器的证书顺序是由路径验证器的编写者决定的。执行向前检查（forward checking）的验证器从实体证书（end-entity）开始，沿证书链向上直到信任锚点（trust anchor）。反向检查（reverse checking）则简单地按照相反方向提交证书，实体证书是最后一个提交的。

需要实现的四个方法是：

#### init()
顾如其名 `init()` 方法初始化检查器的状态。它的唯一布尔参数指示检查器是为正向检查（`true`）还是反向检查（`false`）进行初始化。

#### isForwardCheckingSupported()
如果支持正向检查，此方法应返回 `true`。注意：JCA 期望所有的检查器都支持反向处理。

#### getSupportedExtensions()
`getSupportedExtensions()` 应返回一个包含 `String` 对象的 OID 集合，代表该检查器处理的特定扩展。如果检查器的用途除了处理扩展之外，则它应返回 `null`。

#### check()
`check()` 方法是执行工作的地方。它接受两个参数：一个代表要检查的证书，另一个代表验证器无法处理的关键 OID 集合。这些 OID 存储在 `String` 类型的 `Set` 中，且该 `Set` 是可变的，其思路是您应该从中移除任何检查器已处理过的 OID，从而向调用该检查器的验证器信号这些扩展已处理。

下面的示例展示了一个基于 `PKIXCertPathChecker` 的简单 OCSP 检查器。在 Java 1.8 之前，以及对于支持旧版本 JVM 的提供程序，这是支持“自定义”OCSP 实现的唯一方法。

```java
/**
```



* 一个基础路径检查器，对单个 CA 进行 OCSP 检查

```java
public class OCSPPathChecker extends PKIXCertPathChecker {

    private KeyPair responderPair;
    private X509Certificate caCert;
    private BigInteger revokedSerialNumber;

    public OCSPPathChecker(KeyPair responderPair, X509Certificate caCert, BigInteger revokedSerialNumber) {
        this.responderPair = responderPair;
        this.caCert = caCert;
        this.revokedSerialNumber = revokedSerialNumber;
    }

    public void init(boolean forwardChecking) throws CertPathValidatorException {
        // ignore
    }

    public boolean isForwardCheckingSupported() {
        return true;
    }

    public Set getSupportedExtensions() {
        return null;
    }

    public void check(Certificate cert, Collection extensions) throws CertPathValidatorException {
        try {
            X509CertificateHolder issuerCert = new JcaX509CertificateHolder(caCert);
            X509CertificateHolder certToCheck = new JcaX509CertificateHolder((X509Certificate) cert);

            if (certToCheck.getIssuer().equals(issuerCert.getSubject())) {
                String message = OCSPProcessingExample.getStatusMessage(
                    responderPair.getPrivate(),
                    issuerCert,
                    revokedSerialNumber,
                    certToCheck
                );

                if (message.endsWith("good")) {
                    System.out.println(message);
                } else {
                    throw new CertPathValidatorException(message);
                }
            }
        } catch (Exception e) {
            throw new CertPathValidatorException("exception verifying certificate: " + e, e);
        }
    }
}
```

请注意 `isForwardCheckingSupported()` 方法返回 `true`，且 `getSupportedExtensions()` 返回 `null`。在 `OCSPPathChecker` 的情况下，该检查器对证书呈现的顺序是不敏感的，但因为它被用于撤销检查，它不处理任何扩展，因此 `getSupportedExtensions()` 返回 `null`，并且传递给 `check()` 方法的 `extensions` `Set` 不发生任何变化。

在下面的示例中，我们将 `OCSPPathChecker` 应用于路径验证。你可以看到路径检查器是如何被添加到 `PKIXParameters` 对象中的。请注意，调用 `PKIXParameters.setRevocationEnabled()` 时传入的参数为 `false`，否则路径验证器将期望能够为信任根锚和 CA 证书找到 CRL。

```java
/**
 * 使用 PKIXCertPathChecker 进行证书路径验证的基础示例，
 * 其中该检查器被用于检查撤销状态。
 */
public class JcaCertPathWithCheckerExample {

    public static void main(String[] args) throws Exception {
        KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
        JcaX509CertificateConverter certConverter = new JcaX509CertificateConverter().setProvider("BC");

        KeyPair trustKp = kpGen.generateKeyPair();
        X509CertificateHolder trustHldr = createTrustAnchor(trustKp, "SHA256withECDSA");
        X509Certificate trustCert = certConverter.getCertificate(trustHldr);

        KeyPair caKp = kpGen.generateKeyPair();
        X509CertificateHolder caHldr = createIntermediateCertificate(
            trustHldr,
            trustKp.getPrivate(),
            "SHA256withECDSA",
            caKp.getPublic(),
            0
        );
        X509Certificate caCert = certConverter.getCertificate(caHldr);

        KeyPair eeKp = kpGen.generateKeyPair();
        X509Certificate eeCert = certConverter.getCertificate(
            createEndEntity(caHldr, caKp.getPrivate(), "SHA256withECDSA", eeKp.getPublic())
        );

        List certStoreList = new ArrayList();
        certStoreList.add(caCert);
        certStoreList.add(eeCert);

        CertStoreParameters params = new CollectionCertStoreParameters(certStoreList);
        CertStore certStore = CertStore.getInstance("Collection", params, "BC");

        Set<TrustAnchor> trust = new HashSet<>();
        trust.add(new TrustAnchor(trustCert, null));

        PKIXParameters param = new PKIXParameters(trust);
        X509CertSelector certSelector = new X509CertSelector();
        certSelector.setCertificate(eeCert);

        param.setTargetConstraints(certSelector);
        param.addCertStore(certStore);
        param.setRevocationEnabled(false);
        param.addCertPathChecker(new OCSPPathChecker(caKp, caCert));

        CertPathValidator validator = CertPathValidator.getInstance("PKIX", "BC");
        CertificateFactory certFact = CertificateFactory.getInstance("X.509", "BC");

        List<X509Certificate> chain = new ArrayList<>();
        chain.add(caCert);
        chain.add(eeCert);

        CertPath certPath = certFact.generateCertPath(chain);

        try {
            PKIXPathValidatorResult result = (PKIXPathValidatorResult) validator.validate(certPath, param);
            System.out.println("validated: " + result.getPublicKey());
        } catch (CertPathValidatorException e) {
            System.out.println("validation failed: index (" + e.getIndex() + "), reason \"" + e.getMessage() + "\"");
        }
    }
}
```

`CertPathBuilder` 非常有用。许多协议会允许证书与签名数据或加密数据一起发送，而这些证书通常包含在 ASN.1 集合中，集合是无序的。集合的创建者还可能包含一些与当前任务不直接相关的额外证书和 CRL（证书吊销列表）。你可能会发现自己持有一个需要验证的签名，或者持有一个端实体证书，并怀疑该证书是否真的是你应该用于加密会话密钥的那个证书，并且有一堆“随机”的证书可以从中确定答案。在这种情况下，你需要使用 `CertPathBuilder`。

`CertPathBuilder` 的基本方法体现在 `PKIXBuilderParameters` 类的构造函数中，该构造函数接收信任锚点（trust anchors）以及一个作为端实体目标约束的 `CertSelector`。一旦在 `PKIXBuilderParameters` 对象中配置了其他设置，`CertPathBuilder` 的工作就是找到一个匹配目标约束的端实体，并构建一条通往受接受的信任锚点的有效路径。

这里是 `CertPathBuilder` 的用法示例。如你所见，除了使用 `PKIXBuilderParameters` 之外，发生的情况与你在 `CertPathValidator` 中看到的非常相似。

```java
/**
 * 使用 PKIXCertPathChecker 进行证书路径验证的基本示例，
 * 其中 checker 用于检查吊销状态。
 */
public class JcaCertPathWithCheckerExample {

    public static void main(String[] args) throws Exception {
        KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");
        JcaX509CertificateConverter certConverter = new JcaX509CertificateConverter().setProvider("BC");

        KeyPair trustKp = kpGen.generateKeyPair();
        X509CertificateHolder trustHldr = createTrustAnchor(trustKp, "SHA256withECDSA");
        X509Certificate trustCert = certConverter.getCertificate(trustHldr);

        KeyPair caKp = kpGen.generateKeyPair();
        X509CertificateHolder caHldr = createIntermediateCertificate(
            trustHldr,
            trustKp.getPrivate(),
            "SHA256withECDSA",
            caKp.getPublic(),
            0
        );
        X509Certificate caCert = certConverter.getCertificate(caHldr);

        KeyPair eeKp = kpGen.generateKeyPair();
        X509Certificate eeCert = certConverter.getCertificate(
            createEndEntity(caHldr, caKp.getPrivate(), "SHA256withECDSA", eeKp.getPublic())
        );

        List certStoreList = new ArrayList();
        certStoreList.add(caCert);
        certStoreList.add(eeCert);

        CertStoreParameters params = new CollectionCertStoreParameters(certStoreList);
        CertStore certStore = CertStore.getInstance("Collection", params, "BC");

        Set<TrustAnchor> trust = new HashSet<>();
        trust.add(new TrustAnchor(trustCert, null));

        CertPathValidator validator = CertPathValidator.getInstance("PKIX", "BC");
        PKIXParameters param = new PKIXParameters(trust);
    }
}
```



## 第 10 章：密钥和证书存储

JCA 提供了一个通用的密钥库类，允许以文件形式存储密钥，有时也可以作为硬件密钥的前端。在本章中，我们只查看文件存储类型。Java 原生支持 3 种不同的密钥库类型，Bouncy Castle 又增加了几个。Java 和 Bouncy Castle 中的某些原始密钥库类型现在被认为过时，因为它们无法跟上安全需求的变化。这也影响了 Java `keytool` 的用法——在旧的密钥库类型中，证书等内容通常以明文形式存储，因此可以在不提供密码的情况下对密钥库进行某些处理。现在情况不再如此。

### 示例的设置

在我们开始查看密钥库类型之前，最好要有一些可以存储在其中的内容。在这种情况下，这需要一个私钥以及一个与公钥关联的证书。标准的 Java VM 已经有一个类来将它们链接在一起了，即 `X500PrivateCredential`，它是在 `Java 1.5` 中添加的。我们在这里创建了自己的版本，因为该类在不同 Java 配置中的普及程度并没有你想象中那么广泛（例如，在编写本文时，Android 还缺少该类）。以下是一个私钥及其关联证书的简单载体类的定义。

```java
 1 /**
 2  * 私钥及其相应公钥证书的载体类。
 3  * <p>
 4  * 标准 Java API 也有 javax.security.auth.x500.X500PrivateCredential，
 5  * 该类是它的基础替代品。BC PKIX API 中还有一个稍微更
 6  * 通用的类 - org.bouncycastle.pkix.PKIXIdentity。
 7  * </p>
 8  */
 9 public class PrivateCredential
10 {
11     private final X509Certificate certificate;
12     private final PrivateKey privateKey;
13 
14     /**
15      * 基础构造函数。
16      *
17      * @param certificate 与 privateKey 匹配的公钥证书。
18      * @param privateKey 与 certificate 参数匹配的私钥。
19      */
20     public PrivateCredential(X509Certificate certificate, PrivateKey privateKey)
21     {
22         this.certificate = certificate;
23         this.privateKey = privateKey;
24     }
25 
26     public PrivateKey getPrivateKey()
27     {
28         return privateKey;
29     }
30 
31     public X509Certificate getCertificate()
32     {
33         return certificate;
34     }
35 }
```

定义了载体类后，我们将使用以下方法来生成私钥以及关联的自签名证书。

```java
 1   /**
 2    * 创建一个带有关联自签名证书的私钥，
 3    * 并将其封装在 X500PrivateCredential 中返回。
 4    *
 5    * 注意：我们使用了第 6 章 EcDsaUtils 中的 generateECKeyPair() 
 6    * 以及第 8 章 JcaX509Certificate 中的 createTrustAnchor()。
 7    *
 8    * @return 包含密钥及其证书的 X500PrivateCredential。
 9    */
10   public static PrivateCredential createSelfSignedCredentials()
11       throws GeneralSecurityException, OperatorCreationException
12   {
13       JcaX509CertificateConverter certConverter =
14                          new JcaX509CertificateConverter().setProvider("BC");
15 
16       KeyPair selfSignedKp = generateECKeyPair();
18 
19       X509CertificateHolder selfSignedHldr =
19                          createTrustAnchor(selfSignedKp, "SHA256withECDSA");
21 
22       X509Certificate selfSignedCert = certConverter.getCertificate(selfSignedHldr);
23 
24       return new PrivateCredential(selfSignedCert, selfSignedKp.getPrivate());
25   }
```

我们将利用 `createSelfSignedCredentials()` 方法来提供密钥和证书测试数据，以便存储在我们将查看的各种密钥库中。

### 早期密钥库类型：JKS, JCEKS, BKS 和 UBER

JKS、JCEKS、BKS 和 UBER 格式都是由 JCA 或 Bouncy Castle 提供的早期格式（对于 JKS 和 JCEKS 是 JCA，对于 BKS 和 UBER 则是 Bouncy Castle）。它们现在开始不再用于存储私钥/秘密密钥，部分原因是因为现在有了更安全的格式可用。JKS 和 BKS 密钥库仍常用于公钥证书。

JKS 格式是 JCA 的原始密钥库格式。该格式提供了某种程度的防篡改保护，并且私钥使用了基于 `SHA-1` 的专用流密码进行加密。密钥库无法存储秘密密钥。JKS 密钥库文件通常具有 `.jks` 扩展（如果有的话）。在不知道密钥库密码的情况下，可以使用 `keytool` 查看 JKS 密钥库的大部分内容，尽管在没有密码的情况下无法恢复私钥。

JCEKS 格式随 JCE 引入的。这种存储格式也可以存储秘密密钥，在这种情况下，使用 Triple-DES 来保护私钥和秘密密钥。JCEKS 密钥库文件通常具有 `.jceks` 扩展。同样，在不知道密钥库密码的情况下，可以使用 `keytool` 查看 JCEKS 密钥库的大部分内容，尽管在没有密码的情况下无法恢复受保护的秘密密钥或私钥。

BKS 格式类似于 JCEKS 的格式。在不知道密钥库密码的情况下，可以使用 `keytool` 查看 BKS 密钥库的大部分内容，尽管在没有密码的情况下无法恢复私钥。BKS 也可以存储秘密密钥和私钥，并使用 Triple-DES 保护它们。BKS 中使用 `PKCS#12` 的 `PBKDF` 将密码转换为密钥。

UBER 格式基于 BKS，但与 BKS 不同，它将密钥库存储为加密的二进制大对象，使用 Twofish 加密算法进行保护。这意味着在没有密码的情况下，无法使用 Java 的 `keytool` 访问密钥库。

下面的示例代码展示了如何生成一个带有单个私钥和自签名证书的基础 JKS 密钥库。

```java
 1 /**
 2  * 使用 JKS 存储单个私钥和自签名
 3  * 证书的示例示例。
 4  */
 5 public class JKSExample
6 {
 7     public static void main(String[] args)
 8         throws Exception
 9     {
10         PrivateCredential cred = createSelfSignedCredentials();
11 
12         KeyStore store = KeyStore.getInstance("JKS");
13 
14         store.load(null, null);
15 
16         store.setKeyEntry("key", cred.getPrivateKey(), "keyPass".toCharArray(),
17             new Certificate[] { cred.getCertificate() });
18 
19         FileOutputStream fOut = new FileOutputStream("basic.jks");
20 
21         store.store(fOut, "storePass".toCharArray());
22 
23         fOut.close();
24     }
25 }
```

注意 `store.load(null, null);` 执行了初始化密钥库的任务。

如果你运行该示例，它将创建一个名为 `basic.jks` 的 JKS 格式文件。我们将在下一节中使用该文件查看 `keytool` 的命令。

### keytool 命令

`keytool` 是一个用于命令行处理密钥库的 Java 工具。它默认处理 JKS 密钥库，因此对于基础查看或显示现有密钥库，你只需要使用 `-list` 选项，并提供密钥库的位置 `-keystore` 以及存储密码 `-storepass`。如果没有作为参数传递存储密码，`keytool` 命令会提示输入。

#### 查看密钥库

假设你想使用 `keytool` 查看上一节创建的 JKS 密钥库，可以这样使用：

```
keytool -list -keystore basic.jks -storepass storePass
```

运行此命令应该显示类似下方的输出：

```text
Keystore type: jks
Keystore provider: SUN
您的密钥库包含 1 个条目
key, <dd/mm/yyyy>, PrivateKeyEntry,
Certificate fingerprint (SHA1): <一个 SHA-1 指纹>
```

其中 `<dd/mm/yyyy>` 是条目创建时的日期（日/月/年格式）。

指纹看起来像这样：

```text
ED:44:9F:92:5B:DA:C8:DD:34:9A:7A:A5:B3:8D:04:D7:CE:6B:69:27
```

尽管你可能会预期数字是不同的，因为 SHA-1 指纹的想法是提供一个可以唯一标识证书的 20 字节值。在较新的 JVM 中，你还会发现指纹已升级为 SHA-256，在这种情况下它将包含 32 个十六进制值，描述显示为：

```text
Certificate fingerprint (SHA-256): ...
```

要查看在不在命令行或通过 `Enter keystore password` 提示时不输入密码时会发生什么，请尝试以下操作：在提示输入密码时，不要输入任何密码字符，直接按 `<enter>` 键即可。

```
keytool -list -keystore basic.jks
```

如果你在密码提示处直接按下 `<enter>`，你应该会看到类似下面的内容：

```text
*****************  WARNING WARNING WARNING  *****************
* 您的密钥库中存储信息的完整性  *
* 尚未经过验证！为了验证其完整性，*
* 您必须提供您的密钥库密码。                  *
*****************  WARNING WARNING WARNING  *****************
Keystore type: jks
Keystore provider: SUN
Your keystore contains 1 entry
key, <dd/mm/yyyy>, PrivateKeyEntry,
Certificate fingerprint (SHA1): <a SHA-1 fingerprint>
```

### 生成密钥对

你也可以使用 `keytool` 从命令行创建一个带有初始密钥对的密钥库。例如，尝试运行：

```
keytool -genkey -alias key -keyalg RSA -keystore rsa.jks -keysize 2048
```

由于命令行中没有传递密码，命令将提示你输入密码。在生成密钥对后，它还会提示输入与自签名证书关联的 X.500 DN 元素，该证书将包含公钥，而公钥将与私钥一同存储。

你可以通过对生成的密钥库运行 list 命令来查看结果：



`keytool -list -keystore rsa.jks`

假设你正在使用 Java 9 之前的 JVM，你将看到类似下面的内容，显示了我们为别名 `key` 生成的私钥条目：

```
Enter keystore password:
Keystore type: jks
Keystore provider: SUN

Your keystore contains 1 entry

key, <dd/mm/yyyy>, PrivateKeyEntry,
Certificate fingerprint (SHA1): <a SHA-1 fingerprint>
```

随着 Java 9 的发布，JVM 维护者转而使用 PKCS12 作为默认文件格式，而不是 JKS。我们将在本章的后续部分进一步介绍 PKCS12，但如果你使用 Java 9 或更高版本运行 `list` 命令，你将看到类似下面的内容：

```
Enter keystore password:
Keystore type: PKCS12
Keystore provider: SUN

Your keystore contains 1 entry

key, <dd mmm yyyy>, PrivateKeyEntry,
Certificate fingerprint (SHA-256): <a SHA-256 fingerprint>
```

这表示密钥库是 PKCS12 类型，并且显示的创建日期月份使用的是短名称形式而非数字。

## 生成证书请求

在生成带有自签名证书的密钥后，我们通常希望从证书机构（CA）获取一个证书来替换我们的自签名证书。

```
keytool -certreq -alias key -file csr.txt -keystore rsa.jks
```

`csr.txt` 文件在某种意义上是人类可读的。如果你查看它，会发现在包含 `-----BEGIN NEW CERTIFICATE REQUEST-----` 行和以 `-----END NEW CERTIFICATE REQUEST-----` 结尾的行之间有一个 base64 编码块。我们将在第 12 章详细查看这些内容，但这里的快速摘要是：你在文件中看到的内容实际上是 DER 编码 PKCS#10 证书请求的 base64 编码。它包含了两个值得注意点：你之前生成的公钥，以及你想要与之关联的 X.500 名称。这两个点都使用与公钥关联的私钥生成的签名进行了完整性保护。

## 导入从证书机构收到的证书

一旦你将证书请求发送给证书机构（CA），你将收到另一个包含 CA 签名的实际证书的文件。你需要将此加载到密钥库中以替换你的自签名证书。这通常是一个两步骤的过程：你需要导入 CA 的信任锚点（trust anchor），然后导入 CA 的响应，通过对创建密钥时使用的相同别名进行导入，将其与你生成的密钥关联。

在下面的示例中，我们考虑了实现这一点的方法：CA 在名为 `ca-trustanchor.pem` 的文件中发送了它的信任锚点，并将我们证书请求的响应放在名为 `ca-response.pem` 的文件中。

我们的第一步是将信任锚点作为信任证书导入密钥库。我们的操作如下：

```
keytool -import -alias ca-name -keystore rsa.jks -file ca-trustanchor.pem
```

其中 `ca-name` 是我们为该 CA 选择的别名，`ca-trustanchor.pem` 是信任锚点证书。`keytool` 命令将打印有关信任锚点证书的一些细节，并请求确认以信任它。假设一切顺利，你应该回答 `yes` 以确认该证书应被信任。

接下来我们导入响应，但这次导入使用的是我们生成原始密钥时使用的别名 - `key`。

```
keytool -import -alias key -keystore rsa.jks -file ca-response.pem
```

当执行此导入时，最初为我们的密钥生成的自签名证书将被丢弃，`ca-response.pem` 中的 CA 响应证书将取而代之。此时，对于任何其他依赖你所使用的 CA 的人来说，你应该

### PKCS12 存储类型

PKCS12 store 的名称、格式源自“PKCS #12: Personal Information Exchange”。最初 PKCS #12 是一个 RSA 控制的标准，但现在由 IETF 管理，最新版本为 RFC 7292。

使用 Bouncy Castle 提供程序创建 PKCS12 文件的过程与 JKS 相似，不同之处在于密钥没有密码。在示例中你可以看到密钥被设置为 `null`：

```java
/**
 * 使用 JKS 存储单个私钥和自签名
 * 证书的基本示例。
 */
public class PKCS12Example {
    public static void main(String[] args)
        throws Exception
    {
        PrivateCredential cred = createSelfSignedCredentials();

        KeyStore store = KeyStore.getInstance("PKCS12", "BC");

        store.load(null, null);

        store.setKeyEntry("key", cred.getPrivateKey(), null,
            new Certificate[] { cred.getCertificate() });

        FileOutputStream fOut = new FileOutputStream("basic.12");

        store.store(fOut, "storePass".toCharArray());

        fOut.close();
    }
}
```

没有密钥密码是因为传统的 PKCS12 是为个人数据设计的，因此只需要保护密钥库的密码。Bouncy Castle 遵循这种模式，大多数实现也是如此。

你可以使用 `keytool` 命令列出创建密钥库，尽管在早期的 JVM 上你需要使用 `-storetype` 选项指定密钥库类型，例如：

```
keytool -list -keystore basic.12 -storetype PKCS12
```

### BCFKS/BCSFKS 密钥库类型

BCFKS 密钥库类型的出现是因为我们的首次 FIPS 认证。用户面临的问题涉及将密钥存储在磁盘上，但要确保文件格式完全符合 FIPS 标准。这当然包括使用 PBKDF2 进行密码转换，并能够支持为密钥库中的密钥设置不同的密码。PKCS #12 作为最接近的方案被排除，因为很少有实现支持不同的密钥和密钥库密码，而且普通的 PBE 算法也不符合 FIPS 标准。

考虑到这一点，下面的示例创建了一个 BCFKS 密钥库。

```java
/**
 * 使用 BCFKS 存储单个私钥和自签名
 * 证书的基本示例。
 */
public class BCFKSExample
{
    public static void main(String[] args)
        throws Exception
    {
        PrivateCredential cred = createSelfSignedCredentials();

        KeyStore store = KeyStore.getInstance("BCFKS", "BC");

        store.load(null, null);

        store.setKeyEntry("key", cred.getPrivateKey(), "keyPass".toCharArray(),
            new Certificate[] { cred.getCertificate() });

        FileOutputStream fOut = new FileOutputStream("basic.fks");

        store.store(fOut, "storePass".toCharArray());

        fOut.close();
    }
}
```

创建的角度来看，`BCFKS` 密钥库的功能与 `JKS` 密钥库非常相似。请注意，`BCFKS` 格式虽然允许为密钥关联单独密码，但它在方法上与 `PKCS#12` 类似，即它假设一旦进程解锁了密钥，就可以再次使用它，也就是说密钥密码只会被检查一次。如果你正在运行一个想要保证每个线程隔离的应用程序，请使用下面详细介绍的 `IBCFKS` 变体。`IBCFKS` 是 `BCFKS` 密钥库的不可变封装，因此磁盘上的存储格式相同，但加载时的行为不同。

### 定制化 BCFKS

由于 `BCFKS` 格式完全由其数据文件中存储的算法标识符驱动，因此可以在格式中引入不同的算法。

#### 使用 Scrypt

引入的第一个自定义是引入使用 `scrypt` 算法的能力。`scrypt` 算法为 `FIPS` 方案 `PBKDF2` 提供了一个内存困难的封装。我们最初在第 5 章中查看过 `scrypt`。在接下来的示例中，我们将看到如何使用 `ScryptConfig` 来初始化 `BCFKS` 密钥库，以便使用基于 `scrypt` 的 `PBKDF2` 保护密钥库。

```java
/**
 * 使用 BCFKS 存储单个私钥和自签名
 * 证书的示例，使用 scrypt 进行密钥库保护。
 */
public class BCFKSwithScryptExample
{
    public static void main(String[] args)
        throws Exception
    {
        PrivateCredential cred = createSelfSignedCredentials();

        // 指定 scrypt 参数
        PBKDFConfig config = new ScryptConfig.Builder(1024, 8, 1)
                                                         .withSaltLength(20).build();

        KeyStore store = KeyStore.getInstance("BCFKS", "BC");

        // 使用 scrypt 初始化空存储库
        store.load(new BCFKSLoadStoreParameter.Builder()
                                         .withStorePBKDFConfig(config)
                                         .build());

        store.setKeyEntry("key", cred.getPrivateKey(), "keyPass".toCharArray(),
                                     new Certificate[] { cred.getCertificate() });

        FileOutputStream fOut = new FileOutputStream("scrypt.fks");

        store.store(fOut, "storePass".toCharArray());

        fOut.close();
    }
}
```

正如我们在第 5 章所看到的，`scrypt` 的思想不仅是为了引入密码哈希和加盐来保护密码，它还引入了内存困难性——这意味着它消耗大量内存，以防止哈希过程很容易适配于如改装的图形加速器或专用硬件的加速。

#### 使用 IBCFKS

`IBCFKS` 密钥库设计用于在不同线程之间共享。它是普通 `BCFKS` 密钥库的不可变封装，该库始终需要密码来解锁密钥。如果你已经有一个不想更改的 `BCFKS` 密钥库，可以使用 `IBCFKS` 来防止应用程序线程在加载后更改密钥库。例如：

```
KeyStore store = KeyStore.getInstance("IBCFKS", "BC");
FileInputStream fIn = new FileInputStream("basic.fks");

store.load(fIn, "storePass".toCharArray());
```

可以被用于加载我们在上一个示例中创建的 `BCFKS` 密钥库。

### 使用 keytool 转换密钥库

有时你会发现自己拥有某种格式的密钥库，而你需要完全不同格式的密钥库。你可以使用 `keytool` 的 `-importstore` 操作来执行这种转换。下面的示例展示了如何将 `JKS` 格式的文件转换为 `BCFKS` 文件：

```
keytool -importkeystore -srckeystore rsa.jks \
                -destkeystore rsa.bcfks -deststoretype BCFKS
```

此示例中对源密钥库没有规范，因为我们使用的是 `JKS` 密钥库（默认）。如果源密钥库是其他类型，你需要使用 `-srcstoretype` 来指定源密钥库的类型。

关于密钥库转换有一个警告。在大多数情况下，如果密钥库仅包含私钥及其关联证书，转换应该总是顺畅的。并不是所有的密钥库类型都支持存储对称密钥，因此如果源密钥库中存在对称密钥，转换时可能会出现问题。在这种情况下，你可能需要将原始密钥库拆分，以便你拥有

### 总结

在本章中，我们检查了现在已过时的密钥历史格式。我们研究了现代 FIPS 兼容密钥库的属性以及如何在软件中使用。

本章主要使用 `keytool`，因为虽然密钥和证书存储可以通过 BouncyCastle API 完成，但大多数密钥库的操作是通过命令行完成的。

最后，我们涵盖了密钥库的格式转换，同样使用了 `keytool`。请注意，如果密钥库中有对称密钥，转换可能无法正常工作

## 第 11 章：加密消息语法、S/MIME 和 TSP

在本章中，我们将查看使用我们目前所学的加密原语的高级消息协议。我们将从加密消息语法（Cryptographic Message Syntax）开始，它是其他消息格式的起点，例如安全 MIME (S/MIME) 和时间戳协议 (TSP)。在发布方面，处理这些消息类型的 API 主要出现在以 `bcpix` 为头的 jar 中，唯一的例外是基于 JavaMail 的 S/MIME API，它出现在以 `bcmail` 开头的 jar 中。

### 加密消息语法

加密消息语法最初在 `PKCS#7` 中描述，由于原因，它通常被称为 `PKCS#7` 或缩写 `CMS`。在原始形式中，它提供了消息的签名、加密和基于 MAC 的认证机制。之后情况发生了变化，标准的持续开发已由 IETF 接管，最新版本的 CMS 描述在 `RFC 5652` 中。CMS 的编码基于 `ASN.1`，除了作为签名或 MAC 算法输入的结构外，CMS 结构被定义为使用 `BER` 编码规则。`BER` 的意味着 CMS 结构通常使用不定长度编码构建，并且能够处理比处理它的可用内存更大的消息数据。

CMS 结构都封装在一个基础结构中，即 `ContentInfo` 结构。在 `RFC 5652` 中，`ContentInfo` 结构及其字段定义如下：

```
ContentInfo ::= SEQUENCE {
    contentType ContentType,
    content [0] EXPLICIT ANY DEFINED BY contentType }

ContentType ::= OBJECT IDENTIFIER
```

从本质上说，该结构提供了为特定结构标记对象标识符所需的全部。甚至为 `ContentInfo` 结构本身也有一个对象标识符：

```
id-ct-contentInfo OBJECT IDENTIFIER ::= { iso(1) member-body(2)
         us(840) rsadsi(113549) pkcs(1) pkcs9(9) smime(16) ct(1) 6 }
```

对于交换压缩、加密、签名或经过身份验证的消息，我们需要执行的大多数任务都定义了相应的标识符和结构。Bouncy Castle API 包含了与这些结构大部分功能等同的高级 API，以及可以用于处理构成结构的原始数据的 ASN.1 类（`ASN.1 classes`）。由于某些 CMS 结构可能非常大，API 支持内存模型和流式模型来创建和解析 CMS 结构。

CMS API 的包名为 `org.bouncycastle.cms`。我们将从最简单的结构开始，该结构仅用于包含通用数据。

### 数据内容 (Data Content)

数据内容类型由对象标识符 `id-data` 标识，其定义如下：

```
id-data OBJECT IDENTIFIER ::= { iso(1) member-body(2)
         us(840) rsadsi(113549) pkcs(1) pkcs7(7) 1 }
```

严格来说，`id-data` 可用于指示任何结构，因此它可以应用于特定应用程序的内容。尽管如此，`id-data` 的 `contentType` 通常为 `OCTET STRING`，内容中存在的任何额外结构都编码在组成 `contentType` 的字节流中。

Bouncy Castle 有两个处理内存数据的接口，以及一个支持流式数据的类。这些接口还提供了处理常见情况的默认实现。



对于内存使用，基本接口是 `CMSProcessable`，它与数据类型无关，仅由两个方法组成：一个需要实现以将数据写入输出流，另一个用于将内容作为 `Object` 返回。还扩展接口 `CMSTypeData`，它在需要时允许数据类型为 `id-data` 以外的类型，并包含一个额外方法 `getContentType()`，它返回表示内容类型的 `ASN1ObjectIdentifier`。默认实现由 `CMSProcessableByteArray` 和 `CMSProcessableFile` 提供，它们分别提供处理字节编码数据或文件的支持。这两个默认实现都拥有构造函数，允许在需要 `getContentType()` 返回除表示 `id-data` 的 `ASN1ObjectIdentifier` 之外的内容时指定您自己的内容类型。

## 签名数据内容 (SignedData Content)

`SignedData` 内容通过存在 `signed-data` 内容类型被指定在 `ContentInfo` 内部，其定义如下：

```
id-signedData OBJECT IDENTIFIER ::= { iso(1) member-body(2)
               us(840) rsadsi(113549) pkcs(1) pkcs7(7) 2 }
```

尽管名称 `SignedData` 暗示了如此，但 `SignedData` 并不一定包含被签名的数据，它可能只包含与签名相关的信息。当它不包含数据时（这是 S/MIME 中的常见情况），称 `SignedData` 与数据是分离的（detached）或外部的（external）。当 `SignedData` 结构不是分离的时，该结构还包含了被签名的数据，并描述为封装的（encapsulated）`SignedData`。

![使用两个签名者创建分离的 SignedData - 通常签名者详情是私钥和证书](img/chapter11----DetachedSignedData.png)

使用两个签名者创建分离的 SignedData - 通常签名者详情是私钥和证书

`SignedData` 结构具有以下 ASN.1 定义：

```
SignedData ::= SEQUENCE {
    version CMSVersion,
    digestAlgorithms DigestAlgorithmIdentifiers,
    encapContentInfo EncapsulatedContentInfo,
    certificates [0] IMPLICIT CertificateSet OPTIONAL,
    crls [1] IMPLICIT RevocationInfoChoices OPTIONAL,
    signerInfos SignerInfos }

DigestAlgorithmIdentifiers ::= SET OF DigestAlgorithmIdentifier

SignerInfos ::= SET OF SignerInfo
```

版本号可以是 1, 3, 4 或 5。按照测试顺序，版本号为：

- 如果 `SignedData` 包含“其他”证书和/或“其他”CRL（“其他”指的是 X.509 格式以外的证书/CRL），则为 5；
- 如果存在版本 2 属性证书，则为 4；
- 如果存在版本 1 属性证书、版本 3 `SignerInfo` 以及/或存在类型不为 `id-data` 的封装内容，则为 3。
- 如果上述均不适用，则为 1。

当 `SignedData` 结构也包含被签名的数据时，数据存储在 `encapContentInfo` 字段中。`EncapsulatedContentInfo` 的结构与 `ContentInfo` 。事实上，在 PKCS#7 的原始规范中，`encapContentInfo` 字段的类型为 `ContentInfo`。在 ASN.1 中，`EncapsulatedContentInfo` 定义如下：

```
EncapsulatedContentInfo ::= SEQUENCE {
    eContentType ContentType,
    eContent [0] EXPLICIT OCTET STRING OPTIONAL }
```

将 `eContent` 明确定义为字节字符串是 PKCS#7 和 CMS 区别。如果你需要处理任何遗留系统或数据，这一点值得——`eContent` 可能不是 `OCTET STRING` 类型，而是使用了原始的 `ContentInfo` 结构。当 `SignedData` 用于分离或外部签名时，`eContent` 字段缺失。

如名称所示，`digestAlgorithms` 字段包含了作为 `SignedData` 中存储签名基础的消息摘要的 `AlgorithmIdentifiers`。`certificates` 和 `crls` 字段如果存在，包含了证书和证书吊销列表。并不是所有这些内容都与存储数据中的签名相关，尽管通常对于每个 `SignerInfo` 至少有一个可以验证签名的证书。尽管 `SignedData` 的生成器没有义务这样做，RFC 5652 允许 `certificates` 和 `crls` 字段中的信息不完整甚至无关。

实际签名位于 `SignerInfo` 对象中，这些集合出现在 `SignedData` 结构中。注意它是一个集合，类似于 ASN.1 `SET`，在 ASN.1 中 `SET` 类型是无序的。如果有多个签名者，你不能依赖它们的顺序。

我们可以通过查看实际的 `SignerInfo` 结构看到如何处理这个问题：

```
SignerInfo ::= SEQUENCE {
    version CMSVersion,
    sid SignerIdentifier,
    digestAlgorithm DigestAlgorithmIdentifier,
    signedAttrs [0] IMPLICIT SignedAttributes OPTIONAL,
    signatureAlgorithm SignatureAlgorithmIdentifier,
    signature SignatureValue,
    unsignedAttrs [1] IMPLICIT UnsignedAttributes OPTIONAL }
```

`sid` 字段为我们提供了一种方法，将拥有的签名与可能拥有的签名者详情进行匹配。`sid` 字段确实是为 X.509 证书或公钥设计的，其定义如下：

```
SignerIdentifier ::= CHOICE {
     issuerAndSerialNumber IssuerAndSerialNumber,
     subjectKeyIdentifier [0] SubjectKeyIdentifier }
```

`IssuerAndSerialNumber` 是一个包含证书颁发者 `X.500` 名称以及该颁发者签署的证书序列号的序列，该证书包含了验证签名所需的公钥。如果该字段包含的是 `subjectKeyIdentifier` 而不是上述内容，则它是一个可以作为公钥索引的八字节字符串。我们在查看 `X.509` 证书扩展时也曾见过 `SubjectKeyIdentifier` 类型，且公钥证书通常也会将 `subjectKeyIdentifier` 作为扩展包含其中，这可以用于将 `SignerInfo` 中的签名与验证该签名所需的证书进行匹配。所使用的 `sid` 类型会影响存储在结构体开处的版本号。如果 `SignerIdentifier` 选择的是 `IssuerAndSerialNumber`，则版本号为 `1`；当 `SignerIdentifier` 为 `SubjectKeyIdentifier` 时，版本号为 `3`。

`SignatureValue` 仅仅是 `OCTET STRING`，它包含了实际签名，所使用的算法细节体现在 `signatureAlgorithm` 中。`signatureAlgorithm` 等同于我们已经过的普通 `AlgorithmIdentifier` 类型。

最后两个值得了解的字段是 `signedAttrs` 和 `unsignedAttrs`。它们具有相同的基础定义，定义如下：

```
SignedAttributes ::= SET SIZE (1..MAX) OF Attribute

UnsignedAttributes ::= SET SIZE (1..MAX) OF Attribute

Attribute ::= SEQUENCE {
    attrType OBJECT IDENTIFIER,
    attrValues SET OF AttributeValue }
```

在 `RFC 5652` 使用的旧版 ASN.1 中，`AttributeValue` 被定义为 `ANY`。当 `signedAttrs` 存在时，签名是对组成该字段的集合的 `DER` 编码计算的，`signedAttrs` 中将有一个属性包含与签名相关的任何数据（无论是封装的还是外部的）的哈希。如果 `signedAttrs` 不存在，则签名仅与签名关联的数据计算。`unsignedAttrs` 字段提供了一种在签名原始生成后引入要与签名存储的数据的方法，例如计数签名和时间戳就会出现在未签名属性中。

### 处理 SignedData 内容

在开始查看用于 `CMS SignedData` 的 Bouncy Castle API 之前，我们需要承认，创建这些结构至少需要一个签名密钥和一个用于验证签名的公钥证书。

为了简化示例，我们假设待签名消息以及私钥和签名证书已使用以下代码构建完成：

```java
byte[] msg = Strings.toByteArray("Hello, world!");

KeyPair selfSignedKp = generateECKeyPair();
X509CertificateHolder selfSignedCert =
    createTrustAnchor(selfSignedKp, "SHA256withECDSA");
```

注意，在在此设置中，证书是自签名的。在现实世界，如果签名方无法亲自向你提供公钥证书，你通常会预期证书是一个实体（end-entity）。

### 使用内存模型

`CMSSignedDataGenerator` 是创建 `SignedData` 的基础。处理 `SignedData` 有两种模型：一种是内存模型，假设数据可以很容易加载到内存中；另一种是基于流的，稍微难使用，因为你必须意识到自己所处的位置。我们将首先查看内存模型。

内存模型涉及四个步骤：

1. 我们为所需的算法使用 `ContentSigner`。
2. 我们为所需的摘要创建一个 `DigestCalculatorProvider`。
3. 我们使用 `ContentSigner` 和证书创建一个 `SignerInfoGenerator`。
4. 我们将 `SignerInfoGenerator` 添加到 `SignedDataGenerator` 中。

以下示例展示了这在实践中是如何运作的：

```java
/**
 * 创建 SignedData 结构。
 * @param signingKey 要生成的密钥。
 * @param signingCert 要验证的证书。
 * @param msg 原始数据
 * @param encapsulate 如果数据应该被封装，则为 true。
 * @return 一个创建的 CMSSignedData。
 */
public static CMSSignedData createSignedData(
    PrivateKey signingKey, X509CertificateHolder signingCert,
    byte[] msg, boolean encapsulate)
    throws CMSException, OperatorCreationException
{
    ContentSigner contentSigner =
        new JcaContentSignerBuilder("SHA256withECDSA")
            .setProvider("BC")
            .build(signingKey);

    DigestCalculatorProvider digestCalcProvider =
        new JcaDigestCalculatorBuilder().setProvider("BC").build();

    SignerInfoGenerator signerInfoGenerator =
        new SignerInfoGeneratorBuilder(digestCalcProvider)
            .build(contentSigner, signingCert);

    CMSSignedDataGenerator gen = new CMSSignedDataGenerator();

    gen.addSignerInfoGenerator(signerInfoGenerator);

    Store<X509CertificateHolder> certs =
        new CollectionStore<>(Collections.singletonList(signingCert));

    gen.addCertificates(certs);

    CMSProcessable typedMsg = new CMSProcessableByteArray(msg);

    return gen.generate(typedMsg, encapsulate);
}
```

虽然这种方法看起来有些繁琐，但这种方法的原因是允许混合使用 `ContentSigner` 和 `DigestCalculatorProvider` 对象。`ContentSigner` 和 `DigestCalculatorProvider` 都是接口，因此混合使用的意味着只需要符合接口的实现类即可与 `SignerInfoGenerator` 使用。如果涉及硬件加密适配器（如 HSM），这种能力就变得至关重要。HSM 通常仅具备签名能力，并且甚至可能不支持全面的 JCA 风格 API。

在最简单的情况下，如果 `ContentSigner` 和 `DigestCalculatorProvider` 都从同一个提供者创建，可以使用以下代码通过 `JcaSimpleSignerInfoGeneratorBuilder` 创建 `SignerInfoGenerator`，将上述前三个步骤合并为一个步骤：

```java
SignerInfoGenerator signerInfoGenerator =
    new JcaSimpleSignerInfoGeneratorBuilder()
        .setProvider("BC")
        .build("SHA256withECDSA", signingKey, signingCert);
```

`JcaSimpleSignerInfoGeneratorBuilder` 仍然会创建 `ContentSigner` 和 `DigestCalculatorProvider`，但它是内部使用配置的提供者，或者在没有通过 `setProvider` 方法指定特定提供者的情况下，使用 JVM 安全提供者优先级配置的适当提供者。

我们定义的 `createSignedData()` 方法允许我们创建一个 `SignedData` 结构，该结构可以封装被签名的数据，也可以作为离线式签名（detached signature）。

要创建一个包含封装数据的 `SignedData` 结构，我们可以使用之前所示的示例参数如下调用该方法：

```java
CMSSignedData encapSigned = createSignedData(selfSignedKp.getPrivate(),
                                             selfSignedCert, msg, true);
```

从 Bouncy Castle 的角度来看，验证 `CMSSignedData` 对象中持有的结构也涉及三个步骤：

- 我们向对象提供作为 `SignedData` 结构中签名源的原始数据。
- 我们找到与我们拥有的签名证书相关的 `SignerInformation` 实例。
- 我们使用 `SignerInformationVerifier` 使用签名证书对 `SignerInformation` 对象上的签名进行测试。

`SignerInformation` 类等同于 CMS 中定义的 `SignerInfo` 结构，它是 `CMSSignedDataGenerator` 通过使用提供的 `SignerInfoGenerator` 对象在内部生成的。我们可以通过使用 `SignerInfo` 中 `sid` 字段中 `SignerIdentifier` 包含的信息将证书与其关联的 `SignerInfo` 对象匹配。`SignerInformation.getSID()` 提供 `SignerIdentifier`，并用于搜索 `CMSSignedData.getCertificates()` 返回的 `Store`。

在我们所看的情况下，该结构既包含了验证所需的证书，也包含了数据，我们可以使用以下方法验证 `CMSSignedData`：



## 验证 CMS SignedData

### 封装式签名验证

```java
/**
 * 验证传入的 CMS SignedData 编码，假设为封装数据。
 *
 * @param encodedSignedData SignedData 的 BER 编码
 */
public static void verifySignedEncapsulated(byte[] encodedSignedData)
    throws CMSException, CertificateException, OperatorCreationException
{
    CMSSignedData signedData = new CMSSignedData(encodedSignedData);
    SignerInformationStore signers = signedData.getSignerInfos();
    Store certs = signedData.getCertificates();

    for (SignerInformation signerInfo : signers)
    {
        Collection<X509CertificateHolder> certCollection =
            certs.getMatches(signerInfo.getSID());
        X509CertificateHolder cert = certCollection.iterator().next();

        System.out.println("sig verified: " +
            signerInfo.verify(
                new JcaSimpleSignerInfoVerifierBuilder()
                    .setProvider("BC").build(cert)));
    }
}
```

除了 `SignerInformation` 类外，我们看到的另一个类是 `JcaSimpleSignerInfoVerifierBuilder`，它提供了与 `JcaSimpleSignerInfoGeneratorBuilder` 类类似的辅助。在需要更多灵活性的情况下，也可以通过 `SignerInformationVerifier` 类使用手动方法。

由于 `SignedData` 是完全自包含的，我们可以通过传递 `SignedData` 的编码来调用 `verify` 方法：

```java
verifySignedEncapsulated(encapSigned.getEncoded());
```

此时一个自然的问题是“为什么不总是这样做？”封装的 `SignedData` 的问题在于数据隐藏在对象的 ASN.1 编码中。我们仍然可以通过以下操作访问它：

```java
CMSTypedData cmsData = encapSigned.getSignedContent();
ByteArrayOutputStream bOut = new ByteArrayOutputStream();

cmsData.write(bOut);

System.out.println(Strings.fromByteArray(bOut.toByteArray()));
```

但在某些情况下，不封装被签名的数据，而是将与签名数据关联的签名作为离线式签名维护是很有用的。当我们在本章后续部分查看 S/MIME 时，将看到这种实际操作的示例。

### 离线式签名验证

除了不将签名数据封装在 `SignedData` 结构中，生成离线式签名与生成封装式签名基本相同。我们的 `createSignedData()` 方法已经具有创建离线式签名的能力，我们只需要为封装参数传递 `false`，并如下所示执行新的 `createSignedData()` 调用：

```java
CMSSignedData detachSigned = createSignedData(selfSignedKp.getPrivate(),
                                            selfSignedCert, msg, false);
```

变化的是验证签名所需的内容——在这种情况下，我们不能再假设拥有数据，必须单独传递它。这为我们提供了执行验证步骤的略有不同的方法：

```java
/**
 * 验证传入的 CMS SignedData 编码，假设为离线式
 * 签名，其中 msg 代表被签名的原始数据。
 *
 * @param encodedSignedData SignedData 的 BER 编码
 * @param msg 用于在 SignedData 中创建 SignerInfo 的数据
 */
public static void verifySignedDetached(byte[] encodedSignedData, byte[] msg)
    throws CMSException, CertificateException, OperatorCreationException
{
    CMSSignedData signedData = new CMSSignedData(
        new CMSProcessableByteArray(msg), encodedSignedData);

    SignerInformationStore signers = signedData.getSignerInfos();
    Store<X509CertificateHolder> certs = signedData.getCertificates();

    for (SignerInformation signerInfo : signers)
    {
        Collection<X509CertificateHolder> certCollection
            = certs.getMatches(signerInfo.getSID());
        X509CertificateHolder cert = certCollection.iterator().next();

        System.out.println("sig verified: " +
            signerInfo.verify(
                new JcaSimpleSignerInfoVerifierBuilder()
                    .setProvider("BC").build(cert)));
    }
}
```

唯一的区别在于 `CMSSignedData` 对象的构造方式。在调用方面，该方法只需要原始数据 (msg) 以及 SignedData 结构的编码。使用我们已经定义的示例参数，我们将如下所示调用方法：

```java
verifySignedDetached(detachSigned.getEncoded(), msg);
```

## 使用流式模型处理

PKCS#7 的原始理念之一是可以在 `SignedData` 结构中对任意大小的对象进行签名封装。Bouncy Castle API 通过提供额外的流式类也支持这一点：用于以流式方式生成 SignedData 结构的 `CMSSignedDataStreamGenerator`，以及用于以流式方式读取 SignedData 结构的 `SignedDataParser`。

首先查看生成。当使用流式模型创建 SignedData 结构时，我们仍然需要像以前一样传递证书和 SignerInfo 生成器。用法的变化在于写入要封装的数据。当我们准备好写入数据时，调用 `CMSSignedDataStreamGenerator` 的 `open()` 方法，并传递我们想要写入 SignedData 结构的目标流。在调用 `open()` 时，生成器将写入结构的导言，然后将写入 `open()` 返回流的数据继续写入 `SignedData` 结构中 `encapContentInfo` 字段分配的区域。一旦对 `open()` 返回的流调用了 `close()`，尾言（由证书/CRL 和 SignerInfos 组成）将被写入目标流，结构随之关闭。

以下示例使用流式方式创建一个 SignedData 结构，并使用了与之前的签名数据示例中相同的示例参数。

```java
/**
 * 使用流 API 创建 创建 SignedData 结构。
 *
 * @param signingKey 用于生成签名的密钥。
 * @param signingCert 用于验证 signingKey 签名的证书。
 * @param msg 原始消息数据
 * @return 包含已创建 SignedData 的 CMSSignedData。
 */
public static byte[] createSignedDataStreaming(
    PrivateKey signingKey, X509CertificateHolder signingCert, byte[] msg)
    throws CMSException, OperatorCreationException, IOException
{
    SignerInfoGenerator signerInfoGenerator =
        new JcaSimpleSignerInfoGeneratorBuilder()
            .setProvider("BC")
            .build("SHA256withECDSA", signingKey, signingCert);

    CMSSignedDataStreamGenerator gen = new CMSSignedDataStreamGenerator();

    gen.addSignerInfoGenerator(signerInfoGenerator);

    Store<X509CertificateHolder> certs =
        new CollectionStore<X509CertificateHolder>(
            Collections.singletonList(signingCert));

    gen.addCertificates(certs);

    ByteArrayOutputStream bOut = new ByteArrayOutputStream();

    OutputStream sOut = gen.open(bOut, true);

    sOut.write(msg);

    sOut.close();

    return bOut.toByteArray();
}
```

如果我们处理的是无法处理 CMS 算法保护属性的遗留服务，我们可能会移除 CMS 算法保护属性。我们希望不需要这样做，但示例引入的另一个内容是 `DefaultSignedAttributeTableGenerator`。如果你正在自定义签名属性，此类将为你生成所有标准属性。在用法方面，你可以扩展它，或者像示例代码中那样在内部使用它。通常你需要所有的标准属性，而你添加的内容取决于将如何处理你生成的 `SignedData` 结构的程序。

你可以使用类似的过程来添加未签名属性。默认情况下，未签名属性是空的，因此它们没有默认生成器。未签名属性用于诸如会签名等（我们将在接下来介绍这一点）以及使用时间戳协议（TSP）生成的时间戳（我们将在章节后续部分进一步介绍）。

## 添加会签名

除了能够对数据生成签名外，CMS 还允许生成可以作为现有签名者签名的会签名的签名。在 Bouncy Castle API 中实现此操作需要几个步骤。首先，我们需要将用于会签名者的 `SignerInfoGenerator` 对象添加到 `CMSSignedDataGenerator` 中，然后调用 `CMSSignedDataGenerator.generateCounterSigners()` 并传入代表我们想要会签名的签名者的 `SignerInformation` 对象。最后，在生成会签名者后，将它们添加到我们刚刚会签名的 `SignerInformation` 对象中以便稍后检索。

下面的示例方法显示了如何添加单个会签名，我们假设它始终与我们想要会签名的 `CMSSignedData` 关联的第一个 `SignerInformation`。

```java
/**
 * 更新 SignerInfo 以包含一个会签名。生成的
 * CMSSignedData 也将包含会签名者的证书。
 *
 * @param original 带有要会签名的 SignerInfo 的 SignedData。
 * @param counterSignKey 用于会签名的密钥。
 * @param counterSignCert 与 counterSignKey 关联的证书。
 * @return 一个带有会签名的更新后的 SignedData。
 */
public static CMSSignedData addCounterSignature(
    CMSSignedData original,
    PrivateKey counterSignKey, X509CertificateHolder counterSignCert)
    throws CMSException, OperatorCreationException
{
    SignerInfoGenerator signerInfoGenerator =
        new JcaSimpleSignerInfoGeneratorBuilder()
            .setProvider("BC")
            .build("SHA256withECDSA", counterSignKey, counterSignCert);

    CMSSignedDataGenerator gen = new CMSSignedDataGenerator();

    gen.addSignerInfoGenerator(signerInfoGenerator);

    SignerInformationStore signers = original.getSignerInfos();
    SignerInformation signerInfo = signers.iterator().next();

    signerInfo = SignerInformation.addCounterSigners(
        signerInfo, gen.generateCounterSigners(signerInfo));

    Collection originalCerts = original.getCertificates().getMatches(null);

    Set totalCerts = new HashSet();

    totalCerts.addAll(originalCerts);
    totalCerts.add(counterSignCert);

    CMSSignedData counterSigned = CMSSignedData.replaceSigners(
        original, new SignerInformationStore(signerInfo));

    counterSigned = CMSSignedData.replaceCertificatesAndCRLs(
        counterSigned, new CollectionStore(totalCerts), null, null);

    return counterSigned;
}
```

你可以通过查看 `generateCounterSigners()` 的返回值看到不同的会签名生成与普通 CMS SignedData 生成的不同之处 - 它返回一个 `SignerInformation` 对象的存储器。即使对与封装数据相关的签名者进行会签名，会签名也是在原始签名者的签名上生成的，并且只有在原始签名者的语境下查看时才有意义。



会签名可以像普通签名一样进行验证，通过调用包含它的 `SignerInformation` 对象上的 `verify()` 方法。Bouncy Castle 在 `CMSSignedData` 类上还有一个实例方法 `verifySignatures()`，你可以用它来验证包括会签名在内的所有 `SignerInfo` 结构。要使用它你需要提供 `SignerInformationVerifierProvider` 接口的实现。你将在下面的代码中看到如何实现：

```java
 1   /**
 2    * 验证 SignedData 结构中的所有 SignerInfos，包括任何
 3    * 会签名。
 4    *
 5    * @param signedData SignedData 结构的 BER 编码。
 6    */
 7   public static void verifyAllSigners(CMSSignedData signedData)
 8       throws CMSException
 9   {
10       final Store<X509CertificateHolder> certs = signedData.getCertificates();
 11 
12       System.out.println("signers verified: " + signedData.verifySignatures(
 13           new SignerInformationVerifierProvider()
 14           {
 15               SignerVerifier get(SignerId signerId)
 16                   throws OperatorCreationException
 17               {
 18                   try
 19                   {
 20                       X509CertificateHolder cert = (X509CertificateHolder)certs
 21                                       .getMatches(signerId).iterator().next();
 22                       
 23                       return new JcaSimpleSignerVerifierBuilder()
 24                                                 .setProvider("BC").build(cert);
 25                   }
 26                   catch (CertificateException e)
 27                   {
 28                       throw new OperatorCreationException(
 29                                "verifier provider failed: " + e.getMessage(), e);
 30                   }
 31               }
 32           }));
 33   }
```

你可以看到 `SignerInformationVerifierProvider` 接口有一个 `get()` 方法，它接受签名者标识作为参数并期望返回 `SignerInformationVerifier`。在我们的示例中，我们知道所有的证书都在提供的 `CMSSignedData` 对象中，因此我们可以围绕现有的证书创建验证器。正如我们之前警告过的，实际操作可能比这复杂。

接下来的代码片段是为了填补关于会签名者来源以及如何一起调用这两个方法的空白。你可以将其视为之前用于创建 `encapSigned` 对象的示例代码的延续。

```java
KeyPair counterKp = generateECKeyPair();
X509CertificateHolder counterCert =
    createTrustAnchor(counterKp, "SHA256withECDSA");

CMSSignedData counterSigned = addCounterSignature(encapSigned,
                                    counterKp.getPrivate(), counterCert);

verifyAllSigners(counterSigned);
```

你可以看到，用于会签名的凭据没有任何异常。在这种情况下，区别仅仅在于它们应用的方式 - 应用于 `SignerInfo` 而不是原始签名的数据。

### 处理签名属性编码不当的问题

偶尔你会看到看似正确的 `SignerInfo` 对象验证失败。假设所涉及的 `SignedData` 结构的创建者在其他方面都做得正确，这种失败的常见原因是他们忘记了对计算由签名者证书验证的签名时使用的签名属性进行 DER 编码。在这种情况下，DER 编码是非常重要的，因为属性位于一个 `SET` 中，这是一个无序类型，因此为了让 DER 编码始终产生相同的编码，在生成编码之前必须对构成属性的 `SET` 进行排序。

理想情况下，任何犯这种错误的人都会修复它，但有时这是不可行的，因此 Bouncy Castle API 允许创建一个自定义的 `SignerInformation` 类，允许对签名属性使用普通的定长编码。

你可以按照以下方式操作：

```java
 1 /**
 2  * 重写 SignerInformation 以停止在签名评估期间对签名属性进行 DER 排序
 3  *
 4  */
 5 public class SignerInfoUsingDefLength
 6     extends SignerInformation
 7 {
 8 
 9     protected SignerInfoUsingDefLength(SignerInformation baseInfo)
10     {
11         super(baseInfo);
12     }
13 
14     /**
15      * 重写以允许按 SignerInfo 中的原始形式返回编码后的属性
16      *
17      *
18      * @return 作为定长编码的签名属性。
19      * @throws IOException 当发生编码错误时。
20      */
21     public byte[] getEncodedSignedAttributes()
22         throws IOException
23     {
24         return signedAttributeSet.getEncoded(ASN1Encoding.DL);
25     }
26 }
```

不过，`ASN1Encoding.DL` 的使用并不是你应该经常接受的——DER 的初衷是提供一种可用于验证签名的唯一可能编码。`SET` 的定长编码没有说明元素的顺序，这种额外的灵活性可能会被想要更改 `SignerInfo` 中签名含义的人所利用。

### EnvelopedData 内容

EnvelopedData 用于承载加密信息。EnvelopedData 也包含在 `ContentInfo` 内部，其存在通过 enveloped-data 内容类型表示：

```asn
id-envelopedData OBJECT IDENTIFIER ::= { iso(1) member-body(2)
                us(840) rsadsi(113549) pkcs(1) pkcs7(7) 3 }
```

EnvelopedData 总是封装了已加密的数据，并具有以下 ASN.1 结构：

```asn
EnvelopedData ::= SEQUENCE {
    version CMSVersion,
    originatorInfo [0] IMPLICIT OriginatorInfo OPTIONAL,
    recipientInfos RecipientInfos,
    encryptedContentInfo EncryptedContentInfo,
    unprotectedAttrs [1] IMPLICIT UnprotectedAttributes OPTIONAL }
```

与 `SignedData` 一样，版本号根据 `EnvelopedData` 的内容变化。如果 `originatorInfo` 字段包含“其他”证书或“其他”CRL（这里的“其他”指非 X.509 格式），则版本号为 4。如果 `originatorInfo` 字段包含版本 2 属性证书或密码或存在“其他”接收者，则版本号为 3。如果 `originatorInfo` 缺失且 `unprotectedAttrs` 缺失且所有 `recipientInfos` 的成员都是版本 0，则版本号为 0。假设上述情况都不适用，则版本号为 2。

`originatorInfo`（如果存在）和 `recipientInfos` 字段带有有关 `EnvelopedData` 发送者及其预期接收者的信息。这些字段具有以下 ASN.1 类型定义：

```asn
OriginatorInfo ::= SEQUENCE {
    certs [0] IMPLICIT CertificateSet OPTIONAL,
    crls [1] IMPLICIT RevocationInfoChoices OPTIONAL }

RecipientInfos ::= SET SIZE (1..MAX) OF RecipientInfo
```

`OriginatorInfo` 包含可选字段，其定义与我们之前在 `SignedData` 中看到的相同。假设你是 `EnvelopedData` 的预期接收者之一，理想情况下，如果存在，`OriginatorInfo` 结构将包含足够的信息，使你能够向原始发送者发送加密回复。RFC 5652 确实允许 `originatorInfo` 字段中存储的信息是不完整的或与实际发送者无关的。

`RecipientInfos` 正如定义所示，是能够解密信封数据的接收者使用的细节集。`RecipientInfo` 类型是一个 `CHOICE`，具有以下定义：

```asn
RecipientInfo ::= CHOICE {
    ktri KeyTransRecipientInfo,
    kari [1] KeyAgreeRecipientInfo,
    kekri [2] KEKRecipientInfo,
    pwri [3] PasswordRecipientInfo,
    ori [4] OtherRecipientInfo }
```

我们稍后将进一步查看一些不同的 `RecipientInfo` 选项，但现在最有用的一点是，每个选项都预期包含一个 `EncryptedKey` 类型，该类型编码并封装用于加密信封数据的对称密钥，其使用的算法应该适用于 `RecipientInfo` 针对的接收者。`EncryptedKey` 类型仅仅是一个字节数组，并具有以下定义：

```asn
EncryptedKey ::= OCTET STRING
```

除了加密密钥，每个 `RecipientInfo` 结构内部通常还有一个接收者标识符（RID）。这允许接收者识别应该使用哪一个 `RecipientInfo` 来解密密钥，从而恢复被加密的数据。

`encryptedContentInfo` 字段包含了尝试保护的数据。其类型具有以下 ASN.1 定义：

```asn
EncryptedContentInfo ::= SEQUENCE {
    contentType ContentType,
    contentEncryptionAlgorithm ContentEncryptionIdentifier,
    encryptedContent [0] IMPLICIT EncryptedContent OPTIONAL }

EncryptedContent ::= OCTET STRING
```

你可以看到该类型非常基础。它包含了足够的信息，允许接收者获取 `RecipientInfo` 中的加密密钥，解密它，然后使用 `contentEncryptionAlgorithm`（最终是一个普通的 `AlgorithmIdentifier`）创建一个可用于恢复数据的密器。

![EnvelopedData - 数据密钥在内部生成并被接收者封装](img/chapter11----EnvelopedData.png)

EnvelopedData - 数据密钥在内部生成并被接收者封装

最后，`EnvelopedData` 有一个 `unprotectedAttrs` 字段，用于与受保护的数据关联附加属性。该字段使用了 `SignedData` 相同的 `Attribute` 类型，并具有以下 ASN.1 定义：

```asn
UnprotectedAttributes ::= SET SIZE (1..MAX) OF Attribute
```

#### 处理 EnvelopedData 内容

现在我们将查看使用 CMS API 创建并处理 EnvelopedData。为了简单起见，每个部分的代码都假设以下内容已经定义：

```java
JcaX509CertificateConverter converter =
         new JcaX509CertificateConverter().setProvider("BC");

byte[] msg = Strings.toByteArray("Hello, world!");

CMSEnvelopedDataGenerator envGen = new CMSEnvelopedDataGenerator();
```

我们使用 `CMSEnvelopedDataGenerator` 是因为我们将首先使用内存模型进行生成和解析。Bouncy Castle API 中的 EnvelopedData 支持也包括流式模型。接收者生成在内存和流式模型中都是相同的，因此虽然不同模型在生成和解析 EnvelopedData 方面存在差异，但接收者的生成和使用本质上是相同的。在我们回顾了所有可用接收者类型后，我们将查看流式模型。

对于内存模型，假设已添加一些 `RecipientInfo` 生成器，`CMSEnvelopedDataGenerator` 对象在调用 `generate()` 方法时会返回一个 `CMSEnvelopedData` 对象。

```java
CMSEnvelopedData envData = envGen.generate(
         new CMSProcessableByteArray(msg),
         new JceCMSContentEncryptorBuilder(CMSAlgorithm.AES256_CBC)
             .setProvider("BC")
             .build());
```

随后我们可以通过调用 `CMSEnvelopedData` 对象的 `getEncoded()` 方法来恢复 `enveloped-data` 结构的 BER 编码，如下所示：

```java
CMSEnvelopedData envData = envGen.generate(
         new CMSProcessableByteArray(msg),
         new JceCMSContentEncryptorBuilder(CMSAlgorithm.AES256_CBC)
             .setProvider("BC")
             .build());
```

现在我们将查看一些支持的接收者类型。

## ktri - KeyTransRecipientInfo 的选择

当 `RecipientInfo` 基于密钥传输传输机制（例如在使用 `RSA` 等算法时使用的机制）时，会选择 `ktri` 值。

它具有简单的 ASN.1 结构，反映了它本质上是使用对称密钥进行密钥封装（key wrap），而不仅仅是对称密钥。从下面可以看到，它允许使用两种方法来识别接收者（Recipient），这就像我们在 `SignerInfo` 中看到的那样。

```asn
KeyTransRecipientInfo ::= SEQUENCE {
    version CMSVersion,  -- 始终设置为 0 或 2
    rid RecipientIdentifier,
    keyEncryptionAlgorithm KeyEncryptionAlgorithmIdentifier,
    encryptedKey EncryptedKey }

RecipientIdentifier ::= CHOICE {
    issuerAndSerialNumber IssuerAndSerialNumber,
    subjectKeyIdentifier [0] SubjectKeyIdentifier }
```

在 `RecipientIdentifier` 为 `IssuerAndSerialNumber` 的情况下，`version` 字段被设置为 0，否则设置为 2。

以下方法展示了如何使用 `OAEP` 作为对称密钥封装的编码机制，基于 `RSA` 添加一个接收者。



## 向 EnvelopedData 生成器添加 KeyTransRecipientInfo

```java
 1   /**
 2    * 向传入的 enveloped-data 生成器中添加一个 KeyTransRecipientInfo。
 3    *
 4    * @param envGen 要添加 KeyTransRecipientInfo 的生成器。
 5    * @param encryptionCert 目标接收者的公钥证书。
 6    */
 7   public static void addKeyTransRecipient(
 8           CMSEnvelopedGenerator envGen,
 9           X509Certificate encryptionCert)
10   throws GeneralSecurityException
11   {
 12       JcaAlgorithmParametersConverter paramsConverter =
 13                                           new JcaAlgorithmParametersConverter();
 14 
 15       AlgorithmIdentifier oaepParams = paramsConverter.getAlgorithmIdentifier(
 16           PKCSObjectIdentifiers.id_RSAES_OAEP,
 17           new OAEPParameterSpec("SHA-256",
 18               "MGF1", new MGF1ParameterSpec("SHA-256"),
 19               PSource.PSpecified.DEFAULT));
 20 
 21       envGen.addRecipientInfoGenerator(
 22           new JceKeyTransRecipientInfoGenerator(
 23               encryptionCert, oaepParams).setProvider("BC"));
 24   }
```

该示例引入了 `JcaAlgorithmParametersConverter`，这是一个转换 `AlgorithmParameters` 对象或 `AlgorithmParametersSpec` 对象的工具类。

## 使用 RecipientInformation 恢复密钥

使用 `RecipientInformation` 来恢复被封装的密钥密钥。

正如我们在创建 `RecipientInfo` 时使用证书为接收者提供标识符一样，我们也可以使用证书创建一个 `JceKeyTransRecipientId`，它可以用于查找与我们的证书关联的 `KeyRecipientInfo`。在 Bouncy Castle API 中，这些对象是 `RecipientInformation` 类型，假设我们为该证书找到了一个，就可以调用 `RecipientInformation.getContent()` 方法并传递一个使用我们私钥创建的 `Recipient`。随后，`RecipientInformation` 对象内部使用我们的 `Recipient` 对象来恢复包含在其 `KeyTransRecipientInfo` 结构中的封装密钥密钥，并解密封装在 `CMSEnvelopedData` 对象中的加密数据。

以下代码行展示了一个简单的示例，应用 `extractUsingKeyTransRecipient()` 方法从我们生成的 EnvelopedData 结构的 BER 编码中恢复并打印测试消息。

```java
byte[] keyTransRecovered = extractUsingKeyTransRecipient(
      envEnc, recipientRsaKp.getPrivate(), recipientRsaCert);

System.err.println(Strings.fromByteArray(keyTransRecovered));
```

假设你使用的是之前提供的测试消息并且正确添加了 `KeyTransRecipientInfo`，如果你运行上述代码，你应该会在控制台上看到字符串：

```
Hello, world!
```

输出到控制台。

## kari - KeyAgreeRecipientInfo 的选择

当 `RecipientInfo` 基于密钥协商机制时（例如在 `Diffie-Hellman`、`MQV` 或 `Unified Diffie-Hellman` 等算法时使用的），会选择 `kari` 值。

以下方法展示了如何基于 EC 因子 Diffie-Hellman 添加一个接收者，其中约定的密钥为 256 位的 AES 封装密钥：

```java
 1   /**
 2    * 向传入的 enveloped-data 生成器添加一个 KeyAgreeRecipientInfo。
 3    *
 4    * @param envGen the generator to add the KeyAgreeRecipientInfo to.
 5    * @param initiatorKey the private key for the enveloped-data originator.
 6    * @param initiatorCert the public key certificate for the originator.
 7    * @param recipientCert the public key certificate for the targeted recipient.
 8    */
 9   public static void addKeyAgreeRecipient(
10       CMSEnvelopedGenerator envGen,
11       PrivateKey initiatorKey, X509Certificate initiatorCert,
12       X509Certificate recipientCert)
13   throws GeneralSecurityException
14   {
15       envGen.addRecipientInfoGenerator(
16           new JceKeyAgreeRecipientInfoGenerator(
17               CMSAlgorithm.ECCDH_SHA384KDF,
18               initiatorKey,
19               initiatorCert.getPublicKey(),
20               CMSAlgorithm.AES256_WRAP)
21               .addRecipient(recipientCert).setProvider("BC"));
22   }
```

密钥协商案例与我们之前看到的密钥传输案例之间有两个主要区别。第一个是需要提供 `RecipientInfo` 创建者的公钥，且协商过程产生一个约定的值，而不是直接加密数据块。第二个是由于我们产生的是约定的值，还需要指定一个对称封装算法，以便使用该约定值来封装用于加密被封装数据的密钥。这种对约定值的二级使用值得赞赏，因为这意味着密钥协商接收者也可以出现在带有任何其他接收者的消息中。对于加密数据而言，每个人都需要恢复相同的密钥，只是用于封装密钥的机制不同。

我们可以从用于定义 `KeyAgreeRecipientInfo` 结构的 ASN.1 内容中看到这些差异是如何体现：

```asn1
KeyAgreeRecipientInfo ::= SEQUENCE {
    version CMSVersion,  -- always set to 3
    originator [0] EXPLICIT OriginatorIdentifierOrKey,
    ukm [1] EXPLICIT UserKeyingMaterial OPTIONAL,
    keyEncryptionAlgorithm KeyEncryptionAlgorithmIdentifier,
    recipientEncryptedKeys RecipientEncryptedKeys }

OriginatorIdentifierOrKey ::= CHOICE {
    issuerAndSerialNumber IssuerAndSerialNumber,
    subjectKeyIdentifier [0] SubjectKeyIdentifier,
    originatorKey [1] OriginatorPublicKey }

OriginatorPublicKey ::= SEQUENCE {
    algorithm AlgorithmIdentifier,
    publicKey BIT STRING }

RecipientEncryptedKeys ::= SEQUENCE OF RecipientEncryptedKey

RecipientEncryptedKey ::= SEQUENCE {
    rid KeyAgreeRecipientIdentifier,
    encryptedKey EncryptedKey }

KeyAgreeRecipientIdentifier ::= CHOICE {
    issuerAndSerialNumber IssuerAndSerialNumber,
    rKeyId [0] IMPLICIT RecipientKeyIdentifier }

RecipientKeyIdentifier ::= SEQUENCE {
    subjectKeyIdentifier SubjectKeyIdentifier,
    date GeneralizedTime OPTIONAL,
    other OtherKeyAttribute OPTIONAL }
```

`originator` 字段是一个 `CHOICE` 类型，这为接收者提供了几种恢复其所需的发送者公钥的方法，同时通过使用 `OriginatorPublicKey` 选择允许消息的实际发送者保持匿名。`ukm` 字段提供的数据可以确保在在使用静态密钥时，同一两个双方之间的任何两次密钥协商都不会生成相同的封装密钥。`keyEncryptionAlgorithm` 字段描述了用于创建加密密钥的封装算法。最后，你可能会注意到 `KeyAgreeRecipientInfo` 中可以包含多个接收者密钥。Bouncy Castle API 支持这一点，这也是为什么在 `JceKeyAgreeRecipientInfoGenerator` 中使用 `addRecipient()` 方法来传递接收者详情，而不是通过构造函数完成的原因。

在我们目前的示例中，我们只考虑一个接收者，因此以下代码片段就足够使用 `addKeyAgreeRecipient()` 方法了：

```java
KeyPair originatorEcKp = generateECKeyPair();
X509Certificate originatorEcCert = converter.getCertificate(
    createTrustAnchor(originatorEcKp, "SHA256withECDSA"));

KeyPair recipientEcKp = generateECKeyPair();
X509Certificate recipientEcCert = converter.getCertificate(
    createTrustAnchor(recipientEcKp, "SHA256withECDSA"));

addKeyAgreeRecipient(envGen,
         originatorEcKp.getPrivate(), originatorEcCert, recipientEcCert);
```

如你看到的示例调用代码，与密钥传输的示例代码不同，它必须生成两个密钥对和两个证书，因为消息发送者的密钥对详情至关重要。这从两个角度考虑：一方面是发起者需要计算初始共享密钥，并由此计算出用于保护数据加密密钥的封装密钥；另一方面是接收者本身，因为他们需要发送者的公钥与自己的私钥结合，以进行自己的共享值计算。

另一方面，接收者用于恢复原始数据传递的参数与你在密钥传输案例中看到的相同：

```java
 /**
   * 使用接收者参数从 EnvelopedData
   * 结构中提取加密的原始数据。
   *
   * @param encvelopedData BER 编码的 EnvelopedData。
   * @param recipientKey 接收者私钥（用于协商）。
   * @param recipientCert 接收者对应的证书。
   * @return 封装的原始数据数组。
   */
  public static byte[] extractUsingKeyRecipient(
      byte[] encEnvelopedData,
      PrivateKey recipientKey, X509Certificate recipientCert)
  throws CMSException
  {
      CMSEnvelopedData envelopedData = CMSEnvelopedData(encEnvelopedData);
      RecipientInformationStore recipients = envelopedData.getRecipientInfos();
      RecipientId rid = new JceAgreeRecipientId(recipientCert);
      RecipientInformation recipient = recipients.get(rid);

      return recipient.getContent(
          new JceAgreeEnvelopedRecipient(recipientKey).setProvider("BC"));
  }
```

大部分代码相同，只是使用了不同的 `RecipientId`（`JceAgreeRecipientId`）以及不同的接收者类型（`JceAgreeEnvelopedRecipient`）。

```java
byte[] keyAgreeRecovered = extractUsingKeyRecipient(
         envEnc, recipientEcKp.getPrivate(), recipientEcCert);

System.err.println(Strings.fromByteArray(keyAgreeRecovered));
```

假设你使用的是之前的测试消息并正确添加了 `KeyAgreeRecipientInfo`，运行上述代码你应该看到字符串：

```
Hello, world!
```

你也可以尝试将此示例与之前的密钥传输示例相结合，你会发现这两种机制可以很方便地在同一个 `EnvelopedData` 结构中使用。

### kekri - KEKRecipientInfo 选择

当 `RecipientInfo` 基于对称密钥加密密钥（KEK）机制（例如 AES KWP）时，会选择 `kekri` 值。

KEK 接收使用以下 ASN.1 定义：

```asn1
KEKRecipientInfo ::= SEQUENCE {
    version CMSVersion,  -- always set to 4
    kekid KEKIdentifier,
    keyEncryptionAlgorithm KeyEncryptionAlgorithmIdentifier,
    encryptedKey EncryptedKey }

KEKIdentifier ::= SEQUENCE {
    keyIdentifier OCTET STRING,
    date GeneralizedTime OPTIONAL,
    other OtherKeyAttribute OPTIONAL }
```

此 `RecipientInfo` 比密钥协商版本要简单得多，并且与 `KeyTransRecipientInfo` 的定义方式有更多共同点——这并不意外，因为 `KEK` 只是一个对称封装操作，而不是非对称操作。通常，`KEKIdentifier` 仅由一个 `OCTET STRING` 组成，我们在后文的方法中添加 `KEK` 接收者也是这种这种。`RFC 5652` 出于操作性考虑，建议不要使用 `OtherKeyAttribute`。

以下是一个添加 KEK 接收者生成器的方法：



## 代码示例：添加 KEKRecipientInfo

```java
/**
 * 将 KEKRecipientInfo 添加到传入的封装数据（enveloped-data）生成器中。
 *
 * @param envGen 要添加 KEKRecipientInfo 的生成器。
 * @param keyID 用于匹配接收者的存储 keyID。
 * @param wrappingKey 与 keyID 对应的封装密钥。
 */
public static void addKEKRecipient(
    CMSEnvelopedGenerator envGen,
    byte[] keyID, SecretKey wrappingKey)
{
    envGen.addRecipientInfoGenerator(
        new JceKEKRecipientInfoGenerator(keyID, wrappingKey)
            .setProvider("BC"));
}
```

为了使用该方法，我们需要代码来提供密钥标识符以及我们希望用于封装的对称密钥。`RecipientInfo` 生成器将选择一个适用于传入对称密钥的标准密钥封装算法。例如在用例中：

```java
byte[] keyID = Strings.toByteArray("KeyID");
SecretKey wrappingKey = new SecretKeySpec(
                Hex.decode("000102030405060708090a0b0c0d0e0f"), "AES");
addKEKRecipient(envGen, keyID, wrappingKey);
```

密钥封装算法将是 `AES KW`。

由于 `EnvelopedData` 中的 `RecipientInfo` 带有密钥标识符，提取原始数据只需要提供正确的密钥标识符以定位正确的 `RecipientInfo`，并提供正确的对称密钥来执行检索原始数据所需的解封装（key unwrap）操作。

以下提供了一个使用 `KEK` 密钥及其密钥标识符提取提取的示例。查看代码你会发现，虽然它没有使用公钥/私钥，但该方法仍然遵循我们为其他接收者类型建立的模式。

```java
/**
 * 使用匹配传入参数的接收者，从 EnvelopedData
 * 结构中提取加密的原始数据。
 *
 * @param encEnvelopedData BER 编码的 EnvelopedData 结构。
 * @param keyID 匹配接收者的 keyID。
 * @param wrappingKey 与 keyID 对应的封装密钥。
 * @return 封装为 byte[] 的原始数据。
 */
public static byte[] extractUsingKEKRecipient(
    byte[] encEnvelopedData,
    byte[] keyID, SecretKey wrappingKey)
    throws CMSException
{
    CMSEnvelopedData envelopedData = new CMSEnvelopedData(encEnvelopedData);
    RecipientInformationStore recipients = envelopedData.getRecipientInfos();
    RecipientId rid = new KEKRecipientId(keyID);
    RecipientInformation recipient = recipients.get(rid);

    return recipient.getContent(
        new JceKEKEnvelopedRecipient(wrappingKey)
            .setProvider("BC"));
}
```

最后的片段仅展示了如何调用提取方法。

```java
byte[] kekRecovered = extractUsingKEKRecipient(envEnc, keyID, wrappingKey);

System.err.println(Strings.fromByteArray(kekRecovered));
```

运行时，它应该再次显示“Hello, world!”消息。

本节的示例代码也可以与之前的示例结合，你会发现我们到为止讨论的所有接收者类型都可以组合在单个消息中。

## pwri - 密码 RecipientInfo 的选择

当 `RecipientInfo` 基于 PBE（密码保护加密）的密钥封装机制时，会选择 `pwri` 值。

此 `RecipientInfo` 与用于 `KEK` 的那个区别在于，它携带的是密钥派生算法而不是密钥标识符。`PasswordRecipientInfo` 的 `ASN.1` 定义如下：

```
PasswordRecipientInfo ::= SEQUENCE {
    version CMSVersion,   -- 始终设置为 0
    keyDerivationAlgorithm [0] KeyDerivationAlgorithmIdentifier OPTIONAL,
    keyEncryptionAlgorithm KeyEncryptionAlgorithmIdentifier,
    encryptedKey EncryptedKey }
```

以下方法展示了如何向生成器添加基于密码的 RecipientInfo：

```java
/**
 * 将 PasswordRecipientInfo 添加到传入的封装数据（enveloped-data）生成器中。
 *
 * @param envGen 要添加 PasswordRecipientInfo 的生成器。
 * @param passwd 用作 PBE 密钥基础的密码。
 * @param salt 用于生成 PBE 密钥的盐值（salt）。
 * @param iterationCount 用于生成 PBE 密钥的迭代次数。
 */
public static void addPasswordRecipient(
    CMSEnvelopedGenerator envGen,
    char[] passwd,
    byte[] salt,
    int iterationCount)
{
    envGen.addRecipientInfoGenerator(
        new JceRecipientInfoGenerator(CMSAlgorithm.AES256_CBC, passwd)
            .setProvider("BC")
            .setPasswordScheme(PasswordRecipient.PKCS5_SCHEME_UTF8)
            .setPRF(PasswordRecipient.HmacSHA8)
            .setSaltAndIterationCount(salt, iterationCount));
}
```

使用的 PBE 方案最初在 `RFC 3211` 中推荐，也称为 `PBKDF2`。从 `ASN.1` 和示例可以看出，接收者可以用来识别以选择处理的接收者的标识符是 `pwri`。这个问题并不意味着在单个 EnvelopedData 消息中不能有多个基于 PBE 的 RecipientInfo，但意味着检查接收者的唯一方法是解密存储在 `RecipientInfo` 结构中的密钥。

你可以使用以下代码调用 `addPasswordRecipient()` 方法：

```java
char[] passwd = "password".toCharArray();

addPasswordRecipient(envGen, passwd, Strings.toByteArray("Salt"), 2048);
```

```java
byte[] passwordRecovered = extractUsingPasswordRecipient(envEnc, passwd);

System.err.println(Strings.fromByteArray(passwordRecovered));
```

和之前一样，假设使用相同的样本数据，如果一切顺利，你将看到“Hello, world!”。

## 使用流式模型

对于非常大的数据块 `EnvelopedData`，例如 `SignedData`，也可以流式模型进行创建和处理。如果你计划使用流式模型，则需要使用 `CMSEnvelopedStreamGenerator` 类，可以通过以下方式创建它：

```java
CMSEnvelopedDataStreamGenerator envStreamGen =
                                new CMSEnvelopedDataStreamGenerator();
```

向 `CMSEnvelopedStreamGenerator` 添加接收者生成器与向 `CMSEnvelopedDataGenerator` 添加相同，这两个类都继承自 `CMSEnvelopedGenerator`，你可能已经注意到 `CMSEnvelopedGenerator` 是所有添加接收者方法中使用的类。由于事实是如此，虽然我们下面只查看 `KeyTransRecipientInfo` 的用法，但相同的规则也适用于我们看过的其他 `RecipientInfo` 类型。

如你在下面的代码片段所示，`addKeyTransRecipient()` 方法的使用方式与之前相同，但待加密数据添加到 `EnvelopedData` 结构的方式不同。

```java
addKeyTransRecipient(envStreamGen, recipientRsaCert);

ByteArrayOutputStream bOut = new ByteArrayOutputStream();
OutputStream out = envStreamGen.open(
    bOut,
    new JceCMSContentEncryptorBuilder(CMSAlgorithm.AES256_CBC)
        .setProvider("BC")
        .build());

out.write(msg);

out.close();

envEnc = bOut.toByteArray();
```

在添加数据方面，关键代码是调用 `envStream.open()`。传递给 `open()` 方法的 `OutputStream` 最终是 `EnvelopedData` 结构编码的地方。在示例中，我们使用了 `ByteArrayOutputStream`，因此我们可以在片段末尾通过调用 `bOut.toByteArray()` 获取 `EnvelopedData` 的编码。

> **注意**：我们只在调用 `out.close()` 之后调用 `bOut.toByteArray()` —— 关闭 `open()` 返回的 `OutputStream` 可确保 `EnvelopedData` 编码被正确结束。

提取方法看起来与我们之前看到的使用 `KeyTransInfo` 接收者时提取加密数据的等效方法非常相似。我们使用 `CMSEnvelopedDataParser` 而不是内存中的 `CMSEnvelopedData` 对象来读取 `EnvelopedData`，如下：

```java
/**
 * 从 EnvelopedData 结构中提取加密的原始数据
 * 使用与传入参数匹配的接收者以及
 * CMS 流式模型。
 *
 * @param encEnvelopedData BER 编码的 EnvelopedData 结构。
 * @param privateKey 接收者私钥（用于密钥传输）。
 * @param encryptionCert 接收者对应的公钥证书。
 * @return 封装为 byte[] 的原始数据。
 */
public static CMSTypedStream streamExtractUsingKeyTransRecipient(
    byte[] encEnvelopedData,
    PrivateKey privateKey, X509Certificate encryptionCert)
    throws CMSException, IOException
{
    CMSEnvelopedDataParser envelopedData
                            = new CMSEnvelopedDataParser(encEnvelopedData);
    RecipientInformationStore recipients = envelopedData.getRecipientInfos();
    RecipientInformation recipient = recipients.get(
                                new JceKeyTransRecipientId(encryptionCert));

    if (recipient != null)
    {
        return recipient.getContentStream(
                new JceKeyTransEnvelopedRecipient(privateKey)
                    .setProvider("BC"));
    }

    throw new IllegalArgumentException("recipient for certificate not found");
}
```

虽然我们在示例方法中使用了 `getContentStream()` 方法，但实际上我们也可以像之前那样使用 `getContent()`。在这种情况下，我们没有这样做是为了保留处理包含比 JVM 内存能容纳的更多数据的结构所需的条件。使用 `getContentStream()` 确实改变了我们习惯的方法返回类型，并且如果我们要成功生成“Hello, world!”字符串，就需要以稍微不同的方式进行处理。使用 `getContentStream()` 时需要以下代码：

```java
CMSTypedStream cmsContent = streamExtractUsingKeyTransRecipient(
        envEnc, recipientRsaKp.getPrivate(), recipientRsaCert);

System.err.println(Strings.fromByteArray(
                        Streams.readAll(cmsContent.getContentStream())));
```

注意，如果我们继续使用 `getContent()`，`RecipientInformation` 对象将执行与我们在上面代码片段中相同的操作。还要注意，在流式模型中，由于 `unprotectedAttrs` 字段位于加密内容之后，如果你使用流式模型，则需要完全读取内容或预先排空流。

## S/MIME

Secure MIME（或 S/MIME）提供了安全发送 MIME 数据的方法，并考虑了在不同 MIME 类型之间可能发生的传输问题。Bouncy Castle 中用于 S/MIME 的当前 API 基于 RFC5751，该标准描述了 S/MIME 3.2 版本并于 2010 年发布。S/MIME 最常用于创建签名和/或加密邮件，你很有可能已经在收件箱中见过 S/MIME 创建的消息了。S/MIME 的密码学部分基于加密消息语法（Cryptographic Message Syntax），即我们刚刚查看的协议。

Bouncy Castle 现在有两个处理 S/MIME 的 API：一个是利用 JavaMail 的原始 API，另一个是较新的 API，它可以直接解析 MIME 文件而不需要 JavaMail。这两个 API 都有其用处，因此我们将查看各自的示例。如果你打算使用 JavaMail 版本（位于 Bouncy 分发包中的 `bcmail-*` jar 文件），熟悉 JavaMail 也会有帮助。虽然你可以在不熟悉 JavaMail 的情况下让示例运行，但对 JavaMail API 的知识将使你能够更有效地应用和修改这里的示例。

### S/MIME 签名消息

S/MIME 中的签名消息有两种格式。`multipart/signed` 消息是 S/MIME 签名最常用的格式。消息由两部分组成：第一部分是签名内容，第二部分是分离签名，它提供了 `SignerInfo` 结构，用于验证第一部分数据的完整性。



# S/MIME 封装签名数据与 Multipart/signed 处理

## S/MIME 封装签名数据

S/MIME 也支持封装的签名数据，它出现在单个正文部分。这种格式很少使用，因为它导致无法读取签名数据。封装消息的 MIME 类型为 `application/pkcs7-signature`（在某些情况下为 `application/x-pkcs7-signature`），以 CMS 的原始标准 PKCS#7 命名。如果你遇到这种消息，你会发现消息只是一个 ASN.1 块，通常使用 Base64 编码，以避免在可能无法处理的邮件网关上传输二进制数据时出现问题。

虽然 Bouncy Castle API 支持这两种签名消息类型，但在这里我们只查看最常见的 `multipart/signed`。这是一个值得关注的内容，因为它通常需要对文本数据进行规范化，无论是用于创建签名还是验证签名。我们之所以说通常，是因为普通的 S/MIME 由于默认传输编码是 7 位而需要规范化，但 AS2 等标准的默认传输编码是二进制，因此并不总是需要规范化。

规范化过程因媒体类型而异，大多数情况下只有一种形式，但如果你处理的是特殊的媒体类型，最好检查是否应用了规范化过程。对于我们的目的而言，最需要注意的是主要媒体类型为 `text` 的实体。对于像 `text/plain` 类型的数据，文件中的行尾必须全部是 `\r\n` 格式，且使用的字符集应该是 IANA“字符集”文档中列出的标准 IANA 字符之一 [52]。

除了规范化之外，某些邮件网关仍然会对 MIME 消息进行其他奇怪且意料之外的操作。如果你发现签名在明明看起来可以工作的情况下却不断失败（例如，你已经考虑了规范化），其他需要寻找的“趣味”点包括删除行末最后一个非空字符与行尾字符之间的空白符，以及用同一特殊字符的不同编码来替换特殊字符——这可能发生在字符集对同一字符支持多种编码的情况下。在这样的情况下，你会发现你可能需要自己拟定一些规范化规则。

## 测试数据与密钥设置

在开始示例之前，我们需要设置一些密钥和一条示例消息。

以下是我们的示例消息的定义：

```
byte[] bodyPart = Strings.toByteArray(
             "Content-Type: text/plain; name=null; charset=us-ascii\r\n" +
                 "Content-Transfer-Encoding: 7bit\r\n" +
                 "Content-Disposition: inline; filename=test.txt\r\n" +
                 "\r\n" +
                 "Hello, world!\r\n");
```

该消息已经是规范化格式，全处使用 `\r\n` 作为行尾。

意不意外的是，由于我们从根本上是在做 CMS，密钥和证书的设置与之前完全相同：

```
KeyPair selfSignedKp = generateECKeyPair();
      X509CertificateHolder selfSignedCert =
          createTrustAnchor(selfSignedKp, "SHA256withECDSA");
```

最后，我们将添加的另一部分代码与 S/MIME 的另一个功能有关——S/MIME 能力。这是一个可以包含在与签名数据分离签名相关的 `SignerInfo` 属性中的额外属性。

与 S/MIME 能力属性相关的 ASN.1 定义如下：

```
smimeCapabilities OBJECT IDENTIFIER ::= {iso(1) member-body(2)
           us(840) rsadsi(113549) pkcs(1) pkcs-9(9) 15}

   SMIMECapability ::= SEQUENCE {
      capabilityID OBJECT IDENTIFIER,
      parameters ANY DEFINED BY capabilityID OPTIONAL }

   SMIMECapabilities ::= SEQUENCE OF SMIMECapability
```

如你所见，属性值只是一个 `SMIMECapability` 序列。Bouncy Castle API 提供了 `SMIMECapabilityVector` 和 `SMIMECapability` 类来简化能力的生成和处理。在这种情况下，我们可以像所示编写一个简单的方法来添加一些能力：

```
 /**
   * 基础方法，为任何响应我们消息的人提供一些 S/MIME 能力属性。
   *
   * @return 带有额外属性的 AttributeTable。
   */
  public static AttributeTable generateSMIMECapabilities()
  {
      ASN1EncodableVector signedAttrs = new ASN1EncodableVector();

      SMIMECapabilityVector caps = new SMIMECapabilityVector();
      caps.addCapability(SMIMECapability.aES128_CBC);
      caps.addCapability(SMIMECapability.aES192_CBC);
      caps.addCapability(SMIMECapability.aES256_CBC);
      caps.addCapability(SMIMECapability.preferSignedData);

      signedAttrs.add(new SMIMECapabilitiesAttribute(caps));

      return new AttributeTable(signedAttrs);
  }
```

这些能力用于告诉消息的接收者我们在希望他们如何响应我们方面的偏好。在上面的示例代码中，我们信号表明处理使用 AES CBC 模式加密的各种密钥大小的消息，并且我们也倾向于在响应中使用签名消息。你将在示例中看到，此方法返回的 `AttributeTable` 被添加到我们的 `SignerInfoGeneratorBuilder` 中，以便 S/MIME 能力的额外属性被包含在作为签名过程中生成的 `SignerInfo` 结构中。

现在我们有了一些测试数据和一个带有证书的密钥可以使用，现在可以尝试生成一些 `multipart/signed` 文档了。我们将首先查看新的非 JavaMail API。

## 使用 PKIX S/MIME API 处理 Multipart/signed

PKIX S/MIME API 是构建在 CMS 流式 API 之上的流式 API。

使用 PKIX S/MIME API 创建 `multipart/signed` 是分两个部分的：第一部分是配置一个适用于写入内容的 `SMIMESignedWriter.Builder`，第二部分是使用 `SMIMESignedWriter` 生成签名数据和分离签名。

请看以下创建 `multipart/signed` 的示例代码：

```
   /**
   * 为主体部分创建 multipart/signed。
   *
   * @param signingKey 用于签名的私钥。
   * @param signingCert 与签名关联的公钥证书。
   * @param message 代表待签名主体部分的字节数组。
   * @return 包含 multipart/signed 的字节数组。
   */
  public static byte[] createSignedMultipart(
      PrivateKey signingKey,
      X509CertificateHolder signingCert,
      byte[] message)
      throws OperatorCreationException, CMSException, IOException
   {
      ByteArrayOutputStream bOut = new ByteArrayOutputStream();
      SMIMESignedWriter.Builder sigBldr = new SMIMESignedWriter.Builder();

      sigBldr.addCertificate(signingCert);

      sigBldr.addSignerInfo(
          new JcaSignerInfoGeneratorBuilder()
                    .setProvider("BC")
                    .setSignedAttributeGenerator(generateSMIMECapabilities())
                    .build("SHA256withECDSA", signingKey, signingCert));

      SMIMESignedWriter sigWrt = sigBldr.build(bOut);

      OutputStream out = sigWrt.getContentStream();

      out.write(message);

      out.close();

      return bOut.toByteArray();
   }
```

这是一个示例验证器。它会解析 `multipart/signed` 消息，当遇到包含内容的部分时，将签名部分的内容写入传入的流中；当遇到分离的签名部分时，检查之前找到的数据签名状态。

```
 1   /**
 2    * 验证与 signerCert 关联的 signerInfo，在此过程中将内容写入
 3    * contentStream。
 4    *
  * @param multiPart 包含待检查的签名 multipart 的输入流。
 6    * @param signerCert 与私钥关联的证书，该私钥对内容进行了签名。
 7    * @param contentStream 接收签名内容的输出流。
 9    * @return 如果签名 multipart 通过 signerCert 验证则返回 true，否则返回 false。
10    */
11   public static boolean verifySignedMultipart(
12       InputStream multiPart,
13       X509CertificateHolder signerCert,
14       OutputStream contentStream)
15       throws IOException
16   {
17       AtomicBoolean isVerified = new AtomicBoolean(false);
18 
19       MimeParserProvider provider = new SMimeParserProvider("7bit",
20                                             new BcDigestCalculatorProvider());
21 
22       MimeParser parser = provider.createParser(multiPart);
23 
24       parser.parse(new SMimeParserListener()
25       {
26           public void content(
27               MimeParserContext parserContext,
28               Headers headers,
29               InputStream inputStream)
30               throws IOException
31           {
32               byte[] content = Streams.readAll(inputStream);
33 
34               contentStream.write(content);
35           }
36 
37           public void signedData(
38               MimeParserContext parserContext,
39               Headers headers,
40               Store certificates, Store CRLs, Store attributeCertificates,
41               SignerInformationStore signers)
42               throws CMSException
43           {
44               SignerInformation signerInfo = signers.get(
45                   new SignerId(
46                           signerCert.getIssuer(), signerCert.getSerialNumber()));
46 
47               try
48               {
49                   isVerified.set(signerInfo.verify(
50                       new JcaSimpleSignerInfoVerifierBuilder()
51                              .setProvider("BC").build(signerCert)));
52               }
53               catch (Exception e)
54               {
55                   throw new CMSException(
56                       "unable to process signerInfo: " + e.getMessage(), e);
57               }
58           }
59       });
60 
61       return isVerified.get();
62   }
```

在此请注意，在这种情况下，`SignedData` 结构在传递给 `signedData()` 方法之前已经过解构。与之前不同，之前我们是从完整的 `CMS` SignedData 结构开始，并且手动处理其组件。另一个区别是，我们已经有了签名证书，因此只需找到与使用证书创建的 `SignerId` 匹配的 `SignerInfo` 即可。

这段最后的示例代码展示了如何使用我们之前定义的示例主体部分，以及之前生成的私钥和证书，来运行这两个方法。

```
 byte[] data = createSignedMultipart(
                       selfSignedKp.getPrivate(), selfSignedCert, bodyPart);

      ByteArrayOutputStream contentStream = new ByteArrayOutputStream();

      System.out.println("verified: "+ verifySignedMultipart(
                     new ByteArrayInputStream(data), selfSignedCert, contentStream));
      System.out.println(Strings.fromByteArray(contentStream.toByteArray()));
```

假设一切顺利，代码应该产生以下输出：

```
verified: true
Hello, world!
```

这表明签名已成功验证，且 `text/plain` 主体部分的内容也成功恢复。

## 使用 Mail S/MIME API 处理 Multipart/signed

Mail S/MIME API 同样遵循流模型，但在这种情况下，解析是由 JavaMail API 处理的，“单元”消息类型是 `MimeBodyPart` 类。

以下是一个基于 Mail S/MIME API 创建 `multipart/signed` 的示例方法。



## 创建 S/MIME 签名消息

```java
 1   /**
 2    * 为消息中的主体部分创建 multipart/signed。
 3    *
 4    * @param signingKey 用于生成签名的私钥。
 5    * @param signingCert 与签名密钥关联的公钥证书。
 6    * @param message 要签名的主体部分。
 7    * @return 类型为 multipart/signed MIME 对象的 MimeMultipart。
 8    */
 9   public static MimeMultipart createSignedMultipart(
10       PrivateKey signingKey,
11       X509CertificateHolder signingCert,
12       MimeBodyPart message)
13       throws OperatorCreationException, SMIMEException
14   {
15       List<X509CertificateHolder> certList = new ArrayList<>();
16       certList.add(signingCert);
17       Store<X509CertificateHolder> certs = new CollectionStore<>(certList);
18 
19       SMIMESignedGenerator gen = new SMIMESignedGenerator();
20       gen.addSignerInfoGenerator(
21           new JcaSimpleSignerInfoGeneratorBuilder()
22               .setProvider("BC")
23               .setAlgorithm("SHA256withECDSA")
24               .setAttributes(null)
25               .build(signingKey, signingCert));
26       gen.addCertificates(certs);
27       return gen.generate(message);
28   }
```

你可以看到，它看起来与之前的差不多。对于验证情况，解决方案与我们之前看到的 S/MIME 示例非常相似，很大程度上是因为 JavaMail 处理主体部分的方式。以下方法将验证 `MimeMultipart`。

## 验证 S/MIME 签名消息

```java
 1   /**
 2    * 验证包含 multipart/signed 的 MimeMultipart。
 3    *
 4    * @param signedMessage multipart/signed。
 5    * @param signerCert signedMessage 签名者之一的证书。
 6    * @return 如果 multipart/signed 通过 signerCert 验证则返回 true，否则返回 false。
 7    */
 8   public static boolean verifySignedMultipart(
 9       MimeMultipart signedMessage,
10      X509CertificateHolder signerCert)
11      throws GeneralSecurityException, OperatorCreationException,
12               CMSException, MessagingException
13   {
14       SMIMESigned signedData = new SMIMESigned(signedMessage);
15 
16       SignerInformationStore signers = signedData.getSignerInfos();
17 
18       SignerInformation signer = signers.get(
19           new SignerId(signerCert.getIssuer(),
20                            signerCert.getSerialNumber()));
21 
22       return signer.verify(new JcaSimpleSignerInfoVerifierBuilder()
23                              .setProvider("BC").build(signerCert));
24   }
```

以下示例代码，允许你将这两个方法结合起来：

```java
 MimeMultipart signedMM = createSignedMultipart(selfSignedKp.getPrivate(),
          selfSignedCert, new MimeBodyPart(new ByteArrayInputStream(bodyPart)));

      System.out.println("verified: "+ verifySignedMultipart(
                     signedMM, selfSignedCert));
      System.out.println(signedMM.getBodyPart(0).getContent());
```

同时也显示 `signerCert` 的 `SignerInfo` 验证正确，且已签名主体部分的内容已恢复。

## S/MIME 封装消息

S/MIME 封装消息始终将消息作为封装数据传输，并具有 MIME 类型为 `application/pkcs7-mime` 或较旧的 `application/x-pkcs7-mime`。S/MIME 消息本身的内容只是一个持有 `CMS EnvelopedData` 结构的 `ContentInfo` 编码。

S/MIME 封装消息可以使用任何 CMS 封装接收者类型。为了简洁起见，我们在这里只看一个示例，但如果你查看 CMS 章节中列出的针对不同接收者的指令，你会发现对 S/MIME 封装接收者也可以同样的操作。

### 使用 PKIX S/MIME API 创建封装消息

使用 PKIX S/MIME API 创建 S/MIME 封装消息与创建签名消息类似。第一步是配置 `SMIMEEnvelopedWriter.Builder`，指定能够解密消息的接收者；第二步是使用该构建器创建一个 `SMIMEEnvelopedWriter`，然后通过向其输入内容来输出 S/MIME 封装消息。

以下示例方法展示了如何使用 RSA OAEP 进行密钥传输、AES-256 CBC 模式进行消息加密来创建 S/MIME 封装消息。

```java
 1   /**
 2    * 为消息中的主体部分创建 application/pkcs7-mime。
 3    *
 4    * @param encryptionCert 与预期接收者相关的公钥证书。
 5    * @param message 代表要加密主体部分的 byte[]。
 6    * @return 包含 application/pkcs7-mime MIME 对象的 byte[]。
 8    */
 9   public static byte[] createEnveloped(
10       X509Certificate encryptionCert,
11       byte[] message)
12       throws GeneralSecurityException, CMSException, IOException
13   {
14       ByteArrayOutputStream bOut = new ByteArrayOutputStream();
15       SMIMEEnvelopedWriter.Builder envBldr = new SMIMEEnvelopedWriter.Builder();
16 
17       JcaAlgorithmParametersConverter paramsConverter =
18                                           new JcaAlgorithmParametersConverter();
19 
20       AlgorithmIdentifier oaepParams = paramsConverter.getAlgorithmIdentifier(
21           PKCSObjectIdentifiers.id_RSAES_OAEP,
22           new OAEPParameterSpec("SHA-256",
23               "MGF1", new MGF1ParameterSpec("SHA-256"),
24               PSource.PSpecified.DEFAULT));
25 
26       envBldr.addRecipientInfoGenerator(
27           new JceKeyTransRecipientInfoGenerator(
28               encryptionCert, oaepParams).setProvider("BC"));
29 
30       SMIMEEnvelopedWriter sigWrt = envBldr.build(bOut,
31                   new JceCMSContentEncryptorBuilder(CMSAlgorithm.AES256_CBC)
32                       .setProvider("BC")
33                       .build());
34 
35       OutputStream out = sigWrt.getContentStream();
35 
37       out.write(message);
38 
39       out.close();
41 
41       return bOut.toByteArray();
42   }
```

如果你回看 CMS 中的示例（位于“ktri - the KeyTransRecipientInfo Choice”章节中），你会发现接收者生成器的设置是完全相同的。

消息的解密遵循我们在签名验证中看到的监听器模型。我们为消息设置一个解析器，并提供一个监听器，当遇到我们正在寻找的 MIME 类型时会被调用。在封装数据的情况下，回调还会为我们提供消息的发送者信息和接收者。我们使用这些信息来提取数据。

以下示例方法展示了在假设相应接收者到位的情况下，如何从 S/MIME 封装消息中恢复正文。

```java
 1   /**
 2    * 解密 application/pkcs7-mime 消息中的加密内容，在处理过程中将
 3    * 内容写入 contentStream。
 4    *
 5    * @param encryptedPart 包含待检查封装部分的输入流。
 6    * @param recipientCert 与私钥相关的证书，该内容是为该私钥
 7    *                      加密的。
 8    * @param recipientKey 用于解密内容的私钥。
 9    * @param contentStream 用于接收解密内容的输出流。
10    */
 11   public static void decryptEnveloped(
12       InputStream encryptedPart,
13       X509Certificate recipientCert,
14       PrivateKey recipientKey,
15       OutputStream contentStream)
16       throws IOException
17   {
18       MimeParserProvider provider = new SMimeParserProvider("7bit",
19                                              new BcDigestCalculatorProvider());
20 
21       MimeParser parser = provider.createParser(encryptedPart);
22 
23       parser.parse(new SMimeParserListener()
24       {
25           public void envelopedData(
26               MimeParserContext parserContext,
27               Headers headers,
28               OriginatorInformation originator,
29               RecipientStore recipients)
30               throws IOException
31           {
32               RecipientInformation recipInfo = recipients.get(
33                           new JceKeyTransRecipient(recipientKey));
34               byte[] content = recipInfo.getContent();
35               contentStream.write(content);
36           }
37       });
38   }
```

```java
 1   /**
 2    * 从消息中的主体部分创建 application/pkcs7-mime。
 3    *
 4    * @param encryptionCert 与预期接收者相关的公钥证书。
 5    *                       intended recipient.
 6    * @param message 表示要加密的主体部分的 byte[] 数组。
 7    * @return 一个包含 application/pkcs7-mime MIME 对象的 MimeBodyPart。
 8    */
 9   public static MimeBodyPart createEnveloped(
10       X509Certificate encryptionCert,
11       MimeBodyPart message)
12       throws GeneralSecurityException, CMSException, SMIMEException
13   {
14       SMIMEEnvelopedGenerator envGen = new SMIMEEnvelopedGenerator();
15 
16       JcaAlgorithmParametersConverter paramsConverter =
17                                       new JcaAlgorithmParametersConverter();
18 
19       AlgorithmIdentifier oaepParams = paramsConverter.getAlgorithmIdentifier(
20           PKCSObjectIdentifiers.id_RSAES_OAEP,
21           new OAEPParameterSpec("SHA-256",
22               "MGF1", new MGF1ParameterSpec("SHA-256"),
23               PSource.PSpecified.DEFAULT));
24 
25       envGen.addRecipientInfoGenerator(
26           new JceKeyTransRecipientInfoGenerator(
27               encryptionCert, oaepParams).setProvider("BC"));
28 
29       return envGen.generate(message,
30                   new JceCMSContentEncryptorBuilder(CMSAlgorithm.AES256_CBC)
31                       .setProvider("BC")
32                       .build());
33   }
```

唯一的实质区别在于 `generate()` 方法，它接收 `message`（明文源对象），然后在内部将加密后的内容馈到 `MimeBodyPart` 对象中，使得封装数据可以供 JavaMail API 的其他部分使用。

类似的工作模式也适用于 BC Mail API 解密 S/MIME 封装消息，如下例示例方法所示。



```java
 1   /**
 2    * 从封装消息中提取 MIME 主体部分。
 3    *
 4    * @param encryptedMessage 封装消息。
 5    * @param recipientCert 与接收者密钥相关的证书。
 6    * @param recipientKey 用于恢复主体部分的私钥。
 7    */
 8   public static MimeBodyPart decryptEnveloped(
 9       MimeBodyPart encryptedMessage,
10       X509Certificate recipientCert,
11       PrivateKey recipientKey)
12       throws
13       CMSException, MessagingException, SMIMEException
14   {
15       SMIMEEnveloped envData = new SMIMEEnveloped(encryptedMessage);
16 
17       RecipientInformationStore recipients = envData.getRecipientInfos();
18 
19       RecipientInformation recipient = recipients.get(
20           new JceKeyTransRecipientId(recipientCert));
21 
22       return SMIMEUtil.toMimeBodyPart(recipient.getContent(
23           new JceKeyTransEnvelopedRecipient(recipientKey).setProvider("BC")));
23   }
```

注意，需要使用工具方法 `SMIMEUtil.toMimeBodyPart()`，因为 `RecipientInformation` 类没有对 JavaMail 的直接支持。如果你只是感兴趣获取内容而不为 JavaMail 重新封装数据，则可以避免该调用。

这种情况下的设置与 PKIX S/MIME API 相同。当然，区别在于方法的调用，因为 JavaMail API 并不直接处理流（streams），而是要求你使用 JavaMail 预定义的类型来呈现 MIME 对象。

你可以从以下调用方法的代码中看到这一点——我们需要将 `bodyPart` 封装在 `MimeBodyPart` 对象中以进行处理。

```java
 MimeBodyPart signedMM = createEnveloped(
          selfSignedCert, new MimeBodyPart(new ByteArrayInputStream(bodyPart)));

      BodyPart decPart = decryptEnveloped(
                            signedMM, selfSignedCert, selfSignedKp.getPrivate());

      System.out.println(decPart.getContent());
```

在示例案例中，我们做的另一个变化是使用 `getContent()` 方法获取加密主体部分的内容以便输出。在这种情况下，当运行代码时，你将看到以下输出：

```
Hello, world!
```

这表明加密的主体部分及其内容已成功恢复。

## 使用 JavaMail 的注意事项

我们发现以下操作给人们引起了足够的问题，值得特别提及。

### 处理“multipart/mixed”内容

一个常见的困惑来源是如何处理 multipart/mixed 数据。在这种情况下，必须在将 multipart 内容传递给 S/MIME API 之前，将其封装在单个 `MimeBodyPart` 中。

## 时间戳协议 (Time-Stamp Protocol)

时间戳协议 (TSP) 最初定义在 RFC 3161 [8] 中，随后在 RFC 5816 [107] 中进行了更新，允许使用 SHA-1 以外的消息摘要。其背后的基本概念是时间戳权威（TSA）发布加密安全的时间戳，以响应包含某些文档的时间戳请求。

### 时间戳请求 (Time-Stamp Requests)

时间戳请求由 3161 定义。`TimeStampReq` 的 ASN.1 定义如下：

```
TimeStampReq ::= SEQUENCE  {
    version               INTEGER  { v1(1) },
    messageImprint        MessageImprint,
    reqPolicy             TSAPolicyId              OPTIONAL,
    nonce                 INTEGER                  OPTIONAL,
    certReq               BOOLEAN                  DEFAULT FALSE,
    extensions            [0] IMPLICIT Extensions  OPTIONAL
  }

MessageImprint ::= SEQUENCE  {
    hashAlgorithm         AlgorithmIdentifier,
    hashedMessage         OCTET STRING  }

TSAPolicyId ::= OBJECT
```

你可以看到 `TimeStampReq` 的简单版本只包含版本号和 MessageIm。。示例方法使用 SHA-256（基于 5816）创建一个基础的时间戳请求：

```java
 1   /**
 2    * 为传入的 SHA-256 哈希创建一个简单的 TSP 请求。
 3    *
 4    * @param data 我们想要时间戳的数据。
 5    * @return 结果时间戳请求的 DER 编码。
 6    */
 7   public static byte[] createTspRequest(byte[] data)
 8       throws IOException, NoSuchAlgorithmException
 9   {
10       MessageDigest digest = MessageDigest.getInstance("SHA-256");
11 
12       TimeStampRequestGenerator reqGen = new TimeStampRequestGenerator();
13 
14       return reqGen.generate(TSPAlgorithms.SHA256,
15                               digest.digest(data)).getEncoded();
16   }
```

所有可选字段都用于为时间戳请求者提供额外信息。`reqPolicy` 字段用于请求 TSA 发布配置了特定策略的时间戳响应；`nonce` 允许请求者匹配响应与特定的请求而不必担心重复^(19)；`certReq` 字段请求服务器包含其签名证书（可能还有其他证书）；最后，`extensions` 字段可以添加扩展（如果已定义）。另一个需要注意的是，当扩展被标记为关键且服务器无法解释它时，服务器将拒绝请求。

以下示例方法允许设置 `nonce` 和 `certReq` 字段。

```java
   /**
    * 为传入的 SHA-256 哈希值创建一个 TSP 请求，该请求
    * 包含一个 nonce，并且可能包含证书请求。
    *
    * @param data 我们想要时间戳的数据。
    * @param nonce 与此请求关联的随机数。
    * @param requestTsaCert 如果为 true，权威机构应返回其证书的
    *                       副本。
    * @return 生成的 TSP 请求的 DER 编码。
    */
   public static byte[] createNoncedTspRequest(
       byte[] data, BigInteger nonce, boolean requestTsaCert)
       throws IOException, NoSuchAlgorithmException
   {
       TimeStampRequestGenerator reqGen = new TimeStampRequestGenerator();

       reqGen.setCertReq(requestTsaCert);

       MessageDigest digest = MessageDigest.getInstance("SHA-256");

       return reqGen.generate(
                TSPAlgorithms.SHA256, digest.digest(data), nonce).getEncoded();
   }
```

如你所见，`nonce` 是 `generate` 请求中的一个额外参数，因为 `nonce` 值应该只使用一次。

### 时间戳协议响应

生成 TSP 响应的最低要求是 TSA 的私钥、一个序列号以及用于显示 TSA 在何种策略下创建 TSP 令牌的策略标识符。这通常是服务器特定的，并在服务器所有者控制的 OID 分支下颁发。策略 `oid` 通常会与实际文档关联，该文档详细说明了 TSP 服务器将如何处理特定的时间戳请求。`RFC 3628` [84] 为 TSP 服务器的基线时间戳策略提供了要求。正如我们之前看到的，时间戳请求可能还会在 `reqPolicy` 字段中包含请求提供时间戳时遵循的策略的信息。

时间戳响应具有以下 ASN.1 定义：

```
TimeStampResp ::= SEQUENCE  {
    status                  PKIStatusInfo,
    timeStampToken          TimeStampToken     OPTIONAL  }
```

响应的第一部分 `status` 字段指示请求的成功或失败。第二部分 `timeStampToken` 仅在请求成功时设置。

`PKIStatusInfo` 也是一个序列，并包含一些可选字段，如果请求被服务器拒绝，可以设置这些字段。

```
 PKIStatusInfo ::= SEQUENCE {
      status        PKIStatus,
      statusString  PKIFreeText     OPTIONAL,
      failInfo      PKIFailureInfo  OPTIONAL  }
```

`PKIFreeText` 仅仅是 `UTF8String` 的 `SEQUENCE`。

`PKIStatus` 定义为 `INTEGER`，具有 6 个可能的值。这些可能值及其相关含义为：

- 1 - granted (允许)
- 2 - grantedWithMods (允许并修改)
- 3 - rejection (拒绝)
- 4 - waiting (等待)
- 5 - revocationWarning (撤销警告)
- 6 - revocation (撤销)

当 `timeStampToken` 字段未设置时（`status` 不是 1 或 2 的情况），`failInfo` 字段将持有请求被拒绝的确定信息。与 `PKIStatus` 不同，`PKIFailureInfo` 实际上是一个 `BIT STRING` 而不是 `INTEGER`，具有以下 ASN.1 定义：

```
PKIFailureInfo ::= BIT STRING {
    badAlg               (0),
    badRequest           (2),
    badDataFormat        (5),
    timeNotAvailable    (14),
    unacceptedPolicy    (15),
    unacceptedExtension (16),
    addInfoNotAvailable (17),
    systemFailure       (25) }
```

不同 `BIT STRING` 值的含义在 `RFC 3161` 中给出如下：

- `badAlg`: `messageImprint` 包含一个未识别或不支持的 `AlgorithmIdentifier`（算法标识符）；
- `badRequest`: 请求不受允许或不支持；
- `badDataFormat`: 请求以错误的格式提交；
- `timeNotAvailable`: TSA 的时间源不可用；
- `unacceptedPolicy`: 提请求的 TSA 策略不受 TSA 支持；
- `unacceptedExtension`: 请求中的扩展（通常是关键性扩展）不受 TSA 支持；
- `addInfoNotAvailable`: 任何关于时间戳的额外信息的请求都无法理解，或者该信息不可用；
- `systemFailure`: 由于 TSA 系统故障，无法处理请求。

当请求消息的 `CertReq` 字段设置为 true 时，符合标准的 TSA 必须至少提供一个可以验证时间戳签名的证书。也可能存在其他证书。当 `CertReq` 字段未设置时，符合标准的 TSA 不会在响应中包含任何证书。

当请求成功时，响应的 `timeStampToken` 字段被设置。`TimeStampToken` 结构实际上是一个类型为 `id-signedData` 的 `CMS ContentInfo` 字段。响应中的实际时间戳信息以封装数据的形式出现在 `ContentInfo` 中 `SignedData` 的 `eContent` 中。包含时间戳信息的结构是 `TSTInfo` 结构，它在 `eContent` 中的存在通过将 `eContentType` 设置为 `id-ct-TSTInfo` 来，定义如下：

```
id-ct-TSTInfo  OBJECT IDENTIFIER ::= {
 iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-9(9) smime(16) ct(1) 4
}
```

`TSTInfo` 结构以及它所使用的时间戳的额外结构由以下 ASN.1 定义描述：

```
TSTInfo ::= SEQUENCE  {
    version                      INTEGER  { v1(1) },
    policy                       TSAPolicyId,
    messageImprint               MessageImprint,
    serialNumber                 INTEGER,
    accuracy                     Accuracy                 OPTIONAL,
    ordering                     BOOLEAN             DEFAULT FALSE,
    nonce                        INTEGER                  OPTIONAL,
    tsa                          [0] GeneralName          OPTIONAL,
    extensions                   [1] IMPLICIT Extensions  OPTIONAL   }

Accuracy ::= SEQUENCE {
                seconds        INTEGER           OPTIONAL,
                millis     [0] INTEGER  (1..999) OPTIONAL,
                micros     [1] INTEGER  (1..999) OPTIONAL  }
```

正如你预期的那样，`messageImprint` 字段以及如果请求中存在相同的 `nonce` 字段，在响应的 `TSTInfo` 结构必须回显请求中对应字段的内容。`serialNumber` 代表由服务器颁发的 `INTEGER`，它对于响应是唯一的。

时间戳响应必须包含秒，尽管它们可能包含更详细的内容，并且始终以 UTC 时间表示。当 `accuracy` 字段被设置时，可以使用它来计算时间戳所代表的时间范围的上限（通过向 `genTime` 加上 `accuracy`）和下限（通过从 `genTime` 减去 `accuracy`）。`Accuracy` 结构中任何缺失的字段应被视为零。

在 Bouncy Castle 中，创建 `TSTInfo` 结构的大部分工作都在 API 完成，因此响应生成主要关注提供签名者和请求参数。以下示例方法提供了一个时间戳响应生成器的示例，它可以处理使用我们看过的请求生成方法构建的请求。



```java
  /**
   * 为传入的字节编码 TSP 请求创建 TSP 响应。
   *
   * @param tsaSigningKey  TSA 签名密钥。
   * @param tsaSigningCert TSA 验证证书的副本。
   * @param serialNumber   响应序列号
   * @param tsaPolicy      时间戳
   * @param encRequest     TSP 请求的字节编码。
   */
  public static byte[] createTspResponse(
      PrivateKey tsaSigningKey, X509Certificate tsaSigningCert,
      BigInteger serialNumber, ASN1ObjectIdentifier tsaPolicy, byte[] encRequest)
      throws TSPException, OperatorCreationException,
      GeneralSecurityException, IOException
  {
      AlgorithmIdentifier digestAlgorithm =
          new AlgorithmIdentifier(NISTObjectIdentifiers.id_sha256);
      DigestCalculatorProvider digProvider =
          new JcaDigestCalculatorProviderBuilder().setProvider("BC").build();

      TimeStampRequest tspRequest = new TimeStampRequest(encRequest);

      SignerInfoGenerator tsaSigner = new JcaSimpleSignerInfoGeneratorBuilder()
          .build("SHA256withECDSA", tsaSigningKey, tsaSigningCert);
      TimeStampTokenGenerator tsTokenGen = new TimeStampTokenGenerator(
          tsaSigner, digProvider.get(digestAlgorithm), tsaPolicy);

      // 客户端请求签名证书的副本
      if (tspRequest.getCertReq())
      {
          tsTokenGen.addCertificates(
              new JcaCertStore(Collections.singleton(tsaSigningCert)));
      }

      TimeStampResponseGenerator tsRespGen = new TimeStampResponseGenerator(
          tsTokenGen, TSPAlgorithms.ALLOWED);

      return tsRespGen.generate(tspRequest, serialNumber, new Date()).getEncoded();
  }
```

在示例代码中你会注意到，虽然我们通过调用 `getCertReq()` 方法显式地检查并处理了请求中的 `CertReq` 字段，但并没有提到 nonce（随机数），尽管我们的 `createNoncedTspRequest()` 方法会在其生成的请求中提供一个 nonce。这是因为由于对 nonce 有定义的规则，nonce 是在 `TimeStampResponseGenerator` 类 `generate()` 方法内部构建 `TimeStampToken` 的最终构建过程中被处理的。

以下方法验证时间戳响应，成功时返回 true，否则抛出异常。

```java
  /**
   * 验证传入的响应是否可以通过 TSA 证书验证，并确保与
   * encRequest 中编码的时间戳请求匹配。
   *
   * @param encResponse 时间戳响应的 ASN.1 二进制编码。
   * @param tsaCertificate 生成响应的 TSA 证书。
   * @param encRequest 原始请求的 ASN.1 二进制编码。
   * @return 如果响应可以验证则返回 true，验证失败则抛出异常。
   */
  public static boolean verifyTspResponse(
      byte[] encResponse,
      X509Certificate tsaCertificate,
      byte[] encRequest)
      throws IOException, TSPException, OperatorCreationException
  {
      TimeStampResponse tspResp = new TimeStampResponse(encResponse);

      // 响应/请求验证会在出现问题时抛出异常
      tspResp.validate(new TimeStampRequest(encRequest));

      TimeStampToken tsToken = tspResp.getTimeStampToken();

      // 令牌签名验证会在出现问题时抛出异常
      tsToken.validate(new JcaSimpleSignerInfoVerifierBuilder()
          .setProvider("BC")
          .build(tsaCertificate));

      return true;
  }
```

`validate` 方法非常短，因为 `TSP` API 检查了 `RFC 3161` 规定的标准以确保时间戳响应被正确创建。从开发者的角度来看，这只是组装验证签名所需的 `SignerInformationVerifier` 对象的问题。请注意，`RFC 3161` 规定的标准之一：用于验证 TSP 请求的证书必须包含 `ExtendedKeyUsage` 扩展，该扩展被标记为关键（critical），并断言 `id-kp-timeStamping` 为唯一的密钥用途。

现在只需查看一个完整的用法示例。我们将在下一节中进行介绍。

### 时间戳的应用：CAdES-T

最初，`RFC 3126` “长期电子签名格式”提供了多种将时间戳的使用整合到文档签名中的方法。`RFC 5126` “CMS 高级电子签名 (CAdES)”在此基础上进一步扩展，提供了一种结合 `CMS` 指定长寿命数字签名的方法。

此过程的第一步是创建 TSP 请求。以下方法展示了如何使用我们已有的方法创建 TSP 请求：

```java
  /**
   * 为 SignedData 结构中的 SignerInfo 创建 TSP 请求。
   *
   * @param nonce 与请求一起使用的 nonce。
   * @param encSignedData SignedData 结构的编码。
   * @return 一个 TSP 请求。
   */
  public static byte[] createSignerInfoTspRequest(
      BigInteger nonce,
      byte[] encSignedData)
      throws GeneralSecurityException,
             CMSException, IOException
  {
      CMSSignedData signedData = new CMSSignedData(encSignedData);
      SignerInformation signer = signedData.getSignerInfos().iterator().next();

      return createNoncedTspRequest(signer.getSignature(), nonce, true);
  }
```

注意，该 TSP 请求是使用从表示 `SignedData` 结构的 `CMSSignedData` 对象获取的 `SignerInformation` 对象存储的签名内容创建的。

一旦 TSP 请求被处理并返回响应，该过程的下一步是创建一个 CMS 属性结构，然后将其添加到原始请求签名的 CMS SignerInfo 结构的未签名属性中。

以下方法展示了如何为 SignerInfo 结构创建正确的 CMS 属性：

```java
  /**
   * 为携带 TSP 响应创建 CMS 属性。
   *
   * @param tspResponse 来自我们要引用的时间戳机构的响应。
   * @return 适用于 TSP 响应的属性。
   */
  public static Attribute createTspAttribute(byte[] tspResponse)
      throws TSPException, IOException
  {
      TimeStampResponse response = new TimeStampResponse(tspResponse);
      TimeStampToken timestampToken = response.getTimeStampToken();

      return new Attribute(PKCSObjectIdentifiers.id_aa_signatureTimeStampToken,
                          new DERSet(timestampToken.toCMSSignedData().toASN1Structure()));
  }
```

此示例方法展示了如何整合所有内容，产生一个 CMS SignedData ，其第一个 SignerInfo 结构已通过编辑在其中包含了一个时间戳。

```java
   /**
    * 将 encSignedData 代表的 CMS SignedData 中的 SignerInformation
    * 替换为带有时间戳的版本。
    *
    * @param encSignedData 要时间戳的 SignedData 编码。
    * @param nonce 用于 TSP 请求的随机数（nonce）。
    * @param tsaSigningKey 时间戳机构密钥。
    * @param tsaSigningCert 时间戳机构证书。
    * @param serialNumber 时间戳响应的序列号。
    * @param tsaPolicyOID 时间戳机构工作的策略 OID。
    * @return 带有时间戳的新版本 encSignedData 的编码。
    */
   public static byte[] createTimeStampedSignedData(
      byte[] encSignedData,
      BigInteger nonce,
      PrivateKey tsaSigningKey, X509Certificate tsaSigningCert,
      BigInteger serialNumber, ASN1ObjectIdentifier tsaPolicyOID)
      throws OperatorCreationException,
             GeneralSecurityException,
             CMSException, TSPException, IOException
   {
      CMSSignedData signedData = new CMSSignedData(encSignedData);
      SignerInformation signer = signedData.getSignerInfos().iterator().next();

      byte[] tspReq = createSignerInfoTspRequest(nonce, encSignedData);

      byte[] tspResp = createTspResponse(tsaSigningKey, tsaSigningCert,
                                          serialNumber, tsaPolicyOID, tspReq);

      // 响应
      verifyTspResponse(tspResp, tsaSigningCert, tspReq);

      // 设置包含 TSP 属性的属性表。
      ASN1EncodableVector timestampVector = new ASN1EncodableVector();

      timestampVector.add(createTspAttribute(tspResp));

      AttributeTable at = new AttributeTable(timestampVector);

      // 创建替换的签名者
      signer = SignerInformation.replaceUnsignedAttributes(signer, at);

      // 创建替换的 SignerStore
      SignerInformationStore newSignerStore = new SignerInformationStore(signer);

      // 替换 signed data 对象中的签名者
      return CMSSignedData.replaceSigners(signedData, newSignerStore).getEncoded();
   }
```

在创建了带有时间戳的 `SignerInfo` 结构后，我们现在来看在日后验证该时间戳的过程。这需要从 `SignerInfo` 结构未签名属性中的相应属性中重新构建 `TimeStampToken`。

```java
   /**
    * 验证传入的 CMS SignedData 上的时间戳令牌属性。
    * 注意：在这种情况下，我们使用的是与 SignedData 关联的
    * TimeStampToken 中存储证书。
    *
    * @param cmsSignedData 我们想要检查的 CMS SignedData 编码。
    * @return 如果验证通过返回 true，否则抛出异常。
    */
   public static boolean verifyTimeStampedSigner(byte[] cmsSignedData)
       throws CMSException,
              IOException, TSPException,
              CertificateException, OperatorCreationException
   {
      CMSSignedData signedData = new CMSSignedData(cmsSignedData);
      SignerInformation signer = signedData.getSignerInfos().iterator().next();

      TimeStampToken tspToken = new TimeStampToken(
          ContentInfo.getInstance(
              signer.getUnsignedAttributes()
                  .get(PKCSObjectIdentifiers.id_aa_signatureTimeStampToken)
                      .getAttributeValues()[0]));

      Collection certCollection = tspToken.getCertificates()
                                      .getMatches(tspToken.getSID());
      Iterator certIt = certCollection.iterator();
      X509CertificateHolder cert = (X509CertificateHolder)certIt.next();

      // 如果验证失败，此方法将抛出异常。
      tspToken.validate(new JcaSimpleSignerInfoVerifierBuilder()
                                  .setProvider("BC").build(cert));

      return true;
   }
```

注意，你并不总是能够依赖 `TimeStampToken` 包含验证证书。自然地，你会希望确保验证证书也是有效的。自动从表面上接受这些内容并不是一个好主意。

这段最后的示例代码展示了如何将上述所有内容整合在一起，并从我们之前查看过的 CMS 方法创建的结构生成带有时间戳的 SignedData 结构。



```java
byte[] msg = Strings.toByteArray("Hello, world!");

KeyPair selfSignedKp = generateECKeyPair();
X509CertificateHolder selfSignedCert =
    createTrustAnchor(selfSignedKp, "SHA256withECDSA");

CMSSignedData encapSigned = createSignedData(selfSignedKp.getPrivate(),
    selfSignedCert, msg, true);

... (省略重复代码块) ...
```

# 第 12 章：证书请求与证书管理

正如我们已经看到的，CA 并不是凭空生成证书的——证书生成通常是为了响应证书请求而进行的。证书请求通常是远程的，因此它们也能保护用户的私钥，免受任何被证明是恶意的或在某些方面疏忽的 CA 的滥用。

尽管如此，虽然证书请求意图显而易见，但其中应该包含什么并不十分明确，因此已经提出了许多协议用于向 CA 发送消息以生成证书。在本章中，我们将查看证书请求消息是如何组合的，以及它们被用于哪些协议。这有助于帮助我们理解客户端和 CA 在处理证书请求并将证书从 CA 返回给客户端时需要经历的请求/响应周期。

## PKCS #10 证书请求

PKCS #10 的命名源于原始的 RSA 标准。PKCS #10 证书请求的当前定义现在由 `RFC 2986` [78] 描述，其关联 MIME 类型的描述在 `RFC 5967` [110] 中。

在 Bouncy Castle 中，你可以使用 `org.bouncycastle.pkcs` 包中的 `PKCS10CertificationRequestBuilder` 和 `PKCS10CertificationRequest` 类来创建和处理 PKCS #10 证书请求，也可以使用扩展自它们的类，如 `JcaPKCS10CertificationRequestBuilder` 和 `JcaPKCS10CertificationRequest`。与 PKIX API 中的其他情况一样，以“Jca”开头的类感知 JCA 类型（例如 `PublicKey`），并可以根据需要配置 JCA 者。

在最基础的层，PKCS #10 请求仅仅是对一个结构进行签名，该结构包含了你希望与证书请求中的公钥关联的主体名称（subject name）。RFC 2986 在 ASN.1 中对该结构的描述如下：

```
CertificationRequestInfo ::= SEQUENCE {
       version       INTEGER { v1(0) } (v1,...),
       subject       Name,
       subjectPKInfo SubjectPublicKeyInfo{{ PKInfoAlgorithms }},
       attributes    [0] Attributes{{ CRIAttributes }}
  }

  CertificationRequest ::= SEQUENCE {
       certificationRequestInfo CertificationRequestInfo,
       signatureAlgorithm AlgorithmIdentifier{{ SignatureAlgorithms }},
       signature          BIT STRING
  }
```

`SubjectPublicKeyInfo` 和 `Attributes` 同样提供了定义，但这些结构与我们在第 8 章中已经遇到的证书和属性证书的结构是相同的。从 ASN.1 可以看出，`CertificationRequest` 结构的组合方式本质上与用于构建 ASN.1 `Certificate` 结构的方法是相同的。

PKCS #10 请求上的签名会被 CA 接受，因为它提供了所有权证明（POP），以证明证书请求来自获得授权请求与主体名称关联的人员。POP 是通过使用与请求中公钥关联的私钥生成签名来提供的——从而确定该请求是由已知晓私钥的人创建的。这意味着 PKCS #10 请求与 `RFC 4211` [88] 中定义的不同，它只能用于可以用来生成签名的密钥。这同时也意味着如果公钥旨在用于加密（在 FIPS 语文中），则需要对提供者进行配置，以允许用于签署证书请求的双重用途。

你可以从下面的代码片段中看到如何在 JCA 下构建基础证书请求的示例：

```java
/**
 * 创建一个基础 PKCS#10 请求。
 *
 * @param keyPair 证书请求所属的密钥对。
 * @param sigAlg 用于签署 PKCS#10 请求的签名算法。
 * @return 承载 PKCS#10 请求的对象。
 * @throws OperatorCreationException 如果私钥与所选签名算法
 * 不匹配则抛出异常。
 */
public static PKCS10CertificationRequest createPKCS10(
        KeyPair keyPair, String sigAlg)
        throws OperatorCreationException
{
    X500NameBuilder x500NameBld = new X500NameBuilder(BCStyle.INSTANCE)
            .addRDN(BCStyle.C, "AU")
            .addRDN(BCStyle.ST, "Victoria")
            .addRDN(BCStyle.L, "Melbourne")
            .addRDN(BCStyle.O, "The Legion of the Bouncy Castle");

    X500Name subject = x500NameBld.build();

    PKCS10CertificationRequestBuilder requestBuilder
            = new JcaPKCS10CertificationRequestBuilder(
                                        subject, keyPair.getPublic());

    ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
                            .setProvider("BC").build(keyPair.getPrivate());

    return requestBuilder.build(signer);
}
```

在 CA 侧，你需要能够验证请求上的证书。以下方法在 JCA 下实现了此操作：

```java
/**
 * 使用公钥检查 PKCS#10 签名的简单
 * 方法。
 *
 * @param request PKCS10 请求的编码。
 * @return 如果公钥验证签名则返回 true，否则返回 false。
 * @throws OperatorCreationException 如果公钥不适用。
 * @throws PKCSException 如果无法处理 PKCS#10 请求。
 */
public static boolean isValidPKCS10(
        byte[] request)
    throws OperatorCreationException, PKCSException,
           GeneralSecurityException, IOException
{
    JcaPKCS10CertificationRequest jcaRequest =
            new JcaPKCS10CertificationRequest(request).setProvider("BC");
    PublicKey key = jcaRequest.getPublicKey();

    ContentVerifierProvider verifierProvider =
                                   new JcaVerifierProviderBuilder()
                                       .setProvider("BC").build(key);

    return jcaRequest.isSignatureValid(verifierProvider);
}
```

可以看出这是一个三步骤的过程：首先从请求中提取密钥，在这种情况下是通过编码创建并配置 `JcaPKCS10CertificationRequest` 并调用其 `getPublicKey()` 方法。其次，使用公钥通过 `JcaVerifierProviderBuilder` 类使用 Bouncy 提供者创建一个通用验证者提供者。最后，将内容验证提供者传递给 `isSignatureValid()` 方法，在此处它将在方法内部产生一个可用于验证使用签名算法制作签名的验证者。

### 包含扩展请求

PKCS #10 还允许证书请求包含特定扩展的请求，私钥持有者希望将其包含在证书中。这些扩展中最常见的是 `RFC 5280` [101] 中定义的，并在 Bouncy Castle 中通过 `Extension.subjectAltName` 字段表示。扩展请求使用 PKCS #9 扩展请求属性 OID 添加，该 OID 由 `PKCSObjectIdentifiers.pkcs_9_at_extensionRequest` 表示，值为 `1.2.840.113549.1.9.14`。

示例展示了如何使用 `pkcs_9_at_extensionRequest` OID 添加 `subjectAlternativeName` 扩展，以提供与 CSR 主体关联的电子邮件地址。

```java
/**
 * 创建一个 PKCS#10 请求，包含一个扩展请求，详细说明了
 * CA 应该在 subjectAltName 扩展中包含的电子邮件地址。
 *
 * @param keyPair 证书请求所属的密钥对。
 * @param sigAlg 用于对 PKCS#10 请求签名的算法。
 * @return 载有 PKCS#10 请求的对象。
 * @throws OperatorCreationException 当私钥与所选的签名算法不匹配时抛出。
 * @throws IOException 发生 ASN.1 编码错误时。
 */
public static PKCS10CertificationRequest createPKCS10WithExtensions(
        KeyPair keyPair, String sigAlg)
        throws OperatorCreationException, IOException
{
    X500NameBuilder x500NameBld = new X500NameBuilder(BCStyle.INSTANCE)
            .addRDN(BCStyle.C, "AU")
            .addRDN(BCStyle.ST, "Victoria")
            .addRDN(BCStyle.L, "Melbourne")
            .addRDN(BCStyle.O, "The Legion of the Bouncy Castle");

    X500Name subject = x500NameBld.build();

    PKCS10CertificationRequestBuilder requestBuilder
            = new JcaPKCS10CertificationRequestBuilder(
                                        subject, keyPair.getPublic());

    ExtensionsGenerator extGen = new ExtensionsGenerator();

    extGen.addExtension(Extension.subjectAlternativeName, false,
            new GeneralNames(
                    new GeneralName(
                            GeneralName.rfc822Name,
                            "feedback-crypto@bouncycastle.org")));

    Extensions extensions = extGen.generate();

    requestBuilder.addAttribute(
            PKCSObjectIdentifiers.pkcs_9_at_extensionRequest, extensions);

    ContentSigner signer = new JcaContentSignerBuilder(sigAlg)
                            .setProvider("BC").build(keyPair.getPrivate());

    return requestBuilder.build(signer);
}
```

正如从 `ExtensionsGenerator` 类的使用所示，可以轻松地添加多种扩展。值得注意的是，虽然可以使用 `pkcs_9_at_extensionRequest` 向 CSR 中添加扩展，但 CA 并没有义务添加它们。相反，如果你正在编写一个 CA 并且愿意处理扩展请求属性，你应该检查正在请求的是哪些扩展，以确保没有意外的内容混入你颁发的任何一个证书中。

## 用于 PKCS #10 的 BCFIPS Provider 配置

由于在大多数情况下这是个坏主意，FIPS 140-2 不允许使用双用途密钥。其基本准则是：你可以根据自己的意愿进行加密或签名，但请（大部分）不要对同一个密钥同时进行这两者。这里的“大部分”是指在 SP 800-56B Rev 1 第 6.1 节以及 SP 800-57 Pt1 Rev 4 第 8.1.5.1.1.2 节中允许允许的一个例外。该例外是：允许将加密密钥用于一次签名，用于生成证书请求，以便为该加密密钥颁发证书。

Bouncy Castle FIPS provider 通常会直接阻止 RSA 密钥的这种用法，但提供了一个系统属性用于为了 SP 800-56B Rev 1 中描述的目的启用 RSA 密钥的双用途。该系统属性名为 `org.bouncycastle.rsa.allow_multi_use`，如果你将其设置为 `true`，则用于 RSA 加密密钥的 PKCS #10 将按要求工作。

## 证书请求消息格式

PKCS #10 的缺点之一是，它的设计使用的算法仅能用于签名。唯一的所有权证明（proof-of-possession）步骤是验证 PKCS #10 请求上的签名有效性。通常，验证步骤是为了证明公钥所有者签署了请求，因此他们必须拥有私钥。RFC 4211 定义了证书请求消息格式 (CRMF)，该协议通过提供备用机制来处理这一局限性，这些机制可以处理仅用于加密和密钥约定的密钥，同时也支持用于签名生成和验证的密钥。CRMF 将证书颁发视为两个实体——注册机构（RA）和证书颁发机构（CA）之间的协调，其中 RA 验证请求已获得授权，而 CA 颁发实际证书。显然，这两个实体可以是同一个“实体”，但值得注意的是，这并不是强制要求的。

CRMF 的核心结构是 `CertReqMsg`，它是一个三部分结构，并具有以下 ASN.1 定义：

```
CertReqMsg ::= SEQUENCE {
     certReq   CertRequest,
     popo       ProofOfPossession,
     regInfo   SEQUENCE(1..MAX) of AttributeTypeValue
 }
```

`certReq` 字段由一个结构定义，包含了你可能考虑的各种可能性：



CertRequest ::= SEQUENCE {
      certReqId     INTEGER,        -- 用于匹配请求和响应的 ID
      certTemplate  CertTemplate, -- 将颁发的字段
      controls      Controls OPTIONAL }

CertTemplate ::= SEQUENCE {
      version      [0] Version               OPTIONAL,
      serialNumber [1] INTEGER               OPTIONAL,
      signingAlg   [2] AlgorithmIdentifier   OPTIONAL,
      issuer       [3] Name                  OPTIONAL,
      validity     [4] OptionalValidity      OPTIONAL,
      subject      [5] Name                  OPTIONAL,
      publicKey    [6] SubjectPublicKeyInfo  OPTIONAL,
      issuerUID    [7] UniqueIdentifier      OPTIONAL,
      subjectUID   [8] UniqueIdentifier      OPTIONAL,
      extensions   [9] Extensions            OPTIONAL }

OptionalValidity ::= SEQUENCE {
      notBefore  [0] Time OPTIONAL,
      notAfter   [1] Time OPTIONAL } --至少必须存在一个

Time ::= CHOICE {
      utcTime        UTCTime,
      generalTime    GeneralizedTime }

`certReqId` 仅仅是请求者包含的整数，以便在请求被处理时识别来自 CA 的返回响应。`CertTemplate` 中的字段基本上意味着我们在第 8 节查看 X.509 证书结构时所想象的那样。这里应该指出，其中某些字段受到限制，这些限制由 `RFC 4211` 规定，因此如果你计划对 CRMF 进行大量深入工作，下载一份 RFC 副本也是值得的。

虽然我们也熟悉第 8 节中的 `AttributeTypeValue`，但 `controls` 字段是一个需要更多解释，我们将在后文中看到它的用法示例。CRMF 允许请求者发送 RA 注册令牌、认证信息、发布请求、请求者私钥的存档信息、由新请求更新的证书详情，以及 CA 在发送加密响应时应该使用的协议。所有这些项目都可以在 `controls` 字段中指定。

`popo` 字段是识别其他形式所有权证明的地方。它是一个 ASN.1 CHOICE 项，具有以下选项：

```
ProofOfPossession ::= CHOICE {
       raVerified        [0] NULL,
       signature         [1] POPOSigningKey,
       keyEncipherment   [2] POPOPrivKey,
       keyAgreement      [3] POPOPrivKey }
```

`raVerified` 选择用于 RA（注册机构）已确认 CA（证书颁发机构）公钥所有权的情况。签名选择提供了一个序列，其中包含一个对请求部分进行计算的签名，以类似于 PKCS #10 的方法满足所有权证明的要求。`keyEncipherment` 选择提供了一种方法，指定如何处理为仅加密密钥颁发的证书。最后，`keyAgreement` 选择提供了一种方法，指定如何处理为仅用于密钥协商的密钥颁发的证书。

### 基于签名的所有权证明（Signature-Based PoP）

我们将看到的第一个示例是使用最接近 PKCS #10 的方法生成简单的请求，即用于签名密钥的证书请求。

```java
 1   /**
 2    * 生成带有 POP 的 CRMF 证书请求的基本示例，
 3    * 用于如 DSA 的签名算法或来自如 RSA 的算法用于签名生成的 
 4    * 密钥对。
 5    *
 6    * @param kp 我们正在请求其公钥的密钥对。
 7    * @param subject 要与证书关联的主体主体。
 8    * @param algorithm 要使用的签名算法名称。
 9    * @param certReqID 此证书请求的身份（针对客户端）。
10    */
 11   public static byte[] generateRequestWithPOPSig(
12       KeyPair kp, X500Principal subject, String algorithm, BigInteger certReqID)
13       throws CRMFException, IOException, OperatorCreationException
14   {
 15       JcaCertificateRequestMessageBuilder certReqBuild
 16           = new JcaCertificateRequestMessageBuilder(certReqID);
 17 
 18       certReqBuild
 19           .setPublicKey(kp.getPublic())
 20           .setSubject(subject)
 21           .setProofOfPossessionSigningKeySigner(
 22               new JcaContentSignerBuilder(algorithm)
 23                   .setProvider("BC")
 24                   .build(kp.getPrivate()));
 25 
 26       return certReqBuild.build().getEncoded();
 27   }
```

如代码所示，与请求请求的公钥相关的私钥被用于生成包含在请求中的签名组件，以验证所有权证明。

对于基于签名的所有权证明，CRMF 还允许我们在 RA/CA 和请求者之间共享一个密钥，然后将其作为请求证书的依据。如果我们使用这种方法，我们会在请求中排除主体（subject），我们的方法将如下：

```java
 1   /**
 2    * 生成带有 POP 的 CRMF 证书请求的身份验证示例，
 3    * 用于签名算法。在这种情况下，CA 将通过 MAC 验证 
 4    * 验证主体。
 5    *
 6    * @param kp 我们正在请求其公钥的密钥对。
 7    * @param certReqID 此证书请求的身份（针对客户端）。
 8    * @param algorithm 要使用的签名算法名称。
 9    * @param reqPassword 此此请求的授权密码。
10    */
 11   public static byte[] generateRequestWithPOPSig(
12       KeyPair kp, String algorithm, BigInteger certReqID, char[] reqPassword)
13       throws CRMFException, IOException, OperatorCreationException
14   {
 15       JcaCertificateRequestMessageBuilder certReqBuild
 16           = new JcaCertificateRequestMessageBuilder(certReqID);
 17 
 18       certReqBuild
 19           .setPublicKey(kp.getPublic())
 20           .setAuthInfoPKMAC(
 21               new PKMACBuilder(
 22                   new JcePKMACValuesCalculator()),
 23               reqPassword)
 24           .setProofOfPossessionSigningKeySigner(
 25               new JcaContentSignerBuilder(algorithm)
 26                   .setProvider("BC")
 27                   .build(kp.getPrivate()));
 28 
 29       return certReqBuild.build().getEncoded();
 30   }
```

这里使用的 MAC 为 CA/RA 提供了验证我们的请求并匹配相应主体 ID 的手段，并与任何可能其他其他保持一致。

### 基于加密的所有权证明（Encryption-Based PoP）

对于仅加密密钥，基于私钥签名生成所有权证明并非总是可选的。CRMF 考虑了这一点，在那种情况下，基础请求如下：

```java
 1   /**
 2    * 生成带有 POP 的 CRMF 证书请求的基本示例，
 3    * 用于如 ElGamal 的仅加密算法。
 4    *
 5    * @param kp 我们正在请求其公钥的密钥对。
 6    * @param subject 要与证书关联的主体主体。
 7    * @param certReqID 此证书请求的身份（针对客户端）。
 8    */
 9   public static byte[] generateRequestWithPOPEnc(
10       KeyPair kp, X500Principal subject, BigInteger certReqID)
11       throws CRMFException, IOException
12   {
 13       JcaCertificateRequestMessageBuilder certReqBuild
 14           = new JcaCertificateRequestMessageBuilder(certReqID);
 15 
 16       certReqBuild
 17           .setPublicKey(kp.getPublic())
 18           .setSubject(subject)
 19           .setProofOfPossessionSubsequentMessage(SubsequentMessage.encrCert);
 20 
 21       return certReqBuild.build().getEncoded();
 22   }
```

在这种情况下，关键是调用 `certReqBuild.setProofOfPossessionSubsequentMessage()`。`SubsequentMessage.encrCert` 指定 CA/RA 应以加密包（通常是 EnvelopedData）返回证书，请求者通过解密包并恢复证书来证明所有权。该调用的默认版本仅作为加密密钥的所有权证明。

### 基于密钥协商的所有权证明（Key Agreement-Based PoP）

对于密钥协商，如果 CA 支持使用 EnvelopedData，也可以使用加密所有权证明的方法。以下示例指定应加密加密返回证书。

```java
 1   /**
 2    * 生成带有 POP 的 CRMF 证书请求的基本示例，
 3    * 用于密钥协商公钥。
 4    *
 5    * @param kp 我们正在请求其公钥的密钥对。
 6    * @param subject 要与证书关联的主体主体。
 7    * @param certReqID 此证书请求的身份（针对客户端）。
 8    */
 9   public static byte[] generateRequestWithPOPAgree(
10       KeyPair kp, X500Principal subject, BigInteger certReqID)
11       throws CRMFException, IOException
12   {
 13       JcaCertificateRequestMessageBuilder certReqBuild
 14           = new JcaCertificateRequestMessageBuilder(certReqID);
 15 
 16       certReqBuild
 17           .setPublicKey(kp.getPublic())
 18           .setSubject(subject)
 19           .setProofOfPossessionSubsequentMessage(
 20               ProofOfPossession.TYPE_KEY_AGREMENT, SubsequentMessage.encrCert);
 21 
 22       return certReqBuild.build().getEncoded();
 23   }
```

此调用与上一个调用的区别是将所有权证明类型设置为 `TYPE_KEY_AGREMENT`。对于密钥协商密钥，还有另一种形式的所有权证明，并在 `RFC 4211` 第 4.3 节中描述，该节引用了 `RFC 2875` 第 3 节描述的技术 [77]。目前该技术高度依赖 SHA-1，因此尽管它被列为服务器支持的强制性，但在可用情况下最好使用基于 EnvelopedData 的方法。

基于 CMS 的证书管理 (CMC) 的细节最初于 2008 年在 `RFC 5272` [98]、`RFC 5273` [99] 和 `RFC 5274` [100] 中描述，并在 2011 年由 `RFC 6402` 更新。该协议非常有趣，因为它被用于支持 `RFC 7030` - 基于安全传输的注册 (EST) [120]，我们将在接下来查看它。

## 基于安全传输的注册 (EST)

正如名称所示，`RFC 7030` [120] 中描述的安全传输注册是一个设计为在 TLS 上进行的注册过程。

## 示例设置

由于我们利用了 TLS，设置实际上只需要我们获取适用于 EST 服务器的信任根副本，以便我们能够对连接进行身份验证。下面的方法是获取远程信任根任务的一种最小方法示例：

```java
 1   /**
 2    * 从 URL 获取一组信任根并返回它们。注意，为了示例，我们跳过了
 3    * 任何形式的验证。在现实生活中建议
 4    * 更加谨慎。
 5    *
 6    * @param url 指向信任根集的 URL。
 7    * @return 根据从 URL 获取的内容返回 TrustAnchors 集合。
 8    */
 9   public static Set<TrustAnchor> fetchTrustAnchor(String url)
10       throws Exception
11   {
12       CertificateFactory fac = CertificateFactory.getInstance("X509");
13       HashSet<TrustAnchor> out = new HashSet<TrustAnchor>();
14 
15       InputStream taStream = new URL(url).openStream();
16       for (Certificate cert : fac.generateCertificates(taStream))
17       {
18           out.add(new TrustAnchor((java.security.cert.X509Certificate)cert, null));
19       }
20       taStream.close();
21 
22       return out;
23   }
```

在现实生活中，你显然想要做更多工作来确保信任根确实是你应该使用的那一个，即使 EST 演示站点 `www.testrfc7030.com/` 也建议检查当前的 SHA-256 哈希值（当前值的详情在网站上）。`fetch` 方法确实为我们提供了运行请求证书客户端示例所需的内容。

## 从 EST 服务器获取信息

一旦你有了信任根，就可以查询 EST 服务器以确定 EST 服务器在哪些 CA（证书颁发机构）下，支持哪些证书签名请求 (CSR) 属性。

CSR 属性用于告知客户端在证书颁发过程中需要请求的额外信息，以及客户端在请求内容方面有哪些限制。限制的示例可能包括算法，甚至椭圆曲线必须属于特定的集合。

在 Bouncy Castle 中构建基础 EST 客户端是非常简单的，如下所示的方法所示。看一眼代码，然后我们将更仔细地查看它。



基于 CMS 的证书管理 (CMC) 的细节最初于 2008 年在 `RFC 5272` [98]、`RFC 5273` [99] 和 `RFC 5274` [100] 中描述，并在 2011 年由 `RFC 6402` 更新。该协议非常有趣，因为它被用于支持 `RFC 7030` - 基于安全传输的注册 (EST) [120]，我们将在接下来查看它。

### 基于安全传输的注册 (EST)

正如名称所示，`RFC 7030` [120] 中描述的安全传输注册是一个设计为在 TLS 上进行的注册过程。

### 示例设置

由于我们利用了 TLS，设置实际上只需要我们获取适用于 EST 服务器的信任根副本，以便我们能够对连接进行身份验证。下面的方法是获取远程信任根任务的一种最小方法示例：

```
 1   /**
 2    * Grab a set of trust anchors from a URL and return them. Note, we've skipped
 3    * doing any sort of verification here for the sake of the example. More caution
 4    * is recommended in real life.
 5    *
 6    * @param url the URL pointing at the trust anchor set.
 7    * @return a set of TrustAnchors based on what was retrieved from the URL.
 8    */
 9   public static Set<TrustAnchor> fetchTrustAnchor(String url)
10       throws Exception
11   {
12       CertificateFactory fac = CertificateFactory.getInstance("X509");
13       HashSet<TrustAnchor> out = new HashSet<TrustAnchor>();
14 
15       InputStream taStream = new URL(url).openStream();
16       for (Certificate cert : fac.generateCertificates(taStream))
17       {
18           out.add(new TrustAnchor((java.security.cert.X509Certificate)cert, null));
19       }
20       taStream.close();
21 
22       return out;
23   }
```

在现实生活中，你显然想要做更多工作来确保信任根确实是你应该使用的那一个，即使 EST 演示站点 `www.testrfc7030.com/` 也建议检查当前的 SHA-256 哈希值（当前值的详情在网站上）。`fetch` 方法确实为我们提供了运行请求证书客户端示例所需的内容。

### 从 EST 服务器获取信息

一旦你有了信任根，就可以查询 EST 服务器以确定 EST 服务器在哪些 CA（证书颁发机构）下，并支持哪些证书签名请求 (CSR) 属性。

CSR 属性用于告知客户端在证书颁发过程中需要请求的额外信息，以及客户端在请求内容方面有哪些限制。限制的示例可能包括算法，甚至椭圆曲线必须属于特定的集合。

在 Bouncy Castle 中构建基础 EST 客户端是非常简单的，如下所示的方法所示。看一眼代码，然后我们将更仔细地查看它。

```
 1   /**
 2    * Connect to an EST server and print out it's CA details and CSR Attributes.
 3    *
 4    * @param trustAnchors trustAnchors to validate (or not) the connection
 5    * @param hostName     hostName of the EST server
 6    * @param portNo       port number to connect on
 7    */
 8   public static void listCAsAndCSRAttributes(
 9       Set<TrustAnchor> trustAnchors, String hostName, int portNo)
10       throws ESTException
11   {
12       String serverRootUrl = hostName + ":" + portNo;
13 
14       X509TrustManager[] trustManagers = JcaJceUtils.getCertPathTrustManager(
15                                                            trustAnchors, null);
16 
17       // Create the service builder
18       JsseESTServiceBuilder estBldr = new JsseESTServiceBuilder(
19                                                  serverRootUrl, trustManagers);
20 
21       // Refuse to match on a "*.com". In the most general case you
22       // could use the known suffix list.
23       estBldr.withHostNameAuthorizer(
24           new JsseDefaultHostnameAuthorizer(Collections.singleton("com")));
25 
26       // Build our service object
27       ESTService estService = estBldr.build();
28 
29       // Fetch and list the CA details
30       CACertsResponse csrCerts = estService.getCACerts();
31 
32       for (X509CertificateHolder id : csrCerts.getCertificateStore()
33                                       .getMatches(null))
34       {
35           System.out.println("CA: " + id.getIssuer()
36                                     + "[" + id.getSerialNumber() + "]");
37       }
```



## 连接 EST 服务器并列出 CA 详情与 CSR 属性

```java
/**
 * Connect to an EST server and print out it's CA details and CSR Attributes.
 *
 * @param trustAnchors trustAnchors to validate (or not) the connection
 * @param hostName     hostName of the EST server
 * @param portNo       port number to connect on
 */
public static void listCAsAndCSRAttributes(
    Set<TrustAnchor> trustAnchors, String hostName, int portNo)
    throws ESTException
{
    String serverRootUrl = hostName + ":" + portNo;

    X509TrustManager[] trustManagers = JcaJceUtils.getCertPathTrustManager(
                                                        trustAnchors, null);

    // Create the service builder
    JsseESTServiceBuilder estBldr = new JsseESTServiceBuilder(
                                                serverRootUrl, trustManagers);

    // Refuse to match on a "*.com". In the most general case you
    // could use the known suffix list.
    estBldr.withHostNameAuthorizer(
        new JsseDefaultHostnameAuthorizer(Collections.singleton("com")));

    // Build our service object
    ESTService estService = estBldr.build();

    // Fetch and list the CA details
    CACertsResponse csrCerts = estService.getCACerts();

    for (X509CertificateHolder id : csrCerts.getCertificateStore()
                                    .getMatches(null))
    {
        System.out.println("CA: " + id.getIssuer()
                                  + "[" + id.getSerialNumber() + "]");
    }
}
```

## 使用 HTTP 认证进行 EST 注册

```java
/**
 * 通过向期望 HTTPAuth 的服务器发送 PKCS#10 证书请求
 * 来在 EST CA 中进行注册。
 *
 * @param trustAnchors 用于验证（或不验证）连接的信任锚点
 * @param hostName     EST 服务器的主机名
 * @param portNo       连接的端口号
 * @param userName     用于连接的用户 ID
 * @param password     与用户 ID 关联的密码
 * @param keyPair      用于生成 CSR（证书请求）的密钥对
 * @return 包含作为 X509CertificateHolder 的响应证书 Store
 */
public static Store<X509CertificateHolder> estEnroll(
    Set<TrustAnchor> trustAnchors,
    String hostName, int portNo,
    String userName, char[] password,
    KeyPair keyPair)
    throws Exception
{
    // 构建我们的服务对象
    JsseESTServiceBuilder estBldr = new JsseESTServiceBuilder(
        hostName, portNo, JcaJceUtils.getCertPathTrustManager(
                                            trustAnchors, null));

    estBldr.withHostNameAuthorizer(
        new JsseDefaultHostnameAuthorizer(Collections.singleton("com")));

    ESTService estService = estBldr.build();

    // 创建 PKCS#10 证书请求
    PKCS10CertificationRequestBuilder pkcs10Builder =
        new JcaPKCS10CertificationRequestBuilder(
                    new X500Name("CN=EST Test Client"),
                    keyPair.getPublic());

    ContentSigner contentSigner = new JcaContentSignerBuilder("SHA384WITHECDSA")
                                  .setProvider("BC").build(keyPair.getPrivate());

    PKCS10CertificationRequest certReq = pkcs10Builder.build(contentSigner);

    // 指定我们如何进行身份验证
    ESTAuth auth = new JcaHttpAuthBuilder(null, userName, password)
        .setNonceGenerator(new SecureRandom()).setProvider("BC").build();

    // 请求证书
    boolean isReenroll = false;   // 表示这是一个新注册
    EnrollmentResponse enrollmentResponse = estService.simpleEnroll(
                                                        isReenroll, certReq, auth);

    // 注册操作可以被服务器延迟。
    while (!enrollmentResponse.isCompleted())
    {
        Thread.sleep(Math.max(
            1000,
            enrollmentResponse.getNotBefore() - System.currentTimeMillis()));
        enrollmentResponse = estService.simpleEnroll(isReenroll, certReq, auth);
    }

    return enrollmentResponse.getStore();
}
```

构建服务器与之前类似，我们随后构建一个 `PKCS#10` 证书请求，为服务器提供我们的公钥，以便其为我们创建证书。由于我们正在尝试获取证书，服务器期望我们提供某种程度的身份验证，因此我们构造了一个 `ESTAuth` 对象，使用 HTTP-Auth（通过 TLS）来向服务器识别自己的身份。

下一步是执行注册并获取响应。EST 还支持证书的重新签发，因此在这种情况下，由于是我们的第一次，我们调用 `simpleEnroll()` 方法并将重注册设为 `false`，然后等待响应。EST 服务器有权告诉客户端稍后再回来，所以在尝试从服务器响应中提取证书之前，我们调用 `isCompleted()` 以确保我们确实收到了证书。如果 `isCompleted()` 返回 `false`，响应将包含一个告诉我们可以重试的时间，最好的建议是睡眠到那个时候然后重试。假设一切顺利且我们获得了完成的响应，`EnrollmentResponse` 然后将包含一个或多个供我们使用的证书，其中实体实体是与我们的证书请求相关联的那个。

使用 EST 演示服务器运行这段代码也相当简单。假设你继续使用之前用于获取信任锚点和列出属性的代码片段，以下示例代码将执行注册请求并打印有关返回证书的一些细节：

```java
ECGenParameterSpec ecGenSpec = new ECGenParameterSpec("P-384");
KeyPairGenerator kpg = KeyPairGenerator.getInstance("ECDSA", "BC");
kpg.initialize(ecGenSpec, new SecureRandom());

KeyPair kp = kpg.generateKeyPair();

Store<X509CertificateHolder> certs = estEnroll(
                                        trustAnchors,
                                        "testrfc7030.com", 8443,
                                        "estuser", "estpwd".toCharArray(),
                                        kp);
for (X509CertificateHolder cert : certs.getMatches(null))
{
    System.out.println("Issuer : : + cert.getIssuer()
                                      + "[" + cert.getSerialNumber() + "]");
    System.out.println("Subject: " + cert.getSubject());
}
```

## 使用 POP 获取证书

使用 POP EST 获取证书也支持使用所有权证明（proof-of-possession，简称 POP）。不过这有一点不同之处，协议需要访问 TLS `tls-unique` 通道绑定类型。该通道绑定定义在 `RFC 5929` [109] 中，但目前尚未由 JSSE API 暴露。EST 包提供了一个 `ChannelBindingProvider` 接口，可以使用服务构建器添加。在编写时，只有 JSSE 支持此项，因此以下代码提供了一个适用于 JSSE 的 `ChannelBindingProvider` 实现。

```java
/**
 * BouncyCastle 特定的通道绑定提供程序，允许访问
 * 如 tls-unique 等内容
 */
public class BCJsseChannelBindingProvider
    implements ChannelBindingProvider
{
    public boolean canAccessChannelBinding(Socket sock)
    {
        return sock instanceof BCSSLocket;
    }

    public byte[] getChannelBinding(Socket sock, String binding)
    {
        BCSSLConnection bcon = ((BCSSLocket)sock).getConnection();
        if (bcon != null)
        {
            return bcon.getChannelBinding(binding);
        }
        return null;
    }
}
```

使用 `BCJsseChannelBindingProvider` 和 `ESTService` 类上的 `simpleEnrollPoP()` 方法的示例用法如下所示：

```java
estBldr.withChannelBindingProvider(new BCJsseChannelBindingProvider());

ESTService estService = estBldr.build();

enrollmentResponse = estService.simpleEnrollPoP(
                            reEnroll, pkcs10Builder, contentSigner, auth);
```

注意在这种情况下我们需要向注册方法传递证书请求构建器，而不是预构建的证书请求。这样 POP 所需的属性就可以在与服务器连接后添加到请求中，因为只有那时信息才可用。

## 证书管理协议

证书管理协议（CMP）目前基于 `RFC 4210` [87]。它提供了一种基于 ASN.1 的协议，用于 X509 证书和证书请求的管理与分发。与 CMS 一样，额外的 RFC 提供了适用于新算法的更新。

```asn1
PKIMessage ::= SEQUENCE {
     header           PKIHeader,
     body             PKIBody,
     protection   [0] PKIProtection OPTIONAL,
     extraCerts   [1] SEQUENCE SIZE (1..MAX) OF CMPCertificate
                      OPTIONAL
}
```

其中 `CMPCertificate ::= Certificate`，与 X509 使用的结构相同。

`header` 结构用于包含请求或响应的事务、地址和其他信息。顾名思义，`body` 包含了消息所携带的实际信息，其中 `PKIBody` 结构被分配了一个特定的类型代码。最后一个字段 `extraCerts` 用于存储可能对消息接收者有用的额外证书，例如 CA 可能会发送额外的证书，以便允许形成其在消息正文中刚刚签发的端实体证书的证书验证路径。

`protection` 字段所指的 `PKIProtection` 类型实际上是一个 `BIT STRING`。它是一个计算值，无论是 MAC 还是签名，都是通过对以下结构的 DER 编码计算得：

```
ProtectedPart ::= SEQUENCE {
    header    PKIHeader,
    body      PKIBody
}
```

所使用的保护算法的详细信息显示在构成消息开头的 `PKIHeader` 结构中。

接下来的方法展示了如何使用 Bouncy Castle API 创建简单的 CMP 消息，该消息携带一个证书请求，并使用 MAC 保护和认证。



```java
 1     /**
 2      * 创建一个受 MAC 保护的 CMP ProtectedPKIMessage，其中包含一个 CRMF 证书请求。
 3      *
 4      *
 5      * @param sender 证书请求的发送者。
 6      * @param recipient 目标 CA 地址。
 7      * @param certReqMsg 实际的 CRMF 证书请求。
 8      * @param password 要使用的密码。
 9      * @return 一个 ProtectedPKIMessage
10      */
 11     public static ProtectedPKIMessage generateMacProtectedMessage(
 12         X500Name sender, X500Name recipient,
 13         byte[] senderNonce,
 14         CertificateRequestMessage certReqMsg,
 15         char[] password)
 16         throws CMPException, OperatorCreationException
 17     {
 18         MacCalculator pbCalculator = new JcePBMac1CalculatorBuilder(
 19                       "HmacSHA256", 256).setProvider("BC").build(password);
 20 
 21         return new ProtectedPKIMessageBuilder(
 22                     new GeneralName(sender), new GeneralName(recipient))
 23                             .setMessageTime(new Date())
 24                             .setSenderNonce(senderNonce)
 25                             .setBody(new PKIBody(
 26                                 PKIBody.TYPE_INIT_REQ,
 27                                 new CertReqMessages(
 28                                         certReqMsg.toASN1Structure())))
 29                             .build(pbCalculator);
 30     }
```

你会注意到，用于 MAC 计算器的算法与我们早些在 CRMF 中使用的方案不同。虽然这显示可以适应不同的 MAC 算法，但此情况也展示了一种更符合 FIPS 标准的算法，它基于 RFC 8018 [129]，该标准描述了最初为人知的 PKCS #5 PBKDF2。在这种情况下，通常不需要对 CRMF 消息应用 MAC，因为 CMP MAC 结构同时涵盖了 CRMF 消息和 CMP 消息的头部信息。

虽然 `generateMacProtectedMessage()` 消息的主文相当简洁，但传递给方法的参数数量表明需要进行一些准备。

下面的代码展示了构建必要部分所需的准备工作：

```java
ECGenParameterSpec ecGenSpec = new ECGenParameterSpec("P-384");
KeyPairGenerator kpg = KeyPairGenerator.getInstance("ECDSA", "BC");
kpg.initialize(ecGenSpec, random);
KeyPair kp = kpg.generateKeyPair();

BigInteger certReqId = BigInteger.valueOf(System.currentTimeMillis());

byte[] senderNonce = new byte[16];

random.nextBytes(senderNonce);

CertificateRequestMessage certReqMsg = new CertificateRequestMessage(
        CRMFUtils.generateRequestWithPOPSig(
                kp, new X500Principal("CN=CMP Test Client"),
                "SHA256withECDSA", certReqId));

// 创建封装 CRMF 证书请求的 CMP 消息。
X500Name sender = new X500Name("CN=Certificate Requester");
X500Name recipient = new X500Name("CN=Certificate Issuer");

ProtectedPKIMessage pkiMessage = generateMacProtectedMessage(
    sender, recipient, senderNonce, certReqMsg, "secret".toCharArray());
```

我们生成了一个密钥对，并为接收者选择了一个事务 ID 和随机数（nonce）包含回复中。接下来，我们使用 CRMF API 为我们的公钥生成 `CertificationRequestMessage`。然后，我们使用这些加上我们的共享密钥，使用 CMP 方法生成受保护的 PKI 消息。一个小说明：为了简洁起见，`CertificateRequestMessage` 是根据我们之前看到的 CRMF 方法返回的编码构建的。显而易见，“在现实生活中”你不会这样双重处理消息。除此之外，该代码片段代表了最少所需。

自然，由于在请求中包含了 MAC，接收者将需要验证 MAC 以确认我们的消息是有效的。接下来的简单代码片段展示了接收者将如何验证 MAC：

```java
PBEMacCalculatorProvider macProvider =
        new JcePBMac1CalculatorProviderBuilder().setProvider("BC").build();

System.out.println("message verified: "
    + pkiMessage.verify(macProvider, "secret".toCharArray()));
```

虽然只有几行，但该代码片段展示了 MAC 创建与验证之间的区别。对于验证，我们需要构建一个适用于消息的 `MacCalculatorProvider`。该提供者随后与密钥一起传递给 `verify()` 方法，该类内部构造一个 `MacCalculator`，并用于计算 MAC。假设之前的代码片段都已实现，上面的最后片段应该输出

```
message verified: true
```

表示从消息重构 MAC 成功。

### 总结

在本章中我们查看了创建证书请求的标准协议——PKCS #10 和 CRMF，同时也查看了 CMC、EST 和 CMP 等协议，这些协议通常用于向证书颁发机构（CA）通信证书请求。

CA 通常期望某种形式的所有证明（POP），以证明请求证书的方确实拥有私钥。我们还看到用户能够通过共享密钥向 CA 进行身份验证，这样 CA 就能确信自己正在与已知的人进行通信。

PGP 消息以记录流的形式表示。与我们在 CMS 中看到的不同，这些记录在流中通常表现为独立的实体，例如，封装的签名数据由一组记录组成，分别构成了签名头、数据和最终的签名记录。这与你在 CMS 中看到的有然不同，在 CMS 中所有这些信息都被封装在一个单一的结构中。

OpenPGP 类可以在以“bcpg”开头的 Bouncy Castle 分发包中找到。

## 字面数据记录 (Literal Data Record)

OpenPGP 消息的核心记录类型是 `Literal Data`（字面数据）记录。OpenPGP 中的压缩和加密都适用于 OpenPGP 记录，而 `Literal Data` 记录用于包含你想要压缩或加密的实际数据。同样，对于封装的签名，我们会看到一个 `Literal Data` 记录用于标记被签名消息数据在 OpenPGP 流中出现的位置。

`Literal Data` 记录在 `RFC 4880` 的第 5.9 节中描述。在 Bouncy Castle API 中，它们使用 `PGPLiteralDataGenerator` 创建，你通过调用 `PGPLiteralData` 类上的一个 `open()` 方法来逐个创建。在 OpenPGP 中，字面数据有三种类型：ASCII 文本 (`PGPLiteralData.TEXT`)、二进制 (`PGPLiteralData.BINARY`) 和 UTF-8 (`PGPLiteralData.UTF8`)。`Literal Data` 记录还包含一个文件名，如果不需要文件名，则可以使用特殊字符串“_CONSOLE” (`PGPLiteralData.CONSOLE`) 代替。

## 生成装甲输出 (Armored Output)

OpenPGP 有一种 ASCII 装甲格式（armored format），它与 PEM 非常相似。它是 Base 64 编码的，但在每个记录的末尾包含一个校验和。用于生成装甲输出的类是 `org.bouncycastle.bcpg` 包中的 `ArmoredOutputStream` 类。同包中的 `ArmoredInputStream` 类提供了解析机制。

有消息类型：用于密钥的“PGP PUBLIC KEY BLOCK”和“PGP PRIVATE KEY BLOCK”，用于离线签名的“PGP SIGNATURE”，以及一种通用类型——“PGP MESSAGE”，这有点是一个统称。还有一个特殊情况“PGP SIGNED MESSAGE”，我们将在稍后讨论明文签名时查看它。

下面的代码片段从单个 Literal Data 记录生成装甲输出。

```java
 1       byte[] msg = Strings.toByteArray("Hello, world!");
 2 
3       ByteArrayOutputStream bOut = new ByteArrayOutputStream();
 4       ArmoredOutputStream aOut = new ArmoredOutputStream(bOut);
 5 
6       PGPLiteralDataGenerator lGen = new PGPLiteralDataGenerator();
 7 
8       OutputStream lOut = lGen.open(aOut, PGPLiteralData.TEXT,
 9                           PGPLiteralData.CONSOLE, msg.length, new Date());
10 
11       lOut.write(msg);
12       lOut.close();
13 
14       aOut.close();
15 
16       System.out.println(Strings.fromByteArray(bOut.toByteArray()));
```

如果你运行该代码，你应该看到以下内容：

```
-----BEGIN PGP MESSAGE-----
Version: BCPG v1.63

yxt0CF9DT05TT0xFXX9ONEhlbGxvLCB3b3JsZCE=
=sJgV
-----END PGP MESSAGE-----
```

你可以看到消息块最后一行上的校验和。它是一个 24 位的 CRC，因此适用于检测基本的传输错误，但从加密完整性的角度来看它是没用的。校验和的存在为 `ArmoredOutputStream` 的实现带来了一个有趣的问题，正如警告框所示，这意味着流类上的 `close()` 方法不能关闭底层流，因为调用 `close()` 步骤必须用作生成校验和的触发器。

## 生成密钥环 (Key Rings)

PGP 将密钥和证书存储在密钥环（key rings）中。在最简单的情况下（我们很快就会看到这种情况），密钥环简单来说就是一个主密钥（始终是签名密钥）和一个用于加密的子密钥。

下面的代码生成了一个带有 DSA 主密钥和 RSA 子密钥的基本密钥环，返回私钥和公钥密钥环组件的编码。现在读一遍代码，起初看起来可能有点复杂，但实际的“工作部分”是第 15 到 25 行。

```java
 1   /**
 2    * 使用 DSA 签名密钥和 RSA 加密密钥生成私钥/公钥密钥环。
 3    *
 4    *
 5    * @param identity 与密钥关联的身份标识。
 6    * @param passphrase 用于加密私钥的口密码。
 7    * @return 包含私钥和公钥密钥环编码的 byte[][] 
 8    *              分别对应。
 9    */
10   public static byte[][] generateKeyRings(String identity, char[] passphrase)
11       throws GeneralSecurityException, PGPException, IOException
12   {
13       KeyPair dsaKp = DsaUtils.generateDSAKeyPair();
14       KeyPair rsaKp = RsaUtils.generateRSAKeyPair();
15       PGPKeyPair dsaKeyPair = new JcaPGPKeyPair(
16                                       PGPPublicKey.DSA, dsaKp, new Date());
17       PGPKeyPair rsaKeyPair = new JcaPGPKeyPair(
18                                       PGPPublicKey.RSA_ENCRYPT, rsaKp, new Date());
19       
20       PDigestCalculator sha1Calc = new JcaDigestCalculatorBuilder()
21                                           .setProvider("SHA1")
22                                           .build();
23       
24       PGPKeyRingGenerator keyRingGen = new PGPKeyRingGenerator(
25                PGPSignature.POSITIVE_CERTIFICATION, dsaKeyPair, identity, sha1Calc,
26                null, null,
27                new JcaPSignerBuilder(dsaKeyPair.getPublicKey().getAlgorithm(),
28                       HashAlgorithmTags.SHA384),
29                new JcePBEScretKeyEncryptorBuilder(
30                           PGPEncryptedData.AES_256, sha1Calc)
31                       .setProvider("BC").build(passphrase));
32       keyRingGen.addSubKey(rsaKeyPair);
33 
34       // 创建私钥环的编码
35       ByteArrayOutputStream secretOut = new ByteArrayOutputStream();
36       keyRingGen.generateSecretKeyRing().encode(secretOut);
37       secretOut.close();
38 
39       // 创建公钥环的编码
40       ByteArrayOutputStream publicOut = new ByteArrayOutputStream();
41       keyRingGen.generatePublicKeyRing().encode(publicOut);
42       publicOut.close();
43 
44       return new byte [][]{secretOut.toByteArray(), publicOut.toByteArray()};
45   }
```



一个重要的点在第 17 行，在 `PGPKeyRingGenerator` 构造中指定了 PGP 签名类型。你会注意到这是 `PGPSignature.POSITIVE_CERTIFICATION`。查看一眼 `RFC 4880` 第 5.2.1 节，积极认证意味着密钥持有者对身份声明进行了实质性的验证。积极认证用于将身份绑定到主密钥。公钥也经过内部认证，那里使用的签名类型是 `PGPSignature.SUBKEY_BINDING`。这两个 PGP 签名共同提供了类似于 X.509 为 DSA 主密钥和 RSA 加密子密钥提供的保护。

关于密钥环公钥和私钥组件结构的更多信息，可以在 `RFC 4880` 的第 5.5.2 节和 5.5.3 节中找到。

注意从版本 2.1 开始，GPG 默认使用新的密钥文件格式，即密钥箱文件格式 (.kbx)。我们稍后在本章的后续部分也会查看这种格式。

## 向现有密钥环中添加子密钥

有时你可能想要更新现有密钥环上的加密密钥，通常是通过添加新的子密钥并保留旧密钥。`PGPKeyRingGenerator` 类也有一个构造函数，允许它接收一个现有的 `PGPSecretKeyRing` 并用它生成新的 `PGPSecretKeyRing` 和 `PGPPublicKeyRing` 对象。

添加新子密钥的示例方法如下：

```java
 1   /**
 2    * 根据原始私钥环和一个新的
 3    * 子密钥生成私钥环/公钥环。
 4    *
 5    * @param original 用于创建新密钥环的原始私钥环。
 6    * @param passphrase 用于加密/解密私密钥的密码短。
 7    * @param subKey 要添加的公/私钥子密钥对。
 8    * @return 返回一个 byte[][]，分别包含私钥环和公钥环的编码。
 9    *                  。
10    */
11   public static byte[][] addSubKey(PGPSecretKeyRing original, char[] passphrase, PGP\
12 KeyPair subKey)
13       throws PGPException, IOException
14   {
15       PGPDigestCalculator sha1Calc = new JcaPGPDigestCalculatorProviderBuilder()
16                                           .build()
17                                           .get(HashAlgorithmTags.SHA1);
18 
19       PBESecretKeyDecryptor keyDecryptor = new JcePBESecretKeyDecryptorBuilder().bui\
20                                                               ld(passphrase);
21       PBESecretKeyEncryptor keyEncryptor = new JcePBESecretKeyEncryptorBuilder(
22                                   PGPEncryptedData.AES_256, sha1Calc)
23                               .setProvider("BC").build(passphrase);
24 
25       PGPKeyRingGenerator keyRingGen =
26           new PGPKeyRingGenerator(
27                original, keyDecryptor, sha1Calc,
28                new JcaPGPContentSignerBuilder(
29                       original.getPublicKey().getAlgorithm(),
30                       HashAlgorithmTags.SHA384),
31                keyEncryptor);
32 
33       keyRingGen.addSubKey(subKey);
34 
35       // 创建私钥环的编码
36       ByteArrayOutputStream secretOut = new ByteArrayOutputStream();
37       keyRingGen.generateSecretKeyRing().encode(secretOut);
38       secretOut.close();
39 
40       // 创建公钥环的编码
41       ByteArrayOutputStream publicOut = new ByteArrayOutputStream();
42       keyRingGen.generatePublicKeyRing().encode(publicOut);
43       publicOut.close();
44 
45       return new byte [][]{secretOut.toByteArray(), publicOut.toByteArray()};
46   }
```

在上述方法中，添加子密钥时没有指定要使用哪些哈希/未哈希的签名子包。在这种情况下，签名子包将从主密钥上的主签名继承。此外 `addSubKey(subKey)` 还有一个重载方法，在需要时，它允许显式地指定哈希和未哈希的签名子包。

## 封装签名消息

与 CMS 类似，PGP 同时支持封装签名消息和分离式签名。我们先来看下封装签名。正如我们之前提到的，你可以从代码的构建方式中看出，一个 PGP 封装签名消息是由一系列数据包组成的，而不是像 CMS 那样的单一结构。

![基础封装签名的记录格式。](img/chapter13----PGPSig.png)

基础封装签名的记录格式。

从图中可以看出，一个基础封装签名由三条记录组成：签名头（![A](img/leanpub_equation_649.png)），然后是实际签名（![C](img/leanpub_equation_650.png)）。当签名嵌套时，(!![A](img/leanpub_equation_651.png), ![C](img/leanpub_equation_652.png))对需要对应，因此，如果有两个签名 ![{C_1}](img/leanpub_equation_653.png) 和 ![{C_2}](img/leanpub_equation_654.png)，记录的安排方式应：![{A_2}](img/leanpub_equation_655.png), ![{A_1}](img/leanpub_equation_656.png), ![B](img/leanpub_equation_657.png), ![{C_1}](img/leanpub_equation_658.png), ![{C_2}](img/leanpub_equation_659.png)。

这里是一个示例方法，用于创建一个封装签名消息并返回结果记录的编码。请先查看它，然后我们再进行进一步讨论。

```java
 1   /**
 2    * 根据传入的签名密钥和数据
 3    * 创建一个 PGP 签名消息。
 4    *
 5    * @param signingAlg 要使用的签名算法。
 6    * @param signingKey 用于签名的 PGP 私钥。
 7    * @param data 要签名的消息数据。
 8    * @return 签名消息的编码。
 9    */
10   public static byte[] createSignedMessage(
11       int signingAlg, PGPPrivateKey signingKey, byte[] data)
12       throws PGPException, IOException
13   {
14       ByteArrayOutputStream bOut = new ByteArrayOutputStream();
15 
16       // 创建一个用于写入签名的流。
17       BCPGOutputStream bcOut = new BCPGOutputStream(bOut);
18 
19       // 设置签名生成器
20       PGPSignatureGenerator sGen =
21           new JcaPGPContentSignerBuilder(signingAlg, PGPUtil.SHA384)
22                   .setProvider("BC"));
23 
24       sGen.init(PGPSignature.BINARY_DOCUMENT, signingKey);
25 
26       // 输出签名头
27       // false false 表示我们没有在生成嵌套签名。
28       sGen.generateOnePass(false).encode(bcOut);
29 
30       // 创建字面数据记录
31       PGiteralDataGenerator lGen = new PGiteralDataGenerator();
32 
33       OutputStream lOut = lGen.open(bcOut, PGiteralData.BINARY, PGiteralData.CONSOLE, data.length, new Date());
34       for (int i = 0; i != data.length; i++)
35       {
36           lOut.write(data[i]);
37           sGen.update(data[i]);
38       }
39 
40       // 完成字面数据构造
41       lOut.close();
42 
43       // 输出实际签名
44       sGen.generate().encode(bcOut);
45 
46       // 关闭流。
47       bcOut.close();
48 
49       return bOut.toByteArray();
50   }
```

观察设置签名生成的代码，你可以发现它遵循与 CMS 流式 API 相似的模式。操作符是不同的，因为 OpenPGP 并没有像 ASN.1 `AlgorithmIdentifier` 那样的结构，但如果你像处理 CMS 和 S/MIME 那样将相同的原理应用于 PGP 操作符，一切都会正常工作。

值得注意的是，OpenPGP 将签名与特定类型关联。在示例中，该类型是 `PGPSignature.BINARY_DOCUMENT`，因为我们正在对二进制字面数据记录进行签名。你可以在 RFC 4880 第 5.2.1 节找到 OpenPGP 使用的不同签名和证书类型。证书与文档签名不同，仅与密钥关联。

验证消息涉及几个步骤。验证时最需要注意的一点是，由于字面数据记录独立于签名头和脚部，因此有必要手动将字面数据记录的内容输入签名验证器。

这里给出的示例还利用了为了验证签名而恢复消息的需求，将被签名的数据写入流，以防调用者也希望查看实际的消息数据。请查看以下代码。

```java
  /**
   * 在 bOut 中恢复原始消息，如果签名验证通过则返回 true。
   * 
   * @param verifyingKey 用于验证消息的 PGP 公钥。
   * @param pgpSignedData PGP 签名的消息数据。
   * @param msgStream 用于写入恢复出的消息的流。
   * @return 如果签名消息验证通过，则返回 true，否则返回 false。
   */
  public static boolean verifySignedMessage(
      PGPPublicKey verifyingKey, byte[] pgpSignedData, OutputStream msgStream)
      throws PGPException, IOException
  {
      // 为 PGP 协议流创建一个解析器
      JcaPGPObjectFactory pgpFact = new JcaPGPObjectFactory(pgpSignedData);

      // 读取签名头并设置验证
      PGPOnePassSignatureList onePassList
                               = (PGPOnePassSignatureList)pgpFact.nextObject();
      PGPOnePassSignature ops = onePassList.get(0);

      ops.init(
          new JcaPGPContentVerifierBuilderProvider().setProvider("BC"),
          verifyingKey);

      // 打开包含消息的字面数据记录
      PGPLiteralData literalData = (PGPLiteralData)pgpFact.nextObject();
      InputStream dIn = literalData.getInputStream();

      // 读取消息数据
      int ch;
      while ((ch = dIn.read()) >= 0)
      {
          ops.update((byte)ch);
          msgStream.write(ch);
      }

      dIn.close();

      // 读取并验证签名
      PGPSignatureList sigList = (PGPSignatureList)pgpFact.nextObject();
      PGPSignature sig = sigList.get(0);

      return ops.verify(sig);
  }
```

你会注意到，上述使用的方法——即仅创建一个 `PGPObjectFactory` 然后通过解析来处理数据——被广泛用于处理各种 PGP 消息。请注意，在“现实生活中”中，如果签名失败，你不希望将恢复出的消息数据返回给用户，尽管你可能希望将恢复的消息放在某个安全的地方进行分析。另外一点需要注意的是，我们选择找到找到第一个签名作为验证的匹配项。虽然在这个示例案例中是正确的，但通常情况下并非如此。在我们查看分离签名（detached signatures）时，我们将查看更具通用性的签名处理方法。最后，解析流时通常需要使用 `PGPObjectFactory`，因为你有时无法完全确定接下来会发生什么，所以指定替代方案是比较好的。数据开始处可能会有一个 PGP 标记，这需要被跳过，或者字面数据也可能被封装在压缩数据中。由于这些考虑，如果你正在处理来自多个源的数据，在编写处理代码时，对 PGP 流中可能到达的包类型具有一定的适应性通常是一个好主意。

我们可以使用以下代码片段将这两个方法结合起来，它创建一个消息以及必要的密钥，以便能够创建和验证签名消息，并在验证成功时打印消息数据。

```java
  byte[] message = Strings.toByteArray("Hello, world!");
  KeyPair dsaKp = DsaUtils.generateDSAKeyPair();
  PGPKeyPair dsaKeyPair = new JcaPGPKeyPair(PGPPublicKey.DSA, dsaKp, new Date());

  byte[] signedMessage = createSignedMessage(
      PublicKeyAlgorithmTags.DSA, dsaKeyPair.getPrivateKey(), message);

  ByteArrayOutputStream recStream = new ByteArrayOutputStream();

  if (verifySignedMessage(dsaKeyPair.getPublicKey(), signedMessage, recStream))
  {
      System.out.println(Strings.fromByteArray(recStream.toByteArray()));
  }
```

运行带有提供方法的代码片段应该产生：

```
Hello, world!
```

这表明消息解析正确，签名通过验证，且封装的消息也被成功恢复了。

## 分离签名 (Detached Signatures)

PGP 中的分离签名代表的内容与我们在 S/MIME 的多部分签名数据中看到的分离签名大致相同。以下方法使用传入的字节数组作为待签名数据，为二进制数据生成一个分离签名。



```java
  /**
   * 为二进制数据生成分离签名。
   *
   * @param signingAlg 要使用的签名算法。
   * @param signingKey 要使用的签名密钥。
   * @param data 要签名的数据。
   * @return 经过编码的 PGP 分离签名。
   */
  public static byte[] createDetachedSignature(
      int signingAlg, PGPPrivateKey signingKey, byte[] data)
      throws PGPException, IOException
  {
      PGPSignatureGenerator sGen = new PGPSignatureGenerator(
          new JcaPGPSignerBuilder(signingAlg, PGPUtil.SHA384)
              .setProvider("BC"));

      sGen.init(PGPSignature.BINARY_DOCUMENT, signingKey);

      sGen.update(data);

      PGPSignature pgpSig = sGen.generate();

      return pgpSig.getEncoded();
  }
```

由于签名不包含数据，你可以看到不需要诸如 `generatePassVersion()` 之的操作，因为不需要任何头部信息。此外，由于签名与被签名的数据是分离的，验证还需要提供原始数据作为验证过程的一部分。以下是验证方法：

```java
  /**
   * 验证二进制数据的分离签名。
   *
   * @param verifyingKey 用于验证签名的公钥。
   * @param pgpSignature 为数据生成的签名。
   * @param data 被签名的数据。
   * @return 如果签名验证通过，则返回 true，否则返回 false。
   */
  public static boolean verifyDetachedSignature(
      PGPPublicKey verifyingKey, byte pgpSignature, byte[] data)
      throws PGPException, IOException
  {
      JcaPGPObjectFactory pgpFact = new JcaPGPObjectFactory(pgpSignature);

      PGPSignatureList sigList = (PGPSignatureList)pgpFact.nextObject();

      PGPSignature sig = null;
      for (PGPSignature s: sigList)
      {
          if (s.getKeyID() == verifyingKey.getKeyID())
          {
              sig = s;
              break;
          }
      }

      if (sig == null)
      {
          throw new IllegalStateException("未找到密钥签名");
      }

      sig.init(
          new JcaPGPContentVerifierBuilderProvider().setProvider("BC"),
          verifyingKey);

      sig.update(data);

      return sig.verify();
  }
```

在这种情况下，匹配验证密钥的签名步骤（跨第 17 到 25 行）比之前复杂，但在通常情况下是正确的，因为只有当签名列表中的签名与提供的验证密钥的密钥 ID 匹配时，才会被选中。

可以使用以下代码片段来尝试这两个示例方法。

```java
  byte[] message = Strings.toByteArray("Hello, world!");
  KeyPair dsaKp = DsaUtils.generateDSAKeyPair();
  PGPKeyPair dsaKeyPair = new JcaPGPKeyPair(PGPPublicKey.DSA, dsaKp, new Date());

  byte[] signature = createDetachedSignature(
      PublicKeyAlgorithmTags.DSA, dsaKeyPair.getPrivateKey(), message);

  if (verifyDetachedSignature(dsaKeyPair.getPublicKey(), signature, message))
  {
      System.out.println("signature verified");
  }
  else
  {
      System.out.println("signature failed");
  }
```

假设没有发生任何错误，执行代码应该产生以下输出：

```
signature verified
```

表示已创建正确的签名，并且验证密钥已成功匹配到签名创建方法创建的签名列表中的签名。

### 文本数据签名

PGP 也支持对文本数据进行签名。在这种情况下，无论是否封装，要求都是文本数据必须经过规范化（canonicalized）——在此例中，这意味着签名中的行结束符始终被计算为`"\r\n"`，而不是平台可能使用的原生行结束符。我们在这里查看封装签名的生成（生成分离版本可以通过遵循上一节中对封装代码所做的更改来实现，但是针对文本签名）。值得注意的是，这里的规范化定义与用于明文签名（cleartext signatures）的规范化定义并不相同。我们将在下一节中介绍明文签名。

以下方法创建了一个文本类型的签名。

```java
  1   /**
 2    * 根据传入的签名密钥和数据创建一个 PGP 签名文本消息。
 3    *
 4    * @param signingAlg 要使用的签名算法。
 5    * @param signingKey 用于签签名的 PGP 私钥。
 6    * @param data 待签名的消息数据。
 7    * @return 签名消息的编码。
 9    */
10   public static byte[] createSignedMessage(
 11       int signingAlg, PGPPrivateKey signingKey, byte[] data)
 12       throws PGPException, IOException
 13   {
 14       ByteArrayOutputStream bOut = new ByteArrayOutputStream();
 15 
 16       // 创建一个写入签名的流。
 17       BCPGOutputStream bcOut = new BCPGOutputStream(bOut);
 18 
 19       // 设置签名生成器
 20       PGPSignatureGenerator sGen =
 21           new PGPSignatureGenerator(
 22               new JcaPGPContentSignerBuilder(signingAlg, PGPUtil.SHA384)
 23                   .setProvider("BC"));
 24 
 25       sGen.init(PGPSignature.CANONICAL_TEXT_DOCUMENT, signingKey);
 26 
 27       // 输出签名头
 28       // false 表示我们没有生成嵌套签名。
 29       sGen.generateOnePassVersion(false).encode(bcOut);
 31 
 32       // 创建字面数据记录（Literal Data record）
 33       PGPLiteralDataGenerator lGen = new PGPLiteralDataGenerator();
 34 
 35       OutputStream lOut = lGen.open(bcOut,
 36           PGPLiteralData.TEXT, PGPLiteralData.CONSOLE, data.length, new Date());
 37 
 38       for (int i = 0; i != data.length; i++)
 39       {
 40           lOut.write(data[i]);
 41           sGen.update(data[i]);
 42       }
 
 44       // 完成字面数据构造
 45       lOut.close();
 
 47       // 输出实际签名
 48       sGen.generate().encode(bcOut);
 
 50       // 关闭流。
 51       bcOut.close();
 
 53       return bOut.toByteArray();
 54   }
```

你可以看到它与二进制签名版本相比仅在两处不同：一处是第 25 行设置签名类型，另一处是第 35 行设置字面数据类型。常量`PGPLiteralData.TEXT` 翻译为值为‘t’的类型代码，这通常仅意味着 ASCII 文本。PGP 还为字面数据提供了一个类型为‘u’的类型代码，由`PGPLiteralData.UTF8` 表示。

你可能会想知道数据的规范化是在哪里处理的，因为在代码中似乎没有被显式处理。对于`CANONICAL_TEXT_DOCUMENT` 签名，`PGPSignatureGenerator` 类和`PGPSignature` 类都从内部处理了规范化。

验证消息的方法与之前相同。由于规范化将在内部处理，我们可以利用之前在查看验证封装二进制签名时所定义的`verifySignedMessage()`方法。

作为用法示例，以下代码段创建了消息和必要的密钥，以便使用`verifySignedMessage()` 创建并验证签名消息，并在验证成功时打印消息数据。

```java
 // 平台无关的文本消息生成器
      ByteArrayOutputStream bOut = new ByteArrayOutputStream();
      BufferedWriter bWrt = new BufferedWriter(new OutputStreamWriter(bOut));
      bWrt.write("Hello, world!");
      bWrt.newLine();
      bWrt.close();

      byte[] message = bOut.toByteArray();

      KeyPair dsaKp = DsaUtils.generateDSAKeyPair();
      PGPKeyPair dsaKeyPair = new JcaPGPKeyPair(PGPPublicKey.DSA, dsaKp, new Date());

      byte[] signedMessage = createSignedMessage(
          PublicKeyAlgorithmTags.DSA, dsaKeyPair.getPrivateKey(), message);

      ByteArrayOutputStream recStream = new ByteArrayOutputStream();

      if (verifySignedMessage(dsaKeyPair.getPublicKey(), signedMessage, recStream))
      {
          System.out.print(Strings.fromByteArray(recStream.toByteArray()));
      }
```

使用提供的方法运行该代码段也应该产生：

```
Hello, world!
```

这意味着消息流解析正确，签名通过验证，且封装的消息也成功恢复。

### 明文签名

明文签名在 RFC 4880 的第 7 节中有介绍。它们背后的想法是提供一种类似于我们在 S/IME 中看到的签名多部分（signed multipart）机制——即在不需要任何软件解析的情况下即可读取的签名消息。尽管对该概念持有保留意见，但有很多基于 PGP 的应用程序生成或期望使用明文签名。

#### 创建明文签名

与签名文本数据一样，为了产生可以被验证的明文签名，也需要规范化。在这种情况下，规范化过程比以前更复杂，因为消息包含了装护（armoring），所以行首的破折号必须转义，装护之前的最后一个行结束符需要在签名计算中被忽略，且行尾的空格也应该被忽略。

幸运的是，这些内容大部分可以透明地处理，并由用于生成明文签名的`ArmoredOutputStream` 类支持。然而，识别哪些内容放入签名对象仍然需要用户的参与，因此需要一些代码来为这些签名提供必要的底层支持，特别是当在处理过程中不能更改行结束符的消息时。

以下工具代码允许在输出中保留行结束符，同时处理规范化并忽略待签名数据每行末尾的空白。

```java
  1 // 如果 b 是空白字符，则返回 true。
  static boolean isWhiteSpace(
      byte b)
  {
      return b == '\r' || b == '\n' || b == '\t' || b == ' ';
  }

  // 注意：根据 RFC 4880 第 7.1 节，计算签名时
  // 需要移除每行末尾的空白字符。
  static int getLengthWithoutWhiteSpace(
      byte[] line)
  {
      int end = line.length - 1;

      while (end >= 0 && isWhiteSpace(line[end]))
      {
          end--;
      }

      return end + 1;
  }

  // 将行的头部字节添加到签名生成器中，
  //并将整行写入输出流。
  private static void processLine(
      PGPSignatureGenerator sGen, OutputStream aOut, byte[] line)
      throws IOException
  {
      // 移除尾尾空白。
      int length = getLengthWithoutWhiteSpace(line);
      if (length > 0)
      {
          sGen.update(line, 0, length);
      }

      aOut.write(line, 0, line.length);
  }

  // 读取一行输入，处理各种换行符。
  private static byte[] readInputLine(
      InputStream fIn)
      throws IOException
  {
      ByteArrayOutputStream bOut = new ByteArrayOutputStream();

      int ch;

      while ((ch = fIn.read()) >= 0)
      {
          bOut.write(ch);
          if (ch == '\r')
          {
              fIn.mark(1);
              if ((ch = fIn.read()) == '\n')
              {
                  bOut.write(ch);
              }
              else
              {
                  fIn.reset();
              }
              return bOut.toByteArray();
          }
          else if (ch == '\n')
          {
              return bOut.toByteArray();
          }
      }

      return null;
  }
```

如你所见，保留换行符确实增加了一些复杂度。你可以考虑你的 PGP 明文签名应用是否需要如此通用。如果你的应用并不需要，它将简化代码。

借助于上面定义的 `readInputLine()` 和 `processLine()` 方法，一个根据给定的私钥、摘要算法和某些输入数据生成明文签名的方法示例可能如下：



```java
  1 /**
  2  * 从传入输入流创建明文签名文档。
  3  *
  4  * @param pgpPrivKey 用于签名的私钥。
  5  * @param digest 用于创建签名的摘要算法。
  6  * @param msgIn 中要包含并签名的输入。
  7  * @param clrOut 用于写入明文签名文档的输出流。
  8  */
  9  public static void createCleartextSignature(
  10      PGPPrivateKey pgpPrivKey, int digest, InputStream msgIn, OutputStream clrOut)
  11      throws PGPException, IOException
  12  {
  13      BufferedInputStream mIn = new BufferedInputStream(msgIn);

  15      // 设置签名生成器。
  16      int keyAlgorithm = pgpPrivKey.getPublicKeyPacket().getAlgorithm();
  17      PGPSignatureGenerator sGen = new PGPSignatureGenerator(
  18          new JcaPGPContentSignerBuilder(keyAlgorithm, digest).setProvider("BC"));

  20      sGen.init(PGPSignature.CANONICAL_TEXT_DOCUMENT, pgpPrivKey);

  22      // 创建明文文档。
  23      ArmoredOutputStream aOut = new ArmoredOutputStream(clrOut);

  25      aOut.beginClearText(digest);

  27      //
  28      // 注意，文件中最后一个 \n/\r/\r\n 会被忽略
  29      //
  30      byte[] line = readInputLine(mIn);

  32      processLine(sGen, aOut, line);

  34      while ((line = readInputLine(mIn)) != null)
  36      {
  36          sGen.update((byte)'\r');
  37          sGen.update((byte)'\n');

  39          processLine(sGen, aOut, line);
  40      }

  42      // 结束明文数据
  43      aOut.endClearText();
  44      // 输出签名
  45      sGen.generate();
  46  }
```

```java
 1   /**

 2    * 验证传入的明文签名文档，如果成功则返回 true 和数据的

 3    * 副本，否则返回 false。

 4    *

 5    * @param publicKey 用于验证签名的公钥。

 6    * @param in 包含明文签名文档的输入流。

 7    * @param msgOut 用于保存签名数据的输出流。

 8    * @return 如果文档通过验证，则返回 true，否则返回 false。

 9    */

10   public static boolean verifyCleartextSignature(

11       PGPPublicKey publicKey, InputStream in, OutputStream msgOut)

12       throws IOException, PGPException

13   {

14       ArmoredInputStream aIn = new ArmoredInputStream(in);

15 

16       // 保存一份文本的副本以供验证

17       ByteArrayOutputStream bOut = new ByteArrayOutputStream();

18 

19       int ch;

20       while ((ch = aIn.read()) > 0 && aIn.isClearText())

21       {

22           bOut.write(ch);

23       }

24 

25       //

26       // 加载 "PGP SIGNATURE" 块中的签名记录。

27       //

28       JcaPGPObjectFactory pgpFact = new JcaPGPObjectFactory(aIn);

29       PGPSignatureList p3 = (PGPSignatureList)pgpFact.nextObject();

30       PGPSignature sig = p3.get(0);

31 

32       if (publicKey.getKeyID() != sig.getKeyID())

33       {

34           throw new PGPException("文档中的公钥不用于签名");

35       }

36 

37       sig.init(

38          new JcaPGPContentVerifierBuilderProvider().setProvider("BC"), publicKey);

39 

40       //

41       // 读取输入，确保我们忽略了最后一个换行符。

42       //

43       InputStream sigIn = new ByteArrayInputStream(bOut.toByteArray());

44 

45       processInput(sig, sigIn);

46 

47       if (sig.verify())

48       {

49           msgOut.write(bOut.toByteArray());

50           msgOut.flush();

51 

52           return true;

53       }

54 

55       return false;

56   }
```

你可以在第 32 行看到签名中的密钥 ID 会与提供的公钥进行校验。为了示例的简单起见，我们假设已经知道该密钥，因为只有当你解析了与明文签名文档相关的签名块时，才能确定使用了哪个密钥来生成签名。如你所见，签名中存储了密钥 ID，因此对该方法的简单修改是传递一个适当授权的公钥表。

除了需要公钥之外，使用 `verifyCleartextSignature()` 实际上只需要一个 `OutputStream` 来存储签名数据。下面的代码片段演示了如何使用 `verifyCleartextSignature()` 方法：

```java
 ByteArrayOutputStream msgOut = new ByteArrayOutputStream();

      if (verifyCleartextSignature(

              dsaKeyPair.getPublicKey(),

              new ByteArrayInputStream(sigOut.toByteArray()),

              msgOut))

      {

          System.out.println(Strings.fromByteArray(msgOut.toByteArray()));

      }

      else

      {

          System.out.println("消息验证失败");

      }
```

假设一切进展顺利，如果你将它与之前的文档创建片段一起运行，你应该会看到以下输出。

```
Hello, world!
```

当然，在“现实世界”中，事情可能并不计划进行。假设公钥是正确的且其他一切看起来都是正确的，可能仅仅是因为你正在处理一个遗留应用程序。在这种情况下，值得检查发送端和你的应用程序对所使用的规范一化方法是否达成一致（假设公钥与签名匹配且其他一切看起来正常）。虽然 RFC 4880 记录了应该采取的标准方法，但遗留应用程序生成签名时，末尾空格或换行符有时会被包含在签名中，这并不罕见。有时需要进行微调才能使其正常工作。

### 公钥加密

使用 PGP 的公钥加密遵循通常模式：为对称算法生成会话密钥，然后使用会话密钥加密数据，并使用接收者的公钥加密会话密钥。随后将加密的会话密钥和加密数据发送给接收者，然后使用接收者的私钥恢复原始明文。

这里有一个执行公钥加密的方法。请阅读一遍，然后我们将逐步进行分析。

```java
 1   /**

 2    * 使用 AES-256 会话密钥和传入的

 3    * 公钥创建一个加密数据数据块。

 4    *

 5    * @param encryptionKey 要使用的公钥。

 6    * @param data 要加密的数据。

 7    * @return 加密数据的 PGP 二进制编码版本。

 8    */

 9   public static byte[] createEncryptedData(

10       PGPPublicKey encryptionKey,

11       byte[] data)

12       throws PGPException, IOException

13   {

14       PGPEncryptedDataGenerator encGen = new PGPEncryptedDataGenerator(

15           JceDataEncryptorBuilder(SymmetricKeyTags.AES_256)

16               .setIntegrityPacket(true)

17               .setRandom(new SecureRandom()).setProvider("BC"));

18 

19       encGen.addMethod(

20           new JcePublicKeyEncryptionGenerator(encryptionKey)

21               .setProvider("BC"));

22 

23       ByteArrayOutputStream encOut = new ByteArrayOutputStream();

24 

25       // 创建无限长度加密流

26       OutputStream cOut = encGen.open(encOut, new byte[4096]);

27 

28       // 写入字面数据

29       PGPLiteralDataGenerator lData = new PGPLiteralDataGenerator();

30       OutputStream pOut = lData.open(cOut, PGPLiteralData.BINARY,

31           CONSOLE, data.length, new Date());

32       pOut.write(data);

33       pOut.close();

34 

35       // 完成加密

36       cOut.close();

37 

38       return encOut.toByteArray();

39   }
```

该代码遵循几个简单的步骤：设置 `PGPEncryptedDataGenerator`，包括添加用于加密会话密钥的方法。接下来写入数据，最后完成。

`PGPEncryptedDataGenerator` 的设置涵盖了第 14 到 21 行。第一部分（从 14 到 17 行）指定了用于加密我们要处理数据的对称密钥算法，并指定了使用完整性包。完整性包在 RFC 4880 的第 5.13 节中有详细讨论，但简短描述是指定 `true` 会在加密数据流末尾添加一个 SHA-1 哈希值。通常情况下，如果可以，你会希望使用完整性包，特别是当数据没有被签名时。

`PGPEncryptedDataGenerator` 设置的第二部分是第 19 到 21 行——对 `addMethod()` 函数的调用。你可能认为这看起来与 CMS 中看到的添加的接收者信息非常相似，你的想法是。

实际加密数据的步骤位于第 26 行到第 37 行之间。调用 `encGen.open()` 用于初始化一个流，该流将加密我们写入它的任何数据 - 在情况下，它接收一个大小为 `4096` 的缓冲区，用于确定无限长度加密流的内部块大小。在第 29 行到 34 行，由于我们关注的是 PGP 协议，我们构建了一个字面数据对象，并将数据写入其中。最后在第 37 行，通过关闭所有内容结束结束，并返回加密数据消息的编码。

解密结果数据遵循我们在 `CMSEncryptedData` 中看到的相同模式。识别与你想要使用的密钥匹配的接收者，然后读取数据，或者在这种情况下，读取封装数据的 `Literal Data` 结构。

以下代码提供了一个如何使用接收者私钥从 PGP 加密数据恢复明文的示例。

```java
 1   /**

 2    * 从传入的 PGP 加密数据编码中提取明文数据。

 3    * 程序假设传入的私钥与编码中的第一个 

 4    * 加密数据对象匹配。

 5    *

 6    *

 7    * @param privateKey 用于解密会话密钥的私钥。

 8    * @param pgpEncryptedData PGP 加密数据的编码。

 9    * @return 返回一个包含解密后数据的字节数组。

10    */

 11   public static byte[] extractPlainTextData(

 12       PGPPrivateKey privateKey,

 13       byte[] pgpEncryptedData)

 14       throws PGPException, IOException

 15   {

 16       PGPObjectFactory pgpFact = new JcaPGPObjectFactory(pgpEncryptedData);

 17 

 18       PGPEncryptedDataList encList = (PGPEncryptedDataList)pgpFact.nextObject();

 19 

 20       // 寻找匹配的公钥加密数据包。

 21       PGPPublicKeyEncryptedData encData = null;

 22       for (PGPEncryptedData pgpEnc: encList)

 23       {

 24           PGPPublicKeyEncryptedData pkEnc

 25               = (PGPPublicKeyEncryptedData)pgpEnc;

 26           if (pkEnc.getKeyID() == privateKey.getKeyID())

 27           {

  28               encData = pkEnc;

  29               break;

  30           }

  31       }

  32 

  33       if (encData == null)

  34       {

  35           throw new IllegalStateException("未找到匹配的加密数据");

  36       }

  37 

  38       // 构建解密器工厂

  39       PublicKeyDataDecryptorFactory dataDecryptorFactory =

  40           new JcePublicKeyDataDecryptorFactoryBuilder()

  41               .setProvider("BC")

  42               .build(privateKey);

  43 

  44       InputStream clear = encData.getDataStream(dataDecryptorFactory);

  45       byte[] literalData = Streams.readAll(clear);

  46       clear.close();

  47 

  48       // 检查解密是否正常

  49       if (encData.verify())

  50       {

  51           // 解析字面数据

  52           PGPObjectFactory litFact = new JcaPGPObjectFactory(literalData);

  53           PGPLiteralData litData = (PGPLiteralData)litFact.nextObject();
```



与签名一样，我们使用 PGP 密钥 ID 来匹配持有封装会话密钥的加密块与我们拥有的私钥。注意迭代循环有一个类型为 `PGPEncryptedData` 的循环变量。我们在这里不能使用 `PGPPublicKeyEncryptedData`，因为还有一种用于基于 PBE 密钥的类型，我们将在下一节中查看。

`extractPlainTextData()` 的第 49 行是检查检查完整性包以确认加密数据未被篡改的地方。一旦我们确认没有明显的篡改，就可以安全地解析 `LiteralData` 结构并将封装的数据返回给用户。如果 `encData.verify()` 语句返回 `false`，我们就知道出了问题并抛出异常。请记住，由于 Bouncy Castle PGP API 是流式 API，且完整性包位于流的末尾，因此 `encData.verify()` 方法只能在加密数据被完全处理后才能调用。如果你过早调用 `verify()`，该方法将在内部为你读取流，如果你计划自己处理数据，这可能不是你想要的结果！

如果你正在处理可能没有完整性保护包的 PGP 加密数据，可以调用布尔方法 `PGPEncryptedData.isIntegrityProtected()` 来告知你检查是否可行。如果你对未完整性保护的加密数据调用 `PGPEncryptedData.verify()`，API 将假设最坏的情况并抛出异常。

### 使用 Elgamal 公钥

PGP 支持多种公钥算法。最旧的算法是 RSA 和 Elgamal，它们都使用 PKCS#1 编码来封装对称密钥(22)。以下代码片段展示了如何使用 Elgamal。

```java
byte[] msg = Strings.toByteArray("Hello, world!");

KeyPairGenerator kpGen = KeyPairGenerator.getInstance("DH");

kpGen.initialize(2048);

KeyPair kp = kpGen.generateKeyPair();

PGPKeyPair elgKp = new JcaPGPKeyPair(PGPPublicKey.ELGAMAL_CRYPT, kp, new Date());

byte[] encData = createEncryptedData(elgKp.getPublicKey(), msg);

byte[] decData = extractPlainTextData(elgKp.getPrivateKey(), encData);
```

### 使用 ECDH 公钥

虽然 RFC 4880 没有谈论椭圆曲线加密，但更新后的 RFC 6637 (6) 提供了使用椭圆曲线的公钥加密。如你预期的，这是基于 Diffie-Hellman 的，但与 CMS 不同，它不需要特殊的接收者，PGP 协议允许支持 EC 的新代码片段。

```java
byte[] msg = Strings.toByteArray("Hello, world!");

KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");

kpGen.initialize(new ECParameterSpec("P-256"));

KeyPair kp = kpGen.generateKeyPair();

PGPKeyPair ecdhKp = new JcaPGPKeyPair(PGPPublicKey.ECDH, kp, new Date());

byte[] encData = createEncryptedData(ecdhKp.getPublicKey(), msg);

byte[] decData = extractPlainTextData(ecdhKp.getPrivateKey(), encData);

System.out.println(Strings.fromByteArray(decData));
```

你可以看到，唯一的改变在于 `KeyPairGenerator` 的创建以及加密步骤中指定的算法。如果你想在上述方法中使用 RSA，只需将 `"DH"` 替换为 `"RSA"`，并使用 `PGPPublicKey.RSA_CRYPT` 代替 `PGPPublicKey.ELGAMAL_CRYPT`。输出如下：

```
Hello, world!
```

### 关于公钥加密的最后说明

只有一个 `PGPEncryptedData` 对象的公钥加密消息实际上很少见。通常有两个密钥，因为发送者经常也会加密消息以便以后解密。

### PBE 加密

PGP 还通过使用与公钥加密不同的加密对象支持基于密码的加密。Bouncy Castle 通过 `JcePBEKeyEncryptionMethodGenerator` 支持 PBE 方法，它在构造函数中接收密码，并在内部完成封装会话密钥的工作。

以下方法展示了 `JcePBEKeyEncryptionMethodGenerator` 的用法。在阅读代码时你会注意到，虽然字面数据的处理方式不同，但只有添加到 `PGPEncryptedDataGenerator` 中的方法与我们之前看到的公钥方法示例有所不同。建立所使用的数据加密器和会话密钥的代码是相同的。

```java
/**
   * 使用基于 PBE 的密钥封装的 AES-256 密钥创建一个加密数据块。
   *
   * @param passwd 用于生成基于 PBE 密钥的密码。
   * @param data 要加密的数据。
   * @return 加密数据的 PGP 二进制编码版本。
   */

public static byte[] createPBEEncryptedData(
    char[] passwd,
    byte[] data)
    throws PGPException, IOException
{
    // 创建包含明文的封包。
    ByteArrayOutputStream bOut = new ByteArrayOutputStream();
    PGPLiteralDataGenerator lData = new PGPLiteralDataGenerator();
    OutputStream pOut = lData.open(
        bOut, PGPLiteralData.BINARY, PGPLiteralData.CONSOLE,
        data.length, new Date());
    pOut.write(data);
    pOut.close();
    byte[] plainText = bOut.toByteArray();

    // 设置生成器
    PGPEncryptedDataGenerator encGen = new PGPEncryptedDataGenerator(
        new JcePGPDataEncryptorBuilder(SymmetricKeyAlgorithmTags.AES_256)
            .setWithIntegrityPacket(true)
            .setSecureRandom(new SecureRandom())
            .setProvider("BC"));
    encGen.addMethod(
        new JcePBEKeyEncryptionMethodGenerator(passwd).setProvider("BC"));

    // 加密步骤。
    ByteArrayOutputStream encOut = new ByteArrayOutputStream();
    OutputStream cOut = encGen.open(encOut, plainText.length);
    cOut.write(plainText);
    cOut.close();
    return encOut.toByteArray();
}
```

注意，传入 `JcePBEKeyEncryptionMethodGenerator` 的唯一内容是密码，在这种情况下，这意味着密码将使用基于 `SHA-1` 的算法转换为密钥。也可以通过向构造函数传递一个 `PGPDigestCalculator` 来指定用于转换密码的算法。

字面数据处理上的区别是为了展示如何创建一个固定长度的加密对象，而不是我们之前使用的无限长度对象。预计算明文允许我们使用 `open()` 方法，该方法接收的是长度而非缓冲区。当然，我们本也可以使用无限长度版本的 `open()` 方法。同样，在之前的公钥示例中，我们也可以使用定义长度的方法。

在提取代码案例中，我们需要识别 `PGPEncryptedData` 的一个不同子类，即基于 PBE 的数据类型——`PGPPBEEncryptedData`。该类型没有关联的 ID，因此如果你需要在同一段代码中处理公钥加密数据和 PBE 加密数据，将需要依赖 `instanceof` 来区分它们。

以下是处理基于 PBE 的解密代码。

```java
/**
   * 从传入的 PGP 加密数据编码中提取明文数据。
   * 该程序假设密码与编码中的第一个加密数据对象匹配。
   *
   * @param passwd 用于生成基于 PBE 密钥的密码。
   * @param pgpEncryptedData PGP 加密数据的编码。
   * @return 包含解密数据的字节数组。
   */

public static byte[] extractPlainTextPBEData(
    char[] passwd,
    byte[] pgpEncryptedData)
    throws PGPException, IOException
{
    PGPEncryptedDataList encList = new PGPEncryptedDataList(pgpEncryptedData);
    // 假设 PBE 加密数据在第一个。
    PGPPBEEncryptedData encData = (PGPPBEEncryptedData)encList.get(0);
    PBEDataDecryptorFactory dataDecryptorFactory =
        new JcePBEDataDecryptorFactoryBuilder()
            .setProvider("BC")
            .build(passwd);
    InputStream clear = encData.getDataStream(dataDecryptorFactory);
    byte[] literalData = Streams.readAll(clear);
    clear.close();
    // 检查解密是否正常
    if (encData.verify())
    {
        PGPLiteralData litData = new PGPLiteralData(literalData);
        return Streams.readAll(litData.getInputStream());
    }
    throw new IllegalStateException("modification failed");
}
```

注意，我们假设 `PGPPBEEncryptedData` 对象是 `PGPEncryptedDataList` 中的第一个。`JcePBEDataDecryptorFactoryBuilder` 在构造时可以传递摘要计算器，以便仅对指定的 provider 用于加密。

以下示例代码将测试 PBE 加密器和解密器。

```java
byte[] msg = Strings.toByteArray("Hello, PBE world!");
char[] password = "secret".toCharArray();
byte[] encData = createPBEEncryptedData(password, msg);
byte[] decData = extractPlainTextPBEData(password, encData);
System.out.println(Strings.fromByteArray(decData));
```

运行后应产生以下输出：

```
Hello, PBE world!
```

### Keybox 文件

Keybox 文件是在 GnuPG 2.1 中引入的，主要为了解决在 `pubring.gpg` 中存储大量公钥时出现的性能问题。在使用 Keybox 文件的地方，你会发现是 `pubring.kbx` 文件而不是旧式的 `pubring.gpg`。

#### Keybox Blob

Keybox 文件将公钥数据作为一系列带有关联元数据的块存储。正是元数据允许了更快的解析。对于我们的用途，最有趣的 blob 通常包含两种格式的公钥数据：作为 X.509 证书的公钥数据或原始 PGP 编码格式的公钥数据。有 4 种 blob 类型：Empty blob、First blob、Open-PGP blob 和 X.509 blob。Empty blob 是预期的无数据 blob。First blob 是 Keybox 文件中的第一个 blob，包含头和版本信息。Open-PGP blob 包含一个 PGP 编码公钥环及其相关的元数据，而 X.509 blob 包含一个 X.509 公钥证书及其相关的元数据。在 Bouncy Castle API 中，后两者分别由 `CertificateBlob` 和 `PublicKeyRingBlob` 表示，并共享共同基类 `KeyBlob`，该基类提供了相应 blob 中元数据的访问方法。

#### 加载 Keybox 文件

你可以将 Keybox 文件视为 blob 列表，一个从该文件加载所有密钥数据的示例方法如下：

```java
/**
 * 加载 KeyBox 文件中所有的密钥环和证书。
 *
 * @param keyBox 要加载的 KeyBox。
 * @return 在密钥框中找到的 PGP 公钥环和 X.509 证书的列表。
 */
public static List<Object> loadKeyBoxKeys(KeyBox keyBox)
    throws Exception
{
    List<Object> publicObjects = new ArrayList<Object>();
    for (KeyBlob keyBlob : keyBox.getKeyBlobs())
    {
        switch (keyBlob.getType())
        {
        case X509_BLOB:
            {
            byte[] certData = ((CertificateBlob)keyBlob).getEncodedCertificate();
            CertificateFactory factory = CertificateFactory.getInstance("X509");
            publicObjects.add(factory.generateCertificate(
                                            new ByteArrayInputStream(certData)));
            }
            break;
        case OPEN_PGP_BLOB:
            publicObjects.add(((PublicKeyRingBlob)keyBlob).getPGPPublicKeyRing());
            break;
        default:
            throw new IllegalStateException(
                          "Unexpected blob type: " + keyBlob.getType());
        }
    }
    return publicObjects;
}
```

创建实际的 `KeyBox` 对象是通过构建器完成的 - 因为解析公钥信息需要使用加密服务，你可能希望指定一个特定的提供者。在向构建器指定提供者后，你可以通过如下提供字节编码（或 `InputStream`）来生成 `KeyBox`：



KeyBox kbx = new JcaKeyBoxBuilder().setProvider("BC").build(kbxData);

其中 `kbxData` 是包含密钥框编码的 `byte[]` 或 `InputStream`。

一旦完成上述操作，你就可以像这样将密钥块作为对象列表进行检索了：

```
List<Object> kbxObjs = loadKeyBoxKeys(kbx);
```

请记住，如果你正在编写解析 `.kbx` 文件的代码，如果需要，你可以跳过某些 blob 而不对其进行完全解析。因此，如果你需要处理大量的 blob，通过跳过流并利用每个 `KeyBlob` 上的元数据来选择正确的 blob 然后再扫描数据，将会要快得多。

### 使用 S 表达式处理私钥

除了使用 `.kbx` 文件外，GnuPG 还引入了使用 S 表达式来存储私钥，作为旧版 `secring.gpg` 文件中使用 PGP 编码的替代方案。顾名，S 表达式是 Lisp S 表达式的变体，最初由 Ron Rivest 和 Butler Lampson 等人在麻理工学院（MIT）在 20 世纪 90 年代后期提出的密钥编码 [9]。该格式的细节见《Libgcrypt 参考手册》的第 6.2 节 [10]，并在 `keyformat.txt` 文件中还有一些额外信息 [11]。

一个简单的总结是，S 表达式编码密钥中的值字段遵循以下编码格式：`length:value_bytes`。结构可以通过在左、右括号中包含字段的连接来构建。长度字段是 ascii 格式（例如，字符串 `ecc` 被编码为 `3:ecc`），但 `value_bytes` 可以是二进制数据，因此使用 S 表达式语法编码的 PGP 密钥在文本编辑器中无法完全可读，特别是在加密的情况下。

Bouncy Castle 现在提供了一个用于读取这些文件的解析器 `SExprParser`。该类在构造时需要一个 `PGPDigestCalculatorProviderBuilder`，因为某些密钥在写入 S 表达式时包含了密钥的消息摘要（message digest）。其使用方法非常简单，因为每个文件只能包含一个密钥。以下是调用解析器的示例：

```
PGPSecretKey secretKey = new SExprParser(
         new JcaPGPDigestCalculatorProviderBuilder().build()).parseSecretKey(
                     inputStream,
                     new JcePBEProtectionRemoverFactory("test".toCharArray()),
                     new JcaKeyFingerprintCalculator());
```

某些方法参数的需要是显而易见的，`inputStream` 是一个包含加密私钥的流，而在构建 `PGPSecretKey` 对象时，需要 `JcaFingerPrintCalculator` 来计算密钥的指纹。新类 `JcePBEProtectionRemoverFactory` 是必需的，因为与旧的 PGP 私钥编码不同，S 表达式通常将 PGP 私钥存储为加密 blob，因此需要密码来解密 PGP 私钥。通常这意味着 PGP 私钥携带的 `PGPPrivateKey` 可以被提取出来，而无需使用 `PBESecretKeyDecryptor`，因此可以传递 `null`，如下所示：

```
PGPPrivateKey privateKey = secretKey.extractPrivateKey(null);
```

### 总结

在本章中，我们检查了另一种在互联网上广泛使用的加密协议 - OpenPGP。

我们看到 OpenPGP 在许多方面与……相似，我们看到 GnuPG 的最新进展为引入 `.kbx` 文件格式提供了一些范围。

## 第 14 章：传输层安全 (Transport Layer Security)

## 引言

本章是关于如何使用 Bouncy Castle TLS API 和 JSSE 提供者的指南。JSSE 提供者遵循与 JCA 类似的模型。TLS API 提供了一种使用协议的底层机制，这比 JSSE 提供的更灵活，但对开发者的知识要求更高。该提供者构建在 TLS API 之上。

### 安装

bctls jar 可以安装在 JRE/JDK 的 `jre/lib/ext` 中，或者在许多情况下，安装在运行程序的通用类路径上。如果你将 bctls jar 安装在类路径上，请注意，取决于应用程序其他地方加载 JSSE 提供元素，系统类加载器可能无法使用 bctls jar 中的类而产生异常。

#### 安装 BCJSSE 提供者到 JRE

一旦安装了 bctls jar，如果应用程序全局需要，可能需要安装 `BouncyCastleJsseProvider` 类。可以通过静态方式在 JVM 中安装提供者，将其添加到 JRE/JDK `jre/lib/security` 目录下的 `java.security` 文件中。提供者也可以在执行期间添加。如果你希望在执行期间全局地添加提供者，可以在代码中添加以下导入：

```
import java.security.Security
import org.bouncycastle.jsse.provider.BouncyCastleJsseProvider
```

然后插入行：

```
Security.addProvider(new BouncyCastleJsseProvider());
```

随后可以通过引用 `BCJSSE` 名称来使用该提供者，例如：

```
SSLContext clientContext = SSLContext.getInstance("TLS", "BCJSSE");
```

或者，如果你不想全局安装提供者，而是在本地使用，可以将提供者传递给你正在创建实例的 JSSE 类的 `getInstance()` 方法。例如：

```
SSLContext clientContext = 
    SSLContext.getInstance("TLS", new BouncyCastleJsseProvider());
```

#### 在 FIPS 模式下配置 BCJSSE 提供者

`BCJSSE` 提供者具有 `FIPS` 模式，该模式限制提供者仅使用符合 `FIPS` 标准的 TLS 客户端或服务器设置中提供的密码套件和参数。`FIPS` 模式通过向 `BouncyCastleJsseProvider` 类的构造函数传递字符串 `"fips:<provider>"` 来指定，可以在运行时通过 `JVM` 的 `java.security` 文件设置。`<provider>` 的可用值包括 `"default"`，表示将根据 `JVM` 的提供者优先级列表使用提供者。可以使用提供者名称，例如 `"BC"`，或者如果你在使用 Bouncy Castle FIPS 提供者，则可以使用 `"BCFIPS"`。当使用特定的提供者名称时，执行加密操作时，`BCJSSE` 提供者仅接受来自该提供者的算法。

例如，如果我们想使用 `BCFIPS` 提供者，并使用设置为 `FIPS` 模式的 `BCJSSE` 提供者，而不是仅仅在 `JVM` 的 `java.security` 文件的 `security.provider` 部分中包含以下内容：

```
security.provider.1=org.bouncycastle.jcajce.provider.BouncyCastleFipsProvider
security.provider.2=org.bouncycastle.jsse.provider.BouncyCastleJsseProvider
security.provider.3=sun.security.provider.Sun
```

相反，最少安装还需要在第二行末尾包含 `"fips:BCFIPS"` 声明：

```
security.provider.2=org...provider.BouncyCastleJsseProvider fips:BCFIPS
```

在运行时，可以使用以下实现类似的配置：

```
Security.addProvider(new BouncyCastleJsseProvider("fips:BCFIPS"));
```

### BCJSSE 和 JSSE 提供者之间的其他差异

`BCJSSE` 提供者产生的 `TrustManager` 对象将忽略传递到其工厂的任何 `KeyStores` 中的私钥。只有 `KeyStore` 中的简单证书条目会被用于创建 `TrustManager`。`BCJSSE` 在非 `FIPS` 模式下也支持 `ChaCha20` 和 `Poly1305`。`BCFIPS` 提供者从 `1.0.2` 版本开始支持该密码套件。

后续有一份安全属性列表，对于普通的 `JSSE`，如果属性不存在，它们通常被视为未设置。由于 `BCJSSE` 运行在各种 `JVMs` 上，如果 `BCJSSE` 处理的属性未设置，它通常会根据最新 `JVM` 中使用的内容提供默认设置。

### 约定

#### `getDefault()` 的使用

如 `SSLSocketFactory.getDefault()` 等方法只有在 `BCJSSE` 提供者优先或替换了普通的 `JRE` `JSSE` 提供者时，才会返回后者的类。

#### 实例名称

核心 `KeyManagerFactory` 的实例名称为 `"X.509"`，别名为 `"X509"` 和 `"PKIX"`。核心 `TrustManagerFactory` 的实例名称为 `"PKIX"`，别名为 `"X.509"` 和 `"X509"`。`SSLContext` 实例适用于 `"TLSv1"`、`"TLSv1.1"` 和 `"TLSv1.2"`。在每情况下，实例名称代表支持的最低 TLS 版本，并且也支持更高版本。`SSLContext` 实例名称 `"TLS"` 和 `"DEFAULT"` 提供对 `"TLSv1.2"` 的支持。

### 准备工作 - 简单协议

TLS 显然不是目的本身。总是假设在其上有内容正在通信。以下类提供了一个简单的协议，我们的示例可以使用该协议，其中消息以 `'!'` 字符结束。

```java
 1 /**
 2  * 用于执行的简单协议。
 3  */
 4 public class Protocol
 5 {
 6     private static Logger LOG = Logger.getLogger(Protocol.class.getName());
 7 
 8     /**
 9      * 执行 '!' 协议 - 客户端侧。
 10      */
 11     static void doClientSide(
 12         Socket cSock)
 13         throws IOException
 14     {
 15         OutputStream out = cSock.getOutputStream();
 16         InputStream in = cSock.getInputStream();
 17         out.write(Strings.toByteArray("world"));
 18         out.write('!');
 19         int ch = 0;
 20         while ((ch = in.read()) != '!')
 21         {
 22             System.out.print((char)ch);
 23         }
 24         System.out.println((char)ch);
 25     }
 
 26     /**
 27      * 执行 '!' 协议 - 服务端侧。
 28      */
 29     static void doServerSide(
 30         Socket sSock)
 31         throws IOException
 32     {
 33         LOG.log(Level.INFO, "session started.");
 34         InputStream in = sSock.getInputStream();
 35         OutputStream out = sSock.getOutputStream();
 36         out.write(Strings.toByteArray("Hello, "));
 37         int ch = 0;
 38         while ((ch = in.read()) != '!')
 39         {
 40             out.write(ch);
 41         }
 42         out.write('!');
 43         sSock.close();
 44         LOG.log(Level.INFO, "session closed.");
 45 }
 46 }
```

你可以看到该协议是双向的，客户端连接并发送消息，然后读取服务器发送的内容并将其打印到标准输出。在初始消息后，服务器方法回显它收到的内容，直到收到 `'!'`，然后发送自己的终止 `'!'`。客户端方法发送消息的半部分，然后读取回显内容直到也收到 `'!'` 并退出。这足以证明连接已经发生。

### 基础 TLS 服务器

基础服务器只需要一个 `KeyManager` 来标识身份。实际的 `KeyManager` 然后通过 `KeyManagerFactory` 创建，该工厂使用服务器的密钥库和密钥库密码初始化。

```java
public static final int PORT_NO = 9090;
public static final char[] ID_STORE_PASSWORD = "passwd".toCharArray();
```

```java
/**
 * 创建一个包含单个自签名证书密钥的密钥库。
 *
 * @return 包含单个自签名证书密钥的密钥库。
 */
public static KeyStore createIdentityKeyStore()
    throws Exception
{
    PrivateCredential cred = createSelfSignedCredentials();
    KeyStore store = KeyStore.getInstance("JKS");
    store.load(null, null);
    store.setKeyEntry("identity", cred.getPrivateKey(), ID_STORE_PASSWORD,
                              new Certificate[]{cred.getCertificate()});
    return store;
}
```

注意：在这种情况下，我们假设 `BC` 和 `BCJSSE` 提供者刚刚被添加到提供者列表中 - 没有尝试替换普通的 `JSSE` 提供者，因此 `SSLSocketFactory.getDefault()` 仍然指向普通的 `JSSE` 提供者。

```java
/**
 * 基础 TLS 服务端 - 使用 '!' 协议。
 */
public class BasicTLSServer
{
    private static Logger LOG = Logger.getLogger(BasicTLSServer.class.getName());
    private final CountDownLatch readyLatch = new CountDownLatch(1);
    private final KeyStore serverStore;
    private final char[] passwd;

    /**
     * 基础服务器构造函数。
     *
     * @param serverStore 服务器的公钥/私钥。
     * @param passwd 用于解锁 serverStore 中私钥的密码。
     */
    BasicTLSServer(KeyStore serverStore, char[] passwd)
    {
        this.serverStore = serverStore;
        this.passwd = passwd;
    }

    /**
     * 建立服务端 TLS 连接的任务。
     */
    public void start()
        throws InterruptedException
    {
        new Thread(new ServerTask()).start();
        readyLatch.await();
    }

    /**
     * 建立服务端 TLS 连接的任务任务。
     */
    private class ServerTask
        implements Runnable
    {
        public void run()
        {
            try
            {



SSLContext sslContext = SSLContext.getInstance("TLS", "BCJSSE");

KeyManagerFactory keyMgrFact = KeyManagerFactory.getInstance(
    "PKIX", "BCJSSE");

keyMgrFact.init(serverStore, passwd);

sslContext.init(keyMgrFact.getKeyManagers(), null, null);

SSLServerSocketFactory fact = sslContext.getServerSocketFactory();

SSLServerSocket sSock =
    (SSLServerSocket)fact.createServerSocket(PORT_NO);

readyLatch.countDown();

SSLSocket sslSock = (SSLSocket)sSock.accept();

Protocol.doServerSide(sslSock);

}
catch (Exception e)
{
    LOG.log(Level.SEVERE, "server: " + e.getMessage(), e);
}

}
}
}

```

你会注意到服务端在它的 `start()` 方法中使用了一个 `CountDownLatch`。这样做的原因是服务器需要在准备好接受连接之前，向 `start()` 的调用者信号其启动过程已完成。值得记住这个技巧——否则，编写依赖多线程来模拟客户端和服务器的测试将变得非常困难。

### 基础 TLS 客户端

对于基础客户端，唯一的要求是它有某种识别服务器的方法。这是通过提供一个 `TrustManager` 来验证传入的凭据来实现。`TrustManager` 是使用 `TrustManagerFactory` 创建的，该工厂已使用包含证书的密钥库初始化，这些证书用于验证服务器将提供的证书路径。在我们的案例中，我们可以如下所示从服务器密钥库创建一个合适的密钥库：

```java
/**
 * 创建一个适用于信任存储的密钥库，仅包含与传入的
 * 据 store 中每个别名相关的证书。
 *
 * @param credentialStore 包含公钥/私钥凭据的密钥库。
 * @return 仅包含证书的密钥库。
 */
public static KeyStore createTrustStore(KeyStore credentialStore)
    throws Exception
{
    KeyStore store = KeyStore.getInstance("JKS");
    store.load(null, null);
    for (Enumeration<String> en = credentialStore.aliases(); en.hasMoreElements();)
    {
        String alias = en.nextElement();
        store.setCertificateEntry(alias, credentialStore.getCertificate(alias));
    }
    return store;
}
```

现在我们已经有了信任存储，需要创建一个客户端来配合使用。以下代码实现了一个 `Runnable`，它提供了一个 TLS 客户端，可以与服务端实现的 ‘!’ 协议工作。

```java
/**
 * 基础 TLS 客户端 - 使用 '!' 协议。
 */
public class BasicTLSClient
    implements Runnable
{
    private static Logger LOG = Logger.getLogger(BasicTLSClient.class.getName());
    private final KeyStore trustStore;

    /**
     * 基础客户端构造函数。
     *
     * @param trustStore 我们愿意从服务器信任的证书。
     */
    public BasicTLSClient(KeyStore trustStore)
    {
        this.trustStore = trustStore;
    }

    /**
     * 建立服务端 TLS 连接的任务。
     */
    public void run()
    {
        try
        {
            SSLContext sslContext = SSLContext.getInstance("TLS", "BCJSSE");
            TrustManagerFactory trustMgrFact = KeyManagerFactory.getInstance(
                "PKIX", "BCJSSE");
            trustMgrFact.init(trustStore);
            sslContext.init(null, trustMgrFact.getTrustManagers(), null);
            SSLSocketFactory fact = sslContext.getSocketFactory();
            SSLSocket cSock = (SSLSocket)fact.createSocket("localhost", PORT_NO);
            Protocol.doClientSide(cSock);
        }
        catch (Exception e)
        {
            LOG.log(Level.SEVERE, "client: " + e.getMessage(), e);
        }
    }
}
```

```java
/**
 * 带有客户端认证的 TLS 服务器 - 使用 '!' 协议。
 */
public class TLSServerWithClientAuth
{
    private static Logger LOG = Logger.getLogger(BasicTLSServer.class.getName());
    private final CountDownLatch readyLatch = new CountDownLatch(1);
    private final KeyStore serverStore;
    private final char[] passwd;
    private final KeyStore trustStore;

    /**
     * 基础服务器构造函数。
     *
     * @param serverStore 服务器的公钥/私钥。
     * @param passwd 解锁 serverStore 中私钥的密码。
     * @param trustStore 用于验证任何提交证书的信任库。
     */
    public TLSServerWithClientAuth(
        KeyStore serverStore, char[] passwd, KeyStore trustStore)
    {
        this.serverStore = serverStore;
        this.passwd = passwd;
        this.trustStore = trustStore;
    }

    /**
     * 启动服务器线程.
     */
    public void start()
        throws InterruptedException
    {
        new Thread(new ServerTask()).start();
        readyLatch.await();
    }

    /**
     * 建立 TLS 连接服务器端的任务。
     */
    private class ServerTask
        implements Runnable
    {
        public void run()
        {
            try
            {
                SSLContext sslContext = SSLContext.getInstance("TLS", "BCJSSE");
                KeyManagerFactory keyMgrFact =
                                KeyManagerFactory.getInstance("PKIX", "BCJSSE");
                keyMgrFact.init(serverStore, passwd);
                TrustManagerFactory trustMgrFact =
                                TrustManagerFactory.getInstance("PKIX", "BCJSSE");
                trustMgrFact.init(trustStore);
                sslContext.init(
                    keyMgrFact.getKeyManagers(),
                    trustMgrFact.getTrustManagers(), null);
                // 创建服务器套接并强制客户端认证。
                SSLServerSocketFactory fact = sslContext.getServerSocketFactory();
                SSLServerSocket sSock =
                    (SSLServerSocket)fact.createServerSocket(PORT_NO);
                sSock.setNeedClientAuth(true);
                readyLatch.countDown();
                SSLSocket sslSock = (SSLSocket)sSock.accept();
                Protocol.doServerSide(sslSock);
            }
            catch (Exception e)
            {
                LOG.log(Level.SEVERE, "server: " + e.getMessage(), e);
            }
        }
    }
}
```

请注意，在这种情况下，我们调用了带有参数 `true` 的 `SSLServerSocket.setNeedClientAuth()`，这意味着服务器只会接受能够自身认证的客户端连接。

### 带有客户端认证的 TLS 客户端

正如服务器需要引入 `TrustManager` 来允许其识别客户端一样，客户端也需要向其 `SSLContext` 中添加 `KeyManager` 以允许客户端向服务器标识自身。

接下来的代码示例展示了一个能够向服务器认证的简单客户端。请注意，标识客户端证书路径的信任锚点也必须提供给为服务器创建的 `TrustManager`。

```java
/**
 * 带有客户端认证的 TLS 客户端 - 使用 '!' 协议。
 */
public class TLSClientWithClientAuth
    implements Runnable
{
    private static Logger LOG = Logger.getLogger(BasicTLSClient.class.getName());
    private final KeyStore trustStore;
    private final KeyStore clientStore;
    private final char[] passwd;

    /**
     * 带有认证的基础基础客户端。
     *
     * @param trustStore 我们愿意从服务器信任的证书。
     * @param clientStore 客户端的公钥/私钥。
     * @param passwd 解锁 clientStore 中私钥的密码。
     */
    public TLSClientWithClientAuth(
        KeyStore trustStore, KeyStore clientStore, char[] passwd)
    {
        this.trustStore = trustStore;
        this.clientStore = clientStore;
        this.passwd = passwd;
    }

    /**
     * 建立带有认证的 TLS 客户端的任务。
     */
    public void run()
    {
        try
        {
            SSLContext sslContext = SSLContext.getInstance("TLS", "BCJSSE");
            KeyManagerFactory keyMgrFact =
                            KeyManagerFactory.getInstance("PKIX", "BCJSSE");
            keyMgrFact.init(clientStore, passwd);
            TrustManagerFactory trustMgrFact =
                            TrustManagerFactory.getInstance("PKIX", "BCJSSE");
            trustMgrFact.init(trustStore);
            sslContext.init(
                keyMgrFact.getKeyManagers(),
                trustMgrFact.getTrustManagers(), null);
            SSLSocketFactory fact = sslContext.getSocketFactory();
            SSLSocket cSock = (SSLSocket)fact.createSocket("localhost", PORT_NO);
            Protocol.doClientSide(cSock);
        }
        catch (Exception e)
        {
            LOG.log(Level.SEVERE, "client: " + e.getMessage(), e);
        }
    }
}
```

如示例所示，从客户端的角度来看，只需提供 `KeyManager` 就足够了。不需要为此进行额外的设置。

### 重新查看 TrustManagers

在许多情况下，示例中服务器处理客户端验证的方式是不够的。通常客户端证书会分配在 CA 下，并且 CA 可能需要定期撤销某些证书。

为了让开发者对客户端验证有更多控制权，`TrustManagerFactory.init()` 方法也可以接受 `ManagerFactoryParameters` 的实现。`ManagerFactoryParameters` 的实现实现之一是 `CertPathTrustParameters`，它允许提供一个 `PKIXParameters` 对象，该对象将用于对信任管理器检查的任何提交证书进行路径验证。对于我们之前看到的带有客户端认证的简单服务器示例，通过以下片段替换 `TrustManagerFactory` 的创建代码可以获得相同的结果：

```java
TrustManagerFactory trustMgrFact =
                              TrustManagerFactory.getInstance("PKIX", "BCJSSE");
```



```java
PKIXParameters pkixParameters = new PKIXParameters(trustStore);

trustMgrFact.init(new CertPathTrustManagerParameters(pkixParameters));
```

内部，`PKIXParameters` 对象会将 `trustStore` 转换为一组信任锚点。在简单的示例中，我们不需要做更多，因为场景是围绕自签名证书构建的。在更通用的情况下，你可能还需要用 CA 证书初始化 `PKIXParameters` 对象，并可选地使用 CRL 或 `PKIXCertPathChecker` 来管理撤销。

## 属性

配置 JSSE 配置不断进化，因此属性列表经常更新。在编写期间此处是当前的列表，但值得查看 bouncycastle.org 网站上最新版本的“Java (D)TLS API and JSSE Provider User Guide”中的附录 A 和附录 B。

### 安全属性

某些常规 JVM 安全属性也被 BCJSSE 提供使用。

以下是目前支持的：

*   `keystore.type`: 默认密钥库类型（通过 `java.security.KeyStore.getDefaultType()`）。
*   `keystore.type.compat`: 控制 JKS 和 PKCS12 密钥库类型的兼容模式。
*   `jdk.certpath.disabledAlgorithms`: 证书路径 (CertPath) 处理的算法限制。
*   `jdk.tls.disabledAlgorithms`: TLS 处理的算法限制。
*   `ssl.KeyManagerFactory.algorithm`: 默认的密钥管理器工厂算法（通过 `javax.net.ssl.KeyManagerFactory.getDefaultAlgorithm()` 获取）。
*   `ssl.TrustManagerFactory.algorithm`: 默认的信任管理器工厂算法（通过 `javax.net.ssl.TrustManagerFactory.getDefaultAlgorithm()` 获取）。

### 标准系统属性

BCJSSE 提供程序目前使用以下标准系统属性：

*   `com.sun.net.ssl.checkRevocation`: 用于 PKIX 信任管理器创建默认 PKIX 参数时启用吊销检查。
*   `com.sun.net.ssl.requireCloseNotify`: 是否要求在连接关闭之前发送 `close_notify` 警告告报，这在 TLS 中有所规定但并不总是被正确实现。BCJSSE 使用默认值“true”。
*   `java.home`: Java 安装目录。
*   `javax.net.ssl.keyStore`: 存储端点私钥的密钥库文件名称。用于在内部创建 `KeyManager`。
*   `javax.net.ssl.keyStorePassword`: 访问存储端点私钥的密钥库文件的密码。
*   `javax.net.ssl.keyStoreType`: 存储端点私钥的密钥库文件类型。
*   `javax.net.ssl.keyStoreProvider`: 为 `javax.net.ssl.keyStore` 属性指定的密钥库提供实现支持的程序名称。
*   `javax.net.ssl.sessionCacheSize`: 配置会话上下文“sessionCacheSize” 属性的默认值；参见 `SSLSessionContext.setSessionCachSize(int)`。
*   `javax.net.ssl.trustStore`: 存储验证通信端点信任锚点的密钥库文件名称。用于在内部创建 `TrustManager`。
*   `javax.net.ssl.trustStorePassword`: 访问存储信任锚点的密钥库文件的密码。
*   `javax.net.ssl.trustStoreType`: 存储信任锚点的密钥库文件类型。
*   `javax.net.ssl.trustStoreProvider`: 为 `javax.net.ssl.trustStore` 属性指定的密钥库提供实现支持的程序名称。
*   `jdk.tls.allowLegacyMasterSecret`: 是否允许未协商 `extended_master_secret` 扩展的连接。
*   `jdk.tls.allowLegacyResumption`: 是否允许原始连接未协商 `extended_master_secret` 扩展的会话恢复。
*   `jdk.tls.client.cipherSuites`: 以逗号分隔的列表形式指定 TLS 客户端默认启用的加密套件。
*   `jdk.tls.client.enableCAExtension`: 如果设置为“true”，则启用 `certificate_authorities` 扩展，这是 TLS 1.3 引入的可选的 `ClientHello` 扩展。
*   `jdk.tls.client.enableStatusRequestExtension`: 根据 RFC 6066 的 `status_request` 扩展启用“OCSP 封装”。
*   `jdk.tls.client.protocols`: 欲要启用特定的 TLS 协议，请在引号内以逗号分隔的列表形式指定它们，并将禁用所有其他支持的协议。例如，如果此属性值为“TLSv1,TLSv1.1”，则默认协议设置仅适用于 TLSv1 和 TLSv1.1，没有其他可用协议。
*   `jdk.tls.client.SignatureSchemes`: 包含逗号分隔的支持签名方案名称列表，指定了客户端侧可能用于 TLS 连接的签名方案。
*   `jdk.tls.ephemeralDHKeySize`: 设置此值以自定义临时 DH 密钥的大小（位为单位）。该值默认为 2048，最小为 1024。
*   `jdk.tls.maxCertificateChainLength`: 指定 TLS 握手中允许证书链的最大长度。
*   `jdk.tls.maxHandshakeMessageSize`: 指定 TLS 握手中握手消息的最大大小（字节为单位）。
*   `jdk.tls.namedGroups`: 定义已启用曲线和/或有限域组集合，按偏好顺序排序。格式为逗号分隔的组名列表，例如“secp256r1, secp384r1, secp521r1”。完整的组名列表请参阅 RFC 4492、RFC 7919 和/或 IANA 的 TLS 支持组注册表。
*   `jdk.tls.server.cipherSuites`: 以逗号分隔的列表形式指定 TLS 服务器默认启用的加密套件。
*   `jdk.tls.server.enableCAExtension`: 如果设置为“true”，则启用 `certificate_authorities` 扩展，这是 TLS 1.3 引入的可选 `CertificateRequest` 扩展。
*   `jdk.tls.server.protocols`: 欲要启用特定的 TLS 服务器协议，请在引号内以逗号分隔的列表形式指定它们，并将禁用所有其他支持的协议。例如，如果此属性值为“TLSv1,TLSv1.1”，则默认协议设置仅适用于 TLSv1 和 TLSv1.1，没有其他可用协议。
*   `jdk.tls.server.SignatureSchemes`: 包含逗号分隔的支持签名方案名称列表，指定了客户端可能用于 TLS 连接的签名方案。
*   `jdk.tls.trustName`: 可用于在需要时开启查找。注意：启用查找可能会受到 MITM 攻击。
*   `jdk.tls.useExtendedMasterSecret`: 如果设置为“false”，则禁用扩展主密钥的协商。
*   `jsse.enableFFDHE`: 如果设置为“false”，则禁用 RFC 7919 中定义的 FFDHE 机制。
*   `jsse.enableSNIExtension`: 如果设置为“true”，启用服务器名称指示 (SNI) 扩展。
*   `sun.security.ssl.allowLegacyHelloMessages`: 如果设置为“true”，允许未实现 RFC 5746 安全重新协商的连接。

### BCJSSE 特定属性

以下属性是 BCJSSE 特有的：

*   `org.bouncycastle.jsse.client.dh.minimumPrimeBits`: 整数属性，默认 2048，可以在 1024 到 16384 之间配置。
*   `org.bouncycastle.jsse.client.dh.unrestrictedGroups`: 布尔属性，默认 false，如果被设置为“true”，则将接受任何符合大小要求（即 `minimumPrimeBits`）的 DH 组。
*   `org.bouncycastle.jsse.client.enableSessionResumption`: 控制 TLS 客户端是否启用自动会话恢复（如果支持）。
*   `org.bouncycastle.jsse.client.enableTrustedKeysExtension`: 控制 TLS 客户端是否启用 RFC 6066 中的 `trusted_ca_keys` 扩展。
*   `org.bouncycastle.jsse.config`: 向 JSSE 提供程序传递配置字符串的另一种方法。设置为“default”以正常方式运行，否则可以使用其他配置，例如“fips:BCFIPS”。
*   `org.bouncycastle.jsse.fips.allowRSAKeyExchange`: 布尔属性，默认 true，如果设置为“true”，则允许在 IPS 模式下使用基于 RSA 密钥交换的加密套件。注意：当 SP 800-131A 弃 TLS 中的 RSA 密钥交换生效时，此属性的默认值将变为“false”。
*   `org.bouncycastle.jsse.ec.disableChar2`: 布尔属性，默认 false，如果被设置为“true”，将禁用 TLS 握手和密钥交换中使用任何特征 2（或 F2m）曲线。
*   `org.bouncycastle.jsse.keyManager.checkEKU`: 控制 BCJSSE 密钥管理器在向 TLS 对端提交凭据集时是否检查适当的扩展密钥用途 (EKU)。注意，无效 EKU 的证书可能会被对方拒绝。
*   `org.bouncycastle.jsse.server.enableSessionResumption`: 控制 TLS 服务器是否启用自动会话恢复（如果支持）。
*   `org.bouncycastle.jsse.server.enableTrustedCAKeysExtension`: 控制 TLS 服务器是否启用来自 RFC 6066 的 `trusted_ca_keys` 扩展。
*   `org.bouncycastle.jsse.trustManager.checkEKU`: 控制 BCJSSE 信任管理器检查给定证书链是否受信任时，是否检查适当的扩展密钥用法（Extended Key Usage）扩展。

## BC JSSE 扩展

遵循 TLS 协议对任何人来说都是一项巨大的挑战，因此 Bouncy Castle JSSE 提供程序提供了若干扩展，以填补旧版本 JSSE 的空白，并提供了当前版本中一些尚未完全进入公共 API 的功能。

### 恢复 TLS 唯一 ID

BC JSSE 返回的 `SSLSocket` 对象，这些对象实现了 `org.bouncycastle.jsse.BCSSLSocket` 接口。`BCSSLSocket` 定义如下：

```java
 1 /**
 2  * 一个 BCJSSE 特有的接口，用于在
 3  * javax.net.ssl.SSLSocket 实现上暴露扩展功能。
 4  */
 5 public interface BCSSLSocket
 6 {
 7     BCExtendedSSLSession getBCHandshakeSession();
 8 
 9     /**
10      * 返回扩展 SSL 连接数据的访问器。此方法将在 
11      * 有需要时启动初始握手，然后阻塞直到
12      * 握手建立。如果在初始握手期间发生错误，
13      * 此方法将返回 null。
14      *
15      * @return 一个 BCSSLConnection 实例。
16      */
 17     BCSSLConnection getConnection();
 18 
 19     /**
20      * 返回一个带有反映当前配置的 
21      * 属性的 BCSSLParameters。
22      * @return 当前的 BCSSLParameters 参数
23      */
 24     BCSSLParameters getParameters();
 25 
 26     /**
27      * 当未使用包含其作为参数的 SocketFactory 
28      * 方法时，允许显式设置 'host' 字符串。
29      *
30      * 必须在尝试连接套接字之前调用此方法
31      * 才能生效。
32      *
33      *
34      * @param host 要连接的服务器主机名，或
35      *             null 表示回环地址。
36      */
 37     void setHost(String host);
 38 
 39     /**
40      * 根据 {@link BCSSLParameters} 中的属性设置参数。
41      *
42      * 注意，任何设置为 null 的属性都将被忽略，这 
43      * 将保持相应的设置不变。
44      *
45      *
46      * @param parameters 要设置的 {@link BCSSLParameters 参数}
47      */
 48     void setParameters(BCSSLParameters parameters);
 49 }
```

其中 `org.bouncycastle.jsse.BCSSLConnection` 定义为：

```java
 1 /**
 2  * 一个 BCJSSE 特有的接口，用于访问扩展的连接特定
 3  * 功能。
 4  */
 5 public interface BCSSLConnection
 6 {
 7     /**
 8      * 返回为此连接协商的应用协议，如果没有协商
 9      * 则返回空字符串。详情请参见 https://tools.ietf.org/html/rfc7301
10      *
11      *
12      * @return 协商的应用协议，或一个空 {@code String}。
13      */
 14     String getApplicationProtocol();
 15 
 16     /**
17      * 
18      * 为此连接请求 TLS 通道绑定（Channel Bindings）。详情
19      * 请参见 https://tools.ietf.org/html/rfc5929。
20      *
21      *
22      * @param channelBinding 一个 IANA 注册的“通道绑定唯一前缀”，
23      *                  TLS 有效，例如 "tls-unique" 或 "tls-server-end-point"。
24      * @return 通道绑定数据的 byte[] 拷贝，如果该
25      *     绑定对此连接不可用则返回 null。
26      */
 27     byte[] getChannelBinding(String channelBinding);
 28 
 29     /**
30      * 返回此连接使用的 SSL 会话
31      * @return BCExtendedSSLSession。
32      */
 33     BCExtendedSSLSession getSession();
 34 }
```

`channelBinding` 字符串代表一个在 IANAs（IANA）注册的“通道绑定唯一前缀”，该前缀被列为 TLS 有效，例如：“tls-unique”。你可以按照下例示例，利用这些 BC JSSE 特有的接口创建一个函数，以获取诸如“tls-unique”之类的通道绑定。

```java
public byte[] getTlsUnique(Socket sock)
{
    BCSSLConnection bcon = ((BCSSLSocket)sock).getConnection();
    if (bcon != null)
    {
        return bcon.getChannelBinding("tls-unique");
    }
    return null;
}
```



### 端点识别

端点识别在 bctls 1.0.7 中引入，其方式尽可能地与 SunJSSE 保持兼容。遗憾的是，当使用 `HttpsURLConnection` 时，SunJSSE 使用了一些“魔法手段”（反射和/或内部 API）来告诉套接字用于连接的“主机名”，我们无法使用这种方法，因为它是内部的。为了让端点识别正常工作，需要使用两种变通方法：

1. 将系统属性 `jdk.tls.trustNameService` 设置为“true”。但是，请注意此说明：“如果应用程序对 SSL/TLS 连接中的原始 IP 地址进行反向解析并遇到端点识别问题，可以使用 `jdk.tls.trustNameService`。注意，如果域名服务不可信，启用反向解析可能会受到攻击。”

2. 第二种（推荐的）替代方案是在 `HttpsURLConnection` 上设置自定义的 `SSLSocketFactory`，然后拦截套接字创建并在套接字上手动设置 SNI `host_name`。请参见下例代码。这是人们在想要调整加密套件时使用的通用模式。

```
1 // 代码块
2 {
3     SSLContext sslContext = ...;
4     final URL serverURL = ...;
5     HttpsURLConnection conn = (HttpsURLConnection)serverURL.openConnection();
6 
7     conn.setSSLSocketFactory(new CustomSSocketFactory(
8                     sslContext.getSocketFactory())
9     {
10         @Override
11         protected Socket configureSocket(Socket s)
12         {
13             if (s instanceof SSLSocket)
14                 {
15                     SSLSocket ssl = (SSLSocket)s;
16 
17                 SNIHostName sniHostName = getSNIHostName(serverURL);
18                 if (null != sniHostName)
19                     {
20                         SSLParameters sslParameters = new SSLParameters();
21 
22                         sslParameters.setServerNames(
23                                 Collections.<SNIServerName>singletonList(sniHostName));
24                         ssl.setSSLParameters(sslParameters);
25                     }
26             }
27             return s;
28         }
29     });30 }
31 
32 private SNIHostName getSNIHostName(URL url)
33 {
34     String host = url.getHost();
35     if (null != host && host.indexOf('.') > 0
36             && !org.bouncycastle.util.IPAddress.isValid(host))
37     {
38         try
39         {
40             return new SNIHostName(host);
41         }
42         catch (RuntimeException e)
43         {
44 		// ignore – return null
45         }
46     }
47     return null;
48 }
```

## 使用低级 (D)TLS API

BCJSSE 提供者通过位于 `org.bouncycastle.tls` 包中的低级 (D)TLS API 来实现 TLS。可以直接使用此 API 而无需通过 JSSE 标准 API。它的设计初衷是让程序员具有极大的灵活性，可以修改或扩展实现的各个方面。这可能意味着简单的配置选项，如密码套件、版本、椭圆曲线，或者更复杂的更改，如添加对新 TLS 扩展的支持。对于大多数用户来说，通过 BCJSSE 提供者使用 Bouncy Castle 的 TLS 功能是最佳选择，特别是在与第三方应用程序协作时，这些应用程序通常是基于 JSSE 标准 API 开发的。然而，可能存在某些 JSSE 未暴露必要功能的用例，例如你需要使用 DTLS，或者由于其他原因 JSSE 不适用。在某些情况下，可以使用 BC 特有的扩展来涵盖该用例，但也有可能完全弃用 JSSE。建议对 TLS 规范（如 `RFC 5246` 及其他相关的 `RFCs` 中描述）有一定了解。如果你计划走这条路，参考 TLS 测试套件的源代码作为示例用法，并研究 BCJSSE 提供者本身如何使用该 API 可能会很有帮助。

## TlsCrypto

低级 (D)TLS API 将所有加密操作委托给 `TlsCrypto` API，该 API 位于 `org.bouncycastle.tls.crypto` 包。该 API 的使用是通过 `TlsCrypto` 接口的实例；单个实例可以在多个连接之间共享。例如，BCJSSE 提供者为每个 `SSLContext` 使用单个实例。在标准的 TLS 分发版中提供了 2 个现有的 `TlsCrypto` 实现：

- `org.bouncycastle.tls.crypto.impl.bc.BcTlsCrypto`
- `org.bouncycastle.tls.crypto.impl.jcajce.JcaTlsCrypto`

其他选项是编写完全全新的实现，或者更现实是对这些实现之一进行子类以微调其行为。只需记住 `TlsCrypto` 对象应该是可共享的。

### BcTlsCrypto

`BcTlsCrypto` 依赖轻量级 BC 加密 API 实现加密原语。`BcTlsCrypto` 不在 BCFIPS TLS jar 中。

### JcaTlsCrypto

`JcaTlsCrypto` 通过 Java 加密体系 (JCA) 将操作委托给任何安装的加密提供者。虽然我们预计这通常会与“BC”或“BCFIPS”提供者一起使用，但并非强制。然而，请注意，TLS API 可用的密码套件集受可用提供者的能力。

## 低级 TLS API

低级 TLS API 是 BCJSSE 提供者构建的基础，因此使用 BCJSSE 提供者可以完成的任何操作在低级 TLS API 中也可以完成。

### 简单 TLS 客户端大纲

简单 TLS 客户端的示例代码：

```
// 用于支持客户端功能的 TlsCrypto
TlsCrypto crypto = new BcTlsCrypto(new SecureRandom());
…
InetAddress address = InetAddress.getByName("www.example.com");
int port = 443;
Socket s = new Socket(address, port);
TlsClient client = new DefaultTlsClient(crypto) {
 // 在此处 必须实现 TlsClient.getAuthentication()
};
TlsClientProtocol protocol = new TlsClientProtocol(
 s.getInputStream(), s.getOutputStream());
// 执行 TLS 握手
protocol.connect(client);
// 读写 protocol.getInputStream(), protocol.getOutputStream()
…
protocol.close();
```

`DefaultTlsClient` 提供了一组合理的默认密码套件，类似于典型的 Web 浏览器支持的内容。其他选项包括在使用预共享密钥时使用 `PSKTlsClient`，或者在使用安全远程密码协议 (SRP) 进行身份验证时使用 `SRPTlsClient`。请注意，在使用此代码之前，必须提供 `TlsClient.getAuthentication()` 的实现（见上方的代码注释）。该实现应返回 `TlsAuthentication` 接口的实例，并且该实例 必须在 `TlsAuthentication.notifyServerCertificate` 中执行证书验证。这可以是简单的检查服务器证书是否与预期的完全一致，也可以按照 `RFC 5280` 指定进行全路径验证，或者是两者之间的某种，但至关重要的是，生成的 TLS 连接的安全性取决于这一步。如果你希望客户端向服务器进行身份验证，还需要实现 `TlsAuthentication.getClientCredentials`。

### 简单 TLS 服务器大纲

根据所需的功能范围，编写 TLS 服务器可能比编写 TLS 客户端复杂得多。尽管顶层代码应该非常相似：

```
// 用于支持服务器功能的 TlsCrypto
TlsCrypto crypto = new BcTlsCrypto(new SecureRandom());
…
int port = 443;
ServerSocket ss = new ServerSocket(port);
Socket s = ss.accept();
…
TlsServer server = new DefaultTlsServer(crypto) {
 // 在此处重写例如 TlsServer.getRSASignerCredentials() 或
 // 类似的方法，取决于你想使用的凭据。
};
TlsServerProtocol protocol = new TlsServerProtocol(
 s.getInputStream(), s.getOutputStream());
// 执行 TLS 握手
protocol.accept(server);
// 读写 protocol.getInputStream(), protocol.getOutputStream()
…
protocol.close();
```

`PKSTlsServer` 或 `SRPTlsServer` 是此处的其他选项，与客户端类似。在这里，在进行任何操作之前，必须解决服务器将使用的凭据问题（见代码注释）。支持客户端认证需要重写 `TlsServer.getCertificateRequest()` 和 `TlsServer.notifyClientCertificate`，后者在考虑客户端之前必须执行证书验证。如果需要，也可以对 `TlsClientProtocol` 或 `TlsServerProtocol` 进行子类化。

## DTLS

DTLS 客户端和服务器使用与 TLS 不同的协议类和传输层，但 `TlsClient` 和 `TlsServer` 实现通常可以正常工作。存在某些异常，例如 DTLS 不支持基于流的密码套件如 RC4。客户端代码差异示例：

```
DatagramSocket socket = new DatagramSocket();
socket.connect(InetAddress.getByName("www.example.com"), 5556);
int mtu = 1500;
DatagramTransport transport = new UDPTransport(socket, mtu);
TlsClient client = ...;
DTLSClientProtocol protocol = new DTLSClientProtocol();
DTLSTransport dtls = protocol.connect(client, transport);
// 读写 dtls 方法
dtls.close();
```

服务器再次非常：

```
DatagramTransport transport = ...;
TlsServer server = ...;
DTLSServerProtocol protocol = new DTLSServerProtocol();
DTLSTransport dtls = protocol.accept(server, transport);
dtls.close();
```



### 低级 TLS API 重写

使用低级 TLS 类通常需要扩展基类，然后重写父类的方法以提供所需的功能。以下是一些更有实用的重写。

注意：在许多你需要通过重写基类之一的方法来向操作添加某些内容的情况下，通常最好确保通过 `super` 调用基类中的方法。

#### 基于 TLSPeer 的有用重写

`TLSPeer` 类是低级 API 中 TLS 客户端和服务器的基础。

##### 握手 - notifyHandshakeBeginning(), notifyHandshakeComplete()

`notifyHandshakeBeginning()` 和 `notifyHandshakeComplete()` 提供捕捉握手开始和完成的能力。`notifyHandshakeComplete()` 方法只有在握手成功完成后才会被调用。在出现警告（alert）的情况下，你需要重写 `notifyAlertRaised()` 和 `notifyAlertReceived()` 方法。

##### Alerts - notifyAlertRaised(), notifyAlertReceived()

`notifyAlertRaised()` 和 `notifyAlertReceived()` 方法提供了监听在 TLS 协议执行过程中本地或远程产生的告报（alerts）的能力。当本地产生告报时，将调用 `notifyAlertRaised()`。当从远程节点接收告报时，将调用 `notifyAlertReceived()`。

#### 基于 TLSClient 的实用重写

`TLSClient` 是 `TLSPeer` 的客户端扩展。通常的基础实现类是 `DefaultTLSClient`，但也有一些额外的可用重写方法。

##### 会话信息 - notifySessionID()

`notifySessionID()` 方法被调用用于通知客户端 `ServerHello` 中发送的会话 ID。会话 ID 以 `byte[]` 形式传入。

##### 会话恢复 - getSessionToResume(), notifySessionToResume()

通常，此方法将返回 `null`，表示应该使用新会话。非空返回值可表示客户端想要恢复的会话。假设一切工作已就绪可以实现恢复，该会话将传递给 `notifySessionToResume()` 方法并表示成功。如果无法恢复会话，则将带有 `null` 调用 `notifySessionToResume()`，并将新的会话 ID 传递给 `notifySessionID()` 方法。

#### 基于 TLSServer 的实用重写

`TLSServer` 是 `TLSPeer` 的服务器扩展。通常的基础实现类是 `DefaultTLSServer`，但也一些额外的可用的重写方法。

##### 会话信息 - notifySession()

在服务器对象上调用 `notifySession()` 方法，用于传入所有会话信息以及防止会话被恢复的能力。所需的数据通过一个实现 `TlsSession` 接口的对象传入。`TlsSession` 接口包含返回会话参数、会话 ID 以及会话是否可恢复的方法。该接口还提供了一个 `invalidate()` 方法，可用于防止会话被恢复。

### 专家协议：PSK 和 SRP

低级 API 对 PSK 和 SRP 均有某些支持。目前在 JSSE 级别还没有支持——这在未来可能会发生变化，但目前看来，所需的工作量似乎超过了人们直接使用低级 API 所面临的工作量。

#### TLS-PSK - 传输层安全预共享密钥

在 TLS 中使用预共享密钥由 RFC 4279 涵盖 [89]。低级 TLS API 支持通过 `PSKTlsClient` 类实现 TLS-PSK。你可以通过扩展 `PSKTlsClient` 类并至少重写 `getAuthentication()` 方法来实现 TLS-PSK 客户端。`PSKTlsClient` 类在其构造函数中获取 TLS-PSK 身份信息，实现 `TlsPSKIdentity` 的对象也可用于传入 TLS-PSK 身份信息。

TLS-PSK 服务器支持由 `PSKTlsServer` 类提供，实现者需要重写 `getRSASignerCredentials()`并在构造服务器对象时提供 `TlsPSKIdentityManager` 的实现。

#### TLS-SRP - 传输层安全安全远程密码

使用安全远程密码（SRP）协议进行 TLS 认证（即 TLS-SRP）记录在 RFC 5054 中 [94]。Bouncy Castle 通过 `SRPTlsClient` 类提供 TLS-SRP 支持。要实现 SRP-TLS 客户端，你需要扩展 `SRPTlsClient` 类并至少重写 `getAuthentication()` 方法以提供对协议的支持。与 TLS-PSK 类似，`SRPTlsClient` 在构造函数中获取身份信息，`TlsSRPIdentity` 提供了任何携带身份的对象都需要遵循的基础接口。

TLS-SRP 服务器支持由 `SRPTlsServer` 类提供。在这种情况下，重要的方法是 `getDSASignerCredentials()` 和 `getRSASignerCredentials()`——其中一个需要被重写，以便服务器提供凭据。服务器类在构造服务器对象时还需要 `TlsSRPIdentityManager` 的实现。低级 API 还提供了 `SimulatedTlsSRPIdentityManager`，允许服务器通过提供 RFC 5054 第 2.5.1.3 节算法的实现来模拟“未知”身份的存在。使用此类类将允许服务器隐藏用户名没有验证器的事实。

### 总结

Bouncy Castle API 提供了 JSSE 提供程序和低级 API，以支持 TLS、DTLS 以及某些协议的变体（如 PSK 和 SRP）。对于 PSK 和 SRP 等专家级变体，你需要使用低级 API。

出于调试目的，TLS API 提供了对 Java 日志（Java Logging）的支持。BCJSSE 提供程序也可以使用许多与 JSSE 提供程序相同的系统属性，但请注意，BCJSSE 提供程序针对最新的 JVM 有许多属性的默认值，而普通的 JSSE 提供程序会将未定义的属性简单视为未设置且没有默认值。

## 第 15 章：未来

本章尝试提供密码学当前发展的窗口，以及它们如何开始影响 Bouncy Castle API 的方向。该领域最大的活动是围绕后量子算法——这些算法涵盖了密钥交换、签名和密钥传输等广泛的应用领域。这一发展之所以引起关注的原因之一是，许多此类算法并非“常态”——我们看到了只有一方拥有私钥的状态算法和密钥交换机制。这些差异可能会导致新协议的引入，并改变我们解决问题的方法。

## 安装 Bouncy Castle 量子提供程序

Bouncy Castle 量子提供程序（BCPQC）从 Java 1.5 开始包含在 BC 包（以 `bcprov` 开头）中。即使 BC 在类路径中，它不会自动安装，因此需要静态或在运行时安装。

目前还没有与 BCFIPS 提供程序等效的选择，尽管某些 BCFIPS 工具使用了量子算法。

### 静态安装

静态安装提供程序取决于你处理的是否为 Java 1.9 之前的 JVM。

对于 Java 1.5 到 1.8，你可以通过向 `$JAVA_HOME/jre/lib/security/java.security` 文件中的列表插入类名来添加提供程序。提供程序列表格式为 `security.provider.n` 的项，其中 n 是提供程序的优先级，1 表示最高优先级。在这种情况下添加 Bouncy Castle 量子提供程序需要添加如下行：

```
security.provider.N=org.bouncycastle.pqc.jcajce.provider.BouncyCastlePQCProvider
```

其中 N 代表你希望 BCPQC 提供程序具有的优先级。如果没有将 BCPQC 提供程序添加到列表末尾，确保调整其他提供程序的值。添加该项后，确保提供程序位于类路径上，最好放在 `$JAVA_HOME/jre/lib/ext` 目录，以便它始终能由 JCA 信任的类加载器加载。

对于 Java 1.9 及更高版本，列表位于 `$JAVA_HOME/conf/security`。目前 BC 提供程序不支持 jar 包的 `META-INF/service` 功能，因此需要像以前一样通过使用完整类名添加到提供程序列表中。

Java 1.9 不再支持 `$JAVA_HOME/jre/lib/ext`。在 Java 1.9 的情况下，你只需要确保 BCPQC 包含在类路径中。

### 运行时安装

在运行时使用提供者（provider）有两种方法。

第一方法是使用 `java.security.Security` - 对于 BCPQC 提供者，其写法如下：

```java
java.security.Security.addProvider(
             new org.bouncycastle.pqc.jcajce.provider.BouncyCastlePQCProvider());
```

执行完上述语句后，`JVM` 中的状态几乎等同于静态安装提供者的情况。可以使用提供者的名称通过 `getInstance()` 方法访问签名等服务。

使用第二种方法，则是将提供者对象传递到所请求的服务中，例如，为了使用 `BCPQC` 提供者创建一个 `XMSS` 签名，你可以写：

```java
Signature sig = Signature.getInstance("XMSS", new BouncyCastlePQCProvider());
```

## 有状态签名算法

我们处理的大多数签名算法都是无状态的。也就是说，一旦执行了签名操作，一切都与签名操作之前一样，可以再次使用相同的私钥得到相同的结果。

有状态签名算法在这方面有所不同 - 每生成一个签名，私钥都会被修改。这是因为有状态的方案是基于一次签名方案（one-time signature schemes），而有状态签名方案提供的多次签名方案实际上是通过一组一次性私钥创建签名来工作的，所有这些签名都可以通过同一个公钥进行验证。

在某些方面，有状态签名方案实际上是一种优势，因为私钥的寿命是有限的。使用有状态方案迫使人们更换密钥，并在开发初期妥善处理与加密和安全相关的“硬性”问题，而不是通常的“先部署，后恐慌”的过程。我们在这里查看的算法还包括签名中的签名索引。这使得很容易判断你已经发出了多少个签名，即使你无法直接访问私钥。

尽管如此，有状态签名方案带来了一些我们以前没有遇到过的新问题。考虑到这些新问题很重要，特别是当你需要持久化私钥时。

### 起源

有状态签名算法的起源可以追溯到基于哈希的签名算法早期工作，这些工作源于 1979 年 Leslie Lamport [12] 和 Robert Winternitz [13] 的工作。详细查看这些方案中的一种是值得的，因为它有助于解释这些方案实际上是如何工作的，以及为什么有必要确保密钥中的状态不被重用。

### 基础 Winternitz 一次签名

Winternitz 方案很有意义，因为它既代表了基于哈希的签名生成器，其变体（W-OTS+）也被用于 `XMSS` 以及 `SPHINCS+`（NIST 后量子加密决赛者之一）等算法中。该方案的描述和实现也相对简单。查看下面的图，你将看到它是如何使用 `SHA-256` 作为消息摘要对单个字节进行签名的。

![使用 W-OTS 对单个字节签名的过程](img/chapter15----W-OTS.png)

使用 W-OTS 对单个字节签名的过程

从图中可以看到，我们得到了 64 字节的签名，因为我们还基于被签名字节的补码计算了校验和。虽然前 32 字节的值为我们提供了一个可以验证的数值签名，但再次对该值进行哈希也是轻而易举的，在没有额外信息的情况下，我们会接受前 32 字节作为 `M + 1` 的签名。为了避免这种情况，我们依赖 `M` 的补码，如在 `w - 1 - M` 中用于校验和。这意味着任何试图将 `M + 1` 呈现为有效的伪造者将面临计算 `SHA-256(w - 1 - (M + 1))` 的问题，而这是 `SHA-256(w - 1 - M)` 的原像 - 如果所使用的摘要函数足够好，这是极其困难的，甚至是不可能的。

遗憾的是，保护原像（pre-images）的需求意味着我们只能使用一次 W-OTS 私钥 - 如果不遵循这条规则，并且有人欺骗我们签名字节‘0x00’和字节‘0xFF’，他们就能伪造任何值的签名。

在更通用的意义上实现该方案是相当直接的。Winternitz 方案依赖于参数 `w` 来决定私钥的每个部分可以处理多少位 - `w` 代表 2^bits。为了简单起见，我们仅使用以下设置参数：

```java
private static final String DIGEST = "SHA-256";
private static final int DIGEST_SIZE = 32;
private static final int W = 256;
// CHK_SIZE = floor(log2(DIGEST_SIZE * (W - 1))/log2(W)) + 1
private static final int CHK_SIZE = 2;
private static final int KEY_ELEMENTS = W / 8;
```

我说简单是因为 `w` 为 256 意味着我们可以基于字节进行所有操作。不过你可以将 `w` 增加到更高的 2 的幂，例如 65536 将允许按 2 字节处理消息，并减半签名大小以及公钥和私钥的大小。

校验和大小被设置为 2 字节，因为我们可以如下描述我们想要的计算：

```java
/**
 * 计算补码校验和，以防止基于增加 msg 值的伪造行为。
 *
 * @param msg 要计算校验和的消息。
 * @return 字节数组形式的校验和。
 */
private static byte[] calcCheckSum(byte[] msg)
{
    // 计算 msg 校验和
    int checkSum = 0;
    for (int i = 0; i < msg.length; i++ )
    {
        checkSum += W - 1 - (msg[i] & 0xff);
    }

    // 注意：这取决于 CHK_SIZE
    return Pack.shortToBigEndian((short)checkSum);
}
```

我们可以将其作为 2 字节校验和返回，因为 `32*(w-1)` 是校验和可能的最大值。使用消息的完整补码也可以，但它会使签名大小翻倍 - 较小的计算同样有效，因为它为伪造者制造了相同的问题。任何伪造签名只能通过增加我们正在签名的消息哈希中的某个字节来计算，伪造者无法在特定索引处使用较小的字节值，因为他们无法恢复哈希的原像。增加字节值将导致校验和中至少一个字节的减少，因此潜在的伪造者再次陷入了麻烦。

此时，计算一次性密钥对只需创建一个代表私钥的秘密数组，然后执行所需次数的哈希操作来创建公钥。

```java
/**
 * Generate a W-OTS key pair.
 *
 * @param random 用于密钥生成的随机性数源。
 * @return 一个形式为 {publicKey, privateKey} 的数组。
 */
private static byte[][] computeWotsKeyPair(SecureRandom random)
    throws GeneralSecurityException
{
    MessageDigest digest = MessageDigest.getInstance(DIGEST);
    // create a 32 * 256 bit private key
    byte[] privateKey = new byte[KEY_ELEMENTS * DIGEST_SIZE];
    random.nextBytes(privateKey);
    byte[] publicKey = new byte[privateKey.length];
    System.arraycopy(privateKey, 0, publicKey, 0, publicKey.length);
    for (int i = 0; i != KEY_ELEMENTS; i++)
    {
        for (int j = 0; j != W; j++)
        {
            digest.update(publicKey, i * DIGEST_SIZE, DIGEST_SIZE);
            digest.digest(publicKey, i * DIGEST_SIZE, DIGEST_SIZE);
        }
    }
```



```java
return new byte[][]{publicKey, privateKey};
```

从这里你可以看到，将 `![w](img/leanpub_equation_671.png)` 增加到 65536 意味着虽然公钥计算次数会减少，但剩余的计算创建公钥时将花费 256 倍的时间。这是一个巨大的跃！

计算签名：我们首先对消息进行哈希，将校验和附加到结果中，然后对每个字节执行哈希计算。下面的方法展示了如何实现这一点。

```java
/**
 * 根据消息摘要和私钥计算签名。
 *
 * @param privateKey 要使用的 W-OTS 私钥。
 * @param message 要签名的消息。
 * @return 计算出的签名。
 */
private static byte[] computeWotsSignature(byte[] privateKey, byte[] message)
    throws GeneralSecurityException
{
    MessageDigest digest = MessageDigest.getInstance(DIGEST);
    byte[] msgDigest = digest.digest(message);
    byte[] checkMsg = Arrays.concatenate(msgDigest, calcCheckSum(msgDigest));
    byte[] signature = new byte[privateKey.length];
    System.arraycopy(privateKey, 0, signature, 0, signature.length);
    for (int i = 0; i != KEY_ELEMENTS; i++)
    {
        for (int j = 0; j <= (checkMsg[i] & 0xff); j++)
        {
            digest.update(signature, i * DIGEST_SIZE, DIGEST_SIZE);
            digest.digest(signature, i * DIGEST_SIZE, DIGEST_SIZE);
        }
    }
    return signature;
}
```

从代码中可以看出，如果 `![w](img/leanpub_equation_672.png)` 同样增加，那么适用于密钥生成的问题也会适用于签名生成。

验证签名还需要对消息进行哈希，然后根据消息哈希值正向迭代签名中的哈希值。假设一切正确，这样做应该会产生与公钥相同的值。

```java
/**
 * 验证传入的 W-OTS 签名。
 *
 * @param publicKey 用于验证签名的 W-OTS 公钥。
 * @param signature 要验证的签名。
 * @param message 签名应该验证的消息。
 * @return 如果消息通过则返回 true，否则返回 false。
 */
private static boolean isVerifiedWotsSignature(
    byte[] publicKey, byte[] signature, byte[] message)
    throws GeneralSecurityException
{
    MessageDigest digest = MessageDigest.getInstance(DIGEST);
    byte[] msgDigest = digest.digest(message);
    byte[] calcPubKey = new byte[publicKey.length];
    byte[] checkMsg = Arrays.concatenate(msgDigest, calcCheckSum(msgDigest));
    System.arraycopy(signature, 0, calcPubKey, 0, calcPubKey.length);
    for (int i = 0; i != KEY_ELEMENTS; i++)
    {
        for (int j = (checkMsg[i] & 0xff); j != W - 1; j++)
        {
            digest.update(calcPubKey, i * DIGEST_SIZE, DIGEST_SIZE);
            digest.digest(calcPubKey, i * DIGEST_SIZE, DIGEST_SIZE);
        }
    }
    // calcPubKey 现在应该等于 publicKey
    return Arrays.equals(calcPubKey, publicKey);
}
```

再次你可以注意到增加 `![w](img/leanpub_equation_673.png)` 也会导致尺寸的变化。你可以使用以下代码将这些方法整合在一起：

```java
byte[] msg = Strings.toByteArray("Hello, world!");
byte[][] wotsKp = computeWotsKeyPair(newRandom());
byte[] signature = computeWotsSignature(wotsKp[1], msg);
System.out.println("verifies: "
    + isVerifiedWotsSignature(wotsKp[0], signature, msg));
```

运行该示例应该产生如下：

```
verifies: true
```

你会发现增加 `![w](img/leanpub_equation_674.png)` 也会增加时间。

#### 进阶多签名 - XMSS 和 LMS

我们可以通过在组合中引入索引（或计数器），并在 HMAC 或其他伪随机函数中使用该索引，利用像 W-OTS 算法作为生成多个签名的基础。这仍然允许我们利用恢复原像的困难来保持算法的“抗量子性”，但你也可以看到，虽然索引的引入允许我们重用秘密值，但重用状态将导致能够恢复可能用于伪造的原像。

Leighton-Micali 签名 (LMS) 以及基于 LMS 的分层签名系统 (HSS) 已在 `RFC 8554` [132] 中定义。关于这些签名的额外标准工作也已通过。`RFC 8708` [133] 现在为 CMS 和 X.509 公钥编码提供指导，而 `RFC 8778` [134] 则用于构建基于紧凑二进制对象表示 (CBOR) 的消息。

该方案基于哈希树的使用，最初以美国专利 `5,432,852` 的形式获得专利，该专利现已过期。

### 使用 LMS 的工作流

在多次尝试让有状态的签名算法变得更易用、更安全（包括尝试为有状态签名提供特殊的 `StateAwareSignature` 接口）之后，我们得到了线程安全的私钥，这些私钥会在每次签名操作时自动轮换索引，并且我们所称的“密钥分片 (key-shards)”。

密钥分片代表短时间私钥，占据 LMS 私钥密钥空间的一部分。对于 LMS 和 HSS，密钥分片是通过使用 `LMSPrivateKey` 接口上的 `extractKeyShard()` 方法创建的。

以下是 `LMSPrivateKey` 接口的定义：

```java
/**
 * LMS 私钥的基础接口
 */
public interface LMSPrivateKey
    extends LMSKey, PrivateKey
{
    /**
     * 返回下一次签名的索引。
     *
     * @return 下一次签名的索引号。
     */
    long getIndex();

    /**
     * 返回私钥剩余的使用次数。
     *
     * @return 密钥在耗尽前可以使用的次数。
     */
    long getUsagesRemaining();

    /**
     * 返回一个代表密钥空间分片的密钥，该分片可以被
     * 使用 `usageCount` 次。
     * <p>
     * 注意：这将为当前密钥使用范围 [index...index + usageCount)。
     * 
     * </p>
     * @param usageCount 密钥应该拥有的使用次数。
     * @return 一个基于当前密钥的、可以使用 `usageCount` 次的密钥。
     */
    LMSPrivateKey extractKeyShard(int usageCount);
}
```

请注意，该接口允许您检索私钥的剩余使用次数，以及在证书生成时将使用的下一个索引。我们稍后将看到索引使用的具体示例。

下面的示例代码提供了一个生成 LMS 密钥对的函数。

```java
/**
 * 生成一个基于 SHA-256、树高为 5 的 LMS 密钥对。
 *
 * @return 一个 LMS KeyPair
 */
public static KeyPair generateLMSKeyPair()
    throws GeneralSecurityException
{
    KeyPairGenerator kpg = KeyPairGenerator.getInstance("LMS", "BCPQC");

    kpg.initialize(new LMSKeyGenParameterSpec(
                            LMSigParameters.lms_sha256_n32_h5,
                            LMOtsParameters.sha256_n32_w1));

    return kpg.generateKeyPair();
}
```

请注意，在 LMS 密钥对生成的情况下，使用的哈希函数定义是树的属性。

在下面的代码中，我们看到如何对数据签名并验证生成的签名。

```java
/**
 * 使用 SHA-512 作为树摘要的 LMS 基础示例。
 */
public class LMSExample
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        Security.addProvider(new BouncyCastlePQCProvider());
        
        byte[] msg = Strings.toByteArray("hello, world!");

        KeyPair kp = generateLMSKeyPair();

        Signature lmsSig = Signature.getInstance("LMS", "BCPQC");

        lmsSig.initSign(kp.getPrivate());

        lmsSig.update(msg, 0, msg.length);

        byte[] s = lmsSig.sign();

        lmsSig.initVerify(kp.getPublic());

        lmsSig.update(msg, 0, msg.length);

        System.err.println("LMS verified: " + lmsSig.verify(s));
    }
}
```

### 使用 LMS 生成证书

下面的代码按照 `RFC 8708` [133] 的概述，使用 LMS 生成一个 X.509 证书。在此情况下，我们修改了生成证书的方式，因为 `getIndex()` 被用序列号。这里是示例代码：

```java
/**
 * 使用 SHA-512 作为树摘要的 LMS 基础示例。
 */
public class LMSExample
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        Security.addProvider(new BouncyCastlePQCProvider());
        
        byte[] msg = Strings.toByteArray("hello, world!");

        KeyPair kp = generateLMSKeyPair();

        Signature lmsSig = Signature.getInstance("LMS", "BCPQC");

        lmsSig.initSign(kp.getPrivate());

        lmsSig.update(msg, 0, msg.length);

        byte[] s = lmsSig.sign();

        lmsSig.initVerify(kp.getPublic());

        lmsSig.update(msg, 0, msg.length);

        System.err.println("LMS verified: " + lmsSig.verify(s));
    }
}
```

*(注：由于原文中存在重复的段落，译文已根据逻辑进行了去重处理，确保内容连贯)*

```java
/**
 * 使用 SHA-512 作为树摘要的 LMS 基础示例。
 */
public class LMSExample
{
    public static void main(String[] args)
        throws GeneralSecurityException
    {
        Security.addProvider(new BouncyCastlePQCProvider());
        
        byte[] msg = Strings.toByteArray("hello, world!");

        KeyPair kp = generateLMSKeyPair();

        Signature lmsSig = Signature.getInstance("LMS", "BCPQC");

        lmsSig.initSign(kp.getPrivate());

        lmsSig.update(msg, 0, msg.length);

        byte[] s = lmsSig.sign();

        lmsSig.initVerify(kp.getPublic());

        lmsSig.update(msg, 0, msg.length);

        System.err.println("LMS verified: " + lmsSig.verify(s));
    }
}
```

```java
/**
 * 使用 LMS 私钥签名的证书
 * @param privKey 使用的私钥
 * @param issuer 签发者名称
 * @param pubKey 关联的公钥
 * @param subject 证书主体名称
 * @return X509 证书持有者
 */
public static X509CertificateHolder createLMSCertificate(
```



## 代码示例：LMS 证书创建与 HSS/XMSS 密钥生成

### LMS 证书创建主流程

```java
16         LMSPrivateKey privKey, X500Name issuer,
17         PublicKey pubKey, X500Name subject)
18         throws OperatorException
19     {
20         X509v1Builder certBldr = new JcaX509v1Builder(
21                                     issuer,
22                                     BigInteger.valueOf(privKey.getIndex())),
23                                     calculateDate(0),
24                                     subject,
25                                     pubKey);
26                                 
27         ContentSigner signer = new JcaSignerBuilder("LMS")
28                                 .setProvider("BCPQC").build(privKey);
29 
30         return certBldr.build(signer);
31     }
32 
33     public static void main(String[] args)
34         throws Exception
35     {
36         Security.addProvider(new BouncyCastlePQCProvider());
37         
38         X500Name name = new X500Name("CN=LMS Demo Root");
39 
40         KeyPair kp = generateLMSKeyPair();
41         LMSPrivateKey privKey = (LMSPrivateKey)kp.getPrivate();
42 
43         // 我们放弃索引为 0 的签名 - RFC 5280 要求
44         // 证书序列号大于 0。
45         privKey.extractKeyShard(1);
46 
47         X509CertificateHolder certHldr = createLMSCertificate(
48             privKey, name, kp.getPublic(), name);
49 
50         System.out.println("key index: " + privKey.getIndex());
51         System.out.println("serial no: " + certHldr.getSerialNumber());
52         System.out.println("sig index: " +
53                        getLMSSignatureIndex(certHldr.getSignature()));
54         System.out.println("verifies : " + certHldr.isSignatureValid(
55             new JcaContentVerifierBuilder()
56                 .setProvider("BCPQC").build(kp.getPublic())));
57     }
58 }
```

你会注意到在 52/53 行签名的索引被打印出来。执行此操作的代码简单，因为索引是签名的前 4 个字节。这里是函数定义：

```java
1   /**
2    * 返回创建 LMS 签名时使用的索引。
3    *
4    * @return 编码签名中使用的索引。
5    */
6   public static long getLMSSignatureIndex(byte[] lmsSig)
7   {
8       return Pack.bigEndianToInt(lmsSig, 0) & 0xFFFFFFFFL;
9   }
```

签名中索引值的存在也提供了其他路径来判断某些情况是否出错以及索引是否以某种方式被重用。在我们观察的示例中，我们公开跟踪索引值，因为它也被用于证书的序列号。即使你使用了 `HSM`，对这些保持警惕也永远无坏处。

当然，取决于你遵循的是哪种证书配置，可能会存在陷阱。某些配置要求证书序列号使用随机位生成器生成。如果你正在处理此类问题，请为 `CA` 分配一个随机种子，然后使用 `HMAC` 或 `XOF` 结合 `seed` 和 `key index` 作为输入来为证书生成序列号。虽然这创建了一个原始的 `DRBG`（确定性随机生成器），使得输出是不可预测且不可逆的，但这意味着你永远不会两次获得相同的序列号——除非你给函数提供了相同的输入，这将表明序列号被第二次使用。

如果你运行该示例且一切顺利，你应该能看到以下输出：

```
key index: 2
serial no: 1
sig index: 1
verifies : true
```

显示存储在签名中的签名索引与作为证书序列号使用的索引相同。

### HSS

分层签名系统（`HSS`）提供了一种增加单个公钥可验证签名数量的方法，代价是增加了签名的大小和私钥的大小。本质上，创建了一个树的层次结构，但叶节点树用于对实际数据签名，而父树用于对叶节点树的公钥签名。

![HSS 的多树方法意味着树的低层根节点可以根据需要计算。](img/chapter15----HSS.png)

HSS 的多树方法意味着树的低层根节点可以根据需要计算。

从表面上看，从 API 的角度来看，这意味着用法上的唯一区别是密钥对的生成，因为需要指定额外的子树。以下示例代码提供了生成 HSS 密钥对的函数，它使用了 2 层树，深度均为 5，总深度为 10：

```java
 1   /**
 2    * 基于 SHA-256 生成树高为 10 的 HSS 密钥对。
 3    *
 4    * @return 一个 HSS KeyPair
 5    */
 6   public static KeyPair generateHSSKeyPair()
 7       throws GeneralSecurityException
 8   {
 9       KeyPairGenerator kpg = KeyPairGenerator.getInstance("LMS", "BCPQC");
10 
11       kpg.initialize(new LMSHSSKeyGenParameterSpec(
12           new LMSKeyGenParameterSpec(LMSigParameters.lms_sha256_n32_h5,
13                                           LMOtsParameters.sha256_n32_w1),
14           new LMSKeyGenParameterSpec(LMSigParameters.lms_sha256_n32_h5,
15                                           LMOtsParameters.sha256_n32_w1)));
16 
17       return kpg.generateKeyPair();
18   }
```

这种方法的趣味性之处在于，如果你尝试这种方法并观察公钥编码的大小，你会发现该编码的大小与单层 LMS 密钥的大小相同。原因之前已经暗示过，即在于 `2` 级 HSS 密钥签名实际上是使用 HSS 公钥签名的子树公钥的编码，然后是由子树单次使用私钥生成的签名编码。因此，验证 HSS 签名所需的所有子树信息都包含在编码中，唯一缺失的信息是组成 HSS 层次结构的基树的公钥。

无论如何，这意味着你会发现自己可以像之前应用基础 LMS 密钥一样应用 HSS 密钥。甚至不需要更改签名算法的名称。

### XMSS

`XMSS` 描述于 `RFC 8391` “XMSS: 扩展 Merkle Signature 方案” [131]，该标准于 2018 年 5 月定型。

`XMSS` 像 `LMS` 一样基于哈希，但使用了 `WOTS+` 原语（Winternitz 一次签名的扩展）。`WOTS+` 原语是一种通过取输入消息和单次使用的私钥来计算签名，并产生形成签名的哈希链的操作。在这种情况下，私钥是一组随机字节字符串，公钥也表示为针对构成私钥的随机字节字符串计算的哈希链。与我们之前看到的方案不同（之前的方案验证通常使用公钥和数据进行与签名匹配的计算），`WOTS+` 签名的计算方式使得验证使用签名和数据来计算另一个哈希链，如果签名和数据确实相互相关并与原始私钥相关，该链将与构成公钥的哈希链对应。

`XMSS` 有两种变体；第一种是基础 `XMSS`，它在单树哈希上运行；第二种是 `XMSS^MT`，它在若干层高度减小的 `XMSS` 树上运行。与 `XMSS` 配置相比，`XMSS^MT` 配置允许更快的密钥生成（指数级）和更短的签名时间（线性）。另一方面，`XMSS^MT` 密钥对生成的签名大小上将线性增长。选择哪种方案取决于你希望什么样的权衡。

在 `XMSS` 的限制方面，私钥的使用次数限制为 `2^h`，其中 `h` 是树的高度。`XMSS^MT` 同时使用高度 `h` 和层数 `d` 进行配置，每层由高度为 `h / d` 的 XMSS 树组成（`d` 必须能整除 `h`）。顶层有一棵 XMSS 树，而底层有 `2^{(h - (h / d))}` 棵树。底层之树用于签名下一层，底层的树用于签名实际消息，同样提供了 `2^h` 可能的签名。

以下示例代码提供了一个生成 XMSS 密钥对的函数，其中 `h` 设置为 10。用于构建公钥和任何生成签名的哈希函数将 SHA-512。

```java
 1   /**
 2    * 基于 SHA-512 生成树高为 10 的 XMSS 密钥对。
 3    *
 4    * @return 一个 XMSS KeyPair
 5    */
 6   public static KeyPair generateXMSSKeyPair()
 7       throws GeneralSecurityException
 8   {
 9       KeyPairGenerator kpg = KeyPairGenerator.getInstance("XMSS", "BCPQC");
10 
11       kpg.initialize(XMSSParameterSpec.SHA2_10_512);
12 
13       return kpg.generateKeyPair();
14   }
```

注意，在 XMSS 密钥对生成的情况下，使用的哈希函数定义是树的属性。

在下面的代码中，我们看到如何对实际数据进行签名并验证生成的签名。

```java
/**
 * 使用 SHA-512 作为树摘要的 XMSS 基础示例。
 */
public class XMSSExample
{
   public static void main(String[] args)
       throws GeneralSecurityException
   {
       byte[] msg = Strings.toByteArray("hello, world!");
       KeyPair kp = generateXMSSKeyPair();
       Signature xmssSig = Signature.getInstance("XMSS", "BCPQC");
       xmssSig.initSign(kp.getPrivate());
       xmssSig.update(msg, 0, msg.length);
       byte[] s = xmssSig.sign();
       xmssSig.initVerify(kp.getPublic());
       xmssSig.update(msg, 0, msg.length);
       System.err.println("XMSS verified: " + xmssSig.verify(s));
   }
}
```

你也可以看到算法描述为“XMSS”，在这种情况下，消息将直接哈希到签名中，预哈希按照通常的 JCA 指定，例如“SHA512withXMSS”，其中用于计算消息哈希的摘要名称指定在签名算法的开头。Bouncy Castle 目前将预哈希摘要限制为构建哈希树时使用的摘要。虽然你可以指定一个与密钥生成时不同的摘要来计算形成 XMSS 算法签名消息的数据摘要，但使用相同的摘要更好。除了安全级别可能存在差异外，如果允许不同的算法，可能会出现一些异常情况。如果你还对摘要进行参数化，某些可能会认为不同的参数化可能适合他们的用途——SHA-256 并不是产生 256 位摘要的唯一方法。

假设一切运行正常，你应该会得到以下输出：

```
XMSS verified: true
```

如果你想尝试在密钥对生成时调整树的高度，你会发现这确实会影响示例运行的时间。为 XMSS 或 `XMSS^MT` 的私钥设置一个合理的寿命也有助于系统性能。

## 使用 XMSS 的工作流

与 LMS 类似，XMSS 私钥支持 `extractKeyShard()` 方法，并且有一个与私钥相关联的剩余使用次数计数，该计数最终会减到零。如果你尝试下一个示例，你将看到当密钥的使用计数为零时会发生什么。

```java
/**
 * XMSS 私钥使用次数耗尽的示例及影响。
 */
public class XMSSExceptionExample
{
   public static void main(String[] args)
       throws GeneralSecurityException
   {
       byte[] msg = Strings.toByteArray("hello, world!");
       KeyPair kp = generateXMSSKeyPair();
       XMSSPrivateKey privKey = (XMSSPrivateKey)kp.getPrivate();
       Signature xmssSig = Signature.getInstance("XMSS", "BCPQC");

       // 这使用 extractKeyShard() 获取单次使用的密钥。
       XMSSPrivateKey sigKey = privKey.extractKeyShard(1);

       // 取消此行的注释以使示例完整
//       sigKey = privKey.extractKeyShard(2);

       xmssSig.initSign(sigKey);
       xmssSig.update(msg, 0, msg.length);
       byte[] s1 = xmssSig.sign();

       // 这里的 0 值告诉我们该密钥无法再次使用。
       System.out.println("xmssSig usages remaining: " + sigKey.getUsagesRemaining());

       xmssSig.update(msg, 0, msg.length);

       // 只有当调用 extractKeyShard() 时参数大于 1，此行才会起作用。
       byte[] s2 = xmssSig.sign();
   }
}
```

按照目前的实现运行示例将产生带有以下消息的异常：

```
Exception in thread "main" java.security.SignatureException: no usages of private key remaining
```

如果你移除第 19 行的注释字符（这将重新初始化密钥使其具有 2 次使用机会而不是现有的 1 次），你会发现示例将运行结束而不抛出异常，并产生使用计数消息。

## 使用 XMSS 生成证书

以下代码按照 [73] 所示使用 XMSS 生成 X.509 证书。与 LMS 示例一样，此示例使用 `privKey.getIndex()` 作为证书序列号的源。

```java
/**
 * 构建基于 XMSS 的证书示例 - 此例中为自签名。
 */
public class XMSSCertExample
{
   /**
    * 创建由 XMSS 密钥签名的 X.509 证书，索引即序列号。
    * @param privKey 要使用的 XMSS 密钥。
    * @param issuer 证书的颁发者。
    * @param pubKey 证书中的公钥。
    * @param subject 与公钥关联的名称。
    * @return 一个 X509 证书持有者。
```



```java
public static X509CertificateHolder createXMSSCertificate(
    XMSSPrivateKey privKey, X500Name issuer,
    PublicKey pubKey, X500Name subject)
    throws Exception
{
    X509v1CertificateBuilder certBldr = new JcaX509v1CertificateBuilder(issuer,
        BigInteger.valueOf(privKey.getIndex()));

    ContentSigner signer = new JcaSignerBuilder("XMSS")
        .setProvider("BCPQC").build(privKey);

    return certBldr.build(signer);
}

public static void main(String[] args)
    throws Exception
{
    X500Name name = new X500Name("CN=XMSS Demo Certificate");

    KeyPair kp = generateXMSSKeyPair();

    XMSSPrivateKey privKey = (XMSSPrivateKey)kp.getPrivate();

    // 我们丢弃索引为 0 的签名 - RFC 5280 要求
    // 序列号大于 0。
    privKey.extractKeyShard(1);

    X509CertificateHolder certHldr = createXMSSCertificate(
        privKey, name, kp.getPublic(), name);

    System.out.println("key index: " + privKey.getIndex());
    System.out.println("serial no: " + certHldr.getSerialNumber());
    System.out.println("sig index: "
        + getXMSSSignatureIndex(certHldr.getSignature()));
    System.out.println("verifies : " + certHldr.isSignatureValid(
        new JcaContentVerifierProviderBuilder()
            .setProvider("BCPQC").build(kp.getPublic())));
}
```

与 LMS 类似，索引数字是签名的前 4 个字节。以下是 `getXMSSSignatureIndex()` 方法的定义：

```java
/**
 * 返回创建 XMSS 签名时使用的索引。
 *
 * @return 编码签名的索引。
 */
public static long getXMSSSignatureIndex(byte[] xmssSig)
{
    return Pack.bigEndianToInt(xmssSig, 0) & 0xFFFFFFFFL;
}
```

如果你运行示例且一切顺利，你将看到以下输出：

```
key index: 2
serial no: 1
sig index: 1
verifies : true
```

这表明存储在签名中的签名索引与证书的序列号相同。

我们在这里的示例中重点关注了 `XMSS`。`XMSS^MT` 的用法基本上相同，只是将算法名称“XMSS”替换为“XMSSMT”。唯一的区别在于 `KeyPairGenerator` 的使用上，它需要使用 `XMSSMTParameterSpec`，该规范包含了高度 $h$ 和层数 $d$。以下代码片段显示了如何创建一个 `XMSS^MT` 密钥对，其签名限制与我们之前生成的 `XMSS` 密钥对相同的 $2^{20}$：

```java
KeyPairGenerator kpg = KeyPairGenerator.getInstance("XMSSMT", "BCPQC");
kpg.initialize(new XMSSMTParameterSpec(20, 2, XMSSMTParameterSpec.SHA512));
KeyPair kp = kpg.generateKeyPair();
```

`XMSSMTParameterSpec` 的第二个参数是层数，因此此示例将生成一个适用于 2 层 `XMSS` 树的密钥对，每层的高度为 $20 / 2$。这是标准参数集之一，也可以写为 `XMSSMTParameterSpec.XMSSMT_SHA2_20d2_512`。

### 无状态签名算法

正如“一次性签名”这一术语所暗示的（至少在这种情况下），你不想两次使用同一个私钥进行签名，因为这会削弱应用私钥的方案的整体安全性。这里可能出现的问题从简单到都有，例如对消息进行签名，但在更新的密钥持久化之前服务器崩溃了；或者某人从备份恢复系统时，没有意识到他们也在“回滚”私钥。取决于你的具体操作，这些问题通常都是可以管理的，例如通过在每次服务器启动时生成新密钥对等技术，或者定期持久化，并在生成任何发布签名之前跳过固定数量的密钥（假设在“从备份中恢复”事件时产生新密钥对）。

### 无状态哈希签名算法

对于基于哈希的签名算法，Oded Goldreich [5] 提出了一种消除状态问题的方法，即在私钥中使用树的随机分支，并在分支重用风险变得不可接受的高时，通过停止使用私钥来让安全性“优雅地”降低。这种方法是基于 NIST PQC 决赛选手 SPHINCS+ [14] 构建的。

### 查看 SPHINCS+

SPHINCS+ 带我们回到了更熟悉的领域。该算法是无状态的，这意味着私钥不会随着生成的每个签名而改变。SPHINCS+ 通过将超大树上的一次性签名机制与“多次”签名机制相结合，并随机选择分支来实现此点的。

在写本文时，SPHINCS+ 已被选为待标准化的决赛选手。标准化过程可能会减少目前提供的参数集数量，并可能添加一些适用于想要生成少量签名的用户的新参数集。SPHINCS+ 可以生成的最大签名数量为 $2^{64}$，这是一个很大的数字。不过，这个最大值会影响密钥和签名的大小，SPHINCS+ 的关注领域之一是代码签名，因此人们在讨论是否总是需要如此大的范围——假设每月更新一次固件，1200 次签名可以让你使用 100 年，再乘以 100 倍以防意外，你离 $2^{64}$ 仍然很远。

无论如何，重点在于虽然标准化后 SPHINCS+ 的示例示例感觉不太可能改变，但现实是这些参数及其用法很可能在 2024 年年中尚未定论。

以下方法将根据传入的参数规范生成 SPHINCS+ 密钥对。

```java
/**
 * 生成一个 SPHINCS+ 密钥对。
 * 
 * @param sphincsPlusParameterSpec 要使用的 SPHINCS+ 参数集。
 * @return 一个 SPHINCS+ 密钥对。
 */
public static KeyPair generateSPHINCSPlusKeyPair(
    SPHINCSPlusParameterSpec sphincsPlusParameterSpec)
    throws GeneralSecurityException
{
    KeyPairGenerator kpg = KeyPairGenerator.getInstance("SPHINCSPlus", "BCPQC");
    kpg.initialize(sphincsPlusParameterSpec, new SecureRandom());
    return kpg.generateKeyPair();
}
```

一旦我们有了密钥对，就可以使用私钥进行签名生成。下面的方法允许对简单消息进行签名。

```java
/**
 * 使用传入的 SPHINCS+ 私钥和输入数据生成编码的 SPHINCS+ 签名。
 *
 * @param spxPrivate 用于生成签名的私钥。
 * @param input 要签名的输入。
 * @return 编码的签名。
 */
public static byte[] generateSPHINCSPlusSignature(
    PrivateKey spxPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SPHINCSPlus", "BCPQC");
    signature.initSign(spxPrivate);
    signature.update(input);
    return signature.sign();
}
```

```java
/**
 * @param spxPublic 签名创建者的公钥。
 * @param input 应该签名的输入。
 * @param encSignature 编码的签名。
 * @return 如果签名通过验证则为 true，否则为 false。
 */
public static boolean verifySPHINCSPlusSignature(
    PublicKey spxPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("SPHINCSPlus", "BCPQC");
    signature.initVerify(spxPublic);
    signature.update(input);
    return signature.verify(encSignature);
}
```

从上面可以看出，它比我们看到的任何签名算法都不复杂。处理或担心状态问题已经过去了。最后，我们有一个简单方法来使用相应的公钥验证生成的签名。

### 基于格的签名算法

目前签名类别中选定的另外两种算法是 CRYSTALS-Dilithium [19]（通常称为 Dilithium）和 Falcon [18]。这些算法像 SPHINCS+ 一样都是无状态的，并且具有具名的参数。你可以在 `org.bouncycastle.pqc.jcajce.spec.DilithiumParameterSpec` 中找到 Dilithium 的可用参数，在 `org.bouncycastle.pqc.jcajce.spec.FalconParameterSpec` 中找到 Falcon 的可用参数。

`org.bouncycastle.pqc.jcajce.spec.FalconParameterSpec`。再次记住，这些算法尚未成为官方标准，但 Bouncy Castle 目前实现的内容将让你对它的未来的发展方向有一个良好的直观认识。

由于两种算法的用法仅在参数选择上有所不同，我们在这里只看一个使用 Dilithium 的示例。对于 Falcon，你只需要将“Dilithium”替换为“Falcon”，并使用预定义的 `FalconParameterSpec` 类之一即可。

以下方法将根据给传入的参数规范（spec）生成一个 Dilithium 密钥对。

```java
/**
 * 生成一个 Dilithium 密钥对。
 * 
 * @param dilithiumPlusParameterSpec 要使用的 Dilithium 参数集。
 * @return 一个 Dilithium 密钥对。
 */
public static KeyPair generateDilithiumKeyPair(
    DilithiumParameterSpec dilithiumPlusParameterSpec)
    throws GeneralSecurityException
{
    KeyPairGenerator kpg = KeyPairGenerator.getInstance("Dilithium", "BCPQC");
    kpg.initialize(dilithiumPlusParameterSpec, new SecureRandom());

    return kpg.generateKeyPair();
}
```

一旦我们有了密钥对，就可以使用私钥进行签名生成。下面的方法允许对简单的消息进行签名。

```java
/**
 * 使用传入的 Dilithium 私钥和输入数据生成编码的 Dilithium 
 * 签名。
 *
 * @param dilPrivate 用于生成签名的私钥。
 * @param input 要被签名的输入数据。
 * @return 编码的签名。
 */
public static byte[] generateDilithiumSignature(
    PrivateKey dilPrivate, byte[] input)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("Dilithium", "BCPQC");

    signature.initSign(dilPrivate);

    signature.update(input);

    return signature.sign();
}
```

最后，我们有一个简单的方法，用于使用私钥对应的公钥来验证生成的 Dilithium 签名。

```java
/**
 * 如果传入的 Dilithium 签名通过传入的 Dilithium 
 * 公钥和输入通过验证，则返回 true。
 *
 * @param dilPublic 签名创建者的公钥。
 * @param input 原本应该被签名的输入数据。
 * @param encSignature 编码的签名。
 * @return 如果签名通过验证，则返回 true，否则返回 false。
 */
public static boolean verifyDilithiumSignature(
    PublicKey dilPublic, byte[] input, byte[] encSignature)
    throws GeneralSecurityException
{
    Signature signature = Signature.getInstance("Dilithium", "BCPQC");

    signature.initVerify(dilPublic);

    signature.update(input);

    return signature.verify(encSignature);
}
```

Dilithium 参数现在都是命名的（至少目前是这样），因此将上述方法用于生成签名只需提供我们想要使用的命名参数规范，我们就可以利用之前描述的方法，如下所示示例代码所示：

```java
KeyPair dilKp = generateDilithiumKeyPair(
    DilithiumParameterSpec.dilithium2);

byte[] dilithiumSignature = generateDilithiumSignature(
    dilKp.getPrivate(), Strings.toByteArray("hello, world!"));

System.out.println("Dilithiun verified: " + verifyDilithiumSignature(
```



dilKp.getPublic(), Strings.toByteArray("hello, world!"), dilithiumSignature));

```

运行示例代码应该产生以下输出：

```
Dilithium verified: true
```

这表明签名验证正确。

### 密钥封装机制 (Key Encapsulation Mechanisms)

Bouncy Castle 以两种方式支持密钥封装机制 (KEM)。一种是作为其他密钥的传输机制，通过 `Cipher` 类及其密钥封装（key wrapping）功能实现。另一种是作为种子生成机制，由 KEM 生成的种子密钥可以直接使用。后者通过 `KeyGenerator` 类实现。这两种方法都可用于此处列出的所有 KEM 算法。

#### Classic McEliece

Classic McEliece [16] 现在已移动到 NIST 密钥封装机制算法竞赛的第 4 轮。除了可能是 PQC 竞赛中研究最充分的算法之一外，由于其历史久远（追溯到 1970 年代），它也受到关注，因为该算法的第 3 版本也已被德国 BSI 接受 [15]。

Classic McEliece 的密钥对生成允许使用命名参数类型生成密钥，这些类型代表 128 位、192 位和 256 位安全性。总共有 10 组命名参数集，其强度如下表所示：

| 参数集 | 安全性 (位) | 密钥大小 (字节) | 密文 (字节) |
| --- | --- | --- | --- |
| mceliece3864 | 128 | 261 | 128 |
| mceliece4096 | 128 | 273 | 128 |
| mceliece4608 | 192 | 330 | 192 |
| mceliece5293 | 192 | 346 | 192 |
| mceliece6960 | 192 | 438 | 192 |
| mceliece8192 | 192 | 468 | 192 |
| mceliece6688 | 256 | 564 | 256 |
| mceliece10368 | 256 | 672 | 256 |
| mceliece12960 | 256 | 679 | 256 |
| mceliece16384 | 256 | 801 | 256 |

Classic McEliece 在 BC 提供程序中通过算法名称“CMCE”引用。在我们可以对该算法进行任何操作之前，首先需要生成一对。可以通过使用以下提供的参数规范来实现：

```java
/**
 * 生成一个密钥对。
 *
 * @param cmceParameters 要使用的 CMCE 参数集。
 * @return 一个 Classic McEliece 密钥对。
 */
public static KeyPair cmceGenerateKeyPair(CMCEParameterSpec cmceParameters)
    throws GeneralSecurityException
{
    KeyPairGenerator kpg = KeyPairGenerator.getInstance("CMCE", "BCPQC");
    kpg.initialize(cmceParameters, new SecureRandom());

    return kpg.generateKeyPair();
}
```

`CMCEParameterSpec` 包含了所有 10 个参数集。除了可以使用 `CMCEParameterSpec` 外，CMCE `KeyPairGenerator` 还可以接受 Java 11 添加到 Java 安全 API 的 `NamedParameterSpec` 类。

对于 Classic McEliece，我们将查看通过 `Cipher` 类使用 KEM，在这种情况下，内部生成的密钥将用于生成一个对称封装密钥，用于加密被封装的密钥。这两个密文随后会被拼接并发送。正如如下为发起者编写的示例所示，拼接将在内部发生，并返回单个字节数组。

```java
public static byte[] cmceGeneratePartyU(PublicKey vPubKey, SecretKey secKey)
    throws GeneralSecurityException
{
    Cipher cipher = Cipher.getInstance("CMCE", "BCPQC");

    cipher.init(Cipher.WRAP_MODE, vPubKey, new SecureRandom());

    return cipher.wrap(secKey);
}
```

在我们生成了加密密钥和封装密钥的密文后，我们将密文传递给接收者，他们反向操作，解密密钥，生成封装密钥，最后解封装被封装的密钥并将其返回。所有这些工作也都是在 `Cipher` 内部完成，这意味着解封装代码可以写如下：

```java
public static SecretKey cmceGeneratePartyV(
    PrivateKey vPriv, byte[] encapsulation, String keyAlgorithm)
    throws GeneralSecurityException
{
    Cipher cipher = Cipher.getInstance("CMCE", "BCPQC");
    cipher.init(Cipher.UNWRAP_MODE, vPriv);
    return (SecretKey)cipher.unwrap(
                    encapsulation, keyAlgorithm, Cipher.SECRET_KEY);
}
```

最后，这是一个完整流程的示例，展示了 Classic McEliece 密钥对的生成以及 128 位 AES 密钥的封装与解封装。

```java
KeyPair kp = cmceGenerateKeyPair(CMCEParameterSpec.mceliece348864);
SecretKey aesKey1 = new SecretKeySpec(
            Hex.decode("000102030405060708090a0b0c0d0e0f"), "AES");
byte[] encKey = cmceGeneratePartyU(kp.getPublic(), aesKey1);
SecretKey aesKey2 = cmceGeneratePartyV(kp.getPrivate(), encKey, "AES");
System.out.println("keys match: "
    + Arrays.areEqual(aesKey1.getEncoded(), aesKey2.getEncoded()));
```

并且，假设没有出现错误，运行上述代码段应该产生：

```
keys match: true
```

表明 AES 密钥已通过密文正确传输。

示例中使用的参数集 `mceliece348864` 具有 128 位的安全强度，并产生 1024 位的密文。由 `cmceGeneratePartyU` 返回的组合密文总长度为 1216 位——其中 1024 位用于加密的密钥，192 位用于封装的密钥。正如你可能意识到的，正是 Classic McEliece 关联的短密文以及其健壮性是它受关注的原因。如果你切换到更安全的参数集（例如 `mceliece6960119`）并封装一个 256 位 AES 密钥，你会发现总密文的大小仅增加到 2128 位，仅略大于 2048 位，但提供了比 2048 位 RSA 更高的安全级别（后者目前估计的安全性仅为 112 位）。

我们现在将看一个如何结合 KEM 使用 `KeyGenerator` 类的示例。Classic McEliece 也支持此操作，但出于兴趣考虑，我们将看一个使用 FrodoKEM 的示例。

#### FrodoKEM

FrodoKEM [17] 最初是 NIST 密钥封装机制备选候选算法之一。它也值得关注，因为该算法的第 3 版本已被德国的 BSI 接受 [15]，所以虽然它在 NIST 流程中被淘汰了，但可能仍有生命力。该算法有两个版本，区别在于与密钥对关联的公矩阵的生成方式——一种使用 `AES` 原语，另一种则基于 `SHAKE`。

`FrodoKEM` 的密钥对生成允许生成代表 128 位、192 位和 256 位安全性的命名参数类型的密钥，分别产生公钥大小为 96、152 和 200 字节的密钥。考虑到这两个版本，这组成了六组可以用于生成密钥对的参数集。如下示例所示，生成密钥对只需传入相应的参数集。

```java
public static KeyPair frodoGenerateKeyPair(FrodoParameterSpec frodoParameters)
    throws GeneralSecurityException
{
    KeyPairGenerator kpg = KeyPairGenerator.getInstance("Frodo", "BCPQC");
    kpg.initialize(frodoParameters, new SecureRandom());
    return kpg.generateKeyPair();
}
```

FrodoKEM 的 `KeyPairGenerator` 还可以接受添加到 Java Security 中的 `NamedParameterSpec` 类。虽然 FrodoKEM 也支持我们在 Classic McEliece 中看到的机制，但在本示例中，我们将查看一个使用 KEM 操作的密钥交换发起者，其中由 KEM 生成的密钥将用于其他用途。由于我们想要直接访问 KEM 生成的密钥，我们使用 `KeyGenerator` 类和 `KEMGenerateSpec`，后者接收接收者的公钥并使用 KEM 生成封装和密钥，并将其以实现 `SecretKeyWithEncapsulation` 的对象形式返回给我们。

```java
public static SecretKeyWithEncapsulation frodoGeneratePartyU(PublicKey vPubKey)
    throws GeneralSecurityException
{
    KeyGenerator keyGen = KeyGenerator.getInstance("Frodo", "BCPQC");
    keyGen.init(new KEMGenerateSpec(vPubKey, "AES"), new SecureRandom());
    return (SecretKeyWithEncapsulation)keyGen.generateKey();
}
```

`SecretKeyWithEncapsulation` 上的 `getEncoded()` 方法返回封装生成的密钥。`SecretKeyWithEncapsulation` 类还有一个 `getEncapsulation()` 方法，返回用于发送给接收者的种子加密结果。`SecretKeyWithEncapsulation` 还实现了 `Destroyable`，因此在不再需要时可以擦除对象的内容。在接收方，我们仍然使用 `KeyGenerator` 类，但这次使用了 `KEMExtractSpec`，它使用接收者的私钥和从发起者处收到的封装。

```java
public static SecretKeyWithEncapsulation frodoGeneratePartyV(PrivateKey vPriv, byte[] encapsulation)
    throws GeneralSecurityException
{
    KeyGenerator keyGen = KeyGenerator.getInstance("Frodo", "BCPQC");
    keyGen.init(new KEMExtractSpec(vPriv, encapsulation, "AES"), new SecureRandom());
    return (SecretKeyWithEncapsulation)keyGen.generateKey();
}
```

正如你所见，为了一致性，该方法再次返回 `SecretKeyWithEncapsulation`。我们可以将这些方法结合在一起，提供一个使用 FrodoKEM 进行密钥交换的短示例。如果你想自己尝试，可以使用以下：

```java
KeyPair kp = frodoGenerateKeyPair(FrodoParameterSpec.frodokem64);
SecretKeyWithEncapsulation secEnc1 = frodoGeneratePartyU(kp.getPublic());
SecretKeyWithEncapsulation secEnc2 = frodoGeneratePartyV(kp.getPrivate(), secEnc1.getEncapsulation());
System.out.println("secrets match: "
    + Arrays.areEqual(secEnc1.getEncoded(), secEnc2.getEncoded()));
```

假设一切顺利，你应该看到：

```
secrets match: true
```

表明封装已成功生成并解密。如果你想从该密钥生成一个密钥，而不仅仅是加密“随机数据”（即另一个密钥或私钥），正如我们之前在 Classic McEliece 中看到的密钥传输机制那样，该密钥非常适合作为 KDF 或类似 SHAKE 的 XOF 的输入。我们稍后在讨论混合加密时会看到相关的示例。修改示例以尝试不同的参数也是值得的。在 Bouncy Castle 中，你会发现密钥的大小随参数安全级别的改变而改变，位强度反映了参数的安全强度。

#### CRYSTALS-Kyber

我们在这个类别中看到的最后一个算法是 CRYSTALS-Kyber [20]，它是 CRYSTALS-Dilithium 的 KEM 相关算法。与 Dilithium 一样，CRYALS-Kyber 通常被称为 Kyber。

Kyber 也被选中标准化。在写作期间，它是唯一被中的 PQC KEM 算法。目前正在进行第四轮讨论，因此预计很快会有更多算法加入列表。与后量子签名算法一样，请注意“选中”并不等同于“标准化”，因此算法参数可能会发生一些变化。

如如下例所示，除了 Kyber 的参数规范选择和密钥对名称生成外，其过程与 FrodoKEM 的流程几乎相同：

```java
public static KeyPair kyberGenerateKeyPair(KyberParameterSpec kyberParameters)
    throws GeneralSecurityException
{
    KeyPairGenerator kpg = KeyPairGenerator.getInstance("Kyber", "BCPQC");
    kpg.initialize(kyberParameters, new SecureRandom());

    return kpg.generateKeyPair();
}
```

Kyber 也可以配合 `Cipher` 类使用，但在这种情况下，我们将限制为使用 `KeyGenerator`。我们这样做是因为在我们在本章节稍后讨论的混合加密时，将会用到 `PartyU` 和 `PartyV` 方法。

这里是 Kyber 的 `PartyU`（即发起者）方法。与之前一样，该方法使用 `Kyber` 公钥和 `SecureRandom` 来生成共享密钥以及一个从公钥和共享密钥值派生的封装（encapsulation）。

```java
public static SecretKeyWithEncapsulation kyberGeneratePartyU(PublicKey vPubKey)
    throws GeneralSecurityException
{
    KeyGenerator keyGen = KeyGenerator.getInstance("Kyber", "BCPQC");

    keyGen.init(new KEMGenerateSpec(vPubKey, "AES"), new SecureRandom());

    return (SecretKeyWithEncapsulation)keyGen.generateKey();
}
```

接下来是 `PartyV`（即响应者/接收者）方法。

```java
public static SecretKeyWithEncapsulation kyberGeneratePartyV(
    PrivateKey vPriv, byte[] encapsulation)
    throws GeneralSecurityException
{
```



## 混合加密

虽然新算法的出现意味着帮助已经在路上了，但另一个备受关注的想法是混合加密领域，在该领域中，使用后量子算法（PQC）来对现有加密方案进行量子加固。对于希望获得消息长期保护的情况，这非常有用，因为现在增加一些量子硬性被认为可以消除日后进行重新加密的需求。

为了让你了解其工作原理，值得重新回顾 EC 密钥协商，因为该机制非常适合并行使用额外的算法。随着 NIST SP 800-56C Rev. 2 [31] 的发布，现在还有两种认可的、认证合规的机制用于添加外部 PQC 算法，这在现在尤为重要，因为我们可能等到 2024 年才能看到认证的 KEM 算法。我们将首先查看使用 `OtherInfo` 结构和 NIST SP 800-56C 的方法。

### 使用 OtherInfo 的混合加密 - 设置

为了提供一个混合加密的现成示例，我们将提供一个简单的类来生成 EC 密钥对，作为混合方案的基础。

```java
public class KasParty
{
    protected final KeyPair kp;

    KasParty(SecureRandom random)
        throws GeneralSecurityException
    {
        KeyPairGenerator kpGen = KeyPairGenerator.getInstance("EC", "BC");

        kpGen.initialize(new ECGenParameterSpec("P-256"), random);

        this.kp = kpGen.generateKeyPair();
    }

    public PublicKey getPublic()
    {
        return kp.getPublic();
    }
}
```

在这种情况下我们将使用 `Kyber` PQC 加密算法，尽管其他算法（如 `FrodoKEM`）也可以。

生成器需要两个扩展类而不是一个，来实现 U 和 V 双方之间协商的双方。其原因是发起者侧（或 U 方）将产生公钥，而响应者侧（或 V 方）将产生包含封装密钥值的封装，而 U 方必须提取该值。

我们将查看 U 端。

### 使用 OtherInfo 的混合加密 - U 端

以下代码实现了协商的 U 端。

```java
public class PartyU
extends KasParty
{
    PQCOtherInfoGenerator.PartyU infoGenerator;

    PartyU(SecureRandom random, byte[] uInfo, byte[] vInfo)
        throws GeneralSecurityException
    {
        super(random);

        infoGenerator = new PQCOtherInfoGenerator.PartyU(
            KyberParameters.kyber512,
            newAlgorithmIdentifier(NISTObjectIdentifiers.id_sha256),
            uInfo, vInfo, random);
    }

    /**
     * 返回用于 NewHope 协商的启动者阶段 1 值。
     * @return 基于 New 钥的字节数组。
     */
    public byte[] doStage1()
    {
        return infoGenerator.getSuppPrivPartA();
    }

    /**
     * 根据 V 方的响应返回 KDF 生成的协商值。
     *
     * @param otherKey V 方的 EC 密钥。
     * @param partBInfo V 方的 NewHope 响应。
     * @return 协商的 KDF 生成密钥。
     */
    public byte[] doAgreement(PublicKey otherKey, byte[] partBInfo)
        throws GeneralSecurityException, IOException
    {
        KeyAgreement agreement = KeyAgreement.getInstance(
                                    "ECCDHwithSHA256KDF", "BC");

        agreement.init(kp.getPrivate(),
            new UserKeyingMaterialSpec(
                    infoGenerator.generate(partBInfo).getEncoded()));

        agreement.doPhase(otherKey, true);

        return agreement.generateSecret();
    }
}
```

你可以看到此此的核心区别在于使用了 `PQCOtherInfoGenerator` 类——在本例中为 `PartyU` 分支。`PQCOtherInfoGenerator.PartyU` 类用于在交换期间提供传递给 V 方的额外“阶段 1”值。`infoGenerator` 对象还用于处理 V 方的响应，以生成包含在 KDF 中的用户密钥材料，从而产生最终的协商值。

### 使用 OtherInfo 的混合加密 - V 端

这里是实现 V 端协商的代码。

```java
public class PartyV
    extends KasParty
{
    PQCOtherInfoGenerator.PartyV infoGenerator;

    PartyV(SecureRandom random, byte[] uInfo, byte[] vInfo)
        throws GeneralSecurityException
    {
        super(random);

        infoGenerator = new PQCOtherInfoGenerator.PartyV(
            KyberParameters.kyber512,
            new AlgorithmIdentifier(NISTObjectIdentifiers.id_sha256),
            uInfo, vInfo, random);
    }

    /**
     * 返回基于 NewHope 的对 U 初始值的响应。
     *
     * @param partAInfo 基于 NewHope 的已约定响应。
     * @return 传递给 U 的响应值。
     */
    public byte[] doStage2(byte[] partAInfo)
    {
        return infoGenerator.getSuppPrivInfoPartB(partAInfo);
    }

    /**
     * 返回基于 U 公钥的 KDF 生成的约定值。
     *
     * @param otherKey U 方的 EC 密钥。
     * @return 从约定中通过 KDF 生成的密钥。
     */
    public byte[] doAgreement(PublicKey otherKey)
        throws GeneralSecurityException, IOException
    {
        KeyAgreement agreement = KeyAgreement.getInstance(
                                                "ECCDHwithSHA256KDF", "BC");

        agreement.init(kp.getPrivate(), new UserKeyingMaterialSpec(
                                infoGenerator.generate().getEncoded()));

        agreement.doPhase(otherKey, true);

        return agreement.generateSecret();
    }
}
```

正如你可能已经预料到的样，该类还使用了一个 `infoGenerator` 对象。这次是从 `PQCtherInfoGenerator.PartyV` 创建的。你会注意到这种情况的不同之处，`infoGenerator` 对象需要来自 U 方通过其 `doStage1()` 方法提供的输入，以便通过 `doStage2()` 方法提供阶段 2 响应。同样，`infoGenerator` 对象也用于生成用户密钥材料规范（user keying material spec），并包含在 KDF 中以生成最终的约定值。在这种情况下，没有内容传递给 `infoGenerator`，因为 U 方阶段 1 数据的处理是在 `doStage2()` 方法中完成的。

### 使用 OtherInfo 的混合加密 - 整合在一起

这是一个两个类结合使用进行约定的示例，其中包含了对 `PQCOtherInfoGenerator` 的使用。

```java
SecureRandom random = new SecureRandom();

byte[] partyUId = Strings.toByteArray("PartyU");

byte[] partyVId = Strings.toByteArray("PartyV");

PartyU partyU = new PartyU(random, partyUId, partyVId);

PartyV partyV = new PartyV(random, partyUId, partyVId);

System.out.println(Hex.toHexString(
    partyU.doAgreement(partyV.getPublic(),
                partyV.doStage2(partyU.doStage1()))));

System.out.println(Hex.toHexString(
    partyV.doAgreement(partyU.getPublic())));
```

为了简洁起见，该示例有些过于简化——在这种情况下，你会预期阶段 1 和阶段 2 的值在约定过程中通过网络进行交换。这意味着，如果你想进行单次约定（one pass agreement），它只能从 V 到 U，因为 U 除了其公钥外，还需要预先发布其阶段数据。尽管如此，额外的努力应该使攻击密钥约定变得困难得多，因为混合到生成共享密钥的 KDF 中的信息部分将包含使用 `Kyber`（在本例中）计算出的约定值。

从代码中可以看出，示例仅以十六进制字符串的形式打印共享密钥。由于该算法使用了随机种子，你可能看不到我们这里呈现的输出值。你应该会看到长度相似的输出，并且由两行相同的行组成。我们最近的运行产生了：

```
cd40dc777d3ce109f84660132ebeb52268c2a5aaa2b17a232c397b6d3b33e94c
cd40dc777d3ce109f84660132ebeb52268c2a5aaa2b17a232c397b6d3b33e94c
```

表明 U 方约定的结果与 V 方约定的结果相同。虽然你会看到不同的值，但你应该看到两行都具有与我们所操作相同的不同值。

## 混合加密 - 发生了什么

能够用标准的相同的术语来描述这个过程是有用的。在这种情况下，我们实际上是在利用 NIST 文档 `SP 800-56A` 中定义的字段。

```java
/**
 * Generate an agreed AES key value of 256 bits in length
 * using both UKM and a T value.
 *
 * @param aPriv Party A's private key.
 * @param bPub Party B's public key.
 * @param tValue T value to create Z || T.
 * @param keyMaterial user keying material to mix with Z || T.
 * @return the generated AES key (256 bits).
 */
public static SecretKey ecGenerateHybridAESKey(
    PrivateKey aPriv, PublicKey bPub, byte[] tValue, byte[] keyMaterial)
    throws GeneralSecurityException
{
    KeyAgreement agreement =
        KeyAgreement.getInstance("ECCDHwithSHA256KDF", "BC");

    agreement.init(aPriv, new HybridValueParameterSpec(
            tValue, new UserKeyingMaterialSpec(keyMaterial)));

    agreement.doPhase(bPub, true);

    return agreement.generateSecret("AES");
}
```



如你所见，`HybridValueParameterSpec` 仅仅是一个包装类，内部 Bouncy Castle KAS 实现会获取 ![T](img/leanpub_equation_697.png) 值，然后剥离 `HybridValueParameterSpec`，将内部的算法参数规范传递给实现内部的 KDF 生成器。

计算 ![T](img/leanpub_equation_698.png) 仍然需要使用另一种机制，无论是 KAS 还是 KEM。下面的示例代码展示了结合 CRYSTALS-Kyber KEM 算法使用 `HybridValueParameterSpec`。

```java
// PartyU

KeyPair ecKpU = EcUtils.generateECKeyPair("P-256");

// PartyV, 在此情况下也有 PQC 密钥对。

KeyPair ecKpV = EcUtils.generateECKeyPair("P-256");

KeyPair qKpV = KyberKEMExample.kyberGenerateKeyPair(
    KyberParameterSpec.kyber512);

// 用户密钥材料 - 共享。

byte[] ukm = Hex.decode("030f136fa7fef90d185655ed1c6d46bacdb820");

SecretKeyWithEncapsulation secEncU = KyberKEMExample.kyberGeneratePartyU(
    qKpV.getPublic());

SecretKey secKeyU = ecGenerateHybridAESKey(
    ecKpU.getPrivate(), ecKpV.getPublic(), secEncU.getEncoded(), ukm);

SecretKeyWithEncapsulation secEncV = KyberKEMExample.kyberGeneratePartyV(
    qKpV.getPrivate(), secEncU.getEncapsulation());

SecretKey secKeyV = ecGenerateHybridAESKey(
    ecKpV.getPrivate(), ecKpU.getPublic(), secEncV.getEncoded(), ukm);

System.out.println("U and V Shared Key equal: " +
    Arrays.areEqual(secKeyU.getEncoded(), secKeyV.getEncoded()));
```

虽然在这种情况下，接收者 ![V](img/leanpub_equation_699.png) 是拥有 PQC 密钥对的人，但这种机制运行的唯一要求是至少有一个有一个可使用的 PQC 公钥。请记住，这意味着协议中可能存在额外的密钥交换，而且 PQC 公钥的尺寸通常比我们习惯的要大一些。例如，如果你在使用 Classic McEliece 寻找 256 位安全性，虽然密文相当小，但公钥大小超过了 1MB！这需要仔细思考。

### 总结

由于量子计算机的发展，公钥加密的重大更新正向我们走。遗憾的是，即使你是一个“量子怀疑论者”，认为自己很快不会看到量子计算机，但现实是针对 RSA 和 EC 等算法的经典攻击也在改进。

为了应对这一变化，NIST 一直在举办后量子密码学（PQC）竞赛，以产生能够防御基于量子计算机攻击的新算法。该竞赛将于 2024 年开始产生实际标准。在此期间，对于签名，有两种量子安全签名算法——LMS 和 XMSS，现在就可以使用（需谨慎使用，因为它们也是有状态的）。竞赛还产生了一些实用的 KEM（密钥封装机制）算法，它们现在可以用于短期加密协议，例如那些使用混合密码学的协议。虽然目前发布的无状态签名算法和 KEM 仍在演进中，但已发布的算法如果你想尝试 PQC 密码学将提供了一个非常好的入门。

是的，书到这里结束了，但这个话题绝非结束。毫无疑问，未来会有更多的算法和见解。感谢阅读，祝我们所有人好运！

## 附录 A：ASN.1 和 Bouncy Castle

大多数涉及密码学的标准都使用 ASN.1（抽象语法表示法），它主要是一种用于描述对象如何编码以传输的语言。算法参数、密钥、签名、已签名和加密的消息，你能想到的都有！很有可能会有一个 ASN.1。

### 基础 ASN.1 语法

幸运的是，我们需要处理的 ASN.1 语法部分相对简单，真正的乐趣在于使用编码规则。我们在这里来看一下基本元素。

#### 注释语法

ASN.1 有两种不同的注释样式：一种用于块注释，由 `/*` 和 `*/` 隔开；另一种是用于单行注释，以 `--` 开始并结束。

与 Java 不同，块注释是可以嵌套的，但由于块语法也是 ASN.1 较新引入的特性，你经常会看到使用多行单行注释来替代本该使用块注释的地方。

#### 对象标识符

ASN.1 对象标识符（OID）的引入是为了构建一个全局唯一的命名空间。OID 由一组由点（‘.’）分隔的数字列表组成，理解其工作原理最好的方式是：OID 的结构遵循一条路径（通常称为“弧”，arc），穿过一个由 3 个主分支扩展的树。对于这 3 个主分支下的任何组织，都存在进一步扩展该树，这允许任何组织或个人分配一个 OID，然后他们可以对其进行扩展，以便为算法、数据类型和算法参数等内容提供唯一标识符，并可以与他人共享。

三个主分支根据组织最初在 ISO/ITU-IT 世界中的所属位置进行分配：数字 `0` 分配给 `ITU-T`，数字 `1` 分配给 `ISO`，数字 `2` 分配给 ISO/ITU-T 联合组织。之后的编号系统是任意的，取决于前一个 OID 所有者的分配，该 OID 代表了新 OID 所分配的分支。

例如，NIST 使用 SHA3-512 的 ECDSA 的 NIST OID 为 `2.16.840.1.101.3.4.3.12`，其长格式描述如下：

```
{ joint-iso-itu-t(2) country(16) us(840) organization(1) gov(101) csor(3)
  nistAlgorithms(4) sigAlgs(3) id-ecdsa-with-sha3-512(12) }
```

这意味着 NIST 的计算机安全对象注册中心（CSOR）在联合 ISO/ITU-T (2) 美国国家 (16) 政府 (101) 组织分支下下被分配了一个 OID。随后，CSOR 为 NIST 算法 (4) 分配了进一步的分支，并带有签名算法 (3) 的子分支。最后，我们得到了实际签名算法类型带 SHA3-512 的 ECDSA (12)。

通常情况下，如果某个特定算法已经分配了 OID，最佳实践是始终使用已分配的那个。偶尔，由于分支是基于组织而非算法的，你会发现有时某个算法会与多个 OID 关联。由于这可能会导致处理过程中出现意外故障，因此值得记住这一点。

### 模块结构

ASN.1 模块的基本结构如下：

```
module_name { object_identifier }
DEFINITIONS tagging TAGS ::=
BEGIN
EXPORTS export_list ;
IMPORTS import_list ;
body
END
```

其中，`module_name` 和 `object_identifier` 用于标识正在定义的模块，其预期是指定的 OID 是唯一的。`tagging` 字段定义了模块中使用的标记类型。`body` 部分包含模块中定义的结构局部定义。

例如，RFC 5280 (PKIX) 中 A.1 定义定义的模块开始于：

```
PKIX1Explicit88 { iso(1) identified-organization(3) dod(6) internet(1)
  security(5) mechanisms(5) pkix(7) id-mod(0) id-pkix1-explicit(18) }
DEFINITIONS EXPLICIT TAGS ::=
BEGIN
-- EXPORTS ALL --
-- IMPORTS NONE --
```

因此，模块名为 `PKIX1Explict88`，其唯一标识符为 `1.3.6.1.5.5.7.0.18`。

标记字段为 `EXPLICIT`，默认情况下，模块中的任何标记项都是 `EXPLICIT` 标记，除非另有说明。另一种是 `IMPLICIT`，我们稍后会看到这二者之间的区别。

在这种情况下，缺少了 `EXPORTS` 关键字（它在注释中），这意味着模块中的任何内容都可以导出到另一个模块。如果你看到发现 `export_list` 缺失（即头部只有 `EXPORTS ;`），则无法从该模块中导出任何内容。

`IMPORTS` 关键字也缺失了，正如注释所示，这意味着不需要任何导入，因此你可能需要处理的所有内容已经描述在模块中了。如果你继续查看 RFC 5280 后续部分 A.2 中的模块 `PKIXImplicit88`，你会看到一个导入语句的示例：

```
IMPORTS
  id-pe, id-kp, id-qt-unotice, id-qt-cps,
  -- 如果支持 "new" 类型，则删除下行 --
  BMPString, UTF8String,  -- 结束 "new" 类型 --
  ORAddress, Name, RelativeDistinguishedName,
  CertificateSerialNumber, Attribute, DirectoryString
  FROM PKIX1Explicit88 { iso(1) identified-organization(3)
    dod(6) internet(1) security(5) mechanisms(5) pkix(7)
    id-mod(0) id-pkix1-explicit(18) };
```

在这种情况下，`PKIXImplicit88` 模块正在从单个模块 `PKIXExplicit88` 模块中导入一个定义列表，该模块也定义在 RFC 5280 中。

### 类型

ASN.1 类型属于以下三类之一：简单类型、字符串类型和结构化类型。字符串类型进一步分为两类。结构化类型表示容器类型和无序集。这些都定义在 `org.bouncycastle` 中。

#### 简单类型

ASN.1 中的简单类型包括：

- `BOOLEAN` 表示真或假值。由 `ASN1Boolean` 表示，带有 `ASN1Boolean.TRUE` 和 `ASN1Boolean.FALSE` 两个常量。
- `ENUMERATED` 是 `INTEGER` 的特殊情况，传统上是一个限制集。由 `ASN1Enumerated` 表示。
- `INTEGER` 可表示任意大小的整数。注意：这意味着它们是有符号的且只有一种编码（补码）。INTEGER 由 `ASN1Integer` 表示。
- `NULL` 一个显式空值。不要将其与 Java 的 `null` 混淆，Java 的 `null` 更接近 ASN.1 的缺失概念，即不存在编码。NULL 有一个真实的编码来表示它。由 `ASN1Null` 和旧版的 `DERNull.INSTANCE` 表示。
- `OBJECT IDENTIFIER` 我们在对象标识符章节介绍过这种类型。它由 `ASN1ObjectIdentifier` 表示。
- `UTCTime` 用于定义两位年份的“协调世界时间”。通常两位年份被解释为 1950 年到 2049 年，但显然某些系统使用不同的窗口，因此检查并进行转换是值得的。UTCTime 的最低分辨率是秒。UTCTime 由 `ASN1UTCTime` 和 `DERUTCTime` 表示。
- `GeneralizedTime` 具有四季年份，可以表示任意精度的秒。UTCTime 由 `ASN1GeneralizedTime` 和 `DERGeneralizedTime` 表示。

大多数原始类型只有一种编码方式，因此无论你使用 DER 还是更宽松的 BER，它们总是以相同的方式编码。这两个例外是 `UTCTime` 和 `GeneralizedTime`。这两种原始类型都将时间编码为 ASCII 字符串。如果你始终尝试对这些类型遵循 DER，Bouncy Castle 通常是这么做的的，因为在可能包含签名的数据中对原始类型进行编码非常简单，如果签名验证者没有正确地强制执行编码，在验证时可能会出现意外故障。

#### 字符串类型

字符串类型再次分为两类：位字符串类型和字符字符串类型。

##### 位字符串类型

有两种位字符串类型：

```
BIT STRING
```



# 位字符串 (BIT STRING)

`BIT STRING` 允许存储任意长度的位串。它们被编码为两个部分：第一部分是填充位数，随后是组成实际位串的字节串（octets）。在 DER 编码中，填充位应全部为零。`BIT STRING` 由 `ASN1BitString` 和 `DERBitString` 表示。

# 字节字符串 (OCTET STRING)

`OCTET STRING` 允许存储任意长度的字节串（对于更现代的读者来说，就是一个字节数组）。`OCTET STRING` 由 `ASN1OctetString`、`BEROctetString` 和 `DEROctetString` 表示。还有用于处理 BER OCTET STRING 的流式类 - `BEROctetStringGenerator` 和 `BEROctetStringParser`。

## 字符串类型 (Character String Types)

ASN.1 支持多种字符串类型，其中某些类型可能会让本书更“资深”的读者产生怀旧之泪（也许是想起某些恐怖记忆而尖叫）。这些字符串类型中的某些代表了已经废弃的字符集，因此你很少甚至永远看不到它们（`VideotexString` 和 `Teletex` 是这两个最好的例子），而其他如 `PrintableString`、`IA5String`、`BMPString` 和 `UTF8String` 可能是常用的。与位字符串类型一样，所有这些类型允许存储任意长度的字符串，但在 Bouncy Castle 的工作中，我们只发现过需要 DER 和直接长度编码的情况。

字符串类型的完整列表及其代表的含义如下：

### BMPString

`BMPString` 由 `DERBMPString` 类表示。它的名称源自“基本多语言平面”（Basic Multilingual Plane）——这是一个包含所有与“生存语言”相关的字符的结构。该字符集由 ISO 10646 表示，与 Unicode 表示的字符集相同。

### GeneralString (通用字符串)

`GeneralString` 由 `DERGeneralString` 类表示。它可以包含 ISO 2375 描述的国际编码字符集注册表中描述的任何字符，包括控制字符。

### GraphicString (图形字符串)

`GraphicString` 由 `DERGraphicString` 类表示。这种字符串类型派自与 `GeneralString` 字符集，但不包含控制字符。只允许打印字符。

### IA5String

`IA5String` 由来自“国际字母 5”（International Alphabet 5）的字符组成，这是一个旧的 ITU-T 建议。如今它们被认为涵盖了整个 ASCII 字符集。该类型由 `DERIA5String` 表示。

### NumericString (数字字符串)

`NumericString` 包含数字 0 到 9 和空格字符。它由 `DERNumericString` 表示。

### PrintableString (打印字符串)

`PrintableString` 由 `DERPrintableString` 表示。`PrintableString` 的字符集取自 ASCII 的子集：字母“A”到“Z”、“a”到“z”、“0”到“9”，以及额外的字符“ ”、“'”、“(”、“)”、“+”、“-”、“.”、“:”、“=”、“?”、“/” 和 “,”。

### TeletexString

最初名为 `DERT61String` 并由其表示。它可能很难正确解释，因为它虽然是一个 8 位字符类型，但支持通过使用 ASCII `ESC`（转义字符）开头的字符序列来更改字符集。

### UniversalString (通用字符串)

`UniversalString` 由 `DERUniversalString` 表示。这种字符串类型是为了国际化而添加的，但在所有情况下使用了 32 位的字符大小。默认情况下，Bouncy Castle 将这些字符串转换为显示字符编码的 HEX 字符串。

### UTF8String

`UTF8String` 代表编码“通用转换格式，8 位”（Universal Transformation Format, 8 bit），是全范围国际化的推荐字符串类型。它由 `DERUTF8String` 表示，现在被广泛使用。

### VideotexString (视频文字字符串)

顾名思义，`VideotexString` 设计用于视频文字系统，并适应可以使用控制代码构建简单图像的 8 位字符。

### VisibleString (可见字符串)

`VisibleString` 由 `DERVisibleString` 表示。这种类型最初旨在包含来自 ISO 646 的字符，但从 1994 年以来，它被解释为包含不带控制字符的纯 ASCII。

## 容器类型 (Container Types)

ASN.1 有两种容器类型 - `SET` 和 `SEQUENCE`。这些类型在 BC ASN.1 API 中通过顶层的 `ASN1Set` 和 `ASN1Sequence` 类支持。

`ASN1Set` 和 `ASN1Sequence` 类都是抽象的，并具有暗示特定编码风格的实现类。ASN.1 `SEQUENCE` 结构是有序的，因此编码风格的选择不会影响编码中元素的顺序。另一方面，ASN.1 `SET` 结构是无序的，但为了满足 DER 的要求，它们按照编码的数值对元素进行排序输出（该值通过对元素进行编码，然后在添加足够的尾零以使每个编码长度相同之后转换为无符号整数计算）。

## CHOICE 类型 (The CHOICE Type)

`CHOICE` 是一种特殊类型，指示 ASN.1 字段或变量将是一组可能的 ASN.1 类型或结构中的一种。在 Java 中没有真正的对应物，但如果你将其视为 C 或 Pascal 中的联合体（union），那么就很接近了。

Bouncy Castle 提供了一个标记接口 `ASN1Choice`，它可以实现在表示选择类型的 ASN.1 对象上。在可能的情况下应该使用此标记接口，因为它有助于提醒 Bouncy Castle 编码器对 `CHOICE` 强制执行正确的编码规则（下文将有更多介绍）。

## 编码规则 (Encoding Rules)

ASN.1 支持多种不同的编码方式，从精心设计的、无歧义且尺寸最小的二进制格式到使用 XML 的通用编码。从我们 Bouncy Castle 目前的工作来看，有三组编码规则最为相关：基本编码规则 (BER)、区分编码规则 (DER) 以及较小的规范编码规则 (CER)。

### 基本编码规则 (Basic Encoding Rules)

ASN.1 编码系统的核心围绕基本编码规则 (BER) 构建。BER 编码遵循标记-长度-值（TLV）约定。它使用 `tag` 标识类型，随后给出内容长度的值，然后是相应长度的字节串描述内容。DER 和 CER 都是 BER 的子集。

BER 编码提供了三种编码 ASN.1 结构或原始的方法：

#### 原始确定长度

在这种情况下，整个原始在单个块中描述 - 类型标记后面的长度和数据告诉了你关于编码结构中大小和数据的所有信息。

#### 构造确定长度

构造确定长度既用于表示包含多个原始（可能也是构造的）的 ASN.1 结构，也用于表示由一系列确定长度原始编码聚合成的原始。对于其中一种情况，你只有通过读取组成构造编码的所有原始编码，才能确定数据的真实大小以及组成它的字节串。

#### 构造不定长度

构造不定长度的编码也由其他编码组成 - 这些编码本身可能是不定长度的。它通过长度字节 `0x80` 进行指示，并由两个值为 `0x00` 的字节组成的内容结束标记终止。

### 标记 (Tagging)

作为 TLV 格式，BER 有一套用于常用原始和结构类型的标准预定义标签。BER 还允许在对 `SEQUENCE` 等容器类型的定义可能产生歧义的情况下定义你自己的标签值。

不过，定义自己的标签值还有一些转折。

第一个转折在于，ASN.1 对象可以被标记为 `EXPLICIT`（显式），这意味着你的标记值和对象的原始标记值都包含在编码中；或者 ASN.1 对象可以被标记为 `IMPLICIT`（隐式），这意味着你的标记值在编码中替换了对象的原始标记值。当然，由于原始标记值丢失了，你可能会问，如果你不知道原始标记值是什么，而且手头没有文档告诉你它本应该是什么，你该如何正确解释编码？遗憾的是，你无法判断。这在结构化类型中尤为重要，因为一个显式标记的原始类型生成的编码，与一个包含单个原始类型的隐式标记 `SET` 或 `SEQUENCE` 所生成的编码是相同的。

Bouncy Castle ASN.1 库中的所有标准 API 类型都支持静态的 `getInstance()` 方法，该方法接收一个 `ASN1TaggedObject` 和一个指示隐式或显式标记的 `boolean` 值。由于 `IMPLICIT` 和结构化类型之间存在歧义，在解析类型为 `ASN1TaggedObject` 的对象时使用这些方法非常重要，并确保针对所使用的标记类型使用了正确的 `boolean` 值。

第二个转折在于当 ASN.1 对象是 `CHOICE` 时。对于 `CHOICE` 类型，你无法承受丢失任何与 `CHOICE` 值相关的标记，因为它是你判断 `CHOICE` 值真正代表什么的唯一线索。

Bouncy Castle 提供了一个标记接口 `ASN1Choice`，该接口可以实现在 ASN.1 对象上，以提醒 Bouncy Castle 编码器执行正确的编码规则。我们建议在定义表示 ASN.1 `CHOICE` 的对象时使用它。

## 区分编码规则 (Distinguished Encoding Rules)

由于提供了结构化原始类型、无序集合等规定，给定的 ASN.1 结构可能有几种编码方式。区分编码规则（DER）旨在确保相同的 ASN.1 数据始终产生相同的编码。

这对于签名或经过 MAC（消息认证码）处理的数据尤为重要，因为验证签名 ASN.1 数据的能力依赖于验证方能够准确地重构被签名数据的编码。

为了确保这一点始终成立，`DER` 在 `BER` 的基础上增加了以下限制：

- 仅允许确定长度编码。
- 只有结构化类型 `SEQUENCE`、`SET`、隐式标记的 `SEQUENCE` 或 `SET` 以及显式标记的对象可以使用构造的确定长度。
- 长度编码必须始终以最少字节数进行编码（不允许有前导零）。
- 设置为 `DEFAULT` 值的字段不包含在编码中。
- `SET` 中包含的对象在编码前会根据调整后的编码值进行排序（必要时将补零以使所有编码长度相同）。

注意：最后两项限制也适用于 `CER`。

## 字节编码规则 (Octet Encoding Rules)

2014 年，引入了一套新的编码规则，这些规则现在开始产生影响，主要是在那些认为最终编码大小很重要的标准中。这套新规则——字节编码规则（OER）定义在 `X.696` 中，其规则与 `BER` 和 `DER` 并行工作。基础规则是基础字节编码规则（`BOER`），而与 `DER` 等效的规则是规范化字节编码规则（`COER`）。所有的 `OER` 类型都是字节对齐的，但并非所有类型都包含长度标记，因为当 ASN.1 类型定义已经提供了确定长度的能力时，长度标记会被省略。

`OER` 扩展了 ASN.1 类型列表，包括不同位长度的固定长度无符号整数（`UInt`）以及固定长度的有符号整数（`Int`）。字符串类型也可以是固定长度，例如 `OCTET STRING` 类型可以是固定长度，在这种情况下 `OCTET STRING` 直接编码为其值字节；或者它们可以是变长的，在这种情况下在开头包含标准的长度标记。最后，当 `SEQUENCE` 包含可选项目时，序列开头编码的是存在性位图（presence bitmap）而不是长度，用于标记哪些可选字段是存在的。

Bouncy Castle 目前不支持 `OER`，但请关注这里，我们确信它就会到来！

## 其他编码规则

除了“最近”引入的 `OER` 规则外，ASN.1 还有其他可用的编码规则。在这工作中最可能遇到的是规范化编码规则（`CER`），它也是 `BER` 的子集，但它对不定长度编码中组件的大小施加了限制。通常情况下，意识到 `CER` 是值得的，因为它让你对人们可能实施的限制有一个良好的了解。在 ASN.1 中，实际上在 Java 中，技术上可以构造一个由长度为 $2^{31}$ 字节的字符串组成的有效不定长度构造 `OCTET STRING`——尽管你可能很难找到能解析这种产物的人。

最后两种编码（编写本文时）是打包编码规则（`PER`）和 XML 编码规则（`XER`）。如果你对这些更多信息感兴趣，请参见相关标准 `X.961` 和 `X.963`。

## 基础指南

在面向对象的语言中使用像 ASN.1 这样的协议层时，困难之一在于，有时不清楚何时处理 ASN.1 结构是安全的，例如作为对象 `org.bouncycastle.asn1.x509.AlgorithmIdentifier` 处理，还是作为其原始组合中的结构 `SEQUENCE` 处理。强制转换（Casting）在这种情况下并不好用——如果以意外的方式使用方法，很容易导致 `ClassCastException`。

在 Bouncy Castle 中，这个问题通过使用静态 `getInstance()` 方法来解决。例如，`AlgorithmIdentifier.getInstance()` 可以接收 `AlgorithmIdentifier` 对象或表示 `AlgorithmIdentifier` 的 `ASN1Sequence` 对象，并始终返回 `AlgorithmIdentifier`，如果传入了空值则返回 `null`。同样，`ASN1Sequence.getInstance()` 可以接收 `AlgorithmIdentifier` 对象或 `ASN1Sequence` 对象，并始终返回 `ASN1Sequence`，如果传入了空值则返回 `null`。

## 定义你自己的对象

通常，如果你正在定义一个基于 ASN.1 的对象，你应该定义一个继承自 `org.bouncycastle.asn1.ASN1Object` 的类。这将提供 `equals()` 和 `hashCode()` 定义，并要求在你的扩展类中定义 `toASN1Primitive()` 方法。之后，如果你想遵循现有模式（我们强烈建议），你应该定义一个静态 `getInstance()` 方法，该方法能够接收类类型、`toASN1Primitive()` 返回的内容或 `null`。一旦你完成了这些，类的其余部分几乎是自动生成的——构造函数将根据组成对象的类型产生。

接下来的示例代码提供了一个用于以下 ASN.1 结构的类定义：

```
SimpleStructure ::= SEQUENCE {

    version INTEGER DEFAULT 0,

    created GeneralizedTime,

    data OCTET STRING,

    comment [0] UTF8String OPTIONAL

}
```

该类完整的完整的，了两页纸。请先查看代码，然后阅读随后的注释。

```java

  /**

  * SimpleStructure 的实现 - 一个 ASN.1 对象示例（标记为

  * IMPLICIT）。

  * <pre>

  *     SimpleStructure ::= SEQUENCE {

  *         version INTEGER DEFAULT 0,

  *         created GeneralizedTime,

  *         data OCTET STRING,

  *         comment [0] UTF8String OPTIONAL

  *     }

  * </pre>

  */

 public class SimpleStructure

    extends ASN1Object

{

    private final BigInteger version;

    private final Date created;

    private final byte[] data;

    private String comment;

    /**

     * 将传入的对象转换或强制转换为 SimpleStructure。

     *

     * @param obj 感兴趣的对象。

     * @return 一个 SimpleStructure 

     */

    public static SimpleStructure getInstance(

        Object  obj)

    {

        if (obj instanceof SimpleStructure)

        {

            return (SimpleStructure)obj;

        }

        else if (obj != null)

        {

            return new SimpleStructure(ASN1Sequence.getInstance(obj));

        }

        return null;

    }

    /**

     * 创建一个带有默认版本的结构。

     *

     * @param created 创建日期。

     * @param data 要包含的编码数据。

     */

    public SimpleStructure(Date created, byte[] data)

    {

        this(0, created, data, null);

    }

    /**

     * 创建一个带有默认版本和可选注释的结构。

     *

     * @param created 创建日期。

     * @param data 要包含的编码数据。

     * @param comment 要使用的注释。

     */
```



## SimpleStructure 类实现

```java
public SimpleStructure(Date created, byte[] data, String comment)
{
    this(0, created, data, comment);
}

/**
 * 创建一个带有特定版本和可选注释的结构。
 *
 * @param version 要使用的版本号。
 * @param created 创建日期。
 * @param data 要包含的编码数据。
 * @param comment 要使用的注释。
 */
public SimpleStructure(int version, Date created,
                       byte[] data, String comment)
{
    this.version = BigInteger.valueOf(version);
    this.created = new Date(created.getTime());
    this.data = Arrays.clone(data);
    if (comment != null)
    {
        this.comment = comment;
    }
    else
    {
        this.comment = null;
    }
}

// 注意：序列的私有构造函数 - 我们希望用户养成
// 使用 getInstance() 的习惯。这样安全！
private SimpleStructure(ASN1Sequence seq)
{
    int index = 0;
    if (seq.getObjectAt(0) instanceof ASN1Integer)
    {
        this.version = ASN1Integer.getInstance(
                              seq.getObjectAt(0)).getValue();
        index++;
    }
    else
    {
        this.version = BigInteger.ZERO;
    }

    try
    {
        this.created = ASN1GeneralizedTime.getInstance(
                             seq.getObjectAt(index++)).getDate();
    }
    catch (ParseException e)
    {
        throw new IllegalArgumentException(
            "解析 created 异常：" + e.getMessage(), e);
    }

    this.data = Arrays.clone(
        ASN1OctetString.getInstance(seq.getObjectAt(index++)).getOctets());

    for (int i = index; i != seq.size(); i++)
    {
        ASN1TaggedObject t = ASN1TaggedObject.getInstance(
                           seq.getObjectAt(index++));
        if (t.getTag() == 0)
        {
            this.comment = UTF8String.getInstance(t).getString();
        }
    }
}

public BigInteger getVersion() {
    return version;
}

public Date getCreated() {
    return created;
}

public byte[] getData() {
    return data;
}

public String getComment() {
    return comment;
}

/**
 * 生成该对象的 DER 表示形式。
 * @return 一个 ASN1Primitive
 */
@Override
public ASN1Primitive toASN1Primitive()
{
    ASN1PrintableVector v = new ASN1PrintableVector();
    if (!version.equals(BigInteger.ZERO)) {
        v.add(new DERInteger(version));
    }
    v.add(new DERGeneralizedTime(created));
    v.add(new DEROctetString(data));
    if (comment != null) {
        v.add(new DERTaggedObject(false, 0, new DERUTF8String(comment)));
    }
    return new DERSequence(v);
}
```

可以看出，`SimpleStructure` 遵循标准模式。它扩展了 `ASN1Object`，提供了一个 `getInstance()` 方法，并且考虑了 DER 规则（只有当版本不是默认值时才进行编码）。`getInstance()` 方法能够将其大部分工作外包给 `ASN1Sequence.getInstance()`，而接收 `ASN1Sequence` 的构造函数被标记为私有，因此任何使用它的尝试都必须通过 `getInstance()`。

另一点注意的是，该类是不可变的。这里需要注意的是，与几乎所有的 ASN.1 对象不同，`ASN1OctetString` 不是不可变的——这主要是出于（唉）性能考虑。这就是为什么对 `getOctets()` 方法返回的 `byte[]` 调用了 `Arrays.clone()` 方法的原因。

## 附录：Bouncy Castle Kotlin API

我们经常被问是否有方法可以使用 Bouncy Castle 来编写脚本，或者至少是接近对应的东西。Bouncy Castle Kotlin API 利用了 Kotlin 的领域特定语言 (DSL) 能力，提供了生成证书和证书请求等内容的支持，并为 `java.io.OutputStreamWriter` 提供额外的方法来生成 PEM 文件。

### 关于包的说明

虽然使用 `org.bouncycastle` 很有吸引力，但为了不进一步污染互联网，我们最终使用 `org.bouncycastle.kcrypto` 作为 Kotlin 特有加密类的父包，并使用 `org.bouncycastle.kutil` 作为通用工具类的父包。

Kotlin API 可以在 [`github.com/bcgit/bc-kotlin`](https://github.com/bcgit/bc-kotlin) 获取。我们在这里查看两个“经典”的用法示例，但发行版中也包含一个示例目录，其中展示了其他用例。

### 生成 PKCS#10 证书请求

以下 Kotlin DSL 创建了一个 RSA 密钥对，并据此生成了一个 PKCS#10 证书请求。请求中使用的签名等同于 JCA 在你请求 `SHA256withRSA` 时提供的签名。在末尾，脚本将私钥和 PKCS#10 请求都写为 PEM 文件。

```kotlin
fun main() {
    using(new BouncyCastleProvider())
    var kp = signingKeyPair {
        rsa {
            keySize = 2048
        }
    }
    val name = x500Name {
        rdn(BCStyle.C, "AU")
        rdn(BCStyle.O, "The Legion of the Bouncy Castle")
        rdn(BCStyle.L, "Melbourne")
        rdn(BCStyle.CN, "Eric H. Echidna")
        rdn(BCStyle.EmailAddress, "feedback-crypto@bouncycastle.org")
    }
    val extensions = extensions {
        critical(extension {
            extOid = Extension.keyUsage
            extValue = KeyUsage(KeyUsage.keyCertSign or KeyUsage.cRLSign)
        })
    }
    var pkcs10 = pkcs10Request {
        subject = name
        subjectKey = kp.verificationKey
        attributes = attributes {
              attribute {
                  attrType = PKCSObjectIdentifiers.pkcs_9_at_extensionRequest
                  attrValue = extensions
              }
        }
        signature {
            PKCS1v1dot5 with sha256 using kp.signingKey
        }
    }
    OutputStreamWriter(System.out).writePEMObject(kp.signingKey)
    OutputStreamWriter(System.out).writePEMObject(pkcs10)
}
```

注意证书请求中 `attributes` 块的使用。虽然该块是可选的，但在上面的示例中，我们使用它来请求 CA 在其颁发的证书中包含 `KeyUsage` 扩展。你可以在第 12 章找到更多关于 `PKCS#10` 请求的细节。

关于该脚本的另一个有趣点是，签名算法不是通过字符串指定的。Kotlin API 尝试充分利用 Kotlin 语言特性以确保所有内容在编译时通过检查。结果是，如果你需要禁用某种算法并确保已经禁用，你只需要移除 BC Kotlin API 对该算法的定义，任何使用该禁用算法的脚本都将无法编译。

## 生成证书

```kotlin
fun main() {
    using(new BouncyCastleProvider())
    var expDate = Date(System.currentTimeMillis() + 365L * 24 * 60 * 60 * 1000)
    var caKp = signingKeyPair {
        rsa {
            keySize = 2048
        }
    }
    val caName = x500Name {
        rdn(BCStyle.C, "AU")
        rdn(BCStyle.O, "The Legion of the Bouncy Castle")
        rdn(BCStyle.L, "Melbourne")
        rdn(BCStyle.CN, "Eric's CA")
    }
    var caExtensions = extensions {
        critical(extension {
            extOid = Extension.basicConstraints
            extValue = BasicConstraints(true)
        })
        critical(extension {
            extOid = Extension.keyUsage
            extValue = KeyUsage(KeyUsage.cRLSign or KeyUsage.keyCertSign)
        })
        critical(subjectKeyIdentifierExtension {
            subjectKey = caKp.verificationKey
        })
    }
    var caCert = certificate {
        issuer = caName
        serialNumber = BigInteger.valueOf(1)
        notAfter = expDate
        subject = caName
        subjectPublicKey = caKp.verificationKey
        extensions = caExtensions
        signature {
            PKCS1v1dot5 with sha256 using caKp.signingKey
        }
    }
    OutputStreamWriter(System.out).writePEMObject(caKp.signingKey)
    OutputStreamWriter(System.out).writePEMObject(caCert)
}
```

与 `PKCS#10` 示例一样，目标证书将使用 `SHA256withRSA` 进行签名。在差异方面，证书设置中的字段显然不同，但 API 的用感仍然是一样的。

当然，你可能想用密码加密新的私钥。`OutputStreamWriter` 的 `writePEMObject()` 重写方法可以识别 PEM 编码的一范围对象。因此，另一种保存私钥的方法（显然考虑到密码，这并不是最好的方法）如下：

```kotlin
var encCaKey = encryptedPrivateKey {
    privateKey = caKp.signingKey
    encryption {
        AES using scrypt {
            saltLength = 16
            cost = 16384
            blockSize = 8
            parallelization = 1
            keySize = 256
        } with "Test".toCharArray()
    }
}
OutputStreamWriter(System.out).writePEMObject(encCaKey)
```

这段代码片段将使用 `AES` 密钥加密私钥，并使用 `scrypt` 算法从密码派生密钥。结果是你应该得到一个带有 PEM 头的 blob：

```
-----BEGIN ENCRYPTED PRIVATE KEY-----
```

而不是之前通用 RSA 密钥的格式：

```
-----BEGIN RSA PRIVATE KEY-----
```



这些示例仅涉及了使用 Kotlin API 可以进行的一些操作。如果你好奇还能做什么，不要忘记查看 BC 分发中的示例。

## 附录：Bouncy Castle 提供的算法

### 分组算法 (Block)

| 算法 | 密钥大小 | 通用 | FIPS |
| --- | --- | --- | --- |
| AES | 128, 192, 256 | X | X |
| Blowfish | 40 .. 448 | X | X |
| Camellia | 128, 192, 256 | X | X |
| CAST-5 | 0 .. 128 | X | X |
| CAST-6 | 0 .. 256 | X | X |
| DES | 56 | X | X |
| DSTU7624 | 128, 256, 512 | X | X |
| GOST28147 | 32 | X | X |
| GOST3412-215 | 256 | X | X |
| IDEA | 128 | X | X |
| RC2 | 0 .. 1024 | X | X |
| Rijndael | 0 .. 256 | X | X |
| SEED | 128 | X | X |
| Serpent | 128, 192, 256 | X | X |
| Shacal | 128 | X | X |
| SM4 | 128 | X | X |
| TEA | 128 | X | X |
| Threefish | 128, 192, 256 | X | X |
| Twofish | 128, 192, 256 | X | X |

### 流加密算法 (Stream)

| 算法 | 密钥大小 | 通用 | FIPS |
| --- | --- | --- | --- |
| ARC4 | 40 .. 2048 | X | X |
| HC128 | 128 | X | X |
| HC256 | 256 | X | X |
| ChaCha | 128, 256 | X | X |
| Salsa20 | 128, 256 | X | X |
| XSalsa20 | 256 | X | X |
| ISAAC | 32 .. 8192 | X | X |
| VMPC | 8 .. 6144 | X | X |
| Grain-V1 | 80 | X | X |
| Grain-128 | 128 | X | X |

### 密钥交换算法 (Key Agreement)

| 算法 | 通用 | FIPS |
| --- | --- | --- |
| DH | X | X |
| DHU | X | |
| MQV | X | X |
| ECDH | X | X |
| ECCDH | X | X |
| ECCDHU | X | |
| ECMQV | X | X |
| XDH | X | X |

### 消息认证码 (MACs)

| 算法 | 输出大小 | 通用 | FIPS |
| --- | --- | --- | --- |
| CBC-MAC | blocksize/2 unless specified | X | X |
| CFB-MAC | blocksize/2, in CFB 8 mode, unless specified | X | X |
| CMAC | 24 to cipher block size | X | X |
| GMAC | 32 to 128 bits | X | X |
| GOST28147-MAC | 32 bits | X | X |
| ISO9797Alg3-MAC | multiple of 8 bits up to underlying cipher size | X | |
| HMac | digest length | X | X |
| DSTU7564 | 256, 384, 512 bits | X | |
| DSTU7624 | 128, 256, 512 bits | X | |
| Poly1305 | 128 bits | X | |
| SkeinMac | any byte length | X | |
| SipHash | 64 bits | X | |

### 消息摘要和可扩展输出函数 (XOFs)

| 算法 | 输出大小 | 通用 | FIPS |
| --- | --- | --- | --- |
| Blake2s | 128, 160, 224, 256 | X | |
| Blake2b | 224, 256, 384, 512 | X | |

### 公钥算法 (Public Key)

| 算法 | 通用 | FIPS |
| --- | --- | --- |
| RSA | X | X |
| ElGamal | X | X |

### 密钥封装机制 (KEMS)

| 算法 | 通用 | FIPS |
| --- | --- | --- |
| BIKE | X | |
| Classic McEliece | X | |
| FrodoEM | X | |
| HQC | X | |
| Kyber | X | |
| NTRU | X | |
| RSA-KTS-KEM | X | |
| SABER | X | |

### 消息摘要和可扩展输出函数 (XOFs) 补充

| 算法 | 输出大小 | 通用 | FIPS |
| :--- | :--- | :--- | :--- |
| `Blake3` | 224, 256, 384, 512 | X | |
| `cSHAKE` | 任意 | X | X |
| `DSTU-7564` | 256, 384, 512 | X | |
| `GOST-3411` | 256 | X | X |
| `GOST-3411-2012-256` | 256 | X | |
| `GOST-3411-2012-512` | 512 | X | |
| `Haraka` | 256, 512 | X | |
| `Kangaroo` | 任意 | X | |
| `Keccak` | 224, 256, 288, 384, 512 | X | |
| `KMAC` | 任意 | X | X |
| `MD2` | 128 | X | |
| `MD4` | 128 | X | |
| `MD5` | 128 | X | X |
| `ParallelHash` | 任意 | X | X |
| `RipeMD-128` | 128 | X | X |
| `RipeMD-160` | 160 | X | X |
| `RipeMD-256` | 256 | X | X |
| `RipeMD-320` | 320 | X | X |
| `SHA-1` | 160 | X | X |
| `SHA-224` | 224 | X | X |
| `SHA-256` | 256 | X | X |
| `SHA-384` | 384 | X | X |
| `SHA-512` | 512 | X | X |
| `SHA-3` | 224, 256, 384, 512 | X | X |
| `SHAKE-128` | 任意 | X | X |
| `SHAKE-256` | 任意 | X | X |
| `Skein` | 任意 | X | |
| `SM3` | 256 | X | |
| `TupleHash` | 任意 | X | X |
| `Tiger` | 192 | X | X |
| `Whirlpool` | 512 | X | X |

## 签名算法

| 算法 | BC General | BC FIPS |
| :--- | :--- | :--- |
| `Dilithium` | X | |
| `DSA` | X | X |
| `ECDSA` | X | X |
| `EdDSA` | X | X |
| `Falcon` | X | |
| `GeMSS` | X | |
| `LMS` | X | X |
| `Picnic` | X | |
| `Rainbow` | X | |
| `RSA` | X | X |
| `RSA-PSS` | X | X |
| `SPHINCS+` | X | |
| `XMSS` | X | |

## 缩写与定义

| 缩写 | 定义 |
| :--- | :--- |
| `AES` | 高级加密标准 (Advanced Encryption Standard) |
| `ASN.1` | 抽象语法表示法 1 (Abstract Syntax Notation 1) |
| `ACVP` | 自动密码验证协议 (Automated Cryptographic Validation Protocol) |
| `CAVP` | 密码算法验证程序 (Cryptographic Algorithm Validation Program) |
| `CBC` | 密码块链接 (Cipher-Block Chaining) |
| `CCM` | 带有 CBC-MAC 的计数器 (Counter with CBC-MAC) |
| `CFB` | 密码反馈模式 (Cipher Feedback Mode) |
| `CMAC` | 基于密码的消息认证码 (Cipher-based Message Authentication Code) |
| `CMVP` | 密码模块验证程序 (Cryptographic Module Validation Program) |
| `CRL` | 证书吊销列表 (Certificate Revocation List) |
| `CS` | 密文窃取 (Cipher text Stealing) |
| `CTS` | 密文窃取 (Cipher Text Stealing) |
| `CTR` | 计数模式 (CounTeR-mode) |
| `DES` | 数据加密标准 (Data Encryption Standard) |
| `DSA` | 数字签名算法 (Digital Signature Algorithm) |
| `DRBG` | 确定性随机数生成器 (Deterministic Random Bit Generator) |
| `EC` | 椭圆曲线 (Elliptic Curve) |
| `ECB` | 电子密码本 (Electronic CodeBook) |
| `ECC` | 椭圆曲线密码学 (Elliptic Curve Cryptography) |
| `ECDSA` | 椭圆曲线数字签名 (Elliptic Curve Digital Signature Authority) |
| `FIPS` | 联邦信息处理标准 (Federal Information Processing Standards) |
| `GCM` | 伽罗斯计数模式 (Galois/Counter Mode) |
| `GOST` | 苏维联邦共和国国家标准 (Gosudarstvennyi Standard Soyuza SSR) |
| `HMAC` | 密钥哈希消息认证码 (key-Hashed Message Authentication Code) |
| `HSM` | 硬件安全模块 (Hardware Security Module) |
| `IV` | 初始化向量 (Initialization Vector) |
| `JCA` | Java 密码体系 (Java Cryptography Architecture) |
| `JCE` | Java 密码扩展 (Java Cryptography Extension) |
| `JRE` | Java 运行环境 (Java Runtime Environment) |
| `JVM` | Java 虚拟机 (Java Virtual Machine) |
| `KAS` | 密钥协商方案 (Key Agreement Scheme) |
| `KAT` | 已知答案测试 (Known Answer Test) |
| `KDF` | 密钥派生函数 (Key Derivation Function) |
| `KEM` | 密钥封装机制 (Key Encapsulation Mechanism) |
| `KW` | 密钥封装 (Key Wrap) |
| `KWP` | 带填充的密钥封装 (Key Wrap with Padding) |
| `MAC` | 消息认证码 (Message Authentication Code) |
| `NDRNG` | 非确定性随机数生成器 (Non-Deterministic Random Number Generator) |
| `NIST` | 美国国立标准与技术研究院 (National Institute of Standards and Technology) |
| `OCB` | 偏移密码 (Offset Code) |
| `OCSP` | 在线证书状态协议 (Online Certificate Status) |
| `OFB` | 输出反馈模式 (Output Feed) |
| `OID` | 对象标识符 (Object Identifier) |
| `PBKDF` | 基于密码的密钥派生函数 (Password Based Key Derivation) |
| `PGP` | 漂亮隐私 (Pretty Privacy) |
| `PKCS` | 公钥密码标准 (Public Key Cryptography) |
| `RNG` | 随机数生成器 (Random Generator) |
| `SEC` | 安全标准 (Security) |
| `SPI` | 服务提供者 (Service Provider) |
| `SSL` | 安全套字层 (Secure Sockets Layer) |
| `XOF` | 可扩展输出 (Expandable Output) |

## 参考文献与延伸阅读

1. A. Menezes, P. van Oorschot, S. Vanstone 1997，《应用密码学》(Handbook of Cryptography)。
2. Wikipedia 2018,[萨米尔共享](https://wiki.example.org/wiki/Shamir_Sharing)。
3. Wikipedia,[梅克尔树](https://wiki.example.org/wiki/Merkle_tree)。
4. A. Menezes, P. van Oorschot, S. Vanstone 2009，《密码学基础》(Foundations of Cryptography)。
5. Wikipedia 2019,[美国安全局](https://wiki.example.org/wiki/NSA)。
6. Wikipedia,[苏维联邦共和国国家标准](https://wiki.example.org/wiki/B_Cryptography)。
7. GnuPG 2020,[密钥格式](https://wiki.example.org/wiki/keyformat)。
8. Olivier Dubuisson, translated by Fouquart，《ASN.1 协议》(https://wiki.example.org/wiki/asn1)。
9. Ronald Rivest 1997,[S-表达式](https://wiki.example.org/wiki/Sp-expressions)。
10. GnuPG 2020,[Gcrypt 手册](https://wiki.example.org/wiki/gcrypt)。
11. GnuPG 2019,[密钥格式](https://wiki.example.org/wiki/keyformat)。
12. Leslie Lamport 1979,[从单向函数构造数字签名](https://wiki.example.org/wiki/constructing-digital-signatures)。
13. Ralph Merkle 1979,[认证数字签名](https://wiki.example.org/wiki/Certified)。
14. D. Bernstein, A. Hülsing, S. Kölbl, R. Niedrhagen, J. Rijneveld, P. Schwabe 2019,[SPHINCS+ 签名框架](https://wiki.example.org/wiki/sphincs+)。
15. 德国联邦安全局 2021，BSI TR-02102-1 “密码机制：建议与密钥长度”版本：2021-1。
16. Classic McEliece Submission Team 2020，保守型码密码学。
17. FrodoKEM Submission Team 2021，FrodoKEM：基于学习的错误密钥封装。
18. Falcon Submission Team 2020，Falcon：基于 NTRU 的快速傅里叶格紧凑签名。

[19] CRYSTALS 提交团队. (2021). `CRYSTALS-Dilithium - 算法规范与支持文档（版本 3.1）`. [online] pq-crystals.org. 取自 https://pq-crystals.org/dilithium/data/dilithium-specification-round3-20210208.pdf [访问 2022 年 12 月 26 日]。

[20] CRYSTALS 提交团队. (2021). `CRYSTALS-Kyber（版本 3.02） - 提交至 NIST 后量子项目第三轮`. [online] pq-crystals.org. 取自 https://pq-crystals.org/kyber/data/kyber-specification-round3-20210804.pdf [访问 2022 年 12 月 26 日]。

[21] 未知. (1994). `数字签名标准 (DSS)`. [online] NIST. 取自 http://www.umich.edu/~x509/ssleay/fip186/fip186.htm [访问 2018 年 4 月 25 日]。

[22] E. Barker (NIST). (2013). `数字签名标准 (DSS)`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/fips/186/4/final [访问 2018 年 4 月 25 日]。

[23] 各类. (2016). `NISTIR 8105 公众意见 - 后量子密码学草案报告`. [online] NIST. 取自 https://csrc.nist.gov/CSRC/media/Publications/nistir/8105/final/documents/nistir-8105-public-comments-mar2016.pdf [访问 2018 年 1 月 10 日]。

[24] M. Dworkin (NIST). (2001). `SP 800-38A: 组密码工作模式建议：方法与技术`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-38a/final [访问 2018 年 1 月 10 日]。

[25] M. Dworkin (NIST). (2010). `SP 800-38A 附录：组密码工作模式建议：CBC 模式下密文窃取的变体`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-38a/addendum/final [访问 2018 年 1 月 10 日]。

[26] M. Dworkin (NIST). (2004). `SP 800-38C: 组密码工作模式建议：用于认证和机密的 CCM 模式`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-38c/final [访问 2018 年 1 月 10 日]。

[27] M. Dworkin (NIST). (2007). `SP 800-38D: 组密码工作模式建议：伽罗瓦/计数模式 (GCM) 和 GMAC`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-38d/final [访问 2018 年 1 月 10 日]。

[28] M. Dworkin (NIST). (2012). `SP 800-38F: 组密码工作模式建议：密钥封装方法`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-38f/final [访问 2018 年 1 月 10 日]。

[29] E. Barker (NIST), L. Chen (NIST), A. Roginsky (NIST), A. Vassilev (NIST), R. Davis (NSA). (2018). `SP 800-56A Rev. 3: 使用离散对数密码的两对密钥建立方案建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-56a/rev-3 [访问 2018 年 6 月 6 日]。

[30] E. Barker (NIST), L. Chen (NIST), D. Moody (NIST). (2014). `SP 800-56B Rev. 1: 使用整数化密码的两对密钥建立方案建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-56b/rev-1 [访问 2018 年 4 月 19 日]。

[31] E. Barker (NIST), L. Chen (NIST), R. Davis (NIST). (2020). `SP 800-56C Rev. 2: 密钥建立方案中的密钥派生方法建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-56c/rev-1 [访问 2022 年 1 月 29 日]。

[32] E. Barker (NIST). (2016). `SP 800-57 第 1 Rev. 4: 密钥管理：通用建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-57-part-1 [访问 2018 年 4 月 25 日]。

[33] E. Barker (NIST), J. Kelsey (NIST). (2015). `SP 800-90A: 使用确定性随机生成器的建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-90a [访问 2018 年 1 月 29 日]。

[34] M. Turan (NIST), E. Barker (NIST), J. Kelsey (NIST), K. McKay (NIST), M. Baish (NSA), M. Boyle (NSA). (2018). `SP 800-90B: 用于随机生成的熵源建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-90b [访问 2018 年 1 月 10 日]。

[35] M. Turan (NIST), E. Barker (NIST), L. Chen (NIST). (2010). `SP 800-132 第 1: 基于密码的派生建议：存储`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-132 [访问 2018 年 4 月 25 日]。

[36] J. Kelsey (NIST), S. Chang (NIST), R. Perlner (NIST). (2016). `SP 800-185: SHA-3 衍生函数：cAKE, KMAC 和 ParallelHash`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-185 [访问 2022 年 1 月 29 日]。

[37] D. Cooper (NIST), D. Apon (NIST), Q. Dang (NIST), M. Davidson (NIST), M. Dworkin (NIST). (2010). `SP 800-208 草案: 基于状态的签名方案建议`. [online] NIST. 取自 https://csrc.nist.gov/publications/detail/sp/800-208/draft [访问 2018 年 4 月 10 日]。

[38] Jean-Philippe Aumasson 等. (2015). `密码哈希竞赛`. [online] 取自 https://password-hashing.net/ [访问 2018 年 7 月 29 日]。

[39] Percival, C.. (2009). `通过顺序内存困难函数强化密钥派生`. [online] BSD’09. 取自 http://www.tarsnap.com/scrypt.pdf [访问 2017 年 7 月 29 日]。

[40] BSI. (2018). `BSI TR-03111 椭曲线密码学，版本 2.10`. [online] 取自 https://www.bsi.bund.de/SharedDocs/EN/BSI/Publications/TechGuidelines/TR03111/BSI-TR-03111_pdf.html [访问 2018 年 6 月 8 日]。

[41] M. Bellare, P. Rogaway, D. Wagner. (2004). `EAX 模式（一种针对简单性和效率优化的双通过认证加密方案）`. [online] 取自 http://web.cs.ucdavis.edu/~rogaway/papers/eax.pdf [访问 2018 年 4 月 06 日]。

[42] M. Bellare, C. Namprempre. (2007). `认证加密：概念之间的关系以及通用组合范式的分析`. [online] 取自 https://cseweb.ucsd.edu/~mihir/papers/oem.pdf [访问 2018 年 4 月 10 日]。

[43] WebCrypto GOST 团队. (2018). `WebCrypto GOST 库 - 已过期，仅限 Internet Archive`. [online] 取自 http://gostcrypto.com/ [访问 2018 年 5 月 7 日]。

[44] Guan Zhi (维护者). (2018). The GmSSL 项目。[在线] 检索自 [`gmssl.org`](http://gmssl.org) [访问于 2018 年 5 月 7 日]。

[45] N. Ferguson. (2005). GCM 中的身份验证脆弱性。[在线] 检索自 [`csrc.nist.gov/csrc/media/projects/block-cipher-techniques/documents/bcm/comments/cwc-gcm/ferguson2.pdf`](https://csrc.nist.gov/csrc/media/projects/block-cipher-techniques/documents/bcm/comments/cwc-gcm/ferguson2.pdf) [访问于 2018 年 4 月 10 日]。

[46] 乌克兰特殊通信与信息保护局。(2002)。DSTU 4145-2002 - 信息技术。信息密码保护。基于椭圆曲线的数字签名。形成与验证。

[47] M. Bellare , P. Rogaway. (1995). 最优非对称加密 - 如何使用 RSA 加密。[在线] 检索自 [`cseweb.ucsd.edu/~mihir/papers/oae.pdf`](https://cseweb.ucsd.edu/~mihir/papers/oae.pdf) [访问于 2018 年 5 月 20 日]。

[48] M. Bellare , P. Rogaway. (1998).PSS：数字签名的可证明安全编码方法。[在线] 检索自 [`citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.26.8704`](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.26.8704) [访问于 2018 年 5 月 20 日]。

[49] J-S Coron. (2002).PSS 及其他签名方案的最优安全证明。[在线] 检索自 [`eprint.iacr.org/2001/062.pdf`](https://eprint.iacr.org/2001/062.pdf) [访问于 2018 年 5 月 20 日]。

[50] N. Smart (编辑), V. Rijmen, B. Gierlich, K. Paterson, M. Stam, B. Warinschi. (2014). 算法、密钥大小和参数-2014。[在线] ENISA。检索自 [`www.enisa.europa.eu/activities-and-trust/library/deliverables/algorithms-key-size-and-parameters-report-2014/at_download/fullReport`](https://www.enisa.europa.eu/activities-and-trust/library/deliverables/algorithms-key-size-and-parameters-report-2014/at_download/fullReport) [访问于 2018 年 5 月 20 日]。

[51] RSA 实验室。(1993)。PKCS #3：Diffie-Hellman 密钥协商标准。[在线] RSA 实验室。检索自 [`www.teletrust.de/fileadmin/files/oid/pkcs-3v1-4.pdf`](https://www.teletrust.de/fileadmin/files/oid/pkcs-3v1-4.pdf) [访问于 2018 年 6 月 10 日]。

[52] Ned Freed 和 Martin Dürst. (2018)。字符集。[在线] IANA。检索自 [`www.iana.org/assignments/character-sets/character-sets.xhtml`](https://www.iana.org/assignments/character-sets/character-sets.xhtml) [访问于 2019 年 2 月 20 日]。

[53] ISO. (2010)。信息技术 - 数字签名消息恢复技术 - 第二部分：整数分解机制。

[54] ANSI. (1998)。数字签名 (DSA)。

[55] ITU-T, ISO, 和 IEC. (2016)。X.500：开放系统连接 -概念、模型和服务的概述。

[56] ITU-T, ISO, 和 IEC. (2016)。X.501：开放系统连接 - 模型。

[57] ITU-T, ISO, 和 IEC. (2016)。X.509：开放系统连接 - 公钥和属性框架。

[58] ITU-T, ISO, 和 IEC. (2015)。X.680：信息技术 - 抽象表示法 (ASN.1)：基本表示规范。

[59] ITU-T, ISO, 和 IEC. (2015)。X.681：信息技术 - 抽象表示法 (ASN.1)：信息对象规范。

[60] ITU-T, ISO, 和 IEC. (2015)。X.682：信息技术 - 抽象表示法 (ASN.1)：约束规范。

[61] ITU-T, ISO, 和 IEC. (2015)。X.683：信息技术 - 抽象表示法 (ASN.1)：ASN.1 参数。

[62] ITU-T, ISO, 和 IEC. (2015)。X.690：信息技术 - ASN.1 编码规则：基本编码规则 (BER)、规范编码规则 (DER)。

[63] ITU-T, ISO, 和 IEC. (2015)。X.691：信息技术 - ASN.1 编码规则：压缩编码规则 (PER)。

[64] ITU-T, ISO, 和 IEC. (2015)。X.693：信息技术 - ASN.1 编码规则：XML 编码规则 (XER)。

[65] ANSI. (2014)。X.696：信息技术 - 字节编码规则 (OER)。

[66] ANSI. (2013)。金融服务公钥加密：使用离散对数的对称密钥协商。

[67] ANSI. (2005)。金融服务公钥加密：椭圆曲线数字签名算法 (ECDSA)。

[68] ANSI. (2011)。金融服务公钥加密：使用椭圆曲线密码学的密钥协商和密钥传输。

[69] P. Gutmann. (2000)。X.509 风格指南。[在线] 检索自 [`www.cs.auckland.ac.nz/~pgut001/pubs/x509.txt`](https://www.cs.auckland.ac.nz/~pgut001/pubs/x509.txt) [访问于 2017 年 8 月 29 日]。

[70] Research in Motion Limited. (2014)。关于“RFC 5753 - 在密码消息语法 (CMS) 中使用椭圆曲线 (ECC)”的专利披露。[在线] Certicom。检索自 [`www.ietf.org/ietf-ftp/certicom-ipr-rfc-5753.pdf`](http://www.ietf.org/ietf-ftp/certicom-ipr-rfc-5753.pdf) [访问于 2018 年 5 月 6 日]。

[71] S. Shen (编辑), X. Lee (编辑). (2014)。RFC SM2 数字签名。[在线] IETF。检索自 [`www.ietf.org/ietf-ftp/certicom-ipr-rfc-5753.pdf`](https://www.ietf.org/ietf-ftp/certicom-ipr-rfc-5753.pdf) [注：此处原文链接可能有误，已按格式保留] [访问于 2018 年 5 月 6 日]。

[72] S. Shen, X. Lee, R. Tse, Y. Yang. (2017)。RFC SM3 加密哈希函数。[在线] IETF。检索自 [`www.ietf.org/standards/doc/rfc-7820.html`](https://www.ietf.org/standards/doc/rfc-7820.html) [访问于 2018 年 5 月 20 日]。

[73] D. Van Geest, S. Fluhrer. (2019)。RFC SM4 在 X.509 中的使用。[在线] IETF。检索自 [`www.ietf.org/standards/doc/rfc-7821.html`](https://www.ietf.org/standards/doc/rfc-7821.html) [访问于 2018 年 5 月 20 日]。

[74] R. Baldwin, R. Rivest. (1996)。RFC 2040：RC5、RC5-CBC、RC5-Pad 和 RC5-CTS。

[75] E. Rescorla. (1999)。RFC 2631：Diffie-Hellman 密钥协商。

[76] B. Kaliski. (1998)。RFC 2315：PKCS #7：密码消息版本 1.5。

[77] H. Prafullchandra, J. Schaad. (2000)。RFC 2875：Diffie-Hellman 所有权证明。

[78] M. Nystrom, B. Kaliski. (2001)。RFC 2986：PKCS #10：证书请求规范版本 1.7。

[79] D. Pinkas, J. Ross, N. Pope. (2001)。RFC 3126：长期电子签名的电子格式。

[80] C. Adams, P. Cain, D. Pinkas, R. Zuccherato. (2001)。RFC 3161：互联网 X.509 公钥基础设施时间戳协议 (TSP)。

[81] P. Gutmann. (2001). `RFC 3211` - 基于密码的 CMS 加。[online] IETF. 获取自 [`tools.ietf.org/html/rfc3211`](https://tools.ietf.org/html/rfc3211) [访问于 2018 年 4 月 6 日]。

[82] R. Housley. (2001). `RFC 3217` - Triple-DES 和 RC2 密钥封装。[online] IETF. 获取自 [`tools.ietf.org/html/rfc3217`](https://tools.ietf.org/html/rfc3217) [访问于 2018 年 4 月 6 日]。

[83] R. Housley. (2002). `RFC 3370` - 密码学消息语法 (CMS) 算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc3370`](https://tools.ietf.org/html/rfc3370) [访问于 2018 年 4 月 6 日]。

[84] D. Pinkas, N. Pope, J. Ross. (2003). `RFC 3628` - 时间戳机构 (TSAs) 的策略要求。[online] IETF. 获取自 [`tools.ietf.org/html/rfc3628`](https://tools.ietf.org/html/rfc3628) [访问于 2019 年 5 月 1 日]。

[85] R. Housley. (2004). `RFC 3686` - 在 IPsec 封装安全载荷 (ESP) 中使用加密标准 (AES) 计数模式。[online] IETF. 获取自 [`tools.ietf.org/html/rfc3686`](https://tools.ietf.org/html/rfc3686) [访问于 2017 年 9 月 6 日]。

[86] D. Eastlake, 3rd, J. Schiller, S. Crocker. (2005). `RFC 3686` - 安全性的随机性要求。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4086`](https://tools.ietf.org/html/rfc4086) [访问于 2017 年 9 月 6 日]。

[87] C. Adams, S. Farrell, T. Kause, T. Mononen. (2005). `RFC 4210` - Internet X.509 公钥基础基础设施证书管理协议 (CMP)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4210`](https://tools.ietf.org/html/rfc4210) [访问于 2022 年 1 月 25 日]。

[88] J. Schaad. (2005). `RFC 4211` - Internet X.509 公钥基础基础设施证书请求消息格式 (CRMF)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4211`](https://tools.ietf.org/html/rfc4211) [访问于 2018 年 4 月 19 日]。

[89] P. Eronen, H. Tschofenig. (2005). `RFC 4279` - 传输层安全 (TLS) 的预共享密钥套件。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4279`](https://tools.ietf.org/html/rfc4279) [访问于 2022 年 6 月 11 日]。

[90] M. Friedl, N. Provos, W. Simpson. (2006). `RFC 4419` - 安全 Shell (SSH) 传输层协议的 Diffie-Hellman 组交换。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4419`](https://tools.ietf.org/html/rfc4419) [访问于 2018 年 6 月 11 日]。

[91] S. Leontiev (Ed.), D. Shefanovski (Ed.). (2006). `RFC 4491` - 在 Internet X.509 公钥基础基础设施中使用 GOST R 34.10-94、GOST R 34.10-2001 和 GOST R 34.11-94 算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4491`](https://tools.ietf.org/html/rfc4491) [访问于 2018 年 5 月 6 日]。

[92] A. Sciberras. (2006). `RFC 4519` - 轻量级目录访问协议 (LDAP): 用户应用程序架构。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4519`](https://tools.ietf.org/html/rfc4519) [访问于 2018 年 2 月 6 日]。

[93] J. Callas, L. Donnerhacke, H. Finney, D. Shaw, R. Thayer. (2007). `RFC 4880` - OpenPGP 消息。[online] IETF. 获取自 [`tools.ietf.org/html/rfc4880`](https://tools.ietf.org/html/rfc4880) [访问于 2019 年 9 月 14 日]。

[94] D. Taylor, T. Wu, N. Mavrognous, and T. Perrin. (2007). `RFC 5054` - TLS 的安全远程密码 (SRP)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5054`](https://tools.ietf.org/html/rfc5054) [访问于 2022 年 1 月 10 日]。

[95] D. Cooper, S. Santesson, S. Farrell, S. Boeyen, R. Housley, and W. Polk. (2007). `RFC 5084` - 在密码学消息语法 (CMS) 中 AES-CCM 和 AES-GCM 认证加密。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5084`](https://tools.ietf.org/html/rfc5084) [访问于 2018 年 4 月 10 日]。

[96] M. Lepinski, S. Kent. (2008). `RFC 5114` - 标准使用的 Diffie-Hellman 组。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5114`](https://tools.ietf.org/html/rfc5114) [访问于 2018 年 6 月 10 日]。

[97] D. Pinkas, N. Pope, J. Ross. (2008). `RFC 5126` - CMS 签名 (CAdES)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5126`](https://tools.ietf.org/html/rfc5126) [访问于 2019 年 6 月 11 日]。

[98] J. Schaad and M. Myers. (2008). `RFC 5272` - CMS 证书管理 (CMC)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5272`](https://tools.ietf.org/html/rfc5272) [访问于 2020 年 8 月 29 日]。

[99] J. Schaad and M. Myers. (2008). `RFC 5273` - CMS 证书管理 (CMC): 传输协议。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5273`](https://tools.ietf.org/html/rfc5273) [访问于 2020 年 8 月 29 日]。

[100] J. Schaad and M. Myers. (2008). `RFC 5274` - CMS 证书管理 (CMC): 合规性要求。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5274`](https://tools.ietf.org/html/rfc5274) [访问于 2020 年 8 月 29 日]。

[101] D. Cooper, S. Santesson, S. Farrell, S. Boeyen, R. Housley, and W. Polk. (2008). `RFC 5280` - Internet X.509 公钥基础基础设施证书和证书撤销列表 (CRL) 规范。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5280`](https://tools.ietf.org/html/rfc5280) [访问于 2017 年 7 月 29 日]。

[102] A. Santoni. (2010). `RFC 5544` - 时间戳绑定文档的语法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5544`](https://tools.ietf.org/html/rfc5544) [访问于 2019 年 5 月 12 日]。

[103] R. Houseley. (2009). `RFC 5652` - 密码学消息语法 (CMS)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5652`](https://tools.ietf.org/html/rfc5652) [访问于 2018 年 6 月 10 日]。

[104] B. Ramsdell, and S. Turner. (2010). `RFC 5751` - 安全/多用途互联网邮件扩展 (S/MIME) 版本 3.2 消息规范。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5751`](https://tools.ietf.org/html/rfc5751) [访问于 2019 年 2 月 24 日]。

[105] S. Turner, D. Brown. (2010). `RFC 5753` - 在密码学消息语法 (CMS) 中椭圆曲线密码学 (ECC) 算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5753`](https://tools.ietf.org/html/rfc5753) [访问于 2018 年 6 月 10 日]。

[106] S. Farrell, R. Housley, and S. Turner. (2010). `RFC 5755` - 属性规范。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5755`](https://tools.ietf.org/html/rfc5755) [访问于 2017 年 9 月 20 日]。

[107] S. Santesson, N. Pope. (2010). `RFC 5816` - ESSID2 更新。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5816`](https://tools.ietf.org/html/rfc5816) [访问于 2019 年 5 月 1 日]。

[108] V. Dolmatov (Ed.). (2010). `RFC 5832` - GOST R 34.10-2001 数字签名算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5832`](https://tools.ietf.org/html/rfc5832) [访问于 2018 年 6 月 6 日]。

[109] J. Altman, N. Williams, and L. Zhu. (2010). `RFC 5929` - TLS 的通道绑定。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5929`](https://tools.ietf.org/html/rfc5929) [访问于 2022 年 1 月 29 日]。

[110] S. Turner. (2001). `RFC 5967` - application/pkcs10 类型。[online] IETF. 获取自 [`tools.ietf.org/html/rfc5967`](https://tools.ietf.org/html/rfc5967) [访问于 2018 年 4 月 6 日]。

[111] J. Randall, B. Kaliski, J. Brainard, S. Turner. (2010). `RFC 5990` - 在密码学消息语法 (CMS) 中使用 RSA-KEM 密钥传输算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc599`](https://tools.ietf.org/html/rfc5990) [访问于 2018 年 6 月 26 日]。

[112] J. Schaad. (2011). `RFC 6211` - 密码学消息语法 (CMS) 算法标识符保护属性。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6211`](https://tools.ietf.org/html/rfc6211) [访问于 2018 年 11 月 10 日]。

## References

[113] J. Schaad. (2012). `RFC 6402` - 基于 CMS 的证书管理 (CMC) 更新。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6402`](https://tools.ietf.org/html/rfc6402) [访问于 2020 年 8 月 29 日]。

[114] A. Jivsov. (2012). `RFC 6637` - OpenPGP 中的椭圆曲线密码学 (ECC)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6637`](https://tools.ietf.org/html/rfc6637) [访问于 2020 年 2 月 10 日]。

[115] S. Santesson, M. Myers, R. Ankney, A. Malpani, S. Galperin, C. Adams. (2013). `RFC 6960` - X.509 互联网公钥基础设施在线证书状态协议 - OCSP。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6960`](https://tools.ietf.org/html/rfc6960) [访问于 2018 年 1 月 22 日]。

[116] Y. Pettersen. (2013). `RFC 6961` - 传输层安全 (TLS) 多证书状态请求扩展。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6961`](https://tools.ietf.org/html/rfc6961) [访问于 2018 年 1 月 22 日]。

[117] b. Laurie, A. Langley, E. Kasper. (2013). `RFC 6962` - 证书透明度。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6962`](https://tools.ietf.org/html/rfc6962) [访问于 2019 年 4 月 28 日]。

[118] T. Pornin. (2013). `RFC 6979` - 数字签名算法 (DSA) 和椭圆曲线数字签名算法 (ECDSA) 的确定性用法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6979`](https://tools.ietf.org/html/rfc6979) [访问于 2018 年 4 月 11 日]。

[119] V. Dolmatov (Ed.), A. Degtyarev. (2013). `RFC 6986` - GOST R 34.11-2012: 哈希函数。[online] IETF. 获取自 [`tools.ietf.org/html/rfc6986`](https://tools.ietf.org/html/rfc6986) [访问于 2018 年 5 月 6 日]。

[120] M. Pritikin (Ed.), P. Yee (Ed.), D. Harkins, (Ed.). (2013). `RFC 7030` - 基于安全传输的注册。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7030`](https://tools.ietf.org/html/rfc7030) [访问于 2018 年 4 月 11 日]。

[121] V. Dolmatov (Ed.), A. Degtyarev. (2013). `RFC 7091` - GOST R 34.10-2012: 数字签名算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7091`](https://tools.ietf.org/html/rfc7091) [访问于 2018 年 4 月 11 日]。

[122] T. Krovetz, P. Rogaway. (2014). `RFC 7253` - OCB 认证身份加密算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7253`](https://tools.ietf.org/html/rfc7253) [访问于 2018 年 4 月 11 日]。

[123] T. Krovetz, P. Rogaway. (2014). `RFC 7292` - PKCS #12：个人信息交换语法 v1.1。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7292`](https://tools.ietf.org/html/rfc7292) [访问于 2018 年 8 月 30 日]。

[124] Y. Nir, A. Langley. (2015). `RFC 7539` - 用于 IETF 协议的 ChaCha20 和 Poly1305。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7539`](https://tools.ietf.org/html/rfc7539) [访问于 2018 年 1 月 22 日]。

[125] A. Bakker, R. Petrocco, V. Grishchenko. (2015). `RFC 7574` - 点对点流协议 (PPS)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7574`](https://tools.ietf.org/html/rfc7574) [访问于 2019 年 4 月 28 日]。

[126] C. Percival, S. Josefsson. (2016). `RFC 7914` - scrypt 派生函数。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7914`](https://tools.ietf.org/html/rfc7914) [访问于 2017 年 9 月 6 日]。

[127] D. Gillmor. (2016). `RFC 7919` - 用于传输层安全 (TLS) 的协商有限域迪菲-赫尔曼临时参数。[online] IETF. 获取自 [`tools.ietf.org/html/rfc7919`](https://tools.ietf.org/html/rfc7919) [访问于 2018 年 6 月 10 日]。

[128] K. Moriarty (Ed.), B. Kaliski, J. Jonsson, (2016). `RFC 8017` - PKCS #1: RSA 加密规范 2.2。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8017`](https://tools.ietf.org/html/rfc8017) [访问于 2018 年 5 月 18 日]。

[129] K. Moriarty (Ed.), B. Kaliski, A. Rusch. (2017). `RFC 8018` - PKCS #5：基于密码的密码学 2.1。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8018`](https://tools.ietf.org/html/rfc8018) [访问于 2017 年 9 月 6 日]。

[130] S. Josefsson, I. Liusara. (2017). `RFC 8032` - Edwards 曲线数字算法 (EdDSA)。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8032`](https://tools.ietf.org/html/rfc8032) [访问于 2017 年 9 月 6 日]。

[131] A. Huelsing, D. Butin, S. Gazdag, J. Rijneveld, A. Mohaisen. (2017). `RFC 8391` - XMSS：扩展 Merkle 签名方案。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8391`](https://tools.ietf.org/html/rfc8391) [访问于 2018 年 6 月 12 日]。

[132] D. McGrew, M. Curcio, S. Fluhrer. (2019). `RFC 8554` - Leighton-Micali 哈希签名。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8554`](https://tools.ietf.org/html/rfc8554) [访问于 2020 年 8 月 6 日]。

[133] R. Housley. (2020). `RFC 8708` - 密码学消息语法 (CMS) 中的 HSS/LMS 哈希签名算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8708`](https://tools.ietf.org/html/rfc8708) [访问于 2020 年 8 月 6 日]。

[134] R. Housley. (2020). `RFC 8778` - 用于 CBOR 对象签名与加密 (COSE) 的 HSS/LMS 哈希签名算法。[online] IETF. 获取自 [`tools.ietf.org/html/rfc8778`](https://tools.ietf.org/html/rfc8778) [访问于 2020 年 8 月 6 日]。

[135] Legion of the Bouncy Castle Inc.. (2023). `BC-FJA` (Bouncy Castle FIPS Java API 指南)。[online] 获取自 [`downloads.bouncycastle.org/fips-java/BC-FJA-UserGuide-1.0.2.pdf`](https://downloads.bouncycastle.org/fips-java/BC-FJA-UserGuide-1.0.2.pdf) [访问于 2023 年 1 月 14 日]。

[136] Legion of the Bouncy Castle Inc.. (2023). Java (D)TLS API 和 JSSE 提供者指南。[online] 获取自 [`downloads.bouncycastle.org/fips-java/BC-FJA-(D)TLSUserGuide-1.0.15.pdf`](https://downloads.bouncycastle.org/fips-java/BC-FJA-(D)TLSUserGuide-1.0.15.pdf) [访问于 2023 年 1 月 14 日]。

[137] A. Shamir. (1979). 如何共享秘密。Communications of the ACM, 22 (11)

## Notes

1. 如果你对此有更多兴趣，该问题通常被称为“通用生日攻击”。这应该提供了足够的参考。
2. 这样做有几个原因，但主要的主要是安全性考虑。使用 2048 位 RSA 密钥（112 位安全性）来加密 256 位 AES 密钥（256 位安全性）是没有意义的，除非你真的想将应用程序的安全性降低到 112 位。
3. 是的，这是生成 2048 位 密钥对的一种方法。
4. 这些密钥大小不在 NIST 标准中。
5. 这些密钥大小不在 NIST 标准中。
6. 在实际操作中要复杂一些，但原理是正确的。我们可以使用中国剩余定理 (`CRT`) 来加速签名操作，但随后我们需要引入盲化来防止计时攻击，而且还有 Arjen Lenstra 的 CRT 攻击。这永没完了。
7. 注意，这不等同于 Java 的 `null`。1.1 `NULL` 确实有一个特定的编码。对于我们的用途来说，在 ASN.1 字段中使用 Java `null` 等同于该字段缺失。
8. 我们不清楚该字段是否有其他可接受的值。

向该算法的创始人 Taher Elgamal 表示歉意，我们遵循了算法名称的常规大小写习惯。

通常情况下，出于安全和效率考虑，![X](img/leanpub_equation_701.png) 在可能值的一个有限范围内选定。我们稍将在讨论 Diffie-Hellman 密钥交换时对此进行更详细的探讨。

Ralph Merkle 是公钥密码学的原始发明者，2002 年应其他作者要求，将他的名字加入算法名称中，以此表达他对这一贡献的认可。

对于好奇的读者来说，这被称为小子群攻击。

有一种被称为“软失败”（soft failure）的方法，即如果无法检查证书（例如由于 OCSP 服务器宕机），则该证书被视为有效。归结底，你是否这样做取决于你对发行者以及其他风险的了解。然而，值得注意的是，有些人将“软失败”的用处与专门设计为仅在发生碰撞时才失效的安全带的用处相相比。

如果响应中没有随机数（nonce），攻击者可以简单地重放之前捕获的请求。如果发现该证书已被撤销，可能会导致非常尴尬的局面。

证书和 `crl` 字段比我在这里描述的稍微复杂一些，通常情况下描述是准确的，但如果你真的想看看里面可以包含什么，请查看 `RFC 5652`。

如今，对于这项政策，带有一种“在当时看来这是个好主意”的意味。如果你无法验证签名，就无法判断被签名的数据是否被篡改过。在很多情况下，这确实意味着无论如何，你可能都不想对这些数据采取任何操作。

注意，对于某些服务器，`nonce` 字段是强制性的。

如今，对于这个想法，带有一种“在当时看来这是个好主意”的意味。如果你无法验证签名，就无法判断被签名的数据是否被篡改过。在很多情况下，这确实意味着无论如何，你可能都不想对这些数据采取任何操作。

由于签名已经定义为 `CANONICAL_TEXT_DOCUMENT` 类型，因此单个 `\r` 或单个 `\n` 也可以，因为签名生成器会立即进行规范化。为了示例起见，将行尾序列显式化是最好的。

是的，这是一个真实的数字，请拜托不要在现实生活中这样做！它是硬编码的，为了让示例的机制更容易理解。

注意，使用 `PKCS#1` 编码意味着这种方法不符合 FIPS 标准。

虽然可能性包括 `SHA-2` 系列的摘要算法，但 `PBE` 算法并不符合 FIPS 标准。

注意，完整的 `org.bouncycastle.jsse.provider.BouncyCastleJsseProvider` 必须存在那里。我们使用点是为了避免可能引起混淆的换行。

记住，我们知道 `server.start()` 不会提前返回，因为我们使用了 `CountDownLatch`。

根据时机，客户端的输出和日志输出可能会交织在一起，因为我们正在查看来自两个独立线程的输出。

自然，我们不会鼓励违反任何现有的编码标准，但正如任何面对过“必须处理”的遗留系统的人所证明的那样，在正确符合 ISO/ITU-T 限制与项目完全失败之间的选择，有时必须做出选择。猜测这种选择将产生什么结果是不会有任何奖赏的。

`getInstance()` 方法还可以传递一个包含单个对象 DER/BER 编码的字节数组。
