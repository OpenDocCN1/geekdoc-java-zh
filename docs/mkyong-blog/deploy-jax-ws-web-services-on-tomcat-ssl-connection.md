
# 在 Tomcat + SSL 连接上部署 JAX-WS web 服务

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/webservices/jax-ws/deploy-jax-ws-web-services-on-tomcat-ssl-connection/>

在本文中，我们将向您展示如何在启用了 TLS / SSL 或 https 安全连接的 Tomcat 上部署 JAX-WS web 服务。实际上，答案很简单，只需将它部署为普通的 web 服务，并在 Tomcat 服务器上正确配置 SSL 连接🙂

**Note**

This article is just a combination of my last few posts on developing web service in SSL connection environment.

## 1. 配置 Tomcat + SSL

有关详细信息，请参见本指南—[让 Tomcat 支持 SSL 或 https 连接](http://web.archive.org/web/20220619045647/http://www.mkyong.com/tomcat/how-to-configure-tomcat-to-support-ssl-or-https/)。

基本上，只需从可信的证书提供商那里购买一个证书，或者使用 JDK 的`keytool`命令为本地主机测试生成一个伪证书。并将以下部分放入您的 Tomcat `server.xml`文件中。

*File: `$Tomcat\conf\server.xml`*

```java
 //...
 <!-- Define a SSL HTTP/1.1 Connector on port 8443
         This connector uses the JSSE configuration, when using APR, the 
         connector should be using the OpenSSL style configuration
         described in the APR documentation -->

 <Connector port="8443" protocol="HTTP/1.1" SSLEnabled="true"
               maxThreads="150" scheme="https" secure="true"
               clientAuth="false" sslProtocol="TLS" 
	       keystoreFile="c:\your keystore file"
	       keystorePass="your keystore password" />
  //... 
```

重启 Tomcat，现在，你的 Tomcat 支持 SSL 连接，例如 *https://localhost:8443*

## 2. 部署 Web 服务

像部署一个普通的 web 服务一样部署它，参见本指南—[在 Tomcat servlet 容器上部署 JAX-WS web 服务](http://web.archive.org/web/20220619045647/http://www.mkyong.com/webservices/jax-ws/deploy-jax-ws-web-services-on-tomcat/)。

## 3. 测试一下

配置完成；您可以通过使用普通的 web 服务客户端，在 SSL 连接中访问部署的 web 服务。

举个例子，

```java
 URL url = new URL("https://localhost:8443/HelloWorld/hello?wsdl");
    QName qname = new QName("http://ws.mkyong.com/", "HelloWorldImplService");
    Service service = Service.create(url, qname);

    HelloWorld hello = service.getPort(HelloWorld.class);
    System.out.println(hello.getHelloWorldAsString()); 
```

**Note**

For localhost SSL testing environment, the client will hit following exceptions, please read the problem and solution below :

1. [Java.security.cert.certificate 异常:找不到与本地主机匹配的名称](http://web.archive.org/web/20220619045647/http://www.mkyong.com/webservices/jax-ws/java-security-cert-certificateexception-no-name-matching-localhost-found/)

2. [SunCertPathBuilderException:无法找到请求目标的有效认证路径](http://web.archive.org/web/20220619045647/http://www.mkyong.com/webservices/jax-ws/suncertpathbuilderexception-unable-to-find-valid-certification-path-to-requested-target/)

## 4. 完成的

你的 web 服务是在 SSL 保护下的，相当简单，web 服务站点上没有变化；只需将您的 Tomcat 配置为只支持 SSL 连接。

#### 参考

1. [维基 SSL 连接](http://web.archive.org/web/20220619045647/https://en.wikipedia.org/wiki/SSL)

2. [JAX-WS 你好世界示例](http://web.archive.org/web/20220619045647/http://www.mkyong.com/webservices/jax-ws/jax-ws-hello-world-example/)

<input type="hidden" id="mkyong-current-postId" value="7926">
