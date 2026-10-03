

# 如何在 Wicket 中获取 ServletContext

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/wicket/how-do-get-servletcontext-in-wicket/>

## 问题

`ServletContext` 是一个强大的 servlet 类，它可以提供关于 Web 应用程序的大量信息。有什么方法可以在 Wicket 中获得 `ServletContext` 类？

## 回答

是的，您可以通过 Wicket 的 `WebApplication` 类获得 `ServletContext` 类，如下所示：

```java
import javax.servlet.ServletContext;
import org.apache.wicket.Page;
import org.apache.wicket.protocol.http.WebApplication;
import com.mkyong.hello.Hello;

public class CustomApplication extends WebApplication {

	@Override
	public Class<? extends Page> getHomePage() {

		ServletContext servletContext = WebApplication.get().getServletContext();
		return Hello.class; //return default page

	}

}
```

## `servlet-api`

If Wicket application can not locate the `ServletContext` class, please import the `servlet-api` library into your project class path. For Maven, add this into your `pom.xml` file.

```xml
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>servlet-api</artifactId>
    <version>2.4</version>
</dependency>
```

[`servletcontext`](http://web.archive.org/web/20190304032545/http://www.mkyong.com/tag/servletcontext/) [`wicket`](http://web.archive.org/web/20190304032545/http://www.mkyong.com/tag/wicket/)

