
# 2018 年 Java 的状态

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-in-2018>

过去几周，我一直在进行一年一度的“Java 现状”调查。这是该调查的第五年，自然也是迄今为止最大的一年，5160 名开发人员花时间浏览并回答了这个问题。

让我们直接进入数据。

## 1. Java 的采用

毫不奇怪，Java 8 仍然被大多数开发社区用于生产：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vT6QtOmTux128qHLply9A303gbQe0ovXADpqhu6OeO3obwp7rJnSZFNzG_65aIuHcWas7ZPj0BDwtuv/pubchart?oid=1722870527&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vT6QtOmTux128qHLply9A303gbQe0ovXADpqhu6OeO3obwp7rJnSZFNzG_65aIuHcWas7ZPj0BDwtuv/pubchart?oid=1722870527&format=interactive)

Java 9 和 10 的采用率仍然很低，不到 5%。

作为参考，2017 年，Java 7 和更早版本的数字约为 24.4%，现在为 10.6%——因此生态系统显然在升级，主要是升级到 Java 8。

## 2. 春季领养

现在让我们来看看 Spring 的数字：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vRllPCK5qOdIrxJHKcraR09JXjtNx2y8IvmR21ImZNjaXM4FdIYL6ZDj9ZcE-rjjMPEx53O8M2QzjH1/pubchart?oid=1660044821&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vRllPCK5qOdIrxJHKcraR09JXjtNx2y8IvmR21ImZNjaXM4FdIYL6ZDj9ZcE-rjjMPEx53O8M2QzjH1/pubchart?oid=1660044821&format=interactive)

在这里，向 Spring 5 的转移是显而易见的，24%的 Spring 支持的系统在生产中运行最新版本，比去年的 2.2%有所上升。

当然，今年我们也有明确的 Java EE 数字，因为——信不信由你——不是每个人都在使用 Spring🙂

## 3. Spring Boot 领养

在使用 Spring 构建的系统之外，几乎所有的系统在生产中都使用了 Boot：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vQCTNYDbV8HrTgVQljVZFb0c9b9ElF0vUXb6P9aVNU6k_Q9IJfxaTzs56_pBaSBkAJKx7P1WBGqTfw7/pubchart?oid=1660044821&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vQCTNYDbV8HrTgVQljVZFb0c9b9ElF0vUXb6P9aVNU6k_Q9IJfxaTzs56_pBaSBkAJKx7P1WBGqTfw7/pubchart?oid=1660044821&format=interactive)

令人惊讶的是 Spring Boot 2 被采用的速度有多快，考虑到 GA 发布还不到 2 个月，就已经有高达 30%的采用率。

“Boot 1.4 及以上版本”从一年前的 30%下降到现在的 6.8%，这意味着 Boot 人群的移动和升级比更广泛的生态系统快得多。

最后，去年大约有 30.2%的基于 Spring 的应用只是在使用核心框架，而不是 Boot。现在，这个数字只有 16.7%。简单来说，现在大多数 Spring 应用都在使用 Boot。

## 4. 构建工具采用

玛文哪儿也不去。该工具去年占据了 75.7%的份额，现在占据了 74.2%的市场份额：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vS-FComKlYiL_8EWunbCD8h1T1PWrqv5HOfxZLL9QQiaP5p80Le9IF5BmQCIKEE-ascv7p7kmH8B8sX/pubchart?oid=1660044821&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vS-FComKlYiL_8EWunbCD8h1T1PWrqv5HOfxZLL9QQiaP5p80Le9IF5BmQCIKEE-ascv7p7kmH8B8sX/pubchart?oid=1660044821&format=interactive)

至于 Gradle，它抢占了更多的市场份额，主要来自 Ant，现在只占不到 1/5 的市场份额——21.3%。

## 5. IDE 采用

