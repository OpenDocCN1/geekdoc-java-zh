
# GAE + Java——整合 Google 用户账户

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/google-app-engine/gae-java-integrating-google-user-account/>

在本教程中，我们将向您展示如何通过 Google Java SDK 的`UserService`类将 Google 用户帐户集成到 GAE + Java 项目中。

## 使用的工具

1. JDK 1.6
2. Eclipse 3.7 + Eclipse 的 Google 插件
3. 谷歌应用引擎 Java SDK 1.6.3.1

## 1. GAE 用户服务示例

如果用户使用他们的 Google 帐户登录，显示一条欢迎消息和一个“Logout”链接；否则显示一个“登录”链接。

```java
package com.mkyong.user;

import java.io.IOException;

import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import com.google.appengine.api.users.User;
import com.google.appengine.api.users.UserService;
import com.google.appengine.api.users.UserServiceFactory;

@SuppressWarnings("serial")
public class LoginExampleServlet extends HttpServlet {
	public void doGet(HttpServletRequest req, HttpServletResponse resp)
			throws IOException {

		UserService userService = UserServiceFactory.getUserService();
		User user = userService.getCurrentUser();

		resp.setContentType("text/html");
		resp.getWriter().println("<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>

<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script><h2>GAE - Integrating Google user account</h2>");

		if (user != null) {

			resp.getWriter().println("Welcome, " + user.getNickname());
			resp.getWriter().println(
				"<a href='"
					+ userService.createLogoutURL(req.getRequestURI())
					+ "'> LogOut </a>");

		} else {

			resp.getWriter().println(
				"Please <a href='"
					+ userService.createLoginURL(req.getRequestURI())
					+ "'> LogIn </a>");

		}
	}
}
```

### 注意

登录页或注销页都由 GAE 自动处理，但工作流程不同：

1. 在本地运行：它将模拟 Google 帐户登录页面（无密码认证）。
2. 在 GAE 上运行：它将重定向到实际的 Google 帐户登录屏幕。

## 2. 在本地运行

右键单击项目并作为“Web 应用程序”运行。默认情况下，它在端口`8888`上运行。

*图 2.1*：访问 URL：<http://localhost:8888/loginexample>

![GAE integrating google account and run it local](img/1bccc6ae5470c2b886843f94c8249f5f.png "GAE-local-integrating-google-account-1")

*图 2.2*：一个模拟 Google 的登录界面，输入一些东西，没有认证。

![GAE integrating google account and run it local](img/59880c9ddd67ae8938c05ac48c94ce56.png "GAE-local-integrating-google-account-2")

*图 2.3*：欢迎使用，显示注销链接。

![GAE integrating google account and run it local](img/673c6111e382ba8290237f482efe9bd6.png "GAE-local-integrating-google-account-3")

## 3. 部署在 GAE

使用应用程序 ID“mkyong-Java”部署 Google App Engine。

*图 3.1*：访问网址：<http://mkyong-java.appspot.com/loginexample>

![GAE integrating google account and run it on GAE](img/a9a4a31f9685837335ab87ef983c3729.png "GAE-integrating-google-account-1")

*图 3.2*：重定向至实际的 Google 帐户登录屏幕。

![GAE integrating google account and run it on GAE](img/361e198b7a4b4adeb15155869ee7371f.png "GAE-integrating-google-account-2")

*图 3.3*：如果登录成功，重定向回<http://mkyong-java.appspot.com/loginexample>。

![GAE integrating google account and run it on GAE](img/aa8d460185d8c2dbf1e40fa188ddaf8f.png "GAE-integrating-google-account-3")

## 下载源代码

由于文件很大，所有 GAE SDK 依赖库都被排除在外。

下载：[GAE-UserService-LoginExample.zip](http://web.archive.org/web/20190226114540/http://www.mkyong.com/wp-content/uploads/2012/04/GAE-UserService-LoginExample.zip)（8 KB）

## 参考

1. [使用用户服务](http://web.archive.org/web/20190226114540/https://developers.google.com/appengine/docs/java/gettingstarted/usingusers)
2. [用户 Java API](http://web.archive.org/web/20190226114540/https://developers.google.com/appengine/docs/java/users/)
3. GAE 用户服务 JavaDoc
4. [GAE Java hello world 示例](http://web.archive.org/web/20190226114540/http://www.mkyong.com/google-app-engine/google-app-engine-hello-world-example-using-eclipse/)

[gae](http://web.archive.org/web/20190226114540/http://www.mkyong.com/tag/gae/) [java](http://web.archive.org/web/20190226114540/http://www.mkyong.com/tag/java/)
