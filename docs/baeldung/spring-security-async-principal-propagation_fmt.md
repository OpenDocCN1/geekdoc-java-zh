

# 使用 `@Async` 进行 Spring 安全上下文传播

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/spring-security-async-principal-propagation>

## 1. 简介

在本教程中，我们将重点介绍使用 `@Async` 传播 Spring Security 主体。

默认情况下，Spring Security 认证信息绑定到一个 `ThreadLocal`。因此，当执行流通过 `@Async` 在新线程中运行时，新线程中不会存在认证上下文。

这并不理想，下面让我们修复这个问题。

## 2. Maven 依赖

为了在 Spring Security 中使用异步集成，我们需要在 `pom.xml` 的 `dependencies` 中包含以下部分：

```java
<dependency>
    <groupId>org.springframework.security</groupId>
    <artifactId>spring-security-config</artifactId>
    <version>5.6.0</version>
</dependency>
```

Spring Security 依赖的最新版本可以在[这里](https://web.archive.org/web/20220812060426/https://search.maven.org/classic/#search%7Cga%7C1%7Cg%3A%22org.springframework.security%22)找到。

## 3. `@Async` 的 Spring Security 上下文传播

让我们先编写一个简单的示例：

```java
@RequestMapping(method = RequestMethod.GET, value = "/async")
@ResponseBody
public Object standardProcessing() throws Exception {
    log.info("Outside the @Async logic - before the async call: "
      + SecurityContextHolder.getContext().getAuthentication().getPrincipal());

    asyncService.asyncCall();

    log.info("Inside the @Async logic - after the async call: "
      + SecurityContextHolder.getContext().getAuthentication().getPrincipal());

    return SecurityContextHolder.getContext().getAuthentication().getPrincipal();
}
```

我们要检查 Spring `SecurityContext` 是否传播到新线程。首先，我们在异步调用之前记录上下文；接下来运行异步方法；最后再次记录上下文。`asyncCall()` 方法的实现如下：

```java
@Async
@Override
public void asyncCall() {
    log.info("Inside the @Async logic: "
      + SecurityContextHolder.getContext().getAuthentication().getPrincipal());
}
```

如我们所见，只有一行代码会输出异步方法所在新线程内部的上下文。

## 4. 默认配置

默认情况下，`@Async` 方法中的安全上下文值为 `null`。

特别是，如果我们运行异步逻辑，就能够在主程序中记录 `Authentication` 对象；但是，当我们在 `@Async` 中记录它时，该值将为 `null`。以下是日志输出示例：

```java
web - 2016-12-30 22:41:58,916 [http-nio-8081-exec-3] INFO
  o.baeldung.web.service.AsyncService -
  Outside the @Async logic - before the async call:
  [[email protected]](/web/20220812060426/https://www.baeldung.com/cdn-cgi/l/email-protection):
  Username: temporary; ...

web - 2016-12-30 22:41:58,921 [http-nio-8081-exec-3] INFO
  o.baeldung.web.service.AsyncService -
  Inside the @Async logic - after the async call:
  [[email protected]](/web/20220812060426/https://www.baeldung.com/cdn-cgi/l/email-protection):
  Username: temporary; ...

web - 2016-12-30 22:41:58,926 [SimpleAsyncTaskExecutor-1] ERROR
  o.s.a.i.SimpleAsyncUncaughtExceptionHandler -
  Unexpected error occurred invoking async method
  'public void com.baeldung.web.service.AsyncServiceImpl.asyncCall()'.
  java.lang.NullPointerException: null
```

因此，如你所见，在执行器线程中，调用因 NPE 而失败，这是意料之中的，因为主体并不存在。

## 5. 异步安全上下文配置

如果我们希望像在外部一样访问异步线程内部的主体，就需要创建 `DelegatingSecurityContextAsyncTaskExecutor` Bean：

```java
@Bean
public DelegatingSecurityContextAsyncTaskExecutor taskExecutor(ThreadPoolTaskExecutor delegate) {
    return new DelegatingSecurityContextAsyncTaskExecutor(delegate);
}
```

这样，Spring 就会在每次 `@Async` 调用中使用当前的 `SecurityContext`。

现在，让我们再次运行应用程序，并查看日志信息以确保配置确实生效：

```java
web - 2016-12-30 22:45:18,013 [http-nio-8081-exec-3] INFO
  o.baeldung.web.service.AsyncService -
  Outside the @Async logic - before the async call:
  [[email protected]](/web/20220812060426/https://www.baeldung.com/cdn-cgi/l/email-protection):
  Username: temporary; ...

web - 2016-12-30 22:45:18,018 [http-nio-8081-exec-3] INFO
  o.baeldung.web.service.AsyncService -
  Inside the @Async logic - after the async call:
  [[email protected]](/web/20220812060426/https://www.baeldung.com/cdn-cgi/l/email-protection):
  Username: temporary; ...

web - 2016-12-30 22:45:18,019 [SimpleAsyncTaskExecutor-1] INFO
  o.baeldung.web.service.AsyncService -
  Inside the @Async logic:
  [[email protected]](/web/20220812060426/https://www.baeldung.com/cdn-cgi/l/email-protection):
  Username: temporary; ...
```

现在，正如我们所料，我们在异步执行器线程中看到了相同的主体。

## 6. 用例

有几个有趣的用例，我们可能希望确保 `SecurityContext` 像这样传播：

- 我们希望发出多个外部请求，这些请求可以并行运行，并且可能需要很长时间来执行。
- 我们在本地有一些重要的处理要做，同时外部请求可以并行执行。
- 其他“一发了之”的场景，例如发送电子邮件。

## 7. 结论

在这个快速教程中，我们展示了 Spring 对发送带有传播 `SecurityContext` 的异步请求的支持。从编程模型的角度来看，这些新功能看起来似乎很简单。

请注意，如果多个方法调用以前以同步方式链接在一起，转换为异步方式可能需要同步结果。

这个示例也可以在 GitHub 上作为 Maven 项目[获得](https://web.archive.org/web/20220812060426/https://github.com/eugenp/tutorials/tree/master/spring-security-modules/spring-security-web-rest)。

