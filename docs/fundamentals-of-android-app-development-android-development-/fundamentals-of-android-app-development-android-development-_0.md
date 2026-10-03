
# Android 应用开发基础：初学者学习 Android 技术、SQLite、Firebase 和 Unity 的 Android 开发（英文版）

献给`Sudha Mishra`，我的母亲，她慈爱的精神依然支持着我。

## 关于作者

`Sujit Kumar Mishra`是一位经验丰富的软件工程师，过去七年来一直与客户和合作伙伴一起设计技术解决方案。在职业生涯中，`Sujit Kumar Mishra`在`C# .Net`、`Java (Android)`、`PHP`、`SAP (MM)`以及数据库`SQL Server`、`MySQL`等关键 IT 活动中进行过。他曾在`Tata Steel`、`BPCL`、`Sun pharma`和`KPMG`担任高级软件职位和项目管理职位。

2020 年，`Sujit Kumar Mishra`创立了自己的网站，目前在那里担任创始人兼首席技术官。`Sujit Kumar Mishra`还写了其他四本书：小说《神秘岛 Zoya》、《Dot net & MVC 面试题：面试准备，如何致富》以及 2019 年出版的《一日数学》。在工作之外，`Sujit Kumar Mishra`是一位出演过电视和宝莱坞电影的演员。

## 谢谢

我想感谢几位在本书写作期间向我持续支持的人。首先，我要感谢我的父母和朋友`Anoop Sriwastawa`、`Pritesh Sawant`和`Harish`，感谢在我花费许多周末和晚上写作时包容我——没有他们的支持，我永远无法完成这本书。

如果没有 IT 团队中一些关键供应商和合作伙伴的支持，这本书就不会诞生。我感谢`Computer world`团队，特别是`Pritesh Sawant`，他为其中的一些新功能提供了宝贵的见解。最后，感谢`BPB Publications`给我这个机会为他们写我的第一本书。

## 前言

Android 技术是由美国 Google 开发的技术。它是全球销售最畅销、用户最多的技术。`Android framework`是一个我们可以为用户开发 Web 应用程序、移动应用程序、地图、多媒体应用和云服务的平台。在此，我们必须涵盖在开发过程中遇到问题的学生和专业人士最常见的问题解答。我在 IT 行业拥有六多年的工作经验。我必须从不同类型的来源收集信息，包括与同一领域的人见面并合作等，并且必须从书中找出问题所在以及如何解决它。

诚挚地感谢：

- 我的出版者`BPB publication`及其团队。他给我的生活带来了巨大的变化。他们总是指导并鼓励我工作。
- 读这些材料的 Android 书书读者，没有你们，它无法完成。
- 最后，一直鼓励我的朋友和家人。

## 序言

与目前现有的应用程序交付解决方案以及应用程序通常如何交付到物理手机相比，Android 的应用层化仍然是一项近期进展。这种旧的应用程序交付模型必须改变，以采用虚拟环境提供的完整特性和功能。

这种改变是为了解决如何向无状态虚拟机交付应用程序的问题。这种无状态或非持久的按需交付和构建虚拟机模型意味着终端用户并不“拥有”他们的虚拟机，而是根据需要分配一台全新的、新构建的机器。当他们下次登录时，将再次登录到一个新构建的设备。

App Volumes 提供了什么？从高层次来说，`App Volumes`提供实时应用交付，可以作为您的`android`实时服务器的交付系统。本书的主要目标是提供必要的信息，以理解 Android 应用以及如何工作。

## 第一章：Android 基础

### 第 1 节：介绍

应用层化作为一个概念以及如何工作。

### 第 2 节

本节提供了关于`Android App`要求的必要信息。

### 第 3 节：问题与解答

本节提供了关于 Android 设备的常见答案。

### 第 4 节：练习

本节提供了实用的解决方案，并在未来的 Android 应用中进行练习。

## 第二章：SQLite 与 Android

### 第 1 节

使用`SQLite`的实际截图显示了不同的组件以及如何工作。

### 第 2 节：问题与解答

本节提供了根据业务要求的分步说明以及如何工作。

### 第 3 节：Firebase 服务

