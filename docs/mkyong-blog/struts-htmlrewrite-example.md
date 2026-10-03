
# Struts `<html:rewrite>` 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/struts/struts-htmlrewrite-example/>

Struts `<html:rewrite>` 标签用于在 HTML 页面中重写并生成资源路径。

## 1. CSS 文件

使用 Struts 重写标签在 HTML 页面中包含一个 CSS 文件。

```java
<%@taglib uri="http://struts.apache.org/tags-html" prefix="html"%>
<html:rewrite page="/common.css" />
```

它将转换成下面的 HTML 代码。

```html
<link rel="stylesheet" href="/StrutsExample/common.css" type="text/css" />
```

## 2. Javascript 文件

使用 Struts 重写标签在 HTML 页面中包含一个 Javascript 文件。

```java
<%@taglib uri="http://struts.apache.org/tags-html" prefix="html"%>
<html:rewrite page="/common.js" />
```

它将被转换成下面的 HTML 代码。

```html
<script type="text/javascript" src="/StrutsExample/common.js"></script>
```

`StrutsExample` 是 Struts 项目的根文件夹。

## 参考

- [http://struts.apache.org/1.x/struts-taglib/tlddoc/html/rewrite.html](http://web.archive.org/web/20190209023730/http://struts.apache.org/1.x/struts-taglib/tlddoc/html/rewrite.html)
- [struts](http://web.archive.org/web/20190209023730/http://www.mkyong.com/tag/struts/)
