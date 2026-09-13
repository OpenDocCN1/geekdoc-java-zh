
# 下载/导出 Google 应用程序引擎日志、Java 应用程序

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/google-app-engine/download-export-google-app-engine-logs-java-app/>

在 GAE Java 应用中，您可以使用命令`appcfg request_logs`从 GAE 下载或导出日志到您的电脑，命令签名如下：

```java
AppCfg [options] request_logs <app-dir> <output-file>
```

您可以输入`appcfg request_logs`来查看所有可用选项。

## 1. 什么是`<app-dir>`？

这不是您的`app_id`，也不是来自 GAE 的任何已部署 Web 路径，而是您的本地项目文件夹，其中包含以下文件：

1. `WEB-INF/appengine-web.xml`
2. `WEB-INF/web.xml`

GAE Java SDK 中的命令`appcfg`是硬编码的，可以查找上面两个文件。要从 GAE 下载日志，您必须在`WEB-INF`文件夹中提供上述两个 XML 文件。这虽然没有意义，但您别无选择，只能遵循 GAE 的做法。

在我看来，更好的方法应该是：

```java
AppCfg [options] request_logs <app-id-on-GAE> <output-file>
```

**Note**

如果您没有这些 XML 文件，但仍然想下载日志，可以执行`appcfg download_app`，下载已部署的应用程序，其中包含这些 XML 文件。

## 2. 例子

以下是一些从 GAE 下载日志的常见例子。

### 2.1 从 GAE 下载今天的日志到`c:\gae.log`

```java
C:\appengine-java-sdk-1.6.3.1\bin>
appcfg request_logs C:\workspace-3.7\SpringGAEProject\war\ c:\gae.log
```

### 2.2 将 GAE 的所有日志下载到`c:\gae.log`

```java
C:\appengine-java-sdk-1.6.3.1\bin>
appcfg --num_days=0 request_logs C:\workspace-3.7\SpringGAEProject\war\ c:\gae.log
```

默认情况下，`--num_days=1`。

### 2.3 将严重性为 4 的所有日志从 GAE 下载到`c:\gae.log`

```java
C:\appengine-java-sdk-1.6.3.1\bin>
appcfg --num_days=0 --severity=4 request_logs C:\workspace-3.7\SpringGAEProject\war\ c:\gae.log
```

*P.S. Severity 是日志中的记录级别。范围是 0（调试）到 4（关键）。*

### 2.4 从 GAE 下载所有日志并附加到`c:\gae.log`

```java
C:\appengine-java-sdk-1.6.3.1\bin>
appcfg --num_days=0 --append request_logs C:\workspace-3.7\SpringGAEProject\war\ c:\gae.log
```

## 参考

1. [GAE 下载日志文档](http://web.archive.org/web/20190227044303/https://developers.google.com/appengine/docs/java/tools/uploadinganapp#Downloading_Logs)
2. [下载应用引擎日志](http://web.archive.org/web/20190227044303/http://blog.dantup.com/2009/12/downloadingexporting-app-engine-logs.html)

[export](http://web.archive.org/web/20190227044303/http://www.mkyong.com/tag/export/) [gae](http://web.archive.org/web/20190227044303/http://www.mkyong.com/tag/gae/) [logs](http://web.archive.org/web/20190227044303/http://www.mkyong.com/tag/logs/)
