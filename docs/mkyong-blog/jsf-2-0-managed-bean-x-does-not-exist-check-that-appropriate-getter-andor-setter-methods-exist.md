
# JSF 2.0：托管 bean `x` 不存在，请检查适当的 getter 和/或 setter 方法是否存在

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/jsf-2-0-managed-bean-x-does-not-exist-check-that-appropriate-getter-andor-setter-methods-exist/>

## 问题

在 JSF 2.0 中，当使用`@ManagedProperty`注释将 bean 插入另一个 bean 的字段时，

**HelloBean.java**

```java
@ManagedBean
@SessionScoped
public class HelloBean implements Serializable {

	@ManagedProperty(value="#{message}")
	private MessageBean messageBean; 
```

**MessageBean.java**

```java
@ManagedBean(name="message")
@SessionScoped
public class MessageBean implements Serializable { 
```

它会显示以下错误消息。

> **出现错误：**
>
> 无法创建受管 bean `helloBean`。发现以下问题：–受管 bean `helloBean` 的属性 `messageBean` 不存在。检查是否存在适当的 getter 和/或 setter 方法。

## 解决办法

要将`messageBean`注入到`helloBean`的字段中，必须提供`messageBean` setter 方法。

**HelloBean.java**

```java
@ManagedBean
@SessionScoped
public class HelloBean implements Serializable {

	@ManagedProperty(value="#{message}")
	private MessageBean messageBean;

	public void setMessageBean(MessageBean messageBean) {
		this.messageBean = messageBean;
	} 
```

完成后，错误消息应该会消失。

[jsf2](http://web.archive.org/web/20190225125610/http://www.mkyong.com/tag/jsf2/) [managed bean](http://web.archive.org/web/20190225125610/http://www.mkyong.com/tag/managed-bean/)
