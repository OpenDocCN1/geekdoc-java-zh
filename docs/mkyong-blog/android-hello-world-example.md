
# Android Hello World 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/android/android-hello-world-example/>

在本教程中，我们将向您展示如何在 Eclipse IDE + ADT 插件中创建一个简单的“hello world”Android 项目，并使用 Android 虚拟设备（AVD）运行它。Eclipse ADT 插件提供了简单的 Android 项目创建和管理、组件拖放、自动完成和许多有用的特性来加速您的 Android 开发周期。

## 开发步骤概述

1. 安装 Android SDK
2. 安装 ADT Eclipse 插件
3. 创建一个 Android 虚拟设备（AVD）
4. 用 Eclipse 创建 Android 项目（向导）
5. 编码它……
6. 在 Android 虚拟设备（AVD）中启动

## 本教程中使用的工具

1. JDK 1.6
2. Eclipse IDE 3.7，Indigo
3. Android SDK

## 1. 安装 Android SDK

访问这个 [Android SDK 页面](http://web.archive.org/web/20210421122722/https://developer.android.com/sdk/index.html)，选择哪个平台并安装。

在 Android SDK 安装文件夹中，运行“Android SDK 管理器”，选择你要开发的 Android 版本。

![android sdk manager](img/220d627ba993f539ad94543b3174f993.png "android-sdk-manager")

## 2. 安装 ADT Eclipse 插件

要将 Android SDK 与 Eclipse IDE 集成，需要安装 Eclipse ADT 插件。请参考本官方指南——“安装 ADT 插件”。

在 Eclipse IDE 中，选择“帮助”->“安装新软件……”，并输入以下 URL：

```java
https://dl-ssl.google.com/android/eclipse/
```

![android ADT plugin](img/cc6c01c7d3fc1fab346c3ebde9c9925a.png "android-adt-plugin")

> **Note**
>
> In my case, above ADT plugin is taking years to download, no idea why. If you are facing the similar problem, just download and install the ADT plugin manually, refer to this [ADT plugin troubleshooting guide](http://web.archive.org/web/20210421122722/https://developer.android.com/sdk/eclipse-adt.html#troubleshooting).

## 3. 创建一个 Android 虚拟设备（AVD）

在 Eclipse 中，可以访问 Eclipse 工具栏中的“Android 虚拟设备（AVD）”。单击“新建”创建一个 AVD。

![android avd manager](img/bb9294453b020bbd1e2487629971f3ce.png "android-avd-manager")

稍后，Eclipse 会将应用程序部署到这个 AVD 中。

## 4. 创建 Android 项目

在 Eclipse 中，选择“文件->新建->项目…”，“Android 项目”，并输入您的应用程序详细信息。Eclipse 将创建所有必要的 Android 项目文件和配置。

![Eclipse new android project wizard](img/fe9d578e3a3fad9017285aebeb343560.png "android-new-project")

![folder structure](img/b244f1c63cb46692de07d03bb8266c0a.png "android-hello-world")

## 5. 你好世界

定位生成的活动文件，修改一点输出一个字符串“Hello World”。

`文件: HelloWorldActivity.java`

```java
package com.mkyong.android;

import android.app.Activity;
import android.os.Bundle;
import android.widget.TextView;

public class HelloWorldActivity extends Activity {
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        TextView text = new TextView(this);
        text.setText("Hello World, Android - mkyong.com");
        setContentView(text);
    }
}
```

## 6. 演示

作为“Android 应用”运行，见输出。

![hello world output](img/816f38e6a32b8edf467b689bfb888f2f.png "android-hello-world-screen")

按下“主页”按钮（在右手边），你会注意到“HelloWorld”应用程序已成功部署在 Android 虚拟设备上。

![android deployed](img/9cd4b4f1959c9e30954b518c6da90755.png "android-hello-world-icon")

> **Note**
>
> This tutorial is more to example driven, not much explanation. For detail and complete explanation, please refer to the official [Android developer hello world tutorial](http://web.archive.org/web/20210421122722/https://developer.android.com/resources/tutorials/hello-world.html).

> **Firewall…**
>
> In my computer, the COMODO firewall is installed and blocked the deploying process, caused the connection between Eclipse ADT and AVD is blocked and failed to deploy. Just make sure your firewall is configured properly, or just turn it off for Android development 🙂

> **Debug Android application on real device**
>
> Sometime, “Android Virtual Device” is not enough to test some real phone functionalities, like led light, sensor and etc. Then you should refer to this [how to debug Android application on real device](http://web.archive.org/web/20210421122722/http://www.mkyong.com/android/android-debugging-on-real-device/).

## 下载源代码

Download it – [Android-HelloWorld.zip](http://web.archive.org/web/20210421122722/http://www.mkyong.com/wp-content/uploads/2011/11/Android-HelloWorld.zip) (15 KB)

## 参考

1. [安卓开发者](http://web.archive.org/web/20210421122722/https://developer.android.com/index.html)

Tags: [android](http://web.archive.org/web/20210421122722/https://mkyong.com/tag/android/) [hello world](http://web.archive.org/web/20210421122722/https://mkyong.com/tag/hello-world/)

<input type="hidden" id="mkyong-current-postId" value="10132">
