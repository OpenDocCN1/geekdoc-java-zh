
# 如何在 AWS 弹性豆茎上部署 Angular Universal

> 原文：<https://medium.com/javarevisited/deploy-angular-universal-on-aws-elastic-beanstalk-14dcc44d960b?source=collection_archive---------0----------------------->

在做一个项目的时候，我花了很多时间将 Angular Universal 部署到服务器上进行服务器端渲染。我看了我找到的所有教程，以及所有关于这个话题的 Stackoverflow 问题。这可能是我在编码过程中最沮丧的经历。AWS 不时更新它的文档，而我们却被困在旧的教程中，并最终得到一些不存在或不再受支持的东西。

如果你也经历过这样的旅程，你就会知道我在说什么。这篇文章会让你今天非常开心。我还将向您展示如何建立代码管道，以及在构建步骤中需要做哪些修改。

有两种方法可以将 Angular Universal/Angular SSR 部署到 AWS ElasticBeanstalk：

1. 部署 Angular Universal 而不构建代码
2. 使用代码构建部署 Angular Universal

# 1. 部署 Angular Universal，无需构建代码

假设您已经将代码推送到 AWS CodeCommit，有两个步骤。在这种情况下，您必须手动构建您的应用程序并推送代码。

要构建您的应用程序，请运行以下命令：

```
npm run build:ssr
```

这将在源目录的根目录下创建一个构建文件夹。

现在修改 `package.json`，用下面的命令替换 `npm start`：

```
"start": "node angular-ssr/server/main.js"
```

## 1.1 建立一个 Elastic Beanstalk 环境

- 转到 AWS 并搜索 Elastic Beanstalk。点击创建新环境。
- 在下一步中，选择 Web 服务器环境，然后单击下一步。

- 这里有 4 个部分：

**第一步：创建一个 Web 服务器环境**

在此部分给出应用程序名称。

**步骤 2：环境信息**

选择环境名称，并根据您的选择选择可用的 URL。

**步骤 3：平台设置**

选择 Node.js 作为环境平台，并选择 Node.js 的最新版本。

**步骤 4：申请代码**

选择示例应用程序并配置更多选项。

在“更多”部分，单击“软件”部分的“编辑”并滚动到底部。在环境属性中，您应该添加截图中提到的端口和端口号。单击保存，将为您创建环境。

## 1.2 设置代码管道

这需要 4 个阶段来配置：

**1. 创建管道设置**

去 AWS 搜索 CodePipeline。创建一个新管道并给出管道名称。选择新的服务角色，然后转到下一步。

**2. 选择源阶段**

在源阶段，您需要选择仓库名称、分支和代码提取的源。

**3. 添加构建阶段**

**我们正在跳过构建阶段**，正如我之前提到的，我们正在部署没有 CodeBuild 的代码。如果您需要构建阶段，您可以向下滚动，查看连续构建和部署的 Angular Universal 部署的配置。

**4. 部署阶段**

在部署阶段，选择部署提供者作为 Elastic Beanstalk，并选择我们在 Elastic Beanstalk 配置的步骤 1 中创建的环境和应用程序的名称。现在，您可以单击“下一步”，查看所有设置，然后单击“创建”。

在做了所有这些之后，你应该能看到下面这样的东西。

一旦它像这样出现，转到 Elastic Beanstalk 并打开环境 URL，您应该能够看到您的应用程序。您可以看到我的应用程序已经启动并运行。

# 2. 使用代码构建部署 Angular Universal

在这种情况下，我们不必构建代码，您只需提交代码，构建将自动发生，它将自动部署代码，即持续集成和持续部署。

我们将遵循以下几个步骤：

1. 将配置文件添加到根文件夹
2. 配置 S3 存储桶来保存 `Procfile` 和 `.npmrc` 文件
3. 创建 AWS CodeBuild 环境
4. 更新代码管道环境以添加构建阶段

