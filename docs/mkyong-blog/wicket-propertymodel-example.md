
# Wicket PropertyModel 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/wicket/wicket-propertymodel-example/>

在 Wicket 中，你可以使用`PropertyModel`类将表单组件绑定到一个属性类中。请参见下面的示例，向您展示如何操作：

## 1. 用户类

一个`User`类，有两个属性——`name`和`age`。

```java
package com.mkyong.user;

import java.io.Serializable;

public class User implements Serializable {

    private String name;
    private int age;

    //setter and getter methods

}
```

## 2. PropertyModel 示例

使用`PropertyModel`将`TextField`组件绑定到`User`对象的属性。

```java
package com.mkyong.user;

import org.apache.wicket.PageParameters;
import org.apache.wicket.markup.html.form.Form;
import org.apache.wicket.markup.html.form.TextField;
import org.apache.wicket.markup.html.panel.FeedbackPanel;
import org.apache.wicket.markup.html.WebPage;
import org.apache.wicket.model.PropertyModel;

public class UserPage extends WebPage {

    private User user = new User();
    private String nickname;

    public UserPage(final PageParameters parameters) {

        add(new FeedbackPanel("feedback"));

        final TextField<String> tName = new TextField<String>("name",
                new PropertyModel<String>(user, "name"));

        final TextField<Integer> tAge = new TextField<Integer>("age",
                new PropertyModel<Integer>(user, "age"));

        final TextField<String> tNickname = new TextField<String>("nickname",
                new PropertyModel<String>(this, "nickname"));

        Form<?> form = new Form<Void>("userForm") {

            @Override
            protected void onSubmit() {

                PageParameters pageParameters = new PageParameters();
                pageParameters.add("name", user.getName());
                pageParameters.add("age", Integer.toString(user.getAge()));
                pageParameters.add("nickname", nickname);

                setResponsePage(SuccessPage.class, pageParameters);

            }

        };

        add(form);
        form.add(tName);
        form.add(tAge);
        form.add(tNickname);

    }
}
```

将`tName`文本框组件绑定到`User`对象的`name`属性。

```java
final TextField<String> tName = new TextField<String>("name",
    new PropertyModel<String>(user, "name"));
```

将`tNickname`文本框组件绑定到当前`UserPage`的`nickname`属性。

```java
final TextField<String> tNickname = new TextField<String>("nickname",
    new PropertyModel<String>(this, "nickname"));
```

下载：[Wicket-PropertyModel-Examples.zip](http://web.archive.org/web/20190114230032/http://www.mkyong.com/wp-content/uploads/2011/05/Wicket-PropertyModel-Examples.zip)（10KB）

## 参考

1. [PropertyModel Javadoc](http://web.archive.org/web/20190114230032/http://wicket.apache.org/apidocs/1.4/org/apache/wicket/model/PropertyModel.html)
2. [使用属性模型](http://web.archive.org/web/20190114230032/https://cwiki.apache.org/WICKET/working-with-wicket-models.html#WorkingwithWicketmodels-PropertyModels)

[wicket](http://web.archive.org/web/20190114230032/http://www.mkyong.com/tag/wicket/)
