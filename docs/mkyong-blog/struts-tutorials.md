
# Struts 教程

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/tutorials/struts-tutorials/>

![struts tutorials](img/71e3dc8ef1cec5bf8057bfe65d7ae2c8.png "struts-tutorials")

Struts 1.x 是最著名、最经典、最成熟的模型-视图-控制器（MVC）框架。很多时候，你会听到这样的话，学习 Struts 1.x 毫无意义，它是一个死框架。然而，尽管 Struts 1.x 在早期取得了巨大的成功，仍然有成千上万的公司在实施 Struts 1.x，并且从来没有考虑过升级，所以 Struts 1.x 仍然存在许多可维护性问题。

Struts 1.x 是一个完整的 web 框架，提供了完整的 web 表单组件、验证器、内部化、错误处理、tiles 布局，学习曲线低且易于实现。在本教程中，它提供了许多关于使用 Struts 1.x MVC 框架的分步示例和解释。

快乐学习 Struts。🙂

## Struts 快速入门

让我们快速了解一下 Struts 1.x 框架。

*   Struts hello world 示例

    通过一个 hello world 示例来理解 Struts MVC 是如何工作的。

## Struts 配置

所有关于 Struts 配置的东西。

*   [配置 Struts 标记库](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/configure-the-struts-tag-libraries/)

    要使用 Struts，您必须手动或自动配置 Struts 标记库属性。

*   [在 Struts 中配置欢迎页面](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/configure-a-welcome-page-in-struts/)

    在 Struts 中配置欢迎页面。

*   [多个 Struts 配置文件](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-multiple-configuration-files-example/)

    大型项目环境中需要多个 Struts 配置文件，这里有一个例子展示如何配置多个 Struts 配置文件。

*   [Struts 配置文件中的通配符支持](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-wildcards-example/)

    如果您的项目遵循某些标准文件结构，通配符是一个有用的特性，可以减少 Struts 配置文件中的重复代码。

## Struts 动作和动作表单

`Action` 和 `ActionForm` 实现类。

*   [ForwardAction 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-forwardaction-example/)

    允许你直接访问 JSP 类，而不需要通过控制器类。

*   [DispatchAction 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-dispatchaction-example/)

    允许你将所有相关的函数分组到一个单独的 `Action` 类中。

*   [MappingDispatchAction 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-mappingdispatchaction-example/)

*   [DynaActionForm 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-dynaactionform-example/)

    允许您以声明方式创建虚拟表单 bean，以提高开发速度。

## Struts Web 表单组件

Struts 完全支持所有标准的 web 表单组件。

*   [文本框示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmltext-textbox-example/)

    Struts `<html:text>` 文本框示例。

*   [隐藏值示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmlhidden-hidden-value-example/)

    Struts `<html:Hidden>` 隐藏值示例。

*   [单选选项示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmlradio-radio-option-example/)

    Struts `<html:radio>` 单选选项示例。

*   [下拉框示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmlselect-drop-down-box-example/)

    Struts `<html:select>` 下拉框示例。

*   [复选框示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmlcheckbox-checkbox-example/)

    Struts `<html:checkbox>` 复选框示例。

*   [文件上传示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-file-upload-example/)

    Struts `<html:file>` 文件上传示例。

*   [TextArea 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmltextarea-textarea-example/)

    Struts `<html:textarea>` 文本域示例。

*   [重写示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-htmlrewrite-example/)

    Struts `<html:rewrite>` 示例，呈现请求的 URI，无需创建超链接，对生成 JavaScript 和 CSS 文件有用。

## Struts 逻辑标记

Struts 附带了许多逻辑标记，以简化 bean 组件迭代或条件处理。

*   [<logic:iterate> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logic-iterate-example/)

    Struts 标签迭代集合。

*   [<logic:empty> <logic:notEmpty> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logic-empty-logic-notempty-example/)

    Struts 标记检查指定属性为空或零长度字符串。

*   [<logic:equal> <logic:notEqual> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logic-equal-logicnotequal-example/)

    Struts 标签检查指定属性是否等于给定值。

*   [<logic:greaterThan> <logic:greaterEqual> <logic:lessThan> <logic:lessEqual> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logicgreaterthan-logicgreaterequal-logiclessthan-logiclessequal-example/)

    比较数字的 Struts 条件标签。

*   [<logic:match> <logic:notMatch> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logicmatch-logicnotmatch-example/)

    Struts 标签检查指定属性是否包含给定值作为子串。

*   [<logic:messagesPresent> <logic:messagesNotPresent> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logic-messages-present-logic-messages-notpresent-example/)

    Struts 标签检查当前请求上是否存在指定的消息或错误消息。