IDE 的数字总是很有趣，今年也不例外：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vRFuZlg9qndyvDGGiX7D2iM_y9Ek75kQsXmM7Dcn3nNlfiC0VHvYloDh5CVY4hSO86TAUWbXpK_hs5C/pubchart?oid=1660044821&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vRFuZlg9qndyvDGGiX7D2iM_y9Ek75kQsXmM7Dcn3nNlfiC0VHvYloDh5CVY4hSO86TAUWbXpK_hs5C/pubchart?oid=1660044821&format=interactive)

IntelliJ 从 2017 年的 45.8%增长到今天的 55.4%，显然赢得了今年 Java 领域的 IDE 之战。

让一些非常直言不讳的支持者感到沮丧的是，NetBeans 今年的份额降至 5.1%，不到 2017 年 12.4%的一半。

Eclipse 似乎在一定程度上止住了流血，今年仅下跌了 2%，市场份额为 38%。

令人惊讶的是，IntelliJ 获得的大部分市场份额来自 NetBeans，而不是 Eclipse。

## 6. Web/应用服务器采用

以下是今天的服务器格局：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vQnMzpXb3lML991OEKm4gdEHjdhkvENw46Px_7CH-oA4At-g-OhzyIIpK4S72pwBkN3zrqg9-K9d7hv/pubchart?oid=1660044821&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vQnMzpXb3lML991OEKm4gdEHjdhkvENw46Px_7CH-oA4At-g-OhzyIIpK4S72pwBkN3zrqg9-K9d7hv/pubchart?oid=1660044821&format=interactive)

这实际上是调查中的一个新问题，因此没有 2017 年的数字来比较数据，但结论很明确，一点也不令人惊讶。

简单地说，Tomcat 拥有市场，其采用率比其他所有人加起来都高，达到 62.5%。

其他服务器看起来被大约 5%的市场所使用，这是一个相对平均的划分。

## 7. 其他 JVM 语言

到这里的最后一段——还有哪些基于 JVM 的语言在使用？

首先，62.8%的项目是单一语言的，只有 Java。

生态系统是这样的：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vSNPsNXscdXWpQCxVJ42kMFAqNap4brPWQyMsvEumv_jxmTbXphbyQrV4NZCmTpHjinGJKV7AxUkKyl/pubchart?oid=1695919612&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vSNPsNXscdXWpQCxVJ42kMFAqNap4brPWQyMsvEumv_jxmTbXphbyQrV4NZCmTpHjinGJKV7AxUkKyl/pubchart?oid=1695919612&format=interactive)

下面是一些使用其他语言的前瞻性项目：

[https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vQr-QpGt5mWwT1Ny7RRnuSynagmTHFDUVkSxrflWJrc6c4xJpY64iDCIVx5dcBEiA1MWw_VSjOVgP12/pubchart?oid=2099948811&format=interactive](https://web.archive.org/web/20220627141525if_/https://docs.google.com/spreadsheets/d/e/2PACX-1vQr-QpGt5mWwT1Ny7RRnuSynagmTHFDUVkSxrflWJrc6c4xJpY64iDCIVx5dcBEiA1MWw_VSjOVgP12/pubchart?oid=2099948811&format=interactive)

这里的主要外卖当然是 Kotlin——它经历了疯狂的一年，从 2017 年的 11.4%跃升至今天的 28.8%。

Scala 也很有意思，今年从 28.4%上升到 21.6%。

## 8. 结论

对 2018 年 Java 生态系统的审视无疑是有趣的，证实了一些已经众所周知的趋势，并揭示了一些新的趋势。

Spring Boot 现在是大多数 Spring 项目的一部分，这已经不足为奇了，但是考虑到这个项目相对较短的时间表，这仍然是一个巨大的成就。

在 IDE 方面，IntelliJ 仍然在快速发展。而且，非常相关的是，Kotlin 可能是今年最大的“赢家”，完全改变了 JVM 语言的前景。

总的来说，这是一个非常酷的 Java 社区，非常感谢所有参与的人。
