
# Spring Boot — AWS

> 原文：<https://medium.com/javarevisited/spring-boot-aws-8cf2f1df84a6?source=collection_archive---------2----------------------->

如何部署 Spring Boot 应用程序的简单指南。我用过 AWS 的免费层。你可以去 AWS 网站注册。一年内免费。

如果你有任何建议或者如果你觉得有什么需要，你可以给出你的意见。

让我们开始一步一步地在 AWS 中上传 Spring Boot 应用程序。

## 创建 EC2 实例

步骤 1：创建一个 EC2 实例。登录 AWS 控制台。我们将使用 AWS 的免费层。

`https://signin.aws.amazon.com/`

![](img/1d56204eb02cf3e1e7e995ec45641c86.png)

步骤 2：登录后，单击服务并选择 EC2。

![](img/518796011cd6b760e862ec156566e935.png)

步骤 3：单击启动实例。

![](img/dbfbdd0926e1d1208849da2881205f34.png)

步骤 4：创建 EC2 实例总共有 7 个步骤。

**第一步：选择 AMI。**

![](img/364b458f831b55fb5a3b4f3caf3e1e8d.png)

**第二步：选择实例类型。**

![](img/b277b76bdd3ab2cc7d88af00df039cfd.png)

单击“下一步：配置实例详细信息”。

**第三步：选择实例详细信息。**

现在不要做任何更改，只需进入下一步。

![](img/c0f4da9159c594ddff29c69d450f987b.png)![](img/024087de5dbfcc45de084c979027955e.png)

单击“下一步：添加存储”。

**第四步：添加存储详细信息。**

![](img/6878de9de2e460e85c1b11b70baaa012.png)

不要更改任何内容，单击“下一步：添加标签”。

**第五步：** 我们这里可以有多个标签。

![](img/0a028ae443091539eeee4ed1b4c767f1.png)

在这里，您可以存储名称值对。

**需要创建一个安全组**

*您可以创建新的安全组，也可以选择现有的安全组。我已经创建了名为 `webdmz` 的安全组。*

*安全组用于允许访问 SSH、HTTP 和自定义 TCP 端口等端口，我们将通过这些端口访问我们的 URL。*

**创建安全组的步骤如下：**

单击服务中的 EC2。右手边是网络和安全。

![](img/132672d65dcc0ab8d97a4fdc2139e8eb.png)![](img/abddc75cea5580f3a65eec8747d966ee.png)![](img/6ccc56a7220c2c2e874d9ea95f4afcfb.png)

我们需要创建入站规则，即允许访问哪个端口。对于出站规则，我们不会改变任何东西，因为我们将允许每一个访问。

![](img/c490f19e698a12be0b6035fd4f6d8e5a.png)![](img/b5b7eabf6999c0aaa91d62b8ab7c2d91.png)

我们创建了一个名为 `webdmz` 的安全组。

**第六步：现在配置安全组。**

![](img/6ffe556eb5ae828f1941613d3a248f2f.png)

选择 `webdmz` 安全组。

**第七步：复习一切，启动。**

![](img/40ad1463e4b1fa1dc145f52a7520555a.png)

这是启动 EC2 实例所需的 7 个步骤。

步骤 5：一旦你点击启动，你会得到以下屏幕。

![](img/657bfc4cecbd7eba057d4b6e711d2ebf.png)

我们需要创建密钥对，一旦生成，我们可以在下一个应用程序中使用它。如果你是第一次，从下拉列表中创建新的一对。

![](img/3b4faefe24e1a0fe384018f78e5531d8.png)

给它起个名字，然后下载。现在单击启动实例。

步骤 6：你会得到以下信息。

![](img/0c61d431f9a5f058f6c743858429626b.png)![](img/31df30161c0a090b79e9fd2d48b52ce3.png)

现在你可以点击查看实例。

步骤 7：如果一切正常，你将看到以下状态为“正在运行”的屏幕。

![](img/11ea7030da992f0fe11726e896244d02.png)