对于 Android 设备，这是最常见的实时数据。

### 第 4 节：Unity 服务

包括 2D 和 3D 游戏开发以及 Android 界面。

### 第 5 节：Android 项目

这是 Android Android 开发者的实用部分。

## 实现示例

### 如何开发 SMS 应用

1. 在 Activity XML 中添加以下代码：

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#E0FFFF"
    tools:context=".MainActivity"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="@string/enter_mobile_number_and_messages"
    android:textAlignment="center"
    android:textScaleX="1.5"
    android:textSize="25dp"
    android:layout_marginTop="20dp">

    <EditText
        android:id="@+id/fstTxt"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:layout_marginTop="150dp"
        android:text="Mobile No" />

    <EditText
        android:id="@+id/mblTxt"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:ems="10" />

    <EditText
        android:id="@+id/secTxt"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Message"
        android:layout_marginLeft="100dp" />

    <EditText
        android:id="@+id/msgTxt"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:ems="10" />

    <Button
        android:id="@+id/smsbtnSend"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:text="Send SMS" />
</LinearLayout>
```

2. 在你的 Manifest 文件中添加权限：

```xml
<uses-permission android:name="android.permission.SEND_SMS" />
```

3. 在 MainActivity 的 Java 文件中添加以下代码：

```java
package com.homeworld.android;

import android.content.Intent;
import android.net.Uri;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.telephony.SmsManager;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    private EditText txtMobile;
    private EditText txtMessage;
    private Button btnms;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        txtMobile = (EditText) findViewById(R.id.mblTxt);
        txtMessage = (EditText) findViewById(R.id.msgTxt);
        btnms = (Button) findViewById(R.id.smsbtnSend);
        btnms.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                try {
                    Intent i = new Intent(Intent.ACTION_VIEW);
                    i.setData(Uri.parse("smto:" + txtMobile.toString()));
                    i.setType("vnd.android.mms");
                    i.putExtra("address", txtMobile.toString());
                    i.putExtra("body", txtMessage.toString());
                    startActivity(Intent.createChooser(i, "Send via Mobile:"));
                } catch (Exception e) {
                    Toast.makeText(MainActivity.this, "SMS to Send, Please try again", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }
}
```

### 如何创建音乐播放器

1. MainActivity 的 XML 代码：

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/background"
    tools:context=".MainActivity">

    <ImageButton
        android:id="@+id/btn_play"
        android:layout_width="90dp"
        android:layout_height="90dp"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="550dp"
        android:background="@drawable/play" />

    <ImageButton
        android:id="@+id/btn_pause"
        android:layout_width="90dp"
        android:layout_height="90dp"
        android:layout_marginLeft="10dp"
        android:background="@drawable/pause"
        android:layout_startOf="@+id/btn_play"
        android:layout_leftOf="@+id/btn_play" />

    <ImageButton
        android:id="@+id/btn_stop"
        android:layout_width="90dp"
        android:layout_height="90dp"
        android:layout_alignEnd="@+id/btn_play"
        android:layout_rightOf="@+id/btn_play"
        android:background="@drawable/stop" />
</RelativeLayout>
```

2. 在你的项目中添加新的 raw 文件夹并添加一个用于音乐`aaja.mp3`。

3. 在 Main Activity 文件中添加以下代码：



```java
package com.example.marinamusicplayer;

import android.media.MediaPlayer;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    Button play, pause, stop;
    int pausePosittion;
    MediaPlayer mediaPlayer;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        play = (Button) findViewById(R.id.btn_play);
        pause = (Button) findViewById(R.id.btn_pause);
        stop = (Button) findViewById(R.id.btn_stop);
        play.setOnClickListener(this);
        pause.setOnClickListener(this);
        stop.setOnClickListener(this);
    }

    @Override
    public void onClick(View view) {
        switch (view.getId()) {
            case R.id.btn_play:
                if (mediaPlayer == null) {
                    mediaPlayer = MediaPlayer.create(getApplicationContext(), R.raw.aaja);
                    mediaPlayer.start();
                } else if (!mediaPlayer.isPlaying()) {
                    mediaPlayer.seekTo(pausePosittion);
                    mediaPlayer.start();
                }
                break;
            case R.id.btn_pause:
                if (mediaPlayer != null) {
                    pausePosittion = mediaPlayer.getCurrentPosition();
                    mediaPlayer.pause();
                }
                break;
            case R.id.btn_stop:
                if (mediaPlayer != null) {
                    mediaPlayer.stop();
                    mediaPlayer = null;
                }
                break;
        }
    }
}
```

