
# Spring WebFlux 测试——阻塞读取超时 5000 毫秒

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/spring-boot/spring-webflux-test-timeout-on-blocking-read-for-5000-milliseconds/>

用`WebTestClient`测试一个 Spring Webflux 端点，并显示以下错误消息。这有可能增加超时时间吗？

```java
java.lang.IllegalStateException: Timeout on blocking read for 5000 MILLISECONDS

	at reactor.core.publisher.BlockingSingleSubscriber.blockingGet(BlockingSingleSubscriber.java:117)
	at reactor.core.publisher.Mono.block(Mono.java:1524)
	at org.springframework.test.web.reactive.server.ExchangeResult.formatBody(ExchangeResult.java:247)
	at org.springframework.test.web.reactive.server.ExchangeResult.toString(ExchangeResult.java:216)
	at java.base/java.lang.String.valueOf(String.java:2788)
	at java.base/java.lang.StringBuilder.append(StringBuilder.java:135)
	at org.springframework.test.web.reactive.server.ExchangeResult.assertWithDiagnostics(ExchangeResult.java:200)
```

## 解决办法

默认情况下，`WebTestClient`会在 5 秒后超时。我们可以用`@AutoConfigureWebTestClient`配置超时

```java
@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
@AutoConfigureWebTestClient(timeout = "10000")//10 seconds
public class TestCommentWebApplication {

    @Autowired
    private WebTestClient webClient;
```

# 参考

*   [Spring Boot 测试](http://web.archive.org/web/20190308021305/https://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-testing.html)
*   [AutoConfigureWebTestClient docs](http://web.archive.org/web/20190308021305/https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/autoconfigure/web/reactive/AutoConfigureWebTestClient.html)
*   [WebTestClient 文档](http://web.archive.org/web/20190308021305/https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/test/web/reactive/server/WebTestClient.html)

[unit test](http://web.archive.org/web/20190308021305/http://www.mkyong.com/tag/unit-test/) [webflux](http://web.archive.org/web/20190308021305/http://www.mkyong.com/tag/webflux/)
