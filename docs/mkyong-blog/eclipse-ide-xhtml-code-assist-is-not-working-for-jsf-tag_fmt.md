
# Eclipse IDE：`.xhtml` 代码辅助不适用于 JSF 标签

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/eclipse-ide-xhtml-code-assist-is-not-working-for-jsf-tag/>

## 问题

使用 Eclipse Helios（3.6）开发 JSF 2.0 Web 应用程序。在 `.xhtml` 文件中，当我按下“`Ctrl + Space`”组合键调用 JSF 标签的代码助手时，没有任何提示？看起来 JSF 标签的代码助手在 `.xhtml` 文件扩展名中无法正常工作。

![eclipse-jsf-support](img/324ba5623c411358ec17c224b42c2eed.png "eclipse-jsf-support-0")

## 解决办法

在 Eclipse 项目中，你必须确保项目支持 WTP 和 JSF 功能。

1. 右键单击项目，选择 **Properties**，选择 **Project Facets**，确保 **JavaServer Faces** 被选中。稍后，点击 **Further configuration…** 链接来配置 JSF 功能。

   ![eclipse-jsf-support](img/7e26b827510a0be71e33d9533bf81665.png "eclipse-jsf-support-1")

2. 创建一个用户库，包括 JSF API 和实现库：`jsf-api-xxx.jar` 和 `jsf-impl-xxx.jar`。这将为你的项目添加 JSF 功能。

   ![eclipse-jsf-support](img/25f2fb9009c2b82db4b7db4f79e6852d.png "eclipse-jsf-support-2")

3. 完成后，在 `.xhtml` 文件中再次按下“`Ctrl + Space`”组合键。现在，它可以正确提示 JSF 标签代码辅助功能。此外，它还会为网页编辑器添加 JSF 可视化编辑器。

   ![eclipse-jsf-support](img/8b76e2635fafba8176cee3981fa14c6b.png "eclipse-jsf-support-3")