*   [<logic:present> <logic:notPresent> 示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-logic-present-logic-notpresent-example/)

    Struts 标签检查指定的给定对象或属性是否存在于当前请求中。

## Struts 错误和日志记录

异常处理和错误记录。

*   [<global-exception> 自定义异常处理程序](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-global-custom-exception-example/)

    Struts `<global-exception>` 向用户显示自定义错误页面。

*   [Struts + Log4j 集成](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-log4j-integration-example/)

    将 Struts 与 Log4j 日志框架集成，记录系统异常和错误。

*   [在 Struts 中处理 404 错误](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/how-to-handle-404-error-in-struts/)

    在 Struts 中处理经典的 404 错误页面。

## Struts 本地化

Struts 在国际化或本地化方面有很好的支持。

*   [Struts 国际化或本地化示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-internationalizing-or-localization-example/)

    一个简单的用户登录示例，所有消息和错误消息都被本地化。

## Struts 验证程序框架

在 Struts 验证器框架中，它提供了许多泛型方法（`required`、`maxlength`、`minlength` 等）来验证表单组件，这使您的验证代码更加标准化，也更容易维护。

*   [Struts 验证器示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-validator-framework-example/)

    一个简单的用户注册表单，并用 Struts 验证器验证用户名、密码和电子邮件字段。

## Struts Tiles 框架

Struts tiles 框架是一个强大的布局框架，用于维护所有网页的页眉、页脚或菜单细节的标准外观。

*   [Struts Tiles 框架示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-tiles-framework-example/)

    一个简单的 web 应用程序，演示了使用 Struts tiles 框架来轻松更改页眉和页脚页面。

## Struts 与其他框架集成

任何关于 Struts 与其他框架集成的信息。

*   [Struts + Spring 集成](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-spring-integration-example/)

    用 Spring 框架集成 Struts 的例子。

*   [Struts + Hibernate 集成](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-hibernate-integration-example/)

    用 Hibernate 框架集成 Struts 的例子。

*   [Struts + Spring + Hibernate 集成](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-spring-hibernate-integration-example/)

    集成 Struts 与 Spring 和 Hibernate 框架的例子。

*   [Struts + Quartz scheduler 集成](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-quartz-scheduler-integration-example/)

    用 Quartz 框架集成 Struts 的例子。

*   [Struts + Spring + Quartz scheduler 集成](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-spring-quartz-scheduler-integration-example/)

    用 Spring 和 Quartz 框架集成 Struts 的例子。

## Struts 杂项

其他 Struts 示例。

*   [从网站下载文件示例](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-download-file-from-website-example/)

    如何在 Struts 中从网站下载文件。

## Struts 常见错误

一些 Struts 常见的错误消息。

*   [绝对 uri:http://struts.apache.org/tags-bean 无法在 web.xml 或使用此应用程序部署的 jar 文件中解析](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/the-absolute-uri-httpstruts-apache-orgtags-bean-cannot-be-resolved-in-either-web-xml-or-the-jar-files-deployed-with-this-application/)

*   [java.lang.ClassNotFoundException: org.apache.struts.action.ForwardAction](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/java-lang-classnotfoundexception-org-apache-struts-action-forwardaction/)

*   [在关键字 org.apache.struts.action.MESSAGE 下找不到消息资源](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/cannot-find-message-resources-under-key-org-apache-struts-action-message/)



*   [Java . lang . noclassdeffounderror:org/Apache/commons/file upload/file upload exception](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/java-lang-noclassdeffounderror-orgapachecommonsfileuploadfileuploadexception/)
*   [Java . lang . noclassdeffounderror:org/Apache/commons/io/output/deferred file output stream](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/java-lang-noclassdeffounderror-orgapachecommonsiooutputdeferredfileoutputstream/)
*   [<全局异常> xml 解析异常](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-global-exception-xml-parsing-exception/)
*   [NoSuchMethodError:digester . parse(Ljava/net/URL；)Ljava/lang/Object](http://web.archive.org/web/20220121120759/http://www.mkyong.com/struts/struts-error-nosuchmethoderror-digester-parseljavaneturlljavalangobject/)

## Struts 参考

*   [Struts 1.x 官方文档](http://web.archive.org/web/20220121120759/https://struts.apache.org/1.3.10/userGuide/index.html)
*   [http://en.wikipedia.org/wiki/Apache_Struts](http://web.archive.org/web/20220121120759/https://en.wikipedia.org/wiki/Apache_Struts)

<input type="hidden" id="mkyong-current-postId" value="4831">
