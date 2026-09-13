
# JSF 2 输出文本示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/jsf-2-outputtext-example/>

在 JSF 2.0 web 应用程序中，`h:outputText`标签是显示纯文本最常用的标签，它不会生成任何额外的 HTML 元素。参见示例…

## 1. 受管 Bean

一个受管 bean，提供一些文本用于演示。

```java
import javax.faces.bean.ManagedBean;
import javax.faces.bean.SessionScoped;

@ManagedBean(name="user")
@SessionScoped
public class UserBean{

	public String text = "This is Text!";
	public String htmlInput = "<input type='text' size='20' />";

	//getter and setter methods...
}
```

## 2. 查看页面

带有几个`h:outputText`标签的页面示例。

JSF…

```java
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html    
      xmlns:h="http://java.sun.com/jsf/html">

    <h:body>
    	<h1>JSF 2.0 h:outputText Example</h1>
    	<ol>
    	   <li>#{user.text}</li>

 	   <li><h:outputText value="#{user.text}" /></li>

	   <li><h:outputText value="#{user.text}" styleClass="abc" /></li>

	   <li><h:outputText value="#{user.htmlInput}" /></li>

	   <li><h:outputText value="#{user.htmlInput}" escape="false" /></li>
	 </ol>
    </h:body>
</html>
```

生成以下 HTML 代码…

```java
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
<html >
   <body> 
    	<h1>JSF 2.0 h:outputText Example</h1> 
    	<ol> 
    	   <li>This is Text!</li> 

           <li>This is Text!</li> 

	   <li><span class="abc">This is Text!</span></li> 

	   <li>&lt;input type='text' size='20' /&gt;</li> 

	   <li><input type='text' size='20' /></li> 
	</ol>
   </body> 
</html>
```

1. **对于 JSF 2.0 中的案例 1 和案例 2**，你其实并不需要使用`h:outputText`标签，因为你可以用直接的值表达式`#{user.text}`来实现同样的事情。
2. **对于案例 3**，如果存在`styleClass`、`style`、`dir`或`lang`属性中的任何一个，则呈现文本并用`span`元素将其换行。
3. **对于案例 4 和案例 5**，`h:outputText`标签中的`escape`属性，用于将敏感的 HTML 和 XML 标记转换为对应的有效 HTML 字符。

例如：

- `>` 转换为 `&gt;`
- `&` 转换为 `&amp;`

默认情况下，`escape`属性设置为 true。

**注意**

查看完整的敏感 HTML 和 XML 标记列表，请访问：

[http://www.ascii.cl/htmlcodes.htm](http://web.archive.org/web/20201226142726/http://www.ascii.cl/htmlcodes.htm)

## 3. 演示

URL：`http://localhost:8080/Java server faces/`

![jsf2-outputtext-example](img/413d8b6707570bd730af84dbf6c7ea11.png "jsf2-outputtext-example")

## 下载源代码

下载链接 – [JSF-2-OutputText-Example.zip](http://web.archive.org/web/20201226142726/http://www.mkyong.com/wp-content/uploads/2010/09/JSF-2-OutputText-Example.zip) (9KB)

#### 参考

1. [JSF `<h:outputText />` JavaDoc](http://web.archive.org/web/20201226142726/https://javaserverfaces.dev.java.net/nonav/docs/2.0/pdldocs/facelets/h/outputText.html)

标签：[JSF 2](http://web.archive.org/web/20201226142726/https://mkyong.com/tag/jsf2/)

### 相关文章

- [JSF 2.0 tutorial](http://web.archive.org/web/20201226142726/https://mkyong.com/jsf2/jsf-2-tutorial/)
- [JSF 新协议预发布会示例](/web/20201226142726/https://mkyong.com/jsf2/jsf-2-prerenderviewevent-example/)
- [JSF 2.0 多组件验证器的 commandLink 和 outputLink 示例](http://web.archive.org/web/20201226142726/https://mkyong.com/jsf2/jsf-2-commandlink-and-outputlink-example/)
- [JSF 2 列表框示例](/web/20201226142726/https://mkyong.com/jsf2/jsf-2-listbox-example/)
- [JSF 新协议数据表示例](/web/20201226142726/https://mkyong.com/jsf2/jsf-2-datatable-example/)
- [JSF2 单选按钮示例](/web/20201226142726/https://mkyong.com/jsf2/jsf-2-radio-buttons-example/)
- [警告：JSF1063 警告！设置不可序列化属性值到 HTTPSession](/web/20201226142726/https://mkyong.com/jsf2/warning-jsf1063-warning-setting-non-serializable-attribute-value-into-httpsession/)
- [JSF 2 下拉框示例](/web/20201226142726/https://mkyong.com/jsf2/jsf-2-dropdown-box-example/)