## 步骤 1：将配置文件添加到根文件夹

为此，向源目录的根目录添加两个文件。

**.npmrc**

```
# Force npm to run node-gyp also as root, preventing permission denied errors in AWS with npm@5unsafe-perm=true
```

**Procfile**

```
web: node angular-ssr/server/main.js
```

## 步骤 2：配置 S3 存储桶以保存 Procfile 和 .npmrc 文件

- 在常规配置中给出存储桶名称。
- 在对象中，所有权允许如下所述的所有公共访问。将其余设置保留为默认设置，并创建一个存储桶。
- 创建存储桶后，单击存储桶转到权限，编辑存储桶策略，添加以下规则，并使用**替换资源数组中的存储桶名称**。添加以下规则后，您的存储桶应在顶部显示可公开访问。
- **现在上传文件 `.npmrc` 和 `Procfile` 到你的存储桶中。**

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::your bucket name",
                "arn:aws:s3:::your bucket name/*"
            ]
        }
    ]
}
```

## 步骤 3：创建 AWS CodeBuild 环境

- 去 AWS 搜索 CodeBuild。创建新的构建项目。
- 在项目配置中，添加您选择的名称和描述。
- 选择源作为 AWS CodeCommit。如果你正在使用 GitHub 或其他一些源，选择它并添加仓库和分支名称，保留默认选择的其他设置，并跳到构建规范部分。
- 在构建规范部分选择插入构建命令并点击切换到编辑器，清除所有并添加下面的命令。**确保在环境变量和后构建命令中替换您的存储桶名称**。

```
version: 0.2
env:
    variables:
        CACHE_CONTROL: "86400"
        S3_BUCKET: "arn:aws:s3:::your bucket name"
        BUILD_FOLDER: "dist"
phases:
  install:
    runtime-versions:
        nodejs: 12
    commands:
        - echo Installing source NPM dependencies...
        - npm install
        - npm install -g @angular/cli@next
  build:
    commands:
        - echo Build started 
        - npm run build:ssr
  post_build:
    commands:
        - aws s3 cp s3://your bucket name/Procfile ./dist
        - aws s3 cp s3://your bucket name/.npmrc ./dist
        - bash -c "if [ "$CODEBUILD_BUILD_SUCCEEDING" == "0" ]; then exit 1; fi"

artifacts:
    files:
        - '**/*'
    base-directory: 'dist'
```

- 选择无工件，并选择 CloudWatch 来查看构建日志，然后单击创建构建项目。

## 步骤 4：更新代码管道环境以添加构建阶段

- 再次转到 AWS 并搜索 CodePipeline，编辑您已创建的管道，然后转到构建阶段并创建构建阶段。
- 将构建提供程序添加为 AWS CodeBuild，并选择我们在步骤 3 的构建项目中创建的项目名称，然后单击下一步。
- 现在去改变一些代码，并再次提交，去 CodePipeline。如果一切顺利，您将看到构建和部署成功。

现在转到 Elastic Beanstalk 的 URL，它应该会显示您部署的应用程序。

就这些了。这有点长，但非常有用，因为当我被困在如何做设置时，我的头很乱。你可以参考下面的 StackOverflow 链接来了解实际问题，并喜欢这个博客，投票支持下面的答案。

<https://stackoverflow.com/questions/70564063/angular-universal-build-command-to-include-package-json-at-root-level-of-dist-fo/70577526#70577526>

另外，阅读：

<https://javascript.plainenglish.io/personal-portfolio-using-angular-8-and-bootstrap-5dde6fc7cf9b>

<https://mehulkothari05.medium.com/how-i-earned-400-in-one-week-from-freelancing-86d50a80a760>

<https://mehulkothari05.medium.com/how-to-show-events-on-calender-to-your-application-c01605a6f3bc>

<https://javarevisited.blogspot.com/2018/06/5-best-courses-to-learn-angular.html>