### 如何从一个 Activity 调用另一个 Activity

1. XML（`MainActivity`）的代码：

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/time"
    tools:context=".MainActivity"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Welcome to First Page"
    android:textSize="30dp"
    android:layout_centerHorizontal="true">

    <Button
        android:id="@+id/button"
        android:layout_width="90dp"
        android:layout_height="90dp"
        android:layout_marginTop="450dp"
        android:layout_centerHorizontal="true"
        android:text="Next" />
</RelativeLayout>
```

2. Main Activity Java 代码：

```java
package com.example.marina_secret;

import android.app.Activity;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {
    private Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        button = (Button) findViewById(R.id.button);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Next();
            }
        });
    }

    public void Next() {
        Intent intent = new Intent(this, Activity2.class);
        startActivity(intent);
    }
}
```

3. Activity 2 的 XML 代码：

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/accent"
    tools:context=".Activity2">

    <TextView
        android:id="@+id/titleid"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Second Page"
        android:textSize="30sp"
        android:textStyle="italic"
        android:centerHorizontal="true"
        android:textColor="#FFFFFF"/>

    <ImageView
        android:layout_width="450dp"
        android:layout_height="350dp"
        android:layout_below="@+id/titleid"
        android:src="@drawable/time"
        android:scaleType="fitXY"/>

    <Button
        android:id="@+id/button2"
        android:layout_width="90dp"
        android:layout_height="90dp"
        android:layout_marginTop="450dp"
        android:layout_centerHorizontal="true"
        android:text="Next"
        android:textSize="20dp"/>
</RelativeLayout>
```

4. Activity 2 的 Java 代码：

```java
package com.example.marina_secret;

import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class Activity2 extends AppCompatActivity {
    private Button button2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_2);
        button2 = (Button) findViewById(R.id.button2);
        button2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Next();
            }
        });
    }

    public void Next() {
        Intent intent = new Intent(this, MainActivity.class);
        startActivity(intent);
    }
}
```

### 如何在项目中添加横幅广告？

1. 在 Manifest 文件添加以下代码：

```xml
<uses-permission android:name="android.permission.ACCESS_NETWORK" />
```

在 `meta-data` 中添加以下代码（更多详情请访问 Google 更新网站）：

```xml
<meta-data
    name="com.google.android.ads.APPLICATION_ID"
    value="ca-app-pub-873399301722397/92347129"/>
```

2. 在你的 Main Activity 文件中添加以下代码：

```java
private AdView mAdView;
// 为我的项目添加横幅广告
Ads.initialize(this, "ca-app-pub-873399301722397/92347129");
mAdView = findViewById(R.id.adView);
AdRequest request = new AdRequest.Builder().build();
mAdView.loadAd(request);
```

3. 在 XML 文件中添加以下广告代码：

```xml
<com.google.android.gms.ads.AdView
    android:id="@+id/adView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_centerHorizontal="true"
    android:layout_alignParentBottom="true"
    android:layout_gravity="center"
    ads:adSize="BANNER"
    ads:adUnitId="ca-app-pub-873399301722397/923471291"/>
```

4. 在项目的 Gradle 中添加以下库：

```gradle
implementation 'com.google.android.gms:play-services-ads:17.2.1'
```

### 如何在 Android 中开发反馈表单？

1. 在你的清单文件中添加以下权限代码：

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

2. 在 layout 文件中添加以下代码：

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/time"
    tools:context=".MainActivity"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Welcome to First Page"
    android:textSize="30dp"
    android:layout_centerHorizontal="true">

    <Button
        android:id="@+id/button"
        android:layout_width="90dp"
        android:layout_height="90dp"
        android:layout_marginTop="450dp"
        android:layout_centerHorizontal="true"
        android:text="Next" />
</RelativeLayout>
```
