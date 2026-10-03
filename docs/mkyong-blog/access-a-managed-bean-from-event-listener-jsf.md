
# 从事件监听器访问 JSF 受管 Bean

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/access-a-managed-bean-from-event-listener-jsf/>

## 问题

JSF 事件监听器类如何访问另一个受管 Bean？请参见下面的场景。

### JSF 页面

```java
<h:selectOneMenu value="#{country.localeCode}" onchange="submit()">
    <f:valueChangeListener type="com.mkyong.CountryValueListener" />
    <f:selectItems value="#{country.countryInMap}" />
</h:selectOneMenu>
```

### 国家受管 Bean

```java
package com.mkyong;

import java.io.Serializable;
import javax.faces.bean.ManagedBean;
import javax.faces.bean.SessionScoped;

@ManagedBean(name="country")
@SessionScoped
public class CountryBean implements Serializable {

    private String localeCode;

    public void setLocaleCode(String localeCode) {
        this.localeCode = localeCode;
    }

    //...
}
```

### `ValueChangeListener`

```java
package com.mkyong;

import javax.faces.event.AbortProcessingException;
import javax.faces.event.ValueChangeEvent;
import javax.faces.event.ValueChangeListener;

public class CountryValueListener implements ValueChangeListener {

    @Override
    public void processValueChange(ValueChangeEvent event)
            throws AbortProcessingException {

        // 如何访问现有的 country 受管 Bean？
        // country.setLocaleCode(event.getNewValue().toString());

    }
}
```

## 解决办法

实际上，有许多方法可以从事件监听器类或另一个受管 Bean 访问现有的受管 Bean。参见以下示例。

### 1. `getApplicationMap()`

如果国家受管 Bean 声明在应用程序范围内：

```java
CountryBean country = (CountryBean) FacesContext.getCurrentInstance()
        .getExternalContext().getApplicationMap().get("country");
```

### 2. `getRequestMap()`

如果国家受管 Bean 声明在请求范围内：

```java
CountryBean country = (CountryBean) FacesContext.getCurrentInstance()
        .getExternalContext().getRequestMap().get("country");
```

### 3. `getSessionMap()`

如果国家受管 Bean 声明在会话范围内：

```java
CountryBean country = (CountryBean) FacesContext.getCurrentInstance()
        .getExternalContext().getSessionMap().get("country");
```

### 4. `ELResolver()`

使用 ELResolver：

```java
FacesContext context = FacesContext.getCurrentInstance();

CountryBean country = (CountryBean) context
        .getELContext()
        .getELResolver()
        .getValue(context.getELContext(), null, "country");
```

### 5. `ValueExpression()`

使用 ValueExpression：

```java
FacesContext context = FacesContext.getCurrentInstance();

CountryBean country = (CountryBean) context
        .getApplication()
        .getExpressionFactory()
        .createValueExpression(
                context.getELContext(),
                "#{country}",
                CountryBean.class)
        .getValue(context.getELContext());
```

### 6. `evaluateExpressionGet()`

使用 `evaluateExpressionGet()`：

```java
FacesContext context = FacesContext.getCurrentInstance();

CountryBean country = (CountryBean) context
        .getApplication()
        .evaluateExpressionGet(context, "#{country}", CountryBean.class);
```

## 参考

1. [getApplicationMap() JavaDoc](http://web.archive.org/web/20190225130011/http://download.oracle.com/docs/cd/E17802_01/j2ee/j2ee/javaserverfaces/1.2/docs/api/javax/faces/context/ExternalContext.html#getApplicationMap%28%29)

2. [getRequestMap() JavaDoc](http://web.archive.org/web/20190225130011/http://download.oracle.com/docs/cd/E17802_01/j2ee/j2ee/javaserverfaces/1.2/docs/api/javax/faces/context/ExternalContext.html#getRequestMap%28%29)

3. [getSessionMap() JavaDoc](http://web.archive.org/web/20190225130011/http://download.oracle.com/docs/cd/E17802_01/j2ee/j2ee/javaserverfaces/1.2/docs/api/javax/faces/context/ExternalContext.html#getSessionMap%28%29)

4. [getELResolver() JavaDoc](http://web.archive.org/web/20190225130011/http://download.oracle.com/javaee/5/api/javax/faces/application/Application.html#getELResolver%28%29)

5. [createValueExpression() JavaDoc](http://web.archive.org/web/20190225130011/http://download.oracle.com/javaee/5/api/javax/el/ExpressionFactory.html#createValueExpression%28javax.el.ELContext,%20java.lang.String,%20java.lang.Class%29)

6. [evaluateExpressionGet() JavaDoc](http://web.archive.org/web/20190225130011/http://download.oracle.com/javaee/5/api/javax/faces/application/Application.html#evaluateExpressionGet%28javax.faces.context.FacesContext,%20java.lang.String,%20java.lang.Class%29)

[jsf2](http://web.archive.org/web/20190225130011/http://www.mkyong.com/tag/jsf2/)
