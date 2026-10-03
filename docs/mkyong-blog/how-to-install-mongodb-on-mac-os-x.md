
# 如何在 Mac OS X 上安装 MongoDB

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/mongodb/how-to-install-mongodb-on-mac-os-x/>

本指南向您展示如何在 Mac OS X 上安装 MongoDB。

- MongoDB 2.2.3
- Mac OS X 10.8.2

## 1. 下载 MongoDB

从[官网](http://web.archive.org/web/20221225155415/https://www.mongodb.org/downloads)获取 MongoDB：

```bash
$ cd ~/Download
$ tar xzf mongodb-osx-x86_64-2.2.3.tgz
$ sudo mv mongodb-osx-x86_64-2.2.3 /usr/local/mongodb
```

## 2. MongoDB 数据目录

默认情况下，MongoDB 将数据写入或存储到`/data/db`文件夹中。您需要手动创建这个文件夹并分配适当的权限。

```bash
$ sudo mkdir -p /data/db
$ whoami
mkyong
$ sudo chown mkyong /data/db
```

**注意**

需要设置权限，否则会出现以下锁定错误：

```text
Unable to create/open lock file: /data/db/mongod.lock
```

## 3. 将 MongoDB 的 `bin` 目录添加到 `PATH`

创建一个`~/.bash_profile`文件，并将`/usr/local/mongodb/bin`分配给`$PATH`环境变量，这样就可以轻松访问 MongoDB 的命令。

```bash
$ cd ~
$ pwd
/Users/mkyong
$ touch .bash_profile
$ vim .bash_profile

export MONGO_PATH=/usr/local/mongodb
export PATH=$PATH:$MONGO_PATH/bin

## restart terminal

$ mongo -version
MongoDB shell version: 2.2.3
```

## 4. 启动 MongoDB

使用`mongod`启动 MongoDB，使用`mongo`建立一个简单的 MongoDB 连接。

### 终端 1

```bash
$ mongod
MongoDB starting : pid=34022 port=27017 dbpath=/data/db/ 64-bit host=mkyong.local
//...
waiting for connections on port 27017
```

### 终端 2

```bash
$ mongo
MongoDB shell version: 2.2.3
connecting to: test
> show dbs
local	(empty)
```

**注意**

如果不想使用默认的`/data/db`文件夹，只需使用`--dbpath`指定其他路径：

```bash
$ mongod --dbpath /any-directory
```

## 5. 自动启动 MongoDB

要自动启动 MongoDB，请在 Mac 上创建一个启动作业。

```bash
$ sudo vim /Library/LaunchDaemons/mongodb.plist
```

将以下内容放入`/Library/LaunchDaemons/mongodb.plist`：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
  "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
  <key>Label</key>
  <string>mongodb
  <key>ProgramArguments</key>
  <array>
    <string>/usr/local/mongodb/bin/mongod
  </array>
  <key>RunAtLoad</key>
  <true/>
  <key>KeepAlive</key>
  <true/>
  <key>WorkingDirectory</key>
  <string>/usr/local/mongodb
  <key>StandardErrorPath</key>
  <string>/var/log/mongodb/error.log
  <key>StandardOutPath</key>
  <string>/var/log/mongodb/output.log
</dict>
</plist>
```

执行以下命令：

```bash
$ sudo launchctl load /Library/LaunchDaemons/mongodb.plist

$ ps -ef | grep mongo
    0    71     1   0  1:50PM ??         0:22.26 /usr/local/mongodb/bin/mongod
  501   542   435   0  2:23PM ttys000    0:00.00 grep mongo
```

尝试重启 Mac，MongoDB 会自动启动。

## 参考

1. [MongoDB 网站](http://web.archive.org/web/20221225155415/https://www.mongodb.org/)
2. [在 Mac OS X 上安装 MongoDB](http://web.archive.org/web/20221225155415/http://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/)
3. [launchd.plist 示例](http://web.archive.org/web/20221225155415/https://developer.apple.com/library/mac/#documentation/Darwin/Reference/ManPages/man5/launchd.plist.5.html)
4. [在 Mac OS X 上设计守护进程](http://web.archive.org/web/20221225155415/https://developer.apple.com/library/mac/#documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/DesigningDaemons.html)
5. [Mac 启动示例](http://web.archive.org/web/20221225155415/https://en.wikipedia.org/wiki/Launchd)
