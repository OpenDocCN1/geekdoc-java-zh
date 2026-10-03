

# 如何在 Mac OS X 上运行 Apache Ant

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/ant/how-to-apache-ant-on-mac-os-x/>

在本教程中，我们将向您展示如何在 Mac OSX 上安装 Apache Ant。

## 工具

1. Apache Ant 1.9.4
2. mac OS X Yosemite 10.10

## 预装的 Apache Ant？

在旧版本的 Mac 中，Apache Ant 可能已经默认安装。检查 Apache Ant 是否已安装：

```bash
$ ant -v
```

## 1. 获取 Apache Ant

访问 [Apache Ant 网站](http://web.archive.org/web/20221225035450/https://ant.apache.org/bindownload.cgi)，获取 `.tar.gz` 文件。

![install-apache-ant-on-mac-osx](img/04d4a05026eb1d31d8c5cfa38d53dc17.png)

## 2. 提取文件

将下载的 `gz` 文件复制到您喜欢的位置，然后提取它。

```bash
$ cp ~/Downloads/apache-ant-1.9.4-bin.tar.gz .

$ cd ~
$ pwd
/Users/mkyong

$ tar vxf apache-ant-1.9.4-bin.tar.gz

x apache-ant-1.9.4/bin/ant
x apache-ant-1.9.4/bin/antRun
x apache-ant-1.9.4/bin/antRun.pl
x apache-ant-1.9.4/bin/complete-ant-cmd.pl
x apache-ant-1.9.4/bin/runant.pl
x apache-ant-1.9.4/bin/runant.py
x apache-ant-1.9.4/
x apache-ant-1.9.4/bin/
......

$ cd ~/apache-ant-1.9.4/bin
$ pwd
/Users/mkyong/apache-ant-1.9.4/bin

$ ant -v
Apache Ant(TM) version 1.9.4 compiled on April 29 2014
Trying the default build file: build.xml
Buildfile: build.xml does not exist!
Build failed
```

另外，Apache Ant 命令可以在文件夹 `$APACHE_ANT_FOLDER/bin` 中找到。

## 3. 设置环境变量

将命令 `ant` 设置为环境变量，这样您就可以在任何位置使用 `ant` 构建项目。

```bash
$ vim ~/.bash_profile
```

导出 `$ANT_HOME/bin`，保存并重启终端。

`~/.bash_profile`

```bash
export JAVA_HOME=$(/usr/libexec/java_home)
export GRADLE_HOME=/Users/mkyong/gradle
export M2_HOME=/Users/mkyong/apache-maven-3.1.1

# Apache Ant
export ANT_HOME=/Users/mkyong/apache-ant-1.9.4

# Export to PATH
export PATH=$PATH:$GRADLE_HOME/bin:$M2_HOME/bin:$ANT_HOME/bin
```

再次进行测试。现在，您可以在任何位置访问 `ant` 命令。

```bash
$ cd ~
$ pwd
/Users/mkyong

$ ant -v
Apache Ant(TM) version 1.9.4 compiled on April 29 2014
Trying the default build file: build.xml
Buildfile: build.xml does not exist!
Build failed
```

完成了。

## 参考

1. [Apache Ant 下载页面](http://web.archive.org/web/20221225035450/https://ant.apache.org/bindownload.cgi)
2. [如何在 Mac OSX 上安装 Apache Maven](http://web.archive.org/web/20221225035450/http://www.mkyong.com/maven/install-maven-on-mac-osx/)
3. [Linux：gzip 一个文件夹](http://web.archive.org/web/20221225035450/http://www.mkyong.com/linux/linux-how-to-gzip-a-folder/)

<input type="hidden" id="mkyong-current-postId" value="13540">

