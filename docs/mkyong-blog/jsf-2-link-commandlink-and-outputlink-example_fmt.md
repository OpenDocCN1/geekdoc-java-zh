
# JSF 2 链接、命令链接和输出链接示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/jsf-2-link-commandlink-and-outputlink-example/>

在 JSF 中，`<h:link />`、`<h:commandLink />` 和 `<h:outputLink />` 标签被用来渲染一个 HTML“a”锚元素，请看下面的例子来了解其中的不同。

**Note**

在下面的示例中，假设“/JavaServerFaces/”是项目上下文 URL 的根目录。

## 1. JSF `h:link` 示例

`h:link` 标签是 JSF 2.0 中的新标签，`value` 属性呈现为锚文本，`outcome` 属性确定为 HTML 的目标 URL `href` 属性。参见示例：

1. 链接 + `outcome`

```java
 //JSF
<h:link value="Login page" outcome="login" />

//HTML output
<a href="/JavaServerFaces/faces/login.xhtml">Login page</a> 
```

2. 链接 + `outcome` + 参数

```java
 //JSF
<h:link value="Login page + Param " outcome="login" >
	<f:param name="username" value="mkyong" />
</h:link>

//HTML output
<a href="/JavaServerFaces/faces/login.xhtml?username=mkyong">Login page + Param</a> 
```

3. 链接 + `outcome` + 图像

```java
 //JSF
<h:link outcome="login" >
	<h:graphicImage library="images" name="sofa.png" />
</h:link>

//HTML output
<a href="/JavaServerFaces/faces/login.xhtml">
	<img src="/JavaServerFaces/faces/javax.faces.resource/sofa.png?ln=images" />
</a> 
```

## 2. JSF `h:commandLink` 示例

`h:commandLink` 标签是从 JSF 1.x 开始发布的，它生成一个链接，当点击时就像一个提交按钮。`value` 属性呈现为锚文本，`action` 属性确定为 HTML `href` 属性的目标 URL。此外，`h:commandLink` 将在页面中包含一个 `jsf.js` 文件，并将一个 `onclick` 事件附加到生成的链接上，参见示例：

**Note**

`j_idtx` 是 JSF 生成的随机值。

1. `commandLink`

```java
 //JSF
<h:commandLink value="Login page" />	

//HTML output
<script type="text/javascript" 
 src="/JavaServerFaces/faces/javax.faces.resource/jsf.js?ln=javax.faces&amp;stage=Development">
</script>

<a href="#"
	onclick="mojarra.jsfcljs(document.getElementById('j_idt6'),
        {'j_idt6:j_idt16':'j_idt6:j_idt16'},'');
	return false">
	Login page
</a> 
```

*P.S 如果省略了 `action` 属性，那么当点击按钮时，将重新加载当前页面。*

2. `commandLink` + 操作

```java
 //JSF
<h:commandLink action="#{user.goLoginPage}" value="Login page" />		

//HTML output
<script type="text/javascript" 
 src="/JavaServerFaces/faces/javax.faces.resource/jsf.js?ln=javax.faces&amp;stage=Development">
</script>

<a href="#" 
	onclick="mojarra.jsfcljs(document.getElementById('j_idt6'),
	{'j_idt6:j_idt18':'j_idt6:j_idt18'},'');
	return false">
	Login page
</a> 
```

你甚至不能在 HTML 输出中找到动作值，只有 JSF 知道它去了哪里。

3. `commandLink` + 操作 + 参数

```java
 //JSF
<h:commandLink action="#{user.goLoginPage}" value="Login page + Param ">
	<f:param name="username" value="mkyong" />
</h:commandLink>

//HTML output
<script type="text/javascript" 
 src="/JavaServerFaces/faces/javax.faces.resource/jsf.js?ln=javax.faces&amp;stage=Development">
</script>

<a href="#" 
	onclick="mojarra.jsfcljs(document.getElementById('j_idt6'),
	{'j_idt6:j_idt20':'j_idt6:j_idt20','username':'mkyong'},'');
	return false">
	Login page + Param 
</a> 
```

4. `commandLink` + 动作 + 图像

```java
 //JSF
<h:commandLink action="#{user.goLoginPage}">
	<h:graphicImage library="images" name="sofa.png" />
</h:commandLink>

//HTML output
<script type="text/javascript" 
 src="/JavaServerFaces/faces/javax.faces.resource/jsf.js?ln=javax.faces&amp;stage=Development">
</script>

<a href="#" 
	onclick="mojarra.jsfcljs(document.getElementById('j_idt6'),
	{'j_idt6:j_idt23':'j_idt6:j_idt23'},'');
	return false">
	<img src="/JavaServerFaces/faces/javax.faces.resource/sofa.png?ln=images" />
</a> 
```

## 3. JSF `h:outputLink` 示例

在 JSF 1.x 中发布了 `h:outputLink` 标签，标签体被渲染为锚文本，`value` 属性被直接渲染为 HTML `href` 属性的值，参见示例：

1. `outputLink`

```java
 //JSF
<h:outputLink>Login page</h:outputLink>

//HTML output
<a href="currentpage.xhtml">Login page</a> 
```

*P.S 如果 `value` 属性被省略，它会把当前页面的 URL 作为 `href` 属性的值。*

2. `outputLink` + `value`

```java
 //JSF
<h:outputLink value="login.xhtml" >
	Login page
</h:outputLink>

//HTML output
<a href="login.xhtml">
	Login page
</a> 
```

3. `outputLink` + `value` + `outputText` + 参数

```java
 //JSF
<h:outputLink value="login.xhtml">
	<h:outputText value="Login page" />
	<f:param name="username" value="mkyong" />
</h:outputLink>

//HTML output
<a href="login.xhtml?username=mkyong">Login page</a> 
```

4. `outputLink` + `value` + `outputText` + 图像

```java
 //JSF
<h:outputLink value="login.xhtml">
	<h:graphicImage library="images" name="sofa.png" />
</h:outputLink>

//HTML output
<a href="login.xhtml">
	<img src="/JavaServerFaces/faces/javax.faces.resource/sofa.png?ln=images" />
</a> 
```

## 我的想法…

以上三个链接标签的一些回顾：

1. `h:link` 标签对于生成需要与 JSF `outcome` 交互的链接是有用的，但是缺乏 `action` 支持使得很难生成动态结果。

2. `h:commandLink` 标签很烂，生成的 JavaScript 真的很吓人！不建议使用这个标签，除非你有充分的理由支持。但它支持 `action` 属性，这正是 `h:link` 所缺少的。

3. `h:outputLink` 对于生成不需要与 JSF 程序本身交互的链接是有用的。

最后，如果在 `h:link` 中加入 `action` 属性就更完美了。

## 下载源代码

Download It – [JSF-2-link-commandLink-outputLink-Example.zip](http://web.archive.org/web/20220121234631/http://www.mkyong.com/wp-content/uploads/2010/10/JSF-2-link-commandLink-outputLink-Example.zip) (15KB)

#### 参考

1. JSF `<h:link />` JavaDoc

2. [JSF `<h:commandLink />` JavaDoc](http://web.archive.org/web/20220121234631/https://javaserverfaces.dev.java.net/nonav/docs/2.0/pdldocs/facelets/h/commandLink.html)

3. [JSF `<h:outputLink />` JavaDoc](http://web.archive.org/web/20220121234631/https://javaserverfaces.dev.java.net/nonav/docs/2.0/pdldocs/facelets/h/outputLink.html)

<input type="hidden" id="mkyong-current-postId" value="7249">
