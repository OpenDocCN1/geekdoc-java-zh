
# 旧锁文件：`\data\db\mongod.lock`，可能意味着不干净的关机

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/mongodb/old-lock-file-datadbmongod-lock-probably-means-unclean-shutdown/>

当启动 mongoDB 服务器时，它遇到以下错误，mongoDB 服务器无法启动。

```
**************
old lock file: \data\db\mongod.lock.  probably means unclean shutdown
recommend removing file and running --repair
see: http://dochub.mongodb.org/core/repair for more information
*************
Mon May 09 12:37:43 [initandlisten] exception in initAndListen std::exception: old lock file, 
terminating
Mon May 09 12:37:43 dbexit:
Mon May 09 12:37:43 [initandlisten] shutdown: going to close listening sockets...
Mon May 09 12:37:43 [initandlisten] shutdown: going to flush diaglog...
Mon May 09 12:37:43 [initandlisten] shutdown: going to close sockets...
Mon May 09 12:37:43 [initandlisten] shutdown: waiting for fs preallocator...
Mon May 09 12:37:43 [initandlisten] shutdown: closing all files...
Mon May 09 12:37:43 closeAllFiles() finished
Mon May 09 12:37:43 dbexit: really exiting now 
```

## 解决办法

如果 mongoDB 机器崩溃或发出`kill -9`命令，这是一个常见的错误消息。简而言之，你的 mongoDB 崩溃了，你得修复它。要修复它：

1. 找到`data-directory\mongod.lock`文件，并删除它。

![mongodb lock file](img/7420d265bbedc40854dd00dc61159cf1.png "mongodb-locked-file")

2. 发出`mongod --repair`命令。

```
mongod --repair
Mon May 09 12:42:57 [initandlisten] db version v1.8.1, pdfile version 4.5
//......
Mon May 09 12:42:57 [initandlisten] shutdown: going to close listening sockets...
Mon May 09 12:42:57 [initandlisten] shutdown: going to flush diaglog...
Mon May 09 12:42:57 [initandlisten] shutdown: going to close sockets...
Mon May 09 12:42:57 [initandlisten] shutdown: waiting for fs preallocator...
Mon May 09 12:42:57 [initandlisten] shutdown: closing all files...
Mon May 09 12:42:57 closeAllFiles() finished
Mon May 09 12:42:57 [initandlisten] shutdown: removing fs lock...
Mon May 09 12:42:57 dbexit: really exiting now 
```

**注意**

关于 mongodb 修复的更多细节，请参考 [MongoDB Durability and Repair guide](http://web.archive.org/web/20190220142739/http://dochub.mongodb.org/core/repair)。[mongodb](http://web.archive.org/web/20190220142739/http://www.mkyong.com/tag/mongodb/)![](img/9401fe4590ab9c8692bcf71904a93743.png)
