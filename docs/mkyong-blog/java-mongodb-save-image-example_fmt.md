
# Java MongoDB：保存图像示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/mongodb/java-mongodb-save-image-example/>

在本教程中，我们向您展示如何通过 **GridFS API** 将图像文件**保存到 MongoDB 中**。GridFS APIs 也能够服务于其他二进制文件，比如视频和音乐文件。

**注意**

如需详细说明，请阅读 [MongoDB GridFS 手册](http://web.archive.org/web/20191005215918/http://docs.mongodb.org/manual/applications/gridfs/)。

## 1. 保存图像

将图像文件保存到 MongoDB 的 `photo` 名称空间下的代码片段，并为保存的图像分配一个新的 `filename`。

```java
String newFileName = "mkyong-java-image";
File imageFile = new File("c:\\JavaWebHosting.png");
GridFS gfsPhoto = new GridFS(db, "photo");
GridFSInputFile gfsFile = gfsPhoto.createFile(imageFile);
gfsFile.setFilename(newFileName);
gfsFile.save();
```

## 2. 获取图像

通过 `filename` 获取保存图像的代码片段。

```java
String newFileName = "mkyong-java-image";
GridFS gfsPhoto = new GridFS(db, "photo");
GridFSDBFile imageForOutput = gfsPhoto.findOne(newFileName);
System.out.println(imageForOutput);
```

输出，图像保存为以下 JSON 格式。

```json
{
	"_id": {
		"$oid": "4dc9511a14a7d017fee35746"
	},
	"chunkSize": 262144,
	"length": 22672,
	"md5": "1462a6cfa27669af1d8d21c2d7dd1f8b",
	"filename": "mkyong-java-image",
	"contentType": null,
	"uploadDate": {
		"$date": "2011-05-10T14:52:10Z"
	},
	"aliases": null
}
```

## 3. 打印所有保存的图像

从 MongoDB 获取所有保存的文件并用 `DBCursor` 迭代它的代码片段。

```java
GridFS gfsPhoto = new GridFS(db, "photo");
DBCursor cursor = gfsPhoto.getFileList();
while (cursor.hasNext()) {
	System.out.println(cursor.next());
}
```

## 4. 保存到另一个图像

从 MongoDB 获取一个图像文件并将其输出到另一个图像文件的代码片段。

```java
String newFileName = "mkyong-java-image";
GridFS gfsPhoto = new GridFS(db, "photo");
GridFSDBFile imageForOutput = gfsPhoto.findOne(newFileName);
imageForOutput.writeTo("c:\\JavaWebHostingNew.png"); // 输出到新文件
```

## 5. 删除图像

删除图像文件的代码片段。

```java
String newFileName = "mkyong-java-image";
GridFS gfsPhoto = new GridFS(db, "photo");
gfsPhoto.remove(gfsPhoto.findOne(newFileName));
```

## 完整示例

通过 **Java MongoDB GridFS API** 处理图像的完整示例。解释见注释。

```java
package com.mkyong.core;

import java.io.File;
import java.io.IOException;
import java.net.UnknownHostException;
import com.mongodb.DB;
import com.mongodb.DBCollection;
import com.mongodb.DBCursor;
import com.mongodb.Mongo;
import com.mongodb.MongoException;
import com.mongodb.gridfs.GridFS;
import com.mongodb.gridfs.GridFSDBFile;
import com.mongodb.gridfs.GridFSInputFile;

/**
 * Java MongoDB : Save image example
 * 
 */

public class SaveImageApp {
	public static void main(String[] args) {

		try {

			Mongo mongo = new Mongo("localhost", 27017);
			DB db = mongo.getDB("imagedb");
			DBCollection collection = db.getCollection("dummyColl");

			String newFileName = "mkyong-java-image";

			File imageFile = new File("c:\\JavaWebHosting.png");

			// 创建一个 "photo" 命名空间
			GridFS gfsPhoto = new GridFS(db, "photo");

			// 从本地驱动器获取图像文件
			GridFSInputFile gfsFile = gfsPhoto.createFile(imageFile);

			// 设置一个新的文件名用于标识
			gfsFile.setFilename(newFileName);

			// 将图像文件保存到 MongoDB
			gfsFile.save();

			// 打印结果
			DBCursor cursor = gfsPhoto.getFileList();
			while (cursor.hasNext()) {
				System.out.println(cursor.next());
			}

			// 通过文件名获取图像文件
			GridFSDBFile imageForOutput = gfsPhoto.findOne(newFileName);

			// 将其保存到一个新的图像文件
			imageForOutput.writeTo("c:\\JavaWebHostingNew.png");

			// 从 MongoDB 中删除图像文件
			gfsPhoto.remove(gfsPhoto.findOne(newFileName));

			System.out.println("Done");

		} catch (UnknownHostException e) {
			e.printStackTrace();
		} catch (MongoException e) {
			e.printStackTrace();
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
}
```

程序结束时，在 `c:\JavaWebHostingNew.png` 中创建了一个新的图像文件。

## 参考

1. [MongoDB GridFS 规范](http://web.archive.org/web/20191005215918/http://docs.mongodb.org/manual/applications/gridfs/)

[image](http://web.archive.org/web/20191005215918/https://www.mkyong.com/tag/image/) [mongodb](http://web.archive.org/web/20191005215918/https://www.mkyong.com/tag/mongodb/)
