
# 如何在 Debian 上安装 Oracle JDK 8

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/java/how-to-install-oracle-jdk-8-on-debian/>

![java8-debian](img/4cb57e016eddd96e570e3a6dbe85ec23.png)

在本教程中，我们将向您展示如何在 Debian 上手动安装 Oracle JDK 8。

## 环境

1. Debian 7
2. 已安装 OpenJDK 1.7。（稍后切换到甲骨文 JDK 8）

在撰写本文时，OpenJDK 1.8 还没有包含在默认的`apt-get`存储库中。我只是不喜欢默认的`apt`库时间表，它总是伴随着旧的或过时的版本。

> **Note**
>
> This guide is tested in other Debian derivatives like Ubuntu 14 and Mint 1.7.2.

## 1. 快速检查

### 1.1 快速 Java 版本检查

```java
$ java -version
java version "1.7.0_75"
OpenJDK Runtime Environment (IcedTea 2.5.4) (7u75-2.5.4-1~deb7u1)
OpenJDK 64-Bit Server VM (build 24.75-b04, mixed mode)

$ javac -version
javac 1.7.0_75
```

安装了一个现有的 OpenJDK 1.7，没问题，我们会告诉你如何切换到 JDK 8。

### 1.2 通过`apt-cache`快速搜索

目前还没有`openjdk-8`。

```java
$ apt-cache search openjdk

...
openjdk-7-jre - OpenJDK Java runtime, using Hotspot JIT
openjdk-7-jre-headless - OpenJDK Java runtime, using Hotspot JIT (headless)
openjdk-6-jre - OpenJDK Java runtime, using Hotspot JIT
openjdk-6-jre-headless - OpenJDK Java runtime, using Hotspot JIT (headless)
...
```

## 2. 获取甲骨文 JDK 8

### 2.1 访问[甲骨文 JDK 下载页面](http://web.archive.org/web/20210815103840/http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

### 2.2 找到一个 Linux x64 版本

在这个例子中，我们将通过`wget`命令获得`jdk-8u66-linux-x64.tar.gz`。

```java
$ pwd
/home/mkyong

$ wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u66-b17/jdk-8u66-linux-x64.tar.gz
```

如果不想用`wget`（为什么？），只需手动下载文件并上传到您的服务器即可。

## 3. 提取到`/opt/jdk/`

### 3.1 将其提取到路径`/opt/jdk/jdk1.8.0_66`

```java
$ pwd
/home/mkyong

$ sudo mkdir /opt/jdk/
$ sudo mv ~/jdk-8u66-linux-x64.tar.gz /opt/jdk/
$ sudo cd /opt/jdk/

$ pwd
/opt/jdk/

$ sudo tar -zxf jdk-8u66-linux-x64.tar.gz
$ ls -ls
total 177056
     4 drwxr-xr-x 3 root root      4096 Oct 27 13:05 .
     4 drwxr-xr-x 8 uucp  143      4096 Oct  7 00:40 jdk1.8.0_66
177044 -rw-r--r-- 1 root root 181287376 Oct  8 15:56 jdk-8u66-linux-x64.tar.gz
```

> **Note**
>
> Alternatively, try this one line extraction command.

```java
$ sudo tar x -C /opt/jdk -f jdk-8u66-linux-x64.tar.gz
```

## 4. 安装 JDK

### 4.1 将`/opt/jdk/jdk1.8.0_66`作为`/usr/bin/java`和`/usr/bin/javac`的新 JDK 替代品

```java
$ sudo update-alternatives --install /usr/bin/java java /opt/jdk/jdk1.8.0_66/bin/java 100
$ sudo update-alternatives --install /usr/bin/javac javac /opt/jdk/jdk1.8.0_66/bin/javac 100
```

### 4.2 更新`java`和`javac`的默认 JDK

```java
$ update-alternatives --config java
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                            Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java   1051      auto mode
* 1            /opt/jdk/jdk1.8.0_66/bin/java                    100       manual mode
  2            /usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java   1051      manual mode

Press enter to keep the current choice[*], or type selection number: 1
update-alternatives: using /opt/jdk/jdk1.8.0_66/bin/java to provide /usr/bin/java (java) in manual mode
```

```java
$ update-alternatives --config javac
There are 2 choices for the alternative javac (providing /usr/bin/javac).

  Selection    Path                                         Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-7-openjdk-amd64/bin/javac   1051      auto mode
* 1            /opt/jdk/jdk1.8.0_66/bin/javac                100       manual mode
  2            /usr/lib/jvm/java-7-openjdk-amd64/bin/javac   1051      manual mode

Press enter to keep the current choice[*], or type selection number: 1
update-alternatives: using /opt/jdk/jdk1.8.0_66/bin/javac to provide /usr/bin/javac (javac) in manual mode
```

## 5. 确认

再次检查 Java 版本。

```java
$ java -version
java version "1.8.0_66"
Java(TM) SE Runtime Environment (build 1.8.0_66-b17)
Java HotSpot(TM) 64-Bit Server VM (build 25.66-b17, mixed mode)
root@hydra:/opt/jdk#

$ javac -version
javac 1.8.0_66
```

完成了。享受你的 Lambda！

## 6. 群众演员……怎么升级？

假设新的`jdk1.8.0_99`发布了，我们想升级它。

### 6.1 下载并解压 JDK

下载 JDK tar 文件并解压到`/opt/jdk/jdk1.8.0_99`。

### 6.2 更新 JDK

不言自明。

```java
# 6.2.1 Remove the existing alternatives - jdk1.8.0_66
$ sudo update-alternatives --remove java /opt/jdk/jdk1.8.0_66/bin/java
$ sudo update-alternatives --remove javac /opt/jdk/jdk1.8.0_66/bin/javac

# 6.2.2 Install new JDK alternatives - jdk1.8.0_99
$ sudo update-alternatives --install /usr/bin/java java /opt/jdk/jdk1.8.0_99/bin/java 100
$ sudo update-alternatives --install /usr/bin/javac javac /opt/jdk/jdk1.8.0_99/bin/javac 100

# 6.2.3 Update default JDK again, select /opt/jdk/jdk1.8.0_99
$ update-alternatives --config java
$ update-alternatives --config javac

# 6.2.4 Remove the old JDK folders
$ sudo rm -rf /opt/jdk/jdk1.8.0_66/
```

升级到即将发布的甲骨文 JDK 9 怎么样？你知道该怎么做🙂

## 参考

1. [使用 Debian 替代系统](http://web.archive.org/web/20210815103840/https://www.debian-administration.org/article/91/Using_the_Debian_alternatives_system)
2. [如何在 Debian 或 Ubuntu VPS 上手动安装 Oracle Java](http://web.archive.org/web/20210815103840/https://www.digitalocean.com/community/tutorials/how-to-manually-install-oracle-java-on-a-debian-or-ubuntu-vps)
3. Debian：改变默认的 Java 版本
4. [甲骨文 JDK 下载页面](http://web.archive.org/web/20210815103840/http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

Tags：[debian](http://web.archive.org/web/20210815103840/https://mkyong.com/tag/debian/) [install-java](http://web.archive.org/web/20210815103840/https://mkyong.com/tag/install-java/) [java8](http://web.archive.org/web/20210815103840/https://mkyong.com/tag/java8/) [mint](http://web.archive.org/web/20210815103840/https://mkyong.com/tag/mint/) [ubuntu](http://web.archive.org/web/20210815103840/https://mkyong.com/tag/ubuntu/)