步骤 8：现在我们需要登录，我们可以用 Putty 或终端（Mac）来完成。我会通过 Mac 向你解释。

打开“终端”并转到你的文件夹。

![](img/e3748eb608160e8a799c2d222e5507a1.png)

我们将密钥文件保存在 SSH 文件夹中。使用上述命令登录 EC2。

命令 1：`chmod 400 javaspringkey1.pem`【你的密钥文件名】

命令 2：`ssh ec2-user@[public IP] -I [keyFile].pem`

![](img/23bf3237629e0326ea9db8fab13c55b9.png)

恭喜你，你已经登录了你的第一个 EC2 实例。

## 我们将在 Eclipse 中创建一个简单的 Spring Boot 应用程序

步骤 1：在 Eclipse 中创建新的 Spring 项目。

![](img/a9332820a5df31d8d3ca5aff607db716.png)![](img/6d55eed7951c50d9abdb56d6f0523e70.png)![](img/815abacc74e1d2748e1ac368a3e685de.png)

只需添加这个方法并标注 `@RestTemplate`。

在 `pom.xml` 中添加以下内容。

![](img/0e42389a8d030d7900300f87af625ad7.png)

做 Maven 清理和安装。一旦这个过程完成，将在目标文件夹中创建一个 JAR 文件。

![](img/26af7e0f8b99fdd892db500d83271eeb.png)

现在我们已经创建了 EC2 实例，我们的 Spring Boot 应用程序也准备好了。现在，我们将在 AWS 上部署这个应用程序并执行 URL。

现在，我们将登录 EC2 实例并部署应用程序。

1. 我们将登录 EC2 实例。
2. 我们将检查 Java 的版本。它应该与用于编译的版本相同。
3. 我们不能直接将我们的 JAR 文件传输到 EC2 实例。首先，我们将我们的文件传输到 S3 桶，从 S3 桶，我们将部署到 EC2。

![](img/803312b6b5475a2fc8602a58c6a55769.png)

要安装 Java 1.8，请使用以下命令：

`yum install java-1.8.0-openjdk`

并按照说明进行操作。当你检查版本时，一旦安装了 Java：

`java version` 将显示 1.7，我们需要使用以下命令设置 Java 1.8：

`alternatives --config java`

![](img/0f5221075cd8d525e0937e97ad9613d2.png)

现在我们将 JAR 文件复制到 S3 桶，我们将创建 1 个桶。

[![](img/bb3b6d6a5a7a6157d83f26cd4a5f09bc.png)](https://www.youtube.com/watch?v=30YWIPQtW10)[![](img/af1a53519d6a5f96fae310cdb12113b6.png)](https://www.youtube.com/watch?v=YP4zNBdUlos)

存储桶的名称应该是唯一的。

![](img/1caeeb99d2f4854b20fabc6512bf8679.png)

一旦创建了桶，我们需要在这个桶中上传我们的 JAR 文件。

![](img/2b0da31ab48cdcc096c7d7b2ec2b683c.png)

将 JAR 文件从目标文件夹上传到此桶。

![](img/5a0dd138745c280f79070591ae5f102f.png)![](img/98ffdcdc4828950eb33d0d53246fd8cd.png)

只需点击这个文件并复制对象 URL：

`https://[bucketName].s3.amazonaws.com/<https://bucket123qwedfff.s3.amazonaws.com/SpringJava-aws-exe.jar>[fileName]`

![](img/c67afc001ad02db700a327b58de4f5c9.png)

在终端中使用：

`wget [url已复制]`

![](img/079ec0ee7077b32cc668004e933a04c4.png)

现在我们将运行命令来启动我们的应用程序：

`java -jar SpringJava-aws-exe.jar`

![](img/7dbb42bd5a60399a99edcf8f169ee8c8.png)![](img/40c97fc1378a64ada82889bf600061ea.png)![](img/2d593b9800bdb72497493a1099380005.png)![](img/cfe7fd7b6557e98e2a8ff3b68ee48804.png)

恭喜你，你已经在 AWS 中部署了你的应用程序。
